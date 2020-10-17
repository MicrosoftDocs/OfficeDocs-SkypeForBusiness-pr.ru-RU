---
title: Lync Server 2013 взаимодействие с группой ответа при отказе пула
description: Lync Server 2013 взаимодействие группы ответа при отказе пула.
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
ms.openlocfilehash: 7d8d5904bc6934d4c330202bafa66d6dd8a16ff5
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48564575"
---
# <a name="response-group-experience-in-lync-server-2013-during-pool-failure"></a><span data-ttu-id="89f5a-103">Взаимодействие группы ответа в Lync Server 2013 во время сбоя пула</span><span class="sxs-lookup"><span data-stu-id="89f5a-103">Response group experience in Lync Server 2013 during pool failure</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="89f5a-104">_**Последнее изменение темы:** 2012-10-30_</span><span class="sxs-lookup"><span data-stu-id="89f5a-104">_**Topic Last Modified:** 2012-10-30_</span></span>

<span data-ttu-id="89f5a-105">В этом разделе подробно описывается, какое влияние оказывается на деятельность группы ответа на следующих этапах:</span><span class="sxs-lookup"><span data-stu-id="89f5a-105">This section describes in detail how response group activity is affected in the following stages:</span></span>

  - <span data-ttu-id="89f5a-106">В основном пуле происходит сбой, однако отработка отказа еще не активирована.</span><span class="sxs-lookup"><span data-stu-id="89f5a-106">An outage occurs in the primary pool, but failover is not yet initiated.</span></span>

  - <span data-ttu-id="89f5a-107">Выполняется отработка отказа для службы в резервный пул.</span><span class="sxs-lookup"><span data-stu-id="89f5a-107">Service is failed over to the backup pool.</span></span>

  - <span data-ttu-id="89f5a-108">Выполняется восстановление размещения для службы в основной пул.</span><span class="sxs-lookup"><span data-stu-id="89f5a-108">Service is failed back to the primary pool.</span></span>

<div>

## <a name="user-experience-when-outage-occurs"></a><span data-ttu-id="89f5a-109">Взаимодействие с пользователем при возникновении сбоя</span><span class="sxs-lookup"><span data-stu-id="89f5a-109">User Experience When Outage Occurs</span></span>

<span data-ttu-id="89f5a-110">Если возник сбой пула или сайта, а администратор еще не активировал отработку отказа, обработка деятельности группы ответа осуществляется в соответствии со следующей таблицей.</span><span class="sxs-lookup"><span data-stu-id="89f5a-110">When a pool or site outage occurs, but the administrator has not yet initiated failover, response group activity is handled as described in the following table.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="89f5a-p101">Во время аварийного восстановления звонки реализуются иначе в зависимости от того, были ли группы ответа основного пула импортированы в резервный пул вор время восстановления. В следующей таблице ссылки на импортированные группы ответа означают, что в режиме аварийного восстановления группы ответа основного пула были  импортированы в резервный пул.</span><span class="sxs-lookup"><span data-stu-id="89f5a-p101">During disaster recovery, calls behave differently depending on whether the primary pool response groups were imported to the backup pool during recovery. In the following table, references to imported response groups mean that primary pool response groups were imported to the backup pool during disaster recovery mode.</span></span>



</div>

