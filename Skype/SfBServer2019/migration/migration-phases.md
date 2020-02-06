---
title: Этапы миграции
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: В Skype для бизнеса Server 2019 вы определяете сайты в сети, которые содержат компоненты Skype для Business Server 2019. Сайт — это набор компьютеров, которые надежно соединены в высокоскоростной сети с небольшой задержкой, например в локальной сети или в двух сетях, Соединенных высокоскоростной оптоволоконной одноранговой сетью.
ms.openlocfilehash: b7d7fbddfe77c1303f0f6bde95827d94d7483f32
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813427"
---
# <a name="migration-phases"></a><span data-ttu-id="8ca84-104">Этапы миграции</span><span class="sxs-lookup"><span data-stu-id="8ca84-104">Migration phases</span></span>

<span data-ttu-id="8ca84-105">В Skype для бизнеса Server 2019 вы определяете сайты в сети, которые содержат компоненты Skype для Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="8ca84-105">In Skype for Business Server 2019, you define sites on your network that contain Skype for Business Server 2019 components.</span></span> <span data-ttu-id="8ca84-106">Сайт — это набор компьютеров, которые надежно соединены в высокоскоростной сети с небольшой задержкой, например в локальной сети или в двух сетях, Соединенных высокоскоростной оптоволоконной одноранговой сетью.</span><span class="sxs-lookup"><span data-stu-id="8ca84-106">A site is a set of computers that are well-connected by a high-speed, low-latency network, such as a single local area network (LAN) or two networks connected by a high-speed fiber optic network.</span></span> 
  
<span data-ttu-id="8ca84-107">Пул переднего плана — это набор серверных интерфейсов, которые настроены одинаково и работают вместе для предоставления служб для общей группы пользователей.</span><span class="sxs-lookup"><span data-stu-id="8ca84-107">A Front End pool is a set of Front End Servers that are configured identically and work together to provide services for a common group of users.</span></span> <span data-ttu-id="8ca84-108">Пул обеспечивает возможности масштабирования и отработки отказа для пользователей.</span><span class="sxs-lookup"><span data-stu-id="8ca84-108">A pool provides scalability and failover capability to your users.</span></span> <span data-ttu-id="8ca84-109">Каждый сервер в пуле должен выполнять одну и ту же роль (или роли).</span><span class="sxs-lookup"><span data-stu-id="8ca84-109">Each server in a pool must run an identical server role or roles.</span></span> <span data-ttu-id="8ca84-110">Сервер Standard Edition, разработанный для малых организаций, также определяет пул и выполняется на одном сервере.</span><span class="sxs-lookup"><span data-stu-id="8ca84-110">A Standard Edition server, designed for small organizations, also defines a pool and runs on a single server.</span></span> <span data-ttu-id="8ca84-111">Благодаря этому вы сможете использовать Skype для бизнеса Server 2019 для более производительной стоимости, но это не является полноценным решением, обеспечивающим высокую надежность работы.</span><span class="sxs-lookup"><span data-stu-id="8ca84-111">This enables you to have Skype for Business Server 2019 functionality for a lesser cost, but does not provide a true high-availability solution.</span></span> 
  
<span data-ttu-id="8ca84-112">Следующие этапы описывают процесс миграции пула на Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="8ca84-112">The following phases describe the process of a pool migration to Skype for Business Server 2019.</span></span> <span data-ttu-id="8ca84-113">Для нескольких сайтов с несколькими пулами каждый из них должен следовать этому поэтапному подходу.</span><span class="sxs-lookup"><span data-stu-id="8ca84-113">For multiple sites containing multiple pools, each individual pool should follow this phased approach.</span></span>
  
1. [<span data-ttu-id="8ca84-114">Этап 1: планирование миграции</span><span class="sxs-lookup"><span data-stu-id="8ca84-114">Phase 1: Plan your migration</span></span>](phase-1-plan-your-migration.md)
    
2. [<span data-ttu-id="8ca84-115">Этап 2: подготовка к миграции</span><span class="sxs-lookup"><span data-stu-id="8ca84-115">Phase 2: Prepare for migration</span></span>](phase-2-prepare-for-migration.md)
    
3. [<span data-ttu-id="8ca84-116">Этап 3: развертывание пула Skype для бизнеса Server 2019 Pilot</span><span class="sxs-lookup"><span data-stu-id="8ca84-116">Phase 3: Deploy Skype for Business Server 2019 pilot pool</span></span>](phase-3-deploy-pilot-pool.md)
    
4. [<span data-ttu-id="8ca84-117">Этап 4: перемещение тестовых пользователей в пилотный пул</span><span class="sxs-lookup"><span data-stu-id="8ca84-117">Phase 4: Move test users to the pilot pool</span></span>](phase-4-move-test-users-to-the-pilot-pool.md)
    
5. [<span data-ttu-id="8ca84-118">Этап 5: Добавление сервера подложки Skype для бизнеса Server 2019 в пилотный пул</span><span class="sxs-lookup"><span data-stu-id="8ca84-118">Phase 5: Add Skype for Business Server 2019 Edge Server to pilot pool</span></span>](phase-5-add-edge-server-to-pilot-pool.md)
    
6. [<span data-ttu-id="8ca84-119">Этап 6: переход от пилотного развертывания к рабочей версии</span><span class="sxs-lookup"><span data-stu-id="8ca84-119">Phase 6: Move from pilot deployment into production</span></span>](phase-6-move-from-pilot-deployment-into-production.md)
    
7. [<span data-ttu-id="8ca84-120">Этап 7: необходимые действия после миграции</span><span class="sxs-lookup"><span data-stu-id="8ca84-120">Phase 7: Complete post-migration tasks</span></span>](phase-7-complete-post-migration-tasks.md)
    
8. [<span data-ttu-id="8ca84-121">Этап 8: ликвидация старых пулов</span><span class="sxs-lookup"><span data-stu-id="8ca84-121">Phase 8: Decommission legacy pools</span></span>](phase-8-decommission-legacy-pools.md)
    

