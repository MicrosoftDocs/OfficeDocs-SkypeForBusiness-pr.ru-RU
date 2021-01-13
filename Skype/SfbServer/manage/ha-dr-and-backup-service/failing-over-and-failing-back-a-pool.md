---
title: Отработка отказа для пула
ms.reviewer: ''
author: cichur
ms.author: v-cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: .
ms.openlocfilehash: 1ebd4e8110b8783c869530d95eda0646a895b88e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49826569"
---
# <a name="failing-over-and-failing-back-a-pool-in-skype-for-business-server"></a><span data-ttu-id="e5c08-103">Отбой и отбой пула в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="e5c08-103">Failing over and failing back a pool in Skype for Business Server</span></span> 

<span data-ttu-id="e5c08-104">Используйте следующие процедуры, если сбой одного пула переднего конца и требуется отбой или пул, в который произошла авария, снова в сети, и необходимо восстановить обычное рабочее состояние развертывания.</span><span class="sxs-lookup"><span data-stu-id="e5c08-104">Use the following procedures if a single Front End pool has failed and needs to be failed over, or the pool that experienced the disaster is back online and you need to restore your deployment to regular working status.</span></span> <span data-ttu-id="e5c08-105">Кроме того, узнайте, как отменить отбой и отменить отбой в пуле, используемом для федерации Skype для бизнеса или федерации XMPP, или изменить пул, связанный с пулом переднего края.</span><span class="sxs-lookup"><span data-stu-id="e5c08-105">Also  learn how to fail over and fail back the Edge pool used for Skype for Business federation or XMPP federation, or change the Edge pool associated with a Front End pool.</span></span>

