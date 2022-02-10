---
title: Подключение контроллер границы сеанса (SBC) к прямой маршрутике
ms.reviewer: fillipse
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
description: Узнайте, как настроить SBC и подключить его к Teams телефонная система прямой маршрутии.
ms.openlocfilehash: 7983fa176fec5e4921db169e1e92a6f6ebc2f2a7
ms.sourcegitcommit: 5e9b50cd1b513f06734be6c024ac06d293b27089
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/10/2022
ms.locfileid: "62518721"
---
# <a name="connect-your-session-border-controller-sbc-to-direct-routing"></a>Подключение контроллер границы сеанса (SBC) к прямой маршрутике

В этой статье описано, как настроить контроллер границы сеанса (SBC) и подключить его к прямой маршрутике.  Это шаг 1 из следующих действий по настройке прямой маршрутии:

- **Шаг 1. Подключение SBC с телефонная система и проверьте подключение** (эта статья)
- Шаг 2. [Включить для пользователей прямую маршрутику](direct-routing-enable-users.md)
- Шаг 3. [Настройка маршрутизов  вызовов](direct-routing-voice-routing.md)
- Шаг 4. [Перевод чисел в альтернативный формат](direct-routing-translate-numbers.md)

Сведения о всех действиях, необходимых для настройки прямой маршрутии, см. в этой [ссылке](direct-routing-configure.md).

