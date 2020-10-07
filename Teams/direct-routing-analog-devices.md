---
title: Прямая маршрутизация – подключение аналоговых устройств
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
description: Прочтите эту статью, чтобы научиться использовать аналоговые устройства с прямой маршрутизацией Microsoft Phone System.
ms.openlocfilehash: 0c6531a29e23e736a84db9bf8571abab2e13942a
ms.sourcegitcommit: f9daef3213a305676127cf5140af907e3b96d046
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/07/2020
ms.locfileid: "48369194"
---
# <a name="how-to-use-analog-devices-with-phone-system-direct-routing"></a><span data-ttu-id="94c60-103">Как использовать аналоговые устройства с прямой маршрутизацией телефонной системы</span><span class="sxs-lookup"><span data-stu-id="94c60-103">How to use analog devices with Phone System Direct Routing</span></span>

<span data-ttu-id="94c60-104">В этой статье рассказывается, как использовать аналоговые устройства с прямой маршрутизацией телефонной системы.</span><span class="sxs-lookup"><span data-stu-id="94c60-104">This article describes how to use analog devices with Phone System Direct Routing.</span></span> <span data-ttu-id="94c60-105">Чтобы соединить аналоговые устройства с прямой маршрутизацией, необходимо использовать аналоговый адаптер телефонной связи (ATA), и этот адаптер должен поддерживаться поставщиком SBC-контроллера границ для сертифицированного сеанса.</span><span class="sxs-lookup"><span data-stu-id="94c60-105">To connect analog devices to Direct Routing, you must use an Analog Telephony Adapter (ATA), and this adapter must be supported by the certified Session Border Controller (SBC) vendor.</span></span> 

<span data-ttu-id="94c60-106">Когда пользователь выполняет звонок с аналогового устройства, передача сигналов и мультимедиа через аналоговый адаптер телефонной связи (ATA) в SBC.</span><span class="sxs-lookup"><span data-stu-id="94c60-106">When a user makes a call from an analog device, the signaling and media flow through the Analog Telephony Adapter (ATA) to the SBC.</span></span>  <span data-ttu-id="94c60-107">SBC отправляет Звонок на конечную точку Microsoft Teams или коммутируемую телефонную сеть общего пользования (PSTN), основанную на таблице внутренней маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="94c60-107">The SBC sends the call to a Microsoft Teams endpoint or to the Public Switched Telephone Network (PSTN) based on the internal routing table.</span></span>  <span data-ttu-id="94c60-108">Когда устройство совершает звонок, маршрут будет зависеть от политики маршрутизации, созданной для устройства.</span><span class="sxs-lookup"><span data-stu-id="94c60-108">When a device makes a call, the route it takes depends on the routing policies created for the device.</span></span>

<span data-ttu-id="94c60-109">На приведенной ниже схеме прямая маршрутизация настраивается таким образом, чтобы любые звонки на другие команды и из них между элементами + 1425 4XX XX XX и + 1425 5XX XX XX должны принимать красный маршрут (пунктирная линия), а 1425 любой другой номер за исключением диапазонов номеров + 1425 5XX XX XX — синий маршрут (сплошная линия).</span><span class="sxs-lookup"><span data-stu-id="94c60-109">In the following diagram, Direct Routing is configured so that any Teams calls to and from the numbers between +1425 4XX XX XX and +1425 5XX XX XX must take the red route (dotted line), and any PSTN call to and from numbers between +1425 4XX XX XX and any other number except number range +1425 5XX XX XX must take the blue route (solid line).</span></span> 

> [!div class="mx-imgBorder"]
> <span data-ttu-id="94c60-110">![Диаграмма, на которой показана прямая настройка маршрутизации](media/direct-routing-analog-device.png)</span><span class="sxs-lookup"><span data-stu-id="94c60-110">![Diagram showing Direct Routing configuration](media/direct-routing-analog-device.png)</span></span>

