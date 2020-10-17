---
title: Планирование мощности Lync Server 2013 с использованием пользовательских моделей
description: Lync Server 2013 планирование мощности с помощью пользовательских моделей.
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
ms.openlocfilehash: 6b710f7ec88dd75c872d704f2169fa2f161fc186
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48544415"
---
# <a name="capacity-planning-for-lync-server-2013-using-the-user-models"></a><span data-ttu-id="a532e-103">Планирование емкости для Lync Server 2013 с использованием пользовательских моделей</span><span class="sxs-lookup"><span data-stu-id="a532e-103">Capacity planning for Lync Server 2013 using the user models</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a532e-104">_**Последнее изменение темы:** 2014-01-14_</span><span class="sxs-lookup"><span data-stu-id="a532e-104">_**Topic Last Modified:** 2014-01-14_</span></span>

<span data-ttu-id="a532e-105">В этом разделе приводятся рекомендации по количеству серверов, необходимых на сайте, для количества пользователей на этом сайте в соответствии с описанием использования, описанными в статье [User Models in Lync Server 2013](lync-server-2013-user-models.md).</span><span class="sxs-lookup"><span data-stu-id="a532e-105">This section provides guidance on how many servers you need at a site for the number of users at that site, according to the usage described in [User models in Lync Server 2013](lync-server-2013-user-models.md).</span></span>

<div>

## <a name="tested-hardware-platform"></a><span data-ttu-id="a532e-106">Аппаратная платформа для тестирования</span><span class="sxs-lookup"><span data-stu-id="a532e-106">Tested Hardware Platform</span></span>

<span data-ttu-id="a532e-107">Все результаты тестирования и рекомендации по развертыванию, приведенные в этом разделе, основаны на тестировании производительности на серверах, конфигурация которых описана в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="a532e-107">All the performance results and deployment recommendations in this section are based on performance testing on servers running the hardware described in the following table.</span></span> <span data-ttu-id="a532e-108">Рекомендуется использовать аналогичное оборудование.</span><span class="sxs-lookup"><span data-stu-id="a532e-108">We recommend that you use similar hardware.</span></span> <span data-ttu-id="a532e-109">Использование менее мощного оборудования может привести к проблемам функциональности или низкой производительности.</span><span class="sxs-lookup"><span data-stu-id="a532e-109">If you use less powerful hardware, you may experience functionality problems or poor performance.</span></span> <span data-ttu-id="a532e-110">Обратите внимание на то, что эти рекомендации по оборудованию выше, чем в предыдущих версиях Lync Server.</span><span class="sxs-lookup"><span data-stu-id="a532e-110">Note that these hardware recommendations are higher than those of previous versions of Lync Server.</span></span>

### <a name="hardware-used-in-performance-testing"></a><span data-ttu-id="a532e-111">Оборудование, использованное при проведении тестирования</span><span class="sxs-lookup"><span data-stu-id="a532e-111">Hardware Used in Performance Testing</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a532e-112">Компонент оборудования</span><span class="sxs-lookup"><span data-stu-id="a532e-112">Hardware component</span></span></th>
<th><span data-ttu-id="a532e-113">Рекомендуемый</span><span class="sxs-lookup"><span data-stu-id="a532e-113">Recommended</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a532e-114">ЦП</span><span class="sxs-lookup"><span data-stu-id="a532e-114">CPU</span></span></p></td>
<td><p><span data-ttu-id="a532e-115">Два 64-разрядных шестиядерных процессора 2,26 ГГц или более мощных</span><span class="sxs-lookup"><span data-stu-id="a532e-115">64-bit dual processor, hex-core, 2.26 gigahertz (GHz) or higher</span></span></p>
<p><span data-ttu-id="a532e-116">Процессоры Intel Itanium не поддерживаются для ролей сервера Lync Server.</span><span class="sxs-lookup"><span data-stu-id="a532e-116">Intel Itanium processors are not supported for Lync Server server roles.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a532e-117">Память</span><span class="sxs-lookup"><span data-stu-id="a532e-117">Memory</span></span></p></td>
<td><p><span data-ttu-id="a532e-118">32 ГБ</span><span class="sxs-lookup"><span data-stu-id="a532e-118">32 gigabytes (GB)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a532e-119">Диск</span><span class="sxs-lookup"><span data-stu-id="a532e-119">Disk</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="a532e-120">8 или больше дисков со скоростью вращения 10000 об/мин и как минимум 72 ГБ свободного места.</span><span class="sxs-lookup"><span data-stu-id="a532e-120">8 or more 10,000-RPM hard disk drives with at least 72 GB free disk space.</span></span></p>
<p><span data-ttu-id="a532e-121">Два диска должны использовать RAID 1, а шесть остальных — RAID 10.</span><span class="sxs-lookup"><span data-stu-id="a532e-121">Two of the disks should use RAID 1, and six should use RAID 10.</span></span></p>
<p><span data-ttu-id="a532e-122">- Также</span><span class="sxs-lookup"><span data-stu-id="a532e-122">- OR -</span></span></p></li>
<li><p><span data-ttu-id="a532e-123">Твердотельные накопители (SSD), производительность которых аналогична 8 механическим дискам со скоростью вращения 10000 об/мин.</span><span class="sxs-lookup"><span data-stu-id="a532e-123">Solid state drives (SSDs) which provide performance similar to 8 10,000-RPM mechanical disk drives.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a532e-124">Сеть</span><span class="sxs-lookup"><span data-stu-id="a532e-124">Network</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="a532e-125">1 двухпортовый сетевой адаптер, 1 Гбит/с или выше (рекомендуется 2, что требует объединения с одним MAC-адресом и одним IP-адресом)</span><span class="sxs-lookup"><span data-stu-id="a532e-125">1 dual-port network adapter, 1 Gbps or higher (2 recommended, which requires teaming with a single MAC address and single IP address)</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="summary-of-results"></a><span data-ttu-id="a532e-126">Сводка результатов</span><span class="sxs-lookup"><span data-stu-id="a532e-126">Summary of Results</span></span>

