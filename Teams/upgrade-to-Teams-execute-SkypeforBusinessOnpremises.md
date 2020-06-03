---
title: Переход с локальной среды Skype для бизнеса на Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: В этой статье рассказывается о том, как перейти в Microsoft Teams из локального развертывания Skype для бизнеса.
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
ms.openlocfilehash: bea614da76bd61cf7c29b0e8f150f1aac85223a7
ms.sourcegitcommit: 6acede580649588334aeb48130ab2a5d73245723
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/03/2020
ms.locfileid: "44523162"
---
# <a name="upgrade-from-a-skype-for-business-on-premises-deployment-to-teams"></a><span data-ttu-id="13fac-103">Переход с локального развертывания Skype для бизнеса на Teams</span><span class="sxs-lookup"><span data-stu-id="13fac-103">Upgrade from a Skype for Business on-premises deployment to Teams</span></span>

<span data-ttu-id="13fac-104">![Этапы поездки на обновление, акцент на этапе развертывания и реализации](media/upgrade-banner-deployment.png "Этапы поездки на обновление, акцент на этапе развертывания и реализации")</span><span class="sxs-lookup"><span data-stu-id="13fac-104">![Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage](media/upgrade-banner-deployment.png "Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage")</span></span>

<span data-ttu-id="13fac-105">Эта статья входит в стадию развертывания и внедрения вашего путешествия по обновлению.</span><span class="sxs-lookup"><span data-stu-id="13fac-105">This article is part of the Deployment and Implementation stage of your upgrade journey.</span></span> <span data-ttu-id="13fac-106">Перед продолжением убедитесь, что выполнены следующие действия:</span><span class="sxs-lookup"><span data-stu-id="13fac-106">Before proceeding, confirm that you've completed the following activities:</span></span>

