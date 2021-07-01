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
description: Ниже описана сеть для аудиоконференций.
ms.openlocfilehash: b7851bd2457debe8ee0de3144e24a15edb521222
ms.sourcegitcommit: b39bd1de0219a9e3a3b0c97fc485c9578ddb643c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2021
ms.locfileid: "53230566"
---
# <a name="on-network-conferencing-for-audio-conferencing"></a><span data-ttu-id="e913b-103">Аудиоконференция по сети</span><span class="sxs-lookup"><span data-stu-id="e913b-103">On-network Conferencing for Audio Conferencing</span></span>

<span data-ttu-id="e913b-104">С помощью этой функции организации могут отправлять входящие и исходящие звонки на телефонные номера Майкрософт по прямой маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="e913b-104">On-network Conferencing allows organizations to send inbound and outbound Audio Conferencing calls to Microsoft dial-in numbers through Direct Routing.</span></span> <span data-ttu-id="e913b-105">Эта возможность не предназначена для расширения поддержки аудиоконференций на номера сторонних телефонных телефонов.</span><span class="sxs-lookup"><span data-stu-id="e913b-105">This capability is not intended to extend the support of Audio Conferencing to third party dial-in numbers.</span></span> <span data-ttu-id="e913b-106">Аудиоконференция по сети не поддерживается, если она используется для направления входящие вызовы в службу аудиоконференции через телефонные номера сторонних пользователей или исходящие вызовы через мост аудиоконференции Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="e913b-106">On-network Conferencing is not supported if it is used to route inbound calls to the Audio Conferencing service through third party dial-in phone numbers or outbound calls to the PSTN from Microsoft Audio Conferencing Bridge.</span></span> 

<span data-ttu-id="e913b-107">В этой статье описаны необходимые условия и этапы настройки, необходимые для того, чтобы включить в организации интернет-конференцию.</span><span class="sxs-lookup"><span data-stu-id="e913b-107">This article describes the prerequisites and configuration steps required to enable On-network Conferencing for your organization.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e913b-108">С телефонным оборудованием в Индии не должно быть развернуто сетевое оборудование.</span><span class="sxs-lookup"><span data-stu-id="e913b-108">On-network Conferencing must NOT be deployed with any telephony equipment in India.</span></span>
  
## <a name="prerequisites"></a><span data-ttu-id="e913b-109">Необходимые компоненты</span><span class="sxs-lookup"><span data-stu-id="e913b-109">Prerequisites</span></span>

<span data-ttu-id="e913b-110">Прежде чем настраивать интернет-конференцию, убедитесь, что ваша организация соответствует следующим требованиям:</span><span class="sxs-lookup"><span data-stu-id="e913b-110">Before configuring On-network Conferencing, make sure your organization meets the following prerequisites:</span></span> 

- <span data-ttu-id="e913b-111">Убедитесь, что все пользователи в организации, у которых включена или будет включена аудиоконференция, используют Teams для всех собраний.</span><span class="sxs-lookup"><span data-stu-id="e913b-111">Ensure that all users in your organization who are enabled, or will be enabled, for Audio Conferencing are using Teams for all Meetings.</span></span> <span data-ttu-id="e913b-112">Маршрутизацию входящие и исходящие звонки аудиоконференции через интернет-конференцию поддерживается только для Teams собраний.</span><span class="sxs-lookup"><span data-stu-id="e913b-112">The routing of inbound and outbound Audio Conferencing calls through On-network Conferencing is only supported for Teams meetings.</span></span>

- <span data-ttu-id="e913b-113">Назначьте лицензии на аудиоконференцию всем пользователям, которые будут использовать аудиоконференцию по сети.</span><span class="sxs-lookup"><span data-stu-id="e913b-113">Assign Audio Conferencing licenses to all users who will be using On-network Conferencing.</span></span>

