---
title: Настройка сценариев для централизованной службы ведения журналов в Skype для бизнеса Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: 'Сводка: сведения о том, как создавать, изменять и удалять сценарии централизованной службы ведения журналов в Skype для бизнеса Server 2015.'
ms.openlocfilehash: b7cfcbc85df7d66374d2bf33d572b9e91b30edde
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816598"
---
# <a name="configure-scenarios-for-the-centralized-logging-service-in-skype-for-business-server-2015"></a>Настройка сценариев для централизованной службы ведения журналов в Skype для бизнеса Server 2015
 
**Сводка:** Сведения о том, как создавать, изменять и удалять сценарии централизованной службы ведения журналов в Skype для бизнеса Server 2015.
  
Сценарии определяют область (глобальные, сайты, пулы или компьютеры) и поставщиков услуг, которые используются в централизованной службе ведения журнала. By using scenarios, you enable or disable tracing on providers (for example, S4, SIPStack, IM, and Presence). By configuring a scenario, you can group all of the providers for a given logical collection that address a specific problem condition. Если вы обнаружите, что сценарий нужно изменить в соответствии с требованиями для устранения неполадок и ведения журнала, в средствах отладки Skype для Business Server 2015 есть модуль Windows PowerShell с именем Клссценариоедит. psm1, который содержит функцию Намедедит-Ксклссценарио. The purpose of the module is to edit the properties of the named scenario. Examples of how this module works are provided in this topic. Перед тем как приступить к работе, загрузите [средства отладки](https://go.microsoft.com/fwlink/p/?LinkId=285257) Skype для бизнеса Server 2015.
  
> [!IMPORTANT]
> Для любой области действия (глобальной, области узла, пула и компьютера) одновременно можно использовать не больше двух сценариев. Чтобы определить, какие сценарии выполняются в настоящее время, используйте Windows PowerShell и [Get-ксклссценарио](https://docs.microsoft.com/powershell/module/skype/get-csclsscenario?view=skype-ps). Используя Windows PowerShell и [Set-ксклссценарио](https://docs.microsoft.com/powershell/module/skype/set-csclsscenario?view=skype-ps), вы можете динамически менять, какие сценарии запущены. Это можно сделать во время сеанса ведения журнала, чтобы скорректировать собираемые данные и поставщиков, от которых они собираются. 
  
Для запуска функций централизованной службы ведения журналов с помощью командной консоли Skype для бизнеса Server вы должны быть членами либо группами безопасности Ксадминистратор, либо Кссерверадминистратор для управления доступом на основе ролей (RBAC) или настраиваемой роли RBAC, которая один из этих двух групп. Чтобы возвратить список всех ролей RBAC, которым назначен этот командлет, включая любые пользовательские роли RBAC, созданные пользователем, выполните следующую команду в командной консоли управления Skype для бизнеса Server или Windows PowerShell.
  
```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Skype for Business Server 2015 cmdlet"}
```

Например:
  
```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}
```

The remainder of this topic focuses on how to define a scenario, modify a scenario, retrieve what scenarios are running, remove a scenario, and specify what a scenario contains to optimize your troubleshooting. Вы можете использовать командную консоль сервера Skype для бизнеса, чтобы выпустить команды Windows PowerShell. Если вы используете Windows PowerShell, вы можете определить новые сценарии для использования в сеансах ведения журнала.
  
Как это было представлено в [службе централизованного ведения журналов в Skype для бизнеса 2015](centralized-logging-service.md), элементы сценария описаны ниже.
  
- **Поставщики услуг** Если вы знакомы с Окслогжер, поставщики — это компоненты, которые вы указываете, чтобы сообщить Окслогжер о том, что ядро трассировки должно собирать журналы. Поставщики — это те же компоненты, а во многих случаях их имя совпадает с компонентами в OCSLogger. Если вы не знакомы с Окслогжер, поставщики являются компонентами, специфичными для серверной роли, из которой Служба централизованного ведения журналов может собирать журналы. Подробные сведения о настройке поставщиков можно найти в разделе [Настройка служб централизованного ведения журналов в Skype для бизнеса Server 2015](configure-providers.md).
    
- **Identity (идентификация** ) Параметр-Identity задает область и имя сценария. Например, вы можете задать область "Global" и определить сценарий с помощью "Лисссервицесценарио". При объединении двух данных вы определяете удостоверение (например, "Global/Лисссервицесценарио").
    
    При необходимости можно использовать параметры-Name и-Parent. Параметр Name задается для уникальной идентификации сценария. Если используется параметр Name, необходимо также использовать параметр Parent, чтобы добавить сценарий в глобальную область или область узла. 
    
    > [!IMPORTANT]
    > Если вы используете параметры "имя" и "родительский", нельзя использовать параметр **-Identity** .
  
### <a name="to-create-a-new-scenario-with-the-new-csclsscenario-cmdlet"></a>Создание сценария с помощью командлета New-CsClsScenario

1. Запустите командную консоль Skype для бизнеса: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Skype для бизнеса 2015** и щелкните элемент **Командная консоль Skype для бизнеса**.
    
2. Чтобы создать сценарий для сеанса ведения журналов, используйте [New-CsClsProvider](https://docs.microsoft.com/powershell/module/skype/new-csclsprovider?view=skype-ps) и задайте имя сценария (т. е. его уникальный идентификатор). Выберите тип формата ведения журнала в WPP (т. е. препроцессор трассировки ПО Windows, значение по умолчанию), EventLog (т. е. формат журнала событий Windows) или IISLog (т. е. формат ASCII на основе формата IIS). Затем задайте уровень (как указано в подразделе "Уровни ведения журнала" в этом разделе) и флаги (см. "Флаги" в этом разделе).
    
    Для этого примера сценария мы используем LyssProvider как пример переменной поставщика.
    
    Чтобы создать сценарий с помощью заданных параметров, введите следующую команду:
    
   ```PowerShell
   New-CsClsScenario -Identity <scope>/<unique scenario name> -Provider <provider variable>
   ```

    Например:
    
   ```PowerShell
   New-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider $LyssProvider
   ```

    Альтернативный формат: с помощью параметров-Name и-Parent.
    
   ```PowerShell
   New-CsClsScenario -Name "LyssServiceScenario" -Parent "site:Redmond" -Provider $LyssProvider
   ```

### <a name="to-create-a-new-scenario-with-multiple-providers-with-the-new-csclsscenario-cmdlet"></a>Создание сценария с несколькими поставщиками с помощью командлета New-CsClsScenario

1. Запустите командную консоль Skype для бизнеса: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Skype для бизнеса 2015** и щелкните элемент **Командная консоль Skype для бизнеса**.
    
2. You are limited to two scenarios per scope. However, you are not limited to a set number of providers. In this example, assume that we have created three providers, and you want to assign all three to the scenario you are defining. The provider variable names are LyssProvider, ABServerProvider, and SIPStackProvider. Чтобы определить сценарий и назначить ему несколько поставщиков, введите следующую команду в командной консоли управления Skype для бизнеса Server или Windows PowerShell.
    
   ```PowerShell
   New-CsClsScenario -Identity "site:Redmond/CollectDataScenario" -Provider @{Add=$LyssProvider, $ABServerProvider,  $SIPStackProvider}
   ```

    > [!NOTE]
    > Так как она известна в Windows PowerShell, для создания хэш-таблицы значений используется `@{<variable>=<value1>, <value2>, <value>…}` известная ассплаттинг. Подробные сведения о сплаттинг в Windows PowerShell можно найти [https://go.microsoft.com/fwlink/p/?LinkId=267760](https://go.microsoft.com/fwlink/p/?LinkId=267760)в разделе. 
  
### <a name="to-modify-an-existing-scenario-with-the-set-csclsscenario-cmdlet"></a>Изменение существующего сценария с помощью командлета Set-CsClsScenario

1. Запустите командную консоль Skype для бизнеса: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Skype для бизнеса 2015** и щелкните элемент **Командная консоль Skype для бизнеса**.
    
2. Можно использовать не больше двух сценариев для области действия. Вы можете изменить выполняемые сценарии в любое время даже во время сеанса ведения журналов. Если переопределить выполняемые сценарии, текущий сеанс перестанет использовать удаленный сценарий и начнет применять новый сценарий. Однако данные ведения журналов, полученные с помощью удаленного сценария, останутся в полученных журналах. Чтобы определить новый сценарий, сделайте следующее (то есть, предполагается добавление уже определенного поставщика с именем "S4Provider"):
    
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

1. Запустите командную консоль Skype для бизнеса: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Skype для бизнеса 2015** и щелкните элемент **Командная консоль Skype для бизнеса**.
    
2. Если вы хотите удалить сценарий, определенный ранее, введите следующую команду:
    
   ```PowerShell
   Remove-CsClsScenario -Identity <name of scope and scenario>
   ```

    Например, чтобы удалить заданный сценарий site:Redmond/LyssServiceScenario:
    
   ```PowerShell
   Remove-CsClsScenario -Identity "site:Redmond/LyssServiceScenario"
   ```

Командлет **Remove-CsClsScenario** удаляет указанный сценарий, но полученные трассировки все еще доступны в журналах.
### <a name="to-load-and-unload-the-edit-csclsscenario-cmdlet-using-the-clsscenarioeditpsm1-module"></a>Загрузка и выгрузка командлета Edit-CsClsScenario с помощью модуля ClsScenarioEdit.psm1

1. Запустите командную консоль Skype для бизнеса: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Skype для бизнеса 2015** и щелкните элемент **Командная консоль Skype для бизнеса**.
    
    > [!IMPORTANT]
    > Модуль ClsScenarioEdit.psm1 предоставляется как отдельная веб-загрузка. Модуль входит в состав средств отладки в Skype для бизнеса Server 2015. По умолчанию средства отладки устанавливаются в каталог C:\Program Files\Skype for Business Server 2015\Debugging Tools. 
  
2. В Windows PowerShell введите:
    
   ```PowerShell
   Import-Module "CDBurn\OCO\amd64\Support"
   ```

    > [!TIP]
    > Успешная загрузка модуля возвращает вас в командную команду Windows PowerShell. Чтобы убедиться в том, что модуль загружен и что он доступен для редактирования, Ксклссценарио `Get-Help Edit-CsClsScenario`, введите. Вы должны увидеть базовые сведения о синтаксисе использования EditCsClsScenario. 
  
3. Чтобы выгрузить модули, введите:
    
   ```PowerShell
   Remove-Module ClsController
   ```

    > [!TIP]
    > Успешная выгрузка модуля возвращает вас в командную команду Windows PowerShell. Чтобы убедиться в том, что модуль выгружен, введите `Get-Help Edit-CsClsScenario`. Windows PowerShell попытается найти справку для командлета и не будет выполнена. 
  
### <a name="to-remove-an-existing-provider-from-a-scenario-with-the-edit-clscontroller-module"></a>Удаление существующего поставщика из сценария с помощью командлета Edit-ClsController

1. Запустите командную консоль Skype для бизнеса: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Skype для бизнеса 2015** и щелкните элемент **Командная консоль Skype для бизнеса**.
    
2. В Windows PowerShell введите:
    
   ```PowerShell
   Import-Module "CDBurn\OCO\amd64\Support"
   ```

    > [!TIP]
    > Успешная загрузка модуля возвращает вас в командную команду Windows PowerShell. Чтобы убедиться в том, что модуль загружен и что он доступен для редактирования, Ксклссценарио `Get-Help Edit-CsClsScenario`, введите. Вы должны увидеть базовые сведения о синтаксисе использования EditCsClsScenario. 
  
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

   Позиционные размещения значений параметров применяются только к-сценарию и-поставщику. Все другие параметры нужно определить явно.
    
### <a name="to-add-a-provider-to-a-scenario-with-the-edit-clscontroller-module"></a>Добавление поставщика в сценарий с помощью командлета Edit-ClsController

1. Запустите командную консоль Skype для бизнеса: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Skype для бизнеса 2015** и щелкните элемент **Командная консоль Skype для бизнеса**.
    
2. Чтобы добавить поставщик в сценарий AlwaysOn, введите:
    
   ```PowerShell
   Edit-CsClsScenario -ScenarioName <string of the scenario to edit> -ProviderName <string of the provider to add> -Level <string of type level> -Flags <string of type flags>
   ```

    Например:
    
   ```PowerShell
   Edit-CsClsScenario -ScenarioName AlwaysOn -ProviderName ChatServer -Level Info -Flags TF_COMPONENT
   ```

    Значением -Loglevel может быть Fatal, Error, Warning, Info, Verbose, Debug или All. Флагами могут быть любые флаги, поддерживаемые поставщиком, например TF_COMPONENT, TF_DIAG. -Флаги также могут иметь значение "все"
    
   Предыдущий пример также можно ввести, используя позиционность командлета. Например, чтобы добавить поставщик ChatServer в сценарий AlwaysOn, введите:
    
   ```PowerShell
   Edit-CsClsScenario AlwaysOn ChatServer -Level Info -Flags ALL
   ```
