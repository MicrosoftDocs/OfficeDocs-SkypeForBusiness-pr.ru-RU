---
title: 'Lync Server 2013: представление конференций'
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
ms.openlocfilehash: e94771b1dab86bdad627e2634c84001749a4ad0c
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42140582"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="conferences-view-in-lync-server-2013"></a><span data-ttu-id="51450-102">Представление конференций в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="51450-102">Conferences view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="51450-103">_**Последнее изменение темы:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="51450-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="51450-104">В представлении конференций хранятся сведения о конференциях.</span><span class="sxs-lookup"><span data-stu-id="51450-104">The Conferences View stores information about the conferences.</span></span> <span data-ttu-id="51450-105">Это представление было представлено в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="51450-105">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="51450-106">Столбец</span><span class="sxs-lookup"><span data-stu-id="51450-106">Column</span></span></th>
<th><span data-ttu-id="51450-107">Тип данных</span><span class="sxs-lookup"><span data-stu-id="51450-107">Data Type</span></span></th>
<th><span data-ttu-id="51450-108">Сведения</span><span class="sxs-lookup"><span data-stu-id="51450-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="51450-109"><strong>сессионидтиме</strong></span><span class="sxs-lookup"><span data-stu-id="51450-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="51450-110">datetime</span><span class="sxs-lookup"><span data-stu-id="51450-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="51450-111">Время запроса сеанса.</span><span class="sxs-lookup"><span data-stu-id="51450-111">Time of session request.</span></span> <span data-ttu-id="51450-112">Используется вместе с параметром SessionIdSeq для уникального определения сеанса.</span><span class="sxs-lookup"><span data-stu-id="51450-112">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="51450-113">Дополнительные сведения см. <a href="lync-server-2013-dialogs-table.md">в таблице диалоговых окон в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="51450-113">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="51450-114"><strong>сессионидсек</strong></span><span class="sxs-lookup"><span data-stu-id="51450-114"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="51450-115">int</span><span class="sxs-lookup"><span data-stu-id="51450-115">int</span></span></p></td>
<td><p><span data-ttu-id="51450-116">Идентификационный номер для идентификации сеанса.</span><span class="sxs-lookup"><span data-stu-id="51450-116">ID number to identify the session.</span></span> <span data-ttu-id="51450-117">Используется совместно с параметром SessionIdTime для уникальной идентификации сеанса.</span><span class="sxs-lookup"><span data-stu-id="51450-117">Used in conjunction with SessionIdTime to uniquely identify a session.</span></span> <span data-ttu-id="51450-118">Дополнительные сведения см. <a href="lync-server-2013-dialogs-table.md">в таблице диалоговых окон в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="51450-118">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="51450-119"><strong>конференцеури</strong></span><span class="sxs-lookup"><span data-stu-id="51450-119"><strong>ConferenceUri</strong></span></span></p></td>
<td><p><span data-ttu-id="51450-120">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="51450-120">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="51450-121">URI конференции.</span><span class="sxs-lookup"><span data-stu-id="51450-121">URI for the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="51450-122"><strong>конференцеуритипе</strong></span><span class="sxs-lookup"><span data-stu-id="51450-122"><strong>ConferenceUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="51450-123">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="51450-123">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="51450-124">Тип URI конференции.</span><span class="sxs-lookup"><span data-stu-id="51450-124">Type of the conference URI.</span></span> <span data-ttu-id="51450-125">Дополнительные сведения см. <a href="lync-server-2013-uritypes-table.md">в таблице таблица uritypes в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="51450-125">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="51450-126"><strong>конфинстанце</strong></span><span class="sxs-lookup"><span data-stu-id="51450-126"><strong>ConfInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="51450-127">идентификатора</span><span class="sxs-lookup"><span data-stu-id="51450-127">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="51450-p105">Используется для повторяющихся конференций. Все экземпляры повторяющейся конференции имеют один и тот же ConferenceUri, но разные значения ConfInstance.</span><span class="sxs-lookup"><span data-stu-id="51450-p105">Used for recurring conferences. Each instance of a recurring conference has the same ConferenceUri but a different ConfInstance.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="51450-130"><strong>конференцестарттиме</strong></span><span class="sxs-lookup"><span data-stu-id="51450-130"><strong>ConferenceStartTime</strong></span></span></p></td>
<td><p><span data-ttu-id="51450-131">datetime</span><span class="sxs-lookup"><span data-stu-id="51450-131">datetime</span></span></p></td>
<td><p><span data-ttu-id="51450-132">Время начала конференции.</span><span class="sxs-lookup"><span data-stu-id="51450-132">Starting time for the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="51450-133"><strong>конференцеендтиме</strong></span><span class="sxs-lookup"><span data-stu-id="51450-133"><strong>ConferenceEndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="51450-134">datetime</span><span class="sxs-lookup"><span data-stu-id="51450-134">datetime</span></span></p></td>
<td><p><span data-ttu-id="51450-135">Время окончания конференции.</span><span class="sxs-lookup"><span data-stu-id="51450-135">Ending time for the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="51450-136"><strong>организерури</strong></span><span class="sxs-lookup"><span data-stu-id="51450-136"><strong>OrganizerUri</strong></span></span></p></td>
<td><p><span data-ttu-id="51450-137">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="51450-137">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="51450-138">URI пользователя, организовавшего конференцию.</span><span class="sxs-lookup"><span data-stu-id="51450-138">URI of the user who organized the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="51450-139"><strong>организертипе</strong></span><span class="sxs-lookup"><span data-stu-id="51450-139"><strong>OrganizerType</strong></span></span></p></td>
<td><p><span data-ttu-id="51450-140">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="51450-140">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="51450-141">Тип URI пользователя, организовавшего конференцию.</span><span class="sxs-lookup"><span data-stu-id="51450-141">Type of URI of the user who organized the conference.</span></span> <span data-ttu-id="51450-142">Дополнительные сведения см. <a href="lync-server-2013-uritypes-table.md">в таблице таблица uritypes в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="51450-142">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="51450-143"><strong>организертенант</strong></span><span class="sxs-lookup"><span data-stu-id="51450-143"><strong>OrganizerTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="51450-144">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="51450-144">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="51450-145">Клиент пользователя, организовавшего конференцию.</span><span class="sxs-lookup"><span data-stu-id="51450-145">Tenant of the user who organized the conference.</span></span> <span data-ttu-id="51450-146">Дополнительные сведения см. <a href="lync-server-2013-tenants-table.md">в таблице клиентов в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="51450-146">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="51450-147"><strong>Ресурсов</strong></span><span class="sxs-lookup"><span data-stu-id="51450-147"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="51450-148">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="51450-148">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="51450-149">Полное доменное имя пула, в котором размещена конференция.</span><span class="sxs-lookup"><span data-stu-id="51450-149">Fully qualified domain name of the pool that hosted the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="51450-150"><strong>Флаг</strong></span><span class="sxs-lookup"><span data-stu-id="51450-150"><strong>Flag</strong></span></span></p></td>
<td><p><span data-ttu-id="51450-151">smallint</span><span class="sxs-lookup"><span data-stu-id="51450-151">smallint</span></span></p></td>
<td><p><span data-ttu-id="51450-p108">Битовая маска, содержащая атрибуты конференции. Возможные значения:</span><span class="sxs-lookup"><span data-stu-id="51450-p108">Bit mask that contains Conference Attributes. Possible values are:</span></span></p>
<p><span data-ttu-id="51450-154">0X01 – искусственная транзакция</span><span class="sxs-lookup"><span data-stu-id="51450-154">0X01 – Synthetic Transaction</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

