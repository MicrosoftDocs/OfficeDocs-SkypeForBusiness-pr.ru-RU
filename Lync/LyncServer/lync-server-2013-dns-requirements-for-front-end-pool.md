---
title: 'Lync Server 2013: требования к DNS для пула переднего плана'
description: 'Lync Server 2013: требования к DNS для пула переднего плана.'
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
ms.openlocfilehash: bfce90eccb8c8dff94d4122c96c4ca68ea9150f1
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48574335"
---
# <a name="dns-requirements-for-front-end-pool-in-lync-server-2013"></a><span data-ttu-id="399a6-103">Требования к DNS для пула переднего плана в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="399a6-103">DNS requirements for Front End pool in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="399a6-104">_**Последнее изменение темы:** 2012-11-07_</span><span class="sxs-lookup"><span data-stu-id="399a6-104">_**Topic Last Modified:** 2012-11-07_</span></span>

<span data-ttu-id="399a6-105">Чтобы успешно выполнить данную процедуру, вы должны войти на сервер или в домен хотя бы в качестве члена группы администраторов домена или группы DnsAdmins.</span><span class="sxs-lookup"><span data-stu-id="399a6-105">To successfully complete this procedure, you should be logged on to the server or domain minimally as a member of the Domain Admins group or a member of the DnsAdmins group.</span></span>

<span data-ttu-id="399a6-106">Перед публикацией топологии в построителе топологий необходимо настроить требуемые записи службы доменных имен (DNS).</span><span class="sxs-lookup"><span data-stu-id="399a6-106">You need to configure the required Domain Name System (DNS) records prior to publishing your topology in Topology Builder.</span></span> <span data-ttu-id="399a6-107">Кроме того, некоторые полные доменные имена, используемые в конфигурации развертывания Lync Server 2013, являются логическими и не являются полными доменными именами, поэтому перед публикацией требуется дополнительная настройка DNS.</span><span class="sxs-lookup"><span data-stu-id="399a6-107">Additionally, some of the fully qualified domain names (FQDNs) used in the configuration of a Lync Server 2013 deployment are logical and not physical server FQDNs, so additional DNS configuration is required prior to publishing.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="399a6-108">Lync Server 2013 не поддерживает домены с одной меткой.</span><span class="sxs-lookup"><span data-stu-id="399a6-108">Lync Server 2013 does not support single-labeled domains.</span></span> <span data-ttu-id="399a6-109">Например, лес с корневым доменом <STRONG>contoso.local</STRONG> будет поддерживаться, а с корневым доменом <STRONG>local</STRONG> — нет.</span><span class="sxs-lookup"><span data-stu-id="399a6-109">For example, a forest with a root domain named <STRONG>contoso.local</STRONG> is supported, but a root domain named <STRONG>local</STRONG> is not supported.</span></span> <span data-ttu-id="399a6-110">Дополнительные сведения см. в статье 300684 базы знаний Майкрософт "сведения о настройке Windows для доменов с DNS-именем с одной меткой", "по <A class=uri href="https://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=300684"> https://go.microsoft.com/fwlink/p/?linkid=3052&amp ; kbid = 300684</A>.</span><span class="sxs-lookup"><span data-stu-id="399a6-110">For details, see Microsoft Knowledge Base article 300684, “Information about configuring Windows for domains with single-label DNS names,” at <A class=uri href="https://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=300684">https://go.microsoft.com/fwlink/p/?linkid=3052&amp;kbid=300684</A>.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="399a6-111">Указанное имя должно совпадать с именем компьютера, заданным на сервере.</span><span class="sxs-lookup"><span data-stu-id="399a6-111">The name you specify must be identical to the computer name configured on the server.</span></span> <span data-ttu-id="399a6-112">По умолчанию именем компьютера, не присоединенного к домена,является короткое, а не полное доменное имя.</span><span class="sxs-lookup"><span data-stu-id="399a6-112">By default the computer name of a computer that is not joined to a domain is a short name, not an FQDN.</span></span> <span data-ttu-id="399a6-113">Построитель топологии использует полные доменные имена, а не короткие имена.</span><span class="sxs-lookup"><span data-stu-id="399a6-113">Topology Builder uses FQDNs, not short names.</span></span> <span data-ttu-id="399a6-114"><STRONG>Используйте только стандартные символы</STRONG> (включая a – z, a – z, 0 – 9 и дефисы) при назначении полных доменных имен серверов, на которых работает Lync Server, пограничные серверы и пулы.</span><span class="sxs-lookup"><span data-stu-id="399a6-114"><STRONG>Use only standard characters</STRONG> (including A–Z, a–z, 0–9, and hyphens) when assigning FQDNs of your servers running Lync Server, Edge Servers, and pools.</span></span> <span data-ttu-id="399a6-115">Не используйте символы Юникода и подчеркивания.</span><span class="sxs-lookup"><span data-stu-id="399a6-115">Do not use Unicode characters or underscores.</span></span> <span data-ttu-id="399a6-116">Наличие нестандартных символов в полном доменном имени часто не поддерживается внешней DNS и общими центрами сертификации (когда полное доменное имя должно быть назначено имени субъекта в сертификате).</span><span class="sxs-lookup"><span data-stu-id="399a6-116">Nonstandard characters in an FQDN are often not supported by external DNS and public certification authorities (CAs) (when the FQDN must be assigned to the SN in the certificate).</span></span>



