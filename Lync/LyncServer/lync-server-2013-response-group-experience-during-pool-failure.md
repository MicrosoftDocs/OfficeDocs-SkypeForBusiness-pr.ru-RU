---
title: 'Lync Server 2013: поведение группы ответа при отказе пула'
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
ms.openlocfilehash: ad00afac363642106019269e86111f61eaca504e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723609"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="response-group-experience-in-lync-server-2013-during-pool-failure"></a><span data-ttu-id="2f7e4-102">Поведение группы ответа Lync Server 2013 при отказе пула</span><span class="sxs-lookup"><span data-stu-id="2f7e4-102">Response group experience in Lync Server 2013 during pool failure</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2f7e4-103">_**Тема последнего изменения:** 2012-10-30_</span><span class="sxs-lookup"><span data-stu-id="2f7e4-103">_**Topic Last Modified:** 2012-10-30_</span></span>

<span data-ttu-id="2f7e4-104">В этом разделе объясняется, как влияют действия группы ответа на следующие этапы:</span><span class="sxs-lookup"><span data-stu-id="2f7e4-104">This section describes in detail how response group activity is affected in the following stages:</span></span>

  - <span data-ttu-id="2f7e4-105">В основном пуле происходит отключение, но еще не инициирована отработка отказа.</span><span class="sxs-lookup"><span data-stu-id="2f7e4-105">An outage occurs in the primary pool, but failover is not yet initiated.</span></span>

  - <span data-ttu-id="2f7e4-106">Ошибка при попытке выполнить обслуживание в пуле резервных копий.</span><span class="sxs-lookup"><span data-stu-id="2f7e4-106">Service is failed over to the backup pool.</span></span>

  - <span data-ttu-id="2f7e4-107">Сбой при восстановлении службы в основной пул.</span><span class="sxs-lookup"><span data-stu-id="2f7e4-107">Service is failed back to the primary pool.</span></span>

<div>

## <a name="user-experience-when-outage-occurs"></a><span data-ttu-id="2f7e4-108">Взаимодействие с пользователем при возникновении сбоя</span><span class="sxs-lookup"><span data-stu-id="2f7e4-108">User Experience When Outage Occurs</span></span>

<span data-ttu-id="2f7e4-109">При возникновении сбоя в работе пула или сайта, но администратор еще не инициировал отработку отказа, действия группы ответа обрабатываются в соответствии с приведенной ниже таблицей.</span><span class="sxs-lookup"><span data-stu-id="2f7e4-109">When a pool or site outage occurs, but the administrator has not yet initiated failover, response group activity is handled as described in the following table.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="2f7e4-110">Во время аварийного восстановления звонки работают по-разному в зависимости от того, были ли группы ответов основного пула импортированы в пул резервного копирования во время восстановления.</span><span class="sxs-lookup"><span data-stu-id="2f7e4-110">During disaster recovery, calls behave differently depending on whether the primary pool response groups were imported to the backup pool during recovery.</span></span> <span data-ttu-id="2f7e4-111">В приведенной ниже таблице ссылки на импортированные группы ответов означают, что группы ответов основного пула были импортированы в пул резервных копий в режиме восстановления после сбоя.</span><span class="sxs-lookup"><span data-stu-id="2f7e4-111">In the following table, references to imported response groups mean that primary pool response groups were imported to the backup pool during disaster recovery mode.</span></span>



</div>

