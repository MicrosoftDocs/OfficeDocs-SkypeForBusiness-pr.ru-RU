---
title: Управление настройками централизованной службы ведения журнала в Skype для бизнеса Server 2015 г.
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 8/17/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 93b9a354-9aea-4b3a-a4fe-68a89f436196
description: Сводка. Сведения о том, как получить, обновить и создать параметры конфигурации для централизированной службы ведения журнала в Skype для бизнеса Server 2015 г.
ms.openlocfilehash: 27202b870ba0115f045eda367619a449b307e708
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/08/2021
ms.locfileid: "60831933"
---
# <a name="manage-centralized-logging-service-configuration-settings-in-skype-for-business-server-2015"></a>Управление настройками централизованной службы ведения журнала в Skype для бизнеса Server 2015 г.

**Сводка:** Узнайте, как получить, обновить и создать параметры конфигурации для централизированной службы ведения журнала в Skype для бизнеса Server 2015 г.

Централизованная служба ведения журнала управляется и настраивается параметрами, созданными и используемыми диспетчером централизованной службы ведения журнала (CLSController) для отправки команд агенту централизованной службы ведения журнала на отдельном компьютере (CLSAgent). Агент обрабатывает команды, отправленные ему, и (в случае команды Начните) использует конфигурацию сценариев, поставщиков, продолжительность трассировки и флаги, чтобы начать сбор журналов трассировки в соответствии с предоставленной информацией о конфигурации.

> [!IMPORTANT]
>  Не все Windows PowerShell, перечисленные для централизированной службы ведения журнала, предназначены для Skype для бизнеса Server локального развертывания 2015 г. Несмотря на то, что они могут показаться работой, следующие cmdlets не предназначены для работы с Skype для бизнеса Server 2015 на локальном развертывании:

-  **CsClsRegion cmdlets:** [Get-CsClsRegion](/powershell/module/skype/get-csclsregion?view=skype-ps) ,[Set-CsClsRegion](/powershell/module/skype/set-csclsregion?view=skype-ps), [New-CsClsRegion](/powershell/module/skype/new-csclsregion?view=skype-ps)и [Remove-CsClsRegion](/powershell/module/skype/remove-csclsregion?view=skype-ps).
-  **Cmdlets CsClsSearchTerm:** [Get-CsClsSearchTerm](/powershell/module/skype/get-csclssearchterm?view=skype-ps) и [Set-CsClsSearchTerm](/powershell/module/skype/set-csclssearchterm?view=skype-ps).
-  **Группы CsClsSecurityGroup:** [Get-CsClsSecurityGroup,](/powershell/module/skype/get-csclssecuritygroup?view=skype-ps) [Set-CsClsSecurityGroup,](/powershell/module/skype/set-csclssecuritygroup?view=skype-ps)  [New-CsClsSecurityGroup](/powershell/module/skype/new-csclssecuritygroup?view=skype-ps)и [Remove-CsClsSecurityGroup](/powershell/module/skype/remove-csclssecuritygroup?view=skype-ps).

Параметры, определенные в этих cmdlets, не будут препятствовать или вызывать любое неблагоприятное поведение, но они предназначены для Microsoft 365 или Office 365 и не привнося ожидаемых результатов в локальном развертывании. Это не означает полную бесполезность таких командлетов в локальных развертываниях, но вопрос об их использовании выходит за рамки данной документации.

Централизованная служба ведения журнала может работать в области, которая включает один компьютер или пул компьютеров, в области сайта (то есть определенном сайте, например на сайте Redmond, который содержит коллекцию компьютеров и пулов в развертывании), или в глобальной области (то есть всех компьютерах и пулах в развертывании).

Чтобы настроить область централизованной службы ведения журнала с помощью Skype для бизнеса Server Management Shell, необходимо быть членом группы безопасности CsAdministrator или CsServerAdministrator для управления ролями (RBAC) или настраиваемой роли RBAC, которая содержит обе эти две группы. Чтобы вернуть список всех ролей RBAC, на которые был назначен этот командлет (включая настраиваемые роли RBAC, созданные самостоятельно), запустите следующую команду из командной Skype для бизнеса Server или Windows PowerShell запроса:

```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "<Skype for Business cmdlet>"}
```

Например:

```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}
```

> [!NOTE]
> Существуют фундаментальные различия между командами командной строки, которые можно выполнить в Windows PowerShell CLSController. Windows PowerShell предоставляет богатый метод для настройки и определения сценариев, а также для повторного использования этих сценариев значимым образом для сценариев устранения неполадок. Хотя CLSController позволяет быстро и эффективно выполнять команды и получать результаты, набор команд этого средства ограничен командами, доступными из командной строки. В отличие Windows PowerShell командлетов CLSController не может определять новые сценарии, управлять областью на сайте или глобальном уровне и многими другими ограничениями конечного командного набора, который невозможно динамически настроить. Хотя CLSController предоставляет средство для быстрого выполнения, Windows PowerShell предоставляет средства для расширения функций службы централизованного ведения журнала за пределами возможностей CLSController.

