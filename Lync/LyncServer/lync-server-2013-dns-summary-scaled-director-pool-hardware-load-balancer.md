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
ms.openlocfilehash: 891b69339416c81d81e72e43edf5f09bbf9da3e3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741069"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-summary---scaled-director-pool-hardware-load-balancer-in-lync-server-2013"></a><span data-ttu-id="0d78a-102">Сводка по DNS — масштабируемый пул директоров, аппаратный балансировщик нагрузки в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0d78a-102">DNS summary - Scaled Director pool, hardware load balancer in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0d78a-103">_**Тема последнего изменения:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="0d78a-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="0d78a-104">В таблице ниже приведены сведения о DNS-записях, которые необходимы для работы директора аппаратной балансировки нагрузки.</span><span class="sxs-lookup"><span data-stu-id="0d78a-104">The following table contains a summary of the DNS records that are required to support the hardware load balanced Director.</span></span> <span data-ttu-id="0d78a-105">Роль режиссера требует наличия аналогичных записей DNS в качестве внешнего сервера.</span><span class="sxs-lookup"><span data-stu-id="0d78a-105">The role of the Director requires similar DNS records as the Front End Server.</span></span> <span data-ttu-id="0d78a-106">Количество необходимых записей отражается в альтернативных именах тем, необходимых для вашего сертификата в директории.</span><span class="sxs-lookup"><span data-stu-id="0d78a-106">The number of records needed is reflected in the subject alternative names required on the Director certificate.</span></span> <span data-ttu-id="0d78a-107">На сервере переднего плана не размещается учетные записи пользователей и не размещается служба Mobility Service.</span><span class="sxs-lookup"><span data-stu-id="0d78a-107">Different from the Front End Server, the Director pool does not host user accounts or host the Mobility Services.</span></span>

### <a name="dns-records-required-for-the-director-pool-using-a-hardware-load-balancer-and-dns-load-balancing"></a><span data-ttu-id="0d78a-108">DNS-записи, необходимые для пула режиссеров с помощью аппаратной подсистемы балансировки нагрузки и балансировки нагрузки DNS</span><span class="sxs-lookup"><span data-stu-id="0d78a-108">DNS Records Required for the Director pool using a Hardware Load Balancer and DNS Load Balancing</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0d78a-109">Расположение/тип/порт</span><span class="sxs-lookup"><span data-stu-id="0d78a-109">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="0d78a-110">Полное доменное имя/DNS-запись</span><span class="sxs-lookup"><span data-stu-id="0d78a-110">FQDN/DNS Record</span></span></th>
<th><span data-ttu-id="0d78a-111">IP-адрес или полное доменное имя</span><span class="sxs-lookup"><span data-stu-id="0d78a-111">IP Address/FQDN</span></span></th>
<th><span data-ttu-id="0d78a-112">Карты и примечания</span><span class="sxs-lookup"><span data-stu-id="0d78a-112">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0d78a-113">Внутренняя DNS/A</span><span class="sxs-lookup"><span data-stu-id="0d78a-113">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="0d78a-114">dir01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="0d78a-114">dir01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="0d78a-115">Директор</span><span class="sxs-lookup"><span data-stu-id="0d78a-115">Director</span></span></p></td>
<td><p><span data-ttu-id="0d78a-116">Запись узла директора, используемая для связи между репликацией и сервером</span><span class="sxs-lookup"><span data-stu-id="0d78a-116">Director host record used for replication and server to server communication</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0d78a-117">Внутренняя DNS/A</span><span class="sxs-lookup"><span data-stu-id="0d78a-117">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="0d78a-118">dirpool01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="0d78a-118">dirpool01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="0d78a-119">Пул ХЛБных ВИРТУАЛЬНЫХ каталогов</span><span class="sxs-lookup"><span data-stu-id="0d78a-119">Director pool HLB VIP</span></span></p></td>
<td><p><span data-ttu-id="0d78a-120">Запись Host для пула пулов балансировки нагрузки DNS</span><span class="sxs-lookup"><span data-stu-id="0d78a-120">Host record for the DNS load balanced Director pool</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0d78a-121">Внутренняя DNS/A</span><span class="sxs-lookup"><span data-stu-id="0d78a-121">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="0d78a-122">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="0d78a-122">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="0d78a-123">Пул ХЛБных ВИРТУАЛЬНЫХ каталогов</span><span class="sxs-lookup"><span data-stu-id="0d78a-123">Director pool HLB VIP</span></span></p></td>
<td><p><span data-ttu-id="0d78a-124">Протокол SIP, входящий в внутренний интерфейс пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="0d78a-124">Inbound session initiation protocol (SIP) from the internal interface of the Edge Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0d78a-125">Внутренняя DNS/A</span><span class="sxs-lookup"><span data-stu-id="0d78a-125">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="0d78a-126">dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="0d78a-126">dialin.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="0d78a-127">Пул ХЛБных ВИРТУАЛЬНЫХ каталогов</span><span class="sxs-lookup"><span data-stu-id="0d78a-127">Director pool HLB VIP</span></span></p></td>
<td><p><span data-ttu-id="0d78a-128">Подходящими для аппаратной балансировки нагрузки веб-службы, опубликованные из обратного прокси</span><span class="sxs-lookup"><span data-stu-id="0d78a-128">Hardware load balanced published dialin web services from reverse proxy</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0d78a-129">Внутренняя DNS/A</span><span class="sxs-lookup"><span data-stu-id="0d78a-129">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="0d78a-130">meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="0d78a-130">meet.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="0d78a-131">Пул ХЛБных ВИРТУАЛЬНЫХ каталогов</span><span class="sxs-lookup"><span data-stu-id="0d78a-131">Director pool HLB VIP</span></span></p></td>
<td><p><span data-ttu-id="0d78a-132">Служба балансировки нагрузки для оборудования, опубликованная в соответствии с обратной прокси-сервером</span><span class="sxs-lookup"><span data-stu-id="0d78a-132">Hardware load balanced published meet web services from reverse proxy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0d78a-133">Внутренняя DNS/A</span><span class="sxs-lookup"><span data-stu-id="0d78a-133">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="0d78a-134">webdirexternal.contoso.com</span><span class="sxs-lookup"><span data-stu-id="0d78a-134">webdirexternal.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="0d78a-135">Пул ХЛБных ВИРТУАЛЬНЫХ каталогов</span><span class="sxs-lookup"><span data-stu-id="0d78a-135">Director pool HLB VIP</span></span></p></td>
<td><p><span data-ttu-id="0d78a-136">Балансировка нагрузки для оборудования, опубликованная и определяемая внешними веб-службами обратного прокси, для директора пула</span><span class="sxs-lookup"><span data-stu-id="0d78a-136">Hardware load balanced published and defined by the reverse proxy Web Ticket external web services for the Director pool</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

