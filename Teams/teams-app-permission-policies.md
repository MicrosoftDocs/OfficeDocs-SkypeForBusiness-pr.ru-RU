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
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Узнайте о политиках разрешений приложений в Microsoft Teams и о том, как их использовать для управления доступными для пользователей в вашей организации приложениями.
f1keywords:
- ms.teamsadmincenter.apppolicies.overview
ms.openlocfilehash: d15346370015843eeb497cce7fa85928e77c96d9
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34298893"
---
# <a name="manage-app-permission-policies-in-microsoft-teams"></a><span data-ttu-id="12067-103">Управление политиками разрешений для приложений в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="12067-103">Manage app permission policies in Microsoft Teams</span></span>

> [!INCLUDE [feature coming soon](includes/new-feature-coming-soon-article.md)]

<span data-ttu-id="12067-104">Администраторы могут управлять тем, какие приложения доступны пользователям Microsoft Teams в Организации, с помощью политик разрешений приложений.</span><span class="sxs-lookup"><span data-stu-id="12067-104">As an admin, you can use app permission policies to control what apps are available to Microsoft Teams users in your organization.</span></span> <span data-ttu-id="12067-105">Вы можете разрешить или заблокировать все приложения или отдельные приложения, опубликованные корпорацией Майкрософт, сторонними организациями и вашей организацией.</span><span class="sxs-lookup"><span data-stu-id="12067-105">You can allow or block all apps or specific apps published by Microsoft, third-parties, and your organization.</span></span> <span data-ttu-id="12067-106">Когда вы блокируете приложение, пользователи не смогут установить его из магазина приложений Teams.</span><span class="sxs-lookup"><span data-stu-id="12067-106">When you block an app, users are unable to install it from the Teams app store.</span></span>

<span data-ttu-id="12067-107">Управление политиками разрешений на доступ к приложениям осуществляется в центре администрирования Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="12067-107">You manage app permission policies in the Microsoft Teams admin center.</span></span> <span data-ttu-id="12067-108">Вы можете применить параметры для всей Организации, использовать глобальную политику (по умолчанию на уровне Организации), а также создавать и назначать пользовательские политики отдельным пользователям или пользователям в группе.</span><span class="sxs-lookup"><span data-stu-id="12067-108">You can apply settings org-wide, use the global (Org-wide default) policy, and create and assign custom policies to individual users or users in a group.</span></span>  

![Снимок экрана с политикой разрешений на доступ к приложениям](media/app-permission-policies.png)

> [!NOTE]
> <span data-ttu-id="12067-110">Пользователи в вашей организации автоматически получат глобальную политику, если вы не создадите и не назначаете пользовательскую политику.</span><span class="sxs-lookup"><span data-stu-id="12067-110">Users in your organization will automatically get the global policy unless you create and assign a custom policy.</span></span> <span data-ttu-id="12067-111">Параметры приложения в масштабе организации переопределяют глобальную политику и любые пользовательские политики, которые вы создаете и назначаете пользователям.</span><span class="sxs-lookup"><span data-stu-id="12067-111">Org-wide app settings override the global policy and any custom policies that you create and assign to users.</span></span>

<span data-ttu-id="12067-112">Например, предположим, что вы хотите заблокировать все сторонние приложения и разрешить определенным приложениям из Microsoft для отдела кадров в Организации.</span><span class="sxs-lookup"><span data-stu-id="12067-112">Say, for example, you want to block all third-party apps and allow specific apps from Microsoft for the HR team in your organization.</span></span> <span data-ttu-id="12067-113">Вы должны создать пользовательскую политику с именем "политика разрешений на управление персоналом", настроить блокировку и разрешить нужные вам приложения, а затем назначить ее пользователям в группе отдела кадров.</span><span class="sxs-lookup"><span data-stu-id="12067-113">You would create a custom policy named HR App Permission Policy, set it to block and allow the apps that you want, and then assign it to users on the HR team.</span></span>

## <a name="manage-org-wide-app-settings"></a><span data-ttu-id="12067-114">Управление параметрами приложения в масштабе Организации</span><span class="sxs-lookup"><span data-stu-id="12067-114">Manage org-wide app settings</span></span>

