---
title: Обновление Скайп для бизнеса в Интернете для групп Майкрософт | Развертывание
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: dearbeen
description: Вопросы, касающиеся обновления группы из Скайп для бизнеса в Интернет
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
MS.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6748397c354f9238282f9646388993fc0e9f7b88
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "33902725"
---
<span data-ttu-id="e03ea-103">![Этапы обновления пути с акцентом на развертывание и стадии реализации] (media/upgrade-banner-deployment.png "Этапы обновления пути с акцентом на развертывание и стадии реализации")</span><span class="sxs-lookup"><span data-stu-id="e03ea-103">![Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage](media/upgrade-banner-deployment.png "Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage")</span></span>

<span data-ttu-id="e03ea-104">В этой статье является частью развертывания и внедрения этапа обновления пути.</span><span class="sxs-lookup"><span data-stu-id="e03ea-104">This article is part of Deployment and Implementation stage of your upgrade journey.</span></span> <span data-ttu-id="e03ea-105">Прежде чем продолжить, убедитесь, что вы выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="e03ea-105">Before proceeding, confirm that you’ve completed the following activities:</span></span>

- [<span data-ttu-id="e03ea-106">Прикреплено другие заинтересованные стороны проекта</span><span class="sxs-lookup"><span data-stu-id="e03ea-106">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
- [<span data-ttu-id="e03ea-107">Определенные области проекта</span><span class="sxs-lookup"><span data-stu-id="e03ea-107">Defined your project scope</span></span>](https://aka.ms/SkypetoTeams-Scope)
- [<span data-ttu-id="e03ea-108">Поняты сосуществования и взаимодействия Скайп для бизнеса и рабочих групп</span><span class="sxs-lookup"><span data-stu-id="e03ea-108">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](https://aka.ms/SkypeToTeams-Coexist)
- [<span data-ttu-id="e03ea-109">Выбранные обновления пути</span><span class="sxs-lookup"><span data-stu-id="e03ea-109">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [<span data-ttu-id="e03ea-110">Подготовка среды</span><span class="sxs-lookup"><span data-stu-id="e03ea-110">Prepared your environment</span></span>](https://aka.ms/SkypeToTeams-TechnicalReadiness)
- [<span data-ttu-id="e03ea-111">Подготовлено вашей организации</span><span class="sxs-lookup"><span data-stu-id="e03ea-111">Prepared your organization</span></span>](https://aka.ms/SkypeToTeams-UserReadiness)
- [<span data-ttu-id="e03ea-112">Проведение пилотного проекта</span><span class="sxs-lookup"><span data-stu-id="e03ea-112">Conducted a pilot</span></span>](https://aka.ms/SkypeToTeams-Pilot)

# <a name="upgrade-from-skype-for-business-online-to-teams"></a><span data-ttu-id="e03ea-113">Переход со Skype для бизнеса Online на Teams</span><span class="sxs-lookup"><span data-stu-id="e03ea-113">Upgrade from Skype for Business Online to Teams</span></span>

<span data-ttu-id="e03ea-114">Следуйте указаниям в этой статье, если полностью развернут Скайп для бизнеса в Интернет и требуется обновление пользователей с Скайп для бизнеса в группы.</span><span class="sxs-lookup"><span data-stu-id="e03ea-114">Follow the guidance in this article if you have wholly deployed Skype for Business Online and want to upgrade your users from Skype for Business to Teams.</span></span> <span data-ttu-id="e03ea-115">Можно обновить пользователей выборочно или файловый, основанным на обновление journey, ваша организация решила, назначив соответствующие сосуществования и обновления режима для пользователей.</span><span class="sxs-lookup"><span data-stu-id="e03ea-115">You can upgrade users selectively or all-in, based on the upgrade journey that your organization has chosen, by assigning the appropriate coexistence and upgrade mode to your users.</span></span>

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]

## <a name="assign-the-coexistence-and-upgrade-mode"></a><span data-ttu-id="e03ea-116">Назначение режима совместимости и обновления</span><span class="sxs-lookup"><span data-stu-id="e03ea-116">Assign the coexistence and upgrade mode</span></span>

<span data-ttu-id="e03ea-117">Пользователей можно обновить до режима TeamsOnly с назначением UpgradeToTeams экземпляр TeamsUpgradePolicy, в которой может выполняться с помощью центра администрирования группами Майкрософт или Скайп для бизнеса удаленного сеанса Windows Powershell.</span><span class="sxs-lookup"><span data-stu-id="e03ea-117">You can upgrade your users to TeamsOnly mode by assigning the UpgradeToTeams instance of TeamsUpgradePolicy, which can be performed by using the Microsoft Teams admin center or a Skype for Business remote Windows Powershell session.</span></span> <span data-ttu-id="e03ea-118">Это возможно на уровне пользователя или на уровне клиента Если вы хотите ugprade всей клиента в одном шаге.</span><span class="sxs-lookup"><span data-stu-id="e03ea-118">You can do this either on a per user basis, or on a tenant-wide basis if you want to ugprade the entire tenant in one step.</span></span> 

<span data-ttu-id="e03ea-119">Для получения дополнительных сведений см [Задание вашей сосуществования и параметры обновления](https://aka.ms/SkypeToTeams-SetCoexistence) и [TeamsUpgradePolicy: управление миграция и сосуществование](migration-interop-guidance-for-teams-with-skype.md#teamsupgradepolicy-managing-migration-and-co-existence).</span><span class="sxs-lookup"><span data-stu-id="e03ea-119">For more information, see [Setting your coexistence and upgrade settings](https://aka.ms/SkypeToTeams-SetCoexistence) and [TeamsUpgradePolicy: managing migration and coexistence](migration-interop-guidance-for-teams-with-skype.md#teamsupgradepolicy-managing-migration-and-co-existence).</span></span>

## <a name="upgrade-all-users-to-teams-at-one-time"></a><span data-ttu-id="e03ea-120">Обновление всех пользователей к группам за один раз</span><span class="sxs-lookup"><span data-stu-id="e03ea-120">Upgrade all users to Teams at one time</span></span>

<span data-ttu-id="e03ea-121">Выполните следующие действия для обновления всех пользователей к группам за один раз.</span><span class="sxs-lookup"><span data-stu-id="e03ea-121">Follow these steps to upgrade all of your users to Teams at one time.</span></span>

### <a name="step-1-notify-the-users-of-the-change-optional"></a><span data-ttu-id="e03ea-122">Шаг 1: Уведомить пользователей об изменениях (необязательно)</span><span class="sxs-lookup"><span data-stu-id="e03ea-122">Step 1: Notify the users of the change (optional)</span></span>

1. <span data-ttu-id="e03ea-123">В центре администрирования группами Майкрософт, выберите пункт **Параметры масштабе организации** > **Обновление группы**.</span><span class="sxs-lookup"><span data-stu-id="e03ea-123">In the Microsoft Teams admin center, select **Org-wide settings** > **Teams upgrade**.</span></span>
2. <span data-ttu-id="e03ea-124">В разделе **режим совместимости**измените переключатель **Уведомить Скайп для бизнес-пользователей, что обновление группам доступен** **на**.</span><span class="sxs-lookup"><span data-stu-id="e03ea-124">Under **Coexistence mode**, change the **Notify Skype for Business users that an upgrade to Teams is available** switch to **On**.</span></span>

### <a name="step-2-set-the-coexistence-mode-to-teamsonly-for-the-organization"></a><span data-ttu-id="e03ea-125">Шаг 2: Задайте режим сосуществования TeamsOnly для организации</span><span class="sxs-lookup"><span data-stu-id="e03ea-125">Step 2: Set the coexistence mode to TeamsOnly for the organization</span></span>

1. <span data-ttu-id="e03ea-126">В центре администрирования группами Майкрософт выберите **Параметры на уровне организации**.</span><span class="sxs-lookup"><span data-stu-id="e03ea-126">In the Microsoft Teams admin center, select **Org-wide settings**.</span></span>
2. <span data-ttu-id="e03ea-127">Выберите **Команды только** в режиме **сосуществования режим** раскрывающегося списка.</span><span class="sxs-lookup"><span data-stu-id="e03ea-127">Select **Teams Only** mode from the **Coexistence mode** drop-down list.</span></span>

## <a name="upgrade-users-in-stages"></a><span data-ttu-id="e03ea-128">Обновление пользователей на стадии</span><span class="sxs-lookup"><span data-stu-id="e03ea-128">Upgrade users in stages</span></span>

<span data-ttu-id="e03ea-129">Для постепенного обновления пользователей до TeamsOnly, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="e03ea-129">Follow these steps if you want to gradually upgrade your users to TeamsOnly.</span></span>

### <a name="step-1-identify-groups-of-users-for-upgrade"></a><span data-ttu-id="e03ea-130">Этап 1: Определение групп пользователей к обновлению</span><span class="sxs-lookup"><span data-stu-id="e03ea-130">Step 1: Identify groups of users for upgrade</span></span>

<span data-ttu-id="e03ea-131">Часто организациям может потребоваться обновить своей организации в этапами успеха пользователей.</span><span class="sxs-lookup"><span data-stu-id="e03ea-131">Often organizations may choose to upgrade their organizations in success waves of users.</span></span>  <span data-ttu-id="e03ea-132">Необходимо сначала определить эти пользователи, поэтому можно легко найти их в центре администрирования группами Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="e03ea-132">You'll want to identify these users first so you can easily search for them in the Microsoft Teams admin center.</span></span> <span data-ttu-id="e03ea-133">Кроме того можно сделать это более эффективно с помощью PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e03ea-133">Alternatively, you may want to use PowerShell to more efficiently do this.</span></span> <span data-ttu-id="e03ea-134">После определения группы пользователей для данного обновления звукового файла выполните остальные действия.</span><span class="sxs-lookup"><span data-stu-id="e03ea-134">Once you have identified the set of users for a given upgrade wave, continue with the remaining steps.</span></span>

### <a name="step-2-set-notification-for-the-users-in-the-current-ugprade-wave-optional"></a><span data-ttu-id="e03ea-135">Шаг 2: Настройка уведомлений для пользователей в текущем волне ugprade (необязательно)</span><span class="sxs-lookup"><span data-stu-id="e03ea-135">Step 2: Set notification for the users in the current ugprade wave (optional)</span></span>

<span data-ttu-id="e03ea-136">Если с помощью центра администрирования группами Майкрософт, можно настроить TeamsUpgradePolicy для пользователя до 20 одновременно:</span><span class="sxs-lookup"><span data-stu-id="e03ea-136">If using the Microsoft Teams admin center, you can configure TeamsUpgradePolicy for up to 20 user at once:</span></span>
1. <span data-ttu-id="e03ea-137">В центре администрирования группами Майкрософт флажок **пользователей**и поиск и выбор нескольких для до 20 пользователей, которые должны быть обновлены.</span><span class="sxs-lookup"><span data-stu-id="e03ea-137">In the Microsoft Teams admin center, select **Users**, and find and multi-select the checkbox for up to 20 users who should be upgraded.</span></span> 
2. <span data-ttu-id="e03ea-138">Выберите **Изменить параметры** в верхнем левом углу списка автофильтра.</span><span class="sxs-lookup"><span data-stu-id="e03ea-138">Select **Edit settings** in the upper left corner of the listview.</span></span> 
3. <span data-ttu-id="e03ea-139">В области **Изменение параметров** в правой части окна, в разделе **группы обновления**измените переключатель **Уведомлять Скайп для корпоративных пользователей** **на**.</span><span class="sxs-lookup"><span data-stu-id="e03ea-139">In the **Edit settings** pane on the right, under **Teams upgrade**, change **Notify the Skype for Business user** switch to **On**.</span></span> <span data-ttu-id="e03ea-140">Примечание: Если значение режиме сосуществования «масштабе организации использовать параметры», не будут отображаться этот переключатель, вам потребуется сначала явно режим сосуществования для этих пользователей независимо от существующих значение по умолчанию — для ориентацию.</span><span class="sxs-lookup"><span data-stu-id="e03ea-140">Note: If the value of coexistence mode is "Use Org-wide settings", you won't see this switch, so you'll need to first explicitly set the Coexistence mode for these users to whatever the default value is for the org.</span></span>

<span data-ttu-id="e03ea-141">Кроме того может быть проще Включение уведомлений для групп пользователей, с помощью PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e03ea-141">Alternatively, you may find it easier to enable notifications for groups of users at once using PowerShell.</span></span> 

### <a name="step-3-set-the-coexistence-mode-for-users-to-teams-only"></a><span data-ttu-id="e03ea-142">Шаг 3: Установите режим совместимости для пользователей к группам только</span><span class="sxs-lookup"><span data-stu-id="e03ea-142">Step 3: Set the coexistence mode for users to Teams Only</span></span>

<span data-ttu-id="e03ea-143">Режим совместной работы для пользователей к группам только, когда все будет готово к обновлению пользователей в текущем звукового файла для использования в качестве их только приложения группы.</span><span class="sxs-lookup"><span data-stu-id="e03ea-143">When you are ready to upgrade the users in the current wave to use Teams as their only application, set the Coexistence mode for the users to Teams Only.</span></span>

<span data-ttu-id="e03ea-144">Если с помощью центра администрирования группами Майкрософт, можно настроить TeamsUpgradePolicy для пользователя до 20 одновременно:</span><span class="sxs-lookup"><span data-stu-id="e03ea-144">If using the Microsoft Teams admin center, you can configure TeamsUpgradePolicy for up to 20 user at once:</span></span>
1. <span data-ttu-id="e03ea-145">В центре администрирования группами Майкрософт выберите **пользователей**и затем установите флажок для до 20 пользователями.</span><span class="sxs-lookup"><span data-stu-id="e03ea-145">In the Microsoft Teams admin center, select **Users**, and then select the checkbox for up to 20 users.</span></span>
2. <span data-ttu-id="e03ea-146">Выберите **Изменить параметры** в верхнем левом углу списка автофильтра.</span><span class="sxs-lookup"><span data-stu-id="e03ea-146">Select **Edit settings** in the upper left corner of the listview.</span></span>
3. <span data-ttu-id="e03ea-147">В области **Изменение параметров** в правой части окна, в разделе **Обновление группы** режим совместной работы **Групп** только в раскрывающемся списке.</span><span class="sxs-lookup"><span data-stu-id="e03ea-147">In the **Edit settings** pane on the right, under **Teams upgrade** section, set the coexistence mode to **Teams Only** in the drop-down list.</span></span>

<span data-ttu-id="e03ea-148">Кроме того может быть проще обновление групп пользователей, с помощью PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e03ea-148">Alternatively, you may find it easier to upgrade groups of users at once using PowerShell.</span></span> 

### <a name="step-4-repeat-steps-1-3-for-successive-waves-of-users"></a><span data-ttu-id="e03ea-149">Шаг 4: Повторите шаги 1-3 для последующими этапами пользователей</span><span class="sxs-lookup"><span data-stu-id="e03ea-149">Step 4: Repeat steps 1-3 for successive waves of users</span></span>

<span data-ttu-id="e03ea-150">Как проверить вашего обновления до групп только в режиме и все готово к разверните узел, повторите предыдущие действия, чтобы применить TeamsOnly для других пользователей.</span><span class="sxs-lookup"><span data-stu-id="e03ea-150">As you validate your upgrade to Teams Only mode and are ready to expand, repeat the previous steps to apply TeamsOnly to  more users.</span></span>  


## <a name="phone-system-and-teams-upgrade"></a><span data-ttu-id="e03ea-151">Обновление телефонной системой и рабочих групп</span><span class="sxs-lookup"><span data-stu-id="e03ea-151">Phone System and Teams upgrade</span></span>

<span data-ttu-id="e03ea-152">Если ваше Скайп для бизнеса в Интернет развертывания включает в себя телефонной системы с помощью вызова планы и Microsoft — это ваш поставщик телефонной сети (общего пользования PSTN), обновление пользователей группам автоматический переход входящих PSTN, вызов к группам.</span><span class="sxs-lookup"><span data-stu-id="e03ea-152">If your Skype for Business Online deployment includes Phone System with Calling Plans and Microsoft is your public switched telephone network (PSTN) provider, upgrading your users to Teams will automatically transition inbound PSTN calling to Teams.</span></span>

<span data-ttu-id="e03ea-153">Если ваше Скайп для бизнеса в Интернет развертывания включает системы Phone Edition соединителя облако с, см.в [Дополнительные вопросы для прямой маршрутизации телефонной системы](2-envision-make-my-service-decisions-direct-routing.md).</span><span class="sxs-lookup"><span data-stu-id="e03ea-153">If your Skype for Business Online deployment includes Phone System with Cloud Connector Edition, see the [additional considerations for Phone System Direct Routing](2-envision-make-my-service-decisions-direct-routing.md).</span></span>
