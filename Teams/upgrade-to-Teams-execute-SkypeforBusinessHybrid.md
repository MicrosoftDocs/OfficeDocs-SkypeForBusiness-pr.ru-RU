---
title: Обновление Skype для бизнеса гибридного развертывания до Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: Узнайте, как обновить организацию до Microsoft Teams из гибридного Skype для бизнеса развертывания.
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
ms.openlocfilehash: 97725e7a9790f47f9789366567981f0167fdd806
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51104025"
---
# <a name="upgrade-from-a-skype-for-business-hybrid-deployment-to-teams"></a><span data-ttu-id="132d6-103">Обновление гибридного Skype для бизнеса до Teams</span><span class="sxs-lookup"><span data-stu-id="132d6-103">Upgrade from a Skype for Business hybrid deployment to Teams</span></span>

<span data-ttu-id="132d6-104">![Этапы пути обновления с акцентом на этапе развертывания и внедрения](media/upgrade-banner-deployment.png "Этапы пути обновления с акцентом на этапе развертывания и внедрения")</span><span class="sxs-lookup"><span data-stu-id="132d6-104">![Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage](media/upgrade-banner-deployment.png "Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage")</span></span>

<span data-ttu-id="132d6-105">Эта статья является частью этапа развертывания и реализации, на который вы входите.</span><span class="sxs-lookup"><span data-stu-id="132d6-105">This article is part of Deployment and Implementation stage of your upgrade journey.</span></span> <span data-ttu-id="132d6-106">Прежде чем при этом подтверждать, что вы выполнили следующие действия:</span><span class="sxs-lookup"><span data-stu-id="132d6-106">Before proceeding, confirm that you've completed the following activities:</span></span>