<span data-ttu-id="12067-115">С помощью параметров приложения в масштабе организации можно управлять тем, какие приложения доступны для всех организаций.</span><span class="sxs-lookup"><span data-stu-id="12067-115">Use org-wide app settings to control which apps are available across your organization.</span></span> <span data-ttu-id="12067-116">Параметры приложения в масштабах организации определяют поведение всех пользователей и переопределяют любые другие политики разрешений приложений, назначенные пользователям.</span><span class="sxs-lookup"><span data-stu-id="12067-116">Org-wide app settings govern the behavior for all users and override any other app permission policies assigned to users.</span></span> <span data-ttu-id="12067-117">Параметры приложения на уровне Организации вступают в силу немедленно, и их можно использовать для управления вредоносными или проблематичными приложениями.</span><span class="sxs-lookup"><span data-stu-id="12067-117">Org-wide app settings take effect immediately and you can use them to control malicious or problematic apps.</span></span>

1. <span data-ttu-id="12067-118">В левой области навигации центра администрирования Microsoft Teams перейдите в раздел**политики разрешений** **приложения** > Teams.</span><span class="sxs-lookup"><span data-stu-id="12067-118">In the left navigation of the Microsoft Teams admin center, go to **Teams app** > **Permission policies**.</span></span>
2. <span data-ttu-id="12067-119">Выберите **параметр "Параметры организации**".</span><span class="sxs-lookup"><span data-stu-id="12067-119">Select **Org-wide settings**.</span></span> <span data-ttu-id="12067-120">Затем вы можете настроить нужные параметры на панели.</span><span class="sxs-lookup"><span data-stu-id="12067-120">You can then configure the settings you want in the panel.</span></span> 
<span data-ttu-id="12067-121">![Снимок экрана: параметры приложения в масштабах Организации](media/app-permission-policies-org-wide-settings.png)</span><span class="sxs-lookup"><span data-stu-id="12067-121">![Screen shot of org-wide app settings](media/app-permission-policies-org-wide-settings.png)</span></span>
3. <span data-ttu-id="12067-122">В **приложениях сторонних разработчиков**отключите или включите эти параметры для управления доступом к сторонним приложениям.</span><span class="sxs-lookup"><span data-stu-id="12067-122">Under **Third-party apps**, turn off or turn on these settings to control access to third-party apps:</span></span>

    - <span data-ttu-id="12067-123">**Разрешать сторонние приложения в Teams**: определяет, могут ли пользователи использовать сторонние приложения.</span><span class="sxs-lookup"><span data-stu-id="12067-123">**Allow third-party apps in Teams**: This controls whether users can use third-party apps.</span></span>
    - <span data-ttu-id="12067-124">**Разрешать новые сторонние приложения**, опубликованные в магазине по умолчанию: это определяет, будут ли новые сторонние приложения, опубликованные в магазине приложений Teams, автоматически доступны в Teams.</span><span class="sxs-lookup"><span data-stu-id="12067-124">**Allow any new third-party apps published to the store by default**: This controls whether new third-party apps that are published to the Teams app store become automatically available in Teams.</span></span> <span data-ttu-id="12067-125">Вы можете настроить этот параметр, только если вы разрешите сторонним приложениям.</span><span class="sxs-lookup"><span data-stu-id="12067-125">You can only set this option if you allow third-party apps.</span></span>

