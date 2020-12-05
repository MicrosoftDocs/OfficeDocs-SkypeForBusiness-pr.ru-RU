---
title: Переход с Skype для бизнеса Online на Microsoft Teams
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: Сведения о том, как обновить организационную структуру до Microsoft Teams с помощью развертывания Skype для бизнеса Online.
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
ms.openlocfilehash: ca99c193a17547943018eba75004f0ec0a1a92f3
ms.sourcegitcommit: 1e16c6c7112bdde03209c12468b5705ddd116a62
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2020
ms.locfileid: "49578262"
---
# <a name="upgrade-from-skype-for-business-online-to-teams"></a><span data-ttu-id="8bb57-103">Переход со Skype для бизнеса Online на Teams</span><span class="sxs-lookup"><span data-stu-id="8bb57-103">Upgrade from Skype for Business Online to Teams</span></span>

<span data-ttu-id="8bb57-104">![Обновление схемы поездки, акцент на развертывании и реализации](media/upgrade-banner-deployment.png "Этапы поездки на обновление, акцент на этапе развертывания и реализации")</span><span class="sxs-lookup"><span data-stu-id="8bb57-104">![Upgrade journey diagram, emphasizing Deployment and Implementation](media/upgrade-banner-deployment.png "Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage")</span></span>

<span data-ttu-id="8bb57-105">Эта статья является частью стадии развертывания и внедрения вашего путешествия по обновлению.</span><span class="sxs-lookup"><span data-stu-id="8bb57-105">This article is part of Deployment and Implementation stage of your upgrade journey.</span></span> <span data-ttu-id="8bb57-106">Перед продолжением убедитесь, что выполнены следующие действия:</span><span class="sxs-lookup"><span data-stu-id="8bb57-106">Before proceeding, confirm that you've completed the following activities:</span></span>

