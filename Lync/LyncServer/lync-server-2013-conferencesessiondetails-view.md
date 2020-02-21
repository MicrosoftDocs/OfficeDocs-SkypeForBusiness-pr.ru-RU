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
ms.openlocfilehash: 7bc6d1888753edbeb076d60d6725b6d9cffc509e
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42209365"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="conferencesessiondetails-view-in-lync-server-2013"></a><span data-ttu-id="35723-102">Представление Таблица conferencesessiondetails в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="35723-102">ConferenceSessionDetails view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="35723-103">_**Последнее изменение темы:** 2012-11-12_</span><span class="sxs-lookup"><span data-stu-id="35723-103">_**Topic Last Modified:** 2012-11-12_</span></span>

<span data-ttu-id="35723-104">Представление ConferenceSessionDetails хранит сведения о многосторонних сеансах.</span><span class="sxs-lookup"><span data-stu-id="35723-104">The ConferenceSessionDetails view stores information about multiparty sessions.</span></span> <span data-ttu-id="35723-105">Каждая запись представляет один сеанс конференц-связи, который может быть сеансом с фокусом или сеансом с определенным сервером конференц-связи.</span><span class="sxs-lookup"><span data-stu-id="35723-105">Each record represents one conference session, which could be either the session with Focus or the session with a specific conferencing server.</span></span> <span data-ttu-id="35723-106">Это представление было представлено в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="35723-106">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="35723-107">Столбец</span><span class="sxs-lookup"><span data-stu-id="35723-107">Column</span></span></th>
<th><span data-ttu-id="35723-108">Тип данных</span><span class="sxs-lookup"><span data-stu-id="35723-108">Data Type</span></span></th>
<th><span data-ttu-id="35723-109">Сведения</span><span class="sxs-lookup"><span data-stu-id="35723-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="35723-110"><strong>сессионидтиме</strong></span><span class="sxs-lookup"><span data-stu-id="35723-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="35723-111">datetime</span><span class="sxs-lookup"><span data-stu-id="35723-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="35723-112">Время запроса сеанса.</span><span class="sxs-lookup"><span data-stu-id="35723-112">Time of session request.</span></span> <span data-ttu-id="35723-113">Используется вместе с параметром SessionIdSeq для уникального определения сеанса.</span><span class="sxs-lookup"><span data-stu-id="35723-113">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="35723-114">Дополнительные сведения см. <a href="lync-server-2013-dialogs-table.md">в таблице диалоговых окон в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="35723-114">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="35723-115"><strong>сессионидсек</strong></span><span class="sxs-lookup"><span data-stu-id="35723-115"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="35723-116">int</span><span class="sxs-lookup"><span data-stu-id="35723-116">int</span></span></p></td>
<td><p><span data-ttu-id="35723-117">Идентификационный номер для идентификации сеанса.</span><span class="sxs-lookup"><span data-stu-id="35723-117">ID number to identify the session.</span></span> <span data-ttu-id="35723-118">Используется совместно с параметром SessionIdTime для уникальной идентификации сеанса.</span><span class="sxs-lookup"><span data-stu-id="35723-118">Used in conjunction with SessionIdTime to uniquely identify a session.</span></span> <span data-ttu-id="35723-119">Дополнительные сведения см. <a href="lync-server-2013-dialogs-table.md">в таблице диалоговых окон в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="35723-119">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="35723-120"><strong>инвитетиме</strong></span><span class="sxs-lookup"><span data-stu-id="35723-120"><strong>InviteTime</strong></span></span></p></td>
<td><p><span data-ttu-id="35723-121">datetime</span><span class="sxs-lookup"><span data-stu-id="35723-121">datetime</span></span></p></td>
<td><p><span data-ttu-id="35723-p104">Время первого запроса INVITE. Это поле обычно заполняется данными, генерируемыми из исходного сообщения INVITE в сеансе. При отсутствии сообщения INVITE поле заполняется датой и временем первого соответствующего сообщения SIP (BYE, CANCEL, MESSAGE или INFO).</span><span class="sxs-lookup"><span data-stu-id="35723-p104">Time of the first INVITE request. This field is typically populated by data generated from the initial INVITE message in the session. If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="35723-125"><strong>конференцеури</strong></span><span class="sxs-lookup"><span data-stu-id="35723-125"><strong>ConferenceUri</strong></span></span></p></td>
<td><p><span data-ttu-id="35723-126">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="35723-126">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="35723-127">Идентификатор URI конференции.</span><span class="sxs-lookup"><span data-stu-id="35723-127">URI of the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="35723-128"><strong>конференцеуритипе</strong></span><span class="sxs-lookup"><span data-stu-id="35723-128"><strong>ConferenceUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="35723-129">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="35723-129">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="35723-130">Тип идентификатора URI конференции.</span><span class="sxs-lookup"><span data-stu-id="35723-130">Type of conference URI.</span></span> <span data-ttu-id="35723-131">Дополнительные сведения см. <a href="lync-server-2013-uritypes-table.md">в таблице таблица uritypes в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="35723-131">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="35723-132"><strong>конфинстанце</strong></span><span class="sxs-lookup"><span data-stu-id="35723-132"><strong>ConfInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="35723-133">идентификатора</span><span class="sxs-lookup"><span data-stu-id="35723-133">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="35723-p106">Идентификатор, который разделяет экземпляры повторяющихся конференций. Каждый повторяющийся экземпляр конференции имеет один и тот же ConferenceURI, но разное значение ConfInstance.</span><span class="sxs-lookup"><span data-stu-id="35723-p106">Identifier that differentiates between instances of recurring conferences. Each recurring conference instance has the same ConferenceURI but a different ConfInstance value.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="35723-136"><strong>мкуконференцеури</strong></span><span class="sxs-lookup"><span data-stu-id="35723-136"><strong>McuConferenceUri</strong></span></span></p></td>
<td><p><span data-ttu-id="35723-137">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="35723-137">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="35723-138">Идентификатор URI сервера конференц-связи.</span><span class="sxs-lookup"><span data-stu-id="35723-138">URI of the conferencing server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="35723-139"><strong>мкуконференцеуритипе</strong></span><span class="sxs-lookup"><span data-stu-id="35723-139"><strong>McuConferenceUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="35723-140">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="35723-140">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="35723-141">Тип идентификатора URI сервера конференц-связи.</span><span class="sxs-lookup"><span data-stu-id="35723-141">Type of conferencing server URI.</span></span> <span data-ttu-id="35723-142">Дополнительные сведения см. <a href="lync-server-2013-uritypes-table.md">в таблице таблица uritypes в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="35723-142">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="35723-143"><strong>UserUri</strong></span><span class="sxs-lookup"><span data-stu-id="35723-143"><strong>UserUri</strong></span></span></p></td>
<td><p><span data-ttu-id="35723-144">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="35723-144">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="35723-145">URI пользователя, участвующего в сеансе.</span><span class="sxs-lookup"><span data-stu-id="35723-145">URI of the user involved in the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="35723-146"><strong>усеруритипе</strong></span><span class="sxs-lookup"><span data-stu-id="35723-146"><strong>UserUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="35723-147">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="35723-147">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="35723-148">Тип URI пользователя, который являлся участником сеанса.</span><span class="sxs-lookup"><span data-stu-id="35723-148">Type of URI of the user whose was part of the session.</span></span> <span data-ttu-id="35723-149">Дополнительные сведения см. <a href="lync-server-2013-uritypes-table.md">в таблице таблица uritypes в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="35723-149">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="35723-150"><strong>усертенант</strong></span><span class="sxs-lookup"><span data-stu-id="35723-150"><strong>UserTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="35723-151">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="35723-151">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="35723-152">Клиент пользователя, который являлся участником сеанса.</span><span class="sxs-lookup"><span data-stu-id="35723-152">Tenant of the user whose was part of the session.</span></span> <span data-ttu-id="35723-153">Дополнительные сведения см. <a href="lync-server-2013-tenants-table.md">в таблице клиентов в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="35723-153">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="35723-154"><strong>усерендпоинтид</strong></span><span class="sxs-lookup"><span data-stu-id="35723-154"><strong>UserEndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="35723-155">идентификатора</span><span class="sxs-lookup"><span data-stu-id="35723-155">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="35723-156">Уникальный идентификатор пользователя, который являлся участником сеанса.</span><span class="sxs-lookup"><span data-stu-id="35723-156">Unique identifier of the user whose was part of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="35723-157"><strong>EndTime</strong></span><span class="sxs-lookup"><span data-stu-id="35723-157"><strong>EndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="35723-158">datetime</span><span class="sxs-lookup"><span data-stu-id="35723-158">datetime</span></span></p></td>
<td><p><span data-ttu-id="35723-159">Время окончания сеанса.</span><span class="sxs-lookup"><span data-stu-id="35723-159">End time of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="35723-160"><strong>конференцеклиентверсион</strong></span><span class="sxs-lookup"><span data-stu-id="35723-160"><strong>ConferenceClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="35723-161">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="35723-161">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="35723-162">Версия сервера конференц-связи.</span><span class="sxs-lookup"><span data-stu-id="35723-162">Version of conference server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="35723-163"><strong>конференцеклиенттипе</strong></span><span class="sxs-lookup"><span data-stu-id="35723-163"><strong>ConferenceClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="35723-164">int</span><span class="sxs-lookup"><span data-stu-id="35723-164">int</span></span></p></td>
<td><p><span data-ttu-id="35723-165">Тип сервера конференц-связи.</span><span class="sxs-lookup"><span data-stu-id="35723-165">Type of conference server.</span></span> <span data-ttu-id="35723-166">Дополнительные сведения см. <a href="lync-server-2013-useragentdef-table.md">в таблице таблица useragentdef в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="35723-166">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="35723-167"><strong>конференцекатегори</strong></span><span class="sxs-lookup"><span data-stu-id="35723-167"><strong>ConferenceCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="35723-168">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="35723-168">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="35723-169">Категория сервера конференц-связи.</span><span class="sxs-lookup"><span data-stu-id="35723-169">Conference server category.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="35723-170"><strong>усерклиентверсион</strong></span><span class="sxs-lookup"><span data-stu-id="35723-170"><strong>UserClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="35723-171">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="35723-171">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="35723-172">Версия клиента, используемая пользователем, который являлся участником сеанса.</span><span class="sxs-lookup"><span data-stu-id="35723-172">Version of client used by the user who participated in the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="35723-173"><strong>усерклиенттипе</strong></span><span class="sxs-lookup"><span data-stu-id="35723-173"><strong>UserClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="35723-174">int</span><span class="sxs-lookup"><span data-stu-id="35723-174">int</span></span></p></td>
<td><p><span data-ttu-id="35723-175">Клиент, использованный пользователем, который являлся участником сеанса.</span><span class="sxs-lookup"><span data-stu-id="35723-175">Client used by the user who participated in the session.</span></span> <span data-ttu-id="35723-176">Дополнительные сведения приведены <a href="lync-server-2013-useragentdef-table.md">в таблице таблица useragentdef в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="35723-176">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="35723-177"><strong>усерклиенткатегори</strong></span><span class="sxs-lookup"><span data-stu-id="35723-177"><strong>UserClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="35723-178">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="35723-178">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="35723-179">Название категории клиента, использованной пользователем, который являлся частью сеанса.</span><span class="sxs-lookup"><span data-stu-id="35723-179">Name of the category of the client used by the user who was part of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="35723-180"><strong>онбехалфофури</strong></span><span class="sxs-lookup"><span data-stu-id="35723-180"><strong>OnBehalfOfUri</strong></span></span></p></td>
<td><p><span data-ttu-id="35723-181">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="35723-181">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="35723-182">URI пользователя, от чьего имени был запущен сеанс.</span><span class="sxs-lookup"><span data-stu-id="35723-182">URI of the user on whose behalf the session was started.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="35723-183"><strong>онбехалфофуритипе</strong></span><span class="sxs-lookup"><span data-stu-id="35723-183"><strong>OnBehalfOfUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="35723-184">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="35723-184">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="35723-185">Тип URI пользователя, от имени которого был запущен сеанс.</span><span class="sxs-lookup"><span data-stu-id="35723-185">Type of URI of the user on whose behalf the session was started.</span></span> <span data-ttu-id="35723-186">Дополнительные сведения см. <a href="lync-server-2013-uritypes-table.md">в таблице таблица uritypes в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="35723-186">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="35723-187"><strong>онбехалфофтенант</strong></span><span class="sxs-lookup"><span data-stu-id="35723-187"><strong>OnBehalfOfTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="35723-188">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="35723-188">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="35723-189">Клиент пользователя, от имени которого был запущен сеанс.</span><span class="sxs-lookup"><span data-stu-id="35723-189">Tenant of the user whose on behalf the session was started.</span></span> <span data-ttu-id="35723-190">Дополнительные сведения см. <a href="lync-server-2013-tenants-table.md">в таблице клиентов в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="35723-190">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="35723-191"><strong>реферредбюри</strong></span><span class="sxs-lookup"><span data-stu-id="35723-191"><strong>ReferredByUri</strong></span></span></p></td>
<td><p><span data-ttu-id="35723-192">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="35723-192">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="35723-193">URI пользователя, который указал ссылку на сеанс.</span><span class="sxs-lookup"><span data-stu-id="35723-193">URI of the user who referred the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="35723-194"><strong>реферредбюритипе</strong></span><span class="sxs-lookup"><span data-stu-id="35723-194"><strong>ReferredByUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="35723-195">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="35723-195">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="35723-196">Тип URI пользователя, который указал ссылку на сеанс.</span><span class="sxs-lookup"><span data-stu-id="35723-196">Type of URI of the user who referred the session.</span></span> <span data-ttu-id="35723-197">Дополнительные сведения см. <a href="lync-server-2013-uritypes-table.md">в таблице таблица uritypes в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="35723-197">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="35723-198"><strong>реферредбюритенант</strong></span><span class="sxs-lookup"><span data-stu-id="35723-198"><strong>ReferredByUriTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="35723-199">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="35723-199">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="35723-200">Клиент пользователя, который указал ссылку на сеанс.</span><span class="sxs-lookup"><span data-stu-id="35723-200">Tenant of the user who referred the session.</span></span> <span data-ttu-id="35723-201">Дополнительные сведения см. <a href="lync-server-2013-tenants-table.md">в таблице клиентов в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="35723-201">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="35723-202"><strong>DialogId</strong></span><span class="sxs-lookup"><span data-stu-id="35723-202"><strong>DialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="35723-203">варстринг (775)</span><span class="sxs-lookup"><span data-stu-id="35723-203">varstring(775)</span></span></p></td>
<td><p><span data-ttu-id="35723-p116">ИД диалога SIP в следующем формате:</span><span class="sxs-lookup"><span data-stu-id="35723-p116">SIP dialog ID. The format is</span></span></p>
<p><span data-ttu-id="35723-206">:d иалог; to – Tag</span><span class="sxs-lookup"><span data-stu-id="35723-206">:dialog;from-tag;to-tag</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="35723-207"><strong>реплацедиалогидтиме</strong></span><span class="sxs-lookup"><span data-stu-id="35723-207"><strong>ReplaceDialogIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="35723-208">datetime</span><span class="sxs-lookup"><span data-stu-id="35723-208">datetime</span></span></p></td>
<td><p><span data-ttu-id="35723-209">Идентификатор диалога, который был замещен текущим сеансом.</span><span class="sxs-lookup"><span data-stu-id="35723-209">ID number to identify the dialog which was replaced by current session.</span></span> <span data-ttu-id="35723-210">Дополнительные сведения см. <a href="lync-server-2013-dialogs-table.md">в таблице диалоговых окон в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="35723-210">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="35723-211"><strong>реплацедиалогидсек</strong></span><span class="sxs-lookup"><span data-stu-id="35723-211"><strong>ReplaceDialogIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="35723-212">int</span><span class="sxs-lookup"><span data-stu-id="35723-212">int</span></span></p></td>
<td><p><span data-ttu-id="35723-213">Идентификационный номер для идентификации сеанса.</span><span class="sxs-lookup"><span data-stu-id="35723-213">ID number to identify the session.</span></span> <span data-ttu-id="35723-214">Используется совместно с параметром ReplaceDialogIdTime для уникальной идентификации сеанса, замененного данным сеансом.</span><span class="sxs-lookup"><span data-stu-id="35723-214">Used in conjunction with ReplaceDialogIdTime to uniquely identify a session that is replaced by this session.</span></span> <span data-ttu-id="35723-215">Дополнительные сведения см. <a href="lync-server-2013-dialogs-table.md">в таблице диалоговых окон в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="35723-215">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="35723-216"><strong>реплацесдиалогид</strong></span><span class="sxs-lookup"><span data-stu-id="35723-216"><strong>ReplacesDialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="35723-217">varchar (775)</span><span class="sxs-lookup"><span data-stu-id="35723-217">varchar(775)</span></span></p></td>
<td><p><span data-ttu-id="35723-p119">Идентификатор диалога SIP, который был замещен этим сеансом. Используется следующий формат:</span><span class="sxs-lookup"><span data-stu-id="35723-p119">SIP dialog ID the session replaces. The format of the is:</span></span></p>
<p><span data-ttu-id="35723-220">диалоговое окно; from — Tag; to – Tag</span><span class="sxs-lookup"><span data-stu-id="35723-220">dialog;from-tag;to-tag</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="35723-221"><strong>исстартедбиконфсервер</strong></span><span class="sxs-lookup"><span data-stu-id="35723-221"><strong>IsStartedByConfServer</strong></span></span></p></td>
<td><p><span data-ttu-id="35723-222">Битовая</span><span class="sxs-lookup"><span data-stu-id="35723-222">bit</span></span></p></td>
<td><p><span data-ttu-id="35723-223">Указывает, был ли сеанс запущен сервером конференц-связи.</span><span class="sxs-lookup"><span data-stu-id="35723-223">Indicates whether the session was started by the conferencing server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="35723-224"><strong>исендедбиконфсервер</strong></span><span class="sxs-lookup"><span data-stu-id="35723-224"><strong>IsEndedByConfServer</strong></span></span></p></td>
<td><p><span data-ttu-id="35723-225">Битовая</span><span class="sxs-lookup"><span data-stu-id="35723-225">bit</span></span></p></td>
<td><p><span data-ttu-id="35723-226">Указывает, был ли сеанс завершен сервером конференц-связи.</span><span class="sxs-lookup"><span data-stu-id="35723-226">Indicates whether the session was ended by the conferencing server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="35723-227"><strong>исусеринтернал</strong></span><span class="sxs-lookup"><span data-stu-id="35723-227"><strong>IsUserInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="35723-228">Битовая</span><span class="sxs-lookup"><span data-stu-id="35723-228">bit</span></span></p></td>
<td><p><span data-ttu-id="35723-229">Показывает, зашел ли пользователь в систему из внутренней сети.</span><span class="sxs-lookup"><span data-stu-id="35723-229">Indicates whether the user logged on from the internal network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="35723-230"><strong>респонсетиме</strong></span><span class="sxs-lookup"><span data-stu-id="35723-230"><strong>ResponseTime</strong></span></span></p></td>
<td><p><span data-ttu-id="35723-231">datetime</span><span class="sxs-lookup"><span data-stu-id="35723-231">datetime</span></span></p></td>
<td><p><span data-ttu-id="35723-p120">Время ответа на первое сообщение INVITE. Обычно это поле содержит данные из первоначального сообщения INVITE в сеансе. Если сообщение INVITE отсутствует, в поле записывается дата и время первого соответствующего SIP-сообщения (BYE, CANCEL, MESSAGE или INFO).</span><span class="sxs-lookup"><span data-stu-id="35723-p120">Time of the response to the first INVITE message. This field is typically populated by data generated from the initial INVITE message in the session. If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="35723-235"><strong>респонсекоде</strong></span><span class="sxs-lookup"><span data-stu-id="35723-235"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="35723-236">int</span><span class="sxs-lookup"><span data-stu-id="35723-236">int</span></span></p></td>
<td><p><span data-ttu-id="35723-p121">Код SIP-ответа на приглашение в сеанс. Это поле обычно заполняется данными, генерируемыми из исходного сообщения INVITE в сеансе. Если сообщения INVITE нет, поле заполняется датой и временем первого релевантного SIP-сообщения (BYE, CANCEL, MESSAGE или INFO).</span><span class="sxs-lookup"><span data-stu-id="35723-p121">SIP response code to the session invitation. This field is typically populated by data generated from the initial INVITE message in the session. If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="35723-240"><strong>диагностиЦид</strong></span><span class="sxs-lookup"><span data-stu-id="35723-240"><strong>DiagnosticId</strong></span></span></p></td>
<td><p><span data-ttu-id="35723-241">int</span><span class="sxs-lookup"><span data-stu-id="35723-241">int</span></span></p></td>
<td><p><span data-ttu-id="35723-242">Диагностический идентификатор, взятый из SIP-заголовков сеанса.</span><span class="sxs-lookup"><span data-stu-id="35723-242">Diagnostic ID captured from session SIP headers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="35723-243"><strong>ContentType</strong></span><span class="sxs-lookup"><span data-stu-id="35723-243"><strong>ContentType</strong></span></span></p></td>
<td><p><span data-ttu-id="35723-244">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="35723-244">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="35723-245">Тип содержимого сеанса.</span><span class="sxs-lookup"><span data-stu-id="35723-245">Content type for the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="35723-246"><strong>Интерфейса</strong></span><span class="sxs-lookup"><span data-stu-id="35723-246"><strong>FrontEnd</strong></span></span></p></td>
<td><p><span data-ttu-id="35723-247">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="35723-247">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="35723-248">Полное доменное имя интерфейсного сервера, который получил данные этого сеанса.</span><span class="sxs-lookup"><span data-stu-id="35723-248">FQDN of the Front End server that captured the data for the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="35723-249"><strong>Ресурсов</strong></span><span class="sxs-lookup"><span data-stu-id="35723-249"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="35723-250">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="35723-250">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="35723-251">Полное доменное имя пула, захватившего данные для сеанса.</span><span class="sxs-lookup"><span data-stu-id="35723-251">FQDN of the pool that captured the data for the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="35723-252"><strong>MediationServer</strong></span><span class="sxs-lookup"><span data-stu-id="35723-252"><strong>MediationServer</strong></span></span></p></td>
<td><p><span data-ttu-id="35723-253">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="35723-253">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="35723-254">Сервер-посредник, использованный пользователем, который являлся участником сеанса.</span><span class="sxs-lookup"><span data-stu-id="35723-254">Mediation Server used by the user who participated in the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="35723-255"><strong>Шлюз</strong></span><span class="sxs-lookup"><span data-stu-id="35723-255"><strong>Gateway</strong></span></span></p></td>
<td><p><span data-ttu-id="35723-256">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="35723-256">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="35723-257">Шлюз, использованный пользователем, который являлся участником сеанса.</span><span class="sxs-lookup"><span data-stu-id="35723-257">Gateway used by the user who participated the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="35723-258"><strong>EdgeServer</strong></span><span class="sxs-lookup"><span data-stu-id="35723-258"><strong>EdgeServer</strong></span></span></p></td>
<td><p><span data-ttu-id="35723-259">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="35723-259">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="35723-260">Полное доменное имя пограничного сервера, используемого пользователем, который являлся участником сеанса.</span><span class="sxs-lookup"><span data-stu-id="35723-260">FQDN of the Edge server used by the user who participated in the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="35723-261"><strong>усерфлаг</strong></span><span class="sxs-lookup"><span data-stu-id="35723-261"><strong>UserFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="35723-262">smallint</span><span class="sxs-lookup"><span data-stu-id="35723-262">smallint</span></span></p></td>
<td><p><span data-ttu-id="35723-p122">Указывает атрибуты пользователя, который являлся участником сеанса. Разрешены следующие определения атрибутов.</span><span class="sxs-lookup"><span data-stu-id="35723-p122">Indicates the attributes of the user who participated in the session. The following attribute definitions allowed:</span></span></p>
<p><span data-ttu-id="35723-265">0x01 — интеграция с настольным телефоном</span><span class="sxs-lookup"><span data-stu-id="35723-265">0x01 - Integrated with desktop phone</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="35723-266"><strong>каллфлаг</strong></span><span class="sxs-lookup"><span data-stu-id="35723-266"><strong>CallFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="35723-267">smallint</span><span class="sxs-lookup"><span data-stu-id="35723-267">smallint</span></span></p></td>
<td><p><span data-ttu-id="35723-p123">Указывает атрибуты вызова. Разрешены следующие определения атрибутов.</span><span class="sxs-lookup"><span data-stu-id="35723-p123">Indicates the call attributes. The following attribute definitions are allowed:</span></span></p>
<p><span data-ttu-id="35723-270">0x01 — списанный сеанс 0</span><span class="sxs-lookup"><span data-stu-id="35723-270">0x01 - Retried Session0</span></span></p>
<p><span data-ttu-id="35723-271">x02 — вызов, выполненный агентом от имени группы ответа</span><span class="sxs-lookup"><span data-stu-id="35723-271">x02 - A call made by agent on behalf of a Response Group</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

