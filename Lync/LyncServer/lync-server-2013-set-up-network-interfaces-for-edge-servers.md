---
title: 'Lync Server 2013: настройка сетевых интерфейсов для пограничных серверов'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Set up network interfaces for Edge Servers
ms:assetid: b0aecdf6-4ae2-46f6-b9b6-948bfc3df11e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412847(v=OCS.15)
ms:contentKeyID: 48185152
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e7263c2d7cad3cf1339351f2cb5f90b15a9fa0a2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34821917"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="set-up-network-interfaces-for-edge-servers-in-lync-server-2013"></a><span data-ttu-id="54c14-102">Настройка сетевых интерфейсов для пограничных серверов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="54c14-102">Set up network interfaces for Edge Servers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="54c14-103">_**Тема последнего изменения:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="54c14-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="54c14-104">Каждый пограничный сервер является многосетевым компьютером с внешними и внутренними интерфейсами.</span><span class="sxs-lookup"><span data-stu-id="54c14-104">Each Edge Server is a multihomed computer with external and internal facing interfaces.</span></span> <span data-ttu-id="54c14-105">Параметры системы доменных имен (DNS) адаптера зависят от того, есть ли DNS-серверы в сети периметра.</span><span class="sxs-lookup"><span data-stu-id="54c14-105">The adapter Domain Name System (DNS) settings depend on whether there are DNS servers in the perimeter network.</span></span> <span data-ttu-id="54c14-106">Если DNS-серверы находятся в сети периметра, они должны иметь зону с одной или несколькими записями DNS A для серверов или групп следующего прыжка (то есть режиссера или определенного пула переднего плана), а также для внешних запросов, которые они ссылаются на подстановку имен на другие общедоступные DNS-серверы.</span><span class="sxs-lookup"><span data-stu-id="54c14-106">If DNS servers exist in the perimeter, they must have a zone containing one or more DNS A records for the next hop server or pool (that is, either a Director or a designated Front End pool), and for external queries they refer name lookups to other public DNS servers.</span></span> <span data-ttu-id="54c14-107">Если в демилитаризованной зоне нет DNS-серверов, пограничный сервер использует внешние DNS-серверы для разрешения поиска имен Интернета и каждый пограничный сервер использует узел для сопоставления имен серверов следующего прыжка с IP-адресами.</span><span class="sxs-lookup"><span data-stu-id="54c14-107">If no DNS servers exist in the perimeter, the Edge Server(s) use external DNS servers to resolve Internet name lookups, and each Edge Server uses a HOST to resolve the next hop server names to IP addresses.</span></span>

<div>

<table>
<thead>
<tr class="header">
<th><img src="images/Gg398321.security(OCS.15).gif" title="разрешения" alt="security" /><span data-ttu-id="54c14-109">Примечание о безопасности:</span><span class="sxs-lookup"><span data-stu-id="54c14-109">Security Note:</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="54c14-110">По соображениям безопасности не рекомендуется, чтобы пограничные серверы не могли получать доступ к DNS-серверу, находящемуся во внутренней сети.</span><span class="sxs-lookup"><span data-stu-id="54c14-110">For security reasons, we recommend that you do not have your Edge Servers access a DNS server located in the internal network.</span></span></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="to-configure-interfaces-with-dns-servers-in-the-perimeter-network"></a><span data-ttu-id="54c14-111">Настройка интерфейсов DNS-серверов в демилитаризованной зоне</span><span class="sxs-lookup"><span data-stu-id="54c14-111">To configure interfaces with DNS servers in the perimeter network</span></span>

1.  <span data-ttu-id="54c14-112">Установите два сетевых адаптера для каждого пограничного сервера, один — для внутреннего интерфейса, а другой — для внешнего интерфейса.</span><span class="sxs-lookup"><span data-stu-id="54c14-112">Install two network adapters for each Edge Server, one for the internal-facing interface and one for the external-facing interface.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="54c14-113">Внутренние и внешние подсети должны поддерживать маршрутизацию между собой.</span><span class="sxs-lookup"><span data-stu-id="54c14-113">The internal and external subnets must not be routable to each other.</span></span>

    
    </div>

2.  <span data-ttu-id="54c14-114">На внешнем интерфейсе настройте три статических IP-адреса для подсети внешних сетей (также называемые демилитаризованной зоной, ДМЗ, экранированная подсеть) и наведите шлюз по умолчанию на внутренний интерфейс внешнего брандмауэра.</span><span class="sxs-lookup"><span data-stu-id="54c14-114">On the external interface, configure three static IP addresses on the external perimeter network (also known as DMZ, demilitarized zone, and screened subnet) subnet, and point the default gateway to the internal interface of the external firewall.</span></span> <span data-ttu-id="54c14-115">Настройте параметры DNS адаптера так, чтобы они указывали на пару DNS-серверов с периметром.</span><span class="sxs-lookup"><span data-stu-id="54c14-115">Configure adapter DNS settings to point to a pair of perimeter DNS servers.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="54c14-116">Вы можете использовать только один IP-адрес для этого интерфейса, но для этого вам нужно изменить назначения порта на нестандартные значения.</span><span class="sxs-lookup"><span data-stu-id="54c14-116">It is possible to use as few as one IP address for this interface, but to do this you need to change the port assignments to non-standard values.</span></span> <span data-ttu-id="54c14-117">Это определяется при создании топологии в построителе топологии.</span><span class="sxs-lookup"><span data-stu-id="54c14-117">You determine this when you create the topology in Topology Builder.</span></span>

    
    </div>

