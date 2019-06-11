---
title: 'Lync Server 2013: требования к оборудованию и программному обеспечению для директора'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Hardware and software requirements for the Director
ms:assetid: 747b701e-7f97-46fe-91c5-1e8d9addf9f7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398560(v=OCS.15)
ms:contentKeyID: 48184517
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a3b1b2a3f642c01d3a4743281554834e9ddda55f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834079"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="hardware-and-software-requirements-for-the-director-in-lync-server-2013"></a><span data-ttu-id="b84a1-102">Требования к оборудованию и программному обеспечению для директора в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b84a1-102">Hardware and software requirements for the Director in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b84a1-103">_**Тема последнего изменения:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="b84a1-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="b84a1-104">В этом разделе описаны требования к оборудованию и программному обеспечению для режиссера, а также поддерживаемые сценарии расвыровнения для режиссера.</span><span class="sxs-lookup"><span data-stu-id="b84a1-104">This section details the hardware and software requirements for the Director, and the supported collocation scenarios for the Director.</span></span>

<div>

## <a name="hardware-requirements-for-the-director"></a><span data-ttu-id="b84a1-105">Требования к оборудованию для режиссера</span><span class="sxs-lookup"><span data-stu-id="b84a1-105">Hardware Requirements for the Director</span></span>

<span data-ttu-id="b84a1-106">В таблице ниже перечислены требования к оборудованию для режиссера.</span><span class="sxs-lookup"><span data-stu-id="b84a1-106">The following table lists the hardware requirements for the Director:</span></span>

### <a name="hardware-requirements-for-the-director"></a><span data-ttu-id="b84a1-107">Требования к оборудованию для режиссера</span><span class="sxs-lookup"><span data-stu-id="b84a1-107">Hardware Requirements for the Director</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b84a1-108">Аппаратный компонент</span><span class="sxs-lookup"><span data-stu-id="b84a1-108">Hardware component</span></span></th>
<th><span data-ttu-id="b84a1-109">Минимальное требование</span><span class="sxs-lookup"><span data-stu-id="b84a1-109">Minimum requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b84a1-110">ЦП</span><span class="sxs-lookup"><span data-stu-id="b84a1-110">CPU</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="b84a1-111">64-разрядный процессор с тактовой частотой от 1 до двухъядерных, 2,0 ГГц или выше.</span><span class="sxs-lookup"><span data-stu-id="b84a1-111">64-bit processor, quad-core, 2.0 GHz or higher</span></span></p></li>
<li><p><span data-ttu-id="b84a1-112">64-разрядный двухъядерный процессор с тактовой частотой от двухъядерного процессора, 2,0 ГГц или выше.</span><span class="sxs-lookup"><span data-stu-id="b84a1-112">64-bit dual processor, dual-core, 2.0 GHz or higher</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b84a1-113">Память</span><span class="sxs-lookup"><span data-stu-id="b84a1-113">Memory</span></span></p></td>
<td><p><span data-ttu-id="b84a1-114">4 гигабайта (ГБ)</span><span class="sxs-lookup"><span data-stu-id="b84a1-114">4 gigabytes (GB)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b84a1-115">Диск</span><span class="sxs-lookup"><span data-stu-id="b84a1-115">Disk</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="b84a1-116">жесткий диск 10000 об/мин (HDD)</span><span class="sxs-lookup"><span data-stu-id="b84a1-116">10K RPM hard disk drive (HDD)</span></span></p></li>
<li><p><span data-ttu-id="b84a1-117">Высокопроизводительный твердотельный накопитель (SSD) с производительностью не менее 10 000 RPM</span><span class="sxs-lookup"><span data-stu-id="b84a1-117">High-performance solid state drive (SSD) with performance equal to or better than 10K RPM HDD</span></span></p></li>
<li><p><span data-ttu-id="b84a1-118">2x RAID 10 (чередующиеся и зеркальные): 15 000 RPM для файлов данных базы данных</span><span class="sxs-lookup"><span data-stu-id="b84a1-118">2x RAID 10 (striped and mirrored) 15K RPM disks for database data files</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b84a1-119">Сеть</span><span class="sxs-lookup"><span data-stu-id="b84a1-119">Network</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="b84a1-120">Двухканальные сетевые адаптеры (рекомендуется): 1 Гбит/с</span><span class="sxs-lookup"><span data-stu-id="b84a1-120">Dual 1 gigabit per second (Gbps) network adapters (recommended)</span></span></p></li>
<li><p><span data-ttu-id="b84a1-121">Один сетевой адаптер 1 Гбит/с (поддерживается)</span><span class="sxs-lookup"><span data-stu-id="b84a1-121">Single 1 Gbps network adapter (supported)</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="software-requirements-for-the-director"></a><span data-ttu-id="b84a1-122">Требования к программному обеспечению для режиссера</span><span class="sxs-lookup"><span data-stu-id="b84a1-122">Software Requirements for the Director</span></span>

