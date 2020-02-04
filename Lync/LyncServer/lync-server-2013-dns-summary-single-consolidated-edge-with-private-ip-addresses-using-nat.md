---
title: Сводка по DNS — единая консолидированная пограничная топология с закрытыми IP-адресами и трансляцией сетевых адресов
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS summary - Single consolidated edge with private IP addresses using NAT
ms:assetid: a7e5d792-f397-45e5-af85-20d0f4bf405f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412787(v=OCS.15)
ms:contentKeyID: 48185025
ms.date: 03/09/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3276219fb4c2227cde75cf9a5d3a47616c03336d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736259"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-summary---single-consolidated-edge-with-private-ip-addresses-using-nat-in-lync-server-2013"></a><span data-ttu-id="f9a26-102">Сводка по DNS — единая консолидированная пограничная топология с закрытыми IP-адресами и трансляцией сетевых адресов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f9a26-102">DNS summary - Single consolidated edge with private IP addresses using NAT in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f9a26-103">_**Тема последнего изменения:** 2017-03-09_</span><span class="sxs-lookup"><span data-stu-id="f9a26-103">_**Topic Last Modified:** 2017-03-09_</span></span>

<span data-ttu-id="f9a26-104">Требования к записям DNS для удаленного доступа к Lync Server 2013 довольно просты в сравнении с сертификатами и портами.</span><span class="sxs-lookup"><span data-stu-id="f9a26-104">DNS record requirements for remote access to Lync Server 2013 are fairly straightforward compared to those for certificates and ports.</span></span> <span data-ttu-id="f9a26-105">Кроме того, в зависимости от того, как вы настраиваете клиентов под управлением Lync 2013 и включена ли интеграция, многие записи не являются обязательными.</span><span class="sxs-lookup"><span data-stu-id="f9a26-105">Also, many records are optional, depending on how you configure clients running Lync 2013 and whether you enable federation.</span></span>

