---
title: 'Lync Server 2013: требования к DNS для пула переднего плана'
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
ms.openlocfilehash: d0ace2b05b506b5bbf73177282747a66d212b38f
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42209585"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="dns-requirements-for-front-end-pool-in-lync-server-2013"></a><span data-ttu-id="07b3e-102">Требования к DNS для пула переднего плана в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="07b3e-102">DNS requirements for Front End pool in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="07b3e-103">_**Последнее изменение темы:** 2012-11-07_</span><span class="sxs-lookup"><span data-stu-id="07b3e-103">_**Topic Last Modified:** 2012-11-07_</span></span>

<span data-ttu-id="07b3e-104">Чтобы успешно выполнить данную процедуру, вы должны войти на сервер или в домен хотя бы в качестве члена группы администраторов домена или группы DnsAdmins.</span><span class="sxs-lookup"><span data-stu-id="07b3e-104">To successfully complete this procedure, you should be logged on to the server or domain minimally as a member of the Domain Admins group or a member of the DnsAdmins group.</span></span>

<span data-ttu-id="07b3e-105">Перед публикацией топологии в построителе топологий необходимо настроить требуемые записи службы доменных имен (DNS).</span><span class="sxs-lookup"><span data-stu-id="07b3e-105">You need to configure the required Domain Name System (DNS) records prior to publishing your topology in Topology Builder.</span></span> <span data-ttu-id="07b3e-106">Кроме того, некоторые полные доменные имена, используемые в конфигурации развертывания Lync Server 2013, являются логическими и не являются полными доменными именами, поэтому перед публикацией требуется дополнительная настройка DNS.</span><span class="sxs-lookup"><span data-stu-id="07b3e-106">Additionally, some of the fully qualified domain names (FQDNs) used in the configuration of a Lync Server 2013 deployment are logical and not physical server FQDNs, so additional DNS configuration is required prior to publishing.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="07b3e-107">Lync Server 2013 не поддерживает домены с одной меткой.</span><span class="sxs-lookup"><span data-stu-id="07b3e-107">Lync Server 2013 does not support single-labeled domains.</span></span> <span data-ttu-id="07b3e-108">Например, лес с корневым доменом <STRONG>contoso.local</STRONG> будет поддерживаться, а с корневым доменом <STRONG>local</STRONG> — нет.</span><span class="sxs-lookup"><span data-stu-id="07b3e-108">For example, a forest with a root domain named <STRONG>contoso.local</STRONG> is supported, but a root domain named <STRONG>local</STRONG> is not supported.</span></span> <span data-ttu-id="07b3e-109">Дополнительные сведения см. в статье 300684 базы знаний Майкрософт "сведения о настройке Windows для доменов с DNS-именем с одной меткой", "по <A class=uri href="https://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=300684"> https://go.microsoft.com/fwlink/p/?linkid=3052&amp; kbid = 300684</A>.</span><span class="sxs-lookup"><span data-stu-id="07b3e-109">For details, see Microsoft Knowledge Base article 300684, “Information about configuring Windows for domains with single-label DNS names,” at <A class=uri href="https://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=300684">https://go.microsoft.com/fwlink/p/?linkid=3052&amp;kbid=300684</A>.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="07b3e-110">Указанное имя должно совпадать с именем компьютера, заданным на сервере.</span><span class="sxs-lookup"><span data-stu-id="07b3e-110">The name you specify must be identical to the computer name configured on the server.</span></span> <span data-ttu-id="07b3e-111">По умолчанию именем компьютера, не присоединенного к домена,является короткое, а не полное доменное имя.</span><span class="sxs-lookup"><span data-stu-id="07b3e-111">By default the computer name of a computer that is not joined to a domain is a short name, not an FQDN.</span></span> <span data-ttu-id="07b3e-112">Построитель топологии использует полные доменные имена, а не короткие имена.</span><span class="sxs-lookup"><span data-stu-id="07b3e-112">Topology Builder uses FQDNs, not short names.</span></span> <span data-ttu-id="07b3e-113"><STRONG>Используйте только стандартные символы</STRONG> (включая a – z, a – z, 0 – 9 и дефисы) при назначении полных доменных имен серверов, на которых работает Lync Server, пограничные серверы и пулы.</span><span class="sxs-lookup"><span data-stu-id="07b3e-113"><STRONG>Use only standard characters</STRONG> (including A–Z, a–z, 0–9, and hyphens) when assigning FQDNs of your servers running Lync Server, Edge Servers, and pools.</span></span> <span data-ttu-id="07b3e-114">Не используйте символы Юникода и подчеркивания.</span><span class="sxs-lookup"><span data-stu-id="07b3e-114">Do not use Unicode characters or underscores.</span></span> <span data-ttu-id="07b3e-115">Наличие нестандартных символов в полном доменном имени часто не поддерживается внешней DNS и общими центрами сертификации (когда полное доменное имя должно быть назначено имени субъекта в сертификате).</span><span class="sxs-lookup"><span data-stu-id="07b3e-115">Nonstandard characters in an FQDN are often not supported by external DNS and public certification authorities (CAs) (when the FQDN must be assigned to the SN in the certificate).</span></span>



