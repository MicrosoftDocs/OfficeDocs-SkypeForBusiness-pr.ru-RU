---
title: Планирование мощностей Lync Server 2013 с помощью пользовательских моделей
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
ms.openlocfilehash: cd9b3861e4c84b8df7585ad5cfbdfd5a82359282
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736994"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="capacity-planning-for-lync-server-2013-using-the-user-models"></a><span data-ttu-id="25753-102">Планирование мощностей для Lync Server 2013 с помощью пользовательских моделей</span><span class="sxs-lookup"><span data-stu-id="25753-102">Capacity planning for Lync Server 2013 using the user models</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="25753-103">_**Тема последнего изменения:** 2014-01-14_</span><span class="sxs-lookup"><span data-stu-id="25753-103">_**Topic Last Modified:** 2014-01-14_</span></span>

<span data-ttu-id="25753-104">В этом разделе приводятся рекомендации о том, сколько серверов нужно на сайте для числа пользователей на сайте в соответствии с описанием использования в [моделях пользователей в Lync Server 2013](lync-server-2013-user-models.md).</span><span class="sxs-lookup"><span data-stu-id="25753-104">This section provides guidance on how many servers you need at a site for the number of users at that site, according to the usage described in [User models in Lync Server 2013](lync-server-2013-user-models.md).</span></span>

<div>

## <a name="tested-hardware-platform"></a><span data-ttu-id="25753-105">Аппаратная платформа для тестирования</span><span class="sxs-lookup"><span data-stu-id="25753-105">Tested Hardware Platform</span></span>

<span data-ttu-id="25753-106">Все результаты и рекомендации по развертыванию в этом разделе основаны на тестировании производительности на серверах с оборудованием, описанных в приведенной ниже таблице.</span><span class="sxs-lookup"><span data-stu-id="25753-106">All the performance results and deployment recommendations in this section are based on performance testing on servers running the hardware described in the following table.</span></span> <span data-ttu-id="25753-107">Мы рекомендуем использовать похожие аппаратные средства.</span><span class="sxs-lookup"><span data-stu-id="25753-107">We recommend that you use similar hardware.</span></span> <span data-ttu-id="25753-108">Если вы используете менее мощное оборудование, то могут возникать проблемы с функциональностью или с низкой производительностью.</span><span class="sxs-lookup"><span data-stu-id="25753-108">If you use less powerful hardware, you may experience functionality problems or poor performance.</span></span> <span data-ttu-id="25753-109">Обратите внимание на то, что эти рекомендации по оборудованию выше, чем в предыдущих версиях Lync Server.</span><span class="sxs-lookup"><span data-stu-id="25753-109">Note that these hardware recommendations are higher than those of previous versions of Lync Server.</span></span>

### <a name="hardware-used-in-performance-testing"></a><span data-ttu-id="25753-110">Оборудование, использованное при проведении тестирования</span><span class="sxs-lookup"><span data-stu-id="25753-110">Hardware Used in Performance Testing</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="25753-111">Аппаратный компонент</span><span class="sxs-lookup"><span data-stu-id="25753-111">Hardware component</span></span></th>
<th><span data-ttu-id="25753-112">Рекомендуется</span><span class="sxs-lookup"><span data-stu-id="25753-112">Recommended</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="25753-113">ЦП</span><span class="sxs-lookup"><span data-stu-id="25753-113">CPU</span></span></p></td>
<td><p><span data-ttu-id="25753-114">64-разрядный двухпроцессорный комплекс, шестиядерный, 2,26 ГГц и выше</span><span class="sxs-lookup"><span data-stu-id="25753-114">64-bit dual processor, hex-core, 2.26 gigahertz (GHz) or higher</span></span></p>
<p><span data-ttu-id="25753-115">Процессоры Intel Itanium не поддерживаются для ролей сервера Lync Server.</span><span class="sxs-lookup"><span data-stu-id="25753-115">Intel Itanium processors are not supported for Lync Server server roles.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="25753-116">Память</span><span class="sxs-lookup"><span data-stu-id="25753-116">Memory</span></span></p></td>
<td><p><span data-ttu-id="25753-117">32 ГБ </span><span class="sxs-lookup"><span data-stu-id="25753-117">32 gigabytes (GB)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="25753-118">Диск</span><span class="sxs-lookup"><span data-stu-id="25753-118">Disk</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="25753-119">8 или больше дисков со скоростью вращения 10 000 об/мин и как минимум 72 ГБ свободного места.</span><span class="sxs-lookup"><span data-stu-id="25753-119">8 or more 10,000-RPM hard disk drives with at least 72 GB free disk space.</span></span></p>
<p><span data-ttu-id="25753-120">Два диска должны использовать массив RAID 1, а остальные шесть – RAID 10.</span><span class="sxs-lookup"><span data-stu-id="25753-120">Two of the disks should use RAID 1, and six should use RAID 10.</span></span></p>
<p><span data-ttu-id="25753-121">-/</span><span class="sxs-lookup"><span data-stu-id="25753-121">- OR -</span></span></p></li>
<li><p><span data-ttu-id="25753-122">Твердотельные накопители (SSD) с производительностью, аналогичной производительности 8 жестких дисков с частотой вращения шпинделя 10 000 об/мин. </span><span class="sxs-lookup"><span data-stu-id="25753-122">Solid state drives (SSDs) which provide performance similar to 8 10,000-RPM mechanical disk drives.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="25753-123">Сеть</span><span class="sxs-lookup"><span data-stu-id="25753-123">Network</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="25753-124">1 двухпортовый сетевой адаптер, 1 Гбит/с или выше (рекомендуется 2 Гбит/с, для этого требуется объединение через один MAC-адрес и один IP-адрес)</span><span class="sxs-lookup"><span data-stu-id="25753-124">1 dual-port network adapter, 1 Gbps or higher (2 recommended, which requires teaming with a single MAC address and single IP address)</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="summary-of-results"></a><span data-ttu-id="25753-125">Сводка результатов</span><span class="sxs-lookup"><span data-stu-id="25753-125">Summary of Results</span></span>

