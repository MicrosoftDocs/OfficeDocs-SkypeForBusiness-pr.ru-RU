---
title: Управление настройками службы централизованного ведения журналов в Skype для бизнеса Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 8/17/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 93b9a354-9aea-4b3a-a4fe-68a89f436196
description: Сводка. Узнайте, как извлекать, обновлять и создавать параметры конфигурации для службы централизованного ведения журналов в Skype для бизнеса Server 2015.
ms.openlocfilehash: dd292465d65116dc1f497a733ca8e010e57b9137
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49835159"
---
# <a name="manage-centralized-logging-service-configuration-settings-in-skype-for-business-server-2015"></a>Управление настройками службы централизованного ведения журналов в Skype для бизнеса Server 2015

**Сводка:** Learn how to retrieve, update, and create configuration settings for the Centralized Logging Service in Skype for Business Server 2015.

Служба централизованного ведения журналов управляется и настраивается параметрами, созданными и используемыми контроллером централизованной службы ведения журналов (CLSController) для отправки команд агенту централизованной службы ведения журналов (CLSAgent) отдельного компьютера. Агент обрабатывает команды, которые ему отправляются, и (в случае команды "Начните") использует конфигурацию сценариев, поставщиков, продолжительность трассировки и флаги, чтобы начать собирать журналы трассировки в соответствии с предоставленными сведениями о конфигурации.

> [!IMPORTANT]
>  Не все Windows PowerShell, перечисленные для службы централизованного ведения журналов, предназначены для локального развертывания Skype для бизнеса Server 2015. Несмотря на то что они могут показаться работоудаными, следующие cmdlets не предназначены для работы с локального развертывания Skype для бизнеса Server 2015:

