---
title: Аудиоконференция с прямой маршрутизацией, GCCH и DoD
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
- M365-collaboration
search.appverid: MET150
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
f1.keywords:
- NOCSH
localization_priority: Normal
description: Администратор может узнать, как использовать аудиоконференцию с прямой маршрутизацией в средах GCCH и DoD.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 4daea8636ce99ed711d7fd982cd42eb9aa8c6b93
ms.sourcegitcommit: b39bd1de0219a9e3a3b0c97fc485c9578ddb643c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2021
ms.locfileid: "53230586"
---
# <a name="audio-conferencing-with-direct-routing-for-gcc-high-and-dod"></a><span data-ttu-id="56b74-103">Аудиоконференции с прямой маршрутизацией для GCC High и DoD</span><span class="sxs-lookup"><span data-stu-id="56b74-103">Audio Conferencing with Direct Routing for GCC High and DoD</span></span>

<span data-ttu-id="56b74-104">Аудиоконференция с прямой маршрутизацией для GCC High и DoD позволяет участникам присоединяться к собраниям Teams в организации GCC High или DoD с помощью телефонного устройства.</span><span class="sxs-lookup"><span data-stu-id="56b74-104">Audio Conferencing with Direct Routing for GCC High and DoD enables participants to join Teams meetings in your GCC High or DoD organization by using a phone device.</span></span> <span data-ttu-id="56b74-105">Участники собрания могут использовать телефонное устройство для присоединения к собраниям Teams в таких случаях, как ограниченное подключение к Интернету или когда пользователи находятся в пути и не имеют доступа к Teams.</span><span class="sxs-lookup"><span data-stu-id="56b74-105">Meeting participants might prefer to use a phone device to join Teams meetings in scenarios such as when internet connectivity is limited or when users are on the road and don't have access to Teams.</span></span> <span data-ttu-id="56b74-106">Участники могут присоединяться к собраниям, набрав для вашей организации телефонный номер для телефонного звонка или набрав для собрания телефонный звонок.</span><span class="sxs-lookup"><span data-stu-id="56b74-106">Participants can choose to join meetings by either dialing in to a dial-in phone number for your organization or by having the meeting dial out to their phone device.</span></span>

<span data-ttu-id="56b74-107">Аудиоконференция с прямой маршрутизацией для GCC High и DoD используется в организации в качестве номеров телефонов для телефонного звонка, а все телефонные звонки на телефонные устройства перенаправлены по прямой маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="56b74-107">With Audio Conferencing with Direct Routing for GCC High and DoD, your organization uses its own numbers as dial-in phone numbers and all meeting dial-outs to phone devices are routed via Direct Routing.</span></span> <span data-ttu-id="56b74-108">Чтобы включить службу, организациям необходимо настроить прямую маршрутику и номера телефонов, которые могут использоваться в качестве номеров телефонов для телефонного звонка.</span><span class="sxs-lookup"><span data-stu-id="56b74-108">To enable the service, organizations need to set up Direct Routing and configure phone numbers that can be used as dial-in phone numbers.</span></span> <span data-ttu-id="56b74-109">Требования к прямой маршрутике отличаются от службы аудиоконференций, которая предлагается для организаций, не в которых GCC высокая и не является doD, где телефонные номера для телефонного звонка предоставлены корпорацией Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="56b74-109">The requirement to use Direct Routing is different from the Audio Conferencing service that's offered to non-GCC High and non-DoD organizations where the dial-in phone numbers are provided by Microsoft.</span></span>

## <a name="deploy-audio-conferencing-with-direct-routing-for-gcc-high-and-dod"></a><span data-ttu-id="56b74-110">Развертывание аудиоконференций с прямой маршрутизацией для GCC высокая и doD</span><span class="sxs-lookup"><span data-stu-id="56b74-110">Deploy Audio Conferencing with Direct Routing for GCC High and DoD</span></span>

### <a name="step-1-get-audio-conferencing-with-direct-routing-for-gcc-high-or-dod-licenses"></a><span data-ttu-id="56b74-111">Шаг 1. Получить аудиоконференцию с прямой маршрутизацией для лицензий GCC высокая или DoD</span><span class="sxs-lookup"><span data-stu-id="56b74-111">Step 1: Get Audio Conferencing with Direct Routing for GCC High or DoD licenses</span></span> 