- <span data-ttu-id="e913b-114">Настройка службы аудиоконференций.</span><span class="sxs-lookup"><span data-stu-id="e913b-114">Set up the Audio Conferencing service.</span></span> <span data-ttu-id="e913b-115">Дополнительные сведения см. в [этой](set-up-audio-conferencing-in-teams.md)Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="e913b-115">For additional information, see [Set up Audio Conferencing for Microsoft Teams](set-up-audio-conferencing-in-teams.md).</span></span>

- <span data-ttu-id="e913b-116">Настройка контроллера границы сеанса (SBC) для прямой маршрутии.</span><span class="sxs-lookup"><span data-stu-id="e913b-116">Set up your Session Border Controller (SBC) for Direct Routing.</span></span> <span data-ttu-id="e913b-117">Дополнительные сведения [см.](direct-routing-plan.md) в настройках прямой маршрутной маршрутии и Планировании [прямой маршрутии.](direct-routing-configure.md)</span><span class="sxs-lookup"><span data-stu-id="e913b-117">For additional information, see [Plan Direct Routing](direct-routing-plan.md) and [Configure Direct Routing](direct-routing-configure.md).</span></span> 

  <span data-ttu-id="e913b-118">Если прямая маршрутизация настраивается только для аудиоконференций, необходимо выполнить только "Шаг 1. Подключение SBC" для аудиоконференции по сети.</span><span class="sxs-lookup"><span data-stu-id="e913b-118">If you are setting up Direct Routing only for the purposes of Audio Conferencing, then you need only complete “Step 1: Connect your SBC” for On-network Conferencing.</span></span>
  
## <a name="enable-the-routing-of-dial-in-calls-to-microsoft-audio-conferencing-through-direct-routing"></a><span data-ttu-id="e913b-119">Включить маршрутику звонков с телефонным доступом на аудиоконференцию Майкрософт с помощью прямой маршрутизации</span><span class="sxs-lookup"><span data-stu-id="e913b-119">Enable the routing of dial-in calls to Microsoft Audio Conferencing through Direct Routing</span></span> 

<span data-ttu-id="e913b-120">Чтобы перенаправить звонки с телефонным доступом, сделанные локально пользователями, в службу аудиоконференций с помощью прямой маршрутики, необходимо настроить соответствующие правила маршрутики для служб SBCs и private Branch Exchange (PBX).</span><span class="sxs-lookup"><span data-stu-id="e913b-120">To route dial-in calls made by your on-premises users to the Audio Conferencing service through Direct Routing, you need to configure appropriate routing rules for your SBCs and Private Branch Exchange(s) (PBXs).</span></span>

<span data-ttu-id="e913b-121">Необходимо настроить телефонное оборудование сайтов для маршрутизации звонков на любой номер моста конференц-связи вашей организации с помощью линии прямой маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="e913b-121">You need to configure the telephony equipment of your sites to route calls to any service number of the conference bridge of your organization through a Direct Routing trunk.</span></span>

<span data-ttu-id="e913b-122">Номера служб можно найти в центре администрирования Teams в статье Мосты для собраний **>** или с помощью Skype для бизнеса Online PowerShell Get-CsOnlineDialInConferencingBridge.</span><span class="sxs-lookup"><span data-stu-id="e913b-122">You can find the service numbers in Teams admin center under **Meetings -> Conferencing Bridges** or by using the Skype for Business Online PowerShell cmdlet Get-CsOnlineDialInConferencingBridge.</span></span> <span data-ttu-id="e913b-123">Дополнительные сведения см. в списке номеров аудиоконференций в [Microsoft Teams.](see-a-list-of-audio-conferencing-numbers-in-teams.md)</span><span class="sxs-lookup"><span data-stu-id="e913b-123">For additional information, see a list of [Audio Conferencing numbers in Microsoft Teams](see-a-list-of-audio-conferencing-numbers-in-teams.md).</span></span>

