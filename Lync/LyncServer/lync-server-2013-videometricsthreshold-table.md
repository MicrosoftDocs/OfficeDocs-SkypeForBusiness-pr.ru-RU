---
title: 'Lync Server 2013: таблица Видеометрикссрешолд'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: VideoMetricsThreshold table
ms:assetid: 2e2f4711-35ba-48c6-b15b-5aba61c4eb75
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204778(v=OCS.15)
ms:contentKeyID: 48183736
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7c15910f6478f3df12bf906f04aee82c89a822de
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849176"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="videometricsthreshold-table-in-lync-server-2013"></a><span data-ttu-id="a19b3-102">Таблица Видеометрикссрешолд в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a19b3-102">VideoMetricsThreshold table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a19b3-103">_**Тема последнего изменения:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="a19b3-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="a19b3-104">Таблица Видеометрикссрешолд имеет оптимальные и приемлемые значения для показателей качества взаимодействия, используемых с видеозвонками.</span><span class="sxs-lookup"><span data-stu-id="a19b3-104">The VideoMetricsThreshold table contains optimal and acceptable values for the Quality of Experience metrics used with video calls.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a19b3-105"><strong>Столбец</strong></span><span class="sxs-lookup"><span data-stu-id="a19b3-105"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="a19b3-106"><strong>Тип данных</strong></span><span class="sxs-lookup"><span data-stu-id="a19b3-106"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="a19b3-107"><strong>Ключ/индекс</strong></span><span class="sxs-lookup"><span data-stu-id="a19b3-107"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="a19b3-108"><strong>Сведения</strong></span><span class="sxs-lookup"><span data-stu-id="a19b3-108"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a19b3-109"><strong>CallType</strong></span><span class="sxs-lookup"><span data-stu-id="a19b3-109"><strong>CallType</strong></span></span></p></td>
<td><p><span data-ttu-id="a19b3-110">целое</span><span class="sxs-lookup"><span data-stu-id="a19b3-110">int</span></span></p></td>
<td><p><span data-ttu-id="a19b3-111">Primary</span><span class="sxs-lookup"><span data-stu-id="a19b3-111">Primary</span></span></p></td>
<td><p><span data-ttu-id="a19b3-112">Тип размещенного звонка.</span><span class="sxs-lookup"><span data-stu-id="a19b3-112">Type of call that was placed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a19b3-113"><strong>Видеопостфекплроптимал</strong></span><span class="sxs-lookup"><span data-stu-id="a19b3-113"><strong>VideoPostFECPLROptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="a19b3-114">десятичное число (5; 2)</span><span class="sxs-lookup"><span data-stu-id="a19b3-114">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a19b3-115">Значение по умолчанию — 0,05.</span><span class="sxs-lookup"><span data-stu-id="a19b3-115">The default value is 0.05.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a19b3-116"><strong>Видеопостфекплракцептабле</strong></span><span class="sxs-lookup"><span data-stu-id="a19b3-116"><strong>VideoPostFECPLRAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="a19b3-117">десятичное число (5; 2)</span><span class="sxs-lookup"><span data-stu-id="a19b3-117">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a19b3-118">Значение по умолчанию — 0,10.</span><span class="sxs-lookup"><span data-stu-id="a19b3-118">The default value is 0.10.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a19b3-119"><strong>Видеолокалфрамелостперцентажеаверажеоптимал</strong></span><span class="sxs-lookup"><span data-stu-id="a19b3-119"><strong>VideoLocalFrameLostPercentageAverageOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="a19b3-120">десятичное число (5; 2)</span><span class="sxs-lookup"><span data-stu-id="a19b3-120">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a19b3-121">Значение по умолчанию — 5,0.</span><span class="sxs-lookup"><span data-stu-id="a19b3-121">The default value is 5.0.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a19b3-122"><strong>Видеолокалфрамелостперцентажеаверажеакцептабле</strong></span><span class="sxs-lookup"><span data-stu-id="a19b3-122"><strong>VideoLocalFrameLostPercentageAverageAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="a19b3-123">десятичное число (5; 2)</span><span class="sxs-lookup"><span data-stu-id="a19b3-123">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a19b3-124">Значение по умолчанию — 10,0.</span><span class="sxs-lookup"><span data-stu-id="a19b3-124">The default value is 10.0.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a19b3-125"><strong>Реквфрамератеаверажеоптимал</strong></span><span class="sxs-lookup"><span data-stu-id="a19b3-125"><strong>RecvFrameRateAverageOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="a19b3-126">десятичное число (9; 4)</span><span class="sxs-lookup"><span data-stu-id="a19b3-126">decimal(9,4)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a19b3-127">Значение по умолчанию — 12,0000.</span><span class="sxs-lookup"><span data-stu-id="a19b3-127">The default value is 12.0000.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a19b3-128"><strong>Реквфрамератеаверажеакцептабле</strong></span><span class="sxs-lookup"><span data-stu-id="a19b3-128"><strong>RecvFramerateAverageAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="a19b3-129">десятичное число (9; 4)</span><span class="sxs-lookup"><span data-stu-id="a19b3-129">decimal(9,4)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a19b3-130">Значение по умолчанию — 7,0000.</span><span class="sxs-lookup"><span data-stu-id="a19b3-130">The default value is 7.0000.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a19b3-131"><strong>Ловфрамератекаллперцентоптимал</strong></span><span class="sxs-lookup"><span data-stu-id="a19b3-131"><strong>LowFrameRateCallPercentOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="a19b3-132">десятичное число (5; 2)</span><span class="sxs-lookup"><span data-stu-id="a19b3-132">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a19b3-133">Значение по умолчанию — 5,0.</span><span class="sxs-lookup"><span data-stu-id="a19b3-133">The default value is 5.0.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a19b3-134"><strong>Ловфрамератекаллперцентакцептабле</strong></span><span class="sxs-lookup"><span data-stu-id="a19b3-134"><strong>LowFrameRateCallPercentAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="a19b3-135">десятичное число (5; 2)</span><span class="sxs-lookup"><span data-stu-id="a19b3-135">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a19b3-136">Значение по умолчанию — 10.0/</span><span class="sxs-lookup"><span data-stu-id="a19b3-136">The default value is 10.0/</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a19b3-137"><strong>Ловресолутионкаллперцентоптимал</strong></span><span class="sxs-lookup"><span data-stu-id="a19b3-137"><strong>LowResolutionCallPercentOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="a19b3-138">десятичное число (5; 2)</span><span class="sxs-lookup"><span data-stu-id="a19b3-138">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a19b3-139">Значение по умолчанию — 5,0.</span><span class="sxs-lookup"><span data-stu-id="a19b3-139">The default value is 5.0.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a19b3-140"><strong>Ловресолутионкаллперцентакцептабле</strong></span><span class="sxs-lookup"><span data-stu-id="a19b3-140"><strong>LowResolutionCallPercentAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="a19b3-141">десятичное число (5; 2)</span><span class="sxs-lookup"><span data-stu-id="a19b3-141">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a19b3-142">Значение по умолчанию — 10,0.</span><span class="sxs-lookup"><span data-stu-id="a19b3-142">The default value is 10.0.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a19b3-143"><strong>Видеопаккетлоссратеоптимал</strong></span><span class="sxs-lookup"><span data-stu-id="a19b3-143"><strong>VideoPacketLossRateOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="a19b3-144">Фоат</span><span class="sxs-lookup"><span data-stu-id="a19b3-144">foat</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a19b3-145">Значение по умолчанию — 0,05.</span><span class="sxs-lookup"><span data-stu-id="a19b3-145">The default value is 0.05.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a19b3-146"><strong>Видеопаккетлоссратеакцептабле</strong></span><span class="sxs-lookup"><span data-stu-id="a19b3-146"><strong>VideoPacketLossRateAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="a19b3-147">число с плавающей точкой</span><span class="sxs-lookup"><span data-stu-id="a19b3-147">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a19b3-148">Значение по умолчанию — 0,10.</span><span class="sxs-lookup"><span data-stu-id="a19b3-148">The default value is 0.10.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a19b3-149"><strong>Видеофрамератеавгоптимал</strong></span><span class="sxs-lookup"><span data-stu-id="a19b3-149"><strong>VideoFrameRateAvgOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="a19b3-150">число с плавающей точкой</span><span class="sxs-lookup"><span data-stu-id="a19b3-150">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a19b3-151">Значением по умолчанию является 12.</span><span class="sxs-lookup"><span data-stu-id="a19b3-151">The default value is 12.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a19b3-152"><strong>Видеофрамератеавгакцептабле</strong></span><span class="sxs-lookup"><span data-stu-id="a19b3-152"><strong>VideoFrameRateAvgAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="a19b3-153">число с плавающей точкой</span><span class="sxs-lookup"><span data-stu-id="a19b3-153">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a19b3-154">Значением по умолчанию является 7.</span><span class="sxs-lookup"><span data-stu-id="a19b3-154">The default value is 7.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a19b3-155"><strong>Динамиккапабилитиперцентоптимал</strong></span><span class="sxs-lookup"><span data-stu-id="a19b3-155"><strong>DynamicCapabilityPercentOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="a19b3-156">десятичное число (5; 2)</span><span class="sxs-lookup"><span data-stu-id="a19b3-156">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a19b3-157">Значение по умолчанию — 5,00.</span><span class="sxs-lookup"><span data-stu-id="a19b3-157">The default value is 5.00.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a19b3-158"><strong>Динамиккапабилитиперцентакцептабле</strong></span><span class="sxs-lookup"><span data-stu-id="a19b3-158"><strong>DynamicCapabilityPercentAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="a19b3-159">десятичное число (5; 2)</span><span class="sxs-lookup"><span data-stu-id="a19b3-159">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a19b3-160">Значение по умолчанию — 10,00.</span><span class="sxs-lookup"><span data-stu-id="a19b3-160">The default value is 10.00.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

