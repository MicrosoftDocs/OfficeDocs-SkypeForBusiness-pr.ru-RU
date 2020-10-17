---
title: 'Lync Server 2013: командлеты управления пользователями'
description: 'Lync Server 2013: командлеты управления пользователями.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: User management cmdlets
ms:assetid: 85312f3f-28e8-421c-b94c-e6ead1f5f755
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398677(v=OCS.15)
ms:contentKeyID: 48184702
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b94f2b48017fd29fa7a5a814da8a3c80d8f57968
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48569785"
---
# <a name="user-management-cmdlets-in-lync-server-2013"></a><span data-ttu-id="f7124-103">Командлеты управления пользователями в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f7124-103">User management cmdlets in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f7124-104">_**Последнее изменение темы:** 2013-02-18_</span><span class="sxs-lookup"><span data-stu-id="f7124-104">_**Topic Last Modified:** 2013-02-18_</span></span>

<span data-ttu-id="f7124-105">Командлеты управления пользователями, включенные в Microsoft Lync Server 2013, позволяют включать, отключать и изменять учетные записи пользователей Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f7124-105">The user management cmdlets included in Microsoft Lync Server 2013 allow you to enable, disable, and modify Lync Server user accounts.</span></span>

<div>

## <a name="user-management-cmdlets"></a><span data-ttu-id="f7124-106">Командлеты для управления пользователями</span><span class="sxs-lookup"><span data-stu-id="f7124-106">User Management Cmdlets</span></span>

<span data-ttu-id="f7124-107">Большинство задач управления, которые применяются к пользователям и учетным записям пользователей, можно выполнить с помощью панели управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f7124-107">Most management tasks that apply to users and user accounts can be performed from the Lync Server Control Panel.</span></span> <span data-ttu-id="f7124-108">Основными исключениями являются командлеты, связанные с поставщиками аудиоконференций.</span><span class="sxs-lookup"><span data-stu-id="f7124-108">The primary exceptions are the cmdlets that deal with audio conferencing providers.</span></span> <span data-ttu-id="f7124-109">Задачи управления пользователями можно выполнять с помощью командлетов в командной консоли Lync Server или из скрипта.</span><span class="sxs-lookup"><span data-stu-id="f7124-109">User management tasks can be performed using cmdlets from the Lync Server Management Shell or from within a script.</span></span> <span data-ttu-id="f7124-110">Используя скрипты, можно автоматизировать определенные задачи.</span><span class="sxs-lookup"><span data-stu-id="f7124-110">By using a script, you can automate certain tasks.</span></span> <span data-ttu-id="f7124-111">Далее приводится список командлетов, имеющих прямое отношение к управлению пользователями и учетными записями пользователей.</span><span class="sxs-lookup"><span data-stu-id="f7124-111">The following is a list of cmdlets that relate directly to managing users and user accounts:</span></span>

  - <span></span>  
    [<span data-ttu-id="f7124-112">Get — CsAdContact</span><span class="sxs-lookup"><span data-stu-id="f7124-112">Get-CsAdContact</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsAdContact)

<!-- end list -->

  - <span></span>  
    [<span data-ttu-id="f7124-113">Get — CsAdUser</span><span class="sxs-lookup"><span data-stu-id="f7124-113">Get-CsAdUser</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsAdUser)

<!-- end list -->

  - [<span data-ttu-id="f7124-114">Get — CsClientAccessLicense</span><span class="sxs-lookup"><span data-stu-id="f7124-114">Get-CsClientAccessLicense</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsClientAccessLicense)

<!-- end list -->

  - [<span data-ttu-id="f7124-115">Get — CsEffectivePolicy</span><span class="sxs-lookup"><span data-stu-id="f7124-115">Get-CsEffectivePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsEffectivePolicy)

