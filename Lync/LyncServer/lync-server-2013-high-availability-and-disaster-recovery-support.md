---
title: 'Lync Server 2013: поддержка высокой доступности и аварийного восстановления'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: High availability and disaster recovery support
ms:assetid: 47e77e85-c7c3-4ade-8db7-a34c71aeafd7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204866(v=OCS.15)
ms:contentKeyID: 48184053
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5fa5ec2ad01372d593a4452c352c33dd8077e395
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834069"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="high-availability-and-disaster-recovery-support-in-lync-server-2013"></a><span data-ttu-id="9ea9f-102">Поддержка высокой доступности и аварийного восстановления в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9ea9f-102">High availability and disaster recovery support in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9ea9f-103">_**Тема последнего изменения:** 2012-09-25_</span><span class="sxs-lookup"><span data-stu-id="9ea9f-103">_**Topic Last Modified:** 2012-09-25_</span></span>

<span data-ttu-id="9ea9f-104">Lync Server 2013 обеспечивает высокий уровень доступности благодаря резервированию серверов с помощью группировки.</span><span class="sxs-lookup"><span data-stu-id="9ea9f-104">Lync Server 2013 provides high availability by server redundancy via pooling.</span></span> <span data-ttu-id="9ea9f-105">Если сервер, на котором работает определенная роль, завершает работу со сбоем, другие серверы в пуле, выполняющие ту же самую роль, берут на себя нагрузку первого сервера.</span><span class="sxs-lookup"><span data-stu-id="9ea9f-105">If a server running a certain server role fails, the other servers in the pool running the same role take the load of that server.</span></span> <span data-ttu-id="9ea9f-106">Это применимо к интерфейсным серверам, пограничным серверам, серверам-посредникам и директорам.</span><span class="sxs-lookup"><span data-stu-id="9ea9f-106">This applies to Front End Servers, Edge Servers, Mediation Servers, and Directors.</span></span> <span data-ttu-id="9ea9f-107">Подробнее о ролях сервера можно найти [в разделе роли сервера в Lync server 2013](lync-server-2013-server-roles.md).</span><span class="sxs-lookup"><span data-stu-id="9ea9f-107">For details about server roles, see [Server roles in Lync Server 2013](lync-server-2013-server-roles.md).</span></span>

<span data-ttu-id="9ea9f-108">Lync Server 2013 также предоставляет меры аварийного восстановления, включая Связывание пула.</span><span class="sxs-lookup"><span data-stu-id="9ea9f-108">Lync Server 2013 also provides disaster recovery measures by enabling pool pairing.</span></span> <span data-ttu-id="9ea9f-109">Если развернуть эту топологию, будут назначены пары интерфейсных пулов, при этом каждый пул из этой пары размещается в отдельном центре обработке данных и в отдельном регионе.</span><span class="sxs-lookup"><span data-stu-id="9ea9f-109">If you deploy this topology, you will designate pairs of Front End pools, with each pool in a pair located in a separate data center, and in a separate geographical area.</span></span> <span data-ttu-id="9ea9f-110">Если один пул или сайт завершает работу, можно перенаправить пользователей этого пула в другой пул пары, что приведет к минимальному перерыву в обслуживании.</span><span class="sxs-lookup"><span data-stu-id="9ea9f-110">If one pool or site goes down, you can redirect the users of that pool to use the other pool in the pair, with minimal interruption of service.</span></span>

<span data-ttu-id="9ea9f-111">Lync Server 2013 также поддерживает высокий уровень доступности серверной части.</span><span class="sxs-lookup"><span data-stu-id="9ea9f-111">Lync Server 2013 also supports Back End Server high availability.</span></span> <span data-ttu-id="9ea9f-112">Это необязательная топология, в которой вы развертываете два серверных внешних сервера для пула переднего плана и настроены синхронное зеркальное отображение SQL Server для всех баз данных Lync, запущенных на серверном сервере.</span><span class="sxs-lookup"><span data-stu-id="9ea9f-112">This is an optional topology in which you deploy two Back End Servers for a Front End pool, and set up synchronous SQL Server mirroring for all the Lync databases running on the Back End Servers.</span></span>

<span data-ttu-id="9ea9f-113">Подробные сведения о связывании и зеркальном отображении серверов можно найти [в разделе Планирование обеспечения высокой доступности и аварийного восстановления в Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span><span class="sxs-lookup"><span data-stu-id="9ea9f-113">For details about pool pairing and Back End Server mirroring, see [Planning for high availability and disaster recovery in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="9ea9f-114">См. также</span><span class="sxs-lookup"><span data-stu-id="9ea9f-114">See Also</span></span>


[<span data-ttu-id="9ea9f-115">Роли сервера в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9ea9f-115">Server roles in Lync Server 2013</span></span>](lync-server-2013-server-roles.md)  
[<span data-ttu-id="9ea9f-116">Планирование высокой доступности и аварийного восстановления в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9ea9f-116">Planning for high availability and disaster recovery in Lync Server 2013</span></span>](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