Вы можете использовать Microsoft Teams [или](#using-the-microsoft-teams-admin-center) [PowerShell](#using-powershell) для настройки и подключения SBC к прямой маршрутике.

## <a name="using-the-microsoft-teams-admin-center"></a>С помощью Центра администрирования Microsoft Teams

1. В области навигации слева перейдите в **voiceDirect** >  Routing и щелкните **вкладку SBCs**.

2. Нажмите **Добавить**.

3. Введите FQDN для SBC. <br><br>Убедитесь, что доменное имя части FQDN `*.onmicrosoft.com` совпадает с доменом, зарегистрированным в вашем клиенте, и помните, что доменное имя не поддерживается для доменного имени FQDN SBC. Например, если у вас два доменных имена и `contoso.com` `contoso.onmicrosoft.com`, используйте `sbc.contoso.com` в качестве имени SBC. При использовании поддомена убедитесь, что этот поддомен также зарегистрирован в вашем клиенте. Например, если вы хотите использовать `sbc.service.contoso.com`, необходимо `service.contoso.com` зарегистрировать.

4. Настройте следующие параметры для SBC в соответствии с потребностями вашей организации. Подробные сведения о каждом из этих параметров см. в [параметрах SBC](#sbc-settings).

    ![Снимок экрана: страница добавления SBC в центре Microsoft Teams администрирования.](media/direct-routing-add-sbc.png)

5. Закончив, нажмите кнопку **Сохранить**.

## <a name="using-powershell"></a>С помощью PowerShell

Чтобы подключить SBC к прямой маршрутике, необходимо:

1. [Подключение Skype для бизнеса Online с помощью PowerShell](#connect-to-skype-for-business-online-by-using-powershell).

2. [Подключение SBC для клиента](#connect-the-sbc-to-the-tenant).

3. [Проверьте подключение SBC](#verify-the-sbc-connection).

### <a name="connect-to-skype-for-business-online-by-using-powershell"></a>Подключение Skype для бизнеса Online с помощью PowerShell

Для связывания SBC с интерфейсом Direct Routing используйте сеанс PowerShell, подключенный к клиенту. Чтобы открыть сеанс PowerShell, выполните действия, описанные в [Windows PowerShell.](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
 
После создания удаленного сеанса PowerShell убедитесь, что вы видите команды для управления SBC. Чтобы проверить команды, введите (или скопируйте и введите) следующую команду в сеансе PowerShell и нажмите ввод: 

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

Чтобы подключить SBC к клиенту, воспользуйтесь для этого [cmdlet New-CsOnlinePSTNGateway](/powershell/module/skype/new-csonlinepstngateway) . В сеансе PowerShell введите следующую кнопку и нажмите ввод:

```PowerShell
New-CsOnlinePSTNGateway -Fqdn <SBC FQDN> -SipSignalingPort <SBC SIP Port> -MaxConcurrentSessions <Max Concurrent Sessions the SBC can handle> -Enabled $true
```

  > [!NOTE]
  > 1. Мы рекомендуем установить максимальное число вызовов в SBC, используя сведения, которые можно найти в документации SBC. Ограничение будет вызывать уведомление, если SBC находится на уровне емкости.
  > 2. Вы можете подключить SBC только в том случае, если доменная часть FQDN совпадает с доменом, зарегистрированным в вашем клиенте, \*за исключением .onmicrosoft.com. Использование \*.onmicrosoft.com доменных имен не поддерживается для имени FQDN SBC. Например, если у вас два доменных имена: **contoso.com** и **contoso.onmicrosoft.com**, вы можете использовать sbc.contoso.com имя SBC. При попытке подключить SBC к имени, например sbc.contoso.abc, система не позволит вам, так как домен не принадлежит этому клиенту.<br/>
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
> В этом примере показаны только минимальные необходимые параметры. В процессе подключения можно настроить дополнительные параметры, которые можно настроить с помощью [нового-CsOnlinePSTNGateway](/powershell/module/skype/new-csonlinepstngateway) . Дополнительные информацию см. в [параметрах SBC](#sbc-settings).
 
### <a name="verify-the-sbc-connection"></a>Проверка подключения к SBC

Чтобы проверить подключение:

- [Проверьте, есть ли SBC в списке сопряженных SBCs](#check-whether-the-sbc-is-on-the-list-of-paired-sbcs).
- [Проверка параметров SIP](#validate-sip-options).
 
#### <a name="check-whether-the-sbc-is-on-the-list-of-paired-sbcs"></a>Проверка того, есть ли SBC в списке сопряженных SBCs

После подключения SBC воспользуйтесь помощью [cmdlet Get-CsOnlinePSTNGateway](/powershell/module/skype/get-csonlinepstngateway) , чтобы убедиться, что он присутствует в списке подключенных SBCs. Введите следующую кнопку в удаленном сеансе PowerShell и нажмите ввод:

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

Когда прямая маршрутная маршрутия видит параметры входящих сообщений, она начнет отправлять исходящую информацию о параметрах SIP в FQDN SBC, настроенное в поле Заглавный контакт в сообщении Параметры входящих параметров. 

Чтобы проверить сопряжение с использованием входящих параметров SIP, используйте интерфейс управления SBC и посмотрите, что SBC отправляет ответ на сообщения ПАРАМЕТРы, отправляемые с прямой маршрутии, и что отправляемый им код ответа составляет 200 ОК.

## <a name="sbc-settings"></a>Параметры SBC

В этой таблице перечислены параметры, которые можно настроить для SBC в Центре администрирования Microsoft Teams и с помощью Microsoft Teams [New-CsOnlinePSTNGateway](/powershell/module/skype/new-csonlinepstngateway).

|Обязательно?|Teams центра администрирования|Параметр PowerShell|Описание|По умолчанию|Возможные значения|Тип и ограничения|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Да|**Добавление FQDN для SBC**|Полное доменное имя |Нет|Имя FQDN, ограничение 63 символов|Строка: см. список разрешенных и запрещенных символов в соглашениях об именовке в Active Directory для компьютеров, доменов [, сайтов и доменов](https://support.microsoft.com/help/909264)|
|Нет|**Включено**|Включено|Используется для того, чтобы включить SBC для исходящие звонки. Это можно использовать для временного удаления SBC из службы во время обновления или во время обслуживания. |False|Верно<br/>False|Boolean|
|Да|**Сигнальный порт SIP**|SipSignalingPort |Это порт прослушивания, используемый для связи с прямой маршрутикой с помощью протокола TLS.|Нет|Любой порт|От 0 до 65535 |
|Нет|**Отправка параметров SIP**|SendSIPOptions |Определяет, будет ли SBC отправлять сообщения параметров SIP. Настоятельно рекомендуем включить этот параметр. Если этот параметр отключен, SBC исключается из системы мониторинга и оповещения.|Верно|Верно<br/>False|Boolean|
|Нет|**Переадваровка истории  вызовов**|ForwardCallHistory |Указывает на то, переад или нет, передается ли информация из истории  вызовов через туловище. Когда вы включит этот Microsoft 365, прокси-сервер отправит сведения об истории и заглавные данные, на которые они ссылались. |False|Верно<br/>False|Boolean|
|Нет|**Заглавная**|ForwardPAI|Указывает на то, будет ли переадваровка загона PAI вместе с звоним. Заголовок PAI предоставляет способ проверки удостоверения абонемента. Если этот параметр засвеен, также отправляется заглавный заглавный сайт Privacy:ID.|False|Верно<br/>False|Boolean|
|Нет|**Пропускная способность для одновременного вызова**|MaxConcurrentSessions |При этом система оповещений уведомляет вас о том, что количество сеансов одновременно на 90 процентов или больше, чем это значение. Если значение не за установлено, оповещения не создаются. Однако система мониторинга будет сообщать о количестве сеансов одновременно каждые 24 часа. |Null|Null<br/>От 1 до 100 000 ||
|Нет|**Коды ответов от сбойной передачи**|FailoverResponseCodes<br>|Если direct Routing получает код ошибки 4xx или 6xx SIP в ответ на исходякое приглашение, звонок считается завершенным по умолчанию. Исходят — это звонок от клиента Teams к STN с потоком трафика: клиент Teams -> Прямая маршрутия -> SBC -> телефонная сеть). При указании кода ответа на отбой при прямой маршрутике необходимо попробовать другой код SBC (если в политике голосовой маршрутировки пользователя существует другой SBC), если он получает указанные коды, если SBC не может позвонить из-за сетевых или других проблем. Дополнительные информацию см. в дополнительных данных, полученных с контроллера границы сеанса [(SBC).](direct-routing-trunk-failover-on-outbound-call.md)|408, 503, 504||Int|
|Нет|**Отбойное время (в секундах)**|FailoverTimeSeconds |При значении исходящие вызовы, которые не отвечают шлюзом в течение заданого времени, перенанаются на следующую доступную магистраль. Если дополнительных магистральных услуг нет, звонок будет автоматически сброшен. Значение по умолчанию — 10 секунд. В организации с медленной скоростью работы сетей и ответов шлюза это может привести к нежелательным звонкам.|10|Число|Int|
|Нет|**Предпочитаемая страна или регион для трафика мультимедиа**|MediaRelayRoutingLocationOverride | Не относится к прямой маршрутике. Этот параметр предназначен только для управляемых операторов связи в планах звонков. |Нет|||
|Нет|**SBC поддерживает PIDF/LO для экстренных звонков**|PidfloSupported|Укажите, поддерживает ли SBC объект расположения в формате сведений о присутствии (PIDF/LO) для экстренных вызовов.||||
|Нет| - |MediaBypass|Этот параметр указывает, поддерживает ли SBC обход мультимедиа и нужно ли использовать его для этого SBC. |Нет|Верно<br/>False|Boolean|

## <a name="see-also"></a>См. также

[Планирование прямой маршрутизации](direct-routing-plan.md)

[Настройка прямой маршрутизации](direct-routing-configure.md)

[Обзор PowerShell в Teams](teams-powershell-overview.md)
