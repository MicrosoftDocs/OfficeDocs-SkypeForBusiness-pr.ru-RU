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
ms.openlocfilehash: 577a9fe106cb5dae23049404b54433288e350b78
ms.sourcegitcommit: bd7847de9d1402476f8faaeae2ff97ec60d86a1b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/26/2021
ms.locfileid: "51262624"
---
# <a name="audio-conferencing-with-direct-routing-for-gcc-high-and-dod"></a><span data-ttu-id="61168-103">Аудиоконференции с прямой маршрутизацией для GCC High и DoD</span><span class="sxs-lookup"><span data-stu-id="61168-103">Audio Conferencing with Direct Routing for GCC High and DoD</span></span>

<span data-ttu-id="61168-104">Аудиоконференция с прямой маршрутизацией для GCC High и DoD позволяет участникам присоединяться к собраниям Teams в организации GCC High или DoD с помощью телефонного устройства.</span><span class="sxs-lookup"><span data-stu-id="61168-104">Audio Conferencing with Direct Routing for GCC High and DoD enables participants to join Teams meetings in your GCC High or DoD organization by using a phone device.</span></span> <span data-ttu-id="61168-105">Участники собрания могут использовать телефонное устройство для присоединения к собраниям Teams в таких сценариях, как ограничение подключения к Интернету или когда пользователи находятся в пути и не имеют доступа к Teams.</span><span class="sxs-lookup"><span data-stu-id="61168-105">Meeting participants might prefer to use a phone device to join Teams meetings in scenarios such as when internet connectivity is limited or when users are on the road and don't have access to Teams.</span></span> <span data-ttu-id="61168-106">Участники могут присоединиться к собранию, набрав для организации телефонный номер для телефонного звонка или набрав звонок на свое телефонное устройство.</span><span class="sxs-lookup"><span data-stu-id="61168-106">Participants can choose to join meetings by either dialing in to a dial-in phone number for your organization or by having the meeting dial out to their phone device.</span></span>

<span data-ttu-id="61168-107">При аудиоконференции с прямой маршрутизацией для GCC High и DoD ваша организация использует собственные номера в качестве телефонных номеров для телефонного звонка, а все телефонные звонки на телефонные устройства перенаправляются через прямую маршрутизацию.</span><span class="sxs-lookup"><span data-stu-id="61168-107">With Audio Conferencing with Direct Routing for GCC High and DoD, your organization uses its own numbers as dial-in phone numbers and all meeting dial-outs to phone devices are routed via Direct Routing.</span></span> <span data-ttu-id="61168-108">Чтобы включить службу, организациям необходимо настроить прямую маршрутику и настроить номера телефонов, которые могут использоваться в качестве номеров телефонов для телефонного звонка.</span><span class="sxs-lookup"><span data-stu-id="61168-108">To enable the service, organizations need to set up Direct Routing and configure phone numbers that can be used as dial-in phone numbers.</span></span> <span data-ttu-id="61168-109">Требования к прямой маршрутизаке отличаются от службы аудиоконференций, предлагаемых для организаций, не в которых используется GCC High, и без DoD, где телефонные номера телефонов предоставляются корпорацией Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="61168-109">The requirement to use Direct Routing is different from the Audio Conferencing service that's offered to non-GCC High and non-DoD organizations where the dial-in phone numbers are provided by Microsoft.</span></span>

## <a name="deploy-audio-conferencing-with-direct-routing-for-gcc-high-and-dod"></a><span data-ttu-id="61168-110">Развертывание аудиоконференций с прямой маршрутизацией для GCC High и DoD</span><span class="sxs-lookup"><span data-stu-id="61168-110">Deploy Audio Conferencing with Direct Routing for GCC High and DoD</span></span>

### <a name="step-1-get-audio-conferencing-with-direct-routing-for-gcc-high-or-dod-licenses"></a><span data-ttu-id="61168-111">Шаг 1. Аудиоконференция с прямой маршрутизацией для лицензий GCC High или DoD</span><span class="sxs-lookup"><span data-stu-id="61168-111">Step 1: Get Audio Conferencing with Direct Routing for GCC High or DoD licenses</span></span> 

