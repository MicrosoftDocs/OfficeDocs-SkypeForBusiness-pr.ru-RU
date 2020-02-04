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
ms.openlocfilehash: 24ba45d9ba650a9de4359d64e3281fb488b6a279
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41731489"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblnode-in-lync-server-2013"></a><span data-ttu-id="bd803-102">tblNode в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bd803-102">tblNode in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bd803-103">_**Тема последнего изменения:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="bd803-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="bd803-104">Тблноде включает дерево объектов (с узлами "Категория" или "комната чата") как управляемое на панели управления Lync Server 2013 и административных командлетов.</span><span class="sxs-lookup"><span data-stu-id="bd803-104">tblNode contains the object tree (with category or chat room nodes) as managed in the Lync Server 2013 Control Panel and administrative cmdlets.</span></span>

### <a name="columns"></a><span data-ttu-id="bd803-105">Столбцов</span><span class="sxs-lookup"><span data-stu-id="bd803-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bd803-106">Столбец</span><span class="sxs-lookup"><span data-stu-id="bd803-106">Column</span></span></th>
<th><span data-ttu-id="bd803-107">Тип</span><span class="sxs-lookup"><span data-stu-id="bd803-107">Type</span></span></th>
<th><span data-ttu-id="bd803-108">Описание</span><span class="sxs-lookup"><span data-stu-id="bd803-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bd803-109">нодеид</span><span class="sxs-lookup"><span data-stu-id="bd803-109">nodeID</span></span></p></td>
<td><p><span data-ttu-id="bd803-110">int, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="bd803-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="bd803-111">Идентификатор узла (уникальный номер).</span><span class="sxs-lookup"><span data-stu-id="bd803-111">Node ID (unique number).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bd803-112">нодегуид</span><span class="sxs-lookup"><span data-stu-id="bd803-112">nodeGuid</span></span></p></td>
<td><p><span data-ttu-id="bd803-113">GUID, а не NULL</span><span class="sxs-lookup"><span data-stu-id="bd803-113">GUID, not null</span></span></p></td>
<td><p><span data-ttu-id="bd803-114">GUID узла.</span><span class="sxs-lookup"><span data-stu-id="bd803-114">Node GUID.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bd803-115">parentID</span><span class="sxs-lookup"><span data-stu-id="bd803-115">parentID</span></span></p></td>
<td><p><span data-ttu-id="bd803-116">целое</span><span class="sxs-lookup"><span data-stu-id="bd803-116">int</span></span></p></td>
<td><p><span data-ttu-id="bd803-117">Идентификатор узла родителя.</span><span class="sxs-lookup"><span data-stu-id="bd803-117">Node ID of parent.</span></span> <span data-ttu-id="bd803-118">Корневой узел (с ИДЕНТИФИКАТОРом 1) также включает себя как родительский.</span><span class="sxs-lookup"><span data-stu-id="bd803-118">The root node (with ID 1) includes itself as parent as well.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bd803-119">Узла</span><span class="sxs-lookup"><span data-stu-id="bd803-119">nodeType</span></span></p></td>
<td><p><span data-ttu-id="bd803-120">bit, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="bd803-120">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="bd803-121">Значение true, если узел является категорией.</span><span class="sxs-lookup"><span data-stu-id="bd803-121">True if the node is a category.</span></span></p>
<p><span data-ttu-id="bd803-122">Значение false, если узел является комнатой чата.</span><span class="sxs-lookup"><span data-stu-id="bd803-122">False if the node is a chat room.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bd803-123">nodeName</span><span class="sxs-lookup"><span data-stu-id="bd803-123">nodeName</span></span></p></td>
<td><p><span data-ttu-id="bd803-124">nvarchar (256), NOT NULL</span><span class="sxs-lookup"><span data-stu-id="bd803-124">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="bd803-125">Имя узла.</span><span class="sxs-lookup"><span data-stu-id="bd803-125">Node name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bd803-126">нодедеск</span><span class="sxs-lookup"><span data-stu-id="bd803-126">nodeDesc</span></span></p></td>
<td><p><span data-ttu-id="bd803-127">nvarchar (256), NOT NULL</span><span class="sxs-lookup"><span data-stu-id="bd803-127">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="bd803-128">Описание узла.</span><span class="sxs-lookup"><span data-stu-id="bd803-128">Node description.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bd803-129">сообщение</span><span class="sxs-lookup"><span data-stu-id="bd803-129">invite</span></span></p></td>
<td><p><span data-ttu-id="bd803-130">бит</span><span class="sxs-lookup"><span data-stu-id="bd803-130">bit</span></span></p></td>
<td><p><span data-ttu-id="bd803-131">Для категорий:</span><span class="sxs-lookup"><span data-stu-id="bd803-131">For categories:</span></span></p>
<ul>
<li><p><span data-ttu-id="bd803-132">Значение true, если приглашения включены.</span><span class="sxs-lookup"><span data-stu-id="bd803-132">True if invites are on.</span></span></p></li>
<li><p><span data-ttu-id="bd803-133">Значение false, если приглашения отключены.</span><span class="sxs-lookup"><span data-stu-id="bd803-133">False if invites are off.</span></span></p></li>
</ul>
<p><span data-ttu-id="bd803-134">Для комнат:</span><span class="sxs-lookup"><span data-stu-id="bd803-134">For rooms:</span></span></p>
<ul>
<li><p><span data-ttu-id="bd803-135">Значение false, если приглашения отключены (переопределяет родительскую категорию).</span><span class="sxs-lookup"><span data-stu-id="bd803-135">False if invites are off (overrides the parent category).</span></span></p></li>
<li><p><span data-ttu-id="bd803-136">Значение null, если параметр приглашения наследуется от родительской категории.</span><span class="sxs-lookup"><span data-stu-id="bd803-136">Null if the invites setting is inherited from the parent category.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bd803-137">войдет</span><span class="sxs-lookup"><span data-stu-id="bd803-137">logged</span></span></p></td>
<td><p><span data-ttu-id="bd803-138">бит</span><span class="sxs-lookup"><span data-stu-id="bd803-138">bit</span></span></p></td>
<td><p><span data-ttu-id="bd803-139">Для категорий:</span><span class="sxs-lookup"><span data-stu-id="bd803-139">For categories:</span></span></p>
<ul>
<li><p><span data-ttu-id="bd803-140">Значение true, если история чата включена.</span><span class="sxs-lookup"><span data-stu-id="bd803-140">True if chat history is on.</span></span></p></li>
<li><p><span data-ttu-id="bd803-141">Значение false, если ведение журнала чата отключено.</span><span class="sxs-lookup"><span data-stu-id="bd803-141">False if chat history is off.</span></span></p></li>
</ul>
<p><span data-ttu-id="bd803-142">Для комнат:</span><span class="sxs-lookup"><span data-stu-id="bd803-142">For rooms:</span></span></p>
<ul>
<li><p><span data-ttu-id="bd803-143">Значения.</span><span class="sxs-lookup"><span data-stu-id="bd803-143">Null.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bd803-144">филепост</span><span class="sxs-lookup"><span data-stu-id="bd803-144">filePost</span></span></p></td>
<td><p><span data-ttu-id="bd803-145">бит</span><span class="sxs-lookup"><span data-stu-id="bd803-145">bit</span></span></p></td>
<td><p><span data-ttu-id="bd803-146">Для категорий:</span><span class="sxs-lookup"><span data-stu-id="bd803-146">For categories:</span></span></p>
<ul>
<li><p><span data-ttu-id="bd803-147">Значение true, если отправка файлов разрешена.</span><span class="sxs-lookup"><span data-stu-id="bd803-147">True if file uploads are allowed.</span></span></p></li>
<li><p><span data-ttu-id="bd803-148">Значение false, если отправка файлов запрещена.</span><span class="sxs-lookup"><span data-stu-id="bd803-148">False if file uploads are disallowed.</span></span></p></li>
</ul>
<p><span data-ttu-id="bd803-149">Для комнат:</span><span class="sxs-lookup"><span data-stu-id="bd803-149">For rooms:</span></span></p>
<ul>
<li><p><span data-ttu-id="bd803-150">Значения.</span><span class="sxs-lookup"><span data-stu-id="bd803-150">Null.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bd803-151">отключает</span><span class="sxs-lookup"><span data-stu-id="bd803-151">disabled</span></span></p></td>
<td><p><span data-ttu-id="bd803-152">bit, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="bd803-152">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="bd803-153">Значение true, если комната чата отключена.</span><span class="sxs-lookup"><span data-stu-id="bd803-153">True if the chat room is disabled.</span></span> <span data-ttu-id="bd803-154">Применимо только к комнатам чата.</span><span class="sxs-lookup"><span data-stu-id="bd803-154">Applies only to chat rooms.</span></span> <span data-ttu-id="bd803-155">(Ложь для категорий.)</span><span class="sxs-lookup"><span data-stu-id="bd803-155">(False for categories.)</span></span></p></td>
</tr>
<tr class="odd">
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bd803-156">расширения</span><span class="sxs-lookup"><span data-stu-id="bd803-156">behavior</span></span></p></td>
<td><p><span data-ttu-id="bd803-157">smallint, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="bd803-157">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="bd803-158">Поведение (Поиск в таблице Енумвалуе):</span><span class="sxs-lookup"><span data-stu-id="bd803-158">Behavior (looked up in EnumValue table):</span></span></p>
<ul>
<li><p><span data-ttu-id="bd803-159">4: обычный (обычные комнаты чата).</span><span class="sxs-lookup"><span data-stu-id="bd803-159">4: Normal (normal chat rooms).</span></span></p></li>
<li><p><span data-ttu-id="bd803-160">5: Аудиториум (Аудиториум) — комнаты чата только выступающие могут участвовать в программе.</span><span class="sxs-lookup"><span data-stu-id="bd803-160">5: Auditorium (auditorium chat rooms, only presenters can contribute).</span></span></p></li>
</ul>
<p><span data-ttu-id="bd803-161">Применимо только к комнатам чата.</span><span class="sxs-lookup"><span data-stu-id="bd803-161">Applies only to chat rooms.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bd803-162">Отображение</span><span class="sxs-lookup"><span data-stu-id="bd803-162">visibility</span></span></p></td>
<td><p><span data-ttu-id="bd803-163">smallint, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="bd803-163">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="bd803-164">Visibility (Поиск в таблице Енумвалуе):</span><span class="sxs-lookup"><span data-stu-id="bd803-164">Visibility (looked up on EnumValue table):</span></span></p>
<ul>
<li><p><span data-ttu-id="bd803-165">2: частный</span><span class="sxs-lookup"><span data-stu-id="bd803-165">2: Private</span></span></p></li>
<li><p><span data-ttu-id="bd803-166">3: область охвата</span><span class="sxs-lookup"><span data-stu-id="bd803-166">3: Scoped</span></span></p></li>
<li><p><span data-ttu-id="bd803-167">6: открыть</span><span class="sxs-lookup"><span data-stu-id="bd803-167">6: Open</span></span></p></li>
</ul>
<p><span data-ttu-id="bd803-168">Применимо только к комнатам чата.</span><span class="sxs-lookup"><span data-stu-id="bd803-168">Applies only to chat rooms.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bd803-169">сиопид</span><span class="sxs-lookup"><span data-stu-id="bd803-169">siopID</span></span></p></td>
<td><p><span data-ttu-id="bd803-170">Глобальный уникальный идентификатор (GUID)</span><span class="sxs-lookup"><span data-stu-id="bd803-170">GUID</span></span></p></td>
<td><p><span data-ttu-id="bd803-171">GUID надстройки, если надстройка связана с этой комнатой чата.</span><span class="sxs-lookup"><span data-stu-id="bd803-171">Add-In GUID if an add-in is associated with this chat room.</span></span> <span data-ttu-id="bd803-172">(В категориях нет надстроек.)</span><span class="sxs-lookup"><span data-stu-id="bd803-172">(Categories do not have add-ins.)</span></span></p>
<p><span data-ttu-id="bd803-173">Сведения о надстройке ищутся в таблице Сиопвхителист.</span><span class="sxs-lookup"><span data-stu-id="bd803-173">The add-in information is looked up in SiopWhiteList table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bd803-174">нодеаддедби</span><span class="sxs-lookup"><span data-stu-id="bd803-174">nodeAddedBy</span></span></p></td>
<td><p><span data-ttu-id="bd803-175">int, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="bd803-175">int, not null</span></span></p></td>
<td><p><span data-ttu-id="bd803-176">Идентификатор участника, который создал этот узел.</span><span class="sxs-lookup"><span data-stu-id="bd803-176">ID of the principal that created this node.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bd803-177">нодеаддедон</span><span class="sxs-lookup"><span data-stu-id="bd803-177">nodeAddedOn</span></span></p></td>
<td><p><span data-ttu-id="bd803-178">bigint, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="bd803-178">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="bd803-179">Метка времени создания узла.</span><span class="sxs-lookup"><span data-stu-id="bd803-179">Time stamp of the node creation.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bd803-180">нодеупдатедби</span><span class="sxs-lookup"><span data-stu-id="bd803-180">nodeUpdatedBy</span></span></p></td>
<td><p><span data-ttu-id="bd803-181">int, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="bd803-181">int, not null</span></span></p></td>
<td><p><span data-ttu-id="bd803-182">Идентификатор участника, который последним обновил этот узел.</span><span class="sxs-lookup"><span data-stu-id="bd803-182">ID of the principal that did the latest update of this node.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bd803-183">нодеупдатедон</span><span class="sxs-lookup"><span data-stu-id="bd803-183">nodeUpdatedOn</span></span></p></td>
<td><p><span data-ttu-id="bd803-184">bigint, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="bd803-184">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="bd803-185">Метка времени последнего обновления этого узла.</span><span class="sxs-lookup"><span data-stu-id="bd803-185">Time stamp of the latest update of this node.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bd803-186">пуржедон</span><span class="sxs-lookup"><span data-stu-id="bd803-186">purgedOn</span></span></p></td>
<td><p><span data-ttu-id="bd803-187">datetime</span><span class="sxs-lookup"><span data-stu-id="bd803-187">datetime</span></span></p></td>
<td><p><span data-ttu-id="bd803-188">Время последней операции очистки (удаления областей из таблицы ТблскопедпринЦипал и ролей из ТблпринЦипалроле таблицы), которые затронули этот узел.</span><span class="sxs-lookup"><span data-stu-id="bd803-188">Time of the latest purge operation (removal of scopes from tblScopedPrincipal table and roles from tblPrincipalRole table) that affected this node.</span></span> <span data-ttu-id="bd803-189">Это используется механизмом обновления внутреннего кэша в службе чата.</span><span class="sxs-lookup"><span data-stu-id="bd803-189">This is used by the Chat service’s internal cache update mechanism.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="bd803-190">Параметры</span><span class="sxs-lookup"><span data-stu-id="bd803-190">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bd803-191">Столбец</span><span class="sxs-lookup"><span data-stu-id="bd803-191">Column</span></span></th>
<th><span data-ttu-id="bd803-192">Описание</span><span class="sxs-lookup"><span data-stu-id="bd803-192">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bd803-193">нодеид</span><span class="sxs-lookup"><span data-stu-id="bd803-193">nodeID</span></span></p></td>
<td><p><span data-ttu-id="bd803-194">Первичный ключ.</span><span class="sxs-lookup"><span data-stu-id="bd803-194">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bd803-195">расширения</span><span class="sxs-lookup"><span data-stu-id="bd803-195">behavior</span></span></p></td>
<td><p><span data-ttu-id="bd803-196">Внешний ключ с подстановкой в таблице Тбленумвалуе. Валуеид.</span><span class="sxs-lookup"><span data-stu-id="bd803-196">Foreign key with lookup in tblEnumValue.valueID table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bd803-197">Отображение</span><span class="sxs-lookup"><span data-stu-id="bd803-197">visibility</span></span></p></td>
<td><p><span data-ttu-id="bd803-198">Внешний ключ с подстановкой в таблице Тбленумвалуе. Валуеид.</span><span class="sxs-lookup"><span data-stu-id="bd803-198">Foreign key with lookup in tblEnumValue.valueID table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bd803-199">parentID</span><span class="sxs-lookup"><span data-stu-id="bd803-199">parentID</span></span></p></td>
<td><p><span data-ttu-id="bd803-200">Внешний ключ с подстановкой в таблице Тблноде. Нодеид.</span><span class="sxs-lookup"><span data-stu-id="bd803-200">Foreign key with lookup in tblNode.nodeID table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bd803-201">сиопид</span><span class="sxs-lookup"><span data-stu-id="bd803-201">siopID</span></span></p></td>
<td><p><span data-ttu-id="bd803-202">Внешний ключ с подстановкой в таблице Тблсиопвхителист. Сиопид.</span><span class="sxs-lookup"><span data-stu-id="bd803-202">Foreign key with lookup in tblSiopWhiteList.siopId table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