</div>

<span data-ttu-id="07b3e-116">Прежде чем приступать к работе с топологией, убедитесь, что созданы следующие записи Active Directory и DNS (по мере необходимости для определенных функций):</span><span class="sxs-lookup"><span data-stu-id="07b3e-116">Prior to operating the topology after it has been deployed, ensure that the following Active Directory and DNS records are created (as your needs for specific features dictate):</span></span>

  - <span data-ttu-id="07b3e-117">Каждая роль сервера, которая будет существовать в топологии, публикуется как объект Active Directory (это достигается путем присоединения компьютера к домену).</span><span class="sxs-lookup"><span data-stu-id="07b3e-117">Each server role that will exist in the topology is published as an Active Directory object (joining the computer to the domain will accomplish this).</span></span>

  - <span data-ttu-id="07b3e-118">Для каждого сервера существует DNS-запись A.</span><span class="sxs-lookup"><span data-stu-id="07b3e-118">A DNS A Record exists for each server.</span></span>

  - <span data-ttu-id="07b3e-119">Запись DNS SRV для каждого домена SIP, если вы планируете использовать автоматический вход для клиентов в форме \_сипинтерналтлс\_TCP. \<Домен\>SIP.</span><span class="sxs-lookup"><span data-stu-id="07b3e-119">A DNS SRV Record exists for each SIP domain if you plan to use automatic logon for clients in the form of \_sipinternaltls\_tcp.\<SIP domain\>.</span></span> <span data-ttu-id="07b3e-120">Если вы будете использовать ручную настройку для клиентов, эта запись не является обязательной.</span><span class="sxs-lookup"><span data-stu-id="07b3e-120">If you will use manual configuration for clients, this record is not necessary.</span></span>

  - <span data-ttu-id="07b3e-121">DNS-запись A для каждого настроенного простого URL-адреса, которых обычно существует четыре: meet, dialin, lwa и scheduler.</span><span class="sxs-lookup"><span data-stu-id="07b3e-121">A DNS A Record for each configured simple URL, of which there are typically four: meet, dialin, lwa, and scheduler.</span></span> <span data-ttu-id="07b3e-122">Кроме того, существует простой URL-адрес администратора, который является специальным URL-адресом для доступа к панели управления Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="07b3e-122">Additionally, there is the admin simple URL which is a special URL for access to the Lync Server 2013 Control Panel.</span></span>

  - <span data-ttu-id="07b3e-123">Сервер, на котором работает SQL Server, должен быть присоединен к домену и доступен компьютеру, с которого построитель топологий выполняет публикацию.</span><span class="sxs-lookup"><span data-stu-id="07b3e-123">The server running SQL Server must be joined to the domain, and reachable by the computer that Topology Builder is publishing from.</span></span>

