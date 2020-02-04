---
title: 'Lync Server 2013: таблица FileTransfers'
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
ms.openlocfilehash: de8a3e69c670c273bcdd91ac5895c0b1f0b15d80
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41743369"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="filetransfers-table-in-lync-server-2013"></a><span data-ttu-id="c6070-102">Таблица FileTransfers в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c6070-102">FileTransfers table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c6070-103">_**Тема последнего изменения:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="c6070-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="c6070-104">Каждая запись представляет собой один сеанс передачи файлов.</span><span class="sxs-lookup"><span data-stu-id="c6070-104">Each record represents one file transfer session.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c6070-105">Столбец</span><span class="sxs-lookup"><span data-stu-id="c6070-105">Column</span></span></th>
<th><span data-ttu-id="c6070-106">Тип данных</span><span class="sxs-lookup"><span data-stu-id="c6070-106">Data Type</span></span></th>
<th><span data-ttu-id="c6070-107">Ключ/индекс</span><span class="sxs-lookup"><span data-stu-id="c6070-107">Key/Index</span></span></th>
<th><span data-ttu-id="c6070-108">Сведения</span><span class="sxs-lookup"><span data-stu-id="c6070-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c6070-109"><strong>сессионидтиме</strong></span><span class="sxs-lookup"><span data-stu-id="c6070-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="c6070-110">datetime</span><span class="sxs-lookup"><span data-stu-id="c6070-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="c6070-111">Основной, внешний</span><span class="sxs-lookup"><span data-stu-id="c6070-111">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="c6070-112">Время запроса сеанса.</span><span class="sxs-lookup"><span data-stu-id="c6070-112">Time of session request.</span></span> <span data-ttu-id="c6070-113">Используется в сочетании с <strong>сессионидсек</strong> для уникальной идентификации сеанса.</span><span class="sxs-lookup"><span data-stu-id="c6070-113">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="c6070-114">Дополнительные сведения приведены <a href="lync-server-2013-dialogs-table.md">в таблице диалоговые окна Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="c6070-114">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6070-115"><strong>сессионидсек</strong></span><span class="sxs-lookup"><span data-stu-id="c6070-115"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="c6070-116">целое</span><span class="sxs-lookup"><span data-stu-id="c6070-116">int</span></span></p></td>
<td><p><span data-ttu-id="c6070-117">Основной, внешний</span><span class="sxs-lookup"><span data-stu-id="c6070-117">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="c6070-118">ИДЕНТИФИКАЦИОНный номер для идентификации сеанса.</span><span class="sxs-lookup"><span data-stu-id="c6070-118">ID number to identify the session.</span></span> <span data-ttu-id="c6070-119">Используется в сочетании с <strong>сессионидтиме</strong> для уникальной идентификации сеанса.</span><span class="sxs-lookup"><span data-stu-id="c6070-119">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="c6070-120">Дополнительные сведения приведены <a href="lync-server-2013-dialogs-table.md">в таблице диалоговые окна Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="c6070-120">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6070-121"><strong>Имя файла</strong></span><span class="sxs-lookup"><span data-stu-id="c6070-121"><strong>File Name</strong></span></span></p></td>
<td><p><span data-ttu-id="c6070-122">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="c6070-122">nvarchar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c6070-123">Имя файла.</span><span class="sxs-lookup"><span data-stu-id="c6070-123">Name of the file.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6070-124"><strong>филеидентити</strong></span><span class="sxs-lookup"><span data-stu-id="c6070-124"><strong>FileIdentity</strong></span></span></p></td>
<td><p><span data-ttu-id="c6070-125">идентификатора</span><span class="sxs-lookup"><span data-stu-id="c6070-125">uniqueidentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c6070-126">Уникальный идентификатор, позволяющий отличать передачу файлов с одним и тем же именем файла.</span><span class="sxs-lookup"><span data-stu-id="c6070-126">Unique identifier to distinguish between file transfers involving the same file name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6070-127"><strong>Файлах</strong></span><span class="sxs-lookup"><span data-stu-id="c6070-127"><strong>Cookie</strong></span></span></p></td>
<td><p><span data-ttu-id="c6070-128">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="c6070-128">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="c6070-129">Primary</span><span class="sxs-lookup"><span data-stu-id="c6070-129">Primary</span></span></p></td>
<td><p><span data-ttu-id="c6070-130">Используется для идентификации каждого сообщения к исполнению, связанного с этим сообщением.</span><span class="sxs-lookup"><span data-stu-id="c6070-130">Used to identify every follow-up message as being associated with this one.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6070-131"><strong>Отвечать</strong></span><span class="sxs-lookup"><span data-stu-id="c6070-131"><strong>Accept</strong></span></span></p></td>
<td><p><span data-ttu-id="c6070-132">бит</span><span class="sxs-lookup"><span data-stu-id="c6070-132">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c6070-133">Может иметь значение истина или NULL.</span><span class="sxs-lookup"><span data-stu-id="c6070-133">Can be TRUE or NULL.</span></span> <span data-ttu-id="c6070-134">Если значение равно TRUE, то значение "отклонить" и "Отмена" будет равно NULL.</span><span class="sxs-lookup"><span data-stu-id="c6070-134">If TRUE, then Reject and Cancel will be NULL.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6070-135"><strong>Отклонил</strong></span><span class="sxs-lookup"><span data-stu-id="c6070-135"><strong>Reject</strong></span></span></p></td>
<td><p><span data-ttu-id="c6070-136">бит</span><span class="sxs-lookup"><span data-stu-id="c6070-136">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c6070-137">Может иметь значение истина или NULL.</span><span class="sxs-lookup"><span data-stu-id="c6070-137">Can be TRUE or NULL.</span></span> <span data-ttu-id="c6070-138">Если значение равно TRUE, то "принимать" и "Отмена" будут иметь значение NULL.</span><span class="sxs-lookup"><span data-stu-id="c6070-138">If TRUE, then Accept and Cancel will be NULL.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6070-139"><strong>Отмена</strong>.</span><span class="sxs-lookup"><span data-stu-id="c6070-139"><strong>Cancel</strong></span></span></p></td>
<td><p><span data-ttu-id="c6070-140">бит</span><span class="sxs-lookup"><span data-stu-id="c6070-140">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c6070-141">Может иметь значение истина или NULL.</span><span class="sxs-lookup"><span data-stu-id="c6070-141">Can be TRUE or NULL.</span></span> <span data-ttu-id="c6070-142">Если значение равно TRUE, то принять и отклонить будет значение NULL.</span><span class="sxs-lookup"><span data-stu-id="c6070-142">If TRUE, then Accept and Reject will be NULL.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

