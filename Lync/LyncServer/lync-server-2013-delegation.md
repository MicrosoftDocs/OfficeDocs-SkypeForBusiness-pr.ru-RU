---
title: 'Lync Server 2013: делегирование'
description: 'Lync Server 2013: делегирование.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delegation
ms:assetid: 89e76e5c-3cfb-4504-8d0d-7509c8ba9815
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994045(v=OCS.15)
ms:contentKeyID: 51803956
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6dc25d0ea3dfd64ee1b71677e6bac55c1cb1ca32
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48567455"
---
# <a name="delegation-in-lync-server-2013"></a><span data-ttu-id="85b51-103">Делегирование в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="85b51-103">Delegation in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="85b51-104">_**Последнее изменение темы:** 2013-03-09_</span><span class="sxs-lookup"><span data-stu-id="85b51-104">_**Topic Last Modified:** 2013-03-09_</span></span>

<span data-ttu-id="85b51-105">На возможности делегирования в Lync влияют Location-Based маршрутизацию следующим образом:</span><span class="sxs-lookup"><span data-stu-id="85b51-105">The delegation capabilities in Lync are affected by Location-Based Routing in the following manner:</span></span>

  - <span data-ttu-id="85b51-106">Когда представитель, включенный для маршрутизации Location-Based, помещает вызов от имени руководителя, политика голосовой связи представителя используется для авторизации звонка, а политика маршрутизации голосовой связи на сайте представителя будет использоваться для маршрутизации вызова.</span><span class="sxs-lookup"><span data-stu-id="85b51-106">When a delegate enabled for Location-Based Routing places a call on behalf of a manager, the delegate’s voice policy is used to authorize the call and the delegate’s site voice routing policy will be used to route the call</span></span>

  - <span data-ttu-id="85b51-107">Для входящих звонков по PSTN в директоре применяются те же правила, что и для переадресации звонков или одновременного звонка, как описано в разделах "передача и переадресация вызовов и одновременный Звонок".</span><span class="sxs-lookup"><span data-stu-id="85b51-107">For incoming PSTN calls to a manager, the same rules applicable for call forwarding or simultaneously ringing will apply as described in the Call transfers and forwarding and Simultaneous ringing topics.</span></span>

  - <span data-ttu-id="85b51-108">Когда делегат задает конечную точку PSTN в качестве одновременного абонента, для входящего вызова руководителя будет использоваться политика маршрутизации голосовой связи для сайта, связанного с входящей магистралью, для маршрутизации вызова в конечную точку PSTN представителя.</span><span class="sxs-lookup"><span data-stu-id="85b51-108">When a delegate sets a PSTN endpoint as a simultaneous ring target, for an incoming call to the manager, the voice routing policy of the site that is associated to the incoming trunk will be used to route the call to the delegate’s PSTN endpoint.</span></span>

  - <span data-ttu-id="85b51-109">Для делегирования рекомендуется, чтобы руководитель и связанные с ним делегаты были размещены на одном сетевом сайте.</span><span class="sxs-lookup"><span data-stu-id="85b51-109">For delegation, it’s recommended that the manager and his associated delegates to be usually located in the same network site.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="85b51-110">См. также</span><span class="sxs-lookup"><span data-stu-id="85b51-110">See Also</span></span>


[<span data-ttu-id="85b51-111">Сценарии для маршрутизации Location-Based в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="85b51-111">Scenarios for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

