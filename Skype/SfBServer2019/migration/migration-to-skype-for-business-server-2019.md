---
title: Миграция на Скайп для Business Server 2019
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: В темах этого раздела описывается процесс миграции в Скайп for Business Server 2019.
ms.openlocfilehash: 544dd01cdea68971b54374ca6e0e94909e249c82
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2018
ms.locfileid: "25027832"
---
# <a name="migration-to-skype-for-business-server-2019"></a><span data-ttu-id="8cc6d-103">Миграция на Скайп для Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="8cc6d-103">Migration to Skype for Business Server 2019</span></span>

<span data-ttu-id="8cc6d-104">В темах этого раздела описывается процесс миграции в Скайп for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="8cc6d-104">The topics in this section guide you through the process of migrating to Skype for Business Server 2019.</span></span> <span data-ttu-id="8cc6d-105">В этой статье рассматриваются перенос Lync Server 2013 или Скайп для 2015 Business Server для Скайп для Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="8cc6d-105">This article covers migrating Lync Server 2013 or Skype for Business Server 2015 to Skype for Business Server 2019.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8cc6d-106">В течение всего содержимого мы используем термин *прежних версий* обращайтесь к устаревший Lync Server 2013 или Скайп для 2015 Business Server, который будет перенесен в Скайп для Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="8cc6d-106">Throughout the content, we use the term *legacy* to refer to the legacy Lync Server 2013 or Skype for Business Server 2015 that you are migrating to Skype for Business Server 2019.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="8cc6d-107">В этом руководстве описывается, как правило, необходимых для выполнения каждого этапа переноса.</span><span class="sxs-lookup"><span data-stu-id="8cc6d-107">This guide describes the steps generally required to accomplish each phase of migration.</span></span> <span data-ttu-id="8cc6d-108">Не предусматривает всех возможных устаревшее развертывание топологии или сценарий всех возможных миграции.</span><span class="sxs-lookup"><span data-stu-id="8cc6d-108">It does not address every possible legacy deployment topology or every possible migration scenario.</span></span> <span data-ttu-id="8cc6d-109">Таким образом не может потребоваться выполнить все этапы описано, или может потребоваться выполнить дополнительные действия, в зависимости от вашего развертывания.</span><span class="sxs-lookup"><span data-stu-id="8cc6d-109">Therefore, you may not need to perform every step described, or you may need to perform additional steps, depending on your deployment.</span></span> <span data-ttu-id="8cc6d-110">В этом руководстве также приведены примеры шаги проверки.</span><span class="sxs-lookup"><span data-stu-id="8cc6d-110">This guide also provides examples of verification steps.</span></span> <span data-ttu-id="8cc6d-111">Эти шаги проверки помогут вам понять, что необходимо для поиска, чтобы убедиться, что каждого этапа завершено успешно, в процессе миграции.</span><span class="sxs-lookup"><span data-stu-id="8cc6d-111">These verification steps are provided to help you understand what you need to look for to ensure that each phase completes successfully as you progress through your migration.</span></span> <span data-ttu-id="8cc6d-112">Настройте эти шаги проверки процесса определенного перехода.</span><span class="sxs-lookup"><span data-stu-id="8cc6d-112">Tailor these verification steps to your specific migration process.</span></span> 
  
<span data-ttu-id="8cc6d-113">В этом руководстве представлены сведения, относящиеся к обновления существующего развертывания.</span><span class="sxs-lookup"><span data-stu-id="8cc6d-113">This guide provides information specific to upgrading your existing deployment.</span></span> <span data-ttu-id="8cc6d-114">Он не приводятся сведения для изменения существующей топологии.</span><span class="sxs-lookup"><span data-stu-id="8cc6d-114">It does not explain how to change your existing topology.</span></span> <span data-ttu-id="8cc6d-115">В этом руководстве не рассматриваются реализации новых функций.</span><span class="sxs-lookup"><span data-stu-id="8cc6d-115">This guide does not cover the implementation of new features.</span></span> <span data-ttu-id="8cc6d-116">Когда подробные процедуры задокументирован в другом месте, в этом руководстве направляет статью или раздел статьи.</span><span class="sxs-lookup"><span data-stu-id="8cc6d-116">When a detailed procedure is documented elsewhere, this guide directs you to the article or article section.</span></span> 
  
