---
title: 'Lync Server 2013: сводка по портам — общедоступная служба обмена мгновенными сообщениями'
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
ms.openlocfilehash: bfc057f4d41104dcebc89003ff77eb75622ee3c1
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42183932"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="port-summary---public-instant-messaging-connectivity-in-lync-server-2013"></a><span data-ttu-id="491fa-102">Сводка по портам — общедоступная служба обмена мгновенными сообщениями в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="491fa-102">Port summary - Public instant messaging connectivity in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="491fa-103">_**Последнее изменение темы:** 2013-02-16_</span><span class="sxs-lookup"><span data-stu-id="491fa-103">_**Topic Last Modified:** 2013-02-16_</span></span>

<span data-ttu-id="491fa-104">Чтобы настроить брандмауэр для поддержки портов и протоколов, необходимых для поддержки подключения к общедоступным службам обмена мгновенными сообщениями, сначала обратите внимание на то, что SIP/MTLS/TCP 5061 является двунаправленной учетной записью для связи с контактами в общедоступном поставщике IM для связи с клиентами Lync</span><span class="sxs-lookup"><span data-stu-id="491fa-104">To configure your firewall for ports and protocols necessary to support public instant messaging connectivity, first note that SIP/MTLS/TCP 5061 is bidirectional to account for the ability of contacts in the public IM provider to contact Lync clients, or for Lync to contact public IM contacts.</span></span>

<span data-ttu-id="491fa-105">Windows Live Messenger может участвовать в аудио-и видеосвязи с клиентами Lync.</span><span class="sxs-lookup"><span data-stu-id="491fa-105">Windows Live Messenger can participate in audio/video communications with Lync clients.</span></span> <span data-ttu-id="491fa-106">Эти учетные записи для похожих портов брандмауэра и протоколов, которые, как правило, находятся на брандмауэре для поддержки клиентов Lync как внешних пользователей.</span><span class="sxs-lookup"><span data-stu-id="491fa-106">This accounts for the very similar firewall port and protocol configuration that you would typically have on the firewall to support Lync clients as external users.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="491fa-107">Lync — это мощное средство для связи между организациями и пользователями мира.</span><span class="sxs-lookup"><span data-stu-id="491fa-107">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="491fa-108">Для Федерации с Windows Live Messenger не требуется дополнительных лицензий на пользователей и устройств, не относящихся к стандартной клиентской лицензии Lync (CAL).</span><span class="sxs-lookup"><span data-stu-id="491fa-108">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard Client Access License (CAL).</span></span> <span data-ttu-id="491fa-109">В этот список будет добавлена Федерация Skype, что позволит пользователям Lync достичь сотен миллионов людей с помощью обмена мгновенными сообщениями и голосовой связью.</span><span class="sxs-lookup"><span data-stu-id="491fa-109">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people with IM and voice.</span></span><BR><span data-ttu-id="491fa-110">Федерация с контактами клиентов Messenger официально заканчивается 15 марта 2013, за исключением континентальная Китая.</span><span class="sxs-lookup"><span data-stu-id="491fa-110">Federation with Messenger client contacts will officially end on March 15, 2013, except for mainland China.</span></span> <span data-ttu-id="491fa-111">Skype станет клиентом Федерации для федеративных пользователей, которые ранее использовали Messenger.</span><span class="sxs-lookup"><span data-stu-id="491fa-111">Skype will become the federation client for federated users who previously used Messenger.</span></span>



</div>

<div>

