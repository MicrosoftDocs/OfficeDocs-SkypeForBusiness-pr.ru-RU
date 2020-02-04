---
title: 'Lync Server 2013: таблица Media'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Media table
ms:assetid: 1e1b427f-59b5-4564-bde5-1002a80439ee
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398268(v=OCS.15)
ms:contentKeyID: 48183568
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 69f9ad10c5c06ab8a9d2bc95eddceb67b20e745c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765107"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="media-table-in-lync-server-2013"></a><span data-ttu-id="d3e0e-102">Таблица Media в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d3e0e-102">Media table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d3e0e-103">_**Тема последнего изменения:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="d3e0e-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="d3e0e-104">Каждая запись представляет один тип мультимедиа, используемый в одноранговых сеансах.</span><span class="sxs-lookup"><span data-stu-id="d3e0e-104">Each record represents one media type used in a peer-to-peer session.</span></span> <span data-ttu-id="d3e0e-105">Один сеанс будет представлен в таблице несколькими записями, если используется более одного типа мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="d3e0e-105">One session would be represented by multiple records in the table, if more than one media type is used.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d3e0e-106">Таблицу мультимедиа нельзя использовать для расчета длительности мультимедиа для сеанса.</span><span class="sxs-lookup"><span data-stu-id="d3e0e-106">The Media table should not be used to calculate the media duration for a session.</span></span> <span data-ttu-id="d3e0e-107">В этой таблице содержатся сведения о сигнализации обмена мультимедийными данными в сеансе.</span><span class="sxs-lookup"><span data-stu-id="d3e0e-107">This table contains the signaling details of media exchange in a session.</span></span> <span data-ttu-id="d3e0e-108">Обмен мультимедийными данными выполняется запросом приглашения, а StartTime указывает время отправки приглашения. Время приглашения не обязательно означает время запуска мультимедиа, так как Media запускается только после того, как сеанс принял сеанс.</span><span class="sxs-lookup"><span data-stu-id="d3e0e-108">Media exchange is done by the INVITE request, and StartTime indicates the time that the INVITE was sent out. The invite time does not necessarily mean the media start time, because media starts only after the sessionee accepts the session.</span></span> <span data-ttu-id="d3e0e-109">Значение EndTime обычно означает время окончания этого сеанса.</span><span class="sxs-lookup"><span data-stu-id="d3e0e-109">The EndTime usually means the end time of this session.</span></span>



</div>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d3e0e-110">Столбец</span><span class="sxs-lookup"><span data-stu-id="d3e0e-110">Column</span></span></th>
<th><span data-ttu-id="d3e0e-111">Тип данных</span><span class="sxs-lookup"><span data-stu-id="d3e0e-111">Data Type</span></span></th>
<th><span data-ttu-id="d3e0e-112">Ключ/индекс</span><span class="sxs-lookup"><span data-stu-id="d3e0e-112">Key/Index</span></span></th>
<th><span data-ttu-id="d3e0e-113">Сведения</span><span class="sxs-lookup"><span data-stu-id="d3e0e-113">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d3e0e-114"><strong>сессионидтиме</strong></span><span class="sxs-lookup"><span data-stu-id="d3e0e-114"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="d3e0e-115">datetime</span><span class="sxs-lookup"><span data-stu-id="d3e0e-115">datetime</span></span></p></td>
<td><p><span data-ttu-id="d3e0e-116">Основной, внешний</span><span class="sxs-lookup"><span data-stu-id="d3e0e-116">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="d3e0e-117">Время запроса сеанса.</span><span class="sxs-lookup"><span data-stu-id="d3e0e-117">Time of session request.</span></span> <span data-ttu-id="d3e0e-118">Используется в сочетании с <strong>сессионидсек</strong> для уникальной идентификации сеанса.</span><span class="sxs-lookup"><span data-stu-id="d3e0e-118">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="d3e0e-119">Дополнительные сведения приведены <a href="lync-server-2013-dialogs-table.md">в таблице диалоговые окна Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="d3e0e-119">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d3e0e-120"><strong>сессионидсек</strong></span><span class="sxs-lookup"><span data-stu-id="d3e0e-120"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="d3e0e-121">целое</span><span class="sxs-lookup"><span data-stu-id="d3e0e-121">int</span></span></p></td>
<td><p><span data-ttu-id="d3e0e-122">Основной, внешний</span><span class="sxs-lookup"><span data-stu-id="d3e0e-122">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="d3e0e-123">ИДЕНТИФИКАЦИОНный номер для идентификации сеанса.</span><span class="sxs-lookup"><span data-stu-id="d3e0e-123">ID number to identify the session.</span></span> <span data-ttu-id="d3e0e-124">Используется в сочетании с <strong>сессионидтиме</strong> для уникальной идентификации сеанса.</span><span class="sxs-lookup"><span data-stu-id="d3e0e-124">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="d3e0e-125">Дополнительные сведения приведены <a href="lync-server-2013-dialogs-table.md">в таблице диалоговые окна Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="d3e0e-125">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d3e0e-126"><strong>MediaId</strong></span><span class="sxs-lookup"><span data-stu-id="d3e0e-126"><strong>MediaId</strong></span></span></p></td>
<td><p><span data-ttu-id="d3e0e-127">tinyint</span><span class="sxs-lookup"><span data-stu-id="d3e0e-127">tinyint</span></span></p></td>
<td><p><span data-ttu-id="d3e0e-128">Основной, внешний</span><span class="sxs-lookup"><span data-stu-id="d3e0e-128">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="d3e0e-129">Уникальный номер, идентифицирующий этот тип мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="d3e0e-129">Unique number identifying this media type.</span></span> <span data-ttu-id="d3e0e-130">Для получения дополнительных сведений ознакомьтесь с <a href="lync-server-2013-medialist-table.md">таблицей медиалист в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="d3e0e-130">See the <a href="lync-server-2013-medialist-table.md">MediaList table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d3e0e-131"><strong>StartTime</strong></span><span class="sxs-lookup"><span data-stu-id="d3e0e-131"><strong>StartTime</strong></span></span></p></td>
<td><p><span data-ttu-id="d3e0e-132">datetime</span><span class="sxs-lookup"><span data-stu-id="d3e0e-132">datetime</span></span></p></td>
<td><p><span data-ttu-id="d3e0e-133">Primary</span><span class="sxs-lookup"><span data-stu-id="d3e0e-133">Primary</span></span></p></td>
<td><p><span data-ttu-id="d3e0e-134">Это время отправки запроса мультимедиа, а не фактического времени запуска мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="d3e0e-134">This is the time that a media request was sent out, not the real media start time.</span></span> <span data-ttu-id="d3e0e-135">Параметр <strong>StartTime</strong> включает время настройки сеанса.</span><span class="sxs-lookup"><span data-stu-id="d3e0e-135"><strong>StartTime</strong> includes the session setup time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d3e0e-136"><strong>EndTime</strong></span><span class="sxs-lookup"><span data-stu-id="d3e0e-136"><strong>EndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="d3e0e-137">datetime</span><span class="sxs-lookup"><span data-stu-id="d3e0e-137">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d3e0e-138">Это время окончания сеанса.</span><span class="sxs-lookup"><span data-stu-id="d3e0e-138">This is the end time of the session.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

