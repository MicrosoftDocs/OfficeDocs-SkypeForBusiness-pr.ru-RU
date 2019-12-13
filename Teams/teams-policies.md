---
title: Управление политиками Teams в Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: jastark
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
description: Сведения о том, как использовать политики Teams в Организации и управлять ими, чтобы управлять тем, какие пользователи могут выполнять в Teams и каналах.
f1keywords:
- ms.teamsadmincenter.teams.teamspolicies.new.tooltip.discoverteams
- ms.teamsadmincenter.teams.teamspolicies.new.tooltip.createchannels
- ms.teamsadmincenter.teams.teamsandchannelpolicies.overview
- ms.teamsadmincenter.teamsandchannelpolicies.overview
- ms.teamsadmincenter.teams.teamspolicies.new.tooltip.discover
- ms.teamsadmincenter.teams.teamspolicies.new.tooltip.create
ms.openlocfilehash: 02c7258ebc316d5e08c77698e18935eb51b5b43d
ms.sourcegitcommit: f2c7626dbef4ed250b9a937a9b56d46fe2e2039e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/12/2019
ms.locfileid: "39998817"
---
# <a name="manage-teams-policies-in-microsoft-teams"></a><span data-ttu-id="c7504-103">Управление политиками Teams в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c7504-103">Manage teams policies in Microsoft Teams</span></span>

<span data-ttu-id="c7504-104">Администраторы могут использовать политики Teams в Microsoft Teams для управления тем, какие пользователи в организации могут выполнять в Teams и каналах.</span><span class="sxs-lookup"><span data-stu-id="c7504-104">As an admin, you can use teams policies in Microsoft Teams to control what users in your organization can do in teams and channels.</span></span> <span data-ttu-id="c7504-105">Например, вы можете указать, разрешено ли пользователям находить закрытые команды в результатах поиска и коллекции групп, а также могут ли пользователи создавать закрытые каналы.</span><span class="sxs-lookup"><span data-stu-id="c7504-105">For example, you can set whether users are allowed to discover private teams in search results and in the team gallery and whether users are allowed to create private channels.</span></span>

<span data-ttu-id="c7504-106">Управление политиками Teams осуществляется путем **перехода в** > **политики** Teams в центре администрирования Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="c7504-106">You manage teams policies by going to **Teams** > **Teams policies** in the Microsoft Teams admin center.</span></span> <span data-ttu-id="c7504-107">Вы можете использовать глобальную политику (по умолчанию на уровне Организации) или создавать пользовательские политики и назначать их пользователям.</span><span class="sxs-lookup"><span data-stu-id="c7504-107">You can use the global (Org-wide default) policy or create custom policies and assign them to users.</span></span> <span data-ttu-id="c7504-108">Пользователи в вашей организации автоматически получат глобальную политику, если вы не создадите и не назначаете пользовательскую политику.</span><span class="sxs-lookup"><span data-stu-id="c7504-108">Users in your organization will automatically get the global policy unless you create and assign a custom policy.</span></span>

<span data-ttu-id="c7504-109">Вы можете изменять глобальную политику или создавать и назначать пользовательские политики.</span><span class="sxs-lookup"><span data-stu-id="c7504-109">You can edit the global policy or create and assign a custom policy.</span></span> <span data-ttu-id="c7504-110">Если пользователю назначена настраиваемая политика, эта политика применяется к пользователю.</span><span class="sxs-lookup"><span data-stu-id="c7504-110">If a user is assigned a custom policy, that policy applies to the user.</span></span> <span data-ttu-id="c7504-111">Если пользователю не назначена настраиваемая политика, она применяется к глобальной политике.</span><span class="sxs-lookup"><span data-stu-id="c7504-111">If a user isn't assigned a custom policy, the global policy applies to the user.</span></span> <span data-ttu-id="c7504-112">После изменения глобальной политики или назначения политики для вступления изменений в силу может потребоваться до 24 часов.</span><span class="sxs-lookup"><span data-stu-id="c7504-112">After you edit the global policy or assign a policy, it can take up to 24 hours for changes to take effect.</span></span>

