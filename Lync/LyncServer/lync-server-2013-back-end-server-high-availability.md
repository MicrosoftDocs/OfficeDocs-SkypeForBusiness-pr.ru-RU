---
title: 'Lync Server 2013: высокая доступность внутреннего сервера'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Back End Server high availability
ms:assetid: c559aacb-4e1d-4e78-9582-41f966ad418d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205248(v=OCS.15)
ms:contentKeyID: 48185358
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f7313d11557344586910f6afeeb5422744207023
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044471"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="back-end-server-high-availability-in-lync-server-2013"></a><span data-ttu-id="e9038-102">Высокая доступность внутреннего сервера в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e9038-102">Back End Server high availability in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e9038-103">_**Последнее изменение темы:** 2013-08-12_</span><span class="sxs-lookup"><span data-stu-id="e9038-103">_**Topic Last Modified:** 2013-08-12_</span></span>

<span data-ttu-id="e9038-104">Для обеспечения высокой доступности фоновых серверов можно использовать либо синхронное зеркальное отображение SQL, либо кластеризацию SQL.</span><span class="sxs-lookup"><span data-stu-id="e9038-104">To ensure high availability for your Back End Servers, you can use either synchronous SQL mirroring or SQL clustering.</span></span> <span data-ttu-id="e9038-105">Использование одного из этих решений является необязательным, но рекомендуется для поддержания непрерывности бизнеса в Организации.</span><span class="sxs-lookup"><span data-stu-id="e9038-105">Using one of these solutions optional, but is recommended to maintain your organization's business continuity.</span></span> <span data-ttu-id="e9038-106">Асинхронное зеркальное отображение SQL не поддерживается для обеспечения высокой доступности внутреннего сервера в Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e9038-106">Asynchronous SQL mirroring is not supported for Back End Server high availability in Lync Server 2013.</span></span> <span data-ttu-id="e9038-107">В дальнейшем в данном документе зеркальное отображения SQL будет означать "зеркальное отображение SQL", если явно не будет указано иное.</span><span class="sxs-lookup"><span data-stu-id="e9038-107">In the rest of this document, SQL mirroring means synchronous SQL mirroring, unless otherwise explicitly stated.</span></span>

<span data-ttu-id="e9038-108">Зеркальное отображение SQL можно легко настроить с помощью построителя топологий.</span><span class="sxs-lookup"><span data-stu-id="e9038-108">You can easily set up SQL mirroring with Topology Builder.</span></span> <span data-ttu-id="e9038-109">Для установки отказоустойчивой кластеризации SQL необходимо использовать SQL Server.</span><span class="sxs-lookup"><span data-stu-id="e9038-109">For SQL failover clustering, you must use SQL Server for setup.</span></span>

<span data-ttu-id="e9038-110">Если вы используете зеркальное отображение SQL или кластеризацию SQL в пуле, связанном с другим интерфейсным пулом для аварийного восстановления, следует использовать одно и то же решение высокой доступности в обоих пулах.</span><span class="sxs-lookup"><span data-stu-id="e9038-110">If you use either SQL mirroring or SQL clustering in a pool which is paired with another Front End pool for disaster recovery, you should use the same Back End high availability solution in both pools.</span></span> <span data-ttu-id="e9038-111">Не следует связывать пул с помощью зеркального отображения SQL с пулом, использующим кластеризацию SQL.</span><span class="sxs-lookup"><span data-stu-id="e9038-111">You should not pair a pool using SQL mirroring with a pool using SQL clustering.</span></span>

<span data-ttu-id="e9038-112">При развертывании зеркального отображения SQL все базы данных Lync Server в пуле отображаются зеркально, включая центральное хранилище управления, если оно находится в этом пуле, а также базы данных приложения группы ответа и базы данных приложения парковки вызовов, если эти приложения выполняются в пуле.</span><span class="sxs-lookup"><span data-stu-id="e9038-112">When you deploy SQL mirroring, all Lync Server databases in the pool are mirrored, including the Central Management store, if it is located in this pool, as well as the Response Group application database and the Call Park application database, if those applications are running in the pool.</span></span>

