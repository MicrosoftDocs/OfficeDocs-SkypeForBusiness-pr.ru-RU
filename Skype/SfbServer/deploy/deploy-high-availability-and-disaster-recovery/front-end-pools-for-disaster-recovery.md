---
title: Развертывание попарных пулов переднего плана для аварийного восстановления в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2f12467c-8b90-43e6-831b-a0b096427f17
description: Вам может потребоваться использовать сопряженные интерфейсные пулы для обеспечения аварийного восстановления, однако это не обязательное требование.
ms.openlocfilehash: 4aa24c3a5150efbea87cd3837aca9216f047b11e
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/07/2019
ms.locfileid: "36240039"
---
# <a name="deploy-paired-front-end-pools-for-disaster-recovery-in-skype-for-business-server"></a><span data-ttu-id="28d54-103">Развертывание попарных пулов переднего плана для аварийного восстановления в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="28d54-103">Deploy paired Front End pools for disaster recovery in Skype for Business Server</span></span>
 
<span data-ttu-id="28d54-104">Вам может потребоваться использовать сопряженные интерфейсные пулы для обеспечения аварийного восстановления, однако это не обязательное требование.</span><span class="sxs-lookup"><span data-stu-id="28d54-104">You may decide to use paired Front End pools to provide disaster recovery protection, but doing so is not a requirement.</span></span>
  
<span data-ttu-id="28d54-105">Топологию аварийного восстановления для сопряженных пулов переднего плана можно легко развернуть с помощью построителя топологии.</span><span class="sxs-lookup"><span data-stu-id="28d54-105">You can easily deploy the disaster recovery topology of paired Front End pools using Topology Builder.</span></span> 
  
## <a name="to-deploy-a-pair-of-front-end-pools"></a><span data-ttu-id="28d54-106">Развертывание пары интерфейсных пулов</span><span class="sxs-lookup"><span data-stu-id="28d54-106">To deploy a pair of Front End pools</span></span>

1. <span data-ttu-id="28d54-107">Если вы еще не определили пулы, используйте построитель топологии для создания пулов.</span><span class="sxs-lookup"><span data-stu-id="28d54-107">If the pools are new and not yet defined, use Topology Builder to create the pools.</span></span>
    
2. <span data-ttu-id="28d54-108">В построителе топологии щелкните правой кнопкой мыши один из двух пулов и выберите команду **изменить свойства**.</span><span class="sxs-lookup"><span data-stu-id="28d54-108">In Topology Builder, right-click one of the two pools, and then click **Edit Properties**.</span></span>
    
3. <span data-ttu-id="28d54-109">Щелкните элемент **Устойчивость** на левой панели и выберите **Связанный резервный пул** на правой панели.</span><span class="sxs-lookup"><span data-stu-id="28d54-109">Click **Resiliency** in the left pane, and then select **Associated Backup Pool** in the right pane.</span></span>
    
4. <span data-ttu-id="28d54-p101">В расположенном ниже поле **Связанный резервный пул** выберите пул, который вы хотите связать с данным пулом. Для выбора будут доступны только существующие пулы, которые еще не связаны с другим пулом.</span><span class="sxs-lookup"><span data-stu-id="28d54-p101">In the box below **Associated Backup Pool**, select the pool that you want to pair with this pool. Only existing pools that are not already paired with another pool will be available to select from.</span></span>
    
5. <span data-ttu-id="28d54-112">Выберите **Автоматическая обработка отказов и восстановление после отказа для голосовой связи** и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="28d54-112">Select **Automatic failover and failback for Voice**, and then click **OK**.</span></span>
    
    <span data-ttu-id="28d54-113">Теперь при просмотре сведений о данном пуле связанный с ним пул отображается на правой панели в области **Устойчивость**. </span><span class="sxs-lookup"><span data-stu-id="28d54-113">When you view the details about this pool, the associated pool now appears in the right pane under **Resiliency**.</span></span> 
    
6. <span data-ttu-id="28d54-114">Опубликуйте топологию с помощью построителя топологии.</span><span class="sxs-lookup"><span data-stu-id="28d54-114">Use Topology Builder to publish the topology.</span></span>
    