> [!NOTE]
> <span data-ttu-id="e913b-124">Эта функция недоступна пользователям с лицензией на аудиоконференцию с поминутной оплатой.</span><span class="sxs-lookup"><span data-stu-id="e913b-124">This feature is not available to users with the pay-per-minute Audio Conferencing license.</span></span>

## <a name="enable-the-routing-of-teams-meeting-dial-out-calls-through-direct-routing"></a><span data-ttu-id="e913b-125">Включить маршрутику звонков Teams с помощью прямой маршрутии</span><span class="sxs-lookup"><span data-stu-id="e913b-125">Enable the routing of Teams meeting dial-out calls through Direct Routing</span></span>

<span data-ttu-id="e913b-126">Teams вызовы телефонного звонка инициировали из собрания в организации на номера ЗВОНКОВ по ПСЗ, включая звонки по телефону и вызовы для привлечения новых участников к собранию.</span><span class="sxs-lookup"><span data-stu-id="e913b-126">Teams meeting dial-out calls are initiated from within a meeting in your organization to PSTN numbers, including call-me-at calls and calls to bring new participants to a meeting.</span></span> 

<span data-ttu-id="e913b-127">Чтобы включить Teams маршрутизации собраний с помощью прямой маршрутизации пользователям в сети, необходимо создать и назначить политику маршрутизации аудиоконференции "OnlineAudioConferencingRoutingPolicy".</span><span class="sxs-lookup"><span data-stu-id="e913b-127">To enable Teams meeting dial-out routing through Direct Routing to on-network users, you need to create and assign an Audio Conferencing routing policy called “OnlineAudioConferencingRoutingPolicy”.</span></span> 

<span data-ttu-id="e913b-128">Политика OnlineAudioConferencingRoutingPolicy эквивалентна политике CsOnlineVoiceRoutingPolicy для звонков 1:1 по ОКП по прямой маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="e913b-128">The OnlineAudioConferencingRoutingPolicy policy is equivalent to the CsOnlineVoiceRoutingPolicy for 1:1 PSTN calls via Direct Routing.</span></span> <span data-ttu-id="e913b-129">Управлять политикой OnlineAudioConferencingRoutingPolicy можно с помощью следующих cmdlets:</span><span class="sxs-lookup"><span data-stu-id="e913b-129">The OnlineAudioConferencingRoutingPolicy policy can be managed by using the following cmdlets:</span></span>

-   <span data-ttu-id="e913b-130">New-CsOnlineAudioConferencingRoutingPolicy</span><span class="sxs-lookup"><span data-stu-id="e913b-130">New-CsOnlineAudioConferencingRoutingPolicy</span></span>
- <span data-ttu-id="e913b-131">Set-CsOnlineAudioConferencingRoutingPolicy</span><span class="sxs-lookup"><span data-stu-id="e913b-131">Set-CsOnlineAudioConferencingRoutingPolicy</span></span>
- <span data-ttu-id="e913b-132">Get-CsOnlineAudioConferencingRoutingPolicy</span><span class="sxs-lookup"><span data-stu-id="e913b-132">Get-CsOnlineAudioConferencingRoutingPolicy</span></span>
- <span data-ttu-id="e913b-133">Grant-CsOnlineAudioConferencingRoutingPolicy</span><span class="sxs-lookup"><span data-stu-id="e913b-133">Grant-CsOnlineAudioConferencingRoutingPolicy</span></span>
- <span data-ttu-id="e913b-134">Remove-CsOnlineAudioConferencingRoutingPolicy</span><span class="sxs-lookup"><span data-stu-id="e913b-134">Remove-CsOnlineAudioConferencingRoutingPolicy</span></span>

<span data-ttu-id="e913b-135">Дополнительные сведения о маршрутике для прямой маршрутии см. в этой [теме.](direct-routing-voice-routing.md)</span><span class="sxs-lookup"><span data-stu-id="e913b-135">For more information about routing for Direct Routing, see [Configure voice routing for Direct Routing](direct-routing-voice-routing.md).</span></span>


