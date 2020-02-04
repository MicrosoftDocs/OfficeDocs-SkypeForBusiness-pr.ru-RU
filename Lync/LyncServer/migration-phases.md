---
title: Этапы миграции
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migration phases
ms:assetid: cb7747ba-b872-42ca-ab41-76e3c4e77d06
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205336(v=OCS.15)
ms:contentKeyID: 48185642
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 76719513d3b9df6b3259efef57fc0bd5ae94050f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730949"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migration-phases"></a><span data-ttu-id="c49d9-102">Этапы миграции</span><span class="sxs-lookup"><span data-stu-id="c49d9-102">Migration phases</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c49d9-103">_**Тема последнего изменения:** 2012-09-17_</span><span class="sxs-lookup"><span data-stu-id="c49d9-103">_**Topic Last Modified:** 2012-09-17_</span></span>

<span data-ttu-id="c49d9-104">В Lync Server 2013 вы определяете сайты в сети, которые содержат компоненты Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c49d9-104">In Lync Server 2013, you define sites on your network that contain Lync Server 2013 components.</span></span> <span data-ttu-id="c49d9-105">Сайт — это набор компьютеров, которые надежно соединены в высокоскоростной сети с небольшой задержкой, например в локальной сети или в двух сетях, Соединенных высокоскоростной оптоволоконной одноранговой сетью.</span><span class="sxs-lookup"><span data-stu-id="c49d9-105">A site is a set of computers that are well-connected by a high-speed, low-latency network, such as a single local area network (LAN) or two networks connected by a high-speed fiber optic network.</span></span>

<span data-ttu-id="c49d9-106">*Пул переднего плана* — это набор серверных интерфейсов, которые настроены одинаково и работают вместе для предоставления служб для общей группы пользователей.</span><span class="sxs-lookup"><span data-stu-id="c49d9-106">A *Front End pool* is a set of Front End Servers that are configured identically and work together to provide services for a common group of users.</span></span> <span data-ttu-id="c49d9-107">Пул обеспечивает возможности масштабирования и отработки отказа для пользователей.</span><span class="sxs-lookup"><span data-stu-id="c49d9-107">A pool provides scalability and failover capability to your users.</span></span> <span data-ttu-id="c49d9-108">Каждый сервер в пуле должен выполнять одну и ту же роль (или роли).</span><span class="sxs-lookup"><span data-stu-id="c49d9-108">Each server in a pool must run an identical server role or roles.</span></span> <span data-ttu-id="c49d9-109">Сервер Standard Edition, разработанный для малых организаций, также определяет пул и выполняется на одном сервере.</span><span class="sxs-lookup"><span data-stu-id="c49d9-109">A Standard Edition server, designed for small organizations, also defines a pool and runs on a single server.</span></span> <span data-ttu-id="c49d9-110">Это позволяет использовать функциональность Lync Server 2013 для меньшей стоимости, но не предоставляет полноценное решение для высокой доступности.</span><span class="sxs-lookup"><span data-stu-id="c49d9-110">This enables you to have Lync Server 2013 functionality for a lesser cost, but does not provide a true high-availability solution.</span></span>

<span data-ttu-id="c49d9-111">Следующие этапы описывают процесс миграции пула с Lync Server 2010 на Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c49d9-111">The following phases describe the process of a pool migration from Lync Server 2010 to Lync Server 2013.</span></span> <span data-ttu-id="c49d9-112">Для нескольких сайтов с несколькими пулами каждый из них должен следовать этому поэтапному подходу.</span><span class="sxs-lookup"><span data-stu-id="c49d9-112">For multiple sites containing multiple pools, each individual pool should follow this phased approach.</span></span>

1.  [<span data-ttu-id="c49d9-113">Этап 1: планирование перехода с Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="c49d9-113">Phase 1: Plan your migration from Lync Server 2010</span></span>](phase-1-plan-your-migration-from-lync-server-2010.md)

2.  [<span data-ttu-id="c49d9-114">Этап 2: подготовка к миграции</span><span class="sxs-lookup"><span data-stu-id="c49d9-114">Phase 2: Prepare for migration</span></span>](phase-2-prepare-for-migration.md)

3.  [<span data-ttu-id="c49d9-115">Этап 3: развертывание пула Lync Server 2013 Pilot</span><span class="sxs-lookup"><span data-stu-id="c49d9-115">Phase 3: Deploy Lync Server 2013 pilot pool</span></span>](phase-3-deploy-lync-server-2013-pilot-pool.md)

4.  [<span data-ttu-id="c49d9-116">Этап 4: перемещение тестовых пользователей в пилотный пул</span><span class="sxs-lookup"><span data-stu-id="c49d9-116">Phase 4: Move test users to the pilot pool</span></span>](phase-4-move-test-users-to-the-pilot-pool.md)

5.  [<span data-ttu-id="c49d9-117">Этап 5: Добавление сервера Lync Server 2013 EDGE на пилотный пул</span><span class="sxs-lookup"><span data-stu-id="c49d9-117">Phase 5: Add Lync Server 2013 Edge Server to pilot pool</span></span>](phase-5-add-lync-server-2013-edge-server-to-pilot-pool.md)

6.  [<span data-ttu-id="c49d9-118">Этап 6: переход от пилотного развертывания к рабочей версии</span><span class="sxs-lookup"><span data-stu-id="c49d9-118">Phase 6: Move from pilot deployment into production</span></span>](phase-6-move-from-pilot-deployment-into-production.md)

7.  [<span data-ttu-id="c49d9-119">Этап 7: необходимые действия после миграции</span><span class="sxs-lookup"><span data-stu-id="c49d9-119">Phase 7: Complete post-migration tasks</span></span>](phase-7-complete-post-migration-tasks.md)

8.  [<span data-ttu-id="c49d9-120">Этап 8: ликвидация старых пулов</span><span class="sxs-lookup"><span data-stu-id="c49d9-120">Phase 8: Decommission legacy pools</span></span>](phase-8-decommission-legacy-pools.md)

</div>

<span> </span>

</div>

</div>

</div>

