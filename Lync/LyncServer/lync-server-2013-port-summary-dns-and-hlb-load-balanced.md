---
title: 'Lync Server 2013: сводка по портам — балансировка нагрузки на DNS и HLB'
description: 'Lync Server 2013: сводка по портам — служба DNS и балансировка нагрузки HLB.'
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
ms.openlocfilehash: be2e8204e792fd9c4718cb9171e90784af2d0104
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543135"
---
# <a name="port-summary---dns-and-hlb-load-balanced-in-lync-server-2013"></a><span data-ttu-id="1cdf4-103">Сводка по портам — балансировка нагрузки на DNS и HLB в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1cdf4-103">Port summary - DNS and HLB load balanced in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1cdf4-104">_**Последнее изменение темы:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="1cdf4-104">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="1cdf4-105">Требования к портам брандмауэра для одного директора состоят из портов, которые используются для установления связи с директором от внутреннего интерфейса или внутренней сети обратного прокси-сервера.</span><span class="sxs-lookup"><span data-stu-id="1cdf4-105">Firewall port requirements for a single Director consist of the ports that are used to establish communication with the Director from the internal interface or internal-facing network of the reverse proxy.</span></span> <span data-ttu-id="1cdf4-106">По умолчанию Microsoft Lync Server 2013 ожидает, что порты HTTP/TCP 8080 и HTTPS/TCP 4443 открываются из обратного прокси-сервера в директоре, а также интерфейсный пул и сервер переднего плана.</span><span class="sxs-lookup"><span data-stu-id="1cdf4-106">Microsoft Lync Server 2013 by default expects ports HTTP/TCP 8080 and HTTPS/TCP 4443 to be open from the reverse proxy to the Director, as well as the Front End pool and Front End Server.</span></span> <span data-ttu-id="1cdf4-107">Кроме того, должен быть обмен данными по протоколу SIP от внутреннего интерфейса пограничного сервера к директоре и к интерфейсному пулу и серверу переднего плана.</span><span class="sxs-lookup"><span data-stu-id="1cdf4-107">Additionally, there must be session initiation protocol (SIP) communication from the Edge Server internal interface to the Director and to the Front End pool and Front End Server.</span></span> <span data-ttu-id="1cdf4-108">Протокол SIP использует SIP/MTLS/TCP 5061 с пограничного сервера в интерфейсный пул и сервер переднего плана.</span><span class="sxs-lookup"><span data-stu-id="1cdf4-108">The SIP protocol uses SIP/MTLS/TCP 5061 from the Edge Server to the Front End pool and Front End Server.</span></span> <span data-ttu-id="1cdf4-109">Необходимо также создать правило, разрешающее передачу данных по протоколу SIP/MTLS/TCP 5061 из директора, интерфейсного пула и сервера переднего плана в внутренний интерфейс пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="1cdf4-109">A rule that allows SIP/MTLS/TCP 5061 communication from the Director, Front End pool and Front End Server to the Edge Server internal interface must be created as well.</span></span>

