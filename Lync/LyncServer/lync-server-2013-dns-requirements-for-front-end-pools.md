---
title: 'Lync Server 2013: требования к DNS для пулов интерфейсов с внешним интерфейсом'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: DNS requirements for Front End pools
ms:assetid: ba28919c-fbbe-4c54-8bf9-2b0cd3fa39c7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412910(v=OCS.15)
ms:contentKeyID: 48185228
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 03759267ea10a4eaf7046fd25390b45265e479f6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834368"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-requirements-for-front-end-pools-in-lync-server-2013"></a><span data-ttu-id="28543-102">Требования к DNS для пулов интерфейсов на сервере Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="28543-102">DNS requirements for Front End pools in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="28543-103">_**Тема последнего изменения:** 2012-11-07_</span><span class="sxs-lookup"><span data-stu-id="28543-103">_**Topic Last Modified:** 2012-11-07_</span></span>

<span data-ttu-id="28543-104">В этом разделе описаны записи DNS, необходимые для развертывания интерфейсных пулов переднего плана.</span><span class="sxs-lookup"><span data-stu-id="28543-104">This section describes the Domain Name System (DNS) records that are required for deployment of Front End pools.</span></span>

<div>

## <a name="dns-records-for-front-end-pools"></a><span data-ttu-id="28543-105">Записи DNS для пулов интерфейсов с внешним интерфейсом</span><span class="sxs-lookup"><span data-stu-id="28543-105">DNS Records for Front End Pools</span></span>

<span data-ttu-id="28543-106">В приведенной ниже таблице указаны требования к DNS для развертывания пула внешних интерфейсов Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="28543-106">The following table specifies DNS requirements for a Lync Server 2013 Front End pool deployment.</span></span>

### <a name="dns-requirements-for-a-front-end-pool"></a><span data-ttu-id="28543-107">Требования к службе DNS для пула переднего плана</span><span class="sxs-lookup"><span data-stu-id="28543-107">DNS Requirements for a Front End Pool</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="28543-108">Сценарий развертывания</span><span class="sxs-lookup"><span data-stu-id="28543-108">Deployment scenario</span></span></th>
<th><span data-ttu-id="28543-109">Требование DNS</span><span class="sxs-lookup"><span data-stu-id="28543-109">DNS requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="28543-110">Пул переднего плана с несколькими серверами переднего плана и балансировщик нагрузки оборудования (независимо от того, развернута ли балансировка нагрузки DNS для этого пула)</span><span class="sxs-lookup"><span data-stu-id="28543-110">Front End pool with multiple Front End Servers and a hardware load balancer (whether or not DNS load balancing is also deployed on that pool)</span></span></p></td>
<td><p><span data-ttu-id="28543-111">При использовании балансировки нагрузки DNS и балансировщика аппаратной подсистемы балансировки нагрузки необходимо размещать записи (A).</span><span class="sxs-lookup"><span data-stu-id="28543-111">When using both DNS load balancing and a hardware load balancer, you need to Host (A) records.</span></span> <span data-ttu-id="28543-112">Создание внутренней записи, которая позволяет устранить полное доменное имя (FQDN) для пула балансировки нагрузки DNS на интерфейсе переднего плана.</span><span class="sxs-lookup"><span data-stu-id="28543-112">Create an internal A record that resolves the fully qualified domain name (FQDN) of the Front End pool for DNS load balancing.</span></span> <span data-ttu-id="28543-113">Создайте запись внутренних узлов (A) для внутренних веб-служб в виртуальный IP-адрес подсистемы балансировки нагрузки.</span><span class="sxs-lookup"><span data-stu-id="28543-113">Create an internal host (A) record for the internal Web services to the virtual IP (VIP) address of the load balancer.</span></span> <span data-ttu-id="28543-114">Необходимо использовать внутреннее имя веб-службы, как оно определено в построителе топологии.</span><span class="sxs-lookup"><span data-stu-id="28543-114">You must use the internal Web services name as defined in Topology Builder.</span></span></p>
<p><span data-ttu-id="28543-115">Например, если вы используете балансировку нагрузки DNS и аппаратную балансировку нагрузки, у вас должна быть запись для каждого сервера переднего плана в пуле для балансировки нагрузки DNS, а также запись для внутренних веб-служб, указывающая на виртуальный IP-адрес подсистемы балансировки нагрузки оборудования. :</span><span class="sxs-lookup"><span data-stu-id="28543-115">For example, if you use both DNS load balancing and hardware load balancing, you would have an A record for each Front End Server in a pool for DNS load balancing, and an A record for the internal Web services pointing to the virtual IP of the hardware load balancer:</span></span></p>
<ul>
<li><p><span data-ttu-id="28543-116">Балансировка нагрузки DNS: Pool01.contoso.net IP-адрес 10.10.10.5 пула</span><span class="sxs-lookup"><span data-stu-id="28543-116">DNS load balancing:   Pool01.contoso.net   IP Address of pool   10.10.10.5</span></span></p>
<div>