- [<span data-ttu-id="13fac-107">Вовлеченные заинтересованные лица в проект</span><span class="sxs-lookup"><span data-stu-id="13fac-107">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
- [<span data-ttu-id="13fac-108">Определение области охвата проекта</span><span class="sxs-lookup"><span data-stu-id="13fac-108">Defined your project scope</span></span>](https://aka.ms/SkypetoTeams-Scope)
- [<span data-ttu-id="13fac-109">Сосуществование и взаимодействие Skype для бизнеса и рабочих групп</span><span class="sxs-lookup"><span data-stu-id="13fac-109">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](https://aka.ms/SkypeToTeams-Coexist)
- [<span data-ttu-id="13fac-110">Выбрано путешествие с обновлением</span><span class="sxs-lookup"><span data-stu-id="13fac-110">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [<span data-ttu-id="13fac-111">Подготовка среды</span><span class="sxs-lookup"><span data-stu-id="13fac-111">Prepared your environment</span></span>](https://aka.ms/SkypeToTeams-TechnicalReadiness)
- [<span data-ttu-id="13fac-112">Подготовка Организации</span><span class="sxs-lookup"><span data-stu-id="13fac-112">Prepared your organization</span></span>](https://aka.ms/SkypeToTeams-UserReadiness)
- [<span data-ttu-id="13fac-113">Пробные испытания</span><span class="sxs-lookup"><span data-stu-id="13fac-113">Conducted a pilot</span></span>](https://aka.ms/SkypeToTeams-Pilot)

<span data-ttu-id="13fac-114">Следуйте указаниям, приведенным в этой статье, если вы разработали Skype для бизнеса или Microsoft Lync в локальной среде, и ваша организация хочет выполнить обновление до Microsoft Teams с использованием нескольких режимов сосуществования или все.</span><span class="sxs-lookup"><span data-stu-id="13fac-114">Follow the guidance in this article if you've deployed Skype for Business or Microsoft Lync on-premises and your organization wants to upgrade to Microsoft Teams either selectively—by using multiple coexistence modes—or all-in.</span></span> 

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]

## <a name="step-1-deploy-hybrid-connectivity"></a><span data-ttu-id="13fac-115">Действие 1: развертывание гибридного подключения</span><span class="sxs-lookup"><span data-stu-id="13fac-115">Step 1: Deploy hybrid connectivity</span></span>

<span data-ttu-id="13fac-116">Ключевым условием для обновления пользователей до Teams является развертывание гибридного подключения.</span><span class="sxs-lookup"><span data-stu-id="13fac-116">The key prerequisite for upgrading your users to Teams is to deploy hybrid connectivity.</span></span>

<span data-ttu-id="13fac-117">Дополнительные сведения можно найти в разделе [развертывание гибридной связи между Skype для бизнеса Server и Skype для бизнеса Online](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity)</span><span class="sxs-lookup"><span data-stu-id="13fac-117">For more information, see [Deploy hybrid connectivity between Skype for Business Server and Skype for Business Online](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity)</span></span>

## <a name="step-2-implement-your-chosen-upgrade-journey-for-your-organization"></a><span data-ttu-id="13fac-118">Шаг 2: реализация выбранного пути обновления для Организации</span><span class="sxs-lookup"><span data-stu-id="13fac-118">Step 2: Implement your chosen upgrade journey for your organization</span></span>

<span data-ttu-id="13fac-119">После того как вы закончите развертывание гибридной конфигурации, вы можете запланировать перенос пользователей в Office 365.</span><span class="sxs-lookup"><span data-stu-id="13fac-119">After you've completed your hybrid setup, you can plan to move your users to Office 365.</span></span>

<span data-ttu-id="13fac-120">Дополнительные сведения можно найти в следующих случаях:</span><span class="sxs-lookup"><span data-stu-id="13fac-120">For more information, see:</span></span>

- <span data-ttu-id="13fac-121">[TeamsUpgradePolicy: управление миграцией и сосуществованием](migration-interop-guidance-for-teams-with-skype.md#teamsupgradepolicy-managing-migration-and-co-existence).</span><span class="sxs-lookup"><span data-stu-id="13fac-121">[TeamsUpgradePolicy: managing migration and coexistence](migration-interop-guidance-for-teams-with-skype.md#teamsupgradepolicy-managing-migration-and-co-existence).</span></span>

- <span data-ttu-id="13fac-122">[Переместить пользователей из локальной сети в Skype для бизнеса Online](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online).</span><span class="sxs-lookup"><span data-stu-id="13fac-122">[Move users from on premises to Skype for Business Online](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online).</span></span>

## <a name="phone-system-and-teams-upgrade"></a><span data-ttu-id="13fac-123">Обновление телефонной системы и команды</span><span class="sxs-lookup"><span data-stu-id="13fac-123">Phone System and Teams upgrade</span></span>

<span data-ttu-id="13fac-124">Переход с локальной телефонной системы на Teams позволит вам использовать возможности прямой маршрутизации ("прямая маршрутизация") или планы звонков, предоставленные корпорацией Майкрософт для Office 365.</span><span class="sxs-lookup"><span data-stu-id="13fac-124">Transitioning from on-premises phone systems to Teams will allow you to take advantage of Phone System Direct Routing ("Direct Routing") or the Microsoft-provided Calling Plans for Office 365.</span></span>

<span data-ttu-id="13fac-125">Если вы не используете тарифные планы в Office 365, вам нужно перевести свое развертывание по своему раскладю на телефонную систему с прямой маршрутизацией в рамках обновления до Teams.</span><span class="sxs-lookup"><span data-stu-id="13fac-125">If you're not using Calling Plans in Office 365, you need to transition your enterprise voice deployment to Phone System Direct Routing as part of your upgrade to Teams.</span></span>

<span data-ttu-id="13fac-126">Дополнительные сведения можно найти в разделе [Дополнительные рекомендации по прямой маршрутизации телефонной системы](https://docs.microsoft.com/MicrosoftTeams/2-envision-make-my-service-decisions-direct-routing).</span><span class="sxs-lookup"><span data-stu-id="13fac-126">For more information, see [additional considerations for Phone System Direct Routing](https://docs.microsoft.com/MicrosoftTeams/2-envision-make-my-service-decisions-direct-routing).</span></span> <span data-ttu-id="13fac-127">Если вы планируете использовать планы звонков в Office 365, ознакомьтесь с нашими рекомендациями по [переносу ваших телефонных номеров в Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).</span><span class="sxs-lookup"><span data-stu-id="13fac-127">If you are planning to use Calling Plans in Office 365, please refer to our guidance for [transferring your phone numbers to Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).</span></span>