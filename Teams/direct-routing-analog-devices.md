---
title: Прямая маршрутия — подключение аналоговых устройств
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.reviewer: NMuravlyannikov
ms.topic: conceptual
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: В этой статье вы узнаете, как использовать аналоговые устройства с Телефон (Майкрософт) System Direct Routing.
ms.openlocfilehash: dc49c22dceffda6905d1f57652fd14d584d02cf6
ms.sourcegitcommit: 9d446485aa842abbdcd34d946b247166c2bf1610
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/25/2021
ms.locfileid: "52642099"
---
# <a name="how-to-use-analog-devices-with-phone-system-direct-routing"></a><span data-ttu-id="d4493-103">Использование аналоговых устройств с телефонная система прямой маршрутии</span><span class="sxs-lookup"><span data-stu-id="d4493-103">How to use analog devices with Phone System Direct Routing</span></span>

<span data-ttu-id="d4493-104">В этой статье описано использование аналоговых устройств с телефонная система прямой маршрутии.</span><span class="sxs-lookup"><span data-stu-id="d4493-104">This article describes how to use analog devices with Phone System Direct Routing.</span></span> <span data-ttu-id="d4493-105">Чтобы подключить аналоговые устройства к прямой маршрутике, необходимо использовать аналоговый адаптер телефонии (ATA), который должен поддерживаться сертифицированным поставщиком пограничного контроллера сеанса .</span><span class="sxs-lookup"><span data-stu-id="d4493-105">To connect analog devices to Direct Routing, you must use an Analog Telephony Adapter (ATA), and this adapter must be supported by the certified Session Border Controller (SBC) vendor.</span></span> 

<span data-ttu-id="d4493-106">Когда пользователь звонит с аналогового устройства, сигнальный поток и мультимедиа проходят через адаптер аналоговой телефонии (ATA) к SBC.</span><span class="sxs-lookup"><span data-stu-id="d4493-106">When a user makes a call from an analog device, the signaling and media flow through the Analog Telephony Adapter (ATA) to the SBC.</span></span>  <span data-ttu-id="d4493-107">SBC отправляет звонок на конечную точку Microsoft Teams или в телефонную сеть общего перейти на телефонную сеть (STN), основанную на внутренней таблице маршрутов.</span><span class="sxs-lookup"><span data-stu-id="d4493-107">The SBC sends the call to a Microsoft Teams endpoint or to the Public Switched Telephone Network (PSTN) based on the internal routing table.</span></span>  <span data-ttu-id="d4493-108">Когда устройство совершает звонок, маршрут, который он принимает, зависит от политик маршрутинга, созданных для устройства.</span><span class="sxs-lookup"><span data-stu-id="d4493-108">When a device makes a call, the route it takes depends on the routing policies created for the device.</span></span>

<span data-ttu-id="d4493-109">На приведенной ниже схеме Прямая маршрутная маршрутия настроена таким образом, что все звонки Teams на номера между +1425 4XX XX XX и +1425 5XX XX XX XX должны принимать красный маршрут (пунктирная линия), а все звонки по ПСС между +1425 4XX XX XX и любыми другими номерами, кроме номера +1425 5XX XX XX, должны проходить по синему маршруту (сплошная линия).</span><span class="sxs-lookup"><span data-stu-id="d4493-109">In the following diagram, Direct Routing is configured so that any Teams calls to and from the numbers between +1425 4XX XX XX and +1425 5XX XX XX must take the red route (dotted line), and any PSTN call to and from numbers between +1425 4XX XX XX and any other number except number range +1425 5XX XX XX must take the blue route (solid line).</span></span> 

> [!div class="mx-imgBorder"]
> <span data-ttu-id="d4493-110">![Схема с настройкой прямой маршрутики](media/direct-routing-analog-device.png)</span><span class="sxs-lookup"><span data-stu-id="d4493-110">![Diagram showing Direct Routing configuration](media/direct-routing-analog-device.png)</span></span>

