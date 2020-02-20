---
title: 'Lync Server 2013: таблица Locations'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Locations table
ms:assetid: 78dc1b14-5394-4f8e-89d3-4ba593272a04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398596(v=OCS.15)
ms:contentKeyID: 48184579
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2a294c41f75b988e0c7f442e6f5091b633f88394
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42154991"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="locations-table-in-lync-server-2013"></a><span data-ttu-id="880fd-102">Таблица Locations в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="880fd-102">Locations table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="880fd-103">_**Последнее изменение темы:** 2012-05-25_</span><span class="sxs-lookup"><span data-stu-id="880fd-103">_**Topic Last Modified:** 2012-05-25_</span></span>

<span data-ttu-id="880fd-104">Каждая запись представляет одну ссылку на расположение в экстренном звонке, например звонке E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="880fd-104">Each record represents one location reference in an emergency call, like an E9-1-1 call.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="880fd-105">Столбец</span><span class="sxs-lookup"><span data-stu-id="880fd-105">Column</span></span></th>
<th><span data-ttu-id="880fd-106">Тип данных</span><span class="sxs-lookup"><span data-stu-id="880fd-106">Data Type</span></span></th>
<th><span data-ttu-id="880fd-107">Ключ или индекс</span><span class="sxs-lookup"><span data-stu-id="880fd-107">Key/Index</span></span></th>
<th><span data-ttu-id="880fd-108">Сведения</span><span class="sxs-lookup"><span data-stu-id="880fd-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="880fd-109"><strong>сессионидтиме</strong></span><span class="sxs-lookup"><span data-stu-id="880fd-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="880fd-110">datetime</span><span class="sxs-lookup"><span data-stu-id="880fd-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="880fd-111">Основной, внешний</span><span class="sxs-lookup"><span data-stu-id="880fd-111">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="880fd-112">Время запроса сеанса.</span><span class="sxs-lookup"><span data-stu-id="880fd-112">Time of session request.</span></span> <span data-ttu-id="880fd-113">В сочетании с параметром <strong>SessionIdSeq</strong> определяет сеанс уникальным образом.</span><span class="sxs-lookup"><span data-stu-id="880fd-113">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="880fd-114">Дополнительные сведения см. <a href="lync-server-2013-dialogs-table.md">в таблице диалоговых окон в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="880fd-114">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="880fd-115"><strong>сессионидсек</strong></span><span class="sxs-lookup"><span data-stu-id="880fd-115"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="880fd-116">int</span><span class="sxs-lookup"><span data-stu-id="880fd-116">int</span></span></p></td>
<td><p><span data-ttu-id="880fd-117">Первичный, внешний</span><span class="sxs-lookup"><span data-stu-id="880fd-117">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="880fd-118">Идентификатор для идентификации сеанса.</span><span class="sxs-lookup"><span data-stu-id="880fd-118">ID number to identify the session.</span></span> <span data-ttu-id="880fd-119">В сочетании с параметром <strong>SessionIdTime</strong> определяет сеанс уникальным образом.</span><span class="sxs-lookup"><span data-stu-id="880fd-119">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="880fd-120">Дополнительные сведения см. <a href="lync-server-2013-dialogs-table.md">в таблице диалоговых окон в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="880fd-120">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="880fd-121"><strong>Location</strong></span><span class="sxs-lookup"><span data-stu-id="880fd-121"><strong>Location</strong></span></span></p></td>
<td><p><span data-ttu-id="880fd-122">nvarchar (max)</span><span class="sxs-lookup"><span data-stu-id="880fd-122">nvarchar(max)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="880fd-123">Расположение экстренного звонка.</span><span class="sxs-lookup"><span data-stu-id="880fd-123">Location of emergency call.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

