---
title: Общие сведения о параметрах конфигурации службы централизованного ведения журналов
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Understanding Centralized Logging Service configuration settings
ms:assetid: 3c34e600-0b91-43dc-b4cc-90b6a70ee12e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688029(v=OCS.15)
ms:contentKeyID: 49733619
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1bda4fe432841cd005671b18a163df57bd6e0bb7
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2020
ms.locfileid: "42006695"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="understanding-centralized-logging-service-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="2eaa0-102">Общие сведения о параметрах конфигурации службы централизованного ведения журналов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2eaa0-102">Understanding Centralized Logging Service configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2eaa0-103">_**Последнее изменение темы:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="2eaa0-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="2eaa0-104">Служба централизованного ведения журналов настраивается на определение того, что должна собирать служба ведения журнала, как она собирает данные, откуда она будет собирать данные и какие параметры журнала.</span><span class="sxs-lookup"><span data-stu-id="2eaa0-104">The Centralized Logging Service is configured to define what the logging service is intended to collect, how it collects, where it will collect from, and what the log settings are.</span></span> <span data-ttu-id="2eaa0-105">Эти параметры определяются глобально (то есть для всего развертывания) или для сайта (то есть именованный сайт в вашем развертывании).</span><span class="sxs-lookup"><span data-stu-id="2eaa0-105">You define these settings globally (that is, for the entire deployment) or for a site (that is, a named site in your deployment).</span></span> <span data-ttu-id="2eaa0-106">Любое определенное ведение журнала приведет к использованию параметров, подходящих для удостоверения, используемого для команд запуска, остановки, очистки журналов и выполнения поиска.</span><span class="sxs-lookup"><span data-stu-id="2eaa0-106">Any logging that you define will use the settings that are appropriate for the identity that you use for commands to start, stop, flush, and search logs.</span></span>

<div>

## <a name="to-display-the-current-centralized-logging-service-configuration"></a><span data-ttu-id="2eaa0-107">Отображение текущей конфигурации централизованной службы ведения журналов</span><span class="sxs-lookup"><span data-stu-id="2eaa0-107">To display the current Centralized Logging Service configuration</span></span>

