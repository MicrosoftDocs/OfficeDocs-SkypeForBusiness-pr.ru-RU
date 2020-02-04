---
title: 'Lync Server 2013: сводка по DNS — масштабируемая консолидированная пограничная топология, балансировка нагрузки на DNS с общедоступными IP-адресами'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS summary - Scaled consolidated edge, DNS load balancing with public IP addresses
ms:assetid: dc8f096a-a0a4-4f71-8930-88ff8fc089d9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205319(v=OCS.15)
ms:contentKeyID: 48185594
ms.date: 03/09/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3f748f8107e4d1c0da41a07285eb61e4a3149551
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41737189"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-summary---scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses-in-lync-server-2013"></a><span data-ttu-id="d1ad3-102">Сводка по DNS — масштабируемая консолидированная пограничная топология, балансировка нагрузки на DNS с общедоступными IP-адресами в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d1ad3-102">DNS summary - Scaled consolidated edge, DNS load balancing with public IP addresses in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d1ad3-103">_**Тема последнего изменения:** 2017-03-09_</span><span class="sxs-lookup"><span data-stu-id="d1ad3-103">_**Topic Last Modified:** 2017-03-09_</span></span>

<span data-ttu-id="d1ad3-104">Требования к записям DNS для удаленного доступа к Lync Server 2013 довольно просты в сравнении с сертификатами и портами.</span><span class="sxs-lookup"><span data-stu-id="d1ad3-104">DNS record requirements for remote access to Lync Server 2013 are fairly straightforward compared to those for certificates and ports.</span></span> <span data-ttu-id="d1ad3-105">Кроме того, в зависимости от того, как вы настраиваете клиентов под управлением Lync 2013 и включена ли интеграция, многие записи не являются обязательными.</span><span class="sxs-lookup"><span data-stu-id="d1ad3-105">Also, many records are optional, depending on how you configure clients running Lync 2013 and whether you enable federation.</span></span>

