---
title: Перевод телефонных номеров для прямой маршрутизации
ms.reviewer: filippse
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
description: Узнайте, как настроить прямую маршрутизацию телефонной системы Майкрософт.
ms.openlocfilehash: ac6dbd46d525232235d957b7d47f1fe108e3e4a3
ms.sourcegitcommit: eb0e754d7e2877f686021d3ab75b6d8d44db3a95
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/06/2023
ms.locfileid: "69727771"
---
# <a name="translate-phone-numbers-to-an-alternate-format"></a>Перевод номеров телефонов в альтернативный формат

В этой статье описывается преобразование номеров для исходящих и входящих вызовов в альтернативный формат. Это шаг 4 из следующих шагов по настройке прямой маршрутизации:

- Шаг 1. [Подключение SBC к телефонной системе Майкрософт и проверка подключения](direct-routing-connect-the-sbc.md) 
- Шаг 2. [Включение прямой маршрутизации, голосовой и голосовой почты для пользователей](direct-routing-enable-users.md)   
- Шаг 3. [Настройка маршрутизации голосовой связи](direct-routing-voice-routing.md)
- **Шаг 4. Перевод чисел в альтернативный формат**   (эта статья)

Сведения обо всех шагах, необходимых для настройки прямой маршрутизации, см. в разделе [Настройка прямой маршрутизации](direct-routing-configure.md).

Иногда администраторам клиента может потребоваться изменить число исходящих и (или) входящих вызовов на основе созданных шаблонов для обеспечения взаимодействия с пограничными контроллерами сеансов (SBC). В этой статье описывается, как указать политику правил преобразования чисел для преобразования чисел в альтернативный формат. 

Вы можете использовать политику Правила преобразования чисел для перевода чисел для следующего:

- Входящие вызовы: вызовы из конечной точки ТСОП (вызывающего абонента) в клиент Teams (вызываемый)
- Исходящие вызовы: вызовы из клиента Teams (вызывающего абонента) в конечную точку ТСОП (вызываемый)

Политика применяется на уровне SBC. Вы можете назначить несколько правил преобразования для SBC, которые применяются в том порядке, в котором они отображаются при их перечислении в PowerShell. Вы также можете изменить порядок правил в политике.

Для создания, изменения, просмотра и удаления правил обработки чисел используйте [командлеты New-CsTeamsTranslationRule](/powershell/module/skype/new-csteamstranslationrule), [Set-CsTeamsTranslationRule](/powershell/module/skype/set-csteamstranslationrule), [Get-CsTeamsTranslationRule](/powershell/module/skype/get-csteamstranslationrule) и [Remove-CsTeamsTranslationRule](/powershell/module/skype/remove-csteamstranslationrule) .

Для назначения, настройки и перечисления правил управления номерами в SBC используйте командлеты [New-CSOnlinePSTNGateway](/powershell/module/skype/new-csonlinepstngateway) и [Set-CSOnlinePSTNGateway](/powershell/module/skype/set-csonlinepstngateway) вместе с параметрами InboundTeamsNumberTranslationRules, InboundPSTNNumberTranslationRules, OutboundTeamsNumberTranslationRules и OutboundPSTNNumberTranslationRules.

> [!NOTE]
> Максимальное общее число правил перевода — 400, максимальная длина имени параметра перевода — 100 символов, максимальная длина шаблона параметра перевода — 1024 символа, а максимальная длина преобразования параметра перевода — 256 символов.


## <a name="example-sbc-configuration"></a>Пример конфигурации SBC

В этом сценарии выполняется командлет New-CsOnlinePSTNGateway, чтобы создать следующую конфигурацию SBC:

```PowerShell
New-CSOnlinePSTNGateway -Identity sbc1.contoso.com -SipSignalingPort 5061 –InboundTeamsNumberTranslationRules ‘AddPlus1’, ‘AddE164SeattleAreaCode’ -InboundPSTNNumberTranslationRules ‘AddPlus1’ -OutboundPSTNNumberTranslationRules ‘AddSeattleAreaCode’,‘StripPlus1’  -OutboundTeamsNumberTranslationRules ‘StripPlus1’
```

Правила преобразования, назначенные SBC, приведены в следующей таблице:

|Имя  |Шаблон |Преобразование  |
|---------|---------|---------|
|AddPlus1     |^(\d{10})$          |+1$1          |
|AddE164SeattleAreaCode      |^(\d{4})$          | +1206555$1         |
|AddSeattleAreaCode    |^(\d{4})$          | 425555$1         |
|StripPlus1    |^\+1(\d{10})$          | $1         |

В следующих примерах есть два пользователя: Алиса и Боб. Алиса — это пользователь Teams с номером +1 206 555 0100. Боб является пользователем ТСОП с номером +1 425 555 0100.

## <a name="example-1-inbound-call-to-a-ten-digit-number"></a>Пример 1. Входящий вызов на десятизначный номер

Боб вызывает Алису, используя десятизначное число, отличное от E.164. Боб набирает 2065550100, чтобы связаться с Алисой.
SBC использует 2065550100 в заголовках RequestURI и To и 4255550100 в заголовке From.


