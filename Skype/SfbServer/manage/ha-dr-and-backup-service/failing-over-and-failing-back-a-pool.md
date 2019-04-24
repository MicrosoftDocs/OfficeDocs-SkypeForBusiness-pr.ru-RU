---
title: Отработка отказа для пула
ms.reviewer: ''
author: heidip
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: .
ms.openlocfilehash: 809d0305eaa4c8e2197c5137a647ff9354cbf9bd
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "32197802"
---
# <a name="failing-over-and-failing-back-a-pool-in-skype-for-business-server"></a><span data-ttu-id="5b9c5-103">Сбоя свыше и после неудачной пула в Скайп для Business Server</span><span class="sxs-lookup"><span data-stu-id="5b9c5-103">Failing over and failing back a pool in Skype for Business Server</span></span> 

<span data-ttu-id="5b9c5-104">Используйте следующую процедуру, если не удалось выполнить один пул переднего плана и потребностей неисправный или пула, в котором возникла аварийная оперативный и требуется для восстановления обычного рабочего состояния развертывания.</span><span class="sxs-lookup"><span data-stu-id="5b9c5-104">Use the following procedures if a single Front End pool has failed and needs to be failed over, or the pool that experienced the disaster is back online and you need to restore your deployment to regular working status.</span></span> <span data-ttu-id="5b9c5-105">Также узнайте, как выполнить отработку отказа отказа и восстановления размещения пула пограничного сервера, используемого для Скайп для бизнеса федерации или федерации XMPP, или измените пограничного пула, связанного с пулом переднего плана.</span><span class="sxs-lookup"><span data-stu-id="5b9c5-105">Also  learn how to fail over and fail back the Edge pool used for Skype for Business federation or XMPP federation, or change the Edge pool associated with a Front End pool.</span></span>

