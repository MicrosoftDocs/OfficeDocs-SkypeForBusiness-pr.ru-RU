---
title: 'Сводка по портам: SIP, Федерация XMPP и общедоступная служба обмена мгновенными сообщениями'
description: 'Сводка по портам: SIP, Федерация XMPP и общедоступные мгновенные сообщения.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Port summary - SIP, XMPP federation, and public instant messaging
ms:assetid: ab05bdd6-e9b0-4b1b-9dd9-29ab88e8befe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ618373(v=OCS.15)
ms:contentKeyID: 49105660
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7c58dbf7bdd56b4678d56f96a11332219bb40c17
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566363"
---
# <a name="port-summary---sip-xmpp-federation-and-public-instant-messaging-in-lync-server-2013"></a><span data-ttu-id="e4cbc-103">Сводка по портам: SIP, Федерация XMPP и общедоступные службы обмена мгновенными сообщениями в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e4cbc-103">Port summary - SIP, XMPP federation, and public instant messaging in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e4cbc-104">_**Последнее изменение темы:** 2013-03-15_</span><span class="sxs-lookup"><span data-stu-id="e4cbc-104">_**Topic Last Modified:** 2013-03-15_</span></span>

<span data-ttu-id="e4cbc-105">Требования к портам, протоколам и брандмауэрам для Федерации с Microsoft Lync Server 2013, Lync Server 2010 и Office Communications Server схожи с развернутым пограничным сервером.</span><span class="sxs-lookup"><span data-stu-id="e4cbc-105">Port, protocol and firewall requirements for federation with Microsoft Lync Server 2013, Lync Server 2010 and Office Communications Server are similar to those for the deployed Edge Server.</span></span> <span data-ttu-id="e4cbc-106">Клиенты инициируют связь с пограничной службой доступа через TLS/SIP/TCP 443.</span><span class="sxs-lookup"><span data-stu-id="e4cbc-106">Clients initiate communication with the Access Edge service over TLS/SIP/TCP 443.</span></span> <span data-ttu-id="e4cbc-107">Федеративные партнеры тем не менее инициируют связь с службой пограничного доступа через MTLS/SIP/TCP 5061.</span><span class="sxs-lookup"><span data-stu-id="e4cbc-107">Federated partners however, will initiate communications to the Access Edge service over MTLS/SIP/TCP 5061.</span></span>

<span data-ttu-id="e4cbc-108">Чтобы настроить брандмауэр для поддержки портов и протоколов, необходимых для поддержки подключения к общедоступным службам обмена мгновенными сообщениями, сначала обратите внимание на то, что SIP/MTLS/TCP 5061 является двунаправленной учетной записью для связи с контактами в общедоступном поставщике IM для связи с клиентами Lync</span><span class="sxs-lookup"><span data-stu-id="e4cbc-108">To configure your firewall for ports and protocols necessary to support public instant messaging connectivity, first note that SIP/MTLS/TCP 5061 is bidirectional to account for the ability of contacts in the public IM provider to contact Lync clients, or for Lync to contact public IM contacts.</span></span>

<span data-ttu-id="e4cbc-109">Windows Live Messenger может участвовать в аудио-и видеосвязи с клиентами Lync.</span><span class="sxs-lookup"><span data-stu-id="e4cbc-109">Windows Live Messenger can participate in audio/video communications with Lync clients.</span></span> <span data-ttu-id="e4cbc-110">Эти учетные записи для похожих портов брандмауэра и протоколов, которые, как правило, находятся на брандмауэре для поддержки клиентов Lync как внешних пользователей.</span><span class="sxs-lookup"><span data-stu-id="e4cbc-110">This accounts for the very similar firewall port and protocol configuration that you would typically have on the firewall to support Lync clients as external users.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="e4cbc-111">Lync — это мощное средство для связи между организациями и пользователями мира.</span><span class="sxs-lookup"><span data-stu-id="e4cbc-111">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="e4cbc-112">Для Федерации с Windows Live Messenger не требуется дополнительных лицензий на пользователей и устройств, не относящихся к стандартной клиентской лицензии Lync (CAL).</span><span class="sxs-lookup"><span data-stu-id="e4cbc-112">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard Client Access License (CAL).</span></span> <span data-ttu-id="e4cbc-113">В этот список будет добавлена Федерация Skype, что позволит пользователям Lync достичь сотен миллионов людей с помощью обмена мгновенными сообщениями и голосовой связью.</span><span class="sxs-lookup"><span data-stu-id="e4cbc-113">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people with IM and voice.</span></span><BR><span data-ttu-id="e4cbc-114">Федерация с контактами клиентов Messenger официально заканчивается 15 марта 2013, за исключением континентальная Китая.</span><span class="sxs-lookup"><span data-stu-id="e4cbc-114">Federation with Messenger client contacts will officially end on March 15, 2013, except for mainland China.</span></span> <span data-ttu-id="e4cbc-115">Skype станет клиентом Федерации для федеративных пользователей, которые ранее использовали Messenger.</span><span class="sxs-lookup"><span data-stu-id="e4cbc-115">Skype will become the federation client for federated users who previously used Messenger.</span></span>



