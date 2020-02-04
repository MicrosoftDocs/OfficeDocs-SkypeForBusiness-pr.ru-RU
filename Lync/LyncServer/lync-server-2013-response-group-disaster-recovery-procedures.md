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

# <a name="response-group-disaster-recovery-procedures-in-lync-server-2013"></a><span data-ttu-id="64360-102">Процедуры аварийного восстановления группы ответа в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="64360-102">Response group disaster recovery procedures in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="64360-103">_**Тема последнего изменения:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="64360-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="64360-104">На этапе восстановления после сбоя в аварийном восстановлении группы ответа находятся в нескольких пулах: в основном пуле (который недоступен) и в пуле резервных копий.</span><span class="sxs-lookup"><span data-stu-id="64360-104">During the failover phase of disaster recovery, the response groups reside in multiple pools: in the primary pool (which is unavailable) and in the backup pool.</span></span> <span data-ttu-id="64360-105">Группы ответа в обоих пулах имеют одинаковое имя и одного и того же владельца (основного пула), но у них разные родители.</span><span class="sxs-lookup"><span data-stu-id="64360-105">The response groups in both pools have the same name and the same owner (the primary pool), but they have different parents.</span></span> <span data-ttu-id="64360-106">В течение этого времени командлеты группы ответа работают немного по-другому.</span><span class="sxs-lookup"><span data-stu-id="64360-106">During this time, Response Group cmdlets work a little differently.</span></span> <span data-ttu-id="64360-107">Не забудьте использовать параметры, как указано в описанной ниже процедуре.</span><span class="sxs-lookup"><span data-stu-id="64360-107">Be sure to use parameters as specified in the following procedure.</span></span> <span data-ttu-id="64360-108">Сведения о том, как работают командлеты на этапе перехода на другой ресурс, приведены в статье сведения о переходе на веб – странице [http://go.microsoft.com/fwlink/p/?LinkId=263957](http://go.microsoft.com/fwlink/p/?linkid=263957)блога "Lync Server 2013: восстановление групп ответов во время аварийного восстановления"</span><span class="sxs-lookup"><span data-stu-id="64360-108">For details about how cmdlets work during the failover phase, see NextHop blog article "Lync Server 2013: Recovering Response Groups During Disaster Recovery" at [http://go.microsoft.com/fwlink/p/?LinkId=263957](http://go.microsoft.com/fwlink/p/?linkid=263957).</span></span> <span data-ttu-id="64360-109">Эта статья в блоге также относится к выпущенной версии Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="64360-109">This blog article also applies to the released version of Lync Server 2013.</span></span>

<span data-ttu-id="64360-110">Выполните действия, описанные в приведенной ниже процедуре, для подготовки и выполнения аварийного восстановления для службы группы ответа Lync Server.</span><span class="sxs-lookup"><span data-stu-id="64360-110">Use the steps in the following procedure to prepare for and perform disaster recovery for Lync Server Response Group service.</span></span>

<div>

## <a name="to-fail-over-and-fail-back-response-group"></a><span data-ttu-id="64360-111">Группа ответа для отработки отказа и отката</span><span class="sxs-lookup"><span data-stu-id="64360-111">To fail over and fail back Response Group</span></span>

1.  <span data-ttu-id="64360-112">Запустите командную консоль Lync Server Management Shell: нажмите кнопку **Пуск**, выберите **все программы**, а затем — **Microsoft Lync Server 2013**, а затем — **Командная консоль Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="64360-112">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="64360-113">Регулярное выполнение резервного копирования.</span><span class="sxs-lookup"><span data-stu-id="64360-113">Routinely perform backups.</span></span> <span data-ttu-id="64360-114">В командной строке введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="64360-114">At the command line, type:</span></span>
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<primary pool FQDN>" -FileName "<backup path and file name>"
    
    <span data-ttu-id="64360-115">Например:</span><span class="sxs-lookup"><span data-stu-id="64360-115">For example:</span></span>
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:primary.contoso.com" -FileName "C:\RgsExportPrimary.zip"

