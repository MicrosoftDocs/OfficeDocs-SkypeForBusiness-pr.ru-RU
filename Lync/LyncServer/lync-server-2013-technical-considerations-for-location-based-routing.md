---
title: 'Lync Server 2013: технические рекомендации для маршрутизации на основе расположения'
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
ms.openlocfilehash: 978590484cbb6bd3c23fac26422c186847662e49
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764049"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="technical-considerations-for-location-based-routing-in-lync-server-2013"></a><span data-ttu-id="a5f50-102">Технические рекомендации для маршрутизации на основе расположения в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a5f50-102">Technical considerations for Location-Based Routing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a5f50-103">_**Тема последнего изменения:** 2013-03-09_</span><span class="sxs-lookup"><span data-stu-id="a5f50-103">_**Topic Last Modified:** 2013-03-09_</span></span>

<span data-ttu-id="a5f50-104">При планировании маршрутизации на основе местоположения следует принимать во влияния указанные ниже сценарии.</span><span class="sxs-lookup"><span data-stu-id="a5f50-104">When planning Location-Based Routing, you should consider the impact to the following scenarios.</span></span>

<div>

## <a name="disaster-recovery"></a><span data-ttu-id="a5f50-105">Аварийное восстановление</span><span class="sxs-lookup"><span data-stu-id="a5f50-105">Disaster Recovery</span></span>

<span data-ttu-id="a5f50-106">При отработке отказа из основного пула в пул резервного копирования, а также при восстановлении нормальных операций для основного пула, маршрутизация на основе местоположения всегда будет принудительно применяться во время аварийной ситуации и процедуры восстановления.</span><span class="sxs-lookup"><span data-stu-id="a5f50-106">During a failover from the primary pool to a backup pool as well as when restoring normal operations to the primary pool, Location-Based Routing remains enforced at all times during a disaster and recovery procedure.</span></span>

</div>

<div>

## <a name="survivable-branch-appliance"></a><span data-ttu-id="a5f50-107">для обеспечения связи в филиалах</span><span class="sxs-lookup"><span data-stu-id="a5f50-107">Survivable Branch Appliance</span></span>

<span data-ttu-id="a5f50-108">Настройка маршрутизации на основе местоположения влияет на планирование развертывания шлюзов, связанных с бесперебойными устройствами филиалов.</span><span class="sxs-lookup"><span data-stu-id="a5f50-108">Configuring Location-Based Routing impacts the planning of where you deploy the gateways associated to your Survivable Branch Appliances.</span></span> <span data-ttu-id="a5f50-109">Шлюз, связанный с вашим СБА, должен находиться на том же сетевом сайте, что и работающее устройство филиала. в противном случае, если настроена маршрутизация на основе местоположения, пользователи, работающие на устройстве с бесперебойной подразделением, не смогут выполнять исходящие вызовы.</span><span class="sxs-lookup"><span data-stu-id="a5f50-109">The gateway associated to your SBA must be located in the same network site as your Survivable Branch Appliance; otherwise, users homed on your Survivable Branch Appliance will not be permitted to place outbound calls if Location-Based Routing is configured.</span></span> <span data-ttu-id="a5f50-110">При подключении через глобальную сеть между бесперебойно используемым устройством филиала и центральным сайтом ограничения на маршрутизацию на основе местоположения остаются принудительными.</span><span class="sxs-lookup"><span data-stu-id="a5f50-110">When the WAN connection between your Survivable Branch Appliance and the central site is down, Location-Based Routing restrictions remains enforced.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="a5f50-111">См. также</span><span class="sxs-lookup"><span data-stu-id="a5f50-111">See Also</span></span>


[<span data-ttu-id="a5f50-112">Планирование маршрутизации на основе местоположения в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a5f50-112">Planning for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-planning-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

