---
title: 'Lync Server 2013: назначение учетной записи проверки подлинности Kerberos для сайта'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Assign a Kerberos authentication account to a site
ms:assetid: 3d9c587c-c8b8-4f81-8ed9-1458a31fc292
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425901(v=OCS.15)
ms:contentKeyID: 48183929
ms.date: 04/18/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0c706f9fdd8932456a9f1617e55dc9231dbd6a84
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34841754"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="assign-a-kerberos-authentication-account-to-a-site-in-lync-server-2013"></a>Назначение учетной записи проверки подлинности Kerberos для сайта в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2017-04-18_

Для успешного выполнения этой процедуры необходимо войти в систему в качестве пользователя, который является членом группы Рткуниверсалсерверадминс.

После создания учетной записи Kerberos ее необходимо назначить сайту. Это сайт Lync Server 2013, а не сайт Active Directory. Вы можете создать несколько учетных записей проверки подлинности Kerberos для каждого развертывания, но вы можете назначить сайту только одну учетную запись. Чтобы назначить сайту ранее созданную учетную запись для проверки подлинности Kerberos, выполните описанные ниже действия. Подробнее о том, как создать учетную запись Kerberos, можно найти [в разделе Создание учетной записи проверки подлинности Kerberos в Lync Server 2013](lync-server-2013-create-a-kerberos-authentication-account.md).

<div>

## <a name="to-assign-a-kerberos-authentication-account-to-a-site"></a>Назначение учетной записи проверки подлинности Kerberos сайту

1.  Войдя в группу Рткуниверсалсерверадминс, войдите в домен на компьютере с Lync Server 2013 или на компьютер, на котором установлены средства администрирования.

2.  Запустите командную консоль Lync Server Management Shell: нажмите кнопку **Пуск**, выберите **все программы**, а затем — **Microsoft Lync Server 2013**, а затем — **Командная консоль Lync Server Management Shell**.

3.  В командной строке выполните следующие две команды:
    
       ```
        New-CsKerberosAccountAssignment -UserAccount "Domain\UserAccount"
                  -Identity "site:SiteName"
       ```          
    
       ```
        Enable-CsTopology
       ```
    
    Например:
    
       ```
        New-CsKerberosAccountAssignment -UserAccount "contoso\kerbauth"
                  -Identity "site:redmond"
       ```
    
       ```
        Enable-CsTopology
       ```
    
    <div class="">
    

    > [!NOTE]  
    > Параметр UserAccount необходимо указать с помощью формата домен \ пользователь. Формат "пользовательский @ домен. расширение" не поддерживается для ссылок на объекты компьютера, созданные для проверки подлинности Kerberos.

    
    </div>

4.  **Необязательно**: возможно, вы настроили для своих веб-служб полное доменное имя (FQDN), как и в случае [изменения URL — в Lync Server 2013](lync-server-2013-change-the-web-services-url.md). В этом случае вам потребуется также добавить SPN для этого полного доменного имени. Например, если полное доменное имя — WebService. contoso. local, вы можете выполнить следующие действия:
    
        setspn -S http/webservices.contoso.local kerbauth

5.     
    <div class="">
    

    > [!IMPORTANT]  
    > После внесения изменений в проверку подлинности Kerberos (например, для добавления учетной записи или удаления учетной записи) необходимо запустить команду <STRONG>Enable-кстопологи</STRONG> в командной строке оболочки Lync Server Management Shell.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

