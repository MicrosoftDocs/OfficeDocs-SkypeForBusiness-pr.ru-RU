---
title: 'Lync Server 2013: сводка по портам — масштабируемый пул директоров, аппаратный балансировщик нагрузки'
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
ms.openlocfilehash: 91c1970b85b5b0c76174dfbc9d6dcec9ac24cc4d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48534066"
---
# <a name="port-summary---scaled-director-pool-hardware-load-balancer-in-lync-server-2013"></a><span data-ttu-id="1f043-102">Сводка по портам — масштабируемый пул директоров, аппаратный балансировщик нагрузки в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1f043-102">Port summary - Scaled Director pool, hardware load balancer in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1f043-103">_**Последнее изменение темы:** 2012-10-21_</span><span class="sxs-lookup"><span data-stu-id="1f043-103">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="1f043-104">Требования к портам брандмауэра для пула директоров состоят из портов, которые используются для установления связи с директором от внутреннего интерфейса пограничного сервера или внутреннего интерфейса обратного прокси-сервера.</span><span class="sxs-lookup"><span data-stu-id="1f043-104">Firewall port requirements for a Director pool consist of the ports that are used to establish communication with the Director from the internal interface of the Edge Server or internal-facing interface of the reverse proxy.</span></span> <span data-ttu-id="1f043-105">По умолчанию Microsoft Lync Server 2013 ожидает, что порты HTTP/TCP 8080 и HTTPS/TCP 4443 открываются из обратного прокси-сервера в директоре, а также интерфейсный пул и сервер переднего плана.</span><span class="sxs-lookup"><span data-stu-id="1f043-105">Microsoft Lync Server 2013 by default expects ports HTTP/TCP 8080 and HTTPS/TCP 4443 to be open from the reverse proxy to the Director, as well as the Front End pool and Front End Server.</span></span> <span data-ttu-id="1f043-106">Кроме того, должен быть обмен данными по протоколу SIP от внутреннего интерфейса пограничного сервера к директоре и к интерфейсному пулу и серверу переднего плана.</span><span class="sxs-lookup"><span data-stu-id="1f043-106">Additionally, there must be session initiation protocol (SIP) communication from the Edge Server internal interface to the Director and to the Front End pool and Front End Server.</span></span> <span data-ttu-id="1f043-107">Протокол SIP использует SIP/MTLS/TCP 5061 с пограничного сервера в интерфейсный пул и сервер переднего плана.</span><span class="sxs-lookup"><span data-stu-id="1f043-107">The SIP protocol uses SIP/MTLS/TCP 5061 from the Edge Server to the Front End pool and Front End Server.</span></span> <span data-ttu-id="1f043-108">Необходимо также создать правило, разрешающее передачу данных по протоколу SIP/MTLS/TCP 5061 из директора, интерфейсного пула и сервера переднего плана в внутренний интерфейс пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="1f043-108">A rule that allows SIP/MTLS/TCP 5061 communication from the Director, Front End pool and Front End Server to the Edge Server internal interface must be created as well.</span></span>

