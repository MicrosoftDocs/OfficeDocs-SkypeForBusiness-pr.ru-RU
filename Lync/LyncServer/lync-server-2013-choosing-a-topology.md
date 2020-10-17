---
title: 'Lync Server 2013: выбор топологии'
description: 'Lync Server 2013: выбор топологии.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Choosing a topology
ms:assetid: 23f2aeb6-fed9-4349-8fba-dcbf18ee4b04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425716(v=OCS.15)
ms:contentKeyID: 48183634
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 01ded739c3c5e4e0bd8c0f25f3f0fe8ff1f350b9
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48549685"
---
# <a name="choosing-a-topology-in-lync-server-2013"></a><span data-ttu-id="034f6-103">Выбор топологии в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="034f6-103">Choosing a topology in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span data-ttu-id="034f6-104">_**Последнее изменение темы:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="034f6-104">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="034f6-105">При выборе топологии вы можете использовать один из следующих поддерживаемых вариантов топологии:</span><span class="sxs-lookup"><span data-stu-id="034f6-105">When you choose a topology, you can use one the following supported topology options:</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="034f6-106">Если не указано иное, если у вас есть опыт работы с Microsoft Lync Server 2010, здесь вы найдете рекомендации практически без изменений.</span><span class="sxs-lookup"><span data-stu-id="034f6-106">Unless otherwise noted, if you have experience with Microsoft Lync Server 2010, you will find the guidance here is largely unchanged.</span></span>



</div>

  - [<span data-ttu-id="034f6-107">Единый консолидированный край с частными IP-адресами и NAT в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="034f6-107">Single consolidated edge with private IP addresses and NAT in Lync Server 2013</span></span>](lync-server-2013-single-consolidated-edge-with-private-ip-addresses-and-nat.md)

  - [<span data-ttu-id="034f6-108">Единый консолидированный край с общедоступными IP-адресами в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="034f6-108">Single consolidated edge with public IP addresses in Lync Server 2013</span></span>](lync-server-2013-single-consolidated-edge-with-public-ip-addresses.md)

  - [<span data-ttu-id="034f6-109">Масштабируемый консолидированный край, балансировка нагрузки на DNS с частными IP-адресами, использующими NAT, в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="034f6-109">Scaled consolidated edge, DNS load balancing with private IP addresses using NAT in Lync Server 2013</span></span>](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md)

  - [<span data-ttu-id="034f6-110">Масштабируемый консолидированный край, балансировка нагрузки на DNS с общедоступными IP-адресами в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="034f6-110">Scaled consolidated edge, DNS load balancing with public IP addresses in Lync Server 2013</span></span>](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md)

  - [<span data-ttu-id="034f6-111">Масштабируемая консолидированная пограничная система с аппаратными подсистемами балансировки нагрузки в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="034f6-111">Scaled consolidated edge with hardware load balancers in Lync Server 2013</span></span>](lync-server-2013-scaled-consolidated-edge-with-hardware-load-balancers.md)

<div>


> [!IMPORTANT]
> <span data-ttu-id="034f6-p101">Внутренний пограничный интерфейс и внешний пограничный интерфейс должны использовать один тип балансировки нагрузки. Нельзя использовать балансировку нагрузки на DNS в одном пограничном интерфейсе и аппаратную балансировку нагрузки в другом пограничном интерфейсе.</span><span class="sxs-lookup"><span data-stu-id="034f6-p101">The internal Edge interface and external Edge interface must use the same type of load balancing. You cannot use DNS load balancing on one Edge interface and hardware load balancing on the other Edge interface.</span></span>



</div>

<span data-ttu-id="034f6-114">В следующей таблице перечислены функции, доступные в поддерживаемых топологиях Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="034f6-114">The following table summarizes the functionality available with the supported Microsoft Lync Server 2013 topologies.</span></span> <span data-ttu-id="034f6-115">В заголовках столбцов указываются возможности, доступные в данном варианте конфигурации пограничных серверов.</span><span class="sxs-lookup"><span data-stu-id="034f6-115">The column headings indicate the functionality available for a given Edge configuration option.</span></span> <span data-ttu-id="034f6-116">Например, в случае с масштабированной средой пограничных серверов (балансировка нагрузки на DNS) поддерживается высокая доступность, могут использоваться частные IP-адреса без поддержки маршрутизации (с преобразованием сетевых адресов (NAT)) или общедоступные IP-адреса с поддержкой маршрутизации, назначенные внешним пограничным интерфейсам, и обеспечивается экономия за счет отсутствия потребности в аппаратном балансировщике нагрузки.</span><span class="sxs-lookup"><span data-stu-id="034f6-116">Using the Scaled Edge (DNS load balanced) option as an example, you can see that it supports high availability, can use non-routable private IP addresses (with NAT) or routable public IP addresses assigned to the Edge external interfaces, and reduces cost because a hardware load balancer is not required.</span></span>

