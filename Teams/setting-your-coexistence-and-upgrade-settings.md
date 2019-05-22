---
title: Настройка сосуществования и обновления
author: tonysmit
ms.author: tonysmit
manager: serdars
ms.topic: article
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: bjwhalen
search.appverid: MET150
description: В этой статье рассказывается, как выбрать режим сосуществования и настроить другие параметры сосуществования.
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 52b398a9e70d650ad2afd70c60250076f1ab9fc2
ms.sourcegitcommit: 30995da65ff6a9b33534c3818833cf0ae1952ab9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/22/2019
ms.locfileid: "34344196"
---
# <a name="setting-your-coexistence-and-upgrade-settings"></a><span data-ttu-id="54054-103">Настройка сосуществования и обновления</span><span class="sxs-lookup"><span data-stu-id="54054-103">Setting your coexistence and upgrade settings</span></span>

> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

<span data-ttu-id="54054-104">Когда вы обновляете пользователей Skype для бизнеса, у вас есть несколько вариантов, с помощью которых вы можете сделать этот процесс бесперебойной работе пользователей.</span><span class="sxs-lookup"><span data-stu-id="54054-104">When you upgrade your Skype for Business users to use Teams, you have several options to help you make it a seamless process for your users.</span></span> <span data-ttu-id="54054-105">Вы можете настроить параметры сосуществования и обновления для всех пользователей в Организации одновременно или изменить параметры для одного или множества пользователей в Организации.</span><span class="sxs-lookup"><span data-stu-id="54054-105">You have the option to make coexistence and upgrade settings for all of the users in your organization at once, or you can make settings changes for a single or set of users in your organization.</span></span> <span data-ttu-id="54054-106">Обратите внимание, что в более ранних версиях клиентов Skype для бизнеса эти параметры могут не поддерживаться.</span><span class="sxs-lookup"><span data-stu-id="54054-106">Note that older versions of Skype for Business clients may not honor these settings.</span></span> <span data-ttu-id="54054-107">Дополнительные сведения о версиях клиента Skype для бизнеса можно найти на [странице загрузки и обновления в Skype для бизнеса](https://docs.microsoft.com/en-us/skypeforbusiness/software-updates).</span><span class="sxs-lookup"><span data-stu-id="54054-107">For more information about Skype for Business client versions, go to the [Skype for Business downloads and updates page](https://docs.microsoft.com/en-us/skypeforbusiness/software-updates).</span></span> 

<span data-ttu-id="54054-108">[С помощью Skype для бизнеса](coexistence-chat-calls-presence.md)вы сможете лучше понять, какие типы режимов доступны вам, в том, чтобы понять, как работают [Microsoft Teams и Skype для бизнеса, а также взаимодействие и](teams-and-skypeforbusiness-coexistence-and-interoperability.md) сосуществование.</span><span class="sxs-lookup"><span data-stu-id="54054-108">You can get a better understanding of the types of modes that are available to you by reading [Understand Microsoft Teams and Skype for Business coexistence and interoperability](teams-and-skypeforbusiness-coexistence-and-interoperability.md) or [Coexistence with Skype for Business](coexistence-chat-calls-presence.md).</span></span>  

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]


## <a name="set-upgrade-options-for-all-users-in-your-organization"></a><span data-ttu-id="54054-109">Настройка параметров обновления для всех пользователей в Организации</span><span class="sxs-lookup"><span data-stu-id="54054-109">Set upgrade options for all users in your organization</span></span>

<span data-ttu-id="54054-110">![Значок с логотипом](media/teams-logo-30x30.png) Microsoft Teams, в котором **используется центр администрирования Microsoft Teams**</span><span class="sxs-lookup"><span data-stu-id="54054-110">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="54054-111">На панели навигации слева перейдите к > **обновлению Teams**" **Параметры организации**".</span><span class="sxs-lookup"><span data-stu-id="54054-111">In the left navigation, go to **Org-wide settings** > **Teams upgrade**.</span></span> 

