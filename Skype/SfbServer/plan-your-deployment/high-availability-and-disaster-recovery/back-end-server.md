---
title: Высокая доступность серверов в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: c559aacb-4e1d-4e78-9582-41f966ad418d
description: Learn about the Back End Server high availability options supported in Skype for Business Server, including AlwaysOn Availability Groups, AlwaysOn Failover Cluster Instances, database mirroring, and SQL failover clustering.
ms.openlocfilehash: bbb55ded0d5ce1127f5dcab829907c533cc6316e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802929"
---
# <a name="back-end-server-high-availability-in-skype-for-business-server"></a><span data-ttu-id="86567-103">Высокая доступность серверов в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="86567-103">Back End Server high availability in Skype for Business Server</span></span>
 
<span data-ttu-id="86567-104">Learn about the Back End Server high availability options supported in Skype for Business Server, including AlwaysOn Availability Groups, AlwaysOn Failover Cluster Instances, database mirroring, and SQL failover clustering.</span><span class="sxs-lookup"><span data-stu-id="86567-104">Learn about the Back End Server high availability options supported in Skype for Business Server, including AlwaysOn Availability Groups, AlwaysOn Failover Cluster Instances, database mirroring, and SQL failover clustering.</span></span>
  
<span data-ttu-id="86567-105">Для повышения высокой доступности для тыловые серверы доступны четыре варианта:</span><span class="sxs-lookup"><span data-stu-id="86567-105">To enhance high availability for your Back End Servers, you have four options:</span></span>
  
- <span data-ttu-id="86567-106">Зеркальное отображение базы данных</span><span class="sxs-lookup"><span data-stu-id="86567-106">Database mirroring</span></span>
    
- <span data-ttu-id="86567-107">группы доступности AlwaysOn;</span><span class="sxs-lookup"><span data-stu-id="86567-107">AlwaysOn Availability Groups</span></span>
    
- <span data-ttu-id="86567-108">Экземпляры кластера для отокрутки AlwaysOn (FCI)</span><span class="sxs-lookup"><span data-stu-id="86567-108">AlwaysOn Failover Cluster Instances (FCI)</span></span>
    
- <span data-ttu-id="86567-109">SQL отбойной кластерии</span><span class="sxs-lookup"><span data-stu-id="86567-109">SQL failover clustering</span></span>
    
<span data-ttu-id="86567-110">Использование одного из этих решений является необязательным, но рекомендуется для поддержания непрерывности бизнеса организации.</span><span class="sxs-lookup"><span data-stu-id="86567-110">Using one of these solutions is optional, but is recommended to maintain your organization's business continuity.</span></span> <span data-ttu-id="86567-111">В противном случае при отопадении одного сервера базы данных может привести к потере важных данных Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="86567-111">Otherwise, having a single database server go down could cause the loss of significant Skype for Business Server data.</span></span> 
  
<span data-ttu-id="86567-112">Зеркальное отражение баз данных можно настроить только с помощью построитель топологий.</span><span class="sxs-lookup"><span data-stu-id="86567-112">You can set up database mirroring using only Topology Builder.</span></span> <span data-ttu-id="86567-113">Для групп доступности AlwaysOn, экземпляров failover Cluster AlwaysOn или кластеров SQL для создания решения высокой доступности используется SQL Server, а затем с помощью построитель топологий можно связать его с пулом переднего уровня.</span><span class="sxs-lookup"><span data-stu-id="86567-113">For AlwaysOn Availability Groups, AlwaysOn Failover Cluster Instances,or SQL failover clustering, you use SQL Server to create the high availability solution, then you can use Topology Builder to associate it with a Front End pool.</span></span>
  
<span data-ttu-id="86567-114">Если для аварийного восстановления используется высокий уровень доступности тыловой части сервера в пуле переднего сервера, сопряженном с другим пулом переднего сервера, следует использовать одно и то же решение для высокой доступности в обоих пулах.</span><span class="sxs-lookup"><span data-stu-id="86567-114">If you use Back End Server high availability on a Front End pool that is paired with another Front End pool for disaster recovery, you should use the same Back End high availability solution in both pools.</span></span> 
  
## <a name="database-mirroring"></a><span data-ttu-id="86567-115">Зеркальное отображение базы данных</span><span class="sxs-lookup"><span data-stu-id="86567-115">Database mirroring</span></span>

