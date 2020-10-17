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
ms.openlocfilehash: cb5c5cbe1ef98a4028f8b05d96e4acc90cae7963
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48510276"
---
# <a name="server-hardware-platforms-for-lync-server-2013"></a><span data-ttu-id="8caa6-102">Аппаратные серверные платформы для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8caa6-102">Server hardware platforms for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8caa6-103">_**Последнее изменение темы:** 2016-07-28_</span><span class="sxs-lookup"><span data-stu-id="8caa6-103">_**Topic Last Modified:** 2016-07-28_</span></span>

<span data-ttu-id="8caa6-104">Для серверных ролей и компьютеров Lync Server 2013, на которых запущены средства администрирования Lync Server, требуется 64 — разрядное оборудование.</span><span class="sxs-lookup"><span data-stu-id="8caa6-104">Lync Server 2013 server roles and computers running Lync Server administrative tools require 64-bit hardware.</span></span>

<span data-ttu-id="8caa6-105">Конкретное оборудование, используемое для развертывания Lync Server 2013, может различаться в зависимости от требований к размеру и использованию.</span><span class="sxs-lookup"><span data-stu-id="8caa6-105">The specific hardware used for Lync Server 2013 deployment can vary, depending on size and usage requirements.</span></span> <span data-ttu-id="8caa6-106">В данном разделе описывается рекомендованное оборудование.</span><span class="sxs-lookup"><span data-stu-id="8caa6-106">This section describes the recommended hardware.</span></span> <span data-ttu-id="8caa6-107">Несмотря на то, что это рекомендации, а не требования, использование оборудования, не соответствующего рекомендациям, может привести к серьезным проблемам с производительностью и другим сложностям.</span><span class="sxs-lookup"><span data-stu-id="8caa6-107">Although these are recommendations, not requirements, using hardware that does not meet these recommendations may result in significant performance issues and other issues.</span></span>

<div>

## <a name="recommended-hardware-platform"></a><span data-ttu-id="8caa6-108">Рекомендуемая аппаратная платформа</span><span class="sxs-lookup"><span data-stu-id="8caa6-108">Recommended Hardware Platform</span></span>

<span data-ttu-id="8caa6-109">Для оптимальной производительности рекомендуется запускать Lync Server на серверах с оборудованием, удовлетворяющим требованиям, описанным в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="8caa6-109">For best performance, we recommend that you run Lync Server on servers with hardware that meets the requirements in the following table.</span></span> <span data-ttu-id="8caa6-110">Использование менее мощного оборудования может привести к проблемам функциональности или низкой производительности.</span><span class="sxs-lookup"><span data-stu-id="8caa6-110">If you use less powerful hardware, you may experience functionality problems or poor performance.</span></span> <span data-ttu-id="8caa6-111">Обратите внимание на то, что эти требования выше, чем в предыдущих версиях Lync Server, в основном потому что в Lync Server 2013 все серверы переднего плана работают под управлением SQL Server.</span><span class="sxs-lookup"><span data-stu-id="8caa6-111">Note that these hardware requirements are higher than those of previous versions of Lync Server, primarily because in Lync Server 2013, all Front End Servers run SQL Server.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="8caa6-112">Объединение сетевых карт поддерживается и должно быть прозрачным для Lync Server.</span><span class="sxs-lookup"><span data-stu-id="8caa6-112">NIC teaming is supported and should be transparent to Lync Server.</span></span> <span data-ttu-id="8caa6-113">Дополнительные сведения: <A href="https://go.microsoft.com/fwlink/p/?linkid=389910">Communications Server или Lync Server, а также объединение сетевых адаптеров</A>.</span><span class="sxs-lookup"><span data-stu-id="8caa6-113">For details, see <A href="https://go.microsoft.com/fwlink/p/?linkid=389910">Communications Server or Lync Server and network adapter teaming</A>.</span></span>



</div>

