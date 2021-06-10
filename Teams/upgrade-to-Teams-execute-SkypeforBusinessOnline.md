---
title: Обновив Skype для бизнеса Online до Microsoft Teams
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: Узнайте, как обновить организацию до Microsoft Teams из Skype для бизнеса Online.
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
ms.openlocfilehash: 7c35909bf7787242a07f89d1442a25365348c91a
ms.sourcegitcommit: 32e3bb588abcbeded2d885483384c06706b280eb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2021
ms.locfileid: "52282106"
---
# <a name="upgrade-from-skype-for-business-online-to-teams"></a><span data-ttu-id="1ae54-103">Переход со Skype для бизнеса Online на Teams</span><span class="sxs-lookup"><span data-stu-id="1ae54-103">Upgrade from Skype for Business Online to Teams</span></span>

<span data-ttu-id="1ae54-104">![Схема пути обновления с акцентом на развертывании и внедрении](media/upgrade-banner-deployment.png "Этапы пути обновления с акцентом на этапе развертывания и внедрения")</span><span class="sxs-lookup"><span data-stu-id="1ae54-104">![Upgrade journey diagram, emphasizing Deployment and Implementation](media/upgrade-banner-deployment.png "Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage")</span></span>

<span data-ttu-id="1ae54-105">Эта статья является частью этапа развертывания и реализации, на который вы входите.</span><span class="sxs-lookup"><span data-stu-id="1ae54-105">This article is part of Deployment and Implementation stage of your upgrade journey.</span></span> <span data-ttu-id="1ae54-106">Прежде чем при этом подтверждать, что вы выполнили следующие действия:</span><span class="sxs-lookup"><span data-stu-id="1ae54-106">Before proceeding, confirm that you've completed the following activities:</span></span>

