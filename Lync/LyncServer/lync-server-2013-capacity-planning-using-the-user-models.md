---
title: Планирование мощности Lync Server 2013 с использованием пользовательских моделей
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Capacity planning using the user models
ms:assetid: 902ab23e-94d6-482a-9d6e-c0b28dc3e03d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615015(v=OCS.15)
ms:contentKeyID: 49733733
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ab2b7026ca49f8e12a5f8b67aa0780996feaebe1
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42036489"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="capacity-planning-for-lync-server-2013-using-the-user-models"></a><span data-ttu-id="e3dd9-102">Планирование емкости для Lync Server 2013 с использованием пользовательских моделей</span><span class="sxs-lookup"><span data-stu-id="e3dd9-102">Capacity planning for Lync Server 2013 using the user models</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e3dd9-103">_**Последнее изменение темы:** 2014-01-14_</span><span class="sxs-lookup"><span data-stu-id="e3dd9-103">_**Topic Last Modified:** 2014-01-14_</span></span>

<span data-ttu-id="e3dd9-104">В этом разделе приводятся рекомендации по количеству серверов, необходимых на сайте, для количества пользователей на этом сайте в соответствии с описанием использования, описанными в статье [User Models in Lync Server 2013](lync-server-2013-user-models.md).</span><span class="sxs-lookup"><span data-stu-id="e3dd9-104">This section provides guidance on how many servers you need at a site for the number of users at that site, according to the usage described in [User models in Lync Server 2013](lync-server-2013-user-models.md).</span></span>

<div>

## <a name="tested-hardware-platform"></a><span data-ttu-id="e3dd9-105">Аппаратная платформа для тестирования</span><span class="sxs-lookup"><span data-stu-id="e3dd9-105">Tested Hardware Platform</span></span>

<span data-ttu-id="e3dd9-106">Все результаты тестирования и рекомендации по развертыванию, приведенные в этом разделе, основаны на тестировании производительности на серверах, конфигурация которых описана в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="e3dd9-106">All the performance results and deployment recommendations in this section are based on performance testing on servers running the hardware described in the following table.</span></span> <span data-ttu-id="e3dd9-107">Рекомендуется использовать аналогичное оборудование.</span><span class="sxs-lookup"><span data-stu-id="e3dd9-107">We recommend that you use similar hardware.</span></span> <span data-ttu-id="e3dd9-108">Использование менее мощного оборудования может привести к проблемам функциональности или низкой производительности.</span><span class="sxs-lookup"><span data-stu-id="e3dd9-108">If you use less powerful hardware, you may experience functionality problems or poor performance.</span></span> <span data-ttu-id="e3dd9-109">Обратите внимание на то, что эти рекомендации по оборудованию выше, чем в предыдущих версиях Lync Server.</span><span class="sxs-lookup"><span data-stu-id="e3dd9-109">Note that these hardware recommendations are higher than those of previous versions of Lync Server.</span></span>

### <a name="hardware-used-in-performance-testing"></a><span data-ttu-id="e3dd9-110">Оборудование, использованное при проведении тестирования</span><span class="sxs-lookup"><span data-stu-id="e3dd9-110">Hardware Used in Performance Testing</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e3dd9-111">Компонент оборудования</span><span class="sxs-lookup"><span data-stu-id="e3dd9-111">Hardware component</span></span></th>
<th><span data-ttu-id="e3dd9-112">Рекомендовано</span><span class="sxs-lookup"><span data-stu-id="e3dd9-112">Recommended</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e3dd9-113">ЦП</span><span class="sxs-lookup"><span data-stu-id="e3dd9-113">CPU</span></span></p></td>
<td><p><span data-ttu-id="e3dd9-114">Два 64-разрядных шестиядерных процессора 2,26 ГГц или более мощных</span><span class="sxs-lookup"><span data-stu-id="e3dd9-114">64-bit dual processor, hex-core, 2.26 gigahertz (GHz) or higher</span></span></p>
<p><span data-ttu-id="e3dd9-115">Процессоры Intel Itanium не поддерживаются для ролей сервера Lync Server.</span><span class="sxs-lookup"><span data-stu-id="e3dd9-115">Intel Itanium processors are not supported for Lync Server server roles.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e3dd9-116">Память</span><span class="sxs-lookup"><span data-stu-id="e3dd9-116">Memory</span></span></p></td>
<td><p><span data-ttu-id="e3dd9-117">32 ГБ</span><span class="sxs-lookup"><span data-stu-id="e3dd9-117">32 gigabytes (GB)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e3dd9-118">Диск</span><span class="sxs-lookup"><span data-stu-id="e3dd9-118">Disk</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="e3dd9-119">8 или больше дисков со скоростью вращения 10000 об/мин и как минимум 72 ГБ свободного места.</span><span class="sxs-lookup"><span data-stu-id="e3dd9-119">8 or more 10,000-RPM hard disk drives with at least 72 GB free disk space.</span></span></p>
<p><span data-ttu-id="e3dd9-120">Два диска должны использовать RAID 1, а шесть остальных — RAID 10.</span><span class="sxs-lookup"><span data-stu-id="e3dd9-120">Two of the disks should use RAID 1, and six should use RAID 10.</span></span></p>
<p><span data-ttu-id="e3dd9-121">-Также</span><span class="sxs-lookup"><span data-stu-id="e3dd9-121">- OR -</span></span></p></li>
<li><p><span data-ttu-id="e3dd9-122">Твердотельные накопители (SSD), производительность которых аналогична 8 механическим дискам со скоростью вращения 10000 об/мин.</span><span class="sxs-lookup"><span data-stu-id="e3dd9-122">Solid state drives (SSDs) which provide performance similar to 8 10,000-RPM mechanical disk drives.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e3dd9-123">Сеть</span><span class="sxs-lookup"><span data-stu-id="e3dd9-123">Network</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="e3dd9-124">1 двухпортовый сетевой адаптер, 1 Гбит/с или выше (рекомендуется 2, что требует объединения с одним MAC-адресом и одним IP-адресом)</span><span class="sxs-lookup"><span data-stu-id="e3dd9-124">1 dual-port network adapter, 1 Gbps or higher (2 recommended, which requires teaming with a single MAC address and single IP address)</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="summary-of-results"></a><span data-ttu-id="e3dd9-125">Сводка результатов</span><span class="sxs-lookup"><span data-stu-id="e3dd9-125">Summary of Results</span></span>

