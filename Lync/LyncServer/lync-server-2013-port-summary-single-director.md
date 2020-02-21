---
title: 'Lync Server 2013: сводка по портам — один директор'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Port summary - Single Director
ms:assetid: 079c1414-723f-4499-b7d4-a0d7121c1626
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204648(v=OCS.15)
ms:contentKeyID: 48183322
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 27095f154d4a79af949d3568bb444adfc83699c9
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42208955"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="port-summary---single-director-in-lync-server-2013"></a><span data-ttu-id="b74b9-102">Сводка по портам — единственный директор в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b74b9-102">Port summary - Single Director in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b74b9-103">_**Последнее изменение темы:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="b74b9-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="b74b9-104">Требования к портам брандмауэра для одного директора состоят из портов, которые используются для установления связи с директором от внутреннего интерфейса или внутренней сети обратного прокси-сервера.</span><span class="sxs-lookup"><span data-stu-id="b74b9-104">Firewall port requirements for a single Director consist of the ports that are used to establish communication with the Director from the internal interface or internal-facing network of the reverse proxy.</span></span> <span data-ttu-id="b74b9-105">По умолчанию Microsoft Lync Server 2013 ожидает, что порты HTTP/TCP 8080 и HTTPS/TCP 4443 открываются из обратного прокси-сервера в директоре, а также интерфейсный пул и сервер переднего плана.</span><span class="sxs-lookup"><span data-stu-id="b74b9-105">Microsoft Lync Server 2013 by default expects ports HTTP/TCP 8080 and HTTPS/TCP 4443 to be open from the reverse proxy to the Director, as well as the Front End pool and Front End Server.</span></span> <span data-ttu-id="b74b9-106">Кроме того, должен быть обмен данными по протоколу SIP от внутреннего интерфейса пограничного сервера к директоре и к интерфейсному пулу и серверу переднего плана.</span><span class="sxs-lookup"><span data-stu-id="b74b9-106">Additionally, there must be session initiation protocol (SIP) communication from the Edge Server internal interface to the Director and to the Front End pool and Front End Server.</span></span> <span data-ttu-id="b74b9-107">Протокол SIP использует SIP/MTLS/TCP 5061 с пограничного сервера в интерфейсный пул и сервер переднего плана.</span><span class="sxs-lookup"><span data-stu-id="b74b9-107">The SIP protocol uses SIP/MTLS/TCP 5061 from the Edge Server to the Front End pool and Front End Server.</span></span> <span data-ttu-id="b74b9-108">Необходимо также создать правило, разрешающее передачу данных по протоколу SIP/MTLS/TCP 5061 из директора, интерфейсного пула и сервера переднего плана в внутренний интерфейс пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="b74b9-108">A rule that allows SIP/MTLS/TCP 5061 communication from the Director, Front End pool and Front End Server to the Edge Server internal interface must be created as well.</span></span>

