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
description: 'Сводка: сведения о том, как извлекать, обновлять и создавать параметры конфигурации для централизованной службы ведения журналов в Skype для бизнеса Server 2015.'
ms.openlocfilehash: 95aa05cfcd31acda8e78927d674f3a19dff7ef56
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816588"
---
# <a name="manage-centralized-logging-service-configuration-settings-in-skype-for-business-server-2015"></a>Управление параметрами конфигурации централизованной службы ведения журналов в Skype для бизнеса Server 2015

**Сводка:** Сведения о том, как извлекать, обновлять и создавать параметры конфигурации для централизованной службы ведения журналов в Skype для бизнеса Server 2015.

Централизованная служба ведения журнала контролируется и настраивается с помощью параметров и параметров, создаваемых и используемых централизованным контроллером службы ведения журналов (Клсконтроллер), для отправки команд агенту службы ведения журнала для отдельного компьютера ( Клсажент). The agent processes the commands that are sent to it and (in the case of a Start command) uses the configuration of the scenarios, providers, trace duration, and flags to begin collecting trace logs according to the configuration information provided.

> [!IMPORTANT]
>  Не все командлеты Windows PowerShell, указанные для централизованной службы ведения журналов, предназначены для использования с локальными развертываниями в Skype для бизнеса Server 2015. Несмотря на то, что они могут работать, следующие командлеты не предназначены для работы с локальными развертываниями в Skype для бизнеса Server 2015.

