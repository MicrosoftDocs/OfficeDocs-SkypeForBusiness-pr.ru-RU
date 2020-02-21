---
title: 'Lync Server 2013: масштабируемая консолидированная пограничная система с аппаратными подсистемами балансировки нагрузки'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Scaled consolidated edge with hardware load balancers
ms:assetid: 6783e225-9677-415a-8731-0bf2e2c4cf8b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398478(v=OCS.15)
ms:contentKeyID: 48184353
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0a961b6eabb85e135b1cfb36cf5738cbf757b547
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42201005"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="scaled-consolidated-edge-with-hardware-load-balancers-in-lync-server-2013"></a><span data-ttu-id="5e683-102">Масштабируемая консолидированная пограничная система с аппаратными подсистемами балансировки нагрузки в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5e683-102">Scaled consolidated edge with hardware load balancers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5e683-103">_**Последнее изменение темы:** 2012-10-21_</span><span class="sxs-lookup"><span data-stu-id="5e683-103">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="5e683-104">В топологии пограничного пула два или больше пограничных серверов развертываются в виде пула с балансировкой нагрузки в сети периметра центра обработки данных.</span><span class="sxs-lookup"><span data-stu-id="5e683-104">In the Edge pool topology, two or more Edge Servers are deployed as a load-balanced pool in the perimeter network of the data center.</span></span> <span data-ttu-id="5e683-105">Аппаратная балансировка нагрузки используется для трафика к внешним и внутренним интерфейсам пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="5e683-105">Hardware load balancing is used for traffic to both the external and internal Edge Server interfaces.</span></span>

<span data-ttu-id="5e683-106">Если вашей организации требуется поддержка более 15 000 подключений клиентов пограничного сервера доступа, 1 000 активных веб-конференций пограничного сервера пограничного сервера или 500 параллельные сеансы аудио-и видеосвязи, а также высокая доступность пограничного сервера, то эта топология обеспечивает преимущества масштабируемости и поддержки отработки отказа.</span><span class="sxs-lookup"><span data-stu-id="5e683-106">If your organization requires support for more than 15,000 Access Edge service client connections, 1,000 active Web Conferencing Edge service client connections, or 500 concurrent A/V Edge service sessions, and high availability of the Edge Server is important, this topology offers the advantages of scalability and failover support.</span></span>

