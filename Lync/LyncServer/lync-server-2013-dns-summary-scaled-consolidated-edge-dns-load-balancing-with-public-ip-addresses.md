---
title: 'Lync Server 2013: сводка по DNS — масштабируемый консолидированный край, балансировка нагрузки на DNS с общедоступными IP-адресами'
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
ms.openlocfilehash: 448cbb0834c8ad7dee983fd6dcd56922cbb030d8
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42036891"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-summary---scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses-in-lync-server-2013"></a><span data-ttu-id="32de1-102">Сводка по DNS — масштабируемый консолидированный край, балансировка нагрузки на DNS с общедоступными IP-адресами в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="32de1-102">DNS summary - Scaled consolidated edge, DNS load balancing with public IP addresses in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="32de1-103">_**Последнее изменение темы:** 2017-03-09_</span><span class="sxs-lookup"><span data-stu-id="32de1-103">_**Topic Last Modified:** 2017-03-09_</span></span>

<span data-ttu-id="32de1-104">Требования к записям DNS для удаленного доступа к Lync Server 2013 довольно просты по сравнению с сертификатами и портами.</span><span class="sxs-lookup"><span data-stu-id="32de1-104">DNS record requirements for remote access to Lync Server 2013 are fairly straightforward compared to those for certificates and ports.</span></span> <span data-ttu-id="32de1-105">Кроме того, многие записи являются необязательными в зависимости от того, как вы настраиваете клиенты, на которых работает Lync 2013, и включена ли Федерация.</span><span class="sxs-lookup"><span data-stu-id="32de1-105">Also, many records are optional, depending on how you configure clients running Lync 2013 and whether you enable federation.</span></span>