<span data-ttu-id="f9a26-106">Дополнительные сведения о требованиях к службе DNS для Lync 2013: [Определение требований к DNS для Lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f9a26-106">For details about Lync 2013 DNS requirements, see [Determine DNS requirements for Lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span></span>

<span data-ttu-id="f9a26-107">Дополнительные сведения о автоматической настройке клиентов, использующих Lync 2013, если DNS с разделением не настроена, обратитесь к разделу автоматическая настройка без разделения и мозгового DNS-сервера в разделе [Определение требований DNS для Lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f9a26-107">For details about automatic configuration of clients running Lync 2013 if split-brain DNS is not configured, see “Automatic Configuration without Split-Brain DNS” in [Determine DNS requirements for Lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span></span>

<span data-ttu-id="f9a26-108">В таблице ниже приведены сведения о DNS-записях, которые должны поддерживать единую объединенную топологию пограничного объекта, которая показана на рисунке одномерной топологии.</span><span class="sxs-lookup"><span data-stu-id="f9a26-108">The following table contains a summary of the DNS records that are required to support the single consolidated edge topology shown in the Single Consolidated Edge Topology figure.</span></span> <span data-ttu-id="f9a26-109">Обратите внимание, что определенные записи DNS требуются только для автоматической настройки клиентов Lync 2013 и Lync 2010.</span><span class="sxs-lookup"><span data-stu-id="f9a26-109">Note that certain DNS records are required only for automatic configuration of Lync 2013 and Lync 2010 clients.</span></span> <span data-ttu-id="f9a26-110">Если вы планируете использовать объекты групповой политики (GPO) для настройки клиентов Lync, соответствующие записи автоматической настройки не нужны.</span><span class="sxs-lookup"><span data-stu-id="f9a26-110">If you plan to use group policy objects (GPOs) to configure Lync clients, the associated automatic configuration records are not necessary.</span></span>

<div>

## <a name="important-edge-server-network-adapter-requirements"></a><span data-ttu-id="f9a26-111">ВНИМАНИЕ! требования к сетевому адаптеру пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="f9a26-111">IMPORTANT: Edge Server Network Adapter Requirements</span></span>

<span data-ttu-id="f9a26-112">Чтобы избежать проблем с маршрутизацией, убедитесь в том, что на пограничных серверах есть по крайней мере два сетевых адаптера, и что шлюз по умолчанию задан только на сетевом адаптере, связанном с внешним интерфейсом.</span><span class="sxs-lookup"><span data-stu-id="f9a26-112">To avoid routing issues, verify that there are at least two network adapters in your Edge Servers and that the default gateway is set only on the network adapter associated with the external interface.</span></span> <span data-ttu-id="f9a26-113">Например, как показано в одной консолидированной топологии пограничного сервера на рисунке [с частными IP-адресами и NAT в Lync Server 2013](lync-server-2013-single-consolidated-edge-with-private-ip-addresses-and-nat.md), шлюз по умолчанию будет указывать на внешний брандмауэр (10.45.16.1).</span><span class="sxs-lookup"><span data-stu-id="f9a26-113">For example, as shown in the Single Consolidated Edge Topology figure in [Single consolidated edge with private IP addresses and NAT in Lync Server 2013](lync-server-2013-single-consolidated-edge-with-private-ip-addresses-and-nat.md), the default gateway would point to the external firewall (10.45.16.1).</span></span>

<span data-ttu-id="f9a26-114">Вы можете настроить два сетевых адаптера на пограничном сервере, выполнив указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="f9a26-114">You can configure two network adapters in your Edge Server as follows:</span></span>

  - <span data-ttu-id="f9a26-115">**Сетевой адаптер 1 (внутренний интерфейс)**</span><span class="sxs-lookup"><span data-stu-id="f9a26-115">**Network adapter 1 (Internal Interface)**</span></span>
    
    <span data-ttu-id="f9a26-116">Внутренний интерфейс с назначенным 172.25.33.10.</span><span class="sxs-lookup"><span data-stu-id="f9a26-116">Internal interface with 172.25.33.10 assigned.</span></span>
    
    <span data-ttu-id="f9a26-117">Шлюз по умолчанию не определен.</span><span class="sxs-lookup"><span data-stu-id="f9a26-117">No default gateway is defined.</span></span>
    
    <span data-ttu-id="f9a26-118">Убедитесь в том, что в сети есть маршрут, содержащий внутренний интерфейс EDGE, для всех сетей, содержащих серверы с установленными клиентами Lync Server 2013 или Lync Server 2013 (например, с 172.25.33.0 на 192.168.10.0).</span><span class="sxs-lookup"><span data-stu-id="f9a26-118">Ensure that there is a route from the network containing the Edge internal interface to any networks that contain servers running Lync Server 2013 or Lync Server 2013 clients (for example, from 172.25.33.0 to 192.168.10.0).</span></span>

  - <span data-ttu-id="f9a26-119">**Сетевой адаптер 2 (внешний интерфейс)**</span><span class="sxs-lookup"><span data-stu-id="f9a26-119">**Network adapter 2 (External Interface)**</span></span>
    
    <span data-ttu-id="f9a26-120">Для этого сетевого адаптера назначены три частных IP-адреса, например 10.45.16.10 для доступа к краю, 10.45.16.20 для веб-конференций EDGE, 10.45.16.30 для AV Edge.</span><span class="sxs-lookup"><span data-stu-id="f9a26-120">Three private IP addresses are assigned to this network adapter, for example 10.45.16.10 for Access Edge, 10.45.16.20 for Web Conferencing Edge, 10.45.16.30 for AV Edge</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="f9a26-121">Возможно, хотя и не рекомендуется использовать один IP-адрес для всех трех интерфейсов служб Edge.</span><span class="sxs-lookup"><span data-stu-id="f9a26-121">It is possible, though not recommended, to use a single IP address for all three Edge service interfaces.</span></span> <span data-ttu-id="f9a26-122">Несмотря на то, что это сохранит IP-адреса, для каждой службы требуется указать разные номера портов.</span><span class="sxs-lookup"><span data-stu-id="f9a26-122">Though this does save IP addresses, it requires different port numbers for each service.</span></span> <span data-ttu-id="f9a26-123">Номер порта по умолчанию: 443/TCP, что позволяет большинству удаленных брандмауэров допустить трафик.</span><span class="sxs-lookup"><span data-stu-id="f9a26-123">The default port number is 443/TCP, which ensures that most remote firewalls will allow the traffic.</span></span> <span data-ttu-id="f9a26-124">Изменение значений порта (например,) 5061/TCP для Edge доступа, 444/TCP для веб-конференций EDGE и 443/TCP для теплосвязи может привести к проблемам с удаленными пользователями, в которых брандмауэр не разрешает трафик через 5061/TCP и 444/TCP.</span><span class="sxs-lookup"><span data-stu-id="f9a26-124">Changing the port values to (for example) 5061/TCP for the Access Edge, 444/TCP for the Web Conferencing Edge and 443/TCP for the AV Edge might cause problems for remote users where a firewall that they are behind does not allow the traffic over 5061/TCP and 444/TCP.</span></span> <span data-ttu-id="f9a26-125">Кроме того, три отдельных IP-адреса упрощают устранение неполадок, так как они позволяют фильтровать по IP-адресу.</span><span class="sxs-lookup"><span data-stu-id="f9a26-125">Additionally, three distinct IP addresses makes troubleshooting easier due to being able to filter on IP address.</span></span>

    
    </div>
    
    <span data-ttu-id="f9a26-126">IP-адрес пограничного доступа является основным шлюзом по умолчанию, установленным на встроенный маршрутизатор (10.45.16.1).</span><span class="sxs-lookup"><span data-stu-id="f9a26-126">Access Edge IP address is primary with default gateway set to integrated router (10.45.16.1).</span></span>
    
    <span data-ttu-id="f9a26-127">Веб-конференции и дополнительные IP-адреса Edge.</span><span class="sxs-lookup"><span data-stu-id="f9a26-127">Web conferencing and A/V Edge IP addresses secondary.</span></span>

<div>


> [!TIP]
> <span data-ttu-id="f9a26-128">Настройка пограничного сервера двумя сетевыми адаптерами — один из двух вариантов.</span><span class="sxs-lookup"><span data-stu-id="f9a26-128">Configuring the Edge Server with two network adapters is one of two options.</span></span> <span data-ttu-id="f9a26-129">Другим вариантом является использование одного сетевого адаптера для внутренних и трех сетевых адаптеров на внешней стороне пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="f9a26-129">The other option is to use one network adapter for the internal side and three network adapters for the external side of the Edge Server.</span></span> <span data-ttu-id="f9a26-130">Основным преимуществом этого параметра является отдельный сетевой адаптер для службы пограничного сервера и, возможно, более краткая коллекция данных, если требуется устранение неполадок</span><span class="sxs-lookup"><span data-stu-id="f9a26-130">The main benefit of this option is a distinct network adapter per Edge Server service, and potentially more concise data collection when troubleshooting is necessary</span></span>



</div>

### <a name="dns-records-required-for-single-consolidated-edge-with-private-ip-addresses-using-nat-example"></a><span data-ttu-id="f9a26-131">DNS-записи, необходимые для единого консолидированного Edge с частными IP-адресами с использованием NAT (например,)</span><span class="sxs-lookup"><span data-stu-id="f9a26-131">DNS Records Required for Single Consolidated Edge with Private IP Addresses Using NAT (Example)</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f9a26-132">Расположение/тип/порт</span><span class="sxs-lookup"><span data-stu-id="f9a26-132">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="f9a26-133">Полное доменное имя/DNS-запись</span><span class="sxs-lookup"><span data-stu-id="f9a26-133">FQDN/DNS Record</span></span></th>
<th><span data-ttu-id="f9a26-134">IP-адрес или полное доменное имя</span><span class="sxs-lookup"><span data-stu-id="f9a26-134">IP Address/FQDN</span></span></th>
<th><span data-ttu-id="f9a26-135">Карты и примечания</span><span class="sxs-lookup"><span data-stu-id="f9a26-135">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f9a26-136">Внешние DNS/A</span><span class="sxs-lookup"><span data-stu-id="f9a26-136">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="f9a26-137">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f9a26-137">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="f9a26-138">131.107.155.10</span><span class="sxs-lookup"><span data-stu-id="f9a26-138">131.107.155.10</span></span></p></td>
<td><p><span data-ttu-id="f9a26-139">Внешний интерфейс Access Edge (Contoso) повторяется по мере необходимости для всех доменов SIP с пользователями, поддерживающими Lync.</span><span class="sxs-lookup"><span data-stu-id="f9a26-139">Access Edge external interface (Contoso)Repeat as necessary for all SIP domains with Lync enabled users</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f9a26-140">Внешние DNS/A</span><span class="sxs-lookup"><span data-stu-id="f9a26-140">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="f9a26-141">webcon.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f9a26-141">webcon.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="f9a26-142">131.107.155.20</span><span class="sxs-lookup"><span data-stu-id="f9a26-142">131.107.155.20</span></span></p></td>
<td><p><span data-ttu-id="f9a26-143">Внешний интерфейс для веб-конференций Edge</span><span class="sxs-lookup"><span data-stu-id="f9a26-143">Web Conferencing Edge external interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f9a26-144">Внешние DNS/A</span><span class="sxs-lookup"><span data-stu-id="f9a26-144">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="f9a26-145">av.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f9a26-145">av.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="f9a26-146">131.107.155.30</span><span class="sxs-lookup"><span data-stu-id="f9a26-146">131.107.155.30</span></span></p></td>
<td><p><span data-ttu-id="f9a26-147">Внешний интерфейс "на/V" Edge</span><span class="sxs-lookup"><span data-stu-id="f9a26-147">A/V Edge external interface</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f9a26-148">Внешние DNS/SRV/443</span><span class="sxs-lookup"><span data-stu-id="f9a26-148">External DNS/SRV/443</span></span></p></td>
<td><p><span data-ttu-id="f9a26-149">_sip._tls.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f9a26-149">_sip._tls.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="f9a26-150">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f9a26-150">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="f9a26-151">Внешний интерфейс пограничного доступа.</span><span class="sxs-lookup"><span data-stu-id="f9a26-151">Access Edge external interface.</span></span> <span data-ttu-id="f9a26-152">Требуется для автоматической настройки клиентов Lync 2013 и Lync 2010 для работы с внешними сотрудниками.</span><span class="sxs-lookup"><span data-stu-id="f9a26-152">Required for automatic configuration of Lync 2013 and Lync 2010 clients to work externally.</span></span> <span data-ttu-id="f9a26-153">При необходимости повторите эти действия для всех доменов SIP с пользователями, поддерживающими Lync.</span><span class="sxs-lookup"><span data-stu-id="f9a26-153">Repeat as necessary for all SIP domains with Lync enabled users.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f9a26-154">Внешние DNS/SRV/5061</span><span class="sxs-lookup"><span data-stu-id="f9a26-154">External DNS/SRV/5061</span></span></p></td>
<td><p><span data-ttu-id="f9a26-155">_sipfederationtls._tcp.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f9a26-155">_sipfederationtls._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="f9a26-156">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f9a26-156">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="f9a26-157">Внешний интерфейс пограничного доступа SIP, необходимый для автоматического обнаружения DNS федеративных партнеров, известного как "разрешенный домен SIP" (в предыдущих версиях — Улучшенная Федерация). При необходимости повторите эти действия для всех доменов SIP с пользователями, поддерживающими Lync.</span><span class="sxs-lookup"><span data-stu-id="f9a26-157">SIP Access Edge external interface Required for automatic DNS discovery of federated partners known as “Allowed SIP Domain” (called enhanced federation in previous releases).Repeat as necessary for all SIP domains with Lync enabled users</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f9a26-158">Внутренняя DNS/A</span><span class="sxs-lookup"><span data-stu-id="f9a26-158">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="f9a26-159">lsedge.contoso.net</span><span class="sxs-lookup"><span data-stu-id="f9a26-159">lsedge.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="f9a26-160">172.25.33.10</span><span class="sxs-lookup"><span data-stu-id="f9a26-160">172.25.33.10</span></span></p></td>
<td><p><span data-ttu-id="f9a26-161">Внутренний интерфейс "консолидированный Edge"</span><span class="sxs-lookup"><span data-stu-id="f9a26-161">Consolidated Edge internal interface</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!IMPORTANT]
> <span data-ttu-id="f9a26-162">Записи, указанные в предыдущей таблице, отображаются с расширением <EM>.NET</EM> или <EM>com</EM> , чтобы выделять зону, в которой они должны находиться, если вы не используете DNS с разделением и мозгом.</span><span class="sxs-lookup"><span data-stu-id="f9a26-162">The records listed in the previous table are shown with either a <EM>.net</EM> extension or a <EM>.com</EM> extension to highlight which zone they need to reside in if you are not using split-brain DNS.</span></span> <span data-ttu-id="f9a26-163">Если вы используете DNS с разделением «расщепленные данные», все записи будут находиться в одной и той же зоне <EM>com</EM> , а единственное отличие состоит в том, что они входят в версию внутренней или внешней зоны DNS.</span><span class="sxs-lookup"><span data-stu-id="f9a26-163">If you are using split-brain DNS, all records would be in the same <EM>.com</EM> zone, with the only distinction being whether they are in the internal or external DNS zone version.</span></span> <span data-ttu-id="f9a26-164">Дополнительные сведения можно найти в разделе "разделение — мозг DNS", в котором <A href="lync-server-2013-determine-dns-requirements.md">определяются требования к DNS для Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="f9a26-164">For details, see “Split-Brain DNS” in <A href="lync-server-2013-determine-dns-requirements.md">Determine DNS requirements for Lync Server 2013</A>.</span></span>



</div>

</div>

<div>

## <a name="records-required-for-federation"></a><span data-ttu-id="f9a26-165">Записи, необходимые для Федерации</span><span class="sxs-lookup"><span data-stu-id="f9a26-165">Records Required for Federation</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f9a26-166">Расположение/тип/порт</span><span class="sxs-lookup"><span data-stu-id="f9a26-166">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="f9a26-167">Полное доменное имя</span><span class="sxs-lookup"><span data-stu-id="f9a26-167">FQDN</span></span></th>
<th><span data-ttu-id="f9a26-168">IP-адрес или полное доменное имя записи узла</span><span class="sxs-lookup"><span data-stu-id="f9a26-168">IP address/FQDN host record</span></span></th>
<th><span data-ttu-id="f9a26-169">Карты и примечания</span><span class="sxs-lookup"><span data-stu-id="f9a26-169">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f9a26-170">Внешние DNS/SRV/5061</span><span class="sxs-lookup"><span data-stu-id="f9a26-170">External DNS/SRV/5061</span></span></p></td>
<td><p><span data-ttu-id="f9a26-171">_sipfederationtls._tcp.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f9a26-171">_sipfederationtls._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="f9a26-172">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f9a26-172">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="f9a26-173">Внешний интерфейс внешнего доступа SIP, необходимый для автоматического обнаружения DNS для Федерации с другими потенциальными партнерами Федерации и известный как "разрешенные домены SIP" (с названием "Улучшенная Федерация в предыдущих версиях)". При необходимости повторите эти действия для всех доменов SIP с пользователями, поддерживающими Lync.</span><span class="sxs-lookup"><span data-stu-id="f9a26-173">SIP Access Edge external interface Required for automatic DNS discovery of your federation to other potential federation partners, and is known as “Allowed SIP Domains” (called enhanced federation in previous releases).Repeat as necessary for all SIP domains with Lync enabled users</span></span></p>



> [!IMPORTANT]
> <span data-ttu-id="f9a26-174">Эта запись SRV требуется для мобильных устройств и для очищенных push-уведомлений</span><span class="sxs-lookup"><span data-stu-id="f9a26-174">This SRV record is required for mobility and the push notification clearing house</span></span>

</td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="dns-summary-for-extensible-messaging-and-presence-protocol"></a><span data-ttu-id="f9a26-175">Сводка DNS по расширенному протоколу обмена сообщениями и присутствием</span><span class="sxs-lookup"><span data-stu-id="f9a26-175">DNS Summary for Extensible Messaging and Presence Protocol</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f9a26-176">Расположение/тип/порт</span><span class="sxs-lookup"><span data-stu-id="f9a26-176">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="f9a26-177">Полное доменное имя</span><span class="sxs-lookup"><span data-stu-id="f9a26-177">FQDN</span></span></th>
<th><span data-ttu-id="f9a26-178">IP-адрес или полное доменное имя записи узла</span><span class="sxs-lookup"><span data-stu-id="f9a26-178">IP address/FQDN host record</span></span></th>
<th><span data-ttu-id="f9a26-179">Карты и примечания</span><span class="sxs-lookup"><span data-stu-id="f9a26-179">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f9a26-180">Внешние DNS/SRV/5269</span><span class="sxs-lookup"><span data-stu-id="f9a26-180">External DNS/SRV/5269</span></span></p></td>
<td><p><span data-ttu-id="f9a26-181">_xmpp-server._tcp.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f9a26-181">_xmpp-server._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="f9a26-182">xmpp.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f9a26-182">xmpp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="f9a26-183">Внешний интерфейс КСМПП прокси-сервера в службе пограничного доступа или пуле Edge. При необходимости повторите эти действия для всех внутренних доменов SIP, в которых пользователи Lync поддерживают доступ к контактам с контактами КСМПП с помощью глобальной политики, политики сайта, в которой находится пользователь, или политики пользователя, примененной к Пользователь с поддержкой Lync.</span><span class="sxs-lookup"><span data-stu-id="f9a26-183">XMPP proxy external interface on the Access Edge service or Edge pool.Repeat as necessary for all internal SIP domains with Lync enabled users where contact with XMPP contacts is allowed through the configuration of the External Access Policy through a global policy, site policy where the user is located, or user policy applied to the Lync-enabled user.</span></span> <span data-ttu-id="f9a26-184">Разрешенный домен КСМПП также должен быть настроен в политике федеративных партнеров КСМПП.</span><span class="sxs-lookup"><span data-stu-id="f9a26-184">An allowed XMPP domain must also be configured in the XMPP Federated Partners policy.</span></span> <span data-ttu-id="f9a26-185">Дополнительные сведения <strong>можно</strong> найти в разделах.</span><span class="sxs-lookup"><span data-stu-id="f9a26-185">See topics in <strong>See Also</strong> for additional details</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f9a26-186">Внешние DNS/A</span><span class="sxs-lookup"><span data-stu-id="f9a26-186">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="f9a26-187">xmpp.contoso.com (например)</span><span class="sxs-lookup"><span data-stu-id="f9a26-187">xmpp.contoso.com (for example)</span></span></p></td>
<td><p><span data-ttu-id="f9a26-188">IP-адрес службы пограничного доступа на пограничном сервере или в пограничном пуле, где размещен прокси-сервер КСМПП</span><span class="sxs-lookup"><span data-stu-id="f9a26-188">IP address of Access Edge service on your Edge Server or Edge pool hosting XMPP proxy</span></span></p></td>
<td><p><span data-ttu-id="f9a26-189">Указывает на службу пограничного доступа или пул EDGE, на котором размещена служба прокси КСМПП.</span><span class="sxs-lookup"><span data-stu-id="f9a26-189">Points to the Access Edge service or Edge pool that hosts the XMPP proxy service.</span></span> <span data-ttu-id="f9a26-190">Как правило, создаваемая SRV-запись будет указывать на эту запись узла (A или AAAA).</span><span class="sxs-lookup"><span data-stu-id="f9a26-190">Typically, the SRV record that you create will point to this host (A or AAAA) record</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