<span data-ttu-id="034f6-117">Сценарии пограничного отработки отказа, поддерживаемые с помощью балансировки нагрузки на DNS, являются сеансами связи "Lync-to-Lync", сеансами конференц-связи Lync, сеансами Lync-PSTN, Office 365 и Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="034f6-117">Edge failover scenarios supported with DNS Load Balancing are Lync-to-Lync point-to-point sessions, Lync conferencing sessions, Lync-to-PSTN sessions, Office 365, and Microsoft 365.</span></span> <span data-ttu-id="034f6-118">Сценарии отработки отказа при отработке отказа, не являющиеся преимуществами балансировки нагрузки на DNS, отправляются отработку отказа для удаленных пользователей единой системы обмена сообщениями Exchange (до Exchange 2010 SP1), подключения к общедоступным обмену сообщениями и Федерации с серверами Office Communications Server.</span><span class="sxs-lookup"><span data-stu-id="034f6-118">Edge failover scenarios that do not benefit from DNS Load Balancing are failover for remote user Exchange Unified Messaging (UM) (prior to Exchange 2010 SP1), public instant messaging (IM) connectivity, and federation with servers running Office Communications Server.</span></span>

### <a name="summary-of-edge-server-topology-options"></a><span data-ttu-id="034f6-119">Сводная таблица вариантов топологии пограничных серверов</span><span class="sxs-lookup"><span data-stu-id="034f6-119">Summary of Edge Server Topology Options</span></span>

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="034f6-120">Топология</span><span class="sxs-lookup"><span data-stu-id="034f6-120">Topology</span></span></th>
<th><span data-ttu-id="034f6-121">Высокая доступность</span><span class="sxs-lookup"><span data-stu-id="034f6-121">High availability</span></span></th>
<th><span data-ttu-id="034f6-122">Для внешних пограничных серверов в пограничном пуле требуются дополнительные записи A DNS</span><span class="sxs-lookup"><span data-stu-id="034f6-122">Additional DNS A records required for external Edge Server in the Edge pool</span></span></th>
<th><span data-ttu-id="034f6-123">Пограничный отработка отказа для сеансов Lync – Lync</span><span class="sxs-lookup"><span data-stu-id="034f6-123">Edge Failover for Lync-to-Lync sessions</span></span></th>
<th><span data-ttu-id="034f6-124">Пограничный отработка отказа для сеансов Федерации Lync-to-Lync EUM/PIC/OCS</span><span class="sxs-lookup"><span data-stu-id="034f6-124">Edge Failover for Lync-to-Lync EUM/PIC/OCS Federation sessions</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="034f6-125">Отдельный пограничный сервер, использующий NAT</span><span class="sxs-lookup"><span data-stu-id="034f6-125">Single Edge using NAT</span></span></p></td>
<td><p><span data-ttu-id="034f6-126">Нет</span><span class="sxs-lookup"><span data-stu-id="034f6-126">No</span></span></p></td>
<td><p><span data-ttu-id="034f6-127">Нет</span><span class="sxs-lookup"><span data-stu-id="034f6-127">No</span></span></p></td>
<td><p><span data-ttu-id="034f6-128">Нет</span><span class="sxs-lookup"><span data-stu-id="034f6-128">No</span></span></p></td>
<td><p><span data-ttu-id="034f6-129">Нет</span><span class="sxs-lookup"><span data-stu-id="034f6-129">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="034f6-130">Отдельный пограничный сервер, использующий общедоступный IP-адрес</span><span class="sxs-lookup"><span data-stu-id="034f6-130">Single Edge using Public IP</span></span></p></td>
<td><p><span data-ttu-id="034f6-131">Нет</span><span class="sxs-lookup"><span data-stu-id="034f6-131">No</span></span></p></td>
<td><p><span data-ttu-id="034f6-132">Нет</span><span class="sxs-lookup"><span data-stu-id="034f6-132">No</span></span></p></td>
<td><p><span data-ttu-id="034f6-133">Нет</span><span class="sxs-lookup"><span data-stu-id="034f6-133">No</span></span></p></td>
<td><p><span data-ttu-id="034f6-134">Нет</span><span class="sxs-lookup"><span data-stu-id="034f6-134">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="034f6-135">Масштабированная среда пограничных серверов (балансировка нагрузки на DNS), использующая NAT</span><span class="sxs-lookup"><span data-stu-id="034f6-135">Scaled Edge (DNS Load Balanced) using NAT</span></span></p></td>
<td><p><span data-ttu-id="034f6-136">Да</span><span class="sxs-lookup"><span data-stu-id="034f6-136">Yes</span></span></p></td>
<td><p><span data-ttu-id="034f6-137">Да</span><span class="sxs-lookup"><span data-stu-id="034f6-137">Yes</span></span></p></td>
<td><p><span data-ttu-id="034f6-138">Да</span><span class="sxs-lookup"><span data-stu-id="034f6-138">Yes</span></span></p></td>
<td><p>*</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="034f6-139">Масштабированная среда пограничных серверов (балансировка нагрузки на DNS), использующая общедоступный IP-адрес</span><span class="sxs-lookup"><span data-stu-id="034f6-139">Scaled Edge (DNS Load Balanced) using Public IP</span></span></p></td>
<td><p><span data-ttu-id="034f6-140">Да</span><span class="sxs-lookup"><span data-stu-id="034f6-140">Yes</span></span></p></td>
<td><p><span data-ttu-id="034f6-141">Да</span><span class="sxs-lookup"><span data-stu-id="034f6-141">Yes</span></span></p></td>
<td><p><span data-ttu-id="034f6-142">Да</span><span class="sxs-lookup"><span data-stu-id="034f6-142">Yes</span></span></p></td>
<td><p>*</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="034f6-143">Масштабированная среда пограничных серверов (аппаратная балансировка нагрузки)</span><span class="sxs-lookup"><span data-stu-id="034f6-143">Scaled Edge Hardware load balanced)</span></span></p></td>
<td><p><span data-ttu-id="034f6-144">Да</span><span class="sxs-lookup"><span data-stu-id="034f6-144">Yes</span></span></p></td>
<td><p><span data-ttu-id="034f6-145">Нет (одна запись A DNS на каждый виртуальный IP-адрес)</span><span class="sxs-lookup"><span data-stu-id="034f6-145">No (one DNS A record per VIP)</span></span></p></td>
<td><p><span data-ttu-id="034f6-146">Да</span><span class="sxs-lookup"><span data-stu-id="034f6-146">Yes</span></span></p></td>
<td><p><span data-ttu-id="034f6-147">Да</span><span class="sxs-lookup"><span data-stu-id="034f6-147">Yes</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="034f6-148">**\*** Отработка отказа для подключения к общедоступным службам обмена мгновенными сообщениями и Федерация с серверами Office Communications Server недоступны при балансировке нагрузки на DNS.</span><span class="sxs-lookup"><span data-stu-id="034f6-148">**\*** Failover for public instant messaging (IM) connectivity, and federation with servers running Office Communications Server is not available with DNS load balancing.</span></span> <span data-ttu-id="034f6-149">Для отработки отказа единой системы обмена сообщениями Exchange (удаленный пользователь) при использовании балансировки нагрузки на DNS требуется Exchange Server 2010 SP1 или более</span><span class="sxs-lookup"><span data-stu-id="034f6-149">Exchange UM (remote user) failover using DNS load balancing requires Exchange Server 2010 SP1 or newer.</span></span>



