---
title: Управление политиками идентификации вызывающего абонента в Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-voice
f1.keywords:
- CSH
ms.custom: ms.teamsadmincenter.voice.callinglineid.overview
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Сведения о том, как использовать политики идентификации вызывающего абонента в Microsoft Teams для изменения или блокировки идентификатора вызывающего абонента для пользователей Teams в Организации.
ms.openlocfilehash: ff2f9a02bdf91eb6296dce03e426be673f83495a
ms.sourcegitcommit: bfa5b8db4e42e0480542d61fe05716c52016873c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824547"
---
# <a name="manage-caller-id-policies-in-microsoft-teams"></a><span data-ttu-id="1bb3c-103">Управление политиками идентификации вызывающего абонента в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="1bb3c-103">Manage caller ID policies in Microsoft Teams</span></span>

>[!INCLUDE [new-feature-teams-admin-center](includes/new-feature-teams-admin-center.md)]

<span data-ttu-id="1bb3c-104">Администраторы могут использовать политики идентификации вызывающего абонента в Microsoft Teams для изменения или блокировки идентификатора вызывающего абонента (также называемого ИДЕНТИФИКАТОРом вызывающей строки).</span><span class="sxs-lookup"><span data-stu-id="1bb3c-104">As an admin, you can use caller ID policies in Microsoft Teams to change or block the caller ID (also known as calling line ID).</span></span> <span data-ttu-id="1bb3c-105">По умолчанию телефонный номер пользователей Teams может отображаться при звонке на телефон PSTN, и телефонный номер абонента PSTN может отображаться при звонках пользователю Teams.</span><span class="sxs-lookup"><span data-stu-id="1bb3c-105">By default, the phone number of Teams users can be seen when they make a call to a PSTN phone and the phone number of PSTN callers can be seen when they call a Teams user.</span></span> <span data-ttu-id="1bb3c-106">Вы можете использовать политики идентификации вызывающего абонента, чтобы отобразить дополнительный номер телефона для пользователей Teams в организации или заблокировать входящий номер.</span><span class="sxs-lookup"><span data-stu-id="1bb3c-106">You can use caller ID policies to display an alternate phone number for Teams users in your organization or block an incoming number from being displayed.</span></span>

<span data-ttu-id="1bb3c-107">Например, когда пользователь вызывает звонок, вы можете изменить идентификатор вызывающего абонента, чтобы вместо номера телефона пользователя отображался основной номер телефона Организации.</span><span class="sxs-lookup"><span data-stu-id="1bb3c-107">For example, when users make a call, you can change the caller ID to display your organization's main phone number instead of users' phone numbers.</span></span>

<span data-ttu-id="1bb3c-108">Для управления политиками идентификации вызывающего абонента в центре администрирования Microsoft Teams можно использовать**политики идентификатора** **голосовой связи** > .</span><span class="sxs-lookup"><span data-stu-id="1bb3c-108">You manage caller ID policies by going to **Voice** > **Caller ID policies** in the Microsoft Teams admin center.</span></span> <span data-ttu-id="1bb3c-109">Вы можете использовать глобальную политику (по умолчанию для всей организации) или создавать собственные политики и назначать их пользователям.</span><span class="sxs-lookup"><span data-stu-id="1bb3c-109">You can use the global (Org-wide default) policy or create custom policies and assign them to users.</span></span> <span data-ttu-id="1bb3c-110">Пользователи вашей организации автоматически получают глобальную политику, если вы не создали и не назначили настраиваемую политику.</span><span class="sxs-lookup"><span data-stu-id="1bb3c-110">Users in your organization will automatically get the global policy unless you create and assign a custom policy.</span></span>

