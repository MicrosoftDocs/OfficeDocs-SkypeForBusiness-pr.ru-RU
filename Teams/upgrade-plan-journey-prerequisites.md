---
title: Предварительные условия и зависимости среды для перехода на Teams
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: landerl
audience: admin
description: Используйте это руководство, чтобы узнать о предварительных условиях и зависимостей среды для развертывания Teams в организации.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: bcd3de45954ea500a6be0d325370ab0660604a65
ms.sourcegitcommit: 1e16c6c7112bdde03209c12468b5705ddd116a62
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2020
ms.locfileid: "49578282"
---
# <a name="prerequisites-and-environmental-dependencies-for-teams"></a><span data-ttu-id="cf6d4-103">Предварительные условия и зависимости среды для Teams</span><span class="sxs-lookup"><span data-stu-id="cf6d4-103">Prerequisites and environmental dependencies for Teams</span></span>

<span data-ttu-id="cf6d4-104">![Схема пути обновления с акцентом на этапе технической готовности](media/upgrade-banner-tech-readiness.png "Этапы пути обновления с акцентом на этапе технической готовности")</span><span class="sxs-lookup"><span data-stu-id="cf6d4-104">![Upgrade journey diagram, emphasizing the Technical Readiness stage](media/upgrade-banner-tech-readiness.png "Stages of the upgrade journey, with emphasis on the Technical Readiness stage")</span></span>

<span data-ttu-id="cf6d4-105">Эта статья является частью этапа технической готовности, которое вы завершаете параллельно с этапом подготовки пользователя.</span><span class="sxs-lookup"><span data-stu-id="cf6d4-105">This article is part of the Technical Readiness stage of your upgrade journey, an activity you complete in parallel with the User Readiness stage.</span></span> <span data-ttu-id="cf6d4-106">Прежде чем при этом подтверждать, что вы выполнили эти действия на предыдущих этапах:</span><span class="sxs-lookup"><span data-stu-id="cf6d4-106">Before proceeding, confirm that you've completed these activities from previous stages:</span></span>

