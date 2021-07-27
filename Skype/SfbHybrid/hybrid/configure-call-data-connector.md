---
title: Настройка соединителя данных звонка
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: Инструкции по настройке соединитетеля данных вызовов, который позволяет просматривать телеметрию из Skype для бизнеса локального использования с помощью средств Skype для бизнеса Online.
ms.openlocfilehash: 28a9ba2f00a071ff5b1c0781240cf54a2de929e8
ms.sourcegitcommit: 9879bc587382755d9a5cd63a75b0e7dc4e15574c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/21/2021
ms.locfileid: "53510600"
---
# <a name="configure-call-data-connector"></a>Настройка соединителя данных звонка

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]


В этой статье описывается настройка соединители данных вызовов — единый набор средств, позволяющий просматривать Skype для бизнеса Server качественные данные вызовов с помощью средств Skype для бизнеса мониторинга качества вызовов в Интернете (CQD) и Call Analytics (CA).

Дополнительные сведения о преимуществах и предварительных требованиях к соединителу данных вызовов, таких как требования к роли и настройке гибридного подключения, см. в руб. [Plan Call Data Connector.](plan-call-data-connector.md)

## <a name="enable-monitoring"></a>Включить мониторинг
 
Необходимо настроить сбор данных для записи данных вызовов (CDR) и Quality of Experience (QoE) в переднем окантовке мониторинга пула с локальными базами данных LCSCdr и QoEMetrics; в противном случае панели мониторинга качества вызовов и вызовов не будут работать с данными. Перед настройкой соединители данных вызовов выполните действия, предусмотренные в мониторинге Deploy [в](../../SfbServer/deploy/deploy-monitoring/deploy-monitoring.md) Skype для бизнеса Server, чтобы настроить CDR и QoE, а также базовый мониторинг.

> [!IMPORTANT]
> Соединители данных вызовов не будут работать, если мониторинг не включен в переднем пуле.

## <a name="enable-call-data-connector"></a>Включить соединители данные вызовов

Чтобы настроить и включить соединители данных вызовов, вы будете использовать следующие cmdlets:

| Командлет| Описание|
| :-----------------|---------------:|
| New-CsCloudCallDataConnection | Сетевой комлет, который создает сборщик данных в Интернете.|
| Get-CsCloudCallDataConnection | Сетевой комлет, который извлекает существующий сборщик данных в Интернете.|  
| Get-CsCloudCallDataConnector | Локальное решение, которое извлекает сведения о связи, созданные New-CsCloudCallDataConnection. |
| Set-CsCloudCallDataConnector | Локальное решение, которое сохраняет локальное копирование сведений о подключении, созданных New-CsCloudCallDataConnection. |  
| Set-CsCloudCallDataConnectorConfiguration | Локальное поле, которое позволяет включить или отключить соединители и настроить уровень области.|

> [!NOTE]
> Чтобы стереть конфигурацию и начать сначала, используйте cmdlet Remove-csclouddatconnectorconfiguration.

### <a name="configure-your-environment"></a>Настройка среды 

Чтобы настроить среду, чтобы включить сборщик данных в Интернете, необходимо сначала войти Skype для бизнеса PowerShell в качестве администратора. Дополнительные сведения см. в [Skype для бизнеса Online с Office 365 PowerShell.](/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)

Существует два метода входа в Skype для бизнеса PowerShell:

- Из оболочки управления Skype для бизнеса Server 2019 (рекомендуемый метод)
- Из другого сеанса PowerShell

#### <a name="log-in-to-skype-for-business-online-powershell-from-the-skype-for-business-server-management-shell-recommended-method"></a>Войдите в Skype для бизнеса PowerShell из Skype для бизнеса Server управления (рекомендуемый метод)

1. При первом включении соединитетеля запустите следующую команду:

   ```PowerShell
   New-CsCloudCallDataConnection | Set-CsCloudCallDataConnector -TenantId <tenant_id>
   ```

2. Если вы получаете ошибку, которая уже существует, это означает, что подключение к данным вызова уже существует для клиента. В этом случае запустите команду: 

   ```PowerShell
   Get-CsCloudCallDataConnection | Set-CsCloudCallDataConnector -TenantId <tenant_id>
   ```


#### <a name="log-in-to-skype-for-business-online-powershell-from-another-powershell-session-optional-method"></a>Войдите в Skype для бизнеса PowerShell из другого сеанса PowerShell (необязательный метод)

1.  При первом включении соединитетеля запустите следующую команду: 

    ```PowerShell 
    New-CsCloudCallDataConnection 
    ```

