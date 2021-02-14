---
title: Переход с локальной среды Skype для бизнеса на Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: Узнайте, как перейти с локального развертывания Skype для бизнеса на Microsoft Teams.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- Teams-upgrade-guidance
- seo-marvel-apr2020
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 90542f680c1d3992f5f318bfedad8a12470d282b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49820949"
---
# <a name="upgrade-from-a-skype-for-business-on-premises-deployment-to-teams"></a><span data-ttu-id="e67ed-103">Обновление локального развертывания Skype для бизнеса до Teams</span><span class="sxs-lookup"><span data-stu-id="e67ed-103">Upgrade from a Skype for Business on-premises deployment to Teams</span></span>

<span data-ttu-id="e67ed-104">![Этапы пути обновления с акцентом на этапе развертывания и реализации](media/upgrade-banner-deployment.png "Этапы пути обновления с акцентом на этапе развертывания и реализации")</span><span class="sxs-lookup"><span data-stu-id="e67ed-104">![Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage](media/upgrade-banner-deployment.png "Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage")</span></span>

<span data-ttu-id="e67ed-105">Эта статья является частью этапа развертывания и реализации, которое вы начинаете.</span><span class="sxs-lookup"><span data-stu-id="e67ed-105">This article is part of the Deployment and Implementation stage of your upgrade journey.</span></span> <span data-ttu-id="e67ed-106">Прежде чем продолжается, подтвердим, что вы выполнили следующие действия:</span><span class="sxs-lookup"><span data-stu-id="e67ed-106">Before proceeding, confirm that you've completed the following activities:</span></span>

