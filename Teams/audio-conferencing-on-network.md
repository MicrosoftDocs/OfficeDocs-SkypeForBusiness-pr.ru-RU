---
title: Сетевые конференции для голосовой конференции
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
description: Ниже описаны открытые функции предварительного просмотра для голосовой конференции по сети.
ms.openlocfilehash: 1ae61034ef083c89e14c67cef0effa1c105de758
ms.sourcegitcommit: 57fddb045f4a9df14cc421b1f6a228df91f334de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/13/2020
ms.locfileid: "49031865"
---
# <a name="open-preview-of-on-network-conferencing-for-audio-conferencing"></a><span data-ttu-id="1902c-103">Открытие предварительной версии конференции по сети для голосовой конференции</span><span class="sxs-lookup"><span data-stu-id="1902c-103">Open Preview of On-network Conferencing for Audio Conferencing</span></span>

<span data-ttu-id="1902c-104">Открытая Предварительная версия конференции по сети доступна всем пользователям.</span><span class="sxs-lookup"><span data-stu-id="1902c-104">The Open Preview of On-network Conferencing is available to all customers.</span></span> <span data-ttu-id="1902c-105">Сетевые конференции позволяют организациям отправлять входящие и исходящие звонки на номера телефонной связи Майкрософт посредством прямой маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="1902c-105">On-network Conferencing allows organizations to send inbound and outbound Audio Conferencing calls to Microsoft dial-in numbers through Direct Routing.</span></span> <span data-ttu-id="1902c-106">Эта возможность не предназначена для продления поддержки голосовой конференц-связи с телефонными номерами третьих лиц.</span><span class="sxs-lookup"><span data-stu-id="1902c-106">This capability is not intended to extend the support of Audio Conferencing to third party dial-in numbers.</span></span> <span data-ttu-id="1902c-107">Сетевая Конференция не поддерживается, если она используется для направления входящих звонков в службу голосовой связи по третьим номерам абонентов.</span><span class="sxs-lookup"><span data-stu-id="1902c-107">On-network Conferencing is not supported if it is used to route inbound calls to the Audio Conferencing service through third party dial-in phone numbers.</span></span>

<span data-ttu-id="1902c-108">В этой статье описаны требования и этапы настройки, необходимые для включения сетевой конференции в Организации.</span><span class="sxs-lookup"><span data-stu-id="1902c-108">This article describes the prerequisites and configuration steps required to enable On-network Conferencing for your organization.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1902c-109">Сетевые конференции не должны развертываться с использованием оборудования телефонной связи в Индии.</span><span class="sxs-lookup"><span data-stu-id="1902c-109">On-network Conferencing must NOT be deployed with any telephony equipment in India.</span></span>
  
## <a name="prerequisites"></a><span data-ttu-id="1902c-110">Необходимые компоненты</span><span class="sxs-lookup"><span data-stu-id="1902c-110">Prerequisites</span></span>

<span data-ttu-id="1902c-111">Перед настройкой конференции по сети убедитесь, что ваша организация соответствует следующим требованиям:</span><span class="sxs-lookup"><span data-stu-id="1902c-111">Before configuring On-network Conferencing, make sure your organization meets the following prerequisites:</span></span> 

- <span data-ttu-id="1902c-112">Убедитесь, что все пользователи в вашей организации, которые включены или будут включены, для голосовой конференции используются группы для всех собраний.</span><span class="sxs-lookup"><span data-stu-id="1902c-112">Ensure that all users in your organization who are enabled, or will be enabled, for Audio Conferencing are using Teams for all Meetings.</span></span> <span data-ttu-id="1902c-113">Маршрутизация входящей и исходящей голосовой связи через сетевую конференцию поддерживается только для собраний Teams.</span><span class="sxs-lookup"><span data-stu-id="1902c-113">The routing of inbound and outbound Audio Conferencing calls through On-network Conferencing is only supported for Teams meetings.</span></span>

- <span data-ttu-id="1902c-114">Назначение лицензий на голосовую конференцию всем пользователям, которые будут использовать сетевую конференцию.</span><span class="sxs-lookup"><span data-stu-id="1902c-114">Assign Audio Conferencing licenses to all users who will be using On-network Conferencing.</span></span>

