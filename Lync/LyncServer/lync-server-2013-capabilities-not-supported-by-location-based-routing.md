---
title: 'Lync Server 2013: возможности, не поддерживаемые службой маршрутизации Location-Based'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Capabilities not supported by Location-Based Routing
ms:assetid: c3d54953-a7d6-4465-a6c3-ae411b2d8ea9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994071(v=OCS.15)
ms:contentKeyID: 51803982
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 40a7d32c0448abfe3552fdfe657b9c6bec960a08
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48512866"
---
# <a name="capabilities-not-supported-by-location-based-routing-in-lync-server-2013"></a><span data-ttu-id="beb8f-102">Возможности, не поддерживаемые службой маршрутизации Location-Based в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="beb8f-102">Capabilities not supported by Location-Based Routing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="beb8f-103">_**Последнее изменение темы:** 2014-03-12_</span><span class="sxs-lookup"><span data-stu-id="beb8f-103">_**Topic Last Modified:** 2014-03-12_</span></span>

<span data-ttu-id="beb8f-104">Маршрутизация Location-Based не относится к следующим типам взаимодействий.</span><span class="sxs-lookup"><span data-stu-id="beb8f-104">Location-Based Routing does not apply to the following types of interactions.</span></span> <span data-ttu-id="beb8f-105">Маршрутизация Location-Based не применяется, когда конечные точки Lync взаимодействуют с конечными точками PSTN, используя эти возможности.</span><span class="sxs-lookup"><span data-stu-id="beb8f-105">Location-Based Routing is not enforced when Lync endpoints interact with PSTN endpoints using these capabilities.</span></span>

  - <span data-ttu-id="beb8f-106">Подключаться к конференциям с поддержкой PSTN</span><span class="sxs-lookup"><span data-stu-id="beb8f-106">PSTN dial-in to conferences</span></span>

  - <span data-ttu-id="beb8f-107">Входящие и исходящие вызовы PSTN через группу ответа</span><span class="sxs-lookup"><span data-stu-id="beb8f-107">Incoming and outgoing PSTN calls through Response Group</span></span>

  - <span data-ttu-id="beb8f-108">Парковки вызовов или извлечение вызовов PSTN через приостановку вызовов</span><span class="sxs-lookup"><span data-stu-id="beb8f-108">Call park or retrieval of PSTN calls through Call Park</span></span>

  - <span data-ttu-id="beb8f-109">Входящие звонки PSTN в службу объявлений</span><span class="sxs-lookup"><span data-stu-id="beb8f-109">Incoming PSTN calls to Announcement Service</span></span>

  - <span data-ttu-id="beb8f-110">Входящие звонки PSTN, полученные с помощью групповой отправки звонков</span><span class="sxs-lookup"><span data-stu-id="beb8f-110">Incoming PSTN calls retrieved via Group Call Pickup</span></span>

<span data-ttu-id="beb8f-111">Для применения правил маршрутизации Location-Based к типам взаимодействия, приведенным в следующем списке, необходимо включить маршрутизацию Location-Based для конференц-связи:</span><span class="sxs-lookup"><span data-stu-id="beb8f-111">To enforce Location-Based Routing rules to the types of interactions in the following list, you must enable Location-Based Routing for Conferencing:</span></span>

  - <span data-ttu-id="beb8f-112">Исходящие звонки PSTN из конференций</span><span class="sxs-lookup"><span data-stu-id="beb8f-112">PSTN dial-out from conferences</span></span>

  - <span data-ttu-id="beb8f-113">Укрупнение из одноранговых голосовых бесед в конференц-связи с использованием конечных точек PSTN</span><span class="sxs-lookup"><span data-stu-id="beb8f-113">Escalations from peer-to-peer audio conversations to conferencing involving PSTN endpoints</span></span>

  - <span data-ttu-id="beb8f-114">Консультативного передачи с использованием конечных точек PSTN</span><span class="sxs-lookup"><span data-stu-id="beb8f-114">Consultative transfers involving PSTN endpoints</span></span>

<span data-ttu-id="beb8f-115">Чтобы включить Location-Basedную маршрутизацию для конференц-связи, ознакомьтесь со статьей [Маршрутизация на основе расположения для конференций в Lync Server 2013](lync-server-2013-location-based-routing-for-conferencing.md).</span><span class="sxs-lookup"><span data-stu-id="beb8f-115">To enable Location-Based Routing for Conferencing, see [Location-Based Routing for conferencing in Lync Server 2013](lync-server-2013-location-based-routing-for-conferencing.md).</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="beb8f-116">См. также</span><span class="sxs-lookup"><span data-stu-id="beb8f-116">See Also</span></span>


[<span data-ttu-id="beb8f-117">Планирование маршрутизации Location-Based в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="beb8f-117">Planning for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-planning-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

