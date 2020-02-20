---
title: 'Lync Server 2013: таблица MCUs'
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
ms.openlocfilehash: ad3037f81ccfe2b54f464a3e84d34a97366a3bb0
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42149889"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="mcus-table-in-lync-server-2013"></a><span data-ttu-id="1a848-102">Таблица MCUs в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1a848-102">Mcus table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1a848-103">_**Последнее изменение темы:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="1a848-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="1a848-104">Таблица MCUs является вспомогательной таблицей.</span><span class="sxs-lookup"><span data-stu-id="1a848-104">The Mcus table is a supporting table.</span></span> <span data-ttu-id="1a848-105">Каждая запись содержит сведения об одной службе конференц-связи.</span><span class="sxs-lookup"><span data-stu-id="1a848-105">Each record stores information about one conferencing service.</span></span> <span data-ttu-id="1a848-106">Они могут включать службу конференц-связи для обмена мгновенными сообщениями и службу конференц-связи, выполняемую как процессы на интерфейсных серверах, а также службу веб-конференций и службу аудио-и видеоконференций.</span><span class="sxs-lookup"><span data-stu-id="1a848-106">These can include the IM Conferencing service and the Telephony Conferencing service (which run as processes on front-end servers), and the Web Conferencing service and A/V Conferencing service.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1a848-107">Столбец</span><span class="sxs-lookup"><span data-stu-id="1a848-107">Column</span></span></th>
<th><span data-ttu-id="1a848-108">Тип данных</span><span class="sxs-lookup"><span data-stu-id="1a848-108">Data Type</span></span></th>
<th><span data-ttu-id="1a848-109">Ключ или индекс</span><span class="sxs-lookup"><span data-stu-id="1a848-109">Key/Index</span></span></th>
<th><span data-ttu-id="1a848-110">Сведения</span><span class="sxs-lookup"><span data-stu-id="1a848-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1a848-111"><strong>мкуид</strong></span><span class="sxs-lookup"><span data-stu-id="1a848-111"><strong>McuId</strong></span></span></p></td>
<td><p><span data-ttu-id="1a848-112">int</span><span class="sxs-lookup"><span data-stu-id="1a848-112">int</span></span></p></td>
<td><p><span data-ttu-id="1a848-113">Primary</span><span class="sxs-lookup"><span data-stu-id="1a848-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="1a848-114">Уникальный номер, идентифицирующий этот сервер конференц-связи.</span><span class="sxs-lookup"><span data-stu-id="1a848-114">Unique number identifying this conferencing server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1a848-115"><strong>мкуури</strong></span><span class="sxs-lookup"><span data-stu-id="1a848-115"><strong>McuUri</strong></span></span></p></td>
<td><p><span data-ttu-id="1a848-116">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="1a848-116">nvarchar(450)</span></span></p></td>
<td><p> </p></td>
<td><p> </p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1a848-117"><strong>мкутипеид</strong></span><span class="sxs-lookup"><span data-stu-id="1a848-117"><strong>McuTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="1a848-118">ининт</span><span class="sxs-lookup"><span data-stu-id="1a848-118">inyint</span></span></p></td>
<td><p><span data-ttu-id="1a848-119"> Правительства</span><span class="sxs-lookup"><span data-stu-id="1a848-119"> Foreign</span></span></p></td>
<td><p><span data-ttu-id="1a848-120">Тип сервера конференций, например conf: Chat (для мгновенных сообщений) или conf: Audio-Video.</span><span class="sxs-lookup"><span data-stu-id="1a848-120">Conferencing server type, such as conf:chat (for IMs) or conf:audio-video.</span></span> <span data-ttu-id="1a848-121">Дополнительные сведения см. <a href="lync-server-2013-uritypes-table.md">в таблице таблица uritypes в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="1a848-121">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