- [<span data-ttu-id="5b9c5-106">Отработки отказа пула переднего плана</span><span class="sxs-lookup"><span data-stu-id="5b9c5-106">Fail over a Front End pool</span></span>](#fail-over-a-front-end-pool)
- [<span data-ttu-id="5b9c5-107">Восстановление после сбоя пула</span><span class="sxs-lookup"><span data-stu-id="5b9c5-107">Fail back a pool</span></span>](#fail-back-a-pool)
- [<span data-ttu-id="5b9c5-108">Отработки отказа пограничного пула, используемого для Скайп для сервера федерации</span><span class="sxs-lookup"><span data-stu-id="5b9c5-108">Fail over the Edge pool used for Skype for Business Server federation</span></span>](#fail-over-the-edge-pool-used-for-skype-for-business-server-federation)
- [<span data-ttu-id="5b9c5-109">Отработки отказа пограничного пула, используемого для федерации XMPP в Скайп для Business Server</span><span class="sxs-lookup"><span data-stu-id="5b9c5-109">Fail over the Edge pool used for XMPP federation in Skype for Business Server</span></span>](#fail-over-the-edge-pool-used-for-xmpp-federation-in-skype-for-business-server)
- [<span data-ttu-id="5b9c5-110">Восстановление после сбоя пограничного пула, используемого для Скайп для федерации Business Server или федерации XMPP</span><span class="sxs-lookup"><span data-stu-id="5b9c5-110">Fail back the Edge pool used for Skype for Business Server federation or XMPP federation</span></span>](#fail-back-the-edge-pool-used-for-skype-for-business-server-federation-or-xmpp-federation)
- [<span data-ttu-id="5b9c5-111">Изменение пограничного пула, связанного с пулом переднего плана</span><span class="sxs-lookup"><span data-stu-id="5b9c5-111">Change the Edge pool associated with a Front End pool</span></span>](#change-the-edge-pool-associated-with-a-front-end-pool)

## <a name="fail-over-a-front-end-pool"></a><span data-ttu-id="5b9c5-112">Отработки отказа пула переднего плана</span><span class="sxs-lookup"><span data-stu-id="5b9c5-112">Fail over a Front End pool</span></span>

<span data-ttu-id="5b9c5-113">В этой процедуре Datacenter1 содержит пула Pool1 и пула Pool1 завершен с ошибкой.</span><span class="sxs-lookup"><span data-stu-id="5b9c5-113">In this procedure, Datacenter1 contains Pool1, and Pool1 has failed.</span></span> <span data-ttu-id="5b9c5-114">Необходимо переключиться в пул Pool2, расположенный в Datacenter2.</span><span class="sxs-lookup"><span data-stu-id="5b9c5-114">You are failing over to Pool2 located in Datacenter2.</span></span>

<span data-ttu-id="5b9c5-115">Большая часть работы для отработки отказа пула включает в себя отработки центрального хранилища управления, если это необходимо.</span><span class="sxs-lookup"><span data-stu-id="5b9c5-115">Most of the work for the pool failover involves failing over the Central Management store, if it is required.</span></span> <span data-ttu-id="5b9c5-116">Это важно, так как центральное хранилище управления должно функционировать при сбое пользователей пула.</span><span class="sxs-lookup"><span data-stu-id="5b9c5-116">This is important because the Central Management store must be functional when the pool’s users are failed over.</span></span>

<span data-ttu-id="5b9c5-117">Кроме того Если происходит сбой пула переднего плана, но по-прежнему работает пограничный пул на этом сайте, необходимо знать, используется ли пул пограничного пула, сбой которого как пул следующих прыжков.</span><span class="sxs-lookup"><span data-stu-id="5b9c5-117">Additionally, if a Front End pool fails but the Edge pool at that site is still running, you must know whether the Edge pool uses the failed pool as a next hop pool.</span></span> <span data-ttu-id="5b9c5-118">В этом случае необходимо изменить пограничный пул для использования в другой пул переднего плана до сбоя через сбоя пула переднего плана.</span><span class="sxs-lookup"><span data-stu-id="5b9c5-118">If it does, you must change the Edge pool to use a different Front End pool before failing over the failed Front End pool.</span></span> <span data-ttu-id="5b9c5-119">Как изменить параметр следующего прыжка зависит от ли использование пограничного пула на том же сайте пограничный пул или другой сайт.</span><span class="sxs-lookup"><span data-stu-id="5b9c5-119">How you change the next hop setting depends on whether the Edge will use a pool at the same site as the Edge pool, or a different site.</span></span>

<span data-ttu-id="5b9c5-120">**Чтобы установить пограничный пул на использование пула следующего перехода на том же сайте**</span><span class="sxs-lookup"><span data-stu-id="5b9c5-120">**To set an Edge pool to use a next hop pool at the same site**</span></span>

1.  <span data-ttu-id="5b9c5-121">Откройте построитель топологий, щелкните правой кнопкой мыши пограничный пул, который необходимо изменить и выберите команду **Изменить свойства**.</span><span class="sxs-lookup"><span data-stu-id="5b9c5-121">Open Topology Builder, right-click the Edge pool that needs to be changed, and click **Edit Properties**.</span></span>

2.  <span data-ttu-id="5b9c5-122">Нажмите кнопку **следующего прыжка**.</span><span class="sxs-lookup"><span data-stu-id="5b9c5-122">Click **Next Hop**.</span></span> <span data-ttu-id="5b9c5-123">Из **следующего прыжка пула:** выберите пул, в котором теперь будет использован как пул следующих прыжков.</span><span class="sxs-lookup"><span data-stu-id="5b9c5-123">From the **Next hop pool:** list, select the pool which will now serve as the next hop pool.</span></span>

3.  <span data-ttu-id="5b9c5-124">Нажмите **кнопку ОК**, а затем опубликуйте изменения.</span><span class="sxs-lookup"><span data-stu-id="5b9c5-124">Click **OK**, and then publish the changes.</span></span>

<span data-ttu-id="5b9c5-125">**Чтобы установить пограничный пул на использование пула следующего перехода на другой сайт**</span><span class="sxs-lookup"><span data-stu-id="5b9c5-125">**To set an Edge pool to use a next hop pool at a different site**</span></span>

1.  <span data-ttu-id="5b9c5-126">Откройте Скайп для окна консоли Business Server и введите следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="5b9c5-126">Open a Skype for Business Server Management Shell window and type the following cmdlet:</span></span>
    
        Set-CsEdgeServer -Identity EdgeServer:<Edge Server pool FQDN> -Registrar Registrar:<NextHopPoolFQDN>

<span data-ttu-id="5b9c5-127">**Чтобы обойти пул, в случае аварии**</span><span class="sxs-lookup"><span data-stu-id="5b9c5-127">**To fail over a pool in a disaster**</span></span>

1.  <span data-ttu-id="5b9c5-128">Узнать, какой пул узла для сервера централизованного управления, введя на сервере переднего плана в пуле Pool2 следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="5b9c5-128">Find which pool is the host for the Central Management Server by typing the following cmdlet on a Front End server in Pool2:</span></span>
    
        Invoke-CsManagementServerFailover -Whatif
    
    <span data-ttu-id="5b9c5-129">Результаты Показать этот командлет, какой пул в настоящее время размещается центральный сервер управления.</span><span class="sxs-lookup"><span data-stu-id="5b9c5-129">The results of this cmdlet show which pool currently hosts the Central Management Server.</span></span> <span data-ttu-id="5b9c5-130">В оставшейся части этой процедуры этот пул называется CMS\_пула.</span><span class="sxs-lookup"><span data-stu-id="5b9c5-130">In the rest of this procedure, this pool is known as CMS\_Pool.</span></span>

2.  <span data-ttu-id="5b9c5-131">Используйте построитель топологий для поиска версии Скайп Business Server, запущенные на CMS\_пула.</span><span class="sxs-lookup"><span data-stu-id="5b9c5-131">Use Topology Builder to find the version of Skype for Business Server running on the CMS\_Pool.</span></span> <span data-ttu-id="5b9c5-132">Если он выполняется Скайп для сервера, используйте следующий командлет для поиска в резервный пул пула 1.</span><span class="sxs-lookup"><span data-stu-id="5b9c5-132">If it is running Skype for Business Server, use the following cmdlet to find the backup pool of Pool 1.</span></span>
    
        Get-CsPoolBackupRelationship -PoolFQDN <CMS_Pool FQDN>
    
    <span data-ttu-id="5b9c5-133">Программа резервного копирования\_пула будет пул.</span><span class="sxs-lookup"><span data-stu-id="5b9c5-133">Let Backup\_Pool be the backup pool.</span></span>

3.  <span data-ttu-id="5b9c5-134">Проверьте состояние центрального хранилища управления с помощью следующего командлета:</span><span class="sxs-lookup"><span data-stu-id="5b9c5-134">Check the status of the Central Management store with the following cmdlet:</span></span>
    
        Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
    
    <span data-ttu-id="5b9c5-135">Этот командлет необходимо показать, что указывает указывают ли ActiveMasterFQDN и ActiveFileTransferAgents на полное доменное имя CMS\_пула.</span><span class="sxs-lookup"><span data-stu-id="5b9c5-135">This cmdlet should show that both ActiveMasterFQDN and ActiveFileTransferAgents are pointing to the FQDN of CMS\_Pool.</span></span> <span data-ttu-id="5b9c5-136">Если они являются пустыми, центральный сервер управления недоступен и его необходимо отработки отказа.</span><span class="sxs-lookup"><span data-stu-id="5b9c5-136">If they are empty, the Central Management Server is not available and you must fail it over.</span></span>

4.  <span data-ttu-id="5b9c5-137">Если центральное хранилище управления недоступен или если центральное хранилище управления работала в пуле Pool1 (то есть пула, в котором не удалось выполнить), необходимо отработки отказа центральный сервер управления перед отработка отказа для пула.</span><span class="sxs-lookup"><span data-stu-id="5b9c5-137">If the Central Management store is not available or if the Central Management store was running on Pool1 (that is, the pool that has failed), you must fail over the Central Management Server before failing over the pool.</span></span> <span data-ttu-id="5b9c5-138">Если вам потребуется выполнить отработку отказа сервера централизованного управления, который размещен в пуле, выполнив Скайп для Business Server, командлет на шаге 5 данной процедуры.</span><span class="sxs-lookup"><span data-stu-id="5b9c5-138">If you need to fail over the Central Management Server that was hosted on a pool running Skype for Business Server, use the cmdlet in step 5 of this procedure.</span></span> <span data-ttu-id="5b9c5-139">Если не требуется выполнить отработку отказа сервера централизованного управления, перейдите к действию 7 этой процедуры.</span><span class="sxs-lookup"><span data-stu-id="5b9c5-139">If you do not need to fail over the Central Management Server, skip to step 7 of this procedure.</span></span>

5.  <span data-ttu-id="5b9c5-140">Отработки отказа хранилища в пуле, выполнив Скайп для Business Server, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="5b9c5-140">To fail over the Central Management store on a pool running Skype for Business Server, do the following:</span></span>
    
      - <span data-ttu-id="5b9c5-141">Для начала проверьте какие Тыловой сервер в резервной копии\_пул работает экземпляр-субъект из центрального хранилища управления, введя следующее:</span><span class="sxs-lookup"><span data-stu-id="5b9c5-141">First, check which Back End Server in Backup\_Pool runs the principal instance of the Central Management store by typing the following:</span></span>
        
            Get-CsDatabaseMirrorState -DatabaseType Centralmgmt -PoolFqdn <Backup_Pool Fqdn>
    
      - <span data-ttu-id="5b9c5-142">Если Тыловой сервер в резервной копии\_пула — это тип субъекта,:</span><span class="sxs-lookup"><span data-stu-id="5b9c5-142">If the primary Back End Server in Backup\_Pool is the principal, type:</span></span>
        
            Invoke-CSManagementServerFailover -BackupSQLServerFqdn <Backup_Pool Primary BackEnd Server FQDN> -BackupSQLInstanceName <Backup_Pool Primary SQL Instance Name>
        
        <span data-ttu-id="5b9c5-143">Если зеркальный Тыловой сервер в резервной копии\_пула — это тип субъекта,:</span><span class="sxs-lookup"><span data-stu-id="5b9c5-143">If the mirror Back End Server in Backup\_Pool is the principal, type:</span></span>
        
            Invoke-CSManagementServerFailover -MirrorSQLServerFqdn <Backup_Pool Mirror BackEnd Server FQDN> -MirrorSQLInstanceName <Backup_Pool Mirror SQL Instance Name>
    
      - <span data-ttu-id="5b9c5-144">Проверьте, что отработки отказа сервера централизованного управления завершен.</span><span class="sxs-lookup"><span data-stu-id="5b9c5-144">Validate that the Central Management Server failover is complete.</span></span> <span data-ttu-id="5b9c5-145">Введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="5b9c5-145">Type the following:</span></span>
        
            Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
        
        <span data-ttu-id="5b9c5-146">Проверьте, что указывает указывают ли ActiveMasterFQDN и ActiveFileTransferAgents на полное доменное имя резервного копирования\_пула.</span><span class="sxs-lookup"><span data-stu-id="5b9c5-146">Check that both ActiveMasterFQDN and ActiveFileTransferAgents are pointing to the FQDN of Backup\_Pool.</span></span>
    
      - <span data-ttu-id="5b9c5-147">И, наконец Проверьте состояние реплики для всех серверов переднего плана, введя следующую команду:</span><span class="sxs-lookup"><span data-stu-id="5b9c5-147">Finally, check the replica status for all Front End Servers by typing the following:</span></span>
        
            Get-CsManagementStoreReplicationStatus 
        
        <span data-ttu-id="5b9c5-148">Проверьте, что все реплики имеют значение True.</span><span class="sxs-lookup"><span data-stu-id="5b9c5-148">Check that all replicas have a value of True.</span></span>
        
        <span data-ttu-id="5b9c5-149">Перейдите к действию 7 этой процедуры.</span><span class="sxs-lookup"><span data-stu-id="5b9c5-149">Skip to step 7 in this procedure.</span></span>

6.  <span data-ttu-id="5b9c5-150">Установите центральное хранилище управления на обратно End Server из резервной копии\_пула.</span><span class="sxs-lookup"><span data-stu-id="5b9c5-150">Install the Central Management store on the Back End Server of Backup\_Pool.</span></span>
    
      - <span data-ttu-id="5b9c5-151">Во-первых выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="5b9c5-151">First, run the following command:</span></span>
        
        ``` 
        Install-CsDatabase -CentralManagementDatabase -Clean -SqlServerFqdn <Backup_Pool Back End Server FQDN> -SqlInstanceName rtc  
        ```
    
      - <span data-ttu-id="5b9c5-152">Выполните следующую команду на одном из сервера переднего плана серверы из резервной копии\_пула, чтобы переместить центральное хранилище управления:</span><span class="sxs-lookup"><span data-stu-id="5b9c5-152">Run the next command on one of the Front End Servers of Backup\_Pool to force the move of the Central Management store:</span></span>
        
            Move-CsManagementServer -ConfigurationFileName c:\CsConfigurationFile.zip -LisConfigurationFileName c:\CsLisConfigurationFile.zip -Force 
    
      - <span data-ttu-id="5b9c5-153">Проверка ли перемещение:</span><span class="sxs-lookup"><span data-stu-id="5b9c5-153">Validate the move is complete:</span></span>
        
            Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
        
        <span data-ttu-id="5b9c5-154">Проверьте, что указывает указывают ли ActiveMasterFQDN и ActiveFileTransferAgents на полное доменное имя резервного копирования\_пула.</span><span class="sxs-lookup"><span data-stu-id="5b9c5-154">Check that both ActiveMasterFQDN and ActiveFileTransferAgents are pointing to the FQDN of Backup\_Pool.</span></span>
    
      - <span data-ttu-id="5b9c5-155">Проверьте состояние реплики для всех серверов переднего плана, введя следующую команду:</span><span class="sxs-lookup"><span data-stu-id="5b9c5-155">Check the replica status for all Front End Servers by typing the following:</span></span>
        
            Get-CsManagementStoreReplicationStatus 
        
        <span data-ttu-id="5b9c5-156">Проверьте, что все реплики имеют значение True.</span><span class="sxs-lookup"><span data-stu-id="5b9c5-156">Check that all replicas have a value of True.</span></span>
    
      - <span data-ttu-id="5b9c5-157">Установите службу сервера централизованного управления на остальных серверов переднего плана в резервной копии\_пула.</span><span class="sxs-lookup"><span data-stu-id="5b9c5-157">Install the Central Management Server service on the rest of the Front End Servers in Backup\_Pool.</span></span> <span data-ttu-id="5b9c5-158">Для этого выполните следующую команду на всех серверах переднего плана, за исключением того, под которыми принудительным централизованного управления хранилища перемещение ранее в этой процедуре:</span><span class="sxs-lookup"><span data-stu-id="5b9c5-158">To do so, run the following command on all the Front End Servers, except the one you used when forcing the Central Management store move earlier in this procedure:</span></span>
        
            Bootstrapper /Setup 

7.  <span data-ttu-id="5b9c5-159">Переведите пользователей из пула Pool1 в пул Pool2, выполнив следующий командлет в Скайп для окна консоли Business Server:</span><span class="sxs-lookup"><span data-stu-id="5b9c5-159">Fail over the users from Pool1 to Pool2 by running the following cmdlet in a Skype for Business Server Management Shell window:</span></span>
    
        Invoke-CsPoolFailover -PoolFQDN <Pool1 FQDN> -DisasterMode -Verbose
    
    <span data-ttu-id="5b9c5-160">Поскольку действия, предпринимаемые в предыдущей части этой процедуры, чтобы проверить состояние хранилища централизованного управления не универсальные, по-прежнему возможность этот командлет не так, как центральное хранилище управления — это не еще при сбое полностью.</span><span class="sxs-lookup"><span data-stu-id="5b9c5-160">Because the steps taken in the previous parts of this procedure to check the Central Management store status are not universal, there is still a chance this cmdlet will fail because the Central Management store is not yet fully failed over.</span></span> <span data-ttu-id="5b9c5-161">В этом случае необходимо исправить центральное хранилище управления сообщения об ошибках, отображаемые на основании и затем снова запустите этот командлет.</span><span class="sxs-lookup"><span data-stu-id="5b9c5-161">In this case, you must fix the Central Management store based on the error messages that you see, and then run this cmdlet again.</span></span>
    
    <span data-ttu-id="5b9c5-162">Если появится следующее сообщение об ошибке, необходимо изменить пограничный пул на этом сайте для использования в другой пул в качестве его следующего прыжка до сбоя отказа пула.</span><span class="sxs-lookup"><span data-stu-id="5b9c5-162">If you see the following error message, then you need to change the Edge pool at this site to use a different pool as its next hop before failing over the pool.</span></span> <span data-ttu-id="5b9c5-163">Дополнительные сведения см процедуры, описанные в начале этого раздела.</span><span class="sxs-lookup"><span data-stu-id="5b9c5-163">For details, see the procedures at the beginning of this topic.</span></span>
    
        Invoke-CsPoolFailOver : This Front-end pool "pool1.contoso.com" is specified in
        topology as the next hop for the Edge server. Failing over this pool may cause External
        access/Federation/Split-domain/XMPP features to stop working. Please use Topology Builder to
        change the Edge internal next hop setting to point to a different Front-end pool,  before you
        proceed.


## <a name="fail-back-a-pool"></a><span data-ttu-id="5b9c5-164">Восстановление после сбоя пула</span><span class="sxs-lookup"><span data-stu-id="5b9c5-164">Fail back a pool</span></span>

<span data-ttu-id="5b9c5-165">После пула, в котором возникла аварийная оперативный (то есть пула Pool1 в этом примере), выполните следующие действия для восстановления обычного рабочего состояния развертывания.</span><span class="sxs-lookup"><span data-stu-id="5b9c5-165">After the pool that experienced the disaster is back online (that is, Pool1 in this example), take the following steps to restore your deployment to regular working status.</span></span>

<span data-ttu-id="5b9c5-166">Обратите внимание, что процесс восстановления размещения занимает несколько минут для выполнения.</span><span class="sxs-lookup"><span data-stu-id="5b9c5-166">Note that the failback process takes several minute to complete.</span></span><span data-ttu-id="5b9c5-167">Следует исходить из длительности 60 минут для пула, в котором работает 20 000 пользователей.</span><span class="sxs-lookup"><span data-stu-id="5b9c5-167">  For reference, it is expected to take up to 60 minutes for a pool of 20,000 users.</span></span>

<span data-ttu-id="5b9c5-168">Восстановите размещение пользователей, которые изначально размещались в пуле Pool1 и были переключены на пул Pool2, выполнив следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="5b9c5-168">Fail back the users who were originally homed in Pool1 and have been failed over to Pool2 by typing the following cmdlet:</span></span>
    
    Invoke-CsPoolFailback -PoolFQDN <Pool1 FQDN> -Verbose

<span data-ttu-id="5b9c5-169">Никакие другие действия не требуется.</span><span class="sxs-lookup"><span data-stu-id="5b9c5-169">No other steps are necessary.</span></span> <span data-ttu-id="5b9c5-170">При сбое центральный сервер управления можно оставить его в пул Pool2.</span><span class="sxs-lookup"><span data-stu-id="5b9c5-170">If you failed over the Central Management Server, you can leave it in Pool2.</span></span>

## <a name="fail-over-the-edge-pool-used-for-skype-for-business-server-federation"></a><span data-ttu-id="5b9c5-171">Отработки отказа пограничного пула, используемого для Скайп для сервера федерации</span><span class="sxs-lookup"><span data-stu-id="5b9c5-171">Fail over the Edge pool used for Skype for Business Server federation</span></span> 

<span data-ttu-id="5b9c5-172">Если пограничный пул, где у вас есть Скайп для настройки федерации Business Server отключается, необходимо изменить федерацию для использования в другой пул пограничного сервера для федерации для работы.</span><span class="sxs-lookup"><span data-stu-id="5b9c5-172">If the Edge pool where you have Skype for Business Server federation configured goes down, you must change federation to use a different Edge pool for federation to work.</span></span>

1.  <span data-ttu-id="5b9c5-173">На сервере переднего плана откройте построитель топологий.</span><span class="sxs-lookup"><span data-stu-id="5b9c5-173">On a Front End server, open Topology Builder.</span></span> <span data-ttu-id="5b9c5-174">Разверните узел **пограничные пулы**и щелкните правой кнопкой мыши пограничного сервера или пула пограничных серверов, которые в настоящее время настроены для федерации.</span><span class="sxs-lookup"><span data-stu-id="5b9c5-174">Expand **Edge pools**, and then right-click the Edge server or Edge server pool that is currently configured for Federation.</span></span> <span data-ttu-id="5b9c5-175">Выберите команду **Изменить свойства**.</span><span class="sxs-lookup"><span data-stu-id="5b9c5-175">Select **Edit properties**.</span></span>

2.  <span data-ttu-id="5b9c5-176">В окне **Изменение свойств** на вкладке **Общие**снимите флажок **Включение федерации для этого пограничного пула (порт 5061)**.</span><span class="sxs-lookup"><span data-stu-id="5b9c5-176">In **Edit Properties** under **General**, clear **Enable federation for this Edge pool (Port 5061)**.</span></span> <span data-ttu-id="5b9c5-177">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="5b9c5-177">Click **OK**.</span></span>

3.  <span data-ttu-id="5b9c5-178">Разверните узел **пограничные пулы**и щелкните правой кнопкой мыши пограничного сервера или пула пограничных серверов, теперь необходимо использовать для федерации.</span><span class="sxs-lookup"><span data-stu-id="5b9c5-178">Expand **Edge pools**, and then right-click the Edge server or Edge server pool that you now want to use for Federation.</span></span> <span data-ttu-id="5b9c5-179">Выберите команду **Изменить свойства**.</span><span class="sxs-lookup"><span data-stu-id="5b9c5-179">Select **Edit properties**.</span></span>

4.  <span data-ttu-id="5b9c5-180">В окне **Изменение свойств** на вкладке **Общие**выберите **Включение федерации для этого пограничного пула (порт 5061)**.</span><span class="sxs-lookup"><span data-stu-id="5b9c5-180">In **Edit Properties** under **General**, select **Enable federation for this Edge pool (Port 5061)**.</span></span> <span data-ttu-id="5b9c5-181">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="5b9c5-181">Click **OK**.</span></span>

5.  <span data-ttu-id="5b9c5-182">Выберите в меню **Действие**выберите **топологии**, выберите **Опубликовать**.</span><span class="sxs-lookup"><span data-stu-id="5b9c5-182">Click **Action**, select **Topology**, select **Publish**.</span></span> <span data-ttu-id="5b9c5-183">При появлении запроса на **опубликовать топологию**, нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="5b9c5-183">When prompted on **Publish the topology**, click **Next**.</span></span> <span data-ttu-id="5b9c5-184">После публикации нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="5b9c5-184">When the Publish is finished, click **Finish**.</span></span>

6.  <span data-ttu-id="5b9c5-185">На пограничном сервере откройте Скайп для мастера развертывания Business Server.</span><span class="sxs-lookup"><span data-stu-id="5b9c5-185">On the Edge server, open the Skype for Business Server Deployment wizard.</span></span> <span data-ttu-id="5b9c5-186">Выберите **установить или обновление Скайп для бизнес-системы сервера**и нажмите кнопку **программы установки или удаления Скайп для бизнеса серверных компонентов**.</span><span class="sxs-lookup"><span data-stu-id="5b9c5-186">Click **Install or Update Skype for Business Server System**, and then click **Setup or Remove Skype for Business Server Components**.</span></span> <span data-ttu-id="5b9c5-187">Нажмите кнопку **выполнить еще раз**.</span><span class="sxs-lookup"><span data-stu-id="5b9c5-187">Click **Run Again**.</span></span>

7.  <span data-ttu-id="5b9c5-188">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="5b9c5-188">Click **Next**.</span></span> <span data-ttu-id="5b9c5-189">Сводный экран будет отображаться действия, как они выполняются.</span><span class="sxs-lookup"><span data-stu-id="5b9c5-189">The summary screen will show actions as they are executed.</span></span> <span data-ttu-id="5b9c5-190">После завершения развертывания нажмите кнопку **Просмотреть журнал** , чтобы просмотреть доступные файлы журналов.</span><span class="sxs-lookup"><span data-stu-id="5b9c5-190">Once the deployment is done, click **View Log** to view available log files.</span></span> <span data-ttu-id="5b9c5-191">Нажмите кнопку **Готово** для завершения развертывания.</span><span class="sxs-lookup"><span data-stu-id="5b9c5-191">Click **Finish** to complete the deployment.</span></span>
    
    <span data-ttu-id="5b9c5-192">Если сайт, содержащий пограничный пул содержит серверов переднего плана, по-прежнему работает, необходимо обновить служба веб-конференций и A / V конференц-связи на этих пулов переднего плана для использования службой пограничный пул в удаленной сайтов, по-прежнему выполнения.</span><span class="sxs-lookup"><span data-stu-id="5b9c5-192">If the site containing the failed Edge pool contains Front End Servers that are still running, you must update the Web Conferencing Service and A/V Conferencing Service on these Front End pools to use an Edge pool in a remote site that is still running.</span></span> 

 ## <a name="fail-over-the-edge-pool-used-for-xmpp-federation-in-skype-for-business-server"></a><span data-ttu-id="5b9c5-193">Отработки отказа пограничного пула, используемого для федерации XMPP в Скайп для Business Server</span><span class="sxs-lookup"><span data-stu-id="5b9c5-193">Fail over the Edge pool used for XMPP federation in Skype for Business Server</span></span> 

<span data-ttu-id="5b9c5-194">В вашей организации есть один пограничного пула, определенного как пул для федерации XMPP.</span><span class="sxs-lookup"><span data-stu-id="5b9c5-194">In your organization, there is one Edge pool designated as the pool to use for XMPP federation.</span></span> <span data-ttu-id="5b9c5-195">Если этот пул отключается, необходимо отработки отказа федерации XMPP для использования другого пограничного пула, перед федерации XMPP может работать еще раз.</span><span class="sxs-lookup"><span data-stu-id="5b9c5-195">If this pool goes down, you must fail over XMPP federation to use a different Edge pool before XMPP federation can work again.</span></span>

<span data-ttu-id="5b9c5-196">При первой установке пограничные пулы и включить федерацию XMPP, можно упростить процесс аварийного восстановления, Настройка внешнего DNS SRV-записи для всех пулов пограничного сервера для федерации XMPP, а не только один.</span><span class="sxs-lookup"><span data-stu-id="5b9c5-196">When you first install Edge pools and enable XMPP Federation, you can simplify the disaster recovery process by setting up external DNS SRV records for all of your Edge pools for XMPP federation, instead of just one.</span></span> <span data-ttu-id="5b9c5-197">Каждый из этих SRV-записи необходимо задать другой приоритет.</span><span class="sxs-lookup"><span data-stu-id="5b9c5-197">Each of these SRV records must have a different priority set.</span></span> <span data-ttu-id="5b9c5-198">Весь трафик федерации XMPP проходит через пул с SRV-записи с наивысшим приоритетом.</span><span class="sxs-lookup"><span data-stu-id="5b9c5-198">All XMPP federation traffic goes through the pool with the SRV record with the highest priority.</span></span> 

<span data-ttu-id="5b9c5-199">В следующей процедуре EdgePool1 — это пул, в котором изначально размещена федерация XMPP, а EdgePool2 — пул, в котором теперь будет размещаться федерация XMPP.</span><span class="sxs-lookup"><span data-stu-id="5b9c5-199">In the following procedure, EdgePool1 is the pool which originally hosted XMPP federation, and EdgePool2 is the pool which will now host XMPP federation.</span></span>


### <a name="to-fail-over-the-edge-pool-used-for-xmpp-federation"></a><span data-ttu-id="5b9c5-200">Чтобы выполнить отработку отказа пограничного пула, используемого для федерации XMPP</span><span class="sxs-lookup"><span data-stu-id="5b9c5-200">To fail over the Edge pool used for XMPP federation</span></span>

1.  <span data-ttu-id="5b9c5-201">Если у вас еще нет другого пограничного пула, развернут (Кроме того, который в данный момент не работает), развертывание этого пула.</span><span class="sxs-lookup"><span data-stu-id="5b9c5-201">If you don’t already have another Edge pool deployed (besides the one which is currently down), deploy that pool.</span></span> 

2.  <span data-ttu-id="5b9c5-202">На каждом пограничном сервере в новый пул пограничного сервера, в котором теперь будет размещаться федерация XMPP (EdgePool2) запустите следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="5b9c5-202">On each Edge Server in the new Edge pool which will now host XMPP federation (EdgePool2), run the following cmdlet:</span></span>
    
        Stop-CsWindowsService

3.  <span data-ttu-id="5b9c5-203">Выполните следующий командлет, чтобы повторно указать маршрут федерации XMPP на сервер EdgePool2:</span><span class="sxs-lookup"><span data-stu-id="5b9c5-203">Run the following cmdlet to repoint the XMPP federation route to EdgePool2:</span></span>
    
        Set-CsSite Site2 -XmppExternalFederationRoute EdgeServer2.contoso.com
    
    <span data-ttu-id="5b9c5-204">В этом примере Site2 — это сайт, содержащий пограничного пула, в котором теперь будет размещаться маршрут федерации XMPP и EdgeServer2.contoso.com — это полное доменное имя пограничного сервера в этом пуле.</span><span class="sxs-lookup"><span data-stu-id="5b9c5-204">In this example, Site2 is the site containing the Edge pool which will now host the XMPP federation route, and EdgeServer2.contoso.com is the FQDN of an Edge Server in that pool.</span></span>

4.  <span data-ttu-id="5b9c5-205">На внешнем DNS-сервере измените запись DNS A для федерации XMPP, чтобы она указывала на EdgeServer2.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="5b9c5-205">On the external DNS server, change the DNS A record for XMPP federation to point to EdgeServer2.contoso.com.</span></span>

5.  <span data-ttu-id="5b9c5-206">Если вы уже нет DNS-записи SRV для федерации XMPP, которая разрешается в пограничный пул, в котором теперь будет размещаться федерация XMPP, необходимо добавить его, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="5b9c5-206">If you do not already have a DNS SRV record for XMPP federation which resolves to the Edge pool which will now host XMPP federation, you must add it, as in the following example.</span></span> <span data-ttu-id="5b9c5-207">Эта запись SRV должен иметь значение порт 5269.</span><span class="sxs-lookup"><span data-stu-id="5b9c5-207">This SRV record must have a port value of 5269.</span></span>
    
        _xmpp-server._tcp.contoso.com

6.  <span data-ttu-id="5b9c5-208">Убедитесь, что для пограничного пула, в котором теперь будет размещаться федерация XMPP открыт порт 5269 извне.</span><span class="sxs-lookup"><span data-stu-id="5b9c5-208">Verify that the Edge pool which will now host XMPP federation has port 5269 open externally.</span></span>

7.  <span data-ttu-id="5b9c5-209">Запустите службы на всех пограничных серверов в пограничном пуле, в котором теперь будет размещаться федерация XMPP.</span><span class="sxs-lookup"><span data-stu-id="5b9c5-209">Start the services on all Edge Servers in the Edge pool which will now host XMPP federation:</span></span>
    
        Start-CsWindowsService


## <a name="fail-back-the-edge-pool-used-for-skype-for-business-server-federation-or-xmpp-federation"></a><span data-ttu-id="5b9c5-210">Восстановление после сбоя пограничного пула, используемого для Скайп для федерации Business Server или федерации XMPP</span><span class="sxs-lookup"><span data-stu-id="5b9c5-210">Fail back the Edge pool used for Skype for Business Server federation or XMPP federation</span></span> 

<span data-ttu-id="5b9c5-211">После неудачной пограничного пула, который используется для размещения федерации оперативный обратно в оперативный режим, используйте эту процедуру для сбоя Скайп для маршрута федерации Business Server и/или маршрут федерации XMPP снова использовать этот восстановленного пограничного пула.</span><span class="sxs-lookup"><span data-stu-id="5b9c5-211">After a failed Edge pool that used to host federation has been brought back online, use this procedure to fail back the Skype for Business Server federation route and/or the XMPP federation route to again use this restored Edge pool.</span></span>

1.  <span data-ttu-id="5b9c5-212">На пограничном пуле, который снова доступен запустите службы пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="5b9c5-212">On the Edge pool that is now available again, start the Edge Services.</span></span>

2.  <span data-ttu-id="5b9c5-213">Если вы хотите восстановить Скайп для маршрута федерации Business Server для использования восстановленного пограничного сервера, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="5b9c5-213">If you want to fail back the Skype for Business Server federation route to use the restored Edge Server, do the following:</span></span>
    
      - <span data-ttu-id="5b9c5-214">На сервере переднего плана откройте построитель топологий.</span><span class="sxs-lookup"><span data-stu-id="5b9c5-214">On a Front End server, open Topology Builder.</span></span> <span data-ttu-id="5b9c5-215">Разверните узел **пограничные пулы**, а затем щелкните правой кнопкой мыши пограничного сервера или пула пограничных серверов, которые в настоящее время настроены для федерации.</span><span class="sxs-lookup"><span data-stu-id="5b9c5-215">Expand **Edge pools**, then right click the Edge server or Edge server pool that is currently configured for Federation.</span></span> <span data-ttu-id="5b9c5-216">Выберите команду **Изменить свойства**.</span><span class="sxs-lookup"><span data-stu-id="5b9c5-216">Select **Edit properties**.</span></span>
    
      - <span data-ttu-id="5b9c5-217">В окне **Изменение свойств** на вкладке **Общие**снимите флажок **Включение федерации для этого пограничного пула (порт 5061)**.</span><span class="sxs-lookup"><span data-stu-id="5b9c5-217">In **Edit Properties** under **General**, clear **Enable federation for this Edge pool (Port 5061)**.</span></span> <span data-ttu-id="5b9c5-218">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="5b9c5-218">Click **OK**.</span></span>
    
      - <span data-ttu-id="5b9c5-219">Разверните узел **пограничные пулы**, а затем щелкните правой кнопкой мыши исходный пограничного сервера или пула пограничных серверов, необходимо повторно использовать для федерации.</span><span class="sxs-lookup"><span data-stu-id="5b9c5-219">Expand **Edge pools**, then right click the original Edge server or Edge server pool that you again want to use for Federation.</span></span> <span data-ttu-id="5b9c5-220">Выберите команду **Изменить свойства**.</span><span class="sxs-lookup"><span data-stu-id="5b9c5-220">Select **Edit properties**.</span></span>
    
      - <span data-ttu-id="5b9c5-221">В окне **Изменение свойств** на вкладке **Общие**выберите **Включение федерации для этого пограничного пула (порт 5061)**.</span><span class="sxs-lookup"><span data-stu-id="5b9c5-221">In **Edit Properties** under **General**, select **Enable federation for this Edge pool (Port 5061)**.</span></span> <span data-ttu-id="5b9c5-222">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="5b9c5-222">Click **OK**.</span></span>
    
      - <span data-ttu-id="5b9c5-223">Выберите в меню **Действие**выберите **топологии**, выберите **Опубликовать**.</span><span class="sxs-lookup"><span data-stu-id="5b9c5-223">Click **Action**, select **Topology**, select **Publish**.</span></span> <span data-ttu-id="5b9c5-224">При появлении запроса на **опубликовать топологию**, нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="5b9c5-224">When prompted on **Publish the topology**, click **Next**.</span></span> <span data-ttu-id="5b9c5-225">После публикации нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="5b9c5-225">When the Publish is finished, click **Finish**.</span></span>
    
      - <span data-ttu-id="5b9c5-226">На пограничном сервере откройте Скайп для мастера развертывания Business Server.</span><span class="sxs-lookup"><span data-stu-id="5b9c5-226">On the Edge server, open the Skype for Business Server Deployment wizard.</span></span> <span data-ttu-id="5b9c5-227">Выберите **установить или обновление Скайп для бизнес-системе сервера**, а затем нажмите кнопку **программы установки или удаления Скайп для бизнеса серверных компонентов**.</span><span class="sxs-lookup"><span data-stu-id="5b9c5-227">Click **Install or Update Skype for Business Server System**, then click **Setup or Remove Skype for Business Server Components**.</span></span> <span data-ttu-id="5b9c5-228">Нажмите кнопку **выполнить еще раз**.</span><span class="sxs-lookup"><span data-stu-id="5b9c5-228">Click **Run Again**.</span></span>
    
      - <span data-ttu-id="5b9c5-229">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="5b9c5-229">Click **Next**.</span></span> <span data-ttu-id="5b9c5-230">Сводный экран будет отображаться действия, как они выполняются.</span><span class="sxs-lookup"><span data-stu-id="5b9c5-230">The summary screen will show actions as they are executed.</span></span> <span data-ttu-id="5b9c5-231">После завершения развертывания нажмите кнопку **Просмотреть журнал** , чтобы просмотреть доступные файлы журналов.</span><span class="sxs-lookup"><span data-stu-id="5b9c5-231">Once the deployment is done, click **View Log** to view available log files.</span></span> <span data-ttu-id="5b9c5-232">Нажмите кнопку **Готово** для завершения развертывания.</span><span class="sxs-lookup"><span data-stu-id="5b9c5-232">Click **Finish** to complete the deployment.</span></span>

3.  <span data-ttu-id="5b9c5-233">Если вы хотите восстановить маршрутизацию федерации XMPP для использования восстановленного пограничного сервера, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="5b9c5-233">If you want to fail back the XMPP federation route to use the restored Edge Server, do the following:</span></span>
    
      - <span data-ttu-id="5b9c5-234">Выполните следующий командлет, чтобы повторно указать маршрут федерации XMPP для пограничного пула, в котором теперь будет размещаться федерация XMPP (в данном примере — EdgeServer1):</span><span class="sxs-lookup"><span data-stu-id="5b9c5-234">Run the following cmdlet to repoint the XMPP federation route to the Edge pool which will now host XMPP federation (in this example, EdgeServer1):</span></span>
        
            Set-CsSite Site1 -XmppExternalFederationRoute EdgeServer1.contoso.com
        
        <span data-ttu-id="5b9c5-235">В этом примере Site1 — это сайт, содержащий пограничного пула, в котором теперь будет размещаться маршрут федерации XMPP и EdgeServer1.contoso.com — это полное доменное имя пограничного сервера в этом пуле.</span><span class="sxs-lookup"><span data-stu-id="5b9c5-235">In this example, Site1 is the site containing the Edge pool which will now host the XMPP federation route, and EdgeServer1.contoso.com is the FQDN of an Edge Server in that pool.</span></span>
    
      - <span data-ttu-id="5b9c5-236">Если вы уже нет DNS-записи SRV для федерации XMPP, которая разрешается в пограничный пул, в котором теперь будет размещаться федерация XMPP, необходимо добавить его, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="5b9c5-236">If you do not already have a DNS SRV record for XMPP federation which resolves to the Edge pool which will now host XMPP federation, you must add it, as in the following example.</span></span> <span data-ttu-id="5b9c5-237">Эта запись SRV должен иметь значение порт 5269.</span><span class="sxs-lookup"><span data-stu-id="5b9c5-237">This SRV record must have a port value of 5269.</span></span>
        
            _xmpp-server._tcp.contoso.com
    
      - <span data-ttu-id="5b9c5-238">На внешнем DNS-сервере измените запись DNS A для федерации XMPP, чтобы она указывала на EdgeServer2.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="5b9c5-238">On the external DNS server, change the DNS A record for XMPP federation to point to EdgeServer2.contoso.com.</span></span>
    
      - <span data-ttu-id="5b9c5-239">Убедитесь, что для пограничного пула, в котором теперь будет размещаться федерация XMPP открыт порт 5269 извне.</span><span class="sxs-lookup"><span data-stu-id="5b9c5-239">Verify that the Edge pool which will now host XMPP federation has port 5269 open externally.</span></span>

4.  <span data-ttu-id="5b9c5-240">Если пулов переднего плана оставались работает в сайт, содержащий пограничного пула, который не удалось и восстановления, необходимо обновить служба веб-конференций и A / V служба конференц-связи на эти переднего плана пулы повторно использовать пограничного сервера в его локальном сайте.</span><span class="sxs-lookup"><span data-stu-id="5b9c5-240">If the Front End pools remained running in the site containing the Edge pool that failed and has been restored, you should update the Web Conferencing Service and A/V Conferencing Service on these Front End pools to again use the Edge pools at their local site.</span></span>

5.  <span data-ttu-id="5b9c5-241">Если также сбой пула переднего плана на том же сайте пограничный пул, теперь можно использовать Invoke – CsPoolFailback сбоя пула переднего плана.</span><span class="sxs-lookup"><span data-stu-id="5b9c5-241">If the Front End pool at the same site as the failed Edge pool also failed, you can now use Invoke–CsPoolFailback to fail back the Front End pool.</span></span>


## <a name="change-the-edge-pool-associated-with-a-front-end-pool"></a><span data-ttu-id="5b9c5-242">Изменение пограничного пула, связанного с пулом переднего плана</span><span class="sxs-lookup"><span data-stu-id="5b9c5-242">Change the Edge pool associated with a Front End pool</span></span>

<span data-ttu-id="5b9c5-243">Если пограничный пул происходит сбой, но при сохранении работоспособности пула переднего плана на том же сайте, необходимо установить пул переднего плана для использования пограничного пула на другом сайте до восстановления пограничный пул.</span><span class="sxs-lookup"><span data-stu-id="5b9c5-243">If an Edge pool goes down but the Front End pool at the same site is still running, you will need to set the Front End pool to use an Edge pool at a different site until the failed Edge pool is restored.</span></span>

1.  <span data-ttu-id="5b9c5-244">В построителе топологий перейдите к имени пула переднего плана, которые необходимо изменить.</span><span class="sxs-lookup"><span data-stu-id="5b9c5-244">In Topology Builder, navigate to the name of the Front End pool you need to change.</span></span>

2.  <span data-ttu-id="5b9c5-245">Щелкните пул правой кнопкой мыши и выберите команду **Изменить свойства**.</span><span class="sxs-lookup"><span data-stu-id="5b9c5-245">Right-click the pool, and then click **Edit Properties**.</span></span>

3.  <span data-ttu-id="5b9c5-246">В разделе **связи** **Связать пограничный пул (для компонентов мультимедиа)** используйте раскрывающееся поле для выбора пограничного пула, который нужно сопоставить интерфейсный пул с.</span><span class="sxs-lookup"><span data-stu-id="5b9c5-246">In the **Associations** section, under **Associate Edge Pool (for media components)**, use the drop down box to select the Edge pool you want to associate this Front End pool with.</span></span>

4.  <span data-ttu-id="5b9c5-247">Нажмите **ОК**.</span><span class="sxs-lookup"><span data-stu-id="5b9c5-247">Click **OK**.</span></span>