<span data-ttu-id="e913b-136">Чтобы включить маршрутику звонков с телефонным вызовом через прямую маршрутику, необходимо:</span><span class="sxs-lookup"><span data-stu-id="e913b-136">To enable the routing of meeting dial-out calls through Direct Routing, you need to:</span></span> 

- <span data-ttu-id="e913b-137">Настройка политик маршрутизации аудиоконференций</span><span class="sxs-lookup"><span data-stu-id="e913b-137">Configure Audio Conferencing routing policies</span></span>
- <span data-ttu-id="e913b-138">Настройка маршрутизации на телефонном оборудовании организации</span><span class="sxs-lookup"><span data-stu-id="e913b-138">Configure the routing on the telephony equipment of your organization</span></span>
- <span data-ttu-id="e913b-139">(Необязательно) Настройка набора номера</span><span class="sxs-lookup"><span data-stu-id="e913b-139">(Optional) Configure a dial plan</span></span>

<span data-ttu-id="e913b-140">Исходят звонки из Teams из конференц-зала исходят из номера службы по умолчанию на мосте конференции.</span><span class="sxs-lookup"><span data-stu-id="e913b-140">Dial-out calls from Teams meetings are coming from the default service number on the conference bridge.</span></span> <span data-ttu-id="e913b-141">Дополнительные сведения о номере службы по умолчанию для моста аудиоконференций см. в этой [теме.](change-the-phone-numbers-on-your-audio-conferencing-bridge.md)</span><span class="sxs-lookup"><span data-stu-id="e913b-141">For additional information on the default service number of your Audio Conferencing bridge, see [Change the phone numbers on your Audio Conferencing bridge](change-the-phone-numbers-on-your-audio-conferencing-bridge.md).</span></span>

### <a name="configure-audio-conferencing-routing-policies"></a><span data-ttu-id="e913b-142">Настройка политик маршрутизации аудиоконференций</span><span class="sxs-lookup"><span data-stu-id="e913b-142">Configure Audio Conferencing routing policies</span></span>

<span data-ttu-id="e913b-143">Политика маршрутизации аудиоконференции OnlineAudioConferencingRoutingPolicy определяет, какие звонки на собрания перенаправляются на линии прямой маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="e913b-143">The Audio Conferencing routing policy OnlineAudioConferencingRoutingPolicy determines which meeting dial-out calls are routed to Direct Routing trunks.</span></span> <span data-ttu-id="e913b-144">Если вы знакомы с политикой CsOnlineVoiceRoutingPolicy, она работает почти так же.</span><span class="sxs-lookup"><span data-stu-id="e913b-144">If you are familiar with the CsOnlineVoiceRoutingPolicy policy, this policy works in a very similar way.</span></span>

<span data-ttu-id="e913b-145">Чтобы настроить политики маршрутинга аудиоконференций, необходимо сделать следующее:</span><span class="sxs-lookup"><span data-stu-id="e913b-145">The following steps are needed to set up Audio Conferencing routing policies:</span></span>
1.  <span data-ttu-id="e913b-146">Создание использования ОКП</span><span class="sxs-lookup"><span data-stu-id="e913b-146">Create PSTN usages</span></span>
2.  <span data-ttu-id="e913b-147">Настройка голосовых маршрутов</span><span class="sxs-lookup"><span data-stu-id="e913b-147">Configure voice routes</span></span>
3.  <span data-ttu-id="e913b-148">Создание политик голосовой маршрутизации аудиоконференций</span><span class="sxs-lookup"><span data-stu-id="e913b-148">Create Audio Conferencing voice routing policies</span></span>
4.  <span data-ttu-id="e913b-149">Назначение политики пользователям</span><span class="sxs-lookup"><span data-stu-id="e913b-149">Assign a policy to your users</span></span>


#### <a name="create-pstn-usages"></a><span data-ttu-id="e913b-150">Создание использования ОКП</span><span class="sxs-lookup"><span data-stu-id="e913b-150">Create PSTN usages</span></span>

