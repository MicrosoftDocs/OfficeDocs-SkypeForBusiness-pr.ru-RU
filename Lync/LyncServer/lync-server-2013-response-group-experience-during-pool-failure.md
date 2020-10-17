---
title: Lync Server 2013 взаимодействие с группой ответа при отказе пула
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Response group experience during pool failure
ms:assetid: 4e00fb38-64b1-4fd9-903d-7639177bc303
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204886(v=OCS.15)
ms:contentKeyID: 48184116
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 684d33219bb6146a0c5dc85894c060affd6745a2
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48511646"
---
# <a name="response-group-experience-in-lync-server-2013-during-pool-failure"></a><span data-ttu-id="57af3-102">Взаимодействие группы ответа в Lync Server 2013 во время сбоя пула</span><span class="sxs-lookup"><span data-stu-id="57af3-102">Response group experience in Lync Server 2013 during pool failure</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="57af3-103">_**Последнее изменение темы:** 2012-10-30_</span><span class="sxs-lookup"><span data-stu-id="57af3-103">_**Topic Last Modified:** 2012-10-30_</span></span>

<span data-ttu-id="57af3-104">В этом разделе подробно описывается, какое влияние оказывается на деятельность группы ответа на следующих этапах:</span><span class="sxs-lookup"><span data-stu-id="57af3-104">This section describes in detail how response group activity is affected in the following stages:</span></span>

  - <span data-ttu-id="57af3-105">В основном пуле происходит сбой, однако отработка отказа еще не активирована.</span><span class="sxs-lookup"><span data-stu-id="57af3-105">An outage occurs in the primary pool, but failover is not yet initiated.</span></span>

  - <span data-ttu-id="57af3-106">Выполняется отработка отказа для службы в резервный пул.</span><span class="sxs-lookup"><span data-stu-id="57af3-106">Service is failed over to the backup pool.</span></span>

  - <span data-ttu-id="57af3-107">Выполняется восстановление размещения для службы в основной пул.</span><span class="sxs-lookup"><span data-stu-id="57af3-107">Service is failed back to the primary pool.</span></span>

<div>

## <a name="user-experience-when-outage-occurs"></a><span data-ttu-id="57af3-108">Взаимодействие с пользователем при возникновении сбоя</span><span class="sxs-lookup"><span data-stu-id="57af3-108">User Experience When Outage Occurs</span></span>

<span data-ttu-id="57af3-109">Если возник сбой пула или сайта, а администратор еще не активировал отработку отказа, обработка деятельности группы ответа осуществляется в соответствии со следующей таблицей.</span><span class="sxs-lookup"><span data-stu-id="57af3-109">When a pool or site outage occurs, but the administrator has not yet initiated failover, response group activity is handled as described in the following table.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="57af3-p101">Во время аварийного восстановления звонки реализуются иначе в зависимости от того, были ли группы ответа основного пула импортированы в резервный пул вор время восстановления. В следующей таблице ссылки на импортированные группы ответа означают, что в режиме аварийного восстановления группы ответа основного пула были  импортированы в резервный пул.</span><span class="sxs-lookup"><span data-stu-id="57af3-p101">During disaster recovery, calls behave differently depending on whether the primary pool response groups were imported to the backup pool during recovery. In the following table, references to imported response groups mean that primary pool response groups were imported to the backup pool during disaster recovery mode.</span></span>



</div>

