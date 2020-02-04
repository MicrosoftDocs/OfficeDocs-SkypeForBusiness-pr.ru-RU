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
ms.openlocfilehash: 7609747848e1943a08eff2fa77b87f0168710f81
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41744259"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="userstatistics-table-in-lync-server-2013"></a><span data-ttu-id="05e74-102">Таблица Усерстатистикс в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="05e74-102">UserStatistics table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="05e74-103">_**Тема последнего изменения:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="05e74-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="05e74-104">Таблица Усерстатистикс является вспомогательной таблицей.</span><span class="sxs-lookup"><span data-stu-id="05e74-104">The UserStatistics table is a supporting table.</span></span> <span data-ttu-id="05e74-105">Каждая запись в таблице содержит сведения об использовании системы конкретным пользователем.</span><span class="sxs-lookup"><span data-stu-id="05e74-105">Each record in the table stores information about an individual user’s usage of the system.</span></span> <span data-ttu-id="05e74-106">Эта таблица введена в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="05e74-106">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="05e74-107">Столбец</span><span class="sxs-lookup"><span data-stu-id="05e74-107">Column</span></span></th>
<th><span data-ttu-id="05e74-108">Тип данных</span><span class="sxs-lookup"><span data-stu-id="05e74-108">Data Type</span></span></th>
<th><span data-ttu-id="05e74-109">Ключ/индекс</span><span class="sxs-lookup"><span data-stu-id="05e74-109">Key/Index</span></span></th>
<th><span data-ttu-id="05e74-110">Сведения</span><span class="sxs-lookup"><span data-stu-id="05e74-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="05e74-111"><strong>Идентификатора пользователя</strong></span><span class="sxs-lookup"><span data-stu-id="05e74-111"><strong>UserId</strong></span></span></p></td>
<td><p><span data-ttu-id="05e74-112">целое</span><span class="sxs-lookup"><span data-stu-id="05e74-112">int</span></span></p></td>
<td><p><span data-ttu-id="05e74-113">Primary</span><span class="sxs-lookup"><span data-stu-id="05e74-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="05e74-114">Уникальный номер, идентифицирующий этого пользователя.</span><span class="sxs-lookup"><span data-stu-id="05e74-114">Unique number identifying this user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="05e74-115"><strong>ластлогинтиме</strong></span><span class="sxs-lookup"><span data-stu-id="05e74-115"><strong>LastLogInTime</strong></span></span></p></td>
<td><p><span data-ttu-id="05e74-116">datetime</span><span class="sxs-lookup"><span data-stu-id="05e74-116">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="05e74-117">Время последнего входа пользователя в систему.</span><span class="sxs-lookup"><span data-stu-id="05e74-117">Last time the user logged in.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="05e74-118"><strong>ластконфорганизедтиме</strong></span><span class="sxs-lookup"><span data-stu-id="05e74-118"><strong>LastConfOrganizedTime</strong></span></span></p></td>
<td><p><span data-ttu-id="05e74-119">datetime</span><span class="sxs-lookup"><span data-stu-id="05e74-119">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="05e74-120">Последний раз, когда пользователь организует конференцию.</span><span class="sxs-lookup"><span data-stu-id="05e74-120">Last time the user organized a conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="05e74-121"><strong>ласткаллорганизеркаллфаилуретиме</strong></span><span class="sxs-lookup"><span data-stu-id="05e74-121"><strong>LastCallOrganizerCallFailureTime</strong></span></span></p></td>
<td><p><span data-ttu-id="05e74-122">datetime</span><span class="sxs-lookup"><span data-stu-id="05e74-122">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="05e74-123">Последнее время, когда пользователь попытался вызвать сбой звонка.</span><span class="sxs-lookup"><span data-stu-id="05e74-123">Last time the user experienced a call failure.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="05e74-124"><strong>ластконфорганизеркаллфаилуретиме</strong></span><span class="sxs-lookup"><span data-stu-id="05e74-124"><strong>LastConfOrganizerCallFailureTime</strong></span></span></p></td>
<td><p><span data-ttu-id="05e74-125">datetime</span><span class="sxs-lookup"><span data-stu-id="05e74-125">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="05e74-126">Последний раз, когда пользователь попытался вызвать сбой в организаторе конференц-связи.</span><span class="sxs-lookup"><span data-stu-id="05e74-126">Last time the user experienced a call failure as a conference organizer.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

