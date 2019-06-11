---
title: 'Lync Server 2013: масштабируемая консолидированная пограничная топология, балансировка нагрузки на DNS с закрытыми IP-адресами и трансляцией сетевых адресов'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Scaled consolidated edge, DNS load balancing with private IP addresses using NAT
ms:assetid: c7ca4ca8-c639-4d93-86d7-8891170cacbc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398823(v=OCS.15)
ms:contentKeyID: 48185369
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1ccae081e80b61be767dfbdc82664ff90d4dfabd
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34822267"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat-in-lync-server-2013"></a><span data-ttu-id="8e0e5-102">Масштабируемая консолидированная пограничная топология, балансировка нагрузки на DNS с закрытыми IP-адресами и трансляцией сетевых адресов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8e0e5-102">Scaled consolidated edge, DNS load balancing with private IP addresses using NAT in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8e0e5-103">_**Тема последнего изменения:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="8e0e5-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="8e0e5-104">В топологии пула пограничного сервера два или более пограничных сервера развертываются в качестве пула балансировки нагрузки в демилитаризованной зоне центра обработки данных.</span><span class="sxs-lookup"><span data-stu-id="8e0e5-104">In the Edge Server pool topology, two or more Edge Servers are deployed as a load-balanced pool in the perimeter network of the data center.</span></span> <span data-ttu-id="8e0e5-105">Балансировка нагрузки службы доменных имен (DNS) используется для трафика как в внешних, так и в внутренних интерфейсах Edge.</span><span class="sxs-lookup"><span data-stu-id="8e0e5-105">Domain Name System (DNS) load balancing is used for traffic to both the external and internal Edge interfaces.</span></span>

<span data-ttu-id="8e0e5-106">Если в вашей организации требуется поддержка более 15 000 доступа к клиентским подключениям службы EDGE, 1 000 Active Server Web конференций Service Connections или 500 одновременные сеансы и/или высокий уровень доступности пограничного сервера. Эта топология обеспечивает преимущества масштабируемости и поддержки перехода на другой ресурс.</span><span class="sxs-lookup"><span data-stu-id="8e0e5-106">If your organization requires support for more than 15,000 Access Edge service client connections, 1,000 active Lync Server Web Conferencing service client connections, or 500 concurrent A/V Edge sessions, and/or high availability of the Edge Server is important, this topology offers the advantages of scalability and failover support.</span></span>

<span data-ttu-id="8e0e5-107">На рисунке не показаны режиссеры, необязательная роль сервера, развернутая во внутренней сети между пограничными серверами и пулами и сервером переднего плана.</span><span class="sxs-lookup"><span data-stu-id="8e0e5-107">The figure does not show Directors, an optional server role deployed in the internal network between the Edge Servers and your Front End pools or server.</span></span> <span data-ttu-id="8e0e5-108">Сведения о топологии для режиссеров можно найти [в разделе компоненты, необходимые для режиссера в Lync Server 2013](lync-server-2013-components-required-for-the-director.md).</span><span class="sxs-lookup"><span data-stu-id="8e0e5-108">For details about the topology for Directors, see [Components required for the Director in Lync Server 2013](lync-server-2013-components-required-for-the-director.md).</span></span> <span data-ttu-id="8e0e5-109">Рисунок представляет собой один обратный прокси-сервер.</span><span class="sxs-lookup"><span data-stu-id="8e0e5-109">The figure represents a single reverse proxy.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="8e0e5-110">На рисунке показана ориентация и пример IP-адресации, но они не должны представлять реальные потоки связи с правильным входящим и исходящим трафиком.</span><span class="sxs-lookup"><span data-stu-id="8e0e5-110">The figure shown is for orientation and example IP addressing, but does not intend to represent actual communication flows with the correct incoming and outgoing traffic.</span></span> <span data-ttu-id="8e0e5-111">Рисунок представляет собой вид высокого уровня возможных трафиков.</span><span class="sxs-lookup"><span data-stu-id="8e0e5-111">The figure represents a high level view of possible traffic.</span></span> <span data-ttu-id="8e0e5-112">Сведения о потоке трафика в том виде, в котором они относятся к входящим и исходящим портам (для прослушивания портов) и исходящих (на конечных серверах или клиентах), представлены в схеме сводки порта в каждом сценарии.</span><span class="sxs-lookup"><span data-stu-id="8e0e5-112">Details for traffic flow as they pertain to incoming (to listening ports) and outgoing (to destination servers or clients) is represented in the Port Summary diagram in each scenario.</span></span> <span data-ttu-id="8e0e5-113">Например, TCP 443 фактически является действительным (только для прокси-сервера Edge или Reverse) и является двусторонним потоком с точки зрения протокола TCP.</span><span class="sxs-lookup"><span data-stu-id="8e0e5-113">For example, TCP 443 is actually inbound (to the Edge or reverse proxy) only, and is only a two-way flow from a protocol (TCP) perspective.</span></span> <span data-ttu-id="8e0e5-114">Кроме того, на рисунке показано, как изменится трафик при изменении при преобразовании NAT (преобразование сетевых адресов) (конечный адрес изменяется на входящем, адрес источника меняется на исходящем).</span><span class="sxs-lookup"><span data-stu-id="8e0e5-114">Additionally, the figure shows the nature of traffic as it changes when NAT (network address translation) occurs (destination address is changed on inbound, source address is changed on outbound).</span></span> <span data-ttu-id="8e0e5-115">Пример внешнего и внутреннего межсетевого экрана, а серверные интерфейсы отображаются только в справочных целях.</span><span class="sxs-lookup"><span data-stu-id="8e0e5-115">Example external and internal firewall, and server interfaces are shown for reference purposes only.</span></span> <span data-ttu-id="8e0e5-116">Наконец, показан пример связей по умолчанию шлюза и маршрута, где это применимо.</span><span class="sxs-lookup"><span data-stu-id="8e0e5-116">Finally, example default gateway and route relationships are shown, where applicable.</span></span> <span data-ttu-id="8e0e5-117">Кроме того, обратите внимание, что схема использует <EM>com</EM> -зону DNS для представления внешней зоны DNS для обратного прокси-сервера и пограничного сервера, а зона DNS <EM>.NET</EM> — для внутренней зоны DNS.</span><span class="sxs-lookup"><span data-stu-id="8e0e5-117">Note also that the diagram uses the <EM>.com</EM> DNS zone to represent the external DNS zone for both reverse proxy and Edge Servers, and the <EM>.net</EM> DNS zone refers to the internal DNS zone.</span></span>