- [<span data-ttu-id="1ae54-107">Привлечение заинтересованных лиц по проекту</span><span class="sxs-lookup"><span data-stu-id="1ae54-107">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
- [<span data-ttu-id="1ae54-108">Определение области проекта</span><span class="sxs-lookup"><span data-stu-id="1ae54-108">Defined your project scope</span></span>](./upgrade-define-project-scope.md)
- [<span data-ttu-id="1ae54-109">Понятное сосуществование и совместное Skype для бизнеса и Teams</span><span class="sxs-lookup"><span data-stu-id="1ae54-109">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](./teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [<span data-ttu-id="1ae54-110">Выбор пути обновления</span><span class="sxs-lookup"><span data-stu-id="1ae54-110">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [<span data-ttu-id="1ae54-111">Подготовьте свою среду</span><span class="sxs-lookup"><span data-stu-id="1ae54-111">Prepared your environment</span></span>](./upgrade-prepare-environment.md)
- [<span data-ttu-id="1ae54-112">Подготовленные организации</span><span class="sxs-lookup"><span data-stu-id="1ae54-112">Prepared your organization</span></span>](./upgrade-prepare-organization.md)
- [<span data-ttu-id="1ae54-113">Пилотный проект</span><span class="sxs-lookup"><span data-stu-id="1ae54-113">Conducted a pilot</span></span>](./pilot-essentials.md)

<span data-ttu-id="1ae54-114">Следуйте указаниям в этой статье, если вы полностью развернули Skype для бизнеса Online и хотите обновить пользователей с Skype для бизнеса до Teams.</span><span class="sxs-lookup"><span data-stu-id="1ae54-114">Follow the guidance in this article if you have wholly deployed Skype for Business Online and want to upgrade your users from Skype for Business to Teams.</span></span> <span data-ttu-id="1ae54-115">Вы можете выборочно или полностью обновить пользователей в зависимости от того, как это было выбрано в вашей организации, назначив пользователям соответствующий режим совместной работы и обновления.</span><span class="sxs-lookup"><span data-stu-id="1ae54-115">You can upgrade users selectively or all-in, based on the upgrade journey that your organization has chosen, by assigning the appropriate coexistence and upgrade mode to your users.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1ae54-116">Поддержка Skype для бизнеса Online будет прекращена 31 июля 2021 г., после чего эта служба больше не будет доступна.</span><span class="sxs-lookup"><span data-stu-id="1ae54-116">Skype for Business Online will be retired on July 31, 2021, after which it will no longer be accessible or supported.</span></span> <span data-ttu-id="1ae54-117">Чтобы максимально увеличить преимущества и у вашей организации есть надлежащее время на реализацию обновления, мы рекомендуем начать свой путь к Microsoft Teams сегодня.</span><span class="sxs-lookup"><span data-stu-id="1ae54-117">To maximize benefit realization and ensure your organization has proper time to implement your upgrade, we encourage you to begin your journey to Microsoft Teams today.</span></span> <span data-ttu-id="1ae54-118">Помните, что успешное обновление соответствует технической и пользовательской готовности, поэтому при переходе к Microsoft Teams используйте эти рекомендации.</span><span class="sxs-lookup"><span data-stu-id="1ae54-118">Remember that a successful upgrade aligns technical and user readiness, so be sure to leverage the guidance herein as you navigate your journey to Microsoft Teams.</span></span>

## <a name="assign-the-coexistence-and-upgrade-mode"></a><span data-ttu-id="1ae54-119">Назначение режима сосуществования и обновления</span><span class="sxs-lookup"><span data-stu-id="1ae54-119">Assign the coexistence and upgrade mode</span></span>

<span data-ttu-id="1ae54-120">Вы можете перейти в режим TeamsOnly, назначив экземпляр UpgradeToTeams teamsUpgradePolicy, который можно выполнить с помощью Центра администрирования Microsoft Teams или удаленного Skype для бизнеса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1ae54-120">You can upgrade your users to TeamsOnly mode by assigning the UpgradeToTeams instance of TeamsUpgradePolicy, which can be performed by using the Microsoft Teams admin center or a Skype for Business remote Windows PowerShell session.</span></span> <span data-ttu-id="1ae54-121">Это можно сделать как для каждого пользователя, так и для всего клиента, если вы хотите обновить весь клиент одним шагом.</span><span class="sxs-lookup"><span data-stu-id="1ae54-121">You can do this either on a per user basis, or on a tenant-wide basis if you want to upgrade the entire tenant in one step.</span></span> 

<span data-ttu-id="1ae54-122">Дополнительные сведения [](./setting-your-coexistence-and-upgrade-settings.md) см. в настройках сосуществования и обновления [и TeamsUpgradePolicy:](upgrade-to-teams-on-prem-tools.md)управление миграцией и сосуществованием.</span><span class="sxs-lookup"><span data-stu-id="1ae54-122">For more information, see [Setting your coexistence and upgrade settings](./setting-your-coexistence-and-upgrade-settings.md) and [TeamsUpgradePolicy: managing migration and coexistence](upgrade-to-teams-on-prem-tools.md).</span></span>

## <a name="upgrade-all-users-to-teams-at-one-time"></a><span data-ttu-id="1ae54-123">Обновление всех пользователей до Teams за один раз</span><span class="sxs-lookup"><span data-stu-id="1ae54-123">Upgrade all users to Teams at one time</span></span>

<span data-ttu-id="1ae54-124">Выполните эти действия, чтобы обновить всех пользователей до Teams одновременно.</span><span class="sxs-lookup"><span data-stu-id="1ae54-124">Follow these steps to upgrade all of your users to Teams at one time.</span></span>

### <a name="step-1-notify-the-users-of-the-change-optional"></a><span data-ttu-id="1ae54-125">Шаг 1. Уведомление пользователей об изменении (необязательно)</span><span class="sxs-lookup"><span data-stu-id="1ae54-125">Step 1: Notify the users of the change (optional)</span></span>

1. <span data-ttu-id="1ae54-126">В Центре Microsoft Teams администрирования **выберите** параметры для всей организации Teams  >  **обновления**.</span><span class="sxs-lookup"><span data-stu-id="1ae54-126">In the Microsoft Teams admin center, select **Org-wide settings** > **Teams upgrade**.</span></span>
2. <span data-ttu-id="1ae54-127">В **режиме совместной** работы измените переключатель Уведомлять пользователей Skype для бизнеса о том, что доступно обновление до **Teams** **включит**.</span><span class="sxs-lookup"><span data-stu-id="1ae54-127">Under **Coexistence mode**, change the **Notify Skype for Business users that an upgrade to Teams is available** switch to **On**.</span></span>

### <a name="step-2-set-the-coexistence-mode-to-teamsonly-for-the-organization"></a><span data-ttu-id="1ae54-128">Шаг 2. Настройка режима сосуществования в TeamsOnly для организации</span><span class="sxs-lookup"><span data-stu-id="1ae54-128">Step 2: Set the coexistence mode to TeamsOnly for the organization</span></span>

1. <span data-ttu-id="1ae54-129">В центре Microsoft Teams выберите Параметры для **всей организации**.</span><span class="sxs-lookup"><span data-stu-id="1ae54-129">In the Microsoft Teams admin center, select **Org-wide settings**.</span></span>
2. <span data-ttu-id="1ae54-130">Выберите **Teams режиме** **только** в списке Режим совместной работы.</span><span class="sxs-lookup"><span data-stu-id="1ae54-130">Select **Teams Only** mode from the **Coexistence mode** drop-down list.</span></span>

## <a name="upgrade-users-in-stages"></a><span data-ttu-id="1ae54-131">Поэтапное обновление пользователей</span><span class="sxs-lookup"><span data-stu-id="1ae54-131">Upgrade users in stages</span></span>

<span data-ttu-id="1ae54-132">Если вы хотите постепенно обновлять пользователей до TeamsOnly, выполните указанные здесь действия.</span><span class="sxs-lookup"><span data-stu-id="1ae54-132">Follow these steps if you want to gradually upgrade your users to TeamsOnly.</span></span>

### <a name="step-1-identify-groups-of-users-for-upgrade"></a><span data-ttu-id="1ae54-133">Шаг 1. Определение групп пользователей для обновления</span><span class="sxs-lookup"><span data-stu-id="1ae54-133">Step 1: Identify groups of users for upgrade</span></span>

<span data-ttu-id="1ae54-134">Часто организации могут обновлять свои организации с волной успешного обновления пользователей.</span><span class="sxs-lookup"><span data-stu-id="1ae54-134">Often organizations may choose to upgrade their organizations in success waves of users.</span></span>  <span data-ttu-id="1ae54-135">Сначала определите этих пользователей, чтобы их можно было легко найти в Microsoft Teams центре администрирования.</span><span class="sxs-lookup"><span data-stu-id="1ae54-135">You'll want to identify these users first so you can easily search for them in the Microsoft Teams admin center.</span></span> <span data-ttu-id="1ae54-136">Кроме того, для более эффективной работы можно использовать PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1ae54-136">Alternatively, you may want to use PowerShell to more efficiently do this.</span></span> <span data-ttu-id="1ae54-137">После того как вы определили набор пользователей для заданного этапа обновления, продолжите работу с оставшимися действиями.</span><span class="sxs-lookup"><span data-stu-id="1ae54-137">Once you have identified the set of users for a given upgrade wave, continue with the remaining steps.</span></span>

### <a name="step-2-set-notification-for-the-users-in-the-current-upgrade-wave-optional"></a><span data-ttu-id="1ae54-138">Шаг 2. Настройка уведомлений для пользователей на текущем этапе обновления (необязательно)</span><span class="sxs-lookup"><span data-stu-id="1ae54-138">Step 2: Set notification for the users in the current upgrade wave (optional)</span></span>

<span data-ttu-id="1ae54-139">При использовании центра Microsoft Teams вы можете настроить TeamsUpgradePolicy для одновременного использования до 20 пользователей:</span><span class="sxs-lookup"><span data-stu-id="1ae54-139">If using the Microsoft Teams admin center, you can configure TeamsUpgradePolicy for up to 20 user at once:</span></span>
1. <span data-ttu-id="1ae54-140">В центре Microsoft Teams выберите Пользователи **,** а затем найдите и выберите несколько пользователей, для которых требуется обновить до 20 пользователей.</span><span class="sxs-lookup"><span data-stu-id="1ae54-140">In the Microsoft Teams admin center, select **Users**, and find and multi-select the checkbox for up to 20 users who should be upgraded.</span></span> 
2. <span data-ttu-id="1ae54-141">В **левом верхнем** углу списка выберите изменить параметры.</span><span class="sxs-lookup"><span data-stu-id="1ae54-141">Select **Edit settings** in the upper left corner of the listview.</span></span> 
3. <span data-ttu-id="1ae54-142">В области **Изменение параметров** справа в Teams **обновления** измените параметр Уведомить пользователя Skype для бизнеса **о** переходе на **Включит**.</span><span class="sxs-lookup"><span data-stu-id="1ae54-142">In the **Edit settings** pane on the right, under **Teams upgrade**, change **Notify the Skype for Business user** switch to **On**.</span></span> <span data-ttu-id="1ae54-143">Примечание. Если в режиме сосуществования используется значение "Использовать параметры для всей организации", этот переключатель не будет виден, поэтому необходимо сначала явно настроить для этих пользователей режим совместной работы, заключив его в стандартное значение для организации.</span><span class="sxs-lookup"><span data-stu-id="1ae54-143">Note: If the value of coexistence mode is "Use Org-wide settings", you won't see this switch, so you'll need to first explicitly set the Coexistence mode for these users to whatever the default value is for the org.</span></span>

<span data-ttu-id="1ae54-144">Кроме того, вам может быть проще включить уведомления для групп пользователей одновременно с помощью PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1ae54-144">Alternatively, you may find it easier to enable notifications for groups of users at once using PowerShell.</span></span> 

### <a name="step-3-set-the-coexistence-mode-for-users-to-teams-only"></a><span data-ttu-id="1ae54-145">Шаг 3. Настройка режима совместной работы для пользователей Teams только</span><span class="sxs-lookup"><span data-stu-id="1ae54-145">Step 3: Set the coexistence mode for users to Teams Only</span></span>

<span data-ttu-id="1ae54-146">Когда вы будете готовы обновить пользователей на текущем волне, чтобы использовать Teams в качестве своего приложения, установите для них режим "Только Teams".</span><span class="sxs-lookup"><span data-stu-id="1ae54-146">When you are ready to upgrade the users in the current wave to use Teams as their only application, set the Coexistence mode for the users to Teams Only.</span></span>

<span data-ttu-id="1ae54-147">При использовании центра Microsoft Teams вы можете настроить TeamsUpgradePolicy для одновременного использования до 20 пользователей:</span><span class="sxs-lookup"><span data-stu-id="1ae54-147">If using the Microsoft Teams admin center, you can configure TeamsUpgradePolicy for up to 20 user at once:</span></span>
1. <span data-ttu-id="1ae54-148">В центре Microsoft Teams выберите Пользователи **,** а затем выберите его для 20 пользователей.</span><span class="sxs-lookup"><span data-stu-id="1ae54-148">In the Microsoft Teams admin center, select **Users**, and then select the checkbox for up to 20 users.</span></span>
2. <span data-ttu-id="1ae54-149">В **левом верхнем** углу списка выберите изменить параметры.</span><span class="sxs-lookup"><span data-stu-id="1ae54-149">Select **Edit settings** in the upper left corner of the listview.</span></span>
3. <span data-ttu-id="1ae54-150">В **области Изменение параметров** справа  в разделе Teams обновления установите в списке  режим Teams только в списке.</span><span class="sxs-lookup"><span data-stu-id="1ae54-150">In the **Edit settings** pane on the right, under **Teams upgrade** section, set the coexistence mode to **Teams Only** in the drop-down list.</span></span>

<span data-ttu-id="1ae54-151">Кроме того, вам может быть проще обновить группы пользователей одновременно с помощью PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1ae54-151">Alternatively, you may find it easier to upgrade groups of users at once using PowerShell.</span></span> 

### <a name="step-4-repeat-steps-1-3-for-successive-waves-of-users"></a><span data-ttu-id="1ae54-152">Шаг 4. Повторите шаги 1–3 для последовательных волн пользователей</span><span class="sxs-lookup"><span data-stu-id="1ae54-152">Step 4: Repeat steps 1-3 for successive waves of users</span></span>

<span data-ttu-id="1ae54-153">После проверки обновления Teams режим только для расширения, повторите предыдущие действия, чтобы применить TeamsOnly к большему количества пользователей.</span><span class="sxs-lookup"><span data-stu-id="1ae54-153">As you validate your upgrade to Teams Only mode and are ready to expand, repeat the previous steps to apply TeamsOnly to  more users.</span></span>  


## <a name="phone-system-and-pstn-connectivity-options"></a><span data-ttu-id="1ae54-154">телефонная система подключения к ОКП и ОКП</span><span class="sxs-lookup"><span data-stu-id="1ae54-154">Phone System and PSTN connectivity options</span></span>

<span data-ttu-id="1ae54-155">телефонная система с Teams поддерживается после того, как пользователь находится в режиме TeamsOnly.</span><span class="sxs-lookup"><span data-stu-id="1ae54-155">Phone System with Teams is supported after the user is in TeamsOnly mode.</span></span> <span data-ttu-id="1ae54-156">(Если пользователь находится в режиме "Острова", телефонная система поддерживается только в Skype для бизнеса.)</span><span class="sxs-lookup"><span data-stu-id="1ae54-156">(If the user is in Islands mode, Phone System is only supported with Skype for Business.)</span></span>  

### <a name="pstn-connectivity-options"></a><span data-ttu-id="1ae54-157">Параметры подключения через ДНР</span><span class="sxs-lookup"><span data-stu-id="1ae54-157">PSTN connectivity options</span></span>

<span data-ttu-id="1ae54-158">При рассмотрении параметров подключения к телефонной сети общего перейти из Skype для бизнеса Online в режим TeamsOnly можно двумя возможными.</span><span class="sxs-lookup"><span data-stu-id="1ae54-158">When considering Public Switched Telephone Network (PSTN) connectivity options, there are two possible scenarios when moving from Skype for Business Online to TeamsOnly mode:</span></span>

- <span data-ttu-id="1ae54-159">Пользователь в Skype для бизнеса Online с планом звонков Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="1ae54-159">A user in Skype for Business Online, with a Microsoft Calling Plan.</span></span> <span data-ttu-id="1ae54-160">После обновления у этого пользователя сохранится план Microsoft Calling.</span><span class="sxs-lookup"><span data-stu-id="1ae54-160">Upon upgrade, this user will continue to have a Microsoft Calling plan.</span></span> <span data-ttu-id="1ae54-161">Это самый простой сценарий, требующий всего нескольких действий.</span><span class="sxs-lookup"><span data-stu-id="1ae54-161">This is the simplest scenario requiring only a couple of steps.</span></span> <span data-ttu-id="1ae54-162">Дополнительные сведения см. в [Skype для бизнеса Online с планами звонков Майкрософт.](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-online-with-microsoft-calling-plans)</span><span class="sxs-lookup"><span data-stu-id="1ae54-162">For more information, see [From Skype for Business Online with Microsoft Calling Plans](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-online-with-microsoft-calling-plans).</span></span>

- <span data-ttu-id="1ae54-163">Пользователь в Skype для бизнеса Online с функцией локального голосового подключения через Skype для бизнеса или Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="1ae54-163">A user in Skype for Business Online, with on-premises voice functionality through Skype for Business on-premises or Cloud Connector Edition.</span></span> <span data-ttu-id="1ae54-164">Обновление пользователя до Teams должно быть согласовано с миграцией пользователя на прямую маршрутику, чтобы гарантировать, что у пользователя TeamsOnly есть функциональность ОКП.</span><span class="sxs-lookup"><span data-stu-id="1ae54-164">The user’s upgrade to Teams needs to be coordinated with migration of the user to Direct Routing to ensure the TeamsOnly user has PSTN functionality.</span></span>  <span data-ttu-id="1ae54-165">Дополнительные сведения [см. в Skype для бизнеса Online с локальной голосовой информацией.](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-online-with-on-premises-voice)</span><span class="sxs-lookup"><span data-stu-id="1ae54-165">For more information see, [From Skype for Business Online with on-premises voice](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-online-with-on-premises-voice).</span></span>