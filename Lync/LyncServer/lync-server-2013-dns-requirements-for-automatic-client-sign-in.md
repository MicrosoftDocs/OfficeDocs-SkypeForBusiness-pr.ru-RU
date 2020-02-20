---
title: 'Lync Server 2013: требования к DNS для автоматического входа клиентов'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS requirements for automatic client sign-in
ms:assetid: 3bcd4bb3-a022-4ffa-b005-1a95ad2b1796
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425884(v=OCS.15)
ms:contentKeyID: 48183873
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5464fbef2586467ee922d61bdaa3a09b591c88b4
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42150668"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="dns-requirements-for-automatic-client-sign-in-in-lync-server-2013"></a><span data-ttu-id="cddac-102">Требования DNS для автоматического входа клиентов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cddac-102">DNS requirements for automatic client sign-in in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cddac-103">_**Последнее изменение темы:** 2012-06-19_</span><span class="sxs-lookup"><span data-stu-id="cddac-103">_**Topic Last Modified:** 2012-06-19_</span></span>

<span data-ttu-id="cddac-104">В данном разделе описываются записи службы доменных имен (DNS), необходимые для автоматического входа клиентов.</span><span class="sxs-lookup"><span data-stu-id="cddac-104">This section explains the Domain Name System (DNS) records that are required for automatic client sign-in.</span></span> <span data-ttu-id="cddac-105">При развертывании серверов Standard Edition или интерфейсных пулов вы можете настроить клиентов на использование автоматического обнаружения для входа на соответствующий сервер Standard Edition или в интерфейсный пул.</span><span class="sxs-lookup"><span data-stu-id="cddac-105">When you deploy your Standard Edition servers or Front End pools, you can configure your clients to use automatic discovery to sign in to the appropriate Standard Edition server or Front End pool.</span></span> <span data-ttu-id="cddac-106">Если вы планируете, чтобы клиенты могли подключаться к Lync Server 2013 вручную, вы можете пропустить этот раздел.</span><span class="sxs-lookup"><span data-stu-id="cddac-106">If you plan to require your clients to connect manually to Lync Server 2013, you can skip this topic.</span></span>

<span data-ttu-id="cddac-107">Чтобы обеспечить поддержку автоматического входа клиентов, вам следует выполнить следующие действия:</span><span class="sxs-lookup"><span data-stu-id="cddac-107">To support automatic client sign-in, you must:</span></span>

  - <span data-ttu-id="cddac-p102">Назначить отдельный сервер или пул для распространения и проверки подлинности запросов входа от клиентов. Это может быть существующий в организации сервер или пул с размещенными пользователями, либо вы можете назначить для этой цели выделенный сервер или пул без размещенных пользователей. Для обеспечения высокой доступности мы рекомендуем назначить для этого интерфейсный пул.</span><span class="sxs-lookup"><span data-stu-id="cddac-p102">Designate a single server or pool to distribute and authenticate client sign-in requests. This can be an existing server or pool in your organization that hosts users, or you can designate a dedicated server or pool for this purpose that hosts no users. For high availability, we recommend that you designate a Front End pool for this function.</span></span>

  - <span data-ttu-id="cddac-111">Создать внутреннюю DNS-запись SRV, чтобы обеспечить поддержку автоматического входа клиентов для этого сервера или пула.</span><span class="sxs-lookup"><span data-stu-id="cddac-111">Create an internal DNS SRV record to support automatic client sign-in for this server or pool.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="cddac-p103">В приведенных ниже требованиях к записи домен SIP относится к той части кодов URI SIP, назначенных пользователям, которая обозначает узел. Например, если коды URI SIP имеют форму \*@contoso.com, то contoso.com — это домен SIP. Этот домен SIP часто отличается от внутреннего домена Active Directory. Кроме того, организация может поддерживать несколько доменов SIP.</span><span class="sxs-lookup"><span data-stu-id="cddac-p103">In the following record requirements, SIP domain refers to the host portion of the SIP URIs assigned to users. For example, if SIP URIs are of the form \*@contoso.com, contoso.com is the SIP domain. The SIP domain is often different from the internal Active Directory domain. An organization can also support multiple SIP domains.</span></span>

    
    </div>

<span data-ttu-id="cddac-116">Чтобы включить автоматическую настройку клиентов, необходимо создать внутреннюю DNS-запись SRV, которая сопоставляет одну из следующих записей с полным доменным именем (FQDN) интерфейсного пула или сервера Standard Edition, который распространяет запросы на вход из Lync. заказчика</span><span class="sxs-lookup"><span data-stu-id="cddac-116">To enable automatic configuration for your clients, you must create an internal DNS SRV record that maps one of the following records to the fully qualified domain name (FQDN) of the Front End pool or Standard Edition server that distributes sign-in requests from Lync clients:</span></span>

  - <span data-ttu-id="cddac-117">\_сипинтерналтлс. \_TCP. \<домен\> — для внутренних подключений TLS</span><span class="sxs-lookup"><span data-stu-id="cddac-117">\_sipinternaltls.\_tcp.\<domain\> - for internal TLS connections</span></span>