### <a name="outage-occurs"></a><span data-ttu-id="89f5a-113">Возникает сбой</span><span class="sxs-lookup"><span data-stu-id="89f5a-113">Outage Occurs</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="89f5a-114">Тип звонка или действия пользователя</span><span class="sxs-lookup"><span data-stu-id="89f5a-114">Type of call or user action</span></span></th>
<th><span data-ttu-id="89f5a-115">Во время сбоя</span><span class="sxs-lookup"><span data-stu-id="89f5a-115">During outage</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="89f5a-116">Звонки, подсоединенные к агенту</span><span class="sxs-lookup"><span data-stu-id="89f5a-116">Calls connected to an agent</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="89f5a-117">Обычные звонки остаются соединенными.</span><span class="sxs-lookup"><span data-stu-id="89f5a-117">Regular calls remain connected.</span></span></p></li>
<li><p><span data-ttu-id="89f5a-118">Анонимные звонки отсоединяются.</span><span class="sxs-lookup"><span data-stu-id="89f5a-118">Anonymous calls are disconnected.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="89f5a-119">Обрабатываемые звонки, еще не подсоединенные к агенту</span><span class="sxs-lookup"><span data-stu-id="89f5a-119">In progress calls not yet connected to an agent</span></span></p></td>
<td><p><span data-ttu-id="89f5a-120">Звонки отсоединяются.</span><span class="sxs-lookup"><span data-stu-id="89f5a-120">Calls are disconnected.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="89f5a-121">Новые звонки</span><span class="sxs-lookup"><span data-stu-id="89f5a-121">New calls</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="89f5a-122">Звонки отсоединяются.</span><span class="sxs-lookup"><span data-stu-id="89f5a-122">Calls are disconnected.</span></span></p></li>
<li><p><span data-ttu-id="89f5a-123">Если группы ответа были импортированы, звонки подключаются к резервному пулу, однако возможность подключения к агентам, расположенным в основном пуле, отсутствует.</span><span class="sxs-lookup"><span data-stu-id="89f5a-123">If response groups were imported, calls connect to backup pool, but agents homed in primary pool are unreachable.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="89f5a-124">Звонки агентов от лица группы ответа</span><span class="sxs-lookup"><span data-stu-id="89f5a-124">Agent calls on behalf of response group</span></span></p></td>
<td><p><span data-ttu-id="89f5a-125">На данном этапе возможность отключена.</span><span class="sxs-lookup"><span data-stu-id="89f5a-125">Feature is disabled during this stage.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="89f5a-126">Вход агентов и информация об агентах</span><span class="sxs-lookup"><span data-stu-id="89f5a-126">Agent sign-in and agent information</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="89f5a-127">Группы агентов, принадлежащие основному пулу, можно просматривать в консоли агента, однако выполнить вход агенты не могут.</span><span class="sxs-lookup"><span data-stu-id="89f5a-127">Agent groups owned by the primary pool can be viewed on agent console but agents cannot sign in.</span></span></p></li>
<li><p><span data-ttu-id="89f5a-128">Группы агентов, принадлежащие резервному пулу, можно просматривать в консоли агента, и агенты могут выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="89f5a-128">Agent groups owned by the backup pool can be viewed on agent console and agents can sign in.</span></span></p></li>
<li><p><span data-ttu-id="89f5a-129">Импортированные группы агентов не отображаются в консоли агента.</span><span class="sxs-lookup"><span data-stu-id="89f5a-129">Imported agent groups are not displayed on agent console.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="89f5a-130">Конфигурация группы ответа</span><span class="sxs-lookup"><span data-stu-id="89f5a-130">Response group configuration</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="89f5a-131">Группы ответа, принадлежащие основному пулу, можно просматривать в зависимости от доступности серверной базы данных основного пула, но нельзя изменять.</span><span class="sxs-lookup"><span data-stu-id="89f5a-131">Response groups owned by the primary pool can be viewed, depending on the availability of the primary pool’s back-end database, but cannot be modified.</span></span></p></li>
<li><p><span data-ttu-id="89f5a-132">Группы ответа, принадлежащие резервному пулу, можно просматривать и изменять.</span><span class="sxs-lookup"><span data-stu-id="89f5a-132">Response groups owned by the backup pool can be viewed and modified.</span></span></p></li>
<li><p><span data-ttu-id="89f5a-133">Импортированные группы ответа невозможно просмотреть с помощью панели управления Lync Server или средства настройки группы ответа, но их можно настроить с помощью командлетов командной консоли Lync Server.</span><span class="sxs-lookup"><span data-stu-id="89f5a-133">Imported response groups cannot be viewed with Lync Server Control Panel or the Response Group Configuration Tool, but can be configured by using Lync Server Management Shell cmdlets.</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="user-experience-during-failover"></a><span data-ttu-id="89f5a-134">Взаимодействие с пользователем во время отработки отказа</span><span class="sxs-lookup"><span data-stu-id="89f5a-134">User Experience During Failover</span></span>