<span data-ttu-id="e913b-151">Использование услуг STN — это наборы голосовых маршрутов.</span><span class="sxs-lookup"><span data-stu-id="e913b-151">PSTN usages are collections of voice routes.</span></span> <span data-ttu-id="e913b-152">При инициирующем звонке из собрания организатора голосовые маршруты используются для определения маршрутизов звонка на основе использования услуг STN, связанных с пользователем с помощью политики маршрутизов голосовой связи пользователя.</span><span class="sxs-lookup"><span data-stu-id="e913b-152">When a dial-out call is initiated from the meeting of a given organizer, voice routes will be used to determine the routing path of the call based on the PSTN usages that are associated to the user via the user’s voice routing policy.</span></span>

<span data-ttu-id="e913b-153">Вы можете создать использование ПСОП с помощью "Set-CsOnlinePstnUsage".</span><span class="sxs-lookup"><span data-stu-id="e913b-153">You can create a PSTN usage by using the “Set-CsOnlinePstnUsage” cmdlet.</span></span> <span data-ttu-id="e913b-154">Например:</span><span class="sxs-lookup"><span data-stu-id="e913b-154">For Example:</span></span>

```powershell
Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="US and Canada"}
```

#### <a name="configure-voice-routes"></a><span data-ttu-id="e913b-155">Настройка голосовых маршрутов</span><span class="sxs-lookup"><span data-stu-id="e913b-155">Configure voice routes</span></span>

<span data-ttu-id="e913b-156">Голосовые маршруты определяют шлюз ЗВОНКОВ, который должен использоваться для перенастройки звонка на основе номера телефона, набра номера Teams собрания.</span><span class="sxs-lookup"><span data-stu-id="e913b-156">Voice routes determine the PSTN gateway that should be used to route a call based on the phone number that is dialed from a Teams meeting.</span></span> <span data-ttu-id="e913b-157">Голосовые маршруты определяют шлюз ЗВОНКОВ, который должен использоваться для перенастройки звонка, путем совпадения номера телефона, набраного из собрания Teams с шаблоном регексации.</span><span class="sxs-lookup"><span data-stu-id="e913b-157">Voice routes determine the PSTN gateway that should be used to route a given call by matching the phone number dialed from a Teams meeting with a regex pattern.</span></span> <span data-ttu-id="e913b-158">При создании голосового маршрута он должен быть связан с одним или нескольком использованием ОКП.</span><span class="sxs-lookup"><span data-stu-id="e913b-158">When creating a voice route, the route must be associated to one or more PSTN usages.</span></span>

<span data-ttu-id="e913b-159">Вы можете создать голосовой маршрут и определить regex и шлюзы, которые будут связаны с голосовым маршрутом, с помощью "New-CsOnlineVoiceRoute".</span><span class="sxs-lookup"><span data-stu-id="e913b-159">You can create a voice route and define the regex and gateways to be associated with the voice route by using the “New-CsOnlineVoiceRoute” cmdlet.</span></span> <span data-ttu-id="e913b-160">Например:</span><span class="sxs-lookup"><span data-stu-id="e913b-160">For Example:</span></span>

```powershell
New-CsOnlineVoiceRoute -Identity "Redmond 1" -NumberPattern "^\+1(425|206)(\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
```

#### <a name="create-audio-conferencing-voice-routing-policies"></a><span data-ttu-id="e913b-161">Создание политик голосовой маршрутизации аудиоконференций</span><span class="sxs-lookup"><span data-stu-id="e913b-161">Create Audio Conferencing voice routing policies</span></span>

