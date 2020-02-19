---
title: 'Lync Server 2013: командлеты централизованного ведения журналов'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Centralized Logging cmdlets
ms:assetid: 8ba5bcae-8b99-489c-9355-6e77d4ad9100
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205064(v=OCS.15)
ms:contentKeyID: 48184743
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 12e85666b9aad15243feeeb423f87f1a442d7f52
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42135326"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="centralized-logging-cmdlets-in-lync-server-2013"></a><span data-ttu-id="f236e-102">Командлеты централизованного ведения журналов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f236e-102">Centralized Logging cmdlets in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f236e-103">_**Последнее изменение темы:** 2012-10-08_</span><span class="sxs-lookup"><span data-stu-id="f236e-103">_**Topic Last Modified:** 2012-10-08_</span></span>

<span data-ttu-id="f236e-104">С помощью командлетов централизованного ведения журналов администраторы могут управлять и настраивать возможности централизованного ведения журналов, которые представлены в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f236e-104">The centralized logging cmdlets provide a way for administrators to manage and configure the centralized logging capabilities introduced in Microsoft Lync Server 2013.</span></span> <span data-ttu-id="f236e-105">Централизованное ведение журнала позволяет администраторам одновременно включать или отключать трассировку событий на нескольких компьютерах.</span><span class="sxs-lookup"><span data-stu-id="f236e-105">Centralized logging allows administrators to simultaneously enable or disable event tracing on multiple computers.</span></span>

<div>

## <a name="centralized-logging-cmdlets"></a><span data-ttu-id="f236e-106">Командлеты централизованного ведения журнала</span><span class="sxs-lookup"><span data-stu-id="f236e-106">Centralized Logging Cmdlets</span></span>

<span data-ttu-id="f236e-107">Командлеты централизованного ведения журналов позволяют управлять службой централизованного ведения журналов, которая появилась в Lync Server 2013:</span><span class="sxs-lookup"><span data-stu-id="f236e-107">The centralized logging cmdlets enable you to manage the centralized logging service introduced in Lync Server 2013:</span></span>

