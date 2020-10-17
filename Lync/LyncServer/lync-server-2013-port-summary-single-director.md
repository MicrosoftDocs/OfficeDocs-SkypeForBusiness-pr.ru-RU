---
title: 'Lync Server 2013: сводка по портам — один директор'
description: 'Lync Server 2013: сводка по портам — один директор.'
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
ms.openlocfilehash: a46e394121dbc7dd6158016d39511e9487cec1ff
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566375"
---
# <a name="port-summary---single-director-in-lync-server-2013"></a><span data-ttu-id="d8dd1-103">Сводка по портам — единственный директор в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d8dd1-103">Port summary - Single Director in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d8dd1-104">_**Последнее изменение темы:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="d8dd1-104">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="d8dd1-105">Требования к портам брандмауэра для одного директора состоят из портов, которые используются для установления связи с директором от внутреннего интерфейса или внутренней сети обратного прокси-сервера.</span><span class="sxs-lookup"><span data-stu-id="d8dd1-105">Firewall port requirements for a single Director consist of the ports that are used to establish communication with the Director from the internal interface or internal-facing network of the reverse proxy.</span></span> <span data-ttu-id="d8dd1-106">По умолчанию Microsoft Lync Server 2013 ожидает, что порты HTTP/TCP 8080 и HTTPS/TCP 4443 открываются из обратного прокси-сервера в директоре, а также интерфейсный пул и сервер переднего плана.</span><span class="sxs-lookup"><span data-stu-id="d8dd1-106">Microsoft Lync Server 2013 by default expects ports HTTP/TCP 8080 and HTTPS/TCP 4443 to be open from the reverse proxy to the Director, as well as the Front End pool and Front End Server.</span></span> <span data-ttu-id="d8dd1-107">Кроме того, должен быть обмен данными по протоколу SIP от внутреннего интерфейса пограничного сервера к директоре и к интерфейсному пулу и серверу переднего плана.</span><span class="sxs-lookup"><span data-stu-id="d8dd1-107">Additionally, there must be session initiation protocol (SIP) communication from the Edge Server internal interface to the Director and to the Front End pool and Front End Server.</span></span> <span data-ttu-id="d8dd1-108">Протокол SIP использует SIP/MTLS/TCP 5061 с пограничного сервера в интерфейсный пул и сервер переднего плана.</span><span class="sxs-lookup"><span data-stu-id="d8dd1-108">The SIP protocol uses SIP/MTLS/TCP 5061 from the Edge Server to the Front End pool and Front End Server.</span></span> <span data-ttu-id="d8dd1-109">Необходимо также создать правило, разрешающее передачу данных по протоколу SIP/MTLS/TCP 5061 из директора, интерфейсного пула и сервера переднего плана в внутренний интерфейс пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="d8dd1-109">A rule that allows SIP/MTLS/TCP 5061 communication from the Director, Front End pool and Front End Server to the Edge Server internal interface must be created as well.</span></span>