При выполнении команды [Search-CsClsLogging,](/powershell/module/skype/search-csclslogging?view=skype-ps) [Show-CsClsLogging,](/powershell/module/skype/show-csclslogging?view=skype-ps) [Start-CsClsLogging,](/powershell/module/skype/start-csclslogging?view=skype-ps) [Stop-CsClsLogging,](/powershell/module/skype/stop-csclslogging?view=skype-ps) [Sync-CsClsLogging](/powershell/module/skype/sync-csclslogging?view=skype-ps) и [Update-CsClsLogging](/powershell/module/skype/update-csclslogging?view=skype-ps) можно определить один компьютер. Параметр -Computers принимает разделенный запятой список полностью квалифицированных доменных имен (FQDNs) для целевого компьютера.

> [!TIP]
> Вы также можете определить пулы и разделенный запятой список пулов, на которые необходимо выполнить команды ведения журнала.

Области site и Global определяются в октах **New-**, **Set-** и **Remove-Centralized** Logging Service. В следующих примерах показано, как задать область сайта и глобальную область.

> [!IMPORTANT]
> Показанные команды могут содержать параметры и концепции, описанные в других разделах. Команды в примере предназначены для демонстрации использования параметра **-Identity** для определения области, а остальные параметры включаются для полноты и для указания области. Дополнительные сведения о командлетах **Set-CsClsConfiguration** см. в описании командлета [Set-CsClsConfiguration](/powershell/module/skype/set-csclsconfiguration?view=skype-ps) в документации по применению.

### <a name="to-retrieve-the-current-centralized-logging-service-configuration"></a>Чтобы получить текущую конфигурацию централизованной службы ведения журнала

1. Запустите Skype для бизнеса Server: нажмите кнопку Начните, щелкните Все **программы,** нажмите кнопку Skype для бизнеса **2015,** а затем нажмите кнопку **Skype для бизнеса Server.**

2. Введите следующую команду в командной строке:

   ```PowerShell
   Get-CsClsConfiguration
   ```

Для создания новой конфигурации или обновления существующей конфигурации используйте комлеты **New-CsClsConfiguration** и **Set-CsClsConfiguration.** При запуске **Get-CsClsConfiguration** отображаются сведения, аналогичные следующему снимку экрана, где развертывание в настоящее время имеет глобальную конфигурацию по умолчанию, но конфигурации сайтов не определены:

![Пример вывода get-CsClsConfiguration.](../../media/Ops_Get-CsClsConfiguration_Basic.jpg)

### <a name="to-retrieve-the-current-centralized-logging-service-configuration-from-the-computer-local-store"></a>Извлечение текущей конфигурации централизованной службы ведения журнала из локального магазина компьютера

1. Запустите Skype для бизнеса Server: нажмите кнопку Начните, щелкните Все **программы,** нажмите кнопку Skype для бизнеса **2015,** а затем нажмите кнопку **Skype для бизнеса Server.**

2. Введите следующую команду в командной строке:

   ```PowerShell
   Get-CsClsConfiguration -LocalStore
   ```

При использовании первого примера, в котором **Get-CsClsConfiguration** не указывает никаких параметров, команда ссылается на центральный хранилище управления данными. Если указать параметр -LocalStore, команда ссылается на компьютер LocalStore, а не на центральный магазин управления.
### <a name="to-retrieve-a-listing-of-scenarios-currently-defined"></a>Получение листинга сценариев, определенных в текущий момент

1. Запустите Skype для бизнеса Server: нажмите кнопку Начните, щелкните Все **программы,** нажмите кнопку Skype для бизнеса **2015,** а затем нажмите кнопку **Skype для бизнеса Server.**

2. Введите следующую команду в командной строке:

   ```PowerShell
   Get-CsClsConfiguration -Identity <scope and name> | Select-Object -ExpandProperty Scenarios
   ```

    Например, для получения сценариев, определенных в глобальной области, выполните следующую команду.

   ```PowerShell
   Get-CsClsConfiguration -Identity "global" | Select-Object -ExpandProperty Scenarios
   ```

В cmdlet **Get-CsClsConfiguration** всегда отображаются сценарии, которые являются частью конфигурации данной области. В большинстве случаев отображаются не все сценарии, кроме того, отображаемые сценарии сокращаются. Используемая здесь команда отображает список всех сценариев и частичные сведения об используемых поставщиках, настройках и флагах.
### <a name="to-update-a-global-scope-for-the-centralized-logging-service-by-using-windows-powershell"></a>Обновление глобальной области для централизированной службы ведения журнала с помощью Windows PowerShell

1. Запустите Skype для бизнеса Server: нажмите кнопку Начните, щелкните Все **программы,** нажмите кнопку Skype для бизнеса **2015,** а затем нажмите кнопку **Skype для бизнеса Server.**

