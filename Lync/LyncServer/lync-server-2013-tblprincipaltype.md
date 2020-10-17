---
title: 'Lync Server 2013: tblPrincipalType'
description: 'Lync Server 2013: tblPrincipalType.'
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
ms.openlocfilehash: ba0f607d4499b54b16d7ecf8a4e7de603e874788
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48549865"
---
# <a name="tblprincipaltype-in-lync-server-2013"></a><span data-ttu-id="fc8eb-103">tblPrincipalType в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fc8eb-103">tblPrincipalType in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fc8eb-104">_**Последнее изменение темы:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="fc8eb-104">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="fc8eb-105">Таблица tblPrincipalType содержит типы субъектов для разделения содержимого таблицы tblPrincipal по категориям.</span><span class="sxs-lookup"><span data-stu-id="fc8eb-105">tblPrincipalType contains principal types to categorize what is in the tblPrincipal table.</span></span>

### <a name="columns"></a><span data-ttu-id="fc8eb-106">Столбцы</span><span class="sxs-lookup"><span data-stu-id="fc8eb-106">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fc8eb-107">Столбец</span><span class="sxs-lookup"><span data-stu-id="fc8eb-107">Column</span></span></th>
<th><span data-ttu-id="fc8eb-108">Тип</span><span class="sxs-lookup"><span data-stu-id="fc8eb-108">Type</span></span></th>
<th><span data-ttu-id="fc8eb-109">Описание</span><span class="sxs-lookup"><span data-stu-id="fc8eb-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fc8eb-110">птипеид</span><span class="sxs-lookup"><span data-stu-id="fc8eb-110">ptypeID</span></span></p></td>
<td><p><span data-ttu-id="fc8eb-111">smallint, не может быть null</span><span class="sxs-lookup"><span data-stu-id="fc8eb-111">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="fc8eb-112">Идентификатор типа субъекта.</span><span class="sxs-lookup"><span data-stu-id="fc8eb-112">Principal type ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fc8eb-113">птипедеск</span><span class="sxs-lookup"><span data-stu-id="fc8eb-113">ptypeDesc</span></span></p></td>
<td><p><span data-ttu-id="fc8eb-114">nvarchar (256), не может быть null</span><span class="sxs-lookup"><span data-stu-id="fc8eb-114">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="fc8eb-115">Описание типа.</span><span class="sxs-lookup"><span data-stu-id="fc8eb-115">Description of the type.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fc8eb-116">птипеиссистемусер</span><span class="sxs-lookup"><span data-stu-id="fc8eb-116">ptypeIsSystemUser</span></span></p></td>
<td><p><span data-ttu-id="fc8eb-117">bit, не может быть null</span><span class="sxs-lookup"><span data-stu-id="fc8eb-117">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="fc8eb-118">Имеет значение True, если тип соответствует субъектам, которые используются во внутренних целях.</span><span class="sxs-lookup"><span data-stu-id="fc8eb-118">True if the type corresponds to the principals that are used for internal purposes.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fc8eb-119">птипеисусер</span><span class="sxs-lookup"><span data-stu-id="fc8eb-119">ptypeIsUser</span></span></p></td>
<td><p><span data-ttu-id="fc8eb-120">bit, не может быть null</span><span class="sxs-lookup"><span data-stu-id="fc8eb-120">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="fc8eb-121">Имеет значение True, если тип соответствует пользователям.</span><span class="sxs-lookup"><span data-stu-id="fc8eb-121">True if the type is a user type.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="fc8eb-122">Key</span><span class="sxs-lookup"><span data-stu-id="fc8eb-122">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fc8eb-123">Столбец</span><span class="sxs-lookup"><span data-stu-id="fc8eb-123">Column</span></span></th>
<th><span data-ttu-id="fc8eb-124">Описание</span><span class="sxs-lookup"><span data-stu-id="fc8eb-124">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fc8eb-125">птипеид</span><span class="sxs-lookup"><span data-stu-id="fc8eb-125">ptypeID</span></span></p></td>
<td><p><span data-ttu-id="fc8eb-126">Первичный ключ.</span><span class="sxs-lookup"><span data-stu-id="fc8eb-126">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="principal-values"></a><span data-ttu-id="fc8eb-127">Значения субъектов</span><span class="sxs-lookup"><span data-stu-id="fc8eb-127">Principal Values</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fc8eb-128">ID</span><span class="sxs-lookup"><span data-stu-id="fc8eb-128">ID</span></span></th>
<th><span data-ttu-id="fc8eb-129">Role</span><span class="sxs-lookup"><span data-stu-id="fc8eb-129">Role</span></span></th>
<th><span data-ttu-id="fc8eb-130">Описание</span><span class="sxs-lookup"><span data-stu-id="fc8eb-130">Description</span></span></th>
<th><span data-ttu-id="fc8eb-131">Пользователь</span><span class="sxs-lookup"><span data-stu-id="fc8eb-131">User</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fc8eb-132">1,1</span><span class="sxs-lookup"><span data-stu-id="fc8eb-132">1</span></span></p></td>
<td><p><span data-ttu-id="fc8eb-133">Любой</span><span class="sxs-lookup"><span data-stu-id="fc8eb-133">Any</span></span></p></td>
<td><p><span data-ttu-id="fc8eb-p101">Общий субъект неизвестного типа. Не используется в таблице tblPrincipal.</span><span class="sxs-lookup"><span data-stu-id="fc8eb-p101">Generic principal with no known type. Not used in tblPrincipal table.</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fc8eb-136">2</span><span class="sxs-lookup"><span data-stu-id="fc8eb-136">2</span></span></p></td>
<td><p><span data-ttu-id="fc8eb-137">анюсер</span><span class="sxs-lookup"><span data-stu-id="fc8eb-137">AnyUser</span></span></p></td>
<td><p><span data-ttu-id="fc8eb-p102">Общий субъект типа "пользователь". Не используется в таблице tblPrincipal.</span><span class="sxs-lookup"><span data-stu-id="fc8eb-p102">Generic principal of user type. Not used in tblPrincipal table.</span></span></p></td>
<td><p><span data-ttu-id="fc8eb-140">Да</span><span class="sxs-lookup"><span data-stu-id="fc8eb-140">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fc8eb-141">4</span><span class="sxs-lookup"><span data-stu-id="fc8eb-141">3</span></span></p></td>
<td><p><span data-ttu-id="fc8eb-142">аниграуп</span><span class="sxs-lookup"><span data-stu-id="fc8eb-142">AnyGroup</span></span></p></td>
<td><p><span data-ttu-id="fc8eb-p103">Общий субъект типа "группа". Не используется в таблице tblPrincipal.</span><span class="sxs-lookup"><span data-stu-id="fc8eb-p103">Generic principal with group semantic. Not used in tblPrincipal table.</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fc8eb-145">4 </span><span class="sxs-lookup"><span data-stu-id="fc8eb-145">4</span></span></p></td>
<td><p><span data-ttu-id="fc8eb-146">системусер</span><span class="sxs-lookup"><span data-stu-id="fc8eb-146">SystemUser</span></span></p></td>
<td><p><span data-ttu-id="fc8eb-147">Субъект, используемый сервером сохраняемого чата для внутреннего использования.</span><span class="sxs-lookup"><span data-stu-id="fc8eb-147">Principal used internally by Persistent Chat Server.</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fc8eb-148">5 </span><span class="sxs-lookup"><span data-stu-id="fc8eb-148">5</span></span></p></td>
<td><p><span data-ttu-id="fc8eb-149">Пользователь</span><span class="sxs-lookup"><span data-stu-id="fc8eb-149">User</span></span></p></td>
<td><p><span data-ttu-id="fc8eb-150">Обычный пользователь.</span><span class="sxs-lookup"><span data-stu-id="fc8eb-150">Regular user.</span></span></p></td>
<td><p><span data-ttu-id="fc8eb-151">Да</span><span class="sxs-lookup"><span data-stu-id="fc8eb-151">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fc8eb-152">8 </span><span class="sxs-lookup"><span data-stu-id="fc8eb-152">8</span></span></p></td>
<td><p><span data-ttu-id="fc8eb-153">DC</span><span class="sxs-lookup"><span data-stu-id="fc8eb-153">DC</span></span></p></td>
<td><p><span data-ttu-id="fc8eb-154">Контроллер домена доменных служб Active Directory.</span><span class="sxs-lookup"><span data-stu-id="fc8eb-154">Active Directory Domain Services domain controller.</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fc8eb-155">9 </span><span class="sxs-lookup"><span data-stu-id="fc8eb-155">9</span></span></p></td>
<td><p><span data-ttu-id="fc8eb-156">Группа</span><span class="sxs-lookup"><span data-stu-id="fc8eb-156">Group</span></span></p></td>
<td><p><span data-ttu-id="fc8eb-157">Группа безопасности Active Directory.</span><span class="sxs-lookup"><span data-stu-id="fc8eb-157">Active Directory security group.</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fc8eb-158">10 </span><span class="sxs-lookup"><span data-stu-id="fc8eb-158">10</span></span></p></td>
<td><p><span data-ttu-id="fc8eb-159">Folder</span><span class="sxs-lookup"><span data-stu-id="fc8eb-159">Folder</span></span></p></td>
<td><p><span data-ttu-id="fc8eb-160">Контейнер или подразделение Active Directory.</span><span class="sxs-lookup"><span data-stu-id="fc8eb-160">Active Directory container or organizational unit.</span></span></p></td>
<td></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a><span data-ttu-id="fc8eb-161">См. также</span><span class="sxs-lookup"><span data-stu-id="fc8eb-161">See Also</span></span>


[<span data-ttu-id="fc8eb-162">tblPrincipal в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fc8eb-162">tblPrincipal in Lync Server 2013</span></span>](lync-server-2013-tblprincipal.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