4. <span data-ttu-id="12067-126">В разделе **пользовательские приложения**отключите или включите **параметр Разрешить взаимодействие с пользовательскими приложениями**.</span><span class="sxs-lookup"><span data-stu-id="12067-126">Under **Custom apps**, turn off or turn on **Allow interaction with custom apps**.</span></span> <span data-ttu-id="12067-127">Этот параметр определяет, могут ли пользователи взаимодействовать с пользовательскими приложениями (неопубликованного).</span><span class="sxs-lookup"><span data-stu-id="12067-127">This setting controls whether users can interact with custom (sideloaded) apps.</span></span> <span data-ttu-id="12067-128">Имейте в виду, что это отличается от разрешения пользователям *отправлять* пользовательские приложения.</span><span class="sxs-lookup"><span data-stu-id="12067-128">Keep in mind that this is different from allowing users to *upload* custom apps.</span></span>
5. <span data-ttu-id="12067-129">В разделе **Заблокированные приложения**найдите и добавьте приложения, которые вы хотите заблокировать для всей Организации.</span><span class="sxs-lookup"><span data-stu-id="12067-129">Under **Blocked apps**, search for and add the apps that you want to block across your organization.</span></span> <span data-ttu-id="12067-130">Вы можете выбрать приложения из каталога приложений клиента или из магазина приложений Teams.</span><span class="sxs-lookup"><span data-stu-id="12067-130">You can choose apps from the tenant app catalog or the Teams app store.</span></span>
6. <span data-ttu-id="12067-131">Выберите команду **сохранить** для параметров приложения на уровне Организации, чтобы они вступили в силу.</span><span class="sxs-lookup"><span data-stu-id="12067-131">Click **Save** for org-wide app settings to take effect.</span></span>

## <a name="create-a-custom-app-permission-policy"></a><span data-ttu-id="12067-132">Создание настраиваемой политики разрешений для приложений</span><span class="sxs-lookup"><span data-stu-id="12067-132">Create a custom app permission policy</span></span>

<span data-ttu-id="12067-133">Если вы хотите управлять приложениями, доступными для разных групп пользователей в Организации, создайте и назначьте одну или несколько настраиваемых политик разрешений для приложений.</span><span class="sxs-lookup"><span data-stu-id="12067-133">If you want to control the apps that are available for different groups of users in your organization, create and assign one or more custom app permission policies.</span></span> <span data-ttu-id="12067-134">Вы можете создавать и назначать отдельные пользовательские политики в зависимости от того, публикуются ли приложения корпорацией Майкрософт, сторонними организациями или в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="12067-134">You can create and assign separate custom policies based on whether apps are published by Microsoft, third-parties, or your organization.</span></span> <span data-ttu-id="12067-135">Важно знать, что после создания настраиваемой политики вы не можете изменить ее, если сторонние приложения отключены в параметрах всей Организации.</span><span class="sxs-lookup"><span data-stu-id="12067-135">It's important to know that after you create a custom policy, you can't change it if third-party apps are disabled in org-wide settings.</span></span> 

1. <span data-ttu-id="12067-136">В левой области навигации центра администрирования Microsoft Teams перейдите в раздел**политики разрешений** **приложения** > Teams.</span><span class="sxs-lookup"><span data-stu-id="12067-136">In the left navigation of the Microsoft Teams admin center, go to **Teams app** > **Permission policies**.</span></span>
2. <span data-ttu-id="12067-137">Выберите пункт **создать политику**.</span><span class="sxs-lookup"><span data-stu-id="12067-137">Select **New policy**.</span></span>
    <span data-ttu-id="12067-138">![Снимок экрана с новой политикой разрешений на доступ к приложениям](media/app-permission-policies-new-policy.png)</span><span class="sxs-lookup"><span data-stu-id="12067-138">![Screen shot of new app permission policy](media/app-permission-policies-new-policy.png)</span></span>
3. <span data-ttu-id="12067-139">Введите описательное имя для политики.</span><span class="sxs-lookup"><span data-stu-id="12067-139">Enter a descriptive name for the policy.</span></span>
4. <span data-ttu-id="12067-140">В разделе **приложения Microsoft**, сторонние **приложения**и **приложения клиента**выберите один из указанных ниже вариантов.</span><span class="sxs-lookup"><span data-stu-id="12067-140">Under **Microsoft apps**, **Third-party apps**, and **Tenant apps**, select one of the following:</span></span>

    - <span data-ttu-id="12067-141">**Разрешить все приложения**</span><span class="sxs-lookup"><span data-stu-id="12067-141">**Allow all apps**</span></span>
    - <span data-ttu-id="12067-142">**Разрешать определенные приложения и блокировать всех других приложений**</span><span class="sxs-lookup"><span data-stu-id="12067-142">**Allow specific apps and block all others**</span></span>
    - <span data-ttu-id="12067-143">**Блокировка конкретных приложений и предоставление другим пользователям**</span><span class="sxs-lookup"><span data-stu-id="12067-143">**Block specific apps and allow all others**</span></span>
    - <span data-ttu-id="12067-144">**Блокировать все приложения**</span><span class="sxs-lookup"><span data-stu-id="12067-144">**Block all apps**</span></span>

