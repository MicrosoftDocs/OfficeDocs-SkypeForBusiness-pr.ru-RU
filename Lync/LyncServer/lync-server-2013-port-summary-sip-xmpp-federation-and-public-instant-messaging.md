---
title: 'Сводка по портам: SIP, Федерация XMPP и общедоступная служба обмена мгновенными сообщениями'
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
ms.openlocfilehash: e8fd24bab9596f12060c87937d98cc2a57d0c887
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42183712"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="port-summary---sip-xmpp-federation-and-public-instant-messaging-in-lync-server-2013"></a><span data-ttu-id="12579-102">Сводка по портам: SIP, Федерация XMPP и общедоступные службы обмена мгновенными сообщениями в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="12579-102">Port summary - SIP, XMPP federation, and public instant messaging in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="12579-103">_**Последнее изменение темы:** 2013-03-15_</span><span class="sxs-lookup"><span data-stu-id="12579-103">_**Topic Last Modified:** 2013-03-15_</span></span>

<span data-ttu-id="12579-104">Требования к портам, протоколам и брандмауэрам для Федерации с Microsoft Lync Server 2013, Lync Server 2010 и Office Communications Server схожи с развернутым пограничным сервером.</span><span class="sxs-lookup"><span data-stu-id="12579-104">Port, protocol and firewall requirements for federation with Microsoft Lync Server 2013, Lync Server 2010 and Office Communications Server are similar to those for the deployed Edge Server.</span></span> <span data-ttu-id="12579-105">Клиенты инициируют связь с пограничной службой доступа через TLS/SIP/TCP 443.</span><span class="sxs-lookup"><span data-stu-id="12579-105">Clients initiate communication with the Access Edge service over TLS/SIP/TCP 443.</span></span> <span data-ttu-id="12579-106">Федеративные партнеры тем не менее инициируют связь с службой пограничного доступа через MTLS/SIP/TCP 5061.</span><span class="sxs-lookup"><span data-stu-id="12579-106">Federated partners however, will initiate communications to the Access Edge service over MTLS/SIP/TCP 5061.</span></span>

<span data-ttu-id="12579-107">Чтобы настроить брандмауэр для поддержки портов и протоколов, необходимых для поддержки подключения к общедоступным службам обмена мгновенными сообщениями, сначала обратите внимание на то, что SIP/MTLS/TCP 5061 является двунаправленной учетной записью для связи с контактами в общедоступном поставщике IM для связи с клиентами Lync</span><span class="sxs-lookup"><span data-stu-id="12579-107">To configure your firewall for ports and protocols necessary to support public instant messaging connectivity, first note that SIP/MTLS/TCP 5061 is bidirectional to account for the ability of contacts in the public IM provider to contact Lync clients, or for Lync to contact public IM contacts.</span></span>

<span data-ttu-id="12579-108">Windows Live Messenger может участвовать в аудио-и видеосвязи с клиентами Lync.</span><span class="sxs-lookup"><span data-stu-id="12579-108">Windows Live Messenger can participate in audio/video communications with Lync clients.</span></span> <span data-ttu-id="12579-109">Эти учетные записи для похожих портов брандмауэра и протоколов, которые, как правило, находятся на брандмауэре для поддержки клиентов Lync как внешних пользователей.</span><span class="sxs-lookup"><span data-stu-id="12579-109">This accounts for the very similar firewall port and protocol configuration that you would typically have on the firewall to support Lync clients as external users.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="12579-110">Lync — это мощное средство для связи между организациями и пользователями мира.</span><span class="sxs-lookup"><span data-stu-id="12579-110">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="12579-111">Для Федерации с Windows Live Messenger не требуется дополнительных лицензий на пользователей и устройств, не относящихся к стандартной клиентской лицензии Lync (CAL).</span><span class="sxs-lookup"><span data-stu-id="12579-111">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard Client Access License (CAL).</span></span> <span data-ttu-id="12579-112">В этот список будет добавлена Федерация Skype, что позволит пользователям Lync достичь сотен миллионов людей с помощью обмена мгновенными сообщениями и голосовой связью.</span><span class="sxs-lookup"><span data-stu-id="12579-112">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people with IM and voice.</span></span><BR><span data-ttu-id="12579-113">Федерация с контактами клиентов Messenger официально заканчивается 15 марта 2013, за исключением континентальная Китая.</span><span class="sxs-lookup"><span data-stu-id="12579-113">Federation with Messenger client contacts will officially end on March 15, 2013, except for mainland China.</span></span> <span data-ttu-id="12579-114">Skype станет клиентом Федерации для федеративных пользователей, которые ранее использовали Messenger.</span><span class="sxs-lookup"><span data-stu-id="12579-114">Skype will become the federation client for federated users who previously used Messenger.</span></span>



</div>

