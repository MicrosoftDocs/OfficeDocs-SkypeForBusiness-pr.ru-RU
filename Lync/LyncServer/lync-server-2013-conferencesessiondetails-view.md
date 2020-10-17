---
title: 'Lync Server 2013: представление Таблица conferencesessiondetails'
description: 'Lync Server 2013: представление Таблица conferencesessiondetails.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: ConferenceSessionDetails view
ms:assetid: 5858c84d-baed-421d-ad1d-3726e150e256
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688066(v=OCS.15)
ms:contentKeyID: 49733660
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d1c62f020413efecdbc0f909618256ccc7308d4f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566775"
---
# <a name="conferencesessiondetails-view-in-lync-server-2013"></a><span data-ttu-id="e33f1-103">Представление Таблица conferencesessiondetails в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e33f1-103">ConferenceSessionDetails view in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e33f1-104">_**Последнее изменение темы:** 2012-11-12_</span><span class="sxs-lookup"><span data-stu-id="e33f1-104">_**Topic Last Modified:** 2012-11-12_</span></span>

<span data-ttu-id="e33f1-105">Представление ConferenceSessionDetails хранит сведения о многосторонних сеансах.</span><span class="sxs-lookup"><span data-stu-id="e33f1-105">The ConferenceSessionDetails view stores information about multiparty sessions.</span></span> <span data-ttu-id="e33f1-106">Каждая запись представляет один сеанс конференц-связи, который может быть сеансом с фокусом или сеансом с определенным сервером конференц-связи.</span><span class="sxs-lookup"><span data-stu-id="e33f1-106">Each record represents one conference session, which could be either the session with Focus or the session with a specific conferencing server.</span></span> <span data-ttu-id="e33f1-107">Это представление было представлено в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e33f1-107">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e33f1-108">Столбец</span><span class="sxs-lookup"><span data-stu-id="e33f1-108">Column</span></span></th>
<th><span data-ttu-id="e33f1-109">Тип данных</span><span class="sxs-lookup"><span data-stu-id="e33f1-109">Data Type</span></span></th>
<th><span data-ttu-id="e33f1-110">Сведения</span><span class="sxs-lookup"><span data-stu-id="e33f1-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e33f1-111"><strong>сессионидтиме</strong></span><span class="sxs-lookup"><span data-stu-id="e33f1-111"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="e33f1-112">datetime</span><span class="sxs-lookup"><span data-stu-id="e33f1-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="e33f1-113">Время запроса сеанса.</span><span class="sxs-lookup"><span data-stu-id="e33f1-113">Time of session request.</span></span> <span data-ttu-id="e33f1-114">Используется вместе с параметром SessionIdSeq для уникального определения сеанса.</span><span class="sxs-lookup"><span data-stu-id="e33f1-114">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="e33f1-115">Дополнительные сведения см. <a href="lync-server-2013-dialogs-table.md">в таблице диалоговых окон в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="e33f1-115">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e33f1-116"><strong>сессионидсек</strong></span><span class="sxs-lookup"><span data-stu-id="e33f1-116"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="e33f1-117">int</span><span class="sxs-lookup"><span data-stu-id="e33f1-117">int</span></span></p></td>
<td><p><span data-ttu-id="e33f1-118">Идентификационный номер для идентификации сеанса.</span><span class="sxs-lookup"><span data-stu-id="e33f1-118">ID number to identify the session.</span></span> <span data-ttu-id="e33f1-119">Используется совместно с параметром SessionIdTime для уникальной идентификации сеанса.</span><span class="sxs-lookup"><span data-stu-id="e33f1-119">Used in conjunction with SessionIdTime to uniquely identify a session.</span></span> <span data-ttu-id="e33f1-120">Дополнительные сведения см. <a href="lync-server-2013-dialogs-table.md">в таблице диалоговых окон в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="e33f1-120">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e33f1-121"><strong>инвитетиме</strong></span><span class="sxs-lookup"><span data-stu-id="e33f1-121"><strong>InviteTime</strong></span></span></p></td>
<td><p><span data-ttu-id="e33f1-122">datetime</span><span class="sxs-lookup"><span data-stu-id="e33f1-122">datetime</span></span></p></td>
<td><p><span data-ttu-id="e33f1-p104">Время первого запроса INVITE. Это поле обычно заполняется данными, генерируемыми из исходного сообщения INVITE в сеансе. При отсутствии сообщения INVITE поле заполняется датой и временем первого соответствующего сообщения SIP (BYE, CANCEL, MESSAGE или INFO).</span><span class="sxs-lookup"><span data-stu-id="e33f1-p104">Time of the first INVITE request. This field is typically populated by data generated from the initial INVITE message in the session. If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e33f1-126"><strong>конференцеури</strong></span><span class="sxs-lookup"><span data-stu-id="e33f1-126"><strong>ConferenceUri</strong></span></span></p></td>
<td><p><span data-ttu-id="e33f1-127">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="e33f1-127">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="e33f1-128">Идентификатор URI конференции.</span><span class="sxs-lookup"><span data-stu-id="e33f1-128">URI of the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e33f1-129"><strong>конференцеуритипе</strong></span><span class="sxs-lookup"><span data-stu-id="e33f1-129"><strong>ConferenceUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="e33f1-130">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="e33f1-130">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e33f1-131">Тип идентификатора URI конференции.</span><span class="sxs-lookup"><span data-stu-id="e33f1-131">Type of conference URI.</span></span> <span data-ttu-id="e33f1-132">Дополнительные сведения см. <a href="lync-server-2013-uritypes-table.md">в таблице таблица uritypes в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="e33f1-132">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e33f1-133"><strong>конфинстанце</strong></span><span class="sxs-lookup"><span data-stu-id="e33f1-133"><strong>ConfInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="e33f1-134">идентификатора</span><span class="sxs-lookup"><span data-stu-id="e33f1-134">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="e33f1-p106">Идентификатор, который разделяет экземпляры повторяющихся конференций. Каждый повторяющийся экземпляр конференции имеет один и тот же ConferenceURI, но разное значение ConfInstance.</span><span class="sxs-lookup"><span data-stu-id="e33f1-p106">Identifier that differentiates between instances of recurring conferences. Each recurring conference instance has the same ConferenceURI but a different ConfInstance value.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e33f1-137"><strong>мкуконференцеури</strong></span><span class="sxs-lookup"><span data-stu-id="e33f1-137"><strong>McuConferenceUri</strong></span></span></p></td>
<td><p><span data-ttu-id="e33f1-138">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="e33f1-138">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="e33f1-139">Идентификатор URI сервера конференц-связи.</span><span class="sxs-lookup"><span data-stu-id="e33f1-139">URI of the conferencing server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e33f1-140"><strong>мкуконференцеуритипе</strong></span><span class="sxs-lookup"><span data-stu-id="e33f1-140"><strong>McuConferenceUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="e33f1-141">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="e33f1-141">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e33f1-142">Тип идентификатора URI сервера конференц-связи.</span><span class="sxs-lookup"><span data-stu-id="e33f1-142">Type of conferencing server URI.</span></span> <span data-ttu-id="e33f1-143">Дополнительные сведения см. <a href="lync-server-2013-uritypes-table.md">в таблице таблица uritypes в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="e33f1-143">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e33f1-144"><strong>UserUri</strong></span><span class="sxs-lookup"><span data-stu-id="e33f1-144"><strong>UserUri</strong></span></span></p></td>
<td><p><span data-ttu-id="e33f1-145">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="e33f1-145">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="e33f1-146">URI пользователя, участвующего в сеансе.</span><span class="sxs-lookup"><span data-stu-id="e33f1-146">URI of the user involved in the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e33f1-147"><strong>усеруритипе</strong></span><span class="sxs-lookup"><span data-stu-id="e33f1-147"><strong>UserUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="e33f1-148">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="e33f1-148">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e33f1-149">Тип URI пользователя, который являлся участником сеанса.</span><span class="sxs-lookup"><span data-stu-id="e33f1-149">Type of URI of the user whose was part of the session.</span></span> <span data-ttu-id="e33f1-150">Дополнительные сведения см. <a href="lync-server-2013-uritypes-table.md">в таблице таблица uritypes в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="e33f1-150">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e33f1-151"><strong>усертенант</strong></span><span class="sxs-lookup"><span data-stu-id="e33f1-151"><strong>UserTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="e33f1-152">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="e33f1-152">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e33f1-153">Клиент пользователя, который являлся участником сеанса.</span><span class="sxs-lookup"><span data-stu-id="e33f1-153">Tenant of the user whose was part of the session.</span></span> <span data-ttu-id="e33f1-154">Дополнительные сведения см. <a href="lync-server-2013-tenants-table.md">в таблице клиентов в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="e33f1-154">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e33f1-155"><strong>усерендпоинтид</strong></span><span class="sxs-lookup"><span data-stu-id="e33f1-155"><strong>UserEndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="e33f1-156">идентификатора</span><span class="sxs-lookup"><span data-stu-id="e33f1-156">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="e33f1-157">Уникальный идентификатор пользователя, который являлся участником сеанса.</span><span class="sxs-lookup"><span data-stu-id="e33f1-157">Unique identifier of the user whose was part of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e33f1-158"><strong>EndTime</strong></span><span class="sxs-lookup"><span data-stu-id="e33f1-158"><strong>EndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="e33f1-159">datetime</span><span class="sxs-lookup"><span data-stu-id="e33f1-159">datetime</span></span></p></td>
<td><p><span data-ttu-id="e33f1-160">Время окончания сеанса.</span><span class="sxs-lookup"><span data-stu-id="e33f1-160">End time of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e33f1-161"><strong>конференцеклиентверсион</strong></span><span class="sxs-lookup"><span data-stu-id="e33f1-161"><strong>ConferenceClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="e33f1-162">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="e33f1-162">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e33f1-163">Версия сервера конференц-связи.</span><span class="sxs-lookup"><span data-stu-id="e33f1-163">Version of conference server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e33f1-164"><strong>конференцеклиенттипе</strong></span><span class="sxs-lookup"><span data-stu-id="e33f1-164"><strong>ConferenceClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="e33f1-165">int</span><span class="sxs-lookup"><span data-stu-id="e33f1-165">int</span></span></p></td>
<td><p><span data-ttu-id="e33f1-166">Тип сервера конференц-связи.</span><span class="sxs-lookup"><span data-stu-id="e33f1-166">Type of conference server.</span></span> <span data-ttu-id="e33f1-167">Дополнительные сведения см. <a href="lync-server-2013-useragentdef-table.md">в таблице таблица useragentdef в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="e33f1-167">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e33f1-168"><strong>конференцекатегори</strong></span><span class="sxs-lookup"><span data-stu-id="e33f1-168"><strong>ConferenceCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="e33f1-169">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="e33f1-169">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="e33f1-170">Категория сервера конференц-связи.</span><span class="sxs-lookup"><span data-stu-id="e33f1-170">Conference server category.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e33f1-171"><strong>усерклиентверсион</strong></span><span class="sxs-lookup"><span data-stu-id="e33f1-171"><strong>UserClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="e33f1-172">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="e33f1-172">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e33f1-173">Версия клиента, используемая пользователем, который являлся участником сеанса.</span><span class="sxs-lookup"><span data-stu-id="e33f1-173">Version of client used by the user who participated in the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e33f1-174"><strong>усерклиенттипе</strong></span><span class="sxs-lookup"><span data-stu-id="e33f1-174"><strong>UserClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="e33f1-175">int</span><span class="sxs-lookup"><span data-stu-id="e33f1-175">int</span></span></p></td>
<td><p><span data-ttu-id="e33f1-176">Клиент, использованный пользователем, который являлся участником сеанса.</span><span class="sxs-lookup"><span data-stu-id="e33f1-176">Client used by the user who participated in the session.</span></span> <span data-ttu-id="e33f1-177">Дополнительные сведения приведены <a href="lync-server-2013-useragentdef-table.md">в таблице таблица useragentdef в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="e33f1-177">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e33f1-178"><strong>усерклиенткатегори</strong></span><span class="sxs-lookup"><span data-stu-id="e33f1-178"><strong>UserClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="e33f1-179">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="e33f1-179">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="e33f1-180">Название категории клиента, использованной пользователем, который являлся частью сеанса.</span><span class="sxs-lookup"><span data-stu-id="e33f1-180">Name of the category of the client used by the user who was part of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e33f1-181"><strong>онбехалфофури</strong></span><span class="sxs-lookup"><span data-stu-id="e33f1-181"><strong>OnBehalfOfUri</strong></span></span></p></td>
<td><p><span data-ttu-id="e33f1-182">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="e33f1-182">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="e33f1-183">URI пользователя, от чьего имени был запущен сеанс.</span><span class="sxs-lookup"><span data-stu-id="e33f1-183">URI of the user on whose behalf the session was started.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e33f1-184"><strong>онбехалфофуритипе</strong></span><span class="sxs-lookup"><span data-stu-id="e33f1-184"><strong>OnBehalfOfUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="e33f1-185">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="e33f1-185">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e33f1-186">Тип URI пользователя, от имени которого был запущен сеанс.</span><span class="sxs-lookup"><span data-stu-id="e33f1-186">Type of URI of the user on whose behalf the session was started.</span></span> <span data-ttu-id="e33f1-187">Дополнительные сведения см. <a href="lync-server-2013-uritypes-table.md">в таблице таблица uritypes в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="e33f1-187">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e33f1-188"><strong>онбехалфофтенант</strong></span><span class="sxs-lookup"><span data-stu-id="e33f1-188"><strong>OnBehalfOfTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="e33f1-189">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="e33f1-189">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e33f1-190">Клиент пользователя, от имени которого был запущен сеанс.</span><span class="sxs-lookup"><span data-stu-id="e33f1-190">Tenant of the user whose on behalf the session was started.</span></span> <span data-ttu-id="e33f1-191">Дополнительные сведения см. <a href="lync-server-2013-tenants-table.md">в таблице клиентов в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="e33f1-191">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e33f1-192"><strong>реферредбюри</strong></span><span class="sxs-lookup"><span data-stu-id="e33f1-192"><strong>ReferredByUri</strong></span></span></p></td>
<td><p><span data-ttu-id="e33f1-193">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="e33f1-193">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="e33f1-194">URI пользователя, который указал ссылку на сеанс.</span><span class="sxs-lookup"><span data-stu-id="e33f1-194">URI of the user who referred the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e33f1-195"><strong>реферредбюритипе</strong></span><span class="sxs-lookup"><span data-stu-id="e33f1-195"><strong>ReferredByUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="e33f1-196">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="e33f1-196">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e33f1-197">Тип URI пользователя, который указал ссылку на сеанс.</span><span class="sxs-lookup"><span data-stu-id="e33f1-197">Type of URI of the user who referred the session.</span></span> <span data-ttu-id="e33f1-198">Дополнительные сведения см. <a href="lync-server-2013-uritypes-table.md">в таблице таблица uritypes в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="e33f1-198">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e33f1-199"><strong>реферредбюритенант</strong></span><span class="sxs-lookup"><span data-stu-id="e33f1-199"><strong>ReferredByUriTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="e33f1-200">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="e33f1-200">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e33f1-201">Клиент пользователя, который указал ссылку на сеанс.</span><span class="sxs-lookup"><span data-stu-id="e33f1-201">Tenant of the user who referred the session.</span></span> <span data-ttu-id="e33f1-202">Дополнительные сведения см. <a href="lync-server-2013-tenants-table.md">в таблице клиентов в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="e33f1-202">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e33f1-203"><strong>DialogId</strong></span><span class="sxs-lookup"><span data-stu-id="e33f1-203"><strong>DialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="e33f1-204">варстринг (775)</span><span class="sxs-lookup"><span data-stu-id="e33f1-204">varstring(775)</span></span></p></td>
<td><p><span data-ttu-id="e33f1-p116">ИД диалога SIP в следующем формате:</span><span class="sxs-lookup"><span data-stu-id="e33f1-p116">SIP dialog ID. The format is</span></span></p>
<p><span data-ttu-id="e33f1-207">:d иалог; to – Tag</span><span class="sxs-lookup"><span data-stu-id="e33f1-207">:dialog;from-tag;to-tag</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e33f1-208"><strong>реплацедиалогидтиме</strong></span><span class="sxs-lookup"><span data-stu-id="e33f1-208"><strong>ReplaceDialogIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="e33f1-209">datetime</span><span class="sxs-lookup"><span data-stu-id="e33f1-209">datetime</span></span></p></td>
<td><p><span data-ttu-id="e33f1-210">Идентификатор диалога, который был замещен текущим сеансом.</span><span class="sxs-lookup"><span data-stu-id="e33f1-210">ID number to identify the dialog which was replaced by current session.</span></span> <span data-ttu-id="e33f1-211">Дополнительные сведения см. <a href="lync-server-2013-dialogs-table.md">в таблице диалоговых окон в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="e33f1-211">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e33f1-212"><strong>реплацедиалогидсек</strong></span><span class="sxs-lookup"><span data-stu-id="e33f1-212"><strong>ReplaceDialogIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="e33f1-213">int</span><span class="sxs-lookup"><span data-stu-id="e33f1-213">int</span></span></p></td>
<td><p><span data-ttu-id="e33f1-214">Идентификационный номер для идентификации сеанса.</span><span class="sxs-lookup"><span data-stu-id="e33f1-214">ID number to identify the session.</span></span> <span data-ttu-id="e33f1-215">Используется совместно с параметром ReplaceDialogIdTime для уникальной идентификации сеанса, замененного данным сеансом.</span><span class="sxs-lookup"><span data-stu-id="e33f1-215">Used in conjunction with ReplaceDialogIdTime to uniquely identify a session that is replaced by this session.</span></span> <span data-ttu-id="e33f1-216">Дополнительные сведения см. <a href="lync-server-2013-dialogs-table.md">в таблице диалоговых окон в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="e33f1-216">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e33f1-217"><strong>реплацесдиалогид</strong></span><span class="sxs-lookup"><span data-stu-id="e33f1-217"><strong>ReplacesDialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="e33f1-218">varchar (775)</span><span class="sxs-lookup"><span data-stu-id="e33f1-218">varchar(775)</span></span></p></td>
<td><p><span data-ttu-id="e33f1-p119">Идентификатор диалога SIP, который был замещен этим сеансом. Используется следующий формат:</span><span class="sxs-lookup"><span data-stu-id="e33f1-p119">SIP dialog ID the session replaces. The format of the is:</span></span></p>
<p><span data-ttu-id="e33f1-221">диалоговое окно; from — Tag; to – Tag</span><span class="sxs-lookup"><span data-stu-id="e33f1-221">dialog;from-tag;to-tag</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e33f1-222"><strong>исстартедбиконфсервер</strong></span><span class="sxs-lookup"><span data-stu-id="e33f1-222"><strong>IsStartedByConfServer</strong></span></span></p></td>
<td><p><span data-ttu-id="e33f1-223">Битовая</span><span class="sxs-lookup"><span data-stu-id="e33f1-223">bit</span></span></p></td>
<td><p><span data-ttu-id="e33f1-224">Указывает, был ли сеанс запущен сервером конференц-связи.</span><span class="sxs-lookup"><span data-stu-id="e33f1-224">Indicates whether the session was started by the conferencing server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e33f1-225"><strong>исендедбиконфсервер</strong></span><span class="sxs-lookup"><span data-stu-id="e33f1-225"><strong>IsEndedByConfServer</strong></span></span></p></td>
<td><p><span data-ttu-id="e33f1-226">Битовая</span><span class="sxs-lookup"><span data-stu-id="e33f1-226">bit</span></span></p></td>
<td><p><span data-ttu-id="e33f1-227">Указывает, был ли сеанс завершен сервером конференц-связи.</span><span class="sxs-lookup"><span data-stu-id="e33f1-227">Indicates whether the session was ended by the conferencing server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e33f1-228"><strong>исусеринтернал</strong></span><span class="sxs-lookup"><span data-stu-id="e33f1-228"><strong>IsUserInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="e33f1-229">Битовая</span><span class="sxs-lookup"><span data-stu-id="e33f1-229">bit</span></span></p></td>
<td><p><span data-ttu-id="e33f1-230">Показывает, зашел ли пользователь в систему из внутренней сети.</span><span class="sxs-lookup"><span data-stu-id="e33f1-230">Indicates whether the user logged on from the internal network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e33f1-231"><strong>респонсетиме</strong></span><span class="sxs-lookup"><span data-stu-id="e33f1-231"><strong>ResponseTime</strong></span></span></p></td>
<td><p><span data-ttu-id="e33f1-232">datetime</span><span class="sxs-lookup"><span data-stu-id="e33f1-232">datetime</span></span></p></td>
<td><p><span data-ttu-id="e33f1-p120">Время ответа на первое сообщение INVITE. Обычно это поле содержит данные из первоначального сообщения INVITE в сеансе. Если сообщение INVITE отсутствует, в поле записывается дата и время первого соответствующего SIP-сообщения (BYE, CANCEL, MESSAGE или INFO).</span><span class="sxs-lookup"><span data-stu-id="e33f1-p120">Time of the response to the first INVITE message. This field is typically populated by data generated from the initial INVITE message in the session. If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e33f1-236"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="e33f1-236"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="e33f1-237">int</span><span class="sxs-lookup"><span data-stu-id="e33f1-237">int</span></span></p></td>
<td><p><span data-ttu-id="e33f1-p121">Код SIP-ответа на приглашение в сеанс. Это поле обычно заполняется данными, генерируемыми из исходного сообщения INVITE в сеансе. Если сообщения INVITE нет, поле заполняется датой и временем первого релевантного SIP-сообщения (BYE, CANCEL, MESSAGE или INFO).</span><span class="sxs-lookup"><span data-stu-id="e33f1-p121">SIP response code to the session invitation. This field is typically populated by data generated from the initial INVITE message in the session. If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e33f1-241"><strong>диагностиЦид</strong></span><span class="sxs-lookup"><span data-stu-id="e33f1-241"><strong>DiagnosticId</strong></span></span></p></td>
<td><p><span data-ttu-id="e33f1-242">int</span><span class="sxs-lookup"><span data-stu-id="e33f1-242">int</span></span></p></td>
<td><p><span data-ttu-id="e33f1-243">Диагностический идентификатор, взятый из SIP-заголовков сеанса.</span><span class="sxs-lookup"><span data-stu-id="e33f1-243">Diagnostic ID captured from session SIP headers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e33f1-244"><strong>ContentType</strong></span><span class="sxs-lookup"><span data-stu-id="e33f1-244"><strong>ContentType</strong></span></span></p></td>
<td><p><span data-ttu-id="e33f1-245">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="e33f1-245">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e33f1-246">Тип содержимого сеанса.</span><span class="sxs-lookup"><span data-stu-id="e33f1-246">Content type for the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e33f1-247"><strong>FrontEnd</strong></span><span class="sxs-lookup"><span data-stu-id="e33f1-247"><strong>FrontEnd</strong></span></span></p></td>
<td><p><span data-ttu-id="e33f1-248">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="e33f1-248">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e33f1-249">Полное доменное имя интерфейсного сервера, который получил данные этого сеанса.</span><span class="sxs-lookup"><span data-stu-id="e33f1-249">FQDN of the Front End server that captured the data for the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e33f1-250"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="e33f1-250"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="e33f1-251">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="e33f1-251">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e33f1-252">Полное доменное имя пула, захватившего данные для сеанса.</span><span class="sxs-lookup"><span data-stu-id="e33f1-252">FQDN of the pool that captured the data for the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e33f1-253"><strong>MediationServer</strong></span><span class="sxs-lookup"><span data-stu-id="e33f1-253"><strong>MediationServer</strong></span></span></p></td>
<td><p><span data-ttu-id="e33f1-254">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="e33f1-254">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e33f1-255">Сервер-посредник, использованный пользователем, который являлся участником сеанса.</span><span class="sxs-lookup"><span data-stu-id="e33f1-255">Mediation Server used by the user who participated in the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e33f1-256"><strong>Шлюз</strong></span><span class="sxs-lookup"><span data-stu-id="e33f1-256"><strong>Gateway</strong></span></span></p></td>
<td><p><span data-ttu-id="e33f1-257">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="e33f1-257">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e33f1-258">Шлюз, использованный пользователем, который являлся участником сеанса.</span><span class="sxs-lookup"><span data-stu-id="e33f1-258">Gateway used by the user who participated the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e33f1-259"><strong>EdgeServer</strong></span><span class="sxs-lookup"><span data-stu-id="e33f1-259"><strong>EdgeServer</strong></span></span></p></td>
<td><p><span data-ttu-id="e33f1-260">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="e33f1-260">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e33f1-261">Полное доменное имя пограничного сервера, используемого пользователем, который являлся участником сеанса.</span><span class="sxs-lookup"><span data-stu-id="e33f1-261">FQDN of the Edge server used by the user who participated in the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e33f1-262"><strong>усерфлаг</strong></span><span class="sxs-lookup"><span data-stu-id="e33f1-262"><strong>UserFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="e33f1-263">smallint</span><span class="sxs-lookup"><span data-stu-id="e33f1-263">smallint</span></span></p></td>
<td><p><span data-ttu-id="e33f1-p122">Указывает атрибуты пользователя, который являлся участником сеанса. Разрешены следующие определения атрибутов.</span><span class="sxs-lookup"><span data-stu-id="e33f1-p122">Indicates the attributes of the user who participated in the session. The following attribute definitions allowed:</span></span></p>
<p><span data-ttu-id="e33f1-266">0x01 — интеграция с настольным телефоном</span><span class="sxs-lookup"><span data-stu-id="e33f1-266">0x01 - Integrated with desktop phone</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e33f1-267"><strong>каллфлаг</strong></span><span class="sxs-lookup"><span data-stu-id="e33f1-267"><strong>CallFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="e33f1-268">smallint</span><span class="sxs-lookup"><span data-stu-id="e33f1-268">smallint</span></span></p></td>
<td><p><span data-ttu-id="e33f1-p123">Указывает атрибуты вызова. Разрешены следующие определения атрибутов.</span><span class="sxs-lookup"><span data-stu-id="e33f1-p123">Indicates the call attributes. The following attribute definitions are allowed:</span></span></p>
<p><span data-ttu-id="e33f1-271">0x01 — списанный сеанс 0</span><span class="sxs-lookup"><span data-stu-id="e33f1-271">0x01 - Retried Session0</span></span></p>
<p><span data-ttu-id="e33f1-272">x02 — вызов, выполненный агентом от имени группы ответа</span><span class="sxs-lookup"><span data-stu-id="e33f1-272">x02 - A call made by agent on behalf of a Response Group</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