<span data-ttu-id="56b74-112">Чтобы использовать аудиоконференцию в GCC или DoD, вашей организации и пользователям в организации должна быть назначена лицензия на аудиоконференцию с прямой маршрутизацией.</span><span class="sxs-lookup"><span data-stu-id="56b74-112">To use Audio Conferencing in GCC High or DoD, your organization and the users in your organization need to have an Audio Conferencing with Direct Routing license assigned.</span></span> <span data-ttu-id="56b74-113">Вот лицензии, необходимые для того, чтобы включить аудиоконференцию с прямой маршрутизацией для GCC Высокая или DoD.</span><span class="sxs-lookup"><span data-stu-id="56b74-113">Here are the licenses you need to enable Audio Conferencing with Direct Routing for GCC High or DoD.</span></span>

- <span data-ttu-id="56b74-114">GCC Высокая: аудиоконференция — GCC высокого клиента для вашей организации и Аудиоконференция — GCC лицензии для пользователей.</span><span class="sxs-lookup"><span data-stu-id="56b74-114">GCC High: An Audio Conferencing - GCC High Tenant license for your organization and Audio Conferencing - GCC High licenses for your users.</span></span>

- <span data-ttu-id="56b74-115">DoD: аудиоконференция — лицензия клиента DoD для вашей организации и аудиоконференция — лицензии на DoD для пользователей.</span><span class="sxs-lookup"><span data-stu-id="56b74-115">DoD: An Audio Conferencing - DoD Tenant license for your organization and Audio Conferencing - DoD licenses for your users.</span></span>

<span data-ttu-id="56b74-116">Чтобы включить службу, требуются лицензия клиента и хотя бы одна лицензия пользователя.</span><span class="sxs-lookup"><span data-stu-id="56b74-116">A tenant license and at least one user license are required to enable the service.</span></span> <span data-ttu-id="56b74-117">Вы не можете включить службу только с лицензией клиента или только с пользовательскими лицензиями.</span><span class="sxs-lookup"><span data-stu-id="56b74-117">You can't enable the service with only the tenant license or with only user licenses.</span></span> <span data-ttu-id="56b74-118">Чтобы получить лицензии на обслуживание для клиента и пользователей в организации, обратитесь в свою учетную запись.</span><span class="sxs-lookup"><span data-stu-id="56b74-118">To get service licenses for your tenant and the users in your organization, contact your account team.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="56b74-119">Для пользователей нельзя включить аудиоконференцию с прямой маршрутизацией, пока не будут настроены телефонные номера для телефонного звонка.</span><span class="sxs-lookup"><span data-stu-id="56b74-119">Users can't be enabled for Audio Conferencing with Direct Routing until dial-in phone numbers are set up.</span></span> <span data-ttu-id="56b74-120">Мы не рекомендуем назначать пользователям аудиоконференцию с прямой маршрутизацией для лицензий на GCC high или DoD, пока не настроите номера телефонов для телефонного звонка, как описано в этой статье.</span><span class="sxs-lookup"><span data-stu-id="56b74-120">We recommend that you do not assign Audio Conferencing with Direct Routing for GCC High or DoD licenses to users until you set up dial-in phone numbers as outlined in this article.</span></span>  <span data-ttu-id="56b74-121">Невыполнение инструкций может привести к тому, что панель набора номера будет полностью Teams клиенте.</span><span class="sxs-lookup"><span data-stu-id="56b74-121">Failure to follow this guidance may cause the dial pad to be completely missing in the Teams client.</span></span>

### <a name="step-2-set-up-direct-routing"></a><span data-ttu-id="56b74-122">Шаг 2. Настройка прямой маршрутии</span><span class="sxs-lookup"><span data-stu-id="56b74-122">Step 2: Set up Direct Routing</span></span>

<span data-ttu-id="56b74-123">Чтобы настроить прямую маршрутику, см. следующие статьи:</span><span class="sxs-lookup"><span data-stu-id="56b74-123">To set up Direct Routing, see the following articles:</span></span>

