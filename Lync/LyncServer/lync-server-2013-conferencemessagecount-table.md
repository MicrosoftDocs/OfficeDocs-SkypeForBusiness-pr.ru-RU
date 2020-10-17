---
title: 'Lync Server 2013: таблица таблица conferencemessagecount'
description: 'Lync Server 2013: таблица таблица conferencemessagecount.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: ConferenceMessageCount table
ms:assetid: 78569dbf-5217-42fa-ba1a-4380f56e2a3d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398590(v=OCS.15)
ms:contentKeyID: 48184570
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 271b654c09ab1aef194eb613e660de208aea1534
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48561625"
---
# <a name="conferencemessagecount-table-in-lync-server-2013"></a><span data-ttu-id="e03b5-103">Таблица Таблица conferencemessagecount в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e03b5-103">ConferenceMessageCount table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e03b5-104">_**Последнее изменение темы:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="e03b5-104">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="e03b5-105">Каждая запись в этой таблице представляет одного пользователя в одной конференции для обмена мгновенными сообщениями и включает количество сообщений, отправленных этим пользователем.</span><span class="sxs-lookup"><span data-stu-id="e03b5-105">Each record in this table represents one user in one IM conference and includes the number of messages sent by that user.</span></span> <span data-ttu-id="e03b5-106">Каждая конференция представлена несколькими записями в этой таблице; по одной записи для каждого пользователя.</span><span class="sxs-lookup"><span data-stu-id="e03b5-106">Each conference is represented by multiple records in this table; one record for each user.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e03b5-107">Столбец</span><span class="sxs-lookup"><span data-stu-id="e03b5-107">Column</span></span></th>
<th><span data-ttu-id="e03b5-108">Тип данных</span><span class="sxs-lookup"><span data-stu-id="e03b5-108">Data Type</span></span></th>
<th><span data-ttu-id="e03b5-109">Ключ или индекс</span><span class="sxs-lookup"><span data-stu-id="e03b5-109">Key/Index</span></span></th>
<th><span data-ttu-id="e03b5-110">Сведения</span><span class="sxs-lookup"><span data-stu-id="e03b5-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e03b5-111"><strong>сессионидтиме</strong></span><span class="sxs-lookup"><span data-stu-id="e03b5-111"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="e03b5-112">datetime</span><span class="sxs-lookup"><span data-stu-id="e03b5-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="e03b5-113">Основной, внешний</span><span class="sxs-lookup"><span data-stu-id="e03b5-113">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="e03b5-114">Время экземпляра конференции.</span><span class="sxs-lookup"><span data-stu-id="e03b5-114">Time of conference instance.</span></span> <span data-ttu-id="e03b5-115">Используется совместно с <strong>сессионидсек</strong> для уникальной идентификации экземпляра Конференции.</span><span class="sxs-lookup"><span data-stu-id="e03b5-115">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a conference instance.</span></span> <span data-ttu-id="e03b5-116">Дополнительные сведения см. <a href="lync-server-2013-conferences-table.md">в таблице конференций в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="e03b5-116">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e03b5-117"><strong>сессионидсек</strong></span><span class="sxs-lookup"><span data-stu-id="e03b5-117"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="e03b5-118">int</span><span class="sxs-lookup"><span data-stu-id="e03b5-118">int</span></span></p></td>
<td><p><span data-ttu-id="e03b5-119">Основной, Внешний</span><span class="sxs-lookup"><span data-stu-id="e03b5-119">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="e03b5-120">Идентификатор для определения экземпляра конференции.</span><span class="sxs-lookup"><span data-stu-id="e03b5-120">ID number to identify the conference instance.</span></span> <span data-ttu-id="e03b5-121">Используется совместно с <strong>сессионидтиме</strong> для уникальной идентификации экземпляра Конференции.</span><span class="sxs-lookup"><span data-stu-id="e03b5-121">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a conference instance.</span></span> <span data-ttu-id="e03b5-122">Дополнительные сведения см. <a href="lync-server-2013-conferences-table.md">в таблице конференций в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="e03b5-122">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e03b5-123"><strong>UserId</strong></span><span class="sxs-lookup"><span data-stu-id="e03b5-123"><strong>UserId</strong></span></span></p></td>
<td><p><span data-ttu-id="e03b5-124">int</span><span class="sxs-lookup"><span data-stu-id="e03b5-124">int</span></span></p></td>
<td><p><span data-ttu-id="e03b5-125">Правительства</span><span class="sxs-lookup"><span data-stu-id="e03b5-125">Foreign</span></span></p></td>
<td><p><span data-ttu-id="e03b5-126">Уникальный номер, идентифицирующий этого пользователя, на который ссылается <a href="lync-server-2013-users-table.md">таблица Users в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="e03b5-126">Unique number identifying this user, referenced from the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e03b5-127"><strong>MessageCount</strong></span><span class="sxs-lookup"><span data-stu-id="e03b5-127"><strong>MessageCount</strong></span></span></p></td>
<td><p><span data-ttu-id="e03b5-128">smallint</span><span class="sxs-lookup"><span data-stu-id="e03b5-128">smallint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="e03b5-129">Количество сообщений, отправленных этим пользователем во время данной Конференции.</span><span class="sxs-lookup"><span data-stu-id="e03b5-129">The number of messages sent by this user during this conference.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

