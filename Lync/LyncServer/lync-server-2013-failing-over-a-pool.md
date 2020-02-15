---
title: 'Lync Server 2013: отработка отказа для пула'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Failing over a pool
ms:assetid: 10b13732-bc80-4cb2-a71c-56b1d6cb5bbb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204678(v=OCS.15)
ms:contentKeyID: 48183432
ms.date: 10/10/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7de00de8361ac8bc5827fd76ea2486ae790a66d4
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42048022"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="failing-over-a-pool-in-lync-server-2013"></a><span data-ttu-id="e3685-102">Отработка отказа для пула в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e3685-102">Failing over a pool in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e3685-103">_**Последнее изменение темы:** 2014-10-10_</span><span class="sxs-lookup"><span data-stu-id="e3685-103">_**Topic Last Modified:** 2014-10-10_</span></span>

<span data-ttu-id="e3685-p101">Если отказал одиночный клиентский пул и его требуется обойти, используйте следующую процедуру. В этой процедуре Datacenter1 содержит Pool1, и произошел отказ Pool1. Выполняется обход отказавшего пула к пулу Pool2, находящемуся в Datacenter2.</span><span class="sxs-lookup"><span data-stu-id="e3685-p101">If a single Front End pool has failed and needs to be failed over, use the following procedure. In this procedure, Datacenter1 contains Pool1, and Pool1 has failed. You are failing over to Pool2 located in Datacenter2.</span></span>

<span data-ttu-id="e3685-107">Большая часть работы для отработки отказа пула включает отработку отказа центрального хранилища управления, если это необходимо.</span><span class="sxs-lookup"><span data-stu-id="e3685-107">Most of the work for the pool failover involves failing over the Central Management store, if it is required.</span></span> <span data-ttu-id="e3685-108">Это важно, так как центральное хранилище управления должно быть работоспособным при отработки отказа для пользователей пула.</span><span class="sxs-lookup"><span data-stu-id="e3685-108">This is important because the Central Management store must be functional when the pool’s users are failed over.</span></span>

<span data-ttu-id="e3685-p103">Кроме того, если возник отказ клиентского пула, но пограничный пул на этом сайте по-прежнему работает, необходимо знать, используется ли пограничным пулом отказавший пул в качестве следующего перехода по пулам. Если используется, следует изменить пограничный пул, чтобы он использовал другой клиентский пул до обхода отказавшего клиентского пула. Порядок изменения настройки следующего перехода по пулам зависит от того, будет ли пограничный пул использовать пул на том же сайте, на котором находится пограничный пул, или на другом сайте.</span><span class="sxs-lookup"><span data-stu-id="e3685-p103">Additionally, if a Front End pool fails but the Edge pool at that site is still running, you must know whether the Edge pool uses the failed pool as a next hop pool. If it does, you must change the Edge pool to use a different Front End pool before failing over the failed Front End pool. How you change the next hop setting depends on whether the Edge will use a pool at the same site as the Edge pool, or a different site.</span></span>

<span data-ttu-id="e3685-112">**Чтобы установить пограничный пул на использование пула следующего перехода на том же сайте**</span><span class="sxs-lookup"><span data-stu-id="e3685-112">**To Set an Edge Pool to Use a Next Hop Pool at the Same Site**</span></span>

1.  <span data-ttu-id="e3685-113">Откройте построитель топологий, щелкните правой кнопкой мыши пограничный пул, который необходимо изменить, и выберите команду **изменить свойства**.</span><span class="sxs-lookup"><span data-stu-id="e3685-113">Open Topology Builder, right-click the Edge pool that needs to be changed, and click **Edit Properties**.</span></span>

2.  <span data-ttu-id="e3685-p104">Щелкните **Следующий переход**. В списке **Пул следующего перехода:** выберите пул, который сейчас служит в качестве пула следующего перехода.</span><span class="sxs-lookup"><span data-stu-id="e3685-p104">Click **Next Hop**. From the **Next hop pool:** list, select the pool which will now serve as the next hop pool.</span></span>

3.  <span data-ttu-id="e3685-116">Нажмите кнопку **ОК**, а затем опубликуйте изменения.</span><span class="sxs-lookup"><span data-stu-id="e3685-116">Click **OK**, and then publish the changes.</span></span>

<span data-ttu-id="e3685-117">**Чтобы установить пограничный пул на использование пула следующего перехода на другом сайте**</span><span class="sxs-lookup"><span data-stu-id="e3685-117">**To Set an Edge Pool to Use a Next Hop Pool at a Different Site**</span></span>

