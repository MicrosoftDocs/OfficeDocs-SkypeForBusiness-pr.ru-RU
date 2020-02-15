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
ms.openlocfilehash: 9020821da26c39094e7c04f3cbf72875b91ffaff
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043141"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="port-summary---single-consolidated-edge-with-public-ip-addresses-in-lync-server-2013"></a><span data-ttu-id="b7654-102">Сводка по портам — единая Объединенная пограничная с общедоступными IP-адресами в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b7654-102">Port summary - Single consolidated edge with public IP addresses in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b7654-103">_**Последнее изменение темы:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="b7654-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="b7654-104">Сервер Lync Server 2013, функции пограничного сервера, описанные в этой архитектуре сценариев, очень похожи на компоненты, реализованные в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="b7654-104">The Lync Server 2013, Edge Server functionality described in this scenario architecture is very similar to what was implemented in Lync Server 2010.</span></span> <span data-ttu-id="b7654-105">Наиболее значимым дополнением является порт **5269 по протоколу TCP** для поддержки протокола XMPP (расширяемый протокол обмена сообщениями и сведениями о присутствии).</span><span class="sxs-lookup"><span data-stu-id="b7654-105">The most noticeable addition is the port **5269 over TCP** entry for the extensible messaging and presence protocol (XMPP).</span></span> <span data-ttu-id="b7654-106">Lync Server 2013 при необходимости разворачивает прокси-сервер XMPP на пограничном или пограничном пуле и на сервере шлюза XMPP на сервере переднего плана или интерфейсном пуле.</span><span class="sxs-lookup"><span data-stu-id="b7654-106">Lync Server 2013 optionally deploys an XMPP proxy on the Edge Server or Edge pool and the XMPP gateway server on the Front End Server or Front End pool.</span></span> <span data-ttu-id="b7654-107">Сведения о планировании для обратного прокси-сервера и Федерации находятся в [сценариях для обратного прокси-сервера в Lync server 2013](lync-server-2013-scenarios-for-reverse-proxy.md) и [планировании SIP, Федерации XMPP и общедоступных мгновенных сообщений в разделах Lync Server 2013](lync-server-2013-planning-for-sip-xmpp-federation-and-public-instant-messaging.md) соответственно.</span><span class="sxs-lookup"><span data-stu-id="b7654-107">Planning information for the reverse proxy and federation are found in [Scenarios for reverse proxy in Lync Server 2013](lync-server-2013-scenarios-for-reverse-proxy.md) and [Planning for SIP, XMPP federation, and public instant messaging in Lync Server 2013](lync-server-2013-planning-for-sip-xmpp-federation-and-public-instant-messaging.md) sections, respectively.</span></span>

<span data-ttu-id="b7654-108">Кроме протокола IPv4, пограничный сервер теперь поддерживает IPv6.</span><span class="sxs-lookup"><span data-stu-id="b7654-108">In addition to IPv4, the Edge Server now supports IPv6.</span></span> <span data-ttu-id="b7654-109">Для ясности в этих сценариях используется IPv4.</span><span class="sxs-lookup"><span data-stu-id="b7654-109">For clarity, only IPv4 is used in the scenarios.</span></span>

<span data-ttu-id="b7654-110">**Сеть периметра предприятия для единого консолидированного пограничного сервера с общедоступными IP-адресами**</span><span class="sxs-lookup"><span data-stu-id="b7654-110">**Enterprise perimeter network for single consolidated edge with public IP addressing**</span></span>

<span data-ttu-id="b7654-111">![f8c144c5-e5fb-498a-823e-eb39f26b6847](images/Gg425891.f8c144c5-e5fb-498a-823e-eb39f26b6847(OCS.15).jpg "f8c144c5-e5fb-498a-823e-eb39f26b6847")</span><span class="sxs-lookup"><span data-stu-id="b7654-111">![f8c144c5-e5fb-498a-823e-eb39f26b6847](images/Gg425891.f8c144c5-e5fb-498a-823e-eb39f26b6847(OCS.15).jpg "f8c144c5-e5fb-498a-823e-eb39f26b6847")</span></span>

<div>

## <a name="port-and-protocol-details"></a><span data-ttu-id="b7654-112">Сведения о портах и протоколе</span><span class="sxs-lookup"><span data-stu-id="b7654-112">Port and Protocol Details</span></span>