- [<span data-ttu-id="56b74-124">Планирование прямой маршрутизации</span><span class="sxs-lookup"><span data-stu-id="56b74-124">Plan Direct Routing</span></span>](direct-routing-plan.md)

- [<span data-ttu-id="56b74-125">Настройка прямой маршрутизации</span><span class="sxs-lookup"><span data-stu-id="56b74-125">Configure Direct Routing</span></span>](direct-routing-configure.md)

> [!NOTE]
> <span data-ttu-id="56b74-126">При настроить прямую маршрутику не забудьте использовать FQDNS и порты для GCC высокой или doD, описанные в этих двух статьях.</span><span class="sxs-lookup"><span data-stu-id="56b74-126">When you set up Direct Routing, remember to use the GCC High or DoD-specific FQDNs and ports that are described in these two articles.</span></span>

### <a name="step-3-set-up-dial-in-phone-numbers"></a><span data-ttu-id="56b74-127">Шаг 3. Настройка номеров телефонов для телефонного звонка</span><span class="sxs-lookup"><span data-stu-id="56b74-127">Step 3: Set up dial-in phone numbers</span></span>

<span data-ttu-id="56b74-128">Номера телефонов для телефонного звонка — это номера телефонов, связанные с мостом аудиоконференции.</span><span class="sxs-lookup"><span data-stu-id="56b74-128">Dial-in phone numbers are the phone numbers that are associated to your Audio Conferencing bridge.</span></span> <span data-ttu-id="56b74-129">Эти числа используются участниками для присоединиться к собраниям, запланированным пользователями в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="56b74-129">These numbers are used by participants to join meetings scheduled by users in your organization.</span></span> <span data-ttu-id="56b74-130">Эти номера также включаются в приглашения на собрания пользователей, план которых будут планировать собрания в вашей организации, и на странице "Поиск местного номера".</span><span class="sxs-lookup"><span data-stu-id="56b74-130">These numbers are also included in the meeting invites of the users who schedule meetings in your organization and on the "Find a local number" page.</span></span>

#### <a name="define-service-phone-numbers-in-your-tenant"></a><span data-ttu-id="56b74-131">Определение номеров телефонов службы в клиенте</span><span class="sxs-lookup"><span data-stu-id="56b74-131">Define service phone numbers in your tenant</span></span>

<span data-ttu-id="56b74-132">С помощью нового-csHybridTelephoneNumber PowerShell вы можете определить номера телефонов служб в клиенте, которые можно использовать для маршрутинга звонков в службу аудиоконференций с помощью прямой маршрутики.</span><span class="sxs-lookup"><span data-stu-id="56b74-132">You can use the New-csHybridTelephoneNumber PowerShell cmdlet to define service phone numbers in your tenant that can be used to route calls to the Audio Conferencing service via Direct Routing.</span></span> 

  ```PowerShell
  New-csHybridTelephoneNumber -TelephoneNumber <Phone number in E.164 format>
  ```

<span data-ttu-id="56b74-133">Например:</span><span class="sxs-lookup"><span data-stu-id="56b74-133">For example:</span></span>
  ```PowerShell
  New-csHybridTelephoneNumber -TelephoneNumber "+14250000000"
  ```

#### <a name="assign-the-service-phone-numbers-to-the-audio-conferencing-bridge-of-your-organization"></a><span data-ttu-id="56b74-134">Назначение номеров телефонов службы мосту аудиоконференций организации</span><span class="sxs-lookup"><span data-stu-id="56b74-134">Assign the service phone numbers to the Audio Conferencing bridge of your organization</span></span>

<span data-ttu-id="56b74-135">Вы можете назначить номера телефонов службы мосту аудиоконференции вашей организации с помощью cmdlet Register-csOnlineDialInConferencingServiceNumber PowerShell.</span><span class="sxs-lookup"><span data-stu-id="56b74-135">You can assign service phone numbers to the Audio Conferencing bridge of your organization by using the Register-csOnlineDialInConferencingServiceNumber PowerShell cmdlet.</span></span>

  ```PowerShell
  Register-csOnlineDialInConferencingServiceNumber -identity <Telephone number in E.164 format> -BridgeId <Identity of the audio conferencing bridge>
  ```

