---
title: 'Lync Server 2013: единая консолидированная пограничная топология с общедоступными IP-адресами'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Single consolidated edge with public IP addresses
ms:assetid: a92d1179-6a1f-4efe-908a-f8dfc5024f30
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205148(v=OCS.15)
ms:contentKeyID: 48185035
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8189d360a43887e2992b8b8abf063ef96230e06e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764505"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="single-consolidated-edge-with-public-ip-addresses-in-lync-server-2013"></a><span data-ttu-id="e9b5f-102">Единая консолидированная пограничная топология с общедоступными IP-адресами в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e9b5f-102">Single consolidated edge with public IP addresses in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e9b5f-103">_**Тема последнего изменения:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="e9b5f-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="e9b5f-104">Если в вашей организации требуется поддержка менее чем 15 000 доступа к клиентам службы EDGE 1 000, служба веб-конференций Lync Server Web virtualizations и 500 одновременные и высокодоступные выпуски пограничного сервера не важны, эта топология обеспечивает преимущества более высоких аппаратных затрат и более простое развертывание.</span><span class="sxs-lookup"><span data-stu-id="e9b5f-104">If your organization needs support for fewer than 15,000 Access Edge service client connections, 1,000 active Lync Server Web Conferencing service client connections, and 500 concurrent A/V Edge sessions, and high availability of the Edge Server is not important, this topology offers the advantages of lower hardware cost and simpler deployment.</span></span> <span data-ttu-id="e9b5f-105">Если вам нужна большая емкость или требуется высокая доступность, необходимо развернуть топологию масштабируемой пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="e9b5f-105">If you need greater capacity or you require high availability, you should deploy a scaled consolidated Edge Server topology.</span></span>

  - <span></span>  
    [<span data-ttu-id="e9b5f-106">Масштабируемая консолидированная пограничная топология, балансировка нагрузки на DNS с закрытыми IP-адресами и трансляцией сетевых адресов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e9b5f-106">Scaled consolidated edge, DNS load balancing with private IP addresses using NAT in Lync Server 2013</span></span>](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md)

  - <span></span>  
    [<span data-ttu-id="e9b5f-107">Масштабируемая консолидированная пограничная топология, балансировка нагрузки на DNS с общедоступными IP-адресами в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e9b5f-107">Scaled consolidated edge, DNS load balancing with public IP addresses in Lync Server 2013</span></span>](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md)

  - <span></span>  
    [<span data-ttu-id="e9b5f-108">Масштабируемая консолидированная пограничная топология с аппаратными балансировщиками нагрузки в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e9b5f-108">Scaled consolidated edge with hardware load balancers in Lync Server 2013</span></span>](lync-server-2013-scaled-consolidated-edge-with-hardware-load-balancers.md)

<div>


> [!IMPORTANT]  
> <span data-ttu-id="e9b5f-109">При использовании общедоступного IP-адреса на пограничном сервере Шлюз по умолчанию на пограничном сервере больше не является брандмауэром или маршрутизатором, но маршрутизатор или брандмауэр на краю общедоступной сети (это будет общедоступный адрес).</span><span class="sxs-lookup"><span data-stu-id="e9b5f-109">When using public IP address on the Edge Server, the default gateway on the Edge Server is no longer your firewall or router, but the router or firewall at your public perimeter edge – which will be a public address.</span></span> <span data-ttu-id="e9b5f-110">Обратный прокси продолжает использовать маршрутизатор или брандмауэр, связанный с внешней сетью периметра.</span><span class="sxs-lookup"><span data-stu-id="e9b5f-110">The reverse proxy continues to use the router or firewall associated with the outermost perimeter network.</span></span> <span data-ttu-id="e9b5f-111">Разница между обратным прокси-сервером и пограничного сервера с общедоступными IP-адресами заключается в том, что обратный прокси по-прежнему использует NAT и пограничный сервер использует связь маршрута.</span><span class="sxs-lookup"><span data-stu-id="e9b5f-111">The difference between the reverse proxy and the Edge Server with public IP addresses is that the reverse proxy is still using NAT and the Edge Server is using a route relationship.</span></span>



</div>

<span data-ttu-id="e9b5f-112">На рисунке не показаны режиссеры, необязательная роль сервера, развернутая во внутренней сети между пограничными серверами и пулами и сервером переднего плана.</span><span class="sxs-lookup"><span data-stu-id="e9b5f-112">The figure does not show Directors, an optional server role deployed in the internal network between the Edge Servers and your Front End pools or server.</span></span> <span data-ttu-id="e9b5f-113">Сведения о топологии для режиссеров можно найти [в разделе компоненты, необходимые для режиссера в Lync Server 2013](lync-server-2013-components-required-for-the-director.md).</span><span class="sxs-lookup"><span data-stu-id="e9b5f-113">For details about the topology for Directors, see [Components required for the Director in Lync Server 2013](lync-server-2013-components-required-for-the-director.md).</span></span> <span data-ttu-id="e9b5f-114">Рисунок представляет собой один обратный прокси-сервер.</span><span class="sxs-lookup"><span data-stu-id="e9b5f-114">The figure represents a single reverse proxy.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e9b5f-115">На рисунке показана ориентация и пример IP-адресации, но они не должны представлять реальные потоки связи с правильным входящим и исходящим трафиком.</span><span class="sxs-lookup"><span data-stu-id="e9b5f-115">The figure shown is for orientation and example IP addressing, but does not intend to represent actual communication flows with the correct incoming and outgoing traffic.</span></span> <span data-ttu-id="e9b5f-116">Рисунок представляет собой вид высокого уровня возможных трафиков.</span><span class="sxs-lookup"><span data-stu-id="e9b5f-116">The figure represents a high level view of possible traffic.</span></span> <span data-ttu-id="e9b5f-117">Сведения о потоке трафика в том виде, в котором они относятся к входящим и исходящим портам (для прослушивания портов) и исходящих (на конечных серверах или клиентах), представлены в схеме сводки порта в каждом сценарии.</span><span class="sxs-lookup"><span data-stu-id="e9b5f-117">Details for traffic flow as they pertain to incoming (to listening ports) and outgoing (to destination servers or clients) is represented in the Port Summary diagram in each scenario.</span></span> <span data-ttu-id="e9b5f-118">Например, TCP 443 фактически является действительным (только для прокси-сервера Edge или Reverse) и является двусторонним потоком с точки зрения протокола TCP.</span><span class="sxs-lookup"><span data-stu-id="e9b5f-118">For example, TCP 443 is actually inbound (to the Edge or reverse proxy) only, and is only a two-way flow from a protocol (TCP) perspective.</span></span> <span data-ttu-id="e9b5f-119">Кроме того, на рисунке показано, как изменится трафик при изменении при преобразовании NAT (преобразование сетевых адресов) (конечный адрес изменяется на входящем, адрес источника меняется на исходящем).</span><span class="sxs-lookup"><span data-stu-id="e9b5f-119">Additionally, the figure shows the nature of traffic as it changes when NAT (network address translation) occurs (destination address is changed on inbound, source address is changed on outbound).</span></span> <span data-ttu-id="e9b5f-120">Пример внешнего и внутреннего межсетевого экрана, а серверные интерфейсы отображаются только в справочных целях.</span><span class="sxs-lookup"><span data-stu-id="e9b5f-120">Example external and internal firewall, and server interfaces are shown for reference purposes only.</span></span> <span data-ttu-id="e9b5f-121">Наконец, показан пример связей по умолчанию шлюза и маршрута, где это применимо.</span><span class="sxs-lookup"><span data-stu-id="e9b5f-121">Finally, example default gateway and route relationships are shown, where applicable.</span></span> <span data-ttu-id="e9b5f-122">Кроме того, обратите внимание, что схема использует <EM>com</EM> -зону DNS для представления внешней зоны DNS для обратного прокси-сервера и пограничного сервера, а зона DNS <EM>.NET</EM> — для внутренней зоны DNS.</span><span class="sxs-lookup"><span data-stu-id="e9b5f-122">Note also that the diagram uses the <EM>.com</EM> DNS zone to represent the external DNS zone for both reverse proxy and Edge Servers, and the <EM>.net</EM> DNS zone refers to the internal DNS zone.</span></span>



</div>

<span data-ttu-id="e9b5f-123">Новая возможность для Microsoft Lync Server 2013 — поддержка адресации IPv6.</span><span class="sxs-lookup"><span data-stu-id="e9b5f-123">New to Microsoft Lync Server 2013 is support for IPv6 addressing.</span></span> <span data-ttu-id="e9b5f-124">Как и IPv4-адресация, адреса IPv6 должны быть назначены таким образом, чтобы они были частью назначенного адресного пространства IPv6.</span><span class="sxs-lookup"><span data-stu-id="e9b5f-124">Much like IPv4 addressing, IPv6 addresses must be assigned in such a way that the addresses are part of your assigned IPv6 address space.</span></span> <span data-ttu-id="e9b5f-125">Адреса в этом разделе предназначены только для примера.</span><span class="sxs-lookup"><span data-stu-id="e9b5f-125">The addresses in this topic are for example only.</span></span> <span data-ttu-id="e9b5f-126">Вы должны получить IPv6-адреса, которые будут работать в развертывании, выдать соответствующую область и будут взаимодействовать с внутренней и внешней адресацией.</span><span class="sxs-lookup"><span data-stu-id="e9b5f-126">You must acquire IPv6 addresses that will function in your deployment, provide the correct scope and will interoperate with internal and external addressing.</span></span> <span data-ttu-id="e9b5f-127">Windows Server предоставляет функцию, важную для переходов по операции IPv6 и связь IPv4 и IPv6, которая называется *двойным стеком*.</span><span class="sxs-lookup"><span data-stu-id="e9b5f-127">Windows Server provides a feature that is important to transitional IPv6 operation and IPv4 to IPv6 communication called the *dual stack*.</span></span> <span data-ttu-id="e9b5f-128">Двойной стек — это отдельный и раздельный сетевой стек для IPv4 и IPv6.</span><span class="sxs-lookup"><span data-stu-id="e9b5f-128">The dual stack is a separate and distinct network stack for IPv4 and for IPv6.</span></span> <span data-ttu-id="e9b5f-129">С помощью двух стеков можно одновременно назначать адресацию для IPv4 и IPv6 и допускает взаимодействие сервера с другими узлами и клиентами в зависимости от требований.</span><span class="sxs-lookup"><span data-stu-id="e9b5f-129">The dual stack is what allows you to assign addressing for IPv4 and IPv6 concurrently, and allows the server to communicate with other hosts and clients based on what their requirements are.</span></span>

<span data-ttu-id="e9b5f-130">Типичные типы адресов, которые будут использоваться для адресации IPv6, будут глобальными (аналогично общедоступными IPv4-адресами), уникальными локальными адресами IPv6 (аналогично частным диапазонам IPv4-адресов) и локальным адресам IPv6-связей (как автоматически частный IP адреса в Windows Server для IPv4</span><span class="sxs-lookup"><span data-stu-id="e9b5f-130">Typical address types that you will use for IPv6 addressing will be the IPv6 global addresses (similar to public IPv4 addresses), IPv6 unique local addresses (similar to the private IPv4 address ranges) and IPv6 link-local addresses (similar to automatic private IP addresses in Windows Server for IPv4)</span></span>

<span data-ttu-id="e9b5f-131">Существуют технологии преобразования сетевых адресов (NAT) для IPv6, позволяющие использовать протокол NAT IPv6 для IPv4 (обычно называемый механизмом NAT64), а также для IPv6 NAT (обычно называется NAT66).</span><span class="sxs-lookup"><span data-stu-id="e9b5f-131">Network address translation technologies (NAT) for IPv6 exist that will allow for NAT IPv6 to IPv4 (commonly referred to as NAT64) and for NAT IPv6 to IPv6 (commonly referred to as NAT66).</span></span> <span data-ttu-id="e9b5f-132">Наличие технологий NAT означает, что пять описанных ниже сценариев для пограничных серверов Lync Server по-прежнему действительны.</span><span class="sxs-lookup"><span data-stu-id="e9b5f-132">The existence of NAT technologies means that the five scenarios presented for Lync Server Edge Servers are still valid.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="e9b5f-133">Протокол IPv6 — это сложная тема, требующая тщательного планирования с помощью сетевой команды и поставщика услуг Интернета, чтобы убедиться в том, что адреса, назначенные на уровне Windows Server и на уровне Lync Server 2013, будут работать надлежащим образом.</span><span class="sxs-lookup"><span data-stu-id="e9b5f-133">IPv6 is a complex topic and requires careful planning with your networking team and your Internet provider to ensure that the addresses you assign at the Windows server level and at the Lync Server 2013 level will work as expected.</span></span> <span data-ttu-id="e9b5f-134">Для получения доступа к дополнительным ресурсам, содержащим информацию о планировании и адресации IPv6, воспользуйтесь ссылками, приведенными в конце этого раздела.</span><span class="sxs-lookup"><span data-stu-id="e9b5f-134">See the links at the end of this topic for additional resources on IPv6 addressing and planning.</span></span>



</div>

<span data-ttu-id="e9b5f-135">**Единый объединенный край с топологией общедоступных IP-адресов**</span><span class="sxs-lookup"><span data-stu-id="e9b5f-135">**Single Consolidated Edge with Public IP Addresses topology**</span></span>

<span data-ttu-id="e9b5f-136">![2db9f9e1-75aa-4de0-ab3f-c6effddb4f4d](images/JJ205148.2db9f9e1-75aa-4de0-ab3f-c6effddb4f4d(OCS.15).jpg "2db9f9e1-75aa-4de0-ab3f-c6effddb4f4d")</span><span class="sxs-lookup"><span data-stu-id="e9b5f-136">![2db9f9e1-75aa-4de0-ab3f-c6effddb4f4d](images/JJ205148.2db9f9e1-75aa-4de0-ab3f-c6effddb4f4d(OCS.15).jpg "2db9f9e1-75aa-4de0-ab3f-c6effddb4f4d")</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="e9b5f-137">Если вы используете управление допуском звонков (CAC), вам по-прежнему необходимо назначать адреса IPv4 внутреннему интерфейсу пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="e9b5f-137">If you are using Call Admission Control (CAC), you still must assign IPv4 addresses to the Edge Server internal interface.</span></span> <span data-ttu-id="e9b5f-138">CAC использует IPv4-адреса, и им должны быть доступны для работы.</span><span class="sxs-lookup"><span data-stu-id="e9b5f-138">CAC uses IPv4 addresses and must have them available to operate.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="e9b5f-139">Содержание</span><span class="sxs-lookup"><span data-stu-id="e9b5f-139">In This Section</span></span>

  - [<span data-ttu-id="e9b5f-140">Сводка по сертификатам — единая консолидированная пограничная топология с общедоступными IP-адресами в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e9b5f-140">Certificate summary - Single consolidated edge with public IP addresses in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-single-consolidated-edge-with-public-ip-addresses.md)

  - [<span data-ttu-id="e9b5f-141">Сводка по портам — единая консолидированная пограничная топология с общедоступными IP-адресами в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e9b5f-141">Port summary - Single consolidated edge with public IP addresses in Lync Server 2013</span></span>](lync-server-2013-port-summary-single-consolidated-edge-with-public-ip-addresses.md)

  - [<span data-ttu-id="e9b5f-142">Сводка по DNS — единая консолидированная пограничная топология с общедоступными IP-адресами в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e9b5f-142">DNS summary - Single consolidated edge with public IP addresses in Lync Server 2013</span></span>](lync-server-2013-dns-summary-single-consolidated-edge-with-public-ip-addresses.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="e9b5f-143">См. также</span><span class="sxs-lookup"><span data-stu-id="e9b5f-143">See Also</span></span>


[<span data-ttu-id="e9b5f-144">Архитектура адресации протокола IP версии 6</span><span class="sxs-lookup"><span data-stu-id="e9b5f-144">IP Version 6 Addressing Architecture</span></span>](http://tools.ietf.org/html/rfc4291)  
[<span data-ttu-id="e9b5f-145">Формат адреса глобального одноадресной рассылки IPv6</span><span class="sxs-lookup"><span data-stu-id="e9b5f-145">IPv6 Global Unicast Address Format</span></span>](http://tools.ietf.org/html/rfc3587)  
[<span data-ttu-id="e9b5f-146">Уникальные локальные адреса одноадресной рассылки IPv6</span><span class="sxs-lookup"><span data-stu-id="e9b5f-146">Unique Local IPv6 Unicast Addresses</span></span>](http://tools.ietf.org/html/rfc4193)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

