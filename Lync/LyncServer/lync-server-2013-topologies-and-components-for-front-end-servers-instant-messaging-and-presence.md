---
title: 'Lync Server 2013: топологии и компоненты для серверов переднего плана, обмена мгновенными сообщениями и сведений о присутствии'
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
ms.openlocfilehash: 103d03920df57023ae7dbb953beb0c426d0a43df
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48503756"
---
# <a name="topologies-and-components-for-front-end-servers-instant-messaging-and-presence-in-lync-server-2013"></a><span data-ttu-id="d5007-102">Топологии и компоненты для серверов переднего плана, обмена мгновенными сообщениями и сведений о присутствии в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d5007-102">Topologies and components for Front End Servers, instant messaging, and presence in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d5007-103">_**Последнее изменение темы:** 2014-10-24_</span><span class="sxs-lookup"><span data-stu-id="d5007-103">_**Topic Last Modified:** 2014-10-24_</span></span>

<span data-ttu-id="d5007-104">Для обмена мгновенными сообщениями и сведениями о присутствии требуются только следующие компоненты:</span><span class="sxs-lookup"><span data-stu-id="d5007-104">The only components required for instant messaging (IM) and presence are:</span></span>

  - <span data-ttu-id="d5007-p101">Серверы переднего плана организации или серверы Standard Edition. Функции обмена мгновенными сообщениями и сведениями о присутствии всегда включены на этих серверах.</span><span class="sxs-lookup"><span data-stu-id="d5007-p101">Your organization’s Front End Servers or Standard Edition servers. IM and presence capabilities are always enabled on these servers.</span></span>

  - <span data-ttu-id="d5007-107">Подсистема балансировки нагрузки (при наличии пула переднего плана Enterprise Edition).</span><span class="sxs-lookup"><span data-stu-id="d5007-107">A load balancer, if you have an Enterprise Edition Front End pool.</span></span> <span data-ttu-id="d5007-108">Для получения дополнительных сведений см в разделе [требования к балансировке нагрузки для Lync Server 2013](lync-server-2013-load-balancing-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d5007-108">For more information, see [Load balancing requirements for Lync Server 2013](lync-server-2013-load-balancing-requirements.md).</span></span>

<div>

## <a name="planning-for-the-deployment-of-front-end-pools"></a><span data-ttu-id="d5007-109">Планирование развертывания интерфейсных пулов</span><span class="sxs-lookup"><span data-stu-id="d5007-109">Planning for the Deployment of Front End Pools</span></span>

<span data-ttu-id="d5007-110">В Lync Server 2013 архитектура пула переднего плана изменилась, и эти изменения влияют на планирование и обслуживание интерфейсных пулов.</span><span class="sxs-lookup"><span data-stu-id="d5007-110">In Lync Server 2013, Front End pool architecture has changed, and these changes affect how you should plan and maintain your Front End pools.</span></span>

<span data-ttu-id="d5007-111">Для всех интерфейсных пулов Enterprise Edition рекомендуется включить по крайней мере три сервера переднего плана.</span><span class="sxs-lookup"><span data-stu-id="d5007-111">We recommend that all your Enterprise Edition Front End pools include at least three Front End Servers.</span></span> <span data-ttu-id="d5007-112">В Lync Server архитектура интерфейсных пулов использует модель распределенных систем, в которой данные каждого пользователя хранятся на трех серверах переднего плана в пуле.</span><span class="sxs-lookup"><span data-stu-id="d5007-112">In Lync Server, the architecture of Front End pools uses a distributed systems model, with each user’s data kept on three Front End servers in the pool.</span></span> <span data-ttu-id="d5007-113">Дополнительные сведения об этой новой архитектуре приведены [в статье изменения топологии в Lync Server 2013](lync-server-2013-topology-changes.md).</span><span class="sxs-lookup"><span data-stu-id="d5007-113">For more information about this new architecture, see [Topology changes in Lync Server 2013](lync-server-2013-topology-changes.md).</span></span>

<span data-ttu-id="d5007-114">Если вы не хотите развертывать три сервера переднего плана Enterprise Edition и вы хотите аварийное восстановление, рекомендуем использовать Lync Server Standard Edition и создать два пула со связанным отношением резервного копирования.</span><span class="sxs-lookup"><span data-stu-id="d5007-114">If you do not want to deploy three Enterprise Edition Front End Servers and want disaster recovery, we recommend you use Lync Server Standard Edition and create two pools with a paired backup relationship.</span></span> <span data-ttu-id="d5007-115">При этом будет предоставлено решение аварийного восстановления с двумя серверами.</span><span class="sxs-lookup"><span data-stu-id="d5007-115">This will provide a disaster recovery solution with only two servers.</span></span> <span data-ttu-id="d5007-116">Дополнительные сведения о топологиях и возможностях высокого уровня доступности и аварийного восстановления приведены [в статье Планирование обеспечения высокой доступности и аварийного восстановления в Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span><span class="sxs-lookup"><span data-stu-id="d5007-116">For more information, on high availability and disaster recovery topologies and features, see [Planning for high availability and disaster recovery in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span></span>

</div>

<div>

## <a name="planning-for-the-management-of-front-end-pools"></a><span data-ttu-id="d5007-117">Планирование управления интерфейсными пулами</span><span class="sxs-lookup"><span data-stu-id="d5007-117">Planning for the Management of Front End Pools</span></span>

<span data-ttu-id="d5007-118">Для интерфейсных пулов следуйте указаниям, приведенным в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="d5007-118">For Front End pools, follow the guidelines in this section.</span></span>

<div>

## <a name="ensuring-that-pools-are-functional"></a><span data-ttu-id="d5007-119">Обеспечение работоспособности пулов</span><span class="sxs-lookup"><span data-stu-id="d5007-119">Ensuring That Pools are Functional</span></span>

<span data-ttu-id="d5007-120">При использовании новой распределенной модели для пулов переднего плана необходимо, чтобы пул работал с определенными номерами серверов пула.</span><span class="sxs-lookup"><span data-stu-id="d5007-120">With the new distributed model for Front End pools, certain numbers of a pool’s servers must be running for the pool to function.</span></span> <span data-ttu-id="d5007-121">Существует два режима потерь для пула</span><span class="sxs-lookup"><span data-stu-id="d5007-121">There are two loss modes for a pool</span></span>

  - <span data-ttu-id="d5007-122">Потеря кворума на уровне группы маршрутизации, вызванная недостаточной репликой серверов для определенной группы маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="d5007-122">Routing Group Level quorum loss, caused by not enough replica servers for a particular routing group.</span></span> <span data-ttu-id="d5007-123">Группа маршрутизации является объединением набора пользователей, размещенных в пуле.</span><span class="sxs-lookup"><span data-stu-id="d5007-123">A routing group is an aggregation of a set of users homed in the pool.</span></span> <span data-ttu-id="d5007-124">Каждая группа маршрутизации состоит из трех реплик в пуле: одного основного и двух получателей.</span><span class="sxs-lookup"><span data-stu-id="d5007-124">Each routing group has three replicas in the pool: one primary and two secondaries.</span></span>

  - <span data-ttu-id="d5007-125">Потеря кворума на уровне пула, вызванная тем, что в пуле не работает достаточное количество серверов инициализации.</span><span class="sxs-lookup"><span data-stu-id="d5007-125">Pool Level quorum loss, caused when not enough seed servers are running in the pool.</span></span>

<div>

## <a name="routing-group-level-quorum-loss"></a><span data-ttu-id="d5007-126">Потеря кворума на уровне группы маршрутизации</span><span class="sxs-lookup"><span data-stu-id="d5007-126">Routing Group Level quorum loss</span></span>

<span data-ttu-id="d5007-127">При первом запуске нового пула переднего плана необходимо, чтобы 85% серверов были запущены и запущены, как показано в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="d5007-127">The first time you start a new Front End pool, it is essential that 85% of the servers are up and running, as shown in the following table.</span></span> <span data-ttu-id="d5007-128">Если запущено меньшее количество серверов, службы могут оставаться в состоянии запуска, а пул может не запуститься.</span><span class="sxs-lookup"><span data-stu-id="d5007-128">If fewer servers are running, the services might be stuck in the starting state and the pool might not start.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d5007-129">Общее количество серверов в пуле</span><span class="sxs-lookup"><span data-stu-id="d5007-129">Total number of servers in the pool</span></span></th>
<th><span data-ttu-id="d5007-130">Количество серверов, которые должны быть запущены в первый раз при первом запуске пула</span><span class="sxs-lookup"><span data-stu-id="d5007-130">Number of servers that must be running for the pool to be started the first time</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d5007-131">2</span><span class="sxs-lookup"><span data-stu-id="d5007-131">2</span></span></p></td>
<td><p><span data-ttu-id="d5007-132">1,1</span><span class="sxs-lookup"><span data-stu-id="d5007-132">1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d5007-133">4</span><span class="sxs-lookup"><span data-stu-id="d5007-133">3</span></span></p></td>
<td><p><span data-ttu-id="d5007-134">4</span><span class="sxs-lookup"><span data-stu-id="d5007-134">3</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d5007-135">4 </span><span class="sxs-lookup"><span data-stu-id="d5007-135">4</span></span></p></td>
<td><p><span data-ttu-id="d5007-136">4</span><span class="sxs-lookup"><span data-stu-id="d5007-136">3</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d5007-137">5 </span><span class="sxs-lookup"><span data-stu-id="d5007-137">5</span></span></p></td>
<td><p><span data-ttu-id="d5007-138">4 </span><span class="sxs-lookup"><span data-stu-id="d5007-138">4</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d5007-139">6 </span><span class="sxs-lookup"><span data-stu-id="d5007-139">6</span></span></p></td>
<td><p><span data-ttu-id="d5007-140">5 </span><span class="sxs-lookup"><span data-stu-id="d5007-140">5</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d5007-141">7 </span><span class="sxs-lookup"><span data-stu-id="d5007-141">7</span></span></p></td>
<td><p><span data-ttu-id="d5007-142">5 </span><span class="sxs-lookup"><span data-stu-id="d5007-142">5</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d5007-143">8 </span><span class="sxs-lookup"><span data-stu-id="d5007-143">8</span></span></p></td>
<td><p><span data-ttu-id="d5007-144">6 </span><span class="sxs-lookup"><span data-stu-id="d5007-144">6</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d5007-145">9 </span><span class="sxs-lookup"><span data-stu-id="d5007-145">9</span></span></p></td>
<td><p><span data-ttu-id="d5007-146">7 </span><span class="sxs-lookup"><span data-stu-id="d5007-146">7</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d5007-147">10 </span><span class="sxs-lookup"><span data-stu-id="d5007-147">10</span></span></p></td>
<td><p><span data-ttu-id="d5007-148">8 </span><span class="sxs-lookup"><span data-stu-id="d5007-148">8</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d5007-149">-11:00</span><span class="sxs-lookup"><span data-stu-id="d5007-149">11</span></span></p></td>
<td><p><span data-ttu-id="d5007-150">9 </span><span class="sxs-lookup"><span data-stu-id="d5007-150">9</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d5007-151">12 </span><span class="sxs-lookup"><span data-stu-id="d5007-151">12</span></span></p></td>
<td><p><span data-ttu-id="d5007-152">10 </span><span class="sxs-lookup"><span data-stu-id="d5007-152">10</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="d5007-153">При каждом последующем запуске пула будет запущено 85% серверов (как показано в предыдущей таблице).</span><span class="sxs-lookup"><span data-stu-id="d5007-153">Every subsequent time the pool is started, 85% of the servers should be started (as shown in the preceding table).</span></span> <span data-ttu-id="d5007-154">Если это количество серверов не может быть запущено (но можно запустить достаточное количество серверов, чтобы их можно было отключить из-за потери кворума на уровне пула), можно использовать командлет **Reset-кспулрегистрарстате – ResetType куорумлоссрековери** , чтобы пул мог восстанавливаться после потери кворума на уровне группы маршрутизации и для выполнения.</span><span class="sxs-lookup"><span data-stu-id="d5007-154">If this number of servers cannot be started (but enough servers can be started so that you are not at pool-level quorum loss), you can use the **Reset-CsPoolRegistrarState –ResetType QuorumLossRecovery** cmdlet to enable the pool to recover from this routing group level quorum loss and make progress.</span></span> <span data-ttu-id="d5007-155">Дополнительные сведения о том, как использовать этот командлет, можно найти в статье [Reset/кспулрегистрарстате](https://docs.microsoft.com/powershell/module/skype/Reset-CsPoolRegistrarState).</span><span class="sxs-lookup"><span data-stu-id="d5007-155">For more information about how to use this cmdlet, see [Reset-CsPoolRegistrarState](https://docs.microsoft.com/powershell/module/skype/Reset-CsPoolRegistrarState).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d5007-156">Так как Lync Server использует основную базу данных SQL в качестве следящего сервера, то при завершении работы базы данных-источника и перепереходе на зеркальную копию и завершении работы достаточного количества серверов переднего плана, чтобы они не выполнялись в соответствии с предыдущей таблицей, весь пул перейдет.</span><span class="sxs-lookup"><span data-stu-id="d5007-156">Because Lync Server uses the Primary SQL database as Witness, if you shut down the primary database and switch to the Mirror copy, and shut down enough Front End Servers so that not enough are running according to the preceding table, the entire pool will go down.</span></span> <span data-ttu-id="d5007-157">Дополнительные сведения можно найти в разделе <A href="https://go.microsoft.com/fwlink/?linkid=393672">следящий сервер зеркального отображения баз данных</A>.</span><span class="sxs-lookup"><span data-stu-id="d5007-157">For more information, see <A href="https://go.microsoft.com/fwlink/?linkid=393672">Database Mirroring Witness</A>.</span></span>



</div>

</div>

<div>

## <a name="pool-level-quorum-loss"></a><span data-ttu-id="d5007-158">Потеря кворума на уровне пула</span><span class="sxs-lookup"><span data-stu-id="d5007-158">Pool-level quorum loss</span></span>

<span data-ttu-id="d5007-159">Для того, чтобы интерфейсный пул функционировал вообще, он не может находиться в потерях кворума на уровне пула.</span><span class="sxs-lookup"><span data-stu-id="d5007-159">For a Front End pool to function at all, it cannot be in pool-level quorum loss.</span></span> <span data-ttu-id="d5007-160">Если количество серверов, на которых работает уровень ниже режима работы, показано в следующей таблице, остальные серверы в пуле будут останавливать все службы Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d5007-160">If the number of servers running falls below the functional level as shown in the following table, the remaining servers in the pool will stop all Lync Server services.</span></span> <span data-ttu-id="d5007-161">Обратите внимание, что в приведенных ниже таблицах предполагается, что серверы переднего планов в пуле работают.</span><span class="sxs-lookup"><span data-stu-id="d5007-161">Note that the numbers in the following table assume that the Back End Servers in the pool are running.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d5007-162">Общее число серверов переднего плана в пуле</span><span class="sxs-lookup"><span data-stu-id="d5007-162">Total number of Front End Servers in the pool</span></span></th>
<th><span data-ttu-id="d5007-163">Число работающих серверов, требуемое для правильного функционирования пула</span><span class="sxs-lookup"><span data-stu-id="d5007-163">Number of servers that must be running for pool to be functional</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d5007-164">2</span><span class="sxs-lookup"><span data-stu-id="d5007-164">2</span></span></p></td>
<td><p><span data-ttu-id="d5007-165">1,1</span><span class="sxs-lookup"><span data-stu-id="d5007-165">1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d5007-166">3-4</span><span class="sxs-lookup"><span data-stu-id="d5007-166">3-4</span></span></p></td>
<td><p><span data-ttu-id="d5007-167">Любой 2</span><span class="sxs-lookup"><span data-stu-id="d5007-167">Any 2</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d5007-168">5-6</span><span class="sxs-lookup"><span data-stu-id="d5007-168">5-6</span></span></p></td>
<td><p><span data-ttu-id="d5007-169">Любое 3</span><span class="sxs-lookup"><span data-stu-id="d5007-169">Any 3</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d5007-170">7 </span><span class="sxs-lookup"><span data-stu-id="d5007-170">7</span></span></p></td>
<td><p><span data-ttu-id="d5007-171">Любой 4</span><span class="sxs-lookup"><span data-stu-id="d5007-171">Any 4</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d5007-172">8-9</span><span class="sxs-lookup"><span data-stu-id="d5007-172">8-9</span></span></p></td>
<td><p><span data-ttu-id="d5007-173">4 первых 7 серверов</span><span class="sxs-lookup"><span data-stu-id="d5007-173">Any 4 of the first 7 servers</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d5007-174">10-12</span><span class="sxs-lookup"><span data-stu-id="d5007-174">10-12</span></span></p></td>
<td><p><span data-ttu-id="d5007-175">5 первых девяти серверов</span><span class="sxs-lookup"><span data-stu-id="d5007-175">Any 5 of the first 9 servers</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="d5007-176">В приведенной выше таблице первыми серверами являются серверы, которые были первыми, в хронологическом порядке, когда пул был запущен в первый раз.</span><span class="sxs-lookup"><span data-stu-id="d5007-176">In the preceding table, the “first servers” are the servers which were brought up first, chronologically, when the pool was started for the first time.</span></span> <span data-ttu-id="d5007-177">Для определения этих серверов можно использовать командлет **Get-CsComputer** с параметром **– PoolFqdn** .</span><span class="sxs-lookup"><span data-stu-id="d5007-177">To determine these servers, you can use the **Get-CsComputer** cmdlet with the **–PoolFqdn** option.</span></span> <span data-ttu-id="d5007-178">Этот командлет покажет серверы в том порядке, в котором они отображаются в топологии, а в верхней части списка находятся первые серверы.</span><span class="sxs-lookup"><span data-stu-id="d5007-178">This cmdlet will show the servers in the order that they appear in the topology, and the ones at the top of the list are the first servers.</span></span>

</div>

<div>

## <a name="front-end-pools-with-two-front-end-servers"></a><span data-ttu-id="d5007-179">Интерфейсные пулы с двумя серверами переднего плана</span><span class="sxs-lookup"><span data-stu-id="d5007-179">Front End Pools with Two Front End Servers</span></span>

<span data-ttu-id="d5007-p112">Мы не рекомендуем развертывать интерфейсный пул, содержащий всего два сервера переднего плана. Если вам все же потребуется развернуть такой пул, следуйте приведенным ниже рекомендациям:</span><span class="sxs-lookup"><span data-stu-id="d5007-p112">We do not recommend deploying a Front End pool that contains only two Front End Servers. If you do ever need to deploy such a pool, follow these guidelines:</span></span>

  - <span data-ttu-id="d5007-p113">В случае сбоя одного из двух этих серверов переднего плана вам следует как можно быстрее восстановить его работоспособность. Аналогичным образом, в случае обновления одного из двух серверов его также необходимо вернуть в рабочее состояние как можно быстрее.</span><span class="sxs-lookup"><span data-stu-id="d5007-p113">If one of the two Front End Servers goes down, you should try to bring the failed server back up as soon as you can. Similarly, if you need to upgrade one of the two servers, bring it back online as soon as the upgrade is finished.</span></span>

  - <span data-ttu-id="d5007-184">Если по какой-либо причине требуется отключить оба сервера одновременно, после окончания простоя пула выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="d5007-184">If for some reason you need to bring both servers down at the same time, do the following when the downtime for the pool is finished:</span></span>
    
      - <span data-ttu-id="d5007-185">Рекомендуется перезапустить оба сервера переднего плана одновременно.</span><span class="sxs-lookup"><span data-stu-id="d5007-185">The best practice is to restart both Front End Servers at the same time.</span></span>
    
      - <span data-ttu-id="d5007-186">Если это невозможно, следует включать их в порядке, обратном порядку их отключения.</span><span class="sxs-lookup"><span data-stu-id="d5007-186">If the two servers cannot be restarted at the same time, you should bring them back up in the reverse order of the order they went down.</span></span>
    
      - <span data-ttu-id="d5007-187">Если и это невозможно, перед включением пула выполните следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="d5007-187">If you cannot bring them back up in that order, then use the following cmdlet before bringing the pool back up:.</span></span>
        
            Reset-CsPoolRegistrarState -ResetType QuorumLossRecovery -PoolFQDN <FQDN>

</div>

<div>

## <a name="additional-steps-to-ensure-pools-are-functional"></a><span data-ttu-id="d5007-188">Дополнительные действия для обеспечения работоспособности пулов</span><span class="sxs-lookup"><span data-stu-id="d5007-188">Additional Steps to Ensure Pools are Functional</span></span>

<span data-ttu-id="d5007-189">Необходимо проследить за несколько других факторов, чтобы обеспечить работоспособность пулов переднего плана.</span><span class="sxs-lookup"><span data-stu-id="d5007-189">You should watch for a couple of other factors to ensure that your Front End pools remain functional.</span></span>

  - <span data-ttu-id="d5007-190">При первом перемещении пользователей в пул обязательно убедитесь, что запущено не менее трех серверов переднего плана.</span><span class="sxs-lookup"><span data-stu-id="d5007-190">When you move users to the pool for the first time, be sure at least three of the Front End Servers are running.</span></span>

  - <span data-ttu-id="d5007-191">Если вы устанавливаете отношение связывания между данным пулом и другим пулом в целях обеспечения аварийного восстановления, по после этого вам следует убедиться, что данный пул имеет три одновременно работающих сервера переднего плана для правильной синхронизации данных с резервным пулом.</span><span class="sxs-lookup"><span data-stu-id="d5007-191">If you establish a pairing relationship between this pool and another pool for disaster recovery purposes, then after establishing that relationship you must be sure this pool has three Front End Servers running simultaneously at some time to properly synchronize data with the backup pool.</span></span> <span data-ttu-id="d5007-192">Дополнительные сведения о функциях связывания и аварийного восстановления пула приведены [в статье Планирование обеспечения высокой доступности и аварийного восстановления в Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span><span class="sxs-lookup"><span data-stu-id="d5007-192">For more information on pool pairing and disaster recovery features, see [Planning for high availability and disaster recovery in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span></span>

</div>

</div>

<div>

## <a name="improving-the-reliability-of-pool-upgrades"></a><span data-ttu-id="d5007-193">Повышение надежности пула обновлений</span><span class="sxs-lookup"><span data-stu-id="d5007-193">Improving the Reliability of Pool Upgrades</span></span>

<span data-ttu-id="d5007-194">Если вам нужно обновить или исправить серверы в пуле переднего плана, выполните рабочий процесс, показанный на странице [обновление или обновление серверов переднего плана в Lync Server 2013](lync-server-2013-upgrade-or-update-front-end-servers.md), и следующие рекомендации:</span><span class="sxs-lookup"><span data-stu-id="d5007-194">When you need to upgrade or patch the servers in a Front End pool, follow the workflow shown in [Upgrade or update Front End Servers in Lync Server 2013](lync-server-2013-upgrade-or-update-front-end-servers.md), and the following guidelines:</span></span>

  - <span data-ttu-id="d5007-195">При переходе с одного домена обновления на другой для обновлений (на основе рабочего процесса при [обновлении или обновлении серверов переднего плана в Lync Server 2013](lync-server-2013-upgrade-or-update-front-end-servers.md)) используется командлет **Get-CsPoolUpgradeReadinessState** и выполняется проверка состояния готовности.</span><span class="sxs-lookup"><span data-stu-id="d5007-195">When you move from one upgrade domain to another for upgrades (following the workflow at [Upgrade or update Front End Servers in Lync Server 2013](lync-server-2013-upgrade-or-update-front-end-servers.md)), you will use the **Get-CsPoolUpgradeReadinessState** cmdlet and check for Ready state.</span></span> <span data-ttu-id="d5007-196">Добавление 20 минут ожидания между каждым доменом обновления после того, как он достигнет "Готово", сделает обновление более надежным.</span><span class="sxs-lookup"><span data-stu-id="d5007-196">Adding a 20-minute wait between each upgrade domain after it reaches “Ready” will make the upgrades more reliable.</span></span> <span data-ttu-id="d5007-197">Если он **не будет готов** в течение этого 20 минут, перезапустите таймер 20 минут.</span><span class="sxs-lookup"><span data-stu-id="d5007-197">If it becomes **Not Ready** during this 20 minutes, restart the 20-minute timer.</span></span> <span data-ttu-id="d5007-198">Кроме того, вы можете выполнить командлет **Get – CsPoolFabricState** до и после начала 20 минут и убедиться в отсутствии изменений в первичных и резервных копиях групп маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="d5007-198">Also, you can run the **Get-CsPoolFabricState** cmdlet before and after starting the 20-minute interval and make sure there are no changes to the primaries and secondaries of routing groups.</span></span>

  - <span data-ttu-id="d5007-199">Не переходите к следующему домену обновления, если один из серверов в последнем домене обновления был задержан или не перезапускается.</span><span class="sxs-lookup"><span data-stu-id="d5007-199">Do not move on to the next upgrade domain if any of the servers in the last patched upgrade domain are stuck or not restarted.</span></span> <span data-ttu-id="d5007-200">Это также применимо, если не удается запустить ни один из серверов, входящих в обновление.</span><span class="sxs-lookup"><span data-stu-id="d5007-200">This also applies if any of the servers within an upgrade cannot start.</span></span> <span data-ttu-id="d5007-201">Выполните командлет **Get – CsPoolFabricState** , чтобы убедиться в том, что все группы маршрутизации имеют основной и по крайней мере один вторичный; будет подтверждено, имеет ли все пользователи обслуживание.</span><span class="sxs-lookup"><span data-stu-id="d5007-201">Run **Get-CsPoolFabricState** to make sure all of the routing groups have a primary and at least one secondary; this will confirm whether all users have service.</span></span>

  - <span data-ttu-id="d5007-202">Если некоторые пользователи имеют службы, а другие — нет, выполните командлет **Get-CsPoolFabricState** с параметром – verbose, чтобы проверить наличие групп маршрутизации, в которых отсутствуют реплики.</span><span class="sxs-lookup"><span data-stu-id="d5007-202">If some users have service and others do not, run **Get-CsPoolFabricState** with the –Verbose option to check for routing groups that have missing replicas.</span></span> <span data-ttu-id="d5007-203">Не перезапускайте весь пул в качестве первого этапа устранения неполадок.</span><span class="sxs-lookup"><span data-stu-id="d5007-203">Do not restart the entire pool as the first troubleshooting step.</span></span> <span data-ttu-id="d5007-204">Для получения дополнительных сведений об этом командлете обратитесь к разделу [Get – CsPoolFabricState](https://docs.microsoft.com/powershell/module/skype/Get-CsPoolFabricState).</span><span class="sxs-lookup"><span data-stu-id="d5007-204">For more information on this cmdlet, see [Get-CsPoolFabricState](https://docs.microsoft.com/powershell/module/skype/Get-CsPoolFabricState).</span></span>

  - <span data-ttu-id="d5007-205">Убедитесь, что все экземпляры окон "Просмотр событий" и "системный монитор" закрыты для установки и удаления Windows Fabric.</span><span class="sxs-lookup"><span data-stu-id="d5007-205">Make sure that all instances of the Event Viewer or Performance Monitor windows are closed for windows fabric installs/uninstalls.</span></span>

</div>

<div>

## <a name="changing-a-front-end-pools-configuration"></a><span data-ttu-id="d5007-206">Изменение конфигурации интерфейсного пула</span><span class="sxs-lookup"><span data-stu-id="d5007-206">Changing a Front End Pool’s Configuration</span></span>

<span data-ttu-id="d5007-207">При добавлении серверов переднего плана в пул, их удалении из пула и публикации новой топологии следуйте приведенным ниже рекомендациям:</span><span class="sxs-lookup"><span data-stu-id="d5007-207">Whenever you add Front End Servers to a pool, or remove them from the pool, and then publish the new topology, follow these guidelines:</span></span>

  - <span data-ttu-id="d5007-208">После публикации новой топологии необходимо перезапустить все серверы переднего плана в пуле.</span><span class="sxs-lookup"><span data-stu-id="d5007-208">After the new topology has been published, you must restart each Front End Server in the pool.</span></span> <span data-ttu-id="d5007-209">Перезапускайте их по одному.</span><span class="sxs-lookup"><span data-stu-id="d5007-209">Restart them one at a time.</span></span>

  - <span data-ttu-id="d5007-210">Если во время изменения конфигурации был отключен весь пул, после публикации новой топологии запустите следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="d5007-210">If the entire pool has been down during the configuration change, then run the following cmdlet after the new topology is published:</span></span>
    
        Reset-CsPoolRegistrarState -PoolFQDN <PoolFQDN> -ResetType ServiceReset

<span data-ttu-id="d5007-p119">Если сервер переднего плана ломается и вряд ли будет заменен только через несколько дней или позднее, удалите этот сервер из топологии. Когда новый сервер переднего плана вновь станет доступен, добавьте его в топологию.</span><span class="sxs-lookup"><span data-stu-id="d5007-p119">If a Front End Server fails and is unlikely to be replaced for a few days or more, remove the server from the topology. Add the new Front End Server to the topology when it is available again.</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

