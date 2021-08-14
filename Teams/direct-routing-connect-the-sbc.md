---
title: Подключение контроллер границы сеанса (SBC) к прямой маршрутике
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
description: Узнайте, как настроить SBC и подключить его к телефонная система прямой маршрутии.
ms.openlocfilehash: 46eabb56056526032d45669f0faf12fecf1762e10a1ee020dd9de9be17bff74e
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2021
ms.locfileid: "54327754"
---
# <a name="connect-your-session-border-controller-sbc-to-direct-routing"></a>Подключение контроллер границы сеанса (SBC) к прямой маршрутике

В этой статье описано, как настроить контроллер границы сеанса (SBC) и подключить его к телефонная система прямой маршрутии.  Это шаг 1 из следующих действий по настройке прямой маршрутии:

- **Шаг 1. Подключение SBC с помощью телефонная система проверки подключения** (эта статья)
- Шаг 2. [Включить для пользователей прямую маршрутику](direct-routing-enable-users.md)
- Шаг 3. [Настройка маршрутизов вызовов](direct-routing-voice-routing.md)
- Шаг 4. [Перевод чисел в альтернативный формат](direct-routing-translate-numbers.md)

Сведения о всех действиях, необходимых для настройки прямой маршрутии, см. в этой [ссылке.](direct-routing-configure.md)

