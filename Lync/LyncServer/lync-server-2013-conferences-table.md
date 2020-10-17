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
ms.openlocfilehash: ef5e8811ad4b0adaccd8964e2f0bca718ca531e2
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48529266"
---
# <a name="conferences-table-in-lync-server-2013"></a><span data-ttu-id="b14c1-102">Таблица конференций в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b14c1-102">Conferences table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b14c1-103">_**Последнее изменение темы:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="b14c1-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="b14c1-104">Каждая запись в этой таблице содержит сведения о вызовах для одной конференции.</span><span class="sxs-lookup"><span data-stu-id="b14c1-104">Each record in this table contains call details about one conference.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b14c1-105">Столбец</span><span class="sxs-lookup"><span data-stu-id="b14c1-105">Column</span></span></th>
<th><span data-ttu-id="b14c1-106">Тип данных</span><span class="sxs-lookup"><span data-stu-id="b14c1-106">Data Type</span></span></th>
<th><span data-ttu-id="b14c1-107">Ключ или индекс</span><span class="sxs-lookup"><span data-stu-id="b14c1-107">Key/Index</span></span></th>
<th><span data-ttu-id="b14c1-108">Сведения</span><span class="sxs-lookup"><span data-stu-id="b14c1-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b14c1-109"><strong>сессионидтиме</strong></span><span class="sxs-lookup"><span data-stu-id="b14c1-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="b14c1-110">datetime</span><span class="sxs-lookup"><span data-stu-id="b14c1-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="b14c1-111">Primary</span><span class="sxs-lookup"><span data-stu-id="b14c1-111">Primary</span></span></p></td>
<td><p><span data-ttu-id="b14c1-112">Время, в течение которого запрос на конференцию был захвачен агентом CDR.</span><span class="sxs-lookup"><span data-stu-id="b14c1-112">Time that the conference request was captured by the CDR agent.</span></span> <span data-ttu-id="b14c1-113">Используется только в качестве первичного ключа для уникальной идентификации экземпляра Конференции.</span><span class="sxs-lookup"><span data-stu-id="b14c1-113">Used only as a primary key to uniquely identify a conference instance.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b14c1-114"><strong>сессионидсек</strong></span><span class="sxs-lookup"><span data-stu-id="b14c1-114"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="b14c1-115">int</span><span class="sxs-lookup"><span data-stu-id="b14c1-115">int</span></span></p></td>
<td><p><span data-ttu-id="b14c1-116">Primary</span><span class="sxs-lookup"><span data-stu-id="b14c1-116">Primary</span></span></p></td>
<td><p><span data-ttu-id="b14c1-117">Идентификатор сеанса.</span><span class="sxs-lookup"><span data-stu-id="b14c1-117">ID number to identify the session.</span></span> <span data-ttu-id="b14c1-118">Используется совместно с <strong>сессионидтиме</strong> для уникальной идентификации экземпляра Конференции.</span><span class="sxs-lookup"><span data-stu-id="b14c1-118">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a conference instance.</span></span> *</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b14c1-119"><strong>конференцеуриид</strong></span><span class="sxs-lookup"><span data-stu-id="b14c1-119"><strong>ConferenceUriId</strong></span></span></p></td>
<td><p><span data-ttu-id="b14c1-120">int</span><span class="sxs-lookup"><span data-stu-id="b14c1-120">int</span></span></p></td>
<td><p><span data-ttu-id="b14c1-121">Правительства</span><span class="sxs-lookup"><span data-stu-id="b14c1-121">Foreign</span></span></p></td>
<td><p><span data-ttu-id="b14c1-122">URI конференции.</span><span class="sxs-lookup"><span data-stu-id="b14c1-122">Conference URI.</span></span> <span data-ttu-id="b14c1-123">Дополнительные сведения см. <a href="lync-server-2013-conferenceuris-table.md">в таблице таблица conferenceuris в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="b14c1-123">See the <a href="lync-server-2013-conferenceuris-table.md">ConferenceUris table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b14c1-124"><strong>конфинстанце</strong></span><span class="sxs-lookup"><span data-stu-id="b14c1-124"><strong>ConfInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="b14c1-125">идентификатора</span><span class="sxs-lookup"><span data-stu-id="b14c1-125">uniqueidentifier</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="b14c1-126">Полезен для повторяющихся конференций; Каждый экземпляр повторяющейся Конференции имеет один и тот же <strong>конференцеури</strong>, но у него будет другой <strong>конфинстанце</strong>.</span><span class="sxs-lookup"><span data-stu-id="b14c1-126">Useful for recurring conferences; each instance of a recurring conference has the same <strong>ConferenceUri</strong>, but will have a different <strong>ConfInstance</strong>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b14c1-127"><strong>конференцестарттиме</strong></span><span class="sxs-lookup"><span data-stu-id="b14c1-127"><strong>ConferenceStartTime</strong></span></span></p></td>
<td><p><span data-ttu-id="b14c1-128">datetime</span><span class="sxs-lookup"><span data-stu-id="b14c1-128">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="b14c1-129">Время начала Конференции.</span><span class="sxs-lookup"><span data-stu-id="b14c1-129">Conference start time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b14c1-130"><strong>конференцеендтиме</strong></span><span class="sxs-lookup"><span data-stu-id="b14c1-130"><strong>ConferenceEndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="b14c1-131">datetime</span><span class="sxs-lookup"><span data-stu-id="b14c1-131">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="b14c1-132">Время начала Конференции.</span><span class="sxs-lookup"><span data-stu-id="b14c1-132">Conference start time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b14c1-133"><strong>пулид</strong></span><span class="sxs-lookup"><span data-stu-id="b14c1-133"><strong>PoolId</strong></span></span></p></td>
<td><p><span data-ttu-id="b14c1-134">int</span><span class="sxs-lookup"><span data-stu-id="b14c1-134">int</span></span></p></td>
<td><p><span data-ttu-id="b14c1-135">Правительства</span><span class="sxs-lookup"><span data-stu-id="b14c1-135">Foreign</span></span></p></td>
<td><p><span data-ttu-id="b14c1-136">ИДЕНТИФИКАЦИОНный номер для идентификации пула, в котором была собрана конференция.</span><span class="sxs-lookup"><span data-stu-id="b14c1-136">ID number to identify the pool in which the conference was captured.</span></span> <span data-ttu-id="b14c1-137">Дополнительные сведения см. <a href="lync-server-2013-pools-table.md">в таблице Pools в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="b14c1-137">See the <a href="lync-server-2013-pools-table.md">Pools table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b14c1-138"><strong>организерид</strong></span><span class="sxs-lookup"><span data-stu-id="b14c1-138"><strong>OrganizerId</strong></span></span></p></td>
<td><p><span data-ttu-id="b14c1-139">Целое</span><span class="sxs-lookup"><span data-stu-id="b14c1-139">Int</span></span></p></td>
<td><p><span data-ttu-id="b14c1-140">Правительства</span><span class="sxs-lookup"><span data-stu-id="b14c1-140">Foreign</span></span></p></td>
<td><p><span data-ttu-id="b14c1-141">ИДЕНТИФИКАЦИОНный номер для идентификации универсального кода ресурса (URI) организатора этой Конференции.</span><span class="sxs-lookup"><span data-stu-id="b14c1-141">ID number to identify the organizer URI of this conference.</span></span> <span data-ttu-id="b14c1-142">Дополнительные сведения см. <a href="lync-server-2013-users-table.md">в таблице "Пользователи" в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="b14c1-142">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b14c1-143"><strong>Флаг</strong></span><span class="sxs-lookup"><span data-stu-id="b14c1-143"><strong>Flag</strong></span></span></p></td>
<td><p><span data-ttu-id="b14c1-144">smallint</span><span class="sxs-lookup"><span data-stu-id="b14c1-144">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b14c1-145">Битовая маска, содержащая атрибуты Конференции.</span><span class="sxs-lookup"><span data-stu-id="b14c1-145">A bit mask that contains Conference Attributes.</span></span> <span data-ttu-id="b14c1-146">Возможные значения:</span><span class="sxs-lookup"><span data-stu-id="b14c1-146">Possible values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="b14c1-147">0X01</span><span class="sxs-lookup"><span data-stu-id="b14c1-147">0X01</span></span></p></li>
<li><p><span data-ttu-id="b14c1-148">Виртуальный</span><span class="sxs-lookup"><span data-stu-id="b14c1-148">Synthetic</span></span></p></li>
<li><p><span data-ttu-id="b14c1-149">Транзакция</span><span class="sxs-lookup"><span data-stu-id="b14c1-149">Transaction</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b14c1-150"><strong>Обработать</strong></span><span class="sxs-lookup"><span data-stu-id="b14c1-150"><strong>Processed</strong></span></span></p></td>
<td><p><span data-ttu-id="b14c1-151">Битовая</span><span class="sxs-lookup"><span data-stu-id="b14c1-151">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b14c1-152">Внутреннее поле, используемое службой мониторинга.</span><span class="sxs-lookup"><span data-stu-id="b14c1-152">Internal field used by the Monitoring service.</span></span></p>
<p><span data-ttu-id="b14c1-153">Это поле было введено в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b14c1-153">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="b14c1-154">\* Для большинства сеансов Сессионидсек будет иметь значение 1.</span><span class="sxs-lookup"><span data-stu-id="b14c1-154">\* For most sessions, SessionIdSeq will have the value of 1.</span></span> <span data-ttu-id="b14c1-155">Если два сеанса начинаются в одно и то же время, то Сессионидсек для одного из них будет иметь значение 1, а другое — 2 и т. д.</span><span class="sxs-lookup"><span data-stu-id="b14c1-155">If two sessions start at exactly the same time, the SessionIdSeq for one will be 1, and for the other will be 2, and so on.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

