---
title: 'Lync Server 2013: изменения, внесенные с помощью подготовки домена'
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
ms.openlocfilehash: cbdd1fa1fbb5bd7a396e17f478326a9e4dd700f8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730109"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="changes-made-by-domain-preparation-in-lync-server-2013"></a><span data-ttu-id="12fa4-102">Изменения, внесенные в ходе подготовки домена в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="12fa4-102">Changes made by domain preparation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="12fa4-103">_**Тема последнего изменения:** 2010-10-18_</span><span class="sxs-lookup"><span data-stu-id="12fa4-103">_**Topic Last Modified:** 2010-10-18_</span></span>

<span data-ttu-id="12fa4-104">В следующей таблице перечислены записи управления доступом (ACE), которые подготовка домена создает в корне домена.</span><span class="sxs-lookup"><span data-stu-id="12fa4-104">The following table lists the access control entries (ACEs) that domain preparation creates on the domain root.</span></span> <span data-ttu-id="12fa4-105">Все ACE наследуются, если не указано иное.</span><span class="sxs-lookup"><span data-stu-id="12fa4-105">All ACEs are inherited unless otherwise noted.</span></span>

<div id="sectionSection0" class="section">

### <a name="aces-added-to-domain-root"></a><span data-ttu-id="12fa4-106">ACE, добавленные в корень домена</span><span class="sxs-lookup"><span data-stu-id="12fa4-106">ACEs Added to Domain Root</span></span>

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
<th><span data-ttu-id="12fa4-107">РЕЗУЛЬТИРУЮЩ</span><span class="sxs-lookup"><span data-stu-id="12fa4-107">ACE</span></span></th>
<th><span data-ttu-id="12fa4-108">Рткуниверсал — Усерреадонли-Group</span><span class="sxs-lookup"><span data-stu-id="12fa4-108">RTCUniversal-UserReadOnly-Group</span></span></th>
<th><span data-ttu-id="12fa4-109">Рткуниверсал — Серверреадонли-Group</span><span class="sxs-lookup"><span data-stu-id="12fa4-109">RTCUniversal-ServerReadOnly-Group</span></span></th>
<th><span data-ttu-id="12fa4-110">Рткуниверсал-Усерадминс</span><span class="sxs-lookup"><span data-stu-id="12fa4-110">RTCUniversal-UserAdmins</span></span></th>
<th><span data-ttu-id="12fa4-111">Ртчсуниверсал — службы</span><span class="sxs-lookup"><span data-stu-id="12fa4-111">RTCHSUniversal-Services</span></span></th>
<th><span data-ttu-id="12fa4-112">Прошедшие проверку — пользователи</span><span class="sxs-lookup"><span data-stu-id="12fa4-112">Authenticated-Users</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="12fa4-113">Прочитать контейнер (не наследуется)</span><span class="sxs-lookup"><span data-stu-id="12fa4-113">Read Container (not inherited)</span></span></p></td>
<td><p><span data-ttu-id="12fa4-114"><strong>Кнопки</strong></span><span class="sxs-lookup"><span data-stu-id="12fa4-114"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="12fa4-115"><strong>Да</strong></span><span class="sxs-lookup"><span data-stu-id="12fa4-115"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="12fa4-116">Нет</span><span class="sxs-lookup"><span data-stu-id="12fa4-116">No</span></span></p></td>
<td><p><span data-ttu-id="12fa4-117">Нет</span><span class="sxs-lookup"><span data-stu-id="12fa4-117">No</span></span></p></td>
<td><p><span data-ttu-id="12fa4-118">Нет</span><span class="sxs-lookup"><span data-stu-id="12fa4-118">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="12fa4-119">Чтение пользовательских свойств в пользовательском интерфейсе — ограничения для учетных записей</span><span class="sxs-lookup"><span data-stu-id="12fa4-119">Read User PropertySet User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="12fa4-120"><strong>Да</strong></span><span class="sxs-lookup"><span data-stu-id="12fa4-120"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="12fa4-121">Нет</span><span class="sxs-lookup"><span data-stu-id="12fa4-121">No</span></span></p></td>
<td><p><span data-ttu-id="12fa4-122">Нет</span><span class="sxs-lookup"><span data-stu-id="12fa4-122">No</span></span></p></td>
<td><p><span data-ttu-id="12fa4-123">Нет</span><span class="sxs-lookup"><span data-stu-id="12fa4-123">No</span></span></p></td>
<td><p><span data-ttu-id="12fa4-124">Нет</span><span class="sxs-lookup"><span data-stu-id="12fa4-124">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="12fa4-125">Чтение личных сведений о пользовательском свойстве</span><span class="sxs-lookup"><span data-stu-id="12fa4-125">Read User PropertySet Personal-Information</span></span></p></td>
<td><p><span data-ttu-id="12fa4-126"><strong>Да</strong></span><span class="sxs-lookup"><span data-stu-id="12fa4-126"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="12fa4-127">Нет</span><span class="sxs-lookup"><span data-stu-id="12fa4-127">No</span></span></p></td>
<td><p><span data-ttu-id="12fa4-128">Нет</span><span class="sxs-lookup"><span data-stu-id="12fa4-128">No</span></span></p></td>
<td><p><span data-ttu-id="12fa4-129">Нет</span><span class="sxs-lookup"><span data-stu-id="12fa4-129">No</span></span></p></td>
<td><p><span data-ttu-id="12fa4-130">Нет</span><span class="sxs-lookup"><span data-stu-id="12fa4-130">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="12fa4-131">Чтение общих сведений о пользовательском свойстве</span><span class="sxs-lookup"><span data-stu-id="12fa4-131">Read User PropertySet General-Information</span></span></p></td>
<td><p><span data-ttu-id="12fa4-132"><strong>Да</strong></span><span class="sxs-lookup"><span data-stu-id="12fa4-132"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="12fa4-133">Нет</span><span class="sxs-lookup"><span data-stu-id="12fa4-133">No</span></span></p></td>
<td><p><span data-ttu-id="12fa4-134">Нет</span><span class="sxs-lookup"><span data-stu-id="12fa4-134">No</span></span></p></td>
<td><p><span data-ttu-id="12fa4-135">Нет</span><span class="sxs-lookup"><span data-stu-id="12fa4-135">No</span></span></p></td>
<td><p><span data-ttu-id="12fa4-136">Нет</span><span class="sxs-lookup"><span data-stu-id="12fa4-136">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="12fa4-137">Чтение общедоступной информации о пользовательском свойстве</span><span class="sxs-lookup"><span data-stu-id="12fa4-137">Read User PropertySet Public-Information</span></span></p></td>
<td><p><span data-ttu-id="12fa4-138"><strong>Да</strong></span><span class="sxs-lookup"><span data-stu-id="12fa4-138"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="12fa4-139">Нет</span><span class="sxs-lookup"><span data-stu-id="12fa4-139">No</span></span></p></td>
<td><p><span data-ttu-id="12fa4-140">Нет</span><span class="sxs-lookup"><span data-stu-id="12fa4-140">No</span></span></p></td>
<td><p><span data-ttu-id="12fa4-141">Нет</span><span class="sxs-lookup"><span data-stu-id="12fa4-141">No</span></span></p></td>
<td><p><span data-ttu-id="12fa4-142">Нет</span><span class="sxs-lookup"><span data-stu-id="12fa4-142">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="12fa4-143">Чтение Рткусерсеарчпроперти-Set для пользовательского свойства</span><span class="sxs-lookup"><span data-stu-id="12fa4-143">Read User PropertySet RTCUserSearchProperty-Set</span></span></p></td>
<td><p><span data-ttu-id="12fa4-144"><strong>Да</strong></span><span class="sxs-lookup"><span data-stu-id="12fa4-144"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="12fa4-145">Нет</span><span class="sxs-lookup"><span data-stu-id="12fa4-145">No</span></span></p></td>
<td><p><span data-ttu-id="12fa4-146">Нет</span><span class="sxs-lookup"><span data-stu-id="12fa4-146">No</span></span></p></td>
<td><p><span data-ttu-id="12fa4-147">Нет</span><span class="sxs-lookup"><span data-stu-id="12fa4-147">No</span></span></p></td>
<td><p><span data-ttu-id="12fa4-148"><strong>Да</strong></span><span class="sxs-lookup"><span data-stu-id="12fa4-148"><strong>Yes</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="12fa4-149">Чтение Рткпропертисет свойств пользователя</span><span class="sxs-lookup"><span data-stu-id="12fa4-149">Read User PropertySet RTCPropertySet</span></span></p></td>
<td><p><span data-ttu-id="12fa4-150"><strong>Да</strong></span><span class="sxs-lookup"><span data-stu-id="12fa4-150"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="12fa4-151">Нет</span><span class="sxs-lookup"><span data-stu-id="12fa4-151">No</span></span></p></td>
<td><p><span data-ttu-id="12fa4-152">Нет</span><span class="sxs-lookup"><span data-stu-id="12fa4-152">No</span></span></p></td>
<td><p><span data-ttu-id="12fa4-153">Нет</span><span class="sxs-lookup"><span data-stu-id="12fa4-153">No</span></span></p></td>
<td><p><span data-ttu-id="12fa4-154">Нет</span><span class="sxs-lookup"><span data-stu-id="12fa4-154">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="12fa4-155">Написание прокси-сервера свойств пользователя — адреса</span><span class="sxs-lookup"><span data-stu-id="12fa4-155">Write User Property Proxy-Addresses</span></span></p></td>
<td><p><span data-ttu-id="12fa4-156">Нет</span><span class="sxs-lookup"><span data-stu-id="12fa4-156">No</span></span></p></td>
<td><p><span data-ttu-id="12fa4-157">Нет</span><span class="sxs-lookup"><span data-stu-id="12fa4-157">No</span></span></p></td>
<td><p><span data-ttu-id="12fa4-158"><strong>Да</strong></span><span class="sxs-lookup"><span data-stu-id="12fa4-158"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="12fa4-159">Нет</span><span class="sxs-lookup"><span data-stu-id="12fa4-159">No</span></span></p></td>
<td><p><span data-ttu-id="12fa4-160">Нет</span><span class="sxs-lookup"><span data-stu-id="12fa4-160">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="12fa4-161">Запись пользовательского свойства Рткусерсеарчпроперти-Set</span><span class="sxs-lookup"><span data-stu-id="12fa4-161">Write User PropertySet RTCUserSearchProperty-Set</span></span></p></td>
<td><p><span data-ttu-id="12fa4-162">Нет</span><span class="sxs-lookup"><span data-stu-id="12fa4-162">No</span></span></p></td>
<td><p><span data-ttu-id="12fa4-163">Нет</span><span class="sxs-lookup"><span data-stu-id="12fa4-163">No</span></span></p></td>
<td><p><span data-ttu-id="12fa4-164"><strong>Да</strong></span><span class="sxs-lookup"><span data-stu-id="12fa4-164"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="12fa4-165">Нет</span><span class="sxs-lookup"><span data-stu-id="12fa4-165">No</span></span></p></td>
<td><p><span data-ttu-id="12fa4-166">Нет</span><span class="sxs-lookup"><span data-stu-id="12fa4-166">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="12fa4-167">Написание пользовательского свойства Рткпропертисет</span><span class="sxs-lookup"><span data-stu-id="12fa4-167">Write User PropertySet RTCPropertySet</span></span></p></td>
<td><p><span data-ttu-id="12fa4-168">Нет</span><span class="sxs-lookup"><span data-stu-id="12fa4-168">No</span></span></p></td>
<td><p><span data-ttu-id="12fa4-169">Нет</span><span class="sxs-lookup"><span data-stu-id="12fa4-169">No</span></span></p></td>
<td><p><span data-ttu-id="12fa4-170"><strong>Да</strong></span><span class="sxs-lookup"><span data-stu-id="12fa4-170"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="12fa4-171">Нет</span><span class="sxs-lookup"><span data-stu-id="12fa4-171">No</span></span></p></td>
<td><p><span data-ttu-id="12fa4-172">Нет</span><span class="sxs-lookup"><span data-stu-id="12fa4-172">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="12fa4-173">Чтение набора свойств DS-репликация — получение изменений для всех объектов Active Directory</span><span class="sxs-lookup"><span data-stu-id="12fa4-173">Read PropertySet DS-Replication-Get-Changes of all Active Directory objects</span></span></p></td>
<td><p><span data-ttu-id="12fa4-174">Нет</span><span class="sxs-lookup"><span data-stu-id="12fa4-174">No</span></span></p></td>
<td><p><span data-ttu-id="12fa4-175">Нет</span><span class="sxs-lookup"><span data-stu-id="12fa4-175">No</span></span></p></td>
<td><p><span data-ttu-id="12fa4-176">Нет</span><span class="sxs-lookup"><span data-stu-id="12fa4-176">No</span></span></p></td>
<td><p><span data-ttu-id="12fa4-177"><strong>Да</strong></span><span class="sxs-lookup"><span data-stu-id="12fa4-177"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="12fa4-178">Нет</span><span class="sxs-lookup"><span data-stu-id="12fa4-178">No</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="12fa4-179">В следующей таблице перечислены записи ACE, которые подготовка домена создает в трех встроенных контейнерах: пользователи, компьютеры и контроллеры домена.</span><span class="sxs-lookup"><span data-stu-id="12fa4-179">The following table lists the ACEs that domain preparation creates in the three built-in containers: Users, Computers, and Domain Controllers.</span></span> <span data-ttu-id="12fa4-180">Все ACE наследуются, если не указано иное.</span><span class="sxs-lookup"><span data-stu-id="12fa4-180">All ACEs are inherited unless otherwise noted.</span></span>

