---
title: 'Lync Server 2013: командлеты резервного копирования и высокой доступности'
description: 'Lync Server 2013: командлеты резервного копирования и высокой доступности.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Backup and high availability cmdlets
ms:assetid: 5aff41a3-7a0e-4c51-9d5f-7f08e36bf046
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204925(v=OCS.15)
ms:contentKeyID: 48184236
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d455f25e7a5a816f42d9df58c886429c96208acd
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48563161"
---
# <a name="backup-and-high-availability-cmdlets-in-lync-server-2013"></a><span data-ttu-id="4aee9-103">Командлеты резервного копирования и высокой доступности в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4aee9-103">Backup and high availability cmdlets in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4aee9-104">_**Последнее изменение темы:** 2012-10-09_</span><span class="sxs-lookup"><span data-stu-id="4aee9-104">_**Topic Last Modified:** 2012-10-09_</span></span>

<span data-ttu-id="4aee9-105">Командлеты резервного копирования и высокой доступности позволяют администраторам управлять возможностями резервного копирования, восстановления и обеспечения высокого уровня доступности, появившимися в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4aee9-105">The backup and high availability cmdlets enable administrators to manage the pool backup, restore, and high availability capabilities introduced in Microsoft Lync Server 2013.</span></span>

<div>

## <a name="backup-and-high-availability-cmdlets"></a><span data-ttu-id="4aee9-106">Командлеты резервного копирования и высокой доступности</span><span class="sxs-lookup"><span data-stu-id="4aee9-106">Backup and High Availability Cmdlets</span></span>

<span data-ttu-id="4aee9-107">Ниже приведен список командлетов, которые относятся непосредственно к резервному копированию и настройке доступности вашей топологии Lync Server.</span><span class="sxs-lookup"><span data-stu-id="4aee9-107">The following is a list of cmdlets that relate directly to backing up and configuring the availability of your Lync Server topology:</span></span>

<span data-ttu-id="4aee9-108">**Командлеты резервного копирования и высокой доступности**</span><span class="sxs-lookup"><span data-stu-id="4aee9-108">**Backup and High Availability Cmdlets**</span></span>

  - <span data-ttu-id="4aee9-109">[Get — CsBackupServiceConfiguration](https://technet.microsoft.com/library/JJ205087(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="4aee9-109">[Get-CsBackupServiceConfiguration](https://technet.microsoft.com/library/JJ205087(v=OCS.15))</span></span>

  - <span data-ttu-id="4aee9-110">[Remove — CsBackupServiceConfiguration](https://technet.microsoft.com/library/JJ204903(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="4aee9-110">[Remove-CsBackupServiceConfiguration](https://technet.microsoft.com/library/JJ204903(v=OCS.15))</span></span>

  - <span data-ttu-id="4aee9-111">[Set — CsBackupServiceConfiguration](https://technet.microsoft.com/library/JJ205006(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="4aee9-111">[Set-CsBackupServiceConfiguration](https://technet.microsoft.com/library/JJ205006(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="4aee9-112">[Get — Ксбаккупсервицестатус](https://technet.microsoft.com/library/JJ205032(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="4aee9-112">[Get-CsBackupServiceStatus](https://technet.microsoft.com/library/JJ205032(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="4aee9-113">[Invoke — Ксбаккупсервицесинк](https://technet.microsoft.com/library/JJ205374(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="4aee9-113">[Invoke-CsBackupServiceSync](https://technet.microsoft.com/library/JJ205374(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="4aee9-114">[Debug — CsIntraPoolReplication](https://technet.microsoft.com/library/JJ205103(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="4aee9-114">[Debug-CsIntraPoolReplication](https://technet.microsoft.com/library/JJ205103(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="4aee9-115">[Backup — CsPool](https://technet.microsoft.com/library/JJ204955(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="4aee9-115">[Backup-CsPool](https://technet.microsoft.com/library/JJ204955(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="4aee9-116">[Get — CsPoolBackupRelationship](https://technet.microsoft.com/library/JJ204745(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="4aee9-116">[Get-CsPoolBackupRelationship](https://technet.microsoft.com/library/JJ204745(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="4aee9-117">[Get — CsPoolFabricState](https://technet.microsoft.com/library/JJ619188(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="4aee9-117">[Get-CsPoolFabricState](https://technet.microsoft.com/library/JJ619188(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="4aee9-118">[Invoke — CsPoolFailBack](https://technet.microsoft.com/library/JJ204873(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="4aee9-118">[Invoke-CsPoolFailBack](https://technet.microsoft.com/library/JJ204873(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="4aee9-119">[Invoke — CsPoolFailOver](https://technet.microsoft.com/library/JJ205189(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="4aee9-119">[Invoke-CsPoolFailOver](https://technet.microsoft.com/library/JJ205189(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="4aee9-120">[Get — CsPoolUpgradeReadinessState](https://technet.microsoft.com/library/JJ204689(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="4aee9-120">[Get-CsPoolUpgradeReadinessState](https://technet.microsoft.com/library/JJ204689(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="4aee9-121">[Invoke — Кссторажесервицефлуш](https://technet.microsoft.com/library/JJ619175(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="4aee9-121">[Invoke-CsStorageServiceFlush](https://technet.microsoft.com/library/JJ619175(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="4aee9-122">[Sync — CsUserData](https://technet.microsoft.com/library/JJ205242(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="4aee9-122">[Sync-CsUserData](https://technet.microsoft.com/library/JJ205242(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="4aee9-123">[Remove — Ксусерсторебаккупдата](https://technet.microsoft.com/library/JJ205003(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="4aee9-123">[Remove-CsUserStoreBackupData](https://technet.microsoft.com/library/JJ205003(v=OCS.15))</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

