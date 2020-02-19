---
title: Управление конфигурацией компьютера, сайта и глобальной службы централизованного ведения журналов
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing computer, site and global Centralized Logging Service configuration
ms:assetid: 93b9a354-9aea-4b3a-a4fe-68a89f436196
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688138(v=OCS.15)
ms:contentKeyID: 49733738
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f2d33a67b0b7e8c7e2771fbdc1055d003717dbb1
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42136176"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="managing-computer-site-and-global-centralized-logging-service-configuration-in-lync-server-2013"></a>Управление конфигурацией компьютера, сайта и глобальной централизованной службы ведения журналов в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2014-02-04_

Централизованная служба ведения журналов может выполняться в области, включающей в себя один компьютер, пул компьютеров, на уровне сайта (то есть определенный сайт, такой как Redmond сайта, содержащий коллекцию компьютеров и пулов в развертывании) или в глобальной области (то есть , все компьютеры и пулы в развертывании.

Чтобы настроить область Службы централизованного ведения журналов с помощью Командная консоль Lync Server, необходимо быть членом группы безопасности CsAdministrator или CsServerAdministrator с контролем на основе ролей (RBAC) или настраиваемой ролью RBAC, содержащей Любая из этих двух групп. Чтобы получить список всех ролей RBAC, которым назначен этот командлет (включая все самостоятельно созданные роли RBAC), выполните следующую команду в командной консоли Lync Server или в командной строке Windows PowerShell:

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "<Lync Server 2013 cmdlet>"}

Например:

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}

<div>


> [!NOTE]
> Windows PowerShell предоставляет дополнительные параметры и дополнительные параметры настройки, недоступные с помощью CLSController. exe. CLSController предлагает быстрый способ выполнения команд, однако набор этих команд ограничен. Windows PowerShell не ограничивается только командой, доступной для командного процессора CLSController, и предоставляет широкий набор команд и более широкий набор параметров. Например, средство CLSController.exe предоставляет параметры области для компьютеров (–computers) и пулов (–pools). С помощью Windows PowerShell можно указывать компьютеры или пулы в большинстве команд, а также при определении новых сценариев (CLSController имеет конечное число сценариев, не изменяемых пользователями), можно определить сайт или глобальную область. Эта мощная функция Windows PowerShell позволяет определить сценарий для сайта или глобальной области, но ограничить фактический вход на компьютер или в пул.<BR>Существуют фундаментальные различия между командами командной строки, которые можно запускать в Windows PowerShell или CLSController. Windows PowerShell предоставляет богатый метод настройки и определения сценариев, а также повторное использование этих сценариев для сценариев устранения неполадок. Хотя CLSController позволяет быстро и эффективно выполнять команды и получать результаты, набор команд этого средства ограничен командами, доступными из командной строки. В отличие от командлетов Windows PowerShell, CLSController не может определять новые сценарии, управлять областью на сайте или глобальном уровне, а также многие другие ограничения набора команд, которые не могут быть настроены динамически. Хотя CLSController предоставляет средства для быстрого выполнения, Windows PowerShell предоставляет средства для расширения функциональности централизованной службы ведения журналов помимо того, что возможно в CLSController.



</div>