### <a name="outage-occurs"></a><span data-ttu-id="2f7e4-112">Возникает отключение</span><span class="sxs-lookup"><span data-stu-id="2f7e4-112">Outage Occurs</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2f7e4-113">Тип звонка или действия пользователя</span><span class="sxs-lookup"><span data-stu-id="2f7e4-113">Type of call or user action</span></span></th>
<th><span data-ttu-id="2f7e4-114">Во время отключения</span><span class="sxs-lookup"><span data-stu-id="2f7e4-114">During outage</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2f7e4-115">Звонки, подключенные к агенту</span><span class="sxs-lookup"><span data-stu-id="2f7e4-115">Calls connected to an agent</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="2f7e4-116">Обычные звонки остаются подключенными.</span><span class="sxs-lookup"><span data-stu-id="2f7e4-116">Regular calls remain connected.</span></span></p></li>
<li><p><span data-ttu-id="2f7e4-117">Анонимные звонки будут разорваны.</span><span class="sxs-lookup"><span data-stu-id="2f7e4-117">Anonymous calls are disconnected.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2f7e4-118">Звонки, которые пока не подключены к агенту</span><span class="sxs-lookup"><span data-stu-id="2f7e4-118">In progress calls not yet connected to an agent</span></span></p></td>
<td><p><span data-ttu-id="2f7e4-119">Звонки будут разорваны.</span><span class="sxs-lookup"><span data-stu-id="2f7e4-119">Calls are disconnected.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2f7e4-120">Новые звонки</span><span class="sxs-lookup"><span data-stu-id="2f7e4-120">New calls</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="2f7e4-121">Звонки будут разорваны.</span><span class="sxs-lookup"><span data-stu-id="2f7e4-121">Calls are disconnected.</span></span></p></li>
<li><p><span data-ttu-id="2f7e4-122">Если группы ответа импортированы, вызовы подключаются к пулу резервных копий, но агенты, расположенные в основном пуле, недостижимы.</span><span class="sxs-lookup"><span data-stu-id="2f7e4-122">If response groups were imported, calls connect to backup pool, but agents homed in primary pool are unreachable.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2f7e4-123">Вызов агента от имени группы ответа</span><span class="sxs-lookup"><span data-stu-id="2f7e4-123">Agent calls on behalf of response group</span></span></p></td>
<td><p><span data-ttu-id="2f7e4-124">Функция отключена на этом этапе.</span><span class="sxs-lookup"><span data-stu-id="2f7e4-124">Feature is disabled during this stage.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2f7e4-125">Вход агента и информация агента</span><span class="sxs-lookup"><span data-stu-id="2f7e4-125">Agent sign-in and agent information</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="2f7e4-126">Группы агентов, принадлежащие основному пулу, можно просматривать на консоли агента, но агенты не могут войти в систему.</span><span class="sxs-lookup"><span data-stu-id="2f7e4-126">Agent groups owned by the primary pool can be viewed on agent console but agents cannot sign in.</span></span></p></li>
<li><p><span data-ttu-id="2f7e4-127">Группы агентов, владельцами которых является пул резервных копий, можно просмотреть на консоли агента, а агенты могут войти в нее.</span><span class="sxs-lookup"><span data-stu-id="2f7e4-127">Agent groups owned by the backup pool can be viewed on agent console and agents can sign in.</span></span></p></li>
<li><p><span data-ttu-id="2f7e4-128">Импортированные группы агентов не отображаются на консоли агента.</span><span class="sxs-lookup"><span data-stu-id="2f7e4-128">Imported agent groups are not displayed on agent console.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2f7e4-129">Настройка группы ответа</span><span class="sxs-lookup"><span data-stu-id="2f7e4-129">Response group configuration</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="2f7e4-130">Группы ответа, принадлежащие основному пулу, можно просмотреть в зависимости от доступности серверной базы данных основного пула, но не для ее изменения.</span><span class="sxs-lookup"><span data-stu-id="2f7e4-130">Response groups owned by the primary pool can be viewed, depending on the availability of the primary pool’s back-end database, but cannot be modified.</span></span></p></li>
<li><p><span data-ttu-id="2f7e4-131">Группы ответа, принадлежащие пулу резервных копий, можно просмотреть и изменить.</span><span class="sxs-lookup"><span data-stu-id="2f7e4-131">Response groups owned by the backup pool can be viewed and modified.</span></span></p></li>
<li><p><span data-ttu-id="2f7e4-132">Импортированные группы ответа нельзя просматривать с помощью панели управления Lync Server или средства настройки группы ответа, но их можно настроить в командлетах командной консоли Lync Server.</span><span class="sxs-lookup"><span data-stu-id="2f7e4-132">Imported response groups cannot be viewed with Lync Server Control Panel or the Response Group Configuration Tool, but can be configured by using Lync Server Management Shell cmdlets.</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="user-experience-during-failover"></a><span data-ttu-id="2f7e4-133">Взаимодействие с пользователем во время перехода на другой ресурс</span><span class="sxs-lookup"><span data-stu-id="2f7e4-133">User Experience During Failover</span></span>

