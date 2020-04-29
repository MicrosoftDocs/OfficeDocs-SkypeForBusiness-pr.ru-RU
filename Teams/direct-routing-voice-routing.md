---
title: Настройка маршрутизации голосовой связи для прямой маршрутизации
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
description: Научитесь настраивать маршрутизацию голосовой связи с помощью прямой маршрутизации Microsoft Phone System.
ms.openlocfilehash: 8889475acda00cf1565f944c7925ba0fb5194ec5
ms.sourcegitcommit: 0289062510f0791906dab2791c5db8acb1cf849a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/20/2020
ms.locfileid: "42158011"
---
# <a name="configure-voice-routing-for-direct-routing"></a>Настройка маршрутизации голосовой связи для прямой маршрутизации

В этой статье описано, как настроить маршрутизацию голосовой связи для прямой маршрутизации телефонной системы.  Это действие 3 описанных ниже действий для настройки прямой маршрутизации.

- Шаг 1. [Соединение SBC с телефонной системой Microsoft и проверка соединения](direct-routing-connect-the-sbc.md) 
- Шаг 2. [Предоставление пользователям прямой маршрутизации, голоса и голосовой почты](direct-routing-enable-users.md)    
- **Шаг 3. Настройка голосовой маршрутизации** (в этой статье)
- Шаг 4. [Перевод чисел в альтернативный формат](direct-routing-translate-numbers.md) 

Сведения о всех шагах, необходимых для настройки прямой маршрутизации, приведены в статье [Настройка прямого маршрута](direct-routing-configure.md).

## <a name="voice-routing-overview"></a>Общие сведения о маршрутизации голосовой почты

В телефонной системе Microsoft есть механизм маршрутизации, позволяющий отправлять звонки на определенный контроллер границ сеанса (SBC), основанный на следующих устройствах: 

- Вызываемый шаблон номера 
- Вызываемый шаблон номера и конкретный пользователь, который совершает звонок;
 
SBCs можно назначить активными и архивировать. Если объект SBC, настроенный как активный, недоступен для определенного маршрута вызова, этот звонок будет перенаправлен на одноэлементный объект SBC.
 
Маршрутизация голосовой связи состоит из следующих элементов: 

- **Политика маршрутизации голосовой связи** — контейнер использования PSTN, который можно назначить пользователю или нескольким пользователям. 

- **Использование PSTN** — контейнер для голосовых маршрутов и использование PSTN, которые можно использовать в разных политиках голосовой маршрутизации. 

- **Голосовые маршруты** — шаблон номера и набор сетевых шлюзов, используемых для звонков, где номер звонка соответствует шаблону.

- **Сетевой шлюз PSTN** — указатель на объект SBC, который также хранит конфигурацию, которая применяется при размещении вызова через SBC, например переадресация (PAI) или Предпочтительные кодеки. можно добавлять в Голосовые маршруты.

## <a name="example-1-voice-routing-with-one-pstn-usage"></a>Пример 1: Маршрутизация голосовой связи с использованием одной PSTN

На приведенной ниже схеме показаны два примера политик маршрутизации голосовой связи в потоке звонков.

**Поток звонков 1 (слева):** Если пользователь выполняет вызов + 1 425 XXX XX XX или + 1 206 XXX XX XX, вызов передается на SBC sbc1.contoso.biz или sbc2.contoso.biz. Если ни sbc1.contoso.biz, ни sbc2.contoso.biz недоступны, вызов отбрасывается. 

**Направление звонка 2 (справа):** Если пользователь совершает вызов + 1 425 XXX XX XX или + 1 206 XXX XX XX, вызов сначала пересылается на SBC sbc1.contoso.biz или sbc2.contoso.biz. Если ни один из SBC недоступен, будет применяться маршрут с более низким приоритетом (sbc3.contoso.biz и sbc4.contoso.biz). Если ни одна из этих SBCs недоступна, вызов отбрасывается. 

![Примеры политики голосовой маршрутизации](media/ConfigDirectRouting-VoiceRoutingPolicyExamples.png)

