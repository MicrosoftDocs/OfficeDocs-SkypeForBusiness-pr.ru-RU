---
title: Управление политиками разрешений для приложений в Microsoft Teams
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
description: Ознакомьтесь с политиками разрешений приложения в Microsoft групп и как их использовать для управления, какие приложения доступны для пользователей в вашей организации.
f1keywords:
- ms.teamsadmincenter.apppolicies.overview
ms.openlocfilehash: 49200d597811d87ce27d94d9bb19577def6355c1
ms.sourcegitcommit: a505869a3cc2fe6fe4ee18bcbe99bf980aa91a86
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "31520226"
---
# <a name="manage-app-permission-policies-in-microsoft-teams"></a><span data-ttu-id="a0211-103">Управление политиками разрешений для приложений в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="a0211-103">Manage app permission policies in Microsoft Teams</span></span>

> [!INCLUDE [feature coming soon](includes/new-feature-coming-soon.md)]

<span data-ttu-id="a0211-104">Как администратора чтобы контролировать, какие приложения будут доступны пользователям группами Майкрософт в организации можно использовать политики разрешений приложения.</span><span class="sxs-lookup"><span data-stu-id="a0211-104">As an admin, you can use app permission policies to control what apps are available to Microsoft Teams users in your organization.</span></span> <span data-ttu-id="a0211-105">Можно разрешить или заблокировать все приложения или определенных приложений, опубликованные корпорацией Майкрософт, сторонние производители и вашей организации.</span><span class="sxs-lookup"><span data-stu-id="a0211-105">You can allow or block all apps or specific apps published by Microsoft, third-parties, and your organization.</span></span> <span data-ttu-id="a0211-106">При блокировании приложения, пользователи не могут установить его из хранилища приложения группы.</span><span class="sxs-lookup"><span data-stu-id="a0211-106">When you block an app, users are unable to install it from the Teams app store.</span></span>

<span data-ttu-id="a0211-107">Для управления политиками разрешений приложения в центре администрирования группами Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="a0211-107">You manage app permission policies in the Microsoft Teams admin center.</span></span> <span data-ttu-id="a0211-108">Можно применить параметры всей организации, с помощью глобальной политики (по умолчанию в масштабах организации), создание и назначение настраиваемых политик для отдельных пользователей или пользователей в группу.</span><span class="sxs-lookup"><span data-stu-id="a0211-108">You can apply settings org-wide, use the global (Org-wide default) policy, and create and assign custom policies to individual users or users in a group.</span></span>  

![Снимок экрана приложения политику разрешений](media/app-permission-policies.png)

> [!NOTE]
> <span data-ttu-id="a0211-110">Если не создавать и назначить пользовательскую политику пользователей в вашей организации автоматически получают глобальную политику.</span><span class="sxs-lookup"><span data-stu-id="a0211-110">Users in your organization will automatically get the global policy unless you create and assign a custom policy.</span></span> <span data-ttu-id="a0211-111">Настройки приложения масштабе организации переопределения глобальную политику и настраиваемых политик, создайте и назначьте для пользователей.</span><span class="sxs-lookup"><span data-stu-id="a0211-111">Org-wide app settings override the global policy and any custom policies that you create and assign to users.</span></span>

<span data-ttu-id="a0211-112">Предположим, например, нужно адресов все приложения сторонних производителей и конкретные приложения от корпорации Майкрософт для управления Персоналом группы в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="a0211-112">Say, for example, you want to block all third-party apps and allow specific apps from Microsoft for the HR team in your organization.</span></span> <span data-ttu-id="a0211-113">Будет создать пользовательскую политику с именем политики разрешений приложения отдела Кадров, настройте его на адресов и приложений, которые будут и назначить пользователям в группе отдела Кадров.</span><span class="sxs-lookup"><span data-stu-id="a0211-113">You would create a custom policy named HR App Permission Policy, set it to block and allow the apps that you want, and then assign it to users on the HR team.</span></span>

## <a name="manage-org-wide-app-settings"></a><span data-ttu-id="a0211-114">Управление параметрами приложения масштабе организации</span><span class="sxs-lookup"><span data-stu-id="a0211-114">Manage org-wide app settings</span></span>

