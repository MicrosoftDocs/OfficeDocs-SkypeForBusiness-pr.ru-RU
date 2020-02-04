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
ms.openlocfilehash: 48516f307a084d30fde06a03548119e0ada34d6a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41731509"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblcompliancedata-in-lync-server-2013"></a><span data-ttu-id="a7081-102">tblComplianceData в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a7081-102">tblComplianceData in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a7081-103">_**Тема последнего изменения:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="a7081-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="a7081-104">Тблкомплианцедата содержит события соответствия требованиям, которые пока не обрабатывались адаптером соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="a7081-104">tblComplianceData contains the compliance events that have not been processed by the compliance adapter yet.</span></span>

### <a name="columns"></a><span data-ttu-id="a7081-105">Столбцов</span><span class="sxs-lookup"><span data-stu-id="a7081-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a7081-106">Столбец</span><span class="sxs-lookup"><span data-stu-id="a7081-106">Column</span></span></th>
<th><span data-ttu-id="a7081-107">Тип</span><span class="sxs-lookup"><span data-stu-id="a7081-107">Type</span></span></th>
<th><span data-ttu-id="a7081-108">Описание</span><span class="sxs-lookup"><span data-stu-id="a7081-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a7081-109">кмплевентид</span><span class="sxs-lookup"><span data-stu-id="a7081-109">cmplEventID</span></span></p></td>
<td><p><span data-ttu-id="a7081-110">bigint, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="a7081-110">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="a7081-111">Код события.</span><span class="sxs-lookup"><span data-stu-id="a7081-111">Event ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a7081-112">ентридате</span><span class="sxs-lookup"><span data-stu-id="a7081-112">entryDate</span></span></p></td>
<td><p><span data-ttu-id="a7081-113">smalldatetime, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="a7081-113">smalldatetime, not null</span></span></p></td>
<td><p><span data-ttu-id="a7081-114">Время вставки (может быть в будущем для Кмплтипе = 9, так как в этом случае запись является заполнителем в этом случае).</span><span class="sxs-lookup"><span data-stu-id="a7081-114">Time of insertion (may be far in the future for cmplType=9 because the entry is just a placeholder in that case).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a7081-115">кмплтипе</span><span class="sxs-lookup"><span data-stu-id="a7081-115">cmplType</span></span></p></td>
<td><p><span data-ttu-id="a7081-116">int, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="a7081-116">int, not null</span></span></p></td>
<td><p><span data-ttu-id="a7081-117">Тип события соответствия:</span><span class="sxs-lookup"><span data-stu-id="a7081-117">Type of compliance event:</span></span></p>
<ul>
<li><p><span data-ttu-id="a7081-118">1: чат</span><span class="sxs-lookup"><span data-stu-id="a7081-118">1: Chat</span></span></p></li>
<li><p><span data-ttu-id="a7081-119">2: чат</span><span class="sxs-lookup"><span data-stu-id="a7081-119">2: Backchat</span></span></p></li>
<li><p><span data-ttu-id="a7081-120">3: Загрузка файла</span><span class="sxs-lookup"><span data-stu-id="a7081-120">3: File download</span></span></p></li>
<li><p><span data-ttu-id="a7081-121">4: Отправка файлов</span><span class="sxs-lookup"><span data-stu-id="a7081-121">4: File upload</span></span></p></li>
<li><p><span data-ttu-id="a7081-122">9: подготовка к передаче файлов</span><span class="sxs-lookup"><span data-stu-id="a7081-122">9: Provisional file transfer</span></span></p></li>
<li><p><span data-ttu-id="a7081-123">10: удаление чата (с заменой)</span><span class="sxs-lookup"><span data-stu-id="a7081-123">10: Chat deletion (with replace)</span></span></p></li>
<li><p><span data-ttu-id="a7081-124">11: Очистка чата</span><span class="sxs-lookup"><span data-stu-id="a7081-124">11: Chat purging</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a7081-125">кмплтиме</span><span class="sxs-lookup"><span data-stu-id="a7081-125">cmplTime</span></span></p></td>
<td><p><span data-ttu-id="a7081-126">bigint, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="a7081-126">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="a7081-127">Метка времени для события.</span><span class="sxs-lookup"><span data-stu-id="a7081-127">Time stamp for the event.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a7081-128">кмплчаннелури</span><span class="sxs-lookup"><span data-stu-id="a7081-128">cmplChannelUri</span></span></p></td>
<td><p><span data-ttu-id="a7081-129">nvarchar (255), NOT NULL</span><span class="sxs-lookup"><span data-stu-id="a7081-129">nvarchar (255), not null</span></span></p></td>
<td><p><span data-ttu-id="a7081-130">Универсальный код ресурса (URI) канала.</span><span class="sxs-lookup"><span data-stu-id="a7081-130">Channel Uniform Resource Identifier (URI).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a7081-131">кмплчатид</span><span class="sxs-lookup"><span data-stu-id="a7081-131">cmplChatID</span></span></p></td>
<td><p><span data-ttu-id="a7081-132">bigint</span><span class="sxs-lookup"><span data-stu-id="a7081-132">bigint</span></span></p></td>
<td><p><span data-ttu-id="a7081-133">ИДЕНТИФИКАТОР чата (соответствующая таблице Тблчат. Чатид).</span><span class="sxs-lookup"><span data-stu-id="a7081-133">Chat ID (corresponding to tblChat.chatId table).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a7081-134">кмплусерид</span><span class="sxs-lookup"><span data-stu-id="a7081-134">cmplUserID</span></span></p></td>
<td><p><span data-ttu-id="a7081-135">int, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="a7081-135">int, not null</span></span></p></td>
<td><p><span data-ttu-id="a7081-136">Идентификатор участника афиши (соответствующий таблице ТблпринЦипал. Принид).</span><span class="sxs-lookup"><span data-stu-id="a7081-136">Principal ID of the poster (corresponding to tblPrincipal.prinID table).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a7081-137">кмплусерури</span><span class="sxs-lookup"><span data-stu-id="a7081-137">cmplUserUri</span></span></p></td>
<td><p><span data-ttu-id="a7081-138">nvarchar (255), NOT NULL</span><span class="sxs-lookup"><span data-stu-id="a7081-138">nvarchar (255), not null</span></span></p></td>
<td><p><span data-ttu-id="a7081-139">URI пользователя.</span><span class="sxs-lookup"><span data-stu-id="a7081-139">User URI.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a7081-140">кмплмессаже</span><span class="sxs-lookup"><span data-stu-id="a7081-140">cmplMessage</span></span></p></td>
<td><p><span data-ttu-id="a7081-141">nvarchar (max)</span><span class="sxs-lookup"><span data-stu-id="a7081-141">nvarchar (max)</span></span></p></td>
<td><p><span data-ttu-id="a7081-142">Сообщение (Кодировка зависит от Кмплтипе).</span><span class="sxs-lookup"><span data-stu-id="a7081-142">Message (encoding depends on cmplType).</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="a7081-143">Ключ</span><span class="sxs-lookup"><span data-stu-id="a7081-143">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a7081-144">Столбец</span><span class="sxs-lookup"><span data-stu-id="a7081-144">Column</span></span></th>
<th><span data-ttu-id="a7081-145">Описание</span><span class="sxs-lookup"><span data-stu-id="a7081-145">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a7081-146">кмплевентид</span><span class="sxs-lookup"><span data-stu-id="a7081-146">cmplEventID</span></span></p></td>
<td><p><span data-ttu-id="a7081-147">Первичный ключ.</span><span class="sxs-lookup"><span data-stu-id="a7081-147">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

