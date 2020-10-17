---
title: Сводка по портам — масштабируемая консолидированная пограничная система с аппаратными подсистемами балансировки нагрузки
description: Сводка по портам — масштабируемая консолидированная пограничная система с аппаратными подсистемами балансировки нагрузки.
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
ms.openlocfilehash: 1a03acb3644d83669bcf0065ebb20c526ef5fa32
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48564595"
---
# <a name="port-summary---scaled-consolidated-edge-with-hardware-load-balancers-in-lync-server-2013"></a><span data-ttu-id="efded-103">Сводка по портам — масштабируемая консолидированная пограничная система с аппаратными подсистемами балансировки нагрузки в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="efded-103">Port summary - Scaled consolidated edge with hardware load balancers in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="efded-104">_**Последнее изменение темы:** 2015-04-27_</span><span class="sxs-lookup"><span data-stu-id="efded-104">_**Topic Last Modified:** 2015-04-27_</span></span>

<span data-ttu-id="efded-105">Сервер Lync Server 2013, функции пограничного сервера, описанные в этой архитектуре сценариев, очень похожи на компоненты, реализованные в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="efded-105">The Lync Server 2013, Edge Server functionality described in this scenario architecture is very similar to what was implemented in Lync Server 2010.</span></span> <span data-ttu-id="efded-106">Наиболее значимым дополнением является порт **5269 по протоколу TCP** для поддержки протокола XMPP (расширяемый протокол обмена сообщениями и сведениями о присутствии).</span><span class="sxs-lookup"><span data-stu-id="efded-106">The most noticeable addition is the port **5269 over TCP** entry for the extensible messaging and presence protocol (XMPP).</span></span> <span data-ttu-id="efded-107">Lync Server 2013 при необходимости разворачивает прокси-сервер XMPP на пограничном или пограничном пуле и на сервере шлюза XMPP на сервере переднего плана или интерфейсном пуле.</span><span class="sxs-lookup"><span data-stu-id="efded-107">Lync Server 2013 optionally deploys an XMPP proxy on the Edge Server or Edge pool and the XMPP gateway server on the Front End Server or Front End pool.</span></span>

<span data-ttu-id="efded-108">Кроме протокола IPv4, пограничный сервер теперь поддерживает IPv6.</span><span class="sxs-lookup"><span data-stu-id="efded-108">In addition to IPv4, the Edge Server now supports IPv6.</span></span> <span data-ttu-id="efded-109">Для ясности в этих сценариях используется IPv4.</span><span class="sxs-lookup"><span data-stu-id="efded-109">For clarity, only IPv4 is used in the scenarios.</span></span>

<span data-ttu-id="efded-110">**Масштабируемая консолидированная пограничная балансировка с помощью аппаратной балансировки нагрузки**</span><span class="sxs-lookup"><span data-stu-id="efded-110">**Scaled Consolidated Edge using Hardware Load Balancing**</span></span>

<span data-ttu-id="efded-111">![Порты и протоколы сети периметра пограничного сервера](images/Gg398739.063f7dd1-16db-4cc7-8708-bca9bc41184d(OCS.15).jpg "Порты и протоколы сети периметра пограничного сервера")</span><span class="sxs-lookup"><span data-stu-id="efded-111">![Edge Server Perimeter Network ports and protocols](images/Gg398739.063f7dd1-16db-4cc7-8708-bca9bc41184d(OCS.15).jpg "Edge Server Perimeter Network ports and protocols")</span></span>

<div>

## <a name="port-and-protocol-details"></a><span data-ttu-id="efded-112">Сведения о портах и протоколе</span><span class="sxs-lookup"><span data-stu-id="efded-112">Port and Protocol Details</span></span>

<span data-ttu-id="efded-113">Рекомендуется открывать только те порты, которые требуются для поддержки функциональной возможности, к которой предоставляется внешний доступ.</span><span class="sxs-lookup"><span data-stu-id="efded-113">It is recommended that you open only the ports required to support the functionality for which you are providing external access.</span></span>

<span data-ttu-id="efded-p103">Для предоставления удаленного доступа в целях работы с любой пограничной службой необходимо разрешить двунаправленный трафик SIP, как показано на схеме пограничного входящего/исходящего трафика. Иначе говоря, сообщения SIP, поступающие в пограничную службу доступа и из нее, связаны со службой обмена мгновенными сообщениями и сведениями о присутствии, системой веб-конференций, аудио- и видеосвязи и федерациями.</span><span class="sxs-lookup"><span data-stu-id="efded-p103">For remote access to work for any edge service, it is mandatory that SIP traffic is allowed to flow bi-directionally as shown in the Inbound/Outbound edge traffic figure. Stated another way, the SIP messaging to and from the Access Edge service is involved in instant messaging (IM), presence, web conferencing, audio/video (A/V) and federation.</span></span>

