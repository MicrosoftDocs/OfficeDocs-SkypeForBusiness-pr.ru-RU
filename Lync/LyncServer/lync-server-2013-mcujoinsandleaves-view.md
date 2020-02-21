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
ms.openlocfilehash: c4f3f73606cfd05df17022770da7dcd1f5266b21
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42185332"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="mcujoinsandleaves-view-in-lync-server-2013"></a><span data-ttu-id="5748b-102">Представление Таблица mcujoinsandleaves в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5748b-102">McuJoinsAndLeaves view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5748b-103">_**Последнее изменение темы:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="5748b-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="5748b-104">В представлении McuJoinsAndLeaves хранится информация о присоединении и выходе пользователей для одного сервера конференций.</span><span class="sxs-lookup"><span data-stu-id="5748b-104">The McuJoinsAndLeaves view stores information about users join and leave information for one conference server.</span></span> <span data-ttu-id="5748b-105">Каждая запись в этом представлении содержит сведения о звонке, сочетающие в себе данные о присоединении или отключении пользователя и сервере конференций.</span><span class="sxs-lookup"><span data-stu-id="5748b-105">Each record in this view contains call details about one combination of a user join or leave and conferencing server.</span></span> <span data-ttu-id="5748b-106">Это представление было представлено в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5748b-106">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5748b-107">Столбец</span><span class="sxs-lookup"><span data-stu-id="5748b-107">Column</span></span></th>
<th><span data-ttu-id="5748b-108">Тип данных</span><span class="sxs-lookup"><span data-stu-id="5748b-108">Data Type</span></span></th>
<th><span data-ttu-id="5748b-109">Сведения</span><span class="sxs-lookup"><span data-stu-id="5748b-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5748b-110"><strong>сессионидтиме</strong></span><span class="sxs-lookup"><span data-stu-id="5748b-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="5748b-111">datetime</span><span class="sxs-lookup"><span data-stu-id="5748b-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="5748b-112">Время экземпляра конференции.</span><span class="sxs-lookup"><span data-stu-id="5748b-112">Time of conference instance.</span></span> <span data-ttu-id="5748b-113">Используется вместе с параметром SessionIdSeq для уникального определения экземпляра конференции.</span><span class="sxs-lookup"><span data-stu-id="5748b-113">Used in conjunction with SessionIdSeq to uniquely identify a conference instance.</span></span> <span data-ttu-id="5748b-114">Дополнительные сведения см. <a href="lync-server-2013-conferences-table.md">в таблице конференций в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="5748b-114">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5748b-115"><strong>сессионидсек</strong></span><span class="sxs-lookup"><span data-stu-id="5748b-115"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="5748b-116">int</span><span class="sxs-lookup"><span data-stu-id="5748b-116">int</span></span></p></td>
<td><p><span data-ttu-id="5748b-117">Идентификатор для определения экземпляра конференции.</span><span class="sxs-lookup"><span data-stu-id="5748b-117">ID number to identify the conference instance.</span></span> <span data-ttu-id="5748b-118">Используется вместе с параметром SessionIdTime для уникального определения экземпляра конференции.</span><span class="sxs-lookup"><span data-stu-id="5748b-118">Used in conjunction with SessionIdTime to uniquely identify a conference instance.</span></span> <span data-ttu-id="5748b-119">Дополнительные сведения см. <a href="lync-server-2013-conferences-table.md">в таблице конференций в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="5748b-119">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5748b-120"><strong>мкуури</strong></span><span class="sxs-lookup"><span data-stu-id="5748b-120"><strong>McuUri</strong></span></span></p></td>
<td><p><span data-ttu-id="5748b-121">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="5748b-121">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="5748b-122">URI сервера конференций, к которому подключился пользователь.</span><span class="sxs-lookup"><span data-stu-id="5748b-122">The URI of the conferencing server that the user connected to.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5748b-123"><strong>мкууритипе</strong></span><span class="sxs-lookup"><span data-stu-id="5748b-123"><strong>McuUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="5748b-124">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="5748b-124">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="5748b-125">URI сервера конференций, к которому подключился пользователь.</span><span class="sxs-lookup"><span data-stu-id="5748b-125">The URI of the conferencing server that the user connected to.</span></span> <span data-ttu-id="5748b-126">Дополнительные сведения см. <a href="lync-server-2013-uritypes-table.md">в таблице таблица uritypes в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="5748b-126">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5748b-127"><strong>UserUri</strong></span><span class="sxs-lookup"><span data-stu-id="5748b-127"><strong>UserUri</strong></span></span></p></td>
<td><p><span data-ttu-id="5748b-128">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="5748b-128">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="5748b-129">URI пользователя, сведения о присоединении или выходе к серверу конференций которого были записаны.</span><span class="sxs-lookup"><span data-stu-id="5748b-129">The URI of the user whose conferencing server join/leave information was captured.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5748b-130"><strong>усеруритипе</strong></span><span class="sxs-lookup"><span data-stu-id="5748b-130"><strong>UserUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="5748b-131">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="5748b-131">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="5748b-132">Тип URI пользователя, сведения о присоединении или выходе к серверу конференций которого были записаны.</span><span class="sxs-lookup"><span data-stu-id="5748b-132">The type of URI of the user whose conferencing server join/leave information was captured.</span></span> <span data-ttu-id="5748b-133">Дополнительные сведения см. <a href="lync-server-2013-uritypes-table.md">в таблице таблица uritypes в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="5748b-133">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5748b-134"><strong>усертенант</strong></span><span class="sxs-lookup"><span data-stu-id="5748b-134"><strong>UserTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="5748b-135">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="5748b-135">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="5748b-136">Клиент пользователя, сведения о присоединении или выходе к серверу конференций которого были записаны.</span><span class="sxs-lookup"><span data-stu-id="5748b-136">The tenant of the user whose conferencing server join/leave information was captured.</span></span> <span data-ttu-id="5748b-137">Дополнительные сведения см. <a href="lync-server-2013-tenants-table.md">в таблице клиентов в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="5748b-137">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5748b-138"><strong>усерклиентверсион</strong></span><span class="sxs-lookup"><span data-stu-id="5748b-138"><strong>UserClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="5748b-139">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="5748b-139">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="5748b-140">Версия клиента пользователя, сведения о присоединении или выходе к серверу конференций которого были записаны.</span><span class="sxs-lookup"><span data-stu-id="5748b-140">The version of client used by the user whose conferencing server join/leave information was captured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5748b-141"><strong>усерклиенттипе</strong></span><span class="sxs-lookup"><span data-stu-id="5748b-141"><strong>UserClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="5748b-142">int</span><span class="sxs-lookup"><span data-stu-id="5748b-142">int</span></span></p></td>
<td><p><span data-ttu-id="5748b-143">Версия клиента пользователя, сведения о присоединении или выходе к серверу конференций которого были записаны.</span><span class="sxs-lookup"><span data-stu-id="5748b-143">The client used by the user whose conferencing server join/leave information was captured.</span></span> <span data-ttu-id="5748b-144">Дополнительные сведения приведены <a href="lync-server-2013-useragentdef-table.md">в таблице таблица useragentdef в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="5748b-144">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5748b-145"><strong>усерклиенткатегори</strong></span><span class="sxs-lookup"><span data-stu-id="5748b-145"><strong>UserClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="5748b-146">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="5748b-146">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="5748b-147">Имя категории пользователя, сведения о присоединении или выходе к серверу конференций которого были записаны.</span><span class="sxs-lookup"><span data-stu-id="5748b-147">The name of the category of the client used by the user whose conferencing server join/leave information was captured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5748b-148"><strong>мкуусеринстанце</strong></span><span class="sxs-lookup"><span data-stu-id="5748b-148"><strong>McuUserInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="5748b-149">int</span><span class="sxs-lookup"><span data-stu-id="5748b-149">int</span></span></p></td>
<td><p><span data-ttu-id="5748b-150">Уникально определяет комбинацию пользователя и устройства для пользователей, одновременно вошедших на несколько устройств.</span><span class="sxs-lookup"><span data-stu-id="5748b-150">Uniquely identifies the user/device combination for users simultaneously logged on to multiple devices.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5748b-151"><strong>исусерфромпстн</strong></span><span class="sxs-lookup"><span data-stu-id="5748b-151"><strong>IsUserFromPstn</strong></span></span></p></td>
<td><p><span data-ttu-id="5748b-152">Битовая</span><span class="sxs-lookup"><span data-stu-id="5748b-152">bit</span></span></p></td>
<td><p><span data-ttu-id="5748b-153">Разряд, указывающий, является ли пользователь внутренним.</span><span class="sxs-lookup"><span data-stu-id="5748b-153">Bit that represents whether the user is an internal user or not.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5748b-154"><strong>диалогсессионидтиме</strong></span><span class="sxs-lookup"><span data-stu-id="5748b-154"><strong>DialogSessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="5748b-155">datetime</span><span class="sxs-lookup"><span data-stu-id="5748b-155">datetime</span></span></p></td>
<td><p><span data-ttu-id="5748b-156">Время запроса сеанса.</span><span class="sxs-lookup"><span data-stu-id="5748b-156">Time of session request.</span></span> <span data-ttu-id="5748b-157">Используется вместе с параметром SessionIdSeq для уникального определения сеанса.</span><span class="sxs-lookup"><span data-stu-id="5748b-157">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="5748b-158">Дополнительные сведения см. <a href="lync-server-2013-dialogs-table.md">в таблице диалоговых окон в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="5748b-158">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5748b-159"><strong>диалогсессионидсек</strong></span><span class="sxs-lookup"><span data-stu-id="5748b-159"><strong>DialogSessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="5748b-160">int</span><span class="sxs-lookup"><span data-stu-id="5748b-160">int</span></span></p></td>
<td><p><span data-ttu-id="5748b-161">Идентификационный номер для идентификации сеанса.</span><span class="sxs-lookup"><span data-stu-id="5748b-161">ID number to identify the session.</span></span> <span data-ttu-id="5748b-162">Используется совместно с параметром SessionIdTime для уникальной идентификации сеанса.</span><span class="sxs-lookup"><span data-stu-id="5748b-162">Used in conjunction with SessionIdTime to uniquely identify a session.</span></span> <span data-ttu-id="5748b-163">Дополнительные сведения см. <a href="lync-server-2013-dialogs-table.md">в таблице диалоговых окон в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="5748b-163">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5748b-164"><strong>DialogId</strong></span><span class="sxs-lookup"><span data-stu-id="5748b-164"><strong>DialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="5748b-165">varchar (775)</span><span class="sxs-lookup"><span data-stu-id="5748b-165">varchar(775)</span></span></p></td>
<td><p><span data-ttu-id="5748b-p110">Код диалога SIP этого сеанса. Формат: диалог;начальный тег;конечный тег.</span><span class="sxs-lookup"><span data-stu-id="5748b-p110">SIP dialog ID of the session. The format is: dialog;from-tag;to-tag.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5748b-168"><strong>усержоинтиме</strong></span><span class="sxs-lookup"><span data-stu-id="5748b-168"><strong>UserJoinTime</strong></span></span></p></td>
<td><p><span data-ttu-id="5748b-169">datetime</span><span class="sxs-lookup"><span data-stu-id="5748b-169">datetime</span></span></p></td>
<td><p><span data-ttu-id="5748b-170">Время, когда пользователь присоединился к серверу конференций.</span><span class="sxs-lookup"><span data-stu-id="5748b-170">Time the user joined the conferencing server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5748b-171"><strong>усерлеаветиме</strong></span><span class="sxs-lookup"><span data-stu-id="5748b-171"><strong>UserLeaveTime</strong></span></span></p></td>
<td><p><span data-ttu-id="5748b-172">datetime</span><span class="sxs-lookup"><span data-stu-id="5748b-172">datetime</span></span></p></td>
<td><p><span data-ttu-id="5748b-173">Время, когда пользователь вышел с сервера конференций.</span><span class="sxs-lookup"><span data-stu-id="5748b-173">Time the user left the conferencing server.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

