---
title: Управление политиками экстренных вызовов в Microsoft Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: jastark, roykuntz
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-voice
f1.keywords:
- CSH
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Узнайте, как использовать политики экстренных вызовов и управлять ими в Microsoft Teams, чтобы определить, что происходит, когда Teams в вашей организации совершает экстренный звонок.
ms.custom:
- seo-marvel-apr2020
- ms.teamsadmincenter.voice.emergencycallingpolicies.overview
ms.openlocfilehash: 34f6e901049dd080ee070e7858f24b70535ee189
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120570"
---
# <a name="manage-emergency-calling-policies-in-microsoft-teams"></a><span data-ttu-id="45f2a-103">Управление политиками экстренных вызовов в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="45f2a-103">Manage emergency calling policies in Microsoft Teams</span></span>

<span data-ttu-id="45f2a-104">Если в [](set-up-calling-plans.md) вашей организации используются планы звонков или развернута прямая маршрутизации [телефонная система,](direct-routing-landing-page.md)вы можете использовать политики экстренных вызовов в Microsoft Teams для определения того, что происходит, когда Teams в организации звонит.</span><span class="sxs-lookup"><span data-stu-id="45f2a-104">If your organization uses [Calling Plans](set-up-calling-plans.md) or deployed [Phone System Direct Routing](direct-routing-landing-page.md), you can use emergency calling policies in Microsoft Teams to define what happens when a Teams user in your organization makes an emergency call.</span></span> <span data-ttu-id="45f2a-105">Вы можете настроить, кому уведомлять и как он получает уведомления, когда пользователь, которому назначена политика, звонит в экстренные службы.</span><span class="sxs-lookup"><span data-stu-id="45f2a-105">You can set who to notify and how they are notified when a user who is assigned the policy calls emergency services.</span></span> <span data-ttu-id="45f2a-106">Например, вы можете настроить параметры политики для автоматического уведомления сотрудников службы безопасности организации и их прослушивания во время экстренных звонков.</span><span class="sxs-lookup"><span data-stu-id="45f2a-106">For example, you can configure policy settings to automatically notify your organization's security desk and have them listen in emergency calls.</span></span>  

