---
title: 'Lync Server 2013: Управление расведением группового звонка во время аварийного восстановления'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Manage Group Call Pickup during disaster recovery
ms:assetid: 2d32f19f-c649-4a72-a4fb-edd338e3a7cc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945618(v=OCS.15)
ms:contentKeyID: 51541455
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bed21a672dfecab4c3cc8d828fd40f52bd82a363
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34828364"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="manage-group-call-pickup-during-disaster-recovery-in-lync-server-2013"></a><span data-ttu-id="48c74-102">Управление расведением группового звонка во время восстановления после аварии в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="48c74-102">Manage Group Call Pickup during disaster recovery in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="48c74-103">_**Тема последнего изменения:** 2013-01-30_</span><span class="sxs-lookup"><span data-stu-id="48c74-103">_**Topic Last Modified:** 2013-01-30_</span></span>

<span data-ttu-id="48c74-104">Когда пул переднего плана становится недоступен из-за незапланированного инцидента, служба переключается на резервный пул.</span><span class="sxs-lookup"><span data-stu-id="48c74-104">When a Front End pool becomes unavailable due an unplanned incident, service is failed over to the backup pool.</span></span> <span data-ttu-id="48c74-105">При переходе на другой ресурс в пул резервной копии пользователи перенаправляются в пул резервных копий и в режиме устойчивости.</span><span class="sxs-lookup"><span data-stu-id="48c74-105">During failover to the backup pool, users are redirected to the backup pool and are in resiliency mode.</span></span> <span data-ttu-id="48c74-106">В режиме устойчивости пользователи не могут принимать звонки других пользователей или звонить другим пользователям.</span><span class="sxs-lookup"><span data-stu-id="48c74-106">While in resiliency mode, users cannot pick up other users' calls or have their calls picked up by other users.</span></span> <span data-ttu-id="48c74-107">После завершения перехода на другой ресурс пользователи могут снова использовать функцию отправки групп.</span><span class="sxs-lookup"><span data-stu-id="48c74-107">When failover is complete, users can again use Group Call Pickup as usual.</span></span>

<span data-ttu-id="48c74-108">При восстановлении из основного пула пользователи перенаправляются в основной пул и снова находятся в режиме устойчивости.</span><span class="sxs-lookup"><span data-stu-id="48c74-108">During failback to the primary pool, users are redirected to the primary pool and are again in resiliency mode.</span></span> <span data-ttu-id="48c74-109">Функция отправки группового звонка недоступна, пока пользователи не выходили из режима устойчивости.</span><span class="sxs-lookup"><span data-stu-id="48c74-109">Group Call Pickup functionality is not available until the users are out of resiliency mode.</span></span>

<span data-ttu-id="48c74-110">В этом разделе рассматриваются вопросы, касающиеся отправки группового звонка во время аварийного восстановления, а также описание взаимодействия с пользователем.</span><span class="sxs-lookup"><span data-stu-id="48c74-110">This section discusses some considerations for Group Call Pickup during disaster recovery and also describes the user experience.</span></span>

<div>

## <a name="considerations-for-group-call-pickup-during-disaster-recovery"></a><span data-ttu-id="48c74-111">Рекомендации по выбору группового звонка во время аварийного восстановления</span><span class="sxs-lookup"><span data-stu-id="48c74-111">Considerations for Group Call Pickup During Disaster Recovery</span></span>

<span data-ttu-id="48c74-112">При аварийном восстановлении пользователи, которые были перенаправлены в резервный пул в рамках процесса перемещения, используют приложение для остановки звонков в пуле резервных копий для номеров групп для отправки звонков.</span><span class="sxs-lookup"><span data-stu-id="48c74-112">During disaster recovery, users who have been redirected to the backup pool as part of the failover process use the Call Park application running in the backup pool for the call pickup group numbers.</span></span> <span data-ttu-id="48c74-113">Следовательно, для поддержки отправки группового звонка во время аварийного восстановления необходимо, чтобы приложение парковки на использование было развернуто и включено как в основном пуле, так и в пуле резервных копий.</span><span class="sxs-lookup"><span data-stu-id="48c74-113">Therefore, support for Group Call Pickup during disaster recovery requires the Call Park application to be deployed and enabled in both the primary pool and the backup pool.</span></span>