<span data-ttu-id="61168-112">Чтобы использовать аудиоконференцию в GCC High или DoD, вашей организации и пользователям в организации должна быть назначена лицензия на прямой маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="61168-112">To use Audio Conferencing in GCC High or DoD, your organization and the users in your organization need to have an Audio Conferencing with Direct Routing license assigned.</span></span> <span data-ttu-id="61168-113">Ниже писались лицензии, необходимые для того, чтобы включить аудиоконференцию с прямой маршрутизацией для GCC High или DoD.</span><span class="sxs-lookup"><span data-stu-id="61168-113">Here are the licenses you need to enable Audio Conferencing with Direct Routing for GCC High or DoD.</span></span>

- <span data-ttu-id="61168-114">GCC High: лицензии на аудиоконференцию с высоким клиентом GCC для вашей организации и аудиоконференцию с высоким разрешением GCC для пользователей.</span><span class="sxs-lookup"><span data-stu-id="61168-114">GCC High: An Audio Conferencing - GCC High Tenant license for your organization and Audio Conferencing - GCC High licenses for your users.</span></span>

- <span data-ttu-id="61168-115">DoD: аудиоконференция — лицензия клиента DoD для вашей организации и аудиоконференция — лицензии doD для пользователей.</span><span class="sxs-lookup"><span data-stu-id="61168-115">DoD: An Audio Conferencing - DoD Tenant license for your organization and Audio Conferencing - DoD licenses for your users.</span></span>

<span data-ttu-id="61168-116">Чтобы включить службу, требуются лицензия клиента и хотя бы одна лицензия пользователя.</span><span class="sxs-lookup"><span data-stu-id="61168-116">A tenant license and at least one user license are required to enable the service.</span></span> <span data-ttu-id="61168-117">Службу нельзя включить только с лицензией клиента или только с пользовательскими лицензиями.</span><span class="sxs-lookup"><span data-stu-id="61168-117">You can't enable the service with only the tenant license or with only user licenses.</span></span> <span data-ttu-id="61168-118">Чтобы получить лицензии на обслуживание для клиента и пользователей в организации, обратитесь к своей группе учетных записей.</span><span class="sxs-lookup"><span data-stu-id="61168-118">To get service licenses for your tenant and the users in your organization, contact your account team.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="61168-119">Пользователям нельзя включить аудиоконференцию с прямой маршрутизацией, пока не будут настроены телефонные номера для телефонного звонка.</span><span class="sxs-lookup"><span data-stu-id="61168-119">Users can't be enabled for Audio Conferencing with Direct Routing until dial-in phone numbers are set up.</span></span> <span data-ttu-id="61168-120">Мы рекомендуем не назначать пользователям аудиоконференцию с прямой маршрутизацией лицензий GCC High или DoD, пока не настроите номера телефонов для телефонного звонка, как описано в этой статье.</span><span class="sxs-lookup"><span data-stu-id="61168-120">We recommend that you do not assign Audio Conferencing with Direct Routing for GCC High or DoD licenses to users until you set up dial-in phone numbers as outlined in this article.</span></span>  <span data-ttu-id="61168-121">Невыполнение инструкций может привести к тому, что панель набора номера будет полностью пропущена в клиенте Teams.</span><span class="sxs-lookup"><span data-stu-id="61168-121">Failure to follow this guidance may cause the dial pad to be completely missing in the Teams client.</span></span>

### <a name="step-2-set-up-direct-routing"></a><span data-ttu-id="61168-122">Шаг 2. Настройка прямой маршрутии</span><span class="sxs-lookup"><span data-stu-id="61168-122">Step 2: Set up Direct Routing</span></span>

<span data-ttu-id="61168-123">Чтобы настроить прямую маршрутику, см. следующие статьи:</span><span class="sxs-lookup"><span data-stu-id="61168-123">To set up Direct Routing, see the following articles:</span></span>

- [<span data-ttu-id="61168-124">Планирование прямой маршрутизации</span><span class="sxs-lookup"><span data-stu-id="61168-124">Plan Direct Routing</span></span>](direct-routing-plan.md)

