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
ms.openlocfilehash: 8515785f66101df3af0d7d35de565ba344e2b91a
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42139180"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="port-summary---single-director-in-lync-server-2013"></a><span data-ttu-id="ec275-102">Сводка по портам — единственный директор в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ec275-102">Port summary - Single Director in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ec275-103">_**Последнее изменение темы:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="ec275-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="ec275-104">Требования к портам брандмауэра для одного директора состоят из портов, которые используются для установления связи с директором от внутреннего интерфейса или внутренней сети обратного прокси-сервера.</span><span class="sxs-lookup"><span data-stu-id="ec275-104">Firewall port requirements for a single Director consist of the ports that are used to establish communication with the Director from the internal interface or internal-facing network of the reverse proxy.</span></span> <span data-ttu-id="ec275-105">По умолчанию Microsoft Lync Server 2013 ожидает, что порты HTTP/TCP 8080 и HTTPS/TCP 4443 открываются из обратного прокси-сервера в директоре, а также интерфейсный пул и сервер переднего плана.</span><span class="sxs-lookup"><span data-stu-id="ec275-105">Microsoft Lync Server 2013 by default expects ports HTTP/TCP 8080 and HTTPS/TCP 4443 to be open from the reverse proxy to the Director, as well as the Front End pool and Front End Server.</span></span> <span data-ttu-id="ec275-106">Кроме того, должен быть обмен данными по протоколу SIP от внутреннего интерфейса пограничного сервера к директоре и к интерфейсному пулу и серверу переднего плана.</span><span class="sxs-lookup"><span data-stu-id="ec275-106">Additionally, there must be session initiation protocol (SIP) communication from the Edge Server internal interface to the Director and to the Front End pool and Front End Server.</span></span> <span data-ttu-id="ec275-107">Протокол SIP использует SIP/MTLS/TCP 5061 с пограничного сервера в интерфейсный пул и сервер переднего плана.</span><span class="sxs-lookup"><span data-stu-id="ec275-107">The SIP protocol uses SIP/MTLS/TCP 5061 from the Edge Server to the Front End pool and Front End Server.</span></span> <span data-ttu-id="ec275-108">Необходимо также создать правило, разрешающее передачу данных по протоколу SIP/MTLS/TCP 5061 из директора, интерфейсного пула и сервера переднего плана в внутренний интерфейс пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="ec275-108">A rule that allows SIP/MTLS/TCP 5061 communication from the Director, Front End pool and Front End Server to the Edge Server internal interface must be created as well.</span></span>