В обоих примерах, когда маршрут голоса назначается приоритетами, однобайтовые данные маршрутов выполняются в случайном порядке.

  > [!NOTE]
  > Если у пользователя нет лицензии на план звонков Microsoft, звонки на любое число, кроме номеров, соответствующих шаблонам + 1 425 XXX XX XX или + 1 206 XXX XX XX, удаляются. Если у пользователя есть лицензия на план звонков, этот звонок автоматически маршрутизируется согласно политикам плана вызовов Microsoft. План звонков Microsoft автоматически применяется к последнему маршруту для всех пользователей с лицензией на план звонков Microsoft и не требует дополнительной настройки маршрутизации звонков.

В примере, показанном на приведенной ниже схеме, маршрут голосовой связи добавляется для отправки звонков на все остальные номера США и Канады (звонки, находящиеся под названием "шаблон номера" + 1 XXX XXX XX XX).

![Политика маршрутизации голосовой связи с третьим маршрутом](media/ConfigDirectRouting-VoiceRoutingPolicywith3rdroute.png)

Для всех остальных звонков:

- Если у пользователя есть обе лицензии (телефонная система Майкрософт и план звонков по Microsoft), используется автоматический маршрут. 
- Если ничего не соответствует шаблонам, созданным администратором в режиме онлайновых голосовых сообщений, этот звонок направляется через план звонков по Microsoft.
- Если у пользователя есть только телефонная система Microsoft, вызов отбрасывается из-за того, что нет доступных правил сопоставления.

  > [!NOTE]
  > Значение приоритета для маршрута "Other + 1" не имеет значения в этом случае, так как есть только один маршрут, соответствующий шаблону + 1 XXX XXX XX XX. Если пользователь вызывает + 1 324 567 89 89, а оба sbc5.contoso.biz и sbc6.contoso.biz недоступны, Звонок отбрасывается.

В приведенной ниже таблице перечислены конфигурации с тремя голосовыми маршрутами. В этом примере все три маршрута являются частью одного и того же использования КТСОП "США и Канада".  Все маршруты связаны с использованием КТСОП "США и Канада", а использование КТСОП связано с политикой голосовой маршрутизации "только США". 

|**Использование ТСОП**|**Маршрут голосовой связи**|**Шаблон номеров**|**Priority**|**БАЙТОВ**|**Описание**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|Только для США|"Redmond 1"|^\\+ 1 (425\|206) (\d{7}) $|1|sbc1.contoso.biz<br/>sbc2.contoso.biz|Активный маршрут для вызываемых номеров + 1 425 XXX XX XX или + 1 206 XXX XX XX|
|Только для США|"Redmond 2"|^\\+ 1 (425\|206) (\d{7}) $|2|sbc3.contoso.biz<br/>sbc4.contoso.biz|Маршрут резервного копирования для вызываемых номеров + 1 425 XXX XX XX или + 1 206 XXX XX XX|
|Только для США|"Other + 1"|^\\+ 1 (\d{10}) $|3|sbc5.contoso.biz<br/>sbc6.contoso.biz|Маршрут для вызываемых номеров + 1 XXX XXX XX XX (кроме + 1 425 XXX XX XX или + 1 206 XXX XX XX)|
|||||||


### <a name="example-1-configuration-steps"></a>Пример 1: этапы настройки

В следующем примере показано, как выполнять следующие действия:

- Создание единственной использование PSTN 
- Настройка трех голосовых маршрутов
- Создание политики голосовой маршрутизации
- Назначение политики для пользователя Spencer низкий

**Действие 1:** Создание использования PSTN "США и Канада"

В удаленном сеансе PowerShell в Skype для бизнеса введите:

```PowerShell
Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="US and Canada"}
```

Убедитесь в том, что использование было создано путем ввода: 
```PowerShell
Get-CSOnlinePSTNUsage
``` 
Возвращающий список имен, которые могут быть усечены:
```console
Identity    : Global
Usage       : {testusage, US and Canada, International, karlUsage. . .}
```
В приведенном ниже примере показан результат выполнения команды `(Get-CSOnlinePSTNUsage).usage` PowerShell для отображения полных имен (не усеченных):

<pre>
 testusage
 US and Canada
 International
 karlUsage
 New test env
 Tallinn Lab Sonus
 karlUsage2
 Unrestricted
 Two trunks
</pre>

