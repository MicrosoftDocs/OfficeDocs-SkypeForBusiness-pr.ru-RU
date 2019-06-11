---
title: 'Lync Server 2013: таблица SessionCorrelation'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: SessionCorrelation table
ms:assetid: 041705e1-7290-464f-95f8-96256cfa2e3e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398091(v=OCS.15)
ms:contentKeyID: 48183267
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c588a58126fb83df08550a6300ca8db36cceb647
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34821952"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="sessioncorrelation-table-in-lync-server-2013"></a><span data-ttu-id="a005f-102">Таблица SessionCorrelation в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a005f-102">SessionCorrelation table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a005f-103">_**Тема последнего изменения:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="a005f-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="a005f-104">Таблица Сессионкоррелатион является вспомогательной таблицей.</span><span class="sxs-lookup"><span data-stu-id="a005f-104">The SessionCorrelation table is a supporting table.</span></span> <span data-ttu-id="a005f-105">Каждая запись представляет собой один элемент CorrelationID, который используется для корреляции нескольких сеансов.</span><span class="sxs-lookup"><span data-stu-id="a005f-105">Each record represents one CorrelationID which is used to correlate multiple sessions.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a005f-106"><strong>Столбец</strong></span><span class="sxs-lookup"><span data-stu-id="a005f-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="a005f-107"><strong>Тип данных</strong></span><span class="sxs-lookup"><span data-stu-id="a005f-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="a005f-108"><strong>Ключ/индекс</strong></span><span class="sxs-lookup"><span data-stu-id="a005f-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="a005f-109"><strong>Сведения</strong></span><span class="sxs-lookup"><span data-stu-id="a005f-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a005f-110"><strong>Счет</strong></span><span class="sxs-lookup"><span data-stu-id="a005f-110"><strong>Checksum</strong></span></span></p></td>
<td><p><span data-ttu-id="a005f-111">целое</span><span class="sxs-lookup"><span data-stu-id="a005f-111">int</span></span></p></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a005f-112"><strong>Коррелатионкэй</strong></span><span class="sxs-lookup"><span data-stu-id="a005f-112"><strong>CorrelationKey</strong></span></span></p></td>
<td><p><span data-ttu-id="a005f-113">целое</span><span class="sxs-lookup"><span data-stu-id="a005f-113">int</span></span></p></td>
<td><p><span data-ttu-id="a005f-114">Primary</span><span class="sxs-lookup"><span data-stu-id="a005f-114">Primary</span></span></p></td>
<td><p><span data-ttu-id="a005f-115">Уникальный номер, показывающий этот сервер конференц-связи A/V.</span><span class="sxs-lookup"><span data-stu-id="a005f-115">Unique number identifying this A/V Conferencing Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a005f-116"><strong>Корреляци</strong></span><span class="sxs-lookup"><span data-stu-id="a005f-116"><strong>CorrelationID</strong></span></span></p></td>
<td><p><span data-ttu-id="a005f-117">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="a005f-117">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="a005f-118">Повторя</span><span class="sxs-lookup"><span data-stu-id="a005f-118">Unique</span></span></p></td>
<td><p><span data-ttu-id="a005f-119">Коррелированные сеансы будут иметь одинаковый идентификатор корреляции.</span><span class="sxs-lookup"><span data-stu-id="a005f-119">Sessions that are correlated will have the same correlation ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a005f-120"><strong>Некступдатетс</strong></span><span class="sxs-lookup"><span data-stu-id="a005f-120"><strong>NextUpdateTS</strong></span></span></p></td>
<td><p><span data-ttu-id="a005f-121">datetime</span><span class="sxs-lookup"><span data-stu-id="a005f-121">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="a005f-122">Только для внутреннего использования.</span><span class="sxs-lookup"><span data-stu-id="a005f-122">For internal use only.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