<span data-ttu-id="b7654-113">Рекомендуется открывать только те порты, которые требуются для поддержки функциональной возможности, внешний доступ к которой предоставляется.</span><span class="sxs-lookup"><span data-stu-id="b7654-113">We recommend that you open only the ports required to support the functionality for which you are providing external access.</span></span>

<span data-ttu-id="b7654-p103">Для предоставления удаленного доступа в целях работы с любой пограничной службой необходимо разрешить двунаправленный трафик SIP, как показано на схеме пограничного входящего/исходящего трафика. Иначе говоря, сообщения SIP, поступающие в пограничную службу доступа и из нее, связаны со службой обмена мгновенными сообщениями и сведениями о присутствии, системой веб-конференций, аудио- и видеосвязи и федерациями.</span><span class="sxs-lookup"><span data-stu-id="b7654-p103">For remote access to work for any edge service, it is mandatory that SIP traffic is allowed to flow bidirectionally as shown in the Inbound/Outbound edge traffic figure. Stated another way, the SIP messaging to and from the Access Edge service is involved in instant messaging (IM), presence, web conferencing, audio/video (A/V) and federation.</span></span>

### <a name="firewall-summary-for-single-consolidated-edge-with-public-ip-addresses-external-interface"></a><span data-ttu-id="b7654-116">Сводная информация по брандмауэрам для одного консолидированного пограничного сервера с общедоступными IP-адресами: внешний интерфейс</span><span class="sxs-lookup"><span data-stu-id="b7654-116">Firewall Summary for Single Consolidated Edge with Public IP Addresses: External Interface</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b7654-117">Роль/протокол/TCP или UDP/порт</span><span class="sxs-lookup"><span data-stu-id="b7654-117">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="b7654-118">Исходный IP-адрес</span><span class="sxs-lookup"><span data-stu-id="b7654-118">Source IP address</span></span></th>
<th><span data-ttu-id="b7654-119">Конечный IP-адрес</span><span class="sxs-lookup"><span data-stu-id="b7654-119">Destination IP address</span></span></th>
<th><span data-ttu-id="b7654-120">Notes</span><span class="sxs-lookup"><span data-stu-id="b7654-120">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b7654-121">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="b7654-121">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="b7654-122">Любые</span><span class="sxs-lookup"><span data-stu-id="b7654-122">Any</span></span></p></td>
<td><p><span data-ttu-id="b7654-123">Прокси-служба XMPP (общий IP-адрес с пограничной службой доступа)</span><span class="sxs-lookup"><span data-stu-id="b7654-123">XMPP Proxy service (shares IP address with Access Edge service)</span></span></p></td>
<td><p><span data-ttu-id="b7654-124">Служба прокси XMPP принимает трафик от контактов XMPP в определенных федерациях XMPP</span><span class="sxs-lookup"><span data-stu-id="b7654-124">XMPP Proxy service accepts traffic from XMPP contacts in defined XMPP federations</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b7654-125">Access/HTTP/TCP/80</span><span class="sxs-lookup"><span data-stu-id="b7654-125">Access/HTTP/TCP/80</span></span></p></td>
<td><p><span data-ttu-id="b7654-126">Общедоступный IP-адрес пограничной службы доступа пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="b7654-126">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="b7654-127">Любые</span><span class="sxs-lookup"><span data-stu-id="b7654-127">Any</span></span></p></td>
<td><p><span data-ttu-id="b7654-128">Отзыв сертификата/проверка и поиск CRL</span><span class="sxs-lookup"><span data-stu-id="b7654-128">Certificate revocation/CRL check and retrieval</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b7654-129">Доступ/DNS/TCP/53</span><span class="sxs-lookup"><span data-stu-id="b7654-129">Access/DNS/TCP/53</span></span></p></td>
<td><p><span data-ttu-id="b7654-130">Общедоступный IP-адрес пограничной службы доступа пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="b7654-130">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="b7654-131">Любые</span><span class="sxs-lookup"><span data-stu-id="b7654-131">Any</span></span></p></td>
<td><p><span data-ttu-id="b7654-132">DNS-запрос по протоколу TCP</span><span class="sxs-lookup"><span data-stu-id="b7654-132">DNS query over TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b7654-133">Доступ/DNS/UDP/53</span><span class="sxs-lookup"><span data-stu-id="b7654-133">Access/DNS/UDP/53</span></span></p></td>
<td><p><span data-ttu-id="b7654-134">Общедоступный IP-адрес пограничной службы доступа пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="b7654-134">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="b7654-135">Любые</span><span class="sxs-lookup"><span data-stu-id="b7654-135">Any</span></span></p></td>
<td><p><span data-ttu-id="b7654-136">DNS-запрос по протоколу UDP</span><span class="sxs-lookup"><span data-stu-id="b7654-136">DNS query over UDP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b7654-137">/TCP/443 доступа и SIP (TLS)</span><span class="sxs-lookup"><span data-stu-id="b7654-137">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="b7654-138">Любые</span><span class="sxs-lookup"><span data-stu-id="b7654-138">Any</span></span></p></td>
<td><p><span data-ttu-id="b7654-139">Общедоступный IP-адрес пограничной службы доступа пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="b7654-139">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="b7654-140">Трафик SIP «клиент-сервер» для доступа внешних пользователей</span><span class="sxs-lookup"><span data-stu-id="b7654-140">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b7654-141">Доступ/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="b7654-141">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="b7654-142">Любые</span><span class="sxs-lookup"><span data-stu-id="b7654-142">Any</span></span></p></td>
<td><p><span data-ttu-id="b7654-143">Общедоступный IP-адрес пограничной службы доступа пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="b7654-143">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="b7654-144">Для федеративного подключения и подключения к общедоступным службам обмена мгновенными сообщениями с помощью SIP</span><span class="sxs-lookup"><span data-stu-id="b7654-144">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b7654-145">Доступ/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="b7654-145">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="b7654-146">Общедоступный IP-адрес пограничной службы доступа пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="b7654-146">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="b7654-147">Любые</span><span class="sxs-lookup"><span data-stu-id="b7654-147">Any</span></span></p></td>
<td><p><span data-ttu-id="b7654-148">Для федеративного подключения и подключения к общедоступным службам обмена мгновенными сообщениями с помощью SIP</span><span class="sxs-lookup"><span data-stu-id="b7654-148">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b7654-149">Веб-конференции/PSOM (TLS)/TCP/443</span><span class="sxs-lookup"><span data-stu-id="b7654-149">Web Conferencing/PSOM(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="b7654-150">Любые</span><span class="sxs-lookup"><span data-stu-id="b7654-150">Any</span></span></p></td>
<td><p><span data-ttu-id="b7654-151">Общедоступный IP-адрес службы веб-конференций пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="b7654-151">Edge Server Web Conferencing Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="b7654-152">Устройство для веб-конференций</span><span class="sxs-lookup"><span data-stu-id="b7654-152">Web Conferencing media</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b7654-153">АУДИО-И ВИДЕОДАННЫЕ/RTP/TCP/50000-– 999</span><span class="sxs-lookup"><span data-stu-id="b7654-153">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="b7654-154">Общедоступный IP-адрес пограничной службы доступа пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="b7654-154">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="b7654-155">Любые</span><span class="sxs-lookup"><span data-stu-id="b7654-155">Any</span></span></p></td>
<td><p><span data-ttu-id="b7654-156">Необходимо для Федерации с партнерами, работающими под управлением Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 и Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b7654-156">Required for federating with partners running Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 and Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b7654-157">АУДИО-И ВИДЕОДАННЫЕ/RTP/UDP/50000-– 999</span><span class="sxs-lookup"><span data-stu-id="b7654-157">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="b7654-158">Общедоступный IP-адрес пограничного сервера аудио-и пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="b7654-158">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="b7654-159">Любые</span><span class="sxs-lookup"><span data-stu-id="b7654-159">Any</span></span></p></td>
<td><p><span data-ttu-id="b7654-160">Обязательно только для Федерации с партнерами, работающими под управлением Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="b7654-160">Required only for federation with partners running Office Communications Server 2007</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b7654-161">АУДИО-И ВИДЕОДАННЫЕ/RTP/TCP/50000-– 999</span><span class="sxs-lookup"><span data-stu-id="b7654-161">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="b7654-162">Любые</span><span class="sxs-lookup"><span data-stu-id="b7654-162">Any</span></span></p></td>
<td><p><span data-ttu-id="b7654-163">Общедоступный IP-адрес пограничного сервера аудио-и пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="b7654-163">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="b7654-164">Обязательно только для Федерации с партнерами, работающими под управлением Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="b7654-164">Required only for federation with partners running Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b7654-165">АУДИО-И ВИДЕОДАННЫЕ/RTP/UDP/50000-– 999</span><span class="sxs-lookup"><span data-stu-id="b7654-165">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="b7654-166">Любые</span><span class="sxs-lookup"><span data-stu-id="b7654-166">Any</span></span></p></td>
<td><p><span data-ttu-id="b7654-167">Общедоступный IP-адрес пограничного сервера аудио-и пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="b7654-167">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="b7654-168">Обязательно только для Федерации с партнерами, работающими под управлением Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="b7654-168">Required only for federation with partners running Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b7654-169">АУДИО-И ВИДЕОДАННЫЕ/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="b7654-169">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="b7654-170">Общедоступный IP-адрес пограничного сервера аудио-и пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="b7654-170">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="b7654-171">Любые</span><span class="sxs-lookup"><span data-stu-id="b7654-171">Any</span></span></p></td>
<td><p><span data-ttu-id="b7654-172">3478 исходящие используется для определения версии пограничного сервера, с которым обменивается данными Lync Server, а также для мультимедийного трафика с пограничного сервера на пограничный сервер.</span><span class="sxs-lookup"><span data-stu-id="b7654-172">3478 outbound is used to determine the version of Edge Server that Lync Server is communicating with and also for media traffic from Edge Server-to-Edge Server.</span></span> <span data-ttu-id="b7654-173">Обязательно для Федерации с Lync Server 2010, Windows Live Messenger и Office Communications Server 2007 R2, а также при развертывании нескольких пограничных пулов в компании.</span><span class="sxs-lookup"><span data-stu-id="b7654-173">Required for federation with Lync Server 2010, Windows Live Messenger, and Office Communications Server 2007 R2, and also if multiple Edge pools are deployed within a company.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b7654-174">АУДИО-И ВИДЕОДАННЫЕ/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="b7654-174">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="b7654-175">Любые</span><span class="sxs-lookup"><span data-stu-id="b7654-175">Any</span></span></p></td>
<td><p><span data-ttu-id="b7654-176">Общедоступный IP-адрес пограничного сервера аудио-и пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="b7654-176">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="b7654-177">STUN/TURN — согласование кандидатов по протоколу UDP/3478</span><span class="sxs-lookup"><span data-stu-id="b7654-177">STUN/TURN negotiation of candidates over UDP/3478</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b7654-178">АУДИО-И ВИДЕОДАННЫЕ/STUN, MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="b7654-178">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="b7654-179">Любые</span><span class="sxs-lookup"><span data-stu-id="b7654-179">Any</span></span></p></td>
<td><p><span data-ttu-id="b7654-180">Общедоступный IP-адрес пограничного сервера аудио-и пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="b7654-180">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="b7654-181">STUN/TURN — согласование кандидатов по протоколу TCP/443</span><span class="sxs-lookup"><span data-stu-id="b7654-181">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b7654-182">АУДИО-И ВИДЕОДАННЫЕ/STUN, MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="b7654-182">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="b7654-183">Общедоступный IP-адрес пограничного сервера аудио-и пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="b7654-183">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="b7654-184">Любые</span><span class="sxs-lookup"><span data-stu-id="b7654-184">Any</span></span></p></td>
<td><p><span data-ttu-id="b7654-185">STUN/TURN — согласование кандидатов по протоколу TCP/443</span><span class="sxs-lookup"><span data-stu-id="b7654-185">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="firewall-summary-for-single-consolidated-edge-with-public-ip-addresses-internal-interface"></a><span data-ttu-id="b7654-186">Сводная информация по брандмауэрам для одного консолидированного пограничного сервера с общедоступными IP-адресами: внутренний интерфейс</span><span class="sxs-lookup"><span data-stu-id="b7654-186">Firewall Summary for Single Consolidated Edge with Public IP Addresses: Internal Interface</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b7654-187">Протокол/TCP или UDP/порт</span><span class="sxs-lookup"><span data-stu-id="b7654-187">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="b7654-188">Исходный IP-адрес</span><span class="sxs-lookup"><span data-stu-id="b7654-188">Source IP address</span></span></th>
<th><span data-ttu-id="b7654-189">Конечный IP-адрес</span><span class="sxs-lookup"><span data-stu-id="b7654-189">Destination IP address</span></span></th>
<th><span data-ttu-id="b7654-190">Комментарии</span><span class="sxs-lookup"><span data-stu-id="b7654-190">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b7654-191">XMPP/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="b7654-191">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="b7654-192">Любой (может быть определен как IP-адрес сервера Standard Edition, IP-адрес сервера Standard Edition или IP-адрес пула, на котором запущена служба шлюза XMPP).</span><span class="sxs-lookup"><span data-stu-id="b7654-192">Any (can be defined as Standard Edition server IP, Standard Edition server IP address, or pool IP address running the XMPP Gateway service)</span></span></p></td>
<td><p><span data-ttu-id="b7654-193">Внутренний интерфейс пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="b7654-193">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="b7654-194">Исходящий трафик XMPP из службы шлюза XMPP, работающего на сервере переднего плана или интерфейсном пуле</span><span class="sxs-lookup"><span data-stu-id="b7654-194">Outbound XMPP traffic from XMPP Gateway service running on Front End Server or Front End pool</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b7654-195">SIP/MTLS/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="b7654-195">SIP/MTLS/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="b7654-196">Любой (может быть определен как директор, IP-адрес пула директоров, сервер переднего плана или IP-адрес пула переднего плана).</span><span class="sxs-lookup"><span data-stu-id="b7654-196">Any (can be defined as Director, Director pool IP address, Front End Server or Front End pool IP address)</span></span></p></td>
<td><p><span data-ttu-id="b7654-197">IP-адрес пограничного сервера или пул, в котором хранится внутренний интерфейс</span><span class="sxs-lookup"><span data-stu-id="b7654-197">Edge Server IP, or pool that holds the internal interface</span></span></p></td>
<td><p><span data-ttu-id="b7654-198">Исходящий трафик SIP (от директора, IP-адреса пула директоров, сервера переднего плана или IP-адреса пула переднего плана) к внутреннему интерфейсу пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="b7654-198">Outbound SIP traffic (from Director, Director pool IP address, Front End Server or Front End pool IP address) to Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b7654-199">SIP/MTLS/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="b7654-199">SIP/MTLS/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="b7654-200">Внутренний интерфейс пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="b7654-200">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="b7654-201">Любой (может быть определен как директор, IP-адрес пула директоров, сервер переднего плана или адрес внешнего интерфейса пула)</span><span class="sxs-lookup"><span data-stu-id="b7654-201">Any (can be defined as Director, Director pool IP address, Front End Server or Front End pool address)</span></span></p></td>
<td><p><span data-ttu-id="b7654-202">Входящий трафик SIP (в директоре, IP-адрес пула директоров, IP-адрес сервера переднего плана или интерфейсного пула переднего плана) от внутреннего интерфейса пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="b7654-202">Inbound SIP traffic (to Director, Director pool IP address, Front End Server or Front End pool IP address) from Edge Server internal interface</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b7654-203">PSOM/MTLS/TCP/8057</span><span class="sxs-lookup"><span data-stu-id="b7654-203">PSOM/MTLS/TCP/8057</span></span></p></td>
<td><p><span data-ttu-id="b7654-204">Любой (может быть определен как IP-адрес сервера переднего плана или каждый IP-адрес сервера переднего плана в пуле переднего плана)</span><span class="sxs-lookup"><span data-stu-id="b7654-204">Any (can be defined as Front End Server IP address, or each Front End Server IP address in a Front End pool)</span></span></p></td>
<td><p><span data-ttu-id="b7654-205">Внутренний интерфейс пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="b7654-205">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="b7654-206">Трафик веб-конференций от сервера переднего плана или сервера переднего плана в пул, внутренний интерфейс пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="b7654-206">Web conferencing traffic from Front End Server or each Front End Server if in a pool, to Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b7654-207">SIP/MTLS/TCP/5062</span><span class="sxs-lookup"><span data-stu-id="b7654-207">SIP/MTLS/TCP/5062</span></span></p></td>
<td><p><span data-ttu-id="b7654-208">Любой (может быть определен как IP-адрес сервера переднего плана или IP-адрес пула переднего плана или любое устройство для обеспечения связи в филиале или как сервер для обеспечения связи в филиалах с помощью этого пограничного сервера)</span><span class="sxs-lookup"><span data-stu-id="b7654-208">Any (can be defined as Front End Server IP address, or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server)</span></span></p></td>
<td><p><span data-ttu-id="b7654-209">Внутренний интерфейс пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="b7654-209">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="b7654-210">Проверка подлинности пользователей и подлинности (служба проверки подлинности A/V) с IP-адреса сервера переднего плана или интерфейсного пула или любого устройства для обеспечения связи в филиалах или сервера обеспечения связи в филиалах с помощью этого пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="b7654-210">Authentication of A/V users (A/V authentication service) from Front End Server or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b7654-211">STUN/MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="b7654-211">STUN/MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="b7654-212">Любые</span><span class="sxs-lookup"><span data-stu-id="b7654-212">Any</span></span></p></td>
<td><p><span data-ttu-id="b7654-213">Внутренний интерфейс пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="b7654-213">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="b7654-214">Предпочтительный путь для передачи аудио-и видеоданных между внутренними и внешними пользователями, устройством для обеспечения связи в филиалах или сервером обеспечения связи в филиалах</span><span class="sxs-lookup"><span data-stu-id="b7654-214">Preferred path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b7654-215">STUN/MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="b7654-215">STUN/MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="b7654-216">Любые</span><span class="sxs-lookup"><span data-stu-id="b7654-216">Any</span></span></p></td>
<td><p><span data-ttu-id="b7654-217">Внутренний интерфейс пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="b7654-217">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="b7654-218">Резервный путь для передачи аудио-и видеоданных между внутренними и внешними пользователями, устройства для обеспечения связи в филиалах или сервера для обеспечения связи в филиалах если не удается установить UDP-связь, используется TCP для передачи файлов и общего доступа к рабочему столу</span><span class="sxs-lookup"><span data-stu-id="b7654-218">Fallback path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server if UDP communication cannot be established, TCP is used for file transfer and desktop sharing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b7654-219">HTTPS/TCP/4443</span><span class="sxs-lookup"><span data-stu-id="b7654-219">HTTPS/TCP/4443</span></span></p></td>
<td><p><span data-ttu-id="b7654-220">Любой (может быть определен как IP-адрес сервера переднего плана или пул, в котором хранится центральное хранилище управления)</span><span class="sxs-lookup"><span data-stu-id="b7654-220">Any (can be defined as the Front End Server IP address, or pool that holds the Central Management store)</span></span></p></td>
<td><p><span data-ttu-id="b7654-221">Внутренний интерфейс пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="b7654-221">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="b7654-222">Репликация изменений из центрального хранилища управления на пограничный сервер</span><span class="sxs-lookup"><span data-stu-id="b7654-222">Replication of changes from the Central Management store to the Edge Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b7654-223">MTLS/TCP/50001</span><span class="sxs-lookup"><span data-stu-id="b7654-223">MTLS/TCP/50001</span></span></p></td>
<td><p><span data-ttu-id="b7654-224">Любые</span><span class="sxs-lookup"><span data-stu-id="b7654-224">Any</span></span></p></td>
<td><p><span data-ttu-id="b7654-225">Внутренний интерфейс пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="b7654-225">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="b7654-226">Централизованное ведение журналов с помощью команд Командная консоль Lync Server и командлетов службы централизованного ведения журналов, Командная строка ClsController (ClsController. exe) или агента (ClsAgent. exe) и коллекция журналов</span><span class="sxs-lookup"><span data-stu-id="b7654-226">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b7654-227">MTLS/TCP/50002</span><span class="sxs-lookup"><span data-stu-id="b7654-227">MTLS/TCP/50002</span></span></p></td>
<td><p><span data-ttu-id="b7654-228">Любые</span><span class="sxs-lookup"><span data-stu-id="b7654-228">Any</span></span></p></td>
<td><p><span data-ttu-id="b7654-229">Внутренний интерфейс пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="b7654-229">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="b7654-230">Централизованное ведение журналов с помощью команд Командная консоль Lync Server и командлетов службы централизованного ведения журналов, Командная строка ClsController (ClsController. exe) или агента (ClsAgent. exe) и коллекция журналов</span><span class="sxs-lookup"><span data-stu-id="b7654-230">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b7654-231">MTLS/TCP/50003</span><span class="sxs-lookup"><span data-stu-id="b7654-231">MTLS/TCP/50003</span></span></p></td>
<td><p><span data-ttu-id="b7654-232">Любые</span><span class="sxs-lookup"><span data-stu-id="b7654-232">Any</span></span></p></td>
<td><p><span data-ttu-id="b7654-233">Внутренний интерфейс пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="b7654-233">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="b7654-234">Централизованное ведение журналов с помощью команд Командная консоль Lync Server и командлетов службы централизованного ведения журналов, Командная строка ClsController (ClsController. exe) или агента (ClsAgent. exe) и коллекция журналов</span><span class="sxs-lookup"><span data-stu-id="b7654-234">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-federation"></a><span data-ttu-id="b7654-235">Сводка по брандмауэру для федерации</span><span class="sxs-lookup"><span data-stu-id="b7654-235">Firewall Summary for Federation</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b7654-236">Роль/протокол/TCP или UDP/порт</span><span class="sxs-lookup"><span data-stu-id="b7654-236">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="b7654-237">Исходный IP-адрес</span><span class="sxs-lookup"><span data-stu-id="b7654-237">Source IP address</span></span></th>
<th><span data-ttu-id="b7654-238">Конечный IP-адрес</span><span class="sxs-lookup"><span data-stu-id="b7654-238">Destination IP address</span></span></th>
<th><span data-ttu-id="b7654-239">Notes</span><span class="sxs-lookup"><span data-stu-id="b7654-239">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b7654-240">Доступ/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="b7654-240">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="b7654-241">Общедоступный IP-адрес пограничной службы доступа</span><span class="sxs-lookup"><span data-stu-id="b7654-241">Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="b7654-242">Любые</span><span class="sxs-lookup"><span data-stu-id="b7654-242">Any</span></span></p></td>
<td><p><span data-ttu-id="b7654-243">Для федеративного подключения и подключения к общедоступным службам обмена мгновенными сообщениями с помощью SIP</span><span class="sxs-lookup"><span data-stu-id="b7654-243">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary--public-instant-messaging-connectivity"></a><span data-ttu-id="b7654-244">Сводка по брандмауэру — связь с общедоступной службой обмена мгновенными сообщениями</span><span class="sxs-lookup"><span data-stu-id="b7654-244">Firewall Summary – Public Instant Messaging Connectivity</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b7654-245">Роль/протокол/TCP или UDP/порт</span><span class="sxs-lookup"><span data-stu-id="b7654-245">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="b7654-246">Исходный IP-адрес</span><span class="sxs-lookup"><span data-stu-id="b7654-246">Source IP address</span></span></th>
<th><span data-ttu-id="b7654-247">Конечный IP-адрес</span><span class="sxs-lookup"><span data-stu-id="b7654-247">Destination IP address</span></span></th>
<th><span data-ttu-id="b7654-248">Notes</span><span class="sxs-lookup"><span data-stu-id="b7654-248">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b7654-249">Доступ/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="b7654-249">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="b7654-250">Партнеры по связи с общедоступной службой обмена мгновенными сообщениями</span><span class="sxs-lookup"><span data-stu-id="b7654-250">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="b7654-251">Пограничный сервер доступа, пограничная служба доступа</span><span class="sxs-lookup"><span data-stu-id="b7654-251">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="b7654-252">Для федеративной и общедоступной службы обмена мгновенными сообщениями посредством SIP</span><span class="sxs-lookup"><span data-stu-id="b7654-252">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b7654-253">Доступ/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="b7654-253">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="b7654-254">Пограничный сервер доступа, пограничная служба доступа</span><span class="sxs-lookup"><span data-stu-id="b7654-254">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="b7654-255">Партнеры по связи с общедоступной службой обмена мгновенными сообщениями</span><span class="sxs-lookup"><span data-stu-id="b7654-255">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="b7654-256">Для связи с федеративными и общедоступными системами обмена сообщениями через SIP</span><span class="sxs-lookup"><span data-stu-id="b7654-256">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b7654-257">/TCP/443 доступа и SIP (TLS)</span><span class="sxs-lookup"><span data-stu-id="b7654-257">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="b7654-258">Клиенты</span><span class="sxs-lookup"><span data-stu-id="b7654-258">Clients</span></span></p></td>
<td><p><span data-ttu-id="b7654-259">Пограничный сервер доступа, пограничная служба доступа</span><span class="sxs-lookup"><span data-stu-id="b7654-259">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="b7654-260">Трафик SIP от клиента к серверу для доступа внешних пользователей</span><span class="sxs-lookup"><span data-stu-id="b7654-260">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b7654-261">АУДИО-И ВИДЕОДАННЫЕ/RTP/TCP/50000-– 999</span><span class="sxs-lookup"><span data-stu-id="b7654-261">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="b7654-262">Пограничный сервер, пограничная служба аудио- и видеоданных</span><span class="sxs-lookup"><span data-stu-id="b7654-262">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="b7654-263">Клиенты Live Messenger</span><span class="sxs-lookup"><span data-stu-id="b7654-263">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="b7654-264">Используется для сеансов аудио- и видеоконференций с использованием Windows Live Messenger, если настроена связь с общедоступной службой обмена мгновенными сообщениями.</span><span class="sxs-lookup"><span data-stu-id="b7654-264">Used for A/V sessions with Windows Live Messenger if public IM connectivity is configured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b7654-265">АУДИО-И ВИДЕОДАННЫЕ/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="b7654-265">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="b7654-266">Пограничный сервер, пограничная служба аудио- и видеоданных</span><span class="sxs-lookup"><span data-stu-id="b7654-266">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="b7654-267">Клиенты Live Messenger</span><span class="sxs-lookup"><span data-stu-id="b7654-267">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="b7654-268">Требуется для связи с общедоступной службой обмена мгновенными сообщениями с помощью Windows Live Messenger</span><span class="sxs-lookup"><span data-stu-id="b7654-268">Required for public IM connectivity with Windows Live Messenger</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b7654-269">АУДИО-И ВИДЕОДАННЫЕ/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="b7654-269">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="b7654-270">Клиенты Live Messenger</span><span class="sxs-lookup"><span data-stu-id="b7654-270">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="b7654-271">Пограничный сервер, пограничная служба аудио- и видеоданных</span><span class="sxs-lookup"><span data-stu-id="b7654-271">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="b7654-272">Требуется для связи с общедоступной службой обмена мгновенными сообщениями с помощью Windows Live Messenger</span><span class="sxs-lookup"><span data-stu-id="b7654-272">Required for public IM connectivity with Windows Live Messenger</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-extensible-messaging-and-presence-protocol"></a><span data-ttu-id="b7654-273">Сводка по брандмауэру для протокола XMPP</span><span class="sxs-lookup"><span data-stu-id="b7654-273">Firewall Summary for Extensible Messaging and Presence Protocol</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b7654-274">Протокол/TCP или UDP/порт</span><span class="sxs-lookup"><span data-stu-id="b7654-274">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="b7654-275">Источник (IP-адрес)</span><span class="sxs-lookup"><span data-stu-id="b7654-275">Source (IP address)</span></span></th>
<th><span data-ttu-id="b7654-276">Назначение (IP-адрес)</span><span class="sxs-lookup"><span data-stu-id="b7654-276">Destination (IP address)</span></span></th>
<th><span data-ttu-id="b7654-277">Комментарии</span><span class="sxs-lookup"><span data-stu-id="b7654-277">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b7654-278">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="b7654-278">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="b7654-279">Любые</span><span class="sxs-lookup"><span data-stu-id="b7654-279">Any</span></span></p></td>
<td><p><span data-ttu-id="b7654-280">IP-адрес интерфейса пограничного сервера доступа пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="b7654-280">Edge Server Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="b7654-281">Стандартный порт для связи "сервер-сервер" через XMPP.</span><span class="sxs-lookup"><span data-stu-id="b7654-281">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="b7654-282">Разрешает связь с прокси-сервером пограничного сервера XMPP от федеративных партнеров XMPP</span><span class="sxs-lookup"><span data-stu-id="b7654-282">Allows communication to the Edge Server XMPP proxy from federated XMPP partners</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b7654-283">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="b7654-283">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="b7654-284">IP-адрес интерфейса пограничного сервера доступа пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="b7654-284">Edge Server Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="b7654-285">Любые</span><span class="sxs-lookup"><span data-stu-id="b7654-285">Any</span></span></p></td>
<td><p><span data-ttu-id="b7654-286">Стандартный порт для связи "сервер-сервер" через XMPP.</span><span class="sxs-lookup"><span data-stu-id="b7654-286">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="b7654-287">Разрешает обмен данными от прокси-сервера пограничного сервера XMPP к федеративным партнерам XMPP</span><span class="sxs-lookup"><span data-stu-id="b7654-287">Allows communication from the Edge Server XMPP proxy to federated XMPP partners</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b7654-288">XMPP/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="b7654-288">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="b7654-289">Любые</span><span class="sxs-lookup"><span data-stu-id="b7654-289">Any</span></span></p></td>
<td><p><span data-ttu-id="b7654-290">Каждый внутренний интерфейсный IP-адрес пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="b7654-290">Each internal Edge Server Interface IP</span></span></p></td>
<td><p><span data-ttu-id="b7654-291">Внутренний IP-адрес пограничного сервера или пула переднего плана на внутренний IP-адрес пограничного сервера или на каждый внутренний IP-адрес пограничного пула — внутренний IP-адрес XMPP, входящий в шлюз XMPP.</span><span class="sxs-lookup"><span data-stu-id="b7654-291">Internal XMPP traffic from the XMPP Gateway on the Front End Server or Front End pool to the Edge Server internal IP address or each Edge pool member’s internal IP address</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

