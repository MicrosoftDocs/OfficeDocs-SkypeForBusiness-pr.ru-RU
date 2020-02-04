---
title: 'Lync Server 2013: выбор топологии'
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
ms.openlocfilehash: 0b9f59648d845f37c7cf6d92c471b81a29415753
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41729889"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="choosing-a-topology-in-lync-server-2013"></a><span data-ttu-id="be7e1-102">Выбор топологии в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="be7e1-102">Choosing a topology in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span data-ttu-id="be7e1-103">_**Тема последнего изменения:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="be7e1-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="be7e1-104">При выборе топологии вы можете использовать один из указанных ниже вариантов топологии.</span><span class="sxs-lookup"><span data-stu-id="be7e1-104">When you choose a topology, you can use one the following supported topology options:</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="be7e1-105">Если не указано иное, если у вас есть опыт работы с Microsoft Lync Server 2010, здесь вы найдете рекомендации, описанные в этой статье в значительном неизменном виде.</span><span class="sxs-lookup"><span data-stu-id="be7e1-105">Unless otherwise noted, if you have experience with Microsoft Lync Server 2010, you will find the guidance here is largely unchanged.</span></span>



</div>

  - [<span data-ttu-id="be7e1-106">Единая консолидированная пограничная топология с закрытыми IP-адресами и трансляцией сетевых адресов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="be7e1-106">Single consolidated edge with private IP addresses and NAT in Lync Server 2013</span></span>](lync-server-2013-single-consolidated-edge-with-private-ip-addresses-and-nat.md)

  - [<span data-ttu-id="be7e1-107">Единая консолидированная пограничная топология с общедоступными IP-адресами в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="be7e1-107">Single consolidated edge with public IP addresses in Lync Server 2013</span></span>](lync-server-2013-single-consolidated-edge-with-public-ip-addresses.md)

  - [<span data-ttu-id="be7e1-108">Масштабируемая консолидированная пограничная топология, балансировка нагрузки на DNS с закрытыми IP-адресами и трансляцией сетевых адресов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="be7e1-108">Scaled consolidated edge, DNS load balancing with private IP addresses using NAT in Lync Server 2013</span></span>](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md)

  - [<span data-ttu-id="be7e1-109">Масштабируемая консолидированная пограничная топология, балансировка нагрузки на DNS с общедоступными IP-адресами в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="be7e1-109">Scaled consolidated edge, DNS load balancing with public IP addresses in Lync Server 2013</span></span>](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md)

  - [<span data-ttu-id="be7e1-110">Масштабируемая консолидированная пограничная топология с аппаратными балансировщиками нагрузки в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="be7e1-110">Scaled consolidated edge with hardware load balancers in Lync Server 2013</span></span>](lync-server-2013-scaled-consolidated-edge-with-hardware-load-balancers.md)

<div>


> [!IMPORTANT]
> <span data-ttu-id="be7e1-111">Балансировка нагрузки на внутреннем и внешнем пограничным интерфейсах должна относиться к одному и тому же типу.</span><span class="sxs-lookup"><span data-stu-id="be7e1-111">The internal Edge interface and external Edge interface must use the same type of load balancing.</span></span> <span data-ttu-id="be7e1-112">Невозможно осуществлять балансировку нагрузки на одном пограничном интерфейсе средствами DNS, а на другом — аппаратными средствами.</span><span class="sxs-lookup"><span data-stu-id="be7e1-112">You cannot use DNS load balancing on one Edge interface and hardware load balancing on the other Edge interface.</span></span>



</div>

<span data-ttu-id="be7e1-113">В таблице ниже перечислены функции, доступные при использовании поддерживаемых топологий Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="be7e1-113">The following table summarizes the functionality available with the supported Microsoft Lync Server 2013 topologies.</span></span> <span data-ttu-id="be7e1-114">Заголовки столбцов обозначают функциональные возможности, доступные для определенного параметра конфигурации Edge.</span><span class="sxs-lookup"><span data-stu-id="be7e1-114">The column headings indicate the functionality available for a given Edge configuration option.</span></span> <span data-ttu-id="be7e1-115">С помощью масштабируемого EDGE (Балансировка нагрузки DNS) в качестве примера вы видите, что он поддерживает высокий уровень доступности, может использовать частные IP-адреса без маршрутизации (с NAT) или маршрутизацию общедоступных IP-адресов, назначенных внешним интерфейсам периметра, и сокращает расходы, так как Подсистема балансировки нагрузки аппаратных средств не требуется.</span><span class="sxs-lookup"><span data-stu-id="be7e1-115">Using the Scaled Edge (DNS load balanced) option as an example, you can see that it supports high availability, can use non-routable private IP addresses (with NAT) or routable public IP addresses assigned to the Edge external interfaces, and reduces cost because a hardware load balancer is not required.</span></span>

