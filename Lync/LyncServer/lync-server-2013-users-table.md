---
title: 'Lync Server 2013: таблица Users'
description: 'Lync Server 2013: таблица Users.'
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
ms.openlocfilehash: 9b1418e162a04e46ee0dfeca082aa66b0665fc77
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48548635"
---
# <a name="users-table-in-lync-server-2013"></a><span data-ttu-id="1da40-103">Таблица Users в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1da40-103">Users table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1da40-104">_**Последнее изменение темы:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="1da40-104">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="1da40-105">Таблица Users — это вспомогательная таблица.</span><span class="sxs-lookup"><span data-stu-id="1da40-105">The Users table is a supporting table.</span></span> <span data-ttu-id="1da40-106">Каждая запись в таблице содержит сведения об одном пользователе, участвующем в вызовах или сеансах с записями в базе данных.</span><span class="sxs-lookup"><span data-stu-id="1da40-106">Each record in the table stores information about one user involved in calls or sessions that have records in the database.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1da40-107">Столбец</span><span class="sxs-lookup"><span data-stu-id="1da40-107">Column</span></span></th>
<th><span data-ttu-id="1da40-108">Тип данных</span><span class="sxs-lookup"><span data-stu-id="1da40-108">Data Type</span></span></th>
<th><span data-ttu-id="1da40-109">Ключ или индекс</span><span class="sxs-lookup"><span data-stu-id="1da40-109">Key/Index</span></span></th>
<th><span data-ttu-id="1da40-110">Сведения</span><span class="sxs-lookup"><span data-stu-id="1da40-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1da40-111"><strong>некступдатетс</strong></span><span class="sxs-lookup"><span data-stu-id="1da40-111"><strong>NextUpdateTS</strong></span></span></p></td>
<td><p><span data-ttu-id="1da40-112">datetime</span><span class="sxs-lookup"><span data-stu-id="1da40-112">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1da40-113">Метка времени для внутреннего использования.</span><span class="sxs-lookup"><span data-stu-id="1da40-113">Time stamp for internal use.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1da40-114"><strong>UserId</strong></span><span class="sxs-lookup"><span data-stu-id="1da40-114"><strong>UserId</strong></span></span></p></td>
<td><p><span data-ttu-id="1da40-115">int</span><span class="sxs-lookup"><span data-stu-id="1da40-115">int</span></span></p></td>
<td><p><span data-ttu-id="1da40-116">Primary</span><span class="sxs-lookup"><span data-stu-id="1da40-116">Primary</span></span></p></td>
<td><p><span data-ttu-id="1da40-117">Уникальный номер, идентифицирующий данного пользователя.</span><span class="sxs-lookup"><span data-stu-id="1da40-117">Unique number identifying this user.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1da40-118"><strong>UserUri</strong></span><span class="sxs-lookup"><span data-stu-id="1da40-118"><strong>UserUri</strong></span></span></p></td>
<td><p><span data-ttu-id="1da40-119">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="1da40-119">nvarchar(450)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="1da40-120">URI пользователя.</span><span class="sxs-lookup"><span data-stu-id="1da40-120">User URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1da40-121"><strong>TenantId</strong></span><span class="sxs-lookup"><span data-stu-id="1da40-121"><strong>TenantId</strong></span></span></p></td>
<td><p><span data-ttu-id="1da40-122">int</span><span class="sxs-lookup"><span data-stu-id="1da40-122">int</span></span></p></td>
<td><p><span data-ttu-id="1da40-123">Правительства</span><span class="sxs-lookup"><span data-stu-id="1da40-123">Foreign</span></span></p></td>
<td><p><span data-ttu-id="1da40-124">Идентификатор клиента этого пользователя.</span><span class="sxs-lookup"><span data-stu-id="1da40-124">This user’s Tenant ID.</span></span> <span data-ttu-id="1da40-125">Дополнительные сведения см. <a href="lync-server-2013-tenants-table.md">в таблице клиентов в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="1da40-125">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1da40-126"><strong>уритипеид</strong></span><span class="sxs-lookup"><span data-stu-id="1da40-126"><strong>UriTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="1da40-127">int</span><span class="sxs-lookup"><span data-stu-id="1da40-127">int</span></span></p></td>
<td><p><span data-ttu-id="1da40-128">Правительства</span><span class="sxs-lookup"><span data-stu-id="1da40-128">Foreign</span></span></p></td>
<td><p><span data-ttu-id="1da40-129">Тип URI этого пользователя.</span><span class="sxs-lookup"><span data-stu-id="1da40-129">This user’s URI type.</span></span> <span data-ttu-id="1da40-130">Дополнительные сведения см. <a href="lync-server-2013-uritypes-table.md">в таблице таблица uritypes в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="1da40-130">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