3.  <span data-ttu-id="64360-116">Во время сбоя после перехода на другой ресурс в пул резервной копии импортируйте группы ответа в пул резервных копий.</span><span class="sxs-lookup"><span data-stu-id="64360-116">During an outage, after failover to the backup pool, import the response groups to the backup pool.</span></span> <span data-ttu-id="64360-117">В командной строке выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="64360-117">At the command line, type:</span></span>
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:<backup pool FQDN>" -FileName "<backup path and file name>"
    
    <span data-ttu-id="64360-118">Если вы хотите заменить параметры уровня приложения в пуле резервных копий параметрами из основного пула, добавьте параметр – Реплацеексистингсеттингс.</span><span class="sxs-lookup"><span data-stu-id="64360-118">If you want to replace the application-level settings in the backup pool with the settings from the primary pool, include the –ReplaceExistingSettings parameter.</span></span> <span data-ttu-id="64360-119">Например:</span><span class="sxs-lookup"><span data-stu-id="64360-119">For example:</span></span>
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:backup.contoso.com" -FileName "C:\RgsExportPrimary.zip" -ReplaceExistingSettings
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="64360-120">Если вы не заменили параметры в пуле резервных копий и не сможете восстановить основной пул, настройки основного пула будут потеряны.</span><span class="sxs-lookup"><span data-stu-id="64360-120">If you do not replace the settings in the backup pool and the primary pool can't be recovered, the primary pool settings will be lost.</span></span> <span data-ttu-id="64360-121">Подробные сведения можно найти <A href="lync-server-2013-planning-for-response-group-disaster-recovery.md">в разделе Планирование аварийного восстановления групп ответов в Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="64360-121">For details, see <A href="lync-server-2013-planning-for-response-group-disaster-recovery.md">Planning for response group disaster recovery in Lync Server 2013</A>.</span></span>

    
    </div>

