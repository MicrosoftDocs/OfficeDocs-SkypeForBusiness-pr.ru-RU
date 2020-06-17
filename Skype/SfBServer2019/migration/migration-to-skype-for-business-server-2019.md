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
description: В подразделах этого раздела описывается процесс перехода на Skype для бизнеса Server 2019.
ms.openlocfilehash: 860fce550de33ed726bbbe723c8c7677ff09fc1c
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752621"
---
# <a name="migration-to-skype-for-business-server-2019"></a><span data-ttu-id="7f839-103">Миграция в Skype для бизнеса Server 2019</span><span class="sxs-lookup"><span data-stu-id="7f839-103">Migration to Skype for Business Server 2019</span></span>

<span data-ttu-id="7f839-104">В подразделах этого раздела описывается процесс перехода на Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="7f839-104">The topics in this section guide you through the process of migrating to Skype for Business Server 2019.</span></span> <span data-ttu-id="7f839-105">В этой статье рассматривается миграция Lync Server 2013 или Skype для бизнеса Server 2015 в Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="7f839-105">This article covers migrating Lync Server 2013 or Skype for Business Server 2015 to Skype for Business Server 2019.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7f839-106">На протяжении всего содержимого мы используем термин *Legacy (устаревшее* ), чтобы ссылаться на устаревшее Lync Server 2013 или Skype для бизнеса Server 2015, который вы переносите на Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="7f839-106">Throughout the content, we use the term *legacy* to refer to the legacy Lync Server 2013 or Skype for Business Server 2015 that you are migrating to Skype for Business Server 2019.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="7f839-107">В этом руководстве описываются действия, которые обычно требуется выполнить на каждом из этапов миграции.</span><span class="sxs-lookup"><span data-stu-id="7f839-107">This guide describes the steps generally required to accomplish each phase of migration.</span></span> <span data-ttu-id="7f839-108">Здесь не ставится цель рассмотреть все возможные топологии устаревших развертываний или все возможные сценарии миграции.</span><span class="sxs-lookup"><span data-stu-id="7f839-108">It does not address every possible legacy deployment topology or every possible migration scenario.</span></span> <span data-ttu-id="7f839-109">Таким образом, вам может не потребоваться выполнять каждый шаг, описанный выше, или в зависимости от развертывания может потребоваться выполнить дополнительные действия.</span><span class="sxs-lookup"><span data-stu-id="7f839-109">Therefore, you may not need to perform every step described, or you may need to perform additional steps, depending on your deployment.</span></span> <span data-ttu-id="7f839-110">В этом руководстве также приводятся примеры шагов проверки.</span><span class="sxs-lookup"><span data-stu-id="7f839-110">This guide also provides examples of verification steps.</span></span> <span data-ttu-id="7f839-111">Эти действия по проверке предоставляются для того, чтобы помочь вам определить, что нужно, чтобы убедиться, что каждый этап завершается успешно по мере выполнения миграции.</span><span class="sxs-lookup"><span data-stu-id="7f839-111">These verification steps are provided to help you understand what you need to look for to ensure that each phase completes successfully as you progress through your migration.</span></span> <span data-ttu-id="7f839-112">Выполните эти шаги по проверке в соответствии с конкретным процессом миграции.</span><span class="sxs-lookup"><span data-stu-id="7f839-112">Tailor these verification steps to your specific migration process.</span></span> 
  
<span data-ttu-id="7f839-113">В данном руководстве приводится информация об обновлении вашего существующего развертывания.</span><span class="sxs-lookup"><span data-stu-id="7f839-113">This guide provides information specific to upgrading your existing deployment.</span></span> <span data-ttu-id="7f839-114">Здесь не поясняется, как изменить существующую топологию.</span><span class="sxs-lookup"><span data-stu-id="7f839-114">It does not explain how to change your existing topology.</span></span> <span data-ttu-id="7f839-115">Внедрение новых возможностей также выходит за рамки этого руководства.</span><span class="sxs-lookup"><span data-stu-id="7f839-115">This guide does not cover the implementation of new features.</span></span> <span data-ttu-id="7f839-116">Когда подробная процедура задокументирована в другом месте, это руководство содержит ссылки на статью или статью.</span><span class="sxs-lookup"><span data-stu-id="7f839-116">When a detailed procedure is documented elsewhere, this guide directs you to the article or article section.</span></span> 
  
