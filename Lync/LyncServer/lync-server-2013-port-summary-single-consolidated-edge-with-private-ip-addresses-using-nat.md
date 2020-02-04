---
title: Сводка по портам — единая консолидированная пограничная топология с закрытыми IP-адресами и трансляцией сетевых адресов
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Port summary - Single consolidated edge with private IP addresses using NAT
ms:assetid: 3c1a389f-5f42-4719-a05b-e0b84aa3eb9e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425891(v=OCS.15)
ms:contentKeyID: 48183877
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a425a07bf5ff615fb4766d50f21c6467512d110e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41725019"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="port-summary---single-consolidated-edge-with-private-ip-addresses-using-nat-in-lync-server-2013"></a><span data-ttu-id="8d86b-102">Сводка по портам — единая консолидированная пограничная топология с закрытыми IP-адресами и трансляцией сетевых адресов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8d86b-102">Port summary - Single consolidated edge with private IP addresses using NAT in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8d86b-103">_**Тема последнего изменения:** 2013-04-03_</span><span class="sxs-lookup"><span data-stu-id="8d86b-103">_**Topic Last Modified:** 2013-04-03_</span></span>

<span data-ttu-id="8d86b-104">Функция пограничного сервера Lync Server 2013, описанная в этой архитектуре сценариев, очень похожа на ту, что была реализована в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="8d86b-104">The Lync Server 2013, Edge Server functionality described in this scenario architecture is very similar to what was implemented in Lync Server 2010.</span></span> <span data-ttu-id="8d86b-105">Наиболее заметным дополнением является порт **5269 на TCP** для протокола расширенной обработки сообщений и присутствия (КСМПП).</span><span class="sxs-lookup"><span data-stu-id="8d86b-105">The most noticeable addition is the port **5269 over TCP** entry for the extensible messaging and presence protocol (XMPP).</span></span> <span data-ttu-id="8d86b-106">Lync Server 2013 (при необходимости) можно развернуть прокси-сервер КСМПП на пограничном или пограничном пуле, а также на сервере шлюзов КСМПП на сервере переднего плана или в пуле внешних интерфейсов.</span><span class="sxs-lookup"><span data-stu-id="8d86b-106">Lync Server 2013 optionally deploys an XMPP proxy on the Edge Server or Edge pool and the XMPP gateway server on the Front End Server or Front End pool.</span></span>

<span data-ttu-id="8d86b-107">В дополнение к протоколу IPv4, пограничный сервер теперь поддерживает IPv6.</span><span class="sxs-lookup"><span data-stu-id="8d86b-107">In addition to IPv4, the Edge Server now supports IPv6.</span></span> <span data-ttu-id="8d86b-108">Для ясности в сценариях используется только протокол IPv4.</span><span class="sxs-lookup"><span data-stu-id="8d86b-108">For clarity, only IPv4 is used in the scenarios.</span></span>

<span data-ttu-id="8d86b-109">**Периметр сети для единого консолидированного пограничного сервера с использованием протокола преобразования сетевых адресов (NAT)**</span><span class="sxs-lookup"><span data-stu-id="8d86b-109">**Network Perimeter for a Single Consolidated Edge Server with Private IP Addressing Using NAT**</span></span>

<span data-ttu-id="8d86b-110">![f8c144c5-e5fb-498a-823e-eb39f26b6847](images/Gg425891.f8c144c5-e5fb-498a-823e-eb39f26b6847(OCS.15).jpg "f8c144c5-e5fb-498a-823e-eb39f26b6847")</span><span class="sxs-lookup"><span data-stu-id="8d86b-110">![f8c144c5-e5fb-498a-823e-eb39f26b6847](images/Gg425891.f8c144c5-e5fb-498a-823e-eb39f26b6847(OCS.15).jpg "f8c144c5-e5fb-498a-823e-eb39f26b6847")</span></span>

<div>

## <a name="port-and-protocol-details"></a><span data-ttu-id="8d86b-111">Сведения о портах и протоколах</span><span class="sxs-lookup"><span data-stu-id="8d86b-111">Port and Protocol Details</span></span>

<span data-ttu-id="8d86b-112">Мы рекомендуем открывать только порты, необходимые для поддержки функций, для которых предоставляется внешний доступ.</span><span class="sxs-lookup"><span data-stu-id="8d86b-112">We recommend that you open only the ports required to support the functionality for which you are providing external access.</span></span>