<span data-ttu-id="2f7e4-134">Когда администратор выполняет отработку отказа для резервного пула, действия группы ответа обрабатываются во время и после перехода на другой ресурс, как описано в приведенной ниже таблице.</span><span class="sxs-lookup"><span data-stu-id="2f7e4-134">When an administrator invokes failover to a backup pool, response group activity is handled during and after the failover as described in the following table.</span></span> <span data-ttu-id="2f7e4-135">Первый столбец описывает тип действия, которое может происходить.</span><span class="sxs-lookup"><span data-stu-id="2f7e4-135">The first column describes the type of activity that might be taking place.</span></span> <span data-ttu-id="2f7e4-136">Средний столбец показывает, как обрабатываются все действия в течение короткого времени, при переходе на резервный пул.</span><span class="sxs-lookup"><span data-stu-id="2f7e4-136">The middle column describes how each activity is handled during the brief time that it takes to fail over to the backup pool.</span></span> <span data-ttu-id="2f7e4-137">В последнем столбце показано, как обрабатываются действия в течение длительного времени после завершения процесса отработки отказа и резервного пула для основного пула.</span><span class="sxs-lookup"><span data-stu-id="2f7e4-137">The last column describes how the activity is handled for the duration, after the failover process is complete and the backup pool is standing in for the primary pool.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="2f7e4-138">Во время аварийного восстановления звонки работают по-разному в зависимости от того, были ли группы ответов основного пула импортированы в пул резервного копирования во время восстановления.</span><span class="sxs-lookup"><span data-stu-id="2f7e4-138">During disaster recovery, calls behave differently depending on whether the primary pool response groups were imported to the backup pool during recovery.</span></span> <span data-ttu-id="2f7e4-139">В приведенной ниже таблице ссылки на импортированные группы ответов означают, что группы ответов основного пула были импортированы в пул резервных копий в режиме восстановления после сбоя.</span><span class="sxs-lookup"><span data-stu-id="2f7e4-139">In the following table, references to imported response groups mean that primary pool response groups were imported to the backup pool during disaster recovery mode.</span></span>



</div>