<span data-ttu-id="86567-116">Skype для бизнеса Server поддерживает зеркальное отражение с помощью следующего программного обеспечения базы данных:</span><span class="sxs-lookup"><span data-stu-id="86567-116">Skype for Business Server supports mirroring with the following database software:</span></span>
  
- <span data-ttu-id="86567-117">SQL Server 2019 г. и Enterprise Edition, и Standard Edition</span><span class="sxs-lookup"><span data-stu-id="86567-117">SQL Server 2019, both Enterprise Edition and Standard Edition</span></span>

- <span data-ttu-id="86567-118">SQL Server 2017, Enterprise Edition и Standard Edition</span><span class="sxs-lookup"><span data-stu-id="86567-118">SQL Server 2017, both Enterprise Edition and Standard Edition</span></span>

- <span data-ttu-id="86567-119">SQL Server 2016, Enterprise Edition и Standard Edition</span><span class="sxs-lookup"><span data-stu-id="86567-119">SQL Server 2016, both Enterprise Edition and Standard Edition</span></span>

- <span data-ttu-id="86567-120">SQL Server 2014 enterprise Edition и Standard Edition</span><span class="sxs-lookup"><span data-stu-id="86567-120">SQL Server 2014, both Enterprise Edition and Standard Edition</span></span>
    
- <span data-ttu-id="86567-121">SQL Server 2012 с sp2 и CU2, Enterprise Edition и Standard Edition</span><span class="sxs-lookup"><span data-stu-id="86567-121">SQL Server 2012 SP2 and CU2, both Enterprise Edition and Standard Edition</span></span>
    

> [!NOTE]
> <span data-ttu-id="86567-122">SQL зеркальное отражение доступно в Skype для бизнеса Server 2015, но больше не поддерживается в Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="86567-122">SQL Mirroring is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="86567-123">В Skype для бизнеса Server 2019 поддерживаются только группы доступности AlwaysOn, экземпляры кластера для отстройки AlwaysOn и методы SQL кластеров.</span><span class="sxs-lookup"><span data-stu-id="86567-123">The AlwaysOn Availability Groups, AlwaysOn Failover Cluster Instances (FCI), and SQL failover clustering methods are the only supported options with Skype for Business Server 2019.</span></span>
    
<span data-ttu-id="86567-124">Асинхронное зеркальное зеркальное отражение базы данных не поддерживается для высокой доступности серверов в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="86567-124">Asynchronous database mirroring is not supported for Back End Server high availability in Skype for Business Server.</span></span> <span data-ttu-id="86567-125">В остальной части этого документа зеркальное отражение базы данных означает синхронное зеркальное отражение базы данных, если не указано иное явным образом.</span><span class="sxs-lookup"><span data-stu-id="86567-125">In the rest of this document, database mirroring means synchronous database mirroring, unless otherwise explicitly stated.</span></span> 
  
<span data-ttu-id="86567-126">При развертывании зеркального отражания баз данных в пуле переднего сервера зеркально отражаются все базы данных Skype для бизнеса Server в пуле, включая центральное хранилище управления, если оно расположено в этом пуле, а также база данных приложения группы ответа и база данных приложения парковки вызовов, если эти приложения работают в пуле.</span><span class="sxs-lookup"><span data-stu-id="86567-126">When you deploy database mirroring in a Front End pool, all Skype for Business Server databases in the pool are mirrored, including the Central Management store, if it is located in this pool, as well as the Response Group application database and the Call Park application database, if those applications are running in the pool.</span></span> 
  
<span data-ttu-id="86567-127">При зеркальном отражающих базах данных не требуется использовать общее хранилище для серверов.</span><span class="sxs-lookup"><span data-stu-id="86567-127">With database mirroring, you do not need to use shared storage for the servers.</span></span> <span data-ttu-id="86567-128">Каждый сервер хранит свою копию баз данных в локальном хранилище.</span><span class="sxs-lookup"><span data-stu-id="86567-128">Each server keeps its copy of the databases in local storage.</span></span> 
  
