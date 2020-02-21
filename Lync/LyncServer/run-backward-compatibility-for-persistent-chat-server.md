---
title: Выполнение обратной совместимости для сервера сохраняемого чата
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Run backward compatibility for Persistent Chat Server
ms:assetid: 53f1a706-3104-4a94-8b4e-8badd9a066d6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204901(v=OCS.15)
ms:contentKeyID: 48184175
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 52d107c13d281001196dcad17604d0bfbbb9e522
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42189342"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="run-backward-compatibility-for-persistent-chat-server"></a>Выполнение обратной совместимости для сервера сохраняемого чата

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2013-02-21_

Сервер Lync Server 2013, конечная точка сервера сохраняемого чата позволяет создать простой URL-адрес, указывающий на пул серверов сохраняемого чата. Это полезно для устаревших клиентов (Microsoft Office Communications Server 2007 R2 Group Chat Server или Lync Server 2010, группового чата), так как пользователи могут вводить простой URL-адрес в ручной настройке при попытке установить устаревший клиент на компьютер, работающий под управлением Lync 2013 Сохраняемый чат. Эта конечная точка не используется сохраняемым чат и является обязательной только для устаревших клиентов. Это полезно для временного периода, в течение которого могут переноситься комнаты, но клиенты Lync 2013 не развернуты во всей Организации. Пользователи, работающие с Lync 2010 Group Chat (клиент), по-прежнему могут подключаться к внутреннему серверу сервера сохраняемого чата.

Вам не нужно создавать несколько конечных точек сервера сохраняемого чата; для каждого пула серверов сохраняемого чата требуется только один из них. Администраторы могут создавать несколько конечных точек (по одной на пул), но устаревшие клиенты могут быть настроены для подключения только к одному пулу в каждый момент времени. В обычном или основном сценарии устаревшее развертывание представляет собой только один пул. Новое развертывание обычно переносит этот пул на новый Lync Server 2013 и может добавить некоторые новые дополнительные пулы серверов сохраняемого чата.

Этот основной сценарий обычно придерживается следующего шаблона.

  - Администрирование пользователей с помощью одного пула Lync Server 2010, пула групп чата и клиентов Lync 2010 Group Chat подключается к этому пулу с помощью определенного известного пользователя (SIP по умолчанию:\<OCSChat@\>имя_домена. com или аналогичный). Пользователи входят в доменные службы Active Directory с поддержкой SIP, а служба поиска регистрирует их для получения входящих запросов.

  - Затем необходимо установить сервер сохраняемого чата Lync Server 2013 и пул серверов сохраняемого чата.

  - В течение того времени, когда пользователи в сети отсутствуют (например, в выходные дни), выполняются следующие действия.
    
      - Выключите Lync Server 2010, сгруппируйте чат.
    
      - Перенос данных из пула Lync Server 2010, группового чата в пул серверов сохраняемого чата Lync Server 2013.
    
      - Удаление известного пользователя из доменных служб Active Directory.
    
      - Создается новая *конечная точка устаревшего развертывания* с тем же самым SIP URI, что и у ранее удаленного широко известного пользователя.
    
      - Запустите серверы сервера сохраняемого чата Lync Server 2013.

  - Пользователи входят в систему с помощью Lync 2010 Group Chat (клиент) и подключаются к их данным без необходимости изменять конфигурацию.

  - Позже вы можете списать Lync Server 2010 и групповой чат. Затем вы можете развернуть Lync Server 2013, сервер сохраняемого чата и установить новые пулы серверов сохраняемого чата Lync Server 2013.

Для получения дополнительных сведений о переносе с Lync Server 2010, групповой чат на Lync Server 2013, сервер сохраняемого чата, ознакомьтесь со статьей [Миграция с Lync server 2010, группового чата или Office Communications Server 2007 R2 на Lync server 2013 и сервер сохраняемого чата](migration-from-lync-server-2010-group-chat-or-office-communications-server-2007-r2-group-chat-to-lync-server-2013-persistent-chat-server.md).

Для запуска обратной совместимости (для создания конечной точки сервера сохраняемого чата, указывающей на пул серверов сохраняемого чата, который может использоваться клиентами пула группового чата прежних версий):

    New-CsPersistentChatEndpoint -SipAddress <CO name, ex. persistentchat@contoso.com> -PersistentChatPoolFqdn <pool FQDN, like pcpool.contoso.com>

Затем настройте клиенты сохраняемого чата, чтобы использовать этот SIP адрес в качестве объекта контакта. SIP-адрес создается с помощью командлета **New-CsPersistentChatEndpoint** для определенного пула серверов сохраняемого чата.

Чтобы добавить конечную точку сервера сохраняемого чата с помощью интерфейса командной строки Windows PowerShell, рассмотрим следующий пример. В этом случае настраивается контактный объект с именем "persistentchat" в топологии contoso.com", где полное доменное имя пула — "pcpool.contoso.com".

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

