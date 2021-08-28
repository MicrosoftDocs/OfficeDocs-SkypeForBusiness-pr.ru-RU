---
title: Перевод номеров телефонов для прямой маршрутии
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: Узнайте, как настроить Телефон (Майкрософт) прямой маршрутии Системы.
ms.openlocfilehash: d6b767ace4f00e581e99ec73585b0b596029b17e
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/26/2021
ms.locfileid: "58619465"
---
# <a name="translate-phone-numbers-to-an-alternate-format"></a>Перевод номеров телефонов в другой формат

В этой статье описано, как перевести номера для исходящие и входящие вызовы в альтернативный формат.  Это шаг 4 из следующих действий по настройке прямой маршрутии:

- Шаг 1. [Подключение SBC с Телефон (Майкрософт) и проверьте подключение](direct-routing-connect-the-sbc.md) 
- Шаг 2. [Включить для пользователей прямую маршрутику, голосовую и голосовую почту](direct-routing-enable-users.md)   
- Шаг 3. [Настройка голосовой маршрутии](direct-routing-voice-routing.md)
- **Шаг 4. Перевод чисел в альтернативный формат**   (эта статья)

Сведения о всех действиях, необходимых для настройки прямой маршрутистики, см. в этой [ссылке.](direct-routing-configure.md)

Иногда администраторам клиентов может потребоваться изменить номер для исходящие и /или входящие вызовы на основе шаблонов, созданных для обеспечения связи с контроллерами границ сеанса (SBCs). В этой статье описано, как задать политику правил перевода чисел для перевода чисел в альтернативный формат. 

С помощью политики правил перевода номеров можно переводить номера для следующих чисел:

- Входящие звонки: звонки из конечной точки (вызываемого звонка) в Teams (вызываемому)
- Исходящие звонки: звонки от клиента Teams (вызываемого звонка) на конечную точку ЗВОНКОВ по ЗВОНКОВ

Политика применяется на уровне SBC. Для SBC можно назначить несколько правил перевода, которые применяются в том порядке, в котором они отображаются при их списке в PowerShell. Вы также можете изменить порядок правил в политике.

Для создания, изменения, просмотра и удаления правил управления числом используйте [new-CsTeamsTranslationRule](/powershell/module/skype/new-csteamstranslationrule), [Set-CsTeamsTranslationRule,](/powershell/module/skype/set-csteamstranslationrule) [Get-CsTeamsTranslationRule](/powershell/module/skype/get-csteamstranslationrule)и [Remove-CsTeamsTranslationRule.](/powershell/module/skype/remove-csteamstranslationrule)

Чтобы назначить, настроить и настроить правила управления номерами списков на SBCs, используйте [new-CSOnlinePSTNGateway](/powershell/module/skype/new-csonlinepstngateway) и [Set-CSOnlinePSTNGateway](/powershell/module/skype/set-csonlinepstngateway) вместе с inboundTeamsNumberTranslationRules, InboundPSTNNumberTranslationRules, OutboundTeamsNumberTranslationRules, OutboundPSTNNumberTranslationRules, InboundTeamsNumberTranslationRules, InboundPPNNumberTranslationRules, OutboundTeamsNumberTranslationRules и OutboundPNNumberTranslationRules.

> [!NOTE]
> Максимальное общее число правил перевода — 400, максимальная длина имени параметра перевода — 100 символов, максимальная длина шаблона перевода — 1024, а максимальная длина перевода — 256 символов.


## <a name="example-sbc-configuration"></a>Пример конфигурации SBC

В этом случае будет запускаться следующий сценарий ```New-CsOnlinePSTNGateway``` SBC:

```PowerShell
New-CSOnlinePSTNGateway -Identity sbc1.contoso.com -SipSignalingPort 5061 –InboundTeamsNumberTranslationRules ‘AddPlus1’, ‘AddE164SeattleAreaCode’ -InboundPSTNNumberTranslationRules ‘AddPlus1’ -OutboundPSTNNumberTranslationRules ‘AddSeattleAreaCode’,  -OutboundTeamsNumberTranslationRules ‘StripPlus1’
```

Правила перевода, которые назначены SBC, суммируются в следующей таблице:

|Имя  |Шаблон |Преобразование  |
|---------|---------|---------|
|AddPlus1     |^(\d {10} )$          |+1$1          |
|AddE164SeattleAreaCode      |^(\d {4} )$          | +1206555$1         |
|AddSeattleAreaCode    |^(\d {4} )$          | 425555 $1         |
|StripPlus1    |^+1(\d {10} )$          | $1         |

В следующих примерах есть два пользователя: Андрей и Г. 1 — Teams, номер которого + 1 206 555 0100. Г.М. — пользователь ДНР с номером +1 425 555 0100.

## <a name="example-1-inbound-call-to-a-ten-digit-number"></a>Пример 1. Входящий звонок на десятизначный номер

Г-н Гюл звонит, используя десятизначный номер, не 164 E.164. Bob dials 2065550100 to reach Bob.
В SBC 2065550100 в загонах RequestURI и To, а 4255550100 в заглавной области От.