<span data-ttu-id="1bb3c-111">Вы можете изменять глобальную политику или создавать и назначать пользовательские политики.</span><span class="sxs-lookup"><span data-stu-id="1bb3c-111">You can edit the global policy or create and assign a custom policy.</span></span> <span data-ttu-id="1bb3c-112">Если пользователю назначена настраиваемая политика, эта политика применяется к пользователю.</span><span class="sxs-lookup"><span data-stu-id="1bb3c-112">If a user is assigned a custom policy, that policy applies to the user.</span></span> <span data-ttu-id="1bb3c-113">Если пользователю не назначена настраиваемая политика, она применяется к глобальной политике.</span><span class="sxs-lookup"><span data-stu-id="1bb3c-113">If a user isn't assigned a custom policy, the global policy applies to the user.</span></span>

## <a name="create-a-custom-caller-id-policy"></a><span data-ttu-id="1bb3c-114">Создание политики ИДЕНТИФИКАТОРов для собственного вызывающего абонента</span><span class="sxs-lookup"><span data-stu-id="1bb3c-114">Create a custom caller ID policy</span></span>

1. <span data-ttu-id="1bb3c-115">В левой области навигации центра администрирования Microsoft Teams перейдите на вкладку идентификаторы **голосового** > **вызывающего абонента**.</span><span class="sxs-lookup"><span data-stu-id="1bb3c-115">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Caller ID policies**.</span></span>
2. <span data-ttu-id="1bb3c-116">Нажмите **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="1bb3c-116">Click **Add**.</span></span>
<span data-ttu-id="1bb3c-117">![Снимок экрана с новой страницей политики идентификации звонящего в центре администрирования](media/caller-id-policies-add-policy.png)</span><span class="sxs-lookup"><span data-stu-id="1bb3c-117">![Screenshot of new caller ID policy page in the admin center](media/caller-id-policies-add-policy.png)</span></span>
3. <span data-ttu-id="1bb3c-118">Введите имя и описание для политики.</span><span class="sxs-lookup"><span data-stu-id="1bb3c-118">Enter a name and description for the policy.</span></span>
4. <span data-ttu-id="1bb3c-119">В этой статье выберите нужные параметры.</span><span class="sxs-lookup"><span data-stu-id="1bb3c-119">From here, choose the settings that you want:</span></span>

    - <span data-ttu-id="1bb3c-120">**Блокировать входящий вызывающий абонент ID**: Включите этот параметр, чтобы заблокировать отображение идентификатора вызывающего абонента для входящих звонков.</span><span class="sxs-lookup"><span data-stu-id="1bb3c-120">**Block incoming caller ID**: Turn on this setting to block the caller ID of incoming calls from being displayed.</span></span>
    - <span data-ttu-id="1bb3c-121">**Пользователи могут переопределять политику идентификации вызывающего абонента**: Включите этот параметр, чтобы разрешить пользователям переопределять параметры политики в соответствии с отображением их номера в callees или нет.</span><span class="sxs-lookup"><span data-stu-id="1bb3c-121">**Users can override the caller ID policy**: Turn on this setting to let users override the settings in the policy regarding displaying their number to callees or not.</span></span> <span data-ttu-id="1bb3c-122">Это означает, что пользователи могут выбрать, нужно ли отображать идентификатор вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="1bb3c-122">This means that users can choose whether to display their caller ID.</span></span>
    - <span data-ttu-id="1bb3c-123">**Замените идентификатор вызывающего**абонента: установите для пользователей идентификатор вызывающего абонента, выбирая один из следующих параметров:</span><span class="sxs-lookup"><span data-stu-id="1bb3c-123">**Replace caller ID**: Set the caller ID to be displayed for users by selecting one of the following:</span></span>

        - <span data-ttu-id="1bb3c-124">**Номер пользователя**: отображает номер пользователя.</span><span class="sxs-lookup"><span data-stu-id="1bb3c-124">**User's number**: Displays the user's number.</span></span> 
        - <span data-ttu-id="1bb3c-125">**Номер Услуги**: позволяет указать номер телефона службы, который будет ОТОБРАЖАТЬСЯ как идентификатор вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="1bb3c-125">**Service number**: Lets you set a service phone number to display as the caller ID.</span></span>
        - <span data-ttu-id="1bb3c-126">**Анонимный**доступ: идентификатор вызывающего абонента отображается как анонимный.</span><span class="sxs-lookup"><span data-stu-id="1bb3c-126">**Anonymous**: Displays the caller ID as Anonymous.</span></span>

    - <span data-ttu-id="1bb3c-127">**Номер службы, который будет использоваться для замены идентификатора вызывающего абонента**: выберите номер службы, чтобы заменить идентификатор вызывающего абонента для пользователей.</span><span class="sxs-lookup"><span data-stu-id="1bb3c-127">**Service number to use to replace the caller ID**: Choose a service number to replace the caller ID of users.</span></span> <span data-ttu-id="1bb3c-128">Этот параметр доступен, если вы выбрали **номер службы** в параметре " **заменить идентификатор вызывающего абонента**".</span><span class="sxs-lookup"><span data-stu-id="1bb3c-128">This option is available if you selected **Service number** in **Replace caller ID**.</span></span>

