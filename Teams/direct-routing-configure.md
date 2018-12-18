---
title: Настройка прямой маршрутизации
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.service:
- msteams
- skype-for-business-online
ms.prod: skype-for-business-itpro
localization_priority: Normal
search.appverid: MET150
ms.collection: Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
description: Сведения о настройке Microsoft телефонной системы прямой маршрутизации.
ms.openlocfilehash: cf856989cd4f87f4b46e1eb36cbeb403bf92b029
ms.sourcegitcommit: 8279beffec35fe8a75968245c6cb09f1d622370f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/18/2018
ms.locfileid: "27297913"
---
# <a name="configure-direct-routing"></a>Настройка прямой маршрутизации

> [!Tip]
> Просмотрите следующие сеанса, чтобы узнать о преимуществах прямой маршрутизации, как спланировать его и способе развертывания: [Прямой маршрутизации в группах Майкрософт](https://aka.ms/teams-direct-routing)

Если вы еще не сделали прочитайте [Планирование прямой маршрутизации](direct-routing-plan.md) наличие необходимых компонентов и просмотреть другие действия необходимо выполнить перед настройкой сети Microsoft телефонной системой. 

В этой статье описывается настройка прямой маршрутизации Microsoft телефонной системы. Описывается, как связать поддерживаемые пограничный контроллер сеансов (SBC) для прямой маршрутизации и способы настройки групп Майкрософт пользователям использовать прямой маршрутизации для подключения к общедоступной переключения телефонной сети общего пользования (PSTN). Для выполнения действий, описанных в данной статье, администраторы должны знакомы с командлеты PowerShell. Дополнительные сведения об использовании PowerShell в разделе [Настройка компьютера для Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell). 

Рекомендуется, чтобы подтвердить, что пограничного контроллера Сеансов уже настроен соответствии с рекомендациями по своему поставщику SBC: 

- [Документация по развертыванию AudioCodes](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams)
- [Лента Communications документации по развертыванию](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions/direct-routing-microsoft-teams-calling)

Можно настроить телефонной системой Microsoft и пользователи могли использовать прямой маршрутизации, а затем настроить группами Майкрософт как предпочитаемый вызывающего клиента, выполнив следующие действия: 

- [Пары SBC с телефонной системы Microsoft и проверки связывания](#pair-the-sbc-to-direct-routing-service-of-phone-system)
- [Включение пользователей для службы напрямую маршрутизации](#enable-users-for-direct-routing-service)
- [Убедитесь, что группами Майкрософт является предпочтительным вызывающего клиента для пользователей](#set-microsoft-teams-as-the-preferred-calling-client-for-users) 

## <a name="pair-the-sbc-to-direct-routing-service-of-phone-system"></a>Пары SBC для направления маршрутизации службы телефонной системой 

Ниже приведены три основных действия можно подключиться или пары SBC интерфейс прямой маршрутизации. 

- Подключение к центру администрирования **Скайп для бизнеса в Интернет** , с помощью PowerShell 
- Пара SBC 
- Проверка сопоставления 

### <a name="connect-to--skype-for-business-online-by-using-powershell"></a>Подключение к Скайп для бизнеса в Интернет с помощью PowerShell 

Можно использовать сеанс PowerShell, подключенных к клиенту связать SBC интерфейс прямой маршрутизации. Чтобы открыть сеанс PowerShell, выполните действия, указанные в [Настройка компьютера для Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell). 
 
После создания удаленного сеанса PowerShell, проверьте, что вы видите команды для управления SBC. Для проверки команды, введите или копирование и вставка в следующем в сеанс PowerShell и нажмите клавишу ВВОД: 

```
gcm *onlinePSTNGateway*
```

Команда вернет четыре функций, которые будут позволяют управлять их изготовителей. 

<pre>
CommandType    Name                       Version    Source 
-----------    ----                       -------    ------ 
Function       Get-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt 
Function       New-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt 
Function       Remove-CsOnlinePSTNGateway 1.0        tmp_v5fiu1no.wxt 
Function       Set-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt
</pre>   


### <a name="pair-the-sbc-to-the-tenant"></a>Пара SBC к клиенту 

Связать SBC к клиенту в сеанс PowerShell введите следующую команду и нажмите клавишу ВВОД: 

```
New-CsOnlinePSTNGateway -Fqdn <SBC FQDN> -SipSignallingPort <SBC SIP Port> -MaxConcurrentSessions <Max Concurrent Sessions the SBC can handle> -Enabled $true 
```
  > [!NOTE]
  > 1. Мы настоятельно рекомендуем Установка ограничения для SBC, с помощью сведений, можно найти в документации по SBC. Ограничение запустит уведомление, если SBC был создан на уровне мощности.
  > 2. Вы можете только обеспечить SBC с полным доменным ИМЕНЕМ, где домен часть имени соответствует одной из доменов, зарегистрированных в клиенту, за исключением \*. onmicrosoft.com. С помощью \*. omicrosoft.com доменных имен не поддерживается для имен SBC полное доменное имя. Например, если у вас есть два доменных имен:<br/><br/>
  > **Contoso**.com<br/>**Contoso**. onmicrosoft.com<br/><br/>
  > Для имени SBC можно использовать имя sbc.contoso.com. При попытке связать SBC с именем sbc.contoso.abc, система не позволит вам, как домен не принадлежит этот клиент.

```
New-CsOnlinePSTNGateway -Identity sbc.contoso.com -Enabled $true -SipSignallingPort 5067 -MaxConcurrentSessions 100 
```
Возвращает:
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
Доступны дополнительные методы, которые могут быть заданы во время связывания. В предыдущем примере тем не менее, минимально необходимые параметры показаны. 
 
В следующей таблице перечислены дополнительные параметры, которые можно использовать в настройке параметров для *New-CsOnlinePstnGateway*. 

|Обязательно?|Имя|Описание|По умолчанию|Возможные значения|Тип и ограничения|
|:-----|:-----|:-----|:-----|:-----|:-----|
|Да|Полное доменное имя|Полное ДОМЕННОЕ имя пограничного контроллера Сеансов |Нет|Имя NoneFQDN, ограничение 63 символов|Строка, список разрешенных и запрещенных символов на [соглашениях об именовании в Active Directory для компьютеров, доменов, сайты и подразделениями](https://support.microsoft.com/help/909264)|
|Нет|MediaBypass |Параметр зарезервирован для будущего использования. Параметра, указанное для SBC поддерживает обход сервера-посредника и администратор хочет его использования.|Нет|True<br/>False|Логическое|
|Да|SipSignallingPort |Прослушивающий порт, используемый для взаимодействия со службами прямой маршрутизации с помощью протокола безопасности TLS (Transport Layer).|Нет|Любой порт|от 0 до 65535 |
|Нет|FailoverTimeSeconds |Если задано значение 10 (значение по умолчанию), исходящие вызовы, которые не отвечает в течение 10 секунд шлюз направляются Далее доступные линии связи; Если нет дополнительных магистралей, звонок автоматически удаляются. В организации с медленными ответами сетей и шлюзов, это может приводить к необязательному пропуску вызовов. Значение по умолчанию — 10.| 10|Число|Int|
|Нет|ForwardCallHistory |Означает, будет ли переадресовываться по магистральному каналу сведения о журнале звонков. Если этот параметр включен, прокси-сервер Office 365 ТСОП отправляет два заголовки: сведений журнала и ссылается по. Значение по умолчанию — **False** ($False). |False|True<br/>False|Логическое|
|Нет|ForwardPAI|Указывает, будет ли переадресовываться заголовок P-Asserted-Identity (PAI) одновременно с вызовом. Заголовок PAI предоставляет способ проверки удостоверения абонемента. Значение по умолчанию — **False** ($False).|False|True<br/>False|Логическое|
|Нет|SendSIPOptions |Определяет, если SBC будет или не будет отправлять параметры SIP. Если этот параметр отключен, SBC будут исключены из системы мониторинга и оповещений. Настоятельно рекомендуется включить параметры SIP. Значение по умолчанию — **True**. |True|True<br/>False|Логическое|
|Нет|MaxConcurrentSessions |Используемый предупреждения системы. Если любое значение, предупреждения системы будет создать оповещение для администратора клиента, если количество одновременных сеансов является 90% или выше, чем это значение. Если параметр не задан, оповещения не создаются. Тем не менее система мониторинга сообщает количество одновременных сеансов каждые 24 часа. |NULL|NULL<br/>1 до 100 000 ||
|Нет|Включено *|Используется для включения этой SBC для исходящих звонков. Можно использовать для временно удалить SBC в процессе обновления или во время обслуживания. |False|True<br/>False|Логическое|
 
### <a name="verify-the-sbc-pairing"></a>Проверка подключения к SBC 

Проверьте подключение: 
- Проверьте, если в списке парного SBC будет SBC. 
- Проверка параметров SIP. 
 
#### <a name="validate-if-sbc-is-on-the-list-of-paired-sbcs"></a>Проверить, если SBC находится в списке парного их изготовителей 

По окончании пары SBC проверки SBC присутствует в списке парного их изготовителей, выполнив следующую команду в удаленный сеанс PowerShell:`Get-CSOnlinePSTNGateway`

Парного шлюза следует отображаются в списке, как показано в следующем примере и убедитесь, что параметр *Enabled* значение **True**. Введите:

```
Get-CsOnlinePSTNGateway -Identity sbc.contoso.com  
```
Которая возвращает:
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

#### <a name="validate-sip-options-flow"></a>Проверка потока SIP-параметры 

Для проверки связывания с помощью параметров исходящей SIP, с помощью интерфейса управления SBC и увидеть, что SBC получите 200 OK ответ на исходящие параметры.
  
При прямой маршрутизации видит входящие параметры, он будет запущен процесс исходящей параметры отправки SBC полное доменное имя, настроенных в поле Заголовок контакт входящего сообщения, параметры. 

Для проверки связывания с помощью параметров входящих SIP, с помощью интерфейса управления SBC и увидеть, что SBC получает ответ на параметры сообщения, поступающие из прямой маршрутизации и что код ответа 200 OK.  

## <a name="enable-users-for-direct-routing-service"></a>Включение пользователей для службы напрямую маршрутизации 

Когда вы готовы к Включение пользователей для службы напрямую маршрутизации, выполните следующие действия: 

1. Создание пользователя в Office 365 и назначьте лицензии на систему телефона. 
2. Убедитесь, что пользователь размещенный в Скайп для бизнеса в Интернет. 
3. Настройте номер телефона и включение корпоративной голосовой связи и голосовую почту. 
4. Настройка маршрутизации голосовых вызовов. Маршрут проверяется автоматически.  

### <a name="create-a-user-in-office-365-and-assign-the-license"></a>Создание пользователя в Office 365 и назначьте лицензии 

Существует два варианта для создания нового пользователя в Office 365. Тем не менее рекомендуется выбрать и использовать один из вариантов, чтобы избежать проблем с маршрутизацией вашей организации: 

- Создание пользователя в локальной службе Active Directory и синхронизация пользователей в облако. В разделе [Интеграция на локальную каталогов с помощью Azure Active Directory](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect).  
- Создание пользователя непосредственно в портал администратора Office 365. В разделе [Добавление пользователей по отдельности или набором для Office 365 — помощь администратора](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec). 

  При построении в системе, существует с Скайп для бизнеса 2015 или Lync 2010 или 2013 локальной только поддерживаемые параметр — для создания пользователя в локальной службе Active Directory и синхронизации пользователей в облаке (вариант 1). 

Необходимые лицензии: 

- Office 365 для предприятий E3 (включая SfB Plan2, Exchange Plan2 или группам) телефона системы  
- Office 365 корпоративный E5 (включая SfB Plan2, Exchange Plan2, групп и телефонной системой) 

Необязательный лицензии: 

- Вызов плана 
- Аудиоконференции 

### <a name="ensure-that-the-user-is-homed-in-skype-for-business-online"></a>Пользователь является, размещенными в Скайп для бизнеса в Интернет 

Прямое маршрутизации требует от пользователя быть размещен в Скайп для бизнеса в Интернет. Вы можете проверить, посмотрев параметр RegistrarPool. Он должен иметь значение в домене infra.lync.com.

1. Подключение к удаленной оболочки PowerShell.
2. Введите команду: 

```
Get-CsOnlineUser -Identity "<User name>" | fl RegistrarPool
``` 

### <a name="configure-the-phone-number-and-enable-enterprise-voice-and-voicemail"></a>Настройка номер телефона и включение корпоративной голосовой связи и голосовая почта 

После создания пользователя и назначена лицензия, следующим шагом является настройка их номер телефона и голосовую почту. Это можно сделать в одном шаге. 

Чтобы добавить номер телефона и включить для голосовой почты:
 
1. Подключение удаленного сеанса PowerShell. 
2. Введите команду: 
    
```
Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true -OnPremLineURI tel:+ phone number
```

Например чтобы добавить номер телефона для пользователя «Иван низкий», необходимо ввести следующее: 

```
Set-CsUser -Identity “Spencer Low" -OnPremLineURI tel:+14255388797 -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
```

Номер телефона должен быть настроен как полный номер телефона E.164 с код страны. 

  > [!NOTE]
  > Если номер телефона пользователя управляется локально, используется для настройки номер телефона пользователя в локальной Скайп для бизнеса командную консоль или панель управления. 

### <a name="configure-voice-routing"></a>Настройка маршрутизации голосовой связи 

Microsoft телефонной системой имеет маршрутизации механизм, позволяющий звонка для отправки определенных SBC на основе: 

- Вызов шаблон номера 
- Вызов шаблон номера + определенного пользователя, который делает вызов
 
SBC могут быть обозначены как активных и резервного копирования. Который означает, что при недоступности SBC, настроенный как активных этот шаблон номера или шаблон номера + определенного пользователя, а затем звонки будут перенаправляться к резервного копирования SBC.
 
Маршрутизация звонков состоит из следующих элементов: 
- Политика маршрутизации голосовой связи — контейнер для использования ТСОП; можно назначить пользователю или нескольким пользователям 
- Режимы работы с ТСОП — контейнер для маршрутов голосовых вызовов и использования ТСОП; можно совместно в различные политики маршрутизации голосовой связи 
- Маршруты – шаблон номера и набор Online шлюзы ТСОП, используемый для вызовов, где номер соответствует шаблону голосовой связи 
- Online шлюза ТСОП - указатель в SBC, также хранится конфигурация, которая применяется при звонок с помощью SBC, например переадресации P-Asserted-Identity (PAI) или предпочитаемое кодеков; можно добавить в маршрутов голосовых вызовов 

#### <a name="creating-a-voice-routing-policy-with-one-pstn-usage"></a>Создание политики маршрутизации голосовых данных с помощью одного работы с ТСОП 

На следующей схеме показана два примера политики маршрутизации голосовых данных в поток вызовов.

**Вызова потока 1 (слева):** Если пользователь совершает вызов +1 425 XXX XX XX или +1 206 XXX XX XX, звонок перенаправляется в SBC sbc1<span></span>. contoso.biz или sbc2<span></span>. contoso.biz. Если ни один из sbc1<span></span>. contoso.biz, ни sbc2<span></span>. contoso.biz доступны, вызов отклоняется. 

**Вызова поток 2 (справа):** Если пользователь совершает вызов +1 425 XXX XX XX или +1 206 XXX XX XX, вызов сначала перенаправляется в SBC sbc1<span></span>. contoso.biz или sbc2<span></span>. contoso.biz. Если ни один из SBC, предпринята попытка маршрут с низким приоритетом (sbc3<span></span>. contoso.biz и sbc4<span></span>. contoso.biz). Если ни один из их изготовителей недоступен, вызов отклоняется. 

![Показаны примеры политики маршрутизации голосовой связи](media/ConfigDirectRouting-VoiceRoutingPolicyExamples.png)

В обоих примерах пока маршрута голосовых вызовов назначается приоритеты, их изготовителей в маршруты проверяются в случайном порядке.

  > [!NOTE]
  > Если у пользователя также нет лицензии Майкрософт вызов планирование, звонков на любое число, кроме номеров, соответствующих шаблонов + +1 425 XXX XX XX или +1 206 XXX XX XX в пример конфигурации удаляются. Если у пользователя есть вызов планирование лицензии, звонок автоматически маршрутизируются в соответствии с политики в планирование вызов Microsoft. 

Планирование вызов Microsoft автоматически в качестве последнего маршрута применяется ко всем пользователям с лицензией Microsoft вызов планирование и не требует дополнительных вызовов конфигурации маршрутизации.

В примере показано на следующей схеме голосового маршрута добавляется для направления вызовов на всех других США и Канада номер (вызовы, которые будут входить называемое шаблон номера + 1 XXX XXX XX XX).

![Показывает маршрутизации политики третий маршрут голосовой связи](media/ConfigDirectRouting-VoiceRoutingPolicywith3rdroute.png)

Если пользователь имеет обе лицензии (Microsoft телефонной системой и вызов планирование Microsoft), для всех других вызовов используется автоматический маршрут. Если ничего не соответствует шаблоны номеров в созданное администратором online маршруты голосовой связи, маршрут с помощью вызова планирование Microsoft.

Если у пользователя есть только телефонной системой Microsoft, вызов отклоняется из-за соответствующие правила.

  > [!NOTE]
  > Значение приоритета для маршрута «Другие + 1» не имеет значения, таким образом, как это делается только один маршрут, который соответствует шаблону + 1 XXX XXX XX XX. Если пользователь выполняет запрос 89 89 567 324 + 1 и sbc5.contoso.biz и sbc6.contoso.biz недоступны, вызов отклоняется.

В следующей таблице обобщаются конфигурации, используя три маршруты голосовой связи. В этом примере все три маршруты являются частью одной работы с ТСОП «"Мне Нравится" и Canada».

|**Использование ТСОП**|**Маршрут голосовых вызовов**|**Шаблон номеров**|**Приоритет**|**SBC**|**Описание**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|"Мне НРАВИТСЯ" только|«Redmond 1»|^\\+ 1 (425\|206)(\d{7})$|1|sbc1<span></span>. contoso.biz<br/>sbc2<span></span>. contoso.biz|Active маршрута для вызываемого номера +1 425 XXX XX XX или +1 206 XXX XX XX|
|"Мне НРАВИТСЯ" только|«Redmond 2»|^\\+ 1 (425\|206)(\d{7})$|2|sbc3<span></span>. contoso.biz<br/>sbc4<span></span>. contoso.biz|Резервного копирования маршрута для вызываемого номера +1 425 XXX XX XX или +1 206 XXX XX XX|
|"Мне НРАВИТСЯ" только|«Другие + 1»|^\\+ 1 (\d{10}) $|3|sbc5<span></span>. contoso.biz<br/>sbc6<span></span>. contoso.biz|Маршрут для вызываемого номера + 1 XXX XXX XX XX (за исключением +1 425 XXX XX XX или +1 206 XXX XX XX)|
|||||||

Всех маршрутов, связанных с работы с ТСОП «"Мне Нравится" и Canada» и об использовании PSTN связан с политики маршрутизации голосовой связи «Только для США». В этом примере назначается пользователю Spencer Low политику маршрутизации голосовых вызовов.

#### <a name="examples-of-call-routes"></a>Примеры маршрутов звонков

В следующем примере мы показываем, как Настройка политики маршрутизации, использования ТСОП и маршрутов и назначить политику для пользователя.

**Шаг 1:** Создание работы с ТСОП «США и Канада.»

В поле Скайп для сеанса удаленной оболочки PowerShell бизнеса введите:

```
Set-CsOnlinePstnUsage  -Identity Global -Usage @{Add="US and Canada"}
```

Проверка создания посредством ввода данных об использовании. 
```
Get-CSOnlinePSTNUsage
``` 
Которого возвращается список имен, которые может усекаться:
```
  Identity  : Global
  Usage     : {testusage, US and Canada, International, karlUsage. . .}
```
В приведенном ниже примере можно увидеть результат выполнения команды PowerShell *`(Get-CSOnlinePSTNUsage).usage`* Отображение полного названия (не сокращается).    
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

**Шаг 2:** В сеанс PowerShell в Скайп для бизнеса в Интернет, создайте три маршрутов: Redmond 1, Redmond 2 и других + 1, как описано в предыдущей таблице. 

Чтобы создать маршрут «Redmond 1», введите:

  ```
  New-CsOnlineVoiceRoute -Identity "Redmond 1" -NumberPattern "^\+1(425|206)
  (\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
  ```

Которая возвращает:
<pre>
Identity                : Redmond 1
Priority            : 1
Description         :
NumberPattern       : ^\+1(425|206) (\d{7})$
OnlinePstnUsages    : {US and Canada}
OnlinePstnGatewayList   : {sbc1.contoso.biz, sbc2.contoso.biz}
Name            : Redmond 1
SuppressCallerId    :
AlternateCallerId   :
</pre>
Чтобы создать маршрут Redmond 2, введите:

```
New-CsOnlineVoiceRoute -Identity "Redmond 2" -NumberPattern "^\+1(425|206)
(\d{7})$" -OnlinePstnGatewayList sbc3.contoso.biz, sbc4.contoso.biz -Priority 2 -OnlinePstnUsages "US and Canada"
```

Чтобы создать маршрутом + 1, введите:

```
New-CsOnlineVoiceRoute -Identity "Other +1" -NumberPattern "^\+1(\d{10})$"
-OnlinePstnGatewayList sbc5.contoso.biz, sbc6.contoso.biz -OnlinePstnUsages "US and Canada"
```

  > [!CAUTION]
  > Убедитесь в том, что регулярное выражение в качестве атрибута переменной NumberPattern является допустимым выражением. Вы можете проверить ее с помощью этой веб-сайта:[https://www.regexpal.com](https://www.regexpal.com)

В некоторых случаях нет необходимости все вызовы направляются в одном SBC; Используйте - переменной NumberPattern «. *»

- Маршрутизировать вызовы все же SBC

    ```
    Set-CsOnlineVoiceRoute -id "Redmond 1" -NumberPattern ".*" 
     -OnlinePstnGatewayList sbc1.contoso.biz
    ```

Проверьте, что правильно настроены маршрут, выполнив `Get-CSOnlineVoiceRoute` команду Powershell с помощью параметров, как показано: 

```
Get-CsOnlineVoiceRoute | Where-Object {($_.priority -eq 1) -or ($_.priority -eq 2) or ($_.priority -eq 4) -Identity "Redmond 1" -NumberPattern "^\+1(425|206) (\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
```
Которого должен возвращать:
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

В примере, маршрут «Другие + 1» автоматически была назначена приоритет. 

**Шаг 3:** Создание политики маршрутизации голосовой связи «"мне НРАВИТСЯ" только» и добавить в политику работы с ТСОП «США и Канада.»

В сеанс PowerShell в Скайп для бизнеса в Интернет введите следующую команду:

```
New-CsOnlineVoiceRoutingPolicy "US Only" -OnlinePstnUsages "US and Canada"
```

В этом примере показан результат.

<pre>
Identity        : Tag:US only
OnlinePstnUsages    : {US and Canada}
Description         :
RouteType           : BYOT
</pre>

**Шаг 4:** Предоставление пользователю Спенс Low политику маршрутизации голосовой связи с помощью PowerShell.

- В сеанс Powershell в Скайп для бизнеса в Интернет введите следующую команду:

    ```Grant-CsOnlineVoiceRoutingPolicy -Identity "Spencer Low" -PolicyName "US Only"```

- Проверка назначения политики, введя следующую команду:

```
Get-CsOnlineUser "Spencer Low" | select OnlineVoiceRoutingPolicy
```
Которая возвращает:
<pre>
    OnlineVoiceRoutingPolicy
    ---------------------
    US Only
</pre>

#### <a name="creating-a-voice-routing-policy-with-several-pstn-usages"></a>Создание политики маршрутизации голосовой связи с несколькими случаев использования PSTN

Политику маршрутизации голосовой связи, созданную ранее допускает только вызовы на телефонные номера в США и Канада — Если не лицензии Майкрософт вызов планирование также назначается пользователю.

В этом примере создаются политики маршрутизации голосовой связи «Без ограничений». Политики повторно использует режим работы с ТСОП «"Мне Нравится" и Canada» создан в предыдущем примере, а также новые работы с ТСОП «International». 

Это направляет все вызовы для их изготовителей sbc2<span></span>. contoso.biz и sbc5<span></span>. contoso.biz. Представлены примеры назначить нет ограничения и политики "мне Нравится" только для пользователя «Иван низкий» пользователя «John Woods».

Spencer Low — допускается только в США и Канада числа звонков. При вызове диапазон номеров Redmond, необходимо использовать определенный набор SBC. Номера не в США не будут направляться, если вызов планирование лицензия назначена для пользователя.

Джон Вудз – звонки могут любое число. При вызове диапазон номеров Redmond, необходимо использовать определенный набор SBC. Не в США номера будут направляться через sbc2<span></span>. contoso.biz и sbc5<span></span>. contoso.biz.

![Отображает политику маршрутизации голосовой связи, назначенной пользователю Spencer Low](media/ConfigDirectRouting-VoiceRoutingPolicyAssignedtoSpencerLow.png)

Если пользователь имеет обе лицензии (Microsoft телефонной системой и вызов планирование Microsoft), для всех других вызовов используется автоматический маршрут. Если ничего не соответствует шаблоны номеров в созданное администратором online маршруты голосовой связи, маршрут с помощью вызова планирование Microsoft.

Если у пользователя есть только телефонной системой Microsoft, вызов отклоняется из-за соответствующие правила.

![Отображает политику маршрутизации голосовой связи, назначенные для пользователя John Woods](media/ConfigDirectRouting-VoiceRoutingPolicyAssignedtoJohnWoods.png)

В следующей таблице перечислены маршрутизации сообщений об использовании «Без ограничения» политики и маршруты голосовой связи. 

|**Использование ТСОП**|**Маршрут голосовых вызовов**|**Шаблон номеров**|**Приоритет**|**SBC**|**Описание**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|"Мне НРАВИТСЯ" только|«Redmond 1»|^\\+ 1 (425\|206)(\d{7})$|1|sbc1<span></span>. contoso.biz<br/>sbc2<span></span>. contoso.biz|Active маршрута для вызываемого номера +1 425 XXX XX XX или +1 206 XXX XX XX|
|"Мне НРАВИТСЯ" только|«Redmond 2»|^\\+ 1 (425\|206)(\d{7})$|2|sbc3<span></span>. contoso.biz<br/>sbc4<span></span>. contoso.biz|Резервного копирования маршрута для вызываемого номера +1 425 XXX XX XX или +1 206 XXX XX XX|
|"Мне НРАВИТСЯ" только|«Другие + 1»|^\\+ 1 (\d{10}) $|3|sbc5<span></span>. contoso.biz<br/>sbc6<span></span>. contoso.biz|Маршрут для вызываемого номера + 1 XXX XXX XX XX (за исключением +1 425 XXX XX XX или +1 206 XXX XX XX)|
|International|International|\d+|4|sbc2<span></span>. contoso.biz<br/>sbc5<span></span>. contoso.biz|Маршрут для любой шаблон номера |


  > [!NOTE]
  > - Порядок использования ТСОП в политики маршрутизации голосовой связи крайне важна. Примеры использования применяются в порядке, а если совпадение найдено при первом использовании, затем другие режимы работы с никогда не применяются. Режим работы с ТСОП «International» должны быть введены после работы с ТСОП «"мне НРАВИТСЯ" только.» Чтобы изменить порядок использования ТСОП, запустите `Set-CSOnlineRouteRoutingPolicy` команды. <br/>Например, чтобы изменить порядок «США и Канады» выполните первый и «Международный» секунды в порядке, обратном порядку:<br/>   `Set-CsOnlineVoiceRoutingPolicy -id tag:"no Restrictions" -OnlinePstnUsages @{Replace="International", "US and Canada"}`
 > - Автоматически назначаются приоритет маршруты голосовой связи «International» и «Другие + 1». Они не имеет значения, поскольку они имеют более низкими приоритетами чем «Redmond 1» и «Redmond 2».

#### <a name="example-of-voice-routing-policy-for-user-john-woods"></a>Пример политики маршрутизации голосовой связи для пользователя John Woods

Политики маршрутизации «Нет ограничений,» голосовой маршрут «International» голосовой связи действия по созданию работы с ТСОП «International», и назначение пользователя «John Woods» выглядят следующим образом.


1. Во-первых создайте работы с ТСОП «International». В удаленный сеанс PowerShell в Скайп для бизнеса в Интернет введите:

   ```
   Set-CsOnlinePstnUsage  -Identity Global -Usage @{Add="International"}
   ```

2. Создайте новый маршрут голосовой связи «International».

   ```
   New-CsOnlineVoiceRoute -Identity "International" -NumberPattern "\d+" -OnlinePstnGatewayList sbc2.contoso.biz, sbc5.contoso.biz -OnlinePstnUsages "International"
   ```
   Которая возвращает:

   <pre>
   Identity                  : International 
   Priority                      : 5
   Description                   : 
   NumberPattern                 : \d+
   OnlinePstnUsages          : {International}    
   OnlinePstnGatewayList           : {sbc2.contoso.biz, sbc5.contoso.biz}
   Name                            : International
   SupressCallerId           :
   AlternateCallerId         :
   </pre>
3. Создайте политику маршрутизации голосовой связи «Без ограничений». Режим работы с ТСОП «Redmond 1» и «Redmond» используются повторно в политике маршрутизации голосовой связи, чтобы сохранить специальная обработка звонков на номер «+1 425 XXX XX XX» и «+1 206 XXX XX XX» как на локальном или локальный.

```
New-CsOnlineVoiceRoutingPolicy "No Restrictions" -OnlinePstnUsages "US and Canada", ”International”
```

    Take note of the order of PSTN Usages:

    a. If a call made to number “+1425 XXX XX XX” with the usages configured as in the following example, the call follows the route set in “US and Canada” usage and the special routing logic is applied. That is, the call is routed using  sbc1<span></span>.contoso.biz and sbc2<span></span>.contoso.biz first, and then  sbc3<span></span>.contoso.biz and sbc4<span></span>.contoso.biz as the backup routes. 

    b.  If “International” PSTN usage is before “US and Canada,” calls to + 1425 XXX XX XX are routed to sbc2<span></span>.contoso.biz and sbc5<span></span>.contoso.biz as part of the routing logic. Enter the command:

    ```New-CsOnlineVoiceRoutingPolicy "No Restrictions" -OnlinePstnUsages "US and Canada", ”International”```

   Которая возвращает

  <pre>
   Identity     : International 
   OnlinePstnUsages     : {US and Canada, International}     
   Description      :  
   RouteType        : BYOT
  </pre>

4. Назначение политики маршрутизации голосовой связи для пользователя «John Woods» с помощью следующей команды.

   ```
   Grant-CsOnlineVoiceRoutingPolicy -Identity "John Woods" -PolicyName "No Restrictions”
   ```

   Затем проверьте назначения, с помощью команды:   

   ```
   Get-CsOnlineUser “John Woods” | Select OnlineVoiceRoutingPolicy
   ```
   Которая возвращает:

<pre>
    OnlineVoiceRoutingPolicy
    ------------------------
    No Restrictions
</pre>

Результатом будет неограниченный политика голосовой связи, применяются к вызовам, Джон Вудз и выполним логику маршрутизации вызовов для США, Канада и международных звонков.

## <a name="set-microsoft-teams-as-the-preferred-calling-client-for-users"></a>Установка группами Майкрософт по предпочитаемый вызывающего клиента для пользователей

Прямое маршрутизации только маршруты звонки в и из него пользователей при использовании команды клиента. Если ваша организация использует только группы, параметр «Только для команды» режим в политике обновления рекомендуется. Если ваша организация использует Скайп для Business Server или Скайп для бизнеса в Интернет, обратитесь к следующей статье для получения дополнительных сведений и выберите соответствующий параметр: [понять сосуществования и обновление пути для Скайп для бизнеса и рабочих групп](https://docs.microsoft.com/microsoftteams/migration-interop-guidance-for-teams-with-skype). 


## <a name="see-also"></a>См. также

[Планирование прямой маршрутизации](direct-routing-plan.md)