<span data-ttu-id="e3dd9-126">В следующей таблице приведена сводка по рекомендациям.</span><span class="sxs-lookup"><span data-stu-id="e3dd9-126">The following table summarizes these recommendations.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e3dd9-127">Роль сервера</span><span class="sxs-lookup"><span data-stu-id="e3dd9-127">Server role</span></span></th>
<th><span data-ttu-id="e3dd9-128">Максимальное число поддерживаемых пользователей</span><span class="sxs-lookup"><span data-stu-id="e3dd9-128">Maximum number of users supported</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e3dd9-129">Интерфейсный пул с двенадцать серверами переднего плана и одним внутренним сервером или зеркальным набором зеркальных серверов.</span><span class="sxs-lookup"><span data-stu-id="e3dd9-129">Front End pool with twelve Front End Servers and one Back End Server or a mirrored pair of Back End Servers.</span></span></p></td>
<td><p><span data-ttu-id="e3dd9-130">80000 одновременно зарегистрированных уникальных пользователей, плюс 50% пользователей с несколькими точками присутствия, представляющими немобильные экземпляры, плюс 40% пользователей Mobility; итого 152000 конечных точек.</span><span class="sxs-lookup"><span data-stu-id="e3dd9-130">80,000 unique users simultaneously logged in, plus 50% multiple points of presence (MPOP) representing non-mobile instances, plus 40% of users enabled for Mobility for a total of 152,000 endpoints.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e3dd9-131">Аудио- и видеоконференции</span><span class="sxs-lookup"><span data-stu-id="e3dd9-131">A/V Conferencing</span></span></p></td>
<td><p><span data-ttu-id="e3dd9-132">Служба аудио-и видеоконференций, предоставляемая интерфейсным пулом, поддерживает конференц-связи пула с максимальным размером конференции 250 пользователей и только одной такой большой конференц-связью, запущенной за раз.</span><span class="sxs-lookup"><span data-stu-id="e3dd9-132">The A/V Conferencing service provided by a Front End pool supports the pool’s conferences assuming a maximum conference size of 250 users, and only one such large conference running at a time.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="e3dd9-133">Кроме того, вы можете поддерживать большие конференции между пользователями 250 и 1000, развертывая отдельный пул переднего плана с двумя серверами переднего плана для размещения больших конференций.</span><span class="sxs-lookup"><span data-stu-id="e3dd9-133">Additionally, you can support large conferences of between 250 and 1000 users by deploying a separate Front End pool with two Front End Servers to host the large conferences.</span></span> <span data-ttu-id="e3dd9-134">Дополнительные сведения см. <A href="lync-server-2013-supporting-large-meetings.md">в статье поддержка больших собраний с помощью Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="e3dd9-134">For details, see <A href="lync-server-2013-supporting-large-meetings.md">Supporting large meetings using Lync Server 2013</A>.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e3dd9-135">Один пограничный сервер</span><span class="sxs-lookup"><span data-stu-id="e3dd9-135">One Edge Server</span></span></p></td>
<td><p><span data-ttu-id="e3dd9-136">12 000 одновременно работающих удаленных пользователей</span><span class="sxs-lookup"><span data-stu-id="e3dd9-136">12,000 concurrent remote users</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e3dd9-137">Один директор</span><span class="sxs-lookup"><span data-stu-id="e3dd9-137">One Director</span></span></p></td>
<td><p><span data-ttu-id="e3dd9-138">12 000 одновременно работающих удаленных пользователей</span><span class="sxs-lookup"><span data-stu-id="e3dd9-138">12,000 concurrent remote users</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e3dd9-139">Мониторинг и архивация</span><span class="sxs-lookup"><span data-stu-id="e3dd9-139">Monitoring and Archiving</span></span></p></td>
<td><p><span data-ttu-id="e3dd9-140">В Lync Server 2013 серверные службы мониторинга и архивации теперь выполняются на каждом сервере переднего плана, а не в отдельных ролях сервера.</span><span class="sxs-lookup"><span data-stu-id="e3dd9-140">In Lync Server 2013, the Monitoring and Archiving front end services now run on each Front End Server, instead of on separate server roles.</span></span></p>
<p><span data-ttu-id="e3dd9-141">Для мониторинга и архивации требуются собственные хранилища баз данных.</span><span class="sxs-lookup"><span data-stu-id="e3dd9-141">Monitoring and Archiving each still require their own database stores.</span></span> <span data-ttu-id="e3dd9-142">Если вы также запускаете Exchange 2013, вы можете хранить данные архивации в Exchange, а не в выделенной базе данных SQL.</span><span class="sxs-lookup"><span data-stu-id="e3dd9-142">If you also run Exchange 2013, you can keep your Archiving data in Exchange, rather than in a dedicated SQL database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e3dd9-143">Один сервер-посредник</span><span class="sxs-lookup"><span data-stu-id="e3dd9-143">One Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="e3dd9-144">Сервер-посредник, размещенный на сервере переднего плана, работает на каждом сервере переднего плана в пуле и должен обеспечивать достаточную емкость для пользователей в пуле.</span><span class="sxs-lookup"><span data-stu-id="e3dd9-144">Mediation Server collocated with Front End Server runs on every Front End Server in a pool, and should provide enough capacity for the users in the pool.</span></span> <span data-ttu-id="e3dd9-145">Для автономного сервера-посредника ознакомьтесь с разделом "сервер-посредник" Далее в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="e3dd9-145">For stand-alone Mediation Server, see the “Mediation Server” section later in this topic.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e3dd9-146">Один сервер Standard Edition</span><span class="sxs-lookup"><span data-stu-id="e3dd9-146">One Standard Edition server</span></span></p></td>
<td><p><span data-ttu-id="e3dd9-147">Мы настоятельно рекомендуем использовать для размещения пользователей серверы Standard Edition, которые применяют два сервера, в сочетании с рекомендациями по <a href="lync-server-2013-planning-for-high-availability-and-disaster-recovery.md">планированию обеспечения высокой доступности и аварийного восстановления в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="e3dd9-147">We strongly recommend that if you use Standard Edition servers to host users, you always use two servers, paired using the recommendations in <a href="lync-server-2013-planning-for-high-availability-and-disaster-recovery.md">Planning for high availability and disaster recovery in Lync Server 2013</a>.</span></span> <span data-ttu-id="e3dd9-148">Каждый сервер в каждой из них может размещаться до 2 500 пользователей, и если один из серверов не проходит, то в сценарии отработки отказа может 5 000 поддерживаться оставшийся сервер.</span><span class="sxs-lookup"><span data-stu-id="e3dd9-148">Each server in the pair can host up to 2,500 users, and if one server fails the remaining server can support 5,000 users in a failover scenario.</span></span></p>
<p><span data-ttu-id="e3dd9-149">Если развертывание включает в себя значительный объем аудио и видеоданных, производительность сервера может снизиться более 2 500 пользователей на сервер.</span><span class="sxs-lookup"><span data-stu-id="e3dd9-149">If your deployment includes a significant amount of audio or video traffic, server performance may suffer with more than 2,500 users per server.</span></span> <span data-ttu-id="e3dd9-150">В этом случае следует рассмотреть добавление дополнительных серверов Standard Edition или переход на Lync Server Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="e3dd9-150">In this case, you should consider adding more Standard Edition servers or moving to Lync Server Enterprise Edition.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="front-end-server"></a><span data-ttu-id="e3dd9-151">Сервер переднего плана</span><span class="sxs-lookup"><span data-stu-id="e3dd9-151">Front End Server</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e3dd9-152">Растянутые пулы не поддерживаются для этой роли сервера.</span><span class="sxs-lookup"><span data-stu-id="e3dd9-152">Stretched pools are not supported for this server role.</span></span>



</div>

