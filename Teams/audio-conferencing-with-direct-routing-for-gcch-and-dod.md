---
title: Голосовые конференции с прямой маршрутизацией, GCCH и DoD
author: LanaChin
ms.author: v-lanac
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
description: Администратор может узнать о том, как использовать голосовую конференцию с прямой маршрутизацией в GCCH и в среде с использованием по требованию.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 34fcb84ee0e5126188f47a4ccc231c04ffd093b2
ms.sourcegitcommit: 8924cd77923ca321de72edc3fed04425a4b13044
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "48262496"
---
# <a name="audio-conferencing-with-direct-routing-for-gcc-high-and-dod"></a><span data-ttu-id="1d7d1-103">Аудиоконференции с прямой маршрутизацией для GCC High и DoD</span><span class="sxs-lookup"><span data-stu-id="1d7d1-103">Audio Conferencing with Direct Routing for GCC High and DoD</span></span>

<span data-ttu-id="1d7d1-104">Голосовые конференции с прямой маршрутизацией на GCC High и DoD позволяют участникам присоединяться к собраниям Teams в рамках высокоскоростной или неопределенной Организации с помощью телефонного устройства.</span><span class="sxs-lookup"><span data-stu-id="1d7d1-104">Audio Conferencing with Direct Routing for GCC High and DoD enables participants to join Teams meetings in your GCC High or DoD organization by using a phone device.</span></span> <span data-ttu-id="1d7d1-105">Участники собрания могут предпочесть использовать телефонное устройство для присоединения к собраниям Teams в сценариях, например при ограниченном подключении к Интернету или в том случае, если пользователи находятся в дороге, но у вас нет доступа к Teams.</span><span class="sxs-lookup"><span data-stu-id="1d7d1-105">Meeting participants might prefer to use a phone device to join Teams meetings in scenarios such as when internet connectivity is limited or when users are on the road and don't have access to Teams.</span></span> <span data-ttu-id="1d7d1-106">Участники могут присоединиться к собраниям с помощью набора номера для телефонного номера в вашей организации или с помощью собрания на телефонное устройство.</span><span class="sxs-lookup"><span data-stu-id="1d7d1-106">Participants can choose to join meetings by either dialing in to a dial-in phone number for your organization or by having the meeting dial out to their phone device.</span></span>

<span data-ttu-id="1d7d1-107">Если вы используете голосовую конференцию с прямой маршрутизацией для GCC High и DoD, ваша организация использует собственные номера для телефонного подключения, а все телефонные номера для собраний — через прямую маршрутизацию.</span><span class="sxs-lookup"><span data-stu-id="1d7d1-107">With Audio Conferencing with Direct Routing for GCC High and DoD, your organization uses its own numbers as dial-in phone numbers and all meeting dial-outs to phone devices are routed via Direct Routing.</span></span> <span data-ttu-id="1d7d1-108">Чтобы включить службу, организациям нужно настроить прямую маршрутизацию и настроить номера телефонов, которые можно использовать в качестве телефонных номеров для телефонного подключения.</span><span class="sxs-lookup"><span data-stu-id="1d7d1-108">To enable the service, organizations need to set up Direct Routing and configure phone numbers that can be used as dial-in phone numbers.</span></span> <span data-ttu-id="1d7d1-109">Требование использовать прямую переадресацию отличается от службы голосовой связи, которая предлагается для организаций с телефонным подключением, отличными от GCC и не использующей незвонку, в которой номера телефонов для подключения к службе предоставляются корпорацией Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="1d7d1-109">The requirement to use Direct Routing is different from the Audio Conferencing service that's offered to non-GCC High and non-DoD organizations where the dial-in phone numbers are provided by Microsoft.</span></span>

## <a name="deploy-audio-conferencing-with-direct-routing-for-gcc-high-and-dod"></a><span data-ttu-id="1d7d1-110">Развертывание голосовой конференции с прямой маршрутизацией для установки GCC High и DoD</span><span class="sxs-lookup"><span data-stu-id="1d7d1-110">Deploy Audio Conferencing with Direct Routing for GCC High and DoD</span></span>

