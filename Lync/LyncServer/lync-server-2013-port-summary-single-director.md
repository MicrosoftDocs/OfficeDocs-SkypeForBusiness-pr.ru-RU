---
title: 'Lync Server 2013: сводка по портам — единственный директор'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Port summary - Single Director
ms:assetid: 079c1414-723f-4499-b7d4-a0d7121c1626
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204648(v=OCS.15)
ms:contentKeyID: 48183322
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5568a37093f161caef6717df5d3a3f09be6f18c2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34824206"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="port-summary---single-director-in-lync-server-2013"></a><span data-ttu-id="98b2f-102">Сводка по портам — единственный директор в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="98b2f-102">Port summary - Single Director in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="98b2f-103">_**Тема последнего изменения:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="98b2f-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="98b2f-104">Требования к порту брандмауэра для единого режиссера состоят из портов, используемых для установления связи с режиссером из внутреннего интерфейса или внутренней сети обратного прокси-сервера.</span><span class="sxs-lookup"><span data-stu-id="98b2f-104">Firewall port requirements for a single Director consist of the ports that are used to establish communication with the Director from the internal interface or internal-facing network of the reverse proxy.</span></span> <span data-ttu-id="98b2f-105">По умолчанию Microsoft Lync Server 2013 ожидает, что порты HTTP/TCP 8080 и HTTPS/TCP 4443 будут открыты из обратного прокси-сервера в директор, а также с интерфейсом пула и сервера переднего плана.</span><span class="sxs-lookup"><span data-stu-id="98b2f-105">Microsoft Lync Server 2013 by default expects ports HTTP/TCP 8080 and HTTPS/TCP 4443 to be open from the reverse proxy to the Director, as well as the Front End pool and Front End Server.</span></span> <span data-ttu-id="98b2f-106">Кроме того, между внутренним интерфейсом пограничного сервера и пулом, а также интерфейсом сервера и переднего плана должен быть установлен протокол SIP.</span><span class="sxs-lookup"><span data-stu-id="98b2f-106">Additionally, there must be session initiation protocol (SIP) communication from the Edge Server internal interface to the Director and to the Front End pool and Front End Server.</span></span> <span data-ttu-id="98b2f-107">Протокол SIP использует интерфейс SIP/MTLS/TCP 5061 с пограничного сервера до пула переднего плана и сервера переднего плана.</span><span class="sxs-lookup"><span data-stu-id="98b2f-107">The SIP protocol uses SIP/MTLS/TCP 5061 from the Edge Server to the Front End pool and Front End Server.</span></span> <span data-ttu-id="98b2f-108">Кроме того, необходимо также создать правило, которое позволяет использовать интерфейс SIP/MTLS/TCP 5061, входящий в состав внешнего интерфейса пограничного сервера и сервера переднего плана.</span><span class="sxs-lookup"><span data-stu-id="98b2f-108">A rule that allows SIP/MTLS/TCP 5061 communication from the Director, Front End pool and Front End Server to the Edge Server internal interface must be created as well.</span></span>