<span data-ttu-id="8cc6d-117">В этой статье используются термины, указанные в следующем списке.</span><span class="sxs-lookup"><span data-stu-id="8cc6d-117">This article defines terms as specified in the following list.</span></span>
  
<span data-ttu-id="8cc6d-118">**миграции:** Перемещение производственного развертывания с Lync Server 2013 или Скайп для Business Server 2015 Скайп для Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="8cc6d-118">**migration:** Moving your production deployment from Lync Server 2013 or Skype for Business Server 2015 to Skype for Business Server 2019.</span></span>
    
<span data-ttu-id="8cc6d-119">**совместной работы:** Временная среда, существующая во время миграции, когда некоторые функциональные возможности уже перенесены в Скайп для Business Server 2019, а другие все еще остаются в предыдущей версии.</span><span class="sxs-lookup"><span data-stu-id="8cc6d-119">**coexistence:** The temporary environment that exists during migration when some functionality has been migrated to Skype for Business Server 2019 and other functionality still remains on a prior version.</span></span>
    
<span data-ttu-id="8cc6d-120">**взаимодействия:** Возможность развертывания успешно работать во время периода сосуществования.</span><span class="sxs-lookup"><span data-stu-id="8cc6d-120">**interoperability:** The ability of your deployment to operate successfully during the period of coexistence.</span></span>

<span data-ttu-id="8cc6d-121">**прежних версий:** Система переносе из, которая является Lync Server 2013 или Скайп для Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="8cc6d-121">**legacy:** The system you are migrating away from, which is either Lync Server 2013 or Skype for Business Server 2015.</span></span>
    
## <a name="in-this-section"></a><span data-ttu-id="8cc6d-122">Содержание</span><span class="sxs-lookup"><span data-stu-id="8cc6d-122">In this section</span></span>

- [<span data-ttu-id="8cc6d-123">Перед началом миграции</span><span class="sxs-lookup"><span data-stu-id="8cc6d-123">Before you begin the migration</span></span>](before-you-begin-the-migration.md)
    
- [<span data-ttu-id="8cc6d-124">Этап 1: Планирование миграции</span><span class="sxs-lookup"><span data-stu-id="8cc6d-124">Phase 1: Plan your migration</span></span>](phase-1-plan-your-migration.md)
    
- [<span data-ttu-id="8cc6d-125">Этап 2: Подготовка к миграции</span><span class="sxs-lookup"><span data-stu-id="8cc6d-125">Phase 2: Prepare for migration</span></span>](phase-2-prepare-for-migration.md)
    
- [<span data-ttu-id="8cc6d-126">Этап 3: Развертывание пилотного пула</span><span class="sxs-lookup"><span data-stu-id="8cc6d-126">Phase 3: Deploy pilot pool</span></span>](phase-3-deploy-pilot-pool.md)
    
- [<span data-ttu-id="8cc6d-127">Этап 4: Перемещение тестовых пользователей пилотного пула</span><span class="sxs-lookup"><span data-stu-id="8cc6d-127">Phase 4: Move test users to the pilot pool</span></span>](phase-4-move-test-users-to-the-pilot-pool.md)
    
- [<span data-ttu-id="8cc6d-128">Этап 5: Добавление пограничного сервера в пилотном пуле</span><span class="sxs-lookup"><span data-stu-id="8cc6d-128">Phase 5: Add Edge Server to pilot pool</span></span>](phase-5-add-edge-server-to-pilot-pool.md)
    
- [<span data-ttu-id="8cc6d-129">Этап 6: Переход от пилотного развертывания к рабочей версии</span><span class="sxs-lookup"><span data-stu-id="8cc6d-129">Phase 6: Move from pilot deployment into production</span></span>](phase-6-move-from-pilot-deployment-into-production.md)
    
- [<span data-ttu-id="8cc6d-130">Этап 7: Выполнение послемиграционных задач</span><span class="sxs-lookup"><span data-stu-id="8cc6d-130">Phase 7: Complete post-migration tasks</span></span>](phase-7-complete-post-migration-tasks.md)
    
- [<span data-ttu-id="8cc6d-131">Этап 8: Ликвидация старых пулов</span><span class="sxs-lookup"><span data-stu-id="8cc6d-131">Phase 8: Decommission legacy pools</span></span>](phase-8-decommission-legacy-pools.md)
    