- [<span data-ttu-id="e5c08-106">Отбой пула переднего входа</span><span class="sxs-lookup"><span data-stu-id="e5c08-106">Fail over a Front End pool</span></span>](#fail-over-a-front-end-pool)
- [<span data-ttu-id="e5c08-107">Отбой пула</span><span class="sxs-lookup"><span data-stu-id="e5c08-107">Fail back a pool</span></span>](#fail-back-a-pool)
- [<span data-ttu-id="e5c08-108">Отбой в пуле, используемом для федерации Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="e5c08-108">Fail over the Edge pool used for Skype for Business Server federation</span></span>](#fail-over-the-edge-pool-used-for-skype-for-business-server-federation)
- [<span data-ttu-id="e5c08-109">Отбой в пуле, используемом для федерации XMPP в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="e5c08-109">Fail over the Edge pool used for XMPP federation in Skype for Business Server</span></span>](#fail-over-the-edge-pool-used-for-xmpp-federation-in-skype-for-business-server)
- [<span data-ttu-id="e5c08-110">Отбой в пуле, используемом для федерации Skype для бизнеса Server или федерации XMPP</span><span class="sxs-lookup"><span data-stu-id="e5c08-110">Fail back the Edge pool used for Skype for Business Server federation or XMPP federation</span></span>](#fail-back-the-edge-pool-used-for-skype-for-business-server-federation-or-xmpp-federation)
- [<span data-ttu-id="e5c08-111">Изменение пула, связанного с пулом переднего края</span><span class="sxs-lookup"><span data-stu-id="e5c08-111">Change the Edge pool associated with a Front End pool</span></span>](#change-the-edge-pool-associated-with-a-front-end-pool)

## <a name="fail-over-a-front-end-pool"></a><span data-ttu-id="e5c08-112">Отбой пула переднего входа</span><span class="sxs-lookup"><span data-stu-id="e5c08-112">Fail over a Front End pool</span></span>

<span data-ttu-id="e5c08-113">В этой процедуре Datacenter1 содержит Pool1, и произошел отказ Pool1.</span><span class="sxs-lookup"><span data-stu-id="e5c08-113">In this procedure, Datacenter1 contains Pool1, and Pool1 has failed.</span></span> <span data-ttu-id="e5c08-114">Выполняется обход отказавшего пула к пулу Pool2, находящемуся в Datacenter2.</span><span class="sxs-lookup"><span data-stu-id="e5c08-114">You are failing over to Pool2 located in Datacenter2.</span></span>

<span data-ttu-id="e5c08-115">Большая часть работы по отсечению пула включает отбой центрального банка управления, если это необходимо.</span><span class="sxs-lookup"><span data-stu-id="e5c08-115">Most of the work for the pool failover involves failing over the Central Management store, if it is required.</span></span> <span data-ttu-id="e5c08-116">Это важно, так как центральное хранилище управления должно работать при отсечении пользователей пула.</span><span class="sxs-lookup"><span data-stu-id="e5c08-116">This is important because the Central Management store must be functional when the pool’s users are failed over.</span></span>

<span data-ttu-id="e5c08-p104">Кроме того, если возник отказ клиентского пула, но пограничный пул на этом сайте по-прежнему работает, необходимо знать, используется ли пограничным пулом отказавший пул в качестве следующего перехода по пулам. Если используется, следует изменить пограничный пул, чтобы он использовал другой клиентский пул до обхода отказавшего клиентского пула. Порядок изменения настройки следующего перехода по пулам зависит от того, будет ли пограничный пул использовать пул на том же сайте, на котором находится пограничный пул, или на другом сайте.</span><span class="sxs-lookup"><span data-stu-id="e5c08-p104">Additionally, if a Front End pool fails but the Edge pool at that site is still running, you must know whether the Edge pool uses the failed pool as a next hop pool. If it does, you must change the Edge pool to use a different Front End pool before failing over the failed Front End pool. How you change the next hop setting depends on whether the Edge will use a pool at the same site as the Edge pool, or a different site.</span></span>

<span data-ttu-id="e5c08-120">**Настройка пула edge для использования пула следующего прыжка на том же сайте**</span><span class="sxs-lookup"><span data-stu-id="e5c08-120">**To set an Edge pool to use a next hop pool at the same site**</span></span>

1.  <span data-ttu-id="e5c08-121">Откройте построитель топологий, щелкните правой кнопкой мыши нужный пул и выберите "Изменить **свойства".**</span><span class="sxs-lookup"><span data-stu-id="e5c08-121">Open Topology Builder, right-click the Edge pool that needs to be changed, and click **Edit Properties**.</span></span>

2.  <span data-ttu-id="e5c08-p105">Щелкните **Следующий переход**. В списке **Пул следующего перехода:** выберите пул, который сейчас служит в качестве пула следующего перехода.</span><span class="sxs-lookup"><span data-stu-id="e5c08-p105">Click **Next Hop**. From the **Next hop pool:** list, select the pool which will now serve as the next hop pool.</span></span>

3.  <span data-ttu-id="e5c08-124">Нажмите кнопку **ОК**, а затем опубликуйте изменения.</span><span class="sxs-lookup"><span data-stu-id="e5c08-124">Click **OK**, and then publish the changes.</span></span>

<span data-ttu-id="e5c08-125">**Настройка пула edge для использования пула следующего прыжка на другом сайте**</span><span class="sxs-lookup"><span data-stu-id="e5c08-125">**To set an Edge pool to use a next hop pool at a different site**</span></span>

1.  <span data-ttu-id="e5c08-126">Откройте окно оболочки управления Skype для бизнеса Server и введите следующий cmdlet:</span><span class="sxs-lookup"><span data-stu-id="e5c08-126">Open a Skype for Business Server Management Shell window and type the following cmdlet:</span></span>
    
        Set-CsEdgeServer -Identity EdgeServer:<Edge Server pool FQDN> -Registrar Registrar:<NextHopPoolFQDN>

<span data-ttu-id="e5c08-127">**Отбой пула в аварийной ситуации**</span><span class="sxs-lookup"><span data-stu-id="e5c08-127">**To fail over a pool in a disaster**</span></span>

1.  <span data-ttu-id="e5c08-128">Найдите пул, который является местом для центрального сервера управления, введя следующий cmdlet на сервере переднего сервера в пуле Pool2:</span><span class="sxs-lookup"><span data-stu-id="e5c08-128">Find which pool is the host for the Central Management Server by typing the following cmdlet on a Front End server in Pool2:</span></span>
    
        Invoke-CsManagementServerFailover -Whatif
    
    <span data-ttu-id="e5c08-129">В результатах этого cmdlet покажите, в котором в настоящее время размещен центральный сервер управления.</span><span class="sxs-lookup"><span data-stu-id="e5c08-129">The results of this cmdlet show which pool currently hosts the Central Management Server.</span></span> <span data-ttu-id="e5c08-130">В остальной части этой процедуры этот пул называется пулом \_ CMS.</span><span class="sxs-lookup"><span data-stu-id="e5c08-130">In the rest of this procedure, this pool is known as CMS\_Pool.</span></span>

2.  <span data-ttu-id="e5c08-131">Используйте построитель топологий для поиска версии Skype для бизнеса Server, запущенной в пуле \_ CMS.</span><span class="sxs-lookup"><span data-stu-id="e5c08-131">Use Topology Builder to find the version of Skype for Business Server running on the CMS\_Pool.</span></span> <span data-ttu-id="e5c08-132">Если на сервере работает Skype для бизнеса Server, используйте следующий cmdlet для поиска резервного пула пула 1.</span><span class="sxs-lookup"><span data-stu-id="e5c08-132">If it is running Skype for Business Server, use the following cmdlet to find the backup pool of Pool 1.</span></span>
    
        Get-CsPoolBackupRelationship -PoolFQDN <CMS_Pool FQDN>
    
    <span data-ttu-id="e5c08-133">Пул \_ резервных копий должен быть резервным пулом.</span><span class="sxs-lookup"><span data-stu-id="e5c08-133">Let Backup\_Pool be the backup pool.</span></span>

3.  <span data-ttu-id="e5c08-134">Проверьте состояние центрального банка управления с помощью следующего cmdlet:</span><span class="sxs-lookup"><span data-stu-id="e5c08-134">Check the status of the Central Management store with the following cmdlet:</span></span>
    
        Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
    
    <span data-ttu-id="e5c08-135">Этот cmdlet должен показать, что ActiveMasterFQDN и ActiveFileTransferAgents указывают на FQDN пула \_ CMS.</span><span class="sxs-lookup"><span data-stu-id="e5c08-135">This cmdlet should show that both ActiveMasterFQDN and ActiveFileTransferAgents are pointing to the FQDN of CMS\_Pool.</span></span> <span data-ttu-id="e5c08-136">Если они пустые, центральный сервер управления недопустим, и его необходимо переудать.</span><span class="sxs-lookup"><span data-stu-id="e5c08-136">If they are empty, the Central Management Server is not available and you must fail it over.</span></span>

4.  <span data-ttu-id="e5c08-137">Если центральное хранилище управления не доступно или центральное хранилище управления было запущено в пуле Pool1 (то есть в пуле, в который был сбой), необходимо перенаправить центральный сервер управления перед отбойом пула.</span><span class="sxs-lookup"><span data-stu-id="e5c08-137">If the Central Management store is not available or if the Central Management store was running on Pool1 (that is, the pool that has failed), you must fail over the Central Management Server before failing over the pool.</span></span> <span data-ttu-id="e5c08-138">Если необходимо перенаправить центральный сервер управления, который был запущен в пуле, где работает Skype для бизнеса Server, используйте этот cmdlet на шаге 5 этой процедуры.</span><span class="sxs-lookup"><span data-stu-id="e5c08-138">If you need to fail over the Central Management Server that was hosted on a pool running Skype for Business Server, use the cmdlet in step 5 of this procedure.</span></span> <span data-ttu-id="e5c08-139">Если нет необходимости в отступе центрального сервера управления, переперейти к шагу 7 этой процедуры.</span><span class="sxs-lookup"><span data-stu-id="e5c08-139">If you do not need to fail over the Central Management Server, skip to step 7 of this procedure.</span></span>

5.  <span data-ttu-id="e5c08-140">Чтобы переудать центральное хранилище управления в пуле, где работает Skype для бизнеса Server, сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="e5c08-140">To fail over the Central Management store on a pool running Skype for Business Server, do the following:</span></span>
    
      - <span data-ttu-id="e5c08-141">Сначала проверьте, какой тыловый сервер в резервном пуле запускает основной экземпляр центрального хранилище управления, введя \_ следующую информацию:</span><span class="sxs-lookup"><span data-stu-id="e5c08-141">First, check which Back End Server in Backup\_Pool runs the principal instance of the Central Management store by typing the following:</span></span>
        
            Get-CsDatabaseMirrorState -DatabaseType Centralmgmt -PoolFqdn <Backup_Pool Fqdn>
    
      - <span data-ttu-id="e5c08-142">Если основной сервер в резервном пуле \_ является основным, введите:</span><span class="sxs-lookup"><span data-stu-id="e5c08-142">If the primary Back End Server in Backup\_Pool is the principal, type:</span></span>
        
            Invoke-CSManagementServerFailover -BackupSQLServerFqdn <Backup_Pool Primary BackEnd Server FQDN> -BackupSQLInstanceName <Backup_Pool Primary SQL Instance Name>
        
        <span data-ttu-id="e5c08-143">Если основным является зеркальный тыловой сервер в резервном \_ пуле, введите:</span><span class="sxs-lookup"><span data-stu-id="e5c08-143">If the mirror Back End Server in Backup\_Pool is the principal, type:</span></span>
        
            Invoke-CSManagementServerFailover -MirrorSQLServerFqdn <Backup_Pool Mirror BackEnd Server FQDN> -MirrorSQLInstanceName <Backup_Pool Mirror SQL Instance Name>
    
      - <span data-ttu-id="e5c08-144">Проверьте, завершена ли отбой центрального сервера управления.</span><span class="sxs-lookup"><span data-stu-id="e5c08-144">Validate that the Central Management Server failover is complete.</span></span> <span data-ttu-id="e5c08-145">Введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="e5c08-145">Type the following:</span></span>
        
            Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
        
        <span data-ttu-id="e5c08-146">Убедитесь, что activeMasterFQDN и ActiveFileTransferAgents указывают на FQDN резервного \_ пула.</span><span class="sxs-lookup"><span data-stu-id="e5c08-146">Check that both ActiveMasterFQDN and ActiveFileTransferAgents are pointing to the FQDN of Backup\_Pool.</span></span>
    
      - <span data-ttu-id="e5c08-147">Наконец, проверьте состояние реплики для всех серверов переднего сервера, введя следующую информацию:</span><span class="sxs-lookup"><span data-stu-id="e5c08-147">Finally, check the replica status for all Front End Servers by typing the following:</span></span>
        
            Get-CsManagementStoreReplicationStatus 
        
        <span data-ttu-id="e5c08-148">Проверьте, все ли реплики имеют значение True.</span><span class="sxs-lookup"><span data-stu-id="e5c08-148">Check that all replicas have a value of True.</span></span>
        
        <span data-ttu-id="e5c08-149">Перейдите к действию 7 этой процедуры.</span><span class="sxs-lookup"><span data-stu-id="e5c08-149">Skip to step 7 in this procedure.</span></span>

6.  <span data-ttu-id="e5c08-150">Установите центральное хранилище управления на тыловый сервер резервного \_ пула.</span><span class="sxs-lookup"><span data-stu-id="e5c08-150">Install the Central Management store on the Back End Server of Backup\_Pool.</span></span>
    
      - <span data-ttu-id="e5c08-151">Сначала выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="e5c08-151">First, run the following command:</span></span>
        ```PowerShell
         
        Install-CsDatabase -CentralManagementDatabase -Clean -SqlServerFqdn <Backup_Pool Back End Server FQDN> -SqlInstanceName rtc  
        ```
    
      - <span data-ttu-id="e5c08-152">Чтобы принудительно переместить центральное хранилище управления, запустите следующую команду на одном из серверов переднего сервера резервного \_ пула:</span><span class="sxs-lookup"><span data-stu-id="e5c08-152">Run the next command on one of the Front End Servers of Backup\_Pool to force the move of the Central Management store:</span></span>
        
            Move-CsManagementServer -ConfigurationFileName c:\CsConfigurationFile.zip -LisConfigurationFileName c:\CsLisConfigurationFile.zip -Force 
    
      - <span data-ttu-id="e5c08-153">Проверьте, выполнилось ли перемещение.</span><span class="sxs-lookup"><span data-stu-id="e5c08-153">Validate the move is complete:</span></span>
        
            Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
        
        <span data-ttu-id="e5c08-154">Убедитесь, что activeMasterFQDN и ActiveFileTransferAgents указывают на FQDN резервного \_ пула.</span><span class="sxs-lookup"><span data-stu-id="e5c08-154">Check that both ActiveMasterFQDN and ActiveFileTransferAgents are pointing to the FQDN of Backup\_Pool.</span></span>
    
      - <span data-ttu-id="e5c08-155">Проверьте состояние реплики для всех серверов переднего плана, введя следующую команду:</span><span class="sxs-lookup"><span data-stu-id="e5c08-155">Check the replica status for all Front End Servers by typing the following:</span></span>
        
            Get-CsManagementStoreReplicationStatus 
        
        <span data-ttu-id="e5c08-156">Проверьте, все ли реплики имеют значение True.</span><span class="sxs-lookup"><span data-stu-id="e5c08-156">Check that all replicas have a value of True.</span></span>
    
      - <span data-ttu-id="e5c08-157">Установите службу центрального сервера управления на остальных серверах переднего сервера в резервном \_ пуле.</span><span class="sxs-lookup"><span data-stu-id="e5c08-157">Install the Central Management Server service on the rest of the Front End Servers in Backup\_Pool.</span></span> <span data-ttu-id="e5c08-158">Для этого запустите следующую команду на всех серверах переднего сервера, за исключением того, который использовался при принудительным перемещением центрального банка управления ранее в этой процедуре:</span><span class="sxs-lookup"><span data-stu-id="e5c08-158">To do so, run the following command on all the Front End Servers, except the one you used when forcing the Central Management store move earlier in this procedure:</span></span>
        
            Bootstrapper /Setup 

7.  <span data-ttu-id="e5c08-159">Чтобы перенаправить пользователей из пула Pool1 в пул 2, в окне оболочки управления Skype для бизнеса Server в окне управления Skype для бизнеса Server будет запущен следующий cmdlet:</span><span class="sxs-lookup"><span data-stu-id="e5c08-159">Fail over the users from Pool1 to Pool2 by running the following cmdlet in a Skype for Business Server Management Shell window:</span></span>
    
        Invoke-CsPoolFailover -PoolFQDN <Pool1 FQDN> -DisasterMode -Verbose
    
    <span data-ttu-id="e5c08-160">Поскольку действия, которые были предприняты в предыдущих частях этой процедуры для проверки состояния центрального банка управления, не являются универсальными, существует вероятность сбой этого cmdlet, так как центральное хранилище управления еще не полностью завершено.</span><span class="sxs-lookup"><span data-stu-id="e5c08-160">Because the steps taken in the previous parts of this procedure to check the Central Management store status are not universal, there is still a chance this cmdlet will fail because the Central Management store is not yet fully failed over.</span></span> <span data-ttu-id="e5c08-161">В этом случае необходимо исправить центральное хранилище управления на основе сообщений об ошибках, которые вы видите, а затем снова запустить этот cmdlet.</span><span class="sxs-lookup"><span data-stu-id="e5c08-161">In this case, you must fix the Central Management store based on the error messages that you see, and then run this cmdlet again.</span></span>
    
    <span data-ttu-id="e5c08-p113">Если выводится приводимое ниже сообщение об ошибке, необходимо изменить пограничный пул на данном сайте, чтобы использовать до обхода отказавшего пула другой пул в качестве следующего перехода. Подробности см. в описании процедур в начале этой статьи.</span><span class="sxs-lookup"><span data-stu-id="e5c08-p113">If you see the following error message, then you need to change the Edge pool at this site to use a different pool as its next hop before failing over the pool. For details, see the procedures at the beginning of this topic.</span></span>
    
        Invoke-CsPoolFailOver : This Front-end pool "pool1.contoso.com" is specified in
        topology as the next hop for the Edge server. Failing over this pool may cause External
        access/Federation/Split-domain/XMPP features to stop working. Please use Topology Builder to
        change the Edge internal next hop setting to point to a different Front-end pool,  before you
        proceed.


## <a name="fail-back-a-pool"></a><span data-ttu-id="e5c08-164">Отбой пула</span><span class="sxs-lookup"><span data-stu-id="e5c08-164">Fail back a pool</span></span>

<span data-ttu-id="e5c08-165">После возврата пула, в котором возникла аварийная ситуация, в режим работы (в данном примере это Pool1) выполните следующие действия для восстановления обычного рабочего состояния развертывания.</span><span class="sxs-lookup"><span data-stu-id="e5c08-165">After the pool that experienced the disaster is back online (that is, Pool1 in this example), take the following steps to restore your deployment to regular working status.</span></span>

<span data-ttu-id="e5c08-166">Обратите внимание, что процедура отработки отказа занимает несколько минут.</span><span class="sxs-lookup"><span data-stu-id="e5c08-166">Note that the failback process takes several minute to complete.</span></span>  <span data-ttu-id="e5c08-167">В качестве справки: отработка отказа для пула в 20000 пользователей занимает до 60 минут.</span><span class="sxs-lookup"><span data-stu-id="e5c08-167">For reference, it is expected to take up to 60 minutes for a pool of 20,000 users.</span></span>

<span data-ttu-id="e5c08-168">Восстановите размещение пользователей, которые изначально размещались в пуле Pool1 и были переключены на пул Pool2; для этого введите следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="e5c08-168">Fail back the users who were originally homed in Pool1 and have been failed over to Pool2 by typing the following cmdlet:</span></span>
    
    Invoke-CsPoolFailback -PoolFQDN <Pool1 FQDN> -Verbose

<span data-ttu-id="e5c08-169">Другие действия не требуются.</span><span class="sxs-lookup"><span data-stu-id="e5c08-169">No other steps are necessary.</span></span> <span data-ttu-id="e5c08-170">Если вы перейдут на центральный сервер управления, его можно оставить в пуле Pool2.</span><span class="sxs-lookup"><span data-stu-id="e5c08-170">If you failed over the Central Management Server, you can leave it in Pool2.</span></span>

## <a name="fail-over-the-edge-pool-used-for-skype-for-business-server-federation"></a><span data-ttu-id="e5c08-171">Отбой в пуле, используемом для федерации Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="e5c08-171">Fail over the Edge pool used for Skype for Business Server federation</span></span> 

<span data-ttu-id="e5c08-172">If the Edge pool where you have Skype for Business Server federation configured goes down, you must change federation to use a different Edge pool for federation to work.</span><span class="sxs-lookup"><span data-stu-id="e5c08-172">If the Edge pool where you have Skype for Business Server federation configured goes down, you must change federation to use a different Edge pool for federation to work.</span></span>

1.  <span data-ttu-id="e5c08-173">На интерфейсном сервере откройте построитель топологии.</span><span class="sxs-lookup"><span data-stu-id="e5c08-173">On a Front End server, open Topology Builder.</span></span> <span data-ttu-id="e5c08-174">**Разверните пулы,** а затем щелкните правой кнопкой мыши сервер или пул, настроенный в настоящее время для федерации.</span><span class="sxs-lookup"><span data-stu-id="e5c08-174">Expand **Edge pools**, and then right-click the Edge server or Edge server pool that is currently configured for Federation.</span></span> <span data-ttu-id="e5c08-175">Выберите пункт **Изменить свойства**.</span><span class="sxs-lookup"><span data-stu-id="e5c08-175">Select **Edit properties**.</span></span>

2.  <span data-ttu-id="e5c08-176">В разделе **Общие** области **Изменение свойств** снимите флажок **Включение федерации для этого пограничного пула (порт 5061)**.</span><span class="sxs-lookup"><span data-stu-id="e5c08-176">In **Edit Properties** under **General**, clear **Enable federation for this Edge pool (Port 5061)**.</span></span> <span data-ttu-id="e5c08-177">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="e5c08-177">Click **OK**.</span></span>

3.  <span data-ttu-id="e5c08-178">**Разверните пулы,** а затем щелкните правой кнопкой мыши сервер или пул, который вы хотите использовать для федерации.</span><span class="sxs-lookup"><span data-stu-id="e5c08-178">Expand **Edge pools**, and then right-click the Edge server or Edge server pool that you now want to use for Federation.</span></span> <span data-ttu-id="e5c08-179">Выберите пункт **Изменить свойства**.</span><span class="sxs-lookup"><span data-stu-id="e5c08-179">Select **Edit properties**.</span></span>

4.  <span data-ttu-id="e5c08-p119">В разделе **Общие** области **Изменение свойств** установите флажок **Включение федерации для этого пограничного пула (порт 5061)**. Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="e5c08-p119">In **Edit Properties** under **General**, select **Enable federation for this Edge pool (Port 5061)**. Click **OK**.</span></span>

5.  <span data-ttu-id="e5c08-p120">Щелкните **Действие**, выберите **Топология**, затем **Опубликовать**. По запросу **Публикация топологии** нажмите кнопку **Далее**. При завершении публикации нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="e5c08-p120">Click **Action**, select **Topology**, select **Publish**. When prompted on **Publish the topology**, click **Next**. When the Publish is finished, click **Finish**.</span></span>

6.  <span data-ttu-id="e5c08-185">На сервере edge откройте мастер развертывания Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="e5c08-185">On the Edge server, open the Skype for Business Server Deployment wizard.</span></span> <span data-ttu-id="e5c08-186">Click **Install or Update Skype for Business Server System**, and then click Setup or Remove Skype for Business Server **Components**.</span><span class="sxs-lookup"><span data-stu-id="e5c08-186">Click **Install or Update Skype for Business Server System**, and then click **Setup or Remove Skype for Business Server Components**.</span></span> <span data-ttu-id="e5c08-187">Нажмите кнопку **Перезапуск**.</span><span class="sxs-lookup"><span data-stu-id="e5c08-187">Click **Run Again**.</span></span>

7.  <span data-ttu-id="e5c08-188">Нажмите **Далее**.</span><span class="sxs-lookup"><span data-stu-id="e5c08-188">Click **Next**.</span></span> <span data-ttu-id="e5c08-189">На экране сводки будут отображаться действия по мере их выполнения.</span><span class="sxs-lookup"><span data-stu-id="e5c08-189">The summary screen will show actions as they are executed.</span></span> <span data-ttu-id="e5c08-190">После завершения развертывания щелкните **Просмотреть журнал** для просмотра доступных файлов журнала.</span><span class="sxs-lookup"><span data-stu-id="e5c08-190">Once the deployment is done, click **View Log** to view available log files.</span></span> <span data-ttu-id="e5c08-191">Нажмите кнопку **Готово**, чтобы завершить развертывание.</span><span class="sxs-lookup"><span data-stu-id="e5c08-191">Click **Finish** to complete the deployment.</span></span>
    
    <span data-ttu-id="e5c08-192">Если сайт, содержащий неработающий пограничный пул, содержит интерфейсные серверы, которые все еще продолжают работать, необходимо обновить службу веб-конференций и службу аудио- и видеоконференций на этих интерфейсных пулах для использования работоспособного пограничного пула, расположенного на удаленном сайте.</span><span class="sxs-lookup"><span data-stu-id="e5c08-192">If the site containing the failed Edge pool contains Front End Servers that are still running, you must update the Web Conferencing Service and A/V Conferencing Service on these Front End pools to use an Edge pool in a remote site that is still running.</span></span> 

 ## <a name="fail-over-the-edge-pool-used-for-xmpp-federation-in-skype-for-business-server"></a><span data-ttu-id="e5c08-193">Отбой в пуле, используемом для федерации XMPP в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="e5c08-193">Fail over the Edge pool used for XMPP federation in Skype for Business Server</span></span> 

<span data-ttu-id="e5c08-p123">В организации присутствует только один пограничный пул, назначенный  качестве пула для федерации XMPP. Если этот пул перестанет работать, необходимо выполнить отработку отказа федерации XMPP для использования другого пограничного пула, чтобы федерация XMPP снова начала функционировать.\</span><span class="sxs-lookup"><span data-stu-id="e5c08-p123">In your organization, there is one Edge pool designated as the pool to use for XMPP federation. If this pool goes down, you must fail over XMPP federation to use a different Edge pool before XMPP federation can work again.</span></span>

<span data-ttu-id="e5c08-196">При первой установке пограничных пулов и включении федерации XMPP можно упростить процедуру аварийного восстановления путем определения внешних SRV-записей DNS для всех пограничных пулов федерации XMPP, а не только одного.</span><span class="sxs-lookup"><span data-stu-id="e5c08-196">When you first install Edge pools and enable XMPP Federation, you can simplify the disaster recovery process by setting up external DNS SRV records for all of your Edge pools for XMPP federation, instead of just one.</span></span> <span data-ttu-id="e5c08-197">Каждая из этих SRV-записей должна содержать собственное значение приоритета.</span><span class="sxs-lookup"><span data-stu-id="e5c08-197">Each of these SRV records must have a different priority set.</span></span> <span data-ttu-id="e5c08-198">Весь трафик федерации XMPP проходит через пул с SRV-записью, имеющей наивысший приоритет.</span><span class="sxs-lookup"><span data-stu-id="e5c08-198">All XMPP federation traffic goes through the pool with the SRV record with the highest priority.</span></span> 

<span data-ttu-id="e5c08-199">В следующей процедуре EdgePool1 — это пул, в котором изначально была размещена федерация XMPP, а EdgePool2 — пул, в котором будет размещена федерация XMPP.</span><span class="sxs-lookup"><span data-stu-id="e5c08-199">In the following procedure, EdgePool1 is the pool which originally hosted XMPP federation, and EdgePool2 is the pool which will now host XMPP federation.</span></span>


### <a name="to-fail-over-the-edge-pool-used-for-xmpp-federation"></a><span data-ttu-id="e5c08-200">Отбой в пуле, используемом для федерации XMPP</span><span class="sxs-lookup"><span data-stu-id="e5c08-200">To fail over the Edge pool used for XMPP federation</span></span>

1.  <span data-ttu-id="e5c08-201">Если другой пограничный пул еще не развернут (т. е. единственный пограничный пул в настоящее время не работает), разверните новый пул.</span><span class="sxs-lookup"><span data-stu-id="e5c08-201">If you don’t already have another Edge pool deployed (besides the one which is currently down), deploy that pool.</span></span> 

2.  <span data-ttu-id="e5c08-202">На каждом пограничном сервере в новом пограничном пуле, который теперь размещает федерацию XMPP EdgePool2), запустите следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="e5c08-202">On each Edge Server in the new Edge pool which will now host XMPP federation (EdgePool2), run the following cmdlet:</span></span>
    
        Stop-CsWindowsService

3.  <span data-ttu-id="e5c08-203">Выполните следующий командлет, чтобы переопределить маршрут федерации XMPP на сервер EdgePool2:</span><span class="sxs-lookup"><span data-stu-id="e5c08-203">Run the following cmdlet to repoint the XMPP federation route to EdgePool2:</span></span>
    
        Set-CsSite Site2 -XmppExternalFederationRoute EdgeServer2.contoso.com
    
    <span data-ttu-id="e5c08-204">В этом примере Site2 — это сайт, содержащий пограничный пул, который в настоящее время содержит пограничный пул, через который проходит маршрут федерации XMPP, а EdgeServer2.contoso.com — это полное доменное имя пограничного сервера в этом пуле.</span><span class="sxs-lookup"><span data-stu-id="e5c08-204">In this example, Site2 is the site containing the Edge pool which will now host the XMPP federation route, and EdgeServer2.contoso.com is the FQDN of an Edge Server in that pool.</span></span>

4.  <span data-ttu-id="e5c08-205">На внешнем DNS-сервере измените запись узла A для федерации XMPP, чтобы она указывала на EdgeServer2.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="e5c08-205">On the external DNS server, change the DNS A record for XMPP federation to point to EdgeServer2.contoso.com.</span></span>

5.  <span data-ttu-id="e5c08-p125">Если отсутствует SRV-запись федерации XMPP, которая разрешается в адрес пограничного пула, поддерживающего в настоящее время федерацию XMPP, необходимо добавить ее, как показано в следующем примере. В этой SRV-записи необходимо указать значение порта 5269.</span><span class="sxs-lookup"><span data-stu-id="e5c08-p125">If you do not already have a DNS SRV record for XMPP federation which resolves to the Edge pool which will now host XMPP federation, you must add it, as in the following example. This SRV record must have a port value of 5269.</span></span>
    
        _xmpp-server._tcp.contoso.com

6.  <span data-ttu-id="e5c08-208">Убедитесь, что на внешнем интерфейсе пограничного пула, в котором теперь размещена федерация XMPP, открыт порт 5269.</span><span class="sxs-lookup"><span data-stu-id="e5c08-208">Verify that the Edge pool which will now host XMPP federation has port 5269 open externally.</span></span>

7.  <span data-ttu-id="e5c08-209">Запустите службу на всех пограничных серверах в пограничном пуле, содержащем федерацию XMPP:</span><span class="sxs-lookup"><span data-stu-id="e5c08-209">Start the services on all Edge Servers in the Edge pool which will now host XMPP federation:</span></span>
    
        Start-CsWindowsService


## <a name="fail-back-the-edge-pool-used-for-skype-for-business-server-federation-or-xmpp-federation"></a><span data-ttu-id="e5c08-210">Отбой в пуле, используемом для федерации Skype для бизнеса Server или федерации XMPP</span><span class="sxs-lookup"><span data-stu-id="e5c08-210">Fail back the Edge pool used for Skype for Business Server federation or XMPP federation</span></span> 

<span data-ttu-id="e5c08-211">After a failed Edge pool that used to host federation has been brought back online, use this procedure to fail back the Skype for Business Server federation route and/or the XMPP federation route to again use this restored Edge pool.</span><span class="sxs-lookup"><span data-stu-id="e5c08-211">After a failed Edge pool that used to host federation has been brought back online, use this procedure to fail back the Skype for Business Server federation route and/or the XMPP federation route to again use this restored Edge pool.</span></span>

1.  <span data-ttu-id="e5c08-212">Запустите службы пограничного сервера на пограничном пуле, который снова доступен.</span><span class="sxs-lookup"><span data-stu-id="e5c08-212">On the Edge pool that is now available again, start the Edge Services.</span></span>

2.  <span data-ttu-id="e5c08-213">Чтобы восстановить маршрут федерации Skype для бизнеса Server для использования восстановленного сервера, сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="e5c08-213">If you want to fail back the Skype for Business Server federation route to use the restored Edge Server, do the following:</span></span>
    
      - <span data-ttu-id="e5c08-p126">На интерфейсном сервере откройте построитель топологий. Разверните узел **Пограничные пулы**, затем щелкните правой кнопкой мыши пограничный сервер или пул пограничных серверов, настроенный в настоящее время для федерации. Выберите пункт **Изменить свойства**.</span><span class="sxs-lookup"><span data-stu-id="e5c08-p126">On a Front End server, open Topology Builder. Expand **Edge pools**, then right click the Edge server or Edge server pool that is currently configured for Federation. Select **Edit properties**.</span></span>
    
      - <span data-ttu-id="e5c08-p127">В поле **Edit Properties** (Изменить свойства) раздела **General** (Общие) снимите флажок **Enable federation for this Edge pool (Port 5061)** (Разрешить федерацию для этого пограничного пула (порт 506)). Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="e5c08-p127">In **Edit Properties** under **General**, clear **Enable federation for this Edge pool (Port 5061)**. Click **OK**.</span></span>
    
      - <span data-ttu-id="e5c08-p128">Разверните **пограничные пулы**, затем щелкните правой кнопкой исходный пограничный сервер или пул пограничного сервера, который необходимо снова использовать для федерации. Выберите **Edit properties** (Изменить свойства).</span><span class="sxs-lookup"><span data-stu-id="e5c08-p128">Expand **Edge pools**, then right click the original Edge server or Edge server pool that you again want to use for Federation. Select **Edit properties**.</span></span>
    
      - <span data-ttu-id="e5c08-p129">В поле **Edit Properties** (Изменить свойства) раздела **General** (Общие) установите флажок **Enable federation for this Edge pool (Port 5061)** (Разрешить федерацию для этого пограничного пула (порт 506)). Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="e5c08-p129">In **Edit Properties** under **General**, select **Enable federation for this Edge pool (Port 5061)**. Click **OK**.</span></span>
    
      - <span data-ttu-id="e5c08-p130">Щелкните **Действие**, выберите **Топология**, затем **Опубликовать**. По запросу **Публикация топологии** нажмите кнопку **Далее**. При завершении публикации нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="e5c08-p130">Click **Action**, select **Topology**, select **Publish**. When prompted on **Publish the topology**, click **Next**. When the Publish is finished, click **Finish**.</span></span>
    
      - <span data-ttu-id="e5c08-226">На сервере edge откройте мастер развертывания Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="e5c08-226">On the Edge server, open the Skype for Business Server Deployment wizard.</span></span> <span data-ttu-id="e5c08-227">Click **Install or Update Skype for Business Server System,** then click Setup or Remove Skype for Business Server **Components**.</span><span class="sxs-lookup"><span data-stu-id="e5c08-227">Click **Install or Update Skype for Business Server System**, then click **Setup or Remove Skype for Business Server Components**.</span></span> <span data-ttu-id="e5c08-228">Нажмите кнопку **Перезапуск**.</span><span class="sxs-lookup"><span data-stu-id="e5c08-228">Click **Run Again**.</span></span>
    
      - <span data-ttu-id="e5c08-229">Нажмите **Далее**.</span><span class="sxs-lookup"><span data-stu-id="e5c08-229">Click **Next**.</span></span> <span data-ttu-id="e5c08-230">На экране сводки будут отображаться действия по мере их выполнения.</span><span class="sxs-lookup"><span data-stu-id="e5c08-230">The summary screen will show actions as they are executed.</span></span> <span data-ttu-id="e5c08-231">После завершения развертывания щелкните **Просмотреть журнал** для просмотра доступных файлов журнала.</span><span class="sxs-lookup"><span data-stu-id="e5c08-231">Once the deployment is done, click **View Log** to view available log files.</span></span> <span data-ttu-id="e5c08-232">Щелкните **Finish** (Готово) для завершения развертывания.</span><span class="sxs-lookup"><span data-stu-id="e5c08-232">Click **Finish** to complete the deployment.</span></span>

3.  <span data-ttu-id="e5c08-233">Если необходимо восстановить маршрутизацию федерации XMPP для использования восстановленного пограничного сервера, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="e5c08-233">If you want to fail back the XMPP federation route to use the restored Edge Server, do the following:</span></span>
    
      - <span data-ttu-id="e5c08-234">Выполните следующий командлет, чтобы повторно указать маршрут федерации XMPP к пограничному пулу, в котором теперь будет размещаться федерация XMPP (в данном примере — EdgeServer1):</span><span class="sxs-lookup"><span data-stu-id="e5c08-234">Run the following cmdlet to repoint the XMPP federation route to the Edge pool which will now host XMPP federation (in this example, EdgeServer1):</span></span>
        
            Set-CsSite Site1 -XmppExternalFederationRoute EdgeServer1.contoso.com
        
        <span data-ttu-id="e5c08-235">В данном примере Site1 — это сайт, содержащий пограничный пул, в котором теперь размещается маршрут федерации XMPP, а EdgeServer1.contoso.com — это полное доменное имя пограничного сервера в этом пуле.</span><span class="sxs-lookup"><span data-stu-id="e5c08-235">In this example, Site1 is the site containing the Edge pool which will now host the XMPP federation route, and EdgeServer1.contoso.com is the FQDN of an Edge Server in that pool.</span></span>
    
      - <span data-ttu-id="e5c08-p133">Если у вас пока нет записи DNS SRV для федерации XMPP, которая разрешается в пограничный пул, где будет размещаться федерация XMPP, вы должны добавить ее, как указано в следующем примере. Для этой записи SRV необходимо указать значение порта 5269.</span><span class="sxs-lookup"><span data-stu-id="e5c08-p133">If you do not already have a DNS SRV record for XMPP federation which resolves to the Edge pool which will now host XMPP federation, you must add it, as in the following example. This SRV record must have a port value of 5269.</span></span>
        
            _xmpp-server._tcp.contoso.com
    
      - <span data-ttu-id="e5c08-238">На внешнем DNS-сервере измените запись DNS A для федерации XMPP таким образом, чтобы она указывала на EdgeServer2.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="e5c08-238">On the external DNS server, change the DNS A record for XMPP federation to point to EdgeServer2.contoso.com.</span></span>
    
      - <span data-ttu-id="e5c08-239">Убедитесь, что порт 5269 пограничного пула, в котором теперь будет размещаться федерация XMPP, открыт на внешнем уровне.</span><span class="sxs-lookup"><span data-stu-id="e5c08-239">Verify that the Edge pool which will now host XMPP federation has port 5269 open externally.</span></span>

4.  <span data-ttu-id="e5c08-240">Если пулы переднего края остаются работающими на сайте, содержаном сбойного пула и восстановленном, следует обновить службу веб-служб и службу видео- и видеоконференций в этих пулах переднего края, чтобы снова использовать пулы edge на локальном сайте.</span><span class="sxs-lookup"><span data-stu-id="e5c08-240">If the Front End pools remained running in the site containing the Edge pool that failed and has been restored, you should update the Web Conferencing Service and A/V Conferencing Service on these Front End pools to again use the Edge pools at their local site.</span></span>

5.  <span data-ttu-id="e5c08-241">Если происходит сбой пула переднего плана на том же сайте, где располагается отказавший пограничный пул, можно использовать Invoke–CsPoolFailback для восстановления пула переднего плана.</span><span class="sxs-lookup"><span data-stu-id="e5c08-241">If the Front End pool at the same site as the failed Edge pool also failed, you can now use Invoke–CsPoolFailback to fail back the Front End pool.</span></span>


## <a name="change-the-edge-pool-associated-with-a-front-end-pool"></a><span data-ttu-id="e5c08-242">Изменение пула, связанного с пулом переднего края</span><span class="sxs-lookup"><span data-stu-id="e5c08-242">Change the Edge pool associated with a Front End pool</span></span>

<span data-ttu-id="e5c08-243">Если пограничный пул отключается, однако интерфейсный пул все еще работает, необходимо указать для интерфейсного пула использование пограничного пула в другом сайте, пока не будет восстановлена работоспособность сбойного пограничного пула.</span><span class="sxs-lookup"><span data-stu-id="e5c08-243">If an Edge pool goes down but the Front End pool at the same site is still running, you will need to set the Front End pool to use an Edge pool at a different site until the failed Edge pool is restored.</span></span>

1.  <span data-ttu-id="e5c08-244">В построителе топологий перейдите к имени интерфейсного пула, который необходимо изменить.</span><span class="sxs-lookup"><span data-stu-id="e5c08-244">In Topology Builder, navigate to the name of the Front End pool you need to change.</span></span>

2.  <span data-ttu-id="e5c08-245">Щелкните правой кнопкой мыши соответствующий пул, а затем выберите **Изменить свойства**.</span><span class="sxs-lookup"><span data-stu-id="e5c08-245">Right-click the pool, and then click **Edit Properties**.</span></span>

3.  <span data-ttu-id="e5c08-246">В разделе **Связи** под надписью **Сопоставить пограничный пул (для компонентов мультимедиа)** используйте раскрывающееся поле для выбора пограничного пула, с которым следует сопоставить интерфейсный пул.</span><span class="sxs-lookup"><span data-stu-id="e5c08-246">In the **Associations** section, under **Associate Edge Pool (for media components)**, use the drop down box to select the Edge pool you want to associate this Front End pool with.</span></span>

4.  <span data-ttu-id="e5c08-247">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="e5c08-247">Click **OK**.</span></span>
