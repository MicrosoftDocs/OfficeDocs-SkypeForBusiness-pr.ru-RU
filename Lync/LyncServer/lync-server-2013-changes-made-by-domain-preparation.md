---
title: 'Lync Server 2013: изменения, внесенные при подготовке домена'
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
ms.openlocfilehash: 3e02224636b3e5179a8834e5dd59c0218956e6eb
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151049"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="changes-made-by-domain-preparation-in-lync-server-2013"></a><span data-ttu-id="d99b8-102">Изменения, внесенные при подготовке домена в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d99b8-102">Changes made by domain preparation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d99b8-103">_**Последнее изменение темы:** 2010-10-18_</span><span class="sxs-lookup"><span data-stu-id="d99b8-103">_**Topic Last Modified:** 2010-10-18_</span></span>

<span data-ttu-id="d99b8-p101">В следующей таблице перечислены записи управления доступом (ACE), которые создаются при подготовке домена в корневом домене. Все записи ACE наследуются, если не указано иное.</span><span class="sxs-lookup"><span data-stu-id="d99b8-p101">The following table lists the access control entries (ACEs) that domain preparation creates on the domain root. All ACEs are inherited unless otherwise noted.</span></span>

<div id="sectionSection0" class="section">

### <a name="aces-added-to-domain-root"></a><span data-ttu-id="d99b8-106">Записи ACE, добавленные в корневой домен</span><span class="sxs-lookup"><span data-stu-id="d99b8-106">ACEs Added to Domain Root</span></span>

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
<th><span data-ttu-id="d99b8-107">ACE</span><span class="sxs-lookup"><span data-stu-id="d99b8-107">ACE</span></span></th>
<th><span data-ttu-id="d99b8-108">Рткуниверсал — Усерреадонли — группа</span><span class="sxs-lookup"><span data-stu-id="d99b8-108">RTCUniversal-UserReadOnly-Group</span></span></th>
<th><span data-ttu-id="d99b8-109">Рткуниверсал — Серверреадонли — группа</span><span class="sxs-lookup"><span data-stu-id="d99b8-109">RTCUniversal-ServerReadOnly-Group</span></span></th>
<th><span data-ttu-id="d99b8-110">Рткуниверсал — Усерадминс</span><span class="sxs-lookup"><span data-stu-id="d99b8-110">RTCUniversal-UserAdmins</span></span></th>
<th><span data-ttu-id="d99b8-111">Ртчсуниверсал — службы</span><span class="sxs-lookup"><span data-stu-id="d99b8-111">RTCHSUniversal-Services</span></span></th>
<th><span data-ttu-id="d99b8-112">Прошедшие проверку — пользователи</span><span class="sxs-lookup"><span data-stu-id="d99b8-112">Authenticated-Users</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d99b8-113">Чтение контейнера (не наследуется)</span><span class="sxs-lookup"><span data-stu-id="d99b8-113">Read Container (not inherited)</span></span></p></td>
<td><p><span data-ttu-id="d99b8-114"><strong>Да</strong></span><span class="sxs-lookup"><span data-stu-id="d99b8-114"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="d99b8-115"><strong>Да</strong></span><span class="sxs-lookup"><span data-stu-id="d99b8-115"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="d99b8-116">Нет</span><span class="sxs-lookup"><span data-stu-id="d99b8-116">No</span></span></p></td>
<td><p><span data-ttu-id="d99b8-117">Нет</span><span class="sxs-lookup"><span data-stu-id="d99b8-117">No</span></span></p></td>
<td><p><span data-ttu-id="d99b8-118">Нет</span><span class="sxs-lookup"><span data-stu-id="d99b8-118">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d99b8-119">Чтение User PropertySet User-Account-Restrictions</span><span class="sxs-lookup"><span data-stu-id="d99b8-119">Read User PropertySet User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="d99b8-120"><strong>Да</strong></span><span class="sxs-lookup"><span data-stu-id="d99b8-120"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="d99b8-121">Нет</span><span class="sxs-lookup"><span data-stu-id="d99b8-121">No</span></span></p></td>
<td><p><span data-ttu-id="d99b8-122">Нет</span><span class="sxs-lookup"><span data-stu-id="d99b8-122">No</span></span></p></td>
<td><p><span data-ttu-id="d99b8-123">Нет</span><span class="sxs-lookup"><span data-stu-id="d99b8-123">No</span></span></p></td>
<td><p><span data-ttu-id="d99b8-124">Нет</span><span class="sxs-lookup"><span data-stu-id="d99b8-124">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d99b8-125">Чтение User PropertySet Personal-Information</span><span class="sxs-lookup"><span data-stu-id="d99b8-125">Read User PropertySet Personal-Information</span></span></p></td>
<td><p><span data-ttu-id="d99b8-126"><strong>Да</strong></span><span class="sxs-lookup"><span data-stu-id="d99b8-126"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="d99b8-127">Нет</span><span class="sxs-lookup"><span data-stu-id="d99b8-127">No</span></span></p></td>
<td><p><span data-ttu-id="d99b8-128">Нет</span><span class="sxs-lookup"><span data-stu-id="d99b8-128">No</span></span></p></td>
<td><p><span data-ttu-id="d99b8-129">Нет</span><span class="sxs-lookup"><span data-stu-id="d99b8-129">No</span></span></p></td>
<td><p><span data-ttu-id="d99b8-130">Нет</span><span class="sxs-lookup"><span data-stu-id="d99b8-130">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d99b8-131">Чтение User PropertySet General-Information</span><span class="sxs-lookup"><span data-stu-id="d99b8-131">Read User PropertySet General-Information</span></span></p></td>
<td><p><span data-ttu-id="d99b8-132"><strong>Да</strong></span><span class="sxs-lookup"><span data-stu-id="d99b8-132"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="d99b8-133">Нет</span><span class="sxs-lookup"><span data-stu-id="d99b8-133">No</span></span></p></td>
<td><p><span data-ttu-id="d99b8-134">Нет</span><span class="sxs-lookup"><span data-stu-id="d99b8-134">No</span></span></p></td>
<td><p><span data-ttu-id="d99b8-135">Нет</span><span class="sxs-lookup"><span data-stu-id="d99b8-135">No</span></span></p></td>
<td><p><span data-ttu-id="d99b8-136">Нет</span><span class="sxs-lookup"><span data-stu-id="d99b8-136">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d99b8-137">Чтение User PropertySet Public-Information</span><span class="sxs-lookup"><span data-stu-id="d99b8-137">Read User PropertySet Public-Information</span></span></p></td>
<td><p><span data-ttu-id="d99b8-138"><strong>Да</strong></span><span class="sxs-lookup"><span data-stu-id="d99b8-138"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="d99b8-139">Нет</span><span class="sxs-lookup"><span data-stu-id="d99b8-139">No</span></span></p></td>
<td><p><span data-ttu-id="d99b8-140">Нет</span><span class="sxs-lookup"><span data-stu-id="d99b8-140">No</span></span></p></td>
<td><p><span data-ttu-id="d99b8-141">Нет</span><span class="sxs-lookup"><span data-stu-id="d99b8-141">No</span></span></p></td>
<td><p><span data-ttu-id="d99b8-142">Нет</span><span class="sxs-lookup"><span data-stu-id="d99b8-142">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d99b8-143">Чтение User PropertySet RTCUserSearchProperty-Set</span><span class="sxs-lookup"><span data-stu-id="d99b8-143">Read User PropertySet RTCUserSearchProperty-Set</span></span></p></td>
<td><p><span data-ttu-id="d99b8-144"><strong>Да</strong></span><span class="sxs-lookup"><span data-stu-id="d99b8-144"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="d99b8-145">Нет</span><span class="sxs-lookup"><span data-stu-id="d99b8-145">No</span></span></p></td>
<td><p><span data-ttu-id="d99b8-146">Нет</span><span class="sxs-lookup"><span data-stu-id="d99b8-146">No</span></span></p></td>
<td><p><span data-ttu-id="d99b8-147">Нет</span><span class="sxs-lookup"><span data-stu-id="d99b8-147">No</span></span></p></td>
<td><p><span data-ttu-id="d99b8-148"><strong>Да</strong></span><span class="sxs-lookup"><span data-stu-id="d99b8-148"><strong>Yes</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d99b8-149">Чтение User PropertySet RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="d99b8-149">Read User PropertySet RTCPropertySet</span></span></p></td>
<td><p><span data-ttu-id="d99b8-150"><strong>Да</strong></span><span class="sxs-lookup"><span data-stu-id="d99b8-150"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="d99b8-151">Нет</span><span class="sxs-lookup"><span data-stu-id="d99b8-151">No</span></span></p></td>
<td><p><span data-ttu-id="d99b8-152">Нет</span><span class="sxs-lookup"><span data-stu-id="d99b8-152">No</span></span></p></td>
<td><p><span data-ttu-id="d99b8-153">Нет</span><span class="sxs-lookup"><span data-stu-id="d99b8-153">No</span></span></p></td>
<td><p><span data-ttu-id="d99b8-154">Нет</span><span class="sxs-lookup"><span data-stu-id="d99b8-154">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d99b8-155">Запись User Property Proxy-Addresses</span><span class="sxs-lookup"><span data-stu-id="d99b8-155">Write User Property Proxy-Addresses</span></span></p></td>
<td><p><span data-ttu-id="d99b8-156">Нет</span><span class="sxs-lookup"><span data-stu-id="d99b8-156">No</span></span></p></td>
<td><p><span data-ttu-id="d99b8-157">Нет</span><span class="sxs-lookup"><span data-stu-id="d99b8-157">No</span></span></p></td>
<td><p><span data-ttu-id="d99b8-158"><strong>Да</strong></span><span class="sxs-lookup"><span data-stu-id="d99b8-158"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="d99b8-159">Нет</span><span class="sxs-lookup"><span data-stu-id="d99b8-159">No</span></span></p></td>
<td><p><span data-ttu-id="d99b8-160">Нет</span><span class="sxs-lookup"><span data-stu-id="d99b8-160">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d99b8-161">Запись User PropertySet RTCUserSearchProperty-Set</span><span class="sxs-lookup"><span data-stu-id="d99b8-161">Write User PropertySet RTCUserSearchProperty-Set</span></span></p></td>
<td><p><span data-ttu-id="d99b8-162">Нет</span><span class="sxs-lookup"><span data-stu-id="d99b8-162">No</span></span></p></td>
<td><p><span data-ttu-id="d99b8-163">Нет</span><span class="sxs-lookup"><span data-stu-id="d99b8-163">No</span></span></p></td>
<td><p><span data-ttu-id="d99b8-164"><strong>Да</strong></span><span class="sxs-lookup"><span data-stu-id="d99b8-164"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="d99b8-165">Нет</span><span class="sxs-lookup"><span data-stu-id="d99b8-165">No</span></span></p></td>
<td><p><span data-ttu-id="d99b8-166">Нет</span><span class="sxs-lookup"><span data-stu-id="d99b8-166">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d99b8-167">Запись User PropertySet RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="d99b8-167">Write User PropertySet RTCPropertySet</span></span></p></td>
<td><p><span data-ttu-id="d99b8-168">Нет</span><span class="sxs-lookup"><span data-stu-id="d99b8-168">No</span></span></p></td>
<td><p><span data-ttu-id="d99b8-169">Нет</span><span class="sxs-lookup"><span data-stu-id="d99b8-169">No</span></span></p></td>
<td><p><span data-ttu-id="d99b8-170"><strong>Да</strong></span><span class="sxs-lookup"><span data-stu-id="d99b8-170"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="d99b8-171">Нет</span><span class="sxs-lookup"><span data-stu-id="d99b8-171">No</span></span></p></td>
<td><p><span data-ttu-id="d99b8-172">Нет</span><span class="sxs-lookup"><span data-stu-id="d99b8-172">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d99b8-173">Чтение PropertySet DS-Replication-Get-Changes всех объектов Active Directory</span><span class="sxs-lookup"><span data-stu-id="d99b8-173">Read PropertySet DS-Replication-Get-Changes of all Active Directory objects</span></span></p></td>
<td><p><span data-ttu-id="d99b8-174">Нет</span><span class="sxs-lookup"><span data-stu-id="d99b8-174">No</span></span></p></td>
<td><p><span data-ttu-id="d99b8-175">Нет</span><span class="sxs-lookup"><span data-stu-id="d99b8-175">No</span></span></p></td>
<td><p><span data-ttu-id="d99b8-176">Нет</span><span class="sxs-lookup"><span data-stu-id="d99b8-176">No</span></span></p></td>
<td><p><span data-ttu-id="d99b8-177"><strong>Да</strong></span><span class="sxs-lookup"><span data-stu-id="d99b8-177"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="d99b8-178">Нет</span><span class="sxs-lookup"><span data-stu-id="d99b8-178">No</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="d99b8-p102">В следующей таблице перечислены записи управления доступом (ACE), которые создаются при подготовке домена в трех встроенных контейнерах: «Пользователи», «Компьютеры», «Контроллеры доменов». Все записи ACE наследуются, если не указано иное.</span><span class="sxs-lookup"><span data-stu-id="d99b8-p102">The following table lists the ACEs that domain preparation creates in the three built-in containers: Users, Computers, and Domain Controllers. All ACEs are inherited unless otherwise noted.</span></span>