<span data-ttu-id="07b3e-124">В таблице описаны эталонные архитектуры, представленные в разделе «Планирование».</span><span class="sxs-lookup"><span data-stu-id="07b3e-124">The table follows the reference architectures presented in the Planning section.</span></span> <span data-ttu-id="07b3e-125">Дополнительные сведения: [сценарии доступа внешних пользователей в Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md) в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="07b3e-125">For details, see [Scenarios for external user access in Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md) in the Planning documentation.</span></span>

<div id="sectionSection0" class="section">

### <a name="dns-records-required-for-the-front-end-pool"></a><span data-ttu-id="07b3e-126">Записи DNS, необходимые для пула переднего плана</span><span class="sxs-lookup"><span data-stu-id="07b3e-126">DNS Records Required for the Front End pool</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="07b3e-127">Расположение</span><span class="sxs-lookup"><span data-stu-id="07b3e-127">Location</span></span></th>
<th><span data-ttu-id="07b3e-128">Тип</span><span class="sxs-lookup"><span data-stu-id="07b3e-128">Type</span></span></th>
<th><span data-ttu-id="07b3e-129">FQDN</span><span class="sxs-lookup"><span data-stu-id="07b3e-129">FQDN</span></span></th>
<th><span data-ttu-id="07b3e-130">Сопоставление/комментарии</span><span class="sxs-lookup"><span data-stu-id="07b3e-130">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="07b3e-131">Внутренняя DNS</span><span class="sxs-lookup"><span data-stu-id="07b3e-131">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="07b3e-132">A</span><span class="sxs-lookup"><span data-stu-id="07b3e-132">A</span></span></p></td>
<td><p><span data-ttu-id="07b3e-133">pool01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="07b3e-133">pool01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="07b3e-134">Pool01 (балансировка нагрузки через DNS).</span><span class="sxs-lookup"><span data-stu-id="07b3e-134">Pool01 (DNS load balancing).</span></span> <span data-ttu-id="07b3e-135">Требуется запись A DNS для IP-адреса каждого сервера переднего плана в пуле, сопоставление с полным доменным именем пула.</span><span class="sxs-lookup"><span data-stu-id="07b3e-135">Requires a DNS A record for the IP address of each Front End Server within the pool, mapping to the pool FQDN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="07b3e-136">Внутренняя DNS</span><span class="sxs-lookup"><span data-stu-id="07b3e-136">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="07b3e-137">A</span><span class="sxs-lookup"><span data-stu-id="07b3e-137">A</span></span></p></td>
<td><p><span data-ttu-id="07b3e-138">pool01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="07b3e-138">pool01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="07b3e-139">Pool01 (виртуальный IP (VIP) оборудования подсистемы балансировки нагрузки).</span><span class="sxs-lookup"><span data-stu-id="07b3e-139">Pool01 (virtual IP (VIP) of hardware load balancer).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="07b3e-140">Внутренняя DNS</span><span class="sxs-lookup"><span data-stu-id="07b3e-140">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="07b3e-141">A</span><span class="sxs-lookup"><span data-stu-id="07b3e-141">A</span></span></p></td>
<td><p><span data-ttu-id="07b3e-142">fe01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="07b3e-142">fe01.contoso.net</span></span></p>
<p><span data-ttu-id="07b3e-143">fe02.contoso.net</span><span class="sxs-lookup"><span data-stu-id="07b3e-143">fe02.contoso.net</span></span></p>
<p><span data-ttu-id="07b3e-144">fe03.contoso.net</span><span class="sxs-lookup"><span data-stu-id="07b3e-144">fe03.contoso.net</span></span></p>
<p><span data-ttu-id="07b3e-145">…</span><span class="sxs-lookup"><span data-stu-id="07b3e-145">…</span></span></p></td>
<td><p><span data-ttu-id="07b3e-146">Сервер переднего плана Pool01 (узел 1).</span><span class="sxs-lookup"><span data-stu-id="07b3e-146">Pool01 Front End Server (NODE 1).</span></span></p>
<p><span data-ttu-id="07b3e-147">Сервер переднего плана Pool01 (узел 2).</span><span class="sxs-lookup"><span data-stu-id="07b3e-147">Pool01 Front End Server (NODE 2).</span></span></p>
<p><span data-ttu-id="07b3e-148">Сервер переднего плана Pool01 (узел 3).</span><span class="sxs-lookup"><span data-stu-id="07b3e-148">Pool01 Front End Server (NODE 3).</span></span></p>
<p><span data-ttu-id="07b3e-149">…</span><span class="sxs-lookup"><span data-stu-id="07b3e-149">…</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="07b3e-150">Внутренняя DNS</span><span class="sxs-lookup"><span data-stu-id="07b3e-150">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="07b3e-151">A</span><span class="sxs-lookup"><span data-stu-id="07b3e-151">A</span></span></p></td>
<td><p><span data-ttu-id="07b3e-152">fe02.contoso.net</span><span class="sxs-lookup"><span data-stu-id="07b3e-152">fe02.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="07b3e-153">Сервер переднего плана Pool01 (узел 2).</span><span class="sxs-lookup"><span data-stu-id="07b3e-153">Pool01 Front End Server (NODE 2).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="07b3e-154">Внутренняя DNS</span><span class="sxs-lookup"><span data-stu-id="07b3e-154">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="07b3e-155">A</span><span class="sxs-lookup"><span data-stu-id="07b3e-155">A</span></span></p></td>
<td><p><span data-ttu-id="07b3e-156">lsweb.contoso.net</span><span class="sxs-lookup"><span data-stu-id="07b3e-156">lsweb.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="07b3e-157">Pool01 (VIP) для веб-трафика от клиента на сервер.</span><span class="sxs-lookup"><span data-stu-id="07b3e-157">Pool01 (VIP) for client-to-server web traffic.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="07b3e-158">Внутренняя DNS</span><span class="sxs-lookup"><span data-stu-id="07b3e-158">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="07b3e-159">A</span><span class="sxs-lookup"><span data-stu-id="07b3e-159">A</span></span></p></td>
<td><p><span data-ttu-id="07b3e-160">sqlbe.contoso.net</span><span class="sxs-lookup"><span data-stu-id="07b3e-160">sqlbe.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="07b3e-161">Внутренний сервер Pool01, на котором работает SQL Server 2008 R2.</span><span class="sxs-lookup"><span data-stu-id="07b3e-161">Pool01 Back End Server running SQL Server 2008 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="07b3e-162">Внутренняя DNS</span><span class="sxs-lookup"><span data-stu-id="07b3e-162">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="07b3e-163">A</span><span class="sxs-lookup"><span data-stu-id="07b3e-163">A</span></span></p></td>
<td><p><span data-ttu-id="07b3e-164">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="07b3e-164">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="07b3e-165">Обязательный для Lync Phone Edition или автоматический вход в систему клиентов без DNS-записей SRV и для обязательного согласования доменов.</span><span class="sxs-lookup"><span data-stu-id="07b3e-165">Required for Lync Phone Edition, or automatic logon of clients without DNS SRV records, and for strict domain matching.</span></span> <span data-ttu-id="07b3e-166">Требуется не во всех случаях.</span><span class="sxs-lookup"><span data-stu-id="07b3e-166">Not required in all cases.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="07b3e-167">Внутренняя DNS</span><span class="sxs-lookup"><span data-stu-id="07b3e-167">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="07b3e-168">A</span><span class="sxs-lookup"><span data-stu-id="07b3e-168">A</span></span></p></td>
<td><p><span data-ttu-id="07b3e-169">sip.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="07b3e-169">sip.fabrikam.com</span></span></p></td>
<td><p><span data-ttu-id="07b3e-170">Подразумевает второй домен SIP.</span><span class="sxs-lookup"><span data-stu-id="07b3e-170">Assumes a second SIP domain.</span></span> <span data-ttu-id="07b3e-171">Обязательный для Lync Phone Edition, автоматический вход клиентов без записей DNS SRV и для обязательного согласования доменов.</span><span class="sxs-lookup"><span data-stu-id="07b3e-171">Required for Lync Phone Edition, automatic logon of clients without DNS SRV records, and for strict domain matching.</span></span> <span data-ttu-id="07b3e-172">Требуется не во всех случаях.</span><span class="sxs-lookup"><span data-stu-id="07b3e-172">Not required in all cases.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="07b3e-173">Внутренняя DNS</span><span class="sxs-lookup"><span data-stu-id="07b3e-173">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="07b3e-174">A</span><span class="sxs-lookup"><span data-stu-id="07b3e-174">A</span></span></p></td>
<td><p><span data-ttu-id="07b3e-175">dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="07b3e-175">dialin.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="07b3e-176">Простой URL-адрес для конференц-связи с телефонным подключением, опубликованный внутренним образом — сервер переднего плана (или директор, если он установлен) отвечает на простые URL-запросы.</span><span class="sxs-lookup"><span data-stu-id="07b3e-176">Simple URL for dial-in conferencing published internally – Front End Server (or Director, if installed) responds to simple URL queries.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="07b3e-177">Внутренняя DNS</span><span class="sxs-lookup"><span data-stu-id="07b3e-177">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="07b3e-178">A</span><span class="sxs-lookup"><span data-stu-id="07b3e-178">A</span></span></p></td>
<td><p><span data-ttu-id="07b3e-179">meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="07b3e-179">meet.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="07b3e-180">Простой URL-адрес для конференций, опубликованных внутренним образом — сервер переднего плана (или директор, если он установлен) отвечает на запросы простых URL-адресов.</span><span class="sxs-lookup"><span data-stu-id="07b3e-180">Simple URL for conferences published internally – Front End Server (or Director, if installed) responds to simple URL queries.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="07b3e-181">Внутренняя DNS</span><span class="sxs-lookup"><span data-stu-id="07b3e-181">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="07b3e-182">A</span><span class="sxs-lookup"><span data-stu-id="07b3e-182">A</span></span></p></td>
<td><p><span data-ttu-id="07b3e-183">admin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="07b3e-183">admin.contoso.com</span></span></p>
<p><span data-ttu-id="07b3e-184">группы</span><span class="sxs-lookup"><span data-stu-id="07b3e-184">admin</span></span></p></td>
<td><p><span data-ttu-id="07b3e-185">Необязательная запись, простой URL-адрес для панели управления Lync Server 2013, опубликованный внутренним сервером переднего плана (или режиссером, если он установлен), отвечает на запросы простых URL-адресов.</span><span class="sxs-lookup"><span data-stu-id="07b3e-185">Optional record, simple URL for Lync Server 2013 Control Panel published internally - Front End Server (or Director, if installed) responds to simple URL queries.</span></span> <span data-ttu-id="07b3e-186">Рекомендуется использовать только имя узла (без имени домена).</span><span class="sxs-lookup"><span data-stu-id="07b3e-186">Host name only (no domain name) is recommended.</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="07b3e-187">VIP — виртуальный IP-адрес для аппаратного средства балансировки нагрузки</span><span class="sxs-lookup"><span data-stu-id="07b3e-187">VIP = Virtual IP address for hardware load balancer</span></span>



