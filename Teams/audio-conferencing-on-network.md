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
description: Ниже описаны функции open Preview для аудиоконференций в сети.
ms.openlocfilehash: d6df81cc077c69fdeb4246d682797d2ebb26b875
ms.sourcegitcommit: 950387da2a2c094b7580bcf81ae5d8b6dfba0d6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2021
ms.locfileid: "51637841"
---
# <a name="open-preview-of-on-network-conferencing-for-audio-conferencing"></a><span data-ttu-id="4c780-103">Открытие предварительного просмотра для аудиоконференций по сети</span><span class="sxs-lookup"><span data-stu-id="4c780-103">Open Preview of On-network Conferencing for Audio Conferencing</span></span>

<span data-ttu-id="4c780-104">Открытая предварительная версия для интернет-связи доступна всем клиентам.</span><span class="sxs-lookup"><span data-stu-id="4c780-104">The Open Preview of On-network Conferencing is available to all customers.</span></span> <span data-ttu-id="4c780-105">С помощью этой функции организации могут отправлять входящие и исходящие звонки на телефонные номера Майкрософт по прямой маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="4c780-105">On-network Conferencing allows organizations to send inbound and outbound Audio Conferencing calls to Microsoft dial-in numbers through Direct Routing.</span></span> <span data-ttu-id="4c780-106">Эта возможность не предназначена для расширения поддержки аудиоконференций на номера сторонних телефонных телефонов.</span><span class="sxs-lookup"><span data-stu-id="4c780-106">This capability is not intended to extend the support of Audio Conferencing to third party dial-in numbers.</span></span> <span data-ttu-id="4c780-107">Аудиоконференция по сети не поддерживается, если она используется для направления входящие вызовы в службу аудиоконференции через телефонные номера сторонних пользователей или исходящие вызовы через мост аудиоконференции Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="4c780-107">On-network Conferencing is not supported if it is used to route inbound calls to the Audio Conferencing service through third party dial-in phone numbers or outbound calls to the PSTN from Microsoft Audio Conferencing Bridge.</span></span> 

<span data-ttu-id="4c780-108">В этой статье описаны необходимые условия и этапы настройки, необходимые для того, чтобы включить в организации интернет-конференцию.</span><span class="sxs-lookup"><span data-stu-id="4c780-108">This article describes the prerequisites and configuration steps required to enable On-network Conferencing for your organization.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4c780-109">С телефонным оборудованием в Индии не должно быть развернуто сетевое оборудование.</span><span class="sxs-lookup"><span data-stu-id="4c780-109">On-network Conferencing must NOT be deployed with any telephony equipment in India.</span></span>
  
## <a name="prerequisites"></a><span data-ttu-id="4c780-110">Необходимые компоненты</span><span class="sxs-lookup"><span data-stu-id="4c780-110">Prerequisites</span></span>

<span data-ttu-id="4c780-111">Прежде чем настраивать интернет-конференцию, убедитесь, что ваша организация соответствует следующим требованиям:</span><span class="sxs-lookup"><span data-stu-id="4c780-111">Before configuring On-network Conferencing, make sure your organization meets the following prerequisites:</span></span> 

- <span data-ttu-id="4c780-112">Убедитесь, что все пользователи в организации, у которых включена или будет включена аудиоконференция, используют Teams для всех собраний.</span><span class="sxs-lookup"><span data-stu-id="4c780-112">Ensure that all users in your organization who are enabled, or will be enabled, for Audio Conferencing are using Teams for all Meetings.</span></span> <span data-ttu-id="4c780-113">Маршрутизацию входящие и исходящие звонки аудиоконференции через интернет-конференцию поддерживаются только для Teams собраний.</span><span class="sxs-lookup"><span data-stu-id="4c780-113">The routing of inbound and outbound Audio Conferencing calls through On-network Conferencing is only supported for Teams meetings.</span></span>

- <span data-ttu-id="4c780-114">Назначьте лицензии на аудиоконференцию всем пользователям, которые будут использовать эту функцию.</span><span class="sxs-lookup"><span data-stu-id="4c780-114">Assign Audio Conferencing licenses to all users who will be using On-network Conferencing.</span></span>

