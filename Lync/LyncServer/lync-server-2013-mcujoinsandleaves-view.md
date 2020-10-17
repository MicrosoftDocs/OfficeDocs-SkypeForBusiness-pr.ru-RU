---
title: 'Lync Server 2013: представление Таблица mcujoinsandleaves'
description: 'Lync Server 2013: представление Таблица mcujoinsandleaves.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: McuJoinsAndLeaves view
ms:assetid: 6f00b8e7-b8b6-4657-ac5e-d8a571806ae2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688088(v=OCS.15)
ms:contentKeyID: 49733687
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f7f2f51c340d5bd4824a6e8eff1a0da172a758c9
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48556495"
---
# <a name="mcujoinsandleaves-view-in-lync-server-2013"></a><span data-ttu-id="6b637-103">Представление Таблица mcujoinsandleaves в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6b637-103">McuJoinsAndLeaves view in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6b637-104">_**Последнее изменение темы:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="6b637-104">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="6b637-105">В представлении McuJoinsAndLeaves хранится информация о присоединении и выходе пользователей для одного сервера конференций.</span><span class="sxs-lookup"><span data-stu-id="6b637-105">The McuJoinsAndLeaves view stores information about users join and leave information for one conference server.</span></span> <span data-ttu-id="6b637-106">Каждая запись в этом представлении содержит сведения о звонке, сочетающие в себе данные о присоединении или отключении пользователя и сервере конференций.</span><span class="sxs-lookup"><span data-stu-id="6b637-106">Each record in this view contains call details about one combination of a user join or leave and conferencing server.</span></span> <span data-ttu-id="6b637-107">Это представление было представлено в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6b637-107">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6b637-108">Столбец</span><span class="sxs-lookup"><span data-stu-id="6b637-108">Column</span></span></th>
<th><span data-ttu-id="6b637-109">Тип данных</span><span class="sxs-lookup"><span data-stu-id="6b637-109">Data Type</span></span></th>
<th><span data-ttu-id="6b637-110">Сведения</span><span class="sxs-lookup"><span data-stu-id="6b637-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6b637-111"><strong>сессионидтиме</strong></span><span class="sxs-lookup"><span data-stu-id="6b637-111"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="6b637-112">datetime</span><span class="sxs-lookup"><span data-stu-id="6b637-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="6b637-113">Время экземпляра конференции.</span><span class="sxs-lookup"><span data-stu-id="6b637-113">Time of conference instance.</span></span> <span data-ttu-id="6b637-114">Используется вместе с параметром SessionIdSeq для уникального определения экземпляра конференции.</span><span class="sxs-lookup"><span data-stu-id="6b637-114">Used in conjunction with SessionIdSeq to uniquely identify a conference instance.</span></span> <span data-ttu-id="6b637-115">Дополнительные сведения см. <a href="lync-server-2013-conferences-table.md">в таблице конференций в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="6b637-115">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6b637-116"><strong>сессионидсек</strong></span><span class="sxs-lookup"><span data-stu-id="6b637-116"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="6b637-117">int</span><span class="sxs-lookup"><span data-stu-id="6b637-117">int</span></span></p></td>
<td><p><span data-ttu-id="6b637-118">Идентификатор для определения экземпляра конференции.</span><span class="sxs-lookup"><span data-stu-id="6b637-118">ID number to identify the conference instance.</span></span> <span data-ttu-id="6b637-119">Используется вместе с параметром SessionIdTime для уникального определения экземпляра конференции.</span><span class="sxs-lookup"><span data-stu-id="6b637-119">Used in conjunction with SessionIdTime to uniquely identify a conference instance.</span></span> <span data-ttu-id="6b637-120">Дополнительные сведения см. <a href="lync-server-2013-conferences-table.md">в таблице конференций в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="6b637-120">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6b637-121"><strong>мкуури</strong></span><span class="sxs-lookup"><span data-stu-id="6b637-121"><strong>McuUri</strong></span></span></p></td>
<td><p><span data-ttu-id="6b637-122">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="6b637-122">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="6b637-123">URI сервера конференций, к которому подключился пользователь.</span><span class="sxs-lookup"><span data-stu-id="6b637-123">The URI of the conferencing server that the user connected to.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6b637-124"><strong>мкууритипе</strong></span><span class="sxs-lookup"><span data-stu-id="6b637-124"><strong>McuUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="6b637-125">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="6b637-125">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="6b637-126">URI сервера конференций, к которому подключился пользователь.</span><span class="sxs-lookup"><span data-stu-id="6b637-126">The URI of the conferencing server that the user connected to.</span></span> <span data-ttu-id="6b637-127">Дополнительные сведения см. <a href="lync-server-2013-uritypes-table.md">в таблице таблица uritypes в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="6b637-127">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6b637-128"><strong>UserUri</strong></span><span class="sxs-lookup"><span data-stu-id="6b637-128"><strong>UserUri</strong></span></span></p></td>
<td><p><span data-ttu-id="6b637-129">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="6b637-129">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="6b637-130">URI пользователя, сведения о присоединении или выходе к серверу конференций которого были записаны.</span><span class="sxs-lookup"><span data-stu-id="6b637-130">The URI of the user whose conferencing server join/leave information was captured.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6b637-131"><strong>усеруритипе</strong></span><span class="sxs-lookup"><span data-stu-id="6b637-131"><strong>UserUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="6b637-132">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="6b637-132">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="6b637-133">Тип URI пользователя, сведения о присоединении или выходе к серверу конференций которого были записаны.</span><span class="sxs-lookup"><span data-stu-id="6b637-133">The type of URI of the user whose conferencing server join/leave information was captured.</span></span> <span data-ttu-id="6b637-134">Дополнительные сведения см. <a href="lync-server-2013-uritypes-table.md">в таблице таблица uritypes в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="6b637-134">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6b637-135"><strong>усертенант</strong></span><span class="sxs-lookup"><span data-stu-id="6b637-135"><strong>UserTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="6b637-136">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="6b637-136">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="6b637-137">Клиент пользователя, сведения о присоединении или выходе к серверу конференций которого были записаны.</span><span class="sxs-lookup"><span data-stu-id="6b637-137">The tenant of the user whose conferencing server join/leave information was captured.</span></span> <span data-ttu-id="6b637-138">Дополнительные сведения см. <a href="lync-server-2013-tenants-table.md">в таблице клиентов в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="6b637-138">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6b637-139"><strong>усерклиентверсион</strong></span><span class="sxs-lookup"><span data-stu-id="6b637-139"><strong>UserClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="6b637-140">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="6b637-140">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="6b637-141">Версия клиента пользователя, сведения о присоединении или выходе к серверу конференций которого были записаны.</span><span class="sxs-lookup"><span data-stu-id="6b637-141">The version of client used by the user whose conferencing server join/leave information was captured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6b637-142"><strong>усерклиенттипе</strong></span><span class="sxs-lookup"><span data-stu-id="6b637-142"><strong>UserClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="6b637-143">int</span><span class="sxs-lookup"><span data-stu-id="6b637-143">int</span></span></p></td>
<td><p><span data-ttu-id="6b637-144">Версия клиента пользователя, сведения о присоединении или выходе к серверу конференций которого были записаны.</span><span class="sxs-lookup"><span data-stu-id="6b637-144">The client used by the user whose conferencing server join/leave information was captured.</span></span> <span data-ttu-id="6b637-145">Дополнительные сведения приведены <a href="lync-server-2013-useragentdef-table.md">в таблице таблица useragentdef в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="6b637-145">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6b637-146"><strong>усерклиенткатегори</strong></span><span class="sxs-lookup"><span data-stu-id="6b637-146"><strong>UserClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="6b637-147">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="6b637-147">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="6b637-148">Имя категории пользователя, сведения о присоединении или выходе к серверу конференций которого были записаны.</span><span class="sxs-lookup"><span data-stu-id="6b637-148">The name of the category of the client used by the user whose conferencing server join/leave information was captured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6b637-149"><strong>мкуусеринстанце</strong></span><span class="sxs-lookup"><span data-stu-id="6b637-149"><strong>McuUserInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="6b637-150">int</span><span class="sxs-lookup"><span data-stu-id="6b637-150">int</span></span></p></td>
<td><p><span data-ttu-id="6b637-151">Уникально определяет комбинацию пользователя и устройства для пользователей, одновременно вошедших на несколько устройств.</span><span class="sxs-lookup"><span data-stu-id="6b637-151">Uniquely identifies the user/device combination for users simultaneously logged on to multiple devices.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6b637-152"><strong>исусерфромпстн</strong></span><span class="sxs-lookup"><span data-stu-id="6b637-152"><strong>IsUserFromPstn</strong></span></span></p></td>
<td><p><span data-ttu-id="6b637-153">Битовая</span><span class="sxs-lookup"><span data-stu-id="6b637-153">bit</span></span></p></td>
<td><p><span data-ttu-id="6b637-154">Разряд, указывающий, является ли пользователь внутренним.</span><span class="sxs-lookup"><span data-stu-id="6b637-154">Bit that represents whether the user is an internal user or not.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6b637-155"><strong>диалогсессионидтиме</strong></span><span class="sxs-lookup"><span data-stu-id="6b637-155"><strong>DialogSessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="6b637-156">datetime</span><span class="sxs-lookup"><span data-stu-id="6b637-156">datetime</span></span></p></td>
<td><p><span data-ttu-id="6b637-157">Время запроса сеанса.</span><span class="sxs-lookup"><span data-stu-id="6b637-157">Time of session request.</span></span> <span data-ttu-id="6b637-158">Используется вместе с параметром SessionIdSeq для уникального определения сеанса.</span><span class="sxs-lookup"><span data-stu-id="6b637-158">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="6b637-159">Дополнительные сведения см. <a href="lync-server-2013-dialogs-table.md">в таблице диалоговых окон в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="6b637-159">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6b637-160"><strong>диалогсессионидсек</strong></span><span class="sxs-lookup"><span data-stu-id="6b637-160"><strong>DialogSessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="6b637-161">int</span><span class="sxs-lookup"><span data-stu-id="6b637-161">int</span></span></p></td>
<td><p><span data-ttu-id="6b637-162">Идентификационный номер для идентификации сеанса.</span><span class="sxs-lookup"><span data-stu-id="6b637-162">ID number to identify the session.</span></span> <span data-ttu-id="6b637-163">Используется совместно с параметром SessionIdTime для уникальной идентификации сеанса.</span><span class="sxs-lookup"><span data-stu-id="6b637-163">Used in conjunction with SessionIdTime to uniquely identify a session.</span></span> <span data-ttu-id="6b637-164">Дополнительные сведения см. <a href="lync-server-2013-dialogs-table.md">в таблице диалоговых окон в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="6b637-164">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6b637-165"><strong>DialogId</strong></span><span class="sxs-lookup"><span data-stu-id="6b637-165"><strong>DialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="6b637-166">varchar (775)</span><span class="sxs-lookup"><span data-stu-id="6b637-166">varchar(775)</span></span></p></td>
<td><p><span data-ttu-id="6b637-p110">Код диалога SIP этого сеанса. Формат: диалог;начальный тег;конечный тег.</span><span class="sxs-lookup"><span data-stu-id="6b637-p110">SIP dialog ID of the session. The format is: dialog;from-tag;to-tag.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6b637-169"><strong>усержоинтиме</strong></span><span class="sxs-lookup"><span data-stu-id="6b637-169"><strong>UserJoinTime</strong></span></span></p></td>
<td><p><span data-ttu-id="6b637-170">datetime</span><span class="sxs-lookup"><span data-stu-id="6b637-170">datetime</span></span></p></td>
<td><p><span data-ttu-id="6b637-171">Время, когда пользователь присоединился к серверу конференций.</span><span class="sxs-lookup"><span data-stu-id="6b637-171">Time the user joined the conferencing server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6b637-172"><strong>усерлеаветиме</strong></span><span class="sxs-lookup"><span data-stu-id="6b637-172"><strong>UserLeaveTime</strong></span></span></p></td>
<td><p><span data-ttu-id="6b637-173">datetime</span><span class="sxs-lookup"><span data-stu-id="6b637-173">datetime</span></span></p></td>
<td><p><span data-ttu-id="6b637-174">Время, когда пользователь вышел с сервера конференций.</span><span class="sxs-lookup"><span data-stu-id="6b637-174">Time the user left the conferencing server.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

