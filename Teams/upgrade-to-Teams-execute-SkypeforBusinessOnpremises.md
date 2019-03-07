---
title: Обновление Скайп для бизнеса локальных групп, корпорация Майкрософт | Развертывание | Lync
author: arachmanGitHub
ms.author: arachman
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: dearbeen
description: Вопросы, касающиеся обновления группам из Скайп for Business локальное развертывание.
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
MS.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 78c69b8fb54a430269e63836ef430d63270841f8
ms.sourcegitcommit: 85c34280977fb2c15c8a43874a20e9492bdca57f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/07/2019
ms.locfileid: "30464750"
---
<span data-ttu-id="f4afa-103">![Этапы обновления пути с акцентом на развертывание и стадии реализации] (media/upgrade-banner-deployment.png "Этапы обновления пути с акцентом на развертывание и стадии реализации")</span><span class="sxs-lookup"><span data-stu-id="f4afa-103">![Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage](media/upgrade-banner-deployment.png "Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage")</span></span>

<span data-ttu-id="f4afa-104">В этой статье является частью развертывания и внедрения этапа обновления пути.</span><span class="sxs-lookup"><span data-stu-id="f4afa-104">This article is part of Deployment and Implementation stage of your upgrade journey.</span></span> <span data-ttu-id="f4afa-105">Прежде чем продолжить, убедитесь, что вы выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="f4afa-105">Before proceeding, confirm that you’ve completed the following activities:</span></span>