<span data-ttu-id="a0211-115">Использование параметров приложения в масштабе организации ли контролировать, какие приложения, доступны в организации.</span><span class="sxs-lookup"><span data-stu-id="a0211-115">Use org-wide app settings to control which apps are available across your organization.</span></span> <span data-ttu-id="a0211-116">Параметры приложения в масштабе организации управляют поведением для всех пользователей и переопределить любые разрешение политики приложения, назначенные пользователям.</span><span class="sxs-lookup"><span data-stu-id="a0211-116">Org-wide app settings govern the behavior for all users and override any other app permission policies assigned to users.</span></span> <span data-ttu-id="a0211-117">Настройки приложения масштабе организации вступили в силу немедленно, и их можно использовать для управления вредоносные или инспектором приложений.</span><span class="sxs-lookup"><span data-stu-id="a0211-117">Org-wide app settings take effect immediately and you can use them to control malicious or problematic apps.</span></span>

1. <span data-ttu-id="a0211-118">В левой области переходов центра администрирования группами Майкрософт, перейдите к **группам приложения** > **политики разрешений**.</span><span class="sxs-lookup"><span data-stu-id="a0211-118">In the left navigation of the Microsoft Teams admin center, go to **Teams app** > **Permission policies**.</span></span>
2. <span data-ttu-id="a0211-119">Выберите **Параметры на уровне организации**.</span><span class="sxs-lookup"><span data-stu-id="a0211-119">Select **Org-wide settings**.</span></span> <span data-ttu-id="a0211-120">Затем можно настроить параметры, которые требуется в панели.</span><span class="sxs-lookup"><span data-stu-id="a0211-120">You can then configure the settings you want in the panel.</span></span> 
<span data-ttu-id="a0211-121">![Снимок экрана параметров приложения в масштабе организации](media/app-permission-policies-org-wide-settings.png)</span><span class="sxs-lookup"><span data-stu-id="a0211-121">![Screen shot of org-wide app settings](media/app-permission-policies-org-wide-settings.png)</span></span>
3. <span data-ttu-id="a0211-122">В разделе **приложения сторонних производителей**отключить или включить эти параметры для управления доступом к приложениям сторонних производителей:</span><span class="sxs-lookup"><span data-stu-id="a0211-122">Under **Third-party apps**, turn off or turn on these settings to control access to third-party apps:</span></span>

    - <span data-ttu-id="a0211-123">**Разрешить приложений сторонних производителей в группах**: Определяет, могут ли пользователи с помощью приложения сторонних производителей.</span><span class="sxs-lookup"><span data-stu-id="a0211-123">**Allow third-party apps in Teams**: This controls whether users can use third-party apps.</span></span>
    - <span data-ttu-id="a0211-124">**Разрешить любой новых приложений сторонних производителей, опубликован в хранилище по умолчанию**: в этом ли новые приложения сторонних производителей, которые опубликованы в приложения группы хранения автоматически доступны в группах элементов управления.</span><span class="sxs-lookup"><span data-stu-id="a0211-124">**Allow any new third-party apps published to the store by default**: This controls whether new third-party apps that are published to the Teams app store become automatically available in Teams.</span></span> <span data-ttu-id="a0211-125">Этот параметр можно задать только в том случае, если вы включили приложений сторонних производителей.</span><span class="sxs-lookup"><span data-stu-id="a0211-125">You can only set this option if you allow third-party apps.</span></span>

