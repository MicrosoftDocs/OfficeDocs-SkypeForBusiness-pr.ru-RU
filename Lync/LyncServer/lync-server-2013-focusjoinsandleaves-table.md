---
title: 'Lync Server 2013: таблица FocusJoinsAndLeaves'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: FocusJoinsAndLeaves table
ms:assetid: e6f0212c-67e9-4061-8720-d0296e855991
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399026(v=OCS.15)
ms:contentKeyID: 48185690
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9ead6fc2ce79f7ab1206476ee420bd2ba5a7711f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834146"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="focusjoinsandleaves-table-in-lync-server-2013"></a><span data-ttu-id="c7fc1-102">Таблица FocusJoinsAndLeaves в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c7fc1-102">FocusJoinsAndLeaves table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c7fc1-103">_**Тема последнего изменения:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="c7fc1-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="c7fc1-104">В каждой записи в этой таблице содержатся сведения о CDR для одного пользователя и о том, что нужно оставлять на одной конференции.</span><span class="sxs-lookup"><span data-stu-id="c7fc1-104">Each record in this table contains the CDR information about one user’s join and leave information for one conference.</span></span> <span data-ttu-id="c7fc1-105">Каждая конференция представлена в этой таблице одной записью каждый раз, когда пользователь присоединяется к Конференции и оставляет ее.</span><span class="sxs-lookup"><span data-stu-id="c7fc1-105">Each conference is represented in this table by one record for each time a user joins and leaves the conference.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c7fc1-106">Столбец</span><span class="sxs-lookup"><span data-stu-id="c7fc1-106">Column</span></span></th>
<th><span data-ttu-id="c7fc1-107">Тип данных</span><span class="sxs-lookup"><span data-stu-id="c7fc1-107">Data Type</span></span></th>
<th><span data-ttu-id="c7fc1-108">Ключ/индекс</span><span class="sxs-lookup"><span data-stu-id="c7fc1-108">Key/Index</span></span></th>
<th><span data-ttu-id="c7fc1-109">Сведения</span><span class="sxs-lookup"><span data-stu-id="c7fc1-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c7fc1-110"><strong>Сессионидтиме</strong></span><span class="sxs-lookup"><span data-stu-id="c7fc1-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="c7fc1-111">datetime</span><span class="sxs-lookup"><span data-stu-id="c7fc1-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="c7fc1-112">Основной, внешний</span><span class="sxs-lookup"><span data-stu-id="c7fc1-112">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="c7fc1-113">Время экземпляра Конференции.</span><span class="sxs-lookup"><span data-stu-id="c7fc1-113">Time of conference instance.</span></span> <span data-ttu-id="c7fc1-114">Используется в сочетании с <strong>сессионидсек</strong> для уникальной идентификации экземпляра Конференции.</span><span class="sxs-lookup"><span data-stu-id="c7fc1-114">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a conference instance.</span></span> <span data-ttu-id="c7fc1-115">Дополнительные сведения приведены <a href="lync-server-2013-conferences-table.md">в таблице конференции для Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="c7fc1-115">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c7fc1-116"><strong>Сессионидсек</strong></span><span class="sxs-lookup"><span data-stu-id="c7fc1-116"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="c7fc1-117">целое</span><span class="sxs-lookup"><span data-stu-id="c7fc1-117">int</span></span></p></td>
<td><p><span data-ttu-id="c7fc1-118">Основной, внешний</span><span class="sxs-lookup"><span data-stu-id="c7fc1-118">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="c7fc1-119">ИДЕНТИФИКАЦИОНный номер для идентификации экземпляра Конференции.</span><span class="sxs-lookup"><span data-stu-id="c7fc1-119">ID number to identify the conference instance.</span></span> <span data-ttu-id="c7fc1-120">Используется в сочетании с <strong>сессионидтиме</strong> для уникальной идентификации экземпляра Конференции.</span><span class="sxs-lookup"><span data-stu-id="c7fc1-120">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a conference instance.</span></span> <span data-ttu-id="c7fc1-121">Дополнительные сведения приведены <a href="lync-server-2013-conferences-table.md">в таблице конференции для Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="c7fc1-121">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c7fc1-122"><strong>Диалогсессионидтиме</strong></span><span class="sxs-lookup"><span data-stu-id="c7fc1-122"><strong>DialogSessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="c7fc1-123">datetime</span><span class="sxs-lookup"><span data-stu-id="c7fc1-123">datetime</span></span></p></td>
<td><p><span data-ttu-id="c7fc1-124">Основной, внешний</span><span class="sxs-lookup"><span data-stu-id="c7fc1-124">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="c7fc1-125">Время запроса сеанса.</span><span class="sxs-lookup"><span data-stu-id="c7fc1-125">Time of session request.</span></span> <span data-ttu-id="c7fc1-126">Используется в сочетании с <strong>сессионидсек</strong> для уникальной идентификации сеанса.</span><span class="sxs-lookup"><span data-stu-id="c7fc1-126">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="c7fc1-127">Дополнительные сведения приведены <a href="lync-server-2013-dialogs-table.md">в таблице диалоговые окна Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="c7fc1-127">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c7fc1-128"><strong>Диалогсессионидсек</strong></span><span class="sxs-lookup"><span data-stu-id="c7fc1-128"><strong>DialogSessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="c7fc1-129">целое</span><span class="sxs-lookup"><span data-stu-id="c7fc1-129">int</span></span></p></td>
<td><p><span data-ttu-id="c7fc1-130">Основной, внешний</span><span class="sxs-lookup"><span data-stu-id="c7fc1-130">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="c7fc1-131">ИДЕНТИФИКАЦИОНный номер для идентификации сеанса.</span><span class="sxs-lookup"><span data-stu-id="c7fc1-131">ID number to identify the session.</span></span> <span data-ttu-id="c7fc1-132">Используется в сочетании с <strong>сессионидтиме</strong> для уникальной идентификации сеанса.</span><span class="sxs-lookup"><span data-stu-id="c7fc1-132">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="c7fc1-133">Дополнительные сведения приведены <a href="lync-server-2013-dialogs-table.md">в таблице диалоговые окна Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="c7fc1-133">see the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c7fc1-134"><strong>Идентификатора пользователя</strong></span><span class="sxs-lookup"><span data-stu-id="c7fc1-134"><strong>UserId</strong></span></span></p></td>
<td><p><span data-ttu-id="c7fc1-135">целое</span><span class="sxs-lookup"><span data-stu-id="c7fc1-135">int</span></span></p></td>
<td><p><span data-ttu-id="c7fc1-136">Другом</span><span class="sxs-lookup"><span data-stu-id="c7fc1-136">Foreign</span></span></p></td>
<td><p><span data-ttu-id="c7fc1-137">Уникальный номер, идентифицирующий этого пользователя, на который ссылается <a href="lync-server-2013-users-table.md">Таблица "Пользователи" в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="c7fc1-137">Unique number identifying this user, referenced from the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c7fc1-138"><strong>Фокусусеринстанце</strong></span><span class="sxs-lookup"><span data-stu-id="c7fc1-138"><strong>FocusUserInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="c7fc1-139">целое</span><span class="sxs-lookup"><span data-stu-id="c7fc1-139">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c7fc1-140">Если пользователь входит в систему на нескольких компьютерах или устройствах одновременно, <strong>усеринстанце</strong> используется для уникальной идентификации комбинации пользователей и устройств.</span><span class="sxs-lookup"><span data-stu-id="c7fc1-140">If a user is logged on at multiple computers or devices at the same time, <strong>UserInstance</strong> is used to uniquely identify the user/device combination.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c7fc1-141"><strong>Исусеринтернал</strong></span><span class="sxs-lookup"><span data-stu-id="c7fc1-141"><strong>IsUserInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="c7fc1-142">бит</span><span class="sxs-lookup"><span data-stu-id="c7fc1-142">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="c7fc1-143">Вне зависимости от того, вошел ли пользователь из внутреннего или нет.</span><span class="sxs-lookup"><span data-stu-id="c7fc1-143">Whether the user logged on from internal or not.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c7fc1-144"><strong>UserRole</strong></span><span class="sxs-lookup"><span data-stu-id="c7fc1-144"><strong>UserRole</strong></span></span></p></td>
<td><p><span data-ttu-id="c7fc1-145">целое</span><span class="sxs-lookup"><span data-stu-id="c7fc1-145">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="c7fc1-146">Роль этого пользователя на Конференции, например докладчика или участника.</span><span class="sxs-lookup"><span data-stu-id="c7fc1-146">This user’s role in the conference, such as Presenter or Attendee.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c7fc1-147"><strong>Усержоинтиме</strong></span><span class="sxs-lookup"><span data-stu-id="c7fc1-147"><strong>UserJoinTime</strong></span></span></p></td>
<td><p><span data-ttu-id="c7fc1-148">datetime</span><span class="sxs-lookup"><span data-stu-id="c7fc1-148">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="c7fc1-149">Время присоединения пользователя к Конференции.</span><span class="sxs-lookup"><span data-stu-id="c7fc1-149">The time this user joins the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c7fc1-150"><strong>Усерлеаветиме</strong></span><span class="sxs-lookup"><span data-stu-id="c7fc1-150"><strong>UserLeaveTime</strong></span></span></p></td>
<td><p><span data-ttu-id="c7fc1-151">datetime</span><span class="sxs-lookup"><span data-stu-id="c7fc1-151">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="c7fc1-152">Время, когда пользователь покидает Конференцию.</span><span class="sxs-lookup"><span data-stu-id="c7fc1-152">The time this user leaves the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c7fc1-153"><strong>Клиентверид</strong></span><span class="sxs-lookup"><span data-stu-id="c7fc1-153"><strong>ClientVerId</strong></span></span></p></td>
<td><p><span data-ttu-id="c7fc1-154">целое</span><span class="sxs-lookup"><span data-stu-id="c7fc1-154">int</span></span></p></td>
<td><p><span data-ttu-id="c7fc1-155">Другом</span><span class="sxs-lookup"><span data-stu-id="c7fc1-155">Foreign</span></span></p></td>
<td><p><span data-ttu-id="c7fc1-156">Версия клиентского программного обеспечения пользователя, на которую ссылается <a href="lync-server-2013-clientversions-table.md">Таблица клиентверсионс в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="c7fc1-156">Version of the user’s client software, referenced to the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c7fc1-157"><strong>Усерендпоинтид</strong></span><span class="sxs-lookup"><span data-stu-id="c7fc1-157"><strong>UserEndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="c7fc1-158">Идентификатора</span><span class="sxs-lookup"><span data-stu-id="c7fc1-158">uniqueIdentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c7fc1-159">Глобальный уникальный идентификатор (GUID) конечной точки, используемой в Конференции.</span><span class="sxs-lookup"><span data-stu-id="c7fc1-159">Globally unique identifier (GUID) of the endpoint used in the conference.</span></span></p>
<p><span data-ttu-id="c7fc1-160">Это поле было введено в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c7fc1-160">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

