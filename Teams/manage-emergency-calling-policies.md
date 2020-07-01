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
ms.openlocfilehash: 12d2e114a53c47e6c938c6c2cb4bf3cb83c81180
ms.sourcegitcommit: 60b859dcb8ac727a38bf28cdb63ff762e7338af8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/30/2020
ms.locfileid: "44938438"
---
# <a name="manage-emergency-calling-policies-in-microsoft-teams"></a><span data-ttu-id="2540d-103">Управление политиками вызова экстренной помощи в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="2540d-103">Manage emergency calling policies in Microsoft Teams</span></span>

<span data-ttu-id="2540d-104">Если в вашей организации используются [планы звонков](set-up-calling-plans.md) или [Прямая маршрутизация на телефонную систему](direct-routing-landing-page.md), вы можете использовать политики вызова экстренной помощи в Microsoft Teams, чтобы определить, что происходит, когда пользователь Teams в организации осуществляет вызов экстренной помощи.</span><span class="sxs-lookup"><span data-stu-id="2540d-104">If your organization uses [Calling Plans](set-up-calling-plans.md) or deployed [Phone System Direct Routing](direct-routing-landing-page.md), you can use emergency calling policies in Microsoft Teams to define what happens when a Teams user in your organization makes an emergency call.</span></span> <span data-ttu-id="2540d-105">Вы можете настроить пользователей, которые должны уведомлять и как они уведомляются, когда пользователь, которому назначена эта политика, вызывает экстренные службы.</span><span class="sxs-lookup"><span data-stu-id="2540d-105">You can set who to notify and how they are notified when a user who is assigned the policy calls emergency services.</span></span> <span data-ttu-id="2540d-106">Например, вы можете настроить параметры политики, чтобы автоматически уведомлять службу безопасности Организации и принимать их в экстренных звонках.</span><span class="sxs-lookup"><span data-stu-id="2540d-106">For example, you can configure policy settings to automatically notify your organization's security desk and have them listen in emergency calls.</span></span>  

<span data-ttu-id="2540d-107">Управление политиками вызова экстренной помощи осуществляется путем перехода на политики **голосовой связи**  >  **Emergency policies** в центре администрирования Microsoft Teams или с помощью Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2540d-107">You manage emergency calling policies by going to **Voice** > **Emergency policies** in the Microsoft Teams admin center or by using Windows PowerShell.</span></span> <span data-ttu-id="2540d-108">Политики можно назначить для пользователей и [сайтов сети](cloud-voice-network-settings.md).</span><span class="sxs-lookup"><span data-stu-id="2540d-108">The policies can be assigned to users and [network sites](cloud-voice-network-settings.md).</span></span>

<span data-ttu-id="2540d-109">Пользователи могут использовать глобальную политику (по умолчанию на уровне Организации) или создавать и назначать пользовательские политики.</span><span class="sxs-lookup"><span data-stu-id="2540d-109">For users, you can use the global (Org-wide default) policy or create and assign custom policies.</span></span> <span data-ttu-id="2540d-110">Пользователи будут автоматически получать глобальную политику, если вы не создадите и не назначаете пользовательскую политику.</span><span class="sxs-lookup"><span data-stu-id="2540d-110">Users will automatically get the global policy unless you create and assign a custom policy.</span></span> <span data-ttu-id="2540d-111">Имейте в виду, что вы можете изменять параметры глобальной политики, но переименовывать и удалять их нельзя.</span><span class="sxs-lookup"><span data-stu-id="2540d-111">Keep in mind that you can edit the settings in the global policy but you can't rename or delete it.</span></span> <span data-ttu-id="2540d-112">Для сетевых сайтов можно создавать и назначать пользовательские политики.</span><span class="sxs-lookup"><span data-stu-id="2540d-112">For network sites, you create and assign custom policies.</span></span>

<span data-ttu-id="2540d-113">Если вы назначили для сайта сети и пользователя политику вызова экстренного реагирования, и если этот пользователь находится на сайте сети, политика, назначенная сетевому сайту, переопределяет политику, назначенную пользователю.</span><span class="sxs-lookup"><span data-stu-id="2540d-113">If you assigned an emergency calling policy to a network site and to a user and if that user is at that network site, the policy that's assigned to the network site overrides the policy that's assigned to the user.</span></span>

