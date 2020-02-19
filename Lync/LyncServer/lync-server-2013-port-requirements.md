---
title: Требования к портам Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Port requirements
ms:assetid: 9a6c1300-ef88-4181-a8f1-43cd3093962b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398798(v=OCS.15)
ms:contentKeyID: 48184886
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b27233708be5f6e660e4b4d8fa2900f04819c106
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42139240"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="port-requirements-for-lync-server-2013"></a><span data-ttu-id="20c0b-102">Требования к портам для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="20c0b-102">Port requirements for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="20c0b-103">_**Последнее изменение темы:** 2013-03-27_</span><span class="sxs-lookup"><span data-stu-id="20c0b-103">_**Topic Last Modified:** 2013-03-27_</span></span>

<span data-ttu-id="20c0b-104">Lync Server требует, чтобы определенные порты в брандмауэре были открыты.</span><span class="sxs-lookup"><span data-stu-id="20c0b-104">Lync Server requires that specific ports on the firewall be open.</span></span> <span data-ttu-id="20c0b-105">Кроме того, если в организации развернут протокол IPsec, то он должен быть отключен в диапазоне портов, используемых для доставки звука, видео и панорамного видео.</span><span class="sxs-lookup"><span data-stu-id="20c0b-105">Additionally, if Internet Protocol security (IPsec) is deployed in your organization, IPsec must be disabled over the range of ports used for the delivery of audio, video, and panorama video.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="20c0b-106">Содержание</span><span class="sxs-lookup"><span data-stu-id="20c0b-106">In This Section</span></span>

<span data-ttu-id="20c0b-107">В этой статье содержатся следующие разделы:</span><span class="sxs-lookup"><span data-stu-id="20c0b-107">This section includes the following topics:</span></span>

  - [<span data-ttu-id="20c0b-108">Порты и протоколы для внутренних серверов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="20c0b-108">Ports and protocols for internal servers in Lync Server 2013</span></span>](lync-server-2013-ports-and-protocols-for-internal-servers.md)

  - [<span data-ttu-id="20c0b-109">Исключения IPsec в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="20c0b-109">IPsec exceptions in Lync Server 2013</span></span>](lync-server-2013-ipsec-exceptions.md)

  - [<span data-ttu-id="20c0b-110">Сводка по портам — единый консолидированный край с частными IP-адресами, использующими NAT в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="20c0b-110">Port summary - Single consolidated edge with private IP addresses using NAT in Lync Server 2013</span></span>](lync-server-2013-port-summary-single-consolidated-edge-with-private-ip-addresses-using-nat.md)

  - [<span data-ttu-id="20c0b-111">Сводка по портам — единая Объединенная пограничная с общедоступными IP-адресами в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="20c0b-111">Port summary - Single consolidated edge with public IP addresses in Lync Server 2013</span></span>](lync-server-2013-port-summary-single-consolidated-edge-with-public-ip-addresses.md)

  - [<span data-ttu-id="20c0b-112">Сводка по портам — масштабируемый консолидированный край, балансировка нагрузки на DNS с частными IP-адресами с использованием NAT в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="20c0b-112">Port summary - Scaled consolidated edge, DNS load balancing with private IP addresses using NAT in Lync Server 2013</span></span>](lync-server-2013-port-summary-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md)

  - [<span data-ttu-id="20c0b-113">Сводка по портам — масштабируемый консолидированный край, балансировка нагрузки на DNS с общедоступными IP-адресами в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="20c0b-113">Port summary - Scaled consolidated edge, DNS load balancing with public IP addresses in Lync Server 2013</span></span>](lync-server-2013-port-summary-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md)

  - [<span data-ttu-id="20c0b-114">Сводка по портам — масштабируемая консолидированная пограничная система с аппаратными подсистемами балансировки нагрузки в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="20c0b-114">Port summary - Scaled consolidated edge with hardware load balancers in Lync Server 2013</span></span>](lync-server-2013-port-summary-scaled-consolidated-edge-with-hardware-load-balancers.md)

  - [<span data-ttu-id="20c0b-115">Сводка по портам — обратный прокси-сервер в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="20c0b-115">Port summary - Reverse proxy in Lync Server 2013</span></span>](lync-server-2013-port-summary-reverse-proxy.md)

  - [<span data-ttu-id="20c0b-116">Сводка по портам: SIP, Федерация XMPP и общедоступные службы обмена мгновенными сообщениями в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="20c0b-116">Port summary - SIP, XMPP federation, and public instant messaging in Lync Server 2013</span></span>](lync-server-2013-port-summary-sip-xmpp-federation-and-public-instant-messaging.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

