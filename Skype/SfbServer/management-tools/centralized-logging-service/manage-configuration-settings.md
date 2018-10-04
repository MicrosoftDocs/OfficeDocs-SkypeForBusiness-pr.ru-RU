---
title: Управление параметрами конфигурации централизованной службы ведения журналов в Skype для бизнеса Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 93b9a354-9aea-4b3a-a4fe-68a89f436196
description: 'Сводка: Узнайте, как для получения, обновления и создать параметры конфигурации для службы централизованного ведения журналов в Скайп для Business Server 2015.'
ms.openlocfilehash: 62902a25e50043f2e03eda907f4ba572249b1a60
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/04/2018
ms.locfileid: "25375603"
---
# <a name="manage-centralized-logging-service-configuration-settings-in-skype-for-business-server-2015"></a>Управление параметрами конфигурации централизованной службы ведения журналов в Skype для бизнеса Server 2015

**Сводка:** Узнайте, как для получения, обновления и создать параметры конфигурации для службы централизованного ведения журналов в Скайп для Business Server 2015.

Управляемые и настроен с использованием параметров и параметров, которые создаются и используются контроллером централизованного ведения журналов службы (CLSController) для отправки команд в отдельных компьютера службы агента централизованного ведения журналов (службы централизованного ведения журналов CLSAgent). Агент обрабатывает команды, которые отправляются в нее и (при использовании команды запуска) использует конфигурации из сценариев, поставщиков, длительность трассировки и флаги для начала сбора журналов трассировки согласно сведения о конфигурации.

> [!IMPORTANT]
>  Не все командлеты Windows PowerShell, перечисленных для службы централизованного ведения журналов предназначены для использования с Скайп для развертываний локальной Business Server 2015. Несмотря на то, что они могут отображаться для работы, следующие командлеты не предназначены для работы с Скайп для развертываний локальной Business Server 2015:

