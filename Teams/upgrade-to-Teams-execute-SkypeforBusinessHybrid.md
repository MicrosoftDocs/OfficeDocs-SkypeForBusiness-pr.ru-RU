---
title: Обновление гибридного развертывания Skype для бизнеса до Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: Узнайте, как обновить организацию до Microsoft Teams с помощью гибридного развертывания Skype для бизнеса.
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
ms.openlocfilehash: 67bb6c10bb8cc5f37d332459d8e147f4f626497d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802349"
---
# <a name="upgrade-from-a-skype-for-business-hybrid-deployment-to-teams"></a><span data-ttu-id="b28fd-103">Обновление гибридного развертывания Skype для бизнеса до Teams</span><span class="sxs-lookup"><span data-stu-id="b28fd-103">Upgrade from a Skype for Business hybrid deployment to Teams</span></span>

<span data-ttu-id="b28fd-104">![Этапы пути обновления с акцентом на этапе развертывания и реализации](media/upgrade-banner-deployment.png "Этапы пути обновления с акцентом на этапе развертывания и реализации")</span><span class="sxs-lookup"><span data-stu-id="b28fd-104">![Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage](media/upgrade-banner-deployment.png "Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage")</span></span>

<span data-ttu-id="b28fd-105">Эта статья является частью этапа развертывания и реализации, которое вы начинаете.</span><span class="sxs-lookup"><span data-stu-id="b28fd-105">This article is part of Deployment and Implementation stage of your upgrade journey.</span></span> <span data-ttu-id="b28fd-106">Прежде чем продолжается, подтвердим, что вы выполнили следующие действия:</span><span class="sxs-lookup"><span data-stu-id="b28fd-106">Before proceeding, confirm that you've completed the following activities:</span></span>

