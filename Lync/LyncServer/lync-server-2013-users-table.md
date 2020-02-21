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
ms.openlocfilehash: 70aefd95a8abaa1d9b49e89ac3e7b14dfa2444e7
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42212935"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="users-table-in-lync-server-2013"></a><span data-ttu-id="d255c-102">Таблица Users в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d255c-102">Users table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d255c-103">_**Последнее изменение темы:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="d255c-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="d255c-104">Таблица Users — это вспомогательная таблица.</span><span class="sxs-lookup"><span data-stu-id="d255c-104">The Users table is a supporting table.</span></span> <span data-ttu-id="d255c-105">Каждая запись в таблице содержит сведения об одном пользователе, участвующем в вызовах или сеансах с записями в базе данных.</span><span class="sxs-lookup"><span data-stu-id="d255c-105">Each record in the table stores information about one user involved in calls or sessions that have records in the database.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d255c-106">Столбец</span><span class="sxs-lookup"><span data-stu-id="d255c-106">Column</span></span></th>
<th><span data-ttu-id="d255c-107">Тип данных</span><span class="sxs-lookup"><span data-stu-id="d255c-107">Data Type</span></span></th>
<th><span data-ttu-id="d255c-108">Ключ или индекс</span><span class="sxs-lookup"><span data-stu-id="d255c-108">Key/Index</span></span></th>
<th><span data-ttu-id="d255c-109">Сведения</span><span class="sxs-lookup"><span data-stu-id="d255c-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d255c-110"><strong>некступдатетс</strong></span><span class="sxs-lookup"><span data-stu-id="d255c-110"><strong>NextUpdateTS</strong></span></span></p></td>
<td><p><span data-ttu-id="d255c-111">datetime</span><span class="sxs-lookup"><span data-stu-id="d255c-111">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d255c-112">Метка времени для внутреннего использования.</span><span class="sxs-lookup"><span data-stu-id="d255c-112">Time stamp for internal use.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d255c-113"><strong>UserId</strong></span><span class="sxs-lookup"><span data-stu-id="d255c-113"><strong>UserId</strong></span></span></p></td>
<td><p><span data-ttu-id="d255c-114">int</span><span class="sxs-lookup"><span data-stu-id="d255c-114">int</span></span></p></td>
<td><p><span data-ttu-id="d255c-115">Primary</span><span class="sxs-lookup"><span data-stu-id="d255c-115">Primary</span></span></p></td>
<td><p><span data-ttu-id="d255c-116">Уникальный номер, идентифицирующий данного пользователя.</span><span class="sxs-lookup"><span data-stu-id="d255c-116">Unique number identifying this user.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d255c-117"><strong>UserUri</strong></span><span class="sxs-lookup"><span data-stu-id="d255c-117"><strong>UserUri</strong></span></span></p></td>
<td><p><span data-ttu-id="d255c-118">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="d255c-118">nvarchar(450)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="d255c-119">URI пользователя.</span><span class="sxs-lookup"><span data-stu-id="d255c-119">User URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d255c-120"><strong>TenantId</strong></span><span class="sxs-lookup"><span data-stu-id="d255c-120"><strong>TenantId</strong></span></span></p></td>
<td><p><span data-ttu-id="d255c-121">int</span><span class="sxs-lookup"><span data-stu-id="d255c-121">int</span></span></p></td>
<td><p><span data-ttu-id="d255c-122">Правительства</span><span class="sxs-lookup"><span data-stu-id="d255c-122">Foreign</span></span></p></td>
<td><p><span data-ttu-id="d255c-123">Идентификатор клиента этого пользователя.</span><span class="sxs-lookup"><span data-stu-id="d255c-123">This user’s Tenant ID.</span></span> <span data-ttu-id="d255c-124">Дополнительные сведения см. <a href="lync-server-2013-tenants-table.md">в таблице клиентов в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="d255c-124">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d255c-125"><strong>уритипеид</strong></span><span class="sxs-lookup"><span data-stu-id="d255c-125"><strong>UriTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="d255c-126">int</span><span class="sxs-lookup"><span data-stu-id="d255c-126">int</span></span></p></td>
<td><p><span data-ttu-id="d255c-127">Правительства</span><span class="sxs-lookup"><span data-stu-id="d255c-127">Foreign</span></span></p></td>
<td><p><span data-ttu-id="d255c-128">Тип URI этого пользователя.</span><span class="sxs-lookup"><span data-stu-id="d255c-128">This user’s URI type.</span></span> <span data-ttu-id="d255c-129">Дополнительные сведения см. <a href="lync-server-2013-uritypes-table.md">в таблице таблица uritypes в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="d255c-129">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

