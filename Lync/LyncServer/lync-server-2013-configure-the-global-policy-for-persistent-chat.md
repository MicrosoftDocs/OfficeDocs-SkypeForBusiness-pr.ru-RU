---
title: 'Lync Server 2013: настройка глобальной политики для сохраняемого чата'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure the global policy for Persistent Chat
ms:assetid: 6176eb5c-19de-4c07-bcc0-2e38f8965966
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204951(v=OCS.15)
ms:contentKeyID: 48184323
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 236023756f8d2c917812d38f5a03da8dd4c40b5b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34841315"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-the-global-policy-for-persistent-chat-in-lync-server-2013"></a>Настройка глобальной политики для сохраняемого чата в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-10-06_

Вы можете использовать глобальную политику по умолчанию, чтобы включить параметры сохраняемого чата для всех пользователей в развертывании. Вы также можете указать дополнительные политики для сайтов и пользователей, которые должны включать или отключать сохраняемый чат для конкретных пользователей и сайтов.

Вы не можете удалить глобальную политику. При попытке удалить его в конфигурации восстанавливаются значения по умолчанию.

<div>


> [!NOTE]  
> Чтобы настроить и использовать сохраняемый сервер чата, необходимо сначала использовать Topology Builder, чтобы добавить в топологию постоянную поддержку сервера чата, а затем опубликовать топологию. Подробные сведения о том, <A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">как добавить сохраняемый сервер чата в развертывание в среде Lync server 2013, можно</A> найти в документации по развертыванию.<BR>Чтобы настроить параметры конфигурации сервера для сохраняемого чата, ознакомьтесь с разстройкой <A href="lync-server-2013-configure-persistent-chat-server-options-globally-or-for-persistent-chat-server-pool.md">Параметры сервера сохраняемого чата глобально или для постоянного пула серверов чатов в Lync server 2013</A> в документации по развертыванию.



</div>

<div>

## <a name="to-configure-the-global-policy-for-persistent-chat"></a>Настройка глобальной политики для сохраняемого чата

1.  Войдите в систему на любом компьютере во внутреннем развертывании с помощью учетной записи пользователя, которому назначена роль CsPersistentChatAdministrator, CsAdministrator или CsUserAdministrator.

2.  В меню **Пуск** выберите Панель управления Lync Server или откройте окно браузера и введите URL-адрес администратора. Дополнительные сведения о различных способах, которые можно использовать для запуска панели управления Lync Server, приведены в разделе [Открытие средства администрирования Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md) в документации по эксплуатации.
    
    <div>
    

    > [!IMPORTANT]  
    > Вы также можете использовать командлеты Windows PowerShell. Дополнительные сведения можно найти в разделе <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">Настройка сервера сохраняемого чата с помощью командлетов Windows PowerShell</A> в документации по развертыванию.

    
    </div>

3.  На панели управления Lync Server нажмите кнопку **сохраняемый чат**и выберите пункт **Политика сохраняемого чата**.

4.  Нажмите пункт **Глобальная** в списке политик, выберите **Изменить**, затем **Показать сведения**.

5.  В окне **Изменение политики сохраняемого чата — глобальная политика** выполните следующие действия.
    
      - В поле **Имя** укажите новое имя глобальной политики, если не следует использовать значение по умолчанию "Глобальная".
    
      - В разделе **Описание**укажите сведения о политике пользователя (например, "Глобальная политика для централситенаме").
    
      - Чтобы управлять сохраняемым чат для всех сайтов и пользователей, не контролируемых с помощью политики сайта или политики пользователя, установите или снимите флажок **включить сохраняемый чат** .

6.  Нажмите **Исполнить**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

