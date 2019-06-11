---
title: 'Lync Server 2013: представление "Конференции"'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Conferences view
ms:assetid: c0e5c4db-c135-401f-9296-e9a49f6499a1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721871(v=OCS.15)
ms:contentKeyID: 49733803
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 710aadb2770e9389d9e4becf206d68b8e8d815ee
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34841486"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conferences-view-in-lync-server-2013"></a><span data-ttu-id="fcb12-102">Представление "Конференции" в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fcb12-102">Conferences view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fcb12-103">_**Тема последнего изменения:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="fcb12-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="fcb12-104">В представлении "Конференции" хранятся сведения о конференциях.</span><span class="sxs-lookup"><span data-stu-id="fcb12-104">The Conferences View stores information about the conferences.</span></span> <span data-ttu-id="fcb12-105">Это представление было представлено в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="fcb12-105">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fcb12-106">Столбец</span><span class="sxs-lookup"><span data-stu-id="fcb12-106">Column</span></span></th>
<th><span data-ttu-id="fcb12-107">Тип данных</span><span class="sxs-lookup"><span data-stu-id="fcb12-107">Data Type</span></span></th>
<th><span data-ttu-id="fcb12-108">Подробности</span><span class="sxs-lookup"><span data-stu-id="fcb12-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fcb12-109"><strong>Сессионидтиме</strong></span><span class="sxs-lookup"><span data-stu-id="fcb12-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="fcb12-110">datetime</span><span class="sxs-lookup"><span data-stu-id="fcb12-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="fcb12-111">Время запроса сеанса.</span><span class="sxs-lookup"><span data-stu-id="fcb12-111">Time of session request.</span></span> <span data-ttu-id="fcb12-112">Используется в сочетании с Сессионидсек для уникальной идентификации сеанса.</span><span class="sxs-lookup"><span data-stu-id="fcb12-112">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="fcb12-113">Дополнительные сведения приведены <a href="lync-server-2013-dialogs-table.md">в таблице диалоговые окна Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="fcb12-113">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fcb12-114"><strong>Сессионидсек</strong></span><span class="sxs-lookup"><span data-stu-id="fcb12-114"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="fcb12-115">целое</span><span class="sxs-lookup"><span data-stu-id="fcb12-115">int</span></span></p></td>
<td><p><span data-ttu-id="fcb12-116">ИДЕНТИФИКАЦИОНный номер для идентификации сеанса.</span><span class="sxs-lookup"><span data-stu-id="fcb12-116">ID number to identify the session.</span></span> <span data-ttu-id="fcb12-117">Используется в сочетании с Сессионидтиме для уникальной идентификации сеанса.</span><span class="sxs-lookup"><span data-stu-id="fcb12-117">Used in conjunction with SessionIdTime to uniquely identify a session.</span></span> <span data-ttu-id="fcb12-118">Дополнительные сведения приведены <a href="lync-server-2013-dialogs-table.md">в таблице диалоговые окна Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="fcb12-118">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fcb12-119"><strong>ConferenceUri</strong></span><span class="sxs-lookup"><span data-stu-id="fcb12-119"><strong>ConferenceUri</strong></span></span></p></td>
<td><p><span data-ttu-id="fcb12-120">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="fcb12-120">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="fcb12-121">Универсальный код ресурса (URI) для Конференции.</span><span class="sxs-lookup"><span data-stu-id="fcb12-121">URI for the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fcb12-122"><strong>Конференцеуритипе</strong></span><span class="sxs-lookup"><span data-stu-id="fcb12-122"><strong>ConferenceUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="fcb12-123">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="fcb12-123">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="fcb12-124">Тип URI конференции.</span><span class="sxs-lookup"><span data-stu-id="fcb12-124">Type of the conference URI.</span></span> <span data-ttu-id="fcb12-125">Для получения дополнительных сведений ознакомьтесь с <a href="lync-server-2013-uritypes-table.md">таблицей уритипес в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="fcb12-125">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fcb12-126"><strong>Конфинстанце</strong></span><span class="sxs-lookup"><span data-stu-id="fcb12-126"><strong>ConfInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="fcb12-127">идентификатора</span><span class="sxs-lookup"><span data-stu-id="fcb12-127">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="fcb12-128">Используется для повторяющихся конференций.</span><span class="sxs-lookup"><span data-stu-id="fcb12-128">Used for recurring conferences.</span></span> <span data-ttu-id="fcb12-129">Каждый экземпляр повторяющейся Конференции имеет один и тот же Конференцеури, но другой Конфинстанце.</span><span class="sxs-lookup"><span data-stu-id="fcb12-129">Each instance of a recurring conference has the same ConferenceUri but a different ConfInstance.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fcb12-130"><strong>Конференцестарттиме</strong></span><span class="sxs-lookup"><span data-stu-id="fcb12-130"><strong>ConferenceStartTime</strong></span></span></p></td>
<td><p><span data-ttu-id="fcb12-131">datetime</span><span class="sxs-lookup"><span data-stu-id="fcb12-131">datetime</span></span></p></td>
<td><p><span data-ttu-id="fcb12-132">Время начала Конференции.</span><span class="sxs-lookup"><span data-stu-id="fcb12-132">Starting time for the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fcb12-133"><strong>Конференцеендтиме</strong></span><span class="sxs-lookup"><span data-stu-id="fcb12-133"><strong>ConferenceEndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="fcb12-134">datetime</span><span class="sxs-lookup"><span data-stu-id="fcb12-134">datetime</span></span></p></td>
<td><p><span data-ttu-id="fcb12-135">Время окончания Конференции.</span><span class="sxs-lookup"><span data-stu-id="fcb12-135">Ending time for the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fcb12-136"><strong>Организерури</strong></span><span class="sxs-lookup"><span data-stu-id="fcb12-136"><strong>OrganizerUri</strong></span></span></p></td>
<td><p><span data-ttu-id="fcb12-137">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="fcb12-137">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="fcb12-138">Универсальный код ресурса (URI) пользователя, который организовал конференцию.</span><span class="sxs-lookup"><span data-stu-id="fcb12-138">URI of the user who organized the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fcb12-139"><strong>Организертипе</strong></span><span class="sxs-lookup"><span data-stu-id="fcb12-139"><strong>OrganizerType</strong></span></span></p></td>
<td><p><span data-ttu-id="fcb12-140">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="fcb12-140">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="fcb12-141">Тип URI пользователя, который организовал конференцию.</span><span class="sxs-lookup"><span data-stu-id="fcb12-141">Type of URI of the user who organized the conference.</span></span> <span data-ttu-id="fcb12-142">Для получения дополнительных сведений ознакомьтесь с <a href="lync-server-2013-uritypes-table.md">таблицей уритипес в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="fcb12-142">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fcb12-143"><strong>Организертенант</strong></span><span class="sxs-lookup"><span data-stu-id="fcb12-143"><strong>OrganizerTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="fcb12-144">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="fcb12-144">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="fcb12-145">Клиент пользователя, который организовал конференцию.</span><span class="sxs-lookup"><span data-stu-id="fcb12-145">Tenant of the user who organized the conference.</span></span> <span data-ttu-id="fcb12-146">Дополнительные сведения приведены в <a href="lync-server-2013-tenants-table.md">таблице "клиенты" в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="fcb12-146">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fcb12-147"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="fcb12-147"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="fcb12-148">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="fcb12-148">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="fcb12-149">Полное доменное имя пула, на котором размещается конференция.</span><span class="sxs-lookup"><span data-stu-id="fcb12-149">Fully qualified domain name of the pool that hosted the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fcb12-150"><strong>Пометка</strong></span><span class="sxs-lookup"><span data-stu-id="fcb12-150"><strong>Flag</strong></span></span></p></td>
<td><p><span data-ttu-id="fcb12-151">smallint</span><span class="sxs-lookup"><span data-stu-id="fcb12-151">smallint</span></span></p></td>
<td><p><span data-ttu-id="fcb12-152">Битовая маска, которая включает атрибуты Конференции.</span><span class="sxs-lookup"><span data-stu-id="fcb12-152">Bit mask that contains Conference Attributes.</span></span> <span data-ttu-id="fcb12-153">Возможные значения</span><span class="sxs-lookup"><span data-stu-id="fcb12-153">Possible values are:</span></span></p>
<p><span data-ttu-id="fcb12-154">0X01 — искусственная транзакция</span><span class="sxs-lookup"><span data-stu-id="fcb12-154">0X01 – Synthetic Transaction</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

