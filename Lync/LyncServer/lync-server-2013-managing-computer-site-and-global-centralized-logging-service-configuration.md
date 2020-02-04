---
title: Управление конфигурацией службы ведения журналов компьютера, сайта и глобальной централизованной организации
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
ms.openlocfilehash: 8f714c82fdc4ade0fc70b0a977e32ef46b26914d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41729339"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-computer-site-and-global-centralized-logging-service-configuration-in-lync-server-2013"></a>Управление конфигурацией службы ведения журналов на компьютере, сайте и глобальном централизованном хранилище в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2014-02-04_

Централизованная служба ведения журнала может выполняться в области, содержащей один компьютер, пул компьютеров, а также на уровне сайта (определенного сайта, такого как Redmond сайта, который содержит коллекцию компьютеров и пулов в развертывании), или в глобальной области (то есть , все компьютеры и пулы в развертывании).

Чтобы настроить централизованную службу ведения журналов с помощью командной консоли Lync Server Management Shell, необходимо быть членом группы безопасности Ксадминистратор или Кссерверадминистратор управления доступом на основе ролей (RBAC) или настраиваемой роли RBAC, содержащей Любая из этих двух групп. Чтобы возвратить список всех ролей RBAC, которым был назначен этот командлет (включая любые пользовательские роли RBAC, созданные пользователем), выполните следующую команду из командной консоли Lync Server Management Shell или Windows PowerShell.

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "<Lync Server 2013 cmdlet>"}

Например:

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}

<div>


> [!NOTE]
> Windows PowerShell предлагает дополнительные параметры и дополнительные параметры настройки, недоступные с помощью Клсконтроллер. exe. Клсконтроллер обеспечивает быстрый и короткий метод для выполнения команд, но ограничен набором команд, доступных для Клсконтроллер. Windows PowerShell не ограничивается только командой, доступной для командного процессора Клсконтроллер, и предоставляет широкий набор команд и более широкий набор параметров. Например, в Клсконтроллер. exe предусмотрены параметры области – Компьютеры и – пулы. С помощью Windows PowerShell вы можете указать, какие компьютеры или пулы в большинстве команд, и при определении новых сценариев (Клсконтроллер имеет конечное количество сценариев, которые не могут быть изменены пользователем). Вы можете определить сайт или глобальную область. Эта мощная функция Windows PowerShell позволяет определять сценарий для сайта или глобальной области, но ограничивает фактическое ведение журнала для компьютера или пула.<BR>Существуют фундаментальные различия между командами командной строки, которые можно выполнять в Windows PowerShell или Клсконтроллер. Windows PowerShell предоставляет богатый способ настройки и определения сценариев, а также повторно использовать эти сценарии для сценариев устранения неполадок. While CLSController does provide a fast and efficient way to issue commands and get results, the command set for CLSController is limited by the finite commands that you have available from the command line. В отличие от командлетов Windows PowerShell, Клсконтроллер не может определять новые сценарии, управлять областью на сайте или глобальном уровне и многие другие ограничения набора команд, которые не могут быть настроены динамически. Несмотря на то, что Клсконтроллер предоставляет средства для быстрого выполнения, Windows PowerShell предоставляет средства для продления функций централизованной службы ведения журналов, помимо возможностей, возможных для Клсконтроллер.



</div>

