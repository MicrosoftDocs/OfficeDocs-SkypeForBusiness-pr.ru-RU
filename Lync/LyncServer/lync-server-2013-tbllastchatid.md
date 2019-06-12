---
title: 'Lync Server 2013: tblLastChatId'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: tblLastChatId
ms:assetid: 17a4ffbe-cca9-4ec5-ae46-38a15274889a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558616(v=OCS.15)
ms:contentKeyID: 48183513
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bddc89952b544a71c469538cf11f65658e19e38d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849572"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tbllastchatid-in-lync-server-2013"></a><span data-ttu-id="02997-102">tblLastChatId в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="02997-102">tblLastChatId in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="02997-103">_**Тема последнего изменения:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="02997-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="02997-104">Тблластчатид включает последний идентификатор чата, который был создан (и использован в таблице Тблчат) для каждого пользователя.</span><span class="sxs-lookup"><span data-stu-id="02997-104">tblLastChatId contains the last chat ID that was generated (and used in the tblChat table) for each user.</span></span>

### <a name="columns"></a><span data-ttu-id="02997-105">Столбцов</span><span class="sxs-lookup"><span data-stu-id="02997-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="02997-106">Столбец</span><span class="sxs-lookup"><span data-stu-id="02997-106">Column</span></span></th>
<th><span data-ttu-id="02997-107">Тип</span><span class="sxs-lookup"><span data-stu-id="02997-107">Type</span></span></th>
<th><span data-ttu-id="02997-108">Описание</span><span class="sxs-lookup"><span data-stu-id="02997-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="02997-109">Нодеид</span><span class="sxs-lookup"><span data-stu-id="02997-109">nodeID</span></span></p></td>
<td><p><span data-ttu-id="02997-110">int, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="02997-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="02997-111">Идентификатор узла (комната чата — только тип).</span><span class="sxs-lookup"><span data-stu-id="02997-111">Node ID (chat room-type only).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="02997-112">Ластчатид</span><span class="sxs-lookup"><span data-stu-id="02997-112">lastChatID</span></span></p></td>
<td><p><span data-ttu-id="02997-113">bigint, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="02997-113">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="02997-114">НОМЕР последнего использованного чата.</span><span class="sxs-lookup"><span data-stu-id="02997-114">Last used chat ID.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="02997-115">Параметры</span><span class="sxs-lookup"><span data-stu-id="02997-115">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="02997-116">Столбец</span><span class="sxs-lookup"><span data-stu-id="02997-116">Column</span></span></th>
<th><span data-ttu-id="02997-117">Описание</span><span class="sxs-lookup"><span data-stu-id="02997-117">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="02997-118">&lt;Нодеид, Ластчатид&gt;</span><span class="sxs-lookup"><span data-stu-id="02997-118">&lt;nodeID, lastChatID&gt;</span></span></p></td>
<td><p><span data-ttu-id="02997-119">Первичный ключ (для обработки достаточно просто Нодеид).</span><span class="sxs-lookup"><span data-stu-id="02997-119">Primary key (just nodeID is sufficient for processing).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="02997-120">Нодеид</span><span class="sxs-lookup"><span data-stu-id="02997-120">nodeID</span></span></p></td>
<td><p><span data-ttu-id="02997-121">Внешний ключ с подстановкой в таблице Тблноде. Нодеид.</span><span class="sxs-lookup"><span data-stu-id="02997-121">Foreign key with lookup in tblNode.nodeID table.</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a><span data-ttu-id="02997-122">См. также</span><span class="sxs-lookup"><span data-stu-id="02997-122">See Also</span></span>


[<span data-ttu-id="02997-123">tblChat в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="02997-123">tblChat in Lync Server 2013</span></span>](lync-server-2013-tblchat.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

