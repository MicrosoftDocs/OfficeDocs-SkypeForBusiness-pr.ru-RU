---
title: Аудиоконференция по сети
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: oscarr
ms.topic: conceptual
ms.tgt.pltfrm: cloud
audience: admin
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
- m365initiative-meetings
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: Ниже описаны функции open Preview для аудиоконференции в сети.
ms.openlocfilehash: d6df81cc077c69fdeb4246d682797d2ebb26b875
ms.sourcegitcommit: 950387da2a2c094b7580bcf81ae5d8b6dfba0d6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2021
ms.locfileid: "51637841"
---
# <a name="open-preview-of-on-network-conferencing-for-audio-conferencing"></a><span data-ttu-id="75ae5-103">Открытие предварительного просмотра интернет-аудиоконференции</span><span class="sxs-lookup"><span data-stu-id="75ae5-103">Open Preview of On-network Conferencing for Audio Conferencing</span></span>

<span data-ttu-id="75ae5-104">Открытая предварительная версия интернет-конференции доступна для всех клиентов.</span><span class="sxs-lookup"><span data-stu-id="75ae5-104">The Open Preview of On-network Conferencing is available to all customers.</span></span> <span data-ttu-id="75ae5-105">С помощью сетевой аудиоконференции организации могут отправлять входящие и исходящие звонки на телефонные номера Майкрософт через прямую маршрутизацию.</span><span class="sxs-lookup"><span data-stu-id="75ae5-105">On-network Conferencing allows organizations to send inbound and outbound Audio Conferencing calls to Microsoft dial-in numbers through Direct Routing.</span></span> <span data-ttu-id="75ae5-106">Эта возможность не предназначена для расширения поддержки аудиоконференций на номера сторонних телефонных номеров.</span><span class="sxs-lookup"><span data-stu-id="75ae5-106">This capability is not intended to extend the support of Audio Conferencing to third party dial-in numbers.</span></span> <span data-ttu-id="75ae5-107">Сетовая аудиоконференция не поддерживается, если она используется для направления входящие вызовы в службу аудиоконференций через номера сторонних телефонных номеров или исходящие звонки на ПС из моста аудиоконференций Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="75ae5-107">On-network Conferencing is not supported if it is used to route inbound calls to the Audio Conferencing service through third party dial-in phone numbers or outbound calls to the PSTN from Microsoft Audio Conferencing Bridge.</span></span> 

<span data-ttu-id="75ae5-108">В этой статье описаны необходимые условия и действия по настройке, необходимые для настройки возможности интернет-связи в организации.</span><span class="sxs-lookup"><span data-stu-id="75ae5-108">This article describes the prerequisites and configuration steps required to enable On-network Conferencing for your organization.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="75ae5-109">Сетевое оборудование для телефонной связи в Индии не должно быть развернуто.</span><span class="sxs-lookup"><span data-stu-id="75ae5-109">On-network Conferencing must NOT be deployed with any telephony equipment in India.</span></span>
  
## <a name="prerequisites"></a><span data-ttu-id="75ae5-110">Необходимые компоненты</span><span class="sxs-lookup"><span data-stu-id="75ae5-110">Prerequisites</span></span>

<span data-ttu-id="75ae5-111">Перед настройкой интернет-связи убедитесь, что ваша организация соответствует следующим требованиям:</span><span class="sxs-lookup"><span data-stu-id="75ae5-111">Before configuring On-network Conferencing, make sure your organization meets the following prerequisites:</span></span> 

- <span data-ttu-id="75ae5-112">Убедитесь, что все пользователи в организации, у которых включена или включена аудиоконференция, используют Teams для всех собраний.</span><span class="sxs-lookup"><span data-stu-id="75ae5-112">Ensure that all users in your organization who are enabled, or will be enabled, for Audio Conferencing are using Teams for all Meetings.</span></span> <span data-ttu-id="75ae5-113">Маршрутия входящие и исходящие вызовы аудиоконференции с помощью сетевой аудиоконференции поддерживается только для собраний Teams.</span><span class="sxs-lookup"><span data-stu-id="75ae5-113">The routing of inbound and outbound Audio Conferencing calls through On-network Conferencing is only supported for Teams meetings.</span></span>

