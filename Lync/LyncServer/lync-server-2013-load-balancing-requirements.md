---
title: Требования к балансировке нагрузки для Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Load balancing requirements
ms:assetid: 84489328-64a4-486c-9384-a3e5c8ed9c8b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615011(v=OCS.15)
ms:contentKeyID: 48184697
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8081ba60d826f0f765533abdb6c0f548045a7fa8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765387"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="load-balancing-requirements-for-lync-server-2013"></a><span data-ttu-id="1421e-102">Требования балансировки нагрузки для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1421e-102">Load balancing requirements for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1421e-103">_**Тема последнего изменения:** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="1421e-103">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="1421e-104">Если у вас есть пулы, пулы или пограничные серверы, вам потребуется развернуть балансировку нагрузки для этих пулов.</span><span class="sxs-lookup"><span data-stu-id="1421e-104">If you have Front End pools, Director pools, or Edge Server pools, you need to deploy load balancing for these pools.</span></span> <span data-ttu-id="1421e-105">Load balancing distributes the traffic among the servers in a pool.</span><span class="sxs-lookup"><span data-stu-id="1421e-105">Load balancing distributes the traffic among the servers in a pool.</span></span>

<span data-ttu-id="1421e-106">Lync Server 2013 поддерживает два типа решений для балансировки нагрузки при обмене данными между клиентами: Балансировка нагрузки DNS и балансировка нагрузки оборудования.</span><span class="sxs-lookup"><span data-stu-id="1421e-106">Lync Server 2013 supports two types of load balancing solutions for client-to-server traffic: Domain Name System (DNS) load balancing and hardware load balancing.</span></span> <span data-ttu-id="1421e-107">Балансировка нагрузки DNS обеспечивает ряд преимуществ, включая упрощенное администрирование, более эффективное устранение неполадок и возможность изолировать весь трафик Lync Server от любых потенциальных проблем системы балансировки нагрузки оборудования.</span><span class="sxs-lookup"><span data-stu-id="1421e-107">DNS load balancing offers several advantages including simpler administration, more efficient troubleshooting, and the ability to isolate much of your Lync Server traffic from any potential hardware load balancer problems.</span></span>

<span data-ttu-id="1421e-108">Выберите решение балансировки нагрузки для каждого пула в развертывании, учитывая следующие ограничения:</span><span class="sxs-lookup"><span data-stu-id="1421e-108">Decide which load balancing solution is appropriate for each pool in your deployment, keeping in mind the following restrictions:</span></span>

  - <span data-ttu-id="1421e-p103">Внутренний и внешний пограничные интерфейсы должны использовать одинаковые типы решений балансировки нагрузки. Вы не можете использовать балансировку нагрузки на DNS на одном интерфейсе и аппаратную балансировку на другом.</span><span class="sxs-lookup"><span data-stu-id="1421e-p103">The internal Edge interface and external Edge interface must use the same type of load balancing. You cannot use DNS load balancing on one interface and hardware load balancing on the other.</span></span>

  - <span data-ttu-id="1421e-p104">Для некоторых типов трафика требуется аппаратный балансировщик нагрузки. Например для трафика HTTP вместо балансировки нагрузки на DNS требуется аппаратный балансировщик нагрузки. Балансировка нагрузки на DNS не работает с веб-трафиком "клиент-сервер".</span><span class="sxs-lookup"><span data-stu-id="1421e-p104">Some types of traffic require a hardware load balancer. For example, HTTP traffic requires a hardware load balancer instead of DNS load balancing. DNS load balancing does not work with client-to-server web traffic.</span></span>

<span data-ttu-id="1421e-114">Дополнительные сведения о выборе решения для аппаратной подсистемы балансировки нагрузки можно найти в разделе [требования к оборудованию балансировки нагрузки для Lync Server 2013](lync-server-2013-hardware-load-balancer-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1421e-114">For more details about choosing a hardware load balancer solution, see [Hardware load balancer requirements for Lync Server 2013](lync-server-2013-hardware-load-balancer-requirements.md).</span></span>

<span data-ttu-id="1421e-115">Если в качестве решения для пула вы выбрали балансировку нагрузки на DNS, но вам по-прежнему требуются аппаратные балансировщики нагрузки для определенных видов трафика, например HTTP, то администрирование аппаратных балансировщиков нагрузки существенно упрощается.</span><span class="sxs-lookup"><span data-stu-id="1421e-115">If you choose to use DNS load balancing for a pool but still need to implement hardware load balancers for traffic such as HTTP traffic, the administration of the hardware load balancers is greatly simplified.</span></span> <span data-ttu-id="1421e-116">Например настройка аппаратного балансировщика нагрузки будет упрощена, поскольку потребуется управлять только трафиком HTTP и HTTPS, а для управления остальными протоколами будет использоваться балансировка нагрузки на DNS.</span><span class="sxs-lookup"><span data-stu-id="1421e-116">For example, configuring the hardware load balancer will be simpler as it will only manage the HTTP and HTTPS traffic, while all other protocols will be managed by DNS load balancing.</span></span> <span data-ttu-id="1421e-117">Дополнительные сведения можно найти [в разделе Балансировка нагрузки DNS в Lync Server 2013](lync-server-2013-dns-load-balancing.md).</span><span class="sxs-lookup"><span data-stu-id="1421e-117">For details, see [DNS load balancing in Lync Server 2013](lync-server-2013-dns-load-balancing.md).</span></span>

<span data-ttu-id="1421e-118">Для трафика "сервер-сервер" в Lync Server 2013 используется балансировка нагрузки, учитывающая топологию.</span><span class="sxs-lookup"><span data-stu-id="1421e-118">For server-to-server traffic, Lync Server 2013 uses topology-aware load balancing.</span></span> <span data-ttu-id="1421e-119">Серверы считывают опубликованную топологию в хранилище Центрального управления для получения полных доменных имен серверов в топологии и автоматически распространяют трафик между серверами.</span><span class="sxs-lookup"><span data-stu-id="1421e-119">Servers read the published topology in the Central Management store to obtain the FQDNs of servers in the topology, and automatically distribute the traffic among the servers.</span></span> <span data-ttu-id="1421e-120">Administrators do not need to set up or manage this type of load balancing.</span><span class="sxs-lookup"><span data-stu-id="1421e-120">Administrators do not need to set up or manage this type of load balancing.</span></span>

<span data-ttu-id="1421e-p107">Если используется балансировка DNS-нагрузки и требуется блокировать трафик на конкретный компьютер, недостаточно просто удалить записи IP-адреса из полного имени домена пула. Необходимо также удалить DNS-запись для этого компьютера.</span><span class="sxs-lookup"><span data-stu-id="1421e-p107">If you use DNS load balancing and you need to block traffic to a specific computer, it is not sufficient to just remove the IP address entries from the Pool FQDN. You must remove the DNS entry for the computer as well.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