## <a name="create-a-custom-teams-policy"></a><span data-ttu-id="c7504-113">Создание настраиваемой политики рабочих групп</span><span class="sxs-lookup"><span data-stu-id="c7504-113">Create a custom teams policy</span></span>

1. <span data-ttu-id="c7504-114">В левой области навигации центра администрирования Microsoft Teams перейдите в раздел политики **Teams** > \*\*\*\* Teams.</span><span class="sxs-lookup"><span data-stu-id="c7504-114">In the left navigation of the Microsoft Teams admin center, go to **Teams** > **Teams policies**.</span></span>
2. <span data-ttu-id="c7504-115">Нажмите **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="c7504-115">Click **Add**.</span></span>
3. <span data-ttu-id="c7504-116">Введите имя и описание политики.</span><span class="sxs-lookup"><span data-stu-id="c7504-116">Enter a name and description for the policy.</span></span>

    ![Снимок экрана: параметры политики Teams](media/teams-policies.png)
4. <span data-ttu-id="c7504-118">Выберите нужные параметры.</span><span class="sxs-lookup"><span data-stu-id="c7504-118">Choose the settings that you want:</span></span>

- <span data-ttu-id="c7504-119">**Откройте для себя закрытые команды**:<a name="discoverteams"> </a> включите этот параметр, чтобы разрешить пользователям находить частные команды в результатах поиска и коллекции групп.</span><span class="sxs-lookup"><span data-stu-id="c7504-119">**Discover private teams**:<a name="discoverteams"> </a> Turn on this setting to allow users to discover private teams in search results and in the team gallery.</span></span>
- <span data-ttu-id="c7504-120">**Создание частных каналов**: <a name="createchannels"> </a>включите этот параметр, чтобы разрешить пользователям создавать закрытые каналы.</span><span class="sxs-lookup"><span data-stu-id="c7504-120">**Create private channels**: <a name="createchannels"> </a>Turn on this setting to allow users to create private channels.</span></span>

5. <span data-ttu-id="c7504-121">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="c7504-121">Click **Save**.</span></span>

## <a name="edit-a-teams-policy"></a><span data-ttu-id="c7504-122">Изменение политики Teams</span><span class="sxs-lookup"><span data-stu-id="c7504-122">Edit a teams policy</span></span>

<span data-ttu-id="c7504-123">Вы можете изменить глобальную политику или созданные вами пользовательские политики.</span><span class="sxs-lookup"><span data-stu-id="c7504-123">You can edit the global policy or any custom policies that you create.</span></span>

1. <span data-ttu-id="c7504-124">В левой области навигации центра администрирования Microsoft Teams перейдите в раздел политики **Teams** > \*\*\*\* Teams.</span><span class="sxs-lookup"><span data-stu-id="c7504-124">In the left navigation of the Microsoft Teams admin center, go to **Teams** > **Teams policies**.</span></span>
2. <span data-ttu-id="c7504-125">Выберите политику, щелкнув слева от ее имени, а затем нажмите кнопку **изменить**.</span><span class="sxs-lookup"><span data-stu-id="c7504-125">Select the policy by clicking to the left of the policy name, and then click **Edit**.</span></span>
3. <span data-ttu-id="c7504-126">Включите или выключите нужные параметры, а затем нажмите кнопку **сохранить**.</span><span class="sxs-lookup"><span data-stu-id="c7504-126">Turn on or turn off the settings that you want, and then click **Save**.</span></span>

## <a name="assign-a-custom-teams-policy-to-users"></a><span data-ttu-id="c7504-127">Назначение пользователям политики групп</span><span class="sxs-lookup"><span data-stu-id="c7504-127">Assign a custom teams policy to users</span></span>

<span data-ttu-id="c7504-128">Центр администрирования Microsoft Teams можно использовать для назначения настраиваемой политики для одного или нескольких пользователей или модуля Skype для бизнеса PowerShell для назначения особой политики группам пользователей, таким как группа безопасности или группа рассылки.</span><span class="sxs-lookup"><span data-stu-id="c7504-128">You can use the Microsoft Teams admin center to assign a custom policy to one or more users or the Skype for Business PowerShell module to assign a custom policy to groups of users, such as a security group or distribution group.</span></span>