<span data-ttu-id="7f839-117">В этой статье определяются термины, указанные в приведенном ниже списке.</span><span class="sxs-lookup"><span data-stu-id="7f839-117">This article defines terms as specified in the following list.</span></span>
  
<span data-ttu-id="7f839-118">**Миграция:** Перемещение рабочего развертывания из Lync Server 2013 или Skype для бизнеса Server 2015 в Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="7f839-118">**migration:** Moving your production deployment from Lync Server 2013 or Skype for Business Server 2015 to Skype for Business Server 2019.</span></span>
    
<span data-ttu-id="7f839-119">**сосуществование:** Временная среда, существующая во время миграции, когда некоторые функции были перенесены в Skype для бизнеса Server 2019, а другие функции по-прежнему остаются в предыдущей версии.</span><span class="sxs-lookup"><span data-stu-id="7f839-119">**coexistence:** The temporary environment that exists during migration when some functionality has been migrated to Skype for Business Server 2019 and other functionality still remains on a prior version.</span></span>
    
<span data-ttu-id="7f839-120">**взаимодействие:** Способность развертывания успешно работать в течение периода сосуществования.</span><span class="sxs-lookup"><span data-stu-id="7f839-120">**interoperability:** The ability of your deployment to operate successfully during the period of coexistence.</span></span>

<span data-ttu-id="7f839-121">**устаревшие:** Система, с которой вы переноситесь, которая является Lync Server 2013 или Skype для бизнеса Server 2015.</span><span class="sxs-lookup"><span data-stu-id="7f839-121">**legacy:** The system you are migrating away from, which is either Lync Server 2013 or Skype for Business Server 2015.</span></span>
    
## <a name="in-this-section"></a><span data-ttu-id="7f839-122">В этом разделе:</span><span class="sxs-lookup"><span data-stu-id="7f839-122">In this section</span></span>

- [<span data-ttu-id="7f839-123">Перед началом миграции</span><span class="sxs-lookup"><span data-stu-id="7f839-123">Before you begin the migration</span></span>](before-you-begin-the-migration.md)
    
- [<span data-ttu-id="7f839-124">Этап 1: планирование миграции</span><span class="sxs-lookup"><span data-stu-id="7f839-124">Phase 1: Plan your migration</span></span>](phase-1-plan-your-migration.md)
    
- [<span data-ttu-id="7f839-125">Этап 2: подготовка к миграции</span><span class="sxs-lookup"><span data-stu-id="7f839-125">Phase 2: Prepare for migration</span></span>](phase-2-prepare-for-migration.md)
    
- [<span data-ttu-id="7f839-126">Этап 3: развертывание пилотного пула</span><span class="sxs-lookup"><span data-stu-id="7f839-126">Phase 3: Deploy pilot pool</span></span>](phase-3-deploy-pilot-pool.md)
    
- [<span data-ttu-id="7f839-127">Этап 4: перемещение тестовых пользователей в пилотный пул</span><span class="sxs-lookup"><span data-stu-id="7f839-127">Phase 4: Move test users to the pilot pool</span></span>](phase-4-move-test-users-to-the-pilot-pool.md)
    
- [<span data-ttu-id="7f839-128">Этап 5: добавление пограничного сервера в пилотный пул</span><span class="sxs-lookup"><span data-stu-id="7f839-128">Phase 5: Add Edge Server to pilot pool</span></span>](phase-5-add-edge-server-to-pilot-pool.md)
    
- [<span data-ttu-id="7f839-129">Этап 6: переход от пилотного развертывания к рабочей версии</span><span class="sxs-lookup"><span data-stu-id="7f839-129">Phase 6: Move from pilot deployment into production</span></span>](phase-6-move-from-pilot-deployment-into-production.md)
    
- [<span data-ttu-id="7f839-130">Этап 7: необходимые действия после миграции</span><span class="sxs-lookup"><span data-stu-id="7f839-130">Phase 7: Complete post-migration tasks</span></span>](phase-7-complete-post-migration-tasks.md)
    
- [<span data-ttu-id="7f839-131">Этап 8: ликвидация старых пулов</span><span class="sxs-lookup"><span data-stu-id="7f839-131">Phase 8: Decommission legacy pools</span></span>](phase-8-decommission-legacy-pools.md)
    

