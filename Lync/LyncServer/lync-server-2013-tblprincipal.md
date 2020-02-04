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
ms.openlocfilehash: 25de9273fb6e153bb154bf0062edd96cb67bbac2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41731539"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblprincipal-in-lync-server-2013"></a><span data-ttu-id="8cb95-102">tblPrincipal в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8cb95-102">tblPrincipal in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8cb95-103">_**Тема последнего изменения:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="8cb95-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="8cb95-104">ТблпринЦипал содержит всех участников, в том числе пользователей, папок и групп.</span><span class="sxs-lookup"><span data-stu-id="8cb95-104">tblPrincipal contains all principals, including users, folders, and groups.</span></span>

### <a name="columns"></a><span data-ttu-id="8cb95-105">Столбцов</span><span class="sxs-lookup"><span data-stu-id="8cb95-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8cb95-106">Столбец</span><span class="sxs-lookup"><span data-stu-id="8cb95-106">Column</span></span></th>
<th><span data-ttu-id="8cb95-107">Тип</span><span class="sxs-lookup"><span data-stu-id="8cb95-107">Type</span></span></th>
<th><span data-ttu-id="8cb95-108">Описание</span><span class="sxs-lookup"><span data-stu-id="8cb95-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8cb95-109">принид</span><span class="sxs-lookup"><span data-stu-id="8cb95-109">prinID</span></span></p></td>
<td><p><span data-ttu-id="8cb95-110">int, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="8cb95-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="8cb95-111">Идентификатор участника.</span><span class="sxs-lookup"><span data-stu-id="8cb95-111">Principal ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8cb95-112">прингуид</span><span class="sxs-lookup"><span data-stu-id="8cb95-112">prinGuid</span></span></p></td>
<td><p><span data-ttu-id="8cb95-113">GUID, а не NULL</span><span class="sxs-lookup"><span data-stu-id="8cb95-113">GUID, not null</span></span></p></td>
<td><p><span data-ttu-id="8cb95-114">Идентификатор GUID участника.</span><span class="sxs-lookup"><span data-stu-id="8cb95-114">Principal GUID.</span></span> <span data-ttu-id="8cb95-115">Это широко используется как альтернативный первичный ключ, так как его значение пересекается с пространством доменных служб Active Directory.</span><span class="sxs-lookup"><span data-stu-id="8cb95-115">This is broadly used as an alternate primary key because its meaning crosses over into the Active Directory Domain Services space.</span></span> <span data-ttu-id="8cb95-116">(GUID для кэшированного участника равен GUID соответствующего объекта Active Directory.)</span><span class="sxs-lookup"><span data-stu-id="8cb95-116">(The GUID for a cached principal is equal to the corresponding Active Directory object GUID.)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8cb95-117">принури</span><span class="sxs-lookup"><span data-stu-id="8cb95-117">prinUri</span></span></p></td>
<td><p><span data-ttu-id="8cb95-118">nvarchar (256), NOT NULL</span><span class="sxs-lookup"><span data-stu-id="8cb95-118">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="8cb95-119">Универсальный код ресурса (URI) участника.</span><span class="sxs-lookup"><span data-stu-id="8cb95-119">Principal URI.</span></span> <span data-ttu-id="8cb95-120">Схема SIP используется для пользователей, а MA-GRP используется практически всеми остальными.</span><span class="sxs-lookup"><span data-stu-id="8cb95-120">The SIP scheme is used for users, and ma-grp is used for almost everything else.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8cb95-121">приннаме</span><span class="sxs-lookup"><span data-stu-id="8cb95-121">prinName</span></span></p></td>
<td><p><span data-ttu-id="8cb95-122">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="8cb95-122">nvarchar (256)</span></span></p></td>
<td><p><span data-ttu-id="8cb95-123">Обычное имя.</span><span class="sxs-lookup"><span data-stu-id="8cb95-123">Common name.</span></span> <span data-ttu-id="8cb95-124">Используется только для пользовательских типов.</span><span class="sxs-lookup"><span data-stu-id="8cb95-124">Used only by user types.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8cb95-125">приндисплайнаме</span><span class="sxs-lookup"><span data-stu-id="8cb95-125">prinDisplayName</span></span></p></td>
<td><p><span data-ttu-id="8cb95-126">Nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="8cb95-126">Nvarchar (256)</span></span></p></td>
<td><p><span data-ttu-id="8cb95-127">Отображаемое имя.</span><span class="sxs-lookup"><span data-stu-id="8cb95-127">Display name.</span></span> <span data-ttu-id="8cb95-128">Используется только для пользовательских типов.</span><span class="sxs-lookup"><span data-stu-id="8cb95-128">Used only by user types.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8cb95-129">принкомпанинаме</span><span class="sxs-lookup"><span data-stu-id="8cb95-129">prinCompanyName</span></span></p></td>
<td><p><span data-ttu-id="8cb95-130">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="8cb95-130">nvarchar (256)</span></span></p></td>
<td><p><span data-ttu-id="8cb95-131">Название компании.</span><span class="sxs-lookup"><span data-stu-id="8cb95-131">Company name.</span></span> <span data-ttu-id="8cb95-132">Используется только для пользовательских типов.</span><span class="sxs-lookup"><span data-stu-id="8cb95-132">Used only by user types.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8cb95-133">принемаил</span><span class="sxs-lookup"><span data-stu-id="8cb95-133">prinEmail</span></span></p></td>
<td><p><span data-ttu-id="8cb95-134">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="8cb95-134">nvarchar (256)</span></span></p></td>
<td><p><span data-ttu-id="8cb95-135">Отправить по электронной почте.</span><span class="sxs-lookup"><span data-stu-id="8cb95-135">Email.</span></span> <span data-ttu-id="8cb95-136">Используется только для пользовательских типов.</span><span class="sxs-lookup"><span data-stu-id="8cb95-136">Used only by user types.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8cb95-137">принадпас</span><span class="sxs-lookup"><span data-stu-id="8cb95-137">prinADPath</span></span></p></td>
<td><p><span data-ttu-id="8cb95-138">nvarchar (384)</span><span class="sxs-lookup"><span data-stu-id="8cb95-138">nvarchar (384)</span></span></p></td>
<td><p><span data-ttu-id="8cb95-139">Доменное имя объекта Active Directory, который является кэшированной версией участника.</span><span class="sxs-lookup"><span data-stu-id="8cb95-139">Domain name of the Active Directory object that the principal is a cached version of.</span></span> <span data-ttu-id="8cb95-140">Может принимать значение NULL для типов, которые не являются объектами службы каталогов Active Directory (например, пользователи системы).</span><span class="sxs-lookup"><span data-stu-id="8cb95-140">Can be Null for types that are not Active Directory objects (such as system users).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8cb95-141">принадусерпринЦипалнаме</span><span class="sxs-lookup"><span data-stu-id="8cb95-141">prinADUserPrincipalName</span></span></p></td>
<td><p><span data-ttu-id="8cb95-142">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="8cb95-142">nvarchar (256)</span></span></p></td>
<td><p><span data-ttu-id="8cb95-143">Имя участника-пользователя (UPN) пользователя.</span><span class="sxs-lookup"><span data-stu-id="8cb95-143">User’s user principal name (UPN).</span></span> <span data-ttu-id="8cb95-144">Используется только обычными типами пользователей.</span><span class="sxs-lookup"><span data-stu-id="8cb95-144">Used only by regular user types.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8cb95-145">приндисаблед</span><span class="sxs-lookup"><span data-stu-id="8cb95-145">prinDisabled</span></span></p></td>
<td><p><span data-ttu-id="8cb95-146">smallint, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="8cb95-146">smallint, not null</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="8cb95-147">0: участник активен.</span><span class="sxs-lookup"><span data-stu-id="8cb95-147">0: Principal is active.</span></span></p></li>
<li><p><span data-ttu-id="8cb95-148">1: участник отключен, поскольку возможности SIP пользователя отключены.</span><span class="sxs-lookup"><span data-stu-id="8cb95-148">1: Principal is disabled because user’s SIP capabilities are disabled.</span></span></p></li>
<li><p><span data-ttu-id="8cb95-149">2: участник удален, так как связанный объект рекламы удален.</span><span class="sxs-lookup"><span data-stu-id="8cb95-149">2: Principal is deleted because associated AD object has been deleted.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8cb95-150">принтипеид</span><span class="sxs-lookup"><span data-stu-id="8cb95-150">prinTypeID</span></span></p></td>
<td><p><span data-ttu-id="8cb95-151">smallint, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="8cb95-151">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="8cb95-152">Тип участника (из таблицы ТблпринЦипалтипе).</span><span class="sxs-lookup"><span data-stu-id="8cb95-152">Principal type (from tblPrincipalType table).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8cb95-153">принпулид</span><span class="sxs-lookup"><span data-stu-id="8cb95-153">prinPoolID</span></span></p></td>
<td><p><span data-ttu-id="8cb95-154">Типом</span><span class="sxs-lookup"><span data-stu-id="8cb95-154">Int</span></span></p></td>
<td><p><span data-ttu-id="8cb95-155">Назначение пула Lync для участника.</span><span class="sxs-lookup"><span data-stu-id="8cb95-155">Lync pool assignment for the principal.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8cb95-156">принполициид</span><span class="sxs-lookup"><span data-stu-id="8cb95-156">prinPolicyID</span></span></p></td>
<td><p><span data-ttu-id="8cb95-157">Типом</span><span class="sxs-lookup"><span data-stu-id="8cb95-157">Int</span></span></p></td>
<td><p><span data-ttu-id="8cb95-158">Значение политики сервера сохраняемого чата для пользователя, если указана политика типа тега.</span><span class="sxs-lookup"><span data-stu-id="8cb95-158">Persistent Chat Server policy value for user, if tag type policy is present.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8cb95-159">принаддедби</span><span class="sxs-lookup"><span data-stu-id="8cb95-159">prinAddedBy</span></span></p></td>
<td><p><span data-ttu-id="8cb95-160">целое</span><span class="sxs-lookup"><span data-stu-id="8cb95-160">int</span></span></p></td>
<td><p><span data-ttu-id="8cb95-161">Идентификатор участника создателя.</span><span class="sxs-lookup"><span data-stu-id="8cb95-161">Principal ID of the creator.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8cb95-162">принаддедон</span><span class="sxs-lookup"><span data-stu-id="8cb95-162">prinAddedOn</span></span></p></td>
<td><p><span data-ttu-id="8cb95-163">bigint, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="8cb95-163">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="8cb95-164">Метка времени для времени создания.</span><span class="sxs-lookup"><span data-stu-id="8cb95-164">Time stamp for the creation time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8cb95-165">принупдатедби</span><span class="sxs-lookup"><span data-stu-id="8cb95-165">prinUpdatedBy</span></span></p></td>
<td><p><span data-ttu-id="8cb95-166">целое</span><span class="sxs-lookup"><span data-stu-id="8cb95-166">int</span></span></p></td>
<td><p><span data-ttu-id="8cb95-167">Идентификатор участника, который последним обновил это.</span><span class="sxs-lookup"><span data-stu-id="8cb95-167">ID of the principal that last updated this.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8cb95-168">принупдатедон</span><span class="sxs-lookup"><span data-stu-id="8cb95-168">prinUpdatedOn</span></span></p></td>
<td><p><span data-ttu-id="8cb95-169">bigint, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="8cb95-169">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="8cb95-170">Метка времени для последнего обновления.</span><span class="sxs-lookup"><span data-stu-id="8cb95-170">Time stamp for the last update.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8cb95-171">принверифиедон</span><span class="sxs-lookup"><span data-stu-id="8cb95-171">prinVerifiedOn</span></span></p></td>
<td><p><span data-ttu-id="8cb95-172">DateTime, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="8cb95-172">datetime, not null</span></span></p></td>
<td><p><span data-ttu-id="8cb95-173">Дата и время последнего обновления службы синхронизации Active Directory для участника.</span><span class="sxs-lookup"><span data-stu-id="8cb95-173">Date and time of the last Active Directory Sync refresh for the principal.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="8cb95-174">Параметры</span><span class="sxs-lookup"><span data-stu-id="8cb95-174">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8cb95-175">Столбец</span><span class="sxs-lookup"><span data-stu-id="8cb95-175">Column</span></span></th>
<th><span data-ttu-id="8cb95-176">Описание</span><span class="sxs-lookup"><span data-stu-id="8cb95-176">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8cb95-177">принид</span><span class="sxs-lookup"><span data-stu-id="8cb95-177">prinID</span></span></p></td>
<td><p><span data-ttu-id="8cb95-178">Первичный ключ.</span><span class="sxs-lookup"><span data-stu-id="8cb95-178">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8cb95-179">принтипеид</span><span class="sxs-lookup"><span data-stu-id="8cb95-179">prinTypeID</span></span></p></td>
<td><p><span data-ttu-id="8cb95-180">Внешний ключ с подстановкой в таблице ТблпринЦипалтипе. Птипеид.</span><span class="sxs-lookup"><span data-stu-id="8cb95-180">Foreign key with lookup in tblPrincipalType.ptypeID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

