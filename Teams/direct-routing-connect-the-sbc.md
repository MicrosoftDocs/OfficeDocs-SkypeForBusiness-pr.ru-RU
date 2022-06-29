---
title: Подключение пограничного контроллера сеанса (SBC) к прямой маршрутизации
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
description: Узнайте, как настроить и подключить SBC к прямой маршрутизации телефонной системы Teams.
ms.openlocfilehash: e33f9538fdf69696e0a87da84dc5aec8e8d304af
ms.sourcegitcommit: f2253162a23d0683e7424211da1a0a8760c8a91b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/29/2022
ms.locfileid: "66241108"
---
# <a name="connect-your-session-border-controller-sbc-to-direct-routing"></a>Подключение пограничного контроллера сеанса (SBC) к прямой маршрутизации

В этой статье описывается, как настроить пограничный контроллер сеансов (SBC) и подключить его к прямой маршрутизации.  Это шаг 1 из следующих шагов по настройке прямой маршрутизации:

- **Шаг 1. Подключение SBC к телефонной системе и проверка подключения** (в этой статье)
- Шаг 2. [Включение прямой маршрутизации для пользователей](direct-routing-enable-users.md)
- Шаг 3. [Настройка маршрутизации вызовов](direct-routing-voice-routing.md)
- Шаг 4. [Перевод чисел в альтернативный формат](direct-routing-translate-numbers.md)

Сведения о всех шагах, необходимых для настройки прямой маршрутизации, см. в разделе ["Настройка прямой маршрутизации"](direct-routing-configure.md).

