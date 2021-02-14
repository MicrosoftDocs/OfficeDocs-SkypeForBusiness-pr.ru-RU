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
description: Инструкции по настройке соединители данных звонков, позволяющие просматривать телеметрию из локальной сети Skype для бизнеса с помощью средств Skype для бизнеса Online.
ms.openlocfilehash: 0354f5a1fd1b4794af29d23e0a0fc1bf49dfebd2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726929"
---
# <a name="configure-call-data-connector"></a>Настройка соединителя данных звонка

В этой статье описано, как настроить соединители данных звонков — единый набор инструментов, позволяющий просматривать данные о качестве звонков Skype для бизнеса Server с помощью панели мониторинга качества звонков Skype для бизнеса Online и средств аналитики звонков (CA).

Дополнительные сведения о преимуществах и предварительных требованиях соединительной связи для обработки вызовов, таких как требования к роли и настройка гибридного подключения, см. в подключении [plan Call Data Connector.](plan-call-data-connector.md)

## <a name="enable-monitoring"></a>Включить мониторинг
 
Необходимо настроить сбор данных регистрации вызовов (CDR) и качества обслуживания (QoE) в мониторинге пула переднего уровня с помощью локальных баз данных LCSCdr и QoEMetrics; в противном случае аналитика вызовов и панели мониторинга качества вызовов не будут получать данные для работы. Before you Configure Call Data Connector, follow the steps provided in [Deploy monitoring in Skype for Business Server](../../SfbServer/deploy/deploy-monitoring/deploy-monitoring.md) to configure both CDR and QoE as well as basic Monitoring.

> [!IMPORTANT]
> Соединители данных вызовов не будут работать, если мониторинг не включен в пуле переднего входа.

## <a name="enable-call-data-connector"></a>Enable Call Data Connector

Чтобы настроить и включить соединители данных о вызовах, используйте следующие cmdlets:

| Командлет| Описание|
| :-----------------|---------------:|
| New-CsCloudCallDataConnection | Сетевой cmdlet, который устанавливает сетевой сборщик данных.|
| Get-CsCloudCallDataConnection | Сетевой cmdlet, который извлекает существующий сетевой сборщик данных.|  
| Get-CsCloudCallDataConnector | Локальное решение, которое извлекает сведения о под соединении, созданные New-CsCloudCallDataConnection. |
| Set-CsCloudCallDataConnector | Локальное решение, которое сохраняет локальное копирование сведений о под подключениех, созданных New-CsCloudCallDataConnection. |  
| Set-CsCloudCallDataConnectorConfiguration | Локальное решение, позволяя включить или отключить соединители, а также настроить уровень области.|

> [!NOTE]
> Чтобы стереть конфигурацию и начать заново, используйте cmdlet Remove-csclouddatconnectorconfiguration.

### <a name="configure-your-environment"></a>Настройка среды 

Чтобы настроить среду для сетевого сборщика данных, необходимо сначала войти в Skype для бизнеса Online PowerShell от администратора. Дополнительные сведения см. в под [управлением Skype для бизнеса Online с помощью PowerShell в Office 365.](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)

Существует два способа входа в PowerShell в Skype для бизнеса Online:

- Из оболочки управления Skype для бизнеса Server 2019 (рекомендуемый метод)
- Из другого сеанса PowerShell

#### <a name="log-in-to-skype-for-business-online-powershell-from-the-skype-for-business-server-management-shell-recommended-method"></a>Войдите в Skype для бизнеса Online PowerShell из оболочки управления Skype для бизнеса Server (рекомендуемый метод)

1. При первом включении соединители запустите следующую команду:

   ```PowerShell
   New-CsCloudCallDataConnection | Set-CsCloudCallDataConnector -TenantId <tenant_id>
   ```

2. Если вы получите сообщение об ошибке, что подключение уже существует, это означает, что подключение к данным вызова уже существует для вашего клиента. В этом случае запустите команду: 

   ```PowerShell
   Get-CsCloudCallDataConnection | Set-CsCloudCallDataConnector -TenantId <tenant_id>
   ```


#### <a name="log-in-to-skype-for-business-online-powershell-from-another-powershell-session-optional-method"></a>Войдите в Skype для бизнеса Online PowerShell из другого сеанса PowerShell (необязательный метод)

1.  При первом включении соединители запустите следующую команду: 

    ```PowerShell 
    New-CsCloudCallDataConnection 
    ```

2.  Если вы получите сообщение об ошибке, что подключение уже существует, это означает, что подключение к данным вызова уже существует для вашего клиента. В этом случае запустите команду: 

    ```PowerShell
    Get-CsCloudCallDataConnection  
    ```

