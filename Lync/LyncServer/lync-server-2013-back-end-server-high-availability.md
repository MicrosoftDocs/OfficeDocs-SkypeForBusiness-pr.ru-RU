---
title: 'Lync Server 2013: сервер, на котором выйдет высокий уровень доступности'
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
ms.openlocfilehash: 5708212aa2eb30cfcc3c3d40894ca2340475bd8b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740139"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="back-end-server-high-availability-in-lync-server-2013"></a><span data-ttu-id="711b5-102">Высокий уровень доступности серверной части в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="711b5-102">Back End Server high availability in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="711b5-103">_**Тема последнего изменения:** 2013-08-12_</span><span class="sxs-lookup"><span data-stu-id="711b5-103">_**Topic Last Modified:** 2013-08-12_</span></span>

<span data-ttu-id="711b5-104">Для обеспечения высокой доступности серверных серверов вы можете использовать либо синхронное зеркальное отражение SQL, либо кластеризацию SQL.</span><span class="sxs-lookup"><span data-stu-id="711b5-104">To ensure high availability for your Back End Servers, you can use either synchronous SQL mirroring or SQL clustering.</span></span> <span data-ttu-id="711b5-105">Использовать одно из этих решений необязательно, но рекомендуется для обеспечения бесперебойной деятельности Организации.</span><span class="sxs-lookup"><span data-stu-id="711b5-105">Using one of these solutions optional, but is recommended to maintain your organization's business continuity.</span></span> <span data-ttu-id="711b5-106">Асинхронное зеркальное отображение SQL не поддерживается для обеспечения высокой доступности серверной части в Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="711b5-106">Asynchronous SQL mirroring is not supported for Back End Server high availability in Lync Server 2013.</span></span> <span data-ttu-id="711b5-107">В оставшейся части документа SQL Mirror — это синхронное зеркальное отображение SQL, если явно не указано иное.</span><span class="sxs-lookup"><span data-stu-id="711b5-107">In the rest of this document, SQL mirroring means synchronous SQL mirroring, unless otherwise explicitly stated.</span></span>

<span data-ttu-id="711b5-108">Зеркальное отображение SQL можно легко настроить с помощью Topology Builder.</span><span class="sxs-lookup"><span data-stu-id="711b5-108">You can easily set up SQL mirroring with Topology Builder.</span></span> <span data-ttu-id="711b5-109">Для настройки отказоустойчивой кластеризации SQL необходимо использовать SQL Server.</span><span class="sxs-lookup"><span data-stu-id="711b5-109">For SQL failover clustering, you must use SQL Server for setup.</span></span>

<span data-ttu-id="711b5-110">Если вы используете зеркальное отображение SQL или кластеризацию SQL в пуле, связанном с другим пулом переднего плана для аварийного восстановления, вы должны использовать одно и то же решение с высокой доступностью для обоих пулов.</span><span class="sxs-lookup"><span data-stu-id="711b5-110">If you use either SQL mirroring or SQL clustering in a pool which is paired with another Front End pool for disaster recovery, you should use the same Back End high availability solution in both pools.</span></span> <span data-ttu-id="711b5-111">Не следует связывать пул с помощью зеркального отображения SQL с пулом с использованием кластеризации SQL.</span><span class="sxs-lookup"><span data-stu-id="711b5-111">You should not pair a pool using SQL mirroring with a pool using SQL clustering.</span></span>

<span data-ttu-id="711b5-112">При развертывании зеркального отображения SQL все базы данных Lync Server в пуле будут зеркально отображены, в том числе в этом пуле, а также в базе данных приложения группы ответа и базе данных приложения для приостановки вызова, если эти приложения запущены в пуле.</span><span class="sxs-lookup"><span data-stu-id="711b5-112">When you deploy SQL mirroring, all Lync Server databases in the pool are mirrored, including the Central Management store, if it is located in this pool, as well as the Response Group application database and the Call Park application database, if those applications are running in the pool.</span></span>

