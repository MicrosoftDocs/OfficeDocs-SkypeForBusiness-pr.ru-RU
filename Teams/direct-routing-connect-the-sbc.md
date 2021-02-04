---
title: Подключение граничного контроллера сеанса (SBC) к прямой маршрутике
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
description: Узнайте, как настроить маршрутинг SBC и подключить его к прямой маршрутике телефонной системы.
ms.openlocfilehash: e20ab921e8f01d8beea15f0b1dd8a50e229f4e91
ms.sourcegitcommit: 5c33ca450a3215b9bf3c5da8bb3c9ef1a715a1a2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2021
ms.locfileid: "50099449"
---
# <a name="connect-your-session-border-controller-sbc-to-direct-routing"></a>Подключение граничного контроллера сеанса (SBC) к прямой маршрутике

В этой статье описано, как настроить пограничный контроллер сеанса (SBC) и подключить его к прямой маршрутике телефонной системы.  Это шаг 1 из следующих действий по настройке прямой маршрутинга:

- **Шаг 1. Подключение SBC к телефонной системе и проверка подключения** (в этой статье)
- Шаг 2. [Включить для пользователей прямую маршрутику](direct-routing-enable-users.md)
- Шаг 3. [Настройка маршрутинга вызовов](direct-routing-voice-routing.md)
- Шаг 4. [Перевод чисел в альтернативный формат](direct-routing-translate-numbers.md) 

Сведения о всех шагах, необходимых для настройки прямой маршрутинга, см. в сведениях о [настройке прямой маршрутинга.](direct-routing-configure.md)