<span data-ttu-id="e3dd9-153">В пуле переднего плана должен быть один сервер переднего плана для каждых 6 660 пользователей, размещенных в пуле, предполагая, что технология Hyper-Threading включена на всех серверах в пуле, а оборудование сервера соответствует рекомендациям [серверных аппаратных платформ для Lync Server 2013](lync-server-2013-server-hardware-platforms.md).</span><span class="sxs-lookup"><span data-stu-id="e3dd9-153">In a Front End pool, you should have one Front End Server for every 6,660 users homed in the pool, assuming that hyper-threading is enabled on all servers in the pool, and that the server hardware meets the recommendations in [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md).</span></span> <span data-ttu-id="e3dd9-154">Максимальное число пользователей в одном интерфейсном пуле — 80 000, предполагая, что технология Hyper-Threading включена на всех серверах в пуле.</span><span class="sxs-lookup"><span data-stu-id="e3dd9-154">The maximum number of users in one Front End pool is 80,000, assuming that hyper-threading is enabled on all the servers in the pool.</span></span> <span data-ttu-id="e3dd9-155">Если на сайте больше 80 000 пользователей, можно развернуть несколько интерфейсных пулов.</span><span class="sxs-lookup"><span data-stu-id="e3dd9-155">If you have more than 80,000 users at a site, you can deploy more than one Front End pool.</span></span>

<span data-ttu-id="e3dd9-156">При учете количества пользователей в пуле переднего плана Включите пользователей, размещенных на устройствах для обеспечения связи в филиалах и серверах для обеспечения связи в филиалах, связанных с этим интерфейсным пулом.</span><span class="sxs-lookup"><span data-stu-id="e3dd9-156">When you account for the number of users in a Front End pool, include the users homed on Survivable Branch Appliances and Survivable Branch Servers at branch offices that are associated with this Front End pool.</span></span>

<span data-ttu-id="e3dd9-157">Если активный сервер недоступен, его подключения автоматически перенаправляются на другие серверы в пуле.</span><span class="sxs-lookup"><span data-stu-id="e3dd9-157">When an active server is unavailable, its connections are transferred automatically to the other servers in the pool.</span></span> <span data-ttu-id="e3dd9-158">Например, если у вас 30 000 пользователей и пять серверов переднего плана, то если один сервер недоступен, то при подключении пользователей 6000 необходимо перенести их на остальные четыре сервера.</span><span class="sxs-lookup"><span data-stu-id="e3dd9-158">For example, if you have 30,000 users and five Front End Servers, then if one server is unavailable, the connections of 6000 users need to be transferred to the other four servers.</span></span> <span data-ttu-id="e3dd9-159">На каждом из оставшихся серверов будет по 7500 пользователей, а это число больше рекомендованного.</span><span class="sxs-lookup"><span data-stu-id="e3dd9-159">The remaining four servers will each have 7500 users, which is a larger number than recommended.</span></span>

<span data-ttu-id="e3dd9-160">Если вместо этого были запущены шесть серверов переднего плана для пользователей 30 000, а затем они становятся недоступными, общее количество пользователей 5000 перемещается на оставшиеся пять серверов.</span><span class="sxs-lookup"><span data-stu-id="e3dd9-160">If instead you had started with six Front End Servers for your 30,000 users and subsequently one became unavailable, a total of 5000 users will be moved to the remaining five servers.</span></span> <span data-ttu-id="e3dd9-161">На каждом из этих пяти серверов будет размещаться по 6000 пользователей, и это число не превышает рекомендованное значение.</span><span class="sxs-lookup"><span data-stu-id="e3dd9-161">These five servers will each host 6000 users, which is in the recommended range.</span></span>

<span data-ttu-id="e3dd9-162">Максимальное число пользователей в пуле переднего плана составляет 80 000.</span><span class="sxs-lookup"><span data-stu-id="e3dd9-162">The maximum number of users in a Front End pool is 80,000.</span></span> <span data-ttu-id="e3dd9-163">Максимальное число серверов переднего плана в пуле составляет 12.</span><span class="sxs-lookup"><span data-stu-id="e3dd9-163">The maximum number of Front End Servers in a pool is 12.</span></span>

<span data-ttu-id="e3dd9-164">Для пула переднего плана с 80 000 пользователями для повышения производительности достаточно двенадцати серверов переднего плана в типичных развертываниях, которые следуют [пользовательским моделям в Lync Server 2013](lync-server-2013-user-models.md).</span><span class="sxs-lookup"><span data-stu-id="e3dd9-164">For a Front End pool with 80,000 users, twelve Front End Servers is sufficient for performance, in typical deployments that follow the [User models in Lync Server 2013](lync-server-2013-user-models.md).</span></span> <span data-ttu-id="e3dd9-165">В развертываниях, предназначенных для обеспечения отказоустойчивости аварийного восстановления, предполагается, что в каждом из двух подключенных пулов переднего плана может быть размещено не более 40 000 пользователей, в которых каждый пул имеет достаточное количество серверов переднего плана для размещения пользователей в обоих пулах. к другому.</span><span class="sxs-lookup"><span data-stu-id="e3dd9-165">Deployments designed to support disaster recovery failover assume that a maximum of 40,000 users can be hosted in each of two paired Front End pools, in which each pool has enough Front End Servers to accommodate the users in both pools should one pool need to be failed over to the other.</span></span>

<span data-ttu-id="e3dd9-166">Количество пользователей, поддерживаемых с высокой производительностью для определенного пула переднего плана, может отличаться от этих номеров по следующим причинам:</span><span class="sxs-lookup"><span data-stu-id="e3dd9-166">The number of users supported with good performance by a particular Front End pool may differ from these numbers for the following reasons:</span></span>

  - <span data-ttu-id="e3dd9-167">Оборудование для серверов переднего плана не соответствует рекомендациям [серверных аппаратных платформ для Lync server 2013](lync-server-2013-server-hardware-platforms.md).</span><span class="sxs-lookup"><span data-stu-id="e3dd9-167">The hardware for your Front End Servers does not meet the recommendations in [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md).</span></span>

  - <span data-ttu-id="e3dd9-168">Сценарий использования в организации существенно отличается от пользовательских моделей, например, трафик конференций значительно больше.</span><span class="sxs-lookup"><span data-stu-id="e3dd9-168">Your organization’s usage differs significantly from the user models, such as significantly more conferencing traffic.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="e3dd9-169">В Lync Server 2013 базы данных присутствия теперь размещаются на серверах переднего плана, в отличие от Lync Server 2010, где они были размещены на внутреннем сервере.</span><span class="sxs-lookup"><span data-stu-id="e3dd9-169">In Lync Server 2013, the presence databases are now hosted on Front End Servers, unlike in Lync Server 2010 where they were hosted on the Back End Server.</span></span> <span data-ttu-id="e3dd9-170">Это означает, что производительность и емкость диска серверов переднего плана не должны быть раскрыты в соответствии с рекомендациями, приведенными выше в этом разделе, и в <A href="lync-server-2013-server-hardware-platforms.md">серверных аппаратных платформах для Lync Server 2013</A>, независимо от количества пользователей, размещенных на серверах переднего плана.</span><span class="sxs-lookup"><span data-stu-id="e3dd9-170">This means that the disk performance and capacity of your Front End Servers should not be compromised from the recommendations listed earlier in this section and in <A href="lync-server-2013-server-hardware-platforms.md">Server hardware platforms for Lync Server 2013</A>, regardless of the number of users hosted by your Front End Servers.</span></span>



</div>

