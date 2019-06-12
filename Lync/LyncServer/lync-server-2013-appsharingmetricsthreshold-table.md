---
title: 'Lync Server 2013: таблица Аппшарингметрикссрешолд'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: AppSharingMetricsThreshold table
ms:assetid: 782cfab9-01a6-4843-aea1-28f47b0b51f7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205018(v=OCS.15)
ms:contentKeyID: 48184556
ms.date: 12/09/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a0f8dc1dac3dc7a9ec362473221d36191dd7dd0f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849786"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="appsharingmetricsthreshold-table-in-lync-server-2013"></a><span data-ttu-id="a6f7a-102">Таблица Аппшарингметрикссрешолд в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a6f7a-102">AppSharingMetricsThreshold table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a6f7a-103">_**Тема последнего изменения:** 2015-12-08_</span><span class="sxs-lookup"><span data-stu-id="a6f7a-103">_**Topic Last Modified:** 2015-12-08_</span></span>

<span data-ttu-id="a6f7a-104">В таблице Аппшарингметрикссрешолд содержатся оптимальные и приемлемые значения для показателей качества взаимодействия, используемых совместно с приложением.</span><span class="sxs-lookup"><span data-stu-id="a6f7a-104">The AppSharingMetricsThreshold table contains optimal and acceptable values for the Quality of Experience metrics used with application sharing.</span></span> <span data-ttu-id="a6f7a-105">Эти пороговые значения используются, чтобы определить, следует ли классифицировать взаимодействие приложений как неудовлетворительные.</span><span class="sxs-lookup"><span data-stu-id="a6f7a-105">These thresholds are used to determine if the application sharing experience should be classified as poor.</span></span>

