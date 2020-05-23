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
ms.openlocfilehash: dde534d0c74b11b3c3131a7d5c9eb8611135f70f
ms.sourcegitcommit: ee2b4c207b3c9f993309f66cf8016e137c001c7f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/23/2020
ms.locfileid: "44349783"
---
# <a name="manage-caller-id-policies-in-microsoft-teams"></a><span data-ttu-id="b8320-103">Управление политиками идентификации вызывающего абонента в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b8320-103">Manage caller ID policies in Microsoft Teams</span></span>

>[!INCLUDE [new-feature-teams-admin-center](includes/new-feature-teams-admin-center.md)]

<span data-ttu-id="b8320-104">Администраторы могут использовать политики идентификации вызывающего абонента в Microsoft Teams для изменения или блокировки идентификатора вызывающего абонента (также называемого ИДЕНТИФИКАТОРом вызывающей строки).</span><span class="sxs-lookup"><span data-stu-id="b8320-104">As an admin, you can use caller ID policies in Microsoft Teams to change or block the caller ID (also known as calling line ID).</span></span> <span data-ttu-id="b8320-105">По умолчанию телефонный номер пользователей Teams может отображаться при звонке на телефон PSTN, и телефонный номер абонента PSTN может отображаться при звонках пользователю Teams.</span><span class="sxs-lookup"><span data-stu-id="b8320-105">By default, the phone number of Teams users can be seen when they make a call to a PSTN phone and the phone number of PSTN callers can be seen when they call a Teams user.</span></span> <span data-ttu-id="b8320-106">Вы можете использовать политики идентификации вызывающего абонента, чтобы отобразить дополнительный номер телефона для пользователей Teams в организации или заблокировать входящий номер.</span><span class="sxs-lookup"><span data-stu-id="b8320-106">You can use caller ID policies to display an alternate phone number for Teams users in your organization or block an incoming number from being displayed.</span></span>

<span data-ttu-id="b8320-107">Например, когда пользователь вызывает звонок, вы можете изменить идентификатор вызывающего абонента, чтобы вместо номера телефона пользователя отображался основной номер телефона Организации.</span><span class="sxs-lookup"><span data-stu-id="b8320-107">For example, when users make a call, you can change the caller ID to display your organization's main phone number instead of users' phone numbers.</span></span>

<span data-ttu-id="b8320-108">Для управления политиками идентификации вызывающего абонента **Voice**  >  в центре администрирования Microsoft Teams можно использовать**политики идентификатора** голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="b8320-108">You manage caller ID policies by going to **Voice** > **Caller ID policies** in the Microsoft Teams admin center.</span></span> <span data-ttu-id="b8320-109">Вы можете использовать глобальную политику (по умолчанию для всей организации) или создавать собственные политики и назначать их пользователям.</span><span class="sxs-lookup"><span data-stu-id="b8320-109">You can use the global (Org-wide default) policy or create custom policies and assign them to users.</span></span> <span data-ttu-id="b8320-110">Пользователи вашей организации автоматически получают глобальную политику, если вы не создали и не назначили настраиваемую политику.</span><span class="sxs-lookup"><span data-stu-id="b8320-110">Users in your organization will automatically get the global policy unless you create and assign a custom policy.</span></span>

<span data-ttu-id="b8320-111">Вы можете изменять глобальную политику или создавать и назначать пользовательские политики.</span><span class="sxs-lookup"><span data-stu-id="b8320-111">You can edit the global policy or create and assign a custom policy.</span></span> <span data-ttu-id="b8320-112">Если пользователю назначена настраиваемая политика, эта политика применяется к пользователю.</span><span class="sxs-lookup"><span data-stu-id="b8320-112">If a user is assigned a custom policy, that policy applies to the user.</span></span> <span data-ttu-id="b8320-113">Если пользователю не назначена настраиваемая политика, она применяется к глобальной политике.</span><span class="sxs-lookup"><span data-stu-id="b8320-113">If a user isn't assigned a custom policy, the global policy applies to the user.</span></span>