### <a name="single-director-ports-and-protocols-for-firewall-definitions"></a><span data-ttu-id="d8dd1-110">Порты и протоколы единого директора для определений брандмауэра</span><span class="sxs-lookup"><span data-stu-id="d8dd1-110">Single Director Ports and Protocols for Firewall Definitions</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d8dd1-111">Роль/протокол/TCP или UDP/порт</span><span class="sxs-lookup"><span data-stu-id="d8dd1-111">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="d8dd1-112">Исходный IP-адрес</span><span class="sxs-lookup"><span data-stu-id="d8dd1-112">Source IP address</span></span></th>
<th><span data-ttu-id="d8dd1-113">Конечный IP-адрес</span><span class="sxs-lookup"><span data-stu-id="d8dd1-113">Destination IP address</span></span></th>
<th><span data-ttu-id="d8dd1-114">Примечания</span><span class="sxs-lookup"><span data-stu-id="d8dd1-114">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d8dd1-115">HTTP/TCP 8080</span><span class="sxs-lookup"><span data-stu-id="d8dd1-115">HTTP/TCP 8080</span></span></p></td>
<td><p><span data-ttu-id="d8dd1-116">Внутренний интерфейс обратного прокси-сервера</span><span class="sxs-lookup"><span data-stu-id="d8dd1-116">Reverse proxy internal interface</span></span></p></td>
<td><p><span data-ttu-id="d8dd1-117">Директор</span><span class="sxs-lookup"><span data-stu-id="d8dd1-117">Director</span></span></p></td>
<td><p><span data-ttu-id="d8dd1-118">Полученная внешними сторонами обратного прокси-сервера, связь передается в директории и веб-службы сервера переднего плана</span><span class="sxs-lookup"><span data-stu-id="d8dd1-118">Initially received by the external side of the reverse proxy, the communication is sent on to the Director and Front End Server web services</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d8dd1-119">HTTPS/TCP 4443</span><span class="sxs-lookup"><span data-stu-id="d8dd1-119">HTTPS/TCP 4443</span></span></p></td>
<td><p><span data-ttu-id="d8dd1-120">Внутренний интерфейс обратного прокси-сервера</span><span class="sxs-lookup"><span data-stu-id="d8dd1-120">Reverse proxy internal interface</span></span></p></td>
<td><p><span data-ttu-id="d8dd1-121">Директор</span><span class="sxs-lookup"><span data-stu-id="d8dd1-121">Director</span></span></p></td>
<td><p><span data-ttu-id="d8dd1-122">Полученная внешними сторонами обратного прокси-сервера, связь передается в директории и веб-службы сервера переднего плана</span><span class="sxs-lookup"><span data-stu-id="d8dd1-122">Initially received by the external side of the reverse proxy, the communication is sent on to the Director and Front End Server web services</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d8dd1-123">HTTPS/TCP 444</span><span class="sxs-lookup"><span data-stu-id="d8dd1-123">HTTPS/TCP 444</span></span></p></td>
<td><p><span data-ttu-id="d8dd1-124">Директор</span><span class="sxs-lookup"><span data-stu-id="d8dd1-124">Director</span></span></p></td>
<td><p><span data-ttu-id="d8dd1-125">Сервер переднего плана или интерфейсный пул</span><span class="sxs-lookup"><span data-stu-id="d8dd1-125">Front End server or Front End pool</span></span></p></td>
<td><p><span data-ttu-id="d8dd1-126">Межсерверное взаимодействие между директором и сервером переднего плана</span><span class="sxs-lookup"><span data-stu-id="d8dd1-126">Inter-server communication between the Director and the Front End Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d8dd1-127">HTTP/TCP 80</span><span class="sxs-lookup"><span data-stu-id="d8dd1-127">HTTP/TCP 80</span></span></p></td>
<td><p><span data-ttu-id="d8dd1-128">Внутренние клиенты</span><span class="sxs-lookup"><span data-stu-id="d8dd1-128">Internal Clients</span></span></p></td>
<td><p><span data-ttu-id="d8dd1-129">Веб-службы режиссера</span><span class="sxs-lookup"><span data-stu-id="d8dd1-129">Director web services</span></span></p></td>
<td><p><span data-ttu-id="d8dd1-130">Директор предоставляет веб-службы внутренним и внешним клиентам.</span><span class="sxs-lookup"><span data-stu-id="d8dd1-130">The Director provides web services to internal and external clients.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d8dd1-131">HTTPS/TCP 443</span><span class="sxs-lookup"><span data-stu-id="d8dd1-131">HTTPS/TCP 443</span></span></p></td>
<td><p><span data-ttu-id="d8dd1-132">Внутренние клиенты</span><span class="sxs-lookup"><span data-stu-id="d8dd1-132">Internal Clients</span></span></p></td>
<td><p><span data-ttu-id="d8dd1-133">Веб-службы режиссера</span><span class="sxs-lookup"><span data-stu-id="d8dd1-133">Director web services</span></span></p></td>
<td><p><span data-ttu-id="d8dd1-134">Директор предоставляет веб-службы внутренним и внешним клиентам.</span><span class="sxs-lookup"><span data-stu-id="d8dd1-134">The Director provides web services to internal and external clients.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d8dd1-135">SIP/MTLS/TCP 5061</span><span class="sxs-lookup"><span data-stu-id="d8dd1-135">SIP/MTLS/TCP 5061</span></span></p></td>
<td><p><span data-ttu-id="d8dd1-136">Внутренний интерфейс пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="d8dd1-136">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="d8dd1-137">Директор</span><span class="sxs-lookup"><span data-stu-id="d8dd1-137">Director</span></span></p></td>
<td><p><span data-ttu-id="d8dd1-138">Обмен данными SIP от пограничного сервера к директоре и внешнему серверу.</span><span class="sxs-lookup"><span data-stu-id="d8dd1-138">SIP communication from the Edge Server to the Director, and the Front End Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d8dd1-139">MTLS/TCP/50001</span><span class="sxs-lookup"><span data-stu-id="d8dd1-139">MTLS/TCP/50001</span></span></p></td>
<td><p><span data-ttu-id="d8dd1-140">Любой</span><span class="sxs-lookup"><span data-stu-id="d8dd1-140">Any</span></span></p></td>
<td><p><span data-ttu-id="d8dd1-141">Внутренний интерфейс пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="d8dd1-141">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="d8dd1-142">Команды и сбор данных журнала для контроллера централизованной службы ведения журналов (ClsController.exe) или агента (ClasAgent.exe)</span><span class="sxs-lookup"><span data-stu-id="d8dd1-142">Centralized Logging Service controller (ClsController.exe) or agent (ClasAgent.exe)commands and log collection</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d8dd1-143">MTLS/TCP/50002</span><span class="sxs-lookup"><span data-stu-id="d8dd1-143">MTLS/TCP/50002</span></span></p></td>
<td><p><span data-ttu-id="d8dd1-144">Любой</span><span class="sxs-lookup"><span data-stu-id="d8dd1-144">Any</span></span></p></td>
<td><p><span data-ttu-id="d8dd1-145">Внутренний интерфейс пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="d8dd1-145">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="d8dd1-146">Команды и сбор данных журнала для контроллера централизованной службы ведения журналов (ClsController.exe) или агента (ClasAgent.exe)</span><span class="sxs-lookup"><span data-stu-id="d8dd1-146">Centralized Logging Service controller (ClsController.exe) or agent (ClasAgent.exe)commands and log collection</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d8dd1-147">MTLS/TCP/50003</span><span class="sxs-lookup"><span data-stu-id="d8dd1-147">MTLS/TCP/50003</span></span></p></td>
<td><p><span data-ttu-id="d8dd1-148">Любой</span><span class="sxs-lookup"><span data-stu-id="d8dd1-148">Any</span></span></p></td>
<td><p><span data-ttu-id="d8dd1-149">Внутренний интерфейс пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="d8dd1-149">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="d8dd1-150">Команды и сбор данных журнала для контроллера централизованной службы ведения журналов (ClsController.exe) или агента (ClasAgent.exe)</span><span class="sxs-lookup"><span data-stu-id="d8dd1-150">Centralized Logging Service controller (ClsController.exe) or agent (ClasAgent.exe)commands and log collection</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

