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
ms.openlocfilehash: 138fe5f989fb11986c3db6e134fa7f975a95c96e
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42149909"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="mcujoinsandleaves-table-in-lync-server-2013"></a><span data-ttu-id="9db30-102">Таблица Таблица mcujoinsandleaves в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9db30-102">McuJoinsAndLeaves table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9db30-103">_**Последнее изменение темы:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="9db30-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="9db30-104">Каждая запись в этой таблице содержит сведения о вызовах для одной комбинации присоединения или выхода пользователя и сервера конференц-связи.</span><span class="sxs-lookup"><span data-stu-id="9db30-104">Each record in this table contains call details about one combination of a user join or leave and conferencing server.</span></span> <span data-ttu-id="9db30-105">Например, если пользователь присоединяется к Конференции, которая включает веб-конференции и аудио-и видеоэлементы, будет создана одна запись для соединения веб-конференций этого пользователя, а для подключения аудио-и видеоконференций пользователя будет создана другая запись.</span><span class="sxs-lookup"><span data-stu-id="9db30-105">For example, if a user joins a conference that includes web conferencing and audio/video elements, one record would be created for that user’s web conferencing join, and another record would be created for the user’s audio/video conferencing join.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9db30-106">Столбец</span><span class="sxs-lookup"><span data-stu-id="9db30-106">Column</span></span></th>
<th><span data-ttu-id="9db30-107">Тип данных</span><span class="sxs-lookup"><span data-stu-id="9db30-107">Data Type</span></span></th>
<th><span data-ttu-id="9db30-108">Ключ или индекс</span><span class="sxs-lookup"><span data-stu-id="9db30-108">Key/Index</span></span></th>
<th><span data-ttu-id="9db30-109">Сведения</span><span class="sxs-lookup"><span data-stu-id="9db30-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9db30-110"><strong>сессионидтиме</strong></span><span class="sxs-lookup"><span data-stu-id="9db30-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="9db30-111">datetime</span><span class="sxs-lookup"><span data-stu-id="9db30-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="9db30-112">Основной, внешний</span><span class="sxs-lookup"><span data-stu-id="9db30-112">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="9db30-113">Время экземпляра конференции.</span><span class="sxs-lookup"><span data-stu-id="9db30-113">Time of conference instance.</span></span> <span data-ttu-id="9db30-114">Используется совместно с <strong>сессионидсек</strong> для уникальной идентификации экземпляра Конференции.</span><span class="sxs-lookup"><span data-stu-id="9db30-114">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a conference instance.</span></span> <span data-ttu-id="9db30-115">Дополнительные сведения см. <a href="lync-server-2013-conferences-table.md">в таблице конференций в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="9db30-115">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9db30-116"><strong>сессионидсек</strong></span><span class="sxs-lookup"><span data-stu-id="9db30-116"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="9db30-117">int</span><span class="sxs-lookup"><span data-stu-id="9db30-117">int</span></span></p></td>
<td><p><span data-ttu-id="9db30-118">Основной, Внешний</span><span class="sxs-lookup"><span data-stu-id="9db30-118">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="9db30-119">Идентификатор для определения экземпляра конференции.</span><span class="sxs-lookup"><span data-stu-id="9db30-119">ID number to identify the conference instance.</span></span> <span data-ttu-id="9db30-120">Используется совместно с <strong>сессионидтиме</strong> для уникальной идентификации экземпляра Конференции.</span><span class="sxs-lookup"><span data-stu-id="9db30-120">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a conference instance.</span></span> <span data-ttu-id="9db30-121">Дополнительные сведения см. <a href="lync-server-2013-conferences-table.md">в таблице конференций в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="9db30-121">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9db30-122"><strong>UserId</strong></span><span class="sxs-lookup"><span data-stu-id="9db30-122"><strong>UserId</strong></span></span></p></td>
<td><p><span data-ttu-id="9db30-123">int</span><span class="sxs-lookup"><span data-stu-id="9db30-123">int</span></span></p></td>
<td><p><span data-ttu-id="9db30-124">Основной, Внешний</span><span class="sxs-lookup"><span data-stu-id="9db30-124">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="9db30-125">Уникальный номер, идентифицирующий данного пользователя.</span><span class="sxs-lookup"><span data-stu-id="9db30-125">Unique number identifying this user.</span></span> <span data-ttu-id="9db30-126">Дополнительные сведения см. <a href="lync-server-2013-users-table.md">в таблице "Пользователи" в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="9db30-126">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9db30-127"><strong>мкуусеринстанце</strong></span><span class="sxs-lookup"><span data-stu-id="9db30-127"><strong>McuUserInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="9db30-128">int</span><span class="sxs-lookup"><span data-stu-id="9db30-128">int</span></span></p></td>
<td><p><span data-ttu-id="9db30-129">Primary</span><span class="sxs-lookup"><span data-stu-id="9db30-129">Primary</span></span></p></td>
<td><p><span data-ttu-id="9db30-130">Если пользователь вошел в систему на нескольких компьютерах или устройствах одновременно, Мкуусеринстанце уникально идентифицирует сочетание "пользователь-устройство".</span><span class="sxs-lookup"><span data-stu-id="9db30-130">If a user is logged on at multiple computers or devices at once, McuUserInstance uniquely identifies the user/device combination.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9db30-131"><strong>исфромпстн</strong></span><span class="sxs-lookup"><span data-stu-id="9db30-131"><strong>IsFromPstn</strong></span></span></p></td>
<td><p><span data-ttu-id="9db30-132">Битовая</span><span class="sxs-lookup"><span data-stu-id="9db30-132">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="9db30-133">Присоединение пользователя к сети PSTN или нет.</span><span class="sxs-lookup"><span data-stu-id="9db30-133">Whether the user is joining from a PSTN or not.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9db30-134"><strong>мкуид</strong></span><span class="sxs-lookup"><span data-stu-id="9db30-134"><strong>McuId</strong></span></span></p></td>
<td><p><span data-ttu-id="9db30-135">int</span><span class="sxs-lookup"><span data-stu-id="9db30-135">int</span></span></p></td>
<td><p><span data-ttu-id="9db30-136">Основной, Внешний</span><span class="sxs-lookup"><span data-stu-id="9db30-136">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="9db30-137">Уникальный номер, идентифицирующий этот сервер конференц-связи.</span><span class="sxs-lookup"><span data-stu-id="9db30-137">Unique number identifying this conferencing server.</span></span> <span data-ttu-id="9db30-138">Дополнительные сведения см. <a href="lync-server-2013-mcus-table.md">в таблице MCUs в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="9db30-138">See the <a href="lync-server-2013-mcus-table.md">Mcus table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9db30-139"><strong>диалогсессионидтиме</strong></span><span class="sxs-lookup"><span data-stu-id="9db30-139"><strong>DialogSessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="9db30-140">datetime</span><span class="sxs-lookup"><span data-stu-id="9db30-140">datetime</span></span></p></td>
<td><p><span data-ttu-id="9db30-141">Правительства</span><span class="sxs-lookup"><span data-stu-id="9db30-141">Foreign</span></span></p></td>
<td><p><span data-ttu-id="9db30-142">Время запроса сеанса.</span><span class="sxs-lookup"><span data-stu-id="9db30-142">Time of session request.</span></span> <span data-ttu-id="9db30-143">В сочетании с параметром <strong>SessionIdSeq</strong> определяет сеанс уникальным образом.</span><span class="sxs-lookup"><span data-stu-id="9db30-143">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="9db30-144">Дополнительные сведения см. <a href="lync-server-2013-dialogs-table.md">в таблице диалоговых окон в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="9db30-144">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9db30-145"><strong>диалогсессионидсек</strong></span><span class="sxs-lookup"><span data-stu-id="9db30-145"><strong>DialogSessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="9db30-146">int</span><span class="sxs-lookup"><span data-stu-id="9db30-146">int</span></span></p></td>
<td><p><span data-ttu-id="9db30-147">Правительства</span><span class="sxs-lookup"><span data-stu-id="9db30-147">Foreign</span></span></p></td>
<td><p><span data-ttu-id="9db30-148">Идентификатор для идентификации сеанса.</span><span class="sxs-lookup"><span data-stu-id="9db30-148">ID number to identify the session.</span></span> <span data-ttu-id="9db30-149">В сочетании с параметром <strong>SessionIdTime</strong> определяет сеанс уникальным образом.</span><span class="sxs-lookup"><span data-stu-id="9db30-149">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="9db30-150">Дополнительные сведения см. <a href="lync-server-2013-dialogs-table.md">в таблице диалоговых окон в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="9db30-150">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9db30-151"><strong>усержоинтиме</strong></span><span class="sxs-lookup"><span data-stu-id="9db30-151"><strong>UserJoinTime</strong></span></span></p></td>
<td><p><span data-ttu-id="9db30-152">datetime</span><span class="sxs-lookup"><span data-stu-id="9db30-152">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="9db30-153">Время, когда этот пользователь присоединяется к этому серверу конференций.</span><span class="sxs-lookup"><span data-stu-id="9db30-153">The time this user joins this conferencing server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9db30-154"><strong>усерлеаветиме</strong></span><span class="sxs-lookup"><span data-stu-id="9db30-154"><strong>UserLeaveTime</strong></span></span></p></td>
<td><p><span data-ttu-id="9db30-155">datetime</span><span class="sxs-lookup"><span data-stu-id="9db30-155">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="9db30-156">Время, когда этот пользователь покидает этот сервер конференц-связи.</span><span class="sxs-lookup"><span data-stu-id="9db30-156">The time this user leaves this conferencing server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9db30-157"><strong>клиентверид</strong></span><span class="sxs-lookup"><span data-stu-id="9db30-157"><strong>ClientVerId</strong></span></span></p></td>
<td><p><span data-ttu-id="9db30-158">int</span><span class="sxs-lookup"><span data-stu-id="9db30-158">int</span></span></p></td>
<td><p><span data-ttu-id="9db30-159">Правительства</span><span class="sxs-lookup"><span data-stu-id="9db30-159">Foreign</span></span></p></td>
<td><p><span data-ttu-id="9db30-160">Идентификатор, указывающий номер версии клиентского программного обеспечения, используемого в Конференции.</span><span class="sxs-lookup"><span data-stu-id="9db30-160">Identifier that specifies the version number of the client software use in the conference.</span></span> <span data-ttu-id="9db30-161">Дополнительные сведения см. <a href="lync-server-2013-clientversions-table.md">в таблице таблица clientversions в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="9db30-161">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p>
<p><span data-ttu-id="9db30-162">Это поле было введено в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9db30-162">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

