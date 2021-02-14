---
title: Миграция в Skype для бизнеса Server 2019
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: В темах этого раздела вы можете перейти на Skype для бизнеса Server 2019.
ms.openlocfilehash: 860fce550de33ed726bbbe723c8c7677ff09fc1c
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752621"
---
# <a name="migration-to-skype-for-business-server-2019"></a><span data-ttu-id="6e6aa-103">Миграция в Skype для бизнеса Server 2019</span><span class="sxs-lookup"><span data-stu-id="6e6aa-103">Migration to Skype for Business Server 2019</span></span>

<span data-ttu-id="6e6aa-104">В темах этого раздела вы можете перейти на Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="6e6aa-104">The topics in this section guide you through the process of migrating to Skype for Business Server 2019.</span></span> <span data-ttu-id="6e6aa-105">В этой статье описывается перенос Lync Server 2013 или Skype для бизнеса Server 2015 в Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="6e6aa-105">This article covers migrating Lync Server 2013 or Skype for Business Server 2015 to Skype for Business Server 2019.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6e6aa-106">В этом содержимом термин  "устаревший" используется для обозначения устаревшего сервера Lync Server 2013 или Skype для бизнеса Server 2015, переносимой в Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="6e6aa-106">Throughout the content, we use the term *legacy* to refer to the legacy Lync Server 2013 or Skype for Business Server 2015 that you are migrating to Skype for Business Server 2019.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="6e6aa-107">В этом руководстве описываются действия, которые обычно требуется выполнить на каждом из этапов миграции.</span><span class="sxs-lookup"><span data-stu-id="6e6aa-107">This guide describes the steps generally required to accomplish each phase of migration.</span></span> <span data-ttu-id="6e6aa-108">Здесь не ставится цель рассмотреть все возможные топологии устаревших развертываний или все возможные сценарии миграции.</span><span class="sxs-lookup"><span data-stu-id="6e6aa-108">It does not address every possible legacy deployment topology or every possible migration scenario.</span></span> <span data-ttu-id="6e6aa-109">Поэтому может не потребоваться выполнять все описанные действия или выполнять дополнительные действия в зависимости от развертывания.</span><span class="sxs-lookup"><span data-stu-id="6e6aa-109">Therefore, you may not need to perform every step described, or you may need to perform additional steps, depending on your deployment.</span></span> <span data-ttu-id="6e6aa-110">В этом руководстве также приводится пример действий по проверке.</span><span class="sxs-lookup"><span data-stu-id="6e6aa-110">This guide also provides examples of verification steps.</span></span> <span data-ttu-id="6e6aa-111">Эти шаги проверки помогут вам понять, что нужно искать, чтобы убедиться, что каждый этап успешно завершается по мере выполнения миграции.</span><span class="sxs-lookup"><span data-stu-id="6e6aa-111">These verification steps are provided to help you understand what you need to look for to ensure that each phase completes successfully as you progress through your migration.</span></span> <span data-ttu-id="6e6aa-112">Привяйте эти действия проверки к конкретному процессу миграции.</span><span class="sxs-lookup"><span data-stu-id="6e6aa-112">Tailor these verification steps to your specific migration process.</span></span> 
  
<span data-ttu-id="6e6aa-113">В данном руководстве приводится информация об обновлении вашего существующего развертывания.</span><span class="sxs-lookup"><span data-stu-id="6e6aa-113">This guide provides information specific to upgrading your existing deployment.</span></span> <span data-ttu-id="6e6aa-114">Здесь не поясняется, как изменить существующую топологию.</span><span class="sxs-lookup"><span data-stu-id="6e6aa-114">It does not explain how to change your existing topology.</span></span> <span data-ttu-id="6e6aa-115">Внедрение новых возможностей также выходит за рамки этого руководства.</span><span class="sxs-lookup"><span data-stu-id="6e6aa-115">This guide does not cover the implementation of new features.</span></span> <span data-ttu-id="6e6aa-116">Если подробная процедура задокументирована в другом месте, в этом руководстве описана статья или раздел статьи.</span><span class="sxs-lookup"><span data-stu-id="6e6aa-116">When a detailed procedure is documented elsewhere, this guide directs you to the article or article section.</span></span> 
  
