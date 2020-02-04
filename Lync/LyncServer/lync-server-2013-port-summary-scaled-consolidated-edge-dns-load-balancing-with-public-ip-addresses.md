---
title: 'Lync Server 2013: сводка по портам — масштабируемая консолидированная пограничная топология, балансировка нагрузки на DNS с общедоступными IP-адресами'
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
ms.openlocfilehash: f67a12b05d8724d31f8ef83bfa4aa704b41cee13
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41747589"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="port-summary---scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses-in-lync-server-2013"></a><span data-ttu-id="2c0ef-102">Сводка по портам — масштабируемая консолидированная пограничная топология, балансировка нагрузки на DNS с общедоступными IP-адресами в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2c0ef-102">Port summary - Scaled consolidated edge, DNS load balancing with public IP addresses in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2c0ef-103">_**Тема последнего изменения:** 2013-04-03_</span><span class="sxs-lookup"><span data-stu-id="2c0ef-103">_**Topic Last Modified:** 2013-04-03_</span></span>

<span data-ttu-id="2c0ef-104">Функция пограничного сервера Lync Server 2013, описанная в этой архитектуре сценариев, очень похожа на ту, что была реализована в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="2c0ef-104">The Lync Server 2013, Edge Server functionality described in this scenario architecture is very similar to what was implemented in Lync Server 2010.</span></span> <span data-ttu-id="2c0ef-105">Наиболее заметным дополнением является порт **5269 на TCP** для протокола расширенной обработки сообщений и присутствия (КСМПП).</span><span class="sxs-lookup"><span data-stu-id="2c0ef-105">The most noticeable addition is the port **5269 over TCP** entry for the extensible messaging and presence protocol (XMPP).</span></span> <span data-ttu-id="2c0ef-106">Lync Server 2013 (при необходимости) можно развернуть прокси-сервер КСМПП на пограничном или пограничном пуле, а также на сервере шлюзов КСМПП на сервере переднего плана или в пуле внешних интерфейсов.</span><span class="sxs-lookup"><span data-stu-id="2c0ef-106">Lync Server 2013 optionally deploys an XMPP proxy on the Edge Server or Edge pool and the XMPP gateway server on the Front End Server or Front End pool.</span></span>

<span data-ttu-id="2c0ef-107">В дополнение к протоколу IPv4, пограничный сервер теперь поддерживает IPv6.</span><span class="sxs-lookup"><span data-stu-id="2c0ef-107">In addition to IPv4, the Edge Server now supports IPv6.</span></span> <span data-ttu-id="2c0ef-108">Для ясности в сценариях используется только протокол IPv4.</span><span class="sxs-lookup"><span data-stu-id="2c0ef-108">For clarity, only IPv4 is used in the scenarios.</span></span>

<span data-ttu-id="2c0ef-109">**Корпоративная сеть периметра для масштабируемых консолидированных кромок, балансировка нагрузки DNS с общедоступными IP-адресами**</span><span class="sxs-lookup"><span data-stu-id="2c0ef-109">**Enterprise perimeter network for Scaled Consolidated Edge, DNS Load Balancing with Public IP Addresses**</span></span>

<span data-ttu-id="2c0ef-110">![96f5a8f5-16d2-464d-b86e-7c7ecfc89ead](images/JJ205394.96f5a8f5-16d2-464d-b86e-7c7ecfc89ead(OCS.15).jpg "96f5a8f5-16d2-464d-b86e-7c7ecfc89ead")</span><span class="sxs-lookup"><span data-stu-id="2c0ef-110">![96f5a8f5-16d2-464d-b86e-7c7ecfc89ead](images/JJ205394.96f5a8f5-16d2-464d-b86e-7c7ecfc89ead(OCS.15).jpg "96f5a8f5-16d2-464d-b86e-7c7ecfc89ead")</span></span>

<div>

## <a name="port-and-protocol-details"></a><span data-ttu-id="2c0ef-111">Сведения о портах и протоколах</span><span class="sxs-lookup"><span data-stu-id="2c0ef-111">Port and Protocol Details</span></span>

<span data-ttu-id="2c0ef-112">Рекомендуется открывать только порты, необходимые для поддержки функций, для которых предоставляется внешний доступ.</span><span class="sxs-lookup"><span data-stu-id="2c0ef-112">It is recommended that you open only the ports required to support the functionality for which you are providing external access.</span></span>