## <a name="example--how-to-configure-the-use-of-analog-devices-with-direct-routing"></a><span data-ttu-id="94c60-111">Пример: Настройка использования аналоговых устройств с прямой маршрутизацией</span><span class="sxs-lookup"><span data-stu-id="94c60-111">Example:  How to configure the use of analog devices with Direct Routing</span></span>

<span data-ttu-id="94c60-112">Чтобы настроить использование аналоговых устройств с прямой маршрутизацией, необходимо подключить аналоговый адаптер телефонной связи к SBC и настроить SBC для прямого перенаправления.</span><span class="sxs-lookup"><span data-stu-id="94c60-112">To configure the use of analog devices with Direct Routing, you must connect the Analog Telephony Adapter to the SBC, and configure the SBC to work with Direct Routing.</span></span> 

<span data-ttu-id="94c60-113">В этом примере вы просматриваете следующие шаги:</span><span class="sxs-lookup"><span data-stu-id="94c60-113">This example walks you through the following steps:</span></span>

1. <span data-ttu-id="94c60-114">Соединение SBC для прямой маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="94c60-114">Connect the SBC to Direct Routing.</span></span>
2. <span data-ttu-id="94c60-115">Создание использования КТСОП.</span><span class="sxs-lookup"><span data-stu-id="94c60-115">Create the PSTN Usage.</span></span>
3. <span data-ttu-id="94c60-116">Создайте голосовой маршрут и свяжите его с использованием КТСОП.</span><span class="sxs-lookup"><span data-stu-id="94c60-116">Create a voice route and associate it with the PSTN Usage.</span></span>
4. <span data-ttu-id="94c60-117">Назначайте голосовой маршрут для использования PSTN.</span><span class="sxs-lookup"><span data-stu-id="94c60-117">Assign the voice route to the PSTN Usage.</span></span>
5. <span data-ttu-id="94c60-118">Включите пользователя Online.</span><span class="sxs-lookup"><span data-stu-id="94c60-118">Enable the online user.</span></span>
6. <span data-ttu-id="94c60-119">Назначение пользователю политики голосовых маршрутов.</span><span class="sxs-lookup"><span data-stu-id="94c60-119">Assign the voice route policy to the user.</span></span>
7. <span data-ttu-id="94c60-120">Создайте голосовой маршрут для аналогового устройства.</span><span class="sxs-lookup"><span data-stu-id="94c60-120">Create a voice route for an analog device.</span></span>

<span data-ttu-id="94c60-121">Сведения о том, как подключить ATA к SBC и настроить SBC, можно найти в руководстве по настройке производителей SBC.</span><span class="sxs-lookup"><span data-stu-id="94c60-121">For information on how to connect an ATA to an SBC and configure the SBC, see your SBC manufacturer configuration guide:</span></span>

