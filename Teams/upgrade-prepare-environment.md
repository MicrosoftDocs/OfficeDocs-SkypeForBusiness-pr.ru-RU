---
title: Подготовка среды к переходу на Teams
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: landerl
audience: admin
description: Проверьте готовность среды и сети перед началом обновления с Skype для бизнеса до Teams.
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
ms.openlocfilehash: e154dc5844c4b8f3994c8c7bc00865c494a4c8c6
ms.sourcegitcommit: 32e3bb588abcbeded2d885483384c06706b280eb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2021
ms.locfileid: "52282146"
---
# <a name="prepare-your-environment-for-upgrading-to-teams"></a><span data-ttu-id="71ce7-103">Подготовка среды к переходу на Teams</span><span class="sxs-lookup"><span data-stu-id="71ce7-103">Prepare your environment for upgrading to Teams</span></span>

<span data-ttu-id="71ce7-104">![Схема пути обновления с акцентом на этапе технической готовности](media/upgrade-banner-tech-readiness.png "Этапы пути обновления с акцентом на этапе технической готовности")</span><span class="sxs-lookup"><span data-stu-id="71ce7-104">![Upgrade journey diagram, emphasizing the Technical Readiness stage](media/upgrade-banner-tech-readiness.png "Stages of the upgrade journey, with emphasis on the Technical Readiness stage")</span></span>

<span data-ttu-id="71ce7-105">Эта статья является частью этапа технической готовности, которое вы завершаете параллельно со этапом подготовки пользователей.</span><span class="sxs-lookup"><span data-stu-id="71ce7-105">This article is part of the Technical Readiness stage of your upgrade journey, an activity you complete in parallel with the User Readiness stage.</span></span> <span data-ttu-id="71ce7-106">Прежде чем при этом подтверждать, что вы выполнили эти действия на предыдущих этапах:</span><span class="sxs-lookup"><span data-stu-id="71ce7-106">Before proceeding, confirm that you've completed these activities from previous stages:</span></span>

- [<span data-ttu-id="71ce7-107">Привлечение заинтересованных лиц по проекту</span><span class="sxs-lookup"><span data-stu-id="71ce7-107">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
- [<span data-ttu-id="71ce7-108">Определение области проекта</span><span class="sxs-lookup"><span data-stu-id="71ce7-108">Defined your project scope</span></span>](./upgrade-define-project-scope.md)
- [<span data-ttu-id="71ce7-109">Понятное сосуществование и совместное Skype для бизнеса и Teams</span><span class="sxs-lookup"><span data-stu-id="71ce7-109">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](./teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [<span data-ttu-id="71ce7-110">Выбор пути обновления</span><span class="sxs-lookup"><span data-stu-id="71ce7-110">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

<span data-ttu-id="71ce7-111">Чтобы успешно Teams в организации, важно проверить текущую среду Skype для бизнеса и готовность сети.</span><span class="sxs-lookup"><span data-stu-id="71ce7-111">To drive a successful Teams upgrade in your organization, it's important that you validate your current Skype for Business environment and your network readiness.</span></span> <span data-ttu-id="71ce7-112">Подготовка текущей среды поможет обеспечить высокое качество работы пользователей в дополнение к повышению качества работы пользователей в Teams.</span><span class="sxs-lookup"><span data-stu-id="71ce7-112">Preparing your current environment will help ensure a high-quality user experience now, in addition to improving the quality of the user experience in Teams.</span></span> <span data-ttu-id="71ce7-113">Запланируйте отдельные действия, чтобы ускорить развертывание и убедиться, что вы не пропустили важные поруки.</span><span class="sxs-lookup"><span data-stu-id="71ce7-113">Taking time to plan individual steps can help accelerate your deployment and ensure that you haven't skipped any important action items.</span></span>

<span data-ttu-id="71ce7-114">Параллельно с подготовкой пользователей выполните указанные действия.</span><span class="sxs-lookup"><span data-stu-id="71ce7-114">Complete these activities in parallel with your user readiness preparation:</span></span>

- <span data-ttu-id="71ce7-115">[Подготовьте](upgrade-prepare-IT-pros.md) ИТ-специалистов к успешному обновлению.</span><span class="sxs-lookup"><span data-stu-id="71ce7-115">[Prepare your IT staff](upgrade-prepare-IT-pros.md) to help ensure they have what they need for a successful upgrade journey.</span></span>
- <span data-ttu-id="71ce7-116">Убедитесь, что ваша среда соответствует всем необходимым [требованиям,](upgrade-plan-journey-prerequisites.md)и проверьте зависимости между Microsoft 365 или Office 365 служб и Teams.</span><span class="sxs-lookup"><span data-stu-id="71ce7-116">Verify that your environment meets all [prerequisites](upgrade-plan-journey-prerequisites.md), and understand dependencies among Microsoft 365 or Office 365 services and Teams.</span></span>
- <span data-ttu-id="71ce7-117">[Оцените свою среду,](upgrade-plan-journey-evaluate-environment.md) выполнив обнаружение среды с помощью образца анкеты, чтобы подтвердить готовность организации к успешному обновлению Teams.</span><span class="sxs-lookup"><span data-stu-id="71ce7-117">[Evaluate your environment](upgrade-plan-journey-evaluate-environment.md) by performing environmental discovery by using a sample questionnaire to confirm your organization's readiness to undertake a successful upgrade journey to Teams.</span></span>
- <span data-ttu-id="71ce7-118">[Подготовка сети путем](prepare-network.md) планирования, подготовки и принятия всех необходимых исправлений для вашей сети для Teams рабочих нагрузок.</span><span class="sxs-lookup"><span data-stu-id="71ce7-118">[Prepare your network](prepare-network.md) through planning, preparation, and taking any necessary remediation steps for your network to support Teams workloads.</span></span>
- <span data-ttu-id="71ce7-119">[Подготовьте службу](upgrade-prepare-environment-prepare-service.md) к переходу на новой службе с помощью контрольных списков, чтобы убедиться, что конфигурация Teams готова к переносу пользователей с Skype для бизнеса на Teams.</span><span class="sxs-lookup"><span data-stu-id="71ce7-119">[Prepare your service](upgrade-prepare-environment-prepare-service.md) for rollout by using onboarding checklists to ensure that your Teams configuration is ready to support migrating your users from Skype for Business to Teams.</span></span>