<span data-ttu-id="2c0ef-113">Для удаленного доступа к работе в любой службе пограничного сервера необходимо, чтобы трафик SIP был в направлении на один и тот же трафик по внешнему потоку, как показано на рисунке входящего и исходящего трафика пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="2c0ef-113">For remote access to work for any edge service, it is mandatory that SIP traffic is allowed to flow bi-directionally as shown in the Inbound/Outbound edge traffic figure.</span></span> <span data-ttu-id="2c0ef-114">Другими словами, Обмен сообщениями SIP и из службы Edge для Access осуществляется в обмене мгновенными сообщениями, присутствии, веб-конференциях, аудио-и видеосвязи (A/V) и Федерации.</span><span class="sxs-lookup"><span data-stu-id="2c0ef-114">Stated another way, the SIP messaging to and from the Access Edge service is involved in instant messaging (IM), presence, web conferencing, audio/video (A/V) and federation.</span></span>

### <a name="firewall-summary-for-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses-external-interface--node-1-and-node-2-example"></a><span data-ttu-id="2c0ef-115">Сводка по межсетевому экрану для масштабируемой консолидированной границы, балансировка нагрузки DNS с общедоступными IP-адресами: внешний интерфейс — узел 1 и узел 2 (пример)</span><span class="sxs-lookup"><span data-stu-id="2c0ef-115">Firewall Summary for Scaled Consolidated Edge, DNS Load Balancing with Public IP Addresses: External Interface – Node 1 and Node 2 (Example)</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2c0ef-116">Role/Protocol/TCP/UDP/порт</span><span class="sxs-lookup"><span data-stu-id="2c0ef-116">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="2c0ef-117">IP-адрес источника</span><span class="sxs-lookup"><span data-stu-id="2c0ef-117">Source IP address</span></span></th>
<th><span data-ttu-id="2c0ef-118">IP-адрес назначения</span><span class="sxs-lookup"><span data-stu-id="2c0ef-118">Destination IP address</span></span></th>
<th><span data-ttu-id="2c0ef-119">Примечания.</span><span class="sxs-lookup"><span data-stu-id="2c0ef-119">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2c0ef-120">КСМПП/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="2c0ef-120">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="2c0ef-121">Любой</span><span class="sxs-lookup"><span data-stu-id="2c0ef-121">Any</span></span></p></td>
<td><p><span data-ttu-id="2c0ef-122">Прокси-служба КСМПП (доступ к IP-адресу для общих ресурсов с помощью службы Edge Access)</span><span class="sxs-lookup"><span data-stu-id="2c0ef-122">XMPP Proxy service (shares IP address with Access Edge service)</span></span></p></td>
<td><p><span data-ttu-id="2c0ef-123">Прокси-служба КСМПП принимает трафик от КСМПП контактов в определенных КСМПП федерациях.</span><span class="sxs-lookup"><span data-stu-id="2c0ef-123">XMPP Proxy service accepts traffic from XMPP contacts in defined XMPP federations</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2c0ef-124">Access/HTTP/TCP/80</span><span class="sxs-lookup"><span data-stu-id="2c0ef-124">Access/HTTP/TCP/80</span></span></p></td>
<td><p><span data-ttu-id="2c0ef-125">Пограничный сервер, общедоступный IP-адрес пограничной службы доступа</span><span class="sxs-lookup"><span data-stu-id="2c0ef-125">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="2c0ef-126">Любой</span><span class="sxs-lookup"><span data-stu-id="2c0ef-126">Any</span></span></p></td>
<td><p><span data-ttu-id="2c0ef-127">Проверка отзыва сертификатов и получения CRL</span><span class="sxs-lookup"><span data-stu-id="2c0ef-127">Certificate revocation/CRL check and retrieval</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2c0ef-128">Access/DNS/TCP/53</span><span class="sxs-lookup"><span data-stu-id="2c0ef-128">Access/DNS/TCP/53</span></span></p></td>
<td><p><span data-ttu-id="2c0ef-129">Пограничный сервер, общедоступный IP-адрес пограничной службы доступа</span><span class="sxs-lookup"><span data-stu-id="2c0ef-129">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="2c0ef-130">Любой</span><span class="sxs-lookup"><span data-stu-id="2c0ef-130">Any</span></span></p></td>
<td><p><span data-ttu-id="2c0ef-131">Запрос DNS по протоколу TCP</span><span class="sxs-lookup"><span data-stu-id="2c0ef-131">DNS query over TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2c0ef-132">Access/DNS/UDP/53</span><span class="sxs-lookup"><span data-stu-id="2c0ef-132">Access/DNS/UDP/53</span></span></p></td>
<td><p><span data-ttu-id="2c0ef-133">Пограничный сервер, общедоступный IP-адрес пограничной службы доступа</span><span class="sxs-lookup"><span data-stu-id="2c0ef-133">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="2c0ef-134">Любой</span><span class="sxs-lookup"><span data-stu-id="2c0ef-134">Any</span></span></p></td>
<td><p><span data-ttu-id="2c0ef-135">Запрос DNS по протоколу UDP</span><span class="sxs-lookup"><span data-stu-id="2c0ef-135">DNS query over UDP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2c0ef-136">Access/SIP (TLS)/TCP/443</span><span class="sxs-lookup"><span data-stu-id="2c0ef-136">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="2c0ef-137">Любой</span><span class="sxs-lookup"><span data-stu-id="2c0ef-137">Any</span></span></p></td>
<td><p><span data-ttu-id="2c0ef-138">Пограничный сервер, общедоступный IP-адрес пограничной службы доступа</span><span class="sxs-lookup"><span data-stu-id="2c0ef-138">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="2c0ef-139">Трафик SIP "клиент-сервер" для доступа внешних пользователей</span><span class="sxs-lookup"><span data-stu-id="2c0ef-139">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2c0ef-140">Access/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="2c0ef-140">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="2c0ef-141">Любой</span><span class="sxs-lookup"><span data-stu-id="2c0ef-141">Any</span></span></p></td>
<td><p><span data-ttu-id="2c0ef-142">Пограничный сервер, общедоступный IP-адрес пограничной службы доступа</span><span class="sxs-lookup"><span data-stu-id="2c0ef-142">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="2c0ef-143">Для Федеративной и общедоступной службы обмена мгновенными сообщениями с помощью SIP</span><span class="sxs-lookup"><span data-stu-id="2c0ef-143">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2c0ef-144">Access/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="2c0ef-144">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="2c0ef-145">Пограничный сервер, общедоступный IP-адрес пограничной службы доступа</span><span class="sxs-lookup"><span data-stu-id="2c0ef-145">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="2c0ef-146">Любой</span><span class="sxs-lookup"><span data-stu-id="2c0ef-146">Any</span></span></p></td>
<td><p><span data-ttu-id="2c0ef-147">Для Федеративной и общедоступной службы обмена мгновенными сообщениями с помощью SIP</span><span class="sxs-lookup"><span data-stu-id="2c0ef-147">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2c0ef-148">Веб-конференции/PSOM (TLS) TCP/443</span><span class="sxs-lookup"><span data-stu-id="2c0ef-148">Web Conferencing/PSOM(TLS)TCP/443</span></span></p></td>
<td><p><span data-ttu-id="2c0ef-149">Любой</span><span class="sxs-lookup"><span data-stu-id="2c0ef-149">Any</span></span></p></td>
<td><p><span data-ttu-id="2c0ef-150">Общедоступный IP-адрес службы пограничного сервера для веб-конференций Edge</span><span class="sxs-lookup"><span data-stu-id="2c0ef-150">Edge Server Web Conferencing Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="2c0ef-151">Мультимедиа для веб-конференций</span><span class="sxs-lookup"><span data-stu-id="2c0ef-151">Web Conferencing media</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2c0ef-152">A/V/RTP/TCP/50000-59,999</span><span class="sxs-lookup"><span data-stu-id="2c0ef-152">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="2c0ef-153">Пограничный сервер, общедоступный IP-адрес пограничной службы аудио- и видеоданных</span><span class="sxs-lookup"><span data-stu-id="2c0ef-153">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="2c0ef-154">Любой</span><span class="sxs-lookup"><span data-stu-id="2c0ef-154">Any</span></span></p></td>
<td><p><span data-ttu-id="2c0ef-155">Требуется для Федерации с партнерами, работающими под управлением Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 и Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2c0ef-155">Required for federating with partners running Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 and Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2c0ef-156">A/V/RTP/UDP/50000-59,999</span><span class="sxs-lookup"><span data-stu-id="2c0ef-156">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="2c0ef-157">Пограничный сервер, общедоступный IP-адрес пограничной службы аудио- и видеоданных</span><span class="sxs-lookup"><span data-stu-id="2c0ef-157">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="2c0ef-158">Любой</span><span class="sxs-lookup"><span data-stu-id="2c0ef-158">Any</span></span></p></td>
<td><p><span data-ttu-id="2c0ef-159">Требуется только для Федерации с партнерами, работающими под управлением Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="2c0ef-159">Required only for federation with partners running Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2c0ef-160">A/V/RTP/TCP/50000-59,999</span><span class="sxs-lookup"><span data-stu-id="2c0ef-160">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="2c0ef-161">Любой</span><span class="sxs-lookup"><span data-stu-id="2c0ef-161">Any</span></span></p></td>
<td><p><span data-ttu-id="2c0ef-162">Пограничный сервер, общедоступный IP-адрес пограничной службы аудио- и видеоданных</span><span class="sxs-lookup"><span data-stu-id="2c0ef-162">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="2c0ef-163">Требуется только для Федерации с партнерами, работающими под управлением Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="2c0ef-163">Required only for federation with partners running Office Communications Server 2007</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2c0ef-164">A/V/RTP/UDP/50000-59,999</span><span class="sxs-lookup"><span data-stu-id="2c0ef-164">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="2c0ef-165">Любой</span><span class="sxs-lookup"><span data-stu-id="2c0ef-165">Any</span></span></p></td>
<td><p><span data-ttu-id="2c0ef-166">Пограничный сервер, общедоступный IP-адрес пограничной службы аудио- и видеоданных</span><span class="sxs-lookup"><span data-stu-id="2c0ef-166">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="2c0ef-167">Требуется только для Федерации с партнерами, работающими под управлением Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="2c0ef-167">Required only for federation with partners running Office Communications Server 2007</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2c0ef-168">A/V/STUN, МСТУРН/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="2c0ef-168">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="2c0ef-169">Пограничный сервер, общедоступный IP-адрес пограничной службы аудио- и видеоданных</span><span class="sxs-lookup"><span data-stu-id="2c0ef-169">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="2c0ef-170">Любой</span><span class="sxs-lookup"><span data-stu-id="2c0ef-170">Any</span></span></p></td>
<td><p><span data-ttu-id="2c0ef-171">3478 Outbound используется для определения версии пограничного сервера, с которым обменивается данными Lync Server, а также для мультимедийного трафика от пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="2c0ef-171">3478 outbound is used to determine the version of Edge Server that Lync Server is communicating with and also for media traffic from Edge Server-to-Edge Server.</span></span> <span data-ttu-id="2c0ef-172">Требуется для Федерации с Lync Server 2010, Windows Live Messenger и Office Communications Server 2007 R2, а также в том случае, если в компании развернуты несколько пулов Edge.</span><span class="sxs-lookup"><span data-stu-id="2c0ef-172">Required for federation with Lync Server 2010, Windows Live Messenger, and Office Communications Server 2007 R2, and also if multiple Edge pools are deployed within a company.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2c0ef-173">A/V/STUN, МСТУРН/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="2c0ef-173">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="2c0ef-174">Любой</span><span class="sxs-lookup"><span data-stu-id="2c0ef-174">Any</span></span></p></td>
<td><p><span data-ttu-id="2c0ef-175">Пограничный сервер, общедоступный IP-адрес пограничной службы аудио- и видеоданных</span><span class="sxs-lookup"><span data-stu-id="2c0ef-175">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="2c0ef-176">STUN/отключите согласование кандидатов по протоколу UDP/3478</span><span class="sxs-lookup"><span data-stu-id="2c0ef-176">STUN/TURN negotiation of candidates over UDP/3478</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2c0ef-177">A/V/STUN, МСТУРН/TCP/443</span><span class="sxs-lookup"><span data-stu-id="2c0ef-177">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="2c0ef-178">Любой</span><span class="sxs-lookup"><span data-stu-id="2c0ef-178">Any</span></span></p></td>
<td><p><span data-ttu-id="2c0ef-179">Пограничный сервер, общедоступный IP-адрес пограничной службы аудио- и видеоданных</span><span class="sxs-lookup"><span data-stu-id="2c0ef-179">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="2c0ef-180">STUN/отключите согласование кандидатов по протоколу TCP/443</span><span class="sxs-lookup"><span data-stu-id="2c0ef-180">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2c0ef-181">A/V/STUN, МСТУРН/TCP/443</span><span class="sxs-lookup"><span data-stu-id="2c0ef-181">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="2c0ef-182">Служба Edge для пограничного сервера A/V</span><span class="sxs-lookup"><span data-stu-id="2c0ef-182">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="2c0ef-183">Любой</span><span class="sxs-lookup"><span data-stu-id="2c0ef-183">Any</span></span></p></td>
<td><p><span data-ttu-id="2c0ef-184">STUN/отключите согласование кандидатов по протоколу TCP/443</span><span class="sxs-lookup"><span data-stu-id="2c0ef-184">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="firewall-summary-for-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses-internal-interface--node-1-and-node-2-example"></a><span data-ttu-id="2c0ef-185">Сводка по межсетевому экрану для масштабируемой консолидированной границы, балансировка нагрузки DNS с общедоступными IP-адресами: внутренний интерфейс — узел 1 и узел 2 (пример)</span><span class="sxs-lookup"><span data-stu-id="2c0ef-185">Firewall Summary for Scaled Consolidated Edge, DNS Load Balancing with Public IP Addresses: Internal Interface – Node 1 and Node 2 (Example)</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2c0ef-186">Протокол/TCP или UDP/порт</span><span class="sxs-lookup"><span data-stu-id="2c0ef-186">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="2c0ef-187">IP-адрес источника</span><span class="sxs-lookup"><span data-stu-id="2c0ef-187">Source IP address</span></span></th>
<th><span data-ttu-id="2c0ef-188">IP-адрес назначения</span><span class="sxs-lookup"><span data-stu-id="2c0ef-188">Destination IP address</span></span></th>
<th><span data-ttu-id="2c0ef-189">Комментарии</span><span class="sxs-lookup"><span data-stu-id="2c0ef-189">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2c0ef-190">КСМПП/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="2c0ef-190">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="2c0ef-191">Any (может быть определено как адрес сервера переднего плана или IP-адрес пула переднего плана, на котором запущена служба шлюза КСМПП)</span><span class="sxs-lookup"><span data-stu-id="2c0ef-191">Any (can be defined as Front End Server address, or Front End pool IP address running the XMPP Gateway service)</span></span></p></td>
<td><p><span data-ttu-id="2c0ef-192">Внутренний интерфейс пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="2c0ef-192">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="2c0ef-193">Исходящий трафик КСМПП от службы шлюза КСМПП, работающей на сервере переднего плана или в пуле внешних интерфейсов</span><span class="sxs-lookup"><span data-stu-id="2c0ef-193">Outbound XMPP traffic from XMPP Gateway service running on Front End Server or Front End pool</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2c0ef-194">SIP/MTLS/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="2c0ef-194">SIP/MTLS/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="2c0ef-195">Any (может быть определено как режиссер, IP-адрес пула режиссера, сервер клиентского доступа или IP-адрес пула переднего плана)</span><span class="sxs-lookup"><span data-stu-id="2c0ef-195">Any (can be defined as Director, Director pool IP address, Front End Server or Front End pool IP address)</span></span></p></td>
<td><p><span data-ttu-id="2c0ef-196">Внутренний интерфейс пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="2c0ef-196">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="2c0ef-197">Исходящий трафик SIP (от режиссера, IP-адреса пула, сервера переднего плана или IP-адреса пула переднего плана) к внутреннему интерфейсу пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="2c0ef-197">Outbound SIP traffic (from Director, Director pool IP address, Front End Server or Front End pool IP address) to Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2c0ef-198">SIP/MTLS/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="2c0ef-198">SIP/MTLS/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="2c0ef-199">Внутренний интерфейс пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="2c0ef-199">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="2c0ef-200">Any (может быть определено как режиссер, IP-адрес пула режиссера, сервер клиентского доступа или IP-адрес пула переднего плана)</span><span class="sxs-lookup"><span data-stu-id="2c0ef-200">Any (can be defined as Director, Director pool IP address, Front End Server or Front End pool IP address)</span></span></p></td>
<td><p><span data-ttu-id="2c0ef-201">Входящий трафик SIP (для режиссера, IP-адреса пула, сервера переднего плана или IP-адреса пула переднего плана) от внутреннего интерфейса пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="2c0ef-201">Inbound SIP traffic (to Director, Director pool IP address, Front End Server or Front End pool IP address) from Edge Server internal interface</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2c0ef-202">PSOM/MTLS/TCP/8057</span><span class="sxs-lookup"><span data-stu-id="2c0ef-202">PSOM/MTLS/TCP/8057</span></span></p></td>
<td><p><span data-ttu-id="2c0ef-203">Any (может быть IP-адресом сервера переднего плана или IP-адресом серверного переднего плана в пуле переднего плана)</span><span class="sxs-lookup"><span data-stu-id="2c0ef-203">Any (can be defined as Front End Server IP address, or each Front End Server IP address in a Front End pool)</span></span></p></td>
<td><p><span data-ttu-id="2c0ef-204">Внутренний интерфейс пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="2c0ef-204">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="2c0ef-205">Трафик веб-конференций от сервера переднего плана или каждого серверного переднего плана, если он находится в пуле и является внутренним интерфейсом пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="2c0ef-205">Web conferencing traffic from Front End Server or each Front End Server if in a pool, to Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2c0ef-206">SIP/MTLS/TCP/5062</span><span class="sxs-lookup"><span data-stu-id="2c0ef-206">SIP/MTLS/TCP/5062</span></span></p></td>
<td><p><span data-ttu-id="2c0ef-207">Any (может быть как IP-адресом переднего сервера, так и IP-адресом пула переднего плана либо любым бесперебойно работающее устройство филиала или с помощью этого пограничного сервера).</span><span class="sxs-lookup"><span data-stu-id="2c0ef-207">Any (can be defined as Front End Server IP address, or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server)</span></span></p></td>
<td><p><span data-ttu-id="2c0ef-208">Внутренний интерфейс пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="2c0ef-208">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="2c0ef-209">Проверка подлинности пользователей/V (служба проверки подлинности A/V) от IP-адреса сервера переднего плана или переднего плана, а также от любого работающего филиала или сервера с бесперебойной подразделением с помощью этого пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="2c0ef-209">Authentication of A/V users (A/V authentication service) from Front End Server or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2c0ef-210">STUN/МСТУРН/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="2c0ef-210">STUN/MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="2c0ef-211">Любой</span><span class="sxs-lookup"><span data-stu-id="2c0ef-211">Any</span></span></p></td>
<td><p><span data-ttu-id="2c0ef-212">Внутренний интерфейс пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="2c0ef-212">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="2c0ef-213">Предпочтительный путь для передачи мультимедиа между внутренними и внешними пользователями, бесперебойно работающем устройстве филиалов или бесперебойно работающем сервере филиала</span><span class="sxs-lookup"><span data-stu-id="2c0ef-213">Preferred path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2c0ef-214">STUN/МСТУРН/TCP/443</span><span class="sxs-lookup"><span data-stu-id="2c0ef-214">STUN/MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="2c0ef-215">Любой</span><span class="sxs-lookup"><span data-stu-id="2c0ef-215">Any</span></span></p></td>
<td><p><span data-ttu-id="2c0ef-216">Внутренний интерфейс пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="2c0ef-216">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="2c0ef-217">Резервный путь для передачи мультимедиа между внутренними и внешними пользователями, бесперебойно работающее устройство филиала или бесперебойный сервер филиала, если не удается установить UDP-связь, используется протокол TCP для обмена файлами и демонстрации рабочего стола</span><span class="sxs-lookup"><span data-stu-id="2c0ef-217">Fallback path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server if UDP communication cannot be established, TCP is used for file transfer and desktop sharing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2c0ef-218">HTTPS/TCP/4443</span><span class="sxs-lookup"><span data-stu-id="2c0ef-218">HTTPS/TCP/4443</span></span></p></td>
<td><p><span data-ttu-id="2c0ef-219">Any (может быть указан в качестве IP-адреса сервера переднего плана или пула, содержащего центральное хранилище управления).</span><span class="sxs-lookup"><span data-stu-id="2c0ef-219">Any (can be defined as the Front End Server IP address, or pool that holds the Central Management store)</span></span></p></td>
<td><p><span data-ttu-id="2c0ef-220">Внутренний интерфейс пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="2c0ef-220">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="2c0ef-221">Репликация изменений из хранилища центрального управления на пограничный сервер</span><span class="sxs-lookup"><span data-stu-id="2c0ef-221">Replication of changes from the Central Management store to the Edge Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2c0ef-222">MTLS/TCP/50001</span><span class="sxs-lookup"><span data-stu-id="2c0ef-222">MTLS/TCP/50001</span></span></p></td>
<td><p><span data-ttu-id="2c0ef-223">Любой</span><span class="sxs-lookup"><span data-stu-id="2c0ef-223">Any</span></span></p></td>
<td><p><span data-ttu-id="2c0ef-224">Внутренний интерфейс пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="2c0ef-224">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="2c0ef-225">Централизованное ведение журналов с помощью команд командной строки Lync Server Management Shell и централизованных служб ведения журнала, Клсконтроллер (Командная строка Клсконтроллер. exe) или агента (Клсажент. exe) и коллекции журналов</span><span class="sxs-lookup"><span data-stu-id="2c0ef-225">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2c0ef-226">MTLS/TCP/50002</span><span class="sxs-lookup"><span data-stu-id="2c0ef-226">MTLS/TCP/50002</span></span></p></td>
<td><p><span data-ttu-id="2c0ef-227">Любой</span><span class="sxs-lookup"><span data-stu-id="2c0ef-227">Any</span></span></p></td>
<td><p><span data-ttu-id="2c0ef-228">Внутренний интерфейс пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="2c0ef-228">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="2c0ef-229">Централизованное ведение журналов с помощью команд командной строки Lync Server Management Shell и централизованных служб ведения журнала, Клсконтроллер (Командная строка Клсконтроллер. exe) или агента (Клсажент. exe) и коллекции журналов</span><span class="sxs-lookup"><span data-stu-id="2c0ef-229">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2c0ef-230">MTLS/TCP/50003</span><span class="sxs-lookup"><span data-stu-id="2c0ef-230">MTLS/TCP/50003</span></span></p></td>
<td><p><span data-ttu-id="2c0ef-231">Любой</span><span class="sxs-lookup"><span data-stu-id="2c0ef-231">Any</span></span></p></td>
<td><p><span data-ttu-id="2c0ef-232">Внутренний интерфейс пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="2c0ef-232">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="2c0ef-233">Централизованное ведение журналов с помощью команд командной строки Lync Server Management Shell и централизованных служб ведения журнала, Клсконтроллер (Командная строка Клсконтроллер. exe) или агента (Клсажент. exe) и коллекции журналов</span><span class="sxs-lookup"><span data-stu-id="2c0ef-233">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-federation"></a><span data-ttu-id="2c0ef-234">Сводка по межсетевому экрану для Федерации</span><span class="sxs-lookup"><span data-stu-id="2c0ef-234">Firewall Summary for Federation</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2c0ef-235">Role/Protocol/TCP/UDP/порт</span><span class="sxs-lookup"><span data-stu-id="2c0ef-235">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="2c0ef-236">IP-адрес источника</span><span class="sxs-lookup"><span data-stu-id="2c0ef-236">Source IP address</span></span></th>
<th><span data-ttu-id="2c0ef-237">IP-адрес назначения</span><span class="sxs-lookup"><span data-stu-id="2c0ef-237">Destination IP address</span></span></th>
<th><span data-ttu-id="2c0ef-238">Примечания.</span><span class="sxs-lookup"><span data-stu-id="2c0ef-238">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2c0ef-239">Access/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="2c0ef-239">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="2c0ef-240">Общедоступный IP-адрес службы пограничного доступа</span><span class="sxs-lookup"><span data-stu-id="2c0ef-240">Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="2c0ef-241">Любой</span><span class="sxs-lookup"><span data-stu-id="2c0ef-241">Any</span></span></p></td>
<td><p><span data-ttu-id="2c0ef-242">Для Федеративной и общедоступной службы обмена мгновенными сообщениями с помощью SIP</span><span class="sxs-lookup"><span data-stu-id="2c0ef-242">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary--public-instant-messaging-connectivity"></a><span data-ttu-id="2c0ef-243">Сводка по брандмауэрам: общедоступная служба обмена мгновенными сообщениями</span><span class="sxs-lookup"><span data-stu-id="2c0ef-243">Firewall Summary – Public Instant Messaging Connectivity</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2c0ef-244">Role/Protocol/TCP/UDP/порт</span><span class="sxs-lookup"><span data-stu-id="2c0ef-244">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="2c0ef-245">IP-адрес источника</span><span class="sxs-lookup"><span data-stu-id="2c0ef-245">Source IP address</span></span></th>
<th><span data-ttu-id="2c0ef-246">IP-адрес назначения</span><span class="sxs-lookup"><span data-stu-id="2c0ef-246">Destination IP address</span></span></th>
<th><span data-ttu-id="2c0ef-247">Примечания.</span><span class="sxs-lookup"><span data-stu-id="2c0ef-247">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2c0ef-248">Access/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="2c0ef-248">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="2c0ef-249">Партнеры по подключению общедоступных мгновенных сообщений</span><span class="sxs-lookup"><span data-stu-id="2c0ef-249">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="2c0ef-250">Служба пограничного доступа к пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="2c0ef-250">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="2c0ef-251">Для Федеративной и общедоступной службы обмена мгновенными сообщениями с помощью SIP</span><span class="sxs-lookup"><span data-stu-id="2c0ef-251">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2c0ef-252">Access/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="2c0ef-252">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="2c0ef-253">Служба пограничного доступа к пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="2c0ef-253">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="2c0ef-254">Партнеры по подключению общедоступных мгновенных сообщений</span><span class="sxs-lookup"><span data-stu-id="2c0ef-254">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="2c0ef-255">Для Федеративной и общедоступной службы обмена мгновенными сообщениями с помощью SIP</span><span class="sxs-lookup"><span data-stu-id="2c0ef-255">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2c0ef-256">Access/SIP (TLS)/TCP/443</span><span class="sxs-lookup"><span data-stu-id="2c0ef-256">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="2c0ef-257">Клиенты</span><span class="sxs-lookup"><span data-stu-id="2c0ef-257">Clients</span></span></p></td>
<td><p><span data-ttu-id="2c0ef-258">Служба пограничного доступа к пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="2c0ef-258">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="2c0ef-259">Трафик SIP "клиент-сервер" для доступа внешних пользователей</span><span class="sxs-lookup"><span data-stu-id="2c0ef-259">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2c0ef-260">A/V/RTP/TCP/50000-59,999</span><span class="sxs-lookup"><span data-stu-id="2c0ef-260">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="2c0ef-261">Служба Edge для пограничного сервера A/V</span><span class="sxs-lookup"><span data-stu-id="2c0ef-261">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="2c0ef-262">Клиенты Live Messenger</span><span class="sxs-lookup"><span data-stu-id="2c0ef-262">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="2c0ef-263">Используется для сеансов обмена мгновенными сообщениями с помощью Windows Live Messenger, если настроена служба общего доступа к данным.</span><span class="sxs-lookup"><span data-stu-id="2c0ef-263">Used for A/V sessions with Windows Live Messenger if public IM connectivity is configured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2c0ef-264">A/V/STUN, МСТУРН/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="2c0ef-264">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="2c0ef-265">Служба Edge для пограничного сервера A/V</span><span class="sxs-lookup"><span data-stu-id="2c0ef-265">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="2c0ef-266">Клиенты Live Messenger</span><span class="sxs-lookup"><span data-stu-id="2c0ef-266">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="2c0ef-267">Требуется для общедоступной службы обмена мгновенными сообщениями в Windows Live Messenger</span><span class="sxs-lookup"><span data-stu-id="2c0ef-267">Required for public IM connectivity with Windows Live Messenger</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2c0ef-268">A/V/STUN, МСТУРН/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="2c0ef-268">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="2c0ef-269">Клиенты Live Messenger</span><span class="sxs-lookup"><span data-stu-id="2c0ef-269">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="2c0ef-270">Служба Edge для пограничного сервера A/V</span><span class="sxs-lookup"><span data-stu-id="2c0ef-270">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="2c0ef-271">Требуется для общедоступной службы обмена мгновенными сообщениями в Windows Live Messenger</span><span class="sxs-lookup"><span data-stu-id="2c0ef-271">Required for public IM connectivity with Windows Live Messenger</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-extensible-messaging-and-presence-protocol"></a><span data-ttu-id="2c0ef-272">Сводка брандмауэра по протоколу расширенного обмена сообщениями и присутствия</span><span class="sxs-lookup"><span data-stu-id="2c0ef-272">Firewall Summary for Extensible Messaging and Presence Protocol</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2c0ef-273">Протокол/TCP или UDP/порт</span><span class="sxs-lookup"><span data-stu-id="2c0ef-273">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="2c0ef-274">Источник (IP-адрес)</span><span class="sxs-lookup"><span data-stu-id="2c0ef-274">Source (IP address)</span></span></th>
<th><span data-ttu-id="2c0ef-275">Назначение (IP-адрес)</span><span class="sxs-lookup"><span data-stu-id="2c0ef-275">Destination (IP address)</span></span></th>
<th><span data-ttu-id="2c0ef-276">Комментарии</span><span class="sxs-lookup"><span data-stu-id="2c0ef-276">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2c0ef-277">КСМПП/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="2c0ef-277">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="2c0ef-278">Любой</span><span class="sxs-lookup"><span data-stu-id="2c0ef-278">Any</span></span></p></td>
<td><p><span data-ttu-id="2c0ef-279">IP-адрес интерфейса службы пограничного доступа к серверу Edge</span><span class="sxs-lookup"><span data-stu-id="2c0ef-279">Edge Server Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="2c0ef-280">Стандартный коммуникационный порт "сервер-сервер" для КСМПП.</span><span class="sxs-lookup"><span data-stu-id="2c0ef-280">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="2c0ef-281">Разрешает связь с прокси-сервером пограничного сервера КСМПП от федеративных КСМПП партнеров</span><span class="sxs-lookup"><span data-stu-id="2c0ef-281">Allows communication to the Edge Server XMPP proxy from federated XMPP partners</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2c0ef-282">КСМПП/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="2c0ef-282">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="2c0ef-283">IP-адрес интерфейса службы пограничного доступа к серверу Edge</span><span class="sxs-lookup"><span data-stu-id="2c0ef-283">Edge Server Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="2c0ef-284">Любой</span><span class="sxs-lookup"><span data-stu-id="2c0ef-284">Any</span></span></p></td>
<td><p><span data-ttu-id="2c0ef-285">Стандартный коммуникационный порт "сервер-сервер" для КСМПП.</span><span class="sxs-lookup"><span data-stu-id="2c0ef-285">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="2c0ef-286">Разрешает взаимодействие с КСМПП прокси-сервером для федеративных КСМПП партнеров</span><span class="sxs-lookup"><span data-stu-id="2c0ef-286">Allows communication from the Edge Server XMPP proxy to federated XMPP partners</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2c0ef-287">КСМПП/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="2c0ef-287">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="2c0ef-288">Любой</span><span class="sxs-lookup"><span data-stu-id="2c0ef-288">Any</span></span></p></td>
<td><p><span data-ttu-id="2c0ef-289">Каждый внутренний IP-адрес интерфейса пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="2c0ef-289">Each internal Edge Server Interface IP</span></span></p></td>
<td><p><span data-ttu-id="2c0ef-290">Внутренний IP-адрес КСМПП, входящий в состав шлюза КСМПП на сервере переднего плана или в пуле переднего плана, в адрес внутренней сети пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="2c0ef-290">Internal XMPP traffic from the XMPP Gateway on the Front End Server or Front End pool to the Edge Server internal IP address or each Edge pool member’s internal IP address</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

