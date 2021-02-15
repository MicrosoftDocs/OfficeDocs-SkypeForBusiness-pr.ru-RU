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
description: Узнайте, как использовать политики экстренных вызовов и управлять ими в Microsoft Teams, чтобы определить, что происходит, когда пользователь Teams в вашей организации звонит.
ms.custom:
- seo-marvel-apr2020
- ms.teamsadmincenter.voice.emergencycallingpolicies.overview
ms.openlocfilehash: e58f428fbaa25b03534ce9f168ecf347b183eda3
ms.sourcegitcommit: d6e97621b1bfe9c3fbd8bc41b30a94bafd17b28f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/25/2021
ms.locfileid: "49973143"
---
# <a name="manage-emergency-calling-policies-in-microsoft-teams"></a><span data-ttu-id="abd4c-103">Управление политиками экстренных вызовов в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="abd4c-103">Manage emergency calling policies in Microsoft Teams</span></span>

<span data-ttu-id="abd4c-104">Если в [](set-up-calling-plans.md) вашей организации используются планы звонков или развернута прямая маршрутия телефонной [системы,](direct-routing-landing-page.md)вы можете использовать политики экстренных вызовов в Microsoft Teams, чтобы определить, что происходит, когда пользователь Teams в вашей организации звонит в экстренные службы.</span><span class="sxs-lookup"><span data-stu-id="abd4c-104">If your organization uses [Calling Plans](set-up-calling-plans.md) or deployed [Phone System Direct Routing](direct-routing-landing-page.md), you can use emergency calling policies in Microsoft Teams to define what happens when a Teams user in your organization makes an emergency call.</span></span> <span data-ttu-id="abd4c-105">Вы можете настроить, кому и каким образом уведомлять пользователя, которому назначена политика, в экстренные службы.</span><span class="sxs-lookup"><span data-stu-id="abd4c-105">You can set who to notify and how they are notified when a user who is assigned the policy calls emergency services.</span></span> <span data-ttu-id="abd4c-106">Например, вы можете настроить параметры политики, чтобы служба безопасности организации автоматически уведомляла сотрудников службы безопасности и прослушивала экстренные вызовы.</span><span class="sxs-lookup"><span data-stu-id="abd4c-106">For example, you can configure policy settings to automatically notify your organization's security desk and have them listen in emergency calls.</span></span>  

