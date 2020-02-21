---
title: Процедуры аварийного восстановления для группы ответа Lync Server 2013
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
ms.openlocfilehash: 254f9e95edfb445d996948a17064ae460dbdb7d8
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42214875"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="response-group-disaster-recovery-procedures-in-lync-server-2013"></a><span data-ttu-id="07ef3-102">Процедуры аварийного восстановления группы ответа в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="07ef3-102">Response group disaster recovery procedures in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="07ef3-103">_**Последнее изменение темы:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="07ef3-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="07ef3-104">На этапе отработки отказа в процессе аварийного восстановления группы ответа находятся в двух пулах: основном (который недоступен) и резервном.</span><span class="sxs-lookup"><span data-stu-id="07ef3-104">During the failover phase of disaster recovery, the response groups reside in multiple pools: in the primary pool (which is unavailable) and in the backup pool.</span></span> <span data-ttu-id="07ef3-105">Группы ответа в обоих пулах имеют одинаковое имя и владельца (основной пул), но разные родительские объекты.</span><span class="sxs-lookup"><span data-stu-id="07ef3-105">The response groups in both pools have the same name and the same owner (the primary pool), but they have different parents.</span></span> <span data-ttu-id="07ef3-106">В течение этого времени командлеты группы ответа работают немного по-другому.</span><span class="sxs-lookup"><span data-stu-id="07ef3-106">During this time, Response Group cmdlets work a little differently.</span></span> <span data-ttu-id="07ef3-107">Используйте параметры так, как описано в следующей процедуре.</span><span class="sxs-lookup"><span data-stu-id="07ef3-107">Be sure to use parameters as specified in the following procedure.</span></span> <span data-ttu-id="07ef3-108">Сведения о том, как работают командлеты на этапе отработки отказа, приведены в статье "Lync Server 2013: восстановление групп ответа при [https://go.microsoft.com/fwlink/p/?LinkId=263957](https://go.microsoft.com/fwlink/p/?linkid=263957)аварийном восстановлении" на сайте.</span><span class="sxs-lookup"><span data-stu-id="07ef3-108">For details about how cmdlets work during the failover phase, see NextHop blog article "Lync Server 2013: Recovering Response Groups During Disaster Recovery" at [https://go.microsoft.com/fwlink/p/?LinkId=263957](https://go.microsoft.com/fwlink/p/?linkid=263957).</span></span> <span data-ttu-id="07ef3-109">Эта статья в блоге также относится к выпущенной версии Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="07ef3-109">This blog article also applies to the released version of Lync Server 2013.</span></span>

<span data-ttu-id="07ef3-110">Выполните действия, описанные в следующей процедуре, чтобы подготовиться к аварийному восстановлению для службы группы ответа Lync Server и выполнить аварийное восстановление.</span><span class="sxs-lookup"><span data-stu-id="07ef3-110">Use the steps in the following procedure to prepare for and perform disaster recovery for Lync Server Response Group service.</span></span>

<div>

## <a name="to-fail-over-and-fail-back-response-group"></a><span data-ttu-id="07ef3-111">Отработка отказа и восстановление размещения группы ответа</span><span class="sxs-lookup"><span data-stu-id="07ef3-111">To fail over and fail back Response Group</span></span>

1.  <span data-ttu-id="07ef3-112">Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="07ef3-112">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="07ef3-p102">Создайте резервные копии. Используйте следующую команду:</span><span class="sxs-lookup"><span data-stu-id="07ef3-p102">Routinely perform backups. At the command line, type:</span></span>
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<primary pool FQDN>" -FileName "<backup path and file name>"
    
    <span data-ttu-id="07ef3-115">Например:</span><span class="sxs-lookup"><span data-stu-id="07ef3-115">For example:</span></span>
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:primary.contoso.com" -FileName "C:\RgsExportPrimary.zip"

3.  <span data-ttu-id="07ef3-p103">Переключитесь на резервный пул и затем импортируйте группы ответа в резервный пул. Используйте следующую команду:</span><span class="sxs-lookup"><span data-stu-id="07ef3-p103">During an outage, after failover to the backup pool, import the response groups to the backup pool. At the command line, type:</span></span>
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:<backup pool FQDN>" -FileName "<backup path and file name>"
    
    <span data-ttu-id="07ef3-p104">Если требуется заменить параметры приложений резервного пула на параметры приложений из основного пула, добавьте параметр –ReplaceExistingSettings. Пример:</span><span class="sxs-lookup"><span data-stu-id="07ef3-p104">If you want to replace the application-level settings in the backup pool with the settings from the primary pool, include the –ReplaceExistingSettings parameter. For example:</span></span>
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:backup.contoso.com" -FileName "C:\RgsExportPrimary.zip" -ReplaceExistingSettings
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="07ef3-120">Если вы не замените параметры в резервном пуле и вам не удастся восстановить основной пул, то параметры основного пула будут утеряны.</span><span class="sxs-lookup"><span data-stu-id="07ef3-120">If you do not replace the settings in the backup pool and the primary pool can't be recovered, the primary pool settings will be lost.</span></span> <span data-ttu-id="07ef3-121">Дополнительные сведения см <A href="lync-server-2013-planning-for-response-group-disaster-recovery.md">в разделе Планирование аварийного восстановления группы ответа в Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="07ef3-121">For details, see <A href="lync-server-2013-planning-for-response-group-disaster-recovery.md">Planning for response group disaster recovery in Lync Server 2013</A>.</span></span>

    
    </div>

4.  <span data-ttu-id="07ef3-p106">Чтобы проверить завершение импорта, просмотрите импортированные группы ответа. Владельцем импортированных групп ответа по-прежнему является основной пул. Выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="07ef3-p106">Verify that the import was successful by displaying the imported response groups. The imported response groups are still owned by the primary pool. Do the following:</span></span>
    
      - <span data-ttu-id="07ef3-p107">Выведите список всех рабочих процессов резервного пула, владельцем которых является основной пул, и убедитесь, что добавлены все рабочие процессы основного пула. Используйте следующую команду:</span><span class="sxs-lookup"><span data-stu-id="07ef3-p107">Display all the workflows in the backup pool that are owned by the primary pool, and verify that all the primary pool workflows are included. At the command line, type:</span></span>
        
            Get-CsRgsWorkflow -Identity "service:ApplicationServer:<backup pool FQDN>" -Owner "service:ApplicationServer"<primary pool FQDN>
        
        <span data-ttu-id="07ef3-127">Например:</span><span class="sxs-lookup"><span data-stu-id="07ef3-127">For example:</span></span>
        
            Get-CsRgsWorkflow -Identity "service:ApplicationServer:backup.contoso.com" -Owner "service:ApplicationServer:primary.contoso.com"
    
      - <span data-ttu-id="07ef3-p108">Выведите список всех очередей резервного пула, владельцем которых является основной пул, и убедитесь, что добавлены все очереди основного пула. Используйте следующую команду:</span><span class="sxs-lookup"><span data-stu-id="07ef3-p108">Display all the queues in the backup pool that are owned by the primary pool, and verify that all the primary pool queues are included. At the command line, type:</span></span>
        
            Get-CsRgsQueue -Identity "service:ApplicationServer:<backup pool FQDN>" -Owner "service:ApplicationServer"<primary pool FQDN>
        
        <span data-ttu-id="07ef3-130">Например:</span><span class="sxs-lookup"><span data-stu-id="07ef3-130">For example:</span></span>
        
            Get-CsRgsQueue -Identity "service:ApplicationServer:backup.contoso.com" -Owner "service:ApplicationServer"primary.contoso.com"
    
      - <span data-ttu-id="07ef3-p109">Выведите список всех групп агентов резервного пула, владельцем которых является основной пул, и убедитесь, что добавлены все группы агентов основного пула. Используйте следующую команду:</span><span class="sxs-lookup"><span data-stu-id="07ef3-p109">Display all the agent groups in the backup pool that are owned by the primary pool, and verify that all the primary pool agent groups are included. At the command line, type:</span></span>
        
            Get-CsRgsAgentGroup -Identity "service:ApplicationServer:<backup pool FQDN>" -Owner "service:ApplicationServer"<primary pool FQDN>
        
        <span data-ttu-id="07ef3-133">Например:</span><span class="sxs-lookup"><span data-stu-id="07ef3-133">For example:</span></span>
        
            Get-CsRgsAgentGroup -Identity "service:ApplicationServer:backup.contoso.com" -Owner "service:ApplicationServer"primary.contoso.com"
    
      - <span data-ttu-id="07ef3-p110">Выведите список всех режимов работы резервного пула, владельцем которых является основной пул, и убедитесь, что добавлены все режимы работы основного пула. Используйте следующую команду:</span><span class="sxs-lookup"><span data-stu-id="07ef3-p110">Display all the hours of business in the backup pool that are owned by the primary pool, and verify that all the primary pool hours of business are included. At the command line, type:</span></span>
        
            Get-CsRgsHoursOfBusiness -Identity "service:ApplicationServer:<backup pool FQDN>" -Owner "service:ApplicationServer"<primary pool FQDN>
        
        <span data-ttu-id="07ef3-136">Например:</span><span class="sxs-lookup"><span data-stu-id="07ef3-136">For example:</span></span>
        
            Get-CsRgsHoursOfBusiness -Identity "service:ApplicationServer:backup.contoso.com" -Owner "service:ApplicationServer"primary.contoso.com"
    
      - <span data-ttu-id="07ef3-p111">Выведите список всех наборов выходных дней резервного пула, владельцем которых является основной пул, и убедитесь, что добавлены все наборы выходных дней основного пула. Используйте следующую команду:</span><span class="sxs-lookup"><span data-stu-id="07ef3-p111">Display all the holiday sets in the backup pool that are owned by the primary pool, and verify that all the primary pool holiday sets are included. At the command line, type:</span></span>
        
            Get-CsRgsHolidaySet -Identity "service:ApplicationServer:<backup pool FQDN>" -Owner "service:ApplicationServer"<primary pool FQDN>
        
        <span data-ttu-id="07ef3-139">Например:</span><span class="sxs-lookup"><span data-stu-id="07ef3-139">For example:</span></span>
        
            Get-CsRgsHolidaySet -Identity "service:ApplicationServer:backup.contoso.com" -Owner "service:ApplicationServer"primary.contoso.com"
    
    <span data-ttu-id="07ef3-p112">Чтобы получить список всех групп ответа в резервном пуле, включая группы ответа, владельцем которых является основной пул, и группы ответа, владельцем которых является резервный пул, необходимо вместо параметра –Owner указать параметр –ShowAll. Пример:</span><span class="sxs-lookup"><span data-stu-id="07ef3-p112">Alternatively, you can display all the response groups in the backup pool, including the ones owned by the primary pool and the ones owned by the backup pool by using the –ShowAll parameter instead of the –Owner parameter. For example:</span></span>
    
        Get-CsRgsWorkflow -Identity "service:ApplicationServer:<backup pool FQDN>" -ShowAll
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="07ef3-p113">Нужно использовать либо параметр –ShowAll, либо параметр –Owner. Если вы не используете ни один из них, группы ответа, импортированные в резервный пул, не будут приведены в возвращаемых командлетами результатах.</span><span class="sxs-lookup"><span data-stu-id="07ef3-p113">You must use either the –ShowAll parameter or the –Owner parameter. If you do not use either of these parameters, the response groups that you imported to the backup pool will not be listed in the results returned by the cmdlets.</span></span>

    
    </div>

5.  <span data-ttu-id="07ef3-144">Чтобы проверить завершение импорта, совершите звонок импортированной группе ответа и убедитесь, что звонок обрабатывается правильно.</span><span class="sxs-lookup"><span data-stu-id="07ef3-144">Verify that the import was successful by placing a call to an imported response group and verifying that the call is handled correctly.</span></span>

6.  <span data-ttu-id="07ef3-145">Попросите агентов, которые являются членами групп формальных агентов, выполнить вход в свои группы в резервном пуле.</span><span class="sxs-lookup"><span data-stu-id="07ef3-145">Request agents who are members of formal agent groups to sign in to their agent groups in the backup pool.</span></span>

7.  <span data-ttu-id="07ef3-146">Измените импортированные группы ответа с помощью стандартных процедур.</span><span class="sxs-lookup"><span data-stu-id="07ef3-146">Manage and modify the imported response groups as usual.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="07ef3-147">Группы ответа находятся в резервном пуле, поэтому для управления ими необходимо использовать командную консоль Lync Server.</span><span class="sxs-lookup"><span data-stu-id="07ef3-147">While the response groups are in the backup pool, you need to use Lync Server Management Shell to manage them.</span></span> <span data-ttu-id="07ef3-148">Вы не можете использовать панель управления Lync Server для управления группами ответа, импортированными в резервный пул.</span><span class="sxs-lookup"><span data-stu-id="07ef3-148">You cannot use Lync Server Control Panel to manage the response groups that you imported to the backup pool.</span></span>

    
    </div>

8.  <span data-ttu-id="07ef3-p115">После того как основной пул будет восстановлен и восстановление размещения завершено, экспортируйте группы ответа основного пула, которые были импортированы в резервный пул. Используйте следующую команду:</span><span class="sxs-lookup"><span data-stu-id="07ef3-p115">After the primary pool is restored and failback is complete, export the primary pool response groups that were imported to the backup pool. At the command line, type:</span></span>
    
        Export-CsRgsConfiguration -Source ApplicationServer:<backup pool FQDN> -Owner ApplicationServer:<primary pool FQDN> -FileName "<backup path and file name>"

9.  <span data-ttu-id="07ef3-p116">Импортируйте группы ответа обратно в основной пул. Используйте следующую команду:</span><span class="sxs-lookup"><span data-stu-id="07ef3-p116">Import the response groups back to the primary pool. At the command line, type:</span></span>
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:<primary pool FQDN>" -OverwriteOwner -FileName "<exported path and file name>"
    
    <span data-ttu-id="07ef3-153">Например:</span><span class="sxs-lookup"><span data-stu-id="07ef3-153">For example:</span></span>
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:primary.contoso.com" -OverwriteOwner -FileName "C:\RgsExportPrimaryUpdated.zip"
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="07ef3-p117">Если в процессе восстановления вы перестраиваете пул, меняя или не меняя полное доменное имя, необходимо использовать параметр –OverwriteOwner. Как показывает опыт, вы всегда можете использовать параметр –OverwriteOwner при импорте групп ответа обратно в основной пул.</span><span class="sxs-lookup"><span data-stu-id="07ef3-p117">If you rebuild a pool during recovery, whether with the same or a different fully qualified domain name (FQDN), you need to use the –OverwriteOwner parameter. As a rule of thumb, you can always use the –OverwriteOwner parameter when you import response groups back to the primary pool.</span></span>

    
    </div>
    
    <span data-ttu-id="07ef3-p118">Если вы развертываете новый пул (с таким же или другим полным доменным именем) для замены основного пула и хотите использовать в новом пуле параметры приложений из резервного пула, добавьте параметр –ReplaceExistingSettings. Используйте следующую команду:</span><span class="sxs-lookup"><span data-stu-id="07ef3-p118">If you deployed a new pool (with the same or a different FQDN) to replace the primary pool, and you want to use the application-level settings from the backup pool for the new pool, include the –ReplaceExistingSettings parameter. At the command line, type:</span></span>
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:<new primary pool FQDN>" -OverwriteOwner -FileName "<exported path and file name>" -ReplaceExistingSettings
    
    <span data-ttu-id="07ef3-158">Например:</span><span class="sxs-lookup"><span data-stu-id="07ef3-158">For example:</span></span>
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:newprimary.contoso.com" -OverwriteOwner -FileName "C:\RgsExportPrimaryUpdated.zip" -ReplaceExistingSettings
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="07ef3-159">Если для нового пула вы не хотите использовать параметры приложений и звуковой файл по умолчанию, используемый для воспроизведения музыки на удержании, которые использовались в резервном пуле, в новом пуле будут использоваться параметры приложений по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="07ef3-159">If you don't want to replace the application-level settings and default music-on-hold audio file for the new pool with the settings from the backup pool, the new pool will use the default application-level settings.</span></span>

    
    </div>

10. <span data-ttu-id="07ef3-p119">Чтобы проверить импорт в основной пул, просмотрите импортированную конфигурацию группы. Выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="07ef3-p119">Verify that the import back to the primary pool was successful by displaying the imported response group configuration. Do the following:</span></span>
    
      - <span data-ttu-id="07ef3-p120">Выведите список всех рабочих процессов основного пула и убедитесь в наличии всех импортированных рабочих процессов. Используйте следующую команду:</span><span class="sxs-lookup"><span data-stu-id="07ef3-p120">Display all the workflows in the primary pool, and verify that all the imported workflows are included. At the command line, type:</span></span>
        
            Get-CsRgsWorkflow -Identity "service:ApplicationServer:<primary pool FQDN>" -ShowAll
        
        <span data-ttu-id="07ef3-164">Например:</span><span class="sxs-lookup"><span data-stu-id="07ef3-164">For example:</span></span>
        
            Get-CsRgsWorkflow -Identity "service:ApplicationServer: primary.contoso.com" -ShowAll
    
      - <span data-ttu-id="07ef3-p121">Выведите список всех очередей основного пула и убедитесь в наличии всех импортированных очередей. Используйте следующую команду:</span><span class="sxs-lookup"><span data-stu-id="07ef3-p121">Display all the queues in the primary pool, and verify that all the imported queues are included. At the command line, type:</span></span>
        
            Get-CsRgsQueue -Identity "service:ApplicationServer:<primary pool FQDN>" -ShowAll
        
        <span data-ttu-id="07ef3-167">Например:</span><span class="sxs-lookup"><span data-stu-id="07ef3-167">For example:</span></span>
        
            Get-CsRgsQueue -Identity "service:ApplicationServer:primary.contoso.com" -ShowAll
    
      - <span data-ttu-id="07ef3-p122">Выведите список всех групп агентов основного пула и убедитесь в наличии всех импортированных групп агентов. Используйте следующую команду:</span><span class="sxs-lookup"><span data-stu-id="07ef3-p122">Display all the agent groups in the primary pool, and verify that all the imported agent groups are included. At the command line, type:</span></span>
        
            Get-CsRgsAgentGroup -Identity "service:ApplicationServer: <primary pool FQDN>" -ShowAll
        
        <span data-ttu-id="07ef3-170">Например:</span><span class="sxs-lookup"><span data-stu-id="07ef3-170">For example:</span></span>
        
            Get-CsRgsAgentGroup -Identity "service:ApplicationServer:primary.contoso.com" -ShowAll
    
      - <span data-ttu-id="07ef3-p123">Выведите список всех режимов работы основного пула и убедитесь в наличии всех импортированных режимов работы. Используйте следующую команду:</span><span class="sxs-lookup"><span data-stu-id="07ef3-p123">Display all the hours of business in the primary pool, and verify that all the imported hours of business are included. At the command line, type:</span></span>
        
            Get-CsRgsHoursOfBusiness -Identity "service:ApplicationServer:<primary pool FQDN>" -ShowAll
        
        <span data-ttu-id="07ef3-173">Например:</span><span class="sxs-lookup"><span data-stu-id="07ef3-173">For example:</span></span>
        
            Get-CsRgsHoursOfBusiness -Identity "service:ApplicationServer:primary.contoso.com" -ShowAll
    
      - <span data-ttu-id="07ef3-p124">Выведите список всех наборов выходных дней основного пула и убедитесь в наличии всех импортированных наборов выходных дней. Используйте следующую команду:</span><span class="sxs-lookup"><span data-stu-id="07ef3-p124">Display all the holiday sets in the primary pool, and verify that all the imported holiday sets are included. At the command line, type:</span></span>
        
            Get-CsRgsHolidaySet -Identity "service:ApplicationServer:<primary pool FQDN>" -ShowAll
        
        <span data-ttu-id="07ef3-176">Например:</span><span class="sxs-lookup"><span data-stu-id="07ef3-176">For example:</span></span>
        
            Get-CsRgsHolidaySet -Identity "service:ApplicationServer:primary.contoso.com" -ShowAll

11. <span data-ttu-id="07ef3-177">Чтобы проверить завершение импорта, совершите звонок импортированной группе ответа и убедитесь, что звонок обрабатывается правильно.</span><span class="sxs-lookup"><span data-stu-id="07ef3-177">Verify that the import was successful by placing a call to an imported response group and verifying that the call is handled correctly.</span></span>

12. <span data-ttu-id="07ef3-p125">Удалите из резервного пула группы ответа, владельцем которых является основной пул (необязательно). Используйте следующую команду:</span><span class="sxs-lookup"><span data-stu-id="07ef3-p125">Optionally, remove the response groups owned by the primary pool from the backup pool. At the command line, type:</span></span>
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<backup pool FQDN>" -Owner "service:ApplicationServer:<primary pool FQDN>" -FileName "<backup path and file name>" -RemoveExportedConfiguration
    
    <span data-ttu-id="07ef3-180">Пример:</span><span class="sxs-lookup"><span data-stu-id="07ef3-180">For example:</span></span>
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:backup.contoso.com" -Owner "service:ApplicationServer:primary.contoso.com" -FileName "C:\RgsExportPrimaryUpdated.zip" -RemoveExportedConfiguration
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="07ef3-181">Эта команда создает новый файл с экспортированной конфигурацией и затем удаляет файл из резервного пула.</span><span class="sxs-lookup"><span data-stu-id="07ef3-181">This step creates a new file with the exported configuration, and then removes it from the backup pool.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

