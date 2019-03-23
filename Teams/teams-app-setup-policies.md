---
title: Управление политиками настройки приложений в Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 3/18/2019
ms.reviewer: lajin
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Описание политики в отношении установки приложений в Microsoft групп и как их использовать ПИН-код приложения для настройки групп для пользователей в вашей организации.
f1keywords:
- ms.teamsadmincenter.apppolicies.setup
ms.openlocfilehash: 5633e5158a3f19ea8960e957b91537547d2580a1
ms.sourcegitcommit: 5ed00e911a151d3ab834528f121db8653c25dc12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/22/2019
ms.locfileid: "30747664"
---
# <a name="manage-app-setup-policies-in-microsoft-teams"></a><span data-ttu-id="534b3-103">Управление политиками настройки приложений в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="534b3-103">Manage app setup policies in Microsoft Teams</span></span>

[!INCLUDE [preview-feature](includes/preview-feature.md)]

<span data-ttu-id="534b3-104">Как администратора можно использовать политики в отношении приложений программы установки для настройки групп Майкрософт для выделения приложений, которые наиболее важные для пользователей.</span><span class="sxs-lookup"><span data-stu-id="534b3-104">As an admin, you can use app setup policies to customize Microsoft Teams to highlight the apps that are most important for your users.</span></span> <span data-ttu-id="534b3-105">Выберите приложения для закрепления и установить порядок их отображения.</span><span class="sxs-lookup"><span data-stu-id="534b3-105">You choose the apps to pin and set the order that they appear.</span></span> <span data-ttu-id="534b3-106">Политики в отношении установки приложений позволяют демонстрационных приложений, которые должны пользователей в вашей организации, включая объекты, созданных сторонними разработчиками или разработчиками в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="534b3-106">App setup policies let you showcase apps that users in your organization need, including ones built by third parties or by developers in your organization.</span></span> <span data-ttu-id="534b3-107">Политики в отношении приложений программы установки можно также использовать для управления как встроенных функций отображаются.</span><span class="sxs-lookup"><span data-stu-id="534b3-107">You can also use app setup policies to manage how built-in features appear.</span></span>

<span data-ttu-id="534b3-108">Приложения связанные с панель приложения.</span><span class="sxs-lookup"><span data-stu-id="534b3-108">Apps are pinned to the app bar.</span></span> <span data-ttu-id="534b3-109">Это полосы прокрутки на стороне клиента рабочего стола группами и в нижней части мобильных клиентов группами (операций ввода-вывода и Android (en)).</span><span class="sxs-lookup"><span data-stu-id="534b3-109">This is the bar on the side of the Teams desktop client and at the bottom of the Teams mobile clients (iOS and Android).</span></span> 

|<span data-ttu-id="534b3-110">Настольные клиентские группы</span><span class="sxs-lookup"><span data-stu-id="534b3-110">Teams desktop client</span></span>  |<span data-ttu-id="534b3-111">Мобильный клиент групп</span><span class="sxs-lookup"><span data-stu-id="534b3-111">Teams mobile client</span></span> |
|---------|---------|
|![App-Setup-policies-Desktop-App-Bar.PNG](media/app-setup-policies-desktop-app-bar.png)<br>  |   ![App-Setup-policies-Mobile-App-Bar.PNG](media/app-setup-policies-mobile-app-bar.png)      |

<span data-ttu-id="534b3-114">Управление политики в отношении установки приложений в центре администрирования группами Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="534b3-114">You manage app setup policies in the Microsoft Teams admin center.</span></span> <span data-ttu-id="534b3-115">Можно использовать глобальную политику (масштабе организации по умолчанию) или создание настраиваемых политик и назначьте их пользователям.</span><span class="sxs-lookup"><span data-stu-id="534b3-115">You can use the global (Org-wide default) policy or create custom policies and assign them to users.</span></span> <span data-ttu-id="534b3-116">Если не создавать и назначить пользовательскую политику пользователей в вашей организации автоматически получают глобальную политику.</span><span class="sxs-lookup"><span data-stu-id="534b3-116">Users in your organization will automatically get the global policy unless you create and assign a custom policy.</span></span>