- <span data-ttu-id="75ae5-114">Назначьте лицензии на аудиоконференцию всем пользователям, которые будут использовать эту функцию.</span><span class="sxs-lookup"><span data-stu-id="75ae5-114">Assign Audio Conferencing licenses to all users who will be using On-network Conferencing.</span></span>

- <span data-ttu-id="75ae5-115">Настройка службы аудиоконференций.</span><span class="sxs-lookup"><span data-stu-id="75ae5-115">Set up the Audio Conferencing service.</span></span> <span data-ttu-id="75ae5-116">Дополнительные сведения см. в сведениях о настройках аудиоконференций [для Microsoft Teams.](set-up-audio-conferencing-in-teams.md)</span><span class="sxs-lookup"><span data-stu-id="75ae5-116">For additional information, see [Set up Audio Conferencing for Microsoft Teams](set-up-audio-conferencing-in-teams.md).</span></span>

- <span data-ttu-id="75ae5-117">Настройка граничного контроллера сеанса (SBC) для прямой маршрутки.</span><span class="sxs-lookup"><span data-stu-id="75ae5-117">Set up your Session Border Controller (SBC) for Direct Routing.</span></span> <span data-ttu-id="75ae5-118">Дополнительные сведения см. в планах ["Прямая маршрутия"](direct-routing-plan.md) и ["Настройка прямой маршрутинга".](direct-routing-configure.md)</span><span class="sxs-lookup"><span data-stu-id="75ae5-118">For additional information, see [Plan Direct Routing](direct-routing-plan.md) and [Configure Direct Routing](direct-routing-configure.md).</span></span> 

  <span data-ttu-id="75ae5-119">Если прямая маршрутия настраивается только для аудиоконференции, необходимо выполнить только шаг 1 . Подключение SBC к сетевым сетям.</span><span class="sxs-lookup"><span data-stu-id="75ae5-119">If you are setting up Direct Routing only for the purposes of Audio Conferencing, then you need only complete “Step 1: Connect your SBC” for On-network Conferencing.</span></span>
  
## <a name="enable-the-routing-of-dial-in-calls-to-microsoft-audio-conferencing-through-direct-routing"></a><span data-ttu-id="75ae5-120">Включить маршрутизацию звонков с телефонным доступом на аудиоконференцию Майкрософт через прямую маршрутизацию</span><span class="sxs-lookup"><span data-stu-id="75ae5-120">Enable the routing of dial-in calls to Microsoft Audio Conferencing through Direct Routing</span></span> 

<span data-ttu-id="75ae5-121">Чтобы перенаправлять звонки с телефонным доступом, сделанные пользователями локальной сети, в службу аудиоконференций с помощью прямой маршрутики, необходимо настроить соответствующие правила маршрутики для SBCs и частных филиалов Exchange.</span><span class="sxs-lookup"><span data-stu-id="75ae5-121">To route dial-in calls made by your on-premises users to the Audio Conferencing service through Direct Routing, you need to configure appropriate routing rules for your SBCs and Private Branch Exchange(s) (PBXs).</span></span>

<span data-ttu-id="75ae5-122">Необходимо настроить телефонное оборудование ваших сайтов для перенаправки звонков на любой номер службы моста конференц-связи вашей организации через линию прямой маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="75ae5-122">You need to configure the telephony equipment of your sites to route calls to any service number of the conference bridge of your organization through a Direct Routing trunk.</span></span>