<!-- end list -->

  - [<span data-ttu-id="f7124-116">Invoke — CsUcsRollback</span><span class="sxs-lookup"><span data-stu-id="f7124-116">Invoke-CsUcsRollback</span></span>](https://docs.microsoft.com/powershell/module/skype/Invoke-CsUcsRollback)

<!-- end list -->

  - [<span data-ttu-id="f7124-117">Debug — CsUnifiedContactStore</span><span class="sxs-lookup"><span data-stu-id="f7124-117">Debug-CsUnifiedContactStore</span></span>](https://docs.microsoft.com/powershell/module/skype/Debug-CsUnifiedContactStore)

  - [<span data-ttu-id="f7124-118">Test-CsUnifiedContactStore</span><span class="sxs-lookup"><span data-stu-id="f7124-118">Test-CsUnifiedContactStore</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsUnifiedContactStore)

<!-- end list -->

  - <span></span>  
    [<span data-ttu-id="f7124-119">Disable — CsUser</span><span class="sxs-lookup"><span data-stu-id="f7124-119">Disable-CsUser</span></span>](https://docs.microsoft.com/powershell/module/skype/Disable-CsUser)

  - <span></span>  
    [<span data-ttu-id="f7124-120">Enable — CsUser</span><span class="sxs-lookup"><span data-stu-id="f7124-120">Enable-CsUser</span></span>](https://docs.microsoft.com/powershell/module/skype/Enable-CsUser)

  - <span></span>  
    [<span data-ttu-id="f7124-121">Get — CsUser</span><span class="sxs-lookup"><span data-stu-id="f7124-121">Get-CsUser</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsUser)

  - <span></span>  
    [<span data-ttu-id="f7124-122">Move — CsUser</span><span class="sxs-lookup"><span data-stu-id="f7124-122">Move-CsUser</span></span>](https://docs.microsoft.com/powershell/module/skype/Move-CsUser)

  - <span></span>  
    [<span data-ttu-id="f7124-123">Set — CsUser</span><span class="sxs-lookup"><span data-stu-id="f7124-123">Set-CsUser</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsUser)

<!-- end list -->

  - <span></span>  
    [<span data-ttu-id="f7124-124">Get — CsUserAcp</span><span class="sxs-lookup"><span data-stu-id="f7124-124">Get-CsUserAcp</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsUserAcp)

  - <span></span>  
    [<span data-ttu-id="f7124-125">Remove — CsUserAcp</span><span class="sxs-lookup"><span data-stu-id="f7124-125">Remove-CsUserAcp</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsUserAcp)

  - <span></span>  
    [<span data-ttu-id="f7124-126">Set — CsUserAcp</span><span class="sxs-lookup"><span data-stu-id="f7124-126">Set-CsUserAcp</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsUserAcp)

  - <span></span>  
    [<span data-ttu-id="f7124-127">Test-CsAudioConferencingProvider</span><span class="sxs-lookup"><span data-stu-id="f7124-127">Test-CsAudioConferencingProvider</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsAudioConferencingProvider)

<!-- end list -->

  - <span></span>  
    [<span data-ttu-id="f7124-128">Get — CsUserPoolInfo</span><span class="sxs-lookup"><span data-stu-id="f7124-128">Get-CsUserPoolInfo</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsUserPoolInfo)

<!-- end list -->

  - [<span data-ttu-id="f7124-129">Get — CsUserServicesPolicy</span><span class="sxs-lookup"><span data-stu-id="f7124-129">Get-CsUserServicesPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsUserServicesPolicy)

  - [<span data-ttu-id="f7124-130">Granting — CsUserServicesPolicy</span><span class="sxs-lookup"><span data-stu-id="f7124-130">Grant-CsUserServicesPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Grant-CsUserServicesPolicy)

  - [<span data-ttu-id="f7124-131">New — CsUserServicesPolicy</span><span class="sxs-lookup"><span data-stu-id="f7124-131">New-CsUserServicesPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsUserServicesPolicy)

  - [<span data-ttu-id="f7124-132">Remove — CsUserServicesPolicy</span><span class="sxs-lookup"><span data-stu-id="f7124-132">Remove-CsUserServicesPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsUserServicesPolicy)

  - [<span data-ttu-id="f7124-133">Set — CsUserServicesPolicy</span><span class="sxs-lookup"><span data-stu-id="f7124-133">Set-CsUserServicesPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsUserServicesPolicy)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="f7124-134">См. также</span><span class="sxs-lookup"><span data-stu-id="f7124-134">See Also</span></span>


[<span data-ttu-id="f7124-135">Блог Lync Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="f7124-135">Lync Server PowerShell Blog</span></span>](https://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

