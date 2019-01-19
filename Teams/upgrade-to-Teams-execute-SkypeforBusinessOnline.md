---
title: Обновление Скайп для бизнеса в Интернете для групп Майкрософт | Развертывание
author: arachmanGitHub
ms.author: arachman
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: dearbeen
description: Вопросы, касающиеся обновления группы из Скайп для бизнеса в Интернет
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
MS.collection: Teams_ITAdmin_JourneyFromSfB
appliesto:
- Microsoft Teams
ms.openlocfilehash: 44f3cdad4ab65935c2721244364861db7a140f15
ms.sourcegitcommit: 716d39077784417c3545a91e501ae26ff56ebdf4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/19/2019
ms.locfileid: "29349297"
---
<span data-ttu-id="8ebb9-103">![Этапы обновления пути с акцентом на развертывание и стадии реализации] (media/upgrade-banner-deployment.png "Этапы обновления пути с акцентом на развертывание и стадии реализации")</span><span class="sxs-lookup"><span data-stu-id="8ebb9-103">![Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage](media/upgrade-banner-deployment.png "Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage")</span></span>

<span data-ttu-id="8ebb9-104">В этой статье является частью развертывания и внедрения этапа обновления пути.</span><span class="sxs-lookup"><span data-stu-id="8ebb9-104">This article is part of Deployment and Implementation stage of your upgrade journey.</span></span> <span data-ttu-id="8ebb9-105">Прежде чем продолжить, убедитесь, что вы выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="8ebb9-105">Before proceeding, confirm that you’ve completed the following activities:</span></span>