<span data-ttu-id="75ae5-123">Номера служб можно найти в Центре администрирования Teams в рамках моста собраний **> conferencing Bridges** или с помощью командлета Get-CsOnlineDialInConferencingBridge в Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="75ae5-123">You can find the service numbers in Teams admin center under **Meetings -> Conferencing Bridges** or by using the Skype for Business Online PowerShell cmdlet Get-CsOnlineDialInConferencingBridge.</span></span> <span data-ttu-id="75ae5-124">Дополнительные сведения см. в списке номеров для аудиоконференций [в Microsoft Teams.](see-a-list-of-audio-conferencing-numbers-in-teams.md)</span><span class="sxs-lookup"><span data-stu-id="75ae5-124">For additional information, see a list of [Audio Conferencing numbers in Microsoft Teams](see-a-list-of-audio-conferencing-numbers-in-teams.md).</span></span>

> [!NOTE]
> <span data-ttu-id="75ae5-125">Эта функция недоступна пользователям с лицензией на аудиоконференцию с поминутной оплатой.</span><span class="sxs-lookup"><span data-stu-id="75ae5-125">This feature is not available to users with the pay-per-minute Audio Conferencing license.</span></span>

## <a name="enable-the-routing-of-teams-meeting-dial-out-calls-through-direct-routing"></a><span data-ttu-id="75ae5-126">Включить маршрутику звонков с телефонным вызовом на собрании Teams с помощью прямой маршрутинга</span><span class="sxs-lookup"><span data-stu-id="75ae5-126">Enable the routing of Teams meeting dial-out calls through Direct Routing</span></span>

<span data-ttu-id="75ae5-127">Вызовы телефонного звонка в Teams начаты из собрания в вашей организации на номера ЗВОНКОВ по ДНР, включая звонки на мой номер и вызовы для привлечения новых участников к собранию.</span><span class="sxs-lookup"><span data-stu-id="75ae5-127">Teams meeting dial-out calls are initiated from within a meeting in your organization to PSTN numbers, including call-me-at calls and calls to bring new participants to a meeting.</span></span> 

<span data-ttu-id="75ae5-128">Чтобы включить маршрутизация для собраний Teams с помощью прямой маршрутизации сетевым пользователям, необходимо создать и назначить политику маршрутизации аудиоконференции под названием "OnlineAudioConferencingRoutingPolicy".</span><span class="sxs-lookup"><span data-stu-id="75ae5-128">To enable Teams meeting dial-out routing through Direct Routing to on-network users, you need to create and assign an Audio Conferencing routing policy called “OnlineAudioConferencingRoutingPolicy”.</span></span> 

<span data-ttu-id="75ae5-129">Политика OnlineAudioConferencingRoutingPolicy эквивалентна политике CsOnlineVoiceRoutingPolicy для звонков по 1:1 через прямую маршрутизирование.</span><span class="sxs-lookup"><span data-stu-id="75ae5-129">The OnlineAudioConferencingRoutingPolicy policy is equivalent to the CsOnlineVoiceRoutingPolicy for 1:1 PSTN calls via Direct Routing.</span></span> <span data-ttu-id="75ae5-130">Управлять политикой OnlineAudioConferencingRoutingPolicy можно с помощью следующих cmdlets:</span><span class="sxs-lookup"><span data-stu-id="75ae5-130">The OnlineAudioConferencingRoutingPolicy policy can be managed by using the following cmdlets:</span></span>

-   <span data-ttu-id="75ae5-131">New-CsOnlineAudioConferencingRoutingPolicy</span><span class="sxs-lookup"><span data-stu-id="75ae5-131">New-CsOnlineAudioConferencingRoutingPolicy</span></span>
- <span data-ttu-id="75ae5-132">Set-CsOnlineAudioConferencingRoutingPolicy</span><span class="sxs-lookup"><span data-stu-id="75ae5-132">Set-CsOnlineAudioConferencingRoutingPolicy</span></span>
- <span data-ttu-id="75ae5-133">Get-CsOnlineAudioConferencingRoutingPolicy</span><span class="sxs-lookup"><span data-stu-id="75ae5-133">Get-CsOnlineAudioConferencingRoutingPolicy</span></span>
- <span data-ttu-id="75ae5-134">Grant-CsOnlineAudioConferencingRoutingPolicy</span><span class="sxs-lookup"><span data-stu-id="75ae5-134">Grant-CsOnlineAudioConferencingRoutingPolicy</span></span>
- <span data-ttu-id="75ae5-135">Remove-CsOnlineAudioConferencingRoutingPolicy</span><span class="sxs-lookup"><span data-stu-id="75ae5-135">Remove-CsOnlineAudioConferencingRoutingPolicy</span></span>

