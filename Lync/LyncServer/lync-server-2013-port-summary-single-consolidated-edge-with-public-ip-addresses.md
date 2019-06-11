---
title: Сводка по портам — единая консолидированная пограничная топология с общедоступными IP-адресами
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Port summary - Single consolidated edge with public IP addresses
ms:assetid: 28407acc-8b92-4f78-875c-fd6b4323b602
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204756(v=OCS.15)
ms:contentKeyID: 48183685
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7c1a61341908bef3a3098e70b06816bbf5ea328b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34824241"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="port-summary---single-consolidated-edge-with-public-ip-addresses-in-lync-server-2013"></a><span data-ttu-id="81e50-102">Сводка по портам — единая консолидированная пограничная топология с общедоступными IP-адресами в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="81e50-102">Port summary - Single consolidated edge with public IP addresses in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="81e50-103">_**Тема последнего изменения:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="81e50-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="81e50-104">Функция пограничного сервера Lync Server 2013, описанная в этой архитектуре сценариев, очень похожа на ту, что была реализована в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="81e50-104">The Lync Server 2013, Edge Server functionality described in this scenario architecture is very similar to what was implemented in Lync Server 2010.</span></span> <span data-ttu-id="81e50-105">Наиболее заметным дополнением является порт **5269 на TCP** для протокола расширенной обработки сообщений и присутствия (КСМПП).</span><span class="sxs-lookup"><span data-stu-id="81e50-105">The most noticeable addition is the port **5269 over TCP** entry for the extensible messaging and presence protocol (XMPP).</span></span> <span data-ttu-id="81e50-106">Lync Server 2013 (при необходимости) можно развернуть прокси-сервер КСМПП на пограничном или пограничном пуле, а также на сервере шлюзов КСМПП на сервере переднего плана или в пуле внешних интерфейсов.</span><span class="sxs-lookup"><span data-stu-id="81e50-106">Lync Server 2013 optionally deploys an XMPP proxy on the Edge Server or Edge pool and the XMPP gateway server on the Front End Server or Front End pool.</span></span> <span data-ttu-id="81e50-107">Сведения о планировании для обратного прокси-сервера и Федерации находятся в [сценариях обратного прокси-сервера в Lync server 2013](lync-server-2013-scenarios-for-reverse-proxy.md) и [планировании SIP, КСМПП Federation и общедоступных мгновенных сообщений в разделах Lync Server 2013](lync-server-2013-planning-for-sip-xmpp-federation-and-public-instant-messaging.md) соответственно.</span><span class="sxs-lookup"><span data-stu-id="81e50-107">Planning information for the reverse proxy and federation are found in [Scenarios for reverse proxy in Lync Server 2013](lync-server-2013-scenarios-for-reverse-proxy.md) and [Planning for SIP, XMPP federation, and public instant messaging in Lync Server 2013](lync-server-2013-planning-for-sip-xmpp-federation-and-public-instant-messaging.md) sections, respectively.</span></span>

<span data-ttu-id="81e50-108">В дополнение к протоколу IPv4, пограничный сервер теперь поддерживает IPv6.</span><span class="sxs-lookup"><span data-stu-id="81e50-108">In addition to IPv4, the Edge Server now supports IPv6.</span></span> <span data-ttu-id="81e50-109">Для ясности в сценариях используется только протокол IPv4.</span><span class="sxs-lookup"><span data-stu-id="81e50-109">For clarity, only IPv4 is used in the scenarios.</span></span>

<span data-ttu-id="81e50-110">**Корпоративная сеть периметра для единого консолидированного края с общедоступными IP-адресами**</span><span class="sxs-lookup"><span data-stu-id="81e50-110">**Enterprise perimeter network for single consolidated edge with public IP addressing**</span></span>

<span data-ttu-id="81e50-111">![f8c144c5-e5fb-498a-823e-eb39f26b6847] (images/Gg425891.f8c144c5-e5fb-498a-823e-eb39f26b6847(OCS.15).jpg "f8c144c5-e5fb-498a-823e-eb39f26b6847")</span><span class="sxs-lookup"><span data-stu-id="81e50-111">![f8c144c5-e5fb-498a-823e-eb39f26b6847](images/Gg425891.f8c144c5-e5fb-498a-823e-eb39f26b6847(OCS.15).jpg "f8c144c5-e5fb-498a-823e-eb39f26b6847")</span></span>

<div>

## <a name="port-and-protocol-details"></a><span data-ttu-id="81e50-112">Сведения о портах и протоколах</span><span class="sxs-lookup"><span data-stu-id="81e50-112">Port and Protocol Details</span></span>

