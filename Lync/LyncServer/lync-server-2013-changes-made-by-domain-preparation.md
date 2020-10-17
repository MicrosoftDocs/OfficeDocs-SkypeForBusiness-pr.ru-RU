---
title: 'Lync Server 2013: изменения, внесенные при подготовке домена'
description: 'Lync Server 2013: изменения, внесенные при подготовке домена.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Changes made by domain preparation
ms:assetid: 9191221e-6166-4c2b-837e-fa73d90fdf80
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398742(v=OCS.15)
ms:contentKeyID: 48184845
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 26400bd1c72c6ae3b8dc1f2d2d8f6c6906b80595
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543695"
---
# <a name="changes-made-by-domain-preparation-in-lync-server-2013"></a><span data-ttu-id="49e78-103">Изменения, внесенные при подготовке домена в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="49e78-103">Changes made by domain preparation in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="49e78-104">_**Последнее изменение темы:** 2010-10-18_</span><span class="sxs-lookup"><span data-stu-id="49e78-104">_**Topic Last Modified:** 2010-10-18_</span></span>

<span data-ttu-id="49e78-p101">В следующей таблице перечислены записи управления доступом (ACE), которые создаются при подготовке домена в корневом домене. Все записи ACE наследуются, если не указано иное.</span><span class="sxs-lookup"><span data-stu-id="49e78-p101">The following table lists the access control entries (ACEs) that domain preparation creates on the domain root. All ACEs are inherited unless otherwise noted.</span></span>

<div id="sectionSection0" class="section">

### <a name="aces-added-to-domain-root"></a><span data-ttu-id="49e78-107">Записи ACE, добавленные в корневой домен</span><span class="sxs-lookup"><span data-stu-id="49e78-107">ACEs Added to Domain Root</span></span>