- <span data-ttu-id="4c780-115">Настройка службы аудиоконференций.</span><span class="sxs-lookup"><span data-stu-id="4c780-115">Set up the Audio Conferencing service.</span></span> <span data-ttu-id="4c780-116">Дополнительные сведения см. в [этой](set-up-audio-conferencing-in-teams.md)Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="4c780-116">For additional information, see [Set up Audio Conferencing for Microsoft Teams](set-up-audio-conferencing-in-teams.md).</span></span>

- <span data-ttu-id="4c780-117">Настройка контроллера границы сеанса (SBC) для прямой маршрутии.</span><span class="sxs-lookup"><span data-stu-id="4c780-117">Set up your Session Border Controller (SBC) for Direct Routing.</span></span> <span data-ttu-id="4c780-118">Дополнительные сведения [см.](direct-routing-plan.md) в настройках прямой маршрутной маршрутии и Планировании [прямой маршрутии.](direct-routing-configure.md)</span><span class="sxs-lookup"><span data-stu-id="4c780-118">For additional information, see [Plan Direct Routing](direct-routing-plan.md) and [Configure Direct Routing](direct-routing-configure.md).</span></span> 

  <span data-ttu-id="4c780-119">Если прямая маршрутизация настраивается только для аудиоконференций, необходимо выполнить только "Шаг 1. Подключение SBC" для аудиоконференции по сети.</span><span class="sxs-lookup"><span data-stu-id="4c780-119">If you are setting up Direct Routing only for the purposes of Audio Conferencing, then you need only complete “Step 1: Connect your SBC” for On-network Conferencing.</span></span>
  
## <a name="enable-the-routing-of-dial-in-calls-to-microsoft-audio-conferencing-through-direct-routing"></a><span data-ttu-id="4c780-120">Включить маршрутику звонков с телефонным доступом на аудиоконференцию Майкрософт через прямую маршрутику</span><span class="sxs-lookup"><span data-stu-id="4c780-120">Enable the routing of dial-in calls to Microsoft Audio Conferencing through Direct Routing</span></span> 

<span data-ttu-id="4c780-121">Чтобы перенаправить звонки с телефонным доступом, сделанные локально пользователями, в службу аудиоконференций с помощью прямой маршрутики, необходимо настроить соответствующие правила маршрутики для служб SBCs и private Branch Exchange (PBX).</span><span class="sxs-lookup"><span data-stu-id="4c780-121">To route dial-in calls made by your on-premises users to the Audio Conferencing service through Direct Routing, you need to configure appropriate routing rules for your SBCs and Private Branch Exchange(s) (PBXs).</span></span>

<span data-ttu-id="4c780-122">Необходимо настроить телефонное оборудование сайтов для маршрутизации звонков на любой номер моста конференц-связи вашей организации с помощью линии прямой маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="4c780-122">You need to configure the telephony equipment of your sites to route calls to any service number of the conference bridge of your organization through a Direct Routing trunk.</span></span>

<span data-ttu-id="4c780-123">Номера служб можно найти в центре администрирования Teams в статье Мосты для собраний **>** или с помощью Skype для бизнеса Online PowerShell Get-CsOnlineDialInConferencingBridge.</span><span class="sxs-lookup"><span data-stu-id="4c780-123">You can find the service numbers in Teams admin center under **Meetings -> Conferencing Bridges** or by using the Skype for Business Online PowerShell cmdlet Get-CsOnlineDialInConferencingBridge.</span></span> <span data-ttu-id="4c780-124">Дополнительные сведения см. в списке номеров аудиоконференций в [Microsoft Teams.](see-a-list-of-audio-conferencing-numbers-in-teams.md)</span><span class="sxs-lookup"><span data-stu-id="4c780-124">For additional information, see a list of [Audio Conferencing numbers in Microsoft Teams](see-a-list-of-audio-conferencing-numbers-in-teams.md).</span></span>

> [!NOTE]
> <span data-ttu-id="4c780-125">Эта функция недоступна пользователям с лицензией на аудиоконференцию с поминутной оплатой.</span><span class="sxs-lookup"><span data-stu-id="4c780-125">This feature is not available to users with the pay-per-minute Audio Conferencing license.</span></span>

## <a name="enable-the-routing-of-teams-meeting-dial-out-calls-through-direct-routing"></a><span data-ttu-id="4c780-126">Включить маршрутику звонков Teams с помощью прямой маршрутии</span><span class="sxs-lookup"><span data-stu-id="4c780-126">Enable the routing of Teams meeting dial-out calls through Direct Routing</span></span>

