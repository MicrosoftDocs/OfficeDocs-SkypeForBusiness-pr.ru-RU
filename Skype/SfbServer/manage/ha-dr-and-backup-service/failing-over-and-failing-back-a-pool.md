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
ms.openlocfilehash: 547a71f44fa81f9ba12a1c661465c7b8604b3fa1
ms.sourcegitcommit: 414d077b16a0ae4ea6a49e3b3d0082858174cacb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/17/2021
ms.locfileid: "50278679"
---
# <a name="failing-over-and-failing-back-a-pool-in-skype-for-business-server"></a><span data-ttu-id="5fa57-103">Отбой и отбой пула в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="5fa57-103">Failing over and failing back a pool in Skype for Business Server</span></span>

<span data-ttu-id="5fa57-104">Используйте следующие процедуры, если сбой одного пула Front-End и требуется отбой или пул, в который произошла авария, снова в сети и необходимо восстановить состояние обычной работы развертывания.</span><span class="sxs-lookup"><span data-stu-id="5fa57-104">Use the following procedures if a single Front-End pool has failed and needs to be failed over, or the pool that experienced the disaster is back online and you need to restore your deployment to regular working status.</span></span> <span data-ttu-id="5fa57-105">Learn how to fail over and fail back the Edge pool used for Skype for Business federation or XMPP federation, or change the Edge pool associated with a Front-End pool.</span><span class="sxs-lookup"><span data-stu-id="5fa57-105">Learn how to fail over and fail back the Edge pool used for Skype for Business federation or XMPP federation, or change the Edge pool associated with a Front-End pool.</span></span>

