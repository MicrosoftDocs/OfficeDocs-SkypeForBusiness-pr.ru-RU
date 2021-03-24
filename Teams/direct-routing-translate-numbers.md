---
title: Перевод номеров телефонов для прямой маршрутки
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
description: Узнайте, как настроить прямую маршрутику из microsoft Phone System.
ms.openlocfilehash: 03abeed954a7760c7c53142380a8ca558c5b3761
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51096379"
---
# <a name="translate-phone-numbers-to-an-alternate-format"></a>Перевод номеров телефонов в другой формат

В этой статье описано, как перевести номера для исходящие и входящие вызовы в альтернативный формат.  Это шаг 4 из следующих действий по настройке прямой маршрутинга:

- Шаг 1. [Подключение SBC к телефонной системе Майкрософт и проверка подключения](direct-routing-connect-the-sbc.md) 
- Шаг 2. [Включить для пользователей прямую маршрутику, голосовую и голосовую почту](direct-routing-enable-users.md)   
- Шаг 3. [Настройка голосовой маршрутии](direct-routing-voice-routing.md)
- **Шаг 4. Перевод чисел в другой формат**   (в этой статье)

Сведения о всех шагах, необходимых для настройки прямой маршрутинга, см. в этой [ссылке.](direct-routing-configure.md)

Иногда администраторам клиентов может потребоваться изменить номер исходящие и/или входящие звонки на основе созданных шаблонов для обеспечения связи с граничными контроллерами сеансов. В этой статье описано, как задать политику правил перевода чисел для перевода чисел в альтернативный формат. 

С помощью политики правил перевода чисел можно переводить номера для следующих номеров:

- Входящие звонки: звонки из конечной точки ННР (вызываемого звонка) в клиент Teams (вызываемому)
- Исходящие звонки: звонки из клиента Teams (вызываемого вызова) в конечную точку STN (вызываемого)

Политика применяется на уровне SBC. Можно назначить СКА несколько правил перевода, которые применяются в порядке их упорядочения при их составлении списка в PowerShell. Вы также можете изменить порядок правил в политике.

Для создания, изменения, просмотра и удаления правил обработки номеров используйте для управления числами [new-CsTeamsTranslationRule,](/powershell/module/skype/new-csteamstranslationrule) [Set-CsTeamsTranslationRule,](/powershell/module/skype/set-csteamstranslationrule) [Get-CsTeamsTranslationRule](/powershell/module/skype/get-csteamstranslationrule)и [Remove-CsTeamsTranslationRule.](/powershell/module/skype/remove-csteamstranslationrule)

Чтобы назначать, настраивать и настраивать правила управления номерами списков на SBCs, используйте вместе с правилом InboundTeamsNumberTranslationRules для [New-CSOnlinePSTNGateway](/powershell/module/skype/new-csonlinepstngateway) и [Set-CSOnlinePSTNGateway.](/powershell/module/skype/set-csonlinepstngateway) InboundPSTNNumberTranslationRules, OutboundTeamsNumberTranslationRules, OutboundPSTNNumberTranslationRules, InboundTeamsNumberTranslationRules, InboundPSTNNumberTranslationRules, OutboundTeamsNumberTranslationRules и OutboundPSTNNumberTranslationRules.

> [!NOTE]
> Максимальное общее количество правил перевода — 400, максимальная длина имени параметра перевода — 100 символов, длина шаблона параметра перевода — 1024, а длина длины перевода — 256.


## <a name="example-sbc-configuration"></a>Пример конфигурации SBC

В этом случае будет ```New-CsOnlinePSTNGateway``` выполниться cmdlet, чтобы создать следующую конфигурацию SBC:

```PowerShell
New-CSOnlinePSTNGateway -Identity sbc1.contoso.com -SipSignalingPort 5061 –InboundTeamsNumberTranslationRules ‘AddPlus1’, ‘AddE164SeattleAreaCode’ -InboundPSTNNumberTranslationRules ‘AddPlus1’ -OutboundPSTNNumberTranslationRules ‘AddSeattleAreaCode’,  -OutboundTeamsNumberTranslationRules ‘StripPlus1’
```

Правила перевода, которые назначены SBC, суммируются в следующей таблице:

|Имя  |Шаблон |Преобразование  |
|---------|---------|---------|
|AddPlus1     |^(\d {10} )$          |+1$1          |
|AddE164SeattleAreaCode      |^(\d {4} )$          | +1206555$1         |
|AddSeattleAreaCode    |^(\d {4} )$          | 425555$1         |
|ПолосаPlus1    |^+1(\d {10} )$          | $1         |

В следующих примерах есть два пользователя: Андрей и Г. Он — пользователь Teams, номер которого + 1 206 555 0100. Г.: пользователь ННР, номер которого + 1 425 555 0100.

## <a name="example-1-inbound-call-to-a-ten-digit-number"></a>Пример 1. Входящий звонок на десятизначный номер

Г-н Климов звонит на десятизначный номер, не 164- или E.164. Bob dials 2065550100 to reach To Прил.
В SBC используется 2065550100 в области requestURI и To, а в заглавной области "От" - 4255550100.