> [!WARNING]  
> <span data-ttu-id="28543-117">На каждом сервере переднего плана также будет определена запись, отличная от A.</span><span class="sxs-lookup"><span data-stu-id="28543-117">Each Front End Server will also have a distinct A record:</span></span>


</div>
<ol>
<li><p><span data-ttu-id="28543-118">FE01.contoso.net 10.10.10.1</span><span class="sxs-lookup"><span data-stu-id="28543-118">FE01.contoso.net    10.10.10.1</span></span></p></li>
<li><p><span data-ttu-id="28543-119">FE02.contoso.net 10.10.10.2</span><span class="sxs-lookup"><span data-stu-id="28543-119">FE02.contoso.net    10.10.10.2</span></span></p></li>
<li><p><span data-ttu-id="28543-120">FE03.contoso.net 10.10.10.3</span><span class="sxs-lookup"><span data-stu-id="28543-120">FE03.contoso.net    10.10.10.3</span></span></p></li>
<li><p><span data-ttu-id="28543-121">FE04.contoso.net 10.10.10.4</span><span class="sxs-lookup"><span data-stu-id="28543-121">FE04.contoso.net    10.10.10.4</span></span></p></li>
</ol></li>
<li><p><span data-ttu-id="28543-122">Балансировка нагрузки оборудования: WebInternal.contoso.net IP-адрес ХЛБ VIP 192.168.10.5</span><span class="sxs-lookup"><span data-stu-id="28543-122">Hardware load balancing:   WebInternal.contoso.net   IP Address of HLB VIP   192.168.10.5</span></span></p></li>
</ul>
<p><span data-ttu-id="28543-123">Весь трафик, за исключением трафика HTTP/HTTPS, будет использовать запись Pool01.contoso.net.</span><span class="sxs-lookup"><span data-stu-id="28543-123">All traffic except for HTTP/HTTPS traffic will use the Pool01.contoso.net record.</span></span> <span data-ttu-id="28543-124">Трафик HTTP/HTTPS будет использовать определенные адреса внутренних веб-служб 192.168.10.5</span><span class="sxs-lookup"><span data-stu-id="28543-124">HTTP/HTTPS traffic will use the defined internal Web services address of 192.168.10.5</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="28543-125">Пул внешних интерфейсов с развернутой балансировкой нагрузки DNS</span><span class="sxs-lookup"><span data-stu-id="28543-125">Front End pool with DNS load balancing deployed</span></span></p></td>
<td><p><span data-ttu-id="28543-126">Набор внутренних записей, которые разрешают полное доменное имя пула для IP-адреса каждого сервера в пуле.</span><span class="sxs-lookup"><span data-stu-id="28543-126">A set of internal A records that resolve the FQDN of the pool to the IP address of each server in the pool.</span></span> <span data-ttu-id="28543-127">Для каждого сервера в пуле должна быть одна запись.</span><span class="sxs-lookup"><span data-stu-id="28543-127">There must one A record for each server in the pool.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="28543-128">Пул внешних интерфейсов с развернутой балансировкой нагрузки DNS</span><span class="sxs-lookup"><span data-stu-id="28543-128">Front End pool with DNS load balancing deployed</span></span></p></td>
<td><p><span data-ttu-id="28543-129">Набор внутренних записей, которые разрешают полные доменные имена каждого сервера в пуле на IP-адрес этого сервера.</span><span class="sxs-lookup"><span data-stu-id="28543-129">A set of internal A records that resolve the FQDN of each server in the pool to the IP address of that server.</span></span> <span data-ttu-id="28543-130">Дополнительные сведения можно найти <a href="lync-server-2013-dns-load-balancing.md">в разделе Балансировка нагрузки DNS в Lync Server 2013</a> в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="28543-130">For details, see <a href="lync-server-2013-dns-load-balancing.md">DNS load balancing in Lync Server 2013</a> in the Planning documentation.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="28543-131">Пул переднего плана с одним сервером переднего плана и выделенной серверной базой данных, но без подсистемы балансировки нагрузки</span><span class="sxs-lookup"><span data-stu-id="28543-131">Front End pool with a single Front End Server and a dedicated back-end database but no load balancer</span></span></p></td>
<td><p><span data-ttu-id="28543-132">Внутренняя запись, с помощью которой можно разрешить полное доменное имя для пула переднего плана с IP-адресом отдельного сервера переднего плана Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="28543-132">An internal A record that resolves the FQDN of the Front End pool to the IP address of the single Enterprise Edition Front End Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="28543-133">Автоматический вход в учетную запись клиента</span><span class="sxs-lookup"><span data-stu-id="28543-133">Automatic client sign-in</span></span></p></td>
<td><p><span data-ttu-id="28543-134">Для каждого поддерживаемого домена SIP — запись SRV для _сипинтерналтлс. _tcp. &lt;домен&gt; , поступающий на порт 5061 и соответствующий доменному имени для пула переднего плана, который проверяет подлинность и перенаправляет запросы клиентов на вход.</span><span class="sxs-lookup"><span data-stu-id="28543-134">For each supported SIP domain, an SRV record for _sipinternaltls._tcp.&lt;domain&gt; over port 5061 that maps to the FQDN of the Front End pool that authenticates and redirects client requests for sign-in.</span></span> <span data-ttu-id="28543-135">Дополнительные сведения: <a href="lync-server-2013-dns-requirements-for-automatic-client-sign-in.md">требования к DNS для автоматического входа на клиент в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="28543-135">For details, see <a href="lync-server-2013-dns-requirements-for-automatic-client-sign-in.md">DNS requirements for automatic client sign-in in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="28543-136">Обнаружение веб-служб с помощью обновлений на устройствах с единым коммуникационным подключением (UC)</span><span class="sxs-lookup"><span data-stu-id="28543-136">Device Update Web service discovery by unified communications (UC) devices</span></span></p></td>
<td><p><span data-ttu-id="28543-137">Внутренняя запись с именем укупдатес-R2. &lt;Домен&gt; SIP, который разрешается в IP-адрес пула переднего плана, на котором размещается веб-служба обновления устройства.</span><span class="sxs-lookup"><span data-stu-id="28543-137">An internal A record with the name ucupdates-r2.&lt;SIP domain&gt; that resolves to the IP address of the Front End pool that hosts the Device Update Web service.</span></span> <span data-ttu-id="28543-138">В ситуации, когда устройство для установления связи включена, но пользователь не вошел в систему, запись A позволяет устройству найти веб-службу обновления устройства размещения пула и получить обновления.</span><span class="sxs-lookup"><span data-stu-id="28543-138">In the situation where a UC device is turned on, but a user has never logged into the device, the A record allows the device to discover the Front End pool hosting Device Update Web service and obtain updates.</span></span> <span data-ttu-id="28543-139">В противном случае устройства получают эти данные при первом входе пользователя в систему с помощью стандартных ресурсов.</span><span class="sxs-lookup"><span data-stu-id="28543-139">Otherwise, devices obtain this information though in-band provisioning the first time a user logs in.</span></span></p>
<div>

