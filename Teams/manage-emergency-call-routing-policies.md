---
title: Управление политиками маршрутизации экстренных вызовов
author: cichur
ms.author: v-cichur
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
description: Узнайте, как использовать политики маршрутизировать экстренные вызовы и управлять ими в Microsoft Teams, чтобы настроить номера для экстренного вызова и настроить маршруты экстренных вызовов.
ms.custom:
- seo-marvel-apr2020
- ms.teamsadmincenter.voice.emergencycallroutingpolicies.overview
ms.openlocfilehash: f2e7ce7ee2557745f3819efc84dada77b4a70635
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49804679"
---
# <a name="manage-emergency-call-routing-policies-in-microsoft-teams"></a><span data-ttu-id="e1bc5-103">Управление политиками маршрутизов экстренных вызовов в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="e1bc5-103">Manage emergency call routing policies in Microsoft Teams</span></span>

<span data-ttu-id="e1bc5-104">Если в вашей [](direct-routing-landing-page.md) организации развернута прямая маршрутия телефонной системы, вы можете использовать политики маршрутизации экстренных вызовов в Microsoft Teams, чтобы настроить номера для экстренного вызова и настроить маршруты экстренных вызовов.</span><span class="sxs-lookup"><span data-stu-id="e1bc5-104">If you've deployed [Phone System Direct Routing](direct-routing-landing-page.md) in your organization, you can use emergency call routing policies in Microsoft Teams to set up emergency numbers and specify how emergency calls are routed.</span></span> <span data-ttu-id="e1bc5-105">Политика маршрутинга экстренных вызовов определяет, включены ли улучшенные экстренные службы для пользователей, которым назначена политика, номера, используемые для звонков в экстренные службы (например, 911 в США), и как перена маршруты звонков в экстренные службы.</span><span class="sxs-lookup"><span data-stu-id="e1bc5-105">An emergency call routing policy determines whether enhanced emergency services is enabled for users who are assigned the policy, the numbers used to call emergency services (for example, 911 in the United States), and how calls to emergency services are routed.</span></span>

<span data-ttu-id="e1bc5-106">Вы управляете политиками маршрутизов экстренных вызовов, переходить к политикам голосового экстренного вызова в Центре администрирования Microsoft Teams или с помощью   >   Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e1bc5-106">You manage emergency call routing policies by going to **Voice** > **Emergency policies** in the Microsoft Teams admin center or by using Windows PowerShell.</span></span> <span data-ttu-id="e1bc5-107">Политики могут быть назначены пользователям и [сетевым сайтам.](cloud-voice-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="e1bc5-107">The policies can be assigned to users and [network sites](cloud-voice-network-settings.md).</span></span>

<span data-ttu-id="e1bc5-108">Для пользователей можно использовать глобальную (по умолчанию в организации) политику или создавать и назначать настраиваемые политики.</span><span class="sxs-lookup"><span data-stu-id="e1bc5-108">For users, you can use the global (Org-wide default) policy or create and assign custom policies.</span></span> <span data-ttu-id="e1bc5-109">Пользователи будут автоматически получать глобальную политику, если вы не создайте и не назначите ее.</span><span class="sxs-lookup"><span data-stu-id="e1bc5-109">Users will automatically get the global policy unless you create and assign a custom policy.</span></span> <span data-ttu-id="e1bc5-110">Помните, что вы можете изменить параметры глобальной политики, но не можете переименовать или удалить ее.</span><span class="sxs-lookup"><span data-stu-id="e1bc5-110">Keep in mind that you can edit the settings in the global policy but you can't rename or delete it.</span></span> <span data-ttu-id="e1bc5-111">Для сетевых сайтов создаются и назначаются настраиваемые политики.</span><span class="sxs-lookup"><span data-stu-id="e1bc5-111">For network sites, you create and assign custom policies.</span></span>

<span data-ttu-id="e1bc5-112">Если политика маршрутинга экстренных вызовов назначена сетевому сайту и пользователю, а этот пользователь находится на этом сайте сети, политика, назначенная сетевому сайту, переопределит политику, назначенную пользователю.</span><span class="sxs-lookup"><span data-stu-id="e1bc5-112">If you assigned an emergency call routing policy to a network site and to a user and if that user is at that network site, the policy that's assigned to the network site overrides the policy that's assigned to the user.</span></span>

