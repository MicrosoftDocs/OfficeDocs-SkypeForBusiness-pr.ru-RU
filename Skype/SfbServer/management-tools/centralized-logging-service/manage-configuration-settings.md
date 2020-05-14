---
title: Управление параметрами конфигурации централизованной службы ведения журналов в Skype для бизнеса Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: Сводка. Узнайте, как получать, обновлять и создавать параметры конфигурации для централизованной службы ведения журналов в Skype для бизнеса Server 2015.
ms.openlocfilehash: ed75aab211f2d2abbf0a2007fd83e5be8bb70404
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221179"
---
# <a name="manage-centralized-logging-service-configuration-settings-in-skype-for-business-server-2015"></a>Управление параметрами конфигурации централизованной службы ведения журналов в Skype для бизнеса Server 2015

**Сводка:** Узнайте, как извлекать, обновлять и создавать параметры конфигурации для централизованной службы ведения журналов в Skype для бизнеса Server 2015.

Централизованная служба ведения журналов контролируется и настраивается параметрами и параметрами, которые создаются и используются централизованным контроллером службы ведения журналов (CLSController) для отправки команд в агент службы централизованного ведения журналов (CLSAgent) отдельного компьютера. Агент обрабатывает отправляемые им команды и (в случае команды запуска) использует конфигурацию сценариев, поставщиков, продолжительность трассировки и флаги для начала сбора журналов трассировки в соответствии с предоставленными сведениями о конфигурации.

> [!IMPORTANT]
>  Не все командлеты Windows PowerShell, перечисленные для централизованной службы ведения журналов, предназначены для использования с локальными развертываниями Skype для бизнеса Server 2015. Несмотря на то, что они могут показаться работоспособными, следующие командлеты не предназначены для работы с локальными развертываниями Skype для бизнеса Server 2015:

