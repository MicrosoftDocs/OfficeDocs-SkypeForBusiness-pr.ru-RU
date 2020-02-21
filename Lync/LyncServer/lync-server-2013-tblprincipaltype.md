---
title: 'Lync Server 2013: tblPrincipalType'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblPrincipalType
ms:assetid: 32e1c1d6-80f4-4624-bf4e-b4c77d3982fa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558633(v=OCS.15)
ms:contentKeyID: 48183787
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0de18da521bd4dadc63d5be592009bd60b643e7b
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42195162"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="tblprincipaltype-in-lync-server-2013"></a><span data-ttu-id="0d491-102">tblPrincipalType в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0d491-102">tblPrincipalType in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0d491-103">_**Последнее изменение темы:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="0d491-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="0d491-104">Таблица tblPrincipalType содержит типы субъектов для разделения содержимого таблицы tblPrincipal по категориям.</span><span class="sxs-lookup"><span data-stu-id="0d491-104">tblPrincipalType contains principal types to categorize what is in the tblPrincipal table.</span></span>

### <a name="columns"></a><span data-ttu-id="0d491-105">Columns</span><span class="sxs-lookup"><span data-stu-id="0d491-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0d491-106">Столбец</span><span class="sxs-lookup"><span data-stu-id="0d491-106">Column</span></span></th>
<th><span data-ttu-id="0d491-107">Тип</span><span class="sxs-lookup"><span data-stu-id="0d491-107">Type</span></span></th>
<th><span data-ttu-id="0d491-108">Описание</span><span class="sxs-lookup"><span data-stu-id="0d491-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0d491-109">птипеид</span><span class="sxs-lookup"><span data-stu-id="0d491-109">ptypeID</span></span></p></td>
<td><p><span data-ttu-id="0d491-110">smallint, не может быть null</span><span class="sxs-lookup"><span data-stu-id="0d491-110">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="0d491-111">Идентификатор типа субъекта.</span><span class="sxs-lookup"><span data-stu-id="0d491-111">Principal type ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0d491-112">птипедеск</span><span class="sxs-lookup"><span data-stu-id="0d491-112">ptypeDesc</span></span></p></td>
<td><p><span data-ttu-id="0d491-113">nvarchar (256), не может быть null</span><span class="sxs-lookup"><span data-stu-id="0d491-113">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="0d491-114">Описание типа.</span><span class="sxs-lookup"><span data-stu-id="0d491-114">Description of the type.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0d491-115">птипеиссистемусер</span><span class="sxs-lookup"><span data-stu-id="0d491-115">ptypeIsSystemUser</span></span></p></td>
<td><p><span data-ttu-id="0d491-116">bit, не равно null</span><span class="sxs-lookup"><span data-stu-id="0d491-116">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="0d491-117">Имеет значение True, если тип соответствует субъектам, которые используются во внутренних целях.</span><span class="sxs-lookup"><span data-stu-id="0d491-117">True if the type corresponds to the principals that are used for internal purposes.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0d491-118">птипеисусер</span><span class="sxs-lookup"><span data-stu-id="0d491-118">ptypeIsUser</span></span></p></td>
<td><p><span data-ttu-id="0d491-119">bit, не может быть null</span><span class="sxs-lookup"><span data-stu-id="0d491-119">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="0d491-120">Имеет значение True, если тип соответствует пользователям.</span><span class="sxs-lookup"><span data-stu-id="0d491-120">True if the type is a user type.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="0d491-121">Key</span><span class="sxs-lookup"><span data-stu-id="0d491-121">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0d491-122">Столбец</span><span class="sxs-lookup"><span data-stu-id="0d491-122">Column</span></span></th>
<th><span data-ttu-id="0d491-123">Описание</span><span class="sxs-lookup"><span data-stu-id="0d491-123">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0d491-124">птипеид</span><span class="sxs-lookup"><span data-stu-id="0d491-124">ptypeID</span></span></p></td>
<td><p><span data-ttu-id="0d491-125">Первичный ключ.</span><span class="sxs-lookup"><span data-stu-id="0d491-125">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="principal-values"></a><span data-ttu-id="0d491-126">Значения субъектов</span><span class="sxs-lookup"><span data-stu-id="0d491-126">Principal Values</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0d491-127">ID</span><span class="sxs-lookup"><span data-stu-id="0d491-127">ID</span></span></th>
<th><span data-ttu-id="0d491-128">Роль</span><span class="sxs-lookup"><span data-stu-id="0d491-128">Role</span></span></th>
<th><span data-ttu-id="0d491-129">Описание</span><span class="sxs-lookup"><span data-stu-id="0d491-129">Description</span></span></th>
<th><span data-ttu-id="0d491-130">Пользователь</span><span class="sxs-lookup"><span data-stu-id="0d491-130">User</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0d491-131">1,1</span><span class="sxs-lookup"><span data-stu-id="0d491-131">1</span></span></p></td>
<td><p><span data-ttu-id="0d491-132">Любые</span><span class="sxs-lookup"><span data-stu-id="0d491-132">Any</span></span></p></td>
<td><p><span data-ttu-id="0d491-p101">Общий субъект неизвестного типа. Не используется в таблице tblPrincipal.</span><span class="sxs-lookup"><span data-stu-id="0d491-p101">Generic principal with no known type. Not used in tblPrincipal table.</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0d491-135">2</span><span class="sxs-lookup"><span data-stu-id="0d491-135">2</span></span></p></td>
<td><p><span data-ttu-id="0d491-136">анюсер</span><span class="sxs-lookup"><span data-stu-id="0d491-136">AnyUser</span></span></p></td>
<td><p><span data-ttu-id="0d491-p102">Общий субъект типа "пользователь". Не используется в таблице tblPrincipal.</span><span class="sxs-lookup"><span data-stu-id="0d491-p102">Generic principal of user type. Not used in tblPrincipal table.</span></span></p></td>
<td><p><span data-ttu-id="0d491-139">Да</span><span class="sxs-lookup"><span data-stu-id="0d491-139">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0d491-140">4</span><span class="sxs-lookup"><span data-stu-id="0d491-140">3</span></span></p></td>
<td><p><span data-ttu-id="0d491-141">аниграуп</span><span class="sxs-lookup"><span data-stu-id="0d491-141">AnyGroup</span></span></p></td>
<td><p><span data-ttu-id="0d491-p103">Общий субъект типа "группа". Не используется в таблице tblPrincipal.</span><span class="sxs-lookup"><span data-stu-id="0d491-p103">Generic principal with group semantic. Not used in tblPrincipal table.</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0d491-144">SP4</span><span class="sxs-lookup"><span data-stu-id="0d491-144">4</span></span></p></td>
<td><p><span data-ttu-id="0d491-145">системусер</span><span class="sxs-lookup"><span data-stu-id="0d491-145">SystemUser</span></span></p></td>
<td><p><span data-ttu-id="0d491-146">Субъект, используемый сервером сохраняемого чата для внутреннего использования.</span><span class="sxs-lookup"><span data-stu-id="0d491-146">Principal used internally by Persistent Chat Server.</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0d491-147">17:00</span><span class="sxs-lookup"><span data-stu-id="0d491-147">5</span></span></p></td>
<td><p><span data-ttu-id="0d491-148">Пользователь</span><span class="sxs-lookup"><span data-stu-id="0d491-148">User</span></span></p></td>
<td><p><span data-ttu-id="0d491-149">Обычный пользователь.</span><span class="sxs-lookup"><span data-stu-id="0d491-149">Regular user.</span></span></p></td>
<td><p><span data-ttu-id="0d491-150">Да</span><span class="sxs-lookup"><span data-stu-id="0d491-150">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0d491-151">8 </span><span class="sxs-lookup"><span data-stu-id="0d491-151">8</span></span></p></td>
<td><p><span data-ttu-id="0d491-152">DC</span><span class="sxs-lookup"><span data-stu-id="0d491-152">DC</span></span></p></td>
<td><p><span data-ttu-id="0d491-153">Контроллер домена доменных служб Active Directory.</span><span class="sxs-lookup"><span data-stu-id="0d491-153">Active Directory Domain Services domain controller.</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0d491-154">9 </span><span class="sxs-lookup"><span data-stu-id="0d491-154">9</span></span></p></td>
<td><p><span data-ttu-id="0d491-155">Group</span><span class="sxs-lookup"><span data-stu-id="0d491-155">Group</span></span></p></td>
<td><p><span data-ttu-id="0d491-156">Группа безопасности Active Directory.</span><span class="sxs-lookup"><span data-stu-id="0d491-156">Active Directory security group.</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0d491-157">10 </span><span class="sxs-lookup"><span data-stu-id="0d491-157">10</span></span></p></td>
<td><p><span data-ttu-id="0d491-158">Folder</span><span class="sxs-lookup"><span data-stu-id="0d491-158">Folder</span></span></p></td>
<td><p><span data-ttu-id="0d491-159">Контейнер или подразделение Active Directory.</span><span class="sxs-lookup"><span data-stu-id="0d491-159">Active Directory container or organizational unit.</span></span></p></td>
<td></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a><span data-ttu-id="0d491-160">См. также</span><span class="sxs-lookup"><span data-stu-id="0d491-160">See Also</span></span>


[<span data-ttu-id="0d491-161">tblPrincipal в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0d491-161">tblPrincipal in Lync Server 2013</span></span>](lync-server-2013-tblprincipal.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