7. <span data-ttu-id="28d54-p102">Если два эти пула еще не были развернуты, разверните их для завершения настройки. Вы можете пропустить два последних действия данной процедуры.</span><span class="sxs-lookup"><span data-stu-id="28d54-p102">If the two pools were not yet deployed, deploy them now and the configuration will be complete. You can skip the final two steps in this procedure.</span></span>
    
    <span data-ttu-id="28d54-117">Однако если на момент определения связанного отношения пулы были уже развернуты, следует выполнить два последних действия.</span><span class="sxs-lookup"><span data-stu-id="28d54-117">However, if the pools were already deployed before you defined the paired relationship, you must complete the following two final steps.</span></span>
    
8. <span data-ttu-id="28d54-118">Выполните следующую команду на каждом сервере переднего плана в обоих пулах:</span><span class="sxs-lookup"><span data-stu-id="28d54-118">On every Front End Server in both pools, run the following:</span></span>
    
   ```
   <system drive>\Program Files\Skype for Business Server 2015\Deployment\Bootstrapper.exe 
   ```

    <span data-ttu-id="28d54-119">Это позволяет настроить остальные службы, необходимые для правильной работы резервного сопряжения.</span><span class="sxs-lookup"><span data-stu-id="28d54-119">This configures other services required for backup pairing to work correctly.</span></span>
    
9. <span data-ttu-id="28d54-120">В командной строке консоли управления Skype для бизнеса Server выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="28d54-120">From a Skype for Business Server Management Shell command prompt, run the following:</span></span> 
    
   ```
   Start-CsWindowsService -Name LYNCBACKUP
   ```

10. <span data-ttu-id="28d54-121">Выполните принудительную синхронизацию данных о пользователях и конференциях между двумя пулами с помощью следующих командлетов:</span><span class="sxs-lookup"><span data-stu-id="28d54-121">Force the user and conference data of both pools to be synchronized with each other, with the following cmdlets:</span></span>
    
    ```
    Invoke-CsBackupServiceSync -PoolFqdn <Pool1 FQDN>
    ```

    ```
    Invoke-CsBackupServiceSync -PoolFqdn <Pool2 FQDN>
    ```

    <span data-ttu-id="28d54-p103">Синхронизация данных может занять некоторое время. Можно использовать следующие командлеты для проверки состояния. Убедитесь, что для обоих направлений состояние является стационарным.</span><span class="sxs-lookup"><span data-stu-id="28d54-p103">Synchronizing the data may take some time. You can use the following cmdlets to check the status. Make sure that the status in both directions is in steady state.</span></span>
    
    ```
    Get-CsBackupServiceStatus -PoolFqdn <Pool1 FQDN>
    ```

    ```
    Get-CsBackupServiceStatus -PoolFqdn <Pool2 FQDN>
    ```

> [!NOTE]
> <span data-ttu-id="28d54-125">Параметры **автоматического перехода на другой ресурс и восстановление при сбое для голосовой связи** , а также соответствующие интервалы времени в построителе топологии применяются только к функциям устойчивости голоса, которые появились в Lync Server.</span><span class="sxs-lookup"><span data-stu-id="28d54-125">The **Automatic failover and failback for Voice** option and the associated time intervals in Topology Builder apply only to the voice resiliency features that were introduced in Lync Server.</span></span> <span data-ttu-id="28d54-126">Selecting this option does not imply that the pool failover discussed in this document is automatic.</span><span class="sxs-lookup"><span data-stu-id="28d54-126">Selecting this option does not imply that the pool failover discussed in this document is automatic.</span></span> <span data-ttu-id="28d54-127">Pool failover and failback always require an administrator to manually invoke the failover and failback cmdlets, respectively.</span><span class="sxs-lookup"><span data-stu-id="28d54-127">Pool failover and failback always require an administrator to manually invoke the failover and failback cmdlets, respectively.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="28d54-128">См. также</span><span class="sxs-lookup"><span data-stu-id="28d54-128">See also</span></span>

[<span data-ttu-id="28d54-129">Внешнее аварийное восстановление пула в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="28d54-129">Front End pool disaster recovery in Skype for Business Server</span></span>](../../plan-your-deployment/high-availability-and-disaster-recovery/disaster-recovery.md)