<span data-ttu-id="75ae5-136">Дополнительные сведения о маршрутинге для прямой маршрутки см. в подстройке "Настройка голосовой маршрутии [для прямой маршрутинга".](direct-routing-voice-routing.md)</span><span class="sxs-lookup"><span data-stu-id="75ae5-136">For more information about routing for Direct Routing, see [Configure voice routing for Direct Routing](direct-routing-voice-routing.md).</span></span>


<span data-ttu-id="75ae5-137">Чтобы включить маршрутику звонков для звонков с прямой маршрутии, необходимо:</span><span class="sxs-lookup"><span data-stu-id="75ae5-137">To enable the routing of meeting dial-out calls through Direct Routing, you need to:</span></span> 

- <span data-ttu-id="75ae5-138">Настройка политик маршрутизации аудиоконференций</span><span class="sxs-lookup"><span data-stu-id="75ae5-138">Configure Audio Conferencing routing policies</span></span>
- <span data-ttu-id="75ae5-139">Настройка маршрутизации на телефонном оборудовании организации</span><span class="sxs-lookup"><span data-stu-id="75ae5-139">Configure the routing on the telephony equipment of your organization</span></span>
- <span data-ttu-id="75ae5-140">(Необязательно) Настройка набора номера</span><span class="sxs-lookup"><span data-stu-id="75ae5-140">(Optional) Configure a dial plan</span></span>

<span data-ttu-id="75ae5-141">Исходят звонки из собраний Teams будут приходить с номера службы по умолчанию на мосте конференц-зала.</span><span class="sxs-lookup"><span data-stu-id="75ae5-141">Dial-out calls from Teams meetings are coming from the default service number on the conference bridge.</span></span> <span data-ttu-id="75ae5-142">Дополнительные сведения о номере службы по умолчанию для моста аудиоконференций см. в сведениях об изменении номеров телефонов для моста [аудиоконференции.](change-the-phone-numbers-on-your-audio-conferencing-bridge.md)</span><span class="sxs-lookup"><span data-stu-id="75ae5-142">For additional information on the default service number of your Audio Conferencing bridge, see [Change the phone numbers on your Audio Conferencing bridge](change-the-phone-numbers-on-your-audio-conferencing-bridge.md).</span></span>

### <a name="configure-audio-conferencing-routing-policies"></a><span data-ttu-id="75ae5-143">Настройка политик маршрутизации аудиоконференций</span><span class="sxs-lookup"><span data-stu-id="75ae5-143">Configure Audio Conferencing routing policies</span></span>

<span data-ttu-id="75ae5-144">Политика маршрутизации аудиоконференции OnlineAudioConferencingRoutingPolicy определяет, какие звонки с телефонного звонка на собрания перенаправляются на линии прямой маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="75ae5-144">The Audio Conferencing routing policy OnlineAudioConferencingRoutingPolicy determines which meeting dial-out calls are routed to Direct Routing trunks.</span></span> <span data-ttu-id="75ae5-145">Если вы знакомы с политикой CsOnlineVoiceRoutingPolicy, эта политика работает почти так же.</span><span class="sxs-lookup"><span data-stu-id="75ae5-145">If you are familiar with the CsOnlineVoiceRoutingPolicy policy, this policy works in a very similar way.</span></span>