### <a name="outage-occurs"></a><span data-ttu-id="57af3-112">Возникает сбой</span><span class="sxs-lookup"><span data-stu-id="57af3-112">Outage Occurs</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="57af3-113">Тип звонка или действия пользователя</span><span class="sxs-lookup"><span data-stu-id="57af3-113">Type of call or user action</span></span></th>
<th><span data-ttu-id="57af3-114">Во время сбоя</span><span class="sxs-lookup"><span data-stu-id="57af3-114">During outage</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="57af3-115">Звонки, подсоединенные к агенту</span><span class="sxs-lookup"><span data-stu-id="57af3-115">Calls connected to an agent</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="57af3-116">Обычные звонки остаются соединенными.</span><span class="sxs-lookup"><span data-stu-id="57af3-116">Regular calls remain connected.</span></span></p></li>
<li><p><span data-ttu-id="57af3-117">Анонимные звонки отсоединяются.</span><span class="sxs-lookup"><span data-stu-id="57af3-117">Anonymous calls are disconnected.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="57af3-118">Обрабатываемые звонки, еще не подсоединенные к агенту</span><span class="sxs-lookup"><span data-stu-id="57af3-118">In progress calls not yet connected to an agent</span></span></p></td>
<td><p><span data-ttu-id="57af3-119">Звонки отсоединяются.</span><span class="sxs-lookup"><span data-stu-id="57af3-119">Calls are disconnected.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="57af3-120">Новые звонки</span><span class="sxs-lookup"><span data-stu-id="57af3-120">New calls</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="57af3-121">Звонки отсоединяются.</span><span class="sxs-lookup"><span data-stu-id="57af3-121">Calls are disconnected.</span></span></p></li>
<li><p><span data-ttu-id="57af3-122">Если группы ответа были импортированы, звонки подключаются к резервному пулу, однако возможность подключения к агентам, расположенным в основном пуле, отсутствует.</span><span class="sxs-lookup"><span data-stu-id="57af3-122">If response groups were imported, calls connect to backup pool, but agents homed in primary pool are unreachable.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="57af3-123">Звонки агентов от лица группы ответа</span><span class="sxs-lookup"><span data-stu-id="57af3-123">Agent calls on behalf of response group</span></span></p></td>
<td><p><span data-ttu-id="57af3-124">На данном этапе возможность отключена.</span><span class="sxs-lookup"><span data-stu-id="57af3-124">Feature is disabled during this stage.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="57af3-125">Вход агентов и информация об агентах</span><span class="sxs-lookup"><span data-stu-id="57af3-125">Agent sign-in and agent information</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="57af3-126">Группы агентов, принадлежащие основному пулу, можно просматривать в консоли агента, однако выполнить вход агенты не могут.</span><span class="sxs-lookup"><span data-stu-id="57af3-126">Agent groups owned by the primary pool can be viewed on agent console but agents cannot sign in.</span></span></p></li>
<li><p><span data-ttu-id="57af3-127">Группы агентов, принадлежащие резервному пулу, можно просматривать в консоли агента, и агенты могут выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="57af3-127">Agent groups owned by the backup pool can be viewed on agent console and agents can sign in.</span></span></p></li>
<li><p><span data-ttu-id="57af3-128">Импортированные группы агентов не отображаются в консоли агента.</span><span class="sxs-lookup"><span data-stu-id="57af3-128">Imported agent groups are not displayed on agent console.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="57af3-129">Конфигурация группы ответа</span><span class="sxs-lookup"><span data-stu-id="57af3-129">Response group configuration</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="57af3-130">Группы ответа, принадлежащие основному пулу, можно просматривать в зависимости от доступности серверной базы данных основного пула, но нельзя изменять.</span><span class="sxs-lookup"><span data-stu-id="57af3-130">Response groups owned by the primary pool can be viewed, depending on the availability of the primary pool’s back-end database, but cannot be modified.</span></span></p></li>
<li><p><span data-ttu-id="57af3-131">Группы ответа, принадлежащие резервному пулу, можно просматривать и изменять.</span><span class="sxs-lookup"><span data-stu-id="57af3-131">Response groups owned by the backup pool can be viewed and modified.</span></span></p></li>
<li><p><span data-ttu-id="57af3-132">Импортированные группы ответа невозможно просмотреть с помощью панели управления Lync Server или средства настройки группы ответа, но их можно настроить с помощью командлетов командной консоли Lync Server.</span><span class="sxs-lookup"><span data-stu-id="57af3-132">Imported response groups cannot be viewed with Lync Server Control Panel or the Response Group Configuration Tool, but can be configured by using Lync Server Management Shell cmdlets.</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="user-experience-during-failover"></a><span data-ttu-id="57af3-133">Взаимодействие с пользователем во время отработки отказа</span><span class="sxs-lookup"><span data-stu-id="57af3-133">User Experience During Failover</span></span>

