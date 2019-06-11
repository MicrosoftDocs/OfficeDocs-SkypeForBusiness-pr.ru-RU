---
title: 'Lync Server 2013: сводка по портам — масштабируемая консолидированная пограничная топология, балансировка нагрузки на DNS с закрытыми IP-адресами и трансляцией сетевых адресов'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Port summary - Scaled consolidated edge, DNS load balancing with private IP addresses using NAT
ms:assetid: a296c2af-54d4-4b4f-9795-9191baf688cb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412756(v=OCS.15)
ms:contentKeyID: 48184955
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7d7e9a142e478674f4be369ace5551b2b628db83
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34824332"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="port-summary---scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat-in-lync-server-2013"></a><span data-ttu-id="4aaa1-102">Сводка по портам — масштабируемая консолидированная пограничная топология, балансировка нагрузки на DNS с закрытыми IP-адресами и трансляцией сетевых адресов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4aaa1-102">Port summary - Scaled consolidated edge, DNS load balancing with private IP addresses using NAT in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4aaa1-103">_**Тема последнего изменения:** 2012-12-04_</span><span class="sxs-lookup"><span data-stu-id="4aaa1-103">_**Topic Last Modified:** 2012-12-04_</span></span>

<span data-ttu-id="4aaa1-104">Функция пограничного сервера Lync Server 2013, описанная в этой архитектуре сценариев, очень похожа на ту, что была реализована в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="4aaa1-104">The Lync Server 2013, Edge Server functionality described in this scenario architecture is very similar to what was implemented in Lync Server 2010.</span></span> <span data-ttu-id="4aaa1-105">Наиболее заметным дополнением является порт **5269 на TCP** для протокола расширенной обработки сообщений и присутствия (КСМПП).</span><span class="sxs-lookup"><span data-stu-id="4aaa1-105">The most noticeable addition is the port **5269 over TCP** entry for the extensible messaging and presence protocol (XMPP).</span></span> <span data-ttu-id="4aaa1-106">Lync Server 2013 (при необходимости) можно развернуть прокси-сервер КСМПП на пограничном или пограничном пуле, а также на сервере шлюзов КСМПП на сервере переднего плана или в пуле внешних интерфейсов.</span><span class="sxs-lookup"><span data-stu-id="4aaa1-106">Lync Server 2013 optionally deploys an XMPP proxy on the Edge Server or Edge pool and the XMPP gateway server on the Front End Server or Front End pool.</span></span>

<span data-ttu-id="4aaa1-107">В дополнение к протоколу IPv4, пограничный сервер теперь поддерживает IPv6.</span><span class="sxs-lookup"><span data-stu-id="4aaa1-107">In addition to IPv4, the Edge Server now supports IPv6.</span></span> <span data-ttu-id="4aaa1-108">Для ясности в сценариях используется только протокол IPv4.</span><span class="sxs-lookup"><span data-stu-id="4aaa1-108">For clarity, only IPv4 is used in the scenarios.</span></span>

<span data-ttu-id="4aaa1-109">**Корпоративная сеть периметра для масштабируемой консолидированной кромки с частными IP-адресами с помощью NAT**</span><span class="sxs-lookup"><span data-stu-id="4aaa1-109">**Enterprise perimeter network for scaled consolidated edge with private IP addresses using NAT**</span></span>

<span data-ttu-id="4aaa1-110">![96f5a8f5-16d2-464d-b86e-7c7ecfc89ead] (images/JJ205394.96f5a8f5-16d2-464d-b86e-7c7ecfc89ead(OCS.15).jpg "96f5a8f5-16d2-464d-b86e-7c7ecfc89ead")</span><span class="sxs-lookup"><span data-stu-id="4aaa1-110">![96f5a8f5-16d2-464d-b86e-7c7ecfc89ead](images/JJ205394.96f5a8f5-16d2-464d-b86e-7c7ecfc89ead(OCS.15).jpg "96f5a8f5-16d2-464d-b86e-7c7ecfc89ead")</span></span>

<div>

## <a name="port-and-protocol-details"></a><span data-ttu-id="4aaa1-111">Сведения о портах и протоколах</span><span class="sxs-lookup"><span data-stu-id="4aaa1-111">Port and Protocol Details</span></span>

<span data-ttu-id="4aaa1-112">Рекомендуется открывать только порты, необходимые для поддержки функций, для которых предоставляется внешний доступ.</span><span class="sxs-lookup"><span data-stu-id="4aaa1-112">It is recommended that you open only the ports required to support the functionality for which you are providing external access.</span></span>