<span data-ttu-id="56b74-136">Вы можете посмотреть ИД моста аудиоконференции с помощью Get-CsOnlineDialInConferencingBridge.</span><span class="sxs-lookup"><span data-stu-id="56b74-136">You can see the ID of your Audio Conferencing Bridge using Get-CsOnlineDialInConferencingBridge.</span></span> <span data-ttu-id="56b74-137">Например:</span><span class="sxs-lookup"><span data-stu-id="56b74-137">For example:</span></span>

  ```PowerShell
  $b= Get-CsOnlineDialInConferencingBridge
  Register-csOnlineDialInConferencingServiceNumber -identity 14257048060 -BridgeId $b.identity
  ```


### <a name="step-4-define-a-global-voice-routing-policy-to-enable-the-routing-of-outbound-calls-from-meetings"></a><span data-ttu-id="56b74-138">Шаг 4. Определение глобальной политики маршрутинга голосовой почты, которая позволяет маршрутизовы исходящие звонки из собраний</span><span class="sxs-lookup"><span data-stu-id="56b74-138">Step 4: Define a global voice routing policy to enable the routing of outbound calls from meetings</span></span>

<span data-ttu-id="56b74-139">Маршрутизировка исходящие вызовы через STN из собраний, организованных пользователями в организации, определяется глобальной политикой маршрутизации голосовой почты вашей организации.</span><span class="sxs-lookup"><span data-stu-id="56b74-139">The routing of outbound calls that are made to the PSTN from meetings organized by users in your organization is defined by the global voice routing policy of your organization.</span></span> <span data-ttu-id="56b74-140">Если в вашей организации определена глобальная политика маршрутизации голосовой почты, убедитесь в том, что глобальная политика маршрутизации голосовой почты разрешает исходящие звонки на STN, которые должны инициироваться на собраниях, организованных пользователями в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="56b74-140">If your organization has a global voice routing policy defined, please verify that the global voice routing policy allows the outbound calls to the PSTN that are expected to be initiated from meetings organized by users in your organization.</span></span> <span data-ttu-id="56b74-141">Если в вашей организации не определена глобальная политика маршрутизации голосовой почты, необходимо определить ее, чтобы включить маршрутику исходяющих звонков по STN из собраний, организованных пользователями в организации.</span><span class="sxs-lookup"><span data-stu-id="56b74-141">If your organization doesn’t have a global voice routing policy defined, you will need to define one to enable the routing of outbound calls to the PSTN from meetings organized by users in your organization.</span></span> <span data-ttu-id="56b74-142">Обратите внимание на то, что глобальная политика маршрутизации голосовой почты вашей организации также применяется к звонкам один к одному, сделанным пользователями вашей организации в ОКП.</span><span class="sxs-lookup"><span data-stu-id="56b74-142">Please note that the global voice routing policy of your organization also applies to one-to-one calls made to the PSTN by users in your organization.</span></span> <span data-ttu-id="56b74-143">Если для пользователей в вашей организации включена возможность звонков по STN один-к-одному, убедитесь, что глобальная политика маршрутизации голосовой почты соответствует потребностям организации для обоих типов звонков.</span><span class="sxs-lookup"><span data-stu-id="56b74-143">If one-to-one calls to the PSTN are enabled for users in your organization, make sure that the global voice routing policy meets the needs of your organization for both types of calls.</span></span> 

> [!NOTE]
> <span data-ttu-id="56b74-144">Location-Based маршруты недоступны в Microsoft 365 облако сообщества для государственных организаций (GCC) high или DoD.</span><span class="sxs-lookup"><span data-stu-id="56b74-144">Location-Based Routing isn't available in Microsoft 365 Government Community Cloud (GCC) High or DoD deployments.</span></span> <span data-ttu-id="56b74-145">Включив аудиоконференцию, убедитесь, что для пользователей аудиоконференции в GCC высокая или doD не включена Location-Based маршрутизацию.</span><span class="sxs-lookup"><span data-stu-id="56b74-145">When enabling Audio Conferencing, please verify that no Audio Conferencing users in the GCC High or the DoD environments are enabled for Location-Based Routing.</span></span>

