---
title: 'Lync Server 2013: единый консолидированный край с частными IP-адресами и NAT'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Single consolidated edge with private IP addresses and NAT
ms:assetid: e1e5189e-f17d-45e9-b177-e0e6f97f8951
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399001(v=OCS.15)
ms:contentKeyID: 48185691
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 60beb67ec6d2aca79210f06b9a4dabe8370649cb
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42142735"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="single-consolidated-edge-with-private-ip-addresses-and-nat-in-lync-server-2013"></a><span data-ttu-id="46c2d-102">Единый консолидированный край с частными IP-адресами и NAT в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="46c2d-102">Single consolidated edge with private IP addresses and NAT in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="46c2d-103">_**Последнее изменение темы:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="46c2d-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="46c2d-104">Если организации требуется поддержка менее 15 000 подключений клиентов пограничного сервера доступа, 1 000 активных веб-конференций Lync Server и 500 одновременные пограничные сеансы аудио-и видеоданных, а также высокая доступность пограничного сервера не важна, то эта топология обеспечивает преимущества снижения стоимости оборудования и упрощения развертывания.</span><span class="sxs-lookup"><span data-stu-id="46c2d-104">If your organization requires support for fewer than 15,000 Access Edge service client connections, 1,000 active Lync Server Web Conferencing service client connections, and 500 concurrent A/V Edge sessions, and high availability of the Edge Server is not important, this topology offers the advantages of lower hardware cost and simpler deployment.</span></span> <span data-ttu-id="46c2d-105">If you need greater capacity or you require high availability, you need to deploy a scaled consolidated Edge Server topology.</span><span class="sxs-lookup"><span data-stu-id="46c2d-105">If you need greater capacity or you require high availability, you need to deploy a scaled consolidated Edge Server topology.</span></span> <span data-ttu-id="46c2d-106">For details, see one of the following:</span><span class="sxs-lookup"><span data-stu-id="46c2d-106">For details, see one of the following:</span></span>

  - <span></span>  
    [<span data-ttu-id="46c2d-107">Масштабируемый консолидированный край, балансировка нагрузки на DNS с частными IP-адресами, использующими NAT, в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="46c2d-107">Scaled consolidated edge, DNS load balancing with private IP addresses using NAT in Lync Server 2013</span></span>](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md)

  - <span></span>  
    [<span data-ttu-id="46c2d-108">Масштабируемый консолидированный край, балансировка нагрузки на DNS с общедоступными IP-адресами в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="46c2d-108">Scaled consolidated edge, DNS load balancing with public IP addresses in Lync Server 2013</span></span>](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md)

  - <span></span>  
    [<span data-ttu-id="46c2d-109">Масштабируемая консолидированная пограничная система с аппаратными подсистемами балансировки нагрузки в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="46c2d-109">Scaled consolidated edge with hardware load balancers in Lync Server 2013</span></span>](lync-server-2013-scaled-consolidated-edge-with-hardware-load-balancers.md)

