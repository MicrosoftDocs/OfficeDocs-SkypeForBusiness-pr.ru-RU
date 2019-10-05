---
title: Управление политиками маршрутизации вызова экстренной помощи в Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: jastark, roykuntz
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Сведения о том, как использовать политики маршрутизации вызова экстренной помощи и управлять ими для динамического компонента E911 в Microsoft Teams.
f1keywords: ms.teamsadmincenter.voice.emergencycallroutingpolicies.overview
ms.openlocfilehash: e7a1295d481db2d970fae2c77be2cff6834c6448
ms.sourcegitcommit: d349922409f49b52048597a56b81501163749a69
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/05/2019
ms.locfileid: "37401833"
---
# <a name="manage-emergency-call-routing-policies-in-microsoft-teams"></a><span data-ttu-id="0cc26-103">Управление политиками маршрутизации вызова экстренной помощи в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="0cc26-103">Manage emergency call routing policies in Microsoft Teams</span></span>

[!INCLUDE [preview-feature](includes/preview-feature.md)]

<span data-ttu-id="0cc26-104">Если вы развернули прямую маршрутизацию телефонной системы в своей организации, вы можете настроить номера для экстренного реагирования с помощью политик маршрутизации вызовов экстренной помощи в Microsoft Teams и указать, как будут маршрутизироваться экстренные вызовы.</span><span class="sxs-lookup"><span data-stu-id="0cc26-104">If you've deployed Phone System Direct Routing in your organization, you can use emergency call routing policies in Microsoft Teams to set up emergency numbers and specify how emergency calls are routed.</span></span> <span data-ttu-id="0cc26-105">Политика маршрутизации вызова экстренной помощи определяет, включены ли расширенные службы экстренных служб для пользователей, которым назначена политика, номера, используемые для звонков в экстренные службы (например, 911 в США), и способы маршрутизации вызовов служб экстренной помощи.</span><span class="sxs-lookup"><span data-stu-id="0cc26-105">An emergency call routing policy determines whether enhanced emergency services is enabled for users who are assigned the policy, the numbers used to call emergency services (for example, 911 in the United States), and how calls to emergency services are routed.</span></span>

<span data-ttu-id="0cc26-106">Для управления политиками маршрутизации вызовов экстренной помощи следует перейти к**политикам** **голосовой связи** > в центре администрирования Microsoft Teams или с помощью Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0cc26-106">You manage emergency call routing policies by going to **Voice** > **Emergency policies** in the Microsoft Teams admin center or by using Windows PowerShell.</span></span> <span data-ttu-id="0cc26-107">Политики можно назначить для пользователей и [сайтов сети](location-based-routing-terminology.md).</span><span class="sxs-lookup"><span data-stu-id="0cc26-107">The policies can be assigned to users and [network sites](location-based-routing-terminology.md).</span></span>

<span data-ttu-id="0cc26-108">Пользователи могут использовать глобальную политику (по умолчанию на уровне Организации) или создавать и назначать пользовательские политики.</span><span class="sxs-lookup"><span data-stu-id="0cc26-108">For users, you can use the global (Org-wide default) policy or create and assign custom policies.</span></span> <span data-ttu-id="0cc26-109">Пользователи будут автоматически получать глобальную политику, если вы не создадите и не назначаете пользовательскую политику.</span><span class="sxs-lookup"><span data-stu-id="0cc26-109">Users will automatically get the global policy unless you create and assign a custom policy.</span></span> <span data-ttu-id="0cc26-110">Имейте в виду, что вы можете изменять параметры глобальной политики, но переименовывать и удалять их нельзя.</span><span class="sxs-lookup"><span data-stu-id="0cc26-110">Keep in mind that you can edit the settings in the global policy but you can't rename or delete it.</span></span> <span data-ttu-id="0cc26-111">Для сетевых сайтов можно создавать и назначать пользовательские политики.</span><span class="sxs-lookup"><span data-stu-id="0cc26-111">For network sites, you create and assign custom policies.</span></span>

