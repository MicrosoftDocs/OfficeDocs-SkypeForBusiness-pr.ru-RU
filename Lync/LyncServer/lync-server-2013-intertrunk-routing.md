---
title: 'Lync Server 2013: маршрутизация между каналами'
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
ms.openlocfilehash: eaa41fe229e9246506fd92eb9f48767994997e4e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41725679"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="intertrunk-routing-in-lync-server-2013"></a><span data-ttu-id="49ac9-102">Маршрутизация между каналами в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="49ac9-102">Intertrunk routing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="49ac9-103">_**Тема последнего изменения:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="49ac9-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="49ac9-104">Lync Server 2013 может использовать IP-УАТС с шлюзом коммутируемой телефонной сети (PSTN), чтобы звонки с телефонной АТС могли перенаправляться на телефон, входящий в протокол PSTN.</span><span class="sxs-lookup"><span data-stu-id="49ac9-104">Lync Server 2013 can interconnect an IP-PBX to a public switched telephone network (PSTN) gateway so that calls from a PBX phone can be routed to the PSTN, and incoming PSTN calls can be routed to a private branch exchange (PBX) phone.</span></span> <span data-ttu-id="49ac9-105">Аналогичным образом Lync Server 2013 может использоваться для объединения двух или более систем УАТС IP и обмена звонками между телефонами УАТС из различных систем IP-УАТС.</span><span class="sxs-lookup"><span data-stu-id="49ac9-105">Similarly, Lync Server 2013 can interconnect two or more IP-PBX systems so that calls can be placed and received between PBX phones from the different IP-PBX systems.</span></span>

<span data-ttu-id="49ac9-106">Эту функцию маршрутизации по межмагистрали можно настроить с помощью командлета командной консоли Lync Server, **Set-CsTrunkConfiguration**с новым параметром пстнусажес.</span><span class="sxs-lookup"><span data-stu-id="49ac9-106">This intertrunk routing feature can be configured by using the Lync Server Management Shell cmdlet, **Set-CsTrunkConfiguration**, with the new parameter, PstnUsages.</span></span> <span data-ttu-id="49ac9-107">Этот параметр указывает набор записей использования КТСОП для использования.</span><span class="sxs-lookup"><span data-stu-id="49ac9-107">This parameter specifies the set of PSTN usage records to use.</span></span> <span data-ttu-id="49ac9-108">Магистраль использует это использование PSTN для определения маршрута и для маршрутизации всех входящих вызовов соответственно.</span><span class="sxs-lookup"><span data-stu-id="49ac9-108">A trunk uses this PSTN usage to determine a route and to route all incoming calls accordingly.</span></span>

    Set-CsTrunkConfiguration -Identity <TrunkId> -PstnUsages @{add="<UsageString>"}

<span data-ttu-id="49ac9-109">На следующей схеме показана интеграция сервера Lync Server 2013, обеспечивающая взаимодействие между шлюзом PSTN и IP-УАТС.</span><span class="sxs-lookup"><span data-stu-id="49ac9-109">The following diagram illustrates Lync Server 2013 providing interconnectivity between a PSTN gateway and an IP-PBX.</span></span>

<span data-ttu-id="49ac9-110">**Межмагистральная маршрутизация между шлюзом и IP-УАТС**</span><span class="sxs-lookup"><span data-stu-id="49ac9-110">**Intertrunk routing between gateway and IP PBX**</span></span>

<span data-ttu-id="49ac9-111">![Схема подключения Lync Server к ТСОП-шлюзу/IP-УАТС](images/JJ721940.cc3858ca-2ee3-4d51-8a51-db078366b50b(OCS.15).jpg "Схема подключения Lync Server к ТСОП-шлюзу/IP-УАТС")</span><span class="sxs-lookup"><span data-stu-id="49ac9-111">![Lync Server connecting PSTN gateway/IP-PBX diagram](images/JJ721940.cc3858ca-2ee3-4d51-8a51-db078366b50b(OCS.15).jpg "Lync Server connecting PSTN gateway/IP-PBX diagram")</span></span>

<span data-ttu-id="49ac9-112">На следующей схеме показана платформа Lync Server 2013, соединяющая две системы IP-УАТС.</span><span class="sxs-lookup"><span data-stu-id="49ac9-112">The following diagram illustrates Lync Server 2013 interconnecting two IP-PBX systems.</span></span>

<span data-ttu-id="49ac9-113">**Межмагистральная маршрутизация между двумя IP-АТС**</span><span class="sxs-lookup"><span data-stu-id="49ac9-113">**Intertrunk routing between two IP PBXs**</span></span>

<span data-ttu-id="49ac9-114">![Схема соединений между системами IP-УАТС с помощью Lync Server](images/JJ721940.6ba18ec9-df70-498a-9cf7-7fc41e5ec432(OCS.15).jpg "Схема соединений между системами IP-УАТС с помощью Lync Server")</span><span class="sxs-lookup"><span data-stu-id="49ac9-114">![Lync Server interconnecting IP-PAX systems diagram](images/JJ721940.6ba18ec9-df70-498a-9cf7-7fc41e5ec432(OCS.15).jpg "Lync Server interconnecting IP-PAX systems diagram")</span></span>

</div>

<span> </span>

</div>

</div>

</div>

