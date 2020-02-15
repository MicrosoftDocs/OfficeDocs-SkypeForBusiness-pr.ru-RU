---
title: 'Lync Server 2013: таблица таблица filetransfers'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: FileTransfers table
ms:assetid: 5368e67c-d8a9-43a1-9472-a839950dedb3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398353(v=OCS.15)
ms:contentKeyID: 48184118
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9aedca2ae840947aef4ccc6ec7bff4ba825090a0
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42028490"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="filetransfers-table-in-lync-server-2013"></a><span data-ttu-id="b9924-102">Таблица Таблица filetransfers в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b9924-102">FileTransfers table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b9924-103">_**Последнее изменение темы:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="b9924-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="b9924-104">Каждая запись представляет один сеанс передачи файлов.</span><span class="sxs-lookup"><span data-stu-id="b9924-104">Each record represents one file transfer session.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b9924-105">Столбец</span><span class="sxs-lookup"><span data-stu-id="b9924-105">Column</span></span></th>
<th><span data-ttu-id="b9924-106">Тип данных</span><span class="sxs-lookup"><span data-stu-id="b9924-106">Data Type</span></span></th>
<th><span data-ttu-id="b9924-107">Ключ или индекс</span><span class="sxs-lookup"><span data-stu-id="b9924-107">Key/Index</span></span></th>
<th><span data-ttu-id="b9924-108">Сведения</span><span class="sxs-lookup"><span data-stu-id="b9924-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b9924-109"><strong>сессионидтиме</strong></span><span class="sxs-lookup"><span data-stu-id="b9924-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="b9924-110">datetime</span><span class="sxs-lookup"><span data-stu-id="b9924-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="b9924-111">Основной, внешний</span><span class="sxs-lookup"><span data-stu-id="b9924-111">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="b9924-112">Время запроса сеанса.</span><span class="sxs-lookup"><span data-stu-id="b9924-112">Time of session request.</span></span> <span data-ttu-id="b9924-113">В сочетании с параметром <strong>SessionIdSeq</strong> определяет сеанс уникальным образом.</span><span class="sxs-lookup"><span data-stu-id="b9924-113">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="b9924-114">Дополнительные сведения см. <a href="lync-server-2013-dialogs-table.md">в таблице диалоговых окон в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="b9924-114">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b9924-115"><strong>сессионидсек</strong></span><span class="sxs-lookup"><span data-stu-id="b9924-115"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="b9924-116">int</span><span class="sxs-lookup"><span data-stu-id="b9924-116">int</span></span></p></td>
<td><p><span data-ttu-id="b9924-117">Первичный, внешний</span><span class="sxs-lookup"><span data-stu-id="b9924-117">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="b9924-118">Идентификатор для идентификации сеанса.</span><span class="sxs-lookup"><span data-stu-id="b9924-118">ID number to identify the session.</span></span> <span data-ttu-id="b9924-119">В сочетании с параметром <strong>SessionIdTime</strong> определяет сеанс уникальным образом.</span><span class="sxs-lookup"><span data-stu-id="b9924-119">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="b9924-120">Дополнительные сведения см. <a href="lync-server-2013-dialogs-table.md">в таблице диалоговых окон в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="b9924-120">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b9924-121"><strong>Имя файла</strong></span><span class="sxs-lookup"><span data-stu-id="b9924-121"><strong>File Name</strong></span></span></p></td>
<td><p><span data-ttu-id="b9924-122">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="b9924-122">nvarchar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b9924-123">Имя файла.</span><span class="sxs-lookup"><span data-stu-id="b9924-123">Name of the file.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b9924-124"><strong>филеидентити</strong></span><span class="sxs-lookup"><span data-stu-id="b9924-124"><strong>FileIdentity</strong></span></span></p></td>
<td><p><span data-ttu-id="b9924-125">идентификатора</span><span class="sxs-lookup"><span data-stu-id="b9924-125">uniqueidentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b9924-126">Уникальный идентификатор, позволяющий разделять передачи файлов с одним именем.</span><span class="sxs-lookup"><span data-stu-id="b9924-126">Unique identifier to distinguish between file transfers involving the same file name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b9924-127"><strong>Cookie</strong></span><span class="sxs-lookup"><span data-stu-id="b9924-127"><strong>Cookie</strong></span></span></p></td>
<td><p><span data-ttu-id="b9924-128">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="b9924-128">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="b9924-129">Primary</span><span class="sxs-lookup"><span data-stu-id="b9924-129">Primary</span></span></p></td>
<td><p><span data-ttu-id="b9924-130">Используется для идентификации каждого последующего сообщения, как связанного с текущим.</span><span class="sxs-lookup"><span data-stu-id="b9924-130">Used to identify every follow-up message as being associated with this one.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b9924-131"><strong>Accept</strong></span><span class="sxs-lookup"><span data-stu-id="b9924-131"><strong>Accept</strong></span></span></p></td>
<td><p><span data-ttu-id="b9924-132">Битовая</span><span class="sxs-lookup"><span data-stu-id="b9924-132">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b9924-p103">Может иметь значение TRUE или NULL. Если значение равно TRUE, то значением параметров Reject и Cancel будет NULL.</span><span class="sxs-lookup"><span data-stu-id="b9924-p103">Can be TRUE or NULL. If TRUE, then Reject and Cancel will be NULL.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b9924-135"><strong>Reject</strong></span><span class="sxs-lookup"><span data-stu-id="b9924-135"><strong>Reject</strong></span></span></p></td>
<td><p><span data-ttu-id="b9924-136">Битовая</span><span class="sxs-lookup"><span data-stu-id="b9924-136">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b9924-p104">Может иметь значение TRUE или NULL. Если значение равно TRUE, то значением параметров Accept и Cancel будет NULL.</span><span class="sxs-lookup"><span data-stu-id="b9924-p104">Can be TRUE or NULL. If TRUE, then Accept and Cancel will be NULL.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b9924-139"><strong>Отмена</strong></span><span class="sxs-lookup"><span data-stu-id="b9924-139"><strong>Cancel</strong></span></span></p></td>
<td><p><span data-ttu-id="b9924-140">Битовая</span><span class="sxs-lookup"><span data-stu-id="b9924-140">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b9924-p105">Может иметь значение TRUE или NULL. Если значение равно TRUE, то значением параметров Accept и Reject будет NULL.</span><span class="sxs-lookup"><span data-stu-id="b9924-p105">Can be TRUE or NULL. If TRUE, then Accept and Reject will be NULL.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

