---
title: 'Lync Server 2013: таблица Mcus'
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
ms.openlocfilehash: 522c7babbda63c550679dab1eb8eb03114417169
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41737179"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="mcus-table-in-lync-server-2013"></a><span data-ttu-id="13560-102">Таблица Mcus в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="13560-102">Mcus table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="13560-103">_**Тема последнего изменения:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="13560-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="13560-104">Таблица Мкус является вспомогательной таблицей.</span><span class="sxs-lookup"><span data-stu-id="13560-104">The Mcus table is a supporting table.</span></span> <span data-ttu-id="13560-105">Каждая запись содержит сведения о одной службе конференц-связи.</span><span class="sxs-lookup"><span data-stu-id="13560-105">Each record stores information about one conferencing service.</span></span> <span data-ttu-id="13560-106">К ним относятся служба конференций обмена мгновенными сообщениями и служба конференц-связи с телефонным подключением (которая запускается как процессы на серверах переднего плана), а также службы "веб-конференции" и "Конференция".</span><span class="sxs-lookup"><span data-stu-id="13560-106">These can include the IM Conferencing service and the Telephony Conferencing service (which run as processes on front-end servers), and the Web Conferencing service and A/V Conferencing service.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="13560-107">Столбец</span><span class="sxs-lookup"><span data-stu-id="13560-107">Column</span></span></th>
<th><span data-ttu-id="13560-108">Тип данных</span><span class="sxs-lookup"><span data-stu-id="13560-108">Data Type</span></span></th>
<th><span data-ttu-id="13560-109">Ключ/индекс</span><span class="sxs-lookup"><span data-stu-id="13560-109">Key/Index</span></span></th>
<th><span data-ttu-id="13560-110">Сведения</span><span class="sxs-lookup"><span data-stu-id="13560-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="13560-111"><strong>мкуид</strong></span><span class="sxs-lookup"><span data-stu-id="13560-111"><strong>McuId</strong></span></span></p></td>
<td><p><span data-ttu-id="13560-112">целое</span><span class="sxs-lookup"><span data-stu-id="13560-112">int</span></span></p></td>
<td><p><span data-ttu-id="13560-113">Primary</span><span class="sxs-lookup"><span data-stu-id="13560-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="13560-114">Уникальный номер, идентифицирующий этот сервер конференц-связи.</span><span class="sxs-lookup"><span data-stu-id="13560-114">Unique number identifying this conferencing server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="13560-115"><strong>мкуури</strong></span><span class="sxs-lookup"><span data-stu-id="13560-115"><strong>McuUri</strong></span></span></p></td>
<td><p><span data-ttu-id="13560-116">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="13560-116">nvarchar(450)</span></span></p></td>
<td><p> </p></td>
<td><p> </p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="13560-117"><strong>мкутипеид</strong></span><span class="sxs-lookup"><span data-stu-id="13560-117"><strong>McuTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="13560-118">ининт</span><span class="sxs-lookup"><span data-stu-id="13560-118">inyint</span></span></p></td>
<td><p><span data-ttu-id="13560-119"> Другом</span><span class="sxs-lookup"><span data-stu-id="13560-119"> Foreign</span></span></p></td>
<td><p><span data-ttu-id="13560-120">Тип сервера конференций, например conf: Chat (для мгновенных сообщений) или conf: аудио-видео.</span><span class="sxs-lookup"><span data-stu-id="13560-120">Conferencing server type, such as conf:chat (for IMs) or conf:audio-video.</span></span> <span data-ttu-id="13560-121">Для получения дополнительных сведений ознакомьтесь с <a href="lync-server-2013-uritypes-table.md">таблицей уритипес в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="13560-121">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