### <a name="director-ports-and-protocols-for-firewall-definitions"></a><span data-ttu-id="1f043-109">Порты и протоколы Директора для определений брандмауэра</span><span class="sxs-lookup"><span data-stu-id="1f043-109">Director Ports and Protocols for Firewall Definitions</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1f043-110">Роль/протокол/TCP или UDP/порт</span><span class="sxs-lookup"><span data-stu-id="1f043-110">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="1f043-111">Исходный IP-адрес</span><span class="sxs-lookup"><span data-stu-id="1f043-111">Source IP address</span></span></th>
<th><span data-ttu-id="1f043-112">Конечный IP-адрес</span><span class="sxs-lookup"><span data-stu-id="1f043-112">Destination IP address</span></span></th>
<th><span data-ttu-id="1f043-113">Примечания</span><span class="sxs-lookup"><span data-stu-id="1f043-113">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1f043-114">HTTP/TCP 8080</span><span class="sxs-lookup"><span data-stu-id="1f043-114">HTTP/TCP 8080</span></span></p></td>
<td><p><span data-ttu-id="1f043-115">Внутренний интерфейс обратного прокси-сервера</span><span class="sxs-lookup"><span data-stu-id="1f043-115">Reverse proxy internal interface</span></span></p></td>
<td><p><span data-ttu-id="1f043-116">Виртуальный IP-адрес подсистемы балансировки нагрузки для директоров</span><span class="sxs-lookup"><span data-stu-id="1f043-116">Director Hardware Load Balancer VIP</span></span></p></td>
<td><p><span data-ttu-id="1f043-117">По умолчанию полученная внешняя сторона обратного прокси-сервера передается на директор HLB VIP и серверы переднего плана.</span><span class="sxs-lookup"><span data-stu-id="1f043-117">Initially received by the external side of the reverse proxy, the communication is sent on to the Director HLB VIP and Front End Servers web services</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1f043-118">HTTPS/TCP 4443</span><span class="sxs-lookup"><span data-stu-id="1f043-118">HTTPS/TCP 4443</span></span></p></td>
<td><p><span data-ttu-id="1f043-119">Внутренний интерфейс обратного прокси-сервера</span><span class="sxs-lookup"><span data-stu-id="1f043-119">Reverse proxy internal interface</span></span></p></td>
<td><p><span data-ttu-id="1f043-120">Виртуальный IP-адрес подсистемы балансировки нагрузки для директоров</span><span class="sxs-lookup"><span data-stu-id="1f043-120">Director Hardware Load Balancer VIP</span></span></p></td>
<td><p><span data-ttu-id="1f043-121">По умолчанию полученная внешняя сторона обратного прокси-сервера передается на директор HLB VIP и серверы переднего плана.</span><span class="sxs-lookup"><span data-stu-id="1f043-121">Initially received by the external side of the reverse proxy, the communication is sent on to the Director HLB VIP and Front End Servers web services</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1f043-122">HTTPS/TCP 444</span><span class="sxs-lookup"><span data-stu-id="1f043-122">HTTPS/TCP 444</span></span></p></td>
<td><p><span data-ttu-id="1f043-123">Директор</span><span class="sxs-lookup"><span data-stu-id="1f043-123">Director</span></span></p></td>
<td><p><span data-ttu-id="1f043-124">Сервер переднего плана или интерфейсный пул</span><span class="sxs-lookup"><span data-stu-id="1f043-124">Front End Server or Front End pool</span></span></p></td>
<td><p><span data-ttu-id="1f043-125">Межсерверное взаимодействие между директором HLB VIP и серверами переднего плана</span><span class="sxs-lookup"><span data-stu-id="1f043-125">Inter-server communication between the Director HLB VIP and the Front End Servers</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1f043-126">HTTP/TCP 80</span><span class="sxs-lookup"><span data-stu-id="1f043-126">HTTP/TCP 80</span></span></p></td>
<td><p><span data-ttu-id="1f043-127">Внутренние клиенты</span><span class="sxs-lookup"><span data-stu-id="1f043-127">Internal Clients</span></span></p></td>
<td><p><span data-ttu-id="1f043-128">Виртуальный IP-адрес подсистемы балансировки нагрузки для директоров</span><span class="sxs-lookup"><span data-stu-id="1f043-128">Director Hardware Load Balancer VIP</span></span></p></td>
<td><p><span data-ttu-id="1f043-129">Директор предоставляет веб-службы внутренним и внешним клиентам.</span><span class="sxs-lookup"><span data-stu-id="1f043-129">The Director provides web services to internal as well as external clients.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1f043-130">HTTPS/TCP 443</span><span class="sxs-lookup"><span data-stu-id="1f043-130">HTTPS/TCP 443</span></span></p></td>
<td><p><span data-ttu-id="1f043-131">Внутренние клиенты</span><span class="sxs-lookup"><span data-stu-id="1f043-131">Internal Clients</span></span></p></td>
<td><p><span data-ttu-id="1f043-132">Виртуальный IP-адрес подсистемы балансировки нагрузки для директоров</span><span class="sxs-lookup"><span data-stu-id="1f043-132">Director Hardware Load Balancer VIP</span></span></p></td>
<td><p><span data-ttu-id="1f043-133">Директор предоставляет веб-службы внутренним и внешним клиентам.</span><span class="sxs-lookup"><span data-stu-id="1f043-133">The Director provides web services to internal as well as external clients.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1f043-134">SIP/MTLS/TCP 5061</span><span class="sxs-lookup"><span data-stu-id="1f043-134">SIP/MTLS/TCP 5061</span></span></p></td>
<td><p><span data-ttu-id="1f043-135">Внутренний интерфейс пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="1f043-135">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="1f043-136">Виртуальный IP-адрес подсистемы балансировки нагрузки для директоров</span><span class="sxs-lookup"><span data-stu-id="1f043-136">Director Hardware Load Balancer VIP</span></span></p></td>
<td><p><span data-ttu-id="1f043-137">Обмен данными SIP от пограничного сервера к директоре и серверам переднего плана.</span><span class="sxs-lookup"><span data-stu-id="1f043-137">SIP communication from the Edge Server to the Director, and Front End Servers.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1f043-138">MTLS/TCP/50001</span><span class="sxs-lookup"><span data-stu-id="1f043-138">MTLS/TCP/50001</span></span></p></td>
<td><p><span data-ttu-id="1f043-139">Любой</span><span class="sxs-lookup"><span data-stu-id="1f043-139">Any</span></span></p></td>
<td><p><span data-ttu-id="1f043-140">Директор</span><span class="sxs-lookup"><span data-stu-id="1f043-140">Director</span></span></p></td>
<td><p><span data-ttu-id="1f043-141">Команды и сбор журналов централизованной службы ведения журналов (ClsController.exe) или агента (ClsAgent.exe)</span><span class="sxs-lookup"><span data-stu-id="1f043-141">Centralized Logging Service controller (ClsController.exe) or agent (ClsAgent.exe)commands and log collection</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1f043-142">MTLS/TCP/50002</span><span class="sxs-lookup"><span data-stu-id="1f043-142">MTLS/TCP/50002</span></span></p></td>
<td><p><span data-ttu-id="1f043-143">Любой</span><span class="sxs-lookup"><span data-stu-id="1f043-143">Any</span></span></p></td>
<td><p><span data-ttu-id="1f043-144">Директор</span><span class="sxs-lookup"><span data-stu-id="1f043-144">Director</span></span></p></td>
<td><p><span data-ttu-id="1f043-145">Команды и сбор журналов централизованной службы ведения журналов (ClsController.exe) или агента (ClsAgent.exe)</span><span class="sxs-lookup"><span data-stu-id="1f043-145">Centralized Logging Service controller (ClsController.exe) or agent (ClsAgent.exe)commands and log collection</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1f043-146">MTLS/TCP/50003</span><span class="sxs-lookup"><span data-stu-id="1f043-146">MTLS/TCP/50003</span></span></p></td>
<td><p><span data-ttu-id="1f043-147">Любой</span><span class="sxs-lookup"><span data-stu-id="1f043-147">Any</span></span></p></td>
<td><p><span data-ttu-id="1f043-148">Директор</span><span class="sxs-lookup"><span data-stu-id="1f043-148">Director</span></span></p></td>
<td><p><span data-ttu-id="1f043-149">Команды и сбор журналов централизованной службы ведения журналов (ClsController.exe) или агента (ClsAgent.exe)</span><span class="sxs-lookup"><span data-stu-id="1f043-149">Centralized Logging Service controller (ClsController.exe) or agent (ClsAgent.exe)commands and log collection</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

