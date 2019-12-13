---
title: Управление политиками вызова экстренной помощи в Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: jastark, roykuntz
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Сведения об использовании политик вызова экстренной помощи и управлении ими в Microsoft Teams.
f1keywords: ms.teamsadmincenter.voice.emergencycallingpolicies.overview
ms.openlocfilehash: d6dc6f58085fedadf25f80272bc55dcc7723db19
ms.sourcegitcommit: f2c7626dbef4ed250b9a937a9b56d46fe2e2039e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/12/2019
ms.locfileid: "39998797"
---
# <a name="manage-emergency-calling-policies-in-microsoft-teams"></a><span data-ttu-id="11291-103">Управление политиками вызова экстренной помощи в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="11291-103">Manage emergency calling policies in Microsoft Teams</span></span>

<span data-ttu-id="11291-104">Если в вашей организации используются планы звонков или прямая маршрутизация на телефонную систему, вы можете использовать политики вызова экстренной помощи в Microsoft Teams, чтобы определить, что происходит, когда пользователь Teams в организации осуществляет вызов экстренной помощи.</span><span class="sxs-lookup"><span data-stu-id="11291-104">If your organization uses Calling Plans or deployed Phone System Direct Routing, you can use emergency calling policies in Microsoft Teams to define what happens when a Teams user in your organization makes an emergency call.</span></span> <span data-ttu-id="11291-105">Вы можете настроить пользователей, которые должны уведомлять и как они уведомляются, когда пользователь, которому назначена эта политика, вызывает экстренные службы.</span><span class="sxs-lookup"><span data-stu-id="11291-105">You can set who to notify and how they are notified when a user who is assigned the policy calls emergency services.</span></span> <span data-ttu-id="11291-106">Например, вы можете настроить параметры политики, чтобы автоматически уведомлять службу безопасности Организации и принимать их в экстренных звонках.</span><span class="sxs-lookup"><span data-stu-id="11291-106">For example, you can configure policy settings to automatically notify your organization's security desk and have them listen in emergency calls.</span></span>  

<span data-ttu-id="11291-107">Управление политиками вызова экстренной помощи осуществляется путем перехода на**политики** **голосовой связи** > в центре администрирования Microsoft Teams или с помощью Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="11291-107">You manage emergency calling policies by going to **Voice** > **Emergency policies** in the Microsoft Teams admin center or by using Windows PowerShell.</span></span> <span data-ttu-id="11291-108">Политики можно назначить для пользователей и [сайтов сети](cloud-voice-network-settings.md).</span><span class="sxs-lookup"><span data-stu-id="11291-108">The policies can be assigned to users and [network sites](cloud-voice-network-settings.md).</span></span>

<span data-ttu-id="11291-109">Пользователи могут использовать глобальную политику (по умолчанию на уровне Организации) или создавать и назначать пользовательские политики.</span><span class="sxs-lookup"><span data-stu-id="11291-109">For users, you can use the global (Org-wide default) policy or create and assign custom policies.</span></span> <span data-ttu-id="11291-110">Пользователи будут автоматически получать глобальную политику, если вы не создадите и не назначаете пользовательскую политику.</span><span class="sxs-lookup"><span data-stu-id="11291-110">Users will automatically get the global policy unless you create and assign a custom policy.</span></span> <span data-ttu-id="11291-111">Имейте в виду, что вы можете изменять параметры глобальной политики, но переименовывать и удалять их нельзя.</span><span class="sxs-lookup"><span data-stu-id="11291-111">Keep in mind that you can edit the settings in the global policy but you can't rename or delete it.</span></span> <span data-ttu-id="11291-112">Для сетевых сайтов можно создавать и назначать пользовательские политики.</span><span class="sxs-lookup"><span data-stu-id="11291-112">For network sites, you create and assign custom policies.</span></span>

<span data-ttu-id="11291-113">Если вы назначили для сайта сети и пользователя политику вызова экстренного реагирования, и если этот пользователь находится на сайте сети, политика, назначенная сетевому сайту, переопределяет политику, назначенную пользователю.</span><span class="sxs-lookup"><span data-stu-id="11291-113">If you assigned an emergency calling policy to a network site and to a user and if that user is at that network site, the policy that's assigned to the network site overrides the policy that's assigned to the user.</span></span>

