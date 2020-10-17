---
title: 'Lync Server 2013: Управление групповой отправке звонков во время аварийного восстановления'
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
ms.openlocfilehash: d181570b55ce175a63ac1ac1f218ee99aec7a5a0
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48534536"
---
# <a name="manage-group-call-pickup-during-disaster-recovery-in-lync-server-2013"></a><span data-ttu-id="2e772-102">Управление отправке звонков по группам во время аварийного восстановления в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2e772-102">Manage Group Call Pickup during disaster recovery in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2e772-103">_**Последнее изменение темы:** 2013-01-30_</span><span class="sxs-lookup"><span data-stu-id="2e772-103">_**Topic Last Modified:** 2013-01-30_</span></span>

<span data-ttu-id="2e772-104">Когда интерфейсный пул становится недоступен из-за незапланированного инцидента, происходит сбой службы в резервном пуле.</span><span class="sxs-lookup"><span data-stu-id="2e772-104">When a Front End pool becomes unavailable due an unplanned incident, service is failed over to the backup pool.</span></span> <span data-ttu-id="2e772-105">Во время отработки отказа в резервный пул пользователи перенаправляются в резервный пул и находятся в режиме устойчивости.</span><span class="sxs-lookup"><span data-stu-id="2e772-105">During failover to the backup pool, users are redirected to the backup pool and are in resiliency mode.</span></span> <span data-ttu-id="2e772-106">В режиме устойчивости пользователи не могут получать звонки других пользователей или совершать вызовы, которые отбираются другими пользователями.</span><span class="sxs-lookup"><span data-stu-id="2e772-106">While in resiliency mode, users cannot pick up other users' calls or have their calls picked up by other users.</span></span> <span data-ttu-id="2e772-107">По завершении отработки отказа пользователи могут повторно использовать групповую отработку звонка.</span><span class="sxs-lookup"><span data-stu-id="2e772-107">When failover is complete, users can again use Group Call Pickup as usual.</span></span>

<span data-ttu-id="2e772-108">Во время восстановления размещения в основном пуле пользователи перенаправляются в основной пул и еще раз в режиме устойчивости.</span><span class="sxs-lookup"><span data-stu-id="2e772-108">During failback to the primary pool, users are redirected to the primary pool and are again in resiliency mode.</span></span> <span data-ttu-id="2e772-109">Функция отправки групповых вызовов недоступна до тех пор, пока пользователи не выходят из режима устойчивости.</span><span class="sxs-lookup"><span data-stu-id="2e772-109">Group Call Pickup functionality is not available until the users are out of resiliency mode.</span></span>

<span data-ttu-id="2e772-110">В этом разделе рассматриваются некоторые вопросы, касающиеся групповой отправки звонков во время аварийного восстановления, а также описание взаимодействия с пользователем.</span><span class="sxs-lookup"><span data-stu-id="2e772-110">This section discusses some considerations for Group Call Pickup during disaster recovery and also describes the user experience.</span></span>

<div>

## <a name="considerations-for-group-call-pickup-during-disaster-recovery"></a><span data-ttu-id="2e772-111">Рекомендации по групповому отправке вызовов во время аварийного восстановления</span><span class="sxs-lookup"><span data-stu-id="2e772-111">Considerations for Group Call Pickup During Disaster Recovery</span></span>

<span data-ttu-id="2e772-112">Во время аварийного восстановления пользователи, которые были перенаправлены в резервный пул в рамках процесса отработки отказа, используют приложение парковки вызовов, запущенное в резервном пуле, для номеров групп ответа на звонки.</span><span class="sxs-lookup"><span data-stu-id="2e772-112">During disaster recovery, users who have been redirected to the backup pool as part of the failover process use the Call Park application running in the backup pool for the call pickup group numbers.</span></span> <span data-ttu-id="2e772-113">Таким образом, для поддержки групповой отправки звонков во время аварийного восстановления необходимо, чтобы приложение парковки вызовов было развернуто и включено как в основном пуле, так и в резервном пуле.</span><span class="sxs-lookup"><span data-stu-id="2e772-113">Therefore, support for Group Call Pickup during disaster recovery requires the Call Park application to be deployed and enabled in both the primary pool and the backup pool.</span></span>