Выходные данные вышеперечисленных команд содержат значение маркера, которое потребуется при настройке локальной среды следующим образом:

В командной оболочке Skype для бизнеса Server укажите следующую команду:

```PowerShell
Set-CsCloudCallDataConnector -Identity Global -TenantId <tenant_id> -Token <token-copied-from-online>
```

### <a name="configure-the-scope"></a>Настройка области

Вы можете включить соединители данных звонков для определенного сайта или всего развертывания Skype для бизнеса Server с помощью Set-CsCloudCallDataConnectorConfiguration в оболочке управления Skype для бизнеса Server. Например, следующая команда включает call Data Connector в глобальной области:

```PowerShell
Set-CsCloudCallDataConnectorConfiguration -Identity "global" -EnableCallDataConnector $True
```

Помимо глобальных параметров, параметры конфигурации call Data Connector можно на уровне сайта. Это обеспечивает дополнительную гибкость управления, когда речь идет о мониторинге. Например, администратор может включить переадправление соединители данных вызовов для сайта Redmond, но отключить переадправление call Data Connector для сайта Dublin, как показано в следующем примере:

```PowerShell
Set-CsCloudCallDataConnectorConfiguration -Identity "site:Redmond" -EnableCallDataConnector $True
```

```PowerShell
Set-CsCloudCallDataConnectorConfiguration -Identity "site:Dublin" -EnableCallDataConnector $False
```

Параметры, настроенные на уровне сайта, имеют приоритет над настройками, настроенными на глобальном уровне. Например, предположим, что переад вызов соединитель данных включен на глобальном уровне, но отключен на уровне сайта (для сайта Redmond). Это означает, что регистрация вызовов и сведения о качестве вызова не будут переададации для пользователей на сайте Redmond. Однако пользователи на других сайтах (то есть пользователи, управляемые глобальными настройками, а не с помощью параметров сайта Redmond) будут иметь регистрацию вызовов и перенаправят сведения о QoE.

Значения наиболее часто используемых параметров, используемых соединитетелем данных параметров вызова, показаны в следующей таблице:  

|Свойство|Описание|Значение по умолчанию|
|:-----|:-----|:-----|
|EnableCallDataConnector  <br/> |Указывает, включен ли соединител данных о вызовах. Если задается true, записи мониторинга будут перенаададовы на веб-мониторинг.  <br/> |$False  <br/> |
| Identity | Определяет уровень области для команды: глобальный или сайт.   | global  |

## <a name="disable-call-data-connector"></a>Отключение соединители данных о вызовах

Отключение соединителя данных о вызовах не отключает хранилище мониторинга от пула переднего входа и не делает его удалить или иным образом влиять на базу данных мониторинга. When you disable Call Data Connector, you stop Skype for Business Server from uploading call data to the cloud. 

Соединители данных звонков отключаются с помощью Set-CsCloudCallDataConnectorConfiguration в оболочке управления Skype для бизнеса Server. Например, следующая команда отключает call Data Connector на глобальном уровне, задав для свойства EnableCallDataConnector $False:

```PowerShell
Set-CsCloudCallDataConnectorConfiguration -Identity "global" -EnableCallDataConnector $False
```

Чтобы возобновить отправку данных о вызовах в облако, установите для свойства EnableCallDataConnector $True, как показано в следующем примере:

```PowerShell
Set-CsCloudCallDataConnectorConfiguration -Identity "global" -EnableCallDataConnector $True
```

## <a name="view-on-premises-data-through-the-online-dashboard"></a>Просмотр локальной информации с помощью информационной панели в Интернете

 После включения соединители данных о вызовах вы можете просматривать данные о локальном звонке на [](https://docs.microsoft.com/skypeforbusiness/using-call-quality-in-your-organization/use-call-analytics-to-troubleshoot-poor-call-quality) информационной панели аналитики звонков или панели мониторинга качества звонков, как описано в описании использования аналитики звонков для устранения неполадок с неудовлетворительной качеством и включения и использования панели мониторинга качества звонков для Microsoft Teams и [Skype для бизнеса Online.](/MicrosoftTeams/turning-on-and-using-call-quality-dashboard)

## <a name="for-more-information"></a>Дополнительные сведения

For more information on the cmdlets, you can use the Get-Help command from the Skype for Business Server Management Shell. Пример:

Get-Help Get-CsCloudCallDataConnector | more

Get-Help Set-CsCloudCallDataConnector | more

Get-Help Set-CsCloudCallDataConnectorConfiguration | more
