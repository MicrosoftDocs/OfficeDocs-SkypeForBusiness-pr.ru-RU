---
title: Настройка сценариев для централизованной службы ведения журнала в Skype для бизнеса Server 2015 г.
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
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
description: Сводка. Узнайте, как создавать, изменять и удалять сценарии для централизованной службы ведения журнала в Skype для бизнеса Server 2015 г.
ms.openlocfilehash: ecd96dc849030cb035f965c8cb52eb7607bd9667
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/25/2022
ms.locfileid: "65676361"
---
# <a name="configure-scenarios-for-the-centralized-logging-service-in-skype-for-business-server-2015"></a>Настройка сценариев для централизованной службы ведения журнала в Skype для бизнеса Server 2015 г.

**Сводка:** Узнайте, как создавать, изменять и удалять сценарии для централизованной службы ведения журнала в Skype для бизнеса Server 2015.

Сценарии определяют область (глобальную, сайт, пул или компьютер) и поставщики для использования в централизованной службе ведения журнала. С помощью сценариев вы включаете и отключаете трассировку поставщиков (например, S4, SIPStack, мгновенных сообщений и сведений о присутствии). Настроив сценарий вы можете сгруппировать все поставщики заданной логической коллекции, которые решают определенную проблему. Если вы обнаружите, что сценарий необходимо изменить в соответствии с требованиями к устранению неполадок и ведении журнала, средства отладки Skype для бизнеса Server 2015 предоставляют модуль Windows PowerShell с именем ClsScenarioEdit.psm1, содержащий функцию с именемEdit-CsClsScenario. Предназначение этого модуля — изменение свойств именованного сценария. Примеры работы этого модуля представлены в этом разделе. Скачайте Skype для бизнеса Server отладки 2015, [](https://go.microsoft.com/fwlink/p/?LinkId=285257) прежде чем продолжить.

> [!IMPORTANT]
> Для любой области действия (глобальной, области узла, пула и компьютера) одновременно можно использовать не больше двух сценариев. Чтобы определить, какие сценарии выполняются в данный момент, используйте Windows PowerShell [и Get-CsClsScenario](/powershell/module/skype/get-csclsscenario). С помощью Windows PowerShell [Set-CsClsScenario](/powershell/module/skype/set-csclsscenario) можно динамически изменять выполняемые сценарии. Это можно сделать во время сеанса ведения журнала, чтобы скорректировать собираемые данные и поставщиков, от которых они собираются.

Чтобы запустить функции централизованной службы ведения журнала с помощью командной консоли Skype для бизнеса Server, необходимо быть членом групп безопасности CsAdministrator или CsServerAdministrator на основе ролей (RBAC) или настраиваемой роли RBAC, которая содержит эти две группы. Чтобы получить список всех ролей RBAC, которым был назначен этот командлет, включая пользовательские роли RBAC, созданные вами самостоятельно, выполните следующую команду из командной консоли Skype для бизнеса Server или Windows PowerShell запроса:

```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Skype for Business Server 2015 cmdlet"}
```

Например:

```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}
```

Остальная часть этого раздела посвящена определению сценария, изменению сценария, получению сведений о выполняемых сценариях, удалению сценария указанию содержимого сценария для оптимизации устранения неполадок. Командную консоль Skype для бизнеса Server можно использовать для Windows PowerShell команд. При использовании Windows PowerShell можно определить новые сценарии для использования в сеансах ведения журнала.

Как было [представлено в централизованной службе ведения журнала Skype для бизнеса 2015 г.](centralized-logging-service.md), ниже перечислены элементы сценария.

- **Поставщиков** Если вы знакомы с OCSLogger, поставщики — это компоненты, которые вы решили сообщить OCSLogger, из чего подсистема трассировки должна собирать журналы. Поставщики — это те же компоненты, а во многих случаях их имя совпадает с компонентами в OCSLogger. Если вы не знакомы с OCSLogger, поставщики — это компоненты роли сервера, из которых централизованная служба ведения журнала может собирать журналы. Дополнительные сведения о конфигурации поставщиков см. в разделе "Настройка поставщиков для централизованной службы ведения журнала [в Skype для бизнеса Server 2015 г."](configure-providers.md).

