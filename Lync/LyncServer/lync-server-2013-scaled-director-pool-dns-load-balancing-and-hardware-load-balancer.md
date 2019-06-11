---
title: Масштабируемый пул директоров — балансировка нагрузки на DNS и аппаратный балансировщик нагрузки
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Scaled Director pool - DNS load balancing and hardware load balancer
ms:assetid: a1f6ffc0-9e6e-4217-a923-025c9679e154
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205142(v=OCS.15)
ms:contentKeyID: 48185023
ms.date: 03/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1cd92304ca3a1147737958ad9d9fc94a49b2e5e2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34822183"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="scaled-director-pool---dns-load-balancing-and-hardware-load-balancer-in-lync-server-2013"></a><span data-ttu-id="faf2f-102">Масштабируемый пул директоров — балансировка нагрузки на DNS и аппаратный балансировщик нагрузки в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="faf2f-102">Scaled Director pool - DNS load balancing and hardware load balancer in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="faf2f-103">_**Тема последнего изменения:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="faf2f-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="faf2f-104">Масштабируемый пул режиссеров, на котором развернуты более одного режиссера для обработки дополнительной емкости и обеспечения высокой доступности, требуется балансировка нагрузки для распространения взаимодействия между клиентом и сервером со всеми участниками пула.</span><span class="sxs-lookup"><span data-stu-id="faf2f-104">A scaled Director pool, where there are more than one Director deployed to handle additional capacity and to provide high availability, requires load balancing to distribute client and server communication to all members of the pool.</span></span> <span data-ttu-id="faf2f-105">В режиссере веб-службы размещаются очень похоже на внешний интерфейс пула.</span><span class="sxs-lookup"><span data-stu-id="faf2f-105">A Director hosts web services much like a Front End pool.</span></span> <span data-ttu-id="faf2f-106">Для обеспечения балансировки нагрузки вы можете использовать аппаратную балансировку нагрузки или балансировку нагрузки DNS и аппаратную балансировку нагрузки.</span><span class="sxs-lookup"><span data-stu-id="faf2f-106">To provide the load balancing, you can use either hardware load balancing or domain name system (DNS) load balancing and hardware load balancing.</span></span> <span data-ttu-id="faf2f-107">Для веб-служб требуется балансировка нагрузки на оборудовании, а для балансировки нагрузки DNS — только возможности, необходимые для веб-служб.</span><span class="sxs-lookup"><span data-stu-id="faf2f-107">Hardware load balancing is required for the web services, and DNS load balancing alone does not provide the capabilities required for the web services.</span></span>

<span data-ttu-id="faf2f-108">В следующих разделах описаны вопросы планирования для развертывания пула с помощью балансировки нагрузки DNS в сочетании с аппаратным обеспечением балансировки нагрузки.</span><span class="sxs-lookup"><span data-stu-id="faf2f-108">The following topics describe the planning considerations for deploying a Director pool using DNS load balancing in conjunction with hardware load balancing.</span></span> <span data-ttu-id="faf2f-109">Если вы планируете использовать аппаратную балансировку нагрузки, но не балансировку нагрузки DNS для группового пула, ознакомьтесь с разделом [масштабированный пул пулов — подсистема подсистемы балансировки нагрузки оборудования в Lync Server 2013, в](lync-server-2013-scaled-director-pool-hardware-load-balancer.md) которой описаны требования к планированию для этой топологии.</span><span class="sxs-lookup"><span data-stu-id="faf2f-109">If you intend to use hardware load balancing, but not DNS load balancing for the Director pool, see the topic [Scaled Director pool - hardware load balancer in Lync Server 2013](lync-server-2013-scaled-director-pool-hardware-load-balancer.md) that describes the planning requirements for that topology.</span></span>

<span data-ttu-id="faf2f-110">![Масштабируемый пул режиссеров] (images/JJ205142.35a78a7a-b781-4c8f-951e-168451ba6a65(OCS.15).jpg "Масштабируемый пул режиссеров")</span><span class="sxs-lookup"><span data-stu-id="faf2f-110">![Scaled Director Pool](images/JJ205142.35a78a7a-b781-4c8f-951e-168451ba6a65(OCS.15).jpg "Scaled Director Pool")</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="faf2f-111">Содержание</span><span class="sxs-lookup"><span data-stu-id="faf2f-111">In This Section</span></span>

  - [<span data-ttu-id="faf2f-112">Сводка по сертификатам — балансировка нагрузки на DNS и аппаратная балансировка нагрузки в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="faf2f-112">Certificate summary - DNS and HLB load balanced in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-dns-and-hlb-load-balanced.md)

  - [<span data-ttu-id="faf2f-113">Сводка по портам — балансировка нагрузки на DNS и аппаратная балансировка нагрузки в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="faf2f-113">Port summary - DNS and HLB load balanced in Lync Server 2013</span></span>](lync-server-2013-port-summary-dns-and-hlb-load-balanced.md)

  - [<span data-ttu-id="faf2f-114">Сводка по DNS — балансировка нагрузки на DNS и аппаратная балансировка нагрузки в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="faf2f-114">DNS summary - DNS and HLB load balanced in Lync Server 2013</span></span>](lync-server-2013-dns-summary-dns-and-hlb-load-balanced.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