2. <span data-ttu-id="54054-112">В верхней части страницы **Обновление Teams** внесите указанные ниже изменения, если они будут работать.</span><span class="sxs-lookup"><span data-stu-id="54054-112">At the top of the **Teams upgrade** page, make the following changes if they will work for you.</span></span>
    - <span data-ttu-id="54054-113">Установка режима \*\*\*\* сосуществования.</span><span class="sxs-lookup"><span data-stu-id="54054-113">Set the **Coexistence** mode.</span></span>
        - <span data-ttu-id="54054-114">**О-ва** — используйте этот параметр, если вы хотите, чтобы пользователи могли одновременно использовать Skype для бизнеса и Teams.</span><span class="sxs-lookup"><span data-stu-id="54054-114">**Islands** - Use this setting if you want users to be able to use both Skype for Business and Teams simultaneously.</span></span>
        - <span data-ttu-id="54054-115">**Только Skype для бизнеса** . Этот параметр используется только в том случае, если вы хотите, чтобы ваши пользователи использовали только Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="54054-115">**Skype for Business only** - Use this setting if you want your users to only use Skype for Business.</span></span>
        - <span data-ttu-id="54054-116">**Только** для Teams (в предварительной версии для некоторых организаций) — Используйте этот параметр, если вы хотите, чтобы пользователи могли использовать только Teams.</span><span class="sxs-lookup"><span data-stu-id="54054-116">**Teams only** (in preview for some organizations) - Use this setting if you want your users to use only Teams.</span></span> <span data-ttu-id="54054-117">Обратите внимание, что даже с этим параметром пользователи по-прежнему могут присоединяться к собраниям в Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="54054-117">Note that even with this setting, users can still join meetings hosted in Skype for Business.</span></span>
    - <span data-ttu-id="54054-118">Установите параметр **уведомлять пользователей Skype для бизнеса, что Teams доступен для обновления**.</span><span class="sxs-lookup"><span data-stu-id="54054-118">Set **Notify Skype for Business users that Teams is available for upgrade**.</span></span> <span data-ttu-id="54054-119">Если включить этот параметр, пользователи Skype для бизнеса смогут получать эти сведения о том, что они вскоре будут обновлены до приложения Teams.</span><span class="sxs-lookup"><span data-stu-id="54054-119">If you turn this on, it will tell the Skype for Business users that they will soon be upgraded to the Teams app.</span></span>
    - <span data-ttu-id="54054-120">Установка **предпочтительного приложения для присоединения к собраниям Skype для бизнеса**.</span><span class="sxs-lookup"><span data-stu-id="54054-120">Set the **Preferred app for users to join Skype for Business meetings**.</span></span> <span data-ttu-id="54054-121">Этот параметр определяет, какое приложение используется для присоединения к собраниям в Skype для бизнеса и учитывается независимо от значения режима сосуществования.</span><span class="sxs-lookup"><span data-stu-id="54054-121">This setting determines which app is used for joining Skype for Business meetings and is honored regardless of the value of coexistence mode.</span></span>
      - <span data-ttu-id="54054-122">**Приложение "собрания Skype"**</span><span class="sxs-lookup"><span data-stu-id="54054-122">**Skype Meetings app**</span></span>
      - <span data-ttu-id="54054-123">**Skype для бизнеса с ограниченными возможностями**</span><span class="sxs-lookup"><span data-stu-id="54054-123">**Skype for Business with limited features**</span></span>
    - <span data-ttu-id="54054-124">Укажите, нужно ли **скачивать приложение Teams в фоновом режиме для пользователей Skype для бизнеса**.</span><span class="sxs-lookup"><span data-stu-id="54054-124">Set whether to **Download the Teams app in the background for Skype for Business users**.</span></span>  <span data-ttu-id="54054-125">Этот параметр автоматически загружает приложение Teams для пользователей, работающих под управлением Skype для бизнеса в Windows.</span><span class="sxs-lookup"><span data-stu-id="54054-125">This setting silently downloads the Teams app for users running Skype for Business on Windows.</span></span> <span data-ttu-id="54054-126">Она обрабатывается только в том случае, если режим сосуществования для пользователя — только Teams или если в Skype для бизнеса включены уведомления о состоянии ожидания обновления.</span><span class="sxs-lookup"><span data-stu-id="54054-126">It is honored only if coexistence mode for the user is Teams only or if notifications of pending upgrade are enabled in Skype for Business.</span></span>
3. <span data-ttu-id="54054-127">После внесения изменений нажмите кнопку **сохранить** .</span><span class="sxs-lookup"><span data-stu-id="54054-127">Click **Save** after you make your changes.</span></span>

## <a name="set-upgrade-options-for-a-single-user-in-your-organization"></a><span data-ttu-id="54054-128">Настройка параметров обновления для отдельного пользователя в Организации</span><span class="sxs-lookup"><span data-stu-id="54054-128">Set upgrade options for a single user in your organization</span></span>

