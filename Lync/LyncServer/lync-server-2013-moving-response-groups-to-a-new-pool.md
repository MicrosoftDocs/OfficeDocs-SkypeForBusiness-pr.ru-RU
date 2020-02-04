---
title: 'Lync Server 2013: перемещение групп ответов в новый пул'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Moving response groups to a new pool
ms:assetid: da0db765-41e5-430b-b5a7-5418ec5ff2a7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205298(v=OCS.15)
ms:contentKeyID: 48185538
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 96740d8937f1548952d41d5674ef3e66cd29e2b6
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756713"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="moving-response-groups-to-a-new-pool-in-lync-server-2013"></a>Перемещение групп ответа в новый пул в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-11-01_

Lync Server 2013 предлагает новую поддержку командлетов для перемещения групп ответов из одного пула в другой, даже если полное доменное имя (FQDN) отличается.

Выполните действия, описанные в приведенной ниже процедуре, для перемещения групп ответов из пула переднего плана в другой пул переднего плана с другим полным доменным именем.

<div>


> [!NOTE]  
> В среде сосуществования вы можете перемещать группы ответов только между пулами интерфейсов внешних&nbsp;интерфейсов Lync Server 2013.



</div>

<div>

## <a name="to-move-response-groups-to-a-pool-with-a-different-fqdn"></a>Перемещение групп ответа в пул с другим полным доменным именем

1.  Запустите командную консоль Lync Server Management Shell: нажмите кнопку **Пуск**, выберите **все программы**, а затем — **Microsoft Lync Server 2013**, а затем — **Командная консоль Lync Server Management Shell**.

2.  Экспортируйте группы ответов в исходном пуле. В командной строке введите следующую команду:
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<source FQDN>" -FileName "<export file name>"
    
    Например:
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:source.contoso.com" -FileName "C:\RgsExportSource.zip"
    
    Чтобы удалить группы ответов из исходного пула во время экспорта, включите параметр – Ремовикспортедконфигуратион. Например:
    
        Export-CsRgsConfiguration -Source ApplicationServer:source.contoso.com -FileName "C:\RgsExportSource.zip" -RemoveExportedConfiguration

3.  Импортируйте группы ответа в целевой пул и назначьте пул назначения в качестве нового владельца. В командной строке выполните следующую команду:
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:<destination pool>" -FileName "<export file name>" -OverwriteOwner
    
    Если вы также хотите скопировать параметры уровня приложения группы ответа из исходного пула в конечный пул, добавьте параметр – Реплацеексистингргссеттингс. Для каждого пула можно задать на уровне приложения только один набор параметров. При копировании параметров уровня приложения из исходного пула в конечный пул параметры из исходного пула заменяют параметры для целевого пула. Если вы не копируете параметры уровня приложения из исходного пула, в импортированных группах ответа применяются существующие параметры из целевого пула.
    
    Например:
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:destination.contoso.com" -FileName "C:\RgsExportSource.zip" -OverwriteOwner -ReplaceExistingRgsSettings
    
    <div>
    

    > [!NOTE]  
    > Параметры уровня приложения включают стандартную конфигурацию хранения музыки, используемую по умолчанию в качестве звукового файла для хранения музыки, агент рингбакк льготный период и контекстную конфигурацию вызова. Чтобы просмотреть эти параметры конфигурации, запустите командлет <STRONG>Get-ксргсконфигуратион</STRONG> . Подробнее об этом командлете можно узнать в <A href="https://docs.microsoft.com/powershell/module/skype/Get-CsRgsConfiguration">статьях Get-ксргсконфигуратион</A>.

    
    </div>

4.  Убедитесь, что импорт прошел успешно, отображая импортированную конфигурацию группы ответа следующим образом.
    
      - Убедитесь, что все рабочие процессы импортированы. В командной строке введите следующую команду:
        
            Get-CsRgsWorkflow -Identity "service:ApplicationServer:<destination pool FQDN>"
    
      - Убедитесь, что все очереди импортированы. В командной строке введите следующую команду:
        
            Get-CsRgsQueue -Identity "service:ApplicationServer:<destination pool FQDN>"
    
      - Убедитесь, что все группы агента импортированы. В командной строке введите следующую команду:
        
            Get-CsRgsAgentGroup -Identity "service:ApplicationServer:<destination pool FQDN>"
    
      - Убедитесь, что все деловые часы были импортированы. В командной строке введите следующую команду:
        
            Get-CsRgsHoursOfBusiness -Identity "service:ApplicationServer:<destination pool FQDN>" 
    
      - Убедитесь, что все наборы праздников импортированы. В командной строке введите следующую команду:
        
            Get-CsRgsHolidaySet -Identity "service:ApplicationServer:<destination pool FQDN>" 

5.  Убедитесь, что импорт выполнен успешно, поместив вызов в одну из групп ответа и подтверждаю, что вызов обрабатывается правильно.

6.  Агенты запросов, являющиеся членами формальных групп агента, для входа в группы агента в целевом пуле.

7.  Если вы ранее не удалили группы ответов из исходного пула, удалите группы ответов из исходного пула. В командной строке введите следующую команду:
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<source pool FQDN> -RemoveExportedConfiguration -FileName "<temporary export file name>"
    
    Например:
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:source.contoso.com" -RemoveExportedConfiguration -FileName "C:\TempRGsConfiguration.zip"

</div>

</div>

<span> </span>

</div>

</div>

</div>

