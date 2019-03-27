---
title: Этапы миграции
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: В Скайп Business Server 2019 можно определить сайтов локальной сети, содержащие Скайп для компонентов Business Server 2019. Сайт — это набор компьютеров, соединенных высокоскоростной, небольшой задержкой сети, например одной локальной сети (LAN) или две сети, подключенных к сети оптический высокоскоростную оптоволоконной.
ms.openlocfilehash: d34351b551262450dee852efd7679f17cbe1e161
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2019
ms.locfileid: "30886540"
---
# <a name="migration-phases"></a><span data-ttu-id="32e5d-104">Этапы миграции</span><span class="sxs-lookup"><span data-stu-id="32e5d-104">Migration phases</span></span>

<span data-ttu-id="32e5d-105">В Скайп Business Server 2019 можно определить сайтов локальной сети, содержащие Скайп для компонентов Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="32e5d-105">In Skype for Business Server 2019, you define sites on your network that contain Skype for Business Server 2019 components.</span></span> <span data-ttu-id="32e5d-106">Сайт — это набор компьютеров, соединенных высокоскоростной, небольшой задержкой сети, например одной локальной сети (LAN) или две сети, подключенных к сети оптический высокоскоростную оптоволоконной.</span><span class="sxs-lookup"><span data-stu-id="32e5d-106">A site is a set of computers that are well-connected by a high-speed, low-latency network, such as a single local area network (LAN) or two networks connected by a high-speed fiber optic network.</span></span> 
  
<span data-ttu-id="32e5d-107">Пул переднего плана — это набор серверов переднего плана, одинаково настроенных и работа совместно предоставляют услуги одной группе пользователей.</span><span class="sxs-lookup"><span data-stu-id="32e5d-107">A Front End pool is a set of Front End Servers that are configured identically and work together to provide services for a common group of users.</span></span> <span data-ttu-id="32e5d-108">Пул предоставляет масштабируемость и возможность отработки отказа для пользователей.</span><span class="sxs-lookup"><span data-stu-id="32e5d-108">A pool provides scalability and failover capability to your users.</span></span> <span data-ttu-id="32e5d-109">Каждый сервер в пуле должен содержать идентичные роли сервера.</span><span class="sxs-lookup"><span data-stu-id="32e5d-109">Each server in a pool must run an identical server role or roles.</span></span> <span data-ttu-id="32e5d-110">Сервер Standard Edition, предназначенной для небольших организаций также определяет пул и работает на одном сервере.</span><span class="sxs-lookup"><span data-stu-id="32e5d-110">A Standard Edition server, designed for small organizations, also defines a pool and runs on a single server.</span></span> <span data-ttu-id="32e5d-111">Это позволяет использовать Скайп для функции Business Server 2019 для меньшим затрат, но не предоставляет значение true, решения высокой доступности.</span><span class="sxs-lookup"><span data-stu-id="32e5d-111">This enables you to have Skype for Business Server 2019 functionality for a lesser cost, but does not provide a true high-availability solution.</span></span> 
  
<span data-ttu-id="32e5d-112">Следующие этапы описывают процесс переноса пула в Скайп для Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="32e5d-112">The following phases describe the process of a pool migration to Skype for Business Server 2019.</span></span> <span data-ttu-id="32e5d-113">Для нескольких сайтов, содержащих несколько пулов каждого отдельного пула необходимо соблюдать этот поэтапный подход.</span><span class="sxs-lookup"><span data-stu-id="32e5d-113">For multiple sites containing multiple pools, each individual pool should follow this phased approach.</span></span>
  
1. [<span data-ttu-id="32e5d-114">Этап 1: планирование миграции</span><span class="sxs-lookup"><span data-stu-id="32e5d-114">Phase 1: Plan your migration</span></span>](phase-1-plan-your-migration.md)
    
2. [<span data-ttu-id="32e5d-115">Этап 2: подготовка к миграции</span><span class="sxs-lookup"><span data-stu-id="32e5d-115">Phase 2: Prepare for migration</span></span>](phase-2-prepare-for-migration.md)
    
3. [<span data-ttu-id="32e5d-116">Этап 3: Развертывание Скайп для пилотного пула Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="32e5d-116">Phase 3: Deploy Skype for Business Server 2019 pilot pool</span></span>](phase-3-deploy-pilot-pool.md)
    
4. [<span data-ttu-id="32e5d-117">Этап 4: Перемещение тестовых пользователей пилотного пула</span><span class="sxs-lookup"><span data-stu-id="32e5d-117">Phase 4: Move test users to the pilot pool</span></span>](phase-4-move-test-users-to-the-pilot-pool.md)
    
5. [<span data-ttu-id="32e5d-118">Этап 5: Добавление Скайп Business Server 2019 пограничного сервера для пилотного пула</span><span class="sxs-lookup"><span data-stu-id="32e5d-118">Phase 5: Add Skype for Business Server 2019 Edge Server to pilot pool</span></span>](phase-5-add-edge-server-to-pilot-pool.md)
    
6. [<span data-ttu-id="32e5d-119">Этап 6: переход от пилотного развертывания к рабочей версии</span><span class="sxs-lookup"><span data-stu-id="32e5d-119">Phase 6: Move from pilot deployment into production</span></span>](phase-6-move-from-pilot-deployment-into-production.md)
    
7. [<span data-ttu-id="32e5d-120">Этап 7: необходимые действия после миграции</span><span class="sxs-lookup"><span data-stu-id="32e5d-120">Phase 7: Complete post-migration tasks</span></span>](phase-7-complete-post-migration-tasks.md)
    
8. [<span data-ttu-id="32e5d-121">Этап 8: ликвидация старых пулов</span><span class="sxs-lookup"><span data-stu-id="32e5d-121">Phase 8: Decommission legacy pools</span></span>](phase-8-decommission-legacy-pools.md)
    

