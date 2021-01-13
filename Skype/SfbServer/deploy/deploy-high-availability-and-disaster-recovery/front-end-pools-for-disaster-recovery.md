---
title: Развертывание сопряженных пулов переднего сервера для аварийного восстановления в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 2f12467c-8b90-43e6-831b-a0b096427f17
description: Вы можете использовать сопряженные пулы переднего входа для обеспечения защиты от аварийного восстановления, но это не является требованием.
ms.openlocfilehash: 7d066de60bf3ab98d73d8aeee08044803fad983c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830609"
---
# <a name="deploy-paired-front-end-pools-for-disaster-recovery-in-skype-for-business-server"></a><span data-ttu-id="45099-103">Развертывание сопряженных пулов переднего сервера для аварийного восстановления в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="45099-103">Deploy paired Front End pools for disaster recovery in Skype for Business Server</span></span>
 
<span data-ttu-id="45099-104">Вы можете использовать сопряженные пулы переднего входа для обеспечения защиты от аварийного восстановления, но это не является требованием.</span><span class="sxs-lookup"><span data-stu-id="45099-104">You may decide to use paired Front End pools to provide disaster recovery protection, but doing so is not a requirement.</span></span>
  
<span data-ttu-id="45099-105">Топологию аварийного восстановления сопряженных пулов переднего конца можно легко развернуть с помощью построитель топологий.</span><span class="sxs-lookup"><span data-stu-id="45099-105">You can easily deploy the disaster recovery topology of paired Front End pools using Topology Builder.</span></span> 
  
## <a name="to-deploy-a-pair-of-front-end-pools"></a><span data-ttu-id="45099-106">Развертывание пары интерфейсных пулов</span><span class="sxs-lookup"><span data-stu-id="45099-106">To deploy a pair of Front End pools</span></span>

1. <span data-ttu-id="45099-107">Если пулы являются новыми и еще не определены, используйте построитель топологий для создания пулов.</span><span class="sxs-lookup"><span data-stu-id="45099-107">If the pools are new and not yet defined, use Topology Builder to create the pools.</span></span>
    
2. <span data-ttu-id="45099-108">В построитель топологий щелкните правой кнопкой мыши один из двух пулов и выберите "Изменить **свойства".**</span><span class="sxs-lookup"><span data-stu-id="45099-108">In Topology Builder, right-click one of the two pools, and then click **Edit Properties**.</span></span>
    
3. <span data-ttu-id="45099-109">Щелкните элемент **Resiliency** (Устойчивость) на левой панели и выберите **Associated Backup Pool** (Сопоставленный резервный пул) на правой панели.</span><span class="sxs-lookup"><span data-stu-id="45099-109">Click **Resiliency** in the left pane, and then select **Associated Backup Pool** in the right pane.</span></span>
    
4. <span data-ttu-id="45099-p101">В расположенном ниже поле **Associated Backup Pool** (Сопоставленный резервный пул) выберите пул, который вы хотите связать с данным пулом. Для выбора будут доступны только существующие пулы, которые еще не связаны с другим пулом.</span><span class="sxs-lookup"><span data-stu-id="45099-p101">In the box below **Associated Backup Pool**, select the pool that you want to pair with this pool. Only existing pools that are not already paired with another pool will be available to select from.</span></span>
    
5. <span data-ttu-id="45099-112">Выберите **Automatic failover and failback for Voice** (Автоматическая отработка отказа и восстановление размещения для голосовой связи) и нажмите кнопку **OK** (ОК).</span><span class="sxs-lookup"><span data-stu-id="45099-112">Select **Automatic failover and failback for Voice**, and then click **OK**.</span></span>
    
    <span data-ttu-id="45099-113">Теперь при просмотре сведений о данном пуле связанный с ним пул отображается на правой панели в области **Resiliency** (Устойчивость).</span><span class="sxs-lookup"><span data-stu-id="45099-113">When you view the details about this pool, the associated pool now appears in the right pane under **Resiliency**.</span></span> 
    
6. <span data-ttu-id="45099-114">Используйте построитель топологий для публикации топологии.</span><span class="sxs-lookup"><span data-stu-id="45099-114">Use Topology Builder to publish the topology.</span></span>
    
7. <span data-ttu-id="45099-115">Если два эти пула еще не были развернуты, разверните их для завершения настройки.</span><span class="sxs-lookup"><span data-stu-id="45099-115">If the two pools were not yet deployed, deploy them now and the configuration will be complete.</span></span> <span data-ttu-id="45099-116">Вы можете пропустить последние шаги в этой процедуре.</span><span class="sxs-lookup"><span data-stu-id="45099-116">You can skip the final steps in this procedure.</span></span>
    
    <span data-ttu-id="45099-117">Однако если пулы уже были развернуты до определения парной связи, необходимо выполнить следующие заключительные действия.</span><span class="sxs-lookup"><span data-stu-id="45099-117">However, if the pools were already deployed before you defined the paired relationship, you must complete the following final steps.</span></span>
    
