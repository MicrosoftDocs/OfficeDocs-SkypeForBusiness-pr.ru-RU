---
title: Сводка по DNS — масштабируемая консолидированная пограничная топология с аппаратными балансировщиками нагрузки
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS summary - Scaled consolidated edge with hardware load balancers
ms:assetid: 8453297c-da1d-4b9e-a37e-6721458c6feb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398670(v=OCS.15)
ms:contentKeyID: 48184700
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c6be703e13ec50eb66ba52c981196df06adc6e5b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41737199"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-summary---scaled-consolidated-edge-with-hardware-load-balancers-in-lync-server-2013"></a><span data-ttu-id="d2ac0-102">Сводка по DNS — масштабируемая консолидированная пограничная топология с аппаратными балансировщиками нагрузки в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d2ac0-102">DNS summary - Scaled consolidated edge with hardware load balancers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d2ac0-103">_**Тема последнего изменения:** 2013-01-27_</span><span class="sxs-lookup"><span data-stu-id="d2ac0-103">_**Topic Last Modified:** 2013-01-27_</span></span>

<span data-ttu-id="d2ac0-104">Требования к записям DNS для удаленного доступа к Lync Server 2013 довольно просты в сравнении с сертификатами и портами.</span><span class="sxs-lookup"><span data-stu-id="d2ac0-104">DNS record requirements for remote access to Lync Server 2013 are fairly straightforward compared to those for certificates and ports.</span></span> <span data-ttu-id="d2ac0-105">Кроме того, в зависимости от того, как вы настраиваете клиентов под управлением Lync 2013 и включена ли интеграция, многие записи не являются обязательными.</span><span class="sxs-lookup"><span data-stu-id="d2ac0-105">Also, many records are optional, depending on how you configure clients running Lync 2013 and whether you enable federation.</span></span>