<span data-ttu-id="a6f7a-106">Эта таблица введена в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a6f7a-106">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a6f7a-107"><strong>Столбец</strong></span><span class="sxs-lookup"><span data-stu-id="a6f7a-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="a6f7a-108"><strong>Тип данных</strong></span><span class="sxs-lookup"><span data-stu-id="a6f7a-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="a6f7a-109"><strong>Ключ/индекс</strong></span><span class="sxs-lookup"><span data-stu-id="a6f7a-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="a6f7a-110"><strong>Сведения</strong></span><span class="sxs-lookup"><span data-stu-id="a6f7a-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a6f7a-111"><strong>CallType</strong></span><span class="sxs-lookup"><span data-stu-id="a6f7a-111"><strong>CallType</strong></span></span></p></td>
<td><p><span data-ttu-id="a6f7a-112">целое</span><span class="sxs-lookup"><span data-stu-id="a6f7a-112">int</span></span></p></td>
<td><p><span data-ttu-id="a6f7a-113">Primary</span><span class="sxs-lookup"><span data-stu-id="a6f7a-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="a6f7a-114">Тип размещенного звонка.</span><span class="sxs-lookup"><span data-stu-id="a6f7a-114">Type of call that was placed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a6f7a-115"><strong>Апплиедбандвидслимитоптимал</strong></span><span class="sxs-lookup"><span data-stu-id="a6f7a-115"><strong>AppliedBandwidthLimitOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="a6f7a-116">целое</span><span class="sxs-lookup"><span data-stu-id="a6f7a-116">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a6f7a-117">Оптимальное ограничение пропускной способности для совместного использования приложений.</span><span class="sxs-lookup"><span data-stu-id="a6f7a-117">Optimal bandwidth limitation for application sharing.</span></span> <span data-ttu-id="a6f7a-118">Значение по умолчанию — 1000000.</span><span class="sxs-lookup"><span data-stu-id="a6f7a-118">The default value is 1000000.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a6f7a-119"><strong>Апплиедбандвидслимитакцептабле</strong></span><span class="sxs-lookup"><span data-stu-id="a6f7a-119"><strong>AppliedBandwidthLimitAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="a6f7a-120">целое</span><span class="sxs-lookup"><span data-stu-id="a6f7a-120">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a6f7a-121">Допустимое ограничение пропускной способности для совместного использования приложений.</span><span class="sxs-lookup"><span data-stu-id="a6f7a-121">Acceptable bandwidth limitation for application sharing.</span></span> <span data-ttu-id="a6f7a-122">Значение по умолчанию — 500000.</span><span class="sxs-lookup"><span data-stu-id="a6f7a-122">The default value is 500000.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a6f7a-123"><strong>Споиледтилеперценттоталоптимал</strong></span><span class="sxs-lookup"><span data-stu-id="a6f7a-123"><strong>SpoiledTilePercentTotalOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="a6f7a-124">десятичное число (5; 2)</span><span class="sxs-lookup"><span data-stu-id="a6f7a-124">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a6f7a-125">Оптимальная процентная ставка для плиток "spoiled" для классификации качества общего использования приложения.</span><span class="sxs-lookup"><span data-stu-id="a6f7a-125">Optimal percentage rate for “spoiled” tiles for classifying an Application Sharing quality.</span></span> <span data-ttu-id="a6f7a-126">Это значение — процент содержимого от общего доступа, которое не было доступно для просмотра.</span><span class="sxs-lookup"><span data-stu-id="a6f7a-126">This value is the percentage of the content from the sharer that did not reach the viewer.</span></span> <span data-ttu-id="a6f7a-127">Содержимое может быть удалено (или spoiled), когда общий доступ отбрасывает плитки из источника графики, или АСМКУ плитки отбрасывают плитки от общего доступа, соответственно.</span><span class="sxs-lookup"><span data-stu-id="a6f7a-127">Content may be discarded (or spoiled) when the sharer discards tiles from the graphics source or the ASMCU tiles discards tiles from Sharer respectively.</span></span> <span data-ttu-id="a6f7a-128">Значение по умолчанию составляет 11 процентов.</span><span class="sxs-lookup"><span data-stu-id="a6f7a-128">The default value is 11 percent.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a6f7a-129"><strong>Споиледтилеперценттоталакцептабле</strong></span><span class="sxs-lookup"><span data-stu-id="a6f7a-129"><strong>SpoiledTilePercentTotalAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="a6f7a-130">десятичное число (5; 2)</span><span class="sxs-lookup"><span data-stu-id="a6f7a-130">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a6f7a-131">кцептабле процентная ставка для плиток "spoiled" для классификации качества общего использования приложения.</span><span class="sxs-lookup"><span data-stu-id="a6f7a-131">cceptable percentage rate for “spoiled” tiles for classifying an Application Sharing quality.</span></span> <span data-ttu-id="a6f7a-132">Это значение — процент содержимого от общего доступа, которое не было доступно для просмотра.</span><span class="sxs-lookup"><span data-stu-id="a6f7a-132">This value is the percentage of the content from the sharer that did not reach the viewer.</span></span> <span data-ttu-id="a6f7a-133">Содержимое может быть удалено (или spoiled), когда общий доступ отбрасывает плитки из источника графики, или АСМКУ плитки отбрасывают плитки от общего доступа, соответственно.</span><span class="sxs-lookup"><span data-stu-id="a6f7a-133">Content may be discarded (or spoiled) when the sharer discards tiles from the graphics source or the ASMCU tiles discards tiles from Sharer respectively.</span></span> <span data-ttu-id="a6f7a-134">Значение по умолчанию составляет 36%.</span><span class="sxs-lookup"><span data-stu-id="a6f7a-134">The default value is 36 percent.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a6f7a-135"><strong>Життеринтерарривалоптимал</strong></span><span class="sxs-lookup"><span data-stu-id="a6f7a-135"><strong>JitterInterArrivalOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="a6f7a-136">целое</span><span class="sxs-lookup"><span data-stu-id="a6f7a-136">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a6f7a-137">Этот столбец не используется в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a6f7a-137">This column is not used in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a6f7a-138"><strong>Життеринтерарривалакцептабле</strong></span><span class="sxs-lookup"><span data-stu-id="a6f7a-138"><strong>JitterInterArrivalAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="a6f7a-139">целое</span><span class="sxs-lookup"><span data-stu-id="a6f7a-139">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a6f7a-140">Этот столбец не используется в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a6f7a-140">This column is not used in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a6f7a-141"><strong>Релативеоневайбурстденситйоптимал</strong></span><span class="sxs-lookup"><span data-stu-id="a6f7a-141"><strong>RelativeOneWayBurstDensityOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="a6f7a-142">число с плавающей точкой</span><span class="sxs-lookup"><span data-stu-id="a6f7a-142">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a6f7a-143">Этот столбец не используется в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a6f7a-143">This column is not used in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a6f7a-144"><strong>Релативеоневайбурстденситякцептабле</strong></span><span class="sxs-lookup"><span data-stu-id="a6f7a-144"><strong>RelativeOneWayBurstDensityAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="a6f7a-145">число с плавающей точкой</span><span class="sxs-lookup"><span data-stu-id="a6f7a-145">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a6f7a-146">Этот столбец не используется в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a6f7a-146">This column is not used in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a6f7a-147"><strong>Рдптилепроцессинглатенцибурстденситйоптимал</strong></span><span class="sxs-lookup"><span data-stu-id="a6f7a-147"><strong>RDPTileProcessingLatencyBurstDensityOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="a6f7a-148">число с плавающей точкой</span><span class="sxs-lookup"><span data-stu-id="a6f7a-148">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a6f7a-149">Этот столбец не используется в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a6f7a-149">This column is not used in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a6f7a-150"><strong>Рдптилепроцессинглатенцибурстденситякцептабле</strong></span><span class="sxs-lookup"><span data-stu-id="a6f7a-150"><strong>RDPTileProcessingLatencyBurstDensityAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="a6f7a-151">число с плавающей точкой</span><span class="sxs-lookup"><span data-stu-id="a6f7a-151">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a6f7a-152">Этот столбец не используется в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a6f7a-152">This column is not used in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a6f7a-153"><strong>Релативеоневайаверажеоптимал</strong></span><span class="sxs-lookup"><span data-stu-id="a6f7a-153"><strong>RelativeOneWayAverageOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="a6f7a-154">число с плавающей точкой</span><span class="sxs-lookup"><span data-stu-id="a6f7a-154">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a6f7a-155">Оптимальное значение для относительной односторонней задержки между двумя конечными точками мультимедиа, задействованными в общем доступе к приложению.</span><span class="sxs-lookup"><span data-stu-id="a6f7a-155">Optimal value for the relative one-way delay between the two media endpoints involved in the application sharing.</span></span> <span data-ttu-id="a6f7a-156">Это мера односкачковой задержки.</span><span class="sxs-lookup"><span data-stu-id="a6f7a-156">This is a single-hop latency measure.</span></span> <span data-ttu-id="a6f7a-157">Значение по умолчанию — 1,0 секунд.</span><span class="sxs-lookup"><span data-stu-id="a6f7a-157">The default value is 1.0 seconds.</span></span></p>
<p><span data-ttu-id="a6f7a-158">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a6f7a-158">The column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a6f7a-159"><strong>Релативеоневайаверажеакцептабле</strong></span><span class="sxs-lookup"><span data-stu-id="a6f7a-159"><strong>RelativeOneWayAverageAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="a6f7a-160">число с плавающей точкой</span><span class="sxs-lookup"><span data-stu-id="a6f7a-160">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a6f7a-161">Оптимальное значение для относительной односторонней задержки между двумя конечными точками мультимедиа, задействованными в общем доступе к приложению.</span><span class="sxs-lookup"><span data-stu-id="a6f7a-161">Optimal value for the relative one-way delay between the two media endpoints involved in the application sharing.</span></span> <span data-ttu-id="a6f7a-162">Это мера односкачковой задержки.</span><span class="sxs-lookup"><span data-stu-id="a6f7a-162">This is a single-hop latency measure.</span></span> <span data-ttu-id="a6f7a-163">Значение по умолчанию — 1,75 секунд.</span><span class="sxs-lookup"><span data-stu-id="a6f7a-163">The default value is 1.75 seconds.</span></span></p>
<p><span data-ttu-id="a6f7a-164">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a6f7a-164">The column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a6f7a-165"><strong>Рдптилепроцессинглатенциаверажеоптимал</strong></span><span class="sxs-lookup"><span data-stu-id="a6f7a-165"><strong>RDPTileProcessingLatencyAverageOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="a6f7a-166">число с плавающей точкой</span><span class="sxs-lookup"><span data-stu-id="a6f7a-166">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a6f7a-167">Оптимальное значение средней задержки обработки плитки RDP на сервере конференций в течение сеанса просмотра.</span><span class="sxs-lookup"><span data-stu-id="a6f7a-167">Optimal value of the average RDP tile processing latency in the AS Conferencing Server over the duration of the viewing session.</span></span> <span data-ttu-id="a6f7a-168">Задержка — это разница во времени между моментом, когда начальный кадр кодируется на сервере (в зависимости от сценария, или MCU, а также с помощью того же начального кадра декодируется в средстве просмотра).</span><span class="sxs-lookup"><span data-stu-id="a6f7a-168">Latency is the time difference between when the Start Frame is encoded on the server (sharer or MCU depending on the scenario) and the same Start Frame is decoded on the viewer.</span></span></p>
<p><span data-ttu-id="a6f7a-169">Высокое среднее значение отражает более длительную задержку при просмотре.</span><span class="sxs-lookup"><span data-stu-id="a6f7a-169">A high average reflects a longer delay in the viewing experience.</span></span> <span data-ttu-id="a6f7a-170">На перегруженном сервере конференц-связи могут происходить в среднем более длительные задержки.</span><span class="sxs-lookup"><span data-stu-id="a6f7a-170">An overloaded conferencing server may experience higher average delays.</span></span> <span data-ttu-id="a6f7a-171">Значением по умолчанию является 200ms.</span><span class="sxs-lookup"><span data-stu-id="a6f7a-171">The default value is 200ms.</span></span></p>
<p><span data-ttu-id="a6f7a-172">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a6f7a-172">The column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a6f7a-173"><strong>Рдптилепроцессинглатенциаверажеакцептабле</strong></span><span class="sxs-lookup"><span data-stu-id="a6f7a-173"><strong>RDPTileProcessingLatencyAverageAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="a6f7a-174">число с плавающей точкой</span><span class="sxs-lookup"><span data-stu-id="a6f7a-174">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a6f7a-175">Допустимое значение средней задержки обработки плитки RDP на сервере конференций в течение сеанса просмотра.</span><span class="sxs-lookup"><span data-stu-id="a6f7a-175">Acceptable value of the average RDP tile processing latency in the AS Conferencing Server over the duration of the viewing session.</span></span> <span data-ttu-id="a6f7a-176">Задержка — это разница во времени между моментом, когда начальный кадр кодируется на сервере (в зависимости от сценария, или MCU, а также с помощью того же начального кадра декодируется в средстве просмотра).</span><span class="sxs-lookup"><span data-stu-id="a6f7a-176">Latency is the time difference between when the Start Frame is encoded on the server (sharer or MCU depending on the scenario) and the same Start Frame is decoded on the viewer.</span></span></p>
<p><span data-ttu-id="a6f7a-177">Высокое среднее значение отражает более длительную задержку при просмотре.</span><span class="sxs-lookup"><span data-stu-id="a6f7a-177">A high average reflects a longer delay in the viewing experience.</span></span> <span data-ttu-id="a6f7a-178">На перегруженном сервере конференц-связи могут происходить в среднем более длительные задержки.</span><span class="sxs-lookup"><span data-stu-id="a6f7a-178">An overloaded conferencing server may experience higher average delays.</span></span> <span data-ttu-id="a6f7a-179">Значением по умолчанию является 200ms.</span><span class="sxs-lookup"><span data-stu-id="a6f7a-179">The default value is 200ms.</span></span></p>
<p><span data-ttu-id="a6f7a-180">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a6f7a-180">The column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

