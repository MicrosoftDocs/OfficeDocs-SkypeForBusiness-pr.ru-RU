---
title: 'Lync Server 2013: таблица Users'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Users table
ms:assetid: a8d71373-4b57-4245-9f02-f7fc0d9fcd3c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412791(v=OCS.15)
ms:contentKeyID: 48185032
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c2be643f8a593af01ee47ad93d3910d44ee86e48
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41744329"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="users-table-in-lync-server-2013"></a><span data-ttu-id="04bc5-102">Таблица Users в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="04bc5-102">Users table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="04bc5-103">_**Тема последнего изменения:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="04bc5-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="04bc5-104">Таблица Users является вспомогательной таблицей.</span><span class="sxs-lookup"><span data-stu-id="04bc5-104">The Users table is a supporting table.</span></span> <span data-ttu-id="04bc5-105">В каждой записи в таблице хранятся сведения о пользователях, участвующих в звонках или сеансах с записями в базе данных.</span><span class="sxs-lookup"><span data-stu-id="04bc5-105">Each record in the table stores information about one user involved in calls or sessions that have records in the database.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="04bc5-106">Столбец</span><span class="sxs-lookup"><span data-stu-id="04bc5-106">Column</span></span></th>
<th><span data-ttu-id="04bc5-107">Тип данных</span><span class="sxs-lookup"><span data-stu-id="04bc5-107">Data Type</span></span></th>
<th><span data-ttu-id="04bc5-108">Ключ/индекс</span><span class="sxs-lookup"><span data-stu-id="04bc5-108">Key/Index</span></span></th>
<th><span data-ttu-id="04bc5-109">Сведения</span><span class="sxs-lookup"><span data-stu-id="04bc5-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="04bc5-110"><strong>некступдатетс</strong></span><span class="sxs-lookup"><span data-stu-id="04bc5-110"><strong>NextUpdateTS</strong></span></span></p></td>
<td><p><span data-ttu-id="04bc5-111">datetime</span><span class="sxs-lookup"><span data-stu-id="04bc5-111">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="04bc5-112">Метка времени для внутреннего использования.</span><span class="sxs-lookup"><span data-stu-id="04bc5-112">Time stamp for internal use.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="04bc5-113"><strong>Идентификатора пользователя</strong></span><span class="sxs-lookup"><span data-stu-id="04bc5-113"><strong>UserId</strong></span></span></p></td>
<td><p><span data-ttu-id="04bc5-114">целое</span><span class="sxs-lookup"><span data-stu-id="04bc5-114">int</span></span></p></td>
<td><p><span data-ttu-id="04bc5-115">Primary</span><span class="sxs-lookup"><span data-stu-id="04bc5-115">Primary</span></span></p></td>
<td><p><span data-ttu-id="04bc5-116">Уникальный номер, идентифицирующий этого пользователя.</span><span class="sxs-lookup"><span data-stu-id="04bc5-116">Unique number identifying this user.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="04bc5-117"><strong>усерури</strong></span><span class="sxs-lookup"><span data-stu-id="04bc5-117"><strong>UserUri</strong></span></span></p></td>
<td><p><span data-ttu-id="04bc5-118">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="04bc5-118">nvarchar(450)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="04bc5-119">URI пользователя.</span><span class="sxs-lookup"><span data-stu-id="04bc5-119">User URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="04bc5-120"><strong>TenantId</strong></span><span class="sxs-lookup"><span data-stu-id="04bc5-120"><strong>TenantId</strong></span></span></p></td>
<td><p><span data-ttu-id="04bc5-121">целое</span><span class="sxs-lookup"><span data-stu-id="04bc5-121">int</span></span></p></td>
<td><p><span data-ttu-id="04bc5-122">Другом</span><span class="sxs-lookup"><span data-stu-id="04bc5-122">Foreign</span></span></p></td>
<td><p><span data-ttu-id="04bc5-123">Идентификатор клиента этого пользователя.</span><span class="sxs-lookup"><span data-stu-id="04bc5-123">This user’s Tenant ID.</span></span> <span data-ttu-id="04bc5-124">Дополнительные сведения приведены в <a href="lync-server-2013-tenants-table.md">таблице "клиенты" в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="04bc5-124">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="04bc5-125"><strong>уритипеид</strong></span><span class="sxs-lookup"><span data-stu-id="04bc5-125"><strong>UriTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="04bc5-126">целое</span><span class="sxs-lookup"><span data-stu-id="04bc5-126">int</span></span></p></td>
<td><p><span data-ttu-id="04bc5-127">Другом</span><span class="sxs-lookup"><span data-stu-id="04bc5-127">Foreign</span></span></p></td>
<td><p><span data-ttu-id="04bc5-128">Тип универсального кода ресурса (URI) этого пользователя.</span><span class="sxs-lookup"><span data-stu-id="04bc5-128">This user’s URI type.</span></span> <span data-ttu-id="04bc5-129">Для получения дополнительных сведений ознакомьтесь с <a href="lync-server-2013-uritypes-table.md">таблицей уритипес в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="04bc5-129">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