- [<span data-ttu-id="61168-125">Настройка прямой маршрутизации</span><span class="sxs-lookup"><span data-stu-id="61168-125">Configure Direct Routing</span></span>](direct-routing-configure.md)

> [!NOTE]
> <span data-ttu-id="61168-126">При настроить прямую маршрутику не забудьте использовать FQDD и порты для GCC High или DoD, описанные в этих двух статьях.</span><span class="sxs-lookup"><span data-stu-id="61168-126">When you set up Direct Routing, remember to use the GCC High or DoD-specific FQDNs and ports that are described in these two articles.</span></span>

### <a name="step-3-set-up-dial-in-phone-numbers"></a><span data-ttu-id="61168-127">Шаг 3. Настройка номеров телефонов для телефонного звонка</span><span class="sxs-lookup"><span data-stu-id="61168-127">Step 3: Set up dial-in phone numbers</span></span>

<span data-ttu-id="61168-128">Номера телефонов для телефонного звонка — это номера телефонов, связанные с мостом аудиоконференции.</span><span class="sxs-lookup"><span data-stu-id="61168-128">Dial-in phone numbers are the phone numbers that are associated to your Audio Conferencing bridge.</span></span> <span data-ttu-id="61168-129">Эти номера используются участниками для присоединиться к собраниям, запланированным пользователями в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="61168-129">These numbers are used by participants to join meetings scheduled by users in your organization.</span></span> <span data-ttu-id="61168-130">Эти номера также включаются в приглашения на собрания для пользователей, планвших собрания в вашей организации и на странице "Поиск местного номера".</span><span class="sxs-lookup"><span data-stu-id="61168-130">These numbers are also included in the meeting invites of the users who schedule meetings in your organization and on the "Find a local number" page.</span></span>

#### <a name="define-service-phone-numbers-in-your-tenant"></a><span data-ttu-id="61168-131">Определение номеров телефонов служб в клиенте</span><span class="sxs-lookup"><span data-stu-id="61168-131">Define service phone numbers in your tenant</span></span>

<span data-ttu-id="61168-132">Для определения номеров телефонов служб в клиенте, которые можно использовать для перенаправки звонков в службу аудиоконференции с помощью Прямой маршрутики, можно использовать новый для CsHybridTelephoneNumber PowerShell.</span><span class="sxs-lookup"><span data-stu-id="61168-132">You can use the New-csHybridTelephoneNumber PowerShell cmdlet to define service phone numbers in your tenant that can be used to route calls to the Audio Conferencing service via Direct Routing.</span></span> 

  ```PowerShell
  New-csHybridTelephoneNumber -TelephoneNumber <Phone number in E.164 format>
  ```

<span data-ttu-id="61168-133">Например:</span><span class="sxs-lookup"><span data-stu-id="61168-133">For example:</span></span>
  ```PowerShell
  New-csHybridTelephoneNumber -TelephoneNumber "+14250000000"
  ```

#### <a name="assign-the-service-phone-numbers-to-the-audio-conferencing-bridge-of-your-organization"></a><span data-ttu-id="61168-134">Назначение номеров телефонов службы мосту аудиоконференции вашей организации</span><span class="sxs-lookup"><span data-stu-id="61168-134">Assign the service phone numbers to the Audio Conferencing bridge of your organization</span></span>

<span data-ttu-id="61168-135">Вы можете назначить номера телефонов службы мосту аудиоконференции вашей организации с помощью cmdlet Register-csOnlineDialInConferencingServiceNumber PowerShell.</span><span class="sxs-lookup"><span data-stu-id="61168-135">You can assign service phone numbers to the Audio Conferencing bridge of your organization by using the Register-csOnlineDialInConferencingServiceNumber PowerShell cmdlet.</span></span>

  ```PowerShell
  Register-csOnlineDialInConferencingServiceNumber -identity <Telephone number in E.164 format> -BridgeId <Identity of the audio conferencing bridge>
  ```

