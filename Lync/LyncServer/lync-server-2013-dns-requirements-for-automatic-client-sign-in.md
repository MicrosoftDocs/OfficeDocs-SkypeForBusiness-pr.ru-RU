---
title: 'Lync Server 2013: требования DNS для автоматического входа клиента'
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
ms.openlocfilehash: 6d033621382587367630d9119c2176e976cb2c2d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739159"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-requirements-for-automatic-client-sign-in-in-lync-server-2013"></a><span data-ttu-id="755b7-102">Требования DNS для автоматического входа клиента в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="755b7-102">DNS requirements for automatic client sign-in in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="755b7-103">_**Тема последнего изменения:** 2012-06-19_</span><span class="sxs-lookup"><span data-stu-id="755b7-103">_**Topic Last Modified:** 2012-06-19_</span></span>

<span data-ttu-id="755b7-104">В этом разделе объясняются DNS-записи, необходимые для автоматического входа в систему клиента.</span><span class="sxs-lookup"><span data-stu-id="755b7-104">This section explains the Domain Name System (DNS) records that are required for automatic client sign-in.</span></span> <span data-ttu-id="755b7-105">При развертывании серверов стандартных выпусков или пулов переднего плана можно настроить клиентские компьютеры на использование автоматического обнаружения для входа на соответствующий сервер Standard Edition или пул внешних интерфейсов.</span><span class="sxs-lookup"><span data-stu-id="755b7-105">When you deploy your Standard Edition servers or Front End pools, you can configure your clients to use automatic discovery to sign in to the appropriate Standard Edition server or Front End pool.</span></span> <span data-ttu-id="755b7-106">Если требуется, чтобы клиенты подключались к Lync Server 2013 вручную, вы можете пропустить этот раздел.</span><span class="sxs-lookup"><span data-stu-id="755b7-106">If you plan to require your clients to connect manually to Lync Server 2013, you can skip this topic.</span></span>

<span data-ttu-id="755b7-107">Для поддержки автоматического входа в клиент необходимо выполнить указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="755b7-107">To support automatic client sign-in, you must:</span></span>

  - <span data-ttu-id="755b7-108">Назначение одного сервера или пула для распространения и проверки подлинности запросов на вход в клиент.</span><span class="sxs-lookup"><span data-stu-id="755b7-108">Designate a single server or pool to distribute and authenticate client sign-in requests.</span></span> <span data-ttu-id="755b7-109">Это может быть существующий сервер или пул в Организации, на котором размещаются пользователи, или вы можете назначить выделенный сервер или пул для этой цели, где нет пользователей.</span><span class="sxs-lookup"><span data-stu-id="755b7-109">This can be an existing server or pool in your organization that hosts users, or you can designate a dedicated server or pool for this purpose that hosts no users.</span></span> <span data-ttu-id="755b7-110">Для обеспечения высокой доступности мы рекомендуем указать пул переднего плана для этой функции.</span><span class="sxs-lookup"><span data-stu-id="755b7-110">For high availability, we recommend that you designate a Front End pool for this function.</span></span>

  - <span data-ttu-id="755b7-111">Создание внутренней записи SRV DNS для поддержки автоматического входа клиента для этого сервера или пула.</span><span class="sxs-lookup"><span data-stu-id="755b7-111">Create an internal DNS SRV record to support automatic client sign-in for this server or pool.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="755b7-112">В следующих требованиях к записям домен SIP относится к части URI SIP, назначенной пользователям.</span><span class="sxs-lookup"><span data-stu-id="755b7-112">In the following record requirements, SIP domain refers to the host portion of the SIP URIs assigned to users.</span></span> <span data-ttu-id="755b7-113">Например, если URI SIP имеет форму \* @contoso. com, contoso.com — это домен SIP.</span><span class="sxs-lookup"><span data-stu-id="755b7-113">For example, if SIP URIs are of the form \*@contoso.com, contoso.com is the SIP domain.</span></span> <span data-ttu-id="755b7-114">Домен SIP часто отличается от внутреннего домена Active Directory.</span><span class="sxs-lookup"><span data-stu-id="755b7-114">The SIP domain is often different from the internal Active Directory domain.</span></span> <span data-ttu-id="755b7-115">Организация также может поддерживать несколько доменов SIP.</span><span class="sxs-lookup"><span data-stu-id="755b7-115">An organization can also support multiple SIP domains.</span></span>

    
    </div>

<span data-ttu-id="755b7-116">Чтобы включить автоматическую настройку для клиентов, необходимо создать внутреннюю запись DNS SRV, которая сопоставляет одну из указанных ниже записей с полным доменным именем (FQDN) переднего плана или сервера Standard Edition, который распространяет запросы на вход из Lync. клиентов</span><span class="sxs-lookup"><span data-stu-id="755b7-116">To enable automatic configuration for your clients, you must create an internal DNS SRV record that maps one of the following records to the fully qualified domain name (FQDN) of the Front End pool or Standard Edition server that distributes sign-in requests from Lync clients:</span></span>

  - <span data-ttu-id="755b7-117">\_сипинтерналтлс. \_протокол TCP. \<домен\> — для внутренних TLS-подключений</span><span class="sxs-lookup"><span data-stu-id="755b7-117">\_sipinternaltls.\_tcp.\<domain\> - for internal TLS connections</span></span>

