---
title: Управление политиками настройки приложений в Microsoft Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: rarang
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Узнайте, как использовать политики настройки приложений и управлять ими в Microsoft Teams для пользователей в организации.
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.appsetuppolicies.overview
ms.openlocfilehash: ebfcff8ce7215e34e3c17e9c09f3a56d249d5b40
ms.sourcegitcommit: 1ee9b1857f472a5b95352f7471c0cf21be6ea0c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/27/2021
ms.locfileid: "52059203"
---
# <a name="manage-app-setup-policies-in-microsoft-teams"></a><span data-ttu-id="1961d-103">Управление политиками настройки приложений в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="1961d-103">Manage app setup policies in Microsoft Teams</span></span>

<span data-ttu-id="1961d-104">Администратор может использовать политики настройки приложений для выполнения следующих задач:</span><span class="sxs-lookup"><span data-stu-id="1961d-104">As an admin, you can use app setup policies to do the following tasks:</span></span>

- <span data-ttu-id="1961d-105">Настройте Teams, чтобы выделить приложения, которые наиболее важны для ваших пользователей.</span><span class="sxs-lookup"><span data-stu-id="1961d-105">Customize Teams to highlight the apps that are most important for your users.</span></span> <span data-ttu-id="1961d-106">Вы можете выбрать приложения для закрепления и настроить порядок их появления.</span><span class="sxs-lookup"><span data-stu-id="1961d-106">You choose the apps to pin and set the order that they appear.</span></span> <span data-ttu-id="1961d-107">Закрепление приложений позволяет демонстрировать приложения, которые нужны пользователям в организации, в том числе приложения, встроенные сторонними разработчиками или разработчиками.</span><span class="sxs-lookup"><span data-stu-id="1961d-107">Pinning apps lets you showcase apps that users in your organization need, including apps built by third parties or by developers in your organization.</span></span>
- <span data-ttu-id="1961d-108">Контроль, могут ли пользователи прикреплять приложения к Teams.</span><span class="sxs-lookup"><span data-stu-id="1961d-108">Control whether users can pin apps to Teams.</span></span>
- <span data-ttu-id="1961d-109">Установка приложений от имени пользователей.</span><span class="sxs-lookup"><span data-stu-id="1961d-109">Install apps on behalf of users.</span></span> <span data-ttu-id="1961d-110">Вы выбираете приложения, установленные по умолчанию для пользователей при запуске Teams.</span><span class="sxs-lookup"><span data-stu-id="1961d-110">You choose which apps are installed by default for users when they start Teams.</span></span> <span data-ttu-id="1961d-111">Имейте в виду, что пользователи по-прежнему могут устанавливать приложения самостоятельно, если это разрешает назначенная им политика разрешений. [](teams-app-permission-policies.md)</span><span class="sxs-lookup"><span data-stu-id="1961d-111">Keep in mind that users can still install apps themselves if the [app permission policy](teams-app-permission-policies.md) that's assigned to them allows it.</span></span>

> [!Note]
> <span data-ttu-id="1961d-112">Для приложений, установленных администраторами, пользователи не могут удалить их.</span><span class="sxs-lookup"><span data-stu-id="1961d-112">For apps installed by admins, users can't uninstall those apps.</span></span>

<span data-ttu-id="1961d-113">Приложения закреплены на панели приложений сбоку от Teams и в нижней части мобильных клиентов Teams (iOS и Android).</span><span class="sxs-lookup"><span data-stu-id="1961d-113">Apps are pinned to the app bar, which is the bar on the side of the Teams desktop client and at the bottom of the Teams mobile clients (iOS and Android).</span></span>

|<span data-ttu-id="1961d-114">Teams для настольных ПК</span><span class="sxs-lookup"><span data-stu-id="1961d-114">Teams desktop client</span></span>  |<span data-ttu-id="1961d-115">Мобильный клиент Teams</span><span class="sxs-lookup"><span data-stu-id="1961d-115">Teams mobile client</span></span> |
|---------|---------|
|![Клиент Teams для настольных ПК](media/app-setup-policies-desktop-app-bar.png)<br>  |   ![Мобильный Teams](media/mobile-app-ui.png)      |

