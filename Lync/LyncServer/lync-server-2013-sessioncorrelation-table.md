---
title: 'Lync Server 2013: таблица таблица sessioncorrelation'
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
ms.openlocfilehash: 4be49e052dc7ffd431e980d1a3f969bfffdfce8c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48510106"
---
# <a name="sessioncorrelation-table-in-lync-server-2013"></a><span data-ttu-id="d5d3c-102">Таблица Таблица sessioncorrelation в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d5d3c-102">SessionCorrelation table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d5d3c-103">_**Последнее изменение темы:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="d5d3c-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="d5d3c-104">Таблица Таблица sessioncorrelation является вспомогательной таблицей.</span><span class="sxs-lookup"><span data-stu-id="d5d3c-104">The SessionCorrelation table is a supporting table.</span></span> <span data-ttu-id="d5d3c-105">Каждая запись представляет один элемент CorrelationID, который используется для корреляции нескольких сеансов.</span><span class="sxs-lookup"><span data-stu-id="d5d3c-105">Each record represents one CorrelationID which is used to correlate multiple sessions.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d5d3c-106"><strong>Column</strong></span><span class="sxs-lookup"><span data-stu-id="d5d3c-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="d5d3c-107"><strong>Тип данных</strong></span><span class="sxs-lookup"><span data-stu-id="d5d3c-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="d5d3c-108"><strong>Ключ или индекс</strong></span><span class="sxs-lookup"><span data-stu-id="d5d3c-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="d5d3c-109"><strong>Details</strong></span><span class="sxs-lookup"><span data-stu-id="d5d3c-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d5d3c-110"><strong>Контрольная сумма</strong></span><span class="sxs-lookup"><span data-stu-id="d5d3c-110"><strong>Checksum</strong></span></span></p></td>
<td><p><span data-ttu-id="d5d3c-111">int</span><span class="sxs-lookup"><span data-stu-id="d5d3c-111">int</span></span></p></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d5d3c-112"><strong>коррелатионкэй</strong></span><span class="sxs-lookup"><span data-stu-id="d5d3c-112"><strong>CorrelationKey</strong></span></span></p></td>
<td><p><span data-ttu-id="d5d3c-113">int</span><span class="sxs-lookup"><span data-stu-id="d5d3c-113">int</span></span></p></td>
<td><p><span data-ttu-id="d5d3c-114">Primary</span><span class="sxs-lookup"><span data-stu-id="d5d3c-114">Primary</span></span></p></td>
<td><p><span data-ttu-id="d5d3c-115">Уникальный номер, идентифицирующий этот сервер аудио-и видеоконференций.</span><span class="sxs-lookup"><span data-stu-id="d5d3c-115">Unique number identifying this A/V Conferencing Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d5d3c-116"><strong>ИД</strong></span><span class="sxs-lookup"><span data-stu-id="d5d3c-116"><strong>CorrelationID</strong></span></span></p></td>
<td><p><span data-ttu-id="d5d3c-117">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="d5d3c-117">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="d5d3c-118">Уникальные</span><span class="sxs-lookup"><span data-stu-id="d5d3c-118">Unique</span></span></p></td>
<td><p><span data-ttu-id="d5d3c-119">Коррелированные сеансы будут иметь одинаковый идентификатор корреляции.</span><span class="sxs-lookup"><span data-stu-id="d5d3c-119">Sessions that are correlated will have the same correlation ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d5d3c-120"><strong>некступдатетс</strong></span><span class="sxs-lookup"><span data-stu-id="d5d3c-120"><strong>NextUpdateTS</strong></span></span></p></td>
<td><p><span data-ttu-id="d5d3c-121">datetime</span><span class="sxs-lookup"><span data-stu-id="d5d3c-121">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="d5d3c-122">Только для внутреннего использования.</span><span class="sxs-lookup"><span data-stu-id="d5d3c-122">For internal use only.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

