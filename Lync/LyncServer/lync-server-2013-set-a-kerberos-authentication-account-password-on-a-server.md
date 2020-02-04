---
title: 'Lync Server 2013: установка пароля учетной записи Kerberos для проверки подлинности на сервере'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Set a Kerberos authentication account password on a server
ms:assetid: 902d3292-678d-4512-9248-586053cb638b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398734(v=OCS.15)
ms:contentKeyID: 48184787
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 97130b93052c0e14e1e4b4863be8ceea6118db05
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764705"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="set-a-kerberos-authentication-account-password-on-a-server-in-lync-server-2013"></a>Установка пароля учетной записи Kerberos для проверки подлинности на сервере в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-01-16_

Для успешного выполнения этой процедуры необходимо войти в систему в качестве пользователя, который является членом группы Рткуниверсалсерверадминс.

Необходимо настроить пароль для учетной записи Kerberos для каждого сайта, который содержит серверы переднего плана, серверы стандартных выпусков и режиссеров. Вы можете настроить пароль, запустив командлет **Set-кскерберосаккаунтпассворд** Windows PowerShell на одном сервере сайта (например, на одном сервере переднего плана). Для каждого сайта необходимо выполнить командлет **Set-кскерберосаккаунтпассворд** . Командлет настраивает службы IIS для службы веб-служб, а затем задает пароль для учетной записи компьютера в доменных службах Active Directory. Альтернативный метод, зависящий от того, какой параметр используется с командлетом, настраивает IIS на одном сервере при использовании другого сервера, настроенного в качестве источника пароля учетной записи Kerberos.

При использовании командлета **Set-кскерберосаккаунтпассворд** для задания пароля Kerberos устанавливает пароль в строку, сгенерированную случайным образом. Этот командлет связывается со всеми экземплярами служб IIS на всех центральных сайтах Lync Server 2013, которым назначена эта учетная запись.

<div>

## <a name="to-set-a-password-for-a-kerberos-authentication-account"></a>Настройка пароля для учетной записи проверки подлинности Kerberos

1.  Войдите на любой компьютер домена с помощью командной консоли Lync Server Management Shell, установленной как участник группы Рткуниверсалсерверадминс.

2.  Запустите командную консоль Lync Server Management Shell: нажмите кнопку **Пуск**, выберите **все программы**, а затем — **Microsoft Lync Server 2013**, а затем — **Командная консоль Lync Server Management Shell**.

3.  В командной строке выполните следующие две команды:
    
        Set-CsKerberosAccountPassword -UserAccount "Domain\UserAccount"
    
    Например:
    
        Set-CsKerberosAccountPassword -UserAccount "contoso\KerbAuth"
    
    <div>
    

    > [!NOTE]  
    > Параметр UserAccount необходимо указать с помощью формата домен \ пользователь. Формат User@Domain. расширение не поддерживается для ссылок на объект компьютера, созданный для целей проверки подлинности Kerberos.

    
    </div>
    
    <div>
    

    > [!IMPORTANT]  
    > После внесения изменений в проверку подлинности Kerberos (например, для добавления учетной записи или удаления учетной записи) необходимо запустить команду <STRONG>Enable-кстопологи</STRONG> в командной строке оболочки Lync Server Management Shell.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

