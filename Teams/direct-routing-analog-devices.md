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
# <a name="how-to-use-analog-devices-with-phone-system-direct-routing"></a>Как использовать аналоговые устройства с маршрутиго из телефонной системы

В этой статье описано, как использовать аналоговые устройства с маршрутией Direct Routing телефонной системы. Для подключения аналоговых устройств к прямой маршрутике необходимо использовать аналоговый адаптер телефонии (ATA), который должен поддерживаться сертифицированным поставщиком граничного контроллера сеанса (SBC). 

Когда пользователь совершает звонок с аналогового устройства, сигнальный поток и мультимедиа проходят через адаптер аналоговой телефонии (ATA) на SBC.  SBC отправляет звонок на конечную точку Microsoft Teams или в телефонную сеть общего перейти на основе внутренней таблицы маршрутов.  Когда устройство совершает звонок, маршрут, который он принимает, зависит от политик маршрутинга, созданных для устройства.

На следующей схеме Прямая маршрутия настроена таким образом, что все звонки Teams на номера между +1425 4XX XX XX и +1425 5XX XX XX должны принимать красный маршрут (пунктирная линия), а все звонки по ННР между номерами между +1425 4XX XX и любыми другими номерами, кроме диапазона +1425 5XX XX, должны проходить синим маршрутом (сплошная линия). 

> [!div class="mx-imgBorder"]
> ![Схема с настройкой прямой маршрутации](media/direct-routing-analog-device.png)

## <a name="example--how-to-configure-the-use-of-analog-devices-with-direct-routing"></a>Пример: настройка использования аналоговых устройств с прямой маршрутией

Чтобы настроить использование аналоговых устройств с прямой маршрутией, необходимо подключить адаптер аналоговой телефонии к SBC и настроить SBC для работы с прямой маршрутией. 

В этом примере вы можете сделать следующее:

1. Подключите SBC к прямой маршрутике.
2. Создайте службу использования ННР.
3. Создайте голосовой маршрут и связать его с использованием ННР.
4. Назначьте голосовой маршрут использованию ННР.
5. В этом режиме в сети можно включить пользователя.
6. Назначьте политику голосового пути пользователю.
7. Создайте голосовой маршрут для аналогового устройства.

Сведения о том, как подключить ATA к SBC и настроить его, см. в руководстве производителя:

- [Документация по настройке AudioCodes](https://www.audiocodes.com/media/14278/connecting-audiocodes-sbc-with-analog-device-to-microsoft-teams-direct-routing-enterprise-model-configuration-note.pdf)

- [Документация по конфигурации ленты](https://support.sonus.net/display/UXDOC81/Connect+SBC+Edge+to+Microsoft+Teams+Direct+Routing+to+Support+Analog+Devices)

## <a name="step-1--connect-the-sbc-to-direct-routing"></a>Шаг 1.  Подключение SBC к прямой маршрутике

Следующая команда настраивает подключение SBC следующим образом:

- FQDN sbc.contoso.com
- Сигнальный порт 5068
- Режим обхода мультимедиа
- Сведения из истории вызовов, переадваренные на SBC-
- Заглавная точка с заглавной темой P-Темы (PAI), перенаверенная вместе с вызовом 

```powershell
PS C:\> New-CsOnlinePSTNGateway -FQDN sbc.contoso.com -SIPSignalingPort 5068 -ForwardCallHistory $true -ForwardPAI $true -MediaBypass $true -Enabled $true 
```

## <a name="step-2--create-the-pstn-usage"></a>Шаг 2. Создание службы ННР 

Следующая команда создает пустое использование ННП. Использование сетевых ОКП — это строки значений, которые используются для авторизации вызовов. Использование онлайн-НН связывает веб-политику голосовой связи с маршрутом. В этом примере строка "Interop" добавляется в текущий список доступных использования ОКП. 

```powershell
PS C:\> Set-CsOnlinePstnUsage -Identity global -Usage @{add="Interop"} 
```

## <a name="step-3--create-a-voice-route-and-associate-it-with-the-pstn-usage"></a>Шаг 3. Создайте голосовой маршрут и соблюсти его с использованием ННР:

Эта команда создает новый сетевой голосовой маршрут с идентификатором "аналог-interop" для диапазона номеров +1425 XXX XX XX.  Голосовой маршрут применяется к списку сетевых sbc.contoso.com и связывает маршрут с использованием интернет-ТСОП "Interop". Голосовой маршрут включает регулярное выражение, определя которое определяет номера телефонов, которые будут маршрутизовыы через заданный голосовой маршрут:

```powershell
PS C:\> New-CsOnlineVoiceRoute -Identity analog-interop -NumberPattern "^\+1(425)(\d{7}])$" -OnlinePstnGatewayList sbc.contoso.com -Priority 1 -OnlinePstnUsages "Interop"
```

## <a name="step-4-assign-the-voice-route-to-the-pstn-usage"></a>Шаг 4. Назначение голосового маршрута для использования ННР:

Эта команда создает новую политику сетевой маршрутизации голосовой связи "на пользователя" с идентификатором AnalogInteropPolicy. Этой политике назначено одно сетевое использование ННР: "Interop".

```powershell
PS C:\> New-CsOnlineVoiceRoutingPolicy -Identity "AnalogInteropPolicy" -Name "AnalogInteropPolicy" -OnlinePstnUsages "Interop"
```

## <a name="step-5-enable-the-online-user"></a>Шаг 5. В том, чтобы включить сетевого пользователя

Эта команда изменяет учетную запись пользователя с помощью exampleuser@contoso.com. В этом случае учетная запись будет изменена, чтобы включить Корпоративная голосовая связь — реализацию VoIP (Майкрософт) с включенной голосовой почтой, и назначит номер +14255000000 этому пользователю.  Эту команду следует выполнить для каждого пользователя Teams (за исключением пользователей устройств ATA) в клиенте компании.

```powershell
PS C:\> Set-CsUser -Identity "exampleuser@contoso.com" -EnterpriseVoiceEnabled $True -HostedVoiceMail $True -OnPremLineUri "tel:+14255000000"
```

## <a name="step-6-assign-the-voice-route-policy-to-a-user"></a>Шаг 6. Назначение пользователю политики голосового пути

Эта команда назначает политике голосовой маршрутизации для каждого пользователя в Интернете (AnalogInteropPolicy) пользователю с идентификатором exampleuser@contoso.com.  Эту команду следует выполнить для каждого пользователя Teams (за исключением пользователей устройств ATA) в клиенте компании.

```powershell
PS C:\> Grant-CsOnlineVoiceRoutingPolicy -Identity "exampleuser@contoso.com" -PolicyName "AnalogInteropPolicy" 
```

## <a name="step-7--create-a-voice-route-for-an-analog-device"></a>Шаг 7. Создание голосового маршрута для аналогового устройства

Эта команда создает сетевой голосовой маршрут с идентификатором "аналог-interop" для диапазона номеров +1425 4XX XX XX, применимого к списку сетевых шлюзов sbc.contoso.com и связывает его с использованием ТСОП через Интернет "Interop".  Эту команду следует выполнить для каждого аналогового устройства с соответствующим шаблоном номера телефона. Кроме того, при настройке сетевого голосового пути на одном из предыдущих этапов можно использовать правильный шаблон номеров для аналоговых устройств.

```powershell
PS C:\> New-CsOnlineVoiceRoute -Identity analog-interop -NumberPattern "^\+1(4254)(\d{6}])$"  -OnlinePstnGatewayList sbc.contoso.com -Priority 1 -OnlinePstnUsages "Interop"
```

## <a name="considerations"></a>Рекомендации

- Если не помните иное, аналоговое устройство — это любое устройство, которое может отправлять цифры DTMF для звонка. Например, аналоговые телефоны, факсы и накладные страницы.

- В Teams нет аналоговых телефонов, подключенных к ATA. Пользователи Teams должны вручную ввести номер телефона, связанный с устройством, чтобы позвонить на это устройство.  
 

## <a name="see-also"></a>См. также

[Планирование прямой маршрутизации](direct-routing-plan.md)

[Настройка прямой маршрутизации](direct-routing-configure.md)