4. <span data-ttu-id="a0211-126">В разделе **Custom apps**отключить или включить **Разрешить взаимодействие с настраиваемые приложения**.</span><span class="sxs-lookup"><span data-stu-id="a0211-126">Under **Custom apps**, turn off or turn on **Allow interaction with custom apps**.</span></span> <span data-ttu-id="a0211-127">Этот параметр определяет, будет ли пользователи могут работать с приложениями custom (sideloaded).</span><span class="sxs-lookup"><span data-stu-id="a0211-127">This setting controls whether users can interact with custom (sideloaded) apps.</span></span> <span data-ttu-id="a0211-128">Имейте в виду, что это отличается от позволяя пользователям *загружать* настраиваемые приложения.</span><span class="sxs-lookup"><span data-stu-id="a0211-128">Keep in mind that this is different from allowing users to *upload* custom apps.</span></span>
5. <span data-ttu-id="a0211-129">В разделе **приложения заблокирован**искать и добавлять приложения, которые необходимо заблокировать внутри организации.</span><span class="sxs-lookup"><span data-stu-id="a0211-129">Under **Blocked apps**, search for and add the apps that you want to block across your organization.</span></span> <span data-ttu-id="a0211-130">Приложения можно выбрать из каталога приложений клиента или в хранилище приложений группами.</span><span class="sxs-lookup"><span data-stu-id="a0211-130">You can choose apps from the tenant app catalog or the Teams app store.</span></span>
6. <span data-ttu-id="a0211-131">Нажмите кнопку **Сохранить** для настройки приложения масштабе организации вступили в силу.</span><span class="sxs-lookup"><span data-stu-id="a0211-131">Click **Save** for org-wide app settings to take effect.</span></span>

## <a name="create-a-custom-app-permission-policy"></a><span data-ttu-id="a0211-132">Создайте политику разрешений пользовательское приложение</span><span class="sxs-lookup"><span data-stu-id="a0211-132">Create a custom app permission policy</span></span>

<span data-ttu-id="a0211-133">Если вы хотите управлять приложения, доступные для различных групп пользователей в вашей организации, создайте и назначьте одну или несколько политик разрешений пользовательское приложение.</span><span class="sxs-lookup"><span data-stu-id="a0211-133">If you want to control the apps that are available for different groups of users in your organization, create and assign one or more custom app permission policies.</span></span> <span data-ttu-id="a0211-134">Можно создать и назначить отдельные настраиваемых политик на основании ли приложения публикуются корпорацией Майкрософт, сторонние производители или вашей организации.</span><span class="sxs-lookup"><span data-stu-id="a0211-134">You can create and assign separate custom policies based on whether apps are published by Microsoft, third-parties, or your organization.</span></span> <span data-ttu-id="a0211-135">Важно знать, что после создания пользовательскую политику, изменить его нельзя в масштабе организации параметры при отключении приложений сторонних производителей.</span><span class="sxs-lookup"><span data-stu-id="a0211-135">It's important to know that after you create a custom policy, you can't change it if third-party apps are disabled in org-wide settings.</span></span> 

1. <span data-ttu-id="a0211-136">В левой области переходов центра администрирования группами Майкрософт, перейдите к **группам приложения** > **политики разрешений**.</span><span class="sxs-lookup"><span data-stu-id="a0211-136">In the left navigation of the Microsoft Teams admin center, go to **Teams app** > **Permission policies**.</span></span>
2. <span data-ttu-id="a0211-137">Выберите **новую политику**.</span><span class="sxs-lookup"><span data-stu-id="a0211-137">Select **New policy**.</span></span>
    <span data-ttu-id="a0211-138">![Снимок экрана новую политику разрешений приложения](media/app-permission-policies-new-policy.png)</span><span class="sxs-lookup"><span data-stu-id="a0211-138">![Screen shot of new app permission policy](media/app-permission-policies-new-policy.png)</span></span>
3. <span data-ttu-id="a0211-139">Введите описательное имя для политики.</span><span class="sxs-lookup"><span data-stu-id="a0211-139">Enter a descriptive name for the policy.</span></span>
4. <span data-ttu-id="a0211-140">В разделе **приложений Microsoft**, **приложений сторонних производителей**и **приложения клиента**выберите один из следующих:</span><span class="sxs-lookup"><span data-stu-id="a0211-140">Under **Microsoft apps**, **Third-party apps**, and **Tenant apps**, select one of the following:</span></span>

    - <span data-ttu-id="a0211-141">**Разрешить всем приложениям**</span><span class="sxs-lookup"><span data-stu-id="a0211-141">**Allow all apps**</span></span>
    - <span data-ttu-id="a0211-142">**Разрешать конкретных приложений и заблокировать все остальные**</span><span class="sxs-lookup"><span data-stu-id="a0211-142">**Allow specific apps and block all others**</span></span>
    - <span data-ttu-id="a0211-143">**Блокировать определенных приложений и разрешить всем другим пользователям**</span><span class="sxs-lookup"><span data-stu-id="a0211-143">**Block specific apps and allow all others**</span></span>
    - <span data-ttu-id="a0211-144">**Блокировать все приложения**</span><span class="sxs-lookup"><span data-stu-id="a0211-144">**Block all apps**</span></span>

