---
title: Сводка по портам — масштабируемая консолидированная пограничная система с аппаратными подсистемами балансировки нагрузки
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Port summary - Scaled consolidated edge with hardware load balancers
ms:assetid: 91213b1e-f875-464b-83e8-fe3a351595a4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398739(v=OCS.15)
ms:contentKeyID: 48184841
ms.date: 04/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e6af913a6be7b92a7a640a2e06537197ba21351c
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42183872"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="port-summary---scaled-consolidated-edge-with-hardware-load-balancers-in-lync-server-2013"></a><span data-ttu-id="a1ba1-102">Сводка по портам — масштабируемая консолидированная пограничная система с аппаратными подсистемами балансировки нагрузки в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a1ba1-102">Port summary - Scaled consolidated edge with hardware load balancers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a1ba1-103">_**Последнее изменение темы:** 2015-04-27_</span><span class="sxs-lookup"><span data-stu-id="a1ba1-103">_**Topic Last Modified:** 2015-04-27_</span></span>

<span data-ttu-id="a1ba1-104">Сервер Lync Server 2013, функции пограничного сервера, описанные в этой архитектуре сценариев, очень похожи на компоненты, реализованные в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="a1ba1-104">The Lync Server 2013, Edge Server functionality described in this scenario architecture is very similar to what was implemented in Lync Server 2010.</span></span> <span data-ttu-id="a1ba1-105">Наиболее значимым дополнением является порт **5269 по протоколу TCP** для поддержки протокола XMPP (расширяемый протокол обмена сообщениями и сведениями о присутствии).</span><span class="sxs-lookup"><span data-stu-id="a1ba1-105">The most noticeable addition is the port **5269 over TCP** entry for the extensible messaging and presence protocol (XMPP).</span></span> <span data-ttu-id="a1ba1-106">Lync Server 2013 при необходимости разворачивает прокси-сервер XMPP на пограничном или пограничном пуле и на сервере шлюза XMPP на сервере переднего плана или интерфейсном пуле.</span><span class="sxs-lookup"><span data-stu-id="a1ba1-106">Lync Server 2013 optionally deploys an XMPP proxy on the Edge Server or Edge pool and the XMPP gateway server on the Front End Server or Front End pool.</span></span>

<span data-ttu-id="a1ba1-107">Кроме протокола IPv4, пограничный сервер теперь поддерживает IPv6.</span><span class="sxs-lookup"><span data-stu-id="a1ba1-107">In addition to IPv4, the Edge Server now supports IPv6.</span></span> <span data-ttu-id="a1ba1-108">Для ясности в этих сценариях используется IPv4.</span><span class="sxs-lookup"><span data-stu-id="a1ba1-108">For clarity, only IPv4 is used in the scenarios.</span></span>

<span data-ttu-id="a1ba1-109">**Масштабируемая консолидированная пограничная балансировка с помощью аппаратной балансировки нагрузки**</span><span class="sxs-lookup"><span data-stu-id="a1ba1-109">**Scaled Consolidated Edge using Hardware Load Balancing**</span></span>

<span data-ttu-id="a1ba1-110">![Порты и протоколы сети периметра пограничного сервера](images/Gg398739.063f7dd1-16db-4cc7-8708-bca9bc41184d(OCS.15).jpg "Порты и протоколы сети периметра пограничного сервера")</span><span class="sxs-lookup"><span data-stu-id="a1ba1-110">![Edge Server Perimeter Network ports and protocols](images/Gg398739.063f7dd1-16db-4cc7-8708-bca9bc41184d(OCS.15).jpg "Edge Server Perimeter Network ports and protocols")</span></span>

<div>

## <a name="port-and-protocol-details"></a><span data-ttu-id="a1ba1-111">Сведения о портах и протоколе</span><span class="sxs-lookup"><span data-stu-id="a1ba1-111">Port and Protocol Details</span></span>

<span data-ttu-id="a1ba1-112">Рекомендуется открывать только те порты, которые требуются для поддержки функциональной возможности, к которой предоставляется внешний доступ.</span><span class="sxs-lookup"><span data-stu-id="a1ba1-112">It is recommended that you open only the ports required to support the functionality for which you are providing external access.</span></span>

<span data-ttu-id="a1ba1-p103">Для предоставления удаленного доступа в целях работы с любой пограничной службой необходимо разрешить двунаправленный трафик SIP, как показано на схеме пограничного входящего/исходящего трафика. Иначе говоря, сообщения SIP, поступающие в пограничную службу доступа и из нее, связаны со службой обмена мгновенными сообщениями и сведениями о присутствии, системой веб-конференций, аудио- и видеосвязи и федерациями.</span><span class="sxs-lookup"><span data-stu-id="a1ba1-p103">For remote access to work for any edge service, it is mandatory that SIP traffic is allowed to flow bi-directionally as shown in the Inbound/Outbound edge traffic figure. Stated another way, the SIP messaging to and from the Access Edge service is involved in instant messaging (IM), presence, web conferencing, audio/video (A/V) and federation.</span></span>

