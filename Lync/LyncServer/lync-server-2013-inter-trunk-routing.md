---
title: 'Lync Server 2013: межмагистральная маршрутизация'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Inter-trunk routing
ms:assetid: f687a548-1f2e-48ed-9745-a13dc1f3698f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721940(v=OCS.15)
ms:contentKeyID: 49733877
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 37a9feb818f48317f9a3dddd78a70700e3f6ccfc
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41725849"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="inter-trunk-routing-in-lync-server-2013"></a><span data-ttu-id="aa340-102">Маршрутизация с межмагистральными организациями в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="aa340-102">Inter-trunk routing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="aa340-103">_**Тема последнего изменения:** 2012-10-08_</span><span class="sxs-lookup"><span data-stu-id="aa340-103">_**Topic Last Modified:** 2012-10-08_</span></span>

<span data-ttu-id="aa340-104">Lync Server 2013 обеспечивает базовое управление сеансами благодаря поддержке межмагистральной маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="aa340-104">Lync Server 2013 provides basic session management through the support of intertrunk routing.</span></span> <span data-ttu-id="aa340-105">Благодаря этой новой возможности сервер Lync Server обеспечивает функции управления звонками для вызываемых систем телефонной связи.</span><span class="sxs-lookup"><span data-stu-id="aa340-105">This new capability enables Lync Server to provide call control functionalities to downstream telephony systems.</span></span> <span data-ttu-id="aa340-106">Маршрутизация между магистралями позволяет соединить IP-УАТС со шлюзом телефонной сети общего пользования (ТСОП) для маршрутизации вызовов с телефона учрежденческой АТС (УАТС) в ТСОП, а входящих вызовов из ТСОП — на телефон УАТС.</span><span class="sxs-lookup"><span data-stu-id="aa340-106">Intertrunk routing can interconnect an IP-PBX to a public switched telephone network (PSTN) gateway so that calls from a private branch exchange (PBX) phone can be routed to the PSTN, and incoming PSTN calls can be routed to a PBX phone.</span></span> <span data-ttu-id="aa340-107">Аналогичным образом Lync Server может присоединиться к нескольким системам IP-УАТС, чтобы звонить и принимать их между телефонами УАТС из различных систем IP-УАТС.</span><span class="sxs-lookup"><span data-stu-id="aa340-107">Similarly, Lync Server can interconnect two or more IP-PBX systems so that calls can be placed and received between PBX phones from the different IP-PBX systems.</span></span>

<span data-ttu-id="aa340-108">На рисунке ниже показана интеграция сервера Lync Server 2013, обеспечивающая взаимодействие между шлюзом PSTN и IP-УАТС.</span><span class="sxs-lookup"><span data-stu-id="aa340-108">The following figure illustrates Lync Server 2013 providing interconnectivity between a PSTN gateway and an IP-PBX.</span></span>

<span data-ttu-id="aa340-109">![Схема подключения Lync Server к ТСОП-шлюзу/IP-УАТС](images/JJ721940.cc3858ca-2ee3-4d51-8a51-db078366b50b(OCS.15).jpg "Схема подключения Lync Server к ТСОП-шлюзу/IP-УАТС")</span><span class="sxs-lookup"><span data-stu-id="aa340-109">![Lync Server connecting PSTN gateway/IP-PBX diagram](images/JJ721940.cc3858ca-2ee3-4d51-8a51-db078366b50b(OCS.15).jpg "Lync Server connecting PSTN gateway/IP-PBX diagram")</span></span>

<span data-ttu-id="aa340-110">На следующем рисунке показана платформа Lync Server 2013, соединяющая две системы IP-УАТС.</span><span class="sxs-lookup"><span data-stu-id="aa340-110">The next figure illustrates Lync Server 2013 connecting two IP-PBX systems.</span></span>

<span data-ttu-id="aa340-111">![Схема соединений между системами IP-УАТС с помощью Lync Server](images/JJ721940.6ba18ec9-df70-498a-9cf7-7fc41e5ec432(OCS.15).jpg "Схема соединений между системами IP-УАТС с помощью Lync Server")</span><span class="sxs-lookup"><span data-stu-id="aa340-111">![Lync Server interconnecting IP-PAX systems diagram](images/JJ721940.6ba18ec9-df70-498a-9cf7-7fc41e5ec432(OCS.15).jpg "Lync Server interconnecting IP-PAX systems diagram")</span></span>

</div>

<span> </span>

</div>

</div>

</div>

