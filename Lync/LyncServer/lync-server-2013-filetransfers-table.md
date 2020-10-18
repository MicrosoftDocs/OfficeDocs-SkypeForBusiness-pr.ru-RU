---
title: 'Lync Server 2013: таблица таблица filetransfers'
description: 'Lync Server 2013: таблица таблица filetransfers.'
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
ms.openlocfilehash: ccde45fa3743a809499273676d567846ef292ecc
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48573365"
---
# <a name="filetransfers-table-in-lync-server-2013"></a><span data-ttu-id="2569a-103">Таблица Таблица filetransfers в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2569a-103">FileTransfers table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2569a-104">_**Последнее изменение темы:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="2569a-104">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="2569a-105">Каждая запись представляет один сеанс передачи файлов.</span><span class="sxs-lookup"><span data-stu-id="2569a-105">Each record represents one file transfer session.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2569a-106">Столбец</span><span class="sxs-lookup"><span data-stu-id="2569a-106">Column</span></span></th>
<th><span data-ttu-id="2569a-107">Тип данных</span><span class="sxs-lookup"><span data-stu-id="2569a-107">Data Type</span></span></th>
<th><span data-ttu-id="2569a-108">Ключ или индекс</span><span class="sxs-lookup"><span data-stu-id="2569a-108">Key/Index</span></span></th>
<th><span data-ttu-id="2569a-109">Сведения</span><span class="sxs-lookup"><span data-stu-id="2569a-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2569a-110"><strong>сессионидтиме</strong></span><span class="sxs-lookup"><span data-stu-id="2569a-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="2569a-111">datetime</span><span class="sxs-lookup"><span data-stu-id="2569a-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="2569a-112">Основной, внешний</span><span class="sxs-lookup"><span data-stu-id="2569a-112">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="2569a-113">Время запроса сеанса.</span><span class="sxs-lookup"><span data-stu-id="2569a-113">Time of session request.</span></span> <span data-ttu-id="2569a-114">В сочетании с параметром <strong>SessionIdSeq</strong> определяет сеанс уникальным образом.</span><span class="sxs-lookup"><span data-stu-id="2569a-114">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="2569a-115">Дополнительные сведения см. <a href="lync-server-2013-dialogs-table.md">в таблице диалоговых окон в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="2569a-115">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2569a-116"><strong>сессионидсек</strong></span><span class="sxs-lookup"><span data-stu-id="2569a-116"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="2569a-117">int</span><span class="sxs-lookup"><span data-stu-id="2569a-117">int</span></span></p></td>
<td><p><span data-ttu-id="2569a-118">Основной, внешний</span><span class="sxs-lookup"><span data-stu-id="2569a-118">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="2569a-119">Идентификатор для идентификации сеанса.</span><span class="sxs-lookup"><span data-stu-id="2569a-119">ID number to identify the session.</span></span> <span data-ttu-id="2569a-120">В сочетании с параметром <strong>SessionIdTime</strong> определяет сеанс уникальным образом.</span><span class="sxs-lookup"><span data-stu-id="2569a-120">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="2569a-121">Дополнительные сведения см. <a href="lync-server-2013-dialogs-table.md">в таблице диалоговых окон в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="2569a-121">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2569a-122"><strong>Имя файла</strong></span><span class="sxs-lookup"><span data-stu-id="2569a-122"><strong>File Name</strong></span></span></p></td>
<td><p><span data-ttu-id="2569a-123">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="2569a-123">nvarchar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2569a-124">Имя файла.</span><span class="sxs-lookup"><span data-stu-id="2569a-124">Name of the file.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2569a-125"><strong>филеидентити</strong></span><span class="sxs-lookup"><span data-stu-id="2569a-125"><strong>FileIdentity</strong></span></span></p></td>
<td><p><span data-ttu-id="2569a-126">идентификатора</span><span class="sxs-lookup"><span data-stu-id="2569a-126">uniqueidentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2569a-127">Уникальный идентификатор, позволяющий разделять передачи файлов с одним именем.</span><span class="sxs-lookup"><span data-stu-id="2569a-127">Unique identifier to distinguish between file transfers involving the same file name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2569a-128"><strong>Cookie</strong></span><span class="sxs-lookup"><span data-stu-id="2569a-128"><strong>Cookie</strong></span></span></p></td>
<td><p><span data-ttu-id="2569a-129">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="2569a-129">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="2569a-130">Primary</span><span class="sxs-lookup"><span data-stu-id="2569a-130">Primary</span></span></p></td>
<td><p><span data-ttu-id="2569a-131">Используется для идентификации каждого последующего сообщения, как связанного с текущим.</span><span class="sxs-lookup"><span data-stu-id="2569a-131">Used to identify every follow-up message as being associated with this one.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2569a-132"><strong>Accept</strong></span><span class="sxs-lookup"><span data-stu-id="2569a-132"><strong>Accept</strong></span></span></p></td>
<td><p><span data-ttu-id="2569a-133">Битовая</span><span class="sxs-lookup"><span data-stu-id="2569a-133">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2569a-p103">Может иметь значение TRUE или NULL. Если значение равно TRUE, то значением параметров Reject и Cancel будет NULL.</span><span class="sxs-lookup"><span data-stu-id="2569a-p103">Can be TRUE or NULL. If TRUE, then Reject and Cancel will be NULL.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2569a-136"><strong>Reject</strong></span><span class="sxs-lookup"><span data-stu-id="2569a-136"><strong>Reject</strong></span></span></p></td>
<td><p><span data-ttu-id="2569a-137">Битовая</span><span class="sxs-lookup"><span data-stu-id="2569a-137">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2569a-p104">Может иметь значение TRUE или NULL. Если значение равно TRUE, то значением параметров Accept и Cancel будет NULL.</span><span class="sxs-lookup"><span data-stu-id="2569a-p104">Can be TRUE or NULL. If TRUE, then Accept and Cancel will be NULL.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2569a-140"><strong>Отмена</strong></span><span class="sxs-lookup"><span data-stu-id="2569a-140"><strong>Cancel</strong></span></span></p></td>
<td><p><span data-ttu-id="2569a-141">Битовая</span><span class="sxs-lookup"><span data-stu-id="2569a-141">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2569a-p105">Может иметь значение TRUE или NULL. Если значение равно TRUE, то значением параметров Accept и Reject будет NULL.</span><span class="sxs-lookup"><span data-stu-id="2569a-p105">Can be TRUE or NULL. If TRUE, then Accept and Reject will be NULL.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

