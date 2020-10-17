---
title: 'Lync Server 2013: таблица Усерстатистикс'
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
ms.openlocfilehash: 55df55ba8c9953a1efce25269c24b43328472d7f
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48529996"
---
# <a name="userstatistics-table-in-lync-server-2013"></a><span data-ttu-id="27ea5-102">Таблица Усерстатистикс в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="27ea5-102">UserStatistics table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="27ea5-103">_**Последнее изменение темы:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="27ea5-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="27ea5-104">Таблица UserStatistics предназначена для поддержки.</span><span class="sxs-lookup"><span data-stu-id="27ea5-104">The UserStatistics table is a supporting table.</span></span> <span data-ttu-id="27ea5-105">Каждая запись в таблице содержит информацию об использовании системы отдельными пользователями.</span><span class="sxs-lookup"><span data-stu-id="27ea5-105">Each record in the table stores information about an individual user’s usage of the system.</span></span> <span data-ttu-id="27ea5-106">Эта таблица была введена в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="27ea5-106">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="27ea5-107">Столбец</span><span class="sxs-lookup"><span data-stu-id="27ea5-107">Column</span></span></th>
<th><span data-ttu-id="27ea5-108">Тип данных</span><span class="sxs-lookup"><span data-stu-id="27ea5-108">Data Type</span></span></th>
<th><span data-ttu-id="27ea5-109">Ключ или индекс</span><span class="sxs-lookup"><span data-stu-id="27ea5-109">Key/Index</span></span></th>
<th><span data-ttu-id="27ea5-110">Сведения</span><span class="sxs-lookup"><span data-stu-id="27ea5-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="27ea5-111"><strong>UserId</strong></span><span class="sxs-lookup"><span data-stu-id="27ea5-111"><strong>UserId</strong></span></span></p></td>
<td><p><span data-ttu-id="27ea5-112">int</span><span class="sxs-lookup"><span data-stu-id="27ea5-112">int</span></span></p></td>
<td><p><span data-ttu-id="27ea5-113">Primary</span><span class="sxs-lookup"><span data-stu-id="27ea5-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="27ea5-114">Уникальный номер, идентифицирующий данного пользователя.</span><span class="sxs-lookup"><span data-stu-id="27ea5-114">Unique number identifying this user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="27ea5-115"><strong>ластлогинтиме</strong></span><span class="sxs-lookup"><span data-stu-id="27ea5-115"><strong>LastLogInTime</strong></span></span></p></td>
<td><p><span data-ttu-id="27ea5-116">datetime</span><span class="sxs-lookup"><span data-stu-id="27ea5-116">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="27ea5-117">Время последнего входа пользователя в систему.</span><span class="sxs-lookup"><span data-stu-id="27ea5-117">Last time the user logged in.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="27ea5-118"><strong>ластконфорганизедтиме</strong></span><span class="sxs-lookup"><span data-stu-id="27ea5-118"><strong>LastConfOrganizedTime</strong></span></span></p></td>
<td><p><span data-ttu-id="27ea5-119">datetime</span><span class="sxs-lookup"><span data-stu-id="27ea5-119">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="27ea5-120">Время последней конференции, организованной пользователем.</span><span class="sxs-lookup"><span data-stu-id="27ea5-120">Last time the user organized a conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="27ea5-121"><strong>ласткаллорганизеркаллфаилуретиме</strong></span><span class="sxs-lookup"><span data-stu-id="27ea5-121"><strong>LastCallOrganizerCallFailureTime</strong></span></span></p></td>
<td><p><span data-ttu-id="27ea5-122">datetime</span><span class="sxs-lookup"><span data-stu-id="27ea5-122">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="27ea5-123">Время последнего сбоя вызова пользователя.</span><span class="sxs-lookup"><span data-stu-id="27ea5-123">Last time the user experienced a call failure.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="27ea5-124"><strong>ластконфорганизеркаллфаилуретиме</strong></span><span class="sxs-lookup"><span data-stu-id="27ea5-124"><strong>LastConfOrganizerCallFailureTime</strong></span></span></p></td>
<td><p><span data-ttu-id="27ea5-125">datetime</span><span class="sxs-lookup"><span data-stu-id="27ea5-125">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="27ea5-126">Время последнего сбоя вызова, когда организатором конференции был данный пользователь.</span><span class="sxs-lookup"><span data-stu-id="27ea5-126">Last time the user experienced a call failure as a conference organizer.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