### <a name="recommended-hardware-for-front-end-servers-back-end-servers-standard-edition-servers-persistent-chat-servers-and-persistent-chat-store-and-persistent-chat-compliance-store-back-end-server-roles-for-persistent-chat-server"></a><span data-ttu-id="8caa6-114">Рекомендуемое оборудование для серверов переднего плана, серверов переднего плана, серверов Standard Edition, серверов сохраняемого чата, а хранилище сохраняемого чата и хранилища соответствия требованиям сохраняемого чата (роли сервера переднего плана для сервера сохраняемого чата)</span><span class="sxs-lookup"><span data-stu-id="8caa6-114">Recommended Hardware for Front End Servers, Back End Servers, Standard Edition Servers, Persistent Chat Servers, and Persistent Chat Store and Persistent Chat Compliance Store (Back End Server Roles for Persistent Chat Server)</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8caa6-115">Компонент оборудования</span><span class="sxs-lookup"><span data-stu-id="8caa6-115">Hardware component</span></span></th>
<th><span data-ttu-id="8caa6-116">Рекомендуемый</span><span class="sxs-lookup"><span data-stu-id="8caa6-116">Recommended</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8caa6-117">ЦП</span><span class="sxs-lookup"><span data-stu-id="8caa6-117">CPU</span></span></p></td>
<td><p><span data-ttu-id="8caa6-118">64-разрядный двухъядерный процессор с тактовой частотой в шестнадцатеричном формате, 2,26 ГГц или выше.</span><span class="sxs-lookup"><span data-stu-id="8caa6-118">64-bit dual processor, hex-core, 2.26 gigahertz (GHz) or higher.</span></span></p>
<p><span data-ttu-id="8caa6-119">Процессоры Intel Itanium не поддерживаются для ролей сервера Lync Server.</span><span class="sxs-lookup"><span data-stu-id="8caa6-119">Intel Itanium processors are not supported for Lync Server server roles.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8caa6-120">Память</span><span class="sxs-lookup"><span data-stu-id="8caa6-120">Memory</span></span></p></td>
<td><p><span data-ttu-id="8caa6-121">32 гигабайт (ГБ).</span><span class="sxs-lookup"><span data-stu-id="8caa6-121">32 gigabytes (GB).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8caa6-122">Диск</span><span class="sxs-lookup"><span data-stu-id="8caa6-122">Disk</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="8caa6-123">8 или более 10 000 жестких дисков с частотой об/мин и не менее 72 ГБ свободного места на диске.</span><span class="sxs-lookup"><span data-stu-id="8caa6-123">8 or more 10,000 RPM hard disk drives with at least 72 GB free disk space.</span></span></p>
<p><span data-ttu-id="8caa6-124">Два диска должны использовать RAID 1, а шесть остальных — RAID 10.</span><span class="sxs-lookup"><span data-stu-id="8caa6-124">Two of the disks should use RAID 1, and six should use RAID 10.</span></span></p>
<p><span data-ttu-id="8caa6-125">- Также</span><span class="sxs-lookup"><span data-stu-id="8caa6-125">- OR -</span></span></p></li>
<li><p><span data-ttu-id="8caa6-126">Твердотельные накопители (SSD), производительность которых аналогична 8 механическим дискам со скоростью вращения 10000 об/мин.</span><span class="sxs-lookup"><span data-stu-id="8caa6-126">Solid state drives (SSDs) which provide performance similar to 8 10,000-RPM mechanical disk drives.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8caa6-127">Сеть</span><span class="sxs-lookup"><span data-stu-id="8caa6-127">Network</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="8caa6-128">1 Двухпортовый сетевой адаптер, 1 Гбит/с или выше (рекомендуется 2, для чего требуется объединение с одним MAC-адресом и одним IP-адресом).</span><span class="sxs-lookup"><span data-stu-id="8caa6-128">1 dual-port network adapter, 1 Gbps or higher (2 recommended, which requires teaming with a single MAC address and single IP address).</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="8caa6-129">Конфигурации с двумя или несколькими сетевыми конфигурациями не поддерживаются для серверов переднего плана, серверов переднего плана, серверов Standard Edition и серверов сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="8caa6-129">Dual or multi-homed configurations are not supported for Front End Servers, Back End Servers, Standard Edition servers, and Persistent Chat Servers.</span></span><BR><span data-ttu-id="8caa6-130">ILO/DRAC/и т. д. подключения, не предоставляемые операционной системе и используемые для мониторинга и управления аппаратным обеспечением сервера, не составляют многоадресный сервер и поэтому поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="8caa6-130">ILO/DRAC/etc. connections not exposed to the Operating System and used to monitor and manage the server hardware do not constitute a multi-homed server and thus are supported.</span></span>


</div></li>
</ul></td>
</tr>
</tbody>
</table>