|Заголовка  |Исходный текст |Переведенный заголовок |Применены параметр и правило  |
|---------|---------|---------|---------|
|RequestURI  |ПРИГЛАШЕНИЕ sip:2065550100@sbc.contoso.com|ПРИГЛАШЕНИЕ sip:+12065550100@sbc.contoso.com|InboundTeamsNumberTranslationRules 'AddPlus1'|
|КОМУ    |КОМУ: \<sip:2065550100@sbc.contoso.com>|КОМУ: \<sip:+12065550100@sbc.contoso.com>|InboundTeamsNumberTranlationRules "AddPlus1"|
|ОТ   |ОТ: \<sip:4255550100@sbc.contoso.com>|ОТ: \<sip:+14255550100@sbc.contoso.com>|InboundPSTNNumberTranslationRules "AddPlus1"|

## <a name="example-2-inbound-call-to-a-four-digit-number"></a>Пример 2. Входящий вызов на четырехзначный номер

Боб звонит Алисе, используя четырехзначное число. Боб набирает 0100, чтобы связаться с Алисой.
SBC использует 0100 в заголовках RequestURI и To и 4255550100 в заголовке From.


|Заголовка  |Исходный текст |Переведенный заголовок |Применены параметр и правило  |
|---------|---------|---------|---------|
|RequestURI  |ПРИГЛАШЕНИЕ sip:0100@sbc.contoso.com          |ПРИГЛАШЕНИЕ sip:+12065550100@sbc.contoso.com           |InboundTeamsNumberTranlationRules 'AddE164SeattleAreaCode'        |
|КОМУ    |КОМУ: \<sip:0100@sbc.contoso.com>|КОМУ: \<sip:+12065550100@sbc.contoso.com>|InboundTeamsNumberTranlationRules 'AddE164SeattleAreaCode'         |
|ОТ   |ОТ: \<sip:4255550100@sbc.contoso.com>|ОТ: \<sip:+14255550100@sbc.contoso.com>|InboundPSTNNumberTranlationRules "AddPlus1"        |

## <a name="example-3-outbound-call-using-a-ten-digit-non-e164-number"></a>Пример 3. Исходящий вызов с использованием десятизначного номера, отличного от E.164

Алиса звонит Бобу, используя десятизначное число. Алиса набирает 425 555 0100, чтобы связаться с Бобом.
SBC настроен на использование десятизначных чисел, отличных от E.164, как для пользователей Teams, так и для пользователей ТСОП.

В этом сценарии абонентские группы преобразуют номер перед его отправкой в интерфейс прямой маршрутизации. Когда Алиса вводит 425 555 0100 в клиенте Teams, номер преобразуется в +14255550100 абонентской группой страны. Полученные числа представляют собой совокупную нормализацию правил абонентской группы и правил перевода Teams. Правила перевода Teams удаляют "+1", добавленный абонентской группой.


|Заголовка  |Исходный текст |Переведенный заголовок |Применены параметр и правило  |
|---------|---------|---------|---------|
|RequestURI  |ПРИГЛАШЕНИЕ sip:+14255550100@sbc.contoso.com          |ПРИГЛАШЕНИЕ sip:4255550100@sbc.contoso.com       |OutboundPSTNNumberTranlationRules 'StripPlus1'         |
|КОМУ    |КОМУ: \<sip:+14255550100@sbc.contoso.com>|КОМУ: \<sip:4255555555@sbc.contoso.com>|OutboundPSTNNumberTranlationRules 'StripPlus1'       |
|ОТ   |ОТ: \<sip:+12065550100@sbc.contoso.com>|ОТ: \<sip:2065550100@sbc.contoso.com>|OutboundTeamsNumberTranlationRules 'StripPlus1'         |

## <a name="example-4-outbound-call-using-a-four-digit-non-e164-number"></a>Пример 4. Исходящий вызов с использованием четырехзначного номера, отличного от E.164

Алиса звонит Бобу, используя четырехзначное число. Алиса использует 0100, чтобы связаться с Бобом из звонков или с помощью контакта.
SBC настроен на использование четырехзначных номеров, отличных от E.164, для пользователей Teams и десятизначных чисел для пользователей ТСОП. Абонентская группа не применяется в этом сценарии.


|Заголовка  |Исходный текст |Переведенный заголовок |Применены параметр и правило  |
|---------|---------|---------|---------|
|RequestURI  |ПРИГЛАШЕНИЕ sip:0100@sbc.contoso.com           |ПРИГЛАШЕНИЕ sip:4255550100@sbc.contoso.com       |InboundTeamsNumberTranlationRules 'AddSeattleAreaCode'         |
|КОМУ    |КОМУ: \<sip:0100@sbc.contoso.com>|КОМУ: \<sip:4255555555@sbc.contoso.com>|InboundTeamsNumberTranlationRulesList 'AddSeattleAreaCode'       |
|ОТ   |ОТ: \<sip:+12065550100@sbc.contoso.com>|ОТ: \<sip:2065550100@sbc.contoso.com>| InboundPSTNNumberTranlationRules 'StripPlus1' |

## <a name="see-also"></a>См. также

[Планирование прямой маршрутизации](direct-routing-plan.md)

[Настройка прямой маршрутизации](direct-routing-configure.md)