<span data-ttu-id="534b3-117">Можно изменить параметры в глобальной политики для приложений, которые требуется включить.</span><span class="sxs-lookup"><span data-stu-id="534b3-117">You can edit the settings in the global policy to include the apps that you want.</span></span> <span data-ttu-id="534b3-118">Если вы хотите настроить группы для разных групп пользователей в вашей организации, создайте и назначьте одного или нескольких настраиваемых политик.</span><span class="sxs-lookup"><span data-stu-id="534b3-118">If you want to customize Teams for different groups of users in your organization, create and assign one or more custom policies.</span></span>

![приложение установки policies.png](media/app-setup-policies.png)

> [!NOTE]
> <span data-ttu-id="534b3-120">Если пользователь назначается пользовательскую политику, применяемую политику для пользователя.</span><span class="sxs-lookup"><span data-stu-id="534b3-120">If a user is assigned a custom policy, that policy applies to the user.</span></span> <span data-ttu-id="534b3-121">Если пользователь не будет назначен пользовательскую политику, глобальной политики применяется к пользователю.</span><span class="sxs-lookup"><span data-stu-id="534b3-121">If a user isn't assigned a custom policy, the global policy applies to the user.</span></span>

## <a name="create-a-custom-app-setup-policy"></a><span data-ttu-id="534b3-122">Создание политики пользовательское приложение программы установки</span><span class="sxs-lookup"><span data-stu-id="534b3-122">Create a custom app setup policy</span></span>

<span data-ttu-id="534b3-123">Центр администрирования Microsoft группы можно использовать для создания настраиваемой политики.</span><span class="sxs-lookup"><span data-stu-id="534b3-123">You can use the Microsoft Teams admin center to create a custom policy.</span></span>

1. <span data-ttu-id="534b3-124">В левой области переходов центра администрирования группами Майкрософт, перейдите к **группам приложений** > **Настройка политик**.</span><span class="sxs-lookup"><span data-stu-id="534b3-124">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Setup policies**.</span></span>
2. <span data-ttu-id="534b3-125">Выберите **новую политику**.</span><span class="sxs-lookup"><span data-stu-id="534b3-125">Select **New policy**.</span></span>
3. <span data-ttu-id="534b3-126">Введите описательное имя для политики и нажмите кнопку **Добавить приложения**.</span><span class="sxs-lookup"><span data-stu-id="534b3-126">Enter a descriptive name for the policy, and then click **Add apps**.</span></span>
4. <span data-ttu-id="534b3-127">В области **Добавить прикрепленных приложения** поиска для приложений, которые необходимо добавить, а затем нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="534b3-127">In the **Add pinned apps** pane, search for the apps you want to add, and then click **Add**.</span></span> <span data-ttu-id="534b3-128">Приложения также можно фильтровать по политика разрешений приложения.</span><span class="sxs-lookup"><span data-stu-id="534b3-128">You can also filter apps by app permission policy.</span></span> <span data-ttu-id="534b3-129">Если вы выбрали список приложений, нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="534b3-129">When you've chosen your list of apps, click **Add**.</span></span>

     ![приложение-программы установки политик — Добавление apps.png](media/app-setup-policies-add-apps.png)

5. <span data-ttu-id="534b3-131">Структуризация приложений, в том порядке, в котором они должны отображаться в группах и нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="534b3-131">Arrange the apps in the order that you want them to appear in Teams, and then click **Save**.</span></span>

    ![App-Setup-policies-New-Policy-Setup.PNG](media/app-setup-policies-new-policy-setup.png)

## <a name="edit-an-app-setup-policy"></a><span data-ttu-id="534b3-133">Изменить политику установки приложения</span><span class="sxs-lookup"><span data-stu-id="534b3-133">Edit an app setup policy</span></span>