-  **Командлеты ксклсрегион:** [Get-ксклсрегион](https://docs.microsoft.com/powershell/module/skype/get-csclsregion?view=skype-ps) ,[Set-ксклсрегион](https://docs.microsoft.com/powershell/module/skype/set-csclsregion?view=skype-ps), [New-ксклсрегион](https://docs.microsoft.com/powershell/module/skype/new-csclsregion?view=skype-ps)и [Remove-ксклсрегион](https://docs.microsoft.com/powershell/module/skype/remove-csclsregion?view=skype-ps).
-  **Командлеты ксклссеарчтерм:** [Get-ксклссеарчтерм](https://docs.microsoft.com/powershell/module/skype/get-csclssearchterm?view=skype-ps) и [Set-ксклссеарчтерм](https://docs.microsoft.com/powershell/module/skype/set-csclssearchterm?view=skype-ps).
-  **Командлеты ксклссекуритиграуп:** [Get-ксклссекуритиграуп](https://docs.microsoft.com/powershell/module/skype/get-csclssecuritygroup?view=skype-ps), [Set-ксклссекуритиграуп](https://docs.microsoft.com/powershell/module/skype/set-csclssecuritygroup?view=skype-ps), [New-ксклссекуритиграуп](https://docs.microsoft.com/powershell/module/skype/new-csclssecuritygroup?view=skype-ps)и [Remove-ксклссекуритиграуп](https://docs.microsoft.com/powershell/module/skype/remove-csclssecuritygroup?view=skype-ps).

Параметры, определенные в этих командлетах, не мешают или не вызывают какое-либо неотрицательное поведение, но они предназначены для работы с Microsoft Office 365 и не будут давать ожидаемые результаты в локальных развертываниях. Это не означает полную бесполезность таких командлетов в локальных развертываниях, но вопрос об их использовании выходит за рамки данной документации.

Централизованная служба ведения журнала может выполняться в области, содержащей один компьютер или группу компьютеров, на уровне сайта (определенного сайта, например Redmond, который содержит коллекцию компьютеров и пулов в развертывании), или в глобальной области (то есть , все компьютеры и пулы в развертывании).

Чтобы настроить централизованную службу ведения журналов с помощью командной консоли Skype для бизнеса Server, необходимо быть членом либо в Ксадминистратор, либо в группах безопасности управления доступом на основе ролей Кссерверадминистратор (RBAC) или настраиваемой роли RBAC, которая один из этих двух групп. Чтобы возвратить список всех ролей RBAC, которым был назначен этот командлет (включая любые пользовательские роли RBAC, созданные пользователем), выполните следующую команду в командной консоли управления Skype для бизнеса Server или Windows PowerShell.

```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "<Skype for Business cmdlet>"}
```

Например:

```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}
```

> [!NOTE]
> Существуют фундаментальные различия между командами командной строки, которые можно выполнять в Windows PowerShell или Клсконтроллер. Windows PowerShell предоставляет богатый способ настройки и определения сценариев, а также повторно использовать эти сценарии для сценариев устранения неполадок. While CLSController does provide a fast and efficient way to issue commands and get results, the command set for CLSController is limited by the finite commands that you have available from the command line. В отличие от командлетов Windows PowerShell, Клсконтроллер не может определять новые сценарии, управлять областью на сайте или глобальном уровне и многие другие ограничения набора команд, которые не могут быть настроены динамически. Несмотря на то, что Клсконтроллер предоставляет средства для быстрого выполнения, Windows PowerShell предоставляет средства для продления функций централизованной службы ведения журналов, помимо возможностей, возможных для Клсконтроллер.

В ходе выполнения команды [Поиск — ксклслоггинг](https://docs.microsoft.com/powershell/module/skype/search-csclslogging?view=skype-ps), [Показать-ксклслоггинг](https://docs.microsoft.com/powershell/module/skype/show-csclslogging?view=skype-ps), [Start-](https://docs.microsoft.com/powershell/module/skype/start-csclslogging?view=skype-ps) [ксклслоггинг](https://docs.microsoft.com/powershell/module/skype/stop-csclslogging?view=skype-ps), [Sync-ксклслоггинг](https://docs.microsoft.com/powershell/module/skype/sync-csclslogging?view=skype-ps) и [Update-ксклслоггинг](https://docs.microsoft.com/powershell/module/skype/update-csclslogging?view=skype-ps) может быть определена отдельная область компьютера с помощью параметра-Computers. Параметр-Computers принимает список полных доменных имен (FQDN) для целевого компьютера, разделенный запятыми.

> [!TIP]
> Вы также можете определить пулы и список разделенных запятыми пулов, для которых нужно выполнить команды ведения журнала.

В командлетах служб ведения журналов для **создания**и **удаления** сайтов определены **** сайты и глобальные области. The following examples demonstrate how to set a site and a global scope.

> [!IMPORTANT]
> Показанные команды могут содержать параметры и концепции, описанные в других разделах. В примерах команд используются параметры **-Identity** , определяющие область, а также другие параметры, которые используются для полноты и для указания области. Дополнительные сведения о командлетах **Set-CsClsConfiguration** см. в описании командлета [Set-CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csclsconfiguration?view=skype-ps) в документации по применению.

### <a name="to-retrieve-the-current-centralized-logging-service-configuration"></a>Чтобы получить текущую конфигурацию централизованной службы ведения журнала

1. Запустите командную консоль Skype для бизнеса: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Skype для бизнеса 2015** и щелкните элемент **Командная консоль Skype для бизнеса**.

2. Введите следующую команду в командной строке:

   ```PowerShell
   Get-CsClsConfiguration
   ```

Используйте командлеты **New-ксклсконфигуратион** и **Set-ксклсконфигуратион** для создания новой конфигурации или обновления существующей конфигурации. При запуске **Get-ксклсконфигуратион**на экран выводится информация, показанная на следующем снимке экрана, в которой в настоящее время развертывание имеет глобальную конфигурацию по умолчанию, но не определена конфигурация сайта.

![Выход выборки из Get-CsClsConfiguration.](../../media/Ops_Get-CsClsConfiguration_Basic.jpg)

### <a name="to-retrieve-the-current-centralized-logging-service-configuration-from-the-computer-local-store"></a>Чтобы получить текущую конфигурацию централизованной службы ведения журналов из локального магазина компьютера

1. Запустите командную консоль Skype для бизнеса: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Skype для бизнеса 2015** и щелкните элемент **Командная консоль Skype для бизнеса**.

2. Введите следующую команду в командной строке:

   ```PowerShell
   Get-CsClsConfiguration -LocalStore
   ```

При использовании первого примера, где **Get-ксклсконфигуратион** не задает параметры, команда ссылается на центральное хранилище для управления данными. Если указать параметр-Локалсторе, команда будет ссылаться на компьютер Локалсторе вместо центрального хранилища.
### <a name="to-retrieve-a-listing-of-scenarios-currently-defined"></a>Получение списка сценариев, определенных в текущий момент

1. Запустите командную консоль Skype для бизнеса: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Skype для бизнеса 2015** и щелкните элемент **Командная консоль Skype для бизнеса**.

2. Введите следующую команду в командной строке:

   ```PowerShell
   Get-CsClsConfiguration -Identity <scope and name> | Select-Object -ExpandProperty Scenarios
   ```

    Например для получения сценариев, определенных в глобальной области, выполните следующую команду.

   ```PowerShell
   Get-CsClsConfiguration -Identity "global" | Select-Object -ExpandProperty Scenarios
   ```

Командлет **Get-ксклсконфигуратион** всегда показывает сценарии, которые являются частью конфигурации данной области. В большинстве случаев отображаются не все сценарии, кроме того, отображаемые сценарии сокращаются. Используемая здесь команда отображает список всех сценариев и частичные сведения об используемых поставщиках, настройках и флагах.
### <a name="to-update-a-global-scope-for-the-centralized-logging-service-by-using-windows-powershell"></a>Обновление глобальной области для централизованной службы ведения журналов с помощью Windows PowerShell

1. Запустите командную консоль Skype для бизнеса: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Skype для бизнеса 2015** и щелкните элемент **Командная консоль Skype для бизнеса**.

2. Введите следующую команду в командной строке:

   ```PowerShell
   Set-CsClsConfiguration -Identity <scope> -EtlFileRolloverSizeMB <size for logging file in megabytes>
   ```

   Например:

   ```PowerShell
   Set-CsClsConfiguration -Identity "global" -EtlFileRolloverSizeMB 40
   ```

При выполнении этой команды CLSAgent на каждом компьютере и в каждом пуле развертывания задает для размера переключения на новый файл трассировки значение 40 МБ. Эта команда влияет на компьютеры и пулы на всех сайтах и задает в качестве размера переключения на новый журнал трассировки значение 40 МБ.
### <a name="to-update-a-site-scope-for-the-centralized-logging-service-by-using-windows-powershell"></a>Обновление области сайта для централизованной службы ведения журналов с помощью Windows PowerShell

1. Запустите командную консоль Skype для бизнеса: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Skype для бизнеса 2015** и щелкните элемент **Командная консоль Skype для бизнеса**.

2. Введите следующую команду в командной строке:

   ```PowerShell
   Set-CsClsConfiguration -Identity <scope/site name> -EtlFileRolloverSizeMB <size for logging file in megabytes>
   ```

   Например:

   ```PowerShell
   Set-CsClsConfiguration -Identity "site/Redmond" -EtlFileRolloverSizeMB 40
   ```

> [!NOTE]
> Как отмечено в примере, расположением файлов журнала по умолчанию является каталог %TEMP%\Tracing. Однако так как фактически файл записывает CLSAgent, который выполняется как сетевая служба, переменная %TEMP% расширяется до %WINDIR%\ServiceProfiles\NetworkService\AppData\Local.

При выполнении этой команды CLSAgent на каждом компьютере и в каждом пуле сайта Redmond задает для размера переключения на новый файл трассировки значение 40 МБ. Эта команда не повлияет на компьютеры и пулы на других сайтах, которые продолжат использовать текущее значение размера переключения на новый журнал трассировки, определенное либо по умолчанию (20 МБ), либо во время запуска сеанса ведения журнала.
### <a name="to-create-a-new-centralized-logging-service-configuration"></a>Создание новой конфигурации централизованной службы ведения журнала

1. Запустите командную консоль Skype для бизнеса: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Skype для бизнеса 2015** и щелкните элемент **Командная консоль Skype для бизнеса**.

2. Введите следующую команду в командной строке:

   ```PowerShell
   New-CsClsConfiguration -Identity <scope and name> [CsClsConfiguration options for this site]
   ```

    > [!NOTE]
    > Командлет New-CsClsConfiguration предоставляет доступ к большому количеству необязательных параметров конфигурации. Дополнительные сведения о параметрах конфигурации можно найти в [статьях Get-ксклсконфигуратион](https://docs.microsoft.com/powershell/module/skype/get-csclsconfiguration?view=skype-ps) и общие сведения о [централизованных параметрах конфигурации службы ведения журнала](https://technet.microsoft.com/library/3c34e600-0b91-43dc-b4cc-90b6a70ee12e.aspx).

Например для создания новой конфигурации, которая определяет сетевую папку для файлов кэша, а также период и размер переключения для файлов журнала, введите следующую команду:

  ```PowerShell
  New-CsClsConfiguration -Identity "site:Redmond" -CacheFileNetworkFolder "\\fs01.contoso.net\filestore\logfiles" -EtlFileRolloverMinutes 120 -EtlFileRolloverSizeMB 40
  ```

Тщательно спланируйте создание новых конфигураций и определите, как вы определяете новые свойства для централизованной службы ведения журнала. You should be cautious about making changes and make sure you understand the impact on your ability to properly log problem scenarios. You should make changes to the configuration that will enhance your ability to manage logs to a size and a rollover period that will allow problem solving when it arises.
### <a name="to-remove-an-existing-centralized-logging-service-configuration"></a>Удаление существующей конфигурации службы централизованного ведения журнала

1. Запустите командную консоль Skype для бизнеса: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Skype для бизнеса 2015** и щелкните элемент **Командная консоль Skype для бизнеса**.

2. Введите следующую команду в командной строке:

   ```PowerShell
   Remove-CsClsConfiguration -Identity <scope and name>
   ```

Например, чтобы удалить созданную конфигурацию централизованной службы ведения журналов, чтобы продлить время переключения на файл журнала, измените размер файла журнала продолжения и установите для него расположение кэша файлов журнала, выполнив указанные ниже действия.

  ```PowerShell
  Remove-CsClsConfiguration -Identity "site:Redmond"
  ```

> [!NOTE]
> Это новая конфигурация, созданная в процедуре "Создание новой конфигурации централизованной службы ведения журнала".

Если удалить конфигурацию уровня сайта, сайт будет использовать глобальные параметры.
## <a name="see-also"></a>См. также

[Настройка поставщиков для централизованной службы ведения журналов в Skype для бизнеса Server 2015](configure-providers.md)

[Настройка сценариев для централизованной службы ведения журналов в Skype для бизнеса Server 2015](configure-scenarios.md)

[Centralized Logging Service in Skype for Business 2015](centralized-logging-service.md)

[Set-CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csclsconfiguration?view=skype-ps)

[Get-CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csclsconfiguration?view=skype-ps)

[New-CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csclsconfiguration?view=skype-ps)

[Remove-CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csclsconfiguration?view=skype-ps)
