---
title: 'Lync Server 2013: развертывание подключенных пулов переднего плана для аварийного восстановления'
description: 'Lync Server 2013: развертывание подключенных пулов переднего плана для аварийного восстановления.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying paired Front End pools for disaster recovery
ms:assetid: 2f12467c-8b90-43e6-831b-a0b096427f17
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204773(v=OCS.15)
ms:contentKeyID: 48183727
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4846121f301d2bc7be1af9b58f0a0fef3f88e6d6
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48555905"
---
# <a name="deploying-paired-front-end-pools-for-disaster-recovery-in-lync-server-2013"></a><span data-ttu-id="934b1-103">Развертывание подключенных пулов переднего плана для аварийного восстановления в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="934b1-103">Deploying paired Front End pools for disaster recovery in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="934b1-104">_**Последнее изменение темы:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="934b1-104">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="934b1-105">Топологию аварийного восстановления в связанных пулах переднего плана можно легко развернуть с помощью построителя топологий.</span><span class="sxs-lookup"><span data-stu-id="934b1-105">You can easily deploy the disaster recovery topology of paired Front End pools using Topology Builder.</span></span>

<div>

## <a name="to-deploy-a-pair-of-front-end-pools"></a><span data-ttu-id="934b1-106">Развертывание пары интерфейсных пулов</span><span class="sxs-lookup"><span data-stu-id="934b1-106">To deploy a pair of Front End pools</span></span>

1.  <span data-ttu-id="934b1-107">Если пулы новые и еще не определены, используйте построитель топологий для создания пулов.</span><span class="sxs-lookup"><span data-stu-id="934b1-107">If the pools are new and not yet defined, use Topology Builder to create the pools.</span></span>

2.  <span data-ttu-id="934b1-108">В построителе топологий щелкните правой кнопкой мыши один из двух пулов и выберите команду **изменить свойства**.</span><span class="sxs-lookup"><span data-stu-id="934b1-108">In Topology Builder, right-click one of the two pools, and then click **Edit Properties**.</span></span>

3.  <span data-ttu-id="934b1-109">Щелкните элемент **Resiliency** (Устойчивость) на левой панели и выберите **Associated Backup Pool** (Сопоставленный резервный пул) на правой панели.</span><span class="sxs-lookup"><span data-stu-id="934b1-109">Click **Resiliency** in the left pane, and then select **Associated Backup Pool** in the right pane.</span></span>

4.  <span data-ttu-id="934b1-p101">В расположенном ниже поле **Associated Backup Pool** (Сопоставленный резервный пул) выберите пул, который вы хотите связать с данным пулом. Для выбора будут доступны только существующие пулы, которые еще не связаны с другим пулом.</span><span class="sxs-lookup"><span data-stu-id="934b1-p101">In the box below **Associated Backup Pool**, select the pool that you want to pair with this pool. Only existing pools that are not already paired with another pool will be available to select from.</span></span>
    
    <span data-ttu-id="934b1-112">![36080581 — db76 — 497d — bf9e – f02b39574d0e](images/JJ204773.36080581-db76-497d-bf9e-f02b39574d0e(OCS.15).png "36080581 — db76 — 497d — bf9e – f02b39574d0e")</span><span class="sxs-lookup"><span data-stu-id="934b1-112">![36080581-db76-497d-bf9e-f02b39574d0e](images/JJ204773.36080581-db76-497d-bf9e-f02b39574d0e(OCS.15).png "36080581-db76-497d-bf9e-f02b39574d0e")</span></span>  

5.  <span data-ttu-id="934b1-113">Выберите **Automatic failover and failback for Voice** (Автоматическая отработка отказа и восстановление размещения для голосовой связи) и нажмите кнопку **OK** (ОК).</span><span class="sxs-lookup"><span data-stu-id="934b1-113">Select **Automatic failover and failback for Voice**, and then click **OK**.</span></span>
    
    <span data-ttu-id="934b1-114">Теперь при просмотре сведений о данном пуле связанный с ним пул отображается на правой панели в области **Resiliency** (Устойчивость).</span><span class="sxs-lookup"><span data-stu-id="934b1-114">When you view the details about this pool, the associated pool now appears in the right pane under **Resiliency**.</span></span>

