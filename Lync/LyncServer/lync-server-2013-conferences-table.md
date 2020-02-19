---
title: 'Lync Server 2013: таблица конференций'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Conferences table
ms:assetid: c3da6271-b3c6-4898-894f-10456ec794d0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412964(v=OCS.15)
ms:contentKeyID: 48185340
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e8cbb42d078ccba029ae0cf55c7b1ced803aa94f
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42140592"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="conferences-table-in-lync-server-2013"></a><span data-ttu-id="a4a90-102">Таблица конференций в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a4a90-102">Conferences table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a4a90-103">_**Последнее изменение темы:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="a4a90-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="a4a90-104">Каждая запись в этой таблице содержит сведения о вызовах для одной конференции.</span><span class="sxs-lookup"><span data-stu-id="a4a90-104">Each record in this table contains call details about one conference.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a4a90-105">Столбец</span><span class="sxs-lookup"><span data-stu-id="a4a90-105">Column</span></span></th>
<th><span data-ttu-id="a4a90-106">Тип данных</span><span class="sxs-lookup"><span data-stu-id="a4a90-106">Data Type</span></span></th>
<th><span data-ttu-id="a4a90-107">Ключ или индекс</span><span class="sxs-lookup"><span data-stu-id="a4a90-107">Key/Index</span></span></th>
<th><span data-ttu-id="a4a90-108">Сведения</span><span class="sxs-lookup"><span data-stu-id="a4a90-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a4a90-109"><strong>сессионидтиме</strong></span><span class="sxs-lookup"><span data-stu-id="a4a90-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="a4a90-110">datetime</span><span class="sxs-lookup"><span data-stu-id="a4a90-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="a4a90-111">Primary</span><span class="sxs-lookup"><span data-stu-id="a4a90-111">Primary</span></span></p></td>
<td><p><span data-ttu-id="a4a90-112">Время, в течение которого запрос на конференцию был захвачен агентом CDR.</span><span class="sxs-lookup"><span data-stu-id="a4a90-112">Time that the conference request was captured by the CDR agent.</span></span> <span data-ttu-id="a4a90-113">Используется только в качестве первичного ключа для уникальной идентификации экземпляра Конференции.</span><span class="sxs-lookup"><span data-stu-id="a4a90-113">Used only as a primary key to uniquely identify a conference instance.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a4a90-114"><strong>сессионидсек</strong></span><span class="sxs-lookup"><span data-stu-id="a4a90-114"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="a4a90-115">int</span><span class="sxs-lookup"><span data-stu-id="a4a90-115">int</span></span></p></td>
<td><p><span data-ttu-id="a4a90-116">Primary</span><span class="sxs-lookup"><span data-stu-id="a4a90-116">Primary</span></span></p></td>
<td><p><span data-ttu-id="a4a90-117">Идентификатор сеанса.</span><span class="sxs-lookup"><span data-stu-id="a4a90-117">ID number to identify the session.</span></span> <span data-ttu-id="a4a90-118">Используется совместно с <strong>сессионидтиме</strong> для уникальной идентификации экземпляра Конференции.</span><span class="sxs-lookup"><span data-stu-id="a4a90-118">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a conference instance.</span></span> *</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a4a90-119"><strong>конференцеуриид</strong></span><span class="sxs-lookup"><span data-stu-id="a4a90-119"><strong>ConferenceUriId</strong></span></span></p></td>
<td><p><span data-ttu-id="a4a90-120">int</span><span class="sxs-lookup"><span data-stu-id="a4a90-120">int</span></span></p></td>
<td><p><span data-ttu-id="a4a90-121">Правительства</span><span class="sxs-lookup"><span data-stu-id="a4a90-121">Foreign</span></span></p></td>
<td><p><span data-ttu-id="a4a90-122">URI конференции.</span><span class="sxs-lookup"><span data-stu-id="a4a90-122">Conference URI.</span></span> <span data-ttu-id="a4a90-123">Дополнительные сведения см. <a href="lync-server-2013-conferenceuris-table.md">в таблице таблица conferenceuris в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="a4a90-123">See the <a href="lync-server-2013-conferenceuris-table.md">ConferenceUris table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a4a90-124"><strong>конфинстанце</strong></span><span class="sxs-lookup"><span data-stu-id="a4a90-124"><strong>ConfInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="a4a90-125">идентификатора</span><span class="sxs-lookup"><span data-stu-id="a4a90-125">uniqueidentifier</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="a4a90-126">Полезен для повторяющихся конференций; Каждый экземпляр повторяющейся Конференции имеет один и тот же <strong>конференцеури</strong>, но у него будет другой <strong>конфинстанце</strong>.</span><span class="sxs-lookup"><span data-stu-id="a4a90-126">Useful for recurring conferences; each instance of a recurring conference has the same <strong>ConferenceUri</strong>, but will have a different <strong>ConfInstance</strong>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a4a90-127"><strong>конференцестарттиме</strong></span><span class="sxs-lookup"><span data-stu-id="a4a90-127"><strong>ConferenceStartTime</strong></span></span></p></td>
<td><p><span data-ttu-id="a4a90-128">datetime</span><span class="sxs-lookup"><span data-stu-id="a4a90-128">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="a4a90-129">Время начала Конференции.</span><span class="sxs-lookup"><span data-stu-id="a4a90-129">Conference start time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a4a90-130"><strong>конференцеендтиме</strong></span><span class="sxs-lookup"><span data-stu-id="a4a90-130"><strong>ConferenceEndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="a4a90-131">datetime</span><span class="sxs-lookup"><span data-stu-id="a4a90-131">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="a4a90-132">Время начала Конференции.</span><span class="sxs-lookup"><span data-stu-id="a4a90-132">Conference start time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a4a90-133"><strong>пулид</strong></span><span class="sxs-lookup"><span data-stu-id="a4a90-133"><strong>PoolId</strong></span></span></p></td>
<td><p><span data-ttu-id="a4a90-134">int</span><span class="sxs-lookup"><span data-stu-id="a4a90-134">int</span></span></p></td>
<td><p><span data-ttu-id="a4a90-135">Правительства</span><span class="sxs-lookup"><span data-stu-id="a4a90-135">Foreign</span></span></p></td>
<td><p><span data-ttu-id="a4a90-136">ИДЕНТИФИКАЦИОНный номер для идентификации пула, в котором была собрана конференция.</span><span class="sxs-lookup"><span data-stu-id="a4a90-136">ID number to identify the pool in which the conference was captured.</span></span> <span data-ttu-id="a4a90-137">Дополнительные сведения см. <a href="lync-server-2013-pools-table.md">в таблице Pools в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="a4a90-137">See the <a href="lync-server-2013-pools-table.md">Pools table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a4a90-138"><strong>организерид</strong></span><span class="sxs-lookup"><span data-stu-id="a4a90-138"><strong>OrganizerId</strong></span></span></p></td>
<td><p><span data-ttu-id="a4a90-139">Целое</span><span class="sxs-lookup"><span data-stu-id="a4a90-139">Int</span></span></p></td>
<td><p><span data-ttu-id="a4a90-140">Правительства</span><span class="sxs-lookup"><span data-stu-id="a4a90-140">Foreign</span></span></p></td>
<td><p><span data-ttu-id="a4a90-141">ИДЕНТИФИКАЦИОНный номер для идентификации универсального кода ресурса (URI) организатора этой Конференции.</span><span class="sxs-lookup"><span data-stu-id="a4a90-141">ID number to identify the organizer URI of this conference.</span></span> <span data-ttu-id="a4a90-142">Дополнительные сведения см. <a href="lync-server-2013-users-table.md">в таблице "Пользователи" в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="a4a90-142">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a4a90-143"><strong>Флаг</strong></span><span class="sxs-lookup"><span data-stu-id="a4a90-143"><strong>Flag</strong></span></span></p></td>
<td><p><span data-ttu-id="a4a90-144">smallint</span><span class="sxs-lookup"><span data-stu-id="a4a90-144">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a4a90-145">Битовая маска, содержащая атрибуты Конференции.</span><span class="sxs-lookup"><span data-stu-id="a4a90-145">A bit mask that contains Conference Attributes.</span></span> <span data-ttu-id="a4a90-146">Возможные значения:</span><span class="sxs-lookup"><span data-stu-id="a4a90-146">Possible values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="a4a90-147">0X01</span><span class="sxs-lookup"><span data-stu-id="a4a90-147">0X01</span></span></p></li>
<li><p><span data-ttu-id="a4a90-148">Виртуальный</span><span class="sxs-lookup"><span data-stu-id="a4a90-148">Synthetic</span></span></p></li>
<li><p><span data-ttu-id="a4a90-149">Транзакция</span><span class="sxs-lookup"><span data-stu-id="a4a90-149">Transaction</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a4a90-150"><strong>Обработать</strong></span><span class="sxs-lookup"><span data-stu-id="a4a90-150"><strong>Processed</strong></span></span></p></td>
<td><p><span data-ttu-id="a4a90-151">Битовая</span><span class="sxs-lookup"><span data-stu-id="a4a90-151">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a4a90-152">Внутреннее поле, используемое службой мониторинга.</span><span class="sxs-lookup"><span data-stu-id="a4a90-152">Internal field used by the Monitoring service.</span></span></p>
<p><span data-ttu-id="a4a90-153">Это поле было введено в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a4a90-153">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="a4a90-154">\*Для большинства сеансов Сессионидсек будет иметь значение 1.</span><span class="sxs-lookup"><span data-stu-id="a4a90-154">\* For most sessions, SessionIdSeq will have the value of 1.</span></span> <span data-ttu-id="a4a90-155">Если два сеанса начинаются в одно и то же время, то Сессионидсек для одного из них будет иметь значение 1, а другое — 2 и т. д.</span><span class="sxs-lookup"><span data-stu-id="a4a90-155">If two sessions start at exactly the same time, the SessionIdSeq for one will be 1, and for the other will be 2, and so on.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