<span data-ttu-id="75ae5-146">Чтобы настроить политики маршрутинга аудиоконференций, необходимо сделать следующее:</span><span class="sxs-lookup"><span data-stu-id="75ae5-146">The following steps are needed to set up Audio Conferencing routing policies:</span></span>
1.  <span data-ttu-id="75ae5-147">Создание использования ННР</span><span class="sxs-lookup"><span data-stu-id="75ae5-147">Create PSTN usages</span></span>
2.  <span data-ttu-id="75ae5-148">Настройка голосовых маршрутов</span><span class="sxs-lookup"><span data-stu-id="75ae5-148">Configure voice routes</span></span>
3.  <span data-ttu-id="75ae5-149">Создание политик маршрутизации голосовой маршрутизации для аудиоконференций</span><span class="sxs-lookup"><span data-stu-id="75ae5-149">Create Audio Conferencing voice routing policies</span></span>
4.  <span data-ttu-id="75ae5-150">Назначение политики пользователям</span><span class="sxs-lookup"><span data-stu-id="75ae5-150">Assign a policy to your users</span></span>


#### <a name="create-pstn-usages"></a><span data-ttu-id="75ae5-151">Создание использования ННР</span><span class="sxs-lookup"><span data-stu-id="75ae5-151">Create PSTN usages</span></span>

<span data-ttu-id="75ae5-152">Использование услуг ННР — это наборы голосовых маршрутов.</span><span class="sxs-lookup"><span data-stu-id="75ae5-152">PSTN usages are collections of voice routes.</span></span> <span data-ttu-id="75ae5-153">При инициирующем звонке из собрания организатора голосовые маршруты используются для определения пути маршрутизов звонка на основе использования услуг ННР, связанных с пользователем с помощью политики голосовой маршрутки.</span><span class="sxs-lookup"><span data-stu-id="75ae5-153">When a dial-out call is initiated from the meeting of a given organizer, voice routes will be used to determine the routing path of the call based on the PSTN usages that are associated to the user via the user’s voice routing policy.</span></span>

<span data-ttu-id="75ae5-154">Вы можете создать использование ННР с помощью cmdlet "Set-CsOnlinePstnUsage".</span><span class="sxs-lookup"><span data-stu-id="75ae5-154">You can create a PSTN usage by using the “Set-CsOnlinePstnUsage” cmdlet.</span></span> <span data-ttu-id="75ae5-155">Например:</span><span class="sxs-lookup"><span data-stu-id="75ae5-155">For Example:</span></span>

```powershell
Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="US and Canada"}
```

#### <a name="configure-voice-routes"></a><span data-ttu-id="75ae5-156">Настройка голосовых маршрутов</span><span class="sxs-lookup"><span data-stu-id="75ae5-156">Configure voice routes</span></span>

<span data-ttu-id="75ae5-157">Voice routes determine the PSTN gateway that should be used to route a call based on the phone number that is dialed from a Teams meeting.</span><span class="sxs-lookup"><span data-stu-id="75ae5-157">Voice routes determine the PSTN gateway that should be used to route a call based on the phone number that is dialed from a Teams meeting.</span></span> <span data-ttu-id="75ae5-158">Voice Routes determine the PSTN gateway that should be used to route a call by matching the phone number dialed from a Teams meeting with a regex pattern.</span><span class="sxs-lookup"><span data-stu-id="75ae5-158">Voice routes determine the PSTN gateway that should be used to route a given call by matching the phone number dialed from a Teams meeting with a regex pattern.</span></span> <span data-ttu-id="75ae5-159">При создании голосового маршрута он должен быть связан с одним или несколько использованием услуг ННР.</span><span class="sxs-lookup"><span data-stu-id="75ae5-159">When creating a voice route, the route must be associated to one or more PSTN usages.</span></span>