> [!IMPORTANT]  
> <span data-ttu-id="28543-140">Если у вас есть существующее развертывание веб-службы обновления устройств в Lync Server 2010, вы уже создали внутреннюю запись с именем укупдатес. &lt;Домен&gt;SIP.</span><span class="sxs-lookup"><span data-stu-id="28543-140">If you have an existing deployment of Device Update Web service in Lync Server 2010, you have already created an internal A record with the name ucupdates.&lt;SIP domain&gt;.</span></span> <span data-ttu-id="28543-141">Для Microsoft Office Communications Server 2007 R2 необходимо создать дополнительную запись DNS A с именем укупдатес-R2. &lt;Домен&gt;SIP.</span><span class="sxs-lookup"><span data-stu-id="28543-141">For Microsoft Office Communications Server 2007 R2, you must create an additional DNS A record with the name ucupdates-r2.&lt;SIP domain&gt;.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="28543-142">Обратный прокси-сервер, поддерживающий трафик HTTP</span><span class="sxs-lookup"><span data-stu-id="28543-142">A reverse proxy to support HTTP traffic</span></span></p></td>
<td><p><span data-ttu-id="28543-143">Внешняя запись A, разрешающая полное доменное имя внешней веб-фермы на внешний IP-адрес обратного прокси-сервера.</span><span class="sxs-lookup"><span data-stu-id="28543-143">An external A record that resolves the external web farm FQDN to the external IP address of the reverse proxy.</span></span> <span data-ttu-id="28543-144">Клиенты и устройства UC используют эту запись для подключения к обратному прокси-серверу.</span><span class="sxs-lookup"><span data-stu-id="28543-144">Clients and UC devices use this record to connect to the reverse proxy.</span></span> <span data-ttu-id="28543-145">Подробности можно найти в разделе <a href="lync-server-2013-determine-dns-requirements.md">Определение требований DNS для Lync Server 2013</a> в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="28543-145">For details, see <a href="lync-server-2013-determine-dns-requirements.md">Determine DNS requirements for Lync Server 2013</a> in the Planning documentation.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="28543-146">В приведенной ниже таблице показан пример DNS-записей, необходимых для внутреннего доменного имени внутренней веб-фермы.</span><span class="sxs-lookup"><span data-stu-id="28543-146">The following table shows an example of the DNS records required for the internal web farm FQDN.</span></span>

