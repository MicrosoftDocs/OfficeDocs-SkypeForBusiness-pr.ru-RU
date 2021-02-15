---
title: Настройка сценариев для службы централизованного ведения журналов в Skype для бизнеса Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 12/20/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 6c3bf826-e7fd-4002-95dc-01020641ef01
description: Сводка. Узнайте, как создавать, изменять и удалять сценарии для службы централизованного ведения журналов в Skype для бизнеса Server 2015.
ms.openlocfilehash: 8778530826cdbd0c3ecc5128385644f2191a858e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49835189"
---
# <a name="configure-scenarios-for-the-centralized-logging-service-in-skype-for-business-server-2015"></a>Настройка сценариев для службы централизованного ведения журналов в Skype для бизнеса Server 2015
 
**Сводка:** Узнайте, как создавать, изменять и удалять сценарии для службы централизованного ведения журналов в Skype для бизнеса Server 2015.
  
Сценарии определяют область (глобальную область, сайт, пул или компьютер) и поставщиков, которые будут использовать в службе централизованного ведения журналов. С помощью сценариев вы включаете и отключаете трассировку поставщиков (например, S4, SIPStack, мгновенных сообщений и сведений о присутствии). Настроив сценарий вы можете сгруппировать все поставщики заданной логической коллекции, которые решают определенную проблему. Если вы нашли, что сценарий необходимо изменить для устранения неполадок и ведения журнала, средства отладки Skype для бизнеса Server 2015 предоставляют модуль Windows PowerShell с именем ClsScenarioEdit.psm1, содержащий функцию с именемEdit-CsClsScenario. Предназначение этого модуля — изменение свойств именованного сценария. Примеры работы этого модуля представлены в этом разделе. Скачайте средства отладки Skype [](https://go.microsoft.com/fwlink/p/?LinkId=285257) для бизнеса Server 2015, прежде чем ходить дальше.
  
> [!IMPORTANT]
> Для любой области действия (глобальной, области узла, пула и компьютера) одновременно можно использовать не больше двух сценариев. Чтобы определить, какие сценарии уже запущены, используйте Windows PowerShell [и Get-CsClsScenario.](https://docs.microsoft.com/powershell/module/skype/get-csclsscenario?view=skype-ps) С помощью Windows PowerShell [и Set-CsClsScenario](https://docs.microsoft.com/powershell/module/skype/set-csclsscenario?view=skype-ps)можно динамически изменять запущенные сценарии. Это можно сделать во время сеанса ведения журнала, чтобы скорректировать собираемые данные и поставщиков, от которых они собираются. 
  
Для запуска функций службы централизованного ведения журналов с помощью оболочки управления Skype для бизнеса Server необходимо быть участником групп безопасности управления доступом на основе ролей (RBAC) CsAdministrator или CsServerAdministrator, а также настраиваемой роли RBAC, которая содержит какую-либо из этих двух групп. Чтобы получить список всех ролей RBAC, которые были назначены этому командлету, включая все самостоятельно созданные роли RBAC, запустите следующую команду в командной Windows PowerShell Командная Windows PowerShell Skype для бизнеса Server:
  
```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Skype for Business Server 2015 cmdlet"}
```

Например:
  
```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}
```

Остальная часть этого раздела посвящена определению сценария, изменению сценария, получению сведений о выполняемых сценариях, удалению сценария указанию содержимого сценария для оптимизации устранения неполадок. Для выдачи Windows PowerShell команд можно использовать командную Windows PowerShell Skype для бизнеса Server. При использовании Windows PowerShell можно определить новые сценарии для использования в сеансах ведения журнала.
  
Как было введено в службе централизованного ведения журналов в Skype для бизнеса [2015,](centralized-logging-service.md)сценарий представлен в таких элементах:
  
- **Поставщики** Если вы знакомы с OCSLogger, поставщики — это компоненты, из каких компонентов OCSLogger должен собирать журналы. Поставщики — это те же компоненты, а во многих случаях их имя совпадает с компонентами в OCSLogger. Если вы не знакомы с OCSLogger, поставщики — это компоненты роли сервера, из которые централизованная служба ведения журналов может собирать журналы. Подробные сведения о конфигурации поставщиков см. в сведениях о настройке поставщиков для службы централизованного ведения журналов [в Skype для бизнеса Server 2015.](configure-providers.md)
    
- **Удостоверение** Параметр -Identity задает область действия и имя сценария. Например, можно установить область "global" и определить сценарий с помощью "LyssServiceScenario". При комбинировке этих двух личных данных определяется идентификатор (например, "global/LyssServiceScenario").
    
    При желании можно использовать параметры -Name и -Parent. Параметр Name задается для уникальной идентификации сценария. Если используется параметр Name, необходимо также использовать параметр Parent, чтобы добавить сценарий в глобальную область или область узла. 
    
    > [!IMPORTANT]
    > При использовании параметров Name и Parent нельзя использовать **параметр -Identity.**
  
### <a name="to-create-a-new-scenario-with-the-new-csclsscenario-cmdlet"></a>Создание сценария с помощью командлета New-CsClsScenario

1. Запустите оболочку управления Skype для бизнеса Server: нажмите кнопку "Начните", выберите "Все программы", "Skype для бизнеса **2015",** а затем щелкните "Skype для бизнеса Server Management **Shell".**
    
2. Чтобы создать новый сценарий для сеанса ведения журнала, используйте [New-CsClsProvider](https://docs.microsoft.com/powershell/module/skype/new-csclsprovider?view=skype-ps) и определите имя сценария (т. е. способ его уникальной идентифицированной). Выберите тип формата ведения журнала в WPP (то есть в предпроцессоре программной трасситуры Windows по умолчанию), EventLog (то есть в формате журнала событий Windows) или IISLog (то есть в формате ASCII на основе формата файла журнала IIS). Затем определите уровень (как определено в разделе "Уровни ведения журнала" в этом разделе) и флаги (как определено в разделе "Флаги" в этом разделе).
    
    Для этого примера сценария мы используем LyssProvider как пример переменной поставщика.
    
    Чтобы создать сценарий с помощью заданных параметров, введите следующую команду:
    
   ```PowerShell
   New-CsClsScenario -Identity <scope>/<unique scenario name> -Provider <provider variable>
   ```

    Например:
    
   ```PowerShell
   New-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider $LyssProvider
   ```

    Альтернативный формат с использованием -Name и -Parent:
    
   ```PowerShell
   New-CsClsScenario -Name "LyssServiceScenario" -Parent "site:Redmond" -Provider $LyssProvider
   ```

### <a name="to-create-a-new-scenario-with-multiple-providers-with-the-new-csclsscenario-cmdlet"></a>Создание сценария с несколькими поставщиками с помощью командлета New-CsClsScenario

1. Запустите оболочку управления Skype для бизнеса Server: нажмите кнопку "Начните", выберите "Все программы", "Skype для бизнеса **2015",** а затем щелкните "Skype для бизнеса Server Management **Shell".**
    
2. Можно использовать не больше двух сценариев для области действия. Однако число поставщиков не ограничено. В этом примере предположим, что мы создали три поставщика и хотим назначить все три из них определяемому вами сценарию. Имена переменных поставщиков: LyssProvider, ABServerProvider и SIPStackProvider. Чтобы определить и назначить сценарию нескольких поставщиков, введите следующую команду в командной Windows PowerShell Skype для бизнеса Server:
    
   ```PowerShell
   New-CsClsScenario -Identity "site:Redmond/CollectDataScenario" -Provider @{Add=$LyssProvider, $ABServerProvider,  $SIPStackProvider}
   ```

    > [!NOTE]
    > Как известно в Windows PowerShell, соглашение о создании таблицы значений с использованием hash  `@{<variable>=<value1>, <value2>, <value>…}` называетсяsplatting. Подробные сведения о размещении в Windows PowerShell см. в [https://go.microsoft.com/fwlink/p/?LinkId=267760](https://go.microsoft.com/fwlink/p/?LinkId=267760) . 
  
### <a name="to-modify-an-existing-scenario-with-the-set-csclsscenario-cmdlet"></a>Изменение существующего сценария с помощью командлета Set-CsClsScenario

1. Запустите оболочку управления Skype для бизнеса Server: нажмите кнопку "Начните", выберите "Все программы", "Skype для бизнеса **2015",** а затем щелкните "Skype для бизнеса Server Management **Shell".**
    
2. Можно использовать не больше двух сценариев для области действия. Вы можете изменить выполняемые сценарии в любое время даже во время сеанса ведения журналов. Если переопределить выполняемые сценарии, текущий сеанс перестанет использовать удаленный сценарий и начнет применять новый сценарий. Однако данные ведения журналов, полученные с помощью удаленного сценария, останутся в полученных журналах. Чтобы определить новый сценарий, сделайте следующее (при условии, что добавлен уже определенный поставщик С4Provider):
    
   ```PowerShell
   Set-CsClsScenario -Identity <name of scope and scenario defined by New-CsClsScenario> -Provider @{Add=<new provider to add>}
   ```

    Например:
    
   ```PowerShell
   Set-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider @{Add=$S4Provider}
   ```

    Если вы хотите заменить поставщики, определить один поставщика или разделенный запятыми список поставщиков, чтобы заменить текущий набор. Если вы хотите только заменить один из нескольких поставщиков, добавьте текущие поставщики с новыми поставщиками, чтобы создать новый набор поставщиков, который содержит новые и существующие поставщики. Чтобы заменить все поставщики новым набором, введите следующую команду:
    
   ```PowerShell
   Set-CsClsScenario -Identity <name of scope and scenario defined by New-CsClsScenario> -Provider @{Replace=<providers to replace existing provider set>}
   ```

    Например, чтобы заменить текущий набор из $LyssProvider, $ABServerProvider и $SIPStackProvider на $LyssServiceProvider, выполните следующую команду:
    
   ```PowerShell
   Set-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider @{Replace=$LyssServiceProvider}
   ```

    Чтобы заменить только поставщик $LyssProvider из текущего набора $LyssProvider, $ABServerProvider и $SIPStackProvider на $LyssServiceProvider, введите следующую команду:
    
   ```PowerShell
   Set-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider @{Replace=$LyssServiceProvider, $ABServerProvider, $SIPStackProvider}
   ```

### <a name="to-remove-an-existing-scenario-with-the-remove-csclsscenario-cmdlet"></a>Удаление существующего сценария с помощью командлета Remove-CsClsScenario

1. Запустите оболочку управления Skype для бизнеса Server: нажмите кнопку "Начните", выберите "Все программы", "Skype для бизнеса **2015",** а затем щелкните "Skype для бизнеса Server Management **Shell".**
    
2. Если вы хотите удалить сценарий, определенный ранее, введите следующую команду:
    
   ```PowerShell
   Remove-CsClsScenario -Identity <name of scope and scenario>
   ```

    Например, чтобы удалить заданный сценарий site:Redmond/LyssServiceScenario:
    
   ```PowerShell
   Remove-CsClsScenario -Identity "site:Redmond/LyssServiceScenario"
   ```

Командлет **Remove-CsClsScenario** удаляет указанный сценарий, но полученные трассировки все еще доступны в журналах.
### <a name="to-load-and-unload-the-edit-csclsscenario-cmdlet-using-the-clsscenarioeditpsm1-module"></a>Загрузка и выгрузка Edit-CsClsScenario с помощью модуля ClsScenarioEdit.psm1

1. Запустите оболочку управления Skype для бизнеса Server: нажмите кнопку "Начните", выберите "Все программы", "Skype для бизнеса **2015",** а затем щелкните "Skype для бизнеса Server Management **Shell".**
    
    > [!IMPORTANT]
    > Модуль ClsScenarioEdit.psm1 предоставляется как отдельная веб-загрузка. Модуль входит в состав средств отладки Skype для бизнеса Server 2015. По умолчанию средства отладки устанавливаются в каталог C:\Program Files\Skype для бизнеса Server 2015\Debugging Tools. 
  
2. В Windows PowerShell введите:
    
   ```PowerShell
   Import-Module "CDBurn\OCO\amd64\Support"
   ```

    > [!TIP]
    > После успешной загрузки модуля вы вернетесь в Windows PowerShell командной Windows PowerShell. Чтобы подтвердить загрузку модуля и наличие Edit-CsClsScenario, введите  `Get-Help Edit-CsClsScenario` . Вы должны увидеть базовые сведения о синтаксисе использования EditCsClsScenario. 
  
3. Чтобы выгрузить модули, введите:
    
   ```PowerShell
   Remove-Module ClsController
   ```

    > [!TIP]
    > Успешная выгрузка модуля возвращает вас в Windows PowerShell командной Windows PowerShell. Чтобы подтвердить выгрузку модуля, введите  `Get-Help Edit-CsClsScenario` . Windows PowerShell попытается найти справку для этого cmdlet и не будет работать. 
  
### <a name="to-remove-an-existing-provider-from-a-scenario-with-the-edit-clscontroller-module"></a>Удаление существующего поставщика из сценария с помощью командлета Edit-ClsController

1. Запустите оболочку управления Skype для бизнеса Server: нажмите кнопку "Начните", выберите "Все программы", "Skype для бизнеса **2015",** а затем щелкните "Skype для бизнеса Server Management **Shell".**
    
2. В Windows PowerShell введите:
    
   ```PowerShell
   Import-Module "CDBurn\OCO\amd64\Support"
   ```

    > [!TIP]
    > После успешной загрузки модуля вы вернетесь в Windows PowerShell командной Windows PowerShell. Чтобы подтвердить загрузку модуля и наличие Edit-CsClsScenario, введите  `Get-Help Edit-CsClsScenario` . Вы должны увидеть базовые сведения о синтаксисе использования EditCsClsScenario. 
  
3. Чтобы удалить поставщика из сценария AlwaysOn, введите:
    
   ```PowerShell
   Edit-CsClsScenario -ScenarioName <string of the scenario to edit> -ProviderName <string of the provider to remove> -Remove
   ```

   Например:
    
   ```PowerShell
   Edit-CsClsScenario -ScenarioName AlwaysOn -ProviderName ChatServer -Remove
   ```

   Параметры ScenarioName и ProviderName являются позиционными (т. е. их необходимо задать в ожидаемой позиции в командной строке). Имя параметра необязательно явно определять, если имя сценария находится во второй позиции, а поставщик — в третьей позиции относительно первой позиции имени командлета. Используя эту информацию, предыдущая команда вводится следующим образом:
    
   ```PowerShell
   Edit-CsClsScenario AlwaysOn ChatServer -Remove
   ```

   Позиционное размещение значений параметров применяется только к -Scenario и -Provider. Все другие параметры нужно определить явно.
    
### <a name="to-add-a-provider-to-a-scenario-with-the-edit-clscontroller-module"></a>Добавление поставщика в сценарий с помощью командлета Edit-ClsController

1. Запустите оболочку управления Skype для бизнеса Server: нажмите кнопку "Начните", выберите "Все программы", "Skype для бизнеса **2015",** а затем щелкните "Skype для бизнеса Server Management **Shell".**
    
2. Чтобы добавить поставщик в сценарий AlwaysOn, введите:
    
   ```PowerShell
   Edit-CsClsScenario -ScenarioName <string of the scenario to edit> -ProviderName <string of the provider to add> -Level <string of type level> -Flags <string of type flags>
   ```

    Например:
    
   ```PowerShell
   Edit-CsClsScenario -ScenarioName AlwaysOn -ProviderName ChatServer -Level Info -Flags TF_COMPONENT
   ```

    Значением -Loglevel может быть Fatal, Error, Warning, Info, Verbose, Debug или All. -Flags может быть любым из флагов, поддерживаемого поставщиком, например TF_COMPONENT, TF_DIAG. -Flags также может иметь значение ALL
    
   Предыдущий пример также можно ввести, используя позиционность командлета. Например, чтобы добавить поставщик ChatServer в сценарий AlwaysOn, введите:
    
   ```PowerShell
   Edit-CsClsScenario AlwaysOn ChatServer -Level Info -Flags ALL
   ```
