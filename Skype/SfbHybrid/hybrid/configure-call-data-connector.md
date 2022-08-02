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
ms.localizationpriority: medium
ms.collection: ''
description: Инструкции по настройке соединителя данных вызовов, который позволяет просматривать данные телеметрии из локальной Skype для бизнеса с помощью Skype для бизнеса Online.
ms.openlocfilehash: 0d92d31798cd4b3fb5a1b4c555ff0ff00c2bdf31
ms.sourcegitcommit: 07761c26b53d92fc36b82cab7b3e38a6de4ff945
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/02/2022
ms.locfileid: "67156937"
---
# <a name="configure-call-data-connector"></a>Настройка соединителя данных звонка

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]


В этой статье описывается настройка соединителя данных звонков — единого набора инструментов, который позволяет просматривать данные качества звонков Skype для бизнеса Server с помощью инструментов Microsoft Call Quality Dashboard (CQD) и Call Analytics (CA).

Дополнительные сведения о преимуществах и предварительных требованиях соединителя вызовов, таких как требования к роли и настройка гибридного подключения, см. в разделе [Plan Call Data Connector](plan-call-data-connector.md).

## <a name="enable-monitoring"></a>Включение мониторинга
 
Необходимо настроить сбор данных для записи звонков (CDR) и качества взаимодействия (QoE) в мониторинге пула переднего плана с помощью локальных баз данных LCSCdr и QoEMetrics. в противном случае аналитика звонков и панели мониторинга качества звонков не будут получать данные для работы. Перед настройкой соединителя данных вызовов выполните действия, описанные в разделе "[Развертывание мониторинга в](../../SfbServer/deploy/deploy-monitoring/deploy-monitoring.md) Skype для бизнеса Server, чтобы настроить CDR и QoE, а также базовый мониторинг.

> [!IMPORTANT]
> Соединитель вызовов данных не будет работать, если мониторинг не включен в пуле переднего плана.

## <a name="enable-call-data-connector"></a>Включение соединителя данных вызова

Чтобы настроить и включить соединитель данных вызовов, используйте следующие командлеты:

| Командлет| Описание|
| :-----------------|---------------:|
| New-CsCloudCallDataConnection | Сетевой командлет, который устанавливает сборщик данных в сети.|
| Get-CsCloudCallDataConnection | Сетевой командлет, который извлекает существующий сборщик данных в сети.|  
| Get-CsCloudCallDataConnector | Локальный командлет, который извлекает сведения о подключении, созданные New-CsCloudCallDataConnection командлетом. |
| Set-CsCloudCallDataConnector | Локальный командлет, который сохраняет локальную копию сведений о подключении, созданных New-CsCloudCallDataConnection командлета. |  
| Set-CsCloudCallDataConnectorConfiguration | Локальный командлет, позволяющий включить или отключить соединитель и настроить уровень области.|

> [!NOTE]
> Чтобы очистить конфигурацию и начать заново, используйте командлет Remove-csclouddatconnectorconfiguration.

### <a name="configure-your-environment"></a>Настройка среды 

Чтобы настроить среду для включения сборщика данных в сети, необходимо сначала войти в модуль Microsoft Teams PowerShell с правами администратора. Дополнительные сведения см. в [обзоре Microsoft Teams PowerShell](/microsoftteams/teams-powershell-overview).

Существует два метода входа в модуль Microsoft Teams PowerShell:

- Из оболочки Skype для бизнеса Server 2019 (рекомендуемый метод)
- Из другого сеанса PowerShell

#### <a name="log-in-to-microsoft-teams-powershell-module-from-the-skype-for-business-server-management-shell-recommended-method"></a>Войдите в модуль Microsoft Teams PowerShell из оболочки Skype для бизнеса Server управления (рекомендуемый метод)

1. Если соединитель включен впервые, выполните следующую команду:

   ```PowerShell
   New-CsCloudCallDataConnection | Set-CsCloudCallDataConnector -TenantId <tenant_id>
   ```

2. Если вы получаете сообщение об ошибке, что подключение уже существует, это означает, что подключение к данным вызова уже существует для вашего клиента. В этом случае выполните команду: 

   ```PowerShell
   Get-CsCloudCallDataConnection | Set-CsCloudCallDataConnector -TenantId <tenant_id>
   ```


#### <a name="log-in-to-microsoft-teams-powershell-module-from-another-powershell-session-optional-method"></a>Вход в модуль Microsoft Teams PowerShell из другого сеанса PowerShell (необязательный метод)

1.  Если соединитель включен впервые, выполните следующую команду: 

    ```PowerShell 
    New-CsCloudCallDataConnection 
    ```

