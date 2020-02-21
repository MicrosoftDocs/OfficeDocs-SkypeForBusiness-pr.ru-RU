---
title: 'Lync Server 2013: Настройка сценариев для централизованной службы ведения журналов'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring scenarios for the Centralized Logging Service
ms:assetid: 6c3bf826-e7fd-4002-95dc-01020641ef01
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688085(v=OCS.15)
ms:contentKeyID: 49733682
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fc58e0f29ca0a562a94f771857d88da49d616064
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42199692"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-scenarios-for-the-centralized-logging-service-in-lync-server-2013"></a>Настройка сценариев для централизованной службы ведения журналов в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2014-02-05_

В сценариях определяется область (Глобальная, на уровне сайта, в пуле или на компьютере) и какие поставщики используются в централизованной службе ведения журналов. С помощью сценариев вы включаете и отключаете трассировку поставщиков (например, S4, SIPStack, мгновенных сообщений и сведений о присутствии). Настроив сценарий вы можете сгруппировать все поставщики заданной логической коллекции, которые решают определенную проблему. Если вы обнаружите, что сценарий необходимо изменить в соответствии с требованиями к устранению неполадок и ведению журналов, средства отладки Lync Server 2013 предоставляют модуль Windows PowerShell с именем *ClsController. PSM1* , который содержит функцию с именем *Edit — CsClsScenario*. Предназначение этого модуля — изменение свойств именованного сценария. Примеры работы этого модуля представлены в этом разделе. Средства отладки Lync Server 2013 загружаются по следующей ссылке:[https://go.microsoft.com/fwlink/?LinkId=285257](https://go.microsoft.com/fwlink/?linkid=285257)

<div>


> [!IMPORTANT]  
> Для любой области действия (глобальной, области узла, пула и компьютера) одновременно можно использовать не больше двух сценариев. Чтобы определить, какие сценарии выполняются в данный момент, используйте Windows PowerShell и <A href="https://docs.microsoft.com/powershell/module/skype/Get-CsClsScenario">Get – CsClsScenario</A>. С помощью Windows PowerShell и командлета <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsClsScenario">Set — CsClsScenario</A>можно динамически изменить выполняемые сценарии. Это можно сделать во время сеанса ведения журнала, чтобы скорректировать собираемые данные и поставщиков, от которых они собираются.



</div>

Для запуска функций централизованной службы ведения журналов с помощью командной консоли Lync Server необходимо быть членом группы безопасности CsAdministrator или CsServerAdministrator с управлением доступом на основе ролей (RBAC) или настраиваемой роли RBAC, содержащей либо из этих двух групп. Чтобы получить список всех ролей RBAC, которым назначен этот командлет, включая любые созданные пользователем роли RBAC, выполните следующую команду в командной консоли Lync Server или в командной строке Windows PowerShell:

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Lync Server 2013 cmdlet"}

Например:

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}

Остальная часть этого раздела посвящена определению сценария, изменению сценария, получению сведений о выполняемых сценариях, удалению сценария указанию содержимого сценария для оптимизации устранения неполадок. Существует два способа выдача команд службы централизованного ведения журналов. Вы можете\\использовать файл CLSController. exe, расположенный по умолчанию, в папке C: Program Files\\Common Files\\Microsoft Lync Server 2013\\CLSAgent. Вы также можете использовать командную консоль Lync Server для выполнения команд Windows PowerShell. Важное отличие состоит в том, что при использовании CLSController.exe в командой строке выбор доступных сценариев ограничен. При использовании Windows PowerShell можно определять новые сценарии для использования в сеансах ведения журнала.

Как показано в статье [Обзор централизованной службы ведения журналов в Lync Server 2013](lync-server-2013-overview-of-the-centralized-logging-service.md), элементы сценария:

  - **Поставщики**   . Если вы знакомы с OCSLogger, поставщики — это компоненты, которые указывают OCSLogger, из чего система трассировки должна собирать журналы. Поставщики — это те же компоненты, а во многих случаях их имя совпадает с компонентами в OCSLogger. Если вы не знакомы с OCSLogger, поставщики — это компоненты, зависящие от роли сервера, из которых Служба централизованного ведения журналов может собирать журналы. Подробные сведения о конфигурации поставщиков приведены [в статье Настройка поставщиков для централизованной службы ведения журналов в Lync Server 2013](lync-server-2013-configuring-providers-for-centralized-logging-service.md).

  - **Identity**   параметр — Identity задает область и имя сценария. Например, вы можете задать глобальную область ("global") и задать для сценария идентификатор "LyssServiceScenario". Если объединить эти два параметра, вы полните параметр Identity (например, "global/LyssServiceScenario").
    
    При необходимости можно использовать параметры –Name и –Parent. Параметр Name задается для уникальной идентификации сценария. Если используется параметр Name, необходимо также использовать параметр Parent, чтобы добавить сценарий в глобальную область или область узла.
    
    <div>
    

    > [!IMPORTANT]  
    > Если используются параметры Name и Parent, вы не можете применять параметр <STRONG>–Identity</STRONG>.

    
    </div>