<span data-ttu-id="0cc26-112">Если вы назначили политику маршрутизации для вызова экстренной помощи на сайте сети и в качестве пользователя, а также если этот пользователь находится на сетевом сайте, политика, назначенная сетевому сайту, переопределяет политику, назначенную пользователю.</span><span class="sxs-lookup"><span data-stu-id="0cc26-112">If you assigned an emergency call routing policy to a network site and to a user and if that  user is at that network site, the policy that's assigned to the network site overrides the policy that's assigned to the user.</span></span>

## <a name="create-a-custom-emergency-call-routing-policy"></a><span data-ttu-id="0cc26-113">Создание настраиваемой политики маршрутизации вызова экстренной помощи</span><span class="sxs-lookup"><span data-stu-id="0cc26-113">Create a custom emergency call routing policy</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="0cc26-114">Использование центра администрирования Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="0cc26-114">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="0cc26-115">В левой области навигации центра администрирования Microsoft Teams перейдите в раздел политики **голосовой связи** > \*\*\*\* и перейдите на вкладку **политики маршрутизации звонков** .</span><span class="sxs-lookup"><span data-stu-id="0cc26-115">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Emergency policies**, and then click the **Call routing policies** tab.</span></span>
2. <span data-ttu-id="0cc26-116">Нажмите **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="0cc26-116">Click **Add**.</span></span>
3. <span data-ttu-id="0cc26-117">Введите имя и описание политики.</span><span class="sxs-lookup"><span data-stu-id="0cc26-117">Enter a name and description for the policy.</span></span>
4. <span data-ttu-id="0cc26-118">Для включения расширенных служб экстренной помощи включите **Расширенные службы экстренной**помощи.</span><span class="sxs-lookup"><span data-stu-id="0cc26-118">To enable enhanced emergency services, turn on **Enhanced emergency services**.</span></span> <span data-ttu-id="0cc26-119">Если включены улучшенные службы экстренной помощи, Teams извлекает из службы сведения о политике и местоположении, а также включает эти данные в ходе вызова экстренного реагирования.</span><span class="sxs-lookup"><span data-stu-id="0cc26-119">When enhanced emergency services is enabled, Teams retrieves policy and location information from the service and includes that information as part of the emergency call.</span></span>
5. <span data-ttu-id="0cc26-120">Определите одно из нескольких номеров для экстренного реагирования.</span><span class="sxs-lookup"><span data-stu-id="0cc26-120">Define one of more emergency numbers.</span></span> <span data-ttu-id="0cc26-121">Для этого в разделе **Номера для экстренного**реагирования выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="0cc26-121">To do this, under **Emergency numbers**, do the following:</span></span>
    1. <span data-ttu-id="0cc26-122">**Строка набора номера для экстренного звонка**: введите строку набора номера.</span><span class="sxs-lookup"><span data-stu-id="0cc26-122">**Emergency dial string**: Enter the emergency dial string.</span></span> <span data-ttu-id="0cc26-123">Эта строка набора номера указывает на то, что звонок является экстренным звонком.</span><span class="sxs-lookup"><span data-stu-id="0cc26-123">This dial string indicates that a call is an emergency call.</span></span>
    2. <span data-ttu-id="0cc26-124">**Маска для экстренного набора**номера: для каждого номера для экстренного реагирования можно указать несколько масок экстренного набора номера (ноль или больше).</span><span class="sxs-lookup"><span data-stu-id="0cc26-124">**Emergency dial mask**: For each emergency number, you can specify zero or more emergency dial masks.</span></span> <span data-ttu-id="0cc26-125">Маска набора — это число, которое нужно перевести в значение строки набора экстренных звонков.</span><span class="sxs-lookup"><span data-stu-id="0cc26-125">A dial mask is the number that you want to translate into the value of the emergency dial string.</span></span> <span data-ttu-id="0cc26-126">Это позволяет звонить по другим номерам для экстренного реагирования и по-прежнему поддерживать экстренные службы.</span><span class="sxs-lookup"><span data-stu-id="0cc26-126">This allows for alternate emergency numbers to be dialed and still have the call reach emergency services.</span></span> <br><span data-ttu-id="0cc26-127">Например, вы добавите в качестве маски для экстренного набора 112, который является номером службы экстренной помощи в большинстве стран Европы и 911 как строка набора экстренных номеров.</span><span class="sxs-lookup"><span data-stu-id="0cc26-127">For example, you add 112 as the emergency dial mask, which is the emergency service number for most of Europe, and 911 as the emergency dial string.</span></span> <span data-ttu-id="0cc26-128">Пользователь Teams из Европы, который посещает Посетители, может не знать, что 911 является номером для экстренного реагирования в США, и при набрать 112 звонок будет выполнен до 911.</span><span class="sxs-lookup"><span data-stu-id="0cc26-128">A Teams user from Europe who is visiting may not know that 911 is the emergency number in the United States, and when they dial 112, the call is made to 911.</span></span> <span data-ttu-id="0cc26-129">Чтобы задать несколько масок набора номера, разделяйте их значения точкой с запятой.</span><span class="sxs-lookup"><span data-stu-id="0cc26-129">To define multiple dial masks, separate each value by a semicolon.</span></span> <span data-ttu-id="0cc26-130">Например, 112; 212.</span><span class="sxs-lookup"><span data-stu-id="0cc26-130">For example, 112;212.</span></span>
    3. <span data-ttu-id="0cc26-131">**Использование PSTN**: выберите общедоступную телефонную сеть с коммутируемым подключением (КТСОП).</span><span class="sxs-lookup"><span data-stu-id="0cc26-131">**PSTN Usage**: Select the public switched telephone network (PSTN) usage.</span></span> <span data-ttu-id="0cc26-132">Использование PSTN используется, чтобы определить, какой маршрут используется для направления экстренных вызовов от пользователей, которым разрешено их использовать.</span><span class="sxs-lookup"><span data-stu-id="0cc26-132">The PSTN usage is used to determine which route is used to route emergency calls from users who are authorized to use them.</span></span> <span data-ttu-id="0cc26-133">Маршрут, связанный с этим использованием, должен указывать на магистраль SIP, выделенный для вызова экстренной помощи, или на шлюз с идентификационным номером для экстренной помощи (Елин), который маршрутизирует экстренные вызовы в ближайшую точку ответа на общедоступную безопасность (ПСАП).</span><span class="sxs-lookup"><span data-stu-id="0cc26-133">The route associated with this usage should point to an SIP trunk dedicated to emergency calls or to an Emergency Location Identification Number (ELIN) gateway that routes emergency calls to the nearest Public Safety Answering Point (PSAP).</span></span>

    > [!NOTE]
    > <span data-ttu-id="0cc26-134">Строки набора номера и маски набора должны быть уникальными в пределах политики.</span><span class="sxs-lookup"><span data-stu-id="0cc26-134">Dial strings and dial masks must be unique within a policy.</span></span> <span data-ttu-id="0cc26-135">Это означает, что для политики можно задать несколько номеров для экстренного реагирования, и вы можете задать несколько масок набора номера для строки набора номера, но каждая строка набора номера и маска набора должны использоваться только один раз.</span><span class="sxs-lookup"><span data-stu-id="0cc26-135">This means that for a policy, you can define multiple emergency numbers and you can set multiple dial masks for a dial string, but each dial string and dial mask must only be used one time.</span></span>

