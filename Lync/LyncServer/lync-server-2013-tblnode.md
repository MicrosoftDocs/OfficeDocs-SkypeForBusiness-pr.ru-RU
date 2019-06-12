---
title: 'Lync Server 2013: tblNode'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: tblNode
ms:assetid: a31d2961-aa83-4286-a12e-15d279c95f19
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615024(v=OCS.15)
ms:contentKeyID: 48184960
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 84bf7cf57f9890093a56deb2e0769b82e92aa0ea
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849549"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblnode-in-lync-server-2013"></a><span data-ttu-id="48ecc-102">tblNode в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="48ecc-102">tblNode in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="48ecc-103">_**Тема последнего изменения:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="48ecc-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="48ecc-104">Тблноде включает дерево объектов (с узлами "Категория" или "комната чата") как управляемое на панели управления Lync Server 2013 и административных командлетов.</span><span class="sxs-lookup"><span data-stu-id="48ecc-104">tblNode contains the object tree (with category or chat room nodes) as managed in the Lync Server 2013 Control Panel and administrative cmdlets.</span></span>

### <a name="columns"></a><span data-ttu-id="48ecc-105">Столбцов</span><span class="sxs-lookup"><span data-stu-id="48ecc-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="48ecc-106">Столбец</span><span class="sxs-lookup"><span data-stu-id="48ecc-106">Column</span></span></th>
<th><span data-ttu-id="48ecc-107">Тип</span><span class="sxs-lookup"><span data-stu-id="48ecc-107">Type</span></span></th>
<th><span data-ttu-id="48ecc-108">Описание</span><span class="sxs-lookup"><span data-stu-id="48ecc-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="48ecc-109">Нодеид</span><span class="sxs-lookup"><span data-stu-id="48ecc-109">nodeID</span></span></p></td>
<td><p><span data-ttu-id="48ecc-110">int, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="48ecc-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="48ecc-111">Идентификатор узла (уникальный номер).</span><span class="sxs-lookup"><span data-stu-id="48ecc-111">Node ID (unique number).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="48ecc-112">Нодегуид</span><span class="sxs-lookup"><span data-stu-id="48ecc-112">nodeGuid</span></span></p></td>
<td><p><span data-ttu-id="48ecc-113">GUID, а не NULL</span><span class="sxs-lookup"><span data-stu-id="48ecc-113">GUID, not null</span></span></p></td>
<td><p><span data-ttu-id="48ecc-114">GUID узла.</span><span class="sxs-lookup"><span data-stu-id="48ecc-114">Node GUID.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="48ecc-115">parentID</span><span class="sxs-lookup"><span data-stu-id="48ecc-115">parentID</span></span></p></td>
<td><p><span data-ttu-id="48ecc-116">целое</span><span class="sxs-lookup"><span data-stu-id="48ecc-116">int</span></span></p></td>
<td><p><span data-ttu-id="48ecc-117">Идентификатор узла родителя.</span><span class="sxs-lookup"><span data-stu-id="48ecc-117">Node ID of parent.</span></span> <span data-ttu-id="48ecc-118">Корневой узел (с ИДЕНТИФИКАТОРом 1) также включает себя как родительский.</span><span class="sxs-lookup"><span data-stu-id="48ecc-118">The root node (with ID 1) includes itself as parent as well.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="48ecc-119">Узла</span><span class="sxs-lookup"><span data-stu-id="48ecc-119">nodeType</span></span></p></td>
<td><p><span data-ttu-id="48ecc-120">bit, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="48ecc-120">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="48ecc-121">Значение true, если узел является категорией.</span><span class="sxs-lookup"><span data-stu-id="48ecc-121">True if the node is a category.</span></span></p>
<p><span data-ttu-id="48ecc-122">Значение false, если узел является комнатой чата.</span><span class="sxs-lookup"><span data-stu-id="48ecc-122">False if the node is a chat room.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="48ecc-123">nodeName</span><span class="sxs-lookup"><span data-stu-id="48ecc-123">nodeName</span></span></p></td>
<td><p><span data-ttu-id="48ecc-124">nvarchar (256), NOT NULL</span><span class="sxs-lookup"><span data-stu-id="48ecc-124">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="48ecc-125">Имя узла.</span><span class="sxs-lookup"><span data-stu-id="48ecc-125">Node name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="48ecc-126">Нодедеск</span><span class="sxs-lookup"><span data-stu-id="48ecc-126">nodeDesc</span></span></p></td>
<td><p><span data-ttu-id="48ecc-127">nvarchar (256), NOT NULL</span><span class="sxs-lookup"><span data-stu-id="48ecc-127">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="48ecc-128">Описание узла.</span><span class="sxs-lookup"><span data-stu-id="48ecc-128">Node description.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="48ecc-129">сообщение</span><span class="sxs-lookup"><span data-stu-id="48ecc-129">invite</span></span></p></td>
<td><p><span data-ttu-id="48ecc-130">бит</span><span class="sxs-lookup"><span data-stu-id="48ecc-130">bit</span></span></p></td>
<td><p><span data-ttu-id="48ecc-131">Для категорий:</span><span class="sxs-lookup"><span data-stu-id="48ecc-131">For categories:</span></span></p>
<ul>
<li><p><span data-ttu-id="48ecc-132">Значение true, если приглашения включены.</span><span class="sxs-lookup"><span data-stu-id="48ecc-132">True if invites are on.</span></span></p></li>
<li><p><span data-ttu-id="48ecc-133">Значение false, если приглашения отключены.</span><span class="sxs-lookup"><span data-stu-id="48ecc-133">False if invites are off.</span></span></p></li>
</ul>
<p><span data-ttu-id="48ecc-134">Для комнат:</span><span class="sxs-lookup"><span data-stu-id="48ecc-134">For rooms:</span></span></p>
<ul>
<li><p><span data-ttu-id="48ecc-135">Значение false, если приглашения отключены (переопределяет родительскую категорию).</span><span class="sxs-lookup"><span data-stu-id="48ecc-135">False if invites are off (overrides the parent category).</span></span></p></li>
<li><p><span data-ttu-id="48ecc-136">Значение null, если параметр приглашения наследуется от родительской категории.</span><span class="sxs-lookup"><span data-stu-id="48ecc-136">Null if the invites setting is inherited from the parent category.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="48ecc-137">войдет</span><span class="sxs-lookup"><span data-stu-id="48ecc-137">logged</span></span></p></td>
<td><p><span data-ttu-id="48ecc-138">бит</span><span class="sxs-lookup"><span data-stu-id="48ecc-138">bit</span></span></p></td>
<td><p><span data-ttu-id="48ecc-139">Для категорий:</span><span class="sxs-lookup"><span data-stu-id="48ecc-139">For categories:</span></span></p>
<ul>
<li><p><span data-ttu-id="48ecc-140">Значение true, если история чата включена.</span><span class="sxs-lookup"><span data-stu-id="48ecc-140">True if chat history is on.</span></span></p></li>
<li><p><span data-ttu-id="48ecc-141">Значение false, если ведение журнала чата отключено.</span><span class="sxs-lookup"><span data-stu-id="48ecc-141">False if chat history is off.</span></span></p></li>
</ul>
<p><span data-ttu-id="48ecc-142">Для комнат:</span><span class="sxs-lookup"><span data-stu-id="48ecc-142">For rooms:</span></span></p>
<ul>
<li><p><span data-ttu-id="48ecc-143">Значения.</span><span class="sxs-lookup"><span data-stu-id="48ecc-143">Null.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="48ecc-144">Филепост</span><span class="sxs-lookup"><span data-stu-id="48ecc-144">filePost</span></span></p></td>
<td><p><span data-ttu-id="48ecc-145">бит</span><span class="sxs-lookup"><span data-stu-id="48ecc-145">bit</span></span></p></td>
<td><p><span data-ttu-id="48ecc-146">Для категорий:</span><span class="sxs-lookup"><span data-stu-id="48ecc-146">For categories:</span></span></p>
<ul>
<li><p><span data-ttu-id="48ecc-147">Значение true, если отправка файлов разрешена.</span><span class="sxs-lookup"><span data-stu-id="48ecc-147">True if file uploads are allowed.</span></span></p></li>
<li><p><span data-ttu-id="48ecc-148">Значение false, если отправка файлов запрещена.</span><span class="sxs-lookup"><span data-stu-id="48ecc-148">False if file uploads are disallowed.</span></span></p></li>
</ul>
<p><span data-ttu-id="48ecc-149">Для комнат:</span><span class="sxs-lookup"><span data-stu-id="48ecc-149">For rooms:</span></span></p>
<ul>
<li><p><span data-ttu-id="48ecc-150">Значения.</span><span class="sxs-lookup"><span data-stu-id="48ecc-150">Null.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="48ecc-151">отключает</span><span class="sxs-lookup"><span data-stu-id="48ecc-151">disabled</span></span></p></td>
<td><p><span data-ttu-id="48ecc-152">bit, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="48ecc-152">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="48ecc-153">Значение true, если комната чата отключена.</span><span class="sxs-lookup"><span data-stu-id="48ecc-153">True if the chat room is disabled.</span></span> <span data-ttu-id="48ecc-154">Применимо только к комнатам чата.</span><span class="sxs-lookup"><span data-stu-id="48ecc-154">Applies only to chat rooms.</span></span> <span data-ttu-id="48ecc-155">(Ложь для категорий.)</span><span class="sxs-lookup"><span data-stu-id="48ecc-155">(False for categories.)</span></span></p></td>
</tr>
<tr class="odd">
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="48ecc-156">расширения</span><span class="sxs-lookup"><span data-stu-id="48ecc-156">behavior</span></span></p></td>
<td><p><span data-ttu-id="48ecc-157">smallint, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="48ecc-157">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="48ecc-158">Поведение (Поиск в таблице Енумвалуе):</span><span class="sxs-lookup"><span data-stu-id="48ecc-158">Behavior (looked up in EnumValue table):</span></span></p>
<ul>
<li><p><span data-ttu-id="48ecc-159">4: обычный (обычные комнаты чата).</span><span class="sxs-lookup"><span data-stu-id="48ecc-159">4: Normal (normal chat rooms).</span></span></p></li>
<li><p><span data-ttu-id="48ecc-160">5: Аудиториум (Аудиториум) — комнаты чата только выступающие могут участвовать в программе.</span><span class="sxs-lookup"><span data-stu-id="48ecc-160">5: Auditorium (auditorium chat rooms, only presenters can contribute).</span></span></p></li>
</ul>
<p><span data-ttu-id="48ecc-161">Применимо только к комнатам чата.</span><span class="sxs-lookup"><span data-stu-id="48ecc-161">Applies only to chat rooms.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="48ecc-162">Отображение</span><span class="sxs-lookup"><span data-stu-id="48ecc-162">visibility</span></span></p></td>
<td><p><span data-ttu-id="48ecc-163">smallint, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="48ecc-163">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="48ecc-164">Visibility (Поиск в таблице Енумвалуе):</span><span class="sxs-lookup"><span data-stu-id="48ecc-164">Visibility (looked up on EnumValue table):</span></span></p>
<ul>
<li><p><span data-ttu-id="48ecc-165">2: частный</span><span class="sxs-lookup"><span data-stu-id="48ecc-165">2: Private</span></span></p></li>
<li><p><span data-ttu-id="48ecc-166">3: область охвата</span><span class="sxs-lookup"><span data-stu-id="48ecc-166">3: Scoped</span></span></p></li>
<li><p><span data-ttu-id="48ecc-167">6: открыть</span><span class="sxs-lookup"><span data-stu-id="48ecc-167">6: Open</span></span></p></li>
</ul>
<p><span data-ttu-id="48ecc-168">Применимо только к комнатам чата.</span><span class="sxs-lookup"><span data-stu-id="48ecc-168">Applies only to chat rooms.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="48ecc-169">Сиопид</span><span class="sxs-lookup"><span data-stu-id="48ecc-169">siopID</span></span></p></td>
<td><p><span data-ttu-id="48ecc-170">Глобальный уникальный идентификатор (GUID)</span><span class="sxs-lookup"><span data-stu-id="48ecc-170">GUID</span></span></p></td>
<td><p><span data-ttu-id="48ecc-171">GUID надстройки, если надстройка связана с этой комнатой чата.</span><span class="sxs-lookup"><span data-stu-id="48ecc-171">Add-In GUID if an add-in is associated with this chat room.</span></span> <span data-ttu-id="48ecc-172">(В категориях нет надстроек.)</span><span class="sxs-lookup"><span data-stu-id="48ecc-172">(Categories do not have add-ins.)</span></span></p>
<p><span data-ttu-id="48ecc-173">Сведения о надстройке ищутся в таблице Сиопвхителист.</span><span class="sxs-lookup"><span data-stu-id="48ecc-173">The add-in information is looked up in SiopWhiteList table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="48ecc-174">Нодеаддедби</span><span class="sxs-lookup"><span data-stu-id="48ecc-174">nodeAddedBy</span></span></p></td>
<td><p><span data-ttu-id="48ecc-175">int, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="48ecc-175">int, not null</span></span></p></td>
<td><p><span data-ttu-id="48ecc-176">Идентификатор участника, который создал этот узел.</span><span class="sxs-lookup"><span data-stu-id="48ecc-176">ID of the principal that created this node.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="48ecc-177">Нодеаддедон</span><span class="sxs-lookup"><span data-stu-id="48ecc-177">nodeAddedOn</span></span></p></td>
<td><p><span data-ttu-id="48ecc-178">bigint, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="48ecc-178">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="48ecc-179">Метка времени создания узла.</span><span class="sxs-lookup"><span data-stu-id="48ecc-179">Time stamp of the node creation.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="48ecc-180">Нодеупдатедби</span><span class="sxs-lookup"><span data-stu-id="48ecc-180">nodeUpdatedBy</span></span></p></td>
<td><p><span data-ttu-id="48ecc-181">int, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="48ecc-181">int, not null</span></span></p></td>
<td><p><span data-ttu-id="48ecc-182">Идентификатор участника, который последним обновил этот узел.</span><span class="sxs-lookup"><span data-stu-id="48ecc-182">ID of the principal that did the latest update of this node.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="48ecc-183">Нодеупдатедон</span><span class="sxs-lookup"><span data-stu-id="48ecc-183">nodeUpdatedOn</span></span></p></td>
<td><p><span data-ttu-id="48ecc-184">bigint, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="48ecc-184">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="48ecc-185">Метка времени последнего обновления этого узла.</span><span class="sxs-lookup"><span data-stu-id="48ecc-185">Time stamp of the latest update of this node.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="48ecc-186">Пуржедон</span><span class="sxs-lookup"><span data-stu-id="48ecc-186">purgedOn</span></span></p></td>
<td><p><span data-ttu-id="48ecc-187">datetime</span><span class="sxs-lookup"><span data-stu-id="48ecc-187">datetime</span></span></p></td>
<td><p><span data-ttu-id="48ecc-188">Время последней операции очистки (удаления областей из таблицы ТблскопедпринЦипал и ролей из ТблпринЦипалроле таблицы), которые затронули этот узел.</span><span class="sxs-lookup"><span data-stu-id="48ecc-188">Time of the latest purge operation (removal of scopes from tblScopedPrincipal table and roles from tblPrincipalRole table) that affected this node.</span></span> <span data-ttu-id="48ecc-189">Это используется механизмом обновления внутреннего кэша в службе чата.</span><span class="sxs-lookup"><span data-stu-id="48ecc-189">This is used by the Chat service’s internal cache update mechanism.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="48ecc-190">Параметры</span><span class="sxs-lookup"><span data-stu-id="48ecc-190">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="48ecc-191">Столбец</span><span class="sxs-lookup"><span data-stu-id="48ecc-191">Column</span></span></th>
<th><span data-ttu-id="48ecc-192">Описание</span><span class="sxs-lookup"><span data-stu-id="48ecc-192">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="48ecc-193">Нодеид</span><span class="sxs-lookup"><span data-stu-id="48ecc-193">nodeID</span></span></p></td>
<td><p><span data-ttu-id="48ecc-194">Первичный ключ.</span><span class="sxs-lookup"><span data-stu-id="48ecc-194">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="48ecc-195">расширения</span><span class="sxs-lookup"><span data-stu-id="48ecc-195">behavior</span></span></p></td>
<td><p><span data-ttu-id="48ecc-196">Внешний ключ с подстановкой в таблице Тбленумвалуе. Валуеид.</span><span class="sxs-lookup"><span data-stu-id="48ecc-196">Foreign key with lookup in tblEnumValue.valueID table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="48ecc-197">Отображение</span><span class="sxs-lookup"><span data-stu-id="48ecc-197">visibility</span></span></p></td>
<td><p><span data-ttu-id="48ecc-198">Внешний ключ с подстановкой в таблице Тбленумвалуе. Валуеид.</span><span class="sxs-lookup"><span data-stu-id="48ecc-198">Foreign key with lookup in tblEnumValue.valueID table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="48ecc-199">parentID</span><span class="sxs-lookup"><span data-stu-id="48ecc-199">parentID</span></span></p></td>
<td><p><span data-ttu-id="48ecc-200">Внешний ключ с подстановкой в таблице Тблноде. Нодеид.</span><span class="sxs-lookup"><span data-stu-id="48ecc-200">Foreign key with lookup in tblNode.nodeID table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="48ecc-201">Сиопид</span><span class="sxs-lookup"><span data-stu-id="48ecc-201">siopID</span></span></p></td>
<td><p><span data-ttu-id="48ecc-202">Внешний ключ с подстановкой в таблице Тблсиопвхителист. Сиопид.</span><span class="sxs-lookup"><span data-stu-id="48ecc-202">Foreign key with lookup in tblSiopWhiteList.siopId table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