- <span data-ttu-id="1902c-115">Настройка службы звуковых конференций.</span><span class="sxs-lookup"><span data-stu-id="1902c-115">Set up the Audio Conferencing service.</span></span> <span data-ttu-id="1902c-116">Дополнительные сведения можно найти в разделе [Настройка голосовой конференции для Microsoft Teams](set-up-audio-conferencing-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="1902c-116">For additional information, see [Set up Audio Conferencing for Microsoft Teams](set-up-audio-conferencing-in-teams.md).</span></span>

- <span data-ttu-id="1902c-117">Настройка связи между контроллером границ сеанса (SBC) для прямой маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="1902c-117">Set up your Session Border Controller (SBC) for Direct Routing.</span></span> <span data-ttu-id="1902c-118">Дополнительные сведения можно найти в разделе [планирование прямой маршрутизации](direct-routing-plan.md) и [Настройка прямого маршрута](direct-routing-configure.md).</span><span class="sxs-lookup"><span data-stu-id="1902c-118">For additional information, see [Plan Direct Routing](direct-routing-plan.md) and [Configure Direct Routing](direct-routing-configure.md).</span></span> 

  <span data-ttu-id="1902c-119">Если вы настраиваете прямую маршрутизацию только для целей голосовой конференции, вам нужно только выполнить команду "шаг 1: подключение SBC" для проведения Конференции по сети.</span><span class="sxs-lookup"><span data-stu-id="1902c-119">If you are setting up Direct Routing only for the purposes of Audio Conferencing, then you need only complete “Step 1: Connect your SBC” for On-network Conferencing.</span></span>
  
## <a name="enable-the-routing-of-dial-in-calls-to-microsoft-audio-conferencing-through-direct-routing"></a><span data-ttu-id="1902c-120">Включение маршрутизации звонков на телефонную конференцию Майкрософт через прямую маршрутизацию</span><span class="sxs-lookup"><span data-stu-id="1902c-120">Enable the routing of dial-in calls to Microsoft Audio Conferencing through Direct Routing</span></span> 

<span data-ttu-id="1902c-121">Чтобы перенаправить телефонные звонки, совершенные локальными пользователями, на службу голосовой связи через прямую маршрутизацию, вам нужно настроить соответствующие правила маршрутизации для обмена данными с SBCs и частных филиалов (АТС).</span><span class="sxs-lookup"><span data-stu-id="1902c-121">To route dial-in calls made by your on-premises users to the Audio Conferencing service through Direct Routing, you need to configure appropriate routing rules for your SBCs and Private Branch Exchange(s) (PBXs).</span></span>

<span data-ttu-id="1902c-122">Чтобы направлять звонки на любые номера служб моста конференц-связи с помощью прямой магистральной магистрали, нужно настроить оборудование для своих сайтов.</span><span class="sxs-lookup"><span data-stu-id="1902c-122">You need to configure the telephony equipment of your sites to route calls to any service number of the conference bridge of your organization through a Direct Routing trunk.</span></span>

<span data-ttu-id="1902c-123">Номера служб в центре администрирования Teams можно найти в разделе **собрания — > мосты Конференц-** связи или с помощью командлета PowerShell Get-CsOnlineDialInConferencingBridge в Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="1902c-123">You can find the service numbers in Teams admin center under **Meetings -> Conferencing Bridges** or by using the Skype for Business Online PowerShell cmdlet Get-CsOnlineDialInConferencingBridge.</span></span> <span data-ttu-id="1902c-124">Дополнительные сведения можно найти [в списке номеров голосовой конференц-связи в Microsoft Teams](see-a-list-of-audio-conferencing-numbers-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="1902c-124">For additional information, see a list of [Audio Conferencing numbers in Microsoft Teams](see-a-list-of-audio-conferencing-numbers-in-teams.md).</span></span>

> [!NOTE]
> <span data-ttu-id="1902c-125">Эта функция недоступна для пользователей с лицензией на голосовую конференцию с оплатой через минуту.</span><span class="sxs-lookup"><span data-stu-id="1902c-125">This feature is not available to users with the pay-per-minute Audio Conferencing license.</span></span>

## <a name="enable-the-routing-of-teams-meeting-dial-out-calls-through-direct-routing"></a><span data-ttu-id="1902c-126">Включение маршрутизации звонков для собраний по телефонным звонкам через прямую маршрутизацию</span><span class="sxs-lookup"><span data-stu-id="1902c-126">Enable the routing of Teams meeting dial-out calls through Direct Routing</span></span>

<span data-ttu-id="1902c-127">Звонки по исходящим звонкам в сети загружаются в рамках собрания в вашей организации на номера PSTN, в том числе на звонки и звонки для новых участников собрания.</span><span class="sxs-lookup"><span data-stu-id="1902c-127">Teams meeting dial-out calls are initiated from within a meeting in your organization to PSTN numbers, including call-me-at calls and calls to bring new participants to a meeting.</span></span> 

<span data-ttu-id="1902c-128">Чтобы включить маршрутизацию исходящих звонков в Teams через прямую маршрутизацию на пользователей, подключенных к сети, необходимо создать и назначить политику маршрутизации голосовой конференц-связи с именем "OnlineAudioConferencingRoutingPolicy".</span><span class="sxs-lookup"><span data-stu-id="1902c-128">To enable Teams meeting dial-out routing through Direct Routing to on-network users, you need to create and assign an Audio Conferencing routing policy called “OnlineAudioConferencingRoutingPolicy”.</span></span> 

<span data-ttu-id="1902c-129">Политика OnlineAudioConferencingRoutingPolicy эквивалентна CsOnlineVoiceRoutingPolicy для звонков по протоколу КТСОП для 1:1 PSTN через прямую маршрутизацию.</span><span class="sxs-lookup"><span data-stu-id="1902c-129">The OnlineAudioConferencingRoutingPolicy policy is equivalent to the CsOnlineVoiceRoutingPolicy for 1:1 PSTN calls via Direct Routing.</span></span> <span data-ttu-id="1902c-130">Для управления политикой OnlineAudioConferencingRoutingPolicy используются следующие командлеты:</span><span class="sxs-lookup"><span data-stu-id="1902c-130">The OnlineAudioConferencingRoutingPolicy policy can be managed by using the following cmdlets:</span></span>

-   <span data-ttu-id="1902c-131">New-CsOnlineAudioConferencingRoutingPolicy</span><span class="sxs-lookup"><span data-stu-id="1902c-131">New-CsOnlineAudioConferencingRoutingPolicy</span></span>
- <span data-ttu-id="1902c-132">Set-CsOnlineAudioConferencingRoutingPolicy</span><span class="sxs-lookup"><span data-stu-id="1902c-132">Set-CsOnlineAudioConferencingRoutingPolicy</span></span>
- <span data-ttu-id="1902c-133">Get-CsOnlineAudioConferencingRoutingPolicy</span><span class="sxs-lookup"><span data-stu-id="1902c-133">Get-CsOnlineAudioConferencingRoutingPolicy</span></span>
- <span data-ttu-id="1902c-134">Grant-CsOnlineAudioConferencingRoutingPolicy</span><span class="sxs-lookup"><span data-stu-id="1902c-134">Grant-CsOnlineAudioConferencingRoutingPolicy</span></span>
- <span data-ttu-id="1902c-135">Remove-CsOnlineAudioConferencingRoutingPolicy</span><span class="sxs-lookup"><span data-stu-id="1902c-135">Remove-CsOnlineAudioConferencingRoutingPolicy</span></span>

<span data-ttu-id="1902c-136">Дополнительные сведения о маршрутизации для прямой маршрутизации можно найти в разделе [Настройка маршрутизации голосовой связи для прямой маршрутизации](direct-routing-voice-routing.md).</span><span class="sxs-lookup"><span data-stu-id="1902c-136">For more information about routing for Direct Routing, see [Configure voice routing for Direct Routing](direct-routing-voice-routing.md).</span></span>


<span data-ttu-id="1902c-137">Чтобы включить маршрутизацию звонков по телефонной связи через прямую маршрутизацию, необходимо выполнить следующие действия.</span><span class="sxs-lookup"><span data-stu-id="1902c-137">To enable the routing of meeting dial-out calls through Direct Routing, you need to:</span></span> 

- <span data-ttu-id="1902c-138">Настройка политик маршрутизации голосовой конференции</span><span class="sxs-lookup"><span data-stu-id="1902c-138">Configure Audio Conferencing routing policies</span></span>
- <span data-ttu-id="1902c-139">Настройка маршрутизации для оборудования телефонной связи в Организации</span><span class="sxs-lookup"><span data-stu-id="1902c-139">Configure the routing on the telephony equipment of your organization</span></span>
- <span data-ttu-id="1902c-140">Необязательно Настройка абонентской группы</span><span class="sxs-lookup"><span data-stu-id="1902c-140">(Optional) Configure a dial plan</span></span>

<span data-ttu-id="1902c-141">Звонки по исходящим звонкам из собраний по сети исходят из номера службы, используемого по умолчанию для моста конференц-связи.</span><span class="sxs-lookup"><span data-stu-id="1902c-141">Dial-out calls from Teams meetings are coming from the default service number on the conference bridge.</span></span> <span data-ttu-id="1902c-142">Дополнительные сведения о номере службы по умолчанию для вашего моста голосовой связи можно найти [в разделе изменение номеров телефонов для вашего моста звуковых](change-the-phone-numbers-on-your-audio-conferencing-bridge.md)конференций.</span><span class="sxs-lookup"><span data-stu-id="1902c-142">For additional information on the default service number of your Audio Conferencing bridge, see [Change the phone numbers on your Audio Conferencing bridge](change-the-phone-numbers-on-your-audio-conferencing-bridge.md).</span></span>

### <a name="configure-audio-conferencing-routing-policies"></a><span data-ttu-id="1902c-143">Настройка политик маршрутизации голосовой конференции</span><span class="sxs-lookup"><span data-stu-id="1902c-143">Configure Audio Conferencing routing policies</span></span>

<span data-ttu-id="1902c-144">Политика маршрутизации OnlineAudioConferencingRoutingPolicy определяет, какие звонки на собрание направляются на прямые магистрали маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="1902c-144">The Audio Conferencing routing policy OnlineAudioConferencingRoutingPolicy determines which meeting dial-out calls are routed to Direct Routing trunks.</span></span> <span data-ttu-id="1902c-145">Если вы знакомы с политикой CsOnlineVoiceRoutingPolicy, эта политика работает очень похожим образом.</span><span class="sxs-lookup"><span data-stu-id="1902c-145">If you are familiar with the CsOnlineVoiceRoutingPolicy policy, this policy works in a very similar way.</span></span>

<span data-ttu-id="1902c-146">Чтобы настроить политики маршрутизации голосовой связи, необходимо выполнить указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="1902c-146">The following steps are needed to set up Audio Conferencing routing policies:</span></span>
1.  <span data-ttu-id="1902c-147">Создание использованных PSTN</span><span class="sxs-lookup"><span data-stu-id="1902c-147">Create PSTN usages</span></span>
2.  <span data-ttu-id="1902c-148">Настройка маршрутов голосовой связи</span><span class="sxs-lookup"><span data-stu-id="1902c-148">Configure voice routes</span></span>
3.  <span data-ttu-id="1902c-149">Создание политик маршрутизации голосовых команд для голосовой связи</span><span class="sxs-lookup"><span data-stu-id="1902c-149">Create Audio Conferencing voice routing policies</span></span>
4.  <span data-ttu-id="1902c-150">Назначение политики пользователям</span><span class="sxs-lookup"><span data-stu-id="1902c-150">Assign a policy to your users</span></span>


#### <a name="create-pstn-usages"></a><span data-ttu-id="1902c-151">Создание использованных PSTN</span><span class="sxs-lookup"><span data-stu-id="1902c-151">Create PSTN usages</span></span>

<span data-ttu-id="1902c-152">Использование PSTN — это наборы голосовых маршрутов.</span><span class="sxs-lookup"><span data-stu-id="1902c-152">PSTN usages are collections of voice routes.</span></span> <span data-ttu-id="1902c-153">Когда звонок на исходящий вызов инициируется из собрания определенного организатора, для определения пути маршрутизации звонка на основе параметров использования PSTN, связанных с пользователем, используется политика голосовой маршрутизации пользователя.</span><span class="sxs-lookup"><span data-stu-id="1902c-153">When a dial-out call is initiated from the meeting of a given organizer, voice routes will be used to determine the routing path of the call based on the PSTN usages that are associated to the user via the user’s voice routing policy.</span></span>

<span data-ttu-id="1902c-154">Использование PSTN можно создать с помощью командлета Set-CsOnlinePstnUsage.</span><span class="sxs-lookup"><span data-stu-id="1902c-154">You can create a PSTN usage by using the “Set-CsOnlinePstnUsage” cmdlet.</span></span> <span data-ttu-id="1902c-155">Например:</span><span class="sxs-lookup"><span data-stu-id="1902c-155">For Example:</span></span>

```powershell
Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="US and Canada"}
```

#### <a name="configure-voice-routes"></a><span data-ttu-id="1902c-156">Настройка маршрутов голосовой связи</span><span class="sxs-lookup"><span data-stu-id="1902c-156">Configure voice routes</span></span>

<span data-ttu-id="1902c-157">Голосовые маршруты определяют шлюз PSTN, который должен использоваться для маршрутизации звонка, на основе номера телефона, набираемого из собрания Teams.</span><span class="sxs-lookup"><span data-stu-id="1902c-157">Voice routes determine the PSTN gateway that should be used to route a call based on the phone number that is dialed from a Teams meeting.</span></span> <span data-ttu-id="1902c-158">Голосовые маршруты определяют шлюз PSTN, который должен использоваться для маршрутизации определенного звонка путем сопоставления номера телефона, набранного на собрании Teams, с шаблоном регулярного выражения.</span><span class="sxs-lookup"><span data-stu-id="1902c-158">Voice routes determine the PSTN gateway that should be used to route a given call by matching the phone number dialed from a Teams meeting with a regex pattern.</span></span> <span data-ttu-id="1902c-159">При создании голосового маршрута маршрут должен быть связан с одной или несколькими использованием PSTN.</span><span class="sxs-lookup"><span data-stu-id="1902c-159">When creating a voice route, the route must be associated to one or more PSTN usages.</span></span>

<span data-ttu-id="1902c-160">Вы можете создать голосовой маршрут и задать регулярное выражение и шлюзы, которые будут связаны с голосовыми маршрутами с помощью командлета New-CsOnlineVoiceRoute.</span><span class="sxs-lookup"><span data-stu-id="1902c-160">You can create a voice route and define the regex and gateways to be associated with the voice route by using the “New-CsOnlineVoiceRoute” cmdlet.</span></span> <span data-ttu-id="1902c-161">Например:</span><span class="sxs-lookup"><span data-stu-id="1902c-161">For Example:</span></span>

```powershell
New-CsOnlineVoiceRoute -Identity "Redmond 1" -NumberPattern "^\+1(425|206)(\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
```

#### <a name="create-audio-conferencing-voice-routing-policies"></a><span data-ttu-id="1902c-162">Создание политик маршрутизации голосовых команд для голосовой связи</span><span class="sxs-lookup"><span data-stu-id="1902c-162">Create Audio Conferencing voice routing policies</span></span>

<span data-ttu-id="1902c-163">Политики маршрутизации голосовой связи — это определение возможных маршрутов, которые можно использовать для маршрутизации вызова, направленного на собрание организатора, на основе номера целевого телефона звонка для звонков.</span><span class="sxs-lookup"><span data-stu-id="1902c-163">Audio Conferencing voice routing policies determine the possible routes that can be used to route a call originating from the meetings of an organizer based on the target phone number of the meeting dial-out call.</span></span> <span data-ttu-id="1902c-164">Политики маршрутизации голосовых конференций связаны с одним или несколькими использованием PSTN, которые, в свою очередь, определяют возможные маршруты, которые будут использоваться для звонков по исходящим звонкам организаторов, связанного с политикой.</span><span class="sxs-lookup"><span data-stu-id="1902c-164">Audio Conferencing voice routing policies are associated to one or more PSTN usages, which in turn, determine the possible routes that will be attempted to be used for the meeting dial-out calls of the organizers associated to the policy.</span></span>

<span data-ttu-id="1902c-165">Вы можете создать политику маршрутизации голосовой связи с помощью командлета New-CsOnlineAudioConferencingRoutingPolicy.</span><span class="sxs-lookup"><span data-stu-id="1902c-165">You can create an Audio Conferencing voice routing policy by using the “New- CsOnlineAudioConferencingRoutingPolicy” cmdlet.</span></span> <span data-ttu-id="1902c-166">Например:</span><span class="sxs-lookup"><span data-stu-id="1902c-166">For Example:</span></span>

```powershell
New-CsOnlineAudioConferencingRoutingPolicy "Policy 1" -OnlinePstnUsages "US and Canada"
```

<span data-ttu-id="1902c-167">После того как политика назначена пользователю, и когда звонок на вызов по истечении собрания инициируется из одного из собраний пользователя, будут оцениваться маршруты голосовой связи, связанные с организатором с помощью политики голосовой маршрутизации пользователя.</span><span class="sxs-lookup"><span data-stu-id="1902c-167">After the policy is assigned to a user, and when a meeting dial-out call is initiated from one of the user's meetings, the voice routes in the PSTN usages that are associated to the organizer through the user's voice routing policy will be evaluated.</span></span> <span data-ttu-id="1902c-168">Если конечный объект вызова для собраний по телефонному подключению соответствует регулярному выражению в одном из голосовых маршрутов, связанных с организатором, Звонок на удаленное собрание будет перенаправляться на шлюз PSTN, определенный в маршруте голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="1902c-168">If the meeting dial-out call destination matches a regex in one of the voice routes that are associated to the organizer, the meeting dial-out call will be routed to the PSTN gateway defined in the voice route.</span></span> <span data-ttu-id="1902c-169">Если конечный адрес для звонка на собрание не соответствует ни одному из голосовых маршрутов, связанных с организатором, вызов по удаленному собранию будет маршрутизироваться корпорацией Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="1902c-169">If the meeting dial-out call destination does not match any of the voice routes associated to the organizer, the meeting dial-out call will be routed by Microsoft.</span></span>

#### <a name="assign-a-policy-to-your-users"></a><span data-ttu-id="1902c-170">Назначение политики пользователям</span><span class="sxs-lookup"><span data-stu-id="1902c-170">Assign a policy to your users</span></span>

<span data-ttu-id="1902c-171">После определения политик маршрутизации видеоконференций вы можете назначить их пользователям.</span><span class="sxs-lookup"><span data-stu-id="1902c-171">After the Audio Conferencing routing policies are defined, you can now assign them to users.</span></span> <span data-ttu-id="1902c-172">После того, как политики будут назначены, для них будут вычислены звонки для собраний, чтобы определить путь маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="1902c-172">After policies are assigned to them, the meeting dial-out calls will be evaluated against it to determine their routing path.</span></span> <span data-ttu-id="1902c-173">Политики маршрутизации для голосовой связи всегда оцениваются в зависимости от организатора собрания, независимо от пользователя на собрании, инициирующего Звонок на собрание.</span><span class="sxs-lookup"><span data-stu-id="1902c-173">Audio Conferencing routing policies are always evaluated based on the organizer of the meeting, independently from the user in the meeting that initiates a meeting dial-out call.</span></span>

<span data-ttu-id="1902c-174">Вы можете назначить политику маршрутизации голосовой связи для пользователя с помощью командлета Grant-CsOnlineAudioConferencingRoutingPolicy.</span><span class="sxs-lookup"><span data-stu-id="1902c-174">You can assign an Audio Conferencing voice routing policy to a user by using the “Grant-CsOnlineAudioConferencingRoutingPolicy” cmdlet.</span></span> <span data-ttu-id="1902c-175">Например:</span><span class="sxs-lookup"><span data-stu-id="1902c-175">For example:</span></span>

```powershell
Grant-CsOnlineAudioConferencingRoutingPolicy -Identity "<User Identity>" -PolicyName "Policy 1”
```


### <a name="configure-routing-on-the-telephony-equipment-of-your-organization"></a><span data-ttu-id="1902c-176">Настройка маршрутизации для оборудования телефонной связи в Организации</span><span class="sxs-lookup"><span data-stu-id="1902c-176">Configure routing on the telephony equipment of your organization</span></span>

<span data-ttu-id="1902c-177">На оборудовании организации телефонной связи необходимо убедиться, что звонки по исходящим звонкам, направляемые через прямую маршрутизацию, перенаправляются в предназначенный для использования в сети адрес.</span><span class="sxs-lookup"><span data-stu-id="1902c-177">On the telephony equipment of your organization, you need to ensure that the meeting dial-out calls routed through Direct Routing are routed to the intended on-network destination.</span></span>


### <a name="optional-configure-a-dial-plan"></a><span data-ttu-id="1902c-178">Необязательно Настройка абонентской группы</span><span class="sxs-lookup"><span data-stu-id="1902c-178">(Optional) Configure a dial plan</span></span>

<span data-ttu-id="1902c-179">Абонентская группа — это набор правил нормализации, который может преобразовывать номера набранных номеров отдельных пользователей в альтернативный формат (обычно E. 164) для авторизации звонков и маршрутизации звонков.</span><span class="sxs-lookup"><span data-stu-id="1902c-179">A dial plan is a set of normalization rules that translate dialed phone numbers by an individual user into an alternate format (typically E.164) for purposes of call authorization and call routing.</span></span>

<span data-ttu-id="1902c-180">По умолчанию пользователи Teams могут звонить по номерам PSTN в формате E. 164 (+) \<country code\> \<number\> .</span><span class="sxs-lookup"><span data-stu-id="1902c-180">By default, Teams users can dial-out to PSTN numbers in E.164 format, that is, +\<country code\>\<number\>.</span></span> <span data-ttu-id="1902c-181">Тем не менее, абонентские группы можно использовать, чтобы разрешить пользователям набирать телефонные номера в других форматах, например в 4-разрядных расширениях.</span><span class="sxs-lookup"><span data-stu-id="1902c-181">However, dial plans can be used to allow users to dial phone numbers in other formats, for instance 4-digit extensions.</span></span>

<span data-ttu-id="1902c-182">Если вы хотите включить набор номера на основе расширения в конференц-связи по сети, вы можете настроить абонентские группы так, чтобы они соответствовали шаблону набора номера в диапазонах номеров телефонов в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="1902c-182">If you would like to enable extension-based dialing through On-network conferencing, you can set up dial plans to match the extension dialing pattern to the phone number ranges of the phone number of your organization.</span></span> <span data-ttu-id="1902c-183">Чтобы настроить абонентские группы, ознакомьтесь со сведениями создание абонентских группы [и управление ими](create-and-manage-dial-plans.md).</span><span class="sxs-lookup"><span data-stu-id="1902c-183">To set up dial plans, see [Create and manage dial plans](create-and-manage-dial-plans.md).</span></span>


## <a name="known-issues-in-open-preview"></a><span data-ttu-id="1902c-184">Известные проблемы в открытом предварительном просмотре</span><span class="sxs-lookup"><span data-stu-id="1902c-184">Known issues in Open Preview</span></span>

<span data-ttu-id="1902c-185">Ниже приведен список известных проблем, которые в настоящее время содержатся в предварительной версии для конференц-связи по сети.</span><span class="sxs-lookup"><span data-stu-id="1902c-185">The following is a list of known issues that are currently present in the Open Preview release of On-network conferencing.</span></span> <span data-ttu-id="1902c-186">Корпорация Майкрософт работает над устранением этих проблем.</span><span class="sxs-lookup"><span data-stu-id="1902c-186">Microsoft is working on addressing these issues.</span></span>

| <span data-ttu-id="1902c-187">Ошибка</span><span class="sxs-lookup"><span data-stu-id="1902c-187">Issue</span></span> | <span data-ttu-id="1902c-188">Смысла</span><span class="sxs-lookup"><span data-stu-id="1902c-188">Workaround</span></span> |
| :--- | :--- |
| <span data-ttu-id="1902c-189">Связь с телефонным подключением с анонимными и скрытым идентификаторами вызывающего абонента, направляемая через сетевую конференцию, не может быть подключена к собранию.</span><span class="sxs-lookup"><span data-stu-id="1902c-189">Dial-in calls with anonymous/hidden caller IDs that are routed through On-network conferencing cannot be connected to the meeting.</span></span> | <span data-ttu-id="1902c-190">Если возможно, настройте конфигурацию на УАТС или SBC, чтобы всегда отправлять идентификатор вызывающего абонента для звонков по сети с помощью сетевой конференции.</span><span class="sxs-lookup"><span data-stu-id="1902c-190">If possible, set a configuration in your PBX or SBC to always send a caller ID for calls routed via On-network conferencing.</span></span>|
| <span data-ttu-id="1902c-191">В некоторых случаях приветственное сообщение, которое воспроизводится пользователям при подключении к службе ("Добро пожаловать в службу голосовой связи..."), обрезается, и пользователи не слышит слово "Добро пожаловать".</span><span class="sxs-lookup"><span data-stu-id="1902c-191">In some cases, the welcome message that is played to users when they dial in to the service (“Welcome to the Audio Conferencing service…”) is truncated and users do not hear the “Welcome” word.</span></span>| <span data-ttu-id="1902c-192">В данный момент временное решение этой проблемы не существует.</span><span class="sxs-lookup"><span data-stu-id="1902c-192">There are no workarounds for this issue at the moment.</span></span> |




## <a name="related-topics"></a><span data-ttu-id="1902c-193">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="1902c-193">Related topics</span></span>