</div>

</div>

<div>

## <a name="dns-srv-records-for-the-front-end-pool"></a><span data-ttu-id="07b3e-188">Записи DNS SRV для пула переднего плана</span><span class="sxs-lookup"><span data-stu-id="07b3e-188">DNS SRV Records for the Front End pool</span></span>


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
<th><span data-ttu-id="07b3e-189">Расположение</span><span class="sxs-lookup"><span data-stu-id="07b3e-189">Location</span></span></th>
<th><span data-ttu-id="07b3e-190">Тип</span><span class="sxs-lookup"><span data-stu-id="07b3e-190">Type</span></span></th>
<th><span data-ttu-id="07b3e-191">FQDN</span><span class="sxs-lookup"><span data-stu-id="07b3e-191">FQDN</span></span></th>
<th><span data-ttu-id="07b3e-192">Целевое полное доменное имя</span><span class="sxs-lookup"><span data-stu-id="07b3e-192">Target FQDN</span></span></th>
<th><span data-ttu-id="07b3e-193">Порт</span><span class="sxs-lookup"><span data-stu-id="07b3e-193">Port</span></span></th>
<th><span data-ttu-id="07b3e-194">Сопоставление/комментарии</span><span class="sxs-lookup"><span data-stu-id="07b3e-194">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="07b3e-195">Внутренняя DNS</span><span class="sxs-lookup"><span data-stu-id="07b3e-195">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="07b3e-196">SRV</span><span class="sxs-lookup"><span data-stu-id="07b3e-196">SRV</span></span></p></td>
<td><p><span data-ttu-id="07b3e-197">_sipinternaltls. _tcp. contoso. com</span><span class="sxs-lookup"><span data-stu-id="07b3e-197">_sipinternaltls._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="07b3e-198">pool01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="07b3e-198">pool01.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="07b3e-199">5061</span><span class="sxs-lookup"><span data-stu-id="07b3e-199">5061</span></span></p></td>
<td><p><span data-ttu-id="07b3e-200">Требуется для автоматической настройки клиентов Lync 2013 для внутреннего использования.</span><span class="sxs-lookup"><span data-stu-id="07b3e-200">Required for automatic configuration of Lync 2013 clients to work internally.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="07b3e-201">Внутренняя DNS</span><span class="sxs-lookup"><span data-stu-id="07b3e-201">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="07b3e-202">SRV</span><span class="sxs-lookup"><span data-stu-id="07b3e-202">SRV</span></span></p></td>
<td><p><span data-ttu-id="07b3e-203">_sipinternaltls. _tcp. fabrikam. com</span><span class="sxs-lookup"><span data-stu-id="07b3e-203">_sipinternaltls._tcp.fabrikam.com</span></span></p></td>
<td><p><span data-ttu-id="07b3e-204">pool01.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="07b3e-204">pool01.fabrikam.com</span></span></p></td>
<td><p><span data-ttu-id="07b3e-205">5061</span><span class="sxs-lookup"><span data-stu-id="07b3e-205">5061</span></span></p></td>
<td><p><span data-ttu-id="07b3e-206">Требуется для автоматической настройки клиентов Lync 2013 для внутреннего использования.</span><span class="sxs-lookup"><span data-stu-id="07b3e-206">Required for automatic configuration of Lync 2013 clients to work internally.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="07b3e-207">Внутренняя DNS</span><span class="sxs-lookup"><span data-stu-id="07b3e-207">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="07b3e-208">SRV</span><span class="sxs-lookup"><span data-stu-id="07b3e-208">SRV</span></span></p></td>
<td><p><span data-ttu-id="07b3e-209">_ntp. _udp. contoso. com</span><span class="sxs-lookup"><span data-stu-id="07b3e-209">_ntp._udp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="07b3e-210">dc01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="07b3e-210">dc01.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="07b3e-211">123</span><span class="sxs-lookup"><span data-stu-id="07b3e-211">123</span></span></p></td>
<td><p><span data-ttu-id="07b3e-212">Источник сетевого времени (NTP), необходимый для устройств, на которых работает Lync Phone Edition.</span><span class="sxs-lookup"><span data-stu-id="07b3e-212">Network Time Protocol (NTP) source required for devices running Lync Phone Edition.</span></span> <span data-ttu-id="07b3e-213">При внутреннем использовании она может указывать на контроллер домена.</span><span class="sxs-lookup"><span data-stu-id="07b3e-213">Internally, this should point to the domain controller.</span></span> <span data-ttu-id="07b3e-214">Если контроллер домена не задан, она пытается использовать сервер NTP time.windows.com.</span><span class="sxs-lookup"><span data-stu-id="07b3e-214">If the domain controller is not defined, it will try to use the NTP server time.windows.com.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

