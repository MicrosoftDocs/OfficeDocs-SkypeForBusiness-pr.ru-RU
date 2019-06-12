---
title: Общие сведения о централизованных параметрах конфигурации службы ведения журнала
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Understanding Centralized Logging Service configuration settings
ms:assetid: 3c34e600-0b91-43dc-b4cc-90b6a70ee12e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688029(v=OCS.15)
ms:contentKeyID: 49733619
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7a4f9a6a2db8cb4726abc65553fc4482d349f38f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849329"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="understanding-centralized-logging-service-configuration-settings-in-lync-server-2013"></a>Общие сведения о централизованных параметрах конфигурации службы ведения журналов в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2013-02-21_

Служба централизованного ведения журналов настраивается для определения того, как должна собираться служба ведения журнала, как она будет собирать данные, откуда она собирается и какие параметры журнала. You define these settings globally (that is, for the entire deployment) or for a site (that is, a named site in your deployment). Any logging that you define will use the settings that are appropriate for the identity that you use for commands to start, stop, flush, and search logs.

<div>

## <a name="to-display-the-current-centralized-logging-service-configuration"></a>Чтобы отобразить текущую конфигурацию централизованной службы ведения журнала

1.  Запустите командную консоль Lync Server Management Shell: нажмите кнопку **Пуск**, выберите **все программы**, а затем — **Microsoft Lync Server 2013**, а затем — **Командная консоль Lync Server Management Shell**.

2.  Введите следующую команду в командной строке:
    
        Get-CsClsConfiguration
    
    <div>
    

    > [!TIP]
    > Вы можете сузить или расширить область параметров конфигурации, возвращаемых определением <CODE>-Identity</CODE> и областью, например "site: Redmond", чтобы возвращать только Ксклсконфигуратион для Redmond сайта. Если вы хотите получить подробные сведения о конкретной части конфигурации, вы можете передать эти данные в другой командлет Windows PowerShell. Например, чтобы получить подробные сведения о сценариях, определенных в конфигурации для сайта Redmond, введите:<CODE>Get-CsClsConfiguration -Identity "site:Redmond" | Select-Object -ExpandPropery Scenarios</CODE>

    
    </div>
    
    ![Пример выходных данных из Get-ксклсконфигуратион.] (images/JJ688029.23f98ddc-fc48-499a-b6c5-752611f2a0b0(OCS.15).jpg "Пример выходных данных из Get-ксклсконфигуратион.")
    
    Результат командлета выводит текущую конфигурацию централизованной службы ведения журнала.
    
    
    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th>Параметр конфигурации</th>
    <th>Описание</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><strong>Identity</strong></p></td>
    <td><p>Определяет область действия и имя данной конфигурации.  Существует одна глобальная конфигурация и по одной конфигурации для каждого сайта.</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>Scenarios</strong></p></td>
    <td><p>Список всех сценариев, определенных для данной конфигурации.</p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>SearchTerms</strong></p></td>
    <td><p>Определенные поисковые запросы для этой конфигурации. Office 365, а не локальные развертывания.</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>SecurityGroups</strong></p></td>
    <td><p>Определенные группы безопасности, которые управляют кто (т. е. участники групп безопасности) могут просматривать компьютеры на основе сайта их размещения. Сайт в данном контексте — сайт, определенный в построителе топологии.</p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>Regions</strong></p></td>
    <td><p>Определенные регионы используются для сбора групп безопасности по регионам, например EMEA (страны Европы, Ближнего Востока и Африки).</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>Етлфилефолдер</strong></p></td>
    <td><p>Определенный путь к расположению, в котором файлы журнала записываются на компьютеры. Клсажент записывает файлы журнала и запускается в контексте сетевой службы. В этом случае% TEMP% разворачивается до%Виндир%\сервицепрофилес\нетворксервице\аппдата\локал</p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>EtlFileRolloverSizeMB</strong></p></td>
    <td><p>Данный параметры указывает максимальный размер файла журнала до создания нового файла трассировки журнала (.etl). Новый файл журнала создается при достижении определенного размера, даже если не было достигнуто значение, заданное в параметре EtlFileRolloverMinutes.</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>EtlFileRolloverMinutes</strong></p></td>
    <td><p>Определенное максимальное время существования журнала (в минутах) до создания нового ETL-файла. Новый файл журнала создается по завершении таймера, даже если еще не было достигнуто значение максимального размера, заданное в параметре EtlFileRolloverSizeMB.</p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>TmfFileSearchPath</strong></p></td>
    <td><p>Местоположение для поиска файлов формата трассировки сообщений. Файлы формата сообщений трассировки используются для преобразования двоичных файлов в формат, пригодный для восприятия.</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>CacheFileLocalFolders</strong></p></td>
    <td><p>Определенный путь к месту сохранения файлов кэша на компьютерах. CLSAgent записывает файлы кэша и работает в контексте сетевой службы. В этом случае значением переменной %TEMP% является %WINDIR%\ServiceProfiles\NetworkService\AppData\Local. По умолчанию файлы кэша и файлы журнала записываются в один каталог.</p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>CacheFileNetworkFolder</strong></p></td>
    <td><p>Можно определить UNC-путь для получения файлов кэша во время операций ведения журналов.</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>CacheFileLocalRetentionPeriod</strong></p></td>
    <td><p>Определяется как максимальное время в днях для сохранения файлов кэша.</p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>CacheFileMaxDiskUsage</strong></p></td>
    <td><p>Определяется как часть дискового пространства (выраженное в процентах), которое может использоваться под файлы кэша.</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>ComponentThrottleLimit</strong></p></td>
    <td><p>Определяется как максимальное количество трассировок в секунду, которое может создавать компонент до активации автоматического ограничителя.</p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>ComponentThrottleSample</strong></p></td>
    <td><p>Количество превышений значения ComponentThrottleLimit в течение 60 секунд.</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>MinimumClsAgentServiceVersion</strong></p></td>
    <td><p>Минимальная версия CLSAgent, допустимая для запуска. Этот элемент предназначен для Office 365.</p></td>
    </tr>
    </tbody>
    </table>


</div>

<div>

## <a name="see-also"></a>См. также


[Общие сведения об централизованной службе ведения журналов в Lync Server 2013](lync-server-2013-overview-of-the-centralized-logging-service.md)  


[Set-CsClsConfiguration](https://technet.microsoft.com/en-us/library/JJ619182(v=OCS.15))  
[Remove-CsClsConfiguration](https://technet.microsoft.com/en-us/library/JJ619191(v=OCS.15))  
[New-CsClsConfiguration](https://technet.microsoft.com/en-us/library/JJ619177(v=OCS.15))  
[Get-CsClsConfiguration](https://technet.microsoft.com/en-us/library/JJ619179(v=OCS.15))  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

