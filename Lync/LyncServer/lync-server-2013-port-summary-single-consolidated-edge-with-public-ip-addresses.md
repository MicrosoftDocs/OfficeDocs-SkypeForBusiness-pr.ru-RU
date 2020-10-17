---
title: Сводка по портам — единая Объединенная пограничная с общедоступными IP-адресами
description: Сводка по портам — единая Объединенная пограничная с общедоступными IP-адресами.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Port summary - Single consolidated edge with public IP addresses
ms:assetid: 28407acc-8b92-4f78-875c-fd6b4323b602
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204756(v=OCS.15)
ms:contentKeyID: 48183685
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 82ab2d89404fb174994d8e5b798f64bb68768326
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566405"
---
# <a name="port-summary---single-consolidated-edge-with-public-ip-addresses-in-lync-server-2013"></a><span data-ttu-id="1a6df-103">Сводка по портам — единая Объединенная пограничная с общедоступными IP-адресами в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1a6df-103">Port summary - Single consolidated edge with public IP addresses in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1a6df-104">_**Последнее изменение темы:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="1a6df-104">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="1a6df-105">Сервер Lync Server 2013, функции пограничного сервера, описанные в этой архитектуре сценариев, очень похожи на компоненты, реализованные в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="1a6df-105">The Lync Server 2013, Edge Server functionality described in this scenario architecture is very similar to what was implemented in Lync Server 2010.</span></span> <span data-ttu-id="1a6df-106">Наиболее значимым дополнением является порт **5269 по протоколу TCP** для поддержки протокола XMPP (расширяемый протокол обмена сообщениями и сведениями о присутствии).</span><span class="sxs-lookup"><span data-stu-id="1a6df-106">The most noticeable addition is the port **5269 over TCP** entry for the extensible messaging and presence protocol (XMPP).</span></span> <span data-ttu-id="1a6df-107">Lync Server 2013 при необходимости разворачивает прокси-сервер XMPP на пограничном или пограничном пуле и на сервере шлюза XMPP на сервере переднего плана или интерфейсном пуле.</span><span class="sxs-lookup"><span data-stu-id="1a6df-107">Lync Server 2013 optionally deploys an XMPP proxy on the Edge Server or Edge pool and the XMPP gateway server on the Front End Server or Front End pool.</span></span> <span data-ttu-id="1a6df-108">Сведения о планировании для обратного прокси-сервера и Федерации находятся в [сценариях для обратного прокси-сервера в Lync server 2013](lync-server-2013-scenarios-for-reverse-proxy.md) и [планировании SIP, Федерации XMPP и общедоступных мгновенных сообщений в разделах Lync Server 2013](lync-server-2013-planning-for-sip-xmpp-federation-and-public-instant-messaging.md) соответственно.</span><span class="sxs-lookup"><span data-stu-id="1a6df-108">Planning information for the reverse proxy and federation are found in [Scenarios for reverse proxy in Lync Server 2013](lync-server-2013-scenarios-for-reverse-proxy.md) and [Planning for SIP, XMPP federation, and public instant messaging in Lync Server 2013](lync-server-2013-planning-for-sip-xmpp-federation-and-public-instant-messaging.md) sections, respectively.</span></span>

<span data-ttu-id="1a6df-109">Кроме протокола IPv4, пограничный сервер теперь поддерживает IPv6.</span><span class="sxs-lookup"><span data-stu-id="1a6df-109">In addition to IPv4, the Edge Server now supports IPv6.</span></span> <span data-ttu-id="1a6df-110">Для ясности в этих сценариях используется IPv4.</span><span class="sxs-lookup"><span data-stu-id="1a6df-110">For clarity, only IPv4 is used in the scenarios.</span></span>

<span data-ttu-id="1a6df-111">**Сеть периметра предприятия для единого консолидированного пограничного сервера с общедоступными IP-адресами**</span><span class="sxs-lookup"><span data-stu-id="1a6df-111">**Enterprise perimeter network for single consolidated edge with public IP addressing**</span></span>

<span data-ttu-id="1a6df-112">![f8c144c5-e5fb-498a-823e-eb39f26b6847](images/Gg425891.f8c144c5-e5fb-498a-823e-eb39f26b6847(OCS.15).jpg "f8c144c5-e5fb-498a-823e-eb39f26b6847")</span><span class="sxs-lookup"><span data-stu-id="1a6df-112">![f8c144c5-e5fb-498a-823e-eb39f26b6847](images/Gg425891.f8c144c5-e5fb-498a-823e-eb39f26b6847(OCS.15).jpg "f8c144c5-e5fb-498a-823e-eb39f26b6847")</span></span>

<div>