<span data-ttu-id="e3dd9-171">В следующей таблице показана средняя пропускная способность для обмена мгновенными сообщениями и присутствия при наличии пользовательской модели, как определено в [пользовательских моделях в Lync Server 2013](lync-server-2013-user-models.md).</span><span class="sxs-lookup"><span data-stu-id="e3dd9-171">The following table shows the average bandwidth for IM and presence, given the user model, as defined in [User models in Lync Server 2013](lync-server-2013-user-models.md).</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e3dd9-172">Средняя пропускная способность на пользователя</span><span class="sxs-lookup"><span data-stu-id="e3dd9-172">Average bandwidth per user</span></span></th>
<th><span data-ttu-id="e3dd9-173">Требования к пропускной способности для сервера переднего плана с 6 660 пользователей</span><span class="sxs-lookup"><span data-stu-id="e3dd9-173">Bandwidth requirements per Front End Server with 6,660 users</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e3dd9-174">1,3 кбит/с</span><span class="sxs-lookup"><span data-stu-id="e3dd9-174">1.3 Kpbs</span></span></p></td>
<td><p><span data-ttu-id="e3dd9-175">13 Мбит/с</span><span class="sxs-lookup"><span data-stu-id="e3dd9-175">13 Mbps</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="e3dd9-176">Чтобы увеличить производительность мультимедийных функций совместной конференции и сервера-посредника на серверах переднего плана, следует включить масштабирование на стороне приема (RSS) в сетевых адаптерах на серверах переднего плана.</span><span class="sxs-lookup"><span data-stu-id="e3dd9-176">To improve the media performance of the co-located A/V Conferencing and Mediation Server functionality on your Front End Servers, you should enable receive-side scaling (RSS) on the network adapters on your Front End Servers.</span></span> <span data-ttu-id="e3dd9-177">RSS позволяет обрабатывать входящие пакеты параллельно несколькими процессорами на сервере.</span><span class="sxs-lookup"><span data-stu-id="e3dd9-177">RSS enables incoming packets to be handled in parallel by multiple processors on the server.</span></span> <span data-ttu-id="e3dd9-178">Дополнительные сведения см. в <A href="http://go.microsoft.com/fwlink/p/?linkid=268731">http://go.microsoft.com/fwlink/p/?linkId=268731</A>разделе "усовершенствованные возможности масштабирования на стороне Windows Server 2008".</span><span class="sxs-lookup"><span data-stu-id="e3dd9-178">For details, see "Receive-Side Scaling Enhancements in Windows Server 2008" at <A href="http://go.microsoft.com/fwlink/p/?linkid=268731">http://go.microsoft.com/fwlink/p/?linkId=268731</A>.</span></span> <span data-ttu-id="e3dd9-179">Сведения о том, как включить RSS, см. в документации сетевого адаптера.</span><span class="sxs-lookup"><span data-stu-id="e3dd9-179">For details about how to enable RSS, see your network adapter documentation.</span></span>



</div>

</div>

<div>

## <a name="conferencing-maximums"></a><span data-ttu-id="e3dd9-180">Максимумы конференц-связи</span><span class="sxs-lookup"><span data-stu-id="e3dd9-180">Conferencing Maximums</span></span>

<span data-ttu-id="e3dd9-181">Если пользовательская модель допускает, что 5% пользователей пула могут участвовать в конференциях в любой фиксированный момент времени, для пула из 80000 пользователей количество одновременно участвующих в конференциях пользователей составит около 4000.</span><span class="sxs-lookup"><span data-stu-id="e3dd9-181">Given the user model that 5% of users in a pool may be in a conference at any one time, a pool of 80,000 users could have about 4,000 users in conferences at one time.</span></span> <span data-ttu-id="e3dd9-182">Эти конференции могут использовать разные типы мультимедиа (например, некоторые могут использовать только обмен сообщениями, а другие — обмен сообщениями и аудио или аудио и видео) и охватывать разное количество участников.</span><span class="sxs-lookup"><span data-stu-id="e3dd9-182">These conferences are expected to be a mix of media (some IM-only, some IM with audio, some audio/video, for example) and number of participants.</span></span> <span data-ttu-id="e3dd9-183">Не существует жестких ограничений на количество конференций; реальную производительность определяет фактический сценарий использования.</span><span class="sxs-lookup"><span data-stu-id="e3dd9-183">There is no hard limit for the actual number of conferences allowed, and actual usage determines the actual performance.</span></span> <span data-ttu-id="e3dd9-184">Например, если в организации используется гораздо больше конференций в смешанном режиме, чем предполагается в пользовательской модели, может потребоваться развернуть дополнительные серверы переднего плана или серверы конференций аудио-и видеоконференций, чем рекомендации, приведенные в этом документе.</span><span class="sxs-lookup"><span data-stu-id="e3dd9-184">For example, if your organization has many more mixed-mode conferences than are assumed in the user model, you might need to deploy more Front End Servers or A/V Conferencing Servers than the recommendations in this document.</span></span> <span data-ttu-id="e3dd9-185">Сведения о допущениях в пользовательской модели можно найти в статье [User Models in Lync Server 2013](lync-server-2013-user-models.md).</span><span class="sxs-lookup"><span data-stu-id="e3dd9-185">For details about the assumptions in the user model, see [User models in Lync Server 2013](lync-server-2013-user-models.md).</span></span>

<span data-ttu-id="e3dd9-186">Максимальный поддерживаемый размер Конференции, размещенный в обычном интерфейсном пуле Lync Server 2013, в котором также размещаются пользователи, — 250 участников.</span><span class="sxs-lookup"><span data-stu-id="e3dd9-186">The maximum supported conference size hosted by a regular Lync Server 2013 Front End pool which also hosts users is 250 participants.</span></span> <span data-ttu-id="e3dd9-187">Во время проведения конференции с 250 пользователями пул также поддерживает другие конференции, но количество пользователей, одновременно участвующих в конференциях, не должно превышать 5% от общего числа пользователей пула.</span><span class="sxs-lookup"><span data-stu-id="e3dd9-187">While a 250-user conference is happening, the pool still supports other conferences as well, such that a total of 5% of pool users are in concurrent conferences.</span></span> <span data-ttu-id="e3dd9-188">Например, в пуле двенадцати серверов переднего плана и 80 000 пользователей, в то время как происходит конференция 250-User, Lync Server поддерживает 3 750 других пользователей, участвующих в небольших конференциях.</span><span class="sxs-lookup"><span data-stu-id="e3dd9-188">For example, in a pool of twelve Front End Servers and 80,000 users, while the 250-user conference is happening, Lync Server supports 3,750 other users participating in smaller conferences.</span></span>

<span data-ttu-id="e3dd9-189">Независимо от количества пользователей, размещенных в пуле переднего плана или сервера Standard Edition, Lync Server поддерживает минимум 125 других пользователей, участвующих в небольших конференциях в том же пуле или на сервере, где размещается конференция 250-User.</span><span class="sxs-lookup"><span data-stu-id="e3dd9-189">Regardless of the number of users homed on the Front End pool or Standard Edition server, Lync Server supports a minimum of 125 other users participating in smaller conferences on the same pool or server which is hosting a 250-user conference.</span></span>

<span data-ttu-id="e3dd9-190">Чтобы разрешить конференции между пользователями 250 и 1000, можно настроить отдельный пул переднего плана только для размещения этих конференций.</span><span class="sxs-lookup"><span data-stu-id="e3dd9-190">To enable conferences with between 250 and 1000 users, you can set up a separate Front End pool just to host those conferences.</span></span> <span data-ttu-id="e3dd9-191">В этом интерфейсном пуле не будут размещаться никакие пользователи.</span><span class="sxs-lookup"><span data-stu-id="e3dd9-191">This Front End pool will not host any users.</span></span> <span data-ttu-id="e3dd9-192">Дополнительные сведения см. [в статье поддержка больших собраний с помощью Lync Server 2013](lync-server-2013-supporting-large-meetings.md).</span><span class="sxs-lookup"><span data-stu-id="e3dd9-192">For details, see [Supporting large meetings using Lync Server 2013](lync-server-2013-supporting-large-meetings.md).</span></span>