<span data-ttu-id="abd4c-107">Вы управляете политиками экстренных вызовов, переходить к политикам голосового экстренного вызова в Центре администрирования Microsoft Teams или с помощью   >   Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="abd4c-107">You manage emergency calling policies by going to **Voice** > **Emergency policies** in the Microsoft Teams admin center or by using Windows PowerShell.</span></span> <span data-ttu-id="abd4c-108">Политики могут быть назначены пользователям и [сетевым сайтам.](cloud-voice-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="abd4c-108">The policies can be assigned to users and [network sites](cloud-voice-network-settings.md).</span></span>

<span data-ttu-id="abd4c-109">Для пользователей можно использовать глобальную (по умолчанию в организации) политику или создавать и назначать настраиваемые политики.</span><span class="sxs-lookup"><span data-stu-id="abd4c-109">For users, you can use the global (Org-wide default) policy or create and assign custom policies.</span></span> <span data-ttu-id="abd4c-110">Пользователи будут автоматически получать глобальную политику, если вы не создайте и не назначите ее.</span><span class="sxs-lookup"><span data-stu-id="abd4c-110">Users will automatically get the global policy unless you create and assign a custom policy.</span></span> <span data-ttu-id="abd4c-111">Помните, что вы можете изменить параметры глобальной политики, но не можете переименовать или удалить ее.</span><span class="sxs-lookup"><span data-stu-id="abd4c-111">Keep in mind that you can edit the settings in the global policy but you can't rename or delete it.</span></span> <span data-ttu-id="abd4c-112">Для сетевых сайтов создаются и назначаются настраиваемые политики.</span><span class="sxs-lookup"><span data-stu-id="abd4c-112">For network sites, you create and assign custom policies.</span></span>

<span data-ttu-id="abd4c-113">Если политика экстренных вызовов назначена сетевому сайту и пользователю, а этот пользователь находится на этом сетевом сайте, политика, назначенная сетевому сайту, переопределит политику, назначенную пользователю.</span><span class="sxs-lookup"><span data-stu-id="abd4c-113">If you assigned an emergency calling policy to a network site and to a user and if that user is at that network site, the policy that's assigned to the network site overrides the policy that's assigned to the user.</span></span>

## <a name="create-a-custom-emergency-calling-policy"></a><span data-ttu-id="abd4c-114">Создание настраиваемой политики экстренных вызовов</span><span class="sxs-lookup"><span data-stu-id="abd4c-114">Create a custom emergency calling policy</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="abd4c-115">С помощью Центра администрирования Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="abd4c-115">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="abd4c-116">В левой области навигации Центра администрирования Microsoft Teams перейдите к политикам голосового экстренного вызова и перейдите на вкладку  >   **"Политики звонков".**</span><span class="sxs-lookup"><span data-stu-id="abd4c-116">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Emergency policies**, and then click the **Calling policies** tab.</span></span>
2. <span data-ttu-id="abd4c-117">Нажмите **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="abd4c-117">Click **Add**.</span></span>
3. <span data-ttu-id="abd4c-118">Введите имя и описание для политики.</span><span class="sxs-lookup"><span data-stu-id="abd4c-118">Enter a name and description for the policy.</span></span>
4. <span data-ttu-id="abd4c-119">Настройка оповещать сотрудников организации (обычно это служба безопасности) о звонках в экстренные службы.</span><span class="sxs-lookup"><span data-stu-id="abd4c-119">Set how you want to notify people in your organization, typically the security desk, when an emergency call is made.</span></span> <span data-ttu-id="abd4c-120">Для этого в режиме **уведомлений** выберите одно из следующих:</span><span class="sxs-lookup"><span data-stu-id="abd4c-120">To do this, under **Notification mode**, select one of the following:</span></span>
    - <span data-ttu-id="abd4c-121">**Только отправка уведомления.** Пользователям и группам, которые вы указываете, отправляется сообщение чата Teams.</span><span class="sxs-lookup"><span data-stu-id="abd4c-121">**Send notification only**: A Teams chat message is sent to the users and groups that you specify.</span></span>
    - <span data-ttu-id="abd4c-122">**Конференц-связь** отключена и не может быть отключена: сообщение чата Teams отправляется пользователям и группам, которые вы указываете, и они могут прослушивать (но не принимать участие) в беседе между звонив и оператором PSAP.</span><span class="sxs-lookup"><span data-stu-id="abd4c-122">**Conferenced in muted and unable to unmute**: A Teams chat message is sent to the users and groups that you specify and they can listen (but not participate) in the conversation between the caller and the PSAP operator.</span></span>
    - <span data-ttu-id="abd4c-123">**Звук** конференции отключен, но вы можете его отключать: сообщение чата Teams отправляется пользователям и группам, которые вы указали, и они могут включать звук для прослушивания беседы между звонив и оператором PSAP.</span><span class="sxs-lookup"><span data-stu-id="abd4c-123">**Conferenced in muted but are able to unmute**: A Teams chat message is sent to the users and groups that you specify and they can unmute to listen and participate in the conversation between the caller and the PSAP operator.</span></span>
5.  <span data-ttu-id="abd4c-124">Если вы выбрали любой  из конференций в режиме  отключенных уведомлений, в поле "Номера для звонка в экстренные вызовы" можно ввести номер телефона пользователя или группы по ННР, чтобы позвонить и присоединиться к звонку.</span><span class="sxs-lookup"><span data-stu-id="abd4c-124">If you selected either of the **Conference in muted** notification modes, in the **Numbers to dial for emergency calls notifications** box, you can enter a PSTN phone number of a user or group to call and join the emergency call.</span></span> <span data-ttu-id="abd4c-125">Например, введите номер службы безопасности вашей организации, который будет получать звонок при звонок в экстренные службы и сможет прослушивать звонок.</span><span class="sxs-lookup"><span data-stu-id="abd4c-125">For example, enter the number of your organization's security desk, who will receive a call when an emergency call is made and can then listen in on the call.</span></span> <span data-ttu-id="abd4c-126">Телефон ННР не может быть переключен, даже если в режиме отключен звук конференции, но он может **быть отключен.**</span><span class="sxs-lookup"><span data-stu-id="abd4c-126">The PSTN phone cannot be unmuted even when the mode is set to **Conferenced in muted but are able to unmute**.</span></span>
6. <span data-ttu-id="abd4c-127">Вы можете найти одного или несколько пользователей или групп, например службу безопасности организации, и выбрать их, чтобы уведомить об этом экстренные вызовы.</span><span class="sxs-lookup"><span data-stu-id="abd4c-127">Search for and select one or more users or groups, such as your organization's security desk, to notify when an emergency call is made.</span></span>  <span data-ttu-id="abd4c-128">Уведомление может отправляться на адреса электронной почты пользователей, групп рассылки и групп безопасности.</span><span class="sxs-lookup"><span data-stu-id="abd4c-128">The notification can be sent to email addresses of users, distribution groups, and security groups.</span></span> <span data-ttu-id="abd4c-129">Можно уведомить не более 50 пользователей.</span><span class="sxs-lookup"><span data-stu-id="abd4c-129">A maximum of 50 users can be notified.</span></span>
7. <span data-ttu-id="abd4c-130">Нажмите кнопку **Применить**.</span><span class="sxs-lookup"><span data-stu-id="abd4c-130">Click **Apply**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="abd4c-131">С помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="abd4c-131">Using PowerShell</span></span>

<span data-ttu-id="abd4c-132">См. [new-CsTeamsEmergencyCallingPolicy.](https://docs.microsoft.com/powershell/module/skype/new-csteamsemergencycallingpolicy)</span><span class="sxs-lookup"><span data-stu-id="abd4c-132">See [New-CsTeamsEmergencyCallingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsemergencycallingpolicy).</span></span>

## <a name="edit-an-emergency-calling-policy"></a><span data-ttu-id="abd4c-133">Изменение политики экстренных вызовов</span><span class="sxs-lookup"><span data-stu-id="abd4c-133">Edit an emergency calling policy</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="abd4c-134">С помощью Центра администрирования Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="abd4c-134">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="abd4c-135">Вы можете изменить глобальную политику или любые настраиваемые политики, которые вы создаете.</span><span class="sxs-lookup"><span data-stu-id="abd4c-135">You can edit the global policy or any custom policies that you create.</span></span>

1. <span data-ttu-id="abd4c-136">В левой области навигации Центра администрирования Microsoft Teams перейдите к политикам голосового экстренного вызова и перейдите на вкладку  >   **"Политики звонков".**</span><span class="sxs-lookup"><span data-stu-id="abd4c-136">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Emergency policies**, and then click the **Calling policies** tab.</span></span>
2. <span data-ttu-id="abd4c-137">Выберите политику, щелкнув слева от ее имени, а затем нажмите **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="abd4c-137">Select the policy by clicking to the left of the policy name, and then click **Edit**.</span></span>
3. <span data-ttu-id="abd4c-138">Внесите нужные изменения и нажмите кнопку **"Применить".**</span><span class="sxs-lookup"><span data-stu-id="abd4c-138">Make the changes that you want, and then click **Apply**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="abd4c-139">С помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="abd4c-139">Using PowerShell</span></span>

<span data-ttu-id="abd4c-140">См. [set-CsTeamsEmergencyCallingPolicy.](https://docs.microsoft.com/powershell/module/skype/set-csteamsemergencycallingpolicy)</span><span class="sxs-lookup"><span data-stu-id="abd4c-140">See [Set-CsTeamsEmergencyCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsemergencycallingpolicy).</span></span>

## <a name="assign-a-custom-emergency-calling-policy-to-users"></a><span data-ttu-id="abd4c-141">Назначение пользователям настраиваемой политики экстренных вызовов</span><span class="sxs-lookup"><span data-stu-id="abd4c-141">Assign a custom emergency calling policy to users</span></span>

[!INCLUDE [assign-policy](includes/assign-policy.md)]

<span data-ttu-id="abd4c-142">См. [также Grant-CsTeamsEmergencyCallingPolicy.](https://docs.microsoft.com/powershell/module/skype/grant-csteamsemergencycallingpolicy)</span><span class="sxs-lookup"><span data-stu-id="abd4c-142">See also [Grant-CsTeamsEmergencyCallingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsemergencycallingpolicy).</span></span>

## <a name="assign-a-custom-emergency-calling-policy-to-a-network-site"></a><span data-ttu-id="abd4c-143">Назначение настраиваемой политики экстренных вызовов на сетевом сайте</span><span class="sxs-lookup"><span data-stu-id="abd4c-143">Assign a custom emergency calling policy to a network site</span></span>

<span data-ttu-id="abd4c-144">Используйте [командлет Set-CsTenantNetworkSite,](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite) чтобы назначить политику экстренных вызовов на сетевой сайт.</span><span class="sxs-lookup"><span data-stu-id="abd4c-144">Use the [Set-CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite) cmdlet to assign an emergency calling policy to a network site.</span></span>

<span data-ttu-id="abd4c-145">В следующем примере показано, как назначить политику Contoso для экстренных вызовов 1 сайту Site1.</span><span class="sxs-lookup"><span data-stu-id="abd4c-145">The following example shows how to assign a policy called Contoso Emergency Calling Policy 1 to the Site1 site.</span></span>

```powershell
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallingPolicy "Contoso Emergency Calling Policy 1"
```

## <a name="related-topics"></a><span data-ttu-id="abd4c-146">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="abd4c-146">Related topics</span></span>

[<span data-ttu-id="abd4c-147">Управление политиками маршрутизов экстренных вызовов в Teams</span><span class="sxs-lookup"><span data-stu-id="abd4c-147">Manage emergency call routing policies in Teams</span></span>](manage-emergency-call-routing-policies.md)

[<span data-ttu-id="abd4c-148">Обзор PowerShell в Teams</span><span class="sxs-lookup"><span data-stu-id="abd4c-148">Teams PowerShell overview</span></span>](teams-powershell-overview.md)

[<span data-ttu-id="abd4c-149">Назначение политик пользователям в Teams</span><span class="sxs-lookup"><span data-stu-id="abd4c-149">Assign policies to your users in Teams</span></span>](assign-policies.md)