### <a name="single-director-ports-and-protocols-for-firewall-definitions"></a><span data-ttu-id="ec275-109">Порты и протоколы единого директора для определений брандмауэра</span><span class="sxs-lookup"><span data-stu-id="ec275-109">Single Director Ports and Protocols for Firewall Definitions</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ec275-110">Роль/протокол/TCP или UDP/порт</span><span class="sxs-lookup"><span data-stu-id="ec275-110">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="ec275-111">Исходный IP-адрес</span><span class="sxs-lookup"><span data-stu-id="ec275-111">Source IP address</span></span></th>
<th><span data-ttu-id="ec275-112">Конечный IP-адрес</span><span class="sxs-lookup"><span data-stu-id="ec275-112">Destination IP address</span></span></th>
<th><span data-ttu-id="ec275-113">Notes</span><span class="sxs-lookup"><span data-stu-id="ec275-113">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ec275-114">HTTP/TCP 8080</span><span class="sxs-lookup"><span data-stu-id="ec275-114">HTTP/TCP 8080</span></span></p></td>
<td><p><span data-ttu-id="ec275-115">Внутренний интерфейс обратного прокси-сервера</span><span class="sxs-lookup"><span data-stu-id="ec275-115">Reverse proxy internal interface</span></span></p></td>
<td><p><span data-ttu-id="ec275-116">Режиссер</span><span class="sxs-lookup"><span data-stu-id="ec275-116">Director</span></span></p></td>
<td><p><span data-ttu-id="ec275-117">Полученная внешними сторонами обратного прокси-сервера, связь передается в директории и веб-службы сервера переднего плана</span><span class="sxs-lookup"><span data-stu-id="ec275-117">Initially received by the external side of the reverse proxy, the communication is sent on to the Director and Front End Server web services</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ec275-118">HTTPS/TCP 4443</span><span class="sxs-lookup"><span data-stu-id="ec275-118">HTTPS/TCP 4443</span></span></p></td>
<td><p><span data-ttu-id="ec275-119">Внутренний интерфейс обратного прокси-сервера</span><span class="sxs-lookup"><span data-stu-id="ec275-119">Reverse proxy internal interface</span></span></p></td>
<td><p><span data-ttu-id="ec275-120">Режиссер</span><span class="sxs-lookup"><span data-stu-id="ec275-120">Director</span></span></p></td>
<td><p><span data-ttu-id="ec275-121">Полученная внешними сторонами обратного прокси-сервера, связь передается в директории и веб-службы сервера переднего плана</span><span class="sxs-lookup"><span data-stu-id="ec275-121">Initially received by the external side of the reverse proxy, the communication is sent on to the Director and Front End Server web services</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ec275-122">HTTPS/TCP 444</span><span class="sxs-lookup"><span data-stu-id="ec275-122">HTTPS/TCP 444</span></span></p></td>
<td><p><span data-ttu-id="ec275-123">Режиссер</span><span class="sxs-lookup"><span data-stu-id="ec275-123">Director</span></span></p></td>
<td><p><span data-ttu-id="ec275-124">Сервер переднего плана или интерфейсный пул</span><span class="sxs-lookup"><span data-stu-id="ec275-124">Front End server or Front End pool</span></span></p></td>
<td><p><span data-ttu-id="ec275-125">Межсерверное взаимодействие между директором и сервером переднего плана</span><span class="sxs-lookup"><span data-stu-id="ec275-125">Inter-server communication between the Director and the Front End Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ec275-126">HTTP/TCP 80</span><span class="sxs-lookup"><span data-stu-id="ec275-126">HTTP/TCP 80</span></span></p></td>
<td><p><span data-ttu-id="ec275-127">Внутренние клиенты</span><span class="sxs-lookup"><span data-stu-id="ec275-127">Internal Clients</span></span></p></td>
<td><p><span data-ttu-id="ec275-128">Веб-службы режиссера</span><span class="sxs-lookup"><span data-stu-id="ec275-128">Director web services</span></span></p></td>
<td><p><span data-ttu-id="ec275-129">Директор предоставляет веб-службы внутренним и внешним клиентам.</span><span class="sxs-lookup"><span data-stu-id="ec275-129">The Director provides web services to internal and external clients.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ec275-130">HTTPS/TCP 443</span><span class="sxs-lookup"><span data-stu-id="ec275-130">HTTPS/TCP 443</span></span></p></td>
<td><p><span data-ttu-id="ec275-131">Внутренние клиенты</span><span class="sxs-lookup"><span data-stu-id="ec275-131">Internal Clients</span></span></p></td>
<td><p><span data-ttu-id="ec275-132">Веб-службы режиссера</span><span class="sxs-lookup"><span data-stu-id="ec275-132">Director web services</span></span></p></td>
<td><p><span data-ttu-id="ec275-133">Директор предоставляет веб-службы внутренним и внешним клиентам.</span><span class="sxs-lookup"><span data-stu-id="ec275-133">The Director provides web services to internal and external clients.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ec275-134">SIP/MTLS/TCP 5061</span><span class="sxs-lookup"><span data-stu-id="ec275-134">SIP/MTLS/TCP 5061</span></span></p></td>
<td><p><span data-ttu-id="ec275-135">Внутренний интерфейс пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="ec275-135">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="ec275-136">Режиссер</span><span class="sxs-lookup"><span data-stu-id="ec275-136">Director</span></span></p></td>
<td><p><span data-ttu-id="ec275-137">Обмен данными SIP от пограничного сервера к директоре и внешнему серверу.</span><span class="sxs-lookup"><span data-stu-id="ec275-137">SIP communication from the Edge Server to the Director, and the Front End Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ec275-138">MTLS/TCP/50001</span><span class="sxs-lookup"><span data-stu-id="ec275-138">MTLS/TCP/50001</span></span></p></td>
<td><p><span data-ttu-id="ec275-139">Любые</span><span class="sxs-lookup"><span data-stu-id="ec275-139">Any</span></span></p></td>
<td><p><span data-ttu-id="ec275-140">Внутренний интерфейс пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="ec275-140">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="ec275-141">Команды и сбор данных журнала для контроллера централизованной службы ведения журналов (ClsController.exe) или агента (ClasAgent.exe)</span><span class="sxs-lookup"><span data-stu-id="ec275-141">Centralized Logging Service controller (ClsController.exe) or agent (ClasAgent.exe)commands and log collection</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ec275-142">MTLS/TCP/50002</span><span class="sxs-lookup"><span data-stu-id="ec275-142">MTLS/TCP/50002</span></span></p></td>
<td><p><span data-ttu-id="ec275-143">Любые</span><span class="sxs-lookup"><span data-stu-id="ec275-143">Any</span></span></p></td>
<td><p><span data-ttu-id="ec275-144">Внутренний интерфейс пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="ec275-144">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="ec275-145">Команды и сбор данных журнала для контроллера централизованной службы ведения журналов (ClsController.exe) или агента (ClasAgent.exe)</span><span class="sxs-lookup"><span data-stu-id="ec275-145">Centralized Logging Service controller (ClsController.exe) or agent (ClasAgent.exe)commands and log collection</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ec275-146">MTLS/TCP/50003</span><span class="sxs-lookup"><span data-stu-id="ec275-146">MTLS/TCP/50003</span></span></p></td>
<td><p><span data-ttu-id="ec275-147">Любые</span><span class="sxs-lookup"><span data-stu-id="ec275-147">Any</span></span></p></td>
<td><p><span data-ttu-id="ec275-148">Внутренний интерфейс пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="ec275-148">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="ec275-149">Команды и сбор данных журнала для контроллера централизованной службы ведения журналов (ClsController.exe) или агента (ClasAgent.exe)</span><span class="sxs-lookup"><span data-stu-id="ec275-149">Centralized Logging Service controller (ClsController.exe) or agent (ClasAgent.exe)commands and log collection</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

