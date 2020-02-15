---
title: 'Lync Server 2013: сводка по DNS — балансировка нагрузки на DNS и HLB'
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
ms.openlocfilehash: 11128cb1989bfc2863fe52fe27d0c86eb4b468a9
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42029570"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-summary---dns-and-hlb-load-balanced-in-lync-server-2013"></a><span data-ttu-id="a8edf-102">Сводка по DNS — балансировка нагрузки на DNS и HLB в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a8edf-102">DNS summary - DNS and HLB load balanced in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a8edf-103">_**Последнее изменение темы:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="a8edf-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="a8edf-104">В следующей таблице приведена сводка DNS-записей, необходимых для поддержки директора балансировки нагрузки на DNS и аппаратного директора балансировки нагрузки.</span><span class="sxs-lookup"><span data-stu-id="a8edf-104">The following table contains a summary of the DNS records that are required to support the DNS load balanced and hardware load balanced Director.</span></span> <span data-ttu-id="a8edf-105">Роли директора необходимы аналогичные записи DNS в качестве сервера переднего плана.</span><span class="sxs-lookup"><span data-stu-id="a8edf-105">The role of the Director requires similar DNS records as the Front End Server.</span></span> <span data-ttu-id="a8edf-106">Количество необходимых записей отражается в альтернативных именах субъектов, необходимых для сертификата директора.</span><span class="sxs-lookup"><span data-stu-id="a8edf-106">The number of records needed is reflected in the subject alternative names required on the Director certificate.</span></span> <span data-ttu-id="a8edf-107">От сервера переднего плана директору пула не размещаются учетные записи пользователей или не размещаются службы Mobility Service.</span><span class="sxs-lookup"><span data-stu-id="a8edf-107">Different from the Front End Server, the Director pool does not host user accounts or host the Mobility Services.</span></span>

### <a name="dns-records-required-for-the-director-pool-using-dns-load-balancing-and-hardware-load-balancer"></a><span data-ttu-id="a8edf-108">DNS-записи, обязательные для пула каталогов, использующего балансировщик нагрузки DNS и аппаратный балансировщик нагрузки</span><span class="sxs-lookup"><span data-stu-id="a8edf-108">DNS Records Required for the Director Pool using DNS Load Balancing and Hardware Load Balancer</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a8edf-109">Расположение/тип/порт</span><span class="sxs-lookup"><span data-stu-id="a8edf-109">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="a8edf-110">Полное доменное имя/Запись DNS</span><span class="sxs-lookup"><span data-stu-id="a8edf-110">FQDN/DNS Record</span></span></th>
<th><span data-ttu-id="a8edf-111">IP-адрес/Полное доменное имя</span><span class="sxs-lookup"><span data-stu-id="a8edf-111">IP Address/FQDN</span></span></th>
<th><span data-ttu-id="a8edf-112">Сопоставляется с/комментарии</span><span class="sxs-lookup"><span data-stu-id="a8edf-112">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a8edf-113">Внутренний DNS/A</span><span class="sxs-lookup"><span data-stu-id="a8edf-113">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="a8edf-114">dir01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="a8edf-114">dir01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="a8edf-115">Режиссер</span><span class="sxs-lookup"><span data-stu-id="a8edf-115">Director</span></span></p></td>
<td><p><span data-ttu-id="a8edf-116">Запись узла директора, используемая для репликации и сервера на сервер</span><span class="sxs-lookup"><span data-stu-id="a8edf-116">Director host record used for replication and server to server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a8edf-117">Внутренняя запись DNS/A</span><span class="sxs-lookup"><span data-stu-id="a8edf-117">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="a8edf-118">dirpool01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="a8edf-118">dirpool01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="a8edf-119">Пул директоров</span><span class="sxs-lookup"><span data-stu-id="a8edf-119">Director pool</span></span></p></td>
<td><p><span data-ttu-id="a8edf-120">Запись узла для пула пула балансировки нагрузки DNS для сервера на сервер</span><span class="sxs-lookup"><span data-stu-id="a8edf-120">Host record for the DNS load balanced Director pool for server to server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a8edf-121">Внутренняя запись DNS/A</span><span class="sxs-lookup"><span data-stu-id="a8edf-121">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="a8edf-122">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="a8edf-122">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="a8edf-123">Пул директоров</span><span class="sxs-lookup"><span data-stu-id="a8edf-123">Director pool</span></span></p></td>
<td><p><span data-ttu-id="a8edf-124">Входящий протокол SIP из внутреннего интерфейса пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="a8edf-124">Inbound session initiation protocol (SIP) from the internal interface of the Edge Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a8edf-125">Внутренняя запись DNS/A</span><span class="sxs-lookup"><span data-stu-id="a8edf-125">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="a8edf-126">dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="a8edf-126">dialin.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="a8edf-127">Виртуальный IP-адрес пула директоров HLB</span><span class="sxs-lookup"><span data-stu-id="a8edf-127">Director pool HLB VIP</span></span></p></td>
<td><p><span data-ttu-id="a8edf-128">Аппаратный балансировщик нагрузки, опубликованный веб-службами dialin с обратного прокси-сервера</span><span class="sxs-lookup"><span data-stu-id="a8edf-128">Hardware load balanced published dialin web services from reverse proxy</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a8edf-129">Внутренняя запись DNS/A</span><span class="sxs-lookup"><span data-stu-id="a8edf-129">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="a8edf-130">meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="a8edf-130">meet.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="a8edf-131">Виртуальный IP-адрес пула директоров HLB</span><span class="sxs-lookup"><span data-stu-id="a8edf-131">Director pool HLB VIP</span></span></p></td>
<td><p><span data-ttu-id="a8edf-132">Аппаратный балансировщик нагрузки, опубликованный веб-службами meet с обратного прокси-сервера</span><span class="sxs-lookup"><span data-stu-id="a8edf-132">Hardware load balanced published meet web services from reverse proxy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a8edf-133">Внутренняя запись DNS/A</span><span class="sxs-lookup"><span data-stu-id="a8edf-133">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="a8edf-134">webdirexternal.contoso.com</span><span class="sxs-lookup"><span data-stu-id="a8edf-134">webdirexternal.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="a8edf-135">Виртуальный IP-адрес пула директоров HLB</span><span class="sxs-lookup"><span data-stu-id="a8edf-135">Director pool HLB VIP</span></span></p></td>
<td><p><span data-ttu-id="a8edf-136">Аппаратный балансировщик нагрузки, опубликованный и определенный внешними службами веб-билетов обратного прокси-сервера для пула директора</span><span class="sxs-lookup"><span data-stu-id="a8edf-136">Hardware load balanced published and defined by the reverse proxy Web Ticket external web services for the Director pool</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

