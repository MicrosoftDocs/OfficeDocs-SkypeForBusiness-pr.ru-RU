---
title: Перевод номеров телефонов для прямой маршрутизации
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: Сведения о том, как настроить прямую маршрутизацию Microsoft Phone System.
ms.openlocfilehash: 2b675948153589c73fa545a95ac785b716b55265
ms.sourcegitcommit: 0289062510f0791906dab2791c5db8acb1cf849a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/20/2020
ms.locfileid: "42158016"
---
# <a name="translate-phone-numbers-to-an-alternate-format"></a>Перевод телефонных номеров в альтернативный формат

В этой статье описано, как перевести номера для исходящего и входящего звонка в альтернативный формат.  Это шаг 4 описанных ниже действий для настройки прямой маршрутизации.

- Шаг 1. [Соединение SBC с телефонной системой Microsoft и проверка соединения](direct-routing-connect-the-sbc.md) 
- Шаг 2. [Предоставление пользователям прямой маршрутизации, голоса и голосовой почты](direct-routing-enable-users.md)   
- Шаг 3. [Настройка голосовой маршрутизации](direct-routing-voice-routing.md)
- **Шаг 4. Перевод номеров в альтернативный формат** (в этой статье)

Сведения о всех шагах, необходимых для настройки прямой маршрутизации, приведены в статье [Настройка прямого маршрута](direct-routing-configure.md).

Иногда администраторам клиентов может потребоваться изменить номер для исходящих и/или входящих звонков на основе созданных вами шаблонов, чтобы обеспечить взаимодействие с контроллерами границ сеансов (SBCs). В этой статье объясняется, как указать политику правил преобразования чисел, чтобы перевести числа в альтернативный формат. 

Вы можете использовать политику правил преобразования чисел для перевода указанных ниже чисел.

- Входящие звонки: звонки из конечной точки PSTN (вызывающего абонента) клиенту Teams (вызываемый)
- Исходящие звонки: звонки из клиента Teams (вызывающего абонента) в конечную точку PSTN (вызываемый)

Политика применяется на уровне SBC. Вы можете назначить для SBC несколько правил перевода, которые применяются в том порядке, в котором они отображаются при их перечислении в PowerShell. Вы также можете изменить порядок правил в политике.

