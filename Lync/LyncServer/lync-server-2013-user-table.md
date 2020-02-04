---
title: 'Lync Server 2013: таблица User'
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
ms.openlocfilehash: 8256dec91c93ca6e8f0fd3cfff65280a417324e4
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41744449"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="user-table-in-lync-server-2013"></a><span data-ttu-id="62f74-102">Таблица User в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="62f74-102">User table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="62f74-103">_**Тема последнего изменения:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="62f74-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="62f74-104">Таблица user — это вспомогательная таблица, в которой хранится список различных пользователей, которые участвовали в сеансах, записанных в базе данных.</span><span class="sxs-lookup"><span data-stu-id="62f74-104">The User table is a supporting table that stores a list of the various users who have participated in sessions recorded in the database.</span></span> <span data-ttu-id="62f74-105">Каждая запись в таблице представляет одного пользователя.</span><span class="sxs-lookup"><span data-stu-id="62f74-105">Each record in the table represents one user.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="62f74-106"><strong>Столбец</strong></span><span class="sxs-lookup"><span data-stu-id="62f74-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="62f74-107"><strong>Тип данных</strong></span><span class="sxs-lookup"><span data-stu-id="62f74-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="62f74-108"><strong>Ключ/индекс</strong></span><span class="sxs-lookup"><span data-stu-id="62f74-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="62f74-109"><strong>Сведения</strong></span><span class="sxs-lookup"><span data-stu-id="62f74-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="62f74-110"><strong>усеркэй</strong></span><span class="sxs-lookup"><span data-stu-id="62f74-110"><strong>UserKey</strong></span></span></p></td>
<td><p><span data-ttu-id="62f74-111">целое</span><span class="sxs-lookup"><span data-stu-id="62f74-111">int</span></span></p></td>
<td><p><span data-ttu-id="62f74-112">Primary</span><span class="sxs-lookup"><span data-stu-id="62f74-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="62f74-113">Уникальный номер, идентифицирующий этого пользователя.</span><span class="sxs-lookup"><span data-stu-id="62f74-113">Unique number identifying this user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="62f74-114"><strong>КОД</strong></span><span class="sxs-lookup"><span data-stu-id="62f74-114"><strong>URI</strong></span></span></p></td>
<td><p><span data-ttu-id="62f74-115">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="62f74-115">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="62f74-116">Повторя</span><span class="sxs-lookup"><span data-stu-id="62f74-116">Unique</span></span></p></td>
<td><p><span data-ttu-id="62f74-117">Строка URI.</span><span class="sxs-lookup"><span data-stu-id="62f74-117">URI string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="62f74-118"><strong>уритипе</strong></span><span class="sxs-lookup"><span data-stu-id="62f74-118"><strong>URIType</strong></span></span></p></td>
<td><p><span data-ttu-id="62f74-119">целое</span><span class="sxs-lookup"><span data-stu-id="62f74-119">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="62f74-120">1 — неизвестный тип URI.</span><span class="sxs-lookup"><span data-stu-id="62f74-120">1 is unknown URI type.</span></span></p>
<p><span data-ttu-id="62f74-121">2 — это универсальный код ресурса пользователя.</span><span class="sxs-lookup"><span data-stu-id="62f74-121">2 is user URI.</span></span></p>
<p><span data-ttu-id="62f74-122">4 — универсальный код ресурса Конференции.</span><span class="sxs-lookup"><span data-stu-id="62f74-122">4 is conference URI.</span></span></p>
<p><span data-ttu-id="62f74-123">8 — это универсальный код ресурса (URI) телефона.</span><span class="sxs-lookup"><span data-stu-id="62f74-123">8 is phone URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="62f74-124"><strong>тенанткэй</strong></span><span class="sxs-lookup"><span data-stu-id="62f74-124"><strong>TenantKey</strong></span></span></p></td>
<td><p><span data-ttu-id="62f74-125">целое</span><span class="sxs-lookup"><span data-stu-id="62f74-125">int</span></span></p></td>
<td><p><span data-ttu-id="62f74-126">Другом</span><span class="sxs-lookup"><span data-stu-id="62f74-126">Foreign</span></span></p></td>
<td><p><span data-ttu-id="62f74-127">Клиент для пользователя, на который ссылается таблица "клиент".</span><span class="sxs-lookup"><span data-stu-id="62f74-127">Tenant of the user, referenced from tenant table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="62f74-128"><strong>ластпуркаллтиме</strong></span><span class="sxs-lookup"><span data-stu-id="62f74-128"><strong>LastPoorCallTime</strong></span></span></p></td>
<td><p><span data-ttu-id="62f74-129">datetime</span><span class="sxs-lookup"><span data-stu-id="62f74-129">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="62f74-130">Самая поздняя метка времени, когда пользователь приходил к вызову неудовлетворительного звука.</span><span class="sxs-lookup"><span data-stu-id="62f74-130">Latest time stamp when the user had a poor audio call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="62f74-131"><strong>некступдатетс</strong></span><span class="sxs-lookup"><span data-stu-id="62f74-131"><strong>NextUpdateTS</strong></span></span></p></td>
<td><p><span data-ttu-id="62f74-132">datetime</span><span class="sxs-lookup"><span data-stu-id="62f74-132">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="62f74-133">Только для внутреннего использования.</span><span class="sxs-lookup"><span data-stu-id="62f74-133">For internal use only.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

