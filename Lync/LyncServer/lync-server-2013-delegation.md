---
title: 'Lync Server 2013: делегирование'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Delegation
ms:assetid: 89e76e5c-3cfb-4504-8d0d-7509c8ba9815
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994045(v=OCS.15)
ms:contentKeyID: 51803956
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 82be0bdc382440cc8a4307dc0ba981f31c5a9313
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834660"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delegation-in-lync-server-2013"></a><span data-ttu-id="45ddf-102">Делегирование в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="45ddf-102">Delegation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="45ddf-103">_**Тема последнего изменения:** 2013-03-09_</span><span class="sxs-lookup"><span data-stu-id="45ddf-103">_**Topic Last Modified:** 2013-03-09_</span></span>

<span data-ttu-id="45ddf-104">Возможности делегирования в Lync зависят от маршрутизации на основе местоположения следующими способами:</span><span class="sxs-lookup"><span data-stu-id="45ddf-104">The delegation capabilities in Lync are affected by Location-Based Routing in the following manner:</span></span>

  - <span data-ttu-id="45ddf-105">Если представитель, включенный для маршрутизации на основе местоположения, помещает звонок от имени руководителя, то для проверки подлинности звонка, а также для направления звонка будет использоваться политика маршрутизации голосовой связи для представителя.</span><span class="sxs-lookup"><span data-stu-id="45ddf-105">When a delegate enabled for Location-Based Routing places a call on behalf of a manager, the delegate’s voice policy is used to authorize the call and the delegate’s site voice routing policy will be used to route the call</span></span>

  - <span data-ttu-id="45ddf-106">Что касается исходящих звонков ТСОП диспетчеру, действуют те же правила, регламентирующие переадресацию звонков и порядок обработки одновременных звонков, что и в соответствующих разделах.</span><span class="sxs-lookup"><span data-stu-id="45ddf-106">For incoming PSTN calls to a manager, the same rules applicable for call forwarding or simultaneously ringing will apply as described in the Call transfers and forwarding and Simultaneous ringing topics.</span></span>

  - <span data-ttu-id="45ddf-107">Когда делегат устанавливает конечную точку ТСОП в качестве точки назначения одновременных звонков для входящих звонков в адрес диспетчера, для маршрутизации звонка на конечную точку ТСОП делегата используется политика маршрутизации голосовых звонков сетевого сайта, связанного с входящей магистралью.</span><span class="sxs-lookup"><span data-stu-id="45ddf-107">When a delegate sets a PSTN endpoint as a simultaneous ring target, for an incoming call to the manager, the voice routing policy of the site that is associated to the incoming trunk will be used to route the call to the delegate’s PSTN endpoint.</span></span>

  - <span data-ttu-id="45ddf-108">Для целей делегирования, как правило, рекомендуется, чтобы диспетчер и связанные с ним делегаты находились на одном сетевом сайте.</span><span class="sxs-lookup"><span data-stu-id="45ddf-108">For delegation, it’s recommended that the manager and his associated delegates to be usually located in the same network site.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="45ddf-109">См. также</span><span class="sxs-lookup"><span data-stu-id="45ddf-109">See Also</span></span>


[<span data-ttu-id="45ddf-110">Сценарии маршрутизации на основе местоположения в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="45ddf-110">Scenarios for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