2.  Если вы получаете сообщение об ошибке, что подключение уже существует, это означает, что подключение к данным вызова уже существует для вашего клиента. В этом случае выполните команду: 

    ```PowerShell
    Get-CsCloudCallDataConnection  
    ```

Выходные данные приведенных выше команд содержат значение токена, которое потребуется при настройке локальной среды следующим образом:

В командной Skype для бизнеса Server командной строки укажите следующую команду:

```PowerShell
Set-CsCloudCallDataConnector -Identity Global -TenantId <tenant_id> -Token <token-copied-from-online>
```

### <a name="configure-the-scope"></a>Настройка области

Соединитель вызовов данных можно включить для определенного сайта или для всего развертывания Skype для бизнеса Server с помощью командлета Set-CsCloudCallDataConnectorConfiguration из оболочки Skype для бизнеса Server управления. Например, приведенная ниже команда позволяет вызывать соединитель данных в глобальной области:

```PowerShell
Set-CsCloudCallDataConnectorConfiguration -Identity "global" -EnableCallDataConnector $True
```

Помимо глобальных параметров, параметры конфигурации соединителя вызовов данных можно назначить области сайта. Это обеспечивает дополнительную гибкость управления при мониторинге. Например, администратор может включить переадресацию соединителя данных вызовов для сайта Redmond, но отключить переадресацию соединителя данных  вызовов для сайта в Ирландии, как показано в следующем примере:

```PowerShell
Set-CsCloudCallDataConnectorConfiguration -Identity "site:Redmond" -EnableCallDataConnector $True
```

```PowerShell
Set-CsCloudCallDataConnectorConfiguration -Identity "site:Dublin" -EnableCallDataConnector $False
```

Параметры, настроенные в области сайта, имеют приоритет над параметрами, настроенными в глобальной области. Например, предположим, что переадресация соединителя вызовов данных включена в глобальной области, но отключена в области сайта (для сайта Redmond). Это означает, что регистрация вызовов и сведения о QoE не будут пересылаться пользователям на сайте Redmond. Однако пользователи на других сайтах (то есть пользователи, управляемые глобальными параметрами, а не параметрами сайта Redmond) будут иметь запись сведений о звонках и сведения о QoE.

Значения наиболее часто используемых параметров, используемых соединителем данных вызовов, показаны в следующей таблице:  

|Свойство|Описание|Значение по умолчанию|
|:-----|:-----|:-----|
|EnableCallDataConnector  <br/> |Указывает, включен ли соединитель данных вызова. Если значение равно True, записи мониторинга будут перенаправлены в веб-мониторинг.  <br/> |$False  <br/> |
| Удостоверение | Определяет уровень области для команды: глобальный или сайт.   | глобальный  |

## <a name="disable-call-data-connector"></a>Отключение соединителя данных вызовов

Отключение соединителя данных вызовов не отменяет связь хранилища мониторинга с пулом переднего плана и не удаляет или иным образом не влияет на серверную базу данных мониторинга. При отключении соединителя данных вызовов Skype для бизнеса Server отправку данных вызовов в облако. 

Соединитель данных вызовов отключается с помощью Set-CsCloudCallDataConnectorConfiguration командлета из оболочки Skype для бизнеса Server управления. Например, приведенная ниже команда отключает call Data Connector в глобальной области, задав для свойства EnableCallDataConnector значение $False:

```PowerShell
Set-CsCloudCallDataConnectorConfiguration -Identity "global" -EnableCallDataConnector $False
```

Если вы хотите возобновить отправку данных вызовов в облако, задайте для свойства EnableCallDataConnector значение $True, как показано в следующем примере:

```PowerShell
Set-CsCloudCallDataConnectorConfiguration -Identity "global" -EnableCallDataConnector $True
```

## <a name="view-on-premises-data-through-the-online-dashboard"></a>Просмотр локальных данных через веб-панель мониторинга

 После включения соединителя данных о звонках можно просмотреть локальные данные о звонках на панели мониторинга аналитики звонков или панели мониторинга качества звонков, как описано [](/skypeforbusiness/using-call-quality-in-your-organization/use-call-analytics-to-troubleshoot-poor-call-quality) в разделе "Использование аналитики звонков" для устранения неполадок низкого качества, включения и использования панели мониторинга качества звонков для [Microsoft Teams и Skype для бизнеса Online](/MicrosoftTeams/turning-on-and-using-call-quality-dashboard).

## <a name="for-more-information"></a>Дополнительные сведения

Для получения дополнительных сведений о командлетах можно использовать команду Get-Help из Skype для бизнеса Server Management Shell. Например:

Get-Help Get-CsCloudCallDataConnector | больше

Get-Help Set-CsCloudCallDataConnector | больше

Get-Help Set-CsCloudCallDataConnectorConfiguration | больше