4.  <span data-ttu-id="64360-122">Убедитесь, что импорт прошел успешно, отображая импортированные группы ответа.</span><span class="sxs-lookup"><span data-stu-id="64360-122">Verify that the import was successful by displaying the imported response groups.</span></span> <span data-ttu-id="64360-123">Импортированные группы ответов по-прежнему принадлежат основным пулам.</span><span class="sxs-lookup"><span data-stu-id="64360-123">The imported response groups are still owned by the primary pool.</span></span> <span data-ttu-id="64360-124">Выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="64360-124">Do the following:</span></span>
    
      - <span data-ttu-id="64360-125">Отобразите все рабочие процессы в пуле резервных копий, которым владеет основной пул, и убедитесь, что все основные рабочие процессы пула включены.</span><span class="sxs-lookup"><span data-stu-id="64360-125">Display all the workflows in the backup pool that are owned by the primary pool, and verify that all the primary pool workflows are included.</span></span> <span data-ttu-id="64360-126">В командной строке введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="64360-126">At the command line, type:</span></span>
        
            Get-CsRgsWorkflow -Identity "service:ApplicationServer:<backup pool FQDN>" -Owner "service:ApplicationServer"<primary pool FQDN>
        
        <span data-ttu-id="64360-127">Например:</span><span class="sxs-lookup"><span data-stu-id="64360-127">For example:</span></span>
        
            Get-CsRgsWorkflow -Identity "service:ApplicationServer:backup.contoso.com" -Owner "service:ApplicationServer:primary.contoso.com"
    
      - <span data-ttu-id="64360-128">Отобразите все очереди в пуле резервных копий, владельцем которых является основной пул, и убедитесь, что все очереди основного пула включены.</span><span class="sxs-lookup"><span data-stu-id="64360-128">Display all the queues in the backup pool that are owned by the primary pool, and verify that all the primary pool queues are included.</span></span> <span data-ttu-id="64360-129">В командной строке введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="64360-129">At the command line, type:</span></span>
        
            Get-CsRgsQueue -Identity "service:ApplicationServer:<backup pool FQDN>" -Owner "service:ApplicationServer"<primary pool FQDN>
        
        <span data-ttu-id="64360-130">Например:</span><span class="sxs-lookup"><span data-stu-id="64360-130">For example:</span></span>
        
            Get-CsRgsQueue -Identity "service:ApplicationServer:backup.contoso.com" -Owner "service:ApplicationServer"primary.contoso.com"
    
      - <span data-ttu-id="64360-131">Отобразить все группы агентов в пуле резервных копий, владельцем которых является основной пул, и убедиться в том, что все группы агентов основного пула включены.</span><span class="sxs-lookup"><span data-stu-id="64360-131">Display all the agent groups in the backup pool that are owned by the primary pool, and verify that all the primary pool agent groups are included.</span></span> <span data-ttu-id="64360-132">В командной строке введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="64360-132">At the command line, type:</span></span>
        
            Get-CsRgsAgentGroup -Identity "service:ApplicationServer:<backup pool FQDN>" -Owner "service:ApplicationServer"<primary pool FQDN>
        
        <span data-ttu-id="64360-133">Например:</span><span class="sxs-lookup"><span data-stu-id="64360-133">For example:</span></span>
        
            Get-CsRgsAgentGroup -Identity "service:ApplicationServer:backup.contoso.com" -Owner "service:ApplicationServer"primary.contoso.com"
    
      - <span data-ttu-id="64360-134">Отображение всех рабочих часов в пуле резервных копий, принадлежащих основным пулам, и проверка того, что все основные часы бизнеса включены в бизнес-пул.</span><span class="sxs-lookup"><span data-stu-id="64360-134">Display all the hours of business in the backup pool that are owned by the primary pool, and verify that all the primary pool hours of business are included.</span></span> <span data-ttu-id="64360-135">В командной строке введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="64360-135">At the command line, type:</span></span>
        
            Get-CsRgsHoursOfBusiness -Identity "service:ApplicationServer:<backup pool FQDN>" -Owner "service:ApplicationServer"<primary pool FQDN>
        
        <span data-ttu-id="64360-136">Например:</span><span class="sxs-lookup"><span data-stu-id="64360-136">For example:</span></span>
        
            Get-CsRgsHoursOfBusiness -Identity "service:ApplicationServer:backup.contoso.com" -Owner "service:ApplicationServer"primary.contoso.com"
    
      - <span data-ttu-id="64360-137">Отобразить все наборы праздников в пуле резервных копий, владельцем которых является основной пул, и убедиться, что все наборы праздников основного пула включены.</span><span class="sxs-lookup"><span data-stu-id="64360-137">Display all the holiday sets in the backup pool that are owned by the primary pool, and verify that all the primary pool holiday sets are included.</span></span> <span data-ttu-id="64360-138">В командной строке введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="64360-138">At the command line, type:</span></span>
        
            Get-CsRgsHolidaySet -Identity "service:ApplicationServer:<backup pool FQDN>" -Owner "service:ApplicationServer"<primary pool FQDN>
        
        <span data-ttu-id="64360-139">Например:</span><span class="sxs-lookup"><span data-stu-id="64360-139">For example:</span></span>
        
            Get-CsRgsHolidaySet -Identity "service:ApplicationServer:backup.contoso.com" -Owner "service:ApplicationServer"primary.contoso.com"
    
    <span data-ttu-id="64360-140">Кроме того, вы можете отобразить все группы ответов в пуле резервных копий, в том числе владельцами основного пула и владельцами из пула резервных копий с помощью параметра – Шовалл вместо параметра – owner.</span><span class="sxs-lookup"><span data-stu-id="64360-140">Alternatively, you can display all the response groups in the backup pool, including the ones owned by the primary pool and the ones owned by the backup pool by using the –ShowAll parameter instead of the –Owner parameter.</span></span> <span data-ttu-id="64360-141">Например:</span><span class="sxs-lookup"><span data-stu-id="64360-141">For example:</span></span>
    
        Get-CsRgsWorkflow -Identity "service:ApplicationServer:<backup pool FQDN>" -ShowAll
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="64360-142">Необходимо использовать либо параметр – Шовалл, либо параметр – owner.</span><span class="sxs-lookup"><span data-stu-id="64360-142">You must use either the –ShowAll parameter or the –Owner parameter.</span></span> <span data-ttu-id="64360-143">Если вы не используете ни один из этих параметров, группы ответа, импортированные в пул резервных копий, не будут указаны в результатах, возвращенных командлетами.</span><span class="sxs-lookup"><span data-stu-id="64360-143">If you do not use either of these parameters, the response groups that you imported to the backup pool will not be listed in the results returned by the cmdlets.</span></span>

    
    </div>