<span data-ttu-id="25753-126">Эти рекомендации описаны в приведенной ниже таблице.</span><span class="sxs-lookup"><span data-stu-id="25753-126">The following table summarizes these recommendations.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="25753-127">Роль сервера</span><span class="sxs-lookup"><span data-stu-id="25753-127">Server role</span></span></th>
<th><span data-ttu-id="25753-128">Максимальное число поддерживаемых пользователей</span><span class="sxs-lookup"><span data-stu-id="25753-128">Maximum number of users supported</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="25753-129">Пул переднего плана с двенадцать серверными интерфейсами и одним сервером или зеркальным набором серверных пар серверов.</span><span class="sxs-lookup"><span data-stu-id="25753-129">Front End pool with twelve Front End Servers and one Back End Server or a mirrored pair of Back End Servers.</span></span></p></td>
<td><p><span data-ttu-id="25753-130">80 000 одновременно зарегистрированных уникальных пользователей, плюс 50% пользователей с несколькими точками присутствия, представляющими немобильные экземпляры, плюс 40% пользователей Mobility; итого 152 000 конечных точек.</span><span class="sxs-lookup"><span data-stu-id="25753-130">80,000 unique users simultaneously logged in, plus 50% multiple points of presence (MPOP) representing non-mobile instances, plus 40% of users enabled for Mobility for a total of 152,000 endpoints.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="25753-131">Аудио- и видеоконференции</span><span class="sxs-lookup"><span data-stu-id="25753-131">A/V Conferencing</span></span></p></td>
<td><p><span data-ttu-id="25753-132">Служба конференц-связи A/V, предоставляемая пулом переднего плана, поддерживает конференции пула, предоставили максимальный размер конференции для пользователей 250 и только одну такую крупную конференцию, запущенную за один раз.</span><span class="sxs-lookup"><span data-stu-id="25753-132">The A/V Conferencing service provided by a Front End pool supports the pool’s conferences assuming a maximum conference size of 250 users, and only one such large conference running at a time.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="25753-133">Кроме того, вы можете поддерживать большие конференции пользователей 250 и 1000 путем развертывания отдельного пула переднего плана с двумя серверами переднего плана для размещения больших конференций.</span><span class="sxs-lookup"><span data-stu-id="25753-133">Additionally, you can support large conferences of between 250 and 1000 users by deploying a separate Front End pool with two Front End Servers to host the large conferences.</span></span> <span data-ttu-id="25753-134">Дополнительные сведения можно найти в разделе <A href="lync-server-2013-supporting-large-meetings.md">Поддержка собраний большого размера с помощью Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="25753-134">For details, see <A href="lync-server-2013-supporting-large-meetings.md">Supporting large meetings using Lync Server 2013</A>.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="25753-135">Один пограничный сервер</span><span class="sxs-lookup"><span data-stu-id="25753-135">One Edge Server</span></span></p></td>
<td><p><span data-ttu-id="25753-136">12 000 одновременные удаленные пользователи</span><span class="sxs-lookup"><span data-stu-id="25753-136">12,000 concurrent remote users</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="25753-137">Один режиссер</span><span class="sxs-lookup"><span data-stu-id="25753-137">One Director</span></span></p></td>
<td><p><span data-ttu-id="25753-138">12 000 одновременные удаленные пользователи</span><span class="sxs-lookup"><span data-stu-id="25753-138">12,000 concurrent remote users</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="25753-139">Мониторинг и архивирование</span><span class="sxs-lookup"><span data-stu-id="25753-139">Monitoring and Archiving</span></span></p></td>
<td><p><span data-ttu-id="25753-140">В Lync Server 2013 теперь можно выполнять мониторинг и архивация интерфейсных служб на каждом внешнем сервере, а не на отдельных ролях сервера.</span><span class="sxs-lookup"><span data-stu-id="25753-140">In Lync Server 2013, the Monitoring and Archiving front end services now run on each Front End Server, instead of on separate server roles.</span></span></p>
<p><span data-ttu-id="25753-141">Для мониторинга и архивирования требуются собственные хранилища баз данных.</span><span class="sxs-lookup"><span data-stu-id="25753-141">Monitoring and Archiving each still require their own database stores.</span></span> <span data-ttu-id="25753-142">Если вы также запускаете Exchange 2013, вы можете хранить данные архивации в Exchange, а не в выделенной базе данных SQL.</span><span class="sxs-lookup"><span data-stu-id="25753-142">If you also run Exchange 2013, you can keep your Archiving data in Exchange, rather than in a dedicated SQL database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="25753-143">Один сервер обновлений</span><span class="sxs-lookup"><span data-stu-id="25753-143">One Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="25753-144">Сервер-посредник, выровненный по внешнему серверу, запускается на каждом сервере переднего плана в пуле и должен обеспечивать достаточную емкость для пользователей в пуле.</span><span class="sxs-lookup"><span data-stu-id="25753-144">Mediation Server collocated with Front End Server runs on every Front End Server in a pool, and should provide enough capacity for the users in the pool.</span></span> <span data-ttu-id="25753-145">Для изолированного сервера-посредника ознакомьтесь с разделом "сервер-посредник" Далее в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="25753-145">For stand-alone Mediation Server, see the “Mediation Server” section later in this topic.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="25753-146">Один стандартный сервер выпуска</span><span class="sxs-lookup"><span data-stu-id="25753-146">One Standard Edition server</span></span></p></td>
<td><p><span data-ttu-id="25753-147">Мы настоятельно рекомендуем использовать для размещения пользователей сервер стандартных выпусков, используя рекомендации по <a href="lync-server-2013-planning-for-high-availability-and-disaster-recovery.md">планированию высокой доступности и аварийного восстановления в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="25753-147">We strongly recommend that if you use Standard Edition servers to host users, you always use two servers, paired using the recommendations in <a href="lync-server-2013-planning-for-high-availability-and-disaster-recovery.md">Planning for high availability and disaster recovery in Lync Server 2013</a>.</span></span> <span data-ttu-id="25753-148">Each server in the pair can host up to 2,500 users, and if one server fails the remaining server can support 5,000 users in a failover scenario.</span><span class="sxs-lookup"><span data-stu-id="25753-148">Each server in the pair can host up to 2,500 users, and if one server fails the remaining server can support 5,000 users in a failover scenario.</span></span></p>
<p><span data-ttu-id="25753-149">If your deployment includes a significant amount of audio or video traffic, server performance may suffer with more than 2,500 users per server.</span><span class="sxs-lookup"><span data-stu-id="25753-149">If your deployment includes a significant amount of audio or video traffic, server performance may suffer with more than 2,500 users per server.</span></span> <span data-ttu-id="25753-150">В этом случае рекомендуется добавить другие серверы стандартных выпусков или перейти в Lync Server Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="25753-150">In this case, you should consider adding more Standard Edition servers or moving to Lync Server Enterprise Edition.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="front-end-server"></a><span data-ttu-id="25753-151">переднего плана</span><span class="sxs-lookup"><span data-stu-id="25753-151">Front End Server</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="25753-152">Растянутые пулы для этой роли сервера не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="25753-152">Stretched pools are not supported for this server role.</span></span>



</div>

<span data-ttu-id="25753-153">В пуле переднего плана вы должны иметь один сервер переднего плана для всех пользователей 6 660, размещенных в пуле, предполагая, что технология Hyper-Threading включена на всех серверах пула, и что оборудование сервера соответствует рекомендациям, приведенным в разделе [аппаратные платформы сервера для Lync Server 2013](lync-server-2013-server-hardware-platforms.md).</span><span class="sxs-lookup"><span data-stu-id="25753-153">In a Front End pool, you should have one Front End Server for every 6,660 users homed in the pool, assuming that hyper-threading is enabled on all servers in the pool, and that the server hardware meets the recommendations in [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md).</span></span> <span data-ttu-id="25753-154">Максимальное количество пользователей в одном пуле переднего плана — 80 000, предполагая, что технология Hyper-Threading включена на всех серверах в пуле.</span><span class="sxs-lookup"><span data-stu-id="25753-154">The maximum number of users in one Front End pool is 80,000, assuming that hyper-threading is enabled on all the servers in the pool.</span></span> <span data-ttu-id="25753-155">Если у вас более 80 000 пользователей на сайте, вы можете развернуть более одного пула переднего плана.</span><span class="sxs-lookup"><span data-stu-id="25753-155">If you have more than 80,000 users at a site, you can deploy more than one Front End pool.</span></span>