<span data-ttu-id="755b7-118">Вам нужно только создать единственную запись SRV для пула переднего плана или сервера Standard Edition либо которая будет распространять запросы на вход.</span><span class="sxs-lookup"><span data-stu-id="755b7-118">You only need to create a single SRV record for the Front End pool or Standard Edition server or that will distribute sign-in requests.</span></span>

<span data-ttu-id="755b7-119">В следующей таблице показаны некоторые примеры записей, необходимых для вымышленной компании Contoso, которая поддерживает домены SIP для contoso.com и retail.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="755b7-119">The following table shows some example records required for the fictitious company Contoso, which supports SIP domains of contoso.com and retail.contoso.com.</span></span>

### <a name="example-of-dns-records-required-for-automatic-client-sign-in-with-multiple-sip-domains"></a><span data-ttu-id="755b7-120">Пример DNS-записей, необходимых для автоматического входа в клиент с несколькими доменами SIP</span><span class="sxs-lookup"><span data-stu-id="755b7-120">Example of DNS Records Required for Automatic Client Sign-in with Multiple SIP Domains</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="755b7-121">Полное доменное имя пула переднего плана, используемое для распространения запросов на вход</span><span class="sxs-lookup"><span data-stu-id="755b7-121">FQDN of Front End pool used to distribute sign-in requests</span></span></th>
<th><span data-ttu-id="755b7-122">Домен SIP</span><span class="sxs-lookup"><span data-stu-id="755b7-122">SIP domain</span></span></th>
<th><span data-ttu-id="755b7-123">SRV-запись DNS</span><span class="sxs-lookup"><span data-stu-id="755b7-123">DNS SRV record</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="755b7-124">pool01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="755b7-124">pool01.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="755b7-125">contoso.com</span><span class="sxs-lookup"><span data-stu-id="755b7-125">contoso.com</span></span></p></td>
<td><p><span data-ttu-id="755b7-126">SRV-запись для домена _sipinternaltls. _tcp. contoso. com по порту 5061, сопоставленная с pool01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="755b7-126">An SRV record for _sipinternaltls._tcp.contoso.com domain over port 5061 that maps to pool01.contoso.com</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="755b7-127">pool01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="755b7-127">pool01.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="755b7-128">retail.contoso.com</span><span class="sxs-lookup"><span data-stu-id="755b7-128">retail.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="755b7-129">SRV-запись для домена _sipinternaltls. _tcp. Retail. contoso. com по порту 5061, которая сопоставляется с pool01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="755b7-129">An SRV record for _sipinternaltls._tcp.retail.contoso.com domain over port 5061 that maps to pool01.contoso.com</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="755b7-130">По умолчанию запросы DNS-записей соответствуют строгому сопоставлению доменных имен между доменом в имени пользователя и записи SRV.</span><span class="sxs-lookup"><span data-stu-id="755b7-130">By default, queries for DNS records adhere to strict domain name matching between the domain in the user name and the SRV record.</span></span> <span data-ttu-id="755b7-131">Если вы предпочитаете, чтобы клиентские DNS-запросы вместо этого использовали соответствующие суффиксы, вы можете настроить групповую политику Дисаблестриктднснаминг.</span><span class="sxs-lookup"><span data-stu-id="755b7-131">If you prefer that client DNS queries use suffix matching instead, you can configure the DisableStrictDNSNaming Group Policy.</span></span> <span data-ttu-id="755b7-132">Подробные сведения можно найти <A href="lync-server-2013-planning-for-clients-and-devices.md">в разделе Планирование клиентов и устройств в Lync Server 2013</A> в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="755b7-132">For details, see <A href="lync-server-2013-planning-for-clients-and-devices.md">Planning for clients and devices in Lync Server 2013</A> in the Planning documentation.</span></span>



</div>

<div>

## <a name="example-of-the-certificates-and-dns-records-required-for-automatic-client-sign-in"></a><span data-ttu-id="755b7-133">Пример сертификатов и записей DNS, необходимых для автоматического входа в клиент</span><span class="sxs-lookup"><span data-stu-id="755b7-133">Example of the Certificates and DNS Records Required for Automatic Client Sign-In</span></span>

<span data-ttu-id="755b7-134">В этом примере используются те же примеры имен из приведенной выше таблицы.</span><span class="sxs-lookup"><span data-stu-id="755b7-134">This example uses the same example names in the preceding table.</span></span> <span data-ttu-id="755b7-135">Организация Contoso поддерживает домены SIP для contoso.com и retail.contoso.com, а все его пользователи имеют URI SIP в одной из следующих форм:</span><span class="sxs-lookup"><span data-stu-id="755b7-135">The Contoso organization supports the SIP domains of contoso.com and retail.contoso.com, and all of its users have a SIP URI in one of the following forms:</span></span>

  - <span data-ttu-id="755b7-136">\<User\>@retail. contoso.com</span><span class="sxs-lookup"><span data-stu-id="755b7-136">\<user\>@retail.contoso.com</span></span>

  - <span data-ttu-id="755b7-137">\<User\>@contoso. com</span><span class="sxs-lookup"><span data-stu-id="755b7-137">\<user\>@contoso.com</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

