---
title: 'Lync Server 2013: представление Таблица conferencesessiondetails'
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
ms.openlocfilehash: cf8023408990b7f0243aaf0e937e2d1095dff0c2
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48529186"
---
# <a name="conferencesessiondetails-view-in-lync-server-2013"></a><span data-ttu-id="5c36b-102">Представление Таблица conferencesessiondetails в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5c36b-102">ConferenceSessionDetails view in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5c36b-103">_**Последнее изменение темы:** 2012-11-12_</span><span class="sxs-lookup"><span data-stu-id="5c36b-103">_**Topic Last Modified:** 2012-11-12_</span></span>

<span data-ttu-id="5c36b-104">Представление ConferenceSessionDetails хранит сведения о многосторонних сеансах.</span><span class="sxs-lookup"><span data-stu-id="5c36b-104">The ConferenceSessionDetails view stores information about multiparty sessions.</span></span> <span data-ttu-id="5c36b-105">Каждая запись представляет один сеанс конференц-связи, который может быть сеансом с фокусом или сеансом с определенным сервером конференц-связи.</span><span class="sxs-lookup"><span data-stu-id="5c36b-105">Each record represents one conference session, which could be either the session with Focus or the session with a specific conferencing server.</span></span> <span data-ttu-id="5c36b-106">Это представление было представлено в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5c36b-106">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5c36b-107">Столбец</span><span class="sxs-lookup"><span data-stu-id="5c36b-107">Column</span></span></th>
<th><span data-ttu-id="5c36b-108">Тип данных</span><span class="sxs-lookup"><span data-stu-id="5c36b-108">Data Type</span></span></th>
<th><span data-ttu-id="5c36b-109">Сведения</span><span class="sxs-lookup"><span data-stu-id="5c36b-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5c36b-110"><strong>сессионидтиме</strong></span><span class="sxs-lookup"><span data-stu-id="5c36b-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="5c36b-111">datetime</span><span class="sxs-lookup"><span data-stu-id="5c36b-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="5c36b-112">Время запроса сеанса.</span><span class="sxs-lookup"><span data-stu-id="5c36b-112">Time of session request.</span></span> <span data-ttu-id="5c36b-113">Используется вместе с параметром SessionIdSeq для уникального определения сеанса.</span><span class="sxs-lookup"><span data-stu-id="5c36b-113">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="5c36b-114">Дополнительные сведения см. <a href="lync-server-2013-dialogs-table.md">в таблице диалоговых окон в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="5c36b-114">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5c36b-115"><strong>сессионидсек</strong></span><span class="sxs-lookup"><span data-stu-id="5c36b-115"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="5c36b-116">int</span><span class="sxs-lookup"><span data-stu-id="5c36b-116">int</span></span></p></td>
<td><p><span data-ttu-id="5c36b-117">Идентификационный номер для идентификации сеанса.</span><span class="sxs-lookup"><span data-stu-id="5c36b-117">ID number to identify the session.</span></span> <span data-ttu-id="5c36b-118">Используется совместно с параметром SessionIdTime для уникальной идентификации сеанса.</span><span class="sxs-lookup"><span data-stu-id="5c36b-118">Used in conjunction with SessionIdTime to uniquely identify a session.</span></span> <span data-ttu-id="5c36b-119">Дополнительные сведения см. <a href="lync-server-2013-dialogs-table.md">в таблице диалоговых окон в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="5c36b-119">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5c36b-120"><strong>инвитетиме</strong></span><span class="sxs-lookup"><span data-stu-id="5c36b-120"><strong>InviteTime</strong></span></span></p></td>
<td><p><span data-ttu-id="5c36b-121">datetime</span><span class="sxs-lookup"><span data-stu-id="5c36b-121">datetime</span></span></p></td>
<td><p><span data-ttu-id="5c36b-p104">Время первого запроса INVITE. Это поле обычно заполняется данными, генерируемыми из исходного сообщения INVITE в сеансе. При отсутствии сообщения INVITE поле заполняется датой и временем первого соответствующего сообщения SIP (BYE, CANCEL, MESSAGE или INFO).</span><span class="sxs-lookup"><span data-stu-id="5c36b-p104">Time of the first INVITE request. This field is typically populated by data generated from the initial INVITE message in the session. If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5c36b-125"><strong>конференцеури</strong></span><span class="sxs-lookup"><span data-stu-id="5c36b-125"><strong>ConferenceUri</strong></span></span></p></td>
<td><p><span data-ttu-id="5c36b-126">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="5c36b-126">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="5c36b-127">Идентификатор URI конференции.</span><span class="sxs-lookup"><span data-stu-id="5c36b-127">URI of the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5c36b-128"><strong>конференцеуритипе</strong></span><span class="sxs-lookup"><span data-stu-id="5c36b-128"><strong>ConferenceUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="5c36b-129">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="5c36b-129">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="5c36b-130">Тип идентификатора URI конференции.</span><span class="sxs-lookup"><span data-stu-id="5c36b-130">Type of conference URI.</span></span> <span data-ttu-id="5c36b-131">Дополнительные сведения см. <a href="lync-server-2013-uritypes-table.md">в таблице таблица uritypes в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="5c36b-131">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5c36b-132"><strong>конфинстанце</strong></span><span class="sxs-lookup"><span data-stu-id="5c36b-132"><strong>ConfInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="5c36b-133">идентификатора</span><span class="sxs-lookup"><span data-stu-id="5c36b-133">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="5c36b-p106">Идентификатор, который разделяет экземпляры повторяющихся конференций. Каждый повторяющийся экземпляр конференции имеет один и тот же ConferenceURI, но разное значение ConfInstance.</span><span class="sxs-lookup"><span data-stu-id="5c36b-p106">Identifier that differentiates between instances of recurring conferences. Each recurring conference instance has the same ConferenceURI but a different ConfInstance value.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5c36b-136"><strong>мкуконференцеури</strong></span><span class="sxs-lookup"><span data-stu-id="5c36b-136"><strong>McuConferenceUri</strong></span></span></p></td>
<td><p><span data-ttu-id="5c36b-137">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="5c36b-137">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="5c36b-138">Идентификатор URI сервера конференц-связи.</span><span class="sxs-lookup"><span data-stu-id="5c36b-138">URI of the conferencing server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5c36b-139"><strong>мкуконференцеуритипе</strong></span><span class="sxs-lookup"><span data-stu-id="5c36b-139"><strong>McuConferenceUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="5c36b-140">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="5c36b-140">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="5c36b-141">Тип идентификатора URI сервера конференц-связи.</span><span class="sxs-lookup"><span data-stu-id="5c36b-141">Type of conferencing server URI.</span></span> <span data-ttu-id="5c36b-142">Дополнительные сведения см. <a href="lync-server-2013-uritypes-table.md">в таблице таблица uritypes в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="5c36b-142">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5c36b-143"><strong>UserUri</strong></span><span class="sxs-lookup"><span data-stu-id="5c36b-143"><strong>UserUri</strong></span></span></p></td>
<td><p><span data-ttu-id="5c36b-144">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="5c36b-144">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="5c36b-145">URI пользователя, участвующего в сеансе.</span><span class="sxs-lookup"><span data-stu-id="5c36b-145">URI of the user involved in the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5c36b-146"><strong>усеруритипе</strong></span><span class="sxs-lookup"><span data-stu-id="5c36b-146"><strong>UserUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="5c36b-147">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="5c36b-147">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="5c36b-148">Тип URI пользователя, который являлся участником сеанса.</span><span class="sxs-lookup"><span data-stu-id="5c36b-148">Type of URI of the user whose was part of the session.</span></span> <span data-ttu-id="5c36b-149">Дополнительные сведения см. <a href="lync-server-2013-uritypes-table.md">в таблице таблица uritypes в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="5c36b-149">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5c36b-150"><strong>усертенант</strong></span><span class="sxs-lookup"><span data-stu-id="5c36b-150"><strong>UserTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="5c36b-151">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="5c36b-151">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="5c36b-152">Клиент пользователя, который являлся участником сеанса.</span><span class="sxs-lookup"><span data-stu-id="5c36b-152">Tenant of the user whose was part of the session.</span></span> <span data-ttu-id="5c36b-153">Дополнительные сведения см. <a href="lync-server-2013-tenants-table.md">в таблице клиентов в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="5c36b-153">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5c36b-154"><strong>усерендпоинтид</strong></span><span class="sxs-lookup"><span data-stu-id="5c36b-154"><strong>UserEndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="5c36b-155">идентификатора</span><span class="sxs-lookup"><span data-stu-id="5c36b-155">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="5c36b-156">Уникальный идентификатор пользователя, который являлся участником сеанса.</span><span class="sxs-lookup"><span data-stu-id="5c36b-156">Unique identifier of the user whose was part of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5c36b-157"><strong>EndTime</strong></span><span class="sxs-lookup"><span data-stu-id="5c36b-157"><strong>EndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="5c36b-158">datetime</span><span class="sxs-lookup"><span data-stu-id="5c36b-158">datetime</span></span></p></td>
<td><p><span data-ttu-id="5c36b-159">Время окончания сеанса.</span><span class="sxs-lookup"><span data-stu-id="5c36b-159">End time of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5c36b-160"><strong>конференцеклиентверсион</strong></span><span class="sxs-lookup"><span data-stu-id="5c36b-160"><strong>ConferenceClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="5c36b-161">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="5c36b-161">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="5c36b-162">Версия сервера конференц-связи.</span><span class="sxs-lookup"><span data-stu-id="5c36b-162">Version of conference server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5c36b-163"><strong>конференцеклиенттипе</strong></span><span class="sxs-lookup"><span data-stu-id="5c36b-163"><strong>ConferenceClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="5c36b-164">int</span><span class="sxs-lookup"><span data-stu-id="5c36b-164">int</span></span></p></td>
<td><p><span data-ttu-id="5c36b-165">Тип сервера конференц-связи.</span><span class="sxs-lookup"><span data-stu-id="5c36b-165">Type of conference server.</span></span> <span data-ttu-id="5c36b-166">Дополнительные сведения см. <a href="lync-server-2013-useragentdef-table.md">в таблице таблица useragentdef в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="5c36b-166">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5c36b-167"><strong>конференцекатегори</strong></span><span class="sxs-lookup"><span data-stu-id="5c36b-167"><strong>ConferenceCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="5c36b-168">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="5c36b-168">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="5c36b-169">Категория сервера конференц-связи.</span><span class="sxs-lookup"><span data-stu-id="5c36b-169">Conference server category.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5c36b-170"><strong>усерклиентверсион</strong></span><span class="sxs-lookup"><span data-stu-id="5c36b-170"><strong>UserClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="5c36b-171">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="5c36b-171">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="5c36b-172">Версия клиента, используемая пользователем, который являлся участником сеанса.</span><span class="sxs-lookup"><span data-stu-id="5c36b-172">Version of client used by the user who participated in the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5c36b-173"><strong>усерклиенттипе</strong></span><span class="sxs-lookup"><span data-stu-id="5c36b-173"><strong>UserClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="5c36b-174">int</span><span class="sxs-lookup"><span data-stu-id="5c36b-174">int</span></span></p></td>
<td><p><span data-ttu-id="5c36b-175">Клиент, использованный пользователем, который являлся участником сеанса.</span><span class="sxs-lookup"><span data-stu-id="5c36b-175">Client used by the user who participated in the session.</span></span> <span data-ttu-id="5c36b-176">Дополнительные сведения приведены <a href="lync-server-2013-useragentdef-table.md">в таблице таблица useragentdef в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="5c36b-176">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5c36b-177"><strong>усерклиенткатегори</strong></span><span class="sxs-lookup"><span data-stu-id="5c36b-177"><strong>UserClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="5c36b-178">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="5c36b-178">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="5c36b-179">Название категории клиента, использованной пользователем, который являлся частью сеанса.</span><span class="sxs-lookup"><span data-stu-id="5c36b-179">Name of the category of the client used by the user who was part of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5c36b-180"><strong>онбехалфофури</strong></span><span class="sxs-lookup"><span data-stu-id="5c36b-180"><strong>OnBehalfOfUri</strong></span></span></p></td>
<td><p><span data-ttu-id="5c36b-181">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="5c36b-181">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="5c36b-182">URI пользователя, от чьего имени был запущен сеанс.</span><span class="sxs-lookup"><span data-stu-id="5c36b-182">URI of the user on whose behalf the session was started.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5c36b-183"><strong>онбехалфофуритипе</strong></span><span class="sxs-lookup"><span data-stu-id="5c36b-183"><strong>OnBehalfOfUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="5c36b-184">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="5c36b-184">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="5c36b-185">Тип URI пользователя, от имени которого был запущен сеанс.</span><span class="sxs-lookup"><span data-stu-id="5c36b-185">Type of URI of the user on whose behalf the session was started.</span></span> <span data-ttu-id="5c36b-186">Дополнительные сведения см. <a href="lync-server-2013-uritypes-table.md">в таблице таблица uritypes в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="5c36b-186">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5c36b-187"><strong>онбехалфофтенант</strong></span><span class="sxs-lookup"><span data-stu-id="5c36b-187"><strong>OnBehalfOfTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="5c36b-188">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="5c36b-188">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="5c36b-189">Клиент пользователя, от имени которого был запущен сеанс.</span><span class="sxs-lookup"><span data-stu-id="5c36b-189">Tenant of the user whose on behalf the session was started.</span></span> <span data-ttu-id="5c36b-190">Дополнительные сведения см. <a href="lync-server-2013-tenants-table.md">в таблице клиентов в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="5c36b-190">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5c36b-191"><strong>реферредбюри</strong></span><span class="sxs-lookup"><span data-stu-id="5c36b-191"><strong>ReferredByUri</strong></span></span></p></td>
<td><p><span data-ttu-id="5c36b-192">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="5c36b-192">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="5c36b-193">URI пользователя, который указал ссылку на сеанс.</span><span class="sxs-lookup"><span data-stu-id="5c36b-193">URI of the user who referred the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5c36b-194"><strong>реферредбюритипе</strong></span><span class="sxs-lookup"><span data-stu-id="5c36b-194"><strong>ReferredByUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="5c36b-195">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="5c36b-195">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="5c36b-196">Тип URI пользователя, который указал ссылку на сеанс.</span><span class="sxs-lookup"><span data-stu-id="5c36b-196">Type of URI of the user who referred the session.</span></span> <span data-ttu-id="5c36b-197">Дополнительные сведения см. <a href="lync-server-2013-uritypes-table.md">в таблице таблица uritypes в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="5c36b-197">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5c36b-198"><strong>реферредбюритенант</strong></span><span class="sxs-lookup"><span data-stu-id="5c36b-198"><strong>ReferredByUriTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="5c36b-199">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="5c36b-199">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="5c36b-200">Клиент пользователя, который указал ссылку на сеанс.</span><span class="sxs-lookup"><span data-stu-id="5c36b-200">Tenant of the user who referred the session.</span></span> <span data-ttu-id="5c36b-201">Дополнительные сведения см. <a href="lync-server-2013-tenants-table.md">в таблице клиентов в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="5c36b-201">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5c36b-202"><strong>DialogId</strong></span><span class="sxs-lookup"><span data-stu-id="5c36b-202"><strong>DialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="5c36b-203">варстринг (775)</span><span class="sxs-lookup"><span data-stu-id="5c36b-203">varstring(775)</span></span></p></td>
<td><p><span data-ttu-id="5c36b-p116">ИД диалога SIP в следующем формате:</span><span class="sxs-lookup"><span data-stu-id="5c36b-p116">SIP dialog ID. The format is</span></span></p>
<p><span data-ttu-id="5c36b-206">:d иалог; to – Tag</span><span class="sxs-lookup"><span data-stu-id="5c36b-206">:dialog;from-tag;to-tag</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5c36b-207"><strong>реплацедиалогидтиме</strong></span><span class="sxs-lookup"><span data-stu-id="5c36b-207"><strong>ReplaceDialogIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="5c36b-208">datetime</span><span class="sxs-lookup"><span data-stu-id="5c36b-208">datetime</span></span></p></td>
<td><p><span data-ttu-id="5c36b-209">Идентификатор диалога, который был замещен текущим сеансом.</span><span class="sxs-lookup"><span data-stu-id="5c36b-209">ID number to identify the dialog which was replaced by current session.</span></span> <span data-ttu-id="5c36b-210">Дополнительные сведения см. <a href="lync-server-2013-dialogs-table.md">в таблице диалоговых окон в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="5c36b-210">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5c36b-211"><strong>реплацедиалогидсек</strong></span><span class="sxs-lookup"><span data-stu-id="5c36b-211"><strong>ReplaceDialogIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="5c36b-212">int</span><span class="sxs-lookup"><span data-stu-id="5c36b-212">int</span></span></p></td>
<td><p><span data-ttu-id="5c36b-213">Идентификационный номер для идентификации сеанса.</span><span class="sxs-lookup"><span data-stu-id="5c36b-213">ID number to identify the session.</span></span> <span data-ttu-id="5c36b-214">Используется совместно с параметром ReplaceDialogIdTime для уникальной идентификации сеанса, замененного данным сеансом.</span><span class="sxs-lookup"><span data-stu-id="5c36b-214">Used in conjunction with ReplaceDialogIdTime to uniquely identify a session that is replaced by this session.</span></span> <span data-ttu-id="5c36b-215">Дополнительные сведения см. <a href="lync-server-2013-dialogs-table.md">в таблице диалоговых окон в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="5c36b-215">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5c36b-216"><strong>реплацесдиалогид</strong></span><span class="sxs-lookup"><span data-stu-id="5c36b-216"><strong>ReplacesDialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="5c36b-217">varchar (775)</span><span class="sxs-lookup"><span data-stu-id="5c36b-217">varchar(775)</span></span></p></td>
<td><p><span data-ttu-id="5c36b-p119">Идентификатор диалога SIP, который был замещен этим сеансом. Используется следующий формат:</span><span class="sxs-lookup"><span data-stu-id="5c36b-p119">SIP dialog ID the session replaces. The format of the is:</span></span></p>
<p><span data-ttu-id="5c36b-220">диалоговое окно; from — Tag; to – Tag</span><span class="sxs-lookup"><span data-stu-id="5c36b-220">dialog;from-tag;to-tag</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5c36b-221"><strong>исстартедбиконфсервер</strong></span><span class="sxs-lookup"><span data-stu-id="5c36b-221"><strong>IsStartedByConfServer</strong></span></span></p></td>
<td><p><span data-ttu-id="5c36b-222">Битовая</span><span class="sxs-lookup"><span data-stu-id="5c36b-222">bit</span></span></p></td>
<td><p><span data-ttu-id="5c36b-223">Указывает, был ли сеанс запущен сервером конференц-связи.</span><span class="sxs-lookup"><span data-stu-id="5c36b-223">Indicates whether the session was started by the conferencing server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5c36b-224"><strong>исендедбиконфсервер</strong></span><span class="sxs-lookup"><span data-stu-id="5c36b-224"><strong>IsEndedByConfServer</strong></span></span></p></td>
<td><p><span data-ttu-id="5c36b-225">Битовая</span><span class="sxs-lookup"><span data-stu-id="5c36b-225">bit</span></span></p></td>
<td><p><span data-ttu-id="5c36b-226">Указывает, был ли сеанс завершен сервером конференц-связи.</span><span class="sxs-lookup"><span data-stu-id="5c36b-226">Indicates whether the session was ended by the conferencing server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5c36b-227"><strong>исусеринтернал</strong></span><span class="sxs-lookup"><span data-stu-id="5c36b-227"><strong>IsUserInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="5c36b-228">Битовая</span><span class="sxs-lookup"><span data-stu-id="5c36b-228">bit</span></span></p></td>
<td><p><span data-ttu-id="5c36b-229">Показывает, зашел ли пользователь в систему из внутренней сети.</span><span class="sxs-lookup"><span data-stu-id="5c36b-229">Indicates whether the user logged on from the internal network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5c36b-230"><strong>респонсетиме</strong></span><span class="sxs-lookup"><span data-stu-id="5c36b-230"><strong>ResponseTime</strong></span></span></p></td>
<td><p><span data-ttu-id="5c36b-231">datetime</span><span class="sxs-lookup"><span data-stu-id="5c36b-231">datetime</span></span></p></td>
<td><p><span data-ttu-id="5c36b-p120">Время ответа на первое сообщение INVITE. Обычно это поле содержит данные из первоначального сообщения INVITE в сеансе. Если сообщение INVITE отсутствует, в поле записывается дата и время первого соответствующего SIP-сообщения (BYE, CANCEL, MESSAGE или INFO).</span><span class="sxs-lookup"><span data-stu-id="5c36b-p120">Time of the response to the first INVITE message. This field is typically populated by data generated from the initial INVITE message in the session. If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5c36b-235"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="5c36b-235"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="5c36b-236">int</span><span class="sxs-lookup"><span data-stu-id="5c36b-236">int</span></span></p></td>
<td><p><span data-ttu-id="5c36b-p121">Код SIP-ответа на приглашение в сеанс. Это поле обычно заполняется данными, генерируемыми из исходного сообщения INVITE в сеансе. Если сообщения INVITE нет, поле заполняется датой и временем первого релевантного SIP-сообщения (BYE, CANCEL, MESSAGE или INFO).</span><span class="sxs-lookup"><span data-stu-id="5c36b-p121">SIP response code to the session invitation. This field is typically populated by data generated from the initial INVITE message in the session. If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5c36b-240"><strong>диагностиЦид</strong></span><span class="sxs-lookup"><span data-stu-id="5c36b-240"><strong>DiagnosticId</strong></span></span></p></td>
<td><p><span data-ttu-id="5c36b-241">int</span><span class="sxs-lookup"><span data-stu-id="5c36b-241">int</span></span></p></td>
<td><p><span data-ttu-id="5c36b-242">Диагностический идентификатор, взятый из SIP-заголовков сеанса.</span><span class="sxs-lookup"><span data-stu-id="5c36b-242">Diagnostic ID captured from session SIP headers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5c36b-243"><strong>ContentType</strong></span><span class="sxs-lookup"><span data-stu-id="5c36b-243"><strong>ContentType</strong></span></span></p></td>
<td><p><span data-ttu-id="5c36b-244">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="5c36b-244">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="5c36b-245">Тип содержимого сеанса.</span><span class="sxs-lookup"><span data-stu-id="5c36b-245">Content type for the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5c36b-246"><strong>FrontEnd</strong></span><span class="sxs-lookup"><span data-stu-id="5c36b-246"><strong>FrontEnd</strong></span></span></p></td>
<td><p><span data-ttu-id="5c36b-247">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="5c36b-247">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="5c36b-248">Полное доменное имя интерфейсного сервера, который получил данные этого сеанса.</span><span class="sxs-lookup"><span data-stu-id="5c36b-248">FQDN of the Front End server that captured the data for the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5c36b-249"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="5c36b-249"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="5c36b-250">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="5c36b-250">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="5c36b-251">Полное доменное имя пула, захватившего данные для сеанса.</span><span class="sxs-lookup"><span data-stu-id="5c36b-251">FQDN of the pool that captured the data for the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5c36b-252"><strong>MediationServer</strong></span><span class="sxs-lookup"><span data-stu-id="5c36b-252"><strong>MediationServer</strong></span></span></p></td>
<td><p><span data-ttu-id="5c36b-253">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="5c36b-253">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="5c36b-254">Сервер-посредник, использованный пользователем, который являлся участником сеанса.</span><span class="sxs-lookup"><span data-stu-id="5c36b-254">Mediation Server used by the user who participated in the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5c36b-255"><strong>Шлюз</strong></span><span class="sxs-lookup"><span data-stu-id="5c36b-255"><strong>Gateway</strong></span></span></p></td>
<td><p><span data-ttu-id="5c36b-256">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="5c36b-256">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="5c36b-257">Шлюз, использованный пользователем, который являлся участником сеанса.</span><span class="sxs-lookup"><span data-stu-id="5c36b-257">Gateway used by the user who participated the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5c36b-258"><strong>EdgeServer</strong></span><span class="sxs-lookup"><span data-stu-id="5c36b-258"><strong>EdgeServer</strong></span></span></p></td>
<td><p><span data-ttu-id="5c36b-259">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="5c36b-259">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="5c36b-260">Полное доменное имя пограничного сервера, используемого пользователем, который являлся участником сеанса.</span><span class="sxs-lookup"><span data-stu-id="5c36b-260">FQDN of the Edge server used by the user who participated in the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5c36b-261"><strong>усерфлаг</strong></span><span class="sxs-lookup"><span data-stu-id="5c36b-261"><strong>UserFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="5c36b-262">smallint</span><span class="sxs-lookup"><span data-stu-id="5c36b-262">smallint</span></span></p></td>
<td><p><span data-ttu-id="5c36b-p122">Указывает атрибуты пользователя, который являлся участником сеанса. Разрешены следующие определения атрибутов.</span><span class="sxs-lookup"><span data-stu-id="5c36b-p122">Indicates the attributes of the user who participated in the session. The following attribute definitions allowed:</span></span></p>
<p><span data-ttu-id="5c36b-265">0x01 — интеграция с настольным телефоном</span><span class="sxs-lookup"><span data-stu-id="5c36b-265">0x01 - Integrated with desktop phone</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5c36b-266"><strong>каллфлаг</strong></span><span class="sxs-lookup"><span data-stu-id="5c36b-266"><strong>CallFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="5c36b-267">smallint</span><span class="sxs-lookup"><span data-stu-id="5c36b-267">smallint</span></span></p></td>
<td><p><span data-ttu-id="5c36b-p123">Указывает атрибуты вызова. Разрешены следующие определения атрибутов.</span><span class="sxs-lookup"><span data-stu-id="5c36b-p123">Indicates the call attributes. The following attribute definitions are allowed:</span></span></p>
<p><span data-ttu-id="5c36b-270">0x01 — списанный сеанс 0</span><span class="sxs-lookup"><span data-stu-id="5c36b-270">0x01 - Retried Session0</span></span></p>
<p><span data-ttu-id="5c36b-271">x02 — вызов, выполненный агентом от имени группы ответа</span><span class="sxs-lookup"><span data-stu-id="5c36b-271">x02 - A call made by agent on behalf of a Response Group</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