<span data-ttu-id="25753-156">Если вы захотите количество пользователей в пуле переднего плана, включите пользователей, которые размещаются на устройствах с бесперебойной ветвлением и бесперебойно работающих серверах филиалов в филиалах, связанных с этим пулом переднего плана.</span><span class="sxs-lookup"><span data-stu-id="25753-156">When you account for the number of users in a Front End pool, include the users homed on Survivable Branch Appliances and Survivable Branch Servers at branch offices that are associated with this Front End pool.</span></span>

<span data-ttu-id="25753-157">When an active server is unavailable, its connections are transferred automatically to the other servers in the pool.</span><span class="sxs-lookup"><span data-stu-id="25753-157">When an active server is unavailable, its connections are transferred automatically to the other servers in the pool.</span></span> <span data-ttu-id="25753-158">Например, если у вас есть 30 000 пользователей и пять серверов переднего плана, то если один сервер недоступен, то при подключении к нему для пользователей 6000 необходимо передать их на четыре сервера.</span><span class="sxs-lookup"><span data-stu-id="25753-158">For example, if you have 30,000 users and five Front End Servers, then if one server is unavailable, the connections of 6000 users need to be transferred to the other four servers.</span></span> <span data-ttu-id="25753-159">Оставшиеся четыре сервера будут иметь 7500 пользователей, что превышает рекомендованное число.</span><span class="sxs-lookup"><span data-stu-id="25753-159">The remaining four servers will each have 7500 users, which is a larger number than recommended.</span></span>

<span data-ttu-id="25753-160">Если вместо этого вы начали работать с шестью серверами переднего плана для пользователей 30 000, а затем они становятся недоступными, общее количество пользователей 5000 будет перенесено на оставшиеся пять серверов.</span><span class="sxs-lookup"><span data-stu-id="25753-160">If instead you had started with six Front End Servers for your 30,000 users and subsequently one became unavailable, a total of 5000 users will be moved to the remaining five servers.</span></span> <span data-ttu-id="25753-161">Пять серверов будут каждому узлу 6000, который входит в рекомендуемый диапазон.</span><span class="sxs-lookup"><span data-stu-id="25753-161">These five servers will each host 6000 users, which is in the recommended range.</span></span>

<span data-ttu-id="25753-162">Максимальное количество пользователей в пуле переднего плана — 80 000.</span><span class="sxs-lookup"><span data-stu-id="25753-162">The maximum number of users in a Front End pool is 80,000.</span></span> <span data-ttu-id="25753-163">Максимальное число серверов переднего плана в пуле составляет 12.</span><span class="sxs-lookup"><span data-stu-id="25753-163">The maximum number of Front End Servers in a pool is 12.</span></span>

<span data-ttu-id="25753-164">Для пула переднего плана с пользователями 80 000 для повышения производительности достаточно двенадцати серверов переднего плана в типичных развертываниях, которые следуют за [пользовательскими моделями в Lync Server 2013](lync-server-2013-user-models.md).</span><span class="sxs-lookup"><span data-stu-id="25753-164">For a Front End pool with 80,000 users, twelve Front End Servers is sufficient for performance, in typical deployments that follow the [User models in Lync Server 2013](lync-server-2013-user-models.md).</span></span> <span data-ttu-id="25753-165">Развертывание, разработанное для поддержки перехода на аварийное восстановление после восстановления, предполагает, что в каждом из двух подключенных интерфейсных пулов может находиться не более 40 000 пользователей, в которых каждый из них должен быть недоступен для пользователей обоих пулов. для другого.</span><span class="sxs-lookup"><span data-stu-id="25753-165">Deployments designed to support disaster recovery failover assume that a maximum of 40,000 users can be hosted in each of two paired Front End pools, in which each pool has enough Front End Servers to accommodate the users in both pools should one pool need to be failed over to the other.</span></span>

<span data-ttu-id="25753-166">Количество пользователей, которые поддерживают хорошую производительность с помощью определенного пула переднего плана, может отличаться от приведенных ниже.</span><span class="sxs-lookup"><span data-stu-id="25753-166">The number of users supported with good performance by a particular Front End pool may differ from these numbers for the following reasons:</span></span>

  - <span data-ttu-id="25753-167">Оборудование для серверов переднего плана не соответствует рекомендациям, описанным в разделе [аппаратные платформы сервера Lync server 2013](lync-server-2013-server-hardware-platforms.md).</span><span class="sxs-lookup"><span data-stu-id="25753-167">The hardware for your Front End Servers does not meet the recommendations in [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md).</span></span>

  - <span data-ttu-id="25753-168">Использование вашей организации значительно отличается от пользовательских моделей, например значительно больше трафика для проведения конференций.</span><span class="sxs-lookup"><span data-stu-id="25753-168">Your organization’s usage differs significantly from the user models, such as significantly more conferencing traffic.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="25753-169">В Lync Server 2013 базы данных присутствия теперь размещаются на серверах переднего плана, в отличие от Lync Server 2010, где они были размещены на обратном стороне сервера.</span><span class="sxs-lookup"><span data-stu-id="25753-169">In Lync Server 2013, the presence databases are now hosted on Front End Servers, unlike in Lync Server 2010 where they were hosted on the Back End Server.</span></span> <span data-ttu-id="25753-170">Это означает, что производительность диска и пропускная способность серверов переднего плана не должны быть скомпрометированы в рекомендациях, описанных выше в этом разделе, и в <A href="lync-server-2013-server-hardware-platforms.md">серверных аппаратных платформах для Lync Server 2013</A>независимо от количества пользователей, размещенных на серверах переднего плана.</span><span class="sxs-lookup"><span data-stu-id="25753-170">This means that the disk performance and capacity of your Front End Servers should not be compromised from the recommendations listed earlier in this section and in <A href="lync-server-2013-server-hardware-platforms.md">Server hardware platforms for Lync Server 2013</A>, regardless of the number of users hosted by your Front End Servers.</span></span>



</div>

