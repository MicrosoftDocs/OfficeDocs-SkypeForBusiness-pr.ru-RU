---
title: 'Lync Server 2013: обновление или обновление серверов переднего плана'
description: 'Lync Server 2013: обновление или обновление серверов переднего плана.'
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
ms.openlocfilehash: 5340ca5549aeff51b275798572573b2c9f017644
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48569925"
---
# <a name="upgrade-or-update-front-end-servers-in-lync-server-2013"></a><span data-ttu-id="b80a1-103">Обновление или обновление серверов переднего плана в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b80a1-103">Upgrade or update Front End Servers in Lync Server 2013</span></span>

<div data-xmlns="https://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="https://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b80a1-104">_**Последнее изменение темы:** 2013-06-28_</span><span class="sxs-lookup"><span data-stu-id="b80a1-104">_**Topic Last Modified:** 2013-06-28_</span></span>

<span data-ttu-id="b80a1-105">Серверы переднего плана в пуле Enterprise Edition объединены в *домены обновления*.</span><span class="sxs-lookup"><span data-stu-id="b80a1-105">The Front End Servers in an Enterprise Edition pool are organized into *upgrade domains*.</span></span> <span data-ttu-id="b80a1-106">Такие домены обновления представляют собой подмножество серверов переднего плана в пуле.</span><span class="sxs-lookup"><span data-stu-id="b80a1-106">These are subsets of Front End Servers in the pool.</span></span> <span data-ttu-id="b80a1-107">Домены обновления создаются автоматически с помощью построителя топологий.</span><span class="sxs-lookup"><span data-stu-id="b80a1-107">Upgrade Domains are created automatically by Topology Builder.</span></span>

<span data-ttu-id="b80a1-108">При обновлении серверов необходимо сделать это одним доменом обновления за раз.</span><span class="sxs-lookup"><span data-stu-id="b80a1-108">When you upgrade servers, you must do so one Upgrade Domain at a time.</span></span> <span data-ttu-id="b80a1-109">Переведите каждый сервер в один домен для обновления, обновите и перезапустите его перед переходом к другому домену обновления.</span><span class="sxs-lookup"><span data-stu-id="b80a1-109">Bring each Server in one Upgrade Domain down, upgrade it, and then restart it before you move on to another Upgrade Domain.</span></span> <span data-ttu-id="b80a1-110">Следите за тем, какие домены обновления и серверы были обновлены до сих пор.</span><span class="sxs-lookup"><span data-stu-id="b80a1-110">Be sure to keep track of which Upgrade Domains and Servers that you have upgraded so far.</span></span> <span data-ttu-id="b80a1-111">При обновлении каждого сервера используйте следующую блок-схему.</span><span class="sxs-lookup"><span data-stu-id="b80a1-111">Use the following flowchart diagram when upgrading each server.</span></span>

![Обновление серверов переднего плана](images/upgradeupdatefrontendserverslync2013.png)

<div>

## <a name="to-apply-an-upgrade-to-the-front-end-servers-in-a-pool"></a><span data-ttu-id="b80a1-113">Применение обновления к серверам переднего плана в пуле</span><span class="sxs-lookup"><span data-stu-id="b80a1-113">To apply an upgrade to the Front End servers in a pool</span></span>