Для настройки и подключения SBC к прямой маршрутике можно использовать Центр администрирования [Microsoft Teams](#using-the-microsoft-teams-admin-center) или [PowerShell.](#using-powershell)

## <a name="using-the-microsoft-teams-admin-center"></a>С помощью Центра администрирования Microsoft Teams

1. В области навигации слева перейдите к маршруту **Voice** Direct Routing и выберите вкладку  >   **"SBCs".**
2. Нажмите **Добавить**.
3. Введите FQDN для SBC. <br><br>Убедитесь, что часть доменного имени FQDN совпадает с доменом, зарегистрированным в вашем клиенте, и помните, что доменное имя не поддерживается для доменного имени `*.onmicrosoft.com` FQDN SBC. Например, если у вас два доменных имена и `contoso.com` они используются в качестве имени `contoso.onmicrosoft.com` `sbc.contoso.com` SBC. Если используется поддомен, убедитесь, что этот поддомен также зарегистрирован в вашем клиенте. Например, если вы хотите использовать `sbc.service.contoso.com` эту возможность, `service.contoso.com` ее нужно зарегистрировать.
4. Настройте следующие параметры для SBC в соответствии с потребностями вашей организации. Подробные сведения о каждом из этих параметров см. в [параметрах SBC.](#sbc-settings)

    ![Снимок экрана: страница добавления SBC в Центре администрирования Microsoft Teams](media/direct-routing-add-sbc.png)

5. Закончив, нажмите кнопку **Сохранить**.

## <a name="using-powershell"></a>С помощью PowerShell

Чтобы подключить SBC к прямой маршрутике, необходимо:

1. [Подключите Skype для бизнеса Online с помощью PowerShell.](#connect-to-skype-for-business-online-by-using-powershell)
2. [Подключите SBC к клиенту.](#connect-the-sbc-to-the-tenant)
3. [Проверьте подключение SBC.](#verify-the-sbc-connection)

### <a name="connect-to-skype-for-business-online-by-using-powershell"></a>Подключение к Skype для бизнеса Online с помощью PowerShell

Для связывания SBC с интерфейсом прямой маршрутинга можно использовать сеанс PowerShell, подключенный к клиенту. Чтобы открыть сеанс PowerShell, выполните действия, описанные в описании в этой [Windows PowerShell.](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
 
После создания удаленного сеанса PowerShell убедитесь, что вы видите команды для управления SBC. Чтобы проверить команды, введите (или скопируйте и введите и введите) следующую команду в сеансе PowerShell и нажмите ввод: 

```PowerShell
Get-Command *onlinePSTNGateway*
```

Эта команда возвращает четыре показанных здесь функции для управления SBC.

<pre>
CommandType    Name                       Version    Source 
-----------    ----                       -------    ------ 
Function       Get-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt 
Function       New-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt 
Function       Remove-CsOnlinePSTNGateway 1.0        tmp_v5fiu1no.wxt 
Function       Set-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt
</pre>

### <a name="connect-the-sbc-to-the-tenant"></a>Подключение SBC к клиенту

Используйте [cmdlet New-CsOnlinePSTNGateway,](https://docs.microsoft.com/powershell/module/skype/new-csonlinepstngateway) чтобы подключить SBC к клиенту. В сеансе PowerShell введите следующую кнопку и нажмите ввод:

```PowerShell
New-CsOnlinePSTNGateway -Fqdn <SBC FQDN> -SipSignalingPort <SBC SIP Port> -MaxConcurrentSessions <Max Concurrent Sessions the SBC can handle> -Enabled $true
```

  > [!NOTE]
  > 1. Рекомендуем установить максимальное число звонка в SBC, используя сведения, которые можно найти в документации SBC. Если SBC находится на уровне мощности, это ограничение будет вызывать уведомление.
  > 2. Вы можете подключить SBC только в том случае, если доменная часть его FQDN совпадает с одним из доменов, зарегистрированных в вашем клиенте, кроме \* .onmicrosoft.com. Использование доменных onmicrosoft.com .onmicrosoft.com не поддерживается для имени \* FQDN SBC. Например, если у вас два доменных имена: **contoso**.com и **contoso**.onmicrosoft.com, вы можете использовать sbc.contoso.con в качестве имени SBC. При попытке подключить SBC к имени, например sbc.contoso.abc, система не позволит вам, так как домен не принадлежит этому клиенту.<br/>
  > Помимо домена, зарегистрированного в клиенте, важно, чтобы с этим доменом был пользователь и назначенная лицензия E3 или E5. В этом случае вы получите следующее сообщение об ошибке:<br/>
  `Can not use the "sbc.contoso.com" domain as it was not configured for this tenant`.

Ниже приводится пример.

```PowerShell
New-CsOnlinePSTNGateway -Identity sbc.contoso.com -Enabled $true -SipSignalingPort 5067 -MaxConcurrentSessions 100 
```

Возвращаемая возвращаемая

<pre>
Identity              : sbc.contoso.com 
Fqdn                  : sbc.contoso.com 
SipSignalingPort     : 5067 
FailoverTimeSeconds   : 10 
ForwardCallHistory    : False 
ForwardPai            : False 
SendSipOptions        : True 
MaxConcurrentSessions : 100 
Enabled               : True   
</pre>

> [!NOTE]
> В этом примере показаны только минимальные необходимые параметры. Существуют дополнительные параметры, которые можно установить с помощью нового [csOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/new-csonlinepstngateway) в процессе подключения. Дополнительные информацию см. в [параметрах SBC.](#sbc-settings)
 
### <a name="verify-the-sbc-connection"></a>Проверка подключения к SBC

Чтобы проверить подключение:

- [Проверьте, есть ли SBC в списке парных SBCs.](#check-whether-the-sbc-is-on-the-list-of-paired-sbcs)
- [Проверка параметров SIP.](#validate-sip-options)
 
#### <a name="check-whether-the-sbc-is-on-the-list-of-paired-sbcs"></a>Проверьте, есть ли SBC в списке парных SBCs

После подключения SBC используйте [cmdlet Get-CsOnlinePSTNGateway,](https://docs.microsoft.com/powershell/module/skype/get-csonlinepstngateway) чтобы проверить, присутствует ли SBC в списке парных SBCs. Введите следующую кнопку в удаленном сеансе PowerShell и нажмите ввод:

```PowerShell
Get-CsOnlinePSTNGateway -Identity sbc.contoso.com  
```

Парный шлюз должен появиться в списке, как показано в примере ниже, а параметр **Enabled** должен иметь значение **True.**

Возвращаемая возвращаемая

<pre>
Identity              : sbc.contoso.com  
Fqdn                  : sbc.contoso.com
SipSignalingPort     : 5067
CodecPriority         : SILKWB,SILKNB,PCMU,PCMA
ExcludedCodecs        :  
FailoverTimeSeconds   : 10
ForwardCallHistory    : False
ForwardPai            : False
SendSipOptions        : True
MaxConcurrentSessions : 100
Enabled               : True
</pre>

#### <a name="validate-sip-options"></a>Проверка параметров SIP

Чтобы проверить сопряжение с использованием исходяющих параметров SIP, используйте интерфейс управления SBC и проверьте, получает ли SBC 200 ответов "ОК" на исходяющие параметры сообщений.

Когда direct Routing увидит параметры входящих параметров, он начнет отправлять исходяющие сообщения параметров SIP в FQDN SBC, настроенное в поле "Замещение контакта" в входящих параметрах сообщения. 

Чтобы проверить сопряжение с использованием входящих параметров SIP, используйте интерфейс управления SBC и посмотрите, что SBC отправляет ответ на сообщения OPTIONS, отправляемые с прямой маршрутации, и что отправляемый им код ответа составляет 200.

## <a name="sbc-settings"></a>Параметры SBC

В этой таблице перечислены параметры, которые можно установить для SBC в Центре администрирования Microsoft Teams и с помощью командлета [New-CsOnlinePSTNGateway.](https://docs.microsoft.com/powershell/module/skype/new-csonlinepstngateway)

|Обязательно?|Параметр Центра администрирования Microsoft Teams|Параметр PowerShell|Описание|По умолчанию|Возможные значения|Тип и ограничения|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Да|**Добавление FQDN для SBC**|Полное доменное имя |Нет|Имя FQDN, ограничение 63 символов|Строка. См. список разрешенных и запрещенных символов в соглашениях об именовке в Active Directory для компьютеров, доменов, сайтов [и доменов](https://support.microsoft.com/help/909264)|
|Нет|**Включено**|Включено|Используется для включаемой SBC для исходящие вызовы. Это можно сделать, чтобы временно удалить SBC из службы во время обновления или во время обслуживания. |False|Верно<br/>False|Boolean|
|Да|**Сигнальный порт SIP**|SipSignalingPort |Это порт прослушивания, используемый для связи с прямой маршрутией с помощью протокола TLS.|Нет|Любой порт|От 0 до 65535 |
|Нет|**Параметры отправки SIP**|SendSIPOptions |Определяет, будет ли SBC отправлять сообщения параметров SIP. Настоятельно рекомендуем включить этот параметр. Если этот параметр отключен, SBC исключается из системы мониторинга и оповещения.|Верно|Верно<br/>False|Boolean|
|Нет|**Forward call history**|ForwardCallHistory |Указывает на то, переададуются ли данные истории вызовов через магистраль. Если этот включить, прокси-сервер Microsoft 365 или Office 365 будет отправлять данные истории с заглавным названием. |False|Верно<br/>False|Boolean|
|Нет|**Forward P-Asserted-identity (PAI) header**|ForwardPAI|Указывает на то, что заглавная информация о PAI перенаададовылась вместе с вызовом. Заголовок PAI предоставляет способ проверки удостоверения абонемента. Если этот параметр заданной настройки, также отправляется заглавный параметр Privacy:ID.|False|Верно<br/>False|Boolean|
|Нет|**Пропускная способность для одновременного вызова**|MaxConcurrentSessions |При этом система оповещений будет уведомлять вас о том, что число сеансов одновременно на 90 процентов или больше этого значения. Если значение не за установлено, оповещения не создаются. Однако система мониторинга сообщает о количестве сеансов, которые одновременно должны быть сеансы каждые 24 часа. |Null|Null<br/>От 1 до 100 000 ||
|Нет|**Коды отбойных ответов**|FailoverResponseCodes<br>|Если при прямой маршрутизаке в ответ на исходяовое приглашение принимается код ошибки 4xx или 6xx SIP, вызов считается завершенным по умолчанию. Исходятая означает звонок из клиента Teams в ДНР с потоком трафика: клиент Teams -> Прямая маршрутка -> SBC -> телефонная сеть). При указании кода отозвать отбой, при прямой маршрутировки необходимо попробовать другой код SBC (если в политике голосовой маршрутики пользователя существует другая кодировки голосовой связи) при его приеме указанных кодов, если SBC не может позвонить из-за проблем с сетью или другими вопросами. Дополнительные информацию см. в ответе на [конкретные коды SIP,](direct-routing-trunk-failover-on-outbound-call.md)полученные с контроллера границы сеанса.|408, 503, 504||Int|
|Нет|**Время отбойного времени (в секундах)**|FailoverTimeSeconds |При значении исходящие вызовы, которые не будут отвечать шлюзом в течение заданого времени, будут перенаться на следующую доступную магистраль. Если дополнительные магистрали не забронируются, звонок автоматически переключяется. Значение по умолчанию — 10 секунд. В организации с медленным доступом к сетям и шлюзам это может привести к нежелательным звонкам.|10|Число|Int|
|Нет|**Предпочитаемая страна или регион для трафика мультимедиа**|MediaRelayRoutingLocationOverride |Используется для ручного перенастройки предпочитаемой страны или региона для трафика мультимедиа. Это рекомендуется устанавливать только в том случае, если журналы звонка четко показывают, что по умолчанию центр обработки данных для пути мультимедиа не использует путь, ближайший к центру обработки данных SBC. По умолчанию direct Routing назначает центр обработки данных на основе общего IP-адреса SBC и всегда выбирает путь, ближайший к центру обработки данных SBC. Однако в некоторых случаях путь по умолчанию может быть не оптимальным. Этот параметр позволяет вручную настроить предпочитаемый регион для трафика мультимедиа. |Нет|Коды стран в формате ISO||
|Нет|**SBC поддерживает PIDF/LO для экстренных вызовов**|PidfloSupported|Укажите, поддерживает ли SBC объект сведений о присутствии для экстренных вызовов.||||
|Нет|**Звонок на телефон при попытке найти пользователя**|GenerateRingingWhileLocatingUser|Указать, что для вызываемого звонка должен быть установлен звуковой сигнал, чтобы указать, что Teams находится в процессе установления звонка. Этот параметр применяется только к прямой маршрутии в режиме обхода мультимедиа. Иногда входящие звонки из STN в клиенты Teams могут занять больше времени, чем ожидалось. В этом случае звонок может ничего не слышать, клиент Teams не звонит, а звонок может быть отменен некоторыми поставщиками телекоммуникаций. Этот параметр помогает избежать непредвиденных тишин, которые могут возникать в этих сценариях.|Верно|Верно<br/>False|Boolean|
|Нет| - |MediaBypass|Этот параметр указывает, поддерживает ли SBC обход мультимедиа и нужно ли использовать его для этого SBC. |Нет|Верно<br/>False|Boolean|

## <a name="see-also"></a>См. также

[Планирование прямой маршрутизации](direct-routing-plan.md)

[Настройка прямой маршрутизации](direct-routing-configure.md)

[Обзор PowerShell в Teams](teams-powershell-overview.md)
