---
title: 'Lync Server 2013: сводка по DNS — балансировка нагрузки на DNS и HLB'
description: 'Lync Server 2013: сводка по DNS для балансировки нагрузки на DNS и HLB.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS summary - DNS and HLB load balanced
ms:assetid: d2132695-1956-4190-a98e-cd7255cbded6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205273(v=OCS.15)
ms:contentKeyID: 48185447
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 81c191d653ce4025618e135b4c69bc673f79a6d9
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48574265"
---
# <a name="dns-summary---dns-and-hlb-load-balanced-in-lync-server-2013"></a><span data-ttu-id="b1aae-103">Сводка по DNS — балансировка нагрузки на DNS и HLB в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b1aae-103">DNS summary - DNS and HLB load balanced in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b1aae-104">_**Последнее изменение темы:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="b1aae-104">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="b1aae-105">В следующей таблице приведена сводка DNS-записей, необходимых для поддержки директора балансировки нагрузки на DNS и аппаратного директора балансировки нагрузки.</span><span class="sxs-lookup"><span data-stu-id="b1aae-105">The following table contains a summary of the DNS records that are required to support the DNS load balanced and hardware load balanced Director.</span></span> <span data-ttu-id="b1aae-106">Роли директора необходимы аналогичные записи DNS в качестве сервера переднего плана.</span><span class="sxs-lookup"><span data-stu-id="b1aae-106">The role of the Director requires similar DNS records as the Front End Server.</span></span> <span data-ttu-id="b1aae-107">Количество необходимых записей отражается в альтернативных именах субъектов, необходимых для сертификата директора.</span><span class="sxs-lookup"><span data-stu-id="b1aae-107">The number of records needed is reflected in the subject alternative names required on the Director certificate.</span></span> <span data-ttu-id="b1aae-108">От сервера переднего плана директору пула не размещаются учетные записи пользователей или не размещаются службы Mobility Service.</span><span class="sxs-lookup"><span data-stu-id="b1aae-108">Different from the Front End Server, the Director pool does not host user accounts or host the Mobility Services.</span></span>

### <a name="dns-records-required-for-the-director-pool-using-dns-load-balancing-and-hardware-load-balancer"></a><span data-ttu-id="b1aae-109">DNS-записи, обязательные для пула каталогов, использующего балансировщик нагрузки DNS и аппаратный балансировщик нагрузки</span><span class="sxs-lookup"><span data-stu-id="b1aae-109">DNS Records Required for the Director Pool using DNS Load Balancing and Hardware Load Balancer</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b1aae-110">Расположение/тип/порт</span><span class="sxs-lookup"><span data-stu-id="b1aae-110">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="b1aae-111">Полное доменное имя/Запись DNS</span><span class="sxs-lookup"><span data-stu-id="b1aae-111">FQDN/DNS Record</span></span></th>
<th><span data-ttu-id="b1aae-112">IP-адрес/Полное доменное имя</span><span class="sxs-lookup"><span data-stu-id="b1aae-112">IP Address/FQDN</span></span></th>
<th><span data-ttu-id="b1aae-113">Сопоставляется с/комментарии</span><span class="sxs-lookup"><span data-stu-id="b1aae-113">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b1aae-114">Внутренняя запись DNS/A</span><span class="sxs-lookup"><span data-stu-id="b1aae-114">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="b1aae-115">dir01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="b1aae-115">dir01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="b1aae-116">Директор</span><span class="sxs-lookup"><span data-stu-id="b1aae-116">Director</span></span></p></td>
<td><p><span data-ttu-id="b1aae-117">Запись узла директора, используемая для репликации и сервера на сервер</span><span class="sxs-lookup"><span data-stu-id="b1aae-117">Director host record used for replication and server to server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b1aae-118">Внутренняя запись DNS/A</span><span class="sxs-lookup"><span data-stu-id="b1aae-118">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="b1aae-119">dirpool01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="b1aae-119">dirpool01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="b1aae-120">Пул директоров</span><span class="sxs-lookup"><span data-stu-id="b1aae-120">Director pool</span></span></p></td>
<td><p><span data-ttu-id="b1aae-121">Запись узла для пула пула балансировки нагрузки DNS для сервера на сервер</span><span class="sxs-lookup"><span data-stu-id="b1aae-121">Host record for the DNS load balanced Director pool for server to server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b1aae-122">Внутренняя запись DNS/A</span><span class="sxs-lookup"><span data-stu-id="b1aae-122">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="b1aae-123">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="b1aae-123">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="b1aae-124">Пул директоров</span><span class="sxs-lookup"><span data-stu-id="b1aae-124">Director pool</span></span></p></td>
<td><p><span data-ttu-id="b1aae-125">Входящий протокол SIP из внутреннего интерфейса пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="b1aae-125">Inbound session initiation protocol (SIP) from the internal interface of the Edge Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b1aae-126">Внутренняя запись DNS/A</span><span class="sxs-lookup"><span data-stu-id="b1aae-126">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="b1aae-127">dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="b1aae-127">dialin.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="b1aae-128">Виртуальный IP-адрес пула директоров HLB</span><span class="sxs-lookup"><span data-stu-id="b1aae-128">Director pool HLB VIP</span></span></p></td>
<td><p><span data-ttu-id="b1aae-129">Аппаратный балансировщик нагрузки, опубликованный веб-службами dialin с обратного прокси-сервера</span><span class="sxs-lookup"><span data-stu-id="b1aae-129">Hardware load balanced published dialin web services from reverse proxy</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b1aae-130">Внутренняя запись DNS/A</span><span class="sxs-lookup"><span data-stu-id="b1aae-130">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="b1aae-131">meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="b1aae-131">meet.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="b1aae-132">Виртуальный IP-адрес пула директоров HLB</span><span class="sxs-lookup"><span data-stu-id="b1aae-132">Director pool HLB VIP</span></span></p></td>
<td><p><span data-ttu-id="b1aae-133">Аппаратный балансировщик нагрузки, опубликованный веб-службами meet с обратного прокси-сервера</span><span class="sxs-lookup"><span data-stu-id="b1aae-133">Hardware load balanced published meet web services from reverse proxy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b1aae-134">Внутренняя запись DNS/A</span><span class="sxs-lookup"><span data-stu-id="b1aae-134">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="b1aae-135">webdirexternal.contoso.com</span><span class="sxs-lookup"><span data-stu-id="b1aae-135">webdirexternal.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="b1aae-136">Виртуальный IP-адрес пула директоров HLB</span><span class="sxs-lookup"><span data-stu-id="b1aae-136">Director pool HLB VIP</span></span></p></td>
<td><p><span data-ttu-id="b1aae-137">Аппаратный балансировщик нагрузки, опубликованный и определенный внешними службами веб-билетов обратного прокси-сервера для пула директора</span><span class="sxs-lookup"><span data-stu-id="b1aae-137">Hardware load balanced published and defined by the reverse proxy Web Ticket external web services for the Director pool</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

