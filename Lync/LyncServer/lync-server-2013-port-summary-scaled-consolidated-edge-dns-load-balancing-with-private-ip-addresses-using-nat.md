---
title: 'Lync Server 2013: сводка по портам — масштабируемый консолидированный край, балансировка нагрузки на DNS с частными IP-адресами с использованием NAT'
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
ms.openlocfilehash: 7c26dfe63e468d7b8d6f4ae557c0b84af2ffceaa
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42183861"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="port-summary---scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat-in-lync-server-2013"></a><span data-ttu-id="6d22f-102">Сводка по портам — масштабируемый консолидированный край, балансировка нагрузки на DNS с частными IP-адресами с использованием NAT в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6d22f-102">Port summary - Scaled consolidated edge, DNS load balancing with private IP addresses using NAT in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6d22f-103">_**Последнее изменение темы:** 2012-12-04_</span><span class="sxs-lookup"><span data-stu-id="6d22f-103">_**Topic Last Modified:** 2012-12-04_</span></span>

<span data-ttu-id="6d22f-104">Сервер Lync Server 2013, функции пограничного сервера, описанные в этой архитектуре сценариев, очень похожи на компоненты, реализованные в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="6d22f-104">The Lync Server 2013, Edge Server functionality described in this scenario architecture is very similar to what was implemented in Lync Server 2010.</span></span> <span data-ttu-id="6d22f-105">Наиболее значимым дополнением является порт **5269 по протоколу TCP** для поддержки протокола XMPP (расширяемый протокол обмена сообщениями и сведениями о присутствии).</span><span class="sxs-lookup"><span data-stu-id="6d22f-105">The most noticeable addition is the port **5269 over TCP** entry for the extensible messaging and presence protocol (XMPP).</span></span> <span data-ttu-id="6d22f-106">Lync Server 2013 при необходимости разворачивает прокси-сервер XMPP на пограничном или пограничном пуле и на сервере шлюза XMPP на сервере переднего плана или интерфейсном пуле.</span><span class="sxs-lookup"><span data-stu-id="6d22f-106">Lync Server 2013 optionally deploys an XMPP proxy on the Edge Server or Edge pool and the XMPP gateway server on the Front End Server or Front End pool.</span></span>

<span data-ttu-id="6d22f-107">Кроме протокола IPv4, пограничный сервер теперь поддерживает IPv6.</span><span class="sxs-lookup"><span data-stu-id="6d22f-107">In addition to IPv4, the Edge Server now supports IPv6.</span></span> <span data-ttu-id="6d22f-108">Для ясности в этих сценариях используется IPv4.</span><span class="sxs-lookup"><span data-stu-id="6d22f-108">For clarity, only IPv4 is used in the scenarios.</span></span>

<span data-ttu-id="6d22f-109">**Сеть периметра предприятия для масштабируемого консолидированного периметра с частными IP-адресами, использующими NAT**</span><span class="sxs-lookup"><span data-stu-id="6d22f-109">**Enterprise perimeter network for scaled consolidated edge with private IP addresses using NAT**</span></span>

<span data-ttu-id="6d22f-110">![96f5a8f5-16d2-464d-b86e-7c7ecfc89ead](images/JJ205394.96f5a8f5-16d2-464d-b86e-7c7ecfc89ead(OCS.15).jpg "96f5a8f5-16d2-464d-b86e-7c7ecfc89ead")</span><span class="sxs-lookup"><span data-stu-id="6d22f-110">![96f5a8f5-16d2-464d-b86e-7c7ecfc89ead](images/JJ205394.96f5a8f5-16d2-464d-b86e-7c7ecfc89ead(OCS.15).jpg "96f5a8f5-16d2-464d-b86e-7c7ecfc89ead")</span></span>

<div>

## <a name="port-and-protocol-details"></a><span data-ttu-id="6d22f-111">Сведения о портах и протоколе</span><span class="sxs-lookup"><span data-stu-id="6d22f-111">Port and Protocol Details</span></span>

<span data-ttu-id="6d22f-112">Рекомендуется открывать только те порты, которые требуются для поддержки функциональной возможности, к которой предоставляется внешний доступ.</span><span class="sxs-lookup"><span data-stu-id="6d22f-112">It is recommended that you open only the ports required to support the functionality for which you are providing external access.</span></span>

<span data-ttu-id="6d22f-p103">Чтобы удаленный доступ работал для любой пограничной службы, необходимо разрешить трафик SIP в двух направлениях, как показано на рисунке для входящего и исходящего трафика. Иными словами, входящий и исходящий трафик SIP для службы пограничного доступа используется в сеансах обмена мгновенными сообщениями и сведениями о присутствии, веб-конференциях, аудио- и видеоконференциях, а также для функционирования федерации.</span><span class="sxs-lookup"><span data-stu-id="6d22f-p103">For remote access to work for any edge service, it is mandatory that SIP traffic is allowed to flow bi-directionally as shown in the Inbound/Outbound edge traffic figure. Stated another way, the SIP messaging to and from the Access Edge service is involved in instant messaging (IM), presence, web conferencing, audio/video (A/V) and federation.</span></span>