<span data-ttu-id="61168-136">Вы можете узнать ИД моста аудиоконференции с помощью Get-CsOnlineDialInConferencingBridge.</span><span class="sxs-lookup"><span data-stu-id="61168-136">You can see the ID of your Audio Conferencing Bridge using Get-CsOnlineDialInConferencingBridge.</span></span> <span data-ttu-id="61168-137">Например:</span><span class="sxs-lookup"><span data-stu-id="61168-137">For example:</span></span>

  ```PowerShell
  $b= Get-CsOnlineDialInConferencingBridge
  Register-csOnlineDialInConferencingServiceNumber -identity 14257048060 -BridgeId $b.identity
  ```


### <a name="step-4-define-a-global-voice-routing-policy-to-enable-the-routing-of-outbound-calls-from-meetings"></a><span data-ttu-id="61168-138">Шаг 4. Определение глобальной политики маршрутинга голосовой почты для обеспечения маршрутинга исходяющих звонков из собраний</span><span class="sxs-lookup"><span data-stu-id="61168-138">Step 4: Define a global voice routing policy to enable the routing of outbound calls from meetings</span></span>

<span data-ttu-id="61168-139">Маршрутка исходящие вызовы по STN из собраний, организованных пользователями в организации, определяется глобальной политикой маршрутизации голосовой почты вашей организации.</span><span class="sxs-lookup"><span data-stu-id="61168-139">The routing of outbound calls that are made to the PSTN from meetings organized by users in your organization is defined by the global voice routing policy of your organization.</span></span> <span data-ttu-id="61168-140">Если в вашей организации определена глобальная политика маршрутизации голосовой почты, убедитесь, что глобальная политика маршрутизации голосовой почты позволяет исходящие вызовы по STN, которые должны инициироваться пользователями в организации.</span><span class="sxs-lookup"><span data-stu-id="61168-140">If your organization has a global voice routing policy defined, please verify that the global voice routing policy allows the outbound calls to the PSTN that are expected to be initiated from meetings organized by users in your organization.</span></span> <span data-ttu-id="61168-141">Если в вашей организации не определена глобальная политика маршрутизации голосовой почты, необходимо определить ее, чтобы включить маршрутику исходяющих звонков по ДНР из собраний, организованных пользователями в организации.</span><span class="sxs-lookup"><span data-stu-id="61168-141">If your organization doesn’t have a global voice routing policy defined, you will need to define one to enable the routing of outbound calls to the PSTN from meetings organized by users in your organization.</span></span> <span data-ttu-id="61168-142">Обратите внимание, что глобальная политика маршрутизации голосовой почты вашей организации также применяется к звонкам ЗВОНКОВ по ПС, сделанным пользователями в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="61168-142">Please note that the global voice routing policy of your organization also applies to one-to-one calls made to the PSTN by users in your organization.</span></span> <span data-ttu-id="61168-143">Если для пользователей в вашей организации включены звонков по ННР, убедитесь, что глобальная политика маршрутизации голосовой почты соответствует потребностям организации для обоих типов звонков.</span><span class="sxs-lookup"><span data-stu-id="61168-143">If one-to-one calls to the PSTN are enabled for users in your organization, make sure that the global voice routing policy meets the needs of your organization for both types of calls.</span></span> 

> [!NOTE]
> <span data-ttu-id="61168-144">Location-Based маршруты недоступны в развертываниях Microsoft 365 Government Community Cloud (GCC) High или DoD.</span><span class="sxs-lookup"><span data-stu-id="61168-144">Location-Based Routing isn't available in Microsoft 365 Government Community Cloud (GCC) High or DoD deployments.</span></span> <span data-ttu-id="61168-145">Включив аудиоконференцию, убедитесь, что для пользователей аудиоконференции в среде GCC High или DoD не включена Location-Based маршрутизацией.</span><span class="sxs-lookup"><span data-stu-id="61168-145">When enabling Audio Conferencing, please verify that no Audio Conferencing users in the GCC High or the DoD environments are enabled for Location-Based Routing.</span></span>

#### <a name="defining-a-global-voice-routing-policy"></a><span data-ttu-id="61168-146">Определение глобальной политики маршрутинга голосовой почты</span><span class="sxs-lookup"><span data-stu-id="61168-146">Defining a global voice routing policy</span></span>