### <a name="step-1-get-audio-conferencing-with-direct-routing-for-gcc-high-or-dod-licenses"></a><span data-ttu-id="1d7d1-111">Шаг 1: получение голосовой конференции с прямой маршрутизацией для высокоскоростных лицензий GCC High или DoD</span><span class="sxs-lookup"><span data-stu-id="1d7d1-111">Step 1: Get Audio Conferencing with Direct Routing for GCC High or DoD licenses</span></span> 

<span data-ttu-id="1d7d1-112">Чтобы использовать голосовую конференцию в GCC High или DoD, ваша организация и пользователи в вашей организации должны иметь возможность голосовой конференции с назначенной прямой лицензией.</span><span class="sxs-lookup"><span data-stu-id="1d7d1-112">To use Audio Conferencing in GCC High or DoD, your organization and the users in your organization need to have an Audio Conferencing with Direct Routing license assigned.</span></span> <span data-ttu-id="1d7d1-113">Ниже указаны лицензии, с помощью которых вы можете включить голосовую конференцию с прямой маршрутизацией для GCC High или DoD.</span><span class="sxs-lookup"><span data-stu-id="1d7d1-113">Here are the licenses you need to enable Audio Conferencing with Direct Routing for GCC High or DoD.</span></span>

- <span data-ttu-id="1d7d1-114">GCC High (высокое качество): видеоконференции — более высокая лицензия на клиента для вашей организации и голосовой конференции — самые высокие лицензии для пользователей.</span><span class="sxs-lookup"><span data-stu-id="1d7d1-114">GCC High: An Audio Conferencing - GCC High Tenant license for your organization and Audio Conferencing - GCC High licenses for your users.</span></span>

- <span data-ttu-id="1d7d1-115">Использование голосовой связи – лицензия на клиента с помощью DoD для Организации и голосовой конференции – лицензии на использование по требованию для пользователей.</span><span class="sxs-lookup"><span data-stu-id="1d7d1-115">DoD: An Audio Conferencing - DoD Tenant license for your organization and Audio Conferencing - DoD licenses for your users.</span></span>

<span data-ttu-id="1d7d1-116">Для включения службы требуется лицензия клиента и хотя бы одна лицензия пользователя.</span><span class="sxs-lookup"><span data-stu-id="1d7d1-116">A tenant license and at least one user license are required to enable the service.</span></span> <span data-ttu-id="1d7d1-117">Вы не можете включить службу только с лицензией клиента или только с пользовательскими лицензиями.</span><span class="sxs-lookup"><span data-stu-id="1d7d1-117">You can't enable the service with only the tenant license or with only user licenses.</span></span> <span data-ttu-id="1d7d1-118">Чтобы получить лицензии на обслуживание для вашего клиента и пользователей в Организации, обратитесь в группу своей учетной записи.</span><span class="sxs-lookup"><span data-stu-id="1d7d1-118">To get service licenses for your tenant and the users in your organization, contact your account team.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1d7d1-119">Пользователи не могут быть включены для голосовой конференции с прямой маршрутизацией, пока не будут настроены номера телефонов для подключения.</span><span class="sxs-lookup"><span data-stu-id="1d7d1-119">Users can't be enabled for Audio Conferencing with Direct Routing until dial-in phone numbers are set up.</span></span> <span data-ttu-id="1d7d1-120">Мы не рекомендуем использовать голосовую конференцию с прямой маршрутизацией для лицензий GCC High или DoD для пользователей до тех пор, пока вы не настроили номера телефонов для подключения, описанные в этой статье.</span><span class="sxs-lookup"><span data-stu-id="1d7d1-120">We recommend that you not assign Audio Conferencing with Direct Routing for GCC High or DoD licenses to users until you set up dial-in phone numbers as outlined in this article.</span></span>

### <a name="step-2-set-up-direct-routing"></a><span data-ttu-id="1d7d1-121">Шаг 2: Настройка прямой маршрутизации</span><span class="sxs-lookup"><span data-stu-id="1d7d1-121">Step 2: Set up Direct Routing</span></span>

<span data-ttu-id="1d7d1-122">Чтобы настроить прямую переадресацию, ознакомьтесь со следующими статьями:</span><span class="sxs-lookup"><span data-stu-id="1d7d1-122">To set up Direct Routing, see the following articles:</span></span>

