---
title: 'Lync Server 2013: сводка по портам — масштабируемый консолидированный край, балансировка нагрузки на DNS с общедоступными IP-адресами'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Port summary - Scaled consolidated edge, DNS load balancing with public IP addresses
ms:assetid: f7cbd0f1-841d-4116-8d17-e9d991daa4a8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205394(v=OCS.15)
ms:contentKeyID: 48185865
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5f49a5f14d66e921dc84c42553d3af6a6dddf925
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42034069"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="port-summary---scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses-in-lync-server-2013"></a><span data-ttu-id="7c9a9-102">Сводка по портам — масштабируемый консолидированный край, балансировка нагрузки на DNS с общедоступными IP-адресами в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7c9a9-102">Port summary - Scaled consolidated edge, DNS load balancing with public IP addresses in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7c9a9-103">_**Последнее изменение темы:** 2013-04-03_</span><span class="sxs-lookup"><span data-stu-id="7c9a9-103">_**Topic Last Modified:** 2013-04-03_</span></span>

<span data-ttu-id="7c9a9-104">Сервер Lync Server 2013, функции пограничного сервера, описанные в этой архитектуре сценариев, очень похожи на компоненты, реализованные в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="7c9a9-104">The Lync Server 2013, Edge Server functionality described in this scenario architecture is very similar to what was implemented in Lync Server 2010.</span></span> <span data-ttu-id="7c9a9-105">Наиболее значимым дополнением является порт **5269 по протоколу TCP** для поддержки протокола XMPP (расширяемый протокол обмена сообщениями и сведениями о присутствии).</span><span class="sxs-lookup"><span data-stu-id="7c9a9-105">The most noticeable addition is the port **5269 over TCP** entry for the extensible messaging and presence protocol (XMPP).</span></span> <span data-ttu-id="7c9a9-106">Lync Server 2013 при необходимости разворачивает прокси-сервер XMPP на пограничном или пограничном пуле и на сервере шлюза XMPP на сервере переднего плана или интерфейсном пуле.</span><span class="sxs-lookup"><span data-stu-id="7c9a9-106">Lync Server 2013 optionally deploys an XMPP proxy on the Edge Server or Edge pool and the XMPP gateway server on the Front End Server or Front End pool.</span></span>

<span data-ttu-id="7c9a9-107">Кроме протокола IPv4, пограничный сервер теперь поддерживает IPv6.</span><span class="sxs-lookup"><span data-stu-id="7c9a9-107">In addition to IPv4, the Edge Server now supports IPv6.</span></span> <span data-ttu-id="7c9a9-108">Для ясности в этих сценариях используется IPv4.</span><span class="sxs-lookup"><span data-stu-id="7c9a9-108">For clarity, only IPv4 is used in the scenarios.</span></span>

<span data-ttu-id="7c9a9-109">**Сеть периметра предприятия для масштабируемого консолидированного периметра, балансировка нагрузки на DNS с общедоступными IP-адресами**</span><span class="sxs-lookup"><span data-stu-id="7c9a9-109">**Enterprise perimeter network for Scaled Consolidated Edge, DNS Load Balancing with Public IP Addresses**</span></span>

<span data-ttu-id="7c9a9-110">![96f5a8f5-16d2-464d-b86e-7c7ecfc89ead](images/JJ205394.96f5a8f5-16d2-464d-b86e-7c7ecfc89ead(OCS.15).jpg "96f5a8f5-16d2-464d-b86e-7c7ecfc89ead")</span><span class="sxs-lookup"><span data-stu-id="7c9a9-110">![96f5a8f5-16d2-464d-b86e-7c7ecfc89ead](images/JJ205394.96f5a8f5-16d2-464d-b86e-7c7ecfc89ead(OCS.15).jpg "96f5a8f5-16d2-464d-b86e-7c7ecfc89ead")</span></span>

<div>

## <a name="port-and-protocol-details"></a><span data-ttu-id="7c9a9-111">Сведения о портах и протоколе</span><span class="sxs-lookup"><span data-stu-id="7c9a9-111">Port and Protocol Details</span></span>

<span data-ttu-id="7c9a9-112">Рекомендуется открывать только те порты, которые требуются для поддержки функциональной возможности, к которой предоставляется внешний доступ.</span><span class="sxs-lookup"><span data-stu-id="7c9a9-112">It is recommended that you open only the ports required to support the functionality for which you are providing external access.</span></span>