<span data-ttu-id="4aaa1-113">Для удаленного доступа к работе в любой службе пограничного сервера необходимо, чтобы трафик SIP был в направлении на один и тот же трафик по внешнему потоку, как показано на рисунке входящего и исходящего трафика пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="4aaa1-113">For remote access to work for any edge service, it is mandatory that SIP traffic is allowed to flow bi-directionally as shown in the Inbound/Outbound edge traffic figure.</span></span> <span data-ttu-id="4aaa1-114">Другими словами, Обмен сообщениями SIP и из службы Edge для Access осуществляется в обмене мгновенными сообщениями, присутствии, веб-конференциях, аудио-и видеосвязи (A/V) и Федерации.</span><span class="sxs-lookup"><span data-stu-id="4aaa1-114">Stated another way, the SIP messaging to and from the Access Edge service is involved in instant messaging (IM), presence, web conferencing, audio/video (A/V) and federation.</span></span>

### <a name="firewall-summary-for-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat-external-interface--node-1-and-node-2-example"></a><span data-ttu-id="4aaa1-115">Сводка по межсетевому экрану для масштабируемой консолидированной границы, балансировка нагрузки DNS с частными IP-адресами с использованием NAT: внешний интерфейс — узел 1 и узел 2 (пример).</span><span class="sxs-lookup"><span data-stu-id="4aaa1-115">Firewall Summary for Scaled Consolidated Edge, DNS Load Balancing with Private IP Addresses Using NAT: External Interface – Node 1 and Node 2 (Example)</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4aaa1-116">Role/Protocol/TCP/UDP/порт</span><span class="sxs-lookup"><span data-stu-id="4aaa1-116">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="4aaa1-117">IP-адрес источника</span><span class="sxs-lookup"><span data-stu-id="4aaa1-117">Source IP address</span></span></th>
<th><span data-ttu-id="4aaa1-118">IP-адрес назначения</span><span class="sxs-lookup"><span data-stu-id="4aaa1-118">Destination IP address</span></span></th>
<th><span data-ttu-id="4aaa1-119">Примечания.</span><span class="sxs-lookup"><span data-stu-id="4aaa1-119">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4aaa1-120">КСМПП/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="4aaa1-120">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="4aaa1-121">Любой</span><span class="sxs-lookup"><span data-stu-id="4aaa1-121">Any</span></span></p></td>
<td><p><span data-ttu-id="4aaa1-122">Прокси-служба КСМПП (доступ к IP-адресу для общих ресурсов с помощью службы Edge Access)</span><span class="sxs-lookup"><span data-stu-id="4aaa1-122">XMPP Proxy service (shares IP address with Access Edge service)</span></span></p></td>
<td><p><span data-ttu-id="4aaa1-123">Прокси-служба КСМПП принимает трафик от КСМПП контактов в определенных КСМПП федерациях.</span><span class="sxs-lookup"><span data-stu-id="4aaa1-123">XMPP Proxy service accepts traffic from XMPP contacts in defined XMPP federations</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4aaa1-124">КСМПП/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="4aaa1-124">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="4aaa1-125">Прокси-служба КСМПП (доступ к IP-адресу для общих ресурсов с помощью службы Edge Access)</span><span class="sxs-lookup"><span data-stu-id="4aaa1-125">XMPP Proxy service (shares IP address with Access Edge service)</span></span></p></td>
<td><p><span data-ttu-id="4aaa1-126">Любой</span><span class="sxs-lookup"><span data-stu-id="4aaa1-126">Any</span></span></p></td>
<td><p><span data-ttu-id="4aaa1-127">Служба прокси КСМПП отправляет трафик на КСМППные контакты в определенных КСМПП Федерации</span><span class="sxs-lookup"><span data-stu-id="4aaa1-127">XMPP Proxy service sends traffic to XMPP contacts in defined XMPP federations</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4aaa1-128">Access/HTTP/TCP/80</span><span class="sxs-lookup"><span data-stu-id="4aaa1-128">Access/HTTP/TCP/80</span></span></p></td>
<td><p><span data-ttu-id="4aaa1-129">Служба пограничного доступа к пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="4aaa1-129">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="4aaa1-130">Любой</span><span class="sxs-lookup"><span data-stu-id="4aaa1-130">Any</span></span></p></td>
<td><p><span data-ttu-id="4aaa1-131">Проверка отзыва сертификатов и получения CRL</span><span class="sxs-lookup"><span data-stu-id="4aaa1-131">Certificate revocation/CRL check and retrieval</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4aaa1-132">Access/DNS/TCP/53</span><span class="sxs-lookup"><span data-stu-id="4aaa1-132">Access/DNS/TCP/53</span></span></p></td>
<td><p><span data-ttu-id="4aaa1-133">Служба пограничного доступа к пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="4aaa1-133">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="4aaa1-134">Любой</span><span class="sxs-lookup"><span data-stu-id="4aaa1-134">Any</span></span></p></td>
<td><p><span data-ttu-id="4aaa1-135">Запрос DNS по протоколу TCP</span><span class="sxs-lookup"><span data-stu-id="4aaa1-135">DNS query over TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4aaa1-136">Access/DNS/UDP/53</span><span class="sxs-lookup"><span data-stu-id="4aaa1-136">Access/DNS/UDP/53</span></span></p></td>
<td><p><span data-ttu-id="4aaa1-137">Служба пограничного доступа к пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="4aaa1-137">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="4aaa1-138">Любой</span><span class="sxs-lookup"><span data-stu-id="4aaa1-138">Any</span></span></p></td>
<td><p><span data-ttu-id="4aaa1-139">Запрос DNS по протоколу UDP</span><span class="sxs-lookup"><span data-stu-id="4aaa1-139">DNS query over UDP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4aaa1-140">Access/SIP (TLS)/TCP/443</span><span class="sxs-lookup"><span data-stu-id="4aaa1-140">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="4aaa1-141">Любой</span><span class="sxs-lookup"><span data-stu-id="4aaa1-141">Any</span></span></p></td>
<td><p><span data-ttu-id="4aaa1-142">Служба пограничного доступа к пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="4aaa1-142">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="4aaa1-143">Трафик SIP "клиент-сервер" для доступа внешних пользователей</span><span class="sxs-lookup"><span data-stu-id="4aaa1-143">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4aaa1-144">Access/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="4aaa1-144">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="4aaa1-145">Любой</span><span class="sxs-lookup"><span data-stu-id="4aaa1-145">Any</span></span></p></td>
<td><p><span data-ttu-id="4aaa1-146">Служба пограничного доступа к пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="4aaa1-146">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="4aaa1-147">Для Федеративной и общедоступной службы обмена мгновенными сообщениями с помощью SIP</span><span class="sxs-lookup"><span data-stu-id="4aaa1-147">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4aaa1-148">Access/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="4aaa1-148">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="4aaa1-149">Служба пограничного доступа к пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="4aaa1-149">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="4aaa1-150">Любой</span><span class="sxs-lookup"><span data-stu-id="4aaa1-150">Any</span></span></p></td>
<td><p><span data-ttu-id="4aaa1-151">Для Федеративной и общедоступной службы обмена мгновенными сообщениями с помощью SIP</span><span class="sxs-lookup"><span data-stu-id="4aaa1-151">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4aaa1-152">Веб-конференции/PSOM (TLS)/TCP/443</span><span class="sxs-lookup"><span data-stu-id="4aaa1-152">Web Conferencing/PSOM(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="4aaa1-153">Любой</span><span class="sxs-lookup"><span data-stu-id="4aaa1-153">Any</span></span></p></td>
<td><p><span data-ttu-id="4aaa1-154">Служба веб-конференций пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="4aaa1-154">Edge Server Web Conferencing Edge service</span></span></p></td>
<td><p><span data-ttu-id="4aaa1-155">Мультимедиа для веб-конференций</span><span class="sxs-lookup"><span data-stu-id="4aaa1-155">Web Conferencing media</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4aaa1-156">A/V/RTP/TCP/50000-59,999</span><span class="sxs-lookup"><span data-stu-id="4aaa1-156">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="4aaa1-157">Служба Edge для пограничного сервера A/V</span><span class="sxs-lookup"><span data-stu-id="4aaa1-157">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="4aaa1-158">Любой</span><span class="sxs-lookup"><span data-stu-id="4aaa1-158">Any</span></span></p></td>
<td><p><span data-ttu-id="4aaa1-159">Требуется для Федерации с партнерами, работающими под управлением Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 и Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4aaa1-159">Required for federating with partners running Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 and Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4aaa1-160">A/V/RTP/UDP/50000-59,999</span><span class="sxs-lookup"><span data-stu-id="4aaa1-160">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="4aaa1-161">Служба Edge для пограничного сервера A/V</span><span class="sxs-lookup"><span data-stu-id="4aaa1-161">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="4aaa1-162">Любой</span><span class="sxs-lookup"><span data-stu-id="4aaa1-162">Any</span></span></p></td>
<td><p><span data-ttu-id="4aaa1-163">Требуется только для Федерации с партнерами, работающими под управлением Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="4aaa1-163">Required only for federation with partners running Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4aaa1-164">A/V/RTP/TCP/50000-59,999</span><span class="sxs-lookup"><span data-stu-id="4aaa1-164">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="4aaa1-165">Любой</span><span class="sxs-lookup"><span data-stu-id="4aaa1-165">Any</span></span></p></td>
<td><p><span data-ttu-id="4aaa1-166">Служба Edge для пограничного сервера A/V</span><span class="sxs-lookup"><span data-stu-id="4aaa1-166">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="4aaa1-167">Требуется только для Федерации с партнерами, работающими под управлением Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="4aaa1-167">Required only for federation with partners running Office Communications Server 2007</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4aaa1-168">A/V/RTP/UDP/50000-59,999</span><span class="sxs-lookup"><span data-stu-id="4aaa1-168">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="4aaa1-169">Любой</span><span class="sxs-lookup"><span data-stu-id="4aaa1-169">Any</span></span></p></td>
<td><p><span data-ttu-id="4aaa1-170">Служба Edge для пограничного сервера A/V</span><span class="sxs-lookup"><span data-stu-id="4aaa1-170">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="4aaa1-171">Требуется только для Федерации с партнерами, работающими под управлением Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="4aaa1-171">Required only for federation with partners running Office Communications Server 2007</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4aaa1-172">A/V/STUN, МСТУРН/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="4aaa1-172">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="4aaa1-173">Служба Edge для пограничного сервера A/V</span><span class="sxs-lookup"><span data-stu-id="4aaa1-173">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="4aaa1-174">Любой</span><span class="sxs-lookup"><span data-stu-id="4aaa1-174">Any</span></span></p></td>
<td><p><span data-ttu-id="4aaa1-175">3478 Outbound используется для определения версии пограничного сервера, с которым обменивается данными Lync Server, а также для мультимедийного трафика от пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="4aaa1-175">3478 outbound is used to determine the version of Edge Server that Lync Server is communicating with and also for media traffic from Edge Server-to-Edge Server.</span></span> <span data-ttu-id="4aaa1-176">Требуется для Федерации с Lync Server 2010, Windows Live Messenger и Office Communications Server 2007 R2, а также в том случае, если в компании развернуты несколько пулов Edge.</span><span class="sxs-lookup"><span data-stu-id="4aaa1-176">Required for federation with Lync Server 2010, Windows Live Messenger, and Office Communications Server 2007 R2, and also if multiple Edge pools are deployed within a company.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4aaa1-177">A/V/STUN, МСТУРН/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="4aaa1-177">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="4aaa1-178">Любой</span><span class="sxs-lookup"><span data-stu-id="4aaa1-178">Any</span></span></p></td>
<td><p><span data-ttu-id="4aaa1-179">Служба Edge для пограничного сервера A/V</span><span class="sxs-lookup"><span data-stu-id="4aaa1-179">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="4aaa1-180">STUN/отключите согласование кандидатов по протоколу UDP/3478</span><span class="sxs-lookup"><span data-stu-id="4aaa1-180">STUN/TURN negotiation of candidates over UDP/3478</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4aaa1-181">A/V/STUN, МСТУРН/TCP/443</span><span class="sxs-lookup"><span data-stu-id="4aaa1-181">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="4aaa1-182">Любой</span><span class="sxs-lookup"><span data-stu-id="4aaa1-182">Any</span></span></p></td>
<td><p><span data-ttu-id="4aaa1-183">Служба Edge для пограничного сервера A/V</span><span class="sxs-lookup"><span data-stu-id="4aaa1-183">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="4aaa1-184">STUN/отключите согласование кандидатов по протоколу TCP/443</span><span class="sxs-lookup"><span data-stu-id="4aaa1-184">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4aaa1-185">A/V/STUN, МСТУРН/TCP/443</span><span class="sxs-lookup"><span data-stu-id="4aaa1-185">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="4aaa1-186">Служба Edge для пограничного сервера A/V</span><span class="sxs-lookup"><span data-stu-id="4aaa1-186">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="4aaa1-187">Любой</span><span class="sxs-lookup"><span data-stu-id="4aaa1-187">Any</span></span></p></td>
<td><p><span data-ttu-id="4aaa1-188">STUN/отключите согласование кандидатов по протоколу TCP/443</span><span class="sxs-lookup"><span data-stu-id="4aaa1-188">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="firewall-summary-for-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat-internal-interface--node-1-and-node-2-example"></a><span data-ttu-id="4aaa1-189">Сводка по межсетевому экрану для масштабируемой консолидированной границы, балансировки нагрузки DNS с частными IP-адресами с использованием NAT: внутренний интерфейс — узел 1 и узел 2 (пример)</span><span class="sxs-lookup"><span data-stu-id="4aaa1-189">Firewall Summary for Scaled Consolidated Edge, DNS Load Balancing with Private IP Addresses Using NAT: Internal Interface – Node 1 and Node 2 (Example)</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4aaa1-190">Протокол/TCP или UDP/порт</span><span class="sxs-lookup"><span data-stu-id="4aaa1-190">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="4aaa1-191">IP-адрес источника</span><span class="sxs-lookup"><span data-stu-id="4aaa1-191">Source IP address</span></span></th>
<th><span data-ttu-id="4aaa1-192">IP-адрес назначения</span><span class="sxs-lookup"><span data-stu-id="4aaa1-192">Destination IP address</span></span></th>
<th><span data-ttu-id="4aaa1-193">Комментарии</span><span class="sxs-lookup"><span data-stu-id="4aaa1-193">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4aaa1-194">КСМПП/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="4aaa1-194">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="4aaa1-195">Any (может быть определено как адрес сервера переднего плана или IP-адрес пула переднего плана, на котором запущена служба шлюза КСМПП)</span><span class="sxs-lookup"><span data-stu-id="4aaa1-195">Any (can be defined as Front End Server address, or Front End pool IP address running the XMPP Gateway service)</span></span></p></td>
<td><p><span data-ttu-id="4aaa1-196">IP-адрес внутреннего интерфейса пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="4aaa1-196">Edge Server internal interface IP address</span></span></p></td>
<td><p><span data-ttu-id="4aaa1-197">Исходящий трафик КСМПП от службы шлюза КСМПП, работающей на сервере переднего плана или в пуле внешних интерфейсов</span><span class="sxs-lookup"><span data-stu-id="4aaa1-197">Outbound XMPP traffic from XMPP Gateway service running on Front End Server or Front End pool</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4aaa1-198">SIP/MTLS/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="4aaa1-198">SIP/MTLS/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="4aaa1-199">Any (может быть определено как режиссер, IP-адрес пула режиссера, сервер клиентского доступа или IP-адрес пула переднего плана)</span><span class="sxs-lookup"><span data-stu-id="4aaa1-199">Any (can be defined as Director, Director pool IP address, Front End Server or Front End pool IP address)</span></span></p></td>
<td><p><span data-ttu-id="4aaa1-200">Внутренний интерфейс пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="4aaa1-200">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="4aaa1-201">Исходящий трафик SIP (от режиссера, IP-адреса пула, сервера переднего плана или IP-адреса пула переднего плана) к внутреннему интерфейсу пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="4aaa1-201">Outbound SIP traffic (from Director, Director pool IP address, Front End Server or Front End pool IP address) to Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4aaa1-202">SIP/MTLS/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="4aaa1-202">SIP/MTLS/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="4aaa1-203">Внутренний интерфейс пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="4aaa1-203">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="4aaa1-204">Any (может быть определено как режиссер, IP-адрес пула режиссера, сервер клиентского доступа или IP-адрес пула переднего плана)</span><span class="sxs-lookup"><span data-stu-id="4aaa1-204">Any (can be defined as Director, Director pool IP address, Front End Server or Front End pool IP address)</span></span></p></td>
<td><p><span data-ttu-id="4aaa1-205">Входящий трафик SIP (для режиссера, IP-адреса пула, сервера переднего плана или IP-адреса пула переднего плана) от внутреннего интерфейса пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="4aaa1-205">Inbound SIP traffic (to Director, Director pool IP address, Front End Server or Front End pool IP address) from Edge Server internal interface</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4aaa1-206">PSOM/MTLS/TCP/8057</span><span class="sxs-lookup"><span data-stu-id="4aaa1-206">PSOM/MTLS/TCP/8057</span></span></p></td>
<td><p><span data-ttu-id="4aaa1-207">Any (может быть IP-адресом сервера переднего плана или IP-адресом серверного переднего плана в пуле переднего плана)</span><span class="sxs-lookup"><span data-stu-id="4aaa1-207">Any (can be defined as Front End Server IP address, or each Front End Server IP address in a Front End pool)</span></span></p></td>
<td><p><span data-ttu-id="4aaa1-208">Внутренний интерфейс пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="4aaa1-208">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="4aaa1-209">Трафик веб-конференций от сервера переднего плана или каждого серверного переднего плана, если он находится в пуле и является внутренним интерфейсом пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="4aaa1-209">Web conferencing traffic from Front End Server or each Front End Server if in a pool, to Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4aaa1-210">SIP/MTLS/TCP/5062</span><span class="sxs-lookup"><span data-stu-id="4aaa1-210">SIP/MTLS/TCP/5062</span></span></p></td>
<td><p><span data-ttu-id="4aaa1-211">Any (может быть как IP-адресом переднего сервера, так и IP-адресом пула переднего плана либо любым бесперебойно работающее устройство филиала или с помощью этого пограничного сервера).</span><span class="sxs-lookup"><span data-stu-id="4aaa1-211">Any (can be defined as Front End Server IP address, or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server)</span></span></p></td>
<td><p><span data-ttu-id="4aaa1-212">Внутренний интерфейс пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="4aaa1-212">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="4aaa1-213">Проверка подлинности пользователей/V (служба проверки подлинности A/V) от IP-адреса сервера переднего плана или переднего плана, а также от любого работающего филиала или сервера с бесперебойной подразделением с помощью этого пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="4aaa1-213">Authentication of A/V users (A/V authentication service) from Front End Server or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4aaa1-214">STUN/МСТУРН/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="4aaa1-214">STUN/MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="4aaa1-215">Любой</span><span class="sxs-lookup"><span data-stu-id="4aaa1-215">Any</span></span></p></td>
<td><p><span data-ttu-id="4aaa1-216">Внутренний интерфейс пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="4aaa1-216">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="4aaa1-217">Предпочтительный путь для передачи мультимедиа между внутренними и внешними пользователями, бесперебойно работающем устройстве филиалов или бесперебойно работающем сервере филиала</span><span class="sxs-lookup"><span data-stu-id="4aaa1-217">Preferred path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4aaa1-218">STUN/МСТУРН/TCP/443</span><span class="sxs-lookup"><span data-stu-id="4aaa1-218">STUN/MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="4aaa1-219">Любой</span><span class="sxs-lookup"><span data-stu-id="4aaa1-219">Any</span></span></p></td>
<td><p><span data-ttu-id="4aaa1-220">Внутренний интерфейс пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="4aaa1-220">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="4aaa1-221">Резервный путь для передачи мультимедиа между внутренними и внешними пользователями, бесперебойно работающее устройство филиала или бесперебойный сервер филиала, если не удается установить UDP-связь, используется протокол TCP для обмена файлами и демонстрации рабочего стола</span><span class="sxs-lookup"><span data-stu-id="4aaa1-221">Fallback path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server if UDP communication cannot be established, TCP is used for file transfer and desktop sharing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4aaa1-222">HTTPS/TCP/4443</span><span class="sxs-lookup"><span data-stu-id="4aaa1-222">HTTPS/TCP/4443</span></span></p></td>
<td><p><span data-ttu-id="4aaa1-223">Any (может быть указан в качестве IP-адреса сервера переднего плана или пула, содержащего центральное хранилище управления).</span><span class="sxs-lookup"><span data-stu-id="4aaa1-223">Any (can be defined as the Front End Server IP address, or pool that holds the Central Management store)</span></span></p></td>
<td><p><span data-ttu-id="4aaa1-224">Внутренний интерфейс пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="4aaa1-224">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="4aaa1-225">Репликация изменений из хранилища центрального управления на пограничный сервер</span><span class="sxs-lookup"><span data-stu-id="4aaa1-225">Replication of changes from the Central Management store to the Edge Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4aaa1-226">MTLS/TCP/50001</span><span class="sxs-lookup"><span data-stu-id="4aaa1-226">MTLS/TCP/50001</span></span></p></td>
<td><p><span data-ttu-id="4aaa1-227">Любой</span><span class="sxs-lookup"><span data-stu-id="4aaa1-227">Any</span></span></p></td>
<td><p><span data-ttu-id="4aaa1-228">Внутренний интерфейс пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="4aaa1-228">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="4aaa1-229">Централизованное ведение журналов с помощью команд командной строки Lync Server Management Shell и централизованных служб ведения журнала, Клсконтроллер (Командная строка Клсконтроллер. exe) или агента (Клсажент. exe) и коллекции журналов</span><span class="sxs-lookup"><span data-stu-id="4aaa1-229">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4aaa1-230">MTLS/TCP/50002</span><span class="sxs-lookup"><span data-stu-id="4aaa1-230">MTLS/TCP/50002</span></span></p></td>
<td><p><span data-ttu-id="4aaa1-231">Любой</span><span class="sxs-lookup"><span data-stu-id="4aaa1-231">Any</span></span></p></td>
<td><p><span data-ttu-id="4aaa1-232">Внутренний интерфейс пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="4aaa1-232">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="4aaa1-233">Централизованное ведение журналов с помощью команд командной строки Lync Server Management Shell и централизованных служб ведения журнала, Клсконтроллер (Командная строка Клсконтроллер. exe) или агента (Клсажент. exe) и коллекции журналов</span><span class="sxs-lookup"><span data-stu-id="4aaa1-233">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4aaa1-234">MTLS/TCP/50003</span><span class="sxs-lookup"><span data-stu-id="4aaa1-234">MTLS/TCP/50003</span></span></p></td>
<td><p><span data-ttu-id="4aaa1-235">Любой</span><span class="sxs-lookup"><span data-stu-id="4aaa1-235">Any</span></span></p></td>
<td><p><span data-ttu-id="4aaa1-236">Внутренний интерфейс пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="4aaa1-236">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="4aaa1-237">Централизованное ведение журналов с помощью команд командной строки Lync Server Management Shell и централизованных служб ведения журнала, Клсконтроллер (Командная строка Клсконтроллер. exe) или агента (Клсажент. exe) и коллекции журналов</span><span class="sxs-lookup"><span data-stu-id="4aaa1-237">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-federation"></a><span data-ttu-id="4aaa1-238">Сводка по межсетевому экрану для Федерации</span><span class="sxs-lookup"><span data-stu-id="4aaa1-238">Firewall Summary for Federation</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4aaa1-239">Role/Protocol/TCP/UDP/порт</span><span class="sxs-lookup"><span data-stu-id="4aaa1-239">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="4aaa1-240">IP-адрес источника</span><span class="sxs-lookup"><span data-stu-id="4aaa1-240">Source IP address</span></span></th>
<th><span data-ttu-id="4aaa1-241">IP-адрес назначения</span><span class="sxs-lookup"><span data-stu-id="4aaa1-241">Destination IP address</span></span></th>
<th><span data-ttu-id="4aaa1-242">Примечания.</span><span class="sxs-lookup"><span data-stu-id="4aaa1-242">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4aaa1-243">Access/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="4aaa1-243">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="4aaa1-244">Общедоступный IP-адрес службы пограничного доступа</span><span class="sxs-lookup"><span data-stu-id="4aaa1-244">Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="4aaa1-245">Любой</span><span class="sxs-lookup"><span data-stu-id="4aaa1-245">Any</span></span></p></td>
<td><p><span data-ttu-id="4aaa1-246">Для Федеративной и общедоступной службы обмена мгновенными сообщениями с помощью SIP</span><span class="sxs-lookup"><span data-stu-id="4aaa1-246">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary--public-instant-messaging-connectivity"></a><span data-ttu-id="4aaa1-247">Сводка по брандмауэрам: общедоступная служба обмена мгновенными сообщениями</span><span class="sxs-lookup"><span data-stu-id="4aaa1-247">Firewall Summary – Public Instant Messaging Connectivity</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4aaa1-248">Role/Protocol/TCP/UDP/порт</span><span class="sxs-lookup"><span data-stu-id="4aaa1-248">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="4aaa1-249">IP-адрес источника</span><span class="sxs-lookup"><span data-stu-id="4aaa1-249">Source IP address</span></span></th>
<th><span data-ttu-id="4aaa1-250">IP-адрес назначения</span><span class="sxs-lookup"><span data-stu-id="4aaa1-250">Destination IP address</span></span></th>
<th><span data-ttu-id="4aaa1-251">Примечания.</span><span class="sxs-lookup"><span data-stu-id="4aaa1-251">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4aaa1-252">Access/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="4aaa1-252">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="4aaa1-253">Партнеры по подключению общедоступных мгновенных сообщений</span><span class="sxs-lookup"><span data-stu-id="4aaa1-253">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="4aaa1-254">Служба пограничного доступа к пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="4aaa1-254">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="4aaa1-255">Для Федеративной и общедоступной службы обмена мгновенными сообщениями с помощью SIP</span><span class="sxs-lookup"><span data-stu-id="4aaa1-255">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4aaa1-256">Access/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="4aaa1-256">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="4aaa1-257">Служба пограничного доступа к пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="4aaa1-257">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="4aaa1-258">Партнеры по подключению общедоступных мгновенных сообщений</span><span class="sxs-lookup"><span data-stu-id="4aaa1-258">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="4aaa1-259">Для Федеративной и общедоступной службы обмена мгновенными сообщениями с помощью SIP</span><span class="sxs-lookup"><span data-stu-id="4aaa1-259">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4aaa1-260">Access/SIP (TLS)/TCP/443</span><span class="sxs-lookup"><span data-stu-id="4aaa1-260">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="4aaa1-261">Клиенты</span><span class="sxs-lookup"><span data-stu-id="4aaa1-261">Clients</span></span></p></td>
<td><p><span data-ttu-id="4aaa1-262">Служба пограничного доступа к пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="4aaa1-262">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="4aaa1-263">Трафик SIP "клиент-сервер" для доступа внешних пользователей</span><span class="sxs-lookup"><span data-stu-id="4aaa1-263">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4aaa1-264">A/V/RTP/TCP/50000-59,999</span><span class="sxs-lookup"><span data-stu-id="4aaa1-264">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="4aaa1-265">Служба Edge для пограничного сервера A/V</span><span class="sxs-lookup"><span data-stu-id="4aaa1-265">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="4aaa1-266">Клиенты Live Messenger</span><span class="sxs-lookup"><span data-stu-id="4aaa1-266">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="4aaa1-267">Используется для сеансов обмена мгновенными сообщениями с помощью Windows Live Messenger, если настроена служба общего доступа к данным.</span><span class="sxs-lookup"><span data-stu-id="4aaa1-267">Used for A/V sessions with Windows Live Messenger if public IM connectivity is configured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4aaa1-268">A/V/STUN, МСТУРН/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="4aaa1-268">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="4aaa1-269">Служба Edge для пограничного сервера A/V</span><span class="sxs-lookup"><span data-stu-id="4aaa1-269">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="4aaa1-270">Клиенты Live Messenger</span><span class="sxs-lookup"><span data-stu-id="4aaa1-270">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="4aaa1-271">Требуется для общедоступной службы обмена мгновенными сообщениями в Windows Live Messenger</span><span class="sxs-lookup"><span data-stu-id="4aaa1-271">Required for public IM connectivity with Windows Live Messenger</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4aaa1-272">A/V/STUN, МСТУРН/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="4aaa1-272">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="4aaa1-273">Клиенты Live Messenger</span><span class="sxs-lookup"><span data-stu-id="4aaa1-273">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="4aaa1-274">Служба Edge для пограничного сервера A/V</span><span class="sxs-lookup"><span data-stu-id="4aaa1-274">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="4aaa1-275">Требуется для общедоступной службы обмена мгновенными сообщениями в Windows Live Messenger</span><span class="sxs-lookup"><span data-stu-id="4aaa1-275">Required for public IM connectivity with Windows Live Messenger</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-extensible-messaging-and-presence-protocol"></a><span data-ttu-id="4aaa1-276">Сводка брандмауэра по протоколу расширенного обмена сообщениями и присутствия</span><span class="sxs-lookup"><span data-stu-id="4aaa1-276">Firewall Summary for Extensible Messaging and Presence Protocol</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4aaa1-277">Протокол/TCP или UDP/порт</span><span class="sxs-lookup"><span data-stu-id="4aaa1-277">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="4aaa1-278">Источник (IP-адрес)</span><span class="sxs-lookup"><span data-stu-id="4aaa1-278">Source (IP address)</span></span></th>
<th><span data-ttu-id="4aaa1-279">Назначение (IP-адрес)</span><span class="sxs-lookup"><span data-stu-id="4aaa1-279">Destination (IP address)</span></span></th>
<th><span data-ttu-id="4aaa1-280">Комментарии</span><span class="sxs-lookup"><span data-stu-id="4aaa1-280">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4aaa1-281">КСМПП/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="4aaa1-281">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="4aaa1-282">Любой</span><span class="sxs-lookup"><span data-stu-id="4aaa1-282">Any</span></span></p></td>
<td><p><span data-ttu-id="4aaa1-283">IP-адрес интерфейса службы пограничного доступа к серверу Edge</span><span class="sxs-lookup"><span data-stu-id="4aaa1-283">Edge Server Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="4aaa1-284">Стандартный коммуникационный порт "сервер-сервер" для КСМПП.</span><span class="sxs-lookup"><span data-stu-id="4aaa1-284">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="4aaa1-285">Разрешает связь с прокси-сервером пограничного сервера КСМПП от федеративных КСМПП партнеров</span><span class="sxs-lookup"><span data-stu-id="4aaa1-285">Allows communication to the Edge Server XMPP proxy from federated XMPP partners</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4aaa1-286">КСМПП/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="4aaa1-286">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="4aaa1-287">IP-адрес интерфейса службы пограничного доступа к серверу Edge</span><span class="sxs-lookup"><span data-stu-id="4aaa1-287">Edge Server Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="4aaa1-288">Любой</span><span class="sxs-lookup"><span data-stu-id="4aaa1-288">Any</span></span></p></td>
<td><p><span data-ttu-id="4aaa1-289">Стандартный коммуникационный порт "сервер-сервер" для КСМПП.</span><span class="sxs-lookup"><span data-stu-id="4aaa1-289">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="4aaa1-290">Разрешает взаимодействие с КСМПП прокси-сервером для федеративных КСМПП партнеров</span><span class="sxs-lookup"><span data-stu-id="4aaa1-290">Allows communication from the Edge Server XMPP proxy to federated XMPP partners</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4aaa1-291">КСМПП/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="4aaa1-291">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="4aaa1-292">Любой</span><span class="sxs-lookup"><span data-stu-id="4aaa1-292">Any</span></span></p></td>
<td><p><span data-ttu-id="4aaa1-293">Каждый внутренний IP-адрес интерфейса пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="4aaa1-293">Each internal Edge Server interface IP</span></span></p></td>
<td><p><span data-ttu-id="4aaa1-294">Внутренний IP-адрес КСМПП, входящий в состав шлюза КСМПП на сервере переднего плана или в пуле переднего плана, в адрес внутренней сети пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="4aaa1-294">Internal XMPP traffic from the XMPP Gateway on the Front End Server or Front End pool to the Edge Server internal IP address or each Edge pool member’s internal IP address</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