5. <span data-ttu-id="a0211-145">Если выбран вариант **разрешить конкретные приложения и блокировка других пользователей**, добавьте приложения, которые необходимо разрешить:</span><span class="sxs-lookup"><span data-stu-id="a0211-145">If you selected **Allow specific apps and block others**, add the apps that you want to allow:</span></span>

    1. <span data-ttu-id="a0211-146">Установите флажок **Разрешить приложений**.</span><span class="sxs-lookup"><span data-stu-id="a0211-146">Select **Allow apps**.</span></span>
    1. <span data-ttu-id="a0211-147">Поиск для приложений, которые необходимо разрешить, а затем нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="a0211-147">Search for the apps that you want to allow, and then click **Add**.</span></span> <span data-ttu-id="a0211-148">Результаты поиска фильтруются для издателя приложения (**приложений Microsoft**, **приложений сторонних производителей**или **приложения клиента**).</span><span class="sxs-lookup"><span data-stu-id="a0211-148">The search results are filtered to the app publisher (**Microsoft apps**, **Third-party apps**, or **Tenant apps**).</span></span>
    1. <span data-ttu-id="a0211-149">Если вы выбрали список приложений, нажмите кнопку **Разрешить**.</span><span class="sxs-lookup"><span data-stu-id="a0211-149">When you've chosen the list of apps, click **Allow**.</span></span>

6. <span data-ttu-id="a0211-150">Аналогично Если вы выбрали **адресов конкретные приложения и все остальные**, поиск и добавлять приложения, которые нужно заблокировать.</span><span class="sxs-lookup"><span data-stu-id="a0211-150">Similarly, if you selected **Block specific apps and allow all others**, search for and add the apps that you want to block.</span></span>
7. <span data-ttu-id="a0211-151">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="a0211-151">Click **Save**.</span></span>

## <a name="edit-an-app-permission-policy"></a><span data-ttu-id="a0211-152">Изменение политики разрешений приложения</span><span class="sxs-lookup"><span data-stu-id="a0211-152">Edit an app permission policy</span></span>

<span data-ttu-id="a0211-153">Можно использовать Центр администрирования группами Майкрософт для изменения политики, включая глобальной политики (по умолчанию в масштабах организации) и настраиваемых политик, которые вы создаете.</span><span class="sxs-lookup"><span data-stu-id="a0211-153">You can use the Microsoft Teams admin center to edit a policy, including the global (Org-wide default) policy and custom policies that you create.</span></span> 

1. <span data-ttu-id="a0211-154">В левой области переходов центра администрирования группами Майкрософт, перейдите к **группам приложения** > **политики разрешений**.</span><span class="sxs-lookup"><span data-stu-id="a0211-154">In the left navigation of the Microsoft Teams admin center, go to **Teams app** > **Permission policies**.</span></span>
2. <span data-ttu-id="a0211-155">Выберите политику, которую требуется изменить.</span><span class="sxs-lookup"><span data-stu-id="a0211-155">Select the policy you want to edit.</span></span>
3. <span data-ttu-id="a0211-156">Здесь внесите изменения, которые будут.</span><span class="sxs-lookup"><span data-stu-id="a0211-156">From here, make the changes that you want.</span></span> <span data-ttu-id="a0211-157">Можно управлять параметрами на основании издателя приложения и добавлять и удалять приложения на основе параметра разрешенных и запрещенных.</span><span class="sxs-lookup"><span data-stu-id="a0211-157">You can manage settings based on the app publisher and add and remove apps based on the allow/block setting.</span></span>
4. <span data-ttu-id="a0211-158">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="a0211-158">Click **Save**.</span></span>

