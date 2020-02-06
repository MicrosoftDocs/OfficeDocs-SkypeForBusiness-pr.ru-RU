---
title: Развертывание попарных пулов переднего плана для аварийного восстановления в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 2f12467c-8b90-43e6-831b-a0b096427f17
description: Вам может потребоваться использовать сопряженные интерфейсные пулы для обеспечения аварийного восстановления, однако это не обязательное требование.
ms.openlocfilehash: 63b9c55aad2b31e01eec506ce28e54d2145ee636
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41790087"
---
# <a name="deploy-paired-front-end-pools-for-disaster-recovery-in-skype-for-business-server"></a><span data-ttu-id="fc869-103">Развертывание попарных пулов переднего плана для аварийного восстановления в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="fc869-103">Deploy paired Front End pools for disaster recovery in Skype for Business Server</span></span>
 
<span data-ttu-id="fc869-104">Вам может потребоваться использовать сопряженные интерфейсные пулы для обеспечения аварийного восстановления, однако это не обязательное требование.</span><span class="sxs-lookup"><span data-stu-id="fc869-104">You may decide to use paired Front End pools to provide disaster recovery protection, but doing so is not a requirement.</span></span>
  
<span data-ttu-id="fc869-105">Топологию аварийного восстановления для сопряженных пулов переднего плана можно легко развернуть с помощью построителя топологии.</span><span class="sxs-lookup"><span data-stu-id="fc869-105">You can easily deploy the disaster recovery topology of paired Front End pools using Topology Builder.</span></span> 
  
## <a name="to-deploy-a-pair-of-front-end-pools"></a><span data-ttu-id="fc869-106">Развертывание пары интерфейсных пулов</span><span class="sxs-lookup"><span data-stu-id="fc869-106">To deploy a pair of Front End pools</span></span>

1. <span data-ttu-id="fc869-107">Если вы еще не определили пулы, используйте построитель топологии для создания пулов.</span><span class="sxs-lookup"><span data-stu-id="fc869-107">If the pools are new and not yet defined, use Topology Builder to create the pools.</span></span>
    
2. <span data-ttu-id="fc869-108">В построителе топологии щелкните правой кнопкой мыши один из двух пулов и выберите команду **изменить свойства**.</span><span class="sxs-lookup"><span data-stu-id="fc869-108">In Topology Builder, right-click one of the two pools, and then click **Edit Properties**.</span></span>
    
3. <span data-ttu-id="fc869-109">Щелкните элемент **Устойчивость** на левой панели и выберите **Связанный резервный пул** на правой панели.</span><span class="sxs-lookup"><span data-stu-id="fc869-109">Click **Resiliency** in the left pane, and then select **Associated Backup Pool** in the right pane.</span></span>
    
4. <span data-ttu-id="fc869-p101">В расположенном ниже поле **Связанный резервный пул** выберите пул, который вы хотите связать с данным пулом. Для выбора будут доступны только существующие пулы, которые еще не связаны с другим пулом.</span><span class="sxs-lookup"><span data-stu-id="fc869-p101">In the box below **Associated Backup Pool**, select the pool that you want to pair with this pool. Only existing pools that are not already paired with another pool will be available to select from.</span></span>
    
5. <span data-ttu-id="fc869-112">Выберите **Автоматическая обработка отказов и восстановление после отказа для голосовой связи** и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="fc869-112">Select **Automatic failover and failback for Voice**, and then click **OK**.</span></span>
    
    <span data-ttu-id="fc869-113">Теперь при просмотре сведений о данном пуле связанный с ним пул отображается на правой панели в области **Устойчивость**. </span><span class="sxs-lookup"><span data-stu-id="fc869-113">When you view the details about this pool, the associated pool now appears in the right pane under **Resiliency**.</span></span> 
    
6. <span data-ttu-id="fc869-114">Опубликуйте топологию с помощью построителя топологии.</span><span class="sxs-lookup"><span data-stu-id="fc869-114">Use Topology Builder to publish the topology.</span></span>
    
7. <span data-ttu-id="fc869-115">Если два эти пула еще не были развернуты, разверните их для завершения настройки.</span><span class="sxs-lookup"><span data-stu-id="fc869-115">If the two pools were not yet deployed, deploy them now and the configuration will be complete.</span></span> <span data-ttu-id="fc869-116">Вы можете пропустить заключительные действия, описанные в этой процедуре.</span><span class="sxs-lookup"><span data-stu-id="fc869-116">You can skip the final steps in this procedure.</span></span>
    
    <span data-ttu-id="fc869-117">Тем не менее, если пулы уже развернуты до того, как вы определили связанное отношение, необходимо выполнить следующие действия.</span><span class="sxs-lookup"><span data-stu-id="fc869-117">However, if the pools were already deployed before you defined the paired relationship, you must complete the following final steps.</span></span>
    