5. <span data-ttu-id="12067-145">Если вы выбрали **разрешить определенные приложения и заблокировать других**, добавьте приложения, которые вы хотите разрешить:</span><span class="sxs-lookup"><span data-stu-id="12067-145">If you selected **Allow specific apps and block others**, add the apps that you want to allow:</span></span>

    1. <span data-ttu-id="12067-146">Выберите **Разрешить приложения**.</span><span class="sxs-lookup"><span data-stu-id="12067-146">Select **Allow apps**.</span></span>
    1. <span data-ttu-id="12067-147">Найдите приложения, которые вы хотите разрешить, и нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="12067-147">Search for the apps that you want to allow, and then click **Add**.</span></span> <span data-ttu-id="12067-148">Результаты поиска отфильтрованы по издателю приложения (**приложения Майкрософт**, сторонние **приложения**или **приложения клиента**).</span><span class="sxs-lookup"><span data-stu-id="12067-148">The search results are filtered to the app publisher (**Microsoft apps**, **Third-party apps**, or **Tenant apps**).</span></span>
    1. <span data-ttu-id="12067-149">Выбрав список приложений, нажмите кнопку **Разрешить**.</span><span class="sxs-lookup"><span data-stu-id="12067-149">When you've chosen the list of apps, click **Allow**.</span></span>

6. <span data-ttu-id="12067-150">Аналогичным образом, если вы выбрали **блокировать определенные приложения и разрешите все другие**, выполните поиск и добавьте приложения, которые вы хотите заблокировать.</span><span class="sxs-lookup"><span data-stu-id="12067-150">Similarly, if you selected **Block specific apps and allow all others**, search for and add the apps that you want to block.</span></span>
7. <span data-ttu-id="12067-151">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="12067-151">Click **Save**.</span></span>

## <a name="edit-an-app-permission-policy"></a><span data-ttu-id="12067-152">Изменение политики разрешений на доступ к приложению</span><span class="sxs-lookup"><span data-stu-id="12067-152">Edit an app permission policy</span></span>

<span data-ttu-id="12067-153">Вы можете использовать центр администрирования Microsoft Teams для изменения политики, включая глобальную политику (параметры по умолчанию на уровне Организации) и созданные пользовательские политики.</span><span class="sxs-lookup"><span data-stu-id="12067-153">You can use the Microsoft Teams admin center to edit a policy, including the global (Org-wide default) policy and custom policies that you create.</span></span> 

1. <span data-ttu-id="12067-154">В левой области навигации центра администрирования Microsoft Teams перейдите в раздел**политики разрешений** **приложения** > Teams.</span><span class="sxs-lookup"><span data-stu-id="12067-154">In the left navigation of the Microsoft Teams admin center, go to **Teams app** > **Permission policies**.</span></span>
2. <span data-ttu-id="12067-155">Выберите политику, которую вы хотите изменить.</span><span class="sxs-lookup"><span data-stu-id="12067-155">Select the policy you want to edit.</span></span>
3. <span data-ttu-id="12067-156">В этой статье внесите необходимые изменения.</span><span class="sxs-lookup"><span data-stu-id="12067-156">From here, make the changes that you want.</span></span> <span data-ttu-id="12067-157">Вы можете управлять параметрами на основе издателя приложения, а также добавлять и удалять приложения в зависимости от параметра Разрешить/блокировать.</span><span class="sxs-lookup"><span data-stu-id="12067-157">You can manage settings based on the app publisher and add and remove apps based on the allow/block setting.</span></span>
4. <span data-ttu-id="12067-158">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="12067-158">Click **Save**.</span></span>