## <a name="create-a-custom-emergency-calling-policy"></a><span data-ttu-id="2540d-114">Создание настраиваемой политики вызова экстренной помощи</span><span class="sxs-lookup"><span data-stu-id="2540d-114">Create a custom emergency calling policy</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="2540d-115">С помощью Центра администрирования Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="2540d-115">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="2540d-116">В левой области навигации центра администрирования Microsoft Teams выберите политики **голосовой связи**  >  **Emergency policies**и перейдите на вкладку **политики звонка** .</span><span class="sxs-lookup"><span data-stu-id="2540d-116">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Emergency policies**, and then click the **Calling policies** tab.</span></span>
2. <span data-ttu-id="2540d-117">Нажмите **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="2540d-117">Click **Add**.</span></span>
3. <span data-ttu-id="2540d-118">Введите имя и описание для политики.</span><span class="sxs-lookup"><span data-stu-id="2540d-118">Enter a name and description for the policy.</span></span>
4. <span data-ttu-id="2540d-119">Укажите, как вы хотите уведомлять пользователей в вашей организации, как правило, на рабочем месте, когда производится вызов экстренной помощи.</span><span class="sxs-lookup"><span data-stu-id="2540d-119">Set how you want to notify people in your organization, typically the security desk, when an emergency call is made.</span></span> <span data-ttu-id="2540d-120">Для этого в разделе **режим уведомлений**выберите один из указанных ниже вариантов.</span><span class="sxs-lookup"><span data-stu-id="2540d-120">To do this, under **Notification mode**, select one of the following:</span></span>
    - <span data-ttu-id="2540d-121">**Только уведомление об отправке**: сообщение чата Teams отправляется указанным пользователям и группам.</span><span class="sxs-lookup"><span data-stu-id="2540d-121">**Send notification only**: A Teams chat message is sent to the users and groups that you specify.</span></span>
    - <span data-ttu-id="2540d-122">На **конференции, но отключены**: сообщение чата в Teams отправляется указанным пользователям и группам, и оно может принимать (но не принимать участие) в беседе между вызывающим абонентом и оператором PSAP.</span><span class="sxs-lookup"><span data-stu-id="2540d-122">**Conferenced in but are muted**: A Teams chat message is sent to the users and groups that you specify and they can listen (but not participate) in the conversation between the caller and the PSAP operator.</span></span>
    - <span data-ttu-id="2540d-123">Адресованные **и отключенные конференции** **(скоро)**: сообщение чата команды отправляется пользователям и указанным группам и может включать и отключать звук для прослушивания и участия в разговоре между вызывающим абонентом и оператором PSAP.</span><span class="sxs-lookup"><span data-stu-id="2540d-123">**Conferenced in and are unmuted** **(coming soon)**: A Teams chat message is sent to the users and groups that you specify and they can unmute to listen and participate in the conversation between the caller and the PSAP operator.</span></span>
5.  <span data-ttu-id="2540d-124">Если вы выбрали режим уведомлений, **но микрофон** отключен, в поле **Номера для звонков по экстренным** звонкам вы можете ввести телефонный номер КТСОП для пользователя или группы, чтобы позвонить и присоединиться к экстренному звонку.</span><span class="sxs-lookup"><span data-stu-id="2540d-124">If you selected the **Conferenced in but are muted** notification mode, in the **Numbers to dial for emergency calls notifications** box, you can enter a PSTN phone number of a user or group to call and join the emergency call.</span></span> <span data-ttu-id="2540d-125">Например, введите номер рабочего центра безопасности Организации, который получит звонок при совершении звонка, и затем может прослушать звонок.</span><span class="sxs-lookup"><span data-stu-id="2540d-125">For example, enter the number of your organization's security desk, who will receive a call when an emergency call is made and can then listen in on the call.</span></span>
6. <span data-ttu-id="2540d-126">Найдите и выберите одного или нескольких пользователей или групп, например, на рабочем столе своей организации, чтобы уведомить о совершении экстренного звонка.</span><span class="sxs-lookup"><span data-stu-id="2540d-126">Search for and select one or more users or groups, such as your organization's security desk, to notify when an emergency call is made.</span></span>  <span data-ttu-id="2540d-127">Уведомление можно отправить адресам электронной почты пользователей, группам рассылки и группам безопасности.</span><span class="sxs-lookup"><span data-stu-id="2540d-127">The notification can be sent to email addresses of users, distribution groups, and security groups.</span></span> <span data-ttu-id="2540d-128">Максимальное количество пользователей 50, которые могут быть уведомлены.</span><span class="sxs-lookup"><span data-stu-id="2540d-128">A maximum of 50 users can be notified.</span></span>
7. <span data-ttu-id="2540d-129">Нажмите кнопку **Применить**.</span><span class="sxs-lookup"><span data-stu-id="2540d-129">Click **Apply**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="2540d-130">Использование PowerShell</span><span class="sxs-lookup"><span data-stu-id="2540d-130">Using PowerShell</span></span>

