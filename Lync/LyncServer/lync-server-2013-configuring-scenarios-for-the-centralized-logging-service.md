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
ms.openlocfilehash: cd3933ff81fad6947fcc4ab1ff7a7dc9ad136c39
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739229"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-scenarios-for-the-centralized-logging-service-in-lync-server-2013"></a>Настройка сценариев для централизованной службы ведения журналов в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2014-02-05_

Сценарии определяют область (глобальные, сайты, пулы или компьютеры) и поставщиков услуг, которые используются в централизованной службе ведения журнала. By using scenarios, you enable or disable tracing on providers (for example, S4, SIPStack, IM, and Presence). By configuring a scenario, you can group all of the providers for a given logical collection that address a specific problem condition. Если вы обнаружите, что сценарий необходимо изменить в соответствии с требованиями для устранения неполадок и ведения журнала, в средствах отладки Lync Server 2013 есть модуль Windows PowerShell с именем *клсконтроллер. PSM1* , который содержит функцию с именем *Edit-ксклссценарио*. The purpose of the module is to edit the properties of the named scenario. Examples of how this module works are provided in this topic. Средства отладки Lync Server 2013 загружаются по следующей ссылке:[http://go.microsoft.com/fwlink/?LinkId=285257](http://go.microsoft.com/fwlink/?linkid=285257)

<div>


> [!IMPORTANT]  
> Для любой области действия (глобальной, области узла, пула и компьютера) одновременно можно использовать не больше двух сценариев. Чтобы определить, какие сценарии выполняются в настоящее время, используйте Windows PowerShell и <A href="https://docs.microsoft.com/powershell/module/skype/Get-CsClsScenario">Get-ксклссценарио</A>. Используя Windows PowerShell и <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsClsScenario">Set-ксклссценарио</A>, вы можете динамически менять, какие сценарии запущены. Это можно сделать во время сеанса ведения журнала, чтобы скорректировать собираемые данные и поставщиков, от которых они собираются.



</div>

Для запуска функций централизованной службы ведения журналов с помощью командной консоли Lync Server вы должны быть членом группы безопасности Ксадминистратор или Кссерверадминистратор (или настраиваемой роли RBAC), содержащей либо из этих двух групп. Чтобы возвратить список всех ролей RBAC, которым назначен этот командлет, включая любые пользовательские роли RBAC, созданные пользователем, выполните следующую команду из командной консоли Lync Server Management Shell или Windows PowerShell.

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Lync Server 2013 cmdlet"}

Например:

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}

The remainder of this topic focuses on how to define a scenario, modify a scenario, retrieve what scenarios are running, remove a scenario, and specify what a scenario contains to optimize your troubleshooting. Существует два способа вывести централизованные команды службы ведения журнала. \\По умолчанию вы можете использовать файл клсконтроллер. exe, который находится в папке C: Program Files\\, которые представляют\\собой общие файлы Microsoft\\Lync Server 2013 клсажент. Кроме того, вы можете использовать командную консоль Lync Server для выдаче команды Windows PowerShell. Важное отличие заключается в том, что при использовании Клсконтроллер. exe в командной строке имеется ограниченный выбор доступных сценариев. Если вы используете Windows PowerShell, вы можете определить новые сценарии для использования в сеансах ведения журнала.

