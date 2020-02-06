---
title: Отработка отказа для пула
ms.reviewer: ''
author: lanachin
ms.author: v-lanac
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: .
ms.openlocfilehash: d5409441336ef2af8bbe9c6a39530584a167ec05
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818210"
---
# <a name="failing-over-and-failing-back-a-pool-in-skype-for-business-server"></a><span data-ttu-id="74e38-103">Отказ от резервного копирования пула в Skype для бизнеса Server и отказ от него</span><span class="sxs-lookup"><span data-stu-id="74e38-103">Failing over and failing back a pool in Skype for Business Server</span></span> 

<span data-ttu-id="74e38-104">Выполните описанные ниже действия, если один пул переднего плана завершился сбоем и необходимо отработку отказа, или пул, в котором произошел сбой, снова подключен к сети, и вам необходимо восстановить состояние развертывания в обычном режиме работы.</span><span class="sxs-lookup"><span data-stu-id="74e38-104">Use the following procedures if a single Front End pool has failed and needs to be failed over, or the pool that experienced the disaster is back online and you need to restore your deployment to regular working status.</span></span> <span data-ttu-id="74e38-105">Кроме того, вы узнаете, как переключиться на подложку, используемую для Федерации Skype для бизнеса или КСМПП Federation, или изменить пул краев, связанный с пулом переднего плана.</span><span class="sxs-lookup"><span data-stu-id="74e38-105">Also  learn how to fail over and fail back the Edge pool used for Skype for Business federation or XMPP federation, or change the Edge pool associated with a Front End pool.</span></span>