<span data-ttu-id="2e772-114">Диапазоны номеров для группового ответа на звонки в таблице орбит парковки вызовов необходимо перенаправить в пул резервного копирования после завершения процесса отработки отказа в резервный пул.</span><span class="sxs-lookup"><span data-stu-id="2e772-114">The Group Call Pickup number ranges in the call park orbit table must be redirected to the backup pool after the failover process to the backup pool is complete.</span></span> <span data-ttu-id="2e772-115">После завершения процесса восстановления размещения до основного пула диапазоны номеров необходимо перенаправить обратно в основной пул.</span><span class="sxs-lookup"><span data-stu-id="2e772-115">The number ranges must be redirected back to the primary pool after the failback process to the primary pool is complete.</span></span> <span data-ttu-id="2e772-116">Чтобы перенаправить диапазоны ответа на вызовы групп, используйте командлет **Set – CsCallParkOrbit** .</span><span class="sxs-lookup"><span data-stu-id="2e772-116">To redirect the Group Call Pickup ranges, use the **Set-CsCallParkOrbit** cmdlet.</span></span>

<span data-ttu-id="2e772-117">При развертывании нового пула с другим полным доменным именем (FQDN) для замены основного пула необходимо переназначить все диапазоны номеров ответа группы, связанные с основным пулом, на полное доменное имя нового пула.</span><span class="sxs-lookup"><span data-stu-id="2e772-117">If you deploy a new pool with a different fully qualified domain name (FQDN) to replace the primary pool, you need to reassign all the Group Call Pickup number ranges that were associated with the primary pool to the FQDN of the new pool.</span></span> <span data-ttu-id="2e772-118">Чтобы переназначить диапазоны номеров новому пулу, можно использовать командлет **Set – CsCallParkOrbit** .</span><span class="sxs-lookup"><span data-stu-id="2e772-118">To reassign number ranges to the new pool, you can use the **Set-CsCallParkOrbit** cmdlet.</span></span> <span data-ttu-id="2e772-119">Дополнительные сведения о командлете **Set – CsCallParkOrbit** см. в разделе [Set – CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/Set-CsCallParkOrbit).</span><span class="sxs-lookup"><span data-stu-id="2e772-119">For details about the **Set-CsCallParkOrbit** cmdlet, see [Set-CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/Set-CsCallParkOrbit).</span></span>

</div>

<div>

## <a name="group-call-pickup-experience-during-pool-failure"></a><span data-ttu-id="2e772-120">Взаимодействие группового ответа при отказе пула</span><span class="sxs-lookup"><span data-stu-id="2e772-120">Group Call Pickup Experience During Pool Failure</span></span>

<span data-ttu-id="2e772-121">В приведенной ниже таблице представлена сводная информация о способах отправки звонков по группам с помощью этапов аварийного восстановления.</span><span class="sxs-lookup"><span data-stu-id="2e772-121">The following table summarizes the Group Call Pickup experience through the phases of disaster recovery.</span></span>

