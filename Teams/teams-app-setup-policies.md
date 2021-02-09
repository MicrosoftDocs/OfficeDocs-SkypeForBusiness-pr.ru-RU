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
ms.openlocfilehash: ffc2f15cdbef49daf36e09ca9676925ebb1ac99e
ms.sourcegitcommit: 27bfa015413bc7742bca4ea227e0324da0c740d7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/08/2021
ms.locfileid: "50145926"
---
# <a name="manage-app-setup-policies-in-microsoft-teams"></a><span data-ttu-id="e70ce-103">Управление политиками настройки приложений в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="e70ce-103">Manage app setup policies in Microsoft Teams</span></span>

<span data-ttu-id="e70ce-104">Администраторы могут использовать политики настройки приложений для выполнения следующих задач:</span><span class="sxs-lookup"><span data-stu-id="e70ce-104">As an admin, you can use app setup policies to do the following tasks:</span></span>

- <span data-ttu-id="e70ce-105">Настройте Teams, чтобы выделить приложения, которые наиболее важны для ваших пользователей.</span><span class="sxs-lookup"><span data-stu-id="e70ce-105">Customize Teams to highlight the apps that are most important for your users.</span></span> <span data-ttu-id="e70ce-106">Вы выбираете приложения, которые нужно закрепить, и выбираете порядок их появления.</span><span class="sxs-lookup"><span data-stu-id="e70ce-106">You choose the apps to pin and set the order that they appear.</span></span> <span data-ttu-id="e70ce-107">Закрепление приложений позволяет демонстрировать приложения, которые нужны пользователям в организации, в том числе приложения, построенные сторонними разработчиками или разработчиками.</span><span class="sxs-lookup"><span data-stu-id="e70ce-107">Pinning apps lets you showcase apps that users in your organization need, including apps built by third parties or by developers in your organization.</span></span>
- <span data-ttu-id="e70ce-108">Контроль, могут ли пользователи прикреплять приложения к Teams.</span><span class="sxs-lookup"><span data-stu-id="e70ce-108">Control whether users can pin apps to Teams.</span></span>
- <span data-ttu-id="e70ce-109">Установка приложений от имени пользователей **(в предварительной версии).**</span><span class="sxs-lookup"><span data-stu-id="e70ce-109">Install apps on behalf of users **(in preview)**.</span></span> <span data-ttu-id="e70ce-110">Вы выбираете, какие приложения устанавливаются по умолчанию пользователям при запуске Teams.</span><span class="sxs-lookup"><span data-stu-id="e70ce-110">You choose which apps are installed by default for users when they start Teams.</span></span> <span data-ttu-id="e70ce-111">Помните, что пользователи могут сами устанавливать [](teams-app-permission-policies.md) приложения, если это допускает назначенная им политика разрешений.</span><span class="sxs-lookup"><span data-stu-id="e70ce-111">Keep in mind that users can still install apps themselves if the [app permission policy](teams-app-permission-policies.md) that's assigned to them allows it.</span></span>

<span data-ttu-id="e70ce-112">Приложения закреплены на панели приложений, которая находится сбоку от клиента Teams для настольных ПК и в нижней части мобильных клиентов Teams (iOS и Android).</span><span class="sxs-lookup"><span data-stu-id="e70ce-112">Apps are pinned to the app bar, which is the bar on the side of the Teams desktop client and at the bottom of the Teams mobile clients (iOS and Android).</span></span>

|<span data-ttu-id="e70ce-113">Клиент Teams для настольных ПК</span><span class="sxs-lookup"><span data-stu-id="e70ce-113">Teams desktop client</span></span>  |<span data-ttu-id="e70ce-114">Мобильный клиент Teams</span><span class="sxs-lookup"><span data-stu-id="e70ce-114">Teams mobile client</span></span> |
|---------|---------|
|![Клиент Teams для настольных ПК](media/app-setup-policies-desktop-app-bar.png)<br>  |   ![Мобильный клиент Teams](media/mobile-app-ui.png)      |

