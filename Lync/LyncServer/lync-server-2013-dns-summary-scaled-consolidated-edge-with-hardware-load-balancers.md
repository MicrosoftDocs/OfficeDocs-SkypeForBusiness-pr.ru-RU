---
title: Сводка по DNS — масштабируемая консолидированная пограничная система с аппаратными подсистемами балансировки нагрузки
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
ms.openlocfilehash: c45802282c57ebcf80fbc55b030c985fe7d977cd
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137808"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="dns-summary---scaled-consolidated-edge-with-hardware-load-balancers-in-lync-server-2013"></a><span data-ttu-id="94144-102">Сводка по DNS — масштабируемая консолидированная пограничная система с аппаратными подсистемами балансировки нагрузки в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="94144-102">DNS summary - Scaled consolidated edge with hardware load balancers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="94144-103">_**Последнее изменение темы:** 2013-01-27_</span><span class="sxs-lookup"><span data-stu-id="94144-103">_**Topic Last Modified:** 2013-01-27_</span></span>

<span data-ttu-id="94144-104">Требования к записям DNS для удаленного доступа к Lync Server 2013 довольно просты по сравнению с сертификатами и портами.</span><span class="sxs-lookup"><span data-stu-id="94144-104">DNS record requirements for remote access to Lync Server 2013 are fairly straightforward compared to those for certificates and ports.</span></span> <span data-ttu-id="94144-105">Кроме того, многие записи являются необязательными в зависимости от того, как вы настраиваете клиенты, на которых работает Lync 2013, и включена ли Федерация.</span><span class="sxs-lookup"><span data-stu-id="94144-105">Also, many records are optional, depending on how you configure clients running Lync 2013 and whether you enable federation.</span></span>

