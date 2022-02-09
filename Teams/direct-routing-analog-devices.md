---
title: Прямая маршрутия — подключение аналоговых устройств
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.reviewer: filippse
ms.topic: conceptual
ms.service: msteams
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: В этой статье вы узнаете, как использовать аналоговые устройства с Microsoft Teams телефонная система прямой маршрутии.
ms.openlocfilehash: e3de63de032d2caf06993ac0a08b624feb5a5b42
ms.sourcegitcommit: 79dfda39db208cf943d0f7b4906883bb9d034281
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/09/2022
ms.locfileid: "62457389"
---
# <a name="how-to-use-analog-devices-with-direct-routing"></a>Использование аналоговых устройств с прямой маршрутией

В этой статье описано использование аналоговых устройств с прямой маршрутией. Для подключения аналоговых устройств к прямой маршрутике необходимо использовать аналоговый адаптер телефонии (ATA), который должен поддерживаться сертифицированным поставщиком пограничного контроллера сеанса . 

Когда пользователь звонит с аналогового устройства, сигнальный поток и мультимедиа проходят через адаптер аналоговой телефонии (ATA) к SBC.  SBC отправляет звонок на конечную точку Microsoft Teams или в телефонную сеть общего перейти на телефонную сеть (STN), основанную на внутренней таблице маршрутов.  Когда устройство совершает звонок, маршрут, который он принимает, зависит от политик маршрутинга, созданных для устройства.

На приведенной ниже схеме Прямая маршрутная маршрутия настроена таким образом, что все звонки Teams на номера между +1425 4XX XX XX и +1425 5XX XX XX XX должны принимать красный маршрут (пунктирная линия), а все звонки по ДНР на номера между +1425 4XX XX XX и любыми другими номерами, кроме номера +1425 5XX XX XX XX, должны проходить синим (сплошная линия). 

> [!div class="mx-imgBorder"]
> ![Схема, показывающая конфигурацию прямой маршрутации.](media/direct-routing-analog-device.png)

## <a name="example-how-to-configure-the-use-of-analog-devices-with-direct-routing"></a>Пример: настройка использования аналоговых устройств с прямой маршрутией

Чтобы настроить использование аналоговых устройств с прямой маршрутией, необходимо подключить адаптер аналоговой телефонии к SBC и настроить SBC для работы с прямой маршрутией. 

В этом примере вы можете сделать следующее:

1. Подключение SBC к прямой маршрутике.
2. Создайте использование ОКП.
3. Создайте голосовой маршрут и связываете его с использованием ПСПС.
4. Назначьте голосовой маршрут использованию ОКП.
5. В этом режиме можно включить сетевого пользователя.
6. Назначьте политику голосового маршрута пользователю.
7. Создайте голосовой маршрут для аналогового устройства.

Сведения о том, как подключить ATA к SBC и настроить SBC, см. в руководстве производителя SBC:

