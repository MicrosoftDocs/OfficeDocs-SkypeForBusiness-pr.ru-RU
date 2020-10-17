---
title: 'Lync Server 2013: таблица Аппшарингметрикссрешолд'
description: 'Lync Server 2013: таблица Аппшарингметрикссрешолд.'
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
ms.openlocfilehash: 092c7d08026e6b736b81043a71b4ecaabc4d5f1b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48546815"
---
# <a name="appsharingmetricsthreshold-table-in-lync-server-2013"></a><span data-ttu-id="81269-103">Таблица Аппшарингметрикссрешолд в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="81269-103">AppSharingMetricsThreshold table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="81269-104">_**Последнее изменение темы:** 2015-12-08_</span><span class="sxs-lookup"><span data-stu-id="81269-104">_**Topic Last Modified:** 2015-12-08_</span></span>

<span data-ttu-id="81269-p101">Таблица AppSharingMetricsThreshold содержит оптимальные и допустимые значения показателей качества взаимодействия, применяемые для совместного использования приложений. Эти пороговые значения используются для определения того, следует ли классифицировать совместное использование приложений как плохое.</span><span class="sxs-lookup"><span data-stu-id="81269-p101">The AppSharingMetricsThreshold table contains optimal and acceptable values for the Quality of Experience metrics used with application sharing. These thresholds are used to determine if the application sharing experience should be classified as poor.</span></span>

