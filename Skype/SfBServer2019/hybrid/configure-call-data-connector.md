---
title: Настройка подключения к данным звонка
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: Инструкции по настройке вызова подключения к данным, что позволяет телеметрии из Скайп for Business локально, чтобы просмотреть с помощью Скайп для бизнеса в Интернет средства.
ms.openlocfilehash: adc1c9a1e50130796c4749a958e9030c10a09fd0
ms.sourcegitcommit: 1cb5a3570032250aecd5a1a839cbbe4daeb77f2c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/13/2018
ms.locfileid: "26293618"
---
# <a name="configure-call-data-connector"></a>Настройка подключения к данным звонка

В этой статье описывается настройка вызова подключения к данным — один набор инструментов, который позволяет просматривать Скайп для бизнес-Server вызов качества данных с помощью Скайп средства Business Online вызов качества панели мониторинга (CQD) и вызвать аналитики (ЦС). 

> [!NOTE]
> В выпуске ознакомительной версии доступна только вызова Analytics панели мониторинга.

Дополнительные сведения о преимуществах вызова подключения к данным и необходимые условия, например требования к роли и настройке гибридного подключения можно [Планирование вызова подключения к данным](plan-call-data-connector.md).

## <a name="enable-monitoring"></a>Разрешить мониторинг
 
Необходимо настроить вызовов данных (CDR) и сбора данных качества взаимодействия (QoE) переднего плана пула мониторинг, с помощью локальной базы данных QoEMetrics и LCSCdr; в противном случае вызова аналитики и панелей мониторинга качества звонков не получить данные для работы с. Перед вам настроить вызова средство подключения к данным, выполните действия, указанные в [Развертывание мониторинга в Скайп для Business Server](../../SfbServer/deploy/deploy-monitoring/deploy-monitoring.md) для настройки CDR и QoE как, так и основные мониторинг.

> [!IMPORTANT]
> Подключения к данным вызовов не будут работать, если мониторинг не включено в пуле переднего плана.

## <a name="enable-call-data-connector"></a>Разрешить подключения к данным звонка

Чтобы настроить и включить вызова подключения к данным, будут использовать следующие командлеты:

| Командлет| Описание|
| :-----------------|---------------:|
| Новый CsCloudCallDataConnection | Online командлет, который устанавливает сборщик данных через Интернет.|
| Get-CsCloudCallDataConnection | Online командлет, который извлекает сбора данных через Интернет.|  
| Get-CsCloudCallDataConnector | Локальный командлет, который получает сведения о подключении, созданных с помощью командлета New-CsCloudCallDataConnection. |
| SET-CsCloudCallDataConnector | Локальный командлет, который сохраняет его в локальной копии сведения о подключении, созданных с помощью командлета New-CsCloudCallDataConnection. |  
| SET-CsCloudCallDataConnectorConfiguration | Локальный командлет, который позволяет включить или отключить соединителя и настройка уровня области.|

### <a name="configure-your-environment"></a>Настройка среды 

