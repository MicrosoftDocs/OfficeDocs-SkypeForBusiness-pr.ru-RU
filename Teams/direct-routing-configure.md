---
title: Настройка прямой маршрутизации
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
- Teams_ITAdmin_Help
- M365-voice
appliesto:
- Microsoft Teams
description: Сведения о том, как настроить прямую маршрутизацию Microsoft Phone System.
ms.openlocfilehash: 38938846c594cbb325193e42111ba8dff528f17f
ms.sourcegitcommit: de7e0afbd40bbe52994ab99d85cf9e95ecbc4a6c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/09/2019
ms.locfileid: "37434936"
---
# <a name="configure-direct-routing"></a>Настройка прямой маршрутизации

> [!Tip]
> Просмотрите следующий сеанс, чтобы узнать о преимуществах прямой маршрутизации, о том, как ее спланировать и развертывание: [Прямая маршрутизация в Microsoft Teams](https://aka.ms/teams-direct-routing)

Если вы еще не сделали этого, прочтите [маршрут на прямую маршрутизацию](direct-routing-plan.md) для необходимых компонентов и просмотрите другие действия, которые необходимо выполнить перед настройкой сети Microsoft Phone System. 

В этой статье описано, как настроить прямую маршрутизацию Microsoft Phone System. В нем показано, как связать поддерживаемый контроллер границ сеанса (SBC) для прямой маршрутизации и настроить пользователей Microsoft Teams для подключения к телефонной сети общего пользования (PSTN). Чтобы выполнить шаги, описанные в этой статье, администраторы должны ознакомиться с командлетами PowerShell. Дополнительные сведения об использовании PowerShell можно найти в разделе [Настройка компьютера для Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell). 

Мы рекомендуем убедиться, что ваш SBC уже настроен так, как рекомендовано вашим поставщиком SBC. 

- [Документация по развертыванию AudioCodes](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams)
- [Документация по развертыванию Oracle](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)
- [Документация по развертыванию связи с лентой](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions/direct-routing-microsoft-teams-calling)
- [Документация по развертыванию системы TE (аниноде)](https://www.anynode.de/anynode-and-microsoft-teams/)

Вы можете настроить телефонную систему Microsoft и разрешить пользователям использовать прямую маршрутизацию, а затем настроить Microsoft Teams в качестве основного клиента, выполнив следующие действия: 

- [Связывание SBC с телефонной системой Microsoft и проверка связывания](#pair-the-sbc-to-the-direct-routing-service-of-phone-system)
- [Включение поддержки прямой маршрутизации для пользователей](#enable-users-for-direct-routing-service)
- Убедитесь в том, что Microsoft Teams является предпочтительным клиентским абонентом для пользователей

## <a name="pair-the-sbc-to-the-direct-routing-service-of-phone-system"></a>Связывание SBC с прямой маршрутизацией в телефонной системе 

Ниже приведены три высокоуровневые действия, позволяющие подключать и связывать одноранговые SBC-интерфейсы с прямыми маршрутами. 

- Подключение к центру администрирования **Skype для бизнеса Online** с помощью PowerShell 
- Связывание SBC 
- Проверка связывания 

### <a name="connect-to-skype-for-business-online-by-using-powershell"></a>Подключение к Skype для бизнеса Online с помощью PowerShell 

Вы можете использовать сеанс PowerShell, подключенный к клиенту, для связывания SBC с интерфейсом Direct Routing. Чтобы открыть сеанс PowerShell, выполните шаги, описанные в разделе [Настройка компьютера для Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell). 
 
После установки удаленного сеанса PowerShell убедитесь, что вы видите команды для управления SBC. Чтобы проверить команды, введите (или скопируйте или вставьте) в сеансе PowerShell следующую команду и нажмите клавишу ВВОД: 

```
Get-Command *onlinePSTNGateway*
```

Ваша команда вернет четыре показанные здесь функции, которые позволят вам управлять этим SBC. 

<pre>
CommandType    Name                       Version    Source 
-----------    ----                       -------    ------ 
Function       Get-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt 
Function       New-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt 
Function       Remove-CsOnlinePSTNGateway 1.0        tmp_v5fiu1no.wxt 
Function       Set-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt
</pre>   


### <a name="pair-the-sbc-to-the-tenant"></a>Связывание SBC с клиентом 

Чтобы связать SBC с клиентом, в сеансе PowerShell введите следующую команду и нажмите клавишу ВВОД: 

```
New-CsOnlinePSTNGateway -Fqdn <SBC FQDN> -SipSignallingPort <SBC SIP Port> -MaxConcurrentSessions <Max Concurrent Sessions the SBC can handle> -Enabled $true 
```
  > [!NOTE]
  > 1. Мы настоятельно рекомендуем задать максимальное количество вызовов в SBC, используя сведения, которые можно найти в документации по SBC. Это ограничение инициирует уведомление, если объект SBC находится на уровне емкости.
  > 2. Вы можете присвоить значение SBC только в том случае, если доменная часть своего полного доменного имени соответствует одному из \*доменов, зарегистрированных в вашем клиенте, за исключением onmicrosoft.com. Использование \*доменных имен onmicrosoft.com не поддерживается для полного доменного имени SBC. Например, если у вас есть два доменных имен:<br/><br/>
  > **contoso**. com<br/>**contoso**. onmicrosoft.com<br/><br/>
  > Для имени SBC можно использовать имя sbc.contoso.com. При попытке связывания SBC с именем SBC. contoso. ABC система не позволит вам, так как домен не принадлежит этому клиенту.<br/>
  > Помимо домена, зарегистрированного в клиенте, важно, чтобы пользователь с этим доменом и назначенной лицензией E3 или водо. В противном случае появится следующее сообщение об ошибке:<br/>
  `Can not use the “sbc.contoso.com” domain as it was not configured for this tenant`.

```
New-CsOnlinePSTNGateway -Identity sbc.contoso.com -Enabled $true -SipSignallingPort 5067 -MaxConcurrentSessions 100 
```
Дает
<pre>
Identity              : sbc.contoso.com 
Fqdn                  : sbc.contoso.com 
SipSignallingPort     : 5067 
FailoverTimeSeconds   : 10 
ForwardCallHistory    : False 
ForwardPai            : False 
SendSipOptions        : True 
MaxConcurrentSessions : 100 
Enabled               : True   
</pre>
В процессе связывания можно настроить дополнительные параметры. Однако в предыдущем примере показаны только минимально необходимые параметры. 
 
В таблице ниже перечислены дополнительные параметры, которые можно использовать при настройке параметров для`New-CsOnlinePstnGateway`

|Обязательно?|Имя|Описание|По умолчанию|Возможные значения|Тип и ограничения|
|:-----|:-----|:-----|:-----|:-----|:-----|
|Да|Полное доменное имя|Полное доменное имя SBC |Нет|Нонефкдн имя, ограничение 63 символов|Строка, список допустимых и недопустимых символов в [соглашениях об именовании в Active Directory для компьютеров, доменов, сайтов и подразделений](https://support.microsoft.com/help/909264)|
|Нет|медиабипасс |Параметр, обозначенный SBC, поддерживает обход мультимедиа, и администратор хочет использовать его.|Нет|Верно<br/>False|Boolean|
|Да|сипсигналлингпорт |Порт прослушивания, используемый для связи с прямыми службами маршрутизации с помощью протокола TLS (Transport Layer Security).|Нет|Любой порт|от 0 до 65535 |
|Нет|фаиловертимесекондс |Если для этого параметра установлено значение 10 (значения по умолчанию), исходящие вызовы, которые не ответили шлюзом в течение 10 секунд, пересылаются на следующую доступную магистраль. Если дополнительных каналов связи нет, Звонок автоматически удаляется. В организации с медленными ответами сетей и шлюзов, это может приводить к необязательному пропуску вызовов. Значение по умолчанию — 10.|5-10|Число|Типом|
|Нет|ForwardCallHistory |Означает, будет ли переадресовываться по магистральному каналу сведения о журнале звонков. Если этот флажок установлен, прокси-сервер Office 365 КТСОП отправляет два заголовка: журнал — информация и на которую указывает обращение. Значением по умолчанию является **ложь** ($false). |False|Верно<br/>False|Boolean|
|Нет|ForwardPAI|Указывает, будет ли переадресовываться заголовок P-Asserted-Identity (PAI) одновременно с вызовом. Заголовок PAI предоставляет способ проверки удостоверения абонемента. Если включено, будет также отправлен заголовок "Конфиденциальность: ИД". Значением по умолчанию является **ложь** ($false).|False|Верно<br/>False|Boolean|
|Нет|сендсипоптионс |Определяет, будет ли SBC или не будет отправлять параметры SIP. Если отключено, SBC будет исключен из системы мониторинга и оповещения. Настоятельно рекомендуем включить параметры SIP. Значение по умолчанию — **true**. |Верно|Верно<br/>False|Boolean|
|Нет|максконкуррентсессионс |Используется системой оповещения. Если задано какое либо значение, система оповещения создаст оповещение для администратора клиента, если число параллельных сеансов составляет 90% или выше этого значения. Если параметр не задан, оповещения не создаются. Тем не менее, система мониторинга будет сообщать количество параллельных сеансов каждые 24 часа. |Значения|Значения<br/>от 1 до 100 000 ||
|Нет|медиарелайраутинглокатионоверриде |Позволяет выбрать путь для мультимедиа вручную. Прямая маршрутизация назначает центр обработки данных для пути к носителю, основываясь на общедоступном IP-адресе SBC. Мы всегда Выбери ближайший вариант в центре обработки данных SBC. Тем не менее, в некоторых случаях публичный IP-адрес, например диапазон US, может быть назначен для SBC, находящегося в Европе. В этом случае мы будем использовать не оптимальный путь к носителю. Этот параметр позволяет вручную настроить предпочтительный регион для передачи данных мультимедиа. Мы рекомендуем установить этот параметр только в том случае, если журнал звонков явно указывает на то, что автоматическое назначение центра обработки данных для пути к носителю не присвоено ближайшему элементу в центре обработки данных SBC. |Нет|Коды стран в формате ISO||
|Нет|Включено|Используется для включения этого SBC для исходящих вызовов. Можно использовать для временного удаления SBC, в то время как он обновляется или идет на обслуживание. |False|Верно<br/>False|Boolean|
 
### <a name="verify-the-sbc-pairing"></a>Проверка связывания SBC 

Проверьте подключение: 
- Убедитесь, что SBC есть в списке парных SBCs. 
- Проверьте параметры SIP. 
 
#### <a name="validate-if-the-sbc-is-on-the-list-of-paired-sbcs"></a>Проверка того, что SBC находится в списке парных SBCs 

После связывания SBC убедитесь, что SBC представлен в списке парных SBCs, выполнив следующую команду в удаленном сеансе PowerShell.`Get-CSOnlinePSTNGateway`

Попарный шлюз должен отображаться в списке, как показано в приведенном ниже примере, и убедитесь, что параметр *Enabled* отображает значение **Истина**. Ведите

```
Get-CsOnlinePSTNGateway -Identity sbc.contoso.com  
```
Возвращаемое значение.
<pre>
Identity              : sbc.contoso.com  
Fqdn                  : sbc.contoso.com 
SipSignallingPort     : 5067 
CodecPriority         : SILKWB,SILKNB,PCMU,PCMA 
ExcludedCodecs        :  
FailoverTimeSeconds   : 10 
ForwardCallHistory    : False 
ForwardPai            : False 
SendSipOptions        : True 
MaxConcurrentSessions : 100 
Enabled               : True 
</pre>

#### <a name="validate-sip-options-flow"></a>Проверка потока параметров SIP 

Для проверки связывания с помощью исходящих параметров SIP используйте интерфейс управления SBC и убедитесь, что SBC получает ответы на 200 ОК в сообщениях с параметрами исходящих параметров.

Когда прямая маршрутизация видит параметры входящего трафика, она начнет отправлять сообщения параметров исходящих модулей SIP в FQDN, настроенном в поле "заголовок" в сообщении "параметры входящих". 

Для проверки связывания с помощью параметров входящего SIP используйте интерфейс управления SBC и посмотрите, что SBC отправляет ответы на сообщения параметров, поступившие от Direct Routing, и что код ответа, который он отправляет, — 200 ОК.

## <a name="enable-users-for-direct-routing-service"></a>Включение поддержки прямой маршрутизации для пользователей 

Когда вы будете готовы включить пользователей для службы прямой маршрутизации, выполните указанные ниже действия. 

1. Создание пользователя в Office 365 и назначение лицензии на телефонную систему. 
2. Убедитесь в том, что пользователь размещен в Skype для бизнеса Online. 
3. Настройте номер телефона и включите поддержку корпоративной голосовой и голосовой почты. 
4. Настройка голосовой маршрутизации. Маршрут будет проверяться автоматически.

### <a name="create-a-user-in-office-365-and-assign-the-license"></a>Создание пользователя в Office 365 и назначение лицензии 

Существует два способа создания нового пользователя в Office 365. Однако мы рекомендуем выбрать и использовать один из вариантов для устранения проблем с маршрутизацией. 

- Создайте пользователя в локальной службе каталогов Active Directory и синхронизируйте пользователя с облаком. Откройте раздел [интеграция локальных каталогов с Azure Active Directory](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect).
- Создайте пользователя прямо на портале администратора Office 365. В разделе [Добавление пользователей по отдельности или массово в Office 365 — Справка для администраторов](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec). 

Если развертывание Skype для бизнеса Online осуществляется совместно со Skype для бизнеса 2015 или Lync 2010/2013 локально, единственным поддерживаемым вариантом будет создание пользователя в локальной службе каталогов Active Directory и синхронизация пользователя с облаком (вариант 1). 

Обязательные лицензии: 

- Office 365 Корпоративная E3 (в том числе SfB Plan2, Exchange Plan2 и Teams) + телефонная система
- Office 365 Корпоративная + + + (в том числе SfB Plan2, Exchange Plan2, Teams и Phone System) 

Необязательные лицензии: 

- План звонков 
- Аудиоконференции 

### <a name="ensure-that-the-user-is-homed-in-skype-for-business-online"></a>Убедитесь в том, что пользователь размещен в Skype для бизнеса Online 

Для прямой маршрутизации требуется, чтобы пользователь был подключен в Skype для бизнеса Online. Чтобы проверить это, Взгляните на параметр Регистрарпул. В домене infra.lync.com должно быть значение.

1. Подключитесь к удаленной оболочке PowerShell.
2. Выдайте команду: 

```
Get-CsOnlineUser -Identity "<User name>" | fl RegistrarPool
``` 

### <a name="configure-the-phone-number-and-enable-enterprise-voice-and-voicemail"></a>Настройка номера телефона и включение корпоративной голосовой и голосовой почты 

После создания пользователя и назначения лицензии следует настроить свой номер телефона и голосовую почту. Это можно сделать одним из шагов. 

Чтобы добавить номер телефона и включить голосовую почту, выполните указанные ниже действия.
 
1. Подключитесь к удаленному сеансу PowerShell. 
2. Введите команду: 
 
```
Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true -OnPremLineURI tel:<E.164 phone number>
```

Например, чтобы добавить номер телефона пользователя "Спенцер Low", введите следующее: 

```
Set-CsUser -Identity "Spencer Low" -OnPremLineURI tel:+14255388797 -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
```

Номер телефона должен быть настроен как полный E. 164 номер телефона с кодом страны. 

  > [!NOTE]
  > Если в качестве номера телефона пользователя используется локальный, используйте локальную среду управления и панель управления Skype для бизнеса, чтобы настроить номер телефона пользователя. 

### <a name="configure-voice-routing"></a>Настройка голосовой маршрутизации 

В телефонной системе Microsoft есть механизм маршрутизации, который позволяет отправлять звонки на определенный SBC, основанный на следующих устройствах: 

- Названный шаблон номера 
- Вызываемый шаблон номера + определенный пользователь, который выполняет Звонок
 
SBCs можно назначить активными и архивировать. Это означает, что если объект SBC, настроенный как активный для этого шаблона номера, или шаблон числа + определенного пользователя, недоступен, звонки будут перенаправляться в одноэлементный объект SBC.
 
Маршрутизация звонков состоит из следующих элементов: 
- Политика маршрутизации голосовой связи — контейнер использования КТСОП; может назначаться пользователю или нескольким пользователям 
- Использование PSTN — контейнер для голосовых маршрутов и использование PSTN; могут совместно использоваться в разных политиках голосовой маршрутизации 
- Маршруты голосовой связи — шаблон номера и набор шлюзов в Интернет-шлюзах, которые должны использоваться для звонков, где номер звонка соответствует шаблону 
- Сетевой шлюз PSTN — указатель на SBC, также хранит конфигурацию, которая применяется при помещении звонка через SBC, например переадресация с подлинным идентификатором P-утвержденного (паи) или Предпочтительные кодеки. можно добавлять в Голосовые маршруты 

#### <a name="creating-a-voice-routing-policy-with-one-pstn-usage"></a>Создание политики голосовой маршрутизации с использованием одной PSTN 

На приведенной ниже схеме показаны два примера политик маршрутизации голосовой связи в потоке вызовов.

**Поток звонков 1 (слева):** Если пользователь выполняет вызов + 1 425 XXX XX XX или + 1 206 XXX XX XX, вызов передается на SBC sbc1.contoso.biz или sbc2.contoso.biz. Если ни sbc1.contoso.biz, ни sbc2.contoso.biz недоступны, вызов отбрасывается. 

**Направление звонка 2 (справа):** Если пользователь совершает вызов + 1 425 XXX XX XX или + 1 206 XXX XX XX, вызов сначала пересылается на SBC sbc1.contoso.biz или sbc2.contoso.biz. Если ни один из SBC недоступен, будет применяться маршрут с более низким приоритетом (sbc3.contoso.biz и sbc4.contoso.biz). Если ни одна из этих SBCs недоступна, вызов отбрасывается. 

![Примеры политики голосовой маршрутизации](media/ConfigDirectRouting-VoiceRoutingPolicyExamples.png)

В обоих примерах, когда маршрут голоса назначается приоритетами, однобайтовые данные маршрутов выполняются в случайном порядке.

  > [!NOTE]
  > Если у пользователя нет лицензии на план звонков Microsoft, звонки на любое число, кроме номеров, соответствующих шаблонам + 1 425 XXX XX XX или + 1 206 XXX XX XX, удаляются. Если у пользователя есть лицензия на план звонков, этот звонок автоматически маршрутизируется согласно политикам плана вызовов Microsoft. 

План звонков Microsoft автоматически применяется к последнему маршруту для всех пользователей с лицензией на план звонков Microsoft и не требует дополнительной настройки маршрутизации звонков.

В примере на приведенной ниже схеме маршрут голосовой связи добавляется для отправки звонков на все остальные звонки в США и Канаде (звонки, находящиеся под названием "номер" + 1 XXX XXX XX XX).

![Политика маршрутизации голосовой связи с третьим маршрутом](media/ConfigDirectRouting-VoiceRoutingPolicywith3rdroute.png)

Для всех других звонков, если у пользователя есть обе лицензии (телефонная система Майкрософт и план звонков по Microsoft), используется автоматический маршрут. Если ничего не соответствует шаблонам, созданным администратором в онлайновых голосовых маршрутах, направьте его через план звонков Microsoft.

Если у пользователя есть только телефонная система Microsoft, вызов отклоняется из-за того, что нет доступных правил сопоставления.

  > [!NOTE]
  > Значение приоритета для маршрута "Other + 1" в этом случае не имеет значения, так как есть только один маршрут, соответствующий шаблону + 1 XXX XXX XX XX. Если пользователь вызывает + 1 324 567 89 89, а оба sbc5.contoso.biz и sbc6.contoso.biz недоступны, Звонок отбрасывается.

В приведенной ниже таблице перечислены конфигурации с тремя голосовыми маршрутами. В этом примере все три маршрута являются частью одного и того же использования КТСОП "США и Канада".

|**Использование ТСОП**|**Маршрут голосовой связи**|**Шаблон номеров**|**Priority**|**БАЙТОВ**|**Описание**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|Только для США|"Redmond 1"|^\\+ 1 (425\|206) (\d{7}) $|1|sbc1.contoso.biz<br/>sbc2.contoso.biz|Активный маршрут для вызываемых номеров + 1 425 XXX XX XX или + 1 206 XXX XX XX|
|Только для США|"Redmond 2"|^\\+ 1 (425\|206) (\d{7}) $|2|sbc3.contoso.biz<br/>sbc4.contoso.biz|Маршрут резервного копирования для вызываемых номеров + 1 425 XXX XX XX или + 1 206 XXX XX XX|
|Только для США|"Other + 1"|^\\+ 1 (\d{10}) $|3|sbc5.contoso.biz<br/>sbc6.contoso.biz|Маршрут для вызываемых номеров + 1 XXX XXX XX XX (кроме + 1 425 XXX XX XX или + 1 206 XXX XX XX)|
|||||||

Все маршруты связаны с использованием КТСОП "США и Канада", а использование КТСОП связано с политикой голосовой маршрутизации "только США". В этом примере политика голосовой маршрутизации назначена пользователю Спенцер Low.

#### <a name="examples-of-call-routes"></a>Примеры маршрутов звонков

В приведенном ниже примере мы покажем, как настроить маршруты, использование PSTN и политики маршрутизации, а также назначить политику для пользователя.

**Действие 1:** Создайте использование КТСОП "США и Канада".

В удаленном сеансе PowerShell в Skype для бизнеса введите:

```
Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="US and Canada"}
```

Убедитесь в том, что использование было создано путем ввода: 
```
Get-CSOnlinePSTNUsage
``` 
Возвращающий список имен, которые могут быть усечены:
```
  Identity  : Global
  Usage     : {testusage, US and Canada, International, karlUsage. . .}
```
В примере ниже показано, как можно просмотреть результаты выполнения команды `(Get-CSOnlinePSTNUsage).usage` PowerShell для отображения полных имен (не усеченных). 
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

**Шаг 2.** В сеансе PowerShell в Skype для бизнеса Online создайте три маршрута: Redmond 1, Redmond 2 и другой + 1, как описано в предыдущей таблице. 

Чтобы создать маршрут "Redmond 1", введите:

  ```
  New-CsOnlineVoiceRoute -Identity "Redmond 1" -NumberPattern "^\+1(425|206)
  (\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
  ```

Возвращаемое значение.
<pre>
Identity                : Redmond 1
Priority            : 1
Description         :
NumberPattern       : ^\+1(425|206) (\d{7})$
OnlinePstnUsages    : {US and Canada}
OnlinePstnGatewayList   : {sbc1.contoso.biz, sbc2.contoso.biz}
Name            : Redmond 1
</pre>
Чтобы создать маршрут на 2 Redmond, введите:

```
New-CsOnlineVoiceRoute -Identity "Redmond 2" -NumberPattern "^\+1(425|206)
(\d{7})$" -OnlinePstnGatewayList sbc3.contoso.biz, sbc4.contoso.biz -Priority 2 -OnlinePstnUsages "US and Canada"
```

Чтобы создать другой маршрут + 1, введите:

```
New-CsOnlineVoiceRoute -Identity "Other +1" -NumberPattern "^\+1(\d{10})$"
-OnlinePstnGatewayList sbc5.contoso.biz, sbc6.contoso.biz -OnlinePstnUsages "US and Canada"
```

  > [!CAUTION]
  > Убедитесь, что регулярное выражение в атрибуте Нумберпаттерн является допустимым выражением. Вы можете протестировать его с помощью этого веб-сайта:[https://www.regexpal.com](https://www.regexpal.com)

В некоторых случаях необходимо перенаправлять все вызовы на один и тот же SBC; Пожалуйста, используйте-Нумберпаттерн ". *"

- Перенаправлять все вызовы в один и тот же SBC

    ```
    Set-CsOnlineVoiceRoute -id "Redmond 1" -NumberPattern ".*" 
     -OnlinePstnGatewayList sbc1.contoso.biz
    ```

Проверьте, правильно ли вы настроили маршрут, выполнив команду `Get-CSOnlineVoiceRoute` PowerShell, используя указанные ниже параметры. 

```
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

```
New-CsOnlineVoiceRoutingPolicy "US Only" -OnlinePstnUsages "US and Canada"
```

Результат показан в этом примере:

<pre>
Identity        : Tag:US only
OnlinePstnUsages    : {US and Canada}
Description         :
RouteType           : BYOT
</pre>

**Шаг 4:** Предоставьте пользователю Спенцер низкий уровень политики голосовой маршрутизации с помощью PowerShell.

- В сеансе PowerShell в Skype для бизнеса Online введите:

    ```Grant-CsOnlineVoiceRoutingPolicy -Identity "Spencer Low" -PolicyName "US Only"```

- Чтобы проверить назначение политики, введите следующую команду:

```
Get-CsOnlineUser "Spencer Low" | select OnlineVoiceRoutingPolicy
```
Возвращаемое значение.
<pre>
    OnlineVoiceRoutingPolicy
    ---------------------
    US Only
</pre>

#### <a name="creating-a-voice-routing-policy-with-several-pstn-usages"></a>Создание политики голосовой маршрутизации с несколькими использованием PSTN

Политика маршрутизации голосовой связи, созданная ранее, позволяет звонить только в США и Канаде (за исключением случаев, когда у пользователя также выделена лицензия на план звонков Microsoft).

В приведенном ниже примере вы можете создать политику маршрутизации голосовой связи "нет ограничений". Политика повторно использует использование КТСОП "США и Канада", созданное в предыдущем примере, а также новую использование PSTN "Международная". 

При этом все другие звонки на SBCs sbc2.contoso.biz и sbc5.contoso.biz переправляются. Приведенные примеры применяют политику "только для США" для пользователя "Спенцер Low" и никаких ограничений для пользователя "John лесу".

Спенцер низкий – звонки разрешены только в США и Канаде. При обращении к диапазону номеров Redmond необходимо использовать определенный набор SBC. Номера, не относящиеся к США, не будут маршрутизироваться, если пользователю не назначена лицензия на план звонков.

Джон лесу – звонки разрешены любому номеру. При обращении к диапазону номеров Redmond необходимо использовать определенный набор SBC. Номера, не относящиеся к США, будут маршрутизироваться через sbc2.contoso.biz и sbc5.contoso.biz.

![Политика маршрутизации голосовой связи, назначенная пользователю Спенцер низкий](media/ConfigDirectRouting-VoiceRoutingPolicyAssignedtoSpencerLow.png)

Для всех других звонков, если у пользователя есть обе лицензии (телефонная система Майкрософт и план звонков по Microsoft), используется автоматический маршрут. Если ничего не соответствует шаблонам, созданным администратором в онлайновых голосовых маршрутах, направьте его через план звонков Microsoft.

Если у пользователя есть только телефонная система Microsoft, вызов отклоняется из-за того, что нет доступных правил сопоставления.

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

#### <a name="example-of-voice-routing-policy-for-user-john-woods"></a>Пример политики голосовой маршрутизации для пользователя John лесу

Действия по созданию использования PSTN "международные", Голосовые маршруты "Международная", "политика маршрутизации голосовой связи", "нет ограничений", а затем назначение ее пользователю "John лесу".


1. Сначала необходимо создать использование КТСОП "Международная". В удаленном сеансе PowerShell в Skype для бизнеса Online введите:

   ```
   Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="International"}
   ```

2. Затем создайте новый голосовой маршрут "Международная".

   ```
   New-CsOnlineVoiceRoute -Identity "International" -NumberPattern ".*" -OnlinePstnGatewayList sbc2.contoso.biz, sbc5.contoso.biz -OnlinePstnUsages "International"
   ```
   Возвращаемое значение.

   <pre>
   Identity                  : International 
   Priority                      : 5
   Description                   : 
   NumberPattern                 : .*
   OnlinePstnUsages          : {International} 
   OnlinePstnGatewayList           : {sbc2.contoso.biz, sbc5.contoso.biz}
   Name                            : International
   </pre>
3. Затем создайте политику маршрутизации голосовой связи "без ограничений". Использование PSTN "Redmond 1" и "Redmond" используются в этой политике маршрутизации голосовой связи для сохранения особой обработки звонков на номера "+ 1 425 XXX XX XX" и "+ 1 206 XXX XX XX" как локальных, так и локальных звонков.

```
New-CsOnlineVoiceRoutingPolicy "No Restrictions" -OnlinePstnUsages "US and Canada", "International"
```

    Take note of the order of PSTN Usages:

    a. If a call made to number "+1 425 XXX XX XX" with the usages configured as in the following example, the call follows the route set in "US and Canada" usage and the special routing logic is applied. That is, the call is routed using sbc1.contoso.biz and sbc2.contoso.biz first, and then sbc3.contoso.biz and sbc4.contoso.biz as the backup routes. 

    b.  If "International" PSTN usage is before "US and Canada," calls to +1 425 XXX XX XX are routed to sbc2.contoso.biz and sbc5.contoso.biz as part of the routing logic. Enter the command:

    ```New-CsOnlineVoiceRoutingPolicy "No Restrictions" -OnlinePstnUsages "US and Canada", "International"```

   Который возвращает

  <pre>
   Identity     : International 
   OnlinePstnUsages     : {US and Canada, International}     
   Description      :  
   RouteType        : BYOT
  </pre>

4. Назначьте политику маршрутизации голосовой связи пользователю John лесу с помощью следующей команды.

   ```
   Grant-CsOnlineVoiceRoutingPolicy -Identity "John Woods" -PolicyName "No Restrictions”
   ```

   Затем проверьте назначение с помощью команды: 

   ```
   Get-CsOnlineUser "John Woods" | Select OnlineVoiceRoutingPolicy
   ```
   Возвращаемое значение.

<pre>
    OnlineVoiceRoutingPolicy
    ------------------------
    No Restrictions
</pre>

Результат заключается в том, что политика голосовой связи, примененная к вызовам Джон лесу, не ограничена, и она будет соответствовать логике маршрутизации звонков, доступной для США, Канады и международных звонков.

## <a name="assign-teams-only-mode-to-users-to-ensure-calls-land-in-microsoft-teams"></a>Назначение режима "только для Teams" для пользователей, которые должны обеспечивать звонки в Microsoft Teams

Для прямой маршрутизации необходимо, чтобы пользователи были в режиме "только Teams", чтобы обеспечить поступление входящих звонков в клиенте Teams. Чтобы перевести пользователей в режиме "только Teams", назначьте им экземпляр "Упградетотеамс" для Теамсупградеполици. Если в вашей организации используется Skype для бизнеса Server или Skype для бизнеса Online, ознакомьтесь со статьей сведения о взаимодействии между Skype и teams: [руководство по переносу и взаимодействию для организаций, использующих группы вместе с Skype для бизнеса](https://docs.microsoft.com/microsoftteams/migration-interop-guidance-for-teams-with-skype). 


## <a name="configuring-sending-calls-directly-to-voicemail"></a>Настройка отправки звонков непосредственно в голосовую почту

Прямая маршрутизация позволяет прекратить звонок пользователю и отправить его прямо на голосовую почту пользователей. Если вы хотите отправить звонок прямо в голосовую почту, прикрепите непрозрачность = App: голосовой почте к заголовку URI запроса. Например, "SIP: user@yourdomain.com; непрозрачный = приложение: Голосовая почта".
В этом случае пользователь Teams не получит уведомление о звонке, Звонок будет подключен непосредственно к голосовой почте пользователя.

## <a name="see-also"></a>См. также

[Планирование прямой маршрутизации](direct-routing-plan.md)
