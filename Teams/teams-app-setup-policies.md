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
ms.openlocfilehash: 32b2accc906b0f4f0dc85b5edf1d9501b64dda14
ms.sourcegitcommit: fdef9b52247097e5cae64f01b6b2b710c5b203cf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/20/2021
ms.locfileid: "49909533"
---
# <a name="manage-app-setup-policies-in-microsoft-teams"></a><span data-ttu-id="1dcd4-103">Управление политиками настройки приложений в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="1dcd4-103">Manage app setup policies in Microsoft Teams</span></span>

> [!NOTE]
> <span data-ttu-id="1dcd4-104">Если вы включили параметр приложения для всей **организации,**"Разрешить взаимодействие с пользовательскими приложениями", в Центре администрирования Microsoft Teams политики настройки приложений пока могут не отключаться.</span><span class="sxs-lookup"><span data-stu-id="1dcd4-104">If you enabled the org-wide app setting, **Allow interaction with custom apps**, you may not see app setup policies yet in the Microsoft Teams admin center.</span></span> <span data-ttu-id="1dcd4-105">В настоящее время он будет доступен в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="1dcd4-105">It's currently being rolled out and will be available soon in your organization.</span></span>

<span data-ttu-id="1dcd4-106">Администраторы могут использовать политики настройки приложений для выполнения следующих задач:</span><span class="sxs-lookup"><span data-stu-id="1dcd4-106">As an admin, you can use app setup policies to do the following tasks:</span></span>

- <span data-ttu-id="1dcd4-107">Настройте Teams, чтобы выделить приложения, которые наиболее важны для ваших пользователей.</span><span class="sxs-lookup"><span data-stu-id="1dcd4-107">Customize Teams to highlight the apps that are most important for your users.</span></span> <span data-ttu-id="1dcd4-108">Вы выбираете приложения, которые нужно закрепить, и выбираете порядок их появления.</span><span class="sxs-lookup"><span data-stu-id="1dcd4-108">You choose the apps to pin and set the order that they appear.</span></span> <span data-ttu-id="1dcd4-109">Закрепление приложений позволяет демонстрировать приложения, которые нужны пользователям в организации, в том числе приложения, встроенные сторонними разработчиками или разработчиками.</span><span class="sxs-lookup"><span data-stu-id="1dcd4-109">Pinning apps lets you showcase apps that users in your organization need, including apps built by third parties or by developers in your organization.</span></span>
- <span data-ttu-id="1dcd4-110">Контроль, могут ли пользователи прикреплять приложения к Teams.</span><span class="sxs-lookup"><span data-stu-id="1dcd4-110">Control whether users can pin apps to Teams.</span></span>
- <span data-ttu-id="1dcd4-111">Установка приложений от имени пользователей **(предварительная версия).**</span><span class="sxs-lookup"><span data-stu-id="1dcd4-111">Install apps on behalf of users **(in preview)**.</span></span> <span data-ttu-id="1dcd4-112">Вы выбираете, какие приложения устанавливаются по умолчанию пользователям при запуске Teams.</span><span class="sxs-lookup"><span data-stu-id="1dcd4-112">You choose which apps are installed by default for users when they start Teams.</span></span> <span data-ttu-id="1dcd4-113">Помните, что пользователи могут сами устанавливать [](teams-app-permission-policies.md) приложения, если это допускает назначенная им политика разрешений.</span><span class="sxs-lookup"><span data-stu-id="1dcd4-113">Keep in mind that users can still install apps themselves if the [app permission policy](teams-app-permission-policies.md) that's assigned to them allows it.</span></span>

<span data-ttu-id="1dcd4-114">Приложения закреплены на панели приложений, которая находится сбоку от клиента Teams для настольных ПК и в нижней части мобильных клиентов Teams (iOS и Android).</span><span class="sxs-lookup"><span data-stu-id="1dcd4-114">Apps are pinned to the app bar, which is the bar on the side of the Teams desktop client and at the bottom of the Teams mobile clients (iOS and Android).</span></span>