## <a name="assign-a-custom-app-permission-policy-to-users"></a><span data-ttu-id="a0211-159">Назначение политики разрешений пользовательское приложение для пользователей</span><span class="sxs-lookup"><span data-stu-id="a0211-159">Assign a custom app permission policy to users</span></span>

<span data-ttu-id="a0211-160">Можно использовать Центр администрирования группами Майкрософт назначение настраиваемая политика для отдельных пользователей или Скайп для модуль Business PowerShell, чтобы назначить пользовательскую политику к нескольким пользователям, например всех пользователей в группу безопасности или группу рассылки.</span><span class="sxs-lookup"><span data-stu-id="a0211-160">You can use the Microsoft Teams admin center to assign a custom policy to individual users or the Skype for Business PowerShell module to assign a custom policy to multiple users, such as all users in a security group or distribution group.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a0211-161">Рекомендуется только для назначения политик для пользователей, используя PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a0211-161">We recommend using PowerShell only to assign policies to users.</span></span> <span data-ttu-id="a0211-162">Использование центра администрирования группами Майкрософт для создания, редактирования и управление политиками.</span><span class="sxs-lookup"><span data-stu-id="a0211-162">Use the Microsoft Teams admin center to create, edit, and manage policies.</span></span>

### <a name="assign-a-custom-app-permission-policy-to-individual-users"></a><span data-ttu-id="a0211-163">Назначение политики разрешений пользовательское приложение для отдельных пользователей</span><span class="sxs-lookup"><span data-stu-id="a0211-163">Assign a custom app permission policy to individual users</span></span>

1. <span data-ttu-id="a0211-164">В левой области переходов центра администрирования группами Майкрософт перейдите к **пользователям**и нажмите кнопку пользователя.</span><span class="sxs-lookup"><span data-stu-id="a0211-164">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click the user.</span></span>
2. <span data-ttu-id="a0211-165">Рядом с пунктом **назначения политик**и выберите **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="a0211-165">Next to **Assigned policies**, choose **Edit**.</span></span>
3. <span data-ttu-id="a0211-166">В разделе **Политика разрешений приложения**выберите политику разрешений приложения, которые необходимо назначить и нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="a0211-166">Under **App permission policy**, select the app permission policy you want to assign, and then choose **Save**.</span></span>

    ![приложение-программы установки разрешение assign-policy.png](media/app-permission-policies-assign-policy.png)

<span data-ttu-id="a0211-168">Можно также назначить политику разрешений приложения к одному или нескольким пользователям следующим образом:</span><span class="sxs-lookup"><span data-stu-id="a0211-168">You can also assign an app permission policy to one or more users as follows:</span></span>

1. <span data-ttu-id="a0211-169">Перейдите в **Центр администрирования группами Майкрософт** > **группами приложений** > **политики разрешений**.</span><span class="sxs-lookup"><span data-stu-id="a0211-169">Go to **Microsoft Teams admin center** > **Teams apps** > **Permission policies**.</span></span>
2. <span data-ttu-id="a0211-170">Выберите политику, нажав кнопку слева от имени политики.</span><span class="sxs-lookup"><span data-stu-id="a0211-170">Select the policy by clicking to the left of the policy name.</span></span>
3. <span data-ttu-id="a0211-171">Выберите **Управление пользователями**.</span><span class="sxs-lookup"><span data-stu-id="a0211-171">Select **Manage users**.</span></span>
4. <span data-ttu-id="a0211-172">В области **Управление пользователями** поиска для пользователя по отображаемому имени или по имени пользователя, выберите имя и выберите команду **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="a0211-172">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then select **Add**.</span></span> <span data-ttu-id="a0211-173">Повторите этот шаг для каждого пользователя, который вы хотите добавить.</span><span class="sxs-lookup"><span data-stu-id="a0211-173">Repeat this step for each user that you want to add.</span></span>
5. <span data-ttu-id="a0211-174">Завершив добавление пользователей, выберите команду **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="a0211-174">When you are finished adding users, select **Save**.</span></span>
 