<span data-ttu-id="25753-171">В приведенной ниже таблице показана средняя пропускная способность для обмена сообщениями и присутствия, если пользовательская модель определена в [пользовательских моделях в Lync Server 2013](lync-server-2013-user-models.md).</span><span class="sxs-lookup"><span data-stu-id="25753-171">The following table shows the average bandwidth for IM and presence, given the user model, as defined in [User models in Lync Server 2013](lync-server-2013-user-models.md).</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="25753-172">Средняя пропускная способность на пользователя</span><span class="sxs-lookup"><span data-stu-id="25753-172">Average bandwidth per user</span></span></th>
<th><span data-ttu-id="25753-173">Требования к пропускной способности на сервер переднего плана с пользователями 6 660</span><span class="sxs-lookup"><span data-stu-id="25753-173">Bandwidth requirements per Front End Server with 6,660 users</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="25753-174">1,3 Кбит/с</span><span class="sxs-lookup"><span data-stu-id="25753-174">1.3 Kpbs</span></span></p></td>
<td><p><span data-ttu-id="25753-175">13 Мбит/с</span><span class="sxs-lookup"><span data-stu-id="25753-175">13 Mbps</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="25753-176">Чтобы повысить производительность мультимедиа для совместной работы серверов конференц-связи и сервера-посредников на серверах переднего плана, необходимо включить масштабирование на стороне приема (RSS) на сетевых адаптерах на серверах переднего плана.</span><span class="sxs-lookup"><span data-stu-id="25753-176">To improve the media performance of the co-located A/V Conferencing and Mediation Server functionality on your Front End Servers, you should enable receive-side scaling (RSS) on the network adapters on your Front End Servers.</span></span> <span data-ttu-id="25753-177">RSS поддерживает параллельную обработку входящих пакетов несколькими процессорами сервера.</span><span class="sxs-lookup"><span data-stu-id="25753-177">RSS enables incoming packets to be handled in parallel by multiple processors on the server.</span></span> <span data-ttu-id="25753-178">Дополнительные сведения можно найти в разделе улучшенные возможности масштабирования на стороне приема в Windows Server 2008 <A href="http://go.microsoft.com/fwlink/p/?linkid=268731">http://go.microsoft.com/fwlink/p/?linkId=268731</A>.</span><span class="sxs-lookup"><span data-stu-id="25753-178">For details, see "Receive-Side Scaling Enhancements in Windows Server 2008" at <A href="http://go.microsoft.com/fwlink/p/?linkid=268731">http://go.microsoft.com/fwlink/p/?linkId=268731</A>.</span></span> <span data-ttu-id="25753-179">Сведения о том, как включить RSS, см. в документации сетевого адаптера.</span><span class="sxs-lookup"><span data-stu-id="25753-179">For details about how to enable RSS, see your network adapter documentation.</span></span>



</div>

</div>

<div>

## <a name="conferencing-maximums"></a><span data-ttu-id="25753-180">Максимумы конференц-связи</span><span class="sxs-lookup"><span data-stu-id="25753-180">Conferencing Maximums</span></span>

<span data-ttu-id="25753-181">Если пользовательская модель, в которой 5% пользователей в пуле, может находиться в одной конференции, пул пользователей 80 000 может иметь около 4 000 пользователей на конференциях одновременно.</span><span class="sxs-lookup"><span data-stu-id="25753-181">Given the user model that 5% of users in a pool may be in a conference at any one time, a pool of 80,000 users could have about 4,000 users in conferences at one time.</span></span> <span data-ttu-id="25753-182">These conferences are expected to be a mix of media (some IM-only, some IM with audio, some audio/video, for example) and number of participants.</span><span class="sxs-lookup"><span data-stu-id="25753-182">These conferences are expected to be a mix of media (some IM-only, some IM with audio, some audio/video, for example) and number of participants.</span></span> <span data-ttu-id="25753-183">Ограничения для фактического количества конференций не ограничены, а фактическое использование определяет фактическую производительность.</span><span class="sxs-lookup"><span data-stu-id="25753-183">There is no hard limit for the actual number of conferences allowed, and actual usage determines the actual performance.</span></span> <span data-ttu-id="25753-184">Например, если ваша организация имеет гораздо больше конференций смешанного режима, чем предполагается для пользовательской модели, возможно, вам потребуется развернуть другие серверы переднего плана или серверы конференций/V, чем рекомендации, описанные в этом документе.</span><span class="sxs-lookup"><span data-stu-id="25753-184">For example, if your organization has many more mixed-mode conferences than are assumed in the user model, you might need to deploy more Front End Servers or A/V Conferencing Servers than the recommendations in this document.</span></span> <span data-ttu-id="25753-185">Подробные сведения о допущениях в пользовательской модели можно найти в разделе [модели пользователей в Lync Server 2013](lync-server-2013-user-models.md).</span><span class="sxs-lookup"><span data-stu-id="25753-185">For details about the assumptions in the user model, see [User models in Lync Server 2013](lync-server-2013-user-models.md).</span></span>

<span data-ttu-id="25753-186">Максимально допустимый размер Конференции, размещенный на обычном пуле внешних интерфейсов Lync Server 2013, в котором также размещены пользователи, — 250 участников.</span><span class="sxs-lookup"><span data-stu-id="25753-186">The maximum supported conference size hosted by a regular Lync Server 2013 Front End pool which also hosts users is 250 participants.</span></span> <span data-ttu-id="25753-187">While a 250-user conference is happening, the pool still supports other conferences as well, such that a total of 5% of pool users are in concurrent conferences.</span><span class="sxs-lookup"><span data-stu-id="25753-187">While a 250-user conference is happening, the pool still supports other conferences as well, such that a total of 5% of pool users are in concurrent conferences.</span></span> <span data-ttu-id="25753-188">Например, в пуле двенадцати серверов переднего плана и пользователей 80 000, а также при Конференции 250-User, Lync Server поддерживает 3 750 других пользователей, участвующих в небольших конференциях.</span><span class="sxs-lookup"><span data-stu-id="25753-188">For example, in a pool of twelve Front End Servers and 80,000 users, while the 250-user conference is happening, Lync Server supports 3,750 other users participating in smaller conferences.</span></span>

<span data-ttu-id="25753-189">Независимо от количества пользователей, подключенного к пулу или стандартному серверному выпуску, Lync Server поддерживает минимум 125 других пользователей, участвующих в небольших конференциях в том же пуле или на сервере, где размещается конференция 250-пользователи.</span><span class="sxs-lookup"><span data-stu-id="25753-189">Regardless of the number of users homed on the Front End pool or Standard Edition server, Lync Server supports a minimum of 125 other users participating in smaller conferences on the same pool or server which is hosting a 250-user conference.</span></span>

<span data-ttu-id="25753-190">Чтобы включить конференции между пользователями 250 и 1000, вы можете настроить отдельный пул переднего плана только для того, чтобы разместить эти конференции.</span><span class="sxs-lookup"><span data-stu-id="25753-190">To enable conferences with between 250 and 1000 users, you can set up a separate Front End pool just to host those conferences.</span></span> <span data-ttu-id="25753-191">Этот пул переднего плана не будет содержать пользователей.</span><span class="sxs-lookup"><span data-stu-id="25753-191">This Front End pool will not host any users.</span></span> <span data-ttu-id="25753-192">Дополнительные сведения можно найти в разделе [Поддержка собраний большого размера с помощью Lync Server 2013](lync-server-2013-supporting-large-meetings.md).</span><span class="sxs-lookup"><span data-stu-id="25753-192">For details, see [Supporting large meetings using Lync Server 2013](lync-server-2013-supporting-large-meetings.md).</span></span>

