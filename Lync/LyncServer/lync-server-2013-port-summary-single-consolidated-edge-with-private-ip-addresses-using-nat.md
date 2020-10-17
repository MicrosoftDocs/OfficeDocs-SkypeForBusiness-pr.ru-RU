---
title: Сводка по портам — единая консолидированная пограничная с частными IP-адресами с использованием NAT
description: Сводка по портам — единый консолидированный край с частными IP-адресами, использующими NAT.
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
ms.openlocfilehash: a3fc182b9fbbd24d589feb7f73e3c0086fa23152
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48564565"
---
# <a name="port-summary---single-consolidated-edge-with-private-ip-addresses-using-nat-in-lync-server-2013"></a><span data-ttu-id="8af1e-103">Сводка по портам — единый консолидированный край с частными IP-адресами, использующими NAT в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8af1e-103">Port summary - Single consolidated edge with private IP addresses using NAT in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8af1e-104">_**Последнее изменение темы:** 2013-04-03_</span><span class="sxs-lookup"><span data-stu-id="8af1e-104">_**Topic Last Modified:** 2013-04-03_</span></span>

<span data-ttu-id="8af1e-105">Сервер Lync Server 2013, функции пограничного сервера, описанные в этой архитектуре сценариев, очень похожи на компоненты, реализованные в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="8af1e-105">The Lync Server 2013, Edge Server functionality described in this scenario architecture is very similar to what was implemented in Lync Server 2010.</span></span> <span data-ttu-id="8af1e-106">Наиболее значимым дополнением является порт **5269 по протоколу TCP** для поддержки протокола XMPP (расширяемый протокол обмена сообщениями и сведениями о присутствии).</span><span class="sxs-lookup"><span data-stu-id="8af1e-106">The most noticeable addition is the port **5269 over TCP** entry for the extensible messaging and presence protocol (XMPP).</span></span> <span data-ttu-id="8af1e-107">Lync Server 2013 при необходимости разворачивает прокси-сервер XMPP на пограничном или пограничном пуле и на сервере шлюза XMPP на сервере переднего плана или интерфейсном пуле.</span><span class="sxs-lookup"><span data-stu-id="8af1e-107">Lync Server 2013 optionally deploys an XMPP proxy on the Edge Server or Edge pool and the XMPP gateway server on the Front End Server or Front End pool.</span></span>

<span data-ttu-id="8af1e-108">Кроме протокола IPv4, пограничный сервер теперь поддерживает IPv6.</span><span class="sxs-lookup"><span data-stu-id="8af1e-108">In addition to IPv4, the Edge Server now supports IPv6.</span></span> <span data-ttu-id="8af1e-109">Для ясности в этих сценариях используется IPv4.</span><span class="sxs-lookup"><span data-stu-id="8af1e-109">For clarity, only IPv4 is used in the scenarios.</span></span>

<span data-ttu-id="8af1e-110">**Периметр сети для одного консолидированного пограничного сервера с частным IP-адресацией с помощью NAT**</span><span class="sxs-lookup"><span data-stu-id="8af1e-110">**Network Perimeter for a Single Consolidated Edge Server with Private IP Addressing Using NAT**</span></span>

<span data-ttu-id="8af1e-111">![f8c144c5-e5fb-498a-823e-eb39f26b6847](images/Gg425891.f8c144c5-e5fb-498a-823e-eb39f26b6847(OCS.15).jpg "f8c144c5-e5fb-498a-823e-eb39f26b6847")</span><span class="sxs-lookup"><span data-stu-id="8af1e-111">![f8c144c5-e5fb-498a-823e-eb39f26b6847](images/Gg425891.f8c144c5-e5fb-498a-823e-eb39f26b6847(OCS.15).jpg "f8c144c5-e5fb-498a-823e-eb39f26b6847")</span></span>

<div>

## <a name="port-and-protocol-details"></a><span data-ttu-id="8af1e-112">Сведения о портах и протоколе</span><span class="sxs-lookup"><span data-stu-id="8af1e-112">Port and Protocol Details</span></span>

<span data-ttu-id="8af1e-113">Мы рекомендуем вам открывать только те порты, которые обеспечивают поддержку функциональной возможности, для которой вы и предоставляете внешний доступ.</span><span class="sxs-lookup"><span data-stu-id="8af1e-113">We recommend that you open only the ports required to support the functionality for which you are providing external access.</span></span>