<span data-ttu-id="a532e-127">В следующей таблице приведена сводка по рекомендациям.</span><span class="sxs-lookup"><span data-stu-id="a532e-127">The following table summarizes these recommendations.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a532e-128">Роль сервера</span><span class="sxs-lookup"><span data-stu-id="a532e-128">Server role</span></span></th>
<th><span data-ttu-id="a532e-129">Максимальное число поддерживаемых пользователей</span><span class="sxs-lookup"><span data-stu-id="a532e-129">Maximum number of users supported</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a532e-130">Интерфейсный пул с двенадцать серверами переднего плана и одним внутренним сервером или зеркальным набором зеркальных серверов.</span><span class="sxs-lookup"><span data-stu-id="a532e-130">Front End pool with twelve Front End Servers and one Back End Server or a mirrored pair of Back End Servers.</span></span></p></td>
<td><p><span data-ttu-id="a532e-131">80000 одновременно зарегистрированных уникальных пользователей, плюс 50% пользователей с несколькими точками присутствия, представляющими немобильные экземпляры, плюс 40% пользователей Mobility; итого 152000 конечных точек.</span><span class="sxs-lookup"><span data-stu-id="a532e-131">80,000 unique users simultaneously logged in, plus 50% multiple points of presence (MPOP) representing non-mobile instances, plus 40% of users enabled for Mobility for a total of 152,000 endpoints.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a532e-132">Аудио- и видеоконференции</span><span class="sxs-lookup"><span data-stu-id="a532e-132">A/V Conferencing</span></span></p></td>
<td><p><span data-ttu-id="a532e-133">Служба аудио-и видеоконференций, предоставляемая интерфейсным пулом, поддерживает конференц-связи пула с максимальным размером конференции 250 пользователей и только одной такой большой конференц-связью, запущенной за раз.</span><span class="sxs-lookup"><span data-stu-id="a532e-133">The A/V Conferencing service provided by a Front End pool supports the pool’s conferences assuming a maximum conference size of 250 users, and only one such large conference running at a time.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="a532e-134">Кроме того, вы можете поддерживать большие конференции между пользователями 250 и 1000, развертывая отдельный пул переднего плана с двумя серверами переднего плана для размещения больших конференций.</span><span class="sxs-lookup"><span data-stu-id="a532e-134">Additionally, you can support large conferences of between 250 and 1000 users by deploying a separate Front End pool with two Front End Servers to host the large conferences.</span></span> <span data-ttu-id="a532e-135">Дополнительные сведения см. <A href="lync-server-2013-supporting-large-meetings.md">в статье поддержка больших собраний с помощью Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="a532e-135">For details, see <A href="lync-server-2013-supporting-large-meetings.md">Supporting large meetings using Lync Server 2013</A>.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a532e-136">Один пограничный сервер</span><span class="sxs-lookup"><span data-stu-id="a532e-136">One Edge Server</span></span></p></td>
<td><p><span data-ttu-id="a532e-137">12 000 одновременно работающих удаленных пользователей</span><span class="sxs-lookup"><span data-stu-id="a532e-137">12,000 concurrent remote users</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a532e-138">Один директор</span><span class="sxs-lookup"><span data-stu-id="a532e-138">One Director</span></span></p></td>
<td><p><span data-ttu-id="a532e-139">12 000 одновременно работающих удаленных пользователей</span><span class="sxs-lookup"><span data-stu-id="a532e-139">12,000 concurrent remote users</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a532e-140">Мониторинг и архивация</span><span class="sxs-lookup"><span data-stu-id="a532e-140">Monitoring and Archiving</span></span></p></td>
<td><p><span data-ttu-id="a532e-141">В Lync Server 2013 серверные службы мониторинга и архивации теперь выполняются на каждом сервере переднего плана, а не в отдельных ролях сервера.</span><span class="sxs-lookup"><span data-stu-id="a532e-141">In Lync Server 2013, the Monitoring and Archiving front end services now run on each Front End Server, instead of on separate server roles.</span></span></p>
<p><span data-ttu-id="a532e-142">Для мониторинга и архивации требуются собственные хранилища баз данных.</span><span class="sxs-lookup"><span data-stu-id="a532e-142">Monitoring and Archiving each still require their own database stores.</span></span> <span data-ttu-id="a532e-143">Если вы также запускаете Exchange 2013, вы можете хранить данные архивации в Exchange, а не в выделенной базе данных SQL.</span><span class="sxs-lookup"><span data-stu-id="a532e-143">If you also run Exchange 2013, you can keep your Archiving data in Exchange, rather than in a dedicated SQL database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a532e-144">Один сервер-посредник</span><span class="sxs-lookup"><span data-stu-id="a532e-144">One Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="a532e-145">Сервер-посредник, размещенный на сервере переднего плана, работает на каждом сервере переднего плана в пуле и должен обеспечивать достаточную емкость для пользователей в пуле.</span><span class="sxs-lookup"><span data-stu-id="a532e-145">Mediation Server collocated with Front End Server runs on every Front End Server in a pool, and should provide enough capacity for the users in the pool.</span></span> <span data-ttu-id="a532e-146">Для автономного сервера-посредника ознакомьтесь с разделом "сервер-посредник" Далее в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="a532e-146">For stand-alone Mediation Server, see the “Mediation Server” section later in this topic.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a532e-147">Один сервер Standard Edition</span><span class="sxs-lookup"><span data-stu-id="a532e-147">One Standard Edition server</span></span></p></td>
<td><p><span data-ttu-id="a532e-148">Мы настоятельно рекомендуем использовать для размещения пользователей серверы Standard Edition, которые применяют два сервера, в сочетании с рекомендациями по <a href="lync-server-2013-planning-for-high-availability-and-disaster-recovery.md">планированию обеспечения высокой доступности и аварийного восстановления в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="a532e-148">We strongly recommend that if you use Standard Edition servers to host users, you always use two servers, paired using the recommendations in <a href="lync-server-2013-planning-for-high-availability-and-disaster-recovery.md">Planning for high availability and disaster recovery in Lync Server 2013</a>.</span></span> <span data-ttu-id="a532e-149">Каждый сервер в каждой из них может размещаться до 2 500 пользователей, и если один из серверов не проходит, то в сценарии отработки отказа может 5 000 поддерживаться оставшийся сервер.</span><span class="sxs-lookup"><span data-stu-id="a532e-149">Each server in the pair can host up to 2,500 users, and if one server fails the remaining server can support 5,000 users in a failover scenario.</span></span></p>
<p><span data-ttu-id="a532e-150">Если развертывание включает в себя значительный объем аудио и видеоданных, производительность сервера может снизиться более 2 500 пользователей на сервер.</span><span class="sxs-lookup"><span data-stu-id="a532e-150">If your deployment includes a significant amount of audio or video traffic, server performance may suffer with more than 2,500 users per server.</span></span> <span data-ttu-id="a532e-151">В этом случае следует рассмотреть добавление дополнительных серверов Standard Edition или переход на Lync Server Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="a532e-151">In this case, you should consider adding more Standard Edition servers or moving to Lync Server Enterprise Edition.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="front-end-server"></a><span data-ttu-id="a532e-152">Сервер переднего плана</span><span class="sxs-lookup"><span data-stu-id="a532e-152">Front End Server</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a532e-153">Растянутые пулы не поддерживаются для этой роли сервера.</span><span class="sxs-lookup"><span data-stu-id="a532e-153">Stretched pools are not supported for this server role.</span></span>



</div>

<span data-ttu-id="a532e-154">В пуле переднего плана должен быть один сервер переднего плана для каждых 6 660 пользователей, размещенных в пуле, предполагая, что технология Hyper-Threading включена на всех серверах в пуле, а оборудование сервера соответствует рекомендациям [серверных аппаратных платформ для Lync Server 2013](lync-server-2013-server-hardware-platforms.md).</span><span class="sxs-lookup"><span data-stu-id="a532e-154">In a Front End pool, you should have one Front End Server for every 6,660 users homed in the pool, assuming that hyper-threading is enabled on all servers in the pool, and that the server hardware meets the recommendations in [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md).</span></span> <span data-ttu-id="a532e-155">Максимальное число пользователей в одном интерфейсном пуле — 80 000, предполагая, что технология Hyper-Threading включена на всех серверах в пуле.</span><span class="sxs-lookup"><span data-stu-id="a532e-155">The maximum number of users in one Front End pool is 80,000, assuming that hyper-threading is enabled on all the servers in the pool.</span></span> <span data-ttu-id="a532e-156">Если на сайте больше 80 000 пользователей, можно развернуть несколько интерфейсных пулов.</span><span class="sxs-lookup"><span data-stu-id="a532e-156">If you have more than 80,000 users at a site, you can deploy more than one Front End pool.</span></span>