Область одного компьютера можно определить при выполнении команд [Search-CsClsLogging](https://technet.microsoft.com/en-us/library/JJ619189(v=OCS.15)), [Show-CsClsLogging](https://technet.microsoft.com/en-us/library/JJ619173(v=OCS.15)), [Start-CsClsLogging](https://technet.microsoft.com/en-us/library/JJ619190(v=OCS.15)), [Stop-CsClsLogging](https://technet.microsoft.com/en-us/library/JJ619180(v=OCS.15)), [Sync-CsClsLogging](https://technet.microsoft.com/en-us/library/JJ619169(v=OCS.15)) и [Update-CsClsLogging](https://technet.microsoft.com/en-us/library/JJ619170(v=OCS.15)) с помощью параметра –Computers. Параметр –Computers принимает разделенный запятой список полных доменных имен для целевого компьютера.

<div>


> [!TIP]
> С помощью параметра –Pools можно задать разделенный запятой список пулов, в которых должны выполняться команды ведения журнала.



</div>

В командлетах служб ведения журналов для **создания**и **удаления** сайтов определены **** сайты и глобальные области. The following examples demonstrate how to set a site and a global scope.

<div>


> [!IMPORTANT]
> Показанные команды могут содержать параметры и концепции, описанные в других разделах. Команды в примерах предназначены для демонстрации использования параметра <STRONG>–Identity</STRONG> для определения области, а другие параметры включены для полноты и для указания области. Дополнительные сведения о командлетах <STRONG>Set-CsClsConfiguration</STRONG> см. в описании командлета <A href="https://technet.microsoft.com/en-us/library/JJ619182(v=OCS.15)">Set-CsClsConfiguration</A> в документации по применению.



</div>

<div>

## <a name="to-retrieve-the-current-centralized-logging-service-configuration"></a>Чтобы получить текущую конфигурацию централизованной службы ведения журнала

1.  Запустите командную консоль Lync Server Management Shell: нажмите кнопку **Пуск**, выберите **все программы**, а затем — **Microsoft Lync Server 2013**, а затем — **Командная консоль Lync Server Management Shell**.

2.  Введите следующую команду в командной строке:
    
        Get-CsClsConfiguration

Используйте командлеты **New-CsClsConfiguration** и **Set-CsClsConfiguration** для создания новой конфигурации или для обновления существующей.

При выполнении командлета **Get-CsClsConfiguration** отображаются сведения, подобные показанным на следующем снимке экрана. В этом примере в развертывании имеется глобальная конфигурация по умолчанию, а конфигурации сайтов не определены:

![Выход выборки из Get-CsClsConfiguration.](images/JJ688029.23f98ddc-fc48-499a-b6c5-752611f2a0b0(OCS.15).jpg "Выход выборки из Get-CsClsConfiguration.")

</div>

<div>

## <a name="to-retrieve-the-current-centralized-logging-service-configuration-from-the-computer-local-store"></a>Чтобы получить текущую конфигурацию централизованной службы ведения журналов из локального магазина компьютера

1.  Запустите командную консоль Lync Server Management Shell: нажмите кнопку **Пуск**, выберите **все программы**, а затем — **Microsoft Lync Server 2013**, а затем — **Командная консоль Lync Server Management Shell**.

2.  Введите следующую команду в командной строке:
    
        Get-CsClsConfiguration -LocalStore

При использовании первого примера, где **Get-ксклсконфигуратион** не задает параметры, команда ссылается на центральное хранилище для управления данными. Если указать параметр — Локалсторе, команда будет ссылаться на компьютер Локалсторе вместо центрального хранилища.

</div>

<div>

## <a name="to-retrieve-a-listing-of-scenarios-currently-defined"></a>Получение списка сценариев, определенных в текущий момент

1.  Запустите командную консоль Lync Server Management Shell: нажмите кнопку **Пуск**, выберите **все программы**, а затем — **Microsoft Lync Server 2013**, а затем — **Командная консоль Lync Server Management Shell**.

2.  Введите следующую команду в командной строке:
    
        Get-CsClsConfiguration -Identity <scope and name> | Select-Object -ExpandProperty Scenarios
    
    Например для получения сценариев, определенных в глобальной области, выполните следующую команду.
    
        Get-CsClsConfiguration -Identity "global" | Select-Object -ExpandProperty Scenarios

Командлет **Get-CsClsConfiguration** всегда отображает сценарии, которые являются частью конфигурации заданной области. В большинстве случаев отображаются не все сценарии, кроме того, отображаемые сценарии сокращаются. Используемая здесь команда отображает список всех сценариев и частичные сведения об используемых поставщиках, настройках и флагах.

</div>

<div>

## <a name="to-update-a-global-scope-for-the-centralized-logging-service-by-using-windows-powershell"></a>Обновление глобальной области для централизованной службы ведения журналов с помощью Windows PowerShell

1.  Запустите командную консоль Lync Server Management Shell: нажмите кнопку **Пуск**, выберите **все программы**, а затем — **Microsoft Lync Server 2013**, а затем — **Командная консоль Lync Server Management Shell**.

2.  Введите следующую команду в командной строке:
    
        Set-CsClsConfiguration -Identity <scope> -EtlFileRolloverSizeMB <size for logging file in megabytes>
    
    Например:
    
        Set-CsClsConfiguration -Identity "global" -EtlFileRolloverSizeMB 40

При выполнении этой команды CLSAgent на каждом компьютере и в каждом пуле развертывания задает для размера переключения на новый файл трассировки значение 40 МБ. Эта команда влияет на компьютеры и пулы на всех сайтах и задает в качестве размера переключения на новый журнал трассировки значение 40 МБ.

</div>

<div>

## <a name="to-update-a-site-scope-for-the-centralized-logging-service-by-using-windows-powershell"></a>Обновление области сайта для централизованной службы ведения журналов с помощью Windows PowerShell

1.  Запустите командную консоль Lync Server Management Shell: нажмите кнопку **Пуск**, выберите **все программы**, а затем — **Microsoft Lync Server 2013**, а затем — **Командная консоль Lync Server Management Shell**.

2.  Введите следующую команду в командной строке:
    
        Set-CsClsConfiguration -Identity <scope/site name> -EtlFileRolloverSizeMB <size for logging file in megabytes> -EtlFileFolder <default location %TEMP%\Tracing>
    
    Например:
    
        Set-CsClsConfiguration -Identity "site/Redmond" -EtlFileRolloverSizeMB 40 -EtlFileFolder "C:\LogFiles\Tracing" 
    
    <div>
    

    > [!NOTE]
    > Как отмечено в примере, расположением файлов журнала по умолчанию является каталог %TEMP%\Tracing. Однако так как фактически файл записывает CLSAgent, который выполняется как сетевая служба, переменная %TEMP% расширяется до %WINDIR%\ServiceProfiles\NetworkService\AppData\Local.

    
    </div>

При выполнении этой команды CLSAgent на каждом компьютере и в каждом пуле сайта Redmond задает для размера переключения на новый файл трассировки значение 40 МБ. Эта команда не повлияет на компьютеры и пулы на других сайтах, которые продолжат использовать текущее значение размера переключения на новый журнал трассировки, определенное либо по умолчанию (20 МБ), либо во время запуска сеанса ведения журнала.

</div>

<div>

## <a name="to-create-a-new-centralized-logging-service-configuration"></a>Создание новой конфигурации централизованной службы ведения журнала

1.  Запустите командную консоль Lync Server Management Shell: нажмите кнопку **Пуск**, выберите **все программы**, а затем — **Microsoft Lync Server 2013**, а затем — **Командная консоль Lync Server Management Shell**.

2.  Введите следующую команду в командной строке:
    
        New-CsClsConfiguration -Identity <scope and name> [CsClsConfiguration options for this site]
    
    <div>
    

    > [!NOTE]
    > Командлет New-CsClsConfiguration предоставляет доступ к большому количеству необязательных параметров конфигурации. Сведения о параметрах конфигурации можно найти в <A href="https://technet.microsoft.com/en-us/library/JJ619179(v=OCS.15)">статьях Get-ксклсконфигуратион</A> и общие сведения о <A href="lync-server-2013-understanding-centralized-logging-service-configuration-settings.md">централизованных параметрах конфигурации службы ведения журналов в Lync Server 2013</A>.

    
    </div>
    
    Например для создания новой конфигурации, которая определяет сетевую папку для файлов кэша, а также период и размер переключения для файлов журнала, введите следующую команду:
    
        New-CsClsConfiguration -Identity "site:Redmond" -CacheFileNetworkFolder "\\fs01.contoso.net\filestore\logfiles" -EtlFileRolloverMinutes 120 -EtlFileRolloverSizeMB 40

Тщательно спланируйте создание новых конфигураций и определите, как вы определяете новые свойства для централизованной службы ведения журнала. You should be cautious about making changes and make sure you understand the impact on your ability to properly log problem scenarios. You should make changes to the configuration that will enhance your ability to manage logs to a size and a rollover period that will allow problem solving when it arises.

</div>

<div>

## <a name="to-remove-an-existing-centralized-logging-service-configuration"></a>Удаление существующей конфигурации службы централизованного ведения журнала

1.  Запустите командную консоль Lync Server Management Shell: нажмите кнопку **Пуск**, выберите **все программы**, а затем — **Microsoft Lync Server 2013**, а затем — **Командная консоль Lync Server Management Shell**.

2.  Введите следующую команду в командной строке:
    
        Remove-CsClsConfiguration -Identity <scope and name>
    
    Например, чтобы удалить созданную конфигурацию централизованной службы ведения журналов, чтобы продлить время переключения на файл журнала, измените размер файла журнала продолжения и установите для него расположение кэша файлов журнала, выполнив указанные ниже действия.
    
        Remove-CsClsConfiguration -Identity "site:Redmond"
    
    <div>
    

    > [!NOTE]
    > Это новая конфигурация, созданная в процедуре "Создание новой конфигурации централизованной службы ведения журнала".

    
    </div>

Если удалить конфигурацию уровня сайта, сайт будет использовать глобальные параметры.

</div>

<div>

## <a name="see-also"></a>См. также


[Общие сведения об централизованной службе ведения журналов в Lync Server 2013](lync-server-2013-overview-of-the-centralized-logging-service.md)  


[Управление централизованными параметрами конфигурации службы ведения журналов в Lync Server 2013](lync-server-2013-managing-the-centralized-logging-service-configuration-settings.md)  
[Set-CsClsConfiguration](https://technet.microsoft.com/en-us/library/JJ619182(v=OCS.15))  
[Get-CsClsConfiguration](https://technet.microsoft.com/en-us/library/JJ619179(v=OCS.15))  
[New-CsClsConfiguration](https://technet.microsoft.com/en-us/library/JJ619177(v=OCS.15))  
[Remove-CsClsConfiguration](https://technet.microsoft.com/en-us/library/JJ619191(v=OCS.15))  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