## <a name="create-a-custom-emergency-calling-policy"></a><span data-ttu-id="11291-114">Создание настраиваемой политики вызова экстренной помощи</span><span class="sxs-lookup"><span data-stu-id="11291-114">Create a custom emergency calling policy</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="11291-115">Использование центра администрирования Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="11291-115">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="11291-116">В левой области навигации центра администрирования Microsoft Teams выберите**политики** **голосовой связи** > и перейдите на вкладку **политики звонка** .</span><span class="sxs-lookup"><span data-stu-id="11291-116">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Emergency policies**, and then click the **Calling policies** tab.</span></span>
2. <span data-ttu-id="11291-117">Нажмите **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="11291-117">Click **Add**.</span></span>
3. <span data-ttu-id="11291-118">Введите имя и описание политики.</span><span class="sxs-lookup"><span data-stu-id="11291-118">Enter a name and description for the policy.</span></span>
4. <span data-ttu-id="11291-119">Укажите, как вы хотите уведомлять пользователей в вашей организации, как правило, на рабочем месте, когда производится вызов экстренной помощи.</span><span class="sxs-lookup"><span data-stu-id="11291-119">Set how you want to notify people in your organization, typically the security desk, when an emergency call is made.</span></span> <span data-ttu-id="11291-120">Для этого в разделе **режим уведомлений**выберите один из указанных ниже вариантов.</span><span class="sxs-lookup"><span data-stu-id="11291-120">To do this, under **Notification mode**, select one of the following:</span></span>
    - <span data-ttu-id="11291-121">**Только уведомления**: сообщение чата Teams отправляется указанным пользователям и группам.</span><span class="sxs-lookup"><span data-stu-id="11291-121">**Notification only**: A Teams chat message is sent to the users and groups that you specify.</span></span>
    - <span data-ttu-id="11291-122">На **конференции, но отключены**: сообщение чата в Teams отправляется указанным пользователям и группам, и оно может принимать (но не принимать участие) в беседе между вызывающим абонентом и оператором ПСАП.</span><span class="sxs-lookup"><span data-stu-id="11291-122">**Conferenced in but are muted**: A Teams chat message is sent to the users and groups that you specify and they can listen (but not participate) in the conversation between the caller and the PSAP operator.</span></span>
5.  <span data-ttu-id="11291-123">Если вы выбрали режим уведомлений, **но микрофон** отключен, в поле номер для исходящего **звонка для уведомлений** вы можете ввести телефонный номер КТСОП для пользователя или группы, чтобы позвонить и присоединиться к экстренному звонку.</span><span class="sxs-lookup"><span data-stu-id="11291-123">If you selected the **Conferenced in but are muted** notification mode, in the **Dial-out number for notifications** box, you can enter a PSTN phone number of a user or group to call and join the emergency call.</span></span> <span data-ttu-id="11291-124">Например, введите номер рабочего центра безопасности Организации, который получит звонок при совершении звонка, и затем сможет прослушать или принять участие в звонке.</span><span class="sxs-lookup"><span data-stu-id="11291-124">For example, enter the number of your organization's security desk, who will receive a call when an emergency call is made and can then listen in or participate in the call.</span></span>
6. <span data-ttu-id="11291-125">Найдите и выберите одного или нескольких пользователей или групп, например, на рабочем столе своей организации, чтобы уведомить о совершении экстренного звонка.</span><span class="sxs-lookup"><span data-stu-id="11291-125">Search for and select one or more users or groups, such as your organization's security desk, to notify when an emergency call is made.</span></span>  <span data-ttu-id="11291-126">Уведомление можно отправить адресам электронной почты пользователей, группам рассылки и группам безопасности.</span><span class="sxs-lookup"><span data-stu-id="11291-126">The notification can be sent to email addresses of users, distribution groups, and security groups.</span></span> <span data-ttu-id="11291-127">Максимальное количество пользователей 50, которые могут быть уведомлены.</span><span class="sxs-lookup"><span data-stu-id="11291-127">A maximum of 50 users can be notified.</span></span>
7. <span data-ttu-id="11291-128">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="11291-128">Click **Save**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="11291-129">Использование PowerShell</span><span class="sxs-lookup"><span data-stu-id="11291-129">Using PowerShell</span></span>

