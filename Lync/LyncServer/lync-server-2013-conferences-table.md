---
title: 'Lync Server 2013: таблица Conferences'
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
ms.openlocfilehash: 0c5464d3161a52a31fddb1322c82181d6e7a97fe
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756403"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conferences-table-in-lync-server-2013"></a><span data-ttu-id="cd22d-102">Таблица Conferences в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cd22d-102">Conferences table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cd22d-103">_**Тема последнего изменения:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="cd22d-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="cd22d-104">Каждая запись в этой таблице включает сведения о звонках для одной конференции.</span><span class="sxs-lookup"><span data-stu-id="cd22d-104">Each record in this table contains call details about one conference.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="cd22d-105">Столбец</span><span class="sxs-lookup"><span data-stu-id="cd22d-105">Column</span></span></th>
<th><span data-ttu-id="cd22d-106">Тип данных</span><span class="sxs-lookup"><span data-stu-id="cd22d-106">Data Type</span></span></th>
<th><span data-ttu-id="cd22d-107">Ключ/индекс</span><span class="sxs-lookup"><span data-stu-id="cd22d-107">Key/Index</span></span></th>
<th><span data-ttu-id="cd22d-108">Сведения</span><span class="sxs-lookup"><span data-stu-id="cd22d-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cd22d-109"><strong>сессионидтиме</strong></span><span class="sxs-lookup"><span data-stu-id="cd22d-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="cd22d-110">datetime</span><span class="sxs-lookup"><span data-stu-id="cd22d-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="cd22d-111">Primary</span><span class="sxs-lookup"><span data-stu-id="cd22d-111">Primary</span></span></p></td>
<td><p><span data-ttu-id="cd22d-112">Время, в течение которого запрос на конференцию был собран агентом CDR.</span><span class="sxs-lookup"><span data-stu-id="cd22d-112">Time that the conference request was captured by the CDR agent.</span></span> <span data-ttu-id="cd22d-113">Используется только в качестве первичного ключа для уникальной идентификации экземпляра Конференции.</span><span class="sxs-lookup"><span data-stu-id="cd22d-113">Used only as a primary key to uniquely identify a conference instance.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cd22d-114"><strong>сессионидсек</strong></span><span class="sxs-lookup"><span data-stu-id="cd22d-114"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="cd22d-115">целое</span><span class="sxs-lookup"><span data-stu-id="cd22d-115">int</span></span></p></td>
<td><p><span data-ttu-id="cd22d-116">Primary</span><span class="sxs-lookup"><span data-stu-id="cd22d-116">Primary</span></span></p></td>
<td><p><span data-ttu-id="cd22d-117">ИДЕНТИФИКАЦИОНный номер для идентификации сеанса.</span><span class="sxs-lookup"><span data-stu-id="cd22d-117">ID number to identify the session.</span></span> <span data-ttu-id="cd22d-118">Используется в сочетании с <strong>сессионидтиме</strong> для уникальной идентификации экземпляра Конференции.</span><span class="sxs-lookup"><span data-stu-id="cd22d-118">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a conference instance.</span></span> *</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cd22d-119"><strong>конференцеуриид</strong></span><span class="sxs-lookup"><span data-stu-id="cd22d-119"><strong>ConferenceUriId</strong></span></span></p></td>
<td><p><span data-ttu-id="cd22d-120">целое</span><span class="sxs-lookup"><span data-stu-id="cd22d-120">int</span></span></p></td>
<td><p><span data-ttu-id="cd22d-121">Другом</span><span class="sxs-lookup"><span data-stu-id="cd22d-121">Foreign</span></span></p></td>
<td><p><span data-ttu-id="cd22d-122">Универсальный код ресурса (URI) Конференции.</span><span class="sxs-lookup"><span data-stu-id="cd22d-122">Conference URI.</span></span> <span data-ttu-id="cd22d-123">Для получения дополнительных сведений ознакомьтесь с <a href="lync-server-2013-conferenceuris-table.md">таблицей конференцеурис в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="cd22d-123">See the <a href="lync-server-2013-conferenceuris-table.md">ConferenceUris table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cd22d-124"><strong>конфинстанце</strong></span><span class="sxs-lookup"><span data-stu-id="cd22d-124"><strong>ConfInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="cd22d-125">идентификатора</span><span class="sxs-lookup"><span data-stu-id="cd22d-125">uniqueidentifier</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="cd22d-126">Полезен для повторяющихся конференций; Каждый экземпляр повторяющейся Конференции имеет один и тот же <strong>конференцеури</strong>, но у него будет другой <strong>конфинстанце</strong>.</span><span class="sxs-lookup"><span data-stu-id="cd22d-126">Useful for recurring conferences; each instance of a recurring conference has the same <strong>ConferenceUri</strong>, but will have a different <strong>ConfInstance</strong>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cd22d-127"><strong>конференцестарттиме</strong></span><span class="sxs-lookup"><span data-stu-id="cd22d-127"><strong>ConferenceStartTime</strong></span></span></p></td>
<td><p><span data-ttu-id="cd22d-128">datetime</span><span class="sxs-lookup"><span data-stu-id="cd22d-128">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="cd22d-129">Время начала Конференции.</span><span class="sxs-lookup"><span data-stu-id="cd22d-129">Conference start time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cd22d-130"><strong>конференцеендтиме</strong></span><span class="sxs-lookup"><span data-stu-id="cd22d-130"><strong>ConferenceEndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="cd22d-131">datetime</span><span class="sxs-lookup"><span data-stu-id="cd22d-131">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="cd22d-132">Время начала Конференции.</span><span class="sxs-lookup"><span data-stu-id="cd22d-132">Conference start time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cd22d-133"><strong>пулид</strong></span><span class="sxs-lookup"><span data-stu-id="cd22d-133"><strong>PoolId</strong></span></span></p></td>
<td><p><span data-ttu-id="cd22d-134">целое</span><span class="sxs-lookup"><span data-stu-id="cd22d-134">int</span></span></p></td>
<td><p><span data-ttu-id="cd22d-135">Другом</span><span class="sxs-lookup"><span data-stu-id="cd22d-135">Foreign</span></span></p></td>
<td><p><span data-ttu-id="cd22d-136">ИДЕНТИФИКАЦИОНный номер для идентификации пула, в котором собрана конференция.</span><span class="sxs-lookup"><span data-stu-id="cd22d-136">ID number to identify the pool in which the conference was captured.</span></span> <span data-ttu-id="cd22d-137">Для получения дополнительных сведений ознакомьтесь с <a href="lync-server-2013-pools-table.md">таблицей пулы в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="cd22d-137">See the <a href="lync-server-2013-pools-table.md">Pools table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cd22d-138"><strong>организерид</strong></span><span class="sxs-lookup"><span data-stu-id="cd22d-138"><strong>OrganizerId</strong></span></span></p></td>
<td><p><span data-ttu-id="cd22d-139">Типом</span><span class="sxs-lookup"><span data-stu-id="cd22d-139">Int</span></span></p></td>
<td><p><span data-ttu-id="cd22d-140">Другом</span><span class="sxs-lookup"><span data-stu-id="cd22d-140">Foreign</span></span></p></td>
<td><p><span data-ttu-id="cd22d-141">ИДЕНТИФИКАЦИОНный номер для идентификации универсального кода ресурса (URI) организатора данной Конференции.</span><span class="sxs-lookup"><span data-stu-id="cd22d-141">ID number to identify the organizer URI of this conference.</span></span> <span data-ttu-id="cd22d-142">Дополнительные сведения <a href="lync-server-2013-users-table.md">можно найти в таблице Users (пользователи) в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="cd22d-142">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cd22d-143"><strong>Пометка</strong></span><span class="sxs-lookup"><span data-stu-id="cd22d-143"><strong>Flag</strong></span></span></p></td>
<td><p><span data-ttu-id="cd22d-144">smallint</span><span class="sxs-lookup"><span data-stu-id="cd22d-144">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="cd22d-145">Битовая маска, которая включает атрибуты Конференции.</span><span class="sxs-lookup"><span data-stu-id="cd22d-145">A bit mask that contains Conference Attributes.</span></span> <span data-ttu-id="cd22d-146">Возможные значения</span><span class="sxs-lookup"><span data-stu-id="cd22d-146">Possible values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="cd22d-147">0X01</span><span class="sxs-lookup"><span data-stu-id="cd22d-147">0X01</span></span></p></li>
<li><p><span data-ttu-id="cd22d-148">Накопител</span><span class="sxs-lookup"><span data-stu-id="cd22d-148">Synthetic</span></span></p></li>
<li><p><span data-ttu-id="cd22d-149">Транзакции</span><span class="sxs-lookup"><span data-stu-id="cd22d-149">Transaction</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cd22d-150"><strong>Обработка</strong></span><span class="sxs-lookup"><span data-stu-id="cd22d-150"><strong>Processed</strong></span></span></p></td>
<td><p><span data-ttu-id="cd22d-151">бит</span><span class="sxs-lookup"><span data-stu-id="cd22d-151">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="cd22d-152">Внутреннее поле, используемое службой мониторинга.</span><span class="sxs-lookup"><span data-stu-id="cd22d-152">Internal field used by the Monitoring service.</span></span></p>
<p><span data-ttu-id="cd22d-153">Это поле было введено в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="cd22d-153">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="cd22d-154">\*Для большинства сеансов для Сессионидсек будет задано значение 1.</span><span class="sxs-lookup"><span data-stu-id="cd22d-154">\* For most sessions, SessionIdSeq will have the value of 1.</span></span> <span data-ttu-id="cd22d-155">Если два сеанса начинаются в одно и то же время, Сессионидсек для одного из них будет равен 1, а для другого — 2 и т. д.</span><span class="sxs-lookup"><span data-stu-id="cd22d-155">If two sessions start at exactly the same time, the SessionIdSeq for one will be 1, and for the other will be 2, and so on.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