-  **Командлеты CsClsRegion:** [Get-CsClsRegion](https://docs.microsoft.com/powershell/module/skype/get-csclsregion?view=skype-ps) ,[Set-CsClsRegion](https://docs.microsoft.com/powershell/module/skype/set-csclsregion?view=skype-ps), [New-CsClsRegion](https://docs.microsoft.com/powershell/module/skype/new-csclsregion?view=skype-ps)и [Remove-CsClsRegion](https://docs.microsoft.com/powershell/module/skype/remove-csclsregion?view=skype-ps).
-  **Командлеты CsClsSearchTerm:** [Get-CsClsSearchTerm](https://docs.microsoft.com/powershell/module/skype/get-csclssearchterm?view=skype-ps) и [Set-CsClsSearchTerm](https://docs.microsoft.com/powershell/module/skype/set-csclssearchterm?view=skype-ps).
-  **Командлеты CsClsSecurityGroup:** [Get-CsClsSecurityGroup](https://docs.microsoft.com/powershell/module/skype/get-csclssecuritygroup?view=skype-ps), [Set-CsClsSecurityGroup](https://docs.microsoft.com/powershell/module/skype/set-csclssecuritygroup?view=skype-ps), [New-CsClsSecurityGroup](https://docs.microsoft.com/powershell/module/skype/new-csclssecuritygroup?view=skype-ps)и [Remove-CsClsSecurityGroup](https://docs.microsoft.com/powershell/module/skype/remove-csclssecuritygroup?view=skype-ps).

Параметров, определенных в эти командлеты не мешать или стать причиной любое неблагоприятным поведение, но они предназначены для использования с помощью Microsoft Office 365 и будет дает ожидаемых результатов в локальных развертываниях. Это не означает полную бесполезность таких командлетов в локальных развертываниях, но вопрос об их использовании выходит за рамки данной документации.

Службы централизованного ведения журналов может выполняться на уровне, который включает в себя отдельный компьютер или пул компьютеров, на уровне сайта (то есть, определенного сайта например сайта Redmond, содержащее набор компьютера и пулы в развертывании) или в глобальной области (например все компьютеры и пулы в развертывании).

Настройка области действия службы централизованного ведения журналов с помощью Скайп для консоли Business Server, должна быть членом CsAdministrator или групп безопасности CsServerAdministrator доступом на основе ролей (RBAC) элемента управления или настраиваемые роли RBAC, содержит любой из этих двух групп. Чтобы получить список всех ролей RBAC, назначенных этот командлет (включая любые пользовательские роли RBAC, созданные самостоятельно), выполните следующую команду из Скайп для консоли Business Server или в командной строке Windows PowerShell:

```
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "<Skype for Business cmdlet>"}
```

Например:

```
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}
```

> [!NOTE]
> Существуют основные различия между командной строки, которые могут работать в Windows PowerShell или CLSController. Windows PowerShell предоставляет метод расширенными возможностями для настройки и определить сценарии и повторно использовать эти сценарии осмысленно для устранения неполадок сценариев. Во время CLSController обеспечивают быстрое и эффективный способ выполнения команд и получения результатов, команды, установленное для CLSController ограничивается конечный команды, у вас есть доступны из командной строки. В отличие от командлетов Windows PowerShell CLSController не может определить новые сценарии, управление область действия на сайте или глобальном уровне и многие другие ограничения набор конечное команд, не может быть настроено динамически. Хотя CLSController предоставляет средства для быстрого выполнения, Windows PowerShell служит для расширения функциональности Centralized Logging Service за рамки возможностей с CLSController.

Область отдельный компьютер может быть определен во время выполнения [Search-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/search-csclslogging?view=skype-ps), [Show-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/show-csclslogging?view=skype-ps), [Start-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/start-csclslogging?view=skype-ps), [Stop-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/stop-csclslogging?view=skype-ps), [Sync-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/sync-csclslogging?view=skype-ps) и [Update-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/update-csclslogging?view=skype-ps) команды с помощью параметра - компьютеров. -Компьютеров параметр может принимать список разделенных запятыми полные доменные имена (FQDN) конечного компьютера.

> [!TIP]
> Можно также назначить - пулов и пулов, которые необходимо выполнять команды ведения журнала на список разделенных запятыми.

Сайта и глобальной области определены в командлетах **New-** **Set -** и **Remove -** централизованной службы ведения журналов. В приведенных ниже примерах демонстрируется настройка сайта и глобальной области.

> [!IMPORTANT]
> Показанные команды могут содержать параметры и концепции, описанные в других разделах. Примеры команд предназначены для демонстрации использования **-Identity** параметр для определения области, а другие параметры включены для полноты и для определения области действия. Для получения дополнительных сведений о командлеты **Set-CsClsConfiguration** видеть [Set-CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csclsconfiguration?view=skype-ps) в документации по операциям.

### <a name="to-retrieve-the-current-centralized-logging-service-configuration"></a>Чтобы получить текущую конфигурацию централизованной службы ведения журналов

1. Запустите командную консоль Skype для бизнеса: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Skype для бизнеса 2015** и щелкните элемент **Командная консоль Skype для бизнеса**.

2. Введите следующую команду в командной строке:

   ```
   Get-CsClsConfiguration
   ```

Используйте командлеты **New-CsClsConfiguration** и **Set-CsClsConfiguration** для создания новой конфигурации или для обновления существующей конфигурации. При выполнении **Get-CsClsConfiguration**, отображает сведения, похожие на следующем рисунке, где развертывания в настоящее время имеет глобальную конфигурацию по умолчанию, но не определен конфигурации сайта:

![Выход выборки из Get-CsClsConfiguration.](../../media/Ops_Get-CsClsConfiguration_Basic.jpg)

### <a name="to-retrieve-the-current-centralized-logging-service-configuration-from-the-computer-local-store"></a>Чтобы получить текущую конфигурацию централизованной службы ведения журналов из локального хранилища компьютера

1. Запустите командную консоль Skype для бизнеса: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Skype для бизнеса 2015** и щелкните элемент **Командная консоль Skype для бизнеса**.

2. Введите следующую команду в командной строке:

   ```
   Get-CsClsConfiguration -LocalStore
   ```

При использовании первом примере где **Get-CsClsConfiguration** никакие параметры не указаны, команда ссылки хранилища для данных. Если указан параметр - LocalStore, команда ссылается на компьютере LocalStore вместо центрального хранилища управления.
### <a name="to-retrieve-a-listing-of-scenarios-currently-defined"></a>Получение списка сценариев, определенных в текущий момент

1. Запустите командную консоль Skype для бизнеса: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Skype для бизнеса 2015** и щелкните элемент **Командная консоль Skype для бизнеса**.

2. Введите следующую команду в командной строке:

   ```
   Get-CsClsConfiguration -Identity <scope and name> | Select-Object -ExpandProperty Scenarios
   ```

    Например для получения сценариев, определенных в глобальной области, выполните следующую команду.

   ```
   Get-CsClsConfiguration -Identity "global" | Select-Object -ExpandProperty Scenarios
   ```

Командлет **Get-CsClsConfiguration** всегда отображается сценариев, которые являются частью конфигурации заданной области действия. В большинстве случаев отображаются не все сценарии, кроме того, отображаемые сценарии сокращаются. Используемая здесь команда отображает список всех сценариев и частичные сведения об используемых поставщиках, настройках и флагах.
### <a name="to-update-a-global-scope-for-the-centralized-logging-service-by-using-windows-powershell"></a>Обновление глобальной области для службы централизованного ведения журналов с помощью Windows PowerShell

1. Запустите командную консоль Skype для бизнеса: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Skype для бизнеса 2015** и щелкните элемент **Командная консоль Skype для бизнеса**.

2. Введите следующую команду в командной строке:

   ```
   Set-CsClsConfiguration -Identity <scope> -EtlFileRolloverSizeMB <size for logging file in megabytes>
   ```

   Например:

   ```
   Set-CsClsConfiguration -Identity "global" -EtlFileRolloverSizeMB 40
   ```

При выполнении этой команды CLSAgent на каждом компьютере и в каждом пуле развертывания задает для размера переключения на новый файл трассировки значение 40 МБ. Эта команда влияет на компьютеры и пулы на всех сайтах и задает в качестве размера переключения на новый журнал трассировки значение 40 МБ.
### <a name="to-update-a-site-scope-for-the-centralized-logging-service-by-using-windows-powershell"></a>Обновление области сайта для службы централизованного ведения журналов с помощью Windows PowerShell

1. Запустите командную консоль Skype для бизнеса: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Skype для бизнеса 2015** и щелкните элемент **Командная консоль Skype для бизнеса**.

2. Введите следующую команду в командной строке:

   ```
   Set-CsClsConfiguration -Identity <scope/site name> -EtlFileRolloverSizeMB <size for logging file in megabytes>
   ```

   Например:

   ```
   Set-CsClsConfiguration -Identity "site/Redmond" -EtlFileRolloverSizeMB 40
   ```

> [!NOTE]
> Как отмечено в примере, расположением файлов журнала по умолчанию является каталог %TEMP%\Tracing. Однако так как фактически файл записывает CLSAgent, который выполняется как сетевая служба, переменная %TEMP% расширяется до %WINDIR%\ServiceProfiles\NetworkService\AppData\Local.

При выполнении этой команды CLSAgent на каждом компьютере и в каждом пуле сайта Redmond задает для размера переключения на новый файл трассировки значение 40 МБ. Эта команда не повлияет на компьютеры и пулы на других сайтах, которые продолжат использовать текущее значение размера переключения на новый журнал трассировки, определенное либо по умолчанию (20 МБ), либо во время запуска сеанса ведения журнала.
### <a name="to-create-a-new-centralized-logging-service-configuration"></a>Чтобы создать новую конфигурацию централизованной службы ведения журналов

1. Запустите командную консоль Skype для бизнеса: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Skype для бизнеса 2015** и щелкните элемент **Командная консоль Skype для бизнеса**.

2. Введите следующую команду в командной строке:

   ```
   New-CsClsConfiguration -Identity <scope and name> [CsClsConfiguration options for this site]
   ```

    > [!NOTE]
    > Командлет New-CsClsConfiguration предоставляет доступ к большому количеству необязательных параметров конфигурации. Для получения дополнительных сведений о параметрах конфигурации видеть [Get-CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csclsconfiguration?view=skype-ps) и [Общие сведения о централизованного ведения журналов параметры конфигурации службы](https://technet.microsoft.com/library/3c34e600-0b91-43dc-b4cc-90b6a70ee12e.aspx).

Например для создания новой конфигурации, которая определяет сетевую папку для файлов кэша, а также период и размер переключения для файлов журнала, введите следующую команду:

  ```
  New-CsClsConfiguration -Identity "site:Redmond" -CacheFileNetworkFolder "\\fs01.contoso.net\filestore\logfiles" -EtlFileRolloverMinutes 120 -EtlFileRolloverSizeMB 40
  ```

Необходимо тщательно спланировать создания новой конфигурации и определение новых свойств для службы централизованного ведения журналов. Следует соблюдать осторожность о внесении изменений и убедитесь, что понять воздействие на возможность должным образом войдите в сценарии проблемы. Следует вносить изменения в конфигурацию, расширяет возможности для управления журналы размер и точку выделения, которая позволит решения проблем при его возникает.
### <a name="to-remove-an-existing-centralized-logging-service-configuration"></a>Для удаления существующей конфигурации службы централизованного ведения журналов

1. Запустите командную консоль Skype для бизнеса: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Skype для бизнеса 2015** и щелкните элемент **Командная консоль Skype для бизнеса**.

2. Введите следующую команду в командной строке:

   ```
   Remove-CsClsConfiguration -Identity <scope and name>
   ```

К примеру Чтобы удалить конфигурацию централизованной службы ведения журналов, созданный для увеличения времени откат файлов журнала, увеличение размера файла журнала откат и задайте расположение кэша файла журнала в сетевом ресурсе, как показано ниже:

  ```
  Remove-CsClsConfiguration -Identity "site:Redmond"
  ```

> [!NOTE]
> Это новую конфигурацию, которая была создана в процедуре «Создание новой конфигурации централизованная служба ведения журнала».

Если удалить конфигурацию уровня сайта, сайт будет использовать глобальные параметры.
## <a name="see-also"></a>См. также

[Настройка поставщиков для централизованной службы ведения журналов в Skype для бизнеса Server 2015](configure-providers.md)

[Настройка сценариев для централизованной службы ведения журналов в Skype для бизнеса Server 2015](configure-scenarios.md)

[Централизованная служба ведения журнала в Skype для бизнеса 2015](centralized-logging-service.md)

[SET-CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csclsconfiguration?view=skype-ps)

[Get-CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csclsconfiguration?view=skype-ps)

[New-CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csclsconfiguration?view=skype-ps)

[Remove-CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csclsconfiguration?view=skype-ps)