<span data-ttu-id="57af3-p102">При вызове администратором отработки отказа с переходом на резервный пул, действия группы ответов обрабатывается во время и после отработки отказа, как описано в следующей таблице. В первом столбце описывается тип возможного действия.  В среднем столбце описывается обработка каждого действия во время краткосрочного периода отработки отказа с переходом на резервный пул. В последнем столбце описано, как действие обрабатывается после отработки отказа и во время замещения резервным пулом основного пула.</span><span class="sxs-lookup"><span data-stu-id="57af3-p102">When an administrator invokes failover to a backup pool, response group activity is handled during and after the failover as described in the following table. The first column describes the type of activity that might be taking place. The middle column describes how each activity is handled during the brief time that it takes to fail over to the backup pool. The last column describes how the activity is handled for the duration, after the failover process is complete and the backup pool is standing in for the primary pool.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="57af3-p103">Во время аварийного восстановления звонки реализуются иначе в зависимости от того, были ли группы ответа основного пула импортированы в резервный пул вор время восстановления. В следующей таблице ссылки на импортированные группы ответа означают, что в режиме аварийного восстановления группы ответа основного пула были  импортированы в резервный пул.</span><span class="sxs-lookup"><span data-stu-id="57af3-p103">During disaster recovery, calls behave differently depending on whether the primary pool response groups were imported to the backup pool during recovery. In the following table, references to imported response groups mean that primary pool response groups were imported to the backup pool during disaster recovery mode.</span></span>



</div>

