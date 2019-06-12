---
title: 'Lync Server 2013: tblComplianceData'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: tblComplianceData
ms:assetid: 05b28f9b-4aba-4b69-ba8d-2ceeb6cbfaac
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558606(v=OCS.15)
ms:contentKeyID: 48183308
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 044a57645a8c49ea74ec4e003f9e12720d0b2268
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849545"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblcompliancedata-in-lync-server-2013"></a><span data-ttu-id="18892-102">tblComplianceData в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="18892-102">tblComplianceData in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="18892-103">_**Тема последнего изменения:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="18892-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="18892-104">Тблкомплианцедата содержит события соответствия требованиям, которые пока не обрабатывались адаптером соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="18892-104">tblComplianceData contains the compliance events that have not been processed by the compliance adapter yet.</span></span>

### <a name="columns"></a><span data-ttu-id="18892-105">Столбцов</span><span class="sxs-lookup"><span data-stu-id="18892-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="18892-106">Столбец</span><span class="sxs-lookup"><span data-stu-id="18892-106">Column</span></span></th>
<th><span data-ttu-id="18892-107">Тип</span><span class="sxs-lookup"><span data-stu-id="18892-107">Type</span></span></th>
<th><span data-ttu-id="18892-108">Описание</span><span class="sxs-lookup"><span data-stu-id="18892-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="18892-109">Кмплевентид</span><span class="sxs-lookup"><span data-stu-id="18892-109">cmplEventID</span></span></p></td>
<td><p><span data-ttu-id="18892-110">bigint, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="18892-110">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="18892-111">Код события.</span><span class="sxs-lookup"><span data-stu-id="18892-111">Event ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="18892-112">Ентридате</span><span class="sxs-lookup"><span data-stu-id="18892-112">entryDate</span></span></p></td>
<td><p><span data-ttu-id="18892-113">smalldatetime, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="18892-113">smalldatetime, not null</span></span></p></td>
<td><p><span data-ttu-id="18892-114">Время вставки (может быть в будущем для Кмплтипе = 9, так как в этом случае запись является заполнителем в этом случае).</span><span class="sxs-lookup"><span data-stu-id="18892-114">Time of insertion (may be far in the future for cmplType=9 because the entry is just a placeholder in that case).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="18892-115">Кмплтипе</span><span class="sxs-lookup"><span data-stu-id="18892-115">cmplType</span></span></p></td>
<td><p><span data-ttu-id="18892-116">int, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="18892-116">int, not null</span></span></p></td>
<td><p><span data-ttu-id="18892-117">Тип события соответствия:</span><span class="sxs-lookup"><span data-stu-id="18892-117">Type of compliance event:</span></span></p>
<ul>
<li><p><span data-ttu-id="18892-118">1: чат</span><span class="sxs-lookup"><span data-stu-id="18892-118">1: Chat</span></span></p></li>
<li><p><span data-ttu-id="18892-119">2: чат</span><span class="sxs-lookup"><span data-stu-id="18892-119">2: Backchat</span></span></p></li>
<li><p><span data-ttu-id="18892-120">3: Загрузка файла</span><span class="sxs-lookup"><span data-stu-id="18892-120">3: File download</span></span></p></li>
<li><p><span data-ttu-id="18892-121">4: Отправка файлов</span><span class="sxs-lookup"><span data-stu-id="18892-121">4: File upload</span></span></p></li>
<li><p><span data-ttu-id="18892-122">9: подготовка к передаче файлов</span><span class="sxs-lookup"><span data-stu-id="18892-122">9: Provisional file transfer</span></span></p></li>
<li><p><span data-ttu-id="18892-123">10: удаление чата (с заменой)</span><span class="sxs-lookup"><span data-stu-id="18892-123">10: Chat deletion (with replace)</span></span></p></li>
<li><p><span data-ttu-id="18892-124">11: Очистка чата</span><span class="sxs-lookup"><span data-stu-id="18892-124">11: Chat purging</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="18892-125">Кмплтиме</span><span class="sxs-lookup"><span data-stu-id="18892-125">cmplTime</span></span></p></td>
<td><p><span data-ttu-id="18892-126">bigint, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="18892-126">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="18892-127">Метка времени для события.</span><span class="sxs-lookup"><span data-stu-id="18892-127">Time stamp for the event.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="18892-128">Кмплчаннелури</span><span class="sxs-lookup"><span data-stu-id="18892-128">cmplChannelUri</span></span></p></td>
<td><p><span data-ttu-id="18892-129">nvarchar (255), NOT NULL</span><span class="sxs-lookup"><span data-stu-id="18892-129">nvarchar (255), not null</span></span></p></td>
<td><p><span data-ttu-id="18892-130">Универсальный код ресурса (URI) канала.</span><span class="sxs-lookup"><span data-stu-id="18892-130">Channel Uniform Resource Identifier (URI).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="18892-131">Кмплчатид</span><span class="sxs-lookup"><span data-stu-id="18892-131">cmplChatID</span></span></p></td>
<td><p><span data-ttu-id="18892-132">bigint</span><span class="sxs-lookup"><span data-stu-id="18892-132">bigint</span></span></p></td>
<td><p><span data-ttu-id="18892-133">ИДЕНТИФИКАТОР чата (соответствующая таблице Тблчат. Чатид).</span><span class="sxs-lookup"><span data-stu-id="18892-133">Chat ID (corresponding to tblChat.chatId table).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="18892-134">Кмплусерид</span><span class="sxs-lookup"><span data-stu-id="18892-134">cmplUserID</span></span></p></td>
<td><p><span data-ttu-id="18892-135">int, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="18892-135">int, not null</span></span></p></td>
<td><p><span data-ttu-id="18892-136">Идентификатор участника афиши (соответствующий таблице ТблпринЦипал. Принид).</span><span class="sxs-lookup"><span data-stu-id="18892-136">Principal ID of the poster (corresponding to tblPrincipal.prinID table).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="18892-137">Кмплусерури</span><span class="sxs-lookup"><span data-stu-id="18892-137">cmplUserUri</span></span></p></td>
<td><p><span data-ttu-id="18892-138">nvarchar (255), NOT NULL</span><span class="sxs-lookup"><span data-stu-id="18892-138">nvarchar (255), not null</span></span></p></td>
<td><p><span data-ttu-id="18892-139">URI пользователя.</span><span class="sxs-lookup"><span data-stu-id="18892-139">User URI.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="18892-140">Кмплмессаже</span><span class="sxs-lookup"><span data-stu-id="18892-140">cmplMessage</span></span></p></td>
<td><p><span data-ttu-id="18892-141">nvarchar (max)</span><span class="sxs-lookup"><span data-stu-id="18892-141">nvarchar (max)</span></span></p></td>
<td><p><span data-ttu-id="18892-142">Сообщение (Кодировка зависит от Кмплтипе).</span><span class="sxs-lookup"><span data-stu-id="18892-142">Message (encoding depends on cmplType).</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="18892-143">Ключ</span><span class="sxs-lookup"><span data-stu-id="18892-143">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="18892-144">Столбец</span><span class="sxs-lookup"><span data-stu-id="18892-144">Column</span></span></th>
<th><span data-ttu-id="18892-145">Описание</span><span class="sxs-lookup"><span data-stu-id="18892-145">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="18892-146">Кмплевентид</span><span class="sxs-lookup"><span data-stu-id="18892-146">cmplEventID</span></span></p></td>
<td><p><span data-ttu-id="18892-147">Первичный ключ.</span><span class="sxs-lookup"><span data-stu-id="18892-147">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

