---
title: 'Lync Server 2013: первые шаги перед началом миграции пользователей из Lync Online в локальное Lync'
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
ms.openlocfilehash: 59ca20a994934a199504a4fb6a7dd5eec206c960
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742499"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="first-steps-before-you-start-migrating-users-from-lync-online-to-lync-on-premises-in-lync-server-2013"></a><span data-ttu-id="06557-102">Прежде чем приступить к переносу пользователей из Lync Online в локальную версию Lync в Lync Server 2013, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="06557-102">First steps before you start migrating users from Lync Online to Lync on-premises in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="06557-103">_**Тема последнего изменения:** 2014-05-08_</span><span class="sxs-lookup"><span data-stu-id="06557-103">_**Topic Last Modified:** 2014-05-08_</span></span>

<span data-ttu-id="06557-104">Прежде чем приступить к перемещению пользователей Lync Online в локальную среду, убедитесь в том, что выполняются все указанные ниже условия.</span><span class="sxs-lookup"><span data-stu-id="06557-104">Before you start moving Lync Online users to your on-premises environment, check that all of the following are true:</span></span>

  - <span data-ttu-id="06557-105">Локальная среда Lync Server должна быть полностью развернута и проверена.</span><span class="sxs-lookup"><span data-stu-id="06557-105">Your Lync Server on-premises environment must be fully deployed and validated.</span></span> <span data-ttu-id="06557-106">Дополнительные сведения можно найти в разделе [развертывание Lync Server 2013](lync-server-2013-deploying-lync-server.md).</span><span class="sxs-lookup"><span data-stu-id="06557-106">For more information, see [Deploying Lync Server 2013](lync-server-2013-deploying-lync-server.md).</span></span>

  - <span data-ttu-id="06557-107">Клиент Lync Online должен быть настроен для доступа к удаленной оболочке PowerShell.</span><span class="sxs-lookup"><span data-stu-id="06557-107">Your Lync Online tenant must be configured for remote PowerShell Access.</span></span>
    
    <span data-ttu-id="06557-108">Для этого сначала установите модуль Lync Online для Windows PowerShell, который вы можете найти ниже [http://go.microsoft.com/fwlink/p/?LinkId=391911](http://go.microsoft.com/fwlink/p/?linkid=391911).</span><span class="sxs-lookup"><span data-stu-id="06557-108">To do this, first install the Lync Online module for Windows PowerShell, which you can get here: [http://go.microsoft.com/fwlink/p/?LinkId=391911](http://go.microsoft.com/fwlink/p/?linkid=391911).</span></span>
    
    <span data-ttu-id="06557-109">После установки модуля вы можете установить удаленный сеанс, введя следующие командлеты в командной консоли Lync Server.</span><span class="sxs-lookup"><span data-stu-id="06557-109">After you install the module, you can establish a remote session by typing the following cmdlets in the Lync Server Management Shell:</span></span>
    
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
    
    <span data-ttu-id="06557-110">Дополнительные сведения о том, как установить удаленный сеанс PowerShell в Lync Online, можно найти [в разделе Подключение к Lync Online с помощью Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="06557-110">For more information about how to establish a remote PowerShell session with Lync Online, see [Connecting to Lync Online by using Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span>
  
    <span data-ttu-id="06557-111">Дополнительные сведения об использовании модуля Lync Online PowerShell можно найти в разделе [Использование Windows PowerShell для управления Lync Online](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="06557-111">For more information about using the Lync Online PowerShell module, see [Using Windows PowerShell to manage Lync Online](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span>

  - <span data-ttu-id="06557-112">В Lync Online необходимо настроить общее адресное пространство SIP.</span><span class="sxs-lookup"><span data-stu-id="06557-112">Your Lync Online must be configured for Shared SIP Address Space.</span></span> <span data-ttu-id="06557-113">Для этого сначала запустите удаленный сеанс PowerShell с помощью Lync Online.</span><span class="sxs-lookup"><span data-stu-id="06557-113">To do this, first start a remote Powershell session with Lync Online.</span></span> <span data-ttu-id="06557-114">Затем выполните следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="06557-114">Then run the following cmdlet:</span></span>
    
        Set-CsTenantFederationConfiguration -SharedSipAddressSpace $True

<span data-ttu-id="06557-115">После выполнения этих действий вы можете перейти к [миграции пользователей Lync Online в локальное Lync Server 2013](lync-server-2013-migrating-lync-online-users-to-lync-on-premises.md).</span><span class="sxs-lookup"><span data-stu-id="06557-115">After you’ve finished these steps, you can move on to [Migrating Lync Online users to Lync on-premises in Lync Server 2013](lync-server-2013-migrating-lync-online-users-to-lync-on-premises.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

