---
title: Переход с локальной среды Skype для бизнеса на Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: Узнайте, как перейти на Microsoft Teams из локального Skype для бизнеса организации.
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
ms.openlocfilehash: 0585f0ad829f19334d5a970461f1f3248a107e9d
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51115557"
---
# <a name="upgrade-from-a-skype-for-business-on-premises-deployment-to-teams"></a><span data-ttu-id="1afcb-103">Обновление локального Skype для бизнеса до Teams</span><span class="sxs-lookup"><span data-stu-id="1afcb-103">Upgrade from a Skype for Business on-premises deployment to Teams</span></span>

<span data-ttu-id="1afcb-104">![Этапы пути обновления с акцентом на этапе развертывания и внедрения](media/upgrade-banner-deployment.png "Этапы пути обновления с акцентом на этапе развертывания и внедрения")</span><span class="sxs-lookup"><span data-stu-id="1afcb-104">![Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage](media/upgrade-banner-deployment.png "Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage")</span></span>

<span data-ttu-id="1afcb-105">Эта статья является частью этапа развертывания и реализации, на который вы входите.</span><span class="sxs-lookup"><span data-stu-id="1afcb-105">This article is part of the Deployment and Implementation stage of your upgrade journey.</span></span> <span data-ttu-id="1afcb-106">Прежде чем при этом подтверждать, что вы выполнили следующие действия:</span><span class="sxs-lookup"><span data-stu-id="1afcb-106">Before proceeding, confirm that you've completed the following activities:</span></span>

