---
title: Управление аварийным восстановлением, высокой доступностью и службой резервного копирования Lync Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing Lync Server disaster recovery, high availability, and Backup Service
ms:assetid: f4cd36fb-ffd6-48fa-b761-e11b3bcff91a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721939(v=OCS.15)
ms:contentKeyID: 49733876
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 89c18076a2bbc34386872a7fbee92c26b8084598
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42185612"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="managing-lync-server-2013-disaster-recovery-high-availability-and-backup-service"></a><span data-ttu-id="ebd35-102">Управление аварийным восстановлением, высокой доступностью и службой резервного копирования Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ebd35-102">Managing Lync Server 2013 disaster recovery, high availability, and Backup Service</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ebd35-103">_**Последнее изменение темы:** 2012-11-12_</span><span class="sxs-lookup"><span data-stu-id="ebd35-103">_**Topic Last Modified:** 2012-11-12_</span></span>

<span data-ttu-id="ebd35-104">В данном разделе описываются процедуры по аварийному восстановлению, а также по обслуживанию службы резервного копирования, которая синхронизирует данные в связанных интерфейсных пулах.</span><span class="sxs-lookup"><span data-stu-id="ebd35-104">This section contains procedures for disaster recovery operations, as well as for maintaining the Backup Service which synchronizes the data in paired Front End pools.</span></span>

<span data-ttu-id="ebd35-p101">Процедуры аварийного восстановления — как отработка отказа, так и восстановление размещения — выполняются вручную. В случае аварии администратор должен вручную вызвать процесс отработки отказа. Это относится и к процессу восстановления размещения после восстановления пула.</span><span class="sxs-lookup"><span data-stu-id="ebd35-p101">Disaster recovery procedures, both failover and failback, are manual. If there is a disaster, the administrator must manually invoke the failover procedures. The same applies to failback after the pool is repaired.</span></span>

