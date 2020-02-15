---
title: Серверные платформы Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Server hardware platforms
ms:assetid: c964c1c0-0153-472b-88ad-a38866e0df0c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398835(v=OCS.15)
ms:contentKeyID: 48185395
ms.date: 07/28/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7e352153e4cc2386a159ac11f27f8ba4f5beb09f
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42048670"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="server-hardware-platforms-for-lync-server-2013"></a><span data-ttu-id="01f59-102">Аппаратные серверные платформы для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="01f59-102">Server hardware platforms for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="01f59-103">_**Последнее изменение темы:** 2016-07-28_</span><span class="sxs-lookup"><span data-stu-id="01f59-103">_**Topic Last Modified:** 2016-07-28_</span></span>

<span data-ttu-id="01f59-104">Для серверных ролей и компьютеров Lync Server 2013, на которых запущены средства администрирования Lync Server, требуется 64 — разрядное оборудование.</span><span class="sxs-lookup"><span data-stu-id="01f59-104">Lync Server 2013 server roles and computers running Lync Server administrative tools require 64-bit hardware.</span></span>

<span data-ttu-id="01f59-105">Конкретное оборудование, используемое для развертывания Lync Server 2013, может различаться в зависимости от требований к размеру и использованию.</span><span class="sxs-lookup"><span data-stu-id="01f59-105">The specific hardware used for Lync Server 2013 deployment can vary, depending on size and usage requirements.</span></span> <span data-ttu-id="01f59-106">В данном разделе описывается рекомендованное оборудование.</span><span class="sxs-lookup"><span data-stu-id="01f59-106">This section describes the recommended hardware.</span></span> <span data-ttu-id="01f59-107">Несмотря на то, что это рекомендации, а не требования, использование оборудования, не соответствующего рекомендациям, может привести к серьезным проблемам с производительностью и другим сложностям.</span><span class="sxs-lookup"><span data-stu-id="01f59-107">Although these are recommendations, not requirements, using hardware that does not meet these recommendations may result in significant performance issues and other issues.</span></span>

<div>

## <a name="recommended-hardware-platform"></a><span data-ttu-id="01f59-108">Рекомендуемая аппаратная платформа</span><span class="sxs-lookup"><span data-stu-id="01f59-108">Recommended Hardware Platform</span></span>

<span data-ttu-id="01f59-109">Для оптимальной производительности рекомендуется запускать Lync Server на серверах с оборудованием, удовлетворяющим требованиям, описанным в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="01f59-109">For best performance, we recommend that you run Lync Server on servers with hardware that meets the requirements in the following table.</span></span> <span data-ttu-id="01f59-110">Использование менее мощного оборудования может привести к проблемам функциональности или низкой производительности.</span><span class="sxs-lookup"><span data-stu-id="01f59-110">If you use less powerful hardware, you may experience functionality problems or poor performance.</span></span> <span data-ttu-id="01f59-111">Обратите внимание на то, что эти требования выше, чем в предыдущих версиях Lync Server, в основном потому что в Lync Server 2013 все серверы переднего плана работают под управлением SQL Server.</span><span class="sxs-lookup"><span data-stu-id="01f59-111">Note that these hardware requirements are higher than those of previous versions of Lync Server, primarily because in Lync Server 2013, all Front End Servers run SQL Server.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="01f59-112">Объединение сетевых карт поддерживается и должно быть прозрачным для Lync Server.</span><span class="sxs-lookup"><span data-stu-id="01f59-112">NIC teaming is supported and should be transparent to Lync Server.</span></span> <span data-ttu-id="01f59-113">Дополнительные сведения: <A href="http://go.microsoft.com/fwlink/p/?linkid=389910">Communications Server или Lync Server, а также объединение сетевых адаптеров</A>.</span><span class="sxs-lookup"><span data-stu-id="01f59-113">For details, see <A href="http://go.microsoft.com/fwlink/p/?linkid=389910">Communications Server or Lync Server and network adapter teaming</A>.</span></span>



</div>

