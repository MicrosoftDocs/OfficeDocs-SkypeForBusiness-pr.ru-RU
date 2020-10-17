---
title: 'Lync Server 2013: таблица таблица conferencesessiondetails'
description: 'Lync Server 2013: таблица таблица conferencesessiondetails.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: ConferenceSessionDetails table
ms:assetid: 9eae6a54-69fd-4966-aa17-7ecee1297ad8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412741(v=OCS.15)
ms:contentKeyID: 48184925
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0d101eb1607e366ab814e60acaeee80820fe87c5
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566785"
---
# <a name="conferencesessiondetails-table-in-lync-server-2013"></a><span data-ttu-id="040ad-103">Таблица Таблица conferencesessiondetails в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="040ad-103">ConferenceSessionDetails table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="040ad-104">_**Последнее изменение темы:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="040ad-104">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="040ad-105">Каждая запись представляет один сеанс конференц-связи, который может быть либо сеансом с центром конференций, либо сеансом с конкретным сервером конференций.</span><span class="sxs-lookup"><span data-stu-id="040ad-105">Each record represents one conference session, which could be either the session with Focus or the session with a specific conferencing server.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="040ad-106">Столбец</span><span class="sxs-lookup"><span data-stu-id="040ad-106">Column</span></span></th>
<th><span data-ttu-id="040ad-107">Тип данных</span><span class="sxs-lookup"><span data-stu-id="040ad-107">Data Type</span></span></th>
<th><span data-ttu-id="040ad-108">Ключ или индекс</span><span class="sxs-lookup"><span data-stu-id="040ad-108">Key/Index</span></span></th>
<th><span data-ttu-id="040ad-109">Сведения</span><span class="sxs-lookup"><span data-stu-id="040ad-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="040ad-110"><strong>сессионидтиме</strong></span><span class="sxs-lookup"><span data-stu-id="040ad-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="040ad-111">Отличным</span><span class="sxs-lookup"><span data-stu-id="040ad-111">Datetime</span></span></p></td>
<td><p><span data-ttu-id="040ad-112">Первичный, внешний</span><span class="sxs-lookup"><span data-stu-id="040ad-112">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="040ad-113">Время запроса сеанса; используется вместе с <strong>SessionIdSeq</strong> для уникальной идентификации сеанса конференц-связи.</span><span class="sxs-lookup"><span data-stu-id="040ad-113">Time of session request; used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a conference session.</span></span> <span data-ttu-id="040ad-114">Дополнительные сведения см. <a href="lync-server-2013-dialogs-table.md">в таблице диалоговых окон в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="040ad-114">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="040ad-115"><strong>сессионидсек</strong></span><span class="sxs-lookup"><span data-stu-id="040ad-115"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="040ad-116">int</span><span class="sxs-lookup"><span data-stu-id="040ad-116">int</span></span></p></td>
<td><p><span data-ttu-id="040ad-117">Основной, внешний</span><span class="sxs-lookup"><span data-stu-id="040ad-117">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="040ad-118">Идентификатор для идентификации сеанса.</span><span class="sxs-lookup"><span data-stu-id="040ad-118">ID number to identify the session.</span></span> <span data-ttu-id="040ad-119">Используется совместно с <strong>сессионидтиме</strong> для уникальной идентификации сеанса конференц-связи.</span><span class="sxs-lookup"><span data-stu-id="040ad-119">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a conference session.</span></span> <span data-ttu-id="040ad-120">Дополнительные сведения см. <a href="lync-server-2013-dialogs-table.md">в таблице диалоговых окон в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="040ad-120">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span> *</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="040ad-121"><strong>конференцеуриид</strong></span><span class="sxs-lookup"><span data-stu-id="040ad-121"><strong>ConferenceUriId</strong></span></span></p></td>
<td><p><span data-ttu-id="040ad-122">int</span><span class="sxs-lookup"><span data-stu-id="040ad-122">int</span></span></p></td>
<td><p><span data-ttu-id="040ad-123">Правительства</span><span class="sxs-lookup"><span data-stu-id="040ad-123">Foreign</span></span></p></td>
<td><p><span data-ttu-id="040ad-124">URI конференции с центром конференций, связанной с этим сеансом.</span><span class="sxs-lookup"><span data-stu-id="040ad-124">Focus conference URI related to this session.</span></span> <span data-ttu-id="040ad-125">Дополнительные сведения см. <a href="lync-server-2013-conferenceuris-table.md">в таблице таблица conferenceuris в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="040ad-125">See the <a href="lync-server-2013-conferenceuris-table.md">ConferenceUris table in Lync Server 2013</a> for more information.</span></span> <span data-ttu-id="040ad-126">Это URI конференции на основе центра конференций.</span><span class="sxs-lookup"><span data-stu-id="040ad-126">This URI is a Focus-based conference URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="040ad-127"><strong>конфинстанце</strong></span><span class="sxs-lookup"><span data-stu-id="040ad-127"><strong>ConfInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="040ad-128">Идентификатора</span><span class="sxs-lookup"><span data-stu-id="040ad-128">uniqueIdentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="040ad-129">Идентификатор, который различается для экземпляров повторяющихся конференций.</span><span class="sxs-lookup"><span data-stu-id="040ad-129">Identifier that differentiates between instances of recurring conferences.</span></span> <span data-ttu-id="040ad-130">Каждый повторяющийся экземпляр конференции имеет один и тот же ConferenceURI, но разное значение ConfInstance.</span><span class="sxs-lookup"><span data-stu-id="040ad-130">Each recurring conference instance has the same ConferenceURI but a different ConfInstance value.</span></span></p>
<p><span data-ttu-id="040ad-131">Это поле было введено в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="040ad-131">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="040ad-132"><strong>мкуконференцеуриид</strong></span><span class="sxs-lookup"><span data-stu-id="040ad-132"><strong>McuConferenceUriId</strong></span></span></p></td>
<td><p><span data-ttu-id="040ad-133">int</span><span class="sxs-lookup"><span data-stu-id="040ad-133">int</span></span></p></td>
<td><p><span data-ttu-id="040ad-134">Правительства</span><span class="sxs-lookup"><span data-stu-id="040ad-134">Foreign</span></span></p></td>
<td><p><span data-ttu-id="040ad-135">URI конференции с сервером конференций, относящейся к этому сеансу.</span><span class="sxs-lookup"><span data-stu-id="040ad-135">Conferencing server conference URI related to this session.</span></span> <span data-ttu-id="040ad-136">Дополнительные сведения см. <a href="lync-server-2013-conferenceuris-table.md">в таблице таблица conferenceuris в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="040ad-136">See the <a href="lync-server-2013-conferenceuris-table.md">ConferenceUris table in Lync Server 2013</a> for more information.</span></span> <span data-ttu-id="040ad-137">Это URI конференции на основе сервера конференций.</span><span class="sxs-lookup"><span data-stu-id="040ad-137">This URI is the conferencing server-based conference URI.</span></span> <span data-ttu-id="040ad-138">Для сеансов конференц-связи с центром конференций этот столбец будет пустым.</span><span class="sxs-lookup"><span data-stu-id="040ad-138">For Focus conference sessions, this column will be null.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="040ad-139"><strong>UserId</strong></span><span class="sxs-lookup"><span data-stu-id="040ad-139"><strong>UserId</strong></span></span></p></td>
<td><p><span data-ttu-id="040ad-140">int</span><span class="sxs-lookup"><span data-stu-id="040ad-140">int</span></span></p></td>
<td><p><span data-ttu-id="040ad-141">Правительства</span><span class="sxs-lookup"><span data-stu-id="040ad-141">Foreign</span></span></p></td>
<td><p><span data-ttu-id="040ad-142">Идентификатор одного пользователя в этом сеансе конференц-связи.</span><span class="sxs-lookup"><span data-stu-id="040ad-142">ID of one user in the conference session.</span></span> <span data-ttu-id="040ad-143">Дополнительные сведения см. <a href="lync-server-2013-users-table.md">в таблице "Пользователи" в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="040ad-143">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="040ad-144"><strong>усерендпоинтид</strong></span><span class="sxs-lookup"><span data-stu-id="040ad-144"><strong>UserEndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="040ad-145">идентификатора</span><span class="sxs-lookup"><span data-stu-id="040ad-145">uniqueidentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="040ad-p107">GUID для идентификации экземпляра конечной точки. Например, если один пользователь входит на разные компьютеры с одной и той же учетной записью, то все эти компьютеры будут иметь разные идентификаторы конечной точки.</span><span class="sxs-lookup"><span data-stu-id="040ad-p107">A GUID to identify the instance of endpoint. For example, if one user logs on to different machines with the same account, then each machine will have a different endpoint ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="040ad-148"><strong>онбехалфофид</strong></span><span class="sxs-lookup"><span data-stu-id="040ad-148"><strong>OnBehalfOfId</strong></span></span></p></td>
<td><p><span data-ttu-id="040ad-149">int</span><span class="sxs-lookup"><span data-stu-id="040ad-149">int</span></span></p></td>
<td><p><span data-ttu-id="040ad-150">Правительства</span><span class="sxs-lookup"><span data-stu-id="040ad-150">Foreign</span></span></p></td>
<td><p><span data-ttu-id="040ad-151">Определяет идентификатор пользователя, которого представляет вызывающий абонент.</span><span class="sxs-lookup"><span data-stu-id="040ad-151">Indicates the ID of the user of who the caller is on behalf.</span></span> <span data-ttu-id="040ad-152">Дополнительные сведения см. <a href="lync-server-2013-users-table.md">в таблице "Пользователи" в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="040ad-152">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="040ad-153"><strong>реферредбид</strong></span><span class="sxs-lookup"><span data-stu-id="040ad-153"><strong>ReferredById</strong></span></span></p></td>
<td><p><span data-ttu-id="040ad-154">int</span><span class="sxs-lookup"><span data-stu-id="040ad-154">int</span></span></p></td>
<td><p><span data-ttu-id="040ad-155">Правительства</span><span class="sxs-lookup"><span data-stu-id="040ad-155">Foreign</span></span></p></td>
<td><p><span data-ttu-id="040ad-156">Идентификатор пользователя, который ссылается на вызов.</span><span class="sxs-lookup"><span data-stu-id="040ad-156">ID of the user by who the call is referred.</span></span> <span data-ttu-id="040ad-157">Дополнительные сведения см. <a href="lync-server-2013-users-table.md">в таблице "Пользователи" в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="040ad-157">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="040ad-158"><strong>усерклиентверсионид</strong></span><span class="sxs-lookup"><span data-stu-id="040ad-158"><strong>UserClientVersionId</strong></span></span></p></td>
<td><p><span data-ttu-id="040ad-159">int</span><span class="sxs-lookup"><span data-stu-id="040ad-159">int</span></span></p></td>
<td><p><span data-ttu-id="040ad-160">Правительства</span><span class="sxs-lookup"><span data-stu-id="040ad-160">Foreign</span></span></p></td>
<td><p><span data-ttu-id="040ad-161">Версия клиента, используемого пользователем конференц-связи.</span><span class="sxs-lookup"><span data-stu-id="040ad-161">Client version used by the conference user.</span></span> <span data-ttu-id="040ad-162">Дополнительные сведения см. <a href="lync-server-2013-clientversions-table.md">в таблице таблица clientversions в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="040ad-162">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="040ad-163"><strong>конфклиентверсионид</strong></span><span class="sxs-lookup"><span data-stu-id="040ad-163"><strong>ConfClientVersionId</strong></span></span></p></td>
<td><p><span data-ttu-id="040ad-164">int</span><span class="sxs-lookup"><span data-stu-id="040ad-164">int</span></span></p></td>
<td><p><span data-ttu-id="040ad-165">Правительства</span><span class="sxs-lookup"><span data-stu-id="040ad-165">Foreign</span></span></p></td>
<td><p><span data-ttu-id="040ad-166">Версия клиента, используемого сервером конференций.</span><span class="sxs-lookup"><span data-stu-id="040ad-166">Client version used by the conference server.</span></span> <span data-ttu-id="040ad-167">Дополнительные сведения см. <a href="lync-server-2013-clientversions-table.md">в таблице таблица clientversions в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="040ad-167">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="040ad-168"><strong>реплацедиалогидтиме</strong></span><span class="sxs-lookup"><span data-stu-id="040ad-168"><strong>ReplaceDialogIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="040ad-169">datetime</span><span class="sxs-lookup"><span data-stu-id="040ad-169">datetime</span></span></p></td>
<td><p><span data-ttu-id="040ad-170">Правительства</span><span class="sxs-lookup"><span data-stu-id="040ad-170">Foreign</span></span></p></td>
<td><p><span data-ttu-id="040ad-171">Идентификационный номер для определения диалога, замененного текущим сеансом.</span><span class="sxs-lookup"><span data-stu-id="040ad-171">ID number to identify the dialog which was replaced by current session.</span></span> <span data-ttu-id="040ad-172">Дополнительные сведения см. <a href="lync-server-2013-dialogs-table.md">в таблице диалоговых окон в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="040ad-172">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="040ad-173"><strong>реплацедиалогидсек</strong></span><span class="sxs-lookup"><span data-stu-id="040ad-173"><strong>ReplaceDialogIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="040ad-174">int</span><span class="sxs-lookup"><span data-stu-id="040ad-174">int</span></span></p></td>
<td><p><span data-ttu-id="040ad-175">Правительства</span><span class="sxs-lookup"><span data-stu-id="040ad-175">Foreign</span></span></p></td>
<td><p><span data-ttu-id="040ad-176">Идентификатор для идентификации сеанса.</span><span class="sxs-lookup"><span data-stu-id="040ad-176">ID number to identify the session.</span></span> <span data-ttu-id="040ad-177">Используется в сочетании с <strong>ReplacesDialogIdTime</strong> для уникальной идентификации сеанса.</span><span class="sxs-lookup"><span data-stu-id="040ad-177">Used in conjunction with <strong>ReplacesDialogIdTime</strong> to uniquely identify a session that is replaced by this session.</span></span> <span data-ttu-id="040ad-178">Дополнительные сведения см. <a href="lync-server-2013-dialogs-table.md">в таблице диалоговых окон в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="040ad-178">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="040ad-179"><strong>исстартедбиконфсервер</strong></span><span class="sxs-lookup"><span data-stu-id="040ad-179"><strong>IsStartedByConfServer</strong></span></span></p></td>
<td><p><span data-ttu-id="040ad-180">Битовая</span><span class="sxs-lookup"><span data-stu-id="040ad-180">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="040ad-181">Показывает, был ли сеанс начат сервером конференций.</span><span class="sxs-lookup"><span data-stu-id="040ad-181">Indicates if the session started by the conferencing Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="040ad-182"><strong>исендедбиконфсервер</strong></span><span class="sxs-lookup"><span data-stu-id="040ad-182"><strong>IsEndedByConfServer</strong></span></span></p></td>
<td><p><span data-ttu-id="040ad-183">Битовая</span><span class="sxs-lookup"><span data-stu-id="040ad-183">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="040ad-184">Показывает, был ли сеанс завершен сервером конференций.</span><span class="sxs-lookup"><span data-stu-id="040ad-184">Indicates if the session ended by the conferencing server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="040ad-185"><strong>исусеринтернал</strong></span><span class="sxs-lookup"><span data-stu-id="040ad-185"><strong>IsUserInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="040ad-186">Битовая</span><span class="sxs-lookup"><span data-stu-id="040ad-186">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="040ad-187">Вошел ли пользователь из внутренней сети.</span><span class="sxs-lookup"><span data-stu-id="040ad-187">Whether user is logged on from internal or not.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="040ad-188"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="040ad-188"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="040ad-189">int</span><span class="sxs-lookup"><span data-stu-id="040ad-189">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="040ad-190">Код SIP-ответа на приглашение в сеанс.</span><span class="sxs-lookup"><span data-stu-id="040ad-190">Session Initiation Protocol (SIP) response code to the session invitation.</span></span> <span data-ttu-id="040ad-191">Это поле обычно заполняется данными, генерируемыми из исходного сообщения INVITE в сеансе.</span><span class="sxs-lookup"><span data-stu-id="040ad-191">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="040ad-192">Если сообщения INVITE нет, поле заполняется датой и временем первого релевантного SIP-сообщения (BYE, CANCEL, MESSAGE или INFO).</span><span class="sxs-lookup"><span data-stu-id="040ad-192">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="040ad-193"><strong>диагностиЦид</strong></span><span class="sxs-lookup"><span data-stu-id="040ad-193"><strong>DiagnosticId</strong></span></span></p></td>
<td><p><span data-ttu-id="040ad-194">int</span><span class="sxs-lookup"><span data-stu-id="040ad-194">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="040ad-195">Диагностический идентификатор, захваченный из заголовка SIP.</span><span class="sxs-lookup"><span data-stu-id="040ad-195">Diagnostic ID captured from SIP header.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="040ad-196"><strong>ServerId</strong></span><span class="sxs-lookup"><span data-stu-id="040ad-196"><strong>ServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="040ad-197">int</span><span class="sxs-lookup"><span data-stu-id="040ad-197">int</span></span></p></td>
<td><p><span data-ttu-id="040ad-198">Правительства</span><span class="sxs-lookup"><span data-stu-id="040ad-198">Foreign</span></span></p></td>
<td><p><span data-ttu-id="040ad-199">Идентификатор сервера переднего плана, используемого для этого сеанса.</span><span class="sxs-lookup"><span data-stu-id="040ad-199">ID of the front-end server used for this session.</span></span> <span data-ttu-id="040ad-200">Дополнительные сведения см. <a href="lync-server-2013-servers-table.md">в таблице Servers в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="040ad-200">See the <a href="lync-server-2013-servers-table.md">Servers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="040ad-201"><strong>пулид</strong></span><span class="sxs-lookup"><span data-stu-id="040ad-201"><strong>PoolId</strong></span></span></p></td>
<td><p><span data-ttu-id="040ad-202">int</span><span class="sxs-lookup"><span data-stu-id="040ad-202">int</span></span></p></td>
<td><p><span data-ttu-id="040ad-203">Правительства</span><span class="sxs-lookup"><span data-stu-id="040ad-203">Foreign</span></span></p></td>
<td><p><span data-ttu-id="040ad-204">Идентификатор пула, в котором был записан сеанс.</span><span class="sxs-lookup"><span data-stu-id="040ad-204">ID of the pool in which the session was captured.</span></span> <span data-ttu-id="040ad-205">Дополнительные сведения см. <a href="lync-server-2013-pools-table.md">в таблице Pools в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="040ad-205">See the <a href="lync-server-2013-pools-table.md">Pools table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="040ad-206"><strong>медиатионсерверид</strong></span><span class="sxs-lookup"><span data-stu-id="040ad-206"><strong>MediationServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="040ad-207">int</span><span class="sxs-lookup"><span data-stu-id="040ad-207">int</span></span></p></td>
<td><p><span data-ttu-id="040ad-208">Правительства</span><span class="sxs-lookup"><span data-stu-id="040ad-208">Foreign</span></span></p></td>
<td><p><span data-ttu-id="040ad-209">Сервер-посредник, который использовался вызовом.</span><span class="sxs-lookup"><span data-stu-id="040ad-209">The Mediation Server the call is using.</span></span> <span data-ttu-id="040ad-210">Дополнительные сведения см. <a href="lync-server-2013-mediationservers-table.md">в таблице таблица mediationservers в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="040ad-210">See the <a href="lync-server-2013-mediationservers-table.md">MediationServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="040ad-211"><strong>гатевайид</strong></span><span class="sxs-lookup"><span data-stu-id="040ad-211"><strong>GatewayId</strong></span></span></p></td>
<td><p><span data-ttu-id="040ad-212">int</span><span class="sxs-lookup"><span data-stu-id="040ad-212">int</span></span></p></td>
<td><p><span data-ttu-id="040ad-213">Правительства</span><span class="sxs-lookup"><span data-stu-id="040ad-213">Foreign</span></span></p></td>
<td><p><span data-ttu-id="040ad-214">Шлюз, который использовался вызовом.</span><span class="sxs-lookup"><span data-stu-id="040ad-214">The gateway the call is using.</span></span> <span data-ttu-id="040ad-215">Более подробную информацию можно узнать <a href="lync-server-2013-gateways-table.md">в таблице шлюзы в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="040ad-215">See the <a href="lync-server-2013-gateways-table.md">Gateways table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="040ad-216"><strong>еджесерверид</strong></span><span class="sxs-lookup"><span data-stu-id="040ad-216"><strong>EdgeServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="040ad-217">int</span><span class="sxs-lookup"><span data-stu-id="040ad-217">int</span></span></p></td>
<td><p><span data-ttu-id="040ad-218">Правительства</span><span class="sxs-lookup"><span data-stu-id="040ad-218">Foreign</span></span></p></td>
<td><p><span data-ttu-id="040ad-219">Пограничный сервер, который использовался вызовом.</span><span class="sxs-lookup"><span data-stu-id="040ad-219">The Edge Server the call is using.</span></span> <span data-ttu-id="040ad-220">Дополнительные сведения см. <a href="lync-server-2013-edgeservers-table.md">в таблице таблица edgeservers в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="040ad-220">See the <a href="lync-server-2013-edgeservers-table.md">EdgeServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="040ad-221"><strong>ContentTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="040ad-221"><strong>ContentTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="040ad-222">int</span><span class="sxs-lookup"><span data-stu-id="040ad-222">int</span></span></p></td>
<td><p><span data-ttu-id="040ad-223">Правительства</span><span class="sxs-lookup"><span data-stu-id="040ad-223">Foreign</span></span></p></td>
<td><p><span data-ttu-id="040ad-224">Тип контента, используемый в сеансе.</span><span class="sxs-lookup"><span data-stu-id="040ad-224">Content type used in the session.</span></span> <span data-ttu-id="040ad-225">Для получения дополнительных сведений см <a href="lync-server-2013-contenttypes-table.md">таблицу ContentTypes в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="040ad-225">See the <a href="lync-server-2013-contenttypes-table.md">ContentTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="040ad-226"><strong>инвитетиме</strong></span><span class="sxs-lookup"><span data-stu-id="040ad-226"><strong>InviteTime</strong></span></span></p></td>
<td><p><span data-ttu-id="040ad-227">datetime</span><span class="sxs-lookup"><span data-stu-id="040ad-227">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="040ad-p121">Время первого запроса INVITE. Это поле обычно заполняется данными, генерируемыми из исходного сообщения INVITE в сеансе. Если сообщения INVITE нет, поле заполняется датой и временем первого релевантного SIP-сообщения (BYE, CANCEL, MESSAGE или INFO).</span><span class="sxs-lookup"><span data-stu-id="040ad-p121">The time of the first INVITE request. This field is typically populated by data generated from the initial INVITE message in the session. If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="040ad-231"><strong>респонсетиме</strong></span><span class="sxs-lookup"><span data-stu-id="040ad-231"><strong>ResponseTime</strong></span></span></p></td>
<td><p><span data-ttu-id="040ad-232">datetime</span><span class="sxs-lookup"><span data-stu-id="040ad-232">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="040ad-233">Время первого ответа SIP.</span><span class="sxs-lookup"><span data-stu-id="040ad-233">Time of the first SIP RESPONSE.</span></span> <span data-ttu-id="040ad-234">Это поле обычно заполняется данными, генерируемыми из исходного сообщения INVITE в сеансе.</span><span class="sxs-lookup"><span data-stu-id="040ad-234">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="040ad-235">Если сообщения INVITE нет, поле заполняется датой и временем первого релевантного SIP-сообщения (BYE, CANCEL, MESSAGE или INFO).</span><span class="sxs-lookup"><span data-stu-id="040ad-235">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="040ad-236"><strong>сессионендтиме</strong></span><span class="sxs-lookup"><span data-stu-id="040ad-236"><strong>SessionEndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="040ad-237">datetime</span><span class="sxs-lookup"><span data-stu-id="040ad-237">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="040ad-238">Время окончания сеанса.</span><span class="sxs-lookup"><span data-stu-id="040ad-238">The time when the session is ended.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="040ad-239"><strong>уритипеид</strong></span><span class="sxs-lookup"><span data-stu-id="040ad-239"><strong>UriTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="040ad-240">tinyint</span><span class="sxs-lookup"><span data-stu-id="040ad-240">tinyint</span></span></p></td>
<td><p><span data-ttu-id="040ad-241">Правительства</span><span class="sxs-lookup"><span data-stu-id="040ad-241">Foreign</span></span></p></td>
<td><p><span data-ttu-id="040ad-242">Содержит значение типа универсального кода ресурса (URI) MCU из <a href="lync-server-2013-uritypes-table.md">таблицы таблица uritypes в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="040ad-242">Contains the MCU URI type value from the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a>.</span></span> <span data-ttu-id="040ad-243">Это поле используется для повышения производительности запроса.</span><span class="sxs-lookup"><span data-stu-id="040ad-243">This field is used for improving query performance.</span></span></p>
<p><span data-ttu-id="040ad-244">Это поле было введено в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="040ad-244">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="040ad-245"><strong>усерфлаг</strong></span><span class="sxs-lookup"><span data-stu-id="040ad-245"><strong>UserFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="040ad-246">smallint</span><span class="sxs-lookup"><span data-stu-id="040ad-246">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="040ad-p124">Набор битов, указывающий атрибуты пользователя. Перечисляются следующие определения атрибутов:</span><span class="sxs-lookup"><span data-stu-id="040ad-p124">A bit set that indicates the user attributes. The following attribute definitions are listed:</span></span></p>
<ul>
<li><p><span data-ttu-id="040ad-249">интеграция со стационарным телефоном — 1</span><span class="sxs-lookup"><span data-stu-id="040ad-249">Integrated with desktop phone - 1</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="040ad-250"><strong>каллфлаг</strong></span><span class="sxs-lookup"><span data-stu-id="040ad-250"><strong>CallFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="040ad-251">smallint</span><span class="sxs-lookup"><span data-stu-id="040ad-251">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="040ad-p125">Набор битов, указывающий атрибуты вызова. Перечисляются следующие определения атрибутов:</span><span class="sxs-lookup"><span data-stu-id="040ad-p125">A bit set that indicates the call attributes. The following attribute definitions are listed:</span></span></p>
<ul>
<li><p><span data-ttu-id="040ad-254">повторный сеанс — 1</span><span class="sxs-lookup"><span data-stu-id="040ad-254">Retried Session - 1</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


<span data-ttu-id="040ad-255">\* Для большинства сеансов Сессионидсек будет иметь значение 1.</span><span class="sxs-lookup"><span data-stu-id="040ad-255">\* For most sessions, SessionIdSeq will have the value of 1.</span></span> <span data-ttu-id="040ad-256">Если несколько сеансов начинаются в одно и то же время, для одного из них SessionIdSeq будет иметь значение 1, для другого — 2 и т. д.</span><span class="sxs-lookup"><span data-stu-id="040ad-256">If multiple sessions start at exactly the same time, the SessionIdSeq for one will be 1, for another will be 2, and so on.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

