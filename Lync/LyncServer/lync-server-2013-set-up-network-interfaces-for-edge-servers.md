---
title: 'Lync Server 2013: Настройка сетевых интерфейсов для пограничных серверов'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Set up network interfaces for Edge Servers
ms:assetid: b0aecdf6-4ae2-46f6-b9b6-948bfc3df11e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412847(v=OCS.15)
ms:contentKeyID: 48185152
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 267db7062c19a0b1344d11f27205a51bf1e750ae
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42182152"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="set-up-network-interfaces-for-edge-servers-in-lync-server-2013"></a><span data-ttu-id="2e5ce-102">Настройка сетевых интерфейсов для пограничных серверов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2e5ce-102">Set up network interfaces for Edge Servers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2e5ce-103">_**Последнее изменение темы:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="2e5ce-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="2e5ce-p101">Пограничный сервер — это многосетевой компьютер, имеющий внешние и внутренние интерфейсы. Выбор параметров DNS для сетевого адаптера зависит от наличия DNS-серверов в сети периметра. Если в сети периметра есть DNS-серверы, то они должны иметь зону, содержащую как минимум одну DNS-запись A для сервера или пула следующего прыжка (Директор или назначенный интерфейсный пул). Для разрешения имен внешних запросов эти DNS-серверы используют другие общедоступные DNS-серверы. Если в сети периметра нет ни одного DNS-сервера, то для разрешения имен в Интернете пограничные серверы используют внешние DNS-серверы, а для разрешения имен серверов следующего прыжка в IP-адреса каждый пограничный сервер использует файл HOST.</span><span class="sxs-lookup"><span data-stu-id="2e5ce-p101">Each Edge Server is a multihomed computer with external and internal facing interfaces. The adapter Domain Name System (DNS) settings depend on whether there are DNS servers in the perimeter network. If DNS servers exist in the perimeter, they must have a zone containing one or more DNS A records for the next hop server or pool (that is, either a Director or a designated Front End pool), and for external queries they refer name lookups to other public DNS servers. If no DNS servers exist in the perimeter, the Edge Server(s) use external DNS servers to resolve Internet name lookups, and each Edge Server uses a HOST to resolve the next hop server names to IP addresses.</span></span>

<div>

<table>
<thead>
<tr class="header">
<th><img src="images/Gg398321.security(OCS.15).gif" title="защиты" alt="security" /><span data-ttu-id="2e5ce-109">Примечание о безопасности:</span><span class="sxs-lookup"><span data-stu-id="2e5ce-109">Security Note:</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="2e5ce-110">По соображениям безопасности не рекомендуется предоставлять пограничным серверам доступ к DNS-серверу, расположенному во внутренней сети.</span><span class="sxs-lookup"><span data-stu-id="2e5ce-110">For security reasons, we recommend that you do not have your Edge Servers access a DNS server located in the internal network.</span></span></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="to-configure-interfaces-with-dns-servers-in-the-perimeter-network"></a><span data-ttu-id="2e5ce-111">Настройка интерфейсов при наличии DNS-серверов в сети периметра</span><span class="sxs-lookup"><span data-stu-id="2e5ce-111">To configure interfaces with DNS servers in the perimeter network</span></span>

1.  <span data-ttu-id="2e5ce-112">На каждом пограничном сервере установите два сетевых адаптера, один из которых предназначен для внутреннего интерфейса, а другой — для внешнего интерфейса.</span><span class="sxs-lookup"><span data-stu-id="2e5ce-112">Install two network adapters for each Edge Server, one for the internal-facing interface and one for the external-facing interface.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="2e5ce-113">Внутренние и внешние подсети должны поддерживать маршрутизацию между собой.</span><span class="sxs-lookup"><span data-stu-id="2e5ce-113">The internal and external subnets must not be routable to each other.</span></span>

    
    </div>

2.  <span data-ttu-id="2e5ce-p102">На внешнем интерфейсе настройте 3 статических IP-адреса для подсети внешней сети периметра (также называемой промежуточной подсетью) и задайте шлюз по умолчанию для внутреннего интерфейса внешнего брандмауэра. С помощью параметров DNS укажите два DNS-сервера сети периметра.</span><span class="sxs-lookup"><span data-stu-id="2e5ce-p102">On the external interface, configure three static IP addresses on the external perimeter network (also known as DMZ, demilitarized zone, and screened subnet) subnet, and point the default gateway to the internal interface of the external firewall. Configure adapter DNS settings to point to a pair of perimeter DNS servers.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="2e5ce-116">Для этого интерфейса можно использовать один IP-адрес, однако в этом случае потребуется изменить назначения порта на нестандартные значения.</span><span class="sxs-lookup"><span data-stu-id="2e5ce-116">It is possible to use as few as one IP address for this interface, but to do this you need to change the port assignments to non-standard values.</span></span> <span data-ttu-id="2e5ce-117">Это определяется при создании топологии в построителе топологий.</span><span class="sxs-lookup"><span data-stu-id="2e5ce-117">You determine this when you create the topology in Topology Builder.</span></span>

    
    </div>