</div>

<span data-ttu-id="399a6-117">Прежде чем приступать к работе с топологией, убедитесь, что созданы следующие записи Active Directory и DNS (по мере необходимости для определенных функций):</span><span class="sxs-lookup"><span data-stu-id="399a6-117">Prior to operating the topology after it has been deployed, ensure that the following Active Directory and DNS records are created (as your needs for specific features dictate):</span></span>

  - <span data-ttu-id="399a6-118">Каждая роль сервера, которая будет существовать в топологии, публикуется как объект Active Directory (это достигается путем присоединения компьютера к домену).</span><span class="sxs-lookup"><span data-stu-id="399a6-118">Each server role that will exist in the topology is published as an Active Directory object (joining the computer to the domain will accomplish this).</span></span>

  - <span data-ttu-id="399a6-119">Для каждого сервера существует DNS-запись A.</span><span class="sxs-lookup"><span data-stu-id="399a6-119">A DNS A Record exists for each server.</span></span>

  - <span data-ttu-id="399a6-120">Запись DNS SRV для каждого домена SIP, если вы планируете использовать автоматический вход для клиентов в форме \_ сипинтерналтлс \_ TCP. \<SIP domain\> .</span><span class="sxs-lookup"><span data-stu-id="399a6-120">A DNS SRV Record exists for each SIP domain if you plan to use automatic logon for clients in the form of \_sipinternaltls\_tcp.\<SIP domain\>.</span></span> <span data-ttu-id="399a6-121">Если вы будете использовать ручную настройку для клиентов, эта запись не является обязательной.</span><span class="sxs-lookup"><span data-stu-id="399a6-121">If you will use manual configuration for clients, this record is not necessary.</span></span>

  - <span data-ttu-id="399a6-122">DNS-запись A для каждого настроенного простого URL-адреса, которых обычно существует четыре: meet, dialin, lwa и scheduler.</span><span class="sxs-lookup"><span data-stu-id="399a6-122">A DNS A Record for each configured simple URL, of which there are typically four: meet, dialin, lwa, and scheduler.</span></span> <span data-ttu-id="399a6-123">Кроме того, существует простой URL-адрес администратора, который является специальным URL-адресом для доступа к панели управления Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="399a6-123">Additionally, there is the admin simple URL which is a special URL for access to the Lync Server 2013 Control Panel.</span></span>

  - <span data-ttu-id="399a6-124">Сервер, на котором работает SQL Server, должен быть присоединен к домену и доступен компьютеру, с которого построитель топологий выполняет публикацию.</span><span class="sxs-lookup"><span data-stu-id="399a6-124">The server running SQL Server must be joined to the domain, and reachable by the computer that Topology Builder is publishing from.</span></span>