<span data-ttu-id="e70ce-117">Чтобы увидеть предварительно установленные приложения, на панели приложений **выберите... Другие приложения в** классических и веб-клиентах Teams и проведение пальцем вверх в мобильных клиентах.</span><span class="sxs-lookup"><span data-stu-id="e70ce-117">To see their pre-installed apps, in the app bar, users select **... More apps** in the Teams desktop and web clients and swipe up in the mobile clients.</span></span>

<span data-ttu-id="e70ce-118">Вы управляете политиками настройки приложений в Центре администрирования Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="e70ce-118">You manage app setup policies in the Microsoft Teams admin center.</span></span> <span data-ttu-id="e70ce-119">Используйте глобальную (по умолчанию в организации) политику или создайте и назначьте настраиваемые политики.</span><span class="sxs-lookup"><span data-stu-id="e70ce-119">Use the global (Org-wide default) policy or create and assign custom policies.</span></span>  <span data-ttu-id="e70ce-120">Пользователи вашей организации автоматически получают глобальную политику, если вы не создали и не назначили настраиваемую политику.</span><span class="sxs-lookup"><span data-stu-id="e70ce-120">Users in your organization will automatically get the global policy unless you create and assign a custom policy.</span></span> <span data-ttu-id="e70ce-121">Вы должны быть глобальным администратором или администратором службы Teams, чтобы управлять этими политиками.</span><span class="sxs-lookup"><span data-stu-id="e70ce-121">You must be a global admin or Teams service admin to manage these policies.</span></span>

<span data-ttu-id="e70ce-122">Вы можете изменить параметры в глобальной политике, чтобы включить в нее нужные приложения.</span><span class="sxs-lookup"><span data-stu-id="e70ce-122">You edit the settings in the global policy to include the apps that you want.</span></span> <span data-ttu-id="e70ce-123">Чтобы настроить Teams для разных групп пользователей в организации, создайте и назначьте одну или несколько настраиваемых политик.</span><span class="sxs-lookup"><span data-stu-id="e70ce-123">To customize Teams for different groups of users in your organization, create and assign one or more custom policies.</span></span>

![Страница политик настройки приложений](media/app-setup-policies.png)

> [!NOTE]
> <span data-ttu-id="e70ce-125">Если у вас есть Teams для образовательных образования, важно знать, что приложение "Задания" по умолчанию закреплено в глобальной политике, хотя в настоящее время оно не указано в глобальной политике.</span><span class="sxs-lookup"><span data-stu-id="e70ce-125">If you have Teams for Education, it's important to know that the Assignments app is pinned by default in the global policy even though currently, you don't see it listed in the global policy.</span></span> <span data-ttu-id="e70ce-126">Это будет четвертое приложение в списке закрепленных приложений в клиентах Teams.</span><span class="sxs-lookup"><span data-stu-id="e70ce-126">It will be the fourth app in the list of pinned apps on Teams clients.</span></span>

## <a name="create-a-custom-app-setup-policy"></a><span data-ttu-id="e70ce-127">Создание настраиваемой политики настройки приложений</span><span class="sxs-lookup"><span data-stu-id="e70ce-127">Create a custom app setup policy</span></span>

<span data-ttu-id="e70ce-128">Для создания настраиваемой политики можно использовать Центр администрирования Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="e70ce-128">You can use the Microsoft Teams admin center to create a custom policy.</span></span>

1. <span data-ttu-id="e70ce-129">В левой области навигации Центра администрирования Microsoft Teams перейдите к политикам настройки приложений **Teams.**  >  </span><span class="sxs-lookup"><span data-stu-id="e70ce-129">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Setup policies**.</span></span>