<table style="width:100%;">
<colgroup>
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="49e78-108">ACE</span><span class="sxs-lookup"><span data-stu-id="49e78-108">ACE</span></span></th>
<th><span data-ttu-id="49e78-109">Рткуниверсал — Усерреадонли — группа</span><span class="sxs-lookup"><span data-stu-id="49e78-109">RTCUniversal-UserReadOnly-Group</span></span></th>
<th><span data-ttu-id="49e78-110">Рткуниверсал — Серверреадонли — группа</span><span class="sxs-lookup"><span data-stu-id="49e78-110">RTCUniversal-ServerReadOnly-Group</span></span></th>
<th><span data-ttu-id="49e78-111">RTCUniversal-UserAdmins</span><span class="sxs-lookup"><span data-stu-id="49e78-111">RTCUniversal-UserAdmins</span></span></th>
<th><span data-ttu-id="49e78-112">RTCHSUniversal-Services</span><span class="sxs-lookup"><span data-stu-id="49e78-112">RTCHSUniversal-Services</span></span></th>
<th><span data-ttu-id="49e78-113">Authenticated-Users</span><span class="sxs-lookup"><span data-stu-id="49e78-113">Authenticated-Users</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="49e78-114">Чтение контейнера (не наследуется)</span><span class="sxs-lookup"><span data-stu-id="49e78-114">Read Container (not inherited)</span></span></p></td>
<td><p><span data-ttu-id="49e78-115"><strong>Да</strong></span><span class="sxs-lookup"><span data-stu-id="49e78-115"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="49e78-116"><strong>Да</strong></span><span class="sxs-lookup"><span data-stu-id="49e78-116"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="49e78-117">Нет</span><span class="sxs-lookup"><span data-stu-id="49e78-117">No</span></span></p></td>
<td><p><span data-ttu-id="49e78-118">Нет</span><span class="sxs-lookup"><span data-stu-id="49e78-118">No</span></span></p></td>
<td><p><span data-ttu-id="49e78-119">Нет</span><span class="sxs-lookup"><span data-stu-id="49e78-119">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="49e78-120">Чтение User PropertySet User-Account-Restrictions</span><span class="sxs-lookup"><span data-stu-id="49e78-120">Read User PropertySet User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="49e78-121"><strong>Да</strong></span><span class="sxs-lookup"><span data-stu-id="49e78-121"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="49e78-122">Нет</span><span class="sxs-lookup"><span data-stu-id="49e78-122">No</span></span></p></td>
<td><p><span data-ttu-id="49e78-123">Нет</span><span class="sxs-lookup"><span data-stu-id="49e78-123">No</span></span></p></td>
<td><p><span data-ttu-id="49e78-124">Нет</span><span class="sxs-lookup"><span data-stu-id="49e78-124">No</span></span></p></td>
<td><p><span data-ttu-id="49e78-125">Нет</span><span class="sxs-lookup"><span data-stu-id="49e78-125">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="49e78-126">Чтение User PropertySet Personal-Information</span><span class="sxs-lookup"><span data-stu-id="49e78-126">Read User PropertySet Personal-Information</span></span></p></td>
<td><p><span data-ttu-id="49e78-127"><strong>Да</strong></span><span class="sxs-lookup"><span data-stu-id="49e78-127"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="49e78-128">Нет</span><span class="sxs-lookup"><span data-stu-id="49e78-128">No</span></span></p></td>
<td><p><span data-ttu-id="49e78-129">Нет</span><span class="sxs-lookup"><span data-stu-id="49e78-129">No</span></span></p></td>
<td><p><span data-ttu-id="49e78-130">Нет</span><span class="sxs-lookup"><span data-stu-id="49e78-130">No</span></span></p></td>
<td><p><span data-ttu-id="49e78-131">Нет</span><span class="sxs-lookup"><span data-stu-id="49e78-131">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="49e78-132">Чтение User PropertySet General-Information</span><span class="sxs-lookup"><span data-stu-id="49e78-132">Read User PropertySet General-Information</span></span></p></td>
<td><p><span data-ttu-id="49e78-133"><strong>Да</strong></span><span class="sxs-lookup"><span data-stu-id="49e78-133"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="49e78-134">Нет</span><span class="sxs-lookup"><span data-stu-id="49e78-134">No</span></span></p></td>
<td><p><span data-ttu-id="49e78-135">Нет</span><span class="sxs-lookup"><span data-stu-id="49e78-135">No</span></span></p></td>
<td><p><span data-ttu-id="49e78-136">Нет</span><span class="sxs-lookup"><span data-stu-id="49e78-136">No</span></span></p></td>
<td><p><span data-ttu-id="49e78-137">Нет</span><span class="sxs-lookup"><span data-stu-id="49e78-137">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="49e78-138">Чтение User PropertySet Public-Information</span><span class="sxs-lookup"><span data-stu-id="49e78-138">Read User PropertySet Public-Information</span></span></p></td>
<td><p><span data-ttu-id="49e78-139"><strong>Да</strong></span><span class="sxs-lookup"><span data-stu-id="49e78-139"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="49e78-140">Нет</span><span class="sxs-lookup"><span data-stu-id="49e78-140">No</span></span></p></td>
<td><p><span data-ttu-id="49e78-141">Нет</span><span class="sxs-lookup"><span data-stu-id="49e78-141">No</span></span></p></td>
<td><p><span data-ttu-id="49e78-142">Нет</span><span class="sxs-lookup"><span data-stu-id="49e78-142">No</span></span></p></td>
<td><p><span data-ttu-id="49e78-143">Нет</span><span class="sxs-lookup"><span data-stu-id="49e78-143">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="49e78-144">Чтение User PropertySet RTCUserSearchProperty-Set</span><span class="sxs-lookup"><span data-stu-id="49e78-144">Read User PropertySet RTCUserSearchProperty-Set</span></span></p></td>
<td><p><span data-ttu-id="49e78-145"><strong>Да</strong></span><span class="sxs-lookup"><span data-stu-id="49e78-145"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="49e78-146">Нет</span><span class="sxs-lookup"><span data-stu-id="49e78-146">No</span></span></p></td>
<td><p><span data-ttu-id="49e78-147">Нет</span><span class="sxs-lookup"><span data-stu-id="49e78-147">No</span></span></p></td>
<td><p><span data-ttu-id="49e78-148">Нет</span><span class="sxs-lookup"><span data-stu-id="49e78-148">No</span></span></p></td>
<td><p><span data-ttu-id="49e78-149"><strong>Да</strong></span><span class="sxs-lookup"><span data-stu-id="49e78-149"><strong>Yes</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="49e78-150">Чтение User PropertySet RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="49e78-150">Read User PropertySet RTCPropertySet</span></span></p></td>
<td><p><span data-ttu-id="49e78-151"><strong>Да</strong></span><span class="sxs-lookup"><span data-stu-id="49e78-151"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="49e78-152">Нет</span><span class="sxs-lookup"><span data-stu-id="49e78-152">No</span></span></p></td>
<td><p><span data-ttu-id="49e78-153">Нет</span><span class="sxs-lookup"><span data-stu-id="49e78-153">No</span></span></p></td>
<td><p><span data-ttu-id="49e78-154">Нет</span><span class="sxs-lookup"><span data-stu-id="49e78-154">No</span></span></p></td>
<td><p><span data-ttu-id="49e78-155">Нет</span><span class="sxs-lookup"><span data-stu-id="49e78-155">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="49e78-156">Запись User Property Proxy-Addresses</span><span class="sxs-lookup"><span data-stu-id="49e78-156">Write User Property Proxy-Addresses</span></span></p></td>
<td><p><span data-ttu-id="49e78-157">Нет</span><span class="sxs-lookup"><span data-stu-id="49e78-157">No</span></span></p></td>
<td><p><span data-ttu-id="49e78-158">Нет</span><span class="sxs-lookup"><span data-stu-id="49e78-158">No</span></span></p></td>
<td><p><span data-ttu-id="49e78-159"><strong>Да</strong></span><span class="sxs-lookup"><span data-stu-id="49e78-159"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="49e78-160">Нет</span><span class="sxs-lookup"><span data-stu-id="49e78-160">No</span></span></p></td>
<td><p><span data-ttu-id="49e78-161">Нет</span><span class="sxs-lookup"><span data-stu-id="49e78-161">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="49e78-162">Запись User PropertySet RTCUserSearchProperty-Set</span><span class="sxs-lookup"><span data-stu-id="49e78-162">Write User PropertySet RTCUserSearchProperty-Set</span></span></p></td>
<td><p><span data-ttu-id="49e78-163">Нет</span><span class="sxs-lookup"><span data-stu-id="49e78-163">No</span></span></p></td>
<td><p><span data-ttu-id="49e78-164">Нет</span><span class="sxs-lookup"><span data-stu-id="49e78-164">No</span></span></p></td>
<td><p><span data-ttu-id="49e78-165"><strong>Да</strong></span><span class="sxs-lookup"><span data-stu-id="49e78-165"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="49e78-166">Нет</span><span class="sxs-lookup"><span data-stu-id="49e78-166">No</span></span></p></td>
<td><p><span data-ttu-id="49e78-167">Нет</span><span class="sxs-lookup"><span data-stu-id="49e78-167">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="49e78-168">Запись User PropertySet RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="49e78-168">Write User PropertySet RTCPropertySet</span></span></p></td>
<td><p><span data-ttu-id="49e78-169">Нет</span><span class="sxs-lookup"><span data-stu-id="49e78-169">No</span></span></p></td>
<td><p><span data-ttu-id="49e78-170">Нет</span><span class="sxs-lookup"><span data-stu-id="49e78-170">No</span></span></p></td>
<td><p><span data-ttu-id="49e78-171"><strong>Да</strong></span><span class="sxs-lookup"><span data-stu-id="49e78-171"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="49e78-172">Нет</span><span class="sxs-lookup"><span data-stu-id="49e78-172">No</span></span></p></td>
<td><p><span data-ttu-id="49e78-173">Нет</span><span class="sxs-lookup"><span data-stu-id="49e78-173">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="49e78-174">Чтение PropertySet DS-Replication-Get-Changes всех объектов Active Directory</span><span class="sxs-lookup"><span data-stu-id="49e78-174">Read PropertySet DS-Replication-Get-Changes of all Active Directory objects</span></span></p></td>
<td><p><span data-ttu-id="49e78-175">Нет</span><span class="sxs-lookup"><span data-stu-id="49e78-175">No</span></span></p></td>
<td><p><span data-ttu-id="49e78-176">Нет</span><span class="sxs-lookup"><span data-stu-id="49e78-176">No</span></span></p></td>
<td><p><span data-ttu-id="49e78-177">Нет</span><span class="sxs-lookup"><span data-stu-id="49e78-177">No</span></span></p></td>
<td><p><span data-ttu-id="49e78-178"><strong>Да</strong></span><span class="sxs-lookup"><span data-stu-id="49e78-178"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="49e78-179">Нет</span><span class="sxs-lookup"><span data-stu-id="49e78-179">No</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="49e78-p102">В следующей таблице перечислены записи управления доступом (ACE), которые создаются при подготовке домена в трех встроенных контейнерах: «Пользователи», «Компьютеры», «Контроллеры доменов». Все записи ACE наследуются, если не указано иное.</span><span class="sxs-lookup"><span data-stu-id="49e78-p102">The following table lists the ACEs that domain preparation creates in the three built-in containers: Users, Computers, and Domain Controllers. All ACEs are inherited unless otherwise noted.</span></span>

