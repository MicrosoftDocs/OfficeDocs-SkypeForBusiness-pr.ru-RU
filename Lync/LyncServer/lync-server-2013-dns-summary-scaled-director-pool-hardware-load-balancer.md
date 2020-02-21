---
title: 'Lync Server 2013: сводка по DNS — масштабируемый пул директоров, аппаратный балансировщик нагрузки'
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
ms.openlocfilehash: 10c742d8d58392b06bc563cd0a947d46243703d7
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42192922"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="dns-summary---scaled-director-pool-hardware-load-balancer-in-lync-server-2013"></a><span data-ttu-id="8603f-102">Сводка по DNS — масштабируемый пул директоров, аппаратный балансировщик нагрузки в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8603f-102">DNS summary - Scaled Director pool, hardware load balancer in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8603f-103">_**Последнее изменение темы:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="8603f-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="8603f-104">В следующей таблице приведена сводка DNS-записей, необходимых для поддержки директора аппаратной балансировки нагрузки.</span><span class="sxs-lookup"><span data-stu-id="8603f-104">The following table contains a summary of the DNS records that are required to support the hardware load balanced Director.</span></span> <span data-ttu-id="8603f-105">Роли директора необходимы аналогичные записи DNS в качестве сервера переднего плана.</span><span class="sxs-lookup"><span data-stu-id="8603f-105">The role of the Director requires similar DNS records as the Front End Server.</span></span> <span data-ttu-id="8603f-106">Количество необходимых записей отражается в альтернативных именах субъектов, необходимых для сертификата директора.</span><span class="sxs-lookup"><span data-stu-id="8603f-106">The number of records needed is reflected in the subject alternative names required on the Director certificate.</span></span> <span data-ttu-id="8603f-107">От сервера переднего плана директору пула не размещаются учетные записи пользователей или не размещаются службы Mobility Service.</span><span class="sxs-lookup"><span data-stu-id="8603f-107">Different from the Front End Server, the Director pool does not host user accounts or host the Mobility Services.</span></span>

### <a name="dns-records-required-for-the-director-pool-using-a-hardware-load-balancer-and-dns-load-balancing"></a><span data-ttu-id="8603f-108">Записи DNS, необходимые для пула директоров с использованием аппаратной подсистемы балансировки нагрузки и балансировки нагрузки на DNS</span><span class="sxs-lookup"><span data-stu-id="8603f-108">DNS Records Required for the Director pool using a Hardware Load Balancer and DNS Load Balancing</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8603f-109">Расположение/тип/порт</span><span class="sxs-lookup"><span data-stu-id="8603f-109">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="8603f-110">Полное доменное имя/Запись DNS</span><span class="sxs-lookup"><span data-stu-id="8603f-110">FQDN/DNS Record</span></span></th>
<th><span data-ttu-id="8603f-111">IP-адрес/Полное доменное имя</span><span class="sxs-lookup"><span data-stu-id="8603f-111">IP Address/FQDN</span></span></th>
<th><span data-ttu-id="8603f-112">Сопоставляется с/комментарии</span><span class="sxs-lookup"><span data-stu-id="8603f-112">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8603f-113">Внутренний DNS/A</span><span class="sxs-lookup"><span data-stu-id="8603f-113">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="8603f-114">dir01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="8603f-114">dir01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="8603f-115">Режиссер</span><span class="sxs-lookup"><span data-stu-id="8603f-115">Director</span></span></p></td>
<td><p><span data-ttu-id="8603f-116">Запись узла директора, используемая для обмена данными между репликацией и сервером</span><span class="sxs-lookup"><span data-stu-id="8603f-116">Director host record used for replication and server to server communication</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8603f-117">Внутренняя запись DNS/A</span><span class="sxs-lookup"><span data-stu-id="8603f-117">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="8603f-118">dirpool01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="8603f-118">dirpool01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="8603f-119">Виртуальный IP-адрес пула директоров HLB</span><span class="sxs-lookup"><span data-stu-id="8603f-119">Director pool HLB VIP</span></span></p></td>
<td><p><span data-ttu-id="8603f-120">Запись узла для пула директоров с балансировкой нагрузки DNS</span><span class="sxs-lookup"><span data-stu-id="8603f-120">Host record for the DNS load balanced Director pool</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8603f-121">Внутренняя запись DNS/A</span><span class="sxs-lookup"><span data-stu-id="8603f-121">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="8603f-122">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="8603f-122">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="8603f-123">Виртуальный IP-адрес пула директоров HLB</span><span class="sxs-lookup"><span data-stu-id="8603f-123">Director pool HLB VIP</span></span></p></td>
<td><p><span data-ttu-id="8603f-124">Входящий протокол SIP из внутреннего интерфейса пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="8603f-124">Inbound session initiation protocol (SIP) from the internal interface of the Edge Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8603f-125">Внутренняя запись DNS/A</span><span class="sxs-lookup"><span data-stu-id="8603f-125">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="8603f-126">dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="8603f-126">dialin.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="8603f-127">Виртуальный IP-адрес пула директоров HLB</span><span class="sxs-lookup"><span data-stu-id="8603f-127">Director pool HLB VIP</span></span></p></td>
<td><p><span data-ttu-id="8603f-128">Аппаратный балансировщик нагрузки, опубликованный веб-службами dialin с обратного прокси-сервера</span><span class="sxs-lookup"><span data-stu-id="8603f-128">Hardware load balanced published dialin web services from reverse proxy</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8603f-129">Внутренняя запись DNS/A</span><span class="sxs-lookup"><span data-stu-id="8603f-129">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="8603f-130">meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="8603f-130">meet.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="8603f-131">Виртуальный IP-адрес пула директоров HLB</span><span class="sxs-lookup"><span data-stu-id="8603f-131">Director pool HLB VIP</span></span></p></td>
<td><p><span data-ttu-id="8603f-132">Аппаратный балансировщик нагрузки, опубликованный веб-службами meet с обратного прокси-сервера</span><span class="sxs-lookup"><span data-stu-id="8603f-132">Hardware load balanced published meet web services from reverse proxy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8603f-133">Внутренняя запись DNS/A</span><span class="sxs-lookup"><span data-stu-id="8603f-133">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="8603f-134">webdirexternal.contoso.com</span><span class="sxs-lookup"><span data-stu-id="8603f-134">webdirexternal.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="8603f-135">Виртуальный IP-адрес пула директоров HLB</span><span class="sxs-lookup"><span data-stu-id="8603f-135">Director pool HLB VIP</span></span></p></td>
<td><p><span data-ttu-id="8603f-136">Аппаратный балансировщик нагрузки, опубликованный и определенный внешними службами веб-билетов обратного прокси-сервера для пула директора</span><span class="sxs-lookup"><span data-stu-id="8603f-136">Hardware load balanced published and defined by the reverse proxy Web Ticket external web services for the Director pool</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

