---
title: 'Lync Server 2013: tblSiopWhiteList'
description: 'Lync Server 2013: tblSiopWhiteList.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblSiopWhiteList
ms:assetid: 05fc1df4-32eb-4d46-9d1c-e0b607091142
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558607(v=OCS.15)
ms:contentKeyID: 48183310
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fbb58c0818a6f36959732f210b8eb53bbfe223d0
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48563865"
---
# <a name="tblsiopwhitelist-in-lync-server-2013"></a><span data-ttu-id="e89a9-103">tblSiopWhiteList в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e89a9-103">tblSiopWhiteList in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e89a9-104">_**Последнее изменение темы:** 2012-06-28_</span><span class="sxs-lookup"><span data-stu-id="e89a9-104">_**Topic Last Modified:** 2012-06-28_</span></span>

<span data-ttu-id="e89a9-105">tblSiopWhiteList — это список зарегистрированных надстроек, которые могут быть связаны с узлами.</span><span class="sxs-lookup"><span data-stu-id="e89a9-105">tblSiopWhiteList is the list of registered add-ins that can be associated with nodes.</span></span>

### <a name="columns"></a><span data-ttu-id="e89a9-106">Столбцы</span><span class="sxs-lookup"><span data-stu-id="e89a9-106">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e89a9-107">Столбец</span><span class="sxs-lookup"><span data-stu-id="e89a9-107">Column</span></span></th>
<th><span data-ttu-id="e89a9-108">Тип</span><span class="sxs-lookup"><span data-stu-id="e89a9-108">Type</span></span></th>
<th><span data-ttu-id="e89a9-109">Описание</span><span class="sxs-lookup"><span data-stu-id="e89a9-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e89a9-110">сиопид</span><span class="sxs-lookup"><span data-stu-id="e89a9-110">siopID</span></span></p></td>
<td><p><span data-ttu-id="e89a9-111">GUID, отлично от null</span><span class="sxs-lookup"><span data-stu-id="e89a9-111">GUID, not null</span></span></p></td>
<td><p><span data-ttu-id="e89a9-112">GUID надстройки.</span><span class="sxs-lookup"><span data-stu-id="e89a9-112">GUID of the add-in.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e89a9-113">сиопнаме</span><span class="sxs-lookup"><span data-stu-id="e89a9-113">siopName</span></span></p></td>
<td><p><span data-ttu-id="e89a9-114">nvarchar (50), отлично от null</span><span class="sxs-lookup"><span data-stu-id="e89a9-114">nvarchar (50), not null</span></span></p></td>
<td><p><span data-ttu-id="e89a9-115">Отображаемое имя надстройки.</span><span class="sxs-lookup"><span data-stu-id="e89a9-115">Display-name of the add-in.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e89a9-116">сиопурл</span><span class="sxs-lookup"><span data-stu-id="e89a9-116">siopUrl</span></span></p></td>
<td><p><span data-ttu-id="e89a9-117">nvarchar (255), отлично от null</span><span class="sxs-lookup"><span data-stu-id="e89a9-117">nvarchar (255), not null</span></span></p></td>
<td><p><span data-ttu-id="e89a9-118">URL-адрес надстройки.</span><span class="sxs-lookup"><span data-stu-id="e89a9-118">URL of the add-in.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="e89a9-119">Key</span><span class="sxs-lookup"><span data-stu-id="e89a9-119">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e89a9-120">Столбец</span><span class="sxs-lookup"><span data-stu-id="e89a9-120">Column</span></span></th>
<th><span data-ttu-id="e89a9-121">Описание</span><span class="sxs-lookup"><span data-stu-id="e89a9-121">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e89a9-122">сиопид</span><span class="sxs-lookup"><span data-stu-id="e89a9-122">siopID</span></span></p></td>
<td><p><span data-ttu-id="e89a9-123">Первичный ключ.</span><span class="sxs-lookup"><span data-stu-id="e89a9-123">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