8. <span data-ttu-id="45099-118">Выполните следующую команду на каждом сервере переднего плана в обоих пулах:</span><span class="sxs-lookup"><span data-stu-id="45099-118">On every Front End Server in both pools, run the following:</span></span>
    
   ```powershell
   <system drive>\Program Files\Skype for Business Server 2019\Deployment\Bootstrapper.exe 
   ```

    <span data-ttu-id="45099-119">Это позволяет настроить остальные службы, необходимые для правильной работы резервного связывания.</span><span class="sxs-lookup"><span data-stu-id="45099-119">This configures other services required for backup pairing to work correctly.</span></span>
    
9. <span data-ttu-id="45099-120">Когда Bootstrapper завершит установку необходимых компонентов для сопряжения резервных копий на каждом сервере переднего сервера в обоих пулах, обязательно повторно применив все существующие накопительные обновления, которые ранее применялись на этих серверах переднего сервера в обоих пулах, а затем продолжите выполнение следующего шага.</span><span class="sxs-lookup"><span data-stu-id="45099-120">Once Bootstrapper finishes installing the required components for backup pairing on every Front end Server in both pools, please be sure to re-apply any existing Cumulative Update that was previously applied on these Front End Servers in both pools and then continue with the next step.</span></span>

10. <span data-ttu-id="45099-121">В командной области Skype для бизнеса Server запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="45099-121">From a Skype for Business Server Management Shell command prompt, run the following:</span></span> 
    
   ```powershell
   Start-CsWindowsService -Name LYNCBACKUP
   ```

11. <span data-ttu-id="45099-122">Принудительно синхронизируются данные пользователей и конференций обоих пулов с помощью следующих cmdlets:</span><span class="sxs-lookup"><span data-stu-id="45099-122">Force the user and conference data of both pools to be synchronized with each other with the following cmdlets:</span></span>
    
    ```powershell
    Invoke-CsBackupServiceSync -PoolFqdn <Pool1 FQDN>
    ```

    ```powershell
    Invoke-CsBackupServiceSync -PoolFqdn <Pool2 FQDN>
    ```

    <span data-ttu-id="45099-123">Синхронизация данных может занять некоторое время.</span><span class="sxs-lookup"><span data-stu-id="45099-123">Synchronizing the data may take some time.</span></span> <span data-ttu-id="45099-124">Можно использовать следующие командлеты для проверки состояния.</span><span class="sxs-lookup"><span data-stu-id="45099-124">You can use the following cmdlets to check the status.</span></span> <span data-ttu-id="45099-125">Убедитесь, что состояние в обоих направлениях находится в стабильном состоянии.</span><span class="sxs-lookup"><span data-stu-id="45099-125">Make sure that the status in both directions is in steady state.</span></span>
    
    ```powershell
    Get-CsBackupServiceStatus -PoolFqdn <Pool1 FQDN>
    ```

    ```powershell
    Get-CsBackupServiceStatus -PoolFqdn <Pool2 FQDN>
    ```

> [!NOTE]
> <span data-ttu-id="45099-126">Параметр **"Автоматическая** откат и откат для голосовой связи" и связанные интервалы времени в построителье топологий применяются только к функциям устойчивости голосовой связи, которые были представлены в Lync Server.</span><span class="sxs-lookup"><span data-stu-id="45099-126">The **Automatic failover and failback for Voice** option and the associated time intervals in Topology Builder apply only to the voice resiliency features that were introduced in Lync Server.</span></span> <span data-ttu-id="45099-127">Выбор данного параметра не подразумевает, что отработка отказа пулом, описанная в настоящем документе, является автоматической.</span><span class="sxs-lookup"><span data-stu-id="45099-127">Selecting this option does not imply that the pool failover discussed in this document is automatic.</span></span> <span data-ttu-id="45099-128">Отработка отказа и восстановление размещения пула всегда требуют от администратора ручного вызова соответствующих командлетов.</span><span class="sxs-lookup"><span data-stu-id="45099-128">Pool failover and failback always require an administrator to manually invoke the failover and failback cmdlets, respectively.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="45099-129">См. также</span><span class="sxs-lookup"><span data-stu-id="45099-129">See also</span></span>

[<span data-ttu-id="45099-130">Аварийное восстановление пула переднего сервера в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="45099-130">Front End pool disaster recovery in Skype for Business Server</span></span>](../../plan-your-deployment/high-availability-and-disaster-recovery/disaster-recovery.md)