### <a name="failover-is-initiated"></a><span data-ttu-id="57af3-140">Инициирована отработка отказа</span><span class="sxs-lookup"><span data-stu-id="57af3-140">Failover Is Initiated</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="57af3-141">Тип звонка или действия пользователя</span><span class="sxs-lookup"><span data-stu-id="57af3-141">Type of call or user action</span></span></th>
<th><span data-ttu-id="57af3-142">Во время отработки отказа</span><span class="sxs-lookup"><span data-stu-id="57af3-142">During Failover</span></span></th>
<th><span data-ttu-id="57af3-143">После завершения отработки отказа</span><span class="sxs-lookup"><span data-stu-id="57af3-143">After Failover Completes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="57af3-144">Звонки, подсоединенные к агенту</span><span class="sxs-lookup"><span data-stu-id="57af3-144">Calls connected to an agent</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="57af3-145">Обычные звонки остаются соединенными.</span><span class="sxs-lookup"><span data-stu-id="57af3-145">Regular calls remain connected.</span></span></p></li>
<li><p><span data-ttu-id="57af3-146">Анонимные звонки отсоединяются.</span><span class="sxs-lookup"><span data-stu-id="57af3-146">Anonymous calls are disconnected.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="57af3-147">Обычные звонки остаются соединенными.</span><span class="sxs-lookup"><span data-stu-id="57af3-147">Regular calls remain connected.</span></span></p></li>
<li><p><span data-ttu-id="57af3-148">Для импортированных групп ответа анонимные звонки, достигшие резервного пула, остаются соединенными.</span><span class="sxs-lookup"><span data-stu-id="57af3-148">For imported response groups, anonymous calls that have reached the backup pool remain connected.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="57af3-149">Обрабатываемые звонки, еще не подсоединенные к агенту</span><span class="sxs-lookup"><span data-stu-id="57af3-149">In progress calls not yet connected to an agent</span></span></p></td>
<td><p><span data-ttu-id="57af3-150">Звонки отсоединяются.</span><span class="sxs-lookup"><span data-stu-id="57af3-150">Calls are disconnected.</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="57af3-151">Если группы ответа не были импортированы, звонки в таком состоянии отсутствуют.</span><span class="sxs-lookup"><span data-stu-id="57af3-151">If response groups were not imported, no calls are in this status.</span></span></p></li>
<li><p><span data-ttu-id="57af3-152">Для импортированных групп ответа звонки, достигшие резервного пула, остаются соединенными.</span><span class="sxs-lookup"><span data-stu-id="57af3-152">For imported response groups, calls that have reached the backup pool remain connected.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="57af3-153">Новые звонки</span><span class="sxs-lookup"><span data-stu-id="57af3-153">New calls</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="57af3-154">Звонки отсоединяются.</span><span class="sxs-lookup"><span data-stu-id="57af3-154">Calls are disconnected.</span></span></p></li>
<li><p><span data-ttu-id="57af3-155">Для импортированных групп ответа звонки подключаются к резервному пулу, однако возможность подключения к агентам, расположенным в основном пуле, отсутствует.</span><span class="sxs-lookup"><span data-stu-id="57af3-155">For imported response groups, calls connect to the backup pool, but agents homed in the primary pool are unreachable.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="57af3-156">Если группы ответов не были импортированы, вызовы отключаются.</span><span class="sxs-lookup"><span data-stu-id="57af3-156">If response groups were not imported, calls are disconnected.</span></span></p></li>
<li><p><span data-ttu-id="57af3-157">Для импортированных групп ответа звонки соединяются с резервным пулом.</span><span class="sxs-lookup"><span data-stu-id="57af3-157">For imported response groups, calls connect to the backup pool.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="57af3-158">Звонки агентов от лица группы ответа</span><span class="sxs-lookup"><span data-stu-id="57af3-158">Agent calls on behalf of response group</span></span></p></td>
<td><p><span data-ttu-id="57af3-159">На данном этапе возможность отключена</span><span class="sxs-lookup"><span data-stu-id="57af3-159">Feature is disabled during this stage</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="57af3-160">Если группы ответа не были импортированы, звонки завершаются со сбоем.</span><span class="sxs-lookup"><span data-stu-id="57af3-160">If response groups were not imported, calls fail.</span></span></p></li>
<li><p><span data-ttu-id="57af3-161">Для импортированных групп ответа звонки выполняются успешно.</span><span class="sxs-lookup"><span data-stu-id="57af3-161">For imported response groups, calls succeed.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="57af3-162">Вход агентов и информация об агентах</span><span class="sxs-lookup"><span data-stu-id="57af3-162">Agent sign-in and agent information</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="57af3-163">Группы агентов, принадлежащие основному пулу, можно просматривать в консоли агента, однако выполнить вход агенты не могут.</span><span class="sxs-lookup"><span data-stu-id="57af3-163">Agent groups owned by the primary pool can be viewed on agent console but agents cannot sign in.</span></span></p></li>
<li><p><span data-ttu-id="57af3-164">Группы агентов, принадлежащие резервному пулу, можно просматривать в консоли агента, и агенты могут выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="57af3-164">Agent groups owned by the backup pool can be viewed on agent console and agents can sign in.</span></span></p></li>
<li><p><span data-ttu-id="57af3-165">Импортированные группы агентов отображаются в консоли агента, и агенты могут выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="57af3-165">Imported agent groups are displayed on agent console and agents can sign in.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="57af3-166">Группы агентов, принадлежащие основному пулу, можно просматривать в консоли агента, однако выполнить вход агенты не могут.</span><span class="sxs-lookup"><span data-stu-id="57af3-166">Agent groups owned by the primary pool can be viewed on agent console but agents cannot sign in.</span></span></p></li>
<li><p><span data-ttu-id="57af3-167">Группы агентов, принадлежащие резервному пулу, можно просматривать в консоли агента, и агенты могут выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="57af3-167">Agent groups owned by the backup pool can be viewed on agent console and agents can sign in.</span></span></p></li>
<li><p><span data-ttu-id="57af3-168">Импортированные группы агентов отображаются в консоли агента, и агенты могут выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="57af3-168">Imported agent groups are displayed on agent console and agents can sign in.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="57af3-169">Конфигурация группы ответа</span><span class="sxs-lookup"><span data-stu-id="57af3-169">Response group configuration</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="57af3-170">Группы ответа, принадлежащие основному пулу, можно просматривать в зависимости от доступности серверной базы данных основного пула, но нельзя изменять.</span><span class="sxs-lookup"><span data-stu-id="57af3-170">Response groups owned by the primary pool can be viewed, depending on the availability of the primary pool’s back-end database, but cannot be modified.</span></span></p></li>
<li><p><span data-ttu-id="57af3-171">Группы ответа, принадлежащие резервному пулу, можно просматривать и изменять.</span><span class="sxs-lookup"><span data-stu-id="57af3-171">Response groups owned by the backup pool can be viewed and modified.</span></span></p></li>
<li><p><span data-ttu-id="57af3-172">Импортированные группы ответа невозможно просмотреть с помощью панели управления Lync Server или средства настройки группы ответа, но их можно настроить с помощью командлетов командной консоли Lync Server.</span><span class="sxs-lookup"><span data-stu-id="57af3-172">Imported response groups cannot be viewed with Lync Server Control Panel or the Response Group Configuration Tool, but can be configured by using Lync Server Management Shell cmdlets.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="57af3-173">Группы ответа, принадлежащие основному пулу, можно просматривать в зависимости от доступности серверной базы данных, но нельзя изменять.</span><span class="sxs-lookup"><span data-stu-id="57af3-173">Response groups owned by the primary pool can be viewed, depending on the availability of the back end database, but cannot be modified.</span></span></p></li>
<li><p><span data-ttu-id="57af3-174">Группы ответа, принадлежащие резервному пулу, можно просматривать и изменять.</span><span class="sxs-lookup"><span data-stu-id="57af3-174">Response groups owned by the backup pool can be viewed and modified.</span></span></p></li>
<li><p><span data-ttu-id="57af3-175">Импортированные группы ответа невозможно просмотреть с помощью панели управления Lync Server или средства настройки группы ответа, но их можно настроить с помощью командлетов командной консоли Lync Server.</span><span class="sxs-lookup"><span data-stu-id="57af3-175">Imported response groups cannot be viewed with Lync Server Control Panel or the Response Group Configuration Tool, but can be configured by using Lync Server Management Shell cmdlets.</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="user-experience-during-failback"></a><span data-ttu-id="57af3-176">Взаимодействие с пользователем во время восстановления размещения</span><span class="sxs-lookup"><span data-stu-id="57af3-176">User Experience During Failback</span></span>

