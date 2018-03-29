---
title: Настройка сценариев для централизованной службы ведения журналов в Skype для бизнеса Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 12/20/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 6c3bf826-e7fd-4002-95dc-01020641ef01
description: 'Сводка: Узнайте, как создавать, изменять и удалять сценариев для централизованной службы ведения журналов в Скайп для Business Server 2015.'
ms.openlocfilehash: e8b9575ed949e1769e867113be301deede981018
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="configure-scenarios-for-the-centralized-logging-service-in-skype-for-business-server-2015"></a>Настройка сценариев для централизованной службы ведения журналов в Skype для бизнеса Server 2015
 
**Сводка:** Узнайте, как создавать, изменять и удалять сценариев для централизованной службы ведения журналов в Скайп для Business Server 2015.
  
Сценарии определить область (то есть, глобальная, на уровне сайта, пул или компьютер) и какие поставщиков для использования в службы централизованного ведения журналов. С помощью сценариев, включение или отключение трассировки на поставщиков (например, S4, SIPStack, обмен мгновенными Сообщениями и присутствия). Настроив сценарий, можно сгруппировать всех поставщиков для данного семейства сайтов логической этот адрес условие определенные проблемы. Если сценарий необходимо изменить в соответствии с диагностики и ведение журналов потребности, Скайп для средств отладки 2015 Business Server предоставляет модулем Windows PowerShell с именем ClsScenarioEdit.psm1, содержащий функции namedEdit-CsClsScenario. Модуль предназначен для изменения свойств именованные сценария. В этом разделе приведены примеры того, как работает этот модуль. Загрузите Скайп Business Server 2015 [Средства отладки](https://go.microsoft.com/fwlink/p/?LinkId=285257) , прежде чем перейти к следующему шагу.
  
> [!IMPORTANT]
> Для любой области действия (глобальной, области узла, пула и компьютера) одновременно можно использовать не больше двух сценариев. Чтобы определить, какие сценарии выполняются в настоящее время, используйте Windows PowerShell и [Get-CsClsScenario](https://docs.microsoft.com/powershell/module/skype/get-csclsscenario?view=skype-ps). С помощью Windows PowerShell и [Set-CsClsScenario](https://docs.microsoft.com/powershell/module/skype/set-csclsscenario?view=skype-ps), можно динамически изменять, какие сценарии выполняются. Это можно сделать во время сеанса ведения журнала, чтобы скорректировать собираемые данные и поставщиков, от которых они собираются. 
  
Для запуска функции централизованной службы ведения журналов с помощью Скайп для консоли Business Server, должна быть членом CsAdministrator или групп безопасности CsServerAdministrator доступом на основе ролей (RBAC) элемента управления или настраиваемые роли RBAC, содержит любой из этих двух групп. Чтобы получить список всех RBAC роли, которые этот командлет назначено, включая любые пользовательские роли RBAC, созданные самостоятельно, выполните следующую команду из Скайп для консоли Business Server или в командной строке Windows PowerShell:
  
```
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Skype for Business Server 2015 cmdlet"}
```

Например:
  
```
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}
```

В оставшейся части этого раздела рассказывается о определить сценарий, изменить сценарий, получать выполнение сценариев, удалить сценарий и указать, содержащий сценарий для оптимизации диагностики. Скайп для консоли Business Server можно использовать для выполнения команд Windows PowerShell. При использовании Windows PowerShell можно определить новые сценарии для использования в вашей сеансы ведения журналов.
  
Как было описано в [Централизованной службы ведения журналов в Скайп для бизнеса 2015](centralized-logging-service.md), являются элементы сценария:
  
- **Поставщики** Если вы знакомы с OCSLogger, поставщики — это компоненты, чтобы сообщить OCSLogger обработчик трассировки следует собирать данные для выбора. Поставщики — это те же компоненты, а во многих случаях их имя совпадает с компонентами в OCSLogger. Если вы не знакомы с OCSLogger, поставщиков, определенным компонентам ролей сервера, что службы централизованного ведения журналов можно собирать входит в систему. Для получения дополнительных сведений о конфигурации поставщиков видеть [Настройка поставщиков для централизованной службы ведения журналов в Скайп для Business Server 2015](configure-providers.md).
    
- **Удостоверение** Параметр-Identity задает имя сценария и область применения. Например может задать область «глобальные» и определите сценария с «LyssServiceScenario». При объединении двух можно определить идентификатор (например, «глобальные/LyssServiceScenario»).
    
    Кроме того, можно использовать параметры - Name и - Parent. Параметр Name задается для уникальной идентификации сценария. Если используется параметр Name, необходимо также использовать параметр Parent, чтобы добавить сценарий в глобальную область или область узла. 
    
    > [!IMPORTANT]
    > Если вы используете параметры Name и Parent, нельзя использовать **-Identity** параметр.
  
### <a name="to-create-a-new-scenario-with-the-new-csclsscenario-cmdlet"></a>Создание сценария с помощью командлета New-CsClsScenario

1. Запустите командную консоль Skype для бизнеса: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Skype для бизнеса 2015** и щелкните элемент **Командная консоль Skype для бизнеса**.
    
2. Чтобы создать новый сценарий для сеанса ведения журнала, используйте [New-CsClsProvider](https://docs.microsoft.com/powershell/module/skype/new-csclsprovider?view=skype-ps) и определите имя сценария (то есть, как оно будет уникальным образом идентифицироваться). Выберите тип формата ведения журнала из WPP (то есть, трассировка препроцессору программного обеспечения Windows и используется по умолчанию), журнал событий (то есть, формат журнала событий Windows) или IISLog (то есть, файл в формате ASCII на основе формат файла журнала IIS). Затем определите уровень (как определено в разделе уровни ведения журнала в данном разделе) и флаги (как определено в разделе флаги в данном разделе).
    
    Для этого примера сценария мы используем LyssProvider как пример переменной поставщика.
    
    Чтобы создать сценарий с помощью заданных параметров, введите следующую команду:
    
  ```
  New-CsClsScenario -Identity <scope>/<unique scenario name> -Provider <provider variable>
  ```

    Например:
    
  ```
  New-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider $LyssProvider
  ```

    Альтернативный формат с помощью - Name и - Parent:
    
  ```
  New-CsClsScenario -Name "LyssServiceScenario" -Parent "site:Redmond" -Provider $LyssProvider
  ```

### <a name="to-create-a-new-scenario-with-multiple-providers-with-the-new-csclsscenario-cmdlet"></a>Создание сценария с несколькими поставщиками с помощью командлета New-CsClsScenario

1. Запустите командную консоль Skype для бизнеса: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Skype для бизнеса 2015** и щелкните элемент **Командная консоль Skype для бизнеса**.
    
2. Можно использовать не больше двух сценариев для области действия. Тем не менее вы не ограничиваются заданное количество поставщиков. В этом примере предполагается, что мы создали три поставщика и необходимо назначить все три для сценария, который вы определяете. Имена переменных поставщика, LyssProvider, ABServerProvider и SIPStackProvider. Для определения и назначения нескольких поставщиков в сценарий, введите в Скайп для консоли Business Server и Windows PowerShell командной строке следующую команду:
    
  ```
  New-CsClsScenario -Identity "site:Redmond/CollectDataScenario" -Provider @{Add=$LyssProvider, $ABServerProvider,  $SIPStackProvider}
  ```

    > [!NOTE]
    > Как записано в Windows PowerShell, соглашение о создании хэш-таблицы с помощью значений `@{<variable>=<value1>, <value2>, <value>…}` известно assplatting. Сведения о сплаттинг в Windows PowerShell, в разделе [https://go.microsoft.com/fwlink/p/?LinkId=267760](https://go.microsoft.com/fwlink/p/?LinkId=267760). 
  
### <a name="to-modify-an-existing-scenario-with-the-set-csclsscenario-cmdlet"></a>Изменение существующего сценария с помощью командлета Set-CsClsScenario

1. Запустите командную консоль Skype для бизнеса: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Skype для бизнеса 2015** и щелкните элемент **Командная консоль Skype для бизнеса**.
    
2. Можно использовать не больше двух сценариев для области действия. Вы можете изменить выполняемые сценарии в любое время даже во время сеанса ведения журналов. Если переопределить выполняемые сценарии, текущий сеанс перестанет использовать удаленный сценарий и начнет применять новый сценарий. Однако данные ведения журналов, полученные с помощью удаленного сценария, останутся в полученных журналах. Чтобы определить новый сценарий, выполните следующие действия (который Если также уже определенного поставщика, с именем «S4Provider»):
    
  ```
  Set-CsClsScenario -Identity <name of scope and scenario defined by New-CsClsScenario> -Provider @{Add=<new provider to add>}
  ```

    Например:
    
  ```
  Set-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider @{Add=$S4Provider}
  ```

    Если вы хотите заменить поставщики, определить один поставщика или разделенный запятыми список поставщиков, чтобы заменить текущий набор. Если вы хотите только заменить один из нескольких поставщиков, добавьте текущие поставщики с новыми поставщиками, чтобы создать новый набор поставщиков, который содержит новые и существующие поставщики. Чтобы заменить все поставщики новым набором, введите следующую команду:
    
  ```
  Set-CsClsScenario -Identity <name of scope and scenario defined by New-CsClsScenario> -Provider @{Replace=<providers to replace existing provider set>}
  ```

    Например, чтобы заменить текущий набор из $LyssProvider, $ABServerProvider и $SIPStackProvider на $LyssServiceProvider, выполните следующую команду:
    
  ```
  Set-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider @{Replace=$LyssServiceProvider}
  ```

    Чтобы заменить только поставщик $LyssProvider из текущего набора $LyssProvider, $ABServerProvider и $SIPStackProvider на $LyssServiceProvider, введите следующую команду:
    
  ```
  Set-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider @{Replace=$LyssServiceProvider, $ABServerProvider, $SIPStackProvider}
  ```

### <a name="to-remove-an-existing-scenario-with-the-remove-csclsscenario-cmdlet"></a>Удаление существующего сценария с помощью командлета Remove-CsClsScenario

1. Запустите командную консоль Skype для бизнеса: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Skype для бизнеса 2015** и щелкните элемент **Командная консоль Skype для бизнеса**.
    
2. Если вы хотите удалить сценарий, определенный ранее, введите следующую команду:
    
  ```
  Remove-CsClsScenario -Identity <name of scope and scenario>
  ```

    Например, чтобы удалить заданный сценарий site:Redmond/LyssServiceScenario:
    
  ```
  Remove-CsClsScenario -Identity "site:Redmond/LyssServiceScenario"
  ```

Командлет **Remove-CsClsScenario** Удаляет указанный сценарий, но трассировки, которые были записаны, по-прежнему доступны в журналах для поиска по.
### <a name="to-load-and-unload-the-edit-csclsscenario-cmdlet-using-the-clsscenarioeditpsm1-module"></a>Загрузка и выгрузка командлета Edit-CsClsScenario с помощью модуля ClsScenarioEdit.psm1

1. Запустите командную консоль Skype для бизнеса: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Skype для бизнеса 2015** и щелкните элемент **Командная консоль Skype для бизнеса**.
    
    > [!IMPORTANT]
    > Модуль ClsScenarioEdit.psm1 предоставляется как отдельная веб-загрузка. Модуль является частью Скайп для средства отладки 2015 Business Server. По умолчанию средства отладки устанавливаются в каталог C:\Program Files\Skype for Business Server 2015\Debugging Tools. 
  
2. В Windows PowerShell введите команду:
    
  ```
  Import-Module "CDBurn\OCO\amd64\Support"
  ```

    > [!TIP]
    > Успешные загрузки модуля, вы вернетесь в командной строке Windows PowerShell. Чтобы убедиться, что модуль загружен и доступен Edit-CsClsScenario, введите `Get-Help Edit-CsClsScenario`. Вы должны увидеть базовые сведения о синтаксисе использования EditCsClsScenario. 
  
3. Чтобы выгрузить модули, введите:
    
  ```
  Remove-Module ClsController
  ```

    > [!TIP]
    > Успешные выгрузку возвращает модуль вы в командной строке Windows PowerShell. Чтобы убедиться в том, что модуль выгрузки, введите `Get-Help Edit-CsClsScenario`. Windows PowerShell попытается найти справку по командлету и с ошибкой. 
  
### <a name="to-remove-an-existing-provider-from-a-scenario-with-the-edit-clscontroller-module"></a>Удаление существующего поставщика из сценария с помощью командлета Edit-ClsController

1. Запустите командную консоль Skype для бизнеса: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Skype для бизнеса 2015** и щелкните элемент **Командная консоль Skype для бизнеса**.
    
2. В Windows PowerShell введите команду:
    
  ```
  Import-Module "CDBurn\OCO\amd64\Support"
  ```

    > [!TIP]
    > Успешные загрузки модуля, вы вернетесь в командной строке Windows PowerShell. Чтобы убедиться, что модуль загружен и доступен Edit-CsClsScenario, введите `Get-Help Edit-CsClsScenario`. Вы должны увидеть базовые сведения о синтаксисе использования EditCsClsScenario. 
  
3. Чтобы удалить поставщика из сценария AlwaysOn, введите:
    
  ```
  Edit-CsClsScenario -ScenarioName <string of the scenario to edit> -ProviderName <string of the provider to remove> -Remove
  ```

  Например:
    
  ```
  Edit-CsClsScenario -ScenarioName AlwaysOn -ProviderName ChatServer -Remove
  ```

   Параметры ScenarioName и ProviderName являются позиционными (т. е. их необходимо задать в ожидаемой позиции в командной строке). Имя параметра необязательно явно определять, если имя сценария находится во второй позиции, а поставщик — в третьей позиции относительно первой позиции имени командлета. Используя эту информацию, предыдущая команда вводится следующим образом:
    
  ```
  Edit-CsClsScenario AlwaysOn ChatServer -Remove
  ```

  Позиционные размещение значений параметров применяется только к - сценарий и - поставщиком. Все другие параметры нужно определить явно.
    
### <a name="to-add-a-provider-to-a-scenario-with-the-edit-clscontroller-module"></a>Добавление поставщика в сценарий с помощью командлета Edit-ClsController

1. Запустите командную консоль Skype для бизнеса: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Skype для бизнеса 2015** и щелкните элемент **Командная консоль Skype для бизнеса**.
    
2. Чтобы добавить поставщик в сценарий AlwaysOn, введите:
    
  ```
  Edit-CsClsScenario -ScenarioName <string of the scenario to edit> -ProviderName <string of the provider to add> -Level <string of type level> -Flags <string of type flags>
  ```

    Например:
    
  ```
  Edit-CsClsScenario -ScenarioName AlwaysOn -ProviderName ChatServer -Level Info -Flags TF_COMPONENT
  ```

    Значением -Loglevel может быть Fatal, Error, Warning, Info, Verbose, Debug или All. -Флаги может быть любой из флаги, поставщик поддерживает, такие как TF_COMPONENT, TF_DIAG. -Флаги может быть также все значения
    
  Предыдущий пример также можно ввести, используя позиционность командлета. Например, чтобы добавить поставщик ChatServer в сценарий AlwaysOn, введите:
    
  ```
  Edit-CsClsScenario AlwaysOn ChatServer -Level Info -Flags ALL
  ```