#### <a name="defining-a-global-voice-routing-policy"></a><span data-ttu-id="56b74-146">Определение глобальной политики маршрутинга голосовой почты</span><span class="sxs-lookup"><span data-stu-id="56b74-146">Defining a global voice routing policy</span></span>

<span data-ttu-id="56b74-147">Глобальную политику маршрутизации голосовой почты можно определить, определив использование STN, голосовой маршрут, политику голосовой маршрутизации и назначив новую политику маршрутизации голосовой почты глобальной политикой маршрутизации голосовой почты вашей организации.</span><span class="sxs-lookup"><span data-stu-id="56b74-147">A global voice routing policy can be defined by defining a PSTN usage, a voice route, a voice routing policy, and assigning the new voice routing policy as the global voice routing policy of your organization.</span></span>

<span data-ttu-id="56b74-148">Ниже описано, как определить новую глобальную политику маршрутизации голосовой почты для организации без нее.</span><span class="sxs-lookup"><span data-stu-id="56b74-148">The following steps describe how to define a new global voice routing policy for an organization without one.</span></span> <span data-ttu-id="56b74-149">Если в вашей организации уже определены политики маршрутизации голосовой связи, убедитесь, что следующая конфигурация не конфликтует с существующими политиками маршрутизации голосовой связи в организации.</span><span class="sxs-lookup"><span data-stu-id="56b74-149">If your organization already has voice routing policies defined, verify that the following configuration doesn’t conflict with the existing voice routing policies of your organization.</span></span>

<span data-ttu-id="56b74-150">Чтобы создать новую функцию использования ОКП в удаленном сеансе PowerShell в Skype для бизнеса Online, используйте следующую команду:</span><span class="sxs-lookup"><span data-stu-id="56b74-150">To create a new PSTN usage in a remote PowerShell session in Skype for Business Online, use the following command:</span></span>

  ```PowerShell
  Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="International"}
  ```

<span data-ttu-id="56b74-151">Дополнительные сведения [см. в настройках Set-CsOnlinePstnUsage.](/powershell/module/skype/set-csonlinepstnusage)</span><span class="sxs-lookup"><span data-stu-id="56b74-151">For additional information, see [Set-CsOnlinePstnUsage](/powershell/module/skype/set-csonlinepstnusage).</span></span>

<span data-ttu-id="56b74-152">Чтобы создать новый голосовой маршрут, используйте следующую команду:</span><span class="sxs-lookup"><span data-stu-id="56b74-152">To create a new voice route, use the following command:</span></span>

  ```PowerShell
  New-CsOnlineVoiceRoute -Identity "International" -NumberPattern ".*" -OnlinePstnGatewayList sbc1.contoso.biz -OnlinePstnUsages "International"
  ```

<span data-ttu-id="56b74-153">При определении нового голосового маршрута для организации укажите один или несколько шлюзов ПСДН, определенных для организации при настройке прямой маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="56b74-153">When defining a new voice route for your organization, please specify one or multiple of the PSTN online PSTN gateways that have been defined for your organization during the configuration of Direct Routing.</span></span> 

<span data-ttu-id="56b74-154">Шаблон номера определяет, какие звонки будут перенаправлены через указанный список шлюзов в зависимости от номера конечного телефона.</span><span class="sxs-lookup"><span data-stu-id="56b74-154">The number pattern specifies which calls will be routed through the specified list of gateways based on the destination phone number of the call.</span></span> <span data-ttu-id="56b74-155">В примере выше звонки в любую точку мира будут соответствовать голосовой маршрут.</span><span class="sxs-lookup"><span data-stu-id="56b74-155">In the example above, calls to any destinations in the world will match the voice route.</span></span> <span data-ttu-id="56b74-156">Если вы хотите ограничить набор телефонных номеров с собраний пользователей в вашей организации, вы можете изменить шаблон номера таким образом, чтобы голосовой маршрут совпадал только с шаблонами номеров в разрешенных назначениях.</span><span class="sxs-lookup"><span data-stu-id="56b74-156">If you would like to restrict the phone numbers that can be dialed from the meetings of users in your organization, you can change the number pattern to have the voice route match only the number patterns of the destinations allowed.</span></span> <span data-ttu-id="56b74-157">Обратите внимание, что если не существует голосовых маршрутов, которые соответствуют шаблону номера конечного телефона для данного звонка, звонок не будет перенаправлен.</span><span class="sxs-lookup"><span data-stu-id="56b74-157">Please note that if there are no voice routes that match the number pattern of the destination phone number of a given call, the call will not be routed.</span></span>

