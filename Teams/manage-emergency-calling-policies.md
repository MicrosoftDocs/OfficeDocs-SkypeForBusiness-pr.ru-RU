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
f1.keywords: ms.teamsadmincenter.voice.emergencycallingpolicies.overview
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Сведения о том, как использовать политики вызова экстренной помощи и управлять ими в Microsoft Teams, чтобы определить, что происходит, когда пользователь Teams в организации осуществляет вызов экстренной помощи.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 79332a8675273e86476a68f43489c202b03faea9
ms.sourcegitcommit: 3323c86f31c5ab304944a34892601fcc7b448025
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "44638688"
---
# <a name="manage-emergency-calling-policies-in-microsoft-teams"></a><span data-ttu-id="060c8-103">Управление политиками вызова экстренной помощи в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="060c8-103">Manage emergency calling policies in Microsoft Teams</span></span>

<span data-ttu-id="060c8-104">Если в вашей организации используются [планы звонков](set-up-calling-plans.md) или [Прямая маршрутизация на телефонную систему](direct-routing-landing-page.md), вы можете использовать политики вызова экстренной помощи в Microsoft Teams, чтобы определить, что происходит, когда пользователь Teams в организации осуществляет вызов экстренной помощи.</span><span class="sxs-lookup"><span data-stu-id="060c8-104">If your organization uses [Calling Plans](set-up-calling-plans.md) or deployed [Phone System Direct Routing](direct-routing-landing-page.md), you can use emergency calling policies in Microsoft Teams to define what happens when a Teams user in your organization makes an emergency call.</span></span> <span data-ttu-id="060c8-105">Вы можете настроить пользователей, которые должны уведомлять и как они уведомляются, когда пользователь, которому назначена эта политика, вызывает экстренные службы.</span><span class="sxs-lookup"><span data-stu-id="060c8-105">You can set who to notify and how they are notified when a user who is assigned the policy calls emergency services.</span></span> <span data-ttu-id="060c8-106">Например, вы можете настроить параметры политики, чтобы автоматически уведомлять службу безопасности Организации и принимать их в экстренных звонках.</span><span class="sxs-lookup"><span data-stu-id="060c8-106">For example, you can configure policy settings to automatically notify your organization's security desk and have them listen in emergency calls.</span></span>  

<span data-ttu-id="060c8-107">Управление политиками вызова экстренной помощи осуществляется путем перехода на политики **голосовой связи**  >  **Emergency policies** в центре администрирования Microsoft Teams или с помощью Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="060c8-107">You manage emergency calling policies by going to **Voice** > **Emergency policies** in the Microsoft Teams admin center or by using Windows PowerShell.</span></span> <span data-ttu-id="060c8-108">Политики можно назначить для пользователей и [сайтов сети](cloud-voice-network-settings.md).</span><span class="sxs-lookup"><span data-stu-id="060c8-108">The policies can be assigned to users and [network sites](cloud-voice-network-settings.md).</span></span>

<span data-ttu-id="060c8-109">Пользователи могут использовать глобальную политику (по умолчанию на уровне Организации) или создавать и назначать пользовательские политики.</span><span class="sxs-lookup"><span data-stu-id="060c8-109">For users, you can use the global (Org-wide default) policy or create and assign custom policies.</span></span> <span data-ttu-id="060c8-110">Пользователи будут автоматически получать глобальную политику, если вы не создадите и не назначаете пользовательскую политику.</span><span class="sxs-lookup"><span data-stu-id="060c8-110">Users will automatically get the global policy unless you create and assign a custom policy.</span></span> <span data-ttu-id="060c8-111">Имейте в виду, что вы можете изменять параметры глобальной политики, но переименовывать и удалять их нельзя.</span><span class="sxs-lookup"><span data-stu-id="060c8-111">Keep in mind that you can edit the settings in the global policy but you can't rename or delete it.</span></span> <span data-ttu-id="060c8-112">Для сетевых сайтов можно создавать и назначать пользовательские политики.</span><span class="sxs-lookup"><span data-stu-id="060c8-112">For network sites, you create and assign custom policies.</span></span>

<span data-ttu-id="060c8-113">Если вы назначили для сайта сети и пользователя политику вызова экстренного реагирования, и если этот пользователь находится на сайте сети, политика, назначенная сетевому сайту, переопределяет политику, назначенную пользователю.</span><span class="sxs-lookup"><span data-stu-id="060c8-113">If you assigned an emergency calling policy to a network site and to a user and if that user is at that network site, the policy that's assigned to the network site overrides the policy that's assigned to the user.</span></span>