### <a name="recommended-hardware-for-front-end-servers-back-end-servers-standard-edition-servers-persistent-chat-servers-and-persistent-chat-store-and-persistent-chat-compliance-store-back-end-server-roles-for-persistent-chat-server"></a><span data-ttu-id="01f59-114">Рекомендуемое оборудование для серверов переднего плана, серверов переднего плана, серверов Standard Edition, серверов сохраняемого чата, а хранилище сохраняемого чата и хранилища соответствия требованиям сохраняемого чата (роли сервера переднего плана для сервера сохраняемого чата)</span><span class="sxs-lookup"><span data-stu-id="01f59-114">Recommended Hardware for Front End Servers, Back End Servers, Standard Edition Servers, Persistent Chat Servers, and Persistent Chat Store and Persistent Chat Compliance Store (Back End Server Roles for Persistent Chat Server)</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="01f59-115">Компонент оборудования</span><span class="sxs-lookup"><span data-stu-id="01f59-115">Hardware component</span></span></th>
<th><span data-ttu-id="01f59-116">Рекомендовано</span><span class="sxs-lookup"><span data-stu-id="01f59-116">Recommended</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="01f59-117">ЦП</span><span class="sxs-lookup"><span data-stu-id="01f59-117">CPU</span></span></p></td>
<td><p><span data-ttu-id="01f59-118">64-разрядный двухъядерный процессор с тактовой частотой в шестнадцатеричном формате, 2,26 ГГц или выше.</span><span class="sxs-lookup"><span data-stu-id="01f59-118">64-bit dual processor, hex-core, 2.26 gigahertz (GHz) or higher.</span></span></p>
<p><span data-ttu-id="01f59-119">Процессоры Intel Itanium не поддерживаются для ролей сервера Lync Server.</span><span class="sxs-lookup"><span data-stu-id="01f59-119">Intel Itanium processors are not supported for Lync Server server roles.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="01f59-120">Память</span><span class="sxs-lookup"><span data-stu-id="01f59-120">Memory</span></span></p></td>
<td><p><span data-ttu-id="01f59-121">32 гигабайт (ГБ).</span><span class="sxs-lookup"><span data-stu-id="01f59-121">32 gigabytes (GB).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="01f59-122">Диск</span><span class="sxs-lookup"><span data-stu-id="01f59-122">Disk</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="01f59-123">8 или более 10 000 жестких дисков с частотой об/мин и не менее 72 ГБ свободного места на диске.</span><span class="sxs-lookup"><span data-stu-id="01f59-123">8 or more 10,000 RPM hard disk drives with at least 72 GB free disk space.</span></span></p>
<p><span data-ttu-id="01f59-124">Два диска должны использовать RAID 1, а шесть остальных — RAID 10.</span><span class="sxs-lookup"><span data-stu-id="01f59-124">Two of the disks should use RAID 1, and six should use RAID 10.</span></span></p>
<p><span data-ttu-id="01f59-125">-Также</span><span class="sxs-lookup"><span data-stu-id="01f59-125">- OR -</span></span></p></li>
<li><p><span data-ttu-id="01f59-126">Твердотельные накопители (SSD), производительность которых аналогична 8 механическим дискам со скоростью вращения 10000 об/мин.</span><span class="sxs-lookup"><span data-stu-id="01f59-126">Solid state drives (SSDs) which provide performance similar to 8 10,000-RPM mechanical disk drives.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="01f59-127">Сеть</span><span class="sxs-lookup"><span data-stu-id="01f59-127">Network</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="01f59-128">1 Двухпортовый сетевой адаптер, 1 Гбит/с или выше (рекомендуется 2, для чего требуется объединение с одним MAC-адресом и одним IP-адресом).</span><span class="sxs-lookup"><span data-stu-id="01f59-128">1 dual-port network adapter, 1 Gbps or higher (2 recommended, which requires teaming with a single MAC address and single IP address).</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="01f59-129">Конфигурации с двумя или несколькими сетевыми конфигурациями не поддерживаются для серверов переднего плана, серверов переднего плана, серверов Standard Edition и серверов сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="01f59-129">Dual or multi-homed configurations are not supported for Front End Servers, Back End Servers, Standard Edition servers, and Persistent Chat Servers.</span></span><BR><span data-ttu-id="01f59-130">ILO/DRAC/и т. д. подключения, не предоставляемые операционной системе и используемые для мониторинга и управления аппаратным обеспечением сервера, не составляют многоадресный сервер и поэтому поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="01f59-130">ILO/DRAC/etc. connections not exposed to the Operating System and used to monitor and manage the server hardware do not constitute a multi-homed server and thus are supported.</span></span>


</div></li>
</ul></td>
</tr>
</tbody>
</table>