- [<span data-ttu-id="f4afa-106">Прикреплено другие заинтересованные стороны проекта</span><span class="sxs-lookup"><span data-stu-id="f4afa-106">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
- [<span data-ttu-id="f4afa-107">Определенные области проекта</span><span class="sxs-lookup"><span data-stu-id="f4afa-107">Defined your project scope</span></span>](https://aka.ms/SkypetoTeams-Scope)
- [<span data-ttu-id="f4afa-108">Поняты сосуществования и взаимодействия Скайп для бизнеса и рабочих групп</span><span class="sxs-lookup"><span data-stu-id="f4afa-108">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](https://aka.ms/SkypeToTeams-Coexist)
- [<span data-ttu-id="f4afa-109">Выбранные обновления пути</span><span class="sxs-lookup"><span data-stu-id="f4afa-109">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [<span data-ttu-id="f4afa-110">Подготовка среды</span><span class="sxs-lookup"><span data-stu-id="f4afa-110">Prepared your environment</span></span>](https://aka.ms/SkypeToTeams-TechnicalReadiness)
- [<span data-ttu-id="f4afa-111">Подготовлено вашей организации</span><span class="sxs-lookup"><span data-stu-id="f4afa-111">Prepared your organization</span></span>](https://aka.ms/SkypeToTeams-UserReadiness)
- [<span data-ttu-id="f4afa-112">Проведение пилотного проекта</span><span class="sxs-lookup"><span data-stu-id="f4afa-112">Conducted a pilot</span></span>](https://aka.ms/SkypeToTeams-Pilot)

# <a name="upgrade-from-a-skype-for-business-on-premises-deployment-to-teams"></a><span data-ttu-id="f4afa-113">Обновление с Скайп для локального развертывания Business по группам</span><span class="sxs-lookup"><span data-stu-id="f4afa-113">Upgrade from a Skype for Business on-premises deployment to Teams</span></span>

<span data-ttu-id="f4afa-114">Следуйте рекомендациям в статье в этой статье, если развернута Скайп для бизнеса или Microsoft Lync локальные пользователи и организации необходимо обновить групп, либо выборочно — с помощью нескольких режимах совместная работа — или файловый.</span><span class="sxs-lookup"><span data-stu-id="f4afa-114">Follow the guidance in this article if you’ve deployed Skype for Business or Microsoft Lync on-premises and your organization wants to upgrade to Teams either selectively—by using multiple coexistence modes—or all-in.</span></span> <span data-ttu-id="f4afa-115">Первым этапом является настройка гибридного подключения с помощью клиента Office 365 и переместите пользователей Скайп для бизнеса в Интернет и назначить их соответствующие сосуществования и режим обновления.</span><span class="sxs-lookup"><span data-stu-id="f4afa-115">The first step is to set up hybrid connectivity with your Office 365 tenant, and then move your users to Skype for Business Online and assign them the appropriate coexistence and upgrade mode.</span></span>

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]

## <a name="step-1-deploy-hybrid-connectivity"></a><span data-ttu-id="f4afa-116">Шаг 1: Развертывание гибридного подключения</span><span class="sxs-lookup"><span data-stu-id="f4afa-116">Step 1: Deploy hybrid connectivity</span></span>

<span data-ttu-id="f4afa-117">Ключевые необходимые компоненты для обновления пользователей группам — для развертывания гибридного подключения.</span><span class="sxs-lookup"><span data-stu-id="f4afa-117">The key prerequisite for upgrading your users to Teams is to deploy hybrid connectivity.</span></span> <span data-ttu-id="f4afa-118">Для этого может потребоваться развертывание нового внешнего подключения для вашего существующего Скайп развертывания для бизнеса или Lync или просто Настройка гибридных связь с помощью клиента Office 365.</span><span class="sxs-lookup"><span data-stu-id="f4afa-118">This might involve deploying new external connectivity for your existing Skype for Business or Lync deployment, or simply configuring a hybrid relationship with your Office 365 tenant.</span></span>

<span data-ttu-id="f4afa-119">Дополнительные сведения можно [Развернуть гибридного подключения между Скайп Business Server и Скайп для бизнеса в Интернет](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity)</span><span class="sxs-lookup"><span data-stu-id="f4afa-119">For more information, see [Deploy hybrid connectivity between Skype for Business Server and Skype for Business Online](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity)</span></span>

## <a name="step-2-move-users-to-skype-for-business-online"></a><span data-ttu-id="f4afa-120">Шаг 2: Перемещение пользователей в Скайп для бизнеса в Интернет</span><span class="sxs-lookup"><span data-stu-id="f4afa-120">Step 2: Move users to Skype for Business Online</span></span>

<span data-ttu-id="f4afa-121">По завершении настройки гибридной перемещение пользователей в Скайп для бизнеса в Интернет.</span><span class="sxs-lookup"><span data-stu-id="f4afa-121">After you’ve completed your hybrid setup, move users to Skype for Business Online.</span></span>

<span data-ttu-id="f4afa-122">Дополнительные сведения можно [переместить пользователей из локально на Скайп для бизнеса в Интернет](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online)</span><span class="sxs-lookup"><span data-stu-id="f4afa-122">For more information, see [Move users from on premises to Skype for Business Online](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online)</span></span>

## <a name="step-3-assign-a-coexistence-and-upgrade-mode"></a><span data-ttu-id="f4afa-123">Шаг 3: Назначьте сосуществования и режим обновления</span><span class="sxs-lookup"><span data-stu-id="f4afa-123">Step 3: Assign a coexistence and upgrade mode</span></span>

<span data-ttu-id="f4afa-124">После переноса пользователей к Скайп для бизнеса в Интернет, их можно назначить соответствующие сосуществования режим по пути обновления, принято решение вашей организации.</span><span class="sxs-lookup"><span data-stu-id="f4afa-124">After you’ve moved your users to Skype for Business Online, you can assign them the appropriate coexistence mode based on the upgrade journey that your organization has chosen.</span></span> <span data-ttu-id="f4afa-125">Для получения дополнительных сведений см [Задание вашей сосуществования и параметры обновления](https://aka.ms/SkypeToTeams-SetCoexistence) и [TeamsUpgradePolicy: управление миграция и сосуществование](migration-interop-guidance-for-teams-with-skype.md#teamsupgradepolicy-managing-migration-and-co-existence).</span><span class="sxs-lookup"><span data-stu-id="f4afa-125">For more information, see [Setting your coexistence and upgrade settings](https://aka.ms/SkypeToTeams-SetCoexistence) and [TeamsUpgradePolicy: managing migration and coexistence](migration-interop-guidance-for-teams-with-skype.md#teamsupgradepolicy-managing-migration-and-co-existence).</span></span>

> [!NOTE]
> <span data-ttu-id="f4afa-126">С Скайп Business Server 2019 и будущих накопительного обновления Скайп для Business Server 2015 можно будет выполнять шаг 2 (переход на Скайп для бизнеса в Интернет) и шаг 3 (обновления пользователей группам) за один шаг.</span><span class="sxs-lookup"><span data-stu-id="f4afa-126">With Skype for Business Server 2019 and a future cumulative update of Skype for Business Server 2015, you’ll be able to perform Step 2 (moving users to Skype for Business Online) and Step 3 (upgrade users to Teams) in a single step.</span></span> <span data-ttu-id="f4afa-127">Дополнительные сведения будут предоставлены после выпуска Скайп для Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="f4afa-127">More information will be provided after Skype for Business Server 2019 is released.</span></span>

## <a name="phone-system-and-teams-upgrade"></a><span data-ttu-id="f4afa-128">Обновление телефонной системой и рабочих групп</span><span class="sxs-lookup"><span data-stu-id="f4afa-128">Phone System and Teams upgrade</span></span>

<span data-ttu-id="f4afa-129">При переносе данных вашей Скайп для локального развертывания Business от корпоративной голосовой связи для телефонной системы с помощью вызова планы и Майкрософт будет ваш поставщик телефонной сети (общего пользования PSTN), и при условии, что вы выполнили номер телефона Перенос — обновление пользователей группам автоматический переход входящих звонков ТСОП для групп.</span><span class="sxs-lookup"><span data-stu-id="f4afa-129">If you’re transitioning your Skype for Business on-premises deployment from enterprise voice to Phone System with Calling Plans and Microsoft will be your public switched telephone network (PSTN) provider—and assuming that you’ve completed the phone number porting—upgrading your users to Teams will automatically transition inbound PSTN calling to Teams.</span></span>

<span data-ttu-id="f4afa-130">Вызов планы недоступен, требуется ли перенос развертывания корпоративной голосовой связи для прямой маршрутизации Microsoft телефонной системы.</span><span class="sxs-lookup"><span data-stu-id="f4afa-130">If Calling Plans isn’t available, you need to transition your enterprise voice deployment to Microsoft Phone System Direct Routing.</span></span> <span data-ttu-id="f4afa-131">Обновление пользователей в группы, см.в [Дополнительные вопросы для прямой маршрутизации телефонной системы](2-envision-make-my-service-decisions-direct-routing.md).</span><span class="sxs-lookup"><span data-stu-id="f4afa-131">To upgrade your users to Teams, see the [additional considerations for Phone System Direct Routing](2-envision-make-my-service-decisions-direct-routing.md).</span></span>