## <a name="create-a-custom-emergency-calling-policy"></a><span data-ttu-id="060c8-114">Создание настраиваемой политики вызова экстренной помощи</span><span class="sxs-lookup"><span data-stu-id="060c8-114">Create a custom emergency calling policy</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="060c8-115">С помощью Центра администрирования Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="060c8-115">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="060c8-116">В левой области навигации центра администрирования Microsoft Teams выберите политики **голосовой связи**  >  **Emergency policies**и перейдите на вкладку **политики звонка** .</span><span class="sxs-lookup"><span data-stu-id="060c8-116">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Emergency policies**, and then click the **Calling policies** tab.</span></span>
2. <span data-ttu-id="060c8-117">Нажмите **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="060c8-117">Click **Add**.</span></span>
3. <span data-ttu-id="060c8-118">Введите имя и описание для политики.</span><span class="sxs-lookup"><span data-stu-id="060c8-118">Enter a name and description for the policy.</span></span>
4. <span data-ttu-id="060c8-119">Укажите, как вы хотите уведомлять пользователей в вашей организации, как правило, на рабочем месте, когда производится вызов экстренной помощи.</span><span class="sxs-lookup"><span data-stu-id="060c8-119">Set how you want to notify people in your organization, typically the security desk, when an emergency call is made.</span></span> <span data-ttu-id="060c8-120">Для этого в разделе **режим уведомлений**выберите один из указанных ниже вариантов.</span><span class="sxs-lookup"><span data-stu-id="060c8-120">To do this, under **Notification mode**, select one of the following:</span></span>
    - <span data-ttu-id="060c8-121">**Только уведомление об отправке**: сообщение чата Teams отправляется указанным пользователям и группам.</span><span class="sxs-lookup"><span data-stu-id="060c8-121">**Send notification only**: A Teams chat message is sent to the users and groups that you specify.</span></span>
    - <span data-ttu-id="060c8-122">На **конференции, но отключены**: сообщение чата в Teams отправляется указанным пользователям и группам, и оно может принимать (но не принимать участие) в беседе между вызывающим абонентом и оператором PSAP.</span><span class="sxs-lookup"><span data-stu-id="060c8-122">**Conferenced in but are muted**: A Teams chat message is sent to the users and groups that you specify and they can listen (but not participate) in the conversation between the caller and the PSAP operator.</span></span>
    - <span data-ttu-id="060c8-123">Адресованные **и отключенные конференции** **(скоро)**: сообщение чата команды отправляется пользователям и указанным группам и может включать и отключать звук для прослушивания и участия в разговоре между вызывающим абонентом и оператором PSAP.</span><span class="sxs-lookup"><span data-stu-id="060c8-123">**Conferenced in and are unmuted** **(coming soon)**: A Teams chat message is sent to the users and groups that you specify and they can unmute to listen and participate in the conversation between the caller and the PSAP operator.</span></span>
5.  <span data-ttu-id="060c8-124">Если вы выбрали режим уведомлений, **но микрофон** отключен, в поле **Номера для звонков по экстренным** звонкам вы можете ввести телефонный номер КТСОП для пользователя или группы, чтобы позвонить и присоединиться к экстренному звонку.</span><span class="sxs-lookup"><span data-stu-id="060c8-124">If you selected the **Conferenced in but are muted** notification mode, in the **Numbers to dial for emergency calls notifications** box, you can enter a PSTN phone number of a user or group to call and join the emergency call.</span></span> <span data-ttu-id="060c8-125">Например, введите номер рабочего центра безопасности Организации, который получит звонок при совершении звонка, и затем может прослушать звонок.</span><span class="sxs-lookup"><span data-stu-id="060c8-125">For example, enter the number of your organization's security desk, who will receive a call when an emergency call is made and can then listen in on the call.</span></span>
6. <span data-ttu-id="060c8-126">Найдите и выберите одного или нескольких пользователей или групп, например, на рабочем столе своей организации, чтобы уведомить о совершении экстренного звонка.</span><span class="sxs-lookup"><span data-stu-id="060c8-126">Search for and select one or more users or groups, such as your organization's security desk, to notify when an emergency call is made.</span></span>  <span data-ttu-id="060c8-127">Уведомление можно отправить адресам электронной почты пользователей, группам рассылки и группам безопасности.</span><span class="sxs-lookup"><span data-stu-id="060c8-127">The notification can be sent to email addresses of users, distribution groups, and security groups.</span></span> <span data-ttu-id="060c8-128">Максимальное количество пользователей 50, которые могут быть уведомлены.</span><span class="sxs-lookup"><span data-stu-id="060c8-128">A maximum of 50 users can be notified.</span></span>
7. <span data-ttu-id="060c8-129">Нажмите кнопку **Применить**.</span><span class="sxs-lookup"><span data-stu-id="060c8-129">Click **Apply**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="060c8-130">Использование PowerShell</span><span class="sxs-lookup"><span data-stu-id="060c8-130">Using PowerShell</span></span>

