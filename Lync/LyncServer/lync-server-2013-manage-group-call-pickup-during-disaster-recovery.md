---
title: 'Lync Server 2013: Управление групповой отправке звонков во время аварийного восстановления'
description: 'Lync Server 2013: Управление отправке звонков по группам во время аварийного восстановления.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Manage Group Call Pickup during disaster recovery
ms:assetid: 2d32f19f-c649-4a72-a4fb-edd338e3a7cc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945618(v=OCS.15)
ms:contentKeyID: 51541455
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 04d85bc83cfe35571c2b0f47f707c9dcd8037d80
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48555285"
---
# <a name="manage-group-call-pickup-during-disaster-recovery-in-lync-server-2013"></a><span data-ttu-id="873ac-103">Управление отправке звонков по группам во время аварийного восстановления в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="873ac-103">Manage Group Call Pickup during disaster recovery in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="873ac-104">_**Последнее изменение темы:** 2013-01-30_</span><span class="sxs-lookup"><span data-stu-id="873ac-104">_**Topic Last Modified:** 2013-01-30_</span></span>

<span data-ttu-id="873ac-105">Когда интерфейсный пул становится недоступен из-за незапланированного инцидента, происходит сбой службы в резервном пуле.</span><span class="sxs-lookup"><span data-stu-id="873ac-105">When a Front End pool becomes unavailable due an unplanned incident, service is failed over to the backup pool.</span></span> <span data-ttu-id="873ac-106">Во время отработки отказа в резервный пул пользователи перенаправляются в резервный пул и находятся в режиме устойчивости.</span><span class="sxs-lookup"><span data-stu-id="873ac-106">During failover to the backup pool, users are redirected to the backup pool and are in resiliency mode.</span></span> <span data-ttu-id="873ac-107">В режиме устойчивости пользователи не могут получать звонки других пользователей или совершать вызовы, которые отбираются другими пользователями.</span><span class="sxs-lookup"><span data-stu-id="873ac-107">While in resiliency mode, users cannot pick up other users' calls or have their calls picked up by other users.</span></span> <span data-ttu-id="873ac-108">По завершении отработки отказа пользователи могут повторно использовать групповую отработку звонка.</span><span class="sxs-lookup"><span data-stu-id="873ac-108">When failover is complete, users can again use Group Call Pickup as usual.</span></span>

<span data-ttu-id="873ac-109">Во время восстановления размещения в основном пуле пользователи перенаправляются в основной пул и еще раз в режиме устойчивости.</span><span class="sxs-lookup"><span data-stu-id="873ac-109">During failback to the primary pool, users are redirected to the primary pool and are again in resiliency mode.</span></span> <span data-ttu-id="873ac-110">Функция отправки групповых вызовов недоступна до тех пор, пока пользователи не выходят из режима устойчивости.</span><span class="sxs-lookup"><span data-stu-id="873ac-110">Group Call Pickup functionality is not available until the users are out of resiliency mode.</span></span>

<span data-ttu-id="873ac-111">В этом разделе рассматриваются некоторые вопросы, касающиеся групповой отправки звонков во время аварийного восстановления, а также описание взаимодействия с пользователем.</span><span class="sxs-lookup"><span data-stu-id="873ac-111">This section discusses some considerations for Group Call Pickup during disaster recovery and also describes the user experience.</span></span>

<div>

## <a name="considerations-for-group-call-pickup-during-disaster-recovery"></a><span data-ttu-id="873ac-112">Рекомендации по групповому отправке вызовов во время аварийного восстановления</span><span class="sxs-lookup"><span data-stu-id="873ac-112">Considerations for Group Call Pickup During Disaster Recovery</span></span>

<span data-ttu-id="873ac-113">Во время аварийного восстановления пользователи, которые были перенаправлены в резервный пул в рамках процесса отработки отказа, используют приложение парковки вызовов, запущенное в резервном пуле, для номеров групп ответа на звонки.</span><span class="sxs-lookup"><span data-stu-id="873ac-113">During disaster recovery, users who have been redirected to the backup pool as part of the failover process use the Call Park application running in the backup pool for the call pickup group numbers.</span></span> <span data-ttu-id="873ac-114">Таким образом, для поддержки групповой отправки звонков во время аварийного восстановления необходимо, чтобы приложение парковки вызовов было развернуто и включено как в основном пуле, так и в резервном пуле.</span><span class="sxs-lookup"><span data-stu-id="873ac-114">Therefore, support for Group Call Pickup during disaster recovery requires the Call Park application to be deployed and enabled in both the primary pool and the backup pool.</span></span>

