---
title: Управление политиками маршрутинга экстренных вызовов для прямой маршрутизы
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: jastark, roykuntz
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
f1.keywords:
- NOCSH
- ms.teamsadmincenter.voice.emergencycallroutingpolicies.overview
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Узнайте, как использовать политики маршрутизировать экстренные вызовы и управлять ими в Microsoft Teams настроить номера экстренных служб и настроить маршруты экстренных вызовов.
ms.custom:
- seo-marvel-apr2020
- ms.teamsadmincenter.voice.emergencycallroutingpolicies.overview
ms.openlocfilehash: 86f73bed2e086efee666e5592ca3f42e9756096c
ms.sourcegitcommit: 5720fa12bdabdfc2988bf835c8cf95e4d64fa54e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/09/2021
ms.locfileid: "53354309"
---
# <a name="manage-emergency-call-routing-policies-for-direct-routing"></a><span data-ttu-id="cdb90-103">Управление политиками маршрутинга экстренных вызовов для прямой маршрутизы</span><span class="sxs-lookup"><span data-stu-id="cdb90-103">Manage emergency call routing policies for Direct Routing</span></span>

<span data-ttu-id="cdb90-104">Если вы развернули прямую [маршрутику телефонная система](direct-routing-landing-page.md) в организации, вы можете использовать политики маршрутизации экстренных вызовов в Microsoft Teams, чтобы настроить номера экстренных служб и настроить маршруты экстренных вызовов.</span><span class="sxs-lookup"><span data-stu-id="cdb90-104">If you've deployed [Phone System Direct Routing](direct-routing-landing-page.md) in your organization, you can use emergency call routing policies in Microsoft Teams to set up emergency numbers and specify how emergency calls are routed.</span></span> <span data-ttu-id="cdb90-105">Политика маршрутинга экстренных вызовов определяет, включены ли расширенные экстренные службы для пользователей, которым назначена политика, какие номера используются для звонков в экстренные службы (например, 911 в США) и как перена могут перенапределяться звонки в экстренные службы.</span><span class="sxs-lookup"><span data-stu-id="cdb90-105">An emergency call routing policy determines whether enhanced emergency services are enabled for users who are assigned the policy, the numbers used to call emergency services (for example, 911 in the United States), and how calls to emergency services are routed.</span></span>