## <a name="assign-a-custom-app-permission-policy-to-users"></a><span data-ttu-id="12067-159">Назначение пользователям политики разрешений на доступ к приложениям</span><span class="sxs-lookup"><span data-stu-id="12067-159">Assign a custom app permission policy to users</span></span>

<span data-ttu-id="12067-160">Центр администрирования Microsoft Teams можно использовать для назначения настраиваемой политики отдельным пользователям или модулям Skype для бизнеса PowerShell для назначения особой политики нескольким пользователям, таким как все пользователи в группе безопасности или группе рассылки.</span><span class="sxs-lookup"><span data-stu-id="12067-160">You can use the Microsoft Teams admin center to assign a custom policy to individual users or the Skype for Business PowerShell module to assign a custom policy to multiple users, such as all users in a security group or distribution group.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="12067-161">Мы рекомендуем использовать PowerShell только для назначения политик пользователям.</span><span class="sxs-lookup"><span data-stu-id="12067-161">We recommend using PowerShell only to assign policies to users.</span></span> <span data-ttu-id="12067-162">С помощью центра администрирования Microsoft Teams можно создавать и изменять политики, а также управлять ими.</span><span class="sxs-lookup"><span data-stu-id="12067-162">Use the Microsoft Teams admin center to create, edit, and manage policies.</span></span>

### <a name="assign-a-custom-app-permission-policy-to-individual-users"></a><span data-ttu-id="12067-163">Назначение настраиваемой политики разрешений для отдельных пользователей</span><span class="sxs-lookup"><span data-stu-id="12067-163">Assign a custom app permission policy to individual users</span></span>

1. <span data-ttu-id="12067-164">В левой области навигации центра администрирования Microsoft Teams перейдите в раздел **Пользователи**и выберите пользователя.</span><span class="sxs-lookup"><span data-stu-id="12067-164">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click the user.</span></span>
2. <span data-ttu-id="12067-165">Рядом с пунктом **назначенные политики**нажмите кнопку **изменить**.</span><span class="sxs-lookup"><span data-stu-id="12067-165">Next to **Assigned policies**, choose **Edit**.</span></span>
3. <span data-ttu-id="12067-166">В разделе **политика разрешений приложения**выберите политику разрешений приложений, которую вы хотите назначить, и нажмите кнопку **сохранить**.</span><span class="sxs-lookup"><span data-stu-id="12067-166">Under **App permission policy**, select the app permission policy you want to assign, and then choose **Save**.</span></span>

    ![АПП-сетуп-пермиссион-ассигн-Полици. png](media/app-permission-policies-assign-policy.png)

<span data-ttu-id="12067-168">Вы также можете назначить политику разрешений приложения для одного или нескольких пользователей, выполнив указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="12067-168">You can also assign an app permission policy to one or more users as follows:</span></span>

1. <span data-ttu-id="12067-169">Перейдите в раздел >  **"центр администрирования Microsoft Teams"** в группе "**политики разрешений**для**приложений** > ".</span><span class="sxs-lookup"><span data-stu-id="12067-169">Go to **Microsoft Teams admin center** > **Teams apps** > **Permission policies**.</span></span>
2. <span data-ttu-id="12067-170">Выберите политику, щелкнув слева от имени политики.</span><span class="sxs-lookup"><span data-stu-id="12067-170">Select the policy by clicking to the left of the policy name.</span></span>
3. <span data-ttu-id="12067-171">Выберите **Управление пользователями**.</span><span class="sxs-lookup"><span data-stu-id="12067-171">Select **Manage users**.</span></span>
4. <span data-ttu-id="12067-172">В области **Управление пользователями** найдите пользователя по отображаемому имени или по имени пользователя, выберите имя и нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="12067-172">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then select **Add**.</span></span> <span data-ttu-id="12067-173">Повторите этот шаг для каждого пользователя, которого вы хотите добавить.</span><span class="sxs-lookup"><span data-stu-id="12067-173">Repeat this step for each user that you want to add.</span></span>
5. <span data-ttu-id="12067-174">Завершив добавление пользователей, нажмите кнопку **сохранить**.</span><span class="sxs-lookup"><span data-stu-id="12067-174">When you are finished adding users, select **Save**.</span></span>
 