<span data-ttu-id="e9038-p104">При зеркальном отображении SQL нет необходимости использовать общее хранилище для серверов. Каждый сервер хранит свою копию баз данных в локальном хранилище.</span><span class="sxs-lookup"><span data-stu-id="e9038-p104">With SQL mirroring, you do not need to use shared storage for the servers. Each server keeps its copy of the databases in local storage.</span></span>

<span data-ttu-id="e9038-p105">Развернуть зеркальное копирование SQL можно со следящим сервером или без него. Рекомендуется использовать следящий сервер, поскольку он обеспечивает автоматическую отработку отказа внутренним сервером. В противном случае администратор должен запускать отработку отказа вручную. Обратите внимание, что даже если следящий сервер развернут, администратор все равно при необходимости может запустить отработку отказа внутренним сервером вручную.</span><span class="sxs-lookup"><span data-stu-id="e9038-p105">You may choose to deploy SQL mirroring with or without a witness. We recommend using a witness because it enables failover of the Back End Server to be automatic. Otherwise, an administrator must manually invoke failover. Note that even if a witness is deployed, an administrator can manually invoke Back End Server failover, if necessary.</span></span>

<span data-ttu-id="e9038-p106">Одни следящий сервер можно использовать для нескольких пар внутренних серверов. Строгого взаимно-однозначного соответствия между следящими серверами и парами внутренних серверов нет. Развертывания с одним следящим сервером для нескольких пар внутренних серверов менее отказоустойчивы, чем топологии с отдельным следящим сервером для каждой пары внутренних серверов.</span><span class="sxs-lookup"><span data-stu-id="e9038-p106">If you use a witness, you can use a single witness for multiple pairs of Back End Servers. There is no strict 1:1 correspondence between witnesses and pairs of Back End Servers. Deployments that use a single witness for multiple pairs of Back End Servers are not quite as resilient as topologies with a separate witness for each Back End Server pair.</span></span>

<span data-ttu-id="e9038-122">Для получения дополнительных сведений о поддержке кластеризации SQL ознакомьтесь со статьей [Поддержка программного обеспечения баз данных в Lync Server 2013](lync-server-2013-database-software-support.md).</span><span class="sxs-lookup"><span data-stu-id="e9038-122">For more information about SQL clustering support, see [Database software support in Lync Server 2013](lync-server-2013-database-software-support.md).</span></span> <span data-ttu-id="e9038-123">Подробнее о развертывании SQL кластеризации можно узнать в статье [Настройка кластеризации SQL Server для Lync server 2013](lync-server-2013-configure-sql-server-clustering.md).</span><span class="sxs-lookup"><span data-stu-id="e9038-123">For details on deploying SQL clustering, see [Configure SQL Server clustering for Lync Server 2013](lync-server-2013-configure-sql-server-clustering.md).</span></span>

<div>

## <a name="recovery-time-for-automatic-back-end-server-failover-with-sql-mirroring"></a><span data-ttu-id="e9038-124">Время восстановления при отработке отказа автоматического внутреннего сервера с зеркальным отображением SQL</span><span class="sxs-lookup"><span data-stu-id="e9038-124">Recovery Time for Automatic Back End Server Failover with SQL Mirroring</span></span>

