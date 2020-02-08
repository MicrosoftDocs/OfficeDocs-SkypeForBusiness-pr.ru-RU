---
title: 'Lync Server 2013: обновление и обновление серверов переднего плана'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Upgrade or update Front End Servers
ms:assetid: 20fa39ae-ecfb-4c72-9cc4-8e183d3c752f
ms:mtpsurl: https://technet.microsoft.com/library/JJ204736(v=OCS.15)
ms:contentKeyID: 48183597
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 14a4c5f81b88db33ba86c4410109a0943b81cb87
ms.sourcegitcommit: eb2182617d8f72f8a7ea95f7af101d10c6f4e9a0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/07/2020
ms.locfileid: "41852015"
---
<div data-xmlns="https://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="https://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="upgrade-or-update-front-end-servers-in-lync-server-2013"></a><span data-ttu-id="fc41b-102">Upgrade or update Front End Servers in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fc41b-102">Upgrade or update Front End Servers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fc41b-103">_**Тема последнего изменения:** 2013-06-28_</span><span class="sxs-lookup"><span data-stu-id="fc41b-103">_**Topic Last Modified:** 2013-06-28_</span></span>

<span data-ttu-id="fc41b-104">Серверы переднего плана в пуле выпуска Enterprise Edition объединены в *домены обновления*.</span><span class="sxs-lookup"><span data-stu-id="fc41b-104">The Front End Servers in an Enterprise Edition pool are organized into *upgrade domains*.</span></span> <span data-ttu-id="fc41b-105">Это подмножество серверов переднего плана в пуле.</span><span class="sxs-lookup"><span data-stu-id="fc41b-105">These are subsets of Front End Servers in the pool.</span></span> <span data-ttu-id="fc41b-106">Домены обновления создаются автоматически с помощью построителя топологии.</span><span class="sxs-lookup"><span data-stu-id="fc41b-106">Upgrade Domains are created automatically by Topology Builder.</span></span>

<span data-ttu-id="fc41b-107">Когда вы обновляете серверы, вы должны сделать это одним доменом обновления за один раз.</span><span class="sxs-lookup"><span data-stu-id="fc41b-107">When you upgrade servers, you must do so one Upgrade Domain at a time.</span></span> <span data-ttu-id="fc41b-108">Переведите каждый сервер в один домен обновления вниз, обновите и перезапустите его перед переходом к другому домену обновления.</span><span class="sxs-lookup"><span data-stu-id="fc41b-108">Bring each Server in one Upgrade Domain down, upgrade it, and then restart it before you move on to another Upgrade Domain.</span></span> <span data-ttu-id="fc41b-109">Не забудьте следить за тем, какие домены обновления и серверы были обновлены до сих пор.</span><span class="sxs-lookup"><span data-stu-id="fc41b-109">Be sure to keep track of which Upgrade Domains and Servers that you have upgraded so far.</span></span> <span data-ttu-id="fc41b-110">При обновлении каждого сервера используйте следующую блок-схему.</span><span class="sxs-lookup"><span data-stu-id="fc41b-110">Use the following flowchart diagram when upgrading each server.</span></span>

![Обновление и обновление серверов переднего плана](images/upgradeupdatefrontendserverslync2013.png)

<div>

## <a name="to-apply-an-upgrade-to-the-front-end-servers-in-a-pool"></a><span data-ttu-id="fc41b-112">Установка обновления на серверы переднего плана в пуле</span><span class="sxs-lookup"><span data-stu-id="fc41b-112">To apply an upgrade to the Front End servers in a pool</span></span>

