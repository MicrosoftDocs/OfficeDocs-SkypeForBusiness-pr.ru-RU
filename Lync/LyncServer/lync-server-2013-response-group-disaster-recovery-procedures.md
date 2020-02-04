---
title: 'Lync Server 2013: процедуры аварийного восстановления группы ответа'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Response group disaster recovery procedures
ms:assetid: b49577b7-0ca3-4f20-b614-f3a2a0046b58
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205186(v=OCS.15)
ms:contentKeyID: 48185171
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5325f84ff5bf5a0f8d9d1a856110e0ac18b37d93
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723629"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="response-group-disaster-recovery-procedures-in-lync-server-2013"></a>Процедуры аварийного восстановления группы ответа в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-11-01_

На этапе восстановления после сбоя в аварийном восстановлении группы ответа находятся в нескольких пулах: в основном пуле (который недоступен) и в пуле резервных копий. Группы ответа в обоих пулах имеют одинаковое имя и одного и того же владельца (основного пула), но у них разные родители. В течение этого времени командлеты группы ответа работают немного по-другому. Не забудьте использовать параметры, как указано в описанной ниже процедуре. Сведения о том, как работают командлеты на этапе перехода на другой ресурс, приведены в статье сведения о переходе на веб – странице [http://go.microsoft.com/fwlink/p/?LinkId=263957](http://go.microsoft.com/fwlink/p/?linkid=263957)блога "Lync Server 2013: восстановление групп ответов во время аварийного восстановления" Эта статья в блоге также относится к выпущенной версии Lync Server 2013.

Выполните действия, описанные в приведенной ниже процедуре, для подготовки и выполнения аварийного восстановления для службы группы ответа Lync Server.

<div>

## <a name="to-fail-over-and-fail-back-response-group"></a>Группа ответа для отработки отказа и отката

1.  Запустите командную консоль Lync Server Management Shell: нажмите кнопку **Пуск**, выберите **все программы**, а затем — **Microsoft Lync Server 2013**, а затем — **Командная консоль Lync Server Management Shell**.

2.  Регулярное выполнение резервного копирования. В командной строке введите следующую команду:
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<primary pool FQDN>" -FileName "<backup path and file name>"
    
    Например:
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:primary.contoso.com" -FileName "C:\RgsExportPrimary.zip"

3.  Во время сбоя после перехода на другой ресурс в пул резервной копии импортируйте группы ответа в пул резервных копий. В командной строке выполните следующую команду:
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:<backup pool FQDN>" -FileName "<backup path and file name>"
    
    Если вы хотите заменить параметры уровня приложения в пуле резервных копий параметрами из основного пула, добавьте параметр – Реплацеексистингсеттингс. Например:
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:backup.contoso.com" -FileName "C:\RgsExportPrimary.zip" -ReplaceExistingSettings
    
    <div>
    

    > [!WARNING]  
    > Если вы не заменили параметры в пуле резервных копий и не сможете восстановить основной пул, настройки основного пула будут потеряны. Подробные сведения можно найти <A href="lync-server-2013-planning-for-response-group-disaster-recovery.md">в разделе Планирование аварийного восстановления групп ответов в Lync Server 2013</A>.

    
    </div>

4.  Убедитесь, что импорт прошел успешно, отображая импортированные группы ответа. Импортированные группы ответов по-прежнему принадлежат основным пулам. Выполните указанные ниже действия.
    
      - Отобразите все рабочие процессы в пуле резервных копий, которым владеет основной пул, и убедитесь, что все основные рабочие процессы пула включены. В командной строке введите следующую команду:
        
            Get-CsRgsWorkflow -Identity "service:ApplicationServer:<backup pool FQDN>" -Owner "service:ApplicationServer"<primary pool FQDN>
        
        Например:
        
            Get-CsRgsWorkflow -Identity "service:ApplicationServer:backup.contoso.com" -Owner "service:ApplicationServer:primary.contoso.com"
    
      - Отобразите все очереди в пуле резервных копий, владельцем которых является основной пул, и убедитесь, что все очереди основного пула включены. В командной строке введите следующую команду:
        
            Get-CsRgsQueue -Identity "service:ApplicationServer:<backup pool FQDN>" -Owner "service:ApplicationServer"<primary pool FQDN>
        
        Например:
        
            Get-CsRgsQueue -Identity "service:ApplicationServer:backup.contoso.com" -Owner "service:ApplicationServer"primary.contoso.com"
    
      - Отобразить все группы агентов в пуле резервных копий, владельцем которых является основной пул, и убедиться в том, что все группы агентов основного пула включены. В командной строке введите следующую команду:
        
            Get-CsRgsAgentGroup -Identity "service:ApplicationServer:<backup pool FQDN>" -Owner "service:ApplicationServer"<primary pool FQDN>
        
        Например:
        
            Get-CsRgsAgentGroup -Identity "service:ApplicationServer:backup.contoso.com" -Owner "service:ApplicationServer"primary.contoso.com"
    
      - Отображение всех рабочих часов в пуле резервных копий, принадлежащих основным пулам, и проверка того, что все основные часы бизнеса включены в бизнес-пул. В командной строке введите следующую команду:
        
            Get-CsRgsHoursOfBusiness -Identity "service:ApplicationServer:<backup pool FQDN>" -Owner "service:ApplicationServer"<primary pool FQDN>
        
        Например:
        
            Get-CsRgsHoursOfBusiness -Identity "service:ApplicationServer:backup.contoso.com" -Owner "service:ApplicationServer"primary.contoso.com"
    
      - Отобразить все наборы праздников в пуле резервных копий, владельцем которых является основной пул, и убедиться, что все наборы праздников основного пула включены. В командной строке введите следующую команду:
        
            Get-CsRgsHolidaySet -Identity "service:ApplicationServer:<backup pool FQDN>" -Owner "service:ApplicationServer"<primary pool FQDN>
        
        Например:
        
            Get-CsRgsHolidaySet -Identity "service:ApplicationServer:backup.contoso.com" -Owner "service:ApplicationServer"primary.contoso.com"
    
    Кроме того, вы можете отобразить все группы ответов в пуле резервных копий, в том числе владельцами основного пула и владельцами из пула резервных копий с помощью параметра – Шовалл вместо параметра – owner. Например:
    
        Get-CsRgsWorkflow -Identity "service:ApplicationServer:<backup pool FQDN>" -ShowAll
    
    <div>
    

    > [!IMPORTANT]  
    > Необходимо использовать либо параметр – Шовалл, либо параметр – owner. Если вы не используете ни один из этих параметров, группы ответа, импортированные в пул резервных копий, не будут указаны в результатах, возвращенных командлетами.

    
    </div>

5.  Убедитесь, что импорт выполнен успешно, поместив вызов в импортированную группу ответа и подтверждаю, что вызов обрабатывается правильно.

6.  Агенты запросов, являющиеся членами формальных групп агента, для входа в группы агента в пуле резервного копирования.

7.  Управление импортированными группами ответа и их изменение в обычном режиме.
    
    <div>
    

    > [!IMPORTANT]  
    > Группы ответа находятся в пуле резервных копий, поэтому для управления ими вы должны использовать командную консоль Lync Server Management Shell. Вы не можете использовать панель управления Lync Server для управления группами ответа, которые вы импортировали в пул резервных копий.

    
    </div>

8.  После восстановления основного пула и завершения восстановления, экспортируйте группы ответов основного пула, которые были импортированы в пул резервных копий. В командной строке выполните следующую команду:
    
        Export-CsRgsConfiguration -Source ApplicationServer:<backup pool FQDN> -Owner ApplicationServer:<primary pool FQDN> -FileName "<backup path and file name>"

9.  Импортируйте группы ответа обратно в основной пул. В командной строке введите следующую команду:
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:<primary pool FQDN>" -OverwriteOwner -FileName "<exported path and file name>"
    
    Например:
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:primary.contoso.com" -OverwriteOwner -FileName "C:\RgsExportPrimaryUpdated.zip"
    
    <div>
    

    > [!NOTE]  
    > Если вы перестраиваете пул во время восстановления, независимо от того, есть ли у него другое полное доменное имя (FQDN), необходимо использовать параметр – Овервритеовнер. Как правило, вы всегда можете использовать параметр – Овервритеовнер при импорте групп ответа обратно в основной пул.

    
    </div>
    
    Если вы развернули новый пул (с таким же или другим полным доменным именем) для замены основного пула и хотите использовать параметры уровня приложения из пула резервного копирования для нового пула, добавьте параметр – Реплацеексистингсеттингс. В командной строке введите следующую команду:
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:<new primary pool FQDN>" -OverwriteOwner -FileName "<exported path and file name>" -ReplaceExistingSettings
    
    Например:
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:newprimary.contoso.com" -OverwriteOwner -FileName "C:\RgsExportPrimaryUpdated.zip" -ReplaceExistingSettings
    
    <div>
    

    > [!IMPORTANT]  
    > Если вы не хотите заменять параметры уровня приложения и звуковой файл для хранения музыки по умолчанию для нового пула с параметрами из пула резервных копий, в новом пуле будут использоваться параметры по умолчанию на уровне приложения.

    
    </div>

10. Убедитесь, что импорт возвращен в основной пул, отображая импортированную конфигурацию группы ответа. Выполните указанные ниже действия.
    
      - Отобразите все рабочие процессы в основном пуле и убедитесь, что все импортированные рабочие процессы включены. В командной строке введите следующую команду:
        
            Get-CsRgsWorkflow -Identity "service:ApplicationServer:<primary pool FQDN>" -ShowAll
        
        Например:
        
            Get-CsRgsWorkflow -Identity "service:ApplicationServer: primary.contoso.com" -ShowAll
    
      - Отобразите все очереди в основном пуле и убедитесь, что все импортированные очереди включены. В командной строке введите следующую команду:
        
            Get-CsRgsQueue -Identity "service:ApplicationServer:<primary pool FQDN>" -ShowAll
        
        Например:
        
            Get-CsRgsQueue -Identity "service:ApplicationServer:primary.contoso.com" -ShowAll
    
      - Отобразить все группы агентов в основном пуле и убедиться, что все импортированные группы агентов включены. В командной строке введите следующую команду:
        
            Get-CsRgsAgentGroup -Identity "service:ApplicationServer: <primary pool FQDN>" -ShowAll
        
        Например:
        
            Get-CsRgsAgentGroup -Identity "service:ApplicationServer:primary.contoso.com" -ShowAll
    
      - Отображение всех рабочих часов в основном пуле и проверка того, что все импортированные часы бизнеса включены. В командной строке введите следующую команду:
        
            Get-CsRgsHoursOfBusiness -Identity "service:ApplicationServer:<primary pool FQDN>" -ShowAll
        
        Например:
        
            Get-CsRgsHoursOfBusiness -Identity "service:ApplicationServer:primary.contoso.com" -ShowAll
    
      - Отобразите все наборы праздников в основном пуле и убедитесь, что все импортированные наборы праздников включены. В командной строке введите следующую команду:
        
            Get-CsRgsHolidaySet -Identity "service:ApplicationServer:<primary pool FQDN>" -ShowAll
        
        Например:
        
            Get-CsRgsHolidaySet -Identity "service:ApplicationServer:primary.contoso.com" -ShowAll

11. Убедитесь, что импорт выполнен успешно, поместив вызов в импортированную группу ответа и подтверждаю, что вызов обрабатывается правильно.

12. При необходимости удалите группы ответа, принадлежащие основным пулам из пула резервных копий. В командной строке введите следующую команду:
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<backup pool FQDN>" -Owner "service:ApplicationServer:<primary pool FQDN>" -FileName "<backup path and file name>" -RemoveExportedConfiguration
    
    Например:
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:backup.contoso.com" -Owner "service:ApplicationServer:primary.contoso.com" -FileName "C:\RgsExportPrimaryUpdated.zip" -RemoveExportedConfiguration
    
    <div>
    

    > [!NOTE]  
    > На этом этапе создается новый файл с экспортированной конфигурацией, а затем он удаляется из пула резервных копий.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

