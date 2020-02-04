---
title: 'Lync Server 2013: требования DNS для пулов переднего плана'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS requirements for Front End pool
ms:assetid: 02d2aa6b-9e01-437b-a2df-00590280150d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398082(v=OCS.15)
ms:contentKeyID: 48183249
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 252bacd9818676155dcab0f84e3e1c5fcdb31b5d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765297"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-requirements-for-front-end-pool-in-lync-server-2013"></a><span data-ttu-id="2cce3-102">Требования DNS для пулов переднего плана в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2cce3-102">DNS requirements for Front End pool in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2cce3-103">_**Тема последнего изменения:** 2012-11-07_</span><span class="sxs-lookup"><span data-stu-id="2cce3-103">_**Topic Last Modified:** 2012-11-07_</span></span>

<span data-ttu-id="2cce3-104">Для успешного выполнения этой процедуры необходимо войти в систему на сервере или в домене в группу администраторов домена или в группу пользователей Днсадминс.</span><span class="sxs-lookup"><span data-stu-id="2cce3-104">To successfully complete this procedure, you should be logged on to the server or domain minimally as a member of the Domain Admins group or a member of the DnsAdmins group.</span></span>

<span data-ttu-id="2cce3-105">Прежде чем публиковать топологию в построителе топологии, необходимо настроить нужные записи DNS (Domain Name System).</span><span class="sxs-lookup"><span data-stu-id="2cce3-105">You need to configure the required Domain Name System (DNS) records prior to publishing your topology in Topology Builder.</span></span> <span data-ttu-id="2cce3-106">Кроме того, некоторые полные доменные имена, используемые в конфигурации Lync Server 2013, являются логическими, а не физическими (FQDN), поэтому перед публикацией требуется дополнительная настройка DNS.</span><span class="sxs-lookup"><span data-stu-id="2cce3-106">Additionally, some of the fully qualified domain names (FQDNs) used in the configuration of a Lync Server 2013 deployment are logical and not physical server FQDNs, so additional DNS configuration is required prior to publishing.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="2cce3-107">Lync Server 2013 не поддерживает домены, помеченные как единые.</span><span class="sxs-lookup"><span data-stu-id="2cce3-107">Lync Server 2013 does not support single-labeled domains.</span></span> <span data-ttu-id="2cce3-108">Например, лес с корневым доменом с именем <STRONG>contoso. local</STRONG> поддерживается, но корневой домен с именем <STRONG>Local</STRONG> не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="2cce3-108">For example, a forest with a root domain named <STRONG>contoso.local</STRONG> is supported, but a root domain named <STRONG>local</STRONG> is not supported.</span></span> <span data-ttu-id="2cce3-109">Подробные сведения о том, как настроить Windows для доменов с DNS-именами, сопоставленными с одной меткой, можно найти в статье 300684 (at <A class=uri href="http://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=300684"> http://go.microsoft.com/fwlink/p/?linkid=3052&amp; кбид = 300684</A>.</span><span class="sxs-lookup"><span data-stu-id="2cce3-109">For details, see Microsoft Knowledge Base article 300684, “Information about configuring Windows for domains with single-label DNS names,” at <A class=uri href="http://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=300684">http://go.microsoft.com/fwlink/p/?linkid=3052&amp;kbid=300684</A>.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="2cce3-110">Указанное имя должно быть идентично имени компьютера, настроенному на сервере.</span><span class="sxs-lookup"><span data-stu-id="2cce3-110">The name you specify must be identical to the computer name configured on the server.</span></span> <span data-ttu-id="2cce3-111">По умолчанию имя компьютера, не подключенного к домену, является коротким именем, а не FQDN.</span><span class="sxs-lookup"><span data-stu-id="2cce3-111">By default the computer name of a computer that is not joined to a domain is a short name, not an FQDN.</span></span> <span data-ttu-id="2cce3-112">Построитель топологии использует полные доменные имена, а не короткие имена.</span><span class="sxs-lookup"><span data-stu-id="2cce3-112">Topology Builder uses FQDNs, not short names.</span></span> <span data-ttu-id="2cce3-113">При назначении полных доменных имен серверам Lync Server, пограничным серверам и пулам <STRONG>Используйте только стандартные символы</STRONG> (включая A-z, a-z, 0 – 9 и дефисы).</span><span class="sxs-lookup"><span data-stu-id="2cce3-113"><STRONG>Use only standard characters</STRONG> (including A–Z, a–z, 0–9, and hyphens) when assigning FQDNs of your servers running Lync Server, Edge Servers, and pools.</span></span> <span data-ttu-id="2cce3-114">Не используйте символы Unicode или подчеркивания.</span><span class="sxs-lookup"><span data-stu-id="2cce3-114">Do not use Unicode characters or underscores.</span></span> <span data-ttu-id="2cce3-115">Нестандартные символы в полном доменном имени часто не поддерживаются внешними DNS-и общедоступными центрами сертификации (ЦС) (когда полное доменное имя должно быть назначено для SN в сертификате).</span><span class="sxs-lookup"><span data-stu-id="2cce3-115">Nonstandard characters in an FQDN are often not supported by external DNS and public certification authorities (CAs) (when the FQDN must be assigned to the SN in the certificate).</span></span>



</div>

<span data-ttu-id="2cce3-116">Перед тем как приступать к работе с топологией после ее развертывания, убедитесь в том, что созданы указанные ниже записи Active Directory и DNS (в зависимости от того, что требуется для определенных функций):</span><span class="sxs-lookup"><span data-stu-id="2cce3-116">Prior to operating the topology after it has been deployed, ensure that the following Active Directory and DNS records are created (as your needs for specific features dictate):</span></span>

  - <span data-ttu-id="2cce3-117">Все роли сервера, которые будут существовать в топологии, публикуются как объект Active Directory (это можно сделать с помощью присоединения компьютера к домену).</span><span class="sxs-lookup"><span data-stu-id="2cce3-117">Each server role that will exist in the topology is published as an Active Directory object (joining the computer to the domain will accomplish this).</span></span>

  - <span data-ttu-id="2cce3-118">Для каждого сервера существует запись DNS A.</span><span class="sxs-lookup"><span data-stu-id="2cce3-118">A DNS A Record exists for each server.</span></span>

  - <span data-ttu-id="2cce3-119">DNS SRV-запись для каждого домена SIP используется в том случае, если вы планируете использовать автоматический вход в систему \_для\_клиентов в форме сипинтерналтлс TCP. \<Домен\>SIP.</span><span class="sxs-lookup"><span data-stu-id="2cce3-119">A DNS SRV Record exists for each SIP domain if you plan to use automatic logon for clients in the form of \_sipinternaltls\_tcp.\<SIP domain\>.</span></span> <span data-ttu-id="2cce3-120">Если вы будете использовать ручную настройку для клиентов, эта запись не требуется.</span><span class="sxs-lookup"><span data-stu-id="2cce3-120">If you will use manual configuration for clients, this record is not necessary.</span></span>

  - <span data-ttu-id="2cce3-121">Запись DNS A для каждого настроенного простого URL-адреса, который обычно состоит из четырех: "Встреча", "Входящие", "лва" и "Планировщик".</span><span class="sxs-lookup"><span data-stu-id="2cce3-121">A DNS A Record for each configured simple URL, of which there are typically four: meet, dialin, lwa, and scheduler.</span></span> <span data-ttu-id="2cce3-122">Кроме того, существует простой URL-адрес администратора, который является специальным URL-адресом для доступа к панели управления Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2cce3-122">Additionally, there is the admin simple URL which is a special URL for access to the Lync Server 2013 Control Panel.</span></span>

  - <span data-ttu-id="2cce3-123">Сервер, на котором работает SQL Server, должен быть присоединен к домену и доступен на компьютере, с которого построитель топологии выполняет публикацию.</span><span class="sxs-lookup"><span data-stu-id="2cce3-123">The server running SQL Server must be joined to the domain, and reachable by the computer that Topology Builder is publishing from.</span></span>

<span data-ttu-id="2cce3-124">В таблице ниже приведены справочные архитектуры, представленные в разделе Планирование.</span><span class="sxs-lookup"><span data-stu-id="2cce3-124">The table follows the reference architectures presented in the Planning section.</span></span> <span data-ttu-id="2cce3-125">Дополнительные сведения можно найти [в разделе сценарии доступа внешних пользователей в Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md) в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="2cce3-125">For details, see [Scenarios for external user access in Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md) in the Planning documentation.</span></span>

<div id="sectionSection0" class="section">

### <a name="dns-records-required-for-the-front-end-pool"></a><span data-ttu-id="2cce3-126">DNS-записи, необходимые для пула переднего плана</span><span class="sxs-lookup"><span data-stu-id="2cce3-126">DNS Records Required for the Front End pool</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2cce3-127">Расположение</span><span class="sxs-lookup"><span data-stu-id="2cce3-127">Location</span></span></th>
<th><span data-ttu-id="2cce3-128">Тип</span><span class="sxs-lookup"><span data-stu-id="2cce3-128">Type</span></span></th>
<th><span data-ttu-id="2cce3-129">Полное доменное имя</span><span class="sxs-lookup"><span data-stu-id="2cce3-129">FQDN</span></span></th>
<th><span data-ttu-id="2cce3-130">Карты и примечания</span><span class="sxs-lookup"><span data-stu-id="2cce3-130">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2cce3-131">Внутренняя DNS</span><span class="sxs-lookup"><span data-stu-id="2cce3-131">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="2cce3-132">А</span><span class="sxs-lookup"><span data-stu-id="2cce3-132">A</span></span></p></td>
<td><p><span data-ttu-id="2cce3-133">pool01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="2cce3-133">pool01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="2cce3-134">Pool01 (Балансировка нагрузки DNS).</span><span class="sxs-lookup"><span data-stu-id="2cce3-134">Pool01 (DNS load balancing).</span></span> <span data-ttu-id="2cce3-135">Требуется запись DNS A для IP-адреса каждого сервера переднего плана в пуле, сопоставленная с полным доменным именем пула.</span><span class="sxs-lookup"><span data-stu-id="2cce3-135">Requires a DNS A record for the IP address of each Front End Server within the pool, mapping to the pool FQDN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2cce3-136">Внутренняя DNS</span><span class="sxs-lookup"><span data-stu-id="2cce3-136">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="2cce3-137">А</span><span class="sxs-lookup"><span data-stu-id="2cce3-137">A</span></span></p></td>
<td><p><span data-ttu-id="2cce3-138">pool01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="2cce3-138">pool01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="2cce3-139">Pool01 (виртуальный IP-адрес (VIP) балансировщика аппаратной балансировки нагрузки).</span><span class="sxs-lookup"><span data-stu-id="2cce3-139">Pool01 (virtual IP (VIP) of hardware load balancer).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2cce3-140">Внутренняя DNS</span><span class="sxs-lookup"><span data-stu-id="2cce3-140">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="2cce3-141">А</span><span class="sxs-lookup"><span data-stu-id="2cce3-141">A</span></span></p></td>
<td><p><span data-ttu-id="2cce3-142">fe01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="2cce3-142">fe01.contoso.net</span></span></p>
<p><span data-ttu-id="2cce3-143">fe02.contoso.net</span><span class="sxs-lookup"><span data-stu-id="2cce3-143">fe02.contoso.net</span></span></p>
<p><span data-ttu-id="2cce3-144">fe03.contoso.net</span><span class="sxs-lookup"><span data-stu-id="2cce3-144">fe03.contoso.net</span></span></p>
<p><span data-ttu-id="2cce3-145">…</span><span class="sxs-lookup"><span data-stu-id="2cce3-145">…</span></span></p></td>
<td><p><span data-ttu-id="2cce3-146">Сервер Pool01 переднего плана (узел 1).</span><span class="sxs-lookup"><span data-stu-id="2cce3-146">Pool01 Front End Server (NODE 1).</span></span></p>
<p><span data-ttu-id="2cce3-147">Сервер Pool01 переднего плана (узел 2).</span><span class="sxs-lookup"><span data-stu-id="2cce3-147">Pool01 Front End Server (NODE 2).</span></span></p>
<p><span data-ttu-id="2cce3-148">Сервер Pool01 переднего плана (узел 3).</span><span class="sxs-lookup"><span data-stu-id="2cce3-148">Pool01 Front End Server (NODE 3).</span></span></p>
<p><span data-ttu-id="2cce3-149">…</span><span class="sxs-lookup"><span data-stu-id="2cce3-149">…</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2cce3-150">Внутренняя DNS</span><span class="sxs-lookup"><span data-stu-id="2cce3-150">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="2cce3-151">А</span><span class="sxs-lookup"><span data-stu-id="2cce3-151">A</span></span></p></td>
<td><p><span data-ttu-id="2cce3-152">fe02.contoso.net</span><span class="sxs-lookup"><span data-stu-id="2cce3-152">fe02.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="2cce3-153">Сервер Pool01 переднего плана (узел 2).</span><span class="sxs-lookup"><span data-stu-id="2cce3-153">Pool01 Front End Server (NODE 2).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2cce3-154">Внутренняя DNS</span><span class="sxs-lookup"><span data-stu-id="2cce3-154">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="2cce3-155">А</span><span class="sxs-lookup"><span data-stu-id="2cce3-155">A</span></span></p></td>
<td><p><span data-ttu-id="2cce3-156">lsweb.contoso.net</span><span class="sxs-lookup"><span data-stu-id="2cce3-156">lsweb.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="2cce3-157">Pool01 (VIP) для веб-трафика между клиентом и сервером.</span><span class="sxs-lookup"><span data-stu-id="2cce3-157">Pool01 (VIP) for client-to-server web traffic.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2cce3-158">Внутренняя DNS</span><span class="sxs-lookup"><span data-stu-id="2cce3-158">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="2cce3-159">А</span><span class="sxs-lookup"><span data-stu-id="2cce3-159">A</span></span></p></td>
<td><p><span data-ttu-id="2cce3-160">sqlbe.contoso.net</span><span class="sxs-lookup"><span data-stu-id="2cce3-160">sqlbe.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="2cce3-161">Сервер Pool01 Server, на котором запущен SQL Server 2008 R2.</span><span class="sxs-lookup"><span data-stu-id="2cce3-161">Pool01 Back End Server running SQL Server 2008 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2cce3-162">Внутренняя DNS</span><span class="sxs-lookup"><span data-stu-id="2cce3-162">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="2cce3-163">А</span><span class="sxs-lookup"><span data-stu-id="2cce3-163">A</span></span></p></td>
<td><p><span data-ttu-id="2cce3-164">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="2cce3-164">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="2cce3-165">Требуется для Lync Phone Edition или для автоматического входа в систему клиентов без DNS SRV-записей и для строгого сопоставления доменов.</span><span class="sxs-lookup"><span data-stu-id="2cce3-165">Required for Lync Phone Edition, or automatic logon of clients without DNS SRV records, and for strict domain matching.</span></span> <span data-ttu-id="2cce3-166">Не является обязательным для всех случаев.</span><span class="sxs-lookup"><span data-stu-id="2cce3-166">Not required in all cases.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2cce3-167">Внутренняя DNS</span><span class="sxs-lookup"><span data-stu-id="2cce3-167">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="2cce3-168">А</span><span class="sxs-lookup"><span data-stu-id="2cce3-168">A</span></span></p></td>
<td><p><span data-ttu-id="2cce3-169">sip.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="2cce3-169">sip.fabrikam.com</span></span></p></td>
<td><p><span data-ttu-id="2cce3-170">Предполагается наличие второго домена SIP.</span><span class="sxs-lookup"><span data-stu-id="2cce3-170">Assumes a second SIP domain.</span></span> <span data-ttu-id="2cce3-171">Требуется для Lync Phone Edition, автоматического входа в систему клиентов без DNS SRV-записей и для строгого сопоставления доменов.</span><span class="sxs-lookup"><span data-stu-id="2cce3-171">Required for Lync Phone Edition, automatic logon of clients without DNS SRV records, and for strict domain matching.</span></span> <span data-ttu-id="2cce3-172">Не является обязательным для всех случаев.</span><span class="sxs-lookup"><span data-stu-id="2cce3-172">Not required in all cases.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2cce3-173">Внутренняя DNS</span><span class="sxs-lookup"><span data-stu-id="2cce3-173">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="2cce3-174">А</span><span class="sxs-lookup"><span data-stu-id="2cce3-174">A</span></span></p></td>
<td><p><span data-ttu-id="2cce3-175">dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="2cce3-175">dialin.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="2cce3-176">Простой URL-адрес для конференц-связи с телефонным подключением, опубликованный внутренне — сервер переднего плана (или режиссер, если он установлен) отвечает на простые URL-запросы.</span><span class="sxs-lookup"><span data-stu-id="2cce3-176">Simple URL for dial-in conferencing published internally – Front End Server (or Director, if installed) responds to simple URL queries.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2cce3-177">Внутренняя DNS</span><span class="sxs-lookup"><span data-stu-id="2cce3-177">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="2cce3-178">А</span><span class="sxs-lookup"><span data-stu-id="2cce3-178">A</span></span></p></td>
<td><p><span data-ttu-id="2cce3-179">meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="2cce3-179">meet.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="2cce3-180">Простой URL-адрес для конференций, опубликованный внутренне — сервер переднего плана (или режиссер, если он установлен) отвечает на простые URL-запросы.</span><span class="sxs-lookup"><span data-stu-id="2cce3-180">Simple URL for conferences published internally – Front End Server (or Director, if installed) responds to simple URL queries.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2cce3-181">Внутренняя DNS</span><span class="sxs-lookup"><span data-stu-id="2cce3-181">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="2cce3-182">А</span><span class="sxs-lookup"><span data-stu-id="2cce3-182">A</span></span></p></td>
<td><p><span data-ttu-id="2cce3-183">admin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="2cce3-183">admin.contoso.com</span></span></p>
<p><span data-ttu-id="2cce3-184">RAS</span><span class="sxs-lookup"><span data-stu-id="2cce3-184">admin</span></span></p></td>
<td><p><span data-ttu-id="2cce3-185">Необязательная запись, простой URL-адрес для панели управления Lync Server 2013, опубликованный внутренним образом сервер переднего плана (или режиссер, если он установлен) отвечает на простые URL-запросы.</span><span class="sxs-lookup"><span data-stu-id="2cce3-185">Optional record, simple URL for Lync Server 2013 Control Panel published internally - Front End Server (or Director, if installed) responds to simple URL queries.</span></span> <span data-ttu-id="2cce3-186">Рекомендуется только имя узла (имя домена не поддерживается).</span><span class="sxs-lookup"><span data-stu-id="2cce3-186">Host name only (no domain name) is recommended.</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="2cce3-187">VIP = виртуальный IP-адрес для подсистемы балансировки нагрузки для оборудования</span><span class="sxs-lookup"><span data-stu-id="2cce3-187">VIP = Virtual IP address for hardware load balancer</span></span>



</div>

</div>

<div>

## <a name="dns-srv-records-for-the-front-end-pool"></a><span data-ttu-id="2cce3-188">Записи DNS SRV для пула переднего плана</span><span class="sxs-lookup"><span data-stu-id="2cce3-188">DNS SRV Records for the Front End pool</span></span>


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
<th><span data-ttu-id="2cce3-189">Расположение</span><span class="sxs-lookup"><span data-stu-id="2cce3-189">Location</span></span></th>
<th><span data-ttu-id="2cce3-190">Тип</span><span class="sxs-lookup"><span data-stu-id="2cce3-190">Type</span></span></th>
<th><span data-ttu-id="2cce3-191">Полное доменное имя</span><span class="sxs-lookup"><span data-stu-id="2cce3-191">FQDN</span></span></th>
<th><span data-ttu-id="2cce3-192">Целевое полное доменное имя</span><span class="sxs-lookup"><span data-stu-id="2cce3-192">Target FQDN</span></span></th>
<th><span data-ttu-id="2cce3-193">Порт</span><span class="sxs-lookup"><span data-stu-id="2cce3-193">Port</span></span></th>
<th><span data-ttu-id="2cce3-194">Карты и примечания</span><span class="sxs-lookup"><span data-stu-id="2cce3-194">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2cce3-195">Внутренняя DNS</span><span class="sxs-lookup"><span data-stu-id="2cce3-195">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="2cce3-196">SRV</span><span class="sxs-lookup"><span data-stu-id="2cce3-196">SRV</span></span></p></td>
<td><p><span data-ttu-id="2cce3-197">_sipinternaltls. _tcp. contoso. com</span><span class="sxs-lookup"><span data-stu-id="2cce3-197">_sipinternaltls._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="2cce3-198">pool01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="2cce3-198">pool01.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="2cce3-199">5061</span><span class="sxs-lookup"><span data-stu-id="2cce3-199">5061</span></span></p></td>
<td><p><span data-ttu-id="2cce3-200">Требуется для автоматической настройки клиентов Lync 2013 для внутреннего использования.</span><span class="sxs-lookup"><span data-stu-id="2cce3-200">Required for automatic configuration of Lync 2013 clients to work internally.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2cce3-201">Внутренняя DNS</span><span class="sxs-lookup"><span data-stu-id="2cce3-201">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="2cce3-202">SRV</span><span class="sxs-lookup"><span data-stu-id="2cce3-202">SRV</span></span></p></td>
<td><p><span data-ttu-id="2cce3-203">_sipinternaltls. _tcp. fabrikam. com</span><span class="sxs-lookup"><span data-stu-id="2cce3-203">_sipinternaltls._tcp.fabrikam.com</span></span></p></td>
<td><p><span data-ttu-id="2cce3-204">pool01.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="2cce3-204">pool01.fabrikam.com</span></span></p></td>
<td><p><span data-ttu-id="2cce3-205">5061</span><span class="sxs-lookup"><span data-stu-id="2cce3-205">5061</span></span></p></td>
<td><p><span data-ttu-id="2cce3-206">Требуется для автоматической настройки клиентов Lync 2013 для внутреннего использования.</span><span class="sxs-lookup"><span data-stu-id="2cce3-206">Required for automatic configuration of Lync 2013 clients to work internally.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2cce3-207">Внутренняя DNS</span><span class="sxs-lookup"><span data-stu-id="2cce3-207">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="2cce3-208">SRV</span><span class="sxs-lookup"><span data-stu-id="2cce3-208">SRV</span></span></p></td>
<td><p><span data-ttu-id="2cce3-209">_ntp. _udp. contoso. com</span><span class="sxs-lookup"><span data-stu-id="2cce3-209">_ntp._udp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="2cce3-210">dc01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="2cce3-210">dc01.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="2cce3-211">123</span><span class="sxs-lookup"><span data-stu-id="2cce3-211">123</span></span></p></td>
<td><p><span data-ttu-id="2cce3-212">Для устройств с Lync Phone Edition требуется источник сетевого времени (NTP).</span><span class="sxs-lookup"><span data-stu-id="2cce3-212">Network Time Protocol (NTP) source required for devices running Lync Phone Edition.</span></span> <span data-ttu-id="2cce3-213">На внутреннем уровне это значение должно указывать на контроллер домена.</span><span class="sxs-lookup"><span data-stu-id="2cce3-213">Internally, this should point to the domain controller.</span></span> <span data-ttu-id="2cce3-214">Если контроллер домена не определен, он попытается использовать сервер NTP time.windows.com.</span><span class="sxs-lookup"><span data-stu-id="2cce3-214">If the domain controller is not defined, it will try to use the NTP server time.windows.com.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

