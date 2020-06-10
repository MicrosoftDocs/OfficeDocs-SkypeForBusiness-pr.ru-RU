---
title: Необходимые условия для Microsoft Teams | Обновление внедрения зависимостей
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: landerl
audience: admin
description: В этой статье описаны требования и зависимости окружающей среды для развертывания групп в Организации
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
ms.openlocfilehash: 241c1f2ab0287b6beb2a99386b2f04b1f7cbfb28
ms.sourcegitcommit: f586d2765195dbd5b7cf65615a03a1cb098c5466
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "44666071"
---
# <a name="prerequisites-and-environmental-dependencies-for-teams"></a><span data-ttu-id="d1894-103">Требования и зависимости окружающей среды для Teams</span><span class="sxs-lookup"><span data-stu-id="d1894-103">Prerequisites and environmental dependencies for Teams</span></span>

<span data-ttu-id="d1894-104">![Обновление схемы поездки с акцентом на этапе технической подготовки](media/upgrade-banner-tech-readiness.png "Этапы путешествия по обновлению с акцентом на этапе технической подготовки")</span><span class="sxs-lookup"><span data-stu-id="d1894-104">![Upgrade journey diagram, emphasizing the Technical Readiness stage](media/upgrade-banner-tech-readiness.png "Stages of the upgrade journey, with emphasis on the Technical Readiness stage")</span></span>

<span data-ttu-id="d1894-105">Эта статья относится к техническому этапу подготовки к обновлению, действиям, завершенным параллельно с этапом готовности пользователей.</span><span class="sxs-lookup"><span data-stu-id="d1894-105">This article is part of the Technical Readiness stage of your upgrade journey, an activity you complete in parallel with the User Readiness stage.</span></span> <span data-ttu-id="d1894-106">Прежде чем продолжить, подтвердите, что вы выполнили следующие действия из предыдущих стадий.</span><span class="sxs-lookup"><span data-stu-id="d1894-106">Before proceeding, confirm that you've completed these activities from previous stages:</span></span>

