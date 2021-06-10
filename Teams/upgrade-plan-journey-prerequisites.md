---
title: Необходимые условия и зависимости от среды для обновления до Teams
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: landerl
audience: admin
description: Используйте это руководство, чтобы узнать о предварительных и зависимостей среды для Teams организации.
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
ms.openlocfilehash: e9924c24f19da3cf17f8e8a124a03acc294c24b4
ms.sourcegitcommit: 32e3bb588abcbeded2d885483384c06706b280eb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2021
ms.locfileid: "52282166"
---
# <a name="prerequisites-and-environmental-dependencies-for-teams"></a><span data-ttu-id="5b7d5-103">Предварительные условия и зависимости от среды для Teams</span><span class="sxs-lookup"><span data-stu-id="5b7d5-103">Prerequisites and environmental dependencies for Teams</span></span>

<span data-ttu-id="5b7d5-104">![Схема пути обновления с акцентом на этапе технической готовности](media/upgrade-banner-tech-readiness.png "Этапы пути обновления с акцентом на этапе технической готовности")</span><span class="sxs-lookup"><span data-stu-id="5b7d5-104">![Upgrade journey diagram, emphasizing the Technical Readiness stage](media/upgrade-banner-tech-readiness.png "Stages of the upgrade journey, with emphasis on the Technical Readiness stage")</span></span>

<span data-ttu-id="5b7d5-105">Эта статья является частью этапа технической готовности, которое вы завершаете параллельно со этапом подготовки пользователей.</span><span class="sxs-lookup"><span data-stu-id="5b7d5-105">This article is part of the Technical Readiness stage of your upgrade journey, an activity you complete in parallel with the User Readiness stage.</span></span> <span data-ttu-id="5b7d5-106">Прежде чем при этом подтверждать, что вы выполнили эти действия на предыдущих этапах:</span><span class="sxs-lookup"><span data-stu-id="5b7d5-106">Before proceeding, confirm that you've completed these activities from previous stages:</span></span>