<span data-ttu-id="399a6-125">В таблице описаны эталонные архитектуры, представленные в разделе «Планирование».</span><span class="sxs-lookup"><span data-stu-id="399a6-125">The table follows the reference architectures presented in the Planning section.</span></span> <span data-ttu-id="399a6-126">Дополнительные сведения: [сценарии доступа внешних пользователей в Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md) в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="399a6-126">For details, see [Scenarios for external user access in Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md) in the Planning documentation.</span></span>

<div id="sectionSection0" class="section">

### <a name="dns-records-required-for-the-front-end-pool"></a><span data-ttu-id="399a6-127">Записи DNS, необходимые для пула переднего плана</span><span class="sxs-lookup"><span data-stu-id="399a6-127">DNS Records Required for the Front End pool</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="399a6-128">Расположение</span><span class="sxs-lookup"><span data-stu-id="399a6-128">Location</span></span></th>
<th><span data-ttu-id="399a6-129">Тип</span><span class="sxs-lookup"><span data-stu-id="399a6-129">Type</span></span></th>
<th><span data-ttu-id="399a6-130">полное доменное имя;</span><span class="sxs-lookup"><span data-stu-id="399a6-130">FQDN</span></span></th>
<th><span data-ttu-id="399a6-131">Сопоставление/комментарии</span><span class="sxs-lookup"><span data-stu-id="399a6-131">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="399a6-132">Внутренняя DNS</span><span class="sxs-lookup"><span data-stu-id="399a6-132">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="399a6-133">A</span><span class="sxs-lookup"><span data-stu-id="399a6-133">A</span></span></p></td>
<td><p><span data-ttu-id="399a6-134">pool01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="399a6-134">pool01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="399a6-135">Pool01 (балансировка нагрузки через DNS).</span><span class="sxs-lookup"><span data-stu-id="399a6-135">Pool01 (DNS load balancing).</span></span> <span data-ttu-id="399a6-136">Требуется запись A DNS для IP-адреса каждого сервера переднего плана в пуле, сопоставление с полным доменным именем пула.</span><span class="sxs-lookup"><span data-stu-id="399a6-136">Requires a DNS A record for the IP address of each Front End Server within the pool, mapping to the pool FQDN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="399a6-137">Внутренняя DNS</span><span class="sxs-lookup"><span data-stu-id="399a6-137">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="399a6-138">A</span><span class="sxs-lookup"><span data-stu-id="399a6-138">A</span></span></p></td>
<td><p><span data-ttu-id="399a6-139">pool01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="399a6-139">pool01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="399a6-140">Pool01 (виртуальный IP (VIP) оборудования подсистемы балансировки нагрузки).</span><span class="sxs-lookup"><span data-stu-id="399a6-140">Pool01 (virtual IP (VIP) of hardware load balancer).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="399a6-141">Внутренняя DNS</span><span class="sxs-lookup"><span data-stu-id="399a6-141">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="399a6-142">A</span><span class="sxs-lookup"><span data-stu-id="399a6-142">A</span></span></p></td>
<td><p><span data-ttu-id="399a6-143">fe01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="399a6-143">fe01.contoso.net</span></span></p>
<p><span data-ttu-id="399a6-144">fe02.contoso.net</span><span class="sxs-lookup"><span data-stu-id="399a6-144">fe02.contoso.net</span></span></p>
<p><span data-ttu-id="399a6-145">fe03.contoso.net</span><span class="sxs-lookup"><span data-stu-id="399a6-145">fe03.contoso.net</span></span></p>
<p><span data-ttu-id="399a6-146">…</span><span class="sxs-lookup"><span data-stu-id="399a6-146">…</span></span></p></td>
<td><p><span data-ttu-id="399a6-147">Сервер переднего плана Pool01 (узел 1).</span><span class="sxs-lookup"><span data-stu-id="399a6-147">Pool01 Front End Server (NODE 1).</span></span></p>
<p><span data-ttu-id="399a6-148">Сервер переднего плана Pool01 (узел 2).</span><span class="sxs-lookup"><span data-stu-id="399a6-148">Pool01 Front End Server (NODE 2).</span></span></p>
<p><span data-ttu-id="399a6-149">Сервер переднего плана Pool01 (узел 3).</span><span class="sxs-lookup"><span data-stu-id="399a6-149">Pool01 Front End Server (NODE 3).</span></span></p>
<p><span data-ttu-id="399a6-150">…</span><span class="sxs-lookup"><span data-stu-id="399a6-150">…</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="399a6-151">Внутренняя DNS</span><span class="sxs-lookup"><span data-stu-id="399a6-151">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="399a6-152">A</span><span class="sxs-lookup"><span data-stu-id="399a6-152">A</span></span></p></td>
<td><p><span data-ttu-id="399a6-153">fe02.contoso.net</span><span class="sxs-lookup"><span data-stu-id="399a6-153">fe02.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="399a6-154">Сервер переднего плана Pool01 (узел 2).</span><span class="sxs-lookup"><span data-stu-id="399a6-154">Pool01 Front End Server (NODE 2).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="399a6-155">Внутренняя DNS</span><span class="sxs-lookup"><span data-stu-id="399a6-155">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="399a6-156">A</span><span class="sxs-lookup"><span data-stu-id="399a6-156">A</span></span></p></td>
<td><p><span data-ttu-id="399a6-157">lsweb.contoso.net</span><span class="sxs-lookup"><span data-stu-id="399a6-157">lsweb.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="399a6-158">Pool01 (VIP) для веб-трафика от клиента на сервер.</span><span class="sxs-lookup"><span data-stu-id="399a6-158">Pool01 (VIP) for client-to-server web traffic.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="399a6-159">Внутренняя DNS</span><span class="sxs-lookup"><span data-stu-id="399a6-159">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="399a6-160">A</span><span class="sxs-lookup"><span data-stu-id="399a6-160">A</span></span></p></td>
<td><p><span data-ttu-id="399a6-161">sqlbe.contoso.net</span><span class="sxs-lookup"><span data-stu-id="399a6-161">sqlbe.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="399a6-162">Внутренний сервер Pool01, на котором работает SQL Server 2008 R2.</span><span class="sxs-lookup"><span data-stu-id="399a6-162">Pool01 Back End Server running SQL Server 2008 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="399a6-163">Внутренняя DNS</span><span class="sxs-lookup"><span data-stu-id="399a6-163">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="399a6-164">A</span><span class="sxs-lookup"><span data-stu-id="399a6-164">A</span></span></p></td>
<td><p><span data-ttu-id="399a6-165">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="399a6-165">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="399a6-166">Обязательный для Lync Phone Edition или автоматический вход в систему клиентов без DNS-записей SRV и для обязательного согласования доменов.</span><span class="sxs-lookup"><span data-stu-id="399a6-166">Required for Lync Phone Edition, or automatic logon of clients without DNS SRV records, and for strict domain matching.</span></span> <span data-ttu-id="399a6-167">Требуется не во всех случаях.</span><span class="sxs-lookup"><span data-stu-id="399a6-167">Not required in all cases.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="399a6-168">Внутренняя DNS</span><span class="sxs-lookup"><span data-stu-id="399a6-168">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="399a6-169">A</span><span class="sxs-lookup"><span data-stu-id="399a6-169">A</span></span></p></td>
<td><p><span data-ttu-id="399a6-170">sip.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="399a6-170">sip.fabrikam.com</span></span></p></td>
<td><p><span data-ttu-id="399a6-171">Подразумевает второй домен SIP.</span><span class="sxs-lookup"><span data-stu-id="399a6-171">Assumes a second SIP domain.</span></span> <span data-ttu-id="399a6-172">Обязательный для Lync Phone Edition, автоматический вход клиентов без записей DNS SRV и для обязательного согласования доменов.</span><span class="sxs-lookup"><span data-stu-id="399a6-172">Required for Lync Phone Edition, automatic logon of clients without DNS SRV records, and for strict domain matching.</span></span> <span data-ttu-id="399a6-173">Требуется не во всех случаях.</span><span class="sxs-lookup"><span data-stu-id="399a6-173">Not required in all cases.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="399a6-174">Внутренняя DNS</span><span class="sxs-lookup"><span data-stu-id="399a6-174">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="399a6-175">A</span><span class="sxs-lookup"><span data-stu-id="399a6-175">A</span></span></p></td>
<td><p><span data-ttu-id="399a6-176">dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="399a6-176">dialin.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="399a6-177">Простой URL-адрес для конференц-связи с телефонным подключением, опубликованный внутренним образом — сервер переднего плана (или директор, если он установлен) отвечает на простые URL-запросы.</span><span class="sxs-lookup"><span data-stu-id="399a6-177">Simple URL for dial-in conferencing published internally – Front End Server (or Director, if installed) responds to simple URL queries.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="399a6-178">Внутренняя DNS</span><span class="sxs-lookup"><span data-stu-id="399a6-178">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="399a6-179">A</span><span class="sxs-lookup"><span data-stu-id="399a6-179">A</span></span></p></td>
<td><p><span data-ttu-id="399a6-180">meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="399a6-180">meet.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="399a6-181">Простой URL-адрес для конференций, опубликованных внутренним образом — сервер переднего плана (или директор, если он установлен) отвечает на запросы простых URL-адресов.</span><span class="sxs-lookup"><span data-stu-id="399a6-181">Simple URL for conferences published internally – Front End Server (or Director, if installed) responds to simple URL queries.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="399a6-182">Внутренняя DNS</span><span class="sxs-lookup"><span data-stu-id="399a6-182">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="399a6-183">A</span><span class="sxs-lookup"><span data-stu-id="399a6-183">A</span></span></p></td>
<td><p><span data-ttu-id="399a6-184">admin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="399a6-184">admin.contoso.com</span></span></p>
<p><span data-ttu-id="399a6-185">группы</span><span class="sxs-lookup"><span data-stu-id="399a6-185">admin</span></span></p></td>
<td><p><span data-ttu-id="399a6-186">Необязательная запись, простой URL-адрес для панели управления Lync Server 2013, опубликованный внутренним сервером переднего плана (или режиссером, если он установлен), отвечает на запросы простых URL-адресов.</span><span class="sxs-lookup"><span data-stu-id="399a6-186">Optional record, simple URL for Lync Server 2013 Control Panel published internally - Front End Server (or Director, if installed) responds to simple URL queries.</span></span> <span data-ttu-id="399a6-187">Рекомендуется использовать только имя узла (без имени домена).</span><span class="sxs-lookup"><span data-stu-id="399a6-187">Host name only (no domain name) is recommended.</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="399a6-188">VIP — виртуальный IP-адрес для аппаратного средства балансировки нагрузки</span><span class="sxs-lookup"><span data-stu-id="399a6-188">VIP = Virtual IP address for hardware load balancer</span></span>



