---
title: 'Lync Server 2013: таблица таблица focusjoinsandleaves'
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
ms.openlocfilehash: 8e8d37023d30784d07d9ac74ce89aa8cc1fb43a9
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42207315"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="focusjoinsandleaves-table-in-lync-server-2013"></a><span data-ttu-id="7376a-102">Таблица Таблица focusjoinsandleaves в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7376a-102">FocusJoinsAndLeaves table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7376a-103">_**Последнее изменение темы:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="7376a-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="7376a-104">Каждая запись в этой таблице содержит сведения о CDR для одного пользователя и оставляют информацию для одной конференции.</span><span class="sxs-lookup"><span data-stu-id="7376a-104">Each record in this table contains the CDR information about one user’s join and leave information for one conference.</span></span> <span data-ttu-id="7376a-105">Каждая конференция представлена в этой таблице по одной записи на каждый раз, когда пользователь присоединяется к Конференции и покидает ее.</span><span class="sxs-lookup"><span data-stu-id="7376a-105">Each conference is represented in this table by one record for each time a user joins and leaves the conference.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7376a-106">Столбец</span><span class="sxs-lookup"><span data-stu-id="7376a-106">Column</span></span></th>
<th><span data-ttu-id="7376a-107">Тип данных</span><span class="sxs-lookup"><span data-stu-id="7376a-107">Data Type</span></span></th>
<th><span data-ttu-id="7376a-108">Ключ или индекс</span><span class="sxs-lookup"><span data-stu-id="7376a-108">Key/Index</span></span></th>
<th><span data-ttu-id="7376a-109">Сведения</span><span class="sxs-lookup"><span data-stu-id="7376a-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7376a-110"><strong>сессионидтиме</strong></span><span class="sxs-lookup"><span data-stu-id="7376a-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="7376a-111">datetime</span><span class="sxs-lookup"><span data-stu-id="7376a-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="7376a-112">Основной, внешний</span><span class="sxs-lookup"><span data-stu-id="7376a-112">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="7376a-113">Время экземпляра конференции.</span><span class="sxs-lookup"><span data-stu-id="7376a-113">Time of conference instance.</span></span> <span data-ttu-id="7376a-114">Используется совместно с <strong>сессионидсек</strong> для уникальной идентификации экземпляра Конференции.</span><span class="sxs-lookup"><span data-stu-id="7376a-114">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a conference instance.</span></span> <span data-ttu-id="7376a-115">Дополнительные сведения см. <a href="lync-server-2013-conferences-table.md">в таблице конференций в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="7376a-115">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7376a-116"><strong>сессионидсек</strong></span><span class="sxs-lookup"><span data-stu-id="7376a-116"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="7376a-117">int</span><span class="sxs-lookup"><span data-stu-id="7376a-117">int</span></span></p></td>
<td><p><span data-ttu-id="7376a-118">Основной, Внешний</span><span class="sxs-lookup"><span data-stu-id="7376a-118">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="7376a-119">Идентификатор для определения экземпляра конференции.</span><span class="sxs-lookup"><span data-stu-id="7376a-119">ID number to identify the conference instance.</span></span> <span data-ttu-id="7376a-120">Используется совместно с <strong>сессионидтиме</strong> для уникальной идентификации экземпляра Конференции.</span><span class="sxs-lookup"><span data-stu-id="7376a-120">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a conference instance.</span></span> <span data-ttu-id="7376a-121">Дополнительные сведения см. <a href="lync-server-2013-conferences-table.md">в таблице конференций в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="7376a-121">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7376a-122"><strong>диалогсессионидтиме</strong></span><span class="sxs-lookup"><span data-stu-id="7376a-122"><strong>DialogSessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="7376a-123">datetime</span><span class="sxs-lookup"><span data-stu-id="7376a-123">datetime</span></span></p></td>
<td><p><span data-ttu-id="7376a-124">Основной, внешний</span><span class="sxs-lookup"><span data-stu-id="7376a-124">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="7376a-125">Время запроса сеанса.</span><span class="sxs-lookup"><span data-stu-id="7376a-125">Time of session request.</span></span> <span data-ttu-id="7376a-126">В сочетании с параметром <strong>SessionIdSeq</strong> определяет сеанс уникальным образом.</span><span class="sxs-lookup"><span data-stu-id="7376a-126">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="7376a-127">Дополнительные сведения см. <a href="lync-server-2013-dialogs-table.md">в таблице диалоговых окон в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="7376a-127">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7376a-128"><strong>диалогсессионидсек</strong></span><span class="sxs-lookup"><span data-stu-id="7376a-128"><strong>DialogSessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="7376a-129">int</span><span class="sxs-lookup"><span data-stu-id="7376a-129">int</span></span></p></td>
<td><p><span data-ttu-id="7376a-130">Первичный, внешний</span><span class="sxs-lookup"><span data-stu-id="7376a-130">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="7376a-131">Идентификатор для идентификации сеанса.</span><span class="sxs-lookup"><span data-stu-id="7376a-131">ID number to identify the session.</span></span> <span data-ttu-id="7376a-132">В сочетании с параметром <strong>SessionIdTime</strong> определяет сеанс уникальным образом.</span><span class="sxs-lookup"><span data-stu-id="7376a-132">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="7376a-133">Дополнительные сведения см. <a href="lync-server-2013-dialogs-table.md">в таблице диалоговых окон в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="7376a-133">see the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7376a-134"><strong>UserId</strong></span><span class="sxs-lookup"><span data-stu-id="7376a-134"><strong>UserId</strong></span></span></p></td>
<td><p><span data-ttu-id="7376a-135">int</span><span class="sxs-lookup"><span data-stu-id="7376a-135">int</span></span></p></td>
<td><p><span data-ttu-id="7376a-136">Правительства</span><span class="sxs-lookup"><span data-stu-id="7376a-136">Foreign</span></span></p></td>
<td><p><span data-ttu-id="7376a-137">Уникальный номер, идентифицирующий этого пользователя, на который ссылается <a href="lync-server-2013-users-table.md">таблица Users в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="7376a-137">Unique number identifying this user, referenced from the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7376a-138"><strong>фокусусеринстанце</strong></span><span class="sxs-lookup"><span data-stu-id="7376a-138"><strong>FocusUserInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="7376a-139">int</span><span class="sxs-lookup"><span data-stu-id="7376a-139">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7376a-140">Если пользователь вошел в систему на нескольких компьютерах или устройствах одновременно, <strong>усеринстанце</strong> используется для уникальной идентификации комбинации "пользователь-устройство".</span><span class="sxs-lookup"><span data-stu-id="7376a-140">If a user is logged on at multiple computers or devices at the same time, <strong>UserInstance</strong> is used to uniquely identify the user/device combination.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7376a-141"><strong>исусеринтернал</strong></span><span class="sxs-lookup"><span data-stu-id="7376a-141"><strong>IsUserInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="7376a-142">Битовая</span><span class="sxs-lookup"><span data-stu-id="7376a-142">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="7376a-143">Указывает, вошел ли пользователь из внутренней сети или нет.</span><span class="sxs-lookup"><span data-stu-id="7376a-143">Whether the user logged on from internal or not.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7376a-144"><strong>UserRole</strong></span><span class="sxs-lookup"><span data-stu-id="7376a-144"><strong>UserRole</strong></span></span></p></td>
<td><p><span data-ttu-id="7376a-145">int</span><span class="sxs-lookup"><span data-stu-id="7376a-145">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="7376a-146">Роль этого пользователя в конференции, например докладчик или участник.</span><span class="sxs-lookup"><span data-stu-id="7376a-146">This user’s role in the conference, such as Presenter or Attendee.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7376a-147"><strong>усержоинтиме</strong></span><span class="sxs-lookup"><span data-stu-id="7376a-147"><strong>UserJoinTime</strong></span></span></p></td>
<td><p><span data-ttu-id="7376a-148">datetime</span><span class="sxs-lookup"><span data-stu-id="7376a-148">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="7376a-149">Время, когда этот пользователь присоединяется к Конференции.</span><span class="sxs-lookup"><span data-stu-id="7376a-149">The time this user joins the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7376a-150"><strong>усерлеаветиме</strong></span><span class="sxs-lookup"><span data-stu-id="7376a-150"><strong>UserLeaveTime</strong></span></span></p></td>
<td><p><span data-ttu-id="7376a-151">datetime</span><span class="sxs-lookup"><span data-stu-id="7376a-151">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="7376a-152">Время, когда этот пользователь покидает Конференцию.</span><span class="sxs-lookup"><span data-stu-id="7376a-152">The time this user leaves the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7376a-153"><strong>клиентверид</strong></span><span class="sxs-lookup"><span data-stu-id="7376a-153"><strong>ClientVerId</strong></span></span></p></td>
<td><p><span data-ttu-id="7376a-154">int</span><span class="sxs-lookup"><span data-stu-id="7376a-154">int</span></span></p></td>
<td><p><span data-ttu-id="7376a-155">Правительства</span><span class="sxs-lookup"><span data-stu-id="7376a-155">Foreign</span></span></p></td>
<td><p><span data-ttu-id="7376a-156">Версия клиентского программного обеспечения пользователя, на которую ссылается <a href="lync-server-2013-clientversions-table.md">таблица таблица clientversions в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="7376a-156">Version of the user’s client software, referenced to the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7376a-157"><strong>усерендпоинтид</strong></span><span class="sxs-lookup"><span data-stu-id="7376a-157"><strong>UserEndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="7376a-158">Идентификатора</span><span class="sxs-lookup"><span data-stu-id="7376a-158">uniqueIdentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7376a-159">Глобальный уникальный идентификатор (GUID) конечной точки, используемой в Конференции.</span><span class="sxs-lookup"><span data-stu-id="7376a-159">Globally unique identifier (GUID) of the endpoint used in the conference.</span></span></p>
<p><span data-ttu-id="7376a-160">Это поле было введено в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7376a-160">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

