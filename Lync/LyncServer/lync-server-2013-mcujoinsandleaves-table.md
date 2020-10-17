---
title: 'Lync Server 2013: таблица таблица mcujoinsandleaves'
description: 'Lync Server 2013: таблица таблица mcujoinsandleaves.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: McuJoinsAndLeaves table
ms:assetid: 4e073366-0b5d-45b4-a3f6-d63dd5fd9f25
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398316(v=OCS.15)
ms:contentKeyID: 48184115
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ee7d9473892ac357dcefd80b0d52382c5dd7d930
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48556505"
---
# <a name="mcujoinsandleaves-table-in-lync-server-2013"></a><span data-ttu-id="61c38-103">Таблица Таблица mcujoinsandleaves в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="61c38-103">McuJoinsAndLeaves table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="61c38-104">_**Последнее изменение темы:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="61c38-104">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="61c38-105">Каждая запись в этой таблице содержит сведения о вызовах для одной комбинации присоединения или выхода пользователя и сервера конференц-связи.</span><span class="sxs-lookup"><span data-stu-id="61c38-105">Each record in this table contains call details about one combination of a user join or leave and conferencing server.</span></span> <span data-ttu-id="61c38-106">Например, если пользователь присоединяется к Конференции, которая включает веб-конференции и аудио-и видеоэлементы, будет создана одна запись для соединения веб-конференций этого пользователя, а для подключения аудио-и видеоконференций пользователя будет создана другая запись.</span><span class="sxs-lookup"><span data-stu-id="61c38-106">For example, if a user joins a conference that includes web conferencing and audio/video elements, one record would be created for that user’s web conferencing join, and another record would be created for the user’s audio/video conferencing join.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="61c38-107">Столбец</span><span class="sxs-lookup"><span data-stu-id="61c38-107">Column</span></span></th>
<th><span data-ttu-id="61c38-108">Тип данных</span><span class="sxs-lookup"><span data-stu-id="61c38-108">Data Type</span></span></th>
<th><span data-ttu-id="61c38-109">Ключ или индекс</span><span class="sxs-lookup"><span data-stu-id="61c38-109">Key/Index</span></span></th>
<th><span data-ttu-id="61c38-110">Сведения</span><span class="sxs-lookup"><span data-stu-id="61c38-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="61c38-111"><strong>сессионидтиме</strong></span><span class="sxs-lookup"><span data-stu-id="61c38-111"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="61c38-112">datetime</span><span class="sxs-lookup"><span data-stu-id="61c38-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="61c38-113">Основной, внешний</span><span class="sxs-lookup"><span data-stu-id="61c38-113">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="61c38-114">Время экземпляра конференции.</span><span class="sxs-lookup"><span data-stu-id="61c38-114">Time of conference instance.</span></span> <span data-ttu-id="61c38-115">Используется совместно с <strong>сессионидсек</strong> для уникальной идентификации экземпляра Конференции.</span><span class="sxs-lookup"><span data-stu-id="61c38-115">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a conference instance.</span></span> <span data-ttu-id="61c38-116">Дополнительные сведения см. <a href="lync-server-2013-conferences-table.md">в таблице конференций в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="61c38-116">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61c38-117"><strong>сессионидсек</strong></span><span class="sxs-lookup"><span data-stu-id="61c38-117"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="61c38-118">int</span><span class="sxs-lookup"><span data-stu-id="61c38-118">int</span></span></p></td>
<td><p><span data-ttu-id="61c38-119">Основной, Внешний</span><span class="sxs-lookup"><span data-stu-id="61c38-119">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="61c38-120">Идентификатор для определения экземпляра конференции.</span><span class="sxs-lookup"><span data-stu-id="61c38-120">ID number to identify the conference instance.</span></span> <span data-ttu-id="61c38-121">Используется совместно с <strong>сессионидтиме</strong> для уникальной идентификации экземпляра Конференции.</span><span class="sxs-lookup"><span data-stu-id="61c38-121">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a conference instance.</span></span> <span data-ttu-id="61c38-122">Дополнительные сведения см. <a href="lync-server-2013-conferences-table.md">в таблице конференций в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="61c38-122">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61c38-123"><strong>UserId</strong></span><span class="sxs-lookup"><span data-stu-id="61c38-123"><strong>UserId</strong></span></span></p></td>
<td><p><span data-ttu-id="61c38-124">int</span><span class="sxs-lookup"><span data-stu-id="61c38-124">int</span></span></p></td>
<td><p><span data-ttu-id="61c38-125">Основной, Внешний</span><span class="sxs-lookup"><span data-stu-id="61c38-125">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="61c38-126">Уникальный номер, идентифицирующий данного пользователя.</span><span class="sxs-lookup"><span data-stu-id="61c38-126">Unique number identifying this user.</span></span> <span data-ttu-id="61c38-127">Дополнительные сведения см. <a href="lync-server-2013-users-table.md">в таблице "Пользователи" в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="61c38-127">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61c38-128"><strong>мкуусеринстанце</strong></span><span class="sxs-lookup"><span data-stu-id="61c38-128"><strong>McuUserInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="61c38-129">int</span><span class="sxs-lookup"><span data-stu-id="61c38-129">int</span></span></p></td>
<td><p><span data-ttu-id="61c38-130">Primary</span><span class="sxs-lookup"><span data-stu-id="61c38-130">Primary</span></span></p></td>
<td><p><span data-ttu-id="61c38-131">Если пользователь вошел в систему на нескольких компьютерах или устройствах одновременно, Мкуусеринстанце уникально идентифицирует сочетание "пользователь-устройство".</span><span class="sxs-lookup"><span data-stu-id="61c38-131">If a user is logged on at multiple computers or devices at once, McuUserInstance uniquely identifies the user/device combination.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61c38-132"><strong>исфромпстн</strong></span><span class="sxs-lookup"><span data-stu-id="61c38-132"><strong>IsFromPstn</strong></span></span></p></td>
<td><p><span data-ttu-id="61c38-133">Битовая</span><span class="sxs-lookup"><span data-stu-id="61c38-133">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="61c38-134">Присоединение пользователя к сети PSTN или нет.</span><span class="sxs-lookup"><span data-stu-id="61c38-134">Whether the user is joining from a PSTN or not.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61c38-135"><strong>мкуид</strong></span><span class="sxs-lookup"><span data-stu-id="61c38-135"><strong>McuId</strong></span></span></p></td>
<td><p><span data-ttu-id="61c38-136">int</span><span class="sxs-lookup"><span data-stu-id="61c38-136">int</span></span></p></td>
<td><p><span data-ttu-id="61c38-137">Основной, Внешний</span><span class="sxs-lookup"><span data-stu-id="61c38-137">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="61c38-138">Уникальный номер, идентифицирующий этот сервер конференц-связи.</span><span class="sxs-lookup"><span data-stu-id="61c38-138">Unique number identifying this conferencing server.</span></span> <span data-ttu-id="61c38-139">Дополнительные сведения см. <a href="lync-server-2013-mcus-table.md">в таблице MCUs в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="61c38-139">See the <a href="lync-server-2013-mcus-table.md">Mcus table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61c38-140"><strong>диалогсессионидтиме</strong></span><span class="sxs-lookup"><span data-stu-id="61c38-140"><strong>DialogSessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="61c38-141">datetime</span><span class="sxs-lookup"><span data-stu-id="61c38-141">datetime</span></span></p></td>
<td><p><span data-ttu-id="61c38-142">Правительства</span><span class="sxs-lookup"><span data-stu-id="61c38-142">Foreign</span></span></p></td>
<td><p><span data-ttu-id="61c38-143">Время запроса сеанса.</span><span class="sxs-lookup"><span data-stu-id="61c38-143">Time of session request.</span></span> <span data-ttu-id="61c38-144">В сочетании с параметром <strong>SessionIdSeq</strong> определяет сеанс уникальным образом.</span><span class="sxs-lookup"><span data-stu-id="61c38-144">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="61c38-145">Дополнительные сведения см. <a href="lync-server-2013-dialogs-table.md">в таблице диалоговых окон в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="61c38-145">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61c38-146"><strong>диалогсессионидсек</strong></span><span class="sxs-lookup"><span data-stu-id="61c38-146"><strong>DialogSessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="61c38-147">int</span><span class="sxs-lookup"><span data-stu-id="61c38-147">int</span></span></p></td>
<td><p><span data-ttu-id="61c38-148">Правительства</span><span class="sxs-lookup"><span data-stu-id="61c38-148">Foreign</span></span></p></td>
<td><p><span data-ttu-id="61c38-149">Идентификатор для идентификации сеанса.</span><span class="sxs-lookup"><span data-stu-id="61c38-149">ID number to identify the session.</span></span> <span data-ttu-id="61c38-150">В сочетании с параметром <strong>SessionIdTime</strong> определяет сеанс уникальным образом.</span><span class="sxs-lookup"><span data-stu-id="61c38-150">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="61c38-151">Дополнительные сведения см. <a href="lync-server-2013-dialogs-table.md">в таблице диалоговых окон в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="61c38-151">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61c38-152"><strong>усержоинтиме</strong></span><span class="sxs-lookup"><span data-stu-id="61c38-152"><strong>UserJoinTime</strong></span></span></p></td>
<td><p><span data-ttu-id="61c38-153">datetime</span><span class="sxs-lookup"><span data-stu-id="61c38-153">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="61c38-154">Время, когда этот пользователь присоединяется к этому серверу конференций.</span><span class="sxs-lookup"><span data-stu-id="61c38-154">The time this user joins this conferencing server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61c38-155"><strong>усерлеаветиме</strong></span><span class="sxs-lookup"><span data-stu-id="61c38-155"><strong>UserLeaveTime</strong></span></span></p></td>
<td><p><span data-ttu-id="61c38-156">datetime</span><span class="sxs-lookup"><span data-stu-id="61c38-156">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="61c38-157">Время, когда этот пользователь покидает этот сервер конференц-связи.</span><span class="sxs-lookup"><span data-stu-id="61c38-157">The time this user leaves this conferencing server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61c38-158"><strong>клиентверид</strong></span><span class="sxs-lookup"><span data-stu-id="61c38-158"><strong>ClientVerId</strong></span></span></p></td>
<td><p><span data-ttu-id="61c38-159">int</span><span class="sxs-lookup"><span data-stu-id="61c38-159">int</span></span></p></td>
<td><p><span data-ttu-id="61c38-160">Правительства</span><span class="sxs-lookup"><span data-stu-id="61c38-160">Foreign</span></span></p></td>
<td><p><span data-ttu-id="61c38-161">Идентификатор, указывающий номер версии клиентского программного обеспечения, используемого в Конференции.</span><span class="sxs-lookup"><span data-stu-id="61c38-161">Identifier that specifies the version number of the client software use in the conference.</span></span> <span data-ttu-id="61c38-162">Дополнительные сведения см. <a href="lync-server-2013-clientversions-table.md">в таблице таблица clientversions в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="61c38-162">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p>
<p><span data-ttu-id="61c38-163">Это поле было введено в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="61c38-163">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