</div>

</div>

<div>

## <a name="dns-srv-records-for-the-front-end-pool"></a><span data-ttu-id="399a6-189">Записи DNS SRV для пула переднего плана</span><span class="sxs-lookup"><span data-stu-id="399a6-189">DNS SRV Records for the Front End pool</span></span>


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
<th><span data-ttu-id="399a6-190">Расположение</span><span class="sxs-lookup"><span data-stu-id="399a6-190">Location</span></span></th>
<th><span data-ttu-id="399a6-191">Тип</span><span class="sxs-lookup"><span data-stu-id="399a6-191">Type</span></span></th>
<th><span data-ttu-id="399a6-192">полное доменное имя;</span><span class="sxs-lookup"><span data-stu-id="399a6-192">FQDN</span></span></th>
<th><span data-ttu-id="399a6-193">Целевое полное доменное имя</span><span class="sxs-lookup"><span data-stu-id="399a6-193">Target FQDN</span></span></th>
<th><span data-ttu-id="399a6-194">Порт</span><span class="sxs-lookup"><span data-stu-id="399a6-194">Port</span></span></th>
<th><span data-ttu-id="399a6-195">Сопоставление/комментарии</span><span class="sxs-lookup"><span data-stu-id="399a6-195">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="399a6-196">Внутренняя DNS</span><span class="sxs-lookup"><span data-stu-id="399a6-196">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="399a6-197">SRV</span><span class="sxs-lookup"><span data-stu-id="399a6-197">SRV</span></span></p></td>
<td><p><span data-ttu-id="399a6-198">_sipinternaltls _sipinternaltls._tcp. contoso. com</span><span class="sxs-lookup"><span data-stu-id="399a6-198">_sipinternaltls._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="399a6-199">pool01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="399a6-199">pool01.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="399a6-200">5061</span><span class="sxs-lookup"><span data-stu-id="399a6-200">5061</span></span></p></td>
<td><p><span data-ttu-id="399a6-201">Требуется для автоматической настройки клиентов Lync 2013 для внутреннего использования.</span><span class="sxs-lookup"><span data-stu-id="399a6-201">Required for automatic configuration of Lync 2013 clients to work internally.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="399a6-202">Внутренняя DNS</span><span class="sxs-lookup"><span data-stu-id="399a6-202">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="399a6-203">SRV</span><span class="sxs-lookup"><span data-stu-id="399a6-203">SRV</span></span></p></td>
<td><p><span data-ttu-id="399a6-204">_sipinternaltls _sipinternaltls._tcp. fabrikam. com</span><span class="sxs-lookup"><span data-stu-id="399a6-204">_sipinternaltls._tcp.fabrikam.com</span></span></p></td>
<td><p><span data-ttu-id="399a6-205">pool01.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="399a6-205">pool01.fabrikam.com</span></span></p></td>
<td><p><span data-ttu-id="399a6-206">5061</span><span class="sxs-lookup"><span data-stu-id="399a6-206">5061</span></span></p></td>
<td><p><span data-ttu-id="399a6-207">Требуется для автоматической настройки клиентов Lync 2013 для внутреннего использования.</span><span class="sxs-lookup"><span data-stu-id="399a6-207">Required for automatic configuration of Lync 2013 clients to work internally.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="399a6-208">Внутренняя DNS</span><span class="sxs-lookup"><span data-stu-id="399a6-208">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="399a6-209">SRV</span><span class="sxs-lookup"><span data-stu-id="399a6-209">SRV</span></span></p></td>
<td><p><span data-ttu-id="399a6-210">_ntp _ntp._udp. contoso. com</span><span class="sxs-lookup"><span data-stu-id="399a6-210">_ntp._udp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="399a6-211">dc01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="399a6-211">dc01.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="399a6-212">123</span><span class="sxs-lookup"><span data-stu-id="399a6-212">123</span></span></p></td>
<td><p><span data-ttu-id="399a6-213">Источник сетевого времени (NTP), необходимый для устройств, на которых работает Lync Phone Edition.</span><span class="sxs-lookup"><span data-stu-id="399a6-213">Network Time Protocol (NTP) source required for devices running Lync Phone Edition.</span></span> <span data-ttu-id="399a6-214">При внутреннем использовании она может указывать на контроллер домена.</span><span class="sxs-lookup"><span data-stu-id="399a6-214">Internally, this should point to the domain controller.</span></span> <span data-ttu-id="399a6-215">Если контроллер домена не задан, она пытается использовать сервер NTP time.windows.com.</span><span class="sxs-lookup"><span data-stu-id="399a6-215">If the domain controller is not defined, it will try to use the NTP server time.windows.com.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