<span data-ttu-id="8af1e-p103">Чтобы удаленный доступ работал для любой пограничной службы, следует обязательно разрешить двунаправленное прохождение трафика SIP, как показано на рисунке с пограничным входным/выходным трафиком. Другими словами, обмен SIP-сообщениями с пограничной службой доступа осуществляется при обмене мгновенными сообщениями, использовании сведений о присутствии, во время веб-конференций и аудио- или видеоконференций, а также в рамках федерации.</span><span class="sxs-lookup"><span data-stu-id="8af1e-p103">For remote access to work for any edge service, it is mandatory that SIP traffic is allowed to flow bi-directionally as shown in the Inbound/Outbound edge traffic figure. Stated another way, the SIP messaging to and from the Access Edge service is involved in instant messaging (IM), presence, web conferencing, audio/video (A/V), and federation.</span></span>

### <a name="firewall-summary-for-single-consolidated-edge-with-private-ip-addresses-using-nat-external-interface"></a><span data-ttu-id="8af1e-116">Сводка по брандмауэру для единой и консолидированной среды с частными IP-адресами при использовании NAT — внешний интерфейс</span><span class="sxs-lookup"><span data-stu-id="8af1e-116">Firewall Summary for Single Consolidated Edge with Private IP Addresses using NAT: External Interface</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8af1e-117">Роль/протокол/TCP или UDP/порт</span><span class="sxs-lookup"><span data-stu-id="8af1e-117">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="8af1e-118">Исходный IP-адрес</span><span class="sxs-lookup"><span data-stu-id="8af1e-118">Source IP address</span></span></th>
<th><span data-ttu-id="8af1e-119">Конечный IP-адрес</span><span class="sxs-lookup"><span data-stu-id="8af1e-119">Destination IP address</span></span></th>
<th><span data-ttu-id="8af1e-120">Примечания</span><span class="sxs-lookup"><span data-stu-id="8af1e-120">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8af1e-121">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="8af1e-121">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="8af1e-122">Любой</span><span class="sxs-lookup"><span data-stu-id="8af1e-122">Any</span></span></p></td>
<td><p><span data-ttu-id="8af1e-123">Прокси-служба XMPP (общий IP-адрес с пограничной службой доступа)</span><span class="sxs-lookup"><span data-stu-id="8af1e-123">XMPP Proxy service (shares IP address with Access Edge service)</span></span></p></td>
<td><p><span data-ttu-id="8af1e-124">Служба прокси XMPP принимает трафик от контактов XMPP в определенных федерациях XMPP</span><span class="sxs-lookup"><span data-stu-id="8af1e-124">XMPP Proxy service accepts traffic from XMPP contacts in defined XMPP federations</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8af1e-125">Access/HTTP/TCP/80</span><span class="sxs-lookup"><span data-stu-id="8af1e-125">Access/HTTP/TCP/80</span></span></p></td>
<td><p><span data-ttu-id="8af1e-126">Пограничный сервер доступа, пограничная служба доступа</span><span class="sxs-lookup"><span data-stu-id="8af1e-126">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="8af1e-127">Любой</span><span class="sxs-lookup"><span data-stu-id="8af1e-127">Any</span></span></p></td>
<td><p><span data-ttu-id="8af1e-128">Отзыв сертификата/проверка и поиск CRL</span><span class="sxs-lookup"><span data-stu-id="8af1e-128">Certificate revocation/CRL check and retrieval</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8af1e-129">Доступ/DNS/TCP/53</span><span class="sxs-lookup"><span data-stu-id="8af1e-129">Access/DNS/TCP/53</span></span></p></td>
<td><p><span data-ttu-id="8af1e-130">Пограничный сервер доступа, пограничная служба доступа</span><span class="sxs-lookup"><span data-stu-id="8af1e-130">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="8af1e-131">Любой</span><span class="sxs-lookup"><span data-stu-id="8af1e-131">Any</span></span></p></td>
<td><p><span data-ttu-id="8af1e-132">DNS-запрос по протоколу TCP</span><span class="sxs-lookup"><span data-stu-id="8af1e-132">DNS query over TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8af1e-133">Доступ/DNS/UDP/53</span><span class="sxs-lookup"><span data-stu-id="8af1e-133">Access/DNS/UDP/53</span></span></p></td>
<td><p><span data-ttu-id="8af1e-134">Пограничный сервер доступа, пограничная служба доступа</span><span class="sxs-lookup"><span data-stu-id="8af1e-134">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="8af1e-135">Любой</span><span class="sxs-lookup"><span data-stu-id="8af1e-135">Any</span></span></p></td>
<td><p><span data-ttu-id="8af1e-136">DNS-запрос по протоколу UDP</span><span class="sxs-lookup"><span data-stu-id="8af1e-136">DNS query over UDP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8af1e-137">/TCP/443 доступа и SIP (TLS)</span><span class="sxs-lookup"><span data-stu-id="8af1e-137">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="8af1e-138">Любой</span><span class="sxs-lookup"><span data-stu-id="8af1e-138">Any</span></span></p></td>
<td><p><span data-ttu-id="8af1e-139">Пограничный сервер доступа, пограничная служба доступа</span><span class="sxs-lookup"><span data-stu-id="8af1e-139">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="8af1e-140">Трафик SIP «клиент-сервер» для доступа внешних пользователей</span><span class="sxs-lookup"><span data-stu-id="8af1e-140">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8af1e-141">Доступ/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="8af1e-141">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="8af1e-142">Любой</span><span class="sxs-lookup"><span data-stu-id="8af1e-142">Any</span></span></p></td>
<td><p><span data-ttu-id="8af1e-143">Пограничный сервер доступа, пограничная служба доступа</span><span class="sxs-lookup"><span data-stu-id="8af1e-143">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="8af1e-144">Для федеративного подключения и подключения к общедоступным службам обмена мгновенными сообщениями с помощью SIP</span><span class="sxs-lookup"><span data-stu-id="8af1e-144">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8af1e-145">Доступ/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="8af1e-145">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="8af1e-146">Пограничный сервер доступа, пограничная служба доступа</span><span class="sxs-lookup"><span data-stu-id="8af1e-146">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="8af1e-147">Любой</span><span class="sxs-lookup"><span data-stu-id="8af1e-147">Any</span></span></p></td>
<td><p><span data-ttu-id="8af1e-148">Для федеративного подключения и подключения к общедоступным службам обмена мгновенными сообщениями с помощью SIP</span><span class="sxs-lookup"><span data-stu-id="8af1e-148">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8af1e-149">Веб-конференции/PSOM (TLS)/TCP/443</span><span class="sxs-lookup"><span data-stu-id="8af1e-149">Web Conferencing/PSOM(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="8af1e-150">Любой</span><span class="sxs-lookup"><span data-stu-id="8af1e-150">Any</span></span></p></td>
<td><p><span data-ttu-id="8af1e-151">Пограничный сервер, пограничная служба веб-конференций</span><span class="sxs-lookup"><span data-stu-id="8af1e-151">Edge Server Web Conferencing Edge service</span></span></p></td>
<td><p><span data-ttu-id="8af1e-152">Устройство для веб-конференций</span><span class="sxs-lookup"><span data-stu-id="8af1e-152">Web Conferencing media</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8af1e-153">АУДИО-И ВИДЕОДАННЫЕ/RTP/TCP/50000-– 999</span><span class="sxs-lookup"><span data-stu-id="8af1e-153">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="8af1e-154">Пограничный сервер, пограничная служба аудио- и видеоданных</span><span class="sxs-lookup"><span data-stu-id="8af1e-154">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="8af1e-155">Любой</span><span class="sxs-lookup"><span data-stu-id="8af1e-155">Any</span></span></p></td>
<td><p><span data-ttu-id="8af1e-156">Необходимо для Федерации с партнерами, работающими под управлением Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 и Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8af1e-156">Required for federating with partners running Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 and Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8af1e-157">АУДИО-И ВИДЕОДАННЫЕ/RTP/UDP/50000-– 999</span><span class="sxs-lookup"><span data-stu-id="8af1e-157">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="8af1e-158">Пограничный сервер, пограничная служба аудио- и видеоданных</span><span class="sxs-lookup"><span data-stu-id="8af1e-158">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="8af1e-159">Любой</span><span class="sxs-lookup"><span data-stu-id="8af1e-159">Any</span></span></p></td>
<td><p><span data-ttu-id="8af1e-160">Обязательно только для Федерации с партнерами, работающими под управлением Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="8af1e-160">Required only for federation with partners running Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8af1e-161">АУДИО-И ВИДЕОДАННЫЕ/RTP/TCP/50000-– 999</span><span class="sxs-lookup"><span data-stu-id="8af1e-161">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="8af1e-162">Любой</span><span class="sxs-lookup"><span data-stu-id="8af1e-162">Any</span></span></p></td>
<td><p><span data-ttu-id="8af1e-163">Пограничный сервер, пограничная служба аудио- и видеоданных</span><span class="sxs-lookup"><span data-stu-id="8af1e-163">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="8af1e-164">Обязательно только для Федерации с партнерами, работающими под управлением Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="8af1e-164">Required only for federation with partners running Office Communications Server 2007</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8af1e-165">АУДИО-И ВИДЕОДАННЫЕ/RTP/UDP/50000-– 999</span><span class="sxs-lookup"><span data-stu-id="8af1e-165">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="8af1e-166">Любой</span><span class="sxs-lookup"><span data-stu-id="8af1e-166">Any</span></span></p></td>
<td><p><span data-ttu-id="8af1e-167">Пограничный сервер, пограничная служба аудио- и видеоданных</span><span class="sxs-lookup"><span data-stu-id="8af1e-167">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="8af1e-168">Обязательно только для Федерации с партнерами, работающими под управлением Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="8af1e-168">Required only for federation with partners running Office Communications Server 2007</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8af1e-169">АУДИО-И ВИДЕОДАННЫЕ/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="8af1e-169">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="8af1e-170">Пограничный сервер, пограничная служба аудио- и видеоданных</span><span class="sxs-lookup"><span data-stu-id="8af1e-170">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="8af1e-171">Любой</span><span class="sxs-lookup"><span data-stu-id="8af1e-171">Any</span></span></p></td>
<td><p><span data-ttu-id="8af1e-172">3478 исходящие используется для определения версии пограничного сервера, с которым обменивается данными Lync Server, а также для мультимедийного трафика с пограничного сервера на пограничный сервер.</span><span class="sxs-lookup"><span data-stu-id="8af1e-172">3478 outbound is used to determine the version of Edge Server that Lync Server is communicating with and also for media traffic from Edge Server-to-Edge Server.</span></span> <span data-ttu-id="8af1e-173">Обязательно для Федерации с Lync Server 2010, Windows Live Messenger и Office Communications Server 2007 R2, а также при развертывании нескольких пограничных пулов в компании.</span><span class="sxs-lookup"><span data-stu-id="8af1e-173">Required for federation with Lync Server 2010, Windows Live Messenger, and Office Communications Server 2007 R2, and also if multiple Edge pools are deployed within a company.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8af1e-174">АУДИО-И ВИДЕОДАННЫЕ/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="8af1e-174">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="8af1e-175">Любой</span><span class="sxs-lookup"><span data-stu-id="8af1e-175">Any</span></span></p></td>
<td><p><span data-ttu-id="8af1e-176">Пограничный сервер, пограничная служба аудио- и видеоданных</span><span class="sxs-lookup"><span data-stu-id="8af1e-176">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="8af1e-177">STUN/TURN — согласование кандидатов по протоколу UDP/3478</span><span class="sxs-lookup"><span data-stu-id="8af1e-177">STUN/TURN negotiation of candidates over UDP/3478</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8af1e-178">АУДИО-И ВИДЕОДАННЫЕ/STUN, MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="8af1e-178">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="8af1e-179">Любой</span><span class="sxs-lookup"><span data-stu-id="8af1e-179">Any</span></span></p></td>
<td><p><span data-ttu-id="8af1e-180">Пограничный сервер, пограничная служба аудио- и видеоданных</span><span class="sxs-lookup"><span data-stu-id="8af1e-180">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="8af1e-181">STUN/TURN — согласование кандидатов по протоколу TCP/443</span><span class="sxs-lookup"><span data-stu-id="8af1e-181">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8af1e-182">АУДИО-И ВИДЕОДАННЫЕ/STUN, MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="8af1e-182">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="8af1e-183">Пограничный сервер, пограничная служба аудио- и видеоданных</span><span class="sxs-lookup"><span data-stu-id="8af1e-183">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="8af1e-184">Любой</span><span class="sxs-lookup"><span data-stu-id="8af1e-184">Any</span></span></p></td>
<td><p><span data-ttu-id="8af1e-185">Согласование кандидатов STUN/TURN через TCP/443</span><span class="sxs-lookup"><span data-stu-id="8af1e-185">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="firewall-summary-for-single-consolidated-edge-with-private-ip-addresses-using-nat-internal-interface"></a><span data-ttu-id="8af1e-186">Сводка по брандмауэру для единой и консолидированной среды с частными IP-адресами при использовании NAT — внутренний интерфейс</span><span class="sxs-lookup"><span data-stu-id="8af1e-186">Firewall Summary for Single Consolidated Edge with Private IP Addresses Using NAT: Internal Interface</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8af1e-187">Протокол/TCP или UDP/порт</span><span class="sxs-lookup"><span data-stu-id="8af1e-187">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="8af1e-188">Исходный IP-адрес</span><span class="sxs-lookup"><span data-stu-id="8af1e-188">Source IP address</span></span></th>
<th><span data-ttu-id="8af1e-189">Конечный IP-адрес</span><span class="sxs-lookup"><span data-stu-id="8af1e-189">Destination IP address</span></span></th>
<th><span data-ttu-id="8af1e-190">Comments</span><span class="sxs-lookup"><span data-stu-id="8af1e-190">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8af1e-191">XMPP/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="8af1e-191">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="8af1e-192">Любой (может быть определен как IP-адрес сервера Standard Edition, IP-адрес сервера Standard Edition или IP-адрес пула, на котором запущена служба шлюза XMPP).</span><span class="sxs-lookup"><span data-stu-id="8af1e-192">Any (can be defined as Standard Edition server IP, Standard Edition server IP address, or pool IP address running the XMPP Gateway service)</span></span></p></td>
<td><p><span data-ttu-id="8af1e-193">Внутренний интерфейс пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="8af1e-193">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="8af1e-194">Исходящий трафик XMPP из службы шлюза XMPP, работающего на сервере переднего плана или интерфейсном пуле</span><span class="sxs-lookup"><span data-stu-id="8af1e-194">Outbound XMPP traffic from XMPP Gateway service running on Front End Server or Front End pool</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8af1e-195">SIP/MTLS/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="8af1e-195">SIP/MTLS/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="8af1e-196">Любой (может быть определен как директор, IP-адрес пула директоров, сервер переднего плана или IP-адрес пула переднего плана).</span><span class="sxs-lookup"><span data-stu-id="8af1e-196">Any (can be defined as Director, Director pool IP address, Front End Server or Front End pool IP address)</span></span></p></td>
<td><p><span data-ttu-id="8af1e-197">Внутренний интерфейс пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="8af1e-197">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="8af1e-198">Исходящий трафик SIP (от директора, IP-адреса пула директоров, сервера переднего плана или IP-адреса пула переднего плана) к внутреннему интерфейсу пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="8af1e-198">Outbound SIP traffic (from Director, Director pool IP address, Front End Server or Front End pool IP address) to Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8af1e-199">SIP/MTLS/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="8af1e-199">SIP/MTLS/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="8af1e-200">Внутренний интерфейс пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="8af1e-200">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="8af1e-201">Любой (может быть определен как директор, IP-адрес пула директоров, сервер переднего плана или IP-адрес пула переднего плана).</span><span class="sxs-lookup"><span data-stu-id="8af1e-201">Any (can be defined as Director, Director pool IP address, Front End Server or Front End pool IP address)</span></span></p></td>
<td><p><span data-ttu-id="8af1e-202">Входящий трафик SIP (в директоре, IP-адрес пула директоров, IP-адрес сервера переднего плана или интерфейсного пула переднего плана) от внутреннего интерфейса пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="8af1e-202">Inbound SIP traffic (to Director, Director pool IP address, Front End Server or Front End pool IP address) from Edge Server internal interface</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8af1e-203">PSOM/MTLS/TCP/8057</span><span class="sxs-lookup"><span data-stu-id="8af1e-203">PSOM/MTLS/TCP/8057</span></span></p></td>
<td><p><span data-ttu-id="8af1e-204">Любой (может быть определен как IP-адрес сервера переднего плана или каждый IP-адрес сервера переднего плана в пуле переднего плана)</span><span class="sxs-lookup"><span data-stu-id="8af1e-204">Any (can be defined as Front End Server IP address, or each Front End Server IP address in a Front End pool)</span></span></p></td>
<td><p><span data-ttu-id="8af1e-205">Внутренний интерфейс пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="8af1e-205">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="8af1e-206">Трафик веб-конференций от сервера переднего плана или сервера переднего плана в пул, внутренний интерфейс пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="8af1e-206">Web conferencing traffic from Front End Server or each Front End Server if in a pool, to Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8af1e-207">SIP/MTLS/TCP/5062</span><span class="sxs-lookup"><span data-stu-id="8af1e-207">SIP/MTLS/TCP/5062</span></span></p></td>
<td><p><span data-ttu-id="8af1e-208">Любой (может быть определен как IP-адрес сервера переднего плана или IP-адрес пула переднего плана или любое устройство для обеспечения связи в филиале или как сервер для обеспечения связи в филиалах с помощью этого пограничного сервера)</span><span class="sxs-lookup"><span data-stu-id="8af1e-208">Any (can be defined as Front End Server IP address, or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server)</span></span></p></td>
<td><p><span data-ttu-id="8af1e-209">Внутренний интерфейс пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="8af1e-209">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="8af1e-210">Проверка подлинности пользователей и подлинности (служба проверки подлинности A/V) с IP-адреса сервера переднего плана или интерфейсного пула или любого устройства для обеспечения связи в филиалах или сервера обеспечения связи в филиалах с помощью этого пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="8af1e-210">Authentication of A/V users (A/V authentication service) from Front End Server or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8af1e-211">STUN/MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="8af1e-211">STUN/MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="8af1e-212">Любой</span><span class="sxs-lookup"><span data-stu-id="8af1e-212">Any</span></span></p></td>
<td><p><span data-ttu-id="8af1e-213">Внутренний интерфейс пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="8af1e-213">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="8af1e-214">Предпочтительный путь для передачи аудио-и видеоданных между внутренними и внешними пользователями, устройством для обеспечения связи в филиалах или сервером обеспечения связи в филиалах</span><span class="sxs-lookup"><span data-stu-id="8af1e-214">Preferred path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8af1e-215">STUN/MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="8af1e-215">STUN/MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="8af1e-216">Любой</span><span class="sxs-lookup"><span data-stu-id="8af1e-216">Any</span></span></p></td>
<td><p><span data-ttu-id="8af1e-217">Внутренний интерфейс пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="8af1e-217">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="8af1e-218">Резервный путь для передачи аудио-и видеоданных между внутренними и внешними пользователями, устройства для обеспечения связи в филиалах или сервера для обеспечения связи в филиалах если не удается установить UDP-связь, используется TCP для передачи файлов и общего доступа к рабочему столу</span><span class="sxs-lookup"><span data-stu-id="8af1e-218">Fallback path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server if UDP communication cannot be established, TCP is used for file transfer and desktop sharing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8af1e-219">HTTPS/TCP/4443</span><span class="sxs-lookup"><span data-stu-id="8af1e-219">HTTPS/TCP/4443</span></span></p></td>
<td><p><span data-ttu-id="8af1e-220">Любой (может быть определен как IP-адрес сервера переднего плана или пул, в котором хранится центральное хранилище управления)</span><span class="sxs-lookup"><span data-stu-id="8af1e-220">Any (can be defined as the Front End Server IP address, or pool that holds the Central Management store)</span></span></p></td>
<td><p><span data-ttu-id="8af1e-221">Внутренний интерфейс пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="8af1e-221">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="8af1e-222">Репликация изменений из центрального хранилища управления на пограничный сервер</span><span class="sxs-lookup"><span data-stu-id="8af1e-222">Replication of changes from the Central Management store to the Edge Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8af1e-223">MTLS/TCP/50001</span><span class="sxs-lookup"><span data-stu-id="8af1e-223">MTLS/TCP/50001</span></span></p></td>
<td><p><span data-ttu-id="8af1e-224">Любой</span><span class="sxs-lookup"><span data-stu-id="8af1e-224">Any</span></span></p></td>
<td><p><span data-ttu-id="8af1e-225">Внутренний интерфейс пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="8af1e-225">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="8af1e-226">Централизованное ведение журналов с помощью команд Командная консоль Lync Server и командлетов службы централизованного ведения журналов, Командная строка ClsController (ClsController.exe) или агента (ClsAgent.exe), а также коллекция журналов</span><span class="sxs-lookup"><span data-stu-id="8af1e-226">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8af1e-227">MTLS/TCP/50002</span><span class="sxs-lookup"><span data-stu-id="8af1e-227">MTLS/TCP/50002</span></span></p></td>
<td><p><span data-ttu-id="8af1e-228">Любой</span><span class="sxs-lookup"><span data-stu-id="8af1e-228">Any</span></span></p></td>
<td><p><span data-ttu-id="8af1e-229">Внутренний интерфейс пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="8af1e-229">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="8af1e-230">Централизованное ведение журналов с помощью команд Командная консоль Lync Server и командлетов службы централизованного ведения журналов, Командная строка ClsController (ClsController.exe) или агента (ClsAgent.exe), а также коллекция журналов</span><span class="sxs-lookup"><span data-stu-id="8af1e-230">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8af1e-231">MTLS/TCP/50003</span><span class="sxs-lookup"><span data-stu-id="8af1e-231">MTLS/TCP/50003</span></span></p></td>
<td><p><span data-ttu-id="8af1e-232">Любой</span><span class="sxs-lookup"><span data-stu-id="8af1e-232">Any</span></span></p></td>
<td><p><span data-ttu-id="8af1e-233">Внутренний интерфейс пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="8af1e-233">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="8af1e-234">Централизованное ведение журналов с помощью команд Командная консоль Lync Server и командлетов службы централизованного ведения журналов, Командная строка ClsController (ClsController.exe) или агента (ClsAgent.exe), а также коллекция журналов</span><span class="sxs-lookup"><span data-stu-id="8af1e-234">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-federation"></a><span data-ttu-id="8af1e-235">Сводка по брандмауэру для федерации</span><span class="sxs-lookup"><span data-stu-id="8af1e-235">Firewall Summary for Federation</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8af1e-236">Роль/протокол/TCP или UDP/порт</span><span class="sxs-lookup"><span data-stu-id="8af1e-236">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="8af1e-237">Исходный IP-адрес</span><span class="sxs-lookup"><span data-stu-id="8af1e-237">Source IP address</span></span></th>
<th><span data-ttu-id="8af1e-238">Конечный IP-адрес</span><span class="sxs-lookup"><span data-stu-id="8af1e-238">Destination IP address</span></span></th>
<th><span data-ttu-id="8af1e-239">Примечания</span><span class="sxs-lookup"><span data-stu-id="8af1e-239">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8af1e-240">Доступ/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="8af1e-240">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="8af1e-241">Общедоступный IP-адрес пограничной службы доступа</span><span class="sxs-lookup"><span data-stu-id="8af1e-241">Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="8af1e-242">Любой</span><span class="sxs-lookup"><span data-stu-id="8af1e-242">Any</span></span></p></td>
<td><p><span data-ttu-id="8af1e-243">Для федеративного подключения и подключения к общедоступным службам обмена мгновенными сообщениями с помощью SIP</span><span class="sxs-lookup"><span data-stu-id="8af1e-243">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary--public-instant-messaging-connectivity"></a><span data-ttu-id="8af1e-244">Сводка по брандмауэру — связь с общедоступной службой обмена мгновенными сообщениями</span><span class="sxs-lookup"><span data-stu-id="8af1e-244">Firewall Summary – Public Instant Messaging Connectivity</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8af1e-245">Роль/протокол/TCP или UDP/порт</span><span class="sxs-lookup"><span data-stu-id="8af1e-245">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="8af1e-246">Исходный IP-адрес</span><span class="sxs-lookup"><span data-stu-id="8af1e-246">Source IP address</span></span></th>
<th><span data-ttu-id="8af1e-247">Конечный IP-адрес</span><span class="sxs-lookup"><span data-stu-id="8af1e-247">Destination IP address</span></span></th>
<th><span data-ttu-id="8af1e-248">Примечания</span><span class="sxs-lookup"><span data-stu-id="8af1e-248">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8af1e-249">Доступ/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="8af1e-249">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="8af1e-250">Партнеры по связи с общедоступной службой обмена мгновенными сообщениями</span><span class="sxs-lookup"><span data-stu-id="8af1e-250">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="8af1e-251">Пограничный сервер доступа, пограничная служба доступа</span><span class="sxs-lookup"><span data-stu-id="8af1e-251">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="8af1e-252">Для федеративного подключения и подключения к общедоступным службам обмена мгновенными сообщениями с помощью SIP</span><span class="sxs-lookup"><span data-stu-id="8af1e-252">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8af1e-253">Доступ/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="8af1e-253">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="8af1e-254">Пограничный сервер доступа, пограничная служба доступа</span><span class="sxs-lookup"><span data-stu-id="8af1e-254">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="8af1e-255">Партнеры по связи с общедоступной службой обмена мгновенными сообщениями</span><span class="sxs-lookup"><span data-stu-id="8af1e-255">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="8af1e-256">Для федеративного подключения и подключения к общедоступным службам обмена мгновенными сообщениями с помощью SIP</span><span class="sxs-lookup"><span data-stu-id="8af1e-256">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8af1e-257">/TCP/443 доступа и SIP (TLS)</span><span class="sxs-lookup"><span data-stu-id="8af1e-257">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="8af1e-258">Клиенты</span><span class="sxs-lookup"><span data-stu-id="8af1e-258">Clients</span></span></p></td>
<td><p><span data-ttu-id="8af1e-259">Пограничный сервер доступа, пограничная служба доступа</span><span class="sxs-lookup"><span data-stu-id="8af1e-259">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="8af1e-260">Трафик SIP от клиента к серверу для доступа внешних пользователей</span><span class="sxs-lookup"><span data-stu-id="8af1e-260">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8af1e-261">АУДИО-И ВИДЕОДАННЫЕ/RTP/TCP/50000-– 999</span><span class="sxs-lookup"><span data-stu-id="8af1e-261">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="8af1e-262">Пограничный сервер, пограничная служба аудио- и видеоданных</span><span class="sxs-lookup"><span data-stu-id="8af1e-262">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="8af1e-263">Клиенты Live Messenger</span><span class="sxs-lookup"><span data-stu-id="8af1e-263">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="8af1e-264">Используется для сеансов аудио- и видеоконференций с использованием Windows Live Messenger, если настроена связь с общедоступной службой обмена мгновенными сообщениями.</span><span class="sxs-lookup"><span data-stu-id="8af1e-264">Used for A/V sessions with Windows Live Messenger if public IM connectivity is configured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8af1e-265">АУДИО-И ВИДЕОДАННЫЕ/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="8af1e-265">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="8af1e-266">Пограничный сервер, пограничная служба аудио- и видеоданных</span><span class="sxs-lookup"><span data-stu-id="8af1e-266">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="8af1e-267">Клиенты Live Messenger</span><span class="sxs-lookup"><span data-stu-id="8af1e-267">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="8af1e-268">Требуется для связи с общедоступной службой обмена мгновенными сообщениями с помощью Windows Live Messenger</span><span class="sxs-lookup"><span data-stu-id="8af1e-268">Required for public IM connectivity with Windows Live Messenger</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8af1e-269">АУДИО-И ВИДЕОДАННЫЕ/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="8af1e-269">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="8af1e-270">Клиенты Live Messenger</span><span class="sxs-lookup"><span data-stu-id="8af1e-270">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="8af1e-271">Пограничный сервер, пограничная служба аудио- и видеоданных</span><span class="sxs-lookup"><span data-stu-id="8af1e-271">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="8af1e-272">Требуется для связи с общедоступной службой обмена мгновенными сообщениями с помощью Windows Live Messenger</span><span class="sxs-lookup"><span data-stu-id="8af1e-272">Required for public IM connectivity with Windows Live Messenger</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-extensible-messaging-and-presence-protocol"></a><span data-ttu-id="8af1e-273">Сводка по брандмауэру для протокола XMPP</span><span class="sxs-lookup"><span data-stu-id="8af1e-273">Firewall Summary for Extensible Messaging and Presence Protocol</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8af1e-274">Протокол/TCP или UDP/порт</span><span class="sxs-lookup"><span data-stu-id="8af1e-274">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="8af1e-275">Источник (IP-адрес)</span><span class="sxs-lookup"><span data-stu-id="8af1e-275">Source (IP address)</span></span></th>
<th><span data-ttu-id="8af1e-276">Назначение (IP-адрес)</span><span class="sxs-lookup"><span data-stu-id="8af1e-276">Destination (IP address)</span></span></th>
<th><span data-ttu-id="8af1e-277">Comments</span><span class="sxs-lookup"><span data-stu-id="8af1e-277">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8af1e-278">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="8af1e-278">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="8af1e-279">Любой</span><span class="sxs-lookup"><span data-stu-id="8af1e-279">Any</span></span></p></td>
<td><p><span data-ttu-id="8af1e-280">IP-адрес интерфейса пограничного сервера доступа пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="8af1e-280">Edge Server Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="8af1e-281">Стандартный порт для связи "сервер-сервер" через XMPP.</span><span class="sxs-lookup"><span data-stu-id="8af1e-281">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="8af1e-282">Разрешает связь с прокси-сервером пограничного сервера XMPP от федеративных партнеров XMPP</span><span class="sxs-lookup"><span data-stu-id="8af1e-282">Allows communication to the Edge Server XMPP proxy from federated XMPP partners</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8af1e-283">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="8af1e-283">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="8af1e-284">IP-адрес интерфейса пограничного сервера доступа пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="8af1e-284">Edge Server Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="8af1e-285">Любой</span><span class="sxs-lookup"><span data-stu-id="8af1e-285">Any</span></span></p></td>
<td><p><span data-ttu-id="8af1e-286">Стандартный порт для связи "сервер-сервер" через XMPP.</span><span class="sxs-lookup"><span data-stu-id="8af1e-286">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="8af1e-287">Разрешает обмен данными от прокси-сервера пограничного сервера XMPP к федеративным партнерам XMPP</span><span class="sxs-lookup"><span data-stu-id="8af1e-287">Allows communication from the Edge Server XMPP proxy to federated XMPP partners</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8af1e-288">XMPP/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="8af1e-288">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="8af1e-289">Любой</span><span class="sxs-lookup"><span data-stu-id="8af1e-289">Any</span></span></p></td>
<td><p><span data-ttu-id="8af1e-290">Каждый внутренний интерфейсный IP-адрес пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="8af1e-290">Each internal Edge Server Interface IP</span></span></p></td>
<td><p><span data-ttu-id="8af1e-291">Внутренний IP-адрес пограничного сервера или пула переднего плана на внутренний IP-адрес пограничного сервера или на каждый внутренний IP-адрес пограничного пула — внутренний IP-адрес XMPP, входящий в шлюз XMPP.</span><span class="sxs-lookup"><span data-stu-id="8af1e-291">Internal XMPP traffic from the XMPP Gateway on the Front End Server or Front End pool to the Edge Server internal IP address or each Edge pool member’s internal IP address</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

