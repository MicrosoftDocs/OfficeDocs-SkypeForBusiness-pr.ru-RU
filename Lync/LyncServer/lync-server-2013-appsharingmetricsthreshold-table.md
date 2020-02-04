---
title: 'Lync Server 2013: таблица Аппшарингметрикссрешолд'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: AppSharingMetricsThreshold table
ms:assetid: 782cfab9-01a6-4843-aea1-28f47b0b51f7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205018(v=OCS.15)
ms:contentKeyID: 48184556
ms.date: 12/09/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7e247f83b00d226024f9fc671f2d744f1ee7fdf0
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41738429"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="appsharingmetricsthreshold-table-in-lync-server-2013"></a><span data-ttu-id="6617d-102">Таблица Аппшарингметрикссрешолд в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6617d-102">AppSharingMetricsThreshold table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6617d-103">_**Тема последнего изменения:** 2015-12-08_</span><span class="sxs-lookup"><span data-stu-id="6617d-103">_**Topic Last Modified:** 2015-12-08_</span></span>

<span data-ttu-id="6617d-104">В таблице Аппшарингметрикссрешолд содержатся оптимальные и приемлемые значения для показателей качества взаимодействия, используемых совместно с приложением.</span><span class="sxs-lookup"><span data-stu-id="6617d-104">The AppSharingMetricsThreshold table contains optimal and acceptable values for the Quality of Experience metrics used with application sharing.</span></span> <span data-ttu-id="6617d-105">Эти пороговые значения используются, чтобы определить, следует ли классифицировать взаимодействие приложений как неудовлетворительные.</span><span class="sxs-lookup"><span data-stu-id="6617d-105">These thresholds are used to determine if the application sharing experience should be classified as poor.</span></span>