### <a name="aces-added-to-built-in-containers"></a><span data-ttu-id="49e78-182">Записи ACE, добавленные во встроенные контейнеры</span><span class="sxs-lookup"><span data-stu-id="49e78-182">ACEs Added to Built-in Containers</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="49e78-183">ACE</span><span class="sxs-lookup"><span data-stu-id="49e78-183">ACE</span></span></th>
<th><span data-ttu-id="49e78-184">Рткуниверсал — Усерреадонли — группа</span><span class="sxs-lookup"><span data-stu-id="49e78-184">RTCUniversal-UserReadOnly-Group</span></span></th>
<th><span data-ttu-id="49e78-185">Рткуниверсал — Серверреадонли — группа</span><span class="sxs-lookup"><span data-stu-id="49e78-185">RTCUniversal-ServerReadOnly-Group</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="49e78-186">Чтение контейнера (не наследуется)</span><span class="sxs-lookup"><span data-stu-id="49e78-186">Read Container (not inherited)</span></span></p></td>
<td><p><span data-ttu-id="49e78-187"><strong>Да</strong></span><span class="sxs-lookup"><span data-stu-id="49e78-187"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="49e78-188"><strong>Да</strong></span><span class="sxs-lookup"><span data-stu-id="49e78-188"><strong>Yes</strong></span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