<span data-ttu-id="1961d-118">Чтобы увидеть приложения, установленные администраторами, на панели приложений выберите **... Другие приложения** в Teams и веб-клиентах и проведите пальцем вверх по мобильным клиентам.</span><span class="sxs-lookup"><span data-stu-id="1961d-118">To see the apps installed by admins, in the app bar, users select **... More apps** in the Teams desktop and web clients and swipe up in the mobile clients.</span></span>

<span data-ttu-id="1961d-119">Вы управляете политиками настройки приложений в Microsoft Teams администрирования.</span><span class="sxs-lookup"><span data-stu-id="1961d-119">You manage app setup policies in the Microsoft Teams admin center.</span></span> <span data-ttu-id="1961d-120">Используйте глобальную политику (стандартную для всей организации) или создайте и назначьте настраиваемые политики.</span><span class="sxs-lookup"><span data-stu-id="1961d-120">Use the global (Org-wide default) policy or create and assign custom policies.</span></span>  <span data-ttu-id="1961d-121">Если вы не создадите и не назначите настраиваемую политику, пользователи в вашей организации автоматически получат глобальную политику.</span><span class="sxs-lookup"><span data-stu-id="1961d-121">Users in your organization will automatically get the global policy unless you create and assign a custom policy.</span></span> <span data-ttu-id="1961d-122">Вы должны быть глобальным администратором или администратором службы Teams, чтобы управлять этими политиками.</span><span class="sxs-lookup"><span data-stu-id="1961d-122">You must be a global admin or Teams service admin to manage these policies.</span></span>

<span data-ttu-id="1961d-123">Вы можете изменить параметры глобальной политики, чтобы включить в нее нужные приложения.</span><span class="sxs-lookup"><span data-stu-id="1961d-123">You edit the settings in the global policy to include the apps that you want.</span></span> <span data-ttu-id="1961d-124">Чтобы настроить Teams для разных групп пользователей в организации, создайте и назначьте одну или несколько настраиваемых политик.</span><span class="sxs-lookup"><span data-stu-id="1961d-124">To customize Teams for different groups of users in your organization, create and assign one or more custom policies.</span></span>

![Страница политик настройки приложений](media/app-setup-policies.png)

> [!NOTE]
> <span data-ttu-id="1961d-126">Если вы Teams для образования, важно знать, что приложение "Задания" по умолчанию закреплено в глобальной политике, хотя в настоящее время оно не указано в глобальной политике.</span><span class="sxs-lookup"><span data-stu-id="1961d-126">If you have Teams for Education, it's important to know that the Assignments app is pinned by default in the global policy even though currently, you don't see it listed in the global policy.</span></span> <span data-ttu-id="1961d-127">Это будет четвертое приложение в списке закрепленных приложений в Teams клиентах.</span><span class="sxs-lookup"><span data-stu-id="1961d-127">It will be the fourth app in the list of pinned apps on Teams clients.</span></span>

## <a name="create-a-custom-app-setup-policy"></a><span data-ttu-id="1961d-128">Создание настраиваемой политики настройки приложений</span><span class="sxs-lookup"><span data-stu-id="1961d-128">Create a custom app setup policy</span></span>

<span data-ttu-id="1961d-129">Для создания настраиваемой политики Microsoft Teams центр администрирования.</span><span class="sxs-lookup"><span data-stu-id="1961d-129">You can use the Microsoft Teams admin center to create a custom policy.</span></span>

1. <span data-ttu-id="1961d-130">В левой области навигации Центра администрирования Microsoft Teams перейдите в Teams **политики установки** приложений  >  .</span><span class="sxs-lookup"><span data-stu-id="1961d-130">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Setup policies**.</span></span>