### <a name="assign-a-custom-app-permission-policy-to-users-in-a-group"></a><span data-ttu-id="12067-175">Назначение пользователю политики разрешений на доступ к приложениям в группе</span><span class="sxs-lookup"><span data-stu-id="12067-175">Assign a custom app permission policy to users in a group</span></span>

<span data-ttu-id="12067-176">Вы можете назначить специальную политику разрешений приложения нескольким пользователям, которые уже были идентифицированы.</span><span class="sxs-lookup"><span data-stu-id="12067-176">You may want to assign a custom app permission policy to multiple users that you’ve already identified.</span></span> <span data-ttu-id="12067-177">Например, может потребоваться назначить политику всем пользователям в группе безопасности.</span><span class="sxs-lookup"><span data-stu-id="12067-177">For example, you may want to assign a policy to all users in a security group.</span></span> <span data-ttu-id="12067-178">Это можно сделать, подключив службу Azure Active Directory PowerShell для Graph и модуль PowerShell для Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="12067-178">You can do this by connecting to the Azure Active Directory PowerShell for Graph module and the Skype for Business PowerShell module.</span></span> <span data-ttu-id="12067-179">Дополнительные сведения об использовании PowerShell для управления группами можно найти в разделе [Общие сведения о Teams PowerShell](teams-powershell-overview.md).</span><span class="sxs-lookup"><span data-stu-id="12067-179">For more information about using PowerShell to manage Teams, see [Teams PowerShell Overview](teams-powershell-overview.md).</span></span>

<span data-ttu-id="12067-180">В этом примере мы назначаем политику разрешений на доступ к приложениям, которая называется политикой разрешений на управление персоналом, всем пользователям в группе сотрудников компании Contoso фабрика.</span><span class="sxs-lookup"><span data-stu-id="12067-180">In this example, we assign a custom app permission policy called HR App Permission Policy to all users in the Contoso Pharmaceuticals HR Project group.</span></span>  

> [!NOTE]
> <span data-ttu-id="12067-181">Убедитесь, что вы подключаетесь к модулю Azure Active Directory PowerShell для модуля Graph и Skype для бизнеса PowerShell, выполнив действия, описанные в разделе [подключение ко всем службам Office 365 в одном окне Windows PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).</span><span class="sxs-lookup"><span data-stu-id="12067-181">Make sure you first connect to the Azure Active Directory PowerShell for Graph module and Skype for Business PowerShell module by following the steps in [Connect to all Office 365 services in a single Windows PowerShell window](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).</span></span>

<span data-ttu-id="12067-182">Получить Граупобжектид определенной группы.</span><span class="sxs-lookup"><span data-stu-id="12067-182">Get the GroupObjectId of the particular group.</span></span>
```
$group = Get-AzureADGroup -SearchString "Contoso Pharmaceuticals HR Project"
```
<span data-ttu-id="12067-183">Получение участников указанной группы.</span><span class="sxs-lookup"><span data-stu-id="12067-183">Get the members of the specified group.</span></span>
```
$members = Get-AzureADGroupMember -ObjectId $group.ObjectId -All $true | Where-Object {$_.ObjectType -eq "User"}
```
<span data-ttu-id="12067-184">Назначьте всем пользователям в группе определенную политику разрешений приложения.</span><span class="sxs-lookup"><span data-stu-id="12067-184">Assign all users in the group to a particular app permission policy.</span></span> <span data-ttu-id="12067-185">В этом примере это политика разрешений на управление персоналом.</span><span class="sxs-lookup"><span data-stu-id="12067-185">In this example, it's HR App Permission Policy.</span></span>
```
$members | ForEach-Object { Grant-CsTeamsAppPermissionPolicy -PolicyName "HR App Permission Policy" -Identity $_.EmailAddress}
``` 
<span data-ttu-id="12067-186">Для выполнения этой команды может потребоваться несколько минут в зависимости от количества участников в группе.</span><span class="sxs-lookup"><span data-stu-id="12067-186">Depending on the number of members in the group, this command may take several minutes to execute.</span></span>