<span data-ttu-id="e3dd9-193">Если в организации используется гораздо больше конференций в смешанном режиме, чем предполагается в пользовательской модели, может потребоваться развернуть больше серверов переднего плана, чем рекомендованных в этом документе (до 12 Фес).</span><span class="sxs-lookup"><span data-stu-id="e3dd9-193">If your organization has many more mixed-mode conferences than are assumed in the user model, you might need to deploy more Front End Servers than the recommendations in this document (up to a limit of 12 FEs).</span></span> <span data-ttu-id="e3dd9-194">Сведения о допущениях в пользовательской модели можно найти в статье [User Models in Lync Server 2013](lync-server-2013-user-models.md).</span><span class="sxs-lookup"><span data-stu-id="e3dd9-194">For details about the assumptions in the user model, see [User models in Lync Server 2013](lync-server-2013-user-models.md).</span></span>

</div>

<div>

## <a name="edge-server"></a><span data-ttu-id="e3dd9-195">Пограничный сервер</span><span class="sxs-lookup"><span data-stu-id="e3dd9-195">Edge Server</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e3dd9-196">Растянутые пулы не поддерживаются для этой роли сервера.</span><span class="sxs-lookup"><span data-stu-id="e3dd9-196">Stretched pools are not supported for this server role.</span></span>



</div>

<span data-ttu-id="e3dd9-197">Необходимо развернуть один пограничный сервер для каждых удаленных пользователей 12 000, которые будут обращаться к сайту параллельно.</span><span class="sxs-lookup"><span data-stu-id="e3dd9-197">You should deploy one Edge Server for every 12,000 remote users who will access a site concurrently.</span></span> <span data-ttu-id="e3dd9-198">Как минимум мы рекомендуем использовать два пограничных сервера для обеспечения высокой доступности.</span><span class="sxs-lookup"><span data-stu-id="e3dd9-198">At a minimum we recommend two Edge Servers for high availability.</span></span> <span data-ttu-id="e3dd9-199">В этих рекомендациях предполагается, что оборудование пограничных серверов соответствует рекомендациям [серверных аппаратных платформ для Lync server 2013](lync-server-2013-server-hardware-platforms.md).</span><span class="sxs-lookup"><span data-stu-id="e3dd9-199">These recommendations assume that the hardware for your Edge Servers meets the recommendations in [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md).</span></span>

<span data-ttu-id="e3dd9-200">При учете количества пользователей для пограничных серверов включите пользователей, размещенных на устройствах для обеспечения связи в филиалах и серверах для обеспечения связи в филиалах, которые связаны с пулом переднего плана на этом сайте.</span><span class="sxs-lookup"><span data-stu-id="e3dd9-200">When you account for the number of users for the Edge Servers, include the users homed on Survivable Branch Appliances and Survivable Branch Servers at branch offices that are associated with a Front End pool at this site.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e3dd9-201">Чтобы увеличить производительность пограничной службы аудио-и видеоконференций на пограничных серверах, следует включить масштабирование на стороне приема (RSS) на сетевых адаптерах на пограничных серверах.</span><span class="sxs-lookup"><span data-stu-id="e3dd9-201">To improve the performance of the A/V Conferencing Edge service on your Edge Servers, you should enable receive-side scaling (RSS) on the network adapters on your Edge Servers.</span></span> <span data-ttu-id="e3dd9-202">RSS позволяет обрабатывать входящие пакеты параллельно несколькими процессорами на сервере.</span><span class="sxs-lookup"><span data-stu-id="e3dd9-202">RSS enables incoming packets to be handled in parallel by multiple processors on the server.</span></span> <span data-ttu-id="e3dd9-203">Дополнительные сведения см. в <A href="http://go.microsoft.com/fwlink/p/?linkid=268731">http://go.microsoft.com/fwlink/p/?linkId=268731</A>разделе "усовершенствованные возможности масштабирования на стороне Windows Server 2008".</span><span class="sxs-lookup"><span data-stu-id="e3dd9-203">For details, see "Receive-Side Scaling Enhancements in Windows Server 2008" at <A href="http://go.microsoft.com/fwlink/p/?linkid=268731">http://go.microsoft.com/fwlink/p/?linkId=268731</A>.</span></span> <span data-ttu-id="e3dd9-204">Сведения о включении RSS см. в документации вашего сетевого адаптера.</span><span class="sxs-lookup"><span data-stu-id="e3dd9-204">For details about how to enable RSS, see your network adapter documentation.</span></span>



</div>

</div>

<div>

## <a name="director"></a><span data-ttu-id="e3dd9-205">Режиссер</span><span class="sxs-lookup"><span data-stu-id="e3dd9-205">Director</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e3dd9-206">Растянутые пулы не поддерживаются для этой роли сервера.</span><span class="sxs-lookup"><span data-stu-id="e3dd9-206">Stretched pools are not supported for this server role.</span></span>



</div>

<span data-ttu-id="e3dd9-207">При развертывании роли сервера Director рекомендуется развертывать один директор для каждого удаленного пользователя 12 000, который будет обращаться к сайту одновременно.</span><span class="sxs-lookup"><span data-stu-id="e3dd9-207">If you deploy the Director server role we recommend that you deploy one Director for every 12,000 remote users who will access a site concurrently.</span></span> <span data-ttu-id="e3dd9-208">Как минимум мы рекомендуем двум директорам для обеспечения высокой доступности.</span><span class="sxs-lookup"><span data-stu-id="e3dd9-208">At a minimum we recommend two Directors for high availability.</span></span> <span data-ttu-id="e3dd9-209">В этих рекомендациях предполагается, что оборудование пограничных серверов соответствует рекомендациям [серверных аппаратных платформ для Lync server 2013](lync-server-2013-server-hardware-platforms.md).</span><span class="sxs-lookup"><span data-stu-id="e3dd9-209">These recommendations assume that the hardware for your Edge Servers meets the recommendations in [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md).</span></span>

<span data-ttu-id="e3dd9-210">При учете количества пользователей для директоров Включите пользователей, размещенных на устройствах для обеспечения связи в филиалах и серверах для обеспечения связи в филиалах, которые связаны с пулом переднего плана на этом сайте.</span><span class="sxs-lookup"><span data-stu-id="e3dd9-210">When you account for the number of users for the Directors, include the users homed on Survivable Branch Appliances and Survivable Branch Servers at branch offices that are associated with a Front End pool at this site.</span></span>

</div>

<div>

## <a name="mediation-server"></a><span data-ttu-id="e3dd9-211">Mediation Server (Сервер-посредник);</span><span class="sxs-lookup"><span data-stu-id="e3dd9-211">Mediation Server</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e3dd9-212">Растянутые пулы не поддерживаются для этой роли сервера.</span><span class="sxs-lookup"><span data-stu-id="e3dd9-212">Stretched pools are not supported for this server role.</span></span>



</div>

<span data-ttu-id="e3dd9-213">При совместном размещении сервера-посредника с сервером переднего плана сервер-посредник работает на каждом сервере переднего плана в пуле и должен обеспечивать достаточную емкость для пользователей в пуле.</span><span class="sxs-lookup"><span data-stu-id="e3dd9-213">If you collocate Mediation Server with Front End Server, Mediation Server runs on every Front End Server in the pool, and should provide enough capacity for the users in the pool.</span></span>

