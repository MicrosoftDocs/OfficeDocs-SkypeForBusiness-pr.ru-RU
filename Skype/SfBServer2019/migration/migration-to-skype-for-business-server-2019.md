---
title: Переход на Skype для бизнеса Server 2019
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
description: В этом разделе приведены инструкции по переходу на Skype для бизнеса Server 2019.
ms.openlocfilehash: 51c3be10b90198e1abe24172aa35ab167e871739
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813407"
---
# <a name="migration-to-skype-for-business-server-2019"></a><span data-ttu-id="aa7b1-103">Переход на Skype для бизнеса Server 2019</span><span class="sxs-lookup"><span data-stu-id="aa7b1-103">Migration to Skype for Business Server 2019</span></span>

<span data-ttu-id="aa7b1-104">В этом разделе приведены инструкции по переходу на Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="aa7b1-104">The topics in this section guide you through the process of migrating to Skype for Business Server 2019.</span></span> <span data-ttu-id="aa7b1-105">В этой статье описано, как перенести Lync Server 2013 или Skype для бизнеса Server 2015 на Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="aa7b1-105">This article covers migrating Lync Server 2013 or Skype for Business Server 2015 to Skype for Business Server 2019.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="aa7b1-106">На протяжении всего содержимого мы используем термин *устаревшая версия* для ссылки на традиционный сервер Lync Server 2013 или Skype для бизнеса Server 2015, которые вы переносите на Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="aa7b1-106">Throughout the content, we use the term *legacy* to refer to the legacy Lync Server 2013 or Skype for Business Server 2015 that you are migrating to Skype for Business Server 2019.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="aa7b1-107">В этом руководстве описаны действия, которые обычно требуются для выполнения каждого этапа миграции.</span><span class="sxs-lookup"><span data-stu-id="aa7b1-107">This guide describes the steps generally required to accomplish each phase of migration.</span></span> <span data-ttu-id="aa7b1-108">Она не будет обращаться к каждой возможной топологии устаревшего развертывания или к любому из возможных сценариев миграции.</span><span class="sxs-lookup"><span data-stu-id="aa7b1-108">It does not address every possible legacy deployment topology or every possible migration scenario.</span></span> <span data-ttu-id="aa7b1-109">Таким образом, вам может потребоваться выполнить все описанные выше действия или, возможно, потребуется выполнить дополнительные действия в зависимости от развертывания.</span><span class="sxs-lookup"><span data-stu-id="aa7b1-109">Therefore, you may not need to perform every step described, or you may need to perform additional steps, depending on your deployment.</span></span> <span data-ttu-id="aa7b1-110">В этом руководстве также приводятся примеры шагов проверки.</span><span class="sxs-lookup"><span data-stu-id="aa7b1-110">This guide also provides examples of verification steps.</span></span> <span data-ttu-id="aa7b1-111">Эти шаги проверки предназначены для того, чтобы понять, что необходимо для того, чтобы убедиться в том, что каждый этап прошел успешно по ходу миграции.</span><span class="sxs-lookup"><span data-stu-id="aa7b1-111">These verification steps are provided to help you understand what you need to look for to ensure that each phase completes successfully as you progress through your migration.</span></span> <span data-ttu-id="aa7b1-112">Настройте эти шаги проверки в соответствии с конкретным процессом миграции.</span><span class="sxs-lookup"><span data-stu-id="aa7b1-112">Tailor these verification steps to your specific migration process.</span></span> 
  
<span data-ttu-id="aa7b1-113">Это руководство содержит сведения, относящиеся к обновлению существующих развертываний.</span><span class="sxs-lookup"><span data-stu-id="aa7b1-113">This guide provides information specific to upgrading your existing deployment.</span></span> <span data-ttu-id="aa7b1-114">В этой статье объясняется, как изменить существующую топологию.</span><span class="sxs-lookup"><span data-stu-id="aa7b1-114">It does not explain how to change your existing topology.</span></span> <span data-ttu-id="aa7b1-115">В этом руководстве не рассматриваются реализации новых функций.</span><span class="sxs-lookup"><span data-stu-id="aa7b1-115">This guide does not cover the implementation of new features.</span></span> <span data-ttu-id="aa7b1-116">Подробное описание процедуры приведено в разделе статья или статья.</span><span class="sxs-lookup"><span data-stu-id="aa7b1-116">When a detailed procedure is documented elsewhere, this guide directs you to the article or article section.</span></span> 
  
