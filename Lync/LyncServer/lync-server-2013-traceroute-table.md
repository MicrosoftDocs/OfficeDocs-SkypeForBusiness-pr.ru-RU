---
title: 'Lync Server 2013: таблица Трацерауте'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: TraceRoute table
ms:assetid: b9493cef-6ece-4f13-bf68-dbf132aab4f4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205205(v=OCS.15)
ms:contentKeyID: 48185242
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9d0aa4d6d60c57adb35086ce653cbd906f11c600
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48530366"
---
# <a name="traceroute-table-in-lync-server-2013"></a><span data-ttu-id="ab938-102">Таблица Трацерауте в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ab938-102">TraceRoute table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ab938-103">_**Последнее изменение темы:** 2014-02-21_</span><span class="sxs-lookup"><span data-stu-id="ab938-103">_**Topic Last Modified:** 2014-02-21_</span></span>

<span data-ttu-id="ab938-104">Таблица TraceRoute содержит сведения о маршрутизации звонков.</span><span class="sxs-lookup"><span data-stu-id="ab938-104">The TraceRoute table contains routing information from calls.</span></span> <span data-ttu-id="ab938-105">Эта таблица была введена в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ab938-105">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ab938-106"><strong>Column</strong></span><span class="sxs-lookup"><span data-stu-id="ab938-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="ab938-107"><strong>Тип данных</strong></span><span class="sxs-lookup"><span data-stu-id="ab938-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="ab938-108"><strong>Ключ или индекс</strong></span><span class="sxs-lookup"><span data-stu-id="ab938-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="ab938-109"><strong>Details</strong></span><span class="sxs-lookup"><span data-stu-id="ab938-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ab938-110"><strong>конференцедатетиме</strong></span><span class="sxs-lookup"><span data-stu-id="ab938-110"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="ab938-111">datetime</span><span class="sxs-lookup"><span data-stu-id="ab938-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="ab938-112">Первичный, внешний</span><span class="sxs-lookup"><span data-stu-id="ab938-112">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="ab938-113">Дата и время начала звонка.</span><span class="sxs-lookup"><span data-stu-id="ab938-113">Date and time that the call began.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ab938-114"><strong>сессионсек</strong></span><span class="sxs-lookup"><span data-stu-id="ab938-114"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="ab938-115">int</span><span class="sxs-lookup"><span data-stu-id="ab938-115">int</span></span></p></td>
<td><p><span data-ttu-id="ab938-116">Первичный, внешний</span><span class="sxs-lookup"><span data-stu-id="ab938-116">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="ab938-117">Уникальный идентификатор, используемых для однозначной идентификации звонков, которые могут начаться одновременно.</span><span class="sxs-lookup"><span data-stu-id="ab938-117">Unique identifier used to distinguish between multiple calls that might have begun on the same date and at the same time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ab938-118"><strong>медиалинелабел</strong></span><span class="sxs-lookup"><span data-stu-id="ab938-118"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="ab938-119">tinyint</span><span class="sxs-lookup"><span data-stu-id="ab938-119">tinyint</span></span></p></td>
<td><p><span data-ttu-id="ab938-120">Основной, внешний</span><span class="sxs-lookup"><span data-stu-id="ab938-120">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="ab938-p102">Представляет тип видеоканала, используемого для звонка. Допускаются следующие значения:</span><span class="sxs-lookup"><span data-stu-id="ab938-p102">Represents the type of video line used in the call. Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="ab938-123">0 — звук</span><span class="sxs-lookup"><span data-stu-id="ab938-123">0 – Audio</span></span></p></li>
<li><p><span data-ttu-id="ab938-124">1 — видео</span><span class="sxs-lookup"><span data-stu-id="ab938-124">1 – Video</span></span></p></li>
<li><p><span data-ttu-id="ab938-125">2 — панорамное видео</span><span class="sxs-lookup"><span data-stu-id="ab938-125">2 – Panoramic video</span></span></p></li>
<li><p><span data-ttu-id="ab938-126">3 — общий доступ к приложениям и рабочим столам</span><span class="sxs-lookup"><span data-stu-id="ab938-126">3 – Application/Desktop sharing</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ab938-127"><strong>фромкаллер</strong></span><span class="sxs-lookup"><span data-stu-id="ab938-127"><strong>FromCaller</strong></span></span></p></td>
<td><p><span data-ttu-id="ab938-128">Битовая</span><span class="sxs-lookup"><span data-stu-id="ab938-128">bit</span></span></p></td>
<td><p><span data-ttu-id="ab938-129">Primary</span><span class="sxs-lookup"><span data-stu-id="ab938-129">Primary</span></span></p></td>
<td><p><span data-ttu-id="ab938-130">Конечная точка, выполнившая звонок.</span><span class="sxs-lookup"><span data-stu-id="ab938-130">Endpoint that placed the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ab938-131"><strong>Перехода</strong></span><span class="sxs-lookup"><span data-stu-id="ab938-131"><strong>Hop</strong></span></span></p></td>
<td><p><span data-ttu-id="ab938-132">int</span><span class="sxs-lookup"><span data-stu-id="ab938-132">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ab938-133">Переход между сетями.</span><span class="sxs-lookup"><span data-stu-id="ab938-133">Network hop/</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ab938-134"><strong>ипаддресскэй</strong></span><span class="sxs-lookup"><span data-stu-id="ab938-134"><strong>IPAddressKey</strong></span></span></p></td>
<td><p><span data-ttu-id="ab938-135">int</span><span class="sxs-lookup"><span data-stu-id="ab938-135">int</span></span></p></td>
<td><p><span data-ttu-id="ab938-136">Правительства</span><span class="sxs-lookup"><span data-stu-id="ab938-136">Foreign</span></span></p></td>
<td><p><span data-ttu-id="ab938-137">Уникальный идентификатор IP-адреса.</span><span class="sxs-lookup"><span data-stu-id="ab938-137">Unique identifier for the IP address.</span></span> <span data-ttu-id="ab938-138">Сведения об IP-адресе хранятся в <a href="lync-server-2013-ipaddress-table.md">таблице IPAddress в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="ab938-138">IP address information is stored in the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ab938-139"><strong>ПРИЕМА</strong></span><span class="sxs-lookup"><span data-stu-id="ab938-139"><strong>RTT</strong></span></span></p></td>
<td><p><span data-ttu-id="ab938-140">int</span><span class="sxs-lookup"><span data-stu-id="ab938-140">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ab938-p104">Время цикла. Это время, которое требуется на то, чтобы пакет с голосовыми данными достиг назначения и отправил обратно уведомление о том, что он был получен.</span><span class="sxs-lookup"><span data-stu-id="ab938-p104">Roundtrip time. The roundtrip time measures the amount of time it takes for a voice packet to reach its destination and then send back notification that it was received.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