1.  <span data-ttu-id="e3685-118">Откройте окно командной консоли Lync Server и введите следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="e3685-118">Open a Lync Server Management Shell window and type the following cmdlet:</span></span>
    
        Set-CsEdgeServer -Identity EdgeServer:<Edge Server pool FQDN> -Registrar Registrar:<NextHopPoolFQDN>

<span data-ttu-id="e3685-119">**Чтобы обойти пул, находящийся в аварийном состоянии**</span><span class="sxs-lookup"><span data-stu-id="e3685-119">**To Fail Over a Pool in a Disaster**</span></span>

1.  <span data-ttu-id="e3685-120">Чтобы определить, какой пул является узлом для центрального сервера управления, введите следующий командлет на сервере переднего плана в Pool2:</span><span class="sxs-lookup"><span data-stu-id="e3685-120">Find which pool is the host for the Central Management Server by typing the following cmdlet on a Front End server in Pool2:</span></span>
    
        Invoke-CsManagementServerFailover -Whatif
    
    <span data-ttu-id="e3685-121">Результаты этого командлета покажут, какой пул в настоящее время содержит центральный сервер управления.</span><span class="sxs-lookup"><span data-stu-id="e3685-121">The results of this cmdlet show which pool currently hosts the Central Management Server.</span></span> <span data-ttu-id="e3685-122">В оставшейся части этой процедуры этот пул называется пулом CMS\_.</span><span class="sxs-lookup"><span data-stu-id="e3685-122">In the rest of this procedure, this pool is known as CMS\_Pool.</span></span>

2.  <span data-ttu-id="e3685-123">Используйте построитель топологий, чтобы найти версию Lync Server, работающую\_на пуле CMS.</span><span class="sxs-lookup"><span data-stu-id="e3685-123">Use Topology Builder to find the version of Lync Server running on the CMS\_Pool.</span></span> <span data-ttu-id="e3685-124">Если на нем работает Lync Server 2013, используйте следующий командлет, чтобы найти резервный пул пула 1.</span><span class="sxs-lookup"><span data-stu-id="e3685-124">If it is running Lync Server 2013, use the following cmdlet to find the backup pool of Pool 1.</span></span>
    
        Get-CsPoolBackupRelationship -PoolFQDN <CMS_Pool FQDN>
    
    <span data-ttu-id="e3685-125">Подайте\_резервный пул в резервный пул.</span><span class="sxs-lookup"><span data-stu-id="e3685-125">Let Backup\_Pool be the backup pool.</span></span>

3.  <span data-ttu-id="e3685-126">Проверьте состояние центрального хранилища управления с помощью следующего командлета:</span><span class="sxs-lookup"><span data-stu-id="e3685-126">Check the status of the Central Management store with the following cmdlet:</span></span>
    
        Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
    
    <span data-ttu-id="e3685-127">Этот командлет показывает, что Активемастерфкдн и Активефилетрансферажентс указывают на полное доменное имя пула CMS\_.</span><span class="sxs-lookup"><span data-stu-id="e3685-127">This cmdlet should show that both ActiveMasterFQDN and ActiveFileTransferAgents are pointing to the FQDN of CMS\_Pool.</span></span> <span data-ttu-id="e3685-128">Если они пусты, центральный сервер управления недоступен и его необходимо отработать.</span><span class="sxs-lookup"><span data-stu-id="e3685-128">If they are empty, the Central Management Server is not available and you must fail it over.</span></span>

4.  <span data-ttu-id="e3685-129">Если центральное хранилище управления недоступно или если центральное хранилище управления было запущено в Pool1 (то есть при сбое пула), перед отработкой отказа пула необходимо выполнить отработку отказа на центральном сервере управления.</span><span class="sxs-lookup"><span data-stu-id="e3685-129">If the Central Management store is not available or if the Central Management store was running on Pool1 (that is, the pool that has failed), you must fail over the Central Management Server before failing over the pool.</span></span> <span data-ttu-id="e3685-130">Если необходимо отработка отказа для центрального сервера управления, размещенного в пуле, где запущен Lync Server 2013, используйте командлет, описанный в шаге 5 этой процедуры.</span><span class="sxs-lookup"><span data-stu-id="e3685-130">If you need to fail over the Central Management Server that was hosted on a pool running Lync Server 2013, use the cmdlet in step 5 of this procedure.</span></span> <span data-ttu-id="e3685-131">Если необходимо отработка отказа на центральном сервере управления, размещенном в пуле, где работает Lync Server 2010, используйте командлет, описанный в шаге 6 этой процедуры.</span><span class="sxs-lookup"><span data-stu-id="e3685-131">If you need to fail over the Central Management Server that was hosted on a pool running Lync Server 2010, use the cmdlet in step 6 of this procedure.</span></span> <span data-ttu-id="e3685-132">Если не требуется отработка отказа для центрального сервера управления, перейдите к шагу 7 этой процедуры.</span><span class="sxs-lookup"><span data-stu-id="e3685-132">If you do not need to fail over the Central Management Server, skip to step 7 of this procedure.</span></span>