<span data-ttu-id="45f2a-107">Управлять политиками экстренных вызовов можно в центре администрирования Microsoft Teams или с помощью   >   Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="45f2a-107">You manage emergency calling policies by going to **Voice** > **Emergency policies** in the Microsoft Teams admin center or by using Windows PowerShell.</span></span> <span data-ttu-id="45f2a-108">Политики могут быть назначены пользователям и [сетевым сайтам.](cloud-voice-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="45f2a-108">The policies can be assigned to users and [network sites](cloud-voice-network-settings.md).</span></span>

<span data-ttu-id="45f2a-109">Для пользователей можно использовать глобальную (стандартную для всей организации) политику или создавать и назначать настраиваемые политики.</span><span class="sxs-lookup"><span data-stu-id="45f2a-109">For users, you can use the global (Org-wide default) policy or create and assign custom policies.</span></span> <span data-ttu-id="45f2a-110">Пользователи будут автоматически получать глобальную политику, если только вы не создайте и не назначите настраиваемую политику.</span><span class="sxs-lookup"><span data-stu-id="45f2a-110">Users will automatically get the global policy unless you create and assign a custom policy.</span></span> <span data-ttu-id="45f2a-111">Имейте в виду, что вы можете изменить параметры глобальной политики, но не можете переименовать или удалить ее.</span><span class="sxs-lookup"><span data-stu-id="45f2a-111">Keep in mind that you can edit the settings in the global policy but you can't rename or delete it.</span></span> <span data-ttu-id="45f2a-112">Для сетевых сайтов создаются и назначаются настраиваемые политики.</span><span class="sxs-lookup"><span data-stu-id="45f2a-112">For network sites, you create and assign custom policies.</span></span>

<span data-ttu-id="45f2a-113">Если политика экстренных вызовов назначена сетевому сайту и пользователю, а этот пользователь находится на этом сайте, политика, назначенная сетевому сайту, переопределит политику, назначенную пользователю.</span><span class="sxs-lookup"><span data-stu-id="45f2a-113">If you assigned an emergency calling policy to a network site and to a user and if that user is at that network site, the policy that's assigned to the network site overrides the policy that's assigned to the user.</span></span>

## <a name="create-a-custom-emergency-calling-policy"></a><span data-ttu-id="45f2a-114">Создание настраиваемой политики звонков в экстренные службы</span><span class="sxs-lookup"><span data-stu-id="45f2a-114">Create a custom emergency calling policy</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="45f2a-115">С помощью Центра администрирования Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="45f2a-115">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="45f2a-116">В левой области навигации Центра администрирования Microsoft Teams перейдите к центру Политики для экстренного вызова голосовой почты и перейдите на  >   **вкладку Политики звонков.**</span><span class="sxs-lookup"><span data-stu-id="45f2a-116">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Emergency policies**, and then click the **Calling policies** tab.</span></span>
2. <span data-ttu-id="45f2a-117">Нажмите **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="45f2a-117">Click **Add**.</span></span>
3. <span data-ttu-id="45f2a-118">Введите имя и описание для политики.</span><span class="sxs-lookup"><span data-stu-id="45f2a-118">Enter a name and description for the policy.</span></span>
4. <span data-ttu-id="45f2a-119">Настройка оповещать сотрудников организации (как правило, службу безопасности) о звонках в экстренные службы.</span><span class="sxs-lookup"><span data-stu-id="45f2a-119">Set how you want to notify people in your organization, typically the security desk, when an emergency call is made.</span></span> <span data-ttu-id="45f2a-120">Для этого в **режиме уведомлений** выберите один из следующих ок.</span><span class="sxs-lookup"><span data-stu-id="45f2a-120">To do this, under **Notification mode**, select one of the following:</span></span>
    - <span data-ttu-id="45f2a-121">**Только отправка уведомления:** Teams чата отправляется пользователям и группам, которые вы указали.</span><span class="sxs-lookup"><span data-stu-id="45f2a-121">**Send notification only**: A Teams chat message is sent to the users and groups that you specify.</span></span>
    - <span data-ttu-id="45f2a-122">**Конференц-связь** с отключенным звуком и неудалась: пользователям и группам отправляется сообщение чата Teams, которое позволяет прослушивать беседу между звонив и оператором PSAP (но не участвовать в ней).</span><span class="sxs-lookup"><span data-stu-id="45f2a-122">**Conferenced in muted and unable to unmute**: A Teams chat message is sent to the users and groups that you specify and they can listen (but not participate) in the conversation between the caller and the PSAP operator.</span></span>
    - <span data-ttu-id="45f2a-123">**Конференц-связь** отключена, но вы можете включать звук: пользователям и группам отправляется Teams чата, и они могут включать звук, чтобы прослушать беседу между звонив и оператором PSAP.</span><span class="sxs-lookup"><span data-stu-id="45f2a-123">**Conferenced in muted but are able to unmute**: A Teams chat message is sent to the users and groups that you specify and they can unmute to listen and participate in the conversation between the caller and the PSAP operator.</span></span>
5.  <span data-ttu-id="45f2a-124">Если вы выбрали конференц-зал в режиме отключенных  уведомлений, в поле Номера для набора для уведомлений о экстренных звонках можно ввести номер телефона ЗВОНКОВ пользователя или группы, чтобы позвонить и присоединиться к нему. </span><span class="sxs-lookup"><span data-stu-id="45f2a-124">If you selected either of the **Conference in muted** notification modes, in the **Numbers to dial for emergency calls notifications** box, you can enter a PSTN phone number of a user or group to call and join the emergency call.</span></span> <span data-ttu-id="45f2a-125">Например, введите номер службы безопасности вашей организации, который будет принимать звонок при звонках на экстренные вызовы и сможет прослушивать их.</span><span class="sxs-lookup"><span data-stu-id="45f2a-125">For example, enter the number of your organization's security desk, who will receive a call when an emergency call is made and can then listen in on the call.</span></span> <span data-ttu-id="45f2a-126">Телефон ДНР не может быть переключен, даже если для режима установлено отключение звука Конференц-связи, но он может **быть отключен.**</span><span class="sxs-lookup"><span data-stu-id="45f2a-126">The PSTN phone cannot be unmuted even when the mode is set to **Conferenced in muted but are able to unmute**.</span></span>
6. <span data-ttu-id="45f2a-127">Найди и выберите одного или несколько пользователей или групп, например службу безопасности вашей организации, чтобы уведомить об этом экстренные вызовы.</span><span class="sxs-lookup"><span data-stu-id="45f2a-127">Search for and select one or more users or groups, such as your organization's security desk, to notify when an emergency call is made.</span></span>  <span data-ttu-id="45f2a-128">Уведомление можно отправлять на адреса электронной почты пользователей, групп рассылки и групп безопасности.</span><span class="sxs-lookup"><span data-stu-id="45f2a-128">The notification can be sent to email addresses of users, distribution groups, and security groups.</span></span> <span data-ttu-id="45f2a-129">Уведомление может получить не более 50 пользователей.</span><span class="sxs-lookup"><span data-stu-id="45f2a-129">A maximum of 50 users can be notified.</span></span>
7. <span data-ttu-id="45f2a-130">Нажмите кнопку **Применить**.</span><span class="sxs-lookup"><span data-stu-id="45f2a-130">Click **Apply**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="45f2a-131">С помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="45f2a-131">Using PowerShell</span></span>

<span data-ttu-id="45f2a-132">См. [new-CsTeamsEmergencyCallingPolicy.](/powershell/module/skype/new-csteamsemergencycallingpolicy)</span><span class="sxs-lookup"><span data-stu-id="45f2a-132">See [New-CsTeamsEmergencyCallingPolicy](/powershell/module/skype/new-csteamsemergencycallingpolicy).</span></span>

## <a name="edit-an-emergency-calling-policy"></a><span data-ttu-id="45f2a-133">Изменение политики экстренных вызовов</span><span class="sxs-lookup"><span data-stu-id="45f2a-133">Edit an emergency calling policy</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="45f2a-134">С помощью Центра администрирования Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="45f2a-134">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="45f2a-135">Вы можете изменить глобальную политику или любые настраиваемые политики, которые вы создаете.</span><span class="sxs-lookup"><span data-stu-id="45f2a-135">You can edit the global policy or any custom policies that you create.</span></span>

1. <span data-ttu-id="45f2a-136">В левой области навигации Центра администрирования Microsoft Teams перейдите к центру Политики для экстренного вызова голосовой почты и перейдите на  >   **вкладку Политики звонков.**</span><span class="sxs-lookup"><span data-stu-id="45f2a-136">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Emergency policies**, and then click the **Calling policies** tab.</span></span>
2. <span data-ttu-id="45f2a-137">Выберите политику, щелкнув слева от ее имени, а затем нажмите **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="45f2a-137">Select the policy by clicking to the left of the policy name, and then click **Edit**.</span></span>
3. <span data-ttu-id="45f2a-138">Внесите нужные изменения и нажмите кнопку **Применить**.</span><span class="sxs-lookup"><span data-stu-id="45f2a-138">Make the changes that you want, and then click **Apply**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="45f2a-139">С помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="45f2a-139">Using PowerShell</span></span>

<span data-ttu-id="45f2a-140">См. [set-CsTeamsEmergencyCallingPolicy.](/powershell/module/skype/set-csteamsemergencycallingpolicy)</span><span class="sxs-lookup"><span data-stu-id="45f2a-140">See [Set-CsTeamsEmergencyCallingPolicy](/powershell/module/skype/set-csteamsemergencycallingpolicy).</span></span>

## <a name="assign-a-custom-emergency-calling-policy-to-users"></a><span data-ttu-id="45f2a-141">Назначение пользовательской политики экстренных вызовов пользователям</span><span class="sxs-lookup"><span data-stu-id="45f2a-141">Assign a custom emergency calling policy to users</span></span>

[!INCLUDE [assign-policy](includes/assign-policy.md)]

<span data-ttu-id="45f2a-142">См. [также Grant-CsTeamsEmergencyCallingPolicy.](/powershell/module/skype/grant-csteamsemergencycallingpolicy)</span><span class="sxs-lookup"><span data-stu-id="45f2a-142">See also [Grant-CsTeamsEmergencyCallingPolicy](/powershell/module/skype/grant-csteamsemergencycallingpolicy).</span></span>

## <a name="assign-a-custom-emergency-calling-policy-to-a-network-site"></a><span data-ttu-id="45f2a-143">Назначение настраиваемой политики экстренных вызовов на сетевом сайте</span><span class="sxs-lookup"><span data-stu-id="45f2a-143">Assign a custom emergency calling policy to a network site</span></span>

<span data-ttu-id="45f2a-144">Используйте [командлет Set-CsTenantNetworkSite,](/powershell/module/skype/set-cstenantnetworksite) чтобы назначить политику экстренных вызовов сетевому сайту.</span><span class="sxs-lookup"><span data-stu-id="45f2a-144">Use the [Set-CsTenantNetworkSite](/powershell/module/skype/set-cstenantnetworksite) cmdlet to assign an emergency calling policy to a network site.</span></span>

<span data-ttu-id="45f2a-145">В следующем примере показано, как назначить сайту Site1 политику contoso emergency Calling Policy 1.</span><span class="sxs-lookup"><span data-stu-id="45f2a-145">The following example shows how to assign a policy called Contoso Emergency Calling Policy 1 to the Site1 site.</span></span>

```powershell
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallingPolicy "Contoso Emergency Calling Policy 1"
```

## <a name="related-topics"></a><span data-ttu-id="45f2a-146">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="45f2a-146">Related topics</span></span>

[<span data-ttu-id="45f2a-147">Управление политиками маршрутизов экстренных вызовов в Teams</span><span class="sxs-lookup"><span data-stu-id="45f2a-147">Manage emergency call routing policies in Teams</span></span>](manage-emergency-call-routing-policies.md)

[<span data-ttu-id="45f2a-148">Обзор PowerShell в Teams</span><span class="sxs-lookup"><span data-stu-id="45f2a-148">Teams PowerShell overview</span></span>](teams-powershell-overview.md)

[<span data-ttu-id="45f2a-149">Назначение политик пользователям в Teams</span><span class="sxs-lookup"><span data-stu-id="45f2a-149">Assign policies to your users in Teams</span></span>](assign-policies.md)