### <a name="single-director-ports-and-protocols-for-firewall-definitions"></a><span data-ttu-id="98b2f-109">Порты и протоколы для отдельных режиссеров для определения брандмауэра</span><span class="sxs-lookup"><span data-stu-id="98b2f-109">Single Director Ports and Protocols for Firewall Definitions</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="98b2f-110">Role/Protocol/TCP/UDP/порт</span><span class="sxs-lookup"><span data-stu-id="98b2f-110">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="98b2f-111">IP-адрес источника</span><span class="sxs-lookup"><span data-stu-id="98b2f-111">Source IP address</span></span></th>
<th><span data-ttu-id="98b2f-112">IP-адрес назначения</span><span class="sxs-lookup"><span data-stu-id="98b2f-112">Destination IP address</span></span></th>
<th><span data-ttu-id="98b2f-113">Примечания.</span><span class="sxs-lookup"><span data-stu-id="98b2f-113">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="98b2f-114">HTTP/TCP 8080</span><span class="sxs-lookup"><span data-stu-id="98b2f-114">HTTP/TCP 8080</span></span></p></td>
<td><p><span data-ttu-id="98b2f-115">Внутренний прокси-интерфейс обратной стороне</span><span class="sxs-lookup"><span data-stu-id="98b2f-115">Reverse proxy internal interface</span></span></p></td>
<td><p><span data-ttu-id="98b2f-116">Директор</span><span class="sxs-lookup"><span data-stu-id="98b2f-116">Director</span></span></p></td>
<td><p><span data-ttu-id="98b2f-117">По внешнему каналу на обратной стороне обратных посредников связь передается на веб-службы Director и Front Server.</span><span class="sxs-lookup"><span data-stu-id="98b2f-117">Initially received by the external side of the reverse proxy, the communication is sent on to the Director and Front End Server web services</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="98b2f-118">HTTPS/TCP 4443</span><span class="sxs-lookup"><span data-stu-id="98b2f-118">HTTPS/TCP 4443</span></span></p></td>
<td><p><span data-ttu-id="98b2f-119">Внутренний прокси-интерфейс обратной стороне</span><span class="sxs-lookup"><span data-stu-id="98b2f-119">Reverse proxy internal interface</span></span></p></td>
<td><p><span data-ttu-id="98b2f-120">Директор</span><span class="sxs-lookup"><span data-stu-id="98b2f-120">Director</span></span></p></td>
<td><p><span data-ttu-id="98b2f-121">По внешнему каналу на обратной стороне обратных посредников связь передается на веб-службы Director и Front Server.</span><span class="sxs-lookup"><span data-stu-id="98b2f-121">Initially received by the external side of the reverse proxy, the communication is sent on to the Director and Front End Server web services</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="98b2f-122">HTTPS/TCP 444</span><span class="sxs-lookup"><span data-stu-id="98b2f-122">HTTPS/TCP 444</span></span></p></td>
<td><p><span data-ttu-id="98b2f-123">Директор</span><span class="sxs-lookup"><span data-stu-id="98b2f-123">Director</span></span></p></td>
<td><p><span data-ttu-id="98b2f-124">Пул переднего плана на сервере или внешнем интерфейсе</span><span class="sxs-lookup"><span data-stu-id="98b2f-124">Front End server or Front End pool</span></span></p></td>
<td><p><span data-ttu-id="98b2f-125">Обмен данными между сервером и сервером переднего плана</span><span class="sxs-lookup"><span data-stu-id="98b2f-125">Inter-server communication between the Director and the Front End Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="98b2f-126">HTTP/TCP 80</span><span class="sxs-lookup"><span data-stu-id="98b2f-126">HTTP/TCP 80</span></span></p></td>
<td><p><span data-ttu-id="98b2f-127">Внутренние клиенты</span><span class="sxs-lookup"><span data-stu-id="98b2f-127">Internal Clients</span></span></p></td>
<td><p><span data-ttu-id="98b2f-128">Веб-службы режиссера</span><span class="sxs-lookup"><span data-stu-id="98b2f-128">Director web services</span></span></p></td>
<td><p><span data-ttu-id="98b2f-129">Режиссер предоставляет веб-службы внутренним и внешним клиентам.</span><span class="sxs-lookup"><span data-stu-id="98b2f-129">The Director provides web services to internal and external clients.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="98b2f-130">HTTPS/TCP 443</span><span class="sxs-lookup"><span data-stu-id="98b2f-130">HTTPS/TCP 443</span></span></p></td>
<td><p><span data-ttu-id="98b2f-131">Внутренние клиенты</span><span class="sxs-lookup"><span data-stu-id="98b2f-131">Internal Clients</span></span></p></td>
<td><p><span data-ttu-id="98b2f-132">Веб-службы режиссера</span><span class="sxs-lookup"><span data-stu-id="98b2f-132">Director web services</span></span></p></td>
<td><p><span data-ttu-id="98b2f-133">Режиссер предоставляет веб-службы внутренним и внешним клиентам.</span><span class="sxs-lookup"><span data-stu-id="98b2f-133">The Director provides web services to internal and external clients.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="98b2f-134">SIP/MTLS/TCP 5061</span><span class="sxs-lookup"><span data-stu-id="98b2f-134">SIP/MTLS/TCP 5061</span></span></p></td>
<td><p><span data-ttu-id="98b2f-135">Внутренний интерфейс пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="98b2f-135">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="98b2f-136">Директор</span><span class="sxs-lookup"><span data-stu-id="98b2f-136">Director</span></span></p></td>
<td><p><span data-ttu-id="98b2f-137">Обмен данными SIP от пограничного сервера к директоре и внешнему серверу.</span><span class="sxs-lookup"><span data-stu-id="98b2f-137">SIP communication from the Edge Server to the Director, and the Front End Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="98b2f-138">MTLS/TCP/50001</span><span class="sxs-lookup"><span data-stu-id="98b2f-138">MTLS/TCP/50001</span></span></p></td>
<td><p><span data-ttu-id="98b2f-139">Любой</span><span class="sxs-lookup"><span data-stu-id="98b2f-139">Any</span></span></p></td>
<td><p><span data-ttu-id="98b2f-140">Внутренний интерфейс пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="98b2f-140">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="98b2f-141">Команды для централизованного ведения журналов (Клсконтроллер. exe) или агента (Класажент. exe) и сбора журналов</span><span class="sxs-lookup"><span data-stu-id="98b2f-141">Centralized Logging Service controller (ClsController.exe) or agent (ClasAgent.exe)commands and log collection</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="98b2f-142">MTLS/TCP/50002</span><span class="sxs-lookup"><span data-stu-id="98b2f-142">MTLS/TCP/50002</span></span></p></td>
<td><p><span data-ttu-id="98b2f-143">Любой</span><span class="sxs-lookup"><span data-stu-id="98b2f-143">Any</span></span></p></td>
<td><p><span data-ttu-id="98b2f-144">Внутренний интерфейс пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="98b2f-144">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="98b2f-145">Команды для централизованного ведения журналов (Клсконтроллер. exe) или агента (Класажент. exe) и сбора журналов</span><span class="sxs-lookup"><span data-stu-id="98b2f-145">Centralized Logging Service controller (ClsController.exe) or agent (ClasAgent.exe)commands and log collection</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="98b2f-146">MTLS/TCP/50003</span><span class="sxs-lookup"><span data-stu-id="98b2f-146">MTLS/TCP/50003</span></span></p></td>
<td><p><span data-ttu-id="98b2f-147">Любой</span><span class="sxs-lookup"><span data-stu-id="98b2f-147">Any</span></span></p></td>
<td><p><span data-ttu-id="98b2f-148">Внутренний интерфейс пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="98b2f-148">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="98b2f-149">Команды для централизованного ведения журналов (Клсконтроллер. exe) или агента (Класажент. exe) и сбора журналов</span><span class="sxs-lookup"><span data-stu-id="98b2f-149">Centralized Logging Service controller (ClsController.exe) or agent (ClasAgent.exe)commands and log collection</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

