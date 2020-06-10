---
title: Переход с локальной среды Skype для бизнеса на Teams
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 01/09/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: Сведения о том, как обновить организационную структуру до Microsoft Teams с помощью локального развертывания Skype для бизнеса.
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
ms.openlocfilehash: 4cd9b38f09d4936d2db895f3ae8861bcf65b8a4e
ms.sourcegitcommit: f586d2765195dbd5b7cf65615a03a1cb098c5466
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "44666031"
---
# <a name="upgrade-from-skype-for-business-on-premises-to-teams"></a><span data-ttu-id="0bb6b-103">Переход с Skype для бизнеса локально на Teams</span><span class="sxs-lookup"><span data-stu-id="0bb6b-103">Upgrade from Skype for Business on-premises to Teams</span></span>

<span data-ttu-id="0bb6b-104">![Обновление схемы поездки, акцент на развертывании и реализации](media/upgrade-banner-deployment.png "Этапы поездки на обновление, акцент на этапе развертывания и реализации")</span><span class="sxs-lookup"><span data-stu-id="0bb6b-104">![Upgrade journey diagram, emphasizing Deployment and Implementation](media/upgrade-banner-deployment.png "Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage")</span></span>

<span data-ttu-id="0bb6b-105">Эта статья является частью стадии развертывания и внедрения вашего путешествия по обновлению.</span><span class="sxs-lookup"><span data-stu-id="0bb6b-105">This article is part of Deployment and Implementation stage of your upgrade journey.</span></span> <span data-ttu-id="0bb6b-106">Перед продолжением убедитесь, что выполнены следующие действия:</span><span class="sxs-lookup"><span data-stu-id="0bb6b-106">Before proceeding, confirm that you've completed the following activities:</span></span>