<span data-ttu-id="534b3-134">Можно использовать Центр администрирования группами Майкрософт для изменения политики, включая глобальной политики (по умолчанию в масштабах организации) и настраиваемых политик, которые вы создаете.</span><span class="sxs-lookup"><span data-stu-id="534b3-134">You can use the Microsoft Teams admin center to edit a policy, including the global (Org-wide default) policy and custom policies that you create.</span></span>

1. <span data-ttu-id="534b3-135">В левой области переходов центра администрирования группами Майкрософт, перейдите к **группам приложений** > **Настройка политик**.</span><span class="sxs-lookup"><span data-stu-id="534b3-135">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Setup policies**.</span></span>
2. <span data-ttu-id="534b3-136">Выберите политику, которую требуется изменить.</span><span class="sxs-lookup"><span data-stu-id="534b3-136">Select the policy you want to edit.</span></span> 
3. <span data-ttu-id="534b3-137">Здесь внесите изменения, которые будут.</span><span class="sxs-lookup"><span data-stu-id="534b3-137">From here, make the changes that you want.</span></span> <span data-ttu-id="534b3-138">Можно добавлять, удалять и изменять порядок приложений.</span><span class="sxs-lookup"><span data-stu-id="534b3-138">You can add, remove, and change the order of apps.</span></span>
4. <span data-ttu-id="534b3-139">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="534b3-139">Click **Save**.</span></span>

## <a name="assign-a-custom-app-setup-policy-to-users"></a><span data-ttu-id="534b3-140">Назначение политики пользовательское приложение программы установки для пользователей</span><span class="sxs-lookup"><span data-stu-id="534b3-140">Assign a custom app setup policy to users</span></span>

<span data-ttu-id="534b3-141">Можно использовать Центр администрирования группами Майкрософт назначение настраиваемая политика для отдельных пользователей или Скайп для модуль Business PowerShell назначение настраиваемой политики для групп пользователей, такие как группы безопасности или группу рассылки.</span><span class="sxs-lookup"><span data-stu-id="534b3-141">You can use the Microsoft Teams admin center to assign a custom policy to individual users or the Skype for Business PowerShell module  to assign a custom policy to groups of users, such as a security group or distribution group.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="534b3-142">Рекомендуется только для назначения политик для пользователей, используя PowerShell.</span><span class="sxs-lookup"><span data-stu-id="534b3-142">We recommend using PowerShell only to assign policies to users.</span></span> <span data-ttu-id="534b3-143">Использование центра администрирования группами Майкрософт для создания, редактирования и управление политиками.</span><span class="sxs-lookup"><span data-stu-id="534b3-143">Use the Microsoft Teams admin center to create, edit, and manage policies.</span></span>

### <a name="assign-a-custom-app-setup-policy-to-individual-users"></a><span data-ttu-id="534b3-144">Назначение политики установки пользовательское приложение для отдельных пользователей</span><span class="sxs-lookup"><span data-stu-id="534b3-144">Assign a custom app setup policy to individual users</span></span>

1. <span data-ttu-id="534b3-145">В левой области переходов центра администрирования группами Майкрософт перейдите к **пользователям**и нажмите кнопку пользователя.</span><span class="sxs-lookup"><span data-stu-id="534b3-145">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click  the user.</span></span>
2. <span data-ttu-id="534b3-146">Рядом с пунктом **назначения политик**и выберите **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="534b3-146">Next to **Assigned policies**, choose **Edit**.</span></span>
3. <span data-ttu-id="534b3-147">В разделе **политика установки приложения группы**выберите политику установки приложения, которую необходимо назначить и нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="534b3-147">Under **Teams App Setup policy**, select the app setup policy you want to assign, and then choose **Save**.</span></span>

    ![приложение-программы установки политик assign-policy.png](media/app-setup-policies-assign-policy.png)

<span data-ttu-id="534b3-149">Можно также назначить политику установки приложения к одному или нескольким пользователям следующим образом:</span><span class="sxs-lookup"><span data-stu-id="534b3-149">You can also assign an app setup policy to one or more users as follows:</span></span>