<span data-ttu-id="873ac-115">Диапазоны номеров для группового ответа на звонки в таблице орбит парковки вызовов необходимо перенаправить в пул резервного копирования после завершения процесса отработки отказа в резервный пул.</span><span class="sxs-lookup"><span data-stu-id="873ac-115">The Group Call Pickup number ranges in the call park orbit table must be redirected to the backup pool after the failover process to the backup pool is complete.</span></span> <span data-ttu-id="873ac-116">После завершения процесса восстановления размещения до основного пула диапазоны номеров необходимо перенаправить обратно в основной пул.</span><span class="sxs-lookup"><span data-stu-id="873ac-116">The number ranges must be redirected back to the primary pool after the failback process to the primary pool is complete.</span></span> <span data-ttu-id="873ac-117">Чтобы перенаправить диапазоны ответа на вызовы групп, используйте командлет **Set – CsCallParkOrbit** .</span><span class="sxs-lookup"><span data-stu-id="873ac-117">To redirect the Group Call Pickup ranges, use the **Set-CsCallParkOrbit** cmdlet.</span></span>

<span data-ttu-id="873ac-118">При развертывании нового пула с другим полным доменным именем (FQDN) для замены основного пула необходимо переназначить все диапазоны номеров ответа группы, связанные с основным пулом, на полное доменное имя нового пула.</span><span class="sxs-lookup"><span data-stu-id="873ac-118">If you deploy a new pool with a different fully qualified domain name (FQDN) to replace the primary pool, you need to reassign all the Group Call Pickup number ranges that were associated with the primary pool to the FQDN of the new pool.</span></span> <span data-ttu-id="873ac-119">Чтобы переназначить диапазоны номеров новому пулу, можно использовать командлет **Set – CsCallParkOrbit** .</span><span class="sxs-lookup"><span data-stu-id="873ac-119">To reassign number ranges to the new pool, you can use the **Set-CsCallParkOrbit** cmdlet.</span></span> <span data-ttu-id="873ac-120">Дополнительные сведения о командлете **Set – CsCallParkOrbit** см. в разделе [Set – CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/Set-CsCallParkOrbit).</span><span class="sxs-lookup"><span data-stu-id="873ac-120">For details about the **Set-CsCallParkOrbit** cmdlet, see [Set-CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/Set-CsCallParkOrbit).</span></span>

</div>

<div>

## <a name="group-call-pickup-experience-during-pool-failure"></a><span data-ttu-id="873ac-121">Взаимодействие группового ответа при отказе пула</span><span class="sxs-lookup"><span data-stu-id="873ac-121">Group Call Pickup Experience During Pool Failure</span></span>

<span data-ttu-id="873ac-122">В приведенной ниже таблице представлена сводная информация о способах отправки звонков по группам с помощью этапов аварийного восстановления.</span><span class="sxs-lookup"><span data-stu-id="873ac-122">The following table summarizes the Group Call Pickup experience through the phases of disaster recovery.</span></span>