- **Идентичности** Параметр -Identity задает область и имя сценария. Например, можно задать область "глобальный" и определить сценарий с помощью LyssServiceScenario. При объединении этих двух элементов определяется идентификатор (например, global/LyssServiceScenario).

    При необходимости можно использовать параметры -Name и -Parent. Параметр Name задается для уникальной идентификации сценария. Если используется параметр Name, необходимо также использовать параметр Parent, чтобы добавить сценарий в глобальную область или область узла.

    > [!IMPORTANT]
    > При использовании параметров Name и Parent нельзя использовать **параметр -Identity** .

## <a name="to-create-a-new-scenario-with-the-new-csclsscenario-cmdlet"></a>Создание сценария с помощью командлета New-CsClsScenario

1. Запустите Skype для бизнеса Server management Shell: нажмите кнопку "Пуск **",** щелкните "Все программы **", выберите** Skype для бизнеса **2015**, а затем щелкните **Skype для бизнеса Server Management Shell**.

2. Чтобы создать сценарий для сеанса ведения журналов, используйте [New-CsClsProvider](/powershell/module/skype/new-csclsprovider) и задайте имя сценария (т. е. его уникальный идентификатор). Выберите тип формата ведения журнала в WPP (т. е. препроцессор трассировки ПО Windows, значение по умолчанию), EventLog (т. е. формат журнала событий Windows) или IISLog (т. е. формат ASCII на основе формата IIS). Затем задайте уровень (как указано в подразделе "Уровни ведения журнала" в этом разделе) и флаги (см. "Флаги" в этом разделе).

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

## <a name="to-create-a-new-scenario-with-multiple-providers-with-the-new-csclsscenario-cmdlet"></a>Создание сценария с несколькими поставщиками с помощью командлета New-CsClsScenario

1. Запустите Skype для бизнеса Server management Shell: нажмите кнопку "Пуск **",** щелкните "Все программы **", выберите** Skype для бизнеса **2015**, а затем щелкните **Skype для бизнеса Server Management Shell**.