<span data-ttu-id="89f5a-p102">При вызове администратором отработки отказа с переходом на резервный пул, действия группы ответов обрабатывается во время и после отработки отказа, как описано в следующей таблице. В первом столбце описывается тип возможного действия.  В среднем столбце описывается обработка каждого действия во время краткосрочного периода отработки отказа с переходом на резервный пул. В последнем столбце описано, как действие обрабатывается после отработки отказа и во время замещения резервным пулом основного пула.</span><span class="sxs-lookup"><span data-stu-id="89f5a-p102">When an administrator invokes failover to a backup pool, response group activity is handled during and after the failover as described in the following table. The first column describes the type of activity that might be taking place. The middle column describes how each activity is handled during the brief time that it takes to fail over to the backup pool. The last column describes how the activity is handled for the duration, after the failover process is complete and the backup pool is standing in for the primary pool.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="89f5a-p103">Во время аварийного восстановления звонки реализуются иначе в зависимости от того, были ли группы ответа основного пула импортированы в резервный пул вор время восстановления. В следующей таблице ссылки на импортированные группы ответа означают, что в режиме аварийного восстановления группы ответа основного пула были  импортированы в резервный пул.</span><span class="sxs-lookup"><span data-stu-id="89f5a-p103">During disaster recovery, calls behave differently depending on whether the primary pool response groups were imported to the backup pool during recovery. In the following table, references to imported response groups mean that primary pool response groups were imported to the backup pool during disaster recovery mode.</span></span>



</div>

