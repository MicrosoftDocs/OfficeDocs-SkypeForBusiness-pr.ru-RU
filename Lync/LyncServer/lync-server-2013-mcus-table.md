---
title: 'Lync Server 2013: таблица Mcus'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Mcus table
ms:assetid: 271b7963-8fd8-4d92-a701-1a62aaf895ee
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425742(v=OCS.15)
ms:contentKeyID: 48183674
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bf0a34d24bf60770f2b1e2664a89993f5917d854
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34827538"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="mcus-table-in-lync-server-2013"></a><span data-ttu-id="be6a6-102">Таблица Mcus в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="be6a6-102">Mcus table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="be6a6-103">_**Тема последнего изменения:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="be6a6-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="be6a6-104">Таблица Мкус является вспомогательной таблицей.</span><span class="sxs-lookup"><span data-stu-id="be6a6-104">The Mcus table is a supporting table.</span></span> <span data-ttu-id="be6a6-105">Каждая запись содержит сведения о одной службе конференц-связи.</span><span class="sxs-lookup"><span data-stu-id="be6a6-105">Each record stores information about one conferencing service.</span></span> <span data-ttu-id="be6a6-106">К ним относятся служба конференций обмена мгновенными сообщениями и служба конференц-связи с телефонным подключением (которая запускается как процессы на серверах переднего плана), а также службы "веб-конференции" и "Конференция".</span><span class="sxs-lookup"><span data-stu-id="be6a6-106">These can include the IM Conferencing service and the Telephony Conferencing service (which run as processes on front-end servers), and the Web Conferencing service and A/V Conferencing service.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="be6a6-107">Столбец</span><span class="sxs-lookup"><span data-stu-id="be6a6-107">Column</span></span></th>
<th><span data-ttu-id="be6a6-108">Тип данных</span><span class="sxs-lookup"><span data-stu-id="be6a6-108">Data Type</span></span></th>
<th><span data-ttu-id="be6a6-109">Ключ/индекс</span><span class="sxs-lookup"><span data-stu-id="be6a6-109">Key/Index</span></span></th>
<th><span data-ttu-id="be6a6-110">Сведения</span><span class="sxs-lookup"><span data-stu-id="be6a6-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="be6a6-111"><strong>Мкуид</strong></span><span class="sxs-lookup"><span data-stu-id="be6a6-111"><strong>McuId</strong></span></span></p></td>
<td><p><span data-ttu-id="be6a6-112">целое</span><span class="sxs-lookup"><span data-stu-id="be6a6-112">int</span></span></p></td>
<td><p><span data-ttu-id="be6a6-113">Primary</span><span class="sxs-lookup"><span data-stu-id="be6a6-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="be6a6-114">Уникальный номер, идентифицирующий этот сервер конференц-связи.</span><span class="sxs-lookup"><span data-stu-id="be6a6-114">Unique number identifying this conferencing server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="be6a6-115"><strong>Мкуури</strong></span><span class="sxs-lookup"><span data-stu-id="be6a6-115"><strong>McuUri</strong></span></span></p></td>
<td><p><span data-ttu-id="be6a6-116">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="be6a6-116">nvarchar(450)</span></span></p></td>
<td><p> </p></td>
<td><p> </p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="be6a6-117"><strong>Мкутипеид</strong></span><span class="sxs-lookup"><span data-stu-id="be6a6-117"><strong>McuTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="be6a6-118">ининт</span><span class="sxs-lookup"><span data-stu-id="be6a6-118">inyint</span></span></p></td>
<td><p><span data-ttu-id="be6a6-119"> Другом</span><span class="sxs-lookup"><span data-stu-id="be6a6-119"> Foreign</span></span></p></td>
<td><p><span data-ttu-id="be6a6-120">Тип сервера конференций, например conf: Chat (для мгновенных сообщений) или conf: аудио-видео.</span><span class="sxs-lookup"><span data-stu-id="be6a6-120">Conferencing server type, such as conf:chat (for IMs) or conf:audio-video.</span></span> <span data-ttu-id="be6a6-121">Для получения дополнительных сведений ознакомьтесь с <a href="lync-server-2013-uritypes-table.md">таблицей уритипес в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="be6a6-121">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