<span data-ttu-id="be7e1-116">Сценарии пограничного отработки отказа, поддерживаемые с помощью балансировки нагрузки DNS, являются сеансами "точка-точка" Lync-to-Lync, сеансами конференции Lync, семинарами Lync-to-PSTN и Office 365.</span><span class="sxs-lookup"><span data-stu-id="be7e1-116">Edge failover scenarios supported with DNS Load Balancing are Lync-to-Lync point-to-point sessions, Lync conferencing sessions, Lync-to-PSTN sessions and Office 365.</span></span> <span data-ttu-id="be7e1-117">Сценарии отработки отказа, которые не выигрывают от балансировки нагрузки DNS (для Exchange 2010 SP1), общедоступной службы обмена мгновенными сообщениями и интеграции с серверами с запущенными средствами Office Communications Server.</span><span class="sxs-lookup"><span data-stu-id="be7e1-117">Edge failover scenarios that do not benefit from DNS Load Balancing are failover for remote user Exchange Unified Messaging (UM) (prior to Exchange 2010 SP1), public instant messaging (IM) connectivity, and federation with servers running Office Communications Server.</span></span>

### <a name="summary-of-edge-server-topology-options"></a><span data-ttu-id="be7e1-118">Общие сведения о параметрах топологии пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="be7e1-118">Summary of Edge Server Topology Options</span></span>

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
<th><span data-ttu-id="be7e1-119">Топология</span><span class="sxs-lookup"><span data-stu-id="be7e1-119">Topology</span></span></th>
<th><span data-ttu-id="be7e1-120">Высокая доступность</span><span class="sxs-lookup"><span data-stu-id="be7e1-120">High availability</span></span></th>
<th><span data-ttu-id="be7e1-121">Дополнительные записи DNS A, необходимые для внешнего пограничного сервера в пуле Edge</span><span class="sxs-lookup"><span data-stu-id="be7e1-121">Additional DNS A records required for external Edge Server in the Edge pool</span></span></th>
<th><span data-ttu-id="be7e1-122">Отработка отказа для сеансов Lync-to-Lync</span><span class="sxs-lookup"><span data-stu-id="be7e1-122">Edge Failover for Lync-to-Lync sessions</span></span></th>
<th><span data-ttu-id="be7e1-123">Отработка отказа в сеансах интеграции Lync-to-Lync ЕУМ/PIC/OCS</span><span class="sxs-lookup"><span data-stu-id="be7e1-123">Edge Failover for Lync-to-Lync EUM/PIC/OCS Federation sessions</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="be7e1-124">Один край с помощью NAT</span><span class="sxs-lookup"><span data-stu-id="be7e1-124">Single Edge using NAT</span></span></p></td>
<td><p><span data-ttu-id="be7e1-125">Нет</span><span class="sxs-lookup"><span data-stu-id="be7e1-125">No</span></span></p></td>
<td><p><span data-ttu-id="be7e1-126">Нет</span><span class="sxs-lookup"><span data-stu-id="be7e1-126">No</span></span></p></td>
<td><p><span data-ttu-id="be7e1-127">Нет</span><span class="sxs-lookup"><span data-stu-id="be7e1-127">No</span></span></p></td>
<td><p><span data-ttu-id="be7e1-128">Нет</span><span class="sxs-lookup"><span data-stu-id="be7e1-128">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="be7e1-129">Один край с общедоступным IP-адресом</span><span class="sxs-lookup"><span data-stu-id="be7e1-129">Single Edge using Public IP</span></span></p></td>
<td><p><span data-ttu-id="be7e1-130">Нет</span><span class="sxs-lookup"><span data-stu-id="be7e1-130">No</span></span></p></td>
<td><p><span data-ttu-id="be7e1-131">Нет</span><span class="sxs-lookup"><span data-stu-id="be7e1-131">No</span></span></p></td>
<td><p><span data-ttu-id="be7e1-132">Нет</span><span class="sxs-lookup"><span data-stu-id="be7e1-132">No</span></span></p></td>
<td><p><span data-ttu-id="be7e1-133">Нет</span><span class="sxs-lookup"><span data-stu-id="be7e1-133">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="be7e1-134">Масштабируемый край (Балансировка нагрузки DNS) с использованием NAT</span><span class="sxs-lookup"><span data-stu-id="be7e1-134">Scaled Edge (DNS Load Balanced) using NAT</span></span></p></td>
<td><p><span data-ttu-id="be7e1-135">Да </span><span class="sxs-lookup"><span data-stu-id="be7e1-135">Yes</span></span></p></td>
<td><p><span data-ttu-id="be7e1-136">Да </span><span class="sxs-lookup"><span data-stu-id="be7e1-136">Yes</span></span></p></td>
<td><p><span data-ttu-id="be7e1-137">Да </span><span class="sxs-lookup"><span data-stu-id="be7e1-137">Yes</span></span></p></td>
<td><p>*</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="be7e1-138">Масштабируемый край (Балансировка нагрузки DNS) с использованием общедоступного IP-адреса</span><span class="sxs-lookup"><span data-stu-id="be7e1-138">Scaled Edge (DNS Load Balanced) using Public IP</span></span></p></td>
<td><p><span data-ttu-id="be7e1-139">Да </span><span class="sxs-lookup"><span data-stu-id="be7e1-139">Yes</span></span></p></td>
<td><p><span data-ttu-id="be7e1-140">Да </span><span class="sxs-lookup"><span data-stu-id="be7e1-140">Yes</span></span></p></td>
<td><p><span data-ttu-id="be7e1-141">Да </span><span class="sxs-lookup"><span data-stu-id="be7e1-141">Yes</span></span></p></td>
<td><p>*</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="be7e1-142">Балансировка нагрузки аппаратных средств с масштабированным краем</span><span class="sxs-lookup"><span data-stu-id="be7e1-142">Scaled Edge Hardware load balanced)</span></span></p></td>
<td><p><span data-ttu-id="be7e1-143">Да</span><span class="sxs-lookup"><span data-stu-id="be7e1-143">Yes</span></span></p></td>
<td><p><span data-ttu-id="be7e1-144">Нет (одна запись A DNS на каждый виртуальный IP-адрес)</span><span class="sxs-lookup"><span data-stu-id="be7e1-144">No (one DNS A record per VIP)</span></span></p></td>
<td><p><span data-ttu-id="be7e1-145">Да</span><span class="sxs-lookup"><span data-stu-id="be7e1-145">Yes</span></span></p></td>
<td><p><span data-ttu-id="be7e1-146">Да </span><span class="sxs-lookup"><span data-stu-id="be7e1-146">Yes</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="be7e1-147">**\*** Отработка отказа при подключении к службе обмена мгновенными сообщениями и интеграции с серверами с установленным пакетом Office Communications Server недоступна для балансировки нагрузки DNS.</span><span class="sxs-lookup"><span data-stu-id="be7e1-147">**\*** Failover for public instant messaging (IM) connectivity, and federation with servers running Office Communications Server is not available with DNS load balancing.</span></span> <span data-ttu-id="be7e1-148">Переключение на другой ресурс Exchange UM (удаленный пользователь) с помощью балансировки нагрузки DNS требует наличия Exchange Server 2010 SP1 или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="be7e1-148">Exchange UM (remote user) failover using DNS load balancing requires Exchange Server 2010 SP1 or newer.</span></span>



