---
title: 'Lync Server 2013: tblComplianceParticipant'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: tblComplianceParticipant
ms:assetid: 5d7e0dea-74f7-46d1-badf-b94abc8f066d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558655(v=OCS.15)
ms:contentKeyID: 48184262
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e98b257552f728d0976df6331673f1f55d0dbdeb
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849541"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblcomplianceparticipant-in-lync-server-2013"></a><span data-ttu-id="dbd12-102">tblComplianceParticipant в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dbd12-102">tblComplianceParticipant in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dbd12-103">_**Тема последнего изменения:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="dbd12-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="dbd12-104">ТблкомплианцепартиЦипант включает текущих участников на канал и на сервер.</span><span class="sxs-lookup"><span data-stu-id="dbd12-104">tblComplianceParticipant contains the current participants per channel and per server.</span></span>

### <a name="columns"></a><span data-ttu-id="dbd12-105">Столбцов</span><span class="sxs-lookup"><span data-stu-id="dbd12-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="dbd12-106">Столбец</span><span class="sxs-lookup"><span data-stu-id="dbd12-106">Column</span></span></th>
<th><span data-ttu-id="dbd12-107">Тип</span><span class="sxs-lookup"><span data-stu-id="dbd12-107">Type</span></span></th>
<th><span data-ttu-id="dbd12-108">Описание</span><span class="sxs-lookup"><span data-stu-id="dbd12-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="dbd12-109">Чаннелури</span><span class="sxs-lookup"><span data-stu-id="dbd12-109">channelUri</span></span></p></td>
<td><p><span data-ttu-id="dbd12-110">nvarchar (255), NOT NULL</span><span class="sxs-lookup"><span data-stu-id="dbd12-110">nvarchar (255), not null</span></span></p></td>
<td><p><span data-ttu-id="dbd12-111">Универсальный код ресурса (URI) канала.</span><span class="sxs-lookup"><span data-stu-id="dbd12-111">Channel Uniform Resource Identifier (URI).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dbd12-112">Идентификатора пользователя</span><span class="sxs-lookup"><span data-stu-id="dbd12-112">userId</span></span></p></td>
<td><p><span data-ttu-id="dbd12-113">int, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="dbd12-113">int, not null</span></span></p></td>
<td><p><span data-ttu-id="dbd12-114">Идентификатор участника (соответствующий таблице ТблпринЦипал. Принид).</span><span class="sxs-lookup"><span data-stu-id="dbd12-114">Principal ID of the participant (corresponding to tblPrincipal.prinID table).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dbd12-115">Жоинедат</span><span class="sxs-lookup"><span data-stu-id="dbd12-115">joinedAt</span></span></p></td>
<td><p><span data-ttu-id="dbd12-116">bigint, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="dbd12-116">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="dbd12-117">Метка времени присоединения к событию.</span><span class="sxs-lookup"><span data-stu-id="dbd12-117">Time stamp of the joining event.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dbd12-118">Партедат</span><span class="sxs-lookup"><span data-stu-id="dbd12-118">partedAt</span></span></p></td>
<td><p><span data-ttu-id="dbd12-119">bigint</span><span class="sxs-lookup"><span data-stu-id="dbd12-119">bigint</span></span></p></td>
<td><p><span data-ttu-id="dbd12-120">NULL, если участник все еще присоединен.</span><span class="sxs-lookup"><span data-stu-id="dbd12-120">Null if participant is still joined.</span></span> <span data-ttu-id="dbd12-121">Метка времени события выхода канала, если значение не равно null.</span><span class="sxs-lookup"><span data-stu-id="dbd12-121">The time stamp of the channel leaving event if not null.</span></span></p>
<p><span data-ttu-id="dbd12-122">Эти записи в конечном итоге удаляются, когда все переводчики обрабатывают событие.</span><span class="sxs-lookup"><span data-stu-id="dbd12-122">These entries are eventually removed when all translators process the event.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dbd12-123">Усерури</span><span class="sxs-lookup"><span data-stu-id="dbd12-123">userUri</span></span></p></td>
<td><p><span data-ttu-id="dbd12-124">nvarchar (255), NOT NULL</span><span class="sxs-lookup"><span data-stu-id="dbd12-124">nvarchar(255), not null</span></span></p></td>
<td><p><span data-ttu-id="dbd12-125">URI пользователя.</span><span class="sxs-lookup"><span data-stu-id="dbd12-125">User URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dbd12-126">Серверид</span><span class="sxs-lookup"><span data-stu-id="dbd12-126">serverID</span></span></p></td>
<td><p><span data-ttu-id="dbd12-127">целое</span><span class="sxs-lookup"><span data-stu-id="dbd12-127">int</span></span></p></td>
<td><p><span data-ttu-id="dbd12-128">Идентификация сервера (как в таблице Тблсерверидентити. Серверид).</span><span class="sxs-lookup"><span data-stu-id="dbd12-128">Server identity (as in tblServerIdentity.serverID table).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dbd12-129">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="dbd12-129">sessionId</span></span></p></td>
<td><p><span data-ttu-id="dbd12-130">bigint</span><span class="sxs-lookup"><span data-stu-id="dbd12-130">bigint</span></span></p></td>
<td><p><span data-ttu-id="dbd12-131">Сеанс сервера.</span><span class="sxs-lookup"><span data-stu-id="dbd12-131">Server session.</span></span> <span data-ttu-id="dbd12-132">Это случайное число, которое генерируется каждый раз, когда запускается служба чата.</span><span class="sxs-lookup"><span data-stu-id="dbd12-132">This is a random number generated each time a Chat service starts.</span></span> <span data-ttu-id="dbd12-133">Она используется для различения сеансов в целях идентификации потерянных участников.</span><span class="sxs-lookup"><span data-stu-id="dbd12-133">It is used to differentiate sessions for the purpose of identifying orphaned participants.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="dbd12-134">Ключ</span><span class="sxs-lookup"><span data-stu-id="dbd12-134">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="dbd12-135">Столбец</span><span class="sxs-lookup"><span data-stu-id="dbd12-135">Column</span></span></th>
<th><span data-ttu-id="dbd12-136">Описание</span><span class="sxs-lookup"><span data-stu-id="dbd12-136">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="dbd12-137">&lt;Чаннелури, userId, Жоинедат&gt;</span><span class="sxs-lookup"><span data-stu-id="dbd12-137">&lt;channelUri, userId, joinedAt&gt;</span></span></p></td>
<td><p><span data-ttu-id="dbd12-138">Первичный ключ.</span><span class="sxs-lookup"><span data-stu-id="dbd12-138">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