- [<span data-ttu-id="132d6-107">Привлечение заинтересованных лиц по проекту</span><span class="sxs-lookup"><span data-stu-id="132d6-107">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
- [<span data-ttu-id="132d6-108">Определение области проекта</span><span class="sxs-lookup"><span data-stu-id="132d6-108">Defined your project scope</span></span>](./upgrade-define-project-scope.md)
- [<span data-ttu-id="132d6-109">Понятное сосуществование и совместное Skype для бизнеса и Teams</span><span class="sxs-lookup"><span data-stu-id="132d6-109">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](./teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [<span data-ttu-id="132d6-110">Выбор пути обновления</span><span class="sxs-lookup"><span data-stu-id="132d6-110">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [<span data-ttu-id="132d6-111">Подготовьте свою среду</span><span class="sxs-lookup"><span data-stu-id="132d6-111">Prepared your environment</span></span>](./upgrade-prepare-environment.md)
- [<span data-ttu-id="132d6-112">Подготовленные организации</span><span class="sxs-lookup"><span data-stu-id="132d6-112">Prepared your organization</span></span>](./upgrade-prepare-organization.md)
- [<span data-ttu-id="132d6-113">Пилотный проект</span><span class="sxs-lookup"><span data-stu-id="132d6-113">Conducted a pilot</span></span>](./pilot-essentials.md)

<span data-ttu-id="132d6-114">Следуйте указаниям из этой статьи, если вы развернули локальное развертывание Skype для бизнеса или Microsoft Lync и настроили его в гибридном развертывании с вашей организацией Microsoft 365 или Office 365 и хотите перейти на Teams выборочно — с помощью нескольких режимов совместной работы или в режиме "вся".</span><span class="sxs-lookup"><span data-stu-id="132d6-114">Follow the guidance in this article if you've deployed Skype for Business or Microsoft Lync on-premises and configured it in a hybrid deployment with your Microsoft 365 or Office 365 organization, and your organization wants to upgrade to Teams either selectively—by using multiple coexistence modes—or all-in.</span></span> <span data-ttu-id="132d6-115">Для любого из этих обновлений необходимо переместить пользователей на веб-сайт Skype для бизнеса Online (если они еще не были дома в Интернете), а затем назначить им соответствующий режим совместной работы и обновления.</span><span class="sxs-lookup"><span data-stu-id="132d6-115">For either upgrade journey, you need to move your users to Skype for Business Online (if they aren't already homed online) and then assign them the appropriate coexistence and upgrade mode.</span></span>

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]

## <a name="step-1-move-users-to-skype-for-business-online"></a><span data-ttu-id="132d6-116">Шаг 1. Перемещение пользователей в Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="132d6-116">Step 1: Move users to Skype for Business Online</span></span>

<span data-ttu-id="132d6-117">Этот шаг относится к пользователям, которые сейчас находятся в локальной сети.</span><span class="sxs-lookup"><span data-stu-id="132d6-117">This step applies to users who are currently homed on-premises.</span></span> <span data-ttu-id="132d6-118">Дополнительные сведения о перемещении этих пользователей в Skype для бизнеса Online см. в этой Skype для бизнеса [Online.](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online)</span><span class="sxs-lookup"><span data-stu-id="132d6-118">For more information about moving these users to Skype for Business Online, see [Move users from on -premises to Skype for Business Online](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online).</span></span>

## <a name="step-2-assign-a-coexistence-and-upgrade-mode"></a><span data-ttu-id="132d6-119">Шаг 2. Назначение режима сосуществования и обновления</span><span class="sxs-lookup"><span data-stu-id="132d6-119">Step 2: Assign a coexistence and upgrade mode</span></span>

<span data-ttu-id="132d6-120">После того как вы переместите пользователей в Skype для бизнеса Online, вы можете назначить им соответствующий режим сосуществования в зависимости от пути обновления, выбранного вашей организацией.</span><span class="sxs-lookup"><span data-stu-id="132d6-120">After you've moved your users to Skype for Business Online, you can assign them the appropriate coexistence mode based on the upgrade journey that your organization has chosen.</span></span> <span data-ttu-id="132d6-121">Дополнительные сведения [](./setting-your-coexistence-and-upgrade-settings.md) см. в настройках сосуществования и обновления [и TeamsUpgradePolicy:](upgrade-to-teams-on-prem-tools.md)управление миграцией и сосуществованием.</span><span class="sxs-lookup"><span data-stu-id="132d6-121">For more information, see [Setting your coexistence and upgrade settings](./setting-your-coexistence-and-upgrade-settings.md) and [TeamsUpgradePolicy: managing migration and coexistence](upgrade-to-teams-on-prem-tools.md).</span></span>

> [!NOTE]
> <span data-ttu-id="132d6-122">В Skype для бизнеса Server 2019 г. и в будущем накопительном обновлении Skype для бизнеса Server 2015 вы сможете выполнить шаг 1 (перемещение пользователей в Skype для бизнеса Online) и Шаг 2 (обновление пользователей до Teams) за один шаг.</span><span class="sxs-lookup"><span data-stu-id="132d6-122">With Skype for Business Server 2019 and a future cumulative update of Skype for Business Server 2015, you'll be able to perform Step 1 (moving users to Skype for Business Online) and Step 2 (upgrade users to Teams) in a single step.</span></span> <span data-ttu-id="132d6-123">Дополнительные сведения будут предоставлены Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="132d6-123">More information will be provided after Skype for Business Server 2019 is released.</span></span>

## <a name="phone-system-and-teams-upgrade"></a><span data-ttu-id="132d6-124">телефонная система и Teams обновления</span><span class="sxs-lookup"><span data-stu-id="132d6-124">Phone System and Teams upgrade</span></span>

<span data-ttu-id="132d6-125">Если вы переходите с гибридного развертывания Skype для бизнеса на телефонная система с помощью планов звонков, а поставщиком услуг телефонной сети общего звонков (STN) будет Майкрософт, а при условии, что перенос номеров телефонов завершен, обновление пользователей до Teams автоматически переключит входящие вызовы через Teams.</span><span class="sxs-lookup"><span data-stu-id="132d6-125">If you're transitioning your Skype for Business hybrid deployment to Phone System with Calling Plans and Microsoft will be your public switched telephone network (PSTN) provider—and assuming that you've completed the phone number porting—upgrading your users to Teams will automatically transition inbound PSTN calling to Teams.</span></span>

<span data-ttu-id="132d6-126">Если планы звонков недоступны или вы собираетесь использовать существующего поставщика услуг связи через STN, необходимо перейти с корпоративного голосового развертывания (или гибридного голосового развертывания, которое использует существующее локальное развертывание или Cloud Connector Edition) на Телефон (Майкрософт) Direct Routing.</span><span class="sxs-lookup"><span data-stu-id="132d6-126">If Calling Plans isn't available or you intend to use your existing PSTN connectivity provider, you need to transition your enterprise voice deployment—or hybrid voice deployment that uses your existing on-premises deployment or Cloud Connector Edition—to Microsoft Phone System Direct Routing.</span></span> <span data-ttu-id="132d6-127">Чтобы обновить пользователей до Teams, см. дополнительные телефонная система [прямой маршрутии.](./direct-routing-landing-page.md)</span><span class="sxs-lookup"><span data-stu-id="132d6-127">To upgrade your users to Teams, see the [additional considerations for Phone System Direct Routing](./direct-routing-landing-page.md).</span></span>