- [<span data-ttu-id="cf6d4-107">Привлечение заинтересованных лиц проекта</span><span class="sxs-lookup"><span data-stu-id="cf6d4-107">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
- [<span data-ttu-id="cf6d4-108">Определение области проекта</span><span class="sxs-lookup"><span data-stu-id="cf6d4-108">Defined your project scope</span></span>](https://aka.ms/SkypetoTeams-Scope)
- [<span data-ttu-id="cf6d4-109">Понимание сосуществования и совместной работы Skype для бизнеса и Teams</span><span class="sxs-lookup"><span data-stu-id="cf6d4-109">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](https://aka.ms/SkypeToTeams-Coexist)
- [<span data-ttu-id="cf6d4-110">Выбранный путь обновления</span><span class="sxs-lookup"><span data-stu-id="cf6d4-110">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

<span data-ttu-id="cf6d4-111">Teams объединяет несколько служб Microsoft 365 и Office 365 и поэтому зависит от правильной реализации и работы этих служб.</span><span class="sxs-lookup"><span data-stu-id="cf6d4-111">Teams combines multiple Microsoft 365 and Office 365 services, and is therefore dependent on the correct implementation and operation of these services.</span></span> <span data-ttu-id="cf6d4-112">К таким службам относятся SharePoint Online, Exchange Online и OneDrive для бизнеса, но не ограничивайтесь ими.</span><span class="sxs-lookup"><span data-stu-id="cf6d4-112">These services include—but aren't limited to—SharePoint Online, Exchange Online, and OneDrive for Business.</span></span>

<span data-ttu-id="cf6d4-113">Хотя не все службы требуются, настоятельно рекомендуем внедрить все из них.</span><span class="sxs-lookup"><span data-stu-id="cf6d4-113">Although not all services are required, we highly recommend that you implement all of them.</span></span> <span data-ttu-id="cf6d4-114">Если вы решите не внедрять определенные службы, это повлияет на функции, которые Teams может предложить вашей организации.</span><span class="sxs-lookup"><span data-stu-id="cf6d4-114">If you choose not to implement certain services, it will affect the functionality that Teams can offer your organization.</span></span> <span data-ttu-id="cf6d4-115">Например, хотя вам и не нужно внедрять SharePoint Online, в Teams есть определенные функции SharePoint Online, такие как обмен файлами в групповых беседах, поэтому реализация этой службы снизит функциональность клиента.</span><span class="sxs-lookup"><span data-stu-id="cf6d4-115">For example, though you don't have to implement SharePoint Online, Teams does rely on SharePoint Online for certain functionality such as file sharing in group conversations, so not implementing this service will reduce the functionality offered through the client.</span></span>

<span data-ttu-id="cf6d4-116">В следующих статьях вы узнаете о предварительных условиях и взаимодействии Teams с другими технологиями.</span><span class="sxs-lookup"><span data-stu-id="cf6d4-116">See the following articles to learn about prerequisites and how Teams interacts with other technologies:</span></span>

- <span data-ttu-id="cf6d4-117">Если ваша организация не развернула рабочие нагрузки Microsoft 365 или [](https://support.office.com/article/Get-started-with-Office-365-for-Business-d6466f0d-5d13-464a-adcb-00906ae87029)Office 365, см.</span><span class="sxs-lookup"><span data-stu-id="cf6d4-117">If your organization hasn't deployed any Microsoft 365 or Office 365 workloads, see [Get started](https://support.office.com/article/Get-started-with-Office-365-for-Business-d6466f0d-5d13-464a-adcb-00906ae87029).</span></span>

- <span data-ttu-id="cf6d4-118">Если ваша организация не добавила или не настроил проверенный домен для Microsoft 365 или Office 365, см. вопрос и вопрос о [доменах.](https://support.office.com/article/Verify-your-Office-365-domain-to-prove-ownership-nonprofit-or-education-status-or-to-activate-Yammer-87d1844e-aa47-4dc0-a61b-1b773fd4e590)</span><span class="sxs-lookup"><span data-stu-id="cf6d4-118">If your organization hasn't added or configured a verified domain for Microsoft 365 or Office 365, see [Domains FAQ](https://support.office.com/article/Verify-your-Office-365-domain-to-prove-ownership-nonprofit-or-education-status-or-to-activate-Yammer-87d1844e-aa47-4dc0-a61b-1b773fd4e590).</span></span>

- <span data-ttu-id="cf6d4-119">Если ваша организация не синхронизировала удостоверения с Azure Active Directory, см. модели удостоверений и проверку подлинности [в Microsoft Teams.](identify-models-authentication.md)</span><span class="sxs-lookup"><span data-stu-id="cf6d4-119">If your organization hasn't synchronized identities to Azure Active Directory, see [Identity models and authentication in Microsoft Teams](identify-models-authentication.md).</span></span>

- <span data-ttu-id="cf6d4-120">Если в вашей организации нет Exchange Online, узнайте, как [exchange и Microsoft Teams взаимодействуют.](Exchange-Teams-interact.md)</span><span class="sxs-lookup"><span data-stu-id="cf6d4-120">If your organization doesn't have Exchange Online, see [Understand how Exchange and Microsoft Teams interact](Exchange-Teams-interact.md).</span></span>

- <span data-ttu-id="cf6d4-121">Если в вашей организации нет SharePoint Online, узнайте, как SharePoint Online и OneDrive для бизнеса взаимодействуют [с Microsoft Teams.](SharePoint-OneDrive-interact.md)</span><span class="sxs-lookup"><span data-stu-id="cf6d4-121">If your organization doesn't have SharePoint Online, see [Understand how SharePoint Online and OneDrive for Business interact with Microsoft Teams](SharePoint-OneDrive-interact.md).</span></span>

- <span data-ttu-id="cf6d4-122">Чтобы узнать, как [взаимодействуют группы Microsoft 365 и Microsoft Teams.](Office-365-groups.md)</span><span class="sxs-lookup"><span data-stu-id="cf6d4-122">To learn how [Microsoft 365 groups and Microsoft Teams interact](Office-365-groups.md).</span></span>

- <span data-ttu-id="cf6d4-123">Если ваша организация является учебным заведением и вы используете систему сведений об учащихся, см. статью "Добро пожаловать в [Microsoft School Data Sync](https://docs.microsoft.com/schooldatasync) перед развертыванием Microsoft Teams".</span><span class="sxs-lookup"><span data-stu-id="cf6d4-123">If your organization is an educational institution and you use a Student Information System, see [Welcome to Microsoft School Data Sync](https://docs.microsoft.com/schooldatasync) before deploying Microsoft Teams.</span></span>

- <span data-ttu-id="cf6d4-124">Если в вашей организации рассматриваются варианты звонков по телефонной сети общего звонков (МСК), см. параметры "Голосовая связь [—](cloud-voice-landing-page.md)телефонная система" и "Подключение к СТАНП", [](calling-plan-landing-page.md)"Какой план звонков вам подошел" и "Прямая маршрутия телефонной системы". [](direct-routing-landing-page.md)</span><span class="sxs-lookup"><span data-stu-id="cf6d4-124">If your organization is considering Public Switched Telephone Network (PSTN) calling options, see [Voice - Phone System and PSTN connectivity](cloud-voice-landing-page.md), [Which Calling Plan is right for you](calling-plan-landing-page.md), and [Phone System Direct Routing](direct-routing-landing-page.md).</span></span>

- <span data-ttu-id="cf6d4-125">Чтобы убедиться в том, что все требования к сети выполнены перед развертыванием Teams, см. команду "Подготовка сети организации [к развертыванию Microsoft Teams".](prepare-network.md)</span><span class="sxs-lookup"><span data-stu-id="cf6d4-125">To ensure all network requirements have been met before rolling out Teams, see [Prepare your organization's network for Microsoft Teams](prepare-network.md).</span></span>

<span data-ttu-id="cf6d4-126">Убедився, что ваша среда соответствует всем необходимым требованиям, оцените текущую [среду для Teams.](upgrade-plan-journey-evaluate-environment.md)</span><span class="sxs-lookup"><span data-stu-id="cf6d4-126">After you've verified that your environment meets all applicable prerequisites, [evaluate your current environment for Teams](upgrade-plan-journey-evaluate-environment.md).</span></span>