<span data-ttu-id="6617d-106">Эта таблица введена в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6617d-106">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6617d-107"><strong>Столбец</strong></span><span class="sxs-lookup"><span data-stu-id="6617d-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="6617d-108"><strong>Тип данных</strong></span><span class="sxs-lookup"><span data-stu-id="6617d-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="6617d-109"><strong>Ключ/индекс</strong></span><span class="sxs-lookup"><span data-stu-id="6617d-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="6617d-110"><strong>Сведения</strong></span><span class="sxs-lookup"><span data-stu-id="6617d-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6617d-111"><strong>CallType</strong></span><span class="sxs-lookup"><span data-stu-id="6617d-111"><strong>CallType</strong></span></span></p></td>
<td><p><span data-ttu-id="6617d-112">целое</span><span class="sxs-lookup"><span data-stu-id="6617d-112">int</span></span></p></td>
<td><p><span data-ttu-id="6617d-113">Primary</span><span class="sxs-lookup"><span data-stu-id="6617d-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="6617d-114">Тип размещенного звонка.</span><span class="sxs-lookup"><span data-stu-id="6617d-114">Type of call that was placed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6617d-115"><strong>апплиедбандвидслимитоптимал</strong></span><span class="sxs-lookup"><span data-stu-id="6617d-115"><strong>AppliedBandwidthLimitOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="6617d-116">целое</span><span class="sxs-lookup"><span data-stu-id="6617d-116">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6617d-117">Оптимальное ограничение пропускной способности для совместного использования приложений.</span><span class="sxs-lookup"><span data-stu-id="6617d-117">Optimal bandwidth limitation for application sharing.</span></span> <span data-ttu-id="6617d-118">Значение по умолчанию — 1000000.</span><span class="sxs-lookup"><span data-stu-id="6617d-118">The default value is 1000000.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6617d-119"><strong>апплиедбандвидслимитакцептабле</strong></span><span class="sxs-lookup"><span data-stu-id="6617d-119"><strong>AppliedBandwidthLimitAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="6617d-120">целое</span><span class="sxs-lookup"><span data-stu-id="6617d-120">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6617d-121">Допустимое ограничение пропускной способности для совместного использования приложений.</span><span class="sxs-lookup"><span data-stu-id="6617d-121">Acceptable bandwidth limitation for application sharing.</span></span> <span data-ttu-id="6617d-122">Значение по умолчанию — 500000.</span><span class="sxs-lookup"><span data-stu-id="6617d-122">The default value is 500000.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6617d-123"><strong>споиледтилеперценттоталоптимал</strong></span><span class="sxs-lookup"><span data-stu-id="6617d-123"><strong>SpoiledTilePercentTotalOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="6617d-124">десятичное число (5; 2)</span><span class="sxs-lookup"><span data-stu-id="6617d-124">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6617d-125">Оптимальная процентная ставка для плиток "spoiled" для классификации качества общего использования приложения.</span><span class="sxs-lookup"><span data-stu-id="6617d-125">Optimal percentage rate for “spoiled” tiles for classifying an Application Sharing quality.</span></span> <span data-ttu-id="6617d-126">Это значение — процент содержимого от общего доступа, которое не было доступно для просмотра.</span><span class="sxs-lookup"><span data-stu-id="6617d-126">This value is the percentage of the content from the sharer that did not reach the viewer.</span></span> <span data-ttu-id="6617d-127">Содержимое может быть удалено (или spoiled), когда общий доступ отбрасывает плитки из источника графики, или АСМКУ плитки отбрасывают плитки от общего доступа, соответственно.</span><span class="sxs-lookup"><span data-stu-id="6617d-127">Content may be discarded (or spoiled) when the sharer discards tiles from the graphics source or the ASMCU tiles discards tiles from Sharer respectively.</span></span> <span data-ttu-id="6617d-128">Значение по умолчанию составляет 11 процентов.</span><span class="sxs-lookup"><span data-stu-id="6617d-128">The default value is 11 percent.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6617d-129"><strong>споиледтилеперценттоталакцептабле</strong></span><span class="sxs-lookup"><span data-stu-id="6617d-129"><strong>SpoiledTilePercentTotalAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="6617d-130">десятичное число (5; 2)</span><span class="sxs-lookup"><span data-stu-id="6617d-130">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6617d-131">кцептабле процентная ставка для плиток "spoiled" для классификации качества общего использования приложения.</span><span class="sxs-lookup"><span data-stu-id="6617d-131">cceptable percentage rate for “spoiled” tiles for classifying an Application Sharing quality.</span></span> <span data-ttu-id="6617d-132">Это значение — процент содержимого от общего доступа, которое не было доступно для просмотра.</span><span class="sxs-lookup"><span data-stu-id="6617d-132">This value is the percentage of the content from the sharer that did not reach the viewer.</span></span> <span data-ttu-id="6617d-133">Содержимое может быть удалено (или spoiled), когда общий доступ отбрасывает плитки из источника графики, или АСМКУ плитки отбрасывают плитки от общего доступа, соответственно.</span><span class="sxs-lookup"><span data-stu-id="6617d-133">Content may be discarded (or spoiled) when the sharer discards tiles from the graphics source or the ASMCU tiles discards tiles from Sharer respectively.</span></span> <span data-ttu-id="6617d-134">Значение по умолчанию составляет 36%.</span><span class="sxs-lookup"><span data-stu-id="6617d-134">The default value is 36 percent.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6617d-135"><strong>життеринтерарривалоптимал</strong></span><span class="sxs-lookup"><span data-stu-id="6617d-135"><strong>JitterInterArrivalOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="6617d-136">целое</span><span class="sxs-lookup"><span data-stu-id="6617d-136">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6617d-137">Этот столбец не используется в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6617d-137">This column is not used in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6617d-138"><strong>життеринтерарривалакцептабле</strong></span><span class="sxs-lookup"><span data-stu-id="6617d-138"><strong>JitterInterArrivalAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="6617d-139">целое</span><span class="sxs-lookup"><span data-stu-id="6617d-139">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6617d-140">Этот столбец не используется в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6617d-140">This column is not used in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6617d-141"><strong>релативеоневайбурстденситйоптимал</strong></span><span class="sxs-lookup"><span data-stu-id="6617d-141"><strong>RelativeOneWayBurstDensityOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="6617d-142">число с плавающей точкой</span><span class="sxs-lookup"><span data-stu-id="6617d-142">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6617d-143">Этот столбец не используется в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6617d-143">This column is not used in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6617d-144"><strong>релативеоневайбурстденситякцептабле</strong></span><span class="sxs-lookup"><span data-stu-id="6617d-144"><strong>RelativeOneWayBurstDensityAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="6617d-145">число с плавающей точкой</span><span class="sxs-lookup"><span data-stu-id="6617d-145">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6617d-146">Этот столбец не используется в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6617d-146">This column is not used in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6617d-147"><strong>рдптилепроцессинглатенцибурстденситйоптимал</strong></span><span class="sxs-lookup"><span data-stu-id="6617d-147"><strong>RDPTileProcessingLatencyBurstDensityOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="6617d-148">число с плавающей точкой</span><span class="sxs-lookup"><span data-stu-id="6617d-148">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6617d-149">Этот столбец не используется в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6617d-149">This column is not used in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6617d-150"><strong>рдптилепроцессинглатенцибурстденситякцептабле</strong></span><span class="sxs-lookup"><span data-stu-id="6617d-150"><strong>RDPTileProcessingLatencyBurstDensityAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="6617d-151">число с плавающей точкой</span><span class="sxs-lookup"><span data-stu-id="6617d-151">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6617d-152">Этот столбец не используется в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6617d-152">This column is not used in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6617d-153"><strong>релативеоневайаверажеоптимал</strong></span><span class="sxs-lookup"><span data-stu-id="6617d-153"><strong>RelativeOneWayAverageOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="6617d-154">число с плавающей точкой</span><span class="sxs-lookup"><span data-stu-id="6617d-154">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6617d-155">Оптимальное значение для относительной односторонней задержки между двумя конечными точками мультимедиа, задействованными в общем доступе к приложению.</span><span class="sxs-lookup"><span data-stu-id="6617d-155">Optimal value for the relative one-way delay between the two media endpoints involved in the application sharing.</span></span> <span data-ttu-id="6617d-156">Это мера односкачковой задержки.</span><span class="sxs-lookup"><span data-stu-id="6617d-156">This is a single-hop latency measure.</span></span> <span data-ttu-id="6617d-157">Значение по умолчанию — 1,0 секунд.</span><span class="sxs-lookup"><span data-stu-id="6617d-157">The default value is 1.0 seconds.</span></span></p>
<p><span data-ttu-id="6617d-158">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6617d-158">The column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6617d-159"><strong>релативеоневайаверажеакцептабле</strong></span><span class="sxs-lookup"><span data-stu-id="6617d-159"><strong>RelativeOneWayAverageAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="6617d-160">число с плавающей точкой</span><span class="sxs-lookup"><span data-stu-id="6617d-160">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6617d-161">Оптимальное значение для относительной односторонней задержки между двумя конечными точками мультимедиа, задействованными в общем доступе к приложению.</span><span class="sxs-lookup"><span data-stu-id="6617d-161">Optimal value for the relative one-way delay between the two media endpoints involved in the application sharing.</span></span> <span data-ttu-id="6617d-162">Это мера односкачковой задержки.</span><span class="sxs-lookup"><span data-stu-id="6617d-162">This is a single-hop latency measure.</span></span> <span data-ttu-id="6617d-163">Значение по умолчанию — 1,75 секунд.</span><span class="sxs-lookup"><span data-stu-id="6617d-163">The default value is 1.75 seconds.</span></span></p>
<p><span data-ttu-id="6617d-164">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6617d-164">The column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6617d-165"><strong>рдптилепроцессинглатенциаверажеоптимал</strong></span><span class="sxs-lookup"><span data-stu-id="6617d-165"><strong>RDPTileProcessingLatencyAverageOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="6617d-166">число с плавающей точкой</span><span class="sxs-lookup"><span data-stu-id="6617d-166">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6617d-167">Оптимальное значение средней задержки обработки плитки RDP на сервере конференций в течение сеанса просмотра.</span><span class="sxs-lookup"><span data-stu-id="6617d-167">Optimal value of the average RDP tile processing latency in the AS Conferencing Server over the duration of the viewing session.</span></span> <span data-ttu-id="6617d-168">Задержка — это разница во времени между моментом, когда начальный кадр кодируется на сервере (в зависимости от сценария, или MCU, а также с помощью того же начального кадра декодируется в средстве просмотра).</span><span class="sxs-lookup"><span data-stu-id="6617d-168">Latency is the time difference between when the Start Frame is encoded on the server (sharer or MCU depending on the scenario) and the same Start Frame is decoded on the viewer.</span></span></p>
<p><span data-ttu-id="6617d-169">Высокое среднее значение отражает более длительную задержку при просмотре.</span><span class="sxs-lookup"><span data-stu-id="6617d-169">A high average reflects a longer delay in the viewing experience.</span></span> <span data-ttu-id="6617d-170">На перегруженном сервере конференц-связи могут происходить в среднем более длительные задержки.</span><span class="sxs-lookup"><span data-stu-id="6617d-170">An overloaded conferencing server may experience higher average delays.</span></span> <span data-ttu-id="6617d-171">Значением по умолчанию является 200ms.</span><span class="sxs-lookup"><span data-stu-id="6617d-171">The default value is 200ms.</span></span></p>
<p><span data-ttu-id="6617d-172">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6617d-172">The column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6617d-173"><strong>рдптилепроцессинглатенциаверажеакцептабле</strong></span><span class="sxs-lookup"><span data-stu-id="6617d-173"><strong>RDPTileProcessingLatencyAverageAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="6617d-174">число с плавающей точкой</span><span class="sxs-lookup"><span data-stu-id="6617d-174">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6617d-175">Допустимое значение средней задержки обработки плитки RDP на сервере конференций в течение сеанса просмотра.</span><span class="sxs-lookup"><span data-stu-id="6617d-175">Acceptable value of the average RDP tile processing latency in the AS Conferencing Server over the duration of the viewing session.</span></span> <span data-ttu-id="6617d-176">Задержка — это разница во времени между моментом, когда начальный кадр кодируется на сервере (в зависимости от сценария, или MCU, а также с помощью того же начального кадра декодируется в средстве просмотра).</span><span class="sxs-lookup"><span data-stu-id="6617d-176">Latency is the time difference between when the Start Frame is encoded on the server (sharer or MCU depending on the scenario) and the same Start Frame is decoded on the viewer.</span></span></p>
<p><span data-ttu-id="6617d-177">Высокое среднее значение отражает более длительную задержку при просмотре.</span><span class="sxs-lookup"><span data-stu-id="6617d-177">A high average reflects a longer delay in the viewing experience.</span></span> <span data-ttu-id="6617d-178">На перегруженном сервере конференц-связи могут происходить в среднем более длительные задержки.</span><span class="sxs-lookup"><span data-stu-id="6617d-178">An overloaded conferencing server may experience higher average delays.</span></span> <span data-ttu-id="6617d-179">Значением по умолчанию является 200ms.</span><span class="sxs-lookup"><span data-stu-id="6617d-179">The default value is 200ms.</span></span></p>
<p><span data-ttu-id="6617d-180">Этот столбец появился в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6617d-180">The column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