<span data-ttu-id="75ae5-160">Вы можете создать голосовой маршрут и определить regex и шлюзы, которые будут связаны с голосовым маршрутом, с помощью cmdlet "New-CsOnlineVoiceRoute".</span><span class="sxs-lookup"><span data-stu-id="75ae5-160">You can create a voice route and define the regex and gateways to be associated with the voice route by using the “New-CsOnlineVoiceRoute” cmdlet.</span></span> <span data-ttu-id="75ae5-161">Например:</span><span class="sxs-lookup"><span data-stu-id="75ae5-161">For Example:</span></span>

```powershell
New-CsOnlineVoiceRoute -Identity "Redmond 1" -NumberPattern "^\+1(425|206)(\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
```

#### <a name="create-audio-conferencing-voice-routing-policies"></a><span data-ttu-id="75ae5-162">Создание политик маршрутизации голосовой маршрутизации для аудиоконференций</span><span class="sxs-lookup"><span data-stu-id="75ae5-162">Create Audio Conferencing voice routing policies</span></span>

<span data-ttu-id="75ae5-163">Политики маршрутизации голосовой связи аудиоконференций определяют, какие маршруты можно использовать для направления звонка из собраний организатора на основе целевого номера телефона исходя из телефонного звонка.</span><span class="sxs-lookup"><span data-stu-id="75ae5-163">Audio Conferencing voice routing policies determine the possible routes that can be used to route a call originating from the meetings of an organizer based on the target phone number of the meeting dial-out call.</span></span> <span data-ttu-id="75ae5-164">Политики маршрутинга голосовой связи с аудиоконференцией связаны с одним или нескольком использованием услуг ННР, которые, в свою очередь, определяют возможные маршруты, которые будут использоваться для звонков с телефонным вызовом организаторов, связанных с политикой.</span><span class="sxs-lookup"><span data-stu-id="75ae5-164">Audio Conferencing voice routing policies are associated to one or more PSTN usages, which in turn, determine the possible routes that will be attempted to be used for the meeting dial-out calls of the organizers associated to the policy.</span></span>

<span data-ttu-id="75ae5-165">Политику маршрутизации голоса для аудиоконференции можно создать с помощью cmdlet "New- CsOnlineAudioConferencingRoutingPolicy".</span><span class="sxs-lookup"><span data-stu-id="75ae5-165">You can create an Audio Conferencing voice routing policy by using the “New- CsOnlineAudioConferencingRoutingPolicy” cmdlet.</span></span> <span data-ttu-id="75ae5-166">Например:</span><span class="sxs-lookup"><span data-stu-id="75ae5-166">For Example:</span></span>

```powershell
New-CsOnlineAudioConferencingRoutingPolicy "Policy 1" -OnlinePstnUsages "US and Canada"
```

<span data-ttu-id="75ae5-167">После того как политика будет назначена пользователю и когда для одного из собраний будет начаты звонок с помощью телефонного звонка, оценка маршрутов голосовой связи в ОКП, связанных с организатором с помощью политики маршрутинга голосовой связи пользователя.</span><span class="sxs-lookup"><span data-stu-id="75ae5-167">After the policy is assigned to a user, and when a meeting dial-out call is initiated from one of the user's meetings, the voice routes in the PSTN usages that are associated to the organizer through the user's voice routing policy will be evaluated.</span></span> <span data-ttu-id="75ae5-168">Если место назначения для звонка по телефону совпадает с агрегатом в одном из голосовых маршрутов, связанных с организатором, звонок будет перенаправлен на шлюз ННР, определенный в голосовом маршруте.</span><span class="sxs-lookup"><span data-stu-id="75ae5-168">If the meeting dial-out call destination matches a regex in one of the voice routes that are associated to the organizer, the meeting dial-out call will be routed to the PSTN gateway defined in the voice route.</span></span> <span data-ttu-id="75ae5-169">Если место назначения для телефонного звонка не соответствует ни одной из голосовых маршрутов, связанных с организатором, звонок будет перенаправлен корпорацией Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="75ae5-169">If the meeting dial-out call destination does not match any of the voice routes associated to the organizer, the meeting dial-out call will be routed by Microsoft.</span></span>