1. <span data-ttu-id="534b3-150">Перейдите в **Центр администрирования группами Майкрософт** > **группами приложений** > **Настройка политик**.</span><span class="sxs-lookup"><span data-stu-id="534b3-150">Go to **Microsoft Teams admin center** > **Teams apps** > **Setup policies**.</span></span>
2. <span data-ttu-id="534b3-151">Выберите политику, нажав кнопку слева от имени политики.</span><span class="sxs-lookup"><span data-stu-id="534b3-151">Select the policy by clicking to the left of the policy name.</span></span>
3. <span data-ttu-id="534b3-152">Выберите **Управление пользователями**.</span><span class="sxs-lookup"><span data-stu-id="534b3-152">Select **Manage users**.</span></span>
4. <span data-ttu-id="534b3-153">В области **Управление пользователями** поиска для пользователя по отображаемому имени или по имени пользователя, выберите имя и выберите команду **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="534b3-153">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then select **Add**.</span></span> <span data-ttu-id="534b3-154">Повторите этот шаг для каждого пользователя, который вы хотите добавить.</span><span class="sxs-lookup"><span data-stu-id="534b3-154">Repeat this step for each user that you want to add.</span></span>
5. <span data-ttu-id="534b3-155">Завершив добавление пользователей, выберите команду **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="534b3-155">When you are finished adding users, select **Save**.</span></span>

### <a name="assign-a-custom-app-setup-policy-to-users-in-a-group"></a><span data-ttu-id="534b3-156">Назначение политики пользовательское приложение программы установки для пользователей в группы</span><span class="sxs-lookup"><span data-stu-id="534b3-156">Assign a custom app setup policy to users in a group</span></span>

<span data-ttu-id="534b3-157">Может потребоваться назначение политики установки пользовательское приложение к нескольким пользователям, которые уже определен.</span><span class="sxs-lookup"><span data-stu-id="534b3-157">You may want to assign a custom app setup policy to multiple users that you’ve already identified.</span></span> <span data-ttu-id="534b3-158">Например можно назначить политики для всех пользователей в группу безопасности.</span><span class="sxs-lookup"><span data-stu-id="534b3-158">For example, you may want to assign a policy to all users in a security group.</span></span> <span data-ttu-id="534b3-159">Это можно сделать, подключение к Azure Active Directory PowerShell для модуля график и Скайп для модуль PowerShell бизнеса.</span><span class="sxs-lookup"><span data-stu-id="534b3-159">You can do this by connecting to the Azure Active Directory PowerShell for Graph module and the Skype for Business PowerShell module.</span></span> <span data-ttu-id="534b3-160">Дополнительные сведения об использовании PowerShell для управления группами см [Команды PowerShell](teams-powershell-overview.md).</span><span class="sxs-lookup"><span data-stu-id="534b3-160">For more information about using PowerShell to manage Teams, see [Teams PowerShell Overview](teams-powershell-overview.md).</span></span>

<span data-ttu-id="534b3-161">В этом примере мы назначение политики установки пользовательское приложение вызывается политики программы установки приложения отдела Кадров для всех пользователей в группу проекта Contoso Pharmaceuticals отдела Кадров.</span><span class="sxs-lookup"><span data-stu-id="534b3-161">In this example, we assign a custom app setup policy called HR App Setup Policy to all users in the Contoso Pharmaceuticals HR Project group.</span></span>  

> [!NOTE]
> <span data-ttu-id="534b3-162">Убедитесь, что подключение сначала для Azure Active Directory PowerShell для модуля график и Скайп для модуль Business PowerShell, выполнив действия, описанные в [подключиться ко всем службам Office 365 в одном окне Windows PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).</span><span class="sxs-lookup"><span data-stu-id="534b3-162">Make sure you first connect to the Azure Active Directory PowerShell for Graph module and Skype for Business PowerShell module by following the steps in [Connect to all Office 365 services in a single Windows PowerShell window](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).</span></span>