### <a name="failover-is-initiated"></a><span data-ttu-id="89f5a-141">Инициирована отработка отказа</span><span class="sxs-lookup"><span data-stu-id="89f5a-141">Failover Is Initiated</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="89f5a-142">Тип звонка или действия пользователя</span><span class="sxs-lookup"><span data-stu-id="89f5a-142">Type of call or user action</span></span></th>
<th><span data-ttu-id="89f5a-143">Во время отработки отказа</span><span class="sxs-lookup"><span data-stu-id="89f5a-143">During Failover</span></span></th>
<th><span data-ttu-id="89f5a-144">После завершения отработки отказа</span><span class="sxs-lookup"><span data-stu-id="89f5a-144">After Failover Completes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="89f5a-145">Звонки, подсоединенные к агенту</span><span class="sxs-lookup"><span data-stu-id="89f5a-145">Calls connected to an agent</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="89f5a-146">Обычные звонки остаются соединенными.</span><span class="sxs-lookup"><span data-stu-id="89f5a-146">Regular calls remain connected.</span></span></p></li>
<li><p><span data-ttu-id="89f5a-147">Анонимные звонки отсоединяются.</span><span class="sxs-lookup"><span data-stu-id="89f5a-147">Anonymous calls are disconnected.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="89f5a-148">Обычные звонки остаются соединенными.</span><span class="sxs-lookup"><span data-stu-id="89f5a-148">Regular calls remain connected.</span></span></p></li>
<li><p><span data-ttu-id="89f5a-149">Для импортированных групп ответа анонимные звонки, достигшие резервного пула, остаются соединенными.</span><span class="sxs-lookup"><span data-stu-id="89f5a-149">For imported response groups, anonymous calls that have reached the backup pool remain connected.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="89f5a-150">Обрабатываемые звонки, еще не подсоединенные к агенту</span><span class="sxs-lookup"><span data-stu-id="89f5a-150">In progress calls not yet connected to an agent</span></span></p></td>
<td><p><span data-ttu-id="89f5a-151">Звонки отсоединяются.</span><span class="sxs-lookup"><span data-stu-id="89f5a-151">Calls are disconnected.</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="89f5a-152">Если группы ответа не были импортированы, звонки в таком состоянии отсутствуют.</span><span class="sxs-lookup"><span data-stu-id="89f5a-152">If response groups were not imported, no calls are in this status.</span></span></p></li>
<li><p><span data-ttu-id="89f5a-153">Для импортированных групп ответа звонки, достигшие резервного пула, остаются соединенными.</span><span class="sxs-lookup"><span data-stu-id="89f5a-153">For imported response groups, calls that have reached the backup pool remain connected.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="89f5a-154">Новые звонки</span><span class="sxs-lookup"><span data-stu-id="89f5a-154">New calls</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="89f5a-155">Звонки отсоединяются.</span><span class="sxs-lookup"><span data-stu-id="89f5a-155">Calls are disconnected.</span></span></p></li>
<li><p><span data-ttu-id="89f5a-156">Для импортированных групп ответа звонки подключаются к резервному пулу, однако возможность подключения к агентам, расположенным в основном пуле, отсутствует.</span><span class="sxs-lookup"><span data-stu-id="89f5a-156">For imported response groups, calls connect to the backup pool, but agents homed in the primary pool are unreachable.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="89f5a-157">Если группы ответов не были импортированы, вызовы отключаются.</span><span class="sxs-lookup"><span data-stu-id="89f5a-157">If response groups were not imported, calls are disconnected.</span></span></p></li>
<li><p><span data-ttu-id="89f5a-158">Для импортированных групп ответа звонки соединяются с резервным пулом.</span><span class="sxs-lookup"><span data-stu-id="89f5a-158">For imported response groups, calls connect to the backup pool.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="89f5a-159">Звонки агентов от лица группы ответа</span><span class="sxs-lookup"><span data-stu-id="89f5a-159">Agent calls on behalf of response group</span></span></p></td>
<td><p><span data-ttu-id="89f5a-160">На данном этапе возможность отключена</span><span class="sxs-lookup"><span data-stu-id="89f5a-160">Feature is disabled during this stage</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="89f5a-161">Если группы ответа не были импортированы, звонки завершаются со сбоем.</span><span class="sxs-lookup"><span data-stu-id="89f5a-161">If response groups were not imported, calls fail.</span></span></p></li>
<li><p><span data-ttu-id="89f5a-162">Для импортированных групп ответа звонки выполняются успешно.</span><span class="sxs-lookup"><span data-stu-id="89f5a-162">For imported response groups, calls succeed.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="89f5a-163">Вход агентов и информация об агентах</span><span class="sxs-lookup"><span data-stu-id="89f5a-163">Agent sign-in and agent information</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="89f5a-164">Группы агентов, принадлежащие основному пулу, можно просматривать в консоли агента, однако выполнить вход агенты не могут.</span><span class="sxs-lookup"><span data-stu-id="89f5a-164">Agent groups owned by the primary pool can be viewed on agent console but agents cannot sign in.</span></span></p></li>
<li><p><span data-ttu-id="89f5a-165">Группы агентов, принадлежащие резервному пулу, можно просматривать в консоли агента, и агенты могут выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="89f5a-165">Agent groups owned by the backup pool can be viewed on agent console and agents can sign in.</span></span></p></li>
<li><p><span data-ttu-id="89f5a-166">Импортированные группы агентов отображаются в консоли агента, и агенты могут выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="89f5a-166">Imported agent groups are displayed on agent console and agents can sign in.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="89f5a-167">Группы агентов, принадлежащие основному пулу, можно просматривать в консоли агента, однако выполнить вход агенты не могут.</span><span class="sxs-lookup"><span data-stu-id="89f5a-167">Agent groups owned by the primary pool can be viewed on agent console but agents cannot sign in.</span></span></p></li>
<li><p><span data-ttu-id="89f5a-168">Группы агентов, принадлежащие резервному пулу, можно просматривать в консоли агента, и агенты могут выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="89f5a-168">Agent groups owned by the backup pool can be viewed on agent console and agents can sign in.</span></span></p></li>
<li><p><span data-ttu-id="89f5a-169">Импортированные группы агентов отображаются в консоли агента, и агенты могут выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="89f5a-169">Imported agent groups are displayed on agent console and agents can sign in.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="89f5a-170">Конфигурация группы ответа</span><span class="sxs-lookup"><span data-stu-id="89f5a-170">Response group configuration</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="89f5a-171">Группы ответа, принадлежащие основному пулу, можно просматривать в зависимости от доступности серверной базы данных основного пула, но нельзя изменять.</span><span class="sxs-lookup"><span data-stu-id="89f5a-171">Response groups owned by the primary pool can be viewed, depending on the availability of the primary pool’s back-end database, but cannot be modified.</span></span></p></li>
<li><p><span data-ttu-id="89f5a-172">Группы ответа, принадлежащие резервному пулу, можно просматривать и изменять.</span><span class="sxs-lookup"><span data-stu-id="89f5a-172">Response groups owned by the backup pool can be viewed and modified.</span></span></p></li>
<li><p><span data-ttu-id="89f5a-173">Импортированные группы ответа невозможно просмотреть с помощью панели управления Lync Server или средства настройки группы ответа, но их можно настроить с помощью командлетов командной консоли Lync Server.</span><span class="sxs-lookup"><span data-stu-id="89f5a-173">Imported response groups cannot be viewed with Lync Server Control Panel or the Response Group Configuration Tool, but can be configured by using Lync Server Management Shell cmdlets.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="89f5a-174">Группы ответа, принадлежащие основному пулу, можно просматривать в зависимости от доступности серверной базы данных, но нельзя изменять.</span><span class="sxs-lookup"><span data-stu-id="89f5a-174">Response groups owned by the primary pool can be viewed, depending on the availability of the back end database, but cannot be modified.</span></span></p></li>
<li><p><span data-ttu-id="89f5a-175">Группы ответа, принадлежащие резервному пулу, можно просматривать и изменять.</span><span class="sxs-lookup"><span data-stu-id="89f5a-175">Response groups owned by the backup pool can be viewed and modified.</span></span></p></li>
<li><p><span data-ttu-id="89f5a-176">Импортированные группы ответа невозможно просмотреть с помощью панели управления Lync Server или средства настройки группы ответа, но их можно настроить с помощью командлетов командной консоли Lync Server.</span><span class="sxs-lookup"><span data-stu-id="89f5a-176">Imported response groups cannot be viewed with Lync Server Control Panel or the Response Group Configuration Tool, but can be configured by using Lync Server Management Shell cmdlets.</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="user-experience-during-failback"></a><span data-ttu-id="89f5a-177">Взаимодействие с пользователем во время восстановления размещения</span><span class="sxs-lookup"><span data-stu-id="89f5a-177">User Experience During Failback</span></span>