2.  Если вы получаете ошибку, которая уже существует, это означает, что подключение к данным вызова уже существует для клиента. В этом случае запустите команду: 

    ```PowerShell
    Get-CsCloudCallDataConnection  
    ```

Выход вышеперечисленных команд содержит значение маркера, которое необходимо при настройке локальной среды следующим образом:

Из оболочки Skype для бизнеса Server управления укажите следующую команду:

```PowerShell
Set-CsCloudCallDataConnector -Identity Global -TenantId <tenant_id> -Token <token-copied-from-online>
```

### <a name="configure-the-scope"></a>Настройка области

Вы можете включить соединителя данных вызовов для определенного сайта или для Skype для бизнеса Server развертывания с помощью Set-CsCloudCallDataConnectorConfiguration из Skype для бизнеса Server оболочки управления. Например, следующая команда позволяет подключать данные вызовов в глобальном масштабе:

```PowerShell
Set-CsCloudCallDataConnectorConfiguration -Identity "global" -EnableCallDataConnector $True
```

В дополнение к глобальным настройкам параметры конфигурации соединители данных вызовов могут быть назначены области сайта. Это обеспечивает дополнительную гибкость управления при мониторинге. Например, администратор может включить переадправление соединитель данных вызовов для сайта Redmond, но отключить переадправление соединитель данных вызовов для сайта Дублина, как показано в следующем примере:

```PowerShell
Set-CsCloudCallDataConnectorConfiguration -Identity "site:Redmond" -EnableCallDataConnector $True
```

```PowerShell
Set-CsCloudCallDataConnectorConfiguration -Identity "site:Dublin" -EnableCallDataConnector $False
```

Параметры, настроенные в области сайта, имеют приоритет над настройками, настроенными в глобальном масштабе. Например, предположим, что переададка соединитель данных вызовов включена в глобальном масштабе, но отключена в области сайта (для сайта Redmond). Это означает, что запись детализации вызовов и сведения о QoE не будут переададации для пользователей сайта Redmond. Однако пользователи на других сайтах (то есть пользователи, управляемые глобальными настройками вместо параметров сайта Redmond) будут иметь запись параметров зова и переададации данных QoE.

Значения наиболее часто используемых параметров, используемых соединитетелем данных вызовов, показаны в следующей таблице:  

|Свойство|Описание|Значение по умолчанию|
|:-----|:-----|:-----|
|EnableCallDataConnector  <br/> |Указывает, включен ли соединитатель данных вызовов. Если true, записи мониторинга будут перенаадються в режим онлайн-мониторинга.  <br/> |$False  <br/> |
| Удостоверение | Определяет уровень области для команды: глобальный или сайт.   | глобальный  |

## <a name="disable-call-data-connector"></a>Отключение соединитетеля данных вызовов

Отключение соединителя данных вызовов не отсоединяет хранилище мониторинга от пула переднего конца и не влияет на базу данных мониторинга заднего входа. При отключении соединители данных вызовов Skype для бизнеса Server отправку данных вызовов в облако. 

Вы отключили соединителя данных вызовов с помощью Set-CsCloudCallDataConnectorConfiguration из оболочки управления Skype для бизнеса Server. Например, следующая команда отключает соединитель данных вызовов в глобальной области, установив свойство EnableCallDataConnector для $False:

```PowerShell
Set-CsCloudCallDataConnectorConfiguration -Identity "global" -EnableCallDataConnector $False
```

Если вы хотите возобновить отправку данных вызовов в облако, установите свойство EnableCallDataConnector $True, как показано в следующем примере:

```PowerShell
Set-CsCloudCallDataConnectorConfiguration -Identity "global" -EnableCallDataConnector $True
```

## <a name="view-on-premises-data-through-the-online-dashboard"></a>Просмотр локальной информации с помощью панели мониторинга в Интернете

 После включения соединитетеля данных вызовов можно просматривать данные локального вызова на панели мониторинга аналитики вызовов или панели мониторинга качества вызовов, как описано в use [Call Analytics,](/skypeforbusiness/using-call-quality-in-your-organization/use-call-analytics-to-troubleshoot-poor-call-quality) чтобы устранить проблемы низкого качества, включить и использовать панель мониторинга качества вызовов для Microsoft Teams [и Skype для бизнеса Online](/MicrosoftTeams/turning-on-and-using-call-quality-dashboard).

## <a name="for-more-information"></a>Дополнительные сведения

Дополнительные сведения о командлетах можно использовать Get-Help командной командной Skype для бизнеса Server. Например:

Get-Help Get-CsCloudCallDataConnector | more

Get-Help Set-CsCloudCallDataConnector | more

Get-Help Set-CsCloudCallDataConnectorConfiguration | more