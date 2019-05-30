---
title: Обновите Skype для бизнеса Online до Microsoft Teams | Внедрять
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: dearbeen
description: Рекомендации по обновлению до Teams в Skype для бизнеса Online
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
MS.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6b1cfb8302476983eeb5be180307bc143eb281dc
ms.sourcegitcommit: b5949233f8080a6cf0edb4b5e27272214feb1c22
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/29/2019
ms.locfileid: "34548511"
---
<span data-ttu-id="ae733-103">![Обновление схемы поездки, акцент на развертывании и реализации] (media/upgrade-banner-deployment.png "Этапы поездки на обновление, акцент на этапе развертывания и реализации")</span><span class="sxs-lookup"><span data-stu-id="ae733-103">![Upgrade journey diagram, emphasizing Deployment and Implementation](media/upgrade-banner-deployment.png "Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage")</span></span>

<span data-ttu-id="ae733-104">Эта статья является частью стадии развертывания и внедрения вашего путешествия по обновлению.</span><span class="sxs-lookup"><span data-stu-id="ae733-104">This article is part of Deployment and Implementation stage of your upgrade journey.</span></span> <span data-ttu-id="ae733-105">Перед продолжением убедитесь, что выполнены следующие действия:</span><span class="sxs-lookup"><span data-stu-id="ae733-105">Before proceeding, confirm that you’ve completed the following activities:</span></span>