> [!NOTE]
> <span data-ttu-id="be7e1-149">Топологии с одним краем и масштабированным краем (Балансировка нагрузки DNS) может использовать:</span><span class="sxs-lookup"><span data-stu-id="be7e1-149">Single Edge and Scaled Edge (DNS load balanced) topologies can use:</span></span>
> <ul><li><p><span data-ttu-id="be7e1-150">Маршрутизируемые общедоступные IP-адреса</span><span class="sxs-lookup"><span data-stu-id="be7e1-150">Routable public IP addresses</span></span></p></li>
> <li><p><span data-ttu-id="be7e1-151">Частный IP-адрес без маршрутизации при использовании симметричного преобразования сетевых адресов (NAT)</span><span class="sxs-lookup"><span data-stu-id="be7e1-151">Non-routable private IP address if symmetric network address translation (NAT) is used</span></span></p></li>
>
> <ul><li> <span data-ttu-id="be7e1-152">Если вы используете общедоступный IP-адрес или частный IP-адрес с помощью NAT, вы по-прежнему будете использовать одинаковое количество IP-адресов на основе выбора конфигурации в построителе топологии.</span><span class="sxs-lookup"><span data-stu-id="be7e1-152">If you use public IP address or private IP address with NAT, you will still use the same number of IP addresses based on your configuration choice in Topology Builder.</span></span> <span data-ttu-id="be7e1-153">Вы можете настроить пограничный сервер на использование одного IP-адреса с разными портами для каждой службы или использовать отдельные IP-адреса для каждой службы, но использовать один и тот же порт (по умолчанию — TCP 443).</span><span class="sxs-lookup"><span data-stu-id="be7e1-153">You can configure the Edge Server to use a single IP address with distinct ports per service, or use distinct IP addresses per service, but use the same port (by default, TCP 443).</span></span></li></ul>>
> <span data-ttu-id="be7e1-154">Если вы решили использовать для NAT частные IP-адреса без маршрутизации, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="be7e1-154">If you decide to use non-routable private IP addresses with NAT:</span></span>
> <ul><li><p><span data-ttu-id="be7e1-155">Для всех трех внешних интерфейсов необходимо использовать маршрутизируемый частный IP-адрес.</span><span class="sxs-lookup"><span data-stu-id="be7e1-155">You must use routable private IP addresses on all three external interfaces</span></span></p></li>
> <li><p><span data-ttu-id="be7e1-156">Необходимо настроить Симметричный NAT для входящего и исходящего трафика.</span><span class="sxs-lookup"><span data-stu-id="be7e1-156">You must configure symmetric NAT for incoming and outgoing traffic</span></span></p></li></ul>>
> <span data-ttu-id="be7e1-157">В топологии с масштабированным краем (Балансировка нагрузки оборудования) должны использоваться общедоступные IP-адреса.</span><span class="sxs-lookup"><span data-stu-id="be7e1-157">Scaled Edge (hardware load balanced) topology must use public IP addresses.</span></span>