<span data-ttu-id="46c2d-110">На рисунке не показаны директора, необязательная роль сервера, развернутая во внутренней сети между пограничными серверами и интерфейсными пулами или сервером.</span><span class="sxs-lookup"><span data-stu-id="46c2d-110">The figure does not show Directors, an optional server role deployed in the internal network between the Edge Servers and your Front End pools or server.</span></span> <span data-ttu-id="46c2d-111">Сведения о топологии для директоров можно найти [в статье компоненты, необходимые для директора в Lync Server 2013](lync-server-2013-components-required-for-the-director.md).</span><span class="sxs-lookup"><span data-stu-id="46c2d-111">For details about the topology for Directors, see [Components required for the Director in Lync Server 2013](lync-server-2013-components-required-for-the-director.md).</span></span> <span data-ttu-id="46c2d-112">На рисунке показан один обратный прокси-сервер.</span><span class="sxs-lookup"><span data-stu-id="46c2d-112">The figure represents a single reverse proxy.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="46c2d-113">Показанный рисунок предназначен для общего ознакомления и примера IP-адресации, но не является репрезентацией действительных коммуникационных потоков с точным входящим и исходящим трафиком.</span><span class="sxs-lookup"><span data-stu-id="46c2d-113">The figure shown is for orientation and example IP addressing, but does not intend to represent actual communication flows with the correct incoming and outgoing traffic.</span></span> <span data-ttu-id="46c2d-114">Рисунок дает высокоуровневое представление о возможном трафике.</span><span class="sxs-lookup"><span data-stu-id="46c2d-114">The figure represents a high level view of possible traffic.</span></span> <span data-ttu-id="46c2d-115">Сведения о потоках трафика, относящихся к входящим данным (прослушивание портов) и исходящим данным (к конечным серверам или клиентам), представлены на диаграммах "Сводка по портам" в каждом сценарии.</span><span class="sxs-lookup"><span data-stu-id="46c2d-115">Details for traffic flow as they pertain to incoming (to listening ports) and outgoing (to destination servers or clients) is represented in the Port Summary diagram in each scenario.</span></span> <span data-ttu-id="46c2d-116">Например, TCP 443 является только входящим портом (для пограничного или обратного прокси-сервера) и является только двухсторонним потоком с перспективы протокола (TCP).</span><span class="sxs-lookup"><span data-stu-id="46c2d-116">For example, TCP 443 is actually inbound (to the Edge or reverse proxy) only, and is only a two-way flow from a protocol (TCP) perspective.</span></span> <span data-ttu-id="46c2d-117">Кроме того, на рисунке показан характер трафика после применения преобразования сетевых адресов (NAT) (конечный адрес изменяется на входящий, исходный адрес изменяется на исходящий).</span><span class="sxs-lookup"><span data-stu-id="46c2d-117">Additionally, the figure shows the nature of traffic as it changes when NAT (network address translation) occurs (destination address is changed on inbound, source address is changed on outbound).</span></span> <span data-ttu-id="46c2d-118">Пример внешнего и внутреннего брандмауэра, а также серверных интерфейсов показан только в ознакомительных целях.</span><span class="sxs-lookup"><span data-stu-id="46c2d-118">Example external and internal firewall, and server interfaces are shown for reference purposes only.</span></span> <span data-ttu-id="46c2d-119">Наконец, пример шлюза по умолчанию и отношения маршрутизации показаны, где применимо.</span><span class="sxs-lookup"><span data-stu-id="46c2d-119">Finally, example default gateway and route relationships are shown, where applicable.</span></span> <span data-ttu-id="46c2d-120">Кроме того, обратите внимание, что схема использует DNS-зону DNS для представления внешней зоны DNS как для обратного <EM>прокси-сервера</EM> , так и для пограничных серверов, а зона DNS <EM>.NET</EM> — для внутренней зоны DNS.</span><span class="sxs-lookup"><span data-stu-id="46c2d-120">Note also that the diagram uses the <EM>.com</EM> DNS zone to represent the external DNS zone for both reverse proxy and Edge Servers, and the <EM>.net</EM> DNS zone refers to the internal DNS zone.</span></span>



</div>