</div>

<span data-ttu-id="8e0e5-118">Новая возможность для Microsoft Lync Server 2013 — поддержка адресации IPv6.</span><span class="sxs-lookup"><span data-stu-id="8e0e5-118">New to Microsoft Lync Server 2013 is support for IPv6 addressing.</span></span> <span data-ttu-id="8e0e5-119">Как и IPv4-адресация, адреса IPv6 должны быть назначены таким образом, чтобы они были частью назначенного адресного пространства IPv6.</span><span class="sxs-lookup"><span data-stu-id="8e0e5-119">Much like IPv4 addressing, IPv6 addresses must be assigned in such a way that the addresses are part of your assigned IPv6 address space.</span></span> <span data-ttu-id="8e0e5-120">Адреса в этом разделе предназначены только для примера.</span><span class="sxs-lookup"><span data-stu-id="8e0e5-120">The addresses in this topic are for example only.</span></span> <span data-ttu-id="8e0e5-121">Вы должны получить IPv6-адреса, которые будут работать в развертывании, выдать соответствующую область и будут взаимодействовать с внутренней и внешней адресацией.</span><span class="sxs-lookup"><span data-stu-id="8e0e5-121">You must acquire IPv6 addresses that will function in your deployment, provide the correct scope and will interoperate with internal and external addressing.</span></span> <span data-ttu-id="8e0e5-122">Windows Server предоставляет функцию, важную для переходов по операции IPv6 и связь IPv4 и IPv6, которая называется *двойным стеком*.</span><span class="sxs-lookup"><span data-stu-id="8e0e5-122">Windows Server provides a feature that is important to transitional IPv6 operation and IPv4 to IPv6 communication called the *dual stack*.</span></span> <span data-ttu-id="8e0e5-123">Двойной стек — это отдельный и раздельный сетевой стек для IPv4 и IPv6.</span><span class="sxs-lookup"><span data-stu-id="8e0e5-123">The dual stack is a separate and distinct network stack for IPv4 and for IPv6.</span></span> <span data-ttu-id="8e0e5-124">С помощью двух стеков можно одновременно назначать адресацию для IPv4 и IPv6 и допускает взаимодействие сервера с другими узлами и клиентами в зависимости от требований.</span><span class="sxs-lookup"><span data-stu-id="8e0e5-124">The dual stack is what allows you to assign addressing for IPv4 and IPv6 concurrently, and allows the server to communicate with other hosts and clients based on what their requirements are.</span></span>

