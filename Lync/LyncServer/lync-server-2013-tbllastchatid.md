---
title: 'Lync Server 2013: tblLastChatId'
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
ms.openlocfilehash: b184d863ff9d0404fbc05b90a88f7c203499262a
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48523826"
---
# <a name="tbllastchatid-in-lync-server-2013"></a><span data-ttu-id="b5a4c-102">tblLastChatId в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b5a4c-102">tblLastChatId in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b5a4c-103">_**Последнее изменение темы:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="b5a4c-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="b5a4c-104">Таблица tblLastChatId содержит последние идентификаторы чатов, которые были созданы (и использованы в таблице tblChat) для каждого пользователя.</span><span class="sxs-lookup"><span data-stu-id="b5a4c-104">tblLastChatId contains the last chat ID that was generated (and used in the tblChat table) for each user.</span></span>

### <a name="columns"></a><span data-ttu-id="b5a4c-105">Столбцы</span><span class="sxs-lookup"><span data-stu-id="b5a4c-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b5a4c-106">Столбец</span><span class="sxs-lookup"><span data-stu-id="b5a4c-106">Column</span></span></th>
<th><span data-ttu-id="b5a4c-107">Тип</span><span class="sxs-lookup"><span data-stu-id="b5a4c-107">Type</span></span></th>
<th><span data-ttu-id="b5a4c-108">Описание</span><span class="sxs-lookup"><span data-stu-id="b5a4c-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b5a4c-109">nodeID</span><span class="sxs-lookup"><span data-stu-id="b5a4c-109">nodeID</span></span></p></td>
<td><p><span data-ttu-id="b5a4c-110">int, not null</span><span class="sxs-lookup"><span data-stu-id="b5a4c-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="b5a4c-111">Идентификатор узла (только типа комнаты чата).</span><span class="sxs-lookup"><span data-stu-id="b5a4c-111">Node ID (chat room-type only).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b5a4c-112">ластчатид</span><span class="sxs-lookup"><span data-stu-id="b5a4c-112">lastChatID</span></span></p></td>
<td><p><span data-ttu-id="b5a4c-113">bigint, not null</span><span class="sxs-lookup"><span data-stu-id="b5a4c-113">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="b5a4c-114">Идентификатор последнего чата.</span><span class="sxs-lookup"><span data-stu-id="b5a4c-114">Last used chat ID.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="b5a4c-115">Keys</span><span class="sxs-lookup"><span data-stu-id="b5a4c-115">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b5a4c-116">Столбец</span><span class="sxs-lookup"><span data-stu-id="b5a4c-116">Column</span></span></th>
<th><span data-ttu-id="b5a4c-117">Описание</span><span class="sxs-lookup"><span data-stu-id="b5a4c-117">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b5a4c-118">&lt;nodeID, Ластчатид&gt;</span><span class="sxs-lookup"><span data-stu-id="b5a4c-118">&lt;nodeID, lastChatID&gt;</span></span></p></td>
<td><p><span data-ttu-id="b5a4c-119">Первичный ключ (для обработки достаточно nodeID).</span><span class="sxs-lookup"><span data-stu-id="b5a4c-119">Primary key (just nodeID is sufficient for processing).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b5a4c-120">nodeID</span><span class="sxs-lookup"><span data-stu-id="b5a4c-120">nodeID</span></span></p></td>
<td><p><span data-ttu-id="b5a4c-121">Внешний ключ с поиском в таблице tblNode.nodeID.</span><span class="sxs-lookup"><span data-stu-id="b5a4c-121">Foreign key with lookup in tblNode.nodeID table.</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a><span data-ttu-id="b5a4c-122">См. также</span><span class="sxs-lookup"><span data-stu-id="b5a4c-122">See Also</span></span>


[<span data-ttu-id="b5a4c-123">tblChat в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b5a4c-123">tblChat in Lync Server 2013</span></span>](lync-server-2013-tblchat.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

