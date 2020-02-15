---
title: 'Lync Server 2013: требования к DNS для пулов переднего плана'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS requirements for Front End pools
ms:assetid: ba28919c-fbbe-4c54-8bf9-2b0cd3fa39c7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412910(v=OCS.15)
ms:contentKeyID: 48185228
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 12fc719c52434e07599fb4b65604ea832dc95f7e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42042146"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-requirements-for-front-end-pools-in-lync-server-2013"></a><span data-ttu-id="c70c5-102">Требования DNS для пулов переднего плана в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c70c5-102">DNS requirements for Front End pools in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c70c5-103">_**Последнее изменение темы:** 2012-11-07_</span><span class="sxs-lookup"><span data-stu-id="c70c5-103">_**Topic Last Modified:** 2012-11-07_</span></span>

<span data-ttu-id="c70c5-104">В этом разделе описываются DNS-записи, требуемые для развертывания интерфейсных пулов.</span><span class="sxs-lookup"><span data-stu-id="c70c5-104">This section describes the Domain Name System (DNS) records that are required for deployment of Front End pools.</span></span>

<div>

## <a name="dns-records-for-front-end-pools"></a><span data-ttu-id="c70c5-105">DNS-записи для интерфейсных пулов</span><span class="sxs-lookup"><span data-stu-id="c70c5-105">DNS Records for Front End Pools</span></span>

<span data-ttu-id="c70c5-106">В следующей таблице указаны требования к DNS для развертывания пула переднего плана Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c70c5-106">The following table specifies DNS requirements for a Lync Server 2013 Front End pool deployment.</span></span>

### <a name="dns-requirements-for-a-front-end-pool"></a><span data-ttu-id="c70c5-107">Требования DNS для интерфейсного пула</span><span class="sxs-lookup"><span data-stu-id="c70c5-107">DNS Requirements for a Front End Pool</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c70c5-108">Сценарий развертывания</span><span class="sxs-lookup"><span data-stu-id="c70c5-108">Deployment scenario</span></span></th>
<th><span data-ttu-id="c70c5-109">Требование DNS</span><span class="sxs-lookup"><span data-stu-id="c70c5-109">DNS requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c70c5-110">Интерфейсный пул с несколькими серверами переднего плана и аппаратным балансировщиком нагрузки (независимо от того, развертывается ли в этом пуле балансировка нагрузки на DNS)</span><span class="sxs-lookup"><span data-stu-id="c70c5-110">Front End pool with multiple Front End Servers and a hardware load balancer (whether or not DNS load balancing is also deployed on that pool)</span></span></p></td>
<td><p><span data-ttu-id="c70c5-111">При использовании балансировки нагрузки на DNS и аппаратного балансировщика нагрузки необходимо размещать записи (A).</span><span class="sxs-lookup"><span data-stu-id="c70c5-111">When using both DNS load balancing and a hardware load balancer, you need to Host (A) records.</span></span> <span data-ttu-id="c70c5-112">Создание внутренней записи A, которая разрешает полное доменное имя (FQDN) пула переднего плана для балансировки нагрузки на DNS.</span><span class="sxs-lookup"><span data-stu-id="c70c5-112">Create an internal A record that resolves the fully qualified domain name (FQDN) of the Front End pool for DNS load balancing.</span></span> <span data-ttu-id="c70c5-113">Создайте запись внутреннего узла (A) для внутренних веб-служб в виртуальный IP-адрес подсистемы балансировки нагрузки.</span><span class="sxs-lookup"><span data-stu-id="c70c5-113">Create an internal host (A) record for the internal Web services to the virtual IP (VIP) address of the load balancer.</span></span> <span data-ttu-id="c70c5-114">Необходимо использовать имя внутренней веб-службы в соответствии с определением в построителе топологий.</span><span class="sxs-lookup"><span data-stu-id="c70c5-114">You must use the internal Web services name as defined in Topology Builder.</span></span></p>
<p><span data-ttu-id="c70c5-115">Например, если вы используете балансировку нагрузки на DNS и аппаратную балансировку нагрузки, у вас будет запись A для каждого сервера переднего плана в пуле для балансировки нагрузки DNS и запись A для внутренних веб-служб, указывающая на виртуальный IP-адрес аппаратного балансировщика нагрузки. :</span><span class="sxs-lookup"><span data-stu-id="c70c5-115">For example, if you use both DNS load balancing and hardware load balancing, you would have an A record for each Front End Server in a pool for DNS load balancing, and an A record for the internal Web services pointing to the virtual IP of the hardware load balancer:</span></span></p>
<ul>
<li><p><span data-ttu-id="c70c5-116">Балансировка нагрузки на DNS: Pool01.contoso.net IP-адрес пула 10.10.10.5</span><span class="sxs-lookup"><span data-stu-id="c70c5-116">DNS load balancing:   Pool01.contoso.net   IP Address of pool   10.10.10.5</span></span></p>
<div>

