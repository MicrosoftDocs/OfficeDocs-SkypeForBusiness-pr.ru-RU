---
title: 'Lync Server 2013: представление Таблица conferenceuris'
description: 'Lync Server 2013: представление Таблица conferenceuris.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: ConferenceUris view
ms:assetid: 9a3cdcea-426e-4b6b-9876-ba746a8de706
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688148(v=OCS.15)
ms:contentKeyID: 49733750
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cba643a1992462d501800b4b2fc36b93a2740e72
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48561195"
---
# <a name="conferenceuris-view-in-lync-server-2013"></a><span data-ttu-id="c65b9-103">Представление Таблица conferenceuris в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c65b9-103">ConferenceUris view in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c65b9-104">_**Последнее изменение темы:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="c65b9-104">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="c65b9-105">В представлении ConfernceUris хранятся сведения об идентификаторах URI, которые участвовали в сеансах конференц-связи.</span><span class="sxs-lookup"><span data-stu-id="c65b9-105">The ConfernceUris view stores information about the URIs that have participated in conference sessions.</span></span> <span data-ttu-id="c65b9-106">Это представление было представлено в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c65b9-106">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c65b9-107">Столбец</span><span class="sxs-lookup"><span data-stu-id="c65b9-107">Column</span></span></th>
<th><span data-ttu-id="c65b9-108">Тип данных</span><span class="sxs-lookup"><span data-stu-id="c65b9-108">Data Type</span></span></th>
<th><span data-ttu-id="c65b9-109">Сведения</span><span class="sxs-lookup"><span data-stu-id="c65b9-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c65b9-110">конференцеуриид</span><span class="sxs-lookup"><span data-stu-id="c65b9-110">ConferenceUriId</span></span></p></td>
<td><p><span data-ttu-id="c65b9-111">int</span><span class="sxs-lookup"><span data-stu-id="c65b9-111">int</span></span></p></td>
<td><p><span data-ttu-id="c65b9-112">Уникальный номер, идентифицирующий URI конференции.</span><span class="sxs-lookup"><span data-stu-id="c65b9-112">Unique number identifying the conference URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c65b9-113">конференцеури</span><span class="sxs-lookup"><span data-stu-id="c65b9-113">ConferenceUri</span></span></p></td>
<td><p><span data-ttu-id="c65b9-114">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="c65b9-114">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="c65b9-115">Идентификатор URI конференции.</span><span class="sxs-lookup"><span data-stu-id="c65b9-115">URI of the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c65b9-116">конференцеуритипе</span><span class="sxs-lookup"><span data-stu-id="c65b9-116">ConferenceUriType</span></span></p></td>
<td><p><span data-ttu-id="c65b9-117">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="c65b9-117">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="c65b9-118">Тип идентификатора URI конференции.</span><span class="sxs-lookup"><span data-stu-id="c65b9-118">Type of conference URI.</span></span> <span data-ttu-id="c65b9-119">Дополнительные сведения см. <a href="lync-server-2013-uritypes-table.md">в таблице таблица uritypes в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="c65b9-119">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