<span data-ttu-id="e9038-125">Для автоматической обратной отработки отказа с зеркальным отображением SQL проектирование целевого показателя времени восстановления (RTO) составляет 5 минут.</span><span class="sxs-lookup"><span data-stu-id="e9038-125">For automatic Back End failover with SQL mirroring, the engineering target for recovery time objective (RTO) is 5 minutes.</span></span> <span data-ttu-id="e9038-126">Из-за синхронного зеркального отображения SQL потери данных при отработке отказа внутренним сервером не предполагаются за исключением редких случаев, когда одновременно происходит отказ и серверов переднего плана, и внутреннего сервера во время передачи данных между ними.</span><span class="sxs-lookup"><span data-stu-id="e9038-126">Because of the synchronous SQL mirroring, we do not anticipate data loss during Back End Server failures except in rare occasions when both the Front End Servers and the Back End Server go down simultaneously while data is being moved between the servers.</span></span> <span data-ttu-id="e9038-127">Проектная целевая точка восстановления (RPO) составляет 5 минут.</span><span class="sxs-lookup"><span data-stu-id="e9038-127">The engineering target for recovery point objective (RPO) is 5 minutes.</span></span>

</div>

<div>

## <a name="user-experience-during-back-end-server-failure-with-sql-mirroring"></a><span data-ttu-id="e9038-128">Взаимодействие с пользователем во время внутреннего сбоя сервера с зеркальным отображением SQL</span><span class="sxs-lookup"><span data-stu-id="e9038-128">User Experience During Back End Server Failure with SQL Mirroring</span></span>

<span data-ttu-id="e9038-129">То, каким образом отказ отразится на пользователе, зависит от природы отказа и топологии.</span><span class="sxs-lookup"><span data-stu-id="e9038-129">User experience during a failure depends on the nature of the failure, and on your topology.</span></span>

<span data-ttu-id="e9038-130">Если вы используете зеркальное отображение SQL и не настроили следящий сервер, и основной сервер не проходит, отработка отказа внутреннего сервера происходит автоматически и быстро.</span><span class="sxs-lookup"><span data-stu-id="e9038-130">If you use SQL mirroring and have a witness configured, and the principal fails, Back End Server failover happens automatically and quickly.</span></span> <span data-ttu-id="e9038-131">Активные пользователи не должны заметить особых пауз в своих текущих сеансах.</span><span class="sxs-lookup"><span data-stu-id="e9038-131">Active users should not notice much interruption to their ongoing sessions.</span></span>

<span data-ttu-id="e9038-132">Если следящий сервер на настроен, администратору потребуется некоторое время для проведения отработки отказа вручную.</span><span class="sxs-lookup"><span data-stu-id="e9038-132">If there is no witness configured, it will take some time for the administrator to manually invoke the failover.</span></span> <span data-ttu-id="e9038-133">В этот период активные пользователи могут заметить последствия.</span><span class="sxs-lookup"><span data-stu-id="e9038-133">During that time, active users may be affected.</span></span> <span data-ttu-id="e9038-134">Они продолжат свои сеансы как обычно в течение 30 минут.</span><span class="sxs-lookup"><span data-stu-id="e9038-134">They will continue their sessions as normal for about 30 minutes.</span></span> <span data-ttu-id="e9038-135">Если основной сервер по-прежнему не восстанавливается, или администратор не отключается к резервному копированию, то пользователи переключаются в режим устойчивости, то есть не могут выполнять задачи, требующие постоянного изменения на Lync Server (например, Добавление контакта).</span><span class="sxs-lookup"><span data-stu-id="e9038-135">If the primary is still not restored, or an administrator has not failed over to the backup, then users are switched to Resiliency mode, meaning that they are unable to perform tasks that require a persistent change on Lync Server (such as adding a contact).</span></span>

<span data-ttu-id="e9038-p111">При отказе и главного, и внутреннего зеркальных серверов или при отказе одного из них и следящего сервера внутренний сервер становится недоступным (даже если это основной сервер, продолжающий работать). В этом случае активные пользователи переключаются в режим устойчивости через некоторое время.</span><span class="sxs-lookup"><span data-stu-id="e9038-p111">If both the principal and the mirror Back End Servers fail, or if one of those servers and the witness fails, the Back End Server will become unavailable (even if it is the principal that is still working). In this case, active users are switched to Resiliency mode after some time.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