> [!WARNING]  
> <span data-ttu-id="c70c5-117">Каждый сервер переднего плана также будет иметь отдельную запись A:</span><span class="sxs-lookup"><span data-stu-id="c70c5-117">Each Front End Server will also have a distinct A record:</span></span>


</div>
<ol>
<li><p><span data-ttu-id="c70c5-118">FE01.contoso.net 10.10.10.1</span><span class="sxs-lookup"><span data-stu-id="c70c5-118">FE01.contoso.net    10.10.10.1</span></span></p></li>
<li><p><span data-ttu-id="c70c5-119">FE02.contoso.net 10.10.10.2</span><span class="sxs-lookup"><span data-stu-id="c70c5-119">FE02.contoso.net    10.10.10.2</span></span></p></li>
<li><p><span data-ttu-id="c70c5-120">FE03.contoso.net 10.10.10.3</span><span class="sxs-lookup"><span data-stu-id="c70c5-120">FE03.contoso.net    10.10.10.3</span></span></p></li>
<li><p><span data-ttu-id="c70c5-121">FE04.contoso.net 10.10.10.4</span><span class="sxs-lookup"><span data-stu-id="c70c5-121">FE04.contoso.net    10.10.10.4</span></span></p></li>
</ol></li>
<li><p><span data-ttu-id="c70c5-122">Аппаратная балансировка нагрузки: WebInternal.contoso.net IP-адрес HLB VIP 192.168.10.5</span><span class="sxs-lookup"><span data-stu-id="c70c5-122">Hardware load balancing:   WebInternal.contoso.net   IP Address of HLB VIP   192.168.10.5</span></span></p></li>
</ul>
<p><span data-ttu-id="c70c5-123">Весь трафик, кроме трафика HTTP/HTTPS, будет использовать запись Pool01.contoso.net.</span><span class="sxs-lookup"><span data-stu-id="c70c5-123">All traffic except for HTTP/HTTPS traffic will use the Pool01.contoso.net record.</span></span> <span data-ttu-id="c70c5-124">Трафик HTTP/HTTPS будет использовать определенный адрес внутренних веб-служб 192.168.10.5</span><span class="sxs-lookup"><span data-stu-id="c70c5-124">HTTP/HTTPS traffic will use the defined internal Web services address of 192.168.10.5</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c70c5-125">Интерфейсный пул с развернутой балансировкой нагрузки на DNS</span><span class="sxs-lookup"><span data-stu-id="c70c5-125">Front End pool with DNS load balancing deployed</span></span></p></td>
<td><p><span data-ttu-id="c70c5-p103">Набор внутренних записей A, которые разрешают полное доменное имя пула в IP-адрес каждого сервера пула. Для каждого сервера пула должна существовать только одна запись A.</span><span class="sxs-lookup"><span data-stu-id="c70c5-p103">A set of internal A records that resolve the FQDN of the pool to the IP address of each server in the pool. There must one A record for each server in the pool.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c70c5-128">Интерфейсный пул с развернутой балансировкой нагрузки на DNS</span><span class="sxs-lookup"><span data-stu-id="c70c5-128">Front End pool with DNS load balancing deployed</span></span></p></td>
<td><p><span data-ttu-id="c70c5-129">Набор внутренних записей A, которые разрешают полное доменное каждого сервера пула в IP-адрес этого сервера.</span><span class="sxs-lookup"><span data-stu-id="c70c5-129">A set of internal A records that resolve the FQDN of each server in the pool to the IP address of that server.</span></span> <span data-ttu-id="c70c5-130">Для получения дополнительных сведений обратитесь к разделу <a href="lync-server-2013-dns-load-balancing.md">Балансировка нагрузки на DNS в Lync Server 2013</a> в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="c70c5-130">For details, see <a href="lync-server-2013-dns-load-balancing.md">DNS load balancing in Lync Server 2013</a> in the Planning documentation.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c70c5-131">Интерфейсный пул с одним сервером переднего плана и выделенной серверной базой данных, но без распределения нагрузки</span><span class="sxs-lookup"><span data-stu-id="c70c5-131">Front End pool with a single Front End Server and a dedicated back-end database but no load balancer</span></span></p></td>
<td><p><span data-ttu-id="c70c5-132">Внутренняя запись A, которая разрешает полное доменное имя интерфейсного пула в IP-адрес одного сервера переднего плана выпуска Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="c70c5-132">An internal A record that resolves the FQDN of the Front End pool to the IP address of the single Enterprise Edition Front End Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c70c5-133">Автоматический вход клиента</span><span class="sxs-lookup"><span data-stu-id="c70c5-133">Automatic client sign-in</span></span></p></td>
<td><p><span data-ttu-id="c70c5-134">Для каждого поддерживаемого домена SIP запись SRV для _sipinternaltls. _tcp. &lt;домен&gt; через порт 5061, который соответствует полному доменному имени интерфейсного пула, который выполняет проверку подлинности и перенаправляет запросы клиентов на вход.</span><span class="sxs-lookup"><span data-stu-id="c70c5-134">For each supported SIP domain, an SRV record for _sipinternaltls._tcp.&lt;domain&gt; over port 5061 that maps to the FQDN of the Front End pool that authenticates and redirects client requests for sign-in.</span></span> <span data-ttu-id="c70c5-135">Дополнительные сведения см. <a href="lync-server-2013-dns-requirements-for-automatic-client-sign-in.md">в статье требования к DNS для автоматического входа клиентов в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="c70c5-135">For details, see <a href="lync-server-2013-dns-requirements-for-automatic-client-sign-in.md">DNS requirements for automatic client sign-in in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c70c5-136">Обнаружение веб-службы обновления устройств устройствами объединенных коммуникаций</span><span class="sxs-lookup"><span data-stu-id="c70c5-136">Device Update Web service discovery by unified communications (UC) devices</span></span></p></td>
<td><p><span data-ttu-id="c70c5-137">Внутренняя запись A с именем ucupdates – R2. &lt;Домен&gt; SIP, который разрешается в IP-адрес пула переднего плана, на котором размещается веб-служба обновления устройств.</span><span class="sxs-lookup"><span data-stu-id="c70c5-137">An internal A record with the name ucupdates-r2.&lt;SIP domain&gt; that resolves to the IP address of the Front End pool that hosts the Device Update Web service.</span></span> <span data-ttu-id="c70c5-138">Если устройство объединенных коммуникаций включено, но пользователь никогда не входил в систему устройства, то запись A позволит устройству обнаружить интерфейсный пул, содержащий веб-службу обновления устройств, и получить обновления.</span><span class="sxs-lookup"><span data-stu-id="c70c5-138">In the situation where a UC device is turned on, but a user has never logged into the device, the A record allows the device to discover the Front End pool hosting Device Update Web service and obtain updates.</span></span> <span data-ttu-id="c70c5-139">В противном случае устройства получат эти сведения посредством автоматической подготовки при первичном входе пользователя.</span><span class="sxs-lookup"><span data-stu-id="c70c5-139">Otherwise, devices obtain this information though in-band provisioning the first time a user logs in.</span></span></p>
<div>