<span data-ttu-id="534b3-163">Получите GroupObjectId конкретной группы.</span><span class="sxs-lookup"><span data-stu-id="534b3-163">Get the GroupObjectId of the particular group.</span></span>
```
$group = Get-AzureADGroup -SearchString "Contoso Pharmaceuticals HR Project"
```
<span data-ttu-id="534b3-164">Получение элементов из указанной группы.</span><span class="sxs-lookup"><span data-stu-id="534b3-164">Get the members of the specified group.</span></span>
```
$members = Get-AzureADGroupMember -ObjectId $group.ObjectId -All $true | Where-Object {$_.ObjectType -eq "User"}
```
<span data-ttu-id="534b3-165">Назначьте всех пользователей в группе политика установки определенного приложения.</span><span class="sxs-lookup"><span data-stu-id="534b3-165">Assign all users in the group to a particular app setup policy.</span></span> <span data-ttu-id="534b3-166">В этом примере это политики программы установки приложения отдела Кадров.</span><span class="sxs-lookup"><span data-stu-id="534b3-166">In this example, it's HR App Setup Policy.</span></span>
```
$members | ForEach-Object { Grant-CsTeamsAppSetupPolicy -PolicyName "HR App Setup Policy" -Identity $_.EmailAddress}
``` 
<span data-ttu-id="534b3-167">В зависимости от числа членов группы эта команда может занять несколько минут для выполнения.</span><span class="sxs-lookup"><span data-stu-id="534b3-167">Depending on the number of members in the group, this command may take several minutes to execute.</span></span>

## <a name="faq"></a><span data-ttu-id="534b3-168">Вопросы и ответы</span><span class="sxs-lookup"><span data-stu-id="534b3-168">FAQ</span></span>

### <a name="working-with-app-setup-policies"></a><span data-ttu-id="534b3-169">Работа с политиками программы установки приложения</span><span class="sxs-lookup"><span data-stu-id="534b3-169">Working with app setup policies</span></span>

#### <a name="what-built-in-app-setup-policies-are-included-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="534b3-170">Какие политики установки встроенные приложения включены в центре администрирования группами Майкрософт?</span><span class="sxs-lookup"><span data-stu-id="534b3-170">What built-in app setup policies are included in the Microsoft Teams admin center?</span></span>

- <span data-ttu-id="534b3-171">**Global (по умолчанию в масштабах организации)**: применяется данная политика по умолчанию для всех пользователей в вашей организации, если не назначить другую политику.</span><span class="sxs-lookup"><span data-stu-id="534b3-171">**Global (Org-wide default)**: This default policy applies to all users in your organization unless you assign another policy.</span></span> <span data-ttu-id="534b3-172">Изменение глобальной политики ПИН-код приложений, которые наиболее важные для пользователей.</span><span class="sxs-lookup"><span data-stu-id="534b3-172">Edit the global policy to pin apps that are most important for your users.</span></span>
- <span data-ttu-id="534b3-173">**FirstLineWorker**: эта политика предназначена для firstline работников.</span><span class="sxs-lookup"><span data-stu-id="534b3-173">**FirstLineWorker**: This policy is for firstline workers.</span></span> <span data-ttu-id="534b3-174">Можно назначить его firstline сотрудников в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="534b3-174">You can assign it to firstline workers in your organization.</span></span> <span data-ttu-id="534b3-175">Важно знать, что как настраиваемых политик, которые вы создаете, вам необходимо назначить политику пользователей для параметров является активным.</span><span class="sxs-lookup"><span data-stu-id="534b3-175">It's important to know that like custom policies that you create, you have to assign the policy to users for the settings to be active.</span></span> <span data-ttu-id="534b3-176">Для получения дополнительных сведений перейдите к разделу [Назначение политики пользовательское приложение программы установки для пользователей](#assign-a-custom-app-setup-policy-to-users) в этой статье.</span><span class="sxs-lookup"><span data-stu-id="534b3-176">For more information, go to the [Assign a custom app setup policy to users](#assign-a-custom-app-setup-policy-to-users) section of this article.</span></span>

#### <a name="why-cant-i-find-an-app-in-the-add-pinned-apps-pane"></a><span data-ttu-id="534b3-177">Почему не удается найти приложения в области добавить закрепленных приложений</span><span class="sxs-lookup"><span data-stu-id="534b3-177">Why can't I find an app in the Add pinned apps pane?</span></span>