<span data-ttu-id="6e6aa-117">В этой статье определяются термины, указанные в следующем списке.</span><span class="sxs-lookup"><span data-stu-id="6e6aa-117">This article defines terms as specified in the following list.</span></span>
  
<span data-ttu-id="6e6aa-118">**миграция:** Перемещение производственного развертывания с Lync Server 2013 или Skype для бизнеса Server 2015 на Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="6e6aa-118">**migration:** Moving your production deployment from Lync Server 2013 or Skype for Business Server 2015 to Skype for Business Server 2019.</span></span>
    
<span data-ttu-id="6e6aa-119">**сосуществование:** Временная среда, которая существует во время миграции, когда некоторые функции были перенесены в Skype для бизнеса Server 2019, а другие функции по-прежнему остаются в предыдущей версии.</span><span class="sxs-lookup"><span data-stu-id="6e6aa-119">**coexistence:** The temporary environment that exists during migration when some functionality has been migrated to Skype for Business Server 2019 and other functionality still remains on a prior version.</span></span>
    
<span data-ttu-id="6e6aa-120">**interoperability:** Возможность успешной работы развертывания в период сосуществования.</span><span class="sxs-lookup"><span data-stu-id="6e6aa-120">**interoperability:** The ability of your deployment to operate successfully during the period of coexistence.</span></span>

<span data-ttu-id="6e6aa-121">**legacy:** Система, из которой вы находитесь, — Lync Server 2013 или Skype для бизнеса Server 2015.</span><span class="sxs-lookup"><span data-stu-id="6e6aa-121">**legacy:** The system you are migrating away from, which is either Lync Server 2013 or Skype for Business Server 2015.</span></span>
    
## <a name="in-this-section"></a><span data-ttu-id="6e6aa-122">В этом разделе:</span><span class="sxs-lookup"><span data-stu-id="6e6aa-122">In this section</span></span>

- [<span data-ttu-id="6e6aa-123">Перед началом миграции</span><span class="sxs-lookup"><span data-stu-id="6e6aa-123">Before you begin the migration</span></span>](before-you-begin-the-migration.md)
    
- [<span data-ttu-id="6e6aa-124">Этап 1: планирование миграции</span><span class="sxs-lookup"><span data-stu-id="6e6aa-124">Phase 1: Plan your migration</span></span>](phase-1-plan-your-migration.md)
    
- [<span data-ttu-id="6e6aa-125">Этап 2: подготовка к миграции</span><span class="sxs-lookup"><span data-stu-id="6e6aa-125">Phase 2: Prepare for migration</span></span>](phase-2-prepare-for-migration.md)
    
- [<span data-ttu-id="6e6aa-126">Этап 3: развертывание пилотного пула</span><span class="sxs-lookup"><span data-stu-id="6e6aa-126">Phase 3: Deploy pilot pool</span></span>](phase-3-deploy-pilot-pool.md)
    
- [<span data-ttu-id="6e6aa-127">Этап 4. Перемещение тестовых пользователей в пилотный пул</span><span class="sxs-lookup"><span data-stu-id="6e6aa-127">Phase 4: Move test users to the pilot pool</span></span>](phase-4-move-test-users-to-the-pilot-pool.md)
    
- [<span data-ttu-id="6e6aa-128">Этап 5: добавление пограничного сервера в пилотный пул</span><span class="sxs-lookup"><span data-stu-id="6e6aa-128">Phase 5: Add Edge Server to pilot pool</span></span>](phase-5-add-edge-server-to-pilot-pool.md)
    
- [<span data-ttu-id="6e6aa-129">Этап 6: переход от пилотного развертывания к рабочей версии</span><span class="sxs-lookup"><span data-stu-id="6e6aa-129">Phase 6: Move from pilot deployment into production</span></span>](phase-6-move-from-pilot-deployment-into-production.md)
    
- [<span data-ttu-id="6e6aa-130">Этап 7: необходимые действия после миграции</span><span class="sxs-lookup"><span data-stu-id="6e6aa-130">Phase 7: Complete post-migration tasks</span></span>](phase-7-complete-post-migration-tasks.md)
    
- [<span data-ttu-id="6e6aa-131">Этап 8: ликвидация старых пулов</span><span class="sxs-lookup"><span data-stu-id="6e6aa-131">Phase 8: Decommission legacy pools</span></span>](phase-8-decommission-legacy-pools.md)
    

