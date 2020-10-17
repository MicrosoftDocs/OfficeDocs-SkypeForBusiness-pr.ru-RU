---
title: 'Lync Server 2013: новые функции аварийного восстановления и обеспечения высокого уровня доступности'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: New disaster recovery and high availability features
ms:assetid: 4fa7cd0f-784b-4d3f-b839-432c2ecaf7c1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204892(v=OCS.15)
ms:contentKeyID: 48184130
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 33a9039c65d059042d9eb93c9d5437a00ebff266
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48512566"
---
# <a name="new-disaster-recovery-and-high-availability-features-in-lync-server-2013"></a><span data-ttu-id="4f33e-102">Новые функции аварийного восстановления и обеспечения высокой доступности в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4f33e-102">New disaster recovery and high availability features in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4f33e-103">_**Последнее изменение темы:** 2012-09-20_</span><span class="sxs-lookup"><span data-stu-id="4f33e-103">_**Topic Last Modified:** 2012-09-20_</span></span>

<span data-ttu-id="4f33e-104">Как и в Lync Server 2010, основная схема высокой доступности для Lync Server 2013 основана на избыточности сервера посредством пула.</span><span class="sxs-lookup"><span data-stu-id="4f33e-104">As in Lync Server 2010, the main high availability (HA) scheme for Lync Server 2013 is based on server redundancy via pooling.</span></span> <span data-ttu-id="4f33e-105">При сбое сервера с определенными ролями остальные серверы в пуле с такими же ролями берут на себя нагрузку этого сервера.</span><span class="sxs-lookup"><span data-stu-id="4f33e-105">If a server running a certain server role fails, the other servers in the pool running the same role take the load of that server.</span></span> <span data-ttu-id="4f33e-106">Это касается серверов переднего плана, пограничных серверов, серверов-посредников и Директоров.</span><span class="sxs-lookup"><span data-stu-id="4f33e-106">This applies to Front End Servers, Edge Servers, Mediation Servers, and Directors.</span></span>

<span data-ttu-id="4f33e-107">Lync Server 2013 добавляет новые меры аварийного восстановления, позволяя связывать пулы переднего плана, расположенные в двух центрах обработки данных.</span><span class="sxs-lookup"><span data-stu-id="4f33e-107">Lync Server 2013 adds new disaster recovery measures by enabling you to pair Front End pools located in two datacenters.</span></span> <span data-ttu-id="4f33e-108">В случае выхода из строя одного из сопряженных пулов администратор может выполнить отработку отказа для пользователей из этого пула в другой пул из данной пары, обеспечивая таким образом непрерывность обслуживания.</span><span class="sxs-lookup"><span data-stu-id="4f33e-108">If one of the paired pools goes down, an administrator can fail over the users from that pool to the other pool in the pair, to provide continuation of service.</span></span> <span data-ttu-id="4f33e-109">Эта функциональная возможность не требует дорогостоящих сетевых или аппаратных решений, таких как сети хранения или общие диски.</span><span class="sxs-lookup"><span data-stu-id="4f33e-109">This functionality does not require expensive network or hardware solutions such as storage networks or shared disks.</span></span>

<span data-ttu-id="4f33e-110">Lync Server 2013 также добавляет высокую доступность внутреннего сервера.</span><span class="sxs-lookup"><span data-stu-id="4f33e-110">Lync Server 2013 also adds Back End Server high availability.</span></span> <span data-ttu-id="4f33e-111">Это необязательная топология, в которой развертываются два задних сервера переднего плана, а также синхронное зеркальное отображение SQL для всех баз данных Lync, запущенных на внутренних серверах.</span><span class="sxs-lookup"><span data-stu-id="4f33e-111">This is an optional topology in which you deploy two Back End Servers for a Front End pool, and set up synchronous SQL mirroring for all the Lync databases running on the Back End Servers.</span></span> <span data-ttu-id="4f33e-112">Вы можете выбрать, следует ли развернуть следящий сервер для зеркала.</span><span class="sxs-lookup"><span data-stu-id="4f33e-112">You may choose whether to deploy a witness for the mirror.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="4f33e-113">См. также</span><span class="sxs-lookup"><span data-stu-id="4f33e-113">See Also</span></span>


[<span data-ttu-id="4f33e-114">Планирование обеспечения высокой доступности и аварийного восстановления в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4f33e-114">Planning for high availability and disaster recovery in Lync Server 2013</span></span>](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