6. <span data-ttu-id="0cc26-136">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="0cc26-136">Click **Save**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="0cc26-137">Использование PowerShell</span><span class="sxs-lookup"><span data-stu-id="0cc26-137">Using PowerShell</span></span>

<span data-ttu-id="0cc26-138">Просмотреть раздел [New-кстеамсемерженцикаллраутингполици](https://docs.microsoft.com/powershell/module/skype/new-csteamsemergencycallroutingpolicy).</span><span class="sxs-lookup"><span data-stu-id="0cc26-138">See [New-CsTeamsEmergencyCallRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsemergencycallroutingpolicy).</span></span>

## <a name="edit-an-emergency-call-routing-policy"></a><span data-ttu-id="0cc26-139">Изменение политики маршрутизации вызова экстренной помощи</span><span class="sxs-lookup"><span data-stu-id="0cc26-139">Edit an emergency call routing policy</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="0cc26-140">Использование центра администрирования Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="0cc26-140">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="0cc26-141">Вы можете изменить глобальную политику или созданные вами пользовательские политики.</span><span class="sxs-lookup"><span data-stu-id="0cc26-141">You can edit the global policy or any custom policies that you create.</span></span>

1. <span data-ttu-id="0cc26-142">В левой области навигации центра администрирования Microsoft Teams перейдите в раздел политики **голосовой связи** > \*\*\*\* и перейдите на вкладку **политики маршрутизации звонков** .</span><span class="sxs-lookup"><span data-stu-id="0cc26-142">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Emergency policies**, and then click the **Call routing policies** tab.</span></span>
2. <span data-ttu-id="0cc26-143">Выберите политику, щелкнув слева от ее имени, а затем нажмите кнопку **изменить**.</span><span class="sxs-lookup"><span data-stu-id="0cc26-143">Select the policy by clicking to the left of the policy name, and then click **Edit**.</span></span>
3. <span data-ttu-id="0cc26-144">Внесите нужные изменения и нажмите кнопку **сохранить**.</span><span class="sxs-lookup"><span data-stu-id="0cc26-144">Make the changes that you want, and then click **Save**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="0cc26-145">Использование PowerShell</span><span class="sxs-lookup"><span data-stu-id="0cc26-145">Using PowerShell</span></span>

<span data-ttu-id="0cc26-146">Смотрите раздел [Set-кстеамсемерженцикаллраутингполици](https://docs.microsoft.com/powershell/module/skype/set-csteamsemergencycallroutingpolicy).</span><span class="sxs-lookup"><span data-stu-id="0cc26-146">See [Set-CsTeamsEmergencyCallRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsemergencycallroutingpolicy).</span></span>

## <a name="assign-a-custom-emergency-call-routing-policy-to-users"></a><span data-ttu-id="0cc26-147">Назначение настраиваемой политики маршрутизации вызова экстренной помощи пользователям</span><span class="sxs-lookup"><span data-stu-id="0cc26-147">Assign a custom emergency call routing policy to users</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="0cc26-148">Использование центра администрирования Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="0cc26-148">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="0cc26-149">В левой области навигации центра администрирования Microsoft Teams перейдите в раздел **Пользователи**и выберите пользователя.</span><span class="sxs-lookup"><span data-stu-id="0cc26-149">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click the user.</span></span>
2. <span data-ttu-id="0cc26-150">Нажмите **политики**, а затем рядом с пунктом **назначенные политики**нажмите кнопку **изменить**.</span><span class="sxs-lookup"><span data-stu-id="0cc26-150">Click **Policies**, and then next to **Assigned policies**, click **Edit**.</span></span>
3. <span data-ttu-id="0cc26-151">В разделе **Политика маршрутизации вызова экстренного**реагирования выберите политику, которую вы хотите назначить, и нажмите кнопку **сохранить**.</span><span class="sxs-lookup"><span data-stu-id="0cc26-151">Under **Emergency call routing policy**, select the policy you want to assign, and then click **Save**.</span></span>

<span data-ttu-id="0cc26-152">Чтобы назначить специальную политику групп нескольким пользователям одновременно, ознакомьтесь с [разгруппым изменением параметров пользователей Teams](edit-user-settings-in-bulk.md).</span><span class="sxs-lookup"><span data-stu-id="0cc26-152">To assign a custom teams policy to multiple users at a time, see [Edit Teams user settings in bulk](edit-user-settings-in-bulk.md).</span></span>

<span data-ttu-id="0cc26-153">Кроме того, вы можете сделать следующее:</span><span class="sxs-lookup"><span data-stu-id="0cc26-153">Or, you can also do the following:</span></span>

1. <span data-ttu-id="0cc26-154">В левой области навигации центра администрирования Microsoft Teams перейдите в раздел политики **голосовой связи** > \*\*\*\* и перейдите на вкладку **политики маршрутизации звонков** .</span><span class="sxs-lookup"><span data-stu-id="0cc26-154">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Emergency policies**, and then click the **Call routing policies** tab.</span></span>
2. <span data-ttu-id="0cc26-155">Выберите политику, щелкнув слева от имени политики.</span><span class="sxs-lookup"><span data-stu-id="0cc26-155">Select the policy by clicking to the left of the policy name.</span></span>
3. <span data-ttu-id="0cc26-156">Выберите **Управление пользователями**.</span><span class="sxs-lookup"><span data-stu-id="0cc26-156">Select **Manage users**.</span></span>
4. <span data-ttu-id="0cc26-157">В области **Управление пользователями** найдите пользователя по отображаемому имени или по имени пользователя, выберите имя и нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="0cc26-157">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then select **Add**.</span></span> <span data-ttu-id="0cc26-158">Повторите этот шаг для каждого пользователя, которого вы хотите добавить.</span><span class="sxs-lookup"><span data-stu-id="0cc26-158">Repeat this step for each user that you want to add.</span></span>
5. <span data-ttu-id="0cc26-159">Завершив добавление пользователей, нажмите кнопку **сохранить**.</span><span class="sxs-lookup"><span data-stu-id="0cc26-159">When you're finished adding users, click **Save**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="0cc26-160">Использование PowerShell</span><span class="sxs-lookup"><span data-stu-id="0cc26-160">Using PowerShell</span></span>

#### <a name="assign-a-custom-emergency-call-routing-policy-to-a-user"></a><span data-ttu-id="0cc26-161">Назначение пользователю политики маршрутизации для вызова экстренной помощи</span><span class="sxs-lookup"><span data-stu-id="0cc26-161">Assign a custom emergency call routing policy to a user</span></span>

<span data-ttu-id="0cc26-162">Просмотр [Grant-кстеамсемерженцикаллраутингполици](https://docs.microsoft.com/powershell/module/skype/grant-csteamsemergencycallroutingpolicy).</span><span class="sxs-lookup"><span data-stu-id="0cc26-162">See [Grant-CsTeamsEmergencyCallRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsemergencycallroutingpolicy).</span></span>

### <a name="assign-a-custom-emergency-call-routing-policy-to-users-in-a-group"></a><span data-ttu-id="0cc26-163">Назначение настраиваемой политики маршрутизации вызова экстренной помощи пользователям в группе</span><span class="sxs-lookup"><span data-stu-id="0cc26-163">Assign a custom emergency call routing policy to users in a group</span></span>

<span data-ttu-id="0cc26-164">Вы можете назначить специальную политику маршрутизации вызова экстренной помощи нескольким пользователям, которые уже были идентифицированы.</span><span class="sxs-lookup"><span data-stu-id="0cc26-164">You may want to assign a custom emergency call routing policy to multiple users that you’ve already identified.</span></span> <span data-ttu-id="0cc26-165">Например, может потребоваться назначить политику всем пользователям в группе безопасности или рассылки.</span><span class="sxs-lookup"><span data-stu-id="0cc26-165">For example, you may want to assign a policy to all users in a security or distribution group.</span></span> <span data-ttu-id="0cc26-166">Это можно сделать, подключив службу Azure Active Directory PowerShell для Graph и модуль PowerShell для Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="0cc26-166">You can do this by connecting to the Azure Active Directory PowerShell for Graph module and the Skype for Business PowerShell module.</span></span>

<span data-ttu-id="0cc26-167">В этом примере мы назначаем политику, которая называется политикой маршрутизации вызовов экстренной помощи, для всех пользователей в группе Contoso HR.</span><span class="sxs-lookup"><span data-stu-id="0cc26-167">In this example, we assign a policy called HR Emergency Call Routing Policy to all users in the Contoso HR group.</span></span>  

> [!NOTE]
> <span data-ttu-id="0cc26-168">Убедитесь, что вы подключаетесь к модулю Azure Active Directory PowerShell для модуля Graph и Skype для бизнеса PowerShell, выполнив действия, описанные в разделе [подключение ко всем службам Office 365 в одном окне Windows PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).</span><span class="sxs-lookup"><span data-stu-id="0cc26-168">Make sure you first connect to the Azure Active Directory PowerShell for Graph module and Skype for Business PowerShell module by following the steps in [Connect to all Office 365 services in a single Windows PowerShell window](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).</span></span>

<span data-ttu-id="0cc26-169">Получить Граупобжектид определенной группы.</span><span class="sxs-lookup"><span data-stu-id="0cc26-169">Get the GroupObjectId of the particular group.</span></span>
```
$group = Get-AzureADGroup -SearchString "Contoso HR"
```
<span data-ttu-id="0cc26-170">Получение участников указанной группы.</span><span class="sxs-lookup"><span data-stu-id="0cc26-170">Get the members of the specified group.</span></span>
```
$members = Get-AzureADGroupMember -ObjectId $group.ObjectId -All $true | Where-Object {$_.ObjectType -eq "User"}
```
<span data-ttu-id="0cc26-171">Назначьте всем пользователям в группе определенную политику групп.</span><span class="sxs-lookup"><span data-stu-id="0cc26-171">Assign all users in the group to a particular teams policy.</span></span> <span data-ttu-id="0cc26-172">В данном примере это политика маршрутизации для экстренных вызовов.</span><span class="sxs-lookup"><span data-stu-id="0cc26-172">In this example, it's HR Emergency Call Routing Policy.</span></span>
```
$members | ForEach-Object { Grant-CsTeamsChannelsPolicy -PolicyName "HR Emergency Call Routing Policy" -Identity $_.EmailAddress}
``` 
<span data-ttu-id="0cc26-173">Для выполнения этой команды может потребоваться несколько минут в зависимости от количества участников в группе.</span><span class="sxs-lookup"><span data-stu-id="0cc26-173">Depending on the number of members in the group, this command may take several minutes to execute.</span></span>

## <a name="assign-a-custom-emergency-call-routing-policy-to-a-network-site"></a><span data-ttu-id="0cc26-174">Назначение настраиваемой политики маршрутизации вызова экстренной помощи сетевому сайту</span><span class="sxs-lookup"><span data-stu-id="0cc26-174">Assign a custom emergency call routing policy to a network site</span></span>

<span data-ttu-id="0cc26-175">Используйте командлет [Set-кстенантнетворксите](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite) , чтобы назначить политику маршрутизации вызова экстренной помощи сетевому сайту.</span><span class="sxs-lookup"><span data-stu-id="0cc26-175">Use the [Set-CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite) cmdlet to assign an emergency calling routing policy to a network site.</span></span>

<span data-ttu-id="0cc26-176">В этом примере показано, как назначить на сайт site1 политику с именем политики маршрутизации для вызова экстренной помощи.</span><span class="sxs-lookup"><span data-stu-id="0cc26-176">This example shows how to assign a policy called Emergency Call Routing Policy 1 to the Site1 site.</span></span>

```
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallRoutingPolicy "Emergency Call Routing Policy 1"
```

## <a name="related-topics"></a><span data-ttu-id="0cc26-177">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="0cc26-177">Related topics</span></span>

- [<span data-ttu-id="0cc26-178">Управление политиками вызова экстренной помощи в Teams</span><span class="sxs-lookup"><span data-stu-id="0cc26-178">Manage emergency calling policies in Teams</span></span>](manage-emergency-calling-policies.md)
- [<span data-ttu-id="0cc26-179">Обзор PowerShell в Teams</span><span class="sxs-lookup"><span data-stu-id="0cc26-179">Teams PowerShell overview</span></span>](teams-powershell-overview.md)