- [<span data-ttu-id="1afcb-107">Привлечение заинтересованных лиц по проекту</span><span class="sxs-lookup"><span data-stu-id="1afcb-107">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
- [<span data-ttu-id="1afcb-108">Определение области проекта</span><span class="sxs-lookup"><span data-stu-id="1afcb-108">Defined your project scope</span></span>](./upgrade-define-project-scope.md)
- [<span data-ttu-id="1afcb-109">Понятное сосуществование и совместное Skype для бизнеса и Teams</span><span class="sxs-lookup"><span data-stu-id="1afcb-109">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](./teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [<span data-ttu-id="1afcb-110">Выбор пути обновления</span><span class="sxs-lookup"><span data-stu-id="1afcb-110">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [<span data-ttu-id="1afcb-111">Подготовьте свою среду</span><span class="sxs-lookup"><span data-stu-id="1afcb-111">Prepared your environment</span></span>](./upgrade-prepare-environment.md)
- [<span data-ttu-id="1afcb-112">Подготовленные организации</span><span class="sxs-lookup"><span data-stu-id="1afcb-112">Prepared your organization</span></span>](./upgrade-prepare-organization.md)
- [<span data-ttu-id="1afcb-113">Пилотный проект</span><span class="sxs-lookup"><span data-stu-id="1afcb-113">Conducted a pilot</span></span>](./pilot-essentials.md)

<span data-ttu-id="1afcb-114">Следуйте указаниям из этой статьи, если вы развернули локальное развертывание Skype для бизнеса или Microsoft Lync и хотите перейти на Microsoft Teams выборочно — с помощью нескольких режимов совместной работы или всех.</span><span class="sxs-lookup"><span data-stu-id="1afcb-114">Follow the guidance in this article if you've deployed Skype for Business or Microsoft Lync on-premises and your organization wants to upgrade to Microsoft Teams either selectively—by using multiple coexistence modes—or all-in.</span></span> 

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]

## <a name="step-1-deploy-hybrid-connectivity"></a><span data-ttu-id="1afcb-115">Шаг 1. Развертывание гибридного подключения</span><span class="sxs-lookup"><span data-stu-id="1afcb-115">Step 1: Deploy hybrid connectivity</span></span>

<span data-ttu-id="1afcb-116">Для обновления пользователей до Teams необходимо развернуть гибридное подключение.</span><span class="sxs-lookup"><span data-stu-id="1afcb-116">The key prerequisite for upgrading your users to Teams is to deploy hybrid connectivity.</span></span>

<span data-ttu-id="1afcb-117">Дополнительные сведения см. в [теме Развертывание гибридного](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity) подключения между Skype для бизнеса Server и Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="1afcb-117">For more information, see [Deploy hybrid connectivity between Skype for Business Server and Skype for Business Online](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity)</span></span>

## <a name="step-2-implement-your-chosen-upgrade-journey-for-your-organization"></a><span data-ttu-id="1afcb-118">Шаг 2. Реализация выбранного пути обновления для организации</span><span class="sxs-lookup"><span data-stu-id="1afcb-118">Step 2: Implement your chosen upgrade journey for your organization</span></span>

<span data-ttu-id="1afcb-119">После завершения гибридной настройки вы можете запланировать перемещение пользователей на Microsoft 365 или Office 365.</span><span class="sxs-lookup"><span data-stu-id="1afcb-119">After you've completed your hybrid setup, you can plan to move your users to Microsoft 365 or Office 365.</span></span>

<span data-ttu-id="1afcb-120">Дополнительные сведения см. в</span><span class="sxs-lookup"><span data-stu-id="1afcb-120">For more information, see:</span></span>

- <span data-ttu-id="1afcb-121">[TeamsUpgradePolicy: управление миграцией и сосуществованием.](upgrade-to-teams-on-prem-tools.md)</span><span class="sxs-lookup"><span data-stu-id="1afcb-121">[TeamsUpgradePolicy: managing migration and coexistence](upgrade-to-teams-on-prem-tools.md).</span></span>

- <span data-ttu-id="1afcb-122">[Перемещение пользователей из локальной сети в Skype для бизнеса Online.](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online)</span><span class="sxs-lookup"><span data-stu-id="1afcb-122">[Move users from on premises to Skype for Business Online](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online).</span></span>

## <a name="phone-system-and-teams-upgrade"></a><span data-ttu-id="1afcb-123">телефонная система и Teams обновления</span><span class="sxs-lookup"><span data-stu-id="1afcb-123">Phone System and Teams upgrade</span></span>

<span data-ttu-id="1afcb-124">Переход с локальной телефонной системы на Teams позволит вам воспользоваться преимуществами прямой маршрутации телефонная система ("Прямая маршрутия") или планов звонков, предоставленных Майкрософт для Microsoft 365 или Office 365.</span><span class="sxs-lookup"><span data-stu-id="1afcb-124">Transitioning from on-premises phone systems to Teams will allow you to take advantage of Phone System Direct Routing ("Direct Routing") or the Microsoft-provided Calling Plans for Microsoft 365 or Office 365.</span></span>

<span data-ttu-id="1afcb-125">Если вы не используете планы звонков, необходимо перенаправить развертывание корпоративной голосовой связи на прямую маршрутиз телефонная система в рамках обновления до Teams.</span><span class="sxs-lookup"><span data-stu-id="1afcb-125">If you're not using Calling Plans, you need to transition your enterprise voice deployment to Phone System Direct Routing as part of your upgrade to Teams.</span></span>

<span data-ttu-id="1afcb-126">Дополнительные сведения см. [в дополнительных сведениях о прямой телефонная система маршрутии.](./direct-routing-landing-page.md)</span><span class="sxs-lookup"><span data-stu-id="1afcb-126">For more information, see [additional considerations for Phone System Direct Routing](./direct-routing-landing-page.md).</span></span> <span data-ttu-id="1afcb-127">Если вы планируете использовать планы звонков, обратитесь к нашим рекомендациям по переносу номеров телефонов [в](phone-number-calling-plans/transfer-phone-numbers-to-teams.md)Teams.</span><span class="sxs-lookup"><span data-stu-id="1afcb-127">If you are planning to use Calling Plans, please refer to our guidance for [transferring your phone numbers to Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).</span></span>