### <a name="user-experience-during-disaster-recovery"></a><span data-ttu-id="873ac-123">Возможности пользователей в ходе аварийного восстановления</span><span class="sxs-lookup"><span data-stu-id="873ac-123">User Experience During Disaster Recovery</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="873ac-124">Состоянии вызова</span><span class="sxs-lookup"><span data-stu-id="873ac-124">Call state</span></span></th>
<th><span data-ttu-id="873ac-125">Отработка отказа для резервного пула</span><span class="sxs-lookup"><span data-stu-id="873ac-125">Failover to backup pool</span></span></th>
<th><span data-ttu-id="873ac-126">Восстановление размещения в основном пуле</span><span class="sxs-lookup"><span data-stu-id="873ac-126">Failback to primary pool</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="873ac-127">Новые звонки</span><span class="sxs-lookup"><span data-stu-id="873ac-127">New calls</span></span></p></td>
<td><p><span data-ttu-id="873ac-128"><strong>В процессе отработки отказа:</strong></span><span class="sxs-lookup"><span data-stu-id="873ac-128"><strong>During failover process:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="873ac-129">Отправка группового вызова недоступна для пользователей в режиме устойчивости</span><span class="sxs-lookup"><span data-stu-id="873ac-129">Group Call Pickup not available for users in resiliency mode</span></span></p></li>
</ul>
<p><span data-ttu-id="873ac-130"><strong>После завершения отработки отказа:</strong></span><span class="sxs-lookup"><span data-stu-id="873ac-130"><strong>After failover is complete:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="873ac-131">Групповой ответ на звонки, доступный при выходе пользователей из диапазона номеров для обеспечения устойчивости и групп, перенаправляется в резервный пул</span><span class="sxs-lookup"><span data-stu-id="873ac-131">Group Call Pickup available when users out of resiliency and Group Call Pickup number ranges are redirected to backup pool</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="873ac-132"><strong>В процессе восстановления размещения:</strong></span><span class="sxs-lookup"><span data-stu-id="873ac-132"><strong>During failback process:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="873ac-133">Отправка группового вызова недоступна для пользователей в режиме устойчивости</span><span class="sxs-lookup"><span data-stu-id="873ac-133">Group Call Pickup not available for users in resiliency mode</span></span></p></li>
</ul>
<p><span data-ttu-id="873ac-134"><strong>После завершения работы с восстановлением:</strong></span><span class="sxs-lookup"><span data-stu-id="873ac-134"><strong>After failback is complete:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="873ac-135">Групповой ответ на звонки, доступный при выходе пользователей из диапазона номеров для обеспечения устойчивости и групп, перенаправляется обратно в основной пул</span><span class="sxs-lookup"><span data-stu-id="873ac-135">Group Call Pickup available when users out of resiliency and Group Call Pickup number ranges are redirected back to primary pool</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="873ac-136">Вызовов в очереди раскладки вызовов в группе</span><span class="sxs-lookup"><span data-stu-id="873ac-136">Calls in Group Call Pickup queue</span></span></p></td>
<td><p><span data-ttu-id="873ac-137"><strong>В процессе отработки отказа:</strong></span><span class="sxs-lookup"><span data-stu-id="873ac-137"><strong>During failover process:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="873ac-138">Невозможно ответить на звонки в очереди с помощью групповой отправки звонков.</span><span class="sxs-lookup"><span data-stu-id="873ac-138">Calls in queue cannot be answered through Group Call Pickup.</span></span></p></li>
</ul>
<p><span data-ttu-id="873ac-139"><strong>После завершения отработки отказа:</strong></span><span class="sxs-lookup"><span data-stu-id="873ac-139"><strong>After failover is complete:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="873ac-140">Нет вызовов в этом состоянии</span><span class="sxs-lookup"><span data-stu-id="873ac-140">No calls in this state</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="873ac-141"><strong>В процессе восстановления размещения:</strong></span><span class="sxs-lookup"><span data-stu-id="873ac-141"><strong>During failback process:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="873ac-142">Невозможно ответить на звонки в очереди с помощью групповой отправки звонков.</span><span class="sxs-lookup"><span data-stu-id="873ac-142">Calls in queue cannot be answered through Group Call Pickup.</span></span></p></li>
</ul>
<p><span data-ttu-id="873ac-143"><strong>После завершения работы с восстановлением:</strong></span><span class="sxs-lookup"><span data-stu-id="873ac-143"><strong>After failback is complete:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="873ac-144">Невозможно ответить на звонки в очереди с помощью групповой отправки звонков.</span><span class="sxs-lookup"><span data-stu-id="873ac-144">Calls in queue cannot be answered through Group Call Pickup.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="873ac-145">Установленный Звонок</span><span class="sxs-lookup"><span data-stu-id="873ac-145">Established call</span></span></p></td>
<td><p><span data-ttu-id="873ac-146"><strong>В процессе отработки отказа:</strong></span><span class="sxs-lookup"><span data-stu-id="873ac-146"><strong>During failover process:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="873ac-147">Звонки остаются подключенными</span><span class="sxs-lookup"><span data-stu-id="873ac-147">Calls stay connected</span></span></p></li>
</ul>
<p><span data-ttu-id="873ac-148"><strong>После завершения отработки отказа:</strong></span><span class="sxs-lookup"><span data-stu-id="873ac-148"><strong>After failover is complete:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="873ac-149">Звонки остаются подключенными</span><span class="sxs-lookup"><span data-stu-id="873ac-149">Calls stay connected</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="873ac-150"><strong>В процессе восстановления размещения:</strong></span><span class="sxs-lookup"><span data-stu-id="873ac-150"><strong>During failback process:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="873ac-151">Звонки остаются подключенными</span><span class="sxs-lookup"><span data-stu-id="873ac-151">Calls stay connected</span></span></p></li>
</ul>
<p><span data-ttu-id="873ac-152"><strong>После завершения работы с восстановлением:</strong></span><span class="sxs-lookup"><span data-stu-id="873ac-152"><strong>After failback is complete:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="873ac-153">Звонки остаются подключенными</span><span class="sxs-lookup"><span data-stu-id="873ac-153">Calls stay connected</span></span></p></li>
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

