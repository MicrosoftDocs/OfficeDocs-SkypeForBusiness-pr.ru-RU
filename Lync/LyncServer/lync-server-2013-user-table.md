---
title: 'Lync Server 2013: пользовательская таблица'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: User table
ms:assetid: 6b52047e-286d-47ab-b7bc-a9b266f62d82
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398505(v=OCS.15)
ms:contentKeyID: 48184437
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d9ccf7fad4b7b84746c70384269c2a903b840b6f
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42140772"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="user-table-in-lync-server-2013"></a><span data-ttu-id="183db-102">Таблица user в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="183db-102">User table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="183db-103">_**Последнее изменение темы:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="183db-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="183db-p101">Таблица User является таблицей поддержки, в которой хранится список разных пользователей, участвовавших в сеансах, записанных в базе данных. Каждая запись в таблице представляет одного пользователя.</span><span class="sxs-lookup"><span data-stu-id="183db-p101">The User table is a supporting table that stores a list of the various users who have participated in sessions recorded in the database. Each record in the table represents one user.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="183db-106"><strong>Column</strong></span><span class="sxs-lookup"><span data-stu-id="183db-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="183db-107"><strong>Тип данных</strong></span><span class="sxs-lookup"><span data-stu-id="183db-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="183db-108"><strong>Ключ или индекс</strong></span><span class="sxs-lookup"><span data-stu-id="183db-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="183db-109"><strong>Details</strong></span><span class="sxs-lookup"><span data-stu-id="183db-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="183db-110"><strong>UserKey</strong></span><span class="sxs-lookup"><span data-stu-id="183db-110"><strong>UserKey</strong></span></span></p></td>
<td><p><span data-ttu-id="183db-111">int</span><span class="sxs-lookup"><span data-stu-id="183db-111">int</span></span></p></td>
<td><p><span data-ttu-id="183db-112">Primary</span><span class="sxs-lookup"><span data-stu-id="183db-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="183db-113">Уникальный номер, идентифицирующий этого пользователя.</span><span class="sxs-lookup"><span data-stu-id="183db-113">Unique number identifying this user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="183db-114"><strong>URI</strong></span><span class="sxs-lookup"><span data-stu-id="183db-114"><strong>URI</strong></span></span></p></td>
<td><p><span data-ttu-id="183db-115">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="183db-115">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="183db-116">Уникальные</span><span class="sxs-lookup"><span data-stu-id="183db-116">Unique</span></span></p></td>
<td><p><span data-ttu-id="183db-117">Строка URI.</span><span class="sxs-lookup"><span data-stu-id="183db-117">URI string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="183db-118"><strong>уритипе</strong></span><span class="sxs-lookup"><span data-stu-id="183db-118"><strong>URIType</strong></span></span></p></td>
<td><p><span data-ttu-id="183db-119">int</span><span class="sxs-lookup"><span data-stu-id="183db-119">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="183db-120">1 — неизвестный тип URI.</span><span class="sxs-lookup"><span data-stu-id="183db-120">1 is unknown URI type.</span></span></p>
<p><span data-ttu-id="183db-121">2 — URI пользователя.</span><span class="sxs-lookup"><span data-stu-id="183db-121">2 is user URI.</span></span></p>
<p><span data-ttu-id="183db-122">4 — URI конференции.</span><span class="sxs-lookup"><span data-stu-id="183db-122">4 is conference URI.</span></span></p>
<p><span data-ttu-id="183db-123">8 — URI телефона.</span><span class="sxs-lookup"><span data-stu-id="183db-123">8 is phone URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="183db-124"><strong>тенанткэй</strong></span><span class="sxs-lookup"><span data-stu-id="183db-124"><strong>TenantKey</strong></span></span></p></td>
<td><p><span data-ttu-id="183db-125">int</span><span class="sxs-lookup"><span data-stu-id="183db-125">int</span></span></p></td>
<td><p><span data-ttu-id="183db-126">Правительства</span><span class="sxs-lookup"><span data-stu-id="183db-126">Foreign</span></span></p></td>
<td><p><span data-ttu-id="183db-127">Клиент пользователя, ссылается на таблицу клиентов.</span><span class="sxs-lookup"><span data-stu-id="183db-127">Tenant of the user, referenced from tenant table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="183db-128"><strong>ластпуркаллтиме</strong></span><span class="sxs-lookup"><span data-stu-id="183db-128"><strong>LastPoorCallTime</strong></span></span></p></td>
<td><p><span data-ttu-id="183db-129">datetime</span><span class="sxs-lookup"><span data-stu-id="183db-129">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="183db-130">Последняя метка времени, когда пользователь имел аудиовызов плохого качества.</span><span class="sxs-lookup"><span data-stu-id="183db-130">Latest time stamp when the user had a poor audio call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="183db-131"><strong>некступдатетс</strong></span><span class="sxs-lookup"><span data-stu-id="183db-131"><strong>NextUpdateTS</strong></span></span></p></td>
<td><p><span data-ttu-id="183db-132">datetime</span><span class="sxs-lookup"><span data-stu-id="183db-132">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="183db-133">Только для внутреннего использования.</span><span class="sxs-lookup"><span data-stu-id="183db-133">For internal use only.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