## <a name="create-a-custom-emergency-call-routing-policy"></a><span data-ttu-id="e1bc5-113">Создание настраиваемой политики маршрутизов экстренных вызовов</span><span class="sxs-lookup"><span data-stu-id="e1bc5-113">Create a custom emergency call routing policy</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="e1bc5-114">С помощью Центра администрирования Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="e1bc5-114">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="e1bc5-115">В левой области навигации Центра администрирования Microsoft Teams перейдите к политикам голосового экстренного вызова, а затем щелкните вкладку "Политики  >   **маршрутинга экстренных вызовов".**</span><span class="sxs-lookup"><span data-stu-id="e1bc5-115">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Emergency policies**, and then click the **Call routing policies** tab.</span></span>
2. <span data-ttu-id="e1bc5-116">Нажмите **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="e1bc5-116">Click **Add**.</span></span>
3. <span data-ttu-id="e1bc5-117">Введите имя и описание для политики.</span><span class="sxs-lookup"><span data-stu-id="e1bc5-117">Enter a name and description for the policy.</span></span>
4. <span data-ttu-id="e1bc5-118">Чтобы включить динамические экстренные вызовы, включив **динамические экстренные вызовы.**</span><span class="sxs-lookup"><span data-stu-id="e1bc5-118">To enable dynamic emergency calling, turn on **Dynamic emergency calling**.</span></span> <span data-ttu-id="e1bc5-119">Если динамические экстренные вызовы включены, Teams извлекает сведения о политике и расположении из службы и включает эти сведения в экстренные вызовы.</span><span class="sxs-lookup"><span data-stu-id="e1bc5-119">When dynamic emergency calling is enabled, Teams retrieves policy and location information from the service and includes that information as part of the emergency call.</span></span>
5. <span data-ttu-id="e1bc5-120">Определить один или несколько номеров для экстренного срочная ситуация.</span><span class="sxs-lookup"><span data-stu-id="e1bc5-120">Define one or more emergency numbers.</span></span> <span data-ttu-id="e1bc5-121">Для этого в категории **"Номера для экстренного помощи"** **нажмите** кнопку "Добавить" и сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="e1bc5-121">To do this, under **Emergency numbers**, click **Add**, and then do the following:</span></span>
    1. <span data-ttu-id="e1bc5-122">**Строка набора номера для экстренного помощи:** введите строку набора экстренных служб.</span><span class="sxs-lookup"><span data-stu-id="e1bc5-122">**Emergency dial string**: Enter the emergency dial string.</span></span> <span data-ttu-id="e1bc5-123">Эта строка набора указывает на то, что звонок является экстренным.</span><span class="sxs-lookup"><span data-stu-id="e1bc5-123">This dial string indicates that a call is an emergency call.</span></span>
        > [!NOTE]
        > <span data-ttu-id="e1bc5-124">Для прямой маршрутинга мы переходить от клиентов Teams, которые отправляют экстренные вызовы со строкой "+" перед строкой вызова экстренной помощи.</span><span class="sxs-lookup"><span data-stu-id="e1bc5-124">For Direct Routing, we're transitioning away from Teams clients sending emergency calls with a "+" in front of the emergency dial string.</span></span> <span data-ttu-id="e1bc5-125">До завершения перехода шаблон голосового пути для соотнося с строкой экстренного набора номера должен обеспечить соответствие строкам, которые имеют или не имеют предыдущего "+", например 911 и +911.</span><span class="sxs-lookup"><span data-stu-id="e1bc5-125">Until the transition is completed, the voice route pattern to match an emergency dial string should ensure a match is made for strings that have and don't have a preceding "+", such as 911 and +911.</span></span> <span data-ttu-id="e1bc5-126">Например, ^ \\ +?911 или .\*.</span><span class="sxs-lookup"><span data-stu-id="e1bc5-126">For example, ^\\+?911 or .\*.</span></span>
    2. <span data-ttu-id="e1bc5-127">**Маска набора номера** для экстренного помощи: для каждого номера можно задать ноль или несколько масок для экстренного набора номера.</span><span class="sxs-lookup"><span data-stu-id="e1bc5-127">**Emergency dial mask**: For each emergency number, you can specify zero or more emergency dial masks.</span></span> <span data-ttu-id="e1bc5-128">Маска набора номера — это номер, который вы хотите перевести на значение в строке набора экстренных служб.</span><span class="sxs-lookup"><span data-stu-id="e1bc5-128">A dial mask is the number that you want to translate into the value of the emergency dial string.</span></span> <span data-ttu-id="e1bc5-129">Это позволяет набирать дополнительные номера экстренных служб и по-прежнему звонить в экстренные службы.</span><span class="sxs-lookup"><span data-stu-id="e1bc5-129">This allows for alternate emergency numbers to be dialed and still have the call reach emergency services.</span></span> <br><span data-ttu-id="e1bc5-130">Например, вы можете добавить в качестве маски набора номера экстренных служб номер 112 — номер для экстренных служб для большинства стран Европы, а номер 911 — в качестве строки экстренного набора.</span><span class="sxs-lookup"><span data-stu-id="e1bc5-130">For example, you add 112 as the emergency dial mask, which is the emergency service number for most of Europe, and 911 as the emergency dial string.</span></span> <span data-ttu-id="e1bc5-131">Пользователь Teams из Европы может не знать, что 911 — это номер для экстренного вызова в США, а при наборе номера 112 звоните по номеру 911.</span><span class="sxs-lookup"><span data-stu-id="e1bc5-131">A Teams user from Europe who is visiting may not know that 911 is the emergency number in the United States, and when they dial 112, the call is made to 911.</span></span> <span data-ttu-id="e1bc5-132">Чтобы определить несколько масок набора номера, разделите каждое значение за semicolon.</span><span class="sxs-lookup"><span data-stu-id="e1bc5-132">To define multiple dial masks, separate each value by a semicolon.</span></span> <span data-ttu-id="e1bc5-133">Например, 112:212.</span><span class="sxs-lookup"><span data-stu-id="e1bc5-133">For example, 112;212.</span></span>
    3. <span data-ttu-id="e1bc5-134">**Запись использования ДНР:** выберите запись использования телефонной сети общего пользования (ННР).</span><span class="sxs-lookup"><span data-stu-id="e1bc5-134">**PSTN usage record**: Select the Public Switched Telephone Network (PSTN) usage record.</span></span> <span data-ttu-id="e1bc5-135">Запись использования ННР используется для определения маршрутов, используемых для маршрутизации экстренных вызовов от пользователей, которым разрешено их использовать.</span><span class="sxs-lookup"><span data-stu-id="e1bc5-135">The PSTN usage record is used to determine which route is used to route emergency calls from users who are authorized to use them.</span></span> <span data-ttu-id="e1bc5-136">Маршрут, связанный с этим использованием, должен указать на магистраль SIP, выделенную для экстренных вызовов, или на шлюз ELIN, который перенаправляет экстренные вызовы в ближайший КПЭ.</span><span class="sxs-lookup"><span data-stu-id="e1bc5-136">The route associated with this usage should point to a Session Initiation Protocol (SIP) trunk dedicated to emergency calls or to an Emergency Location Identification Number (ELIN) gateway that routes emergency calls to the nearest Public Safety Answering Point (PSAP).</span></span>

    > [!NOTE]
    > <span data-ttu-id="e1bc5-137">Строки набора и маски набора должны быть уникальными в политике.</span><span class="sxs-lookup"><span data-stu-id="e1bc5-137">Dial strings and dial masks must be unique within a policy.</span></span> <span data-ttu-id="e1bc5-138">Это означает, что для политики можно определить несколько номеров для экстренного помощи и настроить несколько масок набора для строки набора номера, но каждую из них необходимо использовать только один раз.</span><span class="sxs-lookup"><span data-stu-id="e1bc5-138">This means that for a policy, you can define multiple emergency numbers and you can set multiple dial masks for a dial string, but each dial string and dial mask must only be used one time.</span></span>

