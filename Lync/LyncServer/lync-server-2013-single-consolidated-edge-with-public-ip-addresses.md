---
title: 'Lync Server 2013: единый консолидированный край с общедоступными IP-адресами'
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
ms.openlocfilehash: fb5d8af424aa334c19847c993ef338d4ba81d5b6
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48519766"
---
# <a name="single-consolidated-edge-with-public-ip-addresses-in-lync-server-2013"></a><span data-ttu-id="34ce9-102">Единый консолидированный край с общедоступными IP-адресами в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="34ce9-102">Single consolidated edge with public IP addresses in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="34ce9-103">_**Последнее изменение темы:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="34ce9-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="34ce9-104">Если организации требуется поддержка менее 15 000 подключений клиентов пограничного сервера доступа, 1 000 активных веб-конференций Lync Server и 500 одновременные пограничные сеансы аудио-и видеоданных, а также высокая доступность пограничного сервера не важна, то эта топология обеспечивает преимущества снижения стоимости оборудования и упрощения развертывания.</span><span class="sxs-lookup"><span data-stu-id="34ce9-104">If your organization needs support for fewer than 15,000 Access Edge service client connections, 1,000 active Lync Server Web Conferencing service client connections, and 500 concurrent A/V Edge sessions, and high availability of the Edge Server is not important, this topology offers the advantages of lower hardware cost and simpler deployment.</span></span> <span data-ttu-id="34ce9-105">Если ваши серверы несут более высокую нагрузку или требуется высокий уровень доступности, то разверните масштабированную консолидированную топологию пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="34ce9-105">If you need greater capacity or you require high availability, you should deploy a scaled consolidated Edge Server topology.</span></span>

  - <span></span>  
    [<span data-ttu-id="34ce9-106">Масштабируемый консолидированный край, балансировка нагрузки на DNS с частными IP-адресами, использующими NAT, в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="34ce9-106">Scaled consolidated edge, DNS load balancing with private IP addresses using NAT in Lync Server 2013</span></span>](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md)

  - <span></span>  
    [<span data-ttu-id="34ce9-107">Масштабируемый консолидированный край, балансировка нагрузки на DNS с общедоступными IP-адресами в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="34ce9-107">Scaled consolidated edge, DNS load balancing with public IP addresses in Lync Server 2013</span></span>](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md)

  - <span></span>  
    [<span data-ttu-id="34ce9-108">Масштабируемая консолидированная пограничная система с аппаратными подсистемами балансировки нагрузки в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="34ce9-108">Scaled consolidated edge with hardware load balancers in Lync Server 2013</span></span>](lync-server-2013-scaled-consolidated-edge-with-hardware-load-balancers.md)

<div>


> [!IMPORTANT]  
> <span data-ttu-id="34ce9-109">При использовании общедоступного IP-адреса на пограничном сервере Шлюз по умолчанию на пограничном сервере больше не является брандмауэром или маршрутизатором, но маршрутизатор или брандмауэр на границе общедоступного периметра — это общедоступный адрес.</span><span class="sxs-lookup"><span data-stu-id="34ce9-109">When using public IP address on the Edge Server, the default gateway on the Edge Server is no longer your firewall or router, but the router or firewall at your public perimeter edge – which will be a public address.</span></span> <span data-ttu-id="34ce9-110">Обратный прокси-сервер будет по-прежнему использовать маршрутизатор или брандмауэр, связанный с самой внешней сетью периметра.</span><span class="sxs-lookup"><span data-stu-id="34ce9-110">The reverse proxy continues to use the router or firewall associated with the outermost perimeter network.</span></span> <span data-ttu-id="34ce9-111">Разница между обратным прокси-сервером и пограничным сервером с общедоступными IP-адресами заключается в том, что обратный прокси-сервер по-прежнему использует NAT, а пограничный сервер использует связь маршрута.</span><span class="sxs-lookup"><span data-stu-id="34ce9-111">The difference between the reverse proxy and the Edge Server with public IP addresses is that the reverse proxy is still using NAT and the Edge Server is using a route relationship.</span></span>



</div>

