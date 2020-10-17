---
title: 'Lync Server 2013: работа парковки вызовов во время сбоя пула'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Call Park experience during pool failure
ms:assetid: f6303e69-8771-492a-9e8b-c3d7ba231309
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205383(v=OCS.15)
ms:contentKeyID: 48185831
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 605900501a141c053459c690292b1e0a10c8abbc
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48508256"
---
# <a name="call-park-experience-in-lync-server-2013-during-pool-failure"></a><span data-ttu-id="9b640-102">Функции парковки вызовов в Lync Server 2013 во время сбоя пула</span><span class="sxs-lookup"><span data-stu-id="9b640-102">Call Park experience in Lync Server 2013 during pool failure</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9b640-103">_**Последнее изменение темы:** 2012-09-10_</span><span class="sxs-lookup"><span data-stu-id="9b640-103">_**Topic Last Modified:** 2012-09-10_</span></span>

<span data-ttu-id="9b640-104">Если интерфейсный пул становится недоступен из-за незапланированного инцидента, вызовы, которые были приостановлены, но еще не получены, отключаются.</span><span class="sxs-lookup"><span data-stu-id="9b640-104">When a Front End pool becomes unavailable due an unplanned incident, calls that have been parked but not yet retrieved are disconnected.</span></span> <span data-ttu-id="9b640-105">При отработке отказа с переключением на резервный пул пользователи перенаправляются на резервный пул и находятся в режиме устойчивости.</span><span class="sxs-lookup"><span data-stu-id="9b640-105">During failover to a backup pool, users are redirected to the backup pool and are in resiliency mode.</span></span> <span data-ttu-id="9b640-106">В режиме устойчивости пользователи не смогут парковать вызовы, но могут переводить вызовы на удержание и переадресовывать их.</span><span class="sxs-lookup"><span data-stu-id="9b640-106">While in resiliency mode, users cannot park calls, but they can place calls on hold and transfer them.</span></span> <span data-ttu-id="9b640-107">По завершении отработки отказа пользователи могут снова парковать вызовы и извлекать их в обычном режиме.</span><span class="sxs-lookup"><span data-stu-id="9b640-107">When failover is complete, calls can again be parked and retrieved as usual.</span></span> <span data-ttu-id="9b640-108">При восстановлении размещения пользователи не могут парковать вызовы, пока не выйдут из режима устойчивости.</span><span class="sxs-lookup"><span data-stu-id="9b640-108">During failback, users cannot park calls until they are out of resiliency mode.</span></span>

<span data-ttu-id="9b640-109">Во время аварийного восстановления пользователи, которые были перенаправлены в резервный пул в рамках процесса отработки отказа, используют приложение парковки вызовов, развернутое в резервном пуле.</span><span class="sxs-lookup"><span data-stu-id="9b640-109">During disaster recovery, users who have been redirected to the backup pool as part of the failover process use the Call Park application that is deployed in the backup pool.</span></span> <span data-ttu-id="9b640-110">Таким образом, пользователи, которые перенаправляются в резервный пул, используют параметры парковки вызовов, настроенные для приложения парковки вызовов в резервном пуле.</span><span class="sxs-lookup"><span data-stu-id="9b640-110">Therefore, users who are redirected to the backup pool use the call park settings that are configured for the Call Park application in the backup pool.</span></span>

<span data-ttu-id="9b640-111">В приведенной ниже таблице представлена сводная информация о приостановке вызовов через этапы аварийного восстановления.</span><span class="sxs-lookup"><span data-stu-id="9b640-111">The following table summarizes the Call Park experience through the phases of disaster recovery.</span></span>

### <a name="user-experience-during-disaster-recovery"></a><span data-ttu-id="9b640-112">Возможности пользователей в ходе аварийного восстановления</span><span class="sxs-lookup"><span data-stu-id="9b640-112">User Experience During Disaster Recovery</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9b640-113">Состоянии вызова</span><span class="sxs-lookup"><span data-stu-id="9b640-113">Call state</span></span></th>
<th><span data-ttu-id="9b640-114">Когда происходит отключение электричества</span><span class="sxs-lookup"><span data-stu-id="9b640-114">When outage occurs</span></span></th>
<th><span data-ttu-id="9b640-115">Во время отработки отказа</span><span class="sxs-lookup"><span data-stu-id="9b640-115">During failover</span></span></th>
<th><span data-ttu-id="9b640-116">Во время восстановления размещения</span><span class="sxs-lookup"><span data-stu-id="9b640-116">During failback</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9b640-117">Вызов еще не запаркован</span><span class="sxs-lookup"><span data-stu-id="9b640-117">Call not yet parked</span></span></p></td>
<td><p><span data-ttu-id="9b640-118">Вызов не разъединяется, но его парковка невозможна</span><span class="sxs-lookup"><span data-stu-id="9b640-118">Call remains connected, but cannot be parked.</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="9b640-119">Во время отработки отказа вызов нельзя запарковать, если пользователи находятся в режиме устойчивости, но его можно перевести на удержание и переадресовать.</span><span class="sxs-lookup"><span data-stu-id="9b640-119">During failover, call cannot be parked while users are in resiliency mode, but can be put on hold and transferred.</span></span></p></li>
<li><p><span data-ttu-id="9b640-120">При завершении отработки отказа вызовы можно парковать и извлекать.</span><span class="sxs-lookup"><span data-stu-id="9b640-120">When failover completes, call can be parked and retrieved.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="9b640-121">Во время восстановления размещения вызов нельзя запарковать, если пользователи находятся в режиме устойчивости, но его можно перевести на удержание и переадресовать.</span><span class="sxs-lookup"><span data-stu-id="9b640-121">During failback, call cannot be parked while users are in resiliency mode, but can be put on hold and transferred.</span></span></p></li>
<li><p><span data-ttu-id="9b640-122">При завершении восстановления размещения вызовы можно парковать и извлекать.</span><span class="sxs-lookup"><span data-stu-id="9b640-122">When failback completes, call can be parked and retrieved.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9b640-123">Вызов запаркован, но еще не извлечен.</span><span class="sxs-lookup"><span data-stu-id="9b640-123">Call parked, but not yet retrieved</span></span></p></td>
<td><p><span data-ttu-id="9b640-124">Вызов разъединен.</span><span class="sxs-lookup"><span data-stu-id="9b640-124">Call is disconnected.</span></span></p></td>
<td><p><span data-ttu-id="9b640-125">Нет вызовов в этом состоянии.</span><span class="sxs-lookup"><span data-stu-id="9b640-125">No calls in this state.</span></span></p></td>
<td><p><span data-ttu-id="9b640-126">Вызов остается запаркованным.</span><span class="sxs-lookup"><span data-stu-id="9b640-126">Call remains parked.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9b640-127">Запаркованный вызов уже извлечен.</span><span class="sxs-lookup"><span data-stu-id="9b640-127">Parked call already retrieved</span></span></p></td>
<td><p><span data-ttu-id="9b640-128">Вызов остается подключенным.</span><span class="sxs-lookup"><span data-stu-id="9b640-128">Call remains connected.</span></span></p></td>
<td><p><span data-ttu-id="9b640-129">Вызов остается подключенным.</span><span class="sxs-lookup"><span data-stu-id="9b640-129">Call remains connected.</span></span></p></td>
<td><p><span data-ttu-id="9b640-130">Вызов остается подключенным.</span><span class="sxs-lookup"><span data-stu-id="9b640-130">Call remains connected.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