<span data-ttu-id="be7e1-158">Lync Server 2013 поддерживает размещение Access, веб-конференций и внешних интерфейсов, расположенных за маршрутизатором или брандмауэром, выполняющим преобразование сетевых адресов (NAT) для одномерной и масштабируемой топологии пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="be7e1-158">Lync Server 2013 supports placing Access, Web Conferencing, and A/V Edge external interfaces behind a router or firewall that performs network address translation (NAT) for both single and scaled consolidated Edge Server topologies.</span></span>

<span data-ttu-id="be7e1-159">Использование NAT для всех внешних интерфейсов пограничного сервера требует использования балансировки нагрузки DNS.</span><span class="sxs-lookup"><span data-stu-id="be7e1-159">Using NAT for all Edge external interfaces requires the use of DNS load balancing.</span></span> <span data-ttu-id="be7e1-160">При сравнении с использованием подсистем балансировки нагрузки для аппаратных средств, использующих NLB, вы можете сократить количество общедоступных IP-адресов на пограничном сервере в пуле EDGE, как описано в следующем списке.</span><span class="sxs-lookup"><span data-stu-id="be7e1-160">When compared to using hardware load balancers, using DNS load balancing without NAT allows you to reduce the number of public IP address per Edge Server in an Edge pool as described in the following list:</span></span>

  - <span data-ttu-id="be7e1-161">Для Lync Server 2013 с масштабированным консолидированным краем (Балансировка нагрузки DNS) требуется три общедоступных IP-адреса для каждого пограничного сервера в пуле Edge.</span><span class="sxs-lookup"><span data-stu-id="be7e1-161">Lync Server 2013 Scaled Consolidated Edge (DNS load balanced) Requires three public IP addresses for each Edge Server in an Edge pool.</span></span>

  - <span data-ttu-id="be7e1-162">Для виртуального IP-адреса подсистемы балансировки нагрузки в Lync Server 2013 с масштабированием (Балансировка нагрузки оборудования) требуется три общедоступных IP-адреса (требования, которые не изменяются по мере добавления пограничных серверов в пул) плюс три общедоступных IP-адреса в каждом Пограничный сервер в пуле.</span><span class="sxs-lookup"><span data-stu-id="be7e1-162">Lync Server 2013 Scaled Consolidated Edge (hardware load balanced) Requires three public IP address for load balancer virtual IP addresses (one time requirement that does not increment as more Edge Servers are added to the pool) plus three public IP addresses per Edge Server in a pool.</span></span>