<span data-ttu-id="e3dd9-214">Если развернуть автономный пул серверов-посредников, то сколько серверов-посредников необходимо развернуть, зависит от многих факторов, в том числе оборудования, используемого для сервера-посредника, количества пользователей VoIP, количества одноранговых шлюзов, которые каждый пул серверов-посредника элементы управления, объем занятого трафика через эти шлюзы, а также процент вызовов с носителями, которые обходят сервер-посредник.</span><span class="sxs-lookup"><span data-stu-id="e3dd9-214">If you deploy a stand-alone Mediation Server pool, then how many Mediation Servers to deploy depends on many factors, including the hardware used for Mediation Server, the number of VoIP users you have, the number of gateway peers that each Mediation Server pool controls, the busy hour traffic through those gateways, and the percentage of calls with media that bypasses the Mediation Server.</span></span>

<span data-ttu-id="e3dd9-215">В следующих таблицах приводятся рекомендации по количеству одновременных вызовов, которые может обрабатывать сервер-посредник, предполагая, что оборудование для серверов-посредников соответствует требованиям в [аппаратных платформах сервера для Lync server 2013](lync-server-2013-server-hardware-platforms.md) и что технология Hyper-Threading включена.</span><span class="sxs-lookup"><span data-stu-id="e3dd9-215">The following tables provide a guideline for how many concurrent calls a Mediation Server can handle, assuming that the hardware for the Mediation Servers meets the requirements in [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md) and that hyper-threading is enabled.</span></span> <span data-ttu-id="e3dd9-216">Подробные сведения о масштабируемости сервера-посредника приведены в статье [Оценка использования голосовой связи и трафика для Lync server 2013](lync-server-2013-estimating-voice-usage-and-traffic.md) и [рекомендации по развертыванию для сервера-посредника в Lync Server 2013](lync-server-2013-deployment-guidelines-for-mediation-server.md).</span><span class="sxs-lookup"><span data-stu-id="e3dd9-216">For details about Mediation Server scalability, see [Estimating voice usage and traffic for Lync Server 2013](lync-server-2013-estimating-voice-usage-and-traffic.md) and [Deployment guidelines for Mediation Server in Lync Server 2013](lync-server-2013-deployment-guidelines-for-mediation-server.md).</span></span>

<span data-ttu-id="e3dd9-217">Во всех приведенных ниже таблицах предполагается использование, как показано в разделе [User Models in Lync Server 2013](lync-server-2013-user-models.md).</span><span class="sxs-lookup"><span data-stu-id="e3dd9-217">All the following tables assume usage as summarized in [User models in Lync Server 2013](lync-server-2013-user-models.md).</span></span>

### <a name="stand-alone-mediation-server-capacity-70-internal-users-30-external-users-with-non-bypass-call-capacity-media-transcoding-performed-by-mediation-server"></a><span data-ttu-id="e3dd9-218">Объем автономного сервера-посредника: 70% внутренних пользователей, 30% внешних пользователей с необходным объемом вызовов (перекодировка мультимедиа, выполненная сервером-посредником)</span><span class="sxs-lookup"><span data-stu-id="e3dd9-218">Stand-alone Mediation Server Capacity: 70% Internal Users, 30% External users with non-bypass call capacity (media transcoding performed by Mediation Server)</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e3dd9-219">Серверное оборудование</span><span class="sxs-lookup"><span data-stu-id="e3dd9-219">Server hardware</span></span></th>
<th><span data-ttu-id="e3dd9-220">Максимальное количество звонков</span><span class="sxs-lookup"><span data-stu-id="e3dd9-220">Maximum number of calls</span></span></th>
<th><span data-ttu-id="e3dd9-221">Максимальное количество линий T1</span><span class="sxs-lookup"><span data-stu-id="e3dd9-221">Maximum number of T1 lines</span></span></th>
<th><span data-ttu-id="e3dd9-222">Максимальное количество линий E1</span><span class="sxs-lookup"><span data-stu-id="e3dd9-222">Maximum number of E1 lines</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e3dd9-223">Два шестиядерных процессора 2,26 ГГц с поддержкой технологии Hyper-Threading (<strong>технология Hyper-Threading отключена</strong>), память 32 ГБ и одна двухпортовая сетевая карта.</span><span class="sxs-lookup"><span data-stu-id="e3dd9-223">Dual processor, hex core, 2.26 GHz hyper-threaded CPU <strong>with hyper-threading disabled</strong>, with 32 GB memory and one dual-port network adapter card.</span></span></p></td>
<td><p><span data-ttu-id="e3dd9-224">1100</span><span class="sxs-lookup"><span data-stu-id="e3dd9-224">1100</span></span></p></td>
<td><p><span data-ttu-id="e3dd9-225">46</span><span class="sxs-lookup"><span data-stu-id="e3dd9-225">46</span></span></p></td>
<td><p><span data-ttu-id="e3dd9-226">35</span><span class="sxs-lookup"><span data-stu-id="e3dd9-226">35</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e3dd9-227">Два шестиядерных процессора 2,26 ГГц с поддержкой технологии Hyper-Threading, память 32 ГБ и одна двухпортовая сетевая карта.</span><span class="sxs-lookup"><span data-stu-id="e3dd9-227">Dual processor, hex core, 2.26 GHz hyper-threaded CPU, with 32 GB memory and one dual-port network adapter card.</span></span></p></td>
<td><p><span data-ttu-id="e3dd9-228">1500</span><span class="sxs-lookup"><span data-stu-id="e3dd9-228">1500</span></span></p></td>
<td><p><span data-ttu-id="e3dd9-229">63</span><span class="sxs-lookup"><span data-stu-id="e3dd9-229">63</span></span></p></td>
<td><p><span data-ttu-id="e3dd9-230">47</span><span class="sxs-lookup"><span data-stu-id="e3dd9-230">47</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="e3dd9-231">Несмотря на то, что для тестирования производительности использовались серверы с 32 ГБ памяти, серверы с 16 ГБ памяти поддерживаются для изолированного сервера-посредника и достаточно для обеспечения производительности, представленной в этой таблице.</span><span class="sxs-lookup"><span data-stu-id="e3dd9-231">Although servers with 32 GB of memory were used for performance testing, servers with 16 GB of memory are supported for stand-alone Mediation Server, and are sufficient to provide the performance shown in this table.</span></span>



</div>