- [<span data-ttu-id="74e38-106">Переключение из пула переднего плана</span><span class="sxs-lookup"><span data-stu-id="74e38-106">Fail over a Front End pool</span></span>](#fail-over-a-front-end-pool)
- [<span data-ttu-id="74e38-107">Не удается вернуть пул</span><span class="sxs-lookup"><span data-stu-id="74e38-107">Fail back a pool</span></span>](#fail-back-a-pool)
- [<span data-ttu-id="74e38-108">Отказ от пула EDGE, используемого для интеграции Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="74e38-108">Fail over the Edge pool used for Skype for Business Server federation</span></span>](#fail-over-the-edge-pool-used-for-skype-for-business-server-federation)
- [<span data-ttu-id="74e38-109">Отказ от пула EDGE, используемого для Федерации КСМПП в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="74e38-109">Fail over the Edge pool used for XMPP federation in Skype for Business Server</span></span>](#fail-over-the-edge-pool-used-for-xmpp-federation-in-skype-for-business-server)
- [<span data-ttu-id="74e38-110">Сбой при обратном использовании пула EDGE, используемого для Федерации Skype для бизнеса Server или Федерации КСМПП</span><span class="sxs-lookup"><span data-stu-id="74e38-110">Fail back the Edge pool used for Skype for Business Server federation or XMPP federation</span></span>](#fail-back-the-edge-pool-used-for-skype-for-business-server-federation-or-xmpp-federation)
- [<span data-ttu-id="74e38-111">Изменение пула EDGE, связанного с пулом переднего плана</span><span class="sxs-lookup"><span data-stu-id="74e38-111">Change the Edge pool associated with a Front End pool</span></span>](#change-the-edge-pool-associated-with-a-front-end-pool)

## <a name="fail-over-a-front-end-pool"></a><span data-ttu-id="74e38-112">Переключение из пула переднего плана</span><span class="sxs-lookup"><span data-stu-id="74e38-112">Fail over a Front End pool</span></span>

<span data-ttu-id="74e38-113">В этой процедуре Datacenter1 содержит Pool1 и Pool1 завершился сбоем.</span><span class="sxs-lookup"><span data-stu-id="74e38-113">In this procedure, Datacenter1 contains Pool1, and Pool1 has failed.</span></span> <span data-ttu-id="74e38-114">Вы не можете найти Pool2 в Datacenter2.</span><span class="sxs-lookup"><span data-stu-id="74e38-114">You are failing over to Pool2 located in Datacenter2.</span></span>

<span data-ttu-id="74e38-115">Большая часть работы для отработки отказа в пуле связана с отказом в хранилище Центрального управления, если это необходимо.</span><span class="sxs-lookup"><span data-stu-id="74e38-115">Most of the work for the pool failover involves failing over the Central Management store, if it is required.</span></span> <span data-ttu-id="74e38-116">Это важно, так как центральное хранилище управления должно быть работоспособным при сбое пользователей пула.</span><span class="sxs-lookup"><span data-stu-id="74e38-116">This is important because the Central Management store must be functional when the pool’s users are failed over.</span></span>

<span data-ttu-id="74e38-117">Кроме того, если пул переднего плана завершается сбоем, но пул EDGE на нем по-прежнему работает, необходимо знать, использует ли пул отказ в качестве следующего пула прыжков.</span><span class="sxs-lookup"><span data-stu-id="74e38-117">Additionally, if a Front End pool fails but the Edge pool at that site is still running, you must know whether the Edge pool uses the failed pool as a next hop pool.</span></span> <span data-ttu-id="74e38-118">Если это так, вы должны изменить пул EDGE, чтобы использовать другой пул переднего плана, прежде чем произойдет сбой в пуле внешних интерфейсов.</span><span class="sxs-lookup"><span data-stu-id="74e38-118">If it does, you must change the Edge pool to use a different Front End pool before failing over the failed Front End pool.</span></span> <span data-ttu-id="74e38-119">Способ изменения параметров следующего прыжка зависит от того, будет ли край использовать пул на том же сайте, что и пул EDGE, или другой сайт.</span><span class="sxs-lookup"><span data-stu-id="74e38-119">How you change the next hop setting depends on whether the Edge will use a pool at the same site as the Edge pool, or a different site.</span></span>

<span data-ttu-id="74e38-120">**Настройка пограничного пула на использование следующего пула прыжков на том же сайте**</span><span class="sxs-lookup"><span data-stu-id="74e38-120">**To set an Edge pool to use a next hop pool at the same site**</span></span>

1.  <span data-ttu-id="74e38-121">Откройте построитель топологии, щелкните правой кнопкой мыши Граничный пул, который необходимо изменить, и выберите команду **изменить свойства**.</span><span class="sxs-lookup"><span data-stu-id="74e38-121">Open Topology Builder, right-click the Edge pool that needs to be changed, and click **Edit Properties**.</span></span>

2.  <span data-ttu-id="74e38-122">Щелкните **следующий прыжок**.</span><span class="sxs-lookup"><span data-stu-id="74e38-122">Click **Next Hop**.</span></span> <span data-ttu-id="74e38-123">В списке **следующего прыжка пул:** выберите пул, который будет использоваться в качестве пула следующего прыжка.</span><span class="sxs-lookup"><span data-stu-id="74e38-123">From the **Next hop pool:** list, select the pool which will now serve as the next hop pool.</span></span>

3.  <span data-ttu-id="74e38-124">Нажмите кнопку **ОК**, а затем опубликуйте изменения.</span><span class="sxs-lookup"><span data-stu-id="74e38-124">Click **OK**, and then publish the changes.</span></span>

<span data-ttu-id="74e38-125">**Настройка пограничного пула на использование пула следующего прыжка на другом сайте**</span><span class="sxs-lookup"><span data-stu-id="74e38-125">**To set an Edge pool to use a next hop pool at a different site**</span></span>

1.  <span data-ttu-id="74e38-126">Откройте окно командной консоли Skype для бизнеса Server и введите следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="74e38-126">Open a Skype for Business Server Management Shell window and type the following cmdlet:</span></span>
    
        Set-CsEdgeServer -Identity EdgeServer:<Edge Server pool FQDN> -Registrar Registrar:<NextHopPoolFQDN>

<span data-ttu-id="74e38-127">**Отказ от пула в случае аварии**</span><span class="sxs-lookup"><span data-stu-id="74e38-127">**To fail over a pool in a disaster**</span></span>

1.  <span data-ttu-id="74e38-128">Чтобы найти, какой из пулов является узлом центрального сервера управления, введите следующий командлет на сервере переднего плана в Pool2:</span><span class="sxs-lookup"><span data-stu-id="74e38-128">Find which pool is the host for the Central Management Server by typing the following cmdlet on a Front End server in Pool2:</span></span>
    
        Invoke-CsManagementServerFailover -Whatif
    
    <span data-ttu-id="74e38-129">Результаты этого командлета показывают, в каком пуле на данный момент размещен Центральный сервер управления.</span><span class="sxs-lookup"><span data-stu-id="74e38-129">The results of this cmdlet show which pool currently hosts the Central Management Server.</span></span> <span data-ttu-id="74e38-130">В оставшейся части этой процедуры этот пул называется пулом CMS\_.</span><span class="sxs-lookup"><span data-stu-id="74e38-130">In the rest of this procedure, this pool is known as CMS\_Pool.</span></span>

2.  <span data-ttu-id="74e38-131">Использование построителя топологии для поиска версии сервера Skype для бизнеса Server, работающей на\_пуле CMS.</span><span class="sxs-lookup"><span data-stu-id="74e38-131">Use Topology Builder to find the version of Skype for Business Server running on the CMS\_Pool.</span></span> <span data-ttu-id="74e38-132">Если на компьютере установлено приложение Skype для бизнеса Server, найдите пул резервных копий пула 1 с помощью следующего командлета.</span><span class="sxs-lookup"><span data-stu-id="74e38-132">If it is running Skype for Business Server, use the following cmdlet to find the backup pool of Pool 1.</span></span>
    
        Get-CsPoolBackupRelationship -PoolFQDN <CMS_Pool FQDN>
    
    <span data-ttu-id="74e38-133">Пусть резервная копия\_пула является пулом резервных копий.</span><span class="sxs-lookup"><span data-stu-id="74e38-133">Let Backup\_Pool be the backup pool.</span></span>

3.  <span data-ttu-id="74e38-134">Проверьте состояние хранилища центрального управления с помощью следующего командлета:</span><span class="sxs-lookup"><span data-stu-id="74e38-134">Check the status of the Central Management store with the following cmdlet:</span></span>
    
        Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
    
    <span data-ttu-id="74e38-135">Этот командлет показывает, что оба Активемастерфкдн и Активефилетрансферажентс указывают на полное доменное имя пула\_CMS.</span><span class="sxs-lookup"><span data-stu-id="74e38-135">This cmdlet should show that both ActiveMasterFQDN and ActiveFileTransferAgents are pointing to the FQDN of CMS\_Pool.</span></span> <span data-ttu-id="74e38-136">Если они пусты, центральный сервер управления недоступен, и вы должны пройти его.</span><span class="sxs-lookup"><span data-stu-id="74e38-136">If they are empty, the Central Management Server is not available and you must fail it over.</span></span>

4.  <span data-ttu-id="74e38-137">Если хранилище Центрального управления недоступно или хранилище Центрального управления запущено на Pool1 (то есть в пуле, в котором произошел сбой), перед отказом в пуле необходимо выполнить переключение на центральный сервер управления.</span><span class="sxs-lookup"><span data-stu-id="74e38-137">If the Central Management store is not available or if the Central Management store was running on Pool1 (that is, the pool that has failed), you must fail over the Central Management Server before failing over the pool.</span></span> <span data-ttu-id="74e38-138">Если вам нужно переключиться на центральный сервер управления, размещенный в пуле, на котором работает Skype для бизнеса Server, используйте командлет, описанный в шаге 5 этой процедуры.</span><span class="sxs-lookup"><span data-stu-id="74e38-138">If you need to fail over the Central Management Server that was hosted on a pool running Skype for Business Server, use the cmdlet in step 5 of this procedure.</span></span> <span data-ttu-id="74e38-139">Если вам не нужно переключиться на центральный сервер управления, перейдите к шагу 7 этой процедуры.</span><span class="sxs-lookup"><span data-stu-id="74e38-139">If you do not need to fail over the Central Management Server, skip to step 7 of this procedure.</span></span>

5.  <span data-ttu-id="74e38-140">Чтобы отдать отказ на хранение центрального хранилища в пуле, работающем в Skype для бизнеса Server, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="74e38-140">To fail over the Central Management store on a pool running Skype for Business Server, do the following:</span></span>
    
      - <span data-ttu-id="74e38-141">Сначала убедитесь, что сервер, на котором он\_находится в резервной копии, запускает экземпляр основного хранилища, введя следующие символы:</span><span class="sxs-lookup"><span data-stu-id="74e38-141">First, check which Back End Server in Backup\_Pool runs the principal instance of the Central Management store by typing the following:</span></span>
        
            Get-CsDatabaseMirrorState -DatabaseType Centralmgmt -PoolFqdn <Backup_Pool Fqdn>
    
      - <span data-ttu-id="74e38-142">Если основной сервер в пуле резервной копии\_является основным, введите:</span><span class="sxs-lookup"><span data-stu-id="74e38-142">If the primary Back End Server in Backup\_Pool is the principal, type:</span></span>
        
            Invoke-CSManagementServerFailover -BackupSQLServerFqdn <Backup_Pool Primary BackEnd Server FQDN> -BackupSQLInstanceName <Backup_Pool Primary SQL Instance Name>
        
        <span data-ttu-id="74e38-143">Если сервер зеркального отображения в пуле резервных копий\_является основным, введите:</span><span class="sxs-lookup"><span data-stu-id="74e38-143">If the mirror Back End Server in Backup\_Pool is the principal, type:</span></span>
        
            Invoke-CSManagementServerFailover -MirrorSQLServerFqdn <Backup_Pool Mirror BackEnd Server FQDN> -MirrorSQLInstanceName <Backup_Pool Mirror SQL Instance Name>
    
      - <span data-ttu-id="74e38-144">Убедитесь, что переход на центральный сервер управления завершен.</span><span class="sxs-lookup"><span data-stu-id="74e38-144">Validate that the Central Management Server failover is complete.</span></span> <span data-ttu-id="74e38-145">Введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="74e38-145">Type the following:</span></span>
        
            Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
        
        <span data-ttu-id="74e38-146">Убедитесь, что оба Активемастерфкдн и Активефилетрансферажентс указывают на полное доменное имя\_пула резервных копий.</span><span class="sxs-lookup"><span data-stu-id="74e38-146">Check that both ActiveMasterFQDN and ActiveFileTransferAgents are pointing to the FQDN of Backup\_Pool.</span></span>
    
      - <span data-ttu-id="74e38-147">Наконец, проверьте состояние реплики для всех серверов переднего плана, введя следующее:</span><span class="sxs-lookup"><span data-stu-id="74e38-147">Finally, check the replica status for all Front End Servers by typing the following:</span></span>
        
            Get-CsManagementStoreReplicationStatus 
        
        <span data-ttu-id="74e38-148">Убедитесь, что все реплики имеют значение истина.</span><span class="sxs-lookup"><span data-stu-id="74e38-148">Check that all replicas have a value of True.</span></span>
        
        <span data-ttu-id="74e38-149">Перейдите к шагу 7 в этой процедуре.</span><span class="sxs-lookup"><span data-stu-id="74e38-149">Skip to step 7 in this procedure.</span></span>

6.  <span data-ttu-id="74e38-150">Установите хранилище Central Management на сервере заднего резервного\_пула.</span><span class="sxs-lookup"><span data-stu-id="74e38-150">Install the Central Management store on the Back End Server of Backup\_Pool.</span></span>
    
      - <span data-ttu-id="74e38-151">Сначала выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="74e38-151">First, run the following command:</span></span>
        ```PowerShell
         
        Install-CsDatabase -CentralManagementDatabase -Clean -SqlServerFqdn <Backup_Pool Back End Server FQDN> -SqlInstanceName rtc  
        ```
    
      - <span data-ttu-id="74e38-152">Запустите следующую команду на одном из серверов переднего плана резервного\_пула, чтобы принудительно переместить хранилище Центрального управления.</span><span class="sxs-lookup"><span data-stu-id="74e38-152">Run the next command on one of the Front End Servers of Backup\_Pool to force the move of the Central Management store:</span></span>
        
            Move-CsManagementServer -ConfigurationFileName c:\CsConfigurationFile.zip -LisConfigurationFileName c:\CsLisConfigurationFile.zip -Force 
    
      - <span data-ttu-id="74e38-153">Проверка завершения перемещения.</span><span class="sxs-lookup"><span data-stu-id="74e38-153">Validate the move is complete:</span></span>
        
            Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
        
        <span data-ttu-id="74e38-154">Убедитесь, что оба Активемастерфкдн и Активефилетрансферажентс указывают на полное доменное имя\_пула резервных копий.</span><span class="sxs-lookup"><span data-stu-id="74e38-154">Check that both ActiveMasterFQDN and ActiveFileTransferAgents are pointing to the FQDN of Backup\_Pool.</span></span>
    
      - <span data-ttu-id="74e38-155">Проверьте состояние реплики для всех серверов переднего плана, введя следующее:</span><span class="sxs-lookup"><span data-stu-id="74e38-155">Check the replica status for all Front End Servers by typing the following:</span></span>
        
            Get-CsManagementStoreReplicationStatus 
        
        <span data-ttu-id="74e38-156">Убедитесь, что все реплики имеют значение истина.</span><span class="sxs-lookup"><span data-stu-id="74e38-156">Check that all replicas have a value of True.</span></span>
    
      - <span data-ttu-id="74e38-157">Установите службу центрального сервера управления на остальных серверах переднего плана в пуле резервных копий\_.</span><span class="sxs-lookup"><span data-stu-id="74e38-157">Install the Central Management Server service on the rest of the Front End Servers in Backup\_Pool.</span></span> <span data-ttu-id="74e38-158">Для этого выполните следующую команду на всех серверах переднего плана, кроме той, которую вы использовали при принудительном переходе на центральное хранилище управления в этой процедуре:</span><span class="sxs-lookup"><span data-stu-id="74e38-158">To do so, run the following command on all the Front End Servers, except the one you used when forcing the Central Management store move earlier in this procedure:</span></span>
        
            Bootstrapper /Setup 

7.  <span data-ttu-id="74e38-159">Для переключения пользователей из Pool1 в Pool2, выполнив следующий командлет в окне командной консоли Skype для бизнеса Server:</span><span class="sxs-lookup"><span data-stu-id="74e38-159">Fail over the users from Pool1 to Pool2 by running the following cmdlet in a Skype for Business Server Management Shell window:</span></span>
    
        Invoke-CsPoolFailover -PoolFQDN <Pool1 FQDN> -DisasterMode -Verbose
    
    <span data-ttu-id="74e38-160">Поскольку действия, описанные в предыдущем разделе, для проверки состояния центрального хранилища управления не являются универсальными, возможно, этот командлет завершится сбоем, так как хранилище Центрального управления пока не проходит полную отработку отказа.</span><span class="sxs-lookup"><span data-stu-id="74e38-160">Because the steps taken in the previous parts of this procedure to check the Central Management store status are not universal, there is still a chance this cmdlet will fail because the Central Management store is not yet fully failed over.</span></span> <span data-ttu-id="74e38-161">В этом случае необходимо исправить центральное хранилище управления на основе отображаемых сообщений об ошибках, а затем повторно запустить этот командлет.</span><span class="sxs-lookup"><span data-stu-id="74e38-161">In this case, you must fix the Central Management store based on the error messages that you see, and then run this cmdlet again.</span></span>
    
    <span data-ttu-id="74e38-162">Если появляется следующее сообщение об ошибке, вам необходимо изменить пул EDGE на этом сайте, чтобы использовать другой пул в качестве следующего прыжка, прежде чем вы перейдете на пул.</span><span class="sxs-lookup"><span data-stu-id="74e38-162">If you see the following error message, then you need to change the Edge pool at this site to use a different pool as its next hop before failing over the pool.</span></span> <span data-ttu-id="74e38-163">Подробности можно найти в разделе процедуры, описанные в начале этой статьи.</span><span class="sxs-lookup"><span data-stu-id="74e38-163">For details, see the procedures at the beginning of this topic.</span></span>
    
        Invoke-CsPoolFailOver : This Front-end pool "pool1.contoso.com" is specified in
        topology as the next hop for the Edge server. Failing over this pool may cause External
        access/Federation/Split-domain/XMPP features to stop working. Please use Topology Builder to
        change the Edge internal next hop setting to point to a different Front-end pool,  before you
        proceed.


## <a name="fail-back-a-pool"></a><span data-ttu-id="74e38-164">Не удается вернуть пул</span><span class="sxs-lookup"><span data-stu-id="74e38-164">Fail back a pool</span></span>

<span data-ttu-id="74e38-165">После того как пул, в котором произошел сбой, перейдет в оперативный режим (то есть Pool1 в этом примере), выполните указанные ниже действия, чтобы восстановить состояние развертывания для обычного рабочего состояния.</span><span class="sxs-lookup"><span data-stu-id="74e38-165">After the pool that experienced the disaster is back online (that is, Pool1 in this example), take the following steps to restore your deployment to regular working status.</span></span>

<span data-ttu-id="74e38-166">Обратите внимание, что процесс восстановления после сбоя занимает несколько минут.</span><span class="sxs-lookup"><span data-stu-id="74e38-166">Note that the failback process takes several minute to complete.</span></span><span data-ttu-id="74e38-167">Следует исходить из длительности 60 минут для пула, в котором работает 20 000 пользователей.</span><span class="sxs-lookup"><span data-stu-id="74e38-167">  For reference, it is expected to take up to 60 minutes for a pool of 20,000 users.</span></span>

<span data-ttu-id="74e38-168">Не изменяйте пользователей, которые изначально были размещены в Pool1, и произошел сбой при переходе на Pool2, введя следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="74e38-168">Fail back the users who were originally homed in Pool1 and have been failed over to Pool2 by typing the following cmdlet:</span></span>
    
    Invoke-CsPoolFailback -PoolFQDN <Pool1 FQDN> -Verbose

<span data-ttu-id="74e38-169">Никаких других действий не требуется.</span><span class="sxs-lookup"><span data-stu-id="74e38-169">No other steps are necessary.</span></span> <span data-ttu-id="74e38-170">Если вы отошел сбой на центральном сервере управления, вы можете оставить его в Pool2.</span><span class="sxs-lookup"><span data-stu-id="74e38-170">If you failed over the Central Management Server, you can leave it in Pool2.</span></span>

## <a name="fail-over-the-edge-pool-used-for-skype-for-business-server-federation"></a><span data-ttu-id="74e38-171">Отказ от пула EDGE, используемого для интеграции Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="74e38-171">Fail over the Edge pool used for Skype for Business Server federation</span></span> 

<span data-ttu-id="74e38-172">Если пул пограничного пула, на котором настроена веб-сервер Skype для бизнеса Server, не работает, необходимо изменить Федерацию так, чтобы он использовал другой пул Edge для работы Федерации.</span><span class="sxs-lookup"><span data-stu-id="74e38-172">If the Edge pool where you have Skype for Business Server federation configured goes down, you must change federation to use a different Edge pool for federation to work.</span></span>

1.  <span data-ttu-id="74e38-173">На сервере переднего плана откройте окно Построитель топологии.</span><span class="sxs-lookup"><span data-stu-id="74e38-173">On a Front End server, open Topology Builder.</span></span> <span data-ttu-id="74e38-174">Разверните узел **пограничного**пула и щелкните правой кнопкой мыши граничный сервер пограничного сервера или пул пограничного сервера, настроенный на данный момент для Федерации.</span><span class="sxs-lookup"><span data-stu-id="74e38-174">Expand **Edge pools**, and then right-click the Edge server or Edge server pool that is currently configured for Federation.</span></span> <span data-ttu-id="74e38-175">Нажмите кнопку **изменить свойства**.</span><span class="sxs-lookup"><span data-stu-id="74e38-175">Select **Edit properties**.</span></span>

2.  <span data-ttu-id="74e38-176">В диалоговом окне **изменение свойств** в разделе **Общие**снимите флажок **включить федерацию для этого пограничного пула (порт 5061)**.</span><span class="sxs-lookup"><span data-stu-id="74e38-176">In **Edit Properties** under **General**, clear **Enable federation for this Edge pool (Port 5061)**.</span></span> <span data-ttu-id="74e38-177">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="74e38-177">Click **OK**.</span></span>

3.  <span data-ttu-id="74e38-178">Разверните **Пулы Edge**, а затем щелкните правой кнопкой мыши граничный сервер пограничного сервера или пул пограничного сервера, который вы хотите использовать для Федерации.</span><span class="sxs-lookup"><span data-stu-id="74e38-178">Expand **Edge pools**, and then right-click the Edge server or Edge server pool that you now want to use for Federation.</span></span> <span data-ttu-id="74e38-179">Нажмите кнопку **изменить свойства**.</span><span class="sxs-lookup"><span data-stu-id="74e38-179">Select **Edit properties**.</span></span>

4.  <span data-ttu-id="74e38-180">В диалоговом окне **изменение свойств** в разделе **Общие**установите флажок **включить федерацию для этого пограничного пула (порт 5061)**.</span><span class="sxs-lookup"><span data-stu-id="74e38-180">In **Edit Properties** under **General**, select **Enable federation for this Edge pool (Port 5061)**.</span></span> <span data-ttu-id="74e38-181">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="74e38-181">Click **OK**.</span></span>

5.  <span data-ttu-id="74e38-182">Нажмите кнопку **действие**, выберите пункт **топология**, нажмите кнопку **опубликовать**.</span><span class="sxs-lookup"><span data-stu-id="74e38-182">Click **Action**, select **Topology**, select **Publish**.</span></span> <span data-ttu-id="74e38-183">При появлении запроса на **публикацию топологии**нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="74e38-183">When prompted on **Publish the topology**, click **Next**.</span></span> <span data-ttu-id="74e38-184">Завершив публикацию, нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="74e38-184">When the Publish is finished, click **Finish**.</span></span>

6.  <span data-ttu-id="74e38-185">На пограничном сервере откройте мастер развертывания Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="74e38-185">On the Edge server, open the Skype for Business Server Deployment wizard.</span></span> <span data-ttu-id="74e38-186">Нажмите кнопку **Установка или обновление серверной системы Skype для бизнеса**, а затем нажмите кнопку **Настройка или удалите компоненты Skype для бизнеса Server**.</span><span class="sxs-lookup"><span data-stu-id="74e38-186">Click **Install or Update Skype for Business Server System**, and then click **Setup or Remove Skype for Business Server Components**.</span></span> <span data-ttu-id="74e38-187">Нажмите кнопку **выполнить еще раз**.</span><span class="sxs-lookup"><span data-stu-id="74e38-187">Click **Run Again**.</span></span>

7.  <span data-ttu-id="74e38-188">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="74e38-188">Click **Next**.</span></span> <span data-ttu-id="74e38-189">На экране сводки будут показаны действия по мере их выполнения.</span><span class="sxs-lookup"><span data-stu-id="74e38-189">The summary screen will show actions as they are executed.</span></span> <span data-ttu-id="74e38-190">После завершения развертывания щелкните **Просмотреть журнал** , чтобы просмотреть доступные файлы журнала.</span><span class="sxs-lookup"><span data-stu-id="74e38-190">Once the deployment is done, click **View Log** to view available log files.</span></span> <span data-ttu-id="74e38-191">Нажмите кнопку **Готово** , чтобы завершить развертывание.</span><span class="sxs-lookup"><span data-stu-id="74e38-191">Click **Finish** to complete the deployment.</span></span>
    
    <span data-ttu-id="74e38-192">Если сайт, содержащий неисправный пул, содержит серверы переднего плана, которые еще не запущены, для использования пула EDGE на удаленном сайте, который еще не работает, необходимо обновить службу веб-конференций и службу Конференции/V на этих интерфейсных пулах.</span><span class="sxs-lookup"><span data-stu-id="74e38-192">If the site containing the failed Edge pool contains Front End Servers that are still running, you must update the Web Conferencing Service and A/V Conferencing Service on these Front End pools to use an Edge pool in a remote site that is still running.</span></span> 

 ## <a name="fail-over-the-edge-pool-used-for-xmpp-federation-in-skype-for-business-server"></a><span data-ttu-id="74e38-193">Отказ от пула EDGE, используемого для Федерации КСМПП в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="74e38-193">Fail over the Edge pool used for XMPP federation in Skype for Business Server</span></span> 

<span data-ttu-id="74e38-194">В вашей организации используется один пул краев, назначенный пулом для КСМПП Федерации.</span><span class="sxs-lookup"><span data-stu-id="74e38-194">In your organization, there is one Edge pool designated as the pool to use for XMPP federation.</span></span> <span data-ttu-id="74e38-195">Если этот пул отключается, необходимо отдать отказ на КСМПП Федерацию для использования другого пула Edge перед тем, как КСМПП Федерация сможет снова работать.</span><span class="sxs-lookup"><span data-stu-id="74e38-195">If this pool goes down, you must fail over XMPP federation to use a different Edge pool before XMPP federation can work again.</span></span>

<span data-ttu-id="74e38-196">После установки пулов EDGE и включения КСМПП Федерации вы можете упростить процесс аварийного восстановления, настроив внешние записи DNS SRV для всех пулов Edge для КСМПП Федерации, а не только для одной из них.</span><span class="sxs-lookup"><span data-stu-id="74e38-196">When you first install Edge pools and enable XMPP Federation, you can simplify the disaster recovery process by setting up external DNS SRV records for all of your Edge pools for XMPP federation, instead of just one.</span></span> <span data-ttu-id="74e38-197">Для каждой из этих записей SRV должен быть установлен другой приоритет.</span><span class="sxs-lookup"><span data-stu-id="74e38-197">Each of these SRV records must have a different priority set.</span></span> <span data-ttu-id="74e38-198">Весь трафик Федерации КСМПП проходит через пул с записью SRV с самым высоким приоритетом.</span><span class="sxs-lookup"><span data-stu-id="74e38-198">All XMPP federation traffic goes through the pool with the SRV record with the highest priority.</span></span> 

<span data-ttu-id="74e38-199">В описанной ниже процедуре EdgePool1 — пул, изначально размещенный КСМПП Federation, и EdgePool2 — пул, который теперь будет размещен КСМПП Федерации.</span><span class="sxs-lookup"><span data-stu-id="74e38-199">In the following procedure, EdgePool1 is the pool which originally hosted XMPP federation, and EdgePool2 is the pool which will now host XMPP federation.</span></span>


### <a name="to-fail-over-the-edge-pool-used-for-xmpp-federation"></a><span data-ttu-id="74e38-200">Чтобы отдать отказ на использование пула пограничного сервера для Федерации КСМПП</span><span class="sxs-lookup"><span data-stu-id="74e38-200">To fail over the Edge pool used for XMPP federation</span></span>

1.  <span data-ttu-id="74e38-201">Если вы еще не развернули другой пул пограничных кромок (Кроме того, который в данный момент не работает), разверните этот пул.</span><span class="sxs-lookup"><span data-stu-id="74e38-201">If you don’t already have another Edge pool deployed (besides the one which is currently down), deploy that pool.</span></span> 

2.  <span data-ttu-id="74e38-202">На каждом пограничном сервере в новом пограничном пуле, на котором будет размещена КСМПП Федерация (EdgePool2), запустите следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="74e38-202">On each Edge Server in the new Edge pool which will now host XMPP federation (EdgePool2), run the following cmdlet:</span></span>
    
        Stop-CsWindowsService

3.  <span data-ttu-id="74e38-203">Чтобы перенаправить маршрут Федерации КСМПП на EdgePool2, выполните следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="74e38-203">Run the following cmdlet to repoint the XMPP federation route to EdgePool2:</span></span>
    
        Set-CsSite Site2 -XmppExternalFederationRoute EdgeServer2.contoso.com
    
    <span data-ttu-id="74e38-204">В этом примере Site2 — сайт с пулом EDGE, который теперь будет размещаться на маршруте Федерации КСМПП, а EdgeServer2.contoso.com — это полное доменное имя пограничного сервера в этом пуле.</span><span class="sxs-lookup"><span data-stu-id="74e38-204">In this example, Site2 is the site containing the Edge pool which will now host the XMPP federation route, and EdgeServer2.contoso.com is the FQDN of an Edge Server in that pool.</span></span>

4.  <span data-ttu-id="74e38-205">На внешнем DNS-сервере измените запись DNS A для Федерации КСМПП, чтобы она указывала на EdgeServer2.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="74e38-205">On the external DNS server, change the DNS A record for XMPP federation to point to EdgeServer2.contoso.com.</span></span>

5.  <span data-ttu-id="74e38-206">Если у вас еще нет DNS-записи SRV для Федерации КСМПП, которая разрешается в пул EDGE, который теперь будет размещаться в КСМПП Федерации, необходимо добавить его, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="74e38-206">If you do not already have a DNS SRV record for XMPP federation which resolves to the Edge pool which will now host XMPP federation, you must add it, as in the following example.</span></span> <span data-ttu-id="74e38-207">Для этой записи SRV должно быть задано значение Port 5269.</span><span class="sxs-lookup"><span data-stu-id="74e38-207">This SRV record must have a port value of 5269.</span></span>
    
        _xmpp-server._tcp.contoso.com

6.  <span data-ttu-id="74e38-208">Убедитесь, что в пуле EDGE, на котором будет размещена КСМПП Федерация, есть порт 5269, Открытый извне.</span><span class="sxs-lookup"><span data-stu-id="74e38-208">Verify that the Edge pool which will now host XMPP federation has port 5269 open externally.</span></span>

7.  <span data-ttu-id="74e38-209">Запустите службы на всех пограничных серверах в пограничном пуле, где будет размещаться Федерация КСМПП:</span><span class="sxs-lookup"><span data-stu-id="74e38-209">Start the services on all Edge Servers in the Edge pool which will now host XMPP federation:</span></span>
    
        Start-CsWindowsService


## <a name="fail-back-the-edge-pool-used-for-skype-for-business-server-federation-or-xmpp-federation"></a><span data-ttu-id="74e38-210">Сбой при обратном использовании пула EDGE, используемого для Федерации Skype для бизнеса Server или Федерации КСМПП</span><span class="sxs-lookup"><span data-stu-id="74e38-210">Fail back the Edge pool used for Skype for Business Server federation or XMPP federation</span></span> 

<span data-ttu-id="74e38-211">После того как пул пограничного пула, который использовался для размещения Федерации, будет переведен в режим онлайн, выполните указанные ниже действия, чтобы восстановить маршрут Федерации Skype для бизнеса Server и/или КСМПП Федерации для повторного использования этого восстановленного пограничного пула.</span><span class="sxs-lookup"><span data-stu-id="74e38-211">After a failed Edge pool that used to host federation has been brought back online, use this procedure to fail back the Skype for Business Server federation route and/or the XMPP federation route to again use this restored Edge pool.</span></span>

1.  <span data-ttu-id="74e38-212">В пуле EDGE, который теперь доступен еще раз, запустите службы Edge.</span><span class="sxs-lookup"><span data-stu-id="74e38-212">On the Edge pool that is now available again, start the Edge Services.</span></span>

2.  <span data-ttu-id="74e38-213">Если вы хотите вернуть маршрут Федерации Skype для бизнеса Server для использования восстановленного пограничного сервера, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="74e38-213">If you want to fail back the Skype for Business Server federation route to use the restored Edge Server, do the following:</span></span>
    
      - <span data-ttu-id="74e38-214">На сервере переднего плана откройте окно Построитель топологии.</span><span class="sxs-lookup"><span data-stu-id="74e38-214">On a Front End server, open Topology Builder.</span></span> <span data-ttu-id="74e38-215">Разверните узел **Edge**Pools, а затем щелкните правой кнопкой мыши граничный сервер пограничного сервера или пул пограничного сервера, настроенный на данный момент для Федерации.</span><span class="sxs-lookup"><span data-stu-id="74e38-215">Expand **Edge pools**, then right click the Edge server or Edge server pool that is currently configured for Federation.</span></span> <span data-ttu-id="74e38-216">Нажмите кнопку **изменить свойства**.</span><span class="sxs-lookup"><span data-stu-id="74e38-216">Select **Edit properties**.</span></span>
    
      - <span data-ttu-id="74e38-217">В диалоговом окне **изменение свойств** в разделе **Общие**снимите флажок **включить федерацию для этого пограничного пула (порт 5061)**.</span><span class="sxs-lookup"><span data-stu-id="74e38-217">In **Edit Properties** under **General**, clear **Enable federation for this Edge pool (Port 5061)**.</span></span> <span data-ttu-id="74e38-218">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="74e38-218">Click **OK**.</span></span>
    
      - <span data-ttu-id="74e38-219">Разверните узел **Edge**Pools, а затем щелкните правой кнопкой мыши исходный сервер пограничного сервера или пул пограничного сервера, который вы снова хотите использовать для Федерации.</span><span class="sxs-lookup"><span data-stu-id="74e38-219">Expand **Edge pools**, then right click the original Edge server or Edge server pool that you again want to use for Federation.</span></span> <span data-ttu-id="74e38-220">Нажмите кнопку **изменить свойства**.</span><span class="sxs-lookup"><span data-stu-id="74e38-220">Select **Edit properties**.</span></span>
    
      - <span data-ttu-id="74e38-221">В диалоговом окне **изменение свойств** в разделе **Общие**установите флажок **включить федерацию для этого пограничного пула (порт 5061)**.</span><span class="sxs-lookup"><span data-stu-id="74e38-221">In **Edit Properties** under **General**, select **Enable federation for this Edge pool (Port 5061)**.</span></span> <span data-ttu-id="74e38-222">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="74e38-222">Click **OK**.</span></span>
    
      - <span data-ttu-id="74e38-223">Нажмите кнопку **действие**, выберите пункт **топология**, нажмите кнопку **опубликовать**.</span><span class="sxs-lookup"><span data-stu-id="74e38-223">Click **Action**, select **Topology**, select **Publish**.</span></span> <span data-ttu-id="74e38-224">При появлении запроса на **публикацию топологии**нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="74e38-224">When prompted on **Publish the topology**, click **Next**.</span></span> <span data-ttu-id="74e38-225">Завершив публикацию, нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="74e38-225">When the Publish is finished, click **Finish**.</span></span>
    
      - <span data-ttu-id="74e38-226">На пограничном сервере откройте мастер развертывания Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="74e38-226">On the Edge server, open the Skype for Business Server Deployment wizard.</span></span> <span data-ttu-id="74e38-227">Нажмите кнопку **Установка или обновление системы Skype для бизнеса Server**, а затем выберите пункт **Настройка или удалить компоненты Skype для бизнеса Server**.</span><span class="sxs-lookup"><span data-stu-id="74e38-227">Click **Install or Update Skype for Business Server System**, then click **Setup or Remove Skype for Business Server Components**.</span></span> <span data-ttu-id="74e38-228">Нажмите кнопку **выполнить еще раз**.</span><span class="sxs-lookup"><span data-stu-id="74e38-228">Click **Run Again**.</span></span>
    
      - <span data-ttu-id="74e38-229">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="74e38-229">Click **Next**.</span></span> <span data-ttu-id="74e38-230">На экране сводки будут показаны действия по мере их выполнения.</span><span class="sxs-lookup"><span data-stu-id="74e38-230">The summary screen will show actions as they are executed.</span></span> <span data-ttu-id="74e38-231">После завершения развертывания щелкните **Просмотреть журнал** , чтобы просмотреть доступные файлы журнала.</span><span class="sxs-lookup"><span data-stu-id="74e38-231">Once the deployment is done, click **View Log** to view available log files.</span></span> <span data-ttu-id="74e38-232">Нажмите кнопку **Готово** , чтобы завершить развертывание.</span><span class="sxs-lookup"><span data-stu-id="74e38-232">Click **Finish** to complete the deployment.</span></span>

3.  <span data-ttu-id="74e38-233">Если вы хотите восстановить маршрут Федерации КСМПП для использования восстановленного пограничного сервера, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="74e38-233">If you want to fail back the XMPP federation route to use the restored Edge Server, do the following:</span></span>
    
      - <span data-ttu-id="74e38-234">Запустите следующий командлет, чтобы перенаправить маршрут Федерации КСМПП на Граничный пул, который будет размещен КСМПП Federation (в этом примере — EdgeServer1):</span><span class="sxs-lookup"><span data-stu-id="74e38-234">Run the following cmdlet to repoint the XMPP federation route to the Edge pool which will now host XMPP federation (in this example, EdgeServer1):</span></span>
        
            Set-CsSite Site1 -XmppExternalFederationRoute EdgeServer1.contoso.com
        
        <span data-ttu-id="74e38-235">В этом примере site1 — сайт с пулом EDGE, который теперь будет размещаться на маршруте Федерации КСМПП, а EdgeServer1.contoso.com — это полное доменное имя пограничного сервера в этом пуле.</span><span class="sxs-lookup"><span data-stu-id="74e38-235">In this example, Site1 is the site containing the Edge pool which will now host the XMPP federation route, and EdgeServer1.contoso.com is the FQDN of an Edge Server in that pool.</span></span>
    
      - <span data-ttu-id="74e38-236">Если у вас еще нет DNS-записи SRV для Федерации КСМПП, которая разрешается в пул EDGE, который теперь будет размещаться в КСМПП Федерации, необходимо добавить его, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="74e38-236">If you do not already have a DNS SRV record for XMPP federation which resolves to the Edge pool which will now host XMPP federation, you must add it, as in the following example.</span></span> <span data-ttu-id="74e38-237">Для этой записи SRV должно быть задано значение Port 5269.</span><span class="sxs-lookup"><span data-stu-id="74e38-237">This SRV record must have a port value of 5269.</span></span>
        
            _xmpp-server._tcp.contoso.com
    
      - <span data-ttu-id="74e38-238">На внешнем DNS-сервере измените запись DNS A для Федерации КСМПП, чтобы она указывала на EdgeServer2.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="74e38-238">On the external DNS server, change the DNS A record for XMPP federation to point to EdgeServer2.contoso.com.</span></span>
    
      - <span data-ttu-id="74e38-239">Убедитесь, что в пуле EDGE, на котором будет размещена КСМПП Федерация, есть порт 5269, Открытый извне.</span><span class="sxs-lookup"><span data-stu-id="74e38-239">Verify that the Edge pool which will now host XMPP federation has port 5269 open externally.</span></span>

4.  <span data-ttu-id="74e38-240">Если на веб-сайте, содержащем пул пограничного сервера, не удалось выполнить все неудачные и восстановленные интерфейсы, следует обновить службу веб-конференций и службу Конференции/V на этих интерфейсных пулах с помощью пулов EDGE на своем локальном сайте.</span><span class="sxs-lookup"><span data-stu-id="74e38-240">If the Front End pools remained running in the site containing the Edge pool that failed and has been restored, you should update the Web Conferencing Service and A/V Conferencing Service on these Front End pools to again use the Edge pools at their local site.</span></span>

5.  <span data-ttu-id="74e38-241">Если пул переднего плана на сайте, на котором произошла ошибка, также завершился сбоем, вы можете использовать Invoke – Кспулфаилбакк для возврата пула переднего плана.</span><span class="sxs-lookup"><span data-stu-id="74e38-241">If the Front End pool at the same site as the failed Edge pool also failed, you can now use Invoke–CsPoolFailback to fail back the Front End pool.</span></span>


## <a name="change-the-edge-pool-associated-with-a-front-end-pool"></a><span data-ttu-id="74e38-242">Изменение пула EDGE, связанного с пулом переднего плана</span><span class="sxs-lookup"><span data-stu-id="74e38-242">Change the Edge pool associated with a Front End pool</span></span>

<span data-ttu-id="74e38-243">Если пул пограничного пула отключается, но пул переднего плана на этом же сайте по-прежнему работает, вы должны настроить интерфейс пула на использование пограничного пула на другом сайте, пока не произойдет восстановление пула Edge.</span><span class="sxs-lookup"><span data-stu-id="74e38-243">If an Edge pool goes down but the Front End pool at the same site is still running, you will need to set the Front End pool to use an Edge pool at a different site until the failed Edge pool is restored.</span></span>

1.  <span data-ttu-id="74e38-244">В построителе топологии найдите имя пула переднего плана, который нужно изменить.</span><span class="sxs-lookup"><span data-stu-id="74e38-244">In Topology Builder, navigate to the name of the Front End pool you need to change.</span></span>

2.  <span data-ttu-id="74e38-245">Щелкните пул правой кнопкой мыши и выберите команду **изменить свойства**.</span><span class="sxs-lookup"><span data-stu-id="74e38-245">Right-click the pool, and then click **Edit Properties**.</span></span>

3.  <span data-ttu-id="74e38-246">В разделе **связи** в группе **сопоставление краевого пула (для компонентов мультимедиа)** выберите в раскрывающемся списке пул краев, который вы хотите связать с этим пулом переднего плана.</span><span class="sxs-lookup"><span data-stu-id="74e38-246">In the **Associations** section, under **Associate Edge Pool (for media components)**, use the drop down box to select the Edge pool you want to associate this Front End pool with.</span></span>

4.  <span data-ttu-id="74e38-247">Нажмите **ОК**.</span><span class="sxs-lookup"><span data-stu-id="74e38-247">Click **OK**.</span></span>