- [<span data-ttu-id="1d7d1-123">Планирование прямой маршрутизации</span><span class="sxs-lookup"><span data-stu-id="1d7d1-123">Plan Direct Routing</span></span>](direct-routing-plan.md)

- [<span data-ttu-id="1d7d1-124">Настройка прямой маршрутизации</span><span class="sxs-lookup"><span data-stu-id="1d7d1-124">Configure Direct Routing</span></span>](direct-routing-configure.md)

> [!NOTE]
> <span data-ttu-id="1d7d1-125">При настройке прямой маршрутизации не забудьте использовать полные доменные имена и порты, которые описаны в этих двух статьях.</span><span class="sxs-lookup"><span data-stu-id="1d7d1-125">When you set up Direct Routing, remember to use the GCC High or DoD-specific FQDNs and ports that are described in these two articles.</span></span>

### <a name="step-3-set-up-dial-in-phone-numbers"></a><span data-ttu-id="1d7d1-126">Шаг 3. Настройте телефонные номера для телефонного подключения.</span><span class="sxs-lookup"><span data-stu-id="1d7d1-126">Step 3: Set up dial-in phone numbers</span></span>

<span data-ttu-id="1d7d1-127">Телефонные номера для телефонного подключения – это номера телефонов, которые связаны с вашим мостом для проведения голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="1d7d1-127">Dial-in phone numbers are the phone numbers that are associated to your Audio Conferencing bridge.</span></span> <span data-ttu-id="1d7d1-128">Эти номера используются участниками для присоединения к собраниям, которые запланированы для пользователей в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="1d7d1-128">These numbers are used by participants to join meetings scheduled by users in your organization.</span></span> <span data-ttu-id="1d7d1-129">Эти номера также включаются в приглашения на собрания пользователей, которые запланируют собрания в вашей организации, и на странице "Поиск местного номера".</span><span class="sxs-lookup"><span data-stu-id="1d7d1-129">These numbers are also included in the meeting invites of the users who schedule meetings in your organization and on the "Find a local number" page.</span></span>

#### <a name="define-service-phone-numbers-in-your-tenant"></a><span data-ttu-id="1d7d1-130">Определение номеров телефонов служб в клиенте</span><span class="sxs-lookup"><span data-stu-id="1d7d1-130">Define service phone numbers in your tenant</span></span>

<span data-ttu-id="1d7d1-131">С помощью командлета PowerShell New-csHybridTelephoneNumber можно определять номера служебных служб в клиенте, которые можно использовать для маршрутизации звонков к службе голосовой связи через прямую маршрутизацию.</span><span class="sxs-lookup"><span data-stu-id="1d7d1-131">You can use the New-csHybridTelephoneNumber PowerShell cmdlet to define service phone numbers in your tenant that can be used to route calls to the Audio Conferencing service via Direct Routing.</span></span> 

  ```PowerShell
  New-csHybridTelephoneNumber -TelephoneNumber <Phone number in E.164 format>
  ```

<span data-ttu-id="1d7d1-132">Например:</span><span class="sxs-lookup"><span data-stu-id="1d7d1-132">For example:</span></span>
  ```PowerShell
  New-csHybridTelephoneNumber -TelephoneNumber "+14250000000"
  ```

#### <a name="assign-the-service-phone-numbers-to-the-audio-conferencing-bridge-of-your-organization"></a><span data-ttu-id="1d7d1-133">Назначение телефонных номеров служб для моста голосовой конференции в Организации</span><span class="sxs-lookup"><span data-stu-id="1d7d1-133">Assign the service phone numbers to the Audio Conferencing bridge of your organization</span></span>

<span data-ttu-id="1d7d1-134">С помощью командлета PowerShell Register-csOnlineDialInConferencingServiceNumber вы можете назначить номера телефонов служб для моста голосовой связи в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="1d7d1-134">You can assign service phone numbers to the Audio Conferencing bridge of your organization by using the Register-csOnlineDialInConferencingServiceNumber PowerShell cmdlet.</span></span>

  ```PowerShell
  Register-csOnlineDialInConferencingServiceNumber -identity <Telephone number in E.164 format> -BridgeId <Identity of the audio conferencing bridge>
  ```