<span data-ttu-id="25753-193">Если в вашей организации есть больше конференций смешанного режима, чем предполагается для пользовательской модели, вам может потребоваться развернуть другие серверы переднего плана, чем рекомендации в этом документе (до 12 Фес).</span><span class="sxs-lookup"><span data-stu-id="25753-193">If your organization has many more mixed-mode conferences than are assumed in the user model, you might need to deploy more Front End Servers than the recommendations in this document (up to a limit of 12 FEs).</span></span> <span data-ttu-id="25753-194">Подробные сведения о допущениях в пользовательской модели можно найти в разделе [модели пользователей в Lync Server 2013](lync-server-2013-user-models.md).</span><span class="sxs-lookup"><span data-stu-id="25753-194">For details about the assumptions in the user model, see [User models in Lync Server 2013](lync-server-2013-user-models.md).</span></span>

</div>

<div>

## <a name="edge-server"></a><span data-ttu-id="25753-195">Пограничный сервер</span><span class="sxs-lookup"><span data-stu-id="25753-195">Edge Server</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="25753-196">Растянутые пулы для этой роли сервера не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="25753-196">Stretched pools are not supported for this server role.</span></span>



</div>

<span data-ttu-id="25753-197">Вы должны развернуть один пограничный сервер для каждого удаленного пользователя 12 000, который будет одновременно получать доступ к сайту.</span><span class="sxs-lookup"><span data-stu-id="25753-197">You should deploy one Edge Server for every 12,000 remote users who will access a site concurrently.</span></span> <span data-ttu-id="25753-198">Как минимум, мы рекомендуем использовать два пограничных сервера для обеспечения высокой доступности.</span><span class="sxs-lookup"><span data-stu-id="25753-198">At a minimum we recommend two Edge Servers for high availability.</span></span> <span data-ttu-id="25753-199">Эти рекомендации предполагают, что оборудование пограничных серверов соответствует рекомендациям, приведенным в разделе [аппаратные платформы сервера для Lync Server 2013](lync-server-2013-server-hardware-platforms.md).</span><span class="sxs-lookup"><span data-stu-id="25753-199">These recommendations assume that the hardware for your Edge Servers meets the recommendations in [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md).</span></span>

<span data-ttu-id="25753-200">При указании числа пользователей для пограничных серверов включите пользователей, относящихся к бесперебойным устройствам филиалов и к бесперебойным серверам филиалов в филиалах, которые связаны с пулом переднего плана на этом сайте.</span><span class="sxs-lookup"><span data-stu-id="25753-200">When you account for the number of users for the Edge Servers, include the users homed on Survivable Branch Appliances and Survivable Branch Servers at branch offices that are associated with a Front End pool at this site.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="25753-201">Чтобы повысить производительность службы пограничного конференц-связи A/V на пограничных серверах, необходимо включить масштабирование на стороне приема (RSS) на сетевых адаптерах пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="25753-201">To improve the performance of the A/V Conferencing Edge service on your Edge Servers, you should enable receive-side scaling (RSS) on the network adapters on your Edge Servers.</span></span> <span data-ttu-id="25753-202">RSS поддерживает параллельную обработку входящих пакетов несколькими процессорами сервера.</span><span class="sxs-lookup"><span data-stu-id="25753-202">RSS enables incoming packets to be handled in parallel by multiple processors on the server.</span></span> <span data-ttu-id="25753-203">Дополнительные сведения можно найти в разделе улучшенные возможности масштабирования на стороне приема в Windows Server 2008 <A href="http://go.microsoft.com/fwlink/p/?linkid=268731">http://go.microsoft.com/fwlink/p/?linkId=268731</A>.</span><span class="sxs-lookup"><span data-stu-id="25753-203">For details, see "Receive-Side Scaling Enhancements in Windows Server 2008" at <A href="http://go.microsoft.com/fwlink/p/?linkid=268731">http://go.microsoft.com/fwlink/p/?linkId=268731</A>.</span></span> <span data-ttu-id="25753-204">Сведения о том, как включить RSS, см. в документации сетевого адаптера.</span><span class="sxs-lookup"><span data-stu-id="25753-204">For details about how to enable RSS, see your network adapter documentation.</span></span>



</div>

</div>

<div>

## <a name="director"></a><span data-ttu-id="25753-205">Директор</span><span class="sxs-lookup"><span data-stu-id="25753-205">Director</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="25753-206">Растянутые пулы для этой роли сервера не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="25753-206">Stretched pools are not supported for this server role.</span></span>



</div>

<span data-ttu-id="25753-207">При развертывании роли режиссера рекомендуется развернуть один режиссер для каждого удаленного пользователя 12 000, который будет одновременно получать доступ к сайту.</span><span class="sxs-lookup"><span data-stu-id="25753-207">If you deploy the Director server role we recommend that you deploy one Director for every 12,000 remote users who will access a site concurrently.</span></span> <span data-ttu-id="25753-208">Как минимум мы рекомендуем использовать двух директоров для обеспечения высокой доступности.</span><span class="sxs-lookup"><span data-stu-id="25753-208">At a minimum we recommend two Directors for high availability.</span></span> <span data-ttu-id="25753-209">Эти рекомендации предполагают, что оборудование пограничных серверов соответствует рекомендациям, приведенным в разделе [аппаратные платформы сервера для Lync Server 2013](lync-server-2013-server-hardware-platforms.md).</span><span class="sxs-lookup"><span data-stu-id="25753-209">These recommendations assume that the hardware for your Edge Servers meets the recommendations in [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md).</span></span>

<span data-ttu-id="25753-210">При указании количества пользователей для режиссеров Включите пользователей, которые размещаются на устройствах с бесперебойной ветвлением, и бесперебойно работающих серверах филиалов в филиалах, связанных с пулом переднего плана на этом сайте.</span><span class="sxs-lookup"><span data-stu-id="25753-210">When you account for the number of users for the Directors, include the users homed on Survivable Branch Appliances and Survivable Branch Servers at branch offices that are associated with a Front End pool at this site.</span></span>

</div>

<div>

## <a name="mediation-server"></a><span data-ttu-id="25753-211">Сервер-посредник</span><span class="sxs-lookup"><span data-stu-id="25753-211">Mediation Server</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="25753-212">Растянутые пулы для этой роли сервера не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="25753-212">Stretched pools are not supported for this server role.</span></span>



</div>

<span data-ttu-id="25753-213">Если вы разгруппирование сервера обновлений на сервере переднего плана, сервер обработает на каждом сервере переднего плана в пуле и должен предоставить достаточную емкость для пользователей в пуле.</span><span class="sxs-lookup"><span data-stu-id="25753-213">If you collocate Mediation Server with Front End Server, Mediation Server runs on every Front End Server in the pool, and should provide enough capacity for the users in the pool.</span></span>

