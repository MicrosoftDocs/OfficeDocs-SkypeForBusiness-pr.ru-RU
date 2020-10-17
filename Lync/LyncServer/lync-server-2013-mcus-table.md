---
title: 'Lync Server 2013: таблица MCUs'
description: 'Lync Server 2013: таблица MCUs.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Mcus table
ms:assetid: 271b7963-8fd8-4d92-a701-1a62aaf895ee
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425742(v=OCS.15)
ms:contentKeyID: 48183674
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b0b5d0bcbebb5efc1d767776b4581b18d9f2ed18
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48556485"
---
# <a name="mcus-table-in-lync-server-2013"></a><span data-ttu-id="cefc0-103">Таблица MCUs в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cefc0-103">Mcus table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cefc0-104">_**Последнее изменение темы:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="cefc0-104">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="cefc0-105">Таблица MCUs является вспомогательной таблицей.</span><span class="sxs-lookup"><span data-stu-id="cefc0-105">The Mcus table is a supporting table.</span></span> <span data-ttu-id="cefc0-106">Каждая запись содержит сведения об одной службе конференц-связи.</span><span class="sxs-lookup"><span data-stu-id="cefc0-106">Each record stores information about one conferencing service.</span></span> <span data-ttu-id="cefc0-107">Они могут включать службу конференц-связи для обмена мгновенными сообщениями и службу конференц-связи, выполняемую как процессы на интерфейсных серверах, а также службу веб-конференций и службу аудио-и видеоконференций.</span><span class="sxs-lookup"><span data-stu-id="cefc0-107">These can include the IM Conferencing service and the Telephony Conferencing service (which run as processes on front-end servers), and the Web Conferencing service and A/V Conferencing service.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="cefc0-108">Столбец</span><span class="sxs-lookup"><span data-stu-id="cefc0-108">Column</span></span></th>
<th><span data-ttu-id="cefc0-109">Тип данных</span><span class="sxs-lookup"><span data-stu-id="cefc0-109">Data Type</span></span></th>
<th><span data-ttu-id="cefc0-110">Ключ или индекс</span><span class="sxs-lookup"><span data-stu-id="cefc0-110">Key/Index</span></span></th>
<th><span data-ttu-id="cefc0-111">Сведения</span><span class="sxs-lookup"><span data-stu-id="cefc0-111">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cefc0-112"><strong>мкуид</strong></span><span class="sxs-lookup"><span data-stu-id="cefc0-112"><strong>McuId</strong></span></span></p></td>
<td><p><span data-ttu-id="cefc0-113">int</span><span class="sxs-lookup"><span data-stu-id="cefc0-113">int</span></span></p></td>
<td><p><span data-ttu-id="cefc0-114">Primary</span><span class="sxs-lookup"><span data-stu-id="cefc0-114">Primary</span></span></p></td>
<td><p><span data-ttu-id="cefc0-115">Уникальный номер, идентифицирующий этот сервер конференц-связи.</span><span class="sxs-lookup"><span data-stu-id="cefc0-115">Unique number identifying this conferencing server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cefc0-116"><strong>мкуури</strong></span><span class="sxs-lookup"><span data-stu-id="cefc0-116"><strong>McuUri</strong></span></span></p></td>
<td><p><span data-ttu-id="cefc0-117">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="cefc0-117">nvarchar(450)</span></span></p></td>
<td><p> </p></td>
<td><p> </p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cefc0-118"><strong>мкутипеид</strong></span><span class="sxs-lookup"><span data-stu-id="cefc0-118"><strong>McuTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="cefc0-119">ининт</span><span class="sxs-lookup"><span data-stu-id="cefc0-119">inyint</span></span></p></td>
<td><p><span data-ttu-id="cefc0-120"> Правительства</span><span class="sxs-lookup"><span data-stu-id="cefc0-120"> Foreign</span></span></p></td>
<td><p><span data-ttu-id="cefc0-121">Тип сервера конференций, например conf: Chat (для мгновенных сообщений) или conf: Audio-Video.</span><span class="sxs-lookup"><span data-stu-id="cefc0-121">Conferencing server type, such as conf:chat (for IMs) or conf:audio-video.</span></span> <span data-ttu-id="cefc0-122">Дополнительные сведения см. <a href="lync-server-2013-uritypes-table.md">в таблице таблица uritypes в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="cefc0-122">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