1.  <span data-ttu-id="2eaa0-108">Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="2eaa0-108">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="2eaa0-109">Введите следующую команду в командной строке:</span><span class="sxs-lookup"><span data-stu-id="2eaa0-109">Type the following at a command-line prompt:</span></span>
    
        Get-CsClsConfiguration
    
    <div>
    

    > [!TIP]
    > <span data-ttu-id="2eaa0-110">Вы можете сузить или расширить область параметров конфигурации, возвращаемых определением <CODE>-Identity</CODE> и областью, например "site: Redmond", чтобы возвратить только CsClsConfiguration для сайта Redmond.</span><span class="sxs-lookup"><span data-stu-id="2eaa0-110">You can narrow or expand the scope of the configuration settings that are returned by defining <CODE>-Identity</CODE> and a scope, such as "Site:Redmond" to return only the CsClsConfiguration for the site Redmond.</span></span> <span data-ttu-id="2eaa0-111">Если вы хотите получить подробные сведения об определенной части конфигурации, вы можете передать выходные данные в другой командлет Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2eaa0-111">If you want details about a given portion of the configuration, you can pipe the output into another Windows PowerShell cmdlet.</span></span> <span data-ttu-id="2eaa0-112">Например, чтобы получить сведения о сценариях, определенных в конфигурации для сайта Redmond, введите:<CODE>Get-CsClsConfiguration -Identity "site:Redmond" | Select-Object -ExpandPropery Scenarios</CODE></span><span class="sxs-lookup"><span data-stu-id="2eaa0-112">For example, to get details about the scenarios defined in the configuration for site "Redmond", type: <CODE>Get-CsClsConfiguration -Identity "site:Redmond" | Select-Object -ExpandPropery Scenarios</CODE></span></span>

    
    </div>
    
    <span data-ttu-id="2eaa0-113">![Пример выходных данных Get – CsClsConfiguration.](images/JJ688029.23f98ddc-fc48-499a-b6c5-752611f2a0b0(OCS.15).jpg "Пример выходных данных Get – CsClsConfiguration.")</span><span class="sxs-lookup"><span data-stu-id="2eaa0-113">![Sample output from Get-CsClsConfiguration.](images/JJ688029.23f98ddc-fc48-499a-b6c5-752611f2a0b0(OCS.15).jpg "Sample output from Get-CsClsConfiguration.")</span></span>
    
    <span data-ttu-id="2eaa0-114">В результате выполнения командлета отображается текущая конфигурация централизованной службы ведения журналов.</span><span class="sxs-lookup"><span data-stu-id="2eaa0-114">The result from the cmdlet displays the current configuration of the Centralized Logging Service.</span></span>
    
    
    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="2eaa0-115">Параметр конфигурации</span><span class="sxs-lookup"><span data-stu-id="2eaa0-115">Configuration Setting</span></span></th>
    <th><span data-ttu-id="2eaa0-116">Описание</span><span class="sxs-lookup"><span data-stu-id="2eaa0-116">Description</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="2eaa0-117"><strong>Идентификация</strong></span><span class="sxs-lookup"><span data-stu-id="2eaa0-117"><strong>Identity</strong></span></span></p></td>
    <td><p><span data-ttu-id="2eaa0-p103">Определяет область действия и имя данной конфигурации.  Существует одна глобальная конфигурация и по одной конфигурации для каждого сайта.</span><span class="sxs-lookup"><span data-stu-id="2eaa0-p103">Identifies the scope and name for this configuration. There is only one Global configuration, and one configuration per site.</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="2eaa0-120"><strong>Scenarios</strong></span><span class="sxs-lookup"><span data-stu-id="2eaa0-120"><strong>Scenarios</strong></span></span></p></td>
    <td><p><span data-ttu-id="2eaa0-121">Список всех сценариев, определенных для данной конфигурации.</span><span class="sxs-lookup"><span data-stu-id="2eaa0-121">Listing of all scenarios that are defined for this configuration.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="2eaa0-122"><strong>SearchTerms</strong></span><span class="sxs-lookup"><span data-stu-id="2eaa0-122"><strong>SearchTerms</strong></span></span></p></td>
    <td><p><span data-ttu-id="2eaa0-123">Определенные поисковые запросы для этой конфигурации.</span><span class="sxs-lookup"><span data-stu-id="2eaa0-123">Defined search terms for the configuration.</span></span> <span data-ttu-id="2eaa0-124">Office 365, а не локальные развертывания.</span><span class="sxs-lookup"><span data-stu-id="2eaa0-124">Office 365, not on-premises deployments.</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="2eaa0-125"><strong>Групп безопасности</strong></span><span class="sxs-lookup"><span data-stu-id="2eaa0-125"><strong>SecurityGroups</strong></span></span></p></td>
    <td><p><span data-ttu-id="2eaa0-126">Определенные группы безопасности, которые управляют кто (т. е. участники групп безопасности) могут просматривать компьютеры на основе сайта их размещения.</span><span class="sxs-lookup"><span data-stu-id="2eaa0-126">Defined security groups that control who (that is, members of the security groups) can see computers based on the site they are located in.</span></span> <span data-ttu-id="2eaa0-127">Сайт в данном контексте — это сайт, определенный в построителе топологий.</span><span class="sxs-lookup"><span data-stu-id="2eaa0-127">Site, in this context, is the site as defined in Topology Builder.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="2eaa0-128"><strong>Регионы</strong></span><span class="sxs-lookup"><span data-stu-id="2eaa0-128"><strong>Regions</strong></span></span></p></td>
    <td><p><span data-ttu-id="2eaa0-129">Определенные регионы используются для сбора групп безопасности по регионам, например EMEA (страны Европы, Ближнего Востока и Африки).</span><span class="sxs-lookup"><span data-stu-id="2eaa0-129">Defined regions are used to collect SecurityGroups into a region, for example EMEA.</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="2eaa0-130"><strong>етлфилефолдер</strong></span><span class="sxs-lookup"><span data-stu-id="2eaa0-130"><strong>EtlFileFolder</strong></span></span></p></td>
    <td><p><span data-ttu-id="2eaa0-p106">Определенный путь к месту сохранения файлов журналов на компьютерах. CLSAgent записывает файлы журналов и работает в контексте сетевой службы. В этом случае значением переменной %TEMP% является %WINDIR%\ServiceProfiles\NetworkService\AppData\Local</span><span class="sxs-lookup"><span data-stu-id="2eaa0-p106">Defined path to the location where log files are written on computers. CLSAgent writes the log files and runs under the context of the Network Service. In this case, %TEMP% expands to %WINDIR%\ServiceProfiles\NetworkService\AppData\Local</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="2eaa0-134"><strong>етлфилеролловерсиземб</strong></span><span class="sxs-lookup"><span data-stu-id="2eaa0-134"><strong>EtlFileRolloverSizeMB</strong></span></span></p></td>
    <td><p><span data-ttu-id="2eaa0-p107">Данный параметры указывает максимальный размер файла журнала до создания нового файла трассировки журнала (.etl). Новый файл журнала создается при достижении определенного размера, даже если не было достигнуто значение, заданное в параметре EtlFileRolloverMinutes.</span><span class="sxs-lookup"><span data-stu-id="2eaa0-p107">The parameter indicates the maximum size of the log file before a new event trace log (.etl) file is created. A new log file is created when the defined size is reached even if the maximum time set in EtlFileRolloverMinutes has not yet been reached.</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="2eaa0-137"><strong>етлфилеролловерминутес</strong></span><span class="sxs-lookup"><span data-stu-id="2eaa0-137"><strong>EtlFileRolloverMinutes</strong></span></span></p></td>
    <td><p><span data-ttu-id="2eaa0-p108">Определенное максимальное время существования журнала (в минутах) до создания нового ETL-файла. Новый файл журнала создается по завершении таймера, даже если еще не было достигнуто значение максимального размера, заданное в параметре EtlFileRolloverSizeMB.</span><span class="sxs-lookup"><span data-stu-id="2eaa0-p108">Defined maximum amount of time, in minutes, that a log can elapse before a new .etl file is created. A new log file is created when the timer expires even if the maximum size set in EtlFileRolloverSizeMB has not yet been reached.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="2eaa0-140"><strong>тмффилесеарчпас</strong></span><span class="sxs-lookup"><span data-stu-id="2eaa0-140"><strong>TmfFileSearchPath</strong></span></span></p></td>
    <td><p><span data-ttu-id="2eaa0-p109">Местоположение для поиска файлов формата трассировки сообщений. Файлы формата трассировки сообщений используются для преобразования двоичных файлов в понятный для восприятия формат.</span><span class="sxs-lookup"><span data-stu-id="2eaa0-p109">Location to search for the trace message format files. The trace message format files are used to convert the binary files into a human readable format.</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="2eaa0-143"><strong>CacheFileLocalFolders</strong></span><span class="sxs-lookup"><span data-stu-id="2eaa0-143"><strong>CacheFileLocalFolders</strong></span></span></p></td>
    <td><p><span data-ttu-id="2eaa0-p110">Определенный путь к месту сохранения файлов кэша на компьютерах. CLSAgent записывает файлы кэша и работает в контексте сетевой службы. В этом случае значением переменной %TEMP% является %WINDIR%\ServiceProfiles\NetworkService\AppData\Local. По умолчанию файлы кэша и файлы журнала записываются в один каталог.</span><span class="sxs-lookup"><span data-stu-id="2eaa0-p110">Defined path to the location where cache files are written on computers. CLSAgent writes the cache files and runs under the context of the Network Service. In this case, %TEMP% expands to %WINDIR%\ServiceProfiles\NetworkService\AppData\Local. By default, cache files and log files are written to the same directory.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="2eaa0-148"><strong>качефиленетворкфолдер</strong></span><span class="sxs-lookup"><span data-stu-id="2eaa0-148"><strong>CacheFileNetworkFolder</strong></span></span></p></td>
    <td><p><span data-ttu-id="2eaa0-149">Можно определить UNC-путь для получения файлов кэша во время операций ведения журналов.</span><span class="sxs-lookup"><span data-stu-id="2eaa0-149">You can define a universal naming convention (UNC) path to receive the cache files during logging operations.</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="2eaa0-150"><strong>качефилелокалретентионпериод</strong></span><span class="sxs-lookup"><span data-stu-id="2eaa0-150"><strong>CacheFileLocalRetentionPeriod</strong></span></span></p></td>
    <td><p><span data-ttu-id="2eaa0-151">Определяется как максимальное время в днях для сохранения файлов кэша.</span><span class="sxs-lookup"><span data-stu-id="2eaa0-151">Defined as the maximum time, in days, that cache files are retained.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="2eaa0-152"><strong>качефилемаксдискусаже</strong></span><span class="sxs-lookup"><span data-stu-id="2eaa0-152"><strong>CacheFileMaxDiskUsage</strong></span></span></p></td>
    <td><p><span data-ttu-id="2eaa0-153">Определяется как часть дискового пространства (выраженное в процентах), которое может использоваться под файлы кэша.</span><span class="sxs-lookup"><span data-stu-id="2eaa0-153">Defined as the percentage of disk space that can be used by the cache files.</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="2eaa0-154"><strong>Превышений значения componentthrottlelimit</strong></span><span class="sxs-lookup"><span data-stu-id="2eaa0-154"><strong>ComponentThrottleLimit</strong></span></span></p></td>
    <td><p><span data-ttu-id="2eaa0-155">Определяется как максимальное количество трассировок в секунду, которое может создавать компонент до активации автоматического ограничителя.</span><span class="sxs-lookup"><span data-stu-id="2eaa0-155">Defined as the maximum number of traces per second that a component can produce before the automatic throttle limiter is triggered.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="2eaa0-156"><strong>компонентсроттлесампле</strong></span><span class="sxs-lookup"><span data-stu-id="2eaa0-156"><strong>ComponentThrottleSample</strong></span></span></p></td>
    <td><p><span data-ttu-id="2eaa0-157">Количество превышений значения ComponentThrottleLimit в течение 60 секунд.</span><span class="sxs-lookup"><span data-stu-id="2eaa0-157">Number of times in 60 seconds that the ComponentThrottleLimit can be exceeded.</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="2eaa0-158"><strong>минимумклсажентсервицеверсион</strong></span><span class="sxs-lookup"><span data-stu-id="2eaa0-158"><strong>MinimumClsAgentServiceVersion</strong></span></span></p></td>
    <td><p><span data-ttu-id="2eaa0-159">Минимальная версия CLSAgent, допустимая для запуска.</span><span class="sxs-lookup"><span data-stu-id="2eaa0-159">The minimum version of the CLSAgent allowed to run.</span></span> <span data-ttu-id="2eaa0-160">Этот элемент предназначен для Office 365.</span><span class="sxs-lookup"><span data-stu-id="2eaa0-160">This element is intended for Office 365.</span></span></p></td>
    </tr>
    </tbody>
    </table>


