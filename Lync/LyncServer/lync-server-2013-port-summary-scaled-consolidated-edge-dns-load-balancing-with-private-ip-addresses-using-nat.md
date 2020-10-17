---
title: 'Lync Server 2013: сводка по портам — масштабируемый консолидированный край, балансировка нагрузки на DNS с частными IP-адресами с использованием NAT'
description: 'Lync Server 2013: сводка по портам — масштабируемый консолидированный край, балансировка нагрузки на DNS с частными IP-адресами с использованием NAT.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Port summary - Scaled consolidated edge, DNS load balancing with private IP addresses using NAT
ms:assetid: a296c2af-54d4-4b4f-9795-9191baf688cb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412756(v=OCS.15)
ms:contentKeyID: 48184955
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e0402b6682e86e5edf263fca78dfbe0f8fa070b4
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48563945"
---
# <a name="port-summary---scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat-in-lync-server-2013"></a><span data-ttu-id="41ade-103">Сводка по портам — масштабируемый консолидированный край, балансировка нагрузки на DNS с частными IP-адресами с использованием NAT в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="41ade-103">Port summary - Scaled consolidated edge, DNS load balancing with private IP addresses using NAT in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="41ade-104">_**Последнее изменение темы:** 2012-12-04_</span><span class="sxs-lookup"><span data-stu-id="41ade-104">_**Topic Last Modified:** 2012-12-04_</span></span>

<span data-ttu-id="41ade-105">Сервер Lync Server 2013, функции пограничного сервера, описанные в этой архитектуре сценариев, очень похожи на компоненты, реализованные в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="41ade-105">The Lync Server 2013, Edge Server functionality described in this scenario architecture is very similar to what was implemented in Lync Server 2010.</span></span> <span data-ttu-id="41ade-106">Наиболее значимым дополнением является порт **5269 по протоколу TCP** для поддержки протокола XMPP (расширяемый протокол обмена сообщениями и сведениями о присутствии).</span><span class="sxs-lookup"><span data-stu-id="41ade-106">The most noticeable addition is the port **5269 over TCP** entry for the extensible messaging and presence protocol (XMPP).</span></span> <span data-ttu-id="41ade-107">Lync Server 2013 при необходимости разворачивает прокси-сервер XMPP на пограничном или пограничном пуле и на сервере шлюза XMPP на сервере переднего плана или интерфейсном пуле.</span><span class="sxs-lookup"><span data-stu-id="41ade-107">Lync Server 2013 optionally deploys an XMPP proxy on the Edge Server or Edge pool and the XMPP gateway server on the Front End Server or Front End pool.</span></span>

<span data-ttu-id="41ade-108">Кроме протокола IPv4, пограничный сервер теперь поддерживает IPv6.</span><span class="sxs-lookup"><span data-stu-id="41ade-108">In addition to IPv4, the Edge Server now supports IPv6.</span></span> <span data-ttu-id="41ade-109">Для ясности в этих сценариях используется IPv4.</span><span class="sxs-lookup"><span data-stu-id="41ade-109">For clarity, only IPv4 is used in the scenarios.</span></span>

<span data-ttu-id="41ade-110">**Сеть периметра предприятия для масштабируемого консолидированного периметра с частными IP-адресами, использующими NAT**</span><span class="sxs-lookup"><span data-stu-id="41ade-110">**Enterprise perimeter network for scaled consolidated edge with private IP addresses using NAT**</span></span>

<span data-ttu-id="41ade-111">![96f5a8f5-16d2-464d-b86e-7c7ecfc89ead](images/JJ205394.96f5a8f5-16d2-464d-b86e-7c7ecfc89ead(OCS.15).jpg "96f5a8f5-16d2-464d-b86e-7c7ecfc89ead")</span><span class="sxs-lookup"><span data-stu-id="41ade-111">![96f5a8f5-16d2-464d-b86e-7c7ecfc89ead](images/JJ205394.96f5a8f5-16d2-464d-b86e-7c7ecfc89ead(OCS.15).jpg "96f5a8f5-16d2-464d-b86e-7c7ecfc89ead")</span></span>

<div>

## <a name="port-and-protocol-details"></a><span data-ttu-id="41ade-112">Сведения о портах и протоколе</span><span class="sxs-lookup"><span data-stu-id="41ade-112">Port and Protocol Details</span></span>

<span data-ttu-id="41ade-113">Рекомендуется открывать только те порты, которые требуются для поддержки функциональной возможности, к которой предоставляется внешний доступ.</span><span class="sxs-lookup"><span data-stu-id="41ade-113">It is recommended that you open only the ports required to support the functionality for which you are providing external access.</span></span>