Для создания, изменения, просмотра и удаления правил управления цифрами используйте командлеты [New-CsTeamsTranslationRule](https://docs.microsoft.com/powershell/module/skype/new-csteamstranslationrule), [Set-CsTeamsTranslationRule](https://docs.microsoft.com/powershell/module/skype/set-csteamstranslationrule), [Get-CsTeamsTranslationRule](https://docs.microsoft.com/powershell/module/skype/get-csteamstranslationrule)и [Remove-CsTeamsTranslationRule](https://docs.microsoft.com/powershell/module/skype/remove-csteamstranslationrule) .

Чтобы назначить, настроить и перечислить правила управления числом для SBCs, используйте командлеты [New-CSOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/new-csonlinepstngateway) и [Set-CSOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstngateway) вместе с параметрами InboundTeamsNumberTranslationRules, InboundPSTNNumberTranslationRules, OutboundTeamsNumberTranslationRules, OutboundPSTNNumberTranslationRules, InboundTeamsNumberTranslationRulesList, InboundPSTNNumberTranslationRulesList, OutboundTeamsNumberTranslationRulesList и OutboundPSTNNumberTranslationRulesList.


## <a name="example-sbc-configuration"></a>Пример настройки SBC

Для этого сценария запускается ```New-CsOnlinePSTNGateway``` командлет для создания следующей конфигурации SBC:

```PowerShell
New-CSOnlinePSTNGateway -Identity sbc1.contoso.com -SipSignalingPort 5061 –InboundTeamsNumberTranslationRulesList ‘AddPlus1’, ‘AddE164SeattleAreaCode’ -InboundPSTNNumberTranslationRulesList ‘AddPlus1’ -OnboundPSTNNumberTranslationRulesList ‘AddSeattleAreaCode’,  -OutboundTeamsNumberTranslationRulesList ‘StripPlus1’
```

Правила перевода, назначенные SBC, описаны в таблице ниже.

|Имя  |Шаблон |Преобразование  |
|---------|---------|---------|
|AddPlus1     |^ (\d{10}) $          |+1$1          |
|AddE164SeattleAreaCode      |^ (\d{4}) $          | + 1206555 $1         |
|AddSeattleAreaCode    |^ (\d{4}) $          | 425555 $1         |
|StripPlus1    |^ + 1 (\d{10}) $          | $1         |

В приведенных ниже примерах есть два пользователя: Алиса и Боб. Алиса — это пользователь Teams, номер которого равен + 1 206 555 0100. Боб — это пользователь PSTN, номер которого равен + 1 425 555 0100.

## <a name="example-1-inbound-call-to-a-ten-digit-number"></a>Пример 1: входящий звонок на 10-значный номер

Боб вызывает Алиса, используя не-E. 164 число из десяти цифр. Боб набирает номер 2065550100, чтобы связаться с Алисой.
SBC использует 2065550100 в RequestURI, а к заголовкам и 4255550100м в заголовке From.


|Верхнюю  |Исходный текст |Переведенный верхний колонтитул |Примененные параметр и правило  |
|---------|---------|---------|---------|
|RequestURI  |ПРИГЛАСИТЬ sip:2065550100@sbc.contoso.com|ПРИГЛАСИТЬ sip:+12065550100@sbc.contoso.com|InboundTeamsNumberTranslationRulesList 'AddPlus1'|
|Кому    |Кому: \<SIP:2065550100@sbc.contoso.com>|Кому: \<SIP:+12065550100@sbc.contoso.com>|InboundTeamsNumberTranlationRulesList 'AddPlus1'|
|От   |ОТ: \<SIP:4255550100@sbc.contoso.com>|ОТ: \<SIP:+14255550100@sbc.contoso.com>|InboundPSTNNumberTranslationRulesList 'AddPlus1'|

## <a name="example-2-inbound-call-to-a-four-digit-number"></a>Пример 2: входящий звонок на четырехзначный номер

Боб вызывает Алиса, используя четырехзначный номер. Боб набирает номер 0100, чтобы связаться с Алисой.
SBC использует 0100 в RequestURI, а к заголовкам и 4255550100м в заголовке From.


|Верхнюю  |Исходный текст |Переведенный верхний колонтитул |Примененные параметр и правило  |
|---------|---------|---------|---------|
|RequestURI  |ПРИГЛАСИТЬ sip:0100@sbc.contoso.com          |ПРИГЛАСИТЬ sip:+12065550100@sbc.contoso.com           |InboundTeamsNumberTranlationRulesList 'AddE164SeattleAreaCode'        |
|Кому    |Кому: \<SIP:0100@sbc.contoso.com>|Кому: \<SIP:+12065550100@sbc.contoso.com>|InboundTeamsNumberTranlationRulesList 'AddE164SeattleAreaCode'         |
|От   |ОТ: \<SIP:4255550100@sbc.contoso.com>|ОТ: \<SIP:+14255550100@sbc.contoso.com>|InboundPSTNNumberTranlationRulesList 'AddPlus1'        |

## <a name="example-3-outbound-call-using-a-ten-digit-non-e164-number"></a>Пример 3: исходящий звонок с использованием 10-значного номера, отличного от числа E. 164.

Алиса звонит Бобу по 10-значным числам. Алиса набирает номер 425 555 0100, чтобы связаться с Бобом.
SBC настроен на использование не-E. 164 десяти-значных номеров для пользователей Teams и КТСОП.

В этом сценарии абонентская группа преобразует номер перед отправкой в интерфейс Direct Routing. Когда Алиса вводит 425 555 0100 в клиенте Teams, номер преобразуется в + 14255550100 с помощью абонентской группы "страны". Результирующие числа — это совокупная нормализация правил абонентской группы и переводов групп. Правила перевода команды удаляют "+ 1", добавленный абонентской панелью.


|Верхнюю  |Исходный текст |Переведенный верхний колонтитул |Примененные параметр и правило  |
|---------|---------|---------|---------|
|RequestURI  |ПРИГЛАСИТЬ sip:+14255550100@sbc.contoso.com          |ПРИГЛАСИТЬ sip:4255550100@sbc.contoso.com       |OutboundPSTNNumberTranlationRulesList 'StripPlus1'         |
|Кому    |Кому: \<SIP:+14255550100@sbc.contoso.com>|Кому: \<SIP:4255555555@sbc.contoso.com>|OutboundPSTNNumberTranlationRulesList 'StripPlus1'       |
|От   |ОТ: \<SIP:+12065550100@sbc.contoso.com>|ОТ: \<SIP:2065550100@sbc.contoso.com>|OutboundTeamsNumberTranlationRulesList 'StripPlus1'         |

## <a name="example-4-outbound-call-using-a-four-digit-non-e164-number"></a>Пример 4: исходящий звонок, использующий 4-значный номер, отличный от E. 164.

Алиса звонит Бобу, используя четырехзначный номер. Алиса использует 0100 для доступа к Бобу из звонков или с помощью контакта.
SBC настроен на использование не-E. 164 4-значных номеров для пользователей Teams и десяти-значных номеров для пользователей PSTN. Абонентская группа не применяется в этом сценарии.


|Верхнюю  |Исходный текст |Переведенный верхний колонтитул |Примененные параметр и правило  |
|---------|---------|---------|---------|
|RequestURI  |ПРИГЛАСИТЬ sip:0100@sbc.contoso.com           |ПРИГЛАСИТЬ sip:4255550100@sbc.contoso.com       |InboundTeamsNumberTranlationRulesList 'AddSeattleAreaCode'         |
|Кому    |Кому: \<SIP:0100@sbc.contoso.com>|Кому: \<SIP:4255555555@sbc.contoso.com>|InboundTeamsNumberTranlationRulesList 'AddSeattleAreaCode'       |
|От   |ОТ: \<SIP:+12065550100@sbc.contoso.com>|ОТ: \<SIP:2065550100@sbc.contoso.com>| InboundPSTNNumberTranlationRulesList 'StripPlus1' |

## <a name="see-also"></a>См. также

[Планирование прямой маршрутизации](direct-routing-plan.md)

[Настройка прямой маршрутизации](direct-routing-configure.md)
