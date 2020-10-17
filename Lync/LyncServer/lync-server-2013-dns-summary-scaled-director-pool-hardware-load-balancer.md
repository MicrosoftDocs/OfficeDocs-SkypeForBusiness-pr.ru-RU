---
title: 'Lync Server 2013: сводка по DNS — масштабируемый пул директоров, аппаратный балансировщик нагрузки'
description: 'Lync Server 2013: сводка по DNS — масштабируемый пул директоров, аппаратный балансировщик нагрузки.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS summary - Scaled Director pool, hardware load balancer
ms:assetid: 08ba48e6-bfa1-4ab0-bc89-d58ddb9c20af
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204655(v=OCS.15)
ms:contentKeyID: 48183340
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7198e6a97feed8ce70cb16753ad1f21d58ef246c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48555885"
---
# <a name="dns-summary---scaled-director-pool-hardware-load-balancer-in-lync-server-2013"></a><span data-ttu-id="0ca14-103">Сводка по DNS — масштабируемый пул директоров, аппаратный балансировщик нагрузки в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0ca14-103">DNS summary - Scaled Director pool, hardware load balancer in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0ca14-104">_**Последнее изменение темы:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="0ca14-104">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="0ca14-105">В следующей таблице приведена сводка DNS-записей, необходимых для поддержки директора аппаратной балансировки нагрузки.</span><span class="sxs-lookup"><span data-stu-id="0ca14-105">The following table contains a summary of the DNS records that are required to support the hardware load balanced Director.</span></span> <span data-ttu-id="0ca14-106">Роли директора необходимы аналогичные записи DNS в качестве сервера переднего плана.</span><span class="sxs-lookup"><span data-stu-id="0ca14-106">The role of the Director requires similar DNS records as the Front End Server.</span></span> <span data-ttu-id="0ca14-107">Количество необходимых записей отражается в альтернативных именах субъектов, необходимых для сертификата директора.</span><span class="sxs-lookup"><span data-stu-id="0ca14-107">The number of records needed is reflected in the subject alternative names required on the Director certificate.</span></span> <span data-ttu-id="0ca14-108">От сервера переднего плана директору пула не размещаются учетные записи пользователей или не размещаются службы Mobility Service.</span><span class="sxs-lookup"><span data-stu-id="0ca14-108">Different from the Front End Server, the Director pool does not host user accounts or host the Mobility Services.</span></span>

### <a name="dns-records-required-for-the-director-pool-using-a-hardware-load-balancer-and-dns-load-balancing"></a><span data-ttu-id="0ca14-109">Записи DNS, необходимые для пула директоров с использованием аппаратной подсистемы балансировки нагрузки и балансировки нагрузки на DNS</span><span class="sxs-lookup"><span data-stu-id="0ca14-109">DNS Records Required for the Director pool using a Hardware Load Balancer and DNS Load Balancing</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0ca14-110">Расположение/тип/порт</span><span class="sxs-lookup"><span data-stu-id="0ca14-110">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="0ca14-111">Полное доменное имя/Запись DNS</span><span class="sxs-lookup"><span data-stu-id="0ca14-111">FQDN/DNS Record</span></span></th>
<th><span data-ttu-id="0ca14-112">IP-адрес/Полное доменное имя</span><span class="sxs-lookup"><span data-stu-id="0ca14-112">IP Address/FQDN</span></span></th>
<th><span data-ttu-id="0ca14-113">Сопоставляется с/комментарии</span><span class="sxs-lookup"><span data-stu-id="0ca14-113">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0ca14-114">Внутренняя запись DNS/A</span><span class="sxs-lookup"><span data-stu-id="0ca14-114">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="0ca14-115">dir01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="0ca14-115">dir01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="0ca14-116">Директор</span><span class="sxs-lookup"><span data-stu-id="0ca14-116">Director</span></span></p></td>
<td><p><span data-ttu-id="0ca14-117">Запись узла директора, используемая для обмена данными между репликацией и сервером</span><span class="sxs-lookup"><span data-stu-id="0ca14-117">Director host record used for replication and server to server communication</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0ca14-118">Внутренняя запись DNS/A</span><span class="sxs-lookup"><span data-stu-id="0ca14-118">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="0ca14-119">dirpool01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="0ca14-119">dirpool01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="0ca14-120">Виртуальный IP-адрес пула директоров HLB</span><span class="sxs-lookup"><span data-stu-id="0ca14-120">Director pool HLB VIP</span></span></p></td>
<td><p><span data-ttu-id="0ca14-121">Запись узла для пула директоров с балансировкой нагрузки DNS</span><span class="sxs-lookup"><span data-stu-id="0ca14-121">Host record for the DNS load balanced Director pool</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0ca14-122">Внутренняя запись DNS/A</span><span class="sxs-lookup"><span data-stu-id="0ca14-122">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="0ca14-123">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="0ca14-123">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="0ca14-124">Виртуальный IP-адрес пула директоров HLB</span><span class="sxs-lookup"><span data-stu-id="0ca14-124">Director pool HLB VIP</span></span></p></td>
<td><p><span data-ttu-id="0ca14-125">Входящий протокол SIP из внутреннего интерфейса пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="0ca14-125">Inbound session initiation protocol (SIP) from the internal interface of the Edge Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0ca14-126">Внутренняя запись DNS/A</span><span class="sxs-lookup"><span data-stu-id="0ca14-126">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="0ca14-127">dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="0ca14-127">dialin.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="0ca14-128">Виртуальный IP-адрес пула директоров HLB</span><span class="sxs-lookup"><span data-stu-id="0ca14-128">Director pool HLB VIP</span></span></p></td>
<td><p><span data-ttu-id="0ca14-129">Аппаратный балансировщик нагрузки, опубликованный веб-службами dialin с обратного прокси-сервера</span><span class="sxs-lookup"><span data-stu-id="0ca14-129">Hardware load balanced published dialin web services from reverse proxy</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0ca14-130">Внутренняя запись DNS/A</span><span class="sxs-lookup"><span data-stu-id="0ca14-130">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="0ca14-131">meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="0ca14-131">meet.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="0ca14-132">Виртуальный IP-адрес пула директоров HLB</span><span class="sxs-lookup"><span data-stu-id="0ca14-132">Director pool HLB VIP</span></span></p></td>
<td><p><span data-ttu-id="0ca14-133">Аппаратный балансировщик нагрузки, опубликованный веб-службами meet с обратного прокси-сервера</span><span class="sxs-lookup"><span data-stu-id="0ca14-133">Hardware load balanced published meet web services from reverse proxy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0ca14-134">Внутренняя запись DNS/A</span><span class="sxs-lookup"><span data-stu-id="0ca14-134">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="0ca14-135">webdirexternal.contoso.com</span><span class="sxs-lookup"><span data-stu-id="0ca14-135">webdirexternal.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="0ca14-136">Виртуальный IP-адрес пула директоров HLB</span><span class="sxs-lookup"><span data-stu-id="0ca14-136">Director pool HLB VIP</span></span></p></td>
<td><p><span data-ttu-id="0ca14-137">Аппаратный балансировщик нагрузки, опубликованный и определенный внешними службами веб-билетов обратного прокси-сервера для пула директора</span><span class="sxs-lookup"><span data-stu-id="0ca14-137">Hardware load balanced published and defined by the reverse proxy Web Ticket external web services for the Director pool</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

