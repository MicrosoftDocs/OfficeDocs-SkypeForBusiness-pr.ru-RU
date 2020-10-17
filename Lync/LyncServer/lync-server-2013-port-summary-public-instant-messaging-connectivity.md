---
title: 'Lync Server 2013: сводка по портам — общедоступная служба обмена мгновенными сообщениями'
description: 'Lync Server 2013: сводка по портам — общедоступная служба обмена мгновенными сообщениями.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Port summary - Public instant messaging connectivity
ms:assetid: f46756ec-1401-4ca2-a4a4-5cd28bcfdc7f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ618376(v=OCS.15)
ms:contentKeyID: 49105663
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4137b5f92e043dc15dc9aa1f0b9593b4d9f7c2ca
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543065"
---
# <a name="port-summary---public-instant-messaging-connectivity-in-lync-server-2013"></a><span data-ttu-id="18c2f-103">Сводка по портам — общедоступная служба обмена мгновенными сообщениями в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="18c2f-103">Port summary - Public instant messaging connectivity in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="18c2f-104">_**Последнее изменение темы:** 2013-02-16_</span><span class="sxs-lookup"><span data-stu-id="18c2f-104">_**Topic Last Modified:** 2013-02-16_</span></span>

<span data-ttu-id="18c2f-105">Чтобы настроить брандмауэр для поддержки портов и протоколов, необходимых для поддержки подключения к общедоступным службам обмена мгновенными сообщениями, сначала обратите внимание на то, что SIP/MTLS/TCP 5061 является двунаправленной учетной записью для связи с контактами в общедоступном поставщике IM для связи с клиентами Lync</span><span class="sxs-lookup"><span data-stu-id="18c2f-105">To configure your firewall for ports and protocols necessary to support public instant messaging connectivity, first note that SIP/MTLS/TCP 5061 is bidirectional to account for the ability of contacts in the public IM provider to contact Lync clients, or for Lync to contact public IM contacts.</span></span>

<span data-ttu-id="18c2f-106">Windows Live Messenger может участвовать в аудио-и видеосвязи с клиентами Lync.</span><span class="sxs-lookup"><span data-stu-id="18c2f-106">Windows Live Messenger can participate in audio/video communications with Lync clients.</span></span> <span data-ttu-id="18c2f-107">Эти учетные записи для похожих портов брандмауэра и протоколов, которые, как правило, находятся на брандмауэре для поддержки клиентов Lync как внешних пользователей.</span><span class="sxs-lookup"><span data-stu-id="18c2f-107">This accounts for the very similar firewall port and protocol configuration that you would typically have on the firewall to support Lync clients as external users.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="18c2f-108">Lync — это мощное средство для связи между организациями и пользователями мира.</span><span class="sxs-lookup"><span data-stu-id="18c2f-108">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="18c2f-109">Для Федерации с Windows Live Messenger не требуется дополнительных лицензий на пользователей и устройств, не относящихся к стандартной клиентской лицензии Lync (CAL).</span><span class="sxs-lookup"><span data-stu-id="18c2f-109">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard Client Access License (CAL).</span></span> <span data-ttu-id="18c2f-110">В этот список будет добавлена Федерация Skype, что позволит пользователям Lync достичь сотен миллионов людей с помощью обмена мгновенными сообщениями и голосовой связью.</span><span class="sxs-lookup"><span data-stu-id="18c2f-110">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people with IM and voice.</span></span><BR><span data-ttu-id="18c2f-111">Федерация с контактами клиентов Messenger официально заканчивается 15 марта 2013, за исключением континентальная Китая.</span><span class="sxs-lookup"><span data-stu-id="18c2f-111">Federation with Messenger client contacts will officially end on March 15, 2013, except for mainland China.</span></span> <span data-ttu-id="18c2f-112">Skype станет клиентом Федерации для федеративных пользователей, которые ранее использовали Messenger.</span><span class="sxs-lookup"><span data-stu-id="18c2f-112">Skype will become the federation client for federated users who previously used Messenger.</span></span>



</div>

<div>

