---
title: 'Lync Server 2013: tblSiopWhiteList'
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
ms.openlocfilehash: 3cac704c6f62903c502ae5a4345ee0848c775d6f
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48536216"
---
# <a name="tblsiopwhitelist-in-lync-server-2013"></a><span data-ttu-id="9c934-102">tblSiopWhiteList в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9c934-102">tblSiopWhiteList in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9c934-103">_**Последнее изменение темы:** 2012-06-28_</span><span class="sxs-lookup"><span data-stu-id="9c934-103">_**Topic Last Modified:** 2012-06-28_</span></span>

<span data-ttu-id="9c934-104">tblSiopWhiteList — это список зарегистрированных надстроек, которые могут быть связаны с узлами.</span><span class="sxs-lookup"><span data-stu-id="9c934-104">tblSiopWhiteList is the list of registered add-ins that can be associated with nodes.</span></span>

### <a name="columns"></a><span data-ttu-id="9c934-105">Столбцы</span><span class="sxs-lookup"><span data-stu-id="9c934-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9c934-106">Столбец</span><span class="sxs-lookup"><span data-stu-id="9c934-106">Column</span></span></th>
<th><span data-ttu-id="9c934-107">Тип</span><span class="sxs-lookup"><span data-stu-id="9c934-107">Type</span></span></th>
<th><span data-ttu-id="9c934-108">Описание</span><span class="sxs-lookup"><span data-stu-id="9c934-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9c934-109">сиопид</span><span class="sxs-lookup"><span data-stu-id="9c934-109">siopID</span></span></p></td>
<td><p><span data-ttu-id="9c934-110">GUID, отлично от null</span><span class="sxs-lookup"><span data-stu-id="9c934-110">GUID, not null</span></span></p></td>
<td><p><span data-ttu-id="9c934-111">GUID надстройки.</span><span class="sxs-lookup"><span data-stu-id="9c934-111">GUID of the add-in.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9c934-112">сиопнаме</span><span class="sxs-lookup"><span data-stu-id="9c934-112">siopName</span></span></p></td>
<td><p><span data-ttu-id="9c934-113">nvarchar (50), отлично от null</span><span class="sxs-lookup"><span data-stu-id="9c934-113">nvarchar (50), not null</span></span></p></td>
<td><p><span data-ttu-id="9c934-114">Отображаемое имя надстройки.</span><span class="sxs-lookup"><span data-stu-id="9c934-114">Display-name of the add-in.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9c934-115">сиопурл</span><span class="sxs-lookup"><span data-stu-id="9c934-115">siopUrl</span></span></p></td>
<td><p><span data-ttu-id="9c934-116">nvarchar (255), отлично от null</span><span class="sxs-lookup"><span data-stu-id="9c934-116">nvarchar (255), not null</span></span></p></td>
<td><p><span data-ttu-id="9c934-117">URL-адрес надстройки.</span><span class="sxs-lookup"><span data-stu-id="9c934-117">URL of the add-in.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="9c934-118">Key</span><span class="sxs-lookup"><span data-stu-id="9c934-118">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9c934-119">Столбец</span><span class="sxs-lookup"><span data-stu-id="9c934-119">Column</span></span></th>
<th><span data-ttu-id="9c934-120">Описание</span><span class="sxs-lookup"><span data-stu-id="9c934-120">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9c934-121">сиопид</span><span class="sxs-lookup"><span data-stu-id="9c934-121">siopID</span></span></p></td>
<td><p><span data-ttu-id="9c934-122">Первичный ключ.</span><span class="sxs-lookup"><span data-stu-id="9c934-122">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

