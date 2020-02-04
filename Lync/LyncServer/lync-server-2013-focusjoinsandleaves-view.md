---
title: 'Lync Server 2013: представление Фокусжоинсандлеавес'
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
ms.openlocfilehash: 9d7cc1da4f5923a7c42e74c9069054863f1d99a1
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41722410"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="focusjoinsandleaves-view-in-lync-server-2013"></a><span data-ttu-id="03f80-102">Фокусжоинсандлеавес представления в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="03f80-102">FocusJoinsAndLeaves view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="03f80-103">_**Тема последнего изменения:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="03f80-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="03f80-104">В представлении Фокусжоинсандлеавес хранятся сведения о присоединениях и оставлении данных для одной конференции.</span><span class="sxs-lookup"><span data-stu-id="03f80-104">The FocusJoinsAndLeaves view stores information about join and leave information for one conference.</span></span> <span data-ttu-id="03f80-105">Каждое собрание представлено в этом представлении записью, которая записывается каждый раз, когда пользователь присоединяется к Конференции, и оставляет ее.</span><span class="sxs-lookup"><span data-stu-id="03f80-105">Each conference is represented in this view by a record written each time a user joins and leaves the conference.</span></span> <span data-ttu-id="03f80-106">Это представление было представлено в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="03f80-106">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="03f80-107">Столбец</span><span class="sxs-lookup"><span data-stu-id="03f80-107">Column</span></span></th>
<th><span data-ttu-id="03f80-108">Тип данных</span><span class="sxs-lookup"><span data-stu-id="03f80-108">Data Type</span></span></th>
<th><span data-ttu-id="03f80-109">Подробности</span><span class="sxs-lookup"><span data-stu-id="03f80-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="03f80-110"><strong>сессионидтиме</strong></span><span class="sxs-lookup"><span data-stu-id="03f80-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="03f80-111">datetime</span><span class="sxs-lookup"><span data-stu-id="03f80-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="03f80-112">Время экземпляра Конференции.</span><span class="sxs-lookup"><span data-stu-id="03f80-112">Time of conference instance.</span></span> <span data-ttu-id="03f80-113">Используется в сочетании с Сессионидсек для уникальной идентификации экземпляра Конференции.</span><span class="sxs-lookup"><span data-stu-id="03f80-113">Used in conjunction with SessionIdSeq to uniquely identify a conference instance.</span></span> <span data-ttu-id="03f80-114">Дополнительные сведения приведены <a href="lync-server-2013-conferences-table.md">в таблице конференции для Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="03f80-114">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="03f80-115"><strong>сессионидсек</strong></span><span class="sxs-lookup"><span data-stu-id="03f80-115"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="03f80-116">целое</span><span class="sxs-lookup"><span data-stu-id="03f80-116">int</span></span></p></td>
<td><p><span data-ttu-id="03f80-117">ИДЕНТИФИКАЦИОНный номер для идентификации экземпляра Конференции.</span><span class="sxs-lookup"><span data-stu-id="03f80-117">ID number to identify the conference instance.</span></span> <span data-ttu-id="03f80-118">Используется в сочетании с Сессионидтиме для уникальной идентификации экземпляра Конференции.</span><span class="sxs-lookup"><span data-stu-id="03f80-118">Used in conjunction with SessionIdTime to uniquely identify a conference instance.</span></span> <span data-ttu-id="03f80-119">Дополнительные сведения приведены <a href="lync-server-2013-conferences-table.md">в таблице конференции для Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="03f80-119">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="03f80-120"><strong>усерури</strong></span><span class="sxs-lookup"><span data-stu-id="03f80-120"><strong>UserUri</strong></span></span></p></td>
<td><p><span data-ttu-id="03f80-121">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="03f80-121">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="03f80-122">Универсальный код ресурса (URI), на который были собраны сведения о присоединении или закрытии Конференции.</span><span class="sxs-lookup"><span data-stu-id="03f80-122">URI of the user whose conference join/leave information was captured.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="03f80-123"><strong>усеруритипе</strong></span><span class="sxs-lookup"><span data-stu-id="03f80-123"><strong>UserUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="03f80-124">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="03f80-124">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="03f80-125">Тип универсального кода ресурса (URI), на который были собраны сведения о приходе или закрытии Конференции.</span><span class="sxs-lookup"><span data-stu-id="03f80-125">Type of URI of the user whose conference join/leave information was captured.</span></span> <span data-ttu-id="03f80-126">Для получения дополнительных сведений ознакомьтесь с <a href="lync-server-2013-uritypes-table.md">таблицей уритипес в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="03f80-126">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="03f80-127"><strong>усертенант</strong></span><span class="sxs-lookup"><span data-stu-id="03f80-127"><strong>UserTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="03f80-128">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="03f80-128">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="03f80-129">Клиент для пользователя, которому были собраны сведения о присоединении к Конференции или выходе из нее.</span><span class="sxs-lookup"><span data-stu-id="03f80-129">Tenant of the user whose conference join/leave information was captured.</span></span> <span data-ttu-id="03f80-130">Дополнительные сведения приведены в <a href="lync-server-2013-tenants-table.md">таблице "клиенты" в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="03f80-130">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="03f80-131"><strong>усерендпоинтид</strong></span><span class="sxs-lookup"><span data-stu-id="03f80-131"><strong>UserEndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="03f80-132">идентификатора</span><span class="sxs-lookup"><span data-stu-id="03f80-132">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="03f80-133">Уникальный идентификатор пользователя, для которого была собрана информация о присоединении к Конференции или выходе из нее.</span><span class="sxs-lookup"><span data-stu-id="03f80-133">Unique identifier of the user whose conference join/leave information was captured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="03f80-134"><strong>усерклиентверсион</strong></span><span class="sxs-lookup"><span data-stu-id="03f80-134"><strong>UserClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="03f80-135">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="03f80-135">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="03f80-136">Версия клиента, используемая пользователем, для которого была собрана информация о присоединении к Конференции или выходе из нее.</span><span class="sxs-lookup"><span data-stu-id="03f80-136">Version of client used by the user whose conference join/leave information was captured.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="03f80-137"><strong>усерклиенттипе</strong></span><span class="sxs-lookup"><span data-stu-id="03f80-137"><strong>UserClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="03f80-138">целое</span><span class="sxs-lookup"><span data-stu-id="03f80-138">int</span></span></p></td>
<td><p><span data-ttu-id="03f80-139">Клиент, используемый пользователем, для которого были собраны сведения о присоединении к Конференции или выходе из нее.</span><span class="sxs-lookup"><span data-stu-id="03f80-139">Client used by the user whose conference join/leave information was captured.</span></span> <span data-ttu-id="03f80-140">Для получения дополнительных сведений ознакомьтесь <a href="lync-server-2013-useragentdef-table.md">с таблицей усеражентдеф в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="03f80-140">See <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="03f80-141"><strong>усерклиенткатегори</strong></span><span class="sxs-lookup"><span data-stu-id="03f80-141"><strong>UserClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="03f80-142">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="03f80-142">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="03f80-143">Имя категории клиента, используемой пользователем, для которого были собраны сведения о приходе или закрытии Конференции.</span><span class="sxs-lookup"><span data-stu-id="03f80-143">Name of the category of the client used by the user whose conference join/leave information was captured.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="03f80-144"><strong>фокусусеринстанце</strong></span><span class="sxs-lookup"><span data-stu-id="03f80-144"><strong>FocusUserInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="03f80-145">целое</span><span class="sxs-lookup"><span data-stu-id="03f80-145">int</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="03f80-146"><strong>исусеринтернал</strong></span><span class="sxs-lookup"><span data-stu-id="03f80-146"><strong>IsuserInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="03f80-147">бит</span><span class="sxs-lookup"><span data-stu-id="03f80-147">bit</span></span></p></td>
<td><p><span data-ttu-id="03f80-148">Бит, обозначающий, является ли пользователь внутренним.</span><span class="sxs-lookup"><span data-stu-id="03f80-148">Bit that represents whether the user is an internal user or not.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="03f80-149"><strong>диалогсессионидтиме</strong></span><span class="sxs-lookup"><span data-stu-id="03f80-149"><strong>DialogSessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="03f80-150">datetime</span><span class="sxs-lookup"><span data-stu-id="03f80-150">datetime</span></span></p></td>
<td><p><span data-ttu-id="03f80-151">Время запроса сеанса.</span><span class="sxs-lookup"><span data-stu-id="03f80-151">Time of session request.</span></span> <span data-ttu-id="03f80-152">Используется в сочетании с Сессионидсек для уникальной идентификации сеанса.</span><span class="sxs-lookup"><span data-stu-id="03f80-152">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="03f80-153">Дополнительные сведения приведены <a href="lync-server-2013-dialogs-table.md">в таблице диалоговые окна Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="03f80-153">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="03f80-154"><strong>диалогсессионидсек</strong></span><span class="sxs-lookup"><span data-stu-id="03f80-154"><strong>DialogSessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="03f80-155">целое</span><span class="sxs-lookup"><span data-stu-id="03f80-155">int</span></span></p></td>
<td><p><span data-ttu-id="03f80-156">Если пользователь входит в систему на нескольких компьютерах или устройствах одновременно, Усеринстанце используется для уникальной идентификации комбинации пользователей и устройств.</span><span class="sxs-lookup"><span data-stu-id="03f80-156">If a user is logged on at multiple computers or devices at the same time, UserInstance is used to uniquely identify the user/device combination.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="03f80-157"><strong>диалогид</strong></span><span class="sxs-lookup"><span data-stu-id="03f80-157"><strong>DialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="03f80-158">varchar (775)</span><span class="sxs-lookup"><span data-stu-id="03f80-158">varchar(775)</span></span></p></td>
<td><p><span data-ttu-id="03f80-159">ИДЕНТИФИКАТОР диалогового окна SIP для сеанса.</span><span class="sxs-lookup"><span data-stu-id="03f80-159">SIP dialog ID of the session.</span></span> <span data-ttu-id="03f80-160">Формат: диалоговое окно; тег.</span><span class="sxs-lookup"><span data-stu-id="03f80-160">The format is: dialog;from-tag;to-tag.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="03f80-161"><strong>усержоинтиме</strong></span><span class="sxs-lookup"><span data-stu-id="03f80-161"><strong>UserJoinTime</strong></span></span></p></td>
<td><p><span data-ttu-id="03f80-162">datetime</span><span class="sxs-lookup"><span data-stu-id="03f80-162">datetime</span></span></p></td>
<td><p><span data-ttu-id="03f80-163">Время, в которое пользователь присоединился к Конференции.</span><span class="sxs-lookup"><span data-stu-id="03f80-163">Time that the user joined the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="03f80-164"><strong>усерлеаветиме</strong></span><span class="sxs-lookup"><span data-stu-id="03f80-164"><strong>UserLeaveTime</strong></span></span></p></td>
<td><p><span data-ttu-id="03f80-165">datetime</span><span class="sxs-lookup"><span data-stu-id="03f80-165">datetime</span></span></p></td>
<td><p><span data-ttu-id="03f80-166">Время, когда пользователь оставил Конференцию.</span><span class="sxs-lookup"><span data-stu-id="03f80-166">Time that the user left the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="03f80-167"><strong>UserRole</strong></span><span class="sxs-lookup"><span data-stu-id="03f80-167"><strong>UserRole</strong></span></span></p></td>
<td><p><span data-ttu-id="03f80-168">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="03f80-168">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="03f80-169">Роль пользователя на Конференции, например докладчика или участника.</span><span class="sxs-lookup"><span data-stu-id="03f80-169">User’s role in the conference, such as Presenter or Attendee.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

