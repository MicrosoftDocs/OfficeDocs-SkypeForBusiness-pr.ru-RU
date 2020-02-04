---
title: 'Lync Server 2013: таблица McuJoinsAndLeaves'
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
ms.openlocfilehash: 204906deb88a2067b7304088515b25fee2da0350
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739429"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="mcujoinsandleaves-table-in-lync-server-2013"></a><span data-ttu-id="7e827-102">Таблица McuJoinsAndLeaves в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7e827-102">McuJoinsAndLeaves table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7e827-103">_**Тема последнего изменения:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="7e827-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="7e827-104">Каждая запись в этой таблице включает сведения о звонках для одной комбинации присоединения или выхода из нее и сервера конференций.</span><span class="sxs-lookup"><span data-stu-id="7e827-104">Each record in this table contains call details about one combination of a user join or leave and conferencing server.</span></span> <span data-ttu-id="7e827-105">Например, если пользователь присоединяется к Конференции, которая включает веб-конференции и звуковые и видеоэлементы, для подключения к веб-конференции пользователя будет создана одна запись, а для голосовых и видеоконференций пользователя будет создана другая запись.</span><span class="sxs-lookup"><span data-stu-id="7e827-105">For example, if a user joins a conference that includes web conferencing and audio/video elements, one record would be created for that user’s web conferencing join, and another record would be created for the user’s audio/video conferencing join.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7e827-106">Столбец</span><span class="sxs-lookup"><span data-stu-id="7e827-106">Column</span></span></th>
<th><span data-ttu-id="7e827-107">Тип данных</span><span class="sxs-lookup"><span data-stu-id="7e827-107">Data Type</span></span></th>
<th><span data-ttu-id="7e827-108">Ключ/индекс</span><span class="sxs-lookup"><span data-stu-id="7e827-108">Key/Index</span></span></th>
<th><span data-ttu-id="7e827-109">Сведения</span><span class="sxs-lookup"><span data-stu-id="7e827-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7e827-110"><strong>сессионидтиме</strong></span><span class="sxs-lookup"><span data-stu-id="7e827-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="7e827-111">datetime</span><span class="sxs-lookup"><span data-stu-id="7e827-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="7e827-112">Основной, внешний</span><span class="sxs-lookup"><span data-stu-id="7e827-112">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="7e827-113">Время экземпляра Конференции.</span><span class="sxs-lookup"><span data-stu-id="7e827-113">Time of conference instance.</span></span> <span data-ttu-id="7e827-114">Используется в сочетании с <strong>сессионидсек</strong> для уникальной идентификации экземпляра Конференции.</span><span class="sxs-lookup"><span data-stu-id="7e827-114">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a conference instance.</span></span> <span data-ttu-id="7e827-115">Дополнительные сведения приведены <a href="lync-server-2013-conferences-table.md">в таблице конференции для Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="7e827-115">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7e827-116"><strong>сессионидсек</strong></span><span class="sxs-lookup"><span data-stu-id="7e827-116"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="7e827-117">целое</span><span class="sxs-lookup"><span data-stu-id="7e827-117">int</span></span></p></td>
<td><p><span data-ttu-id="7e827-118">Основной, внешний</span><span class="sxs-lookup"><span data-stu-id="7e827-118">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="7e827-119">ИДЕНТИФИКАЦИОНный номер для идентификации экземпляра Конференции.</span><span class="sxs-lookup"><span data-stu-id="7e827-119">ID number to identify the conference instance.</span></span> <span data-ttu-id="7e827-120">Используется в сочетании с <strong>сессионидтиме</strong> для уникальной идентификации экземпляра Конференции.</span><span class="sxs-lookup"><span data-stu-id="7e827-120">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a conference instance.</span></span> <span data-ttu-id="7e827-121">Дополнительные сведения приведены <a href="lync-server-2013-conferences-table.md">в таблице конференции для Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="7e827-121">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7e827-122"><strong>Идентификатора пользователя</strong></span><span class="sxs-lookup"><span data-stu-id="7e827-122"><strong>UserId</strong></span></span></p></td>
<td><p><span data-ttu-id="7e827-123">целое</span><span class="sxs-lookup"><span data-stu-id="7e827-123">int</span></span></p></td>
<td><p><span data-ttu-id="7e827-124">Основной, внешний</span><span class="sxs-lookup"><span data-stu-id="7e827-124">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="7e827-125">Уникальный номер, идентифицирующий этого пользователя.</span><span class="sxs-lookup"><span data-stu-id="7e827-125">Unique number identifying this user.</span></span> <span data-ttu-id="7e827-126">Дополнительные сведения <a href="lync-server-2013-users-table.md">можно найти в таблице Users (пользователи) в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="7e827-126">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7e827-127"><strong>мкуусеринстанце</strong></span><span class="sxs-lookup"><span data-stu-id="7e827-127"><strong>McuUserInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="7e827-128">целое</span><span class="sxs-lookup"><span data-stu-id="7e827-128">int</span></span></p></td>
<td><p><span data-ttu-id="7e827-129">Primary</span><span class="sxs-lookup"><span data-stu-id="7e827-129">Primary</span></span></p></td>
<td><p><span data-ttu-id="7e827-130">Если пользователь входит в систему на нескольких компьютерах или устройствах одновременно, Мкуусеринстанце однозначно определяет сочетание пользователей и устройств.</span><span class="sxs-lookup"><span data-stu-id="7e827-130">If a user is logged on at multiple computers or devices at once, McuUserInstance uniquely identifies the user/device combination.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7e827-131"><strong>исфромпстн</strong></span><span class="sxs-lookup"><span data-stu-id="7e827-131"><strong>IsFromPstn</strong></span></span></p></td>
<td><p><span data-ttu-id="7e827-132">бит</span><span class="sxs-lookup"><span data-stu-id="7e827-132">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="7e827-133">Присоединение пользователя к сети PSTN или нет.</span><span class="sxs-lookup"><span data-stu-id="7e827-133">Whether the user is joining from a PSTN or not.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7e827-134"><strong>мкуид</strong></span><span class="sxs-lookup"><span data-stu-id="7e827-134"><strong>McuId</strong></span></span></p></td>
<td><p><span data-ttu-id="7e827-135">целое</span><span class="sxs-lookup"><span data-stu-id="7e827-135">int</span></span></p></td>
<td><p><span data-ttu-id="7e827-136">Основной, внешний</span><span class="sxs-lookup"><span data-stu-id="7e827-136">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="7e827-137">Уникальный номер, идентифицирующий этот сервер конференц-связи.</span><span class="sxs-lookup"><span data-stu-id="7e827-137">Unique number identifying this conferencing server.</span></span> <span data-ttu-id="7e827-138">Для получения дополнительных сведений ознакомьтесь с <a href="lync-server-2013-mcus-table.md">таблицей мкус в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="7e827-138">See the <a href="lync-server-2013-mcus-table.md">Mcus table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7e827-139"><strong>диалогсессионидтиме</strong></span><span class="sxs-lookup"><span data-stu-id="7e827-139"><strong>DialogSessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="7e827-140">datetime</span><span class="sxs-lookup"><span data-stu-id="7e827-140">datetime</span></span></p></td>
<td><p><span data-ttu-id="7e827-141">Другом</span><span class="sxs-lookup"><span data-stu-id="7e827-141">Foreign</span></span></p></td>
<td><p><span data-ttu-id="7e827-142">Время запроса сеанса.</span><span class="sxs-lookup"><span data-stu-id="7e827-142">Time of session request.</span></span> <span data-ttu-id="7e827-143">Используется в сочетании с <strong>сессионидсек</strong> для уникальной идентификации сеанса.</span><span class="sxs-lookup"><span data-stu-id="7e827-143">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="7e827-144">Дополнительные сведения приведены <a href="lync-server-2013-dialogs-table.md">в таблице диалоговые окна Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="7e827-144">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7e827-145"><strong>диалогсессионидсек</strong></span><span class="sxs-lookup"><span data-stu-id="7e827-145"><strong>DialogSessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="7e827-146">целое</span><span class="sxs-lookup"><span data-stu-id="7e827-146">int</span></span></p></td>
<td><p><span data-ttu-id="7e827-147">Другом</span><span class="sxs-lookup"><span data-stu-id="7e827-147">Foreign</span></span></p></td>
<td><p><span data-ttu-id="7e827-148">ИДЕНТИФИКАЦИОНный номер для идентификации сеанса.</span><span class="sxs-lookup"><span data-stu-id="7e827-148">ID number to identify the session.</span></span> <span data-ttu-id="7e827-149">Используется в сочетании с <strong>сессионидтиме</strong> для уникальной идентификации сеанса.</span><span class="sxs-lookup"><span data-stu-id="7e827-149">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="7e827-150">Дополнительные сведения приведены <a href="lync-server-2013-dialogs-table.md">в таблице диалоговые окна Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="7e827-150">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7e827-151"><strong>усержоинтиме</strong></span><span class="sxs-lookup"><span data-stu-id="7e827-151"><strong>UserJoinTime</strong></span></span></p></td>
<td><p><span data-ttu-id="7e827-152">datetime</span><span class="sxs-lookup"><span data-stu-id="7e827-152">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="7e827-153">Время присоединения пользователя к этому серверу конференций.</span><span class="sxs-lookup"><span data-stu-id="7e827-153">The time this user joins this conferencing server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7e827-154"><strong>усерлеаветиме</strong></span><span class="sxs-lookup"><span data-stu-id="7e827-154"><strong>UserLeaveTime</strong></span></span></p></td>
<td><p><span data-ttu-id="7e827-155">datetime</span><span class="sxs-lookup"><span data-stu-id="7e827-155">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="7e827-156">Время, когда этот пользователь покидает этот сервер конференц-связи.</span><span class="sxs-lookup"><span data-stu-id="7e827-156">The time this user leaves this conferencing server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7e827-157"><strong>клиентверид</strong></span><span class="sxs-lookup"><span data-stu-id="7e827-157"><strong>ClientVerId</strong></span></span></p></td>
<td><p><span data-ttu-id="7e827-158">целое</span><span class="sxs-lookup"><span data-stu-id="7e827-158">int</span></span></p></td>
<td><p><span data-ttu-id="7e827-159">Другом</span><span class="sxs-lookup"><span data-stu-id="7e827-159">Foreign</span></span></p></td>
<td><p><span data-ttu-id="7e827-160">Идентификатор, указывающий номер версии клиентского программного обеспечения, используемого на Конференции.</span><span class="sxs-lookup"><span data-stu-id="7e827-160">Identifier that specifies the version number of the client software use in the conference.</span></span> <span data-ttu-id="7e827-161">Для получения дополнительных сведений ознакомьтесь с <a href="lync-server-2013-clientversions-table.md">таблицей клиентверсионс в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="7e827-161">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p>
<p><span data-ttu-id="7e827-162">Это поле было введено в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7e827-162">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

