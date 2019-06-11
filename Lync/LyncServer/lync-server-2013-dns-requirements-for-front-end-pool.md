---
title: 'Lync Server 2013: требования DNS для пулов переднего плана'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: DNS requirements for Front End pool
ms:assetid: 02d2aa6b-9e01-437b-a2df-00590280150d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398082(v=OCS.15)
ms:contentKeyID: 48183249
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3c033d8f1a4167e423d5663b0c9b0b7dbfb2d760
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834381"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-requirements-for-front-end-pool-in-lync-server-2013"></a><span data-ttu-id="f85d5-102">Требования DNS для пулов переднего плана в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f85d5-102">DNS requirements for Front End pool in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f85d5-103">_**Тема последнего изменения:** 2012-11-07_</span><span class="sxs-lookup"><span data-stu-id="f85d5-103">_**Topic Last Modified:** 2012-11-07_</span></span>

<span data-ttu-id="f85d5-104">Для успешного выполнения этой процедуры необходимо войти в систему на сервере или в домене в группу администраторов домена или в группу пользователей Днсадминс.</span><span class="sxs-lookup"><span data-stu-id="f85d5-104">To successfully complete this procedure, you should be logged on to the server or domain minimally as a member of the Domain Admins group or a member of the DnsAdmins group.</span></span>

