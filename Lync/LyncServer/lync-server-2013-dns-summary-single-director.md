---
title: 'Lync Server 2013: сводка по DNS — единственный директор'
description: 'Lync Server 2013: сводка по DNS — единый директор.'
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
ms.openlocfilehash: 78ef19383df45644ad951ca5da69ef893b231980
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48553235"
---
# <a name="dns-summary---single-director-in-lync-server-2013"></a><span data-ttu-id="0a8c7-103">Сводка по DNS — единственный директор в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0a8c7-103">DNS summary - Single Director in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0a8c7-104">_**Последнее изменение темы:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="0a8c7-104">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="0a8c7-105">В следующей таблице представлена сводная информация о записях DNS, необходимых для поддержки одного директора.</span><span class="sxs-lookup"><span data-stu-id="0a8c7-105">The following table contains a summary of the DNS records that are required to support the single Director.</span></span> <span data-ttu-id="0a8c7-106">Роли директора необходимы аналогичные записи DNS в качестве сервера переднего плана.</span><span class="sxs-lookup"><span data-stu-id="0a8c7-106">The role of the Director requires similar DNS records as the Front End Server.</span></span> <span data-ttu-id="0a8c7-107">Количество необходимых записей отражается в альтернативных именах субъектов, необходимых для сертификата директора.</span><span class="sxs-lookup"><span data-stu-id="0a8c7-107">The number of records needed is reflected in the subject alternative names required on the Director certificate.</span></span> <span data-ttu-id="0a8c7-108">От сервера переднего плана директор не размещает учетные записи пользователей или не размещает службы Mobility Service.</span><span class="sxs-lookup"><span data-stu-id="0a8c7-108">Different from the Front End Server, the Director does not host user accounts or host the Mobility Services.</span></span>

### <a name="dns-records-required-for-the-director"></a><span data-ttu-id="0a8c7-109">Записи DNS, необходимые для директора</span><span class="sxs-lookup"><span data-stu-id="0a8c7-109">DNS Records Required for the Director</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0a8c7-110">Расположение/тип/порт</span><span class="sxs-lookup"><span data-stu-id="0a8c7-110">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="0a8c7-111">Полное доменное имя/Запись DNS</span><span class="sxs-lookup"><span data-stu-id="0a8c7-111">FQDN/DNS Record</span></span></th>
<th><span data-ttu-id="0a8c7-112">IP-адрес/Полное доменное имя</span><span class="sxs-lookup"><span data-stu-id="0a8c7-112">IP Address/FQDN</span></span></th>
<th><span data-ttu-id="0a8c7-113">Сопоставляется с/комментарии</span><span class="sxs-lookup"><span data-stu-id="0a8c7-113">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0a8c7-114">Внутренняя запись DNS/A</span><span class="sxs-lookup"><span data-stu-id="0a8c7-114">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="0a8c7-115">dir01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="0a8c7-115">dir01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="0a8c7-116">Директор</span><span class="sxs-lookup"><span data-stu-id="0a8c7-116">Director</span></span></p></td>
<td><p><span data-ttu-id="0a8c7-117">Запись узла директора, используемая для репликации и сервера на сервер</span><span class="sxs-lookup"><span data-stu-id="0a8c7-117">Director host record used for replication and server to server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0a8c7-118">Внутренняя запись DNS/A</span><span class="sxs-lookup"><span data-stu-id="0a8c7-118">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="0a8c7-119">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="0a8c7-119">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="0a8c7-120">Директор</span><span class="sxs-lookup"><span data-stu-id="0a8c7-120">Director</span></span></p></td>
<td><p><span data-ttu-id="0a8c7-121">Входящий протокол SIP из внутреннего пограничного интерфейса пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="0a8c7-121">Inbound session initiation protocol (SIP) from the internal Edge interface of the Edge Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0a8c7-122">Внутренняя запись DNS/A</span><span class="sxs-lookup"><span data-stu-id="0a8c7-122">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="0a8c7-123">dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="0a8c7-123">dialin.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="0a8c7-124">Директор</span><span class="sxs-lookup"><span data-stu-id="0a8c7-124">Director</span></span></p></td>
<td><p><span data-ttu-id="0a8c7-125">Опубликованные веб-службы удаленного доступа обратного прокси-сервера</span><span class="sxs-lookup"><span data-stu-id="0a8c7-125">Published dialin web services from reverse proxy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0a8c7-126">Внутренний DNS/A</span><span class="sxs-lookup"><span data-stu-id="0a8c7-126">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="0a8c7-127">meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="0a8c7-127">meet.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="0a8c7-128">Директор</span><span class="sxs-lookup"><span data-stu-id="0a8c7-128">Director</span></span></p></td>
<td><p><span data-ttu-id="0a8c7-129">Опубликованные веб-службы собраний обратного прокси-сервера</span><span class="sxs-lookup"><span data-stu-id="0a8c7-129">Published meet web services from reverse proxy</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0a8c7-130">Внутренний DNS/A</span><span class="sxs-lookup"><span data-stu-id="0a8c7-130">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="0a8c7-131">webdirexternal.contoso.com</span><span class="sxs-lookup"><span data-stu-id="0a8c7-131">webdirexternal.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="0a8c7-132">Директор</span><span class="sxs-lookup"><span data-stu-id="0a8c7-132">Director</span></span></p></td>
<td><p><span data-ttu-id="0a8c7-133">Опубликовано и определено внешними службами веб-билетов обратного прокси-сервера для директора</span><span class="sxs-lookup"><span data-stu-id="0a8c7-133">Published and defined by the reverse proxy Web Ticket external web services for the Director</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

