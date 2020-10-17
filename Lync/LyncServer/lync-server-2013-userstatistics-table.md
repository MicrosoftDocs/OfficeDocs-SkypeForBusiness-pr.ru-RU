---
title: 'Lync Server 2013: таблица Усерстатистикс'
description: 'Lync Server 2013: таблица Усерстатистикс.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: UserStatistics table
ms:assetid: cfaf803b-1679-4169-92d3-533fad3e56ed
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721893(v=OCS.15)
ms:contentKeyID: 49733827
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 75b34fa3c34af4cc9cf2cacc6ae7feb4d217114c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48548535"
---
# <a name="userstatistics-table-in-lync-server-2013"></a><span data-ttu-id="9d33e-103">Таблица Усерстатистикс в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9d33e-103">UserStatistics table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9d33e-104">_**Последнее изменение темы:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="9d33e-104">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="9d33e-105">Таблица UserStatistics предназначена для поддержки.</span><span class="sxs-lookup"><span data-stu-id="9d33e-105">The UserStatistics table is a supporting table.</span></span> <span data-ttu-id="9d33e-106">Каждая запись в таблице содержит информацию об использовании системы отдельными пользователями.</span><span class="sxs-lookup"><span data-stu-id="9d33e-106">Each record in the table stores information about an individual user’s usage of the system.</span></span> <span data-ttu-id="9d33e-107">Эта таблица была введена в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9d33e-107">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9d33e-108">Столбец</span><span class="sxs-lookup"><span data-stu-id="9d33e-108">Column</span></span></th>
<th><span data-ttu-id="9d33e-109">Тип данных</span><span class="sxs-lookup"><span data-stu-id="9d33e-109">Data Type</span></span></th>
<th><span data-ttu-id="9d33e-110">Ключ или индекс</span><span class="sxs-lookup"><span data-stu-id="9d33e-110">Key/Index</span></span></th>
<th><span data-ttu-id="9d33e-111">Сведения</span><span class="sxs-lookup"><span data-stu-id="9d33e-111">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9d33e-112"><strong>UserId</strong></span><span class="sxs-lookup"><span data-stu-id="9d33e-112"><strong>UserId</strong></span></span></p></td>
<td><p><span data-ttu-id="9d33e-113">int</span><span class="sxs-lookup"><span data-stu-id="9d33e-113">int</span></span></p></td>
<td><p><span data-ttu-id="9d33e-114">Primary</span><span class="sxs-lookup"><span data-stu-id="9d33e-114">Primary</span></span></p></td>
<td><p><span data-ttu-id="9d33e-115">Уникальный номер, идентифицирующий данного пользователя.</span><span class="sxs-lookup"><span data-stu-id="9d33e-115">Unique number identifying this user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9d33e-116"><strong>ластлогинтиме</strong></span><span class="sxs-lookup"><span data-stu-id="9d33e-116"><strong>LastLogInTime</strong></span></span></p></td>
<td><p><span data-ttu-id="9d33e-117">datetime</span><span class="sxs-lookup"><span data-stu-id="9d33e-117">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9d33e-118">Время последнего входа пользователя в систему.</span><span class="sxs-lookup"><span data-stu-id="9d33e-118">Last time the user logged in.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9d33e-119"><strong>ластконфорганизедтиме</strong></span><span class="sxs-lookup"><span data-stu-id="9d33e-119"><strong>LastConfOrganizedTime</strong></span></span></p></td>
<td><p><span data-ttu-id="9d33e-120">datetime</span><span class="sxs-lookup"><span data-stu-id="9d33e-120">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9d33e-121">Время последней конференции, организованной пользователем.</span><span class="sxs-lookup"><span data-stu-id="9d33e-121">Last time the user organized a conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9d33e-122"><strong>ласткаллорганизеркаллфаилуретиме</strong></span><span class="sxs-lookup"><span data-stu-id="9d33e-122"><strong>LastCallOrganizerCallFailureTime</strong></span></span></p></td>
<td><p><span data-ttu-id="9d33e-123">datetime</span><span class="sxs-lookup"><span data-stu-id="9d33e-123">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9d33e-124">Время последнего сбоя вызова пользователя.</span><span class="sxs-lookup"><span data-stu-id="9d33e-124">Last time the user experienced a call failure.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9d33e-125"><strong>ластконфорганизеркаллфаилуретиме</strong></span><span class="sxs-lookup"><span data-stu-id="9d33e-125"><strong>LastConfOrganizerCallFailureTime</strong></span></span></p></td>
<td><p><span data-ttu-id="9d33e-126">datetime</span><span class="sxs-lookup"><span data-stu-id="9d33e-126">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9d33e-127">Время последнего сбоя вызова, когда организатором конференции был данный пользователь.</span><span class="sxs-lookup"><span data-stu-id="9d33e-127">Last time the user experienced a call failure as a conference organizer.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

