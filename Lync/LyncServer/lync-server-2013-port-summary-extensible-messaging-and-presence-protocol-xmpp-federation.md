---
title: Сводка по порту — расширяемая Федерация протоколов обмена сообщениями и присутствия (КСМПП)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Port summary -  Extensible messaging and presence protocol (XMPP) federation
ms:assetid: 62e98fab-7add-4983-a3fa-dbe74e1c3849
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ618371(v=OCS.15)
ms:contentKeyID: 49105658
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0b36a74393a8c61d5281bb009d212ee0bb12cf0a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34824192"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="port-summary---extensible-messaging-and-presence-protocol-xmpp-federation-in-lync-server-2013"></a><span data-ttu-id="cffa0-102">Сводка по порту — расширяемая Федерация протоколов обмена сообщениями и присутствия (КСМПП) в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cffa0-102">Port summary - Extensible messaging and presence protocol (XMPP) federation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cffa0-103">_**Тема последнего изменения:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="cffa0-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="cffa0-104">Порты и протоколы, определенные для прокси-сервера расширяемых сообщений и протоколов КСМПП, развернутых на пограничном сервере, разрешают обмен данными между сервером пограничного сервера КСМПП и допускает передачу данных с пограничного сервера в КСМПП Федеративный партнер.</span><span class="sxs-lookup"><span data-stu-id="cffa0-104">The ports and protocols defined for the extensible messaging and presence protocol (XMPP) proxy deployed on the Edge Server allow communications from the XMPP federated partner to the Edge Server, and also allows communication from your Edge Server to the XMPP federated partner.</span></span> <span data-ttu-id="cffa0-105">Правило также определяется во внутреннем брандмауэре, доступном на сервере переднего плана или на пограничном пуле, к внешнему и внешнему интерфейсу.</span><span class="sxs-lookup"><span data-stu-id="cffa0-105">A rule is also defined on the internal-facing firewall from the Front End Server or Front End pool to the Edge Server or Edge pool.</span></span>

<div>

## <a name="firewall-summary-for-extensible-messaging-and-presence-protocol"></a><span data-ttu-id="cffa0-106">Сводка брандмауэра по протоколу расширенного обмена сообщениями и присутствия</span><span class="sxs-lookup"><span data-stu-id="cffa0-106">Firewall Summary for Extensible Messaging and Presence Protocol</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="cffa0-107">Протокол/TCP или UDP/порт</span><span class="sxs-lookup"><span data-stu-id="cffa0-107">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="cffa0-108">Источник (IP-адрес)</span><span class="sxs-lookup"><span data-stu-id="cffa0-108">Source (IP address)</span></span></th>
<th><span data-ttu-id="cffa0-109">Назначение (IP-адрес)</span><span class="sxs-lookup"><span data-stu-id="cffa0-109">Destination (IP address)</span></span></th>
<th><span data-ttu-id="cffa0-110">Комментарии</span><span class="sxs-lookup"><span data-stu-id="cffa0-110">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cffa0-111">КСМПП/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="cffa0-111">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="cffa0-112">Любой</span><span class="sxs-lookup"><span data-stu-id="cffa0-112">Any</span></span></p></td>
<td><p><span data-ttu-id="cffa0-113">IP-адрес интерфейса службы Edge Access</span><span class="sxs-lookup"><span data-stu-id="cffa0-113">Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="cffa0-114">Стандартный коммуникационный порт "сервер-сервер" для КСМПП.</span><span class="sxs-lookup"><span data-stu-id="cffa0-114">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="cffa0-115">Разрешает связь с прокси-сервером пограничного сервера КСМПП от федеративных КСМПП партнеров</span><span class="sxs-lookup"><span data-stu-id="cffa0-115">Allows communication to the Edge Server XMPP proxy from federated XMPP partners</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cffa0-116">КСМПП/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="cffa0-116">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="cffa0-117">IP-адрес интерфейса службы Edge Access</span><span class="sxs-lookup"><span data-stu-id="cffa0-117">Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="cffa0-118">Любой</span><span class="sxs-lookup"><span data-stu-id="cffa0-118">Any</span></span></p></td>
<td><p><span data-ttu-id="cffa0-119">Стандартный коммуникационный порт "сервер-сервер" для КСМПП.</span><span class="sxs-lookup"><span data-stu-id="cffa0-119">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="cffa0-120">Разрешает взаимодействие с КСМПП прокси-сервером для федеративных КСМПП партнеров</span><span class="sxs-lookup"><span data-stu-id="cffa0-120">Allows communication from the Edge Server XMPP proxy to federated XMPP partners</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cffa0-121">КСМПП/MTLS/23456</span><span class="sxs-lookup"><span data-stu-id="cffa0-121">XMPP/MTLS/23456</span></span></p></td>
<td><p><span data-ttu-id="cffa0-122">Любой</span><span class="sxs-lookup"><span data-stu-id="cffa0-122">Any</span></span></p></td>
<td><p><span data-ttu-id="cffa0-123">IP-адрес внутреннего интерфейса пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="cffa0-123">Internal Edge Server Interface IP</span></span></p></td>
<td><p><span data-ttu-id="cffa0-124">Внутренний КСМПП трафик из шлюза КСМПП на сервере переднего плана или в пуле переднего плана на пограничный сервер</span><span class="sxs-lookup"><span data-stu-id="cffa0-124">Internal XMPP traffic from the XMPP Gateway on the Front End Server or Front End pool to the Edge Server</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a><span data-ttu-id="cffa0-125">См. также</span><span class="sxs-lookup"><span data-stu-id="cffa0-125">See Also</span></span>


[<span data-ttu-id="cffa0-126">Пример конфигурации XMPP в Lync Server 2013 — федерация XMPP с Google Talk</span><span class="sxs-lookup"><span data-stu-id="cffa0-126">Example XMPP configuration in Lync Server 2013 – XMPP federation with Google Talk</span></span>](lync-server-2013-example-xmpp-configuration-–-xmpp-federation-with-google-talk.md)  


[<span data-ttu-id="cffa0-127">Управление федеративными XMPP-партнерами в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cffa0-127">Manage XMPP federated partners in Lync Server 2013</span></span>](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

