---
title: 'Lync Server 2013: представление Таблица filetransfers'
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
ms.openlocfilehash: c2bf6f78a564ef1fd526ba8d265bedf81c845810
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42206195"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="filetransfers-view-in-lync-server-2013"></a><span data-ttu-id="dcca4-102">Представление Таблица filetransfers в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dcca4-102">FileTransfers view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dcca4-103">_**Последнее изменение темы:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="dcca4-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="dcca4-104">В представлении Филетрансфер хранятся сведения об одноранговых сеансах передачи файлов.</span><span class="sxs-lookup"><span data-stu-id="dcca4-104">The FileTransfer view stores information about peer-to-peer file transfer sessions.</span></span> <span data-ttu-id="dcca4-105">Это представление было представлено в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="dcca4-105">This view was introduced in Microsoft Lync Server 2013.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="dcca4-106">В представлении Таблица filetransfers содержатся все столбцы в <A href="lync-server-2013-sessiondetails-view.md">представлении SessionDetails в Lync Server 2013</A> , а также столбцы, перечисленные ниже.</span><span class="sxs-lookup"><span data-stu-id="dcca4-106">The FileTransfers view contains all of the columns in the <A href="lync-server-2013-sessiondetails-view.md">SessionDetails view in Lync Server 2013</A> in addition the columns listed below.</span></span>



</div>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="dcca4-107">Столбец</span><span class="sxs-lookup"><span data-stu-id="dcca4-107">Column</span></span></th>
<th><span data-ttu-id="dcca4-108">Тип данных</span><span class="sxs-lookup"><span data-stu-id="dcca4-108">Data Type</span></span></th>
<th><span data-ttu-id="dcca4-109">Сведения</span><span class="sxs-lookup"><span data-stu-id="dcca4-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="dcca4-110"><strong>FileName</strong></span><span class="sxs-lookup"><span data-stu-id="dcca4-110"><strong>FileName</strong></span></span></p></td>
<td><p><span data-ttu-id="dcca4-111">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="dcca4-111">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="dcca4-112">Имя переданного файла.</span><span class="sxs-lookup"><span data-stu-id="dcca4-112">Name of the file transferred.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dcca4-113"><strong>Cookie</strong></span><span class="sxs-lookup"><span data-stu-id="dcca4-113"><strong>Cookie</strong></span></span></p></td>
<td><p><span data-ttu-id="dcca4-114">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="dcca4-114">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="dcca4-115">Используется для идентификации каждого последующего сообщения как связанного с этим сообщением.</span><span class="sxs-lookup"><span data-stu-id="dcca4-115">Used to identify every follow-up message as being associated with this one.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dcca4-116"><strong>филеидентити</strong></span><span class="sxs-lookup"><span data-stu-id="dcca4-116"><strong>FileIdentity</strong></span></span></p></td>
<td><p><span data-ttu-id="dcca4-117">идентификатора</span><span class="sxs-lookup"><span data-stu-id="dcca4-117">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="dcca4-118">Уникальный идентификатор для различения операций передачи файлов с одинаковыми именами файлов.</span><span class="sxs-lookup"><span data-stu-id="dcca4-118">Unique identifier to distinguish between file transfers involving the same file name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dcca4-119"><strong>Accept</strong></span><span class="sxs-lookup"><span data-stu-id="dcca4-119"><strong>Accept</strong></span></span></p></td>
<td><p><span data-ttu-id="dcca4-120">Битовая</span><span class="sxs-lookup"><span data-stu-id="dcca4-120">bit</span></span></p></td>
<td><p><span data-ttu-id="dcca4-p102">Может иметь значение TRUE или NULL. Если значение равно TRUE, то значением параметров Reject и Cancel будет NULL.</span><span class="sxs-lookup"><span data-stu-id="dcca4-p102">Can be TRUE or NULL. If TRUE, then Reject and Cancel will be NULL.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dcca4-123"><strong>Reject</strong></span><span class="sxs-lookup"><span data-stu-id="dcca4-123"><strong>Reject</strong></span></span></p></td>
<td><p><span data-ttu-id="dcca4-124">Битовая</span><span class="sxs-lookup"><span data-stu-id="dcca4-124">bit</span></span></p></td>
<td><p><span data-ttu-id="dcca4-p103">Может иметь значение TRUE или NULL. Если значение равно TRUE, то значением параметров Accept и Cancel будет NULL.</span><span class="sxs-lookup"><span data-stu-id="dcca4-p103">Can be TRUE or NULL. If TRUE, then Accept and Cancel will be NULL.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dcca4-127"><strong>Отмена</strong></span><span class="sxs-lookup"><span data-stu-id="dcca4-127"><strong>Cancel</strong></span></span></p></td>
<td><p><span data-ttu-id="dcca4-128">Битовая</span><span class="sxs-lookup"><span data-stu-id="dcca4-128">bit</span></span></p></td>
<td><p><span data-ttu-id="dcca4-p104">Может иметь значение TRUE или NULL. Если значение равно TRUE, то значением параметров Accept и Reject будет NULL.</span><span class="sxs-lookup"><span data-stu-id="dcca4-p104">Can be TRUE or NULL. If TRUE, then Accept and Reject will be NULL.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