<span data-ttu-id="4c780-127">Teams вызовы телефонного звонка инициировали из собрания в организации на номера ДНР, включая звонки по телефону и вызовы для привлечения новых участников к собранию.</span><span class="sxs-lookup"><span data-stu-id="4c780-127">Teams meeting dial-out calls are initiated from within a meeting in your organization to PSTN numbers, including call-me-at calls and calls to bring new participants to a meeting.</span></span> 

<span data-ttu-id="4c780-128">Чтобы включить Teams маршрутизации собраний с помощью прямой маршрутизации пользователям в сети, необходимо создать и назначить политику маршрутизации аудиоконференции "OnlineAudioConferencingRoutingPolicy".</span><span class="sxs-lookup"><span data-stu-id="4c780-128">To enable Teams meeting dial-out routing through Direct Routing to on-network users, you need to create and assign an Audio Conferencing routing policy called “OnlineAudioConferencingRoutingPolicy”.</span></span> 

<span data-ttu-id="4c780-129">Политика OnlineAudioConferencingRoutingPolicy эквивалентна политике CsOnlineVoiceRoutingPolicy для звонков 1:1 по ОКП по прямой маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="4c780-129">The OnlineAudioConferencingRoutingPolicy policy is equivalent to the CsOnlineVoiceRoutingPolicy for 1:1 PSTN calls via Direct Routing.</span></span> <span data-ttu-id="4c780-130">Управлять политикой OnlineAudioConferencingRoutingPolicy можно с помощью следующих cmdlets:</span><span class="sxs-lookup"><span data-stu-id="4c780-130">The OnlineAudioConferencingRoutingPolicy policy can be managed by using the following cmdlets:</span></span>

-   <span data-ttu-id="4c780-131">New-CsOnlineAudioConferencingRoutingPolicy</span><span class="sxs-lookup"><span data-stu-id="4c780-131">New-CsOnlineAudioConferencingRoutingPolicy</span></span>
- <span data-ttu-id="4c780-132">Set-CsOnlineAudioConferencingRoutingPolicy</span><span class="sxs-lookup"><span data-stu-id="4c780-132">Set-CsOnlineAudioConferencingRoutingPolicy</span></span>
- <span data-ttu-id="4c780-133">Get-CsOnlineAudioConferencingRoutingPolicy</span><span class="sxs-lookup"><span data-stu-id="4c780-133">Get-CsOnlineAudioConferencingRoutingPolicy</span></span>
- <span data-ttu-id="4c780-134">Grant-CsOnlineAudioConferencingRoutingPolicy</span><span class="sxs-lookup"><span data-stu-id="4c780-134">Grant-CsOnlineAudioConferencingRoutingPolicy</span></span>
- <span data-ttu-id="4c780-135">Remove-CsOnlineAudioConferencingRoutingPolicy</span><span class="sxs-lookup"><span data-stu-id="4c780-135">Remove-CsOnlineAudioConferencingRoutingPolicy</span></span>

<span data-ttu-id="4c780-136">Дополнительные сведения о маршрутике для прямой маршрутии см. в этой [ссылке.](direct-routing-voice-routing.md)</span><span class="sxs-lookup"><span data-stu-id="4c780-136">For more information about routing for Direct Routing, see [Configure voice routing for Direct Routing](direct-routing-voice-routing.md).</span></span>


<span data-ttu-id="4c780-137">Чтобы включить маршрутику звонков с телефонным вызовом через Прямую маршрутику, необходимо:</span><span class="sxs-lookup"><span data-stu-id="4c780-137">To enable the routing of meeting dial-out calls through Direct Routing, you need to:</span></span> 

- <span data-ttu-id="4c780-138">Настройка политик маршрутизации аудиоконференций</span><span class="sxs-lookup"><span data-stu-id="4c780-138">Configure Audio Conferencing routing policies</span></span>
- <span data-ttu-id="4c780-139">Настройка маршрутизации на телефонном оборудовании организации</span><span class="sxs-lookup"><span data-stu-id="4c780-139">Configure the routing on the telephony equipment of your organization</span></span>
- <span data-ttu-id="4c780-140">(Необязательно) Настройка набора номера</span><span class="sxs-lookup"><span data-stu-id="4c780-140">(Optional) Configure a dial plan</span></span>

