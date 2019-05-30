---
title: Переход на Teams с гибридного или локального развертывания Skype для бизнеса — Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 01/09/2019
ms.topic: article
ms.service: msteams
ms.reviewer: dearbeen
description: Рекомендации по переходу на Teams из гибридного или локального развертывания Skype для бизнеса.
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
MS.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 118bae776f4bb3709d62dea1f384ccaa0707397b
ms.sourcegitcommit: 75b2cd0d2d39c50dc1e1513860841e2ae3f84324
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/28/2019
ms.locfileid: "34493981"
---
<span data-ttu-id="1ab2a-103">![Обновление схемы поездки, акцент на развертывании и реализации] (media/upgrade-banner-deployment.png "Этапы поездки на обновление, акцент на этапе развертывания и реализации")</span><span class="sxs-lookup"><span data-stu-id="1ab2a-103">![Upgrade journey diagram, emphasizing Deployment and Implementation](media/upgrade-banner-deployment.png "Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage")</span></span>

<span data-ttu-id="1ab2a-104">Эта статья является частью стадии развертывания и внедрения вашего путешествия по обновлению.</span><span class="sxs-lookup"><span data-stu-id="1ab2a-104">This article is part of Deployment and Implementation stage of your upgrade journey.</span></span> <span data-ttu-id="1ab2a-105">Перед продолжением убедитесь, что выполнены следующие действия:</span><span class="sxs-lookup"><span data-stu-id="1ab2a-105">Before proceeding, confirm that you’ve completed the following activities:</span></span>