<span data-ttu-id="1d7d1-135">Вы можете просмотреть идентификатор своего моста звуковых конференций с помощью Get-CsOnlineDialInConferencingBridge.</span><span class="sxs-lookup"><span data-stu-id="1d7d1-135">You can see the ID of your Audio Conferencing Bridge using Get-CsOnlineDialInConferencingBridge.</span></span> <span data-ttu-id="1d7d1-136">Например:</span><span class="sxs-lookup"><span data-stu-id="1d7d1-136">For example:</span></span>

  ```PowerShell
  $b= Get-CsOnlineDialInConferencingBridge
  Register-csOnlineDialInConferencingServiceNumber -identity 14257048060 -BridgeId $b.identity
  ```


### <a name="step-4-define-a-global-voice-routing-policy-to-enable-the-routing-of-outbound-calls-from-meetings"></a><span data-ttu-id="1d7d1-137">Действие 4: Определите глобальную политику маршрутизации голосовой связи, чтобы включить маршрутизацию исходящих вызовов из собраний.</span><span class="sxs-lookup"><span data-stu-id="1d7d1-137">Step 4: Define a global voice routing policy to enable the routing of outbound calls from meetings</span></span>

<span data-ttu-id="1d7d1-138">Маршрутизация исходящих вызовов, сделанных в КТСОП, из собраний, организованных пользователями организации, определяется глобальной политикой голосовой маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="1d7d1-138">The routing of outbound calls that are made to the PSTN from meetings organized by users in your organization is defined by the global voice routing policy of your organization.</span></span> <span data-ttu-id="1d7d1-139">Если в вашей организации определена глобальная политика маршрутизации голосовой связи, убедитесь в том, что глобальная политика маршрутизации голосовой связи допускает исходящие вызовы сети PSTN, которые должны быть инициированы для собраний, организованных пользователями в Организации.</span><span class="sxs-lookup"><span data-stu-id="1d7d1-139">If your organization has a global voice routing policy defined, please verify that the global voice routing policy allows the outbound calls to the PSTN that are expected to be initiated from meetings organized by users in your organization.</span></span> <span data-ttu-id="1d7d1-140">Если в вашей организации не определена глобальная политика маршрутизации голосовой связи, вам потребуется задать ее для включения маршрутизации исходящих вызовов в КТСОП с собраний, организованных пользователями в Организации.</span><span class="sxs-lookup"><span data-stu-id="1d7d1-140">If your organization doesn’t have a global voice routing policy defined, you will need to define one to enable the routing of outbound calls to the PSTN from meetings organized by users in your organization.</span></span> <span data-ttu-id="1d7d1-141">Обратите внимание на то, что глобальная политика маршрутизации голосовой связи в вашей организации также применяется к звонкам "один к одному" для пользователей в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="1d7d1-141">Please note that the global voice routing policy of your organization also applies to one-to-one calls made to the PSTN by users in your organization.</span></span> <span data-ttu-id="1d7d1-142">Если для пользователей в вашей организации разрешены одноранговые вызовы по коммутируемой телефонной сети, убедитесь, что глобальная политика голосовой маршрутизации отвечает потребностям вашей организации для обоих типов звонков.</span><span class="sxs-lookup"><span data-stu-id="1d7d1-142">If one-to-one calls to the PSTN are enabled for users in your organization, make sure that the global voice routing policy meets the needs of your organization for both types of calls.</span></span> 

> [!NOTE]
> <span data-ttu-id="1d7d1-143">Маршрутизация на основе местоположения недоступна в развертываниях сообщества Microsoft 365 для государственных организаций (GCC) и в облаке.</span><span class="sxs-lookup"><span data-stu-id="1d7d1-143">Location-Based Routing isn't available in Microsoft 365 Government Community Cloud (GCC) High or DoD deployments.</span></span> <span data-ttu-id="1d7d1-144">При включении голосовой конференции убедитесь в том, что для маршрутизации на основе расположения включены пользователи голосовой связи в среде с незначительной контрастностью или в средах по требованию.</span><span class="sxs-lookup"><span data-stu-id="1d7d1-144">When enabling Audio Conferencing, please verify that no Audio Conferencing users in the GCC High or the DoD environments are enabled for Location-Based Routing.</span></span>