<span data-ttu-id="32de1-106">Дополнительные сведения о требованиях к службе DNS для Lync 2013 приведены в статье [Определение требований DNS для Lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="32de1-106">For details about Lync 2013 DNS requirements, see [Determine DNS requirements for Lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span></span>

<span data-ttu-id="32de1-107">Для получения дополнительных сведений о настройке автоматической настройки клиентов Lync 2013 если DNS с разделением не настроена, ознакомьтесь с разделом "Автоматическая настройка без разделения DNS", чтобы [определить требования к DNS для Lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="32de1-107">For details about configuring automatic configuration of Lync 2013 clients if split-brain DNS is not configured, see the "Automatic Configuration without Split Brain DNS" section in [Determine DNS requirements for Lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span></span>

<span data-ttu-id="32de1-108">В следующей таблице содержится сводка по записям DNS, которые необходимы для поддержки топологии единой и консолидированной среды пограничных серверов, показанной на рисунке "Топология единой и консолидированной среды пограничных серверов".</span><span class="sxs-lookup"><span data-stu-id="32de1-108">The following table contains a summary of the DNS records that are required to support the single consolidated edge topology shown in the Single Consolidated Edge Topology figure.</span></span> <span data-ttu-id="32de1-109">Обратите внимание, что определенные записи DNS необходимы только для автоматической настройки клиентов Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="32de1-109">Note that certain DNS records are required only for automatic configuration of Lync 2013 clients.</span></span> <span data-ttu-id="32de1-110">Если вы планируете использовать объекты групповой политики (GPO) для настройки клиентов Lync, связанные записи не нужны.</span><span class="sxs-lookup"><span data-stu-id="32de1-110">If you plan to use group policy objects (GPOs) to configure Lync clients, the associated records are not necessary.</span></span>

<div>

## <a name="important-edge-server-network-adapter-requirements"></a><span data-ttu-id="32de1-111">ВАЖНО! требования к сетевому адаптеру пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="32de1-111">IMPORTANT: Edge Server Network Adapter Requirements</span></span>

<span data-ttu-id="32de1-112">Чтобы избежать проблем с маршрутизацией, убедитесь, что в пограничных серверах есть по крайней мере два сетевых адаптера и что шлюз по умолчанию задан только на сетевом адаптере, связанном с внешним интерфейсом.</span><span class="sxs-lookup"><span data-stu-id="32de1-112">To avoid routing issues, verify that there are at least two network adapters in your Edge Servers and that the default gateway is set only on the network adapter associated with the external interface.</span></span> <span data-ttu-id="32de1-113">Например, как показано на рисунке масштабируемой консолидированной пограничной стороны [, балансировка нагрузки DNS с общедоступными IP-адресами в Lync Server 2013](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md) , шлюз по умолчанию указывает на внешний брандмауэр.</span><span class="sxs-lookup"><span data-stu-id="32de1-113">For example, as shown in the Scaled Consolidated Edge Scenario figure in [Scaled consolidated edge, DNS load balancing with public IP addresses in Lync Server 2013](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md) , the default gateway would point to the external firewall.</span></span>

<span data-ttu-id="32de1-114">Настроить два сетевых адаптера на пограничном сервере можно следующим образом.</span><span class="sxs-lookup"><span data-stu-id="32de1-114">You can configure two network adapters in each of your Edge Server as follows:</span></span>

  - <span data-ttu-id="32de1-115">**Сетевой адаптер 1 — узел 1 (внутренний интерфейс).**</span><span class="sxs-lookup"><span data-stu-id="32de1-115">**Network adapter 1 - Node 1 (Internal Interface)**</span></span>
    
    <span data-ttu-id="32de1-116">Внутренний интерфейс с назначенным адресом 172.25.33.10.</span><span class="sxs-lookup"><span data-stu-id="32de1-116">Internal interface with 172.25.33.10 assigned.</span></span>
    
    <span data-ttu-id="32de1-117">Шлюз по умолчанию не задан.</span><span class="sxs-lookup"><span data-stu-id="32de1-117">No default gateway is defined.</span></span>
    
    <span data-ttu-id="32de1-118">Убедитесь, что существует маршрут от сети, содержащей внутренний пограничный интерфейс, в любые сети, содержащие серверы, на которых работают клиенты Lync Server 2013 или Lync Server 2013 (например, из 172.25.33.0 в 192.168.10.0).</span><span class="sxs-lookup"><span data-stu-id="32de1-118">Ensure that there is a route from the network containing the Edge internal interface to any networks that contain servers running Lync Server 2013 or Lync Server 2013 clients (for example, from 172.25.33.0 to 192.168.10.0).</span></span>

  - <span data-ttu-id="32de1-119">**Сетевой адаптер 1 — узел 2 (внутренний интерфейс).**</span><span class="sxs-lookup"><span data-stu-id="32de1-119">**Network adapter 1 - Node 2 (Internal Interface)**</span></span>
    
    <span data-ttu-id="32de1-120">Назначается внутренний интерфейс с IP-адресом 172.25.33.11.</span><span class="sxs-lookup"><span data-stu-id="32de1-120">Internal interface with 172.25.33.11 assigned.</span></span>
    
    <span data-ttu-id="32de1-121">Не задается никакой шлюз по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="32de1-121">No default gateway is defined.</span></span>
    
    <span data-ttu-id="32de1-122">Убедитесь, что существует маршрут от сети, содержащей внутренний пограничный интерфейс, в любые сети, содержащие серверы, на которых работают клиенты Lync Server 2013 или Lync Server 2013 (например, из 172.25.33.0 в 192.168.10.0).</span><span class="sxs-lookup"><span data-stu-id="32de1-122">Ensure that there is a route from the network containing the Edge internal interface to any networks that contain servers running Lync Server 2013 or Lync Server 2013 clients (for example, from 172.25.33.0 to 192.168.10.0).</span></span>

  - <span data-ttu-id="32de1-123">**Сетевой адаптер 2 — узел 1 (внешний интерфейс).**</span><span class="sxs-lookup"><span data-stu-id="32de1-123">**Network adapter 2 Node 1 (External Interface)**</span></span>
    
    <span data-ttu-id="32de1-124">Этому сетевому адаптеру назначаются три частных IP-адреса, например 131.107.155.10 для пограничной службы доступа, 131.107.155.20 для пограничной службы веб-конференций, 131.107.155.30 для пограничной службы аудио-и видеоконференций.</span><span class="sxs-lookup"><span data-stu-id="32de1-124">Three private IP addresses are assigned to this network adapter, for example 131.107.155.10 for Access Edge service, 131.107.155.20 for Web Conferencing Edge service, 131.107.155.30 for A/V Edge service.</span></span>
    
    <span data-ttu-id="32de1-125">Общедоступный IP-адрес службы пограничной службы доступа является основным для шлюза по умолчанию, установленного на общедоступном маршрутизаторе (131.107.155.1).</span><span class="sxs-lookup"><span data-stu-id="32de1-125">The Access Edge service public IP address is primary with default gateway set to the public router (131.107.155.1).</span></span>
    
    <span data-ttu-id="32de1-126">Пограничная служба веб-конференций и частные IP-адреса пограничных служб аудио-и видеосвязи являются дополнительными IP-адресами в разделе **Дополнительные** свойства **протокола Интернета версии 4 (TCP/IPv4)** и **протокола IP версии 6 (TCP/IPv6)** **Свойства подключения по локальной сети в свойствах подключения по локальной сети** в Windows Server.</span><span class="sxs-lookup"><span data-stu-id="32de1-126">Web Conferencing Edge service and A/V Edge service private IP addresses are additional IP addresses in the **Advanced** section of the properties of **Internet Protocol Version 4 (TCP/IPv4)** and **Internet Protocol Version 6 (TCP/IPv6)** of the **Local Area Connection Properties** in Windows Server.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="32de1-127">Для всех 3 интерфейсов пограничной службы можно использовать один IP-адрес, однако это не рекомендуется.</span><span class="sxs-lookup"><span data-stu-id="32de1-127">It is possible, though not recommended, to use a single IP address for all three Edge service interfaces.</span></span> <span data-ttu-id="32de1-128">Несмотря на экономию IP-адресов, в этом случае также потребуется 3 различных номера порта для каждой службы.</span><span class="sxs-lookup"><span data-stu-id="32de1-128">Though this does save IP addresses, it requires different port numbers for each service.</span></span> <span data-ttu-id="32de1-129">По умолчанию используется TCP-порт 443, который гарантирует, что большинство удаленных брандмауэров будут разрешать трафик.</span><span class="sxs-lookup"><span data-stu-id="32de1-129">The default port number is 443/TCP, which ensures that most remote firewalls will allow the traffic.</span></span> <span data-ttu-id="32de1-130">Изменение значений порта (например,) 5061/TCP для службы пограничного сервера доступа, 444/TCP для пограничной службы веб-конференций и 443/TCP для пограничной службы аудио-и видеосвязи может привести к проблемам с удаленными пользователями, в которых брандмауэр не разрешает трафик через 5061/TCP и 444/TCP.</span><span class="sxs-lookup"><span data-stu-id="32de1-130">Changing the port values to (for example) 5061/TCP for the Access Edge service, 444/TCP for the Web Conferencing Edge service and 443/TCP for the A/V Edge service might cause problems for remote users where a firewall that they are behind does not allow the traffic over 5061/TCP and 444/TCP.</span></span> <span data-ttu-id="32de1-131">Кроме того, использование трех определенных IP-адресов упрощает устранение неполадок, благодаря возможности фильтрации на IP-адресе.</span><span class="sxs-lookup"><span data-stu-id="32de1-131">Additionally, three distinct IP addresses makes troubleshooting easier due to being able to filter on IP address.</span></span>

    
    </div>

  - <span data-ttu-id="32de1-132">**Сетевой адаптер 2 — узел 2 (внешний интерфейс)**</span><span class="sxs-lookup"><span data-stu-id="32de1-132">**Network adapter 2 Node 2 (External Interface)**</span></span>
    
    <span data-ttu-id="32de1-133">Этому сетевому адаптеру назначаются три частных IP-адреса, например 131.107.155.11 для пограничной службы доступа, 131.107.155.21 для пограничной службы веб-конференций, 131.107.155.31 для пограничной службы аудио-и видеоконференций.</span><span class="sxs-lookup"><span data-stu-id="32de1-133">Three private IP addresses are assigned to this network adapter, for example 131.107.155.11 for Access Edge service, 131.107.155.21 for Web Conferencing Edge service, 131.107.155.31 for A/V Edge service.</span></span>
    
    <span data-ttu-id="32de1-134">Общедоступный IP-адрес службы пограничной службы доступа является основным для шлюза по умолчанию, установленного на общедоступном маршрутизаторе (131.107.155.1).</span><span class="sxs-lookup"><span data-stu-id="32de1-134">The Access Edge service public IP address is primary with default gateway set to the public router (131.107.155.1).</span></span>
    
    <span data-ttu-id="32de1-135">Пограничная служба веб-конференций и частные IP-адреса пограничных служб аудио-и видеосвязи являются дополнительными IP-адресами в разделе **Дополнительные** свойства **протокола Интернета версии 4 (TCP/IPv4)** и **протокола IP версии 6 (TCP/IPv6)** **Свойства подключения по локальной сети в свойствах подключения по локальной сети** в Windows Server.</span><span class="sxs-lookup"><span data-stu-id="32de1-135">Web Conferencing Edge service and A/V Edge service private IP addresses are additional IP addresses in the **Advanced** section of the properties of **Internet Protocol Version 4 (TCP/IPv4)** and **Internet Protocol Version 6 (TCP/IPv6)** of the **Local Area Connection Properties** in Windows Server.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="32de1-136">Для настройки пограничного сервера с двумя сетевыми адаптерами можно выбрать один из двух вариантов.</span><span class="sxs-lookup"><span data-stu-id="32de1-136">Configuring the Edge Server with two network adapters is one of two options.</span></span> <span data-ttu-id="32de1-137">Другой вариант — использовать один сетевой адаптер для внутренней стороны и три сетевых адаптера для внешней стороны пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="32de1-137">The other option is to use one network adapter for the internal side and three network adapters for the external side of the Edge Server.</span></span> <span data-ttu-id="32de1-138">Основным преимуществом этого варианта является отдельный сетевой адаптер для каждой службы пограничного сервера и потенциально более краткий сбор данных, когда требуется устранение неполадок</span><span class="sxs-lookup"><span data-stu-id="32de1-138">The main benefit of this option is a distinct network adapter per Edge Server service, and potentially more concise data collection when troubleshooting is necessary</span></span>



</div>

### <a name="dns-records-required-for-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses-example"></a><span data-ttu-id="32de1-139">Записи DNS, необходимые для масштабируемого консолидированного пограничного сервера, балансировка нагрузки DNS с общими IP-адресами (пример)</span><span class="sxs-lookup"><span data-stu-id="32de1-139">DNS Records Required for Scaled Consolidated Edge, DNS Load Balancing with Public IP Addresses (Example)</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="32de1-140">Расположение/тип/порт</span><span class="sxs-lookup"><span data-stu-id="32de1-140">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="32de1-141">Полное доменное имя/Запись DNS</span><span class="sxs-lookup"><span data-stu-id="32de1-141">FQDN/DNS Record</span></span></th>
<th><span data-ttu-id="32de1-142">IP-адрес/Полное доменное имя</span><span class="sxs-lookup"><span data-stu-id="32de1-142">IP Address/FQDN</span></span></th>
<th><span data-ttu-id="32de1-143">Сопоставление с/Примечания</span><span class="sxs-lookup"><span data-stu-id="32de1-143">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="32de1-144">Внешняя запись DNS/A</span><span class="sxs-lookup"><span data-stu-id="32de1-144">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="32de1-145">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="32de1-145">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="32de1-146">131.107.155.10 и 131.107.155.11</span><span class="sxs-lookup"><span data-stu-id="32de1-146">131.107.155.10 and 131.107.155.11</span></span></p></td>
<td><p><span data-ttu-id="32de1-147">Внешний интерфейс службы пограничной службы доступа (Contoso) повторяется по мере необходимости для всех доменов SIP с пользователями, поддерживающими Lync</span><span class="sxs-lookup"><span data-stu-id="32de1-147">Access Edge service external interface (Contoso) Repeat as necessary for all SIP domains with Lync enabled users</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="32de1-148">Внешняя запись DNS/A</span><span class="sxs-lookup"><span data-stu-id="32de1-148">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="32de1-149">webcon.contoso.com</span><span class="sxs-lookup"><span data-stu-id="32de1-149">webcon.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="32de1-150">131.107.155.20 и 131.107.155.21</span><span class="sxs-lookup"><span data-stu-id="32de1-150">131.107.155.20 and 131.107.155.21</span></span></p></td>
<td><p><span data-ttu-id="32de1-151">Внешний интерфейс пограничной службы веб-конференций</span><span class="sxs-lookup"><span data-stu-id="32de1-151">Web Conferencing Edge service external interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="32de1-152">Внешняя запись DNS/A</span><span class="sxs-lookup"><span data-stu-id="32de1-152">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="32de1-153">av.contoso.com</span><span class="sxs-lookup"><span data-stu-id="32de1-153">av.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="32de1-154">131.107.155.30 и 131.107.155.31</span><span class="sxs-lookup"><span data-stu-id="32de1-154">131.107.155.30 and 131.107.155.31</span></span></p></td>
<td><p><span data-ttu-id="32de1-155">Внешний интерфейс пограничной службы аудио-и видеоданных</span><span class="sxs-lookup"><span data-stu-id="32de1-155">A/V Edge service external interface</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="32de1-156">Внешний DNS/SRV/443</span><span class="sxs-lookup"><span data-stu-id="32de1-156">External DNS/SRV/443</span></span></p></td>
<td><p><span data-ttu-id="32de1-157">_sip. _tls. contoso. com</span><span class="sxs-lookup"><span data-stu-id="32de1-157">_sip._tls.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="32de1-158">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="32de1-158">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="32de1-159">Внешний интерфейс службы пограничного доступа.</span><span class="sxs-lookup"><span data-stu-id="32de1-159">Access Edge service external interface.</span></span> <span data-ttu-id="32de1-160">Требуется для автоматической настройки клиентов Lync 2013 и Lync 2010 для работы с внешними клиентами.</span><span class="sxs-lookup"><span data-stu-id="32de1-160">Required for automatic configuration of Lync 2013 and Lync 2010 clients to work externally.</span></span> <span data-ttu-id="32de1-161">Повторить по мере необходимости для всех доменов SIP с пользователями, которым разрешен Lync.</span><span class="sxs-lookup"><span data-stu-id="32de1-161">Repeat as necessary for all SIP domains with Lync enabled users.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="32de1-162">Внешний DNS/SRV/5061</span><span class="sxs-lookup"><span data-stu-id="32de1-162">External DNS/SRV/5061</span></span></p></td>
<td><p><span data-ttu-id="32de1-163">_sipfederationtls. _tcp. contoso. com</span><span class="sxs-lookup"><span data-stu-id="32de1-163">_sipfederationtls._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="32de1-164">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="32de1-164">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="32de1-165">Внешний интерфейс службы пограничного сервера доступа, необходимый для автоматического обнаружения DNS федеративных партнеров, известных как "разрешенный домен SIP" (под названием Расширенная Федерация в предыдущих выпусках).</span><span class="sxs-lookup"><span data-stu-id="32de1-165">Access Edge service external interface Required for automatic DNS discovery of federated partners known as “Allowed SIP Domain” (called enhanced federation in previous releases).</span></span> <span data-ttu-id="32de1-166">Повторить по мере необходимости для всех доменов SIP с пользователями, которым разрешен Lync.</span><span class="sxs-lookup"><span data-stu-id="32de1-166">Repeat as necessary for all SIP domains with Lync enabled users</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="32de1-167">Внутренняя DNS/A</span><span class="sxs-lookup"><span data-stu-id="32de1-167">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="32de1-168">lsedge.contoso.net</span><span class="sxs-lookup"><span data-stu-id="32de1-168">lsedge.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="32de1-169">172.25.33.10 и 172.25.33.11</span><span class="sxs-lookup"><span data-stu-id="32de1-169">172.25.33.10 and 172.25.33.11</span></span></p></td>
<td><p><span data-ttu-id="32de1-170">Внутренний интерфейс консолидированного пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="32de1-170">Consolidated Edge internal interface</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="records-required-for-federation"></a><span data-ttu-id="32de1-171">Записи, необходимые для создания федерации</span><span class="sxs-lookup"><span data-stu-id="32de1-171">Records Required for Federation</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="32de1-172">Расположение/тип/порт</span><span class="sxs-lookup"><span data-stu-id="32de1-172">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="32de1-173">FQDN</span><span class="sxs-lookup"><span data-stu-id="32de1-173">FQDN</span></span></th>
<th><span data-ttu-id="32de1-174">IP-адрес/запись узла полного доменного имени</span><span class="sxs-lookup"><span data-stu-id="32de1-174">IP address/FQDN host record</span></span></th>
<th><span data-ttu-id="32de1-175">Сопоставление/комментарии</span><span class="sxs-lookup"><span data-stu-id="32de1-175">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="32de1-176">Внешний DNS/SRV/5061</span><span class="sxs-lookup"><span data-stu-id="32de1-176">External DNS/SRV/5061</span></span></p></td>
<td><p><span data-ttu-id="32de1-177">_sipfederationtls. _tcp. contoso. com</span><span class="sxs-lookup"><span data-stu-id="32de1-177">_sipfederationtls._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="32de1-178">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="32de1-178">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="32de1-179">Внешний интерфейс службы пограничного доступа SIP, необходимый для автоматического обнаружения DNS для Федерации другим потенциальным партнерам Федерации, а также называется "разрешенные домены SIP" (называемые расширенной Федерацию в предыдущих выпусках).</span><span class="sxs-lookup"><span data-stu-id="32de1-179">SIP Access Edge service external interface Required for automatic DNS discovery of your federation to other potential federation partners, and is known as “Allowed SIP Domains” (called enhanced federation in previous releases).</span></span></p>
<div>

> [!IMPORTANT]  
> <span data-ttu-id="32de1-180">Повторите эти действия для всех доменов SIP с пользователями Lync с поддержкой Lync и клиентами Microsoft Lync Mobile, которые используют службу push-уведомлений или службу push-уведомлений Apple.</span><span class="sxs-lookup"><span data-stu-id="32de1-180">Repeat as necessary for all SIP domains with Lync enabled users and Microsoft Lync Mobile clients that use either the Push Notification Service or the Apple Push Notification service</span></span>


</div></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="dns-summary-for-extensible-messaging-and-presence-protocol"></a><span data-ttu-id="32de1-181">Сводка по DNS для расширяемого протокола XMPP</span><span class="sxs-lookup"><span data-stu-id="32de1-181">DNS Summary for Extensible Messaging and Presence Protocol</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="32de1-182">Расположение/тип/порт</span><span class="sxs-lookup"><span data-stu-id="32de1-182">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="32de1-183">FQDN</span><span class="sxs-lookup"><span data-stu-id="32de1-183">FQDN</span></span></th>
<th><span data-ttu-id="32de1-184">IP-адрес/запись узла полного доменного имени</span><span class="sxs-lookup"><span data-stu-id="32de1-184">IP address/FQDN host record</span></span></th>
<th><span data-ttu-id="32de1-185">Сопоставление/комментарии</span><span class="sxs-lookup"><span data-stu-id="32de1-185">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="32de1-186">Внешний DNS/SRV/5269</span><span class="sxs-lookup"><span data-stu-id="32de1-186">External DNS/SRV/5269</span></span></p></td>
<td><p><span data-ttu-id="32de1-187">_xmpp-Server. _tcp. contoso. com</span><span class="sxs-lookup"><span data-stu-id="32de1-187">_xmpp-server._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="32de1-188">xmpp.contoso.com</span><span class="sxs-lookup"><span data-stu-id="32de1-188">xmpp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="32de1-189">Внешний интерфейс прокси-сервера XMPP в пограничной службе доступа или пограничном пуле. При необходимости повторите эти действия для всех внутренних доменов SIP с пользователями Lync, в которых доступ к контактам с контактами XMPP разрешен через конфигурацию политики внешнего доступа через глобальную политику, политику сайта, в которой находится пользователь, или политика пользователей, применяемая к Пользователь с поддержкой Lync.</span><span class="sxs-lookup"><span data-stu-id="32de1-189">XMPP proxy external interface on the Access Edge service or Edge pool.Repeat as necessary for all internal SIP domains with Lync enabled users where contact with XMPP contacts is allowed through the configuration of the External Access Policy through a global policy, site policy where the user is located, or user policy applied to the Lync-enabled user.</span></span> <span data-ttu-id="32de1-190">Разрешенный домен XMPP также должен быть настроен в политике федеративных партнеров XMPP.</span><span class="sxs-lookup"><span data-stu-id="32de1-190">An allowed XMPP domain must also be configured in the XMPP Federated Partners policy.</span></span> <span data-ttu-id="32de1-191">Дополнительные сведения можно найти в разделах, <strong>приведенных в разделе</strong> .</span><span class="sxs-lookup"><span data-stu-id="32de1-191">See topics in <strong>See Also</strong> for additional details</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="32de1-192">Внешний DNS/A</span><span class="sxs-lookup"><span data-stu-id="32de1-192">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="32de1-193">xmpp.contoso.com (пример)</span><span class="sxs-lookup"><span data-stu-id="32de1-193">xmpp.contoso.com (for example)</span></span></p></td>
<td><p><span data-ttu-id="32de1-194">IP-адрес пограничной службы доступа на пограничном сервере или пограничном пуле, где размещен прокси-сервер XMPP</span><span class="sxs-lookup"><span data-stu-id="32de1-194">IP address of Access Edge service on your Edge Server or Edge pool hosting XMPP proxy</span></span></p></td>
<td><p><span data-ttu-id="32de1-195">Указывает на пограничный сервер доступа или пограничный пул, на котором размещается прокси-служба XMPP.</span><span class="sxs-lookup"><span data-stu-id="32de1-195">Points to the Access Edge service or Edge pool that hosts the XMPP proxy service.</span></span> <span data-ttu-id="32de1-196">Как правило, созданная запись SRV указывает на эту запись узла (A или AAAA).</span><span class="sxs-lookup"><span data-stu-id="32de1-196">Typically, the SRV record that you create will point to this host (A or AAAA) record</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