### <a name="assign-a-custom-app-permission-policy-to-users-in-a-group"></a><span data-ttu-id="a0211-175">Назначение политики разрешений пользовательское приложение для пользователей в группы</span><span class="sxs-lookup"><span data-stu-id="a0211-175">Assign a custom app permission policy to users in a group</span></span>

<span data-ttu-id="a0211-176">Можно назначить политику разрешений пользовательское приложение к нескольким пользователям, которые уже определен.</span><span class="sxs-lookup"><span data-stu-id="a0211-176">You may want to assign a custom app permission policy to multiple users that you’ve already identified.</span></span> <span data-ttu-id="a0211-177">Например можно назначить политики для всех пользователей в группу безопасности.</span><span class="sxs-lookup"><span data-stu-id="a0211-177">For example, you may want to assign a policy to all users in a security group.</span></span> <span data-ttu-id="a0211-178">Это можно сделать, подключение к Azure Active Directory PowerShell для модуля график и Скайп для модуль PowerShell бизнеса.</span><span class="sxs-lookup"><span data-stu-id="a0211-178">You can do this by connecting to the Azure Active Directory PowerShell for Graph module and the Skype for Business PowerShell module.</span></span> <span data-ttu-id="a0211-179">Дополнительные сведения об использовании PowerShell для управления группами см [Команды PowerShell](teams-powershell-overview.md).</span><span class="sxs-lookup"><span data-stu-id="a0211-179">For more information about using PowerShell to manage Teams, see [Teams PowerShell Overview](teams-powershell-overview.md).</span></span>

<span data-ttu-id="a0211-180">В этом примере назначить политику разрешений пользовательское приложение, называется политика разрешений приложения отдела Кадров для всех пользователей в группу проекта Contoso Pharmaceuticals отдела Кадров.</span><span class="sxs-lookup"><span data-stu-id="a0211-180">In this example, we assign a custom app permission policy called HR App Permission Policy to all users in the Contoso Pharmaceuticals HR Project group.</span></span>  

> [!NOTE]
> <span data-ttu-id="a0211-181">Убедитесь, что подключение сначала для Azure Active Directory PowerShell для модуля график и Скайп для модуль Business PowerShell, выполнив действия, описанные в [подключиться ко всем службам Office 365 в одном окне Windows PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).</span><span class="sxs-lookup"><span data-stu-id="a0211-181">Make sure you first connect to the Azure Active Directory PowerShell for Graph module and Skype for Business PowerShell module by following the steps in [Connect to all Office 365 services in a single Windows PowerShell window](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).</span></span>

<span data-ttu-id="a0211-182">Получите GroupObjectId конкретной группы.</span><span class="sxs-lookup"><span data-stu-id="a0211-182">Get the GroupObjectId of the particular group.</span></span>
```
$group = Get-AzureADGroup -SearchString "Contoso Pharmaceuticals HR Project"
```
<span data-ttu-id="a0211-183">Получение элементов из указанной группы.</span><span class="sxs-lookup"><span data-stu-id="a0211-183">Get the members of the specified group.</span></span>
```
$members = Get-AzureADGroupMember -ObjectId $group.ObjectId -All $true | Where-Object {$_.ObjectType -eq "User"}
```
<span data-ttu-id="a0211-184">Назначьте всем пользователям в группе политика разрешений определенного приложения.</span><span class="sxs-lookup"><span data-stu-id="a0211-184">Assign all users in the group to a particular app permission policy.</span></span> <span data-ttu-id="a0211-185">В этом примере это политика разрешений приложения отдела Кадров.</span><span class="sxs-lookup"><span data-stu-id="a0211-185">In this example, it's HR App Permission Policy.</span></span>
```
$members | ForEach-Object { Grant-CsTeamsAppPermissionPolicy -PolicyName "HR App Permission Policy" -Identity $_.EmailAddress}
``` 
<span data-ttu-id="a0211-186">В зависимости от числа членов группы эта команда может занять несколько минут для выполнения.</span><span class="sxs-lookup"><span data-stu-id="a0211-186">Depending on the number of members in the group, this command may take several minutes to execute.</span></span>

## <a name="faq"></a><span data-ttu-id="a0211-187">Вопросы и ответы</span><span class="sxs-lookup"><span data-stu-id="a0211-187">FAQ</span></span>