5.  <span data-ttu-id="64360-144">Убедитесь, что импорт выполнен успешно, поместив вызов в импортированную группу ответа и подтверждаю, что вызов обрабатывается правильно.</span><span class="sxs-lookup"><span data-stu-id="64360-144">Verify that the import was successful by placing a call to an imported response group and verifying that the call is handled correctly.</span></span>

6.  <span data-ttu-id="64360-145">Агенты запросов, являющиеся членами формальных групп агента, для входа в группы агента в пуле резервного копирования.</span><span class="sxs-lookup"><span data-stu-id="64360-145">Request agents who are members of formal agent groups to sign in to their agent groups in the backup pool.</span></span>

7.  <span data-ttu-id="64360-146">Управление импортированными группами ответа и их изменение в обычном режиме.</span><span class="sxs-lookup"><span data-stu-id="64360-146">Manage and modify the imported response groups as usual.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="64360-147">Группы ответа находятся в пуле резервных копий, поэтому для управления ими вы должны использовать командную консоль Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="64360-147">While the response groups are in the backup pool, you need to use Lync Server Management Shell to manage them.</span></span> <span data-ttu-id="64360-148">Вы не можете использовать панель управления Lync Server для управления группами ответа, которые вы импортировали в пул резервных копий.</span><span class="sxs-lookup"><span data-stu-id="64360-148">You cannot use Lync Server Control Panel to manage the response groups that you imported to the backup pool.</span></span>

    
    </div>

8.  <span data-ttu-id="64360-149">После восстановления основного пула и завершения восстановления, экспортируйте группы ответов основного пула, которые были импортированы в пул резервных копий.</span><span class="sxs-lookup"><span data-stu-id="64360-149">After the primary pool is restored and failback is complete, export the primary pool response groups that were imported to the backup pool.</span></span> <span data-ttu-id="64360-150">В командной строке выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="64360-150">At the command line, type:</span></span>
    
        Export-CsRgsConfiguration -Source ApplicationServer:<backup pool FQDN> -Owner ApplicationServer:<primary pool FQDN> -FileName "<backup path and file name>"