<span data-ttu-id="94144-106">Дополнительные сведения о требованиях к службе DNS для Lync 2013 приведены в статье [Определение требований DNS для Lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="94144-106">For details about Lync 2013 DNS requirements, see [Determine DNS requirements for Lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span></span>

<span data-ttu-id="94144-107">Для получения дополнительных сведений о настройке автоматической настройки клиентов Lync 2013 если DNS с разделением не настроена, ознакомьтесь с разделом "Автоматическая настройка без разделения DNS", чтобы [определить требования к DNS для Lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="94144-107">For details about configuring automatic configuration of Lync 2013 clients if split-brain DNS is not configured, see the "Automatic Configuration without Split Brain DNS" section in [Determine DNS requirements for Lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span></span>

<span data-ttu-id="94144-108">Следующая таблица содержит сводку записей DNS, необходимых для поддержки топологии масштабированной и консолидированной среды пограничных серверов (с аппаратной балансировкой нагрузки).</span><span class="sxs-lookup"><span data-stu-id="94144-108">The following table contains a summary of the DNS records that are required to support the Scaled Consolidated Edge Topology (Hardware Load Balanced) figure.</span></span> <span data-ttu-id="94144-109">Обратите внимание, что определенные записи DNS необходимы только для автоматической настройки для клиентов Lync.</span><span class="sxs-lookup"><span data-stu-id="94144-109">Note that certain DNS records are required only for automatic configuration for Lync clients.</span></span> <span data-ttu-id="94144-110">Если вы планируете использовать объекты групповой политики (GPO) для настройки клиентов Lync, связанные записи не нужны.</span><span class="sxs-lookup"><span data-stu-id="94144-110">If you plan to use group policy objects (GPOs) to configure Lync clients, the associated records are not necessary.</span></span>

<div>

## <a name="important-edge-server-network-adapter-requirements"></a><span data-ttu-id="94144-111">ВАЖНО! требования к сетевому адаптеру пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="94144-111">IMPORTANT: Edge Server Network Adapter Requirements</span></span>

<span data-ttu-id="94144-112">Чтобы избежать проблем с маршрутизацией, убедитесь, что в пограничных серверах есть по крайней мере два сетевых адаптера и что шлюз по умолчанию задан только на сетевом адаптере, связанном с внешним интерфейсом.</span><span class="sxs-lookup"><span data-stu-id="94144-112">To avoid routing issues, verify that there are at least two network adapters in your Edge Servers and that the default gateway is set only on the network adapter associated with the external interface.</span></span> <span data-ttu-id="94144-113">Например, как показано в масштабируемых консолидированных пограничных условиях, например, на [масштабируемой консолидированной границе с аппаратными подсистемами балансировки нагрузки в Lync Server 2013](lync-server-2013-scaled-consolidated-edge-with-hardware-load-balancers.md), шлюз по умолчанию указывает на внешний брандмауэр.</span><span class="sxs-lookup"><span data-stu-id="94144-113">For example, as shown in the Scaled Consolidated Edge Scenario figure in [Scaled consolidated edge with hardware load balancers in Lync Server 2013](lync-server-2013-scaled-consolidated-edge-with-hardware-load-balancers.md), the default gateway would point to the external firewall.</span></span>

<span data-ttu-id="94144-114">В каждом пограничных серверах можно настроить два сетевых адаптера следующим образом:</span><span class="sxs-lookup"><span data-stu-id="94144-114">You can configure two network adapters in each of your Edge Servers as follows:</span></span>

  - <span data-ttu-id="94144-115">**Сетевой адаптер 1 (внутренний интерфейс)**</span><span class="sxs-lookup"><span data-stu-id="94144-115">**Network adapter 1 (Internal Interface)**</span></span>
    
    <span data-ttu-id="94144-116">Внутренний интерфейс с назначенным адресом 172.25.33.10.</span><span class="sxs-lookup"><span data-stu-id="94144-116">Internal interface with 172.25.33.10 assigned.</span></span>
    
    <span data-ttu-id="94144-117">Шлюз по умолчанию не определен.</span><span class="sxs-lookup"><span data-stu-id="94144-117">No default gateway.</span></span>
    
    <span data-ttu-id="94144-118">Убедитесь, что существует маршрут от сети, содержащей внутренний интерфейс пограничного сервера, в любые сети, содержащие клиенты Lync Server или серверы Lync Server (например, из 172.25.33.0 в 192.168.10.0).</span><span class="sxs-lookup"><span data-stu-id="94144-118">Ensure there is a route from the network containing the Edge Server internal interface to any networks that contain Lync Server clients or servers running Lync Server (for example, from 172.25.33.0 to 192.168.10.0).</span></span>

  - <span data-ttu-id="94144-119">**Сетевой адаптер 2 (внешний интерфейс)**</span><span class="sxs-lookup"><span data-stu-id="94144-119">**Network adapter 2 (External Interface)**</span></span>
    
    <span data-ttu-id="94144-120">Этому сетевому адаптеру назначаются три общедоступных IP-адреса, например 131.107.155.10 для пограничной службы доступа, 131.107.155.20 для пограничной службы веб-конференций, 131.107.155.30 для пограничной службы аудио-и видеоконференций.</span><span class="sxs-lookup"><span data-stu-id="94144-120">Three public IP addresses are assigned to this network adapter, for example 131.107.155.10 for Access Edge service, 131.107.155.20 for Web Conferencing Edge service, 131.107.155.30 for A/V Edge service.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="94144-121">IP-адреса, назначенные реальным внешним сетевым интерфейсам пограничного сервера, могут зависеть от выбранного аппаратного балансировщика нагрузки.</span><span class="sxs-lookup"><span data-stu-id="94144-121">The IP addresses that are assigned to the actual external network interfaces of the Edge Server may depend on which hardware load balancer you choose.</span></span> <span data-ttu-id="94144-122">Чтобы узнать фактические требования к IP-адресам, обратитесь к документации по аппаратному подсистеме балансировки нагрузки.</span><span class="sxs-lookup"><span data-stu-id="94144-122">Refer to the documentation for your hardware load balancer to understand the actual IP address requirements.</span></span><BR><span data-ttu-id="94144-123">Для всех 3 интерфейсов пограничной службы можно использовать один IP-адрес, однако это не рекомендуется.</span><span class="sxs-lookup"><span data-stu-id="94144-123">It is possible, though not recommended, to use a single IP address for all three Edge service interfaces.</span></span> <span data-ttu-id="94144-124">Несмотря на экономию IP-адресов, в этом случае также потребуется 3 различных номера порта для каждой службы.</span><span class="sxs-lookup"><span data-stu-id="94144-124">Though this does save IP addresses, it requires different port numbers for each service.</span></span> <span data-ttu-id="94144-125">По умолчанию используется TCP-порт 443, который гарантирует, что большинство удаленных брандмауэров будут разрешать трафик.</span><span class="sxs-lookup"><span data-stu-id="94144-125">The default port number is 443/TCP, which ensures that most remote firewalls will allow the traffic.</span></span> <span data-ttu-id="94144-126">Изменение значений порта (например,) 5061/TCP для службы пограничного сервера доступа, 444/TCP для пограничной службы веб-конференций и 443/TCP для пограничной службы аудио-и видеосвязи может привести к проблемам с удаленными пользователями, в которых брандмауэр не разрешает трафик через 5061/TCP и 444/TCP.</span><span class="sxs-lookup"><span data-stu-id="94144-126">Changing the port values to (for example) 5061/TCP for the Access Edge service, 444/TCP for the Web Conferencing Edge service and 443/TCP for the A/V Edge service might cause problems for remote users where a firewall that they are behind does not allow the traffic over 5061/TCP and 444/TCP.</span></span> <span data-ttu-id="94144-127">Кроме того, 3 отдельных IP-адреса упрощают устранение неполадок, поскольку позволяют выполнять фильтрацию по IP-адресу.</span><span class="sxs-lookup"><span data-stu-id="94144-127">Additionally, three distinct IP addresses makes troubleshooting easier due to being able to filter on IP address.</span></span>

    
    </div>
    
    <span data-ttu-id="94144-128">IP-адрес пограничного сервера доступа является основным для шлюза по умолчанию, установленного на маршрутизатор, подключенный к Интернету (131.107.155.1).</span><span class="sxs-lookup"><span data-stu-id="94144-128">Access Edge service IP address is primary with default gateway set to Internet-facing router (131.107.155.1).</span></span>
    
    <span data-ttu-id="94144-129">Пограничная служба веб-конференций и IP-адреса пограничной службы аудио-и видеоданных.</span><span class="sxs-lookup"><span data-stu-id="94144-129">Web Conferencing Edge service and A/V Edge service IP addresses secondary.</span></span>

<div>


> [!TIP]
> <span data-ttu-id="94144-130">Для настройки пограничного сервера с двумя сетевыми адаптерами можно выбрать один из двух вариантов.</span><span class="sxs-lookup"><span data-stu-id="94144-130">Configuring the Edge Server with two network adapters is one of two options.</span></span> <span data-ttu-id="94144-131">Другой вариант — использовать один сетевой адаптер для внутренней стороны и три сетевых адаптера для внешней стороны пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="94144-131">The other option is to use one network adapter for the internal side and three network adapters for the external side of the Edge Server.</span></span> <span data-ttu-id="94144-132">Основным преимуществом этого варианта является отдельный сетевой адаптер для каждой службы пограничного сервера и потенциально более краткий сбор данных, когда требуется устранение неполадок</span><span class="sxs-lookup"><span data-stu-id="94144-132">The main benefit of this option is a distinct network adapter per Edge Server service, and potentially more concise data collection when troubleshooting is necessary</span></span>



</div>

### <a name="dns-records-required-for-scaled-consolidated-edge-hardware-load-balanced-example"></a><span data-ttu-id="94144-133">Записи DNS, необходимые для масштабированной и консолидированной среды пограничных серверов с аппаратной балансировкой нагрузки (пример)</span><span class="sxs-lookup"><span data-stu-id="94144-133">DNS Records Required for Scaled Consolidated Edge, Hardware Load Balanced (Example)</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="94144-134">Расположение/тип/порт</span><span class="sxs-lookup"><span data-stu-id="94144-134">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="94144-135">Полное доменное имя/Запись DNS</span><span class="sxs-lookup"><span data-stu-id="94144-135">FQDN/DNS Record</span></span></th>
<th><span data-ttu-id="94144-136">IP-адрес/Полное доменное имя</span><span class="sxs-lookup"><span data-stu-id="94144-136">IP Address/FQDN</span></span></th>
<th><span data-ttu-id="94144-137">Сопоставление с/Примечания</span><span class="sxs-lookup"><span data-stu-id="94144-137">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="94144-138">Внешний DNS/A</span><span class="sxs-lookup"><span data-stu-id="94144-138">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="94144-139">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="94144-139">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="94144-140">131.107.155.10</span><span class="sxs-lookup"><span data-stu-id="94144-140">131.107.155.10</span></span></p></td>
<td><p><span data-ttu-id="94144-141">Внешний интерфейс службы пограничного доступа (Contoso).</span><span class="sxs-lookup"><span data-stu-id="94144-141">Access Edge service external interface (Contoso).</span></span> <span data-ttu-id="94144-142">Повторить по мере необходимости для всех доменов SIP с пользователями, которым разрешен Lync.</span><span class="sxs-lookup"><span data-stu-id="94144-142">Repeat as necessary for all SIP domains with Lync enabled users</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="94144-143">Внешняя запись DNS/A</span><span class="sxs-lookup"><span data-stu-id="94144-143">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="94144-144">webcon.contoso.com</span><span class="sxs-lookup"><span data-stu-id="94144-144">webcon.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="94144-145">131.107.155.20</span><span class="sxs-lookup"><span data-stu-id="94144-145">131.107.155.20</span></span></p></td>
<td><p><span data-ttu-id="94144-146">Внешний интерфейс пограничной службы веб-конференций</span><span class="sxs-lookup"><span data-stu-id="94144-146">Web Conferencing Edge service external interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="94144-147">Внешняя запись DNS/A</span><span class="sxs-lookup"><span data-stu-id="94144-147">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="94144-148">av.contoso.com</span><span class="sxs-lookup"><span data-stu-id="94144-148">av.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="94144-149">131.107.155.30</span><span class="sxs-lookup"><span data-stu-id="94144-149">131.107.155.30</span></span></p></td>
<td><p><span data-ttu-id="94144-150">Внешний интерфейс пограничной службы аудио-и видеоданных</span><span class="sxs-lookup"><span data-stu-id="94144-150">A/V Edge service external interface</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="94144-151">Внешний DNS/SRV/443</span><span class="sxs-lookup"><span data-stu-id="94144-151">External DNS/SRV/443</span></span></p></td>
<td><p><span data-ttu-id="94144-152">_sip. _tls. contoso. com</span><span class="sxs-lookup"><span data-stu-id="94144-152">_sip._tls.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="94144-153">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="94144-153">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="94144-154">Внешний интерфейс службы пограничного доступа.</span><span class="sxs-lookup"><span data-stu-id="94144-154">Access Edge service external interface.</span></span> <span data-ttu-id="94144-155">Требуется для автоматической настройки клиентов Lync 2013 и Lync 2010 для работы с внешними клиентами.</span><span class="sxs-lookup"><span data-stu-id="94144-155">Required for automatic configuration of Lync 2013 and Lync 2010 clients to work externally.</span></span> <span data-ttu-id="94144-156">Повторить по мере необходимости для всех доменов SIP с пользователями, которым разрешен Lync.</span><span class="sxs-lookup"><span data-stu-id="94144-156">Repeat as necessary for all SIP domains with Lync enabled users.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="94144-157">Внешняя DNS/SRV/5061</span><span class="sxs-lookup"><span data-stu-id="94144-157">External DNS/SRV/5061</span></span></p></td>
<td><p><span data-ttu-id="94144-158">_sipfederationtls. _tcp. contoso. com</span><span class="sxs-lookup"><span data-stu-id="94144-158">_sipfederationtls._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="94144-159">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="94144-159">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="94144-160">Внешний интерфейс службы доступа SIP Внешний интерфейс, необходимый для автоматического обнаружения DNS федеративных партнеров, известных как "разрешенный домен SIP" (под названием Расширенная Федерация в предыдущих выпусках).</span><span class="sxs-lookup"><span data-stu-id="94144-160">SIP Access Edge service external interface Required for automatic DNS discovery of federated partners known as “Allowed SIP Domain” (called enhanced federation in previous releases).</span></span> <span data-ttu-id="94144-161">Повторите эти действия для всех доменов SIP с пользователями Lync с поддержкой Lync и клиентами Microsoft Lync Mobile, которые используют службу push-уведомлений или службу push-уведомлений Apple.</span><span class="sxs-lookup"><span data-stu-id="94144-161">Repeat as necessary for all SIP domains with Lync enabled users and Microsoft Lync Mobile clients that use either the Push Notification Service or the Apple Push Notification service</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="94144-162">Внутренняя запись DNS/A</span><span class="sxs-lookup"><span data-stu-id="94144-162">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="94144-163">lsedge.contoso.net</span><span class="sxs-lookup"><span data-stu-id="94144-163">lsedge.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="94144-164">172.25.33.10</span><span class="sxs-lookup"><span data-stu-id="94144-164">172.25.33.10</span></span></p></td>
<td><p><span data-ttu-id="94144-165">Внутренний консолидированный интерфейс пограничной службы.</span><span class="sxs-lookup"><span data-stu-id="94144-165">Consolidated Edge internal interface</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

