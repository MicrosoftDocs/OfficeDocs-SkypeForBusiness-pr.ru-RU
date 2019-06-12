---
title: 'Lync Server 2013: таблица Усерстатистикс'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: UserStatistics table
ms:assetid: cfaf803b-1679-4169-92d3-533fad3e56ed
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721893(v=OCS.15)
ms:contentKeyID: 49733827
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f0f684850625f61ca72bbcc9c4bc53b56fcc6b38
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849270"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="userstatistics-table-in-lync-server-2013"></a><span data-ttu-id="afb21-102">Таблица Усерстатистикс в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="afb21-102">UserStatistics table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="afb21-103">_**Тема последнего изменения:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="afb21-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="afb21-104">Таблица Усерстатистикс является вспомогательной таблицей.</span><span class="sxs-lookup"><span data-stu-id="afb21-104">The UserStatistics table is a supporting table.</span></span> <span data-ttu-id="afb21-105">Каждая запись в таблице содержит сведения об использовании системы конкретным пользователем.</span><span class="sxs-lookup"><span data-stu-id="afb21-105">Each record in the table stores information about an individual user’s usage of the system.</span></span> <span data-ttu-id="afb21-106">Эта таблица введена в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="afb21-106">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="afb21-107">Столбец</span><span class="sxs-lookup"><span data-stu-id="afb21-107">Column</span></span></th>
<th><span data-ttu-id="afb21-108">Тип данных</span><span class="sxs-lookup"><span data-stu-id="afb21-108">Data Type</span></span></th>
<th><span data-ttu-id="afb21-109">Ключ/индекс</span><span class="sxs-lookup"><span data-stu-id="afb21-109">Key/Index</span></span></th>
<th><span data-ttu-id="afb21-110">Сведения</span><span class="sxs-lookup"><span data-stu-id="afb21-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="afb21-111"><strong>Идентификатора пользователя</strong></span><span class="sxs-lookup"><span data-stu-id="afb21-111"><strong>UserId</strong></span></span></p></td>
<td><p><span data-ttu-id="afb21-112">целое</span><span class="sxs-lookup"><span data-stu-id="afb21-112">int</span></span></p></td>
<td><p><span data-ttu-id="afb21-113">Primary</span><span class="sxs-lookup"><span data-stu-id="afb21-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="afb21-114">Уникальный номер, идентифицирующий этого пользователя.</span><span class="sxs-lookup"><span data-stu-id="afb21-114">Unique number identifying this user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="afb21-115"><strong>Ластлогинтиме</strong></span><span class="sxs-lookup"><span data-stu-id="afb21-115"><strong>LastLogInTime</strong></span></span></p></td>
<td><p><span data-ttu-id="afb21-116">datetime</span><span class="sxs-lookup"><span data-stu-id="afb21-116">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="afb21-117">Время последнего входа пользователя в систему.</span><span class="sxs-lookup"><span data-stu-id="afb21-117">Last time the user logged in.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="afb21-118"><strong>Ластконфорганизедтиме</strong></span><span class="sxs-lookup"><span data-stu-id="afb21-118"><strong>LastConfOrganizedTime</strong></span></span></p></td>
<td><p><span data-ttu-id="afb21-119">datetime</span><span class="sxs-lookup"><span data-stu-id="afb21-119">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="afb21-120">Последний раз, когда пользователь организует конференцию.</span><span class="sxs-lookup"><span data-stu-id="afb21-120">Last time the user organized a conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="afb21-121"><strong>Ласткаллорганизеркаллфаилуретиме</strong></span><span class="sxs-lookup"><span data-stu-id="afb21-121"><strong>LastCallOrganizerCallFailureTime</strong></span></span></p></td>
<td><p><span data-ttu-id="afb21-122">datetime</span><span class="sxs-lookup"><span data-stu-id="afb21-122">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="afb21-123">Последнее время, когда пользователь попытался вызвать сбой звонка.</span><span class="sxs-lookup"><span data-stu-id="afb21-123">Last time the user experienced a call failure.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="afb21-124"><strong>Ластконфорганизеркаллфаилуретиме</strong></span><span class="sxs-lookup"><span data-stu-id="afb21-124"><strong>LastConfOrganizerCallFailureTime</strong></span></span></p></td>
<td><p><span data-ttu-id="afb21-125">datetime</span><span class="sxs-lookup"><span data-stu-id="afb21-125">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="afb21-126">Последний раз, когда пользователь попытался вызвать сбой в организаторе конференц-связи.</span><span class="sxs-lookup"><span data-stu-id="afb21-126">Last time the user experienced a call failure as a conference organizer.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

