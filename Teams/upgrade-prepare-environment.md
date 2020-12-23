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
ms.openlocfilehash: cb736a0398d1ab77ed67919f02a80400bd2ae19e
ms.sourcegitcommit: 1e16c6c7112bdde03209c12468b5705ddd116a62
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2020
ms.locfileid: "49578252"
---
# <a name="prepare-your-environment-for-upgrading-to-teams"></a><span data-ttu-id="e5cd4-103">Подготовка среды к переходу на Teams</span><span class="sxs-lookup"><span data-stu-id="e5cd4-103">Prepare your environment for upgrading to Teams</span></span>

<span data-ttu-id="e5cd4-104">![Схема пути обновления с акцентом на этапе технической готовности](media/upgrade-banner-tech-readiness.png "Этапы пути обновления с акцентом на этапе технической готовности")</span><span class="sxs-lookup"><span data-stu-id="e5cd4-104">![Upgrade journey diagram, emphasizing the Technical Readiness stage](media/upgrade-banner-tech-readiness.png "Stages of the upgrade journey, with emphasis on the Technical Readiness stage")</span></span>

<span data-ttu-id="e5cd4-105">Эта статья является частью этапа технической готовности, которое вы завершаете параллельно с этапом подготовки пользователя.</span><span class="sxs-lookup"><span data-stu-id="e5cd4-105">This article is part of the Technical Readiness stage of your upgrade journey, an activity you complete in parallel with the User Readiness stage.</span></span> <span data-ttu-id="e5cd4-106">Прежде чем при этом подтверждать, что вы выполнили эти действия на предыдущих этапах:</span><span class="sxs-lookup"><span data-stu-id="e5cd4-106">Before proceeding, confirm that you've completed these activities from previous stages:</span></span>

- [<span data-ttu-id="e5cd4-107">Привлечение заинтересованных лиц проекта</span><span class="sxs-lookup"><span data-stu-id="e5cd4-107">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
- [<span data-ttu-id="e5cd4-108">Определение области проекта</span><span class="sxs-lookup"><span data-stu-id="e5cd4-108">Defined your project scope</span></span>](https://aka.ms/SkypetoTeams-Scope)
- [<span data-ttu-id="e5cd4-109">Понимание сосуществования и совместной работы Skype для бизнеса и Teams</span><span class="sxs-lookup"><span data-stu-id="e5cd4-109">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](https://aka.ms/SkypeToTeams-Coexist)
- [<span data-ttu-id="e5cd4-110">Выбранный путь обновления</span><span class="sxs-lookup"><span data-stu-id="e5cd4-110">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

<span data-ttu-id="e5cd4-111">Чтобы успешно обновить Teams в организации, важно проверить текущую среду Skype для бизнеса и готовность сети.</span><span class="sxs-lookup"><span data-stu-id="e5cd4-111">To drive a successful Teams upgrade in your organization, it's important that you validate your current Skype for Business environment and your network readiness.</span></span> <span data-ttu-id="e5cd4-112">Подготовив текущую среду, вы сможете обеспечить высокое качество работы пользователей, а также повысить качество работы в Teams.</span><span class="sxs-lookup"><span data-stu-id="e5cd4-112">Preparing your current environment will help ensure a high-quality user experience now, in addition to improving the quality of the user experience in Teams.</span></span> <span data-ttu-id="e5cd4-113">Время, необходимое для планирования отдельных действий, поможет ускорить развертывание и убедиться, что вы не пропустили важные поруки.</span><span class="sxs-lookup"><span data-stu-id="e5cd4-113">Taking time to plan individual steps can help accelerate your deployment and ensure that you haven't skipped any important action items.</span></span>

<span data-ttu-id="e5cd4-114">Параллельное завершение этих действий с подготовкой пользователей к работе.</span><span class="sxs-lookup"><span data-stu-id="e5cd4-114">Complete these activities in parallel with your user readiness preparation:</span></span>

- <span data-ttu-id="e5cd4-115">[Подготовьте ИТ-специалистов](upgrade-prepare-IT-pros.md) к успешному обновлению.</span><span class="sxs-lookup"><span data-stu-id="e5cd4-115">[Prepare your IT staff](upgrade-prepare-IT-pros.md) to help ensure they have what they need for a successful upgrade journey.</span></span>
- <span data-ttu-id="e5cd4-116">Убедитесь, что ваша среда соответствует всем необходимым [требованиям,](upgrade-plan-journey-prerequisites.md)и проверьте зависимости между службами Microsoft 365 или Office 365 и Teams.</span><span class="sxs-lookup"><span data-stu-id="e5cd4-116">Verify that your environment meets all [prerequisites](upgrade-plan-journey-prerequisites.md), and understand dependencies among Microsoft 365 or Office 365 services and Teams.</span></span>
- <span data-ttu-id="e5cd4-117">[Оцените свою среду,](upgrade-plan-journey-evaluate-environment.md) выполнив обнаружение среды, используя образец анкеты, чтобы подтвердить готовность вашей организации к успешному обновлению Teams.</span><span class="sxs-lookup"><span data-stu-id="e5cd4-117">[Evaluate your environment](upgrade-plan-journey-evaluate-environment.md) by performing environmental discovery by using a sample questionnaire to confirm your organization's readiness to undertake a successful upgrade journey to Teams.</span></span>
- <span data-ttu-id="e5cd4-118">[Подготовка сети путем](prepare-network.md) планирования, подготовки и принятия всех необходимых исправлений для поддержки рабочих нагрузок Teams.</span><span class="sxs-lookup"><span data-stu-id="e5cd4-118">[Prepare your network](prepare-network.md) through planning, preparation, and taking any necessary remediation steps for your network to support Teams workloads.</span></span>
- <span data-ttu-id="e5cd4-119">[Подготовьте службу](upgrade-prepare-environment-prepare-service.md) к использованию, используя контрольные списки, чтобы убедиться, что конфигурация Teams готова к переносу пользователей из Skype для бизнеса в Teams.</span><span class="sxs-lookup"><span data-stu-id="e5cd4-119">[Prepare your service](upgrade-prepare-environment-prepare-service.md) for rollout by using onboarding checklists to ensure that your Teams configuration is ready to support migrating your users from Skype for Business to Teams.</span></span>
