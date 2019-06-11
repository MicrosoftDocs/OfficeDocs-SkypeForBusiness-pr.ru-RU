---
title: Сводка по портам — масштабируемая консолидированная пограничная топология с аппаратными балансировщиками нагрузки
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Port summary - Scaled consolidated edge with hardware load balancers
ms:assetid: 91213b1e-f875-464b-83e8-fe3a351595a4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398739(v=OCS.15)
ms:contentKeyID: 48184841
ms.date: 04/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 60250db155922999ce677248a41c3f4158aba466
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34824346"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="port-summary---scaled-consolidated-edge-with-hardware-load-balancers-in-lync-server-2013"></a><span data-ttu-id="e2b3b-102">Сводка по портам — масштабируемая консолидированная пограничная топология с аппаратными балансировщиками нагрузки в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e2b3b-102">Port summary - Scaled consolidated edge with hardware load balancers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e2b3b-103">_**Тема последнего изменения:** 2015-04-27_</span><span class="sxs-lookup"><span data-stu-id="e2b3b-103">_**Topic Last Modified:** 2015-04-27_</span></span>

<span data-ttu-id="e2b3b-104">Функция пограничного сервера Lync Server 2013, описанная в этой архитектуре сценариев, очень похожа на ту, что была реализована в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="e2b3b-104">The Lync Server 2013, Edge Server functionality described in this scenario architecture is very similar to what was implemented in Lync Server 2010.</span></span> <span data-ttu-id="e2b3b-105">Наиболее заметным дополнением является порт **5269 на TCP** для протокола расширенной обработки сообщений и присутствия (КСМПП).</span><span class="sxs-lookup"><span data-stu-id="e2b3b-105">The most noticeable addition is the port **5269 over TCP** entry for the extensible messaging and presence protocol (XMPP).</span></span> <span data-ttu-id="e2b3b-106">Lync Server 2013 (при необходимости) можно развернуть прокси-сервер КСМПП на пограничном или пограничном пуле, а также на сервере шлюзов КСМПП на сервере переднего плана или в пуле внешних интерфейсов.</span><span class="sxs-lookup"><span data-stu-id="e2b3b-106">Lync Server 2013 optionally deploys an XMPP proxy on the Edge Server or Edge pool and the XMPP gateway server on the Front End Server or Front End pool.</span></span>

<span data-ttu-id="e2b3b-107">В дополнение к протоколу IPv4, пограничный сервер теперь поддерживает IPv6.</span><span class="sxs-lookup"><span data-stu-id="e2b3b-107">In addition to IPv4, the Edge Server now supports IPv6.</span></span> <span data-ttu-id="e2b3b-108">Для ясности в сценариях используется только протокол IPv4.</span><span class="sxs-lookup"><span data-stu-id="e2b3b-108">For clarity, only IPv4 is used in the scenarios.</span></span>

<span data-ttu-id="e2b3b-109">**Масштабируемый Объединенный край с использованием аппаратной балансировки нагрузки**</span><span class="sxs-lookup"><span data-stu-id="e2b3b-109">**Scaled Consolidated Edge using Hardware Load Balancing**</span></span>

<span data-ttu-id="e2b3b-110">![Порты и протоколы периметра пограничного сервера] (images/Gg398739.063f7dd1-16db-4cc7-8708-bca9bc41184d(OCS.15).jpg "Порты и протоколы периметра пограничного сервера")</span><span class="sxs-lookup"><span data-stu-id="e2b3b-110">![Edge Server Perimeter Network ports and protocols](images/Gg398739.063f7dd1-16db-4cc7-8708-bca9bc41184d(OCS.15).jpg "Edge Server Perimeter Network ports and protocols")</span></span>

<div>

## <a name="port-and-protocol-details"></a><span data-ttu-id="e2b3b-111">Сведения о портах и протоколах</span><span class="sxs-lookup"><span data-stu-id="e2b3b-111">Port and Protocol Details</span></span>

<span data-ttu-id="e2b3b-112">Рекомендуется открывать только порты, необходимые для поддержки функций, для которых предоставляется внешний доступ.</span><span class="sxs-lookup"><span data-stu-id="e2b3b-112">It is recommended that you open only the ports required to support the functionality for which you are providing external access.</span></span>

<span data-ttu-id="e2b3b-113">Для удаленного доступа к работе в любой службе пограничного сервера необходимо, чтобы трафик SIP был в направлении на один и тот же трафик по внешнему потоку, как показано на рисунке входящего и исходящего трафика пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="e2b3b-113">For remote access to work for any edge service, it is mandatory that SIP traffic is allowed to flow bi-directionally as shown in the Inbound/Outbound edge traffic figure.</span></span> <span data-ttu-id="e2b3b-114">Другими словами, Обмен сообщениями SIP и из службы Edge для Access осуществляется в обмене мгновенными сообщениями, присутствии, веб-конференциях, аудио-и видеосвязи (A/V) и Федерации.</span><span class="sxs-lookup"><span data-stu-id="e2b3b-114">Stated another way, the SIP messaging to and from the Access Edge service is involved in instant messaging (IM), presence, web conferencing, audio/video (A/V) and federation.</span></span>

