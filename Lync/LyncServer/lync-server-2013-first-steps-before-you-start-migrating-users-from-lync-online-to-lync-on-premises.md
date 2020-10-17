---
title: 'Lync Server 2013: прежде чем приступить к переносу пользователей из Lync Online в локальную среду Lync, выполните указанные ниже действия.'
description: 'Lync Server 2013: прежде чем приступить к переносу пользователей из Lync Online в локальную среду Lync.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: First steps before you start migrating users from Lync Online to Lync on-premises
ms:assetid: 98245b04-ded4-4186-8da3-ba1c554b5c39
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn689118(v=OCS.15)
ms:contentKeyID: 62258123
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 408820e461c0a9f7c0beaaaae3a502802048d3f5
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48564205"
---
# <a name="first-steps-before-you-start-migrating-users-from-lync-online-to-lync-on-premises-in-lync-server-2013"></a>Прежде чем приступить к переносу пользователей из Lync Online в локальную среду Lync в Lync Server 2013, выполните следующие действия.

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2014-05-08_

Перед перемещением пользователей Lync Online в локальную среду убедитесь, что выполняются все перечисленные ниже условия.

  - Локальная среда Lync Server должна быть полностью развернута и проверена. Дополнительные сведения см. в статье [deploy Lync Server 2013](lync-server-2013-deploying-lync-server.md).

  - Для клиента Lync Online необходимо настроить доступ к удаленной оболочке PowerShell.
    
    Для этого сначала установите модуль Lync Online для Windows PowerShell, который вы можете скачать здесь: [https://go.microsoft.com/fwlink/p/?LinkId=391911](https://go.microsoft.com/fwlink/p/?linkid=391911) .
    
    После установки модуля можно установить удаленный сеанс, введя следующие командлеты в командной консоли Lync Server:
    
       ```PowerShell
        Import-Module LyncOnlineConnector
       ```  
    
       ```PowerShell
        $cred = Get-Credential
       ``` 
    
       ```PowerShell
        $CSSession = New-CsOnlineSession -Credential $cred
       ```
    
       ```PowerShell
        Import-PSSession $CSSession -AllowClobber
       ```
    
    Дополнительные сведения о том, как установить удаленный сеанс PowerShell с помощью Lync Online, можно узнать [в статье подключение к Lync Online с помощью Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).
  
    Более подробную информацию об использовании модуля Lync Online PowerShell можно узнать [в статье Использование Windows PowerShell для управления Lync Online](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).

  - Необходимо настроить Lync Online для общего адресного пространства SIP. Для этого сначала запустите удаленный сеанс PowerShell с Lync Online. Затем выполните следующий командлет:
    
        Set-CsTenantFederationConfiguration -SharedSipAddressSpace $True

После выполнения этих действий вы можете перейти к [переходу пользователей Lync Online в локальную среду Lync в Lync Server 2013](lync-server-2013-migrating-lync-online-users-to-lync-on-premises.md).

</div>

<span> </span>

</div>

</div>

</div>