<span data-ttu-id="e913b-162">Политики маршрутизации голосовой связи для аудиоконференций определяют возможные маршруты, которые могут использоваться для перенастройки звонка, исходя из собраний организатора, на основе целевого номера телефона в телефонном звонке.</span><span class="sxs-lookup"><span data-stu-id="e913b-162">Audio Conferencing voice routing policies determine the possible routes that can be used to route a call originating from the meetings of an organizer based on the target phone number of the meeting dial-out call.</span></span> <span data-ttu-id="e913b-163">Политики перенастройки голосовой маршрутизации аудиоконференций связаны с одним или несколькою вариантами использования услуг ЗВОНКОВ по STN, которые, в свою очередь, определяют возможные маршруты, которые будут использоваться для звонков с телефонным вызовом организаторов, связанных с политикой.</span><span class="sxs-lookup"><span data-stu-id="e913b-163">Audio Conferencing voice routing policies are associated to one or more PSTN usages, which in turn, determine the possible routes that will be attempted to be used for the meeting dial-out calls of the organizers associated to the policy.</span></span>

<span data-ttu-id="e913b-164">Политику маршрутизации голосовой маршрутизации аудиоконференции можно создать с помощью "New-CsOnlineAudioConferencingRoutingPolicy".</span><span class="sxs-lookup"><span data-stu-id="e913b-164">You can create an Audio Conferencing voice routing policy by using the “New- CsOnlineAudioConferencingRoutingPolicy” cmdlet.</span></span> <span data-ttu-id="e913b-165">Например:</span><span class="sxs-lookup"><span data-stu-id="e913b-165">For Example:</span></span>

```powershell
New-CsOnlineAudioConferencingRoutingPolicy "Policy 1" -OnlinePstnUsages "US and Canada"
```

<span data-ttu-id="e913b-166">После того как политика будет назначена пользователю и когда из одного из собраний будет инициировался звонок с телефонного звонка, будут оцениваться голосовые маршруты в рамках использования услуг STN, связанных с организатором с помощью политики маршрутизов голосовой связи пользователя.</span><span class="sxs-lookup"><span data-stu-id="e913b-166">After the policy is assigned to a user, and when a meeting dial-out call is initiated from one of the user's meetings, the voice routes in the PSTN usages that are associated to the organizer through the user's voice routing policy will be evaluated.</span></span> <span data-ttu-id="e913b-167">Если место назначения для телефонного звонка для собрания совпадает срегесом в одном из голосовых маршрутов, связанных с организатором, звонок будет перенаправлен на шлюз ПСN, определенный в голосовом маршруте.</span><span class="sxs-lookup"><span data-stu-id="e913b-167">If the meeting dial-out call destination matches a regex in one of the voice routes that are associated to the organizer, the meeting dial-out call will be routed to the PSTN gateway defined in the voice route.</span></span> <span data-ttu-id="e913b-168">Если место назначения для телефонного звонка не соответствует ни одной из голосовых маршрутов, связанных с организатором, звонок будет перенаправлен корпорацией Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="e913b-168">If the meeting dial-out call destination does not match any of the voice routes associated to the organizer, the meeting dial-out call will be routed by Microsoft.</span></span>

#### <a name="assign-a-policy-to-your-users"></a><span data-ttu-id="e913b-169">Назначение политики пользователям</span><span class="sxs-lookup"><span data-stu-id="e913b-169">Assign a policy to your users</span></span>

<span data-ttu-id="e913b-170">После определения политик маршрутинга аудиоконференций вы можете назначить их пользователям.</span><span class="sxs-lookup"><span data-stu-id="e913b-170">After the Audio Conferencing routing policies are defined, you can now assign them to users.</span></span> <span data-ttu-id="e913b-171">После того как политикам будут назначены политики, для определения пути их маршрутки будут оцениваться звонки с телефонным вызовом на собрание.</span><span class="sxs-lookup"><span data-stu-id="e913b-171">After policies are assigned to them, the meeting dial-out calls will be evaluated against it to determine their routing path.</span></span> <span data-ttu-id="e913b-172">Политики маршрутизации аудиоконференций всегда оцениваются на основе организатора собрания независимо от пользователя в собрании, который инициирует звонок по телефону.</span><span class="sxs-lookup"><span data-stu-id="e913b-172">Audio Conferencing routing policies are always evaluated based on the organizer of the meeting, independently from the user in the meeting that initiates a meeting dial-out call.</span></span>