<span data-ttu-id="25753-214">Если вы разворачиваете пул серверов с изолированными исправлениями, то сколько серверов-посредников нужно развернуть, зависит от многих факторов, в том числе оборудования, используемого для сервера-посредника, количества пользователей VoIP и количества одноранговых узлов, которые используют каждый пул серверов-исправлений. элементы управления, объем занятого трафика через эти шлюзы и процент звонков с носителя, минуя сервер обновлений.</span><span class="sxs-lookup"><span data-stu-id="25753-214">If you deploy a stand-alone Mediation Server pool, then how many Mediation Servers to deploy depends on many factors, including the hardware used for Mediation Server, the number of VoIP users you have, the number of gateway peers that each Mediation Server pool controls, the busy hour traffic through those gateways, and the percentage of calls with media that bypasses the Mediation Server.</span></span>

<span data-ttu-id="25753-215">В приведенных ниже таблицах приведены рекомендации о том, сколько одновременных вызовов может обрабатывать сервер-посредник, предполагая, что оборудование для серверов-исправлений соответствует требованиям в [серверных платформах для Lync server 2013](lync-server-2013-server-hardware-platforms.md) и включена технология Hyper-Threading.</span><span class="sxs-lookup"><span data-stu-id="25753-215">The following tables provide a guideline for how many concurrent calls a Mediation Server can handle, assuming that the hardware for the Mediation Servers meets the requirements in [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md) and that hyper-threading is enabled.</span></span> <span data-ttu-id="25753-216">Подробные сведения об масштабируемости сервера исправлений можно найти в разделе [Оценка использования голоса и трафик для Lync server 2013](lync-server-2013-estimating-voice-usage-and-traffic.md) и [рекомендации по развертыванию сервера исправлений в Lync Server 2013](lync-server-2013-deployment-guidelines-for-mediation-server.md).</span><span class="sxs-lookup"><span data-stu-id="25753-216">For details about Mediation Server scalability, see [Estimating voice usage and traffic for Lync Server 2013](lync-server-2013-estimating-voice-usage-and-traffic.md) and [Deployment guidelines for Mediation Server in Lync Server 2013](lync-server-2013-deployment-guidelines-for-mediation-server.md).</span></span>

<span data-ttu-id="25753-217">Во всех приведенных ниже таблицах предполагается использование, как обобщено в [пользовательских моделях в Lync Server 2013](lync-server-2013-user-models.md).</span><span class="sxs-lookup"><span data-stu-id="25753-217">All the following tables assume usage as summarized in [User models in Lync Server 2013](lync-server-2013-user-models.md).</span></span>

### <a name="stand-alone-mediation-server-capacity-70-internal-users-30-external-users-with-non-bypass-call-capacity-media-transcoding-performed-by-mediation-server"></a><span data-ttu-id="25753-218">Бесплатная емкость сервера исправлений: 70% внутренних пользователей, 30% внешних пользователей с емкостью обоснованных звонков (перекодировка мультимедиа, выполненная сервером исправлений)</span><span class="sxs-lookup"><span data-stu-id="25753-218">Stand-alone Mediation Server Capacity: 70% Internal Users, 30% External users with non-bypass call capacity (media transcoding performed by Mediation Server)</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="25753-219">Серверное оборудование</span><span class="sxs-lookup"><span data-stu-id="25753-219">Server hardware</span></span></th>
<th><span data-ttu-id="25753-220">Максимальное количество звонков</span><span class="sxs-lookup"><span data-stu-id="25753-220">Maximum number of calls</span></span></th>
<th><span data-ttu-id="25753-221">Максимальное количество линий T1</span><span class="sxs-lookup"><span data-stu-id="25753-221">Maximum number of T1 lines</span></span></th>
<th><span data-ttu-id="25753-222">Максимальное количество линий E1</span><span class="sxs-lookup"><span data-stu-id="25753-222">Maximum number of E1 lines</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="25753-223">Два шестиядерных процессора 2,26 ГГц с поддержкой технологии Hyper-Threading (<strong>технология Hyper-Threading отключена</strong>), память 32 ГБ и одна двухпортовая сетевая карта.</span><span class="sxs-lookup"><span data-stu-id="25753-223">Dual processor, hex core, 2.26 GHz hyper-threaded CPU <strong>with hyper-threading disabled</strong>, with 32 GB memory and one dual-port network adapter card.</span></span></p></td>
<td><p><span data-ttu-id="25753-224">1100</span><span class="sxs-lookup"><span data-stu-id="25753-224">1100</span></span></p></td>
<td><p><span data-ttu-id="25753-225">46</span><span class="sxs-lookup"><span data-stu-id="25753-225">46</span></span></p></td>
<td><p><span data-ttu-id="25753-226">35</span><span class="sxs-lookup"><span data-stu-id="25753-226">35</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="25753-227">Два шестиядерных процессора 2,26 ГГц с поддержкой технологии Hyper-Threading, память 32 ГБ и одна двухпортовая сетевая карта.</span><span class="sxs-lookup"><span data-stu-id="25753-227">Dual processor, hex core, 2.26 GHz hyper-threaded CPU, with 32 GB memory and one dual-port network adapter card.</span></span></p></td>
<td><p><span data-ttu-id="25753-228">1500</span><span class="sxs-lookup"><span data-stu-id="25753-228">1500</span></span></p></td>
<td><p><span data-ttu-id="25753-229">63</span><span class="sxs-lookup"><span data-stu-id="25753-229">63</span></span></p></td>
<td><p><span data-ttu-id="25753-230">47</span><span class="sxs-lookup"><span data-stu-id="25753-230">47</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="25753-231">Несмотря на то, что при тестировании производительности использовались серверы размером 32 ГБ, серверы с объемом памяти 16 ГБ поддерживаются для изолированного сервера-посредника и достаточно для обеспечения производительности, представленной в этой таблице.</span><span class="sxs-lookup"><span data-stu-id="25753-231">Although servers with 32 GB of memory were used for performance testing, servers with 16 GB of memory are supported for stand-alone Mediation Server, and are sufficient to provide the performance shown in this table.</span></span>



</div>