5.  <span data-ttu-id="e3685-133">Чтобы отработка отказа центрального хранилища управления в пуле, работающем под управлением Lync Server 2013, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="e3685-133">To fail over the Central Management store on a pool running Lync Server 2013, do the following:</span></span>
    
      - <span data-ttu-id="e3685-134">Сначала проверьте, какой внутренний сервер в резервном\_пуле выполняет основной экземпляр центрального хранилища управления, введя следующую команду:</span><span class="sxs-lookup"><span data-stu-id="e3685-134">First, check which Back End Server in Backup\_Pool runs the principal instance of the Central Management store by typing the following:</span></span>
        
            Get-CsDatabaseMirrorState -DatabaseType Centralmgmt -PoolFqdn <Backup_Pool Fqdn>
    
      - <span data-ttu-id="e3685-135">Если основной сервер переднего план в резервном\_пуле является основным, введите:</span><span class="sxs-lookup"><span data-stu-id="e3685-135">If the primary Back End Server in Backup\_Pool is the principal, type:</span></span>
        
            Invoke-CSManagementServerFailover -BackupSQLServerFqdn <Backup_Pool Primary BackEnd Server FQDN> -BackupSQLInstanceName <Backup_Pool Primary SQL Instance Name>
        
        <span data-ttu-id="e3685-136">Если зеркальный сервер переднего план в\_резервном пуле является основным, введите:</span><span class="sxs-lookup"><span data-stu-id="e3685-136">If the mirror Back End Server in Backup\_Pool is the principal, type:</span></span>
        
            Invoke-CSManagementServerFailover -MirrorSQLServerFqdn <Backup_Pool Mirror BackEnd Server FQDN> -MirrorSQLInstanceName <Backup_Pool Mirror SQL Instance Name>
    
      - <span data-ttu-id="e3685-137">Убедитесь, что отработка отказа для центрального сервера управления завершена.</span><span class="sxs-lookup"><span data-stu-id="e3685-137">Validate that the Central Management Server failover is complete.</span></span> <span data-ttu-id="e3685-138">Введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="e3685-138">Type the following:</span></span>
        
            Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
        
        <span data-ttu-id="e3685-139">Убедитесь, что оба Активемастерфкдн и Активефилетрансферажентс указывают на полное доменное имя\_резервного пула.</span><span class="sxs-lookup"><span data-stu-id="e3685-139">Check that both ActiveMasterFQDN and ActiveFileTransferAgents are pointing to the FQDN of Backup\_Pool.</span></span>
    
      - <span data-ttu-id="e3685-140">Наконец, проверьте состояние реплики для всех серверов переднего плана, введя следующую команду:</span><span class="sxs-lookup"><span data-stu-id="e3685-140">Finally, check the replica status for all Front End Servers by typing the following:</span></span>
        
            Get-CsManagementStoreReplicationStatus 
        
        <span data-ttu-id="e3685-141">Проверьте, все ли реплики имеют значение True.</span><span class="sxs-lookup"><span data-stu-id="e3685-141">Check that all replicas have a value of True.</span></span>
        
        <span data-ttu-id="e3685-142">Перейдите к действию 7 этой процедуры.</span><span class="sxs-lookup"><span data-stu-id="e3685-142">Skip to step 7 in this procedure.</span></span>