### <a name="single-director-ports-and-protocols-for-firewall-definitions"></a><span data-ttu-id="b74b9-109">Порты и протоколы единого директора для определений брандмауэра</span><span class="sxs-lookup"><span data-stu-id="b74b9-109">Single Director Ports and Protocols for Firewall Definitions</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b74b9-110">Роль/протокол/TCP или UDP/порт</span><span class="sxs-lookup"><span data-stu-id="b74b9-110">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="b74b9-111">Исходный IP-адрес</span><span class="sxs-lookup"><span data-stu-id="b74b9-111">Source IP address</span></span></th>
<th><span data-ttu-id="b74b9-112">Конечный IP-адрес</span><span class="sxs-lookup"><span data-stu-id="b74b9-112">Destination IP address</span></span></th>
<th><span data-ttu-id="b74b9-113">Notes</span><span class="sxs-lookup"><span data-stu-id="b74b9-113">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b74b9-114">HTTP/TCP 8080</span><span class="sxs-lookup"><span data-stu-id="b74b9-114">HTTP/TCP 8080</span></span></p></td>
<td><p><span data-ttu-id="b74b9-115">Внутренний интерфейс обратного прокси-сервера</span><span class="sxs-lookup"><span data-stu-id="b74b9-115">Reverse proxy internal interface</span></span></p></td>
<td><p><span data-ttu-id="b74b9-116">Режиссер</span><span class="sxs-lookup"><span data-stu-id="b74b9-116">Director</span></span></p></td>
<td><p><span data-ttu-id="b74b9-117">Полученная внешними сторонами обратного прокси-сервера, связь передается в директории и веб-службы сервера переднего плана</span><span class="sxs-lookup"><span data-stu-id="b74b9-117">Initially received by the external side of the reverse proxy, the communication is sent on to the Director and Front End Server web services</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b74b9-118">HTTPS/TCP 4443</span><span class="sxs-lookup"><span data-stu-id="b74b9-118">HTTPS/TCP 4443</span></span></p></td>
<td><p><span data-ttu-id="b74b9-119">Внутренний интерфейс обратного прокси-сервера</span><span class="sxs-lookup"><span data-stu-id="b74b9-119">Reverse proxy internal interface</span></span></p></td>
<td><p><span data-ttu-id="b74b9-120">Режиссер</span><span class="sxs-lookup"><span data-stu-id="b74b9-120">Director</span></span></p></td>
<td><p><span data-ttu-id="b74b9-121">Полученная внешними сторонами обратного прокси-сервера, связь передается в директории и веб-службы сервера переднего плана</span><span class="sxs-lookup"><span data-stu-id="b74b9-121">Initially received by the external side of the reverse proxy, the communication is sent on to the Director and Front End Server web services</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b74b9-122">HTTPS/TCP 444</span><span class="sxs-lookup"><span data-stu-id="b74b9-122">HTTPS/TCP 444</span></span></p></td>
<td><p><span data-ttu-id="b74b9-123">Режиссер</span><span class="sxs-lookup"><span data-stu-id="b74b9-123">Director</span></span></p></td>
<td><p><span data-ttu-id="b74b9-124">Сервер переднего плана или интерфейсный пул</span><span class="sxs-lookup"><span data-stu-id="b74b9-124">Front End server or Front End pool</span></span></p></td>
<td><p><span data-ttu-id="b74b9-125">Межсерверное взаимодействие между директором и сервером переднего плана</span><span class="sxs-lookup"><span data-stu-id="b74b9-125">Inter-server communication between the Director and the Front End Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b74b9-126">HTTP/TCP 80</span><span class="sxs-lookup"><span data-stu-id="b74b9-126">HTTP/TCP 80</span></span></p></td>
<td><p><span data-ttu-id="b74b9-127">Внутренние клиенты</span><span class="sxs-lookup"><span data-stu-id="b74b9-127">Internal Clients</span></span></p></td>
<td><p><span data-ttu-id="b74b9-128">Веб-службы режиссера</span><span class="sxs-lookup"><span data-stu-id="b74b9-128">Director web services</span></span></p></td>
<td><p><span data-ttu-id="b74b9-129">Директор предоставляет веб-службы внутренним и внешним клиентам.</span><span class="sxs-lookup"><span data-stu-id="b74b9-129">The Director provides web services to internal and external clients.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b74b9-130">HTTPS/TCP 443</span><span class="sxs-lookup"><span data-stu-id="b74b9-130">HTTPS/TCP 443</span></span></p></td>
<td><p><span data-ttu-id="b74b9-131">Внутренние клиенты</span><span class="sxs-lookup"><span data-stu-id="b74b9-131">Internal Clients</span></span></p></td>
<td><p><span data-ttu-id="b74b9-132">Веб-службы режиссера</span><span class="sxs-lookup"><span data-stu-id="b74b9-132">Director web services</span></span></p></td>
<td><p><span data-ttu-id="b74b9-133">Директор предоставляет веб-службы внутренним и внешним клиентам.</span><span class="sxs-lookup"><span data-stu-id="b74b9-133">The Director provides web services to internal and external clients.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b74b9-134">SIP/MTLS/TCP 5061</span><span class="sxs-lookup"><span data-stu-id="b74b9-134">SIP/MTLS/TCP 5061</span></span></p></td>
<td><p><span data-ttu-id="b74b9-135">Внутренний интерфейс пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="b74b9-135">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="b74b9-136">Режиссер</span><span class="sxs-lookup"><span data-stu-id="b74b9-136">Director</span></span></p></td>
<td><p><span data-ttu-id="b74b9-137">Обмен данными SIP от пограничного сервера к директоре и внешнему серверу.</span><span class="sxs-lookup"><span data-stu-id="b74b9-137">SIP communication from the Edge Server to the Director, and the Front End Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b74b9-138">MTLS/TCP/50001</span><span class="sxs-lookup"><span data-stu-id="b74b9-138">MTLS/TCP/50001</span></span></p></td>
<td><p><span data-ttu-id="b74b9-139">Любые</span><span class="sxs-lookup"><span data-stu-id="b74b9-139">Any</span></span></p></td>
<td><p><span data-ttu-id="b74b9-140">Внутренний интерфейс пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="b74b9-140">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="b74b9-141">Команды и сбор данных журнала для контроллера централизованной службы ведения журналов (ClsController.exe) или агента (ClasAgent.exe)</span><span class="sxs-lookup"><span data-stu-id="b74b9-141">Centralized Logging Service controller (ClsController.exe) or agent (ClasAgent.exe)commands and log collection</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b74b9-142">MTLS/TCP/50002</span><span class="sxs-lookup"><span data-stu-id="b74b9-142">MTLS/TCP/50002</span></span></p></td>
<td><p><span data-ttu-id="b74b9-143">Любые</span><span class="sxs-lookup"><span data-stu-id="b74b9-143">Any</span></span></p></td>
<td><p><span data-ttu-id="b74b9-144">Внутренний интерфейс пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="b74b9-144">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="b74b9-145">Команды и сбор данных журнала для контроллера централизованной службы ведения журналов (ClsController.exe) или агента (ClasAgent.exe)</span><span class="sxs-lookup"><span data-stu-id="b74b9-145">Centralized Logging Service controller (ClsController.exe) or agent (ClasAgent.exe)commands and log collection</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b74b9-146">MTLS/TCP/50003</span><span class="sxs-lookup"><span data-stu-id="b74b9-146">MTLS/TCP/50003</span></span></p></td>
<td><p><span data-ttu-id="b74b9-147">Любые</span><span class="sxs-lookup"><span data-stu-id="b74b9-147">Any</span></span></p></td>
<td><p><span data-ttu-id="b74b9-148">Внутренний интерфейс пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="b74b9-148">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="b74b9-149">Команды и сбор данных журнала для контроллера централизованной службы ведения журналов (ClsController.exe) или агента (ClasAgent.exe)</span><span class="sxs-lookup"><span data-stu-id="b74b9-149">Centralized Logging Service controller (ClsController.exe) or agent (ClasAgent.exe)commands and log collection</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