### <a name="assign-a-custom-teams-policy-to-a-user"></a><span data-ttu-id="c7504-129">Назначение пользователю пользовательской политики рабочих групп</span><span class="sxs-lookup"><span data-stu-id="c7504-129">Assign a custom teams policy to a user</span></span>

1. <span data-ttu-id="c7504-130">В левой области навигации центра администрирования Microsoft Teams перейдите в раздел **Пользователи**и выберите пользователя.</span><span class="sxs-lookup"><span data-stu-id="c7504-130">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click  the user.</span></span>
2. <span data-ttu-id="c7504-131">Нажмите **политики**, а затем рядом с пунктом **назначенные политики**нажмите кнопку **изменить**.</span><span class="sxs-lookup"><span data-stu-id="c7504-131">Click **Policies**, and then next to **Assigned policies**, click **Edit**.</span></span>
3. <span data-ttu-id="c7504-132">В разделе **политики Teams**выберите политику, которую вы хотите назначить, и нажмите кнопку **сохранить**.</span><span class="sxs-lookup"><span data-stu-id="c7504-132">Under **Teams policies**, select the policy you want to assign, and then click **Save**.</span></span>

<span data-ttu-id="c7504-133">Чтобы назначить специальную политику групп нескольким пользователям одновременно, ознакомьтесь с [разгруппым изменением параметров пользователей Teams](edit-user-settings-in-bulk.md).</span><span class="sxs-lookup"><span data-stu-id="c7504-133">To assign a custom teams policy to multiple users at a time, see [Edit Teams user settings in bulk](edit-user-settings-in-bulk.md).</span></span>

<span data-ttu-id="c7504-134">Кроме того, вы можете сделать следующее:</span><span class="sxs-lookup"><span data-stu-id="c7504-134">Or, you can also do the following:</span></span>

1. <span data-ttu-id="c7504-135">В левой области навигации центра администрирования Microsoft Teams перейдите в раздел политики **Teams** > \*\*\*\* Teams.</span><span class="sxs-lookup"><span data-stu-id="c7504-135">In the left navigation of the Microsoft Teams admin center, go to **Teams** > **Teams policies**.</span></span>
2. <span data-ttu-id="c7504-136">Выберите политику, щелкнув слева от имени политики.</span><span class="sxs-lookup"><span data-stu-id="c7504-136">Select the policy by clicking to the left of the policy name.</span></span>
3. <span data-ttu-id="c7504-137">Выберите **Управление пользователями**.</span><span class="sxs-lookup"><span data-stu-id="c7504-137">Select **Manage users**.</span></span>
4. <span data-ttu-id="c7504-138">В области **Управление пользователями** найдите пользователя по отображаемому имени или по имени пользователя, выберите имя и нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="c7504-138">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then select **Add**.</span></span> <span data-ttu-id="c7504-139">Повторите этот шаг для каждого пользователя, которого вы хотите добавить.</span><span class="sxs-lookup"><span data-stu-id="c7504-139">Repeat this step for each user that you want to add.</span></span>
5. <span data-ttu-id="c7504-140">Завершив добавление пользователей, нажмите кнопку **сохранить**.</span><span class="sxs-lookup"><span data-stu-id="c7504-140">When you're finished adding users, click **Save**.</span></span>

### <a name="assign-a-custom-teams-policy-to-users-in-a-group"></a><span data-ttu-id="c7504-141">Назначение настраиваемой политики групп пользователям в группе</span><span class="sxs-lookup"><span data-stu-id="c7504-141">Assign a custom teams policy to users in a group</span></span>