#### <a name="assign-a-policy-to-your-users"></a><span data-ttu-id="75ae5-170">Назначение политики пользователям</span><span class="sxs-lookup"><span data-stu-id="75ae5-170">Assign a policy to your users</span></span>

<span data-ttu-id="75ae5-171">После определения политик маршрутинга аудиоконференций вы можете назначать их пользователям.</span><span class="sxs-lookup"><span data-stu-id="75ae5-171">After the Audio Conferencing routing policies are defined, you can now assign them to users.</span></span> <span data-ttu-id="75ae5-172">После того как им будут назначены политики, вызовы телефонного звонка для собрания оцениваются на ее маршрут.</span><span class="sxs-lookup"><span data-stu-id="75ae5-172">After policies are assigned to them, the meeting dial-out calls will be evaluated against it to determine their routing path.</span></span> <span data-ttu-id="75ae5-173">Политики маршрутинга аудиоконференций всегда оцениваются на основе организатора собрания независимо от пользователя в собрании, который инициирует исходяющий звонок.</span><span class="sxs-lookup"><span data-stu-id="75ae5-173">Audio Conferencing routing policies are always evaluated based on the organizer of the meeting, independently from the user in the meeting that initiates a meeting dial-out call.</span></span>

<span data-ttu-id="75ae5-174">Политику маршрутизации голосовых аудиоконференции можно назначить пользователю с помощью cmdlet "Grant-CsOnlineAudioConferencingRoutingPolicy".</span><span class="sxs-lookup"><span data-stu-id="75ae5-174">You can assign an Audio Conferencing voice routing policy to a user by using the “Grant-CsOnlineAudioConferencingRoutingPolicy” cmdlet.</span></span> <span data-ttu-id="75ae5-175">Например:</span><span class="sxs-lookup"><span data-stu-id="75ae5-175">For example:</span></span>

```powershell
Grant-CsOnlineAudioConferencingRoutingPolicy -Identity "<User Identity>" -PolicyName "Policy 1”
```


### <a name="configure-routing-on-the-telephony-equipment-of-your-organization"></a><span data-ttu-id="75ae5-176">Настройка маршрутизации для телефонного оборудования организации</span><span class="sxs-lookup"><span data-stu-id="75ae5-176">Configure routing on the telephony equipment of your organization</span></span>

<span data-ttu-id="75ae5-177">На телефонном оборудовании вашей организации необходимо обеспечить маршрутизации звонков телефонного звонка, перенаправленных по прямой маршрутизации в пункт назначения в сети.</span><span class="sxs-lookup"><span data-stu-id="75ae5-177">On the telephony equipment of your organization, you need to ensure that the meeting dial-out calls routed through Direct Routing are routed to the intended on-network destination.</span></span>


### <a name="optional-configure-a-dial-plan"></a><span data-ttu-id="75ae5-178">(Необязательно) Настройка набора номера</span><span class="sxs-lookup"><span data-stu-id="75ae5-178">(Optional) Configure a dial plan</span></span>

<span data-ttu-id="75ae5-179">Телефонная плана — это набор правил нормализации, который преобразует номера телефонов конкретного пользователя в альтернативный формат (обычно E.164) для авторизации звонков и маршрутизации звонков.</span><span class="sxs-lookup"><span data-stu-id="75ae5-179">A dial plan is a set of normalization rules that translate dialed phone numbers by an individual user into an alternate format (typically E.164) for purposes of call authorization and call routing.</span></span>

<span data-ttu-id="75ae5-180">По умолчанию пользователи Teams могут звонить на номера ННР в формате E.164, то есть + \<country code\> \<number\> .</span><span class="sxs-lookup"><span data-stu-id="75ae5-180">By default, Teams users can dial-out to PSTN numbers in E.164 format, that is, +\<country code\>\<number\>.</span></span> <span data-ttu-id="75ae5-181">Однако можно использовать такие планы, чтобы разрешить пользователям набирать номера телефонов в других форматах, например в четырехзначных расширениях.</span><span class="sxs-lookup"><span data-stu-id="75ae5-181">However, dial plans can be used to allow users to dial phone numbers in other formats, for instance 4-digit extensions.</span></span>