### <a name="single-director-ports-and-protocols-for-firewall-definitions"></a><span data-ttu-id="1cdf4-110">Порты и протоколы единого директора для определений брандмауэра</span><span class="sxs-lookup"><span data-stu-id="1cdf4-110">Single Director Ports and Protocols for Firewall Definitions</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1cdf4-111">Роль/протокол/TCP или UDP/порт</span><span class="sxs-lookup"><span data-stu-id="1cdf4-111">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="1cdf4-112">Исходный IP-адрес</span><span class="sxs-lookup"><span data-stu-id="1cdf4-112">Source IP address</span></span></th>
<th><span data-ttu-id="1cdf4-113">Конечный IP-адрес</span><span class="sxs-lookup"><span data-stu-id="1cdf4-113">Destination IP address</span></span></th>
<th><span data-ttu-id="1cdf4-114">Примечания</span><span class="sxs-lookup"><span data-stu-id="1cdf4-114">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1cdf4-115">HTTP/TCP 8080</span><span class="sxs-lookup"><span data-stu-id="1cdf4-115">HTTP/TCP 8080</span></span></p></td>
<td><p><span data-ttu-id="1cdf4-116">Внутренний интерфейс обратного прокси-сервера</span><span class="sxs-lookup"><span data-stu-id="1cdf4-116">Reverse proxy internal interface</span></span></p></td>
<td><p><span data-ttu-id="1cdf4-117">Виртуальный IP-адрес подсистемы балансировки нагрузки для директоров</span><span class="sxs-lookup"><span data-stu-id="1cdf4-117">Director Hardware Load Balancer VIP</span></span></p></td>
<td><p><span data-ttu-id="1cdf4-118">По умолчанию полученная внешняя сторона обратного прокси-сервера передается на директор HLB VIP и веб-службы сервера переднего плана.</span><span class="sxs-lookup"><span data-stu-id="1cdf4-118">Initially received by the external side of the reverse proxy, the communication is sent on to the Director HLB VIP and Front End Server web services.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1cdf4-119">HTTPS/TCP 4443</span><span class="sxs-lookup"><span data-stu-id="1cdf4-119">HTTPS/TCP 4443</span></span></p></td>
<td><p><span data-ttu-id="1cdf4-120">Внутренний интерфейс обратного прокси-сервера</span><span class="sxs-lookup"><span data-stu-id="1cdf4-120">Reverse proxy internal interface</span></span></p></td>
<td><p><span data-ttu-id="1cdf4-121">Виртуальный IP-адрес подсистемы балансировки нагрузки для директоров</span><span class="sxs-lookup"><span data-stu-id="1cdf4-121">Director Hardware Load Balancer VIP</span></span></p></td>
<td><p><span data-ttu-id="1cdf4-122">По умолчанию полученная внешняя сторона обратного прокси-сервера передается на директор HLB VIP и веб-службы сервера переднего плана.</span><span class="sxs-lookup"><span data-stu-id="1cdf4-122">Initially received by the external side of the reverse proxy, the communication is sent on to the Director HLB VIP and Front End Server web services.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1cdf4-123">HTTPS/TCP 444</span><span class="sxs-lookup"><span data-stu-id="1cdf4-123">HTTPS/TCP 444</span></span></p></td>
<td><p><span data-ttu-id="1cdf4-124">Директор</span><span class="sxs-lookup"><span data-stu-id="1cdf4-124">Director</span></span></p></td>
<td><p><span data-ttu-id="1cdf4-125">Интерфейсный пул или сервер переднего плана</span><span class="sxs-lookup"><span data-stu-id="1cdf4-125">Front End pool or Front End Server</span></span></p></td>
<td><p><span data-ttu-id="1cdf4-126">Обмен данными между сервером HLB и сервером переднего плана и серверами переднего плана и серверами переднего плана.</span><span class="sxs-lookup"><span data-stu-id="1cdf4-126">Inter-server communication between the Director HLB VIP and the Front End Server or Front End Servers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1cdf4-127">HTTP/TCP 80</span><span class="sxs-lookup"><span data-stu-id="1cdf4-127">HTTP/TCP 80</span></span></p></td>
<td><p><span data-ttu-id="1cdf4-128">Внутренние клиенты</span><span class="sxs-lookup"><span data-stu-id="1cdf4-128">Internal Clients</span></span></p></td>
<td><p><span data-ttu-id="1cdf4-129">Виртуальный IP-адрес подсистемы балансировки нагрузки для директоров</span><span class="sxs-lookup"><span data-stu-id="1cdf4-129">Director Hardware Load Balancer VIP</span></span></p></td>
<td><p><span data-ttu-id="1cdf4-130">Директор предоставляет веб-службы внутренним и внешним клиентам.</span><span class="sxs-lookup"><span data-stu-id="1cdf4-130">The Director provides web services to internal as well as external clients.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1cdf4-131">HTTPS/TCP 443</span><span class="sxs-lookup"><span data-stu-id="1cdf4-131">HTTPS/TCP 443</span></span></p></td>
<td><p><span data-ttu-id="1cdf4-132">Внутренние клиенты</span><span class="sxs-lookup"><span data-stu-id="1cdf4-132">Internal Clients</span></span></p></td>
<td><p><span data-ttu-id="1cdf4-133">Виртуальный IP-адрес подсистемы балансировки нагрузки для директоров</span><span class="sxs-lookup"><span data-stu-id="1cdf4-133">Director Hardware Load Balancer VIP</span></span></p></td>
<td><p><span data-ttu-id="1cdf4-134">Директор предоставляет веб-службы внутренним и внешним клиентам.</span><span class="sxs-lookup"><span data-stu-id="1cdf4-134">The Director provides web services to internal as well as external clients.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1cdf4-135">SIP/MTLS/TCP 5061</span><span class="sxs-lookup"><span data-stu-id="1cdf4-135">SIP/MTLS/TCP 5061</span></span></p></td>
<td><p><span data-ttu-id="1cdf4-136">Внутренний интерфейс пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="1cdf4-136">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="1cdf4-137">Директор</span><span class="sxs-lookup"><span data-stu-id="1cdf4-137">Director</span></span></p></td>
<td><p><span data-ttu-id="1cdf4-138">Обмен данными SIP от пограничного сервера к директоре, а также к серверам переднего плана.</span><span class="sxs-lookup"><span data-stu-id="1cdf4-138">SIP communication from the Edge Server to the Director, as well as the Front End Servers.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1cdf4-139">MTLS/TCP/50001</span><span class="sxs-lookup"><span data-stu-id="1cdf4-139">MTLS/TCP/50001</span></span></p></td>
<td><p><span data-ttu-id="1cdf4-140">Любой</span><span class="sxs-lookup"><span data-stu-id="1cdf4-140">Any</span></span></p></td>
<td><p><span data-ttu-id="1cdf4-141">Директор</span><span class="sxs-lookup"><span data-stu-id="1cdf4-141">Director</span></span></p></td>
<td><p><span data-ttu-id="1cdf4-142">Команды и сбор журналов централизованной службы ведения журналов (ClsController.exe) или агента (ClsAgent.exe)</span><span class="sxs-lookup"><span data-stu-id="1cdf4-142">Centralized Logging Service controller (ClsController.exe) or agent (ClsAgent.exe)commands and log collection</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1cdf4-143">MTLS/TCP/50002</span><span class="sxs-lookup"><span data-stu-id="1cdf4-143">MTLS/TCP/50002</span></span></p></td>
<td><p><span data-ttu-id="1cdf4-144">Любой</span><span class="sxs-lookup"><span data-stu-id="1cdf4-144">Any</span></span></p></td>
<td><p><span data-ttu-id="1cdf4-145">Директор</span><span class="sxs-lookup"><span data-stu-id="1cdf4-145">Director</span></span></p></td>
<td><p><span data-ttu-id="1cdf4-146">Команды и сбор журналов централизованной службы ведения журналов (ClsController.exe) или агента (ClsAgent.exe)</span><span class="sxs-lookup"><span data-stu-id="1cdf4-146">Centralized Logging Service controller (ClsController.exe) or agent (ClsAgent.exe)commands and log collection</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1cdf4-147">MTLS/TCP/50003</span><span class="sxs-lookup"><span data-stu-id="1cdf4-147">MTLS/TCP/50003</span></span></p></td>
<td><p><span data-ttu-id="1cdf4-148">Любой</span><span class="sxs-lookup"><span data-stu-id="1cdf4-148">Any</span></span></p></td>
<td><p><span data-ttu-id="1cdf4-149">Директор</span><span class="sxs-lookup"><span data-stu-id="1cdf4-149">Director</span></span></p></td>
<td><p><span data-ttu-id="1cdf4-150">Команды и сбор журналов централизованной службы ведения журналов (ClsController.exe) или агента (ClsAgent.exe)</span><span class="sxs-lookup"><span data-stu-id="1cdf4-150">Centralized Logging Service controller (ClsController.exe) or agent (ClsAgent.exe)commands and log collection</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

