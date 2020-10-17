---
title: Этапы миграции
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migration phases
ms:assetid: cb7747ba-b872-42ca-ab41-76e3c4e77d06
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205336(v=OCS.15)
ms:contentKeyID: 48185642
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 63f789abee1949f7fae5a7a3d7dcdc03c86dc352
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48527226"
---
# <a name="migration-phases"></a><span data-ttu-id="3d79f-102">Этапы миграции</span><span class="sxs-lookup"><span data-stu-id="3d79f-102">Migration phases</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3d79f-103">_**Последнее изменение темы:** 2012-09-17_</span><span class="sxs-lookup"><span data-stu-id="3d79f-103">_**Topic Last Modified:** 2012-09-17_</span></span>

<span data-ttu-id="3d79f-104">В Lync Server 2013 вы определяете сайты в сети, содержащие компоненты Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3d79f-104">In Lync Server 2013, you define sites on your network that contain Lync Server 2013 components.</span></span> <span data-ttu-id="3d79f-105">Сайт — это набор компьютеров, которые подключены к высокоскоростной сети с небольшой задержкой, например к одной локальной сети (LAN), или две сети, соединенные высокоскоростной оптоволоконной сетью.</span><span class="sxs-lookup"><span data-stu-id="3d79f-105">A site is a set of computers that are well-connected by a high-speed, low-latency network, such as a single local area network (LAN) or two networks connected by a high-speed fiber optic network.</span></span>

<span data-ttu-id="3d79f-106">*Интерфейсный пул* — это набор серверов переднего плана, настроенных одинаково и совместно работающих для предоставления служб для общей группы пользователей.</span><span class="sxs-lookup"><span data-stu-id="3d79f-106">A *Front End pool* is a set of Front End Servers that are configured identically and work together to provide services for a common group of users.</span></span> <span data-ttu-id="3d79f-107">Пул обеспечивает масштабируемость и возможность отработки отказа для пользователей.</span><span class="sxs-lookup"><span data-stu-id="3d79f-107">A pool provides scalability and failover capability to your users.</span></span> <span data-ttu-id="3d79f-108">Каждый сервер в пуле должен содержать идентичные роли сервера.</span><span class="sxs-lookup"><span data-stu-id="3d79f-108">Each server in a pool must run an identical server role or roles.</span></span> <span data-ttu-id="3d79f-109">Сервер Standard Edition, предназначенный для малых организаций, также определяет пул и выполняется на отдельном сервере.</span><span class="sxs-lookup"><span data-stu-id="3d79f-109">A Standard Edition server, designed for small organizations, also defines a pool and runs on a single server.</span></span> <span data-ttu-id="3d79f-110">Это позволяет использовать функциональность Lync Server 2013 для уменьшения затрат, но не предоставляет полноценное решение для высокой доступности.</span><span class="sxs-lookup"><span data-stu-id="3d79f-110">This enables you to have Lync Server 2013 functionality for a lesser cost, but does not provide a true high-availability solution.</span></span>

<span data-ttu-id="3d79f-111">На следующих этапах описывается процесс миграции пула с Lync Server 2010 на Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3d79f-111">The following phases describe the process of a pool migration from Lync Server 2010 to Lync Server 2013.</span></span> <span data-ttu-id="3d79f-112">Для нескольких сайтов, содержащих несколько пулов, каждый пул должен соответствовать этому поэтапному подходу.</span><span class="sxs-lookup"><span data-stu-id="3d79f-112">For multiple sites containing multiple pools, each individual pool should follow this phased approach.</span></span>

1.  [<span data-ttu-id="3d79f-113">Этап 1: Планирование миграции с Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="3d79f-113">Phase 1: Plan your migration from Lync Server 2010</span></span>](phase-1-plan-your-migration-from-lync-server-2010.md)

2.  [<span data-ttu-id="3d79f-114">Этап 2: подготовка к миграции</span><span class="sxs-lookup"><span data-stu-id="3d79f-114">Phase 2: Prepare for migration</span></span>](phase-2-prepare-for-migration.md)

3.  [<span data-ttu-id="3d79f-115">Этап 3: Развертывание пилотного пула Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3d79f-115">Phase 3: Deploy Lync Server 2013 pilot pool</span></span>](phase-3-deploy-lync-server-2013-pilot-pool.md)

4.  [<span data-ttu-id="3d79f-116">Этап 4: перемещение тестовых пользователей в пилотный пул</span><span class="sxs-lookup"><span data-stu-id="3d79f-116">Phase 4: Move test users to the pilot pool</span></span>](phase-4-move-test-users-to-the-pilot-pool.md)

5.  [<span data-ttu-id="3d79f-117">Этап 5: Добавление пограничного сервера Lync Server 2013 в пилотный пул</span><span class="sxs-lookup"><span data-stu-id="3d79f-117">Phase 5: Add Lync Server 2013 Edge Server to pilot pool</span></span>](phase-5-add-lync-server-2013-edge-server-to-pilot-pool.md)

6.  [<span data-ttu-id="3d79f-118">Этап 6: переход от пилотного развертывания к рабочей версии</span><span class="sxs-lookup"><span data-stu-id="3d79f-118">Phase 6: Move from pilot deployment into production</span></span>](phase-6-move-from-pilot-deployment-into-production.md)

7.  [<span data-ttu-id="3d79f-119">Этап 7: необходимые действия после миграции</span><span class="sxs-lookup"><span data-stu-id="3d79f-119">Phase 7: Complete post-migration tasks</span></span>](phase-7-complete-post-migration-tasks.md)

8.  [<span data-ttu-id="3d79f-120">Этап 8: ликвидация старых пулов</span><span class="sxs-lookup"><span data-stu-id="3d79f-120">Phase 8: Decommission legacy pools</span></span>](phase-8-decommission-legacy-pools.md)

</div>

<span> </span>

</div>

</div>

</div>