<span data-ttu-id="a532e-157">При учете количества пользователей в пуле переднего плана Включите пользователей, размещенных на устройствах для обеспечения связи в филиалах и серверах для обеспечения связи в филиалах, связанных с этим интерфейсным пулом.</span><span class="sxs-lookup"><span data-stu-id="a532e-157">When you account for the number of users in a Front End pool, include the users homed on Survivable Branch Appliances and Survivable Branch Servers at branch offices that are associated with this Front End pool.</span></span>

<span data-ttu-id="a532e-158">Если активный сервер недоступен, его подключения автоматически перенаправляются на другие серверы в пуле.</span><span class="sxs-lookup"><span data-stu-id="a532e-158">When an active server is unavailable, its connections are transferred automatically to the other servers in the pool.</span></span> <span data-ttu-id="a532e-159">Например, если у вас 30 000 пользователей и пять серверов переднего плана, то если один сервер недоступен, то при подключении пользователей 6000 необходимо перенести их на остальные четыре сервера.</span><span class="sxs-lookup"><span data-stu-id="a532e-159">For example, if you have 30,000 users and five Front End Servers, then if one server is unavailable, the connections of 6000 users need to be transferred to the other four servers.</span></span> <span data-ttu-id="a532e-160">На каждом из оставшихся серверов будет по 7500 пользователей, а это число больше рекомендованного.</span><span class="sxs-lookup"><span data-stu-id="a532e-160">The remaining four servers will each have 7500 users, which is a larger number than recommended.</span></span>

<span data-ttu-id="a532e-161">Если вместо этого были запущены шесть серверов переднего плана для пользователей 30 000, а затем они становятся недоступными, общее количество пользователей 5000 перемещается на оставшиеся пять серверов.</span><span class="sxs-lookup"><span data-stu-id="a532e-161">If instead you had started with six Front End Servers for your 30,000 users and subsequently one became unavailable, a total of 5000 users will be moved to the remaining five servers.</span></span> <span data-ttu-id="a532e-162">На каждом из этих пяти серверов будет размещаться по 6000 пользователей, и это число не превышает рекомендованное значение.</span><span class="sxs-lookup"><span data-stu-id="a532e-162">These five servers will each host 6000 users, which is in the recommended range.</span></span>

<span data-ttu-id="a532e-163">Максимальное число пользователей в пуле переднего плана составляет 80 000.</span><span class="sxs-lookup"><span data-stu-id="a532e-163">The maximum number of users in a Front End pool is 80,000.</span></span> <span data-ttu-id="a532e-164">Максимальное число серверов переднего плана в пуле составляет 12.</span><span class="sxs-lookup"><span data-stu-id="a532e-164">The maximum number of Front End Servers in a pool is 12.</span></span>

<span data-ttu-id="a532e-165">Для пула переднего плана с 80 000 пользователями для повышения производительности достаточно двенадцати серверов переднего плана в типичных развертываниях, которые следуют [пользовательским моделям в Lync Server 2013](lync-server-2013-user-models.md).</span><span class="sxs-lookup"><span data-stu-id="a532e-165">For a Front End pool with 80,000 users, twelve Front End Servers is sufficient for performance, in typical deployments that follow the [User models in Lync Server 2013](lync-server-2013-user-models.md).</span></span> <span data-ttu-id="a532e-166">Развертывания, предназначенные для поддержки отказоустойчивости аварийного восстановления предполагают, что максимальное число пользователей 40 000 в каждом из двух связанных пулов переднего плана, в котором каждый пул имеет достаточно серверов переднего плана для размещения пользователей в обоих пулах, должен ли один пул относиться к другому.</span><span class="sxs-lookup"><span data-stu-id="a532e-166">Deployments designed to support disaster recovery failover assume that a maximum of 40,000 users can be hosted in each of two paired Front End pools, in which each pool has enough Front End Servers to accommodate the users in both pools should one pool need to be failed over to the other.</span></span>

<span data-ttu-id="a532e-167">Количество пользователей, поддерживаемых с высокой производительностью для определенного пула переднего плана, может отличаться от этих номеров по следующим причинам:</span><span class="sxs-lookup"><span data-stu-id="a532e-167">The number of users supported with good performance by a particular Front End pool may differ from these numbers for the following reasons:</span></span>

  - <span data-ttu-id="a532e-168">Оборудование для серверов переднего плана не соответствует рекомендациям [серверных аппаратных платформ для Lync server 2013](lync-server-2013-server-hardware-platforms.md).</span><span class="sxs-lookup"><span data-stu-id="a532e-168">The hardware for your Front End Servers does not meet the recommendations in [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md).</span></span>

  - <span data-ttu-id="a532e-169">Сценарий использования в организации существенно отличается от пользовательских моделей, например, трафик конференций значительно больше.</span><span class="sxs-lookup"><span data-stu-id="a532e-169">Your organization’s usage differs significantly from the user models, such as significantly more conferencing traffic.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="a532e-170">В Lync Server 2013 базы данных присутствия теперь размещаются на серверах переднего плана, в отличие от Lync Server 2010, где они были размещены на внутреннем сервере.</span><span class="sxs-lookup"><span data-stu-id="a532e-170">In Lync Server 2013, the presence databases are now hosted on Front End Servers, unlike in Lync Server 2010 where they were hosted on the Back End Server.</span></span> <span data-ttu-id="a532e-171">Это означает, что производительность и емкость диска серверов переднего плана не должны быть раскрыты в соответствии с рекомендациями, приведенными выше в этом разделе, и в <A href="lync-server-2013-server-hardware-platforms.md">серверных аппаратных платформах для Lync Server 2013</A>, независимо от количества пользователей, размещенных на серверах переднего плана.</span><span class="sxs-lookup"><span data-stu-id="a532e-171">This means that the disk performance and capacity of your Front End Servers should not be compromised from the recommendations listed earlier in this section and in <A href="lync-server-2013-server-hardware-platforms.md">Server hardware platforms for Lync Server 2013</A>, regardless of the number of users hosted by your Front End Servers.</span></span>



</div>

