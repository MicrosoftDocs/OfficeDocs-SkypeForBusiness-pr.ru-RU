---
title: 'Lync Server 2013: представление Таблица mcujoinsandleaves'
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
ms.openlocfilehash: 9eae65a6f19e0eb73098ed5990d6881d0129b34e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42045321"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="mcujoinsandleaves-view-in-lync-server-2013"></a><span data-ttu-id="c15b7-102">Представление Таблица mcujoinsandleaves в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c15b7-102">McuJoinsAndLeaves view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c15b7-103">_**Последнее изменение темы:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="c15b7-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="c15b7-104">В представлении McuJoinsAndLeaves хранится информация о присоединении и выходе пользователей для одного сервера конференций.</span><span class="sxs-lookup"><span data-stu-id="c15b7-104">The McuJoinsAndLeaves view stores information about users join and leave information for one conference server.</span></span> <span data-ttu-id="c15b7-105">Каждая запись в этом представлении содержит сведения о звонке, сочетающие в себе данные о присоединении или отключении пользователя и сервере конференций.</span><span class="sxs-lookup"><span data-stu-id="c15b7-105">Each record in this view contains call details about one combination of a user join or leave and conferencing server.</span></span> <span data-ttu-id="c15b7-106">Это представление было представлено в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c15b7-106">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c15b7-107">Столбец</span><span class="sxs-lookup"><span data-stu-id="c15b7-107">Column</span></span></th>
<th><span data-ttu-id="c15b7-108">Тип данных</span><span class="sxs-lookup"><span data-stu-id="c15b7-108">Data Type</span></span></th>
<th><span data-ttu-id="c15b7-109">Сведения</span><span class="sxs-lookup"><span data-stu-id="c15b7-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c15b7-110"><strong>сессионидтиме</strong></span><span class="sxs-lookup"><span data-stu-id="c15b7-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="c15b7-111">datetime</span><span class="sxs-lookup"><span data-stu-id="c15b7-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="c15b7-112">Время экземпляра конференции.</span><span class="sxs-lookup"><span data-stu-id="c15b7-112">Time of conference instance.</span></span> <span data-ttu-id="c15b7-113">Используется вместе с параметром SessionIdSeq для уникального определения экземпляра конференции.</span><span class="sxs-lookup"><span data-stu-id="c15b7-113">Used in conjunction with SessionIdSeq to uniquely identify a conference instance.</span></span> <span data-ttu-id="c15b7-114">Дополнительные сведения см. <a href="lync-server-2013-conferences-table.md">в таблице конференций в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="c15b7-114">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c15b7-115"><strong>сессионидсек</strong></span><span class="sxs-lookup"><span data-stu-id="c15b7-115"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="c15b7-116">int</span><span class="sxs-lookup"><span data-stu-id="c15b7-116">int</span></span></p></td>
<td><p><span data-ttu-id="c15b7-117">Идентификатор для определения экземпляра конференции.</span><span class="sxs-lookup"><span data-stu-id="c15b7-117">ID number to identify the conference instance.</span></span> <span data-ttu-id="c15b7-118">Используется вместе с параметром SessionIdTime для уникального определения экземпляра конференции.</span><span class="sxs-lookup"><span data-stu-id="c15b7-118">Used in conjunction with SessionIdTime to uniquely identify a conference instance.</span></span> <span data-ttu-id="c15b7-119">Дополнительные сведения см. <a href="lync-server-2013-conferences-table.md">в таблице конференций в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="c15b7-119">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c15b7-120"><strong>мкуури</strong></span><span class="sxs-lookup"><span data-stu-id="c15b7-120"><strong>McuUri</strong></span></span></p></td>
<td><p><span data-ttu-id="c15b7-121">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="c15b7-121">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="c15b7-122">URI сервера конференций, к которому подключился пользователь.</span><span class="sxs-lookup"><span data-stu-id="c15b7-122">The URI of the conferencing server that the user connected to.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c15b7-123"><strong>мкууритипе</strong></span><span class="sxs-lookup"><span data-stu-id="c15b7-123"><strong>McuUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="c15b7-124">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="c15b7-124">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="c15b7-125">URI сервера конференций, к которому подключился пользователь.</span><span class="sxs-lookup"><span data-stu-id="c15b7-125">The URI of the conferencing server that the user connected to.</span></span> <span data-ttu-id="c15b7-126">Дополнительные сведения см. <a href="lync-server-2013-uritypes-table.md">в таблице таблица uritypes в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="c15b7-126">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c15b7-127"><strong>UserUri</strong></span><span class="sxs-lookup"><span data-stu-id="c15b7-127"><strong>UserUri</strong></span></span></p></td>
<td><p><span data-ttu-id="c15b7-128">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="c15b7-128">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="c15b7-129">URI пользователя, сведения о присоединении или выходе к серверу конференций которого были записаны.</span><span class="sxs-lookup"><span data-stu-id="c15b7-129">The URI of the user whose conferencing server join/leave information was captured.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c15b7-130"><strong>усеруритипе</strong></span><span class="sxs-lookup"><span data-stu-id="c15b7-130"><strong>UserUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="c15b7-131">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="c15b7-131">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="c15b7-132">Тип URI пользователя, сведения о присоединении или выходе к серверу конференций которого были записаны.</span><span class="sxs-lookup"><span data-stu-id="c15b7-132">The type of URI of the user whose conferencing server join/leave information was captured.</span></span> <span data-ttu-id="c15b7-133">Дополнительные сведения см. <a href="lync-server-2013-uritypes-table.md">в таблице таблица uritypes в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="c15b7-133">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c15b7-134"><strong>усертенант</strong></span><span class="sxs-lookup"><span data-stu-id="c15b7-134"><strong>UserTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="c15b7-135">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="c15b7-135">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="c15b7-136">Клиент пользователя, сведения о присоединении или выходе к серверу конференций которого были записаны.</span><span class="sxs-lookup"><span data-stu-id="c15b7-136">The tenant of the user whose conferencing server join/leave information was captured.</span></span> <span data-ttu-id="c15b7-137">Дополнительные сведения см. <a href="lync-server-2013-tenants-table.md">в таблице клиентов в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="c15b7-137">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c15b7-138"><strong>усерклиентверсион</strong></span><span class="sxs-lookup"><span data-stu-id="c15b7-138"><strong>UserClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="c15b7-139">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="c15b7-139">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="c15b7-140">Версия клиента пользователя, сведения о присоединении или выходе к серверу конференций которого были записаны.</span><span class="sxs-lookup"><span data-stu-id="c15b7-140">The version of client used by the user whose conferencing server join/leave information was captured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c15b7-141"><strong>усерклиенттипе</strong></span><span class="sxs-lookup"><span data-stu-id="c15b7-141"><strong>UserClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="c15b7-142">int</span><span class="sxs-lookup"><span data-stu-id="c15b7-142">int</span></span></p></td>
<td><p><span data-ttu-id="c15b7-143">Версия клиента пользователя, сведения о присоединении или выходе к серверу конференций которого были записаны.</span><span class="sxs-lookup"><span data-stu-id="c15b7-143">The client used by the user whose conferencing server join/leave information was captured.</span></span> <span data-ttu-id="c15b7-144">Дополнительные сведения приведены <a href="lync-server-2013-useragentdef-table.md">в таблице таблица useragentdef в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="c15b7-144">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c15b7-145"><strong>усерклиенткатегори</strong></span><span class="sxs-lookup"><span data-stu-id="c15b7-145"><strong>UserClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="c15b7-146">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="c15b7-146">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="c15b7-147">Имя категории пользователя, сведения о присоединении или выходе к серверу конференций которого были записаны.</span><span class="sxs-lookup"><span data-stu-id="c15b7-147">The name of the category of the client used by the user whose conferencing server join/leave information was captured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c15b7-148"><strong>мкуусеринстанце</strong></span><span class="sxs-lookup"><span data-stu-id="c15b7-148"><strong>McuUserInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="c15b7-149">int</span><span class="sxs-lookup"><span data-stu-id="c15b7-149">int</span></span></p></td>
<td><p><span data-ttu-id="c15b7-150">Уникально определяет комбинацию пользователя и устройства для пользователей, одновременно вошедших на несколько устройств.</span><span class="sxs-lookup"><span data-stu-id="c15b7-150">Uniquely identifies the user/device combination for users simultaneously logged on to multiple devices.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c15b7-151"><strong>исусерфромпстн</strong></span><span class="sxs-lookup"><span data-stu-id="c15b7-151"><strong>IsUserFromPstn</strong></span></span></p></td>
<td><p><span data-ttu-id="c15b7-152">Битовая</span><span class="sxs-lookup"><span data-stu-id="c15b7-152">bit</span></span></p></td>
<td><p><span data-ttu-id="c15b7-153">Разряд, указывающий, является ли пользователь внутренним.</span><span class="sxs-lookup"><span data-stu-id="c15b7-153">Bit that represents whether the user is an internal user or not.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c15b7-154"><strong>диалогсессионидтиме</strong></span><span class="sxs-lookup"><span data-stu-id="c15b7-154"><strong>DialogSessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="c15b7-155">datetime</span><span class="sxs-lookup"><span data-stu-id="c15b7-155">datetime</span></span></p></td>
<td><p><span data-ttu-id="c15b7-156">Время запроса сеанса.</span><span class="sxs-lookup"><span data-stu-id="c15b7-156">Time of session request.</span></span> <span data-ttu-id="c15b7-157">Используется вместе с параметром SessionIdSeq для уникального определения сеанса.</span><span class="sxs-lookup"><span data-stu-id="c15b7-157">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="c15b7-158">Дополнительные сведения см. <a href="lync-server-2013-dialogs-table.md">в таблице диалоговых окон в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="c15b7-158">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c15b7-159"><strong>диалогсессионидсек</strong></span><span class="sxs-lookup"><span data-stu-id="c15b7-159"><strong>DialogSessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="c15b7-160">int</span><span class="sxs-lookup"><span data-stu-id="c15b7-160">int</span></span></p></td>
<td><p><span data-ttu-id="c15b7-161">Идентификационный номер для идентификации сеанса.</span><span class="sxs-lookup"><span data-stu-id="c15b7-161">ID number to identify the session.</span></span> <span data-ttu-id="c15b7-162">Используется совместно с параметром SessionIdTime для уникальной идентификации сеанса.</span><span class="sxs-lookup"><span data-stu-id="c15b7-162">Used in conjunction with SessionIdTime to uniquely identify a session.</span></span> <span data-ttu-id="c15b7-163">Дополнительные сведения см. <a href="lync-server-2013-dialogs-table.md">в таблице диалоговых окон в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="c15b7-163">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c15b7-164"><strong>DialogId</strong></span><span class="sxs-lookup"><span data-stu-id="c15b7-164"><strong>DialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="c15b7-165">varchar (775)</span><span class="sxs-lookup"><span data-stu-id="c15b7-165">varchar(775)</span></span></p></td>
<td><p><span data-ttu-id="c15b7-p110">Код диалога SIP этого сеанса. Формат: диалог;начальный тег;конечный тег.</span><span class="sxs-lookup"><span data-stu-id="c15b7-p110">SIP dialog ID of the session. The format is: dialog;from-tag;to-tag.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c15b7-168"><strong>усержоинтиме</strong></span><span class="sxs-lookup"><span data-stu-id="c15b7-168"><strong>UserJoinTime</strong></span></span></p></td>
<td><p><span data-ttu-id="c15b7-169">datetime</span><span class="sxs-lookup"><span data-stu-id="c15b7-169">datetime</span></span></p></td>
<td><p><span data-ttu-id="c15b7-170">Время, когда пользователь присоединился к серверу конференций.</span><span class="sxs-lookup"><span data-stu-id="c15b7-170">Time the user joined the conferencing server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c15b7-171"><strong>усерлеаветиме</strong></span><span class="sxs-lookup"><span data-stu-id="c15b7-171"><strong>UserLeaveTime</strong></span></span></p></td>
<td><p><span data-ttu-id="c15b7-172">datetime</span><span class="sxs-lookup"><span data-stu-id="c15b7-172">datetime</span></span></p></td>
<td><p><span data-ttu-id="c15b7-173">Время, когда пользователь вышел с сервера конференций.</span><span class="sxs-lookup"><span data-stu-id="c15b7-173">Time the user left the conferencing server.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

