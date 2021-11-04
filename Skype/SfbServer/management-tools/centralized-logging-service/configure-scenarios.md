---
title: Настройка сценариев для централизованной службы ведения журнала в Skype для бизнеса Server 2015 г.
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 12/20/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 6c3bf826-e7fd-4002-95dc-01020641ef01
description: Сводка. Сведения о создании, изменении и устранении сценариев для службы централизованного ведения журнала в Skype для бизнеса Server 2015 г.
ms.openlocfilehash: da9a3c431be78a3abeab929fab86f1bf45e6cfa7
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/04/2021
ms.locfileid: "60766347"
---
# <a name="configure-scenarios-for-the-centralized-logging-service-in-skype-for-business-server-2015"></a>Настройка сценариев для централизованной службы ведения журнала в Skype для бизнеса Server 2015 г.
 
**Сводка:** Узнайте, как создавать, изменять и удалять сценарии для централизированной службы ведения журнала в Skype для бизнеса Server 2015 г.
  
Сценарии определяют область (то есть глобальный, сайт, пул или компьютер) и то, какие поставщики будут использовать в службе централизованного ведения журнала. С помощью сценариев вы включаете и отключаете трассировку поставщиков (например, S4, SIPStack, мгновенных сообщений и сведений о присутствии). Настроив сценарий вы можете сгруппировать все поставщики заданной логической коллекции, которые решают определенную проблему. Если для устранения неполадок и ведения журнала необходимо изменить сценарий, средства отладки Skype для бизнеса Server 2015 г. предоставляют вам модуль Windows PowerShell ClsScenarioEdit.psm1, содержащий функцию с именемEdit-CsClsScenario. Предназначение этого модуля — изменение свойств именованного сценария. Примеры работы этого модуля представлены в этом разделе. Скачайте Skype для бизнеса Server 2015 [отладки,](https://go.microsoft.com/fwlink/p/?LinkId=285257) прежде чем ходить дальше.
  
> [!IMPORTANT]
> Для любой области действия (глобальной, области узла, пула и компьютера) одновременно можно использовать не больше двух сценариев. Чтобы определить, какие сценарии в настоящее время запущены, Windows PowerShell [и Get-CsClsScenario](/powershell/module/skype/get-csclsscenario?view=skype-ps). Используя Windows PowerShell [и Set-CsClsScenario,](/powershell/module/skype/set-csclsscenario?view=skype-ps)вы можете динамически изменить сценарии. Это можно сделать во время сеанса ведения журнала, чтобы скорректировать собираемые данные и поставщиков, от которых они собираются. 
  
Чтобы запустить функции службы централизованного ведения журнала с помощью Skype для бизнеса Server Management Shell, необходимо быть членом группы безопасности CsAdministrator или группы управления ролями CsServerAdministrator (RBAC) или настраиваемой роли RBAC, которая содержит обе эти две группы. Чтобы вернуть список всех ролей RBAC, на которые был назначен этот командлет, включая настраиваемые роли RBAC, созданные самими, запустите следующую команду из командной Skype для бизнеса Server или Windows PowerShell запроса:
  
```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Skype for Business Server 2015 cmdlet"}
```

Например:
  
```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}
```

Остальная часть этого раздела посвящена определению сценария, изменению сценария, получению сведений о выполняемых сценариях, удалению сценария указанию содержимого сценария для оптимизации устранения неполадок. Вы можете использовать командную Skype для бизнеса Server для выпуска Windows PowerShell команд. При использовании Windows PowerShell можно определить новые сценарии для использования в сеансах ведения журнала.
  
Как было введено в службе централизованного ведения журнала в [Skype для бизнеса 2015](centralized-logging-service.md)г., элементами сценария являются:
  
- **Поставщики** Если вы знакомы с OCSLogger, поставщики — это компоненты, которые необходимо сообщить OCSLogger, из чего должен собирать журналы двигатель отслеживания. Поставщики — это те же компоненты, а во многих случаях их имя совпадает с компонентами в OCSLogger. Если вы не знакомы с OCSLogger, поставщики являются определенными компонентами роли сервера, из них централизованная служба ведения журнала может собирать журналы. Сведения о конфигурации поставщиков см. в материале [Configure providers for Centralized Logging Service in Skype для бизнеса Server 2015.](configure-providers.md)
    
- **Identity** Параметр -Identity задает область и имя сценария. Например, можно установить область "глобальный" и определить сценарий с помощью "LyssServiceScenario". При сочетании этих двух личных данных определяется идентификатор (например, "global/LyssServiceScenario").
    
    Необязательно можно использовать параметры -Name и -Parent. Параметр Name задается для уникальной идентификации сценария. Если используется параметр Name, необходимо также использовать параметр Parent, чтобы добавить сценарий в глобальную область или область узла. 
    
    > [!IMPORTANT]
    > Если вы используете параметры Name и Parent, вы не можете использовать **параметр -Identity.**
  
### <a name="to-create-a-new-scenario-with-the-new-csclsscenario-cmdlet"></a>Создание сценария с помощью командлета New-CsClsScenario

1. Запустите Skype для бизнеса Server: нажмите кнопку Начните, щелкните Все **программы,** нажмите кнопку Skype для бизнеса **2015,** а затем нажмите кнопку **Skype для бизнеса Server.**
    
2. Чтобы создать сценарий для сеанса ведения журналов, используйте [New-CsClsProvider](/powershell/module/skype/new-csclsprovider?view=skype-ps) и задайте имя сценария (т. е. его уникальный идентификатор). Выберите тип формата ведения журнала в WPP (т. е. препроцессор трассировки ПО Windows, значение по умолчанию), EventLog (т. е. формат журнала событий Windows) или IISLog (т. е. формат ASCII на основе формата IIS). Затем задайте уровень (как указано в подразделе "Уровни ведения журнала" в этом разделе) и флаги (см. "Флаги" в этом разделе).
    
    Для этого примера сценария мы используем LyssProvider как пример переменной поставщика.
    
    Чтобы создать сценарий с помощью заданных параметров, введите следующую команду:
    
   ```PowerShell
   New-CsClsScenario -Identity <scope>/<unique scenario name> -Provider <provider variable>
   ```

    Например:
    
   ```PowerShell
   New-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider $LyssProvider
   ```

    Альтернативный формат с помощью -Name и -Parent:
    
   ```PowerShell
   New-CsClsScenario -Name "LyssServiceScenario" -Parent "site:Redmond" -Provider $LyssProvider
   ```

### <a name="to-create-a-new-scenario-with-multiple-providers-with-the-new-csclsscenario-cmdlet"></a>Создание сценария с несколькими поставщиками с помощью командлета New-CsClsScenario

1. Запустите Skype для бизнеса Server: нажмите кнопку Начните, щелкните Все **программы,** нажмите кнопку Skype для бизнеса **2015,** а затем нажмите кнопку **Skype для бизнеса Server.**
    
2. Можно использовать не больше двух сценариев для области действия. Однако число поставщиков не ограничено. В этом примере предположим, что мы создали три поставщика и хотим назначить все три из них определяемому вами сценарию. Имена переменных поставщиков: LyssProvider, ABServerProvider и SIPStackProvider. Чтобы определить и назначить несколько поставщиков сценарию, введите следующее в командной Skype для бизнеса Server или Windows PowerShell командной подсказке:
    
   ```PowerShell
   New-CsClsScenario -Identity "site:Redmond/CollectDataScenario" -Provider @{Add=$LyssProvider, $ABServerProvider,  $SIPStackProvider}
   ```

    > [!NOTE]
    > Как известно в Windows PowerShell, конвенция по созданию таблицы значений с использованием hash называется `@{<variable>=<value1>, <value2>, <value>…}` assplatting. Подробные сведения о splatting в Windows PowerShell [https://go.microsoft.com/fwlink/p/?LinkId=267760](/previous-versions/technet-magazine/gg675931(v=msdn.10)) см. в . 
  
### <a name="to-modify-an-existing-scenario-with-the-set-csclsscenario-cmdlet"></a>Изменение существующего сценария с помощью командлета Set-CsClsScenario

1. Запустите Skype для бизнеса Server: нажмите кнопку Начните, щелкните Все **программы,** нажмите кнопку Skype для бизнеса **2015,** а затем нажмите кнопку **Skype для бизнеса Server.**
    
2. Можно использовать не больше двух сценариев для области действия. Вы можете изменить выполняемые сценарии в любое время даже во время сеанса ведения журналов. Если переопределить выполняемые сценарии, текущий сеанс перестанет использовать удаленный сценарий и начнет применять новый сценарий. Однако данные ведения журналов, полученные с помощью удаленного сценария, останутся в полученных журналах. Чтобы определить новый сценарий, сделайте следующее (то есть при условии добавления уже определенного поставщика с именем "S4Provider"):
    
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

1. Запустите Skype для бизнеса Server: нажмите кнопку Начните, щелкните Все **программы,** нажмите кнопку Skype для бизнеса **2015,** а затем нажмите кнопку **Skype для бизнеса Server.**
    
2. Если вы хотите удалить сценарий, определенный ранее, введите следующую команду:
    
   ```PowerShell
   Remove-CsClsScenario -Identity <name of scope and scenario>
   ```

    Например, чтобы удалить заданный сценарий site:Redmond/LyssServiceScenario:
    
   ```PowerShell
   Remove-CsClsScenario -Identity "site:Redmond/LyssServiceScenario"
   ```

Командлет **Remove-CsClsScenario** удаляет указанный сценарий, но полученные трассировки все еще доступны в журналах.
### <a name="to-load-and-unload-the-edit-csclsscenario-cmdlet-using-the-clsscenarioeditpsm1-module"></a>Загрузка и разгрузка Edit-CsClsScenario с помощью модуля ClsScenarioEdit.psm1

1. Запустите Skype для бизнеса Server: нажмите кнопку Начните, щелкните Все **программы,** нажмите кнопку Skype для бизнеса **2015,** а затем нажмите кнопку **Skype для бизнеса Server.**
    
    > [!IMPORTANT]
    > Модуль ClsScenarioEdit.psm1 предоставляется в качестве отдельного веб-скачивания. Модуль является частью средств отладки Skype для бизнеса Server 2015 года. По умолчанию средства отладки устанавливаются в каталоге C:\Program Files\Skype для бизнеса Server 2015\Debugging Tools. 
  
2. Из Windows PowerShell введите:
    
   ```PowerShell
   Import-Module "CDBurn\OCO\amd64\Support"
   ```

    > [!TIP]
    > Успешная загрузка модуля возвращает вас к Windows PowerShell командной подсказке. Чтобы подтвердить загрузку модуля и наличие Edit-CsClsScenario, введите  `Get-Help Edit-CsClsScenario` . Вы должны увидеть базовые сведения о синтаксисе использования EditCsClsScenario. 
  
3. Чтобы выгрузить модули, введите:
    
   ```PowerShell
   Remove-Module ClsController
   ```

    > [!TIP]
    > Успешная разгрузка модуля возвращает вас к Windows PowerShell командной подсказке. Чтобы подтвердить, что модуль разгружен, введите  `Get-Help Edit-CsClsScenario` . Windows PowerShell будет пытаться найти справку для cmdlet и сбой. 
  
### <a name="to-remove-an-existing-provider-from-a-scenario-with-the-edit-clscontroller-module"></a>Удаление существующего поставщика из сценария с помощью командлета Edit-ClsController

1. Запустите Skype для бизнеса Server: нажмите кнопку Начните, щелкните Все **программы,** нажмите кнопку Skype для бизнеса **2015,** а затем нажмите кнопку **Skype для бизнеса Server.**
    
2. Из Windows PowerShell введите:
    
   ```PowerShell
   Import-Module "CDBurn\OCO\amd64\Support"
   ```

    > [!TIP]
    > Успешная загрузка модуля возвращает вас к Windows PowerShell командной подсказке. Чтобы подтвердить загрузку модуля и наличие Edit-CsClsScenario, введите  `Get-Help Edit-CsClsScenario` . Вы должны увидеть базовые сведения о синтаксисе использования EditCsClsScenario. 
  
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

1. Запустите Skype для бизнеса Server: нажмите кнопку Начните, щелкните Все **программы,** нажмите кнопку Skype для бизнеса **2015,** а затем нажмите кнопку **Skype для бизнеса Server.**
    
2. Чтобы добавить поставщик в сценарий AlwaysOn, введите:
    
   ```PowerShell
   Edit-CsClsScenario -ScenarioName <string of the scenario to edit> -ProviderName <string of the provider to add> -Level <string of type level> -Flags <string of type flags>
   ```

    Например:
    
   ```PowerShell
   Edit-CsClsScenario -ScenarioName AlwaysOn -ProviderName ChatServer -Level Info -Flags TF_COMPONENT
   ```

    Значением -Loglevel может быть Fatal, Error, Warning, Info, Verbose, Debug или All. -Флаги могут быть любыми флагами, поддерживаемыми поставщиком, например TF_COMPONENT, TF_DIAG. -Флаги также могут иметь значение ALL
    
   Предыдущий пример также можно ввести, используя позиционность командлета. Например, чтобы добавить поставщик ChatServer в сценарий AlwaysOn, введите:
    
   ```PowerShell
   Edit-CsClsScenario AlwaysOn ChatServer -Level Info -Flags ALL
   ```