<span data-ttu-id="a532e-172">В следующей таблице показана средняя пропускная способность для обмена мгновенными сообщениями и присутствия при наличии пользовательской модели, как определено в [пользовательских моделях в Lync Server 2013](lync-server-2013-user-models.md).</span><span class="sxs-lookup"><span data-stu-id="a532e-172">The following table shows the average bandwidth for IM and presence, given the user model, as defined in [User models in Lync Server 2013](lync-server-2013-user-models.md).</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a532e-173">Средняя пропускная способность на пользователя</span><span class="sxs-lookup"><span data-stu-id="a532e-173">Average bandwidth per user</span></span></th>
<th><span data-ttu-id="a532e-174">Требования к пропускной способности для сервера переднего плана с 6 660 пользователей</span><span class="sxs-lookup"><span data-stu-id="a532e-174">Bandwidth requirements per Front End Server with 6,660 users</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a532e-175">1,3 кбит/с</span><span class="sxs-lookup"><span data-stu-id="a532e-175">1.3 Kpbs</span></span></p></td>
<td><p><span data-ttu-id="a532e-176">13 Мбит/с</span><span class="sxs-lookup"><span data-stu-id="a532e-176">13 Mbps</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="a532e-177">Чтобы увеличить производительность мультимедийных функций совместной конференции и сервера-посредника на серверах переднего плана, следует включить масштабирование на стороне приема (RSS) в сетевых адаптерах на серверах переднего плана.</span><span class="sxs-lookup"><span data-stu-id="a532e-177">To improve the media performance of the co-located A/V Conferencing and Mediation Server functionality on your Front End Servers, you should enable receive-side scaling (RSS) on the network adapters on your Front End Servers.</span></span> <span data-ttu-id="a532e-178">RSS позволяет обрабатывать входящие пакеты параллельно несколькими процессорами на сервере.</span><span class="sxs-lookup"><span data-stu-id="a532e-178">RSS enables incoming packets to be handled in parallel by multiple processors on the server.</span></span> <span data-ttu-id="a532e-179">Дополнительные сведения см. в разделе "усовершенствованные возможности масштабирования на стороне Windows Server 2008" <A href="https://go.microsoft.com/fwlink/p/?linkid=268731">https://go.microsoft.com/fwlink/p/?linkId=268731</A> .</span><span class="sxs-lookup"><span data-stu-id="a532e-179">For details, see "Receive-Side Scaling Enhancements in Windows Server 2008" at <A href="https://go.microsoft.com/fwlink/p/?linkid=268731">https://go.microsoft.com/fwlink/p/?linkId=268731</A>.</span></span> <span data-ttu-id="a532e-180">Сведения о том, как включить RSS, см. в документации сетевого адаптера.</span><span class="sxs-lookup"><span data-stu-id="a532e-180">For details about how to enable RSS, see your network adapter documentation.</span></span>



</div>

</div>

<div>

## <a name="conferencing-maximums"></a><span data-ttu-id="a532e-181">Максимумы конференц-связи</span><span class="sxs-lookup"><span data-stu-id="a532e-181">Conferencing Maximums</span></span>

<span data-ttu-id="a532e-182">Если пользовательская модель допускает, что 5% пользователей пула могут участвовать в конференциях в любой фиксированный момент времени, для пула из 80000 пользователей количество одновременно участвующих в конференциях пользователей составит около 4000.</span><span class="sxs-lookup"><span data-stu-id="a532e-182">Given the user model that 5% of users in a pool may be in a conference at any one time, a pool of 80,000 users could have about 4,000 users in conferences at one time.</span></span> <span data-ttu-id="a532e-183">Эти конференции могут использовать разные типы мультимедиа (например, некоторые могут использовать только обмен сообщениями, а другие — обмен сообщениями и аудио или аудио и видео) и охватывать разное количество участников.</span><span class="sxs-lookup"><span data-stu-id="a532e-183">These conferences are expected to be a mix of media (some IM-only, some IM with audio, some audio/video, for example) and number of participants.</span></span> <span data-ttu-id="a532e-184">Не существует жестких ограничений на количество конференций; реальную производительность определяет фактический сценарий использования.</span><span class="sxs-lookup"><span data-stu-id="a532e-184">There is no hard limit for the actual number of conferences allowed, and actual usage determines the actual performance.</span></span> <span data-ttu-id="a532e-185">Например, если в организации используется гораздо больше конференций в смешанном режиме, чем предполагается в пользовательской модели, может потребоваться развернуть дополнительные серверы переднего плана или серверы конференций аудио-и видеоконференций, чем рекомендации, приведенные в этом документе.</span><span class="sxs-lookup"><span data-stu-id="a532e-185">For example, if your organization has many more mixed-mode conferences than are assumed in the user model, you might need to deploy more Front End Servers or A/V Conferencing Servers than the recommendations in this document.</span></span> <span data-ttu-id="a532e-186">Сведения о допущениях в пользовательской модели можно найти в статье [User Models in Lync Server 2013](lync-server-2013-user-models.md).</span><span class="sxs-lookup"><span data-stu-id="a532e-186">For details about the assumptions in the user model, see [User models in Lync Server 2013](lync-server-2013-user-models.md).</span></span>

<span data-ttu-id="a532e-187">Максимальный поддерживаемый размер Конференции, размещенный в обычном интерфейсном пуле Lync Server 2013, в котором также размещаются пользователи, — 250 участников.</span><span class="sxs-lookup"><span data-stu-id="a532e-187">The maximum supported conference size hosted by a regular Lync Server 2013 Front End pool which also hosts users is 250 participants.</span></span> <span data-ttu-id="a532e-188">Во время проведения конференции с 250 пользователями пул также поддерживает другие конференции, но количество пользователей, одновременно участвующих в конференциях, не должно превышать 5% от общего числа пользователей пула.</span><span class="sxs-lookup"><span data-stu-id="a532e-188">While a 250-user conference is happening, the pool still supports other conferences as well, such that a total of 5% of pool users are in concurrent conferences.</span></span> <span data-ttu-id="a532e-189">Например, в пуле двенадцати серверов переднего плана и 80 000 пользователей, в то время как происходит конференция 250-User, Lync Server поддерживает 3 750 других пользователей, участвующих в небольших конференциях.</span><span class="sxs-lookup"><span data-stu-id="a532e-189">For example, in a pool of twelve Front End Servers and 80,000 users, while the 250-user conference is happening, Lync Server supports 3,750 other users participating in smaller conferences.</span></span>

<span data-ttu-id="a532e-190">Независимо от количества пользователей, размещенных в пуле переднего плана или сервера Standard Edition, Lync Server поддерживает минимум 125 других пользователей, участвующих в небольших конференциях в том же пуле или на сервере, где размещается конференция 250-User.</span><span class="sxs-lookup"><span data-stu-id="a532e-190">Regardless of the number of users homed on the Front End pool or Standard Edition server, Lync Server supports a minimum of 125 other users participating in smaller conferences on the same pool or server which is hosting a 250-user conference.</span></span>

<span data-ttu-id="a532e-191">Чтобы разрешить конференции между пользователями 250 и 1000, можно настроить отдельный пул переднего плана только для размещения этих конференций.</span><span class="sxs-lookup"><span data-stu-id="a532e-191">To enable conferences with between 250 and 1000 users, you can set up a separate Front End pool just to host those conferences.</span></span> <span data-ttu-id="a532e-192">В этом интерфейсном пуле не будут размещаться никакие пользователи.</span><span class="sxs-lookup"><span data-stu-id="a532e-192">This Front End pool will not host any users.</span></span> <span data-ttu-id="a532e-193">Дополнительные сведения см. [в статье поддержка больших собраний с помощью Lync Server 2013](lync-server-2013-supporting-large-meetings.md).</span><span class="sxs-lookup"><span data-stu-id="a532e-193">For details, see [Supporting large meetings using Lync Server 2013](lync-server-2013-supporting-large-meetings.md).</span></span>