|<span data-ttu-id="1dcd4-115">Клиент Teams для настольных ПК</span><span class="sxs-lookup"><span data-stu-id="1dcd4-115">Teams desktop client</span></span>  |<span data-ttu-id="1dcd4-116">Мобильный клиент Teams</span><span class="sxs-lookup"><span data-stu-id="1dcd4-116">Teams mobile client</span></span> |
|---------|---------|
|![Клиент Teams для настольных ПК](media/app-setup-policies-desktop-app-bar.png)<br>  |   ![Мобильный клиент Teams](media/mobile-app-ui.png)      |

<span data-ttu-id="1dcd4-119">Чтобы увидеть предварительно установленные приложения, на панели приложений **выберите... Другие приложения в** классических и веб-клиентах Teams и проведите пальцем вверх в мобильных клиентах.</span><span class="sxs-lookup"><span data-stu-id="1dcd4-119">To see their pre-installed apps, in the app bar, users select **... More apps** in the Teams desktop and web clients and swipe up in the mobile clients.</span></span>

<span data-ttu-id="1dcd4-120">Вы управляете политиками настройки приложений в Центре администрирования Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="1dcd4-120">You manage app setup policies in the Microsoft Teams admin center.</span></span> <span data-ttu-id="1dcd4-121">Используйте глобальную (по умолчанию в организации) политику или создайте и назначьте настраиваемые политики.</span><span class="sxs-lookup"><span data-stu-id="1dcd4-121">Use the global (Org-wide default) policy or create and assign custom policies.</span></span>  <span data-ttu-id="1dcd4-122">Пользователи вашей организации автоматически получают глобальную политику, если вы не создали и не назначили настраиваемую политику.</span><span class="sxs-lookup"><span data-stu-id="1dcd4-122">Users in your organization will automatically get the global policy unless you create and assign a custom policy.</span></span> <span data-ttu-id="1dcd4-123">Вы должны быть глобальным администратором или администратором службы Teams, чтобы управлять этими политиками.</span><span class="sxs-lookup"><span data-stu-id="1dcd4-123">You must be a global admin or Teams service admin to manage these policies.</span></span>

<span data-ttu-id="1dcd4-124">Вы можете изменить параметры в глобальной политике, чтобы включить в нее нужные приложения.</span><span class="sxs-lookup"><span data-stu-id="1dcd4-124">You edit the settings in the global policy to include the apps that you want.</span></span> <span data-ttu-id="1dcd4-125">Чтобы настроить Teams для разных групп пользователей в организации, создайте и назначьте одну или несколько настраиваемых политик.</span><span class="sxs-lookup"><span data-stu-id="1dcd4-125">To customize Teams for different groups of users in your organization, create and assign one or more custom policies.</span></span>

![Страница "Политики настройки приложений"](media/app-setup-policies.png)

> [!NOTE]
> <span data-ttu-id="1dcd4-127">Если у вас есть Teams для образовательных образования, важно знать, что приложение "Задания" по умолчанию закреплено в глобальной политике, хотя в настоящее время оно не указано в глобальной политике.</span><span class="sxs-lookup"><span data-stu-id="1dcd4-127">If you have Teams for Education, it's important to know that the Assignments app is pinned by default in the global policy even though currently, you don't see it listed in the global policy.</span></span> <span data-ttu-id="1dcd4-128">Это будет четвертое приложение в списке закрепленных приложений в клиентах Teams.</span><span class="sxs-lookup"><span data-stu-id="1dcd4-128">It will be the fourth app in the list of pinned apps on Teams clients.</span></span>

## <a name="create-a-custom-app-setup-policy"></a><span data-ttu-id="1dcd4-129">Создание настраиваемой политики настройки приложений</span><span class="sxs-lookup"><span data-stu-id="1dcd4-129">Create a custom app setup policy</span></span>

<span data-ttu-id="1dcd4-130">Для создания настраиваемой политики можно использовать Центр администрирования Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="1dcd4-130">You can use the Microsoft Teams admin center to create a custom policy.</span></span>