### <a name="failover-is-initiated"></a><span data-ttu-id="2f7e4-140">Отработка отказа инициируется</span><span class="sxs-lookup"><span data-stu-id="2f7e4-140">Failover Is Initiated</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2f7e4-141">Тип звонка или действия пользователя</span><span class="sxs-lookup"><span data-stu-id="2f7e4-141">Type of call or user action</span></span></th>
<th><span data-ttu-id="2f7e4-142">При переходе на другой ресурс</span><span class="sxs-lookup"><span data-stu-id="2f7e4-142">During Failover</span></span></th>
<th><span data-ttu-id="2f7e4-143">После завершения отработки отказа</span><span class="sxs-lookup"><span data-stu-id="2f7e4-143">After Failover Completes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2f7e4-144">Звонки, подключенные к агенту</span><span class="sxs-lookup"><span data-stu-id="2f7e4-144">Calls connected to an agent</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="2f7e4-145">Обычные звонки остаются подключенными.</span><span class="sxs-lookup"><span data-stu-id="2f7e4-145">Regular calls remain connected.</span></span></p></li>
<li><p><span data-ttu-id="2f7e4-146">Анонимные звонки будут разорваны.</span><span class="sxs-lookup"><span data-stu-id="2f7e4-146">Anonymous calls are disconnected.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="2f7e4-147">Обычные звонки остаются подключенными.</span><span class="sxs-lookup"><span data-stu-id="2f7e4-147">Regular calls remain connected.</span></span></p></li>
<li><p><span data-ttu-id="2f7e4-148">Для импортированных групп ответа анонимные звонки, достигнутые пулом резервных копий, остаются подключенными.</span><span class="sxs-lookup"><span data-stu-id="2f7e4-148">For imported response groups, anonymous calls that have reached the backup pool remain connected.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2f7e4-149">Звонки, которые пока не подключены к агенту</span><span class="sxs-lookup"><span data-stu-id="2f7e4-149">In progress calls not yet connected to an agent</span></span></p></td>
<td><p><span data-ttu-id="2f7e4-150">Звонки будут разорваны.</span><span class="sxs-lookup"><span data-stu-id="2f7e4-150">Calls are disconnected.</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="2f7e4-151">Если группы ответа не были импортированы, ни одно из них не находится в этом состоянии.</span><span class="sxs-lookup"><span data-stu-id="2f7e4-151">If response groups were not imported, no calls are in this status.</span></span></p></li>
<li><p><span data-ttu-id="2f7e4-152">Для импортированных групп ответа звонки, достигнутые в пуле резервных копий, остаются подключенными.</span><span class="sxs-lookup"><span data-stu-id="2f7e4-152">For imported response groups, calls that have reached the backup pool remain connected.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2f7e4-153">Новые звонки</span><span class="sxs-lookup"><span data-stu-id="2f7e4-153">New calls</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="2f7e4-154">Звонки будут разорваны.</span><span class="sxs-lookup"><span data-stu-id="2f7e4-154">Calls are disconnected.</span></span></p></li>
<li><p><span data-ttu-id="2f7e4-155">Для импортированных групп ответа звонки подключаются к резервному пулу, но агенты, расположенные в основном пуле, недостижимы.</span><span class="sxs-lookup"><span data-stu-id="2f7e4-155">For imported response groups, calls connect to the backup pool, but agents homed in the primary pool are unreachable.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="2f7e4-156">Если группы ответа не были импортированы, звонки будут разорваны.</span><span class="sxs-lookup"><span data-stu-id="2f7e4-156">If response groups were not imported, calls are disconnected.</span></span></p></li>
<li><p><span data-ttu-id="2f7e4-157">Для импортированных групп ответа вызовы подключаются к резервному пулу.</span><span class="sxs-lookup"><span data-stu-id="2f7e4-157">For imported response groups, calls connect to the backup pool.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2f7e4-158">Вызов агента от имени группы ответа</span><span class="sxs-lookup"><span data-stu-id="2f7e4-158">Agent calls on behalf of response group</span></span></p></td>
<td><p><span data-ttu-id="2f7e4-159">Функция отключена на этом этапе</span><span class="sxs-lookup"><span data-stu-id="2f7e4-159">Feature is disabled during this stage</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="2f7e4-160">Если группы ответа не были импортированы, вызов завершается сбоем.</span><span class="sxs-lookup"><span data-stu-id="2f7e4-160">If response groups were not imported, calls fail.</span></span></p></li>
<li><p><span data-ttu-id="2f7e4-161">Для импортированных групп ответа звонки выполняются успешно.</span><span class="sxs-lookup"><span data-stu-id="2f7e4-161">For imported response groups, calls succeed.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2f7e4-162">Вход агента и информация агента</span><span class="sxs-lookup"><span data-stu-id="2f7e4-162">Agent sign-in and agent information</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="2f7e4-163">Группы агентов, принадлежащие основному пулу, можно просматривать на консоли агента, но агенты не могут войти в систему.</span><span class="sxs-lookup"><span data-stu-id="2f7e4-163">Agent groups owned by the primary pool can be viewed on agent console but agents cannot sign in.</span></span></p></li>
<li><p><span data-ttu-id="2f7e4-164">Группы агентов, владельцами которых является пул резервных копий, можно просмотреть на консоли агента, а агенты могут войти в нее.</span><span class="sxs-lookup"><span data-stu-id="2f7e4-164">Agent groups owned by the backup pool can be viewed on agent console and agents can sign in.</span></span></p></li>
<li><p><span data-ttu-id="2f7e4-165">Импортированные группы агентов отображаются на консоли агента, и агенты могут входить в систему.</span><span class="sxs-lookup"><span data-stu-id="2f7e4-165">Imported agent groups are displayed on agent console and agents can sign in.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="2f7e4-166">Группы агентов, принадлежащие основному пулу, можно просматривать на консоли агента, но агенты не могут войти в систему.</span><span class="sxs-lookup"><span data-stu-id="2f7e4-166">Agent groups owned by the primary pool can be viewed on agent console but agents cannot sign in.</span></span></p></li>
<li><p><span data-ttu-id="2f7e4-167">Группы агентов, владельцами которых является пул резервных копий, можно просмотреть на консоли агента, а агенты могут войти в нее.</span><span class="sxs-lookup"><span data-stu-id="2f7e4-167">Agent groups owned by the backup pool can be viewed on agent console and agents can sign in.</span></span></p></li>
<li><p><span data-ttu-id="2f7e4-168">Импортированные группы агентов отображаются на консоли агента, и агенты могут входить в систему.</span><span class="sxs-lookup"><span data-stu-id="2f7e4-168">Imported agent groups are displayed on agent console and agents can sign in.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2f7e4-169">Настройка группы ответа</span><span class="sxs-lookup"><span data-stu-id="2f7e4-169">Response group configuration</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="2f7e4-170">Группы ответа, принадлежащие основному пулу, можно просмотреть в зависимости от доступности серверной базы данных основного пула, но не для ее изменения.</span><span class="sxs-lookup"><span data-stu-id="2f7e4-170">Response groups owned by the primary pool can be viewed, depending on the availability of the primary pool’s back-end database, but cannot be modified.</span></span></p></li>
<li><p><span data-ttu-id="2f7e4-171">Группы ответа, принадлежащие пулу резервных копий, можно просмотреть и изменить.</span><span class="sxs-lookup"><span data-stu-id="2f7e4-171">Response groups owned by the backup pool can be viewed and modified.</span></span></p></li>
<li><p><span data-ttu-id="2f7e4-172">Импортированные группы ответа нельзя просматривать с помощью панели управления Lync Server или средства настройки группы ответа, но их можно настроить в командлетах командной консоли Lync Server.</span><span class="sxs-lookup"><span data-stu-id="2f7e4-172">Imported response groups cannot be viewed with Lync Server Control Panel or the Response Group Configuration Tool, but can be configured by using Lync Server Management Shell cmdlets.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="2f7e4-173">Группы ответа, принадлежащие основному пулу, можно просмотреть в зависимости от доступности базы данных, но не могут быть изменены.</span><span class="sxs-lookup"><span data-stu-id="2f7e4-173">Response groups owned by the primary pool can be viewed, depending on the availability of the back end database, but cannot be modified.</span></span></p></li>
<li><p><span data-ttu-id="2f7e4-174">Группы ответа, принадлежащие пулу резервных копий, можно просмотреть и изменить.</span><span class="sxs-lookup"><span data-stu-id="2f7e4-174">Response groups owned by the backup pool can be viewed and modified.</span></span></p></li>
<li><p><span data-ttu-id="2f7e4-175">Импортированные группы ответа нельзя просматривать с помощью панели управления Lync Server или средства настройки группы ответа, но их можно настроить в командлетах командной консоли Lync Server.</span><span class="sxs-lookup"><span data-stu-id="2f7e4-175">Imported response groups cannot be viewed with Lync Server Control Panel or the Response Group Configuration Tool, but can be configured by using Lync Server Management Shell cmdlets.</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="user-experience-during-failback"></a><span data-ttu-id="2f7e4-176">Взаимодействие с пользователем при восстановлении из восстановления</span><span class="sxs-lookup"><span data-stu-id="2f7e4-176">User Experience During Failback</span></span>

