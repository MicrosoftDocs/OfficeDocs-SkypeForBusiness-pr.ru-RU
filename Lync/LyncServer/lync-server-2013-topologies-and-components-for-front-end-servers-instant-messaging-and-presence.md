---
title: 'Lync Server 2013: топология и компоненты для серверов переднего плана, обмена мгновенными сообщениями и сведениями о присутствии'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Topologies and components for Front End Servers, instant messaging, and presence
ms:assetid: f08ce7a1-d14e-4a54-9771-a82c870658bf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412996(v=OCS.15)
ms:contentKeyID: 48185763
ms.date: 10/24/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 181ae682ec5ee1352c5d4f4280b4164fbbcd91f2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745249"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="topologies-and-components-for-front-end-servers-instant-messaging-and-presence-in-lync-server-2013"></a><span data-ttu-id="72407-102">Топология и компоненты для серверов переднего плана, обмена мгновенными сообщениями и сведениями о присутствии в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="72407-102">Topologies and components for Front End Servers, instant messaging, and presence in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="72407-103">_**Тема последнего изменения:** 2014-10-24_</span><span class="sxs-lookup"><span data-stu-id="72407-103">_**Topic Last Modified:** 2014-10-24_</span></span>

<span data-ttu-id="72407-104">Для обмена мгновенными сообщениями и сведениями о присутствии требуются только следующие компоненты:</span><span class="sxs-lookup"><span data-stu-id="72407-104">The only components required for instant messaging (IM) and presence are:</span></span>

  - <span data-ttu-id="72407-105">Серверы переднего плана вашей организации или серверы Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="72407-105">Your organization’s Front End Servers or Standard Edition servers.</span></span> <span data-ttu-id="72407-106">Функции обмена мгновенными сообщениями и сведениями о присутствии всегда включены на этих серверах.</span><span class="sxs-lookup"><span data-stu-id="72407-106">IM and presence capabilities are always enabled on these servers.</span></span>

  - <span data-ttu-id="72407-107">Подсистема балансировки нагрузки, если используется интерфейсный пул Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="72407-107">A load balancer, if you have an Enterprise Edition Front End pool.</span></span> <span data-ttu-id="72407-108">Дополнительные сведения можно найти в разделе [требования балансировки нагрузки для Lync Server 2013](lync-server-2013-load-balancing-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="72407-108">For more information, see [Load balancing requirements for Lync Server 2013](lync-server-2013-load-balancing-requirements.md).</span></span>

<div>

## <a name="planning-for-the-deployment-of-front-end-pools"></a><span data-ttu-id="72407-109">Планирование развертывания интерфейсных пулов на стороне сервера</span><span class="sxs-lookup"><span data-stu-id="72407-109">Planning for the Deployment of Front End Pools</span></span>

<span data-ttu-id="72407-110">В Lync Server 2013 архитектура пула переднего плана была изменена, и эти изменения повлияют на планирование и обслуживание пулов переднего плана.</span><span class="sxs-lookup"><span data-stu-id="72407-110">In Lync Server 2013, Front End pool architecture has changed, and these changes affect how you should plan and maintain your Front End pools.</span></span>

<span data-ttu-id="72407-111">Рекомендуется, чтобы все пулы переднего плана Enterprise Edition включали не менее трех серверов переднего плана.</span><span class="sxs-lookup"><span data-stu-id="72407-111">We recommend that all your Enterprise Edition Front End pools include at least three Front End Servers.</span></span> <span data-ttu-id="72407-112">В Lync Server архитектура пулов переднего плана использует модель распределенных систем, при этом данные каждого пользователя хранятся на трех серверах переднего плана в пуле.</span><span class="sxs-lookup"><span data-stu-id="72407-112">In Lync Server, the architecture of Front End pools uses a distributed systems model, with each user’s data kept on three Front End servers in the pool.</span></span> <span data-ttu-id="72407-113">Дополнительные сведения об этой новой архитектуре описаны [в разделе изменения топологии в Lync Server 2013](lync-server-2013-topology-changes.md).</span><span class="sxs-lookup"><span data-stu-id="72407-113">For more information about this new architecture, see [Topology changes in Lync Server 2013](lync-server-2013-topology-changes.md).</span></span>

<span data-ttu-id="72407-114">Если вы не хотите развертывать три сервера переднего плана Enterprise Edition и хотите восстановить работоспособность, мы рекомендуем использовать Lync Server Standard Edition и создать два пула с Объединенным отношением резервного копирования.</span><span class="sxs-lookup"><span data-stu-id="72407-114">If you do not want to deploy three Enterprise Edition Front End Servers and want disaster recovery, we recommend you use Lync Server Standard Edition and create two pools with a paired backup relationship.</span></span> <span data-ttu-id="72407-115">Это позволит устранить проблемы с аварийным восстановлением только двух серверов.</span><span class="sxs-lookup"><span data-stu-id="72407-115">This will provide a disaster recovery solution with only two servers.</span></span> <span data-ttu-id="72407-116">Дополнительные сведения о топологиях и возможностях восстановления с высокой доступностью и аварийным восстановлением содержатся [в разделе Планирование обеспечения высокой доступности и аварийного восстановления в Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span><span class="sxs-lookup"><span data-stu-id="72407-116">For more information, on high availability and disaster recovery topologies and features, see [Planning for high availability and disaster recovery in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span></span>

</div>

<div>

## <a name="planning-for-the-management-of-front-end-pools"></a><span data-ttu-id="72407-117">Планирование управления пулами интерфейсов на стороне сервера</span><span class="sxs-lookup"><span data-stu-id="72407-117">Planning for the Management of Front End Pools</span></span>

<span data-ttu-id="72407-118">Для пулов интерфейсов переднего плана следуйте рекомендациям, приведенным в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="72407-118">For Front End pools, follow the guidelines in this section.</span></span>

<div>

## <a name="ensuring-that-pools-are-functional"></a><span data-ttu-id="72407-119">Обеспечение функциональных возможностей пулов</span><span class="sxs-lookup"><span data-stu-id="72407-119">Ensuring That Pools are Functional</span></span>

<span data-ttu-id="72407-120">При использовании новой распределенной модели для пулов интерфейсов с внешним интерфейсом для функционирования пула необходимо, чтобы были запущены определенные числа серверов пула.</span><span class="sxs-lookup"><span data-stu-id="72407-120">With the new distributed model for Front End pools, certain numbers of a pool’s servers must be running for the pool to function.</span></span> <span data-ttu-id="72407-121">Существует два режима потерь для пула</span><span class="sxs-lookup"><span data-stu-id="72407-121">There are two loss modes for a pool</span></span>

  - <span data-ttu-id="72407-122">Нехватка кворума на уровне группы маршрутизации, что вызвано недостаточным количеством серверов-реплик для определенной группы маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="72407-122">Routing Group Level quorum loss, caused by not enough replica servers for a particular routing group.</span></span> <span data-ttu-id="72407-123">Группа маршрутизации — это совокупность набора пользователей, размещенных в пуле.</span><span class="sxs-lookup"><span data-stu-id="72407-123">A routing group is an aggregation of a set of users homed in the pool.</span></span> <span data-ttu-id="72407-124">У каждой группы маршрутизации есть три реплики в пуле: один первичный и два.</span><span class="sxs-lookup"><span data-stu-id="72407-124">Each routing group has three replicas in the pool: one primary and two secondaries.</span></span>

  - <span data-ttu-id="72407-125">Нехватка кворума на уровне пула, что вызвано недостаточным количеством серверов инициализации в пуле.</span><span class="sxs-lookup"><span data-stu-id="72407-125">Pool Level quorum loss, caused when not enough seed servers are running in the pool.</span></span>

<div>

## <a name="routing-group-level-quorum-loss"></a><span data-ttu-id="72407-126">Нехватка кворума на уровне группы маршрутизации</span><span class="sxs-lookup"><span data-stu-id="72407-126">Routing Group Level quorum loss</span></span>

<span data-ttu-id="72407-p107">При первом запуске нового интерфейсного пула необходимо, чтобы 85% серверов были установлены и запущены, как показано в следующей таблице. Если запущено меньшее количество серверов, службы могут зависнуть в состоянии запуска, а пул может вообще не запуститься.</span><span class="sxs-lookup"><span data-stu-id="72407-p107">The first time you start a new Front End pool, it is essential that 85% of the servers are up and running, as shown in the following table. If fewer servers are running, the services might be stuck in the starting state and the pool might not start.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="72407-129">Общее количество серверов в пуле</span><span class="sxs-lookup"><span data-stu-id="72407-129">Total number of servers in the pool</span></span></th>
<th><span data-ttu-id="72407-130">Количество запущенных серверов, которое требуется для первого запуска пула</span><span class="sxs-lookup"><span data-stu-id="72407-130">Number of servers that must be running for the pool to be started the first time</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="72407-131">2</span><span class="sxs-lookup"><span data-stu-id="72407-131">2</span></span></p></td>
<td><p><span data-ttu-id="72407-132">1</span><span class="sxs-lookup"><span data-stu-id="72407-132">1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="72407-133">3</span><span class="sxs-lookup"><span data-stu-id="72407-133">3</span></span></p></td>
<td><p><span data-ttu-id="72407-134">3</span><span class="sxs-lookup"><span data-stu-id="72407-134">3</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="72407-135">4</span><span class="sxs-lookup"><span data-stu-id="72407-135">4</span></span></p></td>
<td><p><span data-ttu-id="72407-136">3</span><span class="sxs-lookup"><span data-stu-id="72407-136">3</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="72407-137">5</span><span class="sxs-lookup"><span data-stu-id="72407-137">5</span></span></p></td>
<td><p><span data-ttu-id="72407-138">4</span><span class="sxs-lookup"><span data-stu-id="72407-138">4</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="72407-139">6</span><span class="sxs-lookup"><span data-stu-id="72407-139">6</span></span></p></td>
<td><p><span data-ttu-id="72407-140">5</span><span class="sxs-lookup"><span data-stu-id="72407-140">5</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="72407-141">7</span><span class="sxs-lookup"><span data-stu-id="72407-141">7</span></span></p></td>
<td><p><span data-ttu-id="72407-142">5</span><span class="sxs-lookup"><span data-stu-id="72407-142">5</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="72407-143">No8</span><span class="sxs-lookup"><span data-stu-id="72407-143">8</span></span></p></td>
<td><p><span data-ttu-id="72407-144">6</span><span class="sxs-lookup"><span data-stu-id="72407-144">6</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="72407-145">@</span><span class="sxs-lookup"><span data-stu-id="72407-145">9</span></span></p></td>
<td><p><span data-ttu-id="72407-146">7</span><span class="sxs-lookup"><span data-stu-id="72407-146">7</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="72407-147">5-10</span><span class="sxs-lookup"><span data-stu-id="72407-147">10</span></span></p></td>
<td><p><span data-ttu-id="72407-148">No8</span><span class="sxs-lookup"><span data-stu-id="72407-148">8</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="72407-149">11</span><span class="sxs-lookup"><span data-stu-id="72407-149">11</span></span></p></td>
<td><p><span data-ttu-id="72407-150">@</span><span class="sxs-lookup"><span data-stu-id="72407-150">9</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="72407-151">12</span><span class="sxs-lookup"><span data-stu-id="72407-151">12</span></span></p></td>
<td><p><span data-ttu-id="72407-152">5-10</span><span class="sxs-lookup"><span data-stu-id="72407-152">10</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="72407-153">При каждом последующем запуске пула 85% серверов должны быть запущены (как показано на таблице выше).</span><span class="sxs-lookup"><span data-stu-id="72407-153">Every subsequent time the pool is started, 85% of the servers should be started (as shown in the preceding table).</span></span> <span data-ttu-id="72407-154">Если невозможно запустить такое количество серверов (однако можно запустить столько серверов, чтобы избежать нехватки кворума на уровне пула), можно воспользоваться командлетом **Reset-CsPoolRegistrarState –ResetType QuorumLossRecovery** для восстановления пула из нехватки кворума на уровне группы маршрутизации и запуска хода выполнения.</span><span class="sxs-lookup"><span data-stu-id="72407-154">If this number of servers cannot be started (but enough servers can be started so that you are not at pool-level quorum loss), you can use the **Reset-CsPoolRegistrarState –ResetType QuorumLossRecovery** cmdlet to enable the pool to recover from this routing group level quorum loss and make progress.</span></span> <span data-ttu-id="72407-155">Дополнительные сведения о том, как использовать этот командлет, можно найти в разделе [Reset-кспулрегистрарстате](https://docs.microsoft.com/powershell/module/skype/Reset-CsPoolRegistrarState).</span><span class="sxs-lookup"><span data-stu-id="72407-155">For more information about how to use this cmdlet, see [Reset-CsPoolRegistrarState](https://docs.microsoft.com/powershell/module/skype/Reset-CsPoolRegistrarState).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="72407-156">Так как Lync Server использует основную базу данных SQL в качестве следящего сервера, при закрытии базы данных-источника и переходе на зеркальную копию и завершении достаточного количества серверов переднего плана, так как они не работают в соответствии с предыдущей таблицей, весь пул перейдет вниз.</span><span class="sxs-lookup"><span data-stu-id="72407-156">Because Lync Server uses the Primary SQL database as Witness, if you shut down the primary database and switch to the Mirror copy, and shut down enough Front End Servers so that not enough are running according to the preceding table, the entire pool will go down.</span></span> <span data-ttu-id="72407-157">Дополнительные сведения можно найти в разделе <A href="http://go.microsoft.com/fwlink/?linkid=393672">следящий сервер зеркального отображения базы данных</A>.</span><span class="sxs-lookup"><span data-stu-id="72407-157">For more information, see <A href="http://go.microsoft.com/fwlink/?linkid=393672">Database Mirroring Witness</A>.</span></span>



</div>

</div>

<div>

## <a name="pool-level-quorum-loss"></a><span data-ttu-id="72407-158">Нехватка кворума на уровне пула</span><span class="sxs-lookup"><span data-stu-id="72407-158">Pool-level quorum loss</span></span>

<span data-ttu-id="72407-159">Для пула интерфейсов переднего плана не может быть потеря кворума на уровне пула.</span><span class="sxs-lookup"><span data-stu-id="72407-159">For a Front End pool to function at all, it cannot be in pool-level quorum loss.</span></span> <span data-ttu-id="72407-160">Если число запущенных серверов не ниже, как показано в приведенной ниже таблице, оставшиеся серверы в пуле будут остановлены во всех службах Lync Server.</span><span class="sxs-lookup"><span data-stu-id="72407-160">If the number of servers running falls below the functional level as shown in the following table, the remaining servers in the pool will stop all Lync Server services.</span></span> <span data-ttu-id="72407-161">Обратите внимание, что в приведенных ниже таблицах предполагается, что сервер в пуле запущен.</span><span class="sxs-lookup"><span data-stu-id="72407-161">Note that the numbers in the following table assume that the Back End Servers in the pool are running.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="72407-162">Общее количество серверов переднего плана в пуле</span><span class="sxs-lookup"><span data-stu-id="72407-162">Total number of Front End Servers in the pool</span></span></th>
<th><span data-ttu-id="72407-163">Число работающих серверов, требуемое для правильного функционирования пула</span><span class="sxs-lookup"><span data-stu-id="72407-163">Number of servers that must be running for pool to be functional</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="72407-164">2</span><span class="sxs-lookup"><span data-stu-id="72407-164">2</span></span></p></td>
<td><p><span data-ttu-id="72407-165">1</span><span class="sxs-lookup"><span data-stu-id="72407-165">1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="72407-166">3-4</span><span class="sxs-lookup"><span data-stu-id="72407-166">3-4</span></span></p></td>
<td><p><span data-ttu-id="72407-167">Любые 2</span><span class="sxs-lookup"><span data-stu-id="72407-167">Any 2</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="72407-168">5-6</span><span class="sxs-lookup"><span data-stu-id="72407-168">5-6</span></span></p></td>
<td><p><span data-ttu-id="72407-169">Любые 3</span><span class="sxs-lookup"><span data-stu-id="72407-169">Any 3</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="72407-170">7</span><span class="sxs-lookup"><span data-stu-id="72407-170">7</span></span></p></td>
<td><p><span data-ttu-id="72407-171">Любые 4</span><span class="sxs-lookup"><span data-stu-id="72407-171">Any 4</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="72407-172">8-9</span><span class="sxs-lookup"><span data-stu-id="72407-172">8-9</span></span></p></td>
<td><p><span data-ttu-id="72407-173">Любые 4 из первых 7 серверов</span><span class="sxs-lookup"><span data-stu-id="72407-173">Any 4 of the first 7 servers</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="72407-174">10–12</span><span class="sxs-lookup"><span data-stu-id="72407-174">10-12</span></span></p></td>
<td><p><span data-ttu-id="72407-175">Любые 5 из первых 9 серверов</span><span class="sxs-lookup"><span data-stu-id="72407-175">Any 5 of the first 9 servers</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="72407-176">В предыдущей таблице "первые серверы" — это серверы, которые были первыми, в хронологическом порядке, при запуске пула в первый раз.</span><span class="sxs-lookup"><span data-stu-id="72407-176">In the preceding table, the “first servers” are the servers which were brought up first, chronologically, when the pool was started for the first time.</span></span> <span data-ttu-id="72407-177">Чтобы определить эти серверы, можно использовать командлет **Get-кскомпутер** с параметром **– пулфкдн** .</span><span class="sxs-lookup"><span data-stu-id="72407-177">To determine these servers, you can use the **Get-CsComputer** cmdlet with the **–PoolFqdn** option.</span></span> <span data-ttu-id="72407-178">Этот командлет будет показывать серверы в том порядке, в котором они отображаются в топологии, а в верхней части списка — первые серверы.</span><span class="sxs-lookup"><span data-stu-id="72407-178">This cmdlet will show the servers in the order that they appear in the topology, and the ones at the top of the list are the first servers.</span></span>

</div>

<div>

## <a name="front-end-pools-with-two-front-end-servers"></a><span data-ttu-id="72407-179">Пулы интерфейсов с двумя серверами переднего плана</span><span class="sxs-lookup"><span data-stu-id="72407-179">Front End Pools with Two Front End Servers</span></span>

<span data-ttu-id="72407-180">Мы не рекомендуем развертывать пул переднего плана, который включает только два сервера переднего плана.</span><span class="sxs-lookup"><span data-stu-id="72407-180">We do not recommend deploying a Front End pool that contains only two Front End Servers.</span></span> <span data-ttu-id="72407-181">Если вы когда-либо хотите развернуть такой пул, следуйте этим рекомендациям:</span><span class="sxs-lookup"><span data-stu-id="72407-181">If you do ever need to deploy such a pool, follow these guidelines:</span></span>

  - <span data-ttu-id="72407-182">Если один из двух серверов переднего плана отключается, вы должны попытаться выполнить резервное копирование неисправного сервера по мере их появления.</span><span class="sxs-lookup"><span data-stu-id="72407-182">If one of the two Front End Servers goes down, you should try to bring the failed server back up as soon as you can.</span></span> <span data-ttu-id="72407-183">Аналогичным образом, в случае обновления одного из двух серверов его также необходимо вернуть в рабочее состояние как можно быстрее.</span><span class="sxs-lookup"><span data-stu-id="72407-183">Similarly, if you need to upgrade one of the two servers, bring it back online as soon as the upgrade is finished.</span></span>

  - <span data-ttu-id="72407-184">Если по какой-либо причине требуется отключить оба сервера одновременно, после окончания простоя пула выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="72407-184">If for some reason you need to bring both servers down at the same time, do the following when the downtime for the pool is finished:</span></span>
    
      - <span data-ttu-id="72407-185">Рекомендуется перезапускать оба внешних сервера в одно и то же время.</span><span class="sxs-lookup"><span data-stu-id="72407-185">The best practice is to restart both Front End Servers at the same time.</span></span>
    
      - <span data-ttu-id="72407-186">Если это невозможно, следует включать их в порядке, обратном порядку их отключения.</span><span class="sxs-lookup"><span data-stu-id="72407-186">If the two servers cannot be restarted at the same time, you should bring them back up in the reverse order of the order they went down.</span></span>
    
      - <span data-ttu-id="72407-187">Если вы не можете выполнить резервное копирование в указанном порядке, используйте следующий командлет, прежде чем приступить к восстановлению пула:.</span><span class="sxs-lookup"><span data-stu-id="72407-187">If you cannot bring them back up in that order, then use the following cmdlet before bringing the pool back up:.</span></span>
        
            Reset-CsPoolRegistrarState -ResetType QuorumLossRecovery -PoolFQDN <FQDN>

</div>

<div>

## <a name="additional-steps-to-ensure-pools-are-functional"></a><span data-ttu-id="72407-188">Дополнительные действия по обеспечению работоспособности пулов</span><span class="sxs-lookup"><span data-stu-id="72407-188">Additional Steps to Ensure Pools are Functional</span></span>

<span data-ttu-id="72407-189">Для проверки функционирования пулов переднего плана требуется обратить внимание на еще несколько факторов.</span><span class="sxs-lookup"><span data-stu-id="72407-189">You should watch for a couple of other factors to ensure that your Front End pools remain functional.</span></span>

  - <span data-ttu-id="72407-190">При первом перемещении пользователей в пул убедитесь, что запущены по крайней мере три сервера переднего плана.</span><span class="sxs-lookup"><span data-stu-id="72407-190">When you move users to the pool for the first time, be sure at least three of the Front End Servers are running.</span></span>

  - <span data-ttu-id="72407-191">Если вы установили отношение связывания между этим пулом и другим пулом для целей аварийного восстановления, после того как вы установите это отношение, вы должны убедиться, что в этом пуле одновременно работают три сервера переднего плана. данные из пула резервных копий.</span><span class="sxs-lookup"><span data-stu-id="72407-191">If you establish a pairing relationship between this pool and another pool for disaster recovery purposes, then after establishing that relationship you must be sure this pool has three Front End Servers running simultaneously at some time to properly synchronize data with the backup pool.</span></span> <span data-ttu-id="72407-192">Более подробную информацию о функциях связывания и аварийного восстановления пула можно найти [в разделе Планирование обеспечения высокой доступности и аварийного восстановления в Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span><span class="sxs-lookup"><span data-stu-id="72407-192">For more information on pool pairing and disaster recovery features, see [Planning for high availability and disaster recovery in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span></span>

</div>

</div>

<div>

## <a name="improving-the-reliability-of-pool-upgrades"></a><span data-ttu-id="72407-193">Повышение надежности кластерных обновлений</span><span class="sxs-lookup"><span data-stu-id="72407-193">Improving the Reliability of Pool Upgrades</span></span>

<span data-ttu-id="72407-194">Если вам нужно обновить или обновить серверы в пуле переднего плана, выполните действия, указанные в [статье обновление и обновление серверов переднего плана в Lync Server 2013](lync-server-2013-upgrade-or-update-front-end-servers.md), и следующие рекомендации.</span><span class="sxs-lookup"><span data-stu-id="72407-194">When you need to upgrade or patch the servers in a Front End pool, follow the workflow shown in [Upgrade or update Front End Servers in Lync Server 2013](lync-server-2013-upgrade-or-update-front-end-servers.md), and the following guidelines:</span></span>

  - <span data-ttu-id="72407-195">При переходе с одного домена обновления на другой для обновления (после обновления [или обновления серверов переднего плана в Lync Server 2013](lync-server-2013-upgrade-or-update-front-end-servers.md)) вы будете использовать командлет **Get-кспулупградереадинессстате** и проверяйте состояние готовности.</span><span class="sxs-lookup"><span data-stu-id="72407-195">When you move from one upgrade domain to another for upgrades (following the workflow at [Upgrade or update Front End Servers in Lync Server 2013](lync-server-2013-upgrade-or-update-front-end-servers.md)), you will use the **Get-CsPoolUpgradeReadinessState** cmdlet and check for Ready state.</span></span> <span data-ttu-id="72407-196">Добавление в течение 20 минут ожидания между каждым доменом обновления после того, как он достигнет значения "Готово", повышает надежность обновлений.</span><span class="sxs-lookup"><span data-stu-id="72407-196">Adding a 20-minute wait between each upgrade domain after it reaches “Ready” will make the upgrades more reliable.</span></span> <span data-ttu-id="72407-197">Если он **не будет готов** в течение 20 минут, перезапустите 20-минутный таймер.</span><span class="sxs-lookup"><span data-stu-id="72407-197">If it becomes **Not Ready** during this 20 minutes, restart the 20-minute timer.</span></span> <span data-ttu-id="72407-198">Кроме того, вы можете запустить командлет **Get-кспулфабрикстате** до и после 20-минутного интервала времени и убедиться в отсутствии изменений в первичных и логических категориях групп маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="72407-198">Also, you can run the **Get-CsPoolFabricState** cmdlet before and after starting the 20-minute interval and make sure there are no changes to the primaries and secondaries of routing groups.</span></span>

  - <span data-ttu-id="72407-199">Не переходите к следующему домену обновления, если один из серверов в последнем домене обновления задерживается или не перезапускается.</span><span class="sxs-lookup"><span data-stu-id="72407-199">Do not move on to the next upgrade domain if any of the servers in the last patched upgrade domain are stuck or not restarted.</span></span> <span data-ttu-id="72407-200">Это также применимо, если не удается запустить какой – либо сервер, на котором находится обновление.</span><span class="sxs-lookup"><span data-stu-id="72407-200">This also applies if any of the servers within an upgrade cannot start.</span></span> <span data-ttu-id="72407-201">Запустите **Get-кспулфабрикстате** , чтобы убедиться, что у всех групп маршрутизации есть основной и хотя бы один вспомогательный. Это подтвердит, есть ли у всех пользователей обслуживание.</span><span class="sxs-lookup"><span data-stu-id="72407-201">Run **Get-CsPoolFabricState** to make sure all of the routing groups have a primary and at least one secondary; this will confirm whether all users have service.</span></span>

  - <span data-ttu-id="72407-202">Если у некоторых пользователей есть служба и другие пользователи, запустите **Get-кспулфабрикстате** с параметром – verbose для поиска групп маршрутизации с отсутствующими репликами.</span><span class="sxs-lookup"><span data-stu-id="72407-202">If some users have service and others do not, run **Get-CsPoolFabricState** with the –Verbose option to check for routing groups that have missing replicas.</span></span> <span data-ttu-id="72407-203">Не перезапускайте весь пул как первый шаг для устранения неполадок.</span><span class="sxs-lookup"><span data-stu-id="72407-203">Do not restart the entire pool as the first troubleshooting step.</span></span> <span data-ttu-id="72407-204">Дополнительные сведения об этом командлете можно найти в [статьях Get-кспулфабрикстате](https://docs.microsoft.com/powershell/module/skype/Get-CsPoolFabricState).</span><span class="sxs-lookup"><span data-stu-id="72407-204">For more information on this cmdlet, see [Get-CsPoolFabricState](https://docs.microsoft.com/powershell/module/skype/Get-CsPoolFabricState).</span></span>

  - <span data-ttu-id="72407-205">Убедитесь, что все экземпляры окна просмотра событий или системного монитора закрыты для Windows Fabric (устанавливается или удаляет).</span><span class="sxs-lookup"><span data-stu-id="72407-205">Make sure that all instances of the Event Viewer or Performance Monitor windows are closed for windows fabric installs/uninstalls.</span></span>

</div>

<div>

## <a name="changing-a-front-end-pools-configuration"></a><span data-ttu-id="72407-206">Изменение конфигурации пула переднего плана</span><span class="sxs-lookup"><span data-stu-id="72407-206">Changing a Front End Pool’s Configuration</span></span>

<span data-ttu-id="72407-207">Каждый раз, когда вы добавляете серверы переднего плана в пул или удаляете их из пула, а затем публикуете новую топологию, следуйте этим рекомендациям:</span><span class="sxs-lookup"><span data-stu-id="72407-207">Whenever you add Front End Servers to a pool, or remove them from the pool, and then publish the new topology, follow these guidelines:</span></span>

  - <span data-ttu-id="72407-208">После публикации новой топологии необходимо перезапустить каждый сервер переднего плана в пуле.</span><span class="sxs-lookup"><span data-stu-id="72407-208">After the new topology has been published, you must restart each Front End Server in the pool.</span></span> <span data-ttu-id="72407-209">Перезапускайте их по одному.</span><span class="sxs-lookup"><span data-stu-id="72407-209">Restart them one at a time.</span></span>

  - <span data-ttu-id="72407-210">Если во время изменения конфигурации весь пул был остановлен, после публикации новой топологии запустите следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="72407-210">If the entire pool has been down during the configuration change, then run the following cmdlet after the new topology is published:</span></span>
    
        Reset-CsPoolRegistrarState -PoolFQDN <PoolFQDN> -ResetType ServiceReset

<span data-ttu-id="72407-211">Если сервер переднего плана завершается сбоем и вряд ли будет заменен на несколько дней или больше, удалите сервер из топологии.</span><span class="sxs-lookup"><span data-stu-id="72407-211">If a Front End Server fails and is unlikely to be replaced for a few days or more, remove the server from the topology.</span></span> <span data-ttu-id="72407-212">Добавьте новый сервер переднего плана в топологию, когда он снова станет доступен.</span><span class="sxs-lookup"><span data-stu-id="72407-212">Add the new Front End Server to the topology when it is available again.</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