### <a name="firewall-summary-for-scaled-consolidated-edge-hardware-load-balanced-external-interface--node-1-and-node-2-example"></a><span data-ttu-id="e2b3b-115">Сводка по межсетевому экрану для масштабируемой консолидированной границы, аппаратной балансировки нагрузки: внешний интерфейс — узел 1 и узел 2 (пример)</span><span class="sxs-lookup"><span data-stu-id="e2b3b-115">Firewall Summary for Scaled Consolidated Edge, Hardware Load Balanced: External Interface – Node 1 and Node 2 (Example)</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e2b3b-116">Role/Protocol/TCP/UDP/порт</span><span class="sxs-lookup"><span data-stu-id="e2b3b-116">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="e2b3b-117">IP-адрес источника</span><span class="sxs-lookup"><span data-stu-id="e2b3b-117">Source IP address</span></span></th>
<th><span data-ttu-id="e2b3b-118">IP-адрес назначения</span><span class="sxs-lookup"><span data-stu-id="e2b3b-118">Destination IP address</span></span></th>
<th><span data-ttu-id="e2b3b-119">Примечания.</span><span class="sxs-lookup"><span data-stu-id="e2b3b-119">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e2b3b-120">Access/HTTP/TCP/80</span><span class="sxs-lookup"><span data-stu-id="e2b3b-120">Access/HTTP/TCP/80</span></span></p></td>
<td><p><span data-ttu-id="e2b3b-121">Общедоступный IP-адрес службы пограничного доступа к серверу Edge</span><span class="sxs-lookup"><span data-stu-id="e2b3b-121">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="e2b3b-122">Любой</span><span class="sxs-lookup"><span data-stu-id="e2b3b-122">Any</span></span></p></td>
<td><p><span data-ttu-id="e2b3b-123">Проверка отзыва сертификатов и получения CRL</span><span class="sxs-lookup"><span data-stu-id="e2b3b-123">Certificate revocation/CRL check and retrieval</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e2b3b-124">Access/DNS/TCP/53</span><span class="sxs-lookup"><span data-stu-id="e2b3b-124">Access/DNS/TCP/53</span></span></p></td>
<td><p><span data-ttu-id="e2b3b-125">Общедоступный IP-адрес службы пограничного доступа к серверу Edge</span><span class="sxs-lookup"><span data-stu-id="e2b3b-125">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="e2b3b-126">Любой</span><span class="sxs-lookup"><span data-stu-id="e2b3b-126">Any</span></span></p></td>
<td><p><span data-ttu-id="e2b3b-127">Запрос DNS по протоколу TCP</span><span class="sxs-lookup"><span data-stu-id="e2b3b-127">DNS query over TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e2b3b-128">Access/DNS/UDP/53</span><span class="sxs-lookup"><span data-stu-id="e2b3b-128">Access/DNS/UDP/53</span></span></p></td>
<td><p><span data-ttu-id="e2b3b-129">Общедоступный IP-адрес службы пограничного доступа к серверу Edge</span><span class="sxs-lookup"><span data-stu-id="e2b3b-129">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="e2b3b-130">Любой</span><span class="sxs-lookup"><span data-stu-id="e2b3b-130">Any</span></span></p></td>
<td><p><span data-ttu-id="e2b3b-131">Запрос DNS по протоколу UDP</span><span class="sxs-lookup"><span data-stu-id="e2b3b-131">DNS query over UDP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e2b3b-132">A/V/RTP/TCP/50000-59,999</span><span class="sxs-lookup"><span data-stu-id="e2b3b-132">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="e2b3b-133">IP-адрес службы пограничного сервера A/V</span><span class="sxs-lookup"><span data-stu-id="e2b3b-133">Edge Server A/V Edge service IP address</span></span></p></td>
<td><p><span data-ttu-id="e2b3b-134">Любой</span><span class="sxs-lookup"><span data-stu-id="e2b3b-134">Any</span></span></p></td>
<td><p><span data-ttu-id="e2b3b-135">Требуется для Федерации с партнерами, работающими под управлением Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 и Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e2b3b-135">Required for federating with partners running Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 and Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e2b3b-136">A/V/RTP/UDP/50000-59,999</span><span class="sxs-lookup"><span data-stu-id="e2b3b-136">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="e2b3b-137">Общедоступный IP-адрес службы пограничного сервера A/V</span><span class="sxs-lookup"><span data-stu-id="e2b3b-137">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="e2b3b-138">Любой</span><span class="sxs-lookup"><span data-stu-id="e2b3b-138">Any</span></span></p></td>
<td><p><span data-ttu-id="e2b3b-139">Требуется только для Федерации с партнерами, работающими под управлением Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="e2b3b-139">Required only for federation with partners running Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e2b3b-140">A/V/RTP/TCP/50000-59,999</span><span class="sxs-lookup"><span data-stu-id="e2b3b-140">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="e2b3b-141">Любой</span><span class="sxs-lookup"><span data-stu-id="e2b3b-141">Any</span></span></p></td>
<td><p><span data-ttu-id="e2b3b-142">Общедоступный IP-адрес службы пограничного сервера A/V</span><span class="sxs-lookup"><span data-stu-id="e2b3b-142">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="e2b3b-143">Требуется только для Федерации с партнерами, работающими под управлением Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="e2b3b-143">Required only for federation with partners running Office Communications Server 2007</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e2b3b-144">A/V/RTP/UDP/50000-59,999</span><span class="sxs-lookup"><span data-stu-id="e2b3b-144">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="e2b3b-145">Любой</span><span class="sxs-lookup"><span data-stu-id="e2b3b-145">Any</span></span></p></td>
<td><p><span data-ttu-id="e2b3b-146">Общедоступный IP-адрес службы пограничного сервера A/V</span><span class="sxs-lookup"><span data-stu-id="e2b3b-146">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="e2b3b-147">Требуется только для Федерации с партнерами, работающими под управлением Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="e2b3b-147">Required only for federation with partners running Office Communications Server 2007</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e2b3b-148">A/V/STUN, МСТУРН/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="e2b3b-148">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="e2b3b-149">Общедоступный IP-адрес службы пограничного сервера A/V</span><span class="sxs-lookup"><span data-stu-id="e2b3b-149">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="e2b3b-150">Любой</span><span class="sxs-lookup"><span data-stu-id="e2b3b-150">Any</span></span></p></td>
<td><p><span data-ttu-id="e2b3b-151">3478 Outbound используется для определения версии пограничного сервера, с которым обменивается данными Lync Server, а также для мультимедийного трафика от пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="e2b3b-151">3478 outbound is used to determine the version of Edge Server that Lync Server is communicating with and also for media traffic from Edge Server-to-Edge Server.</span></span> <span data-ttu-id="e2b3b-152">Требуется для Федерации с Lync Server 2010, Windows Live Messenger и Office Communications Server 2007 R2, а также в том случае, если в компании развернуты несколько пулов Edge.</span><span class="sxs-lookup"><span data-stu-id="e2b3b-152">Required for federation with Lync Server 2010, Windows Live Messenger, and Office Communications Server 2007 R2, and also if multiple Edge pools are deployed within a company.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e2b3b-153">A/V/STUN, МСТУРН/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="e2b3b-153">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="e2b3b-154">Любой</span><span class="sxs-lookup"><span data-stu-id="e2b3b-154">Any</span></span></p></td>
<td><p><span data-ttu-id="e2b3b-155">Общедоступный IP-адрес службы пограничного сервера A/V</span><span class="sxs-lookup"><span data-stu-id="e2b3b-155">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="e2b3b-156">STUN/отключите согласование кандидатов по протоколу UDP/3478</span><span class="sxs-lookup"><span data-stu-id="e2b3b-156">STUN/TURN negotiation of candidates over UDP/3478</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e2b3b-157">A/V/STUN, МСТУРН/TCP/443</span><span class="sxs-lookup"><span data-stu-id="e2b3b-157">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="e2b3b-158">Любой</span><span class="sxs-lookup"><span data-stu-id="e2b3b-158">Any</span></span></p></td>
<td><p><span data-ttu-id="e2b3b-159">Общедоступный IP-адрес службы пограничного сервера A/V</span><span class="sxs-lookup"><span data-stu-id="e2b3b-159">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="e2b3b-160">STUN/отключите согласование кандидатов по протоколу TCP/443</span><span class="sxs-lookup"><span data-stu-id="e2b3b-160">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e2b3b-161">A/V/STUN, МСТУРН/TCP/443</span><span class="sxs-lookup"><span data-stu-id="e2b3b-161">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="e2b3b-162">Общедоступный IP-адрес службы пограничного сервера A/V</span><span class="sxs-lookup"><span data-stu-id="e2b3b-162">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="e2b3b-163">Любой</span><span class="sxs-lookup"><span data-stu-id="e2b3b-163">Any</span></span></p></td>
<td><p><span data-ttu-id="e2b3b-164">STUN/отключите согласование кандидатов по протоколу TCP/443</span><span class="sxs-lookup"><span data-stu-id="e2b3b-164">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="firewall-summary-for-scaled-consolidated-edge-hardware-load-balanced-internal-interface-node-1-and-node-2"></a><span data-ttu-id="e2b3b-165">Сводка по межсетевому экрану для масштабируемой консолидированной границы, аппаратной балансировки нагрузки: внутренний интерфейс, узел 1 и узел 2</span><span class="sxs-lookup"><span data-stu-id="e2b3b-165">Firewall Summary for Scaled Consolidated Edge, Hardware Load Balanced: Internal Interface Node 1 and Node 2</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e2b3b-166">Role/Protocol/TCP/UDP/порт</span><span class="sxs-lookup"><span data-stu-id="e2b3b-166">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="e2b3b-167">IP-адрес источника</span><span class="sxs-lookup"><span data-stu-id="e2b3b-167">Source IP address</span></span></th>
<th><span data-ttu-id="e2b3b-168">IP-адрес назначения</span><span class="sxs-lookup"><span data-stu-id="e2b3b-168">Destination IP address</span></span></th>
<th><span data-ttu-id="e2b3b-169">Примечания.</span><span class="sxs-lookup"><span data-stu-id="e2b3b-169">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e2b3b-170">КСМПП/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="e2b3b-170">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="e2b3b-171">Any (может быть определено как адрес сервера переднего плана или виртуальный IP-адрес пула переднего плана, на котором запущена служба шлюза КСМПП)</span><span class="sxs-lookup"><span data-stu-id="e2b3b-171">Any (can be defined as Front End Server address, or Front End pool virtual IP address running the XMPP Gateway service)</span></span></p></td>
<td><p><span data-ttu-id="e2b3b-172">Внутренний интерфейс пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="e2b3b-172">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="e2b3b-173">Исходящий трафик КСМПП от службы шлюза КСМПП, работающей на сервере переднего плана или в пуле внешних интерфейсов</span><span class="sxs-lookup"><span data-stu-id="e2b3b-173">Outbound XMPP traffic from XMPP Gateway service running on Front End Server or Front End pool</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e2b3b-174">HTTPS/TCP/4443</span><span class="sxs-lookup"><span data-stu-id="e2b3b-174">HTTPS/TCP/4443</span></span></p></td>
<td><p><span data-ttu-id="e2b3b-175">Any (может быть задан как IP-адрес серверного сервера переднего плана или пул, хранящий центральное хранилище управления).</span><span class="sxs-lookup"><span data-stu-id="e2b3b-175">Any (can be defined as the Front End Server server IP or pool that holds the Central Management store)</span></span></p></td>
<td><p><span data-ttu-id="e2b3b-176">Внутренний интерфейс пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="e2b3b-176">Edge Server Internal interface</span></span></p></td>
<td><p><span data-ttu-id="e2b3b-177">Репликация изменений из хранилища центрального управления на пограничный сервер</span><span class="sxs-lookup"><span data-stu-id="e2b3b-177">Replication of changes from the Central Management store to the Edge Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e2b3b-178">PSOM/MTLS/TCP/8057</span><span class="sxs-lookup"><span data-stu-id="e2b3b-178">PSOM/MTLS/TCP/8057</span></span></p></td>
<td><p><span data-ttu-id="e2b3b-179">Any (может быть определено как режиссер (IP-адрес), IP-адрес внешнего сервера или пул виртуальных IP-адресов.</span><span class="sxs-lookup"><span data-stu-id="e2b3b-179">Any (can be defined as Director IP, Front End Server IP or Pool virtual IP)</span></span></p></td>
<td><p><span data-ttu-id="e2b3b-180">Внутренний интерфейс пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="e2b3b-180">Edge Server Internal interface</span></span></p></td>
<td><p><span data-ttu-id="e2b3b-181">Трафик веб-конференций из внутреннего развертывания в внутренний интерфейс пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="e2b3b-181">Web conferencing traffic from Internal deployment to Internal Edge Server interface</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e2b3b-182">STUN/МСТУРН/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="e2b3b-182">STUN/MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="e2b3b-183">Any (может быть определено как режиссер (IP-адрес), IP-адрес внешнего сервера или пул виртуальных IP-адресов.</span><span class="sxs-lookup"><span data-stu-id="e2b3b-183">Any (can be defined as Director IP, Front End Server IP or Pool virtual IP)</span></span></p></td>
<td><p><span data-ttu-id="e2b3b-184">Внутренний интерфейс пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="e2b3b-184">Edge Server Internal interface</span></span></p></td>
<td><p><span data-ttu-id="e2b3b-185">Предпочтительный путь для передачи мультимедиа между внутренними и внешними пользователями, бесперебойно работающем устройстве филиалов или бесперебойно работающем сервере филиала</span><span class="sxs-lookup"><span data-stu-id="e2b3b-185">Preferred path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e2b3b-186">STUN/МСТУРН/TCP/443</span><span class="sxs-lookup"><span data-stu-id="e2b3b-186">STUN/MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="e2b3b-187">Any (может быть определено как режиссер (IP-адрес), IP-адрес внешнего сервера или пул виртуальных IP-адресов.</span><span class="sxs-lookup"><span data-stu-id="e2b3b-187">Any (can be defined as Director IP, Front End Server IP or Pool virtual IP)</span></span></p></td>
<td><p><span data-ttu-id="e2b3b-188">Внутренний интерфейс пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="e2b3b-188">Edge Server Internal interface</span></span></p></td>
<td><p><span data-ttu-id="e2b3b-189">Резервный путь для передачи мультимедиа между внутренними и внешними пользователями, бесперебойно работающее устройство филиала или бесперебойный сервер филиала, если не удается установить UDP-связь, используется протокол TCP для обмена файлами и демонстрации рабочего стола</span><span class="sxs-lookup"><span data-stu-id="e2b3b-189">Fallback path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server if UDP communication cannot be established, TCP is used for file transfer and desktop sharing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e2b3b-190">MTLS/TCP/50001</span><span class="sxs-lookup"><span data-stu-id="e2b3b-190">MTLS/TCP/50001</span></span></p></td>
<td><p><span data-ttu-id="e2b3b-191">Любой</span><span class="sxs-lookup"><span data-stu-id="e2b3b-191">Any</span></span></p></td>
<td><p><span data-ttu-id="e2b3b-192">Внутренний интерфейс пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="e2b3b-192">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="e2b3b-193">Централизованное ведение журналов с помощью команд командной строки Lync Server Management Shell и централизованных служб ведения журнала, Клсконтроллер (Командная строка Клсконтроллер. exe) или агента (Клсажент. exe) и коллекции журналов</span><span class="sxs-lookup"><span data-stu-id="e2b3b-193">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e2b3b-194">MTLS/TCP/50002</span><span class="sxs-lookup"><span data-stu-id="e2b3b-194">MTLS/TCP/50002</span></span></p></td>
<td><p><span data-ttu-id="e2b3b-195">Любой</span><span class="sxs-lookup"><span data-stu-id="e2b3b-195">Any</span></span></p></td>
<td><p><span data-ttu-id="e2b3b-196">Внутренний интерфейс пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="e2b3b-196">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="e2b3b-197">Централизованное ведение журналов с помощью команд командной строки Lync Server Management Shell и централизованных служб ведения журнала, Клсконтроллер (Командная строка Клсконтроллер. exe) или агента (Клсажент. exe) и коллекции журналов</span><span class="sxs-lookup"><span data-stu-id="e2b3b-197">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e2b3b-198">MTLS/TCP/50003</span><span class="sxs-lookup"><span data-stu-id="e2b3b-198">MTLS/TCP/50003</span></span></p></td>
<td><p><span data-ttu-id="e2b3b-199">Любой</span><span class="sxs-lookup"><span data-stu-id="e2b3b-199">Any</span></span></p></td>
<td><p><span data-ttu-id="e2b3b-200">Внутренний интерфейс пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="e2b3b-200">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="e2b3b-201">Централизованное ведение журналов с помощью команд командной строки Lync Server Management Shell и централизованных служб ведения журнала, Клсконтроллер (Командная строка Клсконтроллер. exe) или агента (Клсажент. exe) и коллекции журналов</span><span class="sxs-lookup"><span data-stu-id="e2b3b-201">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="e2b3b-202">При развертывании для обеспечения доступности и балансировки нагрузки для Lync Server аппаратные подсистемы балансировки нагрузки предъявляют определенные требования.</span><span class="sxs-lookup"><span data-stu-id="e2b3b-202">Hardware load balancers have specific requirements when deployed to provide availability and load balancing for Lync Server.</span></span> <span data-ttu-id="e2b3b-203">Требования определяются на приведенных ниже рисунках и таблицах.</span><span class="sxs-lookup"><span data-stu-id="e2b3b-203">The requirements are defined in the following figure and tables.</span></span> <span data-ttu-id="e2b3b-204">Сторонние производители могут использовать различные термины, которые определяются в соответствии с требованиями.</span><span class="sxs-lookup"><span data-stu-id="e2b3b-204">Third party vendors may use different terminology for the requirements defined here.</span></span> <span data-ttu-id="e2b3b-205">Вам потребуется сопоставить требования к серверу Lync Server функциям и параметрам конфигурации, предоставляемым поставщиком подсистемы балансировки нагрузки для оборудования.</span><span class="sxs-lookup"><span data-stu-id="e2b3b-205">It will be necessary to map the requirements of Lync Server to the features and configuration options provided by your hardware load balancer vendor.</span></span>

<span data-ttu-id="e2b3b-206">При настройке подсистемы балансировки нагрузки для оборудования учитывайте следующие требования:</span><span class="sxs-lookup"><span data-stu-id="e2b3b-206">When configuring hardware load balancers, consider the following requirements:</span></span>

  - <span data-ttu-id="e2b3b-207">Для службы пограничного сервера Access и службы Edge для веб-конференций можно настроить трансляцию сетевых адресов (SNAT) на оборудовании (ХЛБ).</span><span class="sxs-lookup"><span data-stu-id="e2b3b-207">Source Network Address Translation (SNAT) can be configured on the hardware load balancer (HLB) for Access Edge service and Web Conferencing Edge service</span></span>

  - <span data-ttu-id="e2b3b-208">Не удается настроить SNAT в службе Edge/V: служба Edge может отвечать на запросы, не являющиеся виртуальным IP-адресом ХЛБ (VIP), для простого обхода UDP по NAT (STUN)/траверсал с помощью ретрансляции NAT (переключение)/федератион (ФТУРН) для правильной работы</span><span class="sxs-lookup"><span data-stu-id="e2b3b-208">SNAT cannot be configured on the A/V Edge service– the A/V Edge service must respond with the real server address, not the HLB virtual IP (VIP), for simple traversal of UDP over NAT (STUN)/traversal using relay NAT (TURN)/federation TURN (FTURN) to work properly</span></span>
    
      - <span data-ttu-id="e2b3b-209">Если клиент отправляет запрос на ХЛБ, ответ должен возвращаться из IP-адреса ХЛБ</span><span class="sxs-lookup"><span data-stu-id="e2b3b-209">If the client sends a request to the HLB, the response must come back from the HLB VIP</span></span>
    
      - <span data-ttu-id="e2b3b-210">Если клиент отправляет запрос на ребро, ответ должен возвращаться из IP-адреса Edge.</span><span class="sxs-lookup"><span data-stu-id="e2b3b-210">If the client sends a request to the Edge, the response must come back from the Edge IP</span></span>

  - <span data-ttu-id="e2b3b-211">Общедоступные IP-адреса используются на каждом интерфейсе сервера и виртуальных IP-адресах в ХЛБ, а требования к общедоступной сети — в N + 1, где есть общедоступный IP-адрес для каждого сервера реального времени и один для каждого из ХЛБ VIP.</span><span class="sxs-lookup"><span data-stu-id="e2b3b-211">Public IP addresses are used on each server interface and on the VIPs of the HLB, and your public IP address requirements are N+1, where there is a public IP address for each real server interface and one for each HLB VIP.</span></span> <span data-ttu-id="e2b3b-212">Если у вас есть 2 пограничные сервера в пуле, это приводит к 9 общим IP-адресам, где 3 используются для VIP ХЛБ и для каждого интерфейса пограничного сервера (общее количество шести для серверов).</span><span class="sxs-lookup"><span data-stu-id="e2b3b-212">Where you have 2 Edge servers in the pool, this results in 9 public IP addresses, where 3 are used for the HLB VIPs, and one for each Edge server interface (a total of six for the servers)</span></span>

  - <span data-ttu-id="e2b3b-213">Для службы пограничного доступа и службы Edge для веб-конференций (и с помощью NAT на ХЛБ) клиент обращается к VIP, IP-адрес источника меняется с клиента на собственный IP-адрес.</span><span class="sxs-lookup"><span data-stu-id="e2b3b-213">For the Access Edge service and Web Conferencing Edge service, (and using NAT on the HLB) the client contacts the VIP, the VIP changes the source IP address from the client to its own IP address.</span></span> <span data-ttu-id="e2b3b-214">Интерфейс сервера отправляет в VIP-сервер адрес, возвращенный по протоколу IP, VIP изменяет адрес источника из IP адресного интерфейса сервера и направляет пакет клиенту.</span><span class="sxs-lookup"><span data-stu-id="e2b3b-214">The server interface addresses the return address to the VIP, the VIP changes the source address from the server interface IP address and sends the packet to the client</span></span>

  - <span data-ttu-id="e2b3b-215">Для службы EDGE (/V) VIP не должен изменять IP-адрес источника, а реальный адрес сервера возвращается клиенту напрямую — вы не можете настроить NAT для трафика ХЛБ для AV</span><span class="sxs-lookup"><span data-stu-id="e2b3b-215">For the A/V Edge service, the VIP must NOT change the source IP address, and the real server address is returned to the client directly – you cannot configure NAT on the HLB for AV traffic</span></span>
    
      - <span data-ttu-id="e2b3b-216">Если клиент отправляет запрос в ХЛБ VIP, ответ должен возвращаться из виртуального IP-адреса ХЛБ</span><span class="sxs-lookup"><span data-stu-id="e2b3b-216">If the client sends a request to the HLB VIP, the response must come back from the HLB VIP</span></span>
    
      - <span data-ttu-id="e2b3b-217">Если клиент отправляет запрос на Граничный IP-адрес, ответ должен возвращаться из IP-адреса Edge.</span><span class="sxs-lookup"><span data-stu-id="e2b3b-217">If the client sends a request to the Edge IP, the response must come back from the Edge IP</span></span>

  - <span data-ttu-id="e2b3b-218">Для протоколов AV Внешний брандмауэр сохранит общедоступный IP-адрес сервера для всех пакетов.</span><span class="sxs-lookup"><span data-stu-id="e2b3b-218">For AV, the external firewall will retain the real server public IP address for all packets</span></span>

  - <span data-ttu-id="e2b3b-219">После того как вы установили подключение к службе EDGE, клиент может связаться с реальным сервером, а не ХЛБ</span><span class="sxs-lookup"><span data-stu-id="e2b3b-219">Once established, client to A/V Edge service communication is to the real server, not the HLB</span></span>

  - <span data-ttu-id="e2b3b-220">Внутренний доступ к внутренним серверам и клиентам должен маршрутизироваться, а для всех внутренних сетей, которые размещаются на серверах или клиентах, должны быть установлены постоянные маршруты.</span><span class="sxs-lookup"><span data-stu-id="e2b3b-220">Internal edge to internal servers and clients must be routed, and persistent routes are set for all internal networks that host servers or clients</span></span>

  - <span data-ttu-id="e2b3b-221">Виртуальные IP-адреса службы пограничного доступа ХЛБ будут выступать в качестве шлюза по умолчанию для каждого интерфейса пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="e2b3b-221">The HLB Access Edge service VIP will act as the default gateway for each Edge server interface</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="e2b3b-222">Для получения дополнительной информации о планировании и функциональных возможностях NAT ознакомьтесь с требованиями к подсистеме <A href="lync-server-2013-hardware-load-balancer-requirements.md">балансировки нагрузки для Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="e2b3b-222">For further information on NAT planning and functionality, please refer to <A href="lync-server-2013-hardware-load-balancer-requirements.md">Hardware load balancer requirements for Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="e2b3b-223">![Сведения о портах и протоколах пограничного сервера] (images/Gg398739.1c193b80-98ab-4d59-a854-dbfdb5e209e2(OCS.15).jpg "Сведения о портах и протоколах пограничного сервера")</span><span class="sxs-lookup"><span data-stu-id="e2b3b-223">![Edge Server ports and protocols details](images/Gg398739.1c193b80-98ab-4d59-a854-dbfdb5e209e2(OCS.15).jpg "Edge Server ports and protocols details")</span></span>

### <a name="external-port-settings-required-for-scaled-consolidated-edge-hardware-load-balanced-external-interface-virtual-ips"></a><span data-ttu-id="e2b3b-224">Параметры внешнего порта, необходимые для масштабируемой консолидированной границы, аппаратной балансировки нагрузки: внешние IP адресных интерфейсов</span><span class="sxs-lookup"><span data-stu-id="e2b3b-224">External Port Settings Required for Scaled Consolidated Edge, Hardware Load Balanced: External Interface Virtual IPs</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e2b3b-225">Role/Protocol/TCP/UDP/порт</span><span class="sxs-lookup"><span data-stu-id="e2b3b-225">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="e2b3b-226">IP-адрес источника</span><span class="sxs-lookup"><span data-stu-id="e2b3b-226">Source IP address</span></span></th>
<th><span data-ttu-id="e2b3b-227">IP-адрес назначения</span><span class="sxs-lookup"><span data-stu-id="e2b3b-227">Destination IP address</span></span></th>
<th><span data-ttu-id="e2b3b-228">Примечания.</span><span class="sxs-lookup"><span data-stu-id="e2b3b-228">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e2b3b-229">КСМПП/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="e2b3b-229">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="e2b3b-230">Любой</span><span class="sxs-lookup"><span data-stu-id="e2b3b-230">Any</span></span></p></td>
<td><p><span data-ttu-id="e2b3b-231">Прокси-служба КСМПП (доступ к IP-адресу для общих ресурсов с помощью службы Edge Access)</span><span class="sxs-lookup"><span data-stu-id="e2b3b-231">XMPP Proxy service (shares IP address with Access Edge service)</span></span></p></td>
<td><p><span data-ttu-id="e2b3b-232">Прокси-служба КСМПП принимает трафик от КСМПП контактов в определенных КСМПП федерациях.</span><span class="sxs-lookup"><span data-stu-id="e2b3b-232">XMPP Proxy service accepts traffic from XMPP contacts in defined XMPP federations</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e2b3b-233">КСМПП/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="e2b3b-233">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="e2b3b-234">Прокси-служба КСМПП (доступ к IP-адресу для общих ресурсов с помощью службы Edge Access)</span><span class="sxs-lookup"><span data-stu-id="e2b3b-234">XMPP Proxy service (shares IP address with Access Edge service)</span></span></p></td>
<td><p><span data-ttu-id="e2b3b-235">Любой</span><span class="sxs-lookup"><span data-stu-id="e2b3b-235">Any</span></span></p></td>
<td><p><span data-ttu-id="e2b3b-236">Служба прокси КСМПП отправляет трафик на КСМППные контакты в определенных КСМПП Федерации</span><span class="sxs-lookup"><span data-stu-id="e2b3b-236">XMPP Proxy service sends traffic to XMPP contacts in defined XMPP federations</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e2b3b-237">Access/SIP (TLS)/TCP/443</span><span class="sxs-lookup"><span data-stu-id="e2b3b-237">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="e2b3b-238">Любой</span><span class="sxs-lookup"><span data-stu-id="e2b3b-238">Any</span></span></p></td>
<td><p><span data-ttu-id="e2b3b-239">Общедоступный виртуальный IP-адрес службы пограничного доступа</span><span class="sxs-lookup"><span data-stu-id="e2b3b-239">Access Edge service public VIP address</span></span></p></td>
<td><p><span data-ttu-id="e2b3b-240">Трафик SIP "клиент-сервер" для доступа внешних пользователей</span><span class="sxs-lookup"><span data-stu-id="e2b3b-240">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e2b3b-241">Access/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="e2b3b-241">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="e2b3b-242">Любой</span><span class="sxs-lookup"><span data-stu-id="e2b3b-242">Any</span></span></p></td>
<td><p><span data-ttu-id="e2b3b-243">Общедоступный виртуальный IP-адрес службы пограничного доступа</span><span class="sxs-lookup"><span data-stu-id="e2b3b-243">Access Edge service public VIP address</span></span></p></td>
<td><p><span data-ttu-id="e2b3b-244">Передача сигналов SIP, Федеративные и общедоступные возможности обмена мгновенными сообщениями с помощью SIP</span><span class="sxs-lookup"><span data-stu-id="e2b3b-244">SIP signaling, federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e2b3b-245">Access/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="e2b3b-245">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="e2b3b-246">Общедоступный виртуальный IP-адрес службы пограничного доступа</span><span class="sxs-lookup"><span data-stu-id="e2b3b-246">Access Edge service public VIP address</span></span></p></td>
<td><p><span data-ttu-id="e2b3b-247">Федеративный партнер</span><span class="sxs-lookup"><span data-stu-id="e2b3b-247">Federated partner</span></span></p></td>
<td><p><span data-ttu-id="e2b3b-248">Передача сигналов SIP, Федеративные и общедоступные возможности обмена мгновенными сообщениями с помощью SIP</span><span class="sxs-lookup"><span data-stu-id="e2b3b-248">SIP signaling, federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e2b3b-249">Веб-конференции/PSOM (TLS)/TCP/443</span><span class="sxs-lookup"><span data-stu-id="e2b3b-249">Web Conferencing/PSOM(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="e2b3b-250">Любой</span><span class="sxs-lookup"><span data-stu-id="e2b3b-250">Any</span></span></p></td>
<td><p><span data-ttu-id="e2b3b-251">Общедоступный виртуальный IP-адрес службы пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="e2b3b-251">Edge Server Web Conferencing Edge service public VIP address</span></span></p></td>
<td><p><span data-ttu-id="e2b3b-252">Мультимедиа для веб-конференций</span><span class="sxs-lookup"><span data-stu-id="e2b3b-252">Web Conferencing media</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e2b3b-253">A/V/STUN, МСТУРН/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="e2b3b-253">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="e2b3b-254">Любой</span><span class="sxs-lookup"><span data-stu-id="e2b3b-254">Any</span></span></p></td>
<td><p><span data-ttu-id="e2b3b-255">Сервер пограничного сервера A/V (внешний IP-адрес для службы EDGE)</span><span class="sxs-lookup"><span data-stu-id="e2b3b-255">Edge Server A/V Edge service public VIP address</span></span></p></td>
<td><p><span data-ttu-id="e2b3b-256">STUN/отключите согласование кандидатов по протоколу UDP/3478</span><span class="sxs-lookup"><span data-stu-id="e2b3b-256">STUN/TURN negotiation of candidates over UDP/3478</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e2b3b-257">A/V/STUN, МСТУРН/TCP/443</span><span class="sxs-lookup"><span data-stu-id="e2b3b-257">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="e2b3b-258">Любой</span><span class="sxs-lookup"><span data-stu-id="e2b3b-258">Any</span></span></p></td>
<td><p><span data-ttu-id="e2b3b-259">Сервер пограничного сервера A/V (внешний IP-адрес для службы EDGE)</span><span class="sxs-lookup"><span data-stu-id="e2b3b-259">Edge Server A/V Edge service public VIP address</span></span></p></td>
<td><p><span data-ttu-id="e2b3b-260">STUN/отключите согласование кандидатов по протоколу TCP/443</span><span class="sxs-lookup"><span data-stu-id="e2b3b-260">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="firewall-summary-for-scaled-consolidated-edge-hardware-load-balanced-internal-interface-virtual-ips"></a><span data-ttu-id="e2b3b-261">Сводка по межсетевому экрану для масштабируемой консолидированной границы, аппаратной балансировки нагрузки: Внутренние виртуальные IP – адреса интерфейса</span><span class="sxs-lookup"><span data-stu-id="e2b3b-261">Firewall Summary for Scaled Consolidated Edge, Hardware Load Balanced: Internal Interface Virtual IPs</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e2b3b-262">Role/Protocol/TCP/UDP/порт</span><span class="sxs-lookup"><span data-stu-id="e2b3b-262">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="e2b3b-263">IP-адрес источника</span><span class="sxs-lookup"><span data-stu-id="e2b3b-263">Source IP address</span></span></th>
<th><span data-ttu-id="e2b3b-264">IP-адрес назначения</span><span class="sxs-lookup"><span data-stu-id="e2b3b-264">Destination IP address</span></span></th>
<th><span data-ttu-id="e2b3b-265">Примечания.</span><span class="sxs-lookup"><span data-stu-id="e2b3b-265">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e2b3b-266">Access/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="e2b3b-266">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="e2b3b-267">Any (может быть определено как режиссер, виртуальный IP-адрес пула режиссера, виртуальный IP-адрес внешнего сервера или пула переднего плана)</span><span class="sxs-lookup"><span data-stu-id="e2b3b-267">Any (can be defined as Director, Director pool virtual IP address, Front End Server or Front End pool virtual IP address)</span></span></p></td>
<td><p><span data-ttu-id="e2b3b-268">Интерфейс внутренних виртуальных IP-адресов пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="e2b3b-268">Edge Server Internal VIP interface</span></span></p></td>
<td><p><span data-ttu-id="e2b3b-269">Исходящий трафик SIP (от режиссера, виртуальный IP-адрес пула, сервер переднего плана, виртуальный IP-адрес пула переднего плана) до внутреннего граничного сервера.</span><span class="sxs-lookup"><span data-stu-id="e2b3b-269">Outbound SIP traffic (from Director, Director pool virtual IP address, Front End Server or Front End pool virtual IP address)to Internal Edge VIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e2b3b-270">Access/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="e2b3b-270">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="e2b3b-271">Интерфейс внутренних виртуальных IP-адресов пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="e2b3b-271">Edge Server Internal VIP interface</span></span></p></td>
<td><p><span data-ttu-id="e2b3b-272">Any (может быть определено как режиссер, виртуальный IP-адрес пула режиссера, виртуальный IP-адрес внешнего сервера или пула переднего плана)</span><span class="sxs-lookup"><span data-stu-id="e2b3b-272">Any (can be defined as Director, Director pool virtual IP address, Front End Server or Front End pool virtual IP address)</span></span></p></td>
<td><p><span data-ttu-id="e2b3b-273">Входящий трафик SIP (для режиссера, виртуального IP-адреса пула пулов, сервер переднего плана и виртуальный IP-адрес пула переднего плана) от внутреннего интерфейса пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="e2b3b-273">Inbound SIP traffic (to Director, Director pool virtual IP address, Front End Server or Front End pool virtual IP address) from Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e2b3b-274">SIP/MTLS/TCP/5062</span><span class="sxs-lookup"><span data-stu-id="e2b3b-274">SIP/MTLS/TCP/5062</span></span></p></td>
<td><p><span data-ttu-id="e2b3b-275">Any (может быть как IP-адресом переднего сервера, так и IP-адресом пула переднего плана либо любым бесперебойно работающее устройство филиала или с помощью этого пограничного сервера).</span><span class="sxs-lookup"><span data-stu-id="e2b3b-275">Any (can be defined as Front End Server IP address, or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server)</span></span></p></td>
<td><p><span data-ttu-id="e2b3b-276">Интерфейс внутренних виртуальных IP-адресов пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="e2b3b-276">Edge Server Internal VIP interface</span></span></p></td>
<td><p><span data-ttu-id="e2b3b-277">Проверка подлинности пользователей/V (служба проверки подлинности A/V) от IP-адреса сервера переднего плана или переднего плана, а также от любого работающего филиала или сервера с бесперебойной подразделением с помощью этого пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="e2b3b-277">Authentication of A/V users (A/V authentication service) from Front End Server or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e2b3b-278">STUN/МСТУРН/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="e2b3b-278">STUN/MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="e2b3b-279">Любой</span><span class="sxs-lookup"><span data-stu-id="e2b3b-279">Any</span></span></p></td>
<td><p><span data-ttu-id="e2b3b-280">Интерфейс внутренних виртуальных IP-адресов пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="e2b3b-280">Edge Server Internal VIP interface</span></span></p></td>
<td><p><span data-ttu-id="e2b3b-281">Предпочтительный путь для передачи мультимедиа между внутренними и внешними пользователями</span><span class="sxs-lookup"><span data-stu-id="e2b3b-281">Preferred path for A/V media transfer between internal and external users</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e2b3b-282">STUN/МСТУРН/TCP/443</span><span class="sxs-lookup"><span data-stu-id="e2b3b-282">STUN/MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="e2b3b-283">Любой</span><span class="sxs-lookup"><span data-stu-id="e2b3b-283">Any</span></span></p></td>
<td><p><span data-ttu-id="e2b3b-284">Интерфейс внутренних виртуальных IP-адресов пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="e2b3b-284">Edge Server Internal VIP interface</span></span></p></td>
<td><p><span data-ttu-id="e2b3b-285">Резервный путь для передачи мультимедиа между внутренними и внешними пользователями если не удается установить UDP-связь, используется протокол TCP для обмена файлами и демонстрации рабочего стола</span><span class="sxs-lookup"><span data-stu-id="e2b3b-285">Fallback path for A/V media transfer between internal and external users if UDP communication cannot be established, TCP is used for file transfer and desktop sharing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e2b3b-286">STUN/МСТУРН/TCP/443</span><span class="sxs-lookup"><span data-stu-id="e2b3b-286">STUN/MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="e2b3b-287">Интерфейс внутренних виртуальных IP-адресов пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="e2b3b-287">Edge Server Internal VIP interface</span></span></p></td>
<td><p><span data-ttu-id="e2b3b-288">Любой</span><span class="sxs-lookup"><span data-stu-id="e2b3b-288">Any</span></span></p></td>
<td><p><span data-ttu-id="e2b3b-289">Резервный путь для передачи мультимедиа между внутренними и внешними пользователями если не удается установить UDP-связь, используется протокол TCP для обмена файлами и демонстрации рабочего стола</span><span class="sxs-lookup"><span data-stu-id="e2b3b-289">Fallback path for A/V media transfer between internal and external users if UDP communication cannot be established, TCP is used for file transfer and desktop sharing</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

