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
ms.openlocfilehash: 4efbf47cd55fe0e62753843973e67b9eb242862b
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221199"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="understanding-centralized-logging-service-configuration-settings-in-lync-server-2013"></a>Общие сведения о параметрах конфигурации службы централизованного ведения журналов в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2013-02-21_

Служба централизованного ведения журналов настраивается на определение того, что должна собирать служба ведения журнала, как она собирает данные, откуда она будет собирать данные и какие параметры журнала. Эти параметры определяются глобально (то есть для всего развертывания) или для сайта (то есть именованный сайт в вашем развертывании). Любое определенное ведение журнала приведет к использованию параметров, подходящих для удостоверения, используемого для команд запуска, остановки, очистки журналов и выполнения поиска.

<div>

## <a name="to-display-the-current-centralized-logging-service-configuration"></a>Отображение текущей конфигурации централизованной службы ведения журналов

1.  Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.

2.  Введите следующую команду в командной строке:
    
        Get-CsClsConfiguration
    
    <div>
    

    > [!TIP]
    > Вы можете сузить или расширить область параметров конфигурации, возвращаемых определением <CODE>-Identity</CODE> и областью, например "site: Redmond", чтобы возвратить только CsClsConfiguration для сайта Redmond. Если вы хотите получить подробные сведения об определенной части конфигурации, вы можете передать выходные данные в другой командлет Windows PowerShell. Например, чтобы получить сведения о сценариях, определенных в конфигурации для сайта Redmond, введите:<CODE>Get-CsClsConfiguration -Identity "site:Redmond" | Select-Object -ExpandPropery Scenarios</CODE>

    
    </div>
    
    ![Пример выходных данных Get – CsClsConfiguration.](images/JJ688029.23f98ddc-fc48-499a-b6c5-752611f2a0b0(OCS.15).jpg "Пример выходных данных Get – CsClsConfiguration.")
    
    В результате выполнения командлета отображается текущая конфигурация централизованной службы ведения журналов.
    
    
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
    <td><p><strong>Идентификация</strong></p></td>
    <td><p>Определяет область действия и имя данной конфигурации.  Существует одна глобальная конфигурация и по одной конфигурации для каждого сайта.</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>Scenarios</strong></p></td>
    <td><p>Список всех сценариев, определенных для данной конфигурации.</p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>SearchTerms</strong></p></td>
    <td><p>Определенные поисковые запросы для этой конфигурации. Office 365 или Microsoft 365, а не локальные развертывания.</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>Групп безопасности</strong></p></td>
    <td><p>Определенные группы безопасности, которые управляют кто (т. е. участники групп безопасности) могут просматривать компьютеры на основе сайта их размещения. Сайт в данном контексте — это сайт, определенный в построителе топологий.</p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>Регионы</strong></p></td>
    <td><p>Определенные регионы используются для сбора групп безопасности по регионам, например EMEA (страны Европы, Ближнего Востока и Африки).</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>етлфилефолдер</strong></p></td>
    <td><p>Определенный путь к месту сохранения файлов журналов на компьютерах. CLSAgent записывает файлы журналов и работает в контексте сетевой службы. В этом случае значением переменной %TEMP% является %WINDIR%\ServiceProfiles\NetworkService\AppData\Local</p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>етлфилеролловерсиземб</strong></p></td>
    <td><p>Данный параметры указывает максимальный размер файла журнала до создания нового файла трассировки журнала (.etl). Новый файл журнала создается при достижении определенного размера, даже если не было достигнуто значение, заданное в параметре EtlFileRolloverMinutes.</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>етлфилеролловерминутес</strong></p></td>
    <td><p>Определенное максимальное время существования журнала (в минутах) до создания нового ETL-файла. Новый файл журнала создается по завершении таймера, даже если еще не было достигнуто значение максимального размера, заданное в параметре EtlFileRolloverSizeMB.</p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>тмффилесеарчпас</strong></p></td>
    <td><p>Местоположение для поиска файлов формата трассировки сообщений. Файлы формата трассировки сообщений используются для преобразования двоичных файлов в понятный для восприятия формат.</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>CacheFileLocalFolders</strong></p></td>
    <td><p>Определенный путь к месту сохранения файлов кэша на компьютерах. CLSAgent записывает файлы кэша и работает в контексте сетевой службы. В этом случае значением переменной %TEMP% является %WINDIR%\ServiceProfiles\NetworkService\AppData\Local. По умолчанию файлы кэша и файлы журнала записываются в один каталог.</p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>качефиленетворкфолдер</strong></p></td>
    <td><p>Можно определить UNC-путь для получения файлов кэша во время операций ведения журналов.</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>качефилелокалретентионпериод</strong></p></td>
    <td><p>Определяется как максимальное время в днях для сохранения файлов кэша.</p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>качефилемаксдискусаже</strong></p></td>
    <td><p>Определяется как часть дискового пространства (выраженное в процентах), которое может использоваться под файлы кэша.</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>Превышений значения componentthrottlelimit</strong></p></td>
    <td><p>Определяется как максимальное количество трассировок в секунду, которое может создавать компонент до активации автоматического ограничителя.</p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>компонентсроттлесампле</strong></p></td>
    <td><p>Количество превышений значения ComponentThrottleLimit в течение 60 секунд.</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>минимумклсажентсервицеверсион</strong></p></td>
    <td><p>Минимальная версия CLSAgent, допустимая для запуска. Этот элемент предназначен для Office 365 или Microsoft 365.</p></td>
    </tr>
    </tbody>
    </table>


</div>

<div>

## <a name="see-also"></a>См. также


[Обзор централизованной службы ведения журналов в Lync Server 2013](lync-server-2013-overview-of-the-centralized-logging-service.md)  


[Set — CsClsConfiguration](https://technet.microsoft.com/library/JJ619182(v=OCS.15))  
[Remove — CsClsConfiguration](https://technet.microsoft.com/library/JJ619191(v=OCS.15))  
[New — CsClsConfiguration](https://technet.microsoft.com/library/JJ619177(v=OCS.15))  
[Get — CsClsConfiguration](https://technet.microsoft.com/library/JJ619179(v=OCS.15))  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

