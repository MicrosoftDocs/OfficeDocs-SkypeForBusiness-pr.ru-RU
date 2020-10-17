---
title: 'Lync Server 2013: Маршрутизация между магистрали'
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
ms.openlocfilehash: de302ec9bfbf81ea1d5c43ec568f2a0c0f6c19bf
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48498496"
---
# <a name="inter-trunk-routing-in-lync-server-2013"></a><span data-ttu-id="31336-102">Маршрутизация между магистрали в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="31336-102">Inter-trunk routing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="31336-103">_**Последнее изменение темы:** 2012-10-08_</span><span class="sxs-lookup"><span data-stu-id="31336-103">_**Topic Last Modified:** 2012-10-08_</span></span>

<span data-ttu-id="31336-104">Lync Server 2013 обеспечивает базовое управление сеансами посредством поддержки маршрутизации по каналам связи.</span><span class="sxs-lookup"><span data-stu-id="31336-104">Lync Server 2013 provides basic session management through the support of intertrunk routing.</span></span> <span data-ttu-id="31336-105">Эта новая возможность позволяет Lync Server обеспечивать функции управления звонками для вызываемых телефонных систем.</span><span class="sxs-lookup"><span data-stu-id="31336-105">This new capability enables Lync Server to provide call control functionalities to downstream telephony systems.</span></span> <span data-ttu-id="31336-106">Маршрутизация между магистралями позволяет связать IP-УАТС со шлюзом телефонной сети общего пользования (ТСОП), чтобы звонки с телефона УАТС можно было перенаправлять в ТСОП, а входящие звонки ТСОП — на телефон УАТС.</span><span class="sxs-lookup"><span data-stu-id="31336-106">Intertrunk routing can interconnect an IP-PBX to a public switched telephone network (PSTN) gateway so that calls from a private branch exchange (PBX) phone can be routed to the PSTN, and incoming PSTN calls can be routed to a PBX phone.</span></span> <span data-ttu-id="31336-107">Аналогично, Lync Server может соединить две или более системы IP-УАТС, чтобы звонки можно было размещать и принимать между телефонами УАТС из различных систем IP-УАТС.</span><span class="sxs-lookup"><span data-stu-id="31336-107">Similarly, Lync Server can interconnect two or more IP-PBX systems so that calls can be placed and received between PBX phones from the different IP-PBX systems.</span></span>

<span data-ttu-id="31336-108">На следующем рисунке показана платформа Lync Server 2013, обеспечивающая взаимодействие между шлюзом PSTN и IP-УАТС.</span><span class="sxs-lookup"><span data-stu-id="31336-108">The following figure illustrates Lync Server 2013 providing interconnectivity between a PSTN gateway and an IP-PBX.</span></span>

<span data-ttu-id="31336-109">![Lync Server с подключением шлюза PSTN/IP-УАТС](images/JJ721940.cc3858ca-2ee3-4d51-8a51-db078366b50b(OCS.15).jpg "Lync Server с подключением шлюза PSTN/IP-УАТС")</span><span class="sxs-lookup"><span data-stu-id="31336-109">![Lync Server connecting PSTN gateway/IP-PBX diagram](images/JJ721940.cc3858ca-2ee3-4d51-8a51-db078366b50b(OCS.15).jpg "Lync Server connecting PSTN gateway/IP-PBX diagram")</span></span>

<span data-ttu-id="31336-110">На следующем рисунке показана платформа Lync Server 2013, соединяющая две системы IP-УАТС.</span><span class="sxs-lookup"><span data-stu-id="31336-110">The next figure illustrates Lync Server 2013 connecting two IP-PBX systems.</span></span>

<span data-ttu-id="31336-111">![Схема IP-PAX для системы связи Lync Server-PAX](images/JJ721940.6ba18ec9-df70-498a-9cf7-7fc41e5ec432(OCS.15).jpg "Схема IP-PAX для системы связи Lync Server-PAX")</span><span class="sxs-lookup"><span data-stu-id="31336-111">![Lync Server interconnecting IP-PAX systems diagram](images/JJ721940.6ba18ec9-df70-498a-9cf7-7fc41e5ec432(OCS.15).jpg "Lync Server interconnecting IP-PAX systems diagram")</span></span>

</div>

<span> </span>

</div>

</div>

</div>