### <a name="mediation-server-capacity-mediation-server-collocated-with-front-end-server-70-internal-users-30-external-users-non-bypass-call-capacity-media-processing-performed-by-mediation-server"></a><span data-ttu-id="e3dd9-232">Емкость сервера-посредника (сервер-посредник, совместно размещенный с сервером переднего плана) 70% внутренних пользователей, 30% внешних пользователей, без обхода емкости вызовов (обработка мультимедиа выполняется сервером-посредником)</span><span class="sxs-lookup"><span data-stu-id="e3dd9-232">Mediation Server Capacity (Mediation Server Collocated with Front End Server) 70% Internal Users, 30% External Users, Non-Bypass Call Capacity (Media Processing Performed by Mediation Server)</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e3dd9-233">Серверное оборудование</span><span class="sxs-lookup"><span data-stu-id="e3dd9-233">Server hardware</span></span></th>
<th><span data-ttu-id="e3dd9-234">Максимальное количество звонков</span><span class="sxs-lookup"><span data-stu-id="e3dd9-234">Maximum number of calls</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e3dd9-235">Два шестиядерных процессора 2,26 ГГц с поддержкой технологии Hyper-Threading, память 32 ГБ и две сетевых карты со скоростью 1 Гбит/с.</span><span class="sxs-lookup"><span data-stu-id="e3dd9-235">Dual processor, hex core, 2.26 GHz hyper-threaded CPU, with 32 GB memory and 2 1GB network adapter cards.</span></span></p></td>
<td><p><span data-ttu-id="e3dd9-236">150</span><span class="sxs-lookup"><span data-stu-id="e3dd9-236">150</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="e3dd9-237">Это число значительно меньше числа для изолированного сервера-посредника, так как сервер переднего плана должен обрабатывать другие функции и функции для 6600 пользователей, размещенных на нем, в дополнение к перекодировке, необходимой для голосовых вызовов.</span><span class="sxs-lookup"><span data-stu-id="e3dd9-237">This number is much smaller than the numbers for the stand-alone Mediation Server because the Front End Server has to handle other features and functions for the 6600 users homed on it, in addition to the transcoding needed for voice calls.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="e3dd9-238">Чтобы увеличить производительность сервера-посредника, следует включить масштабирование на стороне приема (RSS) в сетевых адаптерах серверов-посредников.</span><span class="sxs-lookup"><span data-stu-id="e3dd9-238">To improve the performance of the Mediation Server, you should enable receive-side scaling (RSS) on the network adapters on your Mediation Servers.</span></span> <span data-ttu-id="e3dd9-239">RSS позволяет обрабатывать входящие пакеты параллельно несколькими процессорами на сервере.</span><span class="sxs-lookup"><span data-stu-id="e3dd9-239">RSS enables incoming packets to be handled in parallel by multiple processors on the server.</span></span> <span data-ttu-id="e3dd9-240">Дополнительные сведения см. в <A href="http://go.microsoft.com/fwlink/p/?linkid=268731">http://go.microsoft.com/fwlink/p/?linkId=268731</A>разделе "усовершенствованные возможности масштабирования на стороне Windows Server 2008".</span><span class="sxs-lookup"><span data-stu-id="e3dd9-240">For details, see "Receive-Side Scaling Enhancements in Windows Server 2008" at <A href="http://go.microsoft.com/fwlink/p/?linkid=268731">http://go.microsoft.com/fwlink/p/?linkId=268731</A>.</span></span> <span data-ttu-id="e3dd9-241">Сведения о включении RSS см. в документации вашего сетевого адаптера.</span><span class="sxs-lookup"><span data-stu-id="e3dd9-241">For details about how to enable RSS, see your network adapter documentation.</span></span>



</div>

</div>

<div>

## <a name="back-end-server"></a><span data-ttu-id="e3dd9-242">Сервер переднего план</span><span class="sxs-lookup"><span data-stu-id="e3dd9-242">Back End Server</span></span>

<span data-ttu-id="e3dd9-243">В Lync Server 2013 базы данных присутствия размещаются на серверах переднего плана, а не на внутреннем сервере.</span><span class="sxs-lookup"><span data-stu-id="e3dd9-243">In Lync Server 2013, the presence databases are located on the Front End Servers instead of the Back End Server.</span></span> <span data-ttu-id="e3dd9-244">Это значительно упрощается для каждого внутреннего сервера в Lync Server 2013, что соответствует требованиям к оборудованию для сервера переднего плана.</span><span class="sxs-lookup"><span data-stu-id="e3dd9-244">This has resulted in a much simpler requirement for each Back End Server in Lync Server 2013, equivalent to the hardware requirement for the Front End Server.</span></span> <span data-ttu-id="e3dd9-245">Сравните это с Lync Server 2010, где фоновый сервер должен быть более мощным сервером с 25 дисками.</span><span class="sxs-lookup"><span data-stu-id="e3dd9-245">Contrast this to Lync Server 2010, where the Back End Server was required to be a much higher grade server with 25 disks.</span></span> <span data-ttu-id="e3dd9-246">Тем не менее, в этом разделе, а также в [серверных аппаратных платформах для Lync Server 2013](lync-server-2013-server-hardware-platforms.md)не следует выполнять загрузку внутренних серверов.</span><span class="sxs-lookup"><span data-stu-id="e3dd9-246">However, the workload of Back End Servers is still such that you should not fail to meet the hardware recommendations listed earlier in this section and in [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md).</span></span>

<span data-ttu-id="e3dd9-247">Для обеспечения высокой доступности внутреннего сервера рекомендуется развертывать зеркальное отображение сервера.</span><span class="sxs-lookup"><span data-stu-id="e3dd9-247">To provide high availability of your Back End Server, we recommend deploying server mirroring.</span></span> <span data-ttu-id="e3dd9-248">Более подробную информацию можно узнать [в статье высокая доступность внутреннего сервера в Lync server 2013](lync-server-2013-back-end-server-high-availability.md).</span><span class="sxs-lookup"><span data-stu-id="e3dd9-248">For more information, see [Back End Server high availability in Lync Server 2013](lync-server-2013-back-end-server-high-availability.md).</span></span>

</div>

<div>

## <a name="monitoring-and-archiving"></a><span data-ttu-id="e3dd9-249">Мониторинг и архивирование</span><span class="sxs-lookup"><span data-stu-id="e3dd9-249">Monitoring and Archiving</span></span>

<span data-ttu-id="e3dd9-250">В Lync Server 2013 при развертывании мониторинга или архивации функция переднего плана этих служб работает на серверах переднего плана, а не на отдельных ролях сервера.</span><span class="sxs-lookup"><span data-stu-id="e3dd9-250">In Lync Server 2013, if you deploy Monitoring or Archiving, the front end functionality of these services runs on the Front End Servers, instead of on separate server roles.</span></span> <span data-ttu-id="e3dd9-251">Службы мониторинга и архивации используют собственные хранилища баз данных, независимые от хранилища тылового сервера.</span><span class="sxs-lookup"><span data-stu-id="e3dd9-251">Monitoring and Archiving each still use their own database store, separate from the Back End store.</span></span> <span data-ttu-id="e3dd9-252">Кроме того, если вы развернули Exchange 2013, вы можете хранить данные для архивации мгновенных сообщений в Exchange, а не в специальном хранилище SQL.</span><span class="sxs-lookup"><span data-stu-id="e3dd9-252">Alternatively, if you have Exchange 2013 deployed, you can store instant message Archiving data in Exchange instead of in a dedicated SQL store.</span></span>

