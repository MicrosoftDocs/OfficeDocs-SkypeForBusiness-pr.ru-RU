---
title: 'Lync Server 2013: контроль допуска звонков в сети MPLS'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Call admission control on an MPLS network
ms:assetid: 0beec6be-2431-4255-a3d2-512dd030e66a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398168(v=OCS.15)
ms:contentKeyID: 48183387
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: efed0826aa35a557628dd64bfdcea9bc22ced28a
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48535186"
---
# <a name="call-admission-control-on-an-mpls-network-with-lync-server-2013"></a><span data-ttu-id="e5826-102">Управление допуском звонков в сети MPLS с помощью Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e5826-102">Call admission control on an MPLS network with Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e5826-103">_**Последнее изменение темы:** 2012-09-22_</span><span class="sxs-lookup"><span data-stu-id="e5826-103">_**Topic Last Modified:** 2012-09-22_</span></span>

<span data-ttu-id="e5826-p101">В сети с многопротокольной коммутацией по меткам (MPLS) все сайты соединены в полную сетку. То есть, все сайты подключаются напрямую к MPLS-магистрали поставщика услуг Интернета, и каждому сайту выделяется полоса пропускания, используемая для взаимодействия по каналу глобальной сети с MPLS-облаком. Не существует ни сетевого концентратора, ни центрального сайта для управления IP-маршрутизацией. На следующему рисунке показана простая сеть, основанная на технологии MPLS.</span><span class="sxs-lookup"><span data-stu-id="e5826-p101">In a Multiprotocol Label Switching (MPLS) network, all sites are connected by a full-mesh. That is, all sites are connected directly to the MPLS backbone of the Internet service provider, and each site is provisioned bandwidth to be used across a WAN link to the MPLS cloud. There is no network hub or central site to control IP routing. The following figure shows a simple network based on MPLS technology.</span></span>

<span data-ttu-id="e5826-108">**Пример сети MPLS**</span><span class="sxs-lookup"><span data-stu-id="e5826-108">**Example MPLS network**</span></span>

<span data-ttu-id="e5826-109">![CAC с MPLS](images/Gg398168.54602e6e-ec11-4dae-936d-b01acda8a179(OCS.15).jpg "CAC с MPLS")</span><span class="sxs-lookup"><span data-stu-id="e5826-109">![CAC with MPLS](images/Gg398168.54602e6e-ec11-4dae-936d-b01acda8a179(OCS.15).jpg "CAC with MPLS")</span></span>

<span data-ttu-id="e5826-p102">Чтобы развернуть контроль допуска звонков в сети MPLS, вам требуется создать область сети, представляющую облако MPLS, и создать сетевой узел, представляющий каждый вспомогательный сайт MPLS. На следующем рисунке показано, как следует настроить область сети и сетевые узлы, чтобы они представляли пример сети MPLS из предыдущего примера. Ограничения для общей пропускной способности и пропускной способности сеанса основываются на емкости канала связи глобальной сети от каждого сетевого узла к области сети, которая представляет облако MPLS.</span><span class="sxs-lookup"><span data-stu-id="e5826-p102">To deploy call admission control (CAC) in an MPLS network, you create a network region to represent the MPLS cloud, and create a network site to represent each MPLS satellite site. The following figure illustrates how the network region and network sites should be configured to represent the example MPLS network in the previous figure. The overall bandwidth limits and bandwidth session limits are then based on the capacity of the WAN link from each network site to the network region that represents the MPLS cloud.</span></span>

<span data-ttu-id="e5826-113">**Область сети и сетевые узлы для сети MPLS**</span><span class="sxs-lookup"><span data-stu-id="e5826-113">**Network region and network sites for an MPLS network**</span></span>

<span data-ttu-id="e5826-114">![Контроль допуска звонков (CAC) со схемой MPLS](images/Gg398168.f8f76283-5c0c-4133-8a78-3fbbfd016dc4(OCS.15).jpg "Контроль допуска звонков (CAC) со схемой MPLS")</span><span class="sxs-lookup"><span data-stu-id="e5826-114">![Call Admission Control (CAC) with MPLS diagram](images/Gg398168.f8f76283-5c0c-4133-8a78-3fbbfd016dc4(OCS.15).jpg "Call Admission Control (CAC) with MPLS diagram")</span></span>

</div>

<span> </span>

</div>

</div>

</div>

