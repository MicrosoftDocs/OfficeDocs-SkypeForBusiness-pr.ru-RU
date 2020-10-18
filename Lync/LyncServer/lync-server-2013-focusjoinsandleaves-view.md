---
title: 'Lync Server 2013: представление Таблица focusjoinsandleaves'
description: 'Lync Server 2013: представление Таблица focusjoinsandleaves.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: FocusJoinsAndLeaves view
ms:assetid: 226460ef-766f-4d61-80cb-f332b65a210d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687992(v=OCS.15)
ms:contentKeyID: 49733582
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c6f68c44461e378e9ebedce1305ee6b384a7a8a7
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48577455"
---
# <a name="focusjoinsandleaves-view-in-lync-server-2013"></a><span data-ttu-id="7221d-103">Представление Таблица focusjoinsandleaves в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7221d-103">FocusJoinsAndLeaves view in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7221d-104">_**Последнее изменение темы:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="7221d-104">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="7221d-105">В представлении FocusJoinsAndLeaves хранятся данные о подключении и отключении от отдельной конференции.</span><span class="sxs-lookup"><span data-stu-id="7221d-105">The FocusJoinsAndLeaves view stores information about join and leave information for one conference.</span></span> <span data-ttu-id="7221d-106">Каждая конференции продемонстрирована на этом представлении отдельной записью, которая создается при каждом подключении и отключении пользователя от этой конференции.</span><span class="sxs-lookup"><span data-stu-id="7221d-106">Each conference is represented in this view by a record written each time a user joins and leaves the conference.</span></span> <span data-ttu-id="7221d-107">Это представление было представлено в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7221d-107">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7221d-108">Столбец</span><span class="sxs-lookup"><span data-stu-id="7221d-108">Column</span></span></th>
<th><span data-ttu-id="7221d-109">Тип данных</span><span class="sxs-lookup"><span data-stu-id="7221d-109">Data Type</span></span></th>
<th><span data-ttu-id="7221d-110">Сведения</span><span class="sxs-lookup"><span data-stu-id="7221d-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7221d-111"><strong>сессионидтиме</strong></span><span class="sxs-lookup"><span data-stu-id="7221d-111"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="7221d-112">datetime</span><span class="sxs-lookup"><span data-stu-id="7221d-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="7221d-113">Время экземпляра конференции.</span><span class="sxs-lookup"><span data-stu-id="7221d-113">Time of conference instance.</span></span> <span data-ttu-id="7221d-114">Используется вместе с параметром SessionIdSeq для уникального определения экземпляра конференции.</span><span class="sxs-lookup"><span data-stu-id="7221d-114">Used in conjunction with SessionIdSeq to uniquely identify a conference instance.</span></span> <span data-ttu-id="7221d-115">Дополнительные сведения см. <a href="lync-server-2013-conferences-table.md">в таблице конференций в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="7221d-115">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7221d-116"><strong>сессионидсек</strong></span><span class="sxs-lookup"><span data-stu-id="7221d-116"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="7221d-117">int</span><span class="sxs-lookup"><span data-stu-id="7221d-117">int</span></span></p></td>
<td><p><span data-ttu-id="7221d-118">Идентификатор для определения экземпляра конференции.</span><span class="sxs-lookup"><span data-stu-id="7221d-118">ID number to identify the conference instance.</span></span> <span data-ttu-id="7221d-119">Используется вместе с параметром SessionIdTime для уникального определения экземпляра конференции.</span><span class="sxs-lookup"><span data-stu-id="7221d-119">Used in conjunction with SessionIdTime to uniquely identify a conference instance.</span></span> <span data-ttu-id="7221d-120">Дополнительные сведения см. <a href="lync-server-2013-conferences-table.md">в таблице конференций в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="7221d-120">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7221d-121"><strong>UserUri</strong></span><span class="sxs-lookup"><span data-stu-id="7221d-121"><strong>UserUri</strong></span></span></p></td>
<td><p><span data-ttu-id="7221d-122">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="7221d-122">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="7221d-123">URI пользователя, для которого получены данные о подключении или отключении от конференции.</span><span class="sxs-lookup"><span data-stu-id="7221d-123">URI of the user whose conference join/leave information was captured.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7221d-124"><strong>усеруритипе</strong></span><span class="sxs-lookup"><span data-stu-id="7221d-124"><strong>UserUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="7221d-125">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="7221d-125">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="7221d-126">Тип URI пользователя, для которого получены данные о подключении или отключении от конференции.</span><span class="sxs-lookup"><span data-stu-id="7221d-126">Type of URI of the user whose conference join/leave information was captured.</span></span> <span data-ttu-id="7221d-127">Дополнительные сведения см. <a href="lync-server-2013-uritypes-table.md">в таблице таблица uritypes в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="7221d-127">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7221d-128"><strong>усертенант</strong></span><span class="sxs-lookup"><span data-stu-id="7221d-128"><strong>UserTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="7221d-129">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="7221d-129">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="7221d-130">Клиент пользователя, для которого получены данные о подключении или отключении от конференции.</span><span class="sxs-lookup"><span data-stu-id="7221d-130">Tenant of the user whose conference join/leave information was captured.</span></span> <span data-ttu-id="7221d-131">Дополнительные сведения см. <a href="lync-server-2013-tenants-table.md">в таблице клиентов в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="7221d-131">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7221d-132"><strong>усерендпоинтид</strong></span><span class="sxs-lookup"><span data-stu-id="7221d-132"><strong>UserEndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="7221d-133">идентификатора</span><span class="sxs-lookup"><span data-stu-id="7221d-133">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="7221d-134">Уникальный идентификатор пользователя, для которого получены данные о подключении или отключении от конференции.</span><span class="sxs-lookup"><span data-stu-id="7221d-134">Unique identifier of the user whose conference join/leave information was captured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7221d-135"><strong>усерклиентверсион</strong></span><span class="sxs-lookup"><span data-stu-id="7221d-135"><strong>UserClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="7221d-136">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="7221d-136">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="7221d-137">Версия клиента, используемая пользователем, для которого получены данные о подключении или отключении от конференции.</span><span class="sxs-lookup"><span data-stu-id="7221d-137">Version of client used by the user whose conference join/leave information was captured.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7221d-138"><strong>усерклиенттипе</strong></span><span class="sxs-lookup"><span data-stu-id="7221d-138"><strong>UserClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="7221d-139">int</span><span class="sxs-lookup"><span data-stu-id="7221d-139">int</span></span></p></td>
<td><p><span data-ttu-id="7221d-140">Клиент, используемый пользователем, для которого получены данные о подключении или отключении от конференции.</span><span class="sxs-lookup"><span data-stu-id="7221d-140">Client used by the user whose conference join/leave information was captured.</span></span> <span data-ttu-id="7221d-141">Более подробную информацию можно узнать <a href="lync-server-2013-useragentdef-table.md">в таблице таблица useragentdef в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="7221d-141">See <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7221d-142"><strong>усерклиенткатегори</strong></span><span class="sxs-lookup"><span data-stu-id="7221d-142"><strong>UserClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="7221d-143">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="7221d-143">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="7221d-144">Имя категории клиента, используемой пользователем, для которого получены данные о подключении или отключении от конференции.</span><span class="sxs-lookup"><span data-stu-id="7221d-144">Name of the category of the client used by the user whose conference join/leave information was captured.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7221d-145"><strong>фокусусеринстанце</strong></span><span class="sxs-lookup"><span data-stu-id="7221d-145"><strong>FocusUserInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="7221d-146">int</span><span class="sxs-lookup"><span data-stu-id="7221d-146">int</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7221d-147"><strong>исусеринтернал</strong></span><span class="sxs-lookup"><span data-stu-id="7221d-147"><strong>IsuserInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="7221d-148">Битовая</span><span class="sxs-lookup"><span data-stu-id="7221d-148">bit</span></span></p></td>
<td><p><span data-ttu-id="7221d-149">Разряд, указывающий, является ли пользователь внутренним.</span><span class="sxs-lookup"><span data-stu-id="7221d-149">Bit that represents whether the user is an internal user or not.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7221d-150"><strong>диалогсессионидтиме</strong></span><span class="sxs-lookup"><span data-stu-id="7221d-150"><strong>DialogSessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="7221d-151">datetime</span><span class="sxs-lookup"><span data-stu-id="7221d-151">datetime</span></span></p></td>
<td><p><span data-ttu-id="7221d-152">Время запроса сеанса.</span><span class="sxs-lookup"><span data-stu-id="7221d-152">Time of session request.</span></span> <span data-ttu-id="7221d-153">Используется вместе с параметром SessionIdSeq для уникального определения сеанса.</span><span class="sxs-lookup"><span data-stu-id="7221d-153">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="7221d-154">Дополнительные сведения см. <a href="lync-server-2013-dialogs-table.md">в таблице диалоговых окон в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="7221d-154">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7221d-155"><strong>диалогсессионидсек</strong></span><span class="sxs-lookup"><span data-stu-id="7221d-155"><strong>DialogSessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="7221d-156">int</span><span class="sxs-lookup"><span data-stu-id="7221d-156">int</span></span></p></td>
<td><p><span data-ttu-id="7221d-157">Если пользователь выполнил вход одновременно на несколько компьютеров или устройств, параметр UserInstance используется для уникальной идентификации комбинации пользователя и устройства.</span><span class="sxs-lookup"><span data-stu-id="7221d-157">If a user is logged on at multiple computers or devices at the same time, UserInstance is used to uniquely identify the user/device combination.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7221d-158"><strong>DialogId</strong></span><span class="sxs-lookup"><span data-stu-id="7221d-158"><strong>DialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="7221d-159">varchar (775)</span><span class="sxs-lookup"><span data-stu-id="7221d-159">varchar(775)</span></span></p></td>
<td><p><span data-ttu-id="7221d-p108">Код диалога SIP этого сеанса. Формат: диалог;начальный тег;конечный тег.</span><span class="sxs-lookup"><span data-stu-id="7221d-p108">SIP dialog ID of the session. The format is: dialog;from-tag;to-tag.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7221d-162"><strong>усержоинтиме</strong></span><span class="sxs-lookup"><span data-stu-id="7221d-162"><strong>UserJoinTime</strong></span></span></p></td>
<td><p><span data-ttu-id="7221d-163">datetime</span><span class="sxs-lookup"><span data-stu-id="7221d-163">datetime</span></span></p></td>
<td><p><span data-ttu-id="7221d-164">Время подключения пользователя к конференции.</span><span class="sxs-lookup"><span data-stu-id="7221d-164">Time that the user joined the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7221d-165"><strong>усерлеаветиме</strong></span><span class="sxs-lookup"><span data-stu-id="7221d-165"><strong>UserLeaveTime</strong></span></span></p></td>
<td><p><span data-ttu-id="7221d-166">datetime</span><span class="sxs-lookup"><span data-stu-id="7221d-166">datetime</span></span></p></td>
<td><p><span data-ttu-id="7221d-167">Время отключения пользователя от конференции.</span><span class="sxs-lookup"><span data-stu-id="7221d-167">Time that the user left the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7221d-168"><strong>UserRole</strong></span><span class="sxs-lookup"><span data-stu-id="7221d-168"><strong>UserRole</strong></span></span></p></td>
<td><p><span data-ttu-id="7221d-169">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="7221d-169">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="7221d-170">Роль пользователя в конференции (например, докладчик или участник).</span><span class="sxs-lookup"><span data-stu-id="7221d-170">User’s role in the conference, such as Presenter or Attendee.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

