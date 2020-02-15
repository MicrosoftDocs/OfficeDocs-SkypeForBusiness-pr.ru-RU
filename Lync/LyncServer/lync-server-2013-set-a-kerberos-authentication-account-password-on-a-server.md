---
title: 'Lync Server 2013: Установка пароля учетной записи проверки подлинности Kerberos на сервере'
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
ms.openlocfilehash: 9799be0fda2b1a3c5b7765774b1f9e3199cc61f3
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42051663"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="set-a-kerberos-authentication-account-password-on-a-server-in-lync-server-2013"></a>Установка пароля учетной записи проверки подлинности Kerberos на сервере в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-01-16_

Чтобы успешно выполнить данную процедуру, войдите в систему как пользователь, являющийся членом группы RTCUniversalServerAdmins.

Необходимо настроить пароль для учетной записи Kerberos для каждого узла с интерфейсными серверами, серверами Standard Edition и Директорами. Вы можете настроить пароль, выполнив командлет **Set-кскерберосаккаунтпассворд** Windows PowerShell на одном сервере сайта (например, на одном сервере переднего плана). Для каждого сайта необходимо выполнить командлет **Set-кскерберосаккаунтпассворд** . Командлет настраивает службы IIS для службы веб-служб, а затем задает пароль учетной записи компьютера в доменных службах Active Directory. Альтернативный метод, основанный на том, какой параметр используется с командлетом, настраивает службы IIS на одном сервере, при этом использует другой сервер, настроенный как источник пароля учетной записи Kerberos.

При использовании командлета **Set-CsKerberosAccountPassword** для установки пароля, Kerberos задает в качестве пароля случайно созданную строку. Этот командлет связывает все экземпляры служб IIS на всех центральных сайтах Lync Server 2013, которым назначена эта учетная запись.

<div>

## <a name="to-set-a-password-for-a-kerberos-authentication-account"></a>Установка пароля учетной записи для проверки подлинности Kerberos

1.  Выполните вход на любой компьютер домена с установленной консолью управления Lync Server в качестве члена группы RTCUniversalServerAdmins.

2.  Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.

3.  Выполните две следующие команды в командной строке:
    
        Set-CsKerberosAccountPassword -UserAccount "Domain\UserAccount"
    
    Например:
    
        Set-CsKerberosAccountPassword -UserAccount "contoso\KerbAuth"
    
    <div>
    

    > [!NOTE]  
    > Необходимо указать параметр UserAccount в формате "Домен\пользователь". Формат "Пользователь@домен.расширение" не поддерживается для указания объектов компьютера, созданных для проверки подлинности Kerberos.

    
    </div>
    
    <div>
    

    > [!IMPORTANT]  
    > После внесения изменений в проверку подлинности Kerberos, например для добавления учетной записи или удаления учетной записи, необходимо выполнить команду <STRONG>Enable – CsTopology</STRONG> в командной строке командной консоли Lync Server.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