<span data-ttu-id="89f5a-178">Когда администратор вызывает восстановление размещения в основной пул, обработка деятельности группы ответа во время и после восстановления размещения осуществляется в соответствии со следующей таблицей.</span><span class="sxs-lookup"><span data-stu-id="89f5a-178">When an administrator invokes failback to the primary pool, response group activity is handled during and after the failback as described in the following table.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="89f5a-p104">Во время аварийного восстановления звонки реализуются иначе в зависимости от того, были ли группы ответа основного пула импортированы в резервный пул вор время восстановления. В следующей таблице ссылки на импортированные группы ответа означают, что в режиме аварийного восстановления группы ответа основного пула были  импортированы в резервный пул.</span><span class="sxs-lookup"><span data-stu-id="89f5a-p104">During disaster recovery, calls behave differently depending on whether the primary pool response groups were imported to the backup pool during recovery. In the following table, references to imported response groups mean that primary pool response groups were imported to the backup pool during disaster recovery mode.</span></span>



</div>

### <a name="call-handling-in-failback"></a><span data-ttu-id="89f5a-181">Обработка звонков во время восстановления размещения</span><span class="sxs-lookup"><span data-stu-id="89f5a-181">Call Handling in Failback</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="89f5a-182">Тип звонка или действия пользователя</span><span class="sxs-lookup"><span data-stu-id="89f5a-182">Type of call or user action</span></span></th>
<th><span data-ttu-id="89f5a-183">Во время восстановления размещения</span><span class="sxs-lookup"><span data-stu-id="89f5a-183">During Failback</span></span></th>
<th><span data-ttu-id="89f5a-184">После завершения восстановления размещения</span><span class="sxs-lookup"><span data-stu-id="89f5a-184">After Failback Completes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="89f5a-185">Звонки, подсоединенные к агенту</span><span class="sxs-lookup"><span data-stu-id="89f5a-185">Calls connected to an agent</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="89f5a-186">Обычные звонки остаются соединенными.</span><span class="sxs-lookup"><span data-stu-id="89f5a-186">Regular calls remain connected.</span></span></p></li>
<li><p><span data-ttu-id="89f5a-187">Если группы ответа не были импортированы, анонимные звонки в таком состоянии отсутствуют.</span><span class="sxs-lookup"><span data-stu-id="89f5a-187">If response groups were not imported, no anonymous calls are in this status.</span></span></p></li>
<li><p><span data-ttu-id="89f5a-188">Для импортированных групп ответа анонимные звонки остаются соединенными.</span><span class="sxs-lookup"><span data-stu-id="89f5a-188">For imported response groups, anonymous calls remain connected.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="89f5a-189">Обычные звонки остаются соединенными.</span><span class="sxs-lookup"><span data-stu-id="89f5a-189">Regular calls remain connected.</span></span></p></li>
<li><p><span data-ttu-id="89f5a-190">Если группы ответа не были импортированы, анонимные звонки в таком состоянии отсутствуют.</span><span class="sxs-lookup"><span data-stu-id="89f5a-190">If response groups were not imported, no anonymous calls are in this status.</span></span></p></li>
<li><p><span data-ttu-id="89f5a-191">Для импортированных групп ответа анонимные звонки остаются соединенными.</span><span class="sxs-lookup"><span data-stu-id="89f5a-191">For imported response groups, anonymous calls remain connected.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="89f5a-192">Обрабатываемые звонки, еще не подсоединенные к агенту</span><span class="sxs-lookup"><span data-stu-id="89f5a-192">In progress calls not yet connected to an agent</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="89f5a-193">Если группы ответа не были импортированы, звонки в таком состоянии отсутствуют.</span><span class="sxs-lookup"><span data-stu-id="89f5a-193">If response groups were not imported, no calls are in this status.</span></span></p></li>
<li><p><span data-ttu-id="89f5a-194">Для импортированных групп ответа звонки будут отключены.</span><span class="sxs-lookup"><span data-stu-id="89f5a-194">For imported response groups, calls will be disconnected.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="89f5a-195">Если группы ответа не были импортированы, звонки в таком состоянии отсутствуют.</span><span class="sxs-lookup"><span data-stu-id="89f5a-195">If response groups were not imported, no calls are in this status.</span></span></p></li>
<li><p><span data-ttu-id="89f5a-196">Для импортированных групп ответа звонки будут отключены.</span><span class="sxs-lookup"><span data-stu-id="89f5a-196">For imported response groups, calls will be disconnected.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="89f5a-197">Новые звонки</span><span class="sxs-lookup"><span data-stu-id="89f5a-197">New calls</span></span></p></td>
<td><p><span data-ttu-id="89f5a-198">Звонки подключаются к основному пулу, однако возможность подключения к агентам, расположенным в основном пуле, отсутствует.</span><span class="sxs-lookup"><span data-stu-id="89f5a-198">Calls connect to the primary pool, but agents homed in the primary pool are unreachable.</span></span></p></td>
<td><p><span data-ttu-id="89f5a-199">Звонки подсоединяются к основному пулу.</span><span class="sxs-lookup"><span data-stu-id="89f5a-199">Calls connect to the primary pool.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="89f5a-200">Звонки агентов от лица группы ответа</span><span class="sxs-lookup"><span data-stu-id="89f5a-200">Agent calls on behalf of response group</span></span></p></td>
<td><p><span data-ttu-id="89f5a-201">На данном этапе возможность отключена.</span><span class="sxs-lookup"><span data-stu-id="89f5a-201">Feature is disabled during this stage.</span></span></p></td>
<td><p><span data-ttu-id="89f5a-202">Звонки выполняются успешно.</span><span class="sxs-lookup"><span data-stu-id="89f5a-202">Calls succeed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="89f5a-203">Вход агентов и информация об агентах</span><span class="sxs-lookup"><span data-stu-id="89f5a-203">Agent sign-in and agent information</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="89f5a-204">Группы агентов, принадлежащие основному пулу, можно просматривать в консоли агента, однако выполнить вход агенты не могут.</span><span class="sxs-lookup"><span data-stu-id="89f5a-204">Agent groups owned by the primary pool can be viewed on agent console but agents cannot sign in.</span></span></p></li>
<li><p><span data-ttu-id="89f5a-205">Группы агентов, принадлежащие резервному пулу, можно просматривать в консоли агента, и агенты могут выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="89f5a-205">Agent groups owned by the backup pool can be viewed on agent console and agents can sign in.</span></span></p></li>
<li><p><span data-ttu-id="89f5a-206">Импортированные группы агентов отображаются в консоли агента, и агенты могут выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="89f5a-206">Imported agent groups are displayed on agent console and agents can sign in.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="89f5a-207">Группы агентов, принадлежащие основному пулу, можно просматривать в консоли агента, и агенты могут выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="89f5a-207">Agent groups owned by the primary pool can be viewed on agent console and agents can sign in.</span></span></p></li>
<li><p><span data-ttu-id="89f5a-208">Группы агентов, принадлежащие резервному пулу, можно просматривать в консоли агента, и агенты могут выполнить вход.</span><span class="sxs-lookup"><span data-stu-id="89f5a-208">Agent groups owned by the backup pool can be viewed on agent console and agents can sign in.</span></span></p></li>
<li><p><span data-ttu-id="89f5a-209">Импортированные группы агентов не отображаются в консоли агента.</span><span class="sxs-lookup"><span data-stu-id="89f5a-209">Imported agent groups are not displayed on agent console.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="89f5a-210">Конфигурация группы ответа</span><span class="sxs-lookup"><span data-stu-id="89f5a-210">Response group configuration</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="89f5a-211">Группы ответа, принадлежащие основному пулу, можно просматривать в зависимости от доступности серверной базы данных основного пула, но нельзя изменять.</span><span class="sxs-lookup"><span data-stu-id="89f5a-211">Response groups owned by the primary pool can be viewed, depending on the availability of the primary pool’s back-end database, but cannot be modified.</span></span></p></li>
<li><p><span data-ttu-id="89f5a-212">Группы ответа, принадлежащие резервному пулу, можно просматривать и изменять.</span><span class="sxs-lookup"><span data-stu-id="89f5a-212">Response groups owned by the backup pool can be viewed and modified.</span></span></p></li>
<li><p><span data-ttu-id="89f5a-213">Импортированные группы ответа невозможно просмотреть с помощью панели управления Lync Server или средства настройки группы ответа, но их можно настроить с помощью командлетов командной консоли Lync Server.</span><span class="sxs-lookup"><span data-stu-id="89f5a-213">Imported response groups cannot be viewed with Lync Server Control Panel or the Response Group Configuration Tool, but can be configured by using Lync Server Management Shell cmdlets.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="89f5a-214">Группы ответа, принадлежащие основному пулу, можно просматривать и изменять.</span><span class="sxs-lookup"><span data-stu-id="89f5a-214">Response groups owned by the primary pool can be viewed and modified.</span></span></p></li>
<li><p><span data-ttu-id="89f5a-215">Группы ответа, принадлежащие резервному пулу, можно просматривать и изменять.</span><span class="sxs-lookup"><span data-stu-id="89f5a-215">Response groups owned by the backup pool can be viewed and modified.</span></span></p></li>
<li><p><span data-ttu-id="89f5a-216">Импортированные группы ответа невозможно просмотреть с помощью панели управления Lync Server или средства настройки группы ответа, но их можно настроить с помощью командлетов командной консоли Lync Server.</span><span class="sxs-lookup"><span data-stu-id="89f5a-216">Imported response groups cannot be viewed with Lync Server Control Panel or the Response Group Configuration Tool, but can be configured by using Lync Server Management Shell cmdlets.</span></span></p></li>
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

