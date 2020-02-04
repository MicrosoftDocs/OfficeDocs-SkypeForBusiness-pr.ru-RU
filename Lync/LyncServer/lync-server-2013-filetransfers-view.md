---
title: 'Lync Server 2013: представление Филетрансферс'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: FileTransfers view
ms:assetid: e52c3ad0-152e-4a18-af1c-1aff0d205151
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721914(v=OCS.15)
ms:contentKeyID: 49733848
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fc4469140f7f92c563a594c883d02f3add1e65c5
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41743379"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="filetransfers-view-in-lync-server-2013"></a><span data-ttu-id="edad5-102">Филетрансферс представления в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="edad5-102">FileTransfers view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="edad5-103">_**Тема последнего изменения:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="edad5-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="edad5-104">В представлении Филетрансфер хранятся сведения о одноранговых сеансах передачи файлов.</span><span class="sxs-lookup"><span data-stu-id="edad5-104">The FileTransfer view stores information about peer-to-peer file transfer sessions.</span></span> <span data-ttu-id="edad5-105">Это представление было представлено в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="edad5-105">This view was introduced in Microsoft Lync Server 2013.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="edad5-106">В представлении Филетрансферс содержатся все столбцы в <A href="lync-server-2013-sessiondetails-view.md">представлении сессиондетаилс в Lync Server 2013</A> в дополнение к столбцам, перечисленным ниже.</span><span class="sxs-lookup"><span data-stu-id="edad5-106">The FileTransfers view contains all of the columns in the <A href="lync-server-2013-sessiondetails-view.md">SessionDetails view in Lync Server 2013</A> in addition the columns listed below.</span></span>



</div>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="edad5-107">Столбец</span><span class="sxs-lookup"><span data-stu-id="edad5-107">Column</span></span></th>
<th><span data-ttu-id="edad5-108">Тип данных</span><span class="sxs-lookup"><span data-stu-id="edad5-108">Data Type</span></span></th>
<th><span data-ttu-id="edad5-109">Подробности</span><span class="sxs-lookup"><span data-stu-id="edad5-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="edad5-110"><strong>FileName</strong></span><span class="sxs-lookup"><span data-stu-id="edad5-110"><strong>FileName</strong></span></span></p></td>
<td><p><span data-ttu-id="edad5-111">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="edad5-111">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="edad5-112">Имя перенесенного файла.</span><span class="sxs-lookup"><span data-stu-id="edad5-112">Name of the file transferred.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="edad5-113"><strong>Файлах</strong></span><span class="sxs-lookup"><span data-stu-id="edad5-113"><strong>Cookie</strong></span></span></p></td>
<td><p><span data-ttu-id="edad5-114">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="edad5-114">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="edad5-115">Используется для идентификации каждого сообщения к исполнению, связанного с этим сообщением.</span><span class="sxs-lookup"><span data-stu-id="edad5-115">Used to identify every follow-up message as being associated with this one.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="edad5-116"><strong>филеидентити</strong></span><span class="sxs-lookup"><span data-stu-id="edad5-116"><strong>FileIdentity</strong></span></span></p></td>
<td><p><span data-ttu-id="edad5-117">идентификатора</span><span class="sxs-lookup"><span data-stu-id="edad5-117">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="edad5-118">Уникальный идентификатор, позволяющий отличать передачу файлов с одним и тем же именем файла.</span><span class="sxs-lookup"><span data-stu-id="edad5-118">Unique identifier to distinguish between file transfers involving the same file name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="edad5-119"><strong>Отвечать</strong></span><span class="sxs-lookup"><span data-stu-id="edad5-119"><strong>Accept</strong></span></span></p></td>
<td><p><span data-ttu-id="edad5-120">бит</span><span class="sxs-lookup"><span data-stu-id="edad5-120">bit</span></span></p></td>
<td><p><span data-ttu-id="edad5-121">Может иметь значение истина или NULL.</span><span class="sxs-lookup"><span data-stu-id="edad5-121">Can be TRUE or NULL.</span></span> <span data-ttu-id="edad5-122">Если значение равно TRUE, то значение "отклонить" и "Отмена" будет равно NULL.</span><span class="sxs-lookup"><span data-stu-id="edad5-122">If TRUE, then Reject and Cancel will be NULL.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="edad5-123"><strong>Отклонил</strong></span><span class="sxs-lookup"><span data-stu-id="edad5-123"><strong>Reject</strong></span></span></p></td>
<td><p><span data-ttu-id="edad5-124">бит</span><span class="sxs-lookup"><span data-stu-id="edad5-124">bit</span></span></p></td>
<td><p><span data-ttu-id="edad5-125">Может иметь значение истина или NULL.</span><span class="sxs-lookup"><span data-stu-id="edad5-125">Can be TRUE or NULL.</span></span> <span data-ttu-id="edad5-126">Если значение равно TRUE, то "принимать" и "Отмена" будут иметь значение NULL.</span><span class="sxs-lookup"><span data-stu-id="edad5-126">If TRUE, then Accept and Cancel will be NULL.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="edad5-127"><strong>Отмена</strong>.</span><span class="sxs-lookup"><span data-stu-id="edad5-127"><strong>Cancel</strong></span></span></p></td>
<td><p><span data-ttu-id="edad5-128">бит</span><span class="sxs-lookup"><span data-stu-id="edad5-128">bit</span></span></p></td>
<td><p><span data-ttu-id="edad5-129">Может иметь значение истина или NULL.</span><span class="sxs-lookup"><span data-stu-id="edad5-129">Can be TRUE or NULL.</span></span> <span data-ttu-id="edad5-130">Если значение равно TRUE, то принять и отклонить будет значение NULL.</span><span class="sxs-lookup"><span data-stu-id="edad5-130">If TRUE, then Accept and Reject will be NULL.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