<span data-ttu-id="cdb90-106">Вы управляете политиками маршрутизов экстренных вызовов, используя политики голосового экстренного вызова Microsoft Teams центре администрирования или с помощью   >   Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="cdb90-106">You manage emergency call routing policies by going to **Voice** > **Emergency policies** in the Microsoft Teams admin center or by using Windows PowerShell.</span></span> <span data-ttu-id="cdb90-107">Политики могут быть назначены пользователям и [сетевым сайтам.](cloud-voice-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="cdb90-107">The policies can be assigned to users and [network sites](cloud-voice-network-settings.md).</span></span>

<span data-ttu-id="cdb90-108">Для пользователей можно использовать глобальную политику (по умолчанию в организации) или создавать и назначать настраиваемые политики.</span><span class="sxs-lookup"><span data-stu-id="cdb90-108">For users, you can use the global (Org-wide default) policy or create and assign custom policies.</span></span> <span data-ttu-id="cdb90-109">Пользователи будут автоматически получать глобальную политику, если только вы не создайте и не назначите настраиваемую политику.</span><span class="sxs-lookup"><span data-stu-id="cdb90-109">Users will automatically get the global policy unless you create and assign a custom policy.</span></span> <span data-ttu-id="cdb90-110">Имейте в виду, что вы можете изменить параметры глобальной политики, но не можете переименовать или удалить ее.</span><span class="sxs-lookup"><span data-stu-id="cdb90-110">Keep in mind that you can edit the settings in the global policy but you can't rename or delete it.</span></span> <span data-ttu-id="cdb90-111">Для сетевых сайтов создаются и назначаются настраиваемые политики.</span><span class="sxs-lookup"><span data-stu-id="cdb90-111">For network sites, you create and assign custom policies.</span></span>

<span data-ttu-id="cdb90-112">Если политика маршрутинга экстренных вызовов назначена сетевому сайту и пользователю, а пользователь находится на этом сайте, политика, назначенная сетевому сайту, переопределит политику, назначенную пользователю.</span><span class="sxs-lookup"><span data-stu-id="cdb90-112">If you assigned an emergency call routing policy to a network site and to a user and if that user is at that network site, the policy that's assigned to the network site overrides the policy that's assigned to the user.</span></span>

## <a name="create-a-custom-emergency-call-routing-policy"></a><span data-ttu-id="cdb90-113">Создание настраиваемой политики маршрутизов экстренных вызовов</span><span class="sxs-lookup"><span data-stu-id="cdb90-113">Create a custom emergency call routing policy</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="cdb90-114">С помощью Центра администрирования Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="cdb90-114">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="cdb90-115">В левой области навигации Центра администрирования Microsoft Teams перейдите к центру Политики для экстренного вызова голосовой почты и перейдите на вкладку Политики  >   **маршрутации** вызовов.</span><span class="sxs-lookup"><span data-stu-id="cdb90-115">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Emergency policies**, and then click the **Call routing policies** tab.</span></span>
2. <span data-ttu-id="cdb90-116">Нажмите **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="cdb90-116">Click **Add**.</span></span>
3. <span data-ttu-id="cdb90-117">Введите имя и описание для политики.</span><span class="sxs-lookup"><span data-stu-id="cdb90-117">Enter a name and description for the policy.</span></span>
4. <span data-ttu-id="cdb90-118">Чтобы включить динамические экстренные вызовы, включите **динамические экстренные вызовы.**</span><span class="sxs-lookup"><span data-stu-id="cdb90-118">To enable dynamic emergency calling, turn on **Dynamic emergency calling**.</span></span> <span data-ttu-id="cdb90-119">Если динамические экстренные вызовы включены, Teams извлекает сведения о политике и расположении из службы и включает их в экстренные вызовы.</span><span class="sxs-lookup"><span data-stu-id="cdb90-119">When dynamic emergency calling is enabled, Teams retrieves policy and location information from the service and includes that information as part of the emergency call.</span></span>
5. <span data-ttu-id="cdb90-120">Определите один или несколько номеров для экстренного ситуация.</span><span class="sxs-lookup"><span data-stu-id="cdb90-120">Define one or more emergency numbers.</span></span> <span data-ttu-id="cdb90-121">Для этого в области **Номера экстренных служб** нажмите **кнопку Добавить** и сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="cdb90-121">To do this, under **Emergency numbers**, click **Add**, and then do the following:</span></span>
    1. <span data-ttu-id="cdb90-122">**Строка набора номера для экстренного помощи:** введите строку экстренного набора.</span><span class="sxs-lookup"><span data-stu-id="cdb90-122">**Emergency dial string**: Enter the emergency dial string.</span></span> <span data-ttu-id="cdb90-123">Эта строка набора указывает на то, что звонок является экстренным.</span><span class="sxs-lookup"><span data-stu-id="cdb90-123">This dial string indicates that a call is an emergency call.</span></span>
        > [!NOTE]
        > <span data-ttu-id="cdb90-124">При прямой маршрутике мы отправляем не Teams, которые отправляют экстренные вызовы со строкой "+" перед строкой набора экстренных служб.</span><span class="sxs-lookup"><span data-stu-id="cdb90-124">For Direct Routing, we're transitioning away from Teams clients sending emergency calls with a "+" in front of the emergency dial string.</span></span> <span data-ttu-id="cdb90-125">До завершения перехода шаблон голосового маршрута, который соответствует строке набора экстренных служб, должен обеспечить соответствие строкам, которые имеют и не имеют предыдущего "+", например 911 и +911.</span><span class="sxs-lookup"><span data-stu-id="cdb90-125">Until the transition is completed, the voice route pattern to match an emergency dial string should ensure a match is made for strings that have and don't have a preceding "+", such as 911 and +911.</span></span> <span data-ttu-id="cdb90-126">Например, ^ \\ +?911 или .\*.</span><span class="sxs-lookup"><span data-stu-id="cdb90-126">For example, ^\\+?911 or .\*.</span></span>
    2. <span data-ttu-id="cdb90-127">**Маска для экстренного набора** номера: для каждого номера можно указать ноль или больше маски для экстренного набора номера.</span><span class="sxs-lookup"><span data-stu-id="cdb90-127">**Emergency dial mask**: For each emergency number, you can specify zero or more emergency dial masks.</span></span> <span data-ttu-id="cdb90-128">Маска набора номера — это номер, который вы хотите перевести в значение строки набора для экстренного срочная помощь.</span><span class="sxs-lookup"><span data-stu-id="cdb90-128">A dial mask is the number that you want to translate into the value of the emergency dial string.</span></span> <span data-ttu-id="cdb90-129">Это позволяет набирать альтернативные номера экстренных служб и по-прежнему звонить в экстренные службы.</span><span class="sxs-lookup"><span data-stu-id="cdb90-129">This allows for alternate emergency numbers to be dialed and still have the call reach emergency services.</span></span> <br><span data-ttu-id="cdb90-130">Например, вы добавляете 112 в качестве маски набора номера для экстренного обслуживания, которая является номером экстренных служб для большинства стран Европы, а 911 — в качестве строки набора экстренных служб.</span><span class="sxs-lookup"><span data-stu-id="cdb90-130">For example, you add 112 as the emergency dial mask, which is the emergency service number for most of Europe, and 911 as the emergency dial string.</span></span> <span data-ttu-id="cdb90-131">Пользователь Teams из Европы может не знать, что 911 — это номер для экстренного вызова в США, а при наборе номера 112 звонят на номер 911.</span><span class="sxs-lookup"><span data-stu-id="cdb90-131">A Teams user from Europe who is visiting may not know that 911 is the emergency number in the United States, and when they dial 112, the call is made to 911.</span></span> <span data-ttu-id="cdb90-132">Чтобы определить несколько масок набора номера, разделите каждое значение за за semicolon.</span><span class="sxs-lookup"><span data-stu-id="cdb90-132">To define multiple dial masks, separate each value by a semicolon.</span></span> <span data-ttu-id="cdb90-133">Например, 112;212.</span><span class="sxs-lookup"><span data-stu-id="cdb90-133">For example, 112;212.</span></span>
    3. <span data-ttu-id="cdb90-134">**Запись использования STN:** выберите запись использования телефонной сети общего пользования (STN).</span><span class="sxs-lookup"><span data-stu-id="cdb90-134">**PSTN usage record**: Select the Public Switched Telephone Network (PSTN) usage record.</span></span> <span data-ttu-id="cdb90-135">Запись использования ОКП используется для определения маршрута, используемого для маршрутизации экстренных вызовов от пользователей, которым разрешено их использовать.</span><span class="sxs-lookup"><span data-stu-id="cdb90-135">The PSTN usage record is used to determine which route is used to route emergency calls from users who are authorized to use them.</span></span> <span data-ttu-id="cdb90-136">Маршрут, связанный с этим использованием, должен указать на магистраль SIP, выделенную для экстренных вызовов, или на шлюз ELIN, который перенаправляет экстренные вызовы в ближайший общедоступный пункт ответа (PSAP).</span><span class="sxs-lookup"><span data-stu-id="cdb90-136">The route associated with this usage should point to a Session Initiation Protocol (SIP) trunk dedicated to emergency calls or to an Emergency Location Identification Number (ELIN) gateway that routes emergency calls to the nearest Public Safety Answering Point (PSAP).</span></span>

    > [!NOTE]
    > <span data-ttu-id="cdb90-137">Строки набора и маски набора должны быть уникальными в политике.</span><span class="sxs-lookup"><span data-stu-id="cdb90-137">Dial strings and dial masks must be unique within a policy.</span></span> <span data-ttu-id="cdb90-138">Это означает, что для политики можно определить несколько номеров экстренных служб и настроить несколько масок набора для строки набора, но каждую из них необходимо использовать только один раз.</span><span class="sxs-lookup"><span data-stu-id="cdb90-138">This means that for a policy, you can define multiple emergency numbers and you can set multiple dial masks for a dial string, but each dial string and dial mask must only be used one time.</span></span>

6. <span data-ttu-id="cdb90-139">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="cdb90-139">Click **Save**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="cdb90-140">С помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="cdb90-140">Using PowerShell</span></span>

<span data-ttu-id="cdb90-141">См. [new-CsTeamsEmergencyCallRoutingPolicy.](/powershell/module/skype/new-csteamsemergencycallroutingpolicy)</span><span class="sxs-lookup"><span data-stu-id="cdb90-141">See [New-CsTeamsEmergencyCallRoutingPolicy](/powershell/module/skype/new-csteamsemergencycallroutingpolicy).</span></span>

## <a name="edit-an-emergency-call-routing-policy"></a><span data-ttu-id="cdb90-142">Изменение политики маршрутики экстренных вызовов</span><span class="sxs-lookup"><span data-stu-id="cdb90-142">Edit an emergency call routing policy</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="cdb90-143">С помощью Центра администрирования Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="cdb90-143">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="cdb90-144">Вы можете изменить глобальную политику или любые настраиваемые политики, которые вы создаете.</span><span class="sxs-lookup"><span data-stu-id="cdb90-144">You can edit the global policy or any custom policies that you create.</span></span>

1. <span data-ttu-id="cdb90-145">В левой области навигации Центра администрирования Microsoft Teams перейдите к центру Политики для экстренного вызова голосовой почты и перейдите на вкладку Политики  >   **маршрутации** вызовов.</span><span class="sxs-lookup"><span data-stu-id="cdb90-145">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Emergency policies**, and then click the **Call routing policies** tab.</span></span>
2. <span data-ttu-id="cdb90-146">Выберите политику, щелкнув слева от ее имени, а затем нажмите **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="cdb90-146">Select the policy by clicking to the left of the policy name, and then click **Edit**.</span></span>
3. <span data-ttu-id="cdb90-147">Внести нужные изменения и нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="cdb90-147">Make the changes that you want, and then click **Save**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="cdb90-148">С помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="cdb90-148">Using PowerShell</span></span>

<span data-ttu-id="cdb90-149">См. [set-CsTeamsEmergencyCallRoutingPolicy.](/powershell/module/skype/set-csteamsemergencycallroutingpolicy)</span><span class="sxs-lookup"><span data-stu-id="cdb90-149">See [Set-CsTeamsEmergencyCallRoutingPolicy](/powershell/module/skype/set-csteamsemergencycallroutingpolicy).</span></span>

## <a name="assign-a-custom-emergency-call-routing-policy-to-users"></a><span data-ttu-id="cdb90-150">Назначение пользовательской политики маршрутизов экстренных вызовов пользователям</span><span class="sxs-lookup"><span data-stu-id="cdb90-150">Assign a custom emergency call routing policy to users</span></span>

[!INCLUDE [assign-policy](includes/assign-policy.md)]

<span data-ttu-id="cdb90-151">См. [также Grant-CsTeamsEmergencyCallRoutingPolicy.](/powershell/module/skype/grant-csteamsemergencycallroutingpolicy)</span><span class="sxs-lookup"><span data-stu-id="cdb90-151">See also [Grant-CsTeamsEmergencyCallRoutingPolicy](/powershell/module/skype/grant-csteamsemergencycallroutingpolicy).</span></span>

## <a name="assign-a-custom-emergency-call-routing-policy-to-a-network-site"></a><span data-ttu-id="cdb90-152">Назначение настраиваемой политики маршрутизов экстренных вызовов на сетевой сайт</span><span class="sxs-lookup"><span data-stu-id="cdb90-152">Assign a custom emergency call routing policy to a network site</span></span>

<span data-ttu-id="cdb90-153">Используйте [командлет Set-CsTenantNetworkSite,](/powershell/module/skype/set-cstenantnetworksite) чтобы назначить политику маршрутизации экстренных вызовов на сетевой сайт.</span><span class="sxs-lookup"><span data-stu-id="cdb90-153">Use the [Set-CsTenantNetworkSite](/powershell/module/skype/set-cstenantnetworksite) cmdlet to assign an emergency calling routing policy to a network site.</span></span>

<span data-ttu-id="cdb90-154">В этом примере показано, как назначить политику маршрутизов экстренных вызовов 1 сайту Site1.</span><span class="sxs-lookup"><span data-stu-id="cdb90-154">This example shows how to assign a policy called Emergency Call Routing Policy 1 to the Site1 site.</span></span>

```PowerShell
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallRoutingPolicy "Emergency Call Routing Policy 1"
```

## <a name="related-topics"></a><span data-ttu-id="cdb90-155">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="cdb90-155">Related topics</span></span>

[<span data-ttu-id="cdb90-156">Управление политиками экстренных вызовов в Teams</span><span class="sxs-lookup"><span data-stu-id="cdb90-156">Manage emergency calling policies in Teams</span></span>](manage-emergency-calling-policies.md)

[<span data-ttu-id="cdb90-157">Обзор PowerShell в Teams</span><span class="sxs-lookup"><span data-stu-id="cdb90-157">Teams PowerShell overview</span></span>](teams-powershell-overview.md)

[<span data-ttu-id="cdb90-158">Назначение политик пользователям в Teams</span><span class="sxs-lookup"><span data-stu-id="cdb90-158">Assign policies to your users in Teams</span></span>](assign-policies.md)