<span data-ttu-id="4c780-141">Исходят звонки из Teams из конференц-зала исходят из номера службы по умолчанию на мосте конференции.</span><span class="sxs-lookup"><span data-stu-id="4c780-141">Dial-out calls from Teams meetings are coming from the default service number on the conference bridge.</span></span> <span data-ttu-id="4c780-142">Дополнительные сведения о номере службы по умолчанию для моста аудиоконференций см. в этой [теме.](change-the-phone-numbers-on-your-audio-conferencing-bridge.md)</span><span class="sxs-lookup"><span data-stu-id="4c780-142">For additional information on the default service number of your Audio Conferencing bridge, see [Change the phone numbers on your Audio Conferencing bridge](change-the-phone-numbers-on-your-audio-conferencing-bridge.md).</span></span>

### <a name="configure-audio-conferencing-routing-policies"></a><span data-ttu-id="4c780-143">Настройка политик маршрутизации аудиоконференций</span><span class="sxs-lookup"><span data-stu-id="4c780-143">Configure Audio Conferencing routing policies</span></span>

<span data-ttu-id="4c780-144">Политика маршрутизации аудиоконференции OnlineAudioConferencingRoutingPolicy определяет, какие звонки на собрания перенаправляются на линии прямой маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="4c780-144">The Audio Conferencing routing policy OnlineAudioConferencingRoutingPolicy determines which meeting dial-out calls are routed to Direct Routing trunks.</span></span> <span data-ttu-id="4c780-145">Если вы знакомы с политикой CsOnlineVoiceRoutingPolicy, она работает почти так же.</span><span class="sxs-lookup"><span data-stu-id="4c780-145">If you are familiar with the CsOnlineVoiceRoutingPolicy policy, this policy works in a very similar way.</span></span>

<span data-ttu-id="4c780-146">Чтобы настроить политики маршрутинга аудиоконференций, необходимо сделать следующее:</span><span class="sxs-lookup"><span data-stu-id="4c780-146">The following steps are needed to set up Audio Conferencing routing policies:</span></span>
1.  <span data-ttu-id="4c780-147">Создание использования ОКП</span><span class="sxs-lookup"><span data-stu-id="4c780-147">Create PSTN usages</span></span>
2.  <span data-ttu-id="4c780-148">Настройка голосовых маршрутов</span><span class="sxs-lookup"><span data-stu-id="4c780-148">Configure voice routes</span></span>
3.  <span data-ttu-id="4c780-149">Создание политик голосовой маршрутизации аудиоконференций</span><span class="sxs-lookup"><span data-stu-id="4c780-149">Create Audio Conferencing voice routing policies</span></span>
4.  <span data-ttu-id="4c780-150">Назначение политики пользователям</span><span class="sxs-lookup"><span data-stu-id="4c780-150">Assign a policy to your users</span></span>


#### <a name="create-pstn-usages"></a><span data-ttu-id="4c780-151">Создание использования ОКП</span><span class="sxs-lookup"><span data-stu-id="4c780-151">Create PSTN usages</span></span>

<span data-ttu-id="4c780-152">Использование услуг STN — это наборы голосовых маршрутов.</span><span class="sxs-lookup"><span data-stu-id="4c780-152">PSTN usages are collections of voice routes.</span></span> <span data-ttu-id="4c780-153">При инициирующем звонке из собрания организатора голосовые маршруты используются для определения маршрутизов звонка на основе использования услуг STN, связанных с пользователем с помощью политики маршрутизов голосовой связи пользователя.</span><span class="sxs-lookup"><span data-stu-id="4c780-153">When a dial-out call is initiated from the meeting of a given organizer, voice routes will be used to determine the routing path of the call based on the PSTN usages that are associated to the user via the user’s voice routing policy.</span></span>

<span data-ttu-id="4c780-154">Вы можете создать использование ПСОП с помощью "Set-CsOnlinePstnUsage".</span><span class="sxs-lookup"><span data-stu-id="4c780-154">You can create a PSTN usage by using the “Set-CsOnlinePstnUsage” cmdlet.</span></span> <span data-ttu-id="4c780-155">Например:</span><span class="sxs-lookup"><span data-stu-id="4c780-155">For Example:</span></span>

```powershell
Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="US and Canada"}
```

#### <a name="configure-voice-routes"></a><span data-ttu-id="4c780-156">Настройка голосовых маршрутов</span><span class="sxs-lookup"><span data-stu-id="4c780-156">Configure voice routes</span></span>