**Шаг 2.** В сеансе PowerShell в Skype для бизнеса Online создайте три маршрута: Redmond 1, Redmond 2 и другие + 1, как показано в предыдущей таблице.

Чтобы создать маршрут "Redmond 1", введите:

```PowerShell
New-CsOnlineVoiceRoute -Identity "Redmond 1" -NumberPattern "^\+1(425|206)
(\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
```

Возвращаемое значение.
<pre>
Identity                : Redmond 1
Priority                : 1
Description             :
NumberPattern           : ^\+1(425|206) (\d{7})$
OnlinePstnUsages        : {US and Canada}
OnlinePstnGatewayList   : {sbc1.contoso.biz, sbc2.contoso.biz}
Name                    : Redmond 1
</pre>
Чтобы создать маршрут на 2 Redmond, введите:

```PowerShell
New-CsOnlineVoiceRoute -Identity "Redmond 2" -NumberPattern "^\+1(425|206)
(\d{7})$" -OnlinePstnGatewayList sbc3.contoso.biz, sbc4.contoso.biz -Priority 2 -OnlinePstnUsages "US and Canada"
```

Чтобы создать другой маршрут + 1, введите:

```PowerShell
New-CsOnlineVoiceRoute -Identity "Other +1" -NumberPattern "^\+1(\d{10})$"
-OnlinePstnGatewayList sbc5.contoso.biz, sbc6.contoso.biz -OnlinePstnUsages "US and Canada"
```

  > [!CAUTION]
  > Убедитесь, что регулярное выражение в атрибуте NumberPattern является допустимым выражением. Вы можете протестировать его с помощью этого веб-сайта:[https://www.regexpal.com](https://www.regexpal.com)

В некоторых случаях необходимо перенаправлять все вызовы на один и тот же SBC; Используйте-NumberPattern ". *"

Перенаправлять все вызовы в один и тот же SBC.

```PowerShell
Set-CsOnlineVoiceRoute -id "Redmond 1" -NumberPattern ".*" -OnlinePstnGatewayList sbc1.contoso.biz
```

Проверьте, правильно ли вы настроили маршрут, выполнив команду `Get-CSOnlineVoiceRoute` PowerShell, используя указанные ниже параметры.

```PowerShell
Get-CsOnlineVoiceRoute | Where-Object {($_.priority -eq 1) -or ($_.priority -eq 2) or ($_.priority -eq 4) -Identity "Redmond 1" -NumberPattern "^\+1(425|206) (\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
```
Что должно вернуть:
<pre>
Identity            : Redmond 1 
Priority            : 1
Description     : 
NumberPattern       : ^\+1(425|206) (\d{7})$
OnlinePstnUsages    : {US and Canada}    
OnlinePstnGatewayList   : {sbc1.contoso.biz, sbc2.contoso.biz}
Name            : Redmond 1
Identity        : Redmond 2 
Priority            : 2
Description     : 
NumberPattern       : ^\+1(425|206) (\d{7})$
OnlinePstnUsages    : {US and Canada}    
OnlinePstnGatewayList   : {sbc3.contoso.biz, sbc4.contoso.biz}
Name            : Redmond 2
    
Identity        : Other +1 
Priority            : 4
Description     : 
NumberPattern       : ^\+1(\d{10})$
OnlinePstnUsages    : {US and Canada}    
OnlinePstnGatewayList   : {sbc5.contoso.biz, sbc6.contoso.biz}
Name            : Other +1
</pre>

В примере для маршрута "Other + 1" автоматически назначается приоритет 4. 

**Шаг 3.** Создайте политику голосовой маршрутизации "только США" и добавьте в политику использование КТСОП "США и Канада".

В сеансе PowerShell в Skype для бизнеса Online введите:

```PowerShell
New-CsOnlineVoiceRoutingPolicy "US Only" -OnlinePstnUsages "US and Canada"
```

Результат показан в этом примере:

<pre>
Identity            : Tag:US only
OnlinePstnUsages    : {US and Canada}
Description         :
RouteType           : BYOT
</pre>

**Шаг 4:** С помощью PowerShell вы можете предоставить пользователю политику маршрутизации голосовой связи Spencer низкий:

В сеансе PowerShell в Skype для бизнеса Online введите:

```PowerShell
Grant-CsOnlineVoiceRoutingPolicy -Identity "Spencer Low" -PolicyName "US Only"
```

Чтобы проверить назначение политики, введите следующую команду:

```PowerShell
Get-CsOnlineUser "Spencer Low" | select OnlineVoiceRoutingPolicy
```

Команда возвращает следующее:
<pre>
OnlineVoiceRoutingPolicy
---------------------
US Only
</pre>

## <a name="example-2-voice-routing-with-multiple-pstn-usages"></a>Пример 2: Маршрутизация голосовой связи с несколькими использованием PSTN

Политика маршрутизации голосовой связи, созданная в примере 1, позволяет звонить только в США и Канаде (за исключением случаев, когда у пользователя также выделена лицензия на план звонков Microsoft).

В приведенном ниже примере вы можете создать политику маршрутизации голосовой связи "нет ограничений". Политика повторно использует использование КТСОП "США и Канада", созданное в примере 1, а также новую использование PSTN "Международная".  Эта политика маршрутизирует все другие вызовы на SBCs sbc2.contoso.biz и sbc5.contoso.biz. 

Приведенные примеры применяют политику "только для США" для пользователей Spencer Low и политики "нет ограничений" для пользователя Джон лесу таким образом, чтобы маршрутизация была показана ниже.

- Spencer низкий – только политика США.  Звонки разрешены только в США и Канаде. При обращении к диапазону номеров Redmond необходимо использовать конкретный набор SBCs. Номера, не относящиеся к США, не будут маршрутизироваться, если пользователю не назначена лицензия на план звонков.

- Джон лесу – Международная политика.  Звонки разрешены любому числу. При обращении к диапазону номеров Redmond необходимо использовать конкретный набор SBCs. Номера, не относящиеся к США, будут маршрутизироваться с помощью sbc2.contoso.biz и sbc5.contoso.biz.

![Политика маршрутизации голосовой связи, назначенная пользователю Spencer низкий](media/ConfigDirectRouting-VoiceRoutingPolicyAssignedtoSpencerLow.png)

Для всех других звонков, если у пользователя есть обе лицензии (телефонная система Майкрософт и план звонков по Microsoft), используется автоматический маршрут. Если ничего не соответствует шаблонам, созданным администратором в режиме онлайновых голосовых сообщений, вызов осуществляется с помощью плана звонков Microsoft.  Если у пользователя есть только телефонная система Microsoft, вызов отклоняется из-за того, что нет доступных правил сопоставления.

![Политика маршрутизации голосовой связи, назначенная пользователю John лесу](media/ConfigDirectRouting-VoiceRoutingPolicyAssignedtoJohnWoods.png)

В таблице ниже приведено краткое описание политики маршрутизации "без ограничений" и для голосовых маршрутов. 

|**Использование ТСОП**|**Маршрут голосовой связи**|**Шаблон номеров**|**Priority**|**БАЙТОВ**|**Описание**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|Только для США|"Redmond 1"|^\\+ 1 (425\|206) (\d{7}) $|1|sbc1.contoso.biz<br/>sbc2.contoso.biz|Активный маршрут для номеров вызываемых абонентов + 1 425 XXX XX XX или + 1 206 XXX XX XX|
|Только для США|"Redmond 2"|^\\+ 1 (425\|206) (\d{7}) $|2|sbc3.contoso.biz<br/>sbc4.contoso.biz|Маршрут резервного копирования для номеров вызываемых абонентов + 1 425 XXX XX XX или + 1 206 XXX XX XX|
|Только для США|"Other + 1"|^\\+ 1 (\d{10}) $|3|sbc5.contoso.biz<br/>sbc6>. contoso.biz|Маршрут для вызываемых номеров + 1 XXX XXX XX XX (кроме + 1 425 XXX XX XX или + 1 206 XXX XX XX)|
|International|International|\d +|4|sbc2.contoso.biz<br/>sbc5.contoso.biz|Маршрут для любого числового шаблона |


  > [!NOTE]
  > - Порядок использования PSTN в политиках маршрутизации голосовой связи очень важен. Использование применяется по порядку, и если соответствие обнаружено при первом использовании, другие варианты использования никогда не оцениваются. Использование КТСОП "Международная" должно быть размещено после использования КТСОП "только США". Чтобы изменить порядок использования PSTN, выполните `Set-CSOnlineVoiceRoutingPolicy` команду. <br/>Например, чтобы изменить порядок с "США и Канада", сначала и "международные" секунд на обратный порядок, выполните указанные ниже действия.<br/> `Set-CsOnlineVoiceRoutingPolicy -id tag:"no Restrictions" -OnlinePstnUsages @{Replace="International", "US and Canada"}`
 > - Приоритет для голосовых маршрутов "другие + 1" и "международные" назначаются автоматически. Они не имеют значения, если у них более низкие приоритеты, чем "Redmond 1" и "Redmond 2".


### <a name="example-2-configuration-steps"></a>Пример 2: этапы настройки

В следующем примере показано, как выполнять следующие действия:

- Создание нового использования PSTN, называемого международным
- Создать новый голосовой маршрут с именем International
- Создание политики голосовой маршрутизации с именем "нет ограничений"
- Назначение политики пользователю John лесу


**Действие 1**: Создайте использование КТСОП "Международная". 

В удаленном сеансе PowerShell в Skype для бизнеса Online введите:

```PowerShell
Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="International"}
```

**Действие 2**: Создайте новый голосовой маршрут "Международная".

```PowerShell
New-CsOnlineVoiceRoute -Identity "International" -NumberPattern ".*" -OnlinePstnGatewayList sbc2.contoso.biz, sbc5.contoso.biz -OnlinePstnUsages "International"
```
Возвращаемое значение.

<pre>
Identity                  : International
Priority                  : 5
Description               :
NumberPattern             : .*
OnlinePstnUsages          : {International}
OnlinePstnGatewayList     : {sbc2.contoso.biz, sbc5.contoso.biz}
Name                      : International
</pre>

**Шаг 3**: Создание политики маршрутизации голосовой связи "без ограничений". 

Использование PSTN "Redmond 1" и "Redmond" используются в этой политике маршрутизации голосовой связи для сохранения особой обработки звонков на номера "+ 1 425 XXX XX XX" и "+ 1 206 XXX XX XX" как локальных, так и локальных звонков.

  ```PowerShell
  New-CsOnlineVoiceRoutingPolicy "No Restrictions" -OnlinePstnUsages "US and Canada", "International"
  ```

Обратите внимание на порядок использования PSTN:

  а) Если вы вызываете число "+ 1 425 XXX XX XX" с использованием описанных ниже способов, вызов проходит по маршруту, заданному в разделе "США и Канада", и применяется специальная логика маршрутизации. Таким образом, вызов пересылается сначала с помощью sbc1.contoso.biz и sbc2.contoso.biz, а затем sbc3.contoso.biz и sbc4.contoso.biz в качестве маршрутов резервного копирования.

  б) Если "Международная" использование PSTN перед "US и Канада", то звонки в + 1 425 XXX XX XX пересылаются в sbc2.contoso.biz и sbc5.contoso.biz как часть логики маршрутизации. Введите команду:

  ```PowerShell
  New-CsOnlineVoiceRoutingPolicy "No Restrictions" -OnlinePstnUsages "US and Canada", "International"
  ```

Возвращаемое значение.

    <pre>
    Identity              : International 
    OnlinePstnUsages : {US and Canada, International}    
    Description      :  
    RouteType             : BYOT
    </pre>

**Действие 4**: назначьте политику маршрутизации голосовой связи пользователю John лесу с помощью следующей команды.

```PowerShell
Grant-CsOnlineVoiceRoutingPolicy -Identity "John Woods" -PolicyName "No Restrictions”
```

Затем проверьте назначение с помощью команды: 

```PowerShell
Get-CsOnlineUser "John Woods" | Select OnlineVoiceRoutingPolicy
```

Возвращаемое значение.

<pre>
OnlineVoiceRoutingPolicy
------------------------
No Restrictions
</pre>

Результат заключается в том, что политика голосовой связи, примененная к вызовам Джон лесу, не ограничена, и она будет соответствовать логике маршрутизации звонков, доступной для США, Канады и международных звонков.



## <a name="see-also"></a>См. также

[Планирование прямой маршрутизации](direct-routing-plan.md)

[Настройка прямой маршрутизации](direct-routing-configure.md)