<span data-ttu-id="34ce9-112">На рисунке не показаны директора, необязательная роль сервера, развернутая во внутренней сети между пограничными серверами и интерфейсными пулами или сервером.</span><span class="sxs-lookup"><span data-stu-id="34ce9-112">The figure does not show Directors, an optional server role deployed in the internal network between the Edge Servers and your Front End pools or server.</span></span> <span data-ttu-id="34ce9-113">Сведения о топологии для директоров можно найти [в статье компоненты, необходимые для директора в Lync Server 2013](lync-server-2013-components-required-for-the-director.md).</span><span class="sxs-lookup"><span data-stu-id="34ce9-113">For details about the topology for Directors, see [Components required for the Director in Lync Server 2013](lync-server-2013-components-required-for-the-director.md).</span></span> <span data-ttu-id="34ce9-114">На рисунке показан один обратный прокси-сервер.</span><span class="sxs-lookup"><span data-stu-id="34ce9-114">The figure represents a single reverse proxy.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="34ce9-115">Показанный рисунок предназначен для общего ознакомления и примера IP-адресации, но не является репрезентацией действительных коммуникационных потоков с точным входящим и исходящим трафиком.</span><span class="sxs-lookup"><span data-stu-id="34ce9-115">The figure shown is for orientation and example IP addressing, but does not intend to represent actual communication flows with the correct incoming and outgoing traffic.</span></span> <span data-ttu-id="34ce9-116">Рисунок дает высокоуровневое представление о возможном трафике.</span><span class="sxs-lookup"><span data-stu-id="34ce9-116">The figure represents a high level view of possible traffic.</span></span> <span data-ttu-id="34ce9-117">Сведения о потоках трафика, относящихся к входящим данным (прослушивание портов) и исходящим данным (к конечным серверам или клиентам), представлены на диаграммах "Сводка по портам" в каждом сценарии.</span><span class="sxs-lookup"><span data-stu-id="34ce9-117">Details for traffic flow as they pertain to incoming (to listening ports) and outgoing (to destination servers or clients) is represented in the Port Summary diagram in each scenario.</span></span> <span data-ttu-id="34ce9-118">Например, TCP 443 является только входящим портом (для пограничного или обратного прокси-сервера) и является только двухсторонним потоком с перспективы протокола (TCP).</span><span class="sxs-lookup"><span data-stu-id="34ce9-118">For example, TCP 443 is actually inbound (to the Edge or reverse proxy) only, and is only a two-way flow from a protocol (TCP) perspective.</span></span> <span data-ttu-id="34ce9-119">Кроме того, на рисунке показан характер трафика после применения преобразования сетевых адресов (NAT) (конечный адрес изменяется на входящий, исходный адрес изменяется на исходящий).</span><span class="sxs-lookup"><span data-stu-id="34ce9-119">Additionally, the figure shows the nature of traffic as it changes when NAT (network address translation) occurs (destination address is changed on inbound, source address is changed on outbound).</span></span> <span data-ttu-id="34ce9-120">Пример внешнего и внутреннего брандмауэра, а также серверных интерфейсов показан только в ознакомительных целях.</span><span class="sxs-lookup"><span data-stu-id="34ce9-120">Example external and internal firewall, and server interfaces are shown for reference purposes only.</span></span> <span data-ttu-id="34ce9-121">Наконец, пример шлюза по умолчанию и отношения маршрутизации показаны, где применимо.</span><span class="sxs-lookup"><span data-stu-id="34ce9-121">Finally, example default gateway and route relationships are shown, where applicable.</span></span> <span data-ttu-id="34ce9-122">Кроме того, обратите внимание, что схема использует DNS-зону DNS для представления внешней зоны DNS как для обратного <EM>прокси-сервера</EM> , так и для пограничных серверов, а зона DNS <EM>.NET</EM> — для внутренней зоны DNS.</span><span class="sxs-lookup"><span data-stu-id="34ce9-122">Note also that the diagram uses the <EM>.com</EM> DNS zone to represent the external DNS zone for both reverse proxy and Edge Servers, and the <EM>.net</EM> DNS zone refers to the internal DNS zone.</span></span>



</div>

