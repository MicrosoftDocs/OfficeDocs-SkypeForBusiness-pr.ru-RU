---
title: 'Lync Server 2013: сводка по портам — балансировка нагрузки на DNS и HLB'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Port summary - DNS and HLB load balanced
ms:assetid: b07c37e4-820e-46ee-a678-1da95d1b87af
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205179(v=OCS.15)
ms:contentKeyID: 48185149
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3e6175f83e1cea20e21ed25c372849c0e6b80b49
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42183942"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="port-summary---dns-and-hlb-load-balanced-in-lync-server-2013"></a><span data-ttu-id="6d9cd-102">Сводка по портам — балансировка нагрузки на DNS и HLB в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6d9cd-102">Port summary - DNS and HLB load balanced in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6d9cd-103">_**Последнее изменение темы:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="6d9cd-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="6d9cd-104">Требования к портам брандмауэра для одного директора состоят из портов, которые используются для установления связи с директором от внутреннего интерфейса или внутренней сети обратного прокси-сервера.</span><span class="sxs-lookup"><span data-stu-id="6d9cd-104">Firewall port requirements for a single Director consist of the ports that are used to establish communication with the Director from the internal interface or internal-facing network of the reverse proxy.</span></span> <span data-ttu-id="6d9cd-105">По умолчанию Microsoft Lync Server 2013 ожидает, что порты HTTP/TCP 8080 и HTTPS/TCP 4443 открываются из обратного прокси-сервера в директоре, а также интерфейсный пул и сервер переднего плана.</span><span class="sxs-lookup"><span data-stu-id="6d9cd-105">Microsoft Lync Server 2013 by default expects ports HTTP/TCP 8080 and HTTPS/TCP 4443 to be open from the reverse proxy to the Director, as well as the Front End pool and Front End Server.</span></span> <span data-ttu-id="6d9cd-106">Кроме того, должен быть обмен данными по протоколу SIP от внутреннего интерфейса пограничного сервера к директоре и к интерфейсному пулу и серверу переднего плана.</span><span class="sxs-lookup"><span data-stu-id="6d9cd-106">Additionally, there must be session initiation protocol (SIP) communication from the Edge Server internal interface to the Director and to the Front End pool and Front End Server.</span></span> <span data-ttu-id="6d9cd-107">Протокол SIP использует SIP/MTLS/TCP 5061 с пограничного сервера в интерфейсный пул и сервер переднего плана.</span><span class="sxs-lookup"><span data-stu-id="6d9cd-107">The SIP protocol uses SIP/MTLS/TCP 5061 from the Edge Server to the Front End pool and Front End Server.</span></span> <span data-ttu-id="6d9cd-108">Необходимо также создать правило, разрешающее передачу данных по протоколу SIP/MTLS/TCP 5061 из директора, интерфейсного пула и сервера переднего плана в внутренний интерфейс пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="6d9cd-108">A rule that allows SIP/MTLS/TCP 5061 communication from the Director, Front End pool and Front End Server to the Edge Server internal interface must be created as well.</span></span>