### <a name="working-with-app-permission-policies"></a><span data-ttu-id="a0211-188">Работа с политиками разрешений приложения</span><span class="sxs-lookup"><span data-stu-id="a0211-188">Working with app permission policies</span></span>

#### <a name="can-i-control-line-of-business-lob-apps"></a><span data-ttu-id="a0211-189">Можно управлять бизнес-приложения</span><span class="sxs-lookup"><span data-stu-id="a0211-189">Can I control line of business (LOB) apps?</span></span>

<span data-ttu-id="a0211-190">Да, можно использовать политики разрешений приложения для контроля развертывания и распространения пользовательских приложений (LOB).</span><span class="sxs-lookup"><span data-stu-id="a0211-190">Yes, you can use app permission policies to control the rollout and distribution of custom (LOB) apps.</span></span>

#### <a name="how-do-app-permission-policies-relate-to-pinned-apps-and-app-setup-policies"></a><span data-ttu-id="a0211-191">Как связаны политики разрешений приложения в закрепленных приложения и политик настройки приложения?</span><span class="sxs-lookup"><span data-stu-id="a0211-191">How do app permission policies relate to pinned apps and app setup policies?</span></span>

<span data-ttu-id="a0211-192">Можно использовать политики в отношении установки приложений вместе с политиками разрешений приложения.</span><span class="sxs-lookup"><span data-stu-id="a0211-192">You can use app setup policies together with app permission policies.</span></span> <span data-ttu-id="a0211-193">Предварительно закрепленных приложений выбираются из набора включенных приложений для пользователя.</span><span class="sxs-lookup"><span data-stu-id="a0211-193">Pre-pinned apps are selected from the set of enabled apps for a user.</span></span> <span data-ttu-id="a0211-194">Кроме того Если пользователь имеет политику разрешений приложения, который блокирует приложения в политику установки приложения, это приложение не будет отображаться в группах.</span><span class="sxs-lookup"><span data-stu-id="a0211-194">Additionally, if a user has an app permission policy that blocks an app in their app setup policy, that app won't appear in Teams.</span></span>

#### <a name="can-i-use-app-permission-policies-to-restrict-uploading-custom-apps-also-known-as-sideloading"></a><span data-ttu-id="a0211-195">Можно ли использовать политики разрешений приложения запретить отправку настраиваемые приложения (также известной как sideloading)?</span><span class="sxs-lookup"><span data-stu-id="a0211-195">Can I use app permission policies to restrict uploading custom apps (also known as sideloading)?</span></span>

<span data-ttu-id="a0211-196">Для получения дополнительных сведений об ограничении загрузки настраиваемые приложения, просмотрите [Управление пользовательское приложение политики и параметры в группах](teams-custom-app-policies-and-settings.md).</span><span class="sxs-lookup"><span data-stu-id="a0211-196">To learn more about how to restrict uploading custom apps, see [Manage custom app policies and settings in Teams](teams-custom-app-policies-and-settings.md).</span></span>

#### <a name="how-long-does-it-take-for-policy-changes-to-take-effect"></a><span data-ttu-id="a0211-197">Сколько времени для изменения политики вступили в силу?</span><span class="sxs-lookup"><span data-stu-id="a0211-197">How long does it take for policy changes to take effect?</span></span>

<span data-ttu-id="a0211-198">Изменить глобальную политику или назначение политики для пользователей, может потребоваться до 24 часов для изменения вступили в силу.</span><span class="sxs-lookup"><span data-stu-id="a0211-198">After you edit the global policy or assign a policy to users, it can take up to 24 hours for changes to take effect.</span></span> <span data-ttu-id="a0211-199">Параметры приложения в масштабе организации вступили в силу немедленно.</span><span class="sxs-lookup"><span data-stu-id="a0211-199">Org-wide app settings take effect immediately.</span></span>

#### <a name="does-blocking-an-app-apply-to-teams-mobile-clients"></a><span data-ttu-id="a0211-200">Блокировка приложения применяется к группам мобильных клиентов?</span><span class="sxs-lookup"><span data-stu-id="a0211-200">Does blocking an app apply to Teams mobile clients?</span></span>

