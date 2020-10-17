---
title: 'Lync Server 2013: Назначение учетной записи проверки подлинности Kerberos сайту'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign a Kerberos authentication account to a site
ms:assetid: 3d9c587c-c8b8-4f81-8ed9-1458a31fc292
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425901(v=OCS.15)
ms:contentKeyID: 48183929
ms.date: 04/18/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e6137224f313238dae33462298931167ba7bb810
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48529526"
---
# <a name="assign-a-kerberos-authentication-account-to-a-site-in-lync-server-2013"></a>Назначение учетной записи проверки подлинности Kerberos для сайта в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2017-04-18_

Чтобы успешно выполнить эту процедуру, вам следует выполнить вход в качестве члена группы RTCUniversalServerAdmins.

После создания учетной записи Kerberos вам следует назначить ее сайту. Это сайт Lync Server 2013, а не сайт Active Directory. Для одного развертывания вы можете создать несколько учетных записей для проверки подлинности Kerberos, однако сайту можно назначить всего одну из них. Используйте описанную ниже процедуру, чтобы назначить сайту ранее созданную учетную запись для проверки подлинности Kerberos. Более подробную информацию о создании учетной записи Kerberos можно узнать [в статье Создание учетной записи проверки подлинности Kerberos в Lync Server 2013](lync-server-2013-create-a-kerberos-authentication-account.md).

<div>

## <a name="to-assign-a-kerberos-authentication-account-to-a-site"></a>Назначение учетной записи для проверки подлинности Kerberos сайту

1.  В качестве члена группы RTCUniversalServerAdmins Войдите на компьютер в домене, на котором работает Lync Server 2013 или на компьютер, на котором установлены средства администрирования.

2.  Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.

3.  Выполните две следующие команды в командной строке:
    
       ```powershell
        New-CsKerberosAccountAssignment -UserAccount "Domain\UserAccount"
                  -Identity "site:SiteName"
       ```          
    
       ```powershell
        Enable-CsTopology
       ```
    
    Например:
    
       ```powershell
        New-CsKerberosAccountAssignment -UserAccount "contoso\kerbauth"
                  -Identity "site:redmond"
       ```
    
       ```powershell
        Enable-CsTopology
       ```
    
    <div class="">
    

    > [!NOTE]  
    > Вам следует указать параметр UserAccount, используя формат «домен\пользователь». Использование формата «пользователь@домен.расширение» для ссылки на объекты-компьютеры, созданные для проверки подлинности Kerberos, не поддерживается.

    
    </div>

4.  **Необязательно**: возможно, вы настроили полное доменное имя переопределения (полное доменное имя) для своих веб-служб, как в случае [изменения URL-адрес веб-служб в Lync Server 2013](lync-server-2013-change-the-web-services-url.md). В этом случае вам потребуется также добавить имя субъекта-службы для полного доменного имени. Например, если полное доменное имя было: WebServices. contoso. local, запустите:
    
    ```console
    setspn -S http/webservices.contoso.local kerbauth
    ```
5.     
    <div class="">
    

    > [!IMPORTANT]  
    > После внесения изменений в проверку подлинности Kerberos, например для добавления учетной записи или удаления учетной записи, необходимо выполнить команду <STRONG>Enable – CsTopology</STRONG> в командной строке командной консоли Lync Server.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