<span data-ttu-id="d2ac0-106">Дополнительные сведения о требованиях к службе DNS для Lync 2013: [Определение требований к DNS для Lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d2ac0-106">For details about Lync 2013 DNS requirements, see [Determine DNS requirements for Lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span></span>

<span data-ttu-id="d2ac0-107">Дополнительные сведения о настройке автоматической конфигурации клиентов Lync 2013, если DNS с разделением не настроена, приведены в статье [Определение требований к DNS для Lync Server 2013](lync-server-2013-determine-dns-requirements.md)в разделе Автоматическая настройка без разделения DNS-мозгового обобщения.</span><span class="sxs-lookup"><span data-stu-id="d2ac0-107">For details about configuring automatic configuration of Lync 2013 clients if split-brain DNS is not configured, see the "Automatic Configuration without Split Brain DNS" section in [Determine DNS requirements for Lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span></span>

<span data-ttu-id="d2ac0-108">В таблице ниже приведены сведения о DNS-записях, которые необходимы для поддержки топологии масштабируемой консолидированной граничного сервера (Балансировка нагрузки оборудования).</span><span class="sxs-lookup"><span data-stu-id="d2ac0-108">The following table contains a summary of the DNS records that are required to support the Scaled Consolidated Edge Topology (Hardware Load Balanced) figure.</span></span> <span data-ttu-id="d2ac0-109">Обратите внимание, что некоторые DNS-записи требуются только для автоматической настройки для клиентов Lync.</span><span class="sxs-lookup"><span data-stu-id="d2ac0-109">Note that certain DNS records are required only for automatic configuration for Lync clients.</span></span> <span data-ttu-id="d2ac0-110">Если вы планируете использовать объекты групповой политики (GPO) для настройки клиентов Lync, связанные записи не нужны.</span><span class="sxs-lookup"><span data-stu-id="d2ac0-110">If you plan to use group policy objects (GPOs) to configure Lync clients, the associated records are not necessary.</span></span>

<div>

## <a name="important-edge-server-network-adapter-requirements"></a><span data-ttu-id="d2ac0-111">ВНИМАНИЕ! требования к сетевому адаптеру пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="d2ac0-111">IMPORTANT: Edge Server Network Adapter Requirements</span></span>

<span data-ttu-id="d2ac0-112">Чтобы избежать проблем с маршрутизацией, убедитесь в том, что на пограничных серверах есть по крайней мере два сетевых адаптера, и что шлюз по умолчанию задан только на сетевом адаптере, связанном с внешним интерфейсом.</span><span class="sxs-lookup"><span data-stu-id="d2ac0-112">To avoid routing issues, verify that there are at least two network adapters in your Edge Servers and that the default gateway is set only on the network adapter associated with the external interface.</span></span> <span data-ttu-id="d2ac0-113">Например, как показано в сценарии масштабируемой подложки в [масштабной консолидированной границе с аппаратными подсистемами балансировки нагрузки в Lync Server 2013](lync-server-2013-scaled-consolidated-edge-with-hardware-load-balancers.md), шлюз по умолчанию будет указывать на внешний брандмауэр.</span><span class="sxs-lookup"><span data-stu-id="d2ac0-113">For example, as shown in the Scaled Consolidated Edge Scenario figure in [Scaled consolidated edge with hardware load balancers in Lync Server 2013](lync-server-2013-scaled-consolidated-edge-with-hardware-load-balancers.md), the default gateway would point to the external firewall.</span></span>

<span data-ttu-id="d2ac0-114">Вы можете настроить два сетевых адаптера для каждого из серверов пограничного сервера, выполнив указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="d2ac0-114">You can configure two network adapters in each of your Edge Servers as follows:</span></span>

  - <span data-ttu-id="d2ac0-115">**Сетевой адаптер 1 (внутренний интерфейс)**</span><span class="sxs-lookup"><span data-stu-id="d2ac0-115">**Network adapter 1 (Internal Interface)**</span></span>
    
    <span data-ttu-id="d2ac0-116">Внутренний интерфейс с назначенным 172.25.33.10.</span><span class="sxs-lookup"><span data-stu-id="d2ac0-116">Internal interface with 172.25.33.10 assigned.</span></span>
    
    <span data-ttu-id="d2ac0-117">Шлюз по умолчанию отсутствует.</span><span class="sxs-lookup"><span data-stu-id="d2ac0-117">No default gateway.</span></span>
    
    <span data-ttu-id="d2ac0-118">Убедитесь в том, что в сети есть маршрут, содержащий внутренний интерфейс пограничного сервера, в любые сети, которые содержат клиенты или серверы Lync Server (например, с 172.25.33.0 на 192.168.10.0).</span><span class="sxs-lookup"><span data-stu-id="d2ac0-118">Ensure there is a route from the network containing the Edge Server internal interface to any networks that contain Lync Server clients or servers running Lync Server (for example, from 172.25.33.0 to 192.168.10.0).</span></span>

  - <span data-ttu-id="d2ac0-119">**Сетевой адаптер 2 (внешний интерфейс)**</span><span class="sxs-lookup"><span data-stu-id="d2ac0-119">**Network adapter 2 (External Interface)**</span></span>
    
    <span data-ttu-id="d2ac0-120">Для этого сетевого адаптера назначены три общедоступные IP-адреса, например 131.107.155.10 для службы Edge Access, 131.107.155.20 для службы Edge для веб-конференций, 131.107.155.30 для службы EDGE (/V).</span><span class="sxs-lookup"><span data-stu-id="d2ac0-120">Three public IP addresses are assigned to this network adapter, for example 131.107.155.10 for Access Edge service, 131.107.155.20 for Web Conferencing Edge service, 131.107.155.30 for A/V Edge service.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="d2ac0-121">IP-адреса, назначенные фактическим внешним сетевым интерфейсам пограничного сервера, могут зависеть от того, какой аппаратный балансировщик нагрузки вы выбрали.</span><span class="sxs-lookup"><span data-stu-id="d2ac0-121">The IP addresses that are assigned to the actual external network interfaces of the Edge Server may depend on which hardware load balancer you choose.</span></span> <span data-ttu-id="d2ac0-122">Для получения сведений о фактическом требованиях к IP-адресам ознакомьтесь с документацией для подсистемы балансировки нагрузки для оборудования.</span><span class="sxs-lookup"><span data-stu-id="d2ac0-122">Refer to the documentation for your hardware load balancer to understand the actual IP address requirements.</span></span><BR><span data-ttu-id="d2ac0-123">Возможно, хотя и не рекомендуется использовать один IP-адрес для всех трех интерфейсов служб Edge.</span><span class="sxs-lookup"><span data-stu-id="d2ac0-123">It is possible, though not recommended, to use a single IP address for all three Edge service interfaces.</span></span> <span data-ttu-id="d2ac0-124">Несмотря на то, что это сохранит IP-адреса, для каждой службы требуется указать разные номера портов.</span><span class="sxs-lookup"><span data-stu-id="d2ac0-124">Though this does save IP addresses, it requires different port numbers for each service.</span></span> <span data-ttu-id="d2ac0-125">Номер порта по умолчанию: 443/TCP, что позволяет большинству удаленных брандмауэров допустить трафик.</span><span class="sxs-lookup"><span data-stu-id="d2ac0-125">The default port number is 443/TCP, which ensures that most remote firewalls will allow the traffic.</span></span> <span data-ttu-id="d2ac0-126">Изменение значений порта (например,) 5061/TCP для службы Edge Access, 444/TCP для службы пограничного доступа к веб-конференции и порт 443/TCP для службы Edge/V может привести к проблемам с удаленными пользователями, в которых брандмауэр не разрешает трафик через 5061/TCP и 444/TCP.</span><span class="sxs-lookup"><span data-stu-id="d2ac0-126">Changing the port values to (for example) 5061/TCP for the Access Edge service, 444/TCP for the Web Conferencing Edge service and 443/TCP for the A/V Edge service might cause problems for remote users where a firewall that they are behind does not allow the traffic over 5061/TCP and 444/TCP.</span></span> <span data-ttu-id="d2ac0-127">Кроме того, три отдельных IP-адреса упрощают устранение неполадок, так как они позволяют фильтровать по IP-адресу.</span><span class="sxs-lookup"><span data-stu-id="d2ac0-127">Additionally, three distinct IP addresses makes troubleshooting easier due to being able to filter on IP address.</span></span>

    
    </div>
    
    <span data-ttu-id="d2ac0-128">IP-адрес службы Edge Access является основным шлюзом, установленным на маршрутизатор, подключенный к Интернету (131.107.155.1).</span><span class="sxs-lookup"><span data-stu-id="d2ac0-128">Access Edge service IP address is primary with default gateway set to Internet-facing router (131.107.155.1).</span></span>
    
    <span data-ttu-id="d2ac0-129">Служба Edge для веб-конференций и IP-адреса службы Edge/V.</span><span class="sxs-lookup"><span data-stu-id="d2ac0-129">Web Conferencing Edge service and A/V Edge service IP addresses secondary.</span></span>

<div>


> [!TIP]
> <span data-ttu-id="d2ac0-130">Настройка пограничного сервера двумя сетевыми адаптерами — один из двух вариантов.</span><span class="sxs-lookup"><span data-stu-id="d2ac0-130">Configuring the Edge Server with two network adapters is one of two options.</span></span> <span data-ttu-id="d2ac0-131">Другим вариантом является использование одного сетевого адаптера для внутренних и трех сетевых адаптеров на внешней стороне пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="d2ac0-131">The other option is to use one network adapter for the internal side and three network adapters for the external side of the Edge Server.</span></span> <span data-ttu-id="d2ac0-132">Основным преимуществом этого параметра является отдельный сетевой адаптер для службы пограничного сервера и, возможно, более краткая коллекция данных, если требуется устранение неполадок</span><span class="sxs-lookup"><span data-stu-id="d2ac0-132">The main benefit of this option is a distinct network adapter per Edge Server service, and potentially more concise data collection when troubleshooting is necessary</span></span>



</div>

### <a name="dns-records-required-for-scaled-consolidated-edge-hardware-load-balanced-example"></a><span data-ttu-id="d2ac0-133">DNS-записи, необходимые для масштабируемой консолидированной кромки, аппаратной балансировки нагрузки (например)</span><span class="sxs-lookup"><span data-stu-id="d2ac0-133">DNS Records Required for Scaled Consolidated Edge, Hardware Load Balanced (Example)</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d2ac0-134">Расположение/тип/порт</span><span class="sxs-lookup"><span data-stu-id="d2ac0-134">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="d2ac0-135">Полное доменное имя/DNS-запись</span><span class="sxs-lookup"><span data-stu-id="d2ac0-135">FQDN/DNS Record</span></span></th>
<th><span data-ttu-id="d2ac0-136">IP-адрес или полное доменное имя</span><span class="sxs-lookup"><span data-stu-id="d2ac0-136">IP Address/FQDN</span></span></th>
<th><span data-ttu-id="d2ac0-137">Карты и примечания</span><span class="sxs-lookup"><span data-stu-id="d2ac0-137">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d2ac0-138">Внешние DNS/A</span><span class="sxs-lookup"><span data-stu-id="d2ac0-138">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="d2ac0-139">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="d2ac0-139">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="d2ac0-140">131.107.155.10</span><span class="sxs-lookup"><span data-stu-id="d2ac0-140">131.107.155.10</span></span></p></td>
<td><p><span data-ttu-id="d2ac0-141">Внешний интерфейс службы пограничного доступа (Contoso).</span><span class="sxs-lookup"><span data-stu-id="d2ac0-141">Access Edge service external interface (Contoso).</span></span> <span data-ttu-id="d2ac0-142">При необходимости повторите эти действия для всех доменов SIP с пользователями, поддерживающими Lync.</span><span class="sxs-lookup"><span data-stu-id="d2ac0-142">Repeat as necessary for all SIP domains with Lync enabled users</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d2ac0-143">Внешние DNS/A</span><span class="sxs-lookup"><span data-stu-id="d2ac0-143">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="d2ac0-144">webcon.contoso.com</span><span class="sxs-lookup"><span data-stu-id="d2ac0-144">webcon.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="d2ac0-145">131.107.155.20</span><span class="sxs-lookup"><span data-stu-id="d2ac0-145">131.107.155.20</span></span></p></td>
<td><p><span data-ttu-id="d2ac0-146">Внешний интерфейс службы Edge для веб-конференций</span><span class="sxs-lookup"><span data-stu-id="d2ac0-146">Web Conferencing Edge service external interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d2ac0-147">Внешние DNS/A</span><span class="sxs-lookup"><span data-stu-id="d2ac0-147">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="d2ac0-148">av.contoso.com</span><span class="sxs-lookup"><span data-stu-id="d2ac0-148">av.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="d2ac0-149">131.107.155.30</span><span class="sxs-lookup"><span data-stu-id="d2ac0-149">131.107.155.30</span></span></p></td>
<td><p><span data-ttu-id="d2ac0-150">Внешний интерфейс службы Edge</span><span class="sxs-lookup"><span data-stu-id="d2ac0-150">A/V Edge service external interface</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d2ac0-151">Внешние DNS/SRV/443</span><span class="sxs-lookup"><span data-stu-id="d2ac0-151">External DNS/SRV/443</span></span></p></td>
<td><p><span data-ttu-id="d2ac0-152">_sip._tls.contoso.com</span><span class="sxs-lookup"><span data-stu-id="d2ac0-152">_sip._tls.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="d2ac0-153">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="d2ac0-153">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="d2ac0-154">Внешний интерфейс службы Edge Access.</span><span class="sxs-lookup"><span data-stu-id="d2ac0-154">Access Edge service external interface.</span></span> <span data-ttu-id="d2ac0-155">Требуется для автоматической настройки клиентов Lync 2013 и Lync 2010 для работы с внешними сотрудниками.</span><span class="sxs-lookup"><span data-stu-id="d2ac0-155">Required for automatic configuration of Lync 2013 and Lync 2010 clients to work externally.</span></span> <span data-ttu-id="d2ac0-156">При необходимости повторите эти действия для всех доменов SIP с пользователями, поддерживающими Lync.</span><span class="sxs-lookup"><span data-stu-id="d2ac0-156">Repeat as necessary for all SIP domains with Lync enabled users.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d2ac0-157">Внешние DNS/SRV/5061</span><span class="sxs-lookup"><span data-stu-id="d2ac0-157">External DNS/SRV/5061</span></span></p></td>
<td><p><span data-ttu-id="d2ac0-158">_sipfederationtls._tcp.contoso.com</span><span class="sxs-lookup"><span data-stu-id="d2ac0-158">_sipfederationtls._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="d2ac0-159">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="d2ac0-159">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="d2ac0-160">Внешний интерфейс службы Edge Access External Interface, необходимый для автоматического обнаружения DNS федеративных партнеров, известный как "разрешенный домен SIP" (в предыдущих версиях — Улучшенная Федерация).</span><span class="sxs-lookup"><span data-stu-id="d2ac0-160">SIP Access Edge service external interface Required for automatic DNS discovery of federated partners known as “Allowed SIP Domain” (called enhanced federation in previous releases).</span></span> <span data-ttu-id="d2ac0-161">Повторите эти действия для всех доменов SIP с пользователями, поддерживающими Lync, и клиентами Microsoft Lync Mobile, использующими либо службу push-уведомлений, либо службу push-уведомлений Apple.</span><span class="sxs-lookup"><span data-stu-id="d2ac0-161">Repeat as necessary for all SIP domains with Lync enabled users and Microsoft Lync Mobile clients that use either the Push Notification Service or the Apple Push Notification service</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d2ac0-162">Внутренняя DNS/A</span><span class="sxs-lookup"><span data-stu-id="d2ac0-162">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="d2ac0-163">lsedge.contoso.net</span><span class="sxs-lookup"><span data-stu-id="d2ac0-163">lsedge.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="d2ac0-164">172.25.33.10</span><span class="sxs-lookup"><span data-stu-id="d2ac0-164">172.25.33.10</span></span></p></td>
<td><p><span data-ttu-id="d2ac0-165">Внутренний интерфейс "консолидированный Edge"</span><span class="sxs-lookup"><span data-stu-id="d2ac0-165">Consolidated Edge internal interface</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

