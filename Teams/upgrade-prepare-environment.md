---
title: Подготовка среды к переходу со Skype для бизнеса на Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: dearbeen
description: Проверяйте готовность среды и сети перед переходом с Skype для бизнеса на Teams.
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
MS.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3b1777aaadb1a4a141ec3c80936fa147cd44353d
ms.sourcegitcommit: 75b2cd0d2d39c50dc1e1513860841e2ae3f84324
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/28/2019
ms.locfileid: "34493844"
---
<span data-ttu-id="abaf4-103">![Обновление схемы поездки с акцентом на этапе технической подготовки] (media/upgrade-banner-tech-readiness.png "Этапы путешествия по обновлению с акцентом на этапе технической подготовки")</span><span class="sxs-lookup"><span data-stu-id="abaf4-103">![Upgrade journey diagram, emphasizing the Technical Readiness stage](media/upgrade-banner-tech-readiness.png "Stages of the upgrade journey, with emphasis on the Technical Readiness stage")</span></span>

<span data-ttu-id="abaf4-104">Эта статья относится к техническому этапу подготовки к обновлению, действиям, завершенным параллельно с этапом готовности пользователей.</span><span class="sxs-lookup"><span data-stu-id="abaf4-104">This article is part of the Technical Readiness stage of your upgrade journey, an activity you complete in parallel with the User Readiness stage.</span></span> <span data-ttu-id="abaf4-105">Прежде чем продолжить, подтвердите, что вы выполнили следующие действия из предыдущих стадий.</span><span class="sxs-lookup"><span data-stu-id="abaf4-105">Before proceeding, confirm that you’ve completed these activities from previous stages:</span></span>

- [<span data-ttu-id="abaf4-106">Вовлеченные заинтересованные лица в проект</span><span class="sxs-lookup"><span data-stu-id="abaf4-106">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
- [<span data-ttu-id="abaf4-107">Определение области охвата проекта</span><span class="sxs-lookup"><span data-stu-id="abaf4-107">Defined your project scope</span></span>](https://aka.ms/SkypetoTeams-Scope)
- [<span data-ttu-id="abaf4-108">Сосуществование и взаимодействие Skype для бизнеса и рабочих групп</span><span class="sxs-lookup"><span data-stu-id="abaf4-108">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](https://aka.ms/SkypeToTeams-Coexist)
- [<span data-ttu-id="abaf4-109">Выбрано путешествие с обновлением</span><span class="sxs-lookup"><span data-stu-id="abaf4-109">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

# <a name="prepare-your-environment-for-upgrading-to-teams"></a><span data-ttu-id="abaf4-110">Подготовка среды для перехода на Teams</span><span class="sxs-lookup"><span data-stu-id="abaf4-110">Prepare your environment for upgrading to Teams</span></span>

<span data-ttu-id="abaf4-111">Чтобы сделать успешно обновленную версию Teams в вашей организации, важно проверить текущую среду Skype для бизнеса и готовность сети.</span><span class="sxs-lookup"><span data-stu-id="abaf4-111">To drive a successful Teams upgrade in your organization, it’s important that you validate your current Skype for Business environment and your network readiness.</span></span> <span data-ttu-id="abaf4-112">Подготовка текущей среды поможет вам повысить качество взаимодействия с пользователем, а также улучшить качество взаимодействия с пользователем в Teams.</span><span class="sxs-lookup"><span data-stu-id="abaf4-112">Preparing your current environment will help ensure a high-quality user experience now, in addition to improving the quality of the user experience in Teams.</span></span> <span data-ttu-id="abaf4-113">Создание времени для планирования отдельных шагов поможет ускорить развертывание и убедиться, что вы не пропустили важные элементы действий.</span><span class="sxs-lookup"><span data-stu-id="abaf4-113">Taking time to plan individual steps can help accelerate your deployment and ensure that you haven’t skipped any important action items.</span></span>

<span data-ttu-id="abaf4-114">Параллельное выполнение этих действий с помощью подготовки пользователей к готовности.</span><span class="sxs-lookup"><span data-stu-id="abaf4-114">Complete these activities in parallel with your user readiness preparation:</span></span>

- <span data-ttu-id="abaf4-115">[Подготовьте ИТ](upgrade-prepare-IT-pros.md) -отделы к тому, чтобы убедиться в том, что они нужны для успешного поездки на обновление.</span><span class="sxs-lookup"><span data-stu-id="abaf4-115">[Prepare your IT staff](upgrade-prepare-IT-pros.md) to help ensure they have what they need for a successful upgrade journey.</span></span>
- <span data-ttu-id="abaf4-116">Убедитесь, что ваша среда соответствует [](upgrade-plan-journey-prerequisites.md)всем требованиям, и Узнайте о зависимостях служб Office 365 и групп.</span><span class="sxs-lookup"><span data-stu-id="abaf4-116">Verify that your environment meets all [prerequisites](upgrade-plan-journey-prerequisites.md), and understand dependencies among Office 365 services and Teams.</span></span>
- <span data-ttu-id="abaf4-117">[Оцените свою среду](upgrade-plan-journey-evaluate-environment.md) , выполнив пробное обнаружение среды, используя образец анкеты для подтверждения готовности Организации к успешному переходу на новую версию в Teams.</span><span class="sxs-lookup"><span data-stu-id="abaf4-117">[Evaluate your environment](upgrade-plan-journey-evaluate-environment.md) by performing environmental discovery by using a sample questionnaire to confirm your organization’s readiness to undertake a successful upgrade journey to Teams.</span></span>
- <span data-ttu-id="abaf4-118">[Подготовьте свою сеть](upgrade-prepare-environment-prepare-network.md) с помощью планирования, подготовки и выполнения необходимых действий по исправлению для вашей сети для поддержки рабочих нагрузок в Teams.</span><span class="sxs-lookup"><span data-stu-id="abaf4-118">[Prepare your network](upgrade-prepare-environment-prepare-network.md) through planning, preparation, and taking any necessary remediation steps for your network to support Teams workloads.</span></span>
- <span data-ttu-id="abaf4-119">[Подготовьте службу](upgrade-prepare-environment-prepare-service.md) для выгрузки с помощью контрольных списков, чтобы убедиться, что настройка групп готова для поддержки миграции пользователей из Skype для бизнеса в Teams.</span><span class="sxs-lookup"><span data-stu-id="abaf4-119">[Prepare your service](upgrade-prepare-environment-prepare-service.md) for rollout by using onboarding checklists to ensure that your Teams configuration is ready to support migrating your users from Skype for Business to Teams.</span></span>
