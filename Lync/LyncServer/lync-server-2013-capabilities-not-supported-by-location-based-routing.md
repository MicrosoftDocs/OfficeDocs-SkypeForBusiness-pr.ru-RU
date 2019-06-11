---
title: 'Lync Server 2013: функции, не поддерживаемые маршрутизацией на основе расположения'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Capabilities not supported by Location-Based Routing
ms:assetid: c3d54953-a7d6-4465-a6c3-ae411b2d8ea9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994071(v=OCS.15)
ms:contentKeyID: 51803982
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7ca2d775fc17d0919ceb31a38b242e54d37b6a55
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34841682"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="capabilities-not-supported-by-location-based-routing-in-lync-server-2013"></a><span data-ttu-id="0882f-102">Функции, не поддерживаемые маршрутизацией на основе расположения в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0882f-102">Capabilities not supported by Location-Based Routing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0882f-103">_**Тема последнего изменения:** 2014-03-12_</span><span class="sxs-lookup"><span data-stu-id="0882f-103">_**Topic Last Modified:** 2014-03-12_</span></span>

<span data-ttu-id="0882f-104">Маршрутизация на основе местоположения не распространяется на следующие типы взаимодействий.</span><span class="sxs-lookup"><span data-stu-id="0882f-104">Location-Based Routing does not apply to the following types of interactions.</span></span> <span data-ttu-id="0882f-105">Маршрутизация на основе местоположения не применяется, если конечные точки Lync взаимодействуют с конечными точками PSTN с помощью этих возможностей.</span><span class="sxs-lookup"><span data-stu-id="0882f-105">Location-Based Routing is not enforced when Lync endpoints interact with PSTN endpoints using these capabilities.</span></span>

  - <span data-ttu-id="0882f-106">Конференции с телефонным подключением</span><span class="sxs-lookup"><span data-stu-id="0882f-106">PSTN dial-in to conferences</span></span>

  - <span data-ttu-id="0882f-107">Входящие и исходящие вызовы ТСОП через группу ответов</span><span class="sxs-lookup"><span data-stu-id="0882f-107">Incoming and outgoing PSTN calls through Response Group</span></span>

  - <span data-ttu-id="0882f-108">Парковка вызовов или преобразование вызовов ТСОП с помощью функции парковки вызовов</span><span class="sxs-lookup"><span data-stu-id="0882f-108">Call park or retrieval of PSTN calls through Call Park</span></span>

  - <span data-ttu-id="0882f-109">Входящие вызовы ТСОП в службу оповещений</span><span class="sxs-lookup"><span data-stu-id="0882f-109">Incoming PSTN calls to Announcement Service</span></span>

  - <span data-ttu-id="0882f-110">Входящие вызовы ТСОП, преобразованные через групповой ответ на вызовы</span><span class="sxs-lookup"><span data-stu-id="0882f-110">Incoming PSTN calls retrieved via Group Call Pickup</span></span>

<span data-ttu-id="0882f-111">Чтобы использовать правила маршрутизации, основанные на расположении, в следующем списке, необходимо включить функцию маршрутизации на основе местоположения для конференций.</span><span class="sxs-lookup"><span data-stu-id="0882f-111">To enforce Location-Based Routing rules to the types of interactions in the following list, you must enable Location-Based Routing for Conferencing:</span></span>

  - <span data-ttu-id="0882f-112">Исходящие вызовы по ТСОП из конференций</span><span class="sxs-lookup"><span data-stu-id="0882f-112">PSTN dial-out from conferences</span></span>

  - <span data-ttu-id="0882f-113">Эскалации из сеансов одноранговой голосовой связи к сеансам конференций с привлечением конечных точек ТСОП</span><span class="sxs-lookup"><span data-stu-id="0882f-113">Escalations from peer-to-peer audio conversations to conferencing involving PSTN endpoints</span></span>

  - <span data-ttu-id="0882f-114">Передачи после консультации с привлечением конечных точек ТСОП</span><span class="sxs-lookup"><span data-stu-id="0882f-114">Consultative transfers involving PSTN endpoints</span></span>

<span data-ttu-id="0882f-115">Чтобы включить возможность маршрутизации для конференций на основе местоположения, ознакомьтесь со сведениями [о маршрутизации на основе местоположения для конференций в Lync Server 2013](lync-server-2013-location-based-routing-for-conferencing.md).</span><span class="sxs-lookup"><span data-stu-id="0882f-115">To enable Location-Based Routing for Conferencing, see [Location-Based Routing for conferencing in Lync Server 2013](lync-server-2013-location-based-routing-for-conferencing.md).</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="0882f-116">См. также</span><span class="sxs-lookup"><span data-stu-id="0882f-116">See Also</span></span>


[<span data-ttu-id="0882f-117">Планирование маршрутизации на основе местоположения в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0882f-117">Planning for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-planning-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