<span data-ttu-id="711b5-113">С помощью зеркального отображения SQL вам не нужно использовать общее хранилище для серверов.</span><span class="sxs-lookup"><span data-stu-id="711b5-113">With SQL mirroring, you do not need to use shared storage for the servers.</span></span> <span data-ttu-id="711b5-114">На каждом сервере копия баз данных хранится в локальном хранилище.</span><span class="sxs-lookup"><span data-stu-id="711b5-114">Each server keeps its copy of the databases in local storage.</span></span>

<span data-ttu-id="711b5-115">Вы можете выбрать развертывание зеркального отображения SQL с участием следящего сервера или без него.</span><span class="sxs-lookup"><span data-stu-id="711b5-115">You may choose to deploy SQL mirroring with or without a witness.</span></span> <span data-ttu-id="711b5-116">Наличие следящего сервера является предпочтительным, поскольку обеспечивает автоматическую отработку отказа внутреннего сервера.</span><span class="sxs-lookup"><span data-stu-id="711b5-116">We recommend using a witness because it enables failover of the Back End Server to be automatic.</span></span> <span data-ttu-id="711b5-117">В противном случае администратор должен запускать отработку отказа вручную.</span><span class="sxs-lookup"><span data-stu-id="711b5-117">Otherwise, an administrator must manually invoke failover.</span></span> <span data-ttu-id="711b5-118">Обратите внимание на то, что даже в случае развертывания следящего сервера администратор может при необходимости запустить отработку отказа внутреннего сервера вручную.</span><span class="sxs-lookup"><span data-stu-id="711b5-118">Note that even if a witness is deployed, an administrator can manually invoke Back End Server failover, if necessary.</span></span>

<span data-ttu-id="711b5-p106">Одни следящий сервер можно использовать для нескольких пар внутренних серверов. Строгого взаимно-однозначного соответствия между следящими серверами и парами внутренних серверов нет. Развертывания с одним следящим сервером для нескольких пар внутренних серверов менее отказоустойчивы, чем топологии с отдельным следящим сервером для каждой пары внутренних серверов.</span><span class="sxs-lookup"><span data-stu-id="711b5-p106">If you use a witness, you can use a single witness for multiple pairs of Back End Servers. There is no strict 1:1 correspondence between witnesses and pairs of Back End Servers. Deployments that use a single witness for multiple pairs of Back End Servers are not quite as resilient as topologies with a separate witness for each Back End Server pair.</span></span>

<span data-ttu-id="711b5-122">Дополнительные сведения о поддержке кластеризации SQL можно найти [в разделе Поддержка программного обеспечения баз данных в Lync Server 2013](lync-server-2013-database-software-support.md).</span><span class="sxs-lookup"><span data-stu-id="711b5-122">For more information about SQL clustering support, see [Database software support in Lync Server 2013](lync-server-2013-database-software-support.md).</span></span> <span data-ttu-id="711b5-123">Подробнее о том, как развертывать кластеризацию SQL, можно найти в разделе [Настройка кластеризации SQL Server для Lync server 2013](lync-server-2013-configure-sql-server-clustering.md).</span><span class="sxs-lookup"><span data-stu-id="711b5-123">For details on deploying SQL clustering, see [Configure SQL Server clustering for Lync Server 2013](lync-server-2013-configure-sql-server-clustering.md).</span></span>

<div>

## <a name="recovery-time-for-automatic-back-end-server-failover-with-sql-mirroring"></a><span data-ttu-id="711b5-124">Время восстановления для автоматических переходов на резервный сервер с помощью зеркального отображения SQL</span><span class="sxs-lookup"><span data-stu-id="711b5-124">Recovery Time for Automatic Back End Server Failover with SQL Mirroring</span></span>

