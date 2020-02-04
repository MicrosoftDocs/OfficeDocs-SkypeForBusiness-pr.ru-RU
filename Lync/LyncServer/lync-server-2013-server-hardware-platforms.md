---
title: 'Lync Server 2013: аппаратные серверные платформы'
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
ms.openlocfilehash: 95c8b0e9b1e13d845672cff07d30b7f2ac1a5b22
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764877"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="server-hardware-platforms-for-lync-server-2013"></a><span data-ttu-id="d6c71-102">Аппаратные серверные платформы для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d6c71-102">Server hardware platforms for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d6c71-103">_**Тема последнего изменения:** 2016-07-28_</span><span class="sxs-lookup"><span data-stu-id="d6c71-103">_**Topic Last Modified:** 2016-07-28_</span></span>

<span data-ttu-id="d6c71-104">Для серверных ролей Lync Server 2013 и компьютеров с запущенными средствами администрирования Lync Server требуется 64-разрядное оборудование.</span><span class="sxs-lookup"><span data-stu-id="d6c71-104">Lync Server 2013 server roles and computers running Lync Server administrative tools require 64-bit hardware.</span></span>

<span data-ttu-id="d6c71-105">Конкретное оборудование, используемое для развертывания Lync Server 2013, может отличаться в зависимости от требований к размеру и использованию.</span><span class="sxs-lookup"><span data-stu-id="d6c71-105">The specific hardware used for Lync Server 2013 deployment can vary, depending on size and usage requirements.</span></span> <span data-ttu-id="d6c71-106">В данном разделе описывается рекомендованное оборудование.</span><span class="sxs-lookup"><span data-stu-id="d6c71-106">This section describes the recommended hardware.</span></span> <span data-ttu-id="d6c71-107">Несмотря на то, что это рекомендации, а не требования, использование оборудования, не соответствующего рекомендациям, может привести к серьезным проблемам с производительностью и другим сложностям.</span><span class="sxs-lookup"><span data-stu-id="d6c71-107">Although these are recommendations, not requirements, using hardware that does not meet these recommendations may result in significant performance issues and other issues.</span></span>

<div>

## <a name="recommended-hardware-platform"></a><span data-ttu-id="d6c71-108">Рекомендуемая аппаратная платформа</span><span class="sxs-lookup"><span data-stu-id="d6c71-108">Recommended Hardware Platform</span></span>

<span data-ttu-id="d6c71-109">Для оптимальной производительности рекомендуется запускать Lync Server на серверах с оборудованием, удовлетворяющим требованиям в приведенной ниже таблице.</span><span class="sxs-lookup"><span data-stu-id="d6c71-109">For best performance, we recommend that you run Lync Server on servers with hardware that meets the requirements in the following table.</span></span> <span data-ttu-id="d6c71-110">Если вы используете менее мощное оборудование, то могут возникать проблемы с функциональностью или с низкой производительностью.</span><span class="sxs-lookup"><span data-stu-id="d6c71-110">If you use less powerful hardware, you may experience functionality problems or poor performance.</span></span> <span data-ttu-id="d6c71-111">Обратите внимание на то, что эти требования к оборудованию выше, чем в предыдущих версиях Lync Server, главным образом из-за того, что в Lync Server 2013 все серверные серверы работают под управлением SQL Server.</span><span class="sxs-lookup"><span data-stu-id="d6c71-111">Note that these hardware requirements are higher than those of previous versions of Lync Server, primarily because in Lync Server 2013, all Front End Servers run SQL Server.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d6c71-112">Объединение сетевых карт поддерживается и должно быть прозрачным для Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d6c71-112">NIC teaming is supported and should be transparent to Lync Server.</span></span> <span data-ttu-id="d6c71-113">Дополнительные сведения можно найти в разделе <A href="http://go.microsoft.com/fwlink/p/?linkid=389910">коммуникационный сервер или Lync Server и сетевая плата</A>.</span><span class="sxs-lookup"><span data-stu-id="d6c71-113">For details, see <A href="http://go.microsoft.com/fwlink/p/?linkid=389910">Communications Server or Lync Server and network adapter teaming</A>.</span></span>



</div>