-   [<span data-ttu-id="0bb6b-107">Вовлеченные заинтересованные лица в проект</span><span class="sxs-lookup"><span data-stu-id="0bb6b-107">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
-   [<span data-ttu-id="0bb6b-108">Определение области охвата проекта</span><span class="sxs-lookup"><span data-stu-id="0bb6b-108">Defined your project scope</span></span>](https://aka.ms/SkypetoTeams-Scope)
-   [<span data-ttu-id="0bb6b-109">Сосуществование и взаимодействие Skype для бизнеса и рабочих групп</span><span class="sxs-lookup"><span data-stu-id="0bb6b-109">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](https://aka.ms/SkypeToTeams-Coexist)
-   [<span data-ttu-id="0bb6b-110">Выбрано путешествие с обновлением</span><span class="sxs-lookup"><span data-stu-id="0bb6b-110">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
-   [<span data-ttu-id="0bb6b-111">Подготовка среды</span><span class="sxs-lookup"><span data-stu-id="0bb6b-111">Prepared your environment</span></span>](https://aka.ms/SkypeToTeams-TechnicalReadiness)
-   [<span data-ttu-id="0bb6b-112">Подготовка Организации</span><span class="sxs-lookup"><span data-stu-id="0bb6b-112">Prepared your organization</span></span>](https://aka.ms/SkypeToTeams-UserReadiness)
-   [<span data-ttu-id="0bb6b-113">Пробные испытания</span><span class="sxs-lookup"><span data-stu-id="0bb6b-113">Conducted a pilot</span></span>](https://aka.ms/SkypeToTeams-Pilot)

<span data-ttu-id="0bb6b-114">Если вы развернули Skype для бизнеса Server или Microsoft Lync в локальной среде, а ваша организация хочет перейти на Teams, следуйте указаниям в этой статье.</span><span class="sxs-lookup"><span data-stu-id="0bb6b-114">If you've deployed Skype for Business Server or Microsoft Lync on-premises and your organization wants to upgrade to Teams, follow the guidance in this article.</span></span> <span data-ttu-id="0bb6b-115">Вам нужно настроить гибридное подключение к вашей организации Microsoft 365 или Office 365 и определить требования к сосуществованию, если вы перемещаете пользователей в Teams (этапы).</span><span class="sxs-lookup"><span data-stu-id="0bb6b-115">You need to set up hybrid connectivity with your Microsoft 365 or Office 365 organization, and determine coexistence requirements if you are moving your users to Teams in phases.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="0bb6b-116">Поддержка Skype для бизнеса Online будет прекращена 31 июля 2021 г., после чего эта служба больше не будет доступна.</span><span class="sxs-lookup"><span data-stu-id="0bb6b-116">Skype for Business Online will be retired on July 31, 2021, after which it will no longer be accessible or supported.</span></span> <span data-ttu-id="0bb6b-117">Чтобы повысить эффективность реализации льготы и убедиться в том, что в вашей организации установлено правильное время для внедрения вашего обновления, мы рекомендуем начать путешествие в Microsoft Teams уже сегодня.</span><span class="sxs-lookup"><span data-stu-id="0bb6b-117">To maximize benefit realization and ensure your organization has proper time to implement your upgrade, we encourage you to begin your journey to Microsoft Teams today.</span></span> <span data-ttu-id="0bb6b-118">Помните о том, что успешное обновление ориентировано на техническую и пользовательскую готовность, поэтому не забудьте использовать руководство для навигации в Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="0bb6b-118">Remember that a successful upgrade aligns technical and user readiness, so be sure to leverage the guidance herein as you navigate your journey to Microsoft Teams.</span></span>

## <a name="step-1-configure-hybrid-connectivity"></a><span data-ttu-id="0bb6b-119">Действие 1: настройка гибридного подключения</span><span class="sxs-lookup"><span data-stu-id="0bb6b-119">Step 1: Configure hybrid connectivity</span></span> 

<span data-ttu-id="0bb6b-120">Ключевым условием для обновления локальных пользователей до Teams является настройка гибридного подключения для локального развертывания Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="0bb6b-120">The key prerequisite for upgrading your on-premises users to Teams is to configure hybrid connectivity for your Skype for Business Server on-premises deployment.</span></span> 

<span data-ttu-id="0bb6b-121">Начните с создания [плана гибридного подключения](https://docs.microsoft.com/SkypeForBusiness/hybrid/plan-hybrid-connectivity?toc=/SkypeForBusiness/sfbhybridtoc/toc.json) и следуйте задачам, описанным в разделе [Настройка гибридного подключения](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity).</span><span class="sxs-lookup"><span data-stu-id="0bb6b-121">Start by reading [Plan hybrid connectivity](https://docs.microsoft.com/SkypeForBusiness/hybrid/plan-hybrid-connectivity?toc=/SkypeForBusiness/sfbhybridtoc/toc.json) and then follow the tasks outlined in [Configure hybrid connectivity](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity).</span></span>


## <a name="step-2-set-transitional-coexistence-mode-optional"></a><span data-ttu-id="0bb6b-122">Шаг 2: Настройка режима переходного сосуществования (необязательно)</span><span class="sxs-lookup"><span data-stu-id="0bb6b-122">Step 2: Set transitional coexistence mode (optional)</span></span>

<span data-ttu-id="0bb6b-123">Сосуществование и взаимодействие между клиентами и пользователями в Skype для бизнеса и Teams определяются режимами обновления Teams.</span><span class="sxs-lookup"><span data-stu-id="0bb6b-123">Coexistence and interoperability between Skype for Business and Teams clients and users are defined by Teams Upgrade modes.</span></span>  <span data-ttu-id="0bb6b-124">По умолчанию организации находятся в режиме острова, что позволяет пользователям одновременно использовать как команды, так и клиенты Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="0bb6b-124">By default, organizations are in Islands mode, which allows users to use both Teams and Skype for Business clients side by side.</span></span>

<span data-ttu-id="0bb6b-125">Для Организации, перемещающейся в Teams, режим TeamsOnly является конечным местом для каждого пользователя, хотя не все пользователи должны быть назначены TeamsOnly (или другим режимам) одновременно.</span><span class="sxs-lookup"><span data-stu-id="0bb6b-125">For an organization moving to Teams, TeamsOnly mode is the final destination for each user--though not all users need to be assigned TeamsOnly (or any other mode) at the same time.</span></span>

<span data-ttu-id="0bb6b-126">До тех пор, пока пользователи работают в режиме TeamsOnly, организации могут использовать любой из режимов сосуществования Skype для бизнеса, чтобы обеспечить предсказуемую связь между пользователями в режиме TeamsOnly и пользователями, которые еще не подключены.</span><span class="sxs-lookup"><span data-stu-id="0bb6b-126">Prior to users reaching TeamsOnly mode, organizations can optionally use any of the Skype for Business coexistence modes to ensure predictable communication between users who are in TeamsOnly mode and users who aren't yet.</span></span>  <span data-ttu-id="0bb6b-127">Цель режимов сосуществования Skype для бизнеса (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings) – это простой и предсказуемый опыт конечных пользователей в том, что в Организации переход с Skype для бизнеса на Teams.</span><span class="sxs-lookup"><span data-stu-id="0bb6b-127">The purpose of the Skype for Business coexistence modes (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings) is to provide a simple, predictable experience for end users as organizations transition from Skype for Business to Teams.</span></span> 

<span data-ttu-id="0bb6b-128">Когда пользователь входит в любой из режимов Skype для бизнеса, все входящие разговоры и звонки перенаправляются клиенту Skype для бизнеса пользователя.</span><span class="sxs-lookup"><span data-stu-id="0bb6b-128">When a user is in any of the Skype for Business modes, all incoming chats and calls are routed to the user's Skype for Business client.</span></span> <span data-ttu-id="0bb6b-129">Чтобы избежать путаницы и удостовериться в том, что функция маршрутизации, вызов и чат в клиенте Teams отключена, когда пользователь входит в любой из режимов Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="0bb6b-129">To avoid end-user confusion and ensure proper routing, calling and chat functionality in the Teams client is disabled when a user is in any of the Skype for Business modes.</span></span> <span data-ttu-id="0bb6b-130">Аналогичным образом планирование собраний в Teams явным образом отключается, если пользователи находятся в режимах SfBOnly или SfBWithTeamsCollab, и явно включаются, когда пользователь находится в режиме SfBWithTeamsCollabAndMeetings.</span><span class="sxs-lookup"><span data-stu-id="0bb6b-130">Similarly, meeting scheduling in Teams is explicitly disabled when users are in the SfBOnly or SfBWithTeamsCollab modes, and explicitly enabled when a user is in the SfBWithTeamsCollabAndMeetings mode.</span></span>

<span data-ttu-id="0bb6b-131">В зависимости от ваших требований вы можете присвоить соответствующий режим совместного существования, основываясь на пути обновления, который выбрала ваша организация.</span><span class="sxs-lookup"><span data-stu-id="0bb6b-131">Depending on your requirements, you can assign the appropriate coexistence mode based on the upgrade path that your organization has chosen.</span></span> <span data-ttu-id="0bb6b-132">Дополнительные сведения можно найти в [статье Руководство по миграции и взаимодействию для организаций, использующих Teams вместе со Skype для бизнеса](migration-interop-guidance-for-teams-with-skype.md) и [настройку параметров сосуществования и обновления](https://aka.ms/SkypeToTeams-SetCoexistence).</span><span class="sxs-lookup"><span data-stu-id="0bb6b-132">For more information, see [Migration and interoperability guidance for organizations using Teams together with Skype for Business](migration-interop-guidance-for-teams-with-skype.md) and [Setting your coexistence and upgrade settings](https://aka.ms/SkypeToTeams-SetCoexistence).</span></span>


## <a name="step-3-move-users-from-skype-for-business-on-premises-to-teams-only"></a><span data-ttu-id="0bb6b-133">Шаг 3: перемещение пользователей из Skype для бизнеса в локальной среде только в Teams</span><span class="sxs-lookup"><span data-stu-id="0bb6b-133">Step 3: Move users from Skype for Business on-premises to Teams Only</span></span>

<span data-ttu-id="0bb6b-134">В конечном итоге вам потребуется переместить пользователей в TeamsOnlyный режим.</span><span class="sxs-lookup"><span data-stu-id="0bb6b-134">Ultimately, you'll want to move your users to TeamsOnly mode.</span></span> <span data-ttu-id="0bb6b-135">Это может включать один или два этапа в зависимости от текущей локальной среды.</span><span class="sxs-lookup"><span data-stu-id="0bb6b-135">This might involve one or two steps depending on your current on-premises environment.</span></span>  

<span data-ttu-id="0bb6b-136">Дополнительные сведения можно найти в разделе [Перемещение пользователей между локальным и облаком](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud) и [Перемещение пользователей из локальной сети в Teams](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-from-on-premises-to-teams).</span><span class="sxs-lookup"><span data-stu-id="0bb6b-136">For more information, see [Move users between on-premises and the cloud](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud) and [Move users from on-premises to Teams](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-from-on-premises-to-teams).</span></span> 



## <a name="phone-system-and-teams-upgrade"></a><span data-ttu-id="0bb6b-137">Обновление телефонной системы и команды</span><span class="sxs-lookup"><span data-stu-id="0bb6b-137">Phone System and Teams upgrade</span></span>

<span data-ttu-id="0bb6b-138">Если вы перейдете на Skype для бизнеса в телефонную систему с тарифными планами, Майкрософт будет являться поставщиком услуг телефонной сети общего пользования (PSTN).</span><span class="sxs-lookup"><span data-stu-id="0bb6b-138">If you are transitioning your Skype for Business deployment to Phone System with Calling Plans, Microsoft will be your public switched telephone network (PSTN) provider.</span></span> <span data-ttu-id="0bb6b-139">Предполагается, что вы выполнили перенос номера телефона--обновление пользователей в Teams автоматически переносит входящий звонок по протоколу PSTN в Teams.</span><span class="sxs-lookup"><span data-stu-id="0bb6b-139">Assuming that you've completed the phone number porting--upgrading your users to Teams will automatically transition inbound PSTN calling to Teams.</span></span>

<span data-ttu-id="0bb6b-140">Если вы перейдете к развертыванию Skype для бизнеса в телефонную систему, но не используете планы звонков, вам нужно перевести свое развертывание в корпоративную раскладю Microsoft Phone System.</span><span class="sxs-lookup"><span data-stu-id="0bb6b-140">If you are transitioning your Skype for Business deployment to Phone System but are not using Calling Plans, you  need to transition your enterprise voice deployment to Microsoft Phone System Direct Routing.</span></span> <span data-ttu-id="0bb6b-141">Дополнительные сведения можно найти в разделе [Прямая маршрутизация телефонной системы](direct-routing-landing-page.md).</span><span class="sxs-lookup"><span data-stu-id="0bb6b-141">For more information, see [Phone System Direct Routing](direct-routing-landing-page.md).</span></span>