9.  <span data-ttu-id="64360-151">Импортируйте группы ответа обратно в основной пул.</span><span class="sxs-lookup"><span data-stu-id="64360-151">Import the response groups back to the primary pool.</span></span> <span data-ttu-id="64360-152">В командной строке введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="64360-152">At the command line, type:</span></span>
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:<primary pool FQDN>" -OverwriteOwner -FileName "<exported path and file name>"
    
    <span data-ttu-id="64360-153">Например:</span><span class="sxs-lookup"><span data-stu-id="64360-153">For example:</span></span>
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:primary.contoso.com" -OverwriteOwner -FileName "C:\RgsExportPrimaryUpdated.zip"
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="64360-154">Если вы перестраиваете пул во время восстановления, независимо от того, есть ли у него другое полное доменное имя (FQDN), необходимо использовать параметр – Овервритеовнер.</span><span class="sxs-lookup"><span data-stu-id="64360-154">If you rebuild a pool during recovery, whether with the same or a different fully qualified domain name (FQDN), you need to use the –OverwriteOwner parameter.</span></span> <span data-ttu-id="64360-155">Как правило, вы всегда можете использовать параметр – Овервритеовнер при импорте групп ответа обратно в основной пул.</span><span class="sxs-lookup"><span data-stu-id="64360-155">As a rule of thumb, you can always use the –OverwriteOwner parameter when you import response groups back to the primary pool.</span></span>

    
    </div>
    
    <span data-ttu-id="64360-156">Если вы развернули новый пул (с таким же или другим полным доменным именем) для замены основного пула и хотите использовать параметры уровня приложения из пула резервного копирования для нового пула, добавьте параметр – Реплацеексистингсеттингс.</span><span class="sxs-lookup"><span data-stu-id="64360-156">If you deployed a new pool (with the same or a different FQDN) to replace the primary pool, and you want to use the application-level settings from the backup pool for the new pool, include the –ReplaceExistingSettings parameter.</span></span> <span data-ttu-id="64360-157">В командной строке введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="64360-157">At the command line, type:</span></span>
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:<new primary pool FQDN>" -OverwriteOwner -FileName "<exported path and file name>" -ReplaceExistingSettings
    
    <span data-ttu-id="64360-158">Например:</span><span class="sxs-lookup"><span data-stu-id="64360-158">For example:</span></span>
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:newprimary.contoso.com" -OverwriteOwner -FileName "C:\RgsExportPrimaryUpdated.zip" -ReplaceExistingSettings
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="64360-159">Если вы не хотите заменять параметры уровня приложения и звуковой файл для хранения музыки по умолчанию для нового пула с параметрами из пула резервных копий, в новом пуле будут использоваться параметры по умолчанию на уровне приложения.</span><span class="sxs-lookup"><span data-stu-id="64360-159">If you don't want to replace the application-level settings and default music-on-hold audio file for the new pool with the settings from the backup pool, the new pool will use the default application-level settings.</span></span>

    
    </div>