- [<span data-ttu-id="e67ed-107">Привлечение заинтересованных лиц проекта</span><span class="sxs-lookup"><span data-stu-id="e67ed-107">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
- [<span data-ttu-id="e67ed-108">Определение области проекта</span><span class="sxs-lookup"><span data-stu-id="e67ed-108">Defined your project scope</span></span>](https://aka.ms/SkypetoTeams-Scope)
- [<span data-ttu-id="e67ed-109">Понимание сосуществования и совместной работы Skype для бизнеса и Teams</span><span class="sxs-lookup"><span data-stu-id="e67ed-109">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](https://aka.ms/SkypeToTeams-Coexist)
- [<span data-ttu-id="e67ed-110">Выбранный путь обновления</span><span class="sxs-lookup"><span data-stu-id="e67ed-110">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [<span data-ttu-id="e67ed-111">Подготовлена среда</span><span class="sxs-lookup"><span data-stu-id="e67ed-111">Prepared your environment</span></span>](https://aka.ms/SkypeToTeams-TechnicalReadiness)
- [<span data-ttu-id="e67ed-112">Подготовив организацию</span><span class="sxs-lookup"><span data-stu-id="e67ed-112">Prepared your organization</span></span>](https://aka.ms/SkypeToTeams-UserReadiness)
- [<span data-ttu-id="e67ed-113">Проводится пилотный проект</span><span class="sxs-lookup"><span data-stu-id="e67ed-113">Conducted a pilot</span></span>](https://aka.ms/SkypeToTeams-Pilot)

<span data-ttu-id="e67ed-114">Следуйте указаниям в этой статье, если вы развернули локальное приложение Skype для бизнеса или Microsoft Lync и хотите выборочно перейти на Microsoft Teams с помощью нескольких режимов сосуществования или в режиме all-in.</span><span class="sxs-lookup"><span data-stu-id="e67ed-114">Follow the guidance in this article if you've deployed Skype for Business or Microsoft Lync on-premises and your organization wants to upgrade to Microsoft Teams either selectively—by using multiple coexistence modes—or all-in.</span></span> 

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]

## <a name="step-1-deploy-hybrid-connectivity"></a><span data-ttu-id="e67ed-115">Шаг 1. Развертывание гибридного подключения</span><span class="sxs-lookup"><span data-stu-id="e67ed-115">Step 1: Deploy hybrid connectivity</span></span>

<span data-ttu-id="e67ed-116">Для обновления пользователей до Teams необходимо развернуть гибридное подключение.</span><span class="sxs-lookup"><span data-stu-id="e67ed-116">The key prerequisite for upgrading your users to Teams is to deploy hybrid connectivity.</span></span>

<span data-ttu-id="e67ed-117">Дополнительные сведения см. в [сведениях о развертывании](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity) гибридного подключения между Skype для бизнеса Server и Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="e67ed-117">For more information, see [Deploy hybrid connectivity between Skype for Business Server and Skype for Business Online](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity)</span></span>

## <a name="step-2-implement-your-chosen-upgrade-journey-for-your-organization"></a><span data-ttu-id="e67ed-118">Шаг 2. Реализация выбранного пути обновления для организации</span><span class="sxs-lookup"><span data-stu-id="e67ed-118">Step 2: Implement your chosen upgrade journey for your organization</span></span>

<span data-ttu-id="e67ed-119">После завершения гибридной настройки вы можете запланировать перемещение пользователей на Microsoft 365 или Office 365.</span><span class="sxs-lookup"><span data-stu-id="e67ed-119">After you've completed your hybrid setup, you can plan to move your users to Microsoft 365 or Office 365.</span></span>

<span data-ttu-id="e67ed-120">Дополнительные сведения см. в:</span><span class="sxs-lookup"><span data-stu-id="e67ed-120">For more information, see:</span></span>

- <span data-ttu-id="e67ed-121">[TeamsUpgradePolicy: управление миграцией и сосуществованием.](upgrade-to-teams-on-prem-tools.md)</span><span class="sxs-lookup"><span data-stu-id="e67ed-121">[TeamsUpgradePolicy: managing migration and coexistence](upgrade-to-teams-on-prem-tools.md).</span></span>

- <span data-ttu-id="e67ed-122">[Перемещение пользователей из локальной сети в Skype для бизнеса Online.](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online)</span><span class="sxs-lookup"><span data-stu-id="e67ed-122">[Move users from on premises to Skype for Business Online](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online).</span></span>

## <a name="phone-system-and-teams-upgrade"></a><span data-ttu-id="e67ed-123">Обновление телефонной системы и Teams</span><span class="sxs-lookup"><span data-stu-id="e67ed-123">Phone System and Teams upgrade</span></span>

<span data-ttu-id="e67ed-124">Переход с локальной телефонной системы на Teams позволит вам воспользоваться прямой маршрутией телефонной системы ("Прямая маршрутия") или предоставленными Майкрософт планами звонков для Microsoft 365 или Office 365.</span><span class="sxs-lookup"><span data-stu-id="e67ed-124">Transitioning from on-premises phone systems to Teams will allow you to take advantage of Phone System Direct Routing ("Direct Routing") or the Microsoft-provided Calling Plans for Microsoft 365 or Office 365.</span></span>

<span data-ttu-id="e67ed-125">Если вы не используете планы звонков, необходимо перейти с корпоративного развертывания голосовой связи на прямую маршрутизаку телефонной системы в рамках обновления до Teams.</span><span class="sxs-lookup"><span data-stu-id="e67ed-125">If you're not using Calling Plans, you need to transition your enterprise voice deployment to Phone System Direct Routing as part of your upgrade to Teams.</span></span>

<span data-ttu-id="e67ed-126">Дополнительные сведения см. [в дополнительных сведениях о прямой маршрутике телефонной системы.](https://docs.microsoft.com/MicrosoftTeams/2-envision-make-my-service-decisions-direct-routing)</span><span class="sxs-lookup"><span data-stu-id="e67ed-126">For more information, see [additional considerations for Phone System Direct Routing](https://docs.microsoft.com/MicrosoftTeams/2-envision-make-my-service-decisions-direct-routing).</span></span> <span data-ttu-id="e67ed-127">Если вы планируете использовать планы звонков, обратитесь к нашим рекомендациям по переносу номеров [телефонов в Teams.](phone-number-calling-plans/transfer-phone-numbers-to-teams.md)</span><span class="sxs-lookup"><span data-stu-id="e67ed-127">If you are planning to use Calling Plans, please refer to our guidance for [transferring your phone numbers to Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).</span></span>