</div>

<span data-ttu-id="e4cbc-116">Порты и протоколы, определенные для прокси-сервера Extensible Messaging and Presence Protocol (XMPP), развернутого на пограничном сервере, разрешают обмен данными между федеративным партнером XMPP на пограничный сервер, а также позволяет осуществлять обмен данными от пограничного сервера к федеративным партнеру XMPP.</span><span class="sxs-lookup"><span data-stu-id="e4cbc-116">The ports and protocols defined for the extensible messaging and presence protocol (XMPP) proxy deployed on the Edge Server allow communications from the XMPP federated partner to the Edge Server, and also allows communication from your Edge Server to the XMPP federated partner.</span></span> <span data-ttu-id="e4cbc-117">Кроме того, правило определяется на внутреннем брандмауэре от сервера переднего плана или интерфейсного пула до пограничного сервера или пограничного пула.</span><span class="sxs-lookup"><span data-stu-id="e4cbc-117">A rule is also defined on the internal-facing firewall from the Front End Server or Front End pool to the Edge Server or Edge pool.</span></span>

<div>

## <a name="firewall-summary---sip-federation"></a><span data-ttu-id="e4cbc-118">Сводка по брандмауэру: Федерация SIP</span><span class="sxs-lookup"><span data-stu-id="e4cbc-118">Firewall Summary - SIP Federation</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e4cbc-119">Роль/протокол/TCP или UDP/порт</span><span class="sxs-lookup"><span data-stu-id="e4cbc-119">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="e4cbc-120">Исходный IP-адрес</span><span class="sxs-lookup"><span data-stu-id="e4cbc-120">Source IP address</span></span></th>
<th><span data-ttu-id="e4cbc-121">Конечный IP-адрес</span><span class="sxs-lookup"><span data-stu-id="e4cbc-121">Destination IP address</span></span></th>
<th><span data-ttu-id="e4cbc-122">Примечания</span><span class="sxs-lookup"><span data-stu-id="e4cbc-122">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e4cbc-123">Доступ/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="e4cbc-123">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="e4cbc-124">Общедоступный IP-адрес пограничной службы доступа</span><span class="sxs-lookup"><span data-stu-id="e4cbc-124">Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="e4cbc-125">Любой</span><span class="sxs-lookup"><span data-stu-id="e4cbc-125">Any</span></span></p></td>
<td><p><span data-ttu-id="e4cbc-126">Для федеративного подключения и подключения к общедоступным службам обмена мгновенными сообщениями с помощью SIP</span><span class="sxs-lookup"><span data-stu-id="e4cbc-126">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary--public-instant-messaging-connectivity"></a><span data-ttu-id="e4cbc-127">Сводка по брандмауэру — связь с общедоступной службой обмена мгновенными сообщениями</span><span class="sxs-lookup"><span data-stu-id="e4cbc-127">Firewall Summary – Public Instant Messaging Connectivity</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e4cbc-128">Роль/протокол/TCP или UDP/порт</span><span class="sxs-lookup"><span data-stu-id="e4cbc-128">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="e4cbc-129">Исходный IP-адрес</span><span class="sxs-lookup"><span data-stu-id="e4cbc-129">Source IP address</span></span></th>
<th><span data-ttu-id="e4cbc-130">Конечный IP-адрес</span><span class="sxs-lookup"><span data-stu-id="e4cbc-130">Destination IP address</span></span></th>
<th><span data-ttu-id="e4cbc-131">Примечания</span><span class="sxs-lookup"><span data-stu-id="e4cbc-131">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e4cbc-132">Доступ/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="e4cbc-132">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="e4cbc-133">Партнеры по связи с общедоступной службой обмена мгновенными сообщениями</span><span class="sxs-lookup"><span data-stu-id="e4cbc-133">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="e4cbc-134">Интерфейс доступа пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="e4cbc-134">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="e4cbc-135">Для федеративного и общедоступной службы обмена мгновенными сообщениями, использующей SIP.</span><span class="sxs-lookup"><span data-stu-id="e4cbc-135">For federated and public IM connectivity that use SIP.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e4cbc-136">Доступ/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="e4cbc-136">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="e4cbc-137">Интерфейс доступа пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="e4cbc-137">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="e4cbc-138">Партнеры по связи с общедоступной службой обмена мгновенными сообщениями</span><span class="sxs-lookup"><span data-stu-id="e4cbc-138">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="e4cbc-139">Для федеративного и общедоступной службы обмена мгновенными сообщениями, использующей SIP.</span><span class="sxs-lookup"><span data-stu-id="e4cbc-139">For federated and public IM connectivity that use SIP.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e4cbc-140">/TCP/443 доступа и SIP (TLS)</span><span class="sxs-lookup"><span data-stu-id="e4cbc-140">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="e4cbc-141">Клиенты</span><span class="sxs-lookup"><span data-stu-id="e4cbc-141">Clients</span></span></p></td>
<td><p><span data-ttu-id="e4cbc-142">Интерфейс доступа пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="e4cbc-142">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="e4cbc-143">Трафик SIP от клиента к серверу для доступа внешних пользователей.</span><span class="sxs-lookup"><span data-stu-id="e4cbc-143">Client-to-server SIP traffic for external user access.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e4cbc-144">АУДИО-И ВИДЕОДАННЫЕ/RTP/TCP/50000-– 999</span><span class="sxs-lookup"><span data-stu-id="e4cbc-144">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="e4cbc-145">Интерфейс доступа пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="e4cbc-145">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="e4cbc-146">Клиенты Live Messenger</span><span class="sxs-lookup"><span data-stu-id="e4cbc-146">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="e4cbc-147">Используется для сеансов аудио- и видеоконференций с использованием Windows Live Messenger, если настроена связь с общедоступной службой обмена мгновенными сообщениями.</span><span class="sxs-lookup"><span data-stu-id="e4cbc-147">Used for A/V sessions with Windows Live Messenger if public IM connectivity is configured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e4cbc-148">АУДИО-И ВИДЕОДАННЫЕ/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="e4cbc-148">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="e4cbc-149">Интерфейс доступа пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="e4cbc-149">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="e4cbc-150">Клиенты Live Messenger</span><span class="sxs-lookup"><span data-stu-id="e4cbc-150">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="e4cbc-151">Необходимо для связи с общедоступной службой обмена мгновенными сообщениями с Windows Live Messenger.</span><span class="sxs-lookup"><span data-stu-id="e4cbc-151">Required for public IM connectivity with Windows Live Messenger.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e4cbc-152">АУДИО-И ВИДЕОДАННЫЕ/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="e4cbc-152">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="e4cbc-153">Клиенты Live Messenger</span><span class="sxs-lookup"><span data-stu-id="e4cbc-153">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="e4cbc-154">Интерфейс доступа пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="e4cbc-154">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="e4cbc-155">Необходимо для связи с общедоступной службой обмена мгновенными сообщениями с Windows Live Messenger.</span><span class="sxs-lookup"><span data-stu-id="e4cbc-155">Required for public IM connectivity with Windows Live Messenger.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary---extensible-messaging-and-presence-protocol-xmpp"></a><span data-ttu-id="e4cbc-156">Сводка по брандмауэру: расширенный протокол обмена сообщениями и присутствия (XMPP)</span><span class="sxs-lookup"><span data-stu-id="e4cbc-156">Firewall Summary - Extensible Messaging and Presence Protocol (XMPP)</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e4cbc-157">Протокол/TCP или UDP/порт</span><span class="sxs-lookup"><span data-stu-id="e4cbc-157">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="e4cbc-158">Источник (IP-адрес)</span><span class="sxs-lookup"><span data-stu-id="e4cbc-158">Source (IP address)</span></span></th>
<th><span data-ttu-id="e4cbc-159">Назначение (IP-адрес)</span><span class="sxs-lookup"><span data-stu-id="e4cbc-159">Destination (IP address)</span></span></th>
<th><span data-ttu-id="e4cbc-160">Comments</span><span class="sxs-lookup"><span data-stu-id="e4cbc-160">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e4cbc-161">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="e4cbc-161">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="e4cbc-162">Любой</span><span class="sxs-lookup"><span data-stu-id="e4cbc-162">Any</span></span></p></td>
<td><p><span data-ttu-id="e4cbc-163">IP-адрес интерфейса пограничного сервера доступа</span><span class="sxs-lookup"><span data-stu-id="e4cbc-163">Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="e4cbc-164">Стандартный порт для связи "сервер-сервер" через XMPP.</span><span class="sxs-lookup"><span data-stu-id="e4cbc-164">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="e4cbc-165">Разрешает связь с прокси-сервером пограничного сервера XMPP от федеративных партнеров XMPP</span><span class="sxs-lookup"><span data-stu-id="e4cbc-165">Allows communication to the Edge Server XMPP proxy from federated XMPP partners</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e4cbc-166">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="e4cbc-166">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="e4cbc-167">IP-адрес интерфейса пограничного сервера доступа</span><span class="sxs-lookup"><span data-stu-id="e4cbc-167">Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="e4cbc-168">Любой</span><span class="sxs-lookup"><span data-stu-id="e4cbc-168">Any</span></span></p></td>
<td><p><span data-ttu-id="e4cbc-169">Стандартный порт для связи "сервер-сервер" через XMPP.</span><span class="sxs-lookup"><span data-stu-id="e4cbc-169">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="e4cbc-170">Разрешает обмен данными от прокси-сервера пограничного сервера XMPP к федеративным партнерам XMPP</span><span class="sxs-lookup"><span data-stu-id="e4cbc-170">Allows communication from the Edge Server XMPP proxy to federated XMPP partners</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e4cbc-171">XMPP/MTLS/23456</span><span class="sxs-lookup"><span data-stu-id="e4cbc-171">XMPP/MTLS/23456</span></span></p></td>
<td><p><span data-ttu-id="e4cbc-172">Любой</span><span class="sxs-lookup"><span data-stu-id="e4cbc-172">Any</span></span></p></td>
<td><p><span data-ttu-id="e4cbc-173">IP-адрес внутреннего интерфейса пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="e4cbc-173">Internal Edge Server Interface IP</span></span></p></td>
<td><p><span data-ttu-id="e4cbc-174">Внутренний трафик XMPP от шлюза XMPP на сервере переднего плана или интерфейсном пуле к пограничным серверам</span><span class="sxs-lookup"><span data-stu-id="e4cbc-174">Internal XMPP traffic from the XMPP Gateway on the Front End Server or Front End pool to the Edge Server</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a><span data-ttu-id="e4cbc-175">См. также</span><span class="sxs-lookup"><span data-stu-id="e4cbc-175">See Also</span></span>


[<span data-ttu-id="e4cbc-176">Сценарии доступа внешних пользователей в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e4cbc-176">Scenarios for external user access in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-external-user-access.md)  
[<span data-ttu-id="e4cbc-177">Определение требований к внешнему брандмауэру аудио-и видеоданных для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e4cbc-177">Determine external A/V firewall and port requirements for Lync Server 2013</span></span>](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)  


[<span data-ttu-id="e4cbc-178">Управление федеративными партнерами XMPP в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e4cbc-178">Manage XMPP federated partners in Lync Server 2013</span></span>](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