<span data-ttu-id="ebd35-108">В процедурах аварийного восстановления, которые приводятся в этом разделе, предполагается следующее.</span><span class="sxs-lookup"><span data-stu-id="ebd35-108">The disaster recovery procedures in the rest of this section assume the following:</span></span>

  - <span data-ttu-id="ebd35-109">У вас есть развернутые связанные пулы переднего плана, расположенные на разных сайтах, как описано в статье [Планирование обеспечения высокой доступности и аварийного восстановления в Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span><span class="sxs-lookup"><span data-stu-id="ebd35-109">You have a deployment with paired Front End pools, located in different sites, as described in [Planning for high availability and disaster recovery in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span></span> <span data-ttu-id="ebd35-110">Служба резервного копирования работает в этих сопряженных пулах для поддержания их синхронизации.</span><span class="sxs-lookup"><span data-stu-id="ebd35-110">The Backup Service has been running on these paired pools to keep them synchronized.</span></span>

  - <span data-ttu-id="ebd35-111">Если центральное хранилище управления размещается в любом пуле, оно устанавливается и запускается в обоих связанных пулах, где один из этих пулов размещает активный хозяин и другой пул, в котором размещается ждущий режим.</span><span class="sxs-lookup"><span data-stu-id="ebd35-111">If the Central Management store is hosted on either pool, it is installed and running on both of the paired pools, with one of those pools hosting the active master and the other pool hosting the standby.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="ebd35-p103">В последующих процедурах параметр <EM>PoolFQDN</EM> указывает на полное доменное имя пула, затронутого аварией, а не того пула, с которого перенаправляются затронутые пользователи. Для одного набора затронутых пользователей он указывает на один и тот же пул в командлетах отработки отказа и восстановления размещения (то есть на пул, который первым принял пользователей перед отработкой отказа).</span><span class="sxs-lookup"><span data-stu-id="ebd35-p103">In the following procedures, the <EM>PoolFQDN</EM> parameter refers to the FQDN of the pool that is affected by disaster, not the pool that affected users are being redirected from. For the same set of affected users, it refers to the same pool in both failover and failback cmdlets (that is, the pool that first homed the users before the failover).</span></span><BR><span data-ttu-id="ebd35-p104">Например, представьте себе ситуацию, когда для всех пользователей, размещенных в пуле P1, была выполнена отработка отказа в резервный пул P2. Если администратор хочет переместить всех пользователей, в данный момент обслуживаемых пулом P2, в пул P1, ему следует выполнить следующие действия:</span><span class="sxs-lookup"><span data-stu-id="ebd35-p104">For example, assume a case in which all users homed on a pool P1 were failed over to the backup pool, P2. If the administrator wants to move all the users currently serviced by P2 to be serviced by P1, the administrator must perform the following steps:</span></span> 
> <OL>
> <LI>
> <P><span data-ttu-id="ebd35-p105">Выполнить восстановление размещения для всех пользователей, изначально размещенных в пуле P1, из пула P2 в пул P1 с помощью соответствующего командлета. В этом случае параметр <EM>PoolFQDN</EM> обозначает полное доменное имя пула P1.</span><span class="sxs-lookup"><span data-stu-id="ebd35-p105">Fail back all the users originally homed on P1 from P2 to P1 using the failback cmdlet. In this case, the <EM>PoolFQDN</EM> is P1’s FQDN.</span></span></P>
> <LI>
> <P><span data-ttu-id="ebd35-p106">Выполнить отработку отказа для всех пользователей, изначально размещенных в пуле P2, в пул P1 с помощью соответствующего командлета. В этом случае параметр <EM>PoolFQDN</EM> обозначает полное доменное имя пула P2.</span><span class="sxs-lookup"><span data-stu-id="ebd35-p106">Fail over all the users originally homed on P2 to P1 using the failover cmdlet. In this case, the <EM>PoolFQDN</EM> is P2’s FQDN.</span></span></P>
> <LI>
> <P><span data-ttu-id="ebd35-120">Если позднее администратор хочет выполнить восстановление размещения для этих пользователей P2 обратно в пул P2, параметр <EM>PoolFQDN</EM> обозначает полное доменное имя пула P2.</span><span class="sxs-lookup"><span data-stu-id="ebd35-120">If the administrator later wants to fail back those P2 users back to P2, the <EM>PoolFQDN</EM> is P2’s FQDN.</span></span></P></LI></OL><span data-ttu-id="ebd35-121">Обратите внимание на то, что описанное выше действие 1 следует выполнять перед действием 2 для сохранения целостности пула.</span><span class="sxs-lookup"><span data-stu-id="ebd35-121">Note that step 1 above must be performed before step 2 to preserve pool integrity.</span></span> <span data-ttu-id="ebd35-122">Если попытаться выполнить действие 2 перед действием 2, произойдет сбой командлета.</span><span class="sxs-lookup"><span data-stu-id="ebd35-122">If you try step 2 before step 1, the step 2 cmdlet will fail.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="ebd35-123">Содержание</span><span class="sxs-lookup"><span data-stu-id="ebd35-123">In This Section</span></span>

  - [<span data-ttu-id="ebd35-124">Настройка и мониторинг службы резервного копирования в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ebd35-124">Configuring and monitoring the Backup Service in Lync Server 2013</span></span>](lync-server-2013-configuring-and-monitoring-the-backup-service.md)

  - [<span data-ttu-id="ebd35-125">Отработка отказа для пула в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ebd35-125">Failing over a pool in Lync Server 2013</span></span>](lync-server-2013-failing-over-a-pool.md)

  - [<span data-ttu-id="ebd35-126">Отработка отказа пула в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ebd35-126">Failing back a pool in Lync Server 2013</span></span>](lync-server-2013-failing-back-a-pool.md)

  - [<span data-ttu-id="ebd35-127">Отработка отказа для зеркальной базы данных в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ebd35-127">Failing over a mirrored database in Lync Server 2013</span></span>](lync-server-2013-failing-over-a-mirrored-database.md)

  - [<span data-ttu-id="ebd35-128">Отработка отказа для пограничного пула, используемого для Федерации Lync Server в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ebd35-128">Failing over the Edge pool used for Lync Server federation in Lync Server 2013</span></span>](lync-server-2013-failing-over-the-edge-pool-used-for-lync-server-federation.md)

  - [<span data-ttu-id="ebd35-129">Отработка отказа для пограничного пула, используемого для Федерации XMPP в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ebd35-129">Failing over the Edge pool used for XMPP federation in Lync Server 2013</span></span>](lync-server-2013-failing-over-the-edge-pool-used-for-xmpp-federation.md)

  - [<span data-ttu-id="ebd35-130">Отработка отказа пограничного пула, используемого для Федерации Lync Server или Федерации XMPP в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ebd35-130">Failing back the Edge pool used for Lync Server federation or XMPP federation in Lync Server 2013</span></span>](lync-server-2013-failing-back-the-edge-pool-used-for-lync-server-federation-or-xmpp-federation.md)

  - [<span data-ttu-id="ebd35-131">Изменение пограничного пула, связанного с пулом переднего плана в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ebd35-131">Changing the Edge pool associated with a Front End pool in Lync Server 2013</span></span>](lync-server-2013-changing-the-edge-pool-associated-with-a-front-end-pool.md)

  - [<span data-ttu-id="ebd35-132">Восстановление содержимого конференций с помощью службы резервного копирования в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ebd35-132">Restoring conference contents using the Backup Service in Lync Server 2013</span></span>](lync-server-2013-restoring-conference-contents-using-the-backup-service.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="ebd35-133">См. также</span><span class="sxs-lookup"><span data-stu-id="ebd35-133">See Also</span></span>


[<span data-ttu-id="ebd35-134">Планирование обеспечения высокой доступности и аварийного восстановления в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ebd35-134">Planning for high availability and disaster recovery in Lync Server 2013</span></span>](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