- [<span data-ttu-id="5fa57-106">Отбой пула переднего входа</span><span class="sxs-lookup"><span data-stu-id="5fa57-106">Fail over a Front End pool</span></span>](#fail-over-a-front-end-pool)
- [<span data-ttu-id="5fa57-107">Отбой пула</span><span class="sxs-lookup"><span data-stu-id="5fa57-107">Fail back a pool</span></span>](#fail-back-a-pool)
- [<span data-ttu-id="5fa57-108">Отбой в пуле, используемом для федерации Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="5fa57-108">Fail over the Edge pool used for Skype for Business Server federation</span></span>](#fail-over-the-edge-pool-used-for-skype-for-business-server-federation)
- [<span data-ttu-id="5fa57-109">Отбой в пуле, используемом для федерации XMPP в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="5fa57-109">Fail over the Edge pool used for XMPP federation in Skype for Business Server</span></span>](#fail-over-the-edge-pool-used-for-xmpp-federation-in-skype-for-business-server)
- [<span data-ttu-id="5fa57-110">Отбой в пуле, используемом для федерации Skype для бизнеса Server или федерации XMPP</span><span class="sxs-lookup"><span data-stu-id="5fa57-110">Fail back the Edge pool used for Skype for Business Server federation or XMPP federation</span></span>](#fail-back-the-edge-pool-used-for-skype-for-business-server-federation-or-xmpp-federation)
- [<span data-ttu-id="5fa57-111">Изменение пула, связанного с пулом переднего края</span><span class="sxs-lookup"><span data-stu-id="5fa57-111">Change the Edge pool associated with a Front End pool</span></span>](#change-the-edge-pool-associated-with-a-front-end-pool)

## <a name="fail-over-a-front-end-pool"></a><span data-ttu-id="5fa57-112">Отбой Front-End пула</span><span class="sxs-lookup"><span data-stu-id="5fa57-112">Fail over a Front-End pool</span></span>

<span data-ttu-id="5fa57-113">Datacenter1 содержит pool1, и сбой пула Pool1.</span><span class="sxs-lookup"><span data-stu-id="5fa57-113">Datacenter1 contains Pool1, and Pool1 has failed.</span></span> <span data-ttu-id="5fa57-114">Отбой в пуле 2, расположенном в центре обработки данных 2.</span><span class="sxs-lookup"><span data-stu-id="5fa57-114">You're failing over to Pool2 located in Datacenter2.</span></span>

<span data-ttu-id="5fa57-115">Большая часть работы по отсечению пула включает отбой центрального банка управления, если это необходимо.</span><span class="sxs-lookup"><span data-stu-id="5fa57-115">Most of the work for the pool failover involves failing over the Central Management store, if it's required.</span></span> <span data-ttu-id="5fa57-116">Центральное хранилище управления должно работать при отсечении пользователей пула.</span><span class="sxs-lookup"><span data-stu-id="5fa57-116">The Central Management store must be functional when the pool’s users are failed over.</span></span>

<span data-ttu-id="5fa57-117">В случае Front-End пула, но пул edge на этом сайте по-прежнему работает, необходимо знать, использует ли пул сбойных пулов в качестве пула следующего прыжка.</span><span class="sxs-lookup"><span data-stu-id="5fa57-117">If a Front-End pool fails, but the Edge pool at that site is still running, you must know whether the Edge pool uses the failed pool as a next hop pool.</span></span> <span data-ttu-id="5fa57-118">В этом случае необходимо изменить пул edge, чтобы использовать другой пул Front-End, прежде чем отменить отбой для Front-End пула.</span><span class="sxs-lookup"><span data-stu-id="5fa57-118">If it does, you must change the Edge pool to use a different Front-End pool before failing over the failed Front-End pool.</span></span> <span data-ttu-id="5fa57-119">Порядок изменения настройки следующего перехода по пулам зависит от того, будет ли пограничный пул использовать пул на том же сайте, на котором находится пограничный пул, или на другом сайте.</span><span class="sxs-lookup"><span data-stu-id="5fa57-119">How you change the next hop setting depends on whether the Edge will use a pool at the same site as the Edge pool, or a different site.</span></span>

<span data-ttu-id="5fa57-120">**Настройка пула edge для использования пула следующего прыжка на том же сайте**</span><span class="sxs-lookup"><span data-stu-id="5fa57-120">**To set an Edge pool to use a next hop pool at the same site**</span></span>

1. <span data-ttu-id="5fa57-121">Откройте построитель топологий, щелкните правой кнопкой мыши нужный пул и выберите "Изменить **свойства".**</span><span class="sxs-lookup"><span data-stu-id="5fa57-121">Open Topology Builder, right-click the Edge pool that needs to be changed, and select **Edit Properties**.</span></span>

2. <span data-ttu-id="5fa57-122">Выберите **следующий переход.**</span><span class="sxs-lookup"><span data-stu-id="5fa57-122">Select **Next Hop**.</span></span> <span data-ttu-id="5fa57-123">В **пуле следующего прыжка выберите** пул, который будет теперь служить пулом следующего прыжка.</span><span class="sxs-lookup"><span data-stu-id="5fa57-123">From the **Next hop pool:** list, select the pool that will now serve as the next hop pool.</span></span>

3. <span data-ttu-id="5fa57-124">Выберите **"ОК"** и опубликуем изменения.</span><span class="sxs-lookup"><span data-stu-id="5fa57-124">Select **OK**, and then publish the changes.</span></span>

<span data-ttu-id="5fa57-125">**Настройка пула edge для использования пула следующего прыжка на другом сайте**</span><span class="sxs-lookup"><span data-stu-id="5fa57-125">**To set an Edge pool to use a next hop pool at a different site**</span></span>

1. <span data-ttu-id="5fa57-126">Откройте окно оболочки управления Skype для бизнеса Server и введите следующий cmdlet:</span><span class="sxs-lookup"><span data-stu-id="5fa57-126">Open a Skype for Business Server Management Shell window and type the following cmdlet:</span></span>

        Set-CsEdgeServer -Identity EdgeServer:<Edge Server pool FQDN> -Registrar Registrar:<NextHopPoolFQDN>

<span data-ttu-id="5fa57-127">**Отбой пула в аварийной ситуации**</span><span class="sxs-lookup"><span data-stu-id="5fa57-127">**To fail over a pool in a disaster**</span></span>

1. <span data-ttu-id="5fa57-128">Найдите пул хост-серверов для центрального сервера управления, введя следующий Front-End в пуле Pool2:</span><span class="sxs-lookup"><span data-stu-id="5fa57-128">Find the host pool for the Central Management Server by typing the following cmdlet on a Front-End server in Pool2:</span></span>

        Invoke-CsManagementServerFailover -Whatif

    <span data-ttu-id="5fa57-129">В результатах этого cmdlet покажите, в котором в настоящее время размещен центральный сервер управления.</span><span class="sxs-lookup"><span data-stu-id="5fa57-129">The results of this cmdlet show which pool currently hosts the Central Management Server.</span></span> <span data-ttu-id="5fa57-130">В остальной части этой процедуры этот пул называется пулом \_ CMS.</span><span class="sxs-lookup"><span data-stu-id="5fa57-130">In the rest of this procedure, this pool is known as CMS\_Pool.</span></span>

2. <span data-ttu-id="5fa57-131">Используйте построитель топологий для поиска версии Skype для бизнеса Server, запущенной в пуле \_ CMS.</span><span class="sxs-lookup"><span data-stu-id="5fa57-131">Use Topology Builder to find the version of Skype for Business Server running on the CMS\_Pool.</span></span> <span data-ttu-id="5fa57-132">Если на нем работает Skype для бизнеса Server, используйте следующий cmdlet для поиска резервного пула пула 1.</span><span class="sxs-lookup"><span data-stu-id="5fa57-132">If it's running Skype for Business Server, use the following cmdlet to find the backup pool of Pool 1.</span></span>

        Get-CsPoolBackupRelationship -PoolFQDN <CMS_Pool FQDN>

    <span data-ttu-id="5fa57-133">Пул \_ резервных копий должен быть резервным пулом.</span><span class="sxs-lookup"><span data-stu-id="5fa57-133">Let Backup\_Pool be the backup pool.</span></span>

3. <span data-ttu-id="5fa57-134">Проверьте состояние центрального банка управления с помощью следующего cmdlet:</span><span class="sxs-lookup"><span data-stu-id="5fa57-134">Check the status of the Central Management store with the following cmdlet:</span></span>

        Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 

    <span data-ttu-id="5fa57-135">Этот cmdlet должен показать, что ActiveMasterFQDN и ActiveFileTransferAgents указывают на FQDN пула \_ CMS.</span><span class="sxs-lookup"><span data-stu-id="5fa57-135">This cmdlet should show that both ActiveMasterFQDN and ActiveFileTransferAgents are pointing to the FQDN of CMS\_Pool.</span></span> <span data-ttu-id="5fa57-136">Если они пустые, центральный сервер управления недопустим, и его необходимо переудать.</span><span class="sxs-lookup"><span data-stu-id="5fa57-136">If they are empty, the Central Management Server is not available and you must fail it over.</span></span>

4.  <span data-ttu-id="5fa57-137">Если центральное хранилище управления не доступно или центральное хранилище управления было запущено в пуле Pool1 (то есть в пуле, в который вошел сбой), необходимо перенаправить центральный сервер управления перед отбойом пула.</span><span class="sxs-lookup"><span data-stu-id="5fa57-137">If the Central Management store is not available or if the Central Management store was running on Pool1 (that is, the pool that has failed), you must fail over the Central Management Server before failing over the pool.</span></span> <span data-ttu-id="5fa57-138">Если необходимо перенаправить центральный сервер управления, который был запущен в пуле, где работает Skype для бизнеса Server, используйте этот cmdlet на шаге 5 этой процедуры.</span><span class="sxs-lookup"><span data-stu-id="5fa57-138">If you need to fail over the Central Management Server that was hosted on a pool running Skype for Business Server, use the cmdlet in step 5 of this procedure.</span></span> <span data-ttu-id="5fa57-139">Если нет необходимости в отступе центрального сервера управления, переперейти к шагу 7 этой процедуры.</span><span class="sxs-lookup"><span data-stu-id="5fa57-139">If you do not need to fail over the Central Management Server, skip to step 7 of this procedure.</span></span>

5.  <span data-ttu-id="5fa57-140">To fail over the Central Management store on a pool running Skype for Business Server, do the following:</span><span class="sxs-lookup"><span data-stu-id="5fa57-140">To fail over the Central Management store on a pool running Skype for Business Server, do the following:</span></span>

      - <span data-ttu-id="5fa57-141">Сначала проверьте, какой Back-End-сервер в резервном пуле запускает основной экземпляр центрального хранилище управления, введя \_ следующую информацию:</span><span class="sxs-lookup"><span data-stu-id="5fa57-141">First, check which Back-End Server in Backup\_Pool runs the principal instance of the Central Management store by typing the following:</span></span>

            Get-CsDatabaseMirrorState -DatabaseType Centralmgmt -PoolFqdn <Backup_Pool Fqdn>
    
      - <span data-ttu-id="5fa57-142">Если основным сервером Back-End в резервном \_ пуле является основной сервер, введите:</span><span class="sxs-lookup"><span data-stu-id="5fa57-142">If the primary Back-End Server in Backup\_Pool is the principal, type:</span></span>
        
            Invoke-CSManagementServerFailover -BackupSQLServerFqdn <Backup_Pool Primary BackEnd Server FQDN> -BackupSQLInstanceName <Backup_Pool Primary SQL Instance Name>
        
        <span data-ttu-id="5fa57-143">Если основным Back-End в резервном пуле является зеркальный \_ сервер, введите:</span><span class="sxs-lookup"><span data-stu-id="5fa57-143">If the mirror Back-End Server in Backup\_Pool is the principal, type:</span></span>
        
            Invoke-CSManagementServerFailover -MirrorSQLServerFqdn <Backup_Pool Mirror BackEnd Server FQDN> -MirrorSQLInstanceName <Backup_Pool Mirror SQL Instance Name>
    
      - <span data-ttu-id="5fa57-144">Проверьте, завершена ли отбой центрального сервера управления.</span><span class="sxs-lookup"><span data-stu-id="5fa57-144">Validate that the Central Management Server failover is complete.</span></span> <span data-ttu-id="5fa57-145">Введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="5fa57-145">Type the following command:</span></span>
        
            Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
        
        <span data-ttu-id="5fa57-146">Убедитесь, что activeMasterFQDN и ActiveFileTransferAgents указывают на FQDN резервного \_ пула.</span><span class="sxs-lookup"><span data-stu-id="5fa57-146">Check that both ActiveMasterFQDN and ActiveFileTransferAgents are pointing to the FQDN of Backup\_Pool.</span></span>
    
      - <span data-ttu-id="5fa57-147">Наконец, проверьте состояние реплики для всех Front-End Server, введя следующую информацию:</span><span class="sxs-lookup"><span data-stu-id="5fa57-147">Finally, check the replica status for all Front-End Servers by typing the following:</span></span>
        
            Get-CsManagementStoreReplicationStatus 
        
        <span data-ttu-id="5fa57-148">Проверьте, все ли реплики имеют значение True.</span><span class="sxs-lookup"><span data-stu-id="5fa57-148">Check that all replicas have a value of True.</span></span>
        
        <span data-ttu-id="5fa57-149">Перейдите к действию 7 этой процедуры.</span><span class="sxs-lookup"><span data-stu-id="5fa57-149">Skip to step 7 in this procedure.</span></span>

6.  <span data-ttu-id="5fa57-150">Установите центральное хранилище управления на тыловый сервер резервного \_ пула.</span><span class="sxs-lookup"><span data-stu-id="5fa57-150">Install the Central Management store on the Back End Server of Backup\_Pool.</span></span>
    
      - <span data-ttu-id="5fa57-151">Сначала выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="5fa57-151">First, run the following command:</span></span>
        ```PowerShell
         
        Install-CsDatabase -CentralManagementDatabase -Clean -SqlServerFqdn <Backup_Pool Back End Server FQDN> -SqlInstanceName rtc  
        ```
    
      - <span data-ttu-id="5fa57-152">Чтобы принудительно переместить центральное хранилище управления, запустите следующую команду на одном из серверов переднего сервера резервного \_ пула:</span><span class="sxs-lookup"><span data-stu-id="5fa57-152">Run the next command on one of the Front End Servers of Backup\_Pool to force the move of the Central Management store:</span></span>
        
            Move-CsManagementServer -ConfigurationFileName c:\CsConfigurationFile.zip -LisConfigurationFileName c:\CsLisConfigurationFile.zip -Force 
    
      - <span data-ttu-id="5fa57-153">Проверьте, выполнилось ли перемещение.</span><span class="sxs-lookup"><span data-stu-id="5fa57-153">Validate the move is complete:</span></span>
        
            Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
        
        <span data-ttu-id="5fa57-154">Убедитесь, что activeMasterFQDN и ActiveFileTransferAgents указывают на FQDN резервного \_ пула.</span><span class="sxs-lookup"><span data-stu-id="5fa57-154">Check that both ActiveMasterFQDN and ActiveFileTransferAgents are pointing to the FQDN of Backup\_Pool.</span></span>
    
      - <span data-ttu-id="5fa57-155">Проверьте состояние реплики для всех серверов переднего плана, введя следующую команду:</span><span class="sxs-lookup"><span data-stu-id="5fa57-155">Check the replica status for all Front End Servers by typing the following:</span></span>
        
            Get-CsManagementStoreReplicationStatus 
        
        <span data-ttu-id="5fa57-156">Проверьте, все ли реплики имеют значение True.</span><span class="sxs-lookup"><span data-stu-id="5fa57-156">Check that all replicas have a value of True.</span></span>
    
      - <span data-ttu-id="5fa57-157">Установите службу центрального сервера управления на остальных серверах переднего сервера в резервном \_ пуле.</span><span class="sxs-lookup"><span data-stu-id="5fa57-157">Install the Central Management Server service on the rest of the Front End Servers in Backup\_Pool.</span></span> <span data-ttu-id="5fa57-158">Для этого запустите следующую команду на всех серверах переднего сервера, за исключением команды, которая использовалась при принудительным перемещением центрального банка управления ранее в этой процедуре:</span><span class="sxs-lookup"><span data-stu-id="5fa57-158">To do so, run the following command on all the Front End Servers, except the one you used when forcing the Central Management store move earlier in this procedure:</span></span>
        
            Bootstrapper /Setup 

7.  <span data-ttu-id="5fa57-159">Чтобы перенаправить пользователей из пула Pool1 в пул 2, в окне оболочки управления Skype для бизнеса Server в окне управления Skype для бизнеса Server будет запущен следующий cmdlet:</span><span class="sxs-lookup"><span data-stu-id="5fa57-159">Fail over the users from Pool1 to Pool2 by running the following cmdlet in a Skype for Business Server Management Shell window:</span></span>
    
        Invoke-CsPoolFailover -PoolFQDN <Pool1 FQDN> -DisasterMode -Verbose
    
    <span data-ttu-id="5fa57-160">Поскольку действия, которые были предприняты в предыдущих частях этой процедуры для проверки состояния центрального банка управления, не являются универсальными, существует вероятность сбой этого cmdlet, так как центральное хранилище управления еще не полностью завершено.</span><span class="sxs-lookup"><span data-stu-id="5fa57-160">Because the steps taken in the previous parts of this procedure to check the Central Management store status are not universal, there is still a chance this cmdlet will fail because the Central Management store is not yet fully failed over.</span></span> <span data-ttu-id="5fa57-161">В этом случае необходимо исправить центральное хранилище управления на основе сообщений об ошибках, которые вы видите, а затем снова запустить этот cmdlet.</span><span class="sxs-lookup"><span data-stu-id="5fa57-161">In this case, you must fix the Central Management store based on the error messages that you see, and then run this cmdlet again.</span></span>
    
    <span data-ttu-id="5fa57-p113">Если выводится приводимое ниже сообщение об ошибке, необходимо изменить пограничный пул на данном сайте, чтобы использовать до обхода отказавшего пула другой пул в качестве следующего перехода. Подробности см. в описании процедур в начале этой статьи.</span><span class="sxs-lookup"><span data-stu-id="5fa57-p113">If you see the following error message, then you need to change the Edge pool at this site to use a different pool as its next hop before failing over the pool. For details, see the procedures at the beginning of this topic.</span></span>
    
        Invoke-CsPoolFailOver : This Front-end pool "pool1.contoso.com" is specified in
        topology as the next hop for the Edge server. Failing over this pool may cause External
        access/Federation/Split-domain/XMPP features to stop working. Please use Topology Builder to
        change the Edge internal next hop setting to point to a different Front-end pool,  before you
        proceed.


## <a name="fail-back-a-pool"></a><span data-ttu-id="5fa57-164">Отбой пула</span><span class="sxs-lookup"><span data-stu-id="5fa57-164">Fail back a pool</span></span>

<span data-ttu-id="5fa57-165">После возврата пула, в котором возникла аварийная ситуация, в режим работы (в данном примере это Pool1) выполните следующие действия для восстановления обычного рабочего состояния развертывания.</span><span class="sxs-lookup"><span data-stu-id="5fa57-165">After the pool that experienced the disaster is back online (that is, Pool1 in this example), take the following steps to restore your deployment to regular working status.</span></span>

<span data-ttu-id="5fa57-166">Процесс восстановления после сбой занимает несколько минут.</span><span class="sxs-lookup"><span data-stu-id="5fa57-166">The failback process takes several minute to complete.</span></span> <span data-ttu-id="5fa57-167">Для справки ожидается, что пул из 20 000 пользователей займет до 60 минут.</span><span class="sxs-lookup"><span data-stu-id="5fa57-167">For reference, it's expected to take up to 60 minutes for a pool of 20,000 users.</span></span>

<span data-ttu-id="5fa57-168">Восстановите размещение пользователей, которые изначально размещались в пуле Pool1 и были переключены на пул Pool2; для этого введите следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="5fa57-168">Fail back the users who were originally homed in Pool1 and have been failed over to Pool2 by typing the following cmdlet:</span></span>
    
    Invoke-CsPoolFailback -PoolFQDN <Pool1 FQDN> -Verbose

<span data-ttu-id="5fa57-169">Другие действия не требуются.</span><span class="sxs-lookup"><span data-stu-id="5fa57-169">No other steps are necessary.</span></span> <span data-ttu-id="5fa57-170">Если отбой был на центральном сервере управления, его можно оставить в пуле Pool2.</span><span class="sxs-lookup"><span data-stu-id="5fa57-170">If you failed over the Central Management Server, you can leave it in Pool2.</span></span>

## <a name="fail-over-the-edge-pool-used-for-skype-for-business-server-federation"></a><span data-ttu-id="5fa57-171">Отбой в пуле, используемом для федерации Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="5fa57-171">Fail over the Edge pool used for Skype for Business Server federation</span></span> 

<span data-ttu-id="5fa57-172">If the Edge pool where you have Skype for Business Server federation configured goes down, you must change federation to use a different Edge pool for federation to work.</span><span class="sxs-lookup"><span data-stu-id="5fa57-172">If the Edge pool where you have Skype for Business Server federation configured goes down, you must change federation to use a different Edge pool for federation to work.</span></span>

1.  <span data-ttu-id="5fa57-173">На интерфейсном сервере откройте построитель топологии.</span><span class="sxs-lookup"><span data-stu-id="5fa57-173">On a Front End server, open Topology Builder.</span></span> <span data-ttu-id="5fa57-174">**Разверните пулы,** а затем щелкните правой кнопкой мыши сервер или пул, настроенный в настоящее время для федерации.</span><span class="sxs-lookup"><span data-stu-id="5fa57-174">Expand **Edge pools**, and then right-click the Edge server or Edge server pool that is currently configured for Federation.</span></span> <span data-ttu-id="5fa57-175">Выберите пункт **Изменить свойства**.</span><span class="sxs-lookup"><span data-stu-id="5fa57-175">Select **Edit properties**.</span></span>

2.  <span data-ttu-id="5fa57-176">В разделе **Общие** области **Изменение свойств** снимите флажок **Включение федерации для этого пограничного пула (порт 5061)**.</span><span class="sxs-lookup"><span data-stu-id="5fa57-176">In **Edit Properties** under **General**, clear **Enable federation for this Edge pool (Port 5061)**.</span></span> <span data-ttu-id="5fa57-177">Нажмите **ОК**.</span><span class="sxs-lookup"><span data-stu-id="5fa57-177">Select **OK**.</span></span>

3.  <span data-ttu-id="5fa57-178">**Разверните пулы,** а затем щелкните правой кнопкой мыши сервер или пул, который вы хотите использовать для федерации.</span><span class="sxs-lookup"><span data-stu-id="5fa57-178">Expand **Edge pools**, and then right-click the Edge server or Edge server pool that you now want to use for Federation.</span></span> <span data-ttu-id="5fa57-179">Выберите пункт **Изменить свойства**.</span><span class="sxs-lookup"><span data-stu-id="5fa57-179">Select **Edit properties**.</span></span>

4.  <span data-ttu-id="5fa57-180">В разделе **Общие** области **Изменение свойств** установите флажок **Включение федерации для этого пограничного пула (порт 5061)**.</span><span class="sxs-lookup"><span data-stu-id="5fa57-180">In **Edit Properties** under **General**, select **Enable federation for this Edge pool (Port 5061)**.</span></span> <span data-ttu-id="5fa57-181">Нажмите **ОК**.</span><span class="sxs-lookup"><span data-stu-id="5fa57-181">Select **OK**.</span></span>

5.  <span data-ttu-id="5fa57-182">Выберите **действие,** выберите **топологию,** выберите **"Опубликовать".**</span><span class="sxs-lookup"><span data-stu-id="5fa57-182">Select **Action**, select **Topology**, select **Publish**.</span></span> <span data-ttu-id="5fa57-183">Когда вам будет предложено **опубликовать топологию,** выберите **"Далее".**</span><span class="sxs-lookup"><span data-stu-id="5fa57-183">When prompted on **Publish the topology**, select **Next**.</span></span> <span data-ttu-id="5fa57-184">После завершения публикации выберите **"Готово".**</span><span class="sxs-lookup"><span data-stu-id="5fa57-184">When the Publish is finished, select **Finish**.</span></span>

6.  <span data-ttu-id="5fa57-185">На этом сервере откройте мастер развертывания Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="5fa57-185">On the Edge server, open the Skype for Business Server Deployment wizard.</span></span> <span data-ttu-id="5fa57-186">Выберите "Установка или обновление системы Skype для бизнеса **Server",** а затем выберите "Установка" или "Удаление компонентов **Skype для бизнеса Server".**</span><span class="sxs-lookup"><span data-stu-id="5fa57-186">Select **Install or Update Skype for Business Server System**, and then select **Setup or Remove Skype for Business Server Components**.</span></span> <span data-ttu-id="5fa57-187">Выберите **"Выполнить еще раз"**.</span><span class="sxs-lookup"><span data-stu-id="5fa57-187">Select **Run Again**.</span></span>

7.  <span data-ttu-id="5fa57-188">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="5fa57-188">Select **Next**.</span></span> <span data-ttu-id="5fa57-189">В окне сводки будут показаны действия по мере их выполнения.</span><span class="sxs-lookup"><span data-stu-id="5fa57-189">The summary screen will show actions as they are executed.</span></span> <span data-ttu-id="5fa57-190">После развертывания выберите "Просмотр журнала", **чтобы** просмотреть доступные файлы журналов.</span><span class="sxs-lookup"><span data-stu-id="5fa57-190">Once the deployment is done, select **View Log** to view available log files.</span></span> <span data-ttu-id="5fa57-191">Выберите **"Готово",** чтобы завершить развертывание.</span><span class="sxs-lookup"><span data-stu-id="5fa57-191">Select **Finish** to complete the deployment.</span></span>
    
    <span data-ttu-id="5fa57-192">Если сайт, содержащий сбойный пул, содержит все еще работающие серверы переднего сервера, необходимо обновить службу веб-служб и службу видео- и видеоконференций в этих пулах Front-End, чтобы использовать пул в удаленном сайте, который еще работает.</span><span class="sxs-lookup"><span data-stu-id="5fa57-192">If the site containing the failed Edge pool contains Front End Servers that are still running, you must update the Web Conferencing Service and A/V Conferencing Service on these Front-End pools to use an Edge pool in a remote site that is still running.</span></span> 

 ## <a name="fail-over-the-edge-pool-used-for-xmpp-federation-in-skype-for-business-server"></a><span data-ttu-id="5fa57-193">Отбой в пуле, используемом для федерации XMPP в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="5fa57-193">Fail over the Edge pool used for XMPP federation in Skype for Business Server</span></span> 

<span data-ttu-id="5fa57-p123">В организации присутствует только один пограничный пул, назначенный  качестве пула для федерации XMPP. Если этот пул перестанет работать, необходимо выполнить отработку отказа федерации XMPP для использования другого пограничного пула, чтобы федерация XMPP снова начала функционировать.\</span><span class="sxs-lookup"><span data-stu-id="5fa57-p123">In your organization, there is one Edge pool designated as the pool to use for XMPP federation. If this pool goes down, you must fail over XMPP federation to use a different Edge pool before XMPP federation can work again.</span></span>

<span data-ttu-id="5fa57-196">При первой установке пограничных пулов и включении федерации XMPP можно упростить процедуру аварийного восстановления путем определения внешних SRV-записей DNS для всех пограничных пулов федерации XMPP, а не только одного.</span><span class="sxs-lookup"><span data-stu-id="5fa57-196">When you first install Edge pools and enable XMPP Federation, you can simplify the disaster recovery process by setting up external DNS SRV records for all of your Edge pools for XMPP federation, instead of just one.</span></span> <span data-ttu-id="5fa57-197">Каждая из этих SRV-записей должна содержать собственное значение приоритета.</span><span class="sxs-lookup"><span data-stu-id="5fa57-197">Each of these SRV records must have a different priority set.</span></span> <span data-ttu-id="5fa57-198">Весь трафик федерации XMPP проходит через пул с SRV-записью, имеющей наивысший приоритет.</span><span class="sxs-lookup"><span data-stu-id="5fa57-198">All XMPP federation traffic goes through the pool with the SRV record with the highest priority.</span></span> 

<span data-ttu-id="5fa57-199">В следующей процедуре EdgePool1 — это пул, в котором изначально была организована федерация XMPP, а EdgePool2 — пул, в котором теперь будет работать федерация XMPP.</span><span class="sxs-lookup"><span data-stu-id="5fa57-199">In the following procedure, EdgePool1 is the pool, which originally hosted XMPP federation, and EdgePool2 is the pool which will now host XMPP federation.</span></span>
### <a name="to-fail-over-the-edge-pool-used-for-xmpp-federation"></a><span data-ttu-id="5fa57-200">Отбой в пуле, используемом для федерации XMPP</span><span class="sxs-lookup"><span data-stu-id="5fa57-200">To fail over the Edge pool used for XMPP federation</span></span>

1.  <span data-ttu-id="5fa57-201">Если у вас еще нет другого развернутого пула (кроме того, который в настоящее время не работает), развернем этот пул.</span><span class="sxs-lookup"><span data-stu-id="5fa57-201">If you don’t already have another Edge pool deployed (besides the one that is currently down), deploy that pool.</span></span> 

2.  <span data-ttu-id="5fa57-202">На каждом пограничном сервере в новом пограничном пуле, который теперь размещает федерацию XMPP EdgePool2), запустите следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="5fa57-202">On each Edge Server in the new Edge pool which will now host XMPP federation (EdgePool2), run the following cmdlet:</span></span>
    
        Stop-CsWindowsService

3.  <span data-ttu-id="5fa57-203">Выполните следующий командлет, чтобы переопределить маршрут федерации XMPP на сервер EdgePool2:</span><span class="sxs-lookup"><span data-stu-id="5fa57-203">Run the following cmdlet to repoint the XMPP federation route to EdgePool2:</span></span>
    
        Set-CsSite Site2 -XmppExternalFederationRoute EdgeServer2.contoso.com
    
    <span data-ttu-id="5fa57-204">В этом примере Site2 — это сайт, содержащий пограничный пул, который в настоящее время содержит пограничный пул, через который проходит маршрут федерации XMPP, а EdgeServer2.contoso.com — это полное доменное имя пограничного сервера в этом пуле.</span><span class="sxs-lookup"><span data-stu-id="5fa57-204">In this example, Site2 is the site containing the Edge pool which will now host the XMPP federation route, and EdgeServer2.contoso.com is the FQDN of an Edge Server in that pool.</span></span>

4.  <span data-ttu-id="5fa57-205">На внешнем DNS-сервере измените запись узла A для федерации XMPP, чтобы она указывала на EdgeServer2.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="5fa57-205">On the external DNS server, change the DNS A record for XMPP federation to point to EdgeServer2.contoso.com.</span></span>

5.  <span data-ttu-id="5fa57-p125">Если отсутствует SRV-запись федерации XMPP, которая разрешается в адрес пограничного пула, поддерживающего в настоящее время федерацию XMPP, необходимо добавить ее, как показано в следующем примере. В этой SRV-записи необходимо указать значение порта 5269.</span><span class="sxs-lookup"><span data-stu-id="5fa57-p125">If you do not already have a DNS SRV record for XMPP federation which resolves to the Edge pool which will now host XMPP federation, you must add it, as in the following example. This SRV record must have a port value of 5269.</span></span>
    
        _xmpp-server._tcp.contoso.com

6.  <span data-ttu-id="5fa57-208">Убедитесь, что на внешнем интерфейсе пограничного пула, в котором теперь размещена федерация XMPP, открыт порт 5269.</span><span class="sxs-lookup"><span data-stu-id="5fa57-208">Verify that the Edge pool which will now host XMPP federation has port 5269 open externally.</span></span>

7.  <span data-ttu-id="5fa57-209">Запустите службу на всех пограничных серверах в пограничном пуле, содержащем федерацию XMPP:</span><span class="sxs-lookup"><span data-stu-id="5fa57-209">Start the services on all Edge Servers in the Edge pool which will now host XMPP federation:</span></span>
    
        Start-CsWindowsService

## <a name="fail-back-the-edge-pool-used-for-skype-for-business-server-federation-or-xmpp-federation"></a><span data-ttu-id="5fa57-210">Отбой в пуле, используемом для федерации Skype для бизнеса Server или федерации XMPP</span><span class="sxs-lookup"><span data-stu-id="5fa57-210">Fail back the Edge pool used for Skype for Business Server federation or XMPP federation</span></span> 

<span data-ttu-id="5fa57-211">After a failed Edge pool that used to host federation has been brought back online, use this procedure to fail back the Skype for Business Server federation route and/or the XMPP federation route to again use this restored Edge pool.</span><span class="sxs-lookup"><span data-stu-id="5fa57-211">After a failed Edge pool that used to host federation has been brought back online, use this procedure to fail back the Skype for Business Server federation route and/or the XMPP federation route to again use this restored Edge pool.</span></span>

1.  <span data-ttu-id="5fa57-212">Запустите службы пограничного сервера на пограничном пуле, который снова доступен.</span><span class="sxs-lookup"><span data-stu-id="5fa57-212">On the Edge pool that is now available again, start the Edge Services.</span></span>

2.  <span data-ttu-id="5fa57-213">Чтобы восстановить маршрут федерации Skype для бизнеса Server для использования восстановленного сервера, сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="5fa57-213">If you want to fail back the Skype for Business Server federation route to use the restored Edge Server, do the following:</span></span>
    
      - <span data-ttu-id="5fa57-214">На интерфейсном сервере откройте построитель топологии.</span><span class="sxs-lookup"><span data-stu-id="5fa57-214">On a Front End server, open Topology Builder.</span></span> <span data-ttu-id="5fa57-215">**Разверните пулы,** а затем щелкните правой кнопкой мыши сервер или пул, настроенный в настоящее время для федерации.</span><span class="sxs-lookup"><span data-stu-id="5fa57-215">Expand **Edge pools**, then right-click the Edge server or Edge server pool that is currently configured for Federation.</span></span> <span data-ttu-id="5fa57-216">Выберите пункт **Изменить свойства**.</span><span class="sxs-lookup"><span data-stu-id="5fa57-216">Select **Edit properties**.</span></span>
    
      - <span data-ttu-id="5fa57-217">В разделе **Общие** области **Изменение свойств** снимите флажок **Включение федерации для этого пограничного пула (порт 5061)**.</span><span class="sxs-lookup"><span data-stu-id="5fa57-217">In **Edit Properties** under **General**, clear **Enable federation for this Edge pool (Port 5061)**.</span></span> <span data-ttu-id="5fa57-218">Нажмите **ОК**.</span><span class="sxs-lookup"><span data-stu-id="5fa57-218">Select **OK**.</span></span>
    
      - <span data-ttu-id="5fa57-219">**Развернув пулы,** щелкните правой кнопкой мыши исходный сервер или пул серверов, который вы снова хотите использовать для федерации.</span><span class="sxs-lookup"><span data-stu-id="5fa57-219">Expand **Edge pools**, then right-click the original Edge server or Edge server pool that you again want to use for Federation.</span></span> <span data-ttu-id="5fa57-220">Выберите пункт **Изменить свойства**.</span><span class="sxs-lookup"><span data-stu-id="5fa57-220">Select **Edit properties**.</span></span>
    
      - <span data-ttu-id="5fa57-221">В разделе **Общие** области **Изменение свойств** установите флажок **Включение федерации для этого пограничного пула (порт 5061)**.</span><span class="sxs-lookup"><span data-stu-id="5fa57-221">In **Edit Properties** under **General**, select **Enable federation for this Edge pool (Port 5061)**.</span></span> <span data-ttu-id="5fa57-222">Нажмите **ОК**.</span><span class="sxs-lookup"><span data-stu-id="5fa57-222">Select **OK**.</span></span>
    
      - <span data-ttu-id="5fa57-223">Выберите **действие,** выберите **топологию,** выберите **"Опубликовать".**</span><span class="sxs-lookup"><span data-stu-id="5fa57-223">Select **Action**, select **Topology**, select **Publish**.</span></span> <span data-ttu-id="5fa57-224">Когда вам будет предложено **опубликовать топологию,** выберите **"Далее".**</span><span class="sxs-lookup"><span data-stu-id="5fa57-224">When prompted on **Publish the topology**, select **Next**.</span></span> <span data-ttu-id="5fa57-225">После завершения публикации выберите **"Готово".**</span><span class="sxs-lookup"><span data-stu-id="5fa57-225">When the Publish is finished, select **Finish**.</span></span>
    
      - <span data-ttu-id="5fa57-226">На этом сервере откройте мастер развертывания Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="5fa57-226">On the Edge server, open the Skype for Business Server Deployment wizard.</span></span> <span data-ttu-id="5fa57-227">Select **Install or Update Skype for Business Server System,** then select Setup or Remove Skype for Business Server **Components**.</span><span class="sxs-lookup"><span data-stu-id="5fa57-227">Select **Install or Update Skype for Business Server System**, then select **Setup or Remove Skype for Business Server Components**.</span></span> <span data-ttu-id="5fa57-228">Выберите **"Выполнить еще раз"**.</span><span class="sxs-lookup"><span data-stu-id="5fa57-228">Select **Run Again**.</span></span>
    
      - <span data-ttu-id="5fa57-229">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="5fa57-229">Select **Next**.</span></span> <span data-ttu-id="5fa57-230">В окне сводки будут показаны действия по мере их выполнения.</span><span class="sxs-lookup"><span data-stu-id="5fa57-230">The summary screen will show actions as they are executed.</span></span> <span data-ttu-id="5fa57-231">После развертывания выберите "Просмотр журнала", **чтобы** просмотреть доступные файлы журналов.</span><span class="sxs-lookup"><span data-stu-id="5fa57-231">Once the deployment is done, select **View Log** to view available log files.</span></span> <span data-ttu-id="5fa57-232">Выберите **"Готово",** чтобы завершить развертывание.</span><span class="sxs-lookup"><span data-stu-id="5fa57-232">Select **Finish** to complete the deployment.</span></span>

3.  <span data-ttu-id="5fa57-233">Если необходимо восстановить маршрутизацию федерации XMPP для использования восстановленного пограничного сервера, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="5fa57-233">If you want to fail back the XMPP federation route to use the restored Edge Server, do the following:</span></span>
    
      - <span data-ttu-id="5fa57-234">Выполните следующий командлет, чтобы повторно указать маршрут федерации XMPP к пограничному пулу, в котором теперь будет размещаться федерация XMPP (в данном примере — EdgeServer1):</span><span class="sxs-lookup"><span data-stu-id="5fa57-234">Run the following cmdlet to repoint the XMPP federation route to the Edge pool which will now host XMPP federation (in this example, EdgeServer1):</span></span>
        
            Set-CsSite Site1 -XmppExternalFederationRoute EdgeServer1.contoso.com
        
        <span data-ttu-id="5fa57-235">В данном примере Site1 — это сайт, содержащий пограничный пул, в котором теперь размещается маршрут федерации XMPP, а EdgeServer1.contoso.com — это полное доменное имя пограничного сервера в этом пуле.</span><span class="sxs-lookup"><span data-stu-id="5fa57-235">In this example, Site1 is the site containing the Edge pool which will now host the XMPP federation route, and EdgeServer1.contoso.com is the FQDN of an Edge Server in that pool.</span></span>
    
      - <span data-ttu-id="5fa57-p133">Если у вас пока нет записи DNS SRV для федерации XMPP, которая разрешается в пограничный пул, где будет размещаться федерация XMPP, вы должны добавить ее, как указано в следующем примере. Для этой записи SRV необходимо указать значение порта 5269.</span><span class="sxs-lookup"><span data-stu-id="5fa57-p133">If you do not already have a DNS SRV record for XMPP federation which resolves to the Edge pool which will now host XMPP federation, you must add it, as in the following example. This SRV record must have a port value of 5269.</span></span>
        
            _xmpp-server._tcp.contoso.com
    
      - <span data-ttu-id="5fa57-238">На внешнем DNS-сервере измените запись DNS A для федерации XMPP таким образом, чтобы она указывала на EdgeServer2.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="5fa57-238">On the external DNS server, change the DNS A record for XMPP federation to point to EdgeServer2.contoso.com.</span></span>
    
      - <span data-ttu-id="5fa57-239">Убедитесь, что порт 5269 пограничного пула, в котором теперь будет размещаться федерация XMPP, открыт на внешнем уровне.</span><span class="sxs-lookup"><span data-stu-id="5fa57-239">Verify that the Edge pool which will now host XMPP federation has port 5269 open externally.</span></span>

4.  <span data-ttu-id="5fa57-240">Если пулы переднего края по-прежнему работают на сайте, содержаном сбойного пула и восстановленном, следует обновить службу веб-служб и службу A/V Conferencing в этих пулах переднего края, чтобы снова использовать пулы edge на локальном сайте.</span><span class="sxs-lookup"><span data-stu-id="5fa57-240">If the Front End pools remained running in the site containing the Edge pool that failed and has been restored, you should update the Web Conferencing Service and A/V Conferencing Service on these Front End pools to again use the Edge pools at their local site.</span></span>

5.  <span data-ttu-id="5fa57-241">Если происходит сбой пула переднего плана на том же сайте, где располагается отказавший пограничный пул, можно использовать Invoke–CsPoolFailback для восстановления пула переднего плана.</span><span class="sxs-lookup"><span data-stu-id="5fa57-241">If the Front End pool at the same site as the failed Edge pool also failed, you can now use Invoke–CsPoolFailback to fail back the Front End pool.</span></span>


## <a name="change-the-edge-pool-associated-with-a-front-end-pool"></a><span data-ttu-id="5fa57-242">Изменение пула, связанного с пулом переднего края</span><span class="sxs-lookup"><span data-stu-id="5fa57-242">Change the Edge pool associated with a Front End pool</span></span>

<span data-ttu-id="5fa57-243">Если пограничный пул отключается, однако интерфейсный пул все еще работает, необходимо указать для интерфейсного пула использование пограничного пула в другом сайте, пока не будет восстановлена работоспособность сбойного пограничного пула.</span><span class="sxs-lookup"><span data-stu-id="5fa57-243">If an Edge pool goes down but the Front End pool at the same site is still running, you will need to set the Front End pool to use an Edge pool at a different site until the failed Edge pool is restored.</span></span>

1.  <span data-ttu-id="5fa57-244">В построителе топологий перейдите к имени интерфейсного пула, который необходимо изменить.</span><span class="sxs-lookup"><span data-stu-id="5fa57-244">In Topology Builder, navigate to the name of the Front End pool you need to change.</span></span>

2.  <span data-ttu-id="5fa57-245">Щелкните пул правой кнопкой мыши и выберите **"Изменить свойства".**</span><span class="sxs-lookup"><span data-stu-id="5fa57-245">Right-click the pool, and then select **Edit Properties**.</span></span>

3.  <span data-ttu-id="5fa57-246">В разделе **Связи** под надписью **Сопоставить пограничный пул (для компонентов мультимедиа)** используйте раскрывающееся поле для выбора пограничного пула, с которым следует сопоставить интерфейсный пул.</span><span class="sxs-lookup"><span data-stu-id="5fa57-246">In the **Associations** section, under **Associate Edge Pool (for media components)**, use the drop down box to select the Edge pool you want to associate this Front End pool with.</span></span>

4.  <span data-ttu-id="5fa57-247">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="5fa57-247">Select **OK**.</span></span>