> [!IMPORTANT]  
> <span data-ttu-id="c70c5-140">При наличии существующего развертывания веб-службы обновления устройств в Lync Server 2010 вы уже создали внутреннюю запись A с именем ucupdates. &lt;Домен&gt;SIP.</span><span class="sxs-lookup"><span data-stu-id="c70c5-140">If you have an existing deployment of Device Update Web service in Lync Server 2010, you have already created an internal A record with the name ucupdates.&lt;SIP domain&gt;.</span></span> <span data-ttu-id="c70c5-141">Для Microsoft Office Communications Server 2007 R2 необходимо создать дополнительную DNS-запись A с именем ucupdates-R2. &lt;Домен&gt;SIP.</span><span class="sxs-lookup"><span data-stu-id="c70c5-141">For Microsoft Office Communications Server 2007 R2, you must create an additional DNS A record with the name ucupdates-r2.&lt;SIP domain&gt;.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c70c5-142">Обратный прокси-сервер для поддержки трафика HTTP</span><span class="sxs-lookup"><span data-stu-id="c70c5-142">A reverse proxy to support HTTP traffic</span></span></p></td>
<td><p><span data-ttu-id="c70c5-143">Внешняя запись A, которая разрешает полное доменное имя внешней веб-фермы во внешний IP-адрес обратного прокси-сервера.</span><span class="sxs-lookup"><span data-stu-id="c70c5-143">An external A record that resolves the external web farm FQDN to the external IP address of the reverse proxy.</span></span> <span data-ttu-id="c70c5-144">Клиенты и устройства объединенных коммуникаций используют эту запись для подключения к обратному прокси-серверу.</span><span class="sxs-lookup"><span data-stu-id="c70c5-144">Clients and UC devices use this record to connect to the reverse proxy.</span></span> <span data-ttu-id="c70c5-145">Дополнительные сведения: <a href="lync-server-2013-determine-dns-requirements.md">Определение требований к DNS для Lync Server 2013</a> в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="c70c5-145">For details, see <a href="lync-server-2013-determine-dns-requirements.md">Determine DNS requirements for Lync Server 2013</a> in the Planning documentation.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="c70c5-146">В следующей таблице показан пример DNS-записей для полного доменного имени внутренней веб-фермы.</span><span class="sxs-lookup"><span data-stu-id="c70c5-146">The following table shows an example of the DNS records required for the internal web farm FQDN.</span></span>