### <a name="mediation-server-capacity-mediation-server-collocated-with-front-end-server-70-internal-users-30-external-users-non-bypass-call-capacity-media-processing-performed-by-mediation-server"></a><span data-ttu-id="25753-232">Емкость сервера ресурсов (сервер-посредник, выровненный по внешнему серверу) 70% внутренних пользователей, 30% внешних пользователей, не пропуская емкость звонка (обработка носителей, выполненная сервером-исправлением)</span><span class="sxs-lookup"><span data-stu-id="25753-232">Mediation Server Capacity (Mediation Server Collocated with Front End Server) 70% Internal Users, 30% External Users, Non-Bypass Call Capacity (Media Processing Performed by Mediation Server)</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="25753-233">Серверное оборудование</span><span class="sxs-lookup"><span data-stu-id="25753-233">Server hardware</span></span></th>
<th><span data-ttu-id="25753-234">Максимальное количество звонков</span><span class="sxs-lookup"><span data-stu-id="25753-234">Maximum number of calls</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="25753-235">Два шестиядерных процессора 2,26 ГГц с поддержкой технологии Hyper-Threading, память 32 ГБ и две сетевых карты со скоростью 1 Гбит/с.</span><span class="sxs-lookup"><span data-stu-id="25753-235">Dual processor, hex core, 2.26 GHz hyper-threaded CPU, with 32 GB memory and 2 1GB network adapter cards.</span></span></p></td>
<td><p><span data-ttu-id="25753-236">150</span><span class="sxs-lookup"><span data-stu-id="25753-236">150</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="25753-237">Это число значительно меньше числа на сервере автономных обновлений, так как сервер переднего плана должен обрабатывать другие функции и функции для пользователей 6600, которые потребуются для голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="25753-237">This number is much smaller than the numbers for the stand-alone Mediation Server because the Front End Server has to handle other features and functions for the 6600 users homed on it, in addition to the transcoding needed for voice calls.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="25753-238">Чтобы повысить производительность сервера-посредника, необходимо включить масштабирование на стороне приема (RSS) на сетевых адаптерах серверов-исправлений.</span><span class="sxs-lookup"><span data-stu-id="25753-238">To improve the performance of the Mediation Server, you should enable receive-side scaling (RSS) on the network adapters on your Mediation Servers.</span></span> <span data-ttu-id="25753-239">RSS поддерживает параллельную обработку входящих пакетов несколькими процессорами сервера.</span><span class="sxs-lookup"><span data-stu-id="25753-239">RSS enables incoming packets to be handled in parallel by multiple processors on the server.</span></span> <span data-ttu-id="25753-240">Дополнительные сведения можно найти в разделе улучшенные возможности масштабирования на стороне приема в Windows Server 2008 <A href="http://go.microsoft.com/fwlink/p/?linkid=268731">http://go.microsoft.com/fwlink/p/?linkId=268731</A>.</span><span class="sxs-lookup"><span data-stu-id="25753-240">For details, see "Receive-Side Scaling Enhancements in Windows Server 2008" at <A href="http://go.microsoft.com/fwlink/p/?linkid=268731">http://go.microsoft.com/fwlink/p/?linkId=268731</A>.</span></span> <span data-ttu-id="25753-241">Сведения о том, как включить RSS, см. в документации сетевого адаптера.</span><span class="sxs-lookup"><span data-stu-id="25753-241">For details about how to enable RSS, see your network adapter documentation.</span></span>



</div>

</div>

<div>

## <a name="back-end-server"></a><span data-ttu-id="25753-242">внутренний сервер</span><span class="sxs-lookup"><span data-stu-id="25753-242">Back End Server</span></span>

<span data-ttu-id="25753-243">В Lync Server 2013 базы данных присутствия находятся на серверах переднего плана, а не на обратном сервере.</span><span class="sxs-lookup"><span data-stu-id="25753-243">In Lync Server 2013, the presence databases are located on the Front End Servers instead of the Back End Server.</span></span> <span data-ttu-id="25753-244">Это является более простым требованием для каждого серверного сервера в Lync Server 2013 и соответствует требованиям к оборудованию для серверного переднего плана.</span><span class="sxs-lookup"><span data-stu-id="25753-244">This has resulted in a much simpler requirement for each Back End Server in Lync Server 2013, equivalent to the hardware requirement for the Front End Server.</span></span> <span data-ttu-id="25753-245">Сравните это с Lync Server 2010, где сервер должен быть на более высоком уровне сервера с 25 дисками.</span><span class="sxs-lookup"><span data-stu-id="25753-245">Contrast this to Lync Server 2010, where the Back End Server was required to be a much higher grade server with 25 disks.</span></span> <span data-ttu-id="25753-246">Тем не менее, если вы не хотите отвечать требованиям к оборудованию, описанным выше в этом разделе, и в [серверных аппаратных платформах для Lync Server 2013](lync-server-2013-server-hardware-platforms.md), вы все равно должны быть в процессе работы серверов.</span><span class="sxs-lookup"><span data-stu-id="25753-246">However, the workload of Back End Servers is still such that you should not fail to meet the hardware recommendations listed earlier in this section and in [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md).</span></span>

<span data-ttu-id="25753-247">Для обеспечения высокого уровня доступности серверного сервера рекомендуется развертывание зеркального отображения сервера.</span><span class="sxs-lookup"><span data-stu-id="25753-247">To provide high availability of your Back End Server, we recommend deploying server mirroring.</span></span> <span data-ttu-id="25753-248">Дополнительные сведения можно найти в разделе о [высокой доступности сервера в Lync server 2013](lync-server-2013-back-end-server-high-availability.md).</span><span class="sxs-lookup"><span data-stu-id="25753-248">For more information, see [Back End Server high availability in Lync Server 2013](lync-server-2013-back-end-server-high-availability.md).</span></span>

</div>

<div>

## <a name="monitoring-and-archiving"></a><span data-ttu-id="25753-249">Мониторинг и архивирование</span><span class="sxs-lookup"><span data-stu-id="25753-249">Monitoring and Archiving</span></span>

<span data-ttu-id="25753-250">В Lync Server 2013 при развертывании мониторинга или архивации интерфейсные функции этих служб выполняются на серверах переднего плана, а не на отдельных ролях сервера.</span><span class="sxs-lookup"><span data-stu-id="25753-250">In Lync Server 2013, if you deploy Monitoring or Archiving, the front end functionality of these services runs on the Front End Servers, instead of on separate server roles.</span></span> <span data-ttu-id="25753-251">Для наблюдения и архивации по-прежнему используется собственное хранилище базы данных, отделенное от хранилища сзади.</span><span class="sxs-lookup"><span data-stu-id="25753-251">Monitoring and Archiving each still use their own database store, separate from the Back End store.</span></span> <span data-ttu-id="25753-252">Кроме того, если вы развернули Exchange 2013, вы можете хранить данные для архивации мгновенных сообщений в Exchange, а не в специальном хранилище SQL.</span><span class="sxs-lookup"><span data-stu-id="25753-252">Alternatively, if you have Exchange 2013 deployed, you can store instant message Archiving data in Exchange instead of in a dedicated SQL store.</span></span>