### <a name="single-director-ports-and-protocols-for-firewall-definitions"></a><span data-ttu-id="6d9cd-109">Порты и протоколы единого директора для определений брандмауэра</span><span class="sxs-lookup"><span data-stu-id="6d9cd-109">Single Director Ports and Protocols for Firewall Definitions</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6d9cd-110">Роль/протокол/TCP или UDP/порт</span><span class="sxs-lookup"><span data-stu-id="6d9cd-110">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="6d9cd-111">Исходный IP-адрес</span><span class="sxs-lookup"><span data-stu-id="6d9cd-111">Source IP address</span></span></th>
<th><span data-ttu-id="6d9cd-112">Конечный IP-адрес</span><span class="sxs-lookup"><span data-stu-id="6d9cd-112">Destination IP address</span></span></th>
<th><span data-ttu-id="6d9cd-113">Notes</span><span class="sxs-lookup"><span data-stu-id="6d9cd-113">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6d9cd-114">HTTP/TCP 8080</span><span class="sxs-lookup"><span data-stu-id="6d9cd-114">HTTP/TCP 8080</span></span></p></td>
<td><p><span data-ttu-id="6d9cd-115">Внутренний интерфейс обратного прокси-сервера</span><span class="sxs-lookup"><span data-stu-id="6d9cd-115">Reverse proxy internal interface</span></span></p></td>
<td><p><span data-ttu-id="6d9cd-116">Виртуальный IP-адрес подсистемы балансировки нагрузки для директоров</span><span class="sxs-lookup"><span data-stu-id="6d9cd-116">Director Hardware Load Balancer VIP</span></span></p></td>
<td><p><span data-ttu-id="6d9cd-117">По умолчанию полученная внешняя сторона обратного прокси-сервера передается на директор HLB VIP и веб-службы сервера переднего плана.</span><span class="sxs-lookup"><span data-stu-id="6d9cd-117">Initially received by the external side of the reverse proxy, the communication is sent on to the Director HLB VIP and Front End Server web services.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6d9cd-118">HTTPS/TCP 4443</span><span class="sxs-lookup"><span data-stu-id="6d9cd-118">HTTPS/TCP 4443</span></span></p></td>
<td><p><span data-ttu-id="6d9cd-119">Внутренний интерфейс обратного прокси-сервера</span><span class="sxs-lookup"><span data-stu-id="6d9cd-119">Reverse proxy internal interface</span></span></p></td>
<td><p><span data-ttu-id="6d9cd-120">Виртуальный IP-адрес подсистемы балансировки нагрузки для директоров</span><span class="sxs-lookup"><span data-stu-id="6d9cd-120">Director Hardware Load Balancer VIP</span></span></p></td>
<td><p><span data-ttu-id="6d9cd-121">По умолчанию полученная внешняя сторона обратного прокси-сервера передается на директор HLB VIP и веб-службы сервера переднего плана.</span><span class="sxs-lookup"><span data-stu-id="6d9cd-121">Initially received by the external side of the reverse proxy, the communication is sent on to the Director HLB VIP and Front End Server web services.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6d9cd-122">HTTPS/TCP 444</span><span class="sxs-lookup"><span data-stu-id="6d9cd-122">HTTPS/TCP 444</span></span></p></td>
<td><p><span data-ttu-id="6d9cd-123">Режиссер</span><span class="sxs-lookup"><span data-stu-id="6d9cd-123">Director</span></span></p></td>
<td><p><span data-ttu-id="6d9cd-124">Интерфейсный пул или сервер переднего плана</span><span class="sxs-lookup"><span data-stu-id="6d9cd-124">Front End pool or Front End Server</span></span></p></td>
<td><p><span data-ttu-id="6d9cd-125">Обмен данными между сервером HLB и сервером переднего плана и серверами переднего плана и серверами переднего плана.</span><span class="sxs-lookup"><span data-stu-id="6d9cd-125">Inter-server communication between the Director HLB VIP and the Front End Server or Front End Servers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6d9cd-126">HTTP/TCP 80</span><span class="sxs-lookup"><span data-stu-id="6d9cd-126">HTTP/TCP 80</span></span></p></td>
<td><p><span data-ttu-id="6d9cd-127">Внутренние клиенты</span><span class="sxs-lookup"><span data-stu-id="6d9cd-127">Internal Clients</span></span></p></td>
<td><p><span data-ttu-id="6d9cd-128">Виртуальный IP-адрес подсистемы балансировки нагрузки для директоров</span><span class="sxs-lookup"><span data-stu-id="6d9cd-128">Director Hardware Load Balancer VIP</span></span></p></td>
<td><p><span data-ttu-id="6d9cd-129">Директор предоставляет веб-службы внутренним и внешним клиентам.</span><span class="sxs-lookup"><span data-stu-id="6d9cd-129">The Director provides web services to internal as well as external clients.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6d9cd-130">HTTPS/TCP 443</span><span class="sxs-lookup"><span data-stu-id="6d9cd-130">HTTPS/TCP 443</span></span></p></td>
<td><p><span data-ttu-id="6d9cd-131">Внутренние клиенты</span><span class="sxs-lookup"><span data-stu-id="6d9cd-131">Internal Clients</span></span></p></td>
<td><p><span data-ttu-id="6d9cd-132">Виртуальный IP-адрес подсистемы балансировки нагрузки для директоров</span><span class="sxs-lookup"><span data-stu-id="6d9cd-132">Director Hardware Load Balancer VIP</span></span></p></td>
<td><p><span data-ttu-id="6d9cd-133">Директор предоставляет веб-службы внутренним и внешним клиентам.</span><span class="sxs-lookup"><span data-stu-id="6d9cd-133">The Director provides web services to internal as well as external clients.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6d9cd-134">SIP/MTLS/TCP 5061</span><span class="sxs-lookup"><span data-stu-id="6d9cd-134">SIP/MTLS/TCP 5061</span></span></p></td>
<td><p><span data-ttu-id="6d9cd-135">Внутренний интерфейс пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="6d9cd-135">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="6d9cd-136">Режиссер</span><span class="sxs-lookup"><span data-stu-id="6d9cd-136">Director</span></span></p></td>
<td><p><span data-ttu-id="6d9cd-137">Обмен данными SIP от пограничного сервера к директоре, а также к серверам переднего плана.</span><span class="sxs-lookup"><span data-stu-id="6d9cd-137">SIP communication from the Edge Server to the Director, as well as the Front End Servers.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6d9cd-138">MTLS/TCP/50001</span><span class="sxs-lookup"><span data-stu-id="6d9cd-138">MTLS/TCP/50001</span></span></p></td>
<td><p><span data-ttu-id="6d9cd-139">Любые</span><span class="sxs-lookup"><span data-stu-id="6d9cd-139">Any</span></span></p></td>
<td><p><span data-ttu-id="6d9cd-140">Режиссер</span><span class="sxs-lookup"><span data-stu-id="6d9cd-140">Director</span></span></p></td>
<td><p><span data-ttu-id="6d9cd-141">Команды и коллекция журналов для централизованного ведения журналов (ClsController. exe) или агента (ClsAgent. exe)</span><span class="sxs-lookup"><span data-stu-id="6d9cd-141">Centralized Logging Service controller (ClsController.exe) or agent (ClsAgent.exe)commands and log collection</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6d9cd-142">MTLS/TCP/50002</span><span class="sxs-lookup"><span data-stu-id="6d9cd-142">MTLS/TCP/50002</span></span></p></td>
<td><p><span data-ttu-id="6d9cd-143">Любые</span><span class="sxs-lookup"><span data-stu-id="6d9cd-143">Any</span></span></p></td>
<td><p><span data-ttu-id="6d9cd-144">Режиссер</span><span class="sxs-lookup"><span data-stu-id="6d9cd-144">Director</span></span></p></td>
<td><p><span data-ttu-id="6d9cd-145">Команды и коллекция журналов для централизованного ведения журналов (ClsController. exe) или агента (ClsAgent. exe)</span><span class="sxs-lookup"><span data-stu-id="6d9cd-145">Centralized Logging Service controller (ClsController.exe) or agent (ClsAgent.exe)commands and log collection</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6d9cd-146">MTLS/TCP/50003</span><span class="sxs-lookup"><span data-stu-id="6d9cd-146">MTLS/TCP/50003</span></span></p></td>
<td><p><span data-ttu-id="6d9cd-147">Любые</span><span class="sxs-lookup"><span data-stu-id="6d9cd-147">Any</span></span></p></td>
<td><p><span data-ttu-id="6d9cd-148">Режиссер</span><span class="sxs-lookup"><span data-stu-id="6d9cd-148">Director</span></span></p></td>
<td><p><span data-ttu-id="6d9cd-149">Команды и коллекция журналов для централизованного ведения журналов (ClsController. exe) или агента (ClsAgent. exe)</span><span class="sxs-lookup"><span data-stu-id="6d9cd-149">Centralized Logging Service controller (ClsController.exe) or agent (ClsAgent.exe)commands and log collection</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