<span data-ttu-id="61168-147">Глобальную политику маршрутизации голосовой почты можно определить путем определения использования ННР, голосового маршрута, политики маршрутизации голосовой маршрутизации и назначения новой политики маршрутизации голосовой почты в качестве глобальной политики маршрутизации голосовой почты в организации.</span><span class="sxs-lookup"><span data-stu-id="61168-147">A global voice routing policy can be defined by defining a PSTN usage, a voice route, a voice routing policy, and assigning the new voice routing policy as the global voice routing policy of your organization.</span></span>

<span data-ttu-id="61168-148">Ниже описано, как определить новую глобальную политику маршрутизации голосовой почты для организации без нее.</span><span class="sxs-lookup"><span data-stu-id="61168-148">The following steps describe how to define a new global voice routing policy for an organization without one.</span></span> <span data-ttu-id="61168-149">Если в вашей организации уже определены политики маршрутизации голосовой связи, убедитесь, что следующая конфигурация не конфликтует с существующими политиками маршрутизации голосовой связи в организации.</span><span class="sxs-lookup"><span data-stu-id="61168-149">If your organization already has voice routing policies defined, verify that the following configuration doesn’t conflict with the existing voice routing policies of your organization.</span></span>

<span data-ttu-id="61168-150">Чтобы создать новую функцию использования ННР в удаленном сеансе PowerShell в Skype для бизнеса Online, используйте следующую команду:</span><span class="sxs-lookup"><span data-stu-id="61168-150">To create a new PSTN usage in a remote PowerShell session in Skype for Business Online, use the following command:</span></span>

  ```PowerShell
  Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="International"}
  ```

<span data-ttu-id="61168-151">Дополнительные сведения [см. в set-CsOnlinePstnUsage.](/powershell/module/skype/set-csonlinepstnusage)</span><span class="sxs-lookup"><span data-stu-id="61168-151">For additional information, see [Set-CsOnlinePstnUsage](/powershell/module/skype/set-csonlinepstnusage).</span></span>

<span data-ttu-id="61168-152">Чтобы создать новый голосовой маршрут, используйте следующую команду:</span><span class="sxs-lookup"><span data-stu-id="61168-152">To create a new voice route, use the following command:</span></span>

  ```PowerShell
  New-CsOnlineVoiceRoute -Identity "International" -NumberPattern ".*" -OnlinePstnGatewayList sbc1.contoso.biz -OnlinePstnUsages "International"
  ```

<span data-ttu-id="61168-153">При определении нового голосового пути для организации укажите один или несколько шлюзов ННР, определенных для организации в ходе настройки прямой маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="61168-153">When defining a new voice route for your organization, please specify one or multiple of the PSTN online PSTN gateways that have been defined for your organization during the configuration of Direct Routing.</span></span> 

<span data-ttu-id="61168-154">Шаблон номера определяет, какие звонки будут перенаправлены через указанный список шлюзов на основе номера конечного телефона звонка.</span><span class="sxs-lookup"><span data-stu-id="61168-154">The number pattern specifies which calls will be routed through the specified list of gateways based on the destination phone number of the call.</span></span> <span data-ttu-id="61168-155">В примере выше звонки в любую точку мира будут соответствовать голосовой маршрут.</span><span class="sxs-lookup"><span data-stu-id="61168-155">In the example above, calls to any destinations in the world will match the voice route.</span></span> <span data-ttu-id="61168-156">Если вы хотите ограничить набор телефонных номеров для собраний пользователей в организации, вы можете изменить шаблон номера таким образом, чтобы голосовой маршрут совпадал только с шаблонами номеров в разрешенных назначениях.</span><span class="sxs-lookup"><span data-stu-id="61168-156">If you would like to restrict the phone numbers that can be dialed from the meetings of users in your organization, you can change the number pattern to have the voice route match only the number patterns of the destinations allowed.</span></span> <span data-ttu-id="61168-157">Обратите внимание, что если не существует голосовых маршрутов, которые соответствуют шаблону номеров телефонов назначения для данного звонка, перенаправление звонка не будет.</span><span class="sxs-lookup"><span data-stu-id="61168-157">Please note that if there are no voice routes that match the number pattern of the destination phone number of a given call, the call will not be routed.</span></span>