<span data-ttu-id="81269-107">Эта таблица была введена в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="81269-107">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="81269-108"><strong>Column</strong></span><span class="sxs-lookup"><span data-stu-id="81269-108"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="81269-109"><strong>Тип данных</strong></span><span class="sxs-lookup"><span data-stu-id="81269-109"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="81269-110"><strong>Ключ или индекс</strong></span><span class="sxs-lookup"><span data-stu-id="81269-110"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="81269-111"><strong>Details</strong></span><span class="sxs-lookup"><span data-stu-id="81269-111"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="81269-112"><strong>CallType</strong></span><span class="sxs-lookup"><span data-stu-id="81269-112"><strong>CallType</strong></span></span></p></td>
<td><p><span data-ttu-id="81269-113">int</span><span class="sxs-lookup"><span data-stu-id="81269-113">int</span></span></p></td>
<td><p><span data-ttu-id="81269-114">Primary</span><span class="sxs-lookup"><span data-stu-id="81269-114">Primary</span></span></p></td>
<td><p><span data-ttu-id="81269-115">Тип размещенного вызова.</span><span class="sxs-lookup"><span data-stu-id="81269-115">Type of call that was placed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="81269-116"><strong>апплиедбандвидслимитоптимал</strong></span><span class="sxs-lookup"><span data-stu-id="81269-116"><strong>AppliedBandwidthLimitOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="81269-117">int</span><span class="sxs-lookup"><span data-stu-id="81269-117">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="81269-p102">Оптимальное ограничение полосы пропускания для совместного использования приложений. Значение по умолчанию — 1000000.</span><span class="sxs-lookup"><span data-stu-id="81269-p102">Optimal bandwidth limitation for application sharing. The default value is 1000000.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="81269-120"><strong>апплиедбандвидслимитакцептабле</strong></span><span class="sxs-lookup"><span data-stu-id="81269-120"><strong>AppliedBandwidthLimitAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="81269-121">int</span><span class="sxs-lookup"><span data-stu-id="81269-121">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="81269-p103">Допустимое ограничение полосы пропускания для совместного использования приложений. Значение по умолчанию — 500000.</span><span class="sxs-lookup"><span data-stu-id="81269-p103">Acceptable bandwidth limitation for application sharing. The default value is 500000.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="81269-124"><strong>споиледтилеперценттоталоптимал</strong></span><span class="sxs-lookup"><span data-stu-id="81269-124"><strong>SpoiledTilePercentTotalOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="81269-125">десятичное число (5, 2)</span><span class="sxs-lookup"><span data-stu-id="81269-125">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="81269-p104">Оптимальное процентное отношение для "испорченных" элементов при классификации качества совместного использования приложений. Это значение равно проценту контента от инициатора совместного доступа, который не достигнул зрителя. Контент может быть отклонен (или испорчен), когда инициатор совместного доступа отклоняет элементы от графического источника или ASMCU отклоняет элементы от инициатора совместного доступа. Значение по умолчанию — 14%.</span><span class="sxs-lookup"><span data-stu-id="81269-p104">Optimal percentage rate for “spoiled” tiles for classifying an Application Sharing quality. This value is the percentage of the content from the sharer that did not reach the viewer. Content may be discarded (or spoiled) when the sharer discards tiles from the graphics source or the ASMCU tiles discards tiles from Sharer respectively. The default value is 11 percent.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="81269-130"><strong>споиледтилеперценттоталакцептабле</strong></span><span class="sxs-lookup"><span data-stu-id="81269-130"><strong>SpoiledTilePercentTotalAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="81269-131">десятичное число (5, 2)</span><span class="sxs-lookup"><span data-stu-id="81269-131">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="81269-p105">Допустимое процентное отношение для "испорченных" элементов при классификации качества совместного использования приложений. Это значение равно проценту контента от инициатора совместного доступа, который не достигнул зрителя. Контент может быть отклонен (или испорчен), когда инициатор совместного доступа отклоняет элементы от графического источника или ASMCU отклоняет элементы от инициатора совместного доступа. Значение по умолчанию — 36%.</span><span class="sxs-lookup"><span data-stu-id="81269-p105">cceptable percentage rate for “spoiled” tiles for classifying an Application Sharing quality. This value is the percentage of the content from the sharer that did not reach the viewer. Content may be discarded (or spoiled) when the sharer discards tiles from the graphics source or the ASMCU tiles discards tiles from Sharer respectively. The default value is 36 percent.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="81269-136"><strong>життеринтерарривалоптимал</strong></span><span class="sxs-lookup"><span data-stu-id="81269-136"><strong>JitterInterArrivalOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="81269-137">int</span><span class="sxs-lookup"><span data-stu-id="81269-137">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="81269-138">Этот столбец не используется в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="81269-138">This column is not used in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="81269-139"><strong>життеринтерарривалакцептабле</strong></span><span class="sxs-lookup"><span data-stu-id="81269-139"><strong>JitterInterArrivalAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="81269-140">int</span><span class="sxs-lookup"><span data-stu-id="81269-140">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="81269-141">Этот столбец не используется в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="81269-141">This column is not used in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="81269-142"><strong>релативеоневайбурстденситйоптимал</strong></span><span class="sxs-lookup"><span data-stu-id="81269-142"><strong>RelativeOneWayBurstDensityOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="81269-143">float</span><span class="sxs-lookup"><span data-stu-id="81269-143">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="81269-144">Этот столбец не используется в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="81269-144">This column is not used in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="81269-145"><strong>релативеоневайбурстденситякцептабле</strong></span><span class="sxs-lookup"><span data-stu-id="81269-145"><strong>RelativeOneWayBurstDensityAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="81269-146">float</span><span class="sxs-lookup"><span data-stu-id="81269-146">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="81269-147">Этот столбец не используется в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="81269-147">This column is not used in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="81269-148"><strong>рдптилепроцессинглатенцибурстденситйоптимал</strong></span><span class="sxs-lookup"><span data-stu-id="81269-148"><strong>RDPTileProcessingLatencyBurstDensityOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="81269-149">float</span><span class="sxs-lookup"><span data-stu-id="81269-149">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="81269-150">Этот столбец не используется в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="81269-150">This column is not used in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="81269-151"><strong>рдптилепроцессинглатенцибурстденситякцептабле</strong></span><span class="sxs-lookup"><span data-stu-id="81269-151"><strong>RDPTileProcessingLatencyBurstDensityAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="81269-152">float</span><span class="sxs-lookup"><span data-stu-id="81269-152">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="81269-153">Этот столбец не используется в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="81269-153">This column is not used in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="81269-154"><strong>релативеоневайаверажеоптимал</strong></span><span class="sxs-lookup"><span data-stu-id="81269-154"><strong>RelativeOneWayAverageOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="81269-155">float</span><span class="sxs-lookup"><span data-stu-id="81269-155">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="81269-p106">Оптимальное значение относительной односторонней задержки между двумя конечными точками, участвующими в сеансе совместного использования приложений. Это мера односкачковой задержки. Значение по умолчанию составляет 1 секунду.</span><span class="sxs-lookup"><span data-stu-id="81269-p106">Optimal value for the relative one-way delay between the two media endpoints involved in the application sharing. This is a single-hop latency measure. The default value is 1.0 seconds.</span></span></p>
<p><span data-ttu-id="81269-159">Столбец был введен в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="81269-159">The column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="81269-160"><strong>релативеоневайаверажеакцептабле</strong></span><span class="sxs-lookup"><span data-stu-id="81269-160"><strong>RelativeOneWayAverageAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="81269-161">float</span><span class="sxs-lookup"><span data-stu-id="81269-161">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="81269-p107">Оптимальное значение относительной односторонней задержки между двумя конечными точками, участвующими в сеансе совместного использования приложений. Это мера односкачковой задержки. Значение по умолчанию составляет 1,75 секунды.</span><span class="sxs-lookup"><span data-stu-id="81269-p107">Optimal value for the relative one-way delay between the two media endpoints involved in the application sharing. This is a single-hop latency measure. The default value is 1.75 seconds.</span></span></p>
<p><span data-ttu-id="81269-165">Столбец был введен в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="81269-165">The column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="81269-166"><strong>рдптилепроцессинглатенциаверажеоптимал</strong></span><span class="sxs-lookup"><span data-stu-id="81269-166"><strong>RDPTileProcessingLatencyAverageOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="81269-167">float</span><span class="sxs-lookup"><span data-stu-id="81269-167">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="81269-168">Оптимальное значение задержки обработки элементов RDP на сервере конференц-связи общего доступа к приложениям во время сеанса просмотра.</span><span class="sxs-lookup"><span data-stu-id="81269-168">Optimal value of the average RDP tile processing latency in the AS Conferencing Server over the duration of the viewing session.</span></span> <span data-ttu-id="81269-169">Задержка — это разница во времени между моментом кодирования начального кадра на сервере (совместное использование или MCU в зависимости от сценария) и тем же начальным кадром, который декодируется в средстве просмотра.</span><span class="sxs-lookup"><span data-stu-id="81269-169">Latency is the time difference between when the Start Frame is encoded on the server (sharer or MCU depending on the scenario) and the same Start Frame is decoded on the viewer.</span></span></p>
<p><span data-ttu-id="81269-p109">Высокое среднее значение отражает более длительную задержку в процессе просмотра. Для перегруженного сервера конференц-связи могут наблюдаться более высокие средние значения задержки. Значение по умолчанию равно 200 мс.</span><span class="sxs-lookup"><span data-stu-id="81269-p109">A high average reflects a longer delay in the viewing experience. An overloaded conferencing server may experience higher average delays. The default value is 200ms.</span></span></p>
<p><span data-ttu-id="81269-173">Столбец был введен в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="81269-173">The column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="81269-174"><strong>рдптилепроцессинглатенциаверажеакцептабле</strong></span><span class="sxs-lookup"><span data-stu-id="81269-174"><strong>RDPTileProcessingLatencyAverageAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="81269-175">float</span><span class="sxs-lookup"><span data-stu-id="81269-175">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="81269-176">Допустимое значение задержки обработки элементов RDP на сервере конференц-связи общего доступа к приложениям во время сеанса просмотра.</span><span class="sxs-lookup"><span data-stu-id="81269-176">Acceptable value of the average RDP tile processing latency in the AS Conferencing Server over the duration of the viewing session.</span></span> <span data-ttu-id="81269-177">Задержка — это разница во времени между моментом кодирования начального кадра на сервере (совместное использование или MCU в зависимости от сценария) и тем же начальным кадром, который декодируется в средстве просмотра.</span><span class="sxs-lookup"><span data-stu-id="81269-177">Latency is the time difference between when the Start Frame is encoded on the server (sharer or MCU depending on the scenario) and the same Start Frame is decoded on the viewer.</span></span></p>
<p><span data-ttu-id="81269-p111">Высокое среднее значение отражает более длительную задержку в процессе просмотра. Для перегруженного сервера конференц-связи могут наблюдаться более высокие средние значения задержки. Значение по умолчанию равно 200 мс.</span><span class="sxs-lookup"><span data-stu-id="81269-p111">A high average reflects a longer delay in the viewing experience. An overloaded conferencing server may experience higher average delays. The default value is 200ms.</span></span></p>
<p><span data-ttu-id="81269-181">Столбец был введен в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="81269-181">The column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