<span data-ttu-id="534b3-178">Не все приложения можно прикрепить к группам через политику установки приложения.</span><span class="sxs-lookup"><span data-stu-id="534b3-178">Not all apps can be pinned to Teams through an app setup policy.</span></span> <span data-ttu-id="534b3-179">Некоторые приложения могут не поддерживать эту функцию.</span><span class="sxs-lookup"><span data-stu-id="534b3-179">Some apps may not support this functionality.</span></span> <span data-ttu-id="534b3-180">Чтобы найти приложения, которые могут быть администратором, выполните поиск приложения в области **Добавить прикрепленных приложений** .</span><span class="sxs-lookup"><span data-stu-id="534b3-180">To find apps that can be pinned, search for the app in the **Add pinned apps** pane.</span></span> <span data-ttu-id="534b3-181">Вкладки с личных область (вкладки «статический») и программы-роботы можно прикрепить к группам клиентское и эти приложения, доступные в области **Добавить прикрепленных приложений** .</span><span class="sxs-lookup"><span data-stu-id="534b3-181">Tabs that have a personal scope (static tabs) and bots can be pinned to the Teams desktop client and these apps are available in the **Add pinned apps** pane.</span></span>

<span data-ttu-id="534b3-182">Имейте в виду, что хранилище приложений группы перечислены все приложения группы, в то время как в области **Добавить прикрепленных приложений** включает в себя только приложения, которые можно прикрепить к группам политикой.</span><span class="sxs-lookup"><span data-stu-id="534b3-182">Keep in mind that the Teams app store lists all Teams apps whereas the **Add pinned apps** pane includes only apps that can be pinned to Teams through a policy.</span></span> 

#### <a name="im-a-teams-for-education-admin-what-do-i-need-to-know-about-app-setup-policies-in-teams-for-education"></a><span data-ttu-id="534b3-183">Я группы для образовательных заведений администратор. Что нужно знать о политиках программы установки приложения в группах для образовательных заведений?</span><span class="sxs-lookup"><span data-stu-id="534b3-183">I'm a Teams for Education admin. What do I need to know about app setup policies in Teams for Education?</span></span>

<span data-ttu-id="534b3-184">Вызов приложения недоступен в группах для образовательных учреждений.</span><span class="sxs-lookup"><span data-stu-id="534b3-184">The Calling app isn't available in Teams for Education.</span></span> <span data-ttu-id="534b3-185">При создании новой политики установки настраиваемого приложения, вызывающего приложение отображается в списке приложений.</span><span class="sxs-lookup"><span data-stu-id="534b3-185">When you create a new custom app setup policy, the Calling app is displayed in the list of apps.</span></span> <span data-ttu-id="534b3-186">Тем не менее приложение не связанные с группами клиентов и групп для образовательных заведений пользователей не будут отображаться приложение вызовы в группы.</span><span class="sxs-lookup"><span data-stu-id="534b3-186">However, the app isn't pinned to Teams clients and Teams for Education users won't see the Calls app in Teams.</span></span> 

#### <a name="how-many-apps-can-be-added-to-a-policy"></a><span data-ttu-id="534b3-187">Сколько приложений можно добавить в политику?</span><span class="sxs-lookup"><span data-stu-id="534b3-187">How many apps can be added to a policy?</span></span>

<span data-ttu-id="534b3-188">Не менее двух приложений должен быть администратором для мобильных клиентов группами (операций ввода-вывода и Android (en)).</span><span class="sxs-lookup"><span data-stu-id="534b3-188">A minimum of two apps must be pinned to the Teams mobile clients (iOS and Android).</span></span> <span data-ttu-id="534b3-189">Если политика имеет меньше, чем двух приложений, мобильные клиенты могут не отражать параметры политики и продолжат использовать существующую конфигурацию.</span><span class="sxs-lookup"><span data-stu-id="534b3-189">If a policy has less than two apps, the mobile clients won't reflect the policy settings and instead will continue to use the existing configuration.</span></span>