6.  <span data-ttu-id="e3685-143">Установите центральное хранилище управления на внутреннем сервере пула резервного копирования\_.</span><span class="sxs-lookup"><span data-stu-id="e3685-143">Install the Central Management store on the Back End Server of Backup\_Pool.</span></span>
    
      - <span data-ttu-id="e3685-144">Сначала выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="e3685-144">First, run the following command:</span></span>
        
        ```PowerShell 
        Install-CsDatabase -CentralManagementDatabase -Clean -SqlServerFqdn <Backup_Pool Back End Server FQDN> -SqlInstanceName rtc  
        ```
    
      - <span data-ttu-id="e3685-145">Выполните следующую команду на одном из серверов переднего плана резервного\_пула для принудительного перемещения центрального хранилища управления:</span><span class="sxs-lookup"><span data-stu-id="e3685-145">Run the next command on one of the Front End Servers of Backup\_Pool to force the move of the Central Management store:</span></span>
        
            Move-CsManagementServer -ConfigurationFileName c:\CsConfigurationFile.zip -LisConfigurationFileName c:\CsLisConfigurationFile.zip -Force 
    
      - <span data-ttu-id="e3685-146">Проверьте, выполнилось ли перемещение.</span><span class="sxs-lookup"><span data-stu-id="e3685-146">Validate the move is complete:</span></span>
        
            Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
        
        <span data-ttu-id="e3685-147">Убедитесь, что оба Активемастерфкдн и Активефилетрансферажентс указывают на полное доменное имя\_резервного пула.</span><span class="sxs-lookup"><span data-stu-id="e3685-147">Check that both ActiveMasterFQDN and ActiveFileTransferAgents are pointing to the FQDN of Backup\_Pool.</span></span>
    
      - <span data-ttu-id="e3685-148">Проверьте состояние реплики для всех серверов переднего плана, введя следующую команду:</span><span class="sxs-lookup"><span data-stu-id="e3685-148">Check the replica status for all Front End Servers by typing the following:</span></span>
        
            Get-CsManagementStoreReplicationStatus 
        
        <span data-ttu-id="e3685-149">Проверьте, все ли реплики имеют значение True.</span><span class="sxs-lookup"><span data-stu-id="e3685-149">Check that all replicas have a value of True.</span></span>
    
      - <span data-ttu-id="e3685-150">Установите службу центрального сервера управления на остальные серверы переднего плана в резервном\_пуле.</span><span class="sxs-lookup"><span data-stu-id="e3685-150">Install the Central Management Server service on the rest of the Front End Servers in Backup\_Pool.</span></span> <span data-ttu-id="e3685-151">Для этого выполните приведенную ниже команду на всех серверах переднего плана, Кроме того, который вы использовали при форсированном перемещении центрального хранилища управления в этой процедуре.</span><span class="sxs-lookup"><span data-stu-id="e3685-151">To do so, run the following command on all the Front End Servers, except the one you used when forcing the Central Management store move earlier in this procedure:</span></span>
        
            Bootstrapper /Setup 

7.  <span data-ttu-id="e3685-152">Выполните отработку отказа для пользователей из Pool1 в Pool2, выполнив следующий командлет в окне командной консоли Lync Server:</span><span class="sxs-lookup"><span data-stu-id="e3685-152">Fail over the users from Pool1 to Pool2 by running the following cmdlet in a Lync Server Management Shell window:</span></span>
    
        Invoke-CsPoolFailover -PoolFQDN <Pool1 FQDN> -DisasterMode -Verbose
    
    <span data-ttu-id="e3685-153">Так как действия, описанные в предыдущих процедурах этой процедуры, для проверки состояния центрального хранилища управления не являются универсальными, существует шанс сбоя этого командлета, так как центральное хранилище управления пока не проходит полную отработку отказа.</span><span class="sxs-lookup"><span data-stu-id="e3685-153">Because the steps taken in the previous parts of this procedure to check the Central Management store status are not universal, there is still a chance this cmdlet will fail because the Central Management store is not yet fully failed over.</span></span> <span data-ttu-id="e3685-154">В этом случае необходимо исправить центральное хранилище управления на основе сообщений об ошибках, которые вы видите, а затем снова запустить этот командлет.</span><span class="sxs-lookup"><span data-stu-id="e3685-154">In this case, you must fix the Central Management store based on the error messages that you see, and then run this cmdlet again.</span></span>
    
    <span data-ttu-id="e3685-p112">Если выводится приводимое ниже сообщение об ошибке, необходимо изменить пограничный пул на данном сайте, чтобы использовать до обхода отказавшего пула другой пул в качестве следующего перехода. Подробности см. в описании процедур в начале этой статьи.</span><span class="sxs-lookup"><span data-stu-id="e3685-p112">If you see the following error message, then you need to change the Edge pool at this site to use a different pool as its next hop before failing over the pool. For details, see the procedures at the beginning of this topic.</span></span>
    
        Invoke-CsPoolFailOver : This Front-end pool "pool1.contoso.com" is specified in
        topology as the next hop for the Edge server. Failing over this pool may cause External
        access/Federation/Split-domain/XMPP features to stop working. Please use Topology Builder to
        change the Edge internal next hop setting to point to a different Front-end pool,  before you
        proceed.

</div>

<span> </span>

</div>

</div>

</div>