<span data-ttu-id="34ce9-123">Новые возможности Microsoft Lync Server 2013 поддерживают адресацию IPv6.</span><span class="sxs-lookup"><span data-stu-id="34ce9-123">New to Microsoft Lync Server 2013 is support for IPv6 addressing.</span></span> <span data-ttu-id="34ce9-124">Подобно назначению адресов IPv4, адреса IPv6 должны назначаться таким образом, чтобы они были частью назначенного адресного пространства IPv6.</span><span class="sxs-lookup"><span data-stu-id="34ce9-124">Much like IPv4 addressing, IPv6 addresses must be assigned in such a way that the addresses are part of your assigned IPv6 address space.</span></span> <span data-ttu-id="34ce9-125">Адреса в этом разделе приводятся только для примера.</span><span class="sxs-lookup"><span data-stu-id="34ce9-125">The addresses in this topic are for example only.</span></span> <span data-ttu-id="34ce9-126">Необходимо приобрести адреса IPv6, которые будут функционировать в вашем развертывании, обеспечивая правильную область, и взаимодействовать с внутренним и внешним назначением адресов.</span><span class="sxs-lookup"><span data-stu-id="34ce9-126">You must acquire IPv6 addresses that will function in your deployment, provide the correct scope and will interoperate with internal and external addressing.</span></span> <span data-ttu-id="34ce9-127">Windows Server предоставляет функцию, важную для переходных IPv6-операций и подключения IPv4 к IPv6, которые называются *двойным стеком*.</span><span class="sxs-lookup"><span data-stu-id="34ce9-127">Windows Server provides a feature that is important to transitional IPv6 operation and IPv4 to IPv6 communication called the *dual stack*.</span></span> <span data-ttu-id="34ce9-128">Двойной стек — это отдельный и отличный сетевой стек для IPv4 и для IPv6.</span><span class="sxs-lookup"><span data-stu-id="34ce9-128">The dual stack is a separate and distinct network stack for IPv4 and for IPv6.</span></span> <span data-ttu-id="34ce9-129">Двойной стек позволяет назначать адреса для IPv4 и IPv6 одновременно, и позволяет серверу взаимодействовать с другими узлами и клиентами на основе их требований.</span><span class="sxs-lookup"><span data-stu-id="34ce9-129">The dual stack is what allows you to assign addressing for IPv4 and IPv6 concurrently, and allows the server to communicate with other hosts and clients based on what their requirements are.</span></span>

<span data-ttu-id="34ce9-130">Типичные типы адресов, которые будут использоваться для адресации IPv6, будут являться глобальными IPv6-адресами (аналогично общедоступными адресами IPv4), уникальными локальными адресами IPv6 (аналогичными диапазонам частных IPv4-адресов) и IPv6-адресам локальной связи (аналогично автоматическим частным IP-адресам в Windows Server для IPv4).</span><span class="sxs-lookup"><span data-stu-id="34ce9-130">Typical address types that you will use for IPv6 addressing will be the IPv6 global addresses (similar to public IPv4 addresses), IPv6 unique local addresses (similar to the private IPv4 address ranges) and IPv6 link-local addresses (similar to automatic private IP addresses in Windows Server for IPv4)</span></span>

<span data-ttu-id="34ce9-131">Существуют технологии преобразования сетевых адресов (NAT) для IPv6, которые позволяют NAT IPv6 в IPv4 (обычно называемое NAT64) и NAT IPv6 в IPv6 (обычно называемое NAT66).</span><span class="sxs-lookup"><span data-stu-id="34ce9-131">Network address translation technologies (NAT) for IPv6 exist that will allow for NAT IPv6 to IPv4 (commonly referred to as NAT64) and for NAT IPv6 to IPv6 (commonly referred to as NAT66).</span></span> <span data-ttu-id="34ce9-132">Наличие технологий преобразования сетевых адресов означает, что пять сценариев, представленных для пограничных серверов Lync Server, остаются действительными.</span><span class="sxs-lookup"><span data-stu-id="34ce9-132">The existence of NAT technologies means that the five scenarios presented for Lync Server Edge Servers are still valid.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="34ce9-133">IPv6 — это сложная тема, которая требует тщательного планирования с вашей командой сети и поставщиком услуг Интернета, чтобы убедиться, что адреса, назначенные на уровне Windows Server и на сервере Lync Server 2013, будут работать должным образом.</span><span class="sxs-lookup"><span data-stu-id="34ce9-133">IPv6 is a complex topic and requires careful planning with your networking team and your Internet provider to ensure that the addresses you assign at the Windows server level and at the Lync Server 2013 level will work as expected.</span></span> <span data-ttu-id="34ce9-134">Для получения доступа к дополнительным ресурсам, содержащим информацию о планировании и адресации IPv6, воспользуйтесь ссылками, приведенными в конце этого раздела.</span><span class="sxs-lookup"><span data-stu-id="34ce9-134">See the links at the end of this topic for additional resources on IPv6 addressing and planning.</span></span>



