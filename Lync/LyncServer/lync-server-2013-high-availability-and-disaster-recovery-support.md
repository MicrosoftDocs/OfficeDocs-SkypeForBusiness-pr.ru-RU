---
title: 'Lync Server 2013: Поддержка высокой доступности и аварийного восстановления'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: High availability and disaster recovery support
ms:assetid: 47e77e85-c7c3-4ade-8db7-a34c71aeafd7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204866(v=OCS.15)
ms:contentKeyID: 48184053
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ba5251b9f0790c39aa3ca03492e50517a177d340
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42135446"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="high-availability-and-disaster-recovery-support-in-lync-server-2013"></a><span data-ttu-id="74b44-102">Поддержка высокого уровня доступности и аварийного восстановления в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="74b44-102">High availability and disaster recovery support in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="74b44-103">_**Последнее изменение темы:** 2012-09-25_</span><span class="sxs-lookup"><span data-stu-id="74b44-103">_**Topic Last Modified:** 2012-09-25_</span></span>

<span data-ttu-id="74b44-104">Lync Server 2013 обеспечивает высокий уровень доступности при резервировании серверов с помощью пула.</span><span class="sxs-lookup"><span data-stu-id="74b44-104">Lync Server 2013 provides high availability by server redundancy via pooling.</span></span> <span data-ttu-id="74b44-105">При сбое сервера с определенными ролями остальные серверы в пуле с такими же ролями берут на себя нагрузку этого сервера.</span><span class="sxs-lookup"><span data-stu-id="74b44-105">If a server running a certain server role fails, the other servers in the pool running the same role take the load of that server.</span></span> <span data-ttu-id="74b44-106">Это касается серверов переднего плана, пограничных серверов, серверов-посредников и Директоров.</span><span class="sxs-lookup"><span data-stu-id="74b44-106">This applies to Front End Servers, Edge Servers, Mediation Servers, and Directors.</span></span> <span data-ttu-id="74b44-107">Дополнительные сведения о ролях серверов приведены [в статье Server Roles in Lync server 2013](lync-server-2013-server-roles.md).</span><span class="sxs-lookup"><span data-stu-id="74b44-107">For details about server roles, see [Server roles in Lync Server 2013](lync-server-2013-server-roles.md).</span></span>

<span data-ttu-id="74b44-108">Lync Server 2013 также предоставляет меры аварийного восстановления, позволяя использовать функции связывания пула.</span><span class="sxs-lookup"><span data-stu-id="74b44-108">Lync Server 2013 also provides disaster recovery measures by enabling pool pairing.</span></span> <span data-ttu-id="74b44-109">Если развернуть эту топологию, будут назначены пары интерфейсных пулов, при этом каждый пул из этой пары размещается в отдельном центре обработке данных и в отдельном регионе.</span><span class="sxs-lookup"><span data-stu-id="74b44-109">If you deploy this topology, you will designate pairs of Front End pools, with each pool in a pair located in a separate data center, and in a separate geographical area.</span></span> <span data-ttu-id="74b44-110">Если один пул или сайт завершает работу, можно перенаправить пользователей этого пула в другой пул пары, что приведет к минимальному перерыву в обслуживании.</span><span class="sxs-lookup"><span data-stu-id="74b44-110">If one pool or site goes down, you can redirect the users of that pool to use the other pool in the pair, with minimal interruption of service.</span></span>

<span data-ttu-id="74b44-111">Lync Server 2013 также поддерживает высокую доступность внутреннего сервера.</span><span class="sxs-lookup"><span data-stu-id="74b44-111">Lync Server 2013 also supports Back End Server high availability.</span></span> <span data-ttu-id="74b44-112">Это необязательная топология, в которой развертываются два задних сервера переднего плана, а также выполняется настройка синхронного зеркального отображения SQL Server для всех баз данных Lync, запущенных на внутренних серверах.</span><span class="sxs-lookup"><span data-stu-id="74b44-112">This is an optional topology in which you deploy two Back End Servers for a Front End pool, and set up synchronous SQL Server mirroring for all the Lync databases running on the Back End Servers.</span></span>

<span data-ttu-id="74b44-113">Сведения о подключении к пулам и зеркальном отображении внутреннего сервера приведены [в статье Планирование обеспечения высокой доступности и аварийного восстановления в Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span><span class="sxs-lookup"><span data-stu-id="74b44-113">For details about pool pairing and Back End Server mirroring, see [Planning for high availability and disaster recovery in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="74b44-114">См. также</span><span class="sxs-lookup"><span data-stu-id="74b44-114">See Also</span></span>


[<span data-ttu-id="74b44-115">Роли сервера в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="74b44-115">Server roles in Lync Server 2013</span></span>](lync-server-2013-server-roles.md)  
[<span data-ttu-id="74b44-116">Планирование обеспечения высокой доступности и аварийного восстановления в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="74b44-116">Planning for high availability and disaster recovery in Lync Server 2013</span></span>](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