<span data-ttu-id="8e0e5-125">Типичные типы адресов, которые будут использоваться для адресации IPv6, будут глобальными (аналогично общедоступными IPv4-адресами), уникальными локальными адресами IPv6 (аналогично частным диапазонам IPv4-адресов) и локальным адресам IPv6-связей (как автоматически частный IP адреса в Windows Server для IPv4</span><span class="sxs-lookup"><span data-stu-id="8e0e5-125">Typical address types that you will use for IPv6 addressing will be the IPv6 global addresses (similar to public IPv4 addresses), IPv6 unique local addresses (similar to the private IPv4 address ranges) and IPv6 link-local addresses (similar to automatic private IP addresses in Windows Server for IPv4)</span></span>

<span data-ttu-id="8e0e5-126">Существуют технологии преобразования сетевых адресов (NAT) для IPv6, позволяющие использовать протокол NAT IPv6 для IPv4 (обычно называемый механизмом NAT64), а также для IPv6 NAT (обычно называется NAT66).</span><span class="sxs-lookup"><span data-stu-id="8e0e5-126">Network address translation technologies (NAT) for IPv6 exist that will allow for NAT IPv6 to IPv4 (commonly referred to as NAT64) and for NAT IPv6 to IPv6 (commonly referred to as NAT66).</span></span> <span data-ttu-id="8e0e5-127">Наличие технологий NAT означает, что пять описанных ниже сценариев для пограничных серверов Lync Server по-прежнему действительны.</span><span class="sxs-lookup"><span data-stu-id="8e0e5-127">The existence of NAT technologies means that the five scenarios presented for Lync Server Edge Servers are still valid.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="8e0e5-128">Протокол IPv6 — это сложная тема, требующая тщательного планирования с помощью сетевой команды и поставщика услуг Интернета, чтобы убедиться в том, что адреса, назначенные на уровне Windows Server и на уровне Lync Server 2013, будут работать надлежащим образом.</span><span class="sxs-lookup"><span data-stu-id="8e0e5-128">IPv6 is a complex topic and requires careful planning with your networking team and your Internet provider to ensure that the addresses you assign at the Windows server level and at the Lync Server 2013 level will work as expected.</span></span> <span data-ttu-id="8e0e5-129">Для получения доступа к дополнительным ресурсам, содержащим информацию о планировании и адресации IPv6, воспользуйтесь ссылками, приведенными в конце этого раздела.</span><span class="sxs-lookup"><span data-stu-id="8e0e5-129">See the links at the end of this topic for additional resources on IPv6 addressing and planning.</span></span>



</div>

<span data-ttu-id="8e0e5-130">![899546d4-2eef-44d2-8317-51c5f699cd2a] (images/Gg398823.899546d4-2eef-44d2-8317-51c5f699cd2a(OCS.15).jpg "899546d4-2eef-44d2-8317-51c5f699cd2a")</span><span class="sxs-lookup"><span data-stu-id="8e0e5-130">![899546d4-2eef-44d2-8317-51c5f699cd2a](images/Gg398823.899546d4-2eef-44d2-8317-51c5f699cd2a(OCS.15).jpg "899546d4-2eef-44d2-8317-51c5f699cd2a")</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="8e0e5-131">Если вы используете управление допуском звонков (CAC), вам по-прежнему необходимо назначать адреса IPv4 внутреннему интерфейсу пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="8e0e5-131">If you are using Call Admission Control (CAC), you still must assign IPv4 addresses to the Edge Server internal interface.</span></span> <span data-ttu-id="8e0e5-132">CAC использует IPv4-адреса, и им должны быть доступны для работы.</span><span class="sxs-lookup"><span data-stu-id="8e0e5-132">CAC uses IPv4 addresses and must have them available to operate.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="8e0e5-133">Содержание</span><span class="sxs-lookup"><span data-stu-id="8e0e5-133">In This Section</span></span>

  - [<span data-ttu-id="8e0e5-134">Сводка по сертификатам — масштабируемая консолидированная пограничная топология, балансировка нагрузки на DNS с закрытыми IP-адресами и трансляцией сетевых адресов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8e0e5-134">Certificate summary - Scaled consolidated edge, DNS load balancing with private IP addresses using NAT in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md)

  - [<span data-ttu-id="8e0e5-135">Сводка по портам — масштабируемая консолидированная пограничная топология, балансировка нагрузки на DNS с закрытыми IP-адресами и трансляцией сетевых адресов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8e0e5-135">Port summary - Scaled consolidated edge, DNS load balancing with private IP addresses using NAT in Lync Server 2013</span></span>](lync-server-2013-port-summary-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md)

  - [<span data-ttu-id="8e0e5-136">Сводка по DNS — масштабируемая консолидированная пограничная топология, балансировка нагрузки на DNS с закрытыми IP-адресами и трансляцией сетевых адресов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8e0e5-136">DNS summary - Scaled consolidated edge, DNS load balancing with private IP addresses using NAT in Lync Server 2013</span></span>](lync-server-2013-dns-summary-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="8e0e5-137">См. также</span><span class="sxs-lookup"><span data-stu-id="8e0e5-137">See Also</span></span>


[<span data-ttu-id="8e0e5-138">Архитектура адресации протокола IP версии 6</span><span class="sxs-lookup"><span data-stu-id="8e0e5-138">IP Version 6 Addressing Architecture</span></span>](http://tools.ietf.org/html/rfc4291)  
[<span data-ttu-id="8e0e5-139">Формат адреса глобального одноадресной рассылки IPv6</span><span class="sxs-lookup"><span data-stu-id="8e0e5-139">IPv6 Global Unicast Address Format</span></span>](http://tools.ietf.org/html/rfc3587)  
[<span data-ttu-id="8e0e5-140">Уникальные локальные адреса одноадресной рассылки IPv6</span><span class="sxs-lookup"><span data-stu-id="8e0e5-140">Unique Local IPv6 Unicast Addresses</span></span>](http://tools.ietf.org/html/rfc4193)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