<span data-ttu-id="a532e-194">Если в организации используется гораздо больше конференций в смешанном режиме, чем предполагается в пользовательской модели, может потребоваться развернуть больше серверов переднего плана, чем рекомендованных в этом документе (до 12 Фес).</span><span class="sxs-lookup"><span data-stu-id="a532e-194">If your organization has many more mixed-mode conferences than are assumed in the user model, you might need to deploy more Front End Servers than the recommendations in this document (up to a limit of 12 FEs).</span></span> <span data-ttu-id="a532e-195">Сведения о допущениях в пользовательской модели можно найти в статье [User Models in Lync Server 2013](lync-server-2013-user-models.md).</span><span class="sxs-lookup"><span data-stu-id="a532e-195">For details about the assumptions in the user model, see [User models in Lync Server 2013](lync-server-2013-user-models.md).</span></span>

</div>

<div>

## <a name="edge-server"></a><span data-ttu-id="a532e-196">Пограничный сервер</span><span class="sxs-lookup"><span data-stu-id="a532e-196">Edge Server</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a532e-197">Растянутые пулы не поддерживаются для этой роли сервера.</span><span class="sxs-lookup"><span data-stu-id="a532e-197">Stretched pools are not supported for this server role.</span></span>



</div>

<span data-ttu-id="a532e-198">Необходимо развернуть один пограничный сервер для каждых удаленных пользователей 12 000, которые будут обращаться к сайту параллельно.</span><span class="sxs-lookup"><span data-stu-id="a532e-198">You should deploy one Edge Server for every 12,000 remote users who will access a site concurrently.</span></span> <span data-ttu-id="a532e-199">Как минимум мы рекомендуем использовать два пограничных сервера для обеспечения высокой доступности.</span><span class="sxs-lookup"><span data-stu-id="a532e-199">At a minimum we recommend two Edge Servers for high availability.</span></span> <span data-ttu-id="a532e-200">В этих рекомендациях предполагается, что оборудование пограничных серверов соответствует рекомендациям [серверных аппаратных платформ для Lync server 2013](lync-server-2013-server-hardware-platforms.md).</span><span class="sxs-lookup"><span data-stu-id="a532e-200">These recommendations assume that the hardware for your Edge Servers meets the recommendations in [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md).</span></span>

<span data-ttu-id="a532e-201">При учете количества пользователей для пограничных серверов включите пользователей, размещенных на устройствах для обеспечения связи в филиалах и серверах для обеспечения связи в филиалах, которые связаны с пулом переднего плана на этом сайте.</span><span class="sxs-lookup"><span data-stu-id="a532e-201">When you account for the number of users for the Edge Servers, include the users homed on Survivable Branch Appliances and Survivable Branch Servers at branch offices that are associated with a Front End pool at this site.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a532e-202">Чтобы увеличить производительность пограничной службы аудио-и видеоконференций на пограничных серверах, следует включить масштабирование на стороне приема (RSS) на сетевых адаптерах на пограничных серверах.</span><span class="sxs-lookup"><span data-stu-id="a532e-202">To improve the performance of the A/V Conferencing Edge service on your Edge Servers, you should enable receive-side scaling (RSS) on the network adapters on your Edge Servers.</span></span> <span data-ttu-id="a532e-203">RSS позволяет обрабатывать входящие пакеты параллельно несколькими процессорами на сервере.</span><span class="sxs-lookup"><span data-stu-id="a532e-203">RSS enables incoming packets to be handled in parallel by multiple processors on the server.</span></span> <span data-ttu-id="a532e-204">Дополнительные сведения см. в разделе "усовершенствованные возможности масштабирования на стороне Windows Server 2008" <A href="https://go.microsoft.com/fwlink/p/?linkid=268731">https://go.microsoft.com/fwlink/p/?linkId=268731</A> .</span><span class="sxs-lookup"><span data-stu-id="a532e-204">For details, see "Receive-Side Scaling Enhancements in Windows Server 2008" at <A href="https://go.microsoft.com/fwlink/p/?linkid=268731">https://go.microsoft.com/fwlink/p/?linkId=268731</A>.</span></span> <span data-ttu-id="a532e-205">Сведения о включении RSS см. в документации вашего сетевого адаптера.</span><span class="sxs-lookup"><span data-stu-id="a532e-205">For details about how to enable RSS, see your network adapter documentation.</span></span>



</div>

</div>

<div>

## <a name="director"></a><span data-ttu-id="a532e-206">Директор</span><span class="sxs-lookup"><span data-stu-id="a532e-206">Director</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a532e-207">Растянутые пулы не поддерживаются для этой роли сервера.</span><span class="sxs-lookup"><span data-stu-id="a532e-207">Stretched pools are not supported for this server role.</span></span>



</div>

<span data-ttu-id="a532e-208">При развертывании роли сервера Director рекомендуется развертывать один директор для каждого удаленного пользователя 12 000, который будет обращаться к сайту одновременно.</span><span class="sxs-lookup"><span data-stu-id="a532e-208">If you deploy the Director server role we recommend that you deploy one Director for every 12,000 remote users who will access a site concurrently.</span></span> <span data-ttu-id="a532e-209">Как минимум мы рекомендуем двум директорам для обеспечения высокой доступности.</span><span class="sxs-lookup"><span data-stu-id="a532e-209">At a minimum we recommend two Directors for high availability.</span></span> <span data-ttu-id="a532e-210">В этих рекомендациях предполагается, что оборудование пограничных серверов соответствует рекомендациям [серверных аппаратных платформ для Lync server 2013](lync-server-2013-server-hardware-platforms.md).</span><span class="sxs-lookup"><span data-stu-id="a532e-210">These recommendations assume that the hardware for your Edge Servers meets the recommendations in [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md).</span></span>

<span data-ttu-id="a532e-211">При учете количества пользователей для директоров Включите пользователей, размещенных на устройствах для обеспечения связи в филиалах и серверах для обеспечения связи в филиалах, которые связаны с пулом переднего плана на этом сайте.</span><span class="sxs-lookup"><span data-stu-id="a532e-211">When you account for the number of users for the Directors, include the users homed on Survivable Branch Appliances and Survivable Branch Servers at branch offices that are associated with a Front End pool at this site.</span></span>

</div>

<div>

## <a name="mediation-server"></a><span data-ttu-id="a532e-212">Mediation Server (Сервер-посредник);</span><span class="sxs-lookup"><span data-stu-id="a532e-212">Mediation Server</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a532e-213">Растянутые пулы не поддерживаются для этой роли сервера.</span><span class="sxs-lookup"><span data-stu-id="a532e-213">Stretched pools are not supported for this server role.</span></span>



</div>

