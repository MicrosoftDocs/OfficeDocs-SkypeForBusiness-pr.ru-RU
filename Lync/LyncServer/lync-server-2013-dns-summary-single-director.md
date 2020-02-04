---
title: 'Lync Server 2013: сводка по DNS — единственный директор'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS summary - Single Director
ms:assetid: 790ecb56-92cd-41f4-baf6-c290a707aa4d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205021(v=OCS.15)
ms:contentKeyID: 48184568
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 71fb3052de36a92afb4ed9076820f7fcb2b54997
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757583"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-summary---single-director-in-lync-server-2013"></a><span data-ttu-id="f2221-102">Сводка по DNS — единственный директор в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f2221-102">DNS summary - Single Director in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f2221-103">_**Тема последнего изменения:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="f2221-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="f2221-104">В таблице ниже приведены основные сведения о DNS-записях, которые необходимы для поддержки единого директора.</span><span class="sxs-lookup"><span data-stu-id="f2221-104">The following table contains a summary of the DNS records that are required to support the single Director.</span></span> <span data-ttu-id="f2221-105">Роль режиссера требует наличия аналогичных записей DNS в качестве внешнего сервера.</span><span class="sxs-lookup"><span data-stu-id="f2221-105">The role of the Director requires similar DNS records as the Front End Server.</span></span> <span data-ttu-id="f2221-106">Количество необходимых записей отражается в альтернативных именах тем, необходимых для вашего сертификата в директории.</span><span class="sxs-lookup"><span data-stu-id="f2221-106">The number of records needed is reflected in the subject alternative names required on the Director certificate.</span></span> <span data-ttu-id="f2221-107">На сервере переднего плана не размещается учетные записи пользователей и не размещается служба Mobility Service.</span><span class="sxs-lookup"><span data-stu-id="f2221-107">Different from the Front End Server, the Director does not host user accounts or host the Mobility Services.</span></span>

### <a name="dns-records-required-for-the-director"></a><span data-ttu-id="f2221-108">DNS-записи, необходимые для режиссера</span><span class="sxs-lookup"><span data-stu-id="f2221-108">DNS Records Required for the Director</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f2221-109">Расположение/тип/порт</span><span class="sxs-lookup"><span data-stu-id="f2221-109">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="f2221-110">Полное доменное имя/DNS-запись</span><span class="sxs-lookup"><span data-stu-id="f2221-110">FQDN/DNS Record</span></span></th>
<th><span data-ttu-id="f2221-111">IP-адрес или полное доменное имя</span><span class="sxs-lookup"><span data-stu-id="f2221-111">IP Address/FQDN</span></span></th>
<th><span data-ttu-id="f2221-112">Карты и примечания</span><span class="sxs-lookup"><span data-stu-id="f2221-112">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f2221-113">Внутренняя DNS/A</span><span class="sxs-lookup"><span data-stu-id="f2221-113">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="f2221-114">dir01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="f2221-114">dir01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="f2221-115">Директор</span><span class="sxs-lookup"><span data-stu-id="f2221-115">Director</span></span></p></td>
<td><p><span data-ttu-id="f2221-116">Запись узла директора, используемая для репликации и сервера на сервер</span><span class="sxs-lookup"><span data-stu-id="f2221-116">Director host record used for replication and server to server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2221-117">Внутренняя DNS/A</span><span class="sxs-lookup"><span data-stu-id="f2221-117">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="f2221-118">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f2221-118">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="f2221-119">Директор</span><span class="sxs-lookup"><span data-stu-id="f2221-119">Director</span></span></p></td>
<td><p><span data-ttu-id="f2221-120">Протокол SIP из внутреннего интерфейса Edge-сервера</span><span class="sxs-lookup"><span data-stu-id="f2221-120">Inbound session initiation protocol (SIP) from the internal Edge interface of the Edge Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2221-121">Внутренняя DNS/A</span><span class="sxs-lookup"><span data-stu-id="f2221-121">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="f2221-122">dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f2221-122">dialin.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="f2221-123">Директор</span><span class="sxs-lookup"><span data-stu-id="f2221-123">Director</span></span></p></td>
<td><p><span data-ttu-id="f2221-124">Опубликованные веб-службы телефонной связи из обратного прокси</span><span class="sxs-lookup"><span data-stu-id="f2221-124">Published dialin web services from reverse proxy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2221-125">Внутренняя DNS/A</span><span class="sxs-lookup"><span data-stu-id="f2221-125">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="f2221-126">meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f2221-126">meet.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="f2221-127">Директор</span><span class="sxs-lookup"><span data-stu-id="f2221-127">Director</span></span></p></td>
<td><p><span data-ttu-id="f2221-128">Опубликованные веб-службы в обратном прокси</span><span class="sxs-lookup"><span data-stu-id="f2221-128">Published meet web services from reverse proxy</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2221-129">Внутренняя DNS/A</span><span class="sxs-lookup"><span data-stu-id="f2221-129">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="f2221-130">webdirexternal.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f2221-130">webdirexternal.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="f2221-131">Директор</span><span class="sxs-lookup"><span data-stu-id="f2221-131">Director</span></span></p></td>
<td><p><span data-ttu-id="f2221-132">Опубликовано и определено в обратном веб-службах External Web Ticket для режиссера.</span><span class="sxs-lookup"><span data-stu-id="f2221-132">Published and defined by the reverse proxy Web Ticket external web services for the Director</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

