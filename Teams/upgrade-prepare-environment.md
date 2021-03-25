---
title: Подготовка среды к переходу на Teams
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: landerl
audience: admin
description: Прежде чем приперейти со Skype для бизнеса на Teams, проверьте готовность среды и сети.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- Teams-upgrade-guidance
- seo-marvel-mar2020
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: f75d899f2b14915e265ce8d36c57daeaf0ce72d2
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119058"
---
# <a name="prepare-your-environment-for-upgrading-to-teams"></a><span data-ttu-id="fd1fe-103">Подготовка среды к переходу на Teams</span><span class="sxs-lookup"><span data-stu-id="fd1fe-103">Prepare your environment for upgrading to Teams</span></span>

<span data-ttu-id="fd1fe-104">![Схема пути обновления с акцентом на этапе технической готовности](media/upgrade-banner-tech-readiness.png "Этапы пути обновления с акцентом на этапе технической готовности")</span><span class="sxs-lookup"><span data-stu-id="fd1fe-104">![Upgrade journey diagram, emphasizing the Technical Readiness stage](media/upgrade-banner-tech-readiness.png "Stages of the upgrade journey, with emphasis on the Technical Readiness stage")</span></span>

<span data-ttu-id="fd1fe-105">Эта статья является частью этапа технической готовности, которое вы завершаете параллельно с этапом подготовки пользователя.</span><span class="sxs-lookup"><span data-stu-id="fd1fe-105">This article is part of the Technical Readiness stage of your upgrade journey, an activity you complete in parallel with the User Readiness stage.</span></span> <span data-ttu-id="fd1fe-106">Прежде чем при этом подтверждать, что вы выполнили эти действия на предыдущих этапах:</span><span class="sxs-lookup"><span data-stu-id="fd1fe-106">Before proceeding, confirm that you've completed these activities from previous stages:</span></span>

- [<span data-ttu-id="fd1fe-107">Привлечение заинтересованных лиц проекта</span><span class="sxs-lookup"><span data-stu-id="fd1fe-107">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
- [<span data-ttu-id="fd1fe-108">Определение области проекта</span><span class="sxs-lookup"><span data-stu-id="fd1fe-108">Defined your project scope</span></span>](./upgrade-define-project-scope.md)
- [<span data-ttu-id="fd1fe-109">Понимание сосуществования и совместной работы Skype для бизнеса и Teams</span><span class="sxs-lookup"><span data-stu-id="fd1fe-109">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](./teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [<span data-ttu-id="fd1fe-110">Вы решили перейти на нее</span><span class="sxs-lookup"><span data-stu-id="fd1fe-110">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

<span data-ttu-id="fd1fe-111">Чтобы успешно обновить Teams в организации, важно проверить текущую среду Skype для бизнеса и готовность к работе сети.</span><span class="sxs-lookup"><span data-stu-id="fd1fe-111">To drive a successful Teams upgrade in your organization, it's important that you validate your current Skype for Business environment and your network readiness.</span></span> <span data-ttu-id="fd1fe-112">Подготовив текущую среду, вы сможете обеспечить высокое качество работы пользователей, а также повысить качество работы в Teams.</span><span class="sxs-lookup"><span data-stu-id="fd1fe-112">Preparing your current environment will help ensure a high-quality user experience now, in addition to improving the quality of the user experience in Teams.</span></span> <span data-ttu-id="fd1fe-113">Время, необходимое для планирования отдельных действий, поможет ускорить развертывание и убедиться, что вы не пропустили важные поруки.</span><span class="sxs-lookup"><span data-stu-id="fd1fe-113">Taking time to plan individual steps can help accelerate your deployment and ensure that you haven't skipped any important action items.</span></span>

<span data-ttu-id="fd1fe-114">Параллельное завершение этих действий с подготовкой пользователей к работе.</span><span class="sxs-lookup"><span data-stu-id="fd1fe-114">Complete these activities in parallel with your user readiness preparation:</span></span>

- <span data-ttu-id="fd1fe-115">[Подготовьте ИТ-сотрудников](upgrade-prepare-IT-pros.md) к успешному обновлению, чтобы убедиться в том, что им нужны все необходимое.</span><span class="sxs-lookup"><span data-stu-id="fd1fe-115">[Prepare your IT staff](upgrade-prepare-IT-pros.md) to help ensure they have what they need for a successful upgrade journey.</span></span>
- <span data-ttu-id="fd1fe-116">Убедитесь, что ваша среда соответствует всем необходимым [требованиям,](upgrade-plan-journey-prerequisites.md)и проверьте зависимости между службами Microsoft 365 или Office 365 и Teams.</span><span class="sxs-lookup"><span data-stu-id="fd1fe-116">Verify that your environment meets all [prerequisites](upgrade-plan-journey-prerequisites.md), and understand dependencies among Microsoft 365 or Office 365 services and Teams.</span></span>
- <span data-ttu-id="fd1fe-117">[Оцените свою среду,](upgrade-plan-journey-evaluate-environment.md) выполнив обнаружение среды, используя образец анкеты, чтобы подтвердить готовность вашей организации к успешному обновлению Teams.</span><span class="sxs-lookup"><span data-stu-id="fd1fe-117">[Evaluate your environment](upgrade-plan-journey-evaluate-environment.md) by performing environmental discovery by using a sample questionnaire to confirm your organization's readiness to undertake a successful upgrade journey to Teams.</span></span>
- <span data-ttu-id="fd1fe-118">[Подготовка сети путем](prepare-network.md) планирования, подготовки и принятия всех необходимых исправлений для поддержки рабочих нагрузок Teams.</span><span class="sxs-lookup"><span data-stu-id="fd1fe-118">[Prepare your network](prepare-network.md) through planning, preparation, and taking any necessary remediation steps for your network to support Teams workloads.</span></span>
- <span data-ttu-id="fd1fe-119">[Подготовьте службу](upgrade-prepare-environment-prepare-service.md) к переходу на него, используя контрольные списки, чтобы убедиться, что конфигурация Teams готова к переносу пользователей из Skype для бизнеса в Teams.</span><span class="sxs-lookup"><span data-stu-id="fd1fe-119">[Prepare your service](upgrade-prepare-environment-prepare-service.md) for rollout by using onboarding checklists to ensure that your Teams configuration is ready to support migrating your users from Skype for Business to Teams.</span></span>