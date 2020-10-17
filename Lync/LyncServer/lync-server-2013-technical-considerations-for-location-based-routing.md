---
title: 'Lync Server 2013: технические рекомендации по маршрутизации Location-Based'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Technical considerations for Location-Based Routing
ms:assetid: 2e2a9199-7c6f-48d3-9adb-3873fc4f8c4e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994027(v=OCS.15)
ms:contentKeyID: 51803936
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 80364f35ffaf361353815988bcae12f29bca019c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48536186"
---
# <a name="technical-considerations-for-location-based-routing-in-lync-server-2013"></a><span data-ttu-id="08bec-102">Технические рекомендации по маршрутизации Location-Based в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="08bec-102">Technical considerations for Location-Based Routing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="08bec-103">_**Последнее изменение темы:** 2013-03-09_</span><span class="sxs-lookup"><span data-stu-id="08bec-103">_**Topic Last Modified:** 2013-03-09_</span></span>

<span data-ttu-id="08bec-104">При планировании Location-Basedной маршрутизации следует учитывать влияние следующих сценариев.</span><span class="sxs-lookup"><span data-stu-id="08bec-104">When planning Location-Based Routing, you should consider the impact to the following scenarios.</span></span>

<div>

## <a name="disaster-recovery"></a><span data-ttu-id="08bec-105">Аварийное восстановление</span><span class="sxs-lookup"><span data-stu-id="08bec-105">Disaster Recovery</span></span>

<span data-ttu-id="08bec-106">При отработке отказа из основного пула в резервный пул, а также при восстановлении нормальных операций в основном пуле, Location-Based маршрутизация всегда применяется во время аварийного восстановления и процедуры восстановления.</span><span class="sxs-lookup"><span data-stu-id="08bec-106">During a failover from the primary pool to a backup pool as well as when restoring normal operations to the primary pool, Location-Based Routing remains enforced at all times during a disaster and recovery procedure.</span></span>

</div>

<div>

## <a name="survivable-branch-appliance"></a><span data-ttu-id="08bec-107">Устройство для обеспечения связи в филиалах</span><span class="sxs-lookup"><span data-stu-id="08bec-107">Survivable Branch Appliance</span></span>

<span data-ttu-id="08bec-108">Настройка маршрутизации Location-Based влияет на планирование развертывания шлюзов, связанных с устройствами для обеспечения связи в филиалах.</span><span class="sxs-lookup"><span data-stu-id="08bec-108">Configuring Location-Based Routing impacts the planning of where you deploy the gateways associated to your Survivable Branch Appliances.</span></span> <span data-ttu-id="08bec-109">Шлюз, связанный с SBA, должен находиться на том же сетевом сайте, что и устройство для обеспечения связи в филиалах. в противном случае пользователи, размещенные на устройстве для обеспечения связи в филиалах, не смогут совершать исходящие вызовы, если настроена Location-Based маршрутизация.</span><span class="sxs-lookup"><span data-stu-id="08bec-109">The gateway associated to your SBA must be located in the same network site as your Survivable Branch Appliance; otherwise, users homed on your Survivable Branch Appliance will not be permitted to place outbound calls if Location-Based Routing is configured.</span></span> <span data-ttu-id="08bec-110">При соединении WAN между устройством для обеспечения связи в филиалах и центральным сайтом ограничения на Location-Based маршрутизации остаются неизменными.</span><span class="sxs-lookup"><span data-stu-id="08bec-110">When the WAN connection between your Survivable Branch Appliance and the central site is down, Location-Based Routing restrictions remains enforced.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="08bec-111">См. также</span><span class="sxs-lookup"><span data-stu-id="08bec-111">See Also</span></span>


[<span data-ttu-id="08bec-112">Планирование маршрутизации Location-Based в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="08bec-112">Planning for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-planning-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

