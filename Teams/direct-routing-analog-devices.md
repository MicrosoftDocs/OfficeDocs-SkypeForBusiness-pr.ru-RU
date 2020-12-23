---
title: Прямая маршрутия — аналоговые устройства для подключения
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
description: Из этой статьи вы узнаете, как использовать аналоговые устройства с маршрутигой Microsoft Phone System Direct Routing.
ms.openlocfilehash: 0c6531a29e23e736a84db9bf8571abab2e13942a
ms.sourcegitcommit: f9daef3213a305676127cf5140af907e3b96d046
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/07/2020
ms.locfileid: "48369194"
---
# <a name="how-to-use-analog-devices-with-phone-system-direct-routing"></a><span data-ttu-id="96b8c-103">Как использовать аналоговые устройства с маршрутиго из телефонной системы</span><span class="sxs-lookup"><span data-stu-id="96b8c-103">How to use analog devices with Phone System Direct Routing</span></span>

<span data-ttu-id="96b8c-104">В этой статье описано, как использовать аналоговые устройства с маршрутией Direct Routing телефонной системы.</span><span class="sxs-lookup"><span data-stu-id="96b8c-104">This article describes how to use analog devices with Phone System Direct Routing.</span></span> <span data-ttu-id="96b8c-105">Для подключения аналоговых устройств к прямой маршрутике необходимо использовать аналоговый адаптер телефонии (ATA), который должен поддерживаться сертифицированным поставщиком граничного контроллера сеанса (SBC).</span><span class="sxs-lookup"><span data-stu-id="96b8c-105">To connect analog devices to Direct Routing, you must use an Analog Telephony Adapter (ATA), and this adapter must be supported by the certified Session Border Controller (SBC) vendor.</span></span> 

<span data-ttu-id="96b8c-106">Когда пользователь совершает звонок с аналогового устройства, сигнальный поток и мультимедиа проходят через адаптер аналоговой телефонии (ATA) на SBC.</span><span class="sxs-lookup"><span data-stu-id="96b8c-106">When a user makes a call from an analog device, the signaling and media flow through the Analog Telephony Adapter (ATA) to the SBC.</span></span>  <span data-ttu-id="96b8c-107">SBC отправляет звонок на конечную точку Microsoft Teams или в телефонную сеть общего перейти на основе внутренней таблицы маршрутов.</span><span class="sxs-lookup"><span data-stu-id="96b8c-107">The SBC sends the call to a Microsoft Teams endpoint or to the Public Switched Telephone Network (PSTN) based on the internal routing table.</span></span>  <span data-ttu-id="96b8c-108">Когда устройство совершает звонок, маршрут, который он принимает, зависит от политик маршрутинга, созданных для устройства.</span><span class="sxs-lookup"><span data-stu-id="96b8c-108">When a device makes a call, the route it takes depends on the routing policies created for the device.</span></span>

<span data-ttu-id="96b8c-109">На следующей схеме Прямая маршрутия настроена таким образом, что все звонки Teams на номера между +1425 4XX XX XX и +1425 5XX XX XX должны принимать красный маршрут (пунктирная линия), а все звонки по ННР между номерами между +1425 4XX XX и любыми другими номерами, кроме диапазона +1425 5XX XX, должны проходить синим маршрутом (сплошная линия).</span><span class="sxs-lookup"><span data-stu-id="96b8c-109">In the following diagram, Direct Routing is configured so that any Teams calls to and from the numbers between +1425 4XX XX XX and +1425 5XX XX XX must take the red route (dotted line), and any PSTN call to and from numbers between +1425 4XX XX XX and any other number except number range +1425 5XX XX XX must take the blue route (solid line).</span></span> 

> [!div class="mx-imgBorder"]
> <span data-ttu-id="96b8c-110">![Схема с настройкой прямой маршрутации](media/direct-routing-analog-device.png)</span><span class="sxs-lookup"><span data-stu-id="96b8c-110">![Diagram showing Direct Routing configuration](media/direct-routing-analog-device.png)</span></span>