### <a name="firewall-summary-for-scaled-consolidated-edge-hardware-load-balanced-external-interface--node-1-and-node-2-example"></a><span data-ttu-id="a1ba1-115">Сводная информация по брандмауэрам для масштабируемого консолидированного пограничного сервера, аппаратно сбалансированная нагрузка: внешний интерфейс — узел 1 и узел 2 (пример)</span><span class="sxs-lookup"><span data-stu-id="a1ba1-115">Firewall Summary for Scaled Consolidated Edge, Hardware Load Balanced: External Interface – Node 1 and Node 2 (Example)</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a1ba1-116">Роль/протокол/TCP или UDP/порт</span><span class="sxs-lookup"><span data-stu-id="a1ba1-116">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="a1ba1-117">Исходный IP-адрес</span><span class="sxs-lookup"><span data-stu-id="a1ba1-117">Source IP address</span></span></th>
<th><span data-ttu-id="a1ba1-118">Конечный IP-адрес</span><span class="sxs-lookup"><span data-stu-id="a1ba1-118">Destination IP address</span></span></th>
<th><span data-ttu-id="a1ba1-119">Notes</span><span class="sxs-lookup"><span data-stu-id="a1ba1-119">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a1ba1-120">Access/HTTP/TCP/80</span><span class="sxs-lookup"><span data-stu-id="a1ba1-120">Access/HTTP/TCP/80</span></span></p></td>
<td><p><span data-ttu-id="a1ba1-121">Общедоступный IP-адрес пограничной службы доступа пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="a1ba1-121">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="a1ba1-122">Любые</span><span class="sxs-lookup"><span data-stu-id="a1ba1-122">Any</span></span></p></td>
<td><p><span data-ttu-id="a1ba1-123">Отзыв сертификата/проверка и поиск CRL</span><span class="sxs-lookup"><span data-stu-id="a1ba1-123">Certificate revocation/CRL check and retrieval</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a1ba1-124">Доступ/DNS/TCP/53</span><span class="sxs-lookup"><span data-stu-id="a1ba1-124">Access/DNS/TCP/53</span></span></p></td>
<td><p><span data-ttu-id="a1ba1-125">Общедоступный IP-адрес пограничной службы доступа пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="a1ba1-125">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="a1ba1-126">Любые</span><span class="sxs-lookup"><span data-stu-id="a1ba1-126">Any</span></span></p></td>
<td><p><span data-ttu-id="a1ba1-127">DNS-запрос по протоколу TCP</span><span class="sxs-lookup"><span data-stu-id="a1ba1-127">DNS query over TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a1ba1-128">Доступ/DNS/UDP/53</span><span class="sxs-lookup"><span data-stu-id="a1ba1-128">Access/DNS/UDP/53</span></span></p></td>
<td><p><span data-ttu-id="a1ba1-129">Общедоступный IP-адрес пограничной службы доступа пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="a1ba1-129">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="a1ba1-130">Любые</span><span class="sxs-lookup"><span data-stu-id="a1ba1-130">Any</span></span></p></td>
<td><p><span data-ttu-id="a1ba1-131">DNS-запрос по протоколу UDP</span><span class="sxs-lookup"><span data-stu-id="a1ba1-131">DNS query over UDP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a1ba1-132">АУДИО-И ВИДЕОДАННЫЕ/RTP/TCP/50000-– 999</span><span class="sxs-lookup"><span data-stu-id="a1ba1-132">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="a1ba1-133">IP-адрес службы пограничного сервера аудио-и видеоданных</span><span class="sxs-lookup"><span data-stu-id="a1ba1-133">Edge Server A/V Edge service IP address</span></span></p></td>
<td><p><span data-ttu-id="a1ba1-134">Любые</span><span class="sxs-lookup"><span data-stu-id="a1ba1-134">Any</span></span></p></td>
<td><p><span data-ttu-id="a1ba1-135">Необходимо для Федерации с партнерами, работающими под управлением Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 и Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a1ba1-135">Required for federating with partners running Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 and Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a1ba1-136">АУДИО-И ВИДЕОДАННЫЕ/RTP/UDP/50000-– 999</span><span class="sxs-lookup"><span data-stu-id="a1ba1-136">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="a1ba1-137">Общедоступный IP-адрес пограничного сервера аудио-и пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="a1ba1-137">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="a1ba1-138">Любые</span><span class="sxs-lookup"><span data-stu-id="a1ba1-138">Any</span></span></p></td>
<td><p><span data-ttu-id="a1ba1-139">Обязательно только для Федерации с партнерами, работающими под управлением Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="a1ba1-139">Required only for federation with partners running Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a1ba1-140">АУДИО-И ВИДЕОДАННЫЕ/RTP/TCP/50000-– 999</span><span class="sxs-lookup"><span data-stu-id="a1ba1-140">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="a1ba1-141">Любые</span><span class="sxs-lookup"><span data-stu-id="a1ba1-141">Any</span></span></p></td>
<td><p><span data-ttu-id="a1ba1-142">Общедоступный IP-адрес пограничного сервера аудио-и пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="a1ba1-142">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="a1ba1-143">Обязательно только для Федерации с партнерами, работающими под управлением Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="a1ba1-143">Required only for federation with partners running Office Communications Server 2007</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a1ba1-144">АУДИО-И ВИДЕОДАННЫЕ/RTP/UDP/50000-– 999</span><span class="sxs-lookup"><span data-stu-id="a1ba1-144">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="a1ba1-145">Любые</span><span class="sxs-lookup"><span data-stu-id="a1ba1-145">Any</span></span></p></td>
<td><p><span data-ttu-id="a1ba1-146">Общедоступный IP-адрес пограничного сервера аудио-и пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="a1ba1-146">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="a1ba1-147">Обязательно только для Федерации с партнерами, работающими под управлением Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="a1ba1-147">Required only for federation with partners running Office Communications Server 2007</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a1ba1-148">АУДИО-И ВИДЕОДАННЫЕ/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="a1ba1-148">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="a1ba1-149">Общедоступный IP-адрес пограничного сервера аудио-и пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="a1ba1-149">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="a1ba1-150">Любые</span><span class="sxs-lookup"><span data-stu-id="a1ba1-150">Any</span></span></p></td>
<td><p><span data-ttu-id="a1ba1-151">3478 исходящие используется для определения версии пограничного сервера, с которым обменивается данными Lync Server, а также для мультимедийного трафика с пограничного сервера на пограничный сервер.</span><span class="sxs-lookup"><span data-stu-id="a1ba1-151">3478 outbound is used to determine the version of Edge Server that Lync Server is communicating with and also for media traffic from Edge Server-to-Edge Server.</span></span> <span data-ttu-id="a1ba1-152">Обязательно для Федерации с Lync Server 2010, Windows Live Messenger и Office Communications Server 2007 R2, а также при развертывании нескольких пограничных пулов в компании.</span><span class="sxs-lookup"><span data-stu-id="a1ba1-152">Required for federation with Lync Server 2010, Windows Live Messenger, and Office Communications Server 2007 R2, and also if multiple Edge pools are deployed within a company.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a1ba1-153">АУДИО-И ВИДЕОДАННЫЕ/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="a1ba1-153">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="a1ba1-154">Любые</span><span class="sxs-lookup"><span data-stu-id="a1ba1-154">Any</span></span></p></td>
<td><p><span data-ttu-id="a1ba1-155">Общедоступный IP-адрес пограничного сервера аудио-и пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="a1ba1-155">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="a1ba1-156">STUN/TURN — согласование кандидатов по протоколу UDP/3478</span><span class="sxs-lookup"><span data-stu-id="a1ba1-156">STUN/TURN negotiation of candidates over UDP/3478</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a1ba1-157">АУДИО-И ВИДЕОДАННЫЕ/STUN, MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="a1ba1-157">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="a1ba1-158">Любые</span><span class="sxs-lookup"><span data-stu-id="a1ba1-158">Any</span></span></p></td>
<td><p><span data-ttu-id="a1ba1-159">Общедоступный IP-адрес пограничного сервера аудио-и пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="a1ba1-159">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="a1ba1-160">STUN/TURN — согласование кандидатов по протоколу TCP/443</span><span class="sxs-lookup"><span data-stu-id="a1ba1-160">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a1ba1-161">АУДИО-И ВИДЕОДАННЫЕ/STUN, MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="a1ba1-161">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="a1ba1-162">Общедоступный IP-адрес пограничного сервера аудио-и пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="a1ba1-162">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="a1ba1-163">Любые</span><span class="sxs-lookup"><span data-stu-id="a1ba1-163">Any</span></span></p></td>
<td><p><span data-ttu-id="a1ba1-164">STUN/TURN — согласование кандидатов по протоколу TCP/443</span><span class="sxs-lookup"><span data-stu-id="a1ba1-164">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="firewall-summary-for-scaled-consolidated-edge-hardware-load-balanced-internal-interface-node-1-and-node-2"></a><span data-ttu-id="a1ba1-165">Сводная информация по брандмауэрам для масштабируемого консолидированного пограничного сервера, аппаратно сбалансированная нагрузка: внутренний интерфейс — узел 1 и узел 2</span><span class="sxs-lookup"><span data-stu-id="a1ba1-165">Firewall Summary for Scaled Consolidated Edge, Hardware Load Balanced: Internal Interface Node 1 and Node 2</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a1ba1-166">Роль/протокол/TCP или UDP/порт</span><span class="sxs-lookup"><span data-stu-id="a1ba1-166">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="a1ba1-167">Исходный IP-адрес</span><span class="sxs-lookup"><span data-stu-id="a1ba1-167">Source IP address</span></span></th>
<th><span data-ttu-id="a1ba1-168">Конечный IP-адрес</span><span class="sxs-lookup"><span data-stu-id="a1ba1-168">Destination IP address</span></span></th>
<th><span data-ttu-id="a1ba1-169">Notes</span><span class="sxs-lookup"><span data-stu-id="a1ba1-169">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a1ba1-170">XMPP/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="a1ba1-170">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="a1ba1-171">Любой (может быть определен как адрес сервера переднего плана или виртуальный IP-адрес пула переднего плана, на котором запущена служба шлюза XMPP)</span><span class="sxs-lookup"><span data-stu-id="a1ba1-171">Any (can be defined as Front End Server address, or Front End pool virtual IP address running the XMPP Gateway service)</span></span></p></td>
<td><p><span data-ttu-id="a1ba1-172">Внутренний интерфейс пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="a1ba1-172">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="a1ba1-173">Исходящий трафик XMPP из службы шлюза XMPP, работающего на сервере переднего плана или интерфейсном пуле</span><span class="sxs-lookup"><span data-stu-id="a1ba1-173">Outbound XMPP traffic from XMPP Gateway service running on Front End Server or Front End pool</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a1ba1-174">HTTPS/TCP/4443</span><span class="sxs-lookup"><span data-stu-id="a1ba1-174">HTTPS/TCP/4443</span></span></p></td>
<td><p><span data-ttu-id="a1ba1-175">Любой (может быть определен как IP-адрес сервера переднего плана или пул, в котором хранится центральное хранилище управления)</span><span class="sxs-lookup"><span data-stu-id="a1ba1-175">Any (can be defined as the Front End Server server IP or pool that holds the Central Management store)</span></span></p></td>
<td><p><span data-ttu-id="a1ba1-176">Внутренний интерфейс пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="a1ba1-176">Edge Server Internal interface</span></span></p></td>
<td><p><span data-ttu-id="a1ba1-177">Репликация изменений из центрального хранилища управления на пограничный сервер</span><span class="sxs-lookup"><span data-stu-id="a1ba1-177">Replication of changes from the Central Management store to the Edge Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a1ba1-178">PSOM/MTLS/TCP/8057</span><span class="sxs-lookup"><span data-stu-id="a1ba1-178">PSOM/MTLS/TCP/8057</span></span></p></td>
<td><p><span data-ttu-id="a1ba1-179">Любой (может быть определен как IP-адрес директора, IP-адрес сервера переднего плана или виртуальный IP-адрес пула)</span><span class="sxs-lookup"><span data-stu-id="a1ba1-179">Any (can be defined as Director IP, Front End Server IP or Pool virtual IP)</span></span></p></td>
<td><p><span data-ttu-id="a1ba1-180">Внутренний интерфейс пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="a1ba1-180">Edge Server Internal interface</span></span></p></td>
<td><p><span data-ttu-id="a1ba1-181">Трафик веб-конференций из внутреннего развертывания во внутренний интерфейс пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="a1ba1-181">Web conferencing traffic from Internal deployment to Internal Edge Server interface</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a1ba1-182">STUN/MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="a1ba1-182">STUN/MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="a1ba1-183">Любой (может быть определен как IP-адрес директора, IP-адрес сервера переднего плана или виртуальный IP-адрес пула)</span><span class="sxs-lookup"><span data-stu-id="a1ba1-183">Any (can be defined as Director IP, Front End Server IP or Pool virtual IP)</span></span></p></td>
<td><p><span data-ttu-id="a1ba1-184">Внутренний интерфейс пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="a1ba1-184">Edge Server Internal interface</span></span></p></td>
<td><p><span data-ttu-id="a1ba1-185">Предпочтительный путь для передачи аудио-и видеоданных между внутренними и внешними пользователями, устройством для обеспечения связи в филиалах или сервером обеспечения связи в филиалах</span><span class="sxs-lookup"><span data-stu-id="a1ba1-185">Preferred path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a1ba1-186">STUN/MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="a1ba1-186">STUN/MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="a1ba1-187">Любой (может быть определен как IP-адрес директора, IP-адрес сервера переднего плана или виртуальный IP-адрес пула)</span><span class="sxs-lookup"><span data-stu-id="a1ba1-187">Any (can be defined as Director IP, Front End Server IP or Pool virtual IP)</span></span></p></td>
<td><p><span data-ttu-id="a1ba1-188">Внутренний интерфейс пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="a1ba1-188">Edge Server Internal interface</span></span></p></td>
<td><p><span data-ttu-id="a1ba1-189">Резервный путь для передачи аудио-и видеоданных между внутренними и внешними пользователями, устройства для обеспечения связи в филиалах или сервера для обеспечения связи в филиалах если не удается установить UDP-связь, используется TCP для передачи файлов и общего доступа к рабочему столу</span><span class="sxs-lookup"><span data-stu-id="a1ba1-189">Fallback path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server if UDP communication cannot be established, TCP is used for file transfer and desktop sharing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a1ba1-190">MTLS/TCP/50001</span><span class="sxs-lookup"><span data-stu-id="a1ba1-190">MTLS/TCP/50001</span></span></p></td>
<td><p><span data-ttu-id="a1ba1-191">Любые</span><span class="sxs-lookup"><span data-stu-id="a1ba1-191">Any</span></span></p></td>
<td><p><span data-ttu-id="a1ba1-192">Внутренний интерфейс пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="a1ba1-192">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="a1ba1-193">Централизованное ведение журналов с помощью команд Командная консоль Lync Server и командлетов службы централизованного ведения журналов, Командная строка ClsController (ClsController. exe) или агента (ClsAgent. exe) и коллекция журналов</span><span class="sxs-lookup"><span data-stu-id="a1ba1-193">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a1ba1-194">MTLS/TCP/50002</span><span class="sxs-lookup"><span data-stu-id="a1ba1-194">MTLS/TCP/50002</span></span></p></td>
<td><p><span data-ttu-id="a1ba1-195">Любые</span><span class="sxs-lookup"><span data-stu-id="a1ba1-195">Any</span></span></p></td>
<td><p><span data-ttu-id="a1ba1-196">Внутренний интерфейс пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="a1ba1-196">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="a1ba1-197">Централизованное ведение журналов с помощью команд Командная консоль Lync Server и командлетов службы централизованного ведения журналов, Командная строка ClsController (ClsController. exe) или агента (ClsAgent. exe) и коллекция журналов</span><span class="sxs-lookup"><span data-stu-id="a1ba1-197">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a1ba1-198">MTLS/TCP/50003</span><span class="sxs-lookup"><span data-stu-id="a1ba1-198">MTLS/TCP/50003</span></span></p></td>
<td><p><span data-ttu-id="a1ba1-199">Любые</span><span class="sxs-lookup"><span data-stu-id="a1ba1-199">Any</span></span></p></td>
<td><p><span data-ttu-id="a1ba1-200">Внутренний интерфейс пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="a1ba1-200">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="a1ba1-201">Централизованное ведение журналов с помощью команд Командная консоль Lync Server и командлетов службы централизованного ведения журналов, Командная строка ClsController (ClsController. exe) или агента (ClsAgent. exe) и коллекция журналов</span><span class="sxs-lookup"><span data-stu-id="a1ba1-201">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="a1ba1-202">Для аппаратных подсистем балансировки нагрузки предъявляются особые требования при развертывании для обеспечения доступности и балансировки нагрузки для Lync Server.</span><span class="sxs-lookup"><span data-stu-id="a1ba1-202">Hardware load balancers have specific requirements when deployed to provide availability and load balancing for Lync Server.</span></span> <span data-ttu-id="a1ba1-203">Эти требования указаны в следующих таблицах и на изображении.</span><span class="sxs-lookup"><span data-stu-id="a1ba1-203">The requirements are defined in the following figure and tables.</span></span> <span data-ttu-id="a1ba1-204">Сторонние поставщики могут использовать различную терминологию для требований, приведенных здесь.</span><span class="sxs-lookup"><span data-stu-id="a1ba1-204">Third party vendors may use different terminology for the requirements defined here.</span></span> <span data-ttu-id="a1ba1-205">Необходимо сопоставить требования Lync Server с функциями и параметрами конфигурации, предоставляемыми поставщиком аппаратной балансировки нагрузки.</span><span class="sxs-lookup"><span data-stu-id="a1ba1-205">It will be necessary to map the requirements of Lync Server to the features and configuration options provided by your hardware load balancer vendor.</span></span>