## <a name="port-and-protocol-details"></a><span data-ttu-id="1a6df-113">Сведения о портах и протоколе</span><span class="sxs-lookup"><span data-stu-id="1a6df-113">Port and Protocol Details</span></span>

<span data-ttu-id="1a6df-114">Рекомендуется открывать только те порты, которые требуются для поддержки функциональной возможности, внешний доступ к которой предоставляется.</span><span class="sxs-lookup"><span data-stu-id="1a6df-114">We recommend that you open only the ports required to support the functionality for which you are providing external access.</span></span>

<span data-ttu-id="1a6df-p103">Для предоставления удаленного доступа в целях работы с любой пограничной службой необходимо разрешить двунаправленный трафик SIP, как показано на схеме пограничного входящего/исходящего трафика. Иначе говоря, сообщения SIP, поступающие в пограничную службу доступа и из нее, связаны со службой обмена мгновенными сообщениями и сведениями о присутствии, системой веб-конференций, аудио- и видеосвязи и федерациями.</span><span class="sxs-lookup"><span data-stu-id="1a6df-p103">For remote access to work for any edge service, it is mandatory that SIP traffic is allowed to flow bidirectionally as shown in the Inbound/Outbound edge traffic figure. Stated another way, the SIP messaging to and from the Access Edge service is involved in instant messaging (IM), presence, web conferencing, audio/video (A/V) and federation.</span></span>