### <a name="firewall-summary-for-scaled-consolidated-edge-hardware-load-balanced-external-interface--node-1-and-node-2-example"></a><span data-ttu-id="efded-116">Сводная информация по брандмауэрам для масштабируемого консолидированного пограничного сервера, аппаратно сбалансированная нагрузка: внешний интерфейс — узел 1 и узел 2 (пример)</span><span class="sxs-lookup"><span data-stu-id="efded-116">Firewall Summary for Scaled Consolidated Edge, Hardware Load Balanced: External Interface – Node 1 and Node 2 (Example)</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="efded-117">Роль/протокол/TCP или UDP/порт</span><span class="sxs-lookup"><span data-stu-id="efded-117">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="efded-118">Исходный IP-адрес</span><span class="sxs-lookup"><span data-stu-id="efded-118">Source IP address</span></span></th>
<th><span data-ttu-id="efded-119">Конечный IP-адрес</span><span class="sxs-lookup"><span data-stu-id="efded-119">Destination IP address</span></span></th>
<th><span data-ttu-id="efded-120">Примечания</span><span class="sxs-lookup"><span data-stu-id="efded-120">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="efded-121">Access/HTTP/TCP/80</span><span class="sxs-lookup"><span data-stu-id="efded-121">Access/HTTP/TCP/80</span></span></p></td>
<td><p><span data-ttu-id="efded-122">Общедоступный IP-адрес пограничной службы доступа пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="efded-122">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="efded-123">Любой</span><span class="sxs-lookup"><span data-stu-id="efded-123">Any</span></span></p></td>
<td><p><span data-ttu-id="efded-124">Отзыв сертификата/проверка и поиск CRL</span><span class="sxs-lookup"><span data-stu-id="efded-124">Certificate revocation/CRL check and retrieval</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="efded-125">Доступ/DNS/TCP/53</span><span class="sxs-lookup"><span data-stu-id="efded-125">Access/DNS/TCP/53</span></span></p></td>
<td><p><span data-ttu-id="efded-126">Общедоступный IP-адрес пограничной службы доступа пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="efded-126">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="efded-127">Любой</span><span class="sxs-lookup"><span data-stu-id="efded-127">Any</span></span></p></td>
<td><p><span data-ttu-id="efded-128">DNS-запрос по протоколу TCP</span><span class="sxs-lookup"><span data-stu-id="efded-128">DNS query over TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="efded-129">Доступ/DNS/UDP/53</span><span class="sxs-lookup"><span data-stu-id="efded-129">Access/DNS/UDP/53</span></span></p></td>
<td><p><span data-ttu-id="efded-130">Общедоступный IP-адрес пограничной службы доступа пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="efded-130">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="efded-131">Любой</span><span class="sxs-lookup"><span data-stu-id="efded-131">Any</span></span></p></td>
<td><p><span data-ttu-id="efded-132">DNS-запрос по протоколу UDP</span><span class="sxs-lookup"><span data-stu-id="efded-132">DNS query over UDP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="efded-133">АУДИО-И ВИДЕОДАННЫЕ/RTP/TCP/50000-– 999</span><span class="sxs-lookup"><span data-stu-id="efded-133">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="efded-134">IP-адрес службы пограничного сервера аудио-и видеоданных</span><span class="sxs-lookup"><span data-stu-id="efded-134">Edge Server A/V Edge service IP address</span></span></p></td>
<td><p><span data-ttu-id="efded-135">Любой</span><span class="sxs-lookup"><span data-stu-id="efded-135">Any</span></span></p></td>
<td><p><span data-ttu-id="efded-136">Необходимо для Федерации с партнерами, работающими под управлением Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 и Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="efded-136">Required for federating with partners running Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 and Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="efded-137">АУДИО-И ВИДЕОДАННЫЕ/RTP/UDP/50000-– 999</span><span class="sxs-lookup"><span data-stu-id="efded-137">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="efded-138">Общедоступный IP-адрес пограничного сервера аудио-и пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="efded-138">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="efded-139">Любой</span><span class="sxs-lookup"><span data-stu-id="efded-139">Any</span></span></p></td>
<td><p><span data-ttu-id="efded-140">Обязательно только для Федерации с партнерами, работающими под управлением Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="efded-140">Required only for federation with partners running Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="efded-141">АУДИО-И ВИДЕОДАННЫЕ/RTP/TCP/50000-– 999</span><span class="sxs-lookup"><span data-stu-id="efded-141">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="efded-142">Любой</span><span class="sxs-lookup"><span data-stu-id="efded-142">Any</span></span></p></td>
<td><p><span data-ttu-id="efded-143">Общедоступный IP-адрес пограничного сервера аудио-и пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="efded-143">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="efded-144">Обязательно только для Федерации с партнерами, работающими под управлением Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="efded-144">Required only for federation with partners running Office Communications Server 2007</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="efded-145">АУДИО-И ВИДЕОДАННЫЕ/RTP/UDP/50000-– 999</span><span class="sxs-lookup"><span data-stu-id="efded-145">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="efded-146">Любой</span><span class="sxs-lookup"><span data-stu-id="efded-146">Any</span></span></p></td>
<td><p><span data-ttu-id="efded-147">Общедоступный IP-адрес пограничного сервера аудио-и пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="efded-147">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="efded-148">Обязательно только для Федерации с партнерами, работающими под управлением Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="efded-148">Required only for federation with partners running Office Communications Server 2007</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="efded-149">АУДИО-И ВИДЕОДАННЫЕ/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="efded-149">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="efded-150">Общедоступный IP-адрес пограничного сервера аудио-и пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="efded-150">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="efded-151">Любой</span><span class="sxs-lookup"><span data-stu-id="efded-151">Any</span></span></p></td>
<td><p><span data-ttu-id="efded-152">3478 исходящие используется для определения версии пограничного сервера, с которым обменивается данными Lync Server, а также для мультимедийного трафика с пограничного сервера на пограничный сервер.</span><span class="sxs-lookup"><span data-stu-id="efded-152">3478 outbound is used to determine the version of Edge Server that Lync Server is communicating with and also for media traffic from Edge Server-to-Edge Server.</span></span> <span data-ttu-id="efded-153">Обязательно для Федерации с Lync Server 2010, Windows Live Messenger и Office Communications Server 2007 R2, а также при развертывании нескольких пограничных пулов в компании.</span><span class="sxs-lookup"><span data-stu-id="efded-153">Required for federation with Lync Server 2010, Windows Live Messenger, and Office Communications Server 2007 R2, and also if multiple Edge pools are deployed within a company.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="efded-154">АУДИО-И ВИДЕОДАННЫЕ/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="efded-154">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="efded-155">Любой</span><span class="sxs-lookup"><span data-stu-id="efded-155">Any</span></span></p></td>
<td><p><span data-ttu-id="efded-156">Общедоступный IP-адрес пограничного сервера аудио-и пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="efded-156">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="efded-157">STUN/TURN — согласование кандидатов по протоколу UDP/3478</span><span class="sxs-lookup"><span data-stu-id="efded-157">STUN/TURN negotiation of candidates over UDP/3478</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="efded-158">АУДИО-И ВИДЕОДАННЫЕ/STUN, MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="efded-158">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="efded-159">Любой</span><span class="sxs-lookup"><span data-stu-id="efded-159">Any</span></span></p></td>
<td><p><span data-ttu-id="efded-160">Общедоступный IP-адрес пограничного сервера аудио-и пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="efded-160">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="efded-161">STUN/TURN — согласование кандидатов по протоколу TCP/443</span><span class="sxs-lookup"><span data-stu-id="efded-161">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="efded-162">АУДИО-И ВИДЕОДАННЫЕ/STUN, MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="efded-162">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="efded-163">Общедоступный IP-адрес пограничного сервера аудио-и пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="efded-163">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="efded-164">Любой</span><span class="sxs-lookup"><span data-stu-id="efded-164">Any</span></span></p></td>
<td><p><span data-ttu-id="efded-165">STUN/TURN — согласование кандидатов по протоколу TCP/443</span><span class="sxs-lookup"><span data-stu-id="efded-165">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="firewall-summary-for-scaled-consolidated-edge-hardware-load-balanced-internal-interface-node-1-and-node-2"></a><span data-ttu-id="efded-166">Сводная информация по брандмауэрам для масштабируемого консолидированного пограничного сервера, аппаратно сбалансированная нагрузка: внутренний интерфейс — узел 1 и узел 2</span><span class="sxs-lookup"><span data-stu-id="efded-166">Firewall Summary for Scaled Consolidated Edge, Hardware Load Balanced: Internal Interface Node 1 and Node 2</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="efded-167">Роль/протокол/TCP или UDP/порт</span><span class="sxs-lookup"><span data-stu-id="efded-167">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="efded-168">Исходный IP-адрес</span><span class="sxs-lookup"><span data-stu-id="efded-168">Source IP address</span></span></th>
<th><span data-ttu-id="efded-169">Конечный IP-адрес</span><span class="sxs-lookup"><span data-stu-id="efded-169">Destination IP address</span></span></th>
<th><span data-ttu-id="efded-170">Примечания</span><span class="sxs-lookup"><span data-stu-id="efded-170">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="efded-171">XMPP/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="efded-171">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="efded-172">Любой (может быть определен как адрес сервера переднего плана или виртуальный IP-адрес пула переднего плана, на котором запущена служба шлюза XMPP)</span><span class="sxs-lookup"><span data-stu-id="efded-172">Any (can be defined as Front End Server address, or Front End pool virtual IP address running the XMPP Gateway service)</span></span></p></td>
<td><p><span data-ttu-id="efded-173">Внутренний интерфейс пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="efded-173">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="efded-174">Исходящий трафик XMPP из службы шлюза XMPP, работающего на сервере переднего плана или интерфейсном пуле</span><span class="sxs-lookup"><span data-stu-id="efded-174">Outbound XMPP traffic from XMPP Gateway service running on Front End Server or Front End pool</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="efded-175">HTTPS/TCP/4443</span><span class="sxs-lookup"><span data-stu-id="efded-175">HTTPS/TCP/4443</span></span></p></td>
<td><p><span data-ttu-id="efded-176">Любой (может быть определен как IP-адрес сервера переднего плана или пул, в котором хранится центральное хранилище управления)</span><span class="sxs-lookup"><span data-stu-id="efded-176">Any (can be defined as the Front End Server server IP or pool that holds the Central Management store)</span></span></p></td>
<td><p><span data-ttu-id="efded-177">Внутренний интерфейс пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="efded-177">Edge Server Internal interface</span></span></p></td>
<td><p><span data-ttu-id="efded-178">Репликация изменений из центрального хранилища управления на пограничный сервер</span><span class="sxs-lookup"><span data-stu-id="efded-178">Replication of changes from the Central Management store to the Edge Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="efded-179">PSOM/MTLS/TCP/8057</span><span class="sxs-lookup"><span data-stu-id="efded-179">PSOM/MTLS/TCP/8057</span></span></p></td>
<td><p><span data-ttu-id="efded-180">Любой (может быть определен как IP-адрес директора, IP-адрес сервера переднего плана или виртуальный IP-адрес пула)</span><span class="sxs-lookup"><span data-stu-id="efded-180">Any (can be defined as Director IP, Front End Server IP or Pool virtual IP)</span></span></p></td>
<td><p><span data-ttu-id="efded-181">Внутренний интерфейс пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="efded-181">Edge Server Internal interface</span></span></p></td>
<td><p><span data-ttu-id="efded-182">Трафик веб-конференций из внутреннего развертывания во внутренний интерфейс пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="efded-182">Web conferencing traffic from Internal deployment to Internal Edge Server interface</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="efded-183">STUN/MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="efded-183">STUN/MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="efded-184">Любой (может быть определен как IP-адрес директора, IP-адрес сервера переднего плана или виртуальный IP-адрес пула)</span><span class="sxs-lookup"><span data-stu-id="efded-184">Any (can be defined as Director IP, Front End Server IP or Pool virtual IP)</span></span></p></td>
<td><p><span data-ttu-id="efded-185">Внутренний интерфейс пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="efded-185">Edge Server Internal interface</span></span></p></td>
<td><p><span data-ttu-id="efded-186">Предпочтительный путь для передачи аудио-и видеоданных между внутренними и внешними пользователями, устройством для обеспечения связи в филиалах или сервером обеспечения связи в филиалах</span><span class="sxs-lookup"><span data-stu-id="efded-186">Preferred path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="efded-187">STUN/MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="efded-187">STUN/MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="efded-188">Любой (может быть определен как IP-адрес директора, IP-адрес сервера переднего плана или виртуальный IP-адрес пула)</span><span class="sxs-lookup"><span data-stu-id="efded-188">Any (can be defined as Director IP, Front End Server IP or Pool virtual IP)</span></span></p></td>
<td><p><span data-ttu-id="efded-189">Внутренний интерфейс пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="efded-189">Edge Server Internal interface</span></span></p></td>
<td><p><span data-ttu-id="efded-190">Резервный путь для передачи аудио-и видеоданных между внутренними и внешними пользователями, устройства для обеспечения связи в филиалах или сервера для обеспечения связи в филиалах если не удается установить UDP-связь, используется TCP для передачи файлов и общего доступа к рабочему столу</span><span class="sxs-lookup"><span data-stu-id="efded-190">Fallback path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server if UDP communication cannot be established, TCP is used for file transfer and desktop sharing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="efded-191">MTLS/TCP/50001</span><span class="sxs-lookup"><span data-stu-id="efded-191">MTLS/TCP/50001</span></span></p></td>
<td><p><span data-ttu-id="efded-192">Любой</span><span class="sxs-lookup"><span data-stu-id="efded-192">Any</span></span></p></td>
<td><p><span data-ttu-id="efded-193">Внутренний интерфейс пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="efded-193">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="efded-194">Централизованное ведение журналов с помощью команд Командная консоль Lync Server и командлетов службы централизованного ведения журналов, Командная строка ClsController (ClsController.exe) или агента (ClsAgent.exe), а также коллекция журналов</span><span class="sxs-lookup"><span data-stu-id="efded-194">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="efded-195">MTLS/TCP/50002</span><span class="sxs-lookup"><span data-stu-id="efded-195">MTLS/TCP/50002</span></span></p></td>
<td><p><span data-ttu-id="efded-196">Любой</span><span class="sxs-lookup"><span data-stu-id="efded-196">Any</span></span></p></td>
<td><p><span data-ttu-id="efded-197">Внутренний интерфейс пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="efded-197">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="efded-198">Централизованное ведение журналов с помощью команд Командная консоль Lync Server и командлетов службы централизованного ведения журналов, Командная строка ClsController (ClsController.exe) или агента (ClsAgent.exe), а также коллекция журналов</span><span class="sxs-lookup"><span data-stu-id="efded-198">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="efded-199">MTLS/TCP/50003</span><span class="sxs-lookup"><span data-stu-id="efded-199">MTLS/TCP/50003</span></span></p></td>
<td><p><span data-ttu-id="efded-200">Любой</span><span class="sxs-lookup"><span data-stu-id="efded-200">Any</span></span></p></td>
<td><p><span data-ttu-id="efded-201">Внутренний интерфейс пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="efded-201">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="efded-202">Централизованное ведение журналов с помощью команд Командная консоль Lync Server и командлетов службы централизованного ведения журналов, Командная строка ClsController (ClsController.exe) или агента (ClsAgent.exe), а также коллекция журналов</span><span class="sxs-lookup"><span data-stu-id="efded-202">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="efded-203">Для аппаратных подсистем балансировки нагрузки предъявляются особые требования при развертывании для обеспечения доступности и балансировки нагрузки для Lync Server.</span><span class="sxs-lookup"><span data-stu-id="efded-203">Hardware load balancers have specific requirements when deployed to provide availability and load balancing for Lync Server.</span></span> <span data-ttu-id="efded-204">Эти требования указаны в следующих таблицах и на изображении.</span><span class="sxs-lookup"><span data-stu-id="efded-204">The requirements are defined in the following figure and tables.</span></span> <span data-ttu-id="efded-205">Сторонние поставщики могут использовать различную терминологию для требований, приведенных здесь.</span><span class="sxs-lookup"><span data-stu-id="efded-205">Third party vendors may use different terminology for the requirements defined here.</span></span> <span data-ttu-id="efded-206">Необходимо сопоставить требования Lync Server с функциями и параметрами конфигурации, предоставляемыми поставщиком аппаратной балансировки нагрузки.</span><span class="sxs-lookup"><span data-stu-id="efded-206">It will be necessary to map the requirements of Lync Server to the features and configuration options provided by your hardware load balancer vendor.</span></span>

