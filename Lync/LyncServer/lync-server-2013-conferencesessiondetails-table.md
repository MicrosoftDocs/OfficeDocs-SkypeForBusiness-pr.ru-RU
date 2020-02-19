---
title: 'Lync Server 2013: таблица таблица conferencesessiondetails'
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
ms.openlocfilehash: f7f0907b6c92d3ca5ed1adf7f1a991242d6ddeb1
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42140572"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="conferencesessiondetails-table-in-lync-server-2013"></a><span data-ttu-id="382cf-102">Таблица Таблица conferencesessiondetails в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="382cf-102">ConferenceSessionDetails table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="382cf-103">_**Последнее изменение темы:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="382cf-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="382cf-104">Каждая запись представляет один сеанс конференц-связи, который может быть либо сеансом с центром конференций, либо сеансом с конкретным сервером конференций.</span><span class="sxs-lookup"><span data-stu-id="382cf-104">Each record represents one conference session, which could be either the session with Focus or the session with a specific conferencing server.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="382cf-105">Столбец</span><span class="sxs-lookup"><span data-stu-id="382cf-105">Column</span></span></th>
<th><span data-ttu-id="382cf-106">Тип данных</span><span class="sxs-lookup"><span data-stu-id="382cf-106">Data Type</span></span></th>
<th><span data-ttu-id="382cf-107">Ключ или индекс</span><span class="sxs-lookup"><span data-stu-id="382cf-107">Key/Index</span></span></th>
<th><span data-ttu-id="382cf-108">Сведения</span><span class="sxs-lookup"><span data-stu-id="382cf-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="382cf-109"><strong>сессионидтиме</strong></span><span class="sxs-lookup"><span data-stu-id="382cf-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="382cf-110">Отличным</span><span class="sxs-lookup"><span data-stu-id="382cf-110">Datetime</span></span></p></td>
<td><p><span data-ttu-id="382cf-111">Первичный, внешний</span><span class="sxs-lookup"><span data-stu-id="382cf-111">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="382cf-112">Время запроса сеанса; используется вместе с <strong>SessionIdSeq</strong> для уникальной идентификации сеанса конференц-связи.</span><span class="sxs-lookup"><span data-stu-id="382cf-112">Time of session request; used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a conference session.</span></span> <span data-ttu-id="382cf-113">Дополнительные сведения см. <a href="lync-server-2013-dialogs-table.md">в таблице диалоговых окон в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="382cf-113">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="382cf-114"><strong>сессионидсек</strong></span><span class="sxs-lookup"><span data-stu-id="382cf-114"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="382cf-115">int</span><span class="sxs-lookup"><span data-stu-id="382cf-115">int</span></span></p></td>
<td><p><span data-ttu-id="382cf-116">Основной, внешний</span><span class="sxs-lookup"><span data-stu-id="382cf-116">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="382cf-117">Идентификатор сеанса.</span><span class="sxs-lookup"><span data-stu-id="382cf-117">ID number to identify the session.</span></span> <span data-ttu-id="382cf-118">Используется совместно с <strong>сессионидтиме</strong> для уникальной идентификации сеанса конференц-связи.</span><span class="sxs-lookup"><span data-stu-id="382cf-118">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a conference session.</span></span> <span data-ttu-id="382cf-119">Дополнительные сведения см. <a href="lync-server-2013-dialogs-table.md">в таблице диалоговых окон в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="382cf-119">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span> *</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="382cf-120"><strong>конференцеуриид</strong></span><span class="sxs-lookup"><span data-stu-id="382cf-120"><strong>ConferenceUriId</strong></span></span></p></td>
<td><p><span data-ttu-id="382cf-121">int</span><span class="sxs-lookup"><span data-stu-id="382cf-121">int</span></span></p></td>
<td><p><span data-ttu-id="382cf-122">Правительства</span><span class="sxs-lookup"><span data-stu-id="382cf-122">Foreign</span></span></p></td>
<td><p><span data-ttu-id="382cf-123">URI конференции с центром конференций, связанной с этим сеансом.</span><span class="sxs-lookup"><span data-stu-id="382cf-123">Focus conference URI related to this session.</span></span> <span data-ttu-id="382cf-124">Дополнительные сведения см. <a href="lync-server-2013-conferenceuris-table.md">в таблице таблица conferenceuris в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="382cf-124">See the <a href="lync-server-2013-conferenceuris-table.md">ConferenceUris table in Lync Server 2013</a> for more information.</span></span> <span data-ttu-id="382cf-125">Это URI конференции на основе центра конференций.</span><span class="sxs-lookup"><span data-stu-id="382cf-125">This URI is a Focus-based conference URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="382cf-126"><strong>конфинстанце</strong></span><span class="sxs-lookup"><span data-stu-id="382cf-126"><strong>ConfInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="382cf-127">Идентификатора</span><span class="sxs-lookup"><span data-stu-id="382cf-127">uniqueIdentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="382cf-128">Идентификатор, который различается для экземпляров повторяющихся конференций.</span><span class="sxs-lookup"><span data-stu-id="382cf-128">Identifier that differentiates between instances of recurring conferences.</span></span> <span data-ttu-id="382cf-129">Каждый повторяющийся экземпляр конференции имеет один и тот же ConferenceURI, но разное значение ConfInstance.</span><span class="sxs-lookup"><span data-stu-id="382cf-129">Each recurring conference instance has the same ConferenceURI but a different ConfInstance value.</span></span></p>
<p><span data-ttu-id="382cf-130">Это поле было введено в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="382cf-130">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="382cf-131"><strong>мкуконференцеуриид</strong></span><span class="sxs-lookup"><span data-stu-id="382cf-131"><strong>McuConferenceUriId</strong></span></span></p></td>
<td><p><span data-ttu-id="382cf-132">int</span><span class="sxs-lookup"><span data-stu-id="382cf-132">int</span></span></p></td>
<td><p><span data-ttu-id="382cf-133">Правительства</span><span class="sxs-lookup"><span data-stu-id="382cf-133">Foreign</span></span></p></td>
<td><p><span data-ttu-id="382cf-134">URI конференции с сервером конференций, относящейся к этому сеансу.</span><span class="sxs-lookup"><span data-stu-id="382cf-134">Conferencing server conference URI related to this session.</span></span> <span data-ttu-id="382cf-135">Дополнительные сведения см. <a href="lync-server-2013-conferenceuris-table.md">в таблице таблица conferenceuris в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="382cf-135">See the <a href="lync-server-2013-conferenceuris-table.md">ConferenceUris table in Lync Server 2013</a> for more information.</span></span> <span data-ttu-id="382cf-136">Это URI конференции на основе сервера конференций.</span><span class="sxs-lookup"><span data-stu-id="382cf-136">This URI is the conferencing server-based conference URI.</span></span> <span data-ttu-id="382cf-137">Для сеансов конференц-связи с центром конференций этот столбец будет пустым.</span><span class="sxs-lookup"><span data-stu-id="382cf-137">For Focus conference sessions, this column will be null.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="382cf-138"><strong>UserId</strong></span><span class="sxs-lookup"><span data-stu-id="382cf-138"><strong>UserId</strong></span></span></p></td>
<td><p><span data-ttu-id="382cf-139">int</span><span class="sxs-lookup"><span data-stu-id="382cf-139">int</span></span></p></td>
<td><p><span data-ttu-id="382cf-140">Правительства</span><span class="sxs-lookup"><span data-stu-id="382cf-140">Foreign</span></span></p></td>
<td><p><span data-ttu-id="382cf-141">Идентификатор одного пользователя в этом сеансе конференц-связи.</span><span class="sxs-lookup"><span data-stu-id="382cf-141">ID of one user in the conference session.</span></span> <span data-ttu-id="382cf-142">Дополнительные сведения см. <a href="lync-server-2013-users-table.md">в таблице "Пользователи" в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="382cf-142">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="382cf-143"><strong>усерендпоинтид</strong></span><span class="sxs-lookup"><span data-stu-id="382cf-143"><strong>UserEndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="382cf-144">идентификатора</span><span class="sxs-lookup"><span data-stu-id="382cf-144">uniqueidentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="382cf-p107">GUID для идентификации экземпляра конечной точки. Например, если один пользователь входит на разные компьютеры с одной и той же учетной записью, то все эти компьютеры будут иметь разные идентификаторы конечной точки.</span><span class="sxs-lookup"><span data-stu-id="382cf-p107">A GUID to identify the instance of endpoint. For example, if one user logs on to different machines with the same account, then each machine will have a different endpoint ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="382cf-147"><strong>онбехалфофид</strong></span><span class="sxs-lookup"><span data-stu-id="382cf-147"><strong>OnBehalfOfId</strong></span></span></p></td>
<td><p><span data-ttu-id="382cf-148">int</span><span class="sxs-lookup"><span data-stu-id="382cf-148">int</span></span></p></td>
<td><p><span data-ttu-id="382cf-149">Правительства</span><span class="sxs-lookup"><span data-stu-id="382cf-149">Foreign</span></span></p></td>
<td><p><span data-ttu-id="382cf-150">Определяет идентификатор пользователя, которого представляет вызывающий абонент.</span><span class="sxs-lookup"><span data-stu-id="382cf-150">Indicates the ID of the user of who the caller is on behalf.</span></span> <span data-ttu-id="382cf-151">Дополнительные сведения см. <a href="lync-server-2013-users-table.md">в таблице "Пользователи" в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="382cf-151">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="382cf-152"><strong>реферредбид</strong></span><span class="sxs-lookup"><span data-stu-id="382cf-152"><strong>ReferredById</strong></span></span></p></td>
<td><p><span data-ttu-id="382cf-153">int</span><span class="sxs-lookup"><span data-stu-id="382cf-153">int</span></span></p></td>
<td><p><span data-ttu-id="382cf-154">Правительства</span><span class="sxs-lookup"><span data-stu-id="382cf-154">Foreign</span></span></p></td>
<td><p><span data-ttu-id="382cf-155">Идентификатор пользователя, который ссылается на вызов.</span><span class="sxs-lookup"><span data-stu-id="382cf-155">ID of the user by who the call is referred.</span></span> <span data-ttu-id="382cf-156">Дополнительные сведения см. <a href="lync-server-2013-users-table.md">в таблице "Пользователи" в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="382cf-156">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="382cf-157"><strong>усерклиентверсионид</strong></span><span class="sxs-lookup"><span data-stu-id="382cf-157"><strong>UserClientVersionId</strong></span></span></p></td>
<td><p><span data-ttu-id="382cf-158">int</span><span class="sxs-lookup"><span data-stu-id="382cf-158">int</span></span></p></td>
<td><p><span data-ttu-id="382cf-159">Правительства</span><span class="sxs-lookup"><span data-stu-id="382cf-159">Foreign</span></span></p></td>
<td><p><span data-ttu-id="382cf-160">Версия клиента, используемого пользователем конференц-связи.</span><span class="sxs-lookup"><span data-stu-id="382cf-160">Client version used by the conference user.</span></span> <span data-ttu-id="382cf-161">Дополнительные сведения см. <a href="lync-server-2013-clientversions-table.md">в таблице таблица clientversions в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="382cf-161">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="382cf-162"><strong>конфклиентверсионид</strong></span><span class="sxs-lookup"><span data-stu-id="382cf-162"><strong>ConfClientVersionId</strong></span></span></p></td>
<td><p><span data-ttu-id="382cf-163">int</span><span class="sxs-lookup"><span data-stu-id="382cf-163">int</span></span></p></td>
<td><p><span data-ttu-id="382cf-164">Правительства</span><span class="sxs-lookup"><span data-stu-id="382cf-164">Foreign</span></span></p></td>
<td><p><span data-ttu-id="382cf-165">Версия клиента, используемого сервером конференций.</span><span class="sxs-lookup"><span data-stu-id="382cf-165">Client version used by the conference server.</span></span> <span data-ttu-id="382cf-166">Дополнительные сведения см. <a href="lync-server-2013-clientversions-table.md">в таблице таблица clientversions в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="382cf-166">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="382cf-167"><strong>реплацедиалогидтиме</strong></span><span class="sxs-lookup"><span data-stu-id="382cf-167"><strong>ReplaceDialogIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="382cf-168">datetime</span><span class="sxs-lookup"><span data-stu-id="382cf-168">datetime</span></span></p></td>
<td><p><span data-ttu-id="382cf-169">Правительства</span><span class="sxs-lookup"><span data-stu-id="382cf-169">Foreign</span></span></p></td>
<td><p><span data-ttu-id="382cf-170">Идентификационный номер для определения диалога, замененного текущим сеансом.</span><span class="sxs-lookup"><span data-stu-id="382cf-170">ID number to identify the dialog which was replaced by current session.</span></span> <span data-ttu-id="382cf-171">Дополнительные сведения см. <a href="lync-server-2013-dialogs-table.md">в таблице диалоговых окон в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="382cf-171">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="382cf-172"><strong>реплацедиалогидсек</strong></span><span class="sxs-lookup"><span data-stu-id="382cf-172"><strong>ReplaceDialogIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="382cf-173">int</span><span class="sxs-lookup"><span data-stu-id="382cf-173">int</span></span></p></td>
<td><p><span data-ttu-id="382cf-174">Правительства</span><span class="sxs-lookup"><span data-stu-id="382cf-174">Foreign</span></span></p></td>
<td><p><span data-ttu-id="382cf-175">Идентификатор для идентификации сеанса.</span><span class="sxs-lookup"><span data-stu-id="382cf-175">ID number to identify the session.</span></span> <span data-ttu-id="382cf-176">Используется в сочетании с <strong>ReplacesDialogIdTime</strong> для уникальной идентификации сеанса.</span><span class="sxs-lookup"><span data-stu-id="382cf-176">Used in conjunction with <strong>ReplacesDialogIdTime</strong> to uniquely identify a session that is replaced by this session.</span></span> <span data-ttu-id="382cf-177">Дополнительные сведения см. <a href="lync-server-2013-dialogs-table.md">в таблице диалоговых окон в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="382cf-177">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="382cf-178"><strong>исстартедбиконфсервер</strong></span><span class="sxs-lookup"><span data-stu-id="382cf-178"><strong>IsStartedByConfServer</strong></span></span></p></td>
<td><p><span data-ttu-id="382cf-179">Битовая</span><span class="sxs-lookup"><span data-stu-id="382cf-179">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="382cf-180">Показывает, был ли сеанс начат сервером конференций.</span><span class="sxs-lookup"><span data-stu-id="382cf-180">Indicates if the session started by the conferencing Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="382cf-181"><strong>исендедбиконфсервер</strong></span><span class="sxs-lookup"><span data-stu-id="382cf-181"><strong>IsEndedByConfServer</strong></span></span></p></td>
<td><p><span data-ttu-id="382cf-182">Битовая</span><span class="sxs-lookup"><span data-stu-id="382cf-182">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="382cf-183">Показывает, был ли сеанс завершен сервером конференций.</span><span class="sxs-lookup"><span data-stu-id="382cf-183">Indicates if the session ended by the conferencing server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="382cf-184"><strong>исусеринтернал</strong></span><span class="sxs-lookup"><span data-stu-id="382cf-184"><strong>IsUserInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="382cf-185">Битовая</span><span class="sxs-lookup"><span data-stu-id="382cf-185">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="382cf-186">Вошел ли пользователь из внутренней сети.</span><span class="sxs-lookup"><span data-stu-id="382cf-186">Whether user is logged on from internal or not.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="382cf-187"><strong>респонсекоде</strong></span><span class="sxs-lookup"><span data-stu-id="382cf-187"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="382cf-188">int</span><span class="sxs-lookup"><span data-stu-id="382cf-188">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="382cf-189">Код SIP-ответа на приглашение в сеанс.</span><span class="sxs-lookup"><span data-stu-id="382cf-189">Session Initiation Protocol (SIP) response code to the session invitation.</span></span> <span data-ttu-id="382cf-190">Это поле обычно заполняется данными, генерируемыми из исходного сообщения INVITE в сеансе.</span><span class="sxs-lookup"><span data-stu-id="382cf-190">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="382cf-191">Если сообщения INVITE нет, поле заполняется датой и временем первого релевантного SIP-сообщения (BYE, CANCEL, MESSAGE или INFO).</span><span class="sxs-lookup"><span data-stu-id="382cf-191">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="382cf-192"><strong>диагностиЦид</strong></span><span class="sxs-lookup"><span data-stu-id="382cf-192"><strong>DiagnosticId</strong></span></span></p></td>
<td><p><span data-ttu-id="382cf-193">int</span><span class="sxs-lookup"><span data-stu-id="382cf-193">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="382cf-194">Диагностический идентификатор, захваченный из заголовка SIP.</span><span class="sxs-lookup"><span data-stu-id="382cf-194">Diagnostic ID captured from SIP header.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="382cf-195"><strong>ServerId</strong></span><span class="sxs-lookup"><span data-stu-id="382cf-195"><strong>ServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="382cf-196">int</span><span class="sxs-lookup"><span data-stu-id="382cf-196">int</span></span></p></td>
<td><p><span data-ttu-id="382cf-197">Правительства</span><span class="sxs-lookup"><span data-stu-id="382cf-197">Foreign</span></span></p></td>
<td><p><span data-ttu-id="382cf-198">Идентификатор сервера переднего плана, используемого для этого сеанса.</span><span class="sxs-lookup"><span data-stu-id="382cf-198">ID of the front-end server used for this session.</span></span> <span data-ttu-id="382cf-199">Дополнительные сведения см. <a href="lync-server-2013-servers-table.md">в таблице Servers в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="382cf-199">See the <a href="lync-server-2013-servers-table.md">Servers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="382cf-200"><strong>пулид</strong></span><span class="sxs-lookup"><span data-stu-id="382cf-200"><strong>PoolId</strong></span></span></p></td>
<td><p><span data-ttu-id="382cf-201">int</span><span class="sxs-lookup"><span data-stu-id="382cf-201">int</span></span></p></td>
<td><p><span data-ttu-id="382cf-202">Правительства</span><span class="sxs-lookup"><span data-stu-id="382cf-202">Foreign</span></span></p></td>
<td><p><span data-ttu-id="382cf-203">Идентификатор пула, в котором был записан сеанс.</span><span class="sxs-lookup"><span data-stu-id="382cf-203">ID of the pool in which the session was captured.</span></span> <span data-ttu-id="382cf-204">Дополнительные сведения см. <a href="lync-server-2013-pools-table.md">в таблице Pools в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="382cf-204">See the <a href="lync-server-2013-pools-table.md">Pools table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="382cf-205"><strong>медиатионсерверид</strong></span><span class="sxs-lookup"><span data-stu-id="382cf-205"><strong>MediationServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="382cf-206">int</span><span class="sxs-lookup"><span data-stu-id="382cf-206">int</span></span></p></td>
<td><p><span data-ttu-id="382cf-207">Правительства</span><span class="sxs-lookup"><span data-stu-id="382cf-207">Foreign</span></span></p></td>
<td><p><span data-ttu-id="382cf-208">Сервер-посредник, который использовался вызовом.</span><span class="sxs-lookup"><span data-stu-id="382cf-208">The Mediation Server the call is using.</span></span> <span data-ttu-id="382cf-209">Дополнительные сведения см. <a href="lync-server-2013-mediationservers-table.md">в таблице таблица mediationservers в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="382cf-209">See the <a href="lync-server-2013-mediationservers-table.md">MediationServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="382cf-210"><strong>гатевайид</strong></span><span class="sxs-lookup"><span data-stu-id="382cf-210"><strong>GatewayId</strong></span></span></p></td>
<td><p><span data-ttu-id="382cf-211">int</span><span class="sxs-lookup"><span data-stu-id="382cf-211">int</span></span></p></td>
<td><p><span data-ttu-id="382cf-212">Правительства</span><span class="sxs-lookup"><span data-stu-id="382cf-212">Foreign</span></span></p></td>
<td><p><span data-ttu-id="382cf-213">Шлюз, который использовался вызовом.</span><span class="sxs-lookup"><span data-stu-id="382cf-213">The gateway the call is using.</span></span> <span data-ttu-id="382cf-214">Более подробную информацию можно узнать <a href="lync-server-2013-gateways-table.md">в таблице шлюзы в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="382cf-214">See the <a href="lync-server-2013-gateways-table.md">Gateways table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="382cf-215"><strong>еджесерверид</strong></span><span class="sxs-lookup"><span data-stu-id="382cf-215"><strong>EdgeServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="382cf-216">int</span><span class="sxs-lookup"><span data-stu-id="382cf-216">int</span></span></p></td>
<td><p><span data-ttu-id="382cf-217">Правительства</span><span class="sxs-lookup"><span data-stu-id="382cf-217">Foreign</span></span></p></td>
<td><p><span data-ttu-id="382cf-218">Пограничный сервер, который использовался вызовом.</span><span class="sxs-lookup"><span data-stu-id="382cf-218">The Edge Server the call is using.</span></span> <span data-ttu-id="382cf-219">Дополнительные сведения см. <a href="lync-server-2013-edgeservers-table.md">в таблице таблица edgeservers в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="382cf-219">See the <a href="lync-server-2013-edgeservers-table.md">EdgeServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="382cf-220"><strong>ContentTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="382cf-220"><strong>ContentTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="382cf-221">int</span><span class="sxs-lookup"><span data-stu-id="382cf-221">int</span></span></p></td>
<td><p><span data-ttu-id="382cf-222">Правительства</span><span class="sxs-lookup"><span data-stu-id="382cf-222">Foreign</span></span></p></td>
<td><p><span data-ttu-id="382cf-223">Тип контента, используемый в сеансе.</span><span class="sxs-lookup"><span data-stu-id="382cf-223">Content type used in the session.</span></span> <span data-ttu-id="382cf-224">Для получения дополнительных сведений см <a href="lync-server-2013-contenttypes-table.md">таблицу ContentTypes в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="382cf-224">See the <a href="lync-server-2013-contenttypes-table.md">ContentTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="382cf-225"><strong>инвитетиме</strong></span><span class="sxs-lookup"><span data-stu-id="382cf-225"><strong>InviteTime</strong></span></span></p></td>
<td><p><span data-ttu-id="382cf-226">datetime</span><span class="sxs-lookup"><span data-stu-id="382cf-226">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="382cf-p121">Время первого запроса INVITE. Это поле обычно заполняется данными, генерируемыми из исходного сообщения INVITE в сеансе. Если сообщения INVITE нет, поле заполняется датой и временем первого релевантного SIP-сообщения (BYE, CANCEL, MESSAGE или INFO).</span><span class="sxs-lookup"><span data-stu-id="382cf-p121">The time of the first INVITE request. This field is typically populated by data generated from the initial INVITE message in the session. If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="382cf-230"><strong>респонсетиме</strong></span><span class="sxs-lookup"><span data-stu-id="382cf-230"><strong>ResponseTime</strong></span></span></p></td>
<td><p><span data-ttu-id="382cf-231">datetime</span><span class="sxs-lookup"><span data-stu-id="382cf-231">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="382cf-232">Время первого ответа SIP.</span><span class="sxs-lookup"><span data-stu-id="382cf-232">Time of the first SIP RESPONSE.</span></span> <span data-ttu-id="382cf-233">Это поле обычно заполняется данными, генерируемыми из исходного сообщения INVITE в сеансе.</span><span class="sxs-lookup"><span data-stu-id="382cf-233">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="382cf-234">Если сообщения INVITE нет, поле заполняется датой и временем первого релевантного SIP-сообщения (BYE, CANCEL, MESSAGE или INFO).</span><span class="sxs-lookup"><span data-stu-id="382cf-234">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="382cf-235"><strong>сессионендтиме</strong></span><span class="sxs-lookup"><span data-stu-id="382cf-235"><strong>SessionEndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="382cf-236">datetime</span><span class="sxs-lookup"><span data-stu-id="382cf-236">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="382cf-237">Время окончания сеанса.</span><span class="sxs-lookup"><span data-stu-id="382cf-237">The time when the session is ended.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="382cf-238"><strong>уритипеид</strong></span><span class="sxs-lookup"><span data-stu-id="382cf-238"><strong>UriTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="382cf-239">tinyint</span><span class="sxs-lookup"><span data-stu-id="382cf-239">tinyint</span></span></p></td>
<td><p><span data-ttu-id="382cf-240">Правительства</span><span class="sxs-lookup"><span data-stu-id="382cf-240">Foreign</span></span></p></td>
<td><p><span data-ttu-id="382cf-241">Содержит значение типа универсального кода ресурса (URI) MCU из <a href="lync-server-2013-uritypes-table.md">таблицы таблица uritypes в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="382cf-241">Contains the MCU URI type value from the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a>.</span></span> <span data-ttu-id="382cf-242">Это поле используется для повышения производительности запроса.</span><span class="sxs-lookup"><span data-stu-id="382cf-242">This field is used for improving query performance.</span></span></p>
<p><span data-ttu-id="382cf-243">Это поле было введено в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="382cf-243">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="382cf-244"><strong>усерфлаг</strong></span><span class="sxs-lookup"><span data-stu-id="382cf-244"><strong>UserFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="382cf-245">smallint</span><span class="sxs-lookup"><span data-stu-id="382cf-245">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="382cf-p124">Набор битов, указывающий атрибуты пользователя. Перечисляются следующие определения атрибутов:</span><span class="sxs-lookup"><span data-stu-id="382cf-p124">A bit set that indicates the user attributes. The following attribute definitions are listed:</span></span></p>
<ul>
<li><p><span data-ttu-id="382cf-248">интеграция со стационарным телефоном — 1</span><span class="sxs-lookup"><span data-stu-id="382cf-248">Integrated with desktop phone - 1</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="382cf-249"><strong>каллфлаг</strong></span><span class="sxs-lookup"><span data-stu-id="382cf-249"><strong>CallFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="382cf-250">smallint</span><span class="sxs-lookup"><span data-stu-id="382cf-250">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="382cf-p125">Набор битов, указывающий атрибуты вызова. Перечисляются следующие определения атрибутов:</span><span class="sxs-lookup"><span data-stu-id="382cf-p125">A bit set that indicates the call attributes. The following attribute definitions are listed:</span></span></p>
<ul>
<li><p><span data-ttu-id="382cf-253">повторный сеанс — 1</span><span class="sxs-lookup"><span data-stu-id="382cf-253">Retried Session - 1</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


<span data-ttu-id="382cf-254">\*Для большинства сеансов Сессионидсек будет иметь значение 1.</span><span class="sxs-lookup"><span data-stu-id="382cf-254">\* For most sessions, SessionIdSeq will have the value of 1.</span></span> <span data-ttu-id="382cf-255">Если несколько сеансов начинаются в одно и то же время, для одного из них SessionIdSeq будет иметь значение 1, для другого — 2 и т. д.</span><span class="sxs-lookup"><span data-stu-id="382cf-255">If multiple sessions start at exactly the same time, the SessionIdSeq for one will be 1, for another will be 2, and so on.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