## <a name="firewall-summary--public-instant-messaging-connectivity"></a><span data-ttu-id="491fa-112">Сводка по брандмауэру — связь с общедоступной службой обмена мгновенными сообщениями</span><span class="sxs-lookup"><span data-stu-id="491fa-112">Firewall Summary – Public Instant Messaging Connectivity</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="491fa-113">Роль/протокол/TCP или UDP/порт</span><span class="sxs-lookup"><span data-stu-id="491fa-113">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="491fa-114">Исходный IP-адрес</span><span class="sxs-lookup"><span data-stu-id="491fa-114">Source IP address</span></span></th>
<th><span data-ttu-id="491fa-115">Конечный IP-адрес</span><span class="sxs-lookup"><span data-stu-id="491fa-115">Destination IP address</span></span></th>
<th><span data-ttu-id="491fa-116">Notes</span><span class="sxs-lookup"><span data-stu-id="491fa-116">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="491fa-117">Доступ/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="491fa-117">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="491fa-118">Партнеры по связи с общедоступной службой обмена мгновенными сообщениями</span><span class="sxs-lookup"><span data-stu-id="491fa-118">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="491fa-119">Интерфейс доступа пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="491fa-119">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="491fa-120">Для федеративного и общедоступной службы обмена мгновенными сообщениями, использующей SIP.</span><span class="sxs-lookup"><span data-stu-id="491fa-120">For federated and public IM connectivity that use SIP.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="491fa-121">Доступ/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="491fa-121">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="491fa-122">Интерфейс доступа пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="491fa-122">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="491fa-123">Партнеры по связи с общедоступной службой обмена мгновенными сообщениями</span><span class="sxs-lookup"><span data-stu-id="491fa-123">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="491fa-124">Для федеративного и общедоступной службы обмена мгновенными сообщениями, использующей SIP.</span><span class="sxs-lookup"><span data-stu-id="491fa-124">For federated and public IM connectivity that use SIP.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="491fa-125">/TCP/443 доступа и SIP (TLS)</span><span class="sxs-lookup"><span data-stu-id="491fa-125">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="491fa-126">Клиенты</span><span class="sxs-lookup"><span data-stu-id="491fa-126">Clients</span></span></p></td>
<td><p><span data-ttu-id="491fa-127">Интерфейс доступа пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="491fa-127">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="491fa-128">Трафик SIP от клиента к серверу для доступа внешних пользователей.</span><span class="sxs-lookup"><span data-stu-id="491fa-128">Client-to-server SIP traffic for external user access.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="491fa-129">АУДИО-И ВИДЕОДАННЫЕ/RTP/TCP/50000-– 999</span><span class="sxs-lookup"><span data-stu-id="491fa-129">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="491fa-130">Интерфейс доступа пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="491fa-130">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="491fa-131">Клиенты Live Messenger</span><span class="sxs-lookup"><span data-stu-id="491fa-131">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="491fa-132">Используется для сеансов аудио- и видеоконференций с использованием Windows Live Messenger, если настроена связь с общедоступной службой обмена мгновенными сообщениями.</span><span class="sxs-lookup"><span data-stu-id="491fa-132">Used for A/V sessions with Windows Live Messenger if public IM connectivity is configured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="491fa-133">АУДИО-И ВИДЕОДАННЫЕ/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="491fa-133">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="491fa-134">Интерфейс доступа пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="491fa-134">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="491fa-135">Клиенты Live Messenger</span><span class="sxs-lookup"><span data-stu-id="491fa-135">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="491fa-136">Необходимо для связи с общедоступной службой обмена мгновенными сообщениями с Windows Live Messenger.</span><span class="sxs-lookup"><span data-stu-id="491fa-136">Required for public IM connectivity with Windows Live Messenger.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="491fa-137">АУДИО-И ВИДЕОДАННЫЕ/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="491fa-137">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="491fa-138">Клиенты Live Messenger</span><span class="sxs-lookup"><span data-stu-id="491fa-138">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="491fa-139">Интерфейс доступа пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="491fa-139">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="491fa-140">Необходимо для связи с общедоступной службой обмена мгновенными сообщениями с Windows Live Messenger.</span><span class="sxs-lookup"><span data-stu-id="491fa-140">Required for public IM connectivity with Windows Live Messenger.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a><span data-ttu-id="491fa-141">См. также</span><span class="sxs-lookup"><span data-stu-id="491fa-141">See Also</span></span>


[<span data-ttu-id="491fa-142">Сценарии доступа внешних пользователей в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="491fa-142">Scenarios for external user access in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-external-user-access.md)  
[<span data-ttu-id="491fa-143">Определение требований к внешнему брандмауэру аудио-и видеоданных для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="491fa-143">Determine external A/V firewall and port requirements for Lync Server 2013</span></span>](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