### <a name="recommended-hardware-for-edge-servers-standalone-mediation-servers-and-directors"></a><span data-ttu-id="01f59-131">Рекомендуемое оборудование для пограничных серверов, изолированных серверов-посредников и директоров</span><span class="sxs-lookup"><span data-stu-id="01f59-131">Recommended Hardware for Edge Servers, Standalone Mediation Servers, and Directors</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="01f59-132">Компонент оборудования</span><span class="sxs-lookup"><span data-stu-id="01f59-132">Hardware component</span></span></th>
<th><span data-ttu-id="01f59-133">Рекомендовано</span><span class="sxs-lookup"><span data-stu-id="01f59-133">Recommended</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="01f59-134">ЦП</span><span class="sxs-lookup"><span data-stu-id="01f59-134">CPU</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="01f59-135">64-разрядный двухъядерный процессор, четырехъядерный процессор с тактовой частотой 2,0 ГГц или выше.</span><span class="sxs-lookup"><span data-stu-id="01f59-135">64-bit dual processor, quad-core, 2.0 gigahertz (GHz) or higher.</span></span></p>
<p><span data-ttu-id="01f59-136">-Также</span><span class="sxs-lookup"><span data-stu-id="01f59-136">- OR -</span></span></p></li>
<li><p><span data-ttu-id="01f59-137">64 бит с 4 процессором, Двухъядерный процессор, 2,0 ГГц или выше.</span><span class="sxs-lookup"><span data-stu-id="01f59-137">64-bit 4-way processor, dual-core, 2.0 GHz or higher.</span></span></p></li>
</ul>
<p><span data-ttu-id="01f59-138">Процессоры Intel Itanium не поддерживаются для ролей сервера Lync Server.</span><span class="sxs-lookup"><span data-stu-id="01f59-138">Intel Itanium processors are not supported for Lync Server server roles.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="01f59-139">Память</span><span class="sxs-lookup"><span data-stu-id="01f59-139">Memory</span></span></p></td>
<td><p><span data-ttu-id="01f59-140">16 гигабайт (ГБ).</span><span class="sxs-lookup"><span data-stu-id="01f59-140">16 gigabytes (GB).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="01f59-141">Диск</span><span class="sxs-lookup"><span data-stu-id="01f59-141">Disk</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="01f59-142">4 или более 10 000 жестких дисков с частотой об/мин и не менее 72 ГБ свободного места на диске.</span><span class="sxs-lookup"><span data-stu-id="01f59-142">4 or more 10,000 RPM hard disk drives with at least 72 GB free disk space.</span></span></p>
<p><span data-ttu-id="01f59-143">Диски должны находиться в конфигурации RAID 1 на 2 раза.</span><span class="sxs-lookup"><span data-stu-id="01f59-143">The disks should be in a 2x RAID 1 configuration.</span></span></p>
<p><span data-ttu-id="01f59-144">-Также</span><span class="sxs-lookup"><span data-stu-id="01f59-144">- OR -</span></span></p></li>
<li><p><span data-ttu-id="01f59-145">Твердотельные накопители (SSDs), которые обеспечивают производительность, схожую с механическими дисковыми накопителями 4 10 000 об/мин.</span><span class="sxs-lookup"><span data-stu-id="01f59-145">Solid state drives (SSDs) which provide performance similar to 4 10,000-RPM mechanical disk drives.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="01f59-146">Сеть</span><span class="sxs-lookup"><span data-stu-id="01f59-146">Network</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="01f59-147">1 Двухпортовый сетевой адаптер, 1 Гбит/с или выше (рекомендуется 2, для чего требуется объединение с одним MAC-адресом и одним IP-адресом).</span><span class="sxs-lookup"><span data-stu-id="01f59-147">1 dual-port network adapter, 1 Gbps or higher (2 recommended, which requires teaming with a single MAC address and single IP address).</span></span> <span data-ttu-id="01f59-148">2 сетевые интерфейсы необходимы на пограничных серверах и поддерживаются на изолированных серверах-посредниках.</span><span class="sxs-lookup"><span data-stu-id="01f59-148">2 network interfaces are required on Edge Servers, and are supported on standalone Mediation Servers.</span></span></p></li>
</ul>
<div>

> [!NOTE]  
> <span data-ttu-id="01f59-149">Конфигурации с двумя или несколькими сетевыми директориями не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="01f59-149">Dual or multi-homed configurations are not supported for Directors.</span></span><BR><span data-ttu-id="01f59-150">ILO/DRAC/и т. д. подключения, не предоставляемые операционной системе и используемые для мониторинга и управления аппаратным обеспечением сервера, не составляют многоадресный сервер и поэтому поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="01f59-150">ILO/DRAC/etc. connections not exposed to the Operating System and used to monitor and manage the server hardware do not constitute a multi-homed server and thus are supported.</span></span>


</div>
<p><span data-ttu-id="01f59-151">Пограничные серверы потребуют наличия двух сетевых интерфейсов, которые являются сетевыми адаптерами с двумя портами, 1 Гбит/с или выше (или двумя парными сетевыми адаптерами, для каждой пары, сопоставленной с одним MAC-адресом и одним IP-адресом, в совокупности две пары).</span><span class="sxs-lookup"><span data-stu-id="01f59-151">Edge Servers will require two network interfaces that are dual-port network adapters, 1 Gbps or higher (or two paired network adapters, for a total of four, each pair being teamed with a single MAC address and a single IP address, for a total of two pairs).</span></span></p>
<p><span data-ttu-id="01f59-152">Установка дополнительных плат сетевого интерфейса (NIC), позволяющая настроить конкретный IP-адрес PSTN, поддерживается на автономных серверах-посредниках.</span><span class="sxs-lookup"><span data-stu-id="01f59-152">Installation of additional network interface cards (NICs) to allow the configuration of a specific PSTN IP address is supported on standalone Mediation Servers.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