<span data-ttu-id="a1ba1-206">При настройке аппаратных балансировщиков нагрузки необходимо учитывать следующие требования.</span><span class="sxs-lookup"><span data-stu-id="a1ba1-206">When configuring hardware load balancers, consider the following requirements:</span></span>

  - <span data-ttu-id="a1ba1-207">Для службы пограничного сервера доступа и пограничной службы веб-конференций можно настроить трансляцию адресов исходной сети (SNAT) на аппаратный балансировщик нагрузки (HLB).</span><span class="sxs-lookup"><span data-stu-id="a1ba1-207">Source Network Address Translation (SNAT) can be configured on the hardware load balancer (HLB) for Access Edge service and Web Conferencing Edge service</span></span>

  - <span data-ttu-id="a1ba1-208">Служба SNAT не может быть настроена для пограничной службы аудио-и видеоданных — пограничная служба аудио-и видеоданных должна отвечать с реальным адресом сервера, а не с виртуальным IP-адресом HLB (VIP) для простого обхода протокола UDP over NAT (STUN)/траверсал с помощью ретрансляции NAT ()/федератион (ФТУРН) для правильной работы</span><span class="sxs-lookup"><span data-stu-id="a1ba1-208">SNAT cannot be configured on the A/V Edge service– the A/V Edge service must respond with the real server address, not the HLB virtual IP (VIP), for simple traversal of UDP over NAT (STUN)/traversal using relay NAT (TURN)/federation TURN (FTURN) to work properly</span></span>
    
      - <span data-ttu-id="a1ba1-209">Если клиент отправляет запрос на HLB, ответ должен возвращаться из виртуального IP-адреса HLB</span><span class="sxs-lookup"><span data-stu-id="a1ba1-209">If the client sends a request to the HLB, the response must come back from the HLB VIP</span></span>
    
      - <span data-ttu-id="a1ba1-210">Если клиент отправляет запрос на пограничный сервер, ответ должен быть получен от пограничного IP-адреса.</span><span class="sxs-lookup"><span data-stu-id="a1ba1-210">If the client sends a request to the Edge, the response must come back from the Edge IP</span></span>

  - <span data-ttu-id="a1ba1-211">Общедоступные IP-адреса используются в каждом интерфейсе сервера и виртуальных IP-адресах HLB, а требования к общедоступным IP-адресам — N + 1, где есть общедоступный IP-адрес для каждого сервера реального сервера и один для каждого IP-адреса HLB.</span><span class="sxs-lookup"><span data-stu-id="a1ba1-211">Public IP addresses are used on each server interface and on the VIPs of the HLB, and your public IP address requirements are N+1, where there is a public IP address for each real server interface and one for each HLB VIP.</span></span> <span data-ttu-id="a1ba1-212">При наличии 2 пограничных серверов в пуле это приводит к 9 общедоступным IP-адресам, где 3 используются для виртуальных IP-адресов, и по одному для каждого интерфейса пограничного сервера (всего до шести для серверов).</span><span class="sxs-lookup"><span data-stu-id="a1ba1-212">Where you have 2 Edge servers in the pool, this results in 9 public IP addresses, where 3 are used for the HLB VIPs, and one for each Edge server interface (a total of six for the servers)</span></span>

  - <span data-ttu-id="a1ba1-213">Для пограничной службы доступа и пограничной службы веб-конференций (и с помощью NAT в HLB) клиент обращается к ВИРТУАЛЬНОЙ IP-сети, IP-адрес источника изменяется с клиента на его IP-адрес.</span><span class="sxs-lookup"><span data-stu-id="a1ba1-213">For the Access Edge service and Web Conferencing Edge service, (and using NAT on the HLB) the client contacts the VIP, the VIP changes the source IP address from the client to its own IP address.</span></span> <span data-ttu-id="a1ba1-214">Интерфейс сервера передает обратный адрес на виртуальный IP-адрес, который заменяет IP-адрес интерфейса сервера на исходный адрес и отправляет пакет клиенту</span><span class="sxs-lookup"><span data-stu-id="a1ba1-214">The server interface addresses the return address to the VIP, the VIP changes the source address from the server interface IP address and sends the packet to the client</span></span>

  - <span data-ttu-id="a1ba1-215">Для пограничной службы аудио-и видеоданных виртуальный IP-адрес не должен измениться, а фактический адрес сервера возвращается клиенту напрямую — невозможно настроить NAT на HLB для трафика AV</span><span class="sxs-lookup"><span data-stu-id="a1ba1-215">For the A/V Edge service, the VIP must NOT change the source IP address, and the real server address is returned to the client directly – you cannot configure NAT on the HLB for AV traffic</span></span>
    
      - <span data-ttu-id="a1ba1-216">Если клиент отправляет запрос на HLB VIP, ответ должен возвращаться из виртуального IP-адреса HLB</span><span class="sxs-lookup"><span data-stu-id="a1ba1-216">If the client sends a request to the HLB VIP, the response must come back from the HLB VIP</span></span>
    
      - <span data-ttu-id="a1ba1-217">Если клиент отправляет запрос на пограничный IP-адрес, ответ должен возвращаться от пограничного IP-адреса.</span><span class="sxs-lookup"><span data-stu-id="a1ba1-217">If the client sends a request to the Edge IP, the response must come back from the Edge IP</span></span>

  - <span data-ttu-id="a1ba1-218">Для трафика аудио и видео внешний брандмауэр будет сохранять реальный общедоступный IP-адрес сервера для всех пакетов</span><span class="sxs-lookup"><span data-stu-id="a1ba1-218">For AV, the external firewall will retain the real server public IP address for all packets</span></span>

  - <span data-ttu-id="a1ba1-219">После установки клиент для пограничной службы аудио-и видеосвязи становится реальным сервером, а не HLB.</span><span class="sxs-lookup"><span data-stu-id="a1ba1-219">Once established, client to A/V Edge service communication is to the real server, not the HLB</span></span>

  - <span data-ttu-id="a1ba1-220">Внутренняя граница для внутренних серверов и клиентов должна маршрутизироваться; постоянные маршруты настраиваются для всех внутренних сетей, в которых размещаются серверы или клиенты</span><span class="sxs-lookup"><span data-stu-id="a1ba1-220">Internal edge to internal servers and clients must be routed, and persistent routes are set for all internal networks that host servers or clients</span></span>

  - <span data-ttu-id="a1ba1-221">Виртуальный IP-адрес пограничной службы доступа HLB будет использоваться в качестве шлюза по умолчанию для каждого интерфейса пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="a1ba1-221">The HLB Access Edge service VIP will act as the default gateway for each Edge server interface</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="a1ba1-222">Для получения дополнительных сведений о планировании и функциональных возможностях NAT обратитесь к разделу <A href="lync-server-2013-hardware-load-balancer-requirements.md">требования к оборудованию балансировки нагрузки для Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="a1ba1-222">For further information on NAT planning and functionality, please refer to <A href="lync-server-2013-hardware-load-balancer-requirements.md">Hardware load balancer requirements for Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="a1ba1-223">![Сведения о портах и протоколах пограничного сервера](images/Gg398739.1c193b80-98ab-4d59-a854-dbfdb5e209e2(OCS.15).jpg "Сведения о портах и протоколах пограничного сервера")</span><span class="sxs-lookup"><span data-stu-id="a1ba1-223">![Edge Server ports and protocols details](images/Gg398739.1c193b80-98ab-4d59-a854-dbfdb5e209e2(OCS.15).jpg "Edge Server ports and protocols details")</span></span>