-  **Командлеты CsClsRegion:** [Get – CsClsRegion](https://docs.microsoft.com/powershell/module/skype/get-csclsregion?view=skype-ps) ,[Set — CsClsRegion](https://docs.microsoft.com/powershell/module/skype/set-csclsregion?view=skype-ps), [New CsClsRegion](https://docs.microsoft.com/powershell/module/skype/new-csclsregion?view=skype-ps)и [Remove – CsClsRegion](https://docs.microsoft.com/powershell/module/skype/remove-csclsregion?view=skype-ps).
-  **Командлеты CsClsSearchTerm:** [Get-CsClsSearchTerm](https://docs.microsoft.com/powershell/module/skype/get-csclssearchterm?view=skype-ps) и [Set-CsClsSearchTerm](https://docs.microsoft.com/powershell/module/skype/set-csclssearchterm?view=skype-ps).
-  **Командлеты CsClsSecurityGroup:** [Get – CsClsSecurityGroup](https://docs.microsoft.com/powershell/module/skype/get-csclssecuritygroup?view=skype-ps), [Set — CsClsSecurityGroup](https://docs.microsoft.com/powershell/module/skype/set-csclssecuritygroup?view=skype-ps), [New CsClsSecurityGroup](https://docs.microsoft.com/powershell/module/skype/new-csclssecuritygroup?view=skype-ps)и [Remove – CsClsSecurityGroup](https://docs.microsoft.com/powershell/module/skype/remove-csclssecuritygroup?view=skype-ps).

Параметры, определенные в этих командлетах, не мешают или не вызывают каких – либо неблагоприятных поведений, но они предназначены для использования с Microsoft 365 или Office 365 и не будут давать ожидаемые результаты в локальных развертываниях. Это не означает полную бесполезность таких командлетов в локальных развертываниях, но вопрос об их использовании выходит за рамки данной документации.

Централизованную службу ведения журналов можно запустить в области, которая включает один компьютер или пул компьютеров, на уровне сайта (то есть, определенного сайта, такого как Redmond сайта, содержащего коллекцию компьютеров и пулов в развертывании) или в глобальной области (то есть на всех компьютерах и в пулах в развертывании).

Чтобы настроить область Службы централизованного ведения журналов с помощью командной консоли Skype для бизнеса Server, необходимо быть членом группы безопасности CsAdministrator или CsServerAdministrator с управлением доступом на основе ролей (RBAC) или настраиваемой роли RBAC, которая содержит любую из этих двух групп. Чтобы получить список всех ролей RBAC, которым назначен этот командлет (включая все самостоятельно созданные роли RBAC), выполните следующую команду в командной консоли Skype для бизнеса Server или в командной строке Windows PowerShell:

```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "<Skype for Business cmdlet>"}
```

Например:

```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}
```

> [!NOTE]
> Существуют фундаментальные различия между командами командной строки, которые можно запускать в Windows PowerShell или CLSController. Windows PowerShell предоставляет богатый метод настройки и определения сценариев, а также повторное использование этих сценариев для сценариев устранения неполадок. Хотя CLSController позволяет быстро и эффективно выполнять команды и получать результаты, набор команд этого средства ограничен командами, доступными из командной строки. В отличие от командлетов Windows PowerShell, CLSController не может определять новые сценарии, управлять областью на сайте или глобальном уровне, а также многие другие ограничения набора команд, которые не могут быть настроены динамически. Хотя CLSController предоставляет средства для быстрого выполнения, Windows PowerShell предоставляет средства для расширения функциональности централизованной службы ведения журналов помимо того, что возможно в CLSController.

Область одного компьютера можно определить во время выполнения команды [Search — CsClsLogging](https://docs.microsoft.com/powershell/module/skype/search-csclslogging?view=skype-ps), [Show CsClsLogging](https://docs.microsoft.com/powershell/module/skype/show-csclslogging?view=skype-ps), [Start — CsClsLogging](https://docs.microsoft.com/powershell/module/skype/start-csclslogging?view=skype-ps), [Stop CsClsLogging](https://docs.microsoft.com/powershell/module/skype/stop-csclslogging?view=skype-ps), [Sync – CsClsLogging](https://docs.microsoft.com/powershell/module/skype/sync-csclslogging?view=skype-ps) и [Update/CsClsLogging](https://docs.microsoft.com/powershell/module/skype/update-csclslogging?view=skype-ps) с помощью параметра – Computers. Параметр-Computers принимает разделенный запятыми список полных доменных имен (FQDN) конечного компьютера.

> [!TIP]
> Кроме того, можно определить пулы и разделенные запятыми список пулов, в которых будут выполняться команды ведения журнала.

Сайты и глобальные области определены в командлетах службы ведения журналов **New-**, **Set-** и **Remove-** централизованный. В следующих примерах показано, как задать область сайта и глобальную область.

> [!IMPORTANT]
> Показанные команды могут содержать параметры и концепции, описанные в других разделах. Примеры команд предназначены для демонстрации использования параметра **– Identity** для определения области, а другие параметры — для полноты и указания области. Дополнительные сведения о командлетах **Set-CsClsConfiguration** см. в описании командлета [Set-CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csclsconfiguration?view=skype-ps) в документации по применению.

### <a name="to-retrieve-the-current-centralized-logging-service-configuration"></a>Получение текущей конфигурации централизованной службы ведения журналов

1. Запустите консоль управления Skype для бизнеса Server: нажмите кнопку **Пуск**, последовательно выберите **все программы**, **Skype для бизнеса 2015**и щелкните **Командная консоль Skype для бизнеса Server**.

2. Введите следующую команду в командной строке:

   ```PowerShell
   Get-CsClsConfiguration
   ```

Используйте командлеты **New – CsClsConfiguration** и **Set – CsClsConfiguration** для создания новой конфигурации или для обновления существующей конфигурации. При выполнении командлета **Get-CsClsConfiguration**отображаются сведения, аналогичные приведенным на следующем снимке экрана, где в настоящее время развертывание содержит глобальную конфигурацию по умолчанию, но не определено ни одной конфигурации сайта:

![Пример выходных данных Get – CsClsConfiguration.](../../media/Ops_Get-CsClsConfiguration_Basic.jpg)

### <a name="to-retrieve-the-current-centralized-logging-service-configuration-from-the-computer-local-store"></a>Получение текущей конфигурации централизованной службы ведения журналов из локального хранилища компьютера

1. Запустите консоль управления Skype для бизнеса Server: нажмите кнопку **Пуск**, последовательно выберите **все программы**, **Skype для бизнеса 2015**и щелкните **Командная консоль Skype для бизнеса Server**.

2. Введите следующую команду в командной строке:

   ```PowerShell
   Get-CsClsConfiguration -LocalStore
   ```

При использовании первого примера, когда **Get – CsClsConfiguration** не задает параметры, команда ссылается на центральное хранилище управления данными. Если указать параметр – Локалсторе, команда будет ссылаться на компьютер Локалсторе вместо центрального хранилища управления.
### <a name="to-retrieve-a-listing-of-scenarios-currently-defined"></a>Получение листинга сценариев, определенных в текущий момент

1. Запустите консоль управления Skype для бизнеса Server: нажмите кнопку **Пуск**, последовательно выберите **все программы**, **Skype для бизнеса 2015**и щелкните **Командная консоль Skype для бизнеса Server**.

2. Введите следующую команду в командной строке:

   ```PowerShell
   Get-CsClsConfiguration -Identity <scope and name> | Select-Object -ExpandProperty Scenarios
   ```

    Например, для получения сценариев, определенных в глобальной области, выполните следующую команду.

   ```PowerShell
   Get-CsClsConfiguration -Identity "global" | Select-Object -ExpandProperty Scenarios
   ```

Командлет **Get – CsClsConfiguration** всегда отображает сценарии, которые являются частью конфигурации данной области. В большинстве случаев отображаются не все сценарии, кроме того, отображаемые сценарии сокращаются. Используемая здесь команда отображает список всех сценариев и частичные сведения об используемых поставщиках, настройках и флагах.
### <a name="to-update-a-global-scope-for-the-centralized-logging-service-by-using-windows-powershell"></a>Обновление глобальной области для централизованной службы ведения журналов с помощью Windows PowerShell

1. Запустите консоль управления Skype для бизнеса Server: нажмите кнопку **Пуск**, последовательно выберите **все программы**, **Skype для бизнеса 2015**и щелкните **Командная консоль Skype для бизнеса Server**.

2. Введите следующую команду в командной строке:

   ```PowerShell
   Set-CsClsConfiguration -Identity <scope> -EtlFileRolloverSizeMB <size for logging file in megabytes>
   ```

   Пример:

   ```PowerShell
   Set-CsClsConfiguration -Identity "global" -EtlFileRolloverSizeMB 40
   ```

При выполнении этой команды CLSAgent на каждом компьютере и в каждом пуле развертывания задает для размера переключения на новый файл трассировки значение 40 МБ. Эта команда влияет на компьютеры и пулы на всех сайтах и задает в качестве размера переключения на новый журнал трассировки значение 40 МБ.
### <a name="to-update-a-site-scope-for-the-centralized-logging-service-by-using-windows-powershell"></a>Обновление области сайта для централизованной службы ведения журналов с помощью Windows PowerShell

1. Запустите консоль управления Skype для бизнеса Server: нажмите кнопку **Пуск**, последовательно выберите **все программы**, **Skype для бизнеса 2015**и щелкните **Командная консоль Skype для бизнеса Server**.

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
### <a name="to-create-a-new-centralized-logging-service-configuration"></a>Создание новой конфигурации централизованной службы ведения журналов

1. Запустите консоль управления Skype для бизнеса Server: нажмите кнопку **Пуск**, последовательно выберите **все программы**, **Skype для бизнеса 2015**и щелкните **Командная консоль Skype для бизнеса Server**.

2. Введите следующую команду в командной строке:

   ```PowerShell
   New-CsClsConfiguration -Identity <scope and name> [CsClsConfiguration options for this site]
   ```

    > [!NOTE]
    > Командлет New-CsClsConfiguration предоставляет доступ к большому количеству необязательных параметров конфигурации. Сведения о параметрах конфигурации приведены в статье [Get – CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csclsconfiguration?view=skype-ps) и [сведения о параметрах конфигурации службы централизованного ведения журналов](https://technet.microsoft.com/library/3c34e600-0b91-43dc-b4cc-90b6a70ee12e.aspx).

Например, для создания новой конфигурации, которая определяет сетевую папку для файлов кэша, а также период и размер переключения для файлов журнала, введите следующую команду:

  ```PowerShell
  New-CsClsConfiguration -Identity "site:Redmond" -CacheFileNetworkFolder "\\fs01.contoso.net\filestore\logfiles" -EtlFileRolloverMinutes 120 -EtlFileRolloverSizeMB 40
  ```

Следует тщательно спланировать создание новых конфигураций и определить новые свойства централизованной службы ведения журналов. Необходимо проявлять осторожность при изменениях и учитывать их влияние на возможность правильного ведения журналов в проблемных сценариях. В конфигурацию следует вносить такие изменения, которые улучшат возможности управления журналами и позволят задать такие значения размера и периода переключения, которые помогут устранить возможные проблемы.
### <a name="to-remove-an-existing-centralized-logging-service-configuration"></a>Удаление существующей конфигурации централизованной службы ведения журналов

1. Запустите консоль управления Skype для бизнеса Server: нажмите кнопку **Пуск**, последовательно выберите **все программы**, **Skype для бизнеса 2015**и щелкните **Командная консоль Skype для бизнеса Server**.

2. Введите следующую команду в командной строке:

   ```PowerShell
   Remove-CsClsConfiguration -Identity <scope and name>
   ```

Например, чтобы удалить созданную конфигурацию централизованной службы ведения журналов, чтобы увеличить время переключения файла журнала, увеличьте размер файла журнала продолжения и установите для расположения кэша файлов журнала следующий сетевой ресурс:

  ```PowerShell
  Remove-CsClsConfiguration -Identity "site:Redmond"
  ```

> [!NOTE]
> Это новая конфигурация, созданная в процедуре "Создание новой конфигурации централизованной службы ведения журналов".

Если удалить конфигурацию уровня сайта, сайт будет использовать глобальные параметры.
## <a name="see-also"></a>См. также

[Настройка поставщиков для централизованной службы ведения журналов в Skype для бизнеса Server 2015](configure-providers.md)

[Настройка сценариев для централизованной службы ведения журналов в Skype для бизнеса Server 2015](configure-scenarios.md)

[Централизованная служба ведения журналов в Skype для бизнеса 2015](centralized-logging-service.md)

[Set — CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csclsconfiguration?view=skype-ps)

[Get — CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csclsconfiguration?view=skype-ps)

[New — CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csclsconfiguration?view=skype-ps)

[Remove — CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csclsconfiguration?view=skype-ps)
