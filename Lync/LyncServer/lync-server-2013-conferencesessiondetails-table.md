---
title: 'Lync Server 2013: таблица ConferenceSessionDetails'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: ConferenceSessionDetails table
ms:assetid: 9eae6a54-69fd-4966-aa17-7ecee1297ad8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412741(v=OCS.15)
ms:contentKeyID: 48184925
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4c5aaa3ec022be18ad54cc8a24b8410c23faf799
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34841495"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conferencesessiondetails-table-in-lync-server-2013"></a><span data-ttu-id="42fb1-102">Таблица ConferenceSessionDetails в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="42fb1-102">ConferenceSessionDetails table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="42fb1-103">_**Тема последнего изменения:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="42fb1-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="42fb1-104">Каждая запись представляет один сеанс конференции, который может быть либо сеансом с фокусом, либо сеансом с определенным сервером конференц-связи.</span><span class="sxs-lookup"><span data-stu-id="42fb1-104">Each record represents one conference session, which could be either the session with Focus or the session with a specific conferencing server.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="42fb1-105">Столбец</span><span class="sxs-lookup"><span data-stu-id="42fb1-105">Column</span></span></th>
<th><span data-ttu-id="42fb1-106">Тип данных</span><span class="sxs-lookup"><span data-stu-id="42fb1-106">Data Type</span></span></th>
<th><span data-ttu-id="42fb1-107">Ключ/индекс</span><span class="sxs-lookup"><span data-stu-id="42fb1-107">Key/Index</span></span></th>
<th><span data-ttu-id="42fb1-108">Сведения</span><span class="sxs-lookup"><span data-stu-id="42fb1-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="42fb1-109"><strong>Сессионидтиме</strong></span><span class="sxs-lookup"><span data-stu-id="42fb1-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="42fb1-110">Датой</span><span class="sxs-lookup"><span data-stu-id="42fb1-110">Datetime</span></span></p></td>
<td><p><span data-ttu-id="42fb1-111">Основной, внешний</span><span class="sxs-lookup"><span data-stu-id="42fb1-111">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="42fb1-112">Время запроса сеанса; используется в сочетании с <strong>сессионидсек</strong> для уникальной идентификации сеанса конференц-связи.</span><span class="sxs-lookup"><span data-stu-id="42fb1-112">Time of session request; used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a conference session.</span></span> <span data-ttu-id="42fb1-113">Дополнительные сведения приведены <a href="lync-server-2013-dialogs-table.md">в таблице диалоговые окна Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="42fb1-113">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="42fb1-114"><strong>Сессионидсек</strong></span><span class="sxs-lookup"><span data-stu-id="42fb1-114"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="42fb1-115">целое</span><span class="sxs-lookup"><span data-stu-id="42fb1-115">int</span></span></p></td>
<td><p><span data-ttu-id="42fb1-116">Основной, внешний</span><span class="sxs-lookup"><span data-stu-id="42fb1-116">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="42fb1-117">ИДЕНТИФИКАЦИОНный номер для идентификации сеанса.</span><span class="sxs-lookup"><span data-stu-id="42fb1-117">ID number to identify the session.</span></span> <span data-ttu-id="42fb1-118">Используется в сочетании с <strong>сессионидтиме</strong> для уникальной идентификации сеанса конференц-связи.</span><span class="sxs-lookup"><span data-stu-id="42fb1-118">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a conference session.</span></span> <span data-ttu-id="42fb1-119">Дополнительные сведения приведены <a href="lync-server-2013-dialogs-table.md">в таблице диалоговые окна Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="42fb1-119">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span> *</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="42fb1-120"><strong>Конференцеуриид</strong></span><span class="sxs-lookup"><span data-stu-id="42fb1-120"><strong>ConferenceUriId</strong></span></span></p></td>
<td><p><span data-ttu-id="42fb1-121">целое</span><span class="sxs-lookup"><span data-stu-id="42fb1-121">int</span></span></p></td>
<td><p><span data-ttu-id="42fb1-122">Другом</span><span class="sxs-lookup"><span data-stu-id="42fb1-122">Foreign</span></span></p></td>
<td><p><span data-ttu-id="42fb1-123">КОД URI конференции Focus, связанный с этим сеансом.</span><span class="sxs-lookup"><span data-stu-id="42fb1-123">Focus conference URI related to this session.</span></span> <span data-ttu-id="42fb1-124">Для получения дополнительных сведений ознакомьтесь с <a href="lync-server-2013-conferenceuris-table.md">таблицей конференцеурис в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="42fb1-124">See the <a href="lync-server-2013-conferenceuris-table.md">ConferenceUris table in Lync Server 2013</a> for more information.</span></span> <span data-ttu-id="42fb1-125">Этот URI является универсальным кодом ресурса конференции на основе фокуса.</span><span class="sxs-lookup"><span data-stu-id="42fb1-125">This URI is a Focus-based conference URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="42fb1-126"><strong>Конфинстанце</strong></span><span class="sxs-lookup"><span data-stu-id="42fb1-126"><strong>ConfInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="42fb1-127">Идентификатора</span><span class="sxs-lookup"><span data-stu-id="42fb1-127">uniqueIdentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="42fb1-128">Идентификатор, отличающийся между экземплярами повторяющихся конференций.</span><span class="sxs-lookup"><span data-stu-id="42fb1-128">Identifier that differentiates between instances of recurring conferences.</span></span> <span data-ttu-id="42fb1-129">Каждый экземпляр повторяющейся Конференции имеет один и тот же Конференцеури, но другое значение Конфинстанце.</span><span class="sxs-lookup"><span data-stu-id="42fb1-129">Each recurring conference instance has the same ConferenceURI but a different ConfInstance value.</span></span></p>
<p><span data-ttu-id="42fb1-130">Это поле было введено в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="42fb1-130">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="42fb1-131"><strong>Мкуконференцеуриид</strong></span><span class="sxs-lookup"><span data-stu-id="42fb1-131"><strong>McuConferenceUriId</strong></span></span></p></td>
<td><p><span data-ttu-id="42fb1-132">целое</span><span class="sxs-lookup"><span data-stu-id="42fb1-132">int</span></span></p></td>
<td><p><span data-ttu-id="42fb1-133">Другом</span><span class="sxs-lookup"><span data-stu-id="42fb1-133">Foreign</span></span></p></td>
<td><p><span data-ttu-id="42fb1-134">URI конференции сервера конференций, связанный с этим сеансом.</span><span class="sxs-lookup"><span data-stu-id="42fb1-134">Conferencing server conference URI related to this session.</span></span> <span data-ttu-id="42fb1-135">Для получения дополнительных сведений ознакомьтесь с <a href="lync-server-2013-conferenceuris-table.md">таблицей конференцеурис в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="42fb1-135">See the <a href="lync-server-2013-conferenceuris-table.md">ConferenceUris table in Lync Server 2013</a> for more information.</span></span> <span data-ttu-id="42fb1-136">Этот универсальный код ресурса (URI) Конференции на базе сервера конференций.</span><span class="sxs-lookup"><span data-stu-id="42fb1-136">This URI is the conferencing server-based conference URI.</span></span> <span data-ttu-id="42fb1-137">Для сеансов опроса в фокусе этот столбец будет иметь значение null.</span><span class="sxs-lookup"><span data-stu-id="42fb1-137">For Focus conference sessions, this column will be null.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="42fb1-138"><strong>Идентификатора пользователя</strong></span><span class="sxs-lookup"><span data-stu-id="42fb1-138"><strong>UserId</strong></span></span></p></td>
<td><p><span data-ttu-id="42fb1-139">целое</span><span class="sxs-lookup"><span data-stu-id="42fb1-139">int</span></span></p></td>
<td><p><span data-ttu-id="42fb1-140">Другом</span><span class="sxs-lookup"><span data-stu-id="42fb1-140">Foreign</span></span></p></td>
<td><p><span data-ttu-id="42fb1-141">ИДЕНТИФИКАТОР одного пользователя в сеансе Конференции.</span><span class="sxs-lookup"><span data-stu-id="42fb1-141">ID of one user in the conference session.</span></span> <span data-ttu-id="42fb1-142">Дополнительные сведения <a href="lync-server-2013-users-table.md">можно найти в таблице Users (пользователи) в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="42fb1-142">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="42fb1-143"><strong>Усерендпоинтид</strong></span><span class="sxs-lookup"><span data-stu-id="42fb1-143"><strong>UserEndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="42fb1-144">идентификатора</span><span class="sxs-lookup"><span data-stu-id="42fb1-144">uniqueidentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="42fb1-145">GUID для идентификации экземпляра конечной точки.</span><span class="sxs-lookup"><span data-stu-id="42fb1-145">A GUID to identify the instance of endpoint.</span></span> <span data-ttu-id="42fb1-146">Например, если один пользователь входит в систему на разных компьютерах с одной и той же учетной записью, каждый из них будет иметь другой идентификатор конечной точки.</span><span class="sxs-lookup"><span data-stu-id="42fb1-146">For example, if one user logs on to different machines with the same account, then each machine will have a different endpoint ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="42fb1-147"><strong>Онбехалфофид</strong></span><span class="sxs-lookup"><span data-stu-id="42fb1-147"><strong>OnBehalfOfId</strong></span></span></p></td>
<td><p><span data-ttu-id="42fb1-148">целое</span><span class="sxs-lookup"><span data-stu-id="42fb1-148">int</span></span></p></td>
<td><p><span data-ttu-id="42fb1-149">Другом</span><span class="sxs-lookup"><span data-stu-id="42fb1-149">Foreign</span></span></p></td>
<td><p><span data-ttu-id="42fb1-150">Идентификатор пользователя, от имени которого вызывающим абонентом является.</span><span class="sxs-lookup"><span data-stu-id="42fb1-150">Indicates the ID of the user of who the caller is on behalf.</span></span> <span data-ttu-id="42fb1-151">Дополнительные сведения <a href="lync-server-2013-users-table.md">можно найти в таблице Users (пользователи) в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="42fb1-151">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="42fb1-152"><strong>Реферредбид</strong></span><span class="sxs-lookup"><span data-stu-id="42fb1-152"><strong>ReferredById</strong></span></span></p></td>
<td><p><span data-ttu-id="42fb1-153">целое</span><span class="sxs-lookup"><span data-stu-id="42fb1-153">int</span></span></p></td>
<td><p><span data-ttu-id="42fb1-154">Другом</span><span class="sxs-lookup"><span data-stu-id="42fb1-154">Foreign</span></span></p></td>
<td><p><span data-ttu-id="42fb1-155">Идентификационный номер пользователя, на который ссылается вызов.</span><span class="sxs-lookup"><span data-stu-id="42fb1-155">ID of the user by who the call is referred.</span></span> <span data-ttu-id="42fb1-156">Дополнительные сведения <a href="lync-server-2013-users-table.md">можно найти в таблице Users (пользователи) в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="42fb1-156">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="42fb1-157"><strong>Усерклиентверсионид</strong></span><span class="sxs-lookup"><span data-stu-id="42fb1-157"><strong>UserClientVersionId</strong></span></span></p></td>
<td><p><span data-ttu-id="42fb1-158">целое</span><span class="sxs-lookup"><span data-stu-id="42fb1-158">int</span></span></p></td>
<td><p><span data-ttu-id="42fb1-159">Другом</span><span class="sxs-lookup"><span data-stu-id="42fb1-159">Foreign</span></span></p></td>
<td><p><span data-ttu-id="42fb1-160">Версия клиента, используемая пользователем Конференции.</span><span class="sxs-lookup"><span data-stu-id="42fb1-160">Client version used by the conference user.</span></span> <span data-ttu-id="42fb1-161">Для получения дополнительных сведений ознакомьтесь с <a href="lync-server-2013-clientversions-table.md">таблицей клиентверсионс в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="42fb1-161">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="42fb1-162"><strong>Конфклиентверсионид</strong></span><span class="sxs-lookup"><span data-stu-id="42fb1-162"><strong>ConfClientVersionId</strong></span></span></p></td>
<td><p><span data-ttu-id="42fb1-163">целое</span><span class="sxs-lookup"><span data-stu-id="42fb1-163">int</span></span></p></td>
<td><p><span data-ttu-id="42fb1-164">Другом</span><span class="sxs-lookup"><span data-stu-id="42fb1-164">Foreign</span></span></p></td>
<td><p><span data-ttu-id="42fb1-165">Версия клиента, используемая сервером Конференции.</span><span class="sxs-lookup"><span data-stu-id="42fb1-165">Client version used by the conference server.</span></span> <span data-ttu-id="42fb1-166">Для получения дополнительных сведений ознакомьтесь с <a href="lync-server-2013-clientversions-table.md">таблицей клиентверсионс в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="42fb1-166">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="42fb1-167"><strong>Реплацедиалогидтиме</strong></span><span class="sxs-lookup"><span data-stu-id="42fb1-167"><strong>ReplaceDialogIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="42fb1-168">datetime</span><span class="sxs-lookup"><span data-stu-id="42fb1-168">datetime</span></span></p></td>
<td><p><span data-ttu-id="42fb1-169">Другом</span><span class="sxs-lookup"><span data-stu-id="42fb1-169">Foreign</span></span></p></td>
<td><p><span data-ttu-id="42fb1-170">ИДЕНТИФИКАЦИОНный номер, определяющий диалоговое окно, которое было заменено текущим сеансом.</span><span class="sxs-lookup"><span data-stu-id="42fb1-170">ID number to identify the dialog which was replaced by current session.</span></span> <span data-ttu-id="42fb1-171">Дополнительные сведения приведены <a href="lync-server-2013-dialogs-table.md">в таблице диалоговые окна Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="42fb1-171">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="42fb1-172"><strong>Реплацедиалогидсек</strong></span><span class="sxs-lookup"><span data-stu-id="42fb1-172"><strong>ReplaceDialogIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="42fb1-173">целое</span><span class="sxs-lookup"><span data-stu-id="42fb1-173">int</span></span></p></td>
<td><p><span data-ttu-id="42fb1-174">Другом</span><span class="sxs-lookup"><span data-stu-id="42fb1-174">Foreign</span></span></p></td>
<td><p><span data-ttu-id="42fb1-175">ИДЕНТИФИКАЦИОНный номер для идентификации сеанса.</span><span class="sxs-lookup"><span data-stu-id="42fb1-175">ID number to identify the session.</span></span> <span data-ttu-id="42fb1-176">Используется в сочетании с <strong>реплацесдиалогидтиме</strong> для уникальной идентификации сеанса, который заменяется этим сеансом.</span><span class="sxs-lookup"><span data-stu-id="42fb1-176">Used in conjunction with <strong>ReplacesDialogIdTime</strong> to uniquely identify a session that is replaced by this session.</span></span> <span data-ttu-id="42fb1-177">Дополнительные сведения приведены <a href="lync-server-2013-dialogs-table.md">в таблице диалоговые окна Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="42fb1-177">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="42fb1-178"><strong>Исстартедбиконфсервер</strong></span><span class="sxs-lookup"><span data-stu-id="42fb1-178"><strong>IsStartedByConfServer</strong></span></span></p></td>
<td><p><span data-ttu-id="42fb1-179">бит</span><span class="sxs-lookup"><span data-stu-id="42fb1-179">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="42fb1-180">Указывает, был ли сеанс запущен сервером конференц-связи.</span><span class="sxs-lookup"><span data-stu-id="42fb1-180">Indicates if the session started by the conferencing Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="42fb1-181"><strong>Исендедбиконфсервер</strong></span><span class="sxs-lookup"><span data-stu-id="42fb1-181"><strong>IsEndedByConfServer</strong></span></span></p></td>
<td><p><span data-ttu-id="42fb1-182">бит</span><span class="sxs-lookup"><span data-stu-id="42fb1-182">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="42fb1-183">Указывает, завершился ли сеанс сервером конференций.</span><span class="sxs-lookup"><span data-stu-id="42fb1-183">Indicates if the session ended by the conferencing server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="42fb1-184"><strong>Исусеринтернал</strong></span><span class="sxs-lookup"><span data-stu-id="42fb1-184"><strong>IsUserInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="42fb1-185">бит</span><span class="sxs-lookup"><span data-stu-id="42fb1-185">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="42fb1-186">Вход пользователя из внутреннего режима или нет.</span><span class="sxs-lookup"><span data-stu-id="42fb1-186">Whether user is logged on from internal or not.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="42fb1-187"><strong>Респонсекоде</strong></span><span class="sxs-lookup"><span data-stu-id="42fb1-187"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="42fb1-188">целое</span><span class="sxs-lookup"><span data-stu-id="42fb1-188">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="42fb1-189">Код ответа протокола запуска сеансов (SIP) в приглашение на сеанс.</span><span class="sxs-lookup"><span data-stu-id="42fb1-189">Session Initiation Protocol (SIP) response code to the session invitation.</span></span> <span data-ttu-id="42fb1-190">Это поле обычно заполняется данными, созданными на основе исходного сообщения INVITE в сеансе.</span><span class="sxs-lookup"><span data-stu-id="42fb1-190">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="42fb1-191">Если сообщение приглашения отсутствует, поле заполняется датой и временем первого соответствующего сообщения SIP (пока, CANCEL, MESSAGE или INFO).</span><span class="sxs-lookup"><span data-stu-id="42fb1-191">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="42fb1-192"><strong>ДиагностиЦид</strong></span><span class="sxs-lookup"><span data-stu-id="42fb1-192"><strong>DiagnosticId</strong></span></span></p></td>
<td><p><span data-ttu-id="42fb1-193">целое</span><span class="sxs-lookup"><span data-stu-id="42fb1-193">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="42fb1-194">Идентификатор диагностики, полученный в заголовке SIP.</span><span class="sxs-lookup"><span data-stu-id="42fb1-194">Diagnostic ID captured from SIP header.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="42fb1-195"><strong>Серверид</strong></span><span class="sxs-lookup"><span data-stu-id="42fb1-195"><strong>ServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="42fb1-196">целое</span><span class="sxs-lookup"><span data-stu-id="42fb1-196">int</span></span></p></td>
<td><p><span data-ttu-id="42fb1-197">Другом</span><span class="sxs-lookup"><span data-stu-id="42fb1-197">Foreign</span></span></p></td>
<td><p><span data-ttu-id="42fb1-198">Идентификатор сервера переднего плана, используемого для этого сеанса.</span><span class="sxs-lookup"><span data-stu-id="42fb1-198">ID of the front-end server used for this session.</span></span> <span data-ttu-id="42fb1-199">Более подробную информацию вы видите <a href="lync-server-2013-servers-table.md">в таблице Servers (серверы) в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="42fb1-199">See the <a href="lync-server-2013-servers-table.md">Servers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="42fb1-200"><strong>Пулид</strong></span><span class="sxs-lookup"><span data-stu-id="42fb1-200"><strong>PoolId</strong></span></span></p></td>
<td><p><span data-ttu-id="42fb1-201">целое</span><span class="sxs-lookup"><span data-stu-id="42fb1-201">int</span></span></p></td>
<td><p><span data-ttu-id="42fb1-202">Другом</span><span class="sxs-lookup"><span data-stu-id="42fb1-202">Foreign</span></span></p></td>
<td><p><span data-ttu-id="42fb1-203">Идентификатор пула, в котором был собран сеанс.</span><span class="sxs-lookup"><span data-stu-id="42fb1-203">ID of the pool in which the session was captured.</span></span> <span data-ttu-id="42fb1-204">Для получения дополнительных сведений ознакомьтесь с <a href="lync-server-2013-pools-table.md">таблицей пулы в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="42fb1-204">See the <a href="lync-server-2013-pools-table.md">Pools table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="42fb1-205"><strong>Медиатионсерверид</strong></span><span class="sxs-lookup"><span data-stu-id="42fb1-205"><strong>MediationServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="42fb1-206">целое</span><span class="sxs-lookup"><span data-stu-id="42fb1-206">int</span></span></p></td>
<td><p><span data-ttu-id="42fb1-207">Другом</span><span class="sxs-lookup"><span data-stu-id="42fb1-207">Foreign</span></span></p></td>
<td><p><span data-ttu-id="42fb1-208">Сервер, на котором используется этот звонок.</span><span class="sxs-lookup"><span data-stu-id="42fb1-208">The Mediation Server the call is using.</span></span> <span data-ttu-id="42fb1-209">Для получения дополнительных сведений ознакомьтесь с <a href="lync-server-2013-mediationservers-table.md">таблицей медиатионсерверс в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="42fb1-209">See the <a href="lync-server-2013-mediationservers-table.md">MediationServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="42fb1-210"><strong>Гатевайид</strong></span><span class="sxs-lookup"><span data-stu-id="42fb1-210"><strong>GatewayId</strong></span></span></p></td>
<td><p><span data-ttu-id="42fb1-211">целое</span><span class="sxs-lookup"><span data-stu-id="42fb1-211">int</span></span></p></td>
<td><p><span data-ttu-id="42fb1-212">Другом</span><span class="sxs-lookup"><span data-stu-id="42fb1-212">Foreign</span></span></p></td>
<td><p><span data-ttu-id="42fb1-213">Шлюз, который использует этот звонок.</span><span class="sxs-lookup"><span data-stu-id="42fb1-213">The gateway the call is using.</span></span> <span data-ttu-id="42fb1-214">Более подробную информацию вы увидите <a href="lync-server-2013-gateways-table.md">в таблице шлюзов в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="42fb1-214">See the <a href="lync-server-2013-gateways-table.md">Gateways table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="42fb1-215"><strong>Еджесерверид</strong></span><span class="sxs-lookup"><span data-stu-id="42fb1-215"><strong>EdgeServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="42fb1-216">целое</span><span class="sxs-lookup"><span data-stu-id="42fb1-216">int</span></span></p></td>
<td><p><span data-ttu-id="42fb1-217">Другом</span><span class="sxs-lookup"><span data-stu-id="42fb1-217">Foreign</span></span></p></td>
<td><p><span data-ttu-id="42fb1-218">Пограничный сервер, на котором используется звонок.</span><span class="sxs-lookup"><span data-stu-id="42fb1-218">The Edge Server the call is using.</span></span> <span data-ttu-id="42fb1-219">Для получения дополнительных сведений ознакомьтесь с <a href="lync-server-2013-edgeservers-table.md">таблицей еджесерверс в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="42fb1-219">See the <a href="lync-server-2013-edgeservers-table.md">EdgeServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="42fb1-220"><strong>Контенттипеид</strong></span><span class="sxs-lookup"><span data-stu-id="42fb1-220"><strong>ContentTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="42fb1-221">целое</span><span class="sxs-lookup"><span data-stu-id="42fb1-221">int</span></span></p></td>
<td><p><span data-ttu-id="42fb1-222">Другом</span><span class="sxs-lookup"><span data-stu-id="42fb1-222">Foreign</span></span></p></td>
<td><p><span data-ttu-id="42fb1-223">Тип контента, используемый в сеансе.</span><span class="sxs-lookup"><span data-stu-id="42fb1-223">Content type used in the session.</span></span> <span data-ttu-id="42fb1-224">Дополнительные сведения приведены <a href="lync-server-2013-contenttypes-table.md">в таблице ContentTypes в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="42fb1-224">See the <a href="lync-server-2013-contenttypes-table.md">ContentTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="42fb1-225"><strong>Инвитетиме</strong></span><span class="sxs-lookup"><span data-stu-id="42fb1-225"><strong>InviteTime</strong></span></span></p></td>
<td><p><span data-ttu-id="42fb1-226">datetime</span><span class="sxs-lookup"><span data-stu-id="42fb1-226">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="42fb1-227">Время первого запроса приглашения.</span><span class="sxs-lookup"><span data-stu-id="42fb1-227">The time of the first INVITE request.</span></span> <span data-ttu-id="42fb1-228">Это поле обычно заполняется данными, созданными на основе исходного сообщения INVITE в сеансе.</span><span class="sxs-lookup"><span data-stu-id="42fb1-228">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="42fb1-229">Если сообщение приглашения отсутствует, поле заполняется датой и временем первого соответствующего сообщения SIP (пока, CANCEL, MESSAGE или INFO).</span><span class="sxs-lookup"><span data-stu-id="42fb1-229">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="42fb1-230"><strong>Респонсетиме</strong></span><span class="sxs-lookup"><span data-stu-id="42fb1-230"><strong>ResponseTime</strong></span></span></p></td>
<td><p><span data-ttu-id="42fb1-231">datetime</span><span class="sxs-lookup"><span data-stu-id="42fb1-231">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="42fb1-232">Время первого ответа SIP.</span><span class="sxs-lookup"><span data-stu-id="42fb1-232">Time of the first SIP RESPONSE.</span></span> <span data-ttu-id="42fb1-233">Это поле обычно заполняется данными, созданными на основе исходного сообщения INVITE в сеансе.</span><span class="sxs-lookup"><span data-stu-id="42fb1-233">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="42fb1-234">Если сообщение приглашения отсутствует, поле заполняется датой и временем первого соответствующего сообщения SIP (пока, CANCEL, MESSAGE или INFO).</span><span class="sxs-lookup"><span data-stu-id="42fb1-234">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="42fb1-235"><strong>Сессионендтиме</strong></span><span class="sxs-lookup"><span data-stu-id="42fb1-235"><strong>SessionEndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="42fb1-236">datetime</span><span class="sxs-lookup"><span data-stu-id="42fb1-236">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="42fb1-237">Время завершения сеанса.</span><span class="sxs-lookup"><span data-stu-id="42fb1-237">The time when the session is ended.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="42fb1-238"><strong>Уритипеид</strong></span><span class="sxs-lookup"><span data-stu-id="42fb1-238"><strong>UriTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="42fb1-239">tinyint</span><span class="sxs-lookup"><span data-stu-id="42fb1-239">tinyint</span></span></p></td>
<td><p><span data-ttu-id="42fb1-240">Другом</span><span class="sxs-lookup"><span data-stu-id="42fb1-240">Foreign</span></span></p></td>
<td><p><span data-ttu-id="42fb1-241">Имеет значение типа URI MCU из <a href="lync-server-2013-uritypes-table.md">таблицы уритипес в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="42fb1-241">Contains the MCU URI type value from the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a>.</span></span> <span data-ttu-id="42fb1-242">Это поле используется для повышения производительности запроса.</span><span class="sxs-lookup"><span data-stu-id="42fb1-242">This field is used for improving query performance.</span></span></p>
<p><span data-ttu-id="42fb1-243">Это поле было введено в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="42fb1-243">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="42fb1-244"><strong>Усерфлаг</strong></span><span class="sxs-lookup"><span data-stu-id="42fb1-244"><strong>UserFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="42fb1-245">smallint</span><span class="sxs-lookup"><span data-stu-id="42fb1-245">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="42fb1-246">Битовый набор, обозначающий атрибуты пользователя.</span><span class="sxs-lookup"><span data-stu-id="42fb1-246">A bit set that indicates the user attributes.</span></span> <span data-ttu-id="42fb1-247">Следующие определения атрибутов перечислены ниже.</span><span class="sxs-lookup"><span data-stu-id="42fb1-247">The following attribute definitions are listed:</span></span></p>
<ul>
<li><p><span data-ttu-id="42fb1-248">Интеграция с настольным телефоном 1</span><span class="sxs-lookup"><span data-stu-id="42fb1-248">Integrated with desktop phone - 1</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="42fb1-249"><strong>Каллфлаг</strong></span><span class="sxs-lookup"><span data-stu-id="42fb1-249"><strong>CallFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="42fb1-250">smallint</span><span class="sxs-lookup"><span data-stu-id="42fb1-250">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="42fb1-251">Битовый набор, обозначающий атрибуты вызова.</span><span class="sxs-lookup"><span data-stu-id="42fb1-251">A bit set that indicates the call attributes.</span></span> <span data-ttu-id="42fb1-252">Следующие определения атрибутов перечислены ниже.</span><span class="sxs-lookup"><span data-stu-id="42fb1-252">The following attribute definitions are listed:</span></span></p>
<ul>
<li><p><span data-ttu-id="42fb1-253">Сеанс с повторной попыткой 1</span><span class="sxs-lookup"><span data-stu-id="42fb1-253">Retried Session - 1</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


<span data-ttu-id="42fb1-254">\*Для большинства сеансов для Сессионидсек будет задано значение 1.</span><span class="sxs-lookup"><span data-stu-id="42fb1-254">\* For most sessions, SessionIdSeq will have the value of 1.</span></span> <span data-ttu-id="42fb1-255">Если несколько сеансов начинаются в одно и то же время, Сессионидсек для одного из них будет равен 1, а для другого — 2 и т. д.</span><span class="sxs-lookup"><span data-stu-id="42fb1-255">If multiple sessions start at exactly the same time, the SessionIdSeq for one will be 1, for another will be 2, and so on.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