6. <span data-ttu-id="e1bc5-139">Щелкните **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="e1bc5-139">Click **Save**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="e1bc5-140">С помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="e1bc5-140">Using PowerShell</span></span>

<span data-ttu-id="e1bc5-141">См. [new-CsTeamsEmergencyCallRoutingPolicy.](https://docs.microsoft.com/powershell/module/skype/new-csteamsemergencycallroutingpolicy)</span><span class="sxs-lookup"><span data-stu-id="e1bc5-141">See [New-CsTeamsEmergencyCallRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsemergencycallroutingpolicy).</span></span>

## <a name="edit-an-emergency-call-routing-policy"></a><span data-ttu-id="e1bc5-142">Изменение политики маршрутизов экстренных вызовов</span><span class="sxs-lookup"><span data-stu-id="e1bc5-142">Edit an emergency call routing policy</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="e1bc5-143">С помощью Центра администрирования Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="e1bc5-143">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="e1bc5-144">Вы можете изменить глобальную политику или любые настраиваемые политики, которые вы создаете.</span><span class="sxs-lookup"><span data-stu-id="e1bc5-144">You can edit the global policy or any custom policies that you create.</span></span>

1. <span data-ttu-id="e1bc5-145">В левой области навигации Центра администрирования Microsoft Teams перейдите к политикам голосового экстренного вызова, а затем щелкните вкладку "Политики  >   **маршрутинга экстренных вызовов".**</span><span class="sxs-lookup"><span data-stu-id="e1bc5-145">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Emergency policies**, and then click the **Call routing policies** tab.</span></span>
2. <span data-ttu-id="e1bc5-146">Выберите политику, щелкнув слева от ее имени, а затем нажмите **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="e1bc5-146">Select the policy by clicking to the left of the policy name, and then click **Edit**.</span></span>
3. <span data-ttu-id="e1bc5-147">Внести нужные изменения и нажмите кнопку **"Сохранить".**</span><span class="sxs-lookup"><span data-stu-id="e1bc5-147">Make the changes that you want, and then click **Save**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="e1bc5-148">С помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="e1bc5-148">Using PowerShell</span></span>

<span data-ttu-id="e1bc5-149">См. [set-CsTeamsEmergencyCallRoutingPolicy.](https://docs.microsoft.com/powershell/module/skype/set-csteamsemergencycallroutingpolicy)</span><span class="sxs-lookup"><span data-stu-id="e1bc5-149">See [Set-CsTeamsEmergencyCallRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsemergencycallroutingpolicy).</span></span>

## <a name="assign-a-custom-emergency-call-routing-policy-to-users"></a><span data-ttu-id="e1bc5-150">Назначение пользователям настраиваемой политики маршрутинга экстренных вызовов</span><span class="sxs-lookup"><span data-stu-id="e1bc5-150">Assign a custom emergency call routing policy to users</span></span>

[!INCLUDE [assign-policy](includes/assign-policy.md)]

<span data-ttu-id="e1bc5-151">См. также [Grant-CsTeamsEmergencyCallRoutingPolicy.](https://docs.microsoft.com/powershell/module/skype/grant-csteamsemergencycallroutingpolicy)</span><span class="sxs-lookup"><span data-stu-id="e1bc5-151">See also [Grant-CsTeamsEmergencyCallRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsemergencycallroutingpolicy).</span></span>

## <a name="assign-a-custom-emergency-call-routing-policy-to-a-network-site"></a><span data-ttu-id="e1bc5-152">Назначение настраиваемой политики маршрутизов экстренных вызовов на сетевой сайт</span><span class="sxs-lookup"><span data-stu-id="e1bc5-152">Assign a custom emergency call routing policy to a network site</span></span>

<span data-ttu-id="e1bc5-153">Используйте [командлет Set-CsTenantNetworkSite,](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite) чтобы назначить политику маршрутизации экстренных вызовов на сетевой сайт.</span><span class="sxs-lookup"><span data-stu-id="e1bc5-153">Use the [Set-CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite) cmdlet to assign an emergency calling routing policy to a network site.</span></span>

<span data-ttu-id="e1bc5-154">В этом примере показано, как назначить политику под названием "Маршрутная политика для экстренных вызовов 1" сайту "Сайт1".</span><span class="sxs-lookup"><span data-stu-id="e1bc5-154">This example shows how to assign a policy called Emergency Call Routing Policy 1 to the Site1 site.</span></span>

```PowerShell
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallRoutingPolicy "Emergency Call Routing Policy 1"
```

## <a name="related-topics"></a><span data-ttu-id="e1bc5-155">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="e1bc5-155">Related topics</span></span>

[<span data-ttu-id="e1bc5-156">Управление политиками экстренных вызовов в Teams</span><span class="sxs-lookup"><span data-stu-id="e1bc5-156">Manage emergency calling policies in Teams</span></span>](manage-emergency-calling-policies.md)

[<span data-ttu-id="e1bc5-157">Обзор PowerShell в Teams</span><span class="sxs-lookup"><span data-stu-id="e1bc5-157">Teams PowerShell overview</span></span>](teams-powershell-overview.md)

[<span data-ttu-id="e1bc5-158">Назначение политик пользователям в Teams</span><span class="sxs-lookup"><span data-stu-id="e1bc5-158">Assign policies to your users in Teams</span></span>](assign-policies.md)