<span data-ttu-id="61168-158">Дополнительные сведения [см. в new-CsOnlineVoiceRoute.](/powershell/module/skype/new-csonlinevoiceroute)</span><span class="sxs-lookup"><span data-stu-id="61168-158">For additional information, see [New-CsOnlineVoiceRoute](/powershell/module/skype/new-csonlinevoiceroute).</span></span>

<span data-ttu-id="61168-159">Чтобы создать политику маршрутинга голосовой почты, используйте следующую команду:</span><span class="sxs-lookup"><span data-stu-id="61168-159">To create a new voice routing policy, use the following command:</span></span>

  ```PowerShell
  New-CsOnlineVoiceRoutingPolicy "InternationalVoiceRoutingPolicy" -OnlinePstnUsages "International"
  ```

<span data-ttu-id="61168-160">Если в политике маршрутинга голосовой маршрутки определено несколько вариантов использования ОКП, они будут оцениваться в том порядке, в котором они определены.</span><span class="sxs-lookup"><span data-stu-id="61168-160">If multiple PSTN usages are being defined in the voice routing policy, they will be evaluated in the order in which they are defined.</span></span> <span data-ttu-id="61168-161">Рекомендуется определить использование телефонной сети общего пользования в порядке определения наиболее общих с точки зрения числовых шаблонов голосовых маршрутов, связанных с использованием ПС ДНР.</span><span class="sxs-lookup"><span data-stu-id="61168-161">It is recommended that the PSTN usages are defined in the order of the most specific to the more generic in terms of the number patterns of the voice routes associated with the PSTN usages.</span></span> <span data-ttu-id="61168-162">Например, если для перенастройки звонков в США определена использование ЗВОНКОВ по ННР, а для перенастройки звонков в любое другое место в мире, то использование ЗВОНКОВ по ПС ДЛЯ звонков в США должно быть указано в политике перенастройки голосовой маршрутки до использования ЗВОНКОВ по СТАНД для маршрутации звонков в любое другое место мира.</span><span class="sxs-lookup"><span data-stu-id="61168-162">For example, if a PSTN usage was defined to route calls to the United States, and another PSTN usage was defined to route calls to any other location in the world, the PSTN usage for calls to the United States should be listed in the voice routing policy ahead of the PSTN usage to route calls to any other location in the world.</span></span>

<span data-ttu-id="61168-163">Дополнительные сведения см. [в new-CsOnlineVoiceRoutingPolicy.](/powershell/module/skype/new-csonlinevoiceroutingpolicy)</span><span class="sxs-lookup"><span data-stu-id="61168-163">For additional information, see [New-CsOnlineVoiceRoutingPolicy](/powershell/module/skype/new-csonlinevoiceroutingpolicy).</span></span>

<span data-ttu-id="61168-164">Чтобы назначить новый голосовой маршрут глобальной политике маршрутизации голосовой почты в организации, используйте следующую команду:</span><span class="sxs-lookup"><span data-stu-id="61168-164">To assign the new voice route to the global voice routing policy of your organization, use the following command:</span></span>

  ```PowerShell
  Grant-CsOnlineVoiceRoutingPolicy -PolicyName "InternationalVoiceRoutingPolicy" -Global
  ```

<span data-ttu-id="61168-165">Дополнительные сведения [см. в grant-CsOnlineVoiceRoutingPolicy.](/powershell/module/skype/grant-csonlinevoiceroutingpolicy)</span><span class="sxs-lookup"><span data-stu-id="61168-165">For additional information, see [Grant-CsOnlineVoiceRoutingPolicy](/powershell/module/skype/grant-csonlinevoiceroutingpolicy).</span></span>

<span data-ttu-id="61168-166">После определения глобальной политики маршрутизации голосовой связи все исходящие звонки, сделанные пользователями в организации, будут оцениваться с использованием голосовых маршрутов, связанных с использованием глобальной политики маршрутизации голосовой связи по ПС.</span><span class="sxs-lookup"><span data-stu-id="61168-166">Once the global voice routing policy has been defined, any outbound calls made from meetings organized by users in your organization will be evaluated against the voice routes associated to the PSTN usages of the global voice routing policy.</span></span> <span data-ttu-id="61168-167">Исходящие звонки будут маршрутизовы в соответствии с первым голосовым маршрутом, соответствующим шаблону набра номера телефона.</span><span class="sxs-lookup"><span data-stu-id="61168-167">The outbound calls will be routed according to the first voice route that matches the number pattern of the dialed phone number.</span></span>

