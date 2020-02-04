---
title: 'Lync Server 2013: сводка по портам — vасштабируемый пул директоров, аппаратный балансировщик нагрузки'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Port summary - Scaled Director pool, hardware load balancer
ms:assetid: 6ae2f4ac-5b64-4e45-8253-133308f5812d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204983(v=OCS.15)
ms:contentKeyID: 48184434
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fdf054ee603f2c0917e35bdd2f19d108094c7c78
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41747509"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="port-summary---scaled-director-pool-hardware-load-balancer-in-lync-server-2013"></a><span data-ttu-id="33d2e-102">Сводка по портам — vасштабируемый пул директоров, аппаратный балансировщик нагрузки в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="33d2e-102">Port summary - Scaled Director pool, hardware load balancer in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="33d2e-103">_**Тема последнего изменения:** 2012-10-21_</span><span class="sxs-lookup"><span data-stu-id="33d2e-103">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="33d2e-104">Требования к порту межсетевого экрана для пула режиссера состоят из портов, используемых для установления связи с режиссером из внутреннего интерфейса пограничного сервера или внутреннего интерфейса обратного прокси-сервера.</span><span class="sxs-lookup"><span data-stu-id="33d2e-104">Firewall port requirements for a Director pool consist of the ports that are used to establish communication with the Director from the internal interface of the Edge Server or internal-facing interface of the reverse proxy.</span></span> <span data-ttu-id="33d2e-105">По умолчанию Microsoft Lync Server 2013 ожидает, что порты HTTP/TCP 8080 и HTTPS/TCP 4443 будут открыты из обратного прокси-сервера в директор, а также с интерфейсом пула и сервера переднего плана.</span><span class="sxs-lookup"><span data-stu-id="33d2e-105">Microsoft Lync Server 2013 by default expects ports HTTP/TCP 8080 and HTTPS/TCP 4443 to be open from the reverse proxy to the Director, as well as the Front End pool and Front End Server.</span></span> <span data-ttu-id="33d2e-106">Кроме того, между внутренним интерфейсом пограничного сервера и пулом, а также интерфейсом сервера и переднего плана должен быть установлен протокол SIP.</span><span class="sxs-lookup"><span data-stu-id="33d2e-106">Additionally, there must be session initiation protocol (SIP) communication from the Edge Server internal interface to the Director and to the Front End pool and Front End Server.</span></span> <span data-ttu-id="33d2e-107">Протокол SIP использует интерфейс SIP/MTLS/TCP 5061 с пограничного сервера до пула переднего плана и сервера переднего плана.</span><span class="sxs-lookup"><span data-stu-id="33d2e-107">The SIP protocol uses SIP/MTLS/TCP 5061 from the Edge Server to the Front End pool and Front End Server.</span></span> <span data-ttu-id="33d2e-108">Кроме того, необходимо также создать правило, которое позволяет использовать интерфейс SIP/MTLS/TCP 5061, входящий в состав внешнего интерфейса пограничного сервера и сервера переднего плана.</span><span class="sxs-lookup"><span data-stu-id="33d2e-108">A rule that allows SIP/MTLS/TCP 5061 communication from the Director, Front End pool and Front End Server to the Edge Server internal interface must be created as well.</span></span>