<span data-ttu-id="4c780-157">Голосовые маршруты определяют шлюз ЗВОНКОВ, который должен использоваться для перенастройки звонка на основе номера телефона, набра номера Teams собрания.</span><span class="sxs-lookup"><span data-stu-id="4c780-157">Voice routes determine the PSTN gateway that should be used to route a call based on the phone number that is dialed from a Teams meeting.</span></span> <span data-ttu-id="4c780-158">Голосовые маршруты определяют шлюз ЗВОНКОВ, который должен использоваться для перенастройки звонка, путем совпадения номера телефона, набраного из собрания Teams с шаблоном регексации.</span><span class="sxs-lookup"><span data-stu-id="4c780-158">Voice routes determine the PSTN gateway that should be used to route a given call by matching the phone number dialed from a Teams meeting with a regex pattern.</span></span> <span data-ttu-id="4c780-159">При создании голосового маршрута он должен быть связан с одним или нескольком использованием ОКП.</span><span class="sxs-lookup"><span data-stu-id="4c780-159">When creating a voice route, the route must be associated to one or more PSTN usages.</span></span>

<span data-ttu-id="4c780-160">Вы можете создать голосовой маршрут и определить regex и шлюзы, которые будут связаны с голосовым маршрутом, с помощью "New-CsOnlineVoiceRoute".</span><span class="sxs-lookup"><span data-stu-id="4c780-160">You can create a voice route and define the regex and gateways to be associated with the voice route by using the “New-CsOnlineVoiceRoute” cmdlet.</span></span> <span data-ttu-id="4c780-161">Например:</span><span class="sxs-lookup"><span data-stu-id="4c780-161">For Example:</span></span>

```powershell
New-CsOnlineVoiceRoute -Identity "Redmond 1" -NumberPattern "^\+1(425|206)(\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
```

#### <a name="create-audio-conferencing-voice-routing-policies"></a><span data-ttu-id="4c780-162">Создание политик голосовой маршрутизации аудиоконференций</span><span class="sxs-lookup"><span data-stu-id="4c780-162">Create Audio Conferencing voice routing policies</span></span>

<span data-ttu-id="4c780-163">Политики маршрутизации голосовой связи для аудиоконференций определяют возможные маршруты, которые могут использоваться для перенастройки звонка, исходя из собраний организатора, на основе целевого номера телефона в телефонном звонке.</span><span class="sxs-lookup"><span data-stu-id="4c780-163">Audio Conferencing voice routing policies determine the possible routes that can be used to route a call originating from the meetings of an organizer based on the target phone number of the meeting dial-out call.</span></span> <span data-ttu-id="4c780-164">Политики маршрутизации голосовой связи аудиоконференции связаны с одним или несколькою вариантами использования услуг ЗВОНКОВ по ННР, которые, в свою очередь, определяют возможные маршруты, которые будут использоваться для звонков с телефонным вызовом организаторов, связанных с политикой.</span><span class="sxs-lookup"><span data-stu-id="4c780-164">Audio Conferencing voice routing policies are associated to one or more PSTN usages, which in turn, determine the possible routes that will be attempted to be used for the meeting dial-out calls of the organizers associated to the policy.</span></span>

<span data-ttu-id="4c780-165">Политику маршрутизации голосовой маршрутизации аудиоконференции можно создать с помощью "New-CsOnlineAudioConferencingRoutingPolicy".</span><span class="sxs-lookup"><span data-stu-id="4c780-165">You can create an Audio Conferencing voice routing policy by using the “New- CsOnlineAudioConferencingRoutingPolicy” cmdlet.</span></span> <span data-ttu-id="4c780-166">Например:</span><span class="sxs-lookup"><span data-stu-id="4c780-166">For Example:</span></span>

```powershell
New-CsOnlineAudioConferencingRoutingPolicy "Policy 1" -OnlinePstnUsages "US and Canada"
```