<span data-ttu-id="86567-129">Можно развернуть зеркальное отражение базы данных с помощью свидетеля или без него.</span><span class="sxs-lookup"><span data-stu-id="86567-129">You may choose to deploy database mirroring with or without a witness.</span></span> <span data-ttu-id="86567-130">Рекомендуется использовать следящий сервер, поскольку он обеспечивает автоматическую отработку отказа внутренним сервером.</span><span class="sxs-lookup"><span data-stu-id="86567-130">We recommend using a witness because it enables failover of the Back End Server to be automatic.</span></span> <span data-ttu-id="86567-131">В противном случае администратор должен запускать отработку отказа вручную.</span><span class="sxs-lookup"><span data-stu-id="86567-131">Otherwise, an administrator must manually invoke failover.</span></span> <span data-ttu-id="86567-132">Обратите внимание, что даже если следящий сервер развернут, администратор все равно при необходимости может запустить отработку отказа внутренним сервером вручную.</span><span class="sxs-lookup"><span data-stu-id="86567-132">Note that even if a witness is deployed, an administrator can manually invoke Back End Server failover, if necessary.</span></span>
  
<span data-ttu-id="86567-p107">Одни следящий сервер можно использовать для нескольких пар внутренних серверов. Строгого взаимно-однозначного соответствия между следящими серверами и парами внутренних серверов нет. Развертывания с одним следящим сервером для нескольких пар внутренних серверов менее отказоустойчивы, чем топологии с отдельным следящим сервером для каждой пары внутренних серверов.</span><span class="sxs-lookup"><span data-stu-id="86567-p107">If you use a witness, you can use a single witness for multiple pairs of Back End Servers. There is no strict 1:1 correspondence between witnesses and pairs of Back End Servers. Deployments that use a single witness for multiple pairs of Back End Servers are not quite as resilient as topologies with a separate witness for each Back End Server pair.</span></span> 
  
### <a name="guidelines-for-planning-back-end-server-mirroring"></a><span data-ttu-id="86567-136">Рекомендации по планированию зеркального зеркального отражания серверов</span><span class="sxs-lookup"><span data-stu-id="86567-136">Guidelines for planning Back End Server mirroring</span></span>

<span data-ttu-id="86567-137">В целом, для настройки зеркального отображения SQL между двумя внутренними серверами с ресурсом-свидетелем требуется следующее:</span><span class="sxs-lookup"><span data-stu-id="86567-137">In general, setting up SQL mirroring between the two Back End Servers with a witness requires the following:</span></span>
  
- <span data-ttu-id="86567-138">Версия сервера-SQL Server должна поддерживать SQL зеркальное отражение.</span><span class="sxs-lookup"><span data-stu-id="86567-138">The primary server's version of SQL Server must support SQL mirroring.</span></span>
    
- <span data-ttu-id="86567-139">На основном ресурсе, зеркальном ресурсе и ресурсе-свидетеле (если развертывается) должна быть установлена одна и та же версия SQL Server.</span><span class="sxs-lookup"><span data-stu-id="86567-139">The primary, mirror, and the witness (if deployed) must have the same version of SQL Server.</span></span> 
    
- <span data-ttu-id="86567-p108">На основном и зеркальном ресурсах должен быть установлен один и тот же выпуск SQL Server. На ресурсе-свидетеле может быть установлен другой выпуск.</span><span class="sxs-lookup"><span data-stu-id="86567-p108">The primary and the mirror must have the same edition of SQL Server. The witness may have a different edition.</span></span>
    