<span data-ttu-id="46c2d-121">Новые возможности Microsoft Lync Server 2013 поддерживают адресацию IPv6.</span><span class="sxs-lookup"><span data-stu-id="46c2d-121">New to Microsoft Lync Server 2013 is support for IPv6 addressing.</span></span> <span data-ttu-id="46c2d-122">Подобно назначению адресов IPv4, адреса IPv6 должны назначаться таким образом, чтобы они были частью назначенного адресного пространства IPv6.</span><span class="sxs-lookup"><span data-stu-id="46c2d-122">Much like IPv4 addressing, IPv6 addresses must be assigned in such a way that the addresses are part of your assigned IPv6 address space.</span></span> <span data-ttu-id="46c2d-123">Адреса в этом разделе приводятся только для примера.</span><span class="sxs-lookup"><span data-stu-id="46c2d-123">The addresses in this topic are for example only.</span></span> <span data-ttu-id="46c2d-124">Необходимо приобрести адреса IPv6, которые будут функционировать в вашем развертывании, обеспечивая правильную область, и взаимодействовать с внутренним и внешним назначением адресов.</span><span class="sxs-lookup"><span data-stu-id="46c2d-124">You must acquire IPv6 addresses that will function in your deployment, provide the correct scope and will interoperate with internal and external addressing.</span></span> <span data-ttu-id="46c2d-125">Windows Server предоставляет функцию, важную для переходных IPv6-операций и подключения IPv4 к IPv6, которые называются *двойным стеком*.</span><span class="sxs-lookup"><span data-stu-id="46c2d-125">Windows Server provides a feature that is important to transitional IPv6 operation and IPv4 to IPv6 communication called the *dual stack*.</span></span> <span data-ttu-id="46c2d-126">Двойной стек — это отдельный и отличный сетевой стек для IPv4 и для IPv6.</span><span class="sxs-lookup"><span data-stu-id="46c2d-126">The dual stack is a separate and distinct network stack for IPv4 and for IPv6.</span></span> <span data-ttu-id="46c2d-127">Двойной стек позволяет назначать адреса для IPv4 и IPv6 одновременно, и позволяет серверу взаимодействовать с другими узлами и клиентами на основе их требований.</span><span class="sxs-lookup"><span data-stu-id="46c2d-127">The dual stack is what allows you to assign addressing for IPv4 and IPv6 concurrently, and allows the server to communicate with other hosts and clients based on what their requirements are.</span></span>

<span data-ttu-id="46c2d-128">Типичные типы адресов, которые будут использоваться для адресации IPv6, будут являться глобальными IPv6-адресами (аналогично общедоступными адресами IPv4), уникальными локальными адресами IPv6 (аналогичными диапазонам частных IPv4-адресов) и локальными адресами IPv6-канала (как и автоматический частный IP-адрес адреса в Windows Server для IPv4)</span><span class="sxs-lookup"><span data-stu-id="46c2d-128">Typical address types that you will use for IPv6 addressing will be the IPv6 global addresses (similar to public IPv4 addresses), IPv6 unique local addresses (similar to the private IPv4 address ranges) and IPv6 link-local addresses (similar to automatic private IP addresses in Windows Server for IPv4)</span></span>

<span data-ttu-id="46c2d-129">Существуют технологии преобразования сетевых адресов (NAT) для IPv6, которые позволяют NAT IPv6 в IPv4 (обычно называемое NAT64) и NAT IPv6 в IPv6 (обычно называемое NAT66).</span><span class="sxs-lookup"><span data-stu-id="46c2d-129">Network address translation technologies (NAT) for IPv6 exist that will allow for NAT IPv6 to IPv4 (commonly referred to as NAT64) and for NAT IPv6 to IPv6 (commonly referred to as NAT66).</span></span> <span data-ttu-id="46c2d-130">Наличие технологий преобразования сетевых адресов означает, что пять сценариев, представленных для пограничных серверов Lync Server, остаются действительными.</span><span class="sxs-lookup"><span data-stu-id="46c2d-130">The existence of NAT technologies means that the five scenarios presented for Lync Server Edge Servers are still valid.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="46c2d-131">IPv6 — это сложная тема, которая требует тщательного планирования с вашей командой сети и поставщиком услуг Интернета, чтобы убедиться, что адреса, назначенные на уровне Windows Server и на сервере Lync Server 2013, будут работать должным образом.</span><span class="sxs-lookup"><span data-stu-id="46c2d-131">IPv6 is a complex topic and requires careful planning with your networking team and your Internet provider to ensure that the addresses you assign at the Windows server level and at the Lync Server 2013 level will work as expected.</span></span> <span data-ttu-id="46c2d-132">Для получения доступа к дополнительным ресурсам, содержащим информацию о планировании и адресации IPv6, воспользуйтесь ссылками, приведенными в конце этого раздела.</span><span class="sxs-lookup"><span data-stu-id="46c2d-132">See the links at the end of this topic for additional resources on IPv6 addressing and planning.</span></span>



