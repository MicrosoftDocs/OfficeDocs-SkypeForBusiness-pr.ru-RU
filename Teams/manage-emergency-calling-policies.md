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
ms.openlocfilehash: 1e516252317a0e5f14e705b674255048fb3defb5
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49804689"
---
# <a name="manage-emergency-calling-policies-in-microsoft-teams"></a><span data-ttu-id="6db61-103">Управление политиками экстренных вызовов в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="6db61-103">Manage emergency calling policies in Microsoft Teams</span></span>

<span data-ttu-id="6db61-104">Если в [](set-up-calling-plans.md) вашей организации используются планы звонков или развернута прямая маршрутия телефонной [системы,](direct-routing-landing-page.md)вы можете использовать политики экстренных вызовов в Microsoft Teams, чтобы определить, что происходит, когда пользователь Teams в вашей организации звонит в экстренные службы.</span><span class="sxs-lookup"><span data-stu-id="6db61-104">If your organization uses [Calling Plans](set-up-calling-plans.md) or deployed [Phone System Direct Routing](direct-routing-landing-page.md), you can use emergency calling policies in Microsoft Teams to define what happens when a Teams user in your organization makes an emergency call.</span></span> <span data-ttu-id="6db61-105">Вы можете настроить, кому и каким образом уведомлять пользователя, которому назначена политика, в экстренные службы.</span><span class="sxs-lookup"><span data-stu-id="6db61-105">You can set who to notify and how they are notified when a user who is assigned the policy calls emergency services.</span></span> <span data-ttu-id="6db61-106">Например, вы можете настроить параметры политики для автоматического уведомления службы безопасности организации и для того, чтобы они могли прослушивать звонки в экстренные службы.</span><span class="sxs-lookup"><span data-stu-id="6db61-106">For example, you can configure policy settings to automatically notify your organization's security desk and have them listen in emergency calls.</span></span>  

<span data-ttu-id="6db61-107">Вы управляете политиками экстренных вызовов, переходить к политикам голосового экстренного вызова в Центре администрирования Microsoft Teams или с помощью   >   Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6db61-107">You manage emergency calling policies by going to **Voice** > **Emergency policies** in the Microsoft Teams admin center or by using Windows PowerShell.</span></span> <span data-ttu-id="6db61-108">Политики могут быть назначены пользователям и [сетевым сайтам.](cloud-voice-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="6db61-108">The policies can be assigned to users and [network sites](cloud-voice-network-settings.md).</span></span>

<span data-ttu-id="6db61-109">Для пользователей можно использовать глобальную (по умолчанию в организации) политику или создавать и назначать настраиваемые политики.</span><span class="sxs-lookup"><span data-stu-id="6db61-109">For users, you can use the global (Org-wide default) policy or create and assign custom policies.</span></span> <span data-ttu-id="6db61-110">Пользователи будут автоматически получать глобальную политику, если вы не создайте и не назначите ее.</span><span class="sxs-lookup"><span data-stu-id="6db61-110">Users will automatically get the global policy unless you create and assign a custom policy.</span></span> <span data-ttu-id="6db61-111">Помните, что вы можете изменить параметры глобальной политики, но не можете переименовать или удалить ее.</span><span class="sxs-lookup"><span data-stu-id="6db61-111">Keep in mind that you can edit the settings in the global policy but you can't rename or delete it.</span></span> <span data-ttu-id="6db61-112">Для сетевых сайтов создаются и назначаются настраиваемые политики.</span><span class="sxs-lookup"><span data-stu-id="6db61-112">For network sites, you create and assign custom policies.</span></span>

<span data-ttu-id="6db61-113">Если политика экстренных вызовов назначена сетевому сайту и пользователю, а этот пользователь находится на этом сетевом сайте, политика, назначенная сетевому сайту, переопределит политику, назначенную пользователю.</span><span class="sxs-lookup"><span data-stu-id="6db61-113">If you assigned an emergency calling policy to a network site and to a user and if that user is at that network site, the policy that's assigned to the network site overrides the policy that's assigned to the user.</span></span>