- [<span data-ttu-id="ae733-106">Вовлеченные заинтересованные лица в проект</span><span class="sxs-lookup"><span data-stu-id="ae733-106">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
- [<span data-ttu-id="ae733-107">Определение области охвата проекта</span><span class="sxs-lookup"><span data-stu-id="ae733-107">Defined your project scope</span></span>](https://aka.ms/SkypetoTeams-Scope)
- [<span data-ttu-id="ae733-108">Сосуществование и взаимодействие Skype для бизнеса и рабочих групп</span><span class="sxs-lookup"><span data-stu-id="ae733-108">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](https://aka.ms/SkypeToTeams-Coexist)
- [<span data-ttu-id="ae733-109">Выбрано путешествие с обновлением</span><span class="sxs-lookup"><span data-stu-id="ae733-109">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [<span data-ttu-id="ae733-110">Подготовка среды</span><span class="sxs-lookup"><span data-stu-id="ae733-110">Prepared your environment</span></span>](https://aka.ms/SkypeToTeams-TechnicalReadiness)
- [<span data-ttu-id="ae733-111">Подготовка Организации</span><span class="sxs-lookup"><span data-stu-id="ae733-111">Prepared your organization</span></span>](https://aka.ms/SkypeToTeams-UserReadiness)
- [<span data-ttu-id="ae733-112">Пробные испытания</span><span class="sxs-lookup"><span data-stu-id="ae733-112">Conducted a pilot</span></span>](https://aka.ms/SkypeToTeams-Pilot)

# <a name="upgrade-from-skype-for-business-online-to-teams"></a><span data-ttu-id="ae733-113">Переход со Skype для бизнеса Online на Teams</span><span class="sxs-lookup"><span data-stu-id="ae733-113">Upgrade from Skype for Business Online to Teams</span></span>

<span data-ttu-id="ae733-114">Следуйте указаниям, приведенным в этой статье, если вы полностью развернули Skype для бизнеса Online и хотите обновить пользователей в Skype для бизнеса в Teams.</span><span class="sxs-lookup"><span data-stu-id="ae733-114">Follow the guidance in this article if you have wholly deployed Skype for Business Online and want to upgrade your users from Skype for Business to Teams.</span></span> <span data-ttu-id="ae733-115">Вы можете обновить пользователей выборочно или полностью в зависимости от пути обновления, который выбрала ваша организация, путем назначения соответствующего режима сосуществования и обновления для пользователей.</span><span class="sxs-lookup"><span data-stu-id="ae733-115">You can upgrade users selectively or all-in, based on the upgrade journey that your organization has chosen, by assigning the appropriate coexistence and upgrade mode to your users.</span></span>

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]

## <a name="assign-the-coexistence-and-upgrade-mode"></a><span data-ttu-id="ae733-116">Назначение режима сосуществования и обновления</span><span class="sxs-lookup"><span data-stu-id="ae733-116">Assign the coexistence and upgrade mode</span></span>

<span data-ttu-id="ae733-117">Вы можете обновить пользователей до Теамсонли Mode, назначив экземпляр Упградетотеамс Теамсупградеполици, который может быть выполнен с помощью центра администрирования Microsoft Teams или удаленного сеанса Windows PowerShell из состава Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="ae733-117">You can upgrade your users to TeamsOnly mode by assigning the UpgradeToTeams instance of TeamsUpgradePolicy, which can be performed by using the Microsoft Teams admin center or a Skype for Business remote Windows Powershell session.</span></span> <span data-ttu-id="ae733-118">Это можно сделать отдельно для каждого пользователя или на уровне клиента, если вы хотите угпраде весь клиент за один шаг.</span><span class="sxs-lookup"><span data-stu-id="ae733-118">You can do this either on a per user basis, or on a tenant-wide basis if you want to ugprade the entire tenant in one step.</span></span> 

<span data-ttu-id="ae733-119">Дополнительные сведения можно найти [в статье Настройка параметров сосуществования и обновления](https://aka.ms/SkypeToTeams-SetCoexistence) и [теамсупградеполици: управление миграцией и](migration-interop-guidance-for-teams-with-skype.md#teamsupgradepolicy-managing-migration-and-co-existence)сосуществованием.</span><span class="sxs-lookup"><span data-stu-id="ae733-119">For more information, see [Setting your coexistence and upgrade settings](https://aka.ms/SkypeToTeams-SetCoexistence) and [TeamsUpgradePolicy: managing migration and coexistence](migration-interop-guidance-for-teams-with-skype.md#teamsupgradepolicy-managing-migration-and-co-existence).</span></span>

## <a name="upgrade-all-users-to-teams-at-one-time"></a><span data-ttu-id="ae733-120">Одновременный переход на новую версию всех пользователей в Teams</span><span class="sxs-lookup"><span data-stu-id="ae733-120">Upgrade all users to Teams at one time</span></span>

<span data-ttu-id="ae733-121">Выполните указанные ниже действия, чтобы одновременно обновить всех пользователей до Teams.</span><span class="sxs-lookup"><span data-stu-id="ae733-121">Follow these steps to upgrade all of your users to Teams at one time.</span></span>

### <a name="step-1-notify-the-users-of-the-change-optional"></a><span data-ttu-id="ae733-122">Шаг 1: уведомление пользователей об изменении (необязательно)</span><span class="sxs-lookup"><span data-stu-id="ae733-122">Step 1: Notify the users of the change (optional)</span></span>

1. <span data-ttu-id="ae733-123">В центре администрирования Microsoft Teams выберите > **Обновление Teams**по **всей Организации**.</span><span class="sxs-lookup"><span data-stu-id="ae733-123">In the Microsoft Teams admin center, select **Org-wide settings** > **Teams upgrade**.</span></span>
2. <span data-ttu-id="ae733-124">В разделе **режим**сосуществования измените параметр **уведомлять пользователей Skype для бизнеса о доступности обновления для Teams** . \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="ae733-124">Under **Coexistence mode**, change the **Notify Skype for Business users that an upgrade to Teams is available** switch to **On**.</span></span>

### <a name="step-2-set-the-coexistence-mode-to-teamsonly-for-the-organization"></a><span data-ttu-id="ae733-125">Шаг 2: Настройка режима сосуществования Теамсонли для Организации</span><span class="sxs-lookup"><span data-stu-id="ae733-125">Step 2: Set the coexistence mode to TeamsOnly for the organization</span></span>

1. <span data-ttu-id="ae733-126">В центре администрирования Microsoft Teams выберите **параметры для всей Организации**.</span><span class="sxs-lookup"><span data-stu-id="ae733-126">In the Microsoft Teams admin center, select **Org-wide settings**.</span></span>
2. <span data-ttu-id="ae733-127">В раскрывающемся списке **режим совместного существования** выберите режим " **только** для Teams".</span><span class="sxs-lookup"><span data-stu-id="ae733-127">Select **Teams Only** mode from the **Coexistence mode** drop-down list.</span></span>

## <a name="upgrade-users-in-stages"></a><span data-ttu-id="ae733-128">Обновление пользователей на этапах</span><span class="sxs-lookup"><span data-stu-id="ae733-128">Upgrade users in stages</span></span>

<span data-ttu-id="ae733-129">Если вы хотите постепенно обновить пользователей до Теамсонли, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="ae733-129">Follow these steps if you want to gradually upgrade your users to TeamsOnly.</span></span>

### <a name="step-1-identify-groups-of-users-for-upgrade"></a><span data-ttu-id="ae733-130">Шаг 1: определение групп пользователей для обновления</span><span class="sxs-lookup"><span data-stu-id="ae733-130">Step 1: Identify groups of users for upgrade</span></span>

<span data-ttu-id="ae733-131">Часто организации могут выбрать обновление своих организаций в случае успеха пользователей.</span><span class="sxs-lookup"><span data-stu-id="ae733-131">Often organizations may choose to upgrade their organizations in success waves of users.</span></span>  <span data-ttu-id="ae733-132">Прежде чем вы сможете легко найти их в центре администрирования Microsoft Teams, вы должны сначала идентифицировать этих пользователей.</span><span class="sxs-lookup"><span data-stu-id="ae733-132">You'll want to identify these users first so you can easily search for them in the Microsoft Teams admin center.</span></span> <span data-ttu-id="ae733-133">Кроме того, вы можете использовать PowerShell для более эффективного выполнения этой задачи.</span><span class="sxs-lookup"><span data-stu-id="ae733-133">Alternatively, you may want to use PowerShell to more efficiently do this.</span></span> <span data-ttu-id="ae733-134">После того как вы определили набор пользователей для данной звуковой волны, выполните оставшиеся действия.</span><span class="sxs-lookup"><span data-stu-id="ae733-134">Once you have identified the set of users for a given upgrade wave, continue with the remaining steps.</span></span>

### <a name="step-2-set-notification-for-the-users-in-the-current-ugprade-wave-optional"></a><span data-ttu-id="ae733-135">Шаг 2: Настройка уведомлений для пользователей в текущей угпраде волна (необязательно)</span><span class="sxs-lookup"><span data-stu-id="ae733-135">Step 2: Set notification for the users in the current ugprade wave (optional)</span></span>

<span data-ttu-id="ae733-136">Если вы используете центр администрирования Microsoft Teams, вы можете настроить Теамсупградеполици для работы до 20 пользователей одновременно:</span><span class="sxs-lookup"><span data-stu-id="ae733-136">If using the Microsoft Teams admin center, you can configure TeamsUpgradePolicy for up to 20 user at once:</span></span>
1. <span data-ttu-id="ae733-137">В центре администрирования Microsoft Teams выберите пункт **Пользователи**, а затем — один или несколько флажков для пользователей, которые должны быть обновлены до 20.</span><span class="sxs-lookup"><span data-stu-id="ae733-137">In the Microsoft Teams admin center, select **Users**, and find and multi-select the checkbox for up to 20 users who should be upgraded.</span></span> 
2. <span data-ttu-id="ae733-138">Нажмите кнопку **изменить параметры** в левом верхнем углу ListView.</span><span class="sxs-lookup"><span data-stu-id="ae733-138">Select **Edit settings** in the upper left corner of the listview.</span></span> 
3. <span data-ttu-id="ae733-139">На панели " **Редактирование параметров** " справа в разделе **Обновление Teams**нажмите изменить, чтобы перейти на вкладку **пользователь Skype для бизнеса** . \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="ae733-139">In the **Edit settings** pane on the right, under **Teams upgrade**, change **Notify the Skype for Business user** switch to **On**.</span></span> <span data-ttu-id="ae733-140">Примечание. Если параметр режимом сосуществования имеет значение "использовать параметры организации", этот параметр не отображается, поэтому необходимо явным образом задать режим совместного существования для этих пользователей в соответствии со значением по умолчанию для Организации.</span><span class="sxs-lookup"><span data-stu-id="ae733-140">Note: If the value of coexistence mode is "Use Org-wide settings", you won't see this switch, so you'll need to first explicitly set the Coexistence mode for these users to whatever the default value is for the org.</span></span>

<span data-ttu-id="ae733-141">Кроме того, вы можете легко включить уведомления для групп пользователей одновременно с помощью PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ae733-141">Alternatively, you may find it easier to enable notifications for groups of users at once using PowerShell.</span></span> 

### <a name="step-3-set-the-coexistence-mode-for-users-to-teams-only"></a><span data-ttu-id="ae733-142">Шаг 3: Настройка режима сосуществования для пользователей в Teams</span><span class="sxs-lookup"><span data-stu-id="ae733-142">Step 3: Set the coexistence mode for users to Teams Only</span></span>

<span data-ttu-id="ae733-143">Когда вы будете готовы обновить пользователей в текущей звуковой области, чтобы использовать их в качестве единственного приложения, установите для них режим сосуществования только для пользователей Teams.</span><span class="sxs-lookup"><span data-stu-id="ae733-143">When you are ready to upgrade the users in the current wave to use Teams as their only application, set the Coexistence mode for the users to Teams Only.</span></span>

<span data-ttu-id="ae733-144">Если вы используете центр администрирования Microsoft Teams, вы можете настроить Теамсупградеполици для работы до 20 пользователей одновременно:</span><span class="sxs-lookup"><span data-stu-id="ae733-144">If using the Microsoft Teams admin center, you can configure TeamsUpgradePolicy for up to 20 user at once:</span></span>
1. <span data-ttu-id="ae733-145">В центре администрирования Microsoft Teams выберите пункт **Пользователи**, а затем установите флажок до 20 пользователей.</span><span class="sxs-lookup"><span data-stu-id="ae733-145">In the Microsoft Teams admin center, select **Users**, and then select the checkbox for up to 20 users.</span></span>
2. <span data-ttu-id="ae733-146">Нажмите кнопку **изменить параметры** в левом верхнем углу ListView.</span><span class="sxs-lookup"><span data-stu-id="ae733-146">Select **Edit settings** in the upper left corner of the listview.</span></span>
3. <span data-ttu-id="ae733-147">В области **изменить параметры** справа в разделе **Обновление Teams** установите режим сосуществования для **Teams только** в раскрывающемся списке.</span><span class="sxs-lookup"><span data-stu-id="ae733-147">In the **Edit settings** pane on the right, under **Teams upgrade** section, set the coexistence mode to **Teams Only** in the drop-down list.</span></span>

<span data-ttu-id="ae733-148">Кроме того, вы можете легко обновлять группы пользователей одновременно с помощью PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ae733-148">Alternatively, you may find it easier to upgrade groups of users at once using PowerShell.</span></span> 

### <a name="step-4-repeat-steps-1-3-for-successive-waves-of-users"></a><span data-ttu-id="ae733-149">Шаг 4: Повторение шагов 1-3 для последовательной волны пользователей</span><span class="sxs-lookup"><span data-stu-id="ae733-149">Step 4: Repeat steps 1-3 for successive waves of users</span></span>

<span data-ttu-id="ae733-150">По мере проверки обновления до режима "только для Team" и готовности к развертыванию повторите предыдущие действия, чтобы применить Теамсонли для других пользователей.</span><span class="sxs-lookup"><span data-stu-id="ae733-150">As you validate your upgrade to Teams Only mode and are ready to expand, repeat the previous steps to apply TeamsOnly to  more users.</span></span>  


## <a name="phone-system-and-teams-upgrade"></a><span data-ttu-id="ae733-151">Обновление телефонной системы и команды</span><span class="sxs-lookup"><span data-stu-id="ae733-151">Phone System and Teams upgrade</span></span>

<span data-ttu-id="ae733-152">Если в развертывании Skype для бизнеса Online есть телефонная система с тарифными планами, а Microsoft является поставщиком услуг коммутируемой телефонной сети (PSTN), то при обновлении ваших пользователей в Teams будут автоматически переведены входящие звонки через PSTN в Teams.</span><span class="sxs-lookup"><span data-stu-id="ae733-152">If your Skype for Business Online deployment includes Phone System with Calling Plans and Microsoft is your public switched telephone network (PSTN) provider, upgrading your users to Teams will automatically transition inbound PSTN calling to Teams.</span></span>

<span data-ttu-id="ae733-153">Если в развертывании Skype для бизнеса Online есть телефонная система с Cloud Connector Edition, ознакомьтесь с [дополнительными сведениями о прямой маршрутизации для телефонной системы](2-envision-make-my-service-decisions-direct-routing.md).</span><span class="sxs-lookup"><span data-stu-id="ae733-153">If your Skype for Business Online deployment includes Phone System with Cloud Connector Edition, see the [additional considerations for Phone System Direct Routing](2-envision-make-my-service-decisions-direct-routing.md).</span></span>