2. Введите следующую команду в командной строке:

   ```PowerShell
   Set-CsClsConfiguration -Identity <scope> -EtlFileRolloverSizeMB <size for logging file in megabytes>
   ```

   Пример:

   ```PowerShell
   Set-CsClsConfiguration -Identity "global" -EtlFileRolloverSizeMB 40
   ```

При выполнении этой команды CLSAgent на каждом компьютере и в каждом пуле развертывания задает для размера переключения на новый файл трассировки значение 40 МБ. Эта команда влияет на компьютеры и пулы на всех сайтах и задает в качестве размера переключения на новый журнал трассировки значение 40 МБ.
### <a name="to-update-a-site-scope-for-the-centralized-logging-service-by-using-windows-powershell"></a>Обновление области сайта для централизированной службы ведения журнала с помощью Windows PowerShell

1. Запустите Skype для бизнеса Server: нажмите кнопку Начните, щелкните Все **программы,** нажмите кнопку Skype для бизнеса **2015,** а затем нажмите кнопку **Skype для бизнеса Server.**

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
### <a name="to-create-a-new-centralized-logging-service-configuration"></a>Создание новой конфигурации централизованной службы ведения журнала

1. Запустите Skype для бизнеса Server: нажмите кнопку Начните, щелкните Все **программы,** нажмите кнопку Skype для бизнеса **2015,** а затем нажмите кнопку **Skype для бизнеса Server.**

2. Введите следующую команду в командной строке:

   ```PowerShell
   New-CsClsConfiguration -Identity <scope and name> [CsClsConfiguration options for this site]
   ```

    > [!NOTE]
    > Командлет New-CsClsConfiguration предоставляет доступ к большому количеству необязательных параметров конфигурации. Сведения о параметрах конфигурации см. в [материале Get-CsClsConfiguration](/powershell/module/skype/get-csclsconfiguration?view=skype-ps) and [Understanding Centralized Logging Service Configuration Параметры.](/previous-versions/office/lync-server-2013/lync-server-2013-understanding-centralized-logging-service-configuration-settings)

Например, для создания новой конфигурации, которая определяет сетевую папку для файлов кэша, а также период и размер переключения для файлов журнала, введите следующую команду:

  ```PowerShell
  New-CsClsConfiguration -Identity "site:Redmond" -CacheFileNetworkFolder "\\fs01.contoso.net\filestore\logfiles" -EtlFileRolloverMinutes 120 -EtlFileRolloverSizeMB 40
  ```

Необходимо тщательно спланировать создание новых конфигураций и определить новые свойства для централизированной службы ведения журнала. Необходимо проявлять осторожность при изменениях и учитывать их влияние на возможность правильного ведения журналов в проблемных сценариях. В конфигурацию следует вносить такие изменения, которые улучшат возможности управления журналами и позволят задать такие значения размера и периода переключения, которые помогут устранить возможные проблемы.
### <a name="to-remove-an-existing-centralized-logging-service-configuration"></a>Удаление существующей конфигурации централизованной службы ведения журнала

1. Запустите Skype для бизнеса Server: нажмите кнопку Начните, щелкните Все **программы,** нажмите кнопку Skype для бизнеса **2015,** а затем нажмите кнопку **Skype для бизнеса Server.**

2. Введите следующую команду в командной строке:

   ```PowerShell
   Remove-CsClsConfiguration -Identity <scope and name>
   ```

Например, чтобы удалить конфигурацию службы централизованного ведения журнала, созданную для увеличения времени опрокидываемого файла журнала, увеличить размер файла журнала опрокидывательных журналов и установить расположение кэша файла журнала в сетевой совместной сети следующим образом:

  ```PowerShell
  Remove-CsClsConfiguration -Identity "site:Redmond"
  ```

> [!NOTE]
> Это новая конфигурация, созданная в процедуре "Создание новой конфигурации централизованной службы ведения журнала".

Если удалить конфигурацию уровня сайта, сайт будет использовать глобальные параметры.
## <a name="see-also"></a>См. также

[Настройка поставщиков для централизованной службы ведения журнала в Skype для бизнеса Server 2015 г.](configure-providers.md)

[Настройка сценариев для централизованной службы ведения журнала в Skype для бизнеса Server 2015 г.](configure-scenarios.md)

[Централизованная служба ведения журнала в Skype для бизнеса 2015 г.](centralized-logging-service.md)

[Set-CsClsConfiguration](/powershell/module/skype/set-csclsconfiguration?view=skype-ps)

[Get-CsClsConfiguration](/powershell/module/skype/get-csclsconfiguration?view=skype-ps)

[New-CsClsConfiguration](/powershell/module/skype/new-csclsconfiguration?view=skype-ps)

[Remove-CsClsConfiguration](/powershell/module/skype/remove-csclsconfiguration?view=skype-ps)