<span data-ttu-id="4c780-167">После того как политика будет назначена пользователю и когда на одном из собраний будет инициировался звонок с телефонного звонка, будут оцениваться голосовые маршруты в рамках использования услуг STN, связанных с организатором с помощью политики маршрутизов голосовой связи пользователя.</span><span class="sxs-lookup"><span data-stu-id="4c780-167">After the policy is assigned to a user, and when a meeting dial-out call is initiated from one of the user's meetings, the voice routes in the PSTN usages that are associated to the organizer through the user's voice routing policy will be evaluated.</span></span> <span data-ttu-id="4c780-168">Если место назначения для телефонного звонка для собрания совпадает срегесом в одном из голосовых маршрутов, связанных с организатором, звонок будет перенаправлен на шлюз STN, определенный в голосовом маршруте.</span><span class="sxs-lookup"><span data-stu-id="4c780-168">If the meeting dial-out call destination matches a regex in one of the voice routes that are associated to the organizer, the meeting dial-out call will be routed to the PSTN gateway defined in the voice route.</span></span> <span data-ttu-id="4c780-169">Если место назначения для телефонного звонка не соответствует ни одной из голосовых маршрутов, связанных с организатором, звонок будет перенаправлен корпорацией Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="4c780-169">If the meeting dial-out call destination does not match any of the voice routes associated to the organizer, the meeting dial-out call will be routed by Microsoft.</span></span>

#### <a name="assign-a-policy-to-your-users"></a><span data-ttu-id="4c780-170">Назначение политики пользователям</span><span class="sxs-lookup"><span data-stu-id="4c780-170">Assign a policy to your users</span></span>

<span data-ttu-id="4c780-171">После определения политик маршрутинга аудиоконференций вы можете назначить их пользователям.</span><span class="sxs-lookup"><span data-stu-id="4c780-171">After the Audio Conferencing routing policies are defined, you can now assign them to users.</span></span> <span data-ttu-id="4c780-172">После того как им будут назначены политики, звонки на собрание будут оцениваться в зависимости от того, как они определяют маршрутизовую маршрутику.</span><span class="sxs-lookup"><span data-stu-id="4c780-172">After policies are assigned to them, the meeting dial-out calls will be evaluated against it to determine their routing path.</span></span> <span data-ttu-id="4c780-173">Политики маршрутизации аудиоконференций всегда оцениваются на основе организатора собрания независимо от пользователя в собрании, который инициирует звонок по телефону.</span><span class="sxs-lookup"><span data-stu-id="4c780-173">Audio Conferencing routing policies are always evaluated based on the organizer of the meeting, independently from the user in the meeting that initiates a meeting dial-out call.</span></span>

<span data-ttu-id="4c780-174">Политику маршрутизации голосовой сети аудиоконференции можно назначить пользователю с помощью "Grant-CsOnlineAudioConferencingRoutingPolicy".</span><span class="sxs-lookup"><span data-stu-id="4c780-174">You can assign an Audio Conferencing voice routing policy to a user by using the “Grant-CsOnlineAudioConferencingRoutingPolicy” cmdlet.</span></span> <span data-ttu-id="4c780-175">Например:</span><span class="sxs-lookup"><span data-stu-id="4c780-175">For example:</span></span>

```powershell
Grant-CsOnlineAudioConferencingRoutingPolicy -Identity "<User Identity>" -PolicyName "Policy 1”
```


### <a name="configure-routing-on-the-telephony-equipment-of-your-organization"></a><span data-ttu-id="4c780-176">Настройка маршрутизации на телефонном оборудовании организации</span><span class="sxs-lookup"><span data-stu-id="4c780-176">Configure routing on the telephony equipment of your organization</span></span>

<span data-ttu-id="4c780-177">На телефонном оборудовании организации необходимо обеспечить маршрутизовы телефонного звонка, перенаправленные по прямой маршрутизации, в предполагаемый сетевой маршрут.</span><span class="sxs-lookup"><span data-stu-id="4c780-177">On the telephony equipment of your organization, you need to ensure that the meeting dial-out calls routed through Direct Routing are routed to the intended on-network destination.</span></span>


### <a name="optional-configure-a-dial-plan"></a><span data-ttu-id="4c780-178">(Необязательно) Настройка набора номера</span><span class="sxs-lookup"><span data-stu-id="4c780-178">(Optional) Configure a dial plan</span></span>

<span data-ttu-id="4c780-179">Телефонная плана — это набор правил нормализации, которые переводят номера телефонов отдельных пользователей в альтернативный формат (обычно E.164) для авторизации звонков и маршрутизации звонков.</span><span class="sxs-lookup"><span data-stu-id="4c780-179">A dial plan is a set of normalization rules that translate dialed phone numbers by an individual user into an alternate format (typically E.164) for purposes of call authorization and call routing.</span></span>