<span data-ttu-id="a532e-214">При совместном размещении сервера-посредника с сервером переднего плана сервер-посредник работает на каждом сервере переднего плана в пуле и должен обеспечивать достаточную емкость для пользователей в пуле.</span><span class="sxs-lookup"><span data-stu-id="a532e-214">If you collocate Mediation Server with Front End Server, Mediation Server runs on every Front End Server in the pool, and should provide enough capacity for the users in the pool.</span></span>

<span data-ttu-id="a532e-215">Если развернуть автономный пул серверов-посредников, то сколько серверов-посредников необходимо развернуть, зависит от многих факторов, в том числе оборудования, используемого для сервера-посредника, количества пользователей VoIP, числа одноранговых шлюзов, которые каждый из них контролирует, трафик, занятый через эти шлюзы, а также процент вызовов с носителями, которые обходят сервер-посредник.</span><span class="sxs-lookup"><span data-stu-id="a532e-215">If you deploy a stand-alone Mediation Server pool, then how many Mediation Servers to deploy depends on many factors, including the hardware used for Mediation Server, the number of VoIP users you have, the number of gateway peers that each Mediation Server pool controls, the busy hour traffic through those gateways, and the percentage of calls with media that bypasses the Mediation Server.</span></span>

<span data-ttu-id="a532e-216">В следующих таблицах приводятся рекомендации по количеству одновременных вызовов, которые может обрабатывать сервер-посредник, предполагая, что оборудование для серверов-посредников соответствует требованиям в [аппаратных платформах сервера для Lync server 2013](lync-server-2013-server-hardware-platforms.md) и что технология Hyper-Threading включена.</span><span class="sxs-lookup"><span data-stu-id="a532e-216">The following tables provide a guideline for how many concurrent calls a Mediation Server can handle, assuming that the hardware for the Mediation Servers meets the requirements in [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md) and that hyper-threading is enabled.</span></span> <span data-ttu-id="a532e-217">Подробные сведения о масштабируемости сервера-посредника приведены в статье [Оценка использования голосовой связи и трафика для Lync server 2013](lync-server-2013-estimating-voice-usage-and-traffic.md) и [рекомендации по развертыванию для сервера-посредника в Lync Server 2013](lync-server-2013-deployment-guidelines-for-mediation-server.md).</span><span class="sxs-lookup"><span data-stu-id="a532e-217">For details about Mediation Server scalability, see [Estimating voice usage and traffic for Lync Server 2013](lync-server-2013-estimating-voice-usage-and-traffic.md) and [Deployment guidelines for Mediation Server in Lync Server 2013](lync-server-2013-deployment-guidelines-for-mediation-server.md).</span></span>

<span data-ttu-id="a532e-218">Во всех приведенных ниже таблицах предполагается использование, как показано в разделе [User Models in Lync Server 2013](lync-server-2013-user-models.md).</span><span class="sxs-lookup"><span data-stu-id="a532e-218">All the following tables assume usage as summarized in [User models in Lync Server 2013](lync-server-2013-user-models.md).</span></span>

### <a name="stand-alone-mediation-server-capacity-70-internal-users-30-external-users-with-non-bypass-call-capacity-media-transcoding-performed-by-mediation-server"></a><span data-ttu-id="a532e-219">Объем автономного сервера-посредника: 70% внутренних пользователей, 30% внешних пользователей с необходным объемом вызовов (перекодировка мультимедиа, выполненная сервером-посредником)</span><span class="sxs-lookup"><span data-stu-id="a532e-219">Stand-alone Mediation Server Capacity: 70% Internal Users, 30% External users with non-bypass call capacity (media transcoding performed by Mediation Server)</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a532e-220">Серверное оборудование</span><span class="sxs-lookup"><span data-stu-id="a532e-220">Server hardware</span></span></th>
<th><span data-ttu-id="a532e-221">Максимальное количество звонков</span><span class="sxs-lookup"><span data-stu-id="a532e-221">Maximum number of calls</span></span></th>
<th><span data-ttu-id="a532e-222">Максимальное количество линий T1</span><span class="sxs-lookup"><span data-stu-id="a532e-222">Maximum number of T1 lines</span></span></th>
<th><span data-ttu-id="a532e-223">Максимальное количество линий E1</span><span class="sxs-lookup"><span data-stu-id="a532e-223">Maximum number of E1 lines</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a532e-224">Два шестиядерных процессора 2,26 ГГц с поддержкой технологии Hyper-Threading (<strong>технология Hyper-Threading отключена</strong>), память 32 ГБ и одна двухпортовая сетевая карта.</span><span class="sxs-lookup"><span data-stu-id="a532e-224">Dual processor, hex core, 2.26 GHz hyper-threaded CPU <strong>with hyper-threading disabled</strong>, with 32 GB memory and one dual-port network adapter card.</span></span></p></td>
<td><p><span data-ttu-id="a532e-225">1100</span><span class="sxs-lookup"><span data-stu-id="a532e-225">1100</span></span></p></td>
<td><p><span data-ttu-id="a532e-226">46</span><span class="sxs-lookup"><span data-stu-id="a532e-226">46</span></span></p></td>
<td><p><span data-ttu-id="a532e-227">35</span><span class="sxs-lookup"><span data-stu-id="a532e-227">35</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a532e-228">Два шестиядерных процессора 2,26 ГГц с поддержкой технологии Hyper-Threading, память 32 ГБ и одна двухпортовая сетевая карта.</span><span class="sxs-lookup"><span data-stu-id="a532e-228">Dual processor, hex core, 2.26 GHz hyper-threaded CPU, with 32 GB memory and one dual-port network adapter card.</span></span></p></td>
<td><p><span data-ttu-id="a532e-229">1500</span><span class="sxs-lookup"><span data-stu-id="a532e-229">1500</span></span></p></td>
<td><p><span data-ttu-id="a532e-230">63</span><span class="sxs-lookup"><span data-stu-id="a532e-230">63</span></span></p></td>
<td><p><span data-ttu-id="a532e-231">47</span><span class="sxs-lookup"><span data-stu-id="a532e-231">47</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="a532e-232">Несмотря на то, что для тестирования производительности использовались серверы с 32 ГБ памяти, серверы с 16 ГБ памяти поддерживаются для изолированного сервера-посредника и достаточно для обеспечения производительности, представленной в этой таблице.</span><span class="sxs-lookup"><span data-stu-id="a532e-232">Although servers with 32 GB of memory were used for performance testing, servers with 16 GB of memory are supported for stand-alone Mediation Server, and are sufficient to provide the performance shown in this table.</span></span>



</div>

