---
title: 'Lync Server 2013: tblPrincipal'
description: 'Lync Server 2013: tblPrincipal.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblPrincipal
ms:assetid: 79a24502-b4ce-41f0-8979-8caddf535338
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558667(v=OCS.15)
ms:contentKeyID: 48184571
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0f07b37ac4c8ceed5c044b5c263eeee6370adfdc
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547495"
---
# <a name="tblprincipal-in-lync-server-2013"></a><span data-ttu-id="5d726-103">tblPrincipal в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5d726-103">tblPrincipal in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5d726-104">_**Последнее изменение темы:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="5d726-104">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="5d726-105">Таблица tblPrincipal содержит все субъекты, включая пользователей, папки и группы.</span><span class="sxs-lookup"><span data-stu-id="5d726-105">tblPrincipal contains all principals, including users, folders, and groups.</span></span>

### <a name="columns"></a><span data-ttu-id="5d726-106">Столбцы</span><span class="sxs-lookup"><span data-stu-id="5d726-106">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5d726-107">Столбец</span><span class="sxs-lookup"><span data-stu-id="5d726-107">Column</span></span></th>
<th><span data-ttu-id="5d726-108">Тип</span><span class="sxs-lookup"><span data-stu-id="5d726-108">Type</span></span></th>
<th><span data-ttu-id="5d726-109">Описание</span><span class="sxs-lookup"><span data-stu-id="5d726-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5d726-110">prinID</span><span class="sxs-lookup"><span data-stu-id="5d726-110">prinID</span></span></p></td>
<td><p><span data-ttu-id="5d726-111">int, not null</span><span class="sxs-lookup"><span data-stu-id="5d726-111">int, not null</span></span></p></td>
<td><p><span data-ttu-id="5d726-112">Идентификатор субъекта.</span><span class="sxs-lookup"><span data-stu-id="5d726-112">Principal ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5d726-113">прингуид</span><span class="sxs-lookup"><span data-stu-id="5d726-113">prinGuid</span></span></p></td>
<td><p><span data-ttu-id="5d726-114">GUID, не null</span><span class="sxs-lookup"><span data-stu-id="5d726-114">GUID, not null</span></span></p></td>
<td><p><span data-ttu-id="5d726-115">Идентификатор GUID субъекта.</span><span class="sxs-lookup"><span data-stu-id="5d726-115">Principal GUID.</span></span> <span data-ttu-id="5d726-116">Он широко используется в качестве альтернативного первичного ключа, так как его смысл пересекается с пространством доменных служб Active Directory.</span><span class="sxs-lookup"><span data-stu-id="5d726-116">This is broadly used as an alternate primary key because its meaning crosses over into the Active Directory Domain Services space.</span></span> <span data-ttu-id="5d726-117">(GUID кэшированного субъекта аналогичен GUID соответствующего объекта Active Directory.)</span><span class="sxs-lookup"><span data-stu-id="5d726-117">(The GUID for a cached principal is equal to the corresponding Active Directory object GUID.)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5d726-118">принури</span><span class="sxs-lookup"><span data-stu-id="5d726-118">prinUri</span></span></p></td>
<td><p><span data-ttu-id="5d726-119">nvarchar (256), не может быть null</span><span class="sxs-lookup"><span data-stu-id="5d726-119">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="5d726-p102">Универсальный код ресурса (URI) субъекта. Схема SIP используется для пользователей, а ma-grp — практически для всех остальных субъектов.</span><span class="sxs-lookup"><span data-stu-id="5d726-p102">Principal URI. The SIP scheme is used for users, and ma-grp is used for almost everything else.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5d726-122">приннаме</span><span class="sxs-lookup"><span data-stu-id="5d726-122">prinName</span></span></p></td>
<td><p><span data-ttu-id="5d726-123">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="5d726-123">nvarchar (256)</span></span></p></td>
<td><p><span data-ttu-id="5d726-p103">Общее имя. Используется только для пользователей.</span><span class="sxs-lookup"><span data-stu-id="5d726-p103">Common name. Used only by user types.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5d726-126">приндисплайнаме</span><span class="sxs-lookup"><span data-stu-id="5d726-126">prinDisplayName</span></span></p></td>
<td><p><span data-ttu-id="5d726-127">Nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="5d726-127">Nvarchar (256)</span></span></p></td>
<td><p><span data-ttu-id="5d726-p104">Отображаемое имя. Используется только для пользователей.</span><span class="sxs-lookup"><span data-stu-id="5d726-p104">Display name. Used only by user types.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5d726-130">принкомпанинаме</span><span class="sxs-lookup"><span data-stu-id="5d726-130">prinCompanyName</span></span></p></td>
<td><p><span data-ttu-id="5d726-131">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="5d726-131">nvarchar (256)</span></span></p></td>
<td><p><span data-ttu-id="5d726-p105">Название компании. Используется только для пользователей.</span><span class="sxs-lookup"><span data-stu-id="5d726-p105">Company name. Used only by user types.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5d726-134">принемаил</span><span class="sxs-lookup"><span data-stu-id="5d726-134">prinEmail</span></span></p></td>
<td><p><span data-ttu-id="5d726-135">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="5d726-135">nvarchar (256)</span></span></p></td>
<td><p><span data-ttu-id="5d726-p106">Электронная почта. Используется только для пользователей.</span><span class="sxs-lookup"><span data-stu-id="5d726-p106">Email. Used only by user types.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5d726-138">принадпас</span><span class="sxs-lookup"><span data-stu-id="5d726-138">prinADPath</span></span></p></td>
<td><p><span data-ttu-id="5d726-139">nvarchar (384)</span><span class="sxs-lookup"><span data-stu-id="5d726-139">nvarchar (384)</span></span></p></td>
<td><p><span data-ttu-id="5d726-p107">Имя домена объекта Active Directory, кэшированной версией которого является субъект. Может иметь значение Null для типов, не являющихся объектами Active Directory (например, системных пользователей).</span><span class="sxs-lookup"><span data-stu-id="5d726-p107">Domain name of the Active Directory object that the principal is a cached version of. Can be Null for types that are not Active Directory objects (such as system users).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5d726-142">принадусерпринЦипалнаме</span><span class="sxs-lookup"><span data-stu-id="5d726-142">prinADUserPrincipalName</span></span></p></td>
<td><p><span data-ttu-id="5d726-143">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="5d726-143">nvarchar (256)</span></span></p></td>
<td><p><span data-ttu-id="5d726-p108">Имя участника-пользователя. Используется только для обычных типов пользователя.</span><span class="sxs-lookup"><span data-stu-id="5d726-p108">User’s user principal name (UPN). Used only by regular user types.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5d726-146">приндисаблед</span><span class="sxs-lookup"><span data-stu-id="5d726-146">prinDisabled</span></span></p></td>
<td><p><span data-ttu-id="5d726-147">smallint, не null</span><span class="sxs-lookup"><span data-stu-id="5d726-147">smallint, not null</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="5d726-148">0 — субъект активен.</span><span class="sxs-lookup"><span data-stu-id="5d726-148">0: Principal is active.</span></span></p></li>
<li><p><span data-ttu-id="5d726-149">1 — субъект отключен, поскольку отключены возможности SIP пользователя.</span><span class="sxs-lookup"><span data-stu-id="5d726-149">1: Principal is disabled because user’s SIP capabilities are disabled.</span></span></p></li>
<li><p><span data-ttu-id="5d726-150">2 — субъект удален, поскольку удален связанный объект Active Directory.</span><span class="sxs-lookup"><span data-stu-id="5d726-150">2: Principal is deleted because associated AD object has been deleted.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5d726-151">принтипеид</span><span class="sxs-lookup"><span data-stu-id="5d726-151">prinTypeID</span></span></p></td>
<td><p><span data-ttu-id="5d726-152">smallint, не может быть null</span><span class="sxs-lookup"><span data-stu-id="5d726-152">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="5d726-153">Тип субъекта (из таблицы tblPrincipalType).</span><span class="sxs-lookup"><span data-stu-id="5d726-153">Principal type (from tblPrincipalType table).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5d726-154">принпулид</span><span class="sxs-lookup"><span data-stu-id="5d726-154">prinPoolID</span></span></p></td>
<td><p><span data-ttu-id="5d726-155">Целое</span><span class="sxs-lookup"><span data-stu-id="5d726-155">Int</span></span></p></td>
<td><p><span data-ttu-id="5d726-156">Назначение пула Lync для субъекта.</span><span class="sxs-lookup"><span data-stu-id="5d726-156">Lync pool assignment for the principal.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5d726-157">принполициид</span><span class="sxs-lookup"><span data-stu-id="5d726-157">prinPolicyID</span></span></p></td>
<td><p><span data-ttu-id="5d726-158">Целое</span><span class="sxs-lookup"><span data-stu-id="5d726-158">Int</span></span></p></td>
<td><p><span data-ttu-id="5d726-159">Значение политики сервера сохраняемого чата для пользователя, если присутствует политика типов тегов.</span><span class="sxs-lookup"><span data-stu-id="5d726-159">Persistent Chat Server policy value for user, if tag type policy is present.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5d726-160">принаддедби</span><span class="sxs-lookup"><span data-stu-id="5d726-160">prinAddedBy</span></span></p></td>
<td><p><span data-ttu-id="5d726-161">int</span><span class="sxs-lookup"><span data-stu-id="5d726-161">int</span></span></p></td>
<td><p><span data-ttu-id="5d726-162">Идентификатор субъекта создателя.</span><span class="sxs-lookup"><span data-stu-id="5d726-162">Principal ID of the creator.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5d726-163">принаддедон</span><span class="sxs-lookup"><span data-stu-id="5d726-163">prinAddedOn</span></span></p></td>
<td><p><span data-ttu-id="5d726-164">bigint, не может быть null</span><span class="sxs-lookup"><span data-stu-id="5d726-164">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="5d726-165">Метка времени создания.</span><span class="sxs-lookup"><span data-stu-id="5d726-165">Time stamp for the creation time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5d726-166">принупдатедби</span><span class="sxs-lookup"><span data-stu-id="5d726-166">prinUpdatedBy</span></span></p></td>
<td><p><span data-ttu-id="5d726-167">int</span><span class="sxs-lookup"><span data-stu-id="5d726-167">int</span></span></p></td>
<td><p><span data-ttu-id="5d726-168">Идентификатор субъекта, выполнившего последнее обновление.</span><span class="sxs-lookup"><span data-stu-id="5d726-168">ID of the principal that last updated this.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5d726-169">принупдатедон</span><span class="sxs-lookup"><span data-stu-id="5d726-169">prinUpdatedOn</span></span></p></td>
<td><p><span data-ttu-id="5d726-170">bigint, не может быть null</span><span class="sxs-lookup"><span data-stu-id="5d726-170">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="5d726-171">Метка времени последнего обновления.</span><span class="sxs-lookup"><span data-stu-id="5d726-171">Time stamp for the last update.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5d726-172">принверифиедон</span><span class="sxs-lookup"><span data-stu-id="5d726-172">prinVerifiedOn</span></span></p></td>
<td><p><span data-ttu-id="5d726-173">datetime, не может быть null</span><span class="sxs-lookup"><span data-stu-id="5d726-173">datetime, not null</span></span></p></td>
<td><p><span data-ttu-id="5d726-174">Дата и время последнего обновления субъекта в результате синхронизации с Active Directory.</span><span class="sxs-lookup"><span data-stu-id="5d726-174">Date and time of the last Active Directory Sync refresh for the principal.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="5d726-175">Keys</span><span class="sxs-lookup"><span data-stu-id="5d726-175">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5d726-176">Столбец</span><span class="sxs-lookup"><span data-stu-id="5d726-176">Column</span></span></th>
<th><span data-ttu-id="5d726-177">Описание</span><span class="sxs-lookup"><span data-stu-id="5d726-177">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5d726-178">prinID</span><span class="sxs-lookup"><span data-stu-id="5d726-178">prinID</span></span></p></td>
<td><p><span data-ttu-id="5d726-179">Первичный ключ.</span><span class="sxs-lookup"><span data-stu-id="5d726-179">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5d726-180">принтипеид</span><span class="sxs-lookup"><span data-stu-id="5d726-180">prinTypeID</span></span></p></td>
<td><p><span data-ttu-id="5d726-181">Внешний ключ с подстановкой в таблице tblPrincipalType.ptypeID.</span><span class="sxs-lookup"><span data-stu-id="5d726-181">Foreign key with lookup in tblPrincipalType.ptypeID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