### <a name="recommended-hardware-for-front-end-servers-back-end-servers-standard-edition-servers-persistent-chat-servers-and-persistent-chat-store-and-persistent-chat-compliance-store-back-end-server-roles-for-persistent-chat-server"></a><span data-ttu-id="d6c71-114">Рекомендуемое оборудование для серверов переднего плана, тыловых серверов, серверов Standard Edition, серверов сохраняемых чатов, хранилища сохраняемого чата и хранилища соответствия сохраняемого чата (роли тыловых серверов для сервера сохраняемого чата)</span><span class="sxs-lookup"><span data-stu-id="d6c71-114">Recommended Hardware for Front End Servers, Back End Servers, Standard Edition Servers, Persistent Chat Servers, and Persistent Chat Store and Persistent Chat Compliance Store (Back End Server Roles for Persistent Chat Server)</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d6c71-115">Аппаратный компонент</span><span class="sxs-lookup"><span data-stu-id="d6c71-115">Hardware component</span></span></th>
<th><span data-ttu-id="d6c71-116">Рекомендуется</span><span class="sxs-lookup"><span data-stu-id="d6c71-116">Recommended</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d6c71-117">ЦП</span><span class="sxs-lookup"><span data-stu-id="d6c71-117">CPU</span></span></p></td>
<td><p><span data-ttu-id="d6c71-118">Два 64-разрядных шестиядерных процессора с частотой 2,26 ГГц или выше.</span><span class="sxs-lookup"><span data-stu-id="d6c71-118">64-bit dual processor, hex-core, 2.26 gigahertz (GHz) or higher.</span></span></p>
<p><span data-ttu-id="d6c71-119">Процессоры Intel Itanium не поддерживаются для ролей сервера Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d6c71-119">Intel Itanium processors are not supported for Lync Server server roles.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d6c71-120">Память</span><span class="sxs-lookup"><span data-stu-id="d6c71-120">Memory</span></span></p></td>
<td><p><span data-ttu-id="d6c71-121">32 ГБ.</span><span class="sxs-lookup"><span data-stu-id="d6c71-121">32 gigabytes (GB).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d6c71-122">Диск</span><span class="sxs-lookup"><span data-stu-id="d6c71-122">Disk</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="d6c71-123">8 или больше дисков со скоростью вращения 10 000 об/мин и как минимум 72 ГБ свободного места.</span><span class="sxs-lookup"><span data-stu-id="d6c71-123">8 or more 10,000 RPM hard disk drives with at least 72 GB free disk space.</span></span></p>
<p><span data-ttu-id="d6c71-124">Два диска должны использовать массив RAID 1, а остальные шесть — RAID 10.</span><span class="sxs-lookup"><span data-stu-id="d6c71-124">Two of the disks should use RAID 1, and six should use RAID 10.</span></span></p>
<p><span data-ttu-id="d6c71-125">-/</span><span class="sxs-lookup"><span data-stu-id="d6c71-125">- OR -</span></span></p></li>
<li><p><span data-ttu-id="d6c71-126">Твердотельные накопители (SSD) с производительностью, аналогичной производительности 8 жестких дисков с частотой вращения шпинделя 10 000 об/мин. </span><span class="sxs-lookup"><span data-stu-id="d6c71-126">Solid state drives (SSDs) which provide performance similar to 8 10,000-RPM mechanical disk drives.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d6c71-127">Сеть</span><span class="sxs-lookup"><span data-stu-id="d6c71-127">Network</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="d6c71-128">1 двухпортовый сетевой адаптер, 1 Гбит/с или выше (рекомендуется 2 Гбит/с, для этого требуется объединение через один MAC-адрес и один IP-адрес).</span><span class="sxs-lookup"><span data-stu-id="d6c71-128">1 dual-port network adapter, 1 Gbps or higher (2 recommended, which requires teaming with a single MAC address and single IP address).</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="d6c71-129">Двух- и многоадресные конфигурации не поддерживаются для серверов переднего плана, внутренних серверов, серверов Standard Edition и серверов сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="d6c71-129">Dual or multi-homed configurations are not supported for Front End Servers, Back End Servers, Standard Edition servers, and Persistent Chat Servers.</span></span><BR><span data-ttu-id="d6c71-130">ILO/DRAC и т. д. соединения, недоступные операционной системе и используемые для мониторинга и управления аппаратным обеспечением сервера, не составляют многосетевой сервер и поэтому поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="d6c71-130">ILO/DRAC/etc. connections not exposed to the Operating System and used to monitor and manage the server hardware do not constitute a multi-homed server and thus are supported.</span></span>


</div></li>
</ul></td>
</tr>
</tbody>
</table>