<span data-ttu-id="d1ad3-106">Дополнительные сведения о требованиях к службе DNS для Lync 2013: [Определение требований к DNS для Lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d1ad3-106">For details about Lync 2013 DNS requirements, see [Determine DNS requirements for Lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span></span>

<span data-ttu-id="d1ad3-107">Дополнительные сведения о настройке автоматической конфигурации клиентов Lync 2013, если DNS с разделением не настроена, приведены в статье [Определение требований к DNS для Lync Server 2013](lync-server-2013-determine-dns-requirements.md)в разделе Автоматическая настройка без разделения DNS-мозгового обобщения.</span><span class="sxs-lookup"><span data-stu-id="d1ad3-107">For details about configuring automatic configuration of Lync 2013 clients if split-brain DNS is not configured, see the "Automatic Configuration without Split Brain DNS" section in [Determine DNS requirements for Lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span></span>

<span data-ttu-id="d1ad3-108">В таблице ниже приведены сведения о DNS-записях, которые должны поддерживать единую объединенную топологию пограничного объекта, которая показана на рисунке одномерной топологии.</span><span class="sxs-lookup"><span data-stu-id="d1ad3-108">The following table contains a summary of the DNS records that are required to support the single consolidated edge topology shown in the Single Consolidated Edge Topology figure.</span></span> <span data-ttu-id="d1ad3-109">Обратите внимание, что определенные записи DNS требуются только для автоматической настройки клиентов Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="d1ad3-109">Note that certain DNS records are required only for automatic configuration of Lync 2013 clients.</span></span> <span data-ttu-id="d1ad3-110">Если вы планируете использовать объекты групповой политики (GPO) для настройки клиентов Lync, связанные записи не нужны.</span><span class="sxs-lookup"><span data-stu-id="d1ad3-110">If you plan to use group policy objects (GPOs) to configure Lync clients, the associated records are not necessary.</span></span>

<div>

## <a name="important-edge-server-network-adapter-requirements"></a><span data-ttu-id="d1ad3-111">ВНИМАНИЕ! требования к сетевому адаптеру пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="d1ad3-111">IMPORTANT: Edge Server Network Adapter Requirements</span></span>

<span data-ttu-id="d1ad3-112">Чтобы избежать проблем с маршрутизацией, убедитесь в том, что на пограничных серверах есть по крайней мере два сетевых адаптера, и что шлюз по умолчанию задан только на сетевом адаптере, связанном с внешним интерфейсом.</span><span class="sxs-lookup"><span data-stu-id="d1ad3-112">To avoid routing issues, verify that there are at least two network adapters in your Edge Servers and that the default gateway is set only on the network adapter associated with the external interface.</span></span> <span data-ttu-id="d1ad3-113">Например, как показано в сценарии масштабируемой консолидированной подложки в [масштабной консолидированной границе, балансировка нагрузки DNS с общедоступными IP-адресами в Lync Server 2013](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md) , шлюз по умолчанию указывает на внешний брандмауэр.</span><span class="sxs-lookup"><span data-stu-id="d1ad3-113">For example, as shown in the Scaled Consolidated Edge Scenario figure in [Scaled consolidated edge, DNS load balancing with public IP addresses in Lync Server 2013](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md) , the default gateway would point to the external firewall.</span></span>

<span data-ttu-id="d1ad3-114">Вы можете настроить два сетевых адаптера для каждого пограничного сервера, выполнив указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="d1ad3-114">You can configure two network adapters in each of your Edge Server as follows:</span></span>

  - <span data-ttu-id="d1ad3-115">**Сетевой адаптер 1-узел 1 (внутренний интерфейс)**</span><span class="sxs-lookup"><span data-stu-id="d1ad3-115">**Network adapter 1 - Node 1 (Internal Interface)**</span></span>
    
    <span data-ttu-id="d1ad3-116">Внутренний интерфейс с назначенным 172.25.33.10.</span><span class="sxs-lookup"><span data-stu-id="d1ad3-116">Internal interface with 172.25.33.10 assigned.</span></span>
    
    <span data-ttu-id="d1ad3-117">Шлюз по умолчанию не определен.</span><span class="sxs-lookup"><span data-stu-id="d1ad3-117">No default gateway is defined.</span></span>
    
    <span data-ttu-id="d1ad3-118">Убедитесь в том, что в сети есть маршрут, содержащий внутренний интерфейс EDGE, для всех сетей, содержащих серверы с установленными клиентами Lync Server 2013 или Lync Server 2013 (например, с 172.25.33.0 на 192.168.10.0).</span><span class="sxs-lookup"><span data-stu-id="d1ad3-118">Ensure that there is a route from the network containing the Edge internal interface to any networks that contain servers running Lync Server 2013 or Lync Server 2013 clients (for example, from 172.25.33.0 to 192.168.10.0).</span></span>

  - <span data-ttu-id="d1ad3-119">**Сетевой адаптер 1-node 2 (внутренний интерфейс)**</span><span class="sxs-lookup"><span data-stu-id="d1ad3-119">**Network adapter 1 - Node 2 (Internal Interface)**</span></span>
    
    <span data-ttu-id="d1ad3-120">Внутренний интерфейс с назначенным 172.25.33.11.</span><span class="sxs-lookup"><span data-stu-id="d1ad3-120">Internal interface with 172.25.33.11 assigned.</span></span>
    
    <span data-ttu-id="d1ad3-121">Шлюз по умолчанию не определен.</span><span class="sxs-lookup"><span data-stu-id="d1ad3-121">No default gateway is defined.</span></span>
    
    <span data-ttu-id="d1ad3-122">Убедитесь в том, что в сети есть маршрут, содержащий внутренний интерфейс EDGE, для всех сетей, содержащих серверы с установленными клиентами Lync Server 2013 или Lync Server 2013 (например, с 172.25.33.0 на 192.168.10.0).</span><span class="sxs-lookup"><span data-stu-id="d1ad3-122">Ensure that there is a route from the network containing the Edge internal interface to any networks that contain servers running Lync Server 2013 or Lync Server 2013 clients (for example, from 172.25.33.0 to 192.168.10.0).</span></span>

  - <span data-ttu-id="d1ad3-123">**Сетевой адаптер 2, узел 1 (внешний интерфейс)**</span><span class="sxs-lookup"><span data-stu-id="d1ad3-123">**Network adapter 2 Node 1 (External Interface)**</span></span>
    
    <span data-ttu-id="d1ad3-124">Этому сетевому адаптеру назначаются три частных IP-адреса, например 131.107.155.10 для службы Edge Access, 131.107.155.20 для службы Edge для веб-конференций, 131.107.155.30 для службы EDGE (/V).</span><span class="sxs-lookup"><span data-stu-id="d1ad3-124">Three private IP addresses are assigned to this network adapter, for example 131.107.155.10 for Access Edge service, 131.107.155.20 for Web Conferencing Edge service, 131.107.155.30 for A/V Edge service.</span></span>
    
    <span data-ttu-id="d1ad3-125">Общедоступный IP-адрес службы Edge для доступа является основным шлюзом по умолчанию, установленным на общедоступном маршрутизаторе (131.107.155.1).</span><span class="sxs-lookup"><span data-stu-id="d1ad3-125">The Access Edge service public IP address is primary with default gateway set to the public router (131.107.155.1).</span></span>
    
    <span data-ttu-id="d1ad3-126">Служба Edge для веб-конференций и частные IP-адреса в Microsoft Edge являются дополнительными IP-адресами в разделе " **Дополнительно** " свойств **протокола IP версии 4 (TCP/IPv4)** и IP- **протоколов версии 6 (TCP/IPv6)** для **подключений по локальной** сети в Windows Server.</span><span class="sxs-lookup"><span data-stu-id="d1ad3-126">Web Conferencing Edge service and A/V Edge service private IP addresses are additional IP addresses in the **Advanced** section of the properties of **Internet Protocol Version 4 (TCP/IPv4)** and **Internet Protocol Version 6 (TCP/IPv6)** of the **Local Area Connection Properties** in Windows Server.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d1ad3-127">Возможно, хотя и не рекомендуется использовать один IP-адрес для всех трех интерфейсов служб Edge.</span><span class="sxs-lookup"><span data-stu-id="d1ad3-127">It is possible, though not recommended, to use a single IP address for all three Edge service interfaces.</span></span> <span data-ttu-id="d1ad3-128">Несмотря на то, что это сохранит IP-адреса, для каждой службы требуется указать разные номера портов.</span><span class="sxs-lookup"><span data-stu-id="d1ad3-128">Though this does save IP addresses, it requires different port numbers for each service.</span></span> <span data-ttu-id="d1ad3-129">Номер порта по умолчанию: 443/TCP, что позволяет большинству удаленных брандмауэров допустить трафик.</span><span class="sxs-lookup"><span data-stu-id="d1ad3-129">The default port number is 443/TCP, which ensures that most remote firewalls will allow the traffic.</span></span> <span data-ttu-id="d1ad3-130">Изменение значений порта (например,) 5061/TCP для службы Edge Access, 444/TCP для службы пограничного доступа к веб-конференции и порт 443/TCP для службы Edge/V может привести к проблемам с удаленными пользователями, в которых брандмауэр не разрешает трафик через 5061/TCP и 444/TCP.</span><span class="sxs-lookup"><span data-stu-id="d1ad3-130">Changing the port values to (for example) 5061/TCP for the Access Edge service, 444/TCP for the Web Conferencing Edge service and 443/TCP for the A/V Edge service might cause problems for remote users where a firewall that they are behind does not allow the traffic over 5061/TCP and 444/TCP.</span></span> <span data-ttu-id="d1ad3-131">Кроме того, три отдельных IP-адреса упрощают устранение неполадок, так как они позволяют фильтровать по IP-адресу.</span><span class="sxs-lookup"><span data-stu-id="d1ad3-131">Additionally, three distinct IP addresses makes troubleshooting easier due to being able to filter on IP address.</span></span>

    
    </div>

  - <span data-ttu-id="d1ad3-132">**Сетевой адаптер 2, узел 2 (внешний интерфейс)**</span><span class="sxs-lookup"><span data-stu-id="d1ad3-132">**Network adapter 2 Node 2 (External Interface)**</span></span>
    
    <span data-ttu-id="d1ad3-133">Этому сетевому адаптеру назначаются три частных IP-адреса, например 131.107.155.11 для службы Edge Access, 131.107.155.21 для службы Edge для веб-конференций, 131.107.155.31 для службы EDGE (/V).</span><span class="sxs-lookup"><span data-stu-id="d1ad3-133">Three private IP addresses are assigned to this network adapter, for example 131.107.155.11 for Access Edge service, 131.107.155.21 for Web Conferencing Edge service, 131.107.155.31 for A/V Edge service.</span></span>
    
    <span data-ttu-id="d1ad3-134">Общедоступный IP-адрес службы Edge для доступа является основным шлюзом по умолчанию, установленным на общедоступном маршрутизаторе (131.107.155.1).</span><span class="sxs-lookup"><span data-stu-id="d1ad3-134">The Access Edge service public IP address is primary with default gateway set to the public router (131.107.155.1).</span></span>
    
    <span data-ttu-id="d1ad3-135">Служба Edge для веб-конференций и частные IP-адреса в Microsoft Edge являются дополнительными IP-адресами в разделе " **Дополнительно** " свойств **протокола IP версии 4 (TCP/IPv4)** и IP- **протоколов версии 6 (TCP/IPv6)** для **подключений по локальной** сети в Windows Server.</span><span class="sxs-lookup"><span data-stu-id="d1ad3-135">Web Conferencing Edge service and A/V Edge service private IP addresses are additional IP addresses in the **Advanced** section of the properties of **Internet Protocol Version 4 (TCP/IPv4)** and **Internet Protocol Version 6 (TCP/IPv6)** of the **Local Area Connection Properties** in Windows Server.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="d1ad3-136">Настройка пограничного сервера двумя сетевыми адаптерами — один из двух вариантов.</span><span class="sxs-lookup"><span data-stu-id="d1ad3-136">Configuring the Edge Server with two network adapters is one of two options.</span></span> <span data-ttu-id="d1ad3-137">Другим вариантом является использование одного сетевого адаптера для внутренних и трех сетевых адаптеров на внешней стороне пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="d1ad3-137">The other option is to use one network adapter for the internal side and three network adapters for the external side of the Edge Server.</span></span> <span data-ttu-id="d1ad3-138">Основным преимуществом этого параметра является отдельный сетевой адаптер для службы пограничного сервера и, возможно, более краткая коллекция данных, если требуется устранение неполадок</span><span class="sxs-lookup"><span data-stu-id="d1ad3-138">The main benefit of this option is a distinct network adapter per Edge Server service, and potentially more concise data collection when troubleshooting is necessary</span></span>



</div>

### <a name="dns-records-required-for-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses-example"></a><span data-ttu-id="d1ad3-139">DNS-записи, необходимые для масштабируемых консолидированных кромок, балансировка нагрузки DNS с общедоступными IP-адресами (пример)</span><span class="sxs-lookup"><span data-stu-id="d1ad3-139">DNS Records Required for Scaled Consolidated Edge, DNS Load Balancing with Public IP Addresses (Example)</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d1ad3-140">Расположение/тип/порт</span><span class="sxs-lookup"><span data-stu-id="d1ad3-140">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="d1ad3-141">Полное доменное имя/DNS-запись</span><span class="sxs-lookup"><span data-stu-id="d1ad3-141">FQDN/DNS Record</span></span></th>
<th><span data-ttu-id="d1ad3-142">IP-адрес или полное доменное имя</span><span class="sxs-lookup"><span data-stu-id="d1ad3-142">IP Address/FQDN</span></span></th>
<th><span data-ttu-id="d1ad3-143">Карты и примечания</span><span class="sxs-lookup"><span data-stu-id="d1ad3-143">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d1ad3-144">Внешние DNS/A</span><span class="sxs-lookup"><span data-stu-id="d1ad3-144">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="d1ad3-145">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="d1ad3-145">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="d1ad3-146">131.107.155.10 и 131.107.155.11</span><span class="sxs-lookup"><span data-stu-id="d1ad3-146">131.107.155.10 and 131.107.155.11</span></span></p></td>
<td><p><span data-ttu-id="d1ad3-147">Внешний интерфейс службы Edge Access (Contoso) при необходимости повторять все домены SIP с пользователями, поддерживающими Lync</span><span class="sxs-lookup"><span data-stu-id="d1ad3-147">Access Edge service external interface (Contoso) Repeat as necessary for all SIP domains with Lync enabled users</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d1ad3-148">Внешние DNS/A</span><span class="sxs-lookup"><span data-stu-id="d1ad3-148">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="d1ad3-149">webcon.contoso.com</span><span class="sxs-lookup"><span data-stu-id="d1ad3-149">webcon.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="d1ad3-150">131.107.155.20 и 131.107.155.21</span><span class="sxs-lookup"><span data-stu-id="d1ad3-150">131.107.155.20 and 131.107.155.21</span></span></p></td>
<td><p><span data-ttu-id="d1ad3-151">Внешний интерфейс службы Edge для веб-конференций</span><span class="sxs-lookup"><span data-stu-id="d1ad3-151">Web Conferencing Edge service external interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d1ad3-152">Внешние DNS/A</span><span class="sxs-lookup"><span data-stu-id="d1ad3-152">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="d1ad3-153">av.contoso.com</span><span class="sxs-lookup"><span data-stu-id="d1ad3-153">av.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="d1ad3-154">131.107.155.30 и 131.107.155.31</span><span class="sxs-lookup"><span data-stu-id="d1ad3-154">131.107.155.30 and 131.107.155.31</span></span></p></td>
<td><p><span data-ttu-id="d1ad3-155">Внешний интерфейс службы Edge</span><span class="sxs-lookup"><span data-stu-id="d1ad3-155">A/V Edge service external interface</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d1ad3-156">Внешние DNS/SRV/443</span><span class="sxs-lookup"><span data-stu-id="d1ad3-156">External DNS/SRV/443</span></span></p></td>
<td><p><span data-ttu-id="d1ad3-157">_sip._tls.contoso.com</span><span class="sxs-lookup"><span data-stu-id="d1ad3-157">_sip._tls.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="d1ad3-158">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="d1ad3-158">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="d1ad3-159">Внешний интерфейс службы Edge Access.</span><span class="sxs-lookup"><span data-stu-id="d1ad3-159">Access Edge service external interface.</span></span> <span data-ttu-id="d1ad3-160">Требуется для автоматической настройки клиентов Lync 2013 и Lync 2010 для работы с внешними сотрудниками.</span><span class="sxs-lookup"><span data-stu-id="d1ad3-160">Required for automatic configuration of Lync 2013 and Lync 2010 clients to work externally.</span></span> <span data-ttu-id="d1ad3-161">При необходимости повторите эти действия для всех доменов SIP с пользователями, поддерживающими Lync.</span><span class="sxs-lookup"><span data-stu-id="d1ad3-161">Repeat as necessary for all SIP domains with Lync enabled users.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d1ad3-162">Внешние DNS/SRV/5061</span><span class="sxs-lookup"><span data-stu-id="d1ad3-162">External DNS/SRV/5061</span></span></p></td>
<td><p><span data-ttu-id="d1ad3-163">_sipfederationtls._tcp.contoso.com</span><span class="sxs-lookup"><span data-stu-id="d1ad3-163">_sipfederationtls._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="d1ad3-164">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="d1ad3-164">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="d1ad3-165">Внешний интерфейс службы Edge Access, необходимый для автоматического обнаружения DNS федеративных партнеров, известный как "разрешенный домен SIP" (в предыдущих версиях — Улучшенная Федерация).</span><span class="sxs-lookup"><span data-stu-id="d1ad3-165">Access Edge service external interface Required for automatic DNS discovery of federated partners known as “Allowed SIP Domain” (called enhanced federation in previous releases).</span></span> <span data-ttu-id="d1ad3-166">При необходимости повторите эти действия для всех доменов SIP с пользователями, поддерживающими Lync.</span><span class="sxs-lookup"><span data-stu-id="d1ad3-166">Repeat as necessary for all SIP domains with Lync enabled users</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d1ad3-167">Внутренняя DNS/A</span><span class="sxs-lookup"><span data-stu-id="d1ad3-167">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="d1ad3-168">lsedge.contoso.net</span><span class="sxs-lookup"><span data-stu-id="d1ad3-168">lsedge.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="d1ad3-169">172.25.33.10 и 172.25.33.11</span><span class="sxs-lookup"><span data-stu-id="d1ad3-169">172.25.33.10 and 172.25.33.11</span></span></p></td>
<td><p><span data-ttu-id="d1ad3-170">Внутренний интерфейс "консолидированный Edge"</span><span class="sxs-lookup"><span data-stu-id="d1ad3-170">Consolidated Edge internal interface</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="records-required-for-federation"></a><span data-ttu-id="d1ad3-171">Записи, необходимые для Федерации</span><span class="sxs-lookup"><span data-stu-id="d1ad3-171">Records Required for Federation</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d1ad3-172">Расположение/тип/порт</span><span class="sxs-lookup"><span data-stu-id="d1ad3-172">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="d1ad3-173">Полное доменное имя</span><span class="sxs-lookup"><span data-stu-id="d1ad3-173">FQDN</span></span></th>
<th><span data-ttu-id="d1ad3-174">IP-адрес или полное доменное имя записи узла</span><span class="sxs-lookup"><span data-stu-id="d1ad3-174">IP address/FQDN host record</span></span></th>
<th><span data-ttu-id="d1ad3-175">Карты и примечания</span><span class="sxs-lookup"><span data-stu-id="d1ad3-175">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d1ad3-176">Внешние DNS/SRV/5061</span><span class="sxs-lookup"><span data-stu-id="d1ad3-176">External DNS/SRV/5061</span></span></p></td>
<td><p><span data-ttu-id="d1ad3-177">_sipfederationtls._tcp.contoso.com</span><span class="sxs-lookup"><span data-stu-id="d1ad3-177">_sipfederationtls._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="d1ad3-178">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="d1ad3-178">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="d1ad3-179">Внешний интерфейс службы Edge Access External Interface, необходимый для автоматического обнаружения DNS для Федерации с другими потенциальными партнерами Федерации и известный как "разрешенные домены SIP" (с названием "Улучшенная Федерация" в предыдущих версиях).</span><span class="sxs-lookup"><span data-stu-id="d1ad3-179">SIP Access Edge service external interface Required for automatic DNS discovery of your federation to other potential federation partners, and is known as “Allowed SIP Domains” (called enhanced federation in previous releases).</span></span></p>
<div>

> [!IMPORTANT]  
> <span data-ttu-id="d1ad3-180">Повторите эти действия для всех доменов SIP с пользователями, поддерживающими Lync, и клиентами Microsoft Lync Mobile, использующими либо службу push-уведомлений, либо службу push-уведомлений Apple.</span><span class="sxs-lookup"><span data-stu-id="d1ad3-180">Repeat as necessary for all SIP domains with Lync enabled users and Microsoft Lync Mobile clients that use either the Push Notification Service or the Apple Push Notification service</span></span>


</div></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="dns-summary-for-extensible-messaging-and-presence-protocol"></a><span data-ttu-id="d1ad3-181">Сводка DNS по расширенному протоколу обмена сообщениями и присутствием</span><span class="sxs-lookup"><span data-stu-id="d1ad3-181">DNS Summary for Extensible Messaging and Presence Protocol</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d1ad3-182">Расположение/тип/порт</span><span class="sxs-lookup"><span data-stu-id="d1ad3-182">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="d1ad3-183">Полное доменное имя</span><span class="sxs-lookup"><span data-stu-id="d1ad3-183">FQDN</span></span></th>
<th><span data-ttu-id="d1ad3-184">IP-адрес или полное доменное имя записи узла</span><span class="sxs-lookup"><span data-stu-id="d1ad3-184">IP address/FQDN host record</span></span></th>
<th><span data-ttu-id="d1ad3-185">Карты и примечания</span><span class="sxs-lookup"><span data-stu-id="d1ad3-185">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d1ad3-186">Внешние DNS/SRV/5269</span><span class="sxs-lookup"><span data-stu-id="d1ad3-186">External DNS/SRV/5269</span></span></p></td>
<td><p><span data-ttu-id="d1ad3-187">_xmpp-server._tcp.contoso.com</span><span class="sxs-lookup"><span data-stu-id="d1ad3-187">_xmpp-server._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="d1ad3-188">xmpp.contoso.com</span><span class="sxs-lookup"><span data-stu-id="d1ad3-188">xmpp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="d1ad3-189">Внешний интерфейс КСМПП прокси-сервера в службе пограничного доступа или пуле Edge. При необходимости повторите эти действия для всех внутренних доменов SIP, в которых пользователи Lync поддерживают доступ к контактам с контактами КСМПП с помощью глобальной политики, политики сайта, в которой находится пользователь, или политики пользователя, примененной к Пользователь с поддержкой Lync.</span><span class="sxs-lookup"><span data-stu-id="d1ad3-189">XMPP proxy external interface on the Access Edge service or Edge pool.Repeat as necessary for all internal SIP domains with Lync enabled users where contact with XMPP contacts is allowed through the configuration of the External Access Policy through a global policy, site policy where the user is located, or user policy applied to the Lync-enabled user.</span></span> <span data-ttu-id="d1ad3-190">Разрешенный домен КСМПП также должен быть настроен в политике федеративных партнеров КСМПП.</span><span class="sxs-lookup"><span data-stu-id="d1ad3-190">An allowed XMPP domain must also be configured in the XMPP Federated Partners policy.</span></span> <span data-ttu-id="d1ad3-191">Дополнительные сведения <strong>можно</strong> найти в разделах.</span><span class="sxs-lookup"><span data-stu-id="d1ad3-191">See topics in <strong>See Also</strong> for additional details</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d1ad3-192">Внешние DNS/A</span><span class="sxs-lookup"><span data-stu-id="d1ad3-192">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="d1ad3-193">xmpp.contoso.com (например)</span><span class="sxs-lookup"><span data-stu-id="d1ad3-193">xmpp.contoso.com (for example)</span></span></p></td>
<td><p><span data-ttu-id="d1ad3-194">IP-адрес службы пограничного доступа на пограничном сервере или в пограничном пуле, где размещен прокси-сервер КСМПП</span><span class="sxs-lookup"><span data-stu-id="d1ad3-194">IP address of Access Edge service on your Edge Server or Edge pool hosting XMPP proxy</span></span></p></td>
<td><p><span data-ttu-id="d1ad3-195">Указывает на службу пограничного доступа или пул EDGE, на котором размещена служба прокси КСМПП.</span><span class="sxs-lookup"><span data-stu-id="d1ad3-195">Points to the Access Edge service or Edge pool that hosts the XMPP proxy service.</span></span> <span data-ttu-id="d1ad3-196">Как правило, создаваемая SRV-запись будет указывать на эту запись узла (A или AAAA).</span><span class="sxs-lookup"><span data-stu-id="d1ad3-196">Typically, the SRV record that you create will point to this host (A or AAAA) record</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

