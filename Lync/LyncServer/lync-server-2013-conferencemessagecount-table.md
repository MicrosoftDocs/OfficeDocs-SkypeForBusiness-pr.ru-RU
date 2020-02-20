---
title: 'Lync Server 2013: таблица таблица conferencemessagecount'
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
ms.openlocfilehash: e862209d384cd3927b6f8136b1a0d04b378e00c2
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42145137"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="conferencemessagecount-table-in-lync-server-2013"></a><span data-ttu-id="56921-102">Таблица Таблица conferencemessagecount в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="56921-102">ConferenceMessageCount table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="56921-103">_**Последнее изменение темы:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="56921-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="56921-104">Каждая запись в этой таблице представляет одного пользователя в одной конференции для обмена мгновенными сообщениями и включает количество сообщений, отправленных этим пользователем.</span><span class="sxs-lookup"><span data-stu-id="56921-104">Each record in this table represents one user in one IM conference and includes the number of messages sent by that user.</span></span> <span data-ttu-id="56921-105">Каждая конференция представлена несколькими записями в этой таблице; по одной записи для каждого пользователя.</span><span class="sxs-lookup"><span data-stu-id="56921-105">Each conference is represented by multiple records in this table; one record for each user.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="56921-106">Столбец</span><span class="sxs-lookup"><span data-stu-id="56921-106">Column</span></span></th>
<th><span data-ttu-id="56921-107">Тип данных</span><span class="sxs-lookup"><span data-stu-id="56921-107">Data Type</span></span></th>
<th><span data-ttu-id="56921-108">Ключ или индекс</span><span class="sxs-lookup"><span data-stu-id="56921-108">Key/Index</span></span></th>
<th><span data-ttu-id="56921-109">Сведения</span><span class="sxs-lookup"><span data-stu-id="56921-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="56921-110"><strong>сессионидтиме</strong></span><span class="sxs-lookup"><span data-stu-id="56921-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="56921-111">datetime</span><span class="sxs-lookup"><span data-stu-id="56921-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="56921-112">Основной, внешний</span><span class="sxs-lookup"><span data-stu-id="56921-112">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="56921-113">Время экземпляра конференции.</span><span class="sxs-lookup"><span data-stu-id="56921-113">Time of conference instance.</span></span> <span data-ttu-id="56921-114">Используется совместно с <strong>сессионидсек</strong> для уникальной идентификации экземпляра Конференции.</span><span class="sxs-lookup"><span data-stu-id="56921-114">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a conference instance.</span></span> <span data-ttu-id="56921-115">Дополнительные сведения см. <a href="lync-server-2013-conferences-table.md">в таблице конференций в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="56921-115">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="56921-116"><strong>сессионидсек</strong></span><span class="sxs-lookup"><span data-stu-id="56921-116"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="56921-117">int</span><span class="sxs-lookup"><span data-stu-id="56921-117">int</span></span></p></td>
<td><p><span data-ttu-id="56921-118">Основной, Внешний</span><span class="sxs-lookup"><span data-stu-id="56921-118">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="56921-119">Идентификатор для определения экземпляра конференции.</span><span class="sxs-lookup"><span data-stu-id="56921-119">ID number to identify the conference instance.</span></span> <span data-ttu-id="56921-120">Используется совместно с <strong>сессионидтиме</strong> для уникальной идентификации экземпляра Конференции.</span><span class="sxs-lookup"><span data-stu-id="56921-120">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a conference instance.</span></span> <span data-ttu-id="56921-121">Дополнительные сведения см. <a href="lync-server-2013-conferences-table.md">в таблице конференций в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="56921-121">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="56921-122"><strong>UserId</strong></span><span class="sxs-lookup"><span data-stu-id="56921-122"><strong>UserId</strong></span></span></p></td>
<td><p><span data-ttu-id="56921-123">int</span><span class="sxs-lookup"><span data-stu-id="56921-123">int</span></span></p></td>
<td><p><span data-ttu-id="56921-124">Правительства</span><span class="sxs-lookup"><span data-stu-id="56921-124">Foreign</span></span></p></td>
<td><p><span data-ttu-id="56921-125">Уникальный номер, идентифицирующий этого пользователя, на который ссылается <a href="lync-server-2013-users-table.md">таблица Users в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="56921-125">Unique number identifying this user, referenced from the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="56921-126"><strong>MessageCount</strong></span><span class="sxs-lookup"><span data-stu-id="56921-126"><strong>MessageCount</strong></span></span></p></td>
<td><p><span data-ttu-id="56921-127">smallint</span><span class="sxs-lookup"><span data-stu-id="56921-127">smallint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="56921-128">Количество сообщений, отправленных этим пользователем во время данной Конференции.</span><span class="sxs-lookup"><span data-stu-id="56921-128">The number of messages sent by this user during this conference.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