3.  <span data-ttu-id="2e5ce-p104">На внутреннем интерфейсе настройте 1 статический IP-адрес для подсети внутренней сети периметра и не задавайте шлюз по умолчанию. С помощью параметров DNS укажите как минимум один DNS-сервер (рекомендуется для DNS-сервера периметра).</span><span class="sxs-lookup"><span data-stu-id="2e5ce-p104">On the internal interface, configure one static IP address on the internal perimeter network subnet and do not set a default gateway. Configure adapter DNS settings to point to at least one DNS server, preferably a pair of perimeter DNS servers.</span></span>

4.  <span data-ttu-id="2e5ce-120">Создайте постоянные статические маршруты на внутреннем интерфейсе для всех внутренних сетей, в которых расположены клиенты, Lync Server 2013 и серверы единой системы обмена сообщениями Exchange.</span><span class="sxs-lookup"><span data-stu-id="2e5ce-120">Create persistent static routes on the internal interface to all internal networks where clients, Lync Server 2013, and Exchange Unified Messaging (UM) servers reside.</span></span>

</div>

<div>

## <a name="to-configure-interfaces-without-dns-servers-in-the-perimeter-network"></a><span data-ttu-id="2e5ce-121">Настройка интерфейсов при отсутствии DNS-серверов в сети периметра</span><span class="sxs-lookup"><span data-stu-id="2e5ce-121">To configure interfaces without DNS servers in the perimeter network</span></span>

1.  <span data-ttu-id="2e5ce-122">На каждом пограничном сервере установите два сетевых адаптера, один из которых предназначен для внутреннего интерфейса, а другой — для внешнего интерфейса.</span><span class="sxs-lookup"><span data-stu-id="2e5ce-122">Install two network adapters for each Edge Server, one for the internal-facing interface and one for the external-facing interface.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="2e5ce-123">Внутренние и внешние подсети должны поддерживать маршрутизацию между собой.</span><span class="sxs-lookup"><span data-stu-id="2e5ce-123">The internal and external subnets must not be routable to each other.</span></span>

    
    </div>

2.  <span data-ttu-id="2e5ce-p105">На внешнем интерфейсе настройте 3 статических IP-адреса для подсети внешней сети периметра. На внешнем интерфейсе также можно настроить шлюз по умолчанию. Например, задайте в качестве шлюза по умолчанию маршрутизатор с выходом в Интернет или внешний брандмауэр. С помощью параметров DNS укажите DNS-сервер (рекомендуется задать 2 внешних DNS-сервера).</span><span class="sxs-lookup"><span data-stu-id="2e5ce-p105">On the external interface, configure three static IP addresses on the external perimeter network subnet. You also configure the default gateway on the external interface. For example, define the Internet-facing router or the external firewall as the default gateway. Configure DNS settings to point to a DNS server, preferably to a pair of external DNS servers.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="2e5ce-128">Для этого интерфейса можно использовать один IP-адрес.</span><span class="sxs-lookup"><span data-stu-id="2e5ce-128">It is possible, but not recommended, to use as few as one IP address for the external interface.</span></span> <span data-ttu-id="2e5ce-129">Однако в этом случае потребуется изменить назначения порта на нестандартные значения, отличающиеся от порта по умолчанию 443, который используется брандмауэров для связи с клиентами.</span><span class="sxs-lookup"><span data-stu-id="2e5ce-129">To allow this to work, you need to change the port assignments to non-standard values, and away from the default port 443 that is typically “firewall friendly” for client communication.</span></span> <span data-ttu-id="2e5ce-130">Вы определяете параметры IP-адреса и порта при создании топологии в построителе топологий.</span><span class="sxs-lookup"><span data-stu-id="2e5ce-130">You determine the IP address setting and the port settings when you create the topology in Topology Builder.</span></span>

    
    </div>

3.  <span data-ttu-id="2e5ce-p107">На внутреннем интерфейсе настройте 1 статический IP-адрес для подсети внутренней сети периметра и не задавайте шлюз по умолчанию. Оставьте параметры DNS пустыми.</span><span class="sxs-lookup"><span data-stu-id="2e5ce-p107">On the internal interface, configure one static IP address on the internal perimeter network subnet and do not set a default gateway. Leave adapter DNS settings empty.</span></span>

4.  <span data-ttu-id="2e5ce-133">Создайте постоянные статические маршруты на внутреннем интерфейсе для всех внутренних сетей, в которых расположены клиенты Lync или серверы Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2e5ce-133">Create persistent static routes on the internal interface to all internal networks where Lync clients or servers running Lync Server 2013 reside.</span></span>

5.  <span data-ttu-id="2e5ce-134">Измените файл узла на каждом пограничном сервере, чтобы он содержал запись для сервера следующего прыжка или виртуального IP-адреса (это запись будет директором, сервером Standard Edition или интерфейсным пулом, настроенным в качестве адреса следующего перехода пограничного сервера в построителе топологий).</span><span class="sxs-lookup"><span data-stu-id="2e5ce-134">Edit the HOST file on each Edge Server to contain a record for the next hop server or virtual IP (VIP) (the record will be the Director, Standard Edition server, or a Front End pool that was configured as the Edge Server next hop address in Topology Builder).</span></span> <span data-ttu-id="2e5ce-135">Если используется балансировка нагрузки на DNS, добавьте строку для каждого члена пула следующего прыжка.</span><span class="sxs-lookup"><span data-stu-id="2e5ce-135">If you are using DNS load balancing, include a line for each member of the next hop pool.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