<span data-ttu-id="060c8-131">Просмотреть раздел [New-CsTeamsEmergencyCallingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsemergencycallingpolicy).</span><span class="sxs-lookup"><span data-stu-id="060c8-131">See [New-CsTeamsEmergencyCallingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsemergencycallingpolicy).</span></span>

## <a name="edit-an-emergency-calling-policy"></a><span data-ttu-id="060c8-132">Изменение политики вызова экстренной помощи</span><span class="sxs-lookup"><span data-stu-id="060c8-132">Edit an emergency calling policy</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="060c8-133">С помощью Центра администрирования Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="060c8-133">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="060c8-134">Вы можете изменить глобальную политику или созданные вами пользовательские политики.</span><span class="sxs-lookup"><span data-stu-id="060c8-134">You can edit the global policy or any custom policies that you create.</span></span>

1. <span data-ttu-id="060c8-135">В левой области навигации центра администрирования Microsoft Teams выберите политики **голосовой связи**  >  **Emergency policies**и перейдите на вкладку **политики звонка** .</span><span class="sxs-lookup"><span data-stu-id="060c8-135">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Emergency policies**, and then click the **Calling policies** tab.</span></span>
2. <span data-ttu-id="060c8-136">Выберите политику, щелкнув слева от ее имени, а затем нажмите кнопку **изменить**.</span><span class="sxs-lookup"><span data-stu-id="060c8-136">Select the policy by clicking to the left of the policy name, and then click **Edit**.</span></span>
3. <span data-ttu-id="060c8-137">Внесите нужные изменения и нажмите кнопку **сохранить**.</span><span class="sxs-lookup"><span data-stu-id="060c8-137">Make the changes that you want, and then click **Save**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="060c8-138">Использование PowerShell</span><span class="sxs-lookup"><span data-stu-id="060c8-138">Using PowerShell</span></span>

<span data-ttu-id="060c8-139">Смотрите раздел [Set-CsTeamsEmergencyCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsemergencycallingpolicy).</span><span class="sxs-lookup"><span data-stu-id="060c8-139">See [Set-CsTeamsEmergencyCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsemergencycallingpolicy).</span></span>

## <a name="assign-a-custom-emergency-calling-policy-to-users"></a><span data-ttu-id="060c8-140">Назначение настраиваемой политики вызова экстренной помощи пользователям</span><span class="sxs-lookup"><span data-stu-id="060c8-140">Assign a custom emergency calling policy to users</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="060c8-141">С помощью Центра администрирования Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="060c8-141">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="060c8-142">Чтобы назначить политику для одного пользователя, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="060c8-142">To assign a policy to one user:</span></span>

1. <span data-ttu-id="060c8-143">В Центре администрирования Microsoft Teams в области навигации слева перейдите в раздел **Пользователи**, затем щелкните пользователя.</span><span class="sxs-lookup"><span data-stu-id="060c8-143">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click the user.</span></span>
2. <span data-ttu-id="060c8-144">Нажмите **политики**, а затем рядом с пунктом **назначенные политики**нажмите кнопку **изменить**.</span><span class="sxs-lookup"><span data-stu-id="060c8-144">Click **Policies**, and then next to **Assigned policies**, click **Edit**.</span></span>
3. <span data-ttu-id="060c8-145">В разделе **политика вызова экстренного**реагирования выберите политику, которую вы хотите назначить, и нажмите кнопку **сохранить**.</span><span class="sxs-lookup"><span data-stu-id="060c8-145">Under **Emergency calling policy**, select the policy you want to assign, and then click **Save**.</span></span>

<span data-ttu-id="060c8-146">Чтобы назначить политику нескольким пользователям одновременно:</span><span class="sxs-lookup"><span data-stu-id="060c8-146">To assign a policy to multiple users at a time:</span></span>