1.  <span data-ttu-id="fc41b-113">На сервере переднего плана в пуле выполните следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="fc41b-113">On a Front End Server in the pool, run the following cmdlet:</span></span>
    
    <span data-ttu-id="fc41b-114">**Get-CsPoolUpgradeReadinessState**</span><span class="sxs-lookup"><span data-stu-id="fc41b-114">**Get-CsPoolUpgradeReadinessState**</span></span>
    
    <span data-ttu-id="fc41b-115">Если значение аргумента " *пулупградестате* " **занято**, подождите 10 минут и повторите попытку **Get-кспулупградереадинессстате** .</span><span class="sxs-lookup"><span data-stu-id="fc41b-115">If the value of *PoolUpgradeState* is **Busy**, wait for 10 minutes, and then try **Get-CsPoolUpgradeReadinessState** again.</span></span> <span data-ttu-id="fc41b-116">Если **вы видите по** крайней мере три последовательных интервалов, по истечении 10 минут между попытками, или, если вы видите результат **инсуффиЦиентактивефронтендс** для **пулупградестате,** у него возникает ошибка.</span><span class="sxs-lookup"><span data-stu-id="fc41b-116">If you see **Busy** for at least three consecutive times, after waiting 10 minutes in between each attempt, or if you see any result of **InsufficientActiveFrontEnds** for **PoolUpgradeState,** then there is an issue with the pool.</span></span> <span data-ttu-id="fc41b-117">Если этот пул связан с другим пулом переднего плана в топологии аварийного восстановления, вы должны восстановить его из пула резервных копий, а затем обновить серверы в этом пуле.</span><span class="sxs-lookup"><span data-stu-id="fc41b-117">If this pool is paired with another Front End pool in a disaster recovery topology, you should fail the pool over to the backup pool, and then update the servers in this pool.</span></span> <span data-ttu-id="fc41b-118">Дополнительные сведения можно найти [в разделе отказ в пуле в Lync Server 2013](lync-server-2013-failing-over-a-pool.md).</span><span class="sxs-lookup"><span data-stu-id="fc41b-118">For details, see [Failing over a pool in Lync Server 2013](lync-server-2013-failing-over-a-pool.md).</span></span>
    
    <span data-ttu-id="fc41b-119">Если значение параметра *Пулупградестате* **Готово**, перейдите к действию 2.</span><span class="sxs-lookup"><span data-stu-id="fc41b-119">If the value of *PoolUpgradeState* is **Ready**, go to step 2.</span></span>

2.  <span data-ttu-id="fc41b-120">Командлет **Get-кспулупградереадинессстате** также возвращает сведения о каждом домене обновления в пуле и о том, какие серверные серверы находятся в каждом домене обновления.</span><span class="sxs-lookup"><span data-stu-id="fc41b-120">The **Get-CsPoolUpgradeReadinessState** cmdlet also returns information about each upgrade domain in the pool, and about which Front End Servers are in each upgrade domain.</span></span> <span data-ttu-id="fc41b-121">Если значение **реадифорупграде** **для домена** обновления, содержащего сервер или серверы, который вы хотите обновить, вы можете безопасно обновить сейчас.</span><span class="sxs-lookup"><span data-stu-id="fc41b-121">If the **ReadyforUpgrade** value is **True** for the upgrade domain that contains the server or servers you want to upgrade, you can safely upgrade those servers now.</span></span> <span data-ttu-id="fc41b-122">Для этого выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="fc41b-122">To do so, do the following:</span></span>
    
    1.  <span data-ttu-id="fc41b-123">Остановите новые соединения с серверами переднего плана, которые вы собираетесь обновить с `Stop-CsWindowsService -Graceful -Verbose` помощью командлета.</span><span class="sxs-lookup"><span data-stu-id="fc41b-123">Stop new connections to the Front End Servers you are going to upgrade by using the `Stop-CsWindowsService -Graceful -Verbose` cmdlet.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="fc41b-124">Если вы выполняете эти обновления сервера во время запланированного времени простоя сервера, вы можете выполнить этот командлет без параметра-<STRONG>graceful</STRONG>, как описано ниже: <STRONG>Stop-ксвиндовссервице</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="fc41b-124">If you are performing these server upgrades during a scheduled server downtime, you can run this cmdlet without the ‘-<STRONG>Graceful</STRONG>‘ parameter, as follows: <STRONG>Stop-CsWindowsService</STRONG>.</span></span> <span data-ttu-id="fc41b-125">Это приведет к немедленному завершению работы служб, не дожидаясь, пока не будут заполнены все существующие запросы на обслуживание.</span><span class="sxs-lookup"><span data-stu-id="fc41b-125">This will immediately shut down services, without waiting for all existing service requests to be filled.</span></span>

        
        </div>
    
    2.  <span data-ttu-id="fc41b-126">Обновите серверы, связанные с этим доменом обновления.</span><span class="sxs-lookup"><span data-stu-id="fc41b-126">Upgrade the servers associated with this the Upgrade Domain.</span></span>
    
    3.  <span data-ttu-id="fc41b-127">Перезапустите серверы и убедитесь, что они принимают новые подключения.</span><span class="sxs-lookup"><span data-stu-id="fc41b-127">Restart the servers, and make sure they are accepting new connections.</span></span>

3.  <span data-ttu-id="fc41b-128">Повторите действия 1 и 2 для каждого домена обновления в пуле, пока не будут обновлены все серверы переднего плана.</span><span class="sxs-lookup"><span data-stu-id="fc41b-128">Repeat Steps 1 and 2 for each other Upgrade Domain in the pool, until all Front End Servers have been upgraded.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

