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
ms.openlocfilehash: a47e8d3bfcac06aed0ce76616208d0ead018ccbf
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42143885"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="sessioncorrelation-table-in-lync-server-2013"></a><span data-ttu-id="16e00-102">Таблица Таблица sessioncorrelation в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="16e00-102">SessionCorrelation table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="16e00-103">_**Последнее изменение темы:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="16e00-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="16e00-104">Таблица Таблица sessioncorrelation является вспомогательной таблицей.</span><span class="sxs-lookup"><span data-stu-id="16e00-104">The SessionCorrelation table is a supporting table.</span></span> <span data-ttu-id="16e00-105">Каждая запись представляет один элемент CorrelationID, который используется для корреляции нескольких сеансов.</span><span class="sxs-lookup"><span data-stu-id="16e00-105">Each record represents one CorrelationID which is used to correlate multiple sessions.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="16e00-106"><strong>Column</strong></span><span class="sxs-lookup"><span data-stu-id="16e00-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="16e00-107"><strong>Тип данных</strong></span><span class="sxs-lookup"><span data-stu-id="16e00-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="16e00-108"><strong>Ключ или индекс</strong></span><span class="sxs-lookup"><span data-stu-id="16e00-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="16e00-109"><strong>Details</strong></span><span class="sxs-lookup"><span data-stu-id="16e00-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="16e00-110"><strong>Контрольная сумма</strong></span><span class="sxs-lookup"><span data-stu-id="16e00-110"><strong>Checksum</strong></span></span></p></td>
<td><p><span data-ttu-id="16e00-111">int</span><span class="sxs-lookup"><span data-stu-id="16e00-111">int</span></span></p></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="16e00-112"><strong>коррелатионкэй</strong></span><span class="sxs-lookup"><span data-stu-id="16e00-112"><strong>CorrelationKey</strong></span></span></p></td>
<td><p><span data-ttu-id="16e00-113">int</span><span class="sxs-lookup"><span data-stu-id="16e00-113">int</span></span></p></td>
<td><p><span data-ttu-id="16e00-114">Primary</span><span class="sxs-lookup"><span data-stu-id="16e00-114">Primary</span></span></p></td>
<td><p><span data-ttu-id="16e00-115">Уникальный номер, идентифицирующий этот сервер аудио-и видеоконференций.</span><span class="sxs-lookup"><span data-stu-id="16e00-115">Unique number identifying this A/V Conferencing Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="16e00-116"><strong>ИД</strong></span><span class="sxs-lookup"><span data-stu-id="16e00-116"><strong>CorrelationID</strong></span></span></p></td>
<td><p><span data-ttu-id="16e00-117">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="16e00-117">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="16e00-118">Уникальные</span><span class="sxs-lookup"><span data-stu-id="16e00-118">Unique</span></span></p></td>
<td><p><span data-ttu-id="16e00-119">Коррелированные сеансы будут иметь одинаковый идентификатор корреляции.</span><span class="sxs-lookup"><span data-stu-id="16e00-119">Sessions that are correlated will have the same correlation ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="16e00-120"><strong>некступдатетс</strong></span><span class="sxs-lookup"><span data-stu-id="16e00-120"><strong>NextUpdateTS</strong></span></span></p></td>
<td><p><span data-ttu-id="16e00-121">datetime</span><span class="sxs-lookup"><span data-stu-id="16e00-121">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="16e00-122">Только для внутреннего использования.</span><span class="sxs-lookup"><span data-stu-id="16e00-122">For internal use only.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