<span data-ttu-id="54054-129">![Значок с логотипом](media/teams-logo-30x30.png) Microsoft Teams, в котором **используется центр администрирования Microsoft Teams**</span><span class="sxs-lookup"><span data-stu-id="54054-129">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="54054-130">На панели навигации слева перейдите в раздел **Пользователи**и выберите пользователя из списка.</span><span class="sxs-lookup"><span data-stu-id="54054-130">In the left navigation, go to **Users**, and then select the user from the list.</span></span> 
2. <span data-ttu-id="54054-131">На вкладке **учетная запись** пользователя в разделе **Обновление Teams**нажмите кнопку **изменить**.</span><span class="sxs-lookup"><span data-stu-id="54054-131">On the **Account** tab for the user, under **Teams upgrade**, click **Edit**.</span></span>
3. <span data-ttu-id="54054-132">Вы можете установить **режим**сосуществования.</span><span class="sxs-lookup"><span data-stu-id="54054-132">You can set the **Coexistence mode**.</span></span> <span data-ttu-id="54054-133">Выберите один из следующих вариантов:</span><span class="sxs-lookup"><span data-stu-id="54054-133">Choose from the following options:</span></span>
     - <span data-ttu-id="54054-134">**Используйте параметры в масштабах Организации** — используйте этот параметр, если вы хотите, чтобы пользователь использовал параметры, указанные в параметрах **уровня Организации** .</span><span class="sxs-lookup"><span data-stu-id="54054-134">**Use Org-wide settings** - Use this setting if you want the user to use the settings in the **Org-wide** settings.</span></span> 
     - <span data-ttu-id="54054-135">**О-ва** – используйте этот параметр, если вы хотите, чтобы пользователь мог использовать Skype для бизнеса и Teams.</span><span class="sxs-lookup"><span data-stu-id="54054-135">**Islands** - Use this setting if you want the user to be able to use both Skype for Business and Teams.</span></span> 
     - <span data-ttu-id="54054-136">**Только для Skype для бизнеса** – этот параметр используется, если вы хотите, чтобы пользователь использовал Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="54054-136">**Skype for Business only** - Use this setting if you want the user to use Skype for Business.</span></span> 
     - <span data-ttu-id="54054-137">**Только** для teams – этот параметр используется, если вы хотите, чтобы пользователь использовал только группы Teams.</span><span class="sxs-lookup"><span data-stu-id="54054-137">**Teams only** - Use this setting if you want the user to use only Teams.</span></span> <span data-ttu-id="54054-138">Пользователь по-прежнему сможет присоединиться к собраниям Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="54054-138">The user will still be able to join Skype for Business meetings.</span></span>
4. <span data-ttu-id="54054-139">Если вы выбрали **режим совместного существования** , отличный от **параметров в масштабе организации**, вы можете включить уведомления в приложении Skype для бизнеса, которое будет вскоре переходить на Teams.</span><span class="sxs-lookup"><span data-stu-id="54054-139">If you select any **Coexistence mode** other than **Use Org-wide settings**, you have the option to enable notifications in the user's Skype for Business app that upgrade to Teams is coming soon.</span></span> <span data-ttu-id="54054-140">Вы можете включить это уведомление для пользователя, включив параметр **уведомлять пользователя Skype для бизнеса** .</span><span class="sxs-lookup"><span data-stu-id="54054-140">You can enable this notification for the user by turning on the **Notify the Skype for Business user** option.</span></span>
5. <span data-ttu-id="54054-141">После внесения изменений нажмите кнопку **сохранить** .</span><span class="sxs-lookup"><span data-stu-id="54054-141">Click **Save** after you make your changes.</span></span>

### <a name="related-topics"></a><span data-ttu-id="54054-142">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="54054-142">Related topics</span></span>
[<span data-ttu-id="54054-143">Планирование поездки</span><span class="sxs-lookup"><span data-stu-id="54054-143">Plan the journey</span></span>](upgrade-plan-journey.md)

[<span data-ttu-id="54054-144">Общие сведения о межсуществовании и обновлении для Skype для бизнеса и рабочих групп</span><span class="sxs-lookup"><span data-stu-id="54054-144">Understand the coexistence and upgrade journey for Skype for Business and Teams</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

[<span data-ttu-id="54054-145">Руководство по миграции и взаимодействию для организаций, использующих Teams вместе со Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="54054-145">Migration and interoperability guidance for organizations using Teams together with Skype for Business</span></span>](migration-interop-guidance-for-teams-with-skype.md)
