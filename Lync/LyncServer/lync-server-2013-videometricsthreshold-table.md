---
title: 'Lync Server 2013: таблица таблица videometricsthreshold'
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
ms.openlocfilehash: 1a40e32b9c9730e37a339286ec152ed4ee0270b9
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42136907"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="videometricsthreshold-table-in-lync-server-2013"></a><span data-ttu-id="40ec2-102">Таблица Таблица videometricsthreshold в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="40ec2-102">VideoMetricsThreshold table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="40ec2-103">_**Последнее изменение темы:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="40ec2-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="40ec2-104">Таблица VideoMetricsThreshold содержит оптимальные и допустимые значения метрик качества взаимодействия, используемых для видеозвонков.</span><span class="sxs-lookup"><span data-stu-id="40ec2-104">The VideoMetricsThreshold table contains optimal and acceptable values for the Quality of Experience metrics used with video calls.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="40ec2-105"><strong>Column</strong></span><span class="sxs-lookup"><span data-stu-id="40ec2-105"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="40ec2-106"><strong>Тип данных</strong></span><span class="sxs-lookup"><span data-stu-id="40ec2-106"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="40ec2-107"><strong>Ключ или индекс</strong></span><span class="sxs-lookup"><span data-stu-id="40ec2-107"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="40ec2-108"><strong>Details</strong></span><span class="sxs-lookup"><span data-stu-id="40ec2-108"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="40ec2-109"><strong>CallType</strong></span><span class="sxs-lookup"><span data-stu-id="40ec2-109"><strong>CallType</strong></span></span></p></td>
<td><p><span data-ttu-id="40ec2-110">int</span><span class="sxs-lookup"><span data-stu-id="40ec2-110">int</span></span></p></td>
<td><p><span data-ttu-id="40ec2-111">Primary</span><span class="sxs-lookup"><span data-stu-id="40ec2-111">Primary</span></span></p></td>
<td><p><span data-ttu-id="40ec2-112">Тип размещенного вызова.</span><span class="sxs-lookup"><span data-stu-id="40ec2-112">Type of call that was placed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="40ec2-113"><strong>видеопостфекплроптимал</strong></span><span class="sxs-lookup"><span data-stu-id="40ec2-113"><strong>VideoPostFECPLROptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="40ec2-114">десятичное число (5, 2)</span><span class="sxs-lookup"><span data-stu-id="40ec2-114">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="40ec2-115">Значение по умолчанию — 0,05.</span><span class="sxs-lookup"><span data-stu-id="40ec2-115">The default value is 0.05.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="40ec2-116"><strong>видеопостфекплракцептабле</strong></span><span class="sxs-lookup"><span data-stu-id="40ec2-116"><strong>VideoPostFECPLRAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="40ec2-117">десятичное число (5, 2)</span><span class="sxs-lookup"><span data-stu-id="40ec2-117">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="40ec2-118">Значение по умолчанию — 0,10.</span><span class="sxs-lookup"><span data-stu-id="40ec2-118">The default value is 0.10.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="40ec2-119"><strong>видеолокалфрамелостперцентажеаверажеоптимал</strong></span><span class="sxs-lookup"><span data-stu-id="40ec2-119"><strong>VideoLocalFrameLostPercentageAverageOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="40ec2-120">десятичное число (5, 2)</span><span class="sxs-lookup"><span data-stu-id="40ec2-120">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="40ec2-121">Значение по умолчанию — 5,0.</span><span class="sxs-lookup"><span data-stu-id="40ec2-121">The default value is 5.0.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="40ec2-122"><strong>видеолокалфрамелостперцентажеаверажеакцептабле</strong></span><span class="sxs-lookup"><span data-stu-id="40ec2-122"><strong>VideoLocalFrameLostPercentageAverageAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="40ec2-123">десятичное число (5, 2)</span><span class="sxs-lookup"><span data-stu-id="40ec2-123">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="40ec2-124">Значение по умолчанию — 10,0.</span><span class="sxs-lookup"><span data-stu-id="40ec2-124">The default value is 10.0.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="40ec2-125"><strong>реквфрамератеаверажеоптимал</strong></span><span class="sxs-lookup"><span data-stu-id="40ec2-125"><strong>RecvFrameRateAverageOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="40ec2-126">десятичное число (9, 4)</span><span class="sxs-lookup"><span data-stu-id="40ec2-126">decimal(9,4)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="40ec2-127">Значение по умолчанию — 12,0000.</span><span class="sxs-lookup"><span data-stu-id="40ec2-127">The default value is 12.0000.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="40ec2-128"><strong>реквфрамератеаверажеакцептабле</strong></span><span class="sxs-lookup"><span data-stu-id="40ec2-128"><strong>RecvFramerateAverageAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="40ec2-129">десятичное число (9, 4)</span><span class="sxs-lookup"><span data-stu-id="40ec2-129">decimal(9,4)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="40ec2-130">Значение по умолчанию — 7,0000.</span><span class="sxs-lookup"><span data-stu-id="40ec2-130">The default value is 7.0000.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="40ec2-131"><strong>ловфрамератекаллперцентоптимал</strong></span><span class="sxs-lookup"><span data-stu-id="40ec2-131"><strong>LowFrameRateCallPercentOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="40ec2-132">десятичное число (5, 2)</span><span class="sxs-lookup"><span data-stu-id="40ec2-132">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="40ec2-133">Значение по умолчанию — 5,0.</span><span class="sxs-lookup"><span data-stu-id="40ec2-133">The default value is 5.0.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="40ec2-134"><strong>ловфрамератекаллперцентакцептабле</strong></span><span class="sxs-lookup"><span data-stu-id="40ec2-134"><strong>LowFrameRateCallPercentAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="40ec2-135">десятичное число (5, 2)</span><span class="sxs-lookup"><span data-stu-id="40ec2-135">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="40ec2-136">Значение по умолчанию — 10,0.</span><span class="sxs-lookup"><span data-stu-id="40ec2-136">The default value is 10.0/</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="40ec2-137"><strong>ловресолутионкаллперцентоптимал</strong></span><span class="sxs-lookup"><span data-stu-id="40ec2-137"><strong>LowResolutionCallPercentOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="40ec2-138">десятичное число (5, 2)</span><span class="sxs-lookup"><span data-stu-id="40ec2-138">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="40ec2-139">Значение по умолчанию — 5,0.</span><span class="sxs-lookup"><span data-stu-id="40ec2-139">The default value is 5.0.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="40ec2-140"><strong>ловресолутионкаллперцентакцептабле</strong></span><span class="sxs-lookup"><span data-stu-id="40ec2-140"><strong>LowResolutionCallPercentAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="40ec2-141">десятичное число (5, 2)</span><span class="sxs-lookup"><span data-stu-id="40ec2-141">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="40ec2-142">Значение по умолчанию — 10,0.</span><span class="sxs-lookup"><span data-stu-id="40ec2-142">The default value is 10.0.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="40ec2-143"><strong>видеопаккетлоссратеоптимал</strong></span><span class="sxs-lookup"><span data-stu-id="40ec2-143"><strong>VideoPacketLossRateOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="40ec2-144">фоат</span><span class="sxs-lookup"><span data-stu-id="40ec2-144">foat</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="40ec2-145">Значение по умолчанию — 0,05.</span><span class="sxs-lookup"><span data-stu-id="40ec2-145">The default value is 0.05.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="40ec2-146"><strong>видеопаккетлоссратеакцептабле</strong></span><span class="sxs-lookup"><span data-stu-id="40ec2-146"><strong>VideoPacketLossRateAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="40ec2-147">с плавающей запятой</span><span class="sxs-lookup"><span data-stu-id="40ec2-147">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="40ec2-148">Значение по умолчанию — 0,10.</span><span class="sxs-lookup"><span data-stu-id="40ec2-148">The default value is 0.10.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="40ec2-149"><strong>видеофрамератеавгоптимал</strong></span><span class="sxs-lookup"><span data-stu-id="40ec2-149"><strong>VideoFrameRateAvgOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="40ec2-150">с плавающей запятой</span><span class="sxs-lookup"><span data-stu-id="40ec2-150">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="40ec2-151">Значение по умолчанию — 12.</span><span class="sxs-lookup"><span data-stu-id="40ec2-151">The default value is 12.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="40ec2-152"><strong>видеофрамератеавгакцептабле</strong></span><span class="sxs-lookup"><span data-stu-id="40ec2-152"><strong>VideoFrameRateAvgAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="40ec2-153">с плавающей запятой</span><span class="sxs-lookup"><span data-stu-id="40ec2-153">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="40ec2-154">Значение по умолчанию — 7.</span><span class="sxs-lookup"><span data-stu-id="40ec2-154">The default value is 7.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="40ec2-155"><strong>динамиккапабилитиперцентоптимал</strong></span><span class="sxs-lookup"><span data-stu-id="40ec2-155"><strong>DynamicCapabilityPercentOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="40ec2-156">десятичное число (5, 2)</span><span class="sxs-lookup"><span data-stu-id="40ec2-156">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="40ec2-157">Значение по умолчанию — 5,00.</span><span class="sxs-lookup"><span data-stu-id="40ec2-157">The default value is 5.00.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="40ec2-158"><strong>динамиккапабилитиперцентакцептабле</strong></span><span class="sxs-lookup"><span data-stu-id="40ec2-158"><strong>DynamicCapabilityPercentAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="40ec2-159">десятичное число (5, 2)</span><span class="sxs-lookup"><span data-stu-id="40ec2-159">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="40ec2-160">Значение по умолчанию — 10,00.</span><span class="sxs-lookup"><span data-stu-id="40ec2-160">The default value is 10.00.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