### <a name="example-dns-records-for-internal-web-farm-fqdn"></a><span data-ttu-id="28543-147">Примеры записей DNS для полного доменного имени внутренней веб-фермы</span><span class="sxs-lookup"><span data-stu-id="28543-147">Example DNS Records for Internal Web Farm FQDN</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="28543-148">Полное доменное имя внутренней веб-фермы</span><span class="sxs-lookup"><span data-stu-id="28543-148">Internal web farm FQDN</span></span></th>
<th><span data-ttu-id="28543-149">Полное доменное имя пула</span><span class="sxs-lookup"><span data-stu-id="28543-149">Pool FQDN</span></span></th>
<th><span data-ttu-id="28543-150">Запись (-а) DNS</span><span class="sxs-lookup"><span data-stu-id="28543-150">DNS A record(s)</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="28543-151">webcon.contoso.com</span><span class="sxs-lookup"><span data-stu-id="28543-151">webcon.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="28543-152">ee-pool.contoso.com</span><span class="sxs-lookup"><span data-stu-id="28543-152">ee-pool.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="28543-153">Запись DNS A для ee-pool.contoso.com, которая разрешается в виртуальный IP-адрес подсистемы балансировки нагрузки, используемой серверами переднего плана.</span><span class="sxs-lookup"><span data-stu-id="28543-153">DNS A record for the ee-pool.contoso.com that resolves to the VIP address of the load balancer used by the Front End Servers.</span></span></p>
<p><span data-ttu-id="28543-154">Запись DNS A для webcon.contoso.com, которая разрешается в VIP-адрес подсистемы балансировки нагрузки, используемой серверными интерфейсами.</span><span class="sxs-lookup"><span data-stu-id="28543-154">DNS A record for webcon.contoso.com that resolves to the VIP address of the load balancer used by the Front End Servers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="28543-155">ee-pool.contoso.com</span><span class="sxs-lookup"><span data-stu-id="28543-155">ee-pool.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="28543-156">ee-pool.contoso.com</span><span class="sxs-lookup"><span data-stu-id="28543-156">ee-pool.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="28543-157">Запись DNS A для ee-pool.contoso.com, которая разрешается в виртуальный IP-адрес подсистемы балансировки нагрузки, используемой серверами переднего плана Enterprise Edition в пуле переднего плана.</span><span class="sxs-lookup"><span data-stu-id="28543-157">DNS A record for ee-pool.contoso.com that resolves to the virtual IP (VIP) address of the load balancer used by the Enterprise Edition Front End Servers in the Front End pool.</span></span></p>
<p><span data-ttu-id="28543-158">Обратите внимание, что при использовании балансировки нагрузки DNS для этого пула пул переднего плана и внутренняя веб-ферма не могут иметь такое же полное доменное имя.</span><span class="sxs-lookup"><span data-stu-id="28543-158">Note that if you are using DNS load balancing on this pool, your Front End pool and internal web farm cannot have the same FQDN.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

