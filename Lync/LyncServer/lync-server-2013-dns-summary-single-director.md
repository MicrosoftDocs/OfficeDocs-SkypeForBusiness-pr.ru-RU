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
ms.openlocfilehash: 76fe7663e0af8eeeb049ca80f1dd92a7cc882b98
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137768"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="dns-summary---single-director-in-lync-server-2013"></a><span data-ttu-id="c3d70-102">Сводка по DNS — единственный директор в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c3d70-102">DNS summary - Single Director in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c3d70-103">_**Последнее изменение темы:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="c3d70-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="c3d70-104">В следующей таблице представлена сводная информация о записях DNS, необходимых для поддержки одного директора.</span><span class="sxs-lookup"><span data-stu-id="c3d70-104">The following table contains a summary of the DNS records that are required to support the single Director.</span></span> <span data-ttu-id="c3d70-105">Роли директора необходимы аналогичные записи DNS в качестве сервера переднего плана.</span><span class="sxs-lookup"><span data-stu-id="c3d70-105">The role of the Director requires similar DNS records as the Front End Server.</span></span> <span data-ttu-id="c3d70-106">Количество необходимых записей отражается в альтернативных именах субъектов, необходимых для сертификата директора.</span><span class="sxs-lookup"><span data-stu-id="c3d70-106">The number of records needed is reflected in the subject alternative names required on the Director certificate.</span></span> <span data-ttu-id="c3d70-107">От сервера переднего плана директор не размещает учетные записи пользователей или не размещает службы Mobility Service.</span><span class="sxs-lookup"><span data-stu-id="c3d70-107">Different from the Front End Server, the Director does not host user accounts or host the Mobility Services.</span></span>

### <a name="dns-records-required-for-the-director"></a><span data-ttu-id="c3d70-108">Записи DNS, необходимые для директора</span><span class="sxs-lookup"><span data-stu-id="c3d70-108">DNS Records Required for the Director</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c3d70-109">Расположение/тип/порт</span><span class="sxs-lookup"><span data-stu-id="c3d70-109">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="c3d70-110">Полное доменное имя/Запись DNS</span><span class="sxs-lookup"><span data-stu-id="c3d70-110">FQDN/DNS Record</span></span></th>
<th><span data-ttu-id="c3d70-111">IP-адрес/Полное доменное имя</span><span class="sxs-lookup"><span data-stu-id="c3d70-111">IP Address/FQDN</span></span></th>
<th><span data-ttu-id="c3d70-112">Сопоставляется с/комментарии</span><span class="sxs-lookup"><span data-stu-id="c3d70-112">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c3d70-113">Внутренняя запись DNS/A</span><span class="sxs-lookup"><span data-stu-id="c3d70-113">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="c3d70-114">dir01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="c3d70-114">dir01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="c3d70-115">Режиссер</span><span class="sxs-lookup"><span data-stu-id="c3d70-115">Director</span></span></p></td>
<td><p><span data-ttu-id="c3d70-116">Запись узла директора, используемая для репликации и сервера на сервер</span><span class="sxs-lookup"><span data-stu-id="c3d70-116">Director host record used for replication and server to server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c3d70-117">Внутренняя запись DNS/A</span><span class="sxs-lookup"><span data-stu-id="c3d70-117">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="c3d70-118">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="c3d70-118">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="c3d70-119">Режиссер</span><span class="sxs-lookup"><span data-stu-id="c3d70-119">Director</span></span></p></td>
<td><p><span data-ttu-id="c3d70-120">Входящий протокол SIP из внутреннего пограничного интерфейса пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="c3d70-120">Inbound session initiation protocol (SIP) from the internal Edge interface of the Edge Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c3d70-121">Внутренняя запись DNS/A</span><span class="sxs-lookup"><span data-stu-id="c3d70-121">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="c3d70-122">dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="c3d70-122">dialin.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="c3d70-123">Режиссер</span><span class="sxs-lookup"><span data-stu-id="c3d70-123">Director</span></span></p></td>
<td><p><span data-ttu-id="c3d70-124">Опубликованные веб-службы удаленного доступа обратного прокси-сервера</span><span class="sxs-lookup"><span data-stu-id="c3d70-124">Published dialin web services from reverse proxy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c3d70-125">Внутренняя запись DNS/A</span><span class="sxs-lookup"><span data-stu-id="c3d70-125">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="c3d70-126">meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="c3d70-126">meet.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="c3d70-127">Режиссер</span><span class="sxs-lookup"><span data-stu-id="c3d70-127">Director</span></span></p></td>
<td><p><span data-ttu-id="c3d70-128">Опубликованные веб-службы собраний обратного прокси-сервера</span><span class="sxs-lookup"><span data-stu-id="c3d70-128">Published meet web services from reverse proxy</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c3d70-129">Внутренний DNS/A</span><span class="sxs-lookup"><span data-stu-id="c3d70-129">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="c3d70-130">webdirexternal.contoso.com</span><span class="sxs-lookup"><span data-stu-id="c3d70-130">webdirexternal.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="c3d70-131">Режиссер</span><span class="sxs-lookup"><span data-stu-id="c3d70-131">Director</span></span></p></td>
<td><p><span data-ttu-id="c3d70-132">Опубликовано и определено внешними службами веб-билетов обратного прокси-сервера для директора</span><span class="sxs-lookup"><span data-stu-id="c3d70-132">Published and defined by the reverse proxy Web Ticket external web services for the Director</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