<span data-ttu-id="41ade-p103">Чтобы удаленный доступ работал для любой пограничной службы, необходимо разрешить трафик SIP в двух направлениях, как показано на рисунке для входящего и исходящего трафика. Иными словами, входящий и исходящий трафик SIP для службы пограничного доступа используется в сеансах обмена мгновенными сообщениями и сведениями о присутствии, веб-конференциях, аудио- и видеоконференциях, а также для функционирования федерации.</span><span class="sxs-lookup"><span data-stu-id="41ade-p103">For remote access to work for any edge service, it is mandatory that SIP traffic is allowed to flow bi-directionally as shown in the Inbound/Outbound edge traffic figure. Stated another way, the SIP messaging to and from the Access Edge service is involved in instant messaging (IM), presence, web conferencing, audio/video (A/V) and federation.</span></span>

### <a name="firewall-summary-for-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat-external-interface--node-1-and-node-2-example"></a><span data-ttu-id="41ade-116">Сводка по брандмауэру для масштабируемой консолидированной сети периметра с балансировкой нагрузки на DNS и частными IP-адресами с использованием преобразования сетевых адресов (NAT). Внешний интерфейс – узел 1 и узел 2 (пример)</span><span class="sxs-lookup"><span data-stu-id="41ade-116">Firewall Summary for Scaled Consolidated Edge, DNS Load Balancing with Private IP Addresses Using NAT: External Interface – Node 1 and Node 2 (Example)</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="41ade-117">Роль/протокол/TCP или UDP/порт</span><span class="sxs-lookup"><span data-stu-id="41ade-117">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="41ade-118">Исходный IP-адрес</span><span class="sxs-lookup"><span data-stu-id="41ade-118">Source IP address</span></span></th>
<th><span data-ttu-id="41ade-119">Конечный IP-адрес</span><span class="sxs-lookup"><span data-stu-id="41ade-119">Destination IP address</span></span></th>
<th><span data-ttu-id="41ade-120">Примечания</span><span class="sxs-lookup"><span data-stu-id="41ade-120">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="41ade-121">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="41ade-121">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="41ade-122">Любой</span><span class="sxs-lookup"><span data-stu-id="41ade-122">Any</span></span></p></td>
<td><p><span data-ttu-id="41ade-123">Прокси-служба XMPP (общий IP-адрес с пограничной службой доступа)</span><span class="sxs-lookup"><span data-stu-id="41ade-123">XMPP Proxy service (shares IP address with Access Edge service)</span></span></p></td>
<td><p><span data-ttu-id="41ade-124">Служба прокси XMPP принимает трафик от контактов XMPP в определенных федерациях XMPP</span><span class="sxs-lookup"><span data-stu-id="41ade-124">XMPP Proxy service accepts traffic from XMPP contacts in defined XMPP federations</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41ade-125">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="41ade-125">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="41ade-126">Прокси-служба XMPP (общий IP-адрес с пограничной службой доступа)</span><span class="sxs-lookup"><span data-stu-id="41ade-126">XMPP Proxy service (shares IP address with Access Edge service)</span></span></p></td>
<td><p><span data-ttu-id="41ade-127">Любой</span><span class="sxs-lookup"><span data-stu-id="41ade-127">Any</span></span></p></td>
<td><p><span data-ttu-id="41ade-128">Прокси-служба XMPP отправляет трафик контактам XMPP в определенных федерациях XMPP</span><span class="sxs-lookup"><span data-stu-id="41ade-128">XMPP Proxy service sends traffic to XMPP contacts in defined XMPP federations</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41ade-129">Access/HTTP/TCP/80</span><span class="sxs-lookup"><span data-stu-id="41ade-129">Access/HTTP/TCP/80</span></span></p></td>
<td><p><span data-ttu-id="41ade-130">Пограничный сервер доступа, пограничная служба доступа</span><span class="sxs-lookup"><span data-stu-id="41ade-130">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="41ade-131">Любой</span><span class="sxs-lookup"><span data-stu-id="41ade-131">Any</span></span></p></td>
<td><p><span data-ttu-id="41ade-132">Отзыв сертификата/проверка и поиск CRL</span><span class="sxs-lookup"><span data-stu-id="41ade-132">Certificate revocation/CRL check and retrieval</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41ade-133">Доступ/DNS/TCP/53</span><span class="sxs-lookup"><span data-stu-id="41ade-133">Access/DNS/TCP/53</span></span></p></td>
<td><p><span data-ttu-id="41ade-134">Пограничный сервер доступа, пограничная служба доступа</span><span class="sxs-lookup"><span data-stu-id="41ade-134">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="41ade-135">Любой</span><span class="sxs-lookup"><span data-stu-id="41ade-135">Any</span></span></p></td>
<td><p><span data-ttu-id="41ade-136">DNS-запрос по протоколу TCP</span><span class="sxs-lookup"><span data-stu-id="41ade-136">DNS query over TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41ade-137">Доступ/DNS/UDP/53</span><span class="sxs-lookup"><span data-stu-id="41ade-137">Access/DNS/UDP/53</span></span></p></td>
<td><p><span data-ttu-id="41ade-138">Пограничный сервер доступа, пограничная служба доступа</span><span class="sxs-lookup"><span data-stu-id="41ade-138">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="41ade-139">Любой</span><span class="sxs-lookup"><span data-stu-id="41ade-139">Any</span></span></p></td>
<td><p><span data-ttu-id="41ade-140">DNS-запрос по протоколу UDP</span><span class="sxs-lookup"><span data-stu-id="41ade-140">DNS query over UDP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41ade-141">/TCP/443 доступа и SIP (TLS)</span><span class="sxs-lookup"><span data-stu-id="41ade-141">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="41ade-142">Любой</span><span class="sxs-lookup"><span data-stu-id="41ade-142">Any</span></span></p></td>
<td><p><span data-ttu-id="41ade-143">Пограничный сервер доступа, пограничная служба доступа</span><span class="sxs-lookup"><span data-stu-id="41ade-143">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="41ade-144">Трафик SIP «клиент-сервер» для доступа внешних пользователей</span><span class="sxs-lookup"><span data-stu-id="41ade-144">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41ade-145">Доступ/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="41ade-145">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="41ade-146">Любой</span><span class="sxs-lookup"><span data-stu-id="41ade-146">Any</span></span></p></td>
<td><p><span data-ttu-id="41ade-147">Пограничный сервер доступа, пограничная служба доступа</span><span class="sxs-lookup"><span data-stu-id="41ade-147">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="41ade-148">Для федеративных и общедоступных служб обмена мгновенными сообщениями с помощью SIP</span><span class="sxs-lookup"><span data-stu-id="41ade-148">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41ade-149">Доступ/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="41ade-149">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="41ade-150">Пограничный сервер доступа, пограничная служба доступа</span><span class="sxs-lookup"><span data-stu-id="41ade-150">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="41ade-151">Любой</span><span class="sxs-lookup"><span data-stu-id="41ade-151">Any</span></span></p></td>
<td><p><span data-ttu-id="41ade-152">Для федеративного подключения и подключения к общедоступным службам обмена мгновенными сообщениями с помощью SIP</span><span class="sxs-lookup"><span data-stu-id="41ade-152">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41ade-153">Веб-конференции/PSOM (TLS)/TCP/443</span><span class="sxs-lookup"><span data-stu-id="41ade-153">Web Conferencing/PSOM(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="41ade-154">Любой</span><span class="sxs-lookup"><span data-stu-id="41ade-154">Any</span></span></p></td>
<td><p><span data-ttu-id="41ade-155">Пограничный сервер, пограничная служба веб-конференций</span><span class="sxs-lookup"><span data-stu-id="41ade-155">Edge Server Web Conferencing Edge service</span></span></p></td>
<td><p><span data-ttu-id="41ade-156">Устройство для веб-конференций</span><span class="sxs-lookup"><span data-stu-id="41ade-156">Web Conferencing media</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41ade-157">АУДИО-И ВИДЕОДАННЫЕ/RTP/TCP/50000-– 999</span><span class="sxs-lookup"><span data-stu-id="41ade-157">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="41ade-158">Пограничный сервер, пограничная служба аудио- и видеоданных</span><span class="sxs-lookup"><span data-stu-id="41ade-158">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="41ade-159">Любой</span><span class="sxs-lookup"><span data-stu-id="41ade-159">Any</span></span></p></td>
<td><p><span data-ttu-id="41ade-160">Необходимо для Федерации с партнерами, работающими под управлением Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 и Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="41ade-160">Required for federating with partners running Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 and Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41ade-161">АУДИО-И ВИДЕОДАННЫЕ/RTP/UDP/50000-– 999</span><span class="sxs-lookup"><span data-stu-id="41ade-161">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="41ade-162">Пограничный сервер, пограничная служба аудио- и видеоданных</span><span class="sxs-lookup"><span data-stu-id="41ade-162">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="41ade-163">Любой</span><span class="sxs-lookup"><span data-stu-id="41ade-163">Any</span></span></p></td>
<td><p><span data-ttu-id="41ade-164">Обязательно только для Федерации с партнерами, работающими под управлением Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="41ade-164">Required only for federation with partners running Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41ade-165">АУДИО-И ВИДЕОДАННЫЕ/RTP/TCP/50000-– 999</span><span class="sxs-lookup"><span data-stu-id="41ade-165">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="41ade-166">Любой</span><span class="sxs-lookup"><span data-stu-id="41ade-166">Any</span></span></p></td>
<td><p><span data-ttu-id="41ade-167">Пограничный сервер, пограничная служба аудио- и видеоданных</span><span class="sxs-lookup"><span data-stu-id="41ade-167">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="41ade-168">Обязательно только для Федерации с партнерами, работающими под управлением Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="41ade-168">Required only for federation with partners running Office Communications Server 2007</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41ade-169">АУДИО-И ВИДЕОДАННЫЕ/RTP/UDP/50000-– 999</span><span class="sxs-lookup"><span data-stu-id="41ade-169">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="41ade-170">Любой</span><span class="sxs-lookup"><span data-stu-id="41ade-170">Any</span></span></p></td>
<td><p><span data-ttu-id="41ade-171">Пограничный сервер, пограничная служба аудио- и видеоданных</span><span class="sxs-lookup"><span data-stu-id="41ade-171">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="41ade-172">Обязательно только для Федерации с партнерами, работающими под управлением Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="41ade-172">Required only for federation with partners running Office Communications Server 2007</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41ade-173">АУДИО-И ВИДЕОДАННЫЕ/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="41ade-173">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="41ade-174">Пограничный сервер, пограничная служба аудио- и видеоданных</span><span class="sxs-lookup"><span data-stu-id="41ade-174">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="41ade-175">Любой</span><span class="sxs-lookup"><span data-stu-id="41ade-175">Any</span></span></p></td>
<td><p><span data-ttu-id="41ade-176">3478 исходящие используется для определения версии пограничного сервера, с которым обменивается данными Lync Server, а также для мультимедийного трафика с пограничного сервера на пограничный сервер.</span><span class="sxs-lookup"><span data-stu-id="41ade-176">3478 outbound is used to determine the version of Edge Server that Lync Server is communicating with and also for media traffic from Edge Server-to-Edge Server.</span></span> <span data-ttu-id="41ade-177">Обязательно для Федерации с Lync Server 2010, Windows Live Messenger и Office Communications Server 2007 R2, а также при развертывании нескольких пограничных пулов в компании.</span><span class="sxs-lookup"><span data-stu-id="41ade-177">Required for federation with Lync Server 2010, Windows Live Messenger, and Office Communications Server 2007 R2, and also if multiple Edge pools are deployed within a company.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41ade-178">АУДИО-И ВИДЕОДАННЫЕ/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="41ade-178">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="41ade-179">Любой</span><span class="sxs-lookup"><span data-stu-id="41ade-179">Any</span></span></p></td>
<td><p><span data-ttu-id="41ade-180">Пограничный сервер, пограничная служба аудио- и видеоданных</span><span class="sxs-lookup"><span data-stu-id="41ade-180">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="41ade-181">STUN/TURN — согласование кандидатов по протоколу UDP/3478</span><span class="sxs-lookup"><span data-stu-id="41ade-181">STUN/TURN negotiation of candidates over UDP/3478</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41ade-182">АУДИО-И ВИДЕОДАННЫЕ/STUN, MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="41ade-182">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="41ade-183">Любой</span><span class="sxs-lookup"><span data-stu-id="41ade-183">Any</span></span></p></td>
<td><p><span data-ttu-id="41ade-184">Пограничный сервер, пограничная служба аудио- и видеоданных</span><span class="sxs-lookup"><span data-stu-id="41ade-184">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="41ade-185">STUN/TURN — согласование кандидатов по протоколу TCP/443</span><span class="sxs-lookup"><span data-stu-id="41ade-185">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41ade-186">АУДИО-И ВИДЕОДАННЫЕ/STUN, MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="41ade-186">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="41ade-187">Пограничный сервер, пограничная служба аудио- и видеоданных</span><span class="sxs-lookup"><span data-stu-id="41ade-187">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="41ade-188">Любой</span><span class="sxs-lookup"><span data-stu-id="41ade-188">Any</span></span></p></td>
<td><p><span data-ttu-id="41ade-189">Согласование кандидатов STUN/TURN через TCP/443</span><span class="sxs-lookup"><span data-stu-id="41ade-189">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="firewall-summary-for-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat-internal-interface--node-1-and-node-2-example"></a><span data-ttu-id="41ade-190">Сводка по брандмауэру для масштабируемой консолидированной сети периметра с балансировкой нагрузки на DNS и частными IP-адресами с использованием преобразования сетевых адресов (NAT). Внутренний интерфейс – узел 1 и узел 2 (пример)</span><span class="sxs-lookup"><span data-stu-id="41ade-190">Firewall Summary for Scaled Consolidated Edge, DNS Load Balancing with Private IP Addresses Using NAT: Internal Interface – Node 1 and Node 2 (Example)</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="41ade-191">Протокол/TCP или UDP/порт</span><span class="sxs-lookup"><span data-stu-id="41ade-191">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="41ade-192">Исходный IP-адрес</span><span class="sxs-lookup"><span data-stu-id="41ade-192">Source IP address</span></span></th>
<th><span data-ttu-id="41ade-193">Конечный IP-адрес</span><span class="sxs-lookup"><span data-stu-id="41ade-193">Destination IP address</span></span></th>
<th><span data-ttu-id="41ade-194">Comments</span><span class="sxs-lookup"><span data-stu-id="41ade-194">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="41ade-195">XMPP/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="41ade-195">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="41ade-196">Любой (может быть определен как адрес сервера переднего плана или IP-адрес пула переднего плана, на котором запущена служба шлюза XMPP)</span><span class="sxs-lookup"><span data-stu-id="41ade-196">Any (can be defined as Front End Server address, or Front End pool IP address running the XMPP Gateway service)</span></span></p></td>
<td><p><span data-ttu-id="41ade-197">IP-адрес внутреннего интерфейса пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="41ade-197">Edge Server internal interface IP address</span></span></p></td>
<td><p><span data-ttu-id="41ade-198">Исходящий трафик XMPP из службы шлюза XMPP, работающего на сервере переднего плана или интерфейсном пуле</span><span class="sxs-lookup"><span data-stu-id="41ade-198">Outbound XMPP traffic from XMPP Gateway service running on Front End Server or Front End pool</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41ade-199">SIP/MTLS/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="41ade-199">SIP/MTLS/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="41ade-200">Любой (может быть определен как директор, IP-адрес пула директоров, сервер переднего плана или IP-адрес пула переднего плана).</span><span class="sxs-lookup"><span data-stu-id="41ade-200">Any (can be defined as Director, Director pool IP address, Front End Server or Front End pool IP address)</span></span></p></td>
<td><p><span data-ttu-id="41ade-201">Внутренний интерфейс пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="41ade-201">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="41ade-202">Исходящий трафик SIP (от директора, IP-адреса пула директоров, сервера переднего плана или IP-адреса пула переднего плана) к внутреннему интерфейсу пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="41ade-202">Outbound SIP traffic (from Director, Director pool IP address, Front End Server or Front End pool IP address) to Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41ade-203">SIP/MTLS/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="41ade-203">SIP/MTLS/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="41ade-204">Внутренний интерфейс пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="41ade-204">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="41ade-205">Любой (может быть определен как директор, IP-адрес пула директоров, сервер переднего плана или IP-адрес пула переднего плана).</span><span class="sxs-lookup"><span data-stu-id="41ade-205">Any (can be defined as Director, Director pool IP address, Front End Server or Front End pool IP address)</span></span></p></td>
<td><p><span data-ttu-id="41ade-206">Входящий трафик SIP (в директоре, IP-адрес пула директоров, IP-адрес сервера переднего плана или интерфейсного пула переднего плана) от внутреннего интерфейса пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="41ade-206">Inbound SIP traffic (to Director, Director pool IP address, Front End Server or Front End pool IP address) from Edge Server internal interface</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41ade-207">PSOM/MTLS/TCP/8057</span><span class="sxs-lookup"><span data-stu-id="41ade-207">PSOM/MTLS/TCP/8057</span></span></p></td>
<td><p><span data-ttu-id="41ade-208">Любой (может быть определен как IP-адрес сервера переднего плана или каждый IP-адрес сервера переднего плана в пуле переднего плана)</span><span class="sxs-lookup"><span data-stu-id="41ade-208">Any (can be defined as Front End Server IP address, or each Front End Server IP address in a Front End pool)</span></span></p></td>
<td><p><span data-ttu-id="41ade-209">Внутренний интерфейс пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="41ade-209">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="41ade-210">Трафик веб-конференций от сервера переднего плана или сервера переднего плана в пул, внутренний интерфейс пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="41ade-210">Web conferencing traffic from Front End Server or each Front End Server if in a pool, to Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41ade-211">SIP/MTLS/TCP/5062</span><span class="sxs-lookup"><span data-stu-id="41ade-211">SIP/MTLS/TCP/5062</span></span></p></td>
<td><p><span data-ttu-id="41ade-212">Любой (может быть определен как IP-адрес сервера переднего плана или IP-адрес пула переднего плана или любое устройство для обеспечения связи в филиале или как сервер для обеспечения связи в филиалах с помощью этого пограничного сервера)</span><span class="sxs-lookup"><span data-stu-id="41ade-212">Any (can be defined as Front End Server IP address, or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server)</span></span></p></td>
<td><p><span data-ttu-id="41ade-213">Внутренний интерфейс пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="41ade-213">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="41ade-214">Проверка подлинности пользователей и подлинности (служба проверки подлинности A/V) с IP-адреса сервера переднего плана или интерфейсного пула или любого устройства для обеспечения связи в филиалах или сервера обеспечения связи в филиалах с помощью этого пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="41ade-214">Authentication of A/V users (A/V authentication service) from Front End Server or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41ade-215">STUN/MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="41ade-215">STUN/MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="41ade-216">Любой</span><span class="sxs-lookup"><span data-stu-id="41ade-216">Any</span></span></p></td>
<td><p><span data-ttu-id="41ade-217">Внутренний интерфейс пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="41ade-217">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="41ade-218">Предпочтительный путь для передачи аудио-и видеоданных между внутренними и внешними пользователями, устройством для обеспечения связи в филиалах или сервером обеспечения связи в филиалах</span><span class="sxs-lookup"><span data-stu-id="41ade-218">Preferred path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41ade-219">STUN/MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="41ade-219">STUN/MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="41ade-220">Любой</span><span class="sxs-lookup"><span data-stu-id="41ade-220">Any</span></span></p></td>
<td><p><span data-ttu-id="41ade-221">Внутренний интерфейс пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="41ade-221">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="41ade-222">Резервный путь для передачи аудио-и видеоданных между внутренними и внешними пользователями, устройства для обеспечения связи в филиалах или сервера для обеспечения связи в филиалах если не удается установить UDP-связь, используется TCP для передачи файлов и общего доступа к рабочему столу</span><span class="sxs-lookup"><span data-stu-id="41ade-222">Fallback path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server if UDP communication cannot be established, TCP is used for file transfer and desktop sharing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41ade-223">HTTPS/TCP/4443</span><span class="sxs-lookup"><span data-stu-id="41ade-223">HTTPS/TCP/4443</span></span></p></td>
<td><p><span data-ttu-id="41ade-224">Любой (может быть определен как IP-адрес сервера переднего плана или пул, в котором хранится центральное хранилище управления)</span><span class="sxs-lookup"><span data-stu-id="41ade-224">Any (can be defined as the Front End Server IP address, or pool that holds the Central Management store)</span></span></p></td>
<td><p><span data-ttu-id="41ade-225">Внутренний интерфейс пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="41ade-225">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="41ade-226">Репликация изменений из центрального хранилища управления на пограничный сервер</span><span class="sxs-lookup"><span data-stu-id="41ade-226">Replication of changes from the Central Management store to the Edge Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41ade-227">MTLS/TCP/50001</span><span class="sxs-lookup"><span data-stu-id="41ade-227">MTLS/TCP/50001</span></span></p></td>
<td><p><span data-ttu-id="41ade-228">Любой</span><span class="sxs-lookup"><span data-stu-id="41ade-228">Any</span></span></p></td>
<td><p><span data-ttu-id="41ade-229">Внутренний интерфейс пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="41ade-229">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="41ade-230">Централизованное ведение журналов с помощью команд Командная консоль Lync Server и командлетов службы централизованного ведения журналов, Командная строка ClsController (ClsController.exe) или агента (ClsAgent.exe), а также коллекция журналов</span><span class="sxs-lookup"><span data-stu-id="41ade-230">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41ade-231">MTLS/TCP/50002</span><span class="sxs-lookup"><span data-stu-id="41ade-231">MTLS/TCP/50002</span></span></p></td>
<td><p><span data-ttu-id="41ade-232">Любой</span><span class="sxs-lookup"><span data-stu-id="41ade-232">Any</span></span></p></td>
<td><p><span data-ttu-id="41ade-233">Внутренний интерфейс пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="41ade-233">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="41ade-234">Централизованное ведение журналов с помощью команд Командная консоль Lync Server и командлетов службы централизованного ведения журналов, Командная строка ClsController (ClsController.exe) или агента (ClsAgent.exe), а также коллекция журналов</span><span class="sxs-lookup"><span data-stu-id="41ade-234">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41ade-235">MTLS/TCP/50003</span><span class="sxs-lookup"><span data-stu-id="41ade-235">MTLS/TCP/50003</span></span></p></td>
<td><p><span data-ttu-id="41ade-236">Любой</span><span class="sxs-lookup"><span data-stu-id="41ade-236">Any</span></span></p></td>
<td><p><span data-ttu-id="41ade-237">Внутренний интерфейс пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="41ade-237">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="41ade-238">Централизованное ведение журналов с помощью команд Командная консоль Lync Server и командлетов службы централизованного ведения журналов, Командная строка ClsController (ClsController.exe) или агента (ClsAgent.exe), а также коллекция журналов</span><span class="sxs-lookup"><span data-stu-id="41ade-238">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-federation"></a><span data-ttu-id="41ade-239">Сводка по брандмауэру для федерации</span><span class="sxs-lookup"><span data-stu-id="41ade-239">Firewall Summary for Federation</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="41ade-240">Роль/протокол/TCP или UDP/порт</span><span class="sxs-lookup"><span data-stu-id="41ade-240">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="41ade-241">Исходный IP-адрес</span><span class="sxs-lookup"><span data-stu-id="41ade-241">Source IP address</span></span></th>
<th><span data-ttu-id="41ade-242">Конечный IP-адрес</span><span class="sxs-lookup"><span data-stu-id="41ade-242">Destination IP address</span></span></th>
<th><span data-ttu-id="41ade-243">Примечания</span><span class="sxs-lookup"><span data-stu-id="41ade-243">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="41ade-244">Доступ/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="41ade-244">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="41ade-245">Общедоступный IP-адрес пограничной службы доступа</span><span class="sxs-lookup"><span data-stu-id="41ade-245">Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="41ade-246">Любой</span><span class="sxs-lookup"><span data-stu-id="41ade-246">Any</span></span></p></td>
<td><p><span data-ttu-id="41ade-247">Для федеративного подключения и подключения к общедоступным службам обмена мгновенными сообщениями с помощью SIP</span><span class="sxs-lookup"><span data-stu-id="41ade-247">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary--public-instant-messaging-connectivity"></a><span data-ttu-id="41ade-248">Сводка по брандмауэру — связь с общедоступной службой обмена мгновенными сообщениями</span><span class="sxs-lookup"><span data-stu-id="41ade-248">Firewall Summary – Public Instant Messaging Connectivity</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="41ade-249">Роль/протокол/TCP или UDP/порт</span><span class="sxs-lookup"><span data-stu-id="41ade-249">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="41ade-250">Исходный IP-адрес</span><span class="sxs-lookup"><span data-stu-id="41ade-250">Source IP address</span></span></th>
<th><span data-ttu-id="41ade-251">Конечный IP-адрес</span><span class="sxs-lookup"><span data-stu-id="41ade-251">Destination IP address</span></span></th>
<th><span data-ttu-id="41ade-252">Примечания</span><span class="sxs-lookup"><span data-stu-id="41ade-252">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="41ade-253">Доступ/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="41ade-253">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="41ade-254">Партнеры по связи с общедоступной службой обмена мгновенными сообщениями</span><span class="sxs-lookup"><span data-stu-id="41ade-254">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="41ade-255">Пограничный сервер доступа, пограничная служба доступа</span><span class="sxs-lookup"><span data-stu-id="41ade-255">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="41ade-256">Для федеративного подключения и подключения к общедоступным службам обмена мгновенными сообщениями с помощью SIP</span><span class="sxs-lookup"><span data-stu-id="41ade-256">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41ade-257">Доступ/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="41ade-257">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="41ade-258">Пограничный сервер доступа, пограничная служба доступа</span><span class="sxs-lookup"><span data-stu-id="41ade-258">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="41ade-259">Партнеры по связи с общедоступной службой обмена мгновенными сообщениями</span><span class="sxs-lookup"><span data-stu-id="41ade-259">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="41ade-260">Для федеративного подключения и подключения к общедоступным службам обмена мгновенными сообщениями с помощью SIP</span><span class="sxs-lookup"><span data-stu-id="41ade-260">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41ade-261">/TCP/443 доступа и SIP (TLS)</span><span class="sxs-lookup"><span data-stu-id="41ade-261">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="41ade-262">Клиенты</span><span class="sxs-lookup"><span data-stu-id="41ade-262">Clients</span></span></p></td>
<td><p><span data-ttu-id="41ade-263">Пограничный сервер доступа, пограничная служба доступа</span><span class="sxs-lookup"><span data-stu-id="41ade-263">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="41ade-264">Трафик SIP от клиента к серверу для доступа внешних пользователей</span><span class="sxs-lookup"><span data-stu-id="41ade-264">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41ade-265">АУДИО-И ВИДЕОДАННЫЕ/RTP/TCP/50000-– 999</span><span class="sxs-lookup"><span data-stu-id="41ade-265">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="41ade-266">Пограничный сервер, пограничная служба аудио- и видеоданных</span><span class="sxs-lookup"><span data-stu-id="41ade-266">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="41ade-267">Клиенты Live Messenger</span><span class="sxs-lookup"><span data-stu-id="41ade-267">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="41ade-268">Используется для сеансов аудио- и видеоконференций с использованием Windows Live Messenger, если настроена связь с общедоступной службой обмена мгновенными сообщениями.</span><span class="sxs-lookup"><span data-stu-id="41ade-268">Used for A/V sessions with Windows Live Messenger if public IM connectivity is configured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41ade-269">АУДИО-И ВИДЕОДАННЫЕ/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="41ade-269">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="41ade-270">Пограничный сервер, пограничная служба аудио- и видеоданных</span><span class="sxs-lookup"><span data-stu-id="41ade-270">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="41ade-271">Клиенты Live Messenger</span><span class="sxs-lookup"><span data-stu-id="41ade-271">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="41ade-272">Требуется для связи с общедоступной службой обмена мгновенными сообщениями с помощью Windows Live Messenger</span><span class="sxs-lookup"><span data-stu-id="41ade-272">Required for public IM connectivity with Windows Live Messenger</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41ade-273">АУДИО-И ВИДЕОДАННЫЕ/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="41ade-273">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="41ade-274">Клиенты Live Messenger</span><span class="sxs-lookup"><span data-stu-id="41ade-274">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="41ade-275">Пограничный сервер, пограничная служба аудио- и видеоданных</span><span class="sxs-lookup"><span data-stu-id="41ade-275">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="41ade-276">Требуется для связи с общедоступной службой обмена мгновенными сообщениями с помощью Windows Live Messenger</span><span class="sxs-lookup"><span data-stu-id="41ade-276">Required for public IM connectivity with Windows Live Messenger</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-extensible-messaging-and-presence-protocol"></a><span data-ttu-id="41ade-277">Сводка по брандмауэру для протокола XMPP</span><span class="sxs-lookup"><span data-stu-id="41ade-277">Firewall Summary for Extensible Messaging and Presence Protocol</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="41ade-278">Протокол/TCP или UDP/порт</span><span class="sxs-lookup"><span data-stu-id="41ade-278">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="41ade-279">Источник (IP-адрес)</span><span class="sxs-lookup"><span data-stu-id="41ade-279">Source (IP address)</span></span></th>
<th><span data-ttu-id="41ade-280">Назначение (IP-адрес)</span><span class="sxs-lookup"><span data-stu-id="41ade-280">Destination (IP address)</span></span></th>
<th><span data-ttu-id="41ade-281">Comments</span><span class="sxs-lookup"><span data-stu-id="41ade-281">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="41ade-282">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="41ade-282">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="41ade-283">Любой</span><span class="sxs-lookup"><span data-stu-id="41ade-283">Any</span></span></p></td>
<td><p><span data-ttu-id="41ade-284">IP-адрес интерфейса пограничного сервера доступа пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="41ade-284">Edge Server Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="41ade-285">Стандартный порт для связи "сервер-сервер" через XMPP.</span><span class="sxs-lookup"><span data-stu-id="41ade-285">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="41ade-286">Разрешает связь с прокси-сервером пограничного сервера XMPP от федеративных партнеров XMPP</span><span class="sxs-lookup"><span data-stu-id="41ade-286">Allows communication to the Edge Server XMPP proxy from federated XMPP partners</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41ade-287">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="41ade-287">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="41ade-288">IP-адрес интерфейса пограничного сервера доступа пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="41ade-288">Edge Server Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="41ade-289">Любой</span><span class="sxs-lookup"><span data-stu-id="41ade-289">Any</span></span></p></td>
<td><p><span data-ttu-id="41ade-290">Стандартный порт для связи "сервер-сервер" через XMPP.</span><span class="sxs-lookup"><span data-stu-id="41ade-290">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="41ade-291">Разрешает обмен данными от прокси-сервера пограничного сервера XMPP к федеративным партнерам XMPP</span><span class="sxs-lookup"><span data-stu-id="41ade-291">Allows communication from the Edge Server XMPP proxy to federated XMPP partners</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41ade-292">XMPP/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="41ade-292">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="41ade-293">Любой</span><span class="sxs-lookup"><span data-stu-id="41ade-293">Any</span></span></p></td>
<td><p><span data-ttu-id="41ade-294">Каждый внутренний интерфейсный IP-адрес пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="41ade-294">Each internal Edge Server interface IP</span></span></p></td>
<td><p><span data-ttu-id="41ade-295">Внутренний IP-адрес пограничного сервера или пула переднего плана на внутренний IP-адрес пограничного сервера или на каждый внутренний IP-адрес пограничного пула — внутренний IP-адрес XMPP, входящий в шлюз XMPP.</span><span class="sxs-lookup"><span data-stu-id="41ade-295">Internal XMPP traffic from the XMPP Gateway on the Front End Server or Front End pool to the Edge Server internal IP address or each Edge pool member’s internal IP address</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