<span data-ttu-id="48c74-114">Диапазоны номеров раскладки для групповых звонков в таблице "приостановить Звонок" необходимо перенаправлять в пул резервных копий после завершения процесса перемещения в пул резервной копии.</span><span class="sxs-lookup"><span data-stu-id="48c74-114">The Group Call Pickup number ranges in the call park orbit table must be redirected to the backup pool after the failover process to the backup pool is complete.</span></span> <span data-ttu-id="48c74-115">После завершения процесса восстановления размещения для основного пула диапазоны номеров необходимо перенаправлять обратно в основной пул.</span><span class="sxs-lookup"><span data-stu-id="48c74-115">The number ranges must be redirected back to the primary pool after the failback process to the primary pool is complete.</span></span> <span data-ttu-id="48c74-116">Чтобы перенаправить диапазоны отправки для групповых звонков, используйте командлет **Set-кскаллпаркорбит** .</span><span class="sxs-lookup"><span data-stu-id="48c74-116">To redirect the Group Call Pickup ranges, use the **Set-CsCallParkOrbit** cmdlet.</span></span>

<span data-ttu-id="48c74-117">При развертывании нового пула с использованием другого полного доменного имени (FQDN) для замены основного пула необходимо переназначить все диапазоны номеров отправки групповых звонков, которые были связаны с основным пулом, в полное доменное имя нового пула.</span><span class="sxs-lookup"><span data-stu-id="48c74-117">If you deploy a new pool with a different fully qualified domain name (FQDN) to replace the primary pool, you need to reassign all the Group Call Pickup number ranges that were associated with the primary pool to the FQDN of the new pool.</span></span> <span data-ttu-id="48c74-118">Чтобы переназначить диапазоны номеров в новый пул, можно использовать командлет **Set-кскаллпаркорбит** .</span><span class="sxs-lookup"><span data-stu-id="48c74-118">To reassign number ranges to the new pool, you can use the **Set-CsCallParkOrbit** cmdlet.</span></span> <span data-ttu-id="48c74-119">Подробные сведения о командлете **Set-кскаллпаркорбит** можно найти в статьях [Set-кскаллпаркорбит](https://docs.microsoft.com/powershell/module/skype/Set-CsCallParkOrbit).</span><span class="sxs-lookup"><span data-stu-id="48c74-119">For details about the **Set-CsCallParkOrbit** cmdlet, see [Set-CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/Set-CsCallParkOrbit).</span></span>

</div>

<div>

## <a name="group-call-pickup-experience-during-pool-failure"></a><span data-ttu-id="48c74-120">Использование функции отправки группового звонка в случае сбоя пула</span><span class="sxs-lookup"><span data-stu-id="48c74-120">Group Call Pickup Experience During Pool Failure</span></span>

<span data-ttu-id="48c74-121">В приведенной ниже таблице описаны возможности отправки групповых звонков с помощью этапов восстановления после аварии.</span><span class="sxs-lookup"><span data-stu-id="48c74-121">The following table summarizes the Group Call Pickup experience through the phases of disaster recovery.</span></span>

### <a name="user-experience-during-disaster-recovery"></a><span data-ttu-id="48c74-122">Взаимодействие с пользователем во время аварийного восстановления</span><span class="sxs-lookup"><span data-stu-id="48c74-122">User Experience During Disaster Recovery</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="48c74-123">Состояние звонка</span><span class="sxs-lookup"><span data-stu-id="48c74-123">Call state</span></span></th>
<th><span data-ttu-id="48c74-124">Отработка отказа для резервного пула</span><span class="sxs-lookup"><span data-stu-id="48c74-124">Failover to backup pool</span></span></th>
<th><span data-ttu-id="48c74-125">Восстановление размещения для основного пула</span><span class="sxs-lookup"><span data-stu-id="48c74-125">Failback to primary pool</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="48c74-126">Новые звонки</span><span class="sxs-lookup"><span data-stu-id="48c74-126">New calls</span></span></p></td>
<td><p><span data-ttu-id="48c74-127"><strong>В процессе отработки отказа:</strong></span><span class="sxs-lookup"><span data-stu-id="48c74-127"><strong>During failover process:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="48c74-128">Отправка группового звонка недоступна для пользователей в режиме устойчивости</span><span class="sxs-lookup"><span data-stu-id="48c74-128">Group Call Pickup not available for users in resiliency mode</span></span></p></li>
</ul>
<p><span data-ttu-id="48c74-129"><strong>После завершения отработки отказа:</strong></span><span class="sxs-lookup"><span data-stu-id="48c74-129"><strong>After failover is complete:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="48c74-130">Функция отправки группового звонка доступна, когда пользователь выходит из диапазона номеров для отправки и нумерации для групповых звонков, которые перенаправляются в пул резервного копирования</span><span class="sxs-lookup"><span data-stu-id="48c74-130">Group Call Pickup available when users out of resiliency and Group Call Pickup number ranges are redirected to backup pool</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="48c74-131"><strong>В процессе восстановления размещения:</strong></span><span class="sxs-lookup"><span data-stu-id="48c74-131"><strong>During failback process:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="48c74-132">Отправка группового звонка недоступна для пользователей в режиме устойчивости</span><span class="sxs-lookup"><span data-stu-id="48c74-132">Group Call Pickup not available for users in resiliency mode</span></span></p></li>
</ul>
<p><span data-ttu-id="48c74-133"><strong>После завершения восстановления после сбоя выполните указанные ниже действия.</strong></span><span class="sxs-lookup"><span data-stu-id="48c74-133"><strong>After failback is complete:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="48c74-134">Функция отправки группового вызова доступна, когда пользователь выходит из диапазонов устойчивости и номеров для отправки групповых вызовов, перенаправляется обратно в основной пул</span><span class="sxs-lookup"><span data-stu-id="48c74-134">Group Call Pickup available when users out of resiliency and Group Call Pickup number ranges are redirected back to primary pool</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="48c74-135">В очереди раскладки звонков в групповых звонках</span><span class="sxs-lookup"><span data-stu-id="48c74-135">Calls in Group Call Pickup queue</span></span></p></td>
<td><p><span data-ttu-id="48c74-136"><strong>В процессе отработки отказа:</strong></span><span class="sxs-lookup"><span data-stu-id="48c74-136"><strong>During failover process:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="48c74-137">Звонки из очереди нельзя отвечать на запросы с помощью группового звонка.</span><span class="sxs-lookup"><span data-stu-id="48c74-137">Calls in queue cannot be answered through Group Call Pickup.</span></span></p></li>
</ul>
<p><span data-ttu-id="48c74-138"><strong>После завершения отработки отказа:</strong></span><span class="sxs-lookup"><span data-stu-id="48c74-138"><strong>After failover is complete:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="48c74-139">Нет вызовов в этом состоянии</span><span class="sxs-lookup"><span data-stu-id="48c74-139">No calls in this state</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="48c74-140"><strong>В процессе восстановления размещения:</strong></span><span class="sxs-lookup"><span data-stu-id="48c74-140"><strong>During failback process:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="48c74-141">Звонки из очереди нельзя отвечать на запросы с помощью группового звонка.</span><span class="sxs-lookup"><span data-stu-id="48c74-141">Calls in queue cannot be answered through Group Call Pickup.</span></span></p></li>
</ul>
<p><span data-ttu-id="48c74-142"><strong>После завершения восстановления после сбоя выполните указанные ниже действия.</strong></span><span class="sxs-lookup"><span data-stu-id="48c74-142"><strong>After failback is complete:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="48c74-143">Звонки из очереди нельзя отвечать на запросы с помощью группового звонка.</span><span class="sxs-lookup"><span data-stu-id="48c74-143">Calls in queue cannot be answered through Group Call Pickup.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="48c74-144">Установленный Звонок</span><span class="sxs-lookup"><span data-stu-id="48c74-144">Established call</span></span></p></td>
<td><p><span data-ttu-id="48c74-145"><strong>В процессе отработки отказа:</strong></span><span class="sxs-lookup"><span data-stu-id="48c74-145"><strong>During failover process:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="48c74-146">Звонки остаются подключенными</span><span class="sxs-lookup"><span data-stu-id="48c74-146">Calls stay connected</span></span></p></li>
</ul>
<p><span data-ttu-id="48c74-147"><strong>После завершения отработки отказа:</strong></span><span class="sxs-lookup"><span data-stu-id="48c74-147"><strong>After failover is complete:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="48c74-148">Звонки остаются подключенными</span><span class="sxs-lookup"><span data-stu-id="48c74-148">Calls stay connected</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="48c74-149"><strong>В процессе восстановления размещения:</strong></span><span class="sxs-lookup"><span data-stu-id="48c74-149"><strong>During failback process:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="48c74-150">Звонки остаются подключенными</span><span class="sxs-lookup"><span data-stu-id="48c74-150">Calls stay connected</span></span></p></li>
</ul>
<p><span data-ttu-id="48c74-151"><strong>После завершения восстановления после сбоя выполните указанные ниже действия.</strong></span><span class="sxs-lookup"><span data-stu-id="48c74-151"><strong>After failback is complete:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="48c74-152">Звонки остаются подключенными</span><span class="sxs-lookup"><span data-stu-id="48c74-152">Calls stay connected</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