8. <span data-ttu-id="fc869-118">Выполните следующую команду на каждом сервере переднего плана в обоих пулах:</span><span class="sxs-lookup"><span data-stu-id="fc869-118">On every Front End Server in both pools, run the following:</span></span>
    
   ```powershell
   <system drive>\Program Files\Skype for Business Server 2019\Deployment\Bootstrapper.exe 
   ```

    <span data-ttu-id="fc869-119">Это позволяет настроить остальные службы, необходимые для правильной работы резервного сопряжения.</span><span class="sxs-lookup"><span data-stu-id="fc869-119">This configures other services required for backup pairing to work correctly.</span></span>
    
9. <span data-ttu-id="fc869-120">После того как загрузчик закончит установку необходимых компонентов для создания пар резервных копий на каждом сервере переднего плана в обоих пулах, необходимо повторно применить к нему существующее накопительное обновление, которое вы уже использовали на этих серверах на следующем этапе.</span><span class="sxs-lookup"><span data-stu-id="fc869-120">Once Bootstrapper finishes installing the required components for backup pairing on every Front end Server in both pools, please be sure to re-apply any existing Cumulative Update that was previously applied on these Front End Servers in both pools and then continue with the next step.</span></span>

10. <span data-ttu-id="fc869-121">В командной строке консоли управления Skype для бизнеса Server выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="fc869-121">From a Skype for Business Server Management Shell command prompt, run the following:</span></span> 
    
   ```powershell
   Start-CsWindowsService -Name LYNCBACKUP
   ```

11. <span data-ttu-id="fc869-122">Настройте синхронизацию данных пользователя и конференции обоих пулов друг с другом с помощью следующих командлетов:</span><span class="sxs-lookup"><span data-stu-id="fc869-122">Force the user and conference data of both pools to be synchronized with each other with the following cmdlets:</span></span>
    
    ```powershell
    Invoke-CsBackupServiceSync -PoolFqdn <Pool1 FQDN>
    ```

    ```powershell
    Invoke-CsBackupServiceSync -PoolFqdn <Pool2 FQDN>
    ```

    <span data-ttu-id="fc869-p103">Синхронизация данных может занять некоторое время. Можно использовать следующие командлеты для проверки состояния. Убедитесь, что для обоих направлений состояние является стационарным.</span><span class="sxs-lookup"><span data-stu-id="fc869-p103">Synchronizing the data may take some time. You can use the following cmdlets to check the status. Make sure that the status in both directions is in steady state.</span></span>
    
    ```powershell
    Get-CsBackupServiceStatus -PoolFqdn <Pool1 FQDN>
    ```

    ```powershell
    Get-CsBackupServiceStatus -PoolFqdn <Pool2 FQDN>
    ```

> [!NOTE]
> <span data-ttu-id="fc869-126">Параметры **автоматического перехода на другой ресурс и восстановление при сбое для голосовой связи** , а также соответствующие интервалы времени в построителе топологии применяются только к функциям устойчивости голоса, которые появились в Lync Server.</span><span class="sxs-lookup"><span data-stu-id="fc869-126">The **Automatic failover and failback for Voice** option and the associated time intervals in Topology Builder apply only to the voice resiliency features that were introduced in Lync Server.</span></span> <span data-ttu-id="fc869-127">Selecting this option does not imply that the pool failover discussed in this document is automatic.</span><span class="sxs-lookup"><span data-stu-id="fc869-127">Selecting this option does not imply that the pool failover discussed in this document is automatic.</span></span> <span data-ttu-id="fc869-128">Pool failover and failback always require an administrator to manually invoke the failover and failback cmdlets, respectively.</span><span class="sxs-lookup"><span data-stu-id="fc869-128">Pool failover and failback always require an administrator to manually invoke the failover and failback cmdlets, respectively.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="fc869-129">См. также</span><span class="sxs-lookup"><span data-stu-id="fc869-129">See also</span></span>

[<span data-ttu-id="fc869-130">Внешнее аварийное восстановление пула в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="fc869-130">Front End pool disaster recovery in Skype for Business Server</span></span>](../../plan-your-deployment/high-availability-and-disaster-recovery/disaster-recovery.md)
