---
title: 'Lync Server 2013: tblPrincipal'
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
ms.openlocfilehash: 5e4b0c8154429fa68bc05e757130e0b92a47e65c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48523766"
---
# <a name="tblprincipal-in-lync-server-2013"></a><span data-ttu-id="a096a-102">tblPrincipal в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a096a-102">tblPrincipal in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a096a-103">_**Последнее изменение темы:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="a096a-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="a096a-104">Таблица tblPrincipal содержит все субъекты, включая пользователей, папки и группы.</span><span class="sxs-lookup"><span data-stu-id="a096a-104">tblPrincipal contains all principals, including users, folders, and groups.</span></span>

### <a name="columns"></a><span data-ttu-id="a096a-105">Столбцы</span><span class="sxs-lookup"><span data-stu-id="a096a-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a096a-106">Столбец</span><span class="sxs-lookup"><span data-stu-id="a096a-106">Column</span></span></th>
<th><span data-ttu-id="a096a-107">Тип</span><span class="sxs-lookup"><span data-stu-id="a096a-107">Type</span></span></th>
<th><span data-ttu-id="a096a-108">Описание</span><span class="sxs-lookup"><span data-stu-id="a096a-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a096a-109">prinID</span><span class="sxs-lookup"><span data-stu-id="a096a-109">prinID</span></span></p></td>
<td><p><span data-ttu-id="a096a-110">int, not null</span><span class="sxs-lookup"><span data-stu-id="a096a-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="a096a-111">Идентификатор субъекта.</span><span class="sxs-lookup"><span data-stu-id="a096a-111">Principal ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a096a-112">прингуид</span><span class="sxs-lookup"><span data-stu-id="a096a-112">prinGuid</span></span></p></td>
<td><p><span data-ttu-id="a096a-113">GUID, не null</span><span class="sxs-lookup"><span data-stu-id="a096a-113">GUID, not null</span></span></p></td>
<td><p><span data-ttu-id="a096a-114">Идентификатор GUID субъекта.</span><span class="sxs-lookup"><span data-stu-id="a096a-114">Principal GUID.</span></span> <span data-ttu-id="a096a-115">Он широко используется в качестве альтернативного первичного ключа, так как его смысл пересекается с пространством доменных служб Active Directory.</span><span class="sxs-lookup"><span data-stu-id="a096a-115">This is broadly used as an alternate primary key because its meaning crosses over into the Active Directory Domain Services space.</span></span> <span data-ttu-id="a096a-116">(GUID кэшированного субъекта аналогичен GUID соответствующего объекта Active Directory.)</span><span class="sxs-lookup"><span data-stu-id="a096a-116">(The GUID for a cached principal is equal to the corresponding Active Directory object GUID.)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a096a-117">принури</span><span class="sxs-lookup"><span data-stu-id="a096a-117">prinUri</span></span></p></td>
<td><p><span data-ttu-id="a096a-118">nvarchar (256), не может быть null</span><span class="sxs-lookup"><span data-stu-id="a096a-118">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="a096a-p102">Универсальный код ресурса (URI) субъекта. Схема SIP используется для пользователей, а ma-grp — практически для всех остальных субъектов.</span><span class="sxs-lookup"><span data-stu-id="a096a-p102">Principal URI. The SIP scheme is used for users, and ma-grp is used for almost everything else.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a096a-121">приннаме</span><span class="sxs-lookup"><span data-stu-id="a096a-121">prinName</span></span></p></td>
<td><p><span data-ttu-id="a096a-122">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="a096a-122">nvarchar (256)</span></span></p></td>
<td><p><span data-ttu-id="a096a-p103">Общее имя. Используется только для пользователей.</span><span class="sxs-lookup"><span data-stu-id="a096a-p103">Common name. Used only by user types.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a096a-125">приндисплайнаме</span><span class="sxs-lookup"><span data-stu-id="a096a-125">prinDisplayName</span></span></p></td>
<td><p><span data-ttu-id="a096a-126">Nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="a096a-126">Nvarchar (256)</span></span></p></td>
<td><p><span data-ttu-id="a096a-p104">Отображаемое имя. Используется только для пользователей.</span><span class="sxs-lookup"><span data-stu-id="a096a-p104">Display name. Used only by user types.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a096a-129">принкомпанинаме</span><span class="sxs-lookup"><span data-stu-id="a096a-129">prinCompanyName</span></span></p></td>
<td><p><span data-ttu-id="a096a-130">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="a096a-130">nvarchar (256)</span></span></p></td>
<td><p><span data-ttu-id="a096a-p105">Название компании. Используется только для пользователей.</span><span class="sxs-lookup"><span data-stu-id="a096a-p105">Company name. Used only by user types.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a096a-133">принемаил</span><span class="sxs-lookup"><span data-stu-id="a096a-133">prinEmail</span></span></p></td>
<td><p><span data-ttu-id="a096a-134">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="a096a-134">nvarchar (256)</span></span></p></td>
<td><p><span data-ttu-id="a096a-p106">Электронная почта. Используется только для пользователей.</span><span class="sxs-lookup"><span data-stu-id="a096a-p106">Email. Used only by user types.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a096a-137">принадпас</span><span class="sxs-lookup"><span data-stu-id="a096a-137">prinADPath</span></span></p></td>
<td><p><span data-ttu-id="a096a-138">nvarchar (384)</span><span class="sxs-lookup"><span data-stu-id="a096a-138">nvarchar (384)</span></span></p></td>
<td><p><span data-ttu-id="a096a-p107">Имя домена объекта Active Directory, кэшированной версией которого является субъект. Может иметь значение Null для типов, не являющихся объектами Active Directory (например, системных пользователей).</span><span class="sxs-lookup"><span data-stu-id="a096a-p107">Domain name of the Active Directory object that the principal is a cached version of. Can be Null for types that are not Active Directory objects (such as system users).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a096a-141">принадусерпринЦипалнаме</span><span class="sxs-lookup"><span data-stu-id="a096a-141">prinADUserPrincipalName</span></span></p></td>
<td><p><span data-ttu-id="a096a-142">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="a096a-142">nvarchar (256)</span></span></p></td>
<td><p><span data-ttu-id="a096a-p108">Имя участника-пользователя. Используется только для обычных типов пользователя.</span><span class="sxs-lookup"><span data-stu-id="a096a-p108">User’s user principal name (UPN). Used only by regular user types.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a096a-145">приндисаблед</span><span class="sxs-lookup"><span data-stu-id="a096a-145">prinDisabled</span></span></p></td>
<td><p><span data-ttu-id="a096a-146">smallint, не null</span><span class="sxs-lookup"><span data-stu-id="a096a-146">smallint, not null</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="a096a-147">0 — субъект активен.</span><span class="sxs-lookup"><span data-stu-id="a096a-147">0: Principal is active.</span></span></p></li>
<li><p><span data-ttu-id="a096a-148">1 — субъект отключен, поскольку отключены возможности SIP пользователя.</span><span class="sxs-lookup"><span data-stu-id="a096a-148">1: Principal is disabled because user’s SIP capabilities are disabled.</span></span></p></li>
<li><p><span data-ttu-id="a096a-149">2 — субъект удален, поскольку удален связанный объект Active Directory.</span><span class="sxs-lookup"><span data-stu-id="a096a-149">2: Principal is deleted because associated AD object has been deleted.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a096a-150">принтипеид</span><span class="sxs-lookup"><span data-stu-id="a096a-150">prinTypeID</span></span></p></td>
<td><p><span data-ttu-id="a096a-151">smallint, не может быть null</span><span class="sxs-lookup"><span data-stu-id="a096a-151">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="a096a-152">Тип субъекта (из таблицы tblPrincipalType).</span><span class="sxs-lookup"><span data-stu-id="a096a-152">Principal type (from tblPrincipalType table).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a096a-153">принпулид</span><span class="sxs-lookup"><span data-stu-id="a096a-153">prinPoolID</span></span></p></td>
<td><p><span data-ttu-id="a096a-154">Целое</span><span class="sxs-lookup"><span data-stu-id="a096a-154">Int</span></span></p></td>
<td><p><span data-ttu-id="a096a-155">Назначение пула Lync для субъекта.</span><span class="sxs-lookup"><span data-stu-id="a096a-155">Lync pool assignment for the principal.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a096a-156">принполициид</span><span class="sxs-lookup"><span data-stu-id="a096a-156">prinPolicyID</span></span></p></td>
<td><p><span data-ttu-id="a096a-157">Целое</span><span class="sxs-lookup"><span data-stu-id="a096a-157">Int</span></span></p></td>
<td><p><span data-ttu-id="a096a-158">Значение политики сервера сохраняемого чата для пользователя, если присутствует политика типов тегов.</span><span class="sxs-lookup"><span data-stu-id="a096a-158">Persistent Chat Server policy value for user, if tag type policy is present.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a096a-159">принаддедби</span><span class="sxs-lookup"><span data-stu-id="a096a-159">prinAddedBy</span></span></p></td>
<td><p><span data-ttu-id="a096a-160">int</span><span class="sxs-lookup"><span data-stu-id="a096a-160">int</span></span></p></td>
<td><p><span data-ttu-id="a096a-161">Идентификатор субъекта создателя.</span><span class="sxs-lookup"><span data-stu-id="a096a-161">Principal ID of the creator.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a096a-162">принаддедон</span><span class="sxs-lookup"><span data-stu-id="a096a-162">prinAddedOn</span></span></p></td>
<td><p><span data-ttu-id="a096a-163">bigint, не может быть null</span><span class="sxs-lookup"><span data-stu-id="a096a-163">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="a096a-164">Метка времени создания.</span><span class="sxs-lookup"><span data-stu-id="a096a-164">Time stamp for the creation time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a096a-165">принупдатедби</span><span class="sxs-lookup"><span data-stu-id="a096a-165">prinUpdatedBy</span></span></p></td>
<td><p><span data-ttu-id="a096a-166">int</span><span class="sxs-lookup"><span data-stu-id="a096a-166">int</span></span></p></td>
<td><p><span data-ttu-id="a096a-167">Идентификатор субъекта, выполнившего последнее обновление.</span><span class="sxs-lookup"><span data-stu-id="a096a-167">ID of the principal that last updated this.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a096a-168">принупдатедон</span><span class="sxs-lookup"><span data-stu-id="a096a-168">prinUpdatedOn</span></span></p></td>
<td><p><span data-ttu-id="a096a-169">bigint, не может быть null</span><span class="sxs-lookup"><span data-stu-id="a096a-169">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="a096a-170">Метка времени последнего обновления.</span><span class="sxs-lookup"><span data-stu-id="a096a-170">Time stamp for the last update.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a096a-171">принверифиедон</span><span class="sxs-lookup"><span data-stu-id="a096a-171">prinVerifiedOn</span></span></p></td>
<td><p><span data-ttu-id="a096a-172">datetime, не может быть null</span><span class="sxs-lookup"><span data-stu-id="a096a-172">datetime, not null</span></span></p></td>
<td><p><span data-ttu-id="a096a-173">Дата и время последнего обновления субъекта в результате синхронизации с Active Directory.</span><span class="sxs-lookup"><span data-stu-id="a096a-173">Date and time of the last Active Directory Sync refresh for the principal.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="a096a-174">Keys</span><span class="sxs-lookup"><span data-stu-id="a096a-174">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a096a-175">Столбец</span><span class="sxs-lookup"><span data-stu-id="a096a-175">Column</span></span></th>
<th><span data-ttu-id="a096a-176">Описание</span><span class="sxs-lookup"><span data-stu-id="a096a-176">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a096a-177">prinID</span><span class="sxs-lookup"><span data-stu-id="a096a-177">prinID</span></span></p></td>
<td><p><span data-ttu-id="a096a-178">Первичный ключ.</span><span class="sxs-lookup"><span data-stu-id="a096a-178">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a096a-179">принтипеид</span><span class="sxs-lookup"><span data-stu-id="a096a-179">prinTypeID</span></span></p></td>
<td><p><span data-ttu-id="a096a-180">Внешний ключ с подстановкой в таблице tblPrincipalType.ptypeID.</span><span class="sxs-lookup"><span data-stu-id="a096a-180">Foreign key with lookup in tblPrincipalType.ptypeID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