### <a name="aces-added-to-built-in-containers"></a><span data-ttu-id="d99b8-181">Записи ACE, добавленные во встроенные контейнеры</span><span class="sxs-lookup"><span data-stu-id="d99b8-181">ACEs Added to Built-in Containers</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d99b8-182">ACE</span><span class="sxs-lookup"><span data-stu-id="d99b8-182">ACE</span></span></th>
<th><span data-ttu-id="d99b8-183">Рткуниверсал — Усерреадонли — группа</span><span class="sxs-lookup"><span data-stu-id="d99b8-183">RTCUniversal-UserReadOnly-Group</span></span></th>
<th><span data-ttu-id="d99b8-184">Рткуниверсал — Серверреадонли — группа</span><span class="sxs-lookup"><span data-stu-id="d99b8-184">RTCUniversal-ServerReadOnly-Group</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d99b8-185">Чтение контейнера (не наследуется)</span><span class="sxs-lookup"><span data-stu-id="d99b8-185">Read Container (not inherited)</span></span></p></td>
<td><p><span data-ttu-id="d99b8-186"><strong>Да</strong></span><span class="sxs-lookup"><span data-stu-id="d99b8-186"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="d99b8-187"><strong>Да</strong></span><span class="sxs-lookup"><span data-stu-id="d99b8-187"><strong>Yes</strong></span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