<span data-ttu-id="f85d5-105">Прежде чем публиковать топологию в построителе топологии, необходимо настроить нужные записи DNS (Domain Name System).</span><span class="sxs-lookup"><span data-stu-id="f85d5-105">You need to configure the required Domain Name System (DNS) records prior to publishing your topology in Topology Builder.</span></span> <span data-ttu-id="f85d5-106">Кроме того, некоторые полные доменные имена, используемые в конфигурации Lync Server 2013, являются логическими, а не физическими (FQDN), поэтому перед публикацией требуется дополнительная настройка DNS.</span><span class="sxs-lookup"><span data-stu-id="f85d5-106">Additionally, some of the fully qualified domain names (FQDNs) used in the configuration of a Lync Server 2013 deployment are logical and not physical server FQDNs, so additional DNS configuration is required prior to publishing.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="f85d5-107">Lync Server 2013 не поддерживает домены, помеченные как единые.</span><span class="sxs-lookup"><span data-stu-id="f85d5-107">Lync Server 2013 does not support single-labeled domains.</span></span> <span data-ttu-id="f85d5-108">Например, лес с корневым доменом с именем <STRONG>contoso. local</STRONG> поддерживается, но корневой домен с именем <STRONG>Local</STRONG> не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="f85d5-108">For example, a forest with a root domain named <STRONG>contoso.local</STRONG> is supported, but a root domain named <STRONG>local</STRONG> is not supported.</span></span> <span data-ttu-id="f85d5-109">Подробные сведения о том, как настроить Windows для доменов с DNS-именами, сопоставленными с одной меткой, можно найти в статье 300684 (at <A class=uri href="http://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=300684"> http://go.microsoft.com/fwlink/p/?linkid=3052&amp; кбид = 300684</A>.</span><span class="sxs-lookup"><span data-stu-id="f85d5-109">For details, see Microsoft Knowledge Base article 300684, “Information about configuring Windows for domains with single-label DNS names,” at <A class=uri href="http://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=300684">http://go.microsoft.com/fwlink/p/?linkid=3052&amp;kbid=300684</A>.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="f85d5-110">Указанное имя должно быть идентично имени компьютера, настроенному на сервере.</span><span class="sxs-lookup"><span data-stu-id="f85d5-110">The name you specify must be identical to the computer name configured on the server.</span></span> <span data-ttu-id="f85d5-111">По умолчанию имя компьютера, не подключенного к домену, является коротким именем, а не FQDN.</span><span class="sxs-lookup"><span data-stu-id="f85d5-111">By default the computer name of a computer that is not joined to a domain is a short name, not an FQDN.</span></span> <span data-ttu-id="f85d5-112">Построитель топологии использует полные доменные имена, а не короткие имена.</span><span class="sxs-lookup"><span data-stu-id="f85d5-112">Topology Builder uses FQDNs, not short names.</span></span> <span data-ttu-id="f85d5-113"><STRONG>Использовать только стандартные символы</STRONG> (включая A – Z, a – z, 0 – 9 и дефисы) при назначении полных доменных имен серверов Lync Server, пограничных серверов и пулов.</span><span class="sxs-lookup"><span data-stu-id="f85d5-113"><STRONG>Use only standard characters</STRONG> (including A–Z, a–z, 0–9, and hyphens) when assigning FQDNs of your servers running Lync Server, Edge Servers, and pools.</span></span> <span data-ttu-id="f85d5-114">Не используйте символы Unicode или подчеркивания.</span><span class="sxs-lookup"><span data-stu-id="f85d5-114">Do not use Unicode characters or underscores.</span></span> <span data-ttu-id="f85d5-115">Нестандартные символы в полном доменном имени часто не поддерживаются внешними DNS-и общедоступными центрами сертификации (ЦС) (когда полное доменное имя должно быть назначено для SN в сертификате).</span><span class="sxs-lookup"><span data-stu-id="f85d5-115">Nonstandard characters in an FQDN are often not supported by external DNS and public certification authorities (CAs) (when the FQDN must be assigned to the SN in the certificate).</span></span>



</div>

<span data-ttu-id="f85d5-116">Перед тем как приступать к работе с топологией после ее развертывания, убедитесь в том, что созданы указанные ниже записи Active Directory и DNS (в зависимости от того, что требуется для определенных функций):</span><span class="sxs-lookup"><span data-stu-id="f85d5-116">Prior to operating the topology after it has been deployed, ensure that the following Active Directory and DNS records are created (as your needs for specific features dictate):</span></span>

  - <span data-ttu-id="f85d5-117">Все роли сервера, которые будут существовать в топологии, публикуются как объект Active Directory (это можно сделать с помощью присоединения компьютера к домену).</span><span class="sxs-lookup"><span data-stu-id="f85d5-117">Each server role that will exist in the topology is published as an Active Directory object (joining the computer to the domain will accomplish this).</span></span>

  - <span data-ttu-id="f85d5-118">Для каждого сервера существует запись DNS A.</span><span class="sxs-lookup"><span data-stu-id="f85d5-118">A DNS A Record exists for each server.</span></span>

  - <span data-ttu-id="f85d5-119">DNS SRV-запись для каждого домена SIP используется в том случае, если вы планируете использовать автоматический вход в систему \_для\_клиентов в форме сипинтерналтлс TCP. \<Домен\>SIP.</span><span class="sxs-lookup"><span data-stu-id="f85d5-119">A DNS SRV Record exists for each SIP domain if you plan to use automatic logon for clients in the form of \_sipinternaltls\_tcp.\<SIP domain\>.</span></span> <span data-ttu-id="f85d5-120">Если вы будете использовать ручную настройку для клиентов, эта запись не требуется.</span><span class="sxs-lookup"><span data-stu-id="f85d5-120">If you will use manual configuration for clients, this record is not necessary.</span></span>

  - <span data-ttu-id="f85d5-121">Запись DNS A для каждого настроенного простого URL-адреса, который обычно состоит из четырех: "Встреча", "Входящие", "лва" и "Планировщик".</span><span class="sxs-lookup"><span data-stu-id="f85d5-121">A DNS A Record for each configured simple URL, of which there are typically four: meet, dialin, lwa, and scheduler.</span></span> <span data-ttu-id="f85d5-122">Кроме того, существует простой URL-адрес администратора, который является специальным URL-адресом для доступа к панели управления Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f85d5-122">Additionally, there is the admin simple URL which is a special URL for access to the Lync Server 2013 Control Panel.</span></span>

  - <span data-ttu-id="f85d5-123">Сервер, на котором работает SQL Server, должен быть присоединен к домену и доступен на компьютере, с которого построитель топологии выполняет публикацию.</span><span class="sxs-lookup"><span data-stu-id="f85d5-123">The server running SQL Server must be joined to the domain, and reachable by the computer that Topology Builder is publishing from.</span></span>

<span data-ttu-id="f85d5-124">В таблице ниже приведены справочные архитектуры, представленные в разделе Планирование.</span><span class="sxs-lookup"><span data-stu-id="f85d5-124">The table follows the reference architectures presented in the Planning section.</span></span> <span data-ttu-id="f85d5-125">Дополнительные сведения можно найти [в разделе сценарии доступа внешних пользователей в Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md) в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="f85d5-125">For details, see [Scenarios for external user access in Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md) in the Planning documentation.</span></span>

<div id="sectionSection0" class="section">

### <a name="dns-records-required-for-the-front-end-pool"></a><span data-ttu-id="f85d5-126">DNS-записи, необходимые для пула переднего плана</span><span class="sxs-lookup"><span data-stu-id="f85d5-126">DNS Records Required for the Front End pool</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f85d5-127">Расположение</span><span class="sxs-lookup"><span data-stu-id="f85d5-127">Location</span></span></th>
<th><span data-ttu-id="f85d5-128">Тип</span><span class="sxs-lookup"><span data-stu-id="f85d5-128">Type</span></span></th>
<th><span data-ttu-id="f85d5-129">Полное доменное имя</span><span class="sxs-lookup"><span data-stu-id="f85d5-129">FQDN</span></span></th>
<th><span data-ttu-id="f85d5-130">Карты и примечания</span><span class="sxs-lookup"><span data-stu-id="f85d5-130">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f85d5-131">Внутренняя DNS</span><span class="sxs-lookup"><span data-stu-id="f85d5-131">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="f85d5-132">A</span><span class="sxs-lookup"><span data-stu-id="f85d5-132">A</span></span></p></td>
<td><p><span data-ttu-id="f85d5-133">pool01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="f85d5-133">pool01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="f85d5-134">Pool01 (Балансировка нагрузки DNS).</span><span class="sxs-lookup"><span data-stu-id="f85d5-134">Pool01 (DNS load balancing).</span></span> <span data-ttu-id="f85d5-135">Требуется запись DNS A для IP-адреса каждого сервера переднего плана в пуле, сопоставленная с полным доменным именем пула.</span><span class="sxs-lookup"><span data-stu-id="f85d5-135">Requires a DNS A record for the IP address of each Front End Server within the pool, mapping to the pool FQDN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f85d5-136">Внутренняя DNS</span><span class="sxs-lookup"><span data-stu-id="f85d5-136">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="f85d5-137">A</span><span class="sxs-lookup"><span data-stu-id="f85d5-137">A</span></span></p></td>
<td><p><span data-ttu-id="f85d5-138">pool01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="f85d5-138">pool01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="f85d5-139">Pool01 (виртуальный IP-адрес (VIP) балансировщика аппаратной балансировки нагрузки).</span><span class="sxs-lookup"><span data-stu-id="f85d5-139">Pool01 (virtual IP (VIP) of hardware load balancer).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f85d5-140">Внутренняя DNS</span><span class="sxs-lookup"><span data-stu-id="f85d5-140">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="f85d5-141">A</span><span class="sxs-lookup"><span data-stu-id="f85d5-141">A</span></span></p></td>
<td><p><span data-ttu-id="f85d5-142">fe01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="f85d5-142">fe01.contoso.net</span></span></p>
<p><span data-ttu-id="f85d5-143">fe02.contoso.net</span><span class="sxs-lookup"><span data-stu-id="f85d5-143">fe02.contoso.net</span></span></p>
<p><span data-ttu-id="f85d5-144">fe03.contoso.net</span><span class="sxs-lookup"><span data-stu-id="f85d5-144">fe03.contoso.net</span></span></p>
<p><span data-ttu-id="f85d5-145">…</span><span class="sxs-lookup"><span data-stu-id="f85d5-145"></span></span></p></td>
<td><p><span data-ttu-id="f85d5-146">Сервер Pool01 переднего плана (узел 1).</span><span class="sxs-lookup"><span data-stu-id="f85d5-146">Pool01 Front End Server (NODE 1).</span></span></p>
<p><span data-ttu-id="f85d5-147">Сервер Pool01 переднего плана (узел 2).</span><span class="sxs-lookup"><span data-stu-id="f85d5-147">Pool01 Front End Server (NODE 2).</span></span></p>
<p><span data-ttu-id="f85d5-148">Сервер Pool01 переднего плана (узел 3).</span><span class="sxs-lookup"><span data-stu-id="f85d5-148">Pool01 Front End Server (NODE 3).</span></span></p>
<p><span data-ttu-id="f85d5-149">…</span><span class="sxs-lookup"><span data-stu-id="f85d5-149"></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f85d5-150">Внутренняя DNS</span><span class="sxs-lookup"><span data-stu-id="f85d5-150">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="f85d5-151">A</span><span class="sxs-lookup"><span data-stu-id="f85d5-151">A</span></span></p></td>
<td><p><span data-ttu-id="f85d5-152">fe02.contoso.net</span><span class="sxs-lookup"><span data-stu-id="f85d5-152">fe02.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="f85d5-153">Сервер Pool01 переднего плана (узел 2).</span><span class="sxs-lookup"><span data-stu-id="f85d5-153">Pool01 Front End Server (NODE 2).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f85d5-154">Внутренняя DNS</span><span class="sxs-lookup"><span data-stu-id="f85d5-154">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="f85d5-155">A</span><span class="sxs-lookup"><span data-stu-id="f85d5-155">A</span></span></p></td>
<td><p><span data-ttu-id="f85d5-156">lsweb.contoso.net</span><span class="sxs-lookup"><span data-stu-id="f85d5-156">lsweb.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="f85d5-157">Pool01 (VIP) для веб-трафика между клиентом и сервером.</span><span class="sxs-lookup"><span data-stu-id="f85d5-157">Pool01 (VIP) for client-to-server web traffic.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f85d5-158">Внутренняя DNS</span><span class="sxs-lookup"><span data-stu-id="f85d5-158">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="f85d5-159">A</span><span class="sxs-lookup"><span data-stu-id="f85d5-159">A</span></span></p></td>
<td><p><span data-ttu-id="f85d5-160">sqlbe.contoso.net</span><span class="sxs-lookup"><span data-stu-id="f85d5-160">sqlbe.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="f85d5-161">Сервер Pool01 Server, на котором запущен SQL Server 2008 R2.</span><span class="sxs-lookup"><span data-stu-id="f85d5-161">Pool01 Back End Server running SQL Server 2008 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f85d5-162">Внутренняя DNS</span><span class="sxs-lookup"><span data-stu-id="f85d5-162">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="f85d5-163">A</span><span class="sxs-lookup"><span data-stu-id="f85d5-163">A</span></span></p></td>
<td><p><span data-ttu-id="f85d5-164">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f85d5-164">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="f85d5-165">Требуется для Lync Phone Edition или для автоматического входа в систему клиентов без DNS SRV-записей и для строгого сопоставления доменов.</span><span class="sxs-lookup"><span data-stu-id="f85d5-165">Required for Lync Phone Edition, or automatic logon of clients without DNS SRV records, and for strict domain matching.</span></span> <span data-ttu-id="f85d5-166">Не является обязательным для всех случаев.</span><span class="sxs-lookup"><span data-stu-id="f85d5-166">Not required in all cases.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f85d5-167">Внутренняя DNS</span><span class="sxs-lookup"><span data-stu-id="f85d5-167">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="f85d5-168">A</span><span class="sxs-lookup"><span data-stu-id="f85d5-168">A</span></span></p></td>
<td><p><span data-ttu-id="f85d5-169">sip.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="f85d5-169">sip.fabrikam.com</span></span></p></td>
<td><p><span data-ttu-id="f85d5-170">Предполагается наличие второго домена SIP.</span><span class="sxs-lookup"><span data-stu-id="f85d5-170">Assumes a second SIP domain.</span></span> <span data-ttu-id="f85d5-171">Требуется для Lync Phone Edition, автоматического входа в систему клиентов без DNS SRV-записей и для строгого сопоставления доменов.</span><span class="sxs-lookup"><span data-stu-id="f85d5-171">Required for Lync Phone Edition, automatic logon of clients without DNS SRV records, and for strict domain matching.</span></span> <span data-ttu-id="f85d5-172">Не является обязательным для всех случаев.</span><span class="sxs-lookup"><span data-stu-id="f85d5-172">Not required in all cases.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f85d5-173">Внутренняя DNS</span><span class="sxs-lookup"><span data-stu-id="f85d5-173">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="f85d5-174">A</span><span class="sxs-lookup"><span data-stu-id="f85d5-174">A</span></span></p></td>
<td><p><span data-ttu-id="f85d5-175">dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f85d5-175">dialin.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="f85d5-176">Простой URL-адрес для конференц-связи с телефонным подключением, опубликованный внутренне — сервер переднего плана (или режиссер, если он установлен) отвечает на простые URL-запросы.</span><span class="sxs-lookup"><span data-stu-id="f85d5-176">Simple URL for dial-in conferencing published internally – Front End Server (or Director, if installed) responds to simple URL queries.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f85d5-177">Внутренняя DNS</span><span class="sxs-lookup"><span data-stu-id="f85d5-177">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="f85d5-178">A</span><span class="sxs-lookup"><span data-stu-id="f85d5-178">A</span></span></p></td>
<td><p><span data-ttu-id="f85d5-179">meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f85d5-179">meet.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="f85d5-180">Простой URL-адрес для конференций, опубликованный внутренне — сервер переднего плана (или режиссер, если он установлен) отвечает на простые URL-запросы.</span><span class="sxs-lookup"><span data-stu-id="f85d5-180">Simple URL for conferences published internally – Front End Server (or Director, if installed) responds to simple URL queries.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f85d5-181">Внутренняя DNS</span><span class="sxs-lookup"><span data-stu-id="f85d5-181">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="f85d5-182">A</span><span class="sxs-lookup"><span data-stu-id="f85d5-182">A</span></span></p></td>
<td><p><span data-ttu-id="f85d5-183">admin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f85d5-183">admin.contoso.com</span></span></p>
<p><span data-ttu-id="f85d5-184">RAS</span><span class="sxs-lookup"><span data-stu-id="f85d5-184">admin</span></span></p></td>
<td><p><span data-ttu-id="f85d5-185">Необязательная запись, простой URL-адрес для панели управления Lync Server 2013, опубликованный внутренним образом сервер переднего плана (или режиссер, если он установлен) отвечает на простые URL-запросы.</span><span class="sxs-lookup"><span data-stu-id="f85d5-185">Optional record, simple URL for Lync Server 2013 Control Panel published internally - Front End Server (or Director, if installed) responds to simple URL queries.</span></span> <span data-ttu-id="f85d5-186">Рекомендуется только имя узла (имя домена не поддерживается).</span><span class="sxs-lookup"><span data-stu-id="f85d5-186">Host name only (no domain name) is recommended.</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="f85d5-187">VIP = виртуальный IP-адрес для подсистемы балансировки нагрузки для оборудования</span><span class="sxs-lookup"><span data-stu-id="f85d5-187">VIP = Virtual IP address for hardware load balancer</span></span>



</div>

</div>

<div>

## <a name="dns-srv-records-for-the-front-end-pool"></a><span data-ttu-id="f85d5-188">Записи DNS SRV для пула переднего плана</span><span class="sxs-lookup"><span data-stu-id="f85d5-188">DNS SRV Records for the Front End pool</span></span>


<table style="width:100%;">
<colgroup>
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f85d5-189">Расположение</span><span class="sxs-lookup"><span data-stu-id="f85d5-189">Location</span></span></th>
<th><span data-ttu-id="f85d5-190">Тип</span><span class="sxs-lookup"><span data-stu-id="f85d5-190">Type</span></span></th>
<th><span data-ttu-id="f85d5-191">Полное доменное имя</span><span class="sxs-lookup"><span data-stu-id="f85d5-191">FQDN</span></span></th>
<th><span data-ttu-id="f85d5-192">Целевое полное доменное имя</span><span class="sxs-lookup"><span data-stu-id="f85d5-192">Target FQDN</span></span></th>
<th><span data-ttu-id="f85d5-193">Порт</span><span class="sxs-lookup"><span data-stu-id="f85d5-193">Port</span></span></th>
<th><span data-ttu-id="f85d5-194">Карты и примечания</span><span class="sxs-lookup"><span data-stu-id="f85d5-194">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f85d5-195">Внутренняя DNS</span><span class="sxs-lookup"><span data-stu-id="f85d5-195">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="f85d5-196">SRV</span><span class="sxs-lookup"><span data-stu-id="f85d5-196">SRV</span></span></p></td>
<td><p><span data-ttu-id="f85d5-197">_сипинтерналтлс. _tcp. contoso. com</span><span class="sxs-lookup"><span data-stu-id="f85d5-197">_sipinternaltls._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="f85d5-198">pool01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f85d5-198">pool01.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="f85d5-199">5061</span><span class="sxs-lookup"><span data-stu-id="f85d5-199">5061</span></span></p></td>
<td><p><span data-ttu-id="f85d5-200">Требуется для автоматической настройки клиентов Lync 2013 для внутреннего использования.</span><span class="sxs-lookup"><span data-stu-id="f85d5-200">Required for automatic configuration of Lync 2013 clients to work internally.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f85d5-201">Внутренняя DNS</span><span class="sxs-lookup"><span data-stu-id="f85d5-201">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="f85d5-202">SRV</span><span class="sxs-lookup"><span data-stu-id="f85d5-202">SRV</span></span></p></td>
<td><p><span data-ttu-id="f85d5-203">_сипинтерналтлс. _tcp. fabrikam. com</span><span class="sxs-lookup"><span data-stu-id="f85d5-203">_sipinternaltls._tcp.fabrikam.com</span></span></p></td>
<td><p><span data-ttu-id="f85d5-204">pool01.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="f85d5-204">pool01.fabrikam.com</span></span></p></td>
<td><p><span data-ttu-id="f85d5-205">5061</span><span class="sxs-lookup"><span data-stu-id="f85d5-205">5061</span></span></p></td>
<td><p><span data-ttu-id="f85d5-206">Требуется для автоматической настройки клиентов Lync 2013 для внутреннего использования.</span><span class="sxs-lookup"><span data-stu-id="f85d5-206">Required for automatic configuration of Lync 2013 clients to work internally.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f85d5-207">Внутренняя DNS</span><span class="sxs-lookup"><span data-stu-id="f85d5-207">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="f85d5-208">SRV</span><span class="sxs-lookup"><span data-stu-id="f85d5-208">SRV</span></span></p></td>
<td><p><span data-ttu-id="f85d5-209">_ntp._udp.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f85d5-209">_ntp._udp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="f85d5-210">dc01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f85d5-210">dc01.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="f85d5-211">123</span><span class="sxs-lookup"><span data-stu-id="f85d5-211">123</span></span></p></td>
<td><p><span data-ttu-id="f85d5-212">Для устройств с Lync Phone Edition требуется источник сетевого времени (NTP).</span><span class="sxs-lookup"><span data-stu-id="f85d5-212">Network Time Protocol (NTP) source required for devices running Lync Phone Edition.</span></span> <span data-ttu-id="f85d5-213">На внутреннем уровне это значение должно указывать на контроллер домена.</span><span class="sxs-lookup"><span data-stu-id="f85d5-213">Internally, this should point to the domain controller.</span></span> <span data-ttu-id="f85d5-214">Если контроллер домена не определен, он попытается использовать сервер NTP time.windows.com.</span><span class="sxs-lookup"><span data-stu-id="f85d5-214">If the domain controller is not defined, it will try to use the NTP server time.windows.com.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