### <a name="example-dns-records-for-internal-web-farm-fqdn"></a><span data-ttu-id="c70c5-147">Пример DNS-записей для полного доменного имени внутренней веб-фермы</span><span class="sxs-lookup"><span data-stu-id="c70c5-147">Example DNS Records for Internal Web Farm FQDN</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c70c5-148">Полное доменное имя внутренней веб-фермы</span><span class="sxs-lookup"><span data-stu-id="c70c5-148">Internal web farm FQDN</span></span></th>
<th><span data-ttu-id="c70c5-149">Полное доменное имя пула</span><span class="sxs-lookup"><span data-stu-id="c70c5-149">Pool FQDN</span></span></th>
<th><span data-ttu-id="c70c5-150">DNS-записи A</span><span class="sxs-lookup"><span data-stu-id="c70c5-150">DNS A record(s)</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c70c5-151">webcon.contoso.com</span><span class="sxs-lookup"><span data-stu-id="c70c5-151">webcon.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="c70c5-152">ee-pool.contoso.com</span><span class="sxs-lookup"><span data-stu-id="c70c5-152">ee-pool.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="c70c5-153">DNS-запись A для ee-pool.contoso.com, которая разрешается в виртуальный IP-адрес балансировщика нагрузки, используемого серверами переднего плана.</span><span class="sxs-lookup"><span data-stu-id="c70c5-153">DNS A record for the ee-pool.contoso.com that resolves to the VIP address of the load balancer used by the Front End Servers.</span></span></p>
<p><span data-ttu-id="c70c5-154">DNS-запись A для webcon.contoso.com, которая разрешается в виртуальный IP-адрес балансировщика нагрузки, используемого серверами переднего плана.</span><span class="sxs-lookup"><span data-stu-id="c70c5-154">DNS A record for webcon.contoso.com that resolves to the VIP address of the load balancer used by the Front End Servers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c70c5-155">ee-pool.contoso.com</span><span class="sxs-lookup"><span data-stu-id="c70c5-155">ee-pool.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="c70c5-156">ee-pool.contoso.com</span><span class="sxs-lookup"><span data-stu-id="c70c5-156">ee-pool.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="c70c5-157">DNS-запись A для ee-pool.contoso.com, которая разрешается в виртуальный IP-адрес балансировщика нагрузки, используемого серверами переднего плана выпуска Enterprise Edition в интерфейсном пуле.</span><span class="sxs-lookup"><span data-stu-id="c70c5-157">DNS A record for ee-pool.contoso.com that resolves to the virtual IP (VIP) address of the load balancer used by the Enterprise Edition Front End Servers in the Front End pool.</span></span></p>
<p><span data-ttu-id="c70c5-158">Обратите внимание, что при использовании балансировки нагрузки на DNS в этом пуле ваш интерфейсный пул и внутренняя веб-ферма не могут иметь одинаковые полные доменные имена.</span><span class="sxs-lookup"><span data-stu-id="c70c5-158">Note that if you are using DNS load balancing on this pool, your Front End pool and internal web farm cannot have the same FQDN.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