## <a name="example--how-to-configure-the-use-of-analog-devices-with-direct-routing"></a><span data-ttu-id="d4493-111">Пример: настройка использования аналоговых устройств с прямой маршрутией</span><span class="sxs-lookup"><span data-stu-id="d4493-111">Example:  How to configure the use of analog devices with Direct Routing</span></span>

<span data-ttu-id="d4493-112">Чтобы настроить использование аналоговых устройств с прямой маршрутией, необходимо подключить адаптер аналоговой телефонии к SBC и настроить SBC для работы с прямой маршрутией.</span><span class="sxs-lookup"><span data-stu-id="d4493-112">To configure the use of analog devices with Direct Routing, you must connect the Analog Telephony Adapter to the SBC, and configure the SBC to work with Direct Routing.</span></span> 

<span data-ttu-id="d4493-113">В этом примере вы можете сделать следующее:</span><span class="sxs-lookup"><span data-stu-id="d4493-113">This example walks you through the following steps:</span></span>

1. <span data-ttu-id="d4493-114">Подключение SBC к прямой маршрутике.</span><span class="sxs-lookup"><span data-stu-id="d4493-114">Connect the SBC to Direct Routing.</span></span>
2. <span data-ttu-id="d4493-115">Создайте службу использования ДНР.</span><span class="sxs-lookup"><span data-stu-id="d4493-115">Create the PSTN Usage.</span></span>
3. <span data-ttu-id="d4493-116">Создайте голосовой маршрут и связываете его с использованием ПСПС.</span><span class="sxs-lookup"><span data-stu-id="d4493-116">Create a voice route and associate it with the PSTN Usage.</span></span>
4. <span data-ttu-id="d4493-117">Назначьте голосовой маршрут использованию ОКП.</span><span class="sxs-lookup"><span data-stu-id="d4493-117">Assign the voice route to the PSTN Usage.</span></span>
5. <span data-ttu-id="d4493-118">В этом режиме можно включить сетевого пользователя.</span><span class="sxs-lookup"><span data-stu-id="d4493-118">Enable the online user.</span></span>
6. <span data-ttu-id="d4493-119">Назначьте политику голосового маршрута пользователю.</span><span class="sxs-lookup"><span data-stu-id="d4493-119">Assign the voice route policy to the user.</span></span>
7. <span data-ttu-id="d4493-120">Создайте голосовой маршрут для аналогового устройства.</span><span class="sxs-lookup"><span data-stu-id="d4493-120">Create a voice route for an analog device.</span></span>

<span data-ttu-id="d4493-121">Сведения о том, как подключить ATA к SBC и настроить SBC, см. в руководстве производителя SBC:</span><span class="sxs-lookup"><span data-stu-id="d4493-121">For information on how to connect an ATA to an SBC and configure the SBC, see your SBC manufacturer configuration guide:</span></span>