- [<span data-ttu-id="8bb57-107">Вовлеченные заинтересованные лица в проект</span><span class="sxs-lookup"><span data-stu-id="8bb57-107">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
- [<span data-ttu-id="8bb57-108">Определение области охвата проекта</span><span class="sxs-lookup"><span data-stu-id="8bb57-108">Defined your project scope</span></span>](https://aka.ms/SkypetoTeams-Scope)
- [<span data-ttu-id="8bb57-109">Сосуществование и взаимодействие Skype для бизнеса и рабочих групп</span><span class="sxs-lookup"><span data-stu-id="8bb57-109">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](https://aka.ms/SkypeToTeams-Coexist)
- [<span data-ttu-id="8bb57-110">Выбрано путешествие с обновлением</span><span class="sxs-lookup"><span data-stu-id="8bb57-110">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [<span data-ttu-id="8bb57-111">Подготовка среды</span><span class="sxs-lookup"><span data-stu-id="8bb57-111">Prepared your environment</span></span>](https://aka.ms/SkypeToTeams-TechnicalReadiness)
- [<span data-ttu-id="8bb57-112">Подготовка Организации</span><span class="sxs-lookup"><span data-stu-id="8bb57-112">Prepared your organization</span></span>](https://aka.ms/SkypeToTeams-UserReadiness)
- [<span data-ttu-id="8bb57-113">Пробные испытания</span><span class="sxs-lookup"><span data-stu-id="8bb57-113">Conducted a pilot</span></span>](https://aka.ms/SkypeToTeams-Pilot)

<span data-ttu-id="8bb57-114">Следуйте указаниям, приведенным в этой статье, если вы полностью развернули Skype для бизнеса Online и хотите обновить пользователей в Skype для бизнеса в Teams.</span><span class="sxs-lookup"><span data-stu-id="8bb57-114">Follow the guidance in this article if you have wholly deployed Skype for Business Online and want to upgrade your users from Skype for Business to Teams.</span></span> <span data-ttu-id="8bb57-115">Вы можете обновить пользователей выборочно или полностью в зависимости от пути обновления, который выбрала ваша организация, путем назначения соответствующего режима сосуществования и обновления для пользователей.</span><span class="sxs-lookup"><span data-stu-id="8bb57-115">You can upgrade users selectively or all-in, based on the upgrade journey that your organization has chosen, by assigning the appropriate coexistence and upgrade mode to your users.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8bb57-116">Поддержка Skype для бизнеса Online будет прекращена 31 июля 2021 г., после чего эта служба больше не будет доступна.</span><span class="sxs-lookup"><span data-stu-id="8bb57-116">Skype for Business Online will be retired on July 31, 2021, after which it will no longer be accessible or supported.</span></span> <span data-ttu-id="8bb57-117">Чтобы повысить эффективность реализации льготы и убедиться в том, что в вашей организации установлено правильное время для внедрения вашего обновления, мы рекомендуем начать путешествие в Microsoft Teams уже сегодня.</span><span class="sxs-lookup"><span data-stu-id="8bb57-117">To maximize benefit realization and ensure your organization has proper time to implement your upgrade, we encourage you to begin your journey to Microsoft Teams today.</span></span> <span data-ttu-id="8bb57-118">Помните о том, что успешное обновление ориентировано на техническую и пользовательскую готовность, поэтому не забудьте использовать руководство для навигации в Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="8bb57-118">Remember that a successful upgrade aligns technical and user readiness, so be sure to leverage the guidance herein as you navigate your journey to Microsoft Teams.</span></span>

## <a name="assign-the-coexistence-and-upgrade-mode"></a><span data-ttu-id="8bb57-119">Назначение режима сосуществования и обновления</span><span class="sxs-lookup"><span data-stu-id="8bb57-119">Assign the coexistence and upgrade mode</span></span>

<span data-ttu-id="8bb57-120">Вы можете обновить пользователей до TeamsOnly Mode, назначив экземпляр UpgradeToTeams TeamsUpgradePolicy, который может быть выполнен с помощью центра администрирования Microsoft Teams или удаленного сеанса Windows PowerShell из состава Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="8bb57-120">You can upgrade your users to TeamsOnly mode by assigning the UpgradeToTeams instance of TeamsUpgradePolicy, which can be performed by using the Microsoft Teams admin center or a Skype for Business remote Windows PowerShell session.</span></span> <span data-ttu-id="8bb57-121">Это можно сделать отдельно для каждого пользователя или на уровне клиента, если вы хотите обновить весь клиент за один шаг.</span><span class="sxs-lookup"><span data-stu-id="8bb57-121">You can do this either on a per user basis, or on a tenant-wide basis if you want to upgrade the entire tenant in one step.</span></span> 

<span data-ttu-id="8bb57-122">Дополнительные сведения можно найти [в статье Настройка параметров сосуществования и обновления](https://aka.ms/SkypeToTeams-SetCoexistence) и [TeamsUpgradePolicy: управление миграцией и сосуществованием](upgrade-to-teams-on-prem-tools.md).</span><span class="sxs-lookup"><span data-stu-id="8bb57-122">For more information, see [Setting your coexistence and upgrade settings](https://aka.ms/SkypeToTeams-SetCoexistence) and [TeamsUpgradePolicy: managing migration and coexistence](upgrade-to-teams-on-prem-tools.md).</span></span>

## <a name="upgrade-all-users-to-teams-at-one-time"></a><span data-ttu-id="8bb57-123">Одновременный переход на новую версию всех пользователей в Teams</span><span class="sxs-lookup"><span data-stu-id="8bb57-123">Upgrade all users to Teams at one time</span></span>

<span data-ttu-id="8bb57-124">Выполните указанные ниже действия, чтобы одновременно обновить всех пользователей до Teams.</span><span class="sxs-lookup"><span data-stu-id="8bb57-124">Follow these steps to upgrade all of your users to Teams at one time.</span></span>

### <a name="step-1-notify-the-users-of-the-change-optional"></a><span data-ttu-id="8bb57-125">Шаг 1: уведомление пользователей об изменении (необязательно)</span><span class="sxs-lookup"><span data-stu-id="8bb57-125">Step 1: Notify the users of the change (optional)</span></span>

1. <span data-ttu-id="8bb57-126">В центре администрирования Microsoft Teams выберите **Org-wide settings**  >  **Обновление Teams** по всей Организации.</span><span class="sxs-lookup"><span data-stu-id="8bb57-126">In the Microsoft Teams admin center, select **Org-wide settings** > **Teams upgrade**.</span></span>
2. <span data-ttu-id="8bb57-127">В разделе **режим сосуществования** измените параметр **уведомлять пользователей Skype для бизнеса о доступности обновления для Teams** **.**</span><span class="sxs-lookup"><span data-stu-id="8bb57-127">Under **Coexistence mode**, change the **Notify Skype for Business users that an upgrade to Teams is available** switch to **On**.</span></span>

### <a name="step-2-set-the-coexistence-mode-to-teamsonly-for-the-organization"></a><span data-ttu-id="8bb57-128">Шаг 2: Настройка режима сосуществования TeamsOnly для Организации</span><span class="sxs-lookup"><span data-stu-id="8bb57-128">Step 2: Set the coexistence mode to TeamsOnly for the organization</span></span>

1. <span data-ttu-id="8bb57-129">В центре администрирования Microsoft Teams выберите **параметры для всей Организации**.</span><span class="sxs-lookup"><span data-stu-id="8bb57-129">In the Microsoft Teams admin center, select **Org-wide settings**.</span></span>
2. <span data-ttu-id="8bb57-130">В раскрывающемся списке **режим совместного существования** выберите режим " **только для Teams** ".</span><span class="sxs-lookup"><span data-stu-id="8bb57-130">Select **Teams Only** mode from the **Coexistence mode** drop-down list.</span></span>

## <a name="upgrade-users-in-stages"></a><span data-ttu-id="8bb57-131">Обновление пользователей на этапах</span><span class="sxs-lookup"><span data-stu-id="8bb57-131">Upgrade users in stages</span></span>

<span data-ttu-id="8bb57-132">Если вы хотите постепенно обновить пользователей до TeamsOnly, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="8bb57-132">Follow these steps if you want to gradually upgrade your users to TeamsOnly.</span></span>

### <a name="step-1-identify-groups-of-users-for-upgrade"></a><span data-ttu-id="8bb57-133">Шаг 1: определение групп пользователей для обновления</span><span class="sxs-lookup"><span data-stu-id="8bb57-133">Step 1: Identify groups of users for upgrade</span></span>

<span data-ttu-id="8bb57-134">Часто организации могут выбрать обновление своих организаций в случае успеха пользователей.</span><span class="sxs-lookup"><span data-stu-id="8bb57-134">Often organizations may choose to upgrade their organizations in success waves of users.</span></span>  <span data-ttu-id="8bb57-135">Прежде чем вы сможете легко найти их в центре администрирования Microsoft Teams, вы должны сначала идентифицировать этих пользователей.</span><span class="sxs-lookup"><span data-stu-id="8bb57-135">You'll want to identify these users first so you can easily search for them in the Microsoft Teams admin center.</span></span> <span data-ttu-id="8bb57-136">Кроме того, вы можете использовать PowerShell для более эффективного выполнения этой задачи.</span><span class="sxs-lookup"><span data-stu-id="8bb57-136">Alternatively, you may want to use PowerShell to more efficiently do this.</span></span> <span data-ttu-id="8bb57-137">После того как вы определили набор пользователей для данной звуковой волны, выполните оставшиеся действия.</span><span class="sxs-lookup"><span data-stu-id="8bb57-137">Once you have identified the set of users for a given upgrade wave, continue with the remaining steps.</span></span>

### <a name="step-2-set-notification-for-the-users-in-the-current-upgrade-wave-optional"></a><span data-ttu-id="8bb57-138">Шаг 2: Настройка уведомлений для пользователей в текущей звуковой версии обновления (необязательно)</span><span class="sxs-lookup"><span data-stu-id="8bb57-138">Step 2: Set notification for the users in the current upgrade wave (optional)</span></span>

<span data-ttu-id="8bb57-139">Если вы используете центр администрирования Microsoft Teams, вы можете настроить TeamsUpgradePolicy для работы до 20 пользователей одновременно:</span><span class="sxs-lookup"><span data-stu-id="8bb57-139">If using the Microsoft Teams admin center, you can configure TeamsUpgradePolicy for up to 20 user at once:</span></span>
1. <span data-ttu-id="8bb57-140">В центре администрирования Microsoft Teams выберите пункт **Пользователи**, а затем — один или несколько флажков для пользователей, которые должны быть обновлены до 20.</span><span class="sxs-lookup"><span data-stu-id="8bb57-140">In the Microsoft Teams admin center, select **Users**, and find and multi-select the checkbox for up to 20 users who should be upgraded.</span></span> 
2. <span data-ttu-id="8bb57-141">Нажмите кнопку **изменить параметры** в левом верхнем углу ListView.</span><span class="sxs-lookup"><span data-stu-id="8bb57-141">Select **Edit settings** in the upper left corner of the listview.</span></span> 
3. <span data-ttu-id="8bb57-142">На панели " **Редактирование параметров** " справа в разделе **Обновление Teams** нажмите изменить **, чтобы перейти на вкладку** **пользователь Skype для бизнеса** .</span><span class="sxs-lookup"><span data-stu-id="8bb57-142">In the **Edit settings** pane on the right, under **Teams upgrade**, change **Notify the Skype for Business user** switch to **On**.</span></span> <span data-ttu-id="8bb57-143">Примечание. Если параметр режимом сосуществования имеет значение "использовать параметры организации", этот параметр не отображается, поэтому необходимо явным образом задать режим совместного существования для этих пользователей в соответствии со значением по умолчанию для Организации.</span><span class="sxs-lookup"><span data-stu-id="8bb57-143">Note: If the value of coexistence mode is "Use Org-wide settings", you won't see this switch, so you'll need to first explicitly set the Coexistence mode for these users to whatever the default value is for the org.</span></span>

<span data-ttu-id="8bb57-144">Кроме того, вы можете легко включить уведомления для групп пользователей одновременно с помощью PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8bb57-144">Alternatively, you may find it easier to enable notifications for groups of users at once using PowerShell.</span></span> 

### <a name="step-3-set-the-coexistence-mode-for-users-to-teams-only"></a><span data-ttu-id="8bb57-145">Шаг 3: Настройка режима сосуществования для пользователей в Teams</span><span class="sxs-lookup"><span data-stu-id="8bb57-145">Step 3: Set the coexistence mode for users to Teams Only</span></span>

<span data-ttu-id="8bb57-146">Когда вы будете готовы обновить пользователей в текущей звуковой области, чтобы использовать их в качестве единственного приложения, установите для них режим сосуществования только для пользователей Teams.</span><span class="sxs-lookup"><span data-stu-id="8bb57-146">When you are ready to upgrade the users in the current wave to use Teams as their only application, set the Coexistence mode for the users to Teams Only.</span></span>

<span data-ttu-id="8bb57-147">Если вы используете центр администрирования Microsoft Teams, вы можете настроить TeamsUpgradePolicy для работы до 20 пользователей одновременно:</span><span class="sxs-lookup"><span data-stu-id="8bb57-147">If using the Microsoft Teams admin center, you can configure TeamsUpgradePolicy for up to 20 user at once:</span></span>
1. <span data-ttu-id="8bb57-148">В центре администрирования Microsoft Teams выберите пункт **Пользователи**, а затем установите флажок до 20 пользователей.</span><span class="sxs-lookup"><span data-stu-id="8bb57-148">In the Microsoft Teams admin center, select **Users**, and then select the checkbox for up to 20 users.</span></span>
2. <span data-ttu-id="8bb57-149">Нажмите кнопку **изменить параметры** в левом верхнем углу ListView.</span><span class="sxs-lookup"><span data-stu-id="8bb57-149">Select **Edit settings** in the upper left corner of the listview.</span></span>
3. <span data-ttu-id="8bb57-150">В области **изменить параметры** справа в разделе **Обновление Teams** установите режим сосуществования для **Teams только** в раскрывающемся списке.</span><span class="sxs-lookup"><span data-stu-id="8bb57-150">In the **Edit settings** pane on the right, under **Teams upgrade** section, set the coexistence mode to **Teams Only** in the drop-down list.</span></span>

<span data-ttu-id="8bb57-151">Кроме того, вы можете легко обновлять группы пользователей одновременно с помощью PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8bb57-151">Alternatively, you may find it easier to upgrade groups of users at once using PowerShell.</span></span> 

### <a name="step-4-repeat-steps-1-3-for-successive-waves-of-users"></a><span data-ttu-id="8bb57-152">Шаг 4: Повторение шагов 1-3 для последовательной волны пользователей</span><span class="sxs-lookup"><span data-stu-id="8bb57-152">Step 4: Repeat steps 1-3 for successive waves of users</span></span>

<span data-ttu-id="8bb57-153">По мере проверки обновления до режима "только для Team" и готовности к развертыванию повторите предыдущие действия, чтобы применить TeamsOnly для других пользователей.</span><span class="sxs-lookup"><span data-stu-id="8bb57-153">As you validate your upgrade to Teams Only mode and are ready to expand, repeat the previous steps to apply TeamsOnly to  more users.</span></span>  


## <a name="phone-system-and-pstn-connectivity-options"></a><span data-ttu-id="8bb57-154">Параметры телефонной системы и подключения к PSTN</span><span class="sxs-lookup"><span data-stu-id="8bb57-154">Phone System and PSTN connectivity options</span></span>

<span data-ttu-id="8bb57-155">Телефонная система с командами поддерживается после того, как пользователь в TeamsOnly режиме.</span><span class="sxs-lookup"><span data-stu-id="8bb57-155">Phone System with Teams is supported after the user is in TeamsOnly mode.</span></span> <span data-ttu-id="8bb57-156">(Если пользователь находится в режиме острова, телефонная система поддерживается только в Skype для бизнеса.)</span><span class="sxs-lookup"><span data-stu-id="8bb57-156">(If the user is in Islands mode, Phone System is only supported with Skype for Business.)</span></span>  

### <a name="pstn-connectivity-options"></a><span data-ttu-id="8bb57-157">Варианты подключения PSTN</span><span class="sxs-lookup"><span data-stu-id="8bb57-157">PSTN connectivity options</span></span>

<span data-ttu-id="8bb57-158">При рассмотрении параметров подключения по коммутируемой телефонной сети (КТСОП) возможны два варианта перехода из Skype для бизнеса Online в режим TeamsOnly:</span><span class="sxs-lookup"><span data-stu-id="8bb57-158">When considering Public Switched Telephone Network (PSTN) connectivity options, there are two possible scenarios when moving from Skype for Business Online to TeamsOnly mode:</span></span>

- <span data-ttu-id="8bb57-159">Пользователь в Skype для бизнеса Online с планом вызова Microsoft.</span><span class="sxs-lookup"><span data-stu-id="8bb57-159">A user in Skype for Business Online, with a Microsoft Calling Plan.</span></span> <span data-ttu-id="8bb57-160">После обновления у этого пользователя будет по-прежнему содержаться план звонков по Microsoft.</span><span class="sxs-lookup"><span data-stu-id="8bb57-160">Upon upgrade, this user will continue to have a Microsoft Calling plan.</span></span> <span data-ttu-id="8bb57-161">Это самый простой сценарий, требующий всего несколько действий.</span><span class="sxs-lookup"><span data-stu-id="8bb57-161">This is the simplest scenario requiring only a couple of steps.</span></span> <span data-ttu-id="8bb57-162">Дополнительные сведения можно найти [в разделе Skype для бизнеса Online с планами вызовов Microsoft](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-online-with-microsoft-calling-plans).</span><span class="sxs-lookup"><span data-stu-id="8bb57-162">For more information, see [From Skype for Business Online with Microsoft Calling Plans](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-online-with-microsoft-calling-plans).</span></span>

- <span data-ttu-id="8bb57-163">Пользователь в Skype для бизнеса Online с локальной функцией голосовой связи через Skype для бизнеса в локальной или облачной версии.</span><span class="sxs-lookup"><span data-stu-id="8bb57-163">A user in Skype for Business Online, with on-premises voice functionality through Skype for Business on-premises or Cloud Connector Edition.</span></span> <span data-ttu-id="8bb57-164">Переход пользователя на Teams необходимо координировать с помощью миграции пользователя в направлении прямой маршрутизации, чтобы убедиться в том, что у пользователя TeamsOnly есть функция КТСОП.</span><span class="sxs-lookup"><span data-stu-id="8bb57-164">The user’s upgrade to Teams needs to be coordinated with migration of the user to Direct Routing to ensure the TeamsOnly user has PSTN functionality.</span></span>  <span data-ttu-id="8bb57-165">Дополнительные сведения можно найти в разделе [Skype для бизнеса Online с локальной голосовой](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-online-with-on-premises-voice)связью.</span><span class="sxs-lookup"><span data-stu-id="8bb57-165">For more information see, [From Skype for Business Online with on-premises voice](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-online-with-on-premises-voice).</span></span>