<span data-ttu-id="2540d-131">Просмотреть раздел [New-CsTeamsEmergencyCallingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsemergencycallingpolicy).</span><span class="sxs-lookup"><span data-stu-id="2540d-131">See [New-CsTeamsEmergencyCallingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsemergencycallingpolicy).</span></span>

## <a name="edit-an-emergency-calling-policy"></a><span data-ttu-id="2540d-132">Изменение политики вызова экстренной помощи</span><span class="sxs-lookup"><span data-stu-id="2540d-132">Edit an emergency calling policy</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="2540d-133">С помощью Центра администрирования Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="2540d-133">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="2540d-134">Вы можете изменить глобальную политику или созданные вами пользовательские политики.</span><span class="sxs-lookup"><span data-stu-id="2540d-134">You can edit the global policy or any custom policies that you create.</span></span>

1. <span data-ttu-id="2540d-135">В левой области навигации центра администрирования Microsoft Teams выберите политики **голосовой связи**  >  **Emergency policies**и перейдите на вкладку **политики звонка** .</span><span class="sxs-lookup"><span data-stu-id="2540d-135">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Emergency policies**, and then click the **Calling policies** tab.</span></span>
2. <span data-ttu-id="2540d-136">Выберите политику, щелкнув слева от ее имени, а затем нажмите кнопку **изменить**.</span><span class="sxs-lookup"><span data-stu-id="2540d-136">Select the policy by clicking to the left of the policy name, and then click **Edit**.</span></span>
3. <span data-ttu-id="2540d-137">Внесите нужные изменения и нажмите кнопку **Применить**.</span><span class="sxs-lookup"><span data-stu-id="2540d-137">Make the changes that you want, and then click **Apply**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="2540d-138">Использование PowerShell</span><span class="sxs-lookup"><span data-stu-id="2540d-138">Using PowerShell</span></span>

<span data-ttu-id="2540d-139">Смотрите раздел [Set-CsTeamsEmergencyCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsemergencycallingpolicy).</span><span class="sxs-lookup"><span data-stu-id="2540d-139">See [Set-CsTeamsEmergencyCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsemergencycallingpolicy).</span></span>

## <a name="assign-a-custom-emergency-calling-policy-to-users"></a><span data-ttu-id="2540d-140">Назначение настраиваемой политики вызова экстренной помощи пользователям</span><span class="sxs-lookup"><span data-stu-id="2540d-140">Assign a custom emergency calling policy to users</span></span>

[!INCLUDE [assign-policy](includes/assign-policy.md)]

<span data-ttu-id="2540d-141">Дополнительные сведения можно найти в разделе [Grant-CsTeamsEmergencyCallingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsemergencycallingpolicy).</span><span class="sxs-lookup"><span data-stu-id="2540d-141">See also [Grant-CsTeamsEmergencyCallingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsemergencycallingpolicy).</span></span>

## <a name="assign-a-custom-emergency-calling-policy-to-a-network-site"></a><span data-ttu-id="2540d-142">Назначение настраиваемой политики вызова для экстренного реагирования сетевому сайту</span><span class="sxs-lookup"><span data-stu-id="2540d-142">Assign a custom emergency calling policy to a network site</span></span>

<span data-ttu-id="2540d-143">Используйте командлет [Set-CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite) , чтобы назначить политику вызова экстренной помощи на сайте сети.</span><span class="sxs-lookup"><span data-stu-id="2540d-143">Use the [Set-CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite) cmdlet to assign an emergency calling policy to a network site.</span></span>

<span data-ttu-id="2540d-144">В следующем примере показано, как назначить политику, которая называется политикой вызова экстренной помощи Contoso 1, на сайт site1.</span><span class="sxs-lookup"><span data-stu-id="2540d-144">The following example shows how to assign a policy called Contoso Emergency Calling Policy 1 to the Site1 site.</span></span>

```powershell
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallingPolicy "Contoso Emergency Calling Policy 1"
```

## <a name="related-topics"></a><span data-ttu-id="2540d-145">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="2540d-145">Related topics</span></span>

[<span data-ttu-id="2540d-146">Управление политиками маршрутизации вызова экстренной помощи в Teams</span><span class="sxs-lookup"><span data-stu-id="2540d-146">Manage emergency call routing policies in Teams</span></span>](manage-emergency-call-routing-policies.md)

[<span data-ttu-id="2540d-147">Обзор PowerShell в Teams</span><span class="sxs-lookup"><span data-stu-id="2540d-147">Teams PowerShell overview</span></span>](teams-powershell-overview.md)

[<span data-ttu-id="2540d-148">Назначение политик пользователям в Teams</span><span class="sxs-lookup"><span data-stu-id="2540d-148">Assign policies to your users in Teams</span></span>](assign-policies.md)
