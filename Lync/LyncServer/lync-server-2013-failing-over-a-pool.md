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
ms.openlocfilehash: ea66ae4a224d78e40a9fdb9de867d4738a5e3714
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756143"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="failing-over-a-pool-in-lync-server-2013"></a><span data-ttu-id="dc7bd-102">Отработка отказа для пула в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dc7bd-102">Failing over a pool in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dc7bd-103">_**Тема последнего изменения:** 2014-10-10_</span><span class="sxs-lookup"><span data-stu-id="dc7bd-103">_**Topic Last Modified:** 2014-10-10_</span></span>

<span data-ttu-id="dc7bd-104">Если один пул переднего плана завершился сбоем, и необходимо выполнить отсоединение, выполните описанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="dc7bd-104">If a single Front End pool has failed and needs to be failed over, use the following procedure.</span></span> <span data-ttu-id="dc7bd-105">В этой процедуре Datacenter1 содержит Pool1 и Pool1 завершился сбоем.</span><span class="sxs-lookup"><span data-stu-id="dc7bd-105">In this procedure, Datacenter1 contains Pool1, and Pool1 has failed.</span></span> <span data-ttu-id="dc7bd-106">Вы не можете найти Pool2 в Datacenter2.</span><span class="sxs-lookup"><span data-stu-id="dc7bd-106">You are failing over to Pool2 located in Datacenter2.</span></span>

<span data-ttu-id="dc7bd-107">Большая часть работы для отработки отказа в пуле связана с отказом в хранилище Центрального управления, если это необходимо.</span><span class="sxs-lookup"><span data-stu-id="dc7bd-107">Most of the work for the pool failover involves failing over the Central Management store, if it is required.</span></span> <span data-ttu-id="dc7bd-108">Это важно, так как центральное хранилище управления должно быть работоспособным при сбое пользователей пула.</span><span class="sxs-lookup"><span data-stu-id="dc7bd-108">This is important because the Central Management store must be functional when the pool’s users are failed over.</span></span>

<span data-ttu-id="dc7bd-109">Кроме того, если пул переднего плана завершается сбоем, но пул EDGE на нем по-прежнему работает, необходимо знать, использует ли пул отказ в качестве следующего пула прыжков.</span><span class="sxs-lookup"><span data-stu-id="dc7bd-109">Additionally, if a Front End pool fails but the Edge pool at that site is still running, you must know whether the Edge pool uses the failed pool as a next hop pool.</span></span> <span data-ttu-id="dc7bd-110">Если это так, вы должны изменить пул EDGE, чтобы использовать другой пул переднего плана, прежде чем произойдет сбой в пуле внешних интерфейсов.</span><span class="sxs-lookup"><span data-stu-id="dc7bd-110">If it does, you must change the Edge pool to use a different Front End pool before failing over the failed Front End pool.</span></span> <span data-ttu-id="dc7bd-111">Способ изменения параметров следующего прыжка зависит от того, будет ли край использовать пул на том же сайте, что и пул EDGE, или другой сайт.</span><span class="sxs-lookup"><span data-stu-id="dc7bd-111">How you change the next hop setting depends on whether the Edge will use a pool at the same site as the Edge pool, or a different site.</span></span>

<span data-ttu-id="dc7bd-112">**Настройка пограничного пула на использование следующего пула прыжков на том же сайте**</span><span class="sxs-lookup"><span data-stu-id="dc7bd-112">**To Set an Edge Pool to Use a Next Hop Pool at the Same Site**</span></span>

1.  <span data-ttu-id="dc7bd-113">Откройте построитель топологии, щелкните правой кнопкой мыши Граничный пул, который необходимо изменить, и выберите команду **изменить свойства**.</span><span class="sxs-lookup"><span data-stu-id="dc7bd-113">Open Topology Builder, right-click the Edge pool that needs to be changed, and click **Edit Properties**.</span></span>

2.  <span data-ttu-id="dc7bd-114">Щелкните **следующий прыжок**.</span><span class="sxs-lookup"><span data-stu-id="dc7bd-114">Click **Next Hop**.</span></span> <span data-ttu-id="dc7bd-115">В списке **следующего прыжка пул:** выберите пул, который будет использоваться в качестве пула следующего прыжка.</span><span class="sxs-lookup"><span data-stu-id="dc7bd-115">From the **Next hop pool:** list, select the pool which will now serve as the next hop pool.</span></span>

3.  <span data-ttu-id="dc7bd-116">Нажмите кнопку **ОК**, а затем опубликуйте изменения.</span><span class="sxs-lookup"><span data-stu-id="dc7bd-116">Click **OK**, and then publish the changes.</span></span>

