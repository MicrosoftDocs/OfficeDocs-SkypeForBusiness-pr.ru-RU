---
title: 'Lync Server 2013: представление Филетрансферс'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: FileTransfers view
ms:assetid: e52c3ad0-152e-4a18-af1c-1aff0d205151
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721914(v=OCS.15)
ms:contentKeyID: 49733848
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4228bbe42f2e7bcf88b26f9147e514f09c106ac3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834153"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="filetransfers-view-in-lync-server-2013"></a><span data-ttu-id="97596-102">Филетрансферс представления в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="97596-102">FileTransfers view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="97596-103">_**Тема последнего изменения:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="97596-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="97596-104">В представлении Филетрансфер хранятся сведения о одноранговых сеансах передачи файлов.</span><span class="sxs-lookup"><span data-stu-id="97596-104">The FileTransfer view stores information about peer-to-peer file transfer sessions.</span></span> <span data-ttu-id="97596-105">Это представление было представлено в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="97596-105">This view was introduced in Microsoft Lync Server 2013.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="97596-106">В представлении Филетрансферс содержатся все столбцы в <A href="lync-server-2013-sessiondetails-view.md">представлении сессиондетаилс в Lync Server 2013</A> в дополнение к столбцам, перечисленным ниже.</span><span class="sxs-lookup"><span data-stu-id="97596-106">The FileTransfers view contains all of the columns in the <A href="lync-server-2013-sessiondetails-view.md">SessionDetails view in Lync Server 2013</A> in addition the columns listed below.</span></span>



</div>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="97596-107">Столбец</span><span class="sxs-lookup"><span data-stu-id="97596-107">Column</span></span></th>
<th><span data-ttu-id="97596-108">Тип данных</span><span class="sxs-lookup"><span data-stu-id="97596-108">Data Type</span></span></th>
<th><span data-ttu-id="97596-109">Подробности</span><span class="sxs-lookup"><span data-stu-id="97596-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="97596-110"><strong>FileName</strong></span><span class="sxs-lookup"><span data-stu-id="97596-110"><strong>FileName</strong></span></span></p></td>
<td><p><span data-ttu-id="97596-111">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="97596-111">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="97596-112">Имя перенесенного файла.</span><span class="sxs-lookup"><span data-stu-id="97596-112">Name of the file transferred.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="97596-113"><strong>Файлах</strong></span><span class="sxs-lookup"><span data-stu-id="97596-113"><strong>Cookie</strong></span></span></p></td>
<td><p><span data-ttu-id="97596-114">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="97596-114">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="97596-115">Используется для идентификации каждого сообщения к исполнению, связанного с этим сообщением.</span><span class="sxs-lookup"><span data-stu-id="97596-115">Used to identify every follow-up message as being associated with this one.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="97596-116"><strong>Филеидентити</strong></span><span class="sxs-lookup"><span data-stu-id="97596-116"><strong>FileIdentity</strong></span></span></p></td>
<td><p><span data-ttu-id="97596-117">идентификатора</span><span class="sxs-lookup"><span data-stu-id="97596-117">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="97596-118">Уникальный идентификатор, позволяющий отличать передачу файлов с одним и тем же именем файла.</span><span class="sxs-lookup"><span data-stu-id="97596-118">Unique identifier to distinguish between file transfers involving the same file name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="97596-119"><strong>Отвечать</strong></span><span class="sxs-lookup"><span data-stu-id="97596-119"><strong>Accept</strong></span></span></p></td>
<td><p><span data-ttu-id="97596-120">бит</span><span class="sxs-lookup"><span data-stu-id="97596-120">bit</span></span></p></td>
<td><p><span data-ttu-id="97596-121">Может иметь значение истина или NULL.</span><span class="sxs-lookup"><span data-stu-id="97596-121">Can be TRUE or NULL.</span></span> <span data-ttu-id="97596-122">Если значение равно TRUE, то значение "отклонить" и "Отмена" будет равно NULL.</span><span class="sxs-lookup"><span data-stu-id="97596-122">If TRUE, then Reject and Cancel will be NULL.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="97596-123"><strong>Отклонил</strong></span><span class="sxs-lookup"><span data-stu-id="97596-123"><strong>Reject</strong></span></span></p></td>
<td><p><span data-ttu-id="97596-124">бит</span><span class="sxs-lookup"><span data-stu-id="97596-124">bit</span></span></p></td>
<td><p><span data-ttu-id="97596-125">Может иметь значение истина или NULL.</span><span class="sxs-lookup"><span data-stu-id="97596-125">Can be TRUE or NULL.</span></span> <span data-ttu-id="97596-126">Если значение равно TRUE, то "принимать" и "Отмена" будут иметь значение NULL.</span><span class="sxs-lookup"><span data-stu-id="97596-126">If TRUE, then Accept and Cancel will be NULL.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="97596-127"><strong>Отмена</strong>.</span><span class="sxs-lookup"><span data-stu-id="97596-127"><strong>Cancel</strong></span></span></p></td>
<td><p><span data-ttu-id="97596-128">бит</span><span class="sxs-lookup"><span data-stu-id="97596-128">bit</span></span></p></td>
<td><p><span data-ttu-id="97596-129">Может иметь значение истина или NULL.</span><span class="sxs-lookup"><span data-stu-id="97596-129">Can be TRUE or NULL.</span></span> <span data-ttu-id="97596-130">Если значение равно TRUE, то принять и отклонить будет значение NULL.</span><span class="sxs-lookup"><span data-stu-id="97596-130">If TRUE, then Accept and Reject will be NULL.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

