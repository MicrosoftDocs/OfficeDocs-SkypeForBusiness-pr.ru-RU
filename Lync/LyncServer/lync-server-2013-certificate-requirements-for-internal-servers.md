---
title: 'Lync Server 2013: требования к сертификатам для внутренних серверов'
description: 'Lync Server 2013: требования к сертификатам для внутренних серверов.'
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
ms.openlocfilehash: dc1a627dd762c849b848087a96e00e19d320ef01
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48575215"
---
# <a name="certificate-requirements-for-internal-servers-in-lync-server-2013"></a><span data-ttu-id="dc8fe-103">Требования к сертификатам для внутренних серверов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dc8fe-103">Certificate requirements for internal servers in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dc8fe-104">_**Последнее изменение темы:** 2017-02-17_</span><span class="sxs-lookup"><span data-stu-id="dc8fe-104">_**Topic Last Modified:** 2017-02-17_</span></span>

<span data-ttu-id="dc8fe-105">Внутренние серверы, на которых работает Lync Server и которым необходимы сертификаты, включают сервер Standard Edition Server, сервер переднего плана Enterprise Edition, сервер-посредник и директор.</span><span class="sxs-lookup"><span data-stu-id="dc8fe-105">Internal servers that are running Lync Server and that require certificates include Standard Edition server, Enterprise Edition Front End Server, Mediation Server, and Director.</span></span> <span data-ttu-id="dc8fe-106">В следующей таблице показаны требования к сертификатам для этих серверов.</span><span class="sxs-lookup"><span data-stu-id="dc8fe-106">The following table shows the certificate requirements for these servers.</span></span> <span data-ttu-id="dc8fe-107">Вы можете запросить эти сертификаты с помощью мастера сертификатов Lync Server.</span><span class="sxs-lookup"><span data-stu-id="dc8fe-107">You can use the Lync Server certificate wizard to request these certificates.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="dc8fe-108">Для альтернативных имен субъектов, связанных с простыми URL-адресами в интерфейсном пуле, на сервере переднего плана или в директоре, поддерживаются подстановочные сертификаты.</span><span class="sxs-lookup"><span data-stu-id="dc8fe-108">Wildcard certificates are supported for the subject alternative names associated with the simple URLs on the Front End pool, Front End Server, or Director.</span></span> <span data-ttu-id="dc8fe-109">Дополнительные сведения о поддержке сертификатов с использованием подстановочных знаков приведены <A href="lync-server-2013-wildcard-certificate-support.md">в разделе Поддержка сертификатов с использованием подстановочных знаков в Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="dc8fe-109">For details about wildcard certificate support, see <A href="lync-server-2013-wildcard-certificate-support.md">Wildcard certificate support in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="dc8fe-110">Хотя для внутренних серверов рекомендуется внутренний центр сертификации (ЦС) предприятия, можно также использовать общедоступный ЦС.</span><span class="sxs-lookup"><span data-stu-id="dc8fe-110">Although an internal enterprise certification authority (CA) is recommended for internal servers, you can also use a public CA.</span></span> <span data-ttu-id="dc8fe-111">Список общедоступных центров сертификации, которые предоставляют сертификаты, соответствующие определенным требованиям для сертификатов Объединенных коммуникаций (UC) и партнерской корпорации Майкрософт, чтобы убедиться, что они работают с мастером сертификатов Lync Server, ознакомьтесь со статьей Microsoft Knowledge Base 929395, "Объединенные партнеры сертификатов для Exchange Server и Communications Server" по адресу [https://go.microsoft.com/fwlink/p/?linkId=202834](https://go.microsoft.com/fwlink/p/?linkid=202834) .</span><span class="sxs-lookup"><span data-stu-id="dc8fe-111">For a list of public CAs that provide certificates that comply with specific requirements for unified communications (UC) certificates and have partnered with Microsoft to ensure they work with the Lync Server Certificate Wizard, see article Microsoft Knowledge Base 929395, "Unified Communications Certificate Partners for Exchange Server and for Communications Server," at [https://go.microsoft.com/fwlink/p/?linkId=202834](https://go.microsoft.com/fwlink/p/?linkid=202834).</span></span>

<span data-ttu-id="dc8fe-112">Для связи с другими приложениями и серверами, например Exchange 2013, необходим сертификат, который поддерживается другими приложениями и продуктами.</span><span class="sxs-lookup"><span data-stu-id="dc8fe-112">Communication with other applications and servers, such as Exchange 2013, requires a certificate that is supported by the other applications and products.</span></span> <span data-ttu-id="dc8fe-113">Для выпусков 2013, Lync Server 2013 и других серверных продуктов Майкрософт, в том числе Exchange 2013 и SharePoint Server, поддерживается протокол OAuth для проверки подлинности и авторизации "сервер-сервер".</span><span class="sxs-lookup"><span data-stu-id="dc8fe-113">For the 2013 release, Lync Server 2013 and other Microsoft server products, including Exchange 2013 and SharePoint Server, support the Open Authorization (OAuth) protocol for server-to-server authentication and authorization.</span></span> <span data-ttu-id="dc8fe-114">Дополнительные сведения: [Управление проверкой подлинности между серверами (OAuth) и партнерских приложений в Lync server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) в документации по развертыванию или документации по операциям.</span><span class="sxs-lookup"><span data-stu-id="dc8fe-114">For details, see [Managing server-to-server authentication (OAuth) and partner applications in Lync Server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) in the Deployment documentation or the Operations documentation.</span></span>

<span data-ttu-id="dc8fe-115">Для подключений клиентов, работающих под управлением операционной системы Windows 7, операционной системы Windows Server 2008, операционной системы Windows Server 2008 R2, операционной системы Windows Vista и Microsoft Lync Phone Edition, Lync Server 2013 включает поддержку (но не обязательно) сертификатов, подписанных с помощью функции шифрования хэша SHA-256.</span><span class="sxs-lookup"><span data-stu-id="dc8fe-115">For connections from clients running Windows 7 operating system, Windows Server 2008 operating system, Windows Server 2008 R2 operating system, Windows Vista operating system, and Microsoft Lync Phone Edition, Lync Server 2013 includes support for (but does not require) certificates signed using the SHA-256 cryptographic hash function.</span></span> <span data-ttu-id="dc8fe-116">Для поддержки внешнего доступа с помощью SHA-256 общедоступным центром сертификации выпускается внешний сертификат, использующий SHA-256.</span><span class="sxs-lookup"><span data-stu-id="dc8fe-116">To support external access using SHA-256, the external certificate is issued by a public CA using SHA-256.</span></span>

<span data-ttu-id="dc8fe-p106">В следующих таблицах приведены требования к сертификатам для ролей сервера для интерфейсных пулов и серверов Standard Edition. Все они являются стандартными сертификатами веб-сервера с закрытым ключом без поддержки экспорта.</span><span class="sxs-lookup"><span data-stu-id="dc8fe-p106">The following tables show certificate requirements by server role for Front End pools and Standard Edition servers. All these are standard web server certificates, private key, non-exportable.</span></span>

<span data-ttu-id="dc8fe-119">Обратите внимание, что расширенное использование ключа (EKU) сервера настраивается автоматически при использовании мастера сертификатов для запроса сертификатов.</span><span class="sxs-lookup"><span data-stu-id="dc8fe-119">Note that server enhanced key usage (EKU) is automatically configured when you use the certificate wizard to request certificates.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="dc8fe-120">Каждое понятное имя сертификата должно быть уникальным в хранилище компьютера.</span><span class="sxs-lookup"><span data-stu-id="dc8fe-120">Each certificate Friendly Name must be unique in the computer store.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="dc8fe-121">Если вы настроили sipinternal.contoso.com или sipexternal.contoso.com в вашей службе DNS, их необходимо будет добавить в альтернативное имя субъекта сертификата.</span><span class="sxs-lookup"><span data-stu-id="dc8fe-121">If you have configured sipinternal.contoso.com or sipexternal.contoso.com in your DNS, you will need to add them in the certificate’s Subject Alternative Name.</span></span>



</div>

### <a name="certificates-for-standard-edition-server"></a><span data-ttu-id="dc8fe-122">Сертификаты для сервера Standard Edition</span><span class="sxs-lookup"><span data-stu-id="dc8fe-122">Certificates for Standard Edition Server</span></span>

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
<th><span data-ttu-id="dc8fe-123">Сертификат</span><span class="sxs-lookup"><span data-stu-id="dc8fe-123">Certificate</span></span></th>
<th><span data-ttu-id="dc8fe-124">Имя субъекта/общее имя</span><span class="sxs-lookup"><span data-stu-id="dc8fe-124">Subject name/ Common name</span></span></th>
<th><span data-ttu-id="dc8fe-125">Альтернативное имя субъекта</span><span class="sxs-lookup"><span data-stu-id="dc8fe-125">Subject alternative name</span></span></th>
<th><span data-ttu-id="dc8fe-126">Пример</span><span class="sxs-lookup"><span data-stu-id="dc8fe-126">Example</span></span></th>
<th><span data-ttu-id="dc8fe-127">Comments</span><span class="sxs-lookup"><span data-stu-id="dc8fe-127">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="dc8fe-128">По умолчанию</span><span class="sxs-lookup"><span data-stu-id="dc8fe-128">Default</span></span></p></td>
<td><p><span data-ttu-id="dc8fe-129">Полное доменное имя пула</span><span class="sxs-lookup"><span data-stu-id="dc8fe-129">Fully qualified domain name (FQDN) of the pool</span></span></p></td>
<td><p><span data-ttu-id="dc8fe-130">Полное доменное имя пула и полное доменное имя сервера</span><span class="sxs-lookup"><span data-stu-id="dc8fe-130">FQDN of the pool and the FQDN of the server</span></span></p>
<p><span data-ttu-id="dc8fe-131">Если существует несколько доменов SIP и включена автоматическая настройка клиента, мастер сертификатов обнаруживает все поддерживаемые полные доменные имена SIP.</span><span class="sxs-lookup"><span data-stu-id="dc8fe-131">If you have multiple SIP domains and have enabled automatic client configuration, the certificate wizard detects and adds each supported SIP domain FQDNs.</span></span></p>
<p><span data-ttu-id="dc8fe-132">Если этот пул является сервером для автоматического входа клиентов и для групповой политики требуется строгое сопоставление DNS-имен, также необходимы записи для sip.sipdomain (для каждого домена SIP).</span><span class="sxs-lookup"><span data-stu-id="dc8fe-132">If this pool is the auto-logon server for clients and strict Domain Name System (DNS) matching is required in group policy, you also need entries for sip.sipdomain (for each SIP domain you have).</span></span></p></td>
<td><p><span data-ttu-id="dc8fe-133">SN = se01. contoso. com; SAN = se01. contoso. com</span><span class="sxs-lookup"><span data-stu-id="dc8fe-133">SN=se01.contoso.com; SAN=se01.contoso.com</span></span></p>
<p><span data-ttu-id="dc8fe-134">Если этот пул предназначен для сервера автоматического входа для клиентов, а в групповой политике требуется строгое сопоставление DNS, необходимо также добавить строки SAN=contoso.com SIP; SAN=fabrikam.com SIP.</span><span class="sxs-lookup"><span data-stu-id="dc8fe-134">If this pool is the auto-logon server for clients and strict DNS matching is required in group policy, you also need SAN=sip.contoso.com; SAN=sip.fabrikam.com</span></span></p></td>
<td><p><span data-ttu-id="dc8fe-135">На сервере Standard Edition полное доменное имя сервера совпадает с полным доменным именем пула.</span><span class="sxs-lookup"><span data-stu-id="dc8fe-135">On Standard Edition server, the server FQDN is the same as the pool FQDN.</span></span></p>
<p><span data-ttu-id="dc8fe-136">Мастер обнаруживает все домены SIP, указанные вами во время установки, и автоматически добавляет их в альтернативное имя субъекта.</span><span class="sxs-lookup"><span data-stu-id="dc8fe-136">The wizard detects any SIP domains you specified during setup and automatically adds them to the subject alternative name.</span></span></p>
<p><span data-ttu-id="dc8fe-137">Вы также можете использовать этот сертификат для проверки подлинности между серверами.</span><span class="sxs-lookup"><span data-stu-id="dc8fe-137">You can also use this certificate for Server-to-Server Authentication.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dc8fe-138">Внутренняя сеть</span><span class="sxs-lookup"><span data-stu-id="dc8fe-138">Web internal</span></span></p></td>
<td><p><span data-ttu-id="dc8fe-139">Полное доменное имя сервера</span><span class="sxs-lookup"><span data-stu-id="dc8fe-139">FQDN of the server</span></span></p></td>
<td><p><span data-ttu-id="dc8fe-140">Каждое из следующих:</span><span class="sxs-lookup"><span data-stu-id="dc8fe-140">Each of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="dc8fe-141">Полное доменное имя внутренней сети (которое совпадает с полным доменным именем сервера)</span><span class="sxs-lookup"><span data-stu-id="dc8fe-141">Internal web FQDN (which is the same as the FQDN of the server)</span></span></p></li>
<li><p><span data-ttu-id="dc8fe-142">Простые URL-адреса собрания</span><span class="sxs-lookup"><span data-stu-id="dc8fe-142">Meet simple URLs</span></span></p></li>
<li><p><span data-ttu-id="dc8fe-143">Простой URL-адрес для телефонной связи</span><span class="sxs-lookup"><span data-stu-id="dc8fe-143">Dial-in simple URL</span></span></p></li>
<li><p><span data-ttu-id="dc8fe-144">Простой URL-адрес администратора</span><span class="sxs-lookup"><span data-stu-id="dc8fe-144">Admin simple URL</span></span></p></li>
<li><p><span data-ttu-id="dc8fe-145">Или групповая запись для простых URL-адресов</span><span class="sxs-lookup"><span data-stu-id="dc8fe-145">Or, a wildcard entry for the simple URLs</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="dc8fe-146">SN = se01. contoso. com; SAN = se01. contoso. com; SAN = встреча. contoso. com; SAN = соответствует. fabrikam. com; SAN = Dialin. contoso. com; SAN = admin. contoso. com</span><span class="sxs-lookup"><span data-stu-id="dc8fe-146">SN=se01.contoso.com; SAN=se01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com</span></span></p>
<p><span data-ttu-id="dc8fe-147">Использование групповых сертификатов:</span><span class="sxs-lookup"><span data-stu-id="dc8fe-147">Using a wildcard certificate:</span></span></p>
<p><span data-ttu-id="dc8fe-148">SN = se01. contoso. com; SAN = se01. contoso. com; SAN = \*. contoso. com</span><span class="sxs-lookup"><span data-stu-id="dc8fe-148">SN=se01.contoso.com; SAN=se01.contoso.com; SAN=\*.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="dc8fe-149">Вы не можете переопределить полное доменное имя внутреннего веб-сервера в построителе топологий.</span><span class="sxs-lookup"><span data-stu-id="dc8fe-149">You cannot override the Internal web FQDN in Topology Builder.</span></span></p>
<p><span data-ttu-id="dc8fe-150">При наличии нескольких простых URL-адресов собрания необходимо включить их все как альтернативные имена субъекта.</span><span class="sxs-lookup"><span data-stu-id="dc8fe-150">If you have multiple Meet simple URLs, you must include all of them as subject alternative names.</span></span></p>
<p><span data-ttu-id="dc8fe-151">Для простых URL-адресов поддерживаются подстановочные записи.</span><span class="sxs-lookup"><span data-stu-id="dc8fe-151">Wildcard entries are supported for the simple URL entries.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dc8fe-152">Внешняя сеть</span><span class="sxs-lookup"><span data-stu-id="dc8fe-152">Web external</span></span></p></td>
<td><p><span data-ttu-id="dc8fe-153">Полное доменное имя сервера</span><span class="sxs-lookup"><span data-stu-id="dc8fe-153">FQDN of the server</span></span></p></td>
<td><p><span data-ttu-id="dc8fe-154">Каждое из следующих:</span><span class="sxs-lookup"><span data-stu-id="dc8fe-154">Each of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="dc8fe-155">Полное доменное имя внешней сети</span><span class="sxs-lookup"><span data-stu-id="dc8fe-155">External web FQDN</span></span></p></li>
<li><p><span data-ttu-id="dc8fe-156">Простой URL-адрес для телефонной связи</span><span class="sxs-lookup"><span data-stu-id="dc8fe-156">Dial-in simple URL</span></span></p></li>
<li><p><span data-ttu-id="dc8fe-157">Соответствие простых URL-адресов для каждого домена SIP</span><span class="sxs-lookup"><span data-stu-id="dc8fe-157">Meet simple URLs per SIP domain</span></span></p></li>
<li><p><span data-ttu-id="dc8fe-158">Или групповая запись для простых URL-адресов</span><span class="sxs-lookup"><span data-stu-id="dc8fe-158">Or, a wildcard entry for the simple URLs</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="dc8fe-159">SN = se01. contoso. com; SAN = webcon01. contoso. com; SAN = встреча. contoso. com; SAN = соответствует. fabrikam. com; SAN = Dialin. contoso. com</span><span class="sxs-lookup"><span data-stu-id="dc8fe-159">SN=se01.contoso.com; SAN=webcon01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com</span></span></p>
<p><span data-ttu-id="dc8fe-160">Использование групповых сертификатов:</span><span class="sxs-lookup"><span data-stu-id="dc8fe-160">Using a wildcard certificate:</span></span></p>
<p><span data-ttu-id="dc8fe-161">SN = se01. contoso. com; SAN = webcon01. contoso. com; SAN = \*. contoso. com</span><span class="sxs-lookup"><span data-stu-id="dc8fe-161">SN=se01.contoso.com; SAN=webcon01.contoso.com; SAN=\*.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="dc8fe-162">При наличии нескольких простых URL-адресов собрания необходимо включить их все как альтернативные имена субъекта.</span><span class="sxs-lookup"><span data-stu-id="dc8fe-162">If you have multiple Meet simple URLs, you must include all of them as subject alternative names.</span></span></p>
<p><span data-ttu-id="dc8fe-163">Для простых URL-адресов поддерживаются подстановочные записи.</span><span class="sxs-lookup"><span data-stu-id="dc8fe-163">Wildcard entries are supported for the simple URL entries.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="certificates-for-front-end-server-in-a-front-end-pool"></a><span data-ttu-id="dc8fe-164">Сертификаты для интерфейсного сервера в интерфейсном пуле</span><span class="sxs-lookup"><span data-stu-id="dc8fe-164">Certificates for Front End Server in a Front End Pool</span></span>

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
<th><span data-ttu-id="dc8fe-165">Сертификат</span><span class="sxs-lookup"><span data-stu-id="dc8fe-165">Certificate</span></span></th>
<th><span data-ttu-id="dc8fe-166">Имя субъекта/общее имя</span><span class="sxs-lookup"><span data-stu-id="dc8fe-166">Subject name/ Common name</span></span></th>
<th><span data-ttu-id="dc8fe-167">Альтернативное имя субъекта</span><span class="sxs-lookup"><span data-stu-id="dc8fe-167">Subject alternative name</span></span></th>
<th><span data-ttu-id="dc8fe-168">Пример</span><span class="sxs-lookup"><span data-stu-id="dc8fe-168">Example</span></span></th>
<th><span data-ttu-id="dc8fe-169">Comments</span><span class="sxs-lookup"><span data-stu-id="dc8fe-169">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="dc8fe-170">По умолчанию</span><span class="sxs-lookup"><span data-stu-id="dc8fe-170">Default</span></span></p></td>
<td><p><span data-ttu-id="dc8fe-171">Полное доменное имя пула</span><span class="sxs-lookup"><span data-stu-id="dc8fe-171">FQDN of the pool</span></span></p></td>
<td><p><span data-ttu-id="dc8fe-172">Полное доменное имя пула и сервера.</span><span class="sxs-lookup"><span data-stu-id="dc8fe-172">FQDN of the pool and FQDN of the server.</span></span></p>
<p><span data-ttu-id="dc8fe-173">Если существует несколько доменов SIP и включена автоматическая настройка клиента, мастер сертификатов обнаруживает все поддерживаемые полные доменные имена SIP.</span><span class="sxs-lookup"><span data-stu-id="dc8fe-173">If you have multiple SIP domains and have enabled automatic client configuration, the certificate wizard detects and adds each supported SIP domain FQDNs.</span></span></p>
<p><span data-ttu-id="dc8fe-174">Если этот пул является сервером для автоматического входа клиентов и для групповой политики требуется строгое сопоставление DNS-имен, также необходимы записи для sip.sipdomain (для каждого домена SIP).</span><span class="sxs-lookup"><span data-stu-id="dc8fe-174">If this pool is the auto-logon server for clients and strict DNS matching is required in group policy, you also need entries for sip.sipdomain (for each SIP domain you have).</span></span></p></td>
<td><p><span data-ttu-id="dc8fe-175">SN = ипул. contoso. com; SAN = ипул. contoso. com; SAN = ee01. contoso. com</span><span class="sxs-lookup"><span data-stu-id="dc8fe-175">SN=eepool.contoso.com; SAN=eepool.contoso.com; SAN=ee01.contoso.com</span></span></p>
<p><span data-ttu-id="dc8fe-176">Если этот пул предназначен для сервера автоматического входа для клиентов, а в групповой политике требуется строгое сопоставление DNS, необходимо также добавить строки SAN=contoso.com SIP; SAN=fabrikam.com SIP.</span><span class="sxs-lookup"><span data-stu-id="dc8fe-176">If this pool is the auto-logon server for clients and strict DNS matching is required in group policy, you also need SAN=sip.contoso.com; SAN=sip.fabrikam.com</span></span></p></td>
<td><p><span data-ttu-id="dc8fe-177">Мастер обнаруживает все домены SIP, указанные вами во время установки, и автоматически добавляет их в альтернативное имя субъекта.</span><span class="sxs-lookup"><span data-stu-id="dc8fe-177">The wizard detects any SIP domains you specified during setup and automatically adds them to the subject alternative name.</span></span></p>
<p><span data-ttu-id="dc8fe-178">Вы также можете использовать этот сертификат для проверки подлинности между серверами.</span><span class="sxs-lookup"><span data-stu-id="dc8fe-178">You can also use this certificate for Server-to-Server Authentication.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dc8fe-179">Внутренняя сеть</span><span class="sxs-lookup"><span data-stu-id="dc8fe-179">Web Internal</span></span></p></td>
<td><p><span data-ttu-id="dc8fe-180">Полное доменное имя пула</span><span class="sxs-lookup"><span data-stu-id="dc8fe-180">FQDN of the pool</span></span></p></td>
<td><p><span data-ttu-id="dc8fe-181">Каждое из следующих:</span><span class="sxs-lookup"><span data-stu-id="dc8fe-181">Each of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="dc8fe-182">Полное доменное имя внутреннего веб-сайта (не то же, что и полное доменное имя сервера)</span><span class="sxs-lookup"><span data-stu-id="dc8fe-182">Internal web FQDN (which is NOT the same as the FQDN of the server)</span></span></p></li>
<li><p><span data-ttu-id="dc8fe-183">Полное доменное имя сервера</span><span class="sxs-lookup"><span data-stu-id="dc8fe-183">Server FQDN</span></span></p></li>
<li><p><span data-ttu-id="dc8fe-184">Полное доменное имя пула Lync</span><span class="sxs-lookup"><span data-stu-id="dc8fe-184">Lync pool FQDN</span></span></p></li>
<li><p><span data-ttu-id="dc8fe-185">Простые URL-адреса собрания</span><span class="sxs-lookup"><span data-stu-id="dc8fe-185">Meet simple URLs</span></span></p></li>
<li><p><span data-ttu-id="dc8fe-186">Простой URL-адрес для телефонной связи</span><span class="sxs-lookup"><span data-stu-id="dc8fe-186">Dial-in simple URL</span></span></p></li>
<li><p><span data-ttu-id="dc8fe-187">Простой URL-адрес администратора</span><span class="sxs-lookup"><span data-stu-id="dc8fe-187">Admin simple URL</span></span></p></li>
<li><p><span data-ttu-id="dc8fe-188">Или групповая запись для простых URL-адресов</span><span class="sxs-lookup"><span data-stu-id="dc8fe-188">Or, a wildcard entry for the simple URLs</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="dc8fe-189">SN = ee01. contoso. com; SAN = ee01. contoso. com; SAN = встреча. contoso. com; SAN = соответствует. fabrikam. com; SAN = Dialin. contoso. com; SAN = admin. contoso. com</span><span class="sxs-lookup"><span data-stu-id="dc8fe-189">SN=ee01.contoso.com; SAN=ee01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com</span></span></p>
<p><span data-ttu-id="dc8fe-190">Использование групповых сертификатов:</span><span class="sxs-lookup"><span data-stu-id="dc8fe-190">Using a wildcard certificate:</span></span></p>
<p><span data-ttu-id="dc8fe-191">SN = ee01. contoso. com; SAN = ee01. contoso. com; SAN = \*. contoso. com</span><span class="sxs-lookup"><span data-stu-id="dc8fe-191">SN=ee01.contoso.com; SAN=ee01.contoso.com; SAN=\*.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="dc8fe-192">При наличии нескольких простых URL-адресов собрания необходимо включить их все как альтернативные имена субъекта.</span><span class="sxs-lookup"><span data-stu-id="dc8fe-192">If you have multiple Meet simple URLs, you must include all of them as subject alternative names.</span></span></p>
<p><span data-ttu-id="dc8fe-193">Для простых URL-адресов поддерживаются подстановочные записи.</span><span class="sxs-lookup"><span data-stu-id="dc8fe-193">Wildcard entries are supported for the simple URL entries.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dc8fe-194">Внешняя сеть</span><span class="sxs-lookup"><span data-stu-id="dc8fe-194">Web external</span></span></p></td>
<td><p><span data-ttu-id="dc8fe-195">Полное доменное имя пула</span><span class="sxs-lookup"><span data-stu-id="dc8fe-195">FQDN of the pool</span></span></p></td>
<td><p><span data-ttu-id="dc8fe-196">Каждое из следующих:</span><span class="sxs-lookup"><span data-stu-id="dc8fe-196">Each of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="dc8fe-197">Полное доменное имя внешней сети</span><span class="sxs-lookup"><span data-stu-id="dc8fe-197">External web FQDN</span></span></p></li>
<li><p><span data-ttu-id="dc8fe-198">Простой URL-адрес для телефонной связи</span><span class="sxs-lookup"><span data-stu-id="dc8fe-198">Dial-in simple URL</span></span></p></li>
<li><p><span data-ttu-id="dc8fe-199">Простой URL-адрес администратора</span><span class="sxs-lookup"><span data-stu-id="dc8fe-199">Admin simple URL</span></span></p></li>
<li><p><span data-ttu-id="dc8fe-200">Или групповая запись для простых URL-адресов</span><span class="sxs-lookup"><span data-stu-id="dc8fe-200">Or, a wildcard entry for the simple URLs</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="dc8fe-201">SN = ee01. contoso. com; SAN = webcon01. contoso. com; SAN = встреча. contoso. com; SAN = соответствует. fabrikam. com; SAN = Dialin. contoso. com</span><span class="sxs-lookup"><span data-stu-id="dc8fe-201">SN=ee01.contoso.com; SAN=webcon01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com</span></span></p>
<p><span data-ttu-id="dc8fe-202">Использование групповых сертификатов:</span><span class="sxs-lookup"><span data-stu-id="dc8fe-202">Using a wildcard certificate:</span></span></p>
<p><span data-ttu-id="dc8fe-203">SN = ee01. contoso. com; SAN = webcon01. contoso. com; SAN = \*. contoso. com</span><span class="sxs-lookup"><span data-stu-id="dc8fe-203">SN=ee01.contoso.com; SAN=webcon01.contoso.com; SAN=\*.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="dc8fe-204">При наличии нескольких простых URL-адресов собрания необходимо включить их все как альтернативные имена субъекта.</span><span class="sxs-lookup"><span data-stu-id="dc8fe-204">If you have multiple Meet simple URLs, you must include all of them as subject alternative names.</span></span></p>
<p><span data-ttu-id="dc8fe-205">Для простых URL-адресов поддерживаются подстановочные записи.</span><span class="sxs-lookup"><span data-stu-id="dc8fe-205">Wildcard entries are supported for the simple URL entries.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="certificates-for-director"></a><span data-ttu-id="dc8fe-206">Сертификаты для Директора</span><span class="sxs-lookup"><span data-stu-id="dc8fe-206">Certificates for Director</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="dc8fe-207">Сертификат</span><span class="sxs-lookup"><span data-stu-id="dc8fe-207">Certificate</span></span></th>
<th><span data-ttu-id="dc8fe-208">Имя субъекта/общее имя</span><span class="sxs-lookup"><span data-stu-id="dc8fe-208">Subject name/ Common name</span></span></th>
<th><span data-ttu-id="dc8fe-209">Альтернативное имя субъекта</span><span class="sxs-lookup"><span data-stu-id="dc8fe-209">Subject alternative name</span></span></th>
<th><span data-ttu-id="dc8fe-210">Пример</span><span class="sxs-lookup"><span data-stu-id="dc8fe-210">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="dc8fe-211">По умолчанию</span><span class="sxs-lookup"><span data-stu-id="dc8fe-211">Default</span></span></p></td>
<td><p><span data-ttu-id="dc8fe-212">Полное доменное имя пула Директоров</span><span class="sxs-lookup"><span data-stu-id="dc8fe-212">FQDN of the Director pool</span></span></p></td>
<td><p><span data-ttu-id="dc8fe-213">Полное доменное имя Директора и пула Директоров</span><span class="sxs-lookup"><span data-stu-id="dc8fe-213">FQDN of the Director, FQDN of the Director pool</span></span></p>
<p><span data-ttu-id="dc8fe-214">Если этот пул является сервером для автоматического входа клиентов и для групповой политики требуется строгое сопоставление DNS-имен, также необходимы записи для sip.sipdomain (для каждого домена SIP).</span><span class="sxs-lookup"><span data-stu-id="dc8fe-214">If this pool is the auto-logon server for clients and strict DNS matching is required in group policy, you also need entries for sip.sipdomain (for each SIP domain you have).</span></span></p></td>
<td><p><span data-ttu-id="dc8fe-215">SN = dir — pool.contoso.com; SAN = dir — pool.contoso.com; SAN = dir01. contoso. com</span><span class="sxs-lookup"><span data-stu-id="dc8fe-215">SN=dir-pool.contoso.com; SAN=dir-pool.contoso.com; SAN=dir01.contoso.com</span></span></p>
<p><span data-ttu-id="dc8fe-216">Если этот пул Директоров предназначен для сервера автоматического входа для клиентов, а в групповой политике требуется строгое сопоставление DNS, необходимо также добавить строки SAN=contoso.com SIP; SAN=fabrikam.com SIP.</span><span class="sxs-lookup"><span data-stu-id="dc8fe-216">If this Director pool is the auto-logon server for clients and strict DNS matching is required in group policy, you also need SAN=sip.contoso.com; SAN=sip.fabrikam.com</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dc8fe-217">Внутренняя сеть</span><span class="sxs-lookup"><span data-stu-id="dc8fe-217">Web Internal</span></span></p></td>
<td><p><span data-ttu-id="dc8fe-218">Полное доменное имя сервера</span><span class="sxs-lookup"><span data-stu-id="dc8fe-218">FQDN of the server</span></span></p></td>
<td><p><span data-ttu-id="dc8fe-219">Каждое из следующих:</span><span class="sxs-lookup"><span data-stu-id="dc8fe-219">Each of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="dc8fe-220">Полное доменное имя внутренней сети (которое совпадает с полным доменным именем сервера)</span><span class="sxs-lookup"><span data-stu-id="dc8fe-220">Internal web FQDN (which is the same as the FQDN of the server)</span></span></p></li>
<li><p><span data-ttu-id="dc8fe-221">Полное доменное имя сервера</span><span class="sxs-lookup"><span data-stu-id="dc8fe-221">Server FQDN</span></span></p></li>
<li><p><span data-ttu-id="dc8fe-222">Полное доменное имя пула Lync</span><span class="sxs-lookup"><span data-stu-id="dc8fe-222">Lync pool FQDN</span></span></p></li>
<li><p><span data-ttu-id="dc8fe-223">Простые URL-адреса собрания</span><span class="sxs-lookup"><span data-stu-id="dc8fe-223">Meet simple URLs</span></span></p></li>
<li><p><span data-ttu-id="dc8fe-224">Простой URL-адрес для телефонной связи</span><span class="sxs-lookup"><span data-stu-id="dc8fe-224">Dial-in simple URL</span></span></p></li>
<li><p><span data-ttu-id="dc8fe-225">Простой URL-адрес администратора</span><span class="sxs-lookup"><span data-stu-id="dc8fe-225">Admin simple URL</span></span></p></li>
<li><p><span data-ttu-id="dc8fe-226">Или групповая запись для простых URL-адресов</span><span class="sxs-lookup"><span data-stu-id="dc8fe-226">Or, a wildcard entry for the simple URLs</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="dc8fe-227">SN = dir01. contoso. com; SAN = dir01. contoso. com; SAN = встреча. contoso. com; SAN = соответствует. fabrikam. com; SAN = Dialin. contoso. com; SAN = admin. contoso. com</span><span class="sxs-lookup"><span data-stu-id="dc8fe-227">SN=dir01.contoso.com; SAN=dir01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com</span></span></p>
<p><span data-ttu-id="dc8fe-228">SN = dir01. contoso. com; SAN = dir01. contoso. com SAN = \*. contoso. com</span><span class="sxs-lookup"><span data-stu-id="dc8fe-228">SN=dir01.contoso.com; SAN=dir01.contoso.com SAN=\*.contoso.com</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dc8fe-229">Внешняя сеть</span><span class="sxs-lookup"><span data-stu-id="dc8fe-229">Web external</span></span></p></td>
<td><p><span data-ttu-id="dc8fe-230">Полное доменное имя сервера</span><span class="sxs-lookup"><span data-stu-id="dc8fe-230">FQDN of the server</span></span></p></td>
<td><p><span data-ttu-id="dc8fe-231">Каждое из следующих:</span><span class="sxs-lookup"><span data-stu-id="dc8fe-231">Each of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="dc8fe-232">Полное доменное имя внешней сети</span><span class="sxs-lookup"><span data-stu-id="dc8fe-232">External web FQDN</span></span></p></li>
<li><p><span data-ttu-id="dc8fe-233">Простой URL-адрес для телефонной связи</span><span class="sxs-lookup"><span data-stu-id="dc8fe-233">Dial-in simple URL</span></span></p></li>
<li><p><span data-ttu-id="dc8fe-234">Простой URL-адрес администратора</span><span class="sxs-lookup"><span data-stu-id="dc8fe-234">Admin simple URL</span></span></p></li>
<li><p><span data-ttu-id="dc8fe-235">Или групповая запись для простых URL-адресов</span><span class="sxs-lookup"><span data-stu-id="dc8fe-235">Or, a wildcard entry for the simple URLs</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="dc8fe-236">Полное доменное имя внешнего веб-сайта директора должно отличаться от внешнего интерфейса пула или сервера переднего плана.</span><span class="sxs-lookup"><span data-stu-id="dc8fe-236">The Director external web FQDN must be different from the Front End pool or Front End Server.</span></span></p>
<p><span data-ttu-id="dc8fe-237">SN = dir01. contoso. com; SAN = directorwebcon01. contoso. com SAN = встретиться. contoso. com; SAN = соответствует. fabrikam. com; SAN = Dialin. contoso. com</span><span class="sxs-lookup"><span data-stu-id="dc8fe-237">SN=dir01.contoso.com; SAN=directorwebcon01.contoso.com SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com</span></span></p>
<p><span data-ttu-id="dc8fe-238">SN = dir01. contoso. com; SAN = directorwebcon01. contoso. com SAN = \*. contoso. com</span><span class="sxs-lookup"><span data-stu-id="dc8fe-238">SN=dir01.contoso.com; SAN=directorwebcon01.contoso.com SAN=\*.contoso.com</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="dc8fe-p107">При использовании автономного пула серверов-посредников всем серверам-посредникам в нем нужны сертификаты, перечисленные в следующей таблице. При совместном размещении серверов-посредников с интерфейсными серверами, сертификаты, перечисленные в таблице "Сертификаты для интерфейсного сервера в интерфейсном пуле", приведенной ранее в этой статье, являются достаточными.</span><span class="sxs-lookup"><span data-stu-id="dc8fe-p107">If you have a stand-alone Mediation Server pool, the Mediation Servers in it each need the certificates listed in the following table. If you collocate Mediation Server with the Front End Servers, the certificates listed in the “Certificates for Front End Server in Front End Pool” table earlier in this topic are sufficient.</span></span>

### <a name="certificates-for-stand-alone-mediation-server"></a><span data-ttu-id="dc8fe-241">Сертификаты для автономного сервера-посредника</span><span class="sxs-lookup"><span data-stu-id="dc8fe-241">Certificates for Stand-alone Mediation Server</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="dc8fe-242">Сертификат</span><span class="sxs-lookup"><span data-stu-id="dc8fe-242">Certificate</span></span></th>
<th><span data-ttu-id="dc8fe-243">Имя субъекта/общее имя</span><span class="sxs-lookup"><span data-stu-id="dc8fe-243">Subject name/ Common name</span></span></th>
<th><span data-ttu-id="dc8fe-244">Альтернативное имя субъекта</span><span class="sxs-lookup"><span data-stu-id="dc8fe-244">Subject alternative name</span></span></th>
<th><span data-ttu-id="dc8fe-245">Пример</span><span class="sxs-lookup"><span data-stu-id="dc8fe-245">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="dc8fe-246">По умолчанию</span><span class="sxs-lookup"><span data-stu-id="dc8fe-246">Default</span></span></p></td>
<td><p><span data-ttu-id="dc8fe-247">Полное доменное имя пула</span><span class="sxs-lookup"><span data-stu-id="dc8fe-247">FQDN of the pool</span></span></p></td>
<td><p><span data-ttu-id="dc8fe-248">Полное доменное имя пула</span><span class="sxs-lookup"><span data-stu-id="dc8fe-248">FQDN of the pool</span></span></p>
<p><span data-ttu-id="dc8fe-249">Полное доменное имя рядового сервера пула</span><span class="sxs-lookup"><span data-stu-id="dc8fe-249">FQDN of pool member server</span></span></p></td>
<td><p><span data-ttu-id="dc8fe-250">SN = медсвр — pool.contoso.net; SAN = медсвр pool.contoso.net; SAN = medsvr01. contoso. NET</span><span class="sxs-lookup"><span data-stu-id="dc8fe-250">SN=medsvr-pool.contoso.net; SAN=medsvr-pool.contoso.net; SAN=medsvr01.contoso.net</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="certificates-for-survivable-branch-appliance"></a><span data-ttu-id="dc8fe-251">Сертификаты для устройства для обеспечения связи в филиалах</span><span class="sxs-lookup"><span data-stu-id="dc8fe-251">Certificates for Survivable Branch Appliance</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="dc8fe-252">Сертификат</span><span class="sxs-lookup"><span data-stu-id="dc8fe-252">Certificate</span></span></th>
<th><span data-ttu-id="dc8fe-253">Имя субъекта/общее имя</span><span class="sxs-lookup"><span data-stu-id="dc8fe-253">Subject name/ Common name</span></span></th>
<th><span data-ttu-id="dc8fe-254">Альтернативное имя субъекта</span><span class="sxs-lookup"><span data-stu-id="dc8fe-254">Subject alternative name</span></span></th>
<th><span data-ttu-id="dc8fe-255">Пример</span><span class="sxs-lookup"><span data-stu-id="dc8fe-255">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="dc8fe-256">По умолчанию</span><span class="sxs-lookup"><span data-stu-id="dc8fe-256">Default</span></span></p></td>
<td><p><span data-ttu-id="dc8fe-257">Полное доменное имя устройства</span><span class="sxs-lookup"><span data-stu-id="dc8fe-257">FQDN of the appliance</span></span></p></td>
<td><p><span data-ttu-id="dc8fe-258">SIP. &lt; sipdomain &gt; (требуется одна запись для каждого домена SIP)</span><span class="sxs-lookup"><span data-stu-id="dc8fe-258">SIP.&lt;sipdomain&gt; (need one entry per SIP domain)</span></span></p></td>
<td><p><span data-ttu-id="dc8fe-259">SN = sba01. contoso. NET; SAN = SIP. contoso. com; SAN = SIP. fabrikam. com</span><span class="sxs-lookup"><span data-stu-id="dc8fe-259">SN=sba01.contoso.net; SAN=sip.contoso.com; SAN=sip.fabrikam.com</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a><span data-ttu-id="dc8fe-260">См. также</span><span class="sxs-lookup"><span data-stu-id="dc8fe-260">See Also</span></span>


[<span data-ttu-id="dc8fe-261">Поддержка сертификатов с подстановочными знаками в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dc8fe-261">Wildcard certificate support in Lync Server 2013</span></span>](lync-server-2013-wildcard-certificate-support.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

