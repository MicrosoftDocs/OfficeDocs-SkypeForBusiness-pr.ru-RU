---
title: 'Lync Server 2013: сводка по DNS — балансировка нагрузки на DNS и аппаратная балансировка нагрузки'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: DNS summary - DNS and HLB load balanced
ms:assetid: d2132695-1956-4190-a98e-cd7255cbded6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205273(v=OCS.15)
ms:contentKeyID: 48185447
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ceccb52a8ef9fae810821ffe6b52b763dd8904c4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834346"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-summary---dns-and-hlb-load-balanced-in-lync-server-2013"></a><span data-ttu-id="310a9-102">Сводка по DNS — балансировка нагрузки на DNS и аппаратная балансировка нагрузки в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="310a9-102">DNS summary - DNS and HLB load balanced in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="310a9-103">_**Тема последнего изменения:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="310a9-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="310a9-104">В таблице ниже приведены сведения о DNS-записях, которые необходимы для поддержки подкаталога балансировки нагрузки DNS и оборудования.</span><span class="sxs-lookup"><span data-stu-id="310a9-104">The following table contains a summary of the DNS records that are required to support the DNS load balanced and hardware load balanced Director.</span></span> <span data-ttu-id="310a9-105">Роль режиссера требует наличия аналогичных записей DNS в качестве внешнего сервера.</span><span class="sxs-lookup"><span data-stu-id="310a9-105">The role of the Director requires similar DNS records as the Front End Server.</span></span> <span data-ttu-id="310a9-106">Количество необходимых записей отражается в альтернативных именах тем, необходимых для вашего сертификата в директории.</span><span class="sxs-lookup"><span data-stu-id="310a9-106">The number of records needed is reflected in the subject alternative names required on the Director certificate.</span></span> <span data-ttu-id="310a9-107">На сервере переднего плана не размещается учетные записи пользователей и не размещается служба Mobility Service.</span><span class="sxs-lookup"><span data-stu-id="310a9-107">Different from the Front End Server, the Director pool does not host user accounts or host the Mobility Services.</span></span>

### <a name="dns-records-required-for-the-director-pool-using-dns-load-balancing-and-hardware-load-balancer"></a><span data-ttu-id="310a9-108">DNS-записи, необходимые для пула режиссеров с помощью балансировки нагрузки DNS и аппаратной подсистемы балансировки нагрузки</span><span class="sxs-lookup"><span data-stu-id="310a9-108">DNS Records Required for the Director Pool using DNS Load Balancing and Hardware Load Balancer</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="310a9-109">Расположение/тип/порт</span><span class="sxs-lookup"><span data-stu-id="310a9-109">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="310a9-110">Полное доменное имя/DNS-запись</span><span class="sxs-lookup"><span data-stu-id="310a9-110">FQDN/DNS Record</span></span></th>
<th><span data-ttu-id="310a9-111">IP-адрес или полное доменное имя</span><span class="sxs-lookup"><span data-stu-id="310a9-111">IP Address/FQDN</span></span></th>
<th><span data-ttu-id="310a9-112">Карты и примечания</span><span class="sxs-lookup"><span data-stu-id="310a9-112">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="310a9-113">Внутренняя DNS/A</span><span class="sxs-lookup"><span data-stu-id="310a9-113">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="310a9-114">dir01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="310a9-114">dir01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="310a9-115">Директор</span><span class="sxs-lookup"><span data-stu-id="310a9-115">Director</span></span></p></td>
<td><p><span data-ttu-id="310a9-116">Запись узла директора, используемая для репликации и сервера на сервер</span><span class="sxs-lookup"><span data-stu-id="310a9-116">Director host record used for replication and server to server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="310a9-117">Внутренняя DNS/A</span><span class="sxs-lookup"><span data-stu-id="310a9-117">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="310a9-118">dirpool01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="310a9-118">dirpool01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="310a9-119">директоров</span><span class="sxs-lookup"><span data-stu-id="310a9-119">Director pool</span></span></p></td>
<td><p><span data-ttu-id="310a9-120">Запись узла для пула службы каталогов балансировки нагрузки DNS для сервера на сервер</span><span class="sxs-lookup"><span data-stu-id="310a9-120">Host record for the DNS load balanced Director pool for server to server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="310a9-121">Внутренняя DNS/A</span><span class="sxs-lookup"><span data-stu-id="310a9-121">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="310a9-122">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="310a9-122">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="310a9-123">директоров</span><span class="sxs-lookup"><span data-stu-id="310a9-123">Director pool</span></span></p></td>
<td><p><span data-ttu-id="310a9-124">Протокол SIP, входящий в внутренний интерфейс пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="310a9-124">Inbound session initiation protocol (SIP) from the internal interface of the Edge Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="310a9-125">Внутренняя DNS/A</span><span class="sxs-lookup"><span data-stu-id="310a9-125">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="310a9-126">dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="310a9-126">dialin.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="310a9-127">Пул ХЛБных ВИРТУАЛЬНЫХ каталогов</span><span class="sxs-lookup"><span data-stu-id="310a9-127">Director pool HLB VIP</span></span></p></td>
<td><p><span data-ttu-id="310a9-128">Подходящими для аппаратной балансировки нагрузки веб-службы, опубликованные из обратного прокси</span><span class="sxs-lookup"><span data-stu-id="310a9-128">Hardware load balanced published dialin web services from reverse proxy</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="310a9-129">Внутренняя DNS/A</span><span class="sxs-lookup"><span data-stu-id="310a9-129">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="310a9-130">meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="310a9-130">meet.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="310a9-131">Пул ХЛБных ВИРТУАЛЬНЫХ каталогов</span><span class="sxs-lookup"><span data-stu-id="310a9-131">Director pool HLB VIP</span></span></p></td>
<td><p><span data-ttu-id="310a9-132">Служба балансировки нагрузки для оборудования, опубликованная в соответствии с обратной прокси-сервером</span><span class="sxs-lookup"><span data-stu-id="310a9-132">Hardware load balanced published meet web services from reverse proxy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="310a9-133">Внутренняя DNS/A</span><span class="sxs-lookup"><span data-stu-id="310a9-133">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="310a9-134">webdirexternal.contoso.com</span><span class="sxs-lookup"><span data-stu-id="310a9-134">webdirexternal.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="310a9-135">Пул ХЛБных ВИРТУАЛЬНЫХ каталогов</span><span class="sxs-lookup"><span data-stu-id="310a9-135">Director pool HLB VIP</span></span></p></td>
<td><p><span data-ttu-id="310a9-136">Балансировка нагрузки для оборудования, опубликованная и определяемая внешними веб-службами обратного прокси, для директора пула</span><span class="sxs-lookup"><span data-stu-id="310a9-136">Hardware load balanced published and defined by the reverse proxy Web Ticket external web services for the Director pool</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

