---
title: 'Lync Server 2013: таблица конференций'
description: 'Lync Server 2013: таблица конференций.'
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
ms.openlocfilehash: 1e0d8c61e795dc0c8f9843b871d7e4efd1bec571
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48561605"
---
# <a name="conferences-table-in-lync-server-2013"></a><span data-ttu-id="8f010-103">Таблица конференций в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8f010-103">Conferences table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8f010-104">_**Последнее изменение темы:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="8f010-104">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="8f010-105">Каждая запись в этой таблице содержит сведения о вызовах для одной конференции.</span><span class="sxs-lookup"><span data-stu-id="8f010-105">Each record in this table contains call details about one conference.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8f010-106">Столбец</span><span class="sxs-lookup"><span data-stu-id="8f010-106">Column</span></span></th>
<th><span data-ttu-id="8f010-107">Тип данных</span><span class="sxs-lookup"><span data-stu-id="8f010-107">Data Type</span></span></th>
<th><span data-ttu-id="8f010-108">Ключ или индекс</span><span class="sxs-lookup"><span data-stu-id="8f010-108">Key/Index</span></span></th>
<th><span data-ttu-id="8f010-109">Сведения</span><span class="sxs-lookup"><span data-stu-id="8f010-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8f010-110"><strong>сессионидтиме</strong></span><span class="sxs-lookup"><span data-stu-id="8f010-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="8f010-111">datetime</span><span class="sxs-lookup"><span data-stu-id="8f010-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="8f010-112">Primary</span><span class="sxs-lookup"><span data-stu-id="8f010-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="8f010-113">Время, в течение которого запрос на конференцию был захвачен агентом CDR.</span><span class="sxs-lookup"><span data-stu-id="8f010-113">Time that the conference request was captured by the CDR agent.</span></span> <span data-ttu-id="8f010-114">Используется только в качестве первичного ключа для уникальной идентификации экземпляра Конференции.</span><span class="sxs-lookup"><span data-stu-id="8f010-114">Used only as a primary key to uniquely identify a conference instance.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8f010-115"><strong>сессионидсек</strong></span><span class="sxs-lookup"><span data-stu-id="8f010-115"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="8f010-116">int</span><span class="sxs-lookup"><span data-stu-id="8f010-116">int</span></span></p></td>
<td><p><span data-ttu-id="8f010-117">Primary</span><span class="sxs-lookup"><span data-stu-id="8f010-117">Primary</span></span></p></td>
<td><p><span data-ttu-id="8f010-118">Идентификатор сеанса.</span><span class="sxs-lookup"><span data-stu-id="8f010-118">ID number to identify the session.</span></span> <span data-ttu-id="8f010-119">Используется совместно с <strong>сессионидтиме</strong> для уникальной идентификации экземпляра Конференции.</span><span class="sxs-lookup"><span data-stu-id="8f010-119">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a conference instance.</span></span> *</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8f010-120"><strong>конференцеуриид</strong></span><span class="sxs-lookup"><span data-stu-id="8f010-120"><strong>ConferenceUriId</strong></span></span></p></td>
<td><p><span data-ttu-id="8f010-121">int</span><span class="sxs-lookup"><span data-stu-id="8f010-121">int</span></span></p></td>
<td><p><span data-ttu-id="8f010-122">Правительства</span><span class="sxs-lookup"><span data-stu-id="8f010-122">Foreign</span></span></p></td>
<td><p><span data-ttu-id="8f010-123">URI конференции.</span><span class="sxs-lookup"><span data-stu-id="8f010-123">Conference URI.</span></span> <span data-ttu-id="8f010-124">Дополнительные сведения см. <a href="lync-server-2013-conferenceuris-table.md">в таблице таблица conferenceuris в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="8f010-124">See the <a href="lync-server-2013-conferenceuris-table.md">ConferenceUris table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8f010-125"><strong>конфинстанце</strong></span><span class="sxs-lookup"><span data-stu-id="8f010-125"><strong>ConfInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="8f010-126">идентификатора</span><span class="sxs-lookup"><span data-stu-id="8f010-126">uniqueidentifier</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="8f010-127">Полезен для повторяющихся конференций; Каждый экземпляр повторяющейся Конференции имеет один и тот же <strong>конференцеури</strong>, но у него будет другой <strong>конфинстанце</strong>.</span><span class="sxs-lookup"><span data-stu-id="8f010-127">Useful for recurring conferences; each instance of a recurring conference has the same <strong>ConferenceUri</strong>, but will have a different <strong>ConfInstance</strong>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8f010-128"><strong>конференцестарттиме</strong></span><span class="sxs-lookup"><span data-stu-id="8f010-128"><strong>ConferenceStartTime</strong></span></span></p></td>
<td><p><span data-ttu-id="8f010-129">datetime</span><span class="sxs-lookup"><span data-stu-id="8f010-129">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="8f010-130">Время начала Конференции.</span><span class="sxs-lookup"><span data-stu-id="8f010-130">Conference start time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8f010-131"><strong>конференцеендтиме</strong></span><span class="sxs-lookup"><span data-stu-id="8f010-131"><strong>ConferenceEndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="8f010-132">datetime</span><span class="sxs-lookup"><span data-stu-id="8f010-132">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="8f010-133">Время начала Конференции.</span><span class="sxs-lookup"><span data-stu-id="8f010-133">Conference start time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8f010-134"><strong>пулид</strong></span><span class="sxs-lookup"><span data-stu-id="8f010-134"><strong>PoolId</strong></span></span></p></td>
<td><p><span data-ttu-id="8f010-135">int</span><span class="sxs-lookup"><span data-stu-id="8f010-135">int</span></span></p></td>
<td><p><span data-ttu-id="8f010-136">Правительства</span><span class="sxs-lookup"><span data-stu-id="8f010-136">Foreign</span></span></p></td>
<td><p><span data-ttu-id="8f010-137">ИДЕНТИФИКАЦИОНный номер для идентификации пула, в котором была собрана конференция.</span><span class="sxs-lookup"><span data-stu-id="8f010-137">ID number to identify the pool in which the conference was captured.</span></span> <span data-ttu-id="8f010-138">Дополнительные сведения см. <a href="lync-server-2013-pools-table.md">в таблице Pools в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="8f010-138">See the <a href="lync-server-2013-pools-table.md">Pools table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8f010-139"><strong>организерид</strong></span><span class="sxs-lookup"><span data-stu-id="8f010-139"><strong>OrganizerId</strong></span></span></p></td>
<td><p><span data-ttu-id="8f010-140">Целое</span><span class="sxs-lookup"><span data-stu-id="8f010-140">Int</span></span></p></td>
<td><p><span data-ttu-id="8f010-141">Правительства</span><span class="sxs-lookup"><span data-stu-id="8f010-141">Foreign</span></span></p></td>
<td><p><span data-ttu-id="8f010-142">ИДЕНТИФИКАЦИОНный номер для идентификации универсального кода ресурса (URI) организатора этой Конференции.</span><span class="sxs-lookup"><span data-stu-id="8f010-142">ID number to identify the organizer URI of this conference.</span></span> <span data-ttu-id="8f010-143">Дополнительные сведения см. <a href="lync-server-2013-users-table.md">в таблице "Пользователи" в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="8f010-143">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8f010-144"><strong>Флаг</strong></span><span class="sxs-lookup"><span data-stu-id="8f010-144"><strong>Flag</strong></span></span></p></td>
<td><p><span data-ttu-id="8f010-145">smallint</span><span class="sxs-lookup"><span data-stu-id="8f010-145">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8f010-146">Битовая маска, содержащая атрибуты Конференции.</span><span class="sxs-lookup"><span data-stu-id="8f010-146">A bit mask that contains Conference Attributes.</span></span> <span data-ttu-id="8f010-147">Возможные значения:</span><span class="sxs-lookup"><span data-stu-id="8f010-147">Possible values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="8f010-148">0X01</span><span class="sxs-lookup"><span data-stu-id="8f010-148">0X01</span></span></p></li>
<li><p><span data-ttu-id="8f010-149">Виртуальный</span><span class="sxs-lookup"><span data-stu-id="8f010-149">Synthetic</span></span></p></li>
<li><p><span data-ttu-id="8f010-150">Транзакция</span><span class="sxs-lookup"><span data-stu-id="8f010-150">Transaction</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8f010-151"><strong>Обработать</strong></span><span class="sxs-lookup"><span data-stu-id="8f010-151"><strong>Processed</strong></span></span></p></td>
<td><p><span data-ttu-id="8f010-152">Битовая</span><span class="sxs-lookup"><span data-stu-id="8f010-152">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8f010-153">Внутреннее поле, используемое службой мониторинга.</span><span class="sxs-lookup"><span data-stu-id="8f010-153">Internal field used by the Monitoring service.</span></span></p>
<p><span data-ttu-id="8f010-154">Это поле было введено в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8f010-154">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="8f010-155">\* Для большинства сеансов Сессионидсек будет иметь значение 1.</span><span class="sxs-lookup"><span data-stu-id="8f010-155">\* For most sessions, SessionIdSeq will have the value of 1.</span></span> <span data-ttu-id="8f010-156">Если два сеанса начинаются в одно и то же время, то Сессионидсек для одного из них будет иметь значение 1, а другое — 2 и т. д.</span><span class="sxs-lookup"><span data-stu-id="8f010-156">If two sessions start at exactly the same time, the SessionIdSeq for one will be 1, and for the other will be 2, and so on.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