<span data-ttu-id="c7504-142">Вы можете назначить специальную политику групп нескольким пользователям, которые уже были идентифицированы.</span><span class="sxs-lookup"><span data-stu-id="c7504-142">You may want to assign a custom teams policy to multiple users that you’ve already identified.</span></span> <span data-ttu-id="c7504-143">Например, может потребоваться назначить политику всем пользователям в группе безопасности.</span><span class="sxs-lookup"><span data-stu-id="c7504-143">For example, you may want to assign a policy to all users in a security group.</span></span> <span data-ttu-id="c7504-144">Это можно сделать, подключив службу Azure Active Directory PowerShell для Graph и модуль PowerShell для Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="c7504-144">You can do this by connecting to the Azure Active Directory PowerShell for Graph module and the Skype for Business PowerShell module.</span></span> <span data-ttu-id="c7504-145">Дополнительные сведения об использовании PowerShell для управления группами можно найти в разделе [Общие сведения о Teams PowerShell](teams-powershell-overview.md).</span><span class="sxs-lookup"><span data-stu-id="c7504-145">For more information about using PowerShell to manage Teams, see [Teams PowerShell Overview](teams-powershell-overview.md).</span></span>

<span data-ttu-id="c7504-146">В этом примере мы назначаем политику Teams, которая называется политикой маркетинговых групп, всем пользователям в маркетинговой группе contoso.</span><span class="sxs-lookup"><span data-stu-id="c7504-146">In this example, we assign a teams policy called Marketing Teams Policy to all users in the Contoso Marketing group.</span></span>  

> [!NOTE]
> <span data-ttu-id="c7504-147">Убедитесь, что вы подключаетесь к модулю Azure Active Directory PowerShell для модуля Graph и Skype для бизнеса PowerShell, выполнив действия, описанные в разделе [подключение ко всем службам Office 365 в одном окне Windows PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).</span><span class="sxs-lookup"><span data-stu-id="c7504-147">Make sure you first connect to the Azure Active Directory PowerShell for Graph module and Skype for Business PowerShell module by following the steps in [Connect to all Office 365 services in a single Windows PowerShell window](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).</span></span>

<span data-ttu-id="c7504-148">Получить Граупобжектид определенной группы.</span><span class="sxs-lookup"><span data-stu-id="c7504-148">Get the GroupObjectId of the particular group.</span></span>
```
$group = Get-AzureADGroup -SearchString "Contoso Marketing"
```
<span data-ttu-id="c7504-149">Получение участников указанной группы.</span><span class="sxs-lookup"><span data-stu-id="c7504-149">Get the members of the specified group.</span></span>
```
$members = Get-AzureADGroupMember -ObjectId $group.ObjectId -All $true | Where-Object {$_.ObjectType -eq "User"}
```
<span data-ttu-id="c7504-150">Назначьте всем пользователям в группе определенную политику групп.</span><span class="sxs-lookup"><span data-stu-id="c7504-150">Assign all users in the group to a particular teams policy.</span></span> <span data-ttu-id="c7504-151">В этом примере это политика маркетинговой группы.</span><span class="sxs-lookup"><span data-stu-id="c7504-151">In this example, it's Marketing Teams Policy.</span></span>
```
$members | ForEach-Object { Grant-CsTeamsChannelsPolicy -PolicyName "Marketing Teams Policy" -Identity $_.UserPrincipalName}
``` 
<span data-ttu-id="c7504-152">Для выполнения этой команды может потребоваться несколько минут в зависимости от количества участников в группе.</span><span class="sxs-lookup"><span data-stu-id="c7504-152">Depending on the number of members in the group, this command may take several minutes to execute.</span></span>

## <a name="related-topics"></a><span data-ttu-id="c7504-153">См. также</span><span class="sxs-lookup"><span data-stu-id="c7504-153">Related topics</span></span>

- [<span data-ttu-id="c7504-154">Управление обнаружением приватных команд в Teams</span><span class="sxs-lookup"><span data-stu-id="c7504-154">Manage discovery of private teams in Teams</span></span>](manage-discovery-of-private-teams.md)
- [<span data-ttu-id="c7504-155">Личные каналы в Teams</span><span class="sxs-lookup"><span data-stu-id="c7504-155">Private channels in Teams</span></span>](private-channels.md)