-   [<span data-ttu-id="1ab2a-106">Вовлеченные заинтересованные лица в проект</span><span class="sxs-lookup"><span data-stu-id="1ab2a-106">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
-   [<span data-ttu-id="1ab2a-107">Определение области охвата проекта</span><span class="sxs-lookup"><span data-stu-id="1ab2a-107">Defined your project scope</span></span>](https://aka.ms/SkypetoTeams-Scope)
-   [<span data-ttu-id="1ab2a-108">Сосуществование и взаимодействие Skype для бизнеса и рабочих групп</span><span class="sxs-lookup"><span data-stu-id="1ab2a-108">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](https://aka.ms/SkypeToTeams-Coexist)
-   [<span data-ttu-id="1ab2a-109">Выбрано путешествие с обновлением</span><span class="sxs-lookup"><span data-stu-id="1ab2a-109">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
-   [<span data-ttu-id="1ab2a-110">Подготовка среды</span><span class="sxs-lookup"><span data-stu-id="1ab2a-110">Prepared your environment</span></span>](https://aka.ms/SkypeToTeams-TechnicalReadiness)
-   [<span data-ttu-id="1ab2a-111">Подготовка Организации</span><span class="sxs-lookup"><span data-stu-id="1ab2a-111">Prepared your organization</span></span>](https://aka.ms/SkypeToTeams-UserReadiness)
-   [<span data-ttu-id="1ab2a-112">Пробные испытания</span><span class="sxs-lookup"><span data-stu-id="1ab2a-112">Conducted a pilot</span></span>](https://aka.ms/SkypeToTeams-Pilot)

# <a name="upgrade-to-teams-from-a-skype-for-business-hybrid-or-on-premises-deployment"></a><span data-ttu-id="1ab2a-113">Переход на Teams из гибридного или локального развертывания Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="1ab2a-113">Upgrade to Teams from a Skype for Business hybrid or on-premises deployment</span></span>

<span data-ttu-id="1ab2a-114">Следуйте указаниям, приведенным в этой статье, если вы разработали Skype для бизнеса или Microsoft Lync в локальной среде, и ваша организация хочет выборочно перейти на Teams, используя несколько режимов сосуществования или все.</span><span class="sxs-lookup"><span data-stu-id="1ab2a-114">Follow the guidance in this article if you’ve deployed Skype for Business or Microsoft Lync on-premises and your organization wants to upgrade to Teams either selectively—by using multiple coexistence modes—or all-in.</span></span> <span data-ttu-id="1ab2a-115">Первый этап — это настройка гибридной связи с вашим клиентом Office 365, а затем перемещение пользователей в Skype для бизнеса Online и назначение им соответствующего режима сосуществования и обновления.</span><span class="sxs-lookup"><span data-stu-id="1ab2a-115">The first step is to set up hybrid connectivity with your Office 365 tenant, and then move your users to Skype for Business Online and assign them the appropriate coexistence and upgrade mode.</span></span> 

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]

## <a name="step-1-deploy-hybrid-connectivity"></a><span data-ttu-id="1ab2a-116">Действие 1: развертывание гибридного подключения</span><span class="sxs-lookup"><span data-stu-id="1ab2a-116">Step 1: Deploy hybrid connectivity</span></span> 

<span data-ttu-id="1ab2a-117">Ключевым условием для обновления пользователей до Teams является развертывание гибридного подключения.</span><span class="sxs-lookup"><span data-stu-id="1ab2a-117">The key prerequisite for upgrading your users to Teams is to deploy hybrid connectivity.</span></span> <span data-ttu-id="1ab2a-118">Это может включать развертывание новых внешних подключений для существующего развертывания Skype для бизнеса или Lync, а также просто настройку гибридного отношения с вашим клиентом Office 365.</span><span class="sxs-lookup"><span data-stu-id="1ab2a-118">This might involve deploying new external connectivity for your existing Skype for Business or Lync deployment, or simply configuring a hybrid relationship with your Office 365 tenant.</span></span> 

<span data-ttu-id="1ab2a-119">Дополнительные сведения можно найти в разделе [развертывание гибридной связи между Skype для бизнеса Server и Skype для бизнеса Online](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity).</span><span class="sxs-lookup"><span data-stu-id="1ab2a-119">For more information, see [Deploy hybrid connectivity between Skype for Business Server and Skype for Business Online](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity).</span></span>

## <a name="step-2-move-users-to-skype-for-business-online"></a><span data-ttu-id="1ab2a-120">Шаг 2: перемещение пользователей в Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="1ab2a-120">Step 2: Move users to Skype for Business Online</span></span> 

<span data-ttu-id="1ab2a-121">После того как вы закончите развертывание гибридной конфигурации, перенесите пользователей в Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="1ab2a-121">After you’ve completed your hybrid setup, move users to Skype for Business Online.</span></span> 

<span data-ttu-id="1ab2a-122">Дополнительные сведения можно найти в разделе [Перемещение пользователей из локальной сети в Skype для бизнеса Online](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online).</span><span class="sxs-lookup"><span data-stu-id="1ab2a-122">For more information, see [Move users from on premises to Skype for Business Online](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online).</span></span> 

## <a name="step-3-assign-a-coexistence-and-upgrade-mode"></a><span data-ttu-id="1ab2a-123">Шаг 3: назначение режима сосуществования и обновления</span><span class="sxs-lookup"><span data-stu-id="1ab2a-123">Step 3: Assign a coexistence and upgrade mode</span></span>

<span data-ttu-id="1ab2a-124">После того как вы перенесли пользователей в Skype для бизнеса Online, вы можете назначить им режим совместного существования, основываясь на пути обновления, который выбрала ваша организация.</span><span class="sxs-lookup"><span data-stu-id="1ab2a-124">After you’ve moved your users to Skype for Business Online, you can assign them the appropriate coexistence mode based on the upgrade journey that your organization has chosen.</span></span> <span data-ttu-id="1ab2a-125">Дополнительные сведения можно найти [в статье Настройка параметров сосуществования и обновления](https://aka.ms/SkypeToTeams-SetCoexistence) и [теамсупградеполици: управление миграцией и](migration-interop-guidance-for-teams-with-skype.md#teamsupgradepolicy-managing-migration-and-co-existence)сосуществованием.</span><span class="sxs-lookup"><span data-stu-id="1ab2a-125">For more information, see [Setting your coexistence and upgrade settings](https://aka.ms/SkypeToTeams-SetCoexistence) and [TeamsUpgradePolicy: managing migration and coexistence](migration-interop-guidance-for-teams-with-skype.md#teamsupgradepolicy-managing-migration-and-co-existence).</span></span>

> [!NOTE]
> <span data-ttu-id="1ab2a-126">С помощью Skype для бизнеса Server 2019 и будущего накопительного обновления для Skype для бизнеса Server 2015 вы сможете выполнить шаг 2 (перемещение пользователей в Skype для бизнеса Online) и шаг 3 (обновление пользователей до Teams).</span><span class="sxs-lookup"><span data-stu-id="1ab2a-126">With Skype for Business Server 2019 and a future cumulative update of Skype for Business Server 2015, you’ll be able to perform Step 2 (moving users to Skype for Business Online) and Step 3 (upgrade users to Teams) in a single step.</span></span> <span data-ttu-id="1ab2a-127">Дополнительные сведения будут предоставлены после выпуска Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="1ab2a-127">More information will be provided after Skype for Business Server 2019 is released.</span></span>

## <a name="phone-system-and-teams-upgrade"></a><span data-ttu-id="1ab2a-128">Обновление телефонной системы и команды</span><span class="sxs-lookup"><span data-stu-id="1ab2a-128">Phone System and Teams upgrade</span></span>

<span data-ttu-id="1ab2a-129">Если вы переносите гибридное развертывание Skype для бизнеса в телефонную систему с помощью планов звонков, а Microsoft является поставщиком услуг коммутируемой телефонной сети (PSTN) и предполагает, что вы выполнили перенос номера телефона, то после обновления пользователей В Teams будут автоматически перенесены входящие звонки через PSTN в Teams.</span><span class="sxs-lookup"><span data-stu-id="1ab2a-129">If you’re transitioning your Skype for Business hybrid deployment to Phone System with Calling Plans and Microsoft will be your public switched telephone network (PSTN) provider—and assuming that you’ve completed the phone number porting—upgrading your users to Teams will automatically transition inbound PSTN calling to Teams.</span></span>

<span data-ttu-id="1ab2a-130">Если тарифные планы недоступны, вам нужно перевести свое развертывание в корпоративную типографию на прямую маршрутизацию Microsoft Phone System.</span><span class="sxs-lookup"><span data-stu-id="1ab2a-130">If Calling Plans isn’t available, you need to transition your enterprise voice deployment to Microsoft Phone System Direct Routing.</span></span> <span data-ttu-id="1ab2a-131">Чтобы обновить пользователей до Teams, ознакомьтесь с [дополнительными сведениями о прямой маршрутизации для телефонной системы](2-envision-make-my-service-decisions-direct-routing.md).</span><span class="sxs-lookup"><span data-stu-id="1ab2a-131">To upgrade your users to Teams, see the [additional considerations for Phone System Direct Routing](2-envision-make-my-service-decisions-direct-routing.md).</span></span>