</div>

<div>

## <a name="see-also"></a><span data-ttu-id="2eaa0-161">См. также</span><span class="sxs-lookup"><span data-stu-id="2eaa0-161">See Also</span></span>


[<span data-ttu-id="2eaa0-162">Обзор централизованной службы ведения журналов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2eaa0-162">Overview of the Centralized Logging Service in Lync Server 2013</span></span>](lync-server-2013-overview-of-the-centralized-logging-service.md)  


<span data-ttu-id="2eaa0-163">[Set — CsClsConfiguration](https://technet.microsoft.com/library/JJ619182(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2eaa0-163">[Set-CsClsConfiguration](https://technet.microsoft.com/library/JJ619182(v=OCS.15))</span></span>  
<span data-ttu-id="2eaa0-164">[Remove — CsClsConfiguration](https://technet.microsoft.com/library/JJ619191(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2eaa0-164">[Remove-CsClsConfiguration](https://technet.microsoft.com/library/JJ619191(v=OCS.15))</span></span>  
<span data-ttu-id="2eaa0-165">[New — CsClsConfiguration](https://technet.microsoft.com/library/JJ619177(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2eaa0-165">[New-CsClsConfiguration](https://technet.microsoft.com/library/JJ619177(v=OCS.15))</span></span>  
<span data-ttu-id="2eaa0-166">[Get — CsClsConfiguration](https://technet.microsoft.com/library/JJ619179(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2eaa0-166">[Get-CsClsConfiguration](https://technet.microsoft.com/library/JJ619179(v=OCS.15))</span></span>  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