<span data-ttu-id="dc7bd-117">**Настройка пограничного пула на использование пула следующего прыжка на другом сайте**</span><span class="sxs-lookup"><span data-stu-id="dc7bd-117">**To Set an Edge Pool to Use a Next Hop Pool at a Different Site**</span></span>

1.  <span data-ttu-id="dc7bd-118">Откройте окно командной консоли Lync Server и введите следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="dc7bd-118">Open a Lync Server Management Shell window and type the following cmdlet:</span></span>
    
        Set-CsEdgeServer -Identity EdgeServer:<Edge Server pool FQDN> -Registrar Registrar:<NextHopPoolFQDN>

<span data-ttu-id="dc7bd-119">**Отказ от пула в случае аварии**</span><span class="sxs-lookup"><span data-stu-id="dc7bd-119">**To Fail Over a Pool in a Disaster**</span></span>

1.  <span data-ttu-id="dc7bd-120">Чтобы найти, какой из пулов является узлом центрального сервера управления, введите следующий командлет на сервере переднего плана в Pool2:</span><span class="sxs-lookup"><span data-stu-id="dc7bd-120">Find which pool is the host for the Central Management Server by typing the following cmdlet on a Front End server in Pool2:</span></span>
    
        Invoke-CsManagementServerFailover -Whatif
    
    <span data-ttu-id="dc7bd-121">Результаты этого командлета показывают, в каком пуле на данный момент размещен Центральный сервер управления.</span><span class="sxs-lookup"><span data-stu-id="dc7bd-121">The results of this cmdlet show which pool currently hosts the Central Management Server.</span></span> <span data-ttu-id="dc7bd-122">В оставшейся части этой процедуры этот пул называется пулом CMS\_.</span><span class="sxs-lookup"><span data-stu-id="dc7bd-122">In the rest of this procedure, this pool is known as CMS\_Pool.</span></span>

2.  <span data-ttu-id="dc7bd-123">Использование построителя топологии для поиска версии сервера Lync Server, работающей в\_пуле CMS.</span><span class="sxs-lookup"><span data-stu-id="dc7bd-123">Use Topology Builder to find the version of Lync Server running on the CMS\_Pool.</span></span> <span data-ttu-id="dc7bd-124">Если на нем работает Lync Server 2013, используйте следующий командлет, чтобы найти пул резервных копий для пула 1.</span><span class="sxs-lookup"><span data-stu-id="dc7bd-124">If it is running Lync Server 2013, use the following cmdlet to find the backup pool of Pool 1.</span></span>
    
        Get-CsPoolBackupRelationship -PoolFQDN <CMS_Pool FQDN>
    
    <span data-ttu-id="dc7bd-125">Пусть резервная копия\_пула является пулом резервных копий.</span><span class="sxs-lookup"><span data-stu-id="dc7bd-125">Let Backup\_Pool be the backup pool.</span></span>

3.  <span data-ttu-id="dc7bd-126">Проверьте состояние хранилища центрального управления с помощью следующего командлета:</span><span class="sxs-lookup"><span data-stu-id="dc7bd-126">Check the status of the Central Management store with the following cmdlet:</span></span>
    
        Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
    
    <span data-ttu-id="dc7bd-127">Этот командлет показывает, что оба Активемастерфкдн и Активефилетрансферажентс указывают на полное доменное имя пула\_CMS.</span><span class="sxs-lookup"><span data-stu-id="dc7bd-127">This cmdlet should show that both ActiveMasterFQDN and ActiveFileTransferAgents are pointing to the FQDN of CMS\_Pool.</span></span> <span data-ttu-id="dc7bd-128">Если они пусты, центральный сервер управления недоступен, и вы должны пройти его.</span><span class="sxs-lookup"><span data-stu-id="dc7bd-128">If they are empty, the Central Management Server is not available and you must fail it over.</span></span>

4.  <span data-ttu-id="dc7bd-129">Если хранилище Центрального управления недоступно или хранилище Центрального управления запущено на Pool1 (то есть в пуле, в котором произошел сбой), перед отказом в пуле необходимо выполнить переключение на центральный сервер управления.</span><span class="sxs-lookup"><span data-stu-id="dc7bd-129">If the Central Management store is not available or if the Central Management store was running on Pool1 (that is, the pool that has failed), you must fail over the Central Management Server before failing over the pool.</span></span> <span data-ttu-id="dc7bd-130">Если вам нужно отдать отказ на центральный сервер управления, размещенный в пуле, на котором работает Lync Server 2013, используйте командлет, описанный в шаге 5 этой процедуры.</span><span class="sxs-lookup"><span data-stu-id="dc7bd-130">If you need to fail over the Central Management Server that was hosted on a pool running Lync Server 2013, use the cmdlet in step 5 of this procedure.</span></span> <span data-ttu-id="dc7bd-131">Если вам нужно отдать отказ на центральный сервер управления, размещенный в пуле, на котором работает Lync Server 2010, используйте командлет, описанный в шаге 6 этой процедуры.</span><span class="sxs-lookup"><span data-stu-id="dc7bd-131">If you need to fail over the Central Management Server that was hosted on a pool running Lync Server 2010, use the cmdlet in step 6 of this procedure.</span></span> <span data-ttu-id="dc7bd-132">Если вам не нужно переключиться на центральный сервер управления, перейдите к шагу 7 этой процедуры.</span><span class="sxs-lookup"><span data-stu-id="dc7bd-132">If you do not need to fail over the Central Management Server, skip to step 7 of this procedure.</span></span>