|Заголовка  |Исходный текст |Заглавный текст с переводом |Применены параметр и правило  |
|---------|---------|---------|---------|
|RequestURI  |ПРИГЛАСИТЬ SIP:2065550100@SBC.CONTOSO.COM|ПРИГЛАСИТЬ sip:+12065550100@sbc.contoso.com|InboundTeamsNumberTranslationRules 'AddPlus1'|
|КОМУ    |КОМУ: \<sip:2065550100@sbc.contoso.com>|КОМУ: \<sip:+12065550100@sbc.contoso.com>|InboundTeamsNumberTranlationRules 'AddPlus1'|
|ОТ   |ОТ: \<sip:4255550100@sbc.contoso.com>|ОТ: \<sip:+14255550100@sbc.contoso.com>|InboundPSTNNumberTranslationRules 'AddPlus1'|

## <a name="example-2-inbound-call-to-a-four-digit-number"></a>Пример 2. Входящий звонок на четырехзначный номер

Г-н Мюн звонит Вайл, используя четырехзначный номер. Bob dials 0100 to reach Bob.
В SBC используется 0100 в заглавных 4255550100 в заглавной области "От".


|Заголовка  |Исходный текст |Заглавный текст с переводом |Применены параметр и правило  |
|---------|---------|---------|---------|
|RequestURI  |ПРИГЛАСИТЬ sip:0100@sbc.contoso.com          |ПРИГЛАСИТЬ sip:+12065550100@sbc.contoso.com           |InboundTeamsNumberTranlationRules 'AddE164SeattleAreaCode'        |
|КОМУ    |КОМУ: \<sip:0100@sbc.contoso.com>|КОМУ: \<sip:+12065550100@sbc.contoso.com>|InboundTeamsNumberTranlationRules 'AddE164SeattleAreaCode'         |
|ОТ   |ОТ: \<sip:4255550100@sbc.contoso.com>|ОТ: \<sip:+14255550100@sbc.contoso.com>|InboundPSTNNumberTranlationRules 'AddPlus1'        |

## <a name="example-3-outbound-call-using-a-ten-digit-non-e164-number"></a>Пример 3. Исходящие вызовы с десятизначным номером без номера E.164

Он звонит Гюлену, используя десятизначный номер. Звонит 425 555 0100, чтобы связаться с Гомеем.
В SBC настроено использование десятизначных номеров, не влияемых на E.164, Teams пользователей ДНР и ДНР.

В этом случае с помощью телефонной линии номер перед отправкой переводится в интерфейс прямой маршрутии. При вводе 425 555 0100 в клиенте Teams телефонной карты номер переводится в +14255550100 по стране. Итоги — это совокупная нормализация правил набора и Teams правил перевода. Правила Teams перевода удаляют "+1", добавленные в телефонную план.


|Заголовка  |Исходный текст |Заглавный текст с переводом |Применены параметр и правило  |
|---------|---------|---------|---------|
|RequestURI  |ПРИГЛАСИТЬ sip:+14255550100@sbc.contoso.com          |ПРИГЛАСИТЬ sip:4255550100@sbc.contoso.com       |ИсходящиеPSTNNumberTranlationRules 'StripPlus1'         |
|КОМУ    |КОМУ: \<sip:+14255550100@sbc.contoso.com>|КОМУ: \<sip:4255555555@sbc.contoso.com>|ИсходящиеPSTNNumberTranlationRules 'StripPlus1'       |
|ОТ   |ОТ: \<sip:+12065550100@sbc.contoso.com>|ОТ: \<sip:2065550100@sbc.contoso.com>|ИсходящиеTeamsNumberTranlationRules 'StripPlus1'         |

## <a name="example-4-outbound-call-using-a-four-digit-non-e164-number"></a>Пример 4. Исходящие вызовы с использованием четырехзначного номера без номера E.164

Он звонит Гюлену, используя четырехзначный номер. С помощью 0100 можно связаться с Сергеем из звонка или с помощью контакта.
В SBC настроено использование четырехзначных номеров, не влияемых на E.164, для Teams пользователей и десятизначных номеров для пользователей ДНР. В этом сценарии набор номеров не применяется.


|Заголовка  |Исходный текст |Заглавный текст с переводом |Применены параметр и правило  |
|---------|---------|---------|---------|
|RequestURI  |ПРИГЛАСИТЬ sip:0100@sbc.contoso.com           |ПРИГЛАСИТЬ sip:4255550100@sbc.contoso.com       |InboundTeamsNumberTranlationRules 'AddSeattleAreaCode'         |
|КОМУ    |КОМУ: \<sip:0100@sbc.contoso.com>|КОМУ: \<sip:4255555555@sbc.contoso.com>|InboundTeamsNumberTranlationRulesList 'AddSeattleAreaCode'       |
|ОТ   |ОТ: \<sip:+12065550100@sbc.contoso.com>|ОТ: \<sip:2065550100@sbc.contoso.com>| InboundPSTNNumberTranlationRules 'StripPlus1' |

## <a name="see-also"></a>См. также

[Планирование прямой маршрутизации](direct-routing-plan.md)

[Настройка прямой маршрутизации](direct-routing-configure.md)