## <a name="faq"></a><span data-ttu-id="12067-187">Вопросы и ответы</span><span class="sxs-lookup"><span data-stu-id="12067-187">FAQ</span></span>

### <a name="working-with-app-permission-policies"></a><span data-ttu-id="12067-188">Работа с политиками разрешений приложений</span><span class="sxs-lookup"><span data-stu-id="12067-188">Working with app permission policies</span></span>

#### <a name="can-i-control-line-of-business-lob-apps"></a><span data-ttu-id="12067-189">Можно ли управлять бизнес-приложениями?</span><span class="sxs-lookup"><span data-stu-id="12067-189">Can I control line of business (LOB) apps?</span></span>

<span data-ttu-id="12067-190">Да, вы можете использовать политики разрешений приложений для управления развертыванием и распространением настраиваемых (LOB) приложений.</span><span class="sxs-lookup"><span data-stu-id="12067-190">Yes, you can use app permission policies to control the rollout and distribution of custom (LOB) apps.</span></span>

#### <a name="how-do-app-permission-policies-relate-to-pinned-apps-and-app-setup-policies"></a><span data-ttu-id="12067-191">Как политики разрешений приложений связаны с закрепленными приложениями и политиками настройки приложений?</span><span class="sxs-lookup"><span data-stu-id="12067-191">How do app permission policies relate to pinned apps and app setup policies?</span></span>

<span data-ttu-id="12067-192">Вы можете использовать политики настройки приложений вместе с политиками разрешений приложений.</span><span class="sxs-lookup"><span data-stu-id="12067-192">You can use app setup policies together with app permission policies.</span></span> <span data-ttu-id="12067-193">Предварительно закрепленные приложения выбираются из набора разрешенных приложений для пользователя.</span><span class="sxs-lookup"><span data-stu-id="12067-193">Pre-pinned apps are selected from the set of enabled apps for a user.</span></span> <span data-ttu-id="12067-194">Кроме того, если пользователь имеет политику разрешений приложения, которая блокирует приложение в политике настройки приложения, это приложение не будет отображаться в Teams.</span><span class="sxs-lookup"><span data-stu-id="12067-194">Additionally, if a user has an app permission policy that blocks an app in their app setup policy, that app won't appear in Teams.</span></span>

#### <a name="can-i-use-app-permission-policies-to-restrict-uploading-custom-apps-also-known-as-sideloading"></a><span data-ttu-id="12067-195">Можно ли использовать политики разрешений приложения, чтобы ограничить загрузку специальных приложений (также называемых неопубликованными)?</span><span class="sxs-lookup"><span data-stu-id="12067-195">Can I use app permission policies to restrict uploading custom apps (also known as sideloading)?</span></span>

<span data-ttu-id="12067-196">Чтобы узнать больше о том, как ограничить загрузку настраиваемых приложений, ознакомьтесь со статьей [Управление пользовательскими политиками и параметрами приложений в Teams](teams-custom-app-policies-and-settings.md).</span><span class="sxs-lookup"><span data-stu-id="12067-196">To learn more about how to restrict uploading custom apps, see [Manage custom app policies and settings in Teams](teams-custom-app-policies-and-settings.md).</span></span>

#### <a name="how-long-does-it-take-for-policy-changes-to-take-effect"></a><span data-ttu-id="12067-197">Как долго изменения политики вступят в силу?</span><span class="sxs-lookup"><span data-stu-id="12067-197">How long does it take for policy changes to take effect?</span></span>

<span data-ttu-id="12067-198">После изменения глобальной политики или назначения пользователям политики для вступления в силу изменений может потребоваться до 24 часов.</span><span class="sxs-lookup"><span data-stu-id="12067-198">After you edit the global policy or assign a policy to users, it can take up to 24 hours for changes to take effect.</span></span> <span data-ttu-id="12067-199">Параметры приложения на уровне Организации вступают в силу немедленно.</span><span class="sxs-lookup"><span data-stu-id="12067-199">Org-wide app settings take effect immediately.</span></span>