- [<span data-ttu-id="d1894-107">Вовлеченные заинтересованные лица в проект</span><span class="sxs-lookup"><span data-stu-id="d1894-107">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
- [<span data-ttu-id="d1894-108">Определение области охвата проекта</span><span class="sxs-lookup"><span data-stu-id="d1894-108">Defined your project scope</span></span>](https://aka.ms/SkypetoTeams-Scope)
- [<span data-ttu-id="d1894-109">Сосуществование и взаимодействие Skype для бизнеса и рабочих групп</span><span class="sxs-lookup"><span data-stu-id="d1894-109">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](https://aka.ms/SkypeToTeams-Coexist)
- [<span data-ttu-id="d1894-110">Выбрано путешествие с обновлением</span><span class="sxs-lookup"><span data-stu-id="d1894-110">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

<span data-ttu-id="d1894-111">В Teams объединены различные службы Microsoft 365 и Office 365, поэтому они зависят от правильной реализации и функционирования этих служб.</span><span class="sxs-lookup"><span data-stu-id="d1894-111">Teams combines multiple Microsoft 365 and Office 365 services, and is therefore dependent on the correct implementation and operation of these services.</span></span> <span data-ttu-id="d1894-112">Эти службы включают (но не ограничиваются) SharePoint Online, Exchange Online и OneDrive для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="d1894-112">These services include—but aren't limited to—SharePoint Online, Exchange Online, and OneDrive for Business.</span></span>

<span data-ttu-id="d1894-113">Несмотря на то, что требуется не все службы, мы настоятельно рекомендуем вам реализовать все.</span><span class="sxs-lookup"><span data-stu-id="d1894-113">Although not all services are required, we highly recommend that you implement all of them.</span></span> <span data-ttu-id="d1894-114">Если вы решили не применять определенные службы, это повлияет на функциональность, которую Teams может предложить вашей организации.</span><span class="sxs-lookup"><span data-stu-id="d1894-114">If you choose not to implement certain services, it will affect the functionality that Teams can offer your organization.</span></span> <span data-ttu-id="d1894-115">Например, несмотря на то, что вам не нужно реализовывать SharePoint Online, в Teams в SharePoint Online используются определенные функции, такие как общий доступ к файлам во время групповых разговоров, поэтому не реализация этой службы уменьшает функциональность, предоставляемую клиентом.</span><span class="sxs-lookup"><span data-stu-id="d1894-115">For example, though you don't have to implement SharePoint Online, Teams does rely on SharePoint Online for certain functionality such as file sharing in group conversations, so not implementing this service will reduce the functionality offered through the client.</span></span>

<span data-ttu-id="d1894-116">Ознакомьтесь со следующими статьями о предварительных требованиях и способах взаимодействия групп с другими технологиями.</span><span class="sxs-lookup"><span data-stu-id="d1894-116">See the following articles to learn about prerequisites and how Teams interacts with other technologies:</span></span>

- <span data-ttu-id="d1894-117">Если ваша организация не развернула рабочие нагрузки Microsoft 365 или Office 365, ознакомьтесь со [статьей начало работы](https://support.office.com/article/Get-started-with-Office-365-for-Business-d6466f0d-5d13-464a-adcb-00906ae87029).</span><span class="sxs-lookup"><span data-stu-id="d1894-117">If your organization hasn't deployed any Microsoft 365 or Office 365 workloads, see [Get started](https://support.office.com/article/Get-started-with-Office-365-for-Business-d6466f0d-5d13-464a-adcb-00906ae87029).</span></span>

- <span data-ttu-id="d1894-118">Если ваша организация не добавила или не настроила проверенный домен для Microsoft 365 или Office 365, ознакомьтесь с разделами [вопросы и ответы о доменах](https://support.office.com/article/Verify-your-Office-365-domain-to-prove-ownership-nonprofit-or-education-status-or-to-activate-Yammer-87d1844e-aa47-4dc0-a61b-1b773fd4e590).</span><span class="sxs-lookup"><span data-stu-id="d1894-118">If your organization hasn't added or configured a verified domain for Microsoft 365 or Office 365, see [Domains FAQ](https://support.office.com/article/Verify-your-Office-365-domain-to-prove-ownership-nonprofit-or-education-status-or-to-activate-Yammer-87d1844e-aa47-4dc0-a61b-1b773fd4e590).</span></span>

- <span data-ttu-id="d1894-119">Если ваша организация не синхронизирует удостоверения с Azure Active Directory, ознакомьтесь с [моделями удостоверений и проверкой подлинности в Microsoft Teams](identify-models-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="d1894-119">If your organization hasn't synchronized identities to Azure Active Directory, see [Identity models and authentication in Microsoft Teams](identify-models-authentication.md).</span></span>

- <span data-ttu-id="d1894-120">Если у вашей организации нет<sup>1</sup>t в Exchange Online, ознакомьтесь [со сведениями о взаимодействии Exchange и Microsoft Teams](Exchange-Teams-interact.md).</span><span class="sxs-lookup"><span data-stu-id="d1894-120">If your organization doesn<sup>1</sup>t have Exchange Online, see [Understand how Exchange and Microsoft Teams interact](Exchange-Teams-interact.md).</span></span>

- <span data-ttu-id="d1894-121">Если в вашей организации нет SharePoint Online, ознакомьтесь [со сведениями о том, как SharePoint Online и OneDrive для бизнеса могут взаимодействовать с Microsoft Teams](SharePoint-OneDrive-interact.md).</span><span class="sxs-lookup"><span data-stu-id="d1894-121">If your organization doesn't have SharePoint Online, see [Understand how SharePoint Online and OneDrive for Business interact with Microsoft Teams](SharePoint-OneDrive-interact.md).</span></span>

- <span data-ttu-id="d1894-122">Сведения о [взаимодействии групп microsoft 365 и Microsoft Teams](Office-365-groups.md).</span><span class="sxs-lookup"><span data-stu-id="d1894-122">Learn how [Microsoft 365 groups and Microsoft Teams interact](Office-365-groups.md).</span></span>

- <span data-ttu-id="d1894-123">Если ваша организация — образовательное учреждение и вы используете информационную систему учащихся, выполните [развертывание School Data Sync](https://docs.microsoft.com/schooldatasync) перед развертыванием Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="d1894-123">If your organization is an educational institution and you use a Student Information System, [deploy School Data Sync](https://docs.microsoft.com/schooldatasync) before deploying Microsoft Teams.</span></span>

<span data-ttu-id="d1894-124">Убедившись в том, что ваша среда отвечает всем применимым требованиям, [оцените текущую среду для Teams](upgrade-plan-journey-evaluate-environment.md).</span><span class="sxs-lookup"><span data-stu-id="d1894-124">After you've verified that your environment meets all applicable prerequisites, [evaluate your current environment for Teams](upgrade-plan-journey-evaluate-environment.md).</span></span>