- [<span data-ttu-id="94c60-122">Документация по конфигурации AudioCodes</span><span class="sxs-lookup"><span data-stu-id="94c60-122">AudioCodes configuration documentation</span></span>](https://www.audiocodes.com/media/14278/connecting-audiocodes-sbc-with-analog-device-to-microsoft-teams-direct-routing-enterprise-model-configuration-note.pdf)

- [<span data-ttu-id="94c60-123">Документация по настройке ленты</span><span class="sxs-lookup"><span data-stu-id="94c60-123">Ribbon configuration documentation</span></span>](https://support.sonus.net/display/UXDOC81/Connect+SBC+Edge+to+Microsoft+Teams+Direct+Routing+to+Support+Analog+Devices)

## <a name="step-1--connect-the-sbc-to-direct-routing"></a><span data-ttu-id="94c60-124">Шаг 1.</span><span class="sxs-lookup"><span data-stu-id="94c60-124">Step 1.</span></span>  <span data-ttu-id="94c60-125">Соединение SBC для прямой маршрутизации</span><span class="sxs-lookup"><span data-stu-id="94c60-125">Connect the SBC to Direct Routing</span></span>

<span data-ttu-id="94c60-126">Следующая команда конфигурирует соединение SBC следующим образом:</span><span class="sxs-lookup"><span data-stu-id="94c60-126">The following command configures the SBC connection as follows:</span></span>

- <span data-ttu-id="94c60-127">Полное доменное имя sbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="94c60-127">FQDN sbc.contoso.com</span></span>
- <span data-ttu-id="94c60-128">Передача сигнала на порт 5068</span><span class="sxs-lookup"><span data-stu-id="94c60-128">Signaling port 5068</span></span>
- <span data-ttu-id="94c60-129">Режим обхода мультимедиа</span><span class="sxs-lookup"><span data-stu-id="94c60-129">Media bypass mode</span></span>
- <span data-ttu-id="94c60-130">Данные журнала вызовов, переадресованные в SBC-</span><span class="sxs-lookup"><span data-stu-id="94c60-130">Call history information forwarded to the SBC-</span></span>
- <span data-ttu-id="94c60-131">Заголовок P-Assert-Identity (PAI), пересылаемый вместе с звонком</span><span class="sxs-lookup"><span data-stu-id="94c60-131">P-Asserted-Identity (PAI) header forwarded along with the call</span></span> 

```powershell
PS C:\> New-CsOnlinePSTNGateway -FQDN sbc.contoso.com -SIPSignalingPort 5068 -ForwardCallHistory $true -ForwardPAI $true -MediaBypass $true -Enabled $true 
```

## <a name="step-2--create-the-pstn-usage"></a><span data-ttu-id="94c60-132">Действие 2: создание использования PSTN</span><span class="sxs-lookup"><span data-stu-id="94c60-132">Step 2:  Create the PSTN usage</span></span> 

<span data-ttu-id="94c60-133">Следующая команда создает пустое использование КТСОП.</span><span class="sxs-lookup"><span data-stu-id="94c60-133">The next command creates an empty PSTN usage.</span></span> <span data-ttu-id="94c60-134">Сетевые сети PSTN — это строковые значения, которые используются для авторизации звонков.</span><span class="sxs-lookup"><span data-stu-id="94c60-134">Online PSTN usages are string values that are used for call authorization.</span></span> <span data-ttu-id="94c60-135">Использование сети PSTN – это связь политики голосовой связи через Интернет с маршрутом.</span><span class="sxs-lookup"><span data-stu-id="94c60-135">An online PSTN usage links an online voice policy to a route.</span></span> <span data-ttu-id="94c60-136">Этот пример добавляет строку "взаимодействие" в текущий список доступных использований PSTN.</span><span class="sxs-lookup"><span data-stu-id="94c60-136">This example adds the string "Interop" to the current list of available PSTN usages.</span></span> 

```powershell
PS C:\> Set-CsOnlinePstnUsage -Identity global -Usage @{add="Interop"} 
```

## <a name="step-3--create-a-voice-route-and-associate-it-with-the-pstn-usage"></a><span data-ttu-id="94c60-137">Шаг 3. Создайте голосовой маршрут и свяжите его с использованием КТСОП.</span><span class="sxs-lookup"><span data-stu-id="94c60-137">Step 3:  Create a voice route and associate it with the PSTN usage:</span></span>

<span data-ttu-id="94c60-138">Эта команда создает новый голосовой маршрут с удостоверением "аналогово-Interop" для диапазона чисел + 1425 XXX XX XX.</span><span class="sxs-lookup"><span data-stu-id="94c60-138">This command creates a new online voice route with the identity “analog-interop” for the number range +1425 XXX XX XX.</span></span>  <span data-ttu-id="94c60-139">Маршрут голосовой связи применим к списку интернет-шлюзов sbc.contoso.com и связывает маршрут с использованием взаимодействия по сети PSTN.</span><span class="sxs-lookup"><span data-stu-id="94c60-139">The voice route is applicable to a list of online gateways sbc.contoso.com and associates the route with online PSTN usage “Interop”.</span></span> <span data-ttu-id="94c60-140">Голосовой маршрут включает регулярное выражение, которое определяет, какие номера телефонов будут маршрутизироваться по данному голосовому маршруту.</span><span class="sxs-lookup"><span data-stu-id="94c60-140">A voice route includes a regular expression that identifies which phone numbers will be routed through a given voice route:</span></span>

```powershell
PS C:\> New-CsOnlineVoiceRoute -Identity analog-interop -NumberPattern "^\+1(425)(\d{7}])$" -OnlinePstnGatewayList sbc.contoso.com -Priority 1 -OnlinePstnUsages "Interop"
```

## <a name="step-4-assign-the-voice-route-to-the-pstn-usage"></a><span data-ttu-id="94c60-141">Действие 4: назначьте голосовой маршрут для использования КТСОП:</span><span class="sxs-lookup"><span data-stu-id="94c60-141">Step 4: Assign the voice route to the PSTN usage:</span></span>

<span data-ttu-id="94c60-142">Эта команда создает новую политику голосовой маршрутизации для пользователя Online с удостоверением "AnalogInteropPolicy".</span><span class="sxs-lookup"><span data-stu-id="94c60-142">This command creates a new online per-user voice routing policy with the Identity “AnalogInteropPolicy”.</span></span> <span data-ttu-id="94c60-143">Этой политике назначается единая сетевая использование PSTN: "Interop".</span><span class="sxs-lookup"><span data-stu-id="94c60-143">This policy is assigned a single online PSTN usage: “Interop”.</span></span>

```powershell
PS C:\> New-CsOnlineVoiceRoutingPolicy -Identity "AnalogInteropPolicy" -Name "AnalogInteropPolicy" -OnlinePstnUsages "Interop"
```

## <a name="step-5-enable-the-online-user"></a><span data-ttu-id="94c60-144">Шаг 5: включение пользователя Online</span><span class="sxs-lookup"><span data-stu-id="94c60-144">Step 5: Enable the online user</span></span>

<span data-ttu-id="94c60-145">Эта команда изменяет учетную запись пользователя с помощью удостоверения exampleuser@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="94c60-145">This command modifies the user account with the Identity exampleuser@contoso.com.</span></span> <span data-ttu-id="94c60-146">В этом случае учетная запись будет изменена, чтобы включить корпоративную голосовую связь (Майкрософт) по протоколу VoIP с включенной голосовой почтой и назначить номер + 14255000000 для этого пользователя.</span><span class="sxs-lookup"><span data-stu-id="94c60-146">In this case, the account is modified to enable Enterprise Voice, the Microsoft implementation of VoIP, with enabled voice mail and assigns the number +14255000000 to this user.</span></span>  <span data-ttu-id="94c60-147">Эту команду следует запускать для каждого пользователя Teams (за исключением пользователей устройств ATA) в клиенте компании.</span><span class="sxs-lookup"><span data-stu-id="94c60-147">This command should be run for each Teams user (excluding ATA device users) in the company tenant.</span></span>

```powershell
PS C:\> Set-CsUser -Identity "exampleuser@contoso.com" -EnterpriseVoiceEnabled $True -HostedVoiceMail $True -OnPremLineUri "tel:+14255000000"
```

## <a name="step-6-assign-the-voice-route-policy-to-a-user"></a><span data-ttu-id="94c60-148">Шаг 6: назначение пользователю политики маршрутов голосовой связи</span><span class="sxs-lookup"><span data-stu-id="94c60-148">Step 6: Assign the voice route policy to a user</span></span>

<span data-ttu-id="94c60-149">Эта команда назначает пользователю политику маршрутизации голосовой связи "на пользователя", AnalogInteropPolicy удостоверением exampleuser@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="94c60-149">This command assigns the per-user online voice routing policy AnalogInteropPolicy to the user with the identity exampleuser@contoso.com.</span></span>  <span data-ttu-id="94c60-150">Эту команду следует запускать для каждого пользователя Teams (за исключением пользователей устройств ATA) в клиенте компании.</span><span class="sxs-lookup"><span data-stu-id="94c60-150">This command should be run for each Teams user (excluding ATA device users) in the company tenant.</span></span>

```powershell
PS C:\> Grant-CsOnlineVoiceRoutingPolicy -Identity "exampleuser@contoso.com" -PolicyName "AnalogInteropPolicy" 
```

## <a name="step-7--create-a-voice-route-for-an-analog-device"></a><span data-ttu-id="94c60-151">Шаг 7: Создание голосового маршрута для аналогового устройства</span><span class="sxs-lookup"><span data-stu-id="94c60-151">Step 7:  Create a voice route for an analog device</span></span>

<span data-ttu-id="94c60-152">Эта команда создает онлайновый маршрут с удостоверением "аналогово-Interop" для диапазона номеров + 1425 4XX XX XX, применимый к списку интернет-шлюзов sbc.contoso.com и связывающий его с помощью сети Интернет-ресурсов PSTN.</span><span class="sxs-lookup"><span data-stu-id="94c60-152">This command creates an online voice route with identity “analog-interop” for number range +1425 4XX XX XX applicable to a list of online gateways sbc.contoso.com and associates it with online PSTN usage “Interop”.</span></span>  <span data-ttu-id="94c60-153">Эту команду следует запускать для каждого аналогового устройства с соответствующим шаблоном номера телефона.</span><span class="sxs-lookup"><span data-stu-id="94c60-153">This command should be run for each analog device with appropriate phone number pattern.</span></span> <span data-ttu-id="94c60-154">Кроме того, можно использовать правильный шаблон номера для аналоговых устройств при настройке голосового голосовой связи в течение одного из предыдущих шагов.</span><span class="sxs-lookup"><span data-stu-id="94c60-154">Alternatively, a proper number pattern for analog devices can be used while configuring the online voice route during one of the previous steps.</span></span>

```powershell
PS C:\> New-CsOnlineVoiceRoute -Identity analog-interop -NumberPattern "^\+1(4254)(\d{6}])$"  -OnlinePstnGatewayList sbc.contoso.com -Priority 1 -OnlinePstnUsages "Interop"
```

## <a name="considerations"></a><span data-ttu-id="94c60-155">Рекомендации</span><span class="sxs-lookup"><span data-stu-id="94c60-155">Considerations</span></span>

- <span data-ttu-id="94c60-156">За исключением случаев, когда иное не стоит Примечание, Аналоговое устройство — это любое устройство, которое может отправлять звонки на DTMF-цифры.</span><span class="sxs-lookup"><span data-stu-id="94c60-156">Unless otherwise note, an analog device is any device that can send DTMF digits to place a call.</span></span> <span data-ttu-id="94c60-157">Например, аналоговые телефоны, факсимильные аппараты и пейджеры служебных данных.</span><span class="sxs-lookup"><span data-stu-id="94c60-157">For example, analog phones, fax machines, and overhead pagers.</span></span>

- <span data-ttu-id="94c60-158">Аналоговые телефоны, подключенные к ATA, не поддерживают поиск в Teams.</span><span class="sxs-lookup"><span data-stu-id="94c60-158">Analog phones connected to an ATA are not searchable from Teams.</span></span> <span data-ttu-id="94c60-159">Пользователи Teams должны вручную ввести номер телефона, связанный с устройством, чтобы позвонить этому устройству.</span><span class="sxs-lookup"><span data-stu-id="94c60-159">Teams users must manually enter the phone number associated with the device to call that device.</span></span>  
 

## <a name="see-also"></a><span data-ttu-id="94c60-160">См. также</span><span class="sxs-lookup"><span data-stu-id="94c60-160">See also</span></span>

[<span data-ttu-id="94c60-161">Планирование прямой маршрутизации</span><span class="sxs-lookup"><span data-stu-id="94c60-161">Plan Direct Routing</span></span>](direct-routing-plan.md)

[<span data-ttu-id="94c60-162">Настройка прямой маршрутизации</span><span class="sxs-lookup"><span data-stu-id="94c60-162">Configure Direct Routing</span></span>](direct-routing-configure.md)