> [!NOTE]
> <span data-ttu-id="034f6-150">В топологиях с одним пограничным сервером и масштабированной средой пограничных серверов (балансировка нагрузки на DNS) могут использоваться:</span><span class="sxs-lookup"><span data-stu-id="034f6-150">Single Edge and Scaled Edge (DNS load balanced) topologies can use:</span></span>
> <ul><li><p><span data-ttu-id="034f6-151">общедоступные IP-адреса с поддержкой маршрутизации;</span><span class="sxs-lookup"><span data-stu-id="034f6-151">Routable public IP addresses</span></span></p></li>
> <li><p><span data-ttu-id="034f6-152">Частный IP-адрес без маршрутизации при использовании симметричного преобразования сетевых адресов (NAT)</span><span class="sxs-lookup"><span data-stu-id="034f6-152">Non-routable private IP address if symmetric network address translation (NAT) is used</span></span></p></li>
>
> <ul><li> <span data-ttu-id="034f6-153">Если вы используете общедоступный IP-адрес или частный IP-адрес с NAT, вы по-прежнему будете использовать одинаковое число IP-адресов в зависимости от выбранного варианта конфигурации в построителе топологий.</span><span class="sxs-lookup"><span data-stu-id="034f6-153">If you use public IP address or private IP address with NAT, you will still use the same number of IP addresses based on your configuration choice in Topology Builder.</span></span> <span data-ttu-id="034f6-154">Можно настроить пограничный сервер на использование одного IP-адреса с отдельными портами для каждой службы или использовать разные IP-адреса для каждой службы, но использовать один и тот же порт (по умолчанию — TCP 443).</span><span class="sxs-lookup"><span data-stu-id="034f6-154">You can configure the Edge Server to use a single IP address with distinct ports per service, or use distinct IP addresses per service, but use the same port (by default, TCP 443).</span></span></li></ul>>
> <span data-ttu-id="034f6-155">Если вы решили использовать частные IP-адреса без поддержки маршрутизации для NAT:</span><span class="sxs-lookup"><span data-stu-id="034f6-155">If you decide to use non-routable private IP addresses with NAT:</span></span>
> <ul><li><p><span data-ttu-id="034f6-156">Вы должны использовать частные IP-адреса с маршрутизацией на всех трех внешних интерфейсах</span><span class="sxs-lookup"><span data-stu-id="034f6-156">You must use routable private IP addresses on all three external interfaces</span></span></p></li>
> <li><p><span data-ttu-id="034f6-157">необходимо настроить симметричное преобразование сетевых адресов (NAT) для входящего и исходящего трафика.</span><span class="sxs-lookup"><span data-stu-id="034f6-157">You must configure symmetric NAT for incoming and outgoing traffic</span></span></p></li></ul>>
> <span data-ttu-id="034f6-158">В топологии с масштабированной средой пограничных серверов (аппаратная балансировка нагрузки) необходимо использовать общедоступные IP-адреса.</span><span class="sxs-lookup"><span data-stu-id="034f6-158">Scaled Edge (hardware load balanced) topology must use public IP addresses.</span></span>



