---
title: 'Lync Server 2013: таблица таблица videometricsthreshold'
description: 'Lync Server 2013: таблица таблица videometricsthreshold.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: VideoMetricsThreshold table
ms:assetid: 2e2f4711-35ba-48c6-b15b-5aba61c4eb75
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204778(v=OCS.15)
ms:contentKeyID: 48183736
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 93cdd6fb4c3c54ac1470499490f36fee87ba283d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48568005"
---
# <a name="videometricsthreshold-table-in-lync-server-2013"></a><span data-ttu-id="558d0-103">Таблица Таблица videometricsthreshold в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="558d0-103">VideoMetricsThreshold table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="558d0-104">_**Последнее изменение темы:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="558d0-104">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="558d0-105">Таблица VideoMetricsThreshold содержит оптимальные и допустимые значения метрик качества взаимодействия, используемых для видеозвонков.</span><span class="sxs-lookup"><span data-stu-id="558d0-105">The VideoMetricsThreshold table contains optimal and acceptable values for the Quality of Experience metrics used with video calls.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="558d0-106"><strong>Column</strong></span><span class="sxs-lookup"><span data-stu-id="558d0-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="558d0-107"><strong>Тип данных</strong></span><span class="sxs-lookup"><span data-stu-id="558d0-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="558d0-108"><strong>Ключ или индекс</strong></span><span class="sxs-lookup"><span data-stu-id="558d0-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="558d0-109"><strong>Details</strong></span><span class="sxs-lookup"><span data-stu-id="558d0-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="558d0-110"><strong>CallType</strong></span><span class="sxs-lookup"><span data-stu-id="558d0-110"><strong>CallType</strong></span></span></p></td>
<td><p><span data-ttu-id="558d0-111">int</span><span class="sxs-lookup"><span data-stu-id="558d0-111">int</span></span></p></td>
<td><p><span data-ttu-id="558d0-112">Primary</span><span class="sxs-lookup"><span data-stu-id="558d0-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="558d0-113">Тип размещенного вызова.</span><span class="sxs-lookup"><span data-stu-id="558d0-113">Type of call that was placed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="558d0-114"><strong>видеопостфекплроптимал</strong></span><span class="sxs-lookup"><span data-stu-id="558d0-114"><strong>VideoPostFECPLROptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="558d0-115">десятичное число (5, 2)</span><span class="sxs-lookup"><span data-stu-id="558d0-115">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="558d0-116">Значение по умолчанию — 0,05.</span><span class="sxs-lookup"><span data-stu-id="558d0-116">The default value is 0.05.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="558d0-117"><strong>видеопостфекплракцептабле</strong></span><span class="sxs-lookup"><span data-stu-id="558d0-117"><strong>VideoPostFECPLRAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="558d0-118">десятичное число (5, 2)</span><span class="sxs-lookup"><span data-stu-id="558d0-118">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="558d0-119">Значение по умолчанию — 0,10.</span><span class="sxs-lookup"><span data-stu-id="558d0-119">The default value is 0.10.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="558d0-120"><strong>видеолокалфрамелостперцентажеаверажеоптимал</strong></span><span class="sxs-lookup"><span data-stu-id="558d0-120"><strong>VideoLocalFrameLostPercentageAverageOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="558d0-121">десятичное число (5, 2)</span><span class="sxs-lookup"><span data-stu-id="558d0-121">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="558d0-122">Значение по умолчанию — 5,0.</span><span class="sxs-lookup"><span data-stu-id="558d0-122">The default value is 5.0.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="558d0-123"><strong>видеолокалфрамелостперцентажеаверажеакцептабле</strong></span><span class="sxs-lookup"><span data-stu-id="558d0-123"><strong>VideoLocalFrameLostPercentageAverageAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="558d0-124">десятичное число (5, 2)</span><span class="sxs-lookup"><span data-stu-id="558d0-124">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="558d0-125">Значение по умолчанию — 10,0.</span><span class="sxs-lookup"><span data-stu-id="558d0-125">The default value is 10.0.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="558d0-126"><strong>реквфрамератеаверажеоптимал</strong></span><span class="sxs-lookup"><span data-stu-id="558d0-126"><strong>RecvFrameRateAverageOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="558d0-127">десятичное число (9, 4)</span><span class="sxs-lookup"><span data-stu-id="558d0-127">decimal(9,4)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="558d0-128">Значение по умолчанию — 12,0000.</span><span class="sxs-lookup"><span data-stu-id="558d0-128">The default value is 12.0000.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="558d0-129"><strong>реквфрамератеаверажеакцептабле</strong></span><span class="sxs-lookup"><span data-stu-id="558d0-129"><strong>RecvFramerateAverageAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="558d0-130">десятичное число (9, 4)</span><span class="sxs-lookup"><span data-stu-id="558d0-130">decimal(9,4)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="558d0-131">Значение по умолчанию — 7,0000.</span><span class="sxs-lookup"><span data-stu-id="558d0-131">The default value is 7.0000.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="558d0-132"><strong>ловфрамератекаллперцентоптимал</strong></span><span class="sxs-lookup"><span data-stu-id="558d0-132"><strong>LowFrameRateCallPercentOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="558d0-133">десятичное число (5, 2)</span><span class="sxs-lookup"><span data-stu-id="558d0-133">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="558d0-134">Значение по умолчанию — 5,0.</span><span class="sxs-lookup"><span data-stu-id="558d0-134">The default value is 5.0.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="558d0-135"><strong>ловфрамератекаллперцентакцептабле</strong></span><span class="sxs-lookup"><span data-stu-id="558d0-135"><strong>LowFrameRateCallPercentAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="558d0-136">десятичное число (5, 2)</span><span class="sxs-lookup"><span data-stu-id="558d0-136">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="558d0-137">Значение по умолчанию — 10,0.</span><span class="sxs-lookup"><span data-stu-id="558d0-137">The default value is 10.0/</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="558d0-138"><strong>ловресолутионкаллперцентоптимал</strong></span><span class="sxs-lookup"><span data-stu-id="558d0-138"><strong>LowResolutionCallPercentOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="558d0-139">десятичное число (5, 2)</span><span class="sxs-lookup"><span data-stu-id="558d0-139">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="558d0-140">Значение по умолчанию — 5,0.</span><span class="sxs-lookup"><span data-stu-id="558d0-140">The default value is 5.0.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="558d0-141"><strong>ловресолутионкаллперцентакцептабле</strong></span><span class="sxs-lookup"><span data-stu-id="558d0-141"><strong>LowResolutionCallPercentAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="558d0-142">десятичное число (5, 2)</span><span class="sxs-lookup"><span data-stu-id="558d0-142">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="558d0-143">Значение по умолчанию — 10,0.</span><span class="sxs-lookup"><span data-stu-id="558d0-143">The default value is 10.0.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="558d0-144"><strong>видеопаккетлоссратеоптимал</strong></span><span class="sxs-lookup"><span data-stu-id="558d0-144"><strong>VideoPacketLossRateOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="558d0-145">фоат</span><span class="sxs-lookup"><span data-stu-id="558d0-145">foat</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="558d0-146">Значение по умолчанию — 0,05.</span><span class="sxs-lookup"><span data-stu-id="558d0-146">The default value is 0.05.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="558d0-147"><strong>видеопаккетлоссратеакцептабле</strong></span><span class="sxs-lookup"><span data-stu-id="558d0-147"><strong>VideoPacketLossRateAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="558d0-148">float</span><span class="sxs-lookup"><span data-stu-id="558d0-148">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="558d0-149">Значение по умолчанию — 0,10.</span><span class="sxs-lookup"><span data-stu-id="558d0-149">The default value is 0.10.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="558d0-150"><strong>видеофрамератеавгоптимал</strong></span><span class="sxs-lookup"><span data-stu-id="558d0-150"><strong>VideoFrameRateAvgOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="558d0-151">float</span><span class="sxs-lookup"><span data-stu-id="558d0-151">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="558d0-152">Значение по умолчанию — 12.</span><span class="sxs-lookup"><span data-stu-id="558d0-152">The default value is 12.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="558d0-153"><strong>видеофрамератеавгакцептабле</strong></span><span class="sxs-lookup"><span data-stu-id="558d0-153"><strong>VideoFrameRateAvgAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="558d0-154">float</span><span class="sxs-lookup"><span data-stu-id="558d0-154">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="558d0-155">Значение по умолчанию — 7.</span><span class="sxs-lookup"><span data-stu-id="558d0-155">The default value is 7.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="558d0-156"><strong>динамиккапабилитиперцентоптимал</strong></span><span class="sxs-lookup"><span data-stu-id="558d0-156"><strong>DynamicCapabilityPercentOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="558d0-157">десятичное число (5, 2)</span><span class="sxs-lookup"><span data-stu-id="558d0-157">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="558d0-158">Значение по умолчанию — 5,00.</span><span class="sxs-lookup"><span data-stu-id="558d0-158">The default value is 5.00.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="558d0-159"><strong>динамиккапабилитиперцентакцептабле</strong></span><span class="sxs-lookup"><span data-stu-id="558d0-159"><strong>DynamicCapabilityPercentAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="558d0-160">десятичное число (5, 2)</span><span class="sxs-lookup"><span data-stu-id="558d0-160">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="558d0-161">Значение по умолчанию — 10,00.</span><span class="sxs-lookup"><span data-stu-id="558d0-161">The default value is 10.00.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