Для настройки среды для разрешения сборщик данных через Интернет, необходимо сначала войти к Скайп для бизнеса Online PowerShell с правами администратора. Дополнительные сведения можно [Управлять Скайп для бизнеса в Интернет с помощью Office 365 PowerShell](https://docs.microsoft.com/en-us/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell).

Существует два метода для входа систему Скайп для бизнеса Online PowerShell.

- Из Скайп оболочки управления Business Server 2019 (рекомендуется метод)
- Из другого сеанса PowerShell

#### <a name="log-in-to-skype-for-business-online-powershell-from-the-skype-for-business-server-management-shell-recommended-method"></a>Выполните вход Скайп для бизнеса Online PowerShell из Скайп оболочки управления Business Server (рекомендуется метод)

1. Если включение соединитель в первый раз, выполните следующую команду:

   ```
   New-CsCloudCallDataConnection | Set-CsCloudCallDataConnector -TenantId <tenant_id>
   ```

2. Если ошибка, которая подключение уже существует, это означает, что подключение данных вызов уже существует для клиента. В этом случае выполните команду: 

   ```
   Get-CsCloudCallDataConnection | Set-CsCloudCallDataConnector -TenantId <tenant_id>
   ```


#### <a name="log-in-to-skype-for-business-online-powershell-from-another-powershell-session-optional-method"></a>Выполните вход Скайп для бизнеса Online PowerShell из другого сеанса PowerShell (необязательный метод)

1.  Если включение соединитель в первый раз, выполните следующую команду: 

    ``` 
    New-CsCloudCallDataConnection 
    ```

2.  Если ошибка, которая подключение уже существует, это означает, что подключение данных вызов уже существует для клиента. В этом случае выполните команду: 

    ```
    Get-CsCloudCallDataConnection  
    ```

Выходные данные приведенные выше команды содержит значение маркера, который требуется при настройке в локальную среду следующим образом:

Из внутри Скайп оболочки управления Business Server, введите следующую команду:

```
Set-CsCloudCallDataConnector -Identity Global -TenantId <tenant_id> -Token <token-copied-from-online>
```

### <a name="configure-the-scope"></a>Настройка области

Вызов подключения к данным можно включить для конкретного сайта или для вашей всей Скайп для развертывания Business Server с помощью командлета Set-CsCloudCallDataConnectorConfiguration в Скайп оболочки управления Business Server. Например следующая команда включает вызова подключения к данным на глобальном уровне.

```
Set-CsCloudCallDataConnectorConfiguration -Identity "global" -EnableCallDataConnector $True
```

В дополнение к глобальные параметры параметры конфигурации вызова подключения к данным может быть назначен на уровне сайта. Это обеспечивает гибкость дополнительное управление, когда речь идет о мониторинга. К примеру администратор может включить переадресацию звонков подключения к данным для сайта Redmond, но отключить переадресацию звонков подключения к данным для сайта Дублин, как показано в следующем примере:

```
Set-CsCloudCallDataConnectorConfiguration -Identity "site:Redmond" -EnableCallDataConnector $True
```

```
Set-CsCloudCallDataConnectorConfiguration -Identity "site:Dublin" -EnableCallDataConnector $False
```

Параметры, настроенные в области узла, имеют более высокий приоритет, чем параметры, настроенные в глобальной области. Предположим, например, переадресации звонков подключения к данным включено в глобальной области, но этот параметр отключен на уровне сайта (для сайта Redmond). Это означает, что вызов регистрации и сведения о качестве взаимодействия не будет необходимо перенаправлять пользователей на сайте Redmond. Тем не менее пользователи в другие веб-сайты (то есть пользователи, управляемые в глобальных параметрах вместо параметры сайта Redmond) будут иметь их регистрации вызовов и пересылку сведений о качестве взаимодействия.

В следующей таблице показаны значения для наиболее часто используемые параметры, используемые вызова подключения к данным:  

|Свойство|Описание|Значение по умолчанию|
|:-----|:-----|:-----|
|EnableCallDataConnector  <br/> |Указывает, включена ли вызов подключения к данным. Если значение True, мониторинг записей будет перенаправляться online мониторинга.  <br/> |$False  <br/> |
| Identity  | Определяет уровень области командой: глобальные или сайта.   | глобальные  |

## <a name="disable-call-data-connector"></a>Отключение вызова подключения к данным

Отключение вызова подключения к данным разорвать связь хранилищу данных наблюдения из пула переднего плана, а также его удаления или повлиять на во внутренней базе данных мониторинга. При отключении вызова подключения к данным, остановите Скайп для Business Server из передача данных вызовов в облаке. 

Отключение вызова подключения к данным с помощью командлета Set-CsCloudCallDataConnectorConfiguration в Скайп оболочки управления Business Server. К примеру следующая команда выключает вызова подключения к данным на глобальном уровне путем установки свойства EnableCallDataConnector значение $False.

```
Set-CsCloudCallDataConnectorConfiguration -Identity "global" -EnableCallDataConnector $False
```

Если нужно восстановить, передача данных вызовов в облаке, необходимо задайте свойство EnableCallDataConnector обратно значение $True, как показано в следующем примере:

```
Set-CsCloudCallDataConnectorConfiguration -Identity "global" -EnableCallDataConnector $True
```

## <a name="view-on-premises-data-through-the-online-dashboard"></a>Просмотр локальных данных через Интернет панели мониторинга

 После включения вызова подключения к данным можно просмотреть данные вызова в локальной на панели мониторинга вызова аналитики, как описано в [Аналитике вызова используется для устранения неполадок плохого качества](https://docs.microsoft.com/en-us/skypeforbusiness/using-call-quality-in-your-organization/use-call-analytics-to-troubleshoot-poor-call-quality).


## <a name="for-more-information"></a>Дополнительные сведения

Дополнительные сведения о командлеты можно использовать команду Get-Help из Скайп для консоли Business Server. Например:

Get-Help Get-CsCloudCallDataConnector | Дополнительные

Get-Help Set-CsCloudCallDataConnector | Дополнительные

Get-Help Set-CsCloudCallDataConnectorConfiguration | Дополнительные