</div>

<span data-ttu-id="34ce9-135">**Топология единой и консолидированной среды пограничных серверов с общедоступными IP-адресами**</span><span class="sxs-lookup"><span data-stu-id="34ce9-135">**Single Consolidated Edge with Public IP Addresses topology**</span></span>

<span data-ttu-id="34ce9-136">![2db9f9e1-75aa-4de0-ab3f-c6effddb4f4d](images/JJ205148.2db9f9e1-75aa-4de0-ab3f-c6effddb4f4d(OCS.15).jpg "2db9f9e1-75aa-4de0-ab3f-c6effddb4f4d")</span><span class="sxs-lookup"><span data-stu-id="34ce9-136">![2db9f9e1-75aa-4de0-ab3f-c6effddb4f4d](images/JJ205148.2db9f9e1-75aa-4de0-ab3f-c6effddb4f4d(OCS.15).jpg "2db9f9e1-75aa-4de0-ab3f-c6effddb4f4d")</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="34ce9-137">Если вы используете контроль допуска звонков (CAC), по-прежнему необходимо назначить IPv4-адреса внутреннему интерфейсу пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="34ce9-137">If you are using Call Admission Control (CAC), you still must assign IPv4 addresses to the Edge Server internal interface.</span></span> <span data-ttu-id="34ce9-138">CAC использует адреса IPv4, и для его работы эти адреса должны быть доступны.</span><span class="sxs-lookup"><span data-stu-id="34ce9-138">CAC uses IPv4 addresses and must have them available to operate.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="34ce9-139">Содержание</span><span class="sxs-lookup"><span data-stu-id="34ce9-139">In This Section</span></span>

  - [<span data-ttu-id="34ce9-140">Сводка по сертификатам — единая Объединенная пограничная с общедоступными IP-адресами в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="34ce9-140">Certificate summary - Single consolidated edge with public IP addresses in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-single-consolidated-edge-with-public-ip-addresses.md)

  - [<span data-ttu-id="34ce9-141">Сводка по портам — единая Объединенная пограничная с общедоступными IP-адресами в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="34ce9-141">Port summary - Single consolidated edge with public IP addresses in Lync Server 2013</span></span>](lync-server-2013-port-summary-single-consolidated-edge-with-public-ip-addresses.md)

  - [<span data-ttu-id="34ce9-142">Сводка по DNS — единая консолидированная пограничная с общедоступными IP-адресами в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="34ce9-142">DNS summary - Single consolidated edge with public IP addresses in Lync Server 2013</span></span>](lync-server-2013-dns-summary-single-consolidated-edge-with-public-ip-addresses.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="34ce9-143">См. также</span><span class="sxs-lookup"><span data-stu-id="34ce9-143">See Also</span></span>


[<span data-ttu-id="34ce9-144">Архитектура адресации протокола IP версии 6</span><span class="sxs-lookup"><span data-stu-id="34ce9-144">IP Version 6 Addressing Architecture</span></span>](https://tools.ietf.org/html/rfc4291)  
[<span data-ttu-id="34ce9-145">Глобальный одноадресный формат IPv6</span><span class="sxs-lookup"><span data-stu-id="34ce9-145">IPv6 Global Unicast Address Format</span></span>](https://tools.ietf.org/html/rfc3587)  
[<span data-ttu-id="34ce9-146">Уникальные локальные адреса одноадресной рассылки IPv6</span><span class="sxs-lookup"><span data-stu-id="34ce9-146">Unique Local IPv6 Unicast Addresses</span></span>](https://tools.ietf.org/html/rfc4193)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