<span data-ttu-id="f236e-108">**Командлеты централизованного ведения журнала**</span><span class="sxs-lookup"><span data-stu-id="f236e-108">**Centralized Logging Cmdlets**</span></span>

  - <span data-ttu-id="f236e-109">[Get — CsClsConfiguration](https://technet.microsoft.com/library/JJ619179(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f236e-109">[Get-CsClsConfiguration](https://technet.microsoft.com/library/JJ619179(v=OCS.15))</span></span>

  - <span data-ttu-id="f236e-110">[New — CsClsConfiguration](https://technet.microsoft.com/library/JJ619177(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f236e-110">[New-CsClsConfiguration](https://technet.microsoft.com/library/JJ619177(v=OCS.15))</span></span>

  - <span data-ttu-id="f236e-111">[Remove — CsClsConfiguration](https://technet.microsoft.com/library/JJ619191(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f236e-111">[Remove-CsClsConfiguration](https://technet.microsoft.com/library/JJ619191(v=OCS.15))</span></span>

  - <span data-ttu-id="f236e-112">[Set — CsClsConfiguration](https://technet.microsoft.com/library/JJ619182(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f236e-112">[Set-CsClsConfiguration](https://technet.microsoft.com/library/JJ619182(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="f236e-113">[Search — CsClsLogging](https://technet.microsoft.com/library/JJ619189(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f236e-113">[Search-CsClsLogging](https://technet.microsoft.com/library/JJ619189(v=OCS.15))</span></span>

  - <span data-ttu-id="f236e-114">[Show — CsClsLogging](https://technet.microsoft.com/library/JJ619173(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f236e-114">[Show-CsClsLogging](https://technet.microsoft.com/library/JJ619173(v=OCS.15))</span></span>

  - <span data-ttu-id="f236e-115">[Start — CsClsLogging](https://technet.microsoft.com/library/JJ619190(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f236e-115">[Start-CsClsLogging](https://technet.microsoft.com/library/JJ619190(v=OCS.15))</span></span>

  - <span data-ttu-id="f236e-116">[Stop — CsClsLogging](https://technet.microsoft.com/library/JJ619180(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f236e-116">[Stop-CsClsLogging](https://technet.microsoft.com/library/JJ619180(v=OCS.15))</span></span>

  - <span data-ttu-id="f236e-117">[Sync — CsClsLogging](https://technet.microsoft.com/library/JJ619169(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f236e-117">[Sync-CsClsLogging](https://technet.microsoft.com/library/JJ619169(v=OCS.15))</span></span>

  - <span data-ttu-id="f236e-118">[Update — CsClsLogging](https://technet.microsoft.com/library/JJ619170(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f236e-118">[Update-CsClsLogging](https://technet.microsoft.com/library/JJ619170(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="f236e-119">[New — CsClsProvider](https://technet.microsoft.com/library/JJ619187(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f236e-119">[New-CsClsProvider](https://technet.microsoft.com/library/JJ619187(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="f236e-120">[Get — CsClsRegion](https://technet.microsoft.com/library/JJ204879(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f236e-120">[Get-CsClsRegion](https://technet.microsoft.com/library/JJ204879(v=OCS.15))</span></span>

  - <span data-ttu-id="f236e-121">[New — CsClsRegion](https://technet.microsoft.com/library/JJ204658(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f236e-121">[New-CsClsRegion](https://technet.microsoft.com/library/JJ204658(v=OCS.15))</span></span>

  - <span data-ttu-id="f236e-122">[Remove — CsClsRegion](https://technet.microsoft.com/library/JJ204971(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f236e-122">[Remove-CsClsRegion](https://technet.microsoft.com/library/JJ204971(v=OCS.15))</span></span>

  - <span data-ttu-id="f236e-123">[Set — CsClsRegion](https://technet.microsoft.com/library/JJ204746(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f236e-123">[Set-CsClsRegion](https://technet.microsoft.com/library/JJ204746(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="f236e-124">[Get — CsClsScenario](https://technet.microsoft.com/library/JJ205091(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f236e-124">[Get-CsClsScenario](https://technet.microsoft.com/library/JJ205091(v=OCS.15))</span></span>

  - <span data-ttu-id="f236e-125">[New — CsClsScenario](https://technet.microsoft.com/library/JJ205022(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f236e-125">[New-CsClsScenario](https://technet.microsoft.com/library/JJ205022(v=OCS.15))</span></span>

  - <span data-ttu-id="f236e-126">[Remove — CsClsScenario](https://technet.microsoft.com/library/JJ205010(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f236e-126">[Remove-CsClsScenario](https://technet.microsoft.com/library/JJ205010(v=OCS.15))</span></span>

  - <span data-ttu-id="f236e-127">[Set — CsClsScenario](https://technet.microsoft.com/library/JJ204622(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f236e-127">[Set-CsClsScenario](https://technet.microsoft.com/library/JJ204622(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="f236e-128">[Get — CsClsSearchTerm](https://technet.microsoft.com/library/JJ205061(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f236e-128">[Get-CsClsSearchTerm](https://technet.microsoft.com/library/JJ205061(v=OCS.15))</span></span>

  - <span data-ttu-id="f236e-129">[Set — CsClsSearchTerm](https://technet.microsoft.com/library/JJ204911(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f236e-129">[Set-CsClsSearchTerm](https://technet.microsoft.com/library/JJ204911(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="f236e-130">[Get — CsClsSecurityGroup](https://technet.microsoft.com/library/JJ205285(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f236e-130">[Get-CsClsSecurityGroup](https://technet.microsoft.com/library/JJ205285(v=OCS.15))</span></span>

  - <span data-ttu-id="f236e-131">[New — CsClsSecurityGroup](https://technet.microsoft.com/library/JJ205359(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f236e-131">[New-CsClsSecurityGroup](https://technet.microsoft.com/library/JJ205359(v=OCS.15))</span></span>

  - <span data-ttu-id="f236e-132">[Remove — CsClsSecurityGroup](https://technet.microsoft.com/library/JJ204958(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f236e-132">[Remove-CsClsSecurityGroup](https://technet.microsoft.com/library/JJ204958(v=OCS.15))</span></span>

  - <span data-ttu-id="f236e-133">[Set — CsClsSecurityGroup](https://technet.microsoft.com/library/JJ204700(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f236e-133">[Set-CsClsSecurityGroup](https://technet.microsoft.com/library/JJ204700(v=OCS.15))</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

