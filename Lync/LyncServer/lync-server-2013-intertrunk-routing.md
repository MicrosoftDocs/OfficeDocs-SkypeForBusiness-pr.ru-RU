---
title: 'Lync Server 2013: Маршрутизация с магистрали'
description: 'Lync Server 2013: Маршрутизация с магистрали.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Intertrunk routing
ms:assetid: d3a33b4a-8bf4-4a8c-a371-8ef79e740780
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205272(v=OCS.15)
ms:contentKeyID: 48185442
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 30c838ee94a2df0807195c172d7e2a3a393523af
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48553145"
---
# <a name="intertrunk-routing-in-lync-server-2013"></a><span data-ttu-id="c225d-103">Маршрутизация по межмагистральным каналам в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c225d-103">Intertrunk routing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c225d-104">_**Последнее изменение темы:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="c225d-104">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="c225d-105">Lync Server 2013 может подсоединить IP-УАТС к шлюзу телефонной сети общего пользования (PSTN), чтобы звонки с телефона УАТС могли маршрутизироваться в PSTN, а входящие звонки PSTN могут маршрутизироваться на телефон УАТС.</span><span class="sxs-lookup"><span data-stu-id="c225d-105">Lync Server 2013 can interconnect an IP-PBX to a public switched telephone network (PSTN) gateway so that calls from a PBX phone can be routed to the PSTN, and incoming PSTN calls can be routed to a private branch exchange (PBX) phone.</span></span> <span data-ttu-id="c225d-106">Аналогично, Lync Server 2013 может использовать две или более системы IP-УАТС, чтобы вызовы можно было размещать и принимать между телефонами УАТС из различных систем IP-УАТС.</span><span class="sxs-lookup"><span data-stu-id="c225d-106">Similarly, Lync Server 2013 can interconnect two or more IP-PBX systems so that calls can be placed and received between PBX phones from the different IP-PBX systems.</span></span>

<span data-ttu-id="c225d-107">Эту функцию маршрутизации по межмагистрали можно настроить с помощью командлета командной консоли Lync Server, **Set — CsTrunkConfiguration**с новым параметром PstnUsages.</span><span class="sxs-lookup"><span data-stu-id="c225d-107">This intertrunk routing feature can be configured by using the Lync Server Management Shell cmdlet, **Set-CsTrunkConfiguration**, with the new parameter, PstnUsages.</span></span> <span data-ttu-id="c225d-108">Он определяет набор записей варианта использовании ТСОП, который будет применяться.</span><span class="sxs-lookup"><span data-stu-id="c225d-108">This parameter specifies the set of PSTN usage records to use.</span></span> <span data-ttu-id="c225d-109">С помощью этой записи магистраль определяет маршрут и переадресует все вызовы соответствующим образом.</span><span class="sxs-lookup"><span data-stu-id="c225d-109">A trunk uses this PSTN usage to determine a route and to route all incoming calls accordingly.</span></span>

    Set-CsTrunkConfiguration -Identity <TrunkId> -PstnUsages @{add="<UsageString>"}

<span data-ttu-id="c225d-110">На следующей схеме показана платформа Lync Server 2013, обеспечивающая взаимодействие между шлюзом PSTN и IP-УАТС.</span><span class="sxs-lookup"><span data-stu-id="c225d-110">The following diagram illustrates Lync Server 2013 providing interconnectivity between a PSTN gateway and an IP-PBX.</span></span>

<span data-ttu-id="c225d-111">**Межмагистральная маршрутизации между шлюзом и IP-УАТС**</span><span class="sxs-lookup"><span data-stu-id="c225d-111">**Intertrunk routing between gateway and IP PBX**</span></span>

<span data-ttu-id="c225d-112">![Lync Server с подключением шлюза PSTN/IP-УАТС](images/JJ721940.cc3858ca-2ee3-4d51-8a51-db078366b50b(OCS.15).jpg "Lync Server с подключением шлюза PSTN/IP-УАТС")</span><span class="sxs-lookup"><span data-stu-id="c225d-112">![Lync Server connecting PSTN gateway/IP-PBX diagram](images/JJ721940.cc3858ca-2ee3-4d51-8a51-db078366b50b(OCS.15).jpg "Lync Server connecting PSTN gateway/IP-PBX diagram")</span></span>

<span data-ttu-id="c225d-113">На следующей схеме показана платформа Lync Server 2013, соединяющая две системы IP-УАТС.</span><span class="sxs-lookup"><span data-stu-id="c225d-113">The following diagram illustrates Lync Server 2013 interconnecting two IP-PBX systems.</span></span>

<span data-ttu-id="c225d-114">**Межмагистральная маршрутизации между двумя IP-УАТС**</span><span class="sxs-lookup"><span data-stu-id="c225d-114">**Intertrunk routing between two IP PBXs**</span></span>

<span data-ttu-id="c225d-115">![Схема IP-PAX для системы связи Lync Server-PAX](images/JJ721940.6ba18ec9-df70-498a-9cf7-7fc41e5ec432(OCS.15).jpg "Схема IP-PAX для системы связи Lync Server-PAX")</span><span class="sxs-lookup"><span data-stu-id="c225d-115">![Lync Server interconnecting IP-PAX systems diagram](images/JJ721940.6ba18ec9-df70-498a-9cf7-7fc41e5ec432(OCS.15).jpg "Lync Server interconnecting IP-PAX systems diagram")</span></span>

</div>

<span> </span>

</div>

</div>

</div>