- [<span data-ttu-id="5b7d5-107">Привлечение заинтересованных лиц по проекту</span><span class="sxs-lookup"><span data-stu-id="5b7d5-107">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
- [<span data-ttu-id="5b7d5-108">Определение области проекта</span><span class="sxs-lookup"><span data-stu-id="5b7d5-108">Defined your project scope</span></span>](./upgrade-define-project-scope.md)
- [<span data-ttu-id="5b7d5-109">Понятное сосуществование и совместное Skype для бизнеса и Teams</span><span class="sxs-lookup"><span data-stu-id="5b7d5-109">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](./teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [<span data-ttu-id="5b7d5-110">Выбор пути обновления</span><span class="sxs-lookup"><span data-stu-id="5b7d5-110">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

<span data-ttu-id="5b7d5-111">Teams объединяют несколько Microsoft 365 и Office 365 служб, поэтому они зависят от правильной реализации и работы этих служб.</span><span class="sxs-lookup"><span data-stu-id="5b7d5-111">Teams combines multiple Microsoft 365 and Office 365 services, and is therefore dependent on the correct implementation and operation of these services.</span></span> <span data-ttu-id="5b7d5-112">Эти службы включают в себя ( но не ограничиваются) SharePoint Online, Exchange Online и OneDrive для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="5b7d5-112">These services include—but aren't limited to—SharePoint Online, Exchange Online, and OneDrive for Business.</span></span>

<span data-ttu-id="5b7d5-113">Хотя не все службы требуются, настоятельно рекомендуем внедрить все из них.</span><span class="sxs-lookup"><span data-stu-id="5b7d5-113">Although not all services are required, we highly recommend that you implement all of them.</span></span> <span data-ttu-id="5b7d5-114">Если вы решите не внедрять определенные службы, это повлияет на функции, Teams могут предложить вашей организации.</span><span class="sxs-lookup"><span data-stu-id="5b7d5-114">If you choose not to implement certain services, it will affect the functionality that Teams can offer your organization.</span></span> <span data-ttu-id="5b7d5-115">Например, если вам не нужно внедрять SharePoint Online, Teams в SharePoint Online есть определенные функции, такие как общий доступ к файлам в групповых беседах, поэтому не внедрение этой службы уменьшит функциональные возможности, предлагаемые клиентом.</span><span class="sxs-lookup"><span data-stu-id="5b7d5-115">For example, though you don't have to implement SharePoint Online, Teams does rely on SharePoint Online for certain functionality such as file sharing in group conversations, so not implementing this service will reduce the functionality offered through the client.</span></span>

<span data-ttu-id="5b7d5-116">В следующих статьях вы узнаете о необходимых предварительных Teams взаимодействия с другими технологиями.</span><span class="sxs-lookup"><span data-stu-id="5b7d5-116">See the following articles to learn about prerequisites and how Teams interacts with other technologies:</span></span>

- <span data-ttu-id="5b7d5-117">Если ваша организация не развернула рабочие нагрузки Microsoft 365 или Office 365, см. начало [работы.](https://support.office.com/article/Get-started-with-Office-365-for-Business-d6466f0d-5d13-464a-adcb-00906ae87029)</span><span class="sxs-lookup"><span data-stu-id="5b7d5-117">If your organization hasn't deployed any Microsoft 365 or Office 365 workloads, see [Get started](https://support.office.com/article/Get-started-with-Office-365-for-Business-d6466f0d-5d13-464a-adcb-00906ae87029).</span></span>

- <span data-ttu-id="5b7d5-118">Если ваша организация не добавила или не настроил проверенный домен для Microsoft 365 или Office 365, см. вопрос [и о доменах.](https://support.office.com/article/Verify-your-Office-365-domain-to-prove-ownership-nonprofit-or-education-status-or-to-activate-Yammer-87d1844e-aa47-4dc0-a61b-1b773fd4e590)</span><span class="sxs-lookup"><span data-stu-id="5b7d5-118">If your organization hasn't added or configured a verified domain for Microsoft 365 or Office 365, see [Domains FAQ](https://support.office.com/article/Verify-your-Office-365-domain-to-prove-ownership-nonprofit-or-education-status-or-to-activate-Yammer-87d1844e-aa47-4dc0-a61b-1b773fd4e590).</span></span>

- <span data-ttu-id="5b7d5-119">Если ваша организация не синхронизировала удостоверения с Azure Active Directory, см. в [Microsoft Teams.](identify-models-authentication.md)</span><span class="sxs-lookup"><span data-stu-id="5b7d5-119">If your organization hasn't synchronized identities to Azure Active Directory, see [Identity models and authentication in Microsoft Teams](identify-models-authentication.md).</span></span>

- <span data-ttu-id="5b7d5-120">Если в вашей организации нет Exchange Online, см. статью [Взаимодействие Exchange и Microsoft Teams](Exchange-Teams-interact.md).</span><span class="sxs-lookup"><span data-stu-id="5b7d5-120">If your organization doesn't have Exchange Online, see [Understand how Exchange and Microsoft Teams interact](Exchange-Teams-interact.md).</span></span>

- <span data-ttu-id="5b7d5-121">Если в вашей организации нет SharePoint Online, см. статью [Взаимодействие SharePoint Online и OneDrive для бизнеса с Microsoft Teams](SharePoint-OneDrive-interact.md).</span><span class="sxs-lookup"><span data-stu-id="5b7d5-121">If your organization doesn't have SharePoint Online, see [Understand how SharePoint Online and OneDrive for Business interact with Microsoft Teams](SharePoint-OneDrive-interact.md).</span></span>

- <span data-ttu-id="5b7d5-122">Чтобы узнать, как [Microsoft 365 групп и Microsoft Teams взаимодействие.](Office-365-groups.md)</span><span class="sxs-lookup"><span data-stu-id="5b7d5-122">To learn how [Microsoft 365 groups and Microsoft Teams interact](Office-365-groups.md).</span></span>

- <span data-ttu-id="5b7d5-123">Если ваша организация является учебным заведением и вы используете систему сведений об учащихся, см. статью Добро пожаловать в [Microsoft Синхронизация сведений о школе](/schooldatasync) перед развертыванием Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="5b7d5-123">If your organization is an educational institution and you use a Student Information System, see [Welcome to Microsoft School Data Sync](/schooldatasync) before deploying Microsoft Teams.</span></span>

- <span data-ttu-id="5b7d5-124">Если в вашей организации рассматриваются варианты звонков по телефонной сети общего звонков с телефонным подключением ,см. параметры Голосовая связь [— телефонная система](cloud-voice-landing-page.md)и Связь через ЗВОНКОВ , Какой план звонков вам подошел и телефонная система Прямой [](calling-plan-landing-page.md) [маршрутизации.](direct-routing-landing-page.md)</span><span class="sxs-lookup"><span data-stu-id="5b7d5-124">If your organization is considering Public Switched Telephone Network (PSTN) calling options, see [Voice - Phone System and PSTN connectivity](cloud-voice-landing-page.md), [Which Calling Plan is right for you](calling-plan-landing-page.md), and [Phone System Direct Routing](direct-routing-landing-page.md).</span></span>

- <span data-ttu-id="5b7d5-125">Чтобы убедиться, что все требования к сети выполнены до Teams, см. в [Microsoft Teams.](prepare-network.md)</span><span class="sxs-lookup"><span data-stu-id="5b7d5-125">To ensure all network requirements have been met before rolling out Teams, see [Prepare your organization's network for Microsoft Teams](prepare-network.md).</span></span>

- <span data-ttu-id="5b7d5-126">Если вы используете Skype для бизнеса Online Connector для управления службами, необходимо перейти в модуль Teams PowerShell и обновить существующие сценарии PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5b7d5-126">If you are currently using Skype for Business Online Connector to manage your services, you will need to move to the Teams PowerShell module and update your existing PowerShell scripts.</span></span> <span data-ttu-id="5b7d5-127">Дополнительные сведения см. в Skype для бизнеса [Online Connector в модуле Teams PowerShell.](teams-powershell-move-from-sfbo.md)</span><span class="sxs-lookup"><span data-stu-id="5b7d5-127">See [Move from Skype for Business Online Connector to the Teams PowerShell module](teams-powershell-move-from-sfbo.md) for more information.</span></span>

<span data-ttu-id="5b7d5-128">Убедився, что ваша среда соответствует всем необходимым требованиям, оцените текущую среду [для Teams.](upgrade-plan-journey-evaluate-environment.md)</span><span class="sxs-lookup"><span data-stu-id="5b7d5-128">After you've verified that your environment meets all applicable prerequisites, [evaluate your current environment for Teams](upgrade-plan-journey-evaluate-environment.md).</span></span>