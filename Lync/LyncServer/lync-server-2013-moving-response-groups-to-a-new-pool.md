---
title: 'Lync Server 2013: перемещение групп ответа в новый пул'
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
ms.openlocfilehash: 562d519e278096acf589482124eeb9cdf7ebf189
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42153601"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="moving-response-groups-to-a-new-pool-in-lync-server-2013"></a>Перемещение групп ответа в новый пул в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-11-01_

Lync Server 2013 представляет новую поддержку командлетов для перемещения групп ответа из одного пула в другой, даже если полное доменное имя (FQDN) отличается.

Выполните действия, описанные в следующей процедуре, чтобы переместить группы ответа из одного пула переднего плана в другой интерфейсный пул с другим полным доменным именем.

<div>


> [!NOTE]  
> В среде сосуществования можно перемещать группы ответа только между интерфейсными пулами Lync Server&nbsp;2013.



</div>

<div>

## <a name="to-move-response-groups-to-a-pool-with-a-different-fqdn"></a>Перемещение группы ответа в пул с другими полным доменным именем

1.  Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.

2.  Экспортируйте группу ответа в исходном пуле. В командной строке введите:
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<source FQDN>" -FileName "<export file name>"
    
    Пример:
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:source.contoso.com" -FileName "C:\RgsExportSource.zip"
    
    Чтобы удалить группы ответа из исходного пула во время экспорта, включите в команду параметр –RemoveExportedConfiguration. Пример:
    
        Export-CsRgsConfiguration -Source ApplicationServer:source.contoso.com -FileName "C:\RgsExportSource.zip" -RemoveExportedConfiguration

3.  Импортируйте группы ответа в конечный пул и назначьте конечный пул новому владельцу. В командной строке введите:
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:<destination pool>" -FileName "<export file name>" -OverwriteOwner
    
    Если вы также хотите скопировать параметры уровня приложения группы ответа из исходного пула в целевой пул, включите параметр – Реплацеексистингргссеттингс. Для каждого пула можно указать только один набор параметров уровня приложения. Если вы копируете параметры уровня приложения из исходного пула в целевой пул, параметры из исходного пула заменяют параметры целевого пула. Если вы не копируете параметры из исходного пула, к импортируемым группам ответа применяются существующие параметры из целевого пула.
    
    Пример:
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:destination.contoso.com" -FileName "C:\RgsExportSource.zip" -OverwriteOwner -ReplaceExistingRgsSettings
    
    <div>
    

    > [!NOTE]  
    > Параметры уровня приложения включают используемую по умолчанию конфигурацию музыки для хранения музыки, по умолчанию музыкальный файл по умолчанию, период отсрочки агента удерживаемого абонента и конфигурацию контекста вызовов. Чтобы просмотреть эти параметры конфигурации, запустите командлет <STRONG>Get – CsRgsConfiguration</STRONG> . Подробнее об этом командлете можно узнать в статье <A href="https://docs.microsoft.com/powershell/module/skype/Get-CsRgsConfiguration">Get – CsRgsConfiguration</A>.

    
    </div>

4.  Убедитесь, что импорт выполнен успешно, просмотрев импортированную конфигурацию группы ответа. Для этого выполните следующие действия:
    
      - Убедитесь, что импортированы все рабочие процессы. В командной строке введите следующую команду:
        
            Get-CsRgsWorkflow -Identity "service:ApplicationServer:<destination pool FQDN>"
    
      - Убедитесь, что импортированы все очереди. В командной строке введите следующую команду:
        
            Get-CsRgsQueue -Identity "service:ApplicationServer:<destination pool FQDN>"
    
      - Убедитесь, что импортированы все группы агентов. В командной строке введите следующую команду:
        
            Get-CsRgsAgentGroup -Identity "service:ApplicationServer:<destination pool FQDN>"
    
      - Убедитесь, что импортированы все часы работы. В командной строке введите следующую команду:
        
            Get-CsRgsHoursOfBusiness -Identity "service:ApplicationServer:<destination pool FQDN>" 
    
      - Убедитесь, что импортированы все наборы выходных. В командной строке введите следующую команду:
        
            Get-CsRgsHolidaySet -Identity "service:ApplicationServer:<destination pool FQDN>" 

5.  Убедитесь, что импорт выполнен успешно, позвонив в одну из групп ответа и убедившись, что вызов обрабатывается правильно.

6.  Попросите агентов, которые являются участниками формальных групп агентов, войти в свои группы в конечном пуле.

7.  Если группы ответа не удалялись из исходного пула в ходе процедуры, удалите их из него. В командной строке введите:
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<source pool FQDN> -RemoveExportedConfiguration -FileName "<temporary export file name>"
    
    Пример:
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:source.contoso.com" -RemoveExportedConfiguration -FileName "C:\TempRGsConfiguration.zip"

</div>

</div>

<span> </span>

</div>

</div>

</div>