5.  <span data-ttu-id="dc7bd-133">Чтобы отдать отказ на хранение центрального хранилища в пуле, работающем в Lync Server 2013, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="dc7bd-133">To fail over the Central Management store on a pool running Lync Server 2013, do the following:</span></span>
    
      - <span data-ttu-id="dc7bd-134">Сначала убедитесь, что сервер, на котором он\_находится в резервной копии, запускает экземпляр основного хранилища, введя следующие символы:</span><span class="sxs-lookup"><span data-stu-id="dc7bd-134">First, check which Back End Server in Backup\_Pool runs the principal instance of the Central Management store by typing the following:</span></span>
        
            Get-CsDatabaseMirrorState -DatabaseType Centralmgmt -PoolFqdn <Backup_Pool Fqdn>
    
      - <span data-ttu-id="dc7bd-135">Если основной сервер в пуле резервной копии\_является основным, введите:</span><span class="sxs-lookup"><span data-stu-id="dc7bd-135">If the primary Back End Server in Backup\_Pool is the principal, type:</span></span>
        
            Invoke-CSManagementServerFailover -BackupSQLServerFqdn <Backup_Pool Primary BackEnd Server FQDN> -BackupSQLInstanceName <Backup_Pool Primary SQL Instance Name>
        
        <span data-ttu-id="dc7bd-136">Если сервер зеркального отображения в пуле резервных копий\_является основным, введите:</span><span class="sxs-lookup"><span data-stu-id="dc7bd-136">If the mirror Back End Server in Backup\_Pool is the principal, type:</span></span>
        
            Invoke-CSManagementServerFailover -MirrorSQLServerFqdn <Backup_Pool Mirror BackEnd Server FQDN> -MirrorSQLInstanceName <Backup_Pool Mirror SQL Instance Name>
    
      - <span data-ttu-id="dc7bd-137">Убедитесь, что переход на центральный сервер управления завершен.</span><span class="sxs-lookup"><span data-stu-id="dc7bd-137">Validate that the Central Management Server failover is complete.</span></span> <span data-ttu-id="dc7bd-138">Введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="dc7bd-138">Type the following:</span></span>
        
            Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
        
        <span data-ttu-id="dc7bd-139">Убедитесь, что оба Активемастерфкдн и Активефилетрансферажентс указывают на полное доменное имя\_пула резервных копий.</span><span class="sxs-lookup"><span data-stu-id="dc7bd-139">Check that both ActiveMasterFQDN and ActiveFileTransferAgents are pointing to the FQDN of Backup\_Pool.</span></span>
    
      - <span data-ttu-id="dc7bd-140">Наконец, проверьте состояние реплики для всех серверов переднего плана, введя следующее:</span><span class="sxs-lookup"><span data-stu-id="dc7bd-140">Finally, check the replica status for all Front End Servers by typing the following:</span></span>
        
            Get-CsManagementStoreReplicationStatus 
        
        <span data-ttu-id="dc7bd-141">Убедитесь, что все реплики имеют значение истина.</span><span class="sxs-lookup"><span data-stu-id="dc7bd-141">Check that all replicas have a value of True.</span></span>
        
        <span data-ttu-id="dc7bd-142">Перейдите к шагу 7 в этой процедуре.</span><span class="sxs-lookup"><span data-stu-id="dc7bd-142">Skip to step 7 in this procedure.</span></span>