## <a name="create-a-custom-caller-id-policy"></a><span data-ttu-id="b8320-114">Создание политики ИДЕНТИФИКАТОРов для собственного вызывающего абонента</span><span class="sxs-lookup"><span data-stu-id="b8320-114">Create a custom caller ID policy</span></span>

1. <span data-ttu-id="b8320-115">В левой области навигации центра администрирования Microsoft Teams перейдите на вкладку идентификаторы **голосового**  >  **вызывающего абонента**.</span><span class="sxs-lookup"><span data-stu-id="b8320-115">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Caller ID policies**.</span></span>
2. <span data-ttu-id="b8320-116">Нажмите **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="b8320-116">Click **Add**.</span></span> <br>
<span data-ttu-id="b8320-117">![Снимок экрана с новой страницей политики идентификации звонящего в центре администрирования](media/caller-id-policies-add-policy.png)</span><span class="sxs-lookup"><span data-stu-id="b8320-117">![Screenshot of new caller ID policy page in the admin center](media/caller-id-policies-add-policy.png)</span></span>
3. <span data-ttu-id="b8320-118">Введите имя и описание для политики.</span><span class="sxs-lookup"><span data-stu-id="b8320-118">Enter a name and description for the policy.</span></span>
4. <span data-ttu-id="b8320-119">В этой статье выберите нужные параметры.</span><span class="sxs-lookup"><span data-stu-id="b8320-119">From here, choose the settings that you want:</span></span>

    - <span data-ttu-id="b8320-120">**Блокировать входящий вызывающий абонент ID**: Включите этот параметр, чтобы заблокировать отображение идентификатора вызывающего абонента для входящих звонков.</span><span class="sxs-lookup"><span data-stu-id="b8320-120">**Block incoming caller ID**: Turn on this setting to block the caller ID of incoming calls from being displayed.</span></span>
    - <span data-ttu-id="b8320-121">**Переопределение политики идентификации вызывающего абонента**: Включите этот параметр, чтобы разрешить пользователям переопределять параметры политики в отношении отображения их номера в callees или нет.</span><span class="sxs-lookup"><span data-stu-id="b8320-121">**Override the caller ID policy**: Turn on this setting to let users override the settings in the policy regarding displaying their number to callees or not.</span></span> <span data-ttu-id="b8320-122">Это означает, что пользователи могут выбрать, нужно ли отображать идентификатор вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="b8320-122">This means that users can choose whether to display their caller ID.</span></span> <span data-ttu-id="b8320-123">Дополнительные сведения можно найти в разделе [управление конечным пользователем для идентификатора исходящего вызывающего абонента](https://docs.microsoft.com/microsoftteams/how-can-caller-id-be-used-in-your-organization#end-user-control-of-outbound-caller-id).</span><span class="sxs-lookup"><span data-stu-id="b8320-123">For more information, see [End user control of outbound caller ID](https://docs.microsoft.com/microsoftteams/how-can-caller-id-be-used-in-your-organization#end-user-control-of-outbound-caller-id).</span></span>
    - <span data-ttu-id="b8320-124">**Замените идентификатор вызывающего абонента**: установите для пользователей идентификатор вызывающего абонента, выбирая один из следующих параметров:</span><span class="sxs-lookup"><span data-stu-id="b8320-124">**Replace the caller ID with**: Set the caller ID to be displayed for users by selecting one of the following:</span></span>

        - <span data-ttu-id="b8320-125">**Номер пользователя**: отображает номер пользователя.</span><span class="sxs-lookup"><span data-stu-id="b8320-125">**User's number**: Displays the user's number.</span></span> 
        - <span data-ttu-id="b8320-126">**Номер Услуги**: позволяет указать номер телефона службы, который будет ОТОБРАЖАТЬСЯ как идентификатор вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="b8320-126">**Service number**: Lets you set a service phone number to display as the caller ID.</span></span>
        - <span data-ttu-id="b8320-127">**Анонимный**доступ: идентификатор вызывающего абонента отображается как анонимный.</span><span class="sxs-lookup"><span data-stu-id="b8320-127">**Anonymous**: Displays the caller ID as Anonymous.</span></span>

    - <span data-ttu-id="b8320-128">**Замените идентификатор вызывающего абонента на этот номер Услуги**: выберите номер службы, чтобы заменить идентификатор вызывающего абонента для пользователей.</span><span class="sxs-lookup"><span data-stu-id="b8320-128">**Replace the caller ID with this service number**: Choose a service number to replace the caller ID of users.</span></span> <span data-ttu-id="b8320-129">Этот параметр доступен, если вы выбрали **номер службы** в **поле заменить идентификатор вызывающего абонента**.</span><span class="sxs-lookup"><span data-stu-id="b8320-129">This option is available if you selected **Service number** in **Replace the caller ID with**.</span></span>

5. <span data-ttu-id="b8320-130">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="b8320-130">Click **Save**.</span></span>

## <a name="edit-a-caller-id-policy"></a><span data-ttu-id="b8320-131">Изменение политики идентификации вызывающего абонента</span><span class="sxs-lookup"><span data-stu-id="b8320-131">Edit a caller ID policy</span></span>

<span data-ttu-id="b8320-132">Вы можете изменить глобальную политику или созданные вами пользовательские политики.</span><span class="sxs-lookup"><span data-stu-id="b8320-132">You can edit the global policy or any custom policies that you create.</span></span> 

1. <span data-ttu-id="b8320-133">В левой области навигации центра администрирования Microsoft Teams перейдите на вкладку идентификаторы **голосового**  >  **вызывающего абонента**.</span><span class="sxs-lookup"><span data-stu-id="b8320-133">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Caller ID policies**.</span></span>
2. <span data-ttu-id="b8320-134">Выберите политику, щелкнув слева от ее имени, а затем нажмите кнопку **изменить**.</span><span class="sxs-lookup"><span data-stu-id="b8320-134">Select the policy by clicking to the left of the policy name, and then click **Edit**.</span></span>
3. <span data-ttu-id="b8320-135">Измените нужные параметры и нажмите кнопку **сохранить**.</span><span class="sxs-lookup"><span data-stu-id="b8320-135">Change the settings that you want, and then click **Save**.</span></span>

## <a name="assign-a-custom-caller-id-policy-to-users"></a><span data-ttu-id="b8320-136">Назначение пользователям политики идентификации вызывающего абонента</span><span class="sxs-lookup"><span data-stu-id="b8320-136">Assign a custom caller ID policy to users</span></span>

<span data-ttu-id="b8320-137">Центр администрирования Microsoft Teams можно использовать для назначения настраиваемой политики для одного или нескольких пользователей или модуля Skype для бизнеса PowerShell, чтобы назначить пользовательскую политику для пользователей в группе, например в группу безопасности или группу рассылки.</span><span class="sxs-lookup"><span data-stu-id="b8320-137">You can use the Microsoft Teams admin center to assign a custom policy to one or more users or the Skype for Business PowerShell module to assign a custom policy to users in a group, such as a security group or distribution group.</span></span>

### <a name="assign-a-custom-caller-line-id-policy-to-users"></a><span data-ttu-id="b8320-138">Назначение пользователю собственной политики ИДЕНТИФИКАТОРов строк вызывающей стороны</span><span class="sxs-lookup"><span data-stu-id="b8320-138">Assign a custom caller line ID policy to users</span></span>

<span data-ttu-id="b8320-139">Чтобы назначить политику для одного пользователя, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="b8320-139">To assign a policy to one user:</span></span>

1. <span data-ttu-id="b8320-140">В Центре администрирования Microsoft Teams в области навигации слева перейдите в раздел **Пользователи**, затем щелкните пользователя.</span><span class="sxs-lookup"><span data-stu-id="b8320-140">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click the user.</span></span>
2. <span data-ttu-id="b8320-141">Нажмите **политики**, а затем рядом с пунктом **назначенные политики**нажмите кнопку **изменить**.</span><span class="sxs-lookup"><span data-stu-id="b8320-141">Click **Policies**, and then next to **Assigned policies**, click **Edit**.</span></span>
3. <span data-ttu-id="b8320-142">В разделе **Политика идентификации звонящего**выберите политику, которую вы хотите назначить, и нажмите кнопку **сохранить**.</span><span class="sxs-lookup"><span data-stu-id="b8320-142">Under **Caller ID policy**, select the policy you want to assign, and then choose **Save**.</span></span>

<span data-ttu-id="b8320-143">Чтобы назначить политику нескольким пользователям за один раз, сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="b8320-143">To assign a policy to multiple users at a time:</span></span>

1. <span data-ttu-id="b8320-144">В левой области навигации центра администрирования Microsoft Teams перейдите в раздел **Пользователи**, а затем найдите пользователей или отфильтруйте представление, чтобы отобразить нужных пользователей.</span><span class="sxs-lookup"><span data-stu-id="b8320-144">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then search for the users or filter the view to show the users you want.</span></span>
2. <span data-ttu-id="b8320-145">В столбце **&#x2713;** (флажок) выберите пользователей.</span><span class="sxs-lookup"><span data-stu-id="b8320-145">In the **&#x2713;** (check mark) column, select the users.</span></span> <span data-ttu-id="b8320-146">Чтобы выбрать всех пользователей, щелкните &#x2713; (галочка) в верхней части таблицы.</span><span class="sxs-lookup"><span data-stu-id="b8320-146">To select all users, click the &#x2713; (check mark) at the top of the table.</span></span>
3. <span data-ttu-id="b8320-147">Нажмите кнопку **изменить параметры**, внесите необходимые изменения и нажмите кнопку **Применить**.</span><span class="sxs-lookup"><span data-stu-id="b8320-147">Click **Edit settings**, make the changes that you want, and then click **Apply**.</span></span>  

<span data-ttu-id="b8320-148">Кроме того, вы можете сделать следующее:</span><span class="sxs-lookup"><span data-stu-id="b8320-148">Or, you can also do the following:</span></span>

1. <span data-ttu-id="b8320-149">Перейдите в **Microsoft Teams admin center**раздел  >  **Voice**  >  **политики идентификаторов**голосового вызова центра администрирования Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="b8320-149">Go to **Microsoft Teams admin center** > **Voice** > **Caller ID policies**.</span></span>
2. <span data-ttu-id="b8320-150">Выберите политику, щелкнув слева от ее имени.</span><span class="sxs-lookup"><span data-stu-id="b8320-150">Select the policy by clicking to the left of the policy name.</span></span>
3. <span data-ttu-id="b8320-151">Выберите **Управление пользователями**.</span><span class="sxs-lookup"><span data-stu-id="b8320-151">Select **Manage users**.</span></span>
4. <span data-ttu-id="b8320-152">В области **Управление пользователями** выполните поиск по отображаемому имени или по имени пользователя, выберите имя и нажмите **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="b8320-152">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then select **Add**.</span></span> <span data-ttu-id="b8320-153">Повторите это действие для каждого пользователя, которого нужно добавить.</span><span class="sxs-lookup"><span data-stu-id="b8320-153">Repeat this step for each user that you want to add.</span></span>
5. <span data-ttu-id="b8320-154">Завершив добавление пользователей, нажмите кнопку **сохранить**.</span><span class="sxs-lookup"><span data-stu-id="b8320-154">When you're finished adding users, select **Save**.</span></span>

### <a name="assign-a-custom-caller-id-policy-to-users-in-a-group"></a><span data-ttu-id="b8320-155">Назначение собственной политики идентификации вызывающего абонента пользователям в группе</span><span class="sxs-lookup"><span data-stu-id="b8320-155">Assign a custom caller ID policy to users in a group</span></span>

<span data-ttu-id="b8320-156">Вы можете назначить специальную политику для нескольких пользователей, которые уже были идентифицированы.</span><span class="sxs-lookup"><span data-stu-id="b8320-156">You may want to assign a custom  policy to multiple users that you’ve already identified.</span></span> <span data-ttu-id="b8320-157">Например, может потребоваться назначить политику всем пользователям в группе безопасности.</span><span class="sxs-lookup"><span data-stu-id="b8320-157">For example, you may want to assign a policy to all users in a security group.</span></span> <span data-ttu-id="b8320-158">Это можно сделать, подключив службу Azure Active Directory PowerShell для Graph и модуль PowerShell для Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="b8320-158">You can do this by connecting to the Azure Active Directory PowerShell for Graph module and the Skype for Business PowerShell module.</span></span> <span data-ttu-id="b8320-159">Дополнительные сведения об использовании PowerShell для управления группами можно найти в разделе [Общие сведения о Teams PowerShell](teams-powershell-overview.md).</span><span class="sxs-lookup"><span data-stu-id="b8320-159">For more information about using PowerShell to manage Teams, see [Teams PowerShell Overview](teams-powershell-overview.md).</span></span>

<span data-ttu-id="b8320-160">В этом примере мы назначаем пользовательскую политику закрытия вызывающего абонента поддержки для всех пользователей в группе поддержки contoso.</span><span class="sxs-lookup"><span data-stu-id="b8320-160">In this example, we assign a custom caller lID policy called Support Caller ID Policy to all users in the Contoso Support group.</span></span>  

> [!NOTE]
> <span data-ttu-id="b8320-161">Убедитесь, что вы подключаетесь к модулю Azure Active Directory PowerShell для модуля Graph и Skype для бизнеса PowerShell, выполнив действия, описанные в разделе [подключение ко всем службам Office 365 в одном окне Windows PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).</span><span class="sxs-lookup"><span data-stu-id="b8320-161">Make sure you first connect to the Azure Active Directory PowerShell for Graph module and Skype for Business PowerShell module by following the steps in [Connect to all Office 365 services in a single Windows PowerShell window](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).</span></span>

<span data-ttu-id="b8320-162">Получить GroupObjectId определенной группы.</span><span class="sxs-lookup"><span data-stu-id="b8320-162">Get the GroupObjectId of the particular group.</span></span>
```PowerShell
$group = Get-AzureADGroup -SearchString "Contoso Support"
```
<span data-ttu-id="b8320-163">Получение участников указанной группы.</span><span class="sxs-lookup"><span data-stu-id="b8320-163">Get the members of the specified group.</span></span>
```PowerShell
$members = Get-AzureADGroupMember -ObjectId $group.ObjectId -All $true | Where-Object {$_.ObjectType -eq "User"}
```
<span data-ttu-id="b8320-164">Назначьте для всех пользователей в группе определенную политику идентификации вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="b8320-164">Assign all users in the group to a particular caller ID policy.</span></span> <span data-ttu-id="b8320-165">В этом примере это поддержка политики идентификации вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="b8320-165">In this example, it's Support Caller ID Policy.</span></span>
```PowerShell
$members | ForEach-Object { Grant-CsCallingLineIdentity -PolicyName "Support Caller ID Policy" -Identity $_.UserPrincipalName}
``` 
<span data-ttu-id="b8320-166">Для выполнения этой команды может потребоваться несколько минут в зависимости от количества участников в группе.</span><span class="sxs-lookup"><span data-stu-id="b8320-166">Depending on the number of members in the group, this command may take several minutes to execute.</span></span>

 ## <a name="related-topics"></a><span data-ttu-id="b8320-167">Связанные статьи</span><span class="sxs-lookup"><span data-stu-id="b8320-167">Related topics</span></span>

- [<span data-ttu-id="b8320-168">New-CsCallingLineIdentity</span><span class="sxs-lookup"><span data-stu-id="b8320-168">New-CsCallingLineIdentity</span></span>](https://docs.microsoft.com/powershell/module/skype/new-cscallinglineidentity?view=skype-ps)
- [<span data-ttu-id="b8320-169">Назначение политик пользователям в Teams</span><span class="sxs-lookup"><span data-stu-id="b8320-169">Assign policies to your users in Teams</span></span>](assign-policies.md)
