---
title: 'Lync Server 2013: представление Таблица focusjoinsandleaves'
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
ms.openlocfilehash: 85e13c744ed92dcbcb70b2da851b915e8c6f8104
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137007"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="focusjoinsandleaves-view-in-lync-server-2013"></a><span data-ttu-id="b70d7-102">Представление Таблица focusjoinsandleaves в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b70d7-102">FocusJoinsAndLeaves view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b70d7-103">_**Последнее изменение темы:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="b70d7-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="b70d7-104">В представлении FocusJoinsAndLeaves хранятся данные о подключении и отключении от отдельной конференции.</span><span class="sxs-lookup"><span data-stu-id="b70d7-104">The FocusJoinsAndLeaves view stores information about join and leave information for one conference.</span></span> <span data-ttu-id="b70d7-105">Каждая конференции продемонстрирована на этом представлении отдельной записью, которая создается при каждом подключении и отключении пользователя от этой конференции.</span><span class="sxs-lookup"><span data-stu-id="b70d7-105">Each conference is represented in this view by a record written each time a user joins and leaves the conference.</span></span> <span data-ttu-id="b70d7-106">Это представление было представлено в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b70d7-106">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b70d7-107">Столбец</span><span class="sxs-lookup"><span data-stu-id="b70d7-107">Column</span></span></th>
<th><span data-ttu-id="b70d7-108">Тип данных</span><span class="sxs-lookup"><span data-stu-id="b70d7-108">Data Type</span></span></th>
<th><span data-ttu-id="b70d7-109">Сведения</span><span class="sxs-lookup"><span data-stu-id="b70d7-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b70d7-110"><strong>сессионидтиме</strong></span><span class="sxs-lookup"><span data-stu-id="b70d7-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="b70d7-111">datetime</span><span class="sxs-lookup"><span data-stu-id="b70d7-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="b70d7-112">Время экземпляра конференции.</span><span class="sxs-lookup"><span data-stu-id="b70d7-112">Time of conference instance.</span></span> <span data-ttu-id="b70d7-113">Используется вместе с параметром SessionIdSeq для уникального определения экземпляра конференции.</span><span class="sxs-lookup"><span data-stu-id="b70d7-113">Used in conjunction with SessionIdSeq to uniquely identify a conference instance.</span></span> <span data-ttu-id="b70d7-114">Дополнительные сведения см. <a href="lync-server-2013-conferences-table.md">в таблице конференций в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="b70d7-114">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b70d7-115"><strong>сессионидсек</strong></span><span class="sxs-lookup"><span data-stu-id="b70d7-115"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="b70d7-116">int</span><span class="sxs-lookup"><span data-stu-id="b70d7-116">int</span></span></p></td>
<td><p><span data-ttu-id="b70d7-117">Идентификатор для определения экземпляра конференции.</span><span class="sxs-lookup"><span data-stu-id="b70d7-117">ID number to identify the conference instance.</span></span> <span data-ttu-id="b70d7-118">Используется вместе с параметром SessionIdTime для уникального определения экземпляра конференции.</span><span class="sxs-lookup"><span data-stu-id="b70d7-118">Used in conjunction with SessionIdTime to uniquely identify a conference instance.</span></span> <span data-ttu-id="b70d7-119">Дополнительные сведения см. <a href="lync-server-2013-conferences-table.md">в таблице конференций в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="b70d7-119">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b70d7-120"><strong>UserUri</strong></span><span class="sxs-lookup"><span data-stu-id="b70d7-120"><strong>UserUri</strong></span></span></p></td>
<td><p><span data-ttu-id="b70d7-121">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="b70d7-121">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="b70d7-122">URI пользователя, для которого получены данные о подключении или отключении от конференции.</span><span class="sxs-lookup"><span data-stu-id="b70d7-122">URI of the user whose conference join/leave information was captured.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b70d7-123"><strong>усеруритипе</strong></span><span class="sxs-lookup"><span data-stu-id="b70d7-123"><strong>UserUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="b70d7-124">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="b70d7-124">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b70d7-125">Тип URI пользователя, для которого получены данные о подключении или отключении от конференции.</span><span class="sxs-lookup"><span data-stu-id="b70d7-125">Type of URI of the user whose conference join/leave information was captured.</span></span> <span data-ttu-id="b70d7-126">Дополнительные сведения см. <a href="lync-server-2013-uritypes-table.md">в таблице таблица uritypes в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="b70d7-126">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b70d7-127"><strong>усертенант</strong></span><span class="sxs-lookup"><span data-stu-id="b70d7-127"><strong>UserTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="b70d7-128">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="b70d7-128">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b70d7-129">Клиент пользователя, для которого получены данные о подключении или отключении от конференции.</span><span class="sxs-lookup"><span data-stu-id="b70d7-129">Tenant of the user whose conference join/leave information was captured.</span></span> <span data-ttu-id="b70d7-130">Дополнительные сведения см. <a href="lync-server-2013-tenants-table.md">в таблице клиентов в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="b70d7-130">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b70d7-131"><strong>усерендпоинтид</strong></span><span class="sxs-lookup"><span data-stu-id="b70d7-131"><strong>UserEndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="b70d7-132">идентификатора</span><span class="sxs-lookup"><span data-stu-id="b70d7-132">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="b70d7-133">Уникальный идентификатор пользователя, для которого получены данные о подключении или отключении от конференции.</span><span class="sxs-lookup"><span data-stu-id="b70d7-133">Unique identifier of the user whose conference join/leave information was captured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b70d7-134"><strong>усерклиентверсион</strong></span><span class="sxs-lookup"><span data-stu-id="b70d7-134"><strong>UserClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="b70d7-135">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="b70d7-135">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b70d7-136">Версия клиента, используемая пользователем, для которого получены данные о подключении или отключении от конференции.</span><span class="sxs-lookup"><span data-stu-id="b70d7-136">Version of client used by the user whose conference join/leave information was captured.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b70d7-137"><strong>усерклиенттипе</strong></span><span class="sxs-lookup"><span data-stu-id="b70d7-137"><strong>UserClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="b70d7-138">int</span><span class="sxs-lookup"><span data-stu-id="b70d7-138">int</span></span></p></td>
<td><p><span data-ttu-id="b70d7-139">Клиент, используемый пользователем, для которого получены данные о подключении или отключении от конференции.</span><span class="sxs-lookup"><span data-stu-id="b70d7-139">Client used by the user whose conference join/leave information was captured.</span></span> <span data-ttu-id="b70d7-140">Более подробную информацию можно узнать <a href="lync-server-2013-useragentdef-table.md">в таблице таблица useragentdef в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="b70d7-140">See <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b70d7-141"><strong>усерклиенткатегори</strong></span><span class="sxs-lookup"><span data-stu-id="b70d7-141"><strong>UserClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="b70d7-142">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="b70d7-142">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="b70d7-143">Имя категории клиента, используемой пользователем, для которого получены данные о подключении или отключении от конференции.</span><span class="sxs-lookup"><span data-stu-id="b70d7-143">Name of the category of the client used by the user whose conference join/leave information was captured.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b70d7-144"><strong>фокусусеринстанце</strong></span><span class="sxs-lookup"><span data-stu-id="b70d7-144"><strong>FocusUserInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="b70d7-145">int</span><span class="sxs-lookup"><span data-stu-id="b70d7-145">int</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b70d7-146"><strong>исусеринтернал</strong></span><span class="sxs-lookup"><span data-stu-id="b70d7-146"><strong>IsuserInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="b70d7-147">Битовая</span><span class="sxs-lookup"><span data-stu-id="b70d7-147">bit</span></span></p></td>
<td><p><span data-ttu-id="b70d7-148">Разряд, указывающий, является ли пользователь внутренним.</span><span class="sxs-lookup"><span data-stu-id="b70d7-148">Bit that represents whether the user is an internal user or not.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b70d7-149"><strong>диалогсессионидтиме</strong></span><span class="sxs-lookup"><span data-stu-id="b70d7-149"><strong>DialogSessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="b70d7-150">datetime</span><span class="sxs-lookup"><span data-stu-id="b70d7-150">datetime</span></span></p></td>
<td><p><span data-ttu-id="b70d7-151">Время запроса сеанса.</span><span class="sxs-lookup"><span data-stu-id="b70d7-151">Time of session request.</span></span> <span data-ttu-id="b70d7-152">Используется вместе с параметром SessionIdSeq для уникального определения сеанса.</span><span class="sxs-lookup"><span data-stu-id="b70d7-152">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="b70d7-153">Дополнительные сведения см. <a href="lync-server-2013-dialogs-table.md">в таблице диалоговых окон в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="b70d7-153">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b70d7-154"><strong>диалогсессионидсек</strong></span><span class="sxs-lookup"><span data-stu-id="b70d7-154"><strong>DialogSessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="b70d7-155">int</span><span class="sxs-lookup"><span data-stu-id="b70d7-155">int</span></span></p></td>
<td><p><span data-ttu-id="b70d7-156">Если пользователь выполнил вход одновременно на несколько компьютеров или устройств, параметр UserInstance используется для уникальной идентификации комбинации пользователя и устройства.</span><span class="sxs-lookup"><span data-stu-id="b70d7-156">If a user is logged on at multiple computers or devices at the same time, UserInstance is used to uniquely identify the user/device combination.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b70d7-157"><strong>DialogId</strong></span><span class="sxs-lookup"><span data-stu-id="b70d7-157"><strong>DialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="b70d7-158">varchar (775)</span><span class="sxs-lookup"><span data-stu-id="b70d7-158">varchar(775)</span></span></p></td>
<td><p><span data-ttu-id="b70d7-p108">Код диалога SIP этого сеанса. Формат: диалог;начальный тег;конечный тег.</span><span class="sxs-lookup"><span data-stu-id="b70d7-p108">SIP dialog ID of the session. The format is: dialog;from-tag;to-tag.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b70d7-161"><strong>усержоинтиме</strong></span><span class="sxs-lookup"><span data-stu-id="b70d7-161"><strong>UserJoinTime</strong></span></span></p></td>
<td><p><span data-ttu-id="b70d7-162">datetime</span><span class="sxs-lookup"><span data-stu-id="b70d7-162">datetime</span></span></p></td>
<td><p><span data-ttu-id="b70d7-163">Время подключения пользователя к конференции.</span><span class="sxs-lookup"><span data-stu-id="b70d7-163">Time that the user joined the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b70d7-164"><strong>усерлеаветиме</strong></span><span class="sxs-lookup"><span data-stu-id="b70d7-164"><strong>UserLeaveTime</strong></span></span></p></td>
<td><p><span data-ttu-id="b70d7-165">datetime</span><span class="sxs-lookup"><span data-stu-id="b70d7-165">datetime</span></span></p></td>
<td><p><span data-ttu-id="b70d7-166">Время отключения пользователя от конференции.</span><span class="sxs-lookup"><span data-stu-id="b70d7-166">Time that the user left the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b70d7-167"><strong>UserRole</strong></span><span class="sxs-lookup"><span data-stu-id="b70d7-167"><strong>UserRole</strong></span></span></p></td>
<td><p><span data-ttu-id="b70d7-168">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="b70d7-168">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b70d7-169">Роль пользователя в конференции (например, докладчик или участник).</span><span class="sxs-lookup"><span data-stu-id="b70d7-169">User’s role in the conference, such as Presenter or Attendee.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

