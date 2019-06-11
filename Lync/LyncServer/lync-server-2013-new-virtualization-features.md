---
title: 'Lync Server 2013: новые функции виртуализации'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: New virtualization features
ms:assetid: edeb2c41-765e-47b8-8a2b-7a7ce09de2ad
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721926(v=OCS.15)
ms:contentKeyID: 49733861
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0e0fcd012470d21a713275fde6aabc29a864fe54
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34825970"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="new-virtualization-features-in-lync-server-2013"></a><span data-ttu-id="742b1-102">Новые функции виртуализации в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="742b1-102">New virtualization features in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="742b1-103">_**Тема последнего изменения:** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="742b1-103">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="742b1-104">Lync Server 2013 поддерживает виртуализацию как на Windows Server 2012, так и в Windows Server 2012 R2, так и в Windows Server 2008 R2.</span><span class="sxs-lookup"><span data-stu-id="742b1-104">Lync Server 2013 supports virtualization on both Windows Server 2012, Windows Server 2012 R2, and Windows Server 2008 R2.</span></span> <span data-ttu-id="742b1-105">Поддержка в Windows Server 2012 и Windows Server 2012 R2 включает в себя поддержку одной из корневых возможностей виртуализации ввода-вывода (SR-IOV).</span><span class="sxs-lookup"><span data-stu-id="742b1-105">Support on Windows Server 2012 and Windows Server 2012 R2 includes support for the Single Root I/O Virtualization (SR-IOV) capabilities.</span></span> <span data-ttu-id="742b1-106">С помощью SR-IOV виртуальная функция физического сетевого адаптера назначается непосредственно виртуальной машине.</span><span class="sxs-lookup"><span data-stu-id="742b1-106">With SR-IOV, the virtual function of a physical network adapter is assigned directly to a virtual machine.</span></span> <span data-ttu-id="742b1-107">Это повышает пропускную способность сети и сокращает время задержки сети, а также сокращает дополнительные ресурсы ЦП узла, необходимые для обработки сетевого трафика.</span><span class="sxs-lookup"><span data-stu-id="742b1-107">This increases network throughput and reduces network latency while also reducing the host CPU overhead that is required for processing network traffic.</span></span> <span data-ttu-id="742b1-108">Чтобы воспользоваться преимуществами SR-IOV, необходимо использовать сервер узла, на котором установлен BIOS, поддерживающий SR-IOV, а также сетевые адаптеры, поддерживающие SR-IOV.</span><span class="sxs-lookup"><span data-stu-id="742b1-108">To take advantage of SR-IOV, you must use a host server which has BIOS which supports SR-IOV, as well as use network adapters that support SR-IOV.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