<span data-ttu-id="034f6-159">Lync Server 2013 поддерживает размещение внешних интерфейсов доступа, веб-конференций и аудио-и пограничных интерфейсов на маршрутизаторе или брандмауэре, который выполняет преобразование сетевых адресов (NAT) как для одной, так и для масштабируемых топологий пограничных серверов.</span><span class="sxs-lookup"><span data-stu-id="034f6-159">Lync Server 2013 supports placing Access, Web Conferencing, and A/V Edge external interfaces behind a router or firewall that performs network address translation (NAT) for both single and scaled consolidated Edge Server topologies.</span></span>

<span data-ttu-id="034f6-p106">Для использования преобразования сетевых адресов (NAT) для всех пограничных внешних интерфейсов требуется балансировка нагрузки DNS. По сравнению с аппаратными балансировщиками нагрузки балансировка нагрузки DNS без NAT позволяет сократить число общедоступных IP-адресов на пограничный сервер в пограничном пуле, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="034f6-p106">Using NAT for all Edge external interfaces requires the use of DNS load balancing. When compared to using hardware load balancers, using DNS load balancing without NAT allows you to reduce the number of public IP address per Edge Server in an Edge pool as described in the following list:</span></span>

  - <span data-ttu-id="034f6-162">Для масштабируемого консолидированного пограничного сервера Lync Server 2013 (Балансировка нагрузки DNS) требуются три общедоступных IP-адреса для каждого пограничного сервера в пограничном пуле.</span><span class="sxs-lookup"><span data-stu-id="034f6-162">Lync Server 2013 Scaled Consolidated Edge (DNS load balanced) Requires three public IP addresses for each Edge Server in an Edge pool.</span></span>

  - <span data-ttu-id="034f6-163">Для масштабируемого консолидированного пограничного сервера Lync Server 2013 (аппаратная балансировка нагрузки) требуется три общедоступных IP-адреса для виртуальных IP-адресов подсистемы балансировки нагрузки (одно требование, не увеличивающееся при добавлении пограничных серверов в пул) плюс три общедоступных IP-адреса на пограничный сервер в пуле.</span><span class="sxs-lookup"><span data-stu-id="034f6-163">Lync Server 2013 Scaled Consolidated Edge (hardware load balanced) Requires three public IP address for load balancer virtual IP addresses (one time requirement that does not increment as more Edge Servers are added to the pool) plus three public IP addresses per Edge Server in a pool.</span></span>