6.  <span data-ttu-id="934b1-115">Опубликуйте топологию с помощью построителя топологий.</span><span class="sxs-lookup"><span data-stu-id="934b1-115">Use Topology Builder to publish the topology.</span></span>

7.  <span data-ttu-id="934b1-p102">Если два эти пула еще не были развернуты, разверните их для завершения настройки. Вы можете пропустить два последних действия данной процедуры.</span><span class="sxs-lookup"><span data-stu-id="934b1-p102">If the two pools were not yet deployed, deploy them now and the configuration will be complete. You can skip the final two steps in this procedure.</span></span>
    
    <span data-ttu-id="934b1-118">Однако если на момент определения связанного отношения пулы были уже развернуты, следует выполнить два последних действия.</span><span class="sxs-lookup"><span data-stu-id="934b1-118">However, if the pools were already deployed before you defined the paired relationship, you must complete the following two final steps.</span></span>

8.  <span data-ttu-id="934b1-119">Выполните следующую команду на каждом сервере переднего плана в обоих пулах:</span><span class="sxs-lookup"><span data-stu-id="934b1-119">On every Front End Server in both pools, run the following:</span></span>
    ```console
    <system drive>\Program Files\Microsoft Lync Server 2013\Deployment\Bootstrapper.exe 
    ```
    <span data-ttu-id="934b1-120">Это позволяет настроить остальные службы, необходимые для правильной работы резервного связывания.</span><span class="sxs-lookup"><span data-stu-id="934b1-120">This configures other services required for backup pairing to work correctly.</span></span>

9.  <span data-ttu-id="934b1-121">В командной строке Командная консоль Lync Server выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="934b1-121">From a Lync Server Management Shell command prompt, run the following:</span></span>
    ```powershell
    Start-CsWindowsService -Name LYNCBACKUP
    ```
10. <span data-ttu-id="934b1-122">Выполните принудительную синхронизацию данных о пользователях и конференциях между двумя пулами с помощью следующих командлетов:</span><span class="sxs-lookup"><span data-stu-id="934b1-122">Force the user and conference data of both pools to be synchronized with each other, with the following cmdlets:</span></span>
    
       ```powershell
        Invoke-CsBackupServiceSync -PoolFqdn <Pool1 FQDN>
       ```
    
       ```powershell
        Invoke-CsBackupServiceSync -PoolFqdn <Pool2 FQDN>
       ```
    
    <span data-ttu-id="934b1-123">Синхронизация данных может занять некоторое время.</span><span class="sxs-lookup"><span data-stu-id="934b1-123">Synchronizing the data may take some time.</span></span> <span data-ttu-id="934b1-124">Можно использовать следующие командлеты для проверки состояния.</span><span class="sxs-lookup"><span data-stu-id="934b1-124">You can use the following cmdlets to check the status.</span></span> <span data-ttu-id="934b1-125">Убедитесь, что состояние в обоих направлениях находится в стабильном состоянии.</span><span class="sxs-lookup"><span data-stu-id="934b1-125">Make sure that the status in both directions is in steady state.</span></span>
    
       ```powershell
        Get-CsBackupServiceStatus -PoolFqdn <Pool1 FQDN>
       ```
    
       ```powershell
        Get-CsBackupServiceStatus -PoolFqdn <Pool2 FQDN>
       ```

<div class="">


> [!NOTE]  
> <span data-ttu-id="934b1-126">Параметры <STRONG>автоматической отработки отказа и восстановления размещения для голосовой связи</STRONG> , а также соответствующие интервалы времени в построителе топологий применяются только к функциям устойчивости голосовой связи, которые были представлены в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="934b1-126">The <STRONG>Automatic failover and failback for Voice</STRONG> option and the associated time intervals in Topology Builder apply only to the voice resiliency features that were introduced in Lync Server 2010.</span></span> <span data-ttu-id="934b1-127">Выбор данного параметра не подразумевает, что отработка отказа пулом, описанная в настоящем документе, является автоматической.</span><span class="sxs-lookup"><span data-stu-id="934b1-127">Selecting this option does not imply that the pool failover discussed in this document is automatic.</span></span> <span data-ttu-id="934b1-128">Отработка отказа и восстановление размещения пула всегда требуют от администратора ручного вызова соответствующих командлетов.</span><span class="sxs-lookup"><span data-stu-id="934b1-128">Pool failover and failback always require an administrator to manually invoke the failover and failback cmdlets, respectively.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