<span data-ttu-id="aa7b1-117">В этой статье описаны условия, указанные в приведенном ниже списке.</span><span class="sxs-lookup"><span data-stu-id="aa7b1-117">This article defines terms as specified in the following list.</span></span>
  
<span data-ttu-id="aa7b1-118">**Миграция:** Перемещение рабочего развертывания из Lync Server 2013 или Skype для бизнеса Server 2015 в Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="aa7b1-118">**migration:** Moving your production deployment from Lync Server 2013 or Skype for Business Server 2015 to Skype for Business Server 2019.</span></span>
    
<span data-ttu-id="aa7b1-119">**сосуществование:** Временная среда, существующая во время миграции, если некоторые функции были перенесены в Skype для бизнеса Server 2019, а другие функции по-прежнему остаются в более ранней версии.</span><span class="sxs-lookup"><span data-stu-id="aa7b1-119">**coexistence:** The temporary environment that exists during migration when some functionality has been migrated to Skype for Business Server 2019 and other functionality still remains on a prior version.</span></span>
    
<span data-ttu-id="aa7b1-120">**взаимодействие:** Развертывание может успешно выполняться в течение периода сосуществования.</span><span class="sxs-lookup"><span data-stu-id="aa7b1-120">**interoperability:** The ability of your deployment to operate successfully during the period of coexistence.</span></span>

<span data-ttu-id="aa7b1-121">**устаревшие:** Система, с которой вы мигрируем, является либо Lync Server 2013, либо Skype для бизнеса Server 2015.</span><span class="sxs-lookup"><span data-stu-id="aa7b1-121">**legacy:** The system you are migrating away from, which is either Lync Server 2013 or Skype for Business Server 2015.</span></span>
    
## <a name="in-this-section"></a><span data-ttu-id="aa7b1-122">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="aa7b1-122">In this section</span></span>

- [<span data-ttu-id="aa7b1-123">Перед началом миграции</span><span class="sxs-lookup"><span data-stu-id="aa7b1-123">Before you begin the migration</span></span>](before-you-begin-the-migration.md)
    
- [<span data-ttu-id="aa7b1-124">Этап 1: планирование миграции</span><span class="sxs-lookup"><span data-stu-id="aa7b1-124">Phase 1: Plan your migration</span></span>](phase-1-plan-your-migration.md)
    
- [<span data-ttu-id="aa7b1-125">Этап 2: подготовка к миграции</span><span class="sxs-lookup"><span data-stu-id="aa7b1-125">Phase 2: Prepare for migration</span></span>](phase-2-prepare-for-migration.md)
    
- [<span data-ttu-id="aa7b1-126">Этап 3: развертывание пилотного пула</span><span class="sxs-lookup"><span data-stu-id="aa7b1-126">Phase 3: Deploy pilot pool</span></span>](phase-3-deploy-pilot-pool.md)
    
- [<span data-ttu-id="aa7b1-127">Этап 4: перемещение тестовых пользователей в пилотный пул</span><span class="sxs-lookup"><span data-stu-id="aa7b1-127">Phase 4: Move test users to the pilot pool</span></span>](phase-4-move-test-users-to-the-pilot-pool.md)
    
- [<span data-ttu-id="aa7b1-128">Этап 5: добавление пограничного сервера в пилотный пул</span><span class="sxs-lookup"><span data-stu-id="aa7b1-128">Phase 5: Add Edge Server to pilot pool</span></span>](phase-5-add-edge-server-to-pilot-pool.md)
    
- [<span data-ttu-id="aa7b1-129">Этап 6: переход от пилотного развертывания к рабочей версии</span><span class="sxs-lookup"><span data-stu-id="aa7b1-129">Phase 6: Move from pilot deployment into production</span></span>](phase-6-move-from-pilot-deployment-into-production.md)
    
- [<span data-ttu-id="aa7b1-130">Этап 7: необходимые действия после миграции</span><span class="sxs-lookup"><span data-stu-id="aa7b1-130">Phase 7: Complete post-migration tasks</span></span>](phase-7-complete-post-migration-tasks.md)
    
- [<span data-ttu-id="aa7b1-131">Этап 8: ликвидация старых пулов</span><span class="sxs-lookup"><span data-stu-id="aa7b1-131">Phase 8: Decommission legacy pools</span></span>](phase-8-decommission-legacy-pools.md)
    