### <a name="mediation-server-capacity-mediation-server-collocated-with-front-end-server-70-internal-users-30-external-users-non-bypass-call-capacity-media-processing-performed-by-mediation-server"></a><span data-ttu-id="a532e-233">Емкость сервера-посредника (сервер-посредник, совместно размещенный с сервером переднего плана) 70% внутренних пользователей, 30% внешних пользователей, без обхода емкости вызовов (обработка мультимедиа выполняется сервером-посредником)</span><span class="sxs-lookup"><span data-stu-id="a532e-233">Mediation Server Capacity (Mediation Server Collocated with Front End Server) 70% Internal Users, 30% External Users, Non-Bypass Call Capacity (Media Processing Performed by Mediation Server)</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a532e-234">Серверное оборудование</span><span class="sxs-lookup"><span data-stu-id="a532e-234">Server hardware</span></span></th>
<th><span data-ttu-id="a532e-235">Максимальное количество звонков</span><span class="sxs-lookup"><span data-stu-id="a532e-235">Maximum number of calls</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a532e-236">Два шестиядерных процессора 2,26 ГГц с поддержкой технологии Hyper-Threading, память 32 ГБ и две сетевых карты со скоростью 1 Гбит/с.</span><span class="sxs-lookup"><span data-stu-id="a532e-236">Dual processor, hex core, 2.26 GHz hyper-threaded CPU, with 32 GB memory and 2 1GB network adapter cards.</span></span></p></td>
<td><p><span data-ttu-id="a532e-237">150</span><span class="sxs-lookup"><span data-stu-id="a532e-237">150</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="a532e-238">Это число значительно меньше числа для изолированного сервера-посредника, так как сервер переднего плана должен обрабатывать другие функции и функции для 6600 пользователей, размещенных на нем, в дополнение к перекодировке, необходимой для голосовых вызовов.</span><span class="sxs-lookup"><span data-stu-id="a532e-238">This number is much smaller than the numbers for the stand-alone Mediation Server because the Front End Server has to handle other features and functions for the 6600 users homed on it, in addition to the transcoding needed for voice calls.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="a532e-239">Чтобы увеличить производительность сервера-посредника, следует включить масштабирование на стороне приема (RSS) в сетевых адаптерах серверов-посредников.</span><span class="sxs-lookup"><span data-stu-id="a532e-239">To improve the performance of the Mediation Server, you should enable receive-side scaling (RSS) on the network adapters on your Mediation Servers.</span></span> <span data-ttu-id="a532e-240">RSS позволяет обрабатывать входящие пакеты параллельно несколькими процессорами на сервере.</span><span class="sxs-lookup"><span data-stu-id="a532e-240">RSS enables incoming packets to be handled in parallel by multiple processors on the server.</span></span> <span data-ttu-id="a532e-241">Дополнительные сведения см. в разделе "усовершенствованные возможности масштабирования на стороне Windows Server 2008" <A href="https://go.microsoft.com/fwlink/p/?linkid=268731">https://go.microsoft.com/fwlink/p/?linkId=268731</A> .</span><span class="sxs-lookup"><span data-stu-id="a532e-241">For details, see "Receive-Side Scaling Enhancements in Windows Server 2008" at <A href="https://go.microsoft.com/fwlink/p/?linkid=268731">https://go.microsoft.com/fwlink/p/?linkId=268731</A>.</span></span> <span data-ttu-id="a532e-242">Сведения о включении RSS см. в документации вашего сетевого адаптера.</span><span class="sxs-lookup"><span data-stu-id="a532e-242">For details about how to enable RSS, see your network adapter documentation.</span></span>



</div>

</div>

<div>

## <a name="back-end-server"></a><span data-ttu-id="a532e-243">Внутренний сервер</span><span class="sxs-lookup"><span data-stu-id="a532e-243">Back End Server</span></span>

<span data-ttu-id="a532e-244">В Lync Server 2013 базы данных присутствия размещаются на серверах переднего плана, а не на внутреннем сервере.</span><span class="sxs-lookup"><span data-stu-id="a532e-244">In Lync Server 2013, the presence databases are located on the Front End Servers instead of the Back End Server.</span></span> <span data-ttu-id="a532e-245">Это значительно упрощается для каждого внутреннего сервера в Lync Server 2013, что соответствует требованиям к оборудованию для сервера переднего плана.</span><span class="sxs-lookup"><span data-stu-id="a532e-245">This has resulted in a much simpler requirement for each Back End Server in Lync Server 2013, equivalent to the hardware requirement for the Front End Server.</span></span> <span data-ttu-id="a532e-246">Сравните это с Lync Server 2010, где фоновый сервер должен быть более мощным сервером с 25 дисками.</span><span class="sxs-lookup"><span data-stu-id="a532e-246">Contrast this to Lync Server 2010, where the Back End Server was required to be a much higher grade server with 25 disks.</span></span> <span data-ttu-id="a532e-247">Тем не менее, в этом разделе, а также в [серверных аппаратных платформах для Lync Server 2013](lync-server-2013-server-hardware-platforms.md)не следует выполнять загрузку внутренних серверов.</span><span class="sxs-lookup"><span data-stu-id="a532e-247">However, the workload of Back End Servers is still such that you should not fail to meet the hardware recommendations listed earlier in this section and in [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md).</span></span>

<span data-ttu-id="a532e-248">Для обеспечения высокой доступности внутреннего сервера рекомендуется развертывать зеркальное отображение сервера.</span><span class="sxs-lookup"><span data-stu-id="a532e-248">To provide high availability of your Back End Server, we recommend deploying server mirroring.</span></span> <span data-ttu-id="a532e-249">Более подробную информацию можно узнать [в статье высокая доступность внутреннего сервера в Lync server 2013](lync-server-2013-back-end-server-high-availability.md).</span><span class="sxs-lookup"><span data-stu-id="a532e-249">For more information, see [Back End Server high availability in Lync Server 2013](lync-server-2013-back-end-server-high-availability.md).</span></span>

</div>

<div>

## <a name="monitoring-and-archiving"></a><span data-ttu-id="a532e-250">Мониторинг и архивирование</span><span class="sxs-lookup"><span data-stu-id="a532e-250">Monitoring and Archiving</span></span>

<span data-ttu-id="a532e-251">В Lync Server 2013 при развертывании мониторинга или архивации функция переднего плана этих служб работает на серверах переднего плана, а не на отдельных ролях сервера.</span><span class="sxs-lookup"><span data-stu-id="a532e-251">In Lync Server 2013, if you deploy Monitoring or Archiving, the front end functionality of these services runs on the Front End Servers, instead of on separate server roles.</span></span> <span data-ttu-id="a532e-252">Службы мониторинга и архивации используют собственные хранилища баз данных, независимые от хранилища тылового сервера.</span><span class="sxs-lookup"><span data-stu-id="a532e-252">Monitoring and Archiving each still use their own database store, separate from the Back End store.</span></span> <span data-ttu-id="a532e-253">Кроме того, если вы развернули Exchange 2013, вы можете хранить данные для архивации мгновенных сообщений в Exchange, а не в специальном хранилище SQL.</span><span class="sxs-lookup"><span data-stu-id="a532e-253">Alternatively, if you have Exchange 2013 deployed, you can store instant message Archiving data in Exchange instead of in a dedicated SQL store.</span></span>

