---
title: 'Lync Server 2013: представление Конференцесессиондетаилс'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: ConferenceSessionDetails view
ms:assetid: 5858c84d-baed-421d-ad1d-3726e150e256
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688066(v=OCS.15)
ms:contentKeyID: 49733660
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0432606a49766f7ea6755f5f234343ac70ca6c0e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34841498"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conferencesessiondetails-view-in-lync-server-2013"></a><span data-ttu-id="77701-102">Конференцесессиондетаилс представления в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="77701-102">ConferenceSessionDetails view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="77701-103">_**Тема последнего изменения:** 2012-11-12_</span><span class="sxs-lookup"><span data-stu-id="77701-103">_**Topic Last Modified:** 2012-11-12_</span></span>

<span data-ttu-id="77701-104">В представлении Конференцесессиондетаилс хранятся сведения о многокомпонентных сеансах.</span><span class="sxs-lookup"><span data-stu-id="77701-104">The ConferenceSessionDetails view stores information about multiparty sessions.</span></span> <span data-ttu-id="77701-105">Каждая запись представляет один сеанс конференции, который может быть либо сеансом с фокусом, либо сеансом с определенным сервером конференц-связи.</span><span class="sxs-lookup"><span data-stu-id="77701-105">Each record represents one conference session, which could be either the session with Focus or the session with a specific conferencing server.</span></span> <span data-ttu-id="77701-106">Это представление было представлено в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="77701-106">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="77701-107">Столбец</span><span class="sxs-lookup"><span data-stu-id="77701-107">Column</span></span></th>
<th><span data-ttu-id="77701-108">Тип данных</span><span class="sxs-lookup"><span data-stu-id="77701-108">Data Type</span></span></th>
<th><span data-ttu-id="77701-109">Подробности</span><span class="sxs-lookup"><span data-stu-id="77701-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="77701-110"><strong>Сессионидтиме</strong></span><span class="sxs-lookup"><span data-stu-id="77701-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="77701-111">datetime</span><span class="sxs-lookup"><span data-stu-id="77701-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="77701-112">Время запроса сеанса.</span><span class="sxs-lookup"><span data-stu-id="77701-112">Time of session request.</span></span> <span data-ttu-id="77701-113">Используется в сочетании с Сессионидсек для уникальной идентификации сеанса.</span><span class="sxs-lookup"><span data-stu-id="77701-113">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="77701-114">Дополнительные сведения приведены <a href="lync-server-2013-dialogs-table.md">в таблице диалоговые окна Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="77701-114">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="77701-115"><strong>Сессионидсек</strong></span><span class="sxs-lookup"><span data-stu-id="77701-115"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="77701-116">целое</span><span class="sxs-lookup"><span data-stu-id="77701-116">int</span></span></p></td>
<td><p><span data-ttu-id="77701-117">ИДЕНТИФИКАЦИОНный номер для идентификации сеанса.</span><span class="sxs-lookup"><span data-stu-id="77701-117">ID number to identify the session.</span></span> <span data-ttu-id="77701-118">Используется в сочетании с Сессионидтиме для уникальной идентификации сеанса.</span><span class="sxs-lookup"><span data-stu-id="77701-118">Used in conjunction with SessionIdTime to uniquely identify a session.</span></span> <span data-ttu-id="77701-119">Дополнительные сведения приведены <a href="lync-server-2013-dialogs-table.md">в таблице диалоговые окна Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="77701-119">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="77701-120"><strong>Инвитетиме</strong></span><span class="sxs-lookup"><span data-stu-id="77701-120"><strong>InviteTime</strong></span></span></p></td>
<td><p><span data-ttu-id="77701-121">datetime</span><span class="sxs-lookup"><span data-stu-id="77701-121">datetime</span></span></p></td>
<td><p><span data-ttu-id="77701-122">Время первого запроса приглашения.</span><span class="sxs-lookup"><span data-stu-id="77701-122">Time of the first INVITE request.</span></span> <span data-ttu-id="77701-123">Это поле обычно заполняется данными, созданными на основе исходного сообщения INVITE в сеансе.</span><span class="sxs-lookup"><span data-stu-id="77701-123">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="77701-124">Если сообщение приглашения отсутствует, поле заполняется датой и временем первого соответствующего сообщения SIP (пока, CANCEL, MESSAGE или INFO).</span><span class="sxs-lookup"><span data-stu-id="77701-124">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="77701-125"><strong>ConferenceUri</strong></span><span class="sxs-lookup"><span data-stu-id="77701-125"><strong>ConferenceUri</strong></span></span></p></td>
<td><p><span data-ttu-id="77701-126">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="77701-126">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="77701-127">Универсальный код ресурса (URI) Конференции.</span><span class="sxs-lookup"><span data-stu-id="77701-127">URI of the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="77701-128"><strong>Конференцеуритипе</strong></span><span class="sxs-lookup"><span data-stu-id="77701-128"><strong>ConferenceUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="77701-129">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="77701-129">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="77701-130">Тип URI конференции.</span><span class="sxs-lookup"><span data-stu-id="77701-130">Type of conference URI.</span></span> <span data-ttu-id="77701-131">Для получения дополнительных сведений ознакомьтесь с <a href="lync-server-2013-uritypes-table.md">таблицей уритипес в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="77701-131">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="77701-132"><strong>Конфинстанце</strong></span><span class="sxs-lookup"><span data-stu-id="77701-132"><strong>ConfInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="77701-133">идентификатора</span><span class="sxs-lookup"><span data-stu-id="77701-133">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="77701-134">Идентификатор, отличающийся между экземплярами повторяющихся конференций.</span><span class="sxs-lookup"><span data-stu-id="77701-134">Identifier that differentiates between instances of recurring conferences.</span></span> <span data-ttu-id="77701-135">Каждый экземпляр повторяющейся Конференции имеет один и тот же Конференцеури, но другое значение Конфинстанце.</span><span class="sxs-lookup"><span data-stu-id="77701-135">Each recurring conference instance has the same ConferenceURI but a different ConfInstance value.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="77701-136"><strong>Мкуконференцеури</strong></span><span class="sxs-lookup"><span data-stu-id="77701-136"><strong>McuConferenceUri</strong></span></span></p></td>
<td><p><span data-ttu-id="77701-137">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="77701-137">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="77701-138">Универсальный код ресурса (URI) сервера конференц-связи.</span><span class="sxs-lookup"><span data-stu-id="77701-138">URI of the conferencing server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="77701-139"><strong>Мкуконференцеуритипе</strong></span><span class="sxs-lookup"><span data-stu-id="77701-139"><strong>McuConferenceUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="77701-140">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="77701-140">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="77701-141">Тип URI сервера конференц-связи.</span><span class="sxs-lookup"><span data-stu-id="77701-141">Type of conferencing server URI.</span></span> <span data-ttu-id="77701-142">Для получения дополнительных сведений ознакомьтесь с <a href="lync-server-2013-uritypes-table.md">таблицей уритипес в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="77701-142">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="77701-143"><strong>Усерури</strong></span><span class="sxs-lookup"><span data-stu-id="77701-143"><strong>UserUri</strong></span></span></p></td>
<td><p><span data-ttu-id="77701-144">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="77701-144">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="77701-145">Универсальный код ресурса (URI) пользователя, участвующего в сеансе.</span><span class="sxs-lookup"><span data-stu-id="77701-145">URI of the user involved in the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="77701-146"><strong>Усеруритипе</strong></span><span class="sxs-lookup"><span data-stu-id="77701-146"><strong>UserUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="77701-147">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="77701-147">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="77701-148">Тип URI пользователя, который является частью сеанса.</span><span class="sxs-lookup"><span data-stu-id="77701-148">Type of URI of the user whose was part of the session.</span></span> <span data-ttu-id="77701-149">Для получения дополнительных сведений ознакомьтесь с <a href="lync-server-2013-uritypes-table.md">таблицей уритипес в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="77701-149">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="77701-150"><strong>Усертенант</strong></span><span class="sxs-lookup"><span data-stu-id="77701-150"><strong>UserTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="77701-151">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="77701-151">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="77701-152">Клиент пользователя, который является частью сеанса.</span><span class="sxs-lookup"><span data-stu-id="77701-152">Tenant of the user whose was part of the session.</span></span> <span data-ttu-id="77701-153">Дополнительные сведения приведены в <a href="lync-server-2013-tenants-table.md">таблице "клиенты" в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="77701-153">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="77701-154"><strong>Усерендпоинтид</strong></span><span class="sxs-lookup"><span data-stu-id="77701-154"><strong>UserEndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="77701-155">идентификатора</span><span class="sxs-lookup"><span data-stu-id="77701-155">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="77701-156">Уникальный идентификатор пользователя, который является частью сеанса.</span><span class="sxs-lookup"><span data-stu-id="77701-156">Unique identifier of the user whose was part of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="77701-157"><strong>EndTime</strong></span><span class="sxs-lookup"><span data-stu-id="77701-157"><strong>EndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="77701-158">datetime</span><span class="sxs-lookup"><span data-stu-id="77701-158">datetime</span></span></p></td>
<td><p><span data-ttu-id="77701-159">Время окончания сеанса.</span><span class="sxs-lookup"><span data-stu-id="77701-159">End time of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="77701-160"><strong>Конференцеклиентверсион</strong></span><span class="sxs-lookup"><span data-stu-id="77701-160"><strong>ConferenceClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="77701-161">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="77701-161">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="77701-162">Версия сервера конференций.</span><span class="sxs-lookup"><span data-stu-id="77701-162">Version of conference server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="77701-163"><strong>Конференцеклиенттипе</strong></span><span class="sxs-lookup"><span data-stu-id="77701-163"><strong>ConferenceClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="77701-164">целое</span><span class="sxs-lookup"><span data-stu-id="77701-164">int</span></span></p></td>
<td><p><span data-ttu-id="77701-165">Тип сервера конференций.</span><span class="sxs-lookup"><span data-stu-id="77701-165">Type of conference server.</span></span> <span data-ttu-id="77701-166">Для получения дополнительных сведений ознакомьтесь с <a href="lync-server-2013-useragentdef-table.md">таблицей усеражентдеф в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="77701-166">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="77701-167"><strong>Конференцекатегори</strong></span><span class="sxs-lookup"><span data-stu-id="77701-167"><strong>ConferenceCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="77701-168">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="77701-168">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="77701-169">Категория "сервер конференции".</span><span class="sxs-lookup"><span data-stu-id="77701-169">Conference server category.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="77701-170"><strong>Усерклиентверсион</strong></span><span class="sxs-lookup"><span data-stu-id="77701-170"><strong>UserClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="77701-171">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="77701-171">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="77701-172">Версия клиента, используемая пользователем, который принимал участие в сеансе.</span><span class="sxs-lookup"><span data-stu-id="77701-172">Version of client used by the user who participated in the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="77701-173"><strong>Усерклиенттипе</strong></span><span class="sxs-lookup"><span data-stu-id="77701-173"><strong>UserClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="77701-174">целое</span><span class="sxs-lookup"><span data-stu-id="77701-174">int</span></span></p></td>
<td><p><span data-ttu-id="77701-175">Клиент, используемый пользователем, который участвовал в сеансе.</span><span class="sxs-lookup"><span data-stu-id="77701-175">Client used by the user who participated in the session.</span></span> <span data-ttu-id="77701-176">Дополнительные сведения вы увидите <a href="lync-server-2013-useragentdef-table.md">в таблице усеражентдеф в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="77701-176">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="77701-177"><strong>Усерклиенткатегори</strong></span><span class="sxs-lookup"><span data-stu-id="77701-177"><strong>UserClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="77701-178">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="77701-178">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="77701-179">Имя категории клиента, используемой пользователем, который является частью сеанса.</span><span class="sxs-lookup"><span data-stu-id="77701-179">Name of the category of the client used by the user who was part of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="77701-180"><strong>Онбехалфофури</strong></span><span class="sxs-lookup"><span data-stu-id="77701-180"><strong>OnBehalfOfUri</strong></span></span></p></td>
<td><p><span data-ttu-id="77701-181">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="77701-181">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="77701-182">Универсальный код ресурса (URI) пользователя, от имени которого был запущен сеанс.</span><span class="sxs-lookup"><span data-stu-id="77701-182">URI of the user on whose behalf the session was started.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="77701-183"><strong>Онбехалфофуритипе</strong></span><span class="sxs-lookup"><span data-stu-id="77701-183"><strong>OnBehalfOfUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="77701-184">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="77701-184">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="77701-185">Тип универсального кода ресурса (URI) пользователя, от имени которого был запущен сеанс.</span><span class="sxs-lookup"><span data-stu-id="77701-185">Type of URI of the user on whose behalf the session was started.</span></span> <span data-ttu-id="77701-186">Для получения дополнительных сведений ознакомьтесь с <a href="lync-server-2013-uritypes-table.md">таблицей уритипес в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="77701-186">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="77701-187"><strong>Онбехалфофтенант</strong></span><span class="sxs-lookup"><span data-stu-id="77701-187"><strong>OnBehalfOfTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="77701-188">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="77701-188">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="77701-189">Клиент пользователя, от имени которого был запущен сеанс.</span><span class="sxs-lookup"><span data-stu-id="77701-189">Tenant of the user whose on behalf the session was started.</span></span> <span data-ttu-id="77701-190">Дополнительные сведения приведены в <a href="lync-server-2013-tenants-table.md">таблице "клиенты" в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="77701-190">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="77701-191"><strong>Реферредбюри</strong></span><span class="sxs-lookup"><span data-stu-id="77701-191"><strong>ReferredByUri</strong></span></span></p></td>
<td><p><span data-ttu-id="77701-192">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="77701-192">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="77701-193">URI пользователя, который ссылался на сеанс.</span><span class="sxs-lookup"><span data-stu-id="77701-193">URI of the user who referred the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="77701-194"><strong>Реферредбюритипе</strong></span><span class="sxs-lookup"><span data-stu-id="77701-194"><strong>ReferredByUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="77701-195">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="77701-195">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="77701-196">Тип URI пользователя, который ссылался на сеанс.</span><span class="sxs-lookup"><span data-stu-id="77701-196">Type of URI of the user who referred the session.</span></span> <span data-ttu-id="77701-197">Для получения дополнительных сведений ознакомьтесь с <a href="lync-server-2013-uritypes-table.md">таблицей уритипес в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="77701-197">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="77701-198"><strong>Реферредбюритенант</strong></span><span class="sxs-lookup"><span data-stu-id="77701-198"><strong>ReferredByUriTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="77701-199">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="77701-199">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="77701-200">Клиент пользователя, который ссылался на сеанс.</span><span class="sxs-lookup"><span data-stu-id="77701-200">Tenant of the user who referred the session.</span></span> <span data-ttu-id="77701-201">Дополнительные сведения приведены в <a href="lync-server-2013-tenants-table.md">таблице "клиенты" в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="77701-201">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="77701-202"><strong>Диалогид</strong></span><span class="sxs-lookup"><span data-stu-id="77701-202"><strong>DialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="77701-203">варстринг (775)</span><span class="sxs-lookup"><span data-stu-id="77701-203">varstring(775)</span></span></p></td>
<td><p><span data-ttu-id="77701-204">ИДЕНТИФИКАТОР диалогового окна SIP.</span><span class="sxs-lookup"><span data-stu-id="77701-204">SIP dialog ID.</span></span> <span data-ttu-id="77701-205">Формат</span><span class="sxs-lookup"><span data-stu-id="77701-205">The format is</span></span></p>
<p><span data-ttu-id="77701-206">:d иалог; to-Tag</span><span class="sxs-lookup"><span data-stu-id="77701-206">:dialog;from-tag;to-tag</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="77701-207"><strong>Реплацедиалогидтиме</strong></span><span class="sxs-lookup"><span data-stu-id="77701-207"><strong>ReplaceDialogIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="77701-208">datetime</span><span class="sxs-lookup"><span data-stu-id="77701-208">datetime</span></span></p></td>
<td><p><span data-ttu-id="77701-209">ИДЕНТИФИКАЦИОНный номер, определяющий диалоговое окно, которое было заменено текущим сеансом.</span><span class="sxs-lookup"><span data-stu-id="77701-209">ID number to identify the dialog which was replaced by current session.</span></span> <span data-ttu-id="77701-210">Дополнительные сведения приведены <a href="lync-server-2013-dialogs-table.md">в таблице диалоговые окна Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="77701-210">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="77701-211"><strong>Реплацедиалогидсек</strong></span><span class="sxs-lookup"><span data-stu-id="77701-211"><strong>ReplaceDialogIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="77701-212">целое</span><span class="sxs-lookup"><span data-stu-id="77701-212">int</span></span></p></td>
<td><p><span data-ttu-id="77701-213">ИДЕНТИФИКАЦИОНный номер для идентификации сеанса.</span><span class="sxs-lookup"><span data-stu-id="77701-213">ID number to identify the session.</span></span> <span data-ttu-id="77701-214">Используется в сочетании с Реплацедиалогидтиме для уникальной идентификации сеанса, который заменяется этим сеансом.</span><span class="sxs-lookup"><span data-stu-id="77701-214">Used in conjunction with ReplaceDialogIdTime to uniquely identify a session that is replaced by this session.</span></span> <span data-ttu-id="77701-215">Дополнительные сведения приведены <a href="lync-server-2013-dialogs-table.md">в таблице диалоговые окна Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="77701-215">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="77701-216"><strong>Реплацесдиалогид</strong></span><span class="sxs-lookup"><span data-stu-id="77701-216"><strong>ReplacesDialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="77701-217">varchar (775)</span><span class="sxs-lookup"><span data-stu-id="77701-217">varchar(775)</span></span></p></td>
<td><p><span data-ttu-id="77701-218">ИДЕНТИФИКАТОР диалогового окна SIP, в котором будет заменяться сеанс.</span><span class="sxs-lookup"><span data-stu-id="77701-218">SIP dialog ID the session replaces.</span></span> <span data-ttu-id="77701-219">Формат:</span><span class="sxs-lookup"><span data-stu-id="77701-219">The format of the is:</span></span></p>
<p><span data-ttu-id="77701-220">диалоговое окно; тег "from-Tag"</span><span class="sxs-lookup"><span data-stu-id="77701-220">dialog;from-tag;to-tag</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="77701-221"><strong>Исстартедбиконфсервер</strong></span><span class="sxs-lookup"><span data-stu-id="77701-221"><strong>IsStartedByConfServer</strong></span></span></p></td>
<td><p><span data-ttu-id="77701-222">бит</span><span class="sxs-lookup"><span data-stu-id="77701-222">bit</span></span></p></td>
<td><p><span data-ttu-id="77701-223">Указывает, был ли запущен сервер конференц-связи.</span><span class="sxs-lookup"><span data-stu-id="77701-223">Indicates whether the session was started by the conferencing server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="77701-224"><strong>Исендедбиконфсервер</strong></span><span class="sxs-lookup"><span data-stu-id="77701-224"><strong>IsEndedByConfServer</strong></span></span></p></td>
<td><p><span data-ttu-id="77701-225">бит</span><span class="sxs-lookup"><span data-stu-id="77701-225">bit</span></span></p></td>
<td><p><span data-ttu-id="77701-226">Указывает, завершен ли сеанс на сервере конференций.</span><span class="sxs-lookup"><span data-stu-id="77701-226">Indicates whether the session was ended by the conferencing server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="77701-227"><strong>Исусеринтернал</strong></span><span class="sxs-lookup"><span data-stu-id="77701-227"><strong>IsUserInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="77701-228">бит</span><span class="sxs-lookup"><span data-stu-id="77701-228">bit</span></span></p></td>
<td><p><span data-ttu-id="77701-229">Указывает, вошел ли пользователь из внутренней сети.</span><span class="sxs-lookup"><span data-stu-id="77701-229">Indicates whether the user logged on from the internal network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="77701-230"><strong>Респонсетиме</strong></span><span class="sxs-lookup"><span data-stu-id="77701-230"><strong>ResponseTime</strong></span></span></p></td>
<td><p><span data-ttu-id="77701-231">datetime</span><span class="sxs-lookup"><span data-stu-id="77701-231">datetime</span></span></p></td>
<td><p><span data-ttu-id="77701-232">Время ответа на первое сообщение приглашения.</span><span class="sxs-lookup"><span data-stu-id="77701-232">Time of the response to the first INVITE message.</span></span> <span data-ttu-id="77701-233">Это поле обычно заполняется данными, созданными на основе исходного сообщения INVITE в сеансе.</span><span class="sxs-lookup"><span data-stu-id="77701-233">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="77701-234">Если сообщение приглашения отсутствует, поле заполняется датой и временем первого соответствующего сообщения SIP (пока, CANCEL, MESSAGE или INFO).</span><span class="sxs-lookup"><span data-stu-id="77701-234">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="77701-235"><strong>Респонсекоде</strong></span><span class="sxs-lookup"><span data-stu-id="77701-235"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="77701-236">целое</span><span class="sxs-lookup"><span data-stu-id="77701-236">int</span></span></p></td>
<td><p><span data-ttu-id="77701-237">Код ответа SIP на приглашение на сеанс.</span><span class="sxs-lookup"><span data-stu-id="77701-237">SIP response code to the session invitation.</span></span> <span data-ttu-id="77701-238">Это поле обычно заполняется данными, созданными на основе исходного сообщения INVITE в сеансе.</span><span class="sxs-lookup"><span data-stu-id="77701-238">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="77701-239">Если сообщение приглашения отсутствует, поле заполняется датой и временем первого соответствующего сообщения SIP (пока, CANCEL, MESSAGE или INFO).</span><span class="sxs-lookup"><span data-stu-id="77701-239">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="77701-240"><strong>ДиагностиЦид</strong></span><span class="sxs-lookup"><span data-stu-id="77701-240"><strong>DiagnosticId</strong></span></span></p></td>
<td><p><span data-ttu-id="77701-241">целое</span><span class="sxs-lookup"><span data-stu-id="77701-241">int</span></span></p></td>
<td><p><span data-ttu-id="77701-242">Идентификатор диагностики, полученный от заголовков SIP сеанса.</span><span class="sxs-lookup"><span data-stu-id="77701-242">Diagnostic ID captured from session SIP headers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="77701-243"><strong>Контента</strong></span><span class="sxs-lookup"><span data-stu-id="77701-243"><strong>ContentType</strong></span></span></p></td>
<td><p><span data-ttu-id="77701-244">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="77701-244">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="77701-245">Тип контента для сеанса.</span><span class="sxs-lookup"><span data-stu-id="77701-245">Content type for the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="77701-246"><strong>FrontEnd</strong></span><span class="sxs-lookup"><span data-stu-id="77701-246"><strong>FrontEnd</strong></span></span></p></td>
<td><p><span data-ttu-id="77701-247">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="77701-247">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="77701-248">Полное доменное имя сервера переднего плана, который захватил данные для сеанса.</span><span class="sxs-lookup"><span data-stu-id="77701-248">FQDN of the Front End server that captured the data for the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="77701-249"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="77701-249"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="77701-250">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="77701-250">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="77701-251">Полное доменное имя пула, который захватывает данные для сеанса.</span><span class="sxs-lookup"><span data-stu-id="77701-251">FQDN of the pool that captured the data for the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="77701-252"><strong>Медиатионсервер</strong></span><span class="sxs-lookup"><span data-stu-id="77701-252"><strong>MediationServer</strong></span></span></p></td>
<td><p><span data-ttu-id="77701-253">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="77701-253">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="77701-254">Сервер исправлений, используемый пользователем, который принимал участие в сеансе.</span><span class="sxs-lookup"><span data-stu-id="77701-254">Mediation Server used by the user who participated in the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="77701-255"><strong>Шлюз</strong></span><span class="sxs-lookup"><span data-stu-id="77701-255"><strong>Gateway</strong></span></span></p></td>
<td><p><span data-ttu-id="77701-256">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="77701-256">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="77701-257">Шлюз, используемый пользователем, который участвовал в сеансе.</span><span class="sxs-lookup"><span data-stu-id="77701-257">Gateway used by the user who participated the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="77701-258"><strong>Пограничный сервер</strong></span><span class="sxs-lookup"><span data-stu-id="77701-258"><strong>EdgeServer</strong></span></span></p></td>
<td><p><span data-ttu-id="77701-259">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="77701-259">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="77701-260">Полное доменное имя пограничного сервера, используемое пользователем, который принимал участие в сеансе.</span><span class="sxs-lookup"><span data-stu-id="77701-260">FQDN of the Edge server used by the user who participated in the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="77701-261"><strong>Усерфлаг</strong></span><span class="sxs-lookup"><span data-stu-id="77701-261"><strong>UserFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="77701-262">smallint</span><span class="sxs-lookup"><span data-stu-id="77701-262">smallint</span></span></p></td>
<td><p><span data-ttu-id="77701-263">Указывает атрибуты пользователя, который принимал участие в сеансе.</span><span class="sxs-lookup"><span data-stu-id="77701-263">Indicates the attributes of the user who participated in the session.</span></span> <span data-ttu-id="77701-264">Допустимы следующие определения атрибутов:</span><span class="sxs-lookup"><span data-stu-id="77701-264">The following attribute definitions allowed:</span></span></p>
<p><span data-ttu-id="77701-265">0x01 — интеграция с настольным телефоном</span><span class="sxs-lookup"><span data-stu-id="77701-265">0x01 - Integrated with desktop phone</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="77701-266"><strong>Каллфлаг</strong></span><span class="sxs-lookup"><span data-stu-id="77701-266"><strong>CallFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="77701-267">smallint</span><span class="sxs-lookup"><span data-stu-id="77701-267">smallint</span></span></p></td>
<td><p><span data-ttu-id="77701-268">Указывает атрибуты вызова.</span><span class="sxs-lookup"><span data-stu-id="77701-268">Indicates the call attributes.</span></span> <span data-ttu-id="77701-269">Допустимы следующие определения атрибутов:</span><span class="sxs-lookup"><span data-stu-id="77701-269">The following attribute definitions are allowed:</span></span></p>
<p><span data-ttu-id="77701-270">0x01 — повторное попыток Session0</span><span class="sxs-lookup"><span data-stu-id="77701-270">0x01 - Retried Session0</span></span></p>
<p><span data-ttu-id="77701-271">x02 — вызов, сделанный агентом от имени группы ответа</span><span class="sxs-lookup"><span data-stu-id="77701-271">x02 - A call made by agent on behalf of a Response Group</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

