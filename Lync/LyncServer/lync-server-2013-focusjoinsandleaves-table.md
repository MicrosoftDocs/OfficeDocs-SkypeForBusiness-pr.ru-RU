---
title: 'Lync Server 2013: таблица FocusJoinsAndLeaves'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: FocusJoinsAndLeaves table
ms:assetid: e6f0212c-67e9-4061-8720-d0296e855991
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399026(v=OCS.15)
ms:contentKeyID: 48185690
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4365e5bbfe92168047165adf6504333e1c34fab6
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765267"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="focusjoinsandleaves-table-in-lync-server-2013"></a><span data-ttu-id="bf5e8-102">Таблица FocusJoinsAndLeaves в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bf5e8-102">FocusJoinsAndLeaves table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bf5e8-103">_**Тема последнего изменения:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="bf5e8-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="bf5e8-104">В каждой записи в этой таблице содержатся сведения о CDR для одного пользователя и о том, что нужно оставлять на одной конференции.</span><span class="sxs-lookup"><span data-stu-id="bf5e8-104">Each record in this table contains the CDR information about one user’s join and leave information for one conference.</span></span> <span data-ttu-id="bf5e8-105">Каждая конференция представлена в этой таблице одной записью каждый раз, когда пользователь присоединяется к Конференции и оставляет ее.</span><span class="sxs-lookup"><span data-stu-id="bf5e8-105">Each conference is represented in this table by one record for each time a user joins and leaves the conference.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bf5e8-106">Столбец</span><span class="sxs-lookup"><span data-stu-id="bf5e8-106">Column</span></span></th>
<th><span data-ttu-id="bf5e8-107">Тип данных</span><span class="sxs-lookup"><span data-stu-id="bf5e8-107">Data Type</span></span></th>
<th><span data-ttu-id="bf5e8-108">Ключ/индекс</span><span class="sxs-lookup"><span data-stu-id="bf5e8-108">Key/Index</span></span></th>
<th><span data-ttu-id="bf5e8-109">Сведения</span><span class="sxs-lookup"><span data-stu-id="bf5e8-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bf5e8-110"><strong>сессионидтиме</strong></span><span class="sxs-lookup"><span data-stu-id="bf5e8-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="bf5e8-111">datetime</span><span class="sxs-lookup"><span data-stu-id="bf5e8-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="bf5e8-112">Основной, внешний</span><span class="sxs-lookup"><span data-stu-id="bf5e8-112">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="bf5e8-113">Время экземпляра Конференции.</span><span class="sxs-lookup"><span data-stu-id="bf5e8-113">Time of conference instance.</span></span> <span data-ttu-id="bf5e8-114">Используется в сочетании с <strong>сессионидсек</strong> для уникальной идентификации экземпляра Конференции.</span><span class="sxs-lookup"><span data-stu-id="bf5e8-114">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a conference instance.</span></span> <span data-ttu-id="bf5e8-115">Дополнительные сведения приведены <a href="lync-server-2013-conferences-table.md">в таблице конференции для Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="bf5e8-115">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bf5e8-116"><strong>сессионидсек</strong></span><span class="sxs-lookup"><span data-stu-id="bf5e8-116"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="bf5e8-117">целое</span><span class="sxs-lookup"><span data-stu-id="bf5e8-117">int</span></span></p></td>
<td><p><span data-ttu-id="bf5e8-118">Основной, внешний</span><span class="sxs-lookup"><span data-stu-id="bf5e8-118">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="bf5e8-119">ИДЕНТИФИКАЦИОНный номер для идентификации экземпляра Конференции.</span><span class="sxs-lookup"><span data-stu-id="bf5e8-119">ID number to identify the conference instance.</span></span> <span data-ttu-id="bf5e8-120">Используется в сочетании с <strong>сессионидтиме</strong> для уникальной идентификации экземпляра Конференции.</span><span class="sxs-lookup"><span data-stu-id="bf5e8-120">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a conference instance.</span></span> <span data-ttu-id="bf5e8-121">Дополнительные сведения приведены <a href="lync-server-2013-conferences-table.md">в таблице конференции для Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="bf5e8-121">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bf5e8-122"><strong>диалогсессионидтиме</strong></span><span class="sxs-lookup"><span data-stu-id="bf5e8-122"><strong>DialogSessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="bf5e8-123">datetime</span><span class="sxs-lookup"><span data-stu-id="bf5e8-123">datetime</span></span></p></td>
<td><p><span data-ttu-id="bf5e8-124">Основной, внешний</span><span class="sxs-lookup"><span data-stu-id="bf5e8-124">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="bf5e8-125">Время запроса сеанса.</span><span class="sxs-lookup"><span data-stu-id="bf5e8-125">Time of session request.</span></span> <span data-ttu-id="bf5e8-126">Используется в сочетании с <strong>сессионидсек</strong> для уникальной идентификации сеанса.</span><span class="sxs-lookup"><span data-stu-id="bf5e8-126">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="bf5e8-127">Дополнительные сведения приведены <a href="lync-server-2013-dialogs-table.md">в таблице диалоговые окна Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="bf5e8-127">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bf5e8-128"><strong>диалогсессионидсек</strong></span><span class="sxs-lookup"><span data-stu-id="bf5e8-128"><strong>DialogSessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="bf5e8-129">целое</span><span class="sxs-lookup"><span data-stu-id="bf5e8-129">int</span></span></p></td>
<td><p><span data-ttu-id="bf5e8-130">Основной, внешний</span><span class="sxs-lookup"><span data-stu-id="bf5e8-130">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="bf5e8-131">ИДЕНТИФИКАЦИОНный номер для идентификации сеанса.</span><span class="sxs-lookup"><span data-stu-id="bf5e8-131">ID number to identify the session.</span></span> <span data-ttu-id="bf5e8-132">Используется в сочетании с <strong>сессионидтиме</strong> для уникальной идентификации сеанса.</span><span class="sxs-lookup"><span data-stu-id="bf5e8-132">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="bf5e8-133">Дополнительные сведения приведены <a href="lync-server-2013-dialogs-table.md">в таблице диалоговые окна Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="bf5e8-133">see the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bf5e8-134"><strong>Идентификатора пользователя</strong></span><span class="sxs-lookup"><span data-stu-id="bf5e8-134"><strong>UserId</strong></span></span></p></td>
<td><p><span data-ttu-id="bf5e8-135">целое</span><span class="sxs-lookup"><span data-stu-id="bf5e8-135">int</span></span></p></td>
<td><p><span data-ttu-id="bf5e8-136">Другом</span><span class="sxs-lookup"><span data-stu-id="bf5e8-136">Foreign</span></span></p></td>
<td><p><span data-ttu-id="bf5e8-137">Уникальный номер, идентифицирующий этого пользователя, на который ссылается <a href="lync-server-2013-users-table.md">Таблица "Пользователи" в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="bf5e8-137">Unique number identifying this user, referenced from the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bf5e8-138"><strong>фокусусеринстанце</strong></span><span class="sxs-lookup"><span data-stu-id="bf5e8-138"><strong>FocusUserInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="bf5e8-139">целое</span><span class="sxs-lookup"><span data-stu-id="bf5e8-139">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bf5e8-140">Если пользователь входит в систему на нескольких компьютерах или устройствах одновременно, <strong>усеринстанце</strong> используется для уникальной идентификации комбинации пользователей и устройств.</span><span class="sxs-lookup"><span data-stu-id="bf5e8-140">If a user is logged on at multiple computers or devices at the same time, <strong>UserInstance</strong> is used to uniquely identify the user/device combination.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bf5e8-141"><strong>исусеринтернал</strong></span><span class="sxs-lookup"><span data-stu-id="bf5e8-141"><strong>IsUserInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="bf5e8-142">бит</span><span class="sxs-lookup"><span data-stu-id="bf5e8-142">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="bf5e8-143">Вне зависимости от того, вошел ли пользователь из внутреннего или нет.</span><span class="sxs-lookup"><span data-stu-id="bf5e8-143">Whether the user logged on from internal or not.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bf5e8-144"><strong>UserRole</strong></span><span class="sxs-lookup"><span data-stu-id="bf5e8-144"><strong>UserRole</strong></span></span></p></td>
<td><p><span data-ttu-id="bf5e8-145">целое</span><span class="sxs-lookup"><span data-stu-id="bf5e8-145">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="bf5e8-146">Роль этого пользователя на Конференции, например докладчика или участника.</span><span class="sxs-lookup"><span data-stu-id="bf5e8-146">This user’s role in the conference, such as Presenter or Attendee.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bf5e8-147"><strong>усержоинтиме</strong></span><span class="sxs-lookup"><span data-stu-id="bf5e8-147"><strong>UserJoinTime</strong></span></span></p></td>
<td><p><span data-ttu-id="bf5e8-148">datetime</span><span class="sxs-lookup"><span data-stu-id="bf5e8-148">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="bf5e8-149">Время присоединения пользователя к Конференции.</span><span class="sxs-lookup"><span data-stu-id="bf5e8-149">The time this user joins the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bf5e8-150"><strong>усерлеаветиме</strong></span><span class="sxs-lookup"><span data-stu-id="bf5e8-150"><strong>UserLeaveTime</strong></span></span></p></td>
<td><p><span data-ttu-id="bf5e8-151">datetime</span><span class="sxs-lookup"><span data-stu-id="bf5e8-151">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="bf5e8-152">Время, когда пользователь покидает Конференцию.</span><span class="sxs-lookup"><span data-stu-id="bf5e8-152">The time this user leaves the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bf5e8-153"><strong>клиентверид</strong></span><span class="sxs-lookup"><span data-stu-id="bf5e8-153"><strong>ClientVerId</strong></span></span></p></td>
<td><p><span data-ttu-id="bf5e8-154">целое</span><span class="sxs-lookup"><span data-stu-id="bf5e8-154">int</span></span></p></td>
<td><p><span data-ttu-id="bf5e8-155">Другом</span><span class="sxs-lookup"><span data-stu-id="bf5e8-155">Foreign</span></span></p></td>
<td><p><span data-ttu-id="bf5e8-156">Версия клиентского программного обеспечения пользователя, на которую ссылается <a href="lync-server-2013-clientversions-table.md">Таблица клиентверсионс в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="bf5e8-156">Version of the user’s client software, referenced to the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bf5e8-157"><strong>усерендпоинтид</strong></span><span class="sxs-lookup"><span data-stu-id="bf5e8-157"><strong>UserEndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="bf5e8-158">Идентификатора</span><span class="sxs-lookup"><span data-stu-id="bf5e8-158">uniqueIdentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bf5e8-159">Глобальный уникальный идентификатор (GUID) конечной точки, используемой в Конференции.</span><span class="sxs-lookup"><span data-stu-id="bf5e8-159">Globally unique identifier (GUID) of the endpoint used in the conference.</span></span></p>
<p><span data-ttu-id="bf5e8-160">Это поле было введено в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="bf5e8-160">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