Вы можете использовать Microsoft Teams [или](#using-the-microsoft-teams-admin-center) [PowerShell](#using-powershell) для настройки и подключения SBC к прямой маршрутике.

## <a name="using-the-microsoft-teams-admin-center"></a>С помощью Центра администрирования Microsoft Teams

1. В левой области навигации перейдите в **voice**  >  **Direct Routing** и щелкните **вкладку SBCs.**
2. Нажмите **Добавить**.
3. Введите FQDN для SBC. <br><br>Убедитесь, что доменное имя части FQDN совпадает с доменом, зарегистрированным в вашем клиенте, и помните, что доменное имя не поддерживается для доменного имени `*.onmicrosoft.com` FQDN SBC. Например, если у вас два доменных имена и `contoso.com` , используйте в качестве имени `contoso.onmicrosoft.com` `sbc.contoso.com` SBC. При использовании поддомена убедитесь, что этот поддомен также зарегистрирован в вашем клиенте. Например, если вы хотите использовать `sbc.service.contoso.com` , необходимо `service.contoso.com` зарегистрировать.
4. Настройте следующие параметры для SBC в соответствии с потребностями вашей организации. Подробные сведения о каждом из этих параметров см. в [параметрах SBC.](#sbc-settings)

    ![Снимок экрана: страница добавления SBC в Центре Microsoft Teams администрирования](media/direct-routing-add-sbc.png)

5. Закончив, нажмите кнопку **Сохранить**.

## <a name="using-powershell"></a>С помощью PowerShell

Чтобы подключить SBC к прямой маршрутике, необходимо:

1. [Подключение Skype для бизнеса Online с помощью PowerShell.](#connect-to-skype-for-business-online-by-using-powershell)
2. [Подключение SBC к клиенту.](#connect-the-sbc-to-the-tenant)
3. [Проверьте подключение SBC.](#verify-the-sbc-connection)

### <a name="connect-to-skype-for-business-online-by-using-powershell"></a>Подключение Skype для бизнеса Online с помощью PowerShell

С помощью сеанса PowerShell, подключенного к клиенту, можно связывать SBC с интерфейсом direct Routing. Чтобы открыть сеанс PowerShell, выполните действия, описанные в [Windows PowerShell.](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
 
После создания удаленного сеанса PowerShell проверьте, есть ли команды для управления SBC. Чтобы проверить команды, введите (или скопируйте и введите) следующую команду в сеансе PowerShell и нажмите ввод: 

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

### <a name="connect-the-sbc-to-the-tenant"></a>Подключение SBC для клиента

Чтобы подключить SBC к клиенту, используйте для подключения [SBC-CsOnlinePSTNGateway.](/powershell/module/skype/new-csonlinepstngateway) В сеансе PowerShell введите следующую кнопку и нажмите ввод:

```PowerShell
New-CsOnlinePSTNGateway -Fqdn <SBC FQDN> -SipSignalingPort <SBC SIP Port> -MaxConcurrentSessions <Max Concurrent Sessions the SBC can handle> -Enabled $true
```

  > [!NOTE]
  > 1. Мы рекомендуем установить максимальное число вызовов в SBC, используя сведения, которые можно найти в документации SBC. Ограничение будет вызывать уведомление, если SBC находится на уровне емкости.
  > 2. Вы можете подключить SBC только в том случае, если доменная часть FQDN совпадает с доменом, зарегистрированным в вашем клиенте, за исключением \* .onmicrosoft.com. Использование \* .onmicrosoft.com доменных имен не поддерживается для имени FQDN SBC. Например, если у вас два доменных имена: **contoso**.com и **contoso**.onmicrosoft.com, вы можете использовать sbc.contoso.com имя SBC. При попытке подключить SBC к имени, например sbc.contoso.abc, система не позволит вам, так как домен не принадлежит этому клиенту.<br/>
  > Помимо домена, зарегистрированного в вашем клиенте, важно, чтобы в нем был пользователь с назначенной лицензией E3 или E5. Если нет, вы получите следующую ошибку:<br/>
  `Can not use the "sbc.contoso.com" domain as it was not configured for this tenant`.

Ниже приводится пример.

```PowerShell
New-CsOnlinePSTNGateway -Identity sbc.contoso.com -Enabled $true -SipSignalingPort 5067 -MaxConcurrentSessions 100 
```

Возвращает:

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
> В этом примере показаны только минимальные необходимые параметры. В процессе подключения можно настроить дополнительные параметры, которые можно настроить с помощью [нового-CsOnlinePSTNGateway.](/powershell/module/skype/new-csonlinepstngateway) Дополнительные информацию см. в [параметрах SBC.](#sbc-settings)
 
### <a name="verify-the-sbc-connection"></a>Проверка подключения к SBC

Чтобы проверить подключение:

- [Проверьте, есть ли SBC в списке сопряженных SBCs.](#check-whether-the-sbc-is-on-the-list-of-paired-sbcs)
- [Проверка параметров SIP](#validate-sip-options).
 
#### <a name="check-whether-the-sbc-is-on-the-list-of-paired-sbcs"></a>Проверьте, есть ли SBC в списке сопряженных SBCs

После подключения SBC воспользуйтесь помощью [cmdlet Get-CsOnlinePSTNGateway,](/powershell/module/skype/get-csonlinepstngateway) чтобы убедиться, что он присутствует в списке подключенных SBCs. Введите следующую кнопку в удаленном сеансе PowerShell и нажмите ввод:

```PowerShell
Get-CsOnlinePSTNGateway -Identity sbc.contoso.com  
```

Парный шлюз должен появиться в списке, как показано в примере ниже, а параметр **Enabled** должен отображать значение **True**.

Возвращает:

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

Чтобы проверить сопряжение с помощью исходяющих параметров SIP, используйте интерфейс управления SBC и проверьте, что SBC получает 200 ответов "ОК" на исходяющие сообщения ПАРАМЕТРы.

Когда прямая маршрутная маршрутия видит параметры входящих сообщений, она начнет отправлять исходящую информацию о параметрах SIP в FQDN SBC, настроенное в поле Заглавный контакт в входящих параметрах сообщения. 

Чтобы проверить сопряжение с использованием входящих параметров SIP, используйте интерфейс управления SBC и посмотрите, что SBC отправляет ответ на сообщения ПАРАМЕТРы, отправляемые с прямой маршрутии, и что отправляемый им код ответа составляет 200 ОК.

## <a name="sbc-settings"></a>Параметры SBC

В этой таблице перечислены параметры, которые можно настроить для SBC в Центре администрирования Microsoft Teams и с помощью Microsoft Teams [New-CsOnlinePSTNGateway.](/powershell/module/skype/new-csonlinepstngateway)

|Обязательно?|Microsoft Teams центра администрирования|Параметр PowerShell|Описание|По умолчанию|Возможные значения|Тип и ограничения|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Да|**Добавление FQDN для SBC**|Полное доменное имя |Нет|Имя FQDN, ограничение 63 символов|Строка: см. список разрешенных и запрещенных символов в соглашениях об именовке в Active Directory для компьютеров, доменов, сайтов [и доменов](https://support.microsoft.com/help/909264)|
|Нет|**Включено**|Включено|Используется для того, чтобы включить SBC для исходящие звонки. Это можно использовать для временного удаления SBC из службы во время обновления или во время обслуживания. |False|Верно<br/>False|Boolean|
|Да|**Сигнальный порт SIP**|SipSignalingPort |Это порт прослушивания, используемый для связи с прямой маршрутикой с помощью протокола TLS.|Нет|Любой порт|От 0 до 65535 |
|Нет|**Отправка параметров SIP**|SendSIPOptions |Определяет, будет ли SBC отправлять сообщения параметров SIP. Настоятельно рекомендуем включить этот параметр. Если этот параметр отключен, SBC исключается из системы мониторинга и оповещения.|Верно|Верно<br/>False|Boolean|
|Нет|**Переадваровка истории вызовов**|ForwardCallHistory |Указывает на то, переад или нет, передается ли информация из истории вызовов через туловище. После этого прокси-сервер Microsoft 365 или Office 365 отправляет сведения об истории и заглавные данные, на которые они ссылались. |False|Верно<br/>False|Boolean|
|Нет|**Заглавная точка pai (Forward P-Наяговая удостоверение)**|ForwardPAI|Указывает на то, что заглавная информация о PAI переад пути к звонку. Заголовок PAI предоставляет способ проверки удостоверения абонемента. Если этот параметр заслан, также отправляется заглавная лента Privacy:ID.|False|Верно<br/>False|Boolean|
|Нет|**Пропускная способность одновременного звонка**|MaxConcurrentSessions |При этом система оповещений уведомляет вас о том, что количество сеансов одновременно на 90 процентов или больше, чем это значение. Если значение не за установлено, оповещения не создаются. Однако система мониторинга будет сообщать о количестве сеансов одновременно каждые 24 часа. |Null|Null<br/>От 1 до 100 000 ||
|Нет|**Коды ответов от сбойной передачи**|FailoverResponseCodes<br>|Если при прямой маршрутизации в ответ на исходяющие приглашения вы получаете код ошибки 4xx или 6xx SIP, вызов считается завершенным по умолчанию. Исходят означает звонок из клиента Teams в ПСПС с потоком трафика: клиент Teams -> Прямая маршрутия -> SBC -> телефонная сеть). При указании кода ответа на отбой при прямой маршрутике необходимо попробовать другой код SBC (если в политике голосовой маршрутировки пользователя существует другой SBC), если он получает указанные коды, если SBC не может позвонить из-за сетевых или других проблем. Дополнительные информацию см. в дополнительных данных, полученных с контроллера границы сеанса [(SBC).](direct-routing-trunk-failover-on-outbound-call.md)|408, 503, 504||Int|
|Нет|**Отбойное время (в секундах)**|FailoverTimeSeconds |При значении исходящие вызовы, которые не отвечают шлюзом в течение заданого времени, перенанаются на следующую доступную магистраль. Если дополнительных магистральных услуг нет, звонок будет автоматически сброшен. Значение по умолчанию — 10 секунд. В организации с медленной скоростью работы сетей и ответов шлюза это может привести к нежелательным звонкам.|10|Число|Int|
|Нет|**Предпочитаемая страна или регион для трафика мультимедиа**|MediaRelayRoutingLocationOverride |Используется для ручного управления трафиком мультимедиа в предпочитаемой стране или регионе. Мы рекомендуем устанавливать это значение только в том случае, если журналы звонка четко показывают, что назначение центра обработки данных по умолчанию для пути мультимедиа не использует путь, ближайший к центру обработки данных SBC. По умолчанию direct Routing назначает центр обработки данных на основе общего IP-адреса SBC и всегда выбирает путь, ближайший к центру обработки данных SBC. Однако в некоторых случаях путь по умолчанию может оказаться не оптимальным. Этот параметр позволяет вручную настроить предпочитаемый регион для трафика мультимедиа. |Нет|Коды стран в формате ISO||
|Нет|**SBC поддерживает PIDF/LO для экстренных звонков**|PidfloSupported|Укажите, поддерживает ли SBC объект расположения в формате сведений о присутствии (PIDF/LO) для экстренных вызовов.||||
|Нет| - |MediaBypass|Этот параметр указывает, поддерживает ли SBC обход мультимедиа и нужно ли использовать его для этого SBC. |Нет|Верно<br/>False|Boolean|

## <a name="see-also"></a>См. также

[Планирование прямой маршрутизации](direct-routing-plan.md)

[Настройка прямой маршрутизации](direct-routing-configure.md)

[Обзор PowerShell в Teams](teams-powershell-overview.md)