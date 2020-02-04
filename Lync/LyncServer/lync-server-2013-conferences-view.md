---
title: 'Lync Server 2013: представление "Конференции"'
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
ms.openlocfilehash: 36278c1053c2b5737e0de6caf914c050db93ea4b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741609"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conferences-view-in-lync-server-2013"></a><span data-ttu-id="ad48c-102">Представление "Конференции" в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ad48c-102">Conferences view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ad48c-103">_**Тема последнего изменения:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="ad48c-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="ad48c-104">В представлении "Конференции" хранятся сведения о конференциях.</span><span class="sxs-lookup"><span data-stu-id="ad48c-104">The Conferences View stores information about the conferences.</span></span> <span data-ttu-id="ad48c-105">Это представление было представлено в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ad48c-105">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ad48c-106">Столбец</span><span class="sxs-lookup"><span data-stu-id="ad48c-106">Column</span></span></th>
<th><span data-ttu-id="ad48c-107">Тип данных</span><span class="sxs-lookup"><span data-stu-id="ad48c-107">Data Type</span></span></th>
<th><span data-ttu-id="ad48c-108">Подробности</span><span class="sxs-lookup"><span data-stu-id="ad48c-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ad48c-109"><strong>сессионидтиме</strong></span><span class="sxs-lookup"><span data-stu-id="ad48c-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="ad48c-110">datetime</span><span class="sxs-lookup"><span data-stu-id="ad48c-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="ad48c-111">Время запроса сеанса.</span><span class="sxs-lookup"><span data-stu-id="ad48c-111">Time of session request.</span></span> <span data-ttu-id="ad48c-112">Используется в сочетании с Сессионидсек для уникальной идентификации сеанса.</span><span class="sxs-lookup"><span data-stu-id="ad48c-112">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="ad48c-113">Дополнительные сведения приведены <a href="lync-server-2013-dialogs-table.md">в таблице диалоговые окна Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="ad48c-113">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ad48c-114"><strong>сессионидсек</strong></span><span class="sxs-lookup"><span data-stu-id="ad48c-114"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="ad48c-115">целое</span><span class="sxs-lookup"><span data-stu-id="ad48c-115">int</span></span></p></td>
<td><p><span data-ttu-id="ad48c-116">ИДЕНТИФИКАЦИОНный номер для идентификации сеанса.</span><span class="sxs-lookup"><span data-stu-id="ad48c-116">ID number to identify the session.</span></span> <span data-ttu-id="ad48c-117">Используется в сочетании с Сессионидтиме для уникальной идентификации сеанса.</span><span class="sxs-lookup"><span data-stu-id="ad48c-117">Used in conjunction with SessionIdTime to uniquely identify a session.</span></span> <span data-ttu-id="ad48c-118">Дополнительные сведения приведены <a href="lync-server-2013-dialogs-table.md">в таблице диалоговые окна Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="ad48c-118">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ad48c-119"><strong>ConferenceUri</strong></span><span class="sxs-lookup"><span data-stu-id="ad48c-119"><strong>ConferenceUri</strong></span></span></p></td>
<td><p><span data-ttu-id="ad48c-120">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="ad48c-120">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="ad48c-121">Универсальный код ресурса (URI) для Конференции.</span><span class="sxs-lookup"><span data-stu-id="ad48c-121">URI for the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ad48c-122"><strong>конференцеуритипе</strong></span><span class="sxs-lookup"><span data-stu-id="ad48c-122"><strong>ConferenceUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="ad48c-123">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="ad48c-123">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="ad48c-124">Тип URI конференции.</span><span class="sxs-lookup"><span data-stu-id="ad48c-124">Type of the conference URI.</span></span> <span data-ttu-id="ad48c-125">Для получения дополнительных сведений ознакомьтесь с <a href="lync-server-2013-uritypes-table.md">таблицей уритипес в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="ad48c-125">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ad48c-126"><strong>конфинстанце</strong></span><span class="sxs-lookup"><span data-stu-id="ad48c-126"><strong>ConfInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="ad48c-127">идентификатора</span><span class="sxs-lookup"><span data-stu-id="ad48c-127">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="ad48c-128">Используется для повторяющихся конференций.</span><span class="sxs-lookup"><span data-stu-id="ad48c-128">Used for recurring conferences.</span></span> <span data-ttu-id="ad48c-129">Каждый экземпляр повторяющейся Конференции имеет один и тот же Конференцеури, но другой Конфинстанце.</span><span class="sxs-lookup"><span data-stu-id="ad48c-129">Each instance of a recurring conference has the same ConferenceUri but a different ConfInstance.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ad48c-130"><strong>конференцестарттиме</strong></span><span class="sxs-lookup"><span data-stu-id="ad48c-130"><strong>ConferenceStartTime</strong></span></span></p></td>
<td><p><span data-ttu-id="ad48c-131">datetime</span><span class="sxs-lookup"><span data-stu-id="ad48c-131">datetime</span></span></p></td>
<td><p><span data-ttu-id="ad48c-132">Время начала Конференции.</span><span class="sxs-lookup"><span data-stu-id="ad48c-132">Starting time for the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ad48c-133"><strong>конференцеендтиме</strong></span><span class="sxs-lookup"><span data-stu-id="ad48c-133"><strong>ConferenceEndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="ad48c-134">datetime</span><span class="sxs-lookup"><span data-stu-id="ad48c-134">datetime</span></span></p></td>
<td><p><span data-ttu-id="ad48c-135">Время окончания Конференции.</span><span class="sxs-lookup"><span data-stu-id="ad48c-135">Ending time for the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ad48c-136"><strong>организерури</strong></span><span class="sxs-lookup"><span data-stu-id="ad48c-136"><strong>OrganizerUri</strong></span></span></p></td>
<td><p><span data-ttu-id="ad48c-137">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="ad48c-137">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="ad48c-138">Универсальный код ресурса (URI) пользователя, который организовал конференцию.</span><span class="sxs-lookup"><span data-stu-id="ad48c-138">URI of the user who organized the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ad48c-139"><strong>организертипе</strong></span><span class="sxs-lookup"><span data-stu-id="ad48c-139"><strong>OrganizerType</strong></span></span></p></td>
<td><p><span data-ttu-id="ad48c-140">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="ad48c-140">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="ad48c-141">Тип URI пользователя, который организовал конференцию.</span><span class="sxs-lookup"><span data-stu-id="ad48c-141">Type of URI of the user who organized the conference.</span></span> <span data-ttu-id="ad48c-142">Для получения дополнительных сведений ознакомьтесь с <a href="lync-server-2013-uritypes-table.md">таблицей уритипес в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="ad48c-142">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ad48c-143"><strong>организертенант</strong></span><span class="sxs-lookup"><span data-stu-id="ad48c-143"><strong>OrganizerTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="ad48c-144">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="ad48c-144">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="ad48c-145">Клиент пользователя, который организовал конференцию.</span><span class="sxs-lookup"><span data-stu-id="ad48c-145">Tenant of the user who organized the conference.</span></span> <span data-ttu-id="ad48c-146">Дополнительные сведения приведены в <a href="lync-server-2013-tenants-table.md">таблице "клиенты" в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="ad48c-146">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ad48c-147"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="ad48c-147"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="ad48c-148">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="ad48c-148">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="ad48c-149">Полное доменное имя пула, на котором размещается конференция.</span><span class="sxs-lookup"><span data-stu-id="ad48c-149">Fully qualified domain name of the pool that hosted the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ad48c-150"><strong>Пометка</strong></span><span class="sxs-lookup"><span data-stu-id="ad48c-150"><strong>Flag</strong></span></span></p></td>
<td><p><span data-ttu-id="ad48c-151">smallint</span><span class="sxs-lookup"><span data-stu-id="ad48c-151">smallint</span></span></p></td>
<td><p><span data-ttu-id="ad48c-152">Битовая маска, которая включает атрибуты Конференции.</span><span class="sxs-lookup"><span data-stu-id="ad48c-152">Bit mask that contains Conference Attributes.</span></span> <span data-ttu-id="ad48c-153">Возможные значения</span><span class="sxs-lookup"><span data-stu-id="ad48c-153">Possible values are:</span></span></p>
<p><span data-ttu-id="ad48c-154">0X01 — искусственная транзакция</span><span class="sxs-lookup"><span data-stu-id="ad48c-154">0X01 – Synthetic Transaction</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