### <a name="step-5-assign-audio-conferencing-with-direct-routing-for-gcc-high-or-dod-licenses-to-your-users"></a><span data-ttu-id="61168-168">Шаг 5. Назначение пользователям аудиоконференций с прямой маршрутизацией для лицензий GCC High или DoD</span><span class="sxs-lookup"><span data-stu-id="61168-168">Step 5: Assign Audio Conferencing with Direct Routing for GCC High or DoD licenses to your users</span></span>

<span data-ttu-id="61168-169">Чтобы назначить пользователю аудиоконференцию с прямой маршрутизацией для лицензий GCC High или DoD, см. назначение [лицензий пользователям.](/microsoft-365/admin/manage/assign-licenses-to-users)</span><span class="sxs-lookup"><span data-stu-id="61168-169">To assign Audio Conferencing with Direct Routing for GCC High or DoD licenses to your user, see [Assign licenses to users](/microsoft-365/admin/manage/assign-licenses-to-users).</span></span>

### <a name="step-6-optional-see-a-list-of-audio-conferencing-numbers-in-teams"></a><span data-ttu-id="61168-170">Шаг 6. Просмотр списка номеров для аудиоконференций в Teams (необязательно)</span><span class="sxs-lookup"><span data-stu-id="61168-170">Step 6: (Optional) See a list of Audio Conferencing numbers in Teams</span></span>

<span data-ttu-id="61168-171">Список номеров для аудиоконференц в организации см. в списке номеров для аудиоконференций [в Microsoft Teams.](see-a-list-of-audio-conferencing-numbers-in-teams.md)</span><span class="sxs-lookup"><span data-stu-id="61168-171">To see the list of Audio Conferencing numbers of your organization, go to [See a list of Audio Conferencing numbers in Microsoft Teams](see-a-list-of-audio-conferencing-numbers-in-teams.md).</span></span>

### <a name="step-7-optional-set-auto-attendant-languages-for-the-audio-conferencing-dial-in-numbers-of-you-organization"></a><span data-ttu-id="61168-172">Шаг 7. Настройка языков автособираемого помощника для номеров аудиоконференций в организации (необязательно)</span><span class="sxs-lookup"><span data-stu-id="61168-172">Step 7: (Optional) Set auto attendant languages for the Audio Conferencing dial-in numbers of you organization</span></span>

<span data-ttu-id="61168-173">Чтобы узнать, как изменить языки номеров для аудиоконференции с телефонным номером в организации, см. в этом видео. [](set-auto-attendant-languages-for-audio-conferencing-in-teams.md)</span><span class="sxs-lookup"><span data-stu-id="61168-173">To change the languages of the Audio Conferencing dial-in numbers of your organization, see [Set auto attendant languages for Audio Conferencing in Microsoft Teams](set-auto-attendant-languages-for-audio-conferencing-in-teams.md).</span></span>

### <a name="step-8-optional-change-the-settings-of-the-audio-conferencing-bridge-of-your-organization"></a><span data-ttu-id="61168-174">Шаг 8. Изменение параметров моста аудиоконференций в организации (необязательно)</span><span class="sxs-lookup"><span data-stu-id="61168-174">Step 8: (Optional) Change the settings of the Audio Conferencing bridge of your organization</span></span>

<span data-ttu-id="61168-175">Чтобы изменить параметры моста аудиоконференций вашей организации, см. статью "Изменение параметров моста [аудиоконференции".](change-the-settings-for-an-audio-conferencing-bridge.md)</span><span class="sxs-lookup"><span data-stu-id="61168-175">To change the settings of the Audio Conferencing bridge of your organization, see [Change the settings for an Audio Conferencing bridge](change-the-settings-for-an-audio-conferencing-bridge.md).</span></span>

