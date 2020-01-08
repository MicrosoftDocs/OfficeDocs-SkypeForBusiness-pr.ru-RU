---
title: 'Lync Server 2013: развертывание сопоставленных пулов переднего плана для аварийного восстановления'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deploying paired Front End pools for disaster recovery
ms:assetid: 2f12467c-8b90-43e6-831b-a0b096427f17
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204773(v=OCS.15)
ms:contentKeyID: 48183727
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c01549722fe04d0a4833a9d2c37fd5e85dc575a7
ms.sourcegitcommit: 30ed4457d7004ba732372fee11a6f0b1baf48e05
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/08/2020
ms.locfileid: "40971123"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-paired-front-end-pools-for-disaster-recovery-in-lync-server-2013"></a><span data-ttu-id="2b33f-102">Развертывание сопоставленных пулов переднего плана для аварийного восстановления в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2b33f-102">Deploying paired Front End pools for disaster recovery in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2b33f-103">_**Тема последнего изменения:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="2b33f-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="2b33f-104">Топологию аварийного восстановления для сопряженных пулов переднего плана можно легко развернуть с помощью построителя топологии.</span><span class="sxs-lookup"><span data-stu-id="2b33f-104">You can easily deploy the disaster recovery topology of paired Front End pools using Topology Builder.</span></span>

<div>

## <a name="to-deploy-a-pair-of-front-end-pools"></a><span data-ttu-id="2b33f-105">Развертывание пары интерфейсных пулов</span><span class="sxs-lookup"><span data-stu-id="2b33f-105">To deploy a pair of Front End pools</span></span>

1.  <span data-ttu-id="2b33f-106">Если вы еще не определили пулы, используйте построитель топологии для создания пулов.</span><span class="sxs-lookup"><span data-stu-id="2b33f-106">If the pools are new and not yet defined, use Topology Builder to create the pools.</span></span>

2.  <span data-ttu-id="2b33f-107">В построителе топологии щелкните правой кнопкой мыши один из двух пулов и выберите команду **изменить свойства**.</span><span class="sxs-lookup"><span data-stu-id="2b33f-107">In Topology Builder, right-click one of the two pools, and then click **Edit Properties**.</span></span>

3.  <span data-ttu-id="2b33f-108">Щелкните элемент **Устойчивость** на левой панели и выберите **Связанный резервный пул** на правой панели.</span><span class="sxs-lookup"><span data-stu-id="2b33f-108">Click **Resiliency** in the left pane, and then select **Associated Backup Pool** in the right pane.</span></span>

4.  <span data-ttu-id="2b33f-p101">В расположенном ниже поле **Связанный резервный пул** выберите пул, который вы хотите связать с данным пулом. Для выбора будут доступны только существующие пулы, которые еще не связаны с другим пулом.</span><span class="sxs-lookup"><span data-stu-id="2b33f-p101">In the box below **Associated Backup Pool**, select the pool that you want to pair with this pool. Only existing pools that are not already paired with another pool will be available to select from.</span></span>
    
    <span data-ttu-id="2b33f-111">![36080581-db76-497d-bf9e-f02b39574d0e](images/JJ204773.36080581-db76-497d-bf9e-f02b39574d0e(OCS.15).png "36080581-db76-497d-bf9e-f02b39574d0e")</span><span class="sxs-lookup"><span data-stu-id="2b33f-111">![36080581-db76-497d-bf9e-f02b39574d0e](images/JJ204773.36080581-db76-497d-bf9e-f02b39574d0e(OCS.15).png "36080581-db76-497d-bf9e-f02b39574d0e")</span></span>  

5.  <span data-ttu-id="2b33f-112">Выберите **Автоматическая обработка отказов и восстановление после отказа для голосовой связи** и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="2b33f-112">Select **Automatic failover and failback for Voice**, and then click **OK**.</span></span>
    
    <span data-ttu-id="2b33f-113">Теперь при просмотре сведений о данном пуле связанный с ним пул отображается на правой панели в области **Устойчивость**. </span><span class="sxs-lookup"><span data-stu-id="2b33f-113">When you view the details about this pool, the associated pool now appears in the right pane under **Resiliency**.</span></span>

