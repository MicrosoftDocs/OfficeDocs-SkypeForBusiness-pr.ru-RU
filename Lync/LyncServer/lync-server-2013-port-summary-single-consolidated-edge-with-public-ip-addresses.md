---
title: Сводка по портам — единая Объединенная пограничная с общедоступными IP-адресами
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
ms.openlocfilehash: 6aa6c3e2ad475cb641a2df50c1dc0016a5ac2fd9
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48534016"
---
# <a name="port-summary---single-consolidated-edge-with-public-ip-addresses-in-lync-server-2013"></a><span data-ttu-id="c3800-102">Сводка по портам — единая Объединенная пограничная с общедоступными IP-адресами в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c3800-102">Port summary - Single consolidated edge with public IP addresses in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c3800-103">_**Последнее изменение темы:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="c3800-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="c3800-104">Сервер Lync Server 2013, функции пограничного сервера, описанные в этой архитектуре сценариев, очень похожи на компоненты, реализованные в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="c3800-104">The Lync Server 2013, Edge Server functionality described in this scenario architecture is very similar to what was implemented in Lync Server 2010.</span></span> <span data-ttu-id="c3800-105">Наиболее значимым дополнением является порт **5269 по протоколу TCP** для поддержки протокола XMPP (расширяемый протокол обмена сообщениями и сведениями о присутствии).</span><span class="sxs-lookup"><span data-stu-id="c3800-105">The most noticeable addition is the port **5269 over TCP** entry for the extensible messaging and presence protocol (XMPP).</span></span> <span data-ttu-id="c3800-106">Lync Server 2013 при необходимости разворачивает прокси-сервер XMPP на пограничном или пограничном пуле и на сервере шлюза XMPP на сервере переднего плана или интерфейсном пуле.</span><span class="sxs-lookup"><span data-stu-id="c3800-106">Lync Server 2013 optionally deploys an XMPP proxy on the Edge Server or Edge pool and the XMPP gateway server on the Front End Server or Front End pool.</span></span> <span data-ttu-id="c3800-107">Сведения о планировании для обратного прокси-сервера и Федерации находятся в [сценариях для обратного прокси-сервера в Lync server 2013](lync-server-2013-scenarios-for-reverse-proxy.md) и [планировании SIP, Федерации XMPP и общедоступных мгновенных сообщений в разделах Lync Server 2013](lync-server-2013-planning-for-sip-xmpp-federation-and-public-instant-messaging.md) соответственно.</span><span class="sxs-lookup"><span data-stu-id="c3800-107">Planning information for the reverse proxy and federation are found in [Scenarios for reverse proxy in Lync Server 2013](lync-server-2013-scenarios-for-reverse-proxy.md) and [Planning for SIP, XMPP federation, and public instant messaging in Lync Server 2013](lync-server-2013-planning-for-sip-xmpp-federation-and-public-instant-messaging.md) sections, respectively.</span></span>

<span data-ttu-id="c3800-108">Кроме протокола IPv4, пограничный сервер теперь поддерживает IPv6.</span><span class="sxs-lookup"><span data-stu-id="c3800-108">In addition to IPv4, the Edge Server now supports IPv6.</span></span> <span data-ttu-id="c3800-109">Для ясности в этих сценариях используется IPv4.</span><span class="sxs-lookup"><span data-stu-id="c3800-109">For clarity, only IPv4 is used in the scenarios.</span></span>

<span data-ttu-id="c3800-110">**Сеть периметра предприятия для единого консолидированного пограничного сервера с общедоступными IP-адресами**</span><span class="sxs-lookup"><span data-stu-id="c3800-110">**Enterprise perimeter network for single consolidated edge with public IP addressing**</span></span>

<span data-ttu-id="c3800-111">![f8c144c5-e5fb-498a-823e-eb39f26b6847](images/Gg425891.f8c144c5-e5fb-498a-823e-eb39f26b6847(OCS.15).jpg "f8c144c5-e5fb-498a-823e-eb39f26b6847")</span><span class="sxs-lookup"><span data-stu-id="c3800-111">![f8c144c5-e5fb-498a-823e-eb39f26b6847](images/Gg425891.f8c144c5-e5fb-498a-823e-eb39f26b6847(OCS.15).jpg "f8c144c5-e5fb-498a-823e-eb39f26b6847")</span></span>

<div>

## <a name="port-and-protocol-details"></a><span data-ttu-id="c3800-112">Сведения о портах и протоколе</span><span class="sxs-lookup"><span data-stu-id="c3800-112">Port and Protocol Details</span></span>