<span data-ttu-id="56b74-158">Дополнительные сведения см. [в new-CsOnlineVoiceRoute.](/powershell/module/skype/new-csonlinevoiceroute)</span><span class="sxs-lookup"><span data-stu-id="56b74-158">For additional information, see [New-CsOnlineVoiceRoute](/powershell/module/skype/new-csonlinevoiceroute).</span></span>

<span data-ttu-id="56b74-159">Чтобы создать политику маршрутинга голосовой почты, используйте следующую команду:</span><span class="sxs-lookup"><span data-stu-id="56b74-159">To create a new voice routing policy, use the following command:</span></span>

  ```PowerShell
  New-CsOnlineVoiceRoutingPolicy "InternationalVoiceRoutingPolicy" -OnlinePstnUsages "International"
  ```

<span data-ttu-id="56b74-160">Если в политике перенастройки голосовой маршрутии определено несколько вариантов использования ОКП, они оцениваются в том порядке, в котором они определены.</span><span class="sxs-lookup"><span data-stu-id="56b74-160">If multiple PSTN usages are being defined in the voice routing policy, they will be evaluated in the order in which they are defined.</span></span> <span data-ttu-id="56b74-161">Рекомендуется определить использование услуг STN в порядке определения наиболее общих с точки зрения шаблонов номеров голосовых маршрутов, связанных с использованием ОКП.</span><span class="sxs-lookup"><span data-stu-id="56b74-161">It is recommended that the PSTN usages are defined in the order of the most specific to the more generic in terms of the number patterns of the voice routes associated with the PSTN usages.</span></span> <span data-ttu-id="56b74-162">Например, если для перенастройки звонков в США было определено использование ЗВОНКОВ через ОКП, а для перенастройки звонков в любое другое место в мире — другое, в политике голосовой маршрутиации перед использованием ЗВОНКОВ по ННП следует устюгов в политике голосовой маршрутиации перенапорять звонки в любое другое место в мире.</span><span class="sxs-lookup"><span data-stu-id="56b74-162">For example, if a PSTN usage was defined to route calls to the United States, and another PSTN usage was defined to route calls to any other location in the world, the PSTN usage for calls to the United States should be listed in the voice routing policy ahead of the PSTN usage to route calls to any other location in the world.</span></span>

<span data-ttu-id="56b74-163">Дополнительные сведения см. [в new-CsOnlineVoiceRoutingPolicy.](/powershell/module/skype/new-csonlinevoiceroutingpolicy)</span><span class="sxs-lookup"><span data-stu-id="56b74-163">For additional information, see [New-CsOnlineVoiceRoutingPolicy](/powershell/module/skype/new-csonlinevoiceroutingpolicy).</span></span>

<span data-ttu-id="56b74-164">Чтобы назначить новый голосовой маршрут глобальной политике маршрутизации голосовой почты вашей организации, используйте следующую команду:</span><span class="sxs-lookup"><span data-stu-id="56b74-164">To assign the new voice route to the global voice routing policy of your organization, use the following command:</span></span>

  ```PowerShell
  Grant-CsOnlineVoiceRoutingPolicy -PolicyName "InternationalVoiceRoutingPolicy" -Global
  ```

<span data-ttu-id="56b74-165">Дополнительные сведения [см. в теме Grant-CsOnlineVoiceRoutingPolicy.](/powershell/module/skype/grant-csonlinevoiceroutingpolicy)</span><span class="sxs-lookup"><span data-stu-id="56b74-165">For additional information, see [Grant-CsOnlineVoiceRoutingPolicy](/powershell/module/skype/grant-csonlinevoiceroutingpolicy).</span></span>

