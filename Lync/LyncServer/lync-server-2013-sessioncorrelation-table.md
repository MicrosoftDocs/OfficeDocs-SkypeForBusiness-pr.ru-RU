---
title: 'Lync Server 2013: таблица таблица sessioncorrelation'
description: 'Lync Server 2013: таблица таблица sessioncorrelation.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: SessionCorrelation table
ms:assetid: 041705e1-7290-464f-95f8-96256cfa2e3e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398091(v=OCS.15)
ms:contentKeyID: 48183267
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 814b7e8539d89f87e7df60ceb03e70800553fb55
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48579665"
---
# <a name="sessioncorrelation-table-in-lync-server-2013"></a><span data-ttu-id="815a3-103">Таблица Таблица sessioncorrelation в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="815a3-103">SessionCorrelation table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="815a3-104">_**Последнее изменение темы:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="815a3-104">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="815a3-105">Таблица Таблица sessioncorrelation является вспомогательной таблицей.</span><span class="sxs-lookup"><span data-stu-id="815a3-105">The SessionCorrelation table is a supporting table.</span></span> <span data-ttu-id="815a3-106">Каждая запись представляет один элемент CorrelationID, который используется для корреляции нескольких сеансов.</span><span class="sxs-lookup"><span data-stu-id="815a3-106">Each record represents one CorrelationID which is used to correlate multiple sessions.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="815a3-107"><strong>Column</strong></span><span class="sxs-lookup"><span data-stu-id="815a3-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="815a3-108"><strong>Тип данных</strong></span><span class="sxs-lookup"><span data-stu-id="815a3-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="815a3-109"><strong>Ключ или индекс</strong></span><span class="sxs-lookup"><span data-stu-id="815a3-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="815a3-110"><strong>Details</strong></span><span class="sxs-lookup"><span data-stu-id="815a3-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="815a3-111"><strong>Контрольная сумма</strong></span><span class="sxs-lookup"><span data-stu-id="815a3-111"><strong>Checksum</strong></span></span></p></td>
<td><p><span data-ttu-id="815a3-112">int</span><span class="sxs-lookup"><span data-stu-id="815a3-112">int</span></span></p></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="815a3-113"><strong>коррелатионкэй</strong></span><span class="sxs-lookup"><span data-stu-id="815a3-113"><strong>CorrelationKey</strong></span></span></p></td>
<td><p><span data-ttu-id="815a3-114">int</span><span class="sxs-lookup"><span data-stu-id="815a3-114">int</span></span></p></td>
<td><p><span data-ttu-id="815a3-115">Primary</span><span class="sxs-lookup"><span data-stu-id="815a3-115">Primary</span></span></p></td>
<td><p><span data-ttu-id="815a3-116">Уникальный номер, идентифицирующий этот сервер аудио-и видеоконференций.</span><span class="sxs-lookup"><span data-stu-id="815a3-116">Unique number identifying this A/V Conferencing Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="815a3-117"><strong>ИД</strong></span><span class="sxs-lookup"><span data-stu-id="815a3-117"><strong>CorrelationID</strong></span></span></p></td>
<td><p><span data-ttu-id="815a3-118">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="815a3-118">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="815a3-119">Уникальные</span><span class="sxs-lookup"><span data-stu-id="815a3-119">Unique</span></span></p></td>
<td><p><span data-ttu-id="815a3-120">Коррелированные сеансы будут иметь одинаковый идентификатор корреляции.</span><span class="sxs-lookup"><span data-stu-id="815a3-120">Sessions that are correlated will have the same correlation ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="815a3-121"><strong>некступдатетс</strong></span><span class="sxs-lookup"><span data-stu-id="815a3-121"><strong>NextUpdateTS</strong></span></span></p></td>
<td><p><span data-ttu-id="815a3-122">datetime</span><span class="sxs-lookup"><span data-stu-id="815a3-122">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="815a3-123">Только для внутреннего использования.</span><span class="sxs-lookup"><span data-stu-id="815a3-123">For internal use only.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