1.  <span data-ttu-id="b80a1-114">Выполните следующий командлет на сервере переднего плана в пуле:</span><span class="sxs-lookup"><span data-stu-id="b80a1-114">On a Front End Server in the pool, run the following cmdlet:</span></span>
    
    <span data-ttu-id="b80a1-115">**Get — CsPoolUpgradeReadinessState**</span><span class="sxs-lookup"><span data-stu-id="b80a1-115">**Get-CsPoolUpgradeReadinessState**</span></span>
    
    <span data-ttu-id="b80a1-116">Если значение *Пулупградестате* **занято**, подождите 10 минут, а затем повторите **Get-CsPoolUpgradeReadinessState** .</span><span class="sxs-lookup"><span data-stu-id="b80a1-116">If the value of *PoolUpgradeState* is **Busy**, wait for 10 minutes, and then try **Get-CsPoolUpgradeReadinessState** again.</span></span> <span data-ttu-id="b80a1-117">Если **вы видите по** крайней мере три последовательных интервала, через каждые 10 минут между попытками, или если вы видите результат **инсуффиЦиентактивефронтендс** для **пулупградестате,** то у этого пула возникла ошибка.</span><span class="sxs-lookup"><span data-stu-id="b80a1-117">If you see **Busy** for at least three consecutive times, after waiting 10 minutes in between each attempt, or if you see any result of **InsufficientActiveFrontEnds** for **PoolUpgradeState,** then there is an issue with the pool.</span></span> <span data-ttu-id="b80a1-118">Если этот пул сопряжен с другим интерфейсным пулом в топологии аварийного восстановления, необходимо аварийно завершить работу пула и перейти в резервный пул, после чего обновить серверы в этом пуле.</span><span class="sxs-lookup"><span data-stu-id="b80a1-118">If this pool is paired with another Front End pool in a disaster recovery topology, you should fail the pool over to the backup pool, and then update the servers in this pool.</span></span> <span data-ttu-id="b80a1-119">Подробнее о том, [как отработка отказа для пула в Lync Server 2013](lync-server-2013-failing-over-a-pool.md).</span><span class="sxs-lookup"><span data-stu-id="b80a1-119">For details, see [Failing over a pool in Lync Server 2013](lync-server-2013-failing-over-a-pool.md).</span></span>
    
    <span data-ttu-id="b80a1-120">Когда для параметра *PoolUpgradeState* отобразится значение **Готово**, перейдите к шагу 2.</span><span class="sxs-lookup"><span data-stu-id="b80a1-120">If the value of *PoolUpgradeState* is **Ready**, go to step 2.</span></span>

2.  <span data-ttu-id="b80a1-121">Командлет **Get – CsPoolUpgradeReadinessState** также возвращает сведения о каждом домене обновления в пуле, а также о том, какие серверы переднего плана находятся в каждом домене обновления.</span><span class="sxs-lookup"><span data-stu-id="b80a1-121">The **Get-CsPoolUpgradeReadinessState** cmdlet also returns information about each upgrade domain in the pool, and about which Front End Servers are in each upgrade domain.</span></span> <span data-ttu-id="b80a1-122">Если значение **реадифорупграде** равно **true** для домена обновления, содержащего сервер или серверы, которые требуется обновить, вы можете безопасно обновить эти серверы.</span><span class="sxs-lookup"><span data-stu-id="b80a1-122">If the **ReadyforUpgrade** value is **True** for the upgrade domain that contains the server or servers you want to upgrade, you can safely upgrade those servers now.</span></span> <span data-ttu-id="b80a1-123">Для этого выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="b80a1-123">To do so, do the following:</span></span>
    
    1.  <span data-ttu-id="b80a1-124">Остановите новые подключения к серверам переднего плана, которые планируется обновить, с помощью `Stop-CsWindowsService -Graceful -Verbose` командлета.</span><span class="sxs-lookup"><span data-stu-id="b80a1-124">Stop new connections to the Front End Servers you are going to upgrade by using the `Stop-CsWindowsService -Graceful -Verbose` cmdlet.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="b80a1-125">При выполнении этих обновлений сервера во время запланированного простоя сервера можно выполнить этот командлет без параметра "–<STRONG>graceful</STRONG>", как показано ниже: <STRONG>Stop — CsWindowsService</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="b80a1-125">If you are performing these server upgrades during a scheduled server downtime, you can run this cmdlet without the ‘-<STRONG>Graceful</STRONG>‘ parameter, as follows: <STRONG>Stop-CsWindowsService</STRONG>.</span></span> <span data-ttu-id="b80a1-126">Это приведет к немедленному завершению работы служб без ожидания заполнения всех существующих запросов на обслуживание.</span><span class="sxs-lookup"><span data-stu-id="b80a1-126">This will immediately shut down services, without waiting for all existing service requests to be filled.</span></span>

        
        </div>
    
    2.  <span data-ttu-id="b80a1-127">Обновите серверы, связанные с этим доменом обновления.</span><span class="sxs-lookup"><span data-stu-id="b80a1-127">Upgrade the servers associated with this the Upgrade Domain.</span></span>
    
    3.  <span data-ttu-id="b80a1-128">Перезапустите серверы и убедитесь, что они принимают новые подключения.</span><span class="sxs-lookup"><span data-stu-id="b80a1-128">Restart the servers, and make sure they are accepting new connections.</span></span>

3.  <span data-ttu-id="b80a1-129">Повторите шаги 1 и 2 для всех остальных доменов обновления в пуле до тех пор, пока не будут обновлены все серверы переднего плана.</span><span class="sxs-lookup"><span data-stu-id="b80a1-129">Repeat Steps 1 and 2 for each other Upgrade Domain in the pool, until all Front End Servers have been upgraded.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