## <a name="create-a-custom-emergency-calling-policy"></a><span data-ttu-id="6db61-114">Создание настраиваемой политики экстренных вызовов</span><span class="sxs-lookup"><span data-stu-id="6db61-114">Create a custom emergency calling policy</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="6db61-115">С помощью Центра администрирования Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="6db61-115">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="6db61-116">В левой области навигации Центра администрирования Microsoft Teams перейдите к политикам голосового экстренного вызова и перейдите на вкладку  >   **"Политики звонков".**</span><span class="sxs-lookup"><span data-stu-id="6db61-116">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Emergency policies**, and then click the **Calling policies** tab.</span></span>
2. <span data-ttu-id="6db61-117">Нажмите **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="6db61-117">Click **Add**.</span></span>
3. <span data-ttu-id="6db61-118">Введите имя и описание для политики.</span><span class="sxs-lookup"><span data-stu-id="6db61-118">Enter a name and description for the policy.</span></span>
4. <span data-ttu-id="6db61-119">Настройка оповещать сотрудников организации (обычно это служба безопасности) о звонках в экстренные службы.</span><span class="sxs-lookup"><span data-stu-id="6db61-119">Set how you want to notify people in your organization, typically the security desk, when an emergency call is made.</span></span> <span data-ttu-id="6db61-120">Для этого в режиме **уведомлений** выберите одно из следующих:</span><span class="sxs-lookup"><span data-stu-id="6db61-120">To do this, under **Notification mode**, select one of the following:</span></span>
    - <span data-ttu-id="6db61-121">**Только отправка уведомления.** Пользователям и группам, которые вы указываете, отправляется сообщение чата Teams.</span><span class="sxs-lookup"><span data-stu-id="6db61-121">**Send notification only**: A Teams chat message is sent to the users and groups that you specify.</span></span>
    - <span data-ttu-id="6db61-122">**Конференц-связь,** но отключен: сообщение чата Teams отправляется пользователям и группам, которые вы указываете, и они могут прослушивать (но не принимать участие) в беседе между звонив и оператором PSAP.</span><span class="sxs-lookup"><span data-stu-id="6db61-122">**Conferenced in but are muted**: A Teams chat message is sent to the users and groups that you specify and they can listen (but not participate) in the conversation between the caller and the PSAP operator.</span></span>
    - <span data-ttu-id="6db61-123">**Конференции** и звук будет в сети **(скоро появится):** сообщение чата Teams будет отправлено пользователям и группам, которые вы указали, и они могут в сети, чтобы слушать беседу между вызываемой и оператором PSAP и участвовать в ней.</span><span class="sxs-lookup"><span data-stu-id="6db61-123">**Conferenced in and are unmuted** **(coming soon)**: A Teams chat message is sent to the users and groups that you specify and they can unmute to listen and participate in the conversation between the caller and the PSAP operator.</span></span>
5.  <span data-ttu-id="6db61-124">Если вы выбрали  конференц-зал в режиме отключенных  уведомлений, в поле "Номера для звонка в экстренные вызовы" можно ввести номер телефона пользователя или группы, чтобы позвонить пользователю или группе и присоединиться к нему.</span><span class="sxs-lookup"><span data-stu-id="6db61-124">If you selected the **Conferenced in but are muted** notification mode, in the **Numbers to dial for emergency calls notifications** box, you can enter a PSTN phone number of a user or group to call and join the emergency call.</span></span> <span data-ttu-id="6db61-125">Например, введите номер службы безопасности вашей организации, который будет получать звонок при звонок в экстренные службы и сможет прослушивать звонок.</span><span class="sxs-lookup"><span data-stu-id="6db61-125">For example, enter the number of your organization's security desk, who will receive a call when an emergency call is made and can then listen in on the call.</span></span>
6. <span data-ttu-id="6db61-126">Вы можете найти одного или несколько пользователей или групп, например службу безопасности вашей организации, и выбрать их, чтобы уведомить об этом экстренные вызовы.</span><span class="sxs-lookup"><span data-stu-id="6db61-126">Search for and select one or more users or groups, such as your organization's security desk, to notify when an emergency call is made.</span></span>  <span data-ttu-id="6db61-127">Уведомление может отправляться на адреса электронной почты пользователей, групп рассылки и групп безопасности.</span><span class="sxs-lookup"><span data-stu-id="6db61-127">The notification can be sent to email addresses of users, distribution groups, and security groups.</span></span> <span data-ttu-id="6db61-128">Можно уведомить не более 50 пользователей.</span><span class="sxs-lookup"><span data-stu-id="6db61-128">A maximum of 50 users can be notified.</span></span>
7. <span data-ttu-id="6db61-129">Нажмите кнопку **Применить**.</span><span class="sxs-lookup"><span data-stu-id="6db61-129">Click **Apply**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="6db61-130">С помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="6db61-130">Using PowerShell</span></span>