## <a name="example--how-to-configure-the-use-of-analog-devices-with-direct-routing"></a><span data-ttu-id="96b8c-111">Пример: настройка использования аналоговых устройств с прямой маршрутией</span><span class="sxs-lookup"><span data-stu-id="96b8c-111">Example:  How to configure the use of analog devices with Direct Routing</span></span>

<span data-ttu-id="96b8c-112">Чтобы настроить использование аналоговых устройств с прямой маршрутией, необходимо подключить адаптер аналоговой телефонии к SBC и настроить SBC для работы с прямой маршрутией.</span><span class="sxs-lookup"><span data-stu-id="96b8c-112">To configure the use of analog devices with Direct Routing, you must connect the Analog Telephony Adapter to the SBC, and configure the SBC to work with Direct Routing.</span></span> 

<span data-ttu-id="96b8c-113">В этом примере вы можете сделать следующее:</span><span class="sxs-lookup"><span data-stu-id="96b8c-113">This example walks you through the following steps:</span></span>

1. <span data-ttu-id="96b8c-114">Подключите SBC к прямой маршрутике.</span><span class="sxs-lookup"><span data-stu-id="96b8c-114">Connect the SBC to Direct Routing.</span></span>
2. <span data-ttu-id="96b8c-115">Создайте службу использования ННР.</span><span class="sxs-lookup"><span data-stu-id="96b8c-115">Create the PSTN Usage.</span></span>
3. <span data-ttu-id="96b8c-116">Создайте голосовой маршрут и связать его с использованием ННР.</span><span class="sxs-lookup"><span data-stu-id="96b8c-116">Create a voice route and associate it with the PSTN Usage.</span></span>
4. <span data-ttu-id="96b8c-117">Назначьте голосовой маршрут использованию ННР.</span><span class="sxs-lookup"><span data-stu-id="96b8c-117">Assign the voice route to the PSTN Usage.</span></span>
5. <span data-ttu-id="96b8c-118">В этом режиме в сети можно включить пользователя.</span><span class="sxs-lookup"><span data-stu-id="96b8c-118">Enable the online user.</span></span>
6. <span data-ttu-id="96b8c-119">Назначьте политику голосового пути пользователю.</span><span class="sxs-lookup"><span data-stu-id="96b8c-119">Assign the voice route policy to the user.</span></span>
7. <span data-ttu-id="96b8c-120">Создайте голосовой маршрут для аналогового устройства.</span><span class="sxs-lookup"><span data-stu-id="96b8c-120">Create a voice route for an analog device.</span></span>

<span data-ttu-id="96b8c-121">Сведения о том, как подключить ATA к SBC и настроить его, см. в руководстве производителя:</span><span class="sxs-lookup"><span data-stu-id="96b8c-121">For information on how to connect an ATA to an SBC and configure the SBC, see your SBC manufacturer configuration guide:</span></span>

