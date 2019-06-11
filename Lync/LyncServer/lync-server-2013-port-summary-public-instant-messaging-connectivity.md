---
title: 'Lync Server 2013: Общие сведения о портах — общедоступная служба обмена мгновенными сообщениями'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Port summary - Public instant messaging connectivity
ms:assetid: f46756ec-1401-4ca2-a4a4-5cd28bcfdc7f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ618376(v=OCS.15)
ms:contentKeyID: 49105663
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5bb6b8d0d9277b7d77440519596da76585b9d91b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34824248"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="port-summary---public-instant-messaging-connectivity-in-lync-server-2013"></a><span data-ttu-id="c8cef-102">Общие сведения о портах — общедоступная служба обмена мгновенными сообщениями в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c8cef-102">Port summary - Public instant messaging connectivity in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c8cef-103">_**Тема последнего изменения:** 2013-02-16_</span><span class="sxs-lookup"><span data-stu-id="c8cef-103">_**Topic Last Modified:** 2013-02-16_</span></span>

<span data-ttu-id="c8cef-104">Чтобы настроить брандмауэр для порта и протоколов, необходимых для поддержки общедоступной службы обмена мгновенными сообщениями, сначала обратите внимание на то, что SIP/MTLS/TCP 5061 является двунаправленным, чтобы иметь возможность контактам в общедоступном поставщике обмена мгновенными сообщениями для связи с клиентами Lync или Lync для контактам из общедоступного обмена мгновенными сообщениями.</span><span class="sxs-lookup"><span data-stu-id="c8cef-104">To configure your firewall for ports and protocols necessary to support public instant messaging connectivity, first note that SIP/MTLS/TCP 5061 is bidirectional to account for the ability of contacts in the public IM provider to contact Lync clients, or for Lync to contact public IM contacts.</span></span>

<span data-ttu-id="c8cef-105">Windows Live Messenger может принимать участие в голосовой и видеосвязи с клиентами Lync.</span><span class="sxs-lookup"><span data-stu-id="c8cef-105">Windows Live Messenger can participate in audio/video communications with Lync clients.</span></span> <span data-ttu-id="c8cef-106">Эти учетные записи похожи на настройки порта и протокола брандмауэра, которые обычно используются в брандмауэре для поддержки клиентов Lync в качестве внешних пользователей.</span><span class="sxs-lookup"><span data-stu-id="c8cef-106">This accounts for the very similar firewall port and protocol configuration that you would typically have on the firewall to support Lync clients as external users.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="c8cef-107">В некоторых случаях Lync — это мощный инструмент для связи между организациями и людьми по всему миру.</span><span class="sxs-lookup"><span data-stu-id="c8cef-107">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="c8cef-108">Для интеграции с Windows Live Messenger не требуется дополнительных лицензий на пользователей и устройств, Кроме стандартной клиентской лицензии Lync (CAL).</span><span class="sxs-lookup"><span data-stu-id="c8cef-108">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard Client Access License (CAL).</span></span> <span data-ttu-id="c8cef-109">В этот список будет добавлена Федерация Skype, благодаря чему пользователи Lync смогут общаться с сотнями миллионов людей с помощью обмена мгновенными сообщениями и голосовой связью.</span><span class="sxs-lookup"><span data-stu-id="c8cef-109">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people with IM and voice.</span></span><BR><span data-ttu-id="c8cef-110">Интеграция с контактами клиентов Messenger официально заканчивается 15 марта 2013, за исключением маинланд Китая.</span><span class="sxs-lookup"><span data-stu-id="c8cef-110">Federation with Messenger client contacts will officially end on March 15, 2013, except for mainland China.</span></span> <span data-ttu-id="c8cef-111">Skype станет клиентом Федерации федеративных пользователей, которые ранее использовали Messenger.</span><span class="sxs-lookup"><span data-stu-id="c8cef-111">Skype will become the federation client for federated users who previously used Messenger.</span></span>



</div>

<div>