<span data-ttu-id="2f7e4-177">Когда администратор выполняет восстановление по восстановлению для основного пула, действия группы ответа обрабатываются во время и после восстановления размещения, как описано в приведенной ниже таблице.</span><span class="sxs-lookup"><span data-stu-id="2f7e4-177">When an administrator invokes failback to the primary pool, response group activity is handled during and after the failback as described in the following table.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="2f7e4-178">Во время аварийного восстановления звонки работают по-разному в зависимости от того, были ли группы ответов основного пула импортированы в пул резервного копирования во время восстановления.</span><span class="sxs-lookup"><span data-stu-id="2f7e4-178">During disaster recovery, calls behave differently depending on whether the primary pool response groups were imported to the backup pool during recovery.</span></span> <span data-ttu-id="2f7e4-179">В приведенной ниже таблице ссылки на импортированные группы ответов означают, что группы ответов основного пула были импортированы в пул резервных копий в режиме восстановления после сбоя.</span><span class="sxs-lookup"><span data-stu-id="2f7e4-179">In the following table, references to imported response groups mean that primary pool response groups were imported to the backup pool during disaster recovery mode.</span></span>



</div>

### <a name="call-handling-in-failback"></a><span data-ttu-id="2f7e4-180">Обработка звонков в отказовозвращение</span><span class="sxs-lookup"><span data-stu-id="2f7e4-180">Call Handling in Failback</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2f7e4-181">Тип звонка или действия пользователя</span><span class="sxs-lookup"><span data-stu-id="2f7e4-181">Type of call or user action</span></span></th>
<th><span data-ttu-id="2f7e4-182">Во время восстановления размещения</span><span class="sxs-lookup"><span data-stu-id="2f7e4-182">During Failback</span></span></th>
<th><span data-ttu-id="2f7e4-183">После завершения восстановления</span><span class="sxs-lookup"><span data-stu-id="2f7e4-183">After Failback Completes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2f7e4-184">Звонки, подключенные к агенту</span><span class="sxs-lookup"><span data-stu-id="2f7e4-184">Calls connected to an agent</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="2f7e4-185">Обычные звонки остаются подключенными.</span><span class="sxs-lookup"><span data-stu-id="2f7e4-185">Regular calls remain connected.</span></span></p></li>
<li><p><span data-ttu-id="2f7e4-186">Если группы ответа не были импортированы, анонимные звонки не будут находиться в этом состоянии.</span><span class="sxs-lookup"><span data-stu-id="2f7e4-186">If response groups were not imported, no anonymous calls are in this status.</span></span></p></li>
<li><p><span data-ttu-id="2f7e4-187">Для импортированных групп ответа анонимные звонки остаются подключенными.</span><span class="sxs-lookup"><span data-stu-id="2f7e4-187">For imported response groups, anonymous calls remain connected.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="2f7e4-188">Обычные звонки остаются подключенными.</span><span class="sxs-lookup"><span data-stu-id="2f7e4-188">Regular calls remain connected.</span></span></p></li>
<li><p><span data-ttu-id="2f7e4-189">Если группы ответа не были импортированы, анонимные звонки не будут находиться в этом состоянии.</span><span class="sxs-lookup"><span data-stu-id="2f7e4-189">If response groups were not imported, no anonymous calls are in this status.</span></span></p></li>
<li><p><span data-ttu-id="2f7e4-190">Для импортированных групп ответа анонимные звонки остаются подключенными.</span><span class="sxs-lookup"><span data-stu-id="2f7e4-190">For imported response groups, anonymous calls remain connected.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2f7e4-191">Звонки, которые пока не подключены к агенту</span><span class="sxs-lookup"><span data-stu-id="2f7e4-191">In progress calls not yet connected to an agent</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="2f7e4-192">Если группы ответа не были импортированы, ни одно из них не находится в этом состоянии.</span><span class="sxs-lookup"><span data-stu-id="2f7e4-192">If response groups were not imported, no calls are in this status.</span></span></p></li>
<li><p><span data-ttu-id="2f7e4-193">Для импортированных групп ответа звонки будут разорваны.</span><span class="sxs-lookup"><span data-stu-id="2f7e4-193">For imported response groups, calls will be disconnected.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="2f7e4-194">Если группы ответа не были импортированы, ни одно из них не находится в этом состоянии.</span><span class="sxs-lookup"><span data-stu-id="2f7e4-194">If response groups were not imported, no calls are in this status.</span></span></p></li>
<li><p><span data-ttu-id="2f7e4-195">Для импортированных групп ответа звонки будут разорваны.</span><span class="sxs-lookup"><span data-stu-id="2f7e4-195">For imported response groups, calls will be disconnected.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2f7e4-196">Новые звонки</span><span class="sxs-lookup"><span data-stu-id="2f7e4-196">New calls</span></span></p></td>
<td><p><span data-ttu-id="2f7e4-197">Вызовы подключаются к основному пулу, но агенты, расположенные в основном пуле, недостижимы.</span><span class="sxs-lookup"><span data-stu-id="2f7e4-197">Calls connect to the primary pool, but agents homed in the primary pool are unreachable.</span></span></p></td>
<td><p><span data-ttu-id="2f7e4-198">Звонки подключаются к основному пулу.</span><span class="sxs-lookup"><span data-stu-id="2f7e4-198">Calls connect to the primary pool.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2f7e4-199">Вызов агента от имени группы ответа</span><span class="sxs-lookup"><span data-stu-id="2f7e4-199">Agent calls on behalf of response group</span></span></p></td>
<td><p><span data-ttu-id="2f7e4-200">Функция отключена на этом этапе.</span><span class="sxs-lookup"><span data-stu-id="2f7e4-200">Feature is disabled during this stage.</span></span></p></td>
<td><p><span data-ttu-id="2f7e4-201">Успешные звонки.</span><span class="sxs-lookup"><span data-stu-id="2f7e4-201">Calls succeed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2f7e4-202">Вход агента и информация агента</span><span class="sxs-lookup"><span data-stu-id="2f7e4-202">Agent sign-in and agent information</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="2f7e4-203">Группы агентов, принадлежащие основному пулу, можно просматривать на консоли агента, но агенты не могут войти в систему.</span><span class="sxs-lookup"><span data-stu-id="2f7e4-203">Agent groups owned by the primary pool can be viewed on agent console but agents cannot sign in.</span></span></p></li>
<li><p><span data-ttu-id="2f7e4-204">Группы агентов, владельцами которых является пул резервных копий, можно просмотреть на консоли агента, а агенты могут войти в нее.</span><span class="sxs-lookup"><span data-stu-id="2f7e4-204">Agent groups owned by the backup pool can be viewed on agent console and agents can sign in.</span></span></p></li>
<li><p><span data-ttu-id="2f7e4-205">Импортированные группы агентов отображаются на консоли агента, и агенты могут входить в систему.</span><span class="sxs-lookup"><span data-stu-id="2f7e4-205">Imported agent groups are displayed on agent console and agents can sign in.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="2f7e4-206">Группы агентов, владельцами которых является основной пул, можно просматривать на консоли агента, а агенты — на входе.</span><span class="sxs-lookup"><span data-stu-id="2f7e4-206">Agent groups owned by the primary pool can be viewed on agent console and agents can sign in.</span></span></p></li>
<li><p><span data-ttu-id="2f7e4-207">Группы агентов, владельцами которых является пул резервных копий, можно просмотреть на консоли агента, а агенты могут войти в нее.</span><span class="sxs-lookup"><span data-stu-id="2f7e4-207">Agent groups owned by the backup pool can be viewed on agent console and agents can sign in.</span></span></p></li>
<li><p><span data-ttu-id="2f7e4-208">Импортированные группы агентов не отображаются на консоли агента.</span><span class="sxs-lookup"><span data-stu-id="2f7e4-208">Imported agent groups are not displayed on agent console.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2f7e4-209">Настройка группы ответа</span><span class="sxs-lookup"><span data-stu-id="2f7e4-209">Response group configuration</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="2f7e4-210">Группы ответа, принадлежащие основному пулу, можно просмотреть в зависимости от доступности серверной базы данных основного пула, но не для ее изменения.</span><span class="sxs-lookup"><span data-stu-id="2f7e4-210">Response groups owned by the primary pool can be viewed, depending on the availability of the primary pool’s back-end database, but cannot be modified.</span></span></p></li>
<li><p><span data-ttu-id="2f7e4-211">Группы ответа, принадлежащие пулу резервных копий, можно просмотреть и изменить.</span><span class="sxs-lookup"><span data-stu-id="2f7e4-211">Response groups owned by the backup pool can be viewed and modified.</span></span></p></li>
<li><p><span data-ttu-id="2f7e4-212">Импортированные группы ответа нельзя просматривать с помощью панели управления Lync Server или средства настройки группы ответа, но их можно настроить в командлетах командной консоли Lync Server.</span><span class="sxs-lookup"><span data-stu-id="2f7e4-212">Imported response groups cannot be viewed with Lync Server Control Panel or the Response Group Configuration Tool, but can be configured by using Lync Server Management Shell cmdlets.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="2f7e4-213">Группы ответа, принадлежащие основным пулам, можно просмотреть и изменить.</span><span class="sxs-lookup"><span data-stu-id="2f7e4-213">Response groups owned by the primary pool can be viewed and modified.</span></span></p></li>
<li><p><span data-ttu-id="2f7e4-214">Группы ответа, принадлежащие пулу резервных копий, можно просмотреть и изменить.</span><span class="sxs-lookup"><span data-stu-id="2f7e4-214">Response groups owned by the backup pool can be viewed and modified.</span></span></p></li>
<li><p><span data-ttu-id="2f7e4-215">Импортированные группы ответа нельзя просматривать с помощью панели управления Lync Server или средства настройки группы ответа, но их можно настроить в командлетах командной консоли Lync Server.</span><span class="sxs-lookup"><span data-stu-id="2f7e4-215">Imported response groups cannot be viewed with Lync Server Control Panel or the Response Group Configuration Tool, but can be configured by using Lync Server Management Shell cmdlets.</span></span></p></li>
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