-  **CsClsRegion cmdlets:** [Get-CsClsRegion,](https://docs.microsoft.com/powershell/module/skype/get-csclsregion?view=skype-ps) [Set-CsClsRegion,](https://docs.microsoft.com/powershell/module/skype/set-csclsregion?view=skype-ps) [New-CsClsRegion](https://docs.microsoft.com/powershell/module/skype/new-csclsregion?view=skype-ps)и [Remove-CsClsRegion](https://docs.microsoft.com/powershell/module/skype/remove-csclsregion?view=skype-ps).
-  **Командлеты CsClsSearchTerm:** [Get-CsClsSearchTerm](https://docs.microsoft.com/powershell/module/skype/get-csclssearchterm?view=skype-ps) и [Set-CsClsSearchTerm](https://docs.microsoft.com/powershell/module/skype/set-csclssearchterm?view=skype-ps).
-  **CsClsSecurityGroup cmdlets:** [Get-CsClsSecurityGroup,](https://docs.microsoft.com/powershell/module/skype/get-csclssecuritygroup?view=skype-ps) [Set-CsClsSecurityGroup,](https://docs.microsoft.com/powershell/module/skype/set-csclssecuritygroup?view=skype-ps) [New-CsClsSecurityGroup](https://docs.microsoft.com/powershell/module/skype/new-csclssecuritygroup?view=skype-ps)и [Remove-CsClsSecurityGroup.](https://docs.microsoft.com/powershell/module/skype/remove-csclssecuritygroup?view=skype-ps)

Параметры, определенные в этих cmdlets, не препятствуют работе и не вызывают никаких отрицательных последствий, но они предназначены для использования с Microsoft 365 или Office 365 и не дают ожидаемых результатов в локальном развертывании. Это не означает полную бесполезность таких командлетов в локальных развертываниях, но вопрос об их использовании выходит за рамки данной документации.

Централизованную службу ведения журналов можно запустить в области, которая включает один компьютер или пул компьютеров, на уровне сайта (то есть на определенном сайте, например на сайте Redmond, который содержит коллекцию компьютеров и пулов в развертывании) или на глобальном уровне (то есть на всех компьютерах и пулах в развертывании).

Чтобы настроить область службы централизованного ведения журналов с помощью оболочки управления Skype для бизнеса Server, необходимо быть участником групп безопасности управления доступом на основе ролей (RBAC) CsAdministrator или CsServerAdministrator, а также настраиваемой роли RBAC, которая содержит какую-либо из этих двух групп. Чтобы получить список всех ролей RBAC, которые были назначены этому командлету (включая все самостоятельно созданные роли RBAC), запустите следующую команду в командной Windows PowerShell Командная Windows PowerShell Skype для бизнеса Server:

```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "<Skype for Business cmdlet>"}
```

Пример:

```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}
```

> [!NOTE]
> Существуют фундаментальные различия между командами командной строки, которые можно выполнить в Windows PowerShell clSController. Windows PowerShell предоставляет богатый метод для настройки и определения сценариев, а также для эффективного использования этих сценариев для сценариев устранения неполадок. Хотя CLSController позволяет быстро и эффективно выполнять команды и получать результаты, набор команд этого средства ограничен командами, доступными из командной строки. В отличие от Windows PowerShell командлетов CLSController не может определять новые сценарии, управлять областью на уровне сайта или на глобальном уровне и многими другими ограничениями ограниченного набора команд, который не может быть динамически настроен. Хотя CLSController предоставляет средства для быстрого выполнения, Windows PowerShell предоставляет средства для расширения функций централизованной службы ведения журналов за пределами возможностей CLSController.

Область одного компьютера может быть определена во время выполнения команды [Search-CsClsLogging,](https://docs.microsoft.com/powershell/module/skype/search-csclslogging?view=skype-ps) [Show-CsClsLogging,](https://docs.microsoft.com/powershell/module/skype/show-csclslogging?view=skype-ps) [Start-CsClsLogging,](https://docs.microsoft.com/powershell/module/skype/start-csclslogging?view=skype-ps) [Stop-CsClsLogging,](https://docs.microsoft.com/powershell/module/skype/stop-csclslogging?view=skype-ps) [Sync-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/sync-csclslogging?view=skype-ps) и [Update-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/update-csclslogging?view=skype-ps) с помощью параметра -Computers. Параметр -Computers принимает разделенный запятой список полного доменного имени (FQDNs) для целевого компьютера.

> [!TIP]
> Можно также определить пулы -Pools и разделенный запятой список пулов, в которые необходимо выполнить команды ведения журнала.

Области сайта и глобальные области определяются в cmdlets **New-**, **Set-** и **Remove-Centralized** Logging Service. В следующих примерах показано, как задать область сайта и глобальную область.

> [!IMPORTANT]
> Показанные команды могут содержать параметры и концепции, описанные в других разделах. Примеры команд предназначены для демонстрации использования параметра **-Identity** для определения области, а остальные параметры включаются для полноты и указания области. Дополнительные сведения о командлетах **Set-CsClsConfiguration** см. в описании командлета [Set-CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csclsconfiguration?view=skype-ps) в документации по применению.

### <a name="to-retrieve-the-current-centralized-logging-service-configuration"></a>Извлечение текущей конфигурации службы централизованного ведения журналов

1. Запустите оболочку управления Skype для бизнеса Server: нажмите кнопку "Начните", выберите "Все программы", "Skype для бизнеса **2015",** а затем щелкните "Skype для бизнеса Server Management **Shell".**

2. Введите следующую команду в командной строке:

   ```PowerShell
   Get-CsClsConfiguration
   ```

Используйте для создания новой конфигурации или обновления существующей конфигурации с помощью cmdlets **New-CsClsConfiguration** и **Set-CsClsConfiguration.** При запуске **Get-CsClsConfiguration** отображаются сведения, похожие на следующие снимки экрана, где в развертывании в настоящее время установлена глобальная конфигурация по умолчанию, но конфигурации сайта не определены:

![Пример выходных данных из get-CsClsConfiguration.](../../media/Ops_Get-CsClsConfiguration_Basic.jpg)

### <a name="to-retrieve-the-current-centralized-logging-service-configuration-from-the-computer-local-store"></a>Извлечение текущей конфигурации службы централизованного ведения журналов с локального компьютера

1. Запустите оболочку управления Skype для бизнеса Server: нажмите кнопку "Начните", выберите "Все программы", "Skype для бизнеса **2015",** а затем щелкните "Skype для бизнеса Server Management **Shell".**

2. Введите следующую команду в командной строке:

   ```PowerShell
   Get-CsClsConfiguration -LocalStore
   ```

При использовании первого примера, в котором **get-CsClsConfiguration** не указывает никаких параметров, команда ссылается на центральное хранилище управления для данных. Если указан параметр -LocalStore, команда ссылается на компьютер LocalStore, а не центральное хранилище управления.
### <a name="to-retrieve-a-listing-of-scenarios-currently-defined"></a>Получение листинга сценариев, определенных в текущий момент

1. Запустите оболочку управления Skype для бизнеса Server: нажмите кнопку "Начните", выберите "Все программы", "Skype для бизнеса **2015",** а затем щелкните "Skype для бизнеса Server Management **Shell".**

2. Введите следующую команду в командной строке:

   ```PowerShell
   Get-CsClsConfiguration -Identity <scope and name> | Select-Object -ExpandProperty Scenarios
   ```

    Например, для получения сценариев, определенных в глобальной области, выполните следующую команду.

   ```PowerShell
   Get-CsClsConfiguration -Identity "global" | Select-Object -ExpandProperty Scenarios
   ```

Этот cmdlet **Get-CsClsConfiguration** всегда отображает сценарии, в которые входит конфигурация заданной области. В большинстве случаев отображаются не все сценарии, кроме того, отображаемые сценарии сокращаются. Используемая здесь команда отображает список всех сценариев и частичные сведения об используемых поставщиках, настройках и флагах.
### <a name="to-update-a-global-scope-for-the-centralized-logging-service-by-using-windows-powershell"></a>Обновление глобальной области для службы централизованного ведения журналов с помощью Windows PowerShell

1. Запустите оболочку управления Skype для бизнеса Server: нажмите кнопку "Начните", выберите "Все программы", "Skype для бизнеса **2015",** а затем щелкните "Skype для бизнеса Server Management **Shell".**

2. Введите следующую команду в командной строке:

   ```PowerShell
   Set-CsClsConfiguration -Identity <scope> -EtlFileRolloverSizeMB <size for logging file in megabytes>
   ```

   Пример:

   ```PowerShell
   Set-CsClsConfiguration -Identity "global" -EtlFileRolloverSizeMB 40
   ```

При выполнении этой команды CLSAgent на каждом компьютере и в каждом пуле развертывания задает для размера переключения на новый файл трассировки значение 40 МБ. Эта команда влияет на компьютеры и пулы на всех сайтах и задает в качестве размера переключения на новый журнал трассировки значение 40 МБ.
### <a name="to-update-a-site-scope-for-the-centralized-logging-service-by-using-windows-powershell"></a>Обновление области сайта для службы централизованного ведения журналов с помощью Windows PowerShell

1. Запустите оболочку управления Skype для бизнеса Server: нажмите кнопку "Начните", выберите "Все программы", "Skype для бизнеса **2015",** а затем щелкните "Skype для бизнеса Server Management **Shell".**

2. Введите следующую команду в командной строке:

   ```PowerShell
   Set-CsClsConfiguration -Identity <scope/site name> -EtlFileRolloverSizeMB <size for logging file in megabytes>
   ```

   Пример:

   ```PowerShell
   Set-CsClsConfiguration -Identity "site/Redmond" -EtlFileRolloverSizeMB 40
   ```

> [!NOTE]
> Как отмечено в примере, расположением файлов журнала по умолчанию является каталог %TEMP%\Tracing. Однако, так как фактически файл записывает CLSAgent, который выполняется как сетевая служба, переменная %TEMP% расширяется до %WINDIR%\ServiceProfiles\NetworkService\AppData\Local.

При выполнении этой команды CLSAgent на каждом компьютере и в каждом пуле сайта Redmond задает для размера переключения на новый файл трассировки значение 40 МБ. Эта команда не повлияет на компьютеры и пулы на других сайтах, которые продолжат использовать текущее значение размера переключения на новый журнал трассировки, определенное либо по умолчанию (20 МБ), либо во время запуска сеанса ведения журнала.
### <a name="to-create-a-new-centralized-logging-service-configuration"></a>Создание новой конфигурации службы централизованного ведения журналов

1. Запустите оболочку управления Skype для бизнеса Server: нажмите кнопку "Начните", выберите "Все программы", "Skype для бизнеса **2015",** а затем щелкните "Skype для бизнеса Server Management **Shell".**

2. Введите следующую команду в командной строке:

   ```PowerShell
   New-CsClsConfiguration -Identity <scope and name> [CsClsConfiguration options for this site]
   ```

    > [!NOTE]
    > Командлет New-CsClsConfiguration предоставляет доступ к большому количеству необязательных параметров конфигурации. Подробные сведения о параметрах конфигурации см. в настройках [Get-CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csclsconfiguration?view=skype-ps) и [Understanding Centralized Logging Service Configuration Settings.](https://technet.microsoft.com/library/3c34e600-0b91-43dc-b4cc-90b6a70ee12e.aspx)

Например, для создания новой конфигурации, которая определяет сетевую папку для файлов кэша, а также период и размер переключения для файлов журнала, введите следующую команду:

  ```PowerShell
  New-CsClsConfiguration -Identity "site:Redmond" -CacheFileNetworkFolder "\\fs01.contoso.net\filestore\logfiles" -EtlFileRolloverMinutes 120 -EtlFileRolloverSizeMB 40
  ```

Следует тщательно спланировать создание новых конфигураций и определение новых свойств для службы централизованного ведения журналов. Необходимо проявлять осторожность при изменениях и учитывать их влияние на возможность правильного ведения журналов в проблемных сценариях. В конфигурацию следует вносить такие изменения, которые улучшат возможности управления журналами и позволят задать такие значения размера и периода переключения, которые помогут устранить возможные проблемы.
### <a name="to-remove-an-existing-centralized-logging-service-configuration"></a>Удаление существующей конфигурации службы централизованного ведения журналов

1. Запустите оболочку управления Skype для бизнеса Server: нажмите кнопку "Начните", выберите "Все программы", "Skype для бизнеса **2015",** а затем щелкните "Skype для бизнеса Server Management **Shell".**

2. Введите следующую команду в командной строке:

   ```PowerShell
   Remove-CsClsConfiguration -Identity <scope and name>
   ```

Например, чтобы удалить конфигурацию службы централизованного ведения журналов, созданную для увеличения времени переката файла журнала, увеличить размер файла журнала отката и установить расположение кэша файлов журнала в сетевую папку следующим образом:

  ```PowerShell
  Remove-CsClsConfiguration -Identity "site:Redmond"
  ```

> [!NOTE]
> Это новая конфигурация, созданная в процедуре "Создание новой конфигурации службы централизованного ведения журналов".

Если удалить конфигурацию уровня сайта, сайт будет использовать глобальные параметры.
## <a name="see-also"></a>См. также

[Настройка поставщиков службы централизованного ведения журналов в Skype для бизнеса Server 2015](configure-providers.md)

[Настройка сценариев для службы централизованного ведения журналов в Skype для бизнеса Server 2015](configure-scenarios.md)

[Служба централизованного ведения журналов в Skype для бизнеса 2015](centralized-logging-service.md)

[Set-CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csclsconfiguration?view=skype-ps)

[Get-CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csclsconfiguration?view=skype-ps)

[New-CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csclsconfiguration?view=skype-ps)

[Remove-CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csclsconfiguration?view=skype-ps)