#### <a name="defining-a-global-voice-routing-policy"></a><span data-ttu-id="1d7d1-145">Определение глобальной политики голосовой маршрутизации</span><span class="sxs-lookup"><span data-stu-id="1d7d1-145">Defining a global voice routing policy</span></span>

<span data-ttu-id="1d7d1-146">Вы можете определить глобальную политику маршрутизации голосовой связи, определив использование PSTN, голосовой маршрут, политику голосовой маршрутизации и назначив новую политику голосовой маршрутизации в качестве глобальной политики голосовой маршрутизации для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="1d7d1-146">A global voice routing policy can be defined by defining a PSTN usage, a voice route, a voice routing policy, and assigning the new voice routing policy as the global voice routing policy of your organization.</span></span>

<span data-ttu-id="1d7d1-147">Ниже приведены инструкции по определению новой глобальной политики голосовой маршрутизации для Организации без нее.</span><span class="sxs-lookup"><span data-stu-id="1d7d1-147">The following steps describe how to define a new global voice routing policy for an organization without one.</span></span> <span data-ttu-id="1d7d1-148">Если в вашей организации уже определены политики голосовой маршрутизации, убедитесь в том, что следующая конфигурация не конфликтует с существующими политиками голосовой маршрутизации для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="1d7d1-148">If your organization already has voice routing policies defined, verify that the following configuration doesn’t conflict with the existing voice routing policies of your organization.</span></span>

<span data-ttu-id="1d7d1-149">Чтобы создать новое использование PSTN в удаленном сеансе PowerShell в Skype для бизнеса Online, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="1d7d1-149">To create a new PSTN usage in a remote PowerShell session in Skype for Business Online, use the following command:</span></span>

  ```PowerShell
  Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="International"}
  ```

<span data-ttu-id="1d7d1-150">Дополнительные сведения можно найти в разделе [Set-CsOnlinePstnUsage](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstnusage).</span><span class="sxs-lookup"><span data-stu-id="1d7d1-150">For additional information, see [Set-CsOnlinePstnUsage](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstnusage).</span></span>

<span data-ttu-id="1d7d1-151">Чтобы создать новый голосовой маршрут, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="1d7d1-151">To create a new voice route, use the following command:</span></span>

  ```PowerShell
  New-CsOnlineVoiceRoute -Identity "International" -NumberPattern ".*" -OnlinePstnGatewayList sbc1.contoso.biz -OnlinePstnUsages "International"
  ```

<span data-ttu-id="1d7d1-152">При определении нового голосового маршрута для вашей организации следует указать один или несколько шлюзов PSTN из Интернета, которые были определены для вашей организации во время настройки прямой маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="1d7d1-152">When defining a new voice route for your organization, please specify one or multiple of the PSTN online PSTN gateways that have been defined for your organization during the configuration of Direct Routing.</span></span> 

<span data-ttu-id="1d7d1-153">Шаблон номера указывает, какие звонки будут маршрутизироваться по указанному списку шлюзов на основе номера телефона звонка.</span><span class="sxs-lookup"><span data-stu-id="1d7d1-153">The number pattern specifies which calls will be routed through the specified list of gateways based on the destination phone number of the call.</span></span> <span data-ttu-id="1d7d1-154">В приведенном выше примере звонки на все места назначения в мире будут соответствовать маршруту голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="1d7d1-154">In the example above, calls to any destinations in the world will match the voice route.</span></span> <span data-ttu-id="1d7d1-155">Если вы хотите ограничить телефонные номера, которые можно набрать на собраниях пользователей в вашей организации, вы можете изменить шаблон номера, чтобы он соответствовал только номерам разрешенных для них целей.</span><span class="sxs-lookup"><span data-stu-id="1d7d1-155">If you would like to restrict the phone numbers that can be dialed from the meetings of users in your organization, you can change the number pattern to have the voice route match only the number patterns of the destinations allowed.</span></span> <span data-ttu-id="1d7d1-156">Обратите внимание на то, что в случае отсутствия голосовых маршрутов, соответствующих шаблону номера телефона назначения данного звонка, Звонок не будет перенаправлен.</span><span class="sxs-lookup"><span data-stu-id="1d7d1-156">Please note that if there are no voice routes that match the number pattern of the destination phone number of a given call, the call will not be routed.</span></span>