#### <a name="how-long-does-it-take-for-policy-changes-to-take-effect"></a><span data-ttu-id="534b3-190">Сколько времени для изменения политики вступили в силу?</span><span class="sxs-lookup"><span data-stu-id="534b3-190">How long does it take for policy changes to take effect?</span></span>

<span data-ttu-id="534b3-191">Изменить глобальную политику или назначение политики, может потребоваться до 24 часов для изменения вступили в силу.</span><span class="sxs-lookup"><span data-stu-id="534b3-191">After you edit the global policy or assign a policy, it can take up to 24 hours for changes to take effect.</span></span>

### <a name="user-experience"></a><span data-ttu-id="534b3-192">Взаимодействие с пользователем</span><span class="sxs-lookup"><span data-stu-id="534b3-192">User experience</span></span>

#### <a name="how-can-users-see-all-their-pinned-apps-in-teams"></a><span data-ttu-id="534b3-193">Как пользователи могут видеть все их закрепленных приложения в группах</span><span class="sxs-lookup"><span data-stu-id="534b3-193">How can users see all their pinned apps in Teams?</span></span>

<span data-ttu-id="534b3-194">Чтобы просмотреть все приложения, связанные для пользователя, пользователи могут иметь к выполните следующие действия в зависимости от числа установленные приложения и размер окна клиента их группами.</span><span class="sxs-lookup"><span data-stu-id="534b3-194">To view all apps that are pinned for a user, users may have to do the following depending on the number of installed apps and the size of their Teams client window.</span></span>

|<span data-ttu-id="534b3-195">Настольные клиентские группы</span><span class="sxs-lookup"><span data-stu-id="534b3-195">Teams desktop client</span></span> |<span data-ttu-id="534b3-196">Мобильный клиент групп</span><span class="sxs-lookup"><span data-stu-id="534b3-196">Teams mobile client</span></span> |
|---------|---------|
|<span data-ttu-id="534b3-197">В панели приложения на краю группы щелкните **... Дополнительные приложения**.</span><span class="sxs-lookup"><span data-stu-id="534b3-197">In the app bar on the side of Teams, click **... More apps**.</span></span>| <span data-ttu-id="534b3-198">В панели приложения в нижней части группы проведите вверх.</span><span class="sxs-lookup"><span data-stu-id="534b3-198">In the app bar near the bottom of Teams, swipe up.</span></span>|
|![App-Setup-policies-Desktop-More-Apps.PNG](media/app-setup-policies-desktop-more-apps.png)<br>   |![App-Setup-policies-Mobile-More-Apps.PNG](media/app-setup-policies-mobile-more-apps.png)  

#### <a name="what-do-i-need-to-know-about-the-teams-mobile-experience"></a><span data-ttu-id="534b3-201">Что нужно знать о взаимодействия мобильных групп?</span><span class="sxs-lookup"><span data-stu-id="534b3-201">What do I need to know about the Teams mobile experience?</span></span>

<span data-ttu-id="534b3-202">Группы мобильных клиентов (операций ввода-вывода и Android) в настоящее время не поддерживают личные приложений с помощью статического вкладок.</span><span class="sxs-lookup"><span data-stu-id="534b3-202">The Teams mobile clients (iOS and Android) currently don't support personal apps with static tabs.</span></span> <span data-ttu-id="534b3-203">В зависимости от приложения, задайте в политике приложения, связанные с группами клиентское могут не отображаться в клиентах мобильных групп.</span><span class="sxs-lookup"><span data-stu-id="534b3-203">Depending on the apps set in the policy, apps pinned to the Teams desktop client might not appear in the Teams mobile clients.</span></span> <span data-ttu-id="534b3-204">Личные программы-роботы по-прежнему будут отображаться в чата на мобильных клиентов.</span><span class="sxs-lookup"><span data-stu-id="534b3-204">Personal bots will still appear in Chat on mobile clients.</span></span>