## <a name="firewall-summary--public-instant-messaging-connectivity"></a><span data-ttu-id="18c2f-113">Сводка по брандмауэру — связь с общедоступной службой обмена мгновенными сообщениями</span><span class="sxs-lookup"><span data-stu-id="18c2f-113">Firewall Summary – Public Instant Messaging Connectivity</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="18c2f-114">Роль/протокол/TCP или UDP/порт</span><span class="sxs-lookup"><span data-stu-id="18c2f-114">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="18c2f-115">Исходный IP-адрес</span><span class="sxs-lookup"><span data-stu-id="18c2f-115">Source IP address</span></span></th>
<th><span data-ttu-id="18c2f-116">Конечный IP-адрес</span><span class="sxs-lookup"><span data-stu-id="18c2f-116">Destination IP address</span></span></th>
<th><span data-ttu-id="18c2f-117">Примечания</span><span class="sxs-lookup"><span data-stu-id="18c2f-117">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="18c2f-118">Доступ/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="18c2f-118">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="18c2f-119">Партнеры по связи с общедоступной службой обмена мгновенными сообщениями</span><span class="sxs-lookup"><span data-stu-id="18c2f-119">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="18c2f-120">Интерфейс доступа пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="18c2f-120">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="18c2f-121">Для федеративного и общедоступной службы обмена мгновенными сообщениями, использующей SIP.</span><span class="sxs-lookup"><span data-stu-id="18c2f-121">For federated and public IM connectivity that use SIP.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="18c2f-122">Доступ/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="18c2f-122">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="18c2f-123">Интерфейс доступа пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="18c2f-123">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="18c2f-124">Партнеры по связи с общедоступной службой обмена мгновенными сообщениями</span><span class="sxs-lookup"><span data-stu-id="18c2f-124">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="18c2f-125">Для федеративного и общедоступной службы обмена мгновенными сообщениями, использующей SIP.</span><span class="sxs-lookup"><span data-stu-id="18c2f-125">For federated and public IM connectivity that use SIP.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="18c2f-126">/TCP/443 доступа и SIP (TLS)</span><span class="sxs-lookup"><span data-stu-id="18c2f-126">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="18c2f-127">Клиенты</span><span class="sxs-lookup"><span data-stu-id="18c2f-127">Clients</span></span></p></td>
<td><p><span data-ttu-id="18c2f-128">Интерфейс доступа пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="18c2f-128">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="18c2f-129">Трафик SIP от клиента к серверу для доступа внешних пользователей.</span><span class="sxs-lookup"><span data-stu-id="18c2f-129">Client-to-server SIP traffic for external user access.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="18c2f-130">АУДИО-И ВИДЕОДАННЫЕ/RTP/TCP/50000-– 999</span><span class="sxs-lookup"><span data-stu-id="18c2f-130">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="18c2f-131">Интерфейс доступа пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="18c2f-131">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="18c2f-132">Клиенты Live Messenger</span><span class="sxs-lookup"><span data-stu-id="18c2f-132">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="18c2f-133">Используется для сеансов аудио- и видеоконференций с использованием Windows Live Messenger, если настроена связь с общедоступной службой обмена мгновенными сообщениями.</span><span class="sxs-lookup"><span data-stu-id="18c2f-133">Used for A/V sessions with Windows Live Messenger if public IM connectivity is configured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="18c2f-134">АУДИО-И ВИДЕОДАННЫЕ/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="18c2f-134">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="18c2f-135">Интерфейс доступа пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="18c2f-135">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="18c2f-136">Клиенты Live Messenger</span><span class="sxs-lookup"><span data-stu-id="18c2f-136">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="18c2f-137">Необходимо для связи с общедоступной службой обмена мгновенными сообщениями с Windows Live Messenger.</span><span class="sxs-lookup"><span data-stu-id="18c2f-137">Required for public IM connectivity with Windows Live Messenger.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="18c2f-138">АУДИО-И ВИДЕОДАННЫЕ/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="18c2f-138">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="18c2f-139">Клиенты Live Messenger</span><span class="sxs-lookup"><span data-stu-id="18c2f-139">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="18c2f-140">Интерфейс доступа пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="18c2f-140">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="18c2f-141">Необходимо для связи с общедоступной службой обмена мгновенными сообщениями с Windows Live Messenger.</span><span class="sxs-lookup"><span data-stu-id="18c2f-141">Required for public IM connectivity with Windows Live Messenger.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a><span data-ttu-id="18c2f-142">См. также</span><span class="sxs-lookup"><span data-stu-id="18c2f-142">See Also</span></span>


[<span data-ttu-id="18c2f-143">Сценарии доступа внешних пользователей в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="18c2f-143">Scenarios for external user access in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-external-user-access.md)  
[<span data-ttu-id="18c2f-144">Определение требований к внешнему брандмауэру аудио-и видеоданных для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="18c2f-144">Determine external A/V firewall and port requirements for Lync Server 2013</span></span>](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