### <a name="firewall-summary-for-single-consolidated-edge-with-public-ip-addresses-external-interface"></a><span data-ttu-id="1a6df-117">Сводная информация по брандмауэрам для одного консолидированного пограничного сервера с общедоступными IP-адресами: внешний интерфейс</span><span class="sxs-lookup"><span data-stu-id="1a6df-117">Firewall Summary for Single Consolidated Edge with Public IP Addresses: External Interface</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1a6df-118">Роль/протокол/TCP или UDP/порт</span><span class="sxs-lookup"><span data-stu-id="1a6df-118">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="1a6df-119">Исходный IP-адрес</span><span class="sxs-lookup"><span data-stu-id="1a6df-119">Source IP address</span></span></th>
<th><span data-ttu-id="1a6df-120">Конечный IP-адрес</span><span class="sxs-lookup"><span data-stu-id="1a6df-120">Destination IP address</span></span></th>
<th><span data-ttu-id="1a6df-121">Примечания</span><span class="sxs-lookup"><span data-stu-id="1a6df-121">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1a6df-122">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="1a6df-122">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="1a6df-123">Любой</span><span class="sxs-lookup"><span data-stu-id="1a6df-123">Any</span></span></p></td>
<td><p><span data-ttu-id="1a6df-124">Прокси-служба XMPP (общий IP-адрес с пограничной службой доступа)</span><span class="sxs-lookup"><span data-stu-id="1a6df-124">XMPP Proxy service (shares IP address with Access Edge service)</span></span></p></td>
<td><p><span data-ttu-id="1a6df-125">Служба прокси XMPP принимает трафик от контактов XMPP в определенных федерациях XMPP</span><span class="sxs-lookup"><span data-stu-id="1a6df-125">XMPP Proxy service accepts traffic from XMPP contacts in defined XMPP federations</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1a6df-126">Access/HTTP/TCP/80</span><span class="sxs-lookup"><span data-stu-id="1a6df-126">Access/HTTP/TCP/80</span></span></p></td>
<td><p><span data-ttu-id="1a6df-127">Общедоступный IP-адрес пограничной службы доступа пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="1a6df-127">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="1a6df-128">Любой</span><span class="sxs-lookup"><span data-stu-id="1a6df-128">Any</span></span></p></td>
<td><p><span data-ttu-id="1a6df-129">Отзыв сертификата/проверка и поиск CRL</span><span class="sxs-lookup"><span data-stu-id="1a6df-129">Certificate revocation/CRL check and retrieval</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1a6df-130">Доступ/DNS/TCP/53</span><span class="sxs-lookup"><span data-stu-id="1a6df-130">Access/DNS/TCP/53</span></span></p></td>
<td><p><span data-ttu-id="1a6df-131">Общедоступный IP-адрес пограничной службы доступа пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="1a6df-131">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="1a6df-132">Любой</span><span class="sxs-lookup"><span data-stu-id="1a6df-132">Any</span></span></p></td>
<td><p><span data-ttu-id="1a6df-133">DNS-запрос по протоколу TCP</span><span class="sxs-lookup"><span data-stu-id="1a6df-133">DNS query over TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1a6df-134">Доступ/DNS/UDP/53</span><span class="sxs-lookup"><span data-stu-id="1a6df-134">Access/DNS/UDP/53</span></span></p></td>
<td><p><span data-ttu-id="1a6df-135">Общедоступный IP-адрес пограничной службы доступа пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="1a6df-135">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="1a6df-136">Любой</span><span class="sxs-lookup"><span data-stu-id="1a6df-136">Any</span></span></p></td>
<td><p><span data-ttu-id="1a6df-137">DNS-запрос по протоколу UDP</span><span class="sxs-lookup"><span data-stu-id="1a6df-137">DNS query over UDP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1a6df-138">/TCP/443 доступа и SIP (TLS)</span><span class="sxs-lookup"><span data-stu-id="1a6df-138">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="1a6df-139">Любой</span><span class="sxs-lookup"><span data-stu-id="1a6df-139">Any</span></span></p></td>
<td><p><span data-ttu-id="1a6df-140">Общедоступный IP-адрес пограничной службы доступа пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="1a6df-140">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="1a6df-141">Трафик SIP «клиент-сервер» для доступа внешних пользователей</span><span class="sxs-lookup"><span data-stu-id="1a6df-141">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1a6df-142">Доступ/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="1a6df-142">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="1a6df-143">Любой</span><span class="sxs-lookup"><span data-stu-id="1a6df-143">Any</span></span></p></td>
<td><p><span data-ttu-id="1a6df-144">Общедоступный IP-адрес пограничной службы доступа пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="1a6df-144">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="1a6df-145">Для федеративного подключения и подключения к общедоступным службам обмена мгновенными сообщениями с помощью SIP</span><span class="sxs-lookup"><span data-stu-id="1a6df-145">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1a6df-146">Доступ/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="1a6df-146">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="1a6df-147">Общедоступный IP-адрес пограничной службы доступа пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="1a6df-147">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="1a6df-148">Любой</span><span class="sxs-lookup"><span data-stu-id="1a6df-148">Any</span></span></p></td>
<td><p><span data-ttu-id="1a6df-149">Для федеративного подключения и подключения к общедоступным службам обмена мгновенными сообщениями с помощью SIP</span><span class="sxs-lookup"><span data-stu-id="1a6df-149">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1a6df-150">Веб-конференции/PSOM (TLS)/TCP/443</span><span class="sxs-lookup"><span data-stu-id="1a6df-150">Web Conferencing/PSOM(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="1a6df-151">Любой</span><span class="sxs-lookup"><span data-stu-id="1a6df-151">Any</span></span></p></td>
<td><p><span data-ttu-id="1a6df-152">Общедоступный IP-адрес службы веб-конференций пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="1a6df-152">Edge Server Web Conferencing Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="1a6df-153">Устройство для веб-конференций</span><span class="sxs-lookup"><span data-stu-id="1a6df-153">Web Conferencing media</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1a6df-154">АУДИО-И ВИДЕОДАННЫЕ/RTP/TCP/50000-– 999</span><span class="sxs-lookup"><span data-stu-id="1a6df-154">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="1a6df-155">Общедоступный IP-адрес пограничной службы доступа пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="1a6df-155">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="1a6df-156">Любой</span><span class="sxs-lookup"><span data-stu-id="1a6df-156">Any</span></span></p></td>
<td><p><span data-ttu-id="1a6df-157">Необходимо для Федерации с партнерами, работающими под управлением Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 и Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1a6df-157">Required for federating with partners running Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 and Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1a6df-158">АУДИО-И ВИДЕОДАННЫЕ/RTP/UDP/50000-– 999</span><span class="sxs-lookup"><span data-stu-id="1a6df-158">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="1a6df-159">Общедоступный IP-адрес пограничного сервера аудио-и пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="1a6df-159">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="1a6df-160">Любой</span><span class="sxs-lookup"><span data-stu-id="1a6df-160">Any</span></span></p></td>
<td><p><span data-ttu-id="1a6df-161">Обязательно только для Федерации с партнерами, работающими под управлением Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="1a6df-161">Required only for federation with partners running Office Communications Server 2007</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1a6df-162">АУДИО-И ВИДЕОДАННЫЕ/RTP/TCP/50000-– 999</span><span class="sxs-lookup"><span data-stu-id="1a6df-162">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="1a6df-163">Любой</span><span class="sxs-lookup"><span data-stu-id="1a6df-163">Any</span></span></p></td>
<td><p><span data-ttu-id="1a6df-164">Общедоступный IP-адрес пограничного сервера аудио-и пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="1a6df-164">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="1a6df-165">Обязательно только для Федерации с партнерами, работающими под управлением Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="1a6df-165">Required only for federation with partners running Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1a6df-166">АУДИО-И ВИДЕОДАННЫЕ/RTP/UDP/50000-– 999</span><span class="sxs-lookup"><span data-stu-id="1a6df-166">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="1a6df-167">Любой</span><span class="sxs-lookup"><span data-stu-id="1a6df-167">Any</span></span></p></td>
<td><p><span data-ttu-id="1a6df-168">Общедоступный IP-адрес пограничного сервера аудио-и пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="1a6df-168">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="1a6df-169">Обязательно только для Федерации с партнерами, работающими под управлением Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="1a6df-169">Required only for federation with partners running Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1a6df-170">АУДИО-И ВИДЕОДАННЫЕ/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="1a6df-170">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="1a6df-171">Общедоступный IP-адрес пограничного сервера аудио-и пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="1a6df-171">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="1a6df-172">Любой</span><span class="sxs-lookup"><span data-stu-id="1a6df-172">Any</span></span></p></td>
<td><p><span data-ttu-id="1a6df-173">3478 исходящие используется для определения версии пограничного сервера, с которым обменивается данными Lync Server, а также для мультимедийного трафика с пограничного сервера на пограничный сервер.</span><span class="sxs-lookup"><span data-stu-id="1a6df-173">3478 outbound is used to determine the version of Edge Server that Lync Server is communicating with and also for media traffic from Edge Server-to-Edge Server.</span></span> <span data-ttu-id="1a6df-174">Обязательно для Федерации с Lync Server 2010, Windows Live Messenger и Office Communications Server 2007 R2, а также при развертывании нескольких пограничных пулов в компании.</span><span class="sxs-lookup"><span data-stu-id="1a6df-174">Required for federation with Lync Server 2010, Windows Live Messenger, and Office Communications Server 2007 R2, and also if multiple Edge pools are deployed within a company.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1a6df-175">АУДИО-И ВИДЕОДАННЫЕ/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="1a6df-175">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="1a6df-176">Любой</span><span class="sxs-lookup"><span data-stu-id="1a6df-176">Any</span></span></p></td>
<td><p><span data-ttu-id="1a6df-177">Общедоступный IP-адрес пограничного сервера аудио-и пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="1a6df-177">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="1a6df-178">STUN/TURN — согласование кандидатов по протоколу UDP/3478</span><span class="sxs-lookup"><span data-stu-id="1a6df-178">STUN/TURN negotiation of candidates over UDP/3478</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1a6df-179">АУДИО-И ВИДЕОДАННЫЕ/STUN, MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="1a6df-179">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="1a6df-180">Любой</span><span class="sxs-lookup"><span data-stu-id="1a6df-180">Any</span></span></p></td>
<td><p><span data-ttu-id="1a6df-181">Общедоступный IP-адрес пограничного сервера аудио-и пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="1a6df-181">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="1a6df-182">STUN/TURN — согласование кандидатов по протоколу TCP/443</span><span class="sxs-lookup"><span data-stu-id="1a6df-182">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1a6df-183">АУДИО-И ВИДЕОДАННЫЕ/STUN, MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="1a6df-183">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="1a6df-184">Общедоступный IP-адрес пограничного сервера аудио-и пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="1a6df-184">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="1a6df-185">Любой</span><span class="sxs-lookup"><span data-stu-id="1a6df-185">Any</span></span></p></td>
<td><p><span data-ttu-id="1a6df-186">STUN/TURN — согласование кандидатов по протоколу TCP/443</span><span class="sxs-lookup"><span data-stu-id="1a6df-186">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="firewall-summary-for-single-consolidated-edge-with-public-ip-addresses-internal-interface"></a><span data-ttu-id="1a6df-187">Сводная информация по брандмауэрам для одного консолидированного пограничного сервера с общедоступными IP-адресами: внутренний интерфейс</span><span class="sxs-lookup"><span data-stu-id="1a6df-187">Firewall Summary for Single Consolidated Edge with Public IP Addresses: Internal Interface</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1a6df-188">Протокол/TCP или UDP/порт</span><span class="sxs-lookup"><span data-stu-id="1a6df-188">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="1a6df-189">Исходный IP-адрес</span><span class="sxs-lookup"><span data-stu-id="1a6df-189">Source IP address</span></span></th>
<th><span data-ttu-id="1a6df-190">Конечный IP-адрес</span><span class="sxs-lookup"><span data-stu-id="1a6df-190">Destination IP address</span></span></th>
<th><span data-ttu-id="1a6df-191">Comments</span><span class="sxs-lookup"><span data-stu-id="1a6df-191">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1a6df-192">XMPP/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="1a6df-192">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="1a6df-193">Любой (может быть определен как IP-адрес сервера Standard Edition, IP-адрес сервера Standard Edition или IP-адрес пула, на котором запущена служба шлюза XMPP).</span><span class="sxs-lookup"><span data-stu-id="1a6df-193">Any (can be defined as Standard Edition server IP, Standard Edition server IP address, or pool IP address running the XMPP Gateway service)</span></span></p></td>
<td><p><span data-ttu-id="1a6df-194">Внутренний интерфейс пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="1a6df-194">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="1a6df-195">Исходящий трафик XMPP из службы шлюза XMPP, работающего на сервере переднего плана или интерфейсном пуле</span><span class="sxs-lookup"><span data-stu-id="1a6df-195">Outbound XMPP traffic from XMPP Gateway service running on Front End Server or Front End pool</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1a6df-196">SIP/MTLS/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="1a6df-196">SIP/MTLS/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="1a6df-197">Любой (может быть определен как директор, IP-адрес пула директоров, сервер переднего плана или IP-адрес пула переднего плана).</span><span class="sxs-lookup"><span data-stu-id="1a6df-197">Any (can be defined as Director, Director pool IP address, Front End Server or Front End pool IP address)</span></span></p></td>
<td><p><span data-ttu-id="1a6df-198">IP-адрес пограничного сервера или пул, в котором хранится внутренний интерфейс</span><span class="sxs-lookup"><span data-stu-id="1a6df-198">Edge Server IP, or pool that holds the internal interface</span></span></p></td>
<td><p><span data-ttu-id="1a6df-199">Исходящий трафик SIP (от директора, IP-адреса пула директоров, сервера переднего плана или IP-адреса пула переднего плана) к внутреннему интерфейсу пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="1a6df-199">Outbound SIP traffic (from Director, Director pool IP address, Front End Server or Front End pool IP address) to Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1a6df-200">SIP/MTLS/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="1a6df-200">SIP/MTLS/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="1a6df-201">Внутренний интерфейс пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="1a6df-201">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="1a6df-202">Любой (может быть определен как директор, IP-адрес пула директоров, сервер переднего плана или адрес внешнего интерфейса пула)</span><span class="sxs-lookup"><span data-stu-id="1a6df-202">Any (can be defined as Director, Director pool IP address, Front End Server or Front End pool address)</span></span></p></td>
<td><p><span data-ttu-id="1a6df-203">Входящий трафик SIP (в директоре, IP-адрес пула директоров, IP-адрес сервера переднего плана или интерфейсного пула переднего плана) от внутреннего интерфейса пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="1a6df-203">Inbound SIP traffic (to Director, Director pool IP address, Front End Server or Front End pool IP address) from Edge Server internal interface</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1a6df-204">PSOM/MTLS/TCP/8057</span><span class="sxs-lookup"><span data-stu-id="1a6df-204">PSOM/MTLS/TCP/8057</span></span></p></td>
<td><p><span data-ttu-id="1a6df-205">Любой (может быть определен как IP-адрес сервера переднего плана или каждый IP-адрес сервера переднего плана в пуле переднего плана)</span><span class="sxs-lookup"><span data-stu-id="1a6df-205">Any (can be defined as Front End Server IP address, or each Front End Server IP address in a Front End pool)</span></span></p></td>
<td><p><span data-ttu-id="1a6df-206">Внутренний интерфейс пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="1a6df-206">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="1a6df-207">Трафик веб-конференций от сервера переднего плана или сервера переднего плана в пул, внутренний интерфейс пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="1a6df-207">Web conferencing traffic from Front End Server or each Front End Server if in a pool, to Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1a6df-208">SIP/MTLS/TCP/5062</span><span class="sxs-lookup"><span data-stu-id="1a6df-208">SIP/MTLS/TCP/5062</span></span></p></td>
<td><p><span data-ttu-id="1a6df-209">Любой (может быть определен как IP-адрес сервера переднего плана или IP-адрес пула переднего плана или любое устройство для обеспечения связи в филиале или как сервер для обеспечения связи в филиалах с помощью этого пограничного сервера)</span><span class="sxs-lookup"><span data-stu-id="1a6df-209">Any (can be defined as Front End Server IP address, or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server)</span></span></p></td>
<td><p><span data-ttu-id="1a6df-210">Внутренний интерфейс пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="1a6df-210">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="1a6df-211">Проверка подлинности пользователей и подлинности (служба проверки подлинности A/V) с IP-адреса сервера переднего плана или интерфейсного пула или любого устройства для обеспечения связи в филиалах или сервера обеспечения связи в филиалах с помощью этого пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="1a6df-211">Authentication of A/V users (A/V authentication service) from Front End Server or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1a6df-212">STUN/MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="1a6df-212">STUN/MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="1a6df-213">Любой</span><span class="sxs-lookup"><span data-stu-id="1a6df-213">Any</span></span></p></td>
<td><p><span data-ttu-id="1a6df-214">Внутренний интерфейс пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="1a6df-214">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="1a6df-215">Предпочтительный путь для передачи аудио-и видеоданных между внутренними и внешними пользователями, устройством для обеспечения связи в филиалах или сервером обеспечения связи в филиалах</span><span class="sxs-lookup"><span data-stu-id="1a6df-215">Preferred path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1a6df-216">STUN/MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="1a6df-216">STUN/MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="1a6df-217">Любой</span><span class="sxs-lookup"><span data-stu-id="1a6df-217">Any</span></span></p></td>
<td><p><span data-ttu-id="1a6df-218">Внутренний интерфейс пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="1a6df-218">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="1a6df-219">Резервный путь для передачи аудио-и видеоданных между внутренними и внешними пользователями, устройства для обеспечения связи в филиалах или сервера для обеспечения связи в филиалах если не удается установить UDP-связь, используется TCP для передачи файлов и общего доступа к рабочему столу</span><span class="sxs-lookup"><span data-stu-id="1a6df-219">Fallback path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server if UDP communication cannot be established, TCP is used for file transfer and desktop sharing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1a6df-220">HTTPS/TCP/4443</span><span class="sxs-lookup"><span data-stu-id="1a6df-220">HTTPS/TCP/4443</span></span></p></td>
<td><p><span data-ttu-id="1a6df-221">Любой (может быть определен как IP-адрес сервера переднего плана или пул, в котором хранится центральное хранилище управления)</span><span class="sxs-lookup"><span data-stu-id="1a6df-221">Any (can be defined as the Front End Server IP address, or pool that holds the Central Management store)</span></span></p></td>
<td><p><span data-ttu-id="1a6df-222">Внутренний интерфейс пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="1a6df-222">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="1a6df-223">Репликация изменений из центрального хранилища управления на пограничный сервер</span><span class="sxs-lookup"><span data-stu-id="1a6df-223">Replication of changes from the Central Management store to the Edge Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1a6df-224">MTLS/TCP/50001</span><span class="sxs-lookup"><span data-stu-id="1a6df-224">MTLS/TCP/50001</span></span></p></td>
<td><p><span data-ttu-id="1a6df-225">Любой</span><span class="sxs-lookup"><span data-stu-id="1a6df-225">Any</span></span></p></td>
<td><p><span data-ttu-id="1a6df-226">Внутренний интерфейс пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="1a6df-226">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="1a6df-227">Централизованное ведение журналов с помощью команд Командная консоль Lync Server и командлетов службы централизованного ведения журналов, Командная строка ClsController (ClsController.exe) или агента (ClsAgent.exe), а также коллекция журналов</span><span class="sxs-lookup"><span data-stu-id="1a6df-227">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1a6df-228">MTLS/TCP/50002</span><span class="sxs-lookup"><span data-stu-id="1a6df-228">MTLS/TCP/50002</span></span></p></td>
<td><p><span data-ttu-id="1a6df-229">Любой</span><span class="sxs-lookup"><span data-stu-id="1a6df-229">Any</span></span></p></td>
<td><p><span data-ttu-id="1a6df-230">Внутренний интерфейс пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="1a6df-230">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="1a6df-231">Централизованное ведение журналов с помощью команд Командная консоль Lync Server и командлетов службы централизованного ведения журналов, Командная строка ClsController (ClsController.exe) или агента (ClsAgent.exe), а также коллекция журналов</span><span class="sxs-lookup"><span data-stu-id="1a6df-231">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1a6df-232">MTLS/TCP/50003</span><span class="sxs-lookup"><span data-stu-id="1a6df-232">MTLS/TCP/50003</span></span></p></td>
<td><p><span data-ttu-id="1a6df-233">Любой</span><span class="sxs-lookup"><span data-stu-id="1a6df-233">Any</span></span></p></td>
<td><p><span data-ttu-id="1a6df-234">Внутренний интерфейс пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="1a6df-234">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="1a6df-235">Централизованное ведение журналов с помощью команд Командная консоль Lync Server и командлетов службы централизованного ведения журналов, Командная строка ClsController (ClsController.exe) или агента (ClsAgent.exe), а также коллекция журналов</span><span class="sxs-lookup"><span data-stu-id="1a6df-235">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-federation"></a><span data-ttu-id="1a6df-236">Сводка по брандмауэру для федерации</span><span class="sxs-lookup"><span data-stu-id="1a6df-236">Firewall Summary for Federation</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1a6df-237">Роль/протокол/TCP или UDP/порт</span><span class="sxs-lookup"><span data-stu-id="1a6df-237">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="1a6df-238">Исходный IP-адрес</span><span class="sxs-lookup"><span data-stu-id="1a6df-238">Source IP address</span></span></th>
<th><span data-ttu-id="1a6df-239">Конечный IP-адрес</span><span class="sxs-lookup"><span data-stu-id="1a6df-239">Destination IP address</span></span></th>
<th><span data-ttu-id="1a6df-240">Примечания</span><span class="sxs-lookup"><span data-stu-id="1a6df-240">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1a6df-241">Доступ/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="1a6df-241">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="1a6df-242">Общедоступный IP-адрес пограничной службы доступа</span><span class="sxs-lookup"><span data-stu-id="1a6df-242">Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="1a6df-243">Любой</span><span class="sxs-lookup"><span data-stu-id="1a6df-243">Any</span></span></p></td>
<td><p><span data-ttu-id="1a6df-244">Для федеративного подключения и подключения к общедоступным службам обмена мгновенными сообщениями с помощью SIP</span><span class="sxs-lookup"><span data-stu-id="1a6df-244">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary--public-instant-messaging-connectivity"></a><span data-ttu-id="1a6df-245">Сводка по брандмауэру — связь с общедоступной службой обмена мгновенными сообщениями</span><span class="sxs-lookup"><span data-stu-id="1a6df-245">Firewall Summary – Public Instant Messaging Connectivity</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1a6df-246">Роль/протокол/TCP или UDP/порт</span><span class="sxs-lookup"><span data-stu-id="1a6df-246">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="1a6df-247">Исходный IP-адрес</span><span class="sxs-lookup"><span data-stu-id="1a6df-247">Source IP address</span></span></th>
<th><span data-ttu-id="1a6df-248">Конечный IP-адрес</span><span class="sxs-lookup"><span data-stu-id="1a6df-248">Destination IP address</span></span></th>
<th><span data-ttu-id="1a6df-249">Примечания</span><span class="sxs-lookup"><span data-stu-id="1a6df-249">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1a6df-250">Доступ/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="1a6df-250">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="1a6df-251">Партнеры по связи с общедоступной службой обмена мгновенными сообщениями</span><span class="sxs-lookup"><span data-stu-id="1a6df-251">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="1a6df-252">Пограничный сервер доступа, пограничная служба доступа</span><span class="sxs-lookup"><span data-stu-id="1a6df-252">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="1a6df-253">Для федеративного подключения и подключения к общедоступным службам обмена мгновенными сообщениями с помощью SIP</span><span class="sxs-lookup"><span data-stu-id="1a6df-253">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1a6df-254">Доступ/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="1a6df-254">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="1a6df-255">Пограничный сервер доступа, пограничная служба доступа</span><span class="sxs-lookup"><span data-stu-id="1a6df-255">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="1a6df-256">Партнеры по связи с общедоступной службой обмена мгновенными сообщениями</span><span class="sxs-lookup"><span data-stu-id="1a6df-256">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="1a6df-257">Для федеративного подключения и подключения к общедоступным службам обмена мгновенными сообщениями с помощью SIP</span><span class="sxs-lookup"><span data-stu-id="1a6df-257">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1a6df-258">/TCP/443 доступа и SIP (TLS)</span><span class="sxs-lookup"><span data-stu-id="1a6df-258">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="1a6df-259">Клиенты</span><span class="sxs-lookup"><span data-stu-id="1a6df-259">Clients</span></span></p></td>
<td><p><span data-ttu-id="1a6df-260">Пограничный сервер доступа, пограничная служба доступа</span><span class="sxs-lookup"><span data-stu-id="1a6df-260">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="1a6df-261">Трафик SIP от клиента к серверу для доступа внешних пользователей</span><span class="sxs-lookup"><span data-stu-id="1a6df-261">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1a6df-262">АУДИО-И ВИДЕОДАННЫЕ/RTP/TCP/50000-– 999</span><span class="sxs-lookup"><span data-stu-id="1a6df-262">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="1a6df-263">Пограничный сервер, пограничная служба аудио- и видеоданных</span><span class="sxs-lookup"><span data-stu-id="1a6df-263">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="1a6df-264">Клиенты Live Messenger</span><span class="sxs-lookup"><span data-stu-id="1a6df-264">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="1a6df-265">Используется для сеансов аудио- и видеоконференций с использованием Windows Live Messenger, если настроена связь с общедоступной службой обмена мгновенными сообщениями.</span><span class="sxs-lookup"><span data-stu-id="1a6df-265">Used for A/V sessions with Windows Live Messenger if public IM connectivity is configured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1a6df-266">АУДИО-И ВИДЕОДАННЫЕ/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="1a6df-266">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="1a6df-267">Пограничный сервер, пограничная служба аудио- и видеоданных</span><span class="sxs-lookup"><span data-stu-id="1a6df-267">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="1a6df-268">Клиенты Live Messenger</span><span class="sxs-lookup"><span data-stu-id="1a6df-268">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="1a6df-269">Требуется для связи с общедоступной службой обмена мгновенными сообщениями с помощью Windows Live Messenger</span><span class="sxs-lookup"><span data-stu-id="1a6df-269">Required for public IM connectivity with Windows Live Messenger</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1a6df-270">АУДИО-И ВИДЕОДАННЫЕ/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="1a6df-270">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="1a6df-271">Клиенты Live Messenger</span><span class="sxs-lookup"><span data-stu-id="1a6df-271">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="1a6df-272">Пограничный сервер, пограничная служба аудио- и видеоданных</span><span class="sxs-lookup"><span data-stu-id="1a6df-272">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="1a6df-273">Требуется для связи с общедоступной службой обмена мгновенными сообщениями с помощью Windows Live Messenger</span><span class="sxs-lookup"><span data-stu-id="1a6df-273">Required for public IM connectivity with Windows Live Messenger</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-extensible-messaging-and-presence-protocol"></a><span data-ttu-id="1a6df-274">Сводка по брандмауэру для протокола XMPP</span><span class="sxs-lookup"><span data-stu-id="1a6df-274">Firewall Summary for Extensible Messaging and Presence Protocol</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1a6df-275">Протокол/TCP или UDP/порт</span><span class="sxs-lookup"><span data-stu-id="1a6df-275">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="1a6df-276">Источник (IP-адрес)</span><span class="sxs-lookup"><span data-stu-id="1a6df-276">Source (IP address)</span></span></th>
<th><span data-ttu-id="1a6df-277">Назначение (IP-адрес)</span><span class="sxs-lookup"><span data-stu-id="1a6df-277">Destination (IP address)</span></span></th>
<th><span data-ttu-id="1a6df-278">Comments</span><span class="sxs-lookup"><span data-stu-id="1a6df-278">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1a6df-279">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="1a6df-279">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="1a6df-280">Любой</span><span class="sxs-lookup"><span data-stu-id="1a6df-280">Any</span></span></p></td>
<td><p><span data-ttu-id="1a6df-281">IP-адрес интерфейса пограничного сервера доступа пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="1a6df-281">Edge Server Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="1a6df-282">Стандартный порт для связи "сервер-сервер" через XMPP.</span><span class="sxs-lookup"><span data-stu-id="1a6df-282">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="1a6df-283">Разрешает связь с прокси-сервером пограничного сервера XMPP от федеративных партнеров XMPP</span><span class="sxs-lookup"><span data-stu-id="1a6df-283">Allows communication to the Edge Server XMPP proxy from federated XMPP partners</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1a6df-284">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="1a6df-284">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="1a6df-285">IP-адрес интерфейса пограничного сервера доступа пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="1a6df-285">Edge Server Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="1a6df-286">Любой</span><span class="sxs-lookup"><span data-stu-id="1a6df-286">Any</span></span></p></td>
<td><p><span data-ttu-id="1a6df-287">Стандартный порт для связи "сервер-сервер" через XMPP.</span><span class="sxs-lookup"><span data-stu-id="1a6df-287">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="1a6df-288">Разрешает обмен данными от прокси-сервера пограничного сервера XMPP к федеративным партнерам XMPP</span><span class="sxs-lookup"><span data-stu-id="1a6df-288">Allows communication from the Edge Server XMPP proxy to federated XMPP partners</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1a6df-289">XMPP/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="1a6df-289">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="1a6df-290">Любой</span><span class="sxs-lookup"><span data-stu-id="1a6df-290">Any</span></span></p></td>
<td><p><span data-ttu-id="1a6df-291">Каждый внутренний интерфейсный IP-адрес пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="1a6df-291">Each internal Edge Server Interface IP</span></span></p></td>
<td><p><span data-ttu-id="1a6df-292">Внутренний IP-адрес пограничного сервера или пула переднего плана на внутренний IP-адрес пограничного сервера или на каждый внутренний IP-адрес пограничного пула — внутренний IP-адрес XMPP, входящий в шлюз XMPP.</span><span class="sxs-lookup"><span data-stu-id="1a6df-292">Internal XMPP traffic from the XMPP Gateway on the Front End Server or Front End pool to the Edge Server internal IP address or each Edge pool member’s internal IP address</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

