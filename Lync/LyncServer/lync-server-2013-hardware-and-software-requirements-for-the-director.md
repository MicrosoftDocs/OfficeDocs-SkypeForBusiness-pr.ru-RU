---
title: 'Lync Server 2013: требования к оборудованию и программному обеспечению для директора'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Hardware and software requirements for the Director
ms:assetid: 747b701e-7f97-46fe-91c5-1e8d9addf9f7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398560(v=OCS.15)
ms:contentKeyID: 48184517
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b00e294291bcafb859cc900ca71463f1315cdfe8
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48536866"
---
# <a name="hardware-and-software-requirements-for-the-director-in-lync-server-2013"></a><span data-ttu-id="beda0-102">Требования к оборудованию и программному обеспечению для директора в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="beda0-102">Hardware and software requirements for the Director in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="beda0-103">_**Последнее изменение темы:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="beda0-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="beda0-104">В этом разделе описываются требования к оборудованию и программному обеспечению для директора и поддерживаемые сценарии совместного использования для директора.</span><span class="sxs-lookup"><span data-stu-id="beda0-104">This section details the hardware and software requirements for the Director, and the supported collocation scenarios for the Director.</span></span>

<div>

## <a name="hardware-requirements-for-the-director"></a><span data-ttu-id="beda0-105">Требования к оборудованию для Директора</span><span class="sxs-lookup"><span data-stu-id="beda0-105">Hardware Requirements for the Director</span></span>

<span data-ttu-id="beda0-106">В следующей таблице перечислены требования к оборудованию для директора:</span><span class="sxs-lookup"><span data-stu-id="beda0-106">The following table lists the hardware requirements for the Director:</span></span>

### <a name="hardware-requirements-for-the-director"></a><span data-ttu-id="beda0-107">Требования к оборудованию для Директора</span><span class="sxs-lookup"><span data-stu-id="beda0-107">Hardware Requirements for the Director</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="beda0-108">Компонент оборудования</span><span class="sxs-lookup"><span data-stu-id="beda0-108">Hardware component</span></span></th>
<th><span data-ttu-id="beda0-109">Минимальное требование</span><span class="sxs-lookup"><span data-stu-id="beda0-109">Minimum requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="beda0-110">ЦП</span><span class="sxs-lookup"><span data-stu-id="beda0-110">CPU</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="beda0-111">Четырехъядерный 64-разрядный процессор с частотой 2,0 ГГц или выше</span><span class="sxs-lookup"><span data-stu-id="beda0-111">64-bit processor, quad-core, 2.0 GHz or higher</span></span></p></li>
<li><p><span data-ttu-id="beda0-112">Двухъядерный 64-разрядный процессор с частотой 2,0 ГГц или выше</span><span class="sxs-lookup"><span data-stu-id="beda0-112">64-bit dual processor, dual-core, 2.0 GHz or higher</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="beda0-113">Память</span><span class="sxs-lookup"><span data-stu-id="beda0-113">Memory</span></span></p></td>
<td><p><span data-ttu-id="beda0-114">4 гигабайта (ГБ)</span><span class="sxs-lookup"><span data-stu-id="beda0-114">4 gigabytes (GB)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="beda0-115">Диск</span><span class="sxs-lookup"><span data-stu-id="beda0-115">Disk</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="beda0-116">Жесткий диск со скоростью вращения 10000 об/мин</span><span class="sxs-lookup"><span data-stu-id="beda0-116">10K RPM hard disk drive (HDD)</span></span></p></li>
<li><p><span data-ttu-id="beda0-117">Высокопроизводительный твердотельный накопитель (SSD) со скоростью, равной или превышающей жесткий диск со скоростью вращения 10000 об/мин</span><span class="sxs-lookup"><span data-stu-id="beda0-117">High-performance solid state drive (SSD) with performance equal to or better than 10K RPM HDD</span></span></p></li>
<li><p><span data-ttu-id="beda0-118">2 диска RAID 10 (чередующихся и зеркальных) со скоростью вращения для файлов базы данных</span><span class="sxs-lookup"><span data-stu-id="beda0-118">2x RAID 10 (striped and mirrored) 15K RPM disks for database data files</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="beda0-119">Сеть</span><span class="sxs-lookup"><span data-stu-id="beda0-119">Network</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="beda0-120">Двойные сетевые адаптеры со скоростью 1 гигабит в секунду (Гбит/с) (рекомендуется)</span><span class="sxs-lookup"><span data-stu-id="beda0-120">Dual 1 gigabit per second (Gbps) network adapters (recommended)</span></span></p></li>
<li><p><span data-ttu-id="beda0-121">Один сетевой адаптер 1 Гбит/с (поддерживается)</span><span class="sxs-lookup"><span data-stu-id="beda0-121">Single 1 Gbps network adapter (supported)</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="software-requirements-for-the-director"></a><span data-ttu-id="beda0-122">Требования к программному обеспечению для директора</span><span class="sxs-lookup"><span data-stu-id="beda0-122">Software Requirements for the Director</span></span>

