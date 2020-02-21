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
ms.openlocfilehash: 6f01d7fb0a2cb0526d4d6954b303a7cf78bb9333
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42190242"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="conferences-view-in-lync-server-2013"></a><span data-ttu-id="f6cf2-102">Представление конференций в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f6cf2-102">Conferences view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f6cf2-103">_**Последнее изменение темы:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="f6cf2-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="f6cf2-104">В представлении конференций хранятся сведения о конференциях.</span><span class="sxs-lookup"><span data-stu-id="f6cf2-104">The Conferences View stores information about the conferences.</span></span> <span data-ttu-id="f6cf2-105">Это представление было представлено в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f6cf2-105">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f6cf2-106">Столбец</span><span class="sxs-lookup"><span data-stu-id="f6cf2-106">Column</span></span></th>
<th><span data-ttu-id="f6cf2-107">Тип данных</span><span class="sxs-lookup"><span data-stu-id="f6cf2-107">Data Type</span></span></th>
<th><span data-ttu-id="f6cf2-108">Сведения</span><span class="sxs-lookup"><span data-stu-id="f6cf2-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f6cf2-109"><strong>сессионидтиме</strong></span><span class="sxs-lookup"><span data-stu-id="f6cf2-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="f6cf2-110">datetime</span><span class="sxs-lookup"><span data-stu-id="f6cf2-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="f6cf2-111">Время запроса сеанса.</span><span class="sxs-lookup"><span data-stu-id="f6cf2-111">Time of session request.</span></span> <span data-ttu-id="f6cf2-112">Используется вместе с параметром SessionIdSeq для уникального определения сеанса.</span><span class="sxs-lookup"><span data-stu-id="f6cf2-112">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="f6cf2-113">Дополнительные сведения см. <a href="lync-server-2013-dialogs-table.md">в таблице диалоговых окон в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="f6cf2-113">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f6cf2-114"><strong>сессионидсек</strong></span><span class="sxs-lookup"><span data-stu-id="f6cf2-114"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="f6cf2-115">int</span><span class="sxs-lookup"><span data-stu-id="f6cf2-115">int</span></span></p></td>
<td><p><span data-ttu-id="f6cf2-116">Идентификационный номер для идентификации сеанса.</span><span class="sxs-lookup"><span data-stu-id="f6cf2-116">ID number to identify the session.</span></span> <span data-ttu-id="f6cf2-117">Используется совместно с параметром SessionIdTime для уникальной идентификации сеанса.</span><span class="sxs-lookup"><span data-stu-id="f6cf2-117">Used in conjunction with SessionIdTime to uniquely identify a session.</span></span> <span data-ttu-id="f6cf2-118">Дополнительные сведения см. <a href="lync-server-2013-dialogs-table.md">в таблице диалоговых окон в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="f6cf2-118">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f6cf2-119"><strong>конференцеури</strong></span><span class="sxs-lookup"><span data-stu-id="f6cf2-119"><strong>ConferenceUri</strong></span></span></p></td>
<td><p><span data-ttu-id="f6cf2-120">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="f6cf2-120">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="f6cf2-121">URI конференции.</span><span class="sxs-lookup"><span data-stu-id="f6cf2-121">URI for the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f6cf2-122"><strong>конференцеуритипе</strong></span><span class="sxs-lookup"><span data-stu-id="f6cf2-122"><strong>ConferenceUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="f6cf2-123">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="f6cf2-123">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="f6cf2-124">Тип URI конференции.</span><span class="sxs-lookup"><span data-stu-id="f6cf2-124">Type of the conference URI.</span></span> <span data-ttu-id="f6cf2-125">Дополнительные сведения см. <a href="lync-server-2013-uritypes-table.md">в таблице таблица uritypes в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="f6cf2-125">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f6cf2-126"><strong>конфинстанце</strong></span><span class="sxs-lookup"><span data-stu-id="f6cf2-126"><strong>ConfInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="f6cf2-127">идентификатора</span><span class="sxs-lookup"><span data-stu-id="f6cf2-127">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="f6cf2-p105">Используется для повторяющихся конференций. Все экземпляры повторяющейся конференции имеют один и тот же ConferenceUri, но разные значения ConfInstance.</span><span class="sxs-lookup"><span data-stu-id="f6cf2-p105">Used for recurring conferences. Each instance of a recurring conference has the same ConferenceUri but a different ConfInstance.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f6cf2-130"><strong>конференцестарттиме</strong></span><span class="sxs-lookup"><span data-stu-id="f6cf2-130"><strong>ConferenceStartTime</strong></span></span></p></td>
<td><p><span data-ttu-id="f6cf2-131">datetime</span><span class="sxs-lookup"><span data-stu-id="f6cf2-131">datetime</span></span></p></td>
<td><p><span data-ttu-id="f6cf2-132">Время начала конференции.</span><span class="sxs-lookup"><span data-stu-id="f6cf2-132">Starting time for the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f6cf2-133"><strong>конференцеендтиме</strong></span><span class="sxs-lookup"><span data-stu-id="f6cf2-133"><strong>ConferenceEndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="f6cf2-134">datetime</span><span class="sxs-lookup"><span data-stu-id="f6cf2-134">datetime</span></span></p></td>
<td><p><span data-ttu-id="f6cf2-135">Время окончания конференции.</span><span class="sxs-lookup"><span data-stu-id="f6cf2-135">Ending time for the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f6cf2-136"><strong>организерури</strong></span><span class="sxs-lookup"><span data-stu-id="f6cf2-136"><strong>OrganizerUri</strong></span></span></p></td>
<td><p><span data-ttu-id="f6cf2-137">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="f6cf2-137">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="f6cf2-138">URI пользователя, организовавшего конференцию.</span><span class="sxs-lookup"><span data-stu-id="f6cf2-138">URI of the user who organized the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f6cf2-139"><strong>организертипе</strong></span><span class="sxs-lookup"><span data-stu-id="f6cf2-139"><strong>OrganizerType</strong></span></span></p></td>
<td><p><span data-ttu-id="f6cf2-140">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="f6cf2-140">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="f6cf2-141">Тип URI пользователя, организовавшего конференцию.</span><span class="sxs-lookup"><span data-stu-id="f6cf2-141">Type of URI of the user who organized the conference.</span></span> <span data-ttu-id="f6cf2-142">Дополнительные сведения см. <a href="lync-server-2013-uritypes-table.md">в таблице таблица uritypes в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="f6cf2-142">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f6cf2-143"><strong>организертенант</strong></span><span class="sxs-lookup"><span data-stu-id="f6cf2-143"><strong>OrganizerTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="f6cf2-144">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="f6cf2-144">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="f6cf2-145">Клиент пользователя, организовавшего конференцию.</span><span class="sxs-lookup"><span data-stu-id="f6cf2-145">Tenant of the user who organized the conference.</span></span> <span data-ttu-id="f6cf2-146">Дополнительные сведения см. <a href="lync-server-2013-tenants-table.md">в таблице клиентов в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="f6cf2-146">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f6cf2-147"><strong>Ресурсов</strong></span><span class="sxs-lookup"><span data-stu-id="f6cf2-147"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="f6cf2-148">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="f6cf2-148">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="f6cf2-149">Полное доменное имя пула, в котором размещена конференция.</span><span class="sxs-lookup"><span data-stu-id="f6cf2-149">Fully qualified domain name of the pool that hosted the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f6cf2-150"><strong>Флаг</strong></span><span class="sxs-lookup"><span data-stu-id="f6cf2-150"><strong>Flag</strong></span></span></p></td>
<td><p><span data-ttu-id="f6cf2-151">smallint</span><span class="sxs-lookup"><span data-stu-id="f6cf2-151">smallint</span></span></p></td>
<td><p><span data-ttu-id="f6cf2-p108">Битовая маска, содержащая атрибуты конференции. Возможные значения:</span><span class="sxs-lookup"><span data-stu-id="f6cf2-p108">Bit mask that contains Conference Attributes. Possible values are:</span></span></p>
<p><span data-ttu-id="f6cf2-154">0X01 – искусственная транзакция</span><span class="sxs-lookup"><span data-stu-id="f6cf2-154">0X01 – Synthetic Transaction</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

