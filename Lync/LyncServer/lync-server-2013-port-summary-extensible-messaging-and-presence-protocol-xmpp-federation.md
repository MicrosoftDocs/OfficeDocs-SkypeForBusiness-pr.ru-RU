---
title: Сводка по портам — Федерация Extensible Messaging and Presence Protocol (XMPP)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Port summary -  Extensible messaging and presence protocol (XMPP) federation
ms:assetid: 62e98fab-7add-4983-a3fa-dbe74e1c3849
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ618371(v=OCS.15)
ms:contentKeyID: 49105658
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b72ab2f2912a78ee30e9c032592a704eccbab8bf
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42152657"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="port-summary---extensible-messaging-and-presence-protocol-xmpp-federation-in-lync-server-2013"></a><span data-ttu-id="c0edc-102">Сводка по портам — Федерация протокола XMPP (Extensible Messaging and Presence Protocol) в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c0edc-102">Port summary - Extensible messaging and presence protocol (XMPP) federation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c0edc-103">_**Последнее изменение темы:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="c0edc-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="c0edc-104">Порты и протоколы, определенные для прокси-сервера Extensible Messaging and Presence Protocol (XMPP), развернутого на пограничном сервере, разрешают обмен данными между федеративным партнером XMPP на пограничный сервер, а также обеспечивает обмен данными между пограничным сервером и XMPP Федеративный партнер.</span><span class="sxs-lookup"><span data-stu-id="c0edc-104">The ports and protocols defined for the extensible messaging and presence protocol (XMPP) proxy deployed on the Edge Server allow communications from the XMPP federated partner to the Edge Server, and also allows communication from your Edge Server to the XMPP federated partner.</span></span> <span data-ttu-id="c0edc-105">Кроме того, правило определяется на внутреннем брандмауэре от сервера переднего плана или интерфейсного пула до пограничного сервера или пограничного пула.</span><span class="sxs-lookup"><span data-stu-id="c0edc-105">A rule is also defined on the internal-facing firewall from the Front End Server or Front End pool to the Edge Server or Edge pool.</span></span>

<div>

## <a name="firewall-summary-for-extensible-messaging-and-presence-protocol"></a><span data-ttu-id="c0edc-106">Сводка по брандмауэру для протокола XMPP</span><span class="sxs-lookup"><span data-stu-id="c0edc-106">Firewall Summary for Extensible Messaging and Presence Protocol</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c0edc-107">Протокол/TCP или UDP/порт</span><span class="sxs-lookup"><span data-stu-id="c0edc-107">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="c0edc-108">Источник (IP-адрес)</span><span class="sxs-lookup"><span data-stu-id="c0edc-108">Source (IP address)</span></span></th>
<th><span data-ttu-id="c0edc-109">Назначение (IP-адрес)</span><span class="sxs-lookup"><span data-stu-id="c0edc-109">Destination (IP address)</span></span></th>
<th><span data-ttu-id="c0edc-110">Комментарии</span><span class="sxs-lookup"><span data-stu-id="c0edc-110">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c0edc-111">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="c0edc-111">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="c0edc-112">Любые</span><span class="sxs-lookup"><span data-stu-id="c0edc-112">Any</span></span></p></td>
<td><p><span data-ttu-id="c0edc-113">IP-адрес интерфейса пограничного сервера доступа</span><span class="sxs-lookup"><span data-stu-id="c0edc-113">Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="c0edc-114">Стандартный порт для связи "сервер-сервер" через XMPP.</span><span class="sxs-lookup"><span data-stu-id="c0edc-114">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="c0edc-115">Разрешает связь с прокси-сервером пограничного сервера XMPP от федеративных партнеров XMPP</span><span class="sxs-lookup"><span data-stu-id="c0edc-115">Allows communication to the Edge Server XMPP proxy from federated XMPP partners</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c0edc-116">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="c0edc-116">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="c0edc-117">IP-адрес интерфейса пограничного сервера доступа</span><span class="sxs-lookup"><span data-stu-id="c0edc-117">Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="c0edc-118">Любые</span><span class="sxs-lookup"><span data-stu-id="c0edc-118">Any</span></span></p></td>
<td><p><span data-ttu-id="c0edc-119">Стандартный порт для связи "сервер-сервер" через XMPP.</span><span class="sxs-lookup"><span data-stu-id="c0edc-119">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="c0edc-120">Разрешает обмен данными от прокси-сервера пограничного сервера XMPP к федеративным партнерам XMPP</span><span class="sxs-lookup"><span data-stu-id="c0edc-120">Allows communication from the Edge Server XMPP proxy to federated XMPP partners</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c0edc-121">XMPP/MTLS/23456</span><span class="sxs-lookup"><span data-stu-id="c0edc-121">XMPP/MTLS/23456</span></span></p></td>
<td><p><span data-ttu-id="c0edc-122">Любые</span><span class="sxs-lookup"><span data-stu-id="c0edc-122">Any</span></span></p></td>
<td><p><span data-ttu-id="c0edc-123">IP-адрес внутреннего интерфейса пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="c0edc-123">Internal Edge Server Interface IP</span></span></p></td>
<td><p><span data-ttu-id="c0edc-124">Внутренний трафик XMPP от шлюза XMPP на сервере переднего плана или интерфейсном пуле к пограничным серверам</span><span class="sxs-lookup"><span data-stu-id="c0edc-124">Internal XMPP traffic from the XMPP Gateway on the Front End Server or Front End pool to the Edge Server</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a><span data-ttu-id="c0edc-125">См. также</span><span class="sxs-lookup"><span data-stu-id="c0edc-125">See Also</span></span>


[<span data-ttu-id="c0edc-126">Пример конфигурации XMPP в Lync Server 2013 – XMPP Федерация с Google говорите</span><span class="sxs-lookup"><span data-stu-id="c0edc-126">Example XMPP configuration in Lync Server 2013 – XMPP federation with Google Talk</span></span>](lync-server-2013-example-xmpp-configuration-–-xmpp-federation-with-google-talk.md)  


[<span data-ttu-id="c0edc-127">Управление федеративными партнерами XMPP в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c0edc-127">Manage XMPP federated partners in Lync Server 2013</span></span>](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

