---
title: 'Lync Server 2013: таблица таблица mcujoinsandleaves'
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
ms.openlocfilehash: f4aa5fb14ff16d13b1cdff72f15c648f9e353922
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48524736"
---
# <a name="mcujoinsandleaves-table-in-lync-server-2013"></a><span data-ttu-id="51fbb-102">Таблица Таблица mcujoinsandleaves в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="51fbb-102">McuJoinsAndLeaves table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="51fbb-103">_**Последнее изменение темы:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="51fbb-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="51fbb-104">Каждая запись в этой таблице содержит сведения о вызовах для одной комбинации присоединения или выхода пользователя и сервера конференц-связи.</span><span class="sxs-lookup"><span data-stu-id="51fbb-104">Each record in this table contains call details about one combination of a user join or leave and conferencing server.</span></span> <span data-ttu-id="51fbb-105">Например, если пользователь присоединяется к Конференции, которая включает веб-конференции и аудио-и видеоэлементы, будет создана одна запись для соединения веб-конференций этого пользователя, а для подключения аудио-и видеоконференций пользователя будет создана другая запись.</span><span class="sxs-lookup"><span data-stu-id="51fbb-105">For example, if a user joins a conference that includes web conferencing and audio/video elements, one record would be created for that user’s web conferencing join, and another record would be created for the user’s audio/video conferencing join.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="51fbb-106">Столбец</span><span class="sxs-lookup"><span data-stu-id="51fbb-106">Column</span></span></th>
<th><span data-ttu-id="51fbb-107">Тип данных</span><span class="sxs-lookup"><span data-stu-id="51fbb-107">Data Type</span></span></th>
<th><span data-ttu-id="51fbb-108">Ключ или индекс</span><span class="sxs-lookup"><span data-stu-id="51fbb-108">Key/Index</span></span></th>
<th><span data-ttu-id="51fbb-109">Сведения</span><span class="sxs-lookup"><span data-stu-id="51fbb-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="51fbb-110"><strong>сессионидтиме</strong></span><span class="sxs-lookup"><span data-stu-id="51fbb-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="51fbb-111">datetime</span><span class="sxs-lookup"><span data-stu-id="51fbb-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="51fbb-112">Основной, внешний</span><span class="sxs-lookup"><span data-stu-id="51fbb-112">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="51fbb-113">Время экземпляра конференции.</span><span class="sxs-lookup"><span data-stu-id="51fbb-113">Time of conference instance.</span></span> <span data-ttu-id="51fbb-114">Используется совместно с <strong>сессионидсек</strong> для уникальной идентификации экземпляра Конференции.</span><span class="sxs-lookup"><span data-stu-id="51fbb-114">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a conference instance.</span></span> <span data-ttu-id="51fbb-115">Дополнительные сведения см. <a href="lync-server-2013-conferences-table.md">в таблице конференций в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="51fbb-115">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="51fbb-116"><strong>сессионидсек</strong></span><span class="sxs-lookup"><span data-stu-id="51fbb-116"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="51fbb-117">int</span><span class="sxs-lookup"><span data-stu-id="51fbb-117">int</span></span></p></td>
<td><p><span data-ttu-id="51fbb-118">Основной, Внешний</span><span class="sxs-lookup"><span data-stu-id="51fbb-118">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="51fbb-119">Идентификатор для определения экземпляра конференции.</span><span class="sxs-lookup"><span data-stu-id="51fbb-119">ID number to identify the conference instance.</span></span> <span data-ttu-id="51fbb-120">Используется совместно с <strong>сессионидтиме</strong> для уникальной идентификации экземпляра Конференции.</span><span class="sxs-lookup"><span data-stu-id="51fbb-120">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a conference instance.</span></span> <span data-ttu-id="51fbb-121">Дополнительные сведения см. <a href="lync-server-2013-conferences-table.md">в таблице конференций в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="51fbb-121">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="51fbb-122"><strong>UserId</strong></span><span class="sxs-lookup"><span data-stu-id="51fbb-122"><strong>UserId</strong></span></span></p></td>
<td><p><span data-ttu-id="51fbb-123">int</span><span class="sxs-lookup"><span data-stu-id="51fbb-123">int</span></span></p></td>
<td><p><span data-ttu-id="51fbb-124">Основной, Внешний</span><span class="sxs-lookup"><span data-stu-id="51fbb-124">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="51fbb-125">Уникальный номер, идентифицирующий данного пользователя.</span><span class="sxs-lookup"><span data-stu-id="51fbb-125">Unique number identifying this user.</span></span> <span data-ttu-id="51fbb-126">Дополнительные сведения см. <a href="lync-server-2013-users-table.md">в таблице "Пользователи" в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="51fbb-126">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="51fbb-127"><strong>мкуусеринстанце</strong></span><span class="sxs-lookup"><span data-stu-id="51fbb-127"><strong>McuUserInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="51fbb-128">int</span><span class="sxs-lookup"><span data-stu-id="51fbb-128">int</span></span></p></td>
<td><p><span data-ttu-id="51fbb-129">Primary</span><span class="sxs-lookup"><span data-stu-id="51fbb-129">Primary</span></span></p></td>
<td><p><span data-ttu-id="51fbb-130">Если пользователь вошел в систему на нескольких компьютерах или устройствах одновременно, Мкуусеринстанце уникально идентифицирует сочетание "пользователь-устройство".</span><span class="sxs-lookup"><span data-stu-id="51fbb-130">If a user is logged on at multiple computers or devices at once, McuUserInstance uniquely identifies the user/device combination.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="51fbb-131"><strong>исфромпстн</strong></span><span class="sxs-lookup"><span data-stu-id="51fbb-131"><strong>IsFromPstn</strong></span></span></p></td>
<td><p><span data-ttu-id="51fbb-132">Битовая</span><span class="sxs-lookup"><span data-stu-id="51fbb-132">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="51fbb-133">Присоединение пользователя к сети PSTN или нет.</span><span class="sxs-lookup"><span data-stu-id="51fbb-133">Whether the user is joining from a PSTN or not.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="51fbb-134"><strong>мкуид</strong></span><span class="sxs-lookup"><span data-stu-id="51fbb-134"><strong>McuId</strong></span></span></p></td>
<td><p><span data-ttu-id="51fbb-135">int</span><span class="sxs-lookup"><span data-stu-id="51fbb-135">int</span></span></p></td>
<td><p><span data-ttu-id="51fbb-136">Основной, Внешний</span><span class="sxs-lookup"><span data-stu-id="51fbb-136">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="51fbb-137">Уникальный номер, идентифицирующий этот сервер конференц-связи.</span><span class="sxs-lookup"><span data-stu-id="51fbb-137">Unique number identifying this conferencing server.</span></span> <span data-ttu-id="51fbb-138">Дополнительные сведения см. <a href="lync-server-2013-mcus-table.md">в таблице MCUs в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="51fbb-138">See the <a href="lync-server-2013-mcus-table.md">Mcus table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="51fbb-139"><strong>диалогсессионидтиме</strong></span><span class="sxs-lookup"><span data-stu-id="51fbb-139"><strong>DialogSessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="51fbb-140">datetime</span><span class="sxs-lookup"><span data-stu-id="51fbb-140">datetime</span></span></p></td>
<td><p><span data-ttu-id="51fbb-141">Правительства</span><span class="sxs-lookup"><span data-stu-id="51fbb-141">Foreign</span></span></p></td>
<td><p><span data-ttu-id="51fbb-142">Время запроса сеанса.</span><span class="sxs-lookup"><span data-stu-id="51fbb-142">Time of session request.</span></span> <span data-ttu-id="51fbb-143">В сочетании с параметром <strong>SessionIdSeq</strong> определяет сеанс уникальным образом.</span><span class="sxs-lookup"><span data-stu-id="51fbb-143">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="51fbb-144">Дополнительные сведения см. <a href="lync-server-2013-dialogs-table.md">в таблице диалоговых окон в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="51fbb-144">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="51fbb-145"><strong>диалогсессионидсек</strong></span><span class="sxs-lookup"><span data-stu-id="51fbb-145"><strong>DialogSessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="51fbb-146">int</span><span class="sxs-lookup"><span data-stu-id="51fbb-146">int</span></span></p></td>
<td><p><span data-ttu-id="51fbb-147">Правительства</span><span class="sxs-lookup"><span data-stu-id="51fbb-147">Foreign</span></span></p></td>
<td><p><span data-ttu-id="51fbb-148">Идентификатор для идентификации сеанса.</span><span class="sxs-lookup"><span data-stu-id="51fbb-148">ID number to identify the session.</span></span> <span data-ttu-id="51fbb-149">В сочетании с параметром <strong>SessionIdTime</strong> определяет сеанс уникальным образом.</span><span class="sxs-lookup"><span data-stu-id="51fbb-149">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="51fbb-150">Дополнительные сведения см. <a href="lync-server-2013-dialogs-table.md">в таблице диалоговых окон в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="51fbb-150">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="51fbb-151"><strong>усержоинтиме</strong></span><span class="sxs-lookup"><span data-stu-id="51fbb-151"><strong>UserJoinTime</strong></span></span></p></td>
<td><p><span data-ttu-id="51fbb-152">datetime</span><span class="sxs-lookup"><span data-stu-id="51fbb-152">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="51fbb-153">Время, когда этот пользователь присоединяется к этому серверу конференций.</span><span class="sxs-lookup"><span data-stu-id="51fbb-153">The time this user joins this conferencing server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="51fbb-154"><strong>усерлеаветиме</strong></span><span class="sxs-lookup"><span data-stu-id="51fbb-154"><strong>UserLeaveTime</strong></span></span></p></td>
<td><p><span data-ttu-id="51fbb-155">datetime</span><span class="sxs-lookup"><span data-stu-id="51fbb-155">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="51fbb-156">Время, когда этот пользователь покидает этот сервер конференц-связи.</span><span class="sxs-lookup"><span data-stu-id="51fbb-156">The time this user leaves this conferencing server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="51fbb-157"><strong>клиентверид</strong></span><span class="sxs-lookup"><span data-stu-id="51fbb-157"><strong>ClientVerId</strong></span></span></p></td>
<td><p><span data-ttu-id="51fbb-158">int</span><span class="sxs-lookup"><span data-stu-id="51fbb-158">int</span></span></p></td>
<td><p><span data-ttu-id="51fbb-159">Правительства</span><span class="sxs-lookup"><span data-stu-id="51fbb-159">Foreign</span></span></p></td>
<td><p><span data-ttu-id="51fbb-160">Идентификатор, указывающий номер версии клиентского программного обеспечения, используемого в Конференции.</span><span class="sxs-lookup"><span data-stu-id="51fbb-160">Identifier that specifies the version number of the client software use in the conference.</span></span> <span data-ttu-id="51fbb-161">Дополнительные сведения см. <a href="lync-server-2013-clientversions-table.md">в таблице таблица clientversions в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="51fbb-161">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p>
<p><span data-ttu-id="51fbb-162">Это поле было введено в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="51fbb-162">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