- [Документация по настройке AudioCodes](https://www.audiocodes.com/media/14278/connecting-audiocodes-sbc-with-analog-device-to-microsoft-teams-direct-routing-enterprise-model-configuration-note.pdf)

- [Документация по конфигурации ленты](https://support.sonus.net/display/UXDOC81/Connect+SBC+Edge+to+Microsoft+Teams+Direct+Routing+to+Support+Analog+Devices)
- [Документация по конфигурации Oracle](https://www.oracle.com/technical-resources/documentation/acme-packet.html#Link-MicrosoftTeams)

## <a name="step-1-connect-the-sbc-to-direct-routing"></a>Шаг 1. Подключение SBC к прямой маршрутике

Следующая команда настраивает подключение SBC следующим образом:

- FQDN sbc.contoso.com
- Сигнальный порт 5068
- Режим обхода мультимедиа
- Сведения из истории  вызовов, переадваренные на SBC-
- Заглавная точка p-Висячих удостоверений (PAI), переадвароваемая вместе с вызовом 

```powershell
PS C:\> New-CsOnlinePSTNGateway -FQDN sbc.contoso.com -SIPSignalingPort 5068 -ForwardCallHistory $true -ForwardPAI $true -MediaBypass $true -Enabled $true 
```

## <a name="step-2-create-the-pstn-usage"></a>Шаг 2. Создание использования ОКП 

Следующая команда создает пустое использование ОКП. Использование ОКП через Интернет — это строки значений, которые используются для авторизации  вызовов. Использование ОКП через Интернет связывает голосовую политику в Интернете с маршрутом. В этом примере строка "Interop" добавляется в текущий список доступных использования ПСОП. 

```powershell
PS C:\> Set-CsOnlinePstnUsage -Identity global -Usage @{add="Interop"} 
```

## <a name="step-3-create-a-voice-route-and-associate-it-with-the-pstn-usage"></a>Шаг 3. Создание голосового маршрута и связыва его с использованием ОКП

Эта команда создает новый сетевой голосовой маршрут с идентификатором "аналоговое интероп" для диапазона номеров +1425 XXX XX XX.  Голосовой маршрут применяется к списку сетевых шлюзов sbc.contoso.com и связывает маршрут с использованием ТСОП через Интернет "Interop". Голосовой маршрут включает регулярное выражение, определя которое определяет номера телефонов, которые будут маршрутизданы по заданным голосовым маршрутам:

```powershell
PS C:\> New-CsOnlineVoiceRoute -Identity analog-interop -NumberPattern "^\+1(425)(\d{7})$" -OnlinePstnGatewayList sbc.contoso.com -Priority 1 -OnlinePstnUsages "Interop"
```

## <a name="step-4-assign-the-voice-route-to-the-pstn-usage"></a>Шаг 4. Назначение голосового маршрута для использования ННР:

Эта команда создает новую политику маршрутизации голосовой связи для каждого пользователя в Интернете с идентификатором AnalogInteropPolicy. Этой политике назначено одно использование ПСОП в Интернете: "Interop".

```powershell
PS C:\> New-CsOnlineVoiceRoutingPolicy -Identity "AnalogInteropPolicy" -OnlinePstnUsages "Interop"
```

## <a name="step-5-enable-the-online-user"></a>Шаг 5. Включить интернет-пользователя

Эта команда изменяет учетную запись пользователя с помощью exampleuser@contoso.com. В этом случае учетная запись будет изменена, чтобы включить Корпоративная голосовая связь, внедрение VoIP корпорации Майкрософт, с включенной голосовой почтой и назначит номер +14255000000 этому пользователю.  Эту команду следует выполнить для каждого Teams пользователя (за исключением пользователей устройств ATA) в клиенте компании.

```powershell
PS C:\> Set-CsUser -Identity "exampleuser@contoso.com" -EnterpriseVoiceEnabled $True -HostedVoiceMail $True -OnPremLineUri "tel:+14255000000"
```

## <a name="step-6-assign-the-voice-route-policy-to-a-user"></a>Шаг 6. Назначение политики голосового маршрута пользователю

Эта команда назначает политику сетевой маршрутизации голосовой маршрутизации "на пользователя" (AnalogInteropPolicy) пользователю с идентификаторами exampleuser@contoso.com. Эту команду следует выполнить для каждого Teams пользователя (за исключением пользователей устройств ATA) в клиенте компании.

```powershell
PS C:\> Grant-CsOnlineVoiceRoutingPolicy -Identity "exampleuser@contoso.com" -PolicyName "AnalogInteropPolicy" 
```

## <a name="step-7-create-a-voice-route-for-an-analog-device"></a>Шаг 7. Создание голосового маршрута для аналогового устройства

Эта команда создает сетевой голосовой маршрут с идентификатором "аналоговое интероп" для диапазона номеров +1425 4XX XX XX, применимого к списку сетевых шлюзов sbc.contoso.com и связывает его с использованием ТСОП через Интернет "Interop".  Эту команду следует выполнить для каждого аналогового устройства с соответствующим шаблоном номера телефона. Кроме того, при настройке сетевого голосового маршрута на одном из предыдущих этапов можно использовать правильный шаблон номера для аналоговых устройств.

```powershell
PS C:\> New-CsOnlineVoiceRoute -Identity analog-interop -NumberPattern "^\+1(4254)(\d{6})$"  -OnlinePstnGatewayList sbc.contoso.com -Priority 1 -OnlinePstnUsages "Interop"
```

## <a name="considerations"></a>Рекомендации

- Если не указано иное, аналоговое устройство — это любое устройство, на которое можно отправлять цифры DTMF для звонка. Например, аналоговые телефоны, факсы и накладные страницы.

- Аналоговые телефоны, подключенные к ATA, невозможно найти в Teams. Teams пользователи должны вручную ввести номер телефона, связанный с устройством, чтобы позвонить на это устройство.  
 

## <a name="see-also"></a>См. также

[Планирование прямой маршрутизации](direct-routing-plan.md)

[Настройка прямой маршрутизации](direct-routing-configure.md)