### <a name="recommended-hardware-for-edge-servers-standalone-mediation-servers-and-directors"></a><span data-ttu-id="8caa6-131">Рекомендуемое оборудование для пограничных серверов, изолированных серверов-посредников и директоров</span><span class="sxs-lookup"><span data-stu-id="8caa6-131">Recommended Hardware for Edge Servers, Standalone Mediation Servers, and Directors</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8caa6-132">Компонент оборудования</span><span class="sxs-lookup"><span data-stu-id="8caa6-132">Hardware component</span></span></th>
<th><span data-ttu-id="8caa6-133">Рекомендуемый</span><span class="sxs-lookup"><span data-stu-id="8caa6-133">Recommended</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8caa6-134">ЦП</span><span class="sxs-lookup"><span data-stu-id="8caa6-134">CPU</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="8caa6-135">64-разрядный двухъядерный процессор, четырехъядерный процессор с тактовой частотой 2,0 ГГц или выше.</span><span class="sxs-lookup"><span data-stu-id="8caa6-135">64-bit dual processor, quad-core, 2.0 gigahertz (GHz) or higher.</span></span></p>
<p><span data-ttu-id="8caa6-136">- Также</span><span class="sxs-lookup"><span data-stu-id="8caa6-136">- OR -</span></span></p></li>
<li><p><span data-ttu-id="8caa6-137">64 бит с 4 процессором, Двухъядерный процессор, 2,0 ГГц или выше.</span><span class="sxs-lookup"><span data-stu-id="8caa6-137">64-bit 4-way processor, dual-core, 2.0 GHz or higher.</span></span></p></li>
</ul>
<p><span data-ttu-id="8caa6-138">Процессоры Intel Itanium не поддерживаются для ролей сервера Lync Server.</span><span class="sxs-lookup"><span data-stu-id="8caa6-138">Intel Itanium processors are not supported for Lync Server server roles.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8caa6-139">Память</span><span class="sxs-lookup"><span data-stu-id="8caa6-139">Memory</span></span></p></td>
<td><p><span data-ttu-id="8caa6-140">16 гигабайт (ГБ).</span><span class="sxs-lookup"><span data-stu-id="8caa6-140">16 gigabytes (GB).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8caa6-141">Диск</span><span class="sxs-lookup"><span data-stu-id="8caa6-141">Disk</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="8caa6-142">4 или более 10 000 жестких дисков с частотой об/мин и не менее 72 ГБ свободного места на диске.</span><span class="sxs-lookup"><span data-stu-id="8caa6-142">4 or more 10,000 RPM hard disk drives with at least 72 GB free disk space.</span></span></p>
<p><span data-ttu-id="8caa6-143">Диски должны находиться в конфигурации RAID 1 на 2 раза.</span><span class="sxs-lookup"><span data-stu-id="8caa6-143">The disks should be in a 2x RAID 1 configuration.</span></span></p>
<p><span data-ttu-id="8caa6-144">- Также</span><span class="sxs-lookup"><span data-stu-id="8caa6-144">- OR -</span></span></p></li>
<li><p><span data-ttu-id="8caa6-145">Твердотельные накопители (SSDs), которые обеспечивают производительность, схожую с механическими дисковыми накопителями 4 10 000 об/мин.</span><span class="sxs-lookup"><span data-stu-id="8caa6-145">Solid state drives (SSDs) which provide performance similar to 4 10,000-RPM mechanical disk drives.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8caa6-146">Сеть</span><span class="sxs-lookup"><span data-stu-id="8caa6-146">Network</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="8caa6-147">1 Двухпортовый сетевой адаптер, 1 Гбит/с или выше (рекомендуется 2, для чего требуется объединение с одним MAC-адресом и одним IP-адресом).</span><span class="sxs-lookup"><span data-stu-id="8caa6-147">1 dual-port network adapter, 1 Gbps or higher (2 recommended, which requires teaming with a single MAC address and single IP address).</span></span> <span data-ttu-id="8caa6-148">2 сетевые интерфейсы необходимы на пограничных серверах и поддерживаются на изолированных серверах-посредниках.</span><span class="sxs-lookup"><span data-stu-id="8caa6-148">2 network interfaces are required on Edge Servers, and are supported on standalone Mediation Servers.</span></span></p></li>
</ul>
<div>

> [!NOTE]  
> <span data-ttu-id="8caa6-149">Конфигурации с двумя или несколькими сетевыми директориями не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="8caa6-149">Dual or multi-homed configurations are not supported for Directors.</span></span><BR><span data-ttu-id="8caa6-150">ILO/DRAC/и т. д. подключения, не предоставляемые операционной системе и используемые для мониторинга и управления аппаратным обеспечением сервера, не составляют многоадресный сервер и поэтому поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="8caa6-150">ILO/DRAC/etc. connections not exposed to the Operating System and used to monitor and manage the server hardware do not constitute a multi-homed server and thus are supported.</span></span>


</div>
<p><span data-ttu-id="8caa6-151">Пограничные серверы потребуют наличия двух сетевых интерфейсов, которые являются сетевыми адаптерами с двумя портами, 1 Гбит/с или выше (или двумя парными сетевыми адаптерами, для каждой пары, сопоставленной с одним MAC-адресом и одним IP-адресом, в совокупности две пары).</span><span class="sxs-lookup"><span data-stu-id="8caa6-151">Edge Servers will require two network interfaces that are dual-port network adapters, 1 Gbps or higher (or two paired network adapters, for a total of four, each pair being teamed with a single MAC address and a single IP address, for a total of two pairs).</span></span></p>
<p><span data-ttu-id="8caa6-152">Установка дополнительных плат сетевого интерфейса (NIC), позволяющая настроить конкретный IP-адрес PSTN, поддерживается на автономных серверах-посредниках.</span><span class="sxs-lookup"><span data-stu-id="8caa6-152">Installation of additional network interface cards (NICs) to allow the configuration of a specific PSTN IP address is supported on standalone Mediation Servers.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

