---
title: 'Lync Server 2013: первые шаги перед началом миграции пользователей из Lync Online в локальное Lync'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: First steps before you start migrating users from Lync Online to Lync on-premises
ms:assetid: 98245b04-ded4-4186-8da3-ba1c554b5c39
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn689118(v=OCS.15)
ms:contentKeyID: 62258123
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ac0377c12cbda0d6080ecfe9b8e64fae08cbed59
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/08/2020
ms.locfileid: "40989134"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="first-steps-before-you-start-migrating-users-from-lync-online-to-lync-on-premises-in-lync-server-2013"></a>Прежде чем приступить к переносу пользователей из Lync Online в локальную версию Lync в Lync Server 2013, выполните указанные ниже действия.

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2014-05-08_

Прежде чем приступить к перемещению пользователей Lync Online в локальную среду, убедитесь в том, что выполняются все указанные ниже условия.

  - Локальная среда Lync Server должна быть полностью развернута и проверена. Дополнительные сведения можно найти в разделе [развертывание Lync Server 2013](lync-server-2013-deploying-lync-server.md).

  - Клиент Lync Online должен быть настроен для доступа к удаленной оболочке PowerShell.
    
    Для этого сначала установите модуль Lync Online для Windows PowerShell, который вы можете найти ниже [http://go.microsoft.com/fwlink/p/?LinkId=391911](http://go.microsoft.com/fwlink/p/?linkid=391911).
    
    После установки модуля вы можете установить удаленный сеанс, введя следующие командлеты в командной консоли Lync Server.
    
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
    
    Дополнительные сведения о том, как установить удаленный сеанс PowerShell в Lync Online, можно найти [в разделе Подключение к Lync Online с помощью Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).
  
    Дополнительные сведения об использовании модуля Lync Online PowerShell можно найти в разделе [Использование Windows PowerShell для управления Lync Online](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).

  - В Lync Online необходимо настроить общее адресное пространство SIP. Для этого сначала запустите удаленный сеанс PowerShell с помощью Lync Online. Затем выполните следующий командлет:
    
        Set-CsTenantFederationConfiguration -SharedSipAddressSpace $True

После выполнения этих действий вы можете перейти к [миграции пользователей Lync Online в локальное Lync Server 2013](lync-server-2013-migrating-lync-online-users-to-lync-on-premises.md).

</div>

<span> </span>

</div>

</div>

</div>