10. <span data-ttu-id="64360-160">Убедитесь, что импорт возвращен в основной пул, отображая импортированную конфигурацию группы ответа.</span><span class="sxs-lookup"><span data-stu-id="64360-160">Verify that the import back to the primary pool was successful by displaying the imported response group configuration.</span></span> <span data-ttu-id="64360-161">Выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="64360-161">Do the following:</span></span>
    
      - <span data-ttu-id="64360-162">Отобразите все рабочие процессы в основном пуле и убедитесь, что все импортированные рабочие процессы включены.</span><span class="sxs-lookup"><span data-stu-id="64360-162">Display all the workflows in the primary pool, and verify that all the imported workflows are included.</span></span> <span data-ttu-id="64360-163">В командной строке введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="64360-163">At the command line, type:</span></span>
        
            Get-CsRgsWorkflow -Identity "service:ApplicationServer:<primary pool FQDN>" -ShowAll
        
        <span data-ttu-id="64360-164">Например:</span><span class="sxs-lookup"><span data-stu-id="64360-164">For example:</span></span>
        
            Get-CsRgsWorkflow -Identity "service:ApplicationServer: primary.contoso.com" -ShowAll
    
      - <span data-ttu-id="64360-165">Отобразите все очереди в основном пуле и убедитесь, что все импортированные очереди включены.</span><span class="sxs-lookup"><span data-stu-id="64360-165">Display all the queues in the primary pool, and verify that all the imported queues are included.</span></span> <span data-ttu-id="64360-166">В командной строке введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="64360-166">At the command line, type:</span></span>
        
            Get-CsRgsQueue -Identity "service:ApplicationServer:<primary pool FQDN>" -ShowAll
        
        <span data-ttu-id="64360-167">Например:</span><span class="sxs-lookup"><span data-stu-id="64360-167">For example:</span></span>
        
            Get-CsRgsQueue -Identity "service:ApplicationServer:primary.contoso.com" -ShowAll
    
      - <span data-ttu-id="64360-168">Отобразить все группы агентов в основном пуле и убедиться, что все импортированные группы агентов включены.</span><span class="sxs-lookup"><span data-stu-id="64360-168">Display all the agent groups in the primary pool, and verify that all the imported agent groups are included.</span></span> <span data-ttu-id="64360-169">В командной строке введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="64360-169">At the command line, type:</span></span>
        
            Get-CsRgsAgentGroup -Identity "service:ApplicationServer: <primary pool FQDN>" -ShowAll
        
        <span data-ttu-id="64360-170">Например:</span><span class="sxs-lookup"><span data-stu-id="64360-170">For example:</span></span>
        
            Get-CsRgsAgentGroup -Identity "service:ApplicationServer:primary.contoso.com" -ShowAll
    
      - <span data-ttu-id="64360-171">Отображение всех рабочих часов в основном пуле и проверка того, что все импортированные часы бизнеса включены.</span><span class="sxs-lookup"><span data-stu-id="64360-171">Display all the hours of business in the primary pool, and verify that all the imported hours of business are included.</span></span> <span data-ttu-id="64360-172">В командной строке введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="64360-172">At the command line, type:</span></span>
        
            Get-CsRgsHoursOfBusiness -Identity "service:ApplicationServer:<primary pool FQDN>" -ShowAll
        
        <span data-ttu-id="64360-173">Например:</span><span class="sxs-lookup"><span data-stu-id="64360-173">For example:</span></span>
        
            Get-CsRgsHoursOfBusiness -Identity "service:ApplicationServer:primary.contoso.com" -ShowAll
    
      - <span data-ttu-id="64360-174">Отобразите все наборы праздников в основном пуле и убедитесь, что все импортированные наборы праздников включены.</span><span class="sxs-lookup"><span data-stu-id="64360-174">Display all the holiday sets in the primary pool, and verify that all the imported holiday sets are included.</span></span> <span data-ttu-id="64360-175">В командной строке введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="64360-175">At the command line, type:</span></span>
        
            Get-CsRgsHolidaySet -Identity "service:ApplicationServer:<primary pool FQDN>" -ShowAll
        
        <span data-ttu-id="64360-176">Например:</span><span class="sxs-lookup"><span data-stu-id="64360-176">For example:</span></span>
        
            Get-CsRgsHolidaySet -Identity "service:ApplicationServer:primary.contoso.com" -ShowAll

11. <span data-ttu-id="64360-177">Убедитесь, что импорт выполнен успешно, поместив вызов в импортированную группу ответа и подтверждаю, что вызов обрабатывается правильно.</span><span class="sxs-lookup"><span data-stu-id="64360-177">Verify that the import was successful by placing a call to an imported response group and verifying that the call is handled correctly.</span></span>

12. <span data-ttu-id="64360-178">При необходимости удалите группы ответа, принадлежащие основным пулам из пула резервных копий.</span><span class="sxs-lookup"><span data-stu-id="64360-178">Optionally, remove the response groups owned by the primary pool from the backup pool.</span></span> <span data-ttu-id="64360-179">В командной строке введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="64360-179">At the command line, type:</span></span>
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<backup pool FQDN>" -Owner "service:ApplicationServer:<primary pool FQDN>" -FileName "<backup path and file name>" -RemoveExportedConfiguration
    
    <span data-ttu-id="64360-180">Например:</span><span class="sxs-lookup"><span data-stu-id="64360-180">For example:</span></span>
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:backup.contoso.com" -Owner "service:ApplicationServer:primary.contoso.com" -FileName "C:\RgsExportPrimaryUpdated.zip" -RemoveExportedConfiguration
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="64360-181">На этом этапе создается новый файл с экспортированной конфигурацией, а затем он удаляется из пула резервных копий.</span><span class="sxs-lookup"><span data-stu-id="64360-181">This step creates a new file with the exported configuration, and then removes it from the backup pool.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