<span data-ttu-id="75ae5-182">Если вы хотите включить телефонную сеть для телефонного набора с учетом расширения, вы можете настроить наборы для того, чтобы они совпадали с диапазонами телефонных номеров вашей организации.</span><span class="sxs-lookup"><span data-stu-id="75ae5-182">If you would like to enable extension-based dialing through On-network conferencing, you can set up dial plans to match the extension dialing pattern to the phone number ranges of the phone number of your organization.</span></span> <span data-ttu-id="75ae5-183">О том, как настроить наборные планы, см. в теме "Создание телефонных планов [и управление ими".](create-and-manage-dial-plans.md)</span><span class="sxs-lookup"><span data-stu-id="75ae5-183">To set up dial plans, see [Create and manage dial plans](create-and-manage-dial-plans.md).</span></span>


## <a name="known-issues-in-open-preview"></a><span data-ttu-id="75ae5-184">Известные проблемы в режиме предварительного просмотра Open Preview</span><span class="sxs-lookup"><span data-stu-id="75ae5-184">Known issues in Open Preview</span></span>

<span data-ttu-id="75ae5-185">Ниже представлен список известных проблем, которые в настоящее время присутствуют в выпуске Open Preview для интернет-связи.</span><span class="sxs-lookup"><span data-stu-id="75ae5-185">The following is a list of known issues that are currently present in the Open Preview release of On-network conferencing.</span></span> <span data-ttu-id="75ae5-186">Корпорация Майкрософт работает над решением этих проблем.</span><span class="sxs-lookup"><span data-stu-id="75ae5-186">Microsoft is working on addressing these issues.</span></span>

| <span data-ttu-id="75ae5-187">Ошибка</span><span class="sxs-lookup"><span data-stu-id="75ae5-187">Issue</span></span> | <span data-ttu-id="75ae5-188">Обходное решение</span><span class="sxs-lookup"><span data-stu-id="75ae5-188">Workaround</span></span> |
| :--- | :--- |
| <span data-ttu-id="75ae5-189">К собранию нельзя подключаться к звонкам с анонимными или скрытыми ИД звонив через сетевую связь.</span><span class="sxs-lookup"><span data-stu-id="75ae5-189">Dial-in calls with anonymous/hidden caller IDs that are routed through On-network conferencing cannot be connected to the meeting.</span></span> | <span data-ttu-id="75ae5-190">Если возможно, задайте в УАЦ или SBC конфигурацию, чтобы всегда отправлять ИД звонив при звонках, перенаправляемых через сетевуюконференцию.</span><span class="sxs-lookup"><span data-stu-id="75ae5-190">If possible, set a configuration in your PBX or SBC to always send a caller ID for calls routed via On-network conferencing.</span></span>|
| <span data-ttu-id="75ae5-191">В некоторых случаях приветствие, которое пользователи слышат при наборе номера в службу ("Добро пожаловать в службу аудиоконференций..."), убирается, и пользователи не слышат слова "Добро пожаловать".</span><span class="sxs-lookup"><span data-stu-id="75ae5-191">In some cases, the welcome message that is played to users when they dial in to the service (“Welcome to the Audio Conferencing service…”) is truncated and users do not hear the “Welcome” word.</span></span>| <span data-ttu-id="75ae5-192">В настоящее время обходного пути для этой проблемы нет.</span><span class="sxs-lookup"><span data-stu-id="75ae5-192">There are no workarounds for this issue at the moment.</span></span> |




## <a name="related-topics"></a><span data-ttu-id="75ae5-193">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="75ae5-193">Related topics</span></span>