Как было представлено в [обзоре централизованной службы ведения журналов в Lync Server 2013](lync-server-2013-overview-of-the-centralized-logging-service.md), элементы сценария описаны ниже.

  - **Поставщики**   если вы знакомы с окслогжер, поставщики — это компоненты, которые вы указываете, чтобы сообщить окслогжер о том, что механизм трассировки должен собирать журналы. Поставщики — это те же компоненты, а во многих случаях их имя совпадает с компонентами в OCSLogger. Если вы не знакомы с Окслогжер, поставщики являются компонентами, специфичными для серверной роли, из которой Служба централизованного ведения журналов может собирать журналы. Подробнее о настройке поставщиков вы узнаете в разделе [Настройка служб централизованного ведения журналов в Lync Server 2013](lync-server-2013-configuring-providers-for-centralized-logging-service.md).

  - **Identity**   параметр — Identity задает область и имя сценария. Например, вы можете задать глобальную область ("global") и задать для сценария идентификатор "LyssServiceScenario". Если объединить эти два параметра, выполните параметр Identity (например, "global/LyssServiceScenario").
    
    При необходимости можно использовать параметры –Name и –Parent. Параметр Name задается для уникальной идентификации сценария. Если используется параметр Name, необходимо также использовать параметр Parent, чтобы добавить сценарий в глобальную область или область узла.
    
    <div>
    

    > [!IMPORTANT]  
    > Если используются параметры Name и Parent, вы не можете применять параметр <STRONG>–Identity</STRONG>.

    
    </div>

<div>

## <a name="to-create-a-new-scenario-with-the-new-csclsscenario-cmdlet"></a>Создание сценария с помощью командлета New-CsClsScenario

1.  Запустите командную консоль Lync Server Management Shell: нажмите кнопку **Пуск**, выберите **все программы**, а затем — **Microsoft Lync Server 2013**, а затем — **Командная консоль Lync Server Management Shell**.