<span data-ttu-id="8d86b-113">Для удаленного доступа к работе в любой службе пограничного сервера необходимо, чтобы трафик SIP был в направлении на один и тот же трафик по внешнему потоку, как показано на рисунке входящего и исходящего трафика пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="8d86b-113">For remote access to work for any edge service, it is mandatory that SIP traffic is allowed to flow bi-directionally as shown in the Inbound/Outbound edge traffic figure.</span></span> <span data-ttu-id="8d86b-114">Другими словами, Обмен сообщениями SIP и из службы Edge для Access осуществляется в обмене мгновенными сообщениями, присутствии, веб-конференциях, аудио-и видеосвязи (A/V) и Федерации.</span><span class="sxs-lookup"><span data-stu-id="8d86b-114">Stated another way, the SIP messaging to and from the Access Edge service is involved in instant messaging (IM), presence, web conferencing, audio/video (A/V), and federation.</span></span>

### <a name="firewall-summary-for-single-consolidated-edge-with-private-ip-addresses-using-nat-external-interface"></a><span data-ttu-id="8d86b-115">Сводка по межсетевому экрану для отдельного консолидированного края с частными IP-адресами с использованием NAT: внешний интерфейс</span><span class="sxs-lookup"><span data-stu-id="8d86b-115">Firewall Summary for Single Consolidated Edge with Private IP Addresses using NAT: External Interface</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8d86b-116">Role/Protocol/TCP/UDP/порт</span><span class="sxs-lookup"><span data-stu-id="8d86b-116">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="8d86b-117">IP-адрес источника</span><span class="sxs-lookup"><span data-stu-id="8d86b-117">Source IP address</span></span></th>
<th><span data-ttu-id="8d86b-118">IP-адрес назначения</span><span class="sxs-lookup"><span data-stu-id="8d86b-118">Destination IP address</span></span></th>
<th><span data-ttu-id="8d86b-119">Примечания.</span><span class="sxs-lookup"><span data-stu-id="8d86b-119">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8d86b-120">КСМПП/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="8d86b-120">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="8d86b-121">Любой</span><span class="sxs-lookup"><span data-stu-id="8d86b-121">Any</span></span></p></td>
<td><p><span data-ttu-id="8d86b-122">Прокси-служба КСМПП (доступ к IP-адресу для общих ресурсов с помощью службы Edge Access)</span><span class="sxs-lookup"><span data-stu-id="8d86b-122">XMPP Proxy service (shares IP address with Access Edge service)</span></span></p></td>
<td><p><span data-ttu-id="8d86b-123">Прокси-служба КСМПП принимает трафик от КСМПП контактов в определенных КСМПП федерациях.</span><span class="sxs-lookup"><span data-stu-id="8d86b-123">XMPP Proxy service accepts traffic from XMPP contacts in defined XMPP federations</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8d86b-124">Access/HTTP/TCP/80</span><span class="sxs-lookup"><span data-stu-id="8d86b-124">Access/HTTP/TCP/80</span></span></p></td>
<td><p><span data-ttu-id="8d86b-125">Служба пограничного доступа к пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="8d86b-125">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="8d86b-126">Любой</span><span class="sxs-lookup"><span data-stu-id="8d86b-126">Any</span></span></p></td>
<td><p><span data-ttu-id="8d86b-127">Проверка отзыва сертификатов и получения CRL</span><span class="sxs-lookup"><span data-stu-id="8d86b-127">Certificate revocation/CRL check and retrieval</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8d86b-128">Access/DNS/TCP/53</span><span class="sxs-lookup"><span data-stu-id="8d86b-128">Access/DNS/TCP/53</span></span></p></td>
<td><p><span data-ttu-id="8d86b-129">Служба пограничного доступа к пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="8d86b-129">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="8d86b-130">Любой</span><span class="sxs-lookup"><span data-stu-id="8d86b-130">Any</span></span></p></td>
<td><p><span data-ttu-id="8d86b-131">Запрос DNS по протоколу TCP</span><span class="sxs-lookup"><span data-stu-id="8d86b-131">DNS query over TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8d86b-132">Access/DNS/UDP/53</span><span class="sxs-lookup"><span data-stu-id="8d86b-132">Access/DNS/UDP/53</span></span></p></td>
<td><p><span data-ttu-id="8d86b-133">Служба пограничного доступа к пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="8d86b-133">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="8d86b-134">Любой</span><span class="sxs-lookup"><span data-stu-id="8d86b-134">Any</span></span></p></td>
<td><p><span data-ttu-id="8d86b-135">Запрос DNS по протоколу UDP</span><span class="sxs-lookup"><span data-stu-id="8d86b-135">DNS query over UDP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8d86b-136">Access/SIP (TLS)/TCP/443</span><span class="sxs-lookup"><span data-stu-id="8d86b-136">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="8d86b-137">Любой</span><span class="sxs-lookup"><span data-stu-id="8d86b-137">Any</span></span></p></td>
<td><p><span data-ttu-id="8d86b-138">Служба пограничного доступа к пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="8d86b-138">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="8d86b-139">Трафик SIP "клиент-сервер" для доступа внешних пользователей</span><span class="sxs-lookup"><span data-stu-id="8d86b-139">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8d86b-140">Access/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="8d86b-140">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="8d86b-141">Любой</span><span class="sxs-lookup"><span data-stu-id="8d86b-141">Any</span></span></p></td>
<td><p><span data-ttu-id="8d86b-142">Служба пограничного доступа к пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="8d86b-142">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="8d86b-143">Для Федеративной и общедоступной службы обмена мгновенными сообщениями с помощью SIP</span><span class="sxs-lookup"><span data-stu-id="8d86b-143">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8d86b-144">Access/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="8d86b-144">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="8d86b-145">Служба пограничного доступа к пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="8d86b-145">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="8d86b-146">Любой</span><span class="sxs-lookup"><span data-stu-id="8d86b-146">Any</span></span></p></td>
<td><p><span data-ttu-id="8d86b-147">Для Федеративной и общедоступной службы обмена мгновенными сообщениями с помощью SIP</span><span class="sxs-lookup"><span data-stu-id="8d86b-147">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8d86b-148">Веб-конференции/PSOM (TLS)/TCP/443</span><span class="sxs-lookup"><span data-stu-id="8d86b-148">Web Conferencing/PSOM(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="8d86b-149">Любой</span><span class="sxs-lookup"><span data-stu-id="8d86b-149">Any</span></span></p></td>
<td><p><span data-ttu-id="8d86b-150">Служба веб-конференций пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="8d86b-150">Edge Server Web Conferencing Edge service</span></span></p></td>
<td><p><span data-ttu-id="8d86b-151">Мультимедиа для веб-конференций</span><span class="sxs-lookup"><span data-stu-id="8d86b-151">Web Conferencing media</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8d86b-152">A/V/RTP/TCP/50000-59,999</span><span class="sxs-lookup"><span data-stu-id="8d86b-152">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="8d86b-153">Служба Edge для пограничного сервера A/V</span><span class="sxs-lookup"><span data-stu-id="8d86b-153">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="8d86b-154">Любой</span><span class="sxs-lookup"><span data-stu-id="8d86b-154">Any</span></span></p></td>
<td><p><span data-ttu-id="8d86b-155">Требуется для Федерации с партнерами, работающими под управлением Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 и Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8d86b-155">Required for federating with partners running Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 and Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8d86b-156">A/V/RTP/UDP/50000-59,999</span><span class="sxs-lookup"><span data-stu-id="8d86b-156">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="8d86b-157">Служба Edge для пограничного сервера A/V</span><span class="sxs-lookup"><span data-stu-id="8d86b-157">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="8d86b-158">Любой</span><span class="sxs-lookup"><span data-stu-id="8d86b-158">Any</span></span></p></td>
<td><p><span data-ttu-id="8d86b-159">Требуется только для Федерации с партнерами, работающими под управлением Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="8d86b-159">Required only for federation with partners running Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8d86b-160">A/V/RTP/TCP/50000-59,999</span><span class="sxs-lookup"><span data-stu-id="8d86b-160">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="8d86b-161">Любой</span><span class="sxs-lookup"><span data-stu-id="8d86b-161">Any</span></span></p></td>
<td><p><span data-ttu-id="8d86b-162">Служба Edge для пограничного сервера A/V</span><span class="sxs-lookup"><span data-stu-id="8d86b-162">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="8d86b-163">Требуется только для Федерации с партнерами, работающими под управлением Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="8d86b-163">Required only for federation with partners running Office Communications Server 2007</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8d86b-164">A/V/RTP/UDP/50000-59,999</span><span class="sxs-lookup"><span data-stu-id="8d86b-164">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="8d86b-165">Любой</span><span class="sxs-lookup"><span data-stu-id="8d86b-165">Any</span></span></p></td>
<td><p><span data-ttu-id="8d86b-166">Служба Edge для пограничного сервера A/V</span><span class="sxs-lookup"><span data-stu-id="8d86b-166">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="8d86b-167">Требуется только для Федерации с партнерами, работающими под управлением Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="8d86b-167">Required only for federation with partners running Office Communications Server 2007</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8d86b-168">A/V/STUN, МСТУРН/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="8d86b-168">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="8d86b-169">Служба Edge для пограничного сервера A/V</span><span class="sxs-lookup"><span data-stu-id="8d86b-169">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="8d86b-170">Любой</span><span class="sxs-lookup"><span data-stu-id="8d86b-170">Any</span></span></p></td>
<td><p><span data-ttu-id="8d86b-171">3478 Outbound используется для определения версии пограничного сервера, с которым обменивается данными Lync Server, а также для мультимедийного трафика от пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="8d86b-171">3478 outbound is used to determine the version of Edge Server that Lync Server is communicating with and also for media traffic from Edge Server-to-Edge Server.</span></span> <span data-ttu-id="8d86b-172">Требуется для Федерации с Lync Server 2010, Windows Live Messenger и Office Communications Server 2007 R2, а также в том случае, если в компании развернуты несколько пулов Edge.</span><span class="sxs-lookup"><span data-stu-id="8d86b-172">Required for federation with Lync Server 2010, Windows Live Messenger, and Office Communications Server 2007 R2, and also if multiple Edge pools are deployed within a company.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8d86b-173">A/V/STUN, МСТУРН/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="8d86b-173">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="8d86b-174">Любой</span><span class="sxs-lookup"><span data-stu-id="8d86b-174">Any</span></span></p></td>
<td><p><span data-ttu-id="8d86b-175">Служба Edge для пограничного сервера A/V</span><span class="sxs-lookup"><span data-stu-id="8d86b-175">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="8d86b-176">STUN/отключите согласование кандидатов по протоколу UDP/3478</span><span class="sxs-lookup"><span data-stu-id="8d86b-176">STUN/TURN negotiation of candidates over UDP/3478</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8d86b-177">A/V/STUN, МСТУРН/TCP/443</span><span class="sxs-lookup"><span data-stu-id="8d86b-177">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="8d86b-178">Любой</span><span class="sxs-lookup"><span data-stu-id="8d86b-178">Any</span></span></p></td>
<td><p><span data-ttu-id="8d86b-179">Служба Edge для пограничного сервера A/V</span><span class="sxs-lookup"><span data-stu-id="8d86b-179">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="8d86b-180">STUN/отключите согласование кандидатов по протоколу TCP/443</span><span class="sxs-lookup"><span data-stu-id="8d86b-180">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8d86b-181">A/V/STUN, МСТУРН/TCP/443</span><span class="sxs-lookup"><span data-stu-id="8d86b-181">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="8d86b-182">Служба Edge для пограничного сервера A/V</span><span class="sxs-lookup"><span data-stu-id="8d86b-182">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="8d86b-183">Любой</span><span class="sxs-lookup"><span data-stu-id="8d86b-183">Any</span></span></p></td>
<td><p><span data-ttu-id="8d86b-184">STUN/отключите согласование кандидатов по протоколу TCP/443</span><span class="sxs-lookup"><span data-stu-id="8d86b-184">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="firewall-summary-for-single-consolidated-edge-with-private-ip-addresses-using-nat-internal-interface"></a><span data-ttu-id="8d86b-185">Сводка по межсетевому экрану для отдельного консолидированного края с частными IP-адресами с использованием NAT: внутренний интерфейс</span><span class="sxs-lookup"><span data-stu-id="8d86b-185">Firewall Summary for Single Consolidated Edge with Private IP Addresses Using NAT: Internal Interface</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8d86b-186">Протокол/TCP или UDP/порт</span><span class="sxs-lookup"><span data-stu-id="8d86b-186">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="8d86b-187">IP-адрес источника</span><span class="sxs-lookup"><span data-stu-id="8d86b-187">Source IP address</span></span></th>
<th><span data-ttu-id="8d86b-188">IP-адрес назначения</span><span class="sxs-lookup"><span data-stu-id="8d86b-188">Destination IP address</span></span></th>
<th><span data-ttu-id="8d86b-189">Комментарии</span><span class="sxs-lookup"><span data-stu-id="8d86b-189">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8d86b-190">КСМПП/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="8d86b-190">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="8d86b-191">Any (может быть определен как IP-адрес сервера Standard Edition, IP-адреса стандартного выпуска или IP-адрес пула, на котором запущена служба шлюза КСМПП).</span><span class="sxs-lookup"><span data-stu-id="8d86b-191">Any (can be defined as Standard Edition server IP, Standard Edition server IP address, or pool IP address running the XMPP Gateway service)</span></span></p></td>
<td><p><span data-ttu-id="8d86b-192">Внутренний интерфейс пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="8d86b-192">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="8d86b-193">Исходящий трафик КСМПП от службы шлюза КСМПП, работающей на сервере переднего плана или в пуле внешних интерфейсов</span><span class="sxs-lookup"><span data-stu-id="8d86b-193">Outbound XMPP traffic from XMPP Gateway service running on Front End Server or Front End pool</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8d86b-194">SIP/MTLS/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="8d86b-194">SIP/MTLS/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="8d86b-195">Any (может быть определено как режиссер, IP-адрес пула режиссера, сервер клиентского доступа или IP-адрес пула переднего плана)</span><span class="sxs-lookup"><span data-stu-id="8d86b-195">Any (can be defined as Director, Director pool IP address, Front End Server or Front End pool IP address)</span></span></p></td>
<td><p><span data-ttu-id="8d86b-196">Внутренний интерфейс пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="8d86b-196">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="8d86b-197">Исходящий трафик SIP (от режиссера, IP-адреса пула, сервера переднего плана или IP-адреса пула переднего плана) к внутреннему интерфейсу пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="8d86b-197">Outbound SIP traffic (from Director, Director pool IP address, Front End Server or Front End pool IP address) to Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8d86b-198">SIP/MTLS/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="8d86b-198">SIP/MTLS/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="8d86b-199">Внутренний интерфейс пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="8d86b-199">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="8d86b-200">Any (может быть определено как режиссер, IP-адрес пула режиссера, сервер клиентского доступа или IP-адрес пула переднего плана)</span><span class="sxs-lookup"><span data-stu-id="8d86b-200">Any (can be defined as Director, Director pool IP address, Front End Server or Front End pool IP address)</span></span></p></td>
<td><p><span data-ttu-id="8d86b-201">Входящий трафик SIP (для режиссера, IP-адреса пула, сервера переднего плана или IP-адреса пула переднего плана) от внутреннего интерфейса пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="8d86b-201">Inbound SIP traffic (to Director, Director pool IP address, Front End Server or Front End pool IP address) from Edge Server internal interface</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8d86b-202">PSOM/MTLS/TCP/8057</span><span class="sxs-lookup"><span data-stu-id="8d86b-202">PSOM/MTLS/TCP/8057</span></span></p></td>
<td><p><span data-ttu-id="8d86b-203">Any (может быть IP-адресом сервера переднего плана или IP-адресом серверного переднего плана в пуле переднего плана)</span><span class="sxs-lookup"><span data-stu-id="8d86b-203">Any (can be defined as Front End Server IP address, or each Front End Server IP address in a Front End pool)</span></span></p></td>
<td><p><span data-ttu-id="8d86b-204">Внутренний интерфейс пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="8d86b-204">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="8d86b-205">Трафик веб-конференций от сервера переднего плана или каждого серверного переднего плана, если он находится в пуле и является внутренним интерфейсом пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="8d86b-205">Web conferencing traffic from Front End Server or each Front End Server if in a pool, to Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8d86b-206">SIP/MTLS/TCP/5062</span><span class="sxs-lookup"><span data-stu-id="8d86b-206">SIP/MTLS/TCP/5062</span></span></p></td>
<td><p><span data-ttu-id="8d86b-207">Any (может быть как IP-адресом переднего сервера, так и IP-адресом пула переднего плана либо любым бесперебойно работающее устройство филиала или с помощью этого пограничного сервера).</span><span class="sxs-lookup"><span data-stu-id="8d86b-207">Any (can be defined as Front End Server IP address, or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server)</span></span></p></td>
<td><p><span data-ttu-id="8d86b-208">Внутренний интерфейс пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="8d86b-208">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="8d86b-209">Проверка подлинности пользователей/V (служба проверки подлинности A/V) от IP-адреса сервера переднего плана или переднего плана, а также от любого работающего филиала или сервера с бесперебойной подразделением с помощью этого пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="8d86b-209">Authentication of A/V users (A/V authentication service) from Front End Server or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8d86b-210">STUN/МСТУРН/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="8d86b-210">STUN/MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="8d86b-211">Любой</span><span class="sxs-lookup"><span data-stu-id="8d86b-211">Any</span></span></p></td>
<td><p><span data-ttu-id="8d86b-212">Внутренний интерфейс пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="8d86b-212">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="8d86b-213">Предпочтительный путь для передачи мультимедиа между внутренними и внешними пользователями, бесперебойно работающем устройстве филиалов или бесперебойно работающем сервере филиала</span><span class="sxs-lookup"><span data-stu-id="8d86b-213">Preferred path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8d86b-214">STUN/МСТУРН/TCP/443</span><span class="sxs-lookup"><span data-stu-id="8d86b-214">STUN/MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="8d86b-215">Любой</span><span class="sxs-lookup"><span data-stu-id="8d86b-215">Any</span></span></p></td>
<td><p><span data-ttu-id="8d86b-216">Внутренний интерфейс пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="8d86b-216">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="8d86b-217">Резервный путь для передачи мультимедиа между внутренними и внешними пользователями, бесперебойно работающее устройство филиала или бесперебойный сервер филиала, если не удается установить UDP-связь, используется протокол TCP для обмена файлами и демонстрации рабочего стола</span><span class="sxs-lookup"><span data-stu-id="8d86b-217">Fallback path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server if UDP communication cannot be established, TCP is used for file transfer and desktop sharing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8d86b-218">HTTPS/TCP/4443</span><span class="sxs-lookup"><span data-stu-id="8d86b-218">HTTPS/TCP/4443</span></span></p></td>
<td><p><span data-ttu-id="8d86b-219">Any (может быть указан в качестве IP-адреса сервера переднего плана или пула, содержащего центральное хранилище управления).</span><span class="sxs-lookup"><span data-stu-id="8d86b-219">Any (can be defined as the Front End Server IP address, or pool that holds the Central Management store)</span></span></p></td>
<td><p><span data-ttu-id="8d86b-220">Внутренний интерфейс пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="8d86b-220">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="8d86b-221">Репликация изменений из хранилища центрального управления на пограничный сервер</span><span class="sxs-lookup"><span data-stu-id="8d86b-221">Replication of changes from the Central Management store to the Edge Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8d86b-222">MTLS/TCP/50001</span><span class="sxs-lookup"><span data-stu-id="8d86b-222">MTLS/TCP/50001</span></span></p></td>
<td><p><span data-ttu-id="8d86b-223">Любой</span><span class="sxs-lookup"><span data-stu-id="8d86b-223">Any</span></span></p></td>
<td><p><span data-ttu-id="8d86b-224">Внутренний интерфейс пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="8d86b-224">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="8d86b-225">Централизованное ведение журналов с помощью команд командной строки Lync Server Management Shell и централизованных служб ведения журнала, Клсконтроллер (Командная строка Клсконтроллер. exe) или агента (Клсажент. exe) и коллекции журналов</span><span class="sxs-lookup"><span data-stu-id="8d86b-225">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8d86b-226">MTLS/TCP/50002</span><span class="sxs-lookup"><span data-stu-id="8d86b-226">MTLS/TCP/50002</span></span></p></td>
<td><p><span data-ttu-id="8d86b-227">Любой</span><span class="sxs-lookup"><span data-stu-id="8d86b-227">Any</span></span></p></td>
<td><p><span data-ttu-id="8d86b-228">Внутренний интерфейс пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="8d86b-228">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="8d86b-229">Централизованное ведение журналов с помощью команд командной строки Lync Server Management Shell и централизованных служб ведения журнала, Клсконтроллер (Командная строка Клсконтроллер. exe) или агента (Клсажент. exe) и коллекции журналов</span><span class="sxs-lookup"><span data-stu-id="8d86b-229">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8d86b-230">MTLS/TCP/50003</span><span class="sxs-lookup"><span data-stu-id="8d86b-230">MTLS/TCP/50003</span></span></p></td>
<td><p><span data-ttu-id="8d86b-231">Любой</span><span class="sxs-lookup"><span data-stu-id="8d86b-231">Any</span></span></p></td>
<td><p><span data-ttu-id="8d86b-232">Внутренний интерфейс пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="8d86b-232">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="8d86b-233">Централизованное ведение журналов с помощью команд командной строки Lync Server Management Shell и централизованных служб ведения журнала, Клсконтроллер (Командная строка Клсконтроллер. exe) или агента (Клсажент. exe) и коллекции журналов</span><span class="sxs-lookup"><span data-stu-id="8d86b-233">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-federation"></a><span data-ttu-id="8d86b-234">Сводка по межсетевому экрану для Федерации</span><span class="sxs-lookup"><span data-stu-id="8d86b-234">Firewall Summary for Federation</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8d86b-235">Role/Protocol/TCP/UDP/порт</span><span class="sxs-lookup"><span data-stu-id="8d86b-235">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="8d86b-236">IP-адрес источника</span><span class="sxs-lookup"><span data-stu-id="8d86b-236">Source IP address</span></span></th>
<th><span data-ttu-id="8d86b-237">IP-адрес назначения</span><span class="sxs-lookup"><span data-stu-id="8d86b-237">Destination IP address</span></span></th>
<th><span data-ttu-id="8d86b-238">Примечания.</span><span class="sxs-lookup"><span data-stu-id="8d86b-238">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8d86b-239">Access/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="8d86b-239">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="8d86b-240">Общедоступный IP-адрес службы пограничного доступа</span><span class="sxs-lookup"><span data-stu-id="8d86b-240">Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="8d86b-241">Любой</span><span class="sxs-lookup"><span data-stu-id="8d86b-241">Any</span></span></p></td>
<td><p><span data-ttu-id="8d86b-242">Для Федеративной и общедоступной службы обмена мгновенными сообщениями с помощью SIP</span><span class="sxs-lookup"><span data-stu-id="8d86b-242">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary--public-instant-messaging-connectivity"></a><span data-ttu-id="8d86b-243">Сводка по брандмауэрам: общедоступная служба обмена мгновенными сообщениями</span><span class="sxs-lookup"><span data-stu-id="8d86b-243">Firewall Summary – Public Instant Messaging Connectivity</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8d86b-244">Role/Protocol/TCP/UDP/порт</span><span class="sxs-lookup"><span data-stu-id="8d86b-244">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="8d86b-245">IP-адрес источника</span><span class="sxs-lookup"><span data-stu-id="8d86b-245">Source IP address</span></span></th>
<th><span data-ttu-id="8d86b-246">IP-адрес назначения</span><span class="sxs-lookup"><span data-stu-id="8d86b-246">Destination IP address</span></span></th>
<th><span data-ttu-id="8d86b-247">Примечания.</span><span class="sxs-lookup"><span data-stu-id="8d86b-247">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8d86b-248">Access/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="8d86b-248">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="8d86b-249">Партнеры по подключению общедоступных мгновенных сообщений</span><span class="sxs-lookup"><span data-stu-id="8d86b-249">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="8d86b-250">Служба пограничного доступа к пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="8d86b-250">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="8d86b-251">Для Федеративной и общедоступной службы обмена мгновенными сообщениями с помощью SIP</span><span class="sxs-lookup"><span data-stu-id="8d86b-251">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8d86b-252">Access/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="8d86b-252">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="8d86b-253">Служба пограничного доступа к пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="8d86b-253">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="8d86b-254">Партнеры по подключению общедоступных мгновенных сообщений</span><span class="sxs-lookup"><span data-stu-id="8d86b-254">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="8d86b-255">Для Федеративной и общедоступной службы обмена мгновенными сообщениями с помощью SIP</span><span class="sxs-lookup"><span data-stu-id="8d86b-255">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8d86b-256">Access/SIP (TLS)/TCP/443</span><span class="sxs-lookup"><span data-stu-id="8d86b-256">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="8d86b-257">Клиенты</span><span class="sxs-lookup"><span data-stu-id="8d86b-257">Clients</span></span></p></td>
<td><p><span data-ttu-id="8d86b-258">Служба пограничного доступа к пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="8d86b-258">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="8d86b-259">Трафик SIP "клиент-сервер" для доступа внешних пользователей</span><span class="sxs-lookup"><span data-stu-id="8d86b-259">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8d86b-260">A/V/RTP/TCP/50000-59,999</span><span class="sxs-lookup"><span data-stu-id="8d86b-260">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="8d86b-261">Служба Edge для пограничного сервера A/V</span><span class="sxs-lookup"><span data-stu-id="8d86b-261">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="8d86b-262">Клиенты Live Messenger</span><span class="sxs-lookup"><span data-stu-id="8d86b-262">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="8d86b-263">Используется для сеансов обмена мгновенными сообщениями с помощью Windows Live Messenger, если настроена служба общего доступа к данным.</span><span class="sxs-lookup"><span data-stu-id="8d86b-263">Used for A/V sessions with Windows Live Messenger if public IM connectivity is configured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8d86b-264">A/V/STUN, МСТУРН/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="8d86b-264">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="8d86b-265">Служба Edge для пограничного сервера A/V</span><span class="sxs-lookup"><span data-stu-id="8d86b-265">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="8d86b-266">Клиенты Live Messenger</span><span class="sxs-lookup"><span data-stu-id="8d86b-266">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="8d86b-267">Требуется для общедоступной службы обмена мгновенными сообщениями в Windows Live Messenger</span><span class="sxs-lookup"><span data-stu-id="8d86b-267">Required for public IM connectivity with Windows Live Messenger</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8d86b-268">A/V/STUN, МСТУРН/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="8d86b-268">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="8d86b-269">Клиенты Live Messenger</span><span class="sxs-lookup"><span data-stu-id="8d86b-269">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="8d86b-270">Служба Edge для пограничного сервера A/V</span><span class="sxs-lookup"><span data-stu-id="8d86b-270">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="8d86b-271">Требуется для общедоступной службы обмена мгновенными сообщениями в Windows Live Messenger</span><span class="sxs-lookup"><span data-stu-id="8d86b-271">Required for public IM connectivity with Windows Live Messenger</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-extensible-messaging-and-presence-protocol"></a><span data-ttu-id="8d86b-272">Сводка брандмауэра по протоколу расширенного обмена сообщениями и присутствия</span><span class="sxs-lookup"><span data-stu-id="8d86b-272">Firewall Summary for Extensible Messaging and Presence Protocol</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8d86b-273">Протокол/TCP или UDP/порт</span><span class="sxs-lookup"><span data-stu-id="8d86b-273">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="8d86b-274">Источник (IP-адрес)</span><span class="sxs-lookup"><span data-stu-id="8d86b-274">Source (IP address)</span></span></th>
<th><span data-ttu-id="8d86b-275">Назначение (IP-адрес)</span><span class="sxs-lookup"><span data-stu-id="8d86b-275">Destination (IP address)</span></span></th>
<th><span data-ttu-id="8d86b-276">Комментарии</span><span class="sxs-lookup"><span data-stu-id="8d86b-276">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8d86b-277">КСМПП/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="8d86b-277">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="8d86b-278">Любой</span><span class="sxs-lookup"><span data-stu-id="8d86b-278">Any</span></span></p></td>
<td><p><span data-ttu-id="8d86b-279">IP-адрес интерфейса службы пограничного доступа к серверу Edge</span><span class="sxs-lookup"><span data-stu-id="8d86b-279">Edge Server Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="8d86b-280">Стандартный коммуникационный порт "сервер-сервер" для КСМПП.</span><span class="sxs-lookup"><span data-stu-id="8d86b-280">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="8d86b-281">Разрешает связь с прокси-сервером пограничного сервера КСМПП от федеративных КСМПП партнеров</span><span class="sxs-lookup"><span data-stu-id="8d86b-281">Allows communication to the Edge Server XMPP proxy from federated XMPP partners</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8d86b-282">КСМПП/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="8d86b-282">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="8d86b-283">IP-адрес интерфейса службы пограничного доступа к серверу Edge</span><span class="sxs-lookup"><span data-stu-id="8d86b-283">Edge Server Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="8d86b-284">Любой</span><span class="sxs-lookup"><span data-stu-id="8d86b-284">Any</span></span></p></td>
<td><p><span data-ttu-id="8d86b-285">Стандартный коммуникационный порт "сервер-сервер" для КСМПП.</span><span class="sxs-lookup"><span data-stu-id="8d86b-285">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="8d86b-286">Разрешает взаимодействие с КСМПП прокси-сервером для федеративных КСМПП партнеров</span><span class="sxs-lookup"><span data-stu-id="8d86b-286">Allows communication from the Edge Server XMPP proxy to federated XMPP partners</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8d86b-287">КСМПП/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="8d86b-287">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="8d86b-288">Любой</span><span class="sxs-lookup"><span data-stu-id="8d86b-288">Any</span></span></p></td>
<td><p><span data-ttu-id="8d86b-289">Каждый внутренний IP-адрес интерфейса пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="8d86b-289">Each internal Edge Server Interface IP</span></span></p></td>
<td><p><span data-ttu-id="8d86b-290">Внутренний IP-адрес КСМПП, входящий в состав шлюза КСМПП на сервере переднего плана или в пуле переднего плана, в адрес внутренней сети пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="8d86b-290">Internal XMPP traffic from the XMPP Gateway on the Front End Server or Front End pool to the Edge Server internal IP address or each Edge pool member’s internal IP address</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