### <a name="aces-added-to-built-in-containers"></a><span data-ttu-id="12fa4-181">ACE, добавленные в встроенные контейнеры</span><span class="sxs-lookup"><span data-stu-id="12fa4-181">ACEs Added to Built-in Containers</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="12fa4-182">РЕЗУЛЬТИРУЮЩ</span><span class="sxs-lookup"><span data-stu-id="12fa4-182">ACE</span></span></th>
<th><span data-ttu-id="12fa4-183">Рткуниверсал — Усерреадонли-Group</span><span class="sxs-lookup"><span data-stu-id="12fa4-183">RTCUniversal-UserReadOnly-Group</span></span></th>
<th><span data-ttu-id="12fa4-184">Рткуниверсал — Серверреадонли-Group</span><span class="sxs-lookup"><span data-stu-id="12fa4-184">RTCUniversal-ServerReadOnly-Group</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="12fa4-185">Прочитать контейнер (не наследуется)</span><span class="sxs-lookup"><span data-stu-id="12fa4-185">Read Container (not inherited)</span></span></p></td>
<td><p><span data-ttu-id="12fa4-186"><strong>Кнопки</strong></span><span class="sxs-lookup"><span data-stu-id="12fa4-186"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="12fa4-187"><strong>Да</strong></span><span class="sxs-lookup"><span data-stu-id="12fa4-187"><strong>Yes</strong></span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

