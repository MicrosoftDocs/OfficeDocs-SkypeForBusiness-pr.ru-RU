---
title: 'Lync Server 2013: поведение парковки вызовов во время отказа пула'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Call Park experience during pool failure
ms:assetid: f6303e69-8771-492a-9e8b-c3d7ba231309
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205383(v=OCS.15)
ms:contentKeyID: 48185831
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7b175e5029749ea4e3a344aaf9f3bcc7a403c1b0
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34841695"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="call-park-experience-in-lync-server-2013-during-pool-failure"></a><span data-ttu-id="eb9a8-102">Поведение парковки вызовов в Lync Server 2013 во время отказа пула</span><span class="sxs-lookup"><span data-stu-id="eb9a8-102">Call Park experience in Lync Server 2013 during pool failure</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="eb9a8-103">_**Тема последнего изменения:** 2012-09-10_</span><span class="sxs-lookup"><span data-stu-id="eb9a8-103">_**Topic Last Modified:** 2012-09-10_</span></span>

<span data-ttu-id="eb9a8-104">Если пул переднего плана становится недоступен из-за незапланированного инцидента, звонки, которые были приостановлены, но еще не были получены, будут разорваны.</span><span class="sxs-lookup"><span data-stu-id="eb9a8-104">When a Front End pool becomes unavailable due an unplanned incident, calls that have been parked but not yet retrieved are disconnected.</span></span> <span data-ttu-id="eb9a8-105">При переходе на другой ресурс в архивный пул пользователи перенаправляются в пул резервных копий и в режиме устойчивости.</span><span class="sxs-lookup"><span data-stu-id="eb9a8-105">During failover to a backup pool, users are redirected to the backup pool and are in resiliency mode.</span></span> <span data-ttu-id="eb9a8-106">В режиме устойчивости пользователи не могут приостановить звонки, но они могут помещать звонки на удержание и передавать их.</span><span class="sxs-lookup"><span data-stu-id="eb9a8-106">While in resiliency mode, users cannot park calls, but they can place calls on hold and transfer them.</span></span> <span data-ttu-id="eb9a8-107">После завершения отработки отказа звонки могут быть приостановлены и извлечены в обычном режиме.</span><span class="sxs-lookup"><span data-stu-id="eb9a8-107">When failover is complete, calls can again be parked and retrieved as usual.</span></span> <span data-ttu-id="eb9a8-108">Во время восстановления после сбоя пользователи не могут приостановить звонки, пока они не попадают в режим устойчивости.</span><span class="sxs-lookup"><span data-stu-id="eb9a8-108">During failback, users cannot park calls until they are out of resiliency mode.</span></span>

<span data-ttu-id="eb9a8-109">При восстановлении после аварии пользователи, которые были перенаправлены в резервный пул в рамках процесса перемещения, используют приложение для остановки звонков, которое разворачивается в пуле резервных копий.</span><span class="sxs-lookup"><span data-stu-id="eb9a8-109">During disaster recovery, users who have been redirected to the backup pool as part of the failover process use the Call Park application that is deployed in the backup pool.</span></span> <span data-ttu-id="eb9a8-110">Таким образом, пользователи, которые перенаправляются в пул резервных копий, используют параметры переадресации звонков, настроенные для приложения на приостановке звонков в пуле резервных копий.</span><span class="sxs-lookup"><span data-stu-id="eb9a8-110">Therefore, users who are redirected to the backup pool use the call park settings that are configured for the Call Park application in the backup pool.</span></span>

<span data-ttu-id="eb9a8-111">В таблице ниже приведены сведения о приостановке звонков с помощью фаз аварийного восстановления.</span><span class="sxs-lookup"><span data-stu-id="eb9a8-111">The following table summarizes the Call Park experience through the phases of disaster recovery.</span></span>