Область одного компьютера можно определить во время выполнения команды [Search-CsClsLogging](https://technet.microsoft.com/library/JJ619189(v=OCS.15)), [Show-CsClsLogging](https://technet.microsoft.com/library/JJ619173(v=OCS.15)), [Start-CsClsLogging](https://technet.microsoft.com/library/JJ619190(v=OCS.15)), [Stop-CsClsLogging](https://technet.microsoft.com/library/JJ619180(v=OCS.15)), [Sync-CsClsLogging](https://technet.microsoft.com/library/JJ619169(v=OCS.15)) и [Update-CsClsLogging](https://technet.microsoft.com/library/JJ619170(v=OCS.15)) с помощью параметра – Computers. Параметр –Computers принимает разделенный запятой список полных доменных имен для целевого компьютера.

<div>


> [!TIP]
> С помощью параметра –Pools можно задать разделенный запятой список пулов, в которых должны выполняться команды ведения журнала.



</div>

Сайты и глобальные области определены в командлетах службы ведения журналов **New-**, **Set-** и **Remove-** централизованный. В следующих примерах показано, как задать область сайта и глобальную область.

<div>


> [!IMPORTANT]
> Показанные команды могут содержать параметры и концепции, описанные в других разделах. Команды в примерах предназначены для демонстрации использования параметра <STRONG>–Identity</STRONG> для определения области, а другие параметры включены для полноты и для указания области. Дополнительные сведения о командлетах <STRONG>Set-CsClsConfiguration</STRONG> см. в описании командлета <A href="https://technet.microsoft.com/library/JJ619182(v=OCS.15)">Set-CsClsConfiguration</A> в документации по применению.



</div>

<div>

## <a name="to-retrieve-the-current-centralized-logging-service-configuration"></a>Получение текущей конфигурации централизованной службы ведения журналов

1.  Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.

2.  Введите следующую команду в командной строке:
    
        Get-CsClsConfiguration

Используйте командлеты **New-CsClsConfiguration** и **Set-CsClsConfiguration** для создания новой конфигурации или для обновления существующей.

При выполнении командлета **Get-CsClsConfiguration**отображаются сведения, аналогичные приведенным на следующем снимке экрана, где в настоящее время развертывание содержит глобальную конфигурацию по умолчанию, но не определено ни одной конфигурации сайта:

![Пример выходных данных Get – CsClsConfiguration.](images/JJ688029.23f98ddc-fc48-499a-b6c5-752611f2a0b0(OCS.15).jpg "Пример выходных данных Get – CsClsConfiguration.")

</div>

<div>

## <a name="to-retrieve-the-current-centralized-logging-service-configuration-from-the-computer-local-store"></a>Получение текущей конфигурации централизованной службы ведения журналов из локального хранилища компьютера

1.  Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.

2.  Введите следующую команду в командной строке:
    
        Get-CsClsConfiguration -LocalStore

При использовании первого примера, когда **Get – CsClsConfiguration** не задает параметры, команда ссылается на центральное хранилище управления данными. Если указать параметр – Локалсторе, команда будет ссылаться на компьютер Локалсторе вместо центрального хранилища управления.

</div>

<div>

## <a name="to-retrieve-a-listing-of-scenarios-currently-defined"></a>Получение листинга сценариев, определенных в текущий момент

1.  Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.

2.  Введите следующую команду в командной строке:
    
        Get-CsClsConfiguration -Identity <scope and name> | Select-Object -ExpandProperty Scenarios
    
    Например, для получения сценариев, определенных в глобальной области, выполните следующую команду.
    
        Get-CsClsConfiguration -Identity "global" | Select-Object -ExpandProperty Scenarios

Командлет **Get-CsClsConfiguration** всегда отображает сценарии, которые являются частью конфигурации заданной области. В большинстве случаев отображаются не все сценарии, кроме того, отображаемые сценарии сокращаются. Используемая здесь команда отображает список всех сценариев и частичные сведения об используемых поставщиках, настройках и флагах.

</div>

<div>

## <a name="to-update-a-global-scope-for-the-centralized-logging-service-by-using-windows-powershell"></a>Обновление глобальной области для централизованной службы ведения журналов с помощью Windows PowerShell

1.  Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.

2.  Введите следующую команду в командной строке:
    
        Set-CsClsConfiguration -Identity <scope> -EtlFileRolloverSizeMB <size for logging file in megabytes>
    
    Пример:
    
        Set-CsClsConfiguration -Identity "global" -EtlFileRolloverSizeMB 40

При выполнении этой команды CLSAgent на каждом компьютере и в каждом пуле развертывания задает для размера переключения на новый файл трассировки значение 40 МБ. Эта команда влияет на компьютеры и пулы на всех сайтах и задает в качестве размера переключения на новый журнал трассировки значение 40 МБ.

</div>

<div>

## <a name="to-update-a-site-scope-for-the-centralized-logging-service-by-using-windows-powershell"></a>Обновление области сайта для централизованной службы ведения журналов с помощью Windows PowerShell

1.  Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.

2.  Введите следующую команду в командной строке:
    
        Set-CsClsConfiguration -Identity <scope/site name> -EtlFileRolloverSizeMB <size for logging file in megabytes> -EtlFileFolder <default location %TEMP%\Tracing>
    
    Пример:
    
        Set-CsClsConfiguration -Identity "site/Redmond" -EtlFileRolloverSizeMB 40 -EtlFileFolder "C:\LogFiles\Tracing" 
    
    <div>
    

    > [!NOTE]
    > Как отмечено в примере, расположением файлов журнала по умолчанию является каталог %TEMP%\Tracing. Однако, так как фактически файл записывает CLSAgent, который выполняется как сетевая служба, переменная %TEMP% расширяется до %WINDIR%\ServiceProfiles\NetworkService\AppData\Local.

    
    </div>

При выполнении этой команды CLSAgent на каждом компьютере и в каждом пуле сайта Redmond задает для размера переключения на новый файл трассировки значение 40 МБ. Эта команда не повлияет на компьютеры и пулы на других сайтах, которые продолжат использовать текущее значение размера переключения на новый журнал трассировки, определенное либо по умолчанию (20 МБ), либо во время запуска сеанса ведения журнала.

</div>

<div>

## <a name="to-create-a-new-centralized-logging-service-configuration"></a>Создание новой конфигурации централизованной службы ведения журналов

1.  Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.

2.  Введите следующую команду в командной строке:
    
        New-CsClsConfiguration -Identity <scope and name> [CsClsConfiguration options for this site]
    
    <div>
    

    > [!NOTE]
    > Командлет New-CsClsConfiguration предоставляет доступ к большому количеству необязательных параметров конфигурации. Сведения о параметрах конфигурации приведены в статье <A href="https://technet.microsoft.com/library/JJ619179(v=OCS.15)">Get – CsClsConfiguration</A> и <A href="lync-server-2013-understanding-centralized-logging-service-configuration-settings.md">сведения о параметрах конфигурации службы централизованного ведения журналов в Lync Server 2013</A>.

    
    </div>
    
    Например, для создания новой конфигурации, которая определяет сетевую папку для файлов кэша, а также период и размер переключения для файлов журнала, введите следующую команду:
    
        New-CsClsConfiguration -Identity "site:Redmond" -CacheFileNetworkFolder "\\fs01.contoso.net\filestore\logfiles" -EtlFileRolloverMinutes 120 -EtlFileRolloverSizeMB 40

Следует тщательно спланировать создание новых конфигураций и определить новые свойства централизованной службы ведения журналов. Необходимо проявлять осторожность при изменениях и учитывать их влияние на возможность правильного ведения журналов в проблемных сценариях. В конфигурацию следует вносить такие изменения, которые улучшат возможности управления журналами и позволят задать такие значения размера и периода переключения, которые помогут устранить возможные проблемы.

</div>

<div>

## <a name="to-remove-an-existing-centralized-logging-service-configuration"></a>Удаление существующей конфигурации централизованной службы ведения журналов

1.  Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.

2.  Введите следующую команду в командной строке:
    
        Remove-CsClsConfiguration -Identity <scope and name>
    
    Например, чтобы удалить созданную конфигурацию централизованной службы ведения журналов, чтобы увеличить время переключения файла журнала, увеличьте размер файла журнала продолжения и установите для расположения кэша файлов журнала следующий сетевой ресурс:
    
        Remove-CsClsConfiguration -Identity "site:Redmond"
    
    <div>
    

    > [!NOTE]
    > Это новая конфигурация, созданная в процедуре "Создание новой конфигурации централизованной службы ведения журналов".

    
    </div>

Если удалить конфигурацию уровня сайта, сайт будет использовать глобальные параметры.

</div>

<div>

## <a name="see-also"></a>См. также


[Обзор централизованной службы ведения журналов в Lync Server 2013](lync-server-2013-overview-of-the-centralized-logging-service.md)  


[Управление параметрами конфигурации централизованной службы ведения журналов в Lync Server 2013](lync-server-2013-managing-the-centralized-logging-service-configuration-settings.md)  
[Set — CsClsConfiguration](https://technet.microsoft.com/library/JJ619182(v=OCS.15))  
[Get — CsClsConfiguration](https://technet.microsoft.com/library/JJ619179(v=OCS.15))  
[New — CsClsConfiguration](https://technet.microsoft.com/library/JJ619177(v=OCS.15))  
[Remove — CsClsConfiguration](https://technet.microsoft.com/library/JJ619191(v=OCS.15))  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