- [<span data-ttu-id="96b8c-122">Документация по настройке AudioCodes</span><span class="sxs-lookup"><span data-stu-id="96b8c-122">AudioCodes configuration documentation</span></span>](https://www.audiocodes.com/media/14278/connecting-audiocodes-sbc-with-analog-device-to-microsoft-teams-direct-routing-enterprise-model-configuration-note.pdf)

- [<span data-ttu-id="96b8c-123">Документация по конфигурации ленты</span><span class="sxs-lookup"><span data-stu-id="96b8c-123">Ribbon configuration documentation</span></span>](https://support.sonus.net/display/UXDOC81/Connect+SBC+Edge+to+Microsoft+Teams+Direct+Routing+to+Support+Analog+Devices)

## <a name="step-1--connect-the-sbc-to-direct-routing"></a><span data-ttu-id="96b8c-124">Шаг 1.</span><span class="sxs-lookup"><span data-stu-id="96b8c-124">Step 1.</span></span>  <span data-ttu-id="96b8c-125">Подключение SBC к прямой маршрутике</span><span class="sxs-lookup"><span data-stu-id="96b8c-125">Connect the SBC to Direct Routing</span></span>

<span data-ttu-id="96b8c-126">Следующая команда настраивает подключение SBC следующим образом:</span><span class="sxs-lookup"><span data-stu-id="96b8c-126">The following command configures the SBC connection as follows:</span></span>

- <span data-ttu-id="96b8c-127">FQDN sbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="96b8c-127">FQDN sbc.contoso.com</span></span>
- <span data-ttu-id="96b8c-128">Сигнальный порт 5068</span><span class="sxs-lookup"><span data-stu-id="96b8c-128">Signaling port 5068</span></span>
- <span data-ttu-id="96b8c-129">Режим обхода мультимедиа</span><span class="sxs-lookup"><span data-stu-id="96b8c-129">Media bypass mode</span></span>
- <span data-ttu-id="96b8c-130">Сведения из истории вызовов, переадваренные на SBC-</span><span class="sxs-lookup"><span data-stu-id="96b8c-130">Call history information forwarded to the SBC-</span></span>
- <span data-ttu-id="96b8c-131">Заглавная точка с заглавной темой P-Темы (PAI), перенаверенная вместе с вызовом</span><span class="sxs-lookup"><span data-stu-id="96b8c-131">P-Asserted-Identity (PAI) header forwarded along with the call</span></span> 

```powershell
PS C:\> New-CsOnlinePSTNGateway -FQDN sbc.contoso.com -SIPSignalingPort 5068 -ForwardCallHistory $true -ForwardPAI $true -MediaBypass $true -Enabled $true 
```

## <a name="step-2--create-the-pstn-usage"></a><span data-ttu-id="96b8c-132">Шаг 2. Создание службы ННР</span><span class="sxs-lookup"><span data-stu-id="96b8c-132">Step 2:  Create the PSTN usage</span></span> 

<span data-ttu-id="96b8c-133">Следующая команда создает пустое использование ННП.</span><span class="sxs-lookup"><span data-stu-id="96b8c-133">The next command creates an empty PSTN usage.</span></span> <span data-ttu-id="96b8c-134">Использование сетевых ОКП — это строки значений, которые используются для авторизации вызовов.</span><span class="sxs-lookup"><span data-stu-id="96b8c-134">Online PSTN usages are string values that are used for call authorization.</span></span> <span data-ttu-id="96b8c-135">Использование онлайн-НН связывает веб-политику голосовой связи с маршрутом.</span><span class="sxs-lookup"><span data-stu-id="96b8c-135">An online PSTN usage links an online voice policy to a route.</span></span> <span data-ttu-id="96b8c-136">В этом примере строка "Interop" добавляется в текущий список доступных использования ОКП.</span><span class="sxs-lookup"><span data-stu-id="96b8c-136">This example adds the string "Interop" to the current list of available PSTN usages.</span></span> 

```powershell
PS C:\> Set-CsOnlinePstnUsage -Identity global -Usage @{add="Interop"} 
```

## <a name="step-3--create-a-voice-route-and-associate-it-with-the-pstn-usage"></a><span data-ttu-id="96b8c-137">Шаг 3. Создайте голосовой маршрут и соблюсти его с использованием ННР:</span><span class="sxs-lookup"><span data-stu-id="96b8c-137">Step 3:  Create a voice route and associate it with the PSTN usage:</span></span>

<span data-ttu-id="96b8c-138">Эта команда создает новый сетевой голосовой маршрут с идентификатором "аналог-interop" для диапазона номеров +1425 XXX XX XX.</span><span class="sxs-lookup"><span data-stu-id="96b8c-138">This command creates a new online voice route with the identity “analog-interop” for the number range +1425 XXX XX XX.</span></span>  <span data-ttu-id="96b8c-139">Голосовой маршрут применяется к списку сетевых sbc.contoso.com и связывает маршрут с использованием интернет-ТСОП "Interop".</span><span class="sxs-lookup"><span data-stu-id="96b8c-139">The voice route is applicable to a list of online gateways sbc.contoso.com and associates the route with online PSTN usage “Interop”.</span></span> <span data-ttu-id="96b8c-140">Голосовой маршрут включает регулярное выражение, определя которое определяет номера телефонов, которые будут маршрутизовыы через заданный голосовой маршрут:</span><span class="sxs-lookup"><span data-stu-id="96b8c-140">A voice route includes a regular expression that identifies which phone numbers will be routed through a given voice route:</span></span>

```powershell
PS C:\> New-CsOnlineVoiceRoute -Identity analog-interop -NumberPattern "^\+1(425)(\d{7}])$" -OnlinePstnGatewayList sbc.contoso.com -Priority 1 -OnlinePstnUsages "Interop"
```

## <a name="step-4-assign-the-voice-route-to-the-pstn-usage"></a><span data-ttu-id="96b8c-141">Шаг 4. Назначение голосового маршрута для использования ННР:</span><span class="sxs-lookup"><span data-stu-id="96b8c-141">Step 4: Assign the voice route to the PSTN usage:</span></span>

<span data-ttu-id="96b8c-142">Эта команда создает новую политику сетевой маршрутизации голосовой связи "на пользователя" с идентификатором AnalogInteropPolicy.</span><span class="sxs-lookup"><span data-stu-id="96b8c-142">This command creates a new online per-user voice routing policy with the Identity “AnalogInteropPolicy”.</span></span> <span data-ttu-id="96b8c-143">Этой политике назначено одно сетевое использование ННР: "Interop".</span><span class="sxs-lookup"><span data-stu-id="96b8c-143">This policy is assigned a single online PSTN usage: “Interop”.</span></span>

```powershell
PS C:\> New-CsOnlineVoiceRoutingPolicy -Identity "AnalogInteropPolicy" -Name "AnalogInteropPolicy" -OnlinePstnUsages "Interop"
```

## <a name="step-5-enable-the-online-user"></a><span data-ttu-id="96b8c-144">Шаг 5. В том, чтобы включить сетевого пользователя</span><span class="sxs-lookup"><span data-stu-id="96b8c-144">Step 5: Enable the online user</span></span>

<span data-ttu-id="96b8c-145">Эта команда изменяет учетную запись пользователя с помощью exampleuser@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="96b8c-145">This command modifies the user account with the Identity exampleuser@contoso.com.</span></span> <span data-ttu-id="96b8c-146">В этом случае учетная запись будет изменена, чтобы включить Корпоративная голосовая связь — реализацию VoIP (Майкрософт) с включенной голосовой почтой, и назначит номер +14255000000 этому пользователю.</span><span class="sxs-lookup"><span data-stu-id="96b8c-146">In this case, the account is modified to enable Enterprise Voice, the Microsoft implementation of VoIP, with enabled voice mail and assigns the number +14255000000 to this user.</span></span>  <span data-ttu-id="96b8c-147">Эту команду следует выполнить для каждого пользователя Teams (за исключением пользователей устройств ATA) в клиенте компании.</span><span class="sxs-lookup"><span data-stu-id="96b8c-147">This command should be run for each Teams user (excluding ATA device users) in the company tenant.</span></span>

```powershell
PS C:\> Set-CsUser -Identity "exampleuser@contoso.com" -EnterpriseVoiceEnabled $True -HostedVoiceMail $True -OnPremLineUri "tel:+14255000000"
```

## <a name="step-6-assign-the-voice-route-policy-to-a-user"></a><span data-ttu-id="96b8c-148">Шаг 6. Назначение пользователю политики голосового пути</span><span class="sxs-lookup"><span data-stu-id="96b8c-148">Step 6: Assign the voice route policy to a user</span></span>

<span data-ttu-id="96b8c-149">Эта команда назначает политике голосовой маршрутизации для каждого пользователя в Интернете (AnalogInteropPolicy) пользователю с идентификатором exampleuser@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="96b8c-149">This command assigns the per-user online voice routing policy AnalogInteropPolicy to the user with the identity exampleuser@contoso.com.</span></span>  <span data-ttu-id="96b8c-150">Эту команду следует выполнить для каждого пользователя Teams (за исключением пользователей устройств ATA) в клиенте компании.</span><span class="sxs-lookup"><span data-stu-id="96b8c-150">This command should be run for each Teams user (excluding ATA device users) in the company tenant.</span></span>

```powershell
PS C:\> Grant-CsOnlineVoiceRoutingPolicy -Identity "exampleuser@contoso.com" -PolicyName "AnalogInteropPolicy" 
```

## <a name="step-7--create-a-voice-route-for-an-analog-device"></a><span data-ttu-id="96b8c-151">Шаг 7. Создание голосового маршрута для аналогового устройства</span><span class="sxs-lookup"><span data-stu-id="96b8c-151">Step 7:  Create a voice route for an analog device</span></span>

<span data-ttu-id="96b8c-152">Эта команда создает сетевой голосовой маршрут с идентификатором "аналог-interop" для диапазона номеров +1425 4XX XX XX, применимого к списку сетевых шлюзов sbc.contoso.com и связывает его с использованием ТСОП через Интернет "Interop".</span><span class="sxs-lookup"><span data-stu-id="96b8c-152">This command creates an online voice route with identity “analog-interop” for number range +1425 4XX XX XX applicable to a list of online gateways sbc.contoso.com and associates it with online PSTN usage “Interop”.</span></span>  <span data-ttu-id="96b8c-153">Эту команду следует выполнить для каждого аналогового устройства с соответствующим шаблоном номера телефона.</span><span class="sxs-lookup"><span data-stu-id="96b8c-153">This command should be run for each analog device with appropriate phone number pattern.</span></span> <span data-ttu-id="96b8c-154">Кроме того, при настройке сетевого голосового пути на одном из предыдущих этапов можно использовать правильный шаблон номеров для аналоговых устройств.</span><span class="sxs-lookup"><span data-stu-id="96b8c-154">Alternatively, a proper number pattern for analog devices can be used while configuring the online voice route during one of the previous steps.</span></span>

```powershell
PS C:\> New-CsOnlineVoiceRoute -Identity analog-interop -NumberPattern "^\+1(4254)(\d{6}])$"  -OnlinePstnGatewayList sbc.contoso.com -Priority 1 -OnlinePstnUsages "Interop"
```

## <a name="considerations"></a><span data-ttu-id="96b8c-155">Рекомендации</span><span class="sxs-lookup"><span data-stu-id="96b8c-155">Considerations</span></span>

- <span data-ttu-id="96b8c-156">Если не помните иное, аналоговое устройство — это любое устройство, которое может отправлять цифры DTMF для звонка.</span><span class="sxs-lookup"><span data-stu-id="96b8c-156">Unless otherwise note, an analog device is any device that can send DTMF digits to place a call.</span></span> <span data-ttu-id="96b8c-157">Например, аналоговые телефоны, факсы и накладные страницы.</span><span class="sxs-lookup"><span data-stu-id="96b8c-157">For example, analog phones, fax machines, and overhead pagers.</span></span>

- <span data-ttu-id="96b8c-158">В Teams нет аналоговых телефонов, подключенных к ATA.</span><span class="sxs-lookup"><span data-stu-id="96b8c-158">Analog phones connected to an ATA are not searchable from Teams.</span></span> <span data-ttu-id="96b8c-159">Пользователи Teams должны вручную ввести номер телефона, связанный с устройством, чтобы позвонить на это устройство.</span><span class="sxs-lookup"><span data-stu-id="96b8c-159">Teams users must manually enter the phone number associated with the device to call that device.</span></span>  
 

## <a name="see-also"></a><span data-ttu-id="96b8c-160">См. также</span><span class="sxs-lookup"><span data-stu-id="96b8c-160">See also</span></span>

[<span data-ttu-id="96b8c-161">Планирование прямой маршрутизации</span><span class="sxs-lookup"><span data-stu-id="96b8c-161">Plan Direct Routing</span></span>](direct-routing-plan.md)

[<span data-ttu-id="96b8c-162">Настройка прямой маршрутизации</span><span class="sxs-lookup"><span data-stu-id="96b8c-162">Configure Direct Routing</span></span>](direct-routing-configure.md)