<div>

## <a name="to-create-a-new-scenario-with-the-new-csclsscenario-cmdlet"></a>Создание сценария с помощью командлета New-CsClsScenario

1.  Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.

2.  Чтобы создать новый сценарий для сеанса ведения журнала, используйте [New-CsClsProvider](https://docs.microsoft.com/powershell/module/skype/New-CsClsProvider) и определите имя сценария (то есть, как он будет однозначно идентифицирован). Выберите тип формата ведения журнала из WPP (то есть препроцессор трассировки программного обеспечения Windows и значение по умолчанию), EventLog (то есть формат журнала событий Windows) или Иислог (то есть файл в формате ASCII, основанный на формате файла журнала IIS). Затем определите уровень (как определено в разделе уровни ведения журнала в данном разделе) и флаги (как указано в разделе flags в этом разделе).
    
    Для этого примера сценария мы используем LyssProvider как пример переменной поставщика.
    
    Чтобы создать сценарий с помощью заданных параметров, введите следующую команду:
    
        New-CsClsScenario -Identity <scope>/<unique scenario name> -Provider <provider variable>
    
    Например:
    
        New-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider $LyssProvider
    
    Альтернативный формат с использованием –Name и –Parent:
    
        New-CsClsScenario -Name "LyssServiceScenario" -Parent "site:Redmond" -Provider $LyssProvider

</div>

<div>

## <a name="to-create-a-new-scenario-with-multiple-providers-with-the-new-csclsscenario-cmdlet"></a>Создание сценария с несколькими поставщиками с помощью командлета New-CsClsScenario

1.  Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.

2.  Можно использовать не больше двух сценариев для области действия. Однако число поставщиков не ограничено. В этом примере предположим, что мы создали три поставщика и хотим назначить все три из них определяемому вами сценарию. Имена переменных поставщиков: LyssProvider, ABServerProvider и SIPStackProvider. Чтобы определить и назначить несколько поставщиков сценарию, введите следующую команду в командной консоли Lync Server или в командной строке Windows PowerShell:
    
        New-CsClsScenario -Identity "site:Redmond/CollectDataScenario" -Provider @{Add=$LyssProvider, $ABServerProvider,  $SIPStackProvider}
    
    <div>
    

    > [!NOTE]  
    > Так как она известна в Windows PowerShell, соглашение о создании хэш-таблицы значений с помощью <CODE>@{&lt;variable&gt;=&lt;value1&gt;, &lt;value2&gt;, &lt;value&gt;...}</CODE> называется <EM>сплаттингом</EM>. Подробнее о сплаттингом в Windows PowerShell можно узнать <A href="https://go.microsoft.com/fwlink/p/?linkid=267760">https://go.microsoft.com/fwlink/p/?LinkId=267760</A>в статье.

    
    </div>

</div>

<div>

## <a name="to-modify-an-existing-scenario-with-the-set-csclsscenario-cmdlet"></a>Изменение существующего сценария с помощью командлета Set-CsClsScenario

1.  Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.

2.  Можно использовать не больше двух сценариев для области действия. Вы можете изменить выполняемые сценарии в любое время даже во время сеанса ведения журналов. Если переопределить выполняемые сценарии, текущий сеанс перестанет использовать удаленный сценарий и начнет применять новый сценарий. Однако данные ведения журналов, полученные с помощью удаленного сценария, останутся в полученных журналах. Чтобы определить новый сценарий, выполните следующие действия (если уже определенный поставщик "S4Provider" уже добавлен):
    
        Set-CsClsScenario -Identity <name of scope and scenario defined by New-CsClsScenario> -Provider @{Add=<new provider to add>}
    
    Например:
    
        Set-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider @{Add=$S4Provider}
    
    Если вы хотите заменить поставщики, определить один поставщика или разделенный запятыми список поставщиков, чтобы заменить текущий набор. Если вы хотите только заменить один из нескольких поставщиков, добавьте текущие поставщики с новыми поставщиками, чтобы создать новый набор поставщиков, который содержит новые и существующие поставщики. Чтобы заменить все поставщики новым набором, введите следующую команду:
    
        Set-CsClsScenario -Identity <name of scope and scenario defined by New-CsClsScenario> -Provider @{Replace=<providers to replace existing provider set>}
    
    Например, чтобы заменить текущий набор из $LyssProvider, $ABServerProvider и $SIPStackProvider на $LyssServiceProvider, выполните следующую команду:
    
        Set-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider @{Replace=$LyssServiceProvider}
    
    Чтобы заменить только поставщик $LyssProvider из текущего набора $LyssProvider, $ABServerProvider и $SIPStackProvider на $LyssServiceProvider, введите следующую команду:
    
        Set-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider @{Replace=$LyssServiceProvider, $ABServerProvider, $SIPStackProvider}

</div>

<div>

## <a name="to-remove-an-existing-scenario-with-the-remove-csclsscenario-cmdlet"></a>Удаление существующего сценария с помощью командлета Remove-CsClsScenario

1.  Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.

2.  Если вы хотите удалить сценарий, определенный ранее, введите следующую команду:
    
        Remove-CsClsScenario -Identity <name of scope and scenario>
    
    Например, чтобы удалить заданный сценарий site:Redmond/LyssServiceScenario:
    
        Remove-CsClsScenario -Identity "site:Redmond/LyssServiceScenario"

Командлет **Remove-CsClsScenario** удаляет указанный сценарий, но полученные трассировки все еще доступны в журналах.

</div>

<div>

## <a name="to-load-and-unload-the-edit-csclsscenario-cmdlet-using-the-clscontrollerpsm1-module"></a>Загрузка и выгрузка командлета Edit-CsClsScenario с помощью модуля ClsController.psm1

1.  Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.
    
    <div>
    

    > [!IMPORTANT]  
    > Модуль ClsController.psm1 предоставляется как отдельная веб-загрузка. Модуль входит в состав средств отладки Lync Server 2013. По умолчанию средства отладки устанавливаются в каталог C:\Program Files\Lync Server 2013\Debugging Tools.

    
    </div>

2.  В Windows PowerShell введите:
    
        Import-Module "C:\Program Files\Lync Server 2013\Debugging Tools\ClsController.psm1"
    
    <div>
    

    > [!TIP]  
    > При успешной загрузке модуля вы вернетесь в командную строку Windows PowerShell. Чтобы убедиться, что модуль загружен и доступен параметр Edit-CsClsScenario, введите <CODE>Get-Help Edit-CsClsScenario</CODE>. Вы должны увидеть базовые сведения о синтаксисе использования EditCsClsScenario.

    
    </div>

3.  Чтобы выгрузить модули, введите:
    
        Remove-Module ClsController
    
    <div>
    

    > [!TIP]  
    > При успешной выгрузке модуля вы вернетесь в командную строку Windows PowerShell. Чтобы убедиться, что модуль выгружается, введите <CODE>Get-Help Edit-CsClsScenario</CODE>. Windows PowerShell будет пытаться определить расположение справки для командлета и выполнить ошибку.

    
    </div>

</div>

<div>

## <a name="to-remove-an-existing-provider-from-a-scenario-with-the-edit-clscontroller-module"></a>Удаление существующего поставщика из сценария с помощью командлета Edit-ClsController

1.  Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.

2.  Чтобы удалить поставщика из сценария AlwaysOn, введите:
    
        Edit-CsClsScenario -ScenarioName <string of the scenario to edit> -ProviderName <string of the provider to remove> -Remove
    
    Например:
    
        Edit-CsClsScenario -ScenarioName AlwaysOn -ProviderName ChatServer -Remove
    
    Параметры ScenarioName и ProviderName являются позиционными (т. е. их необходимо задать в ожидаемой позиции в командной строке). Имя параметра необязательно явно определять, если имя сценария находится во второй позиции, а поставщик — в третьей позиции относительно первой позиции имени командлета. Используя эту информацию, предыдущая команда вводится следующим образом:
    
        Edit-CsClsScenario AlwaysOn ChatServer -Remove
    
    Позиционное размещение значений параметров применяется только к параметрам –Scenario и –Provider. Все другие параметры нужно определить явно.

</div>

<div>

## <a name="to-add-a-provider-to-a-scenario-with-the-edit-clscontroller-module"></a>Добавление поставщика в сценарий с помощью командлета Edit-ClsController

1.  Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.

2.  Чтобы добавить поставщик в сценарий AlwaysOn, введите:
    
        Edit-CsClsScenario -ScenarioName <string of the scenario to edit> -ProviderName <string of the provider to add> -Level <string of type level> -Flags <string of type flags>
    
    Например:
    
        Edit-CsClsScenario -ScenarioName AlwaysOn -ProviderName ChatServer -Level Info -Flags TF_COMPONENT
    
    \-LogLevel может иметь тип Неустранимая ошибка, ошибка, предупреждение, info, Verbose, Debug или ALL. — Flags могут быть любыми флагами, которые поддерживает поставщик, например TF\_Component, TF\_DIAG. Для параметра –Flags также можно указать значение ALL
    
    Предыдущий пример также можно ввести, используя позиционность командлета. Например, чтобы добавить поставщик ChatServer в сценарий AlwaysOn, введите:
    
        Edit-CsClsScenario AlwaysOn ChatServer -Level Info -Flags ALL

</div>

</div>

<span> </span>

</div>

</div>

</div>