<span data-ttu-id="5e683-107">На рисунке не показаны директора, необязательная роль сервера, развернутая во внутренней сети между пограничными серверами и интерфейсными пулами или сервером.</span><span class="sxs-lookup"><span data-stu-id="5e683-107">The figure does not show Directors, an optional server role deployed in the internal network between the Edge Servers and your Front End pools or server.</span></span> <span data-ttu-id="5e683-108">.</span><span class="sxs-lookup"><span data-stu-id="5e683-108">.</span></span> <span data-ttu-id="5e683-109">Сведения о топологии для директоров можно найти [в статье компоненты, необходимые для директора в Lync Server 2013](lync-server-2013-components-required-for-the-director.md).</span><span class="sxs-lookup"><span data-stu-id="5e683-109">For details about the topology for Directors, see [Components required for the Director in Lync Server 2013](lync-server-2013-components-required-for-the-director.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="5e683-110">Показанный рисунок предназначен для общего ознакомления и примера IP-адресации, но не является репрезентацией действительных коммуникационных потоков с точным входящим и исходящим трафиком.</span><span class="sxs-lookup"><span data-stu-id="5e683-110">The figure shown is for orientation and example IP addressing, but does not intend to represent actual communication flows with the correct incoming and outgoing traffic.</span></span> <span data-ttu-id="5e683-111">Рисунок дает высокоуровневое представление о возможном трафике.</span><span class="sxs-lookup"><span data-stu-id="5e683-111">The figure represents a high level view of possible traffic.</span></span> <span data-ttu-id="5e683-112">Сведения о потоках трафика, относящихся к входящим данным (прослушивание портов) и исходящим данным (к конечным серверам или клиентам), представлены на диаграммах "Сводка по портам" в каждом сценарии.</span><span class="sxs-lookup"><span data-stu-id="5e683-112">Details for traffic flow as they pertain to incoming (to listening ports) and outgoing (to destination servers or clients) is represented in the Port Summary diagram in each scenario.</span></span> <span data-ttu-id="5e683-113">Например, TCP 443 фактически является входящим (только для пограничного сервера или обратного прокси-сервера) и является односторонней передачей из перспективы протокола TCP.</span><span class="sxs-lookup"><span data-stu-id="5e683-113">For example, TCP 443 is actually inbound (to the Edge Server or reverse proxy) only, and is only a two-way flow from a protocol (TCP) perspective.</span></span> <span data-ttu-id="5e683-114">Кроме того, на рисунке показан характер трафика после применения преобразования сетевых адресов (NAT) (конечный адрес изменяется на входящий, исходный адрес изменяется на исходящий).</span><span class="sxs-lookup"><span data-stu-id="5e683-114">Additionally, the figure shows the nature of traffic as it changes when NAT (network address translation) occurs (destination address is changed on inbound, source address is changed on outbound).</span></span> <span data-ttu-id="5e683-115">Пример внешнего и внутреннего брандмауэра, а также серверных интерфейсов показан только в ознакомительных целях.</span><span class="sxs-lookup"><span data-stu-id="5e683-115">Example external and internal firewall, and server interfaces are shown for reference purposes only.</span></span> <span data-ttu-id="5e683-116">Наконец, пример шлюза по умолчанию и отношения маршрутизации показаны, где применимо.</span><span class="sxs-lookup"><span data-stu-id="5e683-116">Finally, example default gateway and route relationships are shown, where applicable.</span></span> <span data-ttu-id="5e683-117">Кроме того, обратите внимание, что схема использует DNS-зону DNS для представления внешней зоны DNS как для обратного <EM>прокси-сервера</EM> , так и для пограничных серверов, а зона DNS <EM>.NET</EM> — для внутренней зоны DNS.</span><span class="sxs-lookup"><span data-stu-id="5e683-117">Note also that the diagram uses the <EM>.com</EM> DNS zone to represent the external DNS zone for both reverse proxy and Edge Servers, and the <EM>.net</EM> DNS zone refers to the internal DNS zone.</span></span>



</div>

<span data-ttu-id="5e683-118">Новые возможности Microsoft Lync Server 2013 поддерживают адресацию IPv6.</span><span class="sxs-lookup"><span data-stu-id="5e683-118">New to Microsoft Lync Server 2013 is support for IPv6 addressing.</span></span> <span data-ttu-id="5e683-119">Подобно назначению адресов IPv4, адреса IPv6 должны назначаться таким образом, чтобы они были частью назначенного адресного пространства IPv6.</span><span class="sxs-lookup"><span data-stu-id="5e683-119">Much like IPv4 addressing, IPv6 addresses must be assigned in such a way that the addresses are part of your assigned IPv6 address space.</span></span> <span data-ttu-id="5e683-120">Адреса в этом разделе приводятся только для примера.</span><span class="sxs-lookup"><span data-stu-id="5e683-120">The addresses in this topic are for example only.</span></span> <span data-ttu-id="5e683-121">Необходимо приобрести адреса IPv6, которые будут функционировать в вашем развертывании, обеспечивая правильную область, и взаимодействовать с внутренним и внешним назначением адресов.</span><span class="sxs-lookup"><span data-stu-id="5e683-121">You must acquire IPv6 addresses that will function in your deployment, provide the correct scope and will interoperate with internal and external addressing.</span></span> <span data-ttu-id="5e683-122">Windows Server предоставляет функцию, важную для переходных IPv6-операций и подключения IPv4 к IPv6, которые называются *двойным стеком*.</span><span class="sxs-lookup"><span data-stu-id="5e683-122">Windows Server provides a feature that is important to transitional IPv6 operation and IPv4 to IPv6 communication called the *dual stack*.</span></span> <span data-ttu-id="5e683-123">Двойной стек — это отдельный и отличный сетевой стек для IPv4 и для IPv6.</span><span class="sxs-lookup"><span data-stu-id="5e683-123">The dual stack is a separate and distinct network stack for IPv4 and for IPv6.</span></span> <span data-ttu-id="5e683-124">Двойной стек позволяет назначать адреса для IPv4 и IPv6 одновременно, и позволяет серверу взаимодействовать с другими узлами и клиентами на основе их требований.</span><span class="sxs-lookup"><span data-stu-id="5e683-124">The dual stack is what allows you to assign addressing for IPv4 and IPv6 concurrently, and allows the server to communicate with other hosts and clients based on what their requirements are.</span></span>

<span data-ttu-id="5e683-125">Типичные типы адресов, которые будут использоваться для адресации IPv6, будут являться глобальными IPv6-адресами (аналогично общедоступными адресами IPv4), уникальными локальными адресами IPv6 (аналогичными диапазонам частных IPv4-адресов) и локальными адресами IPv6-канала (как и автоматический частный IP-адрес адреса в Windows Server для IPv4)</span><span class="sxs-lookup"><span data-stu-id="5e683-125">Typical address types that you will use for IPv6 addressing will be the IPv6 global addresses (similar to public IPv4 addresses), IPv6 unique local addresses (similar to the private IPv4 address ranges) and IPv6 link-local addresses (similar to automatic private IP addresses in Windows Server for IPv4)</span></span>

<span data-ttu-id="5e683-126">Существуют технологии преобразования сетевых адресов (NAT) для IPv6, которые позволяют NAT IPv6 в IPv4 (обычно называемое NAT64) и NAT IPv6 в IPv6 (обычно называемое NAT66).</span><span class="sxs-lookup"><span data-stu-id="5e683-126">Network address translation technologies (NAT) for IPv6 exist that will allow for NAT IPv6 to IPv4 (commonly referred to as NAT64) and for NAT IPv6 to IPv6 (commonly referred to as NAT66).</span></span> <span data-ttu-id="5e683-127">Наличие технологий преобразования сетевых адресов означает, что пять сценариев, представленных для пограничных серверов Lync Server, остаются действительными.</span><span class="sxs-lookup"><span data-stu-id="5e683-127">The existence of NAT technologies means that the five scenarios presented for Lync Server Edge Servers are still valid.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="5e683-128">IPv6 — это сложная тема, которая требует тщательного планирования с вашей командой сети и поставщиком услуг Интернета, чтобы убедиться, что адреса, назначенные на уровне Windows Server и на сервере Lync Server 2013, будут работать должным образом.</span><span class="sxs-lookup"><span data-stu-id="5e683-128">IPv6 is a complex topic and requires careful planning with your networking team and your Internet provider to ensure that the addresses you assign at the Windows server level and at the Lync Server 2013 level will work as expected.</span></span> <span data-ttu-id="5e683-129">Ознакомьтесь с приведенными в конце раздела ссылками на дополнительные ресурсы по адресации и планированию IPv6.</span><span class="sxs-lookup"><span data-stu-id="5e683-129">See the links at the end of this topic for additional resources on IPv6 addressing and planning.</span></span>



</div>

<span data-ttu-id="5e683-130">**Конфигурация аппаратного балансировщика нагрузки**</span><span class="sxs-lookup"><span data-stu-id="5e683-130">**Hardware Load Balancer Configuration**</span></span>

<span data-ttu-id="5e683-131">Дополнительные сведения можно найти в разделе "требования к аппаратному подсистеме балансировки нагрузки для A/V Edge" [компонентов, необходимых для доступа внешних пользователей в Lync Server 2013](lync-server-2013-components-required-for-external-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="5e683-131">For details, see the “Hardware Load Balancer Requirements for A/V Edge” section in [Components required for external user access in Lync Server 2013](lync-server-2013-components-required-for-external-user-access.md).</span></span>

<span data-ttu-id="5e683-132">**Масштабируемая консолидируемая пограничная топология (аппаратная балансировка нагрузки)**</span><span class="sxs-lookup"><span data-stu-id="5e683-132">**Scaled consolidated edge topology (hardware load balanced)**</span></span>

<span data-ttu-id="5e683-133">![3a57cd0d-8de4-4ecc-a783-4dff5b3456a2](images/Gg398478.3a57cd0d-8de4-4ecc-a783-4dff5b3456a2(OCS.15).jpg "3a57cd0d-8de4-4ecc-a783-4dff5b3456a2")</span><span class="sxs-lookup"><span data-stu-id="5e683-133">![3a57cd0d-8de4-4ecc-a783-4dff5b3456a2](images/Gg398478.3a57cd0d-8de4-4ecc-a783-4dff5b3456a2(OCS.15).jpg "3a57cd0d-8de4-4ecc-a783-4dff5b3456a2")</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="5e683-134">Если вы используете контроль допуска звонков (CAC), по-прежнему необходимо назначить IPv4-адреса внутреннему интерфейсу пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="5e683-134">If you are using Call Admission Control (CAC), you still must assign IPv4 addresses to the Edge Server internal interface.</span></span> <span data-ttu-id="5e683-135">CAC использует адреса IPv4, и для его работы эти адреса должны быть доступны.</span><span class="sxs-lookup"><span data-stu-id="5e683-135">CAC uses IPv4 addresses and must have them available to operate.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="5e683-136">Содержание</span><span class="sxs-lookup"><span data-stu-id="5e683-136">In This Section</span></span>

  - [<span data-ttu-id="5e683-137">Сводка по сертификатам — масштабируемая консолидированная пограничная система с аппаратными подсистемами балансировки нагрузки в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5e683-137">Certificate summary - Scaled consolidated edge with hardware load balancers in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-scaled-consolidated-edge-with-hardware-load-balancers.md)

  - [<span data-ttu-id="5e683-138">Сводка по портам — масштабируемая консолидированная пограничная система с аппаратными подсистемами балансировки нагрузки в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5e683-138">Port summary - Scaled consolidated edge with hardware load balancers in Lync Server 2013</span></span>](lync-server-2013-port-summary-scaled-consolidated-edge-with-hardware-load-balancers.md)

  - [<span data-ttu-id="5e683-139">Сводка по DNS — масштабируемая консолидированная пограничная система с аппаратными подсистемами балансировки нагрузки в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5e683-139">DNS summary - Scaled consolidated edge with hardware load balancers in Lync Server 2013</span></span>](lync-server-2013-dns-summary-scaled-consolidated-edge-with-hardware-load-balancers.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="5e683-140">См. также</span><span class="sxs-lookup"><span data-stu-id="5e683-140">See Also</span></span>


[<span data-ttu-id="5e683-141">Архитектура адресации протокола IP версии 6</span><span class="sxs-lookup"><span data-stu-id="5e683-141">IP Version 6 Addressing Architecture</span></span>](https://tools.ietf.org/html/rfc4291)  
[<span data-ttu-id="5e683-142">Глобальный одноадресный формат IPv6</span><span class="sxs-lookup"><span data-stu-id="5e683-142">IPv6 Global Unicast Address Format</span></span>](https://tools.ietf.org/html/rfc3587)  
[<span data-ttu-id="5e683-143">Уникальные локальные адреса одноадресной рассылки IPv6</span><span class="sxs-lookup"><span data-stu-id="5e683-143">Unique Local IPv6 Unicast Addresses</span></span>](https://tools.ietf.org/html/rfc4193)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