<span data-ttu-id="b84a1-123">Роль режиссера можно развернуть только на серверах, на которых работает Lync Server 2013 Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="b84a1-123">The Director role can be deployed only on servers running Lync Server 2013 Enterprise Edition.</span></span>

<span data-ttu-id="b84a1-124">Для режиссеров требуется одна из следующих 64-разрядных операционных систем:</span><span class="sxs-lookup"><span data-stu-id="b84a1-124">One of the following 64-bit operating systems is required for the Directors:</span></span>

  - <span data-ttu-id="b84a1-125">Стандартная операционная система Windows Server 2008 R2 с пакетом обновления 1 (SP1)</span><span class="sxs-lookup"><span data-stu-id="b84a1-125">The Windows Server 2008 R2 Standard operating system with Service Pack 1</span></span>

  - <span data-ttu-id="b84a1-126">Операционная система Windows Server 2008 R2 Enterprise с пакетом обновления 1 (SP1)</span><span class="sxs-lookup"><span data-stu-id="b84a1-126">The Windows Server 2008 R2 Enterprise operating system with Service Pack 1</span></span>

  - <span data-ttu-id="b84a1-127">Операционная система Windows Server 2008 R2 Datacenter с пакетом обновления 1 (SP1)</span><span class="sxs-lookup"><span data-stu-id="b84a1-127">The Windows Server 2008 R2 Datacenter operating system with Service Pack 1</span></span>

  - <span data-ttu-id="b84a1-128">Операционная система Windows Server 2012 Standard</span><span class="sxs-lookup"><span data-stu-id="b84a1-128">The Windows Server 2012 Standard operating system</span></span>

  - <span data-ttu-id="b84a1-129">Операционная система Windows Server 2012 Datacenter</span><span class="sxs-lookup"><span data-stu-id="b84a1-129">The Windows Server 2012 Datacenter operating system</span></span>

<span data-ttu-id="b84a1-130">Для Lync Server 2013 также необходимо установить следующие программы и обновления, описанные в разделе [Дополнительные сведения о серверной поддержке и требованиях в Lync server 2013](lync-server-2013-additional-server-support-and-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b84a1-130">Lync Server 2013 also requires installation of the following programs and updates detailed in the topic [Additional server support and requirements in Lync Server 2013](lync-server-2013-additional-server-support-and-requirements.md).</span></span>

</div>

<div>

## <a name="supported-collocation"></a><span data-ttu-id="b84a1-131">Поддерживаемое расвыровнение</span><span class="sxs-lookup"><span data-stu-id="b84a1-131">Supported Collocation</span></span>

<span data-ttu-id="b84a1-132">Роль Director Server не может быть размещена с другой ролью сервера в Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b84a1-132">The Director server role cannot be collocated with any other server role in Lync Server 2013.</span></span> <span data-ttu-id="b84a1-133">Однако если вы не разворачиваете директорию, сервер переднего плана считает роль.</span><span class="sxs-lookup"><span data-stu-id="b84a1-133">However, if you do not deploy a Director, the Front End Servers will assume the role.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