5. <span data-ttu-id="1bb3c-129">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="1bb3c-129">Click **Save**.</span></span>

## <a name="edit-a-caller-id-policy"></a><span data-ttu-id="1bb3c-130">Изменение политики идентификации вызывающего абонента</span><span class="sxs-lookup"><span data-stu-id="1bb3c-130">Edit a caller ID policy</span></span>

<span data-ttu-id="1bb3c-131">Вы можете изменить глобальную политику или созданные вами пользовательские политики.</span><span class="sxs-lookup"><span data-stu-id="1bb3c-131">You can edit the global policy or any custom policies that you create.</span></span> 

1. <span data-ttu-id="1bb3c-132">В левой области навигации центра администрирования Microsoft Teams перейдите на вкладку идентификаторы **голосового** > **вызывающего абонента**.</span><span class="sxs-lookup"><span data-stu-id="1bb3c-132">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Caller ID policies**.</span></span>
2. <span data-ttu-id="1bb3c-133">Выберите политику, щелкнув слева от ее имени, а затем нажмите кнопку **изменить**.</span><span class="sxs-lookup"><span data-stu-id="1bb3c-133">Select the policy by clicking to the left of the policy name, and then click **Edit**.</span></span>
3. <span data-ttu-id="1bb3c-134">Измените нужные параметры и нажмите кнопку **сохранить**.</span><span class="sxs-lookup"><span data-stu-id="1bb3c-134">Change the settings that you want, and then click **Save**.</span></span>

## <a name="assign-a-custom-caller-id-policy-to-users"></a><span data-ttu-id="1bb3c-135">Назначение пользователям политики идентификации вызывающего абонента</span><span class="sxs-lookup"><span data-stu-id="1bb3c-135">Assign a custom caller ID policy to users</span></span>

<span data-ttu-id="1bb3c-136">Центр администрирования Microsoft Teams можно использовать для назначения настраиваемой политики для одного или нескольких пользователей или модуля Skype для бизнеса PowerShell для назначения особой политики группам пользователей, таким как группа безопасности или группа рассылки.</span><span class="sxs-lookup"><span data-stu-id="1bb3c-136">You can use the Microsoft Teams admin center to assign a custom policy to one or more users or the Skype for Business PowerShell module to assign a custom policy to groups of users, such as a security group or distribution group.</span></span>

### <a name="assign-a-custom-caller-line-id-policy-to-a-user"></a><span data-ttu-id="1bb3c-137">Назначение пользователю пользовательской политики идентификации строки вызывающего абонента</span><span class="sxs-lookup"><span data-stu-id="1bb3c-137">Assign a custom caller line ID policy to a user</span></span>