<span data-ttu-id="a532e-254">В следующей таблице показаны приблизительные значения размера хранилища базы данных на пользователя в день, необходимые для данных мониторинга и архивации.</span><span class="sxs-lookup"><span data-stu-id="a532e-254">The following table indicates approximately how much database storage is required per user per day for Monitoring and Archiving data.</span></span>


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
<td><p><span data-ttu-id="a532e-255"><strong>CDR (мониторинг)</strong></span><span class="sxs-lookup"><span data-stu-id="a532e-255"><strong>CDR (Monitoring)</strong></span></span></p></td>
<td><p><span data-ttu-id="a532e-256"><strong>QoE (мониторинг)</strong></span><span class="sxs-lookup"><span data-stu-id="a532e-256"><strong>QoE (Monitoring)</strong></span></span></p></td>
<td><p><span data-ttu-id="a532e-257"><strong>Архивация</strong></span><span class="sxs-lookup"><span data-stu-id="a532e-257"><strong>Archiving</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a532e-258">Дисковое пространство на пользователя в день</span><span class="sxs-lookup"><span data-stu-id="a532e-258">Disk space required per user per day</span></span></p></td>
<td><p><span data-ttu-id="a532e-259">49 кб</span><span class="sxs-lookup"><span data-stu-id="a532e-259">49 KB</span></span></p></td>
<td><p><span data-ttu-id="a532e-260">28 кб</span><span class="sxs-lookup"><span data-stu-id="a532e-260">28 KB</span></span></p></td>
<td><p><span data-ttu-id="a532e-261">57 кб</span><span class="sxs-lookup"><span data-stu-id="a532e-261">57 KB</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="a532e-262">В следующей таблице описано оборудование сервера базы данных мониторинга и архивации, которое использовалось в корпорации Майкрософт при тестировании производительности.</span><span class="sxs-lookup"><span data-stu-id="a532e-262">Microsoft used the hardware in the following table for the database server for Monitoring and Archiving during its performance testing.</span></span> <span data-ttu-id="a532e-263">Тестирование собрало данные двух интерфейсных пулов, каждый из которых содержал 80 000 пользователей.</span><span class="sxs-lookup"><span data-stu-id="a532e-263">The testing collected the data of two Front End pools, each of which contained 80,000 users.</span></span>

### <a name="hardware-used-in-monitoring-and-archiving-performance-testing"></a><span data-ttu-id="a532e-264">Оборудование, использованное при тестировании производительности мониторинга и архивации</span><span class="sxs-lookup"><span data-stu-id="a532e-264">Hardware Used in Monitoring and Archiving Performance Testing</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a532e-265">Компонент оборудования</span><span class="sxs-lookup"><span data-stu-id="a532e-265">Hardware component</span></span></th>
<th><span data-ttu-id="a532e-266">Рекомендуемый</span><span class="sxs-lookup"><span data-stu-id="a532e-266">Recommended</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a532e-267">ЦП</span><span class="sxs-lookup"><span data-stu-id="a532e-267">CPU</span></span></p></td>
<td><p><span data-ttu-id="a532e-268">Два 64-разрядных шестиядерных процессора 2,26 ГГц или более мощных</span><span class="sxs-lookup"><span data-stu-id="a532e-268">64-bit dual processor, hex-core, 2.26 gigahertz (GHz) or higher</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a532e-269">Память</span><span class="sxs-lookup"><span data-stu-id="a532e-269">Memory</span></span></p></td>
<td><p><span data-ttu-id="a532e-270">48 ГБ</span><span class="sxs-lookup"><span data-stu-id="a532e-270">48 gigabytes (GB)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a532e-271">Диск</span><span class="sxs-lookup"><span data-stu-id="a532e-271">Disk</span></span></p></td>
<td><p><span data-ttu-id="a532e-272">25 дисков со скоростью вращения 10000 об/мин по 300 ГБ со следующей конфигурацией</span><span class="sxs-lookup"><span data-stu-id="a532e-272">25 10,000-RPM hard disk drives with 300 GB on each disk, with the following configuration</span></span></p>
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
<td><p><span data-ttu-id="a532e-273"><strong>Drive</strong></span><span class="sxs-lookup"><span data-stu-id="a532e-273"><strong>Drive</strong></span></span></p></td>
<td><p><span data-ttu-id="a532e-274"><strong>Конфигурация RAID</strong></span><span class="sxs-lookup"><span data-stu-id="a532e-274"><strong>RAID Configuration</strong></span></span></p></td>
<td><p><span data-ttu-id="a532e-275"><strong>Количество дисков</strong></span><span class="sxs-lookup"><span data-stu-id="a532e-275"><strong>Number of disks</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a532e-276">Файлы баз данных CDR, QoE и архивации, на одном диске</span><span class="sxs-lookup"><span data-stu-id="a532e-276">CDR, QoE, and Archiving database data files, on a single drive</span></span></p></td>
<td><p><span data-ttu-id="a532e-277">1 + 0</span><span class="sxs-lookup"><span data-stu-id="a532e-277">1+0</span></span></p></td>
<td><p><span data-ttu-id="a532e-278">16 </span><span class="sxs-lookup"><span data-stu-id="a532e-278">16</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a532e-279">Файл журнала базы данных CDR</span><span class="sxs-lookup"><span data-stu-id="a532e-279">CDR database log file</span></span></p></td>
<td><p><span data-ttu-id="a532e-280">1,1</span><span class="sxs-lookup"><span data-stu-id="a532e-280">1</span></span></p></td>
<td><p><span data-ttu-id="a532e-281">2</span><span class="sxs-lookup"><span data-stu-id="a532e-281">2</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a532e-282">Файл журнала базы данных QoE</span><span class="sxs-lookup"><span data-stu-id="a532e-282">QoE database log file</span></span></p></td>
<td><p><span data-ttu-id="a532e-283">1,1</span><span class="sxs-lookup"><span data-stu-id="a532e-283">1</span></span></p></td>
<td><p><span data-ttu-id="a532e-284">2</span><span class="sxs-lookup"><span data-stu-id="a532e-284">2</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a532e-285">Файл журнала базы данных архивации</span><span class="sxs-lookup"><span data-stu-id="a532e-285">Archiving database log file</span></span></p></td>
<td><p><span data-ttu-id="a532e-286">1,1</span><span class="sxs-lookup"><span data-stu-id="a532e-286">1</span></span></p></td>
<td><p><span data-ttu-id="a532e-287">2</span><span class="sxs-lookup"><span data-stu-id="a532e-287">2</span></span></p></td>
</tr>
</tbody>
</table>

</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a532e-288">Сеть</span><span class="sxs-lookup"><span data-stu-id="a532e-288">Network</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="a532e-289">1 двухпортовый сетевой адаптер, 1 Гбит/с или выше (рекомендуется 2, что требует объединения с одним MAC-адресом и одним IP-адресом)</span><span class="sxs-lookup"><span data-stu-id="a532e-289">1 dual-port network adapter, 1 Gbps or higher (2 recommended, which requires teaming with a single MAC address and single IP address)</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="a532e-290">Содержание</span><span class="sxs-lookup"><span data-stu-id="a532e-290">In This Section</span></span>

  - [<span data-ttu-id="a532e-291">Оценка использования голосовой связи и трафика для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a532e-291">Estimating voice usage and traffic for Lync Server 2013</span></span>](lync-server-2013-estimating-voice-usage-and-traffic.md)

  - [<span data-ttu-id="a532e-292">Рекомендации по развертыванию сервера-посредника в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a532e-292">Deployment guidelines for Mediation Server in Lync Server 2013</span></span>](lync-server-2013-deployment-guidelines-for-mediation-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