Центр администрирования [Microsoft Teams](#using-the-microsoft-teams-admin-center) или [PowerShell](#using-powershell) можно использовать для настройки и подключения SBC к прямой маршрутизации.

## <a name="using-the-microsoft-teams-admin-center"></a>С помощью Центра администрирования Microsoft Teams

1. В области навигации слева перейдите к **маршрутизации Voice** > **Direct** и перейдите на **вкладку SBCs** .

2. Нажмите **Добавить**.

3. Введите полное доменное имя для SBC. <br><br>Убедитесь `*.onmicrosoft.com` , что часть полного доменного имени домена совпадает с доменом, зарегистрированным в клиенте, и помните, что доменное имя не поддерживается для доменного имени FQDN SBC. Например, если у вас есть два доменных имени и `contoso.com` `contoso.onmicrosoft.com`используется в `sbc.contoso.com` качестве имени SBC. При использовании поддомена убедитесь, что этот поддомен также зарегистрирован в клиенте. Например, если вы хотите использовать `sbc.service.contoso.com`, необходимо `service.contoso.com` зарегистрировать его.

4. Настройте следующие параметры для SBC в зависимости от потребностей вашей организации. Дополнительные сведения о каждом из этих параметров см. в разделе [параметров SBC](#sbc-settings).

    ![Снимок экрана: страница добавления SBC в Центре администрирования Microsoft Teams.](media/direct-routing-add-sbc.png)

5. Закончив, нажмите кнопку **Сохранить**.

## <a name="using-powershell"></a>С помощью PowerShell

Чтобы подключить SBC к прямой маршрутизации, вам потребуется:

1. [Подключитесь к Skype для бизнеса Online с помощью PowerShell](#connect-to-skype-for-business-online-by-using-powershell).

2. [Подключите SBC к клиенту](#connect-the-sbc-to-the-tenant).

3. [Проверьте подключение SBC](#verify-the-sbc-connection).

### <a name="connect-to-skype-for-business-online-by-using-powershell"></a>Подключение к Skype для бизнеса Online с помощью PowerShell

Чтобы связать SBC с интерфейсом прямой маршрутизации, используйте сеанс PowerShell, подключенный к клиенту. Чтобы открыть сеанс PowerShell, выполните действия, описанные в разделе "[Настройка компьютера для Windows PowerShell"](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).
 
После установки удаленного сеанса PowerShell убедитесь, что вы видите команды для управления SBC. Чтобы проверить команды, введите или скопируйте и вставьте следующую команду в сеансе PowerShell, а затем нажмите клавишу ВВОД: 

```PowerShell
Get-Command *onlinePSTNGateway*
```

Команда возвращает четыре приведенные здесь функции, которые позволяют управлять SBC.

<pre>
CommandType    Name                       Version    Source 
-----------    ----                       -------    ------ 
Function       Get-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt 
Function       New-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt 
Function       Remove-CsOnlinePSTNGateway 1.0        tmp_v5fiu1no.wxt 
Function       Set-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt
</pre>

### <a name="connect-the-sbc-to-the-tenant"></a>Подключение SBC к клиенту

Чтобы подключить SBC к клиенту, используйте командлет [New-CsOnlinePSTNGateway](/powershell/module/skype/new-csonlinepstngateway) . В сеансе PowerShell введите следующую команду и нажмите клавишу ВВОД:

```PowerShell
New-CsOnlinePSTNGateway -Fqdn <SBC FQDN> -SipSignalingPort <SBC SIP Port> -MaxConcurrentSessions <Max Concurrent Sessions the SBC can handle> -Enabled $true
```

  > [!NOTE]
  > 1. Мы рекомендуем установить максимальное ограничение вызовов в SBC, используя сведения, которые можно найти в документации по SBC. Ограничение активирует уведомление, если SBC находится на уровне емкости.
  > 2. SBC можно подключить только в том случае, если доменная часть полного доменного имени соответствует одному из доменов, зарегистрированных в клиенте, \*за исключением .onmicrosoft.com. Использование \*.onmicrosoft.com доменных имен не поддерживается для полного доменного имени SBC. Например, если у вас есть два доменных имени, **contoso.com** и **contoso.onmicrosoft.com**, можно использовать sbc.contoso.com для имени SBC. При попытке подключить SBC с именем, например sbc.contoso.abc, система не позволит вам, так как домен не принадлежит этому клиенту.<br/>
  > Помимо домена, зарегистрированного в клиенте, важно иметь пользователя с этим доменом и назначенную лицензию E3 или E5. В противном случае вы получите следующую ошибку:<br/>
  `Can not use the "sbc.contoso.com" domain as it was not configured for this tenant`.
  > 3. Несколько IP-адресов, сопоставленных с одним и тем же FQDN на стороне SBC, не поддерживаются.

Ниже приводится пример.

```PowerShell
New-CsOnlinePSTNGateway -Identity sbc.contoso.com -Enabled $true -SipSignalingPort 5067 -MaxConcurrentSessions 100 
```

Возвращает следующее:

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
> В этом примере показаны только минимальные обязательные параметры. Существуют дополнительные параметры, которые можно задать с помощью командлета [New-CsOnlinePSTNGateway](/powershell/module/skype/new-csonlinepstngateway) в процессе подключения. Дополнительные сведения см. в разделе [параметров SBC](#sbc-settings).
 
### <a name="verify-the-sbc-connection"></a>Проверка подключения SBC

Чтобы проверить подключение, выполните указанные ниже действия.

- [Проверьте, включен ли SBC в список связанных контроллеров SBC](#check-whether-the-sbc-is-on-the-list-of-paired-sbcs).
- [Проверка параметров SIP](#validate-sip-options).
 
#### <a name="check-whether-the-sbc-is-on-the-list-of-paired-sbcs"></a>Проверьте, включен ли SBC в список связанных контроллеров SBC.

После подключения SBC используйте командлет [Get-CsOnlinePSTNGateway](/powershell/module/skype/get-csonlinepstngateway) , чтобы убедиться, что SBC присутствует в списке парных SBC. Введите следующую команду в удаленном сеансе PowerShell и нажмите клавишу ВВОД:

```PowerShell
Get-CsOnlinePSTNGateway -Identity sbc.contoso.com  
```

Парный шлюз должен появиться в списке, как показано в примере ниже, а параметр **Enabled** должен отображать значение **True**.

Возвращает следующее:

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

Чтобы проверить связывание с помощью исходящих параметров SIP, используйте интерфейс управления SBC и убедитесь, что SBC получает 200 ответов OK на исходящие сообщения OPTIONS.

Когда прямая маршрутизация видит входящие параметры, она начнет отправлять исходящие сообщения параметров SIP в полное доменное имя SBC, настроенное в поле "Контакт" в входящем сообщении OPTIONS. 

Чтобы проверить связывание с помощью входящих параметров SIP, используйте интерфейс управления SBC и убедитесь, что SBC отправляет ответ на сообщения OPTIONS, поступающие из прямой маршрутизации, и что отправляемый код ответа имеет значение 200 OK.

## <a name="sbc-settings"></a>Параметры SBC

В этой таблице перечислены параметры, которые можно задать для SBC в Центре администрирования Microsoft Teams и с помощью [командлета New-CsOnlinePSTNGateway](/powershell/module/skype/new-csonlinepstngateway) .

|Обязательно?|Параметр Центра администрирования Teams|Параметр PowerShell|Описание|По умолчанию|Возможные значения|Тип и ограничения|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Да|**Добавление полного доменного имени для SBC**|Полное доменное имя |Нет|Полное доменное имя, ограничение в 63 символа|Строка, см. список разрешенных и запрещенных символов в соглашениях об именовании в Active Directory для компьютеров, доменов [, сайтов и подразделений](https://support.microsoft.com/help/909264)|
|Нет|**Включено**|Включено|Используется для включения SBC для исходящих вызовов. Его можно использовать для временного удаления SBC из службы во время обновления или во время обслуживания. |False|Верно<br/>False|Boolean|
|Да|**Порт сигналов SIP**|SipSignalingPort |Это порт прослушивания, используемый для обмена данными с прямой маршрутиза службой с помощью протокола TLS.|Нет|Любой порт|От 0 до 65535 |
|Нет|**Отправка параметров SIP**|SendSIPOptions |Определяет, будет ли SBC отправлять сообщения параметров SIP. Настоятельно рекомендуется включить этот параметр. Если этот параметр отключен, SBC исключается из системы мониторинга и оповещений.|Верно|Верно<br/>False|Boolean|
|Нет|**Журнал переадресации звонков**|ForwardCallHistory |Указывает, пересылаются ли данные журнала вызовов по магистрали. При включении этого параметра прокси-сервер Microsoft 365 отправляет данные журнала и заголовок Referred-by. |False|Верно<br/>False|Boolean|
|Нет|**Переадресация заголовка P-Asserted-identity (PAI)**|ForwardPAI|Указывает, перенаправлять ли заголовок PAI вместе с вызовом. Заголовок PAI предоставляет способ проверки удостоверения абонемента. Если этот параметр включен, также отправляется заголовок Privacy:ID.|False|Верно<br/>False|Boolean|
|Нет|**Емкость параллельных вызовов**|MaxConcurrentSessions |При установке значения система оповещений уведомляет вас о том, что количество одновременных сеансов равно 90 % или выше этого значения. Если значение не задано, оповещения не создаются. Однако система мониторинга будет сообщать о количестве одновременных сеансов каждые 24 часа. |Null|Null<br/>От 1 до 100 000 ||
|Нет|**Коды ответов отработки отказа**|FailoverResponseCodes<br>|Если прямая маршрутизация получает код ошибки SIP 4xx или 6xx в ответ на исходящее приглашение, вызов считается завершенным по умолчанию. Исходящий трафик означает вызов клиента Teams к ТСОП с потоком трафика: клиент Teams -> Прямая маршрутизация -> SBC -> телефонной сети). При указании кода ответа на отработку отказа при прямой маршрутизации необходимо попробовать другой SBC (если в политике маршрутизации голосовой связи пользователя существует другой SBC), если он получает указанные коды, если SBC не может выполнить вызов из-за сетевых или других проблем. Дополнительные сведения см. в статье об отработке отказа определенных кодов SIP, полученных от пограничного [контроллера сеансов (SBC).](direct-routing-trunk-failover-on-outbound-call.md)|408, 503, 504||Int|
|Нет|**Время отработки отказа (в секундах)**|FailoverTimeSeconds |При установке значения исходящие вызовы, на которые шлюз не отвечает в течение заданного времени, направляются в следующую доступную магистраль. Если дополнительные магистрали отсутствуют, вызов автоматически удаляется. Значение по умолчанию — 10 секунд. В организации с медленными сетями и ответами шлюза это может привести к излишнему удалению вызовов.|10|Число|Int|
|Нет|**Предпочитаемая страна или регион для трафика мультимедиа**|MediaRelayRoutingLocationOverride | Неприменимо к прямой маршрутизации. Этот параметр зарезервирован для использования с управляемыми операторами в тарифных планах |Нет|||
|Нет|**SBC поддерживает piDF/LO для экстренных вызовов**|PidfloSupported|Укажите, поддерживает ли SBC объект расположения формата данных сведений о присутствии (PIDF/LO) для экстренных вызовов.||||
|Нет| - |MediaBypass|Этот параметр указывает, поддерживает ли SBC обход сервера-посредника и нужно ли использовать его для этого SBC. |Нет|Верно<br/>False|Boolean|

## <a name="see-also"></a>См. также

[Планирование прямой маршрутизации](direct-routing-plan.md)

[Настройка прямой маршрутизации](direct-routing-configure.md)

[Обзор PowerShell в Teams](teams-powershell-overview.md)