3.  <span data-ttu-id="54c14-118">На внутреннем интерфейсе настройте один статический IP-адрес для подсети внутренней сети периметра и не устанавливайте шлюз по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="54c14-118">On the internal interface, configure one static IP address on the internal perimeter network subnet and do not set a default gateway.</span></span> <span data-ttu-id="54c14-119">Настройте параметры DNS для адаптера так, чтобы они указывали хотя бы один DNS-сервер, предпочтительно пару DNS-серверов с демилитаризованными точками.</span><span class="sxs-lookup"><span data-stu-id="54c14-119">Configure adapter DNS settings to point to at least one DNS server, preferably a pair of perimeter DNS servers.</span></span>

4.  <span data-ttu-id="54c14-120">Создавайте постоянные статические маршруты на внутреннем интерфейсе для всех внутренних сетей, где находятся клиенты, Lync Server 2013 и серверы единой системы обмена сообщениями Exchange.</span><span class="sxs-lookup"><span data-stu-id="54c14-120">Create persistent static routes on the internal interface to all internal networks where clients, Lync Server 2013, and Exchange Unified Messaging (UM) servers reside.</span></span>

</div>

<div>

## <a name="to-configure-interfaces-without-dns-servers-in-the-perimeter-network"></a><span data-ttu-id="54c14-121">Настройка интерфейсов без DNS-серверов в защищаемой сети</span><span class="sxs-lookup"><span data-stu-id="54c14-121">To configure interfaces without DNS servers in the perimeter network</span></span>

1.  <span data-ttu-id="54c14-122">Установите два сетевых адаптера для каждого пограничного сервера, один — для внутреннего интерфейса, а другой — для внешнего интерфейса.</span><span class="sxs-lookup"><span data-stu-id="54c14-122">Install two network adapters for each Edge Server, one for the internal-facing interface and one for the external-facing interface.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="54c14-123">Внутренние и внешние подсети должны поддерживать маршрутизацию между собой.</span><span class="sxs-lookup"><span data-stu-id="54c14-123">The internal and external subnets must not be routable to each other.</span></span>

    
    </div>

2.  <span data-ttu-id="54c14-124">На внешнем интерфейсе настройте три статических IP-адреса для подсети внешней сети периметра.</span><span class="sxs-lookup"><span data-stu-id="54c14-124">On the external interface, configure three static IP addresses on the external perimeter network subnet.</span></span> <span data-ttu-id="54c14-125">Вы также можете настроить шлюз по умолчанию во внешнем интерфейсе.</span><span class="sxs-lookup"><span data-stu-id="54c14-125">You also configure the default gateway on the external interface.</span></span> <span data-ttu-id="54c14-126">Например, определите маршрутизатор, подключенный к Интернету, или внешний брандмауэр в качестве шлюза по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="54c14-126">For example, define the Internet-facing router or the external firewall as the default gateway.</span></span> <span data-ttu-id="54c14-127">Настройте параметры DNS таким образом, чтобы они указывали на DNS-сервер, предпочтительно для пары внешних DNS-серверов.</span><span class="sxs-lookup"><span data-stu-id="54c14-127">Configure DNS settings to point to a DNS server, preferably to a pair of external DNS servers.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="54c14-128">Возможно, но не рекомендуется, чтобы использовать в качестве одного IP-адреса внешний интерфейс.</span><span class="sxs-lookup"><span data-stu-id="54c14-128">It is possible, but not recommended, to use as few as one IP address for the external interface.</span></span> <span data-ttu-id="54c14-129">Чтобы сделать это, вам нужно изменить назначения порта на нестандартные значения и из порта 443 по умолчанию, который обычно является "удобным для взаимодействия клиентов".</span><span class="sxs-lookup"><span data-stu-id="54c14-129">To allow this to work, you need to change the port assignments to non-standard values, and away from the default port 443 that is typically “firewall friendly” for client communication.</span></span> <span data-ttu-id="54c14-130">При создании топологии в построителе топологии вы определяете параметр IP-адреса и параметры порта.</span><span class="sxs-lookup"><span data-stu-id="54c14-130">You determine the IP address setting and the port settings when you create the topology in Topology Builder.</span></span>

    
    </div>

3.  <span data-ttu-id="54c14-131">На внутреннем интерфейсе настройте один статический IP-адрес для подсети внутренней сети периметра и не устанавливайте шлюз по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="54c14-131">On the internal interface, configure one static IP address on the internal perimeter network subnet and do not set a default gateway.</span></span> <span data-ttu-id="54c14-132">Оставьте пустыми параметры DNS для адаптера.</span><span class="sxs-lookup"><span data-stu-id="54c14-132">Leave adapter DNS settings empty.</span></span>

4.  <span data-ttu-id="54c14-133">Создавайте постоянные статические маршруты на внутреннем интерфейсе для всех внутренних сетей, где находятся клиенты Lync или серверы с Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="54c14-133">Create persistent static routes on the internal interface to all internal networks where Lync clients or servers running Lync Server 2013 reside.</span></span>

5.  <span data-ttu-id="54c14-134">Измените файл узла на каждом пограничном сервере, чтобы он содержал запись для сервера следующего прыжка или виртуального IP-адреса (VIP) (запись будет режиссером, сервером Standard Edition или пулом переднего плана, настроенным в качестве адреса следующего прыжка пограничного сервера в Topology Builder).</span><span class="sxs-lookup"><span data-stu-id="54c14-134">Edit the HOST file on each Edge Server to contain a record for the next hop server or virtual IP (VIP) (the record will be the Director, Standard Edition server, or a Front End pool that was configured as the Edge Server next hop address in Topology Builder).</span></span> <span data-ttu-id="54c14-135">При использовании балансировки нагрузки DNS включите строку для каждого участника в пуле следующего прыжка.</span><span class="sxs-lookup"><span data-stu-id="54c14-135">If you are using DNS load balancing, include a line for each member of the next hop pool.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