2. <span data-ttu-id="1961d-131">Нажмите **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="1961d-131">Select **Add**.</span></span>

   ![Страница "Добавление политик настройки приложений"](media/app-setup-policies-add.png)

3. <span data-ttu-id="1961d-133">Введите имя и описание для политики.</span><span class="sxs-lookup"><span data-stu-id="1961d-133">Enter a name and description for the policy.</span></span>

4. <span data-ttu-id="1961d-134">Включите или **отключите Upload** настраиваемые приложения в зависимости от того, хотите ли вы разрешать пользователям загружать пользовательские приложения в Teams.</span><span class="sxs-lookup"><span data-stu-id="1961d-134">Turn on or turn off **Upload custom apps**, depending on whether you want to let users upload custom apps to Teams.</span></span> <span data-ttu-id="1961d-135">Этот параметр нельзя изменить,  если в настройках приложений для всей организации отключен параметр Разрешить приложения [сторонних разработчиков.](manage-apps.md#manage-org-wide-app-settings)</span><span class="sxs-lookup"><span data-stu-id="1961d-135">You can't change this setting if **Allow third-party apps** is turned off in [org-wide app settings](manage-apps.md#manage-org-wide-app-settings).</span></span>

5. <span data-ttu-id="1961d-136">Включите или отключите разрешение закрепления для пользователей **в** зависимости от того, хотите ли вы позволить пользователям персонализировать свои панели приложений, прикрепив приложения к ней.</span><span class="sxs-lookup"><span data-stu-id="1961d-136">Turn on or turn off **Allow user pinning**, depending on whether you want to let users personalize their app bar by pinning apps to it.</span></span>

   > [!NOTE]
   > <span data-ttu-id="1961d-137">Параметр **Разрешить** закрепление пользователей доступен в Центре администрирования Teams в Microsoft 365 облако сообщества для государственных организаций (GCC) (GCC, GCC High и DoD), но в настоящее время он не действует.</span><span class="sxs-lookup"><span data-stu-id="1961d-137">The **Allow user pinning** setting is available in the Teams admin center in Microsoft 365 Government Community Cloud (GCC) environments (GCC, GCC High and DoD), but currently it has no effect.</span></span>

6. <span data-ttu-id="1961d-138">Чтобы установить приложения для пользователей, сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="1961d-138">To install apps for users, do the following tasks:</span></span>

    1. <span data-ttu-id="1961d-139">В **области Установленные приложения** выберите Добавить **приложения**.</span><span class="sxs-lookup"><span data-stu-id="1961d-139">Under **Installed apps**, select **Add apps**.</span></span>

    2. <span data-ttu-id="1961d-140">В области **Добавить установленные** приложения найщите приложения, которые вы хотите автоматически установить для пользователей при запуске Teams.</span><span class="sxs-lookup"><span data-stu-id="1961d-140">In the **Add installed apps** pane, search for the apps you want to automatically install for users when they start Teams.</span></span> <span data-ttu-id="1961d-141">Вы также можете фильтровать приложения с помощью политики разрешений приложений.</span><span class="sxs-lookup"><span data-stu-id="1961d-141">You can also filter apps by app permission policy.</span></span> <span data-ttu-id="1961d-142">Выбрав список приложений, выберите **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="1961d-142">When you've chosen your list of apps, select **Add**.</span></span>

       ![The Add installed apps pane](media/app-setup-policies-add-installed-apps.png)

7. <span data-ttu-id="1961d-144">Чтобы закрепить приложения, сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="1961d-144">To pin apps, do the following steps:</span></span>

    1. <span data-ttu-id="1961d-145">В **области Закрепленные приложения** выберите Добавить **приложения**.</span><span class="sxs-lookup"><span data-stu-id="1961d-145">Under **Pinned apps**, select **Add apps**.</span></span>

    2. <span data-ttu-id="1961d-146">В области **Добавление закрепленных приложений** найди приложения, которые вы хотите добавить, и выберите **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="1961d-146">In the **Add pinned apps** pane, search for the apps you want to add, and then select **Add**.</span></span> <span data-ttu-id="1961d-147">Вы также можете фильтровать приложения с помощью политики разрешений приложений.</span><span class="sxs-lookup"><span data-stu-id="1961d-147">You can also filter apps by app permission policy.</span></span> <span data-ttu-id="1961d-148">Выбрав список приложений для закрепления, выберите **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="1961d-148">When you've chosen your list of apps to pin, select **Add**.</span></span>

       ![The Add pinned apps pane](media/app-setup-policies-add-apps.png)

    3. <span data-ttu-id="1961d-150">Расположить приложения в том порядке, в который они должны отображаться в Teams, а затем выберите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="1961d-150">Arrange the apps in the order that you want them to appear in Teams, and then select **Save**.</span></span>

       ![Раздел закрепленных приложений](media/app-setup-policies-new-policy-setup.png)

## <a name="edit-an-app-setup-policy"></a><span data-ttu-id="1961d-152">Изменение политики настройки приложения</span><span class="sxs-lookup"><span data-stu-id="1961d-152">Edit an app setup policy</span></span>

<span data-ttu-id="1961d-153">Центр администрирования Microsoft Teams для изменения политики, в том числе глобальной (по умолчанию в организации) и настраиваемой политики, которые вы создаете.</span><span class="sxs-lookup"><span data-stu-id="1961d-153">You can use the Microsoft Teams admin center to edit a policy, including the global (Org-wide default) policy and custom policies that you create.</span></span>

1. <span data-ttu-id="1961d-154">В левой области навигации Центра администрирования Microsoft Teams перейдите в Teams **политики установки** приложений  >  .</span><span class="sxs-lookup"><span data-stu-id="1961d-154">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Setup policies**.</span></span>

2. <span data-ttu-id="1961d-155">Выберите политику, щелкнув слева от ее имени, и нажмите **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="1961d-155">Select the policy by clicking to the left of the policy name, and then select **Edit**.</span></span>

3. <span data-ttu-id="1961d-156">Внесите необходимые изменения.</span><span class="sxs-lookup"><span data-stu-id="1961d-156">From here, make the changes that you want.</span></span>

4. <span data-ttu-id="1961d-157">Нажмите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="1961d-157">Select **Save**.</span></span>

## <a name="assign-a-custom-app-setup-policy-to-users"></a><span data-ttu-id="1961d-158">Назначение настраиваемой политики настройки приложений пользователям</span><span class="sxs-lookup"><span data-stu-id="1961d-158">Assign a custom app setup policy to users</span></span>

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="faq"></a><span data-ttu-id="1961d-159">Вопросы и ответы</span><span class="sxs-lookup"><span data-stu-id="1961d-159">FAQ</span></span>

### <a name="working-with-app-setup-policies"></a><span data-ttu-id="1961d-160">Работа с политиками настройки приложений</span><span class="sxs-lookup"><span data-stu-id="1961d-160">Working with app setup policies</span></span>

#### <a name="what-built-in-app-setup-policies-are-included-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="1961d-161">Встроенные политики настройки приложений, включенные в центр администрирования Microsoft Teams приложений</span><span class="sxs-lookup"><span data-stu-id="1961d-161">What built-in app setup policies are included in the Microsoft Teams admin center</span></span>

- <span data-ttu-id="1961d-162">**Глобальный (по** умолчанию в организации): эта политика по умолчанию применяется ко всем пользователям в организации, если только вы не назначите другую политику.</span><span class="sxs-lookup"><span data-stu-id="1961d-162">**Global (Org-wide default)**: This default policy applies to all users in your organization unless you assign another policy.</span></span> <span data-ttu-id="1961d-163">Изменение глобальной политики для закрепления приложений, наиболее важных для пользователей.</span><span class="sxs-lookup"><span data-stu-id="1961d-163">Edit the global policy to pin apps that are most important for your users.</span></span>

- <span data-ttu-id="1961d-164">**FrontlineWorker:** эта политика для сотрудников с frontline.</span><span class="sxs-lookup"><span data-stu-id="1961d-164">**FrontlineWorker**: This policy is for Frontline Workers.</span></span> <span data-ttu-id="1961d-165">Вы можете назначить его сотрудникам, работающим с телефоном в организации.</span><span class="sxs-lookup"><span data-stu-id="1961d-165">You can assign it to Frontline Workers in your organization.</span></span> <span data-ttu-id="1961d-166">Важно знать, что, как и настраиваемые политики, которые вы создаете, необходимо назначить политику пользователям, чтобы параметры были активными.</span><span class="sxs-lookup"><span data-stu-id="1961d-166">It's important to know that like custom policies that you create, you have to assign the policy to users for the settings to be active.</span></span> <span data-ttu-id="1961d-167">Дополнительные сведения можно найти в разделе [Назначение](#assign-a-custom-app-setup-policy-to-users) настраиваемой политики настройки приложений пользователям этой статьи.</span><span class="sxs-lookup"><span data-stu-id="1961d-167">For more information, go to the [Assign a custom app setup policy to users](#assign-a-custom-app-setup-policy-to-users) section of this article.</span></span>

#### <a name="why-cant-i-find-an-app-in-the-add-pinned-apps-pane"></a><span data-ttu-id="1961d-168">Почему не могу найти приложение в области "Добавить закрепленные приложения"</span><span class="sxs-lookup"><span data-stu-id="1961d-168">Why can't I find an app in the Add pinned apps pane</span></span>

<span data-ttu-id="1961d-169">Не все приложения можно закрепить на Teams с помощью политики настройки приложений.</span><span class="sxs-lookup"><span data-stu-id="1961d-169">Not all apps can be pinned to Teams through an app setup policy.</span></span> <span data-ttu-id="1961d-170">Некоторые приложения могут не поддерживать эту функцию.</span><span class="sxs-lookup"><span data-stu-id="1961d-170">Some apps may not support this functionality.</span></span> <span data-ttu-id="1961d-171">Чтобы найти приложения, которые можно закрепить, найдите их в области Добавление **закрепленных** приложений.</span><span class="sxs-lookup"><span data-stu-id="1961d-171">To find apps that can be pinned, search for the app in the **Add pinned apps** pane.</span></span> <span data-ttu-id="1961d-172">Вкладки с личной областью (статическими вкладками) и ботами можно закрепить в клиенте Teams для настольных пк, и эти приложения доступны в области Добавление **закрепленных** приложений.</span><span class="sxs-lookup"><span data-stu-id="1961d-172">Tabs that have a personal scope (static tabs) and bots can be pinned to the Teams desktop client and these apps are available in the **Add pinned apps** pane.</span></span>

<span data-ttu-id="1961d-173">Помните, что в Teams приложений перечислены все Teams приложения.</span><span class="sxs-lookup"><span data-stu-id="1961d-173">Keep in mind that the Teams app store lists all Teams apps.</span></span> <span data-ttu-id="1961d-174">В **области Добавить закрепленные** приложения доступны только приложения, которые можно Teams с помощью политики.</span><span class="sxs-lookup"><span data-stu-id="1961d-174">The **Add pinned apps** pane includes only apps that can be pinned to Teams through a policy.</span></span>

#### <a name="im-a-teams-for-education-admin-what-do-i-need-to-know-about-app-setup-policies-in-teams-for-education"></a><span data-ttu-id="1961d-175">Я администратор Teams образования. Что нужно знать о политиках настройки приложений в Teams для образования</span><span class="sxs-lookup"><span data-stu-id="1961d-175">I'm a Teams for Education admin. What do I need to know about app setup policies in Teams for Education</span></span>

<span data-ttu-id="1961d-176">Приложение "Вызовы" не доступно в Teams для образовательных звонков.</span><span class="sxs-lookup"><span data-stu-id="1961d-176">The Calling app isn't available in Teams for Education.</span></span> <span data-ttu-id="1961d-177">При создании новой настраиваемой политики настройки приложения приложение "Вызовы" отображается в списке приложений.</span><span class="sxs-lookup"><span data-stu-id="1961d-177">When you create a new custom app setup policy, the Calling app is displayed in the list of apps.</span></span> <span data-ttu-id="1961d-178">Однако приложение не закреплено в Teams и Teams для образовательных Teams.</span><span class="sxs-lookup"><span data-stu-id="1961d-178">However, the app isn't pinned to Teams clients and Teams for Education users won't see the Calls app in Teams.</span></span>

#### <a name="how-many-pinned-apps-can-be-added-to-a-policy"></a><span data-ttu-id="1961d-179">Количество закрепленных приложений, которые можно добавить в политику</span><span class="sxs-lookup"><span data-stu-id="1961d-179">How many pinned apps can be added to a policy</span></span>

<span data-ttu-id="1961d-180">В мобильных клиентах Teams (iOS и Android) должно быть закреплено как минимум два приложения.</span><span class="sxs-lookup"><span data-stu-id="1961d-180">A minimum of two apps must be pinned to the Teams mobile clients (iOS and Android).</span></span> <span data-ttu-id="1961d-181">Если в политике менее двух приложений, мобильные клиенты не будут отражать ее параметры и будут продолжать использовать существующую конфигурацию.</span><span class="sxs-lookup"><span data-stu-id="1961d-181">If a policy has fewer than two apps, the mobile clients won't reflect the policy settings and instead will continue to use the existing configuration.</span></span>

<span data-ttu-id="1961d-182">Количество закрепленных приложений, которые можно добавить в политику, не ограничивается.</span><span class="sxs-lookup"><span data-stu-id="1961d-182">There's no limit on the number of pinned apps you can add to a policy.</span></span>

#### <a name="how-long-does-it-take-for-policy-changes-to-take-effect"></a><span data-ttu-id="1961d-183">Сколько времени займет внесение изменений в политику</span><span class="sxs-lookup"><span data-stu-id="1961d-183">How long does it take for policy changes to take effect</span></span>

<span data-ttu-id="1961d-184">После изменения или назначения политики изменения вступят в силу в течение нескольких часов.</span><span class="sxs-lookup"><span data-stu-id="1961d-184">After you edit or assign a policy, it can take a few hours for changes to take effect.</span></span>

### <a name="user-experience"></a><span data-ttu-id="1961d-185">Впечатления от использования</span><span class="sxs-lookup"><span data-stu-id="1961d-185">User experience</span></span>

#### <a name="how-can-users-see-all-their-pinned-apps-in-teams"></a><span data-ttu-id="1961d-186">Как пользователи могут видеть все закрепленные приложения в Teams</span><span class="sxs-lookup"><span data-stu-id="1961d-186">How can users see all their pinned apps in Teams</span></span>

<span data-ttu-id="1961d-187">Чтобы просмотреть все приложения, закрепленные для пользователя, пользователям может потребоваться сделать следующее в зависимости от количества установленных приложений и размера окна Teams клиента.</span><span class="sxs-lookup"><span data-stu-id="1961d-187">To view all apps that are pinned for a user, users might have to do the following depending on the number of installed apps and the size of their Teams client window.</span></span>

|<span data-ttu-id="1961d-188">Teams для настольных ПК</span><span class="sxs-lookup"><span data-stu-id="1961d-188">Teams desktop client</span></span> |<span data-ttu-id="1961d-189">Мобильный клиент Teams</span><span class="sxs-lookup"><span data-stu-id="1961d-189">Teams mobile client</span></span> |
|---------|---------|
|<span data-ttu-id="1961d-190">На панели приложения сбоку Teams выберите **... Другие приложения**.</span><span class="sxs-lookup"><span data-stu-id="1961d-190">In the app bar on the side of Teams, select **... More apps**.</span></span>| <span data-ttu-id="1961d-191">На панели приложения в нижней части Teams проведите пальцем вверх.</span><span class="sxs-lookup"><span data-stu-id="1961d-191">In the app bar near the bottom of Teams, swipe up.</span></span>|
|![Другие приложения в клиенте Teams для настольных ПК](media/app-setup-policies-desktop-more-apps.png)<br>   |![другие приложения в Teams мобильном клиенте](media/app-setup-policies-mobile-more-apps.png)  

#### <a name="what-do-i-need-to-know-about-the-teams-mobile-experience"></a><span data-ttu-id="1961d-194">Что нужно знать о Teams мобильном устройстве</span><span class="sxs-lookup"><span data-stu-id="1961d-194">What do I need to know about the Teams mobile experience</span></span>

<span data-ttu-id="1961d-195">Мобильные Teams (iOS и Android) поддерживают личные приложения со статическими вкладками.</span><span class="sxs-lookup"><span data-stu-id="1961d-195">The Teams mobile clients (iOS and Android) support personal apps with static tabs.</span></span> <span data-ttu-id="1961d-196">Приложения, закрепленные на Teams, будут отображаться в Teams мобильных клиентах.</span><span class="sxs-lookup"><span data-stu-id="1961d-196">Apps pinned to the Teams desktop client will appear in the Teams mobile clients.</span></span> <span data-ttu-id="1961d-197">Личные боты будут отображаться в чате в мобильных клиентах.</span><span class="sxs-lookup"><span data-stu-id="1961d-197">Personal bots will appear in Chat on mobile clients.</span></span>

<span data-ttu-id="1961d-198">Сторонние приложения (которые можно скачать из Teams Store) должны быть утверждены, прежде чем они будут доступны на мобильном устройстве.</span><span class="sxs-lookup"><span data-stu-id="1961d-198">Third-party apps (which can be downloaded from Teams Store) need to be approved before they show up on mobile.</span></span> <span data-ttu-id="1961d-199">Если администратор закрепит приложение, которое не используется корпорацией Майкрософт для мобильных устройств, оно будет Teams на рабочем столе, но не на мобильном устройстве.</span><span class="sxs-lookup"><span data-stu-id="1961d-199">If an admin pins an app, which is unapproved by Microsoft for Mobile, it will show up on the Teams Desktop, but not show up on mobile.</span></span> <span data-ttu-id="1961d-200">Дополнительные [сведения см. в](/microsoftteams/platform/tabs/what-are-tabs#mobile-clients) мобильных клиентах.</span><span class="sxs-lookup"><span data-stu-id="1961d-200">See [Mobile clients](/microsoftteams/platform/tabs/what-are-tabs#mobile-clients) for more information.</span></span>

<span data-ttu-id="1961d-201">В мобильных клиентах Teams пользователи будут видеть основные Teams, такие как действия, чат и Teams, и вы можете закрепить некоторые приложения от Майкрософт, например Shifts.</span><span class="sxs-lookup"><span data-stu-id="1961d-201">With the Teams mobile clients, users will see core Teams apps such as Activity, Chat, and Teams, and you can pin some first-party apps from Microsoft, such as Shifts.</span></span>

#### <a name="can-users-change-the-order-of-apps-pinned-through-a-policy"></a><span data-ttu-id="1961d-202">Могут ли пользователи изменять порядок приложений, закрепленных с помощью политики</span><span class="sxs-lookup"><span data-stu-id="1961d-202">Can users change the order of apps pinned through a policy</span></span>

<span data-ttu-id="1961d-203">Пользователи могут изменять порядок закрепленных приложений на Teams и  мобильных клиентах, если включен параметр Разрешить закрепление пользователей.</span><span class="sxs-lookup"><span data-stu-id="1961d-203">Users can change the order of their pinned apps on Teams desktop and mobile clients if the **Allow user pinning** option is turned on.</span></span> <span data-ttu-id="1961d-204">Пользователи не могут изменить порядок закрепленных приложений в Teams клиентах.</span><span class="sxs-lookup"><span data-stu-id="1961d-204">Users can't change the order of their pinned apps on Teams web clients.</span></span>

#### <a name="does-user-pinning-take-precedence"></a><span data-ttu-id="1961d-205">Имеет ли приоритет закрепление пользователей</span><span class="sxs-lookup"><span data-stu-id="1961d-205">Does user pinning take precedence</span></span>

<span data-ttu-id="1961d-206">Пин-коды администраторов всегда имеют приоритет.</span><span class="sxs-lookup"><span data-stu-id="1961d-206">Admin pins always take precedence.</span></span> <span data-ttu-id="1961d-207">Если параметр **Разрешить закрепление** пользователей включен, то пользователи будут хранить закрепленные приложения под закрепленным администратором приложениями.</span><span class="sxs-lookup"><span data-stu-id="1961d-207">If the **Allow user pinning** option is turned on, then users will retain their pinned apps below admin pinned apps.</span></span> <span data-ttu-id="1961d-208">Если параметр **Разрешить** закрепление пользователей отключен, пользователи потеряют свои пин-коды, а на панели приложений будут доступны только приложения, закрепленные администратором.</span><span class="sxs-lookup"><span data-stu-id="1961d-208">If the **Allow user pinning** option is turned off, then users will lose their pre-existing pins, and only admin-pinned apps will be present in the app bar.</span></span>

### <a name="custom-teams-apps"></a><span data-ttu-id="1961d-209">Пользовательские Teams приложения</span><span class="sxs-lookup"><span data-stu-id="1961d-209">Custom Teams apps</span></span>

<span data-ttu-id="1961d-210">Моя организация создало пользовательское приложение Teams и опубликовало его в AppSource или каталоге приложений клиента, но значок приложения не отображается, как ожидалось, когда приложение закреплено на панели приложения в Teams.</span><span class="sxs-lookup"><span data-stu-id="1961d-210">My organization built a custom Teams app and published it, either to AppSource or the tenant app catalog, but the app icon isn't displayed as expected when the app is pinned to the app bar in Teams.</span></span> <span data-ttu-id="1961d-211">Как это исправить</span><span class="sxs-lookup"><span data-stu-id="1961d-211">How do I fix it</span></span>

<span data-ttu-id="1961d-212">Перед отправкой приложения следуйте инструкциям по логотипу.</span><span class="sxs-lookup"><span data-stu-id="1961d-212">Make sure that you follow the logo guidelines before you submit the app.</span></span> <span data-ttu-id="1961d-213">Дополнительные данные см. в списке [отправки панели мониторинга продавца.](/microsoftteams/platform/concepts/deploy-and-publish/appsource/prepare/overview)</span><span class="sxs-lookup"><span data-stu-id="1961d-213">To learn more, see [Checklist for Seller Dashboard submission](/microsoftteams/platform/concepts/deploy-and-publish/appsource/prepare/overview).</span></span>

## <a name="related-topics"></a><span data-ttu-id="1961d-214">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="1961d-214">Related topics</span></span>

[<span data-ttu-id="1961d-215">Параметры администратора для приложений в Teams</span><span class="sxs-lookup"><span data-stu-id="1961d-215">Admin settings for apps in Teams</span></span>](admin-settings.md)

[<span data-ttu-id="1961d-216">Назначение политик пользователям в Teams</span><span class="sxs-lookup"><span data-stu-id="1961d-216">Assign policies to your users in Teams</span></span>](assign-policies.md)