<span data-ttu-id="81e50-113">Мы рекомендуем открывать только порты, необходимые для поддержки функций, для которых предоставляется внешний доступ.</span><span class="sxs-lookup"><span data-stu-id="81e50-113">We recommend that you open only the ports required to support the functionality for which you are providing external access.</span></span>

<span data-ttu-id="81e50-114">Для удаленного доступа к работе в любой службе пограничного сервера необходимо, чтобы трафик SIP был разрешен по двунаправленному потоку, как показано на рисунке входящего и исходящего трафика пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="81e50-114">For remote access to work for any edge service, it is mandatory that SIP traffic is allowed to flow bidirectionally as shown in the Inbound/Outbound edge traffic figure.</span></span> <span data-ttu-id="81e50-115">Другими словами, Обмен сообщениями SIP и из службы Edge для Access осуществляется в обмене мгновенными сообщениями, присутствии, веб-конференциях, аудио-и видеосвязи (A/V) и Федерации.</span><span class="sxs-lookup"><span data-stu-id="81e50-115">Stated another way, the SIP messaging to and from the Access Edge service is involved in instant messaging (IM), presence, web conferencing, audio/video (A/V) and federation.</span></span>

### <a name="firewall-summary-for-single-consolidated-edge-with-public-ip-addresses-external-interface"></a><span data-ttu-id="81e50-116">Сводка по межсетевому экрану единого консолидированного края с общедоступными IP-адресами: внешний интерфейс</span><span class="sxs-lookup"><span data-stu-id="81e50-116">Firewall Summary for Single Consolidated Edge with Public IP Addresses: External Interface</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="81e50-117">Role/Protocol/TCP/UDP/порт</span><span class="sxs-lookup"><span data-stu-id="81e50-117">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="81e50-118">IP-адрес источника</span><span class="sxs-lookup"><span data-stu-id="81e50-118">Source IP address</span></span></th>
<th><span data-ttu-id="81e50-119">IP-адрес назначения</span><span class="sxs-lookup"><span data-stu-id="81e50-119">Destination IP address</span></span></th>
<th><span data-ttu-id="81e50-120">Примечания.</span><span class="sxs-lookup"><span data-stu-id="81e50-120">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="81e50-121">КСМПП/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="81e50-121">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="81e50-122">Любой</span><span class="sxs-lookup"><span data-stu-id="81e50-122">Any</span></span></p></td>
<td><p><span data-ttu-id="81e50-123">Прокси-служба КСМПП (доступ к IP-адресу для общих ресурсов с помощью службы Edge Access)</span><span class="sxs-lookup"><span data-stu-id="81e50-123">XMPP Proxy service (shares IP address with Access Edge service)</span></span></p></td>
<td><p><span data-ttu-id="81e50-124">Прокси-служба КСМПП принимает трафик от КСМПП контактов в определенных КСМПП федерациях.</span><span class="sxs-lookup"><span data-stu-id="81e50-124">XMPP Proxy service accepts traffic from XMPP contacts in defined XMPP federations</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="81e50-125">Access/HTTP/TCP/80</span><span class="sxs-lookup"><span data-stu-id="81e50-125">Access/HTTP/TCP/80</span></span></p></td>
<td><p><span data-ttu-id="81e50-126">Общедоступный IP-адрес службы пограничного доступа к серверу Edge</span><span class="sxs-lookup"><span data-stu-id="81e50-126">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="81e50-127">Любой</span><span class="sxs-lookup"><span data-stu-id="81e50-127">Any</span></span></p></td>
<td><p><span data-ttu-id="81e50-128">Проверка отзыва сертификатов и получения CRL</span><span class="sxs-lookup"><span data-stu-id="81e50-128">Certificate revocation/CRL check and retrieval</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="81e50-129">Access/DNS/TCP/53</span><span class="sxs-lookup"><span data-stu-id="81e50-129">Access/DNS/TCP/53</span></span></p></td>
<td><p><span data-ttu-id="81e50-130">Общедоступный IP-адрес службы пограничного доступа к серверу Edge</span><span class="sxs-lookup"><span data-stu-id="81e50-130">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="81e50-131">Любой</span><span class="sxs-lookup"><span data-stu-id="81e50-131">Any</span></span></p></td>
<td><p><span data-ttu-id="81e50-132">Запрос DNS по протоколу TCP</span><span class="sxs-lookup"><span data-stu-id="81e50-132">DNS query over TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="81e50-133">Access/DNS/UDP/53</span><span class="sxs-lookup"><span data-stu-id="81e50-133">Access/DNS/UDP/53</span></span></p></td>
<td><p><span data-ttu-id="81e50-134">Общедоступный IP-адрес службы пограничного доступа к серверу Edge</span><span class="sxs-lookup"><span data-stu-id="81e50-134">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="81e50-135">Любой</span><span class="sxs-lookup"><span data-stu-id="81e50-135">Any</span></span></p></td>
<td><p><span data-ttu-id="81e50-136">Запрос DNS по протоколу UDP</span><span class="sxs-lookup"><span data-stu-id="81e50-136">DNS query over UDP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="81e50-137">Access/SIP (TLS)/TCP/443</span><span class="sxs-lookup"><span data-stu-id="81e50-137">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="81e50-138">Любой</span><span class="sxs-lookup"><span data-stu-id="81e50-138">Any</span></span></p></td>
<td><p><span data-ttu-id="81e50-139">Общедоступный IP-адрес службы пограничного доступа к серверу Edge</span><span class="sxs-lookup"><span data-stu-id="81e50-139">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="81e50-140">Трафик SIP "клиент-сервер" для доступа внешних пользователей</span><span class="sxs-lookup"><span data-stu-id="81e50-140">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="81e50-141">Access/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="81e50-141">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="81e50-142">Любой</span><span class="sxs-lookup"><span data-stu-id="81e50-142">Any</span></span></p></td>
<td><p><span data-ttu-id="81e50-143">Общедоступный IP-адрес службы пограничного доступа к серверу Edge</span><span class="sxs-lookup"><span data-stu-id="81e50-143">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="81e50-144">Для Федеративной и общедоступной службы обмена мгновенными сообщениями с помощью SIP</span><span class="sxs-lookup"><span data-stu-id="81e50-144">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="81e50-145">Access/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="81e50-145">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="81e50-146">Общедоступный IP-адрес службы пограничного доступа к серверу Edge</span><span class="sxs-lookup"><span data-stu-id="81e50-146">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="81e50-147">Любой</span><span class="sxs-lookup"><span data-stu-id="81e50-147">Any</span></span></p></td>
<td><p><span data-ttu-id="81e50-148">Для Федеративной и общедоступной службы обмена мгновенными сообщениями с помощью SIP</span><span class="sxs-lookup"><span data-stu-id="81e50-148">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="81e50-149">Веб-конференции/PSOM (TLS)/TCP/443</span><span class="sxs-lookup"><span data-stu-id="81e50-149">Web Conferencing/PSOM(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="81e50-150">Любой</span><span class="sxs-lookup"><span data-stu-id="81e50-150">Any</span></span></p></td>
<td><p><span data-ttu-id="81e50-151">Общедоступный IP-адрес службы пограничного сервера для веб-конференций Edge</span><span class="sxs-lookup"><span data-stu-id="81e50-151">Edge Server Web Conferencing Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="81e50-152">Мультимедиа для веб-конференций</span><span class="sxs-lookup"><span data-stu-id="81e50-152">Web Conferencing media</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="81e50-153">A/V/RTP/TCP/50000-59,999</span><span class="sxs-lookup"><span data-stu-id="81e50-153">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="81e50-154">Общедоступный IP-адрес службы пограничного доступа к серверу Edge</span><span class="sxs-lookup"><span data-stu-id="81e50-154">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="81e50-155">Любой</span><span class="sxs-lookup"><span data-stu-id="81e50-155">Any</span></span></p></td>
<td><p><span data-ttu-id="81e50-156">Требуется для Федерации с партнерами, работающими под управлением Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 и Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="81e50-156">Required for federating with partners running Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 and Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="81e50-157">A/V/RTP/UDP/50000-59,999</span><span class="sxs-lookup"><span data-stu-id="81e50-157">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="81e50-158">Общедоступный IP-адрес службы пограничного сервера A/V</span><span class="sxs-lookup"><span data-stu-id="81e50-158">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="81e50-159">Любой</span><span class="sxs-lookup"><span data-stu-id="81e50-159">Any</span></span></p></td>
<td><p><span data-ttu-id="81e50-160">Требуется только для Федерации с партнерами, работающими под управлением Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="81e50-160">Required only for federation with partners running Office Communications Server 2007</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="81e50-161">A/V/RTP/TCP/50000-59,999</span><span class="sxs-lookup"><span data-stu-id="81e50-161">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="81e50-162">Любой</span><span class="sxs-lookup"><span data-stu-id="81e50-162">Any</span></span></p></td>
<td><p><span data-ttu-id="81e50-163">Общедоступный IP-адрес службы пограничного сервера A/V</span><span class="sxs-lookup"><span data-stu-id="81e50-163">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="81e50-164">Требуется только для Федерации с партнерами, работающими под управлением Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="81e50-164">Required only for federation with partners running Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="81e50-165">A/V/RTP/UDP/50000-59,999</span><span class="sxs-lookup"><span data-stu-id="81e50-165">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="81e50-166">Любой</span><span class="sxs-lookup"><span data-stu-id="81e50-166">Any</span></span></p></td>
<td><p><span data-ttu-id="81e50-167">Общедоступный IP-адрес службы пограничного сервера A/V</span><span class="sxs-lookup"><span data-stu-id="81e50-167">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="81e50-168">Требуется только для Федерации с партнерами, работающими под управлением Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="81e50-168">Required only for federation with partners running Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="81e50-169">A/V/STUN, МСТУРН/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="81e50-169">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="81e50-170">Общедоступный IP-адрес службы пограничного сервера A/V</span><span class="sxs-lookup"><span data-stu-id="81e50-170">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="81e50-171">Любой</span><span class="sxs-lookup"><span data-stu-id="81e50-171">Any</span></span></p></td>
<td><p><span data-ttu-id="81e50-172">3478 Outbound используется для определения версии пограничного сервера, с которым обменивается данными Lync Server, а также для мультимедийного трафика от пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="81e50-172">3478 outbound is used to determine the version of Edge Server that Lync Server is communicating with and also for media traffic from Edge Server-to-Edge Server.</span></span> <span data-ttu-id="81e50-173">Требуется для Федерации с Lync Server 2010, Windows Live Messenger и Office Communications Server 2007 R2, а также в том случае, если в компании развернуты несколько пулов Edge.</span><span class="sxs-lookup"><span data-stu-id="81e50-173">Required for federation with Lync Server 2010, Windows Live Messenger, and Office Communications Server 2007 R2, and also if multiple Edge pools are deployed within a company.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="81e50-174">A/V/STUN, МСТУРН/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="81e50-174">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="81e50-175">Любой</span><span class="sxs-lookup"><span data-stu-id="81e50-175">Any</span></span></p></td>
<td><p><span data-ttu-id="81e50-176">Общедоступный IP-адрес службы пограничного сервера A/V</span><span class="sxs-lookup"><span data-stu-id="81e50-176">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="81e50-177">STUN/отключите согласование кандидатов по протоколу UDP/3478</span><span class="sxs-lookup"><span data-stu-id="81e50-177">STUN/TURN negotiation of candidates over UDP/3478</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="81e50-178">A/V/STUN, МСТУРН/TCP/443</span><span class="sxs-lookup"><span data-stu-id="81e50-178">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="81e50-179">Любой</span><span class="sxs-lookup"><span data-stu-id="81e50-179">Any</span></span></p></td>
<td><p><span data-ttu-id="81e50-180">Общедоступный IP-адрес службы пограничного сервера A/V</span><span class="sxs-lookup"><span data-stu-id="81e50-180">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="81e50-181">STUN/отключите согласование кандидатов по протоколу TCP/443</span><span class="sxs-lookup"><span data-stu-id="81e50-181">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="81e50-182">A/V/STUN, МСТУРН/TCP/443</span><span class="sxs-lookup"><span data-stu-id="81e50-182">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="81e50-183">Общедоступный IP-адрес службы пограничного сервера A/V</span><span class="sxs-lookup"><span data-stu-id="81e50-183">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="81e50-184">Любой</span><span class="sxs-lookup"><span data-stu-id="81e50-184">Any</span></span></p></td>
<td><p><span data-ttu-id="81e50-185">STUN/отключите согласование кандидатов по протоколу TCP/443</span><span class="sxs-lookup"><span data-stu-id="81e50-185">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="firewall-summary-for-single-consolidated-edge-with-public-ip-addresses-internal-interface"></a><span data-ttu-id="81e50-186">Сводка по межсетевому экрану отдельного консолидированного края с общедоступными IP-адресами: внутренний интерфейс</span><span class="sxs-lookup"><span data-stu-id="81e50-186">Firewall Summary for Single Consolidated Edge with Public IP Addresses: Internal Interface</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="81e50-187">Протокол/TCP или UDP/порт</span><span class="sxs-lookup"><span data-stu-id="81e50-187">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="81e50-188">IP-адрес источника</span><span class="sxs-lookup"><span data-stu-id="81e50-188">Source IP address</span></span></th>
<th><span data-ttu-id="81e50-189">IP-адрес назначения</span><span class="sxs-lookup"><span data-stu-id="81e50-189">Destination IP address</span></span></th>
<th><span data-ttu-id="81e50-190">Комментарии</span><span class="sxs-lookup"><span data-stu-id="81e50-190">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="81e50-191">КСМПП/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="81e50-191">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="81e50-192">Any (может быть определен как IP-адрес сервера Standard Edition, IP-адреса стандартного выпуска или IP-адрес пула, на котором запущена служба шлюза КСМПП).</span><span class="sxs-lookup"><span data-stu-id="81e50-192">Any (can be defined as Standard Edition server IP, Standard Edition server IP address, or pool IP address running the XMPP Gateway service)</span></span></p></td>
<td><p><span data-ttu-id="81e50-193">Внутренний интерфейс пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="81e50-193">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="81e50-194">Исходящий трафик КСМПП от службы шлюза КСМПП, работающей на сервере переднего плана или в пуле внешних интерфейсов</span><span class="sxs-lookup"><span data-stu-id="81e50-194">Outbound XMPP traffic from XMPP Gateway service running on Front End Server or Front End pool</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="81e50-195">SIP/MTLS/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="81e50-195">SIP/MTLS/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="81e50-196">Any (может быть определено как режиссер, IP-адрес пула режиссера, сервер клиентского доступа или IP-адрес пула переднего плана)</span><span class="sxs-lookup"><span data-stu-id="81e50-196">Any (can be defined as Director, Director pool IP address, Front End Server or Front End pool IP address)</span></span></p></td>
<td><p><span data-ttu-id="81e50-197">IP-адрес пограничного сервера или пул, хранящий внутренний интерфейс.</span><span class="sxs-lookup"><span data-stu-id="81e50-197">Edge Server IP, or pool that holds the internal interface</span></span></p></td>
<td><p><span data-ttu-id="81e50-198">Исходящий трафик SIP (от режиссера, IP-адреса пула, сервера переднего плана или IP-адреса пула переднего плана) к внутреннему интерфейсу пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="81e50-198">Outbound SIP traffic (from Director, Director pool IP address, Front End Server or Front End pool IP address) to Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="81e50-199">SIP/MTLS/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="81e50-199">SIP/MTLS/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="81e50-200">Внутренний интерфейс пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="81e50-200">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="81e50-201">Any (может быть определено как режиссер, IP-адрес пула режиссера, сервер переднего плана или адрес пула переднего плана).</span><span class="sxs-lookup"><span data-stu-id="81e50-201">Any (can be defined as Director, Director pool IP address, Front End Server or Front End pool address)</span></span></p></td>
<td><p><span data-ttu-id="81e50-202">Входящий трафик SIP (для режиссера, IP-адреса пула, сервера переднего плана или IP-адреса пула переднего плана) от внутреннего интерфейса пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="81e50-202">Inbound SIP traffic (to Director, Director pool IP address, Front End Server or Front End pool IP address) from Edge Server internal interface</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="81e50-203">PSOM/MTLS/TCP/8057</span><span class="sxs-lookup"><span data-stu-id="81e50-203">PSOM/MTLS/TCP/8057</span></span></p></td>
<td><p><span data-ttu-id="81e50-204">Any (может быть IP-адресом сервера переднего плана или IP-адресом серверного переднего плана в пуле переднего плана)</span><span class="sxs-lookup"><span data-stu-id="81e50-204">Any (can be defined as Front End Server IP address, or each Front End Server IP address in a Front End pool)</span></span></p></td>
<td><p><span data-ttu-id="81e50-205">Внутренний интерфейс пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="81e50-205">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="81e50-206">Трафик веб-конференций от сервера переднего плана или каждого серверного переднего плана, если он находится в пуле и является внутренним интерфейсом пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="81e50-206">Web conferencing traffic from Front End Server or each Front End Server if in a pool, to Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="81e50-207">SIP/MTLS/TCP/5062</span><span class="sxs-lookup"><span data-stu-id="81e50-207">SIP/MTLS/TCP/5062</span></span></p></td>
<td><p><span data-ttu-id="81e50-208">Any (может быть как IP-адресом переднего сервера, так и IP-адресом пула переднего плана либо любым бесперебойно работающее устройство филиала или с помощью этого пограничного сервера).</span><span class="sxs-lookup"><span data-stu-id="81e50-208">Any (can be defined as Front End Server IP address, or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server)</span></span></p></td>
<td><p><span data-ttu-id="81e50-209">Внутренний интерфейс пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="81e50-209">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="81e50-210">Проверка подлинности пользователей/V (служба проверки подлинности A/V) от IP-адреса сервера переднего плана или переднего плана, а также от любого работающего филиала или сервера с бесперебойной подразделением с помощью этого пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="81e50-210">Authentication of A/V users (A/V authentication service) from Front End Server or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="81e50-211">STUN/МСТУРН/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="81e50-211">STUN/MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="81e50-212">Любой</span><span class="sxs-lookup"><span data-stu-id="81e50-212">Any</span></span></p></td>
<td><p><span data-ttu-id="81e50-213">Внутренний интерфейс пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="81e50-213">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="81e50-214">Предпочтительный путь для передачи мультимедиа между внутренними и внешними пользователями, бесперебойно работающем устройстве филиалов или бесперебойно работающем сервере филиала</span><span class="sxs-lookup"><span data-stu-id="81e50-214">Preferred path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="81e50-215">STUN/МСТУРН/TCP/443</span><span class="sxs-lookup"><span data-stu-id="81e50-215">STUN/MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="81e50-216">Любой</span><span class="sxs-lookup"><span data-stu-id="81e50-216">Any</span></span></p></td>
<td><p><span data-ttu-id="81e50-217">Внутренний интерфейс пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="81e50-217">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="81e50-218">Резервный путь для передачи мультимедиа между внутренними и внешними пользователями, бесперебойно работающее устройство филиала или бесперебойный сервер филиала, если не удается установить UDP-связь, используется протокол TCP для обмена файлами и демонстрации рабочего стола</span><span class="sxs-lookup"><span data-stu-id="81e50-218">Fallback path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server if UDP communication cannot be established, TCP is used for file transfer and desktop sharing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="81e50-219">HTTPS/TCP/4443</span><span class="sxs-lookup"><span data-stu-id="81e50-219">HTTPS/TCP/4443</span></span></p></td>
<td><p><span data-ttu-id="81e50-220">Any (может быть указан в качестве IP-адреса сервера переднего плана или пула, содержащего центральное хранилище управления).</span><span class="sxs-lookup"><span data-stu-id="81e50-220">Any (can be defined as the Front End Server IP address, or pool that holds the Central Management store)</span></span></p></td>
<td><p><span data-ttu-id="81e50-221">Внутренний интерфейс пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="81e50-221">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="81e50-222">Репликация изменений из хранилища центрального управления на пограничный сервер</span><span class="sxs-lookup"><span data-stu-id="81e50-222">Replication of changes from the Central Management store to the Edge Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="81e50-223">MTLS/TCP/50001</span><span class="sxs-lookup"><span data-stu-id="81e50-223">MTLS/TCP/50001</span></span></p></td>
<td><p><span data-ttu-id="81e50-224">Любой</span><span class="sxs-lookup"><span data-stu-id="81e50-224">Any</span></span></p></td>
<td><p><span data-ttu-id="81e50-225">Внутренний интерфейс пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="81e50-225">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="81e50-226">Централизованное ведение журналов с помощью команд командной строки Lync Server Management Shell и централизованных служб ведения журнала, Клсконтроллер (Командная строка Клсконтроллер. exe) или агента (Клсажент. exe) и коллекции журналов</span><span class="sxs-lookup"><span data-stu-id="81e50-226">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="81e50-227">MTLS/TCP/50002</span><span class="sxs-lookup"><span data-stu-id="81e50-227">MTLS/TCP/50002</span></span></p></td>
<td><p><span data-ttu-id="81e50-228">Любой</span><span class="sxs-lookup"><span data-stu-id="81e50-228">Any</span></span></p></td>
<td><p><span data-ttu-id="81e50-229">Внутренний интерфейс пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="81e50-229">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="81e50-230">Централизованное ведение журналов с помощью команд командной строки Lync Server Management Shell и централизованных служб ведения журнала, Клсконтроллер (Командная строка Клсконтроллер. exe) или агента (Клсажент. exe) и коллекции журналов</span><span class="sxs-lookup"><span data-stu-id="81e50-230">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="81e50-231">MTLS/TCP/50003</span><span class="sxs-lookup"><span data-stu-id="81e50-231">MTLS/TCP/50003</span></span></p></td>
<td><p><span data-ttu-id="81e50-232">Любой</span><span class="sxs-lookup"><span data-stu-id="81e50-232">Any</span></span></p></td>
<td><p><span data-ttu-id="81e50-233">Внутренний интерфейс пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="81e50-233">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="81e50-234">Централизованное ведение журналов с помощью команд командной строки Lync Server Management Shell и централизованных служб ведения журнала, Клсконтроллер (Командная строка Клсконтроллер. exe) или агента (Клсажент. exe) и коллекции журналов</span><span class="sxs-lookup"><span data-stu-id="81e50-234">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-federation"></a><span data-ttu-id="81e50-235">Сводка по межсетевому экрану для Федерации</span><span class="sxs-lookup"><span data-stu-id="81e50-235">Firewall Summary for Federation</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="81e50-236">Role/Protocol/TCP/UDP/порт</span><span class="sxs-lookup"><span data-stu-id="81e50-236">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="81e50-237">IP-адрес источника</span><span class="sxs-lookup"><span data-stu-id="81e50-237">Source IP address</span></span></th>
<th><span data-ttu-id="81e50-238">IP-адрес назначения</span><span class="sxs-lookup"><span data-stu-id="81e50-238">Destination IP address</span></span></th>
<th><span data-ttu-id="81e50-239">Примечания.</span><span class="sxs-lookup"><span data-stu-id="81e50-239">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="81e50-240">Access/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="81e50-240">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="81e50-241">Общедоступный IP-адрес службы пограничного доступа</span><span class="sxs-lookup"><span data-stu-id="81e50-241">Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="81e50-242">Любой</span><span class="sxs-lookup"><span data-stu-id="81e50-242">Any</span></span></p></td>
<td><p><span data-ttu-id="81e50-243">Для Федеративной и общедоступной службы обмена мгновенными сообщениями с помощью SIP</span><span class="sxs-lookup"><span data-stu-id="81e50-243">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary--public-instant-messaging-connectivity"></a><span data-ttu-id="81e50-244">Сводка по брандмауэрам: общедоступная служба обмена мгновенными сообщениями</span><span class="sxs-lookup"><span data-stu-id="81e50-244">Firewall Summary – Public Instant Messaging Connectivity</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="81e50-245">Role/Protocol/TCP/UDP/порт</span><span class="sxs-lookup"><span data-stu-id="81e50-245">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="81e50-246">IP-адрес источника</span><span class="sxs-lookup"><span data-stu-id="81e50-246">Source IP address</span></span></th>
<th><span data-ttu-id="81e50-247">IP-адрес назначения</span><span class="sxs-lookup"><span data-stu-id="81e50-247">Destination IP address</span></span></th>
<th><span data-ttu-id="81e50-248">Примечания.</span><span class="sxs-lookup"><span data-stu-id="81e50-248">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="81e50-249">Access/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="81e50-249">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="81e50-250">Партнеры по подключению общедоступных мгновенных сообщений</span><span class="sxs-lookup"><span data-stu-id="81e50-250">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="81e50-251">Служба пограничного доступа к пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="81e50-251">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="81e50-252">Для Федеративной и общедоступной службы обмена мгновенными сообщениями с помощью SIP</span><span class="sxs-lookup"><span data-stu-id="81e50-252">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="81e50-253">Access/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="81e50-253">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="81e50-254">Служба пограничного доступа к пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="81e50-254">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="81e50-255">Партнеры по подключению общедоступных мгновенных сообщений</span><span class="sxs-lookup"><span data-stu-id="81e50-255">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="81e50-256">Для Федеративной и общедоступной службы обмена мгновенными сообщениями с помощью SIP</span><span class="sxs-lookup"><span data-stu-id="81e50-256">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="81e50-257">Access/SIP (TLS)/TCP/443</span><span class="sxs-lookup"><span data-stu-id="81e50-257">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="81e50-258">Клиенты</span><span class="sxs-lookup"><span data-stu-id="81e50-258">Clients</span></span></p></td>
<td><p><span data-ttu-id="81e50-259">Служба пограничного доступа к пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="81e50-259">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="81e50-260">Трафик SIP "клиент-сервер" для доступа внешних пользователей</span><span class="sxs-lookup"><span data-stu-id="81e50-260">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="81e50-261">A/V/RTP/TCP/50000-59,999</span><span class="sxs-lookup"><span data-stu-id="81e50-261">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="81e50-262">Служба Edge для пограничного сервера A/V</span><span class="sxs-lookup"><span data-stu-id="81e50-262">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="81e50-263">Клиенты Live Messenger</span><span class="sxs-lookup"><span data-stu-id="81e50-263">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="81e50-264">Используется для сеансов обмена мгновенными сообщениями с помощью Windows Live Messenger, если настроена служба общего доступа к данным.</span><span class="sxs-lookup"><span data-stu-id="81e50-264">Used for A/V sessions with Windows Live Messenger if public IM connectivity is configured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="81e50-265">A/V/STUN, МСТУРН/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="81e50-265">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="81e50-266">Служба Edge для пограничного сервера A/V</span><span class="sxs-lookup"><span data-stu-id="81e50-266">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="81e50-267">Клиенты Live Messenger</span><span class="sxs-lookup"><span data-stu-id="81e50-267">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="81e50-268">Требуется для общедоступной службы обмена мгновенными сообщениями в Windows Live Messenger</span><span class="sxs-lookup"><span data-stu-id="81e50-268">Required for public IM connectivity with Windows Live Messenger</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="81e50-269">A/V/STUN, МСТУРН/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="81e50-269">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="81e50-270">Клиенты Live Messenger</span><span class="sxs-lookup"><span data-stu-id="81e50-270">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="81e50-271">Служба Edge для пограничного сервера A/V</span><span class="sxs-lookup"><span data-stu-id="81e50-271">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="81e50-272">Требуется для общедоступной службы обмена мгновенными сообщениями в Windows Live Messenger</span><span class="sxs-lookup"><span data-stu-id="81e50-272">Required for public IM connectivity with Windows Live Messenger</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-extensible-messaging-and-presence-protocol"></a><span data-ttu-id="81e50-273">Сводка брандмауэра по протоколу расширенного обмена сообщениями и присутствия</span><span class="sxs-lookup"><span data-stu-id="81e50-273">Firewall Summary for Extensible Messaging and Presence Protocol</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="81e50-274">Протокол/TCP или UDP/порт</span><span class="sxs-lookup"><span data-stu-id="81e50-274">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="81e50-275">Источник (IP-адрес)</span><span class="sxs-lookup"><span data-stu-id="81e50-275">Source (IP address)</span></span></th>
<th><span data-ttu-id="81e50-276">Назначение (IP-адрес)</span><span class="sxs-lookup"><span data-stu-id="81e50-276">Destination (IP address)</span></span></th>
<th><span data-ttu-id="81e50-277">Комментарии</span><span class="sxs-lookup"><span data-stu-id="81e50-277">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="81e50-278">КСМПП/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="81e50-278">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="81e50-279">Любой</span><span class="sxs-lookup"><span data-stu-id="81e50-279">Any</span></span></p></td>
<td><p><span data-ttu-id="81e50-280">IP-адрес интерфейса службы пограничного доступа к серверу Edge</span><span class="sxs-lookup"><span data-stu-id="81e50-280">Edge Server Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="81e50-281">Стандартный коммуникационный порт "сервер-сервер" для КСМПП.</span><span class="sxs-lookup"><span data-stu-id="81e50-281">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="81e50-282">Разрешает связь с прокси-сервером пограничного сервера КСМПП от федеративных КСМПП партнеров</span><span class="sxs-lookup"><span data-stu-id="81e50-282">Allows communication to the Edge Server XMPP proxy from federated XMPP partners</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="81e50-283">КСМПП/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="81e50-283">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="81e50-284">IP-адрес интерфейса службы пограничного доступа к серверу Edge</span><span class="sxs-lookup"><span data-stu-id="81e50-284">Edge Server Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="81e50-285">Любой</span><span class="sxs-lookup"><span data-stu-id="81e50-285">Any</span></span></p></td>
<td><p><span data-ttu-id="81e50-286">Стандартный коммуникационный порт "сервер-сервер" для КСМПП.</span><span class="sxs-lookup"><span data-stu-id="81e50-286">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="81e50-287">Разрешает взаимодействие с КСМПП прокси-сервером для федеративных КСМПП партнеров</span><span class="sxs-lookup"><span data-stu-id="81e50-287">Allows communication from the Edge Server XMPP proxy to federated XMPP partners</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="81e50-288">КСМПП/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="81e50-288">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="81e50-289">Любой</span><span class="sxs-lookup"><span data-stu-id="81e50-289">Any</span></span></p></td>
<td><p><span data-ttu-id="81e50-290">Каждый внутренний IP-адрес интерфейса пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="81e50-290">Each internal Edge Server Interface IP</span></span></p></td>
<td><p><span data-ttu-id="81e50-291">Внутренний IP-адрес КСМПП, входящий в состав шлюза КСМПП на сервере переднего плана или в пуле переднего плана, в адрес внутренней сети пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="81e50-291">Internal XMPP traffic from the XMPP Gateway on the Front End Server or Front End pool to the Edge Server internal IP address or each Edge pool member’s internal IP address</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