<span data-ttu-id="56b74-166">После определения глобальной политики маршрутизации голосовой связи все исходящие звонки, исходящие из собраний, организованных пользователями в вашей организации, будут оцениваться в зависимости от голосовых маршрутов, связанных с использованием услуг ЗВОНКОВ по STN глобальной политики маршрутизации голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="56b74-166">Once the global voice routing policy has been defined, any outbound calls made from meetings organized by users in your organization will be evaluated against the voice routes associated to the PSTN usages of the global voice routing policy.</span></span> <span data-ttu-id="56b74-167">Исходящие звонки будут маршрутизовы в соответствии с первым голосовым маршрутом, который соответствует шаблону набора номера.</span><span class="sxs-lookup"><span data-stu-id="56b74-167">The outbound calls will be routed according to the first voice route that matches the number pattern of the dialed phone number.</span></span>

### <a name="step-5-assign-audio-conferencing-with-direct-routing-for-gcc-high-or-dod-licenses-to-your-users"></a><span data-ttu-id="56b74-168">Шаг 5. Назначение пользователям лицензий на аудиоконференцию с прямой маршрутизацией для GCC высокая или doD-лицензия</span><span class="sxs-lookup"><span data-stu-id="56b74-168">Step 5: Assign Audio Conferencing with Direct Routing for GCC High or DoD licenses to your users</span></span>

<span data-ttu-id="56b74-169">Чтобы назначить пользователю аудиоконференцию с прямой маршрутизацией для лицензий на GCC high или DoD, см. назначение [лицензий пользователям.](/microsoft-365/admin/manage/assign-licenses-to-users)</span><span class="sxs-lookup"><span data-stu-id="56b74-169">To assign Audio Conferencing with Direct Routing for GCC High or DoD licenses to your user, see [Assign licenses to users](/microsoft-365/admin/manage/assign-licenses-to-users).</span></span>

### <a name="step-6-optional-see-a-list-of-audio-conferencing-numbers-in-teams"></a><span data-ttu-id="56b74-170">Шаг 6. (Необязательно) Просмотр списка номеров для аудиоконференций в Teams</span><span class="sxs-lookup"><span data-stu-id="56b74-170">Step 6: (Optional) See a list of Audio Conferencing numbers in Teams</span></span>

<span data-ttu-id="56b74-171">Список номеров для аудиоконференций организации см. в [Microsoft Teams.](see-a-list-of-audio-conferencing-numbers-in-teams.md)</span><span class="sxs-lookup"><span data-stu-id="56b74-171">To see the list of Audio Conferencing numbers of your organization, go to [See a list of Audio Conferencing numbers in Microsoft Teams](see-a-list-of-audio-conferencing-numbers-in-teams.md).</span></span>

### <a name="step-7-optional-set-auto-attendant-languages-for-the-audio-conferencing-dial-in-numbers-of-you-organization"></a><span data-ttu-id="56b74-172">Шаг 7. (Необязательно) Настройка языков автоотединения для номеров для телефонного набора аудиоконференций вашей организации</span><span class="sxs-lookup"><span data-stu-id="56b74-172">Step 7: (Optional) Set auto attendant languages for the Audio Conferencing dial-in numbers of you organization</span></span>

<span data-ttu-id="56b74-173">Чтобы изменить языки телефонных номеров для аудиоконференций в организации, см. в этой [Microsoft Teams.](set-auto-attendant-languages-for-audio-conferencing-in-teams.md)</span><span class="sxs-lookup"><span data-stu-id="56b74-173">To change the languages of the Audio Conferencing dial-in numbers of your organization, see [Set auto attendant languages for Audio Conferencing in Microsoft Teams](set-auto-attendant-languages-for-audio-conferencing-in-teams.md).</span></span>

### <a name="step-8-optional-change-the-settings-of-the-audio-conferencing-bridge-of-your-organization"></a><span data-ttu-id="56b74-174">Шаг 8. Изменение параметров моста аудиоконференций организации (необязательно)</span><span class="sxs-lookup"><span data-stu-id="56b74-174">Step 8: (Optional) Change the settings of the Audio Conferencing bridge of your organization</span></span>

