---
title: Организация обратной совместимости для сервера сохраняемого чата
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Run backward compatibility for Persistent Chat Server
ms:assetid: 53f1a706-3104-4a94-8b4e-8badd9a066d6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204901(v=OCS.15)
ms:contentKeyID: 48184175
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b512d18449c881efd856674477a727cec137b64c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848900"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="run-backward-compatibility-for-persistent-chat-server"></a>Организация обратной совместимости для сервера сохраняемого чата

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2013-02-21_

Сервер Lync Server 2013, постоянная конечная точка сервера чата предоставляет способ создания простого URL-адреса, указывающего на пул серверов сохраняемого чата. Это полезно для устаревших клиентов (Microsoft Office Communications Server 2007 R2 Group Chat Server или Lync Server 2010, групповой чат), так как пользователи могут вводить простой URL-адрес в ручном режиме при попытке указать старый клиент на компьютер с Lync 2013. Сохраняемый чат. Эта конечная точка не используется сохраняемым чат и требуется только для устаревших клиентов. Это полезно для временного периода, в котором может быть перенесены помещения, но клиенты Lync 2013 не развернуты во всей Организации. Пользователи, работающие в Lync 2010 Group Chat (клиент), смогут по-прежнему подключаться к серверу сохраняемого сервера обратного чата.

Вам не нужно создавать несколько конечных точек сервера для сеансов чата. для каждого пула серверов "сохраняемый чат" требуется только один из них. Администраторы могут создать несколько конечных точек (для одного пула), но старые клиенты можно настроить так, чтобы они могли подключаться только к одному пулу за один раз. В стандартном или обычном варианте развертывание устарело только для одного пула. Новое развертывание обычно переносит этот пул на новый сервер Lync Server 2013 и может добавить новые дополнительные пулы серверов для сохраняемого чата.

Этот наиболее распространенный сценарий, как правило, следует за следующим шаблоном:

  - Администрирование пользователей с помощью одного из Lync Server 2010, пула групп чата, а также клиентов группового чата Lync 2010 подключаются к этому пулу с помощью известного пользователя (SIP: оксчат @\<domainName\>. com или аналогичного). Пользователи входят в доменные службы Active Directory с поддержкой SIP, а служба поиска регистрирует их для получения входящих запросов.

  - Затем вы установите сервер для Lync Server 2013 и пул серверов для сохраняемого чата.

  - Когда пользователи обычно не в сети (например, выходные), выполните указанные ниже действия.
    
      - Отключите Lync Server 2010, групповой чат.
    
      - Перенесите данные из пула Lync Server 2010, группового чата в пул серверов для сервера Lync Server 2013 (сохраняемый чат).
    
      - Удалите известного пользователя из доменных служб Active Directory.
    
      - Создайте новую *конечную точку* с тем же URI SIP, что и у ранее известного пользователя.
    
      - Запустите сервер Lync Server 2013, сохраняемый сервер чата.

  - Войдите в систему с помощью Lync 2010 Group Chat (клиент) и подключитесь к своим данным, не изменяя конфигурацию.

  - Позже вы можете списать Lync Server 2010, групповой чат. Затем вы можете развернуть Lync Server 2013, сохраняемый сервер чата и установить новый серверный пул для Lync Server 2013.

Сведения о переходе с Lync Server 2010, групповой чат на Lync Server 2013 и сохраняемый сервер чатов можно найти в разделе [Миграция с Lync server 2010, группового чата или Office Communications Server 2007 R2 Group Chat на Lync server 2013 и сохраняемый сервер чата](migration-from-lync-server-2010-group-chat-or-office-communications-server-2007-r2-group-chat-to-lync-server-2013-persistent-chat-server.md).

Для выполнения обратной совместимости (чтобы создать конечную точку сервера чатов, указывающую на пул сервера сохраняемого чата, который может использоваться клиентами группового чата старого пула):

    New-CsPersistentChatEndpoint -SipAddress <CO name, ex. persistentchat@contoso.com> -PersistentChatPoolFqdn <pool FQDN, like pcpool.contoso.com>

Затем настройте в клиентах сохраняемого чата использование адреса SIP в качестве объекта контакта. Адрес SIP создается с помощью командлета **New-ксперсистентчатендпоинт** для определенного пула серверов сохраняемого чата.

Чтобы добавить конечную точку сервера для работы с сохраняемым чат с помощью интерфейса командной строки Windows PowerShell, рассматривайте пример ниже. В этом случае вы настраиваете объект Contact именем "персистентчат" в топологии "contoso.com", где полное доменное имя (FQDN) пула имеет значение "pcpool.contoso.com":

    New-CsPersistentChatEndpoint -SipAddress sip:persistentchat@contoso.com -PersistentChatPoolFqdn pcpool.contoso.com

<div>

## <a name="see-also"></a>См. также


[Миграция с групповой беседы в Lync Server 2010 или Office Communications Server 2007 R2 на сервер сохраняемого сеанса беседы в Lync Server 2013](migration-from-lync-server-2010-group-chat-or-office-communications-server-2007-r2-group-chat-to-lync-server-2013-persistent-chat-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