## <a name="firewall-summary--public-instant-messaging-connectivity"></a><span data-ttu-id="c8cef-112">Сводка по брандмауэрам: общедоступная служба обмена мгновенными сообщениями</span><span class="sxs-lookup"><span data-stu-id="c8cef-112">Firewall Summary – Public Instant Messaging Connectivity</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c8cef-113">Role/Protocol/TCP/UDP/порт</span><span class="sxs-lookup"><span data-stu-id="c8cef-113">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="c8cef-114">IP-адрес источника</span><span class="sxs-lookup"><span data-stu-id="c8cef-114">Source IP address</span></span></th>
<th><span data-ttu-id="c8cef-115">IP-адрес назначения</span><span class="sxs-lookup"><span data-stu-id="c8cef-115">Destination IP address</span></span></th>
<th><span data-ttu-id="c8cef-116">Примечания.</span><span class="sxs-lookup"><span data-stu-id="c8cef-116">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c8cef-117">Access/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="c8cef-117">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="c8cef-118">Партнеры по подключению общедоступных мгновенных сообщений</span><span class="sxs-lookup"><span data-stu-id="c8cef-118">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="c8cef-119">Интерфейс доступа пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="c8cef-119">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="c8cef-120">Для Федеративной и общедоступной службы обмена мгновенными сообщениями, использующих SIP.</span><span class="sxs-lookup"><span data-stu-id="c8cef-120">For federated and public IM connectivity that use SIP.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c8cef-121">Access/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="c8cef-121">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="c8cef-122">Интерфейс доступа пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="c8cef-122">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="c8cef-123">Партнеры по подключению общедоступных мгновенных сообщений</span><span class="sxs-lookup"><span data-stu-id="c8cef-123">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="c8cef-124">Для Федеративной и общедоступной службы обмена мгновенными сообщениями, использующих SIP.</span><span class="sxs-lookup"><span data-stu-id="c8cef-124">For federated and public IM connectivity that use SIP.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c8cef-125">Access/SIP (TLS)/TCP/443</span><span class="sxs-lookup"><span data-stu-id="c8cef-125">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="c8cef-126">Клиенты</span><span class="sxs-lookup"><span data-stu-id="c8cef-126">Clients</span></span></p></td>
<td><p><span data-ttu-id="c8cef-127">Интерфейс доступа пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="c8cef-127">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="c8cef-128">Трафик SIP от клиента к серверу для доступа внешних пользователей.</span><span class="sxs-lookup"><span data-stu-id="c8cef-128">Client-to-server SIP traffic for external user access.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c8cef-129">A/V/RTP/TCP/50000-59,999</span><span class="sxs-lookup"><span data-stu-id="c8cef-129">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="c8cef-130">Интерфейс доступа пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="c8cef-130">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="c8cef-131">Клиенты Live Messenger</span><span class="sxs-lookup"><span data-stu-id="c8cef-131">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="c8cef-132">Используется для сеансов обмена мгновенными сообщениями с помощью Windows Live Messenger, если настроена служба общего доступа к данным.</span><span class="sxs-lookup"><span data-stu-id="c8cef-132">Used for A/V sessions with Windows Live Messenger if public IM connectivity is configured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c8cef-133">A/V/STUN, МСТУРН/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="c8cef-133">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="c8cef-134">Интерфейс доступа пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="c8cef-134">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="c8cef-135">Клиенты Live Messenger</span><span class="sxs-lookup"><span data-stu-id="c8cef-135">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="c8cef-136">Требуется для общедоступной службы обмена мгновенными сообщениями с Windows Live Messenger.</span><span class="sxs-lookup"><span data-stu-id="c8cef-136">Required for public IM connectivity with Windows Live Messenger.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c8cef-137">A/V/STUN, МСТУРН/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="c8cef-137">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="c8cef-138">Клиенты Live Messenger</span><span class="sxs-lookup"><span data-stu-id="c8cef-138">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="c8cef-139">Интерфейс доступа пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="c8cef-139">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="c8cef-140">Требуется для общедоступной службы обмена мгновенными сообщениями с Windows Live Messenger.</span><span class="sxs-lookup"><span data-stu-id="c8cef-140">Required for public IM connectivity with Windows Live Messenger.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a><span data-ttu-id="c8cef-141">См. также</span><span class="sxs-lookup"><span data-stu-id="c8cef-141">See Also</span></span>


[<span data-ttu-id="c8cef-142">Сценарии доступа внешних пользователей в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c8cef-142">Scenarios for external user access in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-external-user-access.md)  
[<span data-ttu-id="c8cef-143">Определение требований к внешнему брандмауэру аудио- и видеосвязи и портам для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c8cef-143">Determine external A/V firewall and port requirements for Lync Server 2013</span></span>](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