#### <a name="does-blocking-an-app-apply-to-teams-mobile-clients"></a><span data-ttu-id="12067-200">Заблокирует ли приложение для мобильных клиентов Teams?</span><span class="sxs-lookup"><span data-stu-id="12067-200">Does blocking an app apply to Teams mobile clients?</span></span>

<span data-ttu-id="12067-201">Да, когда вы блокируете приложение, это приложение блокируется на всех клиентах групп.</span><span class="sxs-lookup"><span data-stu-id="12067-201">Yes, when you block an app, that app is blocked across all Teams clients.</span></span>  

### <a name="user-experience"></a><span data-ttu-id="12067-202">Взаимодействие с пользователем</span><span class="sxs-lookup"><span data-stu-id="12067-202">User experience</span></span>

#### <a name="what-does-a-user-experience-when-an-app-is-blocked"></a><span data-ttu-id="12067-203">Что может происходить, если приложение заблокировано?</span><span class="sxs-lookup"><span data-stu-id="12067-203">What does a user experience when an app is blocked?</span></span>

<span data-ttu-id="12067-204">Пользователи не могут взаимодействовать с заблокированным приложением или его возможностями, такими как ботов, табуляция и расширениями для обмена сообщениями.</span><span class="sxs-lookup"><span data-stu-id="12067-204">Users can't interact with a blocked app or its capabilities, such bots, tabs, and messaging extensions.</span></span> <span data-ttu-id="12067-205">В общем контексте, таком как команда или групповой чат, ботов может отправлять сообщения всем участникам этого контекста.</span><span class="sxs-lookup"><span data-stu-id="12067-205">In a shared context, such as a team or group chat, bots can still send messages to all participants of that context.</span></span> <span data-ttu-id="12067-206">Команды показывают пользователю, когда приложение заблокировано.</span><span class="sxs-lookup"><span data-stu-id="12067-206">Teams indicates to the user when an app is blocked.</span></span> 

<span data-ttu-id="12067-207">Например, если приложение заблокировано, пользователи не могут выполнять указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="12067-207">For example, when an app is blocked, users can't do any of the following:</span></span>

- <span data-ttu-id="12067-208">Добавление приложения лично или в чате или в рабочую группу</span><span class="sxs-lookup"><span data-stu-id="12067-208">Add the app personally or to a chat or team</span></span>
- <span data-ttu-id="12067-209">Отправка сообщений на роботе приложения</span><span class="sxs-lookup"><span data-stu-id="12067-209">Send messages to the app’s bot</span></span>
- <span data-ttu-id="12067-210">Выполнение действий кнопок, которые отправляют данные обратно приложению, например сообщения, которые можно использовать</span><span class="sxs-lookup"><span data-stu-id="12067-210">Perform button actions that send information back to the app, such as actionable messages</span></span>  
- <span data-ttu-id="12067-211">Просмотр вкладки "приложение"</span><span class="sxs-lookup"><span data-stu-id="12067-211">View the app’s tab</span></span>
- <span data-ttu-id="12067-212">Настройка соединителей для получения уведомлений</span><span class="sxs-lookup"><span data-stu-id="12067-212">Set up connectors to receive notifications</span></span>
- <span data-ttu-id="12067-213">Использование расширения для обмена сообщениями в приложении</span><span class="sxs-lookup"><span data-stu-id="12067-213">Use the app’s messaging extension</span></span>

 ## <a name="related-topics"></a><span data-ttu-id="12067-214">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="12067-214">Related topics</span></span>
- [<span data-ttu-id="12067-215">Параметры администратора для приложений в Teams</span><span class="sxs-lookup"><span data-stu-id="12067-215">Admin settings for apps in Teams</span></span>](admin-settings.md)
- [<span data-ttu-id="12067-216">Управление политиками настройки приложений в Teams</span><span class="sxs-lookup"><span data-stu-id="12067-216">Manage app setup policies in Teams</span></span>](teams-app-setup-policies.md)
- [<span data-ttu-id="12067-217">Управление пользовательскими политиками и параметрами приложений в Teams</span><span class="sxs-lookup"><span data-stu-id="12067-217">Manage custom app policies and settings in Teams</span></span>](teams-custom-app-policies-and-settings.md)