1. <span data-ttu-id="1bb3c-138">В Центре администрирования Microsoft Teams в области навигации слева перейдите в раздел **Пользователи**, затем щелкните пользователя.</span><span class="sxs-lookup"><span data-stu-id="1bb3c-138">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click the user.</span></span>
2. <span data-ttu-id="1bb3c-139">Нажмите **политики**, а затем рядом с пунктом **назначенные политики**нажмите кнопку **изменить**.</span><span class="sxs-lookup"><span data-stu-id="1bb3c-139">Click **Policies**, and then next to **Assigned policies**, click **Edit**.</span></span>
3. <span data-ttu-id="1bb3c-140">В разделе **Политика идентификации звонящего**выберите политику, которую вы хотите назначить, и нажмите кнопку **сохранить**.</span><span class="sxs-lookup"><span data-stu-id="1bb3c-140">Under **Caller ID policy**, select the policy you want to assign, and then choose **Save**.</span></span>

### <a name="assign-a-custom-calling-line-id-policy-to-multiple-users-at-a-time"></a><span data-ttu-id="1bb3c-141">Назначение политики ИДЕНТИФИКАТОРов для настраиваемой строки вызова нескольким пользователям за один раз</span><span class="sxs-lookup"><span data-stu-id="1bb3c-141">Assign a custom calling line ID policy to multiple users at a time</span></span>

<span data-ttu-id="1bb3c-142">Чтобы назначить политику идентификаторов для настраиваемой линии вызова нескольким пользователям одновременно, ознакомьтесь с [разгруппым изменением параметров пользователей Teams](edit-user-settings-in-bulk.md).</span><span class="sxs-lookup"><span data-stu-id="1bb3c-142">To assign a custom calling line Id policy to multiple users at a time, see [Edit Teams user settings in bulk](edit-user-settings-in-bulk.md).</span></span>

<span data-ttu-id="1bb3c-143">Кроме того, вы можете сделать следующее:</span><span class="sxs-lookup"><span data-stu-id="1bb3c-143">Or, you can also do the following:</span></span>

1. <span data-ttu-id="1bb3c-144">Перейдите в раздел**политики идентификаторов** > **голосового** > вызова **центра администрирования Microsoft Teams**.</span><span class="sxs-lookup"><span data-stu-id="1bb3c-144">Go to **Microsoft Teams admin center** > **Voice** > **Caller ID policies**.</span></span>
2. <span data-ttu-id="1bb3c-145">Выберите политику, щелкнув слева от ее имени.</span><span class="sxs-lookup"><span data-stu-id="1bb3c-145">Select the policy by clicking to the left of the policy name.</span></span>
3. <span data-ttu-id="1bb3c-146">Выберите **Управление пользователями**.</span><span class="sxs-lookup"><span data-stu-id="1bb3c-146">Select **Manage users**.</span></span>
4. <span data-ttu-id="1bb3c-147">В области **Управление пользователями** выполните поиск по отображаемому имени или по имени пользователя, выберите имя и нажмите **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="1bb3c-147">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then select **Add**.</span></span> <span data-ttu-id="1bb3c-148">Повторите это действие для каждого пользователя, которого нужно добавить.</span><span class="sxs-lookup"><span data-stu-id="1bb3c-148">Repeat this step for each user that you want to add.</span></span>
5. <span data-ttu-id="1bb3c-149">Завершив добавление пользователей, нажмите кнопку **сохранить**.</span><span class="sxs-lookup"><span data-stu-id="1bb3c-149">When you're finished adding users, select **Save**.</span></span>

### <a name="assign-a-custom-caller-id-policy-to-users-in-a-group"></a><span data-ttu-id="1bb3c-150">Назначение собственной политики идентификации вызывающего абонента пользователям в группе</span><span class="sxs-lookup"><span data-stu-id="1bb3c-150">Assign a custom caller ID policy to users in a group</span></span>

