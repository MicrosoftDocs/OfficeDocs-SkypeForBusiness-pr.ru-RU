---
title: 'Lync Server 2013: работа парковки вызовов во время сбоя пула'
description: 'Lync Server 2013: работа парковки вызовов во время сбоя пула.'
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
ms.openlocfilehash: 6b97a0af13d378b0753979c32b6d5ffe7a525cf0
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48565275"
---
# <a name="call-park-experience-in-lync-server-2013-during-pool-failure"></a><span data-ttu-id="81f35-103">Функции парковки вызовов в Lync Server 2013 во время сбоя пула</span><span class="sxs-lookup"><span data-stu-id="81f35-103">Call Park experience in Lync Server 2013 during pool failure</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="81f35-104">_**Последнее изменение темы:** 2012-09-10_</span><span class="sxs-lookup"><span data-stu-id="81f35-104">_**Topic Last Modified:** 2012-09-10_</span></span>

<span data-ttu-id="81f35-105">Если интерфейсный пул становится недоступен из-за незапланированного инцидента, вызовы, которые были приостановлены, но еще не получены, отключаются.</span><span class="sxs-lookup"><span data-stu-id="81f35-105">When a Front End pool becomes unavailable due an unplanned incident, calls that have been parked but not yet retrieved are disconnected.</span></span> <span data-ttu-id="81f35-106">При отработке отказа с переключением на резервный пул пользователи перенаправляются на резервный пул и находятся в режиме устойчивости.</span><span class="sxs-lookup"><span data-stu-id="81f35-106">During failover to a backup pool, users are redirected to the backup pool and are in resiliency mode.</span></span> <span data-ttu-id="81f35-107">В режиме устойчивости пользователи не смогут парковать вызовы, но могут переводить вызовы на удержание и переадресовывать их.</span><span class="sxs-lookup"><span data-stu-id="81f35-107">While in resiliency mode, users cannot park calls, but they can place calls on hold and transfer them.</span></span> <span data-ttu-id="81f35-108">По завершении отработки отказа пользователи могут снова парковать вызовы и извлекать их в обычном режиме.</span><span class="sxs-lookup"><span data-stu-id="81f35-108">When failover is complete, calls can again be parked and retrieved as usual.</span></span> <span data-ttu-id="81f35-109">При восстановлении размещения пользователи не могут парковать вызовы, пока не выйдут из режима устойчивости.</span><span class="sxs-lookup"><span data-stu-id="81f35-109">During failback, users cannot park calls until they are out of resiliency mode.</span></span>

<span data-ttu-id="81f35-110">Во время аварийного восстановления пользователи, которые были перенаправлены в резервный пул в рамках процесса отработки отказа, используют приложение парковки вызовов, развернутое в резервном пуле.</span><span class="sxs-lookup"><span data-stu-id="81f35-110">During disaster recovery, users who have been redirected to the backup pool as part of the failover process use the Call Park application that is deployed in the backup pool.</span></span> <span data-ttu-id="81f35-111">Таким образом, пользователи, которые перенаправляются в резервный пул, используют параметры парковки вызовов, настроенные для приложения парковки вызовов в резервном пуле.</span><span class="sxs-lookup"><span data-stu-id="81f35-111">Therefore, users who are redirected to the backup pool use the call park settings that are configured for the Call Park application in the backup pool.</span></span>

<span data-ttu-id="81f35-112">В приведенной ниже таблице представлена сводная информация о приостановке вызовов через этапы аварийного восстановления.</span><span class="sxs-lookup"><span data-stu-id="81f35-112">The following table summarizes the Call Park experience through the phases of disaster recovery.</span></span>

### <a name="user-experience-during-disaster-recovery"></a><span data-ttu-id="81f35-113">Возможности пользователей в ходе аварийного восстановления</span><span class="sxs-lookup"><span data-stu-id="81f35-113">User Experience During Disaster Recovery</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="81f35-114">Состоянии вызова</span><span class="sxs-lookup"><span data-stu-id="81f35-114">Call state</span></span></th>
<th><span data-ttu-id="81f35-115">Когда происходит отключение электричества</span><span class="sxs-lookup"><span data-stu-id="81f35-115">When outage occurs</span></span></th>
<th><span data-ttu-id="81f35-116">Во время отработки отказа</span><span class="sxs-lookup"><span data-stu-id="81f35-116">During failover</span></span></th>
<th><span data-ttu-id="81f35-117">Во время восстановления размещения</span><span class="sxs-lookup"><span data-stu-id="81f35-117">During failback</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="81f35-118">Вызов еще не запаркован</span><span class="sxs-lookup"><span data-stu-id="81f35-118">Call not yet parked</span></span></p></td>
<td><p><span data-ttu-id="81f35-119">Вызов не разъединяется, но его парковка невозможна</span><span class="sxs-lookup"><span data-stu-id="81f35-119">Call remains connected, but cannot be parked.</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="81f35-120">Во время отработки отказа вызов нельзя запарковать, если пользователи находятся в режиме устойчивости, но его можно перевести на удержание и переадресовать.</span><span class="sxs-lookup"><span data-stu-id="81f35-120">During failover, call cannot be parked while users are in resiliency mode, but can be put on hold and transferred.</span></span></p></li>
<li><p><span data-ttu-id="81f35-121">При завершении отработки отказа вызовы можно парковать и извлекать.</span><span class="sxs-lookup"><span data-stu-id="81f35-121">When failover completes, call can be parked and retrieved.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="81f35-122">Во время восстановления размещения вызов нельзя запарковать, если пользователи находятся в режиме устойчивости, но его можно перевести на удержание и переадресовать.</span><span class="sxs-lookup"><span data-stu-id="81f35-122">During failback, call cannot be parked while users are in resiliency mode, but can be put on hold and transferred.</span></span></p></li>
<li><p><span data-ttu-id="81f35-123">При завершении восстановления размещения вызовы можно парковать и извлекать.</span><span class="sxs-lookup"><span data-stu-id="81f35-123">When failback completes, call can be parked and retrieved.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="81f35-124">Вызов запаркован, но еще не извлечен.</span><span class="sxs-lookup"><span data-stu-id="81f35-124">Call parked, but not yet retrieved</span></span></p></td>
<td><p><span data-ttu-id="81f35-125">Вызов разъединен.</span><span class="sxs-lookup"><span data-stu-id="81f35-125">Call is disconnected.</span></span></p></td>
<td><p><span data-ttu-id="81f35-126">Нет вызовов в этом состоянии.</span><span class="sxs-lookup"><span data-stu-id="81f35-126">No calls in this state.</span></span></p></td>
<td><p><span data-ttu-id="81f35-127">Вызов остается запаркованным.</span><span class="sxs-lookup"><span data-stu-id="81f35-127">Call remains parked.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="81f35-128">Запаркованный вызов уже извлечен.</span><span class="sxs-lookup"><span data-stu-id="81f35-128">Parked call already retrieved</span></span></p></td>
<td><p><span data-ttu-id="81f35-129">Вызов остается подключенным.</span><span class="sxs-lookup"><span data-stu-id="81f35-129">Call remains connected.</span></span></p></td>
<td><p><span data-ttu-id="81f35-130">Вызов остается подключенным.</span><span class="sxs-lookup"><span data-stu-id="81f35-130">Call remains connected.</span></span></p></td>
<td><p><span data-ttu-id="81f35-131">Вызов остается подключенным.</span><span class="sxs-lookup"><span data-stu-id="81f35-131">Call remains connected.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