2. <span data-ttu-id="e70ce-130">Нажмите **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="e70ce-130">Select **Add**.</span></span>

   ![Страница добавления политик настройки приложений](media/app-setup-policies-add.png)
    
3. <span data-ttu-id="e70ce-132">Введите имя и описание для политики.</span><span class="sxs-lookup"><span data-stu-id="e70ce-132">Enter a name and description for the policy.</span></span>

4. <span data-ttu-id="e70ce-133">Включите или отключите **отправку** пользовательских приложений в зависимости от того, хотите ли вы разрешать пользователям загружать пользовательские приложения в Teams.</span><span class="sxs-lookup"><span data-stu-id="e70ce-133">Turn on or turn off **Upload custom apps**, depending on whether you want to let users upload custom apps to Teams.</span></span> <span data-ttu-id="e70ce-134">Этот параметр нельзя изменить,  если в параметрах приложения для всей организации отключен параметр "Разрешить приложения [сторонних разработчиков".](manage-apps.md#manage-org-wide-app-settings)</span><span class="sxs-lookup"><span data-stu-id="e70ce-134">You can't change this setting if **Allow third-party apps** is turned off in [org-wide app settings](manage-apps.md#manage-org-wide-app-settings).</span></span>

5. <span data-ttu-id="e70ce-135">Включите или отключите "Разрешить закрепление" (в зависимости от того, хотите ли вы позволить пользователям персонализировать свою панели приложений, прикрепив приложения к ней).</span><span class="sxs-lookup"><span data-stu-id="e70ce-135">Turn on or turn off **Allow user pinning**, depending on whether you want to let users personalize their app bar by pinning apps to it.</span></span>

   > [!NOTE]
   > <span data-ttu-id="e70ce-136">Параметр **"Разрешить** закрепление пользователей" доступен в Центре администрирования Teams в средах Microsoft 365 Government Community Cloud (GCC, GCC High и DoD), но в настоящее время он не действует.</span><span class="sxs-lookup"><span data-stu-id="e70ce-136">The **Allow user pinning** setting is available in the Teams admin center in Microsoft 365 Government Community Cloud (GCC) environments (GCC, GCC High and DoD), but currently it has no effect.</span></span>

6. <span data-ttu-id="e70ce-137">Чтобы установить приложения для пользователей **(в предварительной версии),** сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="e70ce-137">To install apps for users **(in preview)**, do the following tasks:</span></span>

    1. <span data-ttu-id="e70ce-138">В **области "Установленные приложения"** выберите **"Добавить приложения".**</span><span class="sxs-lookup"><span data-stu-id="e70ce-138">Under **Installed apps**, select **Add apps**.</span></span>
    
    2. <span data-ttu-id="e70ce-139">В области **"Добавить установленные** приложения" найщите приложения, которые вы хотите автоматически установить для пользователей при запуске Teams.</span><span class="sxs-lookup"><span data-stu-id="e70ce-139">In the **Add installed apps** pane, search for the apps you want to automatically install for users when they start Teams.</span></span> <span data-ttu-id="e70ce-140">Вы также можете фильтровать приложения с помощью политики разрешений приложений.</span><span class="sxs-lookup"><span data-stu-id="e70ce-140">You can also filter apps by app permission policy.</span></span> <span data-ttu-id="e70ce-141">Выбрав список приложений, выберите **"Добавить".**</span><span class="sxs-lookup"><span data-stu-id="e70ce-141">When you've chosen your list of apps, select **Add**.</span></span>

       ![The Add installed apps pane](media/app-setup-policies-add-installed-apps.png)

7. <span data-ttu-id="e70ce-143">Чтобы закрепить приложения, сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="e70ce-143">To pin apps, do the following:</span></span>

    1. <span data-ttu-id="e70ce-144">В **области закрепленных приложений** выберите **"Добавить приложения".**</span><span class="sxs-lookup"><span data-stu-id="e70ce-144">Under **Pinned apps**, select **Add apps**.</span></span>
    
    2. <span data-ttu-id="e70ce-145">В области **"Добавление** закрепленных приложений" на выберите приложения, которые вы хотите добавить, а затем выберите **"Добавить".**</span><span class="sxs-lookup"><span data-stu-id="e70ce-145">In the **Add pinned apps** pane, search for the apps you want to add, and then select **Add**.</span></span> <span data-ttu-id="e70ce-146">Вы также можете фильтровать приложения с помощью политики разрешений приложений.</span><span class="sxs-lookup"><span data-stu-id="e70ce-146">You can also filter apps by app permission policy.</span></span> <span data-ttu-id="e70ce-147">Выбрав список приложений для закрепления, выберите **"Добавить".**</span><span class="sxs-lookup"><span data-stu-id="e70ce-147">When you've chosen your list of apps to pin, select **Add**.</span></span>

       ![The Add pinned apps pane](media/app-setup-policies-add-apps.png)

    3. <span data-ttu-id="e70ce-149">Расположить приложения в том порядке, в который они должны отображаться в Teams, а затем выберите команду **"Сохранить".**</span><span class="sxs-lookup"><span data-stu-id="e70ce-149">Arrange the apps in the order that you want them to appear in Teams, and then select **Save**.</span></span>

       ![Раздел "Закрепленные приложения"](media/app-setup-policies-new-policy-setup.png)

## <a name="edit-an-app-setup-policy"></a><span data-ttu-id="e70ce-151">Изменение политики настройки приложения</span><span class="sxs-lookup"><span data-stu-id="e70ce-151">Edit an app setup policy</span></span>

<span data-ttu-id="e70ce-152">Центр администрирования Microsoft Teams можно использовать для изменения политики, включая глобальную (по умолчанию в организации) политику и настраиваемые политики, которые вы создаете.</span><span class="sxs-lookup"><span data-stu-id="e70ce-152">You can use the Microsoft Teams admin center to edit a policy, including the global (Org-wide default) policy and custom policies that you create.</span></span>

1. <span data-ttu-id="e70ce-153">В левой области навигации Центра администрирования Microsoft Teams перейдите к политикам настройки приложений **Teams.**  >  </span><span class="sxs-lookup"><span data-stu-id="e70ce-153">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Setup policies**.</span></span>

2. <span data-ttu-id="e70ce-154">Выберите политику, щелкнув слева от ее имени и выбрав **"Изменить".**</span><span class="sxs-lookup"><span data-stu-id="e70ce-154">Select the policy by clicking to the left of the policy name, and then select **Edit**.</span></span>

3. <span data-ttu-id="e70ce-155">Внесите необходимые изменения.</span><span class="sxs-lookup"><span data-stu-id="e70ce-155">From here, make the changes that you want.</span></span>

4. <span data-ttu-id="e70ce-156">Выберите **"Сохранить".**</span><span class="sxs-lookup"><span data-stu-id="e70ce-156">Select **Save**.</span></span>

## <a name="assign-a-custom-app-setup-policy-to-users"></a><span data-ttu-id="e70ce-157">Назначение пользовательской политики настройки приложений пользователям</span><span class="sxs-lookup"><span data-stu-id="e70ce-157">Assign a custom app setup policy to users</span></span>

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="faq"></a><span data-ttu-id="e70ce-158">Вопросы и ответы</span><span class="sxs-lookup"><span data-stu-id="e70ce-158">FAQ</span></span>

### <a name="working-with-app-setup-policies"></a><span data-ttu-id="e70ce-159">Работа с политиками настройки приложений</span><span class="sxs-lookup"><span data-stu-id="e70ce-159">Working with app setup policies</span></span>

#### <a name="what-built-in-app-setup-policies-are-included-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="e70ce-160">Какие встроенные политики настройки приложений включены в Центр администрирования Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="e70ce-160">What built-in app setup policies are included in the Microsoft Teams admin center</span></span>

- <span data-ttu-id="e70ce-161">**Глобальная политика (по** умолчанию для всей организации): эта политика по умолчанию применяется ко всем пользователям в организации, если только вы не назначите другую политику.</span><span class="sxs-lookup"><span data-stu-id="e70ce-161">**Global (Org-wide default)**: This default policy applies to all users in your organization unless you assign another policy.</span></span> <span data-ttu-id="e70ce-162">Отредактируем глобальную политику, чтобы закрепить приложения, которые наиболее важны для пользователей.</span><span class="sxs-lookup"><span data-stu-id="e70ce-162">Edit the global policy to pin apps that are most important for your users.</span></span>

- <span data-ttu-id="e70ce-163">**FrontlineWorker:** эта политика для сотрудников, работающих с frontline.</span><span class="sxs-lookup"><span data-stu-id="e70ce-163">**FrontlineWorker**: This policy is for Frontline Workers.</span></span> <span data-ttu-id="e70ce-164">Вы можете назначить ее сотрудникам, работающим с frontline в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="e70ce-164">You can assign it to Frontline Workers in your organization.</span></span> <span data-ttu-id="e70ce-165">Важно знать, что, как и настраиваемые политики, которые вы создаете, необходимо назначить их пользователям, чтобы параметры были активными.</span><span class="sxs-lookup"><span data-stu-id="e70ce-165">It's important to know that like custom policies that you create, you have to assign the policy to users for the settings to be active.</span></span> <span data-ttu-id="e70ce-166">Дополнительные сведения можно найти в разделе "Назначение пользовательской политики настройки приложений [пользователям"](#assign-a-custom-app-setup-policy-to-users) этой статьи.</span><span class="sxs-lookup"><span data-stu-id="e70ce-166">For more information, go to the [Assign a custom app setup policy to users](#assign-a-custom-app-setup-policy-to-users) section of this article.</span></span>

#### <a name="why-cant-i-find-an-app-in-the-add-pinned-apps-pane"></a><span data-ttu-id="e70ce-167">Почему не может найти приложение в области "Добавление закрепленных приложений"</span><span class="sxs-lookup"><span data-stu-id="e70ce-167">Why can't I find an app in the Add pinned apps pane</span></span>

<span data-ttu-id="e70ce-168">Не все приложения можно закрепить в Teams с помощью политики настройки приложений.</span><span class="sxs-lookup"><span data-stu-id="e70ce-168">Not all apps can be pinned to Teams through an app setup policy.</span></span> <span data-ttu-id="e70ce-169">Некоторые приложения могут не поддерживать эту функцию.</span><span class="sxs-lookup"><span data-stu-id="e70ce-169">Some apps may not support this functionality.</span></span> <span data-ttu-id="e70ce-170">Чтобы найти приложения, которые можно закрепить, найдите их на области **"Добавление закрепленных** приложений".</span><span class="sxs-lookup"><span data-stu-id="e70ce-170">To find apps that can be pinned, search for the app in the **Add pinned apps** pane.</span></span> <span data-ttu-id="e70ce-171">Вкладки с личной областью действия (статические вкладки) и боты можно закрепить  в клиенте Teams для настольных компьютеров. Эти приложения доступны в области "Добавление закрепленных приложений".</span><span class="sxs-lookup"><span data-stu-id="e70ce-171">Tabs that have a personal scope (static tabs) and bots can be pinned to the Teams desktop client and these apps are available in the **Add pinned apps** pane.</span></span>

<span data-ttu-id="e70ce-172">Помните, что в магазине приложений Teams перечислены все приложения Teams.</span><span class="sxs-lookup"><span data-stu-id="e70ce-172">Keep in mind that the Teams app store lists all Teams apps.</span></span> <span data-ttu-id="e70ce-173">В **области "Добавить закрепленные** приложения" есть только приложения, которые можно закрепить в Teams с помощью политики.</span><span class="sxs-lookup"><span data-stu-id="e70ce-173">The **Add pinned apps** pane includes only apps that can be pinned to Teams through a policy.</span></span>

#### <a name="im-a-teams-for-education-admin-what-do-i-need-to-know-about-app-setup-policies-in-teams-for-education"></a><span data-ttu-id="e70ce-174">Я администратор Teams для образовательных сфере. Что нужно знать о политиках настройки приложений в Teams для образовательных сфере</span><span class="sxs-lookup"><span data-stu-id="e70ce-174">I'm a Teams for Education admin. What do I need to know about app setup policies in Teams for Education</span></span>

<span data-ttu-id="e70ce-175">Приложение "Вызовы" не доступно в Teams для образовательных звонков.</span><span class="sxs-lookup"><span data-stu-id="e70ce-175">The Calling app isn't available in Teams for Education.</span></span> <span data-ttu-id="e70ce-176">При создании новой настраиваемой политики настройки приложения приложение "Вызовы" отображается в списке приложений.</span><span class="sxs-lookup"><span data-stu-id="e70ce-176">When you create a new custom app setup policy, the Calling app is displayed in the list of apps.</span></span> <span data-ttu-id="e70ce-177">Однако приложение не закреплено в клиентах Teams, и пользователи Teams для образовательных звонков не увидят приложение "Звонки" в Teams.</span><span class="sxs-lookup"><span data-stu-id="e70ce-177">However, the app isn't pinned to Teams clients and Teams for Education users won't see the Calls app in Teams.</span></span>

#### <a name="how-many-pinned-apps-can-be-added-to-a-policy"></a><span data-ttu-id="e70ce-178">Количество закрепленных приложений, которые можно добавить в политику</span><span class="sxs-lookup"><span data-stu-id="e70ce-178">How many pinned apps can be added to a policy</span></span>

<span data-ttu-id="e70ce-179">В мобильных клиентах Teams (iOS и Android) должно быть закреплено как минимум два приложения.</span><span class="sxs-lookup"><span data-stu-id="e70ce-179">A minimum of two apps must be pinned to the Teams mobile clients (iOS and Android).</span></span> <span data-ttu-id="e70ce-180">Если политика имеет менее двух приложений, мобильные клиенты не отразятся на ее параметрах и будут продолжать использовать существующую конфигурацию.</span><span class="sxs-lookup"><span data-stu-id="e70ce-180">If a policy has fewer than two apps, the mobile clients won't reflect the policy settings and instead will continue to use the existing configuration.</span></span>

<span data-ttu-id="e70ce-181">Количество закрепленных приложений, которые можно добавить в политику, не ограничивается.</span><span class="sxs-lookup"><span data-stu-id="e70ce-181">There's no limit on the number of pinned apps you can add to a policy.</span></span>

#### <a name="how-long-does-it-take-for-policy-changes-to-take-effect"></a><span data-ttu-id="e70ce-182">Сколько времени займет изменение политики</span><span class="sxs-lookup"><span data-stu-id="e70ce-182">How long does it take for policy changes to take effect</span></span>

<span data-ttu-id="e70ce-183">После изменения или назначения политики изменения вступят в силу в течение нескольких часов.</span><span class="sxs-lookup"><span data-stu-id="e70ce-183">After you edit or assign a policy, it can take a few hours for changes to take effect.</span></span>

### <a name="user-experience"></a><span data-ttu-id="e70ce-184">Впечатления от использования</span><span class="sxs-lookup"><span data-stu-id="e70ce-184">User experience</span></span>

#### <a name="how-can-users-see-all-their-pinned-apps-in-teams"></a><span data-ttu-id="e70ce-185">Как пользователи могут видеть все свои закрепленные приложения в Teams</span><span class="sxs-lookup"><span data-stu-id="e70ce-185">How can users see all their pinned apps in Teams</span></span>

<span data-ttu-id="e70ce-186">Чтобы просмотреть все приложения, закрепленные для пользователя, пользователям может потребоваться сделать следующее в зависимости от количества установленных приложений и размера окна клиента Teams.</span><span class="sxs-lookup"><span data-stu-id="e70ce-186">To view all apps that are pinned for a user, users might have to do the following depending on the number of installed apps and the size of their Teams client window.</span></span>

|<span data-ttu-id="e70ce-187">Клиент Teams для настольных ПК</span><span class="sxs-lookup"><span data-stu-id="e70ce-187">Teams desktop client</span></span> |<span data-ttu-id="e70ce-188">Мобильный клиент Teams</span><span class="sxs-lookup"><span data-stu-id="e70ce-188">Teams mobile client</span></span> |
|---------|---------|
|<span data-ttu-id="e70ce-189">На панели приложения сбоку Teams **выберите... Другие приложения.**</span><span class="sxs-lookup"><span data-stu-id="e70ce-189">In the app bar on the side of Teams, select **... More apps**.</span></span>| <span data-ttu-id="e70ce-190">Проведите пальцем вверх на панели приложения в нижней части Teams.</span><span class="sxs-lookup"><span data-stu-id="e70ce-190">In the app bar near the bottom of Teams, swipe up.</span></span>|
|![Дополнительные приложения в настольном клиенте Teams](media/app-setup-policies-desktop-more-apps.png)<br>   |![Дополнительные приложения в мобильном клиенте Teams](media/app-setup-policies-mobile-more-apps.png)  

#### <a name="what-do-i-need-to-know-about-the-teams-mobile-experience"></a><span data-ttu-id="e70ce-193">Что нужно знать о мобильном приложении Teams</span><span class="sxs-lookup"><span data-stu-id="e70ce-193">What do I need to know about the Teams mobile experience</span></span>

<span data-ttu-id="e70ce-194">Мобильные клиенты Teams (iOS и Android) в настоящее время не поддерживают личные приложения со статическими вкладками.</span><span class="sxs-lookup"><span data-stu-id="e70ce-194">The Teams mobile clients (iOS and Android) currently don't support personal apps with static tabs.</span></span> <span data-ttu-id="e70ce-195">В зависимости от приложений, установленных в политике, приложения, закрепленные в настольном клиенте Teams, могут не отображаться в мобильных клиентах Teams.</span><span class="sxs-lookup"><span data-stu-id="e70ce-195">Depending on the apps set in the policy, apps pinned to the Teams desktop client might not appear in the Teams mobile clients.</span></span> <span data-ttu-id="e70ce-196">Личные боты по-прежнему будут отображаться в чате в мобильных клиентах.</span><span class="sxs-lookup"><span data-stu-id="e70ce-196">Personal bots will still appear in Chat on mobile clients.</span></span>

<span data-ttu-id="e70ce-197">В мобильных клиентах Teams пользователи будут видеть основные приложения Teams, такие как действия, чат и Teams, и вы можете закрепить некоторые сторонние приложения от Майкрософт, например Shifts.</span><span class="sxs-lookup"><span data-stu-id="e70ce-197">With the Teams mobile clients, users will see core Teams apps such as Activity, Chat, and Teams, and you can pin some first-party apps from Microsoft, such as Shifts.</span></span>

#### <a name="can-users-change-the-order-of-apps-pinned-through-a-policy"></a><span data-ttu-id="e70ce-198">Могут ли пользователи изменять порядок приложений, закрепленных с помощью политики</span><span class="sxs-lookup"><span data-stu-id="e70ce-198">Can users change the order of apps pinned through a policy</span></span>

<span data-ttu-id="e70ce-199">Пользователи могут изменять порядок закрепленных приложений в классических  и мобильных клиентах Teams, если включен параметр "Разрешить закрепление пользователя".</span><span class="sxs-lookup"><span data-stu-id="e70ce-199">Users can change the order of their pinned apps on Teams desktop and mobile clients if the **Allow user pinning** option is turned on.</span></span> <span data-ttu-id="e70ce-200">Пользователи не могут изменять порядок закрепленных приложений в веб-клиентах Teams.</span><span class="sxs-lookup"><span data-stu-id="e70ce-200">Users can't change the order of their pinned apps on Teams web clients.</span></span>

#### <a name="does-user-pinning-take-precedence"></a><span data-ttu-id="e70ce-201">Имеет ли приоритет закрепление пользователя?</span><span class="sxs-lookup"><span data-stu-id="e70ce-201">Does user pinning take precedence</span></span>

<span data-ttu-id="e70ce-202">Если назначенная пользователю политика настройки приложения блокирует закрепление, Teams удаляет все приложения, закрепленные на панели приложения.</span><span class="sxs-lookup"><span data-stu-id="e70ce-202">If the app setup policy assigned to the user is changed to block user app pinning, Teams removes any apps pinned to the app bar.</span></span> <span data-ttu-id="e70ce-203">Если затем изменить политику, чтобы разрешить закрепление приложений, пользователям необходимо повторно закрепить ранее закрепленные приложения.</span><span class="sxs-lookup"><span data-stu-id="e70ce-203">If the policy is then changed to allow user app pinning, users must re-pin their previously pinned apps.</span></span>

### <a name="custom-teams-apps"></a><span data-ttu-id="e70ce-204">Настраиваемые приложения Teams</span><span class="sxs-lookup"><span data-stu-id="e70ce-204">Custom Teams apps</span></span>

#### <a name="my-organization-built-a-custom-teams-app-and-published-it-either-to-appsource-or-the-tenant-app-catalog-but-the-app-icon-isnt-displayed-as-expected-when-the-app-is-pinned-to-the-app-bar-in-teams-how-do-i-fix-it"></a><span data-ttu-id="e70ce-205">Моя организация создало пользовательское приложение Teams и опубликовало его в AppSource или каталоге приложений клиента, но значок приложения не отображается, как ожидалось, когда приложение закреплено на панели приложения в Teams.</span><span class="sxs-lookup"><span data-stu-id="e70ce-205">My organization built a custom Teams app and published it, either to AppSource or the tenant app catalog, but the app icon isn't displayed as expected when the app is pinned to the app bar in Teams.</span></span> <span data-ttu-id="e70ce-206">Как это исправить</span><span class="sxs-lookup"><span data-stu-id="e70ce-206">How do I fix it</span></span>

<span data-ttu-id="e70ce-207">Перед отправкой приложения убедитесь в том, что вы придерживайтесь правил для логотипа.</span><span class="sxs-lookup"><span data-stu-id="e70ce-207">Make sure that you follow the logo guidelines before you submit the app.</span></span> <span data-ttu-id="e70ce-208">Дополнительные данные см. в контрольный список для отправки [панели мониторинга продавца.](/microsoftteams/platform/concepts/deploy-and-publish/appsource/prepare/overview)</span><span class="sxs-lookup"><span data-stu-id="e70ce-208">To learn more, see [Checklist for Seller Dashboard submission](/microsoftteams/platform/concepts/deploy-and-publish/appsource/prepare/overview).</span></span>

## <a name="related-topics"></a><span data-ttu-id="e70ce-209">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="e70ce-209">Related topics</span></span>

[<span data-ttu-id="e70ce-210">Параметры администратора для приложений в Teams</span><span class="sxs-lookup"><span data-stu-id="e70ce-210">Admin settings for apps in Teams</span></span>](admin-settings.md)

[<span data-ttu-id="e70ce-211">Назначение политик пользователям в Teams</span><span class="sxs-lookup"><span data-stu-id="e70ce-211">Assign policies to your users in Teams</span></span>](assign-policies.md)
