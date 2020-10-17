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
ms.openlocfilehash: c56554a26e5f64089a766300f375039409680578
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48526246"
---
# <a name="certificate-requirements-for-internal-servers-in-lync-server-2013"></a><span data-ttu-id="65457-102">Требования к сертификатам для внутренних серверов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="65457-102">Certificate requirements for internal servers in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="65457-103">_**Последнее изменение темы:** 2017-02-17_</span><span class="sxs-lookup"><span data-stu-id="65457-103">_**Topic Last Modified:** 2017-02-17_</span></span>

<span data-ttu-id="65457-104">Внутренние серверы, на которых работает Lync Server и которым необходимы сертификаты, включают сервер Standard Edition Server, сервер переднего плана Enterprise Edition, сервер-посредник и директор.</span><span class="sxs-lookup"><span data-stu-id="65457-104">Internal servers that are running Lync Server and that require certificates include Standard Edition server, Enterprise Edition Front End Server, Mediation Server, and Director.</span></span> <span data-ttu-id="65457-105">В следующей таблице показаны требования к сертификатам для этих серверов.</span><span class="sxs-lookup"><span data-stu-id="65457-105">The following table shows the certificate requirements for these servers.</span></span> <span data-ttu-id="65457-106">Вы можете запросить эти сертификаты с помощью мастера сертификатов Lync Server.</span><span class="sxs-lookup"><span data-stu-id="65457-106">You can use the Lync Server certificate wizard to request these certificates.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="65457-107">Для альтернативных имен субъектов, связанных с простыми URL-адресами в интерфейсном пуле, на сервере переднего плана или в директоре, поддерживаются подстановочные сертификаты.</span><span class="sxs-lookup"><span data-stu-id="65457-107">Wildcard certificates are supported for the subject alternative names associated with the simple URLs on the Front End pool, Front End Server, or Director.</span></span> <span data-ttu-id="65457-108">Дополнительные сведения о поддержке сертификатов с использованием подстановочных знаков приведены <A href="lync-server-2013-wildcard-certificate-support.md">в разделе Поддержка сертификатов с использованием подстановочных знаков в Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="65457-108">For details about wildcard certificate support, see <A href="lync-server-2013-wildcard-certificate-support.md">Wildcard certificate support in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="65457-109">Хотя для внутренних серверов рекомендуется внутренний центр сертификации (ЦС) предприятия, можно также использовать общедоступный ЦС.</span><span class="sxs-lookup"><span data-stu-id="65457-109">Although an internal enterprise certification authority (CA) is recommended for internal servers, you can also use a public CA.</span></span> <span data-ttu-id="65457-110">Список общедоступных центров сертификации, которые предоставляют сертификаты, соответствующие определенным требованиям для сертификатов Объединенных коммуникаций (UC) и партнерской корпорации Майкрософт, чтобы убедиться, что они работают с мастером сертификатов Lync Server, ознакомьтесь со статьей Microsoft Knowledge Base 929395, "Объединенные партнеры сертификатов для Exchange Server и Communications Server" по адресу [https://go.microsoft.com/fwlink/p/?linkId=202834](https://go.microsoft.com/fwlink/p/?linkid=202834) .</span><span class="sxs-lookup"><span data-stu-id="65457-110">For a list of public CAs that provide certificates that comply with specific requirements for unified communications (UC) certificates and have partnered with Microsoft to ensure they work with the Lync Server Certificate Wizard, see article Microsoft Knowledge Base 929395, "Unified Communications Certificate Partners for Exchange Server and for Communications Server," at [https://go.microsoft.com/fwlink/p/?linkId=202834](https://go.microsoft.com/fwlink/p/?linkid=202834).</span></span>

<span data-ttu-id="65457-111">Для связи с другими приложениями и серверами, например Exchange 2013, необходим сертификат, который поддерживается другими приложениями и продуктами.</span><span class="sxs-lookup"><span data-stu-id="65457-111">Communication with other applications and servers, such as Exchange 2013, requires a certificate that is supported by the other applications and products.</span></span> <span data-ttu-id="65457-112">Для выпусков 2013, Lync Server 2013 и других серверных продуктов Майкрософт, в том числе Exchange 2013 и SharePoint Server, поддерживается протокол OAuth для проверки подлинности и авторизации "сервер-сервер".</span><span class="sxs-lookup"><span data-stu-id="65457-112">For the 2013 release, Lync Server 2013 and other Microsoft server products, including Exchange 2013 and SharePoint Server, support the Open Authorization (OAuth) protocol for server-to-server authentication and authorization.</span></span> <span data-ttu-id="65457-113">Дополнительные сведения: [Управление проверкой подлинности между серверами (OAuth) и партнерских приложений в Lync server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) в документации по развертыванию или документации по операциям.</span><span class="sxs-lookup"><span data-stu-id="65457-113">For details, see [Managing server-to-server authentication (OAuth) and partner applications in Lync Server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) in the Deployment documentation or the Operations documentation.</span></span>

<span data-ttu-id="65457-114">Для подключений клиентов, работающих под управлением операционной системы Windows 7, операционной системы Windows Server 2008, операционной системы Windows Server 2008 R2, операционной системы Windows Vista и Microsoft Lync Phone Edition, Lync Server 2013 включает поддержку (но не обязательно) сертификатов, подписанных с помощью функции шифрования хэша SHA-256.</span><span class="sxs-lookup"><span data-stu-id="65457-114">For connections from clients running Windows 7 operating system, Windows Server 2008 operating system, Windows Server 2008 R2 operating system, Windows Vista operating system, and Microsoft Lync Phone Edition, Lync Server 2013 includes support for (but does not require) certificates signed using the SHA-256 cryptographic hash function.</span></span> <span data-ttu-id="65457-115">Для поддержки внешнего доступа с помощью SHA-256 общедоступным центром сертификации выпускается внешний сертификат, использующий SHA-256.</span><span class="sxs-lookup"><span data-stu-id="65457-115">To support external access using SHA-256, the external certificate is issued by a public CA using SHA-256.</span></span>

<span data-ttu-id="65457-p106">В следующих таблицах приведены требования к сертификатам для ролей сервера для интерфейсных пулов и серверов Standard Edition. Все они являются стандартными сертификатами веб-сервера с закрытым ключом без поддержки экспорта.</span><span class="sxs-lookup"><span data-stu-id="65457-p106">The following tables show certificate requirements by server role for Front End pools and Standard Edition servers. All these are standard web server certificates, private key, non-exportable.</span></span>

<span data-ttu-id="65457-118">Обратите внимание, что расширенное использование ключа (EKU) сервера настраивается автоматически при использовании мастера сертификатов для запроса сертификатов.</span><span class="sxs-lookup"><span data-stu-id="65457-118">Note that server enhanced key usage (EKU) is automatically configured when you use the certificate wizard to request certificates.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="65457-119">Каждое понятное имя сертификата должно быть уникальным в хранилище компьютера.</span><span class="sxs-lookup"><span data-stu-id="65457-119">Each certificate Friendly Name must be unique in the computer store.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="65457-120">Если вы настроили sipinternal.contoso.com или sipexternal.contoso.com в вашей службе DNS, их необходимо будет добавить в альтернативное имя субъекта сертификата.</span><span class="sxs-lookup"><span data-stu-id="65457-120">If you have configured sipinternal.contoso.com or sipexternal.contoso.com in your DNS, you will need to add them in the certificate’s Subject Alternative Name.</span></span>



</div>

### <a name="certificates-for-standard-edition-server"></a><span data-ttu-id="65457-121">Сертификаты для сервера Standard Edition</span><span class="sxs-lookup"><span data-stu-id="65457-121">Certificates for Standard Edition Server</span></span>

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
<th><span data-ttu-id="65457-122">Сертификат</span><span class="sxs-lookup"><span data-stu-id="65457-122">Certificate</span></span></th>
<th><span data-ttu-id="65457-123">Имя субъекта/общее имя</span><span class="sxs-lookup"><span data-stu-id="65457-123">Subject name/ Common name</span></span></th>
<th><span data-ttu-id="65457-124">Альтернативное имя субъекта</span><span class="sxs-lookup"><span data-stu-id="65457-124">Subject alternative name</span></span></th>
<th><span data-ttu-id="65457-125">Пример</span><span class="sxs-lookup"><span data-stu-id="65457-125">Example</span></span></th>
<th><span data-ttu-id="65457-126">Comments</span><span class="sxs-lookup"><span data-stu-id="65457-126">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="65457-127">По умолчанию</span><span class="sxs-lookup"><span data-stu-id="65457-127">Default</span></span></p></td>
<td><p><span data-ttu-id="65457-128">Полное доменное имя пула</span><span class="sxs-lookup"><span data-stu-id="65457-128">Fully qualified domain name (FQDN) of the pool</span></span></p></td>
<td><p><span data-ttu-id="65457-129">Полное доменное имя пула и полное доменное имя сервера</span><span class="sxs-lookup"><span data-stu-id="65457-129">FQDN of the pool and the FQDN of the server</span></span></p>
<p><span data-ttu-id="65457-130">Если существует несколько доменов SIP и включена автоматическая настройка клиента, мастер сертификатов обнаруживает все поддерживаемые полные доменные имена SIP.</span><span class="sxs-lookup"><span data-stu-id="65457-130">If you have multiple SIP domains and have enabled automatic client configuration, the certificate wizard detects and adds each supported SIP domain FQDNs.</span></span></p>
<p><span data-ttu-id="65457-131">Если этот пул является сервером для автоматического входа клиентов и для групповой политики требуется строгое сопоставление DNS-имен, также необходимы записи для sip.sipdomain (для каждого домена SIP).</span><span class="sxs-lookup"><span data-stu-id="65457-131">If this pool is the auto-logon server for clients and strict Domain Name System (DNS) matching is required in group policy, you also need entries for sip.sipdomain (for each SIP domain you have).</span></span></p></td>
<td><p><span data-ttu-id="65457-132">SN = se01. contoso. com; SAN = se01. contoso. com</span><span class="sxs-lookup"><span data-stu-id="65457-132">SN=se01.contoso.com; SAN=se01.contoso.com</span></span></p>
<p><span data-ttu-id="65457-133">Если этот пул предназначен для сервера автоматического входа для клиентов, а в групповой политике требуется строгое сопоставление DNS, необходимо также добавить строки SAN=contoso.com SIP; SAN=fabrikam.com SIP.</span><span class="sxs-lookup"><span data-stu-id="65457-133">If this pool is the auto-logon server for clients and strict DNS matching is required in group policy, you also need SAN=sip.contoso.com; SAN=sip.fabrikam.com</span></span></p></td>
<td><p><span data-ttu-id="65457-134">На сервере Standard Edition полное доменное имя сервера совпадает с полным доменным именем пула.</span><span class="sxs-lookup"><span data-stu-id="65457-134">On Standard Edition server, the server FQDN is the same as the pool FQDN.</span></span></p>
<p><span data-ttu-id="65457-135">Мастер обнаруживает все домены SIP, указанные вами во время установки, и автоматически добавляет их в альтернативное имя субъекта.</span><span class="sxs-lookup"><span data-stu-id="65457-135">The wizard detects any SIP domains you specified during setup and automatically adds them to the subject alternative name.</span></span></p>
<p><span data-ttu-id="65457-136">Вы также можете использовать этот сертификат для проверки подлинности между серверами.</span><span class="sxs-lookup"><span data-stu-id="65457-136">You can also use this certificate for Server-to-Server Authentication.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="65457-137">Внутренняя сеть</span><span class="sxs-lookup"><span data-stu-id="65457-137">Web internal</span></span></p></td>
<td><p><span data-ttu-id="65457-138">Полное доменное имя сервера</span><span class="sxs-lookup"><span data-stu-id="65457-138">FQDN of the server</span></span></p></td>
<td><p><span data-ttu-id="65457-139">Каждое из следующих:</span><span class="sxs-lookup"><span data-stu-id="65457-139">Each of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="65457-140">Полное доменное имя внутренней сети (которое совпадает с полным доменным именем сервера)</span><span class="sxs-lookup"><span data-stu-id="65457-140">Internal web FQDN (which is the same as the FQDN of the server)</span></span></p></li>
<li><p><span data-ttu-id="65457-141">Простые URL-адреса собрания</span><span class="sxs-lookup"><span data-stu-id="65457-141">Meet simple URLs</span></span></p></li>
<li><p><span data-ttu-id="65457-142">Простой URL-адрес для телефонной связи</span><span class="sxs-lookup"><span data-stu-id="65457-142">Dial-in simple URL</span></span></p></li>
<li><p><span data-ttu-id="65457-143">Простой URL-адрес администратора</span><span class="sxs-lookup"><span data-stu-id="65457-143">Admin simple URL</span></span></p></li>
<li><p><span data-ttu-id="65457-144">Или групповая запись для простых URL-адресов</span><span class="sxs-lookup"><span data-stu-id="65457-144">Or, a wildcard entry for the simple URLs</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="65457-145">SN = se01. contoso. com; SAN = se01. contoso. com; SAN = встреча. contoso. com; SAN = соответствует. fabrikam. com; SAN = Dialin. contoso. com; SAN = admin. contoso. com</span><span class="sxs-lookup"><span data-stu-id="65457-145">SN=se01.contoso.com; SAN=se01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com</span></span></p>
<p><span data-ttu-id="65457-146">Использование групповых сертификатов:</span><span class="sxs-lookup"><span data-stu-id="65457-146">Using a wildcard certificate:</span></span></p>
<p><span data-ttu-id="65457-147">SN = se01. contoso. com; SAN = se01. contoso. com; SAN = \*. contoso. com</span><span class="sxs-lookup"><span data-stu-id="65457-147">SN=se01.contoso.com; SAN=se01.contoso.com; SAN=\*.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="65457-148">Вы не можете переопределить полное доменное имя внутреннего веб-сервера в построителе топологий.</span><span class="sxs-lookup"><span data-stu-id="65457-148">You cannot override the Internal web FQDN in Topology Builder.</span></span></p>
<p><span data-ttu-id="65457-149">При наличии нескольких простых URL-адресов собрания необходимо включить их все как альтернативные имена субъекта.</span><span class="sxs-lookup"><span data-stu-id="65457-149">If you have multiple Meet simple URLs, you must include all of them as subject alternative names.</span></span></p>
<p><span data-ttu-id="65457-150">Для простых URL-адресов поддерживаются подстановочные записи.</span><span class="sxs-lookup"><span data-stu-id="65457-150">Wildcard entries are supported for the simple URL entries.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="65457-151">Внешняя сеть</span><span class="sxs-lookup"><span data-stu-id="65457-151">Web external</span></span></p></td>
<td><p><span data-ttu-id="65457-152">Полное доменное имя сервера</span><span class="sxs-lookup"><span data-stu-id="65457-152">FQDN of the server</span></span></p></td>
<td><p><span data-ttu-id="65457-153">Каждое из следующих:</span><span class="sxs-lookup"><span data-stu-id="65457-153">Each of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="65457-154">Полное доменное имя внешней сети</span><span class="sxs-lookup"><span data-stu-id="65457-154">External web FQDN</span></span></p></li>
<li><p><span data-ttu-id="65457-155">Простой URL-адрес для телефонной связи</span><span class="sxs-lookup"><span data-stu-id="65457-155">Dial-in simple URL</span></span></p></li>
<li><p><span data-ttu-id="65457-156">Соответствие простых URL-адресов для каждого домена SIP</span><span class="sxs-lookup"><span data-stu-id="65457-156">Meet simple URLs per SIP domain</span></span></p></li>
<li><p><span data-ttu-id="65457-157">Или групповая запись для простых URL-адресов</span><span class="sxs-lookup"><span data-stu-id="65457-157">Or, a wildcard entry for the simple URLs</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="65457-158">SN = se01. contoso. com; SAN = webcon01. contoso. com; SAN = встреча. contoso. com; SAN = соответствует. fabrikam. com; SAN = Dialin. contoso. com</span><span class="sxs-lookup"><span data-stu-id="65457-158">SN=se01.contoso.com; SAN=webcon01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com</span></span></p>
<p><span data-ttu-id="65457-159">Использование групповых сертификатов:</span><span class="sxs-lookup"><span data-stu-id="65457-159">Using a wildcard certificate:</span></span></p>
<p><span data-ttu-id="65457-160">SN = se01. contoso. com; SAN = webcon01. contoso. com; SAN = \*. contoso. com</span><span class="sxs-lookup"><span data-stu-id="65457-160">SN=se01.contoso.com; SAN=webcon01.contoso.com; SAN=\*.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="65457-161">При наличии нескольких простых URL-адресов собрания необходимо включить их все как альтернативные имена субъекта.</span><span class="sxs-lookup"><span data-stu-id="65457-161">If you have multiple Meet simple URLs, you must include all of them as subject alternative names.</span></span></p>
<p><span data-ttu-id="65457-162">Для простых URL-адресов поддерживаются подстановочные записи.</span><span class="sxs-lookup"><span data-stu-id="65457-162">Wildcard entries are supported for the simple URL entries.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="certificates-for-front-end-server-in-a-front-end-pool"></a><span data-ttu-id="65457-163">Сертификаты для интерфейсного сервера в интерфейсном пуле</span><span class="sxs-lookup"><span data-stu-id="65457-163">Certificates for Front End Server in a Front End Pool</span></span>

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
<th><span data-ttu-id="65457-164">Сертификат</span><span class="sxs-lookup"><span data-stu-id="65457-164">Certificate</span></span></th>
<th><span data-ttu-id="65457-165">Имя субъекта/общее имя</span><span class="sxs-lookup"><span data-stu-id="65457-165">Subject name/ Common name</span></span></th>
<th><span data-ttu-id="65457-166">Альтернативное имя субъекта</span><span class="sxs-lookup"><span data-stu-id="65457-166">Subject alternative name</span></span></th>
<th><span data-ttu-id="65457-167">Пример</span><span class="sxs-lookup"><span data-stu-id="65457-167">Example</span></span></th>
<th><span data-ttu-id="65457-168">Comments</span><span class="sxs-lookup"><span data-stu-id="65457-168">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="65457-169">По умолчанию</span><span class="sxs-lookup"><span data-stu-id="65457-169">Default</span></span></p></td>
<td><p><span data-ttu-id="65457-170">Полное доменное имя пула</span><span class="sxs-lookup"><span data-stu-id="65457-170">FQDN of the pool</span></span></p></td>
<td><p><span data-ttu-id="65457-171">Полное доменное имя пула и сервера.</span><span class="sxs-lookup"><span data-stu-id="65457-171">FQDN of the pool and FQDN of the server.</span></span></p>
<p><span data-ttu-id="65457-172">Если существует несколько доменов SIP и включена автоматическая настройка клиента, мастер сертификатов обнаруживает все поддерживаемые полные доменные имена SIP.</span><span class="sxs-lookup"><span data-stu-id="65457-172">If you have multiple SIP domains and have enabled automatic client configuration, the certificate wizard detects and adds each supported SIP domain FQDNs.</span></span></p>
<p><span data-ttu-id="65457-173">Если этот пул является сервером для автоматического входа клиентов и для групповой политики требуется строгое сопоставление DNS-имен, также необходимы записи для sip.sipdomain (для каждого домена SIP).</span><span class="sxs-lookup"><span data-stu-id="65457-173">If this pool is the auto-logon server for clients and strict DNS matching is required in group policy, you also need entries for sip.sipdomain (for each SIP domain you have).</span></span></p></td>
<td><p><span data-ttu-id="65457-174">SN = ипул. contoso. com; SAN = ипул. contoso. com; SAN = ee01. contoso. com</span><span class="sxs-lookup"><span data-stu-id="65457-174">SN=eepool.contoso.com; SAN=eepool.contoso.com; SAN=ee01.contoso.com</span></span></p>
<p><span data-ttu-id="65457-175">Если этот пул предназначен для сервера автоматического входа для клиентов, а в групповой политике требуется строгое сопоставление DNS, необходимо также добавить строки SAN=contoso.com SIP; SAN=fabrikam.com SIP.</span><span class="sxs-lookup"><span data-stu-id="65457-175">If this pool is the auto-logon server for clients and strict DNS matching is required in group policy, you also need SAN=sip.contoso.com; SAN=sip.fabrikam.com</span></span></p></td>
<td><p><span data-ttu-id="65457-176">Мастер обнаруживает все домены SIP, указанные вами во время установки, и автоматически добавляет их в альтернативное имя субъекта.</span><span class="sxs-lookup"><span data-stu-id="65457-176">The wizard detects any SIP domains you specified during setup and automatically adds them to the subject alternative name.</span></span></p>
<p><span data-ttu-id="65457-177">Вы также можете использовать этот сертификат для проверки подлинности между серверами.</span><span class="sxs-lookup"><span data-stu-id="65457-177">You can also use this certificate for Server-to-Server Authentication.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="65457-178">Внутренняя сеть</span><span class="sxs-lookup"><span data-stu-id="65457-178">Web Internal</span></span></p></td>
<td><p><span data-ttu-id="65457-179">Полное доменное имя пула</span><span class="sxs-lookup"><span data-stu-id="65457-179">FQDN of the pool</span></span></p></td>
<td><p><span data-ttu-id="65457-180">Каждое из следующих:</span><span class="sxs-lookup"><span data-stu-id="65457-180">Each of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="65457-181">Полное доменное имя внутреннего веб-сайта (не то же, что и полное доменное имя сервера)</span><span class="sxs-lookup"><span data-stu-id="65457-181">Internal web FQDN (which is NOT the same as the FQDN of the server)</span></span></p></li>
<li><p><span data-ttu-id="65457-182">Полное доменное имя сервера</span><span class="sxs-lookup"><span data-stu-id="65457-182">Server FQDN</span></span></p></li>
<li><p><span data-ttu-id="65457-183">Полное доменное имя пула Lync</span><span class="sxs-lookup"><span data-stu-id="65457-183">Lync pool FQDN</span></span></p></li>
<li><p><span data-ttu-id="65457-184">Простые URL-адреса собрания</span><span class="sxs-lookup"><span data-stu-id="65457-184">Meet simple URLs</span></span></p></li>
<li><p><span data-ttu-id="65457-185">Простой URL-адрес для телефонной связи</span><span class="sxs-lookup"><span data-stu-id="65457-185">Dial-in simple URL</span></span></p></li>
<li><p><span data-ttu-id="65457-186">Простой URL-адрес администратора</span><span class="sxs-lookup"><span data-stu-id="65457-186">Admin simple URL</span></span></p></li>
<li><p><span data-ttu-id="65457-187">Или групповая запись для простых URL-адресов</span><span class="sxs-lookup"><span data-stu-id="65457-187">Or, a wildcard entry for the simple URLs</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="65457-188">SN = ee01. contoso. com; SAN = ee01. contoso. com; SAN = встреча. contoso. com; SAN = соответствует. fabrikam. com; SAN = Dialin. contoso. com; SAN = admin. contoso. com</span><span class="sxs-lookup"><span data-stu-id="65457-188">SN=ee01.contoso.com; SAN=ee01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com</span></span></p>
<p><span data-ttu-id="65457-189">Использование групповых сертификатов:</span><span class="sxs-lookup"><span data-stu-id="65457-189">Using a wildcard certificate:</span></span></p>
<p><span data-ttu-id="65457-190">SN = ee01. contoso. com; SAN = ee01. contoso. com; SAN = \*. contoso. com</span><span class="sxs-lookup"><span data-stu-id="65457-190">SN=ee01.contoso.com; SAN=ee01.contoso.com; SAN=\*.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="65457-191">При наличии нескольких простых URL-адресов собрания необходимо включить их все как альтернативные имена субъекта.</span><span class="sxs-lookup"><span data-stu-id="65457-191">If you have multiple Meet simple URLs, you must include all of them as subject alternative names.</span></span></p>
<p><span data-ttu-id="65457-192">Для простых URL-адресов поддерживаются подстановочные записи.</span><span class="sxs-lookup"><span data-stu-id="65457-192">Wildcard entries are supported for the simple URL entries.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="65457-193">Внешняя сеть</span><span class="sxs-lookup"><span data-stu-id="65457-193">Web external</span></span></p></td>
<td><p><span data-ttu-id="65457-194">Полное доменное имя пула</span><span class="sxs-lookup"><span data-stu-id="65457-194">FQDN of the pool</span></span></p></td>
<td><p><span data-ttu-id="65457-195">Каждое из следующих:</span><span class="sxs-lookup"><span data-stu-id="65457-195">Each of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="65457-196">Полное доменное имя внешней сети</span><span class="sxs-lookup"><span data-stu-id="65457-196">External web FQDN</span></span></p></li>
<li><p><span data-ttu-id="65457-197">Простой URL-адрес для телефонной связи</span><span class="sxs-lookup"><span data-stu-id="65457-197">Dial-in simple URL</span></span></p></li>
<li><p><span data-ttu-id="65457-198">Простой URL-адрес администратора</span><span class="sxs-lookup"><span data-stu-id="65457-198">Admin simple URL</span></span></p></li>
<li><p><span data-ttu-id="65457-199">Или групповая запись для простых URL-адресов</span><span class="sxs-lookup"><span data-stu-id="65457-199">Or, a wildcard entry for the simple URLs</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="65457-200">SN = ee01. contoso. com; SAN = webcon01. contoso. com; SAN = встреча. contoso. com; SAN = соответствует. fabrikam. com; SAN = Dialin. contoso. com</span><span class="sxs-lookup"><span data-stu-id="65457-200">SN=ee01.contoso.com; SAN=webcon01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com</span></span></p>
<p><span data-ttu-id="65457-201">Использование групповых сертификатов:</span><span class="sxs-lookup"><span data-stu-id="65457-201">Using a wildcard certificate:</span></span></p>
<p><span data-ttu-id="65457-202">SN = ee01. contoso. com; SAN = webcon01. contoso. com; SAN = \*. contoso. com</span><span class="sxs-lookup"><span data-stu-id="65457-202">SN=ee01.contoso.com; SAN=webcon01.contoso.com; SAN=\*.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="65457-203">При наличии нескольких простых URL-адресов собрания необходимо включить их все как альтернативные имена субъекта.</span><span class="sxs-lookup"><span data-stu-id="65457-203">If you have multiple Meet simple URLs, you must include all of them as subject alternative names.</span></span></p>
<p><span data-ttu-id="65457-204">Для простых URL-адресов поддерживаются подстановочные записи.</span><span class="sxs-lookup"><span data-stu-id="65457-204">Wildcard entries are supported for the simple URL entries.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="certificates-for-director"></a><span data-ttu-id="65457-205">Сертификаты для Директора</span><span class="sxs-lookup"><span data-stu-id="65457-205">Certificates for Director</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="65457-206">Сертификат</span><span class="sxs-lookup"><span data-stu-id="65457-206">Certificate</span></span></th>
<th><span data-ttu-id="65457-207">Имя субъекта/общее имя</span><span class="sxs-lookup"><span data-stu-id="65457-207">Subject name/ Common name</span></span></th>
<th><span data-ttu-id="65457-208">Альтернативное имя субъекта</span><span class="sxs-lookup"><span data-stu-id="65457-208">Subject alternative name</span></span></th>
<th><span data-ttu-id="65457-209">Пример</span><span class="sxs-lookup"><span data-stu-id="65457-209">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="65457-210">По умолчанию</span><span class="sxs-lookup"><span data-stu-id="65457-210">Default</span></span></p></td>
<td><p><span data-ttu-id="65457-211">Полное доменное имя пула Директоров</span><span class="sxs-lookup"><span data-stu-id="65457-211">FQDN of the Director pool</span></span></p></td>
<td><p><span data-ttu-id="65457-212">Полное доменное имя Директора и пула Директоров</span><span class="sxs-lookup"><span data-stu-id="65457-212">FQDN of the Director, FQDN of the Director pool</span></span></p>
<p><span data-ttu-id="65457-213">Если этот пул является сервером для автоматического входа клиентов и для групповой политики требуется строгое сопоставление DNS-имен, также необходимы записи для sip.sipdomain (для каждого домена SIP).</span><span class="sxs-lookup"><span data-stu-id="65457-213">If this pool is the auto-logon server for clients and strict DNS matching is required in group policy, you also need entries for sip.sipdomain (for each SIP domain you have).</span></span></p></td>
<td><p><span data-ttu-id="65457-214">SN = dir — pool.contoso.com; SAN = dir — pool.contoso.com; SAN = dir01. contoso. com</span><span class="sxs-lookup"><span data-stu-id="65457-214">SN=dir-pool.contoso.com; SAN=dir-pool.contoso.com; SAN=dir01.contoso.com</span></span></p>
<p><span data-ttu-id="65457-215">Если этот пул Директоров предназначен для сервера автоматического входа для клиентов, а в групповой политике требуется строгое сопоставление DNS, необходимо также добавить строки SAN=contoso.com SIP; SAN=fabrikam.com SIP.</span><span class="sxs-lookup"><span data-stu-id="65457-215">If this Director pool is the auto-logon server for clients and strict DNS matching is required in group policy, you also need SAN=sip.contoso.com; SAN=sip.fabrikam.com</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="65457-216">Внутренняя сеть</span><span class="sxs-lookup"><span data-stu-id="65457-216">Web Internal</span></span></p></td>
<td><p><span data-ttu-id="65457-217">Полное доменное имя сервера</span><span class="sxs-lookup"><span data-stu-id="65457-217">FQDN of the server</span></span></p></td>
<td><p><span data-ttu-id="65457-218">Каждое из следующих:</span><span class="sxs-lookup"><span data-stu-id="65457-218">Each of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="65457-219">Полное доменное имя внутренней сети (которое совпадает с полным доменным именем сервера)</span><span class="sxs-lookup"><span data-stu-id="65457-219">Internal web FQDN (which is the same as the FQDN of the server)</span></span></p></li>
<li><p><span data-ttu-id="65457-220">Полное доменное имя сервера</span><span class="sxs-lookup"><span data-stu-id="65457-220">Server FQDN</span></span></p></li>
<li><p><span data-ttu-id="65457-221">Полное доменное имя пула Lync</span><span class="sxs-lookup"><span data-stu-id="65457-221">Lync pool FQDN</span></span></p></li>
<li><p><span data-ttu-id="65457-222">Простые URL-адреса собрания</span><span class="sxs-lookup"><span data-stu-id="65457-222">Meet simple URLs</span></span></p></li>
<li><p><span data-ttu-id="65457-223">Простой URL-адрес для телефонной связи</span><span class="sxs-lookup"><span data-stu-id="65457-223">Dial-in simple URL</span></span></p></li>
<li><p><span data-ttu-id="65457-224">Простой URL-адрес администратора</span><span class="sxs-lookup"><span data-stu-id="65457-224">Admin simple URL</span></span></p></li>
<li><p><span data-ttu-id="65457-225">Или групповая запись для простых URL-адресов</span><span class="sxs-lookup"><span data-stu-id="65457-225">Or, a wildcard entry for the simple URLs</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="65457-226">SN = dir01. contoso. com; SAN = dir01. contoso. com; SAN = встреча. contoso. com; SAN = соответствует. fabrikam. com; SAN = Dialin. contoso. com; SAN = admin. contoso. com</span><span class="sxs-lookup"><span data-stu-id="65457-226">SN=dir01.contoso.com; SAN=dir01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com</span></span></p>
<p><span data-ttu-id="65457-227">SN = dir01. contoso. com; SAN = dir01. contoso. com SAN = \*. contoso. com</span><span class="sxs-lookup"><span data-stu-id="65457-227">SN=dir01.contoso.com; SAN=dir01.contoso.com SAN=\*.contoso.com</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="65457-228">Внешняя сеть</span><span class="sxs-lookup"><span data-stu-id="65457-228">Web external</span></span></p></td>
<td><p><span data-ttu-id="65457-229">Полное доменное имя сервера</span><span class="sxs-lookup"><span data-stu-id="65457-229">FQDN of the server</span></span></p></td>
<td><p><span data-ttu-id="65457-230">Каждое из следующих:</span><span class="sxs-lookup"><span data-stu-id="65457-230">Each of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="65457-231">Полное доменное имя внешней сети</span><span class="sxs-lookup"><span data-stu-id="65457-231">External web FQDN</span></span></p></li>
<li><p><span data-ttu-id="65457-232">Простой URL-адрес для телефонной связи</span><span class="sxs-lookup"><span data-stu-id="65457-232">Dial-in simple URL</span></span></p></li>
<li><p><span data-ttu-id="65457-233">Простой URL-адрес администратора</span><span class="sxs-lookup"><span data-stu-id="65457-233">Admin simple URL</span></span></p></li>
<li><p><span data-ttu-id="65457-234">Или групповая запись для простых URL-адресов</span><span class="sxs-lookup"><span data-stu-id="65457-234">Or, a wildcard entry for the simple URLs</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="65457-235">Полное доменное имя внешнего веб-сайта директора должно отличаться от внешнего интерфейса пула или сервера переднего плана.</span><span class="sxs-lookup"><span data-stu-id="65457-235">The Director external web FQDN must be different from the Front End pool or Front End Server.</span></span></p>
<p><span data-ttu-id="65457-236">SN = dir01. contoso. com; SAN = directorwebcon01. contoso. com SAN = встретиться. contoso. com; SAN = соответствует. fabrikam. com; SAN = Dialin. contoso. com</span><span class="sxs-lookup"><span data-stu-id="65457-236">SN=dir01.contoso.com; SAN=directorwebcon01.contoso.com SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com</span></span></p>
<p><span data-ttu-id="65457-237">SN = dir01. contoso. com; SAN = directorwebcon01. contoso. com SAN = \*. contoso. com</span><span class="sxs-lookup"><span data-stu-id="65457-237">SN=dir01.contoso.com; SAN=directorwebcon01.contoso.com SAN=\*.contoso.com</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="65457-p107">При использовании автономного пула серверов-посредников всем серверам-посредникам в нем нужны сертификаты, перечисленные в следующей таблице. При совместном размещении серверов-посредников с интерфейсными серверами, сертификаты, перечисленные в таблице "Сертификаты для интерфейсного сервера в интерфейсном пуле", приведенной ранее в этой статье, являются достаточными.</span><span class="sxs-lookup"><span data-stu-id="65457-p107">If you have a stand-alone Mediation Server pool, the Mediation Servers in it each need the certificates listed in the following table. If you collocate Mediation Server with the Front End Servers, the certificates listed in the “Certificates for Front End Server in Front End Pool” table earlier in this topic are sufficient.</span></span>

### <a name="certificates-for-stand-alone-mediation-server"></a><span data-ttu-id="65457-240">Сертификаты для автономного сервера-посредника</span><span class="sxs-lookup"><span data-stu-id="65457-240">Certificates for Stand-alone Mediation Server</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="65457-241">Сертификат</span><span class="sxs-lookup"><span data-stu-id="65457-241">Certificate</span></span></th>
<th><span data-ttu-id="65457-242">Имя субъекта/общее имя</span><span class="sxs-lookup"><span data-stu-id="65457-242">Subject name/ Common name</span></span></th>
<th><span data-ttu-id="65457-243">Альтернативное имя субъекта</span><span class="sxs-lookup"><span data-stu-id="65457-243">Subject alternative name</span></span></th>
<th><span data-ttu-id="65457-244">Пример</span><span class="sxs-lookup"><span data-stu-id="65457-244">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="65457-245">По умолчанию</span><span class="sxs-lookup"><span data-stu-id="65457-245">Default</span></span></p></td>
<td><p><span data-ttu-id="65457-246">Полное доменное имя пула</span><span class="sxs-lookup"><span data-stu-id="65457-246">FQDN of the pool</span></span></p></td>
<td><p><span data-ttu-id="65457-247">Полное доменное имя пула</span><span class="sxs-lookup"><span data-stu-id="65457-247">FQDN of the pool</span></span></p>
<p><span data-ttu-id="65457-248">Полное доменное имя рядового сервера пула</span><span class="sxs-lookup"><span data-stu-id="65457-248">FQDN of pool member server</span></span></p></td>
<td><p><span data-ttu-id="65457-249">SN = медсвр — pool.contoso.net; SAN = медсвр pool.contoso.net; SAN = medsvr01. contoso. NET</span><span class="sxs-lookup"><span data-stu-id="65457-249">SN=medsvr-pool.contoso.net; SAN=medsvr-pool.contoso.net; SAN=medsvr01.contoso.net</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="certificates-for-survivable-branch-appliance"></a><span data-ttu-id="65457-250">Сертификаты для устройства для обеспечения связи в филиалах</span><span class="sxs-lookup"><span data-stu-id="65457-250">Certificates for Survivable Branch Appliance</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="65457-251">Сертификат</span><span class="sxs-lookup"><span data-stu-id="65457-251">Certificate</span></span></th>
<th><span data-ttu-id="65457-252">Имя субъекта/общее имя</span><span class="sxs-lookup"><span data-stu-id="65457-252">Subject name/ Common name</span></span></th>
<th><span data-ttu-id="65457-253">Альтернативное имя субъекта</span><span class="sxs-lookup"><span data-stu-id="65457-253">Subject alternative name</span></span></th>
<th><span data-ttu-id="65457-254">Пример</span><span class="sxs-lookup"><span data-stu-id="65457-254">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="65457-255">По умолчанию</span><span class="sxs-lookup"><span data-stu-id="65457-255">Default</span></span></p></td>
<td><p><span data-ttu-id="65457-256">Полное доменное имя устройства</span><span class="sxs-lookup"><span data-stu-id="65457-256">FQDN of the appliance</span></span></p></td>
<td><p><span data-ttu-id="65457-257">SIP. &lt; sipdomain &gt; (требуется одна запись для каждого домена SIP)</span><span class="sxs-lookup"><span data-stu-id="65457-257">SIP.&lt;sipdomain&gt; (need one entry per SIP domain)</span></span></p></td>
<td><p><span data-ttu-id="65457-258">SN = sba01. contoso. NET; SAN = SIP. contoso. com; SAN = SIP. fabrikam. com</span><span class="sxs-lookup"><span data-stu-id="65457-258">SN=sba01.contoso.net; SAN=sip.contoso.com; SAN=sip.fabrikam.com</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a><span data-ttu-id="65457-259">См. также</span><span class="sxs-lookup"><span data-stu-id="65457-259">See Also</span></span>


[<span data-ttu-id="65457-260">Поддержка сертификатов с подстановочными знаками в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="65457-260">Wildcard certificate support in Lync Server 2013</span></span>](lync-server-2013-wildcard-certificate-support.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