6.  <span data-ttu-id="dc7bd-143">Установите хранилище Central Management на сервере заднего резервного\_пула.</span><span class="sxs-lookup"><span data-stu-id="dc7bd-143">Install the Central Management store on the Back End Server of Backup\_Pool.</span></span>
    
      - <span data-ttu-id="dc7bd-144">Сначала выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="dc7bd-144">First, run the following command:</span></span>
        
        ```PowerShell 
        Install-CsDatabase -CentralManagementDatabase -Clean -SqlServerFqdn <Backup_Pool Back End Server FQDN> -SqlInstanceName rtc  
        ```
    
      - <span data-ttu-id="dc7bd-145">Запустите следующую команду на одном из серверов переднего плана резервного\_пула, чтобы принудительно переместить хранилище Центрального управления.</span><span class="sxs-lookup"><span data-stu-id="dc7bd-145">Run the next command on one of the Front End Servers of Backup\_Pool to force the move of the Central Management store:</span></span>
        
            Move-CsManagementServer -ConfigurationFileName c:\CsConfigurationFile.zip -LisConfigurationFileName c:\CsLisConfigurationFile.zip -Force 
    
      - <span data-ttu-id="dc7bd-146">Проверка завершения перемещения.</span><span class="sxs-lookup"><span data-stu-id="dc7bd-146">Validate the move is complete:</span></span>
        
            Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
        
        <span data-ttu-id="dc7bd-147">Убедитесь, что оба Активемастерфкдн и Активефилетрансферажентс указывают на полное доменное имя\_пула резервных копий.</span><span class="sxs-lookup"><span data-stu-id="dc7bd-147">Check that both ActiveMasterFQDN and ActiveFileTransferAgents are pointing to the FQDN of Backup\_Pool.</span></span>
    
      - <span data-ttu-id="dc7bd-148">Проверьте состояние реплики для всех серверов переднего плана, введя следующее:</span><span class="sxs-lookup"><span data-stu-id="dc7bd-148">Check the replica status for all Front End Servers by typing the following:</span></span>
        
            Get-CsManagementStoreReplicationStatus 
        
        <span data-ttu-id="dc7bd-149">Убедитесь, что все реплики имеют значение истина.</span><span class="sxs-lookup"><span data-stu-id="dc7bd-149">Check that all replicas have a value of True.</span></span>
    
      - <span data-ttu-id="dc7bd-150">Установите службу центрального сервера управления на остальных серверах переднего плана в пуле резервных копий\_.</span><span class="sxs-lookup"><span data-stu-id="dc7bd-150">Install the Central Management Server service on the rest of the Front End Servers in Backup\_Pool.</span></span> <span data-ttu-id="dc7bd-151">Для этого выполните следующую команду на всех серверах переднего плана, кроме той, которую вы использовали при принудительном переходе на центральное хранилище управления в этой процедуре:</span><span class="sxs-lookup"><span data-stu-id="dc7bd-151">To do so, run the following command on all the Front End Servers, except the one you used when forcing the Central Management store move earlier in this procedure:</span></span>
        
            Bootstrapper /Setup 

7.  <span data-ttu-id="dc7bd-152">Отработка отказа пользователей из Pool1 в Pool2, выполнив следующий командлет в окне командной консоли Lync Server:</span><span class="sxs-lookup"><span data-stu-id="dc7bd-152">Fail over the users from Pool1 to Pool2 by running the following cmdlet in a Lync Server Management Shell window:</span></span>
    
        Invoke-CsPoolFailover -PoolFQDN <Pool1 FQDN> -DisasterMode -Verbose
    
    <span data-ttu-id="dc7bd-153">Поскольку действия, описанные в предыдущем разделе, для проверки состояния центрального хранилища управления не являются универсальными, возможно, этот командлет завершится сбоем, так как хранилище Центрального управления пока не проходит полную отработку отказа.</span><span class="sxs-lookup"><span data-stu-id="dc7bd-153">Because the steps taken in the previous parts of this procedure to check the Central Management store status are not universal, there is still a chance this cmdlet will fail because the Central Management store is not yet fully failed over.</span></span> <span data-ttu-id="dc7bd-154">В этом случае необходимо исправить центральное хранилище управления на основе отображаемых сообщений об ошибках, а затем повторно запустить этот командлет.</span><span class="sxs-lookup"><span data-stu-id="dc7bd-154">In this case, you must fix the Central Management store based on the error messages that you see, and then run this cmdlet again.</span></span>
    
    <span data-ttu-id="dc7bd-155">Если появляется следующее сообщение об ошибке, вам необходимо изменить пул EDGE на этом сайте, чтобы использовать другой пул в качестве следующего прыжка, прежде чем вы перейдете на пул.</span><span class="sxs-lookup"><span data-stu-id="dc7bd-155">If you see the following error message, then you need to change the Edge pool at this site to use a different pool as its next hop before failing over the pool.</span></span> <span data-ttu-id="dc7bd-156">Подробности можно найти в разделе процедуры, описанные в начале этой статьи.</span><span class="sxs-lookup"><span data-stu-id="dc7bd-156">For details, see the procedures at the beginning of this topic.</span></span>
    
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