2.  Чтобы создать сценарий для сеанса ведения журналов, используйте [New-CsClsProvider](https://docs.microsoft.com/powershell/module/skype/New-CsClsProvider) и задайте имя сценария (т. е. его уникальный идентификатор). Выберите тип формата ведения журнала в WPP (т. е. препроцессор трассировки ПО Windows, значение по умолчанию), EventLog (т. е. формат журнала событий Windows) или IISLog (т. е. формат ASCII на основе формата IIS). Затем задайте уровень (как указано в подразделе "Уровни ведения журнала" в этом разделе) и флаги (см. "Флаги" в этом разделе).
    
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

1.  Запустите командную консоль Lync Server Management Shell: нажмите кнопку **Пуск**, выберите **все программы**, а затем — **Microsoft Lync Server 2013**, а затем — **Командная консоль Lync Server Management Shell**.

2.  You are limited to two scenarios per scope. However, you are not limited to a set number of providers. In this example, assume that we have created three providers, and you want to assign all three to the scenario you are defining. The provider variable names are LyssProvider, ABServerProvider, and SIPStackProvider. Чтобы определить сценарий и назначить ему несколько поставщиков, введите следующую команду в командной консоли Lync Server Management Shell или в командную строке Windows PowerShell.
    
        New-CsClsScenario -Identity "site:Redmond/CollectDataScenario" -Provider @{Add=$LyssProvider, $ABServerProvider,  $SIPStackProvider}
    
    <div>
    

    > [!NOTE]  
    > Так как она известна в Windows PowerShell, правило создания хэш-таблицы значений <CODE>@{&lt;variable&gt;=&lt;value1&gt;, &lt;value2&gt;, &lt;value&gt;...}</CODE> называется <EM>Сплаттинг</EM>. Подробные сведения о сплаттинг в Windows PowerShell можно найти <A href="http://go.microsoft.com/fwlink/p/?linkid=267760">http://go.microsoft.com/fwlink/p/?LinkId=267760</A>в разделе.

    
    </div>

</div>

<div>

## <a name="to-modify-an-existing-scenario-with-the-set-csclsscenario-cmdlet"></a>Изменение существующего сценария с помощью командлета Set-CsClsScenario

1.  Запустите командную консоль Lync Server Management Shell: нажмите кнопку **Пуск**, выберите **все программы**, а затем — **Microsoft Lync Server 2013**, а затем — **Командная консоль Lync Server Management Shell**.

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

1.  Запустите командную консоль Lync Server Management Shell: нажмите кнопку **Пуск**, выберите **все программы**, а затем — **Microsoft Lync Server 2013**, а затем — **Командная консоль Lync Server Management Shell**.

2.  Если вы хотите удалить сценарий, определенный ранее, введите следующую команду:
    
        Remove-CsClsScenario -Identity <name of scope and scenario>
    
    Например, чтобы удалить заданный сценарий site:Redmond/LyssServiceScenario:
    
        Remove-CsClsScenario -Identity "site:Redmond/LyssServiceScenario"

Командлет **Remove-CsClsScenario** удаляет указанный сценарий, но полученные трассировки все еще доступны в журналах.

</div>

<div>

## <a name="to-load-and-unload-the-edit-csclsscenario-cmdlet-using-the-clscontrollerpsm1-module"></a>Загрузка и выгрузка командлета Edit-Ксклссценарио с помощью модуля Клсконтроллер. PSM1

1.  Запустите командную консоль Lync Server Management Shell: нажмите кнопку **Пуск**, выберите **все программы**, а затем — **Microsoft Lync Server 2013**, а затем — **Командная консоль Lync Server Management Shell**.
    
    <div>
    

    > [!IMPORTANT]  
    > Модуль Клсконтроллер. PSM1 предоставляется в виде отдельного веб-файла для загрузки. Модуль входит в состав средств отладки Lync Server 2013. По умолчанию инструменты отладки устанавливаются в каталоге C:\Program Филес\линк Server 2013 \ Отладка.

    
    </div>

2.  В Windows PowerShell введите:
    
        Import-Module "C:\Program Files\Lync Server 2013\Debugging Tools\ClsController.psm1"
    
    <div>
    

    > [!TIP]  
    > Успешная загрузка модуля возвращает вас в командную команду Windows PowerShell. Чтобы убедиться в том, что модуль загружен и что он доступен для редактирования, Ксклссценарио <CODE>Get-Help Edit-CsClsScenario</CODE>, введите. Вы должны увидеть базовые сведения о синтаксисе использования EditCsClsScenario.

    
    </div>

3.  Чтобы выгрузить модули, введите:
    
        Remove-Module ClsController
    
    <div>
    

    > [!TIP]  
    > Успешная выгрузка модуля возвращает вас в командную команду Windows PowerShell. Чтобы убедиться в том, что модуль выгружен, введите <CODE>Get-Help Edit-CsClsScenario</CODE>. Windows PowerShell попытается найти справку для командлета и не будет выполнена.

    
    </div>

</div>

<div>

## <a name="to-remove-an-existing-provider-from-a-scenario-with-the-edit-clscontroller-module"></a>Удаление существующего поставщика из сценария с помощью командлета Edit-ClsController

1.  Запустите командную консоль Lync Server Management Shell: нажмите кнопку **Пуск**, выберите **все программы**, а затем — **Microsoft Lync Server 2013**, а затем — **Командная консоль Lync Server Management Shell**.

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

1.  Запустите командную консоль Lync Server Management Shell: нажмите кнопку **Пуск**, выберите **все программы**, а затем — **Microsoft Lync Server 2013**, а затем — **Командная консоль Lync Server Management Shell**.

2.  Чтобы добавить поставщик в сценарий AlwaysOn, введите:
    
        Edit-CsClsScenario -ScenarioName <string of the scenario to edit> -ProviderName <string of the provider to add> -Level <string of type level> -Flags <string of type flags>
    
    Например:
    
        Edit-CsClsScenario -ScenarioName AlwaysOn -ProviderName ChatServer -Level Info -Flags TF_COMPONENT
    
    \-Логлевел может иметь тип Неустранимая, ошибка, предупреждение, сведения, подробный, отладочный или все. – Флаги могут быть любыми флагами, которые поддерживаются поставщиком, например\_TF Component,\_TF DIAG. Для параметра –Flags также можно указать значение ALL
    
    Предыдущий пример также можно ввести, используя позиционность командлета. Например, чтобы добавить поставщик ChatServer в сценарий AlwaysOn, введите:
    
        Edit-CsClsScenario AlwaysOn ChatServer -Level Info -Flags ALL

</div>

</div>

<span> </span>

</div>

</div>

</div>