- [<span data-ttu-id="d4493-122">Документация по настройке AudioCodes</span><span class="sxs-lookup"><span data-stu-id="d4493-122">AudioCodes configuration documentation</span></span>](https://www.audiocodes.com/media/14278/connecting-audiocodes-sbc-with-analog-device-to-microsoft-teams-direct-routing-enterprise-model-configuration-note.pdf)

- [<span data-ttu-id="d4493-123">Документация по конфигурации ленты</span><span class="sxs-lookup"><span data-stu-id="d4493-123">Ribbon configuration documentation</span></span>](https://support.sonus.net/display/UXDOC81/Connect+SBC+Edge+to+Microsoft+Teams+Direct+Routing+to+Support+Analog+Devices)
- [<span data-ttu-id="d4493-124">Документация по конфигурации Oracle</span><span class="sxs-lookup"><span data-stu-id="d4493-124">Oracle configuration documentation</span></span>](https://www.oracle.com/technical-resources/documentation/acme-packet.html#Link-MicrosoftTeams)

## <a name="step-1--connect-the-sbc-to-direct-routing"></a><span data-ttu-id="d4493-125">Шаг 1.</span><span class="sxs-lookup"><span data-stu-id="d4493-125">Step 1.</span></span>  <span data-ttu-id="d4493-126">Подключение SBC к прямой маршрутике</span><span class="sxs-lookup"><span data-stu-id="d4493-126">Connect the SBC to Direct Routing</span></span>

<span data-ttu-id="d4493-127">Следующая команда настраивает подключение SBC следующим образом:</span><span class="sxs-lookup"><span data-stu-id="d4493-127">The following command configures the SBC connection as follows:</span></span>

- <span data-ttu-id="d4493-128">FQDN sbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="d4493-128">FQDN sbc.contoso.com</span></span>
- <span data-ttu-id="d4493-129">Сигнальный порт 5068</span><span class="sxs-lookup"><span data-stu-id="d4493-129">Signaling port 5068</span></span>
- <span data-ttu-id="d4493-130">Режим обхода мультимедиа</span><span class="sxs-lookup"><span data-stu-id="d4493-130">Media bypass mode</span></span>
- <span data-ttu-id="d4493-131">Сведения из истории вызовов, переадваренные на SBC-</span><span class="sxs-lookup"><span data-stu-id="d4493-131">Call history information forwarded to the SBC-</span></span>
- <span data-ttu-id="d4493-132">Заглавная точка p-Висячих удостоверений (PAI), переадвароваемая вместе с вызовом</span><span class="sxs-lookup"><span data-stu-id="d4493-132">P-Asserted-Identity (PAI) header forwarded along with the call</span></span> 

```powershell
PS C:\> New-CsOnlinePSTNGateway -FQDN sbc.contoso.com -SIPSignalingPort 5068 -ForwardCallHistory $true -ForwardPAI $true -MediaBypass $true -Enabled $true 
```

## <a name="step-2--create-the-pstn-usage"></a><span data-ttu-id="d4493-133">Шаг 2. Создание использования ОКП</span><span class="sxs-lookup"><span data-stu-id="d4493-133">Step 2:  Create the PSTN usage</span></span> 

<span data-ttu-id="d4493-134">Следующая команда создает пустое использование ОКП.</span><span class="sxs-lookup"><span data-stu-id="d4493-134">The next command creates an empty PSTN usage.</span></span> <span data-ttu-id="d4493-135">Использование ОКП через Интернет — это строки значений, которые используются для авторизации вызовов.</span><span class="sxs-lookup"><span data-stu-id="d4493-135">Online PSTN usages are string values that are used for call authorization.</span></span> <span data-ttu-id="d4493-136">Использование ОКП через Интернет связывает голосовую политику в Интернете с маршрутом.</span><span class="sxs-lookup"><span data-stu-id="d4493-136">An online PSTN usage links an online voice policy to a route.</span></span> <span data-ttu-id="d4493-137">В этом примере строка "Interop" добавляется в текущий список доступных использования ПСОП.</span><span class="sxs-lookup"><span data-stu-id="d4493-137">This example adds the string "Interop" to the current list of available PSTN usages.</span></span> 

```powershell
PS C:\> Set-CsOnlinePstnUsage -Identity global -Usage @{add="Interop"} 
```

## <a name="step-3--create-a-voice-route-and-associate-it-with-the-pstn-usage"></a><span data-ttu-id="d4493-138">Шаг 3. Создайте голосовой маршрут и связать его с использованием ННР:</span><span class="sxs-lookup"><span data-stu-id="d4493-138">Step 3:  Create a voice route and associate it with the PSTN usage:</span></span>

<span data-ttu-id="d4493-139">Эта команда создает новый сетевой голосовой маршрут с идентификатором "аналоговое интероп" для диапазона номеров +1425 XXX XX XX.</span><span class="sxs-lookup"><span data-stu-id="d4493-139">This command creates a new online voice route with the identity “analog-interop” for the number range +1425 XXX XX XX.</span></span>  <span data-ttu-id="d4493-140">Голосовой маршрут применяется к списку сетевых шлюзов sbc.contoso.com и связывает маршрут с использованием ТСОП через Интернет "Interop".</span><span class="sxs-lookup"><span data-stu-id="d4493-140">The voice route is applicable to a list of online gateways sbc.contoso.com and associates the route with online PSTN usage “Interop”.</span></span> <span data-ttu-id="d4493-141">Голосовой маршрут включает регулярное выражение, определя которое определяет номера телефонов, которые будут маршрутизданы по заданным голосовым маршрутам:</span><span class="sxs-lookup"><span data-stu-id="d4493-141">A voice route includes a regular expression that identifies which phone numbers will be routed through a given voice route:</span></span>

```powershell
PS C:\> New-CsOnlineVoiceRoute -Identity analog-interop -NumberPattern "^\+1(425)(\d{7})$" -OnlinePstnGatewayList sbc.contoso.com -Priority 1 -OnlinePstnUsages "Interop"
```

## <a name="step-4-assign-the-voice-route-to-the-pstn-usage"></a><span data-ttu-id="d4493-142">Шаг 4. Назначение голосового маршрута для использования ПСПС:</span><span class="sxs-lookup"><span data-stu-id="d4493-142">Step 4: Assign the voice route to the PSTN usage:</span></span>

<span data-ttu-id="d4493-143">Эта команда создает новую политику маршрутизации голосовой связи для каждого пользователя в Интернете с идентификатором AnalogInteropPolicy.</span><span class="sxs-lookup"><span data-stu-id="d4493-143">This command creates a new online per-user voice routing policy with the Identity “AnalogInteropPolicy”.</span></span> <span data-ttu-id="d4493-144">Этой политике назначено одно использование ПСОП в Интернете: "Interop".</span><span class="sxs-lookup"><span data-stu-id="d4493-144">This policy is assigned a single online PSTN usage: “Interop”.</span></span>

```powershell
PS C:\> New-CsOnlineVoiceRoutingPolicy -Identity "AnalogInteropPolicy" -Name "AnalogInteropPolicy" -OnlinePstnUsages "Interop"
```

## <a name="step-5-enable-the-online-user"></a><span data-ttu-id="d4493-145">Шаг 5. Включить пользователя в Сети</span><span class="sxs-lookup"><span data-stu-id="d4493-145">Step 5: Enable the online user</span></span>

<span data-ttu-id="d4493-146">Эта команда изменяет учетную запись пользователя с помощью exampleuser@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="d4493-146">This command modifies the user account with the Identity exampleuser@contoso.com.</span></span> <span data-ttu-id="d4493-147">В этом случае учетная запись будет изменена, чтобы включить Корпоративная голосовая связь, внедрение VoIP корпорации Майкрософт, с включенной голосовой почтой и назначит номер +14255000000 этому пользователю.</span><span class="sxs-lookup"><span data-stu-id="d4493-147">In this case, the account is modified to enable Enterprise Voice, the Microsoft implementation of VoIP, with enabled voice mail and assigns the number +14255000000 to this user.</span></span>  <span data-ttu-id="d4493-148">Эту команду следует выполнить для каждого пользователя Teams (за исключением пользователей устройств ATA) в клиенте компании.</span><span class="sxs-lookup"><span data-stu-id="d4493-148">This command should be run for each Teams user (excluding ATA device users) in the company tenant.</span></span>

```powershell
PS C:\> Set-CsUser -Identity "exampleuser@contoso.com" -EnterpriseVoiceEnabled $True -HostedVoiceMail $True -OnPremLineUri "tel:+14255000000"
```

## <a name="step-6-assign-the-voice-route-policy-to-a-user"></a><span data-ttu-id="d4493-149">Шаг 6. Назначение политики голосового маршрута пользователю</span><span class="sxs-lookup"><span data-stu-id="d4493-149">Step 6: Assign the voice route policy to a user</span></span>

<span data-ttu-id="d4493-150">Эта команда назначает политику сетевой маршрутизации голосовой маршрутизации "на пользователя" (AnalogInteropPolicy) пользователю с идентификаторами exampleuser@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="d4493-150">This command assigns the per-user online voice routing policy AnalogInteropPolicy to the user with the identity exampleuser@contoso.com.</span></span>  <span data-ttu-id="d4493-151">Эту команду следует выполнить для каждого пользователя Teams (за исключением пользователей устройств ATA) в клиенте компании.</span><span class="sxs-lookup"><span data-stu-id="d4493-151">This command should be run for each Teams user (excluding ATA device users) in the company tenant.</span></span>

```powershell
PS C:\> Grant-CsOnlineVoiceRoutingPolicy -Identity "exampleuser@contoso.com" -PolicyName "AnalogInteropPolicy" 
```

## <a name="step-7--create-a-voice-route-for-an-analog-device"></a><span data-ttu-id="d4493-152">Шаг 7. Создание голосового маршрута для аналогового устройства</span><span class="sxs-lookup"><span data-stu-id="d4493-152">Step 7:  Create a voice route for an analog device</span></span>

<span data-ttu-id="d4493-153">Эта команда создает сетевой голосовой маршрут с идентификатором "аналоговое интероп" для диапазона номеров +1425 4XX XX XX, применимого к списку сетевых шлюзов sbc.contoso.com, и связывает его с использованием ТСОП через Интернет "Interop".</span><span class="sxs-lookup"><span data-stu-id="d4493-153">This command creates an online voice route with identity “analog-interop” for number range +1425 4XX XX XX applicable to a list of online gateways sbc.contoso.com and associates it with online PSTN usage “Interop”.</span></span>  <span data-ttu-id="d4493-154">Эту команду следует выполнить для каждого аналогового устройства с соответствующим шаблоном номера телефона.</span><span class="sxs-lookup"><span data-stu-id="d4493-154">This command should be run for each analog device with appropriate phone number pattern.</span></span> <span data-ttu-id="d4493-155">Кроме того, при настройке сетевого голосового маршрута на одном из предыдущих этапов можно использовать правильный шаблон номера для аналоговых устройств.</span><span class="sxs-lookup"><span data-stu-id="d4493-155">Alternatively, a proper number pattern for analog devices can be used while configuring the online voice route during one of the previous steps.</span></span>

```powershell
PS C:\> New-CsOnlineVoiceRoute -Identity analog-interop -NumberPattern "^\+1(4254)(\d{6})$"  -OnlinePstnGatewayList sbc.contoso.com -Priority 1 -OnlinePstnUsages "Interop"
```

## <a name="considerations"></a><span data-ttu-id="d4493-156">Рекомендации</span><span class="sxs-lookup"><span data-stu-id="d4493-156">Considerations</span></span>

- <span data-ttu-id="d4493-157">Если не указано иное, аналоговое устройство — это любое устройство, на которое можно отправлять цифры DTMF для звонка.</span><span class="sxs-lookup"><span data-stu-id="d4493-157">Unless otherwise note, an analog device is any device that can send DTMF digits to place a call.</span></span> <span data-ttu-id="d4493-158">Например, аналоговые телефоны, факсы и накладные страницы.</span><span class="sxs-lookup"><span data-stu-id="d4493-158">For example, analog phones, fax machines, and overhead pagers.</span></span>

- <span data-ttu-id="d4493-159">Аналоговые телефоны, подключенные к ATA, невозможно найти в Teams.</span><span class="sxs-lookup"><span data-stu-id="d4493-159">Analog phones connected to an ATA are not searchable from Teams.</span></span> <span data-ttu-id="d4493-160">Teams пользователи должны вручную ввести номер телефона, связанный с устройством, чтобы позвонить на это устройство.</span><span class="sxs-lookup"><span data-stu-id="d4493-160">Teams users must manually enter the phone number associated with the device to call that device.</span></span>  
 

## <a name="see-also"></a><span data-ttu-id="d4493-161">См. также</span><span class="sxs-lookup"><span data-stu-id="d4493-161">See also</span></span>

[<span data-ttu-id="d4493-162">Планирование прямой маршрутизации</span><span class="sxs-lookup"><span data-stu-id="d4493-162">Plan Direct Routing</span></span>](direct-routing-plan.md)

[<span data-ttu-id="d4493-163">Настройка прямой маршрутизации</span><span class="sxs-lookup"><span data-stu-id="d4493-163">Configure Direct Routing</span></span>](direct-routing-configure.md)