<span data-ttu-id="711b5-125">При автоматическом переходе на другой ресурс с помощью зеркального отображения SQL Целевая цель обслуживания для восстановления (RTO) составляет 5 минут.</span><span class="sxs-lookup"><span data-stu-id="711b5-125">For automatic Back End failover with SQL mirroring, the engineering target for recovery time objective (RTO) is 5 minutes.</span></span> <span data-ttu-id="711b5-126">Благодаря синхронному зеркальному отображению SQL мы не предполагаем потерь данных во время сбоев сервера за пределами, кроме случаев, когда оба внешних сервера и сервер переходят вниз во время перемещения данных между серверами.</span><span class="sxs-lookup"><span data-stu-id="711b5-126">Because of the synchronous SQL mirroring, we do not anticipate data loss during Back End Server failures except in rare occasions when both the Front End Servers and the Back End Server go down simultaneously while data is being moved between the servers.</span></span> <span data-ttu-id="711b5-127">Техническое плановое значение целевого срока восстановления (RPO) составляет 5 минут.</span><span class="sxs-lookup"><span data-stu-id="711b5-127">The engineering target for recovery point objective (RPO) is 5 minutes.</span></span>

</div>

<div>

## <a name="user-experience-during-back-end-server-failure-with-sql-mirroring"></a><span data-ttu-id="711b5-128">Взаимодействие с пользователем во время обратного сбоя сервера с помощью зеркального отображения SQL</span><span class="sxs-lookup"><span data-stu-id="711b5-128">User Experience During Back End Server Failure with SQL Mirroring</span></span>

<span data-ttu-id="711b5-129">То, каким образом отказ отразится на пользователе, зависит от природы отказа и топологии.</span><span class="sxs-lookup"><span data-stu-id="711b5-129">User experience during a failure depends on the nature of the failure, and on your topology.</span></span>

<span data-ttu-id="711b5-130">Если вы используете SQL Mirroring и на нем установлен следящий сервер, а основной сервер не проходит, отработка отказа сервера происходит автоматически и быстро.</span><span class="sxs-lookup"><span data-stu-id="711b5-130">If you use SQL mirroring and have a witness configured, and the principal fails, Back End Server failover happens automatically and quickly.</span></span> <span data-ttu-id="711b5-131">Активные пользователи не должны заметить существенного прерывания текущих сеансов.</span><span class="sxs-lookup"><span data-stu-id="711b5-131">Active users should not notice much interruption to their ongoing sessions.</span></span>

<span data-ttu-id="711b5-132">Если следящий сервер не настроен, администратору потребуется некоторое время для проведения отработки отказа вручную.</span><span class="sxs-lookup"><span data-stu-id="711b5-132">If there is no witness configured, it will take some time for the administrator to manually invoke the failover.</span></span> <span data-ttu-id="711b5-133">В этот период активные пользователи могут заметить последствия.</span><span class="sxs-lookup"><span data-stu-id="711b5-133">During that time, active users may be affected.</span></span> <span data-ttu-id="711b5-134">Они продолжат свои сеансы как обычно в течение 30 минут.</span><span class="sxs-lookup"><span data-stu-id="711b5-134">They will continue their sessions as normal for about 30 minutes.</span></span> <span data-ttu-id="711b5-135">Если основной сервер по-прежнему не восстановлен или не прошел резервное копирование, пользователи переключаются в режим устойчивости, то есть не могут выполнять задачи, требующие постоянного изменения на Lync Server (например, Добавление контакта).</span><span class="sxs-lookup"><span data-stu-id="711b5-135">If the primary is still not restored, or an administrator has not failed over to the backup, then users are switched to Resiliency mode, meaning that they are unable to perform tasks that require a persistent change on Lync Server (such as adding a contact).</span></span>

<span data-ttu-id="711b5-p111">При отказе и главного, и внутреннего зеркальных серверов или при отказе одного из них и следящего сервера внутренний сервер становится недоступным (даже если это основной сервер, продолжающий работать). В этом случае активные пользователи переключаются в режим устойчивости через некоторое время.</span><span class="sxs-lookup"><span data-stu-id="711b5-p111">If both the principal and the mirror Back End Servers fail, or if one of those servers and the witness fails, the Back End Server will become unavailable (even if it is the principal that is still working). In this case, active users are switched to Resiliency mode after some time.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

