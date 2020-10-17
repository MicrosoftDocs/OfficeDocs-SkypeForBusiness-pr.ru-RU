---
title: 'Lync Server 2013: tblNode'
description: 'Lync Server 2013: tblNode.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblNode
ms:assetid: a31d2961-aa83-4286-a12e-15d279c95f19
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615024(v=OCS.15)
ms:contentKeyID: 48184960
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d0a5d630621c32cbc54501249c7a679bf4023c60
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547555"
---
# <a name="tblnode-in-lync-server-2013"></a><span data-ttu-id="f36c3-103">tblNode в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f36c3-103">tblNode in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f36c3-104">_**Последнее изменение темы:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="f36c3-104">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="f36c3-105">tblNode содержит дерево объектов (с узлами категории или комнаты чата), которое управляется в панели управления Lync Server 2013 и административные командлеты.</span><span class="sxs-lookup"><span data-stu-id="f36c3-105">tblNode contains the object tree (with category or chat room nodes) as managed in the Lync Server 2013 Control Panel and administrative cmdlets.</span></span>

### <a name="columns"></a><span data-ttu-id="f36c3-106">Столбцы</span><span class="sxs-lookup"><span data-stu-id="f36c3-106">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f36c3-107">Столбец</span><span class="sxs-lookup"><span data-stu-id="f36c3-107">Column</span></span></th>
<th><span data-ttu-id="f36c3-108">Тип</span><span class="sxs-lookup"><span data-stu-id="f36c3-108">Type</span></span></th>
<th><span data-ttu-id="f36c3-109">Описание</span><span class="sxs-lookup"><span data-stu-id="f36c3-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f36c3-110">nodeID</span><span class="sxs-lookup"><span data-stu-id="f36c3-110">nodeID</span></span></p></td>
<td><p><span data-ttu-id="f36c3-111">int, not null</span><span class="sxs-lookup"><span data-stu-id="f36c3-111">int, not null</span></span></p></td>
<td><p><span data-ttu-id="f36c3-112">ИД узла (уникальное число).</span><span class="sxs-lookup"><span data-stu-id="f36c3-112">Node ID (unique number).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f36c3-113">нодегуид</span><span class="sxs-lookup"><span data-stu-id="f36c3-113">nodeGuid</span></span></p></td>
<td><p><span data-ttu-id="f36c3-114">GUID, not null</span><span class="sxs-lookup"><span data-stu-id="f36c3-114">GUID, not null</span></span></p></td>
<td><p><span data-ttu-id="f36c3-115">Глобальный уникальный ИД узла.</span><span class="sxs-lookup"><span data-stu-id="f36c3-115">Node GUID.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f36c3-116">parentID</span><span class="sxs-lookup"><span data-stu-id="f36c3-116">parentID</span></span></p></td>
<td><p><span data-ttu-id="f36c3-117">int</span><span class="sxs-lookup"><span data-stu-id="f36c3-117">int</span></span></p></td>
<td><p><span data-ttu-id="f36c3-p101">ИД узла родительского элемента. Корневой узел (с ИД 1) включает себя в качестве родительского элемента.</span><span class="sxs-lookup"><span data-stu-id="f36c3-p101">Node ID of parent. The root node (with ID 1) includes itself as parent as well.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f36c3-120">nodeType</span><span class="sxs-lookup"><span data-stu-id="f36c3-120">nodeType</span></span></p></td>
<td><p><span data-ttu-id="f36c3-121">bit, not null</span><span class="sxs-lookup"><span data-stu-id="f36c3-121">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="f36c3-122">True, если узел является категорией.</span><span class="sxs-lookup"><span data-stu-id="f36c3-122">True if the node is a category.</span></span></p>
<p><span data-ttu-id="f36c3-123">False, если узел является комнатой чата.</span><span class="sxs-lookup"><span data-stu-id="f36c3-123">False if the node is a chat room.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f36c3-124">nodeName</span><span class="sxs-lookup"><span data-stu-id="f36c3-124">nodeName</span></span></p></td>
<td><p><span data-ttu-id="f36c3-125">nvarchar (256), not null</span><span class="sxs-lookup"><span data-stu-id="f36c3-125">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="f36c3-126">Имя узла.</span><span class="sxs-lookup"><span data-stu-id="f36c3-126">Node name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f36c3-127">нодедеск</span><span class="sxs-lookup"><span data-stu-id="f36c3-127">nodeDesc</span></span></p></td>
<td><p><span data-ttu-id="f36c3-128">nvarchar (256), not null</span><span class="sxs-lookup"><span data-stu-id="f36c3-128">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="f36c3-129">Описание узла.</span><span class="sxs-lookup"><span data-stu-id="f36c3-129">Node description.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f36c3-130">invite</span><span class="sxs-lookup"><span data-stu-id="f36c3-130">invite</span></span></p></td>
<td><p><span data-ttu-id="f36c3-131">Битовая</span><span class="sxs-lookup"><span data-stu-id="f36c3-131">bit</span></span></p></td>
<td><p><span data-ttu-id="f36c3-132">Для категорий:</span><span class="sxs-lookup"><span data-stu-id="f36c3-132">For categories:</span></span></p>
<ul>
<li><p><span data-ttu-id="f36c3-133">True, если приглашения включены.</span><span class="sxs-lookup"><span data-stu-id="f36c3-133">True if invites are on.</span></span></p></li>
<li><p><span data-ttu-id="f36c3-134">False, если приглашения отключены.</span><span class="sxs-lookup"><span data-stu-id="f36c3-134">False if invites are off.</span></span></p></li>
</ul>
<p><span data-ttu-id="f36c3-135">Для комнат:</span><span class="sxs-lookup"><span data-stu-id="f36c3-135">For rooms:</span></span></p>
<ul>
<li><p><span data-ttu-id="f36c3-136">False, если приглашения отключены (переопределяет родительскую категорию).</span><span class="sxs-lookup"><span data-stu-id="f36c3-136">False if invites are off (overrides the parent category).</span></span></p></li>
<li><p><span data-ttu-id="f36c3-137">Null, если настройки приглашений наследуются от родительской категории.</span><span class="sxs-lookup"><span data-stu-id="f36c3-137">Null if the invites setting is inherited from the parent category.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f36c3-138">шедших</span><span class="sxs-lookup"><span data-stu-id="f36c3-138">logged</span></span></p></td>
<td><p><span data-ttu-id="f36c3-139">Битовая</span><span class="sxs-lookup"><span data-stu-id="f36c3-139">bit</span></span></p></td>
<td><p><span data-ttu-id="f36c3-140">Для категорий:</span><span class="sxs-lookup"><span data-stu-id="f36c3-140">For categories:</span></span></p>
<ul>
<li><p><span data-ttu-id="f36c3-141">True, если журнал чата включен.</span><span class="sxs-lookup"><span data-stu-id="f36c3-141">True if chat history is on.</span></span></p></li>
<li><p><span data-ttu-id="f36c3-142">False, если журнал чата отключен.</span><span class="sxs-lookup"><span data-stu-id="f36c3-142">False if chat history is off.</span></span></p></li>
</ul>
<p><span data-ttu-id="f36c3-143">Для комнат:</span><span class="sxs-lookup"><span data-stu-id="f36c3-143">For rooms:</span></span></p>
<ul>
<li><p><span data-ttu-id="f36c3-144">Определен.</span><span class="sxs-lookup"><span data-stu-id="f36c3-144">Null.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f36c3-145">филепост</span><span class="sxs-lookup"><span data-stu-id="f36c3-145">filePost</span></span></p></td>
<td><p><span data-ttu-id="f36c3-146">Битовая</span><span class="sxs-lookup"><span data-stu-id="f36c3-146">bit</span></span></p></td>
<td><p><span data-ttu-id="f36c3-147">Для категорий:</span><span class="sxs-lookup"><span data-stu-id="f36c3-147">For categories:</span></span></p>
<ul>
<li><p><span data-ttu-id="f36c3-148">True, если передача файлов разрешена.</span><span class="sxs-lookup"><span data-stu-id="f36c3-148">True if file uploads are allowed.</span></span></p></li>
<li><p><span data-ttu-id="f36c3-149">False, если передача файлов запрещена.</span><span class="sxs-lookup"><span data-stu-id="f36c3-149">False if file uploads are disallowed.</span></span></p></li>
</ul>
<p><span data-ttu-id="f36c3-150">Для комнат:</span><span class="sxs-lookup"><span data-stu-id="f36c3-150">For rooms:</span></span></p>
<ul>
<li><p><span data-ttu-id="f36c3-151">Определен.</span><span class="sxs-lookup"><span data-stu-id="f36c3-151">Null.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f36c3-152">отключено</span><span class="sxs-lookup"><span data-stu-id="f36c3-152">disabled</span></span></p></td>
<td><p><span data-ttu-id="f36c3-153">bit, not null</span><span class="sxs-lookup"><span data-stu-id="f36c3-153">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="f36c3-p102">True, если комната чата отключена. Применяется только к комнатам чата. (Для категорий — False.)</span><span class="sxs-lookup"><span data-stu-id="f36c3-p102">True if the chat room is disabled. Applies only to chat rooms. (False for categories.)</span></span></p></td>
</tr>
<tr class="odd">
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f36c3-157">такое</span><span class="sxs-lookup"><span data-stu-id="f36c3-157">behavior</span></span></p></td>
<td><p><span data-ttu-id="f36c3-158">smallint, not null</span><span class="sxs-lookup"><span data-stu-id="f36c3-158">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="f36c3-159">Поведение (поиск в таблице EnumValue):</span><span class="sxs-lookup"><span data-stu-id="f36c3-159">Behavior (looked up in EnumValue table):</span></span></p>
<ul>
<li><p><span data-ttu-id="f36c3-160">4: Normal (обычные комнаты чата).</span><span class="sxs-lookup"><span data-stu-id="f36c3-160">4: Normal (normal chat rooms).</span></span></p></li>
<li><p><span data-ttu-id="f36c3-161">5: Auditorium (комнаты чата аудитории, участвовать могут только докладчики).</span><span class="sxs-lookup"><span data-stu-id="f36c3-161">5: Auditorium (auditorium chat rooms, only presenters can contribute).</span></span></p></li>
</ul>
<p><span data-ttu-id="f36c3-162">Применимо только к комнатам чата.</span><span class="sxs-lookup"><span data-stu-id="f36c3-162">Applies only to chat rooms.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f36c3-163">visibility</span><span class="sxs-lookup"><span data-stu-id="f36c3-163">visibility</span></span></p></td>
<td><p><span data-ttu-id="f36c3-164">smallint, not null</span><span class="sxs-lookup"><span data-stu-id="f36c3-164">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="f36c3-165">Видимость (поиск в таблице EnumValue):</span><span class="sxs-lookup"><span data-stu-id="f36c3-165">Visibility (looked up on EnumValue table):</span></span></p>
<ul>
<li><p><span data-ttu-id="f36c3-166">2: Private</span><span class="sxs-lookup"><span data-stu-id="f36c3-166">2: Private</span></span></p></li>
<li><p><span data-ttu-id="f36c3-167">3: Scoped</span><span class="sxs-lookup"><span data-stu-id="f36c3-167">3: Scoped</span></span></p></li>
<li><p><span data-ttu-id="f36c3-168">6: Open</span><span class="sxs-lookup"><span data-stu-id="f36c3-168">6: Open</span></span></p></li>
</ul>
<p><span data-ttu-id="f36c3-169">Применяется только для комнат чата.</span><span class="sxs-lookup"><span data-stu-id="f36c3-169">Applies only to chat rooms.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f36c3-170">сиопид</span><span class="sxs-lookup"><span data-stu-id="f36c3-170">siopID</span></span></p></td>
<td><p><span data-ttu-id="f36c3-171">GUID</span><span class="sxs-lookup"><span data-stu-id="f36c3-171">GUID</span></span></p></td>
<td><p><span data-ttu-id="f36c3-p103">Глобальный уникальный ИД надстройки, если надстройка связана с этой комнатой чата. (Категории не имеют надстроек.)</span><span class="sxs-lookup"><span data-stu-id="f36c3-p103">Add-In GUID if an add-in is associated with this chat room. (Categories do not have add-ins.)</span></span></p>
<p><span data-ttu-id="f36c3-174">Для поиска сведений о надстройках используется таблица SiopWhiteList.</span><span class="sxs-lookup"><span data-stu-id="f36c3-174">The add-in information is looked up in SiopWhiteList table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f36c3-175">нодеаддедби</span><span class="sxs-lookup"><span data-stu-id="f36c3-175">nodeAddedBy</span></span></p></td>
<td><p><span data-ttu-id="f36c3-176">int, not null</span><span class="sxs-lookup"><span data-stu-id="f36c3-176">int, not null</span></span></p></td>
<td><p><span data-ttu-id="f36c3-177">ИД субъекта, который создал этот узел.</span><span class="sxs-lookup"><span data-stu-id="f36c3-177">ID of the principal that created this node.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f36c3-178">нодеаддедон</span><span class="sxs-lookup"><span data-stu-id="f36c3-178">nodeAddedOn</span></span></p></td>
<td><p><span data-ttu-id="f36c3-179">bigint, not null</span><span class="sxs-lookup"><span data-stu-id="f36c3-179">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="f36c3-180">Метка времени создания узла.</span><span class="sxs-lookup"><span data-stu-id="f36c3-180">Time stamp of the node creation.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f36c3-181">нодеупдатедби</span><span class="sxs-lookup"><span data-stu-id="f36c3-181">nodeUpdatedBy</span></span></p></td>
<td><p><span data-ttu-id="f36c3-182">int, not null</span><span class="sxs-lookup"><span data-stu-id="f36c3-182">int, not null</span></span></p></td>
<td><p><span data-ttu-id="f36c3-183">ИД субъекта, который выполнил последнее обновление этого узла.</span><span class="sxs-lookup"><span data-stu-id="f36c3-183">ID of the principal that did the latest update of this node.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f36c3-184">нодеупдатедон</span><span class="sxs-lookup"><span data-stu-id="f36c3-184">nodeUpdatedOn</span></span></p></td>
<td><p><span data-ttu-id="f36c3-185">bigint, not null</span><span class="sxs-lookup"><span data-stu-id="f36c3-185">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="f36c3-186">Метка времени последнего обновления этого узла.</span><span class="sxs-lookup"><span data-stu-id="f36c3-186">Time stamp of the latest update of this node.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f36c3-187">пуржедон</span><span class="sxs-lookup"><span data-stu-id="f36c3-187">purgedOn</span></span></p></td>
<td><p><span data-ttu-id="f36c3-188">datetime</span><span class="sxs-lookup"><span data-stu-id="f36c3-188">datetime</span></span></p></td>
<td><p><span data-ttu-id="f36c3-p104">Время последней операции очистки (удаление областей из таблицы tblScopedPrincipal и ролей из таблицы tblPrincipalRole) для этого узла. Используется механизмом обновления внутреннего кэша службы чата.</span><span class="sxs-lookup"><span data-stu-id="f36c3-p104">Time of the latest purge operation (removal of scopes from tblScopedPrincipal table and roles from tblPrincipalRole table) that affected this node. This is used by the Chat service’s internal cache update mechanism.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="f36c3-191">Keys</span><span class="sxs-lookup"><span data-stu-id="f36c3-191">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f36c3-192">Столбец</span><span class="sxs-lookup"><span data-stu-id="f36c3-192">Column</span></span></th>
<th><span data-ttu-id="f36c3-193">Описание</span><span class="sxs-lookup"><span data-stu-id="f36c3-193">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f36c3-194">nodeID</span><span class="sxs-lookup"><span data-stu-id="f36c3-194">nodeID</span></span></p></td>
<td><p><span data-ttu-id="f36c3-195">Первичный ключ.</span><span class="sxs-lookup"><span data-stu-id="f36c3-195">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f36c3-196">такое</span><span class="sxs-lookup"><span data-stu-id="f36c3-196">behavior</span></span></p></td>
<td><p><span data-ttu-id="f36c3-197">Внешний ключ с поиском в таблице tblEnumValue.valueID.</span><span class="sxs-lookup"><span data-stu-id="f36c3-197">Foreign key with lookup in tblEnumValue.valueID table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f36c3-198">visibility</span><span class="sxs-lookup"><span data-stu-id="f36c3-198">visibility</span></span></p></td>
<td><p><span data-ttu-id="f36c3-199">Внешний ключ с поиском в таблице tblEnumValue.valueID.</span><span class="sxs-lookup"><span data-stu-id="f36c3-199">Foreign key with lookup in tblEnumValue.valueID table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f36c3-200">parentID</span><span class="sxs-lookup"><span data-stu-id="f36c3-200">parentID</span></span></p></td>
<td><p><span data-ttu-id="f36c3-201">Внешний ключ с поиском в таблице tblNode.nodeID.</span><span class="sxs-lookup"><span data-stu-id="f36c3-201">Foreign key with lookup in tblNode.nodeID table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f36c3-202">сиопид</span><span class="sxs-lookup"><span data-stu-id="f36c3-202">siopID</span></span></p></td>
<td><p><span data-ttu-id="f36c3-203">Внешний ключ с поиском в таблице tblSiopWhiteList.siopId.</span><span class="sxs-lookup"><span data-stu-id="f36c3-203">Foreign key with lookup in tblSiopWhiteList.siopId table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

