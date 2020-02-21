---
title: 'Lync Server 2013: tblNode'
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
ms.openlocfilehash: 459b5393f255ade4e510f17c11beccf2f38f7cfc
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42214554"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="tblnode-in-lync-server-2013"></a><span data-ttu-id="eb093-102">tblNode в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="eb093-102">tblNode in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="eb093-103">_**Последнее изменение темы:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="eb093-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="eb093-104">tblNode содержит дерево объектов (с узлами категории или комнаты чата), которое управляется в панели управления Lync Server 2013 и административные командлеты.</span><span class="sxs-lookup"><span data-stu-id="eb093-104">tblNode contains the object tree (with category or chat room nodes) as managed in the Lync Server 2013 Control Panel and administrative cmdlets.</span></span>

### <a name="columns"></a><span data-ttu-id="eb093-105">Columns</span><span class="sxs-lookup"><span data-stu-id="eb093-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="eb093-106">Столбец</span><span class="sxs-lookup"><span data-stu-id="eb093-106">Column</span></span></th>
<th><span data-ttu-id="eb093-107">Тип</span><span class="sxs-lookup"><span data-stu-id="eb093-107">Type</span></span></th>
<th><span data-ttu-id="eb093-108">Описание</span><span class="sxs-lookup"><span data-stu-id="eb093-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="eb093-109">nodeID</span><span class="sxs-lookup"><span data-stu-id="eb093-109">nodeID</span></span></p></td>
<td><p><span data-ttu-id="eb093-110">int, не null</span><span class="sxs-lookup"><span data-stu-id="eb093-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="eb093-111">ИД узла (уникальное число).</span><span class="sxs-lookup"><span data-stu-id="eb093-111">Node ID (unique number).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eb093-112">нодегуид</span><span class="sxs-lookup"><span data-stu-id="eb093-112">nodeGuid</span></span></p></td>
<td><p><span data-ttu-id="eb093-113">GUID, not null</span><span class="sxs-lookup"><span data-stu-id="eb093-113">GUID, not null</span></span></p></td>
<td><p><span data-ttu-id="eb093-114">Глобальный уникальный ИД узла.</span><span class="sxs-lookup"><span data-stu-id="eb093-114">Node GUID.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eb093-115">parentID</span><span class="sxs-lookup"><span data-stu-id="eb093-115">parentID</span></span></p></td>
<td><p><span data-ttu-id="eb093-116">int</span><span class="sxs-lookup"><span data-stu-id="eb093-116">int</span></span></p></td>
<td><p><span data-ttu-id="eb093-p101">ИД узла родительского элемента. Корневой узел (с ИД 1) включает себя в качестве родительского элемента.</span><span class="sxs-lookup"><span data-stu-id="eb093-p101">Node ID of parent. The root node (with ID 1) includes itself as parent as well.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eb093-119">nodeType</span><span class="sxs-lookup"><span data-stu-id="eb093-119">nodeType</span></span></p></td>
<td><p><span data-ttu-id="eb093-120">bit, не равно null</span><span class="sxs-lookup"><span data-stu-id="eb093-120">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="eb093-121">True, если узел является категорией.</span><span class="sxs-lookup"><span data-stu-id="eb093-121">True if the node is a category.</span></span></p>
<p><span data-ttu-id="eb093-122">False, если узел является комнатой чата.</span><span class="sxs-lookup"><span data-stu-id="eb093-122">False if the node is a chat room.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eb093-123">nodeName</span><span class="sxs-lookup"><span data-stu-id="eb093-123">nodeName</span></span></p></td>
<td><p><span data-ttu-id="eb093-124">nvarchar (256), не может быть null</span><span class="sxs-lookup"><span data-stu-id="eb093-124">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="eb093-125">Имя узла.</span><span class="sxs-lookup"><span data-stu-id="eb093-125">Node name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eb093-126">нодедеск</span><span class="sxs-lookup"><span data-stu-id="eb093-126">nodeDesc</span></span></p></td>
<td><p><span data-ttu-id="eb093-127">nvarchar (256), not null</span><span class="sxs-lookup"><span data-stu-id="eb093-127">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="eb093-128">Описание узла.</span><span class="sxs-lookup"><span data-stu-id="eb093-128">Node description.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eb093-129">invite</span><span class="sxs-lookup"><span data-stu-id="eb093-129">invite</span></span></p></td>
<td><p><span data-ttu-id="eb093-130">Битовая</span><span class="sxs-lookup"><span data-stu-id="eb093-130">bit</span></span></p></td>
<td><p><span data-ttu-id="eb093-131">Для категорий:</span><span class="sxs-lookup"><span data-stu-id="eb093-131">For categories:</span></span></p>
<ul>
<li><p><span data-ttu-id="eb093-132">True, если приглашения включены.</span><span class="sxs-lookup"><span data-stu-id="eb093-132">True if invites are on.</span></span></p></li>
<li><p><span data-ttu-id="eb093-133">False, если приглашения отключены.</span><span class="sxs-lookup"><span data-stu-id="eb093-133">False if invites are off.</span></span></p></li>
</ul>
<p><span data-ttu-id="eb093-134">Для комнат:</span><span class="sxs-lookup"><span data-stu-id="eb093-134">For rooms:</span></span></p>
<ul>
<li><p><span data-ttu-id="eb093-135">False, если приглашения отключены (переопределяет родительскую категорию).</span><span class="sxs-lookup"><span data-stu-id="eb093-135">False if invites are off (overrides the parent category).</span></span></p></li>
<li><p><span data-ttu-id="eb093-136">Null, если настройки приглашений наследуются от родительской категории.</span><span class="sxs-lookup"><span data-stu-id="eb093-136">Null if the invites setting is inherited from the parent category.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eb093-137">шедших</span><span class="sxs-lookup"><span data-stu-id="eb093-137">logged</span></span></p></td>
<td><p><span data-ttu-id="eb093-138">Битовая</span><span class="sxs-lookup"><span data-stu-id="eb093-138">bit</span></span></p></td>
<td><p><span data-ttu-id="eb093-139">Для категорий:</span><span class="sxs-lookup"><span data-stu-id="eb093-139">For categories:</span></span></p>
<ul>
<li><p><span data-ttu-id="eb093-140">True, если журнал чата включен.</span><span class="sxs-lookup"><span data-stu-id="eb093-140">True if chat history is on.</span></span></p></li>
<li><p><span data-ttu-id="eb093-141">False, если журнал чата отключен.</span><span class="sxs-lookup"><span data-stu-id="eb093-141">False if chat history is off.</span></span></p></li>
</ul>
<p><span data-ttu-id="eb093-142">Для комнат:</span><span class="sxs-lookup"><span data-stu-id="eb093-142">For rooms:</span></span></p>
<ul>
<li><p><span data-ttu-id="eb093-143">Определен.</span><span class="sxs-lookup"><span data-stu-id="eb093-143">Null.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eb093-144">филепост</span><span class="sxs-lookup"><span data-stu-id="eb093-144">filePost</span></span></p></td>
<td><p><span data-ttu-id="eb093-145">Битовая</span><span class="sxs-lookup"><span data-stu-id="eb093-145">bit</span></span></p></td>
<td><p><span data-ttu-id="eb093-146">Для категорий:</span><span class="sxs-lookup"><span data-stu-id="eb093-146">For categories:</span></span></p>
<ul>
<li><p><span data-ttu-id="eb093-147">True, если передача файлов разрешена.</span><span class="sxs-lookup"><span data-stu-id="eb093-147">True if file uploads are allowed.</span></span></p></li>
<li><p><span data-ttu-id="eb093-148">False, если передача файлов запрещена.</span><span class="sxs-lookup"><span data-stu-id="eb093-148">False if file uploads are disallowed.</span></span></p></li>
</ul>
<p><span data-ttu-id="eb093-149">Для комнат:</span><span class="sxs-lookup"><span data-stu-id="eb093-149">For rooms:</span></span></p>
<ul>
<li><p><span data-ttu-id="eb093-150">Определен.</span><span class="sxs-lookup"><span data-stu-id="eb093-150">Null.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eb093-151">активирован</span><span class="sxs-lookup"><span data-stu-id="eb093-151">disabled</span></span></p></td>
<td><p><span data-ttu-id="eb093-152">bit, not null</span><span class="sxs-lookup"><span data-stu-id="eb093-152">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="eb093-p102">True, если комната чата отключена. Применяется только к комнатам чата. (Для категорий — False.)</span><span class="sxs-lookup"><span data-stu-id="eb093-p102">True if the chat room is disabled. Applies only to chat rooms. (False for categories.)</span></span></p></td>
</tr>
<tr class="odd">
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eb093-156">такое</span><span class="sxs-lookup"><span data-stu-id="eb093-156">behavior</span></span></p></td>
<td><p><span data-ttu-id="eb093-157">smallint, не может быть null</span><span class="sxs-lookup"><span data-stu-id="eb093-157">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="eb093-158">Поведение (поиск в таблице EnumValue):</span><span class="sxs-lookup"><span data-stu-id="eb093-158">Behavior (looked up in EnumValue table):</span></span></p>
<ul>
<li><p><span data-ttu-id="eb093-159">4: Normal (обычные комнаты чата).</span><span class="sxs-lookup"><span data-stu-id="eb093-159">4: Normal (normal chat rooms).</span></span></p></li>
<li><p><span data-ttu-id="eb093-160">5: Auditorium (комнаты чата аудитории, участвовать могут только докладчики).</span><span class="sxs-lookup"><span data-stu-id="eb093-160">5: Auditorium (auditorium chat rooms, only presenters can contribute).</span></span></p></li>
</ul>
<p><span data-ttu-id="eb093-161">Применимо только к комнатам чата.</span><span class="sxs-lookup"><span data-stu-id="eb093-161">Applies only to chat rooms.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eb093-162">visibility</span><span class="sxs-lookup"><span data-stu-id="eb093-162">visibility</span></span></p></td>
<td><p><span data-ttu-id="eb093-163">smallint, not null</span><span class="sxs-lookup"><span data-stu-id="eb093-163">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="eb093-164">Видимость (поиск в таблице EnumValue):</span><span class="sxs-lookup"><span data-stu-id="eb093-164">Visibility (looked up on EnumValue table):</span></span></p>
<ul>
<li><p><span data-ttu-id="eb093-165">2: Private</span><span class="sxs-lookup"><span data-stu-id="eb093-165">2: Private</span></span></p></li>
<li><p><span data-ttu-id="eb093-166">3: Scoped</span><span class="sxs-lookup"><span data-stu-id="eb093-166">3: Scoped</span></span></p></li>
<li><p><span data-ttu-id="eb093-167">6: Open</span><span class="sxs-lookup"><span data-stu-id="eb093-167">6: Open</span></span></p></li>
</ul>
<p><span data-ttu-id="eb093-168">Применяется только для комнат чата.</span><span class="sxs-lookup"><span data-stu-id="eb093-168">Applies only to chat rooms.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eb093-169">сиопид</span><span class="sxs-lookup"><span data-stu-id="eb093-169">siopID</span></span></p></td>
<td><p><span data-ttu-id="eb093-170">GUID</span><span class="sxs-lookup"><span data-stu-id="eb093-170">GUID</span></span></p></td>
<td><p><span data-ttu-id="eb093-p103">Глобальный уникальный ИД надстройки, если надстройка связана с этой комнатой чата. (Категории не имеют надстроек.)</span><span class="sxs-lookup"><span data-stu-id="eb093-p103">Add-In GUID if an add-in is associated with this chat room. (Categories do not have add-ins.)</span></span></p>
<p><span data-ttu-id="eb093-173">Для поиска сведений о надстройках используется таблица SiopWhiteList.</span><span class="sxs-lookup"><span data-stu-id="eb093-173">The add-in information is looked up in SiopWhiteList table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eb093-174">нодеаддедби</span><span class="sxs-lookup"><span data-stu-id="eb093-174">nodeAddedBy</span></span></p></td>
<td><p><span data-ttu-id="eb093-175">int, not null</span><span class="sxs-lookup"><span data-stu-id="eb093-175">int, not null</span></span></p></td>
<td><p><span data-ttu-id="eb093-176">ИД субъекта, который создал этот узел.</span><span class="sxs-lookup"><span data-stu-id="eb093-176">ID of the principal that created this node.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eb093-177">нодеаддедон</span><span class="sxs-lookup"><span data-stu-id="eb093-177">nodeAddedOn</span></span></p></td>
<td><p><span data-ttu-id="eb093-178">bigint, not null</span><span class="sxs-lookup"><span data-stu-id="eb093-178">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="eb093-179">Метка времени создания узла.</span><span class="sxs-lookup"><span data-stu-id="eb093-179">Time stamp of the node creation.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eb093-180">нодеупдатедби</span><span class="sxs-lookup"><span data-stu-id="eb093-180">nodeUpdatedBy</span></span></p></td>
<td><p><span data-ttu-id="eb093-181">int, not null</span><span class="sxs-lookup"><span data-stu-id="eb093-181">int, not null</span></span></p></td>
<td><p><span data-ttu-id="eb093-182">ИД субъекта, который выполнил последнее обновление этого узла.</span><span class="sxs-lookup"><span data-stu-id="eb093-182">ID of the principal that did the latest update of this node.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eb093-183">нодеупдатедон</span><span class="sxs-lookup"><span data-stu-id="eb093-183">nodeUpdatedOn</span></span></p></td>
<td><p><span data-ttu-id="eb093-184">bigint, not null</span><span class="sxs-lookup"><span data-stu-id="eb093-184">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="eb093-185">Метка времени последнего обновления этого узла.</span><span class="sxs-lookup"><span data-stu-id="eb093-185">Time stamp of the latest update of this node.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eb093-186">пуржедон</span><span class="sxs-lookup"><span data-stu-id="eb093-186">purgedOn</span></span></p></td>
<td><p><span data-ttu-id="eb093-187">datetime</span><span class="sxs-lookup"><span data-stu-id="eb093-187">datetime</span></span></p></td>
<td><p><span data-ttu-id="eb093-p104">Время последней операции очистки (удаление областей из таблицы tblScopedPrincipal и ролей из таблицы tblPrincipalRole) для этого узла. Используется механизмом обновления внутреннего кэша службы чата.</span><span class="sxs-lookup"><span data-stu-id="eb093-p104">Time of the latest purge operation (removal of scopes from tblScopedPrincipal table and roles from tblPrincipalRole table) that affected this node. This is used by the Chat service’s internal cache update mechanism.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="eb093-190">Keys</span><span class="sxs-lookup"><span data-stu-id="eb093-190">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="eb093-191">Столбец</span><span class="sxs-lookup"><span data-stu-id="eb093-191">Column</span></span></th>
<th><span data-ttu-id="eb093-192">Описание</span><span class="sxs-lookup"><span data-stu-id="eb093-192">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="eb093-193">nodeID</span><span class="sxs-lookup"><span data-stu-id="eb093-193">nodeID</span></span></p></td>
<td><p><span data-ttu-id="eb093-194">Первичный ключ.</span><span class="sxs-lookup"><span data-stu-id="eb093-194">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eb093-195">такое</span><span class="sxs-lookup"><span data-stu-id="eb093-195">behavior</span></span></p></td>
<td><p><span data-ttu-id="eb093-196">Внешний ключ с поиском в таблице tblEnumValue.valueID.</span><span class="sxs-lookup"><span data-stu-id="eb093-196">Foreign key with lookup in tblEnumValue.valueID table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eb093-197">visibility</span><span class="sxs-lookup"><span data-stu-id="eb093-197">visibility</span></span></p></td>
<td><p><span data-ttu-id="eb093-198">Внешний ключ с поиском в таблице tblEnumValue.valueID.</span><span class="sxs-lookup"><span data-stu-id="eb093-198">Foreign key with lookup in tblEnumValue.valueID table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eb093-199">parentID</span><span class="sxs-lookup"><span data-stu-id="eb093-199">parentID</span></span></p></td>
<td><p><span data-ttu-id="eb093-200">Внешний ключ с поиском в таблице tblNode.nodeID.</span><span class="sxs-lookup"><span data-stu-id="eb093-200">Foreign key with lookup in tblNode.nodeID table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eb093-201">сиопид</span><span class="sxs-lookup"><span data-stu-id="eb093-201">siopID</span></span></p></td>
<td><p><span data-ttu-id="eb093-202">Внешний ключ с поиском в таблице tblSiopWhiteList.siopId.</span><span class="sxs-lookup"><span data-stu-id="eb093-202">Foreign key with lookup in tblSiopWhiteList.siopId table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