<span data-ttu-id="11291-130">Просмотреть раздел [New-кстеамсемерженцикаллингполици](https://docs.microsoft.com/powershell/module/skype/new-csteamsemergencycallingpolicy).</span><span class="sxs-lookup"><span data-stu-id="11291-130">See [New-CsTeamsEmergencyCallingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsemergencycallingpolicy).</span></span>

## <a name="edit-an-emergency-calling-policy"></a><span data-ttu-id="11291-131">Изменение политики вызова экстренной помощи</span><span class="sxs-lookup"><span data-stu-id="11291-131">Edit an emergency calling policy</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="11291-132">Использование центра администрирования Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="11291-132">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="11291-133">Вы можете изменить глобальную политику или созданные вами пользовательские политики.</span><span class="sxs-lookup"><span data-stu-id="11291-133">You can edit the global policy or any custom policies that you create.</span></span>

1. <span data-ttu-id="11291-134">В левой области навигации центра администрирования Microsoft Teams выберите**политики** **голосовой связи** > и перейдите на вкладку **политики звонка** .</span><span class="sxs-lookup"><span data-stu-id="11291-134">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Emergency policies**, and then click the **Calling policies** tab.</span></span>
2. <span data-ttu-id="11291-135">Выберите политику, щелкнув слева от ее имени, а затем нажмите кнопку **изменить**.</span><span class="sxs-lookup"><span data-stu-id="11291-135">Select the policy by clicking to the left of the policy name, and then click **Edit**.</span></span>
3. <span data-ttu-id="11291-136">Внесите нужные изменения и нажмите кнопку **сохранить**.</span><span class="sxs-lookup"><span data-stu-id="11291-136">Make the changes that you want, and then click **Save**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="11291-137">Использование PowerShell</span><span class="sxs-lookup"><span data-stu-id="11291-137">Using PowerShell</span></span>

<span data-ttu-id="11291-138">Смотрите раздел [Set-кстеамсемерженцикаллингполици](https://docs.microsoft.com/powershell/module/skype/set-csteamsemergencycallingpolicy).</span><span class="sxs-lookup"><span data-stu-id="11291-138">See [Set-CsTeamsEmergencyCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsemergencycallingpolicy).</span></span>

## <a name="assign-a-custom-emergency-calling-policy-to-users"></a><span data-ttu-id="11291-139">Назначение настраиваемой политики вызова экстренной помощи пользователям</span><span class="sxs-lookup"><span data-stu-id="11291-139">Assign a custom emergency calling policy to users</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="11291-140">Использование центра администрирования Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="11291-140">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="11291-141">В левой области навигации центра администрирования Microsoft Teams перейдите в раздел **Пользователи**и выберите пользователя.</span><span class="sxs-lookup"><span data-stu-id="11291-141">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click the user.</span></span>
2. <span data-ttu-id="11291-142">Нажмите **политики**, а затем рядом с пунктом **назначенные политики**нажмите кнопку **изменить**.</span><span class="sxs-lookup"><span data-stu-id="11291-142">Click **Policies**, and then next to **Assigned policies**, click **Edit**.</span></span>
3. <span data-ttu-id="11291-143">В разделе **политика вызова экстренного**реагирования выберите политику, которую вы хотите назначить, и нажмите кнопку **сохранить**.</span><span class="sxs-lookup"><span data-stu-id="11291-143">Under **Emergency calling policy**, select the policy you want to assign, and then click **Save**.</span></span>

<span data-ttu-id="11291-144">Чтобы назначить специальную политику групп нескольким пользователям одновременно, ознакомьтесь с [разгруппым изменением параметров пользователей Teams](edit-user-settings-in-bulk.md).</span><span class="sxs-lookup"><span data-stu-id="11291-144">To assign a custom teams policy to multiple users at a time, see [Edit Teams user settings in bulk](edit-user-settings-in-bulk.md).</span></span>

<span data-ttu-id="11291-145">Кроме того, вы можете сделать следующее:</span><span class="sxs-lookup"><span data-stu-id="11291-145">Or, you can also do the following:</span></span>

1. <span data-ttu-id="11291-146">В левой области навигации центра администрирования Microsoft Teams выберите**политики** **голосовой связи** > и перейдите на вкладку **политики звонка** .</span><span class="sxs-lookup"><span data-stu-id="11291-146">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Emergency policies**, and then click the **Calling policies** tab.</span></span>
2. <span data-ttu-id="11291-147">Выберите политику, щелкнув слева от имени политики.</span><span class="sxs-lookup"><span data-stu-id="11291-147">Select the policy by clicking to the left of the policy name.</span></span>
3. <span data-ttu-id="11291-148">Выберите **Управление пользователями**.</span><span class="sxs-lookup"><span data-stu-id="11291-148">Select **Manage users**.</span></span>
4. <span data-ttu-id="11291-149">В области **Управление пользователями** найдите пользователя по отображаемому имени или по имени пользователя, выберите имя и нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="11291-149">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then select **Add**.</span></span> <span data-ttu-id="11291-150">Повторите этот шаг для каждого пользователя, которого вы хотите добавить.</span><span class="sxs-lookup"><span data-stu-id="11291-150">Repeat this step for each user that you want to add.</span></span>
5. <span data-ttu-id="11291-151">Завершив добавление пользователей, нажмите кнопку **сохранить**.</span><span class="sxs-lookup"><span data-stu-id="11291-151">When you're finished adding users, click **Save**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="11291-152">Использование PowerShell</span><span class="sxs-lookup"><span data-stu-id="11291-152">Using PowerShell</span></span>

#### <a name="assign-a-custom-emergency-calling-policy-to-a-user"></a><span data-ttu-id="11291-153">Назначение пользователю пользовательской политики вызова экстренной помощи</span><span class="sxs-lookup"><span data-stu-id="11291-153">Assign a custom emergency calling policy to a user</span></span>

<span data-ttu-id="11291-154">Просмотр [Grant-кстеамсемерженцикаллингполици](https://docs.microsoft.com/powershell/module/skype/grant-csteamsemergencycallingpolicy).</span><span class="sxs-lookup"><span data-stu-id="11291-154">See [Grant-CsTeamsEmergencyCallingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsemergencycallingpolicy).</span></span>

#### <a name="assign-a-custom-emergency-calling-policy-to-users-in-a-group"></a><span data-ttu-id="11291-155">Назначение настраиваемой политики вызова для экстренного реагирования пользователям в группе</span><span class="sxs-lookup"><span data-stu-id="11291-155">Assign a custom emergency calling policy to users in a group</span></span>

<span data-ttu-id="11291-156">Вы можете назначить специальную политику для вызова экстренной помощи нескольким пользователям, которые уже были идентифицированы.</span><span class="sxs-lookup"><span data-stu-id="11291-156">You may want to assign a custom emergency calling policy to multiple users that you’ve already identified.</span></span> <span data-ttu-id="11291-157">Например, может потребоваться назначить политику всем пользователям в группе безопасности.</span><span class="sxs-lookup"><span data-stu-id="11291-157">For example, you may want to assign a policy to all users in a security group.</span></span> <span data-ttu-id="11291-158">Это можно сделать, подключив службу Azure Active Directory PowerShell для Graph и модуль PowerShell для Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="11291-158">You can do this by connecting to the Azure Active Directory PowerShell for Graph module and the Skype for Business PowerShell module.</span></span>

<span data-ttu-id="11291-159">В этом примере мы назначаем политику, которая называется политикой вызова экстренных операций, всем пользователям в группе "операции Contoso".</span><span class="sxs-lookup"><span data-stu-id="11291-159">In this example, we assign a policy called Operations Emergency Calling Policy to all users in the Contoso Operations group.</span></span>  

> [!NOTE]
> <span data-ttu-id="11291-160">Убедитесь, что вы подключаетесь к модулю Azure Active Directory PowerShell для модуля Graph и Skype для бизнеса PowerShell, выполнив действия, описанные в разделе [подключение ко всем службам Office 365 в одном окне Windows PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).</span><span class="sxs-lookup"><span data-stu-id="11291-160">Make sure you first connect to the Azure Active Directory PowerShell for Graph module and Skype for Business PowerShell module by following the steps in [Connect to all Office 365 services in a single Windows PowerShell window](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).</span></span>

<span data-ttu-id="11291-161">Получить Граупобжектид определенной группы.</span><span class="sxs-lookup"><span data-stu-id="11291-161">Get the GroupObjectId of the particular group.</span></span>
```
$group = Get-AzureADGroup -SearchString "Contoso Operations"
```
<span data-ttu-id="11291-162">Получение участников указанной группы.</span><span class="sxs-lookup"><span data-stu-id="11291-162">Get the members of the specified group.</span></span>
```
$members = Get-AzureADGroupMember -ObjectId $group.ObjectId -All $true | Where-Object {$_.ObjectType -eq "User"}
```
<span data-ttu-id="11291-163">Назначьте всем пользователям в группе определенную политику групп.</span><span class="sxs-lookup"><span data-stu-id="11291-163">Assign all users in the group to a particular teams policy.</span></span> <span data-ttu-id="11291-164">В этом примере выполняется операция политики маршрутизации вызова экстренной помощи.</span><span class="sxs-lookup"><span data-stu-id="11291-164">In this example, it's Operations Emergency Call Routing Policy.</span></span>
```
$members | ForEach-Object { Grant-CsTeamsChannelsPolicy -PolicyName "Operations Emergency Calling Policy" -Identity $_.UserPrincipalName}
``` 
<span data-ttu-id="11291-165">Для выполнения этой команды может потребоваться несколько минут в зависимости от количества участников в группе.</span><span class="sxs-lookup"><span data-stu-id="11291-165">Depending on the number of members in the group, this command may take several minutes to execute.</span></span>

## <a name="assign-a-custom-emergency-calling-policy-to-a-network-site"></a><span data-ttu-id="11291-166">Назначение настраиваемой политики вызова для экстренного реагирования сетевому сайту</span><span class="sxs-lookup"><span data-stu-id="11291-166">Assign a custom emergency calling policy to a network site</span></span>

<span data-ttu-id="11291-167">Используйте командлет [Set-кстенантнетворксите](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite) , чтобы назначить политику вызова экстренной помощи на сайте сети.</span><span class="sxs-lookup"><span data-stu-id="11291-167">Use the [Set-CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite) cmdlet to assign an emergency calling policy to a network site.</span></span>

<span data-ttu-id="11291-168">В следующем примере показано, как назначить политику, которая называется политикой вызова экстренной помощи Contoso 1, на сайт site1.</span><span class="sxs-lookup"><span data-stu-id="11291-168">The following example shows how to assign a policy called Contoso Emergency Calling Policy 1 to the Site1 site.</span></span>

    ```
    Set-CsTenantNetworkSite -identity "site1" -EmergencyCallingPolicy "Contoso Emergency Calling Policy 1"
    ```

## <a name="related-topics"></a><span data-ttu-id="11291-169">См. также</span><span class="sxs-lookup"><span data-stu-id="11291-169">Related topics</span></span>

- [<span data-ttu-id="11291-170">Управление политиками маршрутизации вызова экстренной помощи в Teams</span><span class="sxs-lookup"><span data-stu-id="11291-170">Manage emergency call routing policies in Teams</span></span>](manage-emergency-call-routing-policies.md)
- [<span data-ttu-id="11291-171">Обзор PowerShell в Teams</span><span class="sxs-lookup"><span data-stu-id="11291-171">Teams PowerShell overview</span></span>](teams-powershell-overview.md)