<span data-ttu-id="cddac-118">Вам требуется только создать одну запись SRV для интерфейсного пула или сервера Standard Edition, который будет распространять запросы на вход.</span><span class="sxs-lookup"><span data-stu-id="cddac-118">You only need to create a single SRV record for the Front End pool or Standard Edition server or that will distribute sign-in requests.</span></span>

<span data-ttu-id="cddac-119">В следующей таблице приведено несколько примеров записей, требуемых для вымышленной компании Contoso, осуществляющей поддержку доменов SIP contoso.com и retail.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="cddac-119">The following table shows some example records required for the fictitious company Contoso, which supports SIP domains of contoso.com and retail.contoso.com.</span></span>

### <a name="example-of-dns-records-required-for-automatic-client-sign-in-with-multiple-sip-domains"></a><span data-ttu-id="cddac-120">Пример DNS-записей, необходимых для автоматического входа клиентов с несколькими доменами SIP</span><span class="sxs-lookup"><span data-stu-id="cddac-120">Example of DNS Records Required for Automatic Client Sign-in with Multiple SIP Domains</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="cddac-121">Полное доменное имя интерфейсного пула, используемого для распространения запросов на вход</span><span class="sxs-lookup"><span data-stu-id="cddac-121">FQDN of Front End pool used to distribute sign-in requests</span></span></th>
<th><span data-ttu-id="cddac-122">Домен SIP</span><span class="sxs-lookup"><span data-stu-id="cddac-122">SIP domain</span></span></th>
<th><span data-ttu-id="cddac-123">DNS-запись SRV</span><span class="sxs-lookup"><span data-stu-id="cddac-123">DNS SRV record</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cddac-124">pool01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="cddac-124">pool01.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="cddac-125">contoso.com</span><span class="sxs-lookup"><span data-stu-id="cddac-125">contoso.com</span></span></p></td>
<td><p><span data-ttu-id="cddac-126">Запись SRV для домена _sipinternaltls._tcp.contoso.com через порт 5061, которая сопоставлена с pool01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="cddac-126">An SRV record for _sipinternaltls._tcp.contoso.com domain over port 5061 that maps to pool01.contoso.com</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cddac-127">pool01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="cddac-127">pool01.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="cddac-128">retail.contoso.com</span><span class="sxs-lookup"><span data-stu-id="cddac-128">retail.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="cddac-129">Запись SRV для домена _sipinternaltls._tcp.retail.contoso.com через порт 5061, которая сопоставлена с pool01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="cddac-129">An SRV record for _sipinternaltls._tcp.retail.contoso.com domain over port 5061 that maps to pool01.contoso.com</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="cddac-130">По умолчанию запросы для DNS-записей придерживаются строгого совпадения имен доменов между доменом в имени пользователя и в записи SRV.</span><span class="sxs-lookup"><span data-stu-id="cddac-130">By default, queries for DNS records adhere to strict domain name matching between the domain in the user name and the SRV record.</span></span> <span data-ttu-id="cddac-131">Если вы предпочитаете, чтобы DNS-запросы клиентов вместо этого использовали совпадение суффиксов, то можете настроить групповую политику DisableStrictDNSNaming.</span><span class="sxs-lookup"><span data-stu-id="cddac-131">If you prefer that client DNS queries use suffix matching instead, you can configure the DisableStrictDNSNaming Group Policy.</span></span> <span data-ttu-id="cddac-132">Дополнительные сведения приведены в статье <A href="lync-server-2013-planning-for-clients-and-devices.md">планирование для клиентов и устройств в Lync Server 2013</A> в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="cddac-132">For details, see <A href="lync-server-2013-planning-for-clients-and-devices.md">Planning for clients and devices in Lync Server 2013</A> in the Planning documentation.</span></span>



</div>

<div>

## <a name="example-of-the-certificates-and-dns-records-required-for-automatic-client-sign-in"></a><span data-ttu-id="cddac-133">Пример сертификатов и DNS-записей, необходимых для автоматического входа клиентов</span><span class="sxs-lookup"><span data-stu-id="cddac-133">Example of the Certificates and DNS Records Required for Automatic Client Sign-In</span></span>

<span data-ttu-id="cddac-p105">В данном примере используются образцы имен из предыдущей таблицы. Организация Contoso поддерживает домены SIP contoso.com и retail.contoso.com, и все ее пользователи имеют код URI SIP в одной из следующих форм:</span><span class="sxs-lookup"><span data-stu-id="cddac-p105">This example uses the same example names in the preceding table. The Contoso organization supports the SIP domains of contoso.com and retail.contoso.com, and all of its users have a SIP URI in one of the following forms:</span></span>

  - <span data-ttu-id="cddac-136">\<пользователь\>@retail. contoso.com</span><span class="sxs-lookup"><span data-stu-id="cddac-136">\<user\>@retail.contoso.com</span></span>

  - <span data-ttu-id="cddac-137">\<пользователь\>@contoso. com</span><span class="sxs-lookup"><span data-stu-id="cddac-137">\<user\>@contoso.com</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

