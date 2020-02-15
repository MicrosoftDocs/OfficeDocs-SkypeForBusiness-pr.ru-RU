---
title: 'Lync Server 2013: ТблкомплианцепартиЦипант'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblComplianceParticipant
ms:assetid: 5d7e0dea-74f7-46d1-badf-b94abc8f066d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558655(v=OCS.15)
ms:contentKeyID: 48184262
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a4d5a0024c273dbef8fee16f1fb4b3372692ab4f
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049241"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblcomplianceparticipant-in-lync-server-2013"></a><span data-ttu-id="b490d-102">ТблкомплианцепартиЦипант в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b490d-102">tblComplianceParticipant in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b490d-103">_**Последнее изменение темы:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="b490d-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="b490d-104">Таблица ComplianceParticipant содержит текущих участников по каналам или по серверам.</span><span class="sxs-lookup"><span data-stu-id="b490d-104">tblComplianceParticipant contains the current participants per channel and per server.</span></span>

### <a name="columns"></a><span data-ttu-id="b490d-105">Columns</span><span class="sxs-lookup"><span data-stu-id="b490d-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b490d-106">Столбец</span><span class="sxs-lookup"><span data-stu-id="b490d-106">Column</span></span></th>
<th><span data-ttu-id="b490d-107">Тип</span><span class="sxs-lookup"><span data-stu-id="b490d-107">Type</span></span></th>
<th><span data-ttu-id="b490d-108">Описание</span><span class="sxs-lookup"><span data-stu-id="b490d-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b490d-109">чаннелури</span><span class="sxs-lookup"><span data-stu-id="b490d-109">channelUri</span></span></p></td>
<td><p><span data-ttu-id="b490d-110">nvarchar (255), not null</span><span class="sxs-lookup"><span data-stu-id="b490d-110">nvarchar (255), not null</span></span></p></td>
<td><p><span data-ttu-id="b490d-111">Универсальный код ресурса (URI) для канала.</span><span class="sxs-lookup"><span data-stu-id="b490d-111">Channel Uniform Resource Identifier (URI).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b490d-112">userId</span><span class="sxs-lookup"><span data-stu-id="b490d-112">userId</span></span></p></td>
<td><p><span data-ttu-id="b490d-113">int, not null</span><span class="sxs-lookup"><span data-stu-id="b490d-113">int, not null</span></span></p></td>
<td><p><span data-ttu-id="b490d-114">Идентификатор участника (в соответствии с таблицей tblPrincipal.prinID).</span><span class="sxs-lookup"><span data-stu-id="b490d-114">Principal ID of the participant (corresponding to tblPrincipal.prinID table).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b490d-115">жоинедат</span><span class="sxs-lookup"><span data-stu-id="b490d-115">joinedAt</span></span></p></td>
<td><p><span data-ttu-id="b490d-116">bigint, not null</span><span class="sxs-lookup"><span data-stu-id="b490d-116">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="b490d-117">Метка времени события присоединения.</span><span class="sxs-lookup"><span data-stu-id="b490d-117">Time stamp of the joining event.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b490d-118">партедат</span><span class="sxs-lookup"><span data-stu-id="b490d-118">partedAt</span></span></p></td>
<td><p><span data-ttu-id="b490d-119">типу</span><span class="sxs-lookup"><span data-stu-id="b490d-119">bigint</span></span></p></td>
<td><p><span data-ttu-id="b490d-p101">Null, если участник еще присоединен.Если не null, то метка времени события выхода из канала.</span><span class="sxs-lookup"><span data-stu-id="b490d-p101">Null if participant is still joined. The time stamp of the channel leaving event if not null.</span></span></p>
<p><span data-ttu-id="b490d-122">Эти записи в конечном итоге удаляются, когда все переводчики обработают событие.</span><span class="sxs-lookup"><span data-stu-id="b490d-122">These entries are eventually removed when all translators process the event.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b490d-123">userUri</span><span class="sxs-lookup"><span data-stu-id="b490d-123">userUri</span></span></p></td>
<td><p><span data-ttu-id="b490d-124">nvarchar(255), not null</span><span class="sxs-lookup"><span data-stu-id="b490d-124">nvarchar(255), not null</span></span></p></td>
<td><p><span data-ttu-id="b490d-125">URI пользователя.</span><span class="sxs-lookup"><span data-stu-id="b490d-125">User URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b490d-126">serverID</span><span class="sxs-lookup"><span data-stu-id="b490d-126">serverID</span></span></p></td>
<td><p><span data-ttu-id="b490d-127">int</span><span class="sxs-lookup"><span data-stu-id="b490d-127">int</span></span></p></td>
<td><p><span data-ttu-id="b490d-128">Удостоверение сервера (в соответствии с таблицей tblServerIdentity.serverID).</span><span class="sxs-lookup"><span data-stu-id="b490d-128">Server identity (as in tblServerIdentity.serverID table).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b490d-129">sessionId</span><span class="sxs-lookup"><span data-stu-id="b490d-129">sessionId</span></span></p></td>
<td><p><span data-ttu-id="b490d-130">типу</span><span class="sxs-lookup"><span data-stu-id="b490d-130">bigint</span></span></p></td>
<td><p><span data-ttu-id="b490d-p102">Сеанс сервера. Это произвольный номер, который создается каждый раз при запуске службы чата. Он используется, чтобы различать сеансы в целях идентификации потерянных участников.</span><span class="sxs-lookup"><span data-stu-id="b490d-p102">Server session. This is a random number generated each time a Chat service starts. It is used to differentiate sessions for the purpose of identifying orphaned participants.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="b490d-134">Key</span><span class="sxs-lookup"><span data-stu-id="b490d-134">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b490d-135">Столбец</span><span class="sxs-lookup"><span data-stu-id="b490d-135">Column</span></span></th>
<th><span data-ttu-id="b490d-136">Описание</span><span class="sxs-lookup"><span data-stu-id="b490d-136">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b490d-137">&lt;Чаннелури, userId, Жоинедат&gt;</span><span class="sxs-lookup"><span data-stu-id="b490d-137">&lt;channelUri, userId, joinedAt&gt;</span></span></p></td>
<td><p><span data-ttu-id="b490d-138">Первичный ключ.</span><span class="sxs-lookup"><span data-stu-id="b490d-138">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