<span data-ttu-id="12579-115">Порты и протоколы, определенные для прокси-сервера Extensible Messaging and Presence Protocol (XMPP), развернутого на пограничном сервере, разрешают обмен данными между федеративным партнером XMPP на пограничный сервер, а также обеспечивает обмен данными между пограничным сервером и XMPP Федеративный партнер.</span><span class="sxs-lookup"><span data-stu-id="12579-115">The ports and protocols defined for the extensible messaging and presence protocol (XMPP) proxy deployed on the Edge Server allow communications from the XMPP federated partner to the Edge Server, and also allows communication from your Edge Server to the XMPP federated partner.</span></span> <span data-ttu-id="12579-116">Кроме того, правило определяется на внутреннем брандмауэре от сервера переднего плана или интерфейсного пула до пограничного сервера или пограничного пула.</span><span class="sxs-lookup"><span data-stu-id="12579-116">A rule is also defined on the internal-facing firewall from the Front End Server or Front End pool to the Edge Server or Edge pool.</span></span>

<div>

## <a name="firewall-summary---sip-federation"></a><span data-ttu-id="12579-117">Сводка по брандмауэру: Федерация SIP</span><span class="sxs-lookup"><span data-stu-id="12579-117">Firewall Summary - SIP Federation</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="12579-118">Роль/протокол/TCP или UDP/порт</span><span class="sxs-lookup"><span data-stu-id="12579-118">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="12579-119">Исходный IP-адрес</span><span class="sxs-lookup"><span data-stu-id="12579-119">Source IP address</span></span></th>
<th><span data-ttu-id="12579-120">Конечный IP-адрес</span><span class="sxs-lookup"><span data-stu-id="12579-120">Destination IP address</span></span></th>
<th><span data-ttu-id="12579-121">Notes</span><span class="sxs-lookup"><span data-stu-id="12579-121">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="12579-122">Доступ/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="12579-122">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="12579-123">Общедоступный IP-адрес пограничной службы доступа</span><span class="sxs-lookup"><span data-stu-id="12579-123">Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="12579-124">Любые</span><span class="sxs-lookup"><span data-stu-id="12579-124">Any</span></span></p></td>
<td><p><span data-ttu-id="12579-125">Для федеративного подключения и подключения к общедоступным службам обмена мгновенными сообщениями с помощью SIP</span><span class="sxs-lookup"><span data-stu-id="12579-125">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary--public-instant-messaging-connectivity"></a><span data-ttu-id="12579-126">Сводка по брандмауэру — связь с общедоступной службой обмена мгновенными сообщениями</span><span class="sxs-lookup"><span data-stu-id="12579-126">Firewall Summary – Public Instant Messaging Connectivity</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="12579-127">Роль/протокол/TCP или UDP/порт</span><span class="sxs-lookup"><span data-stu-id="12579-127">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="12579-128">Исходный IP-адрес</span><span class="sxs-lookup"><span data-stu-id="12579-128">Source IP address</span></span></th>
<th><span data-ttu-id="12579-129">Конечный IP-адрес</span><span class="sxs-lookup"><span data-stu-id="12579-129">Destination IP address</span></span></th>
<th><span data-ttu-id="12579-130">Notes</span><span class="sxs-lookup"><span data-stu-id="12579-130">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="12579-131">Доступ/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="12579-131">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="12579-132">Партнеры по связи с общедоступной службой обмена мгновенными сообщениями</span><span class="sxs-lookup"><span data-stu-id="12579-132">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="12579-133">Интерфейс доступа пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="12579-133">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="12579-134">Для федеративного и общедоступной службы обмена мгновенными сообщениями, использующей SIP.</span><span class="sxs-lookup"><span data-stu-id="12579-134">For federated and public IM connectivity that use SIP.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="12579-135">Доступ/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="12579-135">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="12579-136">Интерфейс доступа пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="12579-136">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="12579-137">Партнеры по связи с общедоступной службой обмена мгновенными сообщениями</span><span class="sxs-lookup"><span data-stu-id="12579-137">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="12579-138">Для федеративного и общедоступной службы обмена мгновенными сообщениями, использующей SIP.</span><span class="sxs-lookup"><span data-stu-id="12579-138">For federated and public IM connectivity that use SIP.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="12579-139">/TCP/443 доступа и SIP (TLS)</span><span class="sxs-lookup"><span data-stu-id="12579-139">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="12579-140">Клиенты</span><span class="sxs-lookup"><span data-stu-id="12579-140">Clients</span></span></p></td>
<td><p><span data-ttu-id="12579-141">Интерфейс доступа пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="12579-141">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="12579-142">Трафик SIP от клиента к серверу для доступа внешних пользователей.</span><span class="sxs-lookup"><span data-stu-id="12579-142">Client-to-server SIP traffic for external user access.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="12579-143">АУДИО-И ВИДЕОДАННЫЕ/RTP/TCP/50000-– 999</span><span class="sxs-lookup"><span data-stu-id="12579-143">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="12579-144">Интерфейс доступа пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="12579-144">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="12579-145">Клиенты Live Messenger</span><span class="sxs-lookup"><span data-stu-id="12579-145">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="12579-146">Используется для сеансов аудио- и видеоконференций с использованием Windows Live Messenger, если настроена связь с общедоступной службой обмена мгновенными сообщениями.</span><span class="sxs-lookup"><span data-stu-id="12579-146">Used for A/V sessions with Windows Live Messenger if public IM connectivity is configured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="12579-147">АУДИО-И ВИДЕОДАННЫЕ/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="12579-147">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="12579-148">Интерфейс доступа пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="12579-148">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="12579-149">Клиенты Live Messenger</span><span class="sxs-lookup"><span data-stu-id="12579-149">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="12579-150">Необходимо для связи с общедоступной службой обмена мгновенными сообщениями с Windows Live Messenger.</span><span class="sxs-lookup"><span data-stu-id="12579-150">Required for public IM connectivity with Windows Live Messenger.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="12579-151">АУДИО-И ВИДЕОДАННЫЕ/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="12579-151">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="12579-152">Клиенты Live Messenger</span><span class="sxs-lookup"><span data-stu-id="12579-152">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="12579-153">Интерфейс доступа пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="12579-153">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="12579-154">Необходимо для связи с общедоступной службой обмена мгновенными сообщениями с Windows Live Messenger.</span><span class="sxs-lookup"><span data-stu-id="12579-154">Required for public IM connectivity with Windows Live Messenger.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary---extensible-messaging-and-presence-protocol-xmpp"></a><span data-ttu-id="12579-155">Сводка по брандмауэру: расширенный протокол обмена сообщениями и присутствия (XMPP)</span><span class="sxs-lookup"><span data-stu-id="12579-155">Firewall Summary - Extensible Messaging and Presence Protocol (XMPP)</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="12579-156">Протокол/TCP или UDP/порт</span><span class="sxs-lookup"><span data-stu-id="12579-156">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="12579-157">Источник (IP-адрес)</span><span class="sxs-lookup"><span data-stu-id="12579-157">Source (IP address)</span></span></th>
<th><span data-ttu-id="12579-158">Назначение (IP-адрес)</span><span class="sxs-lookup"><span data-stu-id="12579-158">Destination (IP address)</span></span></th>
<th><span data-ttu-id="12579-159">Комментарии</span><span class="sxs-lookup"><span data-stu-id="12579-159">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="12579-160">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="12579-160">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="12579-161">Любые</span><span class="sxs-lookup"><span data-stu-id="12579-161">Any</span></span></p></td>
<td><p><span data-ttu-id="12579-162">IP-адрес интерфейса пограничного сервера доступа</span><span class="sxs-lookup"><span data-stu-id="12579-162">Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="12579-163">Стандартный порт для связи "сервер-сервер" через XMPP.</span><span class="sxs-lookup"><span data-stu-id="12579-163">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="12579-164">Разрешает связь с прокси-сервером пограничного сервера XMPP от федеративных партнеров XMPP</span><span class="sxs-lookup"><span data-stu-id="12579-164">Allows communication to the Edge Server XMPP proxy from federated XMPP partners</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="12579-165">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="12579-165">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="12579-166">IP-адрес интерфейса пограничного сервера доступа</span><span class="sxs-lookup"><span data-stu-id="12579-166">Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="12579-167">Любые</span><span class="sxs-lookup"><span data-stu-id="12579-167">Any</span></span></p></td>
<td><p><span data-ttu-id="12579-168">Стандартный порт для связи "сервер-сервер" через XMPP.</span><span class="sxs-lookup"><span data-stu-id="12579-168">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="12579-169">Разрешает обмен данными от прокси-сервера пограничного сервера XMPP к федеративным партнерам XMPP</span><span class="sxs-lookup"><span data-stu-id="12579-169">Allows communication from the Edge Server XMPP proxy to federated XMPP partners</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="12579-170">XMPP/MTLS/23456</span><span class="sxs-lookup"><span data-stu-id="12579-170">XMPP/MTLS/23456</span></span></p></td>
<td><p><span data-ttu-id="12579-171">Любые</span><span class="sxs-lookup"><span data-stu-id="12579-171">Any</span></span></p></td>
<td><p><span data-ttu-id="12579-172">IP-адрес внутреннего интерфейса пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="12579-172">Internal Edge Server Interface IP</span></span></p></td>
<td><p><span data-ttu-id="12579-173">Внутренний трафик XMPP от шлюза XMPP на сервере переднего плана или интерфейсном пуле к пограничным серверам</span><span class="sxs-lookup"><span data-stu-id="12579-173">Internal XMPP traffic from the XMPP Gateway on the Front End Server or Front End pool to the Edge Server</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a><span data-ttu-id="12579-174">См. также</span><span class="sxs-lookup"><span data-stu-id="12579-174">See Also</span></span>


[<span data-ttu-id="12579-175">Сценарии доступа внешних пользователей в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="12579-175">Scenarios for external user access in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-external-user-access.md)  
[<span data-ttu-id="12579-176">Определение требований к внешнему брандмауэру аудио-и видеоданных для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="12579-176">Determine external A/V firewall and port requirements for Lync Server 2013</span></span>](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)  


[<span data-ttu-id="12579-177">Управление федеративными партнерами XMPP в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="12579-177">Manage XMPP federated partners in Lync Server 2013</span></span>](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