### <a name="recommended-hardware-for-edge-servers-standalone-mediation-servers-and-directors"></a><span data-ttu-id="d6c71-131">Рекомендуемое оборудование для пограничных серверов, изолированных серверов-посредников и Директоров</span><span class="sxs-lookup"><span data-stu-id="d6c71-131">Recommended Hardware for Edge Servers, Standalone Mediation Servers, and Directors</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d6c71-132">Аппаратный компонент</span><span class="sxs-lookup"><span data-stu-id="d6c71-132">Hardware component</span></span></th>
<th><span data-ttu-id="d6c71-133">Рекомендуется</span><span class="sxs-lookup"><span data-stu-id="d6c71-133">Recommended</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d6c71-134">ЦП</span><span class="sxs-lookup"><span data-stu-id="d6c71-134">CPU</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="d6c71-135">64-разрядный двухъядерный процессор с тактовой частотой от 1 до 2,0 ГГц или выше.</span><span class="sxs-lookup"><span data-stu-id="d6c71-135">64-bit dual processor, quad-core, 2.0 gigahertz (GHz) or higher.</span></span></p>
<p><span data-ttu-id="d6c71-136">-/</span><span class="sxs-lookup"><span data-stu-id="d6c71-136">- OR -</span></span></p></li>
<li><p><span data-ttu-id="d6c71-137">64-разрядный процессор с тактовой частотой 1 ГГц или более 2,0 двухъядерный</span><span class="sxs-lookup"><span data-stu-id="d6c71-137">64-bit 4-way processor, dual-core, 2.0 GHz or higher.</span></span></p></li>
</ul>
<p><span data-ttu-id="d6c71-138">Процессоры Intel Itanium не поддерживаются для ролей сервера Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d6c71-138">Intel Itanium processors are not supported for Lync Server server roles.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d6c71-139">Память</span><span class="sxs-lookup"><span data-stu-id="d6c71-139">Memory</span></span></p></td>
<td><p><span data-ttu-id="d6c71-140">16 гигабайт (ГБ).</span><span class="sxs-lookup"><span data-stu-id="d6c71-140">16 gigabytes (GB).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d6c71-141">Диск</span><span class="sxs-lookup"><span data-stu-id="d6c71-141">Disk</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="d6c71-142">4 или более 10 000 ГБ свободного места на диске емкостью не менее 72 Гбайт.</span><span class="sxs-lookup"><span data-stu-id="d6c71-142">4 or more 10,000 RPM hard disk drives with at least 72 GB free disk space.</span></span></p>
<p><span data-ttu-id="d6c71-143">Диски должны иметь конфигурацию из 2 дисков RAID 1.</span><span class="sxs-lookup"><span data-stu-id="d6c71-143">The disks should be in a 2x RAID 1 configuration.</span></span></p>
<p><span data-ttu-id="d6c71-144">-/</span><span class="sxs-lookup"><span data-stu-id="d6c71-144">- OR -</span></span></p></li>
<li><p><span data-ttu-id="d6c71-145">Твердотельные накопители (SSD) с производительностью, аналогичной производительности 4 жестких дисков с частотой вращения шпинделя 10 000 об/мин. </span><span class="sxs-lookup"><span data-stu-id="d6c71-145">Solid state drives (SSDs) which provide performance similar to 4 10,000-RPM mechanical disk drives.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d6c71-146">Сеть</span><span class="sxs-lookup"><span data-stu-id="d6c71-146">Network</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="d6c71-147">1 двухпортовый сетевой адаптер, 1 Гбит/с или выше (рекомендуется 2 Гбит/с, для этого требуется объединение через один MAC-адрес и один IP-адрес).</span><span class="sxs-lookup"><span data-stu-id="d6c71-147">1 dual-port network adapter, 1 Gbps or higher (2 recommended, which requires teaming with a single MAC address and single IP address).</span></span> <span data-ttu-id="d6c71-148">2 сетевые интерфейсы требуются на пограничных серверах и поддерживаются на отдельных серверах обновлений.</span><span class="sxs-lookup"><span data-stu-id="d6c71-148">2 network interfaces are required on Edge Servers, and are supported on standalone Mediation Servers.</span></span></p></li>
</ul>
<div>

> [!NOTE]  
> <span data-ttu-id="d6c71-149">Конфигурации с двумя или несколькими сетевыми конфигурациями не поддерживаются для режиссеров.</span><span class="sxs-lookup"><span data-stu-id="d6c71-149">Dual or multi-homed configurations are not supported for Directors.</span></span><BR><span data-ttu-id="d6c71-150">ILO/DRAC и т. д. соединения, недоступные операционной системе и используемые для мониторинга и управления аппаратным обеспечением сервера, не составляют многосетевой сервер и поэтому поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="d6c71-150">ILO/DRAC/etc. connections not exposed to the Operating System and used to monitor and manage the server hardware do not constitute a multi-homed server and thus are supported.</span></span>


</div>
<p><span data-ttu-id="d6c71-151">Пограничные серверы требуют двух сетевых интерфейсов, которые являются сетевыми адаптерами с двумя портами: 1 Гбит/с или выше (или двумя парными сетевыми адаптерами, для каждой пары, состоящую из одного MAC-адреса и одним IP-адресом, для всего двух пар).</span><span class="sxs-lookup"><span data-stu-id="d6c71-151">Edge Servers will require two network interfaces that are dual-port network adapters, 1 Gbps or higher (or two paired network adapters, for a total of four, each pair being teamed with a single MAC address and a single IP address, for a total of two pairs).</span></span></p>
<p><span data-ttu-id="d6c71-152">Установка дополнительных сетевых интерфейсных карт (NIC), позволяющая настроить конкретный IP-адрес PSTN, будет поддерживаться на отдельных серверах обновлений.</span><span class="sxs-lookup"><span data-stu-id="d6c71-152">Installation of additional network interface cards (NICs) to allow the configuration of a specific PSTN IP address is supported on standalone Mediation Servers.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

