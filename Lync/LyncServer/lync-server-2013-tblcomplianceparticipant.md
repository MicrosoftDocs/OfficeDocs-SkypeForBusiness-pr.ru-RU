---
title: 'Lync Server 2013: ТблкомплианцепартиЦипант'
description: 'Lync Server 2013: ТблкомплианцепартиЦипант.'
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
ms.openlocfilehash: c1385b0a635f003a72de93f10f72642314ad7ebd
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48569075"
---
# <a name="tblcomplianceparticipant-in-lync-server-2013"></a><span data-ttu-id="165e4-103">ТблкомплианцепартиЦипант в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="165e4-103">tblComplianceParticipant in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="165e4-104">_**Последнее изменение темы:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="165e4-104">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="165e4-105">Таблица ComplianceParticipant содержит текущих участников по каналам или по серверам.</span><span class="sxs-lookup"><span data-stu-id="165e4-105">tblComplianceParticipant contains the current participants per channel and per server.</span></span>

### <a name="columns"></a><span data-ttu-id="165e4-106">Столбцы</span><span class="sxs-lookup"><span data-stu-id="165e4-106">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="165e4-107">Столбец</span><span class="sxs-lookup"><span data-stu-id="165e4-107">Column</span></span></th>
<th><span data-ttu-id="165e4-108">Тип</span><span class="sxs-lookup"><span data-stu-id="165e4-108">Type</span></span></th>
<th><span data-ttu-id="165e4-109">Описание</span><span class="sxs-lookup"><span data-stu-id="165e4-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="165e4-110">чаннелури</span><span class="sxs-lookup"><span data-stu-id="165e4-110">channelUri</span></span></p></td>
<td><p><span data-ttu-id="165e4-111">nvarchar (255), not null</span><span class="sxs-lookup"><span data-stu-id="165e4-111">nvarchar (255), not null</span></span></p></td>
<td><p><span data-ttu-id="165e4-112">Универсальный код ресурса (URI) для канала.</span><span class="sxs-lookup"><span data-stu-id="165e4-112">Channel Uniform Resource Identifier (URI).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="165e4-113">userId</span><span class="sxs-lookup"><span data-stu-id="165e4-113">userId</span></span></p></td>
<td><p><span data-ttu-id="165e4-114">int, not null</span><span class="sxs-lookup"><span data-stu-id="165e4-114">int, not null</span></span></p></td>
<td><p><span data-ttu-id="165e4-115">Идентификатор участника (в соответствии с таблицей tblPrincipal.prinID).</span><span class="sxs-lookup"><span data-stu-id="165e4-115">Principal ID of the participant (corresponding to tblPrincipal.prinID table).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="165e4-116">жоинедат</span><span class="sxs-lookup"><span data-stu-id="165e4-116">joinedAt</span></span></p></td>
<td><p><span data-ttu-id="165e4-117">bigint, not null</span><span class="sxs-lookup"><span data-stu-id="165e4-117">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="165e4-118">Метка времени события присоединения.</span><span class="sxs-lookup"><span data-stu-id="165e4-118">Time stamp of the joining event.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="165e4-119">партедат</span><span class="sxs-lookup"><span data-stu-id="165e4-119">partedAt</span></span></p></td>
<td><p><span data-ttu-id="165e4-120">типу</span><span class="sxs-lookup"><span data-stu-id="165e4-120">bigint</span></span></p></td>
<td><p><span data-ttu-id="165e4-p101">Null, если участник еще присоединен.Если не null, то метка времени события выхода из канала.</span><span class="sxs-lookup"><span data-stu-id="165e4-p101">Null if participant is still joined. The time stamp of the channel leaving event if not null.</span></span></p>
<p><span data-ttu-id="165e4-123">Эти записи в конечном итоге удаляются, когда все переводчики обработают событие.</span><span class="sxs-lookup"><span data-stu-id="165e4-123">These entries are eventually removed when all translators process the event.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="165e4-124">userUri</span><span class="sxs-lookup"><span data-stu-id="165e4-124">userUri</span></span></p></td>
<td><p><span data-ttu-id="165e4-125">nvarchar(255), not null</span><span class="sxs-lookup"><span data-stu-id="165e4-125">nvarchar(255), not null</span></span></p></td>
<td><p><span data-ttu-id="165e4-126">URI пользователя.</span><span class="sxs-lookup"><span data-stu-id="165e4-126">User URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="165e4-127">serverID</span><span class="sxs-lookup"><span data-stu-id="165e4-127">serverID</span></span></p></td>
<td><p><span data-ttu-id="165e4-128">int</span><span class="sxs-lookup"><span data-stu-id="165e4-128">int</span></span></p></td>
<td><p><span data-ttu-id="165e4-129">Удостоверение сервера (в соответствии с таблицей tblServerIdentity.serverID).</span><span class="sxs-lookup"><span data-stu-id="165e4-129">Server identity (as in tblServerIdentity.serverID table).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="165e4-130">sessionId</span><span class="sxs-lookup"><span data-stu-id="165e4-130">sessionId</span></span></p></td>
<td><p><span data-ttu-id="165e4-131">типу</span><span class="sxs-lookup"><span data-stu-id="165e4-131">bigint</span></span></p></td>
<td><p><span data-ttu-id="165e4-p102">Сеанс сервера. Это произвольный номер, который создается каждый раз при запуске службы чата. Он используется, чтобы различать сеансы в целях идентификации потерянных участников.</span><span class="sxs-lookup"><span data-stu-id="165e4-p102">Server session. This is a random number generated each time a Chat service starts. It is used to differentiate sessions for the purpose of identifying orphaned participants.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="165e4-135">Key</span><span class="sxs-lookup"><span data-stu-id="165e4-135">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="165e4-136">Столбец</span><span class="sxs-lookup"><span data-stu-id="165e4-136">Column</span></span></th>
<th><span data-ttu-id="165e4-137">Описание</span><span class="sxs-lookup"><span data-stu-id="165e4-137">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="165e4-138">&lt;Чаннелури, userId, Жоинедат&gt;</span><span class="sxs-lookup"><span data-stu-id="165e4-138">&lt;channelUri, userId, joinedAt&gt;</span></span></p></td>
<td><p><span data-ttu-id="165e4-139">Первичный ключ.</span><span class="sxs-lookup"><span data-stu-id="165e4-139">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