<span data-ttu-id="e3dd9-253">В следующей таблице показаны приблизительные значения размера хранилища базы данных на пользователя в день, необходимые для данных мониторинга и архивации.</span><span class="sxs-lookup"><span data-stu-id="e3dd9-253">The following table indicates approximately how much database storage is required per user per day for Monitoring and Archiving data.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<tbody>
<tr class="odd">
<td></td>
<td><p><span data-ttu-id="e3dd9-254"><strong>CDR (мониторинг)</strong></span><span class="sxs-lookup"><span data-stu-id="e3dd9-254"><strong>CDR (Monitoring)</strong></span></span></p></td>
<td><p><span data-ttu-id="e3dd9-255"><strong>QoE (мониторинг)</strong></span><span class="sxs-lookup"><span data-stu-id="e3dd9-255"><strong>QoE (Monitoring)</strong></span></span></p></td>
<td><p><span data-ttu-id="e3dd9-256"><strong>Архивация</strong></span><span class="sxs-lookup"><span data-stu-id="e3dd9-256"><strong>Archiving</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e3dd9-257">Дисковое пространство на пользователя в день</span><span class="sxs-lookup"><span data-stu-id="e3dd9-257">Disk space required per user per day</span></span></p></td>
<td><p><span data-ttu-id="e3dd9-258">49 кб</span><span class="sxs-lookup"><span data-stu-id="e3dd9-258">49 KB</span></span></p></td>
<td><p><span data-ttu-id="e3dd9-259">28 кб</span><span class="sxs-lookup"><span data-stu-id="e3dd9-259">28 KB</span></span></p></td>
<td><p><span data-ttu-id="e3dd9-260">57 кб</span><span class="sxs-lookup"><span data-stu-id="e3dd9-260">57 KB</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="e3dd9-261">В следующей таблице описано оборудование сервера базы данных мониторинга и архивации, которое использовалось в корпорации Майкрософт при тестировании производительности.</span><span class="sxs-lookup"><span data-stu-id="e3dd9-261">Microsoft used the hardware in the following table for the database server for Monitoring and Archiving during its performance testing.</span></span> <span data-ttu-id="e3dd9-262">Тестирование собрало данные двух интерфейсных пулов, каждый из которых содержал 80 000 пользователей.</span><span class="sxs-lookup"><span data-stu-id="e3dd9-262">The testing collected the data of two Front End pools, each of which contained 80,000 users.</span></span>

### <a name="hardware-used-in-monitoring-and-archiving-performance-testing"></a><span data-ttu-id="e3dd9-263">Оборудование, использованное при тестировании производительности мониторинга и архивации</span><span class="sxs-lookup"><span data-stu-id="e3dd9-263">Hardware Used in Monitoring and Archiving Performance Testing</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e3dd9-264">Компонент оборудования</span><span class="sxs-lookup"><span data-stu-id="e3dd9-264">Hardware component</span></span></th>
<th><span data-ttu-id="e3dd9-265">Рекомендовано</span><span class="sxs-lookup"><span data-stu-id="e3dd9-265">Recommended</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e3dd9-266">ЦП</span><span class="sxs-lookup"><span data-stu-id="e3dd9-266">CPU</span></span></p></td>
<td><p><span data-ttu-id="e3dd9-267">Два 64-разрядных шестиядерных процессора 2,26 ГГц или более мощных</span><span class="sxs-lookup"><span data-stu-id="e3dd9-267">64-bit dual processor, hex-core, 2.26 gigahertz (GHz) or higher</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e3dd9-268">Память</span><span class="sxs-lookup"><span data-stu-id="e3dd9-268">Memory</span></span></p></td>
<td><p><span data-ttu-id="e3dd9-269">48 ГБ</span><span class="sxs-lookup"><span data-stu-id="e3dd9-269">48 gigabytes (GB)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e3dd9-270">Диск</span><span class="sxs-lookup"><span data-stu-id="e3dd9-270">Disk</span></span></p></td>
<td><p><span data-ttu-id="e3dd9-271">25 дисков со скоростью вращения 10000 об/мин по 300 ГБ со следующей конфигурацией</span><span class="sxs-lookup"><span data-stu-id="e3dd9-271">25 10,000-RPM hard disk drives with 300 GB on each disk, with the following configuration</span></span></p>
<h3 id="section-3"> </h3>
<div>
<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e3dd9-272"><strong>Drive</strong></span><span class="sxs-lookup"><span data-stu-id="e3dd9-272"><strong>Drive</strong></span></span></p></td>
<td><p><span data-ttu-id="e3dd9-273"><strong>Конфигурация RAID</strong></span><span class="sxs-lookup"><span data-stu-id="e3dd9-273"><strong>RAID Configuration</strong></span></span></p></td>
<td><p><span data-ttu-id="e3dd9-274"><strong>Количество дисков</strong></span><span class="sxs-lookup"><span data-stu-id="e3dd9-274"><strong>Number of disks</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e3dd9-275">Файлы баз данных CDR, QoE и архивации, на одном диске</span><span class="sxs-lookup"><span data-stu-id="e3dd9-275">CDR, QoE, and Archiving database data files, on a single drive</span></span></p></td>
<td><p><span data-ttu-id="e3dd9-276">1 + 0</span><span class="sxs-lookup"><span data-stu-id="e3dd9-276">1+0</span></span></p></td>
<td><p><span data-ttu-id="e3dd9-277">16 </span><span class="sxs-lookup"><span data-stu-id="e3dd9-277">16</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e3dd9-278">Файл журнала базы данных CDR</span><span class="sxs-lookup"><span data-stu-id="e3dd9-278">CDR database log file</span></span></p></td>
<td><p><span data-ttu-id="e3dd9-279">1 </span><span class="sxs-lookup"><span data-stu-id="e3dd9-279">1</span></span></p></td>
<td><p><span data-ttu-id="e3dd9-280">2 </span><span class="sxs-lookup"><span data-stu-id="e3dd9-280">2</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e3dd9-281">Файл журнала базы данных QoE</span><span class="sxs-lookup"><span data-stu-id="e3dd9-281">QoE database log file</span></span></p></td>
<td><p><span data-ttu-id="e3dd9-282">1 </span><span class="sxs-lookup"><span data-stu-id="e3dd9-282">1</span></span></p></td>
<td><p><span data-ttu-id="e3dd9-283">2 </span><span class="sxs-lookup"><span data-stu-id="e3dd9-283">2</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e3dd9-284">Файл журнала базы данных архивации</span><span class="sxs-lookup"><span data-stu-id="e3dd9-284">Archiving database log file</span></span></p></td>
<td><p><span data-ttu-id="e3dd9-285">1 </span><span class="sxs-lookup"><span data-stu-id="e3dd9-285">1</span></span></p></td>
<td><p><span data-ttu-id="e3dd9-286">2 </span><span class="sxs-lookup"><span data-stu-id="e3dd9-286">2</span></span></p></td>
</tr>
</tbody>
</table>

</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e3dd9-287">Сеть</span><span class="sxs-lookup"><span data-stu-id="e3dd9-287">Network</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="e3dd9-288">1 двухпортовый сетевой адаптер, 1 Гбит/с или выше (рекомендуется 2, что требует объединения с одним MAC-адресом и одним IP-адресом)</span><span class="sxs-lookup"><span data-stu-id="e3dd9-288">1 dual-port network adapter, 1 Gbps or higher (2 recommended, which requires teaming with a single MAC address and single IP address)</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="e3dd9-289">Содержание</span><span class="sxs-lookup"><span data-stu-id="e3dd9-289">In This Section</span></span>

  - [<span data-ttu-id="e3dd9-290">Оценка использования голосовой связи и трафика для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e3dd9-290">Estimating voice usage and traffic for Lync Server 2013</span></span>](lync-server-2013-estimating-voice-usage-and-traffic.md)

  - [<span data-ttu-id="e3dd9-291">Рекомендации по развертыванию сервера-посредника в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e3dd9-291">Deployment guidelines for Mediation Server in Lync Server 2013</span></span>](lync-server-2013-deployment-guidelines-for-mediation-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