</div>

<span data-ttu-id="46c2d-133">**Single consolidated edge topology**</span><span class="sxs-lookup"><span data-stu-id="46c2d-133">**Single consolidated edge topology**</span></span>

<span data-ttu-id="46c2d-134">![d9b889c1-587c-4732-9b68-841186ccff78](images/Gg399001.d9b889c1-587c-4732-9b68-841186ccff78(OCS.15).jpg "d9b889c1-587c-4732-9b68-841186ccff78")</span><span class="sxs-lookup"><span data-stu-id="46c2d-134">![d9b889c1-587c-4732-9b68-841186ccff78](images/Gg399001.d9b889c1-587c-4732-9b68-841186ccff78(OCS.15).jpg "d9b889c1-587c-4732-9b68-841186ccff78")</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="46c2d-135">Если вы используете контроль допуска звонков (CAC), по-прежнему необходимо назначить IPv4-адреса внутреннему интерфейсу пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="46c2d-135">If you are using Call Admission Control (CAC), you still must assign IPv4 addresses to the Edge Server internal interface.</span></span> <span data-ttu-id="46c2d-136">CAC использует адреса IPv4, и для его работы эти адреса должны быть доступны.</span><span class="sxs-lookup"><span data-stu-id="46c2d-136">CAC uses IPv4 addresses and must have them available to operate.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="46c2d-137">Содержание</span><span class="sxs-lookup"><span data-stu-id="46c2d-137">In This Section</span></span>

  - [<span data-ttu-id="46c2d-138">Сводка по сертификатам — единая консолидированная пограничная с частными IP-адресами с использованием NAT в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="46c2d-138">Certificate summary - Single consolidated edge with private IP addresses using NAT in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-single-consolidated-edge-with-private-ip-addresses-using-nat.md)

  - [<span data-ttu-id="46c2d-139">Сводка по портам — единый консолидированный край с частными IP-адресами, использующими NAT в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="46c2d-139">Port summary - Single consolidated edge with private IP addresses using NAT in Lync Server 2013</span></span>](lync-server-2013-port-summary-single-consolidated-edge-with-private-ip-addresses-using-nat.md)

  - [<span data-ttu-id="46c2d-140">Сводка по DNS — единый консолидированный край с частными IP-адресами, использующими NAT в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="46c2d-140">DNS summary - Single consolidated edge with private IP addresses using NAT in Lync Server 2013</span></span>](lync-server-2013-dns-summary-single-consolidated-edge-with-private-ip-addresses-using-nat.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="46c2d-141">См. также</span><span class="sxs-lookup"><span data-stu-id="46c2d-141">See Also</span></span>


[<span data-ttu-id="46c2d-142">Архитектура адресации протокола IP версии 6</span><span class="sxs-lookup"><span data-stu-id="46c2d-142">IP Version 6 Addressing Architecture</span></span>](https://tools.ietf.org/html/rfc4291)  
[<span data-ttu-id="46c2d-143">Глобальный одноадресный формат IPv6</span><span class="sxs-lookup"><span data-stu-id="46c2d-143">IPv6 Global Unicast Address Format</span></span>](https://tools.ietf.org/html/rfc3587)  
[<span data-ttu-id="46c2d-144">Уникальные локальные адреса одноадресной рассылки IPv6</span><span class="sxs-lookup"><span data-stu-id="46c2d-144">Unique Local IPv6 Unicast Addresses</span></span>](https://tools.ietf.org/html/rfc4193)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