<span data-ttu-id="86567-142">Чтобы SQL с точки зрения того, какие SQL версий поддерживаются для роли свидетеля, см. в подмесье  ["Свидетель](https://go.microsoft.com/fwlink/p/?LinkId=247345) зеркального библиотека MSDN.</span><span class="sxs-lookup"><span data-stu-id="86567-142">For SQL best practices in terms of what SQL versions are supported for a Witness role, see  ["Database Mirroring Witness"](https://go.microsoft.com/fwlink/p/?LinkId=247345) in the MSDN Library.</span></span>
  
<span data-ttu-id="86567-143">Прежде чем настраивать зеркальное отражение сервера, необходимо правильно SQL базы данных.</span><span class="sxs-lookup"><span data-stu-id="86567-143">Before configuring server mirroring, you must first set up SQL database permissions correctly.</span></span> <span data-ttu-id="86567-144">Подробные сведения см. в подстройки "Настройка учетных записей входа для зеркального управления базами данных или групп [доступности AlwaysOn (SQL Server)".](https://go.microsoft.com/fwlink/p/?LinkId=268454)</span><span class="sxs-lookup"><span data-stu-id="86567-144">For details, see  ["Set Up Login Accounts for Database Mirroring or AlwaysOn Availability Groups (SQL Server)"](https://go.microsoft.com/fwlink/p/?LinkId=268454).</span></span>
  
<span data-ttu-id="86567-p110">При использовании зеркального отображения SQL режим восстановления базы данных всегда задан как **Полный**, т. е. вы должны регулярно внимательно следить за размером журнала транзакций и журналов транзакций резервного копирования, чтобы предотвратить нехватку места на диске на фоновых серверах. Частота резервного копирования журналов транзакций зависит от скорости роста журналов, которая в свою очередь зависит от транзакций баз данных в результате действий пользователей в пуле переднего плана. Рекомендуется определить ожидаемую скорость роста журналов для полезной нагрузки развертывания Lync, чтобы вы могли правильно провести планирование. В следующих статьях представлены дополнительные сведения об управлении резервным копированием и журналами SQL:</span><span class="sxs-lookup"><span data-stu-id="86567-p110">With SQL mirroring, database recovery mode is always set to **Full**, which means you must closely monitor transaction log size and back up transaction logs on a regular basis to avoid running out of disk space on the Back End Servers. The frequency of transaction log backups depends on the log growth rate, which in turn depends on database transactions incurred by user activities on the Front End pool. We recommend that you determine how much transaction log growth is expected for your Lync deployment workload so that you can do the planning accordingly. The following articles provide additional information on SQL backup and log management:</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="86567-149">Использование построитель топологий или cmdlets для SQL зеркального SQL поддерживается только в том случае, если основной, зеркальный и свидетельный (при желании) серверы принадлежат одному домену.</span><span class="sxs-lookup"><span data-stu-id="86567-149">Using Topology Builder or cmdlets to set up and remove SQL mirroring is supported only when the primary, mirror, and witness (if desired) servers all belong to the same domain.</span></span> <span data-ttu-id="86567-150">Если необходимо настроить зеркальное отображение SQL для серверов в других доменах, см. документацию по SQL Server.</span><span class="sxs-lookup"><span data-stu-id="86567-150">If you want to set up SQL mirroring among servers in different domains, see your SQL Server documentation.</span></span> 

> [!NOTE]
> <span data-ttu-id="86567-151">SQL зеркальное отражение доступно в Skype для бизнеса Server 2015, но больше не поддерживается в Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="86567-151">SQL Mirroring is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="86567-152">В Skype для бизнеса Server 2019 предпочтительнее использовать группы доступности AlwaysOn, экземпляры кластера для отстройки AlwaysOn и SQL кластеров.</span><span class="sxs-lookup"><span data-stu-id="86567-152">The  AlwaysOn Availability Groups, AlwaysOn Failover Cluster Instances (FCI), and SQL failover clustering methods are preferred with Skype for Business Server 2019.</span></span>
  
### <a name="recovery-time-for-automatic-back-end-server-failover-with-database-mirroring"></a><span data-ttu-id="86567-153">Время восстановления для автоматической отключки тыл сервера с зеркальным отражением базы данных</span><span class="sxs-lookup"><span data-stu-id="86567-153">Recovery time for automatic Back End Server failover with database mirroring</span></span>

<span data-ttu-id="86567-154">Для автоматической отладки тылов с зеркальным отражением базы данных целевое время восстановления (RTO) составляет 5 минут.</span><span class="sxs-lookup"><span data-stu-id="86567-154">For automatic Back End failover with database mirroring, the engineering target for recovery time objective (RTO) is 5 minutes.</span></span> <span data-ttu-id="86567-155">Из-за синхронного зеркального отражания базы данных мы не ожидаем потери данных во время сбоев тыловой части сервера, за исключением редких случаев одновременного отказа серверов переднего и заднего серверов во время передачи данных между серверами.</span><span class="sxs-lookup"><span data-stu-id="86567-155">Because of the synchronous database mirroring, we do not anticipate data loss during Back End Server failures except in rare occasions when both the Front End Servers and the Back End Server go down simultaneously while data is being moved between the servers.</span></span> <span data-ttu-id="86567-156">Проектная целевая точка восстановления (RPO) составляет 5 минут.</span><span class="sxs-lookup"><span data-stu-id="86567-156">The engineering target for recovery point objective (RPO) is 5 minutes.</span></span>
  
### <a name="user-experience-during-back-end-server-failure-with-database-mirroring"></a><span data-ttu-id="86567-157">Пользовательский интерфейс при сбое тыловом сервере с зеркальным зеркальным отражением базы данных</span><span class="sxs-lookup"><span data-stu-id="86567-157">User experience during Back End Server failure with database mirroring</span></span>

<span data-ttu-id="86567-158">То, каким образом отказ отразится на пользователе, зависит от природы отказа и топологии.</span><span class="sxs-lookup"><span data-stu-id="86567-158">User experience during a failure depends on the nature of the failure, and on your topology.</span></span>
  
<span data-ttu-id="86567-159">Если вы используете зеркальное отражение базы данных и настроили свидетель и основной сервер завершится сбой, отключка на тыловом сервере происходит автоматически и быстро.</span><span class="sxs-lookup"><span data-stu-id="86567-159">If you use database mirroring and have a witness configured, and the principal fails, Back End Server failover happens automatically and quickly.</span></span> <span data-ttu-id="86567-160">Активные пользователи не должны заметить особых пауз в своих текущих сеансах.</span><span class="sxs-lookup"><span data-stu-id="86567-160">Active users should not notice much interruption to their ongoing sessions.</span></span>
  
<span data-ttu-id="86567-161">Если следящий сервер на настроен, администратору потребуется некоторое время для проведения отработки отказа вручную.</span><span class="sxs-lookup"><span data-stu-id="86567-161">If there is no witness configured, it will take some time for the administrator to manually invoke the failover.</span></span> <span data-ttu-id="86567-162">В этот период активные пользователи могут заметить последствия.</span><span class="sxs-lookup"><span data-stu-id="86567-162">During that time, active users may be affected.</span></span> <span data-ttu-id="86567-163">Они продолжат свои сеансы как обычно в течение 30 минут.</span><span class="sxs-lookup"><span data-stu-id="86567-163">They will continue their sessions as normal for about 30 minutes.</span></span> <span data-ttu-id="86567-164">Если основной сервер по-прежнему не восстановлен или администратор не переключился на резервную копию, пользователи переключаются в режим устойчивости, что означает, что они не могут выполнять задачи, которые требуют постоянного изменения в Lync Server (например, добавление контакта).</span><span class="sxs-lookup"><span data-stu-id="86567-164">If the primary is still not restored, or an administrator has not failed over to the backup, then users are switched to Resiliency mode, meaning that they are unable to perform tasks that require a persistent change on Lync Server (such as adding a contact).</span></span>
  
<span data-ttu-id="86567-p116">При отказе и главного, и внутреннего зеркальных серверов или при отказе одного из них и следящего сервера внутренний сервер становится недоступным (даже если это основной сервер, продолжающий работать). В этом случае активные пользователи переключаются в режим устойчивости через некоторое время.</span><span class="sxs-lookup"><span data-stu-id="86567-p116">If both the principal and the mirror Back End Servers fail, or if one of those servers and the witness fails, the Back End Server will become unavailable (even if it is the principal that is still working). In this case, active users are switched to Resiliency mode after some time.</span></span>
  
## <a name="alwayson-availability-groups-and-alwayson-failover-cluster-instances"></a><span data-ttu-id="86567-167">Группы доступности AlwaysOn и экземпляры кластера для отстройки AlwaysOn</span><span class="sxs-lookup"><span data-stu-id="86567-167">AlwaysOn Availability Groups and AlwaysOn Failover Cluster Instances</span></span>

<span data-ttu-id="86567-168">Skype для бизнеса Server поддерживает группы доступности AlwaysOn только как активные, так и пассивные, а не активные.</span><span class="sxs-lookup"><span data-stu-id="86567-168">Skype for Business Server supports AlwaysOn Availability Groups only as active/passive, not active/active.</span></span> 
  
<span data-ttu-id="86567-169">Чтобы использовать группы доступности AlwaysOn или экземпляры отбойного кластера AlwaysOn, сначала необходимо использовать SQL Server для настройки решения высокой доступности.</span><span class="sxs-lookup"><span data-stu-id="86567-169">To use AlwaysOn Availability Groups or AlwaysOn Failover Cluster Instances, you first use SQL Server to set up and configure the high availability solution.</span></span> <span data-ttu-id="86567-170">Затем можно использовать построитель топологий, чтобы связать его с пулом переднего входа.</span><span class="sxs-lookup"><span data-stu-id="86567-170">You can then use Topology Builder to associate it with a Front End pool.</span></span>

<span data-ttu-id="86567-171">Skype для бизнеса Server поддерживает AlwaysOn с помощью следующего программного обеспечения базы данных:</span><span class="sxs-lookup"><span data-stu-id="86567-171">Skype for Business Server supports AlwaysOn with the following database software:</span></span>

- <span data-ttu-id="86567-172">SQL Server 2019 Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="86567-172">SQL Server 2019 Enterprise Edition</span></span>

- <span data-ttu-id="86567-173">SQL Server 2019 Standard Edition с ограничениями см. примечание ниже</span><span class="sxs-lookup"><span data-stu-id="86567-173">SQL Server 2019 Standard Edition with limitations, see note below</span></span>

- <span data-ttu-id="86567-174">SQL Server 2017 Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="86567-174">SQL Server 2017 Enterprise Edition</span></span>

- <span data-ttu-id="86567-175">SQL Server 2017 Standard Edition с ограничениями см. примечание ниже</span><span class="sxs-lookup"><span data-stu-id="86567-175">SQL Server 2017 Standard Edition with limitations, see note below</span></span>

- <span data-ttu-id="86567-176">SQL Server 2016 Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="86567-176">SQL Server 2016 Enterprise Edition</span></span>

- <span data-ttu-id="86567-177">SQL Server 2016 Standard Edition с ограничениями см. примечание ниже</span><span class="sxs-lookup"><span data-stu-id="86567-177">SQL Server 2016 Standard Edition with limitations, see note below</span></span>

- <span data-ttu-id="86567-178">SQL Server 2014 Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="86567-178">SQL Server 2014 Enterprise Edition</span></span>
    
- <span data-ttu-id="86567-179">SQL Server 2012 с sp2 и CU2 Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="86567-179">SQL Server 2012 SP2 and CU2 Enterprise Edition</span></span>

> [!NOTE]
> <span data-ttu-id="86567-180">SQL Server Версии 2019, 2017 и 2016 поддерживаются в Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="86567-180">SQL Server 2019, 2017, and 2016 are the only versions supported by Skype for Business Server 2019.</span></span>

> [!NOTE]
> <span data-ttu-id="86567-181">Группы доступности Always  On не поддерживаются в выпусках SQL 2016, 2017 и 2019 Standard Edition, но можно использовать экземпляры кластера Always On.</span><span class="sxs-lookup"><span data-stu-id="86567-181">Always On Availability Groups is **not** supported in SQL 2016, 2017, and 2019 Standard Editions but you can use Always On Failover Cluster Instances.</span></span> <span data-ttu-id="86567-182">Дополнительные см. в выпусках и [поддерживаемых SQL Server 2016.](https://docs.microsoft.com/sql/sql-server/editions-and-components-of-sql-server-2016?view=sql-server-2017)</span><span class="sxs-lookup"><span data-stu-id="86567-182">See [Editions and supported features of SQL Server 2016](https://docs.microsoft.com/sql/sql-server/editions-and-components-of-sql-server-2016?view=sql-server-2017) to learn more.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="86567-183">Имена экземпляров для нескольких экземпляров группы доступности AlwaysOn должны быть одинаковыми.</span><span class="sxs-lookup"><span data-stu-id="86567-183">Instance names for multiple AlwaysOn Availability Group instances must be the same.</span></span> 
  
<span data-ttu-id="86567-184">Действия по развертыванию групп доступности AlwaysOn см. в подгруппе "Развертывание группы доступности [AlwaysOn"](../../deploy/deploy-high-availability-and-disaster-recovery/alwayson-availability-group.md)на тыловом сервере в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="86567-184">For steps for deploying AlwaysOn Availability Groups, see [Deploy an AlwaysOn Availability Group on a Back End Server in Skype for Business Server](../../deploy/deploy-high-availability-and-disaster-recovery/alwayson-availability-group.md).</span></span>
  
## <a name="sql-server-failover-clustering"></a><span data-ttu-id="86567-185">SQL Server отбойной кластерии</span><span class="sxs-lookup"><span data-stu-id="86567-185">SQL Server Failover Clustering</span></span>

<span data-ttu-id="86567-186">Skype для бизнеса Server поддерживает SQL Server кластеров с помощью следующего программного обеспечения базы данных:</span><span class="sxs-lookup"><span data-stu-id="86567-186">Skype for Business Server supports SQL Server failover clustering with the following database software:</span></span>
  
- <span data-ttu-id="86567-187">SQL Server 2019 г. и Enterprise Edition, и Standard Edition</span><span class="sxs-lookup"><span data-stu-id="86567-187">SQL Server 2019, both Enterprise Edition and Standard Edition</span></span>

- <span data-ttu-id="86567-188">SQL Server 2017, Enterprise Edition и Standard Edition</span><span class="sxs-lookup"><span data-stu-id="86567-188">SQL Server 2017, both Enterprise Edition and Standard Edition</span></span>

- <span data-ttu-id="86567-189">SQL Server 2016, Enterprise Edition и Standard Edition</span><span class="sxs-lookup"><span data-stu-id="86567-189">SQL Server 2016, both Enterprise Edition and Standard Edition</span></span>

- <span data-ttu-id="86567-190">SQL Server 2014 enterprise Edition и Standard Edition</span><span class="sxs-lookup"><span data-stu-id="86567-190">SQL Server 2014, both Enterprise Edition and Standard Edition</span></span>
    
- <span data-ttu-id="86567-191">SQL Server 2012 с sp2 и CU2, Enterprise Edition и Standard Edition</span><span class="sxs-lookup"><span data-stu-id="86567-191">SQL Server 2012 SP2 and CU2, both Enterprise Edition and Standard Edition</span></span>

<span data-ttu-id="86567-192">Чтобы использовать SQL кластеров, необходимо сначала настроить и настроить кластер SQL Server перед развертыванием пула переднего входа.</span><span class="sxs-lookup"><span data-stu-id="86567-192">To use SQL failover clustering, you should first set up and configure the SQL Server cluster before deploying your Front End pool.</span></span> <span data-ttu-id="86567-193">Практические инструкции и инструкции по настройке для отстающих кластеров в SQL Server 2012 см. в . [https://technet.microsoft.com/library/hh231721.aspx](https://technet.microsoft.com/library/hh231721.aspx)</span><span class="sxs-lookup"><span data-stu-id="86567-193">For best practices and setup instructions for failover clustering in SQL Server 2012, see [https://technet.microsoft.com/library/hh231721.aspx](https://technet.microsoft.com/library/hh231721.aspx).</span></span>

> [!NOTE]
> <span data-ttu-id="86567-194">SQL Server 2019, 2017 и SQL Server 2016 — единственные версии, поддерживаемые Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="86567-194">SQL Server 2019, 2017, and SQL Server 2016 are the only versions supported by Skype for Business Server 2019.</span></span>
    
<span data-ttu-id="86567-195">Чтобы использовать SQL кластеров, необходимо сначала настроить и настроить кластер SQL Server перед развертыванием пула переднего входа.</span><span class="sxs-lookup"><span data-stu-id="86567-195">To use SQL failover clustering, you should first set up and configure the SQL Server cluster before deploying your Front End pool.</span></span> <span data-ttu-id="86567-196">Практические инструкции и инструкции по настройке для отстающих кластеров в SQL Server 2014 и 2016 годах см. в . [https://technet.microsoft.com/library/hh231721.aspx](https://technet.microsoft.com/library/hh231721.aspx)</span><span class="sxs-lookup"><span data-stu-id="86567-196">For best practices and setup instructions for failover clustering in SQL Server 2014 and 2016, see [https://technet.microsoft.com/library/hh231721.aspx](https://technet.microsoft.com/library/hh231721.aspx).</span></span> <span data-ttu-id="86567-197">О кластере от сбойов в SQL Server 2008 см. в [https://technet.microsoft.com/library/ms189134(v=sql.105).aspx](https://technet.microsoft.com/library/ms189134%28v=sql.105%29.aspx) .</span><span class="sxs-lookup"><span data-stu-id="86567-197">For failover clustering in SQL Server 2008, see [https://technet.microsoft.com/library/ms189134(v=sql.105).aspx](https://technet.microsoft.com/library/ms189134%28v=sql.105%29.aspx).</span></span>
  
<span data-ttu-id="86567-198">При установке SQL Server следует установить SQL Server Management Studio для управления расположениями баз данных и файлов журналов.</span><span class="sxs-lookup"><span data-stu-id="86567-198">When you install SQL Server, you should install SQL Server Management Studio to manage the locations for database and log file locations.</span></span> <span data-ttu-id="86567-199">SQL Server Management Studio устанавливается в качестве дополнительного компонента при установке SQL Server.</span><span class="sxs-lookup"><span data-stu-id="86567-199">SQL Server Management Studio is installed as an optional component when you install SQL Server.</span></span>
  