### <a name="ip-address-requirements-for-scaled-consolidated-edge-ip-address-per-role"></a><span data-ttu-id="034f6-164">Требования к IP-адресам для масштабированной консолидированной среды пограничных серверов (отдельный IP-адрес для каждой роли)</span><span class="sxs-lookup"><span data-stu-id="034f6-164">IP Address Requirements for Scaled Consolidated Edge (IP Address per role)</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="034f6-165">Число пограничных серверов в пуле</span><span class="sxs-lookup"><span data-stu-id="034f6-165">Number of Edge Servers per pool</span></span></th>
<th><span data-ttu-id="034f6-166">Количество обязательных IP-адресов Lync Server 2013 (Балансировка нагрузки на DNS)</span><span class="sxs-lookup"><span data-stu-id="034f6-166">Number of required IP addresses Lync Server 2013 (DNS load balanced)</span></span></th>
<th><span data-ttu-id="034f6-167">Количество обязательных IP-адресов Lync Server 2013 (аппаратная балансировка нагрузки)</span><span class="sxs-lookup"><span data-stu-id="034f6-167">Number of required IP addresses Lync Server 2013 (hardware load balanced)</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="034f6-168">2</span><span class="sxs-lookup"><span data-stu-id="034f6-168">2</span></span></p></td>
<td><p><span data-ttu-id="034f6-169">6 </span><span class="sxs-lookup"><span data-stu-id="034f6-169">6</span></span></p></td>
<td><p><span data-ttu-id="034f6-170">3 (по 1 на виртуальный IP-адрес) + 6</span><span class="sxs-lookup"><span data-stu-id="034f6-170">3 (1 per VIP) + 6</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="034f6-171">4</span><span class="sxs-lookup"><span data-stu-id="034f6-171">3</span></span></p></td>
<td><p><span data-ttu-id="034f6-172">9 </span><span class="sxs-lookup"><span data-stu-id="034f6-172">9</span></span></p></td>
<td><p><span data-ttu-id="034f6-173">3 (по 1 на виртуальный IP-адрес) + 9</span><span class="sxs-lookup"><span data-stu-id="034f6-173">3 (1 per VIP) + 9</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="034f6-174">4 </span><span class="sxs-lookup"><span data-stu-id="034f6-174">4</span></span></p></td>
<td><p><span data-ttu-id="034f6-175">12 </span><span class="sxs-lookup"><span data-stu-id="034f6-175">12</span></span></p></td>
<td><p><span data-ttu-id="034f6-176">3 (по 1 на виртуальный IP-адрес) + 12</span><span class="sxs-lookup"><span data-stu-id="034f6-176">3 (1 per VIP) + 12</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="034f6-177">5 </span><span class="sxs-lookup"><span data-stu-id="034f6-177">5</span></span></p></td>
<td><p><span data-ttu-id="034f6-178">15 </span><span class="sxs-lookup"><span data-stu-id="034f6-178">15</span></span></p></td>
<td><p><span data-ttu-id="034f6-179">3 (по 1 на виртуальный IP-адрес) + 15</span><span class="sxs-lookup"><span data-stu-id="034f6-179">3 (1 per VIP) + 15</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="ip-address-requirements-for-scaled-consolidated-edge-single-ip-address-for-all-roles"></a><span data-ttu-id="034f6-180">Требования к IP-адресам для масштабированной консолидированной среды пограничных серверов (один IP-адрес для всех ролей)</span><span class="sxs-lookup"><span data-stu-id="034f6-180">IP Address Requirements for Scaled Consolidated Edge (Single IP address for all roles)</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="034f6-181">Число пограничных серверов в пуле</span><span class="sxs-lookup"><span data-stu-id="034f6-181">Number of Edge Servers per pool</span></span></th>
<th><span data-ttu-id="034f6-182">Количество обязательных IP-адресов Lync Server 2013 (Балансировка нагрузки на DNS)</span><span class="sxs-lookup"><span data-stu-id="034f6-182">Number of required IP addresses Lync Server 2013 (DNS load balanced)</span></span></th>
<th><span data-ttu-id="034f6-183">Количество обязательных IP-адресов Lync Server 2013 (аппаратная балансировка нагрузки)</span><span class="sxs-lookup"><span data-stu-id="034f6-183">Number of required IP addresses Lync Server 2013 (hardware load balanced)</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="034f6-184">2</span><span class="sxs-lookup"><span data-stu-id="034f6-184">2</span></span></p></td>
<td><p><span data-ttu-id="034f6-185">2</span><span class="sxs-lookup"><span data-stu-id="034f6-185">2</span></span></p></td>
<td><p><span data-ttu-id="034f6-186">1 (по 1 на виртуальный IP-адрес) + 2</span><span class="sxs-lookup"><span data-stu-id="034f6-186">1 (1 per VIP) + 2</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="034f6-187">4</span><span class="sxs-lookup"><span data-stu-id="034f6-187">3</span></span></p></td>
<td><p><span data-ttu-id="034f6-188">4</span><span class="sxs-lookup"><span data-stu-id="034f6-188">3</span></span></p></td>
<td><p><span data-ttu-id="034f6-189">1 (по 1 на виртуальный IP-адрес) + 3</span><span class="sxs-lookup"><span data-stu-id="034f6-189">1 (1 per VIP) + 3</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="034f6-190">4 </span><span class="sxs-lookup"><span data-stu-id="034f6-190">4</span></span></p></td>
<td><p><span data-ttu-id="034f6-191">4 </span><span class="sxs-lookup"><span data-stu-id="034f6-191">4</span></span></p></td>
<td><p><span data-ttu-id="034f6-192">1 (по 1 на виртуальный IP-адрес) + 4</span><span class="sxs-lookup"><span data-stu-id="034f6-192">1 (1 per VIP) + 4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="034f6-193">5 </span><span class="sxs-lookup"><span data-stu-id="034f6-193">5</span></span></p></td>
<td><p><span data-ttu-id="034f6-194">17:00</span><span class="sxs-lookup"><span data-stu-id="034f6-194">5</span></span></p></td>
<td><p><span data-ttu-id="034f6-195">1 (по 1 на виртуальный IP-адрес) + 5</span><span class="sxs-lookup"><span data-stu-id="034f6-195">1 (1 per VIP) + 5</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="034f6-p107">Основными факторами при выборе топологии являются высокая доступность и балансировка нагрузки. Требования к высокой доступности могут влиять на решение в отношении балансировки нагрузки.</span><span class="sxs-lookup"><span data-stu-id="034f6-p107">The primary decision points for topology selection are high availability and load balancing. The requirement for high availability can influence the load balancing decision.</span></span>

  - <span data-ttu-id="034f6-198">**Высокая доступность**   Если вам нужна высокая доступность, разверните по крайней мере два пограничных сервера в пуле.</span><span class="sxs-lookup"><span data-stu-id="034f6-198">**High availability**   If you need high availability, deploy at least two Edge Servers in a pool.</span></span> <span data-ttu-id="034f6-199">Один пограничный пул обеспечивает поддержку до двенадцати пограничных серверов.</span><span class="sxs-lookup"><span data-stu-id="034f6-199">A single Edge pool will support up to twelve Edge Servers.</span></span> <span data-ttu-id="034f6-200">Если требуется большая емкость, вы можете развернуть несколько пограничных пулов.</span><span class="sxs-lookup"><span data-stu-id="034f6-200">If more capacity is required, you can deploy multiple Edge pools.</span></span> <span data-ttu-id="034f6-201">Как правило, внешний доступ требуется 10 % контингента пользователей.</span><span class="sxs-lookup"><span data-stu-id="034f6-201">As a general rule, 10% of a given user base will need external access.</span></span>
    
    <div>
    

    > [!IMPORTANT]
    > <span data-ttu-id="034f6-202">Построитель топологий позволяет настраивать до двадцати пограничных серверов в один пограничный пул.</span><span class="sxs-lookup"><span data-stu-id="034f6-202">Topology Builder will allow you to configure up to twenty Edge Servers in a single Edge pool.</span></span> <span data-ttu-id="034f6-203">Проверенное и поддерживаемое максимальное количество пограничных серверов в пуле составляет двенадцать и построитель топологий, что позволяет не использовать более двенадцати пограничных серверов в пределах одного пограничного пула.</span><span class="sxs-lookup"><span data-stu-id="034f6-203">The tested and supported maximum number of Edge Servers in a pool is twelve and Topology Builder allowing for a number larger than twelve should not be construed as implied support for more than twelve Edge Servers in a single Edge pool.</span></span>

    
    </div>

  - <span data-ttu-id="034f6-204">**Аппаратная балансировка нагрузки**   Аппаратная балансировка нагрузки поддерживается для балансировки нагрузки Lync Server 2013 пограничных серверов при использовании общедоступных IP-адресов для пограничных внешних интерфейсов.</span><span class="sxs-lookup"><span data-stu-id="034f6-204">**Hardware load balancing**   Hardware load balancing is supported for load balancing Lync Server 2013 Edge Servers when using publicly routable IP addresses for the Edge external interfaces.</span></span> <span data-ttu-id="034f6-205">Например, этот подход следует использовать для отработки отказа следующих приложений:</span><span class="sxs-lookup"><span data-stu-id="034f6-205">For example, you would use this approach in situations where failover is required for any of the following applications:</span></span>
    
      - <span data-ttu-id="034f6-206">общедоступная служба обмена мгновенными сообщениями;</span><span class="sxs-lookup"><span data-stu-id="034f6-206">Public IM connectivity</span></span>
    
      - <span data-ttu-id="034f6-207">Федерация с компаниями, работающими под управлением Microsoft Office Communications Server 2007 или Microsoft Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="034f6-207">Federation with companies running Microsoft Office Communications Server 2007 or Microsoft Office Communications Server 2007 R2</span></span>
    
      - <span data-ttu-id="034f6-208">внешний доступ к единой системе обмена сообщениями Exchange 2007 или Exchange 2010;</span><span class="sxs-lookup"><span data-stu-id="034f6-208">External access to Exchange 2007 Unified Messaging (UM) or Exchange 2010 UM</span></span>
        
        <div>
        

        > [!IMPORTANT]
        > <span data-ttu-id="034f6-209">Балансировка нагрузки на DNS для Exchange 2010 SP1 и более поздних версий поддерживается для единой системы обмена сообщениями Exchange.</span><span class="sxs-lookup"><span data-stu-id="034f6-209">DNS load balancing for Exchange 2010 SP1 and newer is supported for Exchange UM.</span></span>

        
        </div>
    
    <span data-ttu-id="034f6-p111">Эти приложения не поддерживают балансировку нагрузки DNS и, хотя и будут работать, но будут подключаться только к первому пограничному серверу в пуле. Если он недоступен, установить подключение не удастся. Например, если в пуле развернуто несколько пограничных серверов для обработки федеративного трафика, только один прокси-сервер доступа будет получать трафик, а остальные будут бездействовать.</span><span class="sxs-lookup"><span data-stu-id="034f6-p111">These three applications will continue to operate, but they are not DNS load balancing aware and will only connect to the first Edge Server in the pool. If that server is unavailable, the connection will fail. For example, if multiple Edge Servers are deployed in a pool to handle the federated traffic load, only one access proxy actually receives traffic while the others are idle.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="034f6-213">Использование балансировки нагрузки на DNS рекомендуется при Федерации с компаниями, использующими Lync Server 2010 и Office 365 или Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="034f6-213">Using DNS load balancing is recommended if you are federating with companies using Lync Server 2010 and Office 365 or Microsoft 365.</span></span> <span data-ttu-id="034f6-214">Имейте в виду, что в большинстве федеративных партнеров используется Office Communications Server 2007 или Office Communications Server 2007 R2, что существенно влияет на производительность.</span><span class="sxs-lookup"><span data-stu-id="034f6-214">Be aware that there are significant performance impacts if most of your federated partners are using Office Communications Server 2007 or Office Communications Server 2007 R2.</span></span>



<span data-ttu-id="034f6-215"></div>

</div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="034f6-215"></div>

</div>

<span> </span>

</div>

</div>

</span></span></div>