<span data-ttu-id="1d7d1-157">Дополнительные сведения можно найти в разделе [New-CsOnlineVoiceRoute](https://docs.microsoft.com/powershell/module/skype/new-csonlinevoiceroute).</span><span class="sxs-lookup"><span data-stu-id="1d7d1-157">For additional information, see [New-CsOnlineVoiceRoute](https://docs.microsoft.com/powershell/module/skype/new-csonlinevoiceroute).</span></span>

<span data-ttu-id="1d7d1-158">Чтобы создать новую политику голосовой маршрутизации, введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="1d7d1-158">To create a new voice routing policy, use the following command:</span></span>

  ```PowerShell
  New-CsOnlineVoiceRoutingPolicy "InternationalVoiceRoutingPolicy" -OnlinePstnUsages "International"
  ```

<span data-ttu-id="1d7d1-159">Если в политике голосовой маршрутизации определено несколько использований PSTN, они будут оцениваться в том порядке, в котором они определены.</span><span class="sxs-lookup"><span data-stu-id="1d7d1-159">If multiple PSTN usages are being defined in the voice routing policy, they will be evaluated in the order in which they are defined.</span></span> <span data-ttu-id="1d7d1-160">Рекомендуется, чтобы использование КТСОП было определено в том порядке, в котором они более специфичны, в соответствии с шаблонами количества голосовых маршрутов, связанных с использованием PSTN.</span><span class="sxs-lookup"><span data-stu-id="1d7d1-160">It is recommended that the PSTN usages are defined in the order of the most specific to the more generic in terms of the number patterns of the voice routes associated with the PSTN usages.</span></span> <span data-ttu-id="1d7d1-161">Например, если использование PSTN была определено для направления звонков в США, и для направления звонков в другие местоположения в мире определена другая плата, использование КТСОП для звонков в США должно быть указано в политике голосовой маршрутизации перед тем, как использовать КТСОП для нахождения звонков в любом другом месте мира.</span><span class="sxs-lookup"><span data-stu-id="1d7d1-161">For example, if a PSTN usage was defined to route calls to the United States, and another PSTN usage was defined to route calls to any other location in the world, the PSTN usage for calls to the United States should be listed in the voice routing policy ahead of the PSTN usage to route calls to any other location in the world.</span></span>

<span data-ttu-id="1d7d1-162">Дополнительные сведения можно найти в разделе [New-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csonlinevoiceroutingpolicy).</span><span class="sxs-lookup"><span data-stu-id="1d7d1-162">For additional information, see [New-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csonlinevoiceroutingpolicy).</span></span>

<span data-ttu-id="1d7d1-163">Чтобы назначить новый голосовой маршрут глобальной политике голосовой связи в вашей организации, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="1d7d1-163">To assign the new voice route to the global voice routing policy of your organization, use the following command:</span></span>

  ```PowerShell
  Grant-CsOnlineVoiceRoutingPolicy -PolicyName "InternationalVoiceRoutingPolicy" -Global
  ```

<span data-ttu-id="1d7d1-164">Дополнительные сведения можно найти в разделе [Grant-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csonlinevoiceroutingpolicy).</span><span class="sxs-lookup"><span data-stu-id="1d7d1-164">For additional information, see [Grant-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csonlinevoiceroutingpolicy).</span></span>

<span data-ttu-id="1d7d1-165">После того как определена глобальная политика маршрутизации голосовой связи, любые исходящие вызовы из собраний, организованных пользователями в вашей организации, будут оцениваться по голосовым маршрутам, связанным с использованием глобальной политики голосовой маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="1d7d1-165">Once the global voice routing policy has been defined, any outbound calls made from meetings organized by users in your organization will be evaluated against the voice routes associated to the PSTN usages of the global voice routing policy.</span></span> <span data-ttu-id="1d7d1-166">Исходящие звонки будут перенаправляться в соответствии с первым маршрутом голосовой почты, который соответствует шаблону номера телефона.</span><span class="sxs-lookup"><span data-stu-id="1d7d1-166">The outbound calls will be routed according to the first voice route that matches the number pattern of the dialed phone number.</span></span>

### <a name="step-5-assign-audio-conferencing-with-direct-routing-for-gcc-high-or-dod-licenses-to-your-users"></a><span data-ttu-id="1d7d1-167">Шаг 5: назначение голосовой конференции с прямой маршрутизацией для лицензий на самые высокие или нелицензионные лицензии на GCC</span><span class="sxs-lookup"><span data-stu-id="1d7d1-167">Step 5: Assign Audio Conferencing with Direct Routing for GCC High or DoD licenses to your users</span></span>

<span data-ttu-id="1d7d1-168">Чтобы назначить голосовой конференции с прямой маршрутизацией для лицензий GCC High или DoD, ознакомьтесь с разрешениями [Назначение лицензий для пользователей](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users).</span><span class="sxs-lookup"><span data-stu-id="1d7d1-168">To assign Audio Conferencing with Direct Routing for GCC High or DoD licenses to your user, see [Assign licenses to users](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users).</span></span>

### <a name="step-6-optional-see-a-list-of-audio-conferencing-numbers-in-teams"></a><span data-ttu-id="1d7d1-169">Шаг 6: (необязательно) Просмотр списка номеров голосовой конференции в Teams</span><span class="sxs-lookup"><span data-stu-id="1d7d1-169">Step 6: (Optional) See a list of Audio Conferencing numbers in Teams</span></span>

<span data-ttu-id="1d7d1-170">Чтобы просмотреть список номеров голосовой конференц-связи в вашей организации, перейдите в раздел [Просмотр списка номеров голосовой конференции в Microsoft Teams](see-a-list-of-audio-conferencing-numbers-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="1d7d1-170">To see the list of Audio Conferencing numbers of your organization, go to [See a list of Audio Conferencing numbers in Microsoft Teams](see-a-list-of-audio-conferencing-numbers-in-teams.md).</span></span>

### <a name="step-7-optional-set-auto-attendant-languages-for-the-audio-conferencing-dial-in-numbers-of-you-organization"></a><span data-ttu-id="1d7d1-171">Шаг 7: (необязательно) Настройка языков автосекретаря для номеров телефонов для телефонной конференции в вашей организации</span><span class="sxs-lookup"><span data-stu-id="1d7d1-171">Step 7: (Optional) Set auto attendant languages for the Audio Conferencing dial-in numbers of you organization</span></span>

<span data-ttu-id="1d7d1-172">Чтобы изменить языки номеров телефонной конференции для голосовой связи в вашей организации, ознакомьтесь с разделами [Установка языков автосекретаря для голосовой конференции в Microsoft Teams](set-auto-attendant-languages-for-audio-conferencing-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="1d7d1-172">To change the languages of the Audio Conferencing dial-in numbers of your organization, see [Set auto attendant languages for Audio Conferencing in Microsoft Teams](set-auto-attendant-languages-for-audio-conferencing-in-teams.md).</span></span>

### <a name="step-8-optional-change-the-settings-of-the-audio-conferencing-bridge-of-your-organization"></a><span data-ttu-id="1d7d1-173">Шаг 8: (необязательно) измените параметры моста голосовой связи в Организации.</span><span class="sxs-lookup"><span data-stu-id="1d7d1-173">Step 8: (Optional) Change the settings of the Audio Conferencing bridge of your organization</span></span>

<span data-ttu-id="1d7d1-174">Сведения о том, как изменить параметры моста голосовой конференц-связи в вашей организации, можно найти в разделе [изменение параметров моста голосовой](change-the-settings-for-an-audio-conferencing-bridge.md)связи.</span><span class="sxs-lookup"><span data-stu-id="1d7d1-174">To change the settings of the Audio Conferencing bridge of your organization, see [Change the settings for an Audio Conferencing bridge](change-the-settings-for-an-audio-conferencing-bridge.md).</span></span>

### <a name="step-9-optional-set-the-phone-numbers-included-in-the-meeting-invites-of-the-users-in-your-organization"></a><span data-ttu-id="1d7d1-175">Шаг 9: (необязательно) Настройка номеров телефонов, включенных в приглашения на собрания пользователей в Организации</span><span class="sxs-lookup"><span data-stu-id="1d7d1-175">Step 9: (Optional) Set the phone numbers included in the meeting invites of the users in your organization</span></span>

<span data-ttu-id="1d7d1-176">Чтобы изменить набор телефонных номеров, включенных в приглашения на собрание пользователей, обратитесь к разделу [Настройка номеров телефонов, включенных в приглашения в Microsoft Teams](set-the-phone-numbers-included-on-invites-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="1d7d1-176">To change the set of phone numbers that are included in the meeting invites of the users is your organization, see [Set the phone numbers included on invites in Microsoft Teams](set-the-phone-numbers-included-on-invites-in-teams.md).</span></span>

## <a name="audio-conferencing-capabilities-not-supported-in-audio-conferencing-with-direct-routing-for-gcc-high-and-dod"></a><span data-ttu-id="1d7d1-177">Возможности голосовой связи не поддерживаются в голосовой конференции с прямой маршрутизацией для более высокого и невысокой четкости</span><span class="sxs-lookup"><span data-stu-id="1d7d1-177">Audio Conferencing capabilities not supported in Audio Conferencing with Direct Routing for GCC High and DoD</span></span>

<span data-ttu-id="1d7d1-178">Ниже приведены возможности голосовой конференции, которые не поддерживаются в голосовой конференции с прямой маршрутизацией для более высокого и невысокой четкости.</span><span class="sxs-lookup"><span data-stu-id="1d7d1-178">The following are Audio Conferencing capabilities that are not supported in Audio Conferencing with Direct Routing for GCC High and DoD:</span></span>

- <span data-ttu-id="1d7d1-179">Уведомления о входе и выходе с помощью записи имен.</span><span class="sxs-lookup"><span data-stu-id="1d7d1-179">Entry and exit notifications using name recording.</span></span> <span data-ttu-id="1d7d1-180">Для голосовой конференции с прямым маршрутом уведомления о входе и выходе воспроизводится на собрании как звуки.</span><span class="sxs-lookup"><span data-stu-id="1d7d1-180">For Audio Conferencing with Direct Routing, entry and exit notifications are played in the meeting as tones.</span></span>

- <span data-ttu-id="1d7d1-181">Политики ограничения исходящих звонков для голосовой конференции.</span><span class="sxs-lookup"><span data-stu-id="1d7d1-181">Outbound calling restriction policies for Audio Conferencing.</span></span> <span data-ttu-id="1d7d1-182">Элементы управления на уровне пользователей для ограничения исходящих вызовов не относятся к вызовам для собраний, направляемым через прямую маршрутизацию.</span><span class="sxs-lookup"><span data-stu-id="1d7d1-182">User-level controls to restrict outbound calls aren't applicable to meeting dial-out calls routed via Direct Routing.</span></span>

- <span data-ttu-id="1d7d1-183">Отключите использование бесплатных номеров для организатора собраний.</span><span class="sxs-lookup"><span data-stu-id="1d7d1-183">Disable the usage of toll-free numbers for the meetings specific organizer.</span></span> <span data-ttu-id="1d7d1-184">Элементы управления на уровне пользователей, которые ограничивают использование бесплатных номеров для присоединения к собраниям Организации, не применимы к вызовам, направляемым через прямую маршрутизацию.</span><span class="sxs-lookup"><span data-stu-id="1d7d1-184">User-level controls to restrict the usage of toll-free numbers to join the meetings of your organization aren't applicable to calls routed via Direct Routing.</span></span>

- <span data-ttu-id="1d7d1-185">Отправка пользователям уведомлений об изменении их параметров.</span><span class="sxs-lookup"><span data-stu-id="1d7d1-185">Sending notification emails to users when their settings change.</span></span> <span data-ttu-id="1d7d1-186">Уведомления о голосовой конференции не поддерживаются для голосовой связи с прямой маршрутизацией на GCC High и DoD.</span><span class="sxs-lookup"><span data-stu-id="1d7d1-186">Audio Conferencing notification emails aren't supported for Audio Conferencing with Direct Routing for GCC High and DoD.</span></span>
