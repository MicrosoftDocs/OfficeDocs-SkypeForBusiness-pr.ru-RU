---
title: 'Lync Server 2013: tblLastChatId'
description: 'Lync Server 2013: tblLastChatId.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblLastChatId
ms:assetid: 17a4ffbe-cca9-4ec5-ae46-38a15274889a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558616(v=OCS.15)
ms:contentKeyID: 48183513
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 69e80a735e70c8a03441038f5e58eb93e0af1f82
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547605"
---
# <a name="tbllastchatid-in-lync-server-2013"></a><span data-ttu-id="3712e-103">tblLastChatId в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3712e-103">tblLastChatId in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3712e-104">_**Последнее изменение темы:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="3712e-104">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="3712e-105">Таблица tblLastChatId содержит последние идентификаторы чатов, которые были созданы (и использованы в таблице tblChat) для каждого пользователя.</span><span class="sxs-lookup"><span data-stu-id="3712e-105">tblLastChatId contains the last chat ID that was generated (and used in the tblChat table) for each user.</span></span>

### <a name="columns"></a><span data-ttu-id="3712e-106">Столбцы</span><span class="sxs-lookup"><span data-stu-id="3712e-106">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3712e-107">Столбец</span><span class="sxs-lookup"><span data-stu-id="3712e-107">Column</span></span></th>
<th><span data-ttu-id="3712e-108">Тип</span><span class="sxs-lookup"><span data-stu-id="3712e-108">Type</span></span></th>
<th><span data-ttu-id="3712e-109">Описание</span><span class="sxs-lookup"><span data-stu-id="3712e-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3712e-110">nodeID</span><span class="sxs-lookup"><span data-stu-id="3712e-110">nodeID</span></span></p></td>
<td><p><span data-ttu-id="3712e-111">int, not null</span><span class="sxs-lookup"><span data-stu-id="3712e-111">int, not null</span></span></p></td>
<td><p><span data-ttu-id="3712e-112">Идентификатор узла (только типа комнаты чата).</span><span class="sxs-lookup"><span data-stu-id="3712e-112">Node ID (chat room-type only).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3712e-113">ластчатид</span><span class="sxs-lookup"><span data-stu-id="3712e-113">lastChatID</span></span></p></td>
<td><p><span data-ttu-id="3712e-114">bigint, not null</span><span class="sxs-lookup"><span data-stu-id="3712e-114">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="3712e-115">Идентификатор последнего чата.</span><span class="sxs-lookup"><span data-stu-id="3712e-115">Last used chat ID.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="3712e-116">Keys</span><span class="sxs-lookup"><span data-stu-id="3712e-116">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3712e-117">Столбец</span><span class="sxs-lookup"><span data-stu-id="3712e-117">Column</span></span></th>
<th><span data-ttu-id="3712e-118">Описание</span><span class="sxs-lookup"><span data-stu-id="3712e-118">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3712e-119">&lt;nodeID, Ластчатид&gt;</span><span class="sxs-lookup"><span data-stu-id="3712e-119">&lt;nodeID, lastChatID&gt;</span></span></p></td>
<td><p><span data-ttu-id="3712e-120">Первичный ключ (для обработки достаточно nodeID).</span><span class="sxs-lookup"><span data-stu-id="3712e-120">Primary key (just nodeID is sufficient for processing).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3712e-121">nodeID</span><span class="sxs-lookup"><span data-stu-id="3712e-121">nodeID</span></span></p></td>
<td><p><span data-ttu-id="3712e-122">Внешний ключ с поиском в таблице tblNode.nodeID.</span><span class="sxs-lookup"><span data-stu-id="3712e-122">Foreign key with lookup in tblNode.nodeID table.</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a><span data-ttu-id="3712e-123">См. также</span><span class="sxs-lookup"><span data-stu-id="3712e-123">See Also</span></span>


[<span data-ttu-id="3712e-124">tblChat в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3712e-124">tblChat in Lync Server 2013</span></span>](lync-server-2013-tblchat.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