<span data-ttu-id="534b3-205">С помощью мобильных клиентов групп пользователи увидят основных групп приложений такие как действия, беседы или группам и можно закрепить некоторых приложений основном от корпорации Майкрософт, такие как смены.</span><span class="sxs-lookup"><span data-stu-id="534b3-205">With the Teams mobile clients, users will see core Teams apps such as Activity, Chat, and Teams, and you can pin some first-party apps from Microsoft, such as Shifts.</span></span>

#### <a name="can-users-change-the-order-of-apps-pinned-through-a-policy"></a><span data-ttu-id="534b3-206">Пользователи порядок можно изменить прикрепленных политикой приложений?</span><span class="sxs-lookup"><span data-stu-id="534b3-206">Can users change the order of apps pinned through a policy?</span></span>

<span data-ttu-id="534b3-207">В настоящее время пользователи могут изменять порядок их закрепленных приложения на групп мобильных клиентов, но не на группы рабочий стол или веб-клиентов.</span><span class="sxs-lookup"><span data-stu-id="534b3-207">Currently, users can change the order of their pinned apps on Teams mobile clients but not on the Teams desktop or web clients.</span></span> 

### <a name="custom-teams-apps"></a><span data-ttu-id="534b3-208">Настраиваемые группы приложений</span><span class="sxs-lookup"><span data-stu-id="534b3-208">Custom Teams apps</span></span>

#### <a name="my-organization-built-a-custom-teams-app-and-published-it-either-to-appsource-or-the-tenant-app-catalog-but-the-app-icon-isnt-displayed-as-expected-when-the-app-is-pinned-to-the-app-bar-in-teams-how-do-i-fix-it"></a><span data-ttu-id="534b3-209">Моя организация созданных пользовательское приложение групп и публикации его, либо AppSource или каталога приложений клиентов, но значок приложения не отображается должным образом при приложения, прикрепленные к панели приложения в группах.</span><span class="sxs-lookup"><span data-stu-id="534b3-209">My organization built a custom Teams app and published it, either to AppSource or the Tenant app catalog, but the app icon isn't displayed as expected when the app is pinned to the app bar in Teams.</span></span> <span data-ttu-id="534b3-210">Как исправить его?</span><span class="sxs-lookup"><span data-stu-id="534b3-210">How do I fix it?</span></span> 

<span data-ttu-id="534b3-211">Убедитесь в том, следуйте правилам логотипов перед отправкой приложения.</span><span class="sxs-lookup"><span data-stu-id="534b3-211">Make sure that you follow the logo guidelines before you submit the app.</span></span> <span data-ttu-id="534b3-212">[Контрольный список для отправки панели мониторинга продавца](https://docs.microsoft.com/microsoftteams/platform/publishing/office-store-checklist)Дополнительные сведения см.</span><span class="sxs-lookup"><span data-stu-id="534b3-212">To learn more, see [Checklist for Seller Dashboard submission](https://docs.microsoft.com/microsoftteams/platform/publishing/office-store-checklist).</span></span> 

 ## <a name="related-topics"></a><span data-ttu-id="534b3-213">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="534b3-213">Related topics</span></span>
- [<span data-ttu-id="534b3-214">Параметры администратора для приложений в Teams</span><span class="sxs-lookup"><span data-stu-id="534b3-214">Admin settings for apps in Teams</span></span>](admin-settings.md)
- [<span data-ttu-id="534b3-215">Управление политиками разрешений приложения в группах</span><span class="sxs-lookup"><span data-stu-id="534b3-215">Manage app permission policies in Teams</span></span>](teams-app-permission-policies.md)
- [<span data-ttu-id="534b3-216">Управлять политиками пользовательское приложение и параметры в группах</span><span class="sxs-lookup"><span data-stu-id="534b3-216">Manage custom app policies and settings in Teams</span></span>](teams-custom-app-policies-and-settings.md)
- [<span data-ttu-id="534b3-217">Публикация приложения в каталог приложений клиента из группы клиента</span><span class="sxs-lookup"><span data-stu-id="534b3-217">Publish an app to the Tenant Apps Catalog from the Teams client</span></span>](tenant-apps-catalog-teams.md)