- [<span data-ttu-id="8ebb9-106">Прикреплено другие заинтересованные стороны проекта</span><span class="sxs-lookup"><span data-stu-id="8ebb9-106">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
- [<span data-ttu-id="8ebb9-107">Определенные области проекта</span><span class="sxs-lookup"><span data-stu-id="8ebb9-107">Defined your project scope</span></span>](https://aka.ms/SkypetoTeams-Scope)
- [<span data-ttu-id="8ebb9-108">Поняты сосуществования и взаимодействия Скайп для бизнеса и рабочих групп</span><span class="sxs-lookup"><span data-stu-id="8ebb9-108">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](https://aka.ms/SkypeToTeams-Coexist)
- [<span data-ttu-id="8ebb9-109">Выбранные обновления пути</span><span class="sxs-lookup"><span data-stu-id="8ebb9-109">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [<span data-ttu-id="8ebb9-110">Подготовка среды</span><span class="sxs-lookup"><span data-stu-id="8ebb9-110">Prepared your environment</span></span>](https://aka.ms/SkypeToTeams-TechnicalReadiness)
- [<span data-ttu-id="8ebb9-111">Подготовлено вашей организации</span><span class="sxs-lookup"><span data-stu-id="8ebb9-111">Prepared your organization</span></span>](https://aka.ms/SkypeToTeams-UserReadiness)
- [<span data-ttu-id="8ebb9-112">Проведение пилотного проекта</span><span class="sxs-lookup"><span data-stu-id="8ebb9-112">Conducted a pilot</span></span>](https://aka.ms/SkypeToTeams-Pilot)

# <a name="upgrade-from-skype-for-business-online-to-teams"></a><span data-ttu-id="8ebb9-113">Обновление от Скайп для бизнеса в Интернете по группам</span><span class="sxs-lookup"><span data-stu-id="8ebb9-113">Upgrade from Skype for Business Online to Teams</span></span>

<span data-ttu-id="8ebb9-114">Следуйте указаниям в этой статье, если полностью развернут Скайп для бизнеса в Интернет и требуется обновление пользователей с Скайп для бизнеса в группы.</span><span class="sxs-lookup"><span data-stu-id="8ebb9-114">Follow the guidance in this article if you have wholly deployed Skype for Business Online and want to upgrade your users from Skype for Business to Teams.</span></span> <span data-ttu-id="8ebb9-115">Можно обновить пользователей выборочно или файловый, основанным на обновление journey, ваша организация решила, назначив соответствующие сосуществования и обновления режима для пользователей.</span><span class="sxs-lookup"><span data-stu-id="8ebb9-115">You can upgrade users selectively or all-in, based on the upgrade journey that your organization has chosen, by assigning the appropriate coexistence and upgrade mode to your users.</span></span>

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]

## <a name="assign-the-coexistence-and-upgrade-mode"></a><span data-ttu-id="8ebb9-116">Назначение режима совместимости и обновления</span><span class="sxs-lookup"><span data-stu-id="8ebb9-116">Assign the coexistence and upgrade mode</span></span>

<span data-ttu-id="8ebb9-117">Пользователи с группами можно обновить с назначением режим TeamsOnly TeamsUpgradePolicy, который может выполняться с помощью групп Майкрософт & Скайп для бизнеса центра администрирования или Скайп для бизнеса удаленного сеанса Windows Powershell.</span><span class="sxs-lookup"><span data-stu-id="8ebb9-117">You can upgrade your users by Teams by assigning the TeamsOnly mode of TeamsUpgradePolicy, which can be performed by using the Microsoft Teams & Skype for Business Admin Center or a Skype for Business remote Windows Powershell session.</span></span>

<span data-ttu-id="8ebb9-118">Для получения дополнительных сведений см [Задание вашей сосуществования и параметры обновления](https://aka.ms/SkypeToTeams-SetCoexistence) и [TeamsUpgradePolicy: управление миграция и сосуществование](migration-interop-guidance-for-teams-with-skype.md#teamsupgradepolicy-managing-migration-and-co-existence).</span><span class="sxs-lookup"><span data-stu-id="8ebb9-118">For more information, see [Setting your coexistence and upgrade settings](https://aka.ms/SkypeToTeams-SetCoexistence) and [TeamsUpgradePolicy: managing migration and coexistence](migration-interop-guidance-for-teams-with-skype.md#teamsupgradepolicy-managing-migration-and-co-existence).</span></span>

## <a name="upgrade-all-users-to-teams-at-one-time"></a><span data-ttu-id="8ebb9-119">Обновление всех пользователей к группам за один раз</span><span class="sxs-lookup"><span data-stu-id="8ebb9-119">Upgrade all users to Teams at one time</span></span>

<span data-ttu-id="8ebb9-120">Выполните следующие действия для обновления всех пользователей к группам за один раз.</span><span class="sxs-lookup"><span data-stu-id="8ebb9-120">Follow these steps to upgrade all of your users to Teams at one time.</span></span>

### <a name="step-1-notify-the-users-of-the-change"></a><span data-ttu-id="8ebb9-121">Шаг 1: Уведомить пользователей об изменениях</span><span class="sxs-lookup"><span data-stu-id="8ebb9-121">Step 1: Notify the users of the change</span></span>

1. <span data-ttu-id="8ebb9-122">В Скайп по центру администрирования Business & группами Майкрософт, выберите **Параметры масштабе организации** > **Обновление группы**.</span><span class="sxs-lookup"><span data-stu-id="8ebb9-122">In the Microsoft Teams & Skype for Business Admin Center, select **Org-wide settings** > **Teams upgrade**.</span></span>
2. <span data-ttu-id="8ebb9-123">В разделе **режим совместимости**измените переключатель **Уведомить Скайп для бизнес-пользователей, что обновление группам доступен** **на**.</span><span class="sxs-lookup"><span data-stu-id="8ebb9-123">Under **Coexistence mode**, change the **Notify Skype for Business users that an upgrade to Teams is available** switch to **On**.</span></span>

### <a name="step-2-set-the-coexistence-mode-for-the-users"></a><span data-ttu-id="8ebb9-124">Шаг 2: Задайте режим совместной работы для пользователей</span><span class="sxs-lookup"><span data-stu-id="8ebb9-124">Step 2: Set the coexistence mode for the users</span></span>

1. <span data-ttu-id="8ebb9-125">В Скайп по центру администрирования Business & группами Майкрософт выберите **Параметры на уровне организации**.</span><span class="sxs-lookup"><span data-stu-id="8ebb9-125">In the Microsoft Teams & Skype for Business Admin Center, select **Org-wide settings**.</span></span>
2. <span data-ttu-id="8ebb9-126">Выберите **Команды только** в режиме **сосуществования режим** раскрывающегося списка.</span><span class="sxs-lookup"><span data-stu-id="8ebb9-126">Select **Teams Only** mode from the **Coexistence mode** drop-down list.</span></span>

## <a name="upgrade-users-in-stages"></a><span data-ttu-id="8ebb9-127">Обновление пользователей на стадии</span><span class="sxs-lookup"><span data-stu-id="8ebb9-127">Upgrade users in stages</span></span>

<span data-ttu-id="8ebb9-128">Для постепенного обновления пользователей по группам, выполните приведенные далее действия.</span><span class="sxs-lookup"><span data-stu-id="8ebb9-128">Follow these steps if you want to gradually upgrade your users to Teams.</span></span>

### <a name="step-1-create-your-user-cohorts-for-the-upgrade"></a><span data-ttu-id="8ebb9-129">Шаг 1: Создание вашего последователей пользователя для обновления</span><span class="sxs-lookup"><span data-stu-id="8ebb9-129">Step 1: Create your user cohorts for the upgrade</span></span>

<span data-ttu-id="8ebb9-130">Последователей пользователя — это группы пользователей, которые будут перемещены в режим только для групп в то же время.</span><span class="sxs-lookup"><span data-stu-id="8ebb9-130">User cohorts are groups of users who will be moved to Teams Only mode at the same time.</span></span>

<span data-ttu-id="8ebb9-131">Для создания вашего пользовательского последователей (Добавить ссылку на страницу Выбор пользователя)</span><span class="sxs-lookup"><span data-stu-id="8ebb9-131">To create your user cohorts (Add link to user selection page)</span></span>

### <a name="step-2-set-the-user-mode-to-islands"></a><span data-ttu-id="8ebb9-132">Шаг 2: Задайте режим пользователя о-ва</span><span class="sxs-lookup"><span data-stu-id="8ebb9-132">Step 2: Set the user mode to Islands</span></span>

1. <span data-ttu-id="8ebb9-133">В Скайп по центру администрирования Business & группами Майкрософт Выбор **пользователей**и выберите cohort пользователя.</span><span class="sxs-lookup"><span data-stu-id="8ebb9-133">In the Microsoft Teams & Skype for Business Admin Center, select **Users**, and then select a user cohort.</span></span>
2. <span data-ttu-id="8ebb9-134">**Обновление группы**выберите **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="8ebb9-134">Next to **Teams upgrade**, select **Edit**.</span></span>
3. <span data-ttu-id="8ebb9-135">На левой панели **Команд обновления** в **режиме сосуществования**выберите **острова** из раскрывающегося списка.</span><span class="sxs-lookup"><span data-stu-id="8ebb9-135">In the **Teams Upgrade** pane, under **Coexistence mode**, select **Islands** from the drop-down list.</span></span>

### <a name="step-3-set-notification-for-the-user-optional"></a><span data-ttu-id="8ebb9-136">Шаг 3: Задайте уведомления для пользователя (необязательно)</span><span class="sxs-lookup"><span data-stu-id="8ebb9-136">Step 3: Set notification for the user (optional)</span></span>

1. <span data-ttu-id="8ebb9-137">В Скайп по центру администрирования Business & группами Майкрософт Выбор **пользователей**и выберите cohort пользователя.</span><span class="sxs-lookup"><span data-stu-id="8ebb9-137">In the Microsoft Teams & Skype for Business Admin Center, select **Users**, and select a user cohort.</span></span>
2. <span data-ttu-id="8ebb9-138">**Обновление группы**выберите **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="8ebb9-138">Next to **Teams upgrade**, select **Edit**.</span></span>
3. <span data-ttu-id="8ebb9-139">На левой панели **Команд обновления** в разделе **режим совместимости**измените переключатель **Уведомлять Скайп для корпоративных пользователей** **на**.</span><span class="sxs-lookup"><span data-stu-id="8ebb9-139">In the **Teams Upgrade** pane, under **Coexistence mode**, change **Notify the Skype for Business user** switch to **On**.</span></span>

### <a name="step-4-set-the-user-mode-to-teams-only"></a><span data-ttu-id="8ebb9-140">Шаг 4: Задайте режим пользователей группам только</span><span class="sxs-lookup"><span data-stu-id="8ebb9-140">Step 4: Set the user mode to Teams Only</span></span>

<span data-ttu-id="8ebb9-141">Режим сосуществования пользователя для групп только, когда все будет готово к обновлению пользователям использовать команды в качестве их только приложения.</span><span class="sxs-lookup"><span data-stu-id="8ebb9-141">When you are ready to upgrade the users to use Teams as their only application, set the Coexistence mode for the user to Teams Only.</span></span>

1. <span data-ttu-id="8ebb9-142">В Скайп по центру администрирования Business & группами Майкрософт Выбор **пользователей**и выберите cohort пользователя.</span><span class="sxs-lookup"><span data-stu-id="8ebb9-142">In the Microsoft Teams & Skype for Business Admin Center, select **Users**, and then select a user cohort.</span></span>
2. <span data-ttu-id="8ebb9-143">**Обновление группы**выберите **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="8ebb9-143">Next to **Teams upgrade**, select **Edit**.</span></span>
3. <span data-ttu-id="8ebb9-144">На левой панели **Команд обновления** в **режиме сосуществования**выберите **Группы только** из раскрывающегося списка.</span><span class="sxs-lookup"><span data-stu-id="8ebb9-144">In the **Teams Upgrade** pane, under **Coexistence mode**, select **Teams Only** from the drop-down list.</span></span>

## <a name="phone-system-and-teams-upgrade"></a><span data-ttu-id="8ebb9-145">Обновление телефонной системой и рабочих групп</span><span class="sxs-lookup"><span data-stu-id="8ebb9-145">Phone System and Teams upgrade</span></span>

<span data-ttu-id="8ebb9-146">Если ваше Скайп для бизнеса в Интернет развертывания включает в себя телефонной системы с помощью вызова планы и Microsoft — это ваш поставщик телефонной сети (общего пользования PSTN), обновление пользователей группам автоматический переход входящих PSTN, вызов к группам.</span><span class="sxs-lookup"><span data-stu-id="8ebb9-146">If your Skype for Business Online deployment includes Phone System with Calling Plans and Microsoft is your public switched telephone network (PSTN) provider, upgrading your users to Teams will automatically transition inbound PSTN calling to Teams.</span></span>

<span data-ttu-id="8ebb9-147">Если ваше Скайп для бизнеса в Интернет развертывания включает системы Phone Edition соединителя облако с, см.в [Дополнительные вопросы для прямой маршрутизации телефонной системы](2-envision-make-my-service-decisions-direct-routing.md).</span><span class="sxs-lookup"><span data-stu-id="8ebb9-147">If your Skype for Business Online deployment includes Phone System with Cloud Connector Edition, see the [additional considerations for Phone System Direct Routing](2-envision-make-my-service-decisions-direct-routing.md).</span></span>