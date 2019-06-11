---
title: 'Lync Server 2013: представление Фокусжоинсандлеавес'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: FocusJoinsAndLeaves view
ms:assetid: 226460ef-766f-4d61-80cb-f332b65a210d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687992(v=OCS.15)
ms:contentKeyID: 49733582
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3e1302bf744b0954d00eae4f4cc27454b2889745
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834147"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="focusjoinsandleaves-view-in-lync-server-2013"></a><span data-ttu-id="fe33b-102">Фокусжоинсандлеавес представления в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fe33b-102">FocusJoinsAndLeaves view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fe33b-103">_**Тема последнего изменения:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="fe33b-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="fe33b-104">В представлении Фокусжоинсандлеавес хранятся сведения о присоединениях и оставлении данных для одной конференции.</span><span class="sxs-lookup"><span data-stu-id="fe33b-104">The FocusJoinsAndLeaves view stores information about join and leave information for one conference.</span></span> <span data-ttu-id="fe33b-105">Каждое собрание представлено в этом представлении записью, которая записывается каждый раз, когда пользователь присоединяется к Конференции, и оставляет ее.</span><span class="sxs-lookup"><span data-stu-id="fe33b-105">Each conference is represented in this view by a record written each time a user joins and leaves the conference.</span></span> <span data-ttu-id="fe33b-106">Это представление было представлено в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="fe33b-106">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fe33b-107">Столбец</span><span class="sxs-lookup"><span data-stu-id="fe33b-107">Column</span></span></th>
<th><span data-ttu-id="fe33b-108">Тип данных</span><span class="sxs-lookup"><span data-stu-id="fe33b-108">Data Type</span></span></th>
<th><span data-ttu-id="fe33b-109">Подробности</span><span class="sxs-lookup"><span data-stu-id="fe33b-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fe33b-110"><strong>Сессионидтиме</strong></span><span class="sxs-lookup"><span data-stu-id="fe33b-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="fe33b-111">datetime</span><span class="sxs-lookup"><span data-stu-id="fe33b-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="fe33b-112">Время экземпляра Конференции.</span><span class="sxs-lookup"><span data-stu-id="fe33b-112">Time of conference instance.</span></span> <span data-ttu-id="fe33b-113">Используется в сочетании с Сессионидсек для уникальной идентификации экземпляра Конференции.</span><span class="sxs-lookup"><span data-stu-id="fe33b-113">Used in conjunction with SessionIdSeq to uniquely identify a conference instance.</span></span> <span data-ttu-id="fe33b-114">Дополнительные сведения приведены <a href="lync-server-2013-conferences-table.md">в таблице конференции для Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="fe33b-114">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fe33b-115"><strong>Сессионидсек</strong></span><span class="sxs-lookup"><span data-stu-id="fe33b-115"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="fe33b-116">целое</span><span class="sxs-lookup"><span data-stu-id="fe33b-116">int</span></span></p></td>
<td><p><span data-ttu-id="fe33b-117">ИДЕНТИФИКАЦИОНный номер для идентификации экземпляра Конференции.</span><span class="sxs-lookup"><span data-stu-id="fe33b-117">ID number to identify the conference instance.</span></span> <span data-ttu-id="fe33b-118">Используется в сочетании с Сессионидтиме для уникальной идентификации экземпляра Конференции.</span><span class="sxs-lookup"><span data-stu-id="fe33b-118">Used in conjunction with SessionIdTime to uniquely identify a conference instance.</span></span> <span data-ttu-id="fe33b-119">Дополнительные сведения приведены <a href="lync-server-2013-conferences-table.md">в таблице конференции для Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="fe33b-119">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fe33b-120"><strong>Усерури</strong></span><span class="sxs-lookup"><span data-stu-id="fe33b-120"><strong>UserUri</strong></span></span></p></td>
<td><p><span data-ttu-id="fe33b-121">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="fe33b-121">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="fe33b-122">Универсальный код ресурса (URI), на который были собраны сведения о присоединении или закрытии Конференции.</span><span class="sxs-lookup"><span data-stu-id="fe33b-122">URI of the user whose conference join/leave information was captured.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fe33b-123"><strong>Усеруритипе</strong></span><span class="sxs-lookup"><span data-stu-id="fe33b-123"><strong>UserUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="fe33b-124">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="fe33b-124">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="fe33b-125">Тип универсального кода ресурса (URI), на который были собраны сведения о приходе или закрытии Конференции.</span><span class="sxs-lookup"><span data-stu-id="fe33b-125">Type of URI of the user whose conference join/leave information was captured.</span></span> <span data-ttu-id="fe33b-126">Для получения дополнительных сведений ознакомьтесь с <a href="lync-server-2013-uritypes-table.md">таблицей уритипес в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="fe33b-126">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fe33b-127"><strong>Усертенант</strong></span><span class="sxs-lookup"><span data-stu-id="fe33b-127"><strong>UserTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="fe33b-128">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="fe33b-128">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="fe33b-129">Клиент для пользователя, которому были собраны сведения о присоединении к Конференции или выходе из нее.</span><span class="sxs-lookup"><span data-stu-id="fe33b-129">Tenant of the user whose conference join/leave information was captured.</span></span> <span data-ttu-id="fe33b-130">Дополнительные сведения приведены в <a href="lync-server-2013-tenants-table.md">таблице "клиенты" в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="fe33b-130">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fe33b-131"><strong>Усерендпоинтид</strong></span><span class="sxs-lookup"><span data-stu-id="fe33b-131"><strong>UserEndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="fe33b-132">идентификатора</span><span class="sxs-lookup"><span data-stu-id="fe33b-132">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="fe33b-133">Уникальный идентификатор пользователя, для которого была собрана информация о присоединении к Конференции или выходе из нее.</span><span class="sxs-lookup"><span data-stu-id="fe33b-133">Unique identifier of the user whose conference join/leave information was captured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fe33b-134"><strong>Усерклиентверсион</strong></span><span class="sxs-lookup"><span data-stu-id="fe33b-134"><strong>UserClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="fe33b-135">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="fe33b-135">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="fe33b-136">Версия клиента, используемая пользователем, для которого была собрана информация о присоединении к Конференции или выходе из нее.</span><span class="sxs-lookup"><span data-stu-id="fe33b-136">Version of client used by the user whose conference join/leave information was captured.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fe33b-137"><strong>Усерклиенттипе</strong></span><span class="sxs-lookup"><span data-stu-id="fe33b-137"><strong>UserClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="fe33b-138">целое</span><span class="sxs-lookup"><span data-stu-id="fe33b-138">int</span></span></p></td>
<td><p><span data-ttu-id="fe33b-139">Клиент, используемый пользователем, для которого были собраны сведения о присоединении к Конференции или выходе из нее.</span><span class="sxs-lookup"><span data-stu-id="fe33b-139">Client used by the user whose conference join/leave information was captured.</span></span> <span data-ttu-id="fe33b-140">Для получения дополнительных сведений ознакомьтесь <a href="lync-server-2013-useragentdef-table.md">с таблицей усеражентдеф в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="fe33b-140">See <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fe33b-141"><strong>Усерклиенткатегори</strong></span><span class="sxs-lookup"><span data-stu-id="fe33b-141"><strong>UserClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="fe33b-142">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="fe33b-142">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="fe33b-143">Имя категории клиента, используемой пользователем, для которого были собраны сведения о приходе или закрытии Конференции.</span><span class="sxs-lookup"><span data-stu-id="fe33b-143">Name of the category of the client used by the user whose conference join/leave information was captured.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fe33b-144"><strong>Фокусусеринстанце</strong></span><span class="sxs-lookup"><span data-stu-id="fe33b-144"><strong>FocusUserInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="fe33b-145">целое</span><span class="sxs-lookup"><span data-stu-id="fe33b-145">int</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fe33b-146"><strong>Исусеринтернал</strong></span><span class="sxs-lookup"><span data-stu-id="fe33b-146"><strong>IsuserInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="fe33b-147">бит</span><span class="sxs-lookup"><span data-stu-id="fe33b-147">bit</span></span></p></td>
<td><p><span data-ttu-id="fe33b-148">Бит, обозначающий, является ли пользователь внутренним.</span><span class="sxs-lookup"><span data-stu-id="fe33b-148">Bit that represents whether the user is an internal user or not.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fe33b-149"><strong>Диалогсессионидтиме</strong></span><span class="sxs-lookup"><span data-stu-id="fe33b-149"><strong>DialogSessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="fe33b-150">datetime</span><span class="sxs-lookup"><span data-stu-id="fe33b-150">datetime</span></span></p></td>
<td><p><span data-ttu-id="fe33b-151">Время запроса сеанса.</span><span class="sxs-lookup"><span data-stu-id="fe33b-151">Time of session request.</span></span> <span data-ttu-id="fe33b-152">Используется в сочетании с Сессионидсек для уникальной идентификации сеанса.</span><span class="sxs-lookup"><span data-stu-id="fe33b-152">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="fe33b-153">Дополнительные сведения приведены <a href="lync-server-2013-dialogs-table.md">в таблице диалоговые окна Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="fe33b-153">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fe33b-154"><strong>Диалогсессионидсек</strong></span><span class="sxs-lookup"><span data-stu-id="fe33b-154"><strong>DialogSessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="fe33b-155">целое</span><span class="sxs-lookup"><span data-stu-id="fe33b-155">int</span></span></p></td>
<td><p><span data-ttu-id="fe33b-156">Если пользователь входит в систему на нескольких компьютерах или устройствах одновременно, Усеринстанце используется для уникальной идентификации комбинации пользователей и устройств.</span><span class="sxs-lookup"><span data-stu-id="fe33b-156">If a user is logged on at multiple computers or devices at the same time, UserInstance is used to uniquely identify the user/device combination.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fe33b-157"><strong>Диалогид</strong></span><span class="sxs-lookup"><span data-stu-id="fe33b-157"><strong>DialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="fe33b-158">varchar (775)</span><span class="sxs-lookup"><span data-stu-id="fe33b-158">varchar(775)</span></span></p></td>
<td><p><span data-ttu-id="fe33b-159">ИДЕНТИФИКАТОР диалогового окна SIP для сеанса.</span><span class="sxs-lookup"><span data-stu-id="fe33b-159">SIP dialog ID of the session.</span></span> <span data-ttu-id="fe33b-160">Формат: диалоговое окно; тег.</span><span class="sxs-lookup"><span data-stu-id="fe33b-160">The format is: dialog;from-tag;to-tag.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fe33b-161"><strong>Усержоинтиме</strong></span><span class="sxs-lookup"><span data-stu-id="fe33b-161"><strong>UserJoinTime</strong></span></span></p></td>
<td><p><span data-ttu-id="fe33b-162">datetime</span><span class="sxs-lookup"><span data-stu-id="fe33b-162">datetime</span></span></p></td>
<td><p><span data-ttu-id="fe33b-163">Время, в которое пользователь присоединился к Конференции.</span><span class="sxs-lookup"><span data-stu-id="fe33b-163">Time that the user joined the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fe33b-164"><strong>Усерлеаветиме</strong></span><span class="sxs-lookup"><span data-stu-id="fe33b-164"><strong>UserLeaveTime</strong></span></span></p></td>
<td><p><span data-ttu-id="fe33b-165">datetime</span><span class="sxs-lookup"><span data-stu-id="fe33b-165">datetime</span></span></p></td>
<td><p><span data-ttu-id="fe33b-166">Время, когда пользователь оставил Конференцию.</span><span class="sxs-lookup"><span data-stu-id="fe33b-166">Time that the user left the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fe33b-167"><strong>UserRole</strong></span><span class="sxs-lookup"><span data-stu-id="fe33b-167"><strong>UserRole</strong></span></span></p></td>
<td><p><span data-ttu-id="fe33b-168">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="fe33b-168">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="fe33b-169">Роль пользователя на Конференции, например докладчика или участника.</span><span class="sxs-lookup"><span data-stu-id="fe33b-169">User’s role in the conference, such as Presenter or Attendee.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