<span data-ttu-id="e913b-173">Политику маршрутизации голосовой сети аудиоконференции можно назначить пользователю с помощью "Grant-CsOnlineAudioConferencingRoutingPolicy".</span><span class="sxs-lookup"><span data-stu-id="e913b-173">You can assign an Audio Conferencing voice routing policy to a user by using the “Grant-CsOnlineAudioConferencingRoutingPolicy” cmdlet.</span></span> <span data-ttu-id="e913b-174">Например:</span><span class="sxs-lookup"><span data-stu-id="e913b-174">For example:</span></span>

```powershell
Grant-CsOnlineAudioConferencingRoutingPolicy -Identity "<User Identity>" -PolicyName "Policy 1”
```


### <a name="configure-routing-on-the-telephony-equipment-of-your-organization"></a><span data-ttu-id="e913b-175">Настройка маршрутизации на телефонном оборудовании организации</span><span class="sxs-lookup"><span data-stu-id="e913b-175">Configure routing on the telephony equipment of your organization</span></span>

<span data-ttu-id="e913b-176">На телефонном оборудовании организации необходимо убедиться, что звонки с телефонным вызовом, перенаправленные по прямой маршрутизации, перенаправятся в нужное сетевое место.</span><span class="sxs-lookup"><span data-stu-id="e913b-176">On the telephony equipment of your organization, you need to ensure that the meeting dial-out calls routed through Direct Routing are routed to the intended on-network destination.</span></span>


### <a name="optional-configure-a-dial-plan"></a><span data-ttu-id="e913b-177">(Необязательно) Настройка набора номера</span><span class="sxs-lookup"><span data-stu-id="e913b-177">(Optional) Configure a dial plan</span></span>

<span data-ttu-id="e913b-178">Телефонная плана — это набор правил нормализации, которые переводят номера телефонов отдельных пользователей в альтернативный формат (обычно E.164) для авторизации звонков и маршрутизации звонков.</span><span class="sxs-lookup"><span data-stu-id="e913b-178">A dial plan is a set of normalization rules that translate dialed phone numbers by an individual user into an alternate format (typically E.164) for purposes of call authorization and call routing.</span></span>

<span data-ttu-id="e913b-179">По умолчанию Teams к номерам ДНР в формате E.164, т. е. + \<country code\> \<number\> .</span><span class="sxs-lookup"><span data-stu-id="e913b-179">By default, Teams users can dial-out to PSTN numbers in E.164 format, that is, +\<country code\>\<number\>.</span></span> <span data-ttu-id="e913b-180">Однако можно использовать планы набора, чтобы разрешить пользователям набирать номера телефонов в других форматах, например в четырехзначных расширениях.</span><span class="sxs-lookup"><span data-stu-id="e913b-180">However, dial plans can be used to allow users to dial phone numbers in other formats, for instance 4-digit extensions.</span></span>

<span data-ttu-id="e913b-181">Если вы хотите включить телефонную сеть с телефонным набором с учетом расширения, вы можете настроить наборные планы так, чтобы он совпадал с диапазонами телефонных номеров вашей организации.</span><span class="sxs-lookup"><span data-stu-id="e913b-181">If you would like to enable extension-based dialing through On-network conferencing, you can set up dial plans to match the extension dialing pattern to the phone number ranges of the phone number of your organization.</span></span> <span data-ttu-id="e913b-182">Чтобы настроить наборные планы, см. создание планов набора номера [и управление ими.](create-and-manage-dial-plans.md)</span><span class="sxs-lookup"><span data-stu-id="e913b-182">To set up dial plans, see [Create and manage dial plans](create-and-manage-dial-plans.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="e913b-183">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="e913b-183">Related topics</span></span>