1. <span data-ttu-id="060c8-147">В левой области навигации Центра администрирования Microsoft Teams выберите **Пользователи** и найдите пользователей или отфильтруйте представление, чтобы отобразить нужных пользователей.</span><span class="sxs-lookup"><span data-stu-id="060c8-147">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then search for the users or filter the view to show the users you want.</span></span>
2. <span data-ttu-id="060c8-148">В столбце **&#x2713;** (галочка) выберите пользователей.</span><span class="sxs-lookup"><span data-stu-id="060c8-148">In the **&#x2713;** (check mark) column, select the users.</span></span> <span data-ttu-id="060c8-149">Чтобы выбрать всех пользователей, щелкните &#x2713; (галочку) в верхней части таблицы.</span><span class="sxs-lookup"><span data-stu-id="060c8-149">To select all users, click the &#x2713; (check mark) at the top of the table.</span></span>
3. <span data-ttu-id="060c8-150">Щелкните **Изменить настройки**, внесите нужные изменения и нажмите **Применить**.</span><span class="sxs-lookup"><span data-stu-id="060c8-150">Click **Edit settings**, make the changes that you want, and then click **Apply**.</span></span>  

<span data-ttu-id="060c8-151">Кроме того, вы можете сделать следующее:</span><span class="sxs-lookup"><span data-stu-id="060c8-151">Or, you can also do the following:</span></span>

1. <span data-ttu-id="060c8-152">В левой области навигации центра администрирования Microsoft Teams выберите политики **голосовой связи**  >  **Emergency policies**и перейдите на вкладку **политики звонка** .</span><span class="sxs-lookup"><span data-stu-id="060c8-152">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Emergency policies**, and then click the **Calling policies** tab.</span></span>
2. <span data-ttu-id="060c8-153">Выберите политику, щелкнув слева от ее имени.</span><span class="sxs-lookup"><span data-stu-id="060c8-153">Select the policy by clicking to the left of the policy name.</span></span>
3. <span data-ttu-id="060c8-154">Выберите **Управление пользователями**.</span><span class="sxs-lookup"><span data-stu-id="060c8-154">Select **Manage users**.</span></span>
4. <span data-ttu-id="060c8-155">В области **Управление пользователями** выполните поиск по отображаемому имени или по имени пользователя, выберите имя и нажмите **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="060c8-155">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then select **Add**.</span></span> <span data-ttu-id="060c8-156">Повторите это действие для каждого пользователя, которого нужно добавить.</span><span class="sxs-lookup"><span data-stu-id="060c8-156">Repeat this step for each user that you want to add.</span></span>
5. <span data-ttu-id="060c8-157">Завершив добавление пользователей, нажмите кнопку **сохранить**.</span><span class="sxs-lookup"><span data-stu-id="060c8-157">When you're finished adding users, click **Save**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="060c8-158">Использование PowerShell</span><span class="sxs-lookup"><span data-stu-id="060c8-158">Using PowerShell</span></span>

#### <a name="assign-a-custom-emergency-calling-policy-to-a-user"></a><span data-ttu-id="060c8-159">Назначение пользователю пользовательской политики вызова экстренной помощи</span><span class="sxs-lookup"><span data-stu-id="060c8-159">Assign a custom emergency calling policy to a user</span></span>

<span data-ttu-id="060c8-160">Просмотр [Grant-CsTeamsEmergencyCallingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsemergencycallingpolicy).</span><span class="sxs-lookup"><span data-stu-id="060c8-160">See [Grant-CsTeamsEmergencyCallingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsemergencycallingpolicy).</span></span>

#### <a name="assign-a-custom-emergency-calling-policy-to-users-in-a-group"></a><span data-ttu-id="060c8-161">Назначение настраиваемой политики вызова для экстренного реагирования пользователям в группе</span><span class="sxs-lookup"><span data-stu-id="060c8-161">Assign a custom emergency calling policy to users in a group</span></span>

<span data-ttu-id="060c8-162">Вы можете назначить специальную политику для вызова экстренной помощи нескольким пользователям, которые уже были идентифицированы.</span><span class="sxs-lookup"><span data-stu-id="060c8-162">You may want to assign a custom emergency calling policy to multiple users that you've already identified.</span></span> <span data-ttu-id="060c8-163">Например, может потребоваться назначить политику всем пользователям в группе безопасности.</span><span class="sxs-lookup"><span data-stu-id="060c8-163">For example, you may want to assign a policy to all users in a security group.</span></span> <span data-ttu-id="060c8-164">Это можно сделать, подключив службу Azure Active Directory PowerShell для Graph и модуль PowerShell для Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="060c8-164">You can do this by connecting to the Azure Active Directory PowerShell for Graph module and the Skype for Business PowerShell module.</span></span>