1. <span data-ttu-id="1dcd4-131">В левой области навигации Центра администрирования Microsoft Teams перейдите к политикам настройки приложений **Teams.**  >  </span><span class="sxs-lookup"><span data-stu-id="1dcd4-131">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Setup policies**.</span></span>

2. <span data-ttu-id="1dcd4-132">Нажмите **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="1dcd4-132">Select **Add**.</span></span>

   ![Страница добавления политик настройки приложений](media/app-setup-policies-add.png)
    
3. <span data-ttu-id="1dcd4-134">Введите имя и описание для политики.</span><span class="sxs-lookup"><span data-stu-id="1dcd4-134">Enter a name and description for the policy.</span></span>

4. <span data-ttu-id="1dcd4-135">Включите или отключите **отправку** пользовательских приложений в зависимости от того, хотите ли вы разрешать пользователям загружать пользовательские приложения в Teams.</span><span class="sxs-lookup"><span data-stu-id="1dcd4-135">Turn on or turn off **Upload custom apps**, depending on whether you want to let users upload custom apps to Teams.</span></span> <span data-ttu-id="1dcd4-136">Вы не можете изменить  этот параметр, если в параметрах приложения для всей организации отключен параметр "Разрешить приложения сторонних [разработчиков".](manage-apps.md#manage-org-wide-app-settings)</span><span class="sxs-lookup"><span data-stu-id="1dcd4-136">You can't change this setting if **Allow third-party apps** is turned off in [org-wide app settings](manage-apps.md#manage-org-wide-app-settings).</span></span>

5. <span data-ttu-id="1dcd4-137">Включите или отключите "Разрешить закрепление" (в зависимости от того, хотите ли вы позволить пользователям персонализировать свою панели приложений, прикрепив приложения к ней).</span><span class="sxs-lookup"><span data-stu-id="1dcd4-137">Turn on or turn off **Allow user pinning**, depending on whether you want to let users personalize their app bar by pinning apps to it.</span></span>

   > [!NOTE]
   > <span data-ttu-id="1dcd4-138">Параметр **"Разрешить** закрепление пользователей" доступен в Центре администрирования Teams в средах Microsoft 365 Government Community Cloud (GCC, GCC High и DoD), но в настоящее время он не действует.</span><span class="sxs-lookup"><span data-stu-id="1dcd4-138">The **Allow user pinning** setting is available in the Teams admin center in Microsoft 365 Government Community Cloud (GCC) environments (GCC, GCC High and DoD), but currently it has no effect.</span></span>

6. <span data-ttu-id="1dcd4-139">Чтобы установить приложения для пользователей **(в предварительной версии),** сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="1dcd4-139">To install apps for users **(in preview)**, do the following tasks:</span></span>

    1. <span data-ttu-id="1dcd4-140">В **области "Установленные приложения"** выберите **"Добавить приложения".**</span><span class="sxs-lookup"><span data-stu-id="1dcd4-140">Under **Installed apps**, select **Add apps**.</span></span>
    
    2. <span data-ttu-id="1dcd4-141">В области **"Добавить установленные** приложения" найщите приложения, которые вы хотите автоматически установить для пользователей при запуске Teams.</span><span class="sxs-lookup"><span data-stu-id="1dcd4-141">In the **Add installed apps** pane, search for the apps you want to automatically install for users when they start Teams.</span></span> <span data-ttu-id="1dcd4-142">Вы также можете фильтровать приложения с помощью политики разрешений приложений.</span><span class="sxs-lookup"><span data-stu-id="1dcd4-142">You can also filter apps by app permission policy.</span></span> <span data-ttu-id="1dcd4-143">Выбрав список приложений, выберите **"Добавить".**</span><span class="sxs-lookup"><span data-stu-id="1dcd4-143">When you've chosen your list of apps, select **Add**.</span></span>

       ![The Add installed apps pane](media/app-setup-policies-add-installed-apps.png)

7. <span data-ttu-id="1dcd4-145">Чтобы закрепить приложения, сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="1dcd4-145">To pin apps, do the following:</span></span>

    1. <span data-ttu-id="1dcd4-146">В **области закрепленных приложений** выберите **"Добавить приложения".**</span><span class="sxs-lookup"><span data-stu-id="1dcd4-146">Under **Pinned apps**, select **Add apps**.</span></span>
    
    2. <span data-ttu-id="1dcd4-147">В области **"Добавление** закрепленных приложений" на выберите приложения, которые вы хотите добавить, а затем выберите **"Добавить".**</span><span class="sxs-lookup"><span data-stu-id="1dcd4-147">In the **Add pinned apps** pane, search for the apps you want to add, and then select **Add**.</span></span> <span data-ttu-id="1dcd4-148">Вы также можете фильтровать приложения с помощью политики разрешений приложений.</span><span class="sxs-lookup"><span data-stu-id="1dcd4-148">You can also filter apps by app permission policy.</span></span> <span data-ttu-id="1dcd4-149">Выбрав список приложений для закрепления, выберите **"Добавить".**</span><span class="sxs-lookup"><span data-stu-id="1dcd4-149">When you've chosen your list of apps to pin, select **Add**.</span></span>

       ![The Add pinned apps pane](media/app-setup-policies-add-apps.png)

    3. <span data-ttu-id="1dcd4-151">Расположить приложения в том порядке, в который они должны отображаться в Teams, а затем выберите команду **"Сохранить".**</span><span class="sxs-lookup"><span data-stu-id="1dcd4-151">Arrange the apps in the order that you want them to appear in Teams, and then select **Save**.</span></span>

       ![Раздел "Закрепленные приложения"](media/app-setup-policies-new-policy-setup.png)

## <a name="edit-an-app-setup-policy"></a><span data-ttu-id="1dcd4-153">Изменение политики настройки приложения</span><span class="sxs-lookup"><span data-stu-id="1dcd4-153">Edit an app setup policy</span></span>

<span data-ttu-id="1dcd4-154">Центр администрирования Microsoft Teams можно использовать для изменения политики, включая глобальную (по умолчанию в организации) политику и настраиваемые политики, которые вы создаете.</span><span class="sxs-lookup"><span data-stu-id="1dcd4-154">You can use the Microsoft Teams admin center to edit a policy, including the global (Org-wide default) policy and custom policies that you create.</span></span>

1. <span data-ttu-id="1dcd4-155">В левой области навигации Центра администрирования Microsoft Teams перейдите к политикам настройки приложений **Teams.**  >  </span><span class="sxs-lookup"><span data-stu-id="1dcd4-155">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Setup policies**.</span></span>

2. <span data-ttu-id="1dcd4-156">Выберите политику, щелкнув слева от ее имени и выбрав **"Изменить".**</span><span class="sxs-lookup"><span data-stu-id="1dcd4-156">Select the policy by clicking to the left of the policy name, and then select **Edit**.</span></span>

3. <span data-ttu-id="1dcd4-157">В этой области внести нужные изменения.</span><span class="sxs-lookup"><span data-stu-id="1dcd4-157">From here, make the changes that you want.</span></span>

4. <span data-ttu-id="1dcd4-158">Выберите **"Сохранить".**</span><span class="sxs-lookup"><span data-stu-id="1dcd4-158">Select **Save**.</span></span>

## <a name="assign-a-custom-app-setup-policy-to-users"></a><span data-ttu-id="1dcd4-159">Назначение пользовательской политики настройки приложений пользователям</span><span class="sxs-lookup"><span data-stu-id="1dcd4-159">Assign a custom app setup policy to users</span></span>

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="faq"></a><span data-ttu-id="1dcd4-160">Вопросы и ответы</span><span class="sxs-lookup"><span data-stu-id="1dcd4-160">FAQ</span></span>

### <a name="working-with-app-setup-policies"></a><span data-ttu-id="1dcd4-161">Работа с политиками настройки приложений</span><span class="sxs-lookup"><span data-stu-id="1dcd4-161">Working with app setup policies</span></span>

#### <a name="what-built-in-app-setup-policies-are-included-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="1dcd4-162">Какие встроенные политики настройки приложений включены в Центр администрирования Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="1dcd4-162">What built-in app setup policies are included in the Microsoft Teams admin center</span></span>

- <span data-ttu-id="1dcd4-163">**Глобальная политика (по** умолчанию для всей организации): эта политика по умолчанию применяется ко всем пользователям в организации, если только вы не назначите другую политику.</span><span class="sxs-lookup"><span data-stu-id="1dcd4-163">**Global (Org-wide default)**: This default policy applies to all users in your organization unless you assign another policy.</span></span> <span data-ttu-id="1dcd4-164">Отредактируем глобальную политику, чтобы закрепить приложения, которые наиболее важны для пользователей.</span><span class="sxs-lookup"><span data-stu-id="1dcd4-164">Edit the global policy to pin apps that are most important for your users.</span></span>

- <span data-ttu-id="1dcd4-165">**FrontlineWorker:** эта политика для сотрудников, работающих с frontline.</span><span class="sxs-lookup"><span data-stu-id="1dcd4-165">**FrontlineWorker**: This policy is for Frontline Workers.</span></span> <span data-ttu-id="1dcd4-166">Вы можете назначить ее сотрудникам, работающим с frontline в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="1dcd4-166">You can assign it to Frontline Workers in your organization.</span></span> <span data-ttu-id="1dcd4-167">Важно знать, что, как и настраиваемые политики, которые вы создаете, необходимо назначить их пользователям, чтобы параметры были активными.</span><span class="sxs-lookup"><span data-stu-id="1dcd4-167">It's important to know that like custom policies that you create, you have to assign the policy to users for the settings to be active.</span></span> <span data-ttu-id="1dcd4-168">Дополнительные сведения можно найти в разделе "Назначение настраиваемой политики настройки приложений [пользователям"](#assign-a-custom-app-setup-policy-to-users) этой статьи.</span><span class="sxs-lookup"><span data-stu-id="1dcd4-168">For more information, go to the [Assign a custom app setup policy to users](#assign-a-custom-app-setup-policy-to-users) section of this article.</span></span>

#### <a name="why-cant-i-find-an-app-in-the-add-pinned-apps-pane"></a><span data-ttu-id="1dcd4-169">Почему не может найти приложение в области "Добавление закрепленных приложений"</span><span class="sxs-lookup"><span data-stu-id="1dcd4-169">Why can't I find an app in the Add pinned apps pane</span></span>

<span data-ttu-id="1dcd4-170">Не все приложения можно закрепить в Teams с помощью политики настройки приложений.</span><span class="sxs-lookup"><span data-stu-id="1dcd4-170">Not all apps can be pinned to Teams through an app setup policy.</span></span> <span data-ttu-id="1dcd4-171">Некоторые приложения могут не поддерживать эту функцию.</span><span class="sxs-lookup"><span data-stu-id="1dcd4-171">Some apps may not support this functionality.</span></span> <span data-ttu-id="1dcd4-172">Чтобы найти приложения, которые можно закрепить, найдите их на области **"Добавление** закрепленных приложений".</span><span class="sxs-lookup"><span data-stu-id="1dcd4-172">To find apps that can be pinned, search for the app in the **Add pinned apps** pane.</span></span> <span data-ttu-id="1dcd4-173">Вкладки с личной областью действия (статические вкладки) и боты можно закрепить  в клиенте Teams для настольных компьютеров. Эти приложения доступны в области "Добавление закрепленных приложений".</span><span class="sxs-lookup"><span data-stu-id="1dcd4-173">Tabs that have a personal scope (static tabs) and bots can be pinned to the Teams desktop client and these apps are available in the **Add pinned apps** pane.</span></span>

<span data-ttu-id="1dcd4-174">Помните, что в магазине приложений Teams перечислены все приложения Teams.</span><span class="sxs-lookup"><span data-stu-id="1dcd4-174">Keep in mind that the Teams app store lists all Teams apps.</span></span> <span data-ttu-id="1dcd4-175">В **области "Добавить** закрепленные приложения" есть только приложения, которые можно закрепить в Teams с помощью политики.</span><span class="sxs-lookup"><span data-stu-id="1dcd4-175">The **Add pinned apps** pane includes only apps that can be pinned to Teams through a policy.</span></span>

#### <a name="im-a-teams-for-education-admin-what-do-i-need-to-know-about-app-setup-policies-in-teams-for-education"></a><span data-ttu-id="1dcd4-176">Я администратор Teams для образовательных сфере. Что нужно знать о политиках настройки приложений в Teams для образовательных сфере</span><span class="sxs-lookup"><span data-stu-id="1dcd4-176">I'm a Teams for Education admin. What do I need to know about app setup policies in Teams for Education</span></span>

<span data-ttu-id="1dcd4-177">Приложение "Вызовы" не доступно в Teams для образовательных звонков.</span><span class="sxs-lookup"><span data-stu-id="1dcd4-177">The Calling app isn't available in Teams for Education.</span></span> <span data-ttu-id="1dcd4-178">При создании новой настраиваемой политики настройки приложения приложение "Вызовы" отображается в списке приложений.</span><span class="sxs-lookup"><span data-stu-id="1dcd4-178">When you create a new custom app setup policy, the Calling app is displayed in the list of apps.</span></span> <span data-ttu-id="1dcd4-179">Однако приложение не закреплено в клиентах Teams, и пользователи Teams для образовательных звонков не увидят приложение "Звонки" в Teams.</span><span class="sxs-lookup"><span data-stu-id="1dcd4-179">However, the app isn't pinned to Teams clients and Teams for Education users won't see the Calls app in Teams.</span></span>

#### <a name="how-many-pinned-apps-can-be-added-to-a-policy"></a><span data-ttu-id="1dcd4-180">Количество закрепленных приложений, которые можно добавить в политику</span><span class="sxs-lookup"><span data-stu-id="1dcd4-180">How many pinned apps can be added to a policy</span></span>

<span data-ttu-id="1dcd4-181">В мобильных клиентах Teams (iOS и Android) должно быть закреплено как минимум два приложения.</span><span class="sxs-lookup"><span data-stu-id="1dcd4-181">A minimum of two apps must be pinned to the Teams mobile clients (iOS and Android).</span></span> <span data-ttu-id="1dcd4-182">Если политика имеет менее двух приложений, мобильные клиенты не отразятся на ее параметрах и будут продолжать использовать существующую конфигурацию.</span><span class="sxs-lookup"><span data-stu-id="1dcd4-182">If a policy has fewer than two apps, the mobile clients won't reflect the policy settings and instead will continue to use the existing configuration.</span></span>

<span data-ttu-id="1dcd4-183">Количество закрепленных приложений, которые можно добавить в политику, не ограничивается.</span><span class="sxs-lookup"><span data-stu-id="1dcd4-183">There's no limit on the number of pinned apps you can add to a policy.</span></span>

#### <a name="how-long-does-it-take-for-policy-changes-to-take-effect"></a><span data-ttu-id="1dcd4-184">Сколько времени займет изменение политики</span><span class="sxs-lookup"><span data-stu-id="1dcd4-184">How long does it take for policy changes to take effect</span></span>

<span data-ttu-id="1dcd4-185">После изменения или назначения политики может занять несколько часов, чтобы изменения вступили в силу.</span><span class="sxs-lookup"><span data-stu-id="1dcd4-185">After you edit or assign a policy, it can take a few hours for changes to take effect.</span></span>

### <a name="user-experience"></a><span data-ttu-id="1dcd4-186">Взаимодействие с пользователем</span><span class="sxs-lookup"><span data-stu-id="1dcd4-186">User experience</span></span>

#### <a name="how-can-users-see-all-their-pinned-apps-in-teams"></a><span data-ttu-id="1dcd4-187">Как пользователи могут видеть все свои закрепленные приложения в Teams</span><span class="sxs-lookup"><span data-stu-id="1dcd4-187">How can users see all their pinned apps in Teams</span></span>

<span data-ttu-id="1dcd4-188">Чтобы просмотреть все приложения, закрепленные для пользователя, пользователям может потребоваться сделать следующее в зависимости от количества установленных приложений и размера окна клиента Teams.</span><span class="sxs-lookup"><span data-stu-id="1dcd4-188">To view all apps that are pinned for a user, users might have to do the following depending on the number of installed apps and the size of their Teams client window.</span></span>

|<span data-ttu-id="1dcd4-189">Клиент Teams для настольных ПК</span><span class="sxs-lookup"><span data-stu-id="1dcd4-189">Teams desktop client</span></span> |<span data-ttu-id="1dcd4-190">Мобильный клиент Teams</span><span class="sxs-lookup"><span data-stu-id="1dcd4-190">Teams mobile client</span></span> |
|---------|---------|
|<span data-ttu-id="1dcd4-191">На панели приложения сбоку Teams **выберите... Другие приложения.**</span><span class="sxs-lookup"><span data-stu-id="1dcd4-191">In the app bar on the side of Teams, select **... More apps**.</span></span>| <span data-ttu-id="1dcd4-192">Проведите пальцем вверх на панели приложения в нижней части Teams.</span><span class="sxs-lookup"><span data-stu-id="1dcd4-192">In the app bar near the bottom of Teams, swipe up.</span></span>|
|![Дополнительные приложения в настольном клиенте Teams](media/app-setup-policies-desktop-more-apps.png)<br>   |![Дополнительные приложения в мобильном клиенте Teams](media/app-setup-policies-mobile-more-apps.png)  

#### <a name="what-do-i-need-to-know-about-the-teams-mobile-experience"></a><span data-ttu-id="1dcd4-195">Что нужно знать о мобильном приложении Teams</span><span class="sxs-lookup"><span data-stu-id="1dcd4-195">What do I need to know about the Teams mobile experience</span></span>

<span data-ttu-id="1dcd4-196">Мобильные клиенты Teams (iOS и Android) в настоящее время не поддерживают личные приложения со статическими вкладками.</span><span class="sxs-lookup"><span data-stu-id="1dcd4-196">The Teams mobile clients (iOS and Android) currently don't support personal apps with static tabs.</span></span> <span data-ttu-id="1dcd4-197">В зависимости от приложений, установленных в политике, приложения, закрепленные в настольном клиенте Teams, могут не отображаться в мобильных клиентах Teams.</span><span class="sxs-lookup"><span data-stu-id="1dcd4-197">Depending on the apps set in the policy, apps pinned to the Teams desktop client might not appear in the Teams mobile clients.</span></span> <span data-ttu-id="1dcd4-198">Личные боты по-прежнему будут отображаться в чате в мобильных клиентах.</span><span class="sxs-lookup"><span data-stu-id="1dcd4-198">Personal bots will still appear in Chat on mobile clients.</span></span>

<span data-ttu-id="1dcd4-199">В мобильных клиентах Teams пользователи будут видеть основные приложения Teams, такие как действия, чат и Teams, и вы можете закрепить некоторые сторонние приложения от Майкрософт, например Shifts.</span><span class="sxs-lookup"><span data-stu-id="1dcd4-199">With the Teams mobile clients, users will see core Teams apps such as Activity, Chat, and Teams, and you can pin some first-party apps from Microsoft, such as Shifts.</span></span>

#### <a name="can-users-change-the-order-of-apps-pinned-through-a-policy"></a><span data-ttu-id="1dcd4-200">Могут ли пользователи изменять порядок приложений, закрепленных с помощью политики</span><span class="sxs-lookup"><span data-stu-id="1dcd4-200">Can users change the order of apps pinned through a policy</span></span>

<span data-ttu-id="1dcd4-201">Пользователи могут изменять порядок закрепленных приложений в классических  и мобильных клиентах Teams, если включен параметр "Разрешить закрепление пользователя".</span><span class="sxs-lookup"><span data-stu-id="1dcd4-201">Users can change the order of their pinned apps on Teams desktop and mobile clients if the **Allow user pinning** option is turned on.</span></span> <span data-ttu-id="1dcd4-202">Пользователи не могут изменять порядок закрепленных приложений в веб-клиентах Teams.</span><span class="sxs-lookup"><span data-stu-id="1dcd4-202">Users can't change the order of their pinned apps on Teams web clients.</span></span>

#### <a name="does-user-pinning-take-precedence"></a><span data-ttu-id="1dcd4-203">Имеет ли приоритет закрепление пользователя?</span><span class="sxs-lookup"><span data-stu-id="1dcd4-203">Does user pinning take precedence</span></span>

<span data-ttu-id="1dcd4-204">Если назначенная пользователю политика настройки приложения блокирует закрепление, Teams удаляет все приложения, закрепленные на панели приложения.</span><span class="sxs-lookup"><span data-stu-id="1dcd4-204">If the app setup policy assigned to the user is changed to block user app pinning, Teams removes any apps pinned to the app bar.</span></span> <span data-ttu-id="1dcd4-205">Если затем будет изменена политика, чтобы разрешить закрепление приложений, пользователям необходимо повторно закрепить ранее закрепленные приложения.</span><span class="sxs-lookup"><span data-stu-id="1dcd4-205">If the policy is then changed to allow user app pinning, users must re-pin their previously pinned apps.</span></span>

### <a name="custom-teams-apps"></a><span data-ttu-id="1dcd4-206">Настраиваемые приложения Teams</span><span class="sxs-lookup"><span data-stu-id="1dcd4-206">Custom Teams apps</span></span>

#### <a name="my-organization-built-a-custom-teams-app-and-published-it-either-to-appsource-or-the-tenant-app-catalog-but-the-app-icon-isnt-displayed-as-expected-when-the-app-is-pinned-to-the-app-bar-in-teams-how-do-i-fix-it"></a><span data-ttu-id="1dcd4-207">Моя организация создало пользовательское приложение Teams и опубликовало его в AppSource или каталоге приложений клиента, но значок приложения не отображается, как ожидалось, когда приложение закреплено на панели приложения в Teams.</span><span class="sxs-lookup"><span data-stu-id="1dcd4-207">My organization built a custom Teams app and published it, either to AppSource or the tenant app catalog, but the app icon isn't displayed as expected when the app is pinned to the app bar in Teams.</span></span> <span data-ttu-id="1dcd4-208">Как это исправить</span><span class="sxs-lookup"><span data-stu-id="1dcd4-208">How do I fix it</span></span>

<span data-ttu-id="1dcd4-209">Перед отправкой приложения убедитесь в том, что вы придерживайтесь правил для логотипа.</span><span class="sxs-lookup"><span data-stu-id="1dcd4-209">Make sure that you follow the logo guidelines before you submit the app.</span></span> <span data-ttu-id="1dcd4-210">Дополнительные данные см. в контрольный список для отправки [панели мониторинга продавца.](/microsoftteams/platform/concepts/deploy-and-publish/appsource/prepare/overview)</span><span class="sxs-lookup"><span data-stu-id="1dcd4-210">To learn more, see [Checklist for Seller Dashboard submission](/microsoftteams/platform/concepts/deploy-and-publish/appsource/prepare/overview).</span></span>

## <a name="related-topics"></a><span data-ttu-id="1dcd4-211">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="1dcd4-211">Related topics</span></span>

[<span data-ttu-id="1dcd4-212">Параметры администратора для приложений в Teams</span><span class="sxs-lookup"><span data-stu-id="1dcd4-212">Admin settings for apps in Teams</span></span>](admin-settings.md)

[<span data-ttu-id="1dcd4-213">Назначение политик пользователям в Teams</span><span class="sxs-lookup"><span data-stu-id="1dcd4-213">Assign policies to your users in Teams</span></span>](assign-policies.md)
