---
title: Обновление гибридного развертывания Skype для бизнеса в Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: Сведения о том, как обновить организационную структуру до Microsoft Teams с помощью гибридного развертывания Skype для бизнеса.
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
ms.openlocfilehash: 72786dc2ef5cefe7c3c87c5a376cc01d93a2c22c
ms.sourcegitcommit: b07938c0b6edafacaeaaef205a1be00c4c1693ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/16/2020
ms.locfileid: "47940519"
---
# <a name="upgrade-from-a-skype-for-business-hybrid-deployment-to-teams"></a><span data-ttu-id="b1f2a-103">Переход с гибридного развертывания Skype для бизнеса на Teams</span><span class="sxs-lookup"><span data-stu-id="b1f2a-103">Upgrade from a Skype for Business hybrid deployment to Teams</span></span>

<span data-ttu-id="b1f2a-104">![Этапы поездки на обновление, акцент на этапе развертывания и реализации](media/upgrade-banner-deployment.png "Этапы поездки на обновление, акцент на этапе развертывания и реализации")</span><span class="sxs-lookup"><span data-stu-id="b1f2a-104">![Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage](media/upgrade-banner-deployment.png "Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage")</span></span>

<span data-ttu-id="b1f2a-105">Эта статья является частью стадии развертывания и внедрения вашего путешествия по обновлению.</span><span class="sxs-lookup"><span data-stu-id="b1f2a-105">This article is part of Deployment and Implementation stage of your upgrade journey.</span></span> <span data-ttu-id="b1f2a-106">Перед продолжением убедитесь, что выполнены следующие действия:</span><span class="sxs-lookup"><span data-stu-id="b1f2a-106">Before proceeding, confirm that you've completed the following activities:</span></span>

