---
title: 'Lync Server 2013: представление пользователя'
description: 'Lync Server 2013: пользовательское представление.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: User view
ms:assetid: 796f77e6-1da6-4969-b18b-3537209a1fe4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688100(v=OCS.15)
ms:contentKeyID: 49733699
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: aa606887e8050a51f1e5a87656bb74a7cd58bbc3
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48558915"
---
# <a name="user-view-in-lync-server-2013"></a><span data-ttu-id="455b3-103">Пользовательское представление в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="455b3-103">User view in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="455b3-104">_**Последнее изменение темы:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="455b3-104">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="455b3-105">Представление User хранит информацию о пользователях, участвовавших в звонках или сеансах с записями в базе данных.</span><span class="sxs-lookup"><span data-stu-id="455b3-105">The User view stores information about users who have been involved in calls or sessions that have records in the database.</span></span> <span data-ttu-id="455b3-106">Это представление было представлено в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="455b3-106">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="455b3-107">Столбец</span><span class="sxs-lookup"><span data-stu-id="455b3-107">Column</span></span></th>
<th><span data-ttu-id="455b3-108">Тип данных</span><span class="sxs-lookup"><span data-stu-id="455b3-108">Data Type</span></span></th>
<th><span data-ttu-id="455b3-109">Сведения</span><span class="sxs-lookup"><span data-stu-id="455b3-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="455b3-110">UserId</span><span class="sxs-lookup"><span data-stu-id="455b3-110">UserId</span></span></p></td>
<td><p><span data-ttu-id="455b3-111">int</span><span class="sxs-lookup"><span data-stu-id="455b3-111">int</span></span></p></td>
<td><p><span data-ttu-id="455b3-112">Уникальный номер, идентифицирующий этого пользователя.</span><span class="sxs-lookup"><span data-stu-id="455b3-112">Unique number identifying this user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="455b3-113">UserUri</span><span class="sxs-lookup"><span data-stu-id="455b3-113">UserUri</span></span></p></td>
<td><p><span data-ttu-id="455b3-114">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="455b3-114">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="455b3-115">URI пользователя.</span><span class="sxs-lookup"><span data-stu-id="455b3-115">Uri of the user.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="455b3-116">тенанткэй</span><span class="sxs-lookup"><span data-stu-id="455b3-116">TenantKey</span></span></p></td>
<td><p><span data-ttu-id="455b3-117">идентификатора</span><span class="sxs-lookup"><span data-stu-id="455b3-117">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="455b3-118">Клиент пользователя.</span><span class="sxs-lookup"><span data-stu-id="455b3-118">Tenant of user.</span></span> <span data-ttu-id="455b3-119">Дополнительные сведения см. <a href="lync-server-2013-tenants-table.md">в таблице клиентов в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="455b3-119">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="455b3-120">уритипе</span><span class="sxs-lookup"><span data-stu-id="455b3-120">UriType</span></span></p></td>
<td><p><span data-ttu-id="455b3-121">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="455b3-121">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="455b3-122">Тип URI пользователя.</span><span class="sxs-lookup"><span data-stu-id="455b3-122">Type of user URI.</span></span> <span data-ttu-id="455b3-123">Дополнительные сведения см. <a href="lync-server-2013-uritypes-table.md">в таблице таблица uritypes в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="455b3-123">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