<span data-ttu-id="a0211-201">Да, при блокировании приложения это приложение блокируется для всех групп клиентов.</span><span class="sxs-lookup"><span data-stu-id="a0211-201">Yes, when you block an app, that app is blocked across all Teams clients.</span></span>  

### <a name="user-experience"></a><span data-ttu-id="a0211-202">Взаимодействие с пользователем</span><span class="sxs-lookup"><span data-stu-id="a0211-202">User experience</span></span>

#### <a name="what-does-a-user-experience-when-an-app-is-blocked"></a><span data-ttu-id="a0211-203">Что взаимодействие с пользователем при блокировании приложения?</span><span class="sxs-lookup"><span data-stu-id="a0211-203">What does a user experience when an app is blocked?</span></span>

<span data-ttu-id="a0211-204">Пользователи не могут взаимодействовать с заблокированные приложения или свои возможности, такие программы-роботы, вкладок и расширения системы обмена сообщениями.</span><span class="sxs-lookup"><span data-stu-id="a0211-204">Users can't interact with a blocked app or its capabilities, such bots, tabs, and messaging extensions.</span></span> <span data-ttu-id="a0211-205">В общего контекста, такие как группы или группы чата программы-роботы по-прежнему могут отправлять сообщения всем участникам этого контекста.</span><span class="sxs-lookup"><span data-stu-id="a0211-205">In a shared context, such as a team or group chat, bots can still send messages to all participants of that context.</span></span> <span data-ttu-id="a0211-206">Группы указывает пользователя при блокировании приложения.</span><span class="sxs-lookup"><span data-stu-id="a0211-206">Teams indicates to the user when an app is blocked.</span></span> 

<span data-ttu-id="a0211-207">Например приложения заблокирована, пользователям не удается одной из следующих:</span><span class="sxs-lookup"><span data-stu-id="a0211-207">For example, when an app is blocked, users can't do any of the following:</span></span>

- <span data-ttu-id="a0211-208">Добавить приложение, раскрывающие личность или беседы или группы</span><span class="sxs-lookup"><span data-stu-id="a0211-208">Add the app personally or to a chat or team</span></span>
- <span data-ttu-id="a0211-209">Отправлять сообщения в приложении программа-робот</span><span class="sxs-lookup"><span data-stu-id="a0211-209">Send messages to the app’s bot</span></span>
- <span data-ttu-id="a0211-210">Выполнение действия кнопки, которые отправляют данные обратно в приложения, например предусматривающей действие сообщения</span><span class="sxs-lookup"><span data-stu-id="a0211-210">Perform button actions that send information back to the app, such as actionable messages</span></span>  
- <span data-ttu-id="a0211-211">Вкладка приложения</span><span class="sxs-lookup"><span data-stu-id="a0211-211">View the app’s tab</span></span>
- <span data-ttu-id="a0211-212">Настройка соединителей для получения уведомлений</span><span class="sxs-lookup"><span data-stu-id="a0211-212">Set up connectors to receive notifications</span></span>
- <span data-ttu-id="a0211-213">Использование расширения приложения обмена сообщениями</span><span class="sxs-lookup"><span data-stu-id="a0211-213">Use the app’s messaging extension</span></span>

 ## <a name="related-topics"></a><span data-ttu-id="a0211-214">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="a0211-214">Related topics</span></span>
- [<span data-ttu-id="a0211-215">Параметры администратора для приложений в Teams</span><span class="sxs-lookup"><span data-stu-id="a0211-215">Admin settings for apps in Teams</span></span>](admin-settings.md)
- [<span data-ttu-id="a0211-216">Управление политиками настройки приложений в Teams</span><span class="sxs-lookup"><span data-stu-id="a0211-216">Manage app setup policies in Teams</span></span>](teams-app-setup-policies.md)
- [<span data-ttu-id="a0211-217">Управление пользовательскими политиками и параметрами приложений в Teams</span><span class="sxs-lookup"><span data-stu-id="a0211-217">Manage custom app policies and settings in Teams</span></span>](teams-custom-app-policies-and-settings.md)
