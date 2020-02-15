---
title: 'Lync Server 2013: tblComplianceData'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblComplianceData
ms:assetid: 05b28f9b-4aba-4b69-ba8d-2ceeb6cbfaac
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558606(v=OCS.15)
ms:contentKeyID: 48183308
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 03f5a65b11c610849c5b9d031f24d236dcbcf332
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42048510"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblcompliancedata-in-lync-server-2013"></a><span data-ttu-id="73caf-102">tblComplianceData в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="73caf-102">tblComplianceData in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="73caf-103">_**Последнее изменение темы:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="73caf-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="73caf-104">tblComplianceData содержит события соответствия нормативным требованиям, которые еще не были обработаны адаптером соответствия.</span><span class="sxs-lookup"><span data-stu-id="73caf-104">tblComplianceData contains the compliance events that have not been processed by the compliance adapter yet.</span></span>

### <a name="columns"></a><span data-ttu-id="73caf-105">Columns</span><span class="sxs-lookup"><span data-stu-id="73caf-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="73caf-106">Столбец</span><span class="sxs-lookup"><span data-stu-id="73caf-106">Column</span></span></th>
<th><span data-ttu-id="73caf-107">Тип</span><span class="sxs-lookup"><span data-stu-id="73caf-107">Type</span></span></th>
<th><span data-ttu-id="73caf-108">Описание</span><span class="sxs-lookup"><span data-stu-id="73caf-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="73caf-109">кмплевентид</span><span class="sxs-lookup"><span data-stu-id="73caf-109">cmplEventID</span></span></p></td>
<td><p><span data-ttu-id="73caf-110">bigint, not null</span><span class="sxs-lookup"><span data-stu-id="73caf-110">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="73caf-111">Идентификатор события.</span><span class="sxs-lookup"><span data-stu-id="73caf-111">Event ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="73caf-112">ентридате</span><span class="sxs-lookup"><span data-stu-id="73caf-112">entryDate</span></span></p></td>
<td><p><span data-ttu-id="73caf-113">smalldatetime, не NULL</span><span class="sxs-lookup"><span data-stu-id="73caf-113">smalldatetime, not null</span></span></p></td>
<td><p><span data-ttu-id="73caf-114">Время вставки (может относиться к далекому будущему для  cmplType=9, так как в этом случае запись является всего лишь заполнителем).</span><span class="sxs-lookup"><span data-stu-id="73caf-114">Time of insertion (may be far in the future for cmplType=9 because the entry is just a placeholder in that case).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="73caf-115">cmplType</span><span class="sxs-lookup"><span data-stu-id="73caf-115">cmplType</span></span></p></td>
<td><p><span data-ttu-id="73caf-116">int, not null</span><span class="sxs-lookup"><span data-stu-id="73caf-116">int, not null</span></span></p></td>
<td><p><span data-ttu-id="73caf-117">Типа события соответствия нормативным требованиям:</span><span class="sxs-lookup"><span data-stu-id="73caf-117">Type of compliance event:</span></span></p>
<ul>
<li><p><span data-ttu-id="73caf-118">1: Чат</span><span class="sxs-lookup"><span data-stu-id="73caf-118">1: Chat</span></span></p></li>
<li><p><span data-ttu-id="73caf-119">2: Ответ на чат</span><span class="sxs-lookup"><span data-stu-id="73caf-119">2: Backchat</span></span></p></li>
<li><p><span data-ttu-id="73caf-120">3: Загрузка файла</span><span class="sxs-lookup"><span data-stu-id="73caf-120">3: File download</span></span></p></li>
<li><p><span data-ttu-id="73caf-121">4: Отправка файла</span><span class="sxs-lookup"><span data-stu-id="73caf-121">4: File upload</span></span></p></li>
<li><p><span data-ttu-id="73caf-122">9: Промежуточная передача файла</span><span class="sxs-lookup"><span data-stu-id="73caf-122">9: Provisional file transfer</span></span></p></li>
<li><p><span data-ttu-id="73caf-123">10: Удаление чата (с заменой)</span><span class="sxs-lookup"><span data-stu-id="73caf-123">10: Chat deletion (with replace)</span></span></p></li>
<li><p><span data-ttu-id="73caf-124">11: Очистка чата</span><span class="sxs-lookup"><span data-stu-id="73caf-124">11: Chat purging</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="73caf-125">кмплтиме</span><span class="sxs-lookup"><span data-stu-id="73caf-125">cmplTime</span></span></p></td>
<td><p><span data-ttu-id="73caf-126">bigint, не NULL</span><span class="sxs-lookup"><span data-stu-id="73caf-126">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="73caf-127">Метка времени для события.</span><span class="sxs-lookup"><span data-stu-id="73caf-127">Time stamp for the event.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="73caf-128">кмплчаннелури</span><span class="sxs-lookup"><span data-stu-id="73caf-128">cmplChannelUri</span></span></p></td>
<td><p><span data-ttu-id="73caf-129">nvarchar (255), not null</span><span class="sxs-lookup"><span data-stu-id="73caf-129">nvarchar (255), not null</span></span></p></td>
<td><p><span data-ttu-id="73caf-130">Универсальный код ресурса (URI) для канала.</span><span class="sxs-lookup"><span data-stu-id="73caf-130">Channel Uniform Resource Identifier (URI).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="73caf-131">кмплчатид</span><span class="sxs-lookup"><span data-stu-id="73caf-131">cmplChatID</span></span></p></td>
<td><p><span data-ttu-id="73caf-132">типу</span><span class="sxs-lookup"><span data-stu-id="73caf-132">bigint</span></span></p></td>
<td><p><span data-ttu-id="73caf-133">Идентификатор чата (в соответствии с таблицей tblChat.chatId).</span><span class="sxs-lookup"><span data-stu-id="73caf-133">Chat ID (corresponding to tblChat.chatId table).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="73caf-134">кмплусерид</span><span class="sxs-lookup"><span data-stu-id="73caf-134">cmplUserID</span></span></p></td>
<td><p><span data-ttu-id="73caf-135">int, не NULL</span><span class="sxs-lookup"><span data-stu-id="73caf-135">int, not null</span></span></p></td>
<td><p><span data-ttu-id="73caf-136">Идентификатор субъекта для отправителя (в соответствии с таблицей tblPrincipal.prinID).</span><span class="sxs-lookup"><span data-stu-id="73caf-136">Principal ID of the poster (corresponding to tblPrincipal.prinID table).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="73caf-137">кмплусерури</span><span class="sxs-lookup"><span data-stu-id="73caf-137">cmplUserUri</span></span></p></td>
<td><p><span data-ttu-id="73caf-138">nvarchar (255), не NULL</span><span class="sxs-lookup"><span data-stu-id="73caf-138">nvarchar (255), not null</span></span></p></td>
<td><p><span data-ttu-id="73caf-139">Универсальный код ресурса (URI) для пользователя.</span><span class="sxs-lookup"><span data-stu-id="73caf-139">User URI.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="73caf-140">кмплмессаже</span><span class="sxs-lookup"><span data-stu-id="73caf-140">cmplMessage</span></span></p></td>
<td><p><span data-ttu-id="73caf-141">nvarchar (max)</span><span class="sxs-lookup"><span data-stu-id="73caf-141">nvarchar (max)</span></span></p></td>
<td><p><span data-ttu-id="73caf-142">Сообщение (кодировка зависит от cmplType).</span><span class="sxs-lookup"><span data-stu-id="73caf-142">Message (encoding depends on cmplType).</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="73caf-143">Key</span><span class="sxs-lookup"><span data-stu-id="73caf-143">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="73caf-144">Столбец</span><span class="sxs-lookup"><span data-stu-id="73caf-144">Column</span></span></th>
<th><span data-ttu-id="73caf-145">Описание</span><span class="sxs-lookup"><span data-stu-id="73caf-145">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="73caf-146">кмплевентид</span><span class="sxs-lookup"><span data-stu-id="73caf-146">cmplEventID</span></span></p></td>
<td><p><span data-ttu-id="73caf-147">Первичный ключ.</span><span class="sxs-lookup"><span data-stu-id="73caf-147">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