<span data-ttu-id="56b74-175">Чтобы изменить параметры моста аудиоконференций в организации, см. статью Изменение параметров моста [аудиоконференций.](change-the-settings-for-an-audio-conferencing-bridge.md)</span><span class="sxs-lookup"><span data-stu-id="56b74-175">To change the settings of the Audio Conferencing bridge of your organization, see [Change the settings for an Audio Conferencing bridge](change-the-settings-for-an-audio-conferencing-bridge.md).</span></span>

### <a name="step-9-optional-set-the-phone-numbers-included-in-the-meeting-invites-of-the-users-in-your-organization"></a><span data-ttu-id="56b74-176">Шаг 9. (Необязательно) Настройка телефонных номеров, включенных в приглашения на собрания пользователей в организации</span><span class="sxs-lookup"><span data-stu-id="56b74-176">Step 9: (Optional) Set the phone numbers included in the meeting invites of the users in your organization</span></span>

<span data-ttu-id="56b74-177">Чтобы изменить набор номеров телефонов, включенных в приглашения на собрания пользователей, является ваша организация, см. в этой [Microsoft Teams.](set-the-phone-numbers-included-on-invites-in-teams.md)</span><span class="sxs-lookup"><span data-stu-id="56b74-177">To change the set of phone numbers that are included in the meeting invites of the users is your organization, see [Set the phone numbers included on invites in Microsoft Teams](set-the-phone-numbers-included-on-invites-in-teams.md).</span></span>

## <a name="audio-conferencing-capabilities-not-supported-in-audio-conferencing-with-direct-routing-for-gcc-high-and-dod"></a><span data-ttu-id="56b74-178">Возможности аудиоконференций, не поддерживаемые в аудиоконференциях с прямой маршрутизацией для GCC High и DoD</span><span class="sxs-lookup"><span data-stu-id="56b74-178">Audio Conferencing capabilities not supported in Audio Conferencing with Direct Routing for GCC High and DoD</span></span>

<span data-ttu-id="56b74-179">Ниже 2010 г. ниже 2010 г. поддерживаются возможности аудиоконференции, которые не поддерживаются в аудиоконференциях с прямой маршрутизацией для GCC High и DoD.</span><span class="sxs-lookup"><span data-stu-id="56b74-179">The following are Audio Conferencing capabilities that are not supported in Audio Conferencing with Direct Routing for GCC High and DoD:</span></span>

- <span data-ttu-id="56b74-180">Уведомления о входе и выходе с помощью записи имени.</span><span class="sxs-lookup"><span data-stu-id="56b74-180">Entry and exit notifications using name recording.</span></span> <span data-ttu-id="56b74-181">Для аудиоконференации с прямой маршрутизацией уведомления о входе и выходе на собрание будут заимещены в тонах.</span><span class="sxs-lookup"><span data-stu-id="56b74-181">For Audio Conferencing with Direct Routing, entry and exit notifications are played in the meeting as tones.</span></span>

- <span data-ttu-id="56b74-182">Отключать использование бесплатных номеров для определенных организаторов собраний.</span><span class="sxs-lookup"><span data-stu-id="56b74-182">Disable the usage of toll-free numbers for the meetings specific organizer.</span></span> <span data-ttu-id="56b74-183">Элементы управления на уровне пользователей, ограничивающие использование бесплатных номеров для звонков в организации, не применимы к звонкам, перенаправимым по прямой маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="56b74-183">User-level controls to restrict the usage of toll-free numbers to join the meetings of your organization aren't applicable to calls routed via Direct Routing.</span></span>

- <span data-ttu-id="56b74-184">Отправка уведомлений пользователям при изменении их параметров.</span><span class="sxs-lookup"><span data-stu-id="56b74-184">Sending notification emails to users when their settings change.</span></span> <span data-ttu-id="56b74-185">Сообщения электронной почты с уведомлениями о аудиоконференции не поддерживаются для аудиоконференций с прямой маршрутизацией для GCC Высокая и DoD.</span><span class="sxs-lookup"><span data-stu-id="56b74-185">Audio Conferencing notification emails aren't supported for Audio Conferencing with Direct Routing for GCC High and DoD.</span></span>