### <a name="user-experience-during-disaster-recovery"></a><span data-ttu-id="eb9a8-112">Взаимодействие с пользователем во время аварийного восстановления</span><span class="sxs-lookup"><span data-stu-id="eb9a8-112">User Experience During Disaster Recovery</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="eb9a8-113">Состояние звонка</span><span class="sxs-lookup"><span data-stu-id="eb9a8-113">Call state</span></span></th>
<th><span data-ttu-id="eb9a8-114">При возникновении сбоя</span><span class="sxs-lookup"><span data-stu-id="eb9a8-114">When outage occurs</span></span></th>
<th><span data-ttu-id="eb9a8-115">При переходе на другой ресурс</span><span class="sxs-lookup"><span data-stu-id="eb9a8-115">During failover</span></span></th>
<th><span data-ttu-id="eb9a8-116">Во время восстановления размещения</span><span class="sxs-lookup"><span data-stu-id="eb9a8-116">During failback</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="eb9a8-117">Звонок еще не приостановлен</span><span class="sxs-lookup"><span data-stu-id="eb9a8-117">Call not yet parked</span></span></p></td>
<td><p><span data-ttu-id="eb9a8-118">Звонок остается подключенным, но его нельзя приостановить.</span><span class="sxs-lookup"><span data-stu-id="eb9a8-118">Call remains connected, but cannot be parked.</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="eb9a8-119">Во время отработки отказа звонок не может быть приостановлен, пока пользователи находятся в режиме устойчивости, но могут быть переведены на удержание и переданы.</span><span class="sxs-lookup"><span data-stu-id="eb9a8-119">During failover, call cannot be parked while users are in resiliency mode, but can be put on hold and transferred.</span></span></p></li>
<li><p><span data-ttu-id="eb9a8-120">После завершения отработки отказа Звонок можно приостановить и получить.</span><span class="sxs-lookup"><span data-stu-id="eb9a8-120">When failover completes, call can be parked and retrieved.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="eb9a8-121">Во время восстановления после сбоя звонок не может быть приостановлен, пока пользователи находятся в режиме устойчивости, но могут быть переведены на удержание и переданы.</span><span class="sxs-lookup"><span data-stu-id="eb9a8-121">During failback, call cannot be parked while users are in resiliency mode, but can be put on hold and transferred.</span></span></p></li>
<li><p><span data-ttu-id="eb9a8-122">После завершения восстановления, Звонок можно приостановить и получить.</span><span class="sxs-lookup"><span data-stu-id="eb9a8-122">When failback completes, call can be parked and retrieved.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eb9a8-123">Звонок приостановлен, но еще не получен</span><span class="sxs-lookup"><span data-stu-id="eb9a8-123">Call parked, but not yet retrieved</span></span></p></td>
<td><p><span data-ttu-id="eb9a8-124">Звонок прерван.</span><span class="sxs-lookup"><span data-stu-id="eb9a8-124">Call is disconnected.</span></span></p></td>
<td><p><span data-ttu-id="eb9a8-125">Нет вызовов в этом состоянии.</span><span class="sxs-lookup"><span data-stu-id="eb9a8-125">No calls in this state.</span></span></p></td>
<td><p><span data-ttu-id="eb9a8-126">Звонок будет приостановлен.</span><span class="sxs-lookup"><span data-stu-id="eb9a8-126">Call remains parked.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eb9a8-127">Припаркованный Звонок уже получен</span><span class="sxs-lookup"><span data-stu-id="eb9a8-127">Parked call already retrieved</span></span></p></td>
<td><p><span data-ttu-id="eb9a8-128">Звонки будут оставаться на связи.</span><span class="sxs-lookup"><span data-stu-id="eb9a8-128">Call remains connected.</span></span></p></td>
<td><p><span data-ttu-id="eb9a8-129">Звонки будут оставаться на связи.</span><span class="sxs-lookup"><span data-stu-id="eb9a8-129">Call remains connected.</span></span></p></td>
<td><p><span data-ttu-id="eb9a8-130">Звонки будут оставаться на связи.</span><span class="sxs-lookup"><span data-stu-id="eb9a8-130">Call remains connected.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

