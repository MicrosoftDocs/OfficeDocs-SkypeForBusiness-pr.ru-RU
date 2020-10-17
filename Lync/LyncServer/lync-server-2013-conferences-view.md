---
title: 'Lync Server 2013: представление конференций'
description: 'Lync Server 2013: представление конференций.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Conferences view
ms:assetid: c0e5c4db-c135-401f-9296-e9a49f6499a1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721871(v=OCS.15)
ms:contentKeyID: 49733803
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dee7fbb7c839c351fc9c81716a5800a678980549
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48561585"
---
# <a name="conferences-view-in-lync-server-2013"></a><span data-ttu-id="5ba06-103">Представление конференций в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5ba06-103">Conferences view in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5ba06-104">_**Последнее изменение темы:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="5ba06-104">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="5ba06-105">В представлении конференций хранятся сведения о конференциях.</span><span class="sxs-lookup"><span data-stu-id="5ba06-105">The Conferences View stores information about the conferences.</span></span> <span data-ttu-id="5ba06-106">Это представление было представлено в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5ba06-106">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5ba06-107">Столбец</span><span class="sxs-lookup"><span data-stu-id="5ba06-107">Column</span></span></th>
<th><span data-ttu-id="5ba06-108">Тип данных</span><span class="sxs-lookup"><span data-stu-id="5ba06-108">Data Type</span></span></th>
<th><span data-ttu-id="5ba06-109">Сведения</span><span class="sxs-lookup"><span data-stu-id="5ba06-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5ba06-110"><strong>сессионидтиме</strong></span><span class="sxs-lookup"><span data-stu-id="5ba06-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="5ba06-111">datetime</span><span class="sxs-lookup"><span data-stu-id="5ba06-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="5ba06-112">Время запроса сеанса.</span><span class="sxs-lookup"><span data-stu-id="5ba06-112">Time of session request.</span></span> <span data-ttu-id="5ba06-113">Используется вместе с параметром SessionIdSeq для уникального определения сеанса.</span><span class="sxs-lookup"><span data-stu-id="5ba06-113">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="5ba06-114">Дополнительные сведения см. <a href="lync-server-2013-dialogs-table.md">в таблице диалоговых окон в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="5ba06-114">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5ba06-115"><strong>сессионидсек</strong></span><span class="sxs-lookup"><span data-stu-id="5ba06-115"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="5ba06-116">int</span><span class="sxs-lookup"><span data-stu-id="5ba06-116">int</span></span></p></td>
<td><p><span data-ttu-id="5ba06-117">Идентификационный номер для идентификации сеанса.</span><span class="sxs-lookup"><span data-stu-id="5ba06-117">ID number to identify the session.</span></span> <span data-ttu-id="5ba06-118">Используется совместно с параметром SessionIdTime для уникальной идентификации сеанса.</span><span class="sxs-lookup"><span data-stu-id="5ba06-118">Used in conjunction with SessionIdTime to uniquely identify a session.</span></span> <span data-ttu-id="5ba06-119">Дополнительные сведения см. <a href="lync-server-2013-dialogs-table.md">в таблице диалоговых окон в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="5ba06-119">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5ba06-120"><strong>конференцеури</strong></span><span class="sxs-lookup"><span data-stu-id="5ba06-120"><strong>ConferenceUri</strong></span></span></p></td>
<td><p><span data-ttu-id="5ba06-121">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="5ba06-121">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="5ba06-122">URI конференции.</span><span class="sxs-lookup"><span data-stu-id="5ba06-122">URI for the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5ba06-123"><strong>конференцеуритипе</strong></span><span class="sxs-lookup"><span data-stu-id="5ba06-123"><strong>ConferenceUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="5ba06-124">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="5ba06-124">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="5ba06-125">Тип URI конференции.</span><span class="sxs-lookup"><span data-stu-id="5ba06-125">Type of the conference URI.</span></span> <span data-ttu-id="5ba06-126">Дополнительные сведения см. <a href="lync-server-2013-uritypes-table.md">в таблице таблица uritypes в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="5ba06-126">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5ba06-127"><strong>конфинстанце</strong></span><span class="sxs-lookup"><span data-stu-id="5ba06-127"><strong>ConfInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="5ba06-128">идентификатора</span><span class="sxs-lookup"><span data-stu-id="5ba06-128">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="5ba06-p105">Используется для повторяющихся конференций. Все экземпляры повторяющейся конференции имеют один и тот же ConferenceUri, но разные значения ConfInstance.</span><span class="sxs-lookup"><span data-stu-id="5ba06-p105">Used for recurring conferences. Each instance of a recurring conference has the same ConferenceUri but a different ConfInstance.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5ba06-131"><strong>конференцестарттиме</strong></span><span class="sxs-lookup"><span data-stu-id="5ba06-131"><strong>ConferenceStartTime</strong></span></span></p></td>
<td><p><span data-ttu-id="5ba06-132">datetime</span><span class="sxs-lookup"><span data-stu-id="5ba06-132">datetime</span></span></p></td>
<td><p><span data-ttu-id="5ba06-133">Время начала конференции.</span><span class="sxs-lookup"><span data-stu-id="5ba06-133">Starting time for the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5ba06-134"><strong>конференцеендтиме</strong></span><span class="sxs-lookup"><span data-stu-id="5ba06-134"><strong>ConferenceEndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="5ba06-135">datetime</span><span class="sxs-lookup"><span data-stu-id="5ba06-135">datetime</span></span></p></td>
<td><p><span data-ttu-id="5ba06-136">Время окончания конференции.</span><span class="sxs-lookup"><span data-stu-id="5ba06-136">Ending time for the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5ba06-137"><strong>организерури</strong></span><span class="sxs-lookup"><span data-stu-id="5ba06-137"><strong>OrganizerUri</strong></span></span></p></td>
<td><p><span data-ttu-id="5ba06-138">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="5ba06-138">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="5ba06-139">URI пользователя, организовавшего конференцию.</span><span class="sxs-lookup"><span data-stu-id="5ba06-139">URI of the user who organized the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5ba06-140"><strong>организертипе</strong></span><span class="sxs-lookup"><span data-stu-id="5ba06-140"><strong>OrganizerType</strong></span></span></p></td>
<td><p><span data-ttu-id="5ba06-141">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="5ba06-141">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="5ba06-142">Тип URI пользователя, организовавшего конференцию.</span><span class="sxs-lookup"><span data-stu-id="5ba06-142">Type of URI of the user who organized the conference.</span></span> <span data-ttu-id="5ba06-143">Дополнительные сведения см. <a href="lync-server-2013-uritypes-table.md">в таблице таблица uritypes в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="5ba06-143">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5ba06-144"><strong>организертенант</strong></span><span class="sxs-lookup"><span data-stu-id="5ba06-144"><strong>OrganizerTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="5ba06-145">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="5ba06-145">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="5ba06-146">Клиент пользователя, организовавшего конференцию.</span><span class="sxs-lookup"><span data-stu-id="5ba06-146">Tenant of the user who organized the conference.</span></span> <span data-ttu-id="5ba06-147">Дополнительные сведения см. <a href="lync-server-2013-tenants-table.md">в таблице клиентов в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="5ba06-147">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5ba06-148"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="5ba06-148"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="5ba06-149">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="5ba06-149">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="5ba06-150">Полное доменное имя пула, в котором размещена конференция.</span><span class="sxs-lookup"><span data-stu-id="5ba06-150">Fully qualified domain name of the pool that hosted the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5ba06-151"><strong>Флаг</strong></span><span class="sxs-lookup"><span data-stu-id="5ba06-151"><strong>Flag</strong></span></span></p></td>
<td><p><span data-ttu-id="5ba06-152">smallint</span><span class="sxs-lookup"><span data-stu-id="5ba06-152">smallint</span></span></p></td>
<td><p><span data-ttu-id="5ba06-p108">Битовая маска, содержащая атрибуты конференции. Возможные значения:</span><span class="sxs-lookup"><span data-stu-id="5ba06-p108">Bit mask that contains Conference Attributes. Possible values are:</span></span></p>
<p><span data-ttu-id="5ba06-155">0X01 – искусственная транзакция</span><span class="sxs-lookup"><span data-stu-id="5ba06-155">0X01 – Synthetic Transaction</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

