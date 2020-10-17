---
title: 'Lync Server 2013: сводка по портам — масштабируемый пул директоров, аппаратный балансировщик нагрузки'
description: 'Lync Server 2013: сводка по портам — масштабируемый пул директоров, аппаратный балансировщик нагрузки.'
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
ms.openlocfilehash: 10bfb3a3ad3a38b6cb0e46414bf22deecc71d7b5
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48564555"
---
# <a name="port-summary---scaled-director-pool-hardware-load-balancer-in-lync-server-2013"></a><span data-ttu-id="891ac-103">Сводка по портам — масштабируемый пул директоров, аппаратный балансировщик нагрузки в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="891ac-103">Port summary - Scaled Director pool, hardware load balancer in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="891ac-104">_**Последнее изменение темы:** 2012-10-21_</span><span class="sxs-lookup"><span data-stu-id="891ac-104">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="891ac-105">Требования к портам брандмауэра для пула директоров состоят из портов, которые используются для установления связи с директором от внутреннего интерфейса пограничного сервера или внутреннего интерфейса обратного прокси-сервера.</span><span class="sxs-lookup"><span data-stu-id="891ac-105">Firewall port requirements for a Director pool consist of the ports that are used to establish communication with the Director from the internal interface of the Edge Server or internal-facing interface of the reverse proxy.</span></span> <span data-ttu-id="891ac-106">По умолчанию Microsoft Lync Server 2013 ожидает, что порты HTTP/TCP 8080 и HTTPS/TCP 4443 открываются из обратного прокси-сервера в директоре, а также интерфейсный пул и сервер переднего плана.</span><span class="sxs-lookup"><span data-stu-id="891ac-106">Microsoft Lync Server 2013 by default expects ports HTTP/TCP 8080 and HTTPS/TCP 4443 to be open from the reverse proxy to the Director, as well as the Front End pool and Front End Server.</span></span> <span data-ttu-id="891ac-107">Кроме того, должен быть обмен данными по протоколу SIP от внутреннего интерфейса пограничного сервера к директоре и к интерфейсному пулу и серверу переднего плана.</span><span class="sxs-lookup"><span data-stu-id="891ac-107">Additionally, there must be session initiation protocol (SIP) communication from the Edge Server internal interface to the Director and to the Front End pool and Front End Server.</span></span> <span data-ttu-id="891ac-108">Протокол SIP использует SIP/MTLS/TCP 5061 с пограничного сервера в интерфейсный пул и сервер переднего плана.</span><span class="sxs-lookup"><span data-stu-id="891ac-108">The SIP protocol uses SIP/MTLS/TCP 5061 from the Edge Server to the Front End pool and Front End Server.</span></span> <span data-ttu-id="891ac-109">Необходимо также создать правило, разрешающее передачу данных по протоколу SIP/MTLS/TCP 5061 из директора, интерфейсного пула и сервера переднего плана в внутренний интерфейс пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="891ac-109">A rule that allows SIP/MTLS/TCP 5061 communication from the Director, Front End pool and Front End Server to the Edge Server internal interface must be created as well.</span></span>