|Заглавная  |Исходный текст |Заглавный текст с переводом |Параметр и правило применены  |
|---------|---------|---------|---------|
|RequestURI  |ПРИГЛАШЕНИЕ sip:2065550100@sbc.contoso.com|ПРИГЛАШЕНИЕ sip:+12065550100@sbc.contoso.com|InboundTeamsNumberTranslationRules 'AddPlus1'|
|Кому    |Кому: \<sip:2065550100@sbc.contoso.com>|Кому: \<sip:+12065550100@sbc.contoso.com>|InboundTeamsNumberTranlationRules 'AddPlus1'|
|От   |От: \<sip:4255550100@sbc.contoso.com>|От: \<sip:+14255550100@sbc.contoso.com>|InboundPSTNNumberTranslationRules 'AddPlus1'|

## <a name="example-2-inbound-call-to-a-four-digit-number"></a>Пример 2. Входящий звонок на четырехзначный номер

Г-н Климов звонит по четырехзначным номерам. Bob dials 0100 to reach To To.
В SBC используется 0100 в запросеURI и to headers, а в заглавной области "От" используется 4255550100.


|Заглавная  |Исходный текст |Заглавный текст с переводом |Параметр и правило применены  |
|---------|---------|---------|---------|
|RequestURI  |ПРИГЛАШЕНИЕ sip:0100@sbc.contoso.com          |ПРИГЛАШЕНИЕ sip:+12065550100@sbc.contoso.com           |InboundTeamsNumberTranlationRules 'AddE164SeattleAreaCode'        |
|Кому    |Кому: \<sip:0100@sbc.contoso.com>|Кому: \<sip:+12065550100@sbc.contoso.com>|InboundTeamsNumberTranlationRules 'AddE164SeattleAreaCode'         |
|От   |От: \<sip:4255550100@sbc.contoso.com>|От: \<sip:+14255550100@sbc.contoso.com>|InboundPSTNNumberTranlationRules 'AddPlus1'        |

## <a name="example-3-outbound-call-using-a-ten-digit-non-e164-number"></a>Пример 3. Исходящие вызовы с десятизначным номером без E.164

Он звонит Гюлену, используя десятизначный номер. Звонить по номеру 425 555 0100, чтобы связаться с Гомом.
SBC настроен для использования десятизначных номеров, не от E.164, для пользователей Teams и STN.

В этом сценарии номер переводится перед отправкой в интерфейс прямой маршрутки. При вводе 425 555 0100 в клиенте Teams номер переводится в +14255550100 в стране или стране. Итогом является совокупная нормализация правил набора и правил перевода Teams. Правила перевода Teams удаляют "+1", добавленное в наборную группу.


|Заглавная  |Исходный текст |Заглавный текст с переводом |Параметр и правило применены  |
|---------|---------|---------|---------|
|RequestURI  |ПРИГЛАШЕНИЕ sip:+14255550100@sbc.contoso.com          |ПРИГЛАШЕНИЕ sip:4255550100@sbc.contoso.com       |OutboundPSTNNumberTranlationRules 'StripPlus1'         |
|Кому    |Кому: \<sip:+14255550100@sbc.contoso.com>|Кому: \<sip:4255555555@sbc.contoso.com>|OutboundPSTNNumberTranlationRules 'StripPlus1'       |
|От   |От: \<sip:+12065550100@sbc.contoso.com>|От: \<sip:2065550100@sbc.contoso.com>|OutboundTeamsNumberTranlationRules 'StripPlus1'         |

## <a name="example-4-outbound-call-using-a-four-digit-non-e164-number"></a>Пример 4. Исходящие вызовы с четырехзначным номером без номера E.164

Звонит Гюлену, используя четырехзначный номер. Для связи с Гом из звонка или с помощью контакта Климов использует 0100.
В SBC настроено использование четырехзначных номеров, не влияемых на E.164, для пользователей Teams и десятизначных номеров для пользователей ННР. В этом сценарии набор номеров не применяется.


|Заглавная  |Исходный текст |Заглавный текст с переводом |Параметр и правило применены  |
|---------|---------|---------|---------|
|RequestURI  |ПРИГЛАШЕНИЕ sip:0100@sbc.contoso.com           |ПРИГЛАШЕНИЕ sip:4255550100@sbc.contoso.com       |InboundTeamsNumberTranlationRules 'AddSeattleAreaCode'         |
|Кому    |Кому: \<sip:0100@sbc.contoso.com>|Кому: \<sip:4255555555@sbc.contoso.com>|InboundTeamsNumberTranlationRulesList 'AddSeattleAreaCode'       |
|От   |От: \<sip:+12065550100@sbc.contoso.com>|От: \<sip:2065550100@sbc.contoso.com>| InboundPSTNNumberTranlationRules 'StripPlus1' |

## <a name="see-also"></a>См. также

[Планирование прямой маршрутизации](direct-routing-plan.md)

[Настройка прямой маршрутизации](direct-routing-configure.md)