<span data-ttu-id="25753-253">В следующей таблице показаны приблизительные значения размера хранилища базы данных на пользователя в день, необходимые для данных мониторинга и архивирования.</span><span class="sxs-lookup"><span data-stu-id="25753-253">The following table indicates approximately how much database storage is required per user per day for Monitoring and Archiving data.</span></span>


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
<td><p><span data-ttu-id="25753-254"><strong>CDR (мониторинг)</strong></span><span class="sxs-lookup"><span data-stu-id="25753-254"><strong>CDR (Monitoring)</strong></span></span></p></td>
<td><p><span data-ttu-id="25753-255"><strong>QoE (мониторинг)</strong></span><span class="sxs-lookup"><span data-stu-id="25753-255"><strong>QoE (Monitoring)</strong></span></span></p></td>
<td><p><span data-ttu-id="25753-256"><strong>Архивирование</strong></span><span class="sxs-lookup"><span data-stu-id="25753-256"><strong>Archiving</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="25753-257">Дисковое пространство на пользователя в день</span><span class="sxs-lookup"><span data-stu-id="25753-257">Disk space required per user per day</span></span></p></td>
<td><p><span data-ttu-id="25753-258">49 КБ</span><span class="sxs-lookup"><span data-stu-id="25753-258">49 KB</span></span></p></td>
<td><p><span data-ttu-id="25753-259">28 КБ</span><span class="sxs-lookup"><span data-stu-id="25753-259">28 KB</span></span></p></td>
<td><p><span data-ttu-id="25753-260">57 КБ</span><span class="sxs-lookup"><span data-stu-id="25753-260">57 KB</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="25753-261">Microsoft used the hardware in the following table for the database server for Monitoring and Archiving during its performance testing.</span><span class="sxs-lookup"><span data-stu-id="25753-261">Microsoft used the hardware in the following table for the database server for Monitoring and Archiving during its performance testing.</span></span> <span data-ttu-id="25753-262">Тестирование собрало данные двух пулов интерфейсов, каждый из которых содержал 80 000 пользователей.</span><span class="sxs-lookup"><span data-stu-id="25753-262">The testing collected the data of two Front End pools, each of which contained 80,000 users.</span></span>

### <a name="hardware-used-in-monitoring-and-archiving-performance-testing"></a><span data-ttu-id="25753-263">Оборудование, использованное при тестировании производительности мониторинга и архивирования</span><span class="sxs-lookup"><span data-stu-id="25753-263">Hardware Used in Monitoring and Archiving Performance Testing</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="25753-264">Аппаратный компонент</span><span class="sxs-lookup"><span data-stu-id="25753-264">Hardware component</span></span></th>
<th><span data-ttu-id="25753-265">Рекомендуется</span><span class="sxs-lookup"><span data-stu-id="25753-265">Recommended</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="25753-266">ЦП</span><span class="sxs-lookup"><span data-stu-id="25753-266">CPU</span></span></p></td>
<td><p><span data-ttu-id="25753-267">64-разрядный двухпроцессорный комплекс, шестиядерный, 26 ГГц и выше</span><span class="sxs-lookup"><span data-stu-id="25753-267">64-bit dual processor, hex-core, 2.26 gigahertz (GHz) or higher</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="25753-268">Память</span><span class="sxs-lookup"><span data-stu-id="25753-268">Memory</span></span></p></td>
<td><p><span data-ttu-id="25753-269">48 ГБ</span><span class="sxs-lookup"><span data-stu-id="25753-269">48 gigabytes (GB)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="25753-270">Диск</span><span class="sxs-lookup"><span data-stu-id="25753-270">Disk</span></span></p></td>
<td><p><span data-ttu-id="25753-271">25 дисков со скоростью вращения 10 000 об/мин по 300 ГБ со следующей конфигурацией</span><span class="sxs-lookup"><span data-stu-id="25753-271">25 10,000-RPM hard disk drives with 300 GB on each disk, with the following configuration</span></span></p>
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
<td><p><span data-ttu-id="25753-272"><strong>Диск</strong></span><span class="sxs-lookup"><span data-stu-id="25753-272"><strong>Drive</strong></span></span></p></td>
<td><p><span data-ttu-id="25753-273"><strong>Конфигурация RAID</strong></span><span class="sxs-lookup"><span data-stu-id="25753-273"><strong>RAID Configuration</strong></span></span></p></td>
<td><p><span data-ttu-id="25753-274"><strong>Количество дисков</strong></span><span class="sxs-lookup"><span data-stu-id="25753-274"><strong>Number of disks</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="25753-275">Файлы баз данных CDR, QoE и архивирования, на одном диске</span><span class="sxs-lookup"><span data-stu-id="25753-275">CDR, QoE, and Archiving database data files, on a single drive</span></span></p></td>
<td><p><span data-ttu-id="25753-276">1+0</span><span class="sxs-lookup"><span data-stu-id="25753-276">1+0</span></span></p></td>
<td><p><span data-ttu-id="25753-277">шестнадцат</span><span class="sxs-lookup"><span data-stu-id="25753-277">16</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="25753-278">Файл журнала базы данных CDR</span><span class="sxs-lookup"><span data-stu-id="25753-278">CDR database log file</span></span></p></td>
<td><p><span data-ttu-id="25753-279">1</span><span class="sxs-lookup"><span data-stu-id="25753-279">1</span></span></p></td>
<td><p><span data-ttu-id="25753-280">2</span><span class="sxs-lookup"><span data-stu-id="25753-280">2</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="25753-281">Файл журнала базы данных QoE</span><span class="sxs-lookup"><span data-stu-id="25753-281">QoE database log file</span></span></p></td>
<td><p><span data-ttu-id="25753-282">1</span><span class="sxs-lookup"><span data-stu-id="25753-282">1</span></span></p></td>
<td><p><span data-ttu-id="25753-283">2</span><span class="sxs-lookup"><span data-stu-id="25753-283">2</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="25753-284">Файл журнала базы данных архивирования</span><span class="sxs-lookup"><span data-stu-id="25753-284">Archiving database log file</span></span></p></td>
<td><p><span data-ttu-id="25753-285">1</span><span class="sxs-lookup"><span data-stu-id="25753-285">1</span></span></p></td>
<td><p><span data-ttu-id="25753-286">2</span><span class="sxs-lookup"><span data-stu-id="25753-286">2</span></span></p></td>
</tr>
</tbody>
</table>

</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="25753-287">Сеть</span><span class="sxs-lookup"><span data-stu-id="25753-287">Network</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="25753-288">1 двухпортовый сетевой адаптер, 1 Гбит/с или выше (рекомендуется 2 Гбит/с, для этого требуется объединение через один MAC-адрес и один IP-адрес)</span><span class="sxs-lookup"><span data-stu-id="25753-288">1 dual-port network adapter, 1 Gbps or higher (2 recommended, which requires teaming with a single MAC address and single IP address)</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="25753-289">Содержание</span><span class="sxs-lookup"><span data-stu-id="25753-289">In This Section</span></span>

  - [<span data-ttu-id="25753-290">Оценка объема использования и трафика голосовой связи для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="25753-290">Estimating voice usage and traffic for Lync Server 2013</span></span>](lync-server-2013-estimating-voice-usage-and-traffic.md)

  - [<span data-ttu-id="25753-291">Рекомендации по развертыванию сервера обновлений в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="25753-291">Deployment guidelines for Mediation Server in Lync Server 2013</span></span>](lync-server-2013-deployment-guidelines-for-mediation-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