<span data-ttu-id="57af3-177">Когда администратор вызывает восстановление размещения в основной пул, обработка деятельности группы ответа во время и после восстановления размещения осуществляется в соответствии со следующей таблицей.</span><span class="sxs-lookup"><span data-stu-id="57af3-177">When an administrator invokes failback to the primary pool, response group activity is handled during and after the failback as described in the following table.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="57af3-p104">Во время аварийного восстановления звонки реализуются иначе в зависимости от того, были ли группы ответа основного пула импортированы в резервный пул вор время восстановления. В следующей таблице ссылки на импортированные группы ответа означают, что в режиме аварийного восстановления группы ответа основного пула были  импортированы в резервный пул.</span><span class="sxs-lookup"><span data-stu-id="57af3-p104">During disaster recovery, calls behave differently depending on whether the primary pool response groups were imported to the backup pool during recovery. In the following table, references to imported response groups mean that primary pool response groups were imported to the backup pool during disaster recovery mode.</span></span>



</div>

### <a name="call-handling-in-failback"></a><span data-ttu-id="57af3-180">Обработка звонков во время восстановления размещения</span><span class="sxs-lookup"><span data-stu-id="57af3-180">Call Handling in Failback</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="57af3-181">Тип звонка или действия пользователя</span><span class="sxs-lookup"><span data-stu-id="57af3-181">Type of call or user action</span></span></th>
<th><span data-ttu-id="57af3-182">Во время восстановления размещения</span><span class="sxs-lookup"><span data-stu-id="57af3-182">During Failback</span></span></th>
<th><span data-ttu-id="57af3-183">После завершения восстановления размещения</span><span class="sxs-lookup"><span data-stu-id="57af3-183">After Failback Completes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="57af3-184">Звонки, подсоединенные к агенту</span><span class="sxs-lookup"><span data-stu-id="57af3-184">Calls connected to an agent</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="57af3-185">Обычные звонки остаются соединенными.</span><span class="sxs-lookup"><span data-stu-id="57af3-185">Regular calls remain connected.</span></span></p></li>
<li><p><span data-ttu-id="57af3-186">Если группы ответа не были импортированы, анонимные звонки в таком состоянии отсутствуют.</span><span class="sxs-lookup"><span data-stu-id="57af3-186">If response groups were not imported, no anonymous calls are in this status.</span></span></p></li>
<li><p><span data-ttu-id="57af3-187">Для импортированных групп ответа анонимные звонки остаются соединенными.</span><span class="sxs-lookup"><span data-stu-id="57af3-187">For imported response groups, anonymous calls remain connected.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="57af3-188">Обычные звонки остаются соединенными.</span><span class="sxs-lookup"><span data-stu-id="57af3-188">Regular calls remain connected.</span></span></p></li>
<li><p><span data-ttu-id="57af3-189">Если группы ответа не были импортированы, анонимные звонки в таком состоянии отсутствуют.</span><span class="sxs-lookup"><span data-stu-id="57af3-189">If response groups were not imported, no anonymous calls are in this status.</span></span></p></li>
<li><p><span data-ttu-id="57af3-190">Для импортированных групп ответа анонимные звонки остаются соединенными.</span><span class="sxs-lookup"><span data-stu-id="57af3-190">For imported response groups, anonymous calls remain connected.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="57af3-191">Обрабатываемые звонки, еще не подсоединенные к агенту</span><span class="sxs-lookup"><span data-stu-id="57af3-191">In progress calls not yet connected to an agent</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="57af3-192">Если группы ответа не были импортированы, звонки в таком состоянии отсутствуют.</span><span class="sxs-lookup"><span data-stu-id="57af3-192">If response groups were not imported, no calls are in this status.</span></span></p></li>
<li><p><span data-ttu-id="57af3-193">Для импортированных групп ответа звонки будут отключены.</span><span class="sxs-lookup"><span data-stu-id="57af3-193">For imported response groups, calls will be disconnected.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="57af3-194">Если группы ответа не были импортированы, звонки в таком состоянии отсутствуют.</span><span class="sxs-lookup"><span data-stu-id="57af3-194">If response groups were not imported, no calls are in this status.</span></span></p></li>
<li><p><span data-ttu-id="57af3-195">Для импортированных групп ответа звонки будут отключены.</span><span class="sxs-lookup"><span data-stu-id="57af3-195">For imported response groups, calls will be disconnected.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="57af3-196">Новые звонки</span><span class="sxs-lookup"><span data-stu-id="57af3-196">New calls</span></span></p></td>
<td><p><span data-ttu-id="57af3-197">Звонки подключаются к основному пулу, однако возможность подключения к агентам, расположенным в основном пуле, отсутствует.</span><span class="sxs-lookup"><span data-stu-id="57af3-197">Calls connect to the primary pool, but agents homed in the primary pool are unreachable.</span></span></p></td>
<td><p><span data-ttu-id="57af3-198">Звонки подсоединяются к основному пулу.</span><span class="sxs-lookup"><span data-stu-id="57af3-198">Calls connect to the primary pool.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="57af3-199">Звонки агентов от лица группы ответа</span><span class="sxs-lookup"><span data-stu-id="57af3-199">Agent calls on behalf of response group</span></span></p></td>
<td><p><span data-ttu-id="57af3-200">На данном этапе возможность отключена.</span><span class="sxs-lookup"><span data-stu-id="57af3-200">Feature is disabled during this stage.</span></span></p></td>
<td><p><span data-ttu-id="57af3-201">Звонки выполняются успешно.</span><span class="sxs-lookup"><span data-stu-id="57af3-201">Calls succeed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="57af3-202">Вход агентов и информация об агентах</span><span class="sxs-lookup"><span data-stu-id="57af3-202">Agent sign-in and agent information</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="57af3-203">Группы агентов, принадлежащие основному пулу, можно просматривать в консоли агента, однако выполнить вход агенты не могут.</span><span class="sxs-lookup"><span data-stu-id="57af3-203">Agent groups owned by the primary pool can be viewed on agent console but agents cannot sign in.</span></span></p></li>
<li><p><span data-ttu-id="57af3-204">Группы агентов, принадлежащие резервному пулу, можно просматривать в консоли агента, и агенты могут выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="57af3-204">Agent groups owned by the backup pool can be viewed on agent console and agents can sign in.</span></span></p></li>
<li><p><span data-ttu-id="57af3-205">Импортированные группы агентов отображаются в консоли агента, и агенты могут выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="57af3-205">Imported agent groups are displayed on agent console and agents can sign in.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="57af3-206">Группы агентов, принадлежащие основному пулу, можно просматривать в консоли агента, и агенты могут выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="57af3-206">Agent groups owned by the primary pool can be viewed on agent console and agents can sign in.</span></span></p></li>
<li><p><span data-ttu-id="57af3-207">Группы агентов, принадлежащие резервному пулу, можно просматривать в консоли агента, и агенты могут выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="57af3-207">Agent groups owned by the backup pool can be viewed on agent console and agents can sign in.</span></span></p></li>
<li><p><span data-ttu-id="57af3-208">Импортированные группы агентов не отображаются в консоли агента.</span><span class="sxs-lookup"><span data-stu-id="57af3-208">Imported agent groups are not displayed on agent console.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="57af3-209">Конфигурация группы ответа</span><span class="sxs-lookup"><span data-stu-id="57af3-209">Response group configuration</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="57af3-210">Группы ответа, принадлежащие основному пулу, можно просматривать в зависимости от доступности серверной базы данных основного пула, но нельзя изменять.</span><span class="sxs-lookup"><span data-stu-id="57af3-210">Response groups owned by the primary pool can be viewed, depending on the availability of the primary pool’s back-end database, but cannot be modified.</span></span></p></li>
<li><p><span data-ttu-id="57af3-211">Группы ответа, принадлежащие резервному пулу, можно просматривать и изменять.</span><span class="sxs-lookup"><span data-stu-id="57af3-211">Response groups owned by the backup pool can be viewed and modified.</span></span></p></li>
<li><p><span data-ttu-id="57af3-212">Импортированные группы ответа невозможно просмотреть с помощью панели управления Lync Server или средства настройки группы ответа, но их можно настроить с помощью командлетов командной консоли Lync Server.</span><span class="sxs-lookup"><span data-stu-id="57af3-212">Imported response groups cannot be viewed with Lync Server Control Panel or the Response Group Configuration Tool, but can be configured by using Lync Server Management Shell cmdlets.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="57af3-213">Группы ответа, принадлежащие основному пулу, можно просматривать и изменять.</span><span class="sxs-lookup"><span data-stu-id="57af3-213">Response groups owned by the primary pool can be viewed and modified.</span></span></p></li>
<li><p><span data-ttu-id="57af3-214">Группы ответа, принадлежащие резервному пулу, можно просматривать и изменять.</span><span class="sxs-lookup"><span data-stu-id="57af3-214">Response groups owned by the backup pool can be viewed and modified.</span></span></p></li>
<li><p><span data-ttu-id="57af3-215">Импортированные группы ответа невозможно просмотреть с помощью панели управления Lync Server или средства настройки группы ответа, но их можно настроить с помощью командлетов командной консоли Lync Server.</span><span class="sxs-lookup"><span data-stu-id="57af3-215">Imported response groups cannot be viewed with Lync Server Control Panel or the Response Group Configuration Tool, but can be configured by using Lync Server Management Shell cmdlets.</span></span></p></li>
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

