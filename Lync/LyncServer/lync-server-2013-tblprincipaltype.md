---
title: 'Lync Server 2013: tblPrincipalType'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: tblPrincipalType
ms:assetid: 32e1c1d6-80f4-4624-bf4e-b4c77d3982fa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558633(v=OCS.15)
ms:contentKeyID: 48183787
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 725d097e1e2e75b6430974a4f133cb5fa4130346
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849527"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblprincipaltype-in-lync-server-2013"></a><span data-ttu-id="05dba-102">tblPrincipalType в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="05dba-102">tblPrincipalType in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="05dba-103">_**Тема последнего изменения:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="05dba-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="05dba-104">ТблпринЦипалтипе содержит основные типы для классификации содержимого в таблице ТблпринЦипал.</span><span class="sxs-lookup"><span data-stu-id="05dba-104">tblPrincipalType contains principal types to categorize what is in the tblPrincipal table.</span></span>

### <a name="columns"></a><span data-ttu-id="05dba-105">Столбцов</span><span class="sxs-lookup"><span data-stu-id="05dba-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="05dba-106">Столбец</span><span class="sxs-lookup"><span data-stu-id="05dba-106">Column</span></span></th>
<th><span data-ttu-id="05dba-107">Тип</span><span class="sxs-lookup"><span data-stu-id="05dba-107">Type</span></span></th>
<th><span data-ttu-id="05dba-108">Описание</span><span class="sxs-lookup"><span data-stu-id="05dba-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="05dba-109">Птипеид</span><span class="sxs-lookup"><span data-stu-id="05dba-109">ptypeID</span></span></p></td>
<td><p><span data-ttu-id="05dba-110">smallint, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="05dba-110">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="05dba-111">Идентификатор типа участника.</span><span class="sxs-lookup"><span data-stu-id="05dba-111">Principal type ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="05dba-112">Птипедеск</span><span class="sxs-lookup"><span data-stu-id="05dba-112">ptypeDesc</span></span></p></td>
<td><p><span data-ttu-id="05dba-113">nvarchar (256), NOT NULL</span><span class="sxs-lookup"><span data-stu-id="05dba-113">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="05dba-114">Описание типа.</span><span class="sxs-lookup"><span data-stu-id="05dba-114">Description of the type.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="05dba-115">Птипеиссистемусер</span><span class="sxs-lookup"><span data-stu-id="05dba-115">ptypeIsSystemUser</span></span></p></td>
<td><p><span data-ttu-id="05dba-116">bit, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="05dba-116">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="05dba-117">Значение true, если тип соответствует участникам, которые используются для внутренних целей.</span><span class="sxs-lookup"><span data-stu-id="05dba-117">True if the type corresponds to the principals that are used for internal purposes.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="05dba-118">Птипеисусер</span><span class="sxs-lookup"><span data-stu-id="05dba-118">ptypeIsUser</span></span></p></td>
<td><p><span data-ttu-id="05dba-119">bit, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="05dba-119">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="05dba-120">Значение true, если тип является пользовательским типом.</span><span class="sxs-lookup"><span data-stu-id="05dba-120">True if the type is a user type.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="05dba-121">Ключ</span><span class="sxs-lookup"><span data-stu-id="05dba-121">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="05dba-122">Столбец</span><span class="sxs-lookup"><span data-stu-id="05dba-122">Column</span></span></th>
<th><span data-ttu-id="05dba-123">Описание</span><span class="sxs-lookup"><span data-stu-id="05dba-123">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="05dba-124">Птипеид</span><span class="sxs-lookup"><span data-stu-id="05dba-124">ptypeID</span></span></p></td>
<td><p><span data-ttu-id="05dba-125">Первичный ключ.</span><span class="sxs-lookup"><span data-stu-id="05dba-125">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="principal-values"></a><span data-ttu-id="05dba-126">Основные значения</span><span class="sxs-lookup"><span data-stu-id="05dba-126">Principal Values</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="05dba-127">ID</span><span class="sxs-lookup"><span data-stu-id="05dba-127">ID</span></span></th>
<th><span data-ttu-id="05dba-128">Должность</span><span class="sxs-lookup"><span data-stu-id="05dba-128">Role</span></span></th>
<th><span data-ttu-id="05dba-129">Описание</span><span class="sxs-lookup"><span data-stu-id="05dba-129">Description</span></span></th>
<th><span data-ttu-id="05dba-130">Пользователь</span><span class="sxs-lookup"><span data-stu-id="05dba-130">User</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="05dba-131">1</span><span class="sxs-lookup"><span data-stu-id="05dba-131">1</span></span></p></td>
<td><p><span data-ttu-id="05dba-132">Любой</span><span class="sxs-lookup"><span data-stu-id="05dba-132">Any</span></span></p></td>
<td><p><span data-ttu-id="05dba-133">Универсальный принципал без известного типа.</span><span class="sxs-lookup"><span data-stu-id="05dba-133">Generic principal with no known type.</span></span> <span data-ttu-id="05dba-134">Не используется в таблице ТблпринЦипал.</span><span class="sxs-lookup"><span data-stu-id="05dba-134">Not used in tblPrincipal table.</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="05dba-135">2</span><span class="sxs-lookup"><span data-stu-id="05dba-135">2</span></span></p></td>
<td><p><span data-ttu-id="05dba-136">Анюсер</span><span class="sxs-lookup"><span data-stu-id="05dba-136">AnyUser</span></span></p></td>
<td><p><span data-ttu-id="05dba-137">Универсальный принципал для типа пользователя.</span><span class="sxs-lookup"><span data-stu-id="05dba-137">Generic principal of user type.</span></span> <span data-ttu-id="05dba-138">Не используется в таблице ТблпринЦипал.</span><span class="sxs-lookup"><span data-stu-id="05dba-138">Not used in tblPrincipal table.</span></span></p></td>
<td><p><span data-ttu-id="05dba-139">Да</span><span class="sxs-lookup"><span data-stu-id="05dba-139">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="05dba-140">3</span><span class="sxs-lookup"><span data-stu-id="05dba-140">3</span></span></p></td>
<td><p><span data-ttu-id="05dba-141">Аниграуп</span><span class="sxs-lookup"><span data-stu-id="05dba-141">AnyGroup</span></span></p></td>
<td><p><span data-ttu-id="05dba-142">Универсальный принципал с семантикой группы.</span><span class="sxs-lookup"><span data-stu-id="05dba-142">Generic principal with group semantic.</span></span> <span data-ttu-id="05dba-143">Не используется в таблице ТблпринЦипал.</span><span class="sxs-lookup"><span data-stu-id="05dba-143">Not used in tblPrincipal table.</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="05dba-144">4</span><span class="sxs-lookup"><span data-stu-id="05dba-144">4</span></span></p></td>
<td><p><span data-ttu-id="05dba-145">Системусер</span><span class="sxs-lookup"><span data-stu-id="05dba-145">SystemUser</span></span></p></td>
<td><p><span data-ttu-id="05dba-146">Основной сервер, который используется для внутренних целей с помощью сохраняемого сервера чата.</span><span class="sxs-lookup"><span data-stu-id="05dba-146">Principal used internally by Persistent Chat Server.</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="05dba-147">5</span><span class="sxs-lookup"><span data-stu-id="05dba-147">5</span></span></p></td>
<td><p><span data-ttu-id="05dba-148">Пользователь</span><span class="sxs-lookup"><span data-stu-id="05dba-148">User</span></span></p></td>
<td><p><span data-ttu-id="05dba-149">Обычный пользователь.</span><span class="sxs-lookup"><span data-stu-id="05dba-149">Regular user.</span></span></p></td>
<td><p><span data-ttu-id="05dba-150">Да</span><span class="sxs-lookup"><span data-stu-id="05dba-150">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="05dba-151">No8</span><span class="sxs-lookup"><span data-stu-id="05dba-151">8</span></span></p></td>
<td><p><span data-ttu-id="05dba-152">NУДАЛЕННЫЙ</span><span class="sxs-lookup"><span data-stu-id="05dba-152">DC</span></span></p></td>
<td><p><span data-ttu-id="05dba-153">Контроллер домена доменных служб Active Directory.</span><span class="sxs-lookup"><span data-stu-id="05dba-153">Active Directory Domain Services domain controller.</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="05dba-154">@</span><span class="sxs-lookup"><span data-stu-id="05dba-154">9</span></span></p></td>
<td><p><span data-ttu-id="05dba-155">Сгруппирован</span><span class="sxs-lookup"><span data-stu-id="05dba-155">Group</span></span></p></td>
<td><p><span data-ttu-id="05dba-156">Группа безопасности Active Directory.</span><span class="sxs-lookup"><span data-stu-id="05dba-156">Active Directory security group.</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="05dba-157">5-10</span><span class="sxs-lookup"><span data-stu-id="05dba-157">10</span></span></p></td>
<td><p><span data-ttu-id="05dba-158">Нее</span><span class="sxs-lookup"><span data-stu-id="05dba-158">Folder</span></span></p></td>
<td><p><span data-ttu-id="05dba-159">Контейнер Active Directory или подразделение.</span><span class="sxs-lookup"><span data-stu-id="05dba-159">Active Directory container or organizational unit.</span></span></p></td>
<td></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a><span data-ttu-id="05dba-160">См. также</span><span class="sxs-lookup"><span data-stu-id="05dba-160">See Also</span></span>


[<span data-ttu-id="05dba-161">tblPrincipal в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="05dba-161">tblPrincipal in Lync Server 2013</span></span>](lync-server-2013-tblprincipal.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