<span data-ttu-id="efded-207">При настройке аппаратных балансировщиков нагрузки необходимо учитывать следующие требования.</span><span class="sxs-lookup"><span data-stu-id="efded-207">When configuring hardware load balancers, consider the following requirements:</span></span>

  - <span data-ttu-id="efded-208">Для службы пограничного сервера доступа и пограничной службы веб-конференций можно настроить трансляцию адресов исходной сети (SNAT) на аппаратный балансировщик нагрузки (HLB).</span><span class="sxs-lookup"><span data-stu-id="efded-208">Source Network Address Translation (SNAT) can be configured on the hardware load balancer (HLB) for Access Edge service and Web Conferencing Edge service</span></span>

  - <span data-ttu-id="efded-209">Служба SNAT не может быть настроена для пограничной службы аудио-и видеоданных — пограничная служба аудио-и видеоданных должна отвечать с реальным адресом сервера, а не с виртуальным IP-адресом HLB (VIP) для простого обхода протокола UDP over NAT (STUN)/траверсал с помощью ретрансляции NAT ()/федератион (ФТУРН) для правильной работы</span><span class="sxs-lookup"><span data-stu-id="efded-209">SNAT cannot be configured on the A/V Edge service– the A/V Edge service must respond with the real server address, not the HLB virtual IP (VIP), for simple traversal of UDP over NAT (STUN)/traversal using relay NAT (TURN)/federation TURN (FTURN) to work properly</span></span>
    
      - <span data-ttu-id="efded-210">Если клиент отправляет запрос на HLB, ответ должен возвращаться из виртуального IP-адреса HLB</span><span class="sxs-lookup"><span data-stu-id="efded-210">If the client sends a request to the HLB, the response must come back from the HLB VIP</span></span>
    
      - <span data-ttu-id="efded-211">Если клиент отправляет запрос на пограничный сервер, ответ должен быть получен от пограничного IP-адреса.</span><span class="sxs-lookup"><span data-stu-id="efded-211">If the client sends a request to the Edge, the response must come back from the Edge IP</span></span>

  - <span data-ttu-id="efded-212">Общедоступные IP-адреса используются в каждом интерфейсе сервера и виртуальных IP-адресах HLB, а требования к общедоступным IP-адресам — N + 1, где есть общедоступный IP-адрес для каждого сервера реального сервера и один для каждого IP-адреса HLB.</span><span class="sxs-lookup"><span data-stu-id="efded-212">Public IP addresses are used on each server interface and on the VIPs of the HLB, and your public IP address requirements are N+1, where there is a public IP address for each real server interface and one for each HLB VIP.</span></span> <span data-ttu-id="efded-213">При наличии 2 пограничных серверов в пуле это приводит к 9 общедоступным IP-адресам, где 3 используются для виртуальных IP-адресов, и по одному для каждого интерфейса пограничного сервера (всего до шести для серверов).</span><span class="sxs-lookup"><span data-stu-id="efded-213">Where you have 2 Edge servers in the pool, this results in 9 public IP addresses, where 3 are used for the HLB VIPs, and one for each Edge server interface (a total of six for the servers)</span></span>

  - <span data-ttu-id="efded-214">Для пограничной службы доступа и пограничной службы веб-конференций (и с помощью NAT в HLB) клиент обращается к ВИРТУАЛЬНОЙ IP-сети, IP-адрес источника изменяется с клиента на его IP-адрес.</span><span class="sxs-lookup"><span data-stu-id="efded-214">For the Access Edge service and Web Conferencing Edge service, (and using NAT on the HLB) the client contacts the VIP, the VIP changes the source IP address from the client to its own IP address.</span></span> <span data-ttu-id="efded-215">Интерфейс сервера передает обратный адрес на виртуальный IP-адрес, который заменяет IP-адрес интерфейса сервера на исходный адрес и отправляет пакет клиенту</span><span class="sxs-lookup"><span data-stu-id="efded-215">The server interface addresses the return address to the VIP, the VIP changes the source address from the server interface IP address and sends the packet to the client</span></span>

  - <span data-ttu-id="efded-216">Для пограничной службы аудио-и видеоданных виртуальный IP-адрес не должен измениться, а фактический адрес сервера возвращается клиенту напрямую — невозможно настроить NAT на HLB для трафика AV</span><span class="sxs-lookup"><span data-stu-id="efded-216">For the A/V Edge service, the VIP must NOT change the source IP address, and the real server address is returned to the client directly – you cannot configure NAT on the HLB for AV traffic</span></span>
    
      - <span data-ttu-id="efded-217">Если клиент отправляет запрос на HLB VIP, ответ должен возвращаться из виртуального IP-адреса HLB</span><span class="sxs-lookup"><span data-stu-id="efded-217">If the client sends a request to the HLB VIP, the response must come back from the HLB VIP</span></span>
    
      - <span data-ttu-id="efded-218">Если клиент отправляет запрос на пограничный IP-адрес, ответ должен возвращаться от пограничного IP-адреса.</span><span class="sxs-lookup"><span data-stu-id="efded-218">If the client sends a request to the Edge IP, the response must come back from the Edge IP</span></span>

  - <span data-ttu-id="efded-219">Для трафика аудио и видео внешний брандмауэр будет сохранять реальный общедоступный IP-адрес сервера для всех пакетов</span><span class="sxs-lookup"><span data-stu-id="efded-219">For AV, the external firewall will retain the real server public IP address for all packets</span></span>

  - <span data-ttu-id="efded-220">После установки клиент для пограничной службы аудио-и видеосвязи становится реальным сервером, а не HLB.</span><span class="sxs-lookup"><span data-stu-id="efded-220">Once established, client to A/V Edge service communication is to the real server, not the HLB</span></span>

  - <span data-ttu-id="efded-221">Внутренняя граница для внутренних серверов и клиентов должна маршрутизироваться; постоянные маршруты настраиваются для всех внутренних сетей, в которых размещаются серверы или клиенты</span><span class="sxs-lookup"><span data-stu-id="efded-221">Internal edge to internal servers and clients must be routed, and persistent routes are set for all internal networks that host servers or clients</span></span>

  - <span data-ttu-id="efded-222">Виртуальный IP-адрес пограничной службы доступа HLB будет использоваться в качестве шлюза по умолчанию для каждого интерфейса пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="efded-222">The HLB Access Edge service VIP will act as the default gateway for each Edge server interface</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="efded-223">Для получения дополнительных сведений о планировании и функциональных возможностях NAT обратитесь к разделу <A href="lync-server-2013-hardware-load-balancer-requirements.md">требования к оборудованию балансировки нагрузки для Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="efded-223">For further information on NAT planning and functionality, please refer to <A href="lync-server-2013-hardware-load-balancer-requirements.md">Hardware load balancer requirements for Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="efded-224">![Сведения о портах и протоколах пограничного сервера](images/Gg398739.1c193b80-98ab-4d59-a854-dbfdb5e209e2(OCS.15).jpg "Сведения о портах и протоколах пограничного сервера")</span><span class="sxs-lookup"><span data-stu-id="efded-224">![Edge Server ports and protocols details](images/Gg398739.1c193b80-98ab-4d59-a854-dbfdb5e209e2(OCS.15).jpg "Edge Server ports and protocols details")</span></span>

