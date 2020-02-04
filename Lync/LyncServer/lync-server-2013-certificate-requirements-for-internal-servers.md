---
title: 'Lync Server 2013: требования к сертификатам для внутренних серверов'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate requirements for internal servers
ms:assetid: 0444cdbd-538c-43b1-b9a1-9d7d6cf818d6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398094(v=OCS.15)
ms:contentKeyID: 48183270
ms.date: 02/17/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0351ab4f54273e1eccc09992ab933525cc2527ae
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736792"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="certificate-requirements-for-internal-servers-in-lync-server-2013"></a><span data-ttu-id="5a067-102">Требования к сертификатам для внутренних серверов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5a067-102">Certificate requirements for internal servers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5a067-103">_**Тема последнего изменения:** 2017-02-17_</span><span class="sxs-lookup"><span data-stu-id="5a067-103">_**Topic Last Modified:** 2017-02-17_</span></span>

<span data-ttu-id="5a067-104">Внутренние серверы, на которых работает Lync Server и которым требуются сертификаты, включают сервер Standard Edition Server, сервер доменных служб Enterprise Edition, сервер обновлений и режиссер.</span><span class="sxs-lookup"><span data-stu-id="5a067-104">Internal servers that are running Lync Server and that require certificates include Standard Edition server, Enterprise Edition Front End Server, Mediation Server, and Director.</span></span> <span data-ttu-id="5a067-105">В следующей таблице приведены требования к сертификатам для этих серверов.</span><span class="sxs-lookup"><span data-stu-id="5a067-105">The following table shows the certificate requirements for these servers.</span></span> <span data-ttu-id="5a067-106">Вы можете запросить эти сертификаты с помощью мастера сертификатов Lync Server.</span><span class="sxs-lookup"><span data-stu-id="5a067-106">You can use the Lync Server certificate wizard to request these certificates.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="5a067-107">Сертификаты с подстановочными знаками поддерживаются для альтернативных имен субъектов, связанных с простыми URL-адресами в пуле переднего плана, сервере переднего плана или режиссере.</span><span class="sxs-lookup"><span data-stu-id="5a067-107">Wildcard certificates are supported for the subject alternative names associated with the simple URLs on the Front End pool, Front End Server, or Director.</span></span> <span data-ttu-id="5a067-108">Дополнительные сведения о поддержке сертификата с подстановочными знаками можно найти <A href="lync-server-2013-wildcard-certificate-support.md">в разделе Поддержка сертификатов подстановочных знаков в Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="5a067-108">For details about wildcard certificate support, see <A href="lync-server-2013-wildcard-certificate-support.md">Wildcard certificate support in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="5a067-109">Несмотря на то, что для внутренних серверов рекомендуется использовать внутренний центр сертификации (ЦС) предприятия, вы также можете воспользоваться общедоступным центром сертификации.</span><span class="sxs-lookup"><span data-stu-id="5a067-109">Although an internal enterprise certification authority (CA) is recommended for internal servers, you can also use a public CA.</span></span> <span data-ttu-id="5a067-110">Список общедоступных центров сертификации, предоставляющих сертификаты, соответствующие конкретным требованиям для сертификатов с единым коммуникационным подключением (UC) и связанных с корпорацией Майкрософт, чтобы убедиться в том, что они работают с мастером сертификатов Lync Server, можно найти в статье Microsoft Knowledge Base 929395, "Партнеры сертификата единой системы [https://go.microsoft.com/fwlink/p/?linkId=202834](https://go.microsoft.com/fwlink/p/?linkid=202834)связи для Exchange Server и на коммуникационном сервере" at.</span><span class="sxs-lookup"><span data-stu-id="5a067-110">For a list of public CAs that provide certificates that comply with specific requirements for unified communications (UC) certificates and have partnered with Microsoft to ensure they work with the Lync Server Certificate Wizard, see article Microsoft Knowledge Base 929395, "Unified Communications Certificate Partners for Exchange Server and for Communications Server," at [https://go.microsoft.com/fwlink/p/?linkId=202834](https://go.microsoft.com/fwlink/p/?linkid=202834).</span></span>

<span data-ttu-id="5a067-111">Для связи с другими приложениями и серверами, такими как Exchange 2013, требуется сертификат, который поддерживается другими приложениями и продуктами.</span><span class="sxs-lookup"><span data-stu-id="5a067-111">Communication with other applications and servers, such as Exchange 2013, requires a certificate that is supported by the other applications and products.</span></span> <span data-ttu-id="5a067-112">В выпуске 2013, Lync Server 2013 и других серверных продуктах Microsoft, включая Exchange 2013 и SharePoint Server, поддерживается протокол OAuth для проверки подлинности и авторизации сервера и сервера.</span><span class="sxs-lookup"><span data-stu-id="5a067-112">For the 2013 release, Lync Server 2013 and other Microsoft server products, including Exchange 2013 and SharePoint Server, support the Open Authorization (OAuth) protocol for server-to-server authentication and authorization.</span></span> <span data-ttu-id="5a067-113">Дополнительные сведения можно найти [в разделе Управление проверкой подлинности серверов (OAuth) и партнерским приложением в Lync server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) в документации по развертыванию или документации по эксплуатации.</span><span class="sxs-lookup"><span data-stu-id="5a067-113">For details, see [Managing server-to-server authentication (OAuth) and partner applications in Lync Server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) in the Deployment documentation or the Operations documentation.</span></span>

<span data-ttu-id="5a067-114">Для подключений клиентов с операционной системой Windows 7, Windows Server 2008, операционной системой Windows Server 2008 R2, операционной системой Windows Vista и Microsoft Lync Phone Edition, Lync Server 2013 включает поддержку (но не требовать) сертификатов, подписанных с помощью криптографической хэш-функции SHA-256.</span><span class="sxs-lookup"><span data-stu-id="5a067-114">For connections from clients running Windows 7 operating system, Windows Server 2008 operating system, Windows Server 2008 R2 operating system, Windows Vista operating system, and Microsoft Lync Phone Edition, Lync Server 2013 includes support for (but does not require) certificates signed using the SHA-256 cryptographic hash function.</span></span> <span data-ttu-id="5a067-115">Для поддержки внешнего доступа с помощью SHA-256 внешний сертификат выдается общедоступным центром сертификации с помощью SHA-256.</span><span class="sxs-lookup"><span data-stu-id="5a067-115">To support external access using SHA-256, the external certificate is issued by a public CA using SHA-256.</span></span>

<span data-ttu-id="5a067-116">В приведенных ниже таблицах показаны требования к сертификатам для серверных пулов и серверов стандартных выпусков.</span><span class="sxs-lookup"><span data-stu-id="5a067-116">The following tables show certificate requirements by server role for Front End pools and Standard Edition servers.</span></span> <span data-ttu-id="5a067-117">Все они являются стандартными сертификатами веб-сервера, закрытым ключом, но не экспортируемым.</span><span class="sxs-lookup"><span data-stu-id="5a067-117">All these are standard web server certificates, private key, non-exportable.</span></span>

<span data-ttu-id="5a067-118">Обратите внимание на то, что при использовании мастера сертификатов для запроса сертификатов автоматически настраивается расширенное использование ключа (EKU) сервера.</span><span class="sxs-lookup"><span data-stu-id="5a067-118">Note that server enhanced key usage (EKU) is automatically configured when you use the certificate wizard to request certificates.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="5a067-119">Каждое понятное имя сертификата должно быть уникальным в магазине компьютера.</span><span class="sxs-lookup"><span data-stu-id="5a067-119">Each certificate Friendly Name must be unique in the computer store.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="5a067-120">Если вы настроили sipinternal.contoso.com или sipexternal.contoso.com в своей службе DNS, вам нужно будет добавить их в альтернативное имя субъекта сертификата.</span><span class="sxs-lookup"><span data-stu-id="5a067-120">If you have configured sipinternal.contoso.com or sipexternal.contoso.com in your DNS, you will need to add them in the certificate’s Subject Alternative Name.</span></span>



</div>

### <a name="certificates-for-standard-edition-server"></a><span data-ttu-id="5a067-121">Сертификаты для сервера Standard Edition</span><span class="sxs-lookup"><span data-stu-id="5a067-121">Certificates for Standard Edition Server</span></span>

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5a067-122">Сертификат</span><span class="sxs-lookup"><span data-stu-id="5a067-122">Certificate</span></span></th>
<th><span data-ttu-id="5a067-123">Имя субъекта/общее имя</span><span class="sxs-lookup"><span data-stu-id="5a067-123">Subject name/ Common name</span></span></th>
<th><span data-ttu-id="5a067-124">Альтернативное имя субъекта</span><span class="sxs-lookup"><span data-stu-id="5a067-124">Subject alternative name</span></span></th>
<th><span data-ttu-id="5a067-125">Пример</span><span class="sxs-lookup"><span data-stu-id="5a067-125">Example</span></span></th>
<th><span data-ttu-id="5a067-126">Комментарии</span><span class="sxs-lookup"><span data-stu-id="5a067-126">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5a067-127">"Default" (По умолчанию)</span><span class="sxs-lookup"><span data-stu-id="5a067-127">Default</span></span></p></td>
<td><p><span data-ttu-id="5a067-128">Полное доменное имя (FQDN) пула</span><span class="sxs-lookup"><span data-stu-id="5a067-128">Fully qualified domain name (FQDN) of the pool</span></span></p></td>
<td><p><span data-ttu-id="5a067-129">Полное доменное имя пула и полное доменное имя сервера</span><span class="sxs-lookup"><span data-stu-id="5a067-129">FQDN of the pool and the FQDN of the server</span></span></p>
<p><span data-ttu-id="5a067-130">Если существует несколько доменов SIP и включена автоматическая настройка клиента, мастер сертификатов обнаруживает все поддерживаемые полные доменные имена SIP.</span><span class="sxs-lookup"><span data-stu-id="5a067-130">If you have multiple SIP domains and have enabled automatic client configuration, the certificate wizard detects and adds each supported SIP domain FQDNs.</span></span></p>
<p><span data-ttu-id="5a067-131">Если этот пул является сервером для автоматического входа клиентов и для групповой политики требуется строгое сопоставление DNS-имен, также необходимы записи для sip.sipdomain (для каждого домена SIP).</span><span class="sxs-lookup"><span data-stu-id="5a067-131">If this pool is the auto-logon server for clients and strict Domain Name System (DNS) matching is required in group policy, you also need entries for sip.sipdomain (for each SIP domain you have).</span></span></p></td>
<td><p><span data-ttu-id="5a067-132">SN=se01.contoso.com; SAN=se01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="5a067-132">SN=se01.contoso.com; SAN=se01.contoso.com</span></span></p>
<p><span data-ttu-id="5a067-133">Если этот пул предназначен для сервера автоматического входа для клиентов, а в групповой политике требуется строгое сопоставление DNS, необходимо также добавить строки SAN=sip.contoso.com; SAN=sip.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="5a067-133">If this pool is the auto-logon server for clients and strict DNS matching is required in group policy, you also need SAN=sip.contoso.com; SAN=sip.fabrikam.com</span></span></p></td>
<td><p><span data-ttu-id="5a067-134">На сервере Standard Edition полное доменное имя сервера такое же, как полное доменное имя пула.</span><span class="sxs-lookup"><span data-stu-id="5a067-134">On Standard Edition server, the server FQDN is the same as the pool FQDN.</span></span></p>
<p><span data-ttu-id="5a067-135">Мастер обнаруживает все домены SIP, указанные вами во время установки, и автоматически добавляет их в альтернативное имя субъекта.</span><span class="sxs-lookup"><span data-stu-id="5a067-135">The wizard detects any SIP domains you specified during setup and automatically adds them to the subject alternative name.</span></span></p>
<p><span data-ttu-id="5a067-136">Вы также можете использовать этот сертификат для проверки подлинности между серверами.</span><span class="sxs-lookup"><span data-stu-id="5a067-136">You can also use this certificate for Server-to-Server Authentication.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5a067-137">Внутренняя сеть</span><span class="sxs-lookup"><span data-stu-id="5a067-137">Web internal</span></span></p></td>
<td><p><span data-ttu-id="5a067-138">Полное доменное имя сервера</span><span class="sxs-lookup"><span data-stu-id="5a067-138">FQDN of the server</span></span></p></td>
<td><p><span data-ttu-id="5a067-139">Каждое из следующих:</span><span class="sxs-lookup"><span data-stu-id="5a067-139">Each of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="5a067-140">Полное доменное имя внутренней сети (которое совпадает с полным доменным именем сервера)</span><span class="sxs-lookup"><span data-stu-id="5a067-140">Internal web FQDN (which is the same as the FQDN of the server)</span></span></p></li>
<li><p><span data-ttu-id="5a067-141">Простые URL-адреса собрания</span><span class="sxs-lookup"><span data-stu-id="5a067-141">Meet simple URLs</span></span></p></li>
<li><p><span data-ttu-id="5a067-142">Простой URL-адрес для телефонного подключения</span><span class="sxs-lookup"><span data-stu-id="5a067-142">Dial-in simple URL</span></span></p></li>
<li><p><span data-ttu-id="5a067-143">Простой URL-адрес администратора</span><span class="sxs-lookup"><span data-stu-id="5a067-143">Admin simple URL</span></span></p></li>
<li><p><span data-ttu-id="5a067-144">Или подстановочный знак для простых URL-адресов</span><span class="sxs-lookup"><span data-stu-id="5a067-144">Or, a wildcard entry for the simple URLs</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="5a067-145">SN=se01.contoso.com; SAN=se01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="5a067-145">SN=se01.contoso.com; SAN=se01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com</span></span></p>
<p><span data-ttu-id="5a067-146">Использование групповых сертификатов:</span><span class="sxs-lookup"><span data-stu-id="5a067-146">Using a wildcard certificate:</span></span></p>
<p><span data-ttu-id="5a067-147">SN=se01.contoso.com; SAN=se01.contoso.com; SAN=\*.contoso.com</span><span class="sxs-lookup"><span data-stu-id="5a067-147">SN=se01.contoso.com; SAN=se01.contoso.com; SAN=\*.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="5a067-148">Невозможно переопределить внутреннее ДОМЕНное имя веб-сайта в построителе топологии.</span><span class="sxs-lookup"><span data-stu-id="5a067-148">You cannot override the Internal web FQDN in Topology Builder.</span></span></p>
<p><span data-ttu-id="5a067-149">При наличии нескольких простых URL-адресов собрания необходимо включить их все как альтернативные имена субъекта.</span><span class="sxs-lookup"><span data-stu-id="5a067-149">If you have multiple Meet simple URLs, you must include all of them as subject alternative names.</span></span></p>
<p><span data-ttu-id="5a067-150">Для простых URL-адресов поддерживаются подстановочные записи.</span><span class="sxs-lookup"><span data-stu-id="5a067-150">Wildcard entries are supported for the simple URL entries.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5a067-151">Внешняя сеть</span><span class="sxs-lookup"><span data-stu-id="5a067-151">Web external</span></span></p></td>
<td><p><span data-ttu-id="5a067-152">Полное доменное имя сервера</span><span class="sxs-lookup"><span data-stu-id="5a067-152">FQDN of the server</span></span></p></td>
<td><p><span data-ttu-id="5a067-153">Каждое из следующих:</span><span class="sxs-lookup"><span data-stu-id="5a067-153">Each of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="5a067-154">Полное доменное имя внешней сети</span><span class="sxs-lookup"><span data-stu-id="5a067-154">External web FQDN</span></span></p></li>
<li><p><span data-ttu-id="5a067-155">Простой URL-адрес для телефонного подключения</span><span class="sxs-lookup"><span data-stu-id="5a067-155">Dial-in simple URL</span></span></p></li>
<li><p><span data-ttu-id="5a067-156">Простые URL-адреса собраний для каждого домена SIP</span><span class="sxs-lookup"><span data-stu-id="5a067-156">Meet simple URLs per SIP domain</span></span></p></li>
<li><p><span data-ttu-id="5a067-157">Или подстановочный знак для простых URL-адресов</span><span class="sxs-lookup"><span data-stu-id="5a067-157">Or, a wildcard entry for the simple URLs</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="5a067-158">SN=se01.contoso.com; SAN=webcon01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="5a067-158">SN=se01.contoso.com; SAN=webcon01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com</span></span></p>
<p><span data-ttu-id="5a067-159">Использование групповых сертификатов:</span><span class="sxs-lookup"><span data-stu-id="5a067-159">Using a wildcard certificate:</span></span></p>
<p><span data-ttu-id="5a067-160">SN=se01.contoso.com; SAN=webcon01.contoso.com; SAN=\*.contoso.com</span><span class="sxs-lookup"><span data-stu-id="5a067-160">SN=se01.contoso.com; SAN=webcon01.contoso.com; SAN=\*.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="5a067-161">При наличии нескольких простых URL-адресов собрания необходимо включить их все как альтернативные имена субъекта.</span><span class="sxs-lookup"><span data-stu-id="5a067-161">If you have multiple Meet simple URLs, you must include all of them as subject alternative names.</span></span></p>
<p><span data-ttu-id="5a067-162">Для простых URL-адресов поддерживаются подстановочные записи.</span><span class="sxs-lookup"><span data-stu-id="5a067-162">Wildcard entries are supported for the simple URL entries.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="certificates-for-front-end-server-in-a-front-end-pool"></a><span data-ttu-id="5a067-163">Сертификаты для сервера переднего плана в пуле переднего плана</span><span class="sxs-lookup"><span data-stu-id="5a067-163">Certificates for Front End Server in a Front End Pool</span></span>

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5a067-164">Сертификат</span><span class="sxs-lookup"><span data-stu-id="5a067-164">Certificate</span></span></th>
<th><span data-ttu-id="5a067-165">Имя субъекта/общее имя</span><span class="sxs-lookup"><span data-stu-id="5a067-165">Subject name/ Common name</span></span></th>
<th><span data-ttu-id="5a067-166">Альтернативное имя субъекта</span><span class="sxs-lookup"><span data-stu-id="5a067-166">Subject alternative name</span></span></th>
<th><span data-ttu-id="5a067-167">Пример</span><span class="sxs-lookup"><span data-stu-id="5a067-167">Example</span></span></th>
<th><span data-ttu-id="5a067-168">Комментарии</span><span class="sxs-lookup"><span data-stu-id="5a067-168">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5a067-169">"Default" (По умолчанию)</span><span class="sxs-lookup"><span data-stu-id="5a067-169">Default</span></span></p></td>
<td><p><span data-ttu-id="5a067-170">Полное доменное имя пула</span><span class="sxs-lookup"><span data-stu-id="5a067-170">FQDN of the pool</span></span></p></td>
<td><p><span data-ttu-id="5a067-171">Полное доменное имя пула и полного доменного имени сервера.</span><span class="sxs-lookup"><span data-stu-id="5a067-171">FQDN of the pool and FQDN of the server.</span></span></p>
<p><span data-ttu-id="5a067-172">Если существует несколько доменов SIP и включена автоматическая настройка клиента, мастер сертификатов обнаруживает все поддерживаемые полные доменные имена SIP.</span><span class="sxs-lookup"><span data-stu-id="5a067-172">If you have multiple SIP domains and have enabled automatic client configuration, the certificate wizard detects and adds each supported SIP domain FQDNs.</span></span></p>
<p><span data-ttu-id="5a067-173">Если этот пул является сервером автоматического входа для клиентов и в групповой политике требуется строгое сопоставление DNS, вам также понадобятся записи SIP. сипдомаин (для каждого домена SIP).</span><span class="sxs-lookup"><span data-stu-id="5a067-173">If this pool is the auto-logon server for clients and strict DNS matching is required in group policy, you also need entries for sip.sipdomain (for each SIP domain you have).</span></span></p></td>
<td><p><span data-ttu-id="5a067-174">SN=eepool.contoso.com; SAN=eepool.contoso.com; SAN=ee01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="5a067-174">SN=eepool.contoso.com; SAN=eepool.contoso.com; SAN=ee01.contoso.com</span></span></p>
<p><span data-ttu-id="5a067-175">Если этот пул предназначен для сервера автоматического входа для клиентов, а в групповой политике требуется строгое сопоставление DNS, необходимо также добавить строки SAN=sip.contoso.com; SAN=sip.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="5a067-175">If this pool is the auto-logon server for clients and strict DNS matching is required in group policy, you also need SAN=sip.contoso.com; SAN=sip.fabrikam.com</span></span></p></td>
<td><p><span data-ttu-id="5a067-176">Мастер обнаруживает все домены SIP, указанные вами во время установки, и автоматически добавляет их в альтернативное имя субъекта.</span><span class="sxs-lookup"><span data-stu-id="5a067-176">The wizard detects any SIP domains you specified during setup and automatically adds them to the subject alternative name.</span></span></p>
<p><span data-ttu-id="5a067-177">Вы также можете использовать этот сертификат для проверки подлинности между серверами.</span><span class="sxs-lookup"><span data-stu-id="5a067-177">You can also use this certificate for Server-to-Server Authentication.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5a067-178">Внутренние веб-страницы</span><span class="sxs-lookup"><span data-stu-id="5a067-178">Web Internal</span></span></p></td>
<td><p><span data-ttu-id="5a067-179">Полное доменное имя пула</span><span class="sxs-lookup"><span data-stu-id="5a067-179">FQDN of the pool</span></span></p></td>
<td><p><span data-ttu-id="5a067-180">Каждое из следующих:</span><span class="sxs-lookup"><span data-stu-id="5a067-180">Each of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="5a067-181">Полное доменное имя внутренней сети (которое НЕ совпадает с полным доменным именем сервера)</span><span class="sxs-lookup"><span data-stu-id="5a067-181">Internal web FQDN (which is NOT the same as the FQDN of the server)</span></span></p></li>
<li><p><span data-ttu-id="5a067-182">Полное доменное имя сервера</span><span class="sxs-lookup"><span data-stu-id="5a067-182">Server FQDN</span></span></p></li>
<li><p><span data-ttu-id="5a067-183">Полное доменное имя пула Lync</span><span class="sxs-lookup"><span data-stu-id="5a067-183">Lync pool FQDN</span></span></p></li>
<li><p><span data-ttu-id="5a067-184">Простые URL-адреса собрания</span><span class="sxs-lookup"><span data-stu-id="5a067-184">Meet simple URLs</span></span></p></li>
<li><p><span data-ttu-id="5a067-185">Простой URL-адрес для телефонного подключения</span><span class="sxs-lookup"><span data-stu-id="5a067-185">Dial-in simple URL</span></span></p></li>
<li><p><span data-ttu-id="5a067-186">Простой URL-адрес администратора</span><span class="sxs-lookup"><span data-stu-id="5a067-186">Admin simple URL</span></span></p></li>
<li><p><span data-ttu-id="5a067-187">Или подстановочный знак для простых URL-адресов</span><span class="sxs-lookup"><span data-stu-id="5a067-187">Or, a wildcard entry for the simple URLs</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="5a067-188">SN=ee01.contoso.com; SAN=ee01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="5a067-188">SN=ee01.contoso.com; SAN=ee01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com</span></span></p>
<p><span data-ttu-id="5a067-189">Использование групповых сертификатов:</span><span class="sxs-lookup"><span data-stu-id="5a067-189">Using a wildcard certificate:</span></span></p>
<p><span data-ttu-id="5a067-190">SN=ee01.contoso.com; SAN=ee01.contoso.com; SAN=\*.contoso.com</span><span class="sxs-lookup"><span data-stu-id="5a067-190">SN=ee01.contoso.com; SAN=ee01.contoso.com; SAN=\*.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="5a067-191">При наличии нескольких простых URL-адресов собрания необходимо включить их все как альтернативные имена субъекта.</span><span class="sxs-lookup"><span data-stu-id="5a067-191">If you have multiple Meet simple URLs, you must include all of them as subject alternative names.</span></span></p>
<p><span data-ttu-id="5a067-192">Для простых URL-адресов поддерживаются подстановочные записи.</span><span class="sxs-lookup"><span data-stu-id="5a067-192">Wildcard entries are supported for the simple URL entries.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5a067-193">Внешняя сеть</span><span class="sxs-lookup"><span data-stu-id="5a067-193">Web external</span></span></p></td>
<td><p><span data-ttu-id="5a067-194">Полное доменное имя пула</span><span class="sxs-lookup"><span data-stu-id="5a067-194">FQDN of the pool</span></span></p></td>
<td><p><span data-ttu-id="5a067-195">Каждое из следующих:</span><span class="sxs-lookup"><span data-stu-id="5a067-195">Each of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="5a067-196">Полное доменное имя внешней сети</span><span class="sxs-lookup"><span data-stu-id="5a067-196">External web FQDN</span></span></p></li>
<li><p><span data-ttu-id="5a067-197">Простой URL-адрес для телефонного подключения</span><span class="sxs-lookup"><span data-stu-id="5a067-197">Dial-in simple URL</span></span></p></li>
<li><p><span data-ttu-id="5a067-198">Простой URL-адрес администратора</span><span class="sxs-lookup"><span data-stu-id="5a067-198">Admin simple URL</span></span></p></li>
<li><p><span data-ttu-id="5a067-199">Или подстановочный знак для простых URL-адресов</span><span class="sxs-lookup"><span data-stu-id="5a067-199">Or, a wildcard entry for the simple URLs</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="5a067-200">SN=ee01.contoso.com; SAN=webcon01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="5a067-200">SN=ee01.contoso.com; SAN=webcon01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com</span></span></p>
<p><span data-ttu-id="5a067-201">Использование групповых сертификатов:</span><span class="sxs-lookup"><span data-stu-id="5a067-201">Using a wildcard certificate:</span></span></p>
<p><span data-ttu-id="5a067-202">SN=ee01.contoso.com; SAN=webcon01.contoso.com; SAN=\*.contoso.com</span><span class="sxs-lookup"><span data-stu-id="5a067-202">SN=ee01.contoso.com; SAN=webcon01.contoso.com; SAN=\*.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="5a067-203">При наличии нескольких простых URL-адресов собрания необходимо включить их все как альтернативные имена субъекта.</span><span class="sxs-lookup"><span data-stu-id="5a067-203">If you have multiple Meet simple URLs, you must include all of them as subject alternative names.</span></span></p>
<p><span data-ttu-id="5a067-204">Для простых URL-адресов поддерживаются подстановочные записи.</span><span class="sxs-lookup"><span data-stu-id="5a067-204">Wildcard entries are supported for the simple URL entries.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="certificates-for-director"></a><span data-ttu-id="5a067-205">Сертификаты для режиссера</span><span class="sxs-lookup"><span data-stu-id="5a067-205">Certificates for Director</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5a067-206">Сертификат</span><span class="sxs-lookup"><span data-stu-id="5a067-206">Certificate</span></span></th>
<th><span data-ttu-id="5a067-207">Имя субъекта/общее имя</span><span class="sxs-lookup"><span data-stu-id="5a067-207">Subject name/ Common name</span></span></th>
<th><span data-ttu-id="5a067-208">Альтернативное имя субъекта</span><span class="sxs-lookup"><span data-stu-id="5a067-208">Subject alternative name</span></span></th>
<th><span data-ttu-id="5a067-209">Пример</span><span class="sxs-lookup"><span data-stu-id="5a067-209">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5a067-210">"Default" (По умолчанию)</span><span class="sxs-lookup"><span data-stu-id="5a067-210">Default</span></span></p></td>
<td><p><span data-ttu-id="5a067-211">Полное доменное имя директора пула</span><span class="sxs-lookup"><span data-stu-id="5a067-211">FQDN of the Director pool</span></span></p></td>
<td><p><span data-ttu-id="5a067-212">Полное доменное имя режиссера в качестве полного доменного имени директора пула</span><span class="sxs-lookup"><span data-stu-id="5a067-212">FQDN of the Director, FQDN of the Director pool</span></span></p>
<p><span data-ttu-id="5a067-213">Если этот пул является сервером автоматического входа для клиентов и в групповой политике требуется строгое сопоставление DNS, вам также понадобятся записи SIP. сипдомаин (для каждого домена SIP).</span><span class="sxs-lookup"><span data-stu-id="5a067-213">If this pool is the auto-logon server for clients and strict DNS matching is required in group policy, you also need entries for sip.sipdomain (for each SIP domain you have).</span></span></p></td>
<td><p><span data-ttu-id="5a067-214">SN = dir-pool.contoso.com; Сеть хранения данных = Dir-pool.contoso.com; SAN = dir01. contoso. com</span><span class="sxs-lookup"><span data-stu-id="5a067-214">SN=dir-pool.contoso.com; SAN=dir-pool.contoso.com; SAN=dir01.contoso.com</span></span></p>
<p><span data-ttu-id="5a067-215">Если этот пул директоров предназначен для сервера автоматического входа для клиентов, а в групповой политике требуется строгое сопоставление DNS, необходимо также добавить строки SAN=contoso.com SIP; SAN=fabrikam.com SIP.</span><span class="sxs-lookup"><span data-stu-id="5a067-215">If this Director pool is the auto-logon server for clients and strict DNS matching is required in group policy, you also need SAN=sip.contoso.com; SAN=sip.fabrikam.com</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5a067-216">Внутренние веб-страницы</span><span class="sxs-lookup"><span data-stu-id="5a067-216">Web Internal</span></span></p></td>
<td><p><span data-ttu-id="5a067-217">Полное доменное имя сервера</span><span class="sxs-lookup"><span data-stu-id="5a067-217">FQDN of the server</span></span></p></td>
<td><p><span data-ttu-id="5a067-218">Каждое из следующих:</span><span class="sxs-lookup"><span data-stu-id="5a067-218">Each of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="5a067-219">Полное доменное имя внутренней сети (которое совпадает с полным доменным именем сервера)</span><span class="sxs-lookup"><span data-stu-id="5a067-219">Internal web FQDN (which is the same as the FQDN of the server)</span></span></p></li>
<li><p><span data-ttu-id="5a067-220">Полное доменное имя сервера</span><span class="sxs-lookup"><span data-stu-id="5a067-220">Server FQDN</span></span></p></li>
<li><p><span data-ttu-id="5a067-221">Полное доменное имя пула Lync</span><span class="sxs-lookup"><span data-stu-id="5a067-221">Lync pool FQDN</span></span></p></li>
<li><p><span data-ttu-id="5a067-222">Простые URL-адреса собрания</span><span class="sxs-lookup"><span data-stu-id="5a067-222">Meet simple URLs</span></span></p></li>
<li><p><span data-ttu-id="5a067-223">Простой URL-адрес для телефонного подключения</span><span class="sxs-lookup"><span data-stu-id="5a067-223">Dial-in simple URL</span></span></p></li>
<li><p><span data-ttu-id="5a067-224">Простой URL-адрес администратора</span><span class="sxs-lookup"><span data-stu-id="5a067-224">Admin simple URL</span></span></p></li>
<li><p><span data-ttu-id="5a067-225">Или подстановочный знак для простых URL-адресов</span><span class="sxs-lookup"><span data-stu-id="5a067-225">Or, a wildcard entry for the simple URLs</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="5a067-226">SN=dir01.contoso.com; SAN=dir01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="5a067-226">SN=dir01.contoso.com; SAN=dir01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com</span></span></p>
<p><span data-ttu-id="5a067-227">SN=dir01.contoso.com; SAN=dir01.contoso.com SAN=\*.contoso.com</span><span class="sxs-lookup"><span data-stu-id="5a067-227">SN=dir01.contoso.com; SAN=dir01.contoso.com SAN=\*.contoso.com</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5a067-228">Внешняя сеть</span><span class="sxs-lookup"><span data-stu-id="5a067-228">Web external</span></span></p></td>
<td><p><span data-ttu-id="5a067-229">Полное доменное имя сервера</span><span class="sxs-lookup"><span data-stu-id="5a067-229">FQDN of the server</span></span></p></td>
<td><p><span data-ttu-id="5a067-230">Каждое из следующих:</span><span class="sxs-lookup"><span data-stu-id="5a067-230">Each of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="5a067-231">Полное доменное имя внешней сети</span><span class="sxs-lookup"><span data-stu-id="5a067-231">External web FQDN</span></span></p></li>
<li><p><span data-ttu-id="5a067-232">Простой URL-адрес для телефонного подключения</span><span class="sxs-lookup"><span data-stu-id="5a067-232">Dial-in simple URL</span></span></p></li>
<li><p><span data-ttu-id="5a067-233">Простой URL-адрес администратора</span><span class="sxs-lookup"><span data-stu-id="5a067-233">Admin simple URL</span></span></p></li>
<li><p><span data-ttu-id="5a067-234">Или подстановочный знак для простых URL-адресов</span><span class="sxs-lookup"><span data-stu-id="5a067-234">Or, a wildcard entry for the simple URLs</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="5a067-235">Полное доменное имя внешней сети директора должно отличаться от пула переднего плана и сервера переднего плана.</span><span class="sxs-lookup"><span data-stu-id="5a067-235">The Director external web FQDN must be different from the Front End pool or Front End Server.</span></span></p>
<p><span data-ttu-id="5a067-236">SN=dir01.contoso.com; SAN=directorwebcon01.contoso.com SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="5a067-236">SN=dir01.contoso.com; SAN=directorwebcon01.contoso.com SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com</span></span></p>
<p><span data-ttu-id="5a067-237">SN=dir01.contoso.com; SAN=directorwebcon01.contoso.com SAN=\*.contoso.com</span><span class="sxs-lookup"><span data-stu-id="5a067-237">SN=dir01.contoso.com; SAN=directorwebcon01.contoso.com SAN=\*.contoso.com</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="5a067-238">Если у вас есть независимый пул серверов с исправлениями, для каждого из них необходимы сертификаты, указанные в приведенной ниже таблице.</span><span class="sxs-lookup"><span data-stu-id="5a067-238">If you have a stand-alone Mediation Server pool, the Mediation Servers in it each need the certificates listed in the following table.</span></span> <span data-ttu-id="5a067-239">Если вы развернули сервер обновлений с помощью серверов переднего плана, вам достаточно сертификатов, указанных в таблице "сертификаты для сервера переднего плана в пуле переднего плана", описанном выше в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="5a067-239">If you collocate Mediation Server with the Front End Servers, the certificates listed in the “Certificates for Front End Server in Front End Pool” table earlier in this topic are sufficient.</span></span>

### <a name="certificates-for-stand-alone-mediation-server"></a><span data-ttu-id="5a067-240">Сертификаты для сервера автономных обновлений</span><span class="sxs-lookup"><span data-stu-id="5a067-240">Certificates for Stand-alone Mediation Server</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5a067-241">Сертификат</span><span class="sxs-lookup"><span data-stu-id="5a067-241">Certificate</span></span></th>
<th><span data-ttu-id="5a067-242">Имя субъекта/общее имя</span><span class="sxs-lookup"><span data-stu-id="5a067-242">Subject name/ Common name</span></span></th>
<th><span data-ttu-id="5a067-243">Альтернативное имя субъекта</span><span class="sxs-lookup"><span data-stu-id="5a067-243">Subject alternative name</span></span></th>
<th><span data-ttu-id="5a067-244">Пример</span><span class="sxs-lookup"><span data-stu-id="5a067-244">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5a067-245">"Default" (По умолчанию)</span><span class="sxs-lookup"><span data-stu-id="5a067-245">Default</span></span></p></td>
<td><p><span data-ttu-id="5a067-246">Полное доменное имя пула</span><span class="sxs-lookup"><span data-stu-id="5a067-246">FQDN of the pool</span></span></p></td>
<td><p><span data-ttu-id="5a067-247">Полное доменное имя пула</span><span class="sxs-lookup"><span data-stu-id="5a067-247">FQDN of the pool</span></span></p>
<p><span data-ttu-id="5a067-248">Полное доменное имя сервера участника пула</span><span class="sxs-lookup"><span data-stu-id="5a067-248">FQDN of pool member server</span></span></p></td>
<td><p><span data-ttu-id="5a067-249">SN=medsvr-pool.contoso.net; SAN=medsvr-pool.contoso.net; SAN=medsvr01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="5a067-249">SN=medsvr-pool.contoso.net; SAN=medsvr-pool.contoso.net; SAN=medsvr01.contoso.net</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="certificates-for-survivable-branch-appliance"></a><span data-ttu-id="5a067-250">Сертификаты для устройства с бесперебойной подразделением</span><span class="sxs-lookup"><span data-stu-id="5a067-250">Certificates for Survivable Branch Appliance</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5a067-251">Сертификат</span><span class="sxs-lookup"><span data-stu-id="5a067-251">Certificate</span></span></th>
<th><span data-ttu-id="5a067-252">Имя субъекта/общее имя</span><span class="sxs-lookup"><span data-stu-id="5a067-252">Subject name/ Common name</span></span></th>
<th><span data-ttu-id="5a067-253">Альтернативное имя субъекта</span><span class="sxs-lookup"><span data-stu-id="5a067-253">Subject alternative name</span></span></th>
<th><span data-ttu-id="5a067-254">Пример</span><span class="sxs-lookup"><span data-stu-id="5a067-254">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5a067-255">"Default" (По умолчанию)</span><span class="sxs-lookup"><span data-stu-id="5a067-255">Default</span></span></p></td>
<td><p><span data-ttu-id="5a067-256">Полное доменное имя устройства</span><span class="sxs-lookup"><span data-stu-id="5a067-256">FQDN of the appliance</span></span></p></td>
<td><p><span data-ttu-id="5a067-257">Установка. &lt;сипдомаин&gt; (требуется одна запись для каждого домена SIP)</span><span class="sxs-lookup"><span data-stu-id="5a067-257">SIP.&lt;sipdomain&gt; (need one entry per SIP domain)</span></span></p></td>
<td><p><span data-ttu-id="5a067-258">SN=sba01.contoso.net; SAN=sip.contoso.com; SAN=sip.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="5a067-258">SN=sba01.contoso.net; SAN=sip.contoso.com; SAN=sip.fabrikam.com</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a><span data-ttu-id="5a067-259">См. также</span><span class="sxs-lookup"><span data-stu-id="5a067-259">See Also</span></span>


[<span data-ttu-id="5a067-260">Поддержка групповых сертификатов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5a067-260">Wildcard certificate support in Lync Server 2013</span></span>](lync-server-2013-wildcard-certificate-support.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