### <a name="ip-address-requirements-for-scaled-consolidated-edge-ip-address-per-role"></a><span data-ttu-id="be7e1-163">Требования к IP-адресу для масштабируемой консолидированной кромки (IP-адрес на роль)</span><span class="sxs-lookup"><span data-stu-id="be7e1-163">IP Address Requirements for Scaled Consolidated Edge (IP Address per role)</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="be7e1-164">Число пограничных серверов в пуле</span><span class="sxs-lookup"><span data-stu-id="be7e1-164">Number of Edge Servers per pool</span></span></th>
<th><span data-ttu-id="be7e1-165">Число необходимых IP-адресов Lync Server 2013 (Балансировка нагрузки DNS)</span><span class="sxs-lookup"><span data-stu-id="be7e1-165">Number of required IP addresses Lync Server 2013 (DNS load balanced)</span></span></th>
<th><span data-ttu-id="be7e1-166">Число обязательных IP-адресов, Lync Server 2013 (Балансировка нагрузки оборудования)</span><span class="sxs-lookup"><span data-stu-id="be7e1-166">Number of required IP addresses Lync Server 2013 (hardware load balanced)</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="be7e1-167">2</span><span class="sxs-lookup"><span data-stu-id="be7e1-167">2</span></span></p></td>
<td><p><span data-ttu-id="be7e1-168">6</span><span class="sxs-lookup"><span data-stu-id="be7e1-168">6</span></span></p></td>
<td><p><span data-ttu-id="be7e1-169">3 (по 1 на виртуальный IP-адрес) + 6</span><span class="sxs-lookup"><span data-stu-id="be7e1-169">3 (1 per VIP) + 6</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="be7e1-170">3</span><span class="sxs-lookup"><span data-stu-id="be7e1-170">3</span></span></p></td>
<td><p><span data-ttu-id="be7e1-171">@</span><span class="sxs-lookup"><span data-stu-id="be7e1-171">9</span></span></p></td>
<td><p><span data-ttu-id="be7e1-172">3 (по 1 на виртуальный IP-адрес) + 9</span><span class="sxs-lookup"><span data-stu-id="be7e1-172">3 (1 per VIP) + 9</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="be7e1-173">4</span><span class="sxs-lookup"><span data-stu-id="be7e1-173">4</span></span></p></td>
<td><p><span data-ttu-id="be7e1-174">12</span><span class="sxs-lookup"><span data-stu-id="be7e1-174">12</span></span></p></td>
<td><p><span data-ttu-id="be7e1-175">3 (по 1 на виртуальный IP-адрес) + 12</span><span class="sxs-lookup"><span data-stu-id="be7e1-175">3 (1 per VIP) + 12</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="be7e1-176">5</span><span class="sxs-lookup"><span data-stu-id="be7e1-176">5</span></span></p></td>
<td><p><span data-ttu-id="be7e1-177">10-15</span><span class="sxs-lookup"><span data-stu-id="be7e1-177">15</span></span></p></td>
<td><p><span data-ttu-id="be7e1-178">3 (1 на виртуальный IP-адрес) + 15</span><span class="sxs-lookup"><span data-stu-id="be7e1-178">3 (1 per VIP) + 15</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="ip-address-requirements-for-scaled-consolidated-edge-single-ip-address-for-all-roles"></a><span data-ttu-id="be7e1-179">Требования к IP-адресу для масштабируемой консолидированной кромки (один IP-адрес для всех ролей)</span><span class="sxs-lookup"><span data-stu-id="be7e1-179">IP Address Requirements for Scaled Consolidated Edge (Single IP address for all roles)</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="be7e1-180">Число пограничных серверов в пуле</span><span class="sxs-lookup"><span data-stu-id="be7e1-180">Number of Edge Servers per pool</span></span></th>
<th><span data-ttu-id="be7e1-181">Число необходимых IP-адресов Lync Server 2013 (Балансировка нагрузки DNS)</span><span class="sxs-lookup"><span data-stu-id="be7e1-181">Number of required IP addresses Lync Server 2013 (DNS load balanced)</span></span></th>
<th><span data-ttu-id="be7e1-182">Число обязательных IP-адресов, Lync Server 2013 (Балансировка нагрузки оборудования)</span><span class="sxs-lookup"><span data-stu-id="be7e1-182">Number of required IP addresses Lync Server 2013 (hardware load balanced)</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="be7e1-183">2</span><span class="sxs-lookup"><span data-stu-id="be7e1-183">2</span></span></p></td>
<td><p><span data-ttu-id="be7e1-184">2</span><span class="sxs-lookup"><span data-stu-id="be7e1-184">2</span></span></p></td>
<td><p><span data-ttu-id="be7e1-185">1 (по 1 на виртуальный IP-адрес) + 2</span><span class="sxs-lookup"><span data-stu-id="be7e1-185">1 (1 per VIP) + 2</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="be7e1-186">3</span><span class="sxs-lookup"><span data-stu-id="be7e1-186">3</span></span></p></td>
<td><p><span data-ttu-id="be7e1-187">3</span><span class="sxs-lookup"><span data-stu-id="be7e1-187">3</span></span></p></td>
<td><p><span data-ttu-id="be7e1-188">1 (по 1 на виртуальный IP-адрес) + 3</span><span class="sxs-lookup"><span data-stu-id="be7e1-188">1 (1 per VIP) + 3</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="be7e1-189">4</span><span class="sxs-lookup"><span data-stu-id="be7e1-189">4</span></span></p></td>
<td><p><span data-ttu-id="be7e1-190">4</span><span class="sxs-lookup"><span data-stu-id="be7e1-190">4</span></span></p></td>
<td><p><span data-ttu-id="be7e1-191">1 (по 1 на виртуальный IP-адрес) + 4</span><span class="sxs-lookup"><span data-stu-id="be7e1-191">1 (1 per VIP) + 4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="be7e1-192">5</span><span class="sxs-lookup"><span data-stu-id="be7e1-192">5</span></span></p></td>
<td><p><span data-ttu-id="be7e1-193">5</span><span class="sxs-lookup"><span data-stu-id="be7e1-193">5</span></span></p></td>
<td><p><span data-ttu-id="be7e1-194">1 (по 1 на виртуальный IP-адрес) + 5</span><span class="sxs-lookup"><span data-stu-id="be7e1-194">1 (1 per VIP) + 5</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="be7e1-195">Основные точки решения для выбора топологии — это высокая доступность и балансировка нагрузки.</span><span class="sxs-lookup"><span data-stu-id="be7e1-195">The primary decision points for topology selection are high availability and load balancing.</span></span> <span data-ttu-id="be7e1-196">Требование высокой доступности может повлиять на решение балансировки нагрузки.</span><span class="sxs-lookup"><span data-stu-id="be7e1-196">The requirement for high availability can influence the load balancing decision.</span></span>

  - <span data-ttu-id="be7e1-197">**Высокая доступность**   Если вам нужна высокая доступность, разверните по крайней мере два пограничных сервера в пуле.</span><span class="sxs-lookup"><span data-stu-id="be7e1-197">**High availability**   If you need high availability, deploy at least two Edge Servers in a pool.</span></span> <span data-ttu-id="be7e1-198">Один пул пограничного сервера обеспечивает поддержку до двенадцати пограничных серверов.</span><span class="sxs-lookup"><span data-stu-id="be7e1-198">A single Edge pool will support up to twelve Edge Servers.</span></span> <span data-ttu-id="be7e1-199">Если требуется дополнительная емкость, вы можете развернуть несколько пулов пограничных групп.</span><span class="sxs-lookup"><span data-stu-id="be7e1-199">If more capacity is required, you can deploy multiple Edge pools.</span></span> <span data-ttu-id="be7e1-200">Как правило, для 10% от данной базы пользователей потребуется внешний доступ.</span><span class="sxs-lookup"><span data-stu-id="be7e1-200">As a general rule, 10% of a given user base will need external access.</span></span>
    
    <div>
    

    > [!IMPORTANT]
    > <span data-ttu-id="be7e1-201">В построителе топологии вы можете настроить до двадцати пограничных серверов в одном пуле Edge.</span><span class="sxs-lookup"><span data-stu-id="be7e1-201">Topology Builder will allow you to configure up to twenty Edge Servers in a single Edge pool.</span></span> <span data-ttu-id="be7e1-202">Проверенное и поддерживаемое максимальное количество пограничных серверов в пуле — двенадцать, а построитель топологии — число больше двенадцати, которое не должно превышать двенадцать пограничных серверов в одном пуле пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="be7e1-202">The tested and supported maximum number of Edge Servers in a pool is twelve and Topology Builder allowing for a number larger than twelve should not be construed as implied support for more than twelve Edge Servers in a single Edge pool.</span></span>

    
    </div>

  - <span data-ttu-id="be7e1-203">**Балансировка нагрузки аппаратных средств**   Балансировка нагрузки оборудования поддерживается для балансировки нагрузки серверов Lync Server 2013 EDGE, если используется IP-адреса с общедоступной маршрутизацией для внешних интерфейсов Edge.</span><span class="sxs-lookup"><span data-stu-id="be7e1-203">**Hardware load balancing**   Hardware load balancing is supported for load balancing Lync Server 2013 Edge Servers when using publicly routable IP addresses for the Edge external interfaces.</span></span> <span data-ttu-id="be7e1-204">Например, этот подход следует использовать в ситуациях, когда для любого из следующих приложений требуется отработка отказа.</span><span class="sxs-lookup"><span data-stu-id="be7e1-204">For example, you would use this approach in situations where failover is required for any of the following applications:</span></span>
    
      - <span data-ttu-id="be7e1-205">Подключение к общедоступным системам обмена мгновенными сообщениями</span><span class="sxs-lookup"><span data-stu-id="be7e1-205">Public IM connectivity</span></span>
    
      - <span data-ttu-id="be7e1-206">Интеграция с компаниями, использующими Microsoft Office Communications Server 2007 или Microsoft Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="be7e1-206">Federation with companies running Microsoft Office Communications Server 2007 or Microsoft Office Communications Server 2007 R2</span></span>
    
      - <span data-ttu-id="be7e1-207">Внешний доступ к единой системе обмена сообщениями Exchange 2007 и Exchange 2010 (UM)</span><span class="sxs-lookup"><span data-stu-id="be7e1-207">External access to Exchange 2007 Unified Messaging (UM) or Exchange 2010 UM</span></span>
        
        <div>
        

        > [!IMPORTANT]
        > <span data-ttu-id="be7e1-208">Балансировка нагрузки DNS для Exchange 2010 с пакетом обновления 1 (SP1) и более поздних версий поддерживается для Exchange UM.</span><span class="sxs-lookup"><span data-stu-id="be7e1-208">DNS load balancing for Exchange 2010 SP1 and newer is supported for Exchange UM.</span></span>

        
        </div>
    
    <span data-ttu-id="be7e1-209">Эти три приложения продолжают работать, но они не поддерживают балансировку нагрузки DNS и будут подключены только к первому пограничного сервера в пуле.</span><span class="sxs-lookup"><span data-stu-id="be7e1-209">These three applications will continue to operate, but they are not DNS load balancing aware and will only connect to the first Edge Server in the pool.</span></span> <span data-ttu-id="be7e1-210">Если этот сервер недоступен, соединение закончится сбоем.</span><span class="sxs-lookup"><span data-stu-id="be7e1-210">If that server is unavailable, the connection will fail.</span></span> <span data-ttu-id="be7e1-211">Например, если в пуле развернуто несколько пограничных серверов для обработки загрузки федеративных данных, только один прокси-сервер доступа получает трафик, пока другие не простаивают.</span><span class="sxs-lookup"><span data-stu-id="be7e1-211">For example, if multiple Edge Servers are deployed in a pool to handle the federated traffic load, only one access proxy actually receives traffic while the others are idle.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="be7e1-212">Использование балансировки нагрузки DNS рекомендуется, если вы собираетесь в компании с помощью Lync Server 2010 и Microsoft Office 365.</span><span class="sxs-lookup"><span data-stu-id="be7e1-212">Using DNS load balancing is recommended if you are federating with companies using Lync Server 2010 and Microsoft Office 365.</span></span> <span data-ttu-id="be7e1-213">Имейте в виду, что в большинстве федеративных партнеров используется Office Communications Server 2007 или Office Communications Server 2007 R2, что влияет на производительность.</span><span class="sxs-lookup"><span data-stu-id="be7e1-213">Be aware that there are significant performance impacts if most of your federated partners are using Office Communications Server 2007 or Office Communications Server 2007 R2.</span></span>



<span data-ttu-id="be7e1-214"></div>

</div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="be7e1-214"></div>

</div>

<span> </span>

</div>

</div>

</span></span></div>