### <a name="step-9-optional-set-the-phone-numbers-included-in-the-meeting-invites-of-the-users-in-your-organization"></a><span data-ttu-id="61168-176">Шаг 9. Настройка телефонных номеров, включенных в приглашения на собрания для пользователей в организации (необязательно)</span><span class="sxs-lookup"><span data-stu-id="61168-176">Step 9: (Optional) Set the phone numbers included in the meeting invites of the users in your organization</span></span>

<span data-ttu-id="61168-177">Чтобы изменить набор телефонных номеров, которые включаются в приглашения на собрания, см. в настройках номеров телефонов, включенных в приглашения [в Microsoft Teams.](set-the-phone-numbers-included-on-invites-in-teams.md)</span><span class="sxs-lookup"><span data-stu-id="61168-177">To change the set of phone numbers that are included in the meeting invites of the users is your organization, see [Set the phone numbers included on invites in Microsoft Teams](set-the-phone-numbers-included-on-invites-in-teams.md).</span></span>

## <a name="audio-conferencing-capabilities-not-supported-in-audio-conferencing-with-direct-routing-for-gcc-high-and-dod"></a><span data-ttu-id="61168-178">Возможности аудиоконференции не поддерживаются для аудиоконференций с прямой маршрутизацией для GCC High и DoD</span><span class="sxs-lookup"><span data-stu-id="61168-178">Audio Conferencing capabilities not supported in Audio Conferencing with Direct Routing for GCC High and DoD</span></span>

<span data-ttu-id="61168-179">Ниже 2010 г. возможности аудиоконференций, которые не поддерживаются при прямой маршрутизаке для GCC High и DoD:</span><span class="sxs-lookup"><span data-stu-id="61168-179">The following are Audio Conferencing capabilities that are not supported in Audio Conferencing with Direct Routing for GCC High and DoD:</span></span>

- <span data-ttu-id="61168-180">Уведомления о входе и выходе с помощью записи имени.</span><span class="sxs-lookup"><span data-stu-id="61168-180">Entry and exit notifications using name recording.</span></span> <span data-ttu-id="61168-181">Для аудиоконференций с прямой маршрутизацией уведомления о входе и выходе будут играть на собрании в тонах.</span><span class="sxs-lookup"><span data-stu-id="61168-181">For Audio Conferencing with Direct Routing, entry and exit notifications are played in the meeting as tones.</span></span>

- <span data-ttu-id="61168-182">Политики ограничений на исходящие вызовы для аудиоконференций.</span><span class="sxs-lookup"><span data-stu-id="61168-182">Outbound calling restriction policies for Audio Conferencing.</span></span> <span data-ttu-id="61168-183">Элементы управления на уровне пользователей, ограничивающие исходящие звонки, не применимы к звонкам на собрания, перенаправимым с помощью прямой маршрутинга.</span><span class="sxs-lookup"><span data-stu-id="61168-183">User-level controls to restrict outbound calls aren't applicable to meeting dial-out calls routed via Direct Routing.</span></span>

- <span data-ttu-id="61168-184">Отключать использование бесплатных номеров для определенного организатора собраний.</span><span class="sxs-lookup"><span data-stu-id="61168-184">Disable the usage of toll-free numbers for the meetings specific organizer.</span></span> <span data-ttu-id="61168-185">Элементы управления на уровне пользователей, ограничивающие использование бесплатных номеров для звонков, которые можно использовать для звонков, не применимы к звонкам, перенаправимым с помощью прямой маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="61168-185">User-level controls to restrict the usage of toll-free numbers to join the meetings of your organization aren't applicable to calls routed via Direct Routing.</span></span>

- <span data-ttu-id="61168-186">Отправка уведомлений пользователям при изменении их параметров.</span><span class="sxs-lookup"><span data-stu-id="61168-186">Sending notification emails to users when their settings change.</span></span> <span data-ttu-id="61168-187">Сообщения электронной почты с уведомлениями об аудиоконференции не поддерживаются для аудиоконференций с прямой маршрутизацией для GCC High и DoD.</span><span class="sxs-lookup"><span data-stu-id="61168-187">Audio Conferencing notification emails aren't supported for Audio Conferencing with Direct Routing for GCC High and DoD.</span></span>