### <a name="director-ports-and-protocols-for-firewall-definitions"></a><span data-ttu-id="33d2e-109">Сетевые порты и протоколы для определений брандмауэра</span><span class="sxs-lookup"><span data-stu-id="33d2e-109">Director Ports and Protocols for Firewall Definitions</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="33d2e-110">Role/Protocol/TCP/UDP/порт</span><span class="sxs-lookup"><span data-stu-id="33d2e-110">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="33d2e-111">IP-адрес источника</span><span class="sxs-lookup"><span data-stu-id="33d2e-111">Source IP address</span></span></th>
<th><span data-ttu-id="33d2e-112">IP-адрес назначения</span><span class="sxs-lookup"><span data-stu-id="33d2e-112">Destination IP address</span></span></th>
<th><span data-ttu-id="33d2e-113">Примечания.</span><span class="sxs-lookup"><span data-stu-id="33d2e-113">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="33d2e-114">HTTP/TCP 8080</span><span class="sxs-lookup"><span data-stu-id="33d2e-114">HTTP/TCP 8080</span></span></p></td>
<td><p><span data-ttu-id="33d2e-115">Внутренний прокси-интерфейс обратной стороне</span><span class="sxs-lookup"><span data-stu-id="33d2e-115">Reverse proxy internal interface</span></span></p></td>
<td><p><span data-ttu-id="33d2e-116">IP-адрес подсистемы балансировки нагрузки для режиссера</span><span class="sxs-lookup"><span data-stu-id="33d2e-116">Director Hardware Load Balancer VIP</span></span></p></td>
<td><p><span data-ttu-id="33d2e-117">По умолчанию получил внешняя сторона обратного прокси-сервера, связь передается в каталог ХЛБ VIP и на сервер переднего плана.</span><span class="sxs-lookup"><span data-stu-id="33d2e-117">Initially received by the external side of the reverse proxy, the communication is sent on to the Director HLB VIP and Front End Servers web services</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="33d2e-118">HTTPS/TCP 4443</span><span class="sxs-lookup"><span data-stu-id="33d2e-118">HTTPS/TCP 4443</span></span></p></td>
<td><p><span data-ttu-id="33d2e-119">Внутренний прокси-интерфейс обратной стороне</span><span class="sxs-lookup"><span data-stu-id="33d2e-119">Reverse proxy internal interface</span></span></p></td>
<td><p><span data-ttu-id="33d2e-120">IP-адрес подсистемы балансировки нагрузки для режиссера</span><span class="sxs-lookup"><span data-stu-id="33d2e-120">Director Hardware Load Balancer VIP</span></span></p></td>
<td><p><span data-ttu-id="33d2e-121">По умолчанию получил внешняя сторона обратного прокси-сервера, связь передается в каталог ХЛБ VIP и на сервер переднего плана.</span><span class="sxs-lookup"><span data-stu-id="33d2e-121">Initially received by the external side of the reverse proxy, the communication is sent on to the Director HLB VIP and Front End Servers web services</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="33d2e-122">HTTPS/TCP 444</span><span class="sxs-lookup"><span data-stu-id="33d2e-122">HTTPS/TCP 444</span></span></p></td>
<td><p><span data-ttu-id="33d2e-123">Директор</span><span class="sxs-lookup"><span data-stu-id="33d2e-123">Director</span></span></p></td>
<td><p><span data-ttu-id="33d2e-124">Пул переднего плана на сервере или внешнем интерфейсе</span><span class="sxs-lookup"><span data-stu-id="33d2e-124">Front End Server or Front End pool</span></span></p></td>
<td><p><span data-ttu-id="33d2e-125">Межсерверная связь между директором ХЛБ VIP и серверами переднего плана</span><span class="sxs-lookup"><span data-stu-id="33d2e-125">Inter-server communication between the Director HLB VIP and the Front End Servers</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="33d2e-126">HTTP/TCP 80</span><span class="sxs-lookup"><span data-stu-id="33d2e-126">HTTP/TCP 80</span></span></p></td>
<td><p><span data-ttu-id="33d2e-127">Внутренние клиенты</span><span class="sxs-lookup"><span data-stu-id="33d2e-127">Internal Clients</span></span></p></td>
<td><p><span data-ttu-id="33d2e-128">IP-адрес подсистемы балансировки нагрузки для режиссера</span><span class="sxs-lookup"><span data-stu-id="33d2e-128">Director Hardware Load Balancer VIP</span></span></p></td>
<td><p><span data-ttu-id="33d2e-129">Режиссер предоставляет веб-службы внутренним и внешним клиентам.</span><span class="sxs-lookup"><span data-stu-id="33d2e-129">The Director provides web services to internal as well as external clients.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="33d2e-130">HTTPS/TCP 443</span><span class="sxs-lookup"><span data-stu-id="33d2e-130">HTTPS/TCP 443</span></span></p></td>
<td><p><span data-ttu-id="33d2e-131">Внутренние клиенты</span><span class="sxs-lookup"><span data-stu-id="33d2e-131">Internal Clients</span></span></p></td>
<td><p><span data-ttu-id="33d2e-132">IP-адрес подсистемы балансировки нагрузки для режиссера</span><span class="sxs-lookup"><span data-stu-id="33d2e-132">Director Hardware Load Balancer VIP</span></span></p></td>
<td><p><span data-ttu-id="33d2e-133">Режиссер предоставляет веб-службы внутренним и внешним клиентам.</span><span class="sxs-lookup"><span data-stu-id="33d2e-133">The Director provides web services to internal as well as external clients.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="33d2e-134">SIP/MTLS/TCP 5061</span><span class="sxs-lookup"><span data-stu-id="33d2e-134">SIP/MTLS/TCP 5061</span></span></p></td>
<td><p><span data-ttu-id="33d2e-135">Внутренний интерфейс пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="33d2e-135">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="33d2e-136">IP-адрес подсистемы балансировки нагрузки для режиссера</span><span class="sxs-lookup"><span data-stu-id="33d2e-136">Director Hardware Load Balancer VIP</span></span></p></td>
<td><p><span data-ttu-id="33d2e-137">Обмен данными SIP от пограничного сервера к директору и к серверам переднего плана.</span><span class="sxs-lookup"><span data-stu-id="33d2e-137">SIP communication from the Edge Server to the Director, and Front End Servers.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="33d2e-138">MTLS/TCP/50001</span><span class="sxs-lookup"><span data-stu-id="33d2e-138">MTLS/TCP/50001</span></span></p></td>
<td><p><span data-ttu-id="33d2e-139">Любой</span><span class="sxs-lookup"><span data-stu-id="33d2e-139">Any</span></span></p></td>
<td><p><span data-ttu-id="33d2e-140">Директор</span><span class="sxs-lookup"><span data-stu-id="33d2e-140">Director</span></span></p></td>
<td><p><span data-ttu-id="33d2e-141">Команды для централизованного ведения журналов (Клсконтроллер. exe) или агента (Клсажент. exe) и сбора журналов</span><span class="sxs-lookup"><span data-stu-id="33d2e-141">Centralized Logging Service controller (ClsController.exe) or agent (ClsAgent.exe)commands and log collection</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="33d2e-142">MTLS/TCP/50002</span><span class="sxs-lookup"><span data-stu-id="33d2e-142">MTLS/TCP/50002</span></span></p></td>
<td><p><span data-ttu-id="33d2e-143">Любой</span><span class="sxs-lookup"><span data-stu-id="33d2e-143">Any</span></span></p></td>
<td><p><span data-ttu-id="33d2e-144">Директор</span><span class="sxs-lookup"><span data-stu-id="33d2e-144">Director</span></span></p></td>
<td><p><span data-ttu-id="33d2e-145">Команды для централизованного ведения журналов (Клсконтроллер. exe) или агента (Клсажент. exe) и сбора журналов</span><span class="sxs-lookup"><span data-stu-id="33d2e-145">Centralized Logging Service controller (ClsController.exe) or agent (ClsAgent.exe)commands and log collection</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="33d2e-146">MTLS/TCP/50003</span><span class="sxs-lookup"><span data-stu-id="33d2e-146">MTLS/TCP/50003</span></span></p></td>
<td><p><span data-ttu-id="33d2e-147">Любой</span><span class="sxs-lookup"><span data-stu-id="33d2e-147">Any</span></span></p></td>
<td><p><span data-ttu-id="33d2e-148">Директор</span><span class="sxs-lookup"><span data-stu-id="33d2e-148">Director</span></span></p></td>
<td><p><span data-ttu-id="33d2e-149">Команды для централизованного ведения журналов (Клсконтроллер. exe) или агента (Клсажент. exe) и сбора журналов</span><span class="sxs-lookup"><span data-stu-id="33d2e-149">Centralized Logging Service controller (ClsController.exe) or agent (ClsAgent.exe)commands and log collection</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

