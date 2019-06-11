---
title: 'Lync Server 2013: представление Мкужоинсандлеавес'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: McuJoinsAndLeaves view
ms:assetid: 6f00b8e7-b8b6-4657-ac5e-d8a571806ae2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688088(v=OCS.15)
ms:contentKeyID: 49733687
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7592879a1c6c6cc6bbcac54fd843046b69acee83
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34827573"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="mcujoinsandleaves-view-in-lync-server-2013"></a><span data-ttu-id="bbb76-102">Мкужоинсандлеавес представления в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bbb76-102">McuJoinsAndLeaves view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bbb76-103">_**Тема последнего изменения:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="bbb76-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="bbb76-104">В представлении Мкужоинсандлеавес хранятся сведения о присоединениях и выходе пользователей на один сервер конференции.</span><span class="sxs-lookup"><span data-stu-id="bbb76-104">The McuJoinsAndLeaves view stores information about users join and leave information for one conference server.</span></span> <span data-ttu-id="bbb76-105">Каждая запись в этом представлении включает в себя сведения о звонках для одной комбинации присоединения пользователя или выхода из него и сервера конференц-связи.</span><span class="sxs-lookup"><span data-stu-id="bbb76-105">Each record in this view contains call details about one combination of a user join or leave and conferencing server.</span></span> <span data-ttu-id="bbb76-106">Это представление было представлено в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="bbb76-106">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bbb76-107">Столбец</span><span class="sxs-lookup"><span data-stu-id="bbb76-107">Column</span></span></th>
<th><span data-ttu-id="bbb76-108">Тип данных</span><span class="sxs-lookup"><span data-stu-id="bbb76-108">Data Type</span></span></th>
<th><span data-ttu-id="bbb76-109">Подробности</span><span class="sxs-lookup"><span data-stu-id="bbb76-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bbb76-110"><strong>Сессионидтиме</strong></span><span class="sxs-lookup"><span data-stu-id="bbb76-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="bbb76-111">datetime</span><span class="sxs-lookup"><span data-stu-id="bbb76-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="bbb76-112">Время экземпляра Конференции.</span><span class="sxs-lookup"><span data-stu-id="bbb76-112">Time of conference instance.</span></span> <span data-ttu-id="bbb76-113">Используется в сочетании с Сессионидсек для уникальной идентификации экземпляра Конференции.</span><span class="sxs-lookup"><span data-stu-id="bbb76-113">Used in conjunction with SessionIdSeq to uniquely identify a conference instance.</span></span> <span data-ttu-id="bbb76-114">Дополнительные сведения приведены <a href="lync-server-2013-conferences-table.md">в таблице конференции для Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="bbb76-114">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bbb76-115"><strong>Сессионидсек</strong></span><span class="sxs-lookup"><span data-stu-id="bbb76-115"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="bbb76-116">целое</span><span class="sxs-lookup"><span data-stu-id="bbb76-116">int</span></span></p></td>
<td><p><span data-ttu-id="bbb76-117">ИДЕНТИФИКАЦИОНный номер для идентификации экземпляра Конференции.</span><span class="sxs-lookup"><span data-stu-id="bbb76-117">ID number to identify the conference instance.</span></span> <span data-ttu-id="bbb76-118">Используется в сочетании с Сессионидтиме для уникальной идентификации экземпляра Конференции.</span><span class="sxs-lookup"><span data-stu-id="bbb76-118">Used in conjunction with SessionIdTime to uniquely identify a conference instance.</span></span> <span data-ttu-id="bbb76-119">Дополнительные сведения приведены <a href="lync-server-2013-conferences-table.md">в таблице конференции для Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="bbb76-119">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bbb76-120"><strong>Мкуури</strong></span><span class="sxs-lookup"><span data-stu-id="bbb76-120"><strong>McuUri</strong></span></span></p></td>
<td><p><span data-ttu-id="bbb76-121">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="bbb76-121">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="bbb76-122">Универсальный код ресурса (URI) сервера конференций, к которому подключен пользователь.</span><span class="sxs-lookup"><span data-stu-id="bbb76-122">The URI of the conferencing server that the user connected to.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bbb76-123"><strong>Мкууритипе</strong></span><span class="sxs-lookup"><span data-stu-id="bbb76-123"><strong>McuUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="bbb76-124">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="bbb76-124">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="bbb76-125">Универсальный код ресурса (URI) сервера конференций, к которому подключен пользователь.</span><span class="sxs-lookup"><span data-stu-id="bbb76-125">The URI of the conferencing server that the user connected to.</span></span> <span data-ttu-id="bbb76-126">Для получения дополнительных сведений ознакомьтесь с <a href="lync-server-2013-uritypes-table.md">таблицей уритипес в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="bbb76-126">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bbb76-127"><strong>Усерури</strong></span><span class="sxs-lookup"><span data-stu-id="bbb76-127"><strong>UserUri</strong></span></span></p></td>
<td><p><span data-ttu-id="bbb76-128">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="bbb76-128">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="bbb76-129">Универсальный код ресурса (URI) пользователя, которому были собраны сведения о присоединении или выходе сервера конференций.</span><span class="sxs-lookup"><span data-stu-id="bbb76-129">The URI of the user whose conferencing server join/leave information was captured.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bbb76-130"><strong>Усеруритипе</strong></span><span class="sxs-lookup"><span data-stu-id="bbb76-130"><strong>UserUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="bbb76-131">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="bbb76-131">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="bbb76-132">Тип универсального кода ресурса (URI), к которому были собраны сведения о присоединении или выходе сервера конференций.</span><span class="sxs-lookup"><span data-stu-id="bbb76-132">The type of URI of the user whose conferencing server join/leave information was captured.</span></span> <span data-ttu-id="bbb76-133">Для получения дополнительных сведений ознакомьтесь с <a href="lync-server-2013-uritypes-table.md">таблицей уритипес в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="bbb76-133">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bbb76-134"><strong>Усертенант</strong></span><span class="sxs-lookup"><span data-stu-id="bbb76-134"><strong>UserTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="bbb76-135">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="bbb76-135">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="bbb76-136">Клиент пользователя, которому были собраны сведения о присоединении или выходе сервера конференций.</span><span class="sxs-lookup"><span data-stu-id="bbb76-136">The tenant of the user whose conferencing server join/leave information was captured.</span></span> <span data-ttu-id="bbb76-137">Дополнительные сведения приведены в <a href="lync-server-2013-tenants-table.md">таблице "клиенты" в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="bbb76-137">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bbb76-138"><strong>Усерклиентверсион</strong></span><span class="sxs-lookup"><span data-stu-id="bbb76-138"><strong>UserClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="bbb76-139">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="bbb76-139">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="bbb76-140">Версия клиента, используемая пользователем, для которого была собрана информация о присоединении или выходе сервера конференций.</span><span class="sxs-lookup"><span data-stu-id="bbb76-140">The version of client used by the user whose conferencing server join/leave information was captured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bbb76-141"><strong>Усерклиенттипе</strong></span><span class="sxs-lookup"><span data-stu-id="bbb76-141"><strong>UserClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="bbb76-142">целое</span><span class="sxs-lookup"><span data-stu-id="bbb76-142">int</span></span></p></td>
<td><p><span data-ttu-id="bbb76-143">Клиент, который использовался пользователем, которому присвоены данные для присоединения или выхода на сервер конференц-связи.</span><span class="sxs-lookup"><span data-stu-id="bbb76-143">The client used by the user whose conferencing server join/leave information was captured.</span></span> <span data-ttu-id="bbb76-144">Дополнительные сведения вы увидите <a href="lync-server-2013-useragentdef-table.md">в таблице усеражентдеф в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="bbb76-144">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bbb76-145"><strong>Усерклиенткатегори</strong></span><span class="sxs-lookup"><span data-stu-id="bbb76-145"><strong>UserClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="bbb76-146">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="bbb76-146">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="bbb76-147">Название категории клиента, используемой пользователем, для которого была получена информация о приходе и выходе сервера конференций.</span><span class="sxs-lookup"><span data-stu-id="bbb76-147">The name of the category of the client used by the user whose conferencing server join/leave information was captured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bbb76-148"><strong>Мкуусеринстанце</strong></span><span class="sxs-lookup"><span data-stu-id="bbb76-148"><strong>McuUserInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="bbb76-149">целое</span><span class="sxs-lookup"><span data-stu-id="bbb76-149">int</span></span></p></td>
<td><p><span data-ttu-id="bbb76-150">Уникально определяет сочетание пользователей и устройств для пользователей, одновременно выполнивших вход на несколько устройств.</span><span class="sxs-lookup"><span data-stu-id="bbb76-150">Uniquely identifies the user/device combination for users simultaneously logged on to multiple devices.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bbb76-151"><strong>Исусерфромпстн</strong></span><span class="sxs-lookup"><span data-stu-id="bbb76-151"><strong>IsUserFromPstn</strong></span></span></p></td>
<td><p><span data-ttu-id="bbb76-152">бит</span><span class="sxs-lookup"><span data-stu-id="bbb76-152">bit</span></span></p></td>
<td><p><span data-ttu-id="bbb76-153">Бит, обозначающий, является ли пользователь внутренним.</span><span class="sxs-lookup"><span data-stu-id="bbb76-153">Bit that represents whether the user is an internal user or not.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bbb76-154"><strong>Диалогсессионидтиме</strong></span><span class="sxs-lookup"><span data-stu-id="bbb76-154"><strong>DialogSessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="bbb76-155">datetime</span><span class="sxs-lookup"><span data-stu-id="bbb76-155">datetime</span></span></p></td>
<td><p><span data-ttu-id="bbb76-156">Время запроса сеанса.</span><span class="sxs-lookup"><span data-stu-id="bbb76-156">Time of session request.</span></span> <span data-ttu-id="bbb76-157">Используется в сочетании с Сессионидсек для уникальной идентификации сеанса.</span><span class="sxs-lookup"><span data-stu-id="bbb76-157">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="bbb76-158">Дополнительные сведения приведены <a href="lync-server-2013-dialogs-table.md">в таблице диалоговые окна Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="bbb76-158">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bbb76-159"><strong>Диалогсессионидсек</strong></span><span class="sxs-lookup"><span data-stu-id="bbb76-159"><strong>DialogSessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="bbb76-160">целое</span><span class="sxs-lookup"><span data-stu-id="bbb76-160">int</span></span></p></td>
<td><p><span data-ttu-id="bbb76-161">ИДЕНТИФИКАЦИОНный номер для идентификации сеанса.</span><span class="sxs-lookup"><span data-stu-id="bbb76-161">ID number to identify the session.</span></span> <span data-ttu-id="bbb76-162">Используется в сочетании с Сессионидтиме для уникальной идентификации сеанса.</span><span class="sxs-lookup"><span data-stu-id="bbb76-162">Used in conjunction with SessionIdTime to uniquely identify a session.</span></span> <span data-ttu-id="bbb76-163">Дополнительные сведения приведены <a href="lync-server-2013-dialogs-table.md">в таблице диалоговые окна Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="bbb76-163">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bbb76-164"><strong>Диалогид</strong></span><span class="sxs-lookup"><span data-stu-id="bbb76-164"><strong>DialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="bbb76-165">varchar (775)</span><span class="sxs-lookup"><span data-stu-id="bbb76-165">varchar(775)</span></span></p></td>
<td><p><span data-ttu-id="bbb76-166">ИДЕНТИФИКАТОР диалогового окна SIP для сеанса.</span><span class="sxs-lookup"><span data-stu-id="bbb76-166">SIP dialog ID of the session.</span></span> <span data-ttu-id="bbb76-167">Формат: диалоговое окно; тег.</span><span class="sxs-lookup"><span data-stu-id="bbb76-167">The format is: dialog;from-tag;to-tag.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bbb76-168"><strong>Усержоинтиме</strong></span><span class="sxs-lookup"><span data-stu-id="bbb76-168"><strong>UserJoinTime</strong></span></span></p></td>
<td><p><span data-ttu-id="bbb76-169">datetime</span><span class="sxs-lookup"><span data-stu-id="bbb76-169">datetime</span></span></p></td>
<td><p><span data-ttu-id="bbb76-170">Время присоединения пользователя к серверу конференц-связи.</span><span class="sxs-lookup"><span data-stu-id="bbb76-170">Time the user joined the conferencing server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bbb76-171"><strong>Усерлеаветиме</strong></span><span class="sxs-lookup"><span data-stu-id="bbb76-171"><strong>UserLeaveTime</strong></span></span></p></td>
<td><p><span data-ttu-id="bbb76-172">datetime</span><span class="sxs-lookup"><span data-stu-id="bbb76-172">datetime</span></span></p></td>
<td><p><span data-ttu-id="bbb76-173">Время, когда пользователь оставил сервер конференц-связи.</span><span class="sxs-lookup"><span data-stu-id="bbb76-173">Time the user left the conferencing server.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