<span data-ttu-id="1bb3c-151">Вы можете назначить специальную политику для нескольких пользователей, которые уже были идентифицированы.</span><span class="sxs-lookup"><span data-stu-id="1bb3c-151">You may want to assign a custom  policy to multiple users that you’ve already identified.</span></span> <span data-ttu-id="1bb3c-152">Например, может потребоваться назначить политику всем пользователям в группе безопасности.</span><span class="sxs-lookup"><span data-stu-id="1bb3c-152">For example, you may want to assign a policy to all users in a security group.</span></span> <span data-ttu-id="1bb3c-153">Это можно сделать, подключив службу Azure Active Directory PowerShell для Graph и модуль PowerShell для Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="1bb3c-153">You can do this by connecting to the Azure Active Directory PowerShell for Graph module and the Skype for Business PowerShell module.</span></span> <span data-ttu-id="1bb3c-154">Дополнительные сведения об использовании PowerShell для управления группами можно найти в разделе [Общие сведения о Teams PowerShell](teams-powershell-overview.md).</span><span class="sxs-lookup"><span data-stu-id="1bb3c-154">For more information about using PowerShell to manage Teams, see [Teams PowerShell Overview](teams-powershell-overview.md).</span></span>

<span data-ttu-id="1bb3c-155">В этом примере мы назначаем пользовательскую политику закрытия вызывающего абонента поддержки для всех пользователей в группе поддержки contoso.</span><span class="sxs-lookup"><span data-stu-id="1bb3c-155">In this example, we assign a custom caller lID policy called Support Caller ID Policy to all users in the Contoso Support group.</span></span>  

> [!NOTE]
> <span data-ttu-id="1bb3c-156">Убедитесь, что вы подключаетесь к модулю Azure Active Directory PowerShell для модуля Graph и Skype для бизнеса PowerShell, выполнив действия, описанные в разделе [подключение ко всем службам Office 365 в одном окне Windows PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).</span><span class="sxs-lookup"><span data-stu-id="1bb3c-156">Make sure you first connect to the Azure Active Directory PowerShell for Graph module and Skype for Business PowerShell module by following the steps in [Connect to all Office 365 services in a single Windows PowerShell window](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).</span></span>

<span data-ttu-id="1bb3c-157">Получить GroupObjectId определенной группы.</span><span class="sxs-lookup"><span data-stu-id="1bb3c-157">Get the GroupObjectId of the particular group.</span></span>
```PowerShell
$group = Get-AzureADGroup -SearchString "Contoso Support"
```
<span data-ttu-id="1bb3c-158">Получение участников указанной группы.</span><span class="sxs-lookup"><span data-stu-id="1bb3c-158">Get the members of the specified group.</span></span>
```PowerShell
$members = Get-AzureADGroupMember -ObjectId $group.ObjectId -All $true | Where-Object {$_.ObjectType -eq "User"}
```
<span data-ttu-id="1bb3c-159">Назначьте для всех пользователей в группе определенную политику идентификации вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="1bb3c-159">Assign all users in the group to a particular caller ID policy.</span></span> <span data-ttu-id="1bb3c-160">В этом примере это поддержка политики идентификации вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="1bb3c-160">In this example, it's Support Caller ID Policy.</span></span>
```PowerShell
$members | ForEach-Object { Grant-CsCallingLineIdentity -PolicyName "Support Caller ID Policy" -Identity $_.UserPrincipalName}
``` 
<span data-ttu-id="1bb3c-161">Для выполнения этой команды может потребоваться несколько минут в зависимости от количества участников в группе.</span><span class="sxs-lookup"><span data-stu-id="1bb3c-161">Depending on the number of members in the group, this command may take several minutes to execute.</span></span>

 ## <a name="related-topics"></a><span data-ttu-id="1bb3c-162">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="1bb3c-162">Related topics</span></span>

- [<span data-ttu-id="1bb3c-163">New-CsCallingLineIdentity</span><span class="sxs-lookup"><span data-stu-id="1bb3c-163">New-CsCallingLineIdentity</span></span>](https://docs.microsoft.com/powershell/module/skype/new-cscallinglineidentity?view=skype-ps)