<span data-ttu-id="7c9a9-p103">Для предоставления удаленного доступа в целях работы с любой пограничной службой необходимо разрешить двунаправленный трафик SIP, как показано на схеме пограничного входящего/исходящего трафика. Иначе говоря, сообщения SIP, поступающие в пограничную службу доступа и из нее, связаны со службой обмена мгновенными сообщениями и сведениями о присутствии, системой веб-конференций, аудио- и видеосвязи и федерациями.</span><span class="sxs-lookup"><span data-stu-id="7c9a9-p103">For remote access to work for any edge service, it is mandatory that SIP traffic is allowed to flow bi-directionally as shown in the Inbound/Outbound edge traffic figure. Stated another way, the SIP messaging to and from the Access Edge service is involved in instant messaging (IM), presence, web conferencing, audio/video (A/V) and federation.</span></span>

### <a name="firewall-summary-for-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses-external-interface--node-1-and-node-2-example"></a><span data-ttu-id="7c9a9-115">Сводка по брандмауэру для масштабируемых консолидированных пограничных серверов, балансировка нагрузки на DNS с общедоступными IP-адресами: внешний интерфейс — узел 1 и узел 2 (пример)</span><span class="sxs-lookup"><span data-stu-id="7c9a9-115">Firewall Summary for Scaled Consolidated Edge, DNS Load Balancing with Public IP Addresses: External Interface – Node 1 and Node 2 (Example)</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7c9a9-116">Роль/протокол/TCP или UDP/порт</span><span class="sxs-lookup"><span data-stu-id="7c9a9-116">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="7c9a9-117">Исходный IP-адрес</span><span class="sxs-lookup"><span data-stu-id="7c9a9-117">Source IP address</span></span></th>
<th><span data-ttu-id="7c9a9-118">Конечный IP-адрес</span><span class="sxs-lookup"><span data-stu-id="7c9a9-118">Destination IP address</span></span></th>
<th><span data-ttu-id="7c9a9-119">Notes</span><span class="sxs-lookup"><span data-stu-id="7c9a9-119">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7c9a9-120">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="7c9a9-120">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="7c9a9-121">Любые</span><span class="sxs-lookup"><span data-stu-id="7c9a9-121">Any</span></span></p></td>
<td><p><span data-ttu-id="7c9a9-122">Прокси-служба XMPP (общий IP-адрес с пограничной службой доступа)</span><span class="sxs-lookup"><span data-stu-id="7c9a9-122">XMPP Proxy service (shares IP address with Access Edge service)</span></span></p></td>
<td><p><span data-ttu-id="7c9a9-123">Служба прокси XMPP принимает трафик от контактов XMPP в определенных федерациях XMPP</span><span class="sxs-lookup"><span data-stu-id="7c9a9-123">XMPP Proxy service accepts traffic from XMPP contacts in defined XMPP federations</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7c9a9-124">Access/HTTP/TCP/80</span><span class="sxs-lookup"><span data-stu-id="7c9a9-124">Access/HTTP/TCP/80</span></span></p></td>
<td><p><span data-ttu-id="7c9a9-125">Общедоступный IP-адрес пограничной службы доступа пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="7c9a9-125">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="7c9a9-126">Любые</span><span class="sxs-lookup"><span data-stu-id="7c9a9-126">Any</span></span></p></td>
<td><p><span data-ttu-id="7c9a9-127">Отзыв сертификата/проверка и поиск CRL</span><span class="sxs-lookup"><span data-stu-id="7c9a9-127">Certificate revocation/CRL check and retrieval</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7c9a9-128">Доступ/DNS/TCP/53</span><span class="sxs-lookup"><span data-stu-id="7c9a9-128">Access/DNS/TCP/53</span></span></p></td>
<td><p><span data-ttu-id="7c9a9-129">Общедоступный IP-адрес пограничной службы доступа пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="7c9a9-129">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="7c9a9-130">Любые</span><span class="sxs-lookup"><span data-stu-id="7c9a9-130">Any</span></span></p></td>
<td><p><span data-ttu-id="7c9a9-131">DNS-запрос по протоколу TCP</span><span class="sxs-lookup"><span data-stu-id="7c9a9-131">DNS query over TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7c9a9-132">Доступ/DNS/UDP/53</span><span class="sxs-lookup"><span data-stu-id="7c9a9-132">Access/DNS/UDP/53</span></span></p></td>
<td><p><span data-ttu-id="7c9a9-133">Общедоступный IP-адрес пограничной службы доступа пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="7c9a9-133">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="7c9a9-134">Любые</span><span class="sxs-lookup"><span data-stu-id="7c9a9-134">Any</span></span></p></td>
<td><p><span data-ttu-id="7c9a9-135">DNS-запрос по протоколу UDP</span><span class="sxs-lookup"><span data-stu-id="7c9a9-135">DNS query over UDP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7c9a9-136">/TCP/443 доступа и SIP (TLS)</span><span class="sxs-lookup"><span data-stu-id="7c9a9-136">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="7c9a9-137">Любые</span><span class="sxs-lookup"><span data-stu-id="7c9a9-137">Any</span></span></p></td>
<td><p><span data-ttu-id="7c9a9-138">Общедоступный IP-адрес пограничной службы доступа пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="7c9a9-138">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="7c9a9-139">Трафик SIP «клиент-сервер» для доступа внешних пользователей</span><span class="sxs-lookup"><span data-stu-id="7c9a9-139">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7c9a9-140">Доступ/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="7c9a9-140">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="7c9a9-141">Любые</span><span class="sxs-lookup"><span data-stu-id="7c9a9-141">Any</span></span></p></td>
<td><p><span data-ttu-id="7c9a9-142">Общедоступный IP-адрес пограничной службы доступа пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="7c9a9-142">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="7c9a9-143">Для федеративного подключения и подключения к общедоступным службам обмена мгновенными сообщениями с помощью SIP</span><span class="sxs-lookup"><span data-stu-id="7c9a9-143">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7c9a9-144">Доступ/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="7c9a9-144">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="7c9a9-145">Общедоступный IP-адрес пограничной службы доступа пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="7c9a9-145">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="7c9a9-146">Любые</span><span class="sxs-lookup"><span data-stu-id="7c9a9-146">Any</span></span></p></td>
<td><p><span data-ttu-id="7c9a9-147">Для федеративной и общедоступной службы обмена мгновенными сообщениями посредством SIP</span><span class="sxs-lookup"><span data-stu-id="7c9a9-147">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7c9a9-148">Веб-конференции/PSOM(TLS)TCP/443</span><span class="sxs-lookup"><span data-stu-id="7c9a9-148">Web Conferencing/PSOM(TLS)TCP/443</span></span></p></td>
<td><p><span data-ttu-id="7c9a9-149">Любые</span><span class="sxs-lookup"><span data-stu-id="7c9a9-149">Any</span></span></p></td>
<td><p><span data-ttu-id="7c9a9-150">Общедоступный IP-адрес службы веб-конференций пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="7c9a9-150">Edge Server Web Conferencing Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="7c9a9-151">Устройство для веб-конференций</span><span class="sxs-lookup"><span data-stu-id="7c9a9-151">Web Conferencing media</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7c9a9-152">АУДИО-И ВИДЕОДАННЫЕ/RTP/TCP/50000-– 999</span><span class="sxs-lookup"><span data-stu-id="7c9a9-152">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="7c9a9-153">Общедоступный IP-адрес пограничного сервера аудио-и пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="7c9a9-153">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="7c9a9-154">Любые</span><span class="sxs-lookup"><span data-stu-id="7c9a9-154">Any</span></span></p></td>
<td><p><span data-ttu-id="7c9a9-155">Необходимо для Федерации с партнерами, работающими под управлением Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 и Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7c9a9-155">Required for federating with partners running Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 and Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7c9a9-156">АУДИО-И ВИДЕОДАННЫЕ/RTP/UDP/50000-– 999</span><span class="sxs-lookup"><span data-stu-id="7c9a9-156">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="7c9a9-157">Общедоступный IP-адрес пограничного сервера аудио-и пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="7c9a9-157">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="7c9a9-158">Любые</span><span class="sxs-lookup"><span data-stu-id="7c9a9-158">Any</span></span></p></td>
<td><p><span data-ttu-id="7c9a9-159">Обязательно только для Федерации с партнерами, работающими под управлением Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="7c9a9-159">Required only for federation with partners running Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7c9a9-160">АУДИО-И ВИДЕОДАННЫЕ/RTP/TCP/50000-– 999</span><span class="sxs-lookup"><span data-stu-id="7c9a9-160">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="7c9a9-161">Любые</span><span class="sxs-lookup"><span data-stu-id="7c9a9-161">Any</span></span></p></td>
<td><p><span data-ttu-id="7c9a9-162">Общедоступный IP-адрес пограничного сервера аудио-и пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="7c9a9-162">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="7c9a9-163">Обязательно только для Федерации с партнерами, работающими под управлением Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="7c9a9-163">Required only for federation with partners running Office Communications Server 2007</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7c9a9-164">АУДИО-И ВИДЕОДАННЫЕ/RTP/UDP/50000-– 999</span><span class="sxs-lookup"><span data-stu-id="7c9a9-164">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="7c9a9-165">Любые</span><span class="sxs-lookup"><span data-stu-id="7c9a9-165">Any</span></span></p></td>
<td><p><span data-ttu-id="7c9a9-166">Общедоступный IP-адрес пограничного сервера аудио-и пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="7c9a9-166">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="7c9a9-167">Обязательно только для Федерации с партнерами, работающими под управлением Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="7c9a9-167">Required only for federation with partners running Office Communications Server 2007</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7c9a9-168">АУДИО-И ВИДЕОДАННЫЕ/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="7c9a9-168">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="7c9a9-169">Общедоступный IP-адрес пограничного сервера аудио-и пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="7c9a9-169">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="7c9a9-170">Любые</span><span class="sxs-lookup"><span data-stu-id="7c9a9-170">Any</span></span></p></td>
<td><p><span data-ttu-id="7c9a9-171">3478 исходящие используется для определения версии пограничного сервера, с которым обменивается данными Lync Server, а также для мультимедийного трафика с пограничного сервера на пограничный сервер.</span><span class="sxs-lookup"><span data-stu-id="7c9a9-171">3478 outbound is used to determine the version of Edge Server that Lync Server is communicating with and also for media traffic from Edge Server-to-Edge Server.</span></span> <span data-ttu-id="7c9a9-172">Обязательно для Федерации с Lync Server 2010, Windows Live Messenger и Office Communications Server 2007 R2, а также при развертывании нескольких пограничных пулов в компании.</span><span class="sxs-lookup"><span data-stu-id="7c9a9-172">Required for federation with Lync Server 2010, Windows Live Messenger, and Office Communications Server 2007 R2, and also if multiple Edge pools are deployed within a company.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7c9a9-173">АУДИО-И ВИДЕОДАННЫЕ/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="7c9a9-173">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="7c9a9-174">Любые</span><span class="sxs-lookup"><span data-stu-id="7c9a9-174">Any</span></span></p></td>
<td><p><span data-ttu-id="7c9a9-175">Общедоступный IP-адрес пограничного сервера аудио-и пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="7c9a9-175">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="7c9a9-176">STUN/TURN — согласование кандидатов по протоколу UDP/3478</span><span class="sxs-lookup"><span data-stu-id="7c9a9-176">STUN/TURN negotiation of candidates over UDP/3478</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7c9a9-177">АУДИО-И ВИДЕОДАННЫЕ/STUN, MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="7c9a9-177">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="7c9a9-178">Любые</span><span class="sxs-lookup"><span data-stu-id="7c9a9-178">Any</span></span></p></td>
<td><p><span data-ttu-id="7c9a9-179">Общедоступный IP-адрес пограничного сервера аудио-и пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="7c9a9-179">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="7c9a9-180">STUN/TURN — согласование кандидатов по протоколу TCP/443</span><span class="sxs-lookup"><span data-stu-id="7c9a9-180">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7c9a9-181">АУДИО-И ВИДЕОДАННЫЕ/STUN, MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="7c9a9-181">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="7c9a9-182">Пограничный сервер, пограничная служба аудио- и видеоданных</span><span class="sxs-lookup"><span data-stu-id="7c9a9-182">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="7c9a9-183">Любые</span><span class="sxs-lookup"><span data-stu-id="7c9a9-183">Any</span></span></p></td>
<td><p><span data-ttu-id="7c9a9-184">STUN/TURN — согласование кандидатов по протоколу TCP/443</span><span class="sxs-lookup"><span data-stu-id="7c9a9-184">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="firewall-summary-for-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses-internal-interface--node-1-and-node-2-example"></a><span data-ttu-id="7c9a9-185">Сводная информация по брандмауэрам для масштабируемого консолидированного пограничного сервера, балансировка нагрузки DNS с общедоступными IP-адресами: внутренний интерфейс — узел 1 и узел 2 (пример)</span><span class="sxs-lookup"><span data-stu-id="7c9a9-185">Firewall Summary for Scaled Consolidated Edge, DNS Load Balancing with Public IP Addresses: Internal Interface – Node 1 and Node 2 (Example)</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7c9a9-186">Протокол/TCP или UDP/порт</span><span class="sxs-lookup"><span data-stu-id="7c9a9-186">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="7c9a9-187">Исходный IP-адрес</span><span class="sxs-lookup"><span data-stu-id="7c9a9-187">Source IP address</span></span></th>
<th><span data-ttu-id="7c9a9-188">Конечный IP-адрес</span><span class="sxs-lookup"><span data-stu-id="7c9a9-188">Destination IP address</span></span></th>
<th><span data-ttu-id="7c9a9-189">Комментарии</span><span class="sxs-lookup"><span data-stu-id="7c9a9-189">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7c9a9-190">XMPP/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="7c9a9-190">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="7c9a9-191">Любой (может быть определен как адрес сервера переднего плана или IP-адрес пула переднего плана, на котором запущена служба шлюза XMPP)</span><span class="sxs-lookup"><span data-stu-id="7c9a9-191">Any (can be defined as Front End Server address, or Front End pool IP address running the XMPP Gateway service)</span></span></p></td>
<td><p><span data-ttu-id="7c9a9-192">Внутренний интерфейс пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="7c9a9-192">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="7c9a9-193">Исходящий трафик XMPP из службы шлюза XMPP, работающего на сервере переднего плана или интерфейсном пуле</span><span class="sxs-lookup"><span data-stu-id="7c9a9-193">Outbound XMPP traffic from XMPP Gateway service running on Front End Server or Front End pool</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7c9a9-194">SIP/MTLS/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="7c9a9-194">SIP/MTLS/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="7c9a9-195">Любой (может быть определен как директор, IP-адрес пула директоров, сервер переднего плана или IP-адрес пула переднего плана).</span><span class="sxs-lookup"><span data-stu-id="7c9a9-195">Any (can be defined as Director, Director pool IP address, Front End Server or Front End pool IP address)</span></span></p></td>
<td><p><span data-ttu-id="7c9a9-196">Внутренний интерфейс пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="7c9a9-196">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="7c9a9-197">Исходящий трафик SIP (от директора, IP-адреса пула директоров, сервера переднего плана или IP-адреса пула переднего плана) к внутреннему интерфейсу пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="7c9a9-197">Outbound SIP traffic (from Director, Director pool IP address, Front End Server or Front End pool IP address) to Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7c9a9-198">SIP/MTLS/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="7c9a9-198">SIP/MTLS/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="7c9a9-199">Внутренний интерфейс пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="7c9a9-199">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="7c9a9-200">Любой (может быть определен как директор, IP-адрес пула директоров, сервер переднего плана или IP-адрес пула переднего плана).</span><span class="sxs-lookup"><span data-stu-id="7c9a9-200">Any (can be defined as Director, Director pool IP address, Front End Server or Front End pool IP address)</span></span></p></td>
<td><p><span data-ttu-id="7c9a9-201">Входящий трафик SIP (в директоре, IP-адрес пула директоров, IP-адрес сервера переднего плана или интерфейсного пула переднего плана) от внутреннего интерфейса пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="7c9a9-201">Inbound SIP traffic (to Director, Director pool IP address, Front End Server or Front End pool IP address) from Edge Server internal interface</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7c9a9-202">PSOM/MTLS/TCP/8057</span><span class="sxs-lookup"><span data-stu-id="7c9a9-202">PSOM/MTLS/TCP/8057</span></span></p></td>
<td><p><span data-ttu-id="7c9a9-203">Любой (может быть определен как IP-адрес сервера переднего плана или каждый IP-адрес сервера переднего плана в пуле переднего плана)</span><span class="sxs-lookup"><span data-stu-id="7c9a9-203">Any (can be defined as Front End Server IP address, or each Front End Server IP address in a Front End pool)</span></span></p></td>
<td><p><span data-ttu-id="7c9a9-204">Внутренний интерфейс пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="7c9a9-204">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="7c9a9-205">Трафик веб-конференций от сервера переднего плана или сервера переднего плана в пул, внутренний интерфейс пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="7c9a9-205">Web conferencing traffic from Front End Server or each Front End Server if in a pool, to Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7c9a9-206">SIP/MTLS/TCP/5062</span><span class="sxs-lookup"><span data-stu-id="7c9a9-206">SIP/MTLS/TCP/5062</span></span></p></td>
<td><p><span data-ttu-id="7c9a9-207">Любой (может быть определен как IP-адрес сервера переднего плана или IP-адрес пула переднего плана или любое устройство для обеспечения связи в филиале или как сервер для обеспечения связи в филиалах с помощью этого пограничного сервера)</span><span class="sxs-lookup"><span data-stu-id="7c9a9-207">Any (can be defined as Front End Server IP address, or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server)</span></span></p></td>
<td><p><span data-ttu-id="7c9a9-208">Внутренний интерфейс пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="7c9a9-208">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="7c9a9-209">Проверка подлинности пользователей и подлинности (служба проверки подлинности A/V) с IP-адреса сервера переднего плана или интерфейсного пула или любого устройства для обеспечения связи в филиалах или сервера обеспечения связи в филиалах с помощью этого пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="7c9a9-209">Authentication of A/V users (A/V authentication service) from Front End Server or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7c9a9-210">STUN/MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="7c9a9-210">STUN/MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="7c9a9-211">Любые</span><span class="sxs-lookup"><span data-stu-id="7c9a9-211">Any</span></span></p></td>
<td><p><span data-ttu-id="7c9a9-212">Внутренний интерфейс пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="7c9a9-212">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="7c9a9-213">Предпочтительный путь для передачи аудио-и видеоданных между внутренними и внешними пользователями, устройством для обеспечения связи в филиалах или сервером обеспечения связи в филиалах</span><span class="sxs-lookup"><span data-stu-id="7c9a9-213">Preferred path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7c9a9-214">STUN/MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="7c9a9-214">STUN/MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="7c9a9-215">Любые</span><span class="sxs-lookup"><span data-stu-id="7c9a9-215">Any</span></span></p></td>
<td><p><span data-ttu-id="7c9a9-216">Внутренний интерфейс пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="7c9a9-216">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="7c9a9-217">Резервный путь для передачи аудио-и видеоданных между внутренними и внешними пользователями, устройства для обеспечения связи в филиалах или сервера для обеспечения связи в филиалах если не удается установить UDP-связь, используется TCP для передачи файлов и общего доступа к рабочему столу</span><span class="sxs-lookup"><span data-stu-id="7c9a9-217">Fallback path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server if UDP communication cannot be established, TCP is used for file transfer and desktop sharing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7c9a9-218">HTTPS/TCP/4443</span><span class="sxs-lookup"><span data-stu-id="7c9a9-218">HTTPS/TCP/4443</span></span></p></td>
<td><p><span data-ttu-id="7c9a9-219">Любой (может быть определен как IP-адрес сервера переднего плана или пул, в котором хранится центральное хранилище управления)</span><span class="sxs-lookup"><span data-stu-id="7c9a9-219">Any (can be defined as the Front End Server IP address, or pool that holds the Central Management store)</span></span></p></td>
<td><p><span data-ttu-id="7c9a9-220">Внутренний интерфейс пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="7c9a9-220">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="7c9a9-221">Репликация изменений из центрального хранилища управления на пограничный сервер</span><span class="sxs-lookup"><span data-stu-id="7c9a9-221">Replication of changes from the Central Management store to the Edge Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7c9a9-222">MTLS/TCP/50001</span><span class="sxs-lookup"><span data-stu-id="7c9a9-222">MTLS/TCP/50001</span></span></p></td>
<td><p><span data-ttu-id="7c9a9-223">Любые</span><span class="sxs-lookup"><span data-stu-id="7c9a9-223">Any</span></span></p></td>
<td><p><span data-ttu-id="7c9a9-224">Внутренний интерфейс пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="7c9a9-224">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="7c9a9-225">Централизованное ведение журналов с помощью команд Командная консоль Lync Server и командлетов службы централизованного ведения журналов, Командная строка ClsController (ClsController. exe) или агента (ClsAgent. exe) и коллекция журналов</span><span class="sxs-lookup"><span data-stu-id="7c9a9-225">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7c9a9-226">MTLS/TCP/50002</span><span class="sxs-lookup"><span data-stu-id="7c9a9-226">MTLS/TCP/50002</span></span></p></td>
<td><p><span data-ttu-id="7c9a9-227">Любые</span><span class="sxs-lookup"><span data-stu-id="7c9a9-227">Any</span></span></p></td>
<td><p><span data-ttu-id="7c9a9-228">Внутренний интерфейс пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="7c9a9-228">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="7c9a9-229">Централизованное ведение журналов с помощью команд Командная консоль Lync Server и командлетов службы централизованного ведения журналов, Командная строка ClsController (ClsController. exe) или агента (ClsAgent. exe) и коллекция журналов</span><span class="sxs-lookup"><span data-stu-id="7c9a9-229">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7c9a9-230">MTLS/TCP/50003</span><span class="sxs-lookup"><span data-stu-id="7c9a9-230">MTLS/TCP/50003</span></span></p></td>
<td><p><span data-ttu-id="7c9a9-231">Любые</span><span class="sxs-lookup"><span data-stu-id="7c9a9-231">Any</span></span></p></td>
<td><p><span data-ttu-id="7c9a9-232">Внутренний интерфейс пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="7c9a9-232">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="7c9a9-233">Централизованное ведение журналов с помощью команд Командная консоль Lync Server и командлетов службы централизованного ведения журналов, Командная строка ClsController (ClsController. exe) или агента (ClsAgent. exe) и коллекция журналов</span><span class="sxs-lookup"><span data-stu-id="7c9a9-233">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-federation"></a><span data-ttu-id="7c9a9-234">Сводка по брандмауэру для федерации</span><span class="sxs-lookup"><span data-stu-id="7c9a9-234">Firewall Summary for Federation</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7c9a9-235">Роль/протокол/TCP или UDP/порт</span><span class="sxs-lookup"><span data-stu-id="7c9a9-235">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="7c9a9-236">Исходный IP-адрес</span><span class="sxs-lookup"><span data-stu-id="7c9a9-236">Source IP address</span></span></th>
<th><span data-ttu-id="7c9a9-237">Конечный IP-адрес</span><span class="sxs-lookup"><span data-stu-id="7c9a9-237">Destination IP address</span></span></th>
<th><span data-ttu-id="7c9a9-238">Notes</span><span class="sxs-lookup"><span data-stu-id="7c9a9-238">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7c9a9-239">Доступ/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="7c9a9-239">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="7c9a9-240">Общедоступный IP-адрес пограничной службы доступа</span><span class="sxs-lookup"><span data-stu-id="7c9a9-240">Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="7c9a9-241">Любые</span><span class="sxs-lookup"><span data-stu-id="7c9a9-241">Any</span></span></p></td>
<td><p><span data-ttu-id="7c9a9-242">Для федеративного подключения и подключения к общедоступным службам обмена мгновенными сообщениями с помощью SIP</span><span class="sxs-lookup"><span data-stu-id="7c9a9-242">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary--public-instant-messaging-connectivity"></a><span data-ttu-id="7c9a9-243">Сводка по брандмауэру — связь с общедоступной службой обмена мгновенными сообщениями</span><span class="sxs-lookup"><span data-stu-id="7c9a9-243">Firewall Summary – Public Instant Messaging Connectivity</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7c9a9-244">Роль/протокол/TCP или UDP/порт</span><span class="sxs-lookup"><span data-stu-id="7c9a9-244">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="7c9a9-245">Исходный IP-адрес</span><span class="sxs-lookup"><span data-stu-id="7c9a9-245">Source IP address</span></span></th>
<th><span data-ttu-id="7c9a9-246">Конечный IP-адрес</span><span class="sxs-lookup"><span data-stu-id="7c9a9-246">Destination IP address</span></span></th>
<th><span data-ttu-id="7c9a9-247">Notes</span><span class="sxs-lookup"><span data-stu-id="7c9a9-247">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7c9a9-248">Доступ/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="7c9a9-248">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="7c9a9-249">Партнеры по связи с общедоступной службой обмена мгновенными сообщениями</span><span class="sxs-lookup"><span data-stu-id="7c9a9-249">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="7c9a9-250">Пограничный сервер доступа, пограничная служба доступа</span><span class="sxs-lookup"><span data-stu-id="7c9a9-250">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="7c9a9-251">Для федеративной и общедоступной службы обмена мгновенными сообщениями посредством SIP</span><span class="sxs-lookup"><span data-stu-id="7c9a9-251">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7c9a9-252">Доступ/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="7c9a9-252">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="7c9a9-253">Пограничный сервер доступа, пограничная служба доступа</span><span class="sxs-lookup"><span data-stu-id="7c9a9-253">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="7c9a9-254">Партнеры по связи с общедоступной службой обмена мгновенными сообщениями</span><span class="sxs-lookup"><span data-stu-id="7c9a9-254">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="7c9a9-255">Для связи с федеративными и общедоступными системами обмена сообщениями через SIP</span><span class="sxs-lookup"><span data-stu-id="7c9a9-255">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7c9a9-256">/TCP/443 доступа и SIP (TLS)</span><span class="sxs-lookup"><span data-stu-id="7c9a9-256">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="7c9a9-257">Клиенты</span><span class="sxs-lookup"><span data-stu-id="7c9a9-257">Clients</span></span></p></td>
<td><p><span data-ttu-id="7c9a9-258">Пограничный сервер доступа, пограничная служба доступа</span><span class="sxs-lookup"><span data-stu-id="7c9a9-258">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="7c9a9-259">Трафик SIP от клиента к серверу для доступа внешних пользователей</span><span class="sxs-lookup"><span data-stu-id="7c9a9-259">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7c9a9-260">АУДИО-И ВИДЕОДАННЫЕ/RTP/TCP/50000-– 999</span><span class="sxs-lookup"><span data-stu-id="7c9a9-260">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="7c9a9-261">Пограничный сервер, пограничная служба аудио- и видеоданных</span><span class="sxs-lookup"><span data-stu-id="7c9a9-261">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="7c9a9-262">Клиенты Live Messenger</span><span class="sxs-lookup"><span data-stu-id="7c9a9-262">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="7c9a9-263">Используется для сеансов аудио- и видеоконференций с использованием Windows Live Messenger, если настроена связь с общедоступной службой обмена мгновенными сообщениями.</span><span class="sxs-lookup"><span data-stu-id="7c9a9-263">Used for A/V sessions with Windows Live Messenger if public IM connectivity is configured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7c9a9-264">АУДИО-И ВИДЕОДАННЫЕ/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="7c9a9-264">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="7c9a9-265">Пограничный сервер, пограничная служба аудио- и видеоданных</span><span class="sxs-lookup"><span data-stu-id="7c9a9-265">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="7c9a9-266">Клиенты Live Messenger</span><span class="sxs-lookup"><span data-stu-id="7c9a9-266">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="7c9a9-267">Требуется для связи с общедоступной службой обмена мгновенными сообщениями с помощью Windows Live Messenger</span><span class="sxs-lookup"><span data-stu-id="7c9a9-267">Required for public IM connectivity with Windows Live Messenger</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7c9a9-268">АУДИО-И ВИДЕОДАННЫЕ/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="7c9a9-268">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="7c9a9-269">Клиенты Live Messenger</span><span class="sxs-lookup"><span data-stu-id="7c9a9-269">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="7c9a9-270">Пограничный сервер, пограничная служба аудио- и видеоданных</span><span class="sxs-lookup"><span data-stu-id="7c9a9-270">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="7c9a9-271">Требуется для связи с общедоступной службой обмена мгновенными сообщениями с помощью Windows Live Messenger</span><span class="sxs-lookup"><span data-stu-id="7c9a9-271">Required for public IM connectivity with Windows Live Messenger</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-extensible-messaging-and-presence-protocol"></a><span data-ttu-id="7c9a9-272">Сводка по брандмауэру для протокола XMPP</span><span class="sxs-lookup"><span data-stu-id="7c9a9-272">Firewall Summary for Extensible Messaging and Presence Protocol</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7c9a9-273">Протокол/TCP или UDP/порт</span><span class="sxs-lookup"><span data-stu-id="7c9a9-273">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="7c9a9-274">Источник (IP-адрес)</span><span class="sxs-lookup"><span data-stu-id="7c9a9-274">Source (IP address)</span></span></th>
<th><span data-ttu-id="7c9a9-275">Назначение (IP-адрес)</span><span class="sxs-lookup"><span data-stu-id="7c9a9-275">Destination (IP address)</span></span></th>
<th><span data-ttu-id="7c9a9-276">Комментарии</span><span class="sxs-lookup"><span data-stu-id="7c9a9-276">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7c9a9-277">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="7c9a9-277">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="7c9a9-278">Любые</span><span class="sxs-lookup"><span data-stu-id="7c9a9-278">Any</span></span></p></td>
<td><p><span data-ttu-id="7c9a9-279">IP-адрес интерфейса пограничного сервера доступа пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="7c9a9-279">Edge Server Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="7c9a9-280">Стандартный порт для связи "сервер-сервер" через XMPP.</span><span class="sxs-lookup"><span data-stu-id="7c9a9-280">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="7c9a9-281">Разрешает связь с прокси-сервером пограничного сервера XMPP от федеративных партнеров XMPP</span><span class="sxs-lookup"><span data-stu-id="7c9a9-281">Allows communication to the Edge Server XMPP proxy from federated XMPP partners</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7c9a9-282">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="7c9a9-282">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="7c9a9-283">IP-адрес интерфейса пограничного сервера доступа пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="7c9a9-283">Edge Server Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="7c9a9-284">Любые</span><span class="sxs-lookup"><span data-stu-id="7c9a9-284">Any</span></span></p></td>
<td><p><span data-ttu-id="7c9a9-285">Стандартный порт для связи "сервер-сервер" через XMPP.</span><span class="sxs-lookup"><span data-stu-id="7c9a9-285">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="7c9a9-286">Разрешает обмен данными от прокси-сервера пограничного сервера XMPP к федеративным партнерам XMPP</span><span class="sxs-lookup"><span data-stu-id="7c9a9-286">Allows communication from the Edge Server XMPP proxy to federated XMPP partners</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7c9a9-287">XMPP/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="7c9a9-287">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="7c9a9-288">Любые</span><span class="sxs-lookup"><span data-stu-id="7c9a9-288">Any</span></span></p></td>
<td><p><span data-ttu-id="7c9a9-289">Каждый внутренний интерфейсный IP-адрес пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="7c9a9-289">Each internal Edge Server Interface IP</span></span></p></td>
<td><p><span data-ttu-id="7c9a9-290">Внутренний IP-адрес пограничного сервера или пула переднего плана на внутренний IP-адрес пограничного сервера или на каждый внутренний IP-адрес пограничного пула — внутренний IP-адрес XMPP, входящий в шлюз XMPP.</span><span class="sxs-lookup"><span data-stu-id="7c9a9-290">Internal XMPP traffic from the XMPP Gateway on the Front End Server or Front End pool to the Edge Server internal IP address or each Edge pool member’s internal IP address</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