- [<span data-ttu-id="b28fd-107">Привлечение заинтересованных лиц проекта</span><span class="sxs-lookup"><span data-stu-id="b28fd-107">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
- [<span data-ttu-id="b28fd-108">Определение области проекта</span><span class="sxs-lookup"><span data-stu-id="b28fd-108">Defined your project scope</span></span>](https://aka.ms/SkypetoTeams-Scope)
- [<span data-ttu-id="b28fd-109">Понимание сосуществования и совместной работы Skype для бизнеса и Teams</span><span class="sxs-lookup"><span data-stu-id="b28fd-109">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](https://aka.ms/SkypeToTeams-Coexist)
- [<span data-ttu-id="b28fd-110">Выбранный путь обновления</span><span class="sxs-lookup"><span data-stu-id="b28fd-110">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [<span data-ttu-id="b28fd-111">Подготовлена среда</span><span class="sxs-lookup"><span data-stu-id="b28fd-111">Prepared your environment</span></span>](https://aka.ms/SkypeToTeams-TechnicalReadiness)
- [<span data-ttu-id="b28fd-112">Подготовив организацию</span><span class="sxs-lookup"><span data-stu-id="b28fd-112">Prepared your organization</span></span>](https://aka.ms/SkypeToTeams-UserReadiness)
- [<span data-ttu-id="b28fd-113">Проводится пилотный проект</span><span class="sxs-lookup"><span data-stu-id="b28fd-113">Conducted a pilot</span></span>](https://aka.ms/SkypeToTeams-Pilot)

<span data-ttu-id="b28fd-114">Следуйте указаниям в этой статье, если вы развернули Локальное приложение Skype для бизнеса или Microsoft Lync и настроили его в гибридном развертывании с вашей организацией Microsoft 365 или Office 365 и хотите перейти на Teams выборочно — с использованием нескольких режимов сосуществования или в случае всех.</span><span class="sxs-lookup"><span data-stu-id="b28fd-114">Follow the guidance in this article if you've deployed Skype for Business or Microsoft Lync on-premises and configured it in a hybrid deployment with your Microsoft 365 or Office 365 organization, and your organization wants to upgrade to Teams either selectively—by using multiple coexistence modes—or all-in.</span></span> <span data-ttu-id="b28fd-115">Для обновления необходимо перенести пользователей в Skype для бизнеса Online (если они еще не были дома в Интернете), а затем назначить им соответствующий режим совместной работы и обновления.</span><span class="sxs-lookup"><span data-stu-id="b28fd-115">For either upgrade journey, you need to move your users to Skype for Business Online (if they aren't already homed online) and then assign them the appropriate coexistence and upgrade mode.</span></span>

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]

## <a name="step-1-move-users-to-skype-for-business-online"></a><span data-ttu-id="b28fd-116">Шаг 1. Перемещение пользователей в Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="b28fd-116">Step 1: Move users to Skype for Business Online</span></span>

<span data-ttu-id="b28fd-117">Этот шаг относится к пользователям, которые сейчас находятся в локальной сети.</span><span class="sxs-lookup"><span data-stu-id="b28fd-117">This step applies to users who are currently homed on-premises.</span></span> <span data-ttu-id="b28fd-118">Дополнительные сведения о перемещении этих пользователей в Skype для бизнеса Online см. в теме "Перемещение пользователей из локальной сети в [Skype для бизнеса Online".](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online)</span><span class="sxs-lookup"><span data-stu-id="b28fd-118">For more information about moving these users to Skype for Business Online, see [Move users from on -premises to Skype for Business Online](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online).</span></span>

## <a name="step-2-assign-a-coexistence-and-upgrade-mode"></a><span data-ttu-id="b28fd-119">Шаг 2. Назначение режима сосуществования и обновления</span><span class="sxs-lookup"><span data-stu-id="b28fd-119">Step 2: Assign a coexistence and upgrade mode</span></span>

<span data-ttu-id="b28fd-120">После того как вы переместите пользователей в Skype для бизнеса Online, вы можете назначить им соответствующий режим сосуществования в зависимости от выбранного в организации пути обновления.</span><span class="sxs-lookup"><span data-stu-id="b28fd-120">After you've moved your users to Skype for Business Online, you can assign them the appropriate coexistence mode based on the upgrade journey that your organization has chosen.</span></span> <span data-ttu-id="b28fd-121">Дополнительные сведения см. в настройках сосуществования и обновления [и](https://aka.ms/SkypeToTeams-SetCoexistence) [TeamsUpgradePolicy,](upgrade-to-teams-on-prem-tools.md)управляющих миграцией и сосуществованием.</span><span class="sxs-lookup"><span data-stu-id="b28fd-121">For more information, see [Setting your coexistence and upgrade settings](https://aka.ms/SkypeToTeams-SetCoexistence) and [TeamsUpgradePolicy: managing migration and coexistence](upgrade-to-teams-on-prem-tools.md).</span></span>

> [!NOTE]
> <span data-ttu-id="b28fd-122">С помощью Skype для бизнеса Server 2019 и будущим накопительным обновлением Skype для бизнеса Server 2015 вы сможете выполнить этапы 1 (перемещение пользователей в Skype для бизнеса Online) и шаг 2 (обновление пользователей до Teams) одним шагом.</span><span class="sxs-lookup"><span data-stu-id="b28fd-122">With Skype for Business Server 2019 and a future cumulative update of Skype for Business Server 2015, you'll be able to perform Step 1 (moving users to Skype for Business Online) and Step 2 (upgrade users to Teams) in a single step.</span></span> <span data-ttu-id="b28fd-123">Дополнительные сведения будут предоставлены после выпуска Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="b28fd-123">More information will be provided after Skype for Business Server 2019 is released.</span></span>

## <a name="phone-system-and-teams-upgrade"></a><span data-ttu-id="b28fd-124">Обновление телефонной системы и Teams</span><span class="sxs-lookup"><span data-stu-id="b28fd-124">Phone System and Teams upgrade</span></span>

<span data-ttu-id="b28fd-125">Если вы переходите с гибридного развертывания Skype для бизнеса на телефонную систему с планами звонков, а вашим поставщиком услуг телефонной сети ЗВОНКОВ будет Майкрософт и предполагается, что вы выполнили перенос номеров телефонов, при обновлении пользователей в Teams входящие звонки по STN будут автоматически переносимы в Teams.</span><span class="sxs-lookup"><span data-stu-id="b28fd-125">If you're transitioning your Skype for Business hybrid deployment to Phone System with Calling Plans and Microsoft will be your public switched telephone network (PSTN) provider—and assuming that you've completed the phone number porting—upgrading your users to Teams will automatically transition inbound PSTN calling to Teams.</span></span>

<span data-ttu-id="b28fd-126">Если планы звонков недоступны или вы намерены использовать существующего поставщика услуг связи через ПС, вам необходимо перейти с корпоративного голосового развертывания (или гибридного голосового развертывания, которое использует существующее локальное развертывание или Cloud Connector Edition) на прямую маршрутизовку телефонной системы Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="b28fd-126">If Calling Plans isn't available or you intend to use your existing PSTN connectivity provider, you need to transition your enterprise voice deployment—or hybrid voice deployment that uses your existing on-premises deployment or Cloud Connector Edition—to Microsoft Phone System Direct Routing.</span></span> <span data-ttu-id="b28fd-127">Чтобы обновить пользователей до Teams, см. дополнительные соображения по прямой маршрутике телефонной [системы.](2-envision-make-my-service-decisions-direct-routing.md)</span><span class="sxs-lookup"><span data-stu-id="b28fd-127">To upgrade your users to Teams, see the [additional considerations for Phone System Direct Routing](2-envision-make-my-service-decisions-direct-routing.md).</span></span>