### <a name="director-ports-and-protocols-for-firewall-definitions"></a><span data-ttu-id="891ac-110">Порты и протоколы Директора для определений брандмауэра</span><span class="sxs-lookup"><span data-stu-id="891ac-110">Director Ports and Protocols for Firewall Definitions</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="891ac-111">Роль/протокол/TCP или UDP/порт</span><span class="sxs-lookup"><span data-stu-id="891ac-111">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="891ac-112">Исходный IP-адрес</span><span class="sxs-lookup"><span data-stu-id="891ac-112">Source IP address</span></span></th>
<th><span data-ttu-id="891ac-113">Конечный IP-адрес</span><span class="sxs-lookup"><span data-stu-id="891ac-113">Destination IP address</span></span></th>
<th><span data-ttu-id="891ac-114">Примечания</span><span class="sxs-lookup"><span data-stu-id="891ac-114">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="891ac-115">HTTP/TCP 8080</span><span class="sxs-lookup"><span data-stu-id="891ac-115">HTTP/TCP 8080</span></span></p></td>
<td><p><span data-ttu-id="891ac-116">Внутренний интерфейс обратного прокси-сервера</span><span class="sxs-lookup"><span data-stu-id="891ac-116">Reverse proxy internal interface</span></span></p></td>
<td><p><span data-ttu-id="891ac-117">Виртуальный IP-адрес подсистемы балансировки нагрузки для директоров</span><span class="sxs-lookup"><span data-stu-id="891ac-117">Director Hardware Load Balancer VIP</span></span></p></td>
<td><p><span data-ttu-id="891ac-118">По умолчанию полученная внешняя сторона обратного прокси-сервера передается на директор HLB VIP и серверы переднего плана.</span><span class="sxs-lookup"><span data-stu-id="891ac-118">Initially received by the external side of the reverse proxy, the communication is sent on to the Director HLB VIP and Front End Servers web services</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="891ac-119">HTTPS/TCP 4443</span><span class="sxs-lookup"><span data-stu-id="891ac-119">HTTPS/TCP 4443</span></span></p></td>
<td><p><span data-ttu-id="891ac-120">Внутренний интерфейс обратного прокси-сервера</span><span class="sxs-lookup"><span data-stu-id="891ac-120">Reverse proxy internal interface</span></span></p></td>
<td><p><span data-ttu-id="891ac-121">Виртуальный IP-адрес подсистемы балансировки нагрузки для директоров</span><span class="sxs-lookup"><span data-stu-id="891ac-121">Director Hardware Load Balancer VIP</span></span></p></td>
<td><p><span data-ttu-id="891ac-122">По умолчанию полученная внешняя сторона обратного прокси-сервера передается на директор HLB VIP и серверы переднего плана.</span><span class="sxs-lookup"><span data-stu-id="891ac-122">Initially received by the external side of the reverse proxy, the communication is sent on to the Director HLB VIP and Front End Servers web services</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="891ac-123">HTTPS/TCP 444</span><span class="sxs-lookup"><span data-stu-id="891ac-123">HTTPS/TCP 444</span></span></p></td>
<td><p><span data-ttu-id="891ac-124">Директор</span><span class="sxs-lookup"><span data-stu-id="891ac-124">Director</span></span></p></td>
<td><p><span data-ttu-id="891ac-125">Сервер переднего плана или интерфейсный пул</span><span class="sxs-lookup"><span data-stu-id="891ac-125">Front End Server or Front End pool</span></span></p></td>
<td><p><span data-ttu-id="891ac-126">Межсерверное взаимодействие между директором HLB VIP и серверами переднего плана</span><span class="sxs-lookup"><span data-stu-id="891ac-126">Inter-server communication between the Director HLB VIP and the Front End Servers</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="891ac-127">HTTP/TCP 80</span><span class="sxs-lookup"><span data-stu-id="891ac-127">HTTP/TCP 80</span></span></p></td>
<td><p><span data-ttu-id="891ac-128">Внутренние клиенты</span><span class="sxs-lookup"><span data-stu-id="891ac-128">Internal Clients</span></span></p></td>
<td><p><span data-ttu-id="891ac-129">Виртуальный IP-адрес подсистемы балансировки нагрузки для директоров</span><span class="sxs-lookup"><span data-stu-id="891ac-129">Director Hardware Load Balancer VIP</span></span></p></td>
<td><p><span data-ttu-id="891ac-130">Директор предоставляет веб-службы внутренним и внешним клиентам.</span><span class="sxs-lookup"><span data-stu-id="891ac-130">The Director provides web services to internal as well as external clients.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="891ac-131">HTTPS/TCP 443</span><span class="sxs-lookup"><span data-stu-id="891ac-131">HTTPS/TCP 443</span></span></p></td>
<td><p><span data-ttu-id="891ac-132">Внутренние клиенты</span><span class="sxs-lookup"><span data-stu-id="891ac-132">Internal Clients</span></span></p></td>
<td><p><span data-ttu-id="891ac-133">Виртуальный IP-адрес подсистемы балансировки нагрузки для директоров</span><span class="sxs-lookup"><span data-stu-id="891ac-133">Director Hardware Load Balancer VIP</span></span></p></td>
<td><p><span data-ttu-id="891ac-134">Директор предоставляет веб-службы внутренним и внешним клиентам.</span><span class="sxs-lookup"><span data-stu-id="891ac-134">The Director provides web services to internal as well as external clients.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="891ac-135">SIP/MTLS/TCP 5061</span><span class="sxs-lookup"><span data-stu-id="891ac-135">SIP/MTLS/TCP 5061</span></span></p></td>
<td><p><span data-ttu-id="891ac-136">Внутренний интерфейс пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="891ac-136">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="891ac-137">Виртуальный IP-адрес подсистемы балансировки нагрузки для директоров</span><span class="sxs-lookup"><span data-stu-id="891ac-137">Director Hardware Load Balancer VIP</span></span></p></td>
<td><p><span data-ttu-id="891ac-138">Обмен данными SIP от пограничного сервера к директоре и серверам переднего плана.</span><span class="sxs-lookup"><span data-stu-id="891ac-138">SIP communication from the Edge Server to the Director, and Front End Servers.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="891ac-139">MTLS/TCP/50001</span><span class="sxs-lookup"><span data-stu-id="891ac-139">MTLS/TCP/50001</span></span></p></td>
<td><p><span data-ttu-id="891ac-140">Любой</span><span class="sxs-lookup"><span data-stu-id="891ac-140">Any</span></span></p></td>
<td><p><span data-ttu-id="891ac-141">Директор</span><span class="sxs-lookup"><span data-stu-id="891ac-141">Director</span></span></p></td>
<td><p><span data-ttu-id="891ac-142">Команды и сбор журналов централизованной службы ведения журналов (ClsController.exe) или агента (ClsAgent.exe)</span><span class="sxs-lookup"><span data-stu-id="891ac-142">Centralized Logging Service controller (ClsController.exe) or agent (ClsAgent.exe)commands and log collection</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="891ac-143">MTLS/TCP/50002</span><span class="sxs-lookup"><span data-stu-id="891ac-143">MTLS/TCP/50002</span></span></p></td>
<td><p><span data-ttu-id="891ac-144">Любой</span><span class="sxs-lookup"><span data-stu-id="891ac-144">Any</span></span></p></td>
<td><p><span data-ttu-id="891ac-145">Директор</span><span class="sxs-lookup"><span data-stu-id="891ac-145">Director</span></span></p></td>
<td><p><span data-ttu-id="891ac-146">Команды и сбор журналов централизованной службы ведения журналов (ClsController.exe) или агента (ClsAgent.exe)</span><span class="sxs-lookup"><span data-stu-id="891ac-146">Centralized Logging Service controller (ClsController.exe) or agent (ClsAgent.exe)commands and log collection</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="891ac-147">MTLS/TCP/50003</span><span class="sxs-lookup"><span data-stu-id="891ac-147">MTLS/TCP/50003</span></span></p></td>
<td><p><span data-ttu-id="891ac-148">Любой</span><span class="sxs-lookup"><span data-stu-id="891ac-148">Any</span></span></p></td>
<td><p><span data-ttu-id="891ac-149">Директор</span><span class="sxs-lookup"><span data-stu-id="891ac-149">Director</span></span></p></td>
<td><p><span data-ttu-id="891ac-150">Команды и сбор журналов централизованной службы ведения журналов (ClsController.exe) или агента (ClsAgent.exe)</span><span class="sxs-lookup"><span data-stu-id="891ac-150">Centralized Logging Service controller (ClsController.exe) or agent (ClsAgent.exe)commands and log collection</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