### <a name="external-port-settings-required-for-scaled-consolidated-edge-hardware-load-balanced-external-interface-virtual-ips"></a><span data-ttu-id="efded-225">Параметры внешнего порта, необходимые для масштабируемого консолидированного пограничного сервера, аппаратно сбалансированная нагрузка: виртуальные IP-адреса внешнего интерфейса</span><span class="sxs-lookup"><span data-stu-id="efded-225">External Port Settings Required for Scaled Consolidated Edge, Hardware Load Balanced: External Interface Virtual IPs</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="efded-226">Роль/протокол/TCP или UDP/порт</span><span class="sxs-lookup"><span data-stu-id="efded-226">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="efded-227">Исходный IP-адрес</span><span class="sxs-lookup"><span data-stu-id="efded-227">Source IP address</span></span></th>
<th><span data-ttu-id="efded-228">Конечный IP-адрес</span><span class="sxs-lookup"><span data-stu-id="efded-228">Destination IP address</span></span></th>
<th><span data-ttu-id="efded-229">Примечания</span><span class="sxs-lookup"><span data-stu-id="efded-229">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="efded-230">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="efded-230">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="efded-231">Любой</span><span class="sxs-lookup"><span data-stu-id="efded-231">Any</span></span></p></td>
<td><p><span data-ttu-id="efded-232">Прокси-служба XMPP (общий IP-адрес с пограничной службой доступа)</span><span class="sxs-lookup"><span data-stu-id="efded-232">XMPP Proxy service (shares IP address with Access Edge service)</span></span></p></td>
<td><p><span data-ttu-id="efded-233">Служба прокси XMPP принимает трафик от контактов XMPP в определенных федерациях XMPP</span><span class="sxs-lookup"><span data-stu-id="efded-233">XMPP Proxy service accepts traffic from XMPP contacts in defined XMPP federations</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="efded-234">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="efded-234">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="efded-235">Прокси-служба XMPP (общий IP-адрес с пограничной службой доступа)</span><span class="sxs-lookup"><span data-stu-id="efded-235">XMPP Proxy service (shares IP address with Access Edge service)</span></span></p></td>
<td><p><span data-ttu-id="efded-236">Любой</span><span class="sxs-lookup"><span data-stu-id="efded-236">Any</span></span></p></td>
<td><p><span data-ttu-id="efded-237">Прокси-служба XMPP отправляет трафик контактам XMPP в определенных федерациях XMPP</span><span class="sxs-lookup"><span data-stu-id="efded-237">XMPP Proxy service sends traffic to XMPP contacts in defined XMPP federations</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="efded-238">/TCP/443 доступа и SIP (TLS)</span><span class="sxs-lookup"><span data-stu-id="efded-238">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="efded-239">Любой</span><span class="sxs-lookup"><span data-stu-id="efded-239">Any</span></span></p></td>
<td><p><span data-ttu-id="efded-240">Общедоступный виртуальный IP-адрес пограничной службы доступа</span><span class="sxs-lookup"><span data-stu-id="efded-240">Access Edge service public VIP address</span></span></p></td>
<td><p><span data-ttu-id="efded-241">Трафик SIP «клиент-сервер» для доступа внешних пользователей</span><span class="sxs-lookup"><span data-stu-id="efded-241">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="efded-242">Доступ/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="efded-242">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="efded-243">Любой</span><span class="sxs-lookup"><span data-stu-id="efded-243">Any</span></span></p></td>
<td><p><span data-ttu-id="efded-244">Общедоступный виртуальный IP-адрес пограничной службы доступа</span><span class="sxs-lookup"><span data-stu-id="efded-244">Access Edge service public VIP address</span></span></p></td>
<td><p><span data-ttu-id="efded-245">Передача сигналов SIP, Федеративные и общедоступные службы обмена мгновенными сообщениями с помощью SIP</span><span class="sxs-lookup"><span data-stu-id="efded-245">SIP signaling, federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="efded-246">Доступ/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="efded-246">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="efded-247">Общедоступный виртуальный IP-адрес пограничной службы доступа</span><span class="sxs-lookup"><span data-stu-id="efded-247">Access Edge service public VIP address</span></span></p></td>
<td><p><span data-ttu-id="efded-248">Федеративный партнер</span><span class="sxs-lookup"><span data-stu-id="efded-248">Federated partner</span></span></p></td>
<td><p><span data-ttu-id="efded-249">Передача сигналов SIP, Федеративные и общедоступные службы обмена мгновенными сообщениями с помощью SIP</span><span class="sxs-lookup"><span data-stu-id="efded-249">SIP signaling, federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="efded-250">Веб-конференции/PSOM (TLS)/TCP/443</span><span class="sxs-lookup"><span data-stu-id="efded-250">Web Conferencing/PSOM(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="efded-251">Любой</span><span class="sxs-lookup"><span data-stu-id="efded-251">Any</span></span></p></td>
<td><p><span data-ttu-id="efded-252">Общедоступный виртуальный IP-адрес пограничного сервера веб-конференций пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="efded-252">Edge Server Web Conferencing Edge service public VIP address</span></span></p></td>
<td><p><span data-ttu-id="efded-253">Устройство для веб-конференций</span><span class="sxs-lookup"><span data-stu-id="efded-253">Web Conferencing media</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="efded-254">АУДИО-И ВИДЕОДАННЫЕ/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="efded-254">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="efded-255">Любой</span><span class="sxs-lookup"><span data-stu-id="efded-255">Any</span></span></p></td>
<td><p><span data-ttu-id="efded-256">Общедоступный виртуальный IP-адрес пограничного сервера аудио-и пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="efded-256">Edge Server A/V Edge service public VIP address</span></span></p></td>
<td><p><span data-ttu-id="efded-257">STUN/TURN — согласование кандидатов по протоколу UDP/3478</span><span class="sxs-lookup"><span data-stu-id="efded-257">STUN/TURN negotiation of candidates over UDP/3478</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="efded-258">АУДИО-И ВИДЕОДАННЫЕ/STUN, MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="efded-258">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="efded-259">Любой</span><span class="sxs-lookup"><span data-stu-id="efded-259">Any</span></span></p></td>
<td><p><span data-ttu-id="efded-260">Общедоступный виртуальный IP-адрес пограничного сервера аудио-и пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="efded-260">Edge Server A/V Edge service public VIP address</span></span></p></td>
<td><p><span data-ttu-id="efded-261">STUN/TURN — согласование кандидатов по протоколу TCP/443</span><span class="sxs-lookup"><span data-stu-id="efded-261">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="firewall-summary-for-scaled-consolidated-edge-hardware-load-balanced-internal-interface-virtual-ips"></a><span data-ttu-id="efded-262">Сводная информация по брандмауэрам для масштабируемого консолидированного пограничного сервера, аппаратно сбалансированная нагрузка: внутренний интерфейс — виртуальные IP-адреса</span><span class="sxs-lookup"><span data-stu-id="efded-262">Firewall Summary for Scaled Consolidated Edge, Hardware Load Balanced: Internal Interface Virtual IPs</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="efded-263">Роль/протокол/TCP или UDP/порт</span><span class="sxs-lookup"><span data-stu-id="efded-263">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="efded-264">Исходный IP-адрес</span><span class="sxs-lookup"><span data-stu-id="efded-264">Source IP address</span></span></th>
<th><span data-ttu-id="efded-265">Конечный IP-адрес</span><span class="sxs-lookup"><span data-stu-id="efded-265">Destination IP address</span></span></th>
<th><span data-ttu-id="efded-266">Примечания</span><span class="sxs-lookup"><span data-stu-id="efded-266">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="efded-267">Доступ/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="efded-267">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="efded-268">Любой (может быть определен как директор, виртуальный IP-адрес пула директоров, сервер переднего плана или виртуальный IP-адрес пула переднего плана)</span><span class="sxs-lookup"><span data-stu-id="efded-268">Any (can be defined as Director, Director pool virtual IP address, Front End Server or Front End pool virtual IP address)</span></span></p></td>
<td><p><span data-ttu-id="efded-269">Интерфейс внутреннего виртуального IP-адреса пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="efded-269">Edge Server Internal VIP interface</span></span></p></td>
<td><p><span data-ttu-id="efded-270">Исходящий трафик SIP (от директоров, виртуальный IP-адрес пула директоров, виртуальный IP-адрес сервера переднего плана или пула переднего плана) на внутренний пограничный IP-адрес.</span><span class="sxs-lookup"><span data-stu-id="efded-270">Outbound SIP traffic (from Director, Director pool virtual IP address, Front End Server or Front End pool virtual IP address)to Internal Edge VIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="efded-271">Доступ/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="efded-271">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="efded-272">Интерфейс внутреннего виртуального IP-адреса пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="efded-272">Edge Server Internal VIP interface</span></span></p></td>
<td><p><span data-ttu-id="efded-273">Любой (может быть определен как директор, виртуальный IP-адрес пула директоров, сервер переднего плана или виртуальный IP-адрес пула переднего плана)</span><span class="sxs-lookup"><span data-stu-id="efded-273">Any (can be defined as Director, Director pool virtual IP address, Front End Server or Front End pool virtual IP address)</span></span></p></td>
<td><p><span data-ttu-id="efded-274">Входящий трафик SIP (в директоре, виртуальный IP-адрес пула директоров, виртуальный IP-адрес сервера переднего плана или пула переднего плана) от внутреннего интерфейса пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="efded-274">Inbound SIP traffic (to Director, Director pool virtual IP address, Front End Server or Front End pool virtual IP address) from Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="efded-275">SIP/MTLS/TCP/5062</span><span class="sxs-lookup"><span data-stu-id="efded-275">SIP/MTLS/TCP/5062</span></span></p></td>
<td><p><span data-ttu-id="efded-276">Любой (может быть определен как IP-адрес сервера переднего плана или IP-адрес пула переднего плана или любое устройство для обеспечения связи в филиале или как сервер для обеспечения связи в филиалах с помощью этого пограничного сервера)</span><span class="sxs-lookup"><span data-stu-id="efded-276">Any (can be defined as Front End Server IP address, or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server)</span></span></p></td>
<td><p><span data-ttu-id="efded-277">Интерфейс внутреннего виртуального IP-адреса пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="efded-277">Edge Server Internal VIP interface</span></span></p></td>
<td><p><span data-ttu-id="efded-278">Проверка подлинности пользователей и подлинности (служба проверки подлинности A/V) с IP-адреса сервера переднего плана или интерфейсного пула или любого устройства для обеспечения связи в филиалах или сервера обеспечения связи в филиалах с помощью этого пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="efded-278">Authentication of A/V users (A/V authentication service) from Front End Server or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="efded-279">STUN/MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="efded-279">STUN/MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="efded-280">Любой</span><span class="sxs-lookup"><span data-stu-id="efded-280">Any</span></span></p></td>
<td><p><span data-ttu-id="efded-281">Интерфейс внутреннего виртуального IP-адреса пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="efded-281">Edge Server Internal VIP interface</span></span></p></td>
<td><p><span data-ttu-id="efded-282">Предпочитаемый путь передачи аудио/видео между внутренними и внешними пользователями</span><span class="sxs-lookup"><span data-stu-id="efded-282">Preferred path for A/V media transfer between internal and external users</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="efded-283">STUN/MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="efded-283">STUN/MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="efded-284">Любой</span><span class="sxs-lookup"><span data-stu-id="efded-284">Any</span></span></p></td>
<td><p><span data-ttu-id="efded-285">Интерфейс внутреннего виртуального IP-адреса пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="efded-285">Edge Server Internal VIP interface</span></span></p></td>
<td><p><span data-ttu-id="efded-286">Резервный путь для передачи аудио/видео между внутренними и внешними пользователями в случае, если не удается установить подключение UDP; для передачи файлов и общего доступа к рабочему столу используется TCP</span><span class="sxs-lookup"><span data-stu-id="efded-286">Fallback path for A/V media transfer between internal and external users if UDP communication cannot be established, TCP is used for file transfer and desktop sharing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="efded-287">STUN/MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="efded-287">STUN/MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="efded-288">Интерфейс внутреннего виртуального IP-адреса пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="efded-288">Edge Server Internal VIP interface</span></span></p></td>
<td><p><span data-ttu-id="efded-289">Любой</span><span class="sxs-lookup"><span data-stu-id="efded-289">Any</span></span></p></td>
<td><p><span data-ttu-id="efded-290">Резервный путь для передачи аудио/видео между внутренними и внешними пользователями в случае, если не удается установить подключение UDP; для передачи файлов и общего доступа к рабочему столу используется TCP</span><span class="sxs-lookup"><span data-stu-id="efded-290">Fallback path for A/V media transfer between internal and external users if UDP communication cannot be established, TCP is used for file transfer and desktop sharing</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

