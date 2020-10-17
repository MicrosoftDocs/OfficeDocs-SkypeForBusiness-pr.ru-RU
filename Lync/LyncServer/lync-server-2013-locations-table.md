---
title: 'Lync Server 2013: таблица Locations'
description: 'Lync Server 2013: Locations Table.'
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
ms.openlocfilehash: 9d07b6d3d3820f4efb3310adf0734a7e10c53e6d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48570585"
---
# <a name="locations-table-in-lync-server-2013"></a><span data-ttu-id="f43ff-103">Таблица Locations в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f43ff-103">Locations table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f43ff-104">_**Последнее изменение темы:** 2012-05-25_</span><span class="sxs-lookup"><span data-stu-id="f43ff-104">_**Topic Last Modified:** 2012-05-25_</span></span>

<span data-ttu-id="f43ff-105">Каждая запись представляет одну ссылку на расположение в экстренном звонке, например звонке E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="f43ff-105">Each record represents one location reference in an emergency call, like an E9-1-1 call.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f43ff-106">Столбец</span><span class="sxs-lookup"><span data-stu-id="f43ff-106">Column</span></span></th>
<th><span data-ttu-id="f43ff-107">Тип данных</span><span class="sxs-lookup"><span data-stu-id="f43ff-107">Data Type</span></span></th>
<th><span data-ttu-id="f43ff-108">Ключ или индекс</span><span class="sxs-lookup"><span data-stu-id="f43ff-108">Key/Index</span></span></th>
<th><span data-ttu-id="f43ff-109">Сведения</span><span class="sxs-lookup"><span data-stu-id="f43ff-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f43ff-110"><strong>сессионидтиме</strong></span><span class="sxs-lookup"><span data-stu-id="f43ff-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="f43ff-111">datetime</span><span class="sxs-lookup"><span data-stu-id="f43ff-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="f43ff-112">Основной, внешний</span><span class="sxs-lookup"><span data-stu-id="f43ff-112">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="f43ff-113">Время запроса сеанса.</span><span class="sxs-lookup"><span data-stu-id="f43ff-113">Time of session request.</span></span> <span data-ttu-id="f43ff-114">В сочетании с параметром <strong>SessionIdSeq</strong> определяет сеанс уникальным образом.</span><span class="sxs-lookup"><span data-stu-id="f43ff-114">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="f43ff-115">Дополнительные сведения см. <a href="lync-server-2013-dialogs-table.md">в таблице диалоговых окон в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="f43ff-115">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f43ff-116"><strong>сессионидсек</strong></span><span class="sxs-lookup"><span data-stu-id="f43ff-116"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="f43ff-117">int</span><span class="sxs-lookup"><span data-stu-id="f43ff-117">int</span></span></p></td>
<td><p><span data-ttu-id="f43ff-118">Основной, внешний</span><span class="sxs-lookup"><span data-stu-id="f43ff-118">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="f43ff-119">Идентификатор для идентификации сеанса.</span><span class="sxs-lookup"><span data-stu-id="f43ff-119">ID number to identify the session.</span></span> <span data-ttu-id="f43ff-120">В сочетании с параметром <strong>SessionIdTime</strong> определяет сеанс уникальным образом.</span><span class="sxs-lookup"><span data-stu-id="f43ff-120">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="f43ff-121">Дополнительные сведения см. <a href="lync-server-2013-dialogs-table.md">в таблице диалоговых окон в Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="f43ff-121">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f43ff-122"><strong>Location</strong></span><span class="sxs-lookup"><span data-stu-id="f43ff-122"><strong>Location</strong></span></span></p></td>
<td><p><span data-ttu-id="f43ff-123">nvarchar (max)</span><span class="sxs-lookup"><span data-stu-id="f43ff-123">nvarchar(max)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f43ff-124">Расположение экстренного звонка.</span><span class="sxs-lookup"><span data-stu-id="f43ff-124">Location of emergency call.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