<span data-ttu-id="c3800-113">Рекомендуется открывать только те порты, которые требуются для поддержки функциональной возможности, внешний доступ к которой предоставляется.</span><span class="sxs-lookup"><span data-stu-id="c3800-113">We recommend that you open only the ports required to support the functionality for which you are providing external access.</span></span>

<span data-ttu-id="c3800-p103">Для предоставления удаленного доступа в целях работы с любой пограничной службой необходимо разрешить двунаправленный трафик SIP, как показано на схеме пограничного входящего/исходящего трафика. Иначе говоря, сообщения SIP, поступающие в пограничную службу доступа и из нее, связаны со службой обмена мгновенными сообщениями и сведениями о присутствии, системой веб-конференций, аудио- и видеосвязи и федерациями.</span><span class="sxs-lookup"><span data-stu-id="c3800-p103">For remote access to work for any edge service, it is mandatory that SIP traffic is allowed to flow bidirectionally as shown in the Inbound/Outbound edge traffic figure. Stated another way, the SIP messaging to and from the Access Edge service is involved in instant messaging (IM), presence, web conferencing, audio/video (A/V) and federation.</span></span>

### <a name="firewall-summary-for-single-consolidated-edge-with-public-ip-addresses-external-interface"></a><span data-ttu-id="c3800-116">Сводная информация по брандмауэрам для одного консолидированного пограничного сервера с общедоступными IP-адресами: внешний интерфейс</span><span class="sxs-lookup"><span data-stu-id="c3800-116">Firewall Summary for Single Consolidated Edge with Public IP Addresses: External Interface</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c3800-117">Роль/протокол/TCP или UDP/порт</span><span class="sxs-lookup"><span data-stu-id="c3800-117">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="c3800-118">Исходный IP-адрес</span><span class="sxs-lookup"><span data-stu-id="c3800-118">Source IP address</span></span></th>
<th><span data-ttu-id="c3800-119">Конечный IP-адрес</span><span class="sxs-lookup"><span data-stu-id="c3800-119">Destination IP address</span></span></th>
<th><span data-ttu-id="c3800-120">Примечания</span><span class="sxs-lookup"><span data-stu-id="c3800-120">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c3800-121">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="c3800-121">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="c3800-122">Любой</span><span class="sxs-lookup"><span data-stu-id="c3800-122">Any</span></span></p></td>
<td><p><span data-ttu-id="c3800-123">Прокси-служба XMPP (общий IP-адрес с пограничной службой доступа)</span><span class="sxs-lookup"><span data-stu-id="c3800-123">XMPP Proxy service (shares IP address with Access Edge service)</span></span></p></td>
<td><p><span data-ttu-id="c3800-124">Служба прокси XMPP принимает трафик от контактов XMPP в определенных федерациях XMPP</span><span class="sxs-lookup"><span data-stu-id="c3800-124">XMPP Proxy service accepts traffic from XMPP contacts in defined XMPP federations</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c3800-125">Access/HTTP/TCP/80</span><span class="sxs-lookup"><span data-stu-id="c3800-125">Access/HTTP/TCP/80</span></span></p></td>
<td><p><span data-ttu-id="c3800-126">Общедоступный IP-адрес пограничной службы доступа пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="c3800-126">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="c3800-127">Любой</span><span class="sxs-lookup"><span data-stu-id="c3800-127">Any</span></span></p></td>
<td><p><span data-ttu-id="c3800-128">Отзыв сертификата/проверка и поиск CRL</span><span class="sxs-lookup"><span data-stu-id="c3800-128">Certificate revocation/CRL check and retrieval</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c3800-129">Доступ/DNS/TCP/53</span><span class="sxs-lookup"><span data-stu-id="c3800-129">Access/DNS/TCP/53</span></span></p></td>
<td><p><span data-ttu-id="c3800-130">Общедоступный IP-адрес пограничной службы доступа пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="c3800-130">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="c3800-131">Любой</span><span class="sxs-lookup"><span data-stu-id="c3800-131">Any</span></span></p></td>
<td><p><span data-ttu-id="c3800-132">DNS-запрос по протоколу TCP</span><span class="sxs-lookup"><span data-stu-id="c3800-132">DNS query over TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c3800-133">Доступ/DNS/UDP/53</span><span class="sxs-lookup"><span data-stu-id="c3800-133">Access/DNS/UDP/53</span></span></p></td>
<td><p><span data-ttu-id="c3800-134">Общедоступный IP-адрес пограничной службы доступа пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="c3800-134">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="c3800-135">Любой</span><span class="sxs-lookup"><span data-stu-id="c3800-135">Any</span></span></p></td>
<td><p><span data-ttu-id="c3800-136">DNS-запрос по протоколу UDP</span><span class="sxs-lookup"><span data-stu-id="c3800-136">DNS query over UDP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c3800-137">/TCP/443 доступа и SIP (TLS)</span><span class="sxs-lookup"><span data-stu-id="c3800-137">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="c3800-138">Любой</span><span class="sxs-lookup"><span data-stu-id="c3800-138">Any</span></span></p></td>
<td><p><span data-ttu-id="c3800-139">Общедоступный IP-адрес пограничной службы доступа пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="c3800-139">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="c3800-140">Трафик SIP «клиент-сервер» для доступа внешних пользователей</span><span class="sxs-lookup"><span data-stu-id="c3800-140">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c3800-141">Доступ/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="c3800-141">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="c3800-142">Любой</span><span class="sxs-lookup"><span data-stu-id="c3800-142">Any</span></span></p></td>
<td><p><span data-ttu-id="c3800-143">Общедоступный IP-адрес пограничной службы доступа пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="c3800-143">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="c3800-144">Для федеративного подключения и подключения к общедоступным службам обмена мгновенными сообщениями с помощью SIP</span><span class="sxs-lookup"><span data-stu-id="c3800-144">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c3800-145">Доступ/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="c3800-145">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="c3800-146">Общедоступный IP-адрес пограничной службы доступа пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="c3800-146">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="c3800-147">Любой</span><span class="sxs-lookup"><span data-stu-id="c3800-147">Any</span></span></p></td>
<td><p><span data-ttu-id="c3800-148">Для федеративного подключения и подключения к общедоступным службам обмена мгновенными сообщениями с помощью SIP</span><span class="sxs-lookup"><span data-stu-id="c3800-148">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c3800-149">Веб-конференции/PSOM (TLS)/TCP/443</span><span class="sxs-lookup"><span data-stu-id="c3800-149">Web Conferencing/PSOM(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="c3800-150">Любой</span><span class="sxs-lookup"><span data-stu-id="c3800-150">Any</span></span></p></td>
<td><p><span data-ttu-id="c3800-151">Общедоступный IP-адрес службы веб-конференций пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="c3800-151">Edge Server Web Conferencing Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="c3800-152">Устройство для веб-конференций</span><span class="sxs-lookup"><span data-stu-id="c3800-152">Web Conferencing media</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c3800-153">АУДИО-И ВИДЕОДАННЫЕ/RTP/TCP/50000-– 999</span><span class="sxs-lookup"><span data-stu-id="c3800-153">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="c3800-154">Общедоступный IP-адрес пограничной службы доступа пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="c3800-154">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="c3800-155">Любой</span><span class="sxs-lookup"><span data-stu-id="c3800-155">Any</span></span></p></td>
<td><p><span data-ttu-id="c3800-156">Необходимо для Федерации с партнерами, работающими под управлением Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 и Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c3800-156">Required for federating with partners running Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 and Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c3800-157">АУДИО-И ВИДЕОДАННЫЕ/RTP/UDP/50000-– 999</span><span class="sxs-lookup"><span data-stu-id="c3800-157">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="c3800-158">Общедоступный IP-адрес пограничного сервера аудио-и пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="c3800-158">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="c3800-159">Любой</span><span class="sxs-lookup"><span data-stu-id="c3800-159">Any</span></span></p></td>
<td><p><span data-ttu-id="c3800-160">Обязательно только для Федерации с партнерами, работающими под управлением Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="c3800-160">Required only for federation with partners running Office Communications Server 2007</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c3800-161">АУДИО-И ВИДЕОДАННЫЕ/RTP/TCP/50000-– 999</span><span class="sxs-lookup"><span data-stu-id="c3800-161">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="c3800-162">Любой</span><span class="sxs-lookup"><span data-stu-id="c3800-162">Any</span></span></p></td>
<td><p><span data-ttu-id="c3800-163">Общедоступный IP-адрес пограничного сервера аудио-и пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="c3800-163">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="c3800-164">Обязательно только для Федерации с партнерами, работающими под управлением Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="c3800-164">Required only for federation with partners running Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c3800-165">АУДИО-И ВИДЕОДАННЫЕ/RTP/UDP/50000-– 999</span><span class="sxs-lookup"><span data-stu-id="c3800-165">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="c3800-166">Любой</span><span class="sxs-lookup"><span data-stu-id="c3800-166">Any</span></span></p></td>
<td><p><span data-ttu-id="c3800-167">Общедоступный IP-адрес пограничного сервера аудио-и пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="c3800-167">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="c3800-168">Обязательно только для Федерации с партнерами, работающими под управлением Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="c3800-168">Required only for federation with partners running Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c3800-169">АУДИО-И ВИДЕОДАННЫЕ/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="c3800-169">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="c3800-170">Общедоступный IP-адрес пограничного сервера аудио-и пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="c3800-170">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="c3800-171">Любой</span><span class="sxs-lookup"><span data-stu-id="c3800-171">Any</span></span></p></td>
<td><p><span data-ttu-id="c3800-172">3478 исходящие используется для определения версии пограничного сервера, с которым обменивается данными Lync Server, а также для мультимедийного трафика с пограничного сервера на пограничный сервер.</span><span class="sxs-lookup"><span data-stu-id="c3800-172">3478 outbound is used to determine the version of Edge Server that Lync Server is communicating with and also for media traffic from Edge Server-to-Edge Server.</span></span> <span data-ttu-id="c3800-173">Обязательно для Федерации с Lync Server 2010, Windows Live Messenger и Office Communications Server 2007 R2, а также при развертывании нескольких пограничных пулов в компании.</span><span class="sxs-lookup"><span data-stu-id="c3800-173">Required for federation with Lync Server 2010, Windows Live Messenger, and Office Communications Server 2007 R2, and also if multiple Edge pools are deployed within a company.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c3800-174">АУДИО-И ВИДЕОДАННЫЕ/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="c3800-174">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="c3800-175">Любой</span><span class="sxs-lookup"><span data-stu-id="c3800-175">Any</span></span></p></td>
<td><p><span data-ttu-id="c3800-176">Общедоступный IP-адрес пограничного сервера аудио-и пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="c3800-176">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="c3800-177">STUN/TURN — согласование кандидатов по протоколу UDP/3478</span><span class="sxs-lookup"><span data-stu-id="c3800-177">STUN/TURN negotiation of candidates over UDP/3478</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c3800-178">АУДИО-И ВИДЕОДАННЫЕ/STUN, MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="c3800-178">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="c3800-179">Любой</span><span class="sxs-lookup"><span data-stu-id="c3800-179">Any</span></span></p></td>
<td><p><span data-ttu-id="c3800-180">Общедоступный IP-адрес пограничного сервера аудио-и пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="c3800-180">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="c3800-181">STUN/TURN — согласование кандидатов по протоколу TCP/443</span><span class="sxs-lookup"><span data-stu-id="c3800-181">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c3800-182">АУДИО-И ВИДЕОДАННЫЕ/STUN, MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="c3800-182">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="c3800-183">Общедоступный IP-адрес пограничного сервера аудио-и пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="c3800-183">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="c3800-184">Любой</span><span class="sxs-lookup"><span data-stu-id="c3800-184">Any</span></span></p></td>
<td><p><span data-ttu-id="c3800-185">STUN/TURN — согласование кандидатов по протоколу TCP/443</span><span class="sxs-lookup"><span data-stu-id="c3800-185">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="firewall-summary-for-single-consolidated-edge-with-public-ip-addresses-internal-interface"></a><span data-ttu-id="c3800-186">Сводная информация по брандмауэрам для одного консолидированного пограничного сервера с общедоступными IP-адресами: внутренний интерфейс</span><span class="sxs-lookup"><span data-stu-id="c3800-186">Firewall Summary for Single Consolidated Edge with Public IP Addresses: Internal Interface</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c3800-187">Протокол/TCP или UDP/порт</span><span class="sxs-lookup"><span data-stu-id="c3800-187">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="c3800-188">Исходный IP-адрес</span><span class="sxs-lookup"><span data-stu-id="c3800-188">Source IP address</span></span></th>
<th><span data-ttu-id="c3800-189">Конечный IP-адрес</span><span class="sxs-lookup"><span data-stu-id="c3800-189">Destination IP address</span></span></th>
<th><span data-ttu-id="c3800-190">Comments</span><span class="sxs-lookup"><span data-stu-id="c3800-190">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c3800-191">XMPP/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="c3800-191">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="c3800-192">Любой (может быть определен как IP-адрес сервера Standard Edition, IP-адрес сервера Standard Edition или IP-адрес пула, на котором запущена служба шлюза XMPP).</span><span class="sxs-lookup"><span data-stu-id="c3800-192">Any (can be defined as Standard Edition server IP, Standard Edition server IP address, or pool IP address running the XMPP Gateway service)</span></span></p></td>
<td><p><span data-ttu-id="c3800-193">Внутренний интерфейс пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="c3800-193">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="c3800-194">Исходящий трафик XMPP из службы шлюза XMPP, работающего на сервере переднего плана или интерфейсном пуле</span><span class="sxs-lookup"><span data-stu-id="c3800-194">Outbound XMPP traffic from XMPP Gateway service running on Front End Server or Front End pool</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c3800-195">SIP/MTLS/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="c3800-195">SIP/MTLS/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="c3800-196">Любой (может быть определен как директор, IP-адрес пула директоров, сервер переднего плана или IP-адрес пула переднего плана).</span><span class="sxs-lookup"><span data-stu-id="c3800-196">Any (can be defined as Director, Director pool IP address, Front End Server or Front End pool IP address)</span></span></p></td>
<td><p><span data-ttu-id="c3800-197">IP-адрес пограничного сервера или пул, в котором хранится внутренний интерфейс</span><span class="sxs-lookup"><span data-stu-id="c3800-197">Edge Server IP, or pool that holds the internal interface</span></span></p></td>
<td><p><span data-ttu-id="c3800-198">Исходящий трафик SIP (от директора, IP-адреса пула директоров, сервера переднего плана или IP-адреса пула переднего плана) к внутреннему интерфейсу пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="c3800-198">Outbound SIP traffic (from Director, Director pool IP address, Front End Server or Front End pool IP address) to Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c3800-199">SIP/MTLS/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="c3800-199">SIP/MTLS/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="c3800-200">Внутренний интерфейс пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="c3800-200">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="c3800-201">Любой (может быть определен как директор, IP-адрес пула директоров, сервер переднего плана или адрес внешнего интерфейса пула)</span><span class="sxs-lookup"><span data-stu-id="c3800-201">Any (can be defined as Director, Director pool IP address, Front End Server or Front End pool address)</span></span></p></td>
<td><p><span data-ttu-id="c3800-202">Входящий трафик SIP (в директоре, IP-адрес пула директоров, IP-адрес сервера переднего плана или интерфейсного пула переднего плана) от внутреннего интерфейса пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="c3800-202">Inbound SIP traffic (to Director, Director pool IP address, Front End Server or Front End pool IP address) from Edge Server internal interface</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c3800-203">PSOM/MTLS/TCP/8057</span><span class="sxs-lookup"><span data-stu-id="c3800-203">PSOM/MTLS/TCP/8057</span></span></p></td>
<td><p><span data-ttu-id="c3800-204">Любой (может быть определен как IP-адрес сервера переднего плана или каждый IP-адрес сервера переднего плана в пуле переднего плана)</span><span class="sxs-lookup"><span data-stu-id="c3800-204">Any (can be defined as Front End Server IP address, or each Front End Server IP address in a Front End pool)</span></span></p></td>
<td><p><span data-ttu-id="c3800-205">Внутренний интерфейс пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="c3800-205">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="c3800-206">Трафик веб-конференций от сервера переднего плана или сервера переднего плана в пул, внутренний интерфейс пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="c3800-206">Web conferencing traffic from Front End Server or each Front End Server if in a pool, to Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c3800-207">SIP/MTLS/TCP/5062</span><span class="sxs-lookup"><span data-stu-id="c3800-207">SIP/MTLS/TCP/5062</span></span></p></td>
<td><p><span data-ttu-id="c3800-208">Любой (может быть определен как IP-адрес сервера переднего плана или IP-адрес пула переднего плана или любое устройство для обеспечения связи в филиале или как сервер для обеспечения связи в филиалах с помощью этого пограничного сервера)</span><span class="sxs-lookup"><span data-stu-id="c3800-208">Any (can be defined as Front End Server IP address, or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server)</span></span></p></td>
<td><p><span data-ttu-id="c3800-209">Внутренний интерфейс пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="c3800-209">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="c3800-210">Проверка подлинности пользователей и подлинности (служба проверки подлинности A/V) с IP-адреса сервера переднего плана или интерфейсного пула или любого устройства для обеспечения связи в филиалах или сервера обеспечения связи в филиалах с помощью этого пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="c3800-210">Authentication of A/V users (A/V authentication service) from Front End Server or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c3800-211">STUN/MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="c3800-211">STUN/MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="c3800-212">Любой</span><span class="sxs-lookup"><span data-stu-id="c3800-212">Any</span></span></p></td>
<td><p><span data-ttu-id="c3800-213">Внутренний интерфейс пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="c3800-213">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="c3800-214">Предпочтительный путь для передачи аудио-и видеоданных между внутренними и внешними пользователями, устройством для обеспечения связи в филиалах или сервером обеспечения связи в филиалах</span><span class="sxs-lookup"><span data-stu-id="c3800-214">Preferred path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c3800-215">STUN/MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="c3800-215">STUN/MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="c3800-216">Любой</span><span class="sxs-lookup"><span data-stu-id="c3800-216">Any</span></span></p></td>
<td><p><span data-ttu-id="c3800-217">Внутренний интерфейс пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="c3800-217">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="c3800-218">Резервный путь для передачи аудио-и видеоданных между внутренними и внешними пользователями, устройства для обеспечения связи в филиалах или сервера для обеспечения связи в филиалах если не удается установить UDP-связь, используется TCP для передачи файлов и общего доступа к рабочему столу</span><span class="sxs-lookup"><span data-stu-id="c3800-218">Fallback path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server if UDP communication cannot be established, TCP is used for file transfer and desktop sharing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c3800-219">HTTPS/TCP/4443</span><span class="sxs-lookup"><span data-stu-id="c3800-219">HTTPS/TCP/4443</span></span></p></td>
<td><p><span data-ttu-id="c3800-220">Любой (может быть определен как IP-адрес сервера переднего плана или пул, в котором хранится центральное хранилище управления)</span><span class="sxs-lookup"><span data-stu-id="c3800-220">Any (can be defined as the Front End Server IP address, or pool that holds the Central Management store)</span></span></p></td>
<td><p><span data-ttu-id="c3800-221">Внутренний интерфейс пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="c3800-221">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="c3800-222">Репликация изменений из центрального хранилища управления на пограничный сервер</span><span class="sxs-lookup"><span data-stu-id="c3800-222">Replication of changes from the Central Management store to the Edge Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c3800-223">MTLS/TCP/50001</span><span class="sxs-lookup"><span data-stu-id="c3800-223">MTLS/TCP/50001</span></span></p></td>
<td><p><span data-ttu-id="c3800-224">Любой</span><span class="sxs-lookup"><span data-stu-id="c3800-224">Any</span></span></p></td>
<td><p><span data-ttu-id="c3800-225">Внутренний интерфейс пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="c3800-225">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="c3800-226">Централизованное ведение журналов с помощью команд Командная консоль Lync Server и командлетов службы централизованного ведения журналов, Командная строка ClsController (ClsController.exe) или агента (ClsAgent.exe), а также коллекция журналов</span><span class="sxs-lookup"><span data-stu-id="c3800-226">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c3800-227">MTLS/TCP/50002</span><span class="sxs-lookup"><span data-stu-id="c3800-227">MTLS/TCP/50002</span></span></p></td>
<td><p><span data-ttu-id="c3800-228">Любой</span><span class="sxs-lookup"><span data-stu-id="c3800-228">Any</span></span></p></td>
<td><p><span data-ttu-id="c3800-229">Внутренний интерфейс пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="c3800-229">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="c3800-230">Централизованное ведение журналов с помощью команд Командная консоль Lync Server и командлетов службы централизованного ведения журналов, Командная строка ClsController (ClsController.exe) или агента (ClsAgent.exe), а также коллекция журналов</span><span class="sxs-lookup"><span data-stu-id="c3800-230">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c3800-231">MTLS/TCP/50003</span><span class="sxs-lookup"><span data-stu-id="c3800-231">MTLS/TCP/50003</span></span></p></td>
<td><p><span data-ttu-id="c3800-232">Любой</span><span class="sxs-lookup"><span data-stu-id="c3800-232">Any</span></span></p></td>
<td><p><span data-ttu-id="c3800-233">Внутренний интерфейс пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="c3800-233">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="c3800-234">Централизованное ведение журналов с помощью команд Командная консоль Lync Server и командлетов службы централизованного ведения журналов, Командная строка ClsController (ClsController.exe) или агента (ClsAgent.exe), а также коллекция журналов</span><span class="sxs-lookup"><span data-stu-id="c3800-234">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-federation"></a><span data-ttu-id="c3800-235">Сводка по брандмауэру для федерации</span><span class="sxs-lookup"><span data-stu-id="c3800-235">Firewall Summary for Federation</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c3800-236">Роль/протокол/TCP или UDP/порт</span><span class="sxs-lookup"><span data-stu-id="c3800-236">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="c3800-237">Исходный IP-адрес</span><span class="sxs-lookup"><span data-stu-id="c3800-237">Source IP address</span></span></th>
<th><span data-ttu-id="c3800-238">Конечный IP-адрес</span><span class="sxs-lookup"><span data-stu-id="c3800-238">Destination IP address</span></span></th>
<th><span data-ttu-id="c3800-239">Примечания</span><span class="sxs-lookup"><span data-stu-id="c3800-239">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c3800-240">Доступ/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="c3800-240">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="c3800-241">Общедоступный IP-адрес пограничной службы доступа</span><span class="sxs-lookup"><span data-stu-id="c3800-241">Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="c3800-242">Любой</span><span class="sxs-lookup"><span data-stu-id="c3800-242">Any</span></span></p></td>
<td><p><span data-ttu-id="c3800-243">Для федеративного подключения и подключения к общедоступным службам обмена мгновенными сообщениями с помощью SIP</span><span class="sxs-lookup"><span data-stu-id="c3800-243">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary--public-instant-messaging-connectivity"></a><span data-ttu-id="c3800-244">Сводка по брандмауэру — связь с общедоступной службой обмена мгновенными сообщениями</span><span class="sxs-lookup"><span data-stu-id="c3800-244">Firewall Summary – Public Instant Messaging Connectivity</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c3800-245">Роль/протокол/TCP или UDP/порт</span><span class="sxs-lookup"><span data-stu-id="c3800-245">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="c3800-246">Исходный IP-адрес</span><span class="sxs-lookup"><span data-stu-id="c3800-246">Source IP address</span></span></th>
<th><span data-ttu-id="c3800-247">Конечный IP-адрес</span><span class="sxs-lookup"><span data-stu-id="c3800-247">Destination IP address</span></span></th>
<th><span data-ttu-id="c3800-248">Примечания</span><span class="sxs-lookup"><span data-stu-id="c3800-248">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c3800-249">Доступ/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="c3800-249">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="c3800-250">Партнеры по связи с общедоступной службой обмена мгновенными сообщениями</span><span class="sxs-lookup"><span data-stu-id="c3800-250">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="c3800-251">Пограничный сервер доступа, пограничная служба доступа</span><span class="sxs-lookup"><span data-stu-id="c3800-251">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="c3800-252">Для федеративного подключения и подключения к общедоступным службам обмена мгновенными сообщениями с помощью SIP</span><span class="sxs-lookup"><span data-stu-id="c3800-252">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c3800-253">Доступ/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="c3800-253">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="c3800-254">Пограничный сервер доступа, пограничная служба доступа</span><span class="sxs-lookup"><span data-stu-id="c3800-254">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="c3800-255">Партнеры по связи с общедоступной службой обмена мгновенными сообщениями</span><span class="sxs-lookup"><span data-stu-id="c3800-255">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="c3800-256">Для федеративного подключения и подключения к общедоступным службам обмена мгновенными сообщениями с помощью SIP</span><span class="sxs-lookup"><span data-stu-id="c3800-256">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c3800-257">/TCP/443 доступа и SIP (TLS)</span><span class="sxs-lookup"><span data-stu-id="c3800-257">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="c3800-258">Клиенты</span><span class="sxs-lookup"><span data-stu-id="c3800-258">Clients</span></span></p></td>
<td><p><span data-ttu-id="c3800-259">Пограничный сервер доступа, пограничная служба доступа</span><span class="sxs-lookup"><span data-stu-id="c3800-259">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="c3800-260">Трафик SIP от клиента к серверу для доступа внешних пользователей</span><span class="sxs-lookup"><span data-stu-id="c3800-260">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c3800-261">АУДИО-И ВИДЕОДАННЫЕ/RTP/TCP/50000-– 999</span><span class="sxs-lookup"><span data-stu-id="c3800-261">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="c3800-262">Пограничный сервер, пограничная служба аудио- и видеоданных</span><span class="sxs-lookup"><span data-stu-id="c3800-262">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="c3800-263">Клиенты Live Messenger</span><span class="sxs-lookup"><span data-stu-id="c3800-263">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="c3800-264">Используется для сеансов аудио- и видеоконференций с использованием Windows Live Messenger, если настроена связь с общедоступной службой обмена мгновенными сообщениями.</span><span class="sxs-lookup"><span data-stu-id="c3800-264">Used for A/V sessions with Windows Live Messenger if public IM connectivity is configured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c3800-265">АУДИО-И ВИДЕОДАННЫЕ/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="c3800-265">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="c3800-266">Пограничный сервер, пограничная служба аудио- и видеоданных</span><span class="sxs-lookup"><span data-stu-id="c3800-266">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="c3800-267">Клиенты Live Messenger</span><span class="sxs-lookup"><span data-stu-id="c3800-267">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="c3800-268">Требуется для связи с общедоступной службой обмена мгновенными сообщениями с помощью Windows Live Messenger</span><span class="sxs-lookup"><span data-stu-id="c3800-268">Required for public IM connectivity with Windows Live Messenger</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c3800-269">АУДИО-И ВИДЕОДАННЫЕ/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="c3800-269">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="c3800-270">Клиенты Live Messenger</span><span class="sxs-lookup"><span data-stu-id="c3800-270">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="c3800-271">Пограничный сервер, пограничная служба аудио- и видеоданных</span><span class="sxs-lookup"><span data-stu-id="c3800-271">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="c3800-272">Требуется для связи с общедоступной службой обмена мгновенными сообщениями с помощью Windows Live Messenger</span><span class="sxs-lookup"><span data-stu-id="c3800-272">Required for public IM connectivity with Windows Live Messenger</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-extensible-messaging-and-presence-protocol"></a><span data-ttu-id="c3800-273">Сводка по брандмауэру для протокола XMPP</span><span class="sxs-lookup"><span data-stu-id="c3800-273">Firewall Summary for Extensible Messaging and Presence Protocol</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c3800-274">Протокол/TCP или UDP/порт</span><span class="sxs-lookup"><span data-stu-id="c3800-274">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="c3800-275">Источник (IP-адрес)</span><span class="sxs-lookup"><span data-stu-id="c3800-275">Source (IP address)</span></span></th>
<th><span data-ttu-id="c3800-276">Назначение (IP-адрес)</span><span class="sxs-lookup"><span data-stu-id="c3800-276">Destination (IP address)</span></span></th>
<th><span data-ttu-id="c3800-277">Comments</span><span class="sxs-lookup"><span data-stu-id="c3800-277">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c3800-278">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="c3800-278">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="c3800-279">Любой</span><span class="sxs-lookup"><span data-stu-id="c3800-279">Any</span></span></p></td>
<td><p><span data-ttu-id="c3800-280">IP-адрес интерфейса пограничного сервера доступа пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="c3800-280">Edge Server Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="c3800-281">Стандартный порт для связи "сервер-сервер" через XMPP.</span><span class="sxs-lookup"><span data-stu-id="c3800-281">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="c3800-282">Разрешает связь с прокси-сервером пограничного сервера XMPP от федеративных партнеров XMPP</span><span class="sxs-lookup"><span data-stu-id="c3800-282">Allows communication to the Edge Server XMPP proxy from federated XMPP partners</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c3800-283">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="c3800-283">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="c3800-284">IP-адрес интерфейса пограничного сервера доступа пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="c3800-284">Edge Server Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="c3800-285">Любой</span><span class="sxs-lookup"><span data-stu-id="c3800-285">Any</span></span></p></td>
<td><p><span data-ttu-id="c3800-286">Стандартный порт для связи "сервер-сервер" через XMPP.</span><span class="sxs-lookup"><span data-stu-id="c3800-286">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="c3800-287">Разрешает обмен данными от прокси-сервера пограничного сервера XMPP к федеративным партнерам XMPP</span><span class="sxs-lookup"><span data-stu-id="c3800-287">Allows communication from the Edge Server XMPP proxy to federated XMPP partners</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c3800-288">XMPP/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="c3800-288">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="c3800-289">Любой</span><span class="sxs-lookup"><span data-stu-id="c3800-289">Any</span></span></p></td>
<td><p><span data-ttu-id="c3800-290">Каждый внутренний интерфейсный IP-адрес пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="c3800-290">Each internal Edge Server Interface IP</span></span></p></td>
<td><p><span data-ttu-id="c3800-291">Внутренний IP-адрес пограничного сервера или пула переднего плана на внутренний IP-адрес пограничного сервера или на каждый внутренний IP-адрес пограничного пула — внутренний IP-адрес XMPP, входящий в шлюз XMPP.</span><span class="sxs-lookup"><span data-stu-id="c3800-291">Internal XMPP traffic from the XMPP Gateway on the Front End Server or Front End pool to the Edge Server internal IP address or each Edge pool member’s internal IP address</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