- [<span data-ttu-id="b1f2a-107">Вовлеченные заинтересованные лица в проект</span><span class="sxs-lookup"><span data-stu-id="b1f2a-107">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
- [<span data-ttu-id="b1f2a-108">Определение области охвата проекта</span><span class="sxs-lookup"><span data-stu-id="b1f2a-108">Defined your project scope</span></span>](https://aka.ms/SkypetoTeams-Scope)
- [<span data-ttu-id="b1f2a-109">Сосуществование и взаимодействие Skype для бизнеса и рабочих групп</span><span class="sxs-lookup"><span data-stu-id="b1f2a-109">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](https://aka.ms/SkypeToTeams-Coexist)
- [<span data-ttu-id="b1f2a-110">Выбрано путешествие с обновлением</span><span class="sxs-lookup"><span data-stu-id="b1f2a-110">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [<span data-ttu-id="b1f2a-111">Подготовка среды</span><span class="sxs-lookup"><span data-stu-id="b1f2a-111">Prepared your environment</span></span>](https://aka.ms/SkypeToTeams-TechnicalReadiness)
- [<span data-ttu-id="b1f2a-112">Подготовка Организации</span><span class="sxs-lookup"><span data-stu-id="b1f2a-112">Prepared your organization</span></span>](https://aka.ms/SkypeToTeams-UserReadiness)
- [<span data-ttu-id="b1f2a-113">Пробные испытания</span><span class="sxs-lookup"><span data-stu-id="b1f2a-113">Conducted a pilot</span></span>](https://aka.ms/SkypeToTeams-Pilot)

<span data-ttu-id="b1f2a-114">Следуйте указаниям, приведенным в этой статье, если вы развернули Skype для бизнеса или Microsoft Lync в локальной среде и настроили ее в гибридном развертывании с помощью Microsoft 365 или Office 365, и ваша организация хочет выборочно перейти на Teams, используя несколько режимов сосуществования или все.</span><span class="sxs-lookup"><span data-stu-id="b1f2a-114">Follow the guidance in this article if you've deployed Skype for Business or Microsoft Lync on-premises and configured it in a hybrid deployment with your Microsoft 365 or Office 365 organization, and your organization wants to upgrade to Teams either selectively—by using multiple coexistence modes—or all-in.</span></span> <span data-ttu-id="b1f2a-115">Если вы хотите провести обновление, вам нужно будет переносить пользователей в Skype для бизнеса Online (если они еще не подключены к сети), а затем назначить им подходящий режим сосуществования и обновления.</span><span class="sxs-lookup"><span data-stu-id="b1f2a-115">For either upgrade journey, you need to move your users to Skype for Business Online (if they aren't already homed online) and then assign them the appropriate coexistence and upgrade mode.</span></span>

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]

## <a name="step-1-move-users-to-skype-for-business-online"></a><span data-ttu-id="b1f2a-116">Шаг 1: перемещение пользователей в Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="b1f2a-116">Step 1: Move users to Skype for Business Online</span></span>

<span data-ttu-id="b1f2a-117">Это действие распространяется на пользователей, которые в настоящее время размещены в локальной среде.</span><span class="sxs-lookup"><span data-stu-id="b1f2a-117">This step applies to users who are currently homed on-premises.</span></span> <span data-ttu-id="b1f2a-118">Дополнительные сведения о переносе этих пользователей в Skype для бизнеса Online можно найти [в разделе Перемещение пользователей из локальной сети в Skype для бизнеса Online](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online).</span><span class="sxs-lookup"><span data-stu-id="b1f2a-118">For more information about moving these users to Skype for Business Online, see [Move users from on -premises to Skype for Business Online](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online).</span></span>

## <a name="step-2-assign-a-coexistence-and-upgrade-mode"></a><span data-ttu-id="b1f2a-119">Действие 2: назначение режима сосуществования и обновления</span><span class="sxs-lookup"><span data-stu-id="b1f2a-119">Step 2: Assign a coexistence and upgrade mode</span></span>

<span data-ttu-id="b1f2a-120">После того как вы перенесли пользователей в Skype для бизнеса Online, вы можете назначить им режим совместного существования, основываясь на пути обновления, который выбрала ваша организация.</span><span class="sxs-lookup"><span data-stu-id="b1f2a-120">After you've moved your users to Skype for Business Online, you can assign them the appropriate coexistence mode based on the upgrade journey that your organization has chosen.</span></span> <span data-ttu-id="b1f2a-121">Дополнительные сведения можно найти [в статье Настройка параметров сосуществования и обновления](https://aka.ms/SkypeToTeams-SetCoexistence) и [TeamsUpgradePolicy: управление миграцией и сосуществованием](upgrade-to-teams-on-prem-tools.md).</span><span class="sxs-lookup"><span data-stu-id="b1f2a-121">For more information, see [Setting your coexistence and upgrade settings](https://aka.ms/SkypeToTeams-SetCoexistence) and [TeamsUpgradePolicy: managing migration and coexistence](upgrade-to-teams-on-prem-tools.md).</span></span>

> [!NOTE]
> <span data-ttu-id="b1f2a-122">С помощью Skype для бизнеса Server 2019 и будущего накопительного обновления для Skype для бизнеса Server 2015 вы сможете выполнить шаг 1 (перемещение пользователей в Skype для бизнеса Online) и шаг 2 (обновление пользователей до Teams).</span><span class="sxs-lookup"><span data-stu-id="b1f2a-122">With Skype for Business Server 2019 and a future cumulative update of Skype for Business Server 2015, you'll be able to perform Step 1 (moving users to Skype for Business Online) and Step 2 (upgrade users to Teams) in a single step.</span></span> <span data-ttu-id="b1f2a-123">Дополнительные сведения будут предоставлены после выпуска Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="b1f2a-123">More information will be provided after Skype for Business Server 2019 is released.</span></span>

## <a name="phone-system-and-teams-upgrade"></a><span data-ttu-id="b1f2a-124">Обновление телефонной системы и команды</span><span class="sxs-lookup"><span data-stu-id="b1f2a-124">Phone System and Teams upgrade</span></span>

<span data-ttu-id="b1f2a-125">Если вы переносите гибридное развертывание Skype для бизнеса в телефонную систему с помощью планов звонков, а Microsoft является поставщиком услуг коммутируемой телефонной сети (PSTN) и предполагает, что вы выполнили перенос номеров телефонов, то после обновления ваших пользователей в Teams будут автоматически переноситься входящие звонки в Teams по протоколу PSTN.</span><span class="sxs-lookup"><span data-stu-id="b1f2a-125">If you're transitioning your Skype for Business hybrid deployment to Phone System with Calling Plans and Microsoft will be your public switched telephone network (PSTN) provider—and assuming that you've completed the phone number porting—upgrading your users to Teams will automatically transition inbound PSTN calling to Teams.</span></span>

<span data-ttu-id="b1f2a-126">Если тарифные планы недоступны или вы планируете использовать существующий поставщик подключений по протоколу PSTN, вам нужно перенести свое корпоративное развертывание (или гибридное развертывание для голосовой связи), которое использует существующее локальное развертывание или облачное издание, в прямом маршруте Microsoft Phone System.</span><span class="sxs-lookup"><span data-stu-id="b1f2a-126">If Calling Plans isn't available or you intend to use your existing PSTN connectivity provider, you need to transition your enterprise voice deployment—or hybrid voice deployment that uses your existing on-premises deployment or Cloud Connector Edition—to Microsoft Phone System Direct Routing.</span></span> <span data-ttu-id="b1f2a-127">Чтобы обновить пользователей до Teams, ознакомьтесь с [дополнительными сведениями о прямой маршрутизации для телефонной системы](2-envision-make-my-service-decisions-direct-routing.md).</span><span class="sxs-lookup"><span data-stu-id="b1f2a-127">To upgrade your users to Teams, see the [additional considerations for Phone System Direct Routing](2-envision-make-my-service-decisions-direct-routing.md).</span></span>