<span data-ttu-id="060c8-165">В этом примере мы назначаем политику, которая называется политикой вызова экстренных операций, всем пользователям в группе "операции Contoso".</span><span class="sxs-lookup"><span data-stu-id="060c8-165">In this example, we assign a policy called Operations Emergency Calling Policy to all users in the Contoso Operations group.</span></span>  

> [!NOTE]
> <span data-ttu-id="060c8-166">Убедитесь в том, что сначала вы подключаетесь к модулю Azure Active Directory PowerShell для модуля Graph и Skype для бизнеса PowerShell, выполнив действия, описанные в разделе [подключение ко всем службам Microsoft 365 или Office 365 в одном окне Windows PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).</span><span class="sxs-lookup"><span data-stu-id="060c8-166">Make sure you first connect to the Azure Active Directory PowerShell for Graph module and Skype for Business PowerShell module by following the steps in [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).</span></span>

<span data-ttu-id="060c8-167">Получить GroupObjectId определенной группы.</span><span class="sxs-lookup"><span data-stu-id="060c8-167">Get the GroupObjectId of the particular group.</span></span>
```powershell
$group = Get-AzureADGroup -SearchString "Contoso Operations"
```
<span data-ttu-id="060c8-168">Получение участников указанной группы.</span><span class="sxs-lookup"><span data-stu-id="060c8-168">Get the members of the specified group.</span></span>
```powershell
$members = Get-AzureADGroupMember -ObjectId $group.ObjectId -All $true | Where-Object {$_.ObjectType -eq "User"}
```
<span data-ttu-id="060c8-169">Назначьте всем пользователям в группе определенную политику групп.</span><span class="sxs-lookup"><span data-stu-id="060c8-169">Assign all users in the group to a particular teams policy.</span></span> <span data-ttu-id="060c8-170">В этом примере выполняется операция политики маршрутизации вызова экстренной помощи.</span><span class="sxs-lookup"><span data-stu-id="060c8-170">In this example, it's Operations Emergency Call Routing Policy.</span></span>
```powershell
$members | ForEach-Object {Grant-CsTeamsEmergencyCallingPolicy -PolicyName "Operations Emergency Calling Policy" -Identity $_.UserPrincipalName}
``` 
<span data-ttu-id="060c8-171">Для выполнения этой команды может потребоваться несколько минут в зависимости от количества участников в группе.</span><span class="sxs-lookup"><span data-stu-id="060c8-171">Depending on the number of members in the group, this command may take several minutes to execute.</span></span>

## <a name="assign-a-custom-emergency-calling-policy-to-a-network-site"></a><span data-ttu-id="060c8-172">Назначение настраиваемой политики вызова для экстренного реагирования сетевому сайту</span><span class="sxs-lookup"><span data-stu-id="060c8-172">Assign a custom emergency calling policy to a network site</span></span>

<span data-ttu-id="060c8-173">Используйте командлет [Set-CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite) , чтобы назначить политику вызова экстренной помощи на сайте сети.</span><span class="sxs-lookup"><span data-stu-id="060c8-173">Use the [Set-CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite) cmdlet to assign an emergency calling policy to a network site.</span></span>

<span data-ttu-id="060c8-174">В следующем примере показано, как назначить политику, которая называется политикой вызова экстренной помощи Contoso 1, на сайт site1.</span><span class="sxs-lookup"><span data-stu-id="060c8-174">The following example shows how to assign a policy called Contoso Emergency Calling Policy 1 to the Site1 site.</span></span>

```powershell
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallingPolicy "Contoso Emergency Calling Policy 1"
```

## <a name="related-topics"></a><span data-ttu-id="060c8-175">Связанные статьи</span><span class="sxs-lookup"><span data-stu-id="060c8-175">Related topics</span></span>

- [<span data-ttu-id="060c8-176">Управление политиками маршрутизации вызова экстренной помощи в Teams</span><span class="sxs-lookup"><span data-stu-id="060c8-176">Manage emergency call routing policies in Teams</span></span>](manage-emergency-call-routing-policies.md)
- [<span data-ttu-id="060c8-177">Обзор PowerShell в Teams</span><span class="sxs-lookup"><span data-stu-id="060c8-177">Teams PowerShell overview</span></span>](teams-powershell-overview.md)
- [<span data-ttu-id="060c8-178">Назначение политик пользователям в Teams</span><span class="sxs-lookup"><span data-stu-id="060c8-178">Assign policies to your users in Teams</span></span>](assign-policies.md)