### <a name="user-experience-during-disaster-recovery"></a><span data-ttu-id="2e772-122">Возможности пользователей в ходе аварийного восстановления</span><span class="sxs-lookup"><span data-stu-id="2e772-122">User Experience During Disaster Recovery</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2e772-123">Состоянии вызова</span><span class="sxs-lookup"><span data-stu-id="2e772-123">Call state</span></span></th>
<th><span data-ttu-id="2e772-124">Отработка отказа для резервного пула</span><span class="sxs-lookup"><span data-stu-id="2e772-124">Failover to backup pool</span></span></th>
<th><span data-ttu-id="2e772-125">Восстановление размещения в основном пуле</span><span class="sxs-lookup"><span data-stu-id="2e772-125">Failback to primary pool</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2e772-126">Новые звонки</span><span class="sxs-lookup"><span data-stu-id="2e772-126">New calls</span></span></p></td>
<td><p><span data-ttu-id="2e772-127"><strong>В процессе отработки отказа:</strong></span><span class="sxs-lookup"><span data-stu-id="2e772-127"><strong>During failover process:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="2e772-128">Отправка группового вызова недоступна для пользователей в режиме устойчивости</span><span class="sxs-lookup"><span data-stu-id="2e772-128">Group Call Pickup not available for users in resiliency mode</span></span></p></li>
</ul>
<p><span data-ttu-id="2e772-129"><strong>После завершения отработки отказа:</strong></span><span class="sxs-lookup"><span data-stu-id="2e772-129"><strong>After failover is complete:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="2e772-130">Групповой ответ на звонки, доступный при выходе пользователей из диапазона номеров для обеспечения устойчивости и групп, перенаправляется в резервный пул</span><span class="sxs-lookup"><span data-stu-id="2e772-130">Group Call Pickup available when users out of resiliency and Group Call Pickup number ranges are redirected to backup pool</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="2e772-131"><strong>В процессе восстановления размещения:</strong></span><span class="sxs-lookup"><span data-stu-id="2e772-131"><strong>During failback process:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="2e772-132">Отправка группового вызова недоступна для пользователей в режиме устойчивости</span><span class="sxs-lookup"><span data-stu-id="2e772-132">Group Call Pickup not available for users in resiliency mode</span></span></p></li>
</ul>
<p><span data-ttu-id="2e772-133"><strong>После завершения работы с восстановлением:</strong></span><span class="sxs-lookup"><span data-stu-id="2e772-133"><strong>After failback is complete:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="2e772-134">Групповой ответ на звонки, доступный при выходе пользователей из диапазона номеров для обеспечения устойчивости и групп, перенаправляется обратно в основной пул</span><span class="sxs-lookup"><span data-stu-id="2e772-134">Group Call Pickup available when users out of resiliency and Group Call Pickup number ranges are redirected back to primary pool</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2e772-135">Вызовов в очереди раскладки вызовов в группе</span><span class="sxs-lookup"><span data-stu-id="2e772-135">Calls in Group Call Pickup queue</span></span></p></td>
<td><p><span data-ttu-id="2e772-136"><strong>В процессе отработки отказа:</strong></span><span class="sxs-lookup"><span data-stu-id="2e772-136"><strong>During failover process:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="2e772-137">Невозможно ответить на звонки в очереди с помощью групповой отправки звонков.</span><span class="sxs-lookup"><span data-stu-id="2e772-137">Calls in queue cannot be answered through Group Call Pickup.</span></span></p></li>
</ul>
<p><span data-ttu-id="2e772-138"><strong>После завершения отработки отказа:</strong></span><span class="sxs-lookup"><span data-stu-id="2e772-138"><strong>After failover is complete:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="2e772-139">Нет вызовов в этом состоянии</span><span class="sxs-lookup"><span data-stu-id="2e772-139">No calls in this state</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="2e772-140"><strong>В процессе восстановления размещения:</strong></span><span class="sxs-lookup"><span data-stu-id="2e772-140"><strong>During failback process:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="2e772-141">Невозможно ответить на звонки в очереди с помощью групповой отправки звонков.</span><span class="sxs-lookup"><span data-stu-id="2e772-141">Calls in queue cannot be answered through Group Call Pickup.</span></span></p></li>
</ul>
<p><span data-ttu-id="2e772-142"><strong>После завершения работы с восстановлением:</strong></span><span class="sxs-lookup"><span data-stu-id="2e772-142"><strong>After failback is complete:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="2e772-143">Невозможно ответить на звонки в очереди с помощью групповой отправки звонков.</span><span class="sxs-lookup"><span data-stu-id="2e772-143">Calls in queue cannot be answered through Group Call Pickup.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2e772-144">Установленный Звонок</span><span class="sxs-lookup"><span data-stu-id="2e772-144">Established call</span></span></p></td>
<td><p><span data-ttu-id="2e772-145"><strong>В процессе отработки отказа:</strong></span><span class="sxs-lookup"><span data-stu-id="2e772-145"><strong>During failover process:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="2e772-146">Звонки остаются подключенными</span><span class="sxs-lookup"><span data-stu-id="2e772-146">Calls stay connected</span></span></p></li>
</ul>
<p><span data-ttu-id="2e772-147"><strong>После завершения отработки отказа:</strong></span><span class="sxs-lookup"><span data-stu-id="2e772-147"><strong>After failover is complete:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="2e772-148">Звонки остаются подключенными</span><span class="sxs-lookup"><span data-stu-id="2e772-148">Calls stay connected</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="2e772-149"><strong>В процессе восстановления размещения:</strong></span><span class="sxs-lookup"><span data-stu-id="2e772-149"><strong>During failback process:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="2e772-150">Звонки остаются подключенными</span><span class="sxs-lookup"><span data-stu-id="2e772-150">Calls stay connected</span></span></p></li>
</ul>
<p><span data-ttu-id="2e772-151"><strong>После завершения работы с восстановлением:</strong></span><span class="sxs-lookup"><span data-stu-id="2e772-151"><strong>After failback is complete:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="2e772-152">Звонки остаются подключенными</span><span class="sxs-lookup"><span data-stu-id="2e772-152">Calls stay connected</span></span></p></li>
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