2. Можно использовать не больше двух сценариев для области действия. Однако число поставщиков не ограничено. В этом примере предположим, что мы создали три поставщика и хотим назначить все три из них определяемому вами сценарию. Имена переменных поставщиков: LyssProvider, ABServerProvider и SIPStackProvider. Чтобы определить и назначить несколько поставщиков для сценария, введите следующую команду в командной Skype для бизнеса Server или Windows PowerShell командной строке:

   ```PowerShell
   New-CsClsScenario -Identity "site:Redmond/CollectDataScenario" -Provider @{Add=$LyssProvider, $ABServerProvider,  $SIPStackProvider}
   ```

    > [!NOTE]
    > Как известно в Windows PowerShell, `@{<variable>=<value1>, <value2>, <value>...}` соглашение о создании хэш-таблицы значений с помощью называется assplatting. Дополнительные сведения о сплаттинге в Windows PowerShell см. в разделе [https://go.microsoft.com/fwlink/p/?LinkId=267760](/previous-versions/technet-magazine/gg675931(v=msdn.10)).

## <a name="to-modify-an-existing-scenario-with-the-set-csclsscenario-cmdlet"></a>Изменение существующего сценария с помощью командлета Set-CsClsScenario

1. Запустите Skype для бизнеса Server management Shell: нажмите кнопку "Пуск **",** щелкните "Все программы **", выберите** Skype для бизнеса **2015**, а затем щелкните **Skype для бизнеса Server Management Shell**.

2. Можно использовать не больше двух сценариев для области действия. Вы можете изменить выполняемые сценарии в любое время даже во время сеанса ведения журналов. Если переопределить выполняемые сценарии, текущий сеанс перестанет использовать удаленный сценарий и начнет применять новый сценарий. Однако данные ведения журналов, полученные с помощью удаленного сценария, останутся в полученных журналах. Чтобы определить новый сценарий, выполните следующие действия (то есть при условии, что добавлен уже определенный поставщик с именем S4Provider).

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

## <a name="to-remove-an-existing-scenario-with-the-remove-csclsscenario-cmdlet"></a>Удаление существующего сценария с помощью командлета Remove-CsClsScenario

1. Запустите Skype для бизнеса Server management Shell: нажмите кнопку "Пуск **",** щелкните "Все программы **", выберите** Skype для бизнеса **2015**, а затем щелкните **Skype для бизнеса Server Management Shell**.

2. Если вы хотите удалить сценарий, определенный ранее, введите следующую команду:

   ```PowerShell
   Remove-CsClsScenario -Identity <name of scope and scenario>
   ```

    Например, чтобы удалить заданный сценарий site:Redmond/LyssServiceScenario:

   ```PowerShell
   Remove-CsClsScenario -Identity "site:Redmond/LyssServiceScenario"
   ```

Командлет **Remove-CsClsScenario** удаляет указанный сценарий, но полученные трассировки все еще доступны в журналах.

## <a name="to-load-and-unload-the-edit-csclsscenario-cmdlet-using-the-clsscenarioeditpsm1-module"></a>Загрузка и выгрузка Edit-CsClsScenario с помощью модуля ClsScenarioEdit.psm1

1. Запустите Skype для бизнеса Server management Shell: нажмите кнопку "Пуск **",** щелкните "Все программы **", выберите** Skype для бизнеса **2015**, а затем щелкните **Skype для бизнеса Server Management Shell**.

    > [!IMPORTANT]
    > Модуль ClsScenarioEdit.psm1 предоставляется в виде отдельного веб-скачивания. Модуль является частью средств Skype для бизнеса Server 2015. По умолчанию средства отладки устанавливаются в каталог C:\Program Files\Skype для бизнеса Server 2015\Debugging Tools.

2. В Windows PowerShell введите:

   ```PowerShell
   Import-Module "CDBurn\OCO\amd64\Support"
   ```

    > [!TIP]
    > После успешной загрузки модуля вы йдите в Windows PowerShell командной строке. Чтобы убедиться, что модуль загружен и что Edit-CsClsScenario доступен, введите .`Get-Help Edit-CsClsScenario` Вы должны увидеть базовые сведения о синтаксисе использования EditCsClsScenario.

3. Чтобы выгрузить модули, введите:

   ```PowerShell
   Remove-Module ClsController
   ```

    > [!TIP]
    > После успешной выгрузки модуля вы йдите в Windows PowerShell командной строке. Чтобы убедиться, что модуль выгружен, введите  `Get-Help Edit-CsClsScenario`. Windows PowerShell попытается найти справку для командлета и завершится сбоем.

## <a name="to-remove-an-existing-provider-from-a-scenario-with-the-edit-clscontroller-module"></a>Удаление существующего поставщика из сценария с помощью командлета Edit-ClsController

1. Запустите Skype для бизнеса Server management Shell: нажмите кнопку "Пуск **",** щелкните "Все программы **", выберите** Skype для бизнеса **2015**, а затем щелкните **Skype для бизнеса Server Management Shell**.

2. В Windows PowerShell введите:

   ```PowerShell
   Import-Module "CDBurn\OCO\amd64\Support"
   ```

    > [!TIP]
    > После успешной загрузки модуля вы йдите в Windows PowerShell командной строке. Чтобы убедиться, что модуль загружен и что Edit-CsClsScenario доступен, введите .`Get-Help Edit-CsClsScenario` Вы должны увидеть базовые сведения о синтаксисе использования EditCsClsScenario.

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

## <a name="to-add-a-provider-to-a-scenario-with-the-edit-clscontroller-module"></a>Добавление поставщика в сценарий с помощью командлета Edit-ClsController

1. Запустите Skype для бизнеса Server management Shell: нажмите кнопку "Пуск **",** щелкните "Все программы **", выберите** Skype для бизнеса **2015**, а затем щелкните **Skype для бизнеса Server Management Shell**.

2. Чтобы добавить поставщик в сценарий AlwaysOn, введите:

   ```PowerShell
   Edit-CsClsScenario -ScenarioName <string of the scenario to edit> -ProviderName <string of the provider to add> -Level <string of type level> -Flags <string of type flags>
   ```

    Например:

   ```PowerShell
   Edit-CsClsScenario -ScenarioName AlwaysOn -ProviderName ChatServer -Level Info -Flags TF_COMPONENT
   ```

    Значением -Loglevel может быть Fatal, Error, Warning, Info, Verbose, Debug или All. - Флагами могут быть любые флаги, поддерживаемые поставщиком, например TF_COMPONENT, TF_DIAG. -Flags также может иметь значение ALL

   Предыдущий пример также можно ввести, используя позиционность командлета. Например, чтобы добавить поставщик ChatServer в сценарий AlwaysOn, введите:

   ```PowerShell
   Edit-CsClsScenario AlwaysOn ChatServer -Level Info -Flags ALL
   ```