6.  <span data-ttu-id="2b33f-114">Опубликуйте топологию с помощью построителя топологии.</span><span class="sxs-lookup"><span data-stu-id="2b33f-114">Use Topology Builder to publish the topology.</span></span>

7.  <span data-ttu-id="2b33f-p102">Если два эти пула еще не были развернуты, разверните их для завершения настройки. Вы можете пропустить два последних действия данной процедуры.</span><span class="sxs-lookup"><span data-stu-id="2b33f-p102">If the two pools were not yet deployed, deploy them now and the configuration will be complete. You can skip the final two steps in this procedure.</span></span>
    
    <span data-ttu-id="2b33f-117">Однако если на момент определения связанного отношения пулы были уже развернуты, следует выполнить два последних действия.</span><span class="sxs-lookup"><span data-stu-id="2b33f-117">However, if the pools were already deployed before you defined the paired relationship, you must complete the following two final steps.</span></span>

8.  <span data-ttu-id="2b33f-118">Выполните следующую команду на каждом сервере переднего плана в обоих пулах:</span><span class="sxs-lookup"><span data-stu-id="2b33f-118">On every Front End Server in both pools, run the following:</span></span>
    ```console
    <system drive>\Program Files\Microsoft Lync Server 2013\Deployment\Bootstrapper.exe 
    ```
    <span data-ttu-id="2b33f-119">Это позволяет настроить остальные службы, необходимые для правильной работы резервного сопряжения.</span><span class="sxs-lookup"><span data-stu-id="2b33f-119">This configures other services required for backup pairing to work correctly.</span></span>

9.  <span data-ttu-id="2b33f-120">В командной строке оболочки Lync Server Management Shell выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="2b33f-120">From a Lync Server Management Shell command prompt, run the following:</span></span>
    ```powershell
    Start-CsWindowsService -Name LYNCBACKUP
    ```
10. <span data-ttu-id="2b33f-121">Выполните принудительную синхронизацию данных о пользователях и конференциях между двумя пулами с помощью следующих командлетов:</span><span class="sxs-lookup"><span data-stu-id="2b33f-121">Force the user and conference data of both pools to be synchronized with each other, with the following cmdlets:</span></span>
    
       ```powershell
        Invoke-CsBackupServiceSync -PoolFqdn <Pool1 FQDN>
       ```
    
       ```powershell
        Invoke-CsBackupServiceSync -PoolFqdn <Pool2 FQDN>
       ```
    
    <span data-ttu-id="2b33f-p103">Синхронизация данных может занять некоторое время. Можно использовать следующие командлеты для проверки состояния. Убедитесь, что для обоих направлений состояние является стационарным.</span><span class="sxs-lookup"><span data-stu-id="2b33f-p103">Synchronizing the data may take some time. You can use the following cmdlets to check the status. Make sure that the status in both directions is in steady state.</span></span>
    
       ```powershell
        Get-CsBackupServiceStatus -PoolFqdn <Pool1 FQDN>
       ```
    
       ```powershell
        Get-CsBackupServiceStatus -PoolFqdn <Pool2 FQDN>
       ```

<div class="">


> [!NOTE]  
> <span data-ttu-id="2b33f-125">Параметры <STRONG>автоматического перехода на другой ресурс и восстановление при сбое для голосовой связи</STRONG> , а также соответствующие интервалы времени в построителе топологии применяются только к функциям устойчивости голоса, которые появились в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="2b33f-125">The <STRONG>Automatic failover and failback for Voice</STRONG> option and the associated time intervals in Topology Builder apply only to the voice resiliency features that were introduced in Lync Server 2010.</span></span> <span data-ttu-id="2b33f-126">Selecting this option does not imply that the pool failover discussed in this document is automatic.</span><span class="sxs-lookup"><span data-stu-id="2b33f-126">Selecting this option does not imply that the pool failover discussed in this document is automatic.</span></span> <span data-ttu-id="2b33f-127">Pool failover and failback always require an administrator to manually invoke the failover and failback cmdlets, respectively.</span><span class="sxs-lookup"><span data-stu-id="2b33f-127">Pool failover and failback always require an administrator to manually invoke the failover and failback cmdlets, respectively.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