<span data-ttu-id="4c780-180">По умолчанию Teams к номерам ДНР в формате E.164, т. е. + \<country code\> \<number\> .</span><span class="sxs-lookup"><span data-stu-id="4c780-180">By default, Teams users can dial-out to PSTN numbers in E.164 format, that is, +\<country code\>\<number\>.</span></span> <span data-ttu-id="4c780-181">Однако можно использовать планы набора, чтобы разрешить пользователям набирать номера телефонов в других форматах, например в четырехзначных расширениях.</span><span class="sxs-lookup"><span data-stu-id="4c780-181">However, dial plans can be used to allow users to dial phone numbers in other formats, for instance 4-digit extensions.</span></span>

<span data-ttu-id="4c780-182">Если вы хотите включить телефонную сеть с телефонным набором с учетом расширения, вы можете настроить наборные планы так, чтобы он совпадал с диапазонами телефонных номеров вашей организации.</span><span class="sxs-lookup"><span data-stu-id="4c780-182">If you would like to enable extension-based dialing through On-network conferencing, you can set up dial plans to match the extension dialing pattern to the phone number ranges of the phone number of your organization.</span></span> <span data-ttu-id="4c780-183">Чтобы настроить наборные планы, см. создание планов набора номера [и управление ими.](create-and-manage-dial-plans.md)</span><span class="sxs-lookup"><span data-stu-id="4c780-183">To set up dial plans, see [Create and manage dial plans](create-and-manage-dial-plans.md).</span></span>


## <a name="known-issues-in-open-preview"></a><span data-ttu-id="4c780-184">Известные проблемы в open Preview</span><span class="sxs-lookup"><span data-stu-id="4c780-184">Known issues in Open Preview</span></span>

<span data-ttu-id="4c780-185">Ниже представлен список известных проблем, которые в настоящее время присутствуют в выпуске Open Preview для интернет-услуг.</span><span class="sxs-lookup"><span data-stu-id="4c780-185">The following is a list of known issues that are currently present in the Open Preview release of On-network conferencing.</span></span> <span data-ttu-id="4c780-186">Корпорация Майкрософт работает над решением этих проблем.</span><span class="sxs-lookup"><span data-stu-id="4c780-186">Microsoft is working on addressing these issues.</span></span>

| <span data-ttu-id="4c780-187">Ошибка</span><span class="sxs-lookup"><span data-stu-id="4c780-187">Issue</span></span> | <span data-ttu-id="4c780-188">Решение</span><span class="sxs-lookup"><span data-stu-id="4c780-188">Workaround</span></span> |
| :--- | :--- |
| <span data-ttu-id="4c780-189">К собранию нельзя подключаться к звонкам с телефонным подключением с анонимными и скрытыми ИД звонив, перенана маршрутизованным через интернет-связь.</span><span class="sxs-lookup"><span data-stu-id="4c780-189">Dial-in calls with anonymous/hidden caller IDs that are routed through On-network conferencing cannot be connected to the meeting.</span></span> | <span data-ttu-id="4c780-190">Если возможно, задайте в своей УАПС или SBC конфигурацию, чтобы всегда отправлять ИД звонив по звонкам, перенаправляемым с помощью онлайн-конференции.</span><span class="sxs-lookup"><span data-stu-id="4c780-190">If possible, set a configuration in your PBX or SBC to always send a caller ID for calls routed via On-network conferencing.</span></span>|
| <span data-ttu-id="4c780-191">В некоторых случаях приветствие, которое будет разослано пользователям при наборе номера в службу ("Добро пожаловать в службу аудиоконференций..."), усоединяется, и пользователи не слышат слово "Добро пожаловать".</span><span class="sxs-lookup"><span data-stu-id="4c780-191">In some cases, the welcome message that is played to users when they dial in to the service (“Welcome to the Audio Conferencing service…”) is truncated and users do not hear the “Welcome” word.</span></span>| <span data-ttu-id="4c780-192">В настоящее время обходных пути решения этой проблемы нет.</span><span class="sxs-lookup"><span data-stu-id="4c780-192">There are no workarounds for this issue at the moment.</span></span> |




## <a name="related-topics"></a><span data-ttu-id="4c780-193">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="4c780-193">Related topics</span></span>