<span data-ttu-id="6db61-131">См. [new-CsTeamsEmergencyCallingPolicy.](https://docs.microsoft.com/powershell/module/skype/new-csteamsemergencycallingpolicy)</span><span class="sxs-lookup"><span data-stu-id="6db61-131">See [New-CsTeamsEmergencyCallingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsemergencycallingpolicy).</span></span>

## <a name="edit-an-emergency-calling-policy"></a><span data-ttu-id="6db61-132">Изменение политики экстренных вызовов</span><span class="sxs-lookup"><span data-stu-id="6db61-132">Edit an emergency calling policy</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="6db61-133">С помощью Центра администрирования Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="6db61-133">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="6db61-134">Вы можете изменить глобальную политику или любые настраиваемые политики, которые вы создаете.</span><span class="sxs-lookup"><span data-stu-id="6db61-134">You can edit the global policy or any custom policies that you create.</span></span>

1. <span data-ttu-id="6db61-135">В левой области навигации Центра администрирования Microsoft Teams перейдите к политикам голосового экстренного вызова и перейдите на вкладку  >   **"Политики звонков".**</span><span class="sxs-lookup"><span data-stu-id="6db61-135">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Emergency policies**, and then click the **Calling policies** tab.</span></span>
2. <span data-ttu-id="6db61-136">Выберите политику, щелкнув слева от ее имени и нажав кнопку **"Изменить".**</span><span class="sxs-lookup"><span data-stu-id="6db61-136">Select the policy by clicking to the left of the policy name, and then click **Edit**.</span></span>
3. <span data-ttu-id="6db61-137">Внесите нужные изменения и нажмите кнопку **"Применить".**</span><span class="sxs-lookup"><span data-stu-id="6db61-137">Make the changes that you want, and then click **Apply**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="6db61-138">С помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="6db61-138">Using PowerShell</span></span>

<span data-ttu-id="6db61-139">См. [set-CsTeamsEmergencyCallingPolicy.](https://docs.microsoft.com/powershell/module/skype/set-csteamsemergencycallingpolicy)</span><span class="sxs-lookup"><span data-stu-id="6db61-139">See [Set-CsTeamsEmergencyCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsemergencycallingpolicy).</span></span>

## <a name="assign-a-custom-emergency-calling-policy-to-users"></a><span data-ttu-id="6db61-140">Назначение пользователям настраиваемой политики экстренных вызовов</span><span class="sxs-lookup"><span data-stu-id="6db61-140">Assign a custom emergency calling policy to users</span></span>

[!INCLUDE [assign-policy](includes/assign-policy.md)]

<span data-ttu-id="6db61-141">См. [также Grant-CsTeamsEmergencyCallingPolicy.](https://docs.microsoft.com/powershell/module/skype/grant-csteamsemergencycallingpolicy)</span><span class="sxs-lookup"><span data-stu-id="6db61-141">See also [Grant-CsTeamsEmergencyCallingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsemergencycallingpolicy).</span></span>

## <a name="assign-a-custom-emergency-calling-policy-to-a-network-site"></a><span data-ttu-id="6db61-142">Назначение настраиваемой политики экстренных вызовов на сетевом сайте</span><span class="sxs-lookup"><span data-stu-id="6db61-142">Assign a custom emergency calling policy to a network site</span></span>

<span data-ttu-id="6db61-143">Используйте [командлет Set-CsTenantNetworkSite,](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite) чтобы назначить политику экстренных вызовов на сетевой сайт.</span><span class="sxs-lookup"><span data-stu-id="6db61-143">Use the [Set-CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite) cmdlet to assign an emergency calling policy to a network site.</span></span>

<span data-ttu-id="6db61-144">В следующем примере показано, как назначить политику Contoso для экстренных вызовов 1 сайту Site1.</span><span class="sxs-lookup"><span data-stu-id="6db61-144">The following example shows how to assign a policy called Contoso Emergency Calling Policy 1 to the Site1 site.</span></span>

```powershell
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallingPolicy "Contoso Emergency Calling Policy 1"
```

## <a name="related-topics"></a><span data-ttu-id="6db61-145">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="6db61-145">Related topics</span></span>

[<span data-ttu-id="6db61-146">Управление политиками маршрутизов экстренных вызовов в Teams</span><span class="sxs-lookup"><span data-stu-id="6db61-146">Manage emergency call routing policies in Teams</span></span>](manage-emergency-call-routing-policies.md)

[<span data-ttu-id="6db61-147">Обзор PowerShell в Teams</span><span class="sxs-lookup"><span data-stu-id="6db61-147">Teams PowerShell overview</span></span>](teams-powershell-overview.md)

[<span data-ttu-id="6db61-148">Назначение политик пользователям в Teams</span><span class="sxs-lookup"><span data-stu-id="6db61-148">Assign policies to your users in Teams</span></span>](assign-policies.md)