<span data-ttu-id="beda0-123">Роль Director можно развернуть только на серверах, на которых работает Lync Server 2013 Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="beda0-123">The Director role can be deployed only on servers running Lync Server 2013 Enterprise Edition.</span></span>

<span data-ttu-id="beda0-124">Для директоров необходима одна из следующих операционных систем 64-bit:</span><span class="sxs-lookup"><span data-stu-id="beda0-124">One of the following 64-bit operating systems is required for the Directors:</span></span>

  - <span data-ttu-id="beda0-125">Стандартная операционная система Windows Server 2008 R2 с пакетом обновления 1 (SP1)</span><span class="sxs-lookup"><span data-stu-id="beda0-125">The Windows Server 2008 R2 Standard operating system with Service Pack 1</span></span>

  - <span data-ttu-id="beda0-126">Операционная система Windows Server 2008 R2 Enterprise с пакетом обновления 1 (SP1)</span><span class="sxs-lookup"><span data-stu-id="beda0-126">The Windows Server 2008 R2 Enterprise operating system with Service Pack 1</span></span>

  - <span data-ttu-id="beda0-127">Операционная система Windows Server 2008 R2 Datacenter с пакетом обновления 1 (SP1)</span><span class="sxs-lookup"><span data-stu-id="beda0-127">The Windows Server 2008 R2 Datacenter operating system with Service Pack 1</span></span>

  - <span data-ttu-id="beda0-128">Операционная система Windows Server 2012 Standard</span><span class="sxs-lookup"><span data-stu-id="beda0-128">The Windows Server 2012 Standard operating system</span></span>

  - <span data-ttu-id="beda0-129">Операционная система Windows Server 2012 Datacenter</span><span class="sxs-lookup"><span data-stu-id="beda0-129">The Windows Server 2012 Datacenter operating system</span></span>

<span data-ttu-id="beda0-130">Для Lync Server 2013 также необходимо установить следующие программы и обновления, подробно описанные в разделе [Дополнительная поддержка серверов и требования в Lync server 2013](lync-server-2013-additional-server-support-and-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="beda0-130">Lync Server 2013 also requires installation of the following programs and updates detailed in the topic [Additional server support and requirements in Lync Server 2013](lync-server-2013-additional-server-support-and-requirements.md).</span></span>

</div>

<div>

## <a name="supported-collocation"></a><span data-ttu-id="beda0-131">Поддерживаемые режимы совместного размещения</span><span class="sxs-lookup"><span data-stu-id="beda0-131">Supported Collocation</span></span>

<span data-ttu-id="beda0-132">Роль Director Server не может быть размещена с любой другой ролью сервера в Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="beda0-132">The Director server role cannot be collocated with any other server role in Lync Server 2013.</span></span> <span data-ttu-id="beda0-133">Однако если вы не развертываете директор, сервер переднего плана будет предполагать, что роль.</span><span class="sxs-lookup"><span data-stu-id="beda0-133">However, if you do not deploy a Director, the Front End Servers will assume the role.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

