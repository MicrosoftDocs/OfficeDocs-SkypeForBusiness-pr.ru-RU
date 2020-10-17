---
title: 'Lync Server 2013: tblComplianceData'
description: 'Lync Server 2013: tblComplianceData.'
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
ms.openlocfilehash: 3c597d67054303de2753182b37419f68051d3af8
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48568105"
---
# <a name="tblcompliancedata-in-lync-server-2013"></a><span data-ttu-id="b4c31-103">tblComplianceData в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b4c31-103">tblComplianceData in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b4c31-104">_**Последнее изменение темы:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="b4c31-104">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="b4c31-105">tblComplianceData содержит события соответствия нормативным требованиям, которые еще не были обработаны адаптером соответствия.</span><span class="sxs-lookup"><span data-stu-id="b4c31-105">tblComplianceData contains the compliance events that have not been processed by the compliance adapter yet.</span></span>

### <a name="columns"></a><span data-ttu-id="b4c31-106">Столбцы</span><span class="sxs-lookup"><span data-stu-id="b4c31-106">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b4c31-107">Столбец</span><span class="sxs-lookup"><span data-stu-id="b4c31-107">Column</span></span></th>
<th><span data-ttu-id="b4c31-108">Тип</span><span class="sxs-lookup"><span data-stu-id="b4c31-108">Type</span></span></th>
<th><span data-ttu-id="b4c31-109">Описание</span><span class="sxs-lookup"><span data-stu-id="b4c31-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b4c31-110">кмплевентид</span><span class="sxs-lookup"><span data-stu-id="b4c31-110">cmplEventID</span></span></p></td>
<td><p><span data-ttu-id="b4c31-111">bigint, не NULL</span><span class="sxs-lookup"><span data-stu-id="b4c31-111">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="b4c31-112">Идентификатор события.</span><span class="sxs-lookup"><span data-stu-id="b4c31-112">Event ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b4c31-113">ентридате</span><span class="sxs-lookup"><span data-stu-id="b4c31-113">entryDate</span></span></p></td>
<td><p><span data-ttu-id="b4c31-114">smalldatetime, не NULL</span><span class="sxs-lookup"><span data-stu-id="b4c31-114">smalldatetime, not null</span></span></p></td>
<td><p><span data-ttu-id="b4c31-115">Время вставки (может относиться к далекому будущему для  cmplType=9, так как в этом случае запись является всего лишь заполнителем).</span><span class="sxs-lookup"><span data-stu-id="b4c31-115">Time of insertion (may be far in the future for cmplType=9 because the entry is just a placeholder in that case).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b4c31-116">cmplType</span><span class="sxs-lookup"><span data-stu-id="b4c31-116">cmplType</span></span></p></td>
<td><p><span data-ttu-id="b4c31-117">int, не NULL</span><span class="sxs-lookup"><span data-stu-id="b4c31-117">int, not null</span></span></p></td>
<td><p><span data-ttu-id="b4c31-118">Типа события соответствия нормативным требованиям:</span><span class="sxs-lookup"><span data-stu-id="b4c31-118">Type of compliance event:</span></span></p>
<ul>
<li><p><span data-ttu-id="b4c31-119">1: Чат</span><span class="sxs-lookup"><span data-stu-id="b4c31-119">1: Chat</span></span></p></li>
<li><p><span data-ttu-id="b4c31-120">2: Ответ на чат</span><span class="sxs-lookup"><span data-stu-id="b4c31-120">2: Backchat</span></span></p></li>
<li><p><span data-ttu-id="b4c31-121">3: Загрузка файла</span><span class="sxs-lookup"><span data-stu-id="b4c31-121">3: File download</span></span></p></li>
<li><p><span data-ttu-id="b4c31-122">4: Отправка файла</span><span class="sxs-lookup"><span data-stu-id="b4c31-122">4: File upload</span></span></p></li>
<li><p><span data-ttu-id="b4c31-123">9: Промежуточная передача файла</span><span class="sxs-lookup"><span data-stu-id="b4c31-123">9: Provisional file transfer</span></span></p></li>
<li><p><span data-ttu-id="b4c31-124">10: Удаление чата (с заменой)</span><span class="sxs-lookup"><span data-stu-id="b4c31-124">10: Chat deletion (with replace)</span></span></p></li>
<li><p><span data-ttu-id="b4c31-125">11: Очистка чата</span><span class="sxs-lookup"><span data-stu-id="b4c31-125">11: Chat purging</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b4c31-126">кмплтиме</span><span class="sxs-lookup"><span data-stu-id="b4c31-126">cmplTime</span></span></p></td>
<td><p><span data-ttu-id="b4c31-127">bigint, не NULL</span><span class="sxs-lookup"><span data-stu-id="b4c31-127">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="b4c31-128">Метка времени для события.</span><span class="sxs-lookup"><span data-stu-id="b4c31-128">Time stamp for the event.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b4c31-129">кмплчаннелури</span><span class="sxs-lookup"><span data-stu-id="b4c31-129">cmplChannelUri</span></span></p></td>
<td><p><span data-ttu-id="b4c31-130">nvarchar (255), не NULL</span><span class="sxs-lookup"><span data-stu-id="b4c31-130">nvarchar (255), not null</span></span></p></td>
<td><p><span data-ttu-id="b4c31-131">Универсальный код ресурса (URI) для канала.</span><span class="sxs-lookup"><span data-stu-id="b4c31-131">Channel Uniform Resource Identifier (URI).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b4c31-132">кмплчатид</span><span class="sxs-lookup"><span data-stu-id="b4c31-132">cmplChatID</span></span></p></td>
<td><p><span data-ttu-id="b4c31-133">типу</span><span class="sxs-lookup"><span data-stu-id="b4c31-133">bigint</span></span></p></td>
<td><p><span data-ttu-id="b4c31-134">Идентификатор чата (в соответствии с таблицей tblChat.chatId).</span><span class="sxs-lookup"><span data-stu-id="b4c31-134">Chat ID (corresponding to tblChat.chatId table).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b4c31-135">кмплусерид</span><span class="sxs-lookup"><span data-stu-id="b4c31-135">cmplUserID</span></span></p></td>
<td><p><span data-ttu-id="b4c31-136">int, не NULL</span><span class="sxs-lookup"><span data-stu-id="b4c31-136">int, not null</span></span></p></td>
<td><p><span data-ttu-id="b4c31-137">Идентификатор субъекта для отправителя (в соответствии с таблицей tblPrincipal.prinID).</span><span class="sxs-lookup"><span data-stu-id="b4c31-137">Principal ID of the poster (corresponding to tblPrincipal.prinID table).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b4c31-138">кмплусерури</span><span class="sxs-lookup"><span data-stu-id="b4c31-138">cmplUserUri</span></span></p></td>
<td><p><span data-ttu-id="b4c31-139">nvarchar (255), не NULL</span><span class="sxs-lookup"><span data-stu-id="b4c31-139">nvarchar (255), not null</span></span></p></td>
<td><p><span data-ttu-id="b4c31-140">Универсальный код ресурса (URI) для пользователя.</span><span class="sxs-lookup"><span data-stu-id="b4c31-140">User URI.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b4c31-141">кмплмессаже</span><span class="sxs-lookup"><span data-stu-id="b4c31-141">cmplMessage</span></span></p></td>
<td><p><span data-ttu-id="b4c31-142">nvarchar (max)</span><span class="sxs-lookup"><span data-stu-id="b4c31-142">nvarchar (max)</span></span></p></td>
<td><p><span data-ttu-id="b4c31-143">Сообщение (кодировка зависит от cmplType).</span><span class="sxs-lookup"><span data-stu-id="b4c31-143">Message (encoding depends on cmplType).</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="b4c31-144">Key</span><span class="sxs-lookup"><span data-stu-id="b4c31-144">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b4c31-145">Столбец</span><span class="sxs-lookup"><span data-stu-id="b4c31-145">Column</span></span></th>
<th><span data-ttu-id="b4c31-146">Описание</span><span class="sxs-lookup"><span data-stu-id="b4c31-146">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b4c31-147">кмплевентид</span><span class="sxs-lookup"><span data-stu-id="b4c31-147">cmplEventID</span></span></p></td>
<td><p><span data-ttu-id="b4c31-148">Первичный ключ.</span><span class="sxs-lookup"><span data-stu-id="b4c31-148">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