### <a name="external-port-settings-required-for-scaled-consolidated-edge-hardware-load-balanced-external-interface-virtual-ips"></a><span data-ttu-id="a1ba1-224">Параметры внешнего порта, необходимые для масштабируемого консолидированного пограничного сервера, аппаратно сбалансированная нагрузка: виртуальные IP-адреса внешнего интерфейса</span><span class="sxs-lookup"><span data-stu-id="a1ba1-224">External Port Settings Required for Scaled Consolidated Edge, Hardware Load Balanced: External Interface Virtual IPs</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a1ba1-225">Роль/протокол/TCP или UDP/порт</span><span class="sxs-lookup"><span data-stu-id="a1ba1-225">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="a1ba1-226">Исходный IP-адрес</span><span class="sxs-lookup"><span data-stu-id="a1ba1-226">Source IP address</span></span></th>
<th><span data-ttu-id="a1ba1-227">Конечный IP-адрес</span><span class="sxs-lookup"><span data-stu-id="a1ba1-227">Destination IP address</span></span></th>
<th><span data-ttu-id="a1ba1-228">Notes</span><span class="sxs-lookup"><span data-stu-id="a1ba1-228">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a1ba1-229">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="a1ba1-229">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="a1ba1-230">Любые</span><span class="sxs-lookup"><span data-stu-id="a1ba1-230">Any</span></span></p></td>
<td><p><span data-ttu-id="a1ba1-231">Прокси-служба XMPP (общий IP-адрес с пограничной службой доступа)</span><span class="sxs-lookup"><span data-stu-id="a1ba1-231">XMPP Proxy service (shares IP address with Access Edge service)</span></span></p></td>
<td><p><span data-ttu-id="a1ba1-232">Служба прокси XMPP принимает трафик от контактов XMPP в определенных федерациях XMPP</span><span class="sxs-lookup"><span data-stu-id="a1ba1-232">XMPP Proxy service accepts traffic from XMPP contacts in defined XMPP federations</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a1ba1-233">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="a1ba1-233">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="a1ba1-234">Прокси-служба XMPP (общий IP-адрес с пограничной службой доступа)</span><span class="sxs-lookup"><span data-stu-id="a1ba1-234">XMPP Proxy service (shares IP address with Access Edge service)</span></span></p></td>
<td><p><span data-ttu-id="a1ba1-235">Любые</span><span class="sxs-lookup"><span data-stu-id="a1ba1-235">Any</span></span></p></td>
<td><p><span data-ttu-id="a1ba1-236">Прокси-служба XMPP отправляет трафик контактам XMPP в определенных федерациях XMPP</span><span class="sxs-lookup"><span data-stu-id="a1ba1-236">XMPP Proxy service sends traffic to XMPP contacts in defined XMPP federations</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a1ba1-237">/TCP/443 доступа и SIP (TLS)</span><span class="sxs-lookup"><span data-stu-id="a1ba1-237">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="a1ba1-238">Любые</span><span class="sxs-lookup"><span data-stu-id="a1ba1-238">Any</span></span></p></td>
<td><p><span data-ttu-id="a1ba1-239">Общедоступный виртуальный IP-адрес пограничной службы доступа</span><span class="sxs-lookup"><span data-stu-id="a1ba1-239">Access Edge service public VIP address</span></span></p></td>
<td><p><span data-ttu-id="a1ba1-240">Трафик SIP «клиент-сервер» для доступа внешних пользователей</span><span class="sxs-lookup"><span data-stu-id="a1ba1-240">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a1ba1-241">Доступ/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="a1ba1-241">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="a1ba1-242">Любые</span><span class="sxs-lookup"><span data-stu-id="a1ba1-242">Any</span></span></p></td>
<td><p><span data-ttu-id="a1ba1-243">Общедоступный виртуальный IP-адрес пограничной службы доступа</span><span class="sxs-lookup"><span data-stu-id="a1ba1-243">Access Edge service public VIP address</span></span></p></td>
<td><p><span data-ttu-id="a1ba1-244">Передача сигналов SIP, Федеративные и общедоступные службы обмена мгновенными сообщениями с помощью SIP</span><span class="sxs-lookup"><span data-stu-id="a1ba1-244">SIP signaling, federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a1ba1-245">Доступ/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="a1ba1-245">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="a1ba1-246">Общедоступный виртуальный IP-адрес пограничной службы доступа</span><span class="sxs-lookup"><span data-stu-id="a1ba1-246">Access Edge service public VIP address</span></span></p></td>
<td><p><span data-ttu-id="a1ba1-247">Федеративный партнер</span><span class="sxs-lookup"><span data-stu-id="a1ba1-247">Federated partner</span></span></p></td>
<td><p><span data-ttu-id="a1ba1-248">Передача сигналов SIP, Федеративные и общедоступные службы обмена мгновенными сообщениями с помощью SIP</span><span class="sxs-lookup"><span data-stu-id="a1ba1-248">SIP signaling, federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a1ba1-249">Веб-конференции/PSOM (TLS)/TCP/443</span><span class="sxs-lookup"><span data-stu-id="a1ba1-249">Web Conferencing/PSOM(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="a1ba1-250">Любые</span><span class="sxs-lookup"><span data-stu-id="a1ba1-250">Any</span></span></p></td>
<td><p><span data-ttu-id="a1ba1-251">Общедоступный виртуальный IP-адрес пограничного сервера веб-конференций пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="a1ba1-251">Edge Server Web Conferencing Edge service public VIP address</span></span></p></td>
<td><p><span data-ttu-id="a1ba1-252">Устройство для веб-конференций</span><span class="sxs-lookup"><span data-stu-id="a1ba1-252">Web Conferencing media</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a1ba1-253">АУДИО-И ВИДЕОДАННЫЕ/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="a1ba1-253">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="a1ba1-254">Любые</span><span class="sxs-lookup"><span data-stu-id="a1ba1-254">Any</span></span></p></td>
<td><p><span data-ttu-id="a1ba1-255">Общедоступный виртуальный IP-адрес пограничного сервера аудио-и пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="a1ba1-255">Edge Server A/V Edge service public VIP address</span></span></p></td>
<td><p><span data-ttu-id="a1ba1-256">STUN/TURN — согласование кандидатов по протоколу UDP/3478</span><span class="sxs-lookup"><span data-stu-id="a1ba1-256">STUN/TURN negotiation of candidates over UDP/3478</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a1ba1-257">АУДИО-И ВИДЕОДАННЫЕ/STUN, MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="a1ba1-257">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="a1ba1-258">Любые</span><span class="sxs-lookup"><span data-stu-id="a1ba1-258">Any</span></span></p></td>
<td><p><span data-ttu-id="a1ba1-259">Общедоступный виртуальный IP-адрес пограничного сервера аудио-и пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="a1ba1-259">Edge Server A/V Edge service public VIP address</span></span></p></td>
<td><p><span data-ttu-id="a1ba1-260">STUN/TURN — согласование кандидатов по протоколу TCP/443</span><span class="sxs-lookup"><span data-stu-id="a1ba1-260">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="firewall-summary-for-scaled-consolidated-edge-hardware-load-balanced-internal-interface-virtual-ips"></a><span data-ttu-id="a1ba1-261">Сводная информация по брандмауэрам для масштабируемого консолидированного пограничного сервера, аппаратно сбалансированная нагрузка: внутренний интерфейс — виртуальные IP-адреса</span><span class="sxs-lookup"><span data-stu-id="a1ba1-261">Firewall Summary for Scaled Consolidated Edge, Hardware Load Balanced: Internal Interface Virtual IPs</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a1ba1-262">Роль/протокол/TCP или UDP/порт</span><span class="sxs-lookup"><span data-stu-id="a1ba1-262">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="a1ba1-263">Исходный IP-адрес</span><span class="sxs-lookup"><span data-stu-id="a1ba1-263">Source IP address</span></span></th>
<th><span data-ttu-id="a1ba1-264">Конечный IP-адрес</span><span class="sxs-lookup"><span data-stu-id="a1ba1-264">Destination IP address</span></span></th>
<th><span data-ttu-id="a1ba1-265">Notes</span><span class="sxs-lookup"><span data-stu-id="a1ba1-265">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a1ba1-266">Доступ/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="a1ba1-266">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="a1ba1-267">Любой (может быть определен как директор, виртуальный IP-адрес пула директоров, сервер переднего плана или виртуальный IP-адрес пула переднего плана)</span><span class="sxs-lookup"><span data-stu-id="a1ba1-267">Any (can be defined as Director, Director pool virtual IP address, Front End Server or Front End pool virtual IP address)</span></span></p></td>
<td><p><span data-ttu-id="a1ba1-268">Интерфейс внутреннего виртуального IP-адреса пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="a1ba1-268">Edge Server Internal VIP interface</span></span></p></td>
<td><p><span data-ttu-id="a1ba1-269">Исходящий трафик SIP (от директоров, виртуальный IP-адрес пула директоров, виртуальный IP-адрес сервера переднего плана или пула переднего плана) на внутренний пограничный IP-адрес.</span><span class="sxs-lookup"><span data-stu-id="a1ba1-269">Outbound SIP traffic (from Director, Director pool virtual IP address, Front End Server or Front End pool virtual IP address)to Internal Edge VIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a1ba1-270">Доступ/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="a1ba1-270">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="a1ba1-271">Интерфейс внутреннего виртуального IP-адреса пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="a1ba1-271">Edge Server Internal VIP interface</span></span></p></td>
<td><p><span data-ttu-id="a1ba1-272">Любой (может быть определен как директор, виртуальный IP-адрес пула директоров, сервер переднего плана или виртуальный IP-адрес пула переднего плана)</span><span class="sxs-lookup"><span data-stu-id="a1ba1-272">Any (can be defined as Director, Director pool virtual IP address, Front End Server or Front End pool virtual IP address)</span></span></p></td>
<td><p><span data-ttu-id="a1ba1-273">Входящий трафик SIP (в директоре, виртуальный IP-адрес пула директоров, виртуальный IP-адрес сервера переднего плана или пула переднего плана) от внутреннего интерфейса пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="a1ba1-273">Inbound SIP traffic (to Director, Director pool virtual IP address, Front End Server or Front End pool virtual IP address) from Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a1ba1-274">SIP/MTLS/TCP/5062</span><span class="sxs-lookup"><span data-stu-id="a1ba1-274">SIP/MTLS/TCP/5062</span></span></p></td>
<td><p><span data-ttu-id="a1ba1-275">Любой (может быть определен как IP-адрес сервера переднего плана или IP-адрес пула переднего плана или любое устройство для обеспечения связи в филиале или как сервер для обеспечения связи в филиалах с помощью этого пограничного сервера)</span><span class="sxs-lookup"><span data-stu-id="a1ba1-275">Any (can be defined as Front End Server IP address, or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server)</span></span></p></td>
<td><p><span data-ttu-id="a1ba1-276">Интерфейс внутреннего виртуального IP-адреса пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="a1ba1-276">Edge Server Internal VIP interface</span></span></p></td>
<td><p><span data-ttu-id="a1ba1-277">Проверка подлинности пользователей и подлинности (служба проверки подлинности A/V) с IP-адреса сервера переднего плана или интерфейсного пула или любого устройства для обеспечения связи в филиалах или сервера обеспечения связи в филиалах с помощью этого пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="a1ba1-277">Authentication of A/V users (A/V authentication service) from Front End Server or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a1ba1-278">STUN/MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="a1ba1-278">STUN/MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="a1ba1-279">Любые</span><span class="sxs-lookup"><span data-stu-id="a1ba1-279">Any</span></span></p></td>
<td><p><span data-ttu-id="a1ba1-280">Интерфейс внутреннего виртуального IP-адреса пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="a1ba1-280">Edge Server Internal VIP interface</span></span></p></td>
<td><p><span data-ttu-id="a1ba1-281">Предпочитаемый путь передачи аудио/видео между внутренними и внешними пользователями</span><span class="sxs-lookup"><span data-stu-id="a1ba1-281">Preferred path for A/V media transfer between internal and external users</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a1ba1-282">STUN/MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="a1ba1-282">STUN/MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="a1ba1-283">Любые</span><span class="sxs-lookup"><span data-stu-id="a1ba1-283">Any</span></span></p></td>
<td><p><span data-ttu-id="a1ba1-284">Интерфейс внутреннего виртуального IP-адреса пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="a1ba1-284">Edge Server Internal VIP interface</span></span></p></td>
<td><p><span data-ttu-id="a1ba1-285">Резервный путь для передачи аудио/видео между внутренними и внешними пользователями в случае, если не удается установить подключение UDP; для передачи файлов и общего доступа к рабочему столу используется TCP</span><span class="sxs-lookup"><span data-stu-id="a1ba1-285">Fallback path for A/V media transfer between internal and external users if UDP communication cannot be established, TCP is used for file transfer and desktop sharing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a1ba1-286">STUN/MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="a1ba1-286">STUN/MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="a1ba1-287">Интерфейс внутреннего виртуального IP-адреса пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="a1ba1-287">Edge Server Internal VIP interface</span></span></p></td>
<td><p><span data-ttu-id="a1ba1-288">Любые</span><span class="sxs-lookup"><span data-stu-id="a1ba1-288">Any</span></span></p></td>
<td><p><span data-ttu-id="a1ba1-289">Резервный путь для передачи аудио/видео между внутренними и внешними пользователями в случае, если не удается установить подключение UDP; для передачи файлов и общего доступа к рабочему столу используется TCP</span><span class="sxs-lookup"><span data-stu-id="a1ba1-289">Fallback path for A/V media transfer between internal and external users if UDP communication cannot be established, TCP is used for file transfer and desktop sharing</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