### <a name="firewall-summary-for-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat-external-interface--node-1-and-node-2-example"></a><span data-ttu-id="6d22f-115">Сводка по брандмауэру для масштабируемой консолидированной сети периметра с балансировкой нагрузки на DNS и частными IP-адресами с использованием преобразования сетевых адресов (NAT). Внешний интерфейс – узел 1 и узел 2 (пример)</span><span class="sxs-lookup"><span data-stu-id="6d22f-115">Firewall Summary for Scaled Consolidated Edge, DNS Load Balancing with Private IP Addresses Using NAT: External Interface – Node 1 and Node 2 (Example)</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6d22f-116">Роль/протокол/TCP или UDP/порт</span><span class="sxs-lookup"><span data-stu-id="6d22f-116">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="6d22f-117">Исходный IP-адрес</span><span class="sxs-lookup"><span data-stu-id="6d22f-117">Source IP address</span></span></th>
<th><span data-ttu-id="6d22f-118">Конечный IP-адрес</span><span class="sxs-lookup"><span data-stu-id="6d22f-118">Destination IP address</span></span></th>
<th><span data-ttu-id="6d22f-119">Notes</span><span class="sxs-lookup"><span data-stu-id="6d22f-119">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6d22f-120">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="6d22f-120">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="6d22f-121">Любые</span><span class="sxs-lookup"><span data-stu-id="6d22f-121">Any</span></span></p></td>
<td><p><span data-ttu-id="6d22f-122">Прокси-служба XMPP (общий IP-адрес с пограничной службой доступа)</span><span class="sxs-lookup"><span data-stu-id="6d22f-122">XMPP Proxy service (shares IP address with Access Edge service)</span></span></p></td>
<td><p><span data-ttu-id="6d22f-123">Служба прокси XMPP принимает трафик от контактов XMPP в определенных федерациях XMPP</span><span class="sxs-lookup"><span data-stu-id="6d22f-123">XMPP Proxy service accepts traffic from XMPP contacts in defined XMPP federations</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6d22f-124">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="6d22f-124">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="6d22f-125">Прокси-служба XMPP (общий IP-адрес с пограничной службой доступа)</span><span class="sxs-lookup"><span data-stu-id="6d22f-125">XMPP Proxy service (shares IP address with Access Edge service)</span></span></p></td>
<td><p><span data-ttu-id="6d22f-126">Любые</span><span class="sxs-lookup"><span data-stu-id="6d22f-126">Any</span></span></p></td>
<td><p><span data-ttu-id="6d22f-127">Прокси-служба XMPP отправляет трафик контактам XMPP в определенных федерациях XMPP</span><span class="sxs-lookup"><span data-stu-id="6d22f-127">XMPP Proxy service sends traffic to XMPP contacts in defined XMPP federations</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6d22f-128">Access/HTTP/TCP/80</span><span class="sxs-lookup"><span data-stu-id="6d22f-128">Access/HTTP/TCP/80</span></span></p></td>
<td><p><span data-ttu-id="6d22f-129">Пограничный сервер доступа, пограничная служба доступа</span><span class="sxs-lookup"><span data-stu-id="6d22f-129">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="6d22f-130">Любые</span><span class="sxs-lookup"><span data-stu-id="6d22f-130">Any</span></span></p></td>
<td><p><span data-ttu-id="6d22f-131">Отзыв сертификата/проверка и поиск CRL</span><span class="sxs-lookup"><span data-stu-id="6d22f-131">Certificate revocation/CRL check and retrieval</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6d22f-132">Доступ/DNS/TCP/53</span><span class="sxs-lookup"><span data-stu-id="6d22f-132">Access/DNS/TCP/53</span></span></p></td>
<td><p><span data-ttu-id="6d22f-133">Пограничный сервер доступа, пограничная служба доступа</span><span class="sxs-lookup"><span data-stu-id="6d22f-133">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="6d22f-134">Любые</span><span class="sxs-lookup"><span data-stu-id="6d22f-134">Any</span></span></p></td>
<td><p><span data-ttu-id="6d22f-135">DNS-запрос по протоколу TCP</span><span class="sxs-lookup"><span data-stu-id="6d22f-135">DNS query over TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6d22f-136">Доступ/DNS/UDP/53</span><span class="sxs-lookup"><span data-stu-id="6d22f-136">Access/DNS/UDP/53</span></span></p></td>
<td><p><span data-ttu-id="6d22f-137">Пограничный сервер доступа, пограничная служба доступа</span><span class="sxs-lookup"><span data-stu-id="6d22f-137">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="6d22f-138">Любые</span><span class="sxs-lookup"><span data-stu-id="6d22f-138">Any</span></span></p></td>
<td><p><span data-ttu-id="6d22f-139">DNS-запрос по протоколу UDP</span><span class="sxs-lookup"><span data-stu-id="6d22f-139">DNS query over UDP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6d22f-140">/TCP/443 доступа и SIP (TLS)</span><span class="sxs-lookup"><span data-stu-id="6d22f-140">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="6d22f-141">Любые</span><span class="sxs-lookup"><span data-stu-id="6d22f-141">Any</span></span></p></td>
<td><p><span data-ttu-id="6d22f-142">Пограничный сервер доступа, пограничная служба доступа</span><span class="sxs-lookup"><span data-stu-id="6d22f-142">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="6d22f-143">Трафик SIP «клиент-сервер» для доступа внешних пользователей</span><span class="sxs-lookup"><span data-stu-id="6d22f-143">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6d22f-144">Доступ/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="6d22f-144">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="6d22f-145">Любые</span><span class="sxs-lookup"><span data-stu-id="6d22f-145">Any</span></span></p></td>
<td><p><span data-ttu-id="6d22f-146">Пограничный сервер доступа, пограничная служба доступа</span><span class="sxs-lookup"><span data-stu-id="6d22f-146">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="6d22f-147">Для федеративного подключения и подключения к общедоступным службам обмена мгновенными сообщениями с помощью SIP</span><span class="sxs-lookup"><span data-stu-id="6d22f-147">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6d22f-148">Доступ/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="6d22f-148">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="6d22f-149">Пограничный сервер доступа, пограничная служба доступа</span><span class="sxs-lookup"><span data-stu-id="6d22f-149">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="6d22f-150">Любые</span><span class="sxs-lookup"><span data-stu-id="6d22f-150">Any</span></span></p></td>
<td><p><span data-ttu-id="6d22f-151">Для федеративного подключения и подключения к общедоступным службам обмена мгновенными сообщениями с помощью SIP</span><span class="sxs-lookup"><span data-stu-id="6d22f-151">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6d22f-152">Веб-конференции/PSOM (TLS)/TCP/443</span><span class="sxs-lookup"><span data-stu-id="6d22f-152">Web Conferencing/PSOM(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="6d22f-153">Любые</span><span class="sxs-lookup"><span data-stu-id="6d22f-153">Any</span></span></p></td>
<td><p><span data-ttu-id="6d22f-154">Пограничный сервер, пограничная служба веб-конференций</span><span class="sxs-lookup"><span data-stu-id="6d22f-154">Edge Server Web Conferencing Edge service</span></span></p></td>
<td><p><span data-ttu-id="6d22f-155">Устройство для веб-конференций</span><span class="sxs-lookup"><span data-stu-id="6d22f-155">Web Conferencing media</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6d22f-156">АУДИО-И ВИДЕОДАННЫЕ/RTP/TCP/50000-– 999</span><span class="sxs-lookup"><span data-stu-id="6d22f-156">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="6d22f-157">Пограничный сервер, пограничная служба аудио- и видеоданных</span><span class="sxs-lookup"><span data-stu-id="6d22f-157">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="6d22f-158">Любые</span><span class="sxs-lookup"><span data-stu-id="6d22f-158">Any</span></span></p></td>
<td><p><span data-ttu-id="6d22f-159">Необходимо для Федерации с партнерами, работающими под управлением Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 и Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6d22f-159">Required for federating with partners running Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 and Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6d22f-160">АУДИО-И ВИДЕОДАННЫЕ/RTP/UDP/50000-– 999</span><span class="sxs-lookup"><span data-stu-id="6d22f-160">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="6d22f-161">Пограничный сервер, пограничная служба аудио- и видеоданных</span><span class="sxs-lookup"><span data-stu-id="6d22f-161">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="6d22f-162">Любые</span><span class="sxs-lookup"><span data-stu-id="6d22f-162">Any</span></span></p></td>
<td><p><span data-ttu-id="6d22f-163">Обязательно только для Федерации с партнерами, работающими под управлением Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="6d22f-163">Required only for federation with partners running Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6d22f-164">АУДИО-И ВИДЕОДАННЫЕ/RTP/TCP/50000-– 999</span><span class="sxs-lookup"><span data-stu-id="6d22f-164">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="6d22f-165">Любые</span><span class="sxs-lookup"><span data-stu-id="6d22f-165">Any</span></span></p></td>
<td><p><span data-ttu-id="6d22f-166">Пограничный сервер, пограничная служба аудио- и видеоданных</span><span class="sxs-lookup"><span data-stu-id="6d22f-166">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="6d22f-167">Обязательно только для Федерации с партнерами, работающими под управлением Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="6d22f-167">Required only for federation with partners running Office Communications Server 2007</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6d22f-168">АУДИО-И ВИДЕОДАННЫЕ/RTP/UDP/50000-– 999</span><span class="sxs-lookup"><span data-stu-id="6d22f-168">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="6d22f-169">Любые</span><span class="sxs-lookup"><span data-stu-id="6d22f-169">Any</span></span></p></td>
<td><p><span data-ttu-id="6d22f-170">Пограничный сервер, пограничная служба аудио- и видеоданных</span><span class="sxs-lookup"><span data-stu-id="6d22f-170">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="6d22f-171">Обязательно только для Федерации с партнерами, работающими под управлением Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="6d22f-171">Required only for federation with partners running Office Communications Server 2007</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6d22f-172">АУДИО-И ВИДЕОДАННЫЕ/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="6d22f-172">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="6d22f-173">Пограничный сервер, пограничная служба аудио- и видеоданных</span><span class="sxs-lookup"><span data-stu-id="6d22f-173">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="6d22f-174">Любые</span><span class="sxs-lookup"><span data-stu-id="6d22f-174">Any</span></span></p></td>
<td><p><span data-ttu-id="6d22f-175">3478 исходящие используется для определения версии пограничного сервера, с которым обменивается данными Lync Server, а также для мультимедийного трафика с пограничного сервера на пограничный сервер.</span><span class="sxs-lookup"><span data-stu-id="6d22f-175">3478 outbound is used to determine the version of Edge Server that Lync Server is communicating with and also for media traffic from Edge Server-to-Edge Server.</span></span> <span data-ttu-id="6d22f-176">Обязательно для Федерации с Lync Server 2010, Windows Live Messenger и Office Communications Server 2007 R2, а также при развертывании нескольких пограничных пулов в компании.</span><span class="sxs-lookup"><span data-stu-id="6d22f-176">Required for federation with Lync Server 2010, Windows Live Messenger, and Office Communications Server 2007 R2, and also if multiple Edge pools are deployed within a company.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6d22f-177">АУДИО-И ВИДЕОДАННЫЕ/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="6d22f-177">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="6d22f-178">Любые</span><span class="sxs-lookup"><span data-stu-id="6d22f-178">Any</span></span></p></td>
<td><p><span data-ttu-id="6d22f-179">Пограничный сервер, пограничная служба аудио- и видеоданных</span><span class="sxs-lookup"><span data-stu-id="6d22f-179">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="6d22f-180">STUN/TURN — согласование кандидатов по протоколу UDP/3478</span><span class="sxs-lookup"><span data-stu-id="6d22f-180">STUN/TURN negotiation of candidates over UDP/3478</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6d22f-181">АУДИО-И ВИДЕОДАННЫЕ/STUN, MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="6d22f-181">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="6d22f-182">Любые</span><span class="sxs-lookup"><span data-stu-id="6d22f-182">Any</span></span></p></td>
<td><p><span data-ttu-id="6d22f-183">Пограничный сервер, пограничная служба аудио- и видеоданных</span><span class="sxs-lookup"><span data-stu-id="6d22f-183">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="6d22f-184">STUN/TURN — согласование кандидатов по протоколу TCP/443</span><span class="sxs-lookup"><span data-stu-id="6d22f-184">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6d22f-185">АУДИО-И ВИДЕОДАННЫЕ/STUN, MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="6d22f-185">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="6d22f-186">Пограничный сервер, пограничная служба аудио- и видеоданных</span><span class="sxs-lookup"><span data-stu-id="6d22f-186">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="6d22f-187">Любые</span><span class="sxs-lookup"><span data-stu-id="6d22f-187">Any</span></span></p></td>
<td><p><span data-ttu-id="6d22f-188">Согласование кандидатов STUN/TURN через TCP/443</span><span class="sxs-lookup"><span data-stu-id="6d22f-188">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="firewall-summary-for-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat-internal-interface--node-1-and-node-2-example"></a><span data-ttu-id="6d22f-189">Сводка по брандмауэру для масштабируемой консолидированной сети периметра с балансировкой нагрузки на DNS и частными IP-адресами с использованием преобразования сетевых адресов (NAT). Внутренний интерфейс – узел 1 и узел 2 (пример)</span><span class="sxs-lookup"><span data-stu-id="6d22f-189">Firewall Summary for Scaled Consolidated Edge, DNS Load Balancing with Private IP Addresses Using NAT: Internal Interface – Node 1 and Node 2 (Example)</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6d22f-190">Протокол/TCP или UDP/порт</span><span class="sxs-lookup"><span data-stu-id="6d22f-190">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="6d22f-191">Исходный IP-адрес</span><span class="sxs-lookup"><span data-stu-id="6d22f-191">Source IP address</span></span></th>
<th><span data-ttu-id="6d22f-192">Конечный IP-адрес</span><span class="sxs-lookup"><span data-stu-id="6d22f-192">Destination IP address</span></span></th>
<th><span data-ttu-id="6d22f-193">Комментарии</span><span class="sxs-lookup"><span data-stu-id="6d22f-193">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6d22f-194">XMPP/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="6d22f-194">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="6d22f-195">Любой (может быть определен как адрес сервера переднего плана или IP-адрес пула переднего плана, на котором запущена служба шлюза XMPP)</span><span class="sxs-lookup"><span data-stu-id="6d22f-195">Any (can be defined as Front End Server address, or Front End pool IP address running the XMPP Gateway service)</span></span></p></td>
<td><p><span data-ttu-id="6d22f-196">IP-адрес внутреннего интерфейса пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="6d22f-196">Edge Server internal interface IP address</span></span></p></td>
<td><p><span data-ttu-id="6d22f-197">Исходящий трафик XMPP из службы шлюза XMPP, работающего на сервере переднего плана или интерфейсном пуле</span><span class="sxs-lookup"><span data-stu-id="6d22f-197">Outbound XMPP traffic from XMPP Gateway service running on Front End Server or Front End pool</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6d22f-198">SIP/MTLS/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="6d22f-198">SIP/MTLS/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="6d22f-199">Любой (может быть определен как директор, IP-адрес пула директоров, сервер переднего плана или IP-адрес пула переднего плана).</span><span class="sxs-lookup"><span data-stu-id="6d22f-199">Any (can be defined as Director, Director pool IP address, Front End Server or Front End pool IP address)</span></span></p></td>
<td><p><span data-ttu-id="6d22f-200">Внутренний интерфейс пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="6d22f-200">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="6d22f-201">Исходящий трафик SIP (от директора, IP-адреса пула директоров, сервера переднего плана или IP-адреса пула переднего плана) к внутреннему интерфейсу пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="6d22f-201">Outbound SIP traffic (from Director, Director pool IP address, Front End Server or Front End pool IP address) to Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6d22f-202">SIP/MTLS/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="6d22f-202">SIP/MTLS/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="6d22f-203">Внутренний интерфейс пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="6d22f-203">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="6d22f-204">Любой (может быть определен как директор, IP-адрес пула директоров, сервер переднего плана или IP-адрес пула переднего плана).</span><span class="sxs-lookup"><span data-stu-id="6d22f-204">Any (can be defined as Director, Director pool IP address, Front End Server or Front End pool IP address)</span></span></p></td>
<td><p><span data-ttu-id="6d22f-205">Входящий трафик SIP (в директоре, IP-адрес пула директоров, IP-адрес сервера переднего плана или интерфейсного пула переднего плана) от внутреннего интерфейса пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="6d22f-205">Inbound SIP traffic (to Director, Director pool IP address, Front End Server or Front End pool IP address) from Edge Server internal interface</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6d22f-206">PSOM/MTLS/TCP/8057</span><span class="sxs-lookup"><span data-stu-id="6d22f-206">PSOM/MTLS/TCP/8057</span></span></p></td>
<td><p><span data-ttu-id="6d22f-207">Любой (может быть определен как IP-адрес сервера переднего плана или каждый IP-адрес сервера переднего плана в пуле переднего плана)</span><span class="sxs-lookup"><span data-stu-id="6d22f-207">Any (can be defined as Front End Server IP address, or each Front End Server IP address in a Front End pool)</span></span></p></td>
<td><p><span data-ttu-id="6d22f-208">Внутренний интерфейс пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="6d22f-208">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="6d22f-209">Трафик веб-конференций от сервера переднего плана или сервера переднего плана в пул, внутренний интерфейс пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="6d22f-209">Web conferencing traffic from Front End Server or each Front End Server if in a pool, to Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6d22f-210">SIP/MTLS/TCP/5062</span><span class="sxs-lookup"><span data-stu-id="6d22f-210">SIP/MTLS/TCP/5062</span></span></p></td>
<td><p><span data-ttu-id="6d22f-211">Любой (может быть определен как IP-адрес сервера переднего плана или IP-адрес пула переднего плана или любое устройство для обеспечения связи в филиале или как сервер для обеспечения связи в филиалах с помощью этого пограничного сервера)</span><span class="sxs-lookup"><span data-stu-id="6d22f-211">Any (can be defined as Front End Server IP address, or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server)</span></span></p></td>
<td><p><span data-ttu-id="6d22f-212">Внутренний интерфейс пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="6d22f-212">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="6d22f-213">Проверка подлинности пользователей и подлинности (служба проверки подлинности A/V) с IP-адреса сервера переднего плана или интерфейсного пула или любого устройства для обеспечения связи в филиалах или сервера обеспечения связи в филиалах с помощью этого пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="6d22f-213">Authentication of A/V users (A/V authentication service) from Front End Server or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6d22f-214">STUN/MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="6d22f-214">STUN/MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="6d22f-215">Любые</span><span class="sxs-lookup"><span data-stu-id="6d22f-215">Any</span></span></p></td>
<td><p><span data-ttu-id="6d22f-216">Внутренний интерфейс пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="6d22f-216">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="6d22f-217">Предпочтительный путь для передачи аудио-и видеоданных между внутренними и внешними пользователями, устройством для обеспечения связи в филиалах или сервером обеспечения связи в филиалах</span><span class="sxs-lookup"><span data-stu-id="6d22f-217">Preferred path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6d22f-218">STUN/MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="6d22f-218">STUN/MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="6d22f-219">Любые</span><span class="sxs-lookup"><span data-stu-id="6d22f-219">Any</span></span></p></td>
<td><p><span data-ttu-id="6d22f-220">Внутренний интерфейс пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="6d22f-220">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="6d22f-221">Резервный путь для передачи аудио-и видеоданных между внутренними и внешними пользователями, устройства для обеспечения связи в филиалах или сервера для обеспечения связи в филиалах если не удается установить UDP-связь, используется TCP для передачи файлов и общего доступа к рабочему столу</span><span class="sxs-lookup"><span data-stu-id="6d22f-221">Fallback path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server if UDP communication cannot be established, TCP is used for file transfer and desktop sharing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6d22f-222">HTTPS/TCP/4443</span><span class="sxs-lookup"><span data-stu-id="6d22f-222">HTTPS/TCP/4443</span></span></p></td>
<td><p><span data-ttu-id="6d22f-223">Любой (может быть определен как IP-адрес сервера переднего плана или пул, в котором хранится центральное хранилище управления)</span><span class="sxs-lookup"><span data-stu-id="6d22f-223">Any (can be defined as the Front End Server IP address, or pool that holds the Central Management store)</span></span></p></td>
<td><p><span data-ttu-id="6d22f-224">Внутренний интерфейс пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="6d22f-224">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="6d22f-225">Репликация изменений из центрального хранилища управления на пограничный сервер</span><span class="sxs-lookup"><span data-stu-id="6d22f-225">Replication of changes from the Central Management store to the Edge Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6d22f-226">MTLS/TCP/50001</span><span class="sxs-lookup"><span data-stu-id="6d22f-226">MTLS/TCP/50001</span></span></p></td>
<td><p><span data-ttu-id="6d22f-227">Любые</span><span class="sxs-lookup"><span data-stu-id="6d22f-227">Any</span></span></p></td>
<td><p><span data-ttu-id="6d22f-228">Внутренний интерфейс пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="6d22f-228">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="6d22f-229">Централизованное ведение журналов с помощью команд Командная консоль Lync Server и командлетов службы централизованного ведения журналов, Командная строка ClsController (ClsController. exe) или агента (ClsAgent. exe) и коллекция журналов</span><span class="sxs-lookup"><span data-stu-id="6d22f-229">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6d22f-230">MTLS/TCP/50002</span><span class="sxs-lookup"><span data-stu-id="6d22f-230">MTLS/TCP/50002</span></span></p></td>
<td><p><span data-ttu-id="6d22f-231">Любые</span><span class="sxs-lookup"><span data-stu-id="6d22f-231">Any</span></span></p></td>
<td><p><span data-ttu-id="6d22f-232">Внутренний интерфейс пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="6d22f-232">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="6d22f-233">Централизованное ведение журналов с помощью команд Командная консоль Lync Server и командлетов службы централизованного ведения журналов, Командная строка ClsController (ClsController. exe) или агента (ClsAgent. exe) и коллекция журналов</span><span class="sxs-lookup"><span data-stu-id="6d22f-233">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6d22f-234">MTLS/TCP/50003</span><span class="sxs-lookup"><span data-stu-id="6d22f-234">MTLS/TCP/50003</span></span></p></td>
<td><p><span data-ttu-id="6d22f-235">Любые</span><span class="sxs-lookup"><span data-stu-id="6d22f-235">Any</span></span></p></td>
<td><p><span data-ttu-id="6d22f-236">Внутренний интерфейс пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="6d22f-236">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="6d22f-237">Централизованное ведение журналов с помощью команд Командная консоль Lync Server и командлетов службы централизованного ведения журналов, Командная строка ClsController (ClsController. exe) или агента (ClsAgent. exe) и коллекция журналов</span><span class="sxs-lookup"><span data-stu-id="6d22f-237">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-federation"></a><span data-ttu-id="6d22f-238">Сводка по брандмауэру для федерации</span><span class="sxs-lookup"><span data-stu-id="6d22f-238">Firewall Summary for Federation</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6d22f-239">Роль/протокол/TCP или UDP/порт</span><span class="sxs-lookup"><span data-stu-id="6d22f-239">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="6d22f-240">Исходный IP-адрес</span><span class="sxs-lookup"><span data-stu-id="6d22f-240">Source IP address</span></span></th>
<th><span data-ttu-id="6d22f-241">Конечный IP-адрес</span><span class="sxs-lookup"><span data-stu-id="6d22f-241">Destination IP address</span></span></th>
<th><span data-ttu-id="6d22f-242">Notes</span><span class="sxs-lookup"><span data-stu-id="6d22f-242">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6d22f-243">Доступ/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="6d22f-243">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="6d22f-244">Общедоступный IP-адрес пограничной службы доступа</span><span class="sxs-lookup"><span data-stu-id="6d22f-244">Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="6d22f-245">Любые</span><span class="sxs-lookup"><span data-stu-id="6d22f-245">Any</span></span></p></td>
<td><p><span data-ttu-id="6d22f-246">Для федеративного подключения и подключения к общедоступным службам обмена мгновенными сообщениями с помощью SIP</span><span class="sxs-lookup"><span data-stu-id="6d22f-246">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary--public-instant-messaging-connectivity"></a><span data-ttu-id="6d22f-247">Сводка по брандмауэру — связь с общедоступной службой обмена мгновенными сообщениями</span><span class="sxs-lookup"><span data-stu-id="6d22f-247">Firewall Summary – Public Instant Messaging Connectivity</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6d22f-248">Роль/протокол/TCP или UDP/порт</span><span class="sxs-lookup"><span data-stu-id="6d22f-248">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="6d22f-249">Исходный IP-адрес</span><span class="sxs-lookup"><span data-stu-id="6d22f-249">Source IP address</span></span></th>
<th><span data-ttu-id="6d22f-250">Конечный IP-адрес</span><span class="sxs-lookup"><span data-stu-id="6d22f-250">Destination IP address</span></span></th>
<th><span data-ttu-id="6d22f-251">Notes</span><span class="sxs-lookup"><span data-stu-id="6d22f-251">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6d22f-252">Доступ/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="6d22f-252">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="6d22f-253">Партнеры по связи с общедоступной службой обмена мгновенными сообщениями</span><span class="sxs-lookup"><span data-stu-id="6d22f-253">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="6d22f-254">Пограничный сервер доступа, пограничная служба доступа</span><span class="sxs-lookup"><span data-stu-id="6d22f-254">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="6d22f-255">Для федеративной и общедоступной службы обмена мгновенными сообщениями посредством SIP</span><span class="sxs-lookup"><span data-stu-id="6d22f-255">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6d22f-256">Доступ/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="6d22f-256">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="6d22f-257">Пограничный сервер доступа, пограничная служба доступа</span><span class="sxs-lookup"><span data-stu-id="6d22f-257">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="6d22f-258">Партнеры по связи с общедоступной службой обмена мгновенными сообщениями</span><span class="sxs-lookup"><span data-stu-id="6d22f-258">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="6d22f-259">Для связи с федеративными и общедоступными системами обмена сообщениями через SIP</span><span class="sxs-lookup"><span data-stu-id="6d22f-259">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6d22f-260">/TCP/443 доступа и SIP (TLS)</span><span class="sxs-lookup"><span data-stu-id="6d22f-260">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="6d22f-261">Клиенты</span><span class="sxs-lookup"><span data-stu-id="6d22f-261">Clients</span></span></p></td>
<td><p><span data-ttu-id="6d22f-262">Пограничный сервер доступа, пограничная служба доступа</span><span class="sxs-lookup"><span data-stu-id="6d22f-262">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="6d22f-263">Трафик SIP от клиента к серверу для доступа внешних пользователей</span><span class="sxs-lookup"><span data-stu-id="6d22f-263">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6d22f-264">АУДИО-И ВИДЕОДАННЫЕ/RTP/TCP/50000-– 999</span><span class="sxs-lookup"><span data-stu-id="6d22f-264">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="6d22f-265">Пограничный сервер, пограничная служба аудио- и видеоданных</span><span class="sxs-lookup"><span data-stu-id="6d22f-265">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="6d22f-266">Клиенты Live Messenger</span><span class="sxs-lookup"><span data-stu-id="6d22f-266">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="6d22f-267">Используется для сеансов аудио- и видеоконференций с использованием Windows Live Messenger, если настроена связь с общедоступной службой обмена мгновенными сообщениями.</span><span class="sxs-lookup"><span data-stu-id="6d22f-267">Used for A/V sessions with Windows Live Messenger if public IM connectivity is configured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6d22f-268">АУДИО-И ВИДЕОДАННЫЕ/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="6d22f-268">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="6d22f-269">Пограничный сервер, пограничная служба аудио- и видеоданных</span><span class="sxs-lookup"><span data-stu-id="6d22f-269">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="6d22f-270">Клиенты Live Messenger</span><span class="sxs-lookup"><span data-stu-id="6d22f-270">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="6d22f-271">Требуется для связи с общедоступной службой обмена мгновенными сообщениями с помощью Windows Live Messenger</span><span class="sxs-lookup"><span data-stu-id="6d22f-271">Required for public IM connectivity with Windows Live Messenger</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6d22f-272">АУДИО-И ВИДЕОДАННЫЕ/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="6d22f-272">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="6d22f-273">Клиенты Live Messenger</span><span class="sxs-lookup"><span data-stu-id="6d22f-273">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="6d22f-274">Пограничный сервер, пограничная служба аудио- и видеоданных</span><span class="sxs-lookup"><span data-stu-id="6d22f-274">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="6d22f-275">Требуется для связи с общедоступной службой обмена мгновенными сообщениями с помощью Windows Live Messenger</span><span class="sxs-lookup"><span data-stu-id="6d22f-275">Required for public IM connectivity with Windows Live Messenger</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-extensible-messaging-and-presence-protocol"></a><span data-ttu-id="6d22f-276">Сводка по брандмауэру для протокола XMPP</span><span class="sxs-lookup"><span data-stu-id="6d22f-276">Firewall Summary for Extensible Messaging and Presence Protocol</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6d22f-277">Протокол/TCP или UDP/порт</span><span class="sxs-lookup"><span data-stu-id="6d22f-277">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="6d22f-278">Источник (IP-адрес)</span><span class="sxs-lookup"><span data-stu-id="6d22f-278">Source (IP address)</span></span></th>
<th><span data-ttu-id="6d22f-279">Назначение (IP-адрес)</span><span class="sxs-lookup"><span data-stu-id="6d22f-279">Destination (IP address)</span></span></th>
<th><span data-ttu-id="6d22f-280">Комментарии</span><span class="sxs-lookup"><span data-stu-id="6d22f-280">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6d22f-281">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="6d22f-281">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="6d22f-282">Любые</span><span class="sxs-lookup"><span data-stu-id="6d22f-282">Any</span></span></p></td>
<td><p><span data-ttu-id="6d22f-283">IP-адрес интерфейса пограничного сервера доступа пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="6d22f-283">Edge Server Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="6d22f-284">Стандартный порт для связи "сервер-сервер" через XMPP.</span><span class="sxs-lookup"><span data-stu-id="6d22f-284">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="6d22f-285">Разрешает связь с прокси-сервером пограничного сервера XMPP от федеративных партнеров XMPP</span><span class="sxs-lookup"><span data-stu-id="6d22f-285">Allows communication to the Edge Server XMPP proxy from federated XMPP partners</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6d22f-286">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="6d22f-286">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="6d22f-287">IP-адрес интерфейса пограничного сервера доступа пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="6d22f-287">Edge Server Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="6d22f-288">Любые</span><span class="sxs-lookup"><span data-stu-id="6d22f-288">Any</span></span></p></td>
<td><p><span data-ttu-id="6d22f-289">Стандартный порт для связи "сервер-сервер" через XMPP.</span><span class="sxs-lookup"><span data-stu-id="6d22f-289">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="6d22f-290">Разрешает обмен данными от прокси-сервера пограничного сервера XMPP к федеративным партнерам XMPP</span><span class="sxs-lookup"><span data-stu-id="6d22f-290">Allows communication from the Edge Server XMPP proxy to federated XMPP partners</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6d22f-291">XMPP/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="6d22f-291">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="6d22f-292">Любые</span><span class="sxs-lookup"><span data-stu-id="6d22f-292">Any</span></span></p></td>
<td><p><span data-ttu-id="6d22f-293">Каждый внутренний интерфейсный IP-адрес пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="6d22f-293">Each internal Edge Server interface IP</span></span></p></td>
<td><p><span data-ttu-id="6d22f-294">Внутренний IP-адрес пограничного сервера или пула переднего плана на внутренний IP-адрес пограничного сервера или на каждый внутренний IP-адрес пограничного пула — внутренний IP-адрес XMPP, входящий в шлюз XMPP.</span><span class="sxs-lookup"><span data-stu-id="6d22f-294">Internal XMPP traffic from the XMPP Gateway on the Front End Server or Front End pool to the Edge Server internal IP address or each Edge pool member’s internal IP address</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

