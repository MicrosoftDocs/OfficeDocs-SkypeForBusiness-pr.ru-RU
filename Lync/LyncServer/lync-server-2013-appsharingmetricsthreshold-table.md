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
ms.openlocfilehash: 6e7a2d73f09a3cb48b1d50f06aa530c91d779b28
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48529556"
---
# <a name="appsharingmetricsthreshold-table-in-lync-server-2013"></a><span data-ttu-id="1dc3b-102">Таблица Аппшарингметрикссрешолд в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1dc3b-102">AppSharingMetricsThreshold table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1dc3b-103">_**Последнее изменение темы:** 2015-12-08_</span><span class="sxs-lookup"><span data-stu-id="1dc3b-103">_**Topic Last Modified:** 2015-12-08_</span></span>

<span data-ttu-id="1dc3b-p101">Таблица AppSharingMetricsThreshold содержит оптимальные и допустимые значения показателей качества взаимодействия, применяемые для совместного использования приложений. Эти пороговые значения используются для определения того, следует ли классифицировать совместное использование приложений как плохое.</span><span class="sxs-lookup"><span data-stu-id="1dc3b-p101">The AppSharingMetricsThreshold table contains optimal and acceptable values for the Quality of Experience metrics used with application sharing. These thresholds are used to determine if the application sharing experience should be classified as poor.</span></span>

<span data-ttu-id="1dc3b-106">Эта таблица была введена в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1dc3b-106">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1dc3b-107"><strong>Column</strong></span><span class="sxs-lookup"><span data-stu-id="1dc3b-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="1dc3b-108"><strong>Тип данных</strong></span><span class="sxs-lookup"><span data-stu-id="1dc3b-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="1dc3b-109"><strong>Ключ или индекс</strong></span><span class="sxs-lookup"><span data-stu-id="1dc3b-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="1dc3b-110"><strong>Details</strong></span><span class="sxs-lookup"><span data-stu-id="1dc3b-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1dc3b-111"><strong>CallType</strong></span><span class="sxs-lookup"><span data-stu-id="1dc3b-111"><strong>CallType</strong></span></span></p></td>
<td><p><span data-ttu-id="1dc3b-112">int</span><span class="sxs-lookup"><span data-stu-id="1dc3b-112">int</span></span></p></td>
<td><p><span data-ttu-id="1dc3b-113">Primary</span><span class="sxs-lookup"><span data-stu-id="1dc3b-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="1dc3b-114">Тип размещенного вызова.</span><span class="sxs-lookup"><span data-stu-id="1dc3b-114">Type of call that was placed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1dc3b-115"><strong>апплиедбандвидслимитоптимал</strong></span><span class="sxs-lookup"><span data-stu-id="1dc3b-115"><strong>AppliedBandwidthLimitOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="1dc3b-116">int</span><span class="sxs-lookup"><span data-stu-id="1dc3b-116">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1dc3b-p102">Оптимальное ограничение полосы пропускания для совместного использования приложений. Значение по умолчанию — 1000000.</span><span class="sxs-lookup"><span data-stu-id="1dc3b-p102">Optimal bandwidth limitation for application sharing. The default value is 1000000.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1dc3b-119"><strong>апплиедбандвидслимитакцептабле</strong></span><span class="sxs-lookup"><span data-stu-id="1dc3b-119"><strong>AppliedBandwidthLimitAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="1dc3b-120">int</span><span class="sxs-lookup"><span data-stu-id="1dc3b-120">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1dc3b-p103">Допустимое ограничение полосы пропускания для совместного использования приложений. Значение по умолчанию — 500000.</span><span class="sxs-lookup"><span data-stu-id="1dc3b-p103">Acceptable bandwidth limitation for application sharing. The default value is 500000.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1dc3b-123"><strong>споиледтилеперценттоталоптимал</strong></span><span class="sxs-lookup"><span data-stu-id="1dc3b-123"><strong>SpoiledTilePercentTotalOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="1dc3b-124">десятичное число (5, 2)</span><span class="sxs-lookup"><span data-stu-id="1dc3b-124">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1dc3b-p104">Оптимальное процентное отношение для "испорченных" элементов при классификации качества совместного использования приложений. Это значение равно проценту контента от инициатора совместного доступа, который не достигнул зрителя. Контент может быть отклонен (или испорчен), когда инициатор совместного доступа отклоняет элементы от графического источника или ASMCU отклоняет элементы от инициатора совместного доступа. Значение по умолчанию — 14%.</span><span class="sxs-lookup"><span data-stu-id="1dc3b-p104">Optimal percentage rate for “spoiled” tiles for classifying an Application Sharing quality. This value is the percentage of the content from the sharer that did not reach the viewer. Content may be discarded (or spoiled) when the sharer discards tiles from the graphics source or the ASMCU tiles discards tiles from Sharer respectively. The default value is 11 percent.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1dc3b-129"><strong>споиледтилеперценттоталакцептабле</strong></span><span class="sxs-lookup"><span data-stu-id="1dc3b-129"><strong>SpoiledTilePercentTotalAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="1dc3b-130">десятичное число (5, 2)</span><span class="sxs-lookup"><span data-stu-id="1dc3b-130">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1dc3b-p105">Допустимое процентное отношение для "испорченных" элементов при классификации качества совместного использования приложений. Это значение равно проценту контента от инициатора совместного доступа, который не достигнул зрителя. Контент может быть отклонен (или испорчен), когда инициатор совместного доступа отклоняет элементы от графического источника или ASMCU отклоняет элементы от инициатора совместного доступа. Значение по умолчанию — 36%.</span><span class="sxs-lookup"><span data-stu-id="1dc3b-p105">cceptable percentage rate for “spoiled” tiles for classifying an Application Sharing quality. This value is the percentage of the content from the sharer that did not reach the viewer. Content may be discarded (or spoiled) when the sharer discards tiles from the graphics source or the ASMCU tiles discards tiles from Sharer respectively. The default value is 36 percent.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1dc3b-135"><strong>життеринтерарривалоптимал</strong></span><span class="sxs-lookup"><span data-stu-id="1dc3b-135"><strong>JitterInterArrivalOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="1dc3b-136">int</span><span class="sxs-lookup"><span data-stu-id="1dc3b-136">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1dc3b-137">Этот столбец не используется в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1dc3b-137">This column is not used in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1dc3b-138"><strong>життеринтерарривалакцептабле</strong></span><span class="sxs-lookup"><span data-stu-id="1dc3b-138"><strong>JitterInterArrivalAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="1dc3b-139">int</span><span class="sxs-lookup"><span data-stu-id="1dc3b-139">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1dc3b-140">Этот столбец не используется в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1dc3b-140">This column is not used in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1dc3b-141"><strong>релативеоневайбурстденситйоптимал</strong></span><span class="sxs-lookup"><span data-stu-id="1dc3b-141"><strong>RelativeOneWayBurstDensityOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="1dc3b-142">float</span><span class="sxs-lookup"><span data-stu-id="1dc3b-142">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1dc3b-143">Этот столбец не используется в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1dc3b-143">This column is not used in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1dc3b-144"><strong>релативеоневайбурстденситякцептабле</strong></span><span class="sxs-lookup"><span data-stu-id="1dc3b-144"><strong>RelativeOneWayBurstDensityAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="1dc3b-145">float</span><span class="sxs-lookup"><span data-stu-id="1dc3b-145">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1dc3b-146">Этот столбец не используется в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1dc3b-146">This column is not used in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1dc3b-147"><strong>рдптилепроцессинглатенцибурстденситйоптимал</strong></span><span class="sxs-lookup"><span data-stu-id="1dc3b-147"><strong>RDPTileProcessingLatencyBurstDensityOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="1dc3b-148">float</span><span class="sxs-lookup"><span data-stu-id="1dc3b-148">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1dc3b-149">Этот столбец не используется в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1dc3b-149">This column is not used in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1dc3b-150"><strong>рдптилепроцессинглатенцибурстденситякцептабле</strong></span><span class="sxs-lookup"><span data-stu-id="1dc3b-150"><strong>RDPTileProcessingLatencyBurstDensityAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="1dc3b-151">float</span><span class="sxs-lookup"><span data-stu-id="1dc3b-151">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1dc3b-152">Этот столбец не используется в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1dc3b-152">This column is not used in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1dc3b-153"><strong>релативеоневайаверажеоптимал</strong></span><span class="sxs-lookup"><span data-stu-id="1dc3b-153"><strong>RelativeOneWayAverageOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="1dc3b-154">float</span><span class="sxs-lookup"><span data-stu-id="1dc3b-154">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1dc3b-p106">Оптимальное значение относительной односторонней задержки между двумя конечными точками, участвующими в сеансе совместного использования приложений. Это мера односкачковой задержки. Значение по умолчанию составляет 1 секунду.</span><span class="sxs-lookup"><span data-stu-id="1dc3b-p106">Optimal value for the relative one-way delay between the two media endpoints involved in the application sharing. This is a single-hop latency measure. The default value is 1.0 seconds.</span></span></p>
<p><span data-ttu-id="1dc3b-158">Столбец был введен в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1dc3b-158">The column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1dc3b-159"><strong>релативеоневайаверажеакцептабле</strong></span><span class="sxs-lookup"><span data-stu-id="1dc3b-159"><strong>RelativeOneWayAverageAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="1dc3b-160">float</span><span class="sxs-lookup"><span data-stu-id="1dc3b-160">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1dc3b-p107">Оптимальное значение относительной односторонней задержки между двумя конечными точками, участвующими в сеансе совместного использования приложений. Это мера односкачковой задержки. Значение по умолчанию составляет 1,75 секунды.</span><span class="sxs-lookup"><span data-stu-id="1dc3b-p107">Optimal value for the relative one-way delay between the two media endpoints involved in the application sharing. This is a single-hop latency measure. The default value is 1.75 seconds.</span></span></p>
<p><span data-ttu-id="1dc3b-164">Столбец был введен в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1dc3b-164">The column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1dc3b-165"><strong>рдптилепроцессинглатенциаверажеоптимал</strong></span><span class="sxs-lookup"><span data-stu-id="1dc3b-165"><strong>RDPTileProcessingLatencyAverageOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="1dc3b-166">float</span><span class="sxs-lookup"><span data-stu-id="1dc3b-166">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1dc3b-167">Оптимальное значение задержки обработки элементов RDP на сервере конференц-связи общего доступа к приложениям во время сеанса просмотра.</span><span class="sxs-lookup"><span data-stu-id="1dc3b-167">Optimal value of the average RDP tile processing latency in the AS Conferencing Server over the duration of the viewing session.</span></span> <span data-ttu-id="1dc3b-168">Задержка — это разница во времени между моментом кодирования начального кадра на сервере (совместное использование или MCU в зависимости от сценария) и тем же начальным кадром, который декодируется в средстве просмотра.</span><span class="sxs-lookup"><span data-stu-id="1dc3b-168">Latency is the time difference between when the Start Frame is encoded on the server (sharer or MCU depending on the scenario) and the same Start Frame is decoded on the viewer.</span></span></p>
<p><span data-ttu-id="1dc3b-p109">Высокое среднее значение отражает более длительную задержку в процессе просмотра. Для перегруженного сервера конференц-связи могут наблюдаться более высокие средние значения задержки. Значение по умолчанию равно 200 мс.</span><span class="sxs-lookup"><span data-stu-id="1dc3b-p109">A high average reflects a longer delay in the viewing experience. An overloaded conferencing server may experience higher average delays. The default value is 200ms.</span></span></p>
<p><span data-ttu-id="1dc3b-172">Столбец был введен в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1dc3b-172">The column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1dc3b-173"><strong>рдптилепроцессинглатенциаверажеакцептабле</strong></span><span class="sxs-lookup"><span data-stu-id="1dc3b-173"><strong>RDPTileProcessingLatencyAverageAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="1dc3b-174">float</span><span class="sxs-lookup"><span data-stu-id="1dc3b-174">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1dc3b-175">Допустимое значение задержки обработки элементов RDP на сервере конференц-связи общего доступа к приложениям во время сеанса просмотра.</span><span class="sxs-lookup"><span data-stu-id="1dc3b-175">Acceptable value of the average RDP tile processing latency in the AS Conferencing Server over the duration of the viewing session.</span></span> <span data-ttu-id="1dc3b-176">Задержка — это разница во времени между моментом кодирования начального кадра на сервере (совместное использование или MCU в зависимости от сценария) и тем же начальным кадром, который декодируется в средстве просмотра.</span><span class="sxs-lookup"><span data-stu-id="1dc3b-176">Latency is the time difference between when the Start Frame is encoded on the server (sharer or MCU depending on the scenario) and the same Start Frame is decoded on the viewer.</span></span></p>
<p><span data-ttu-id="1dc3b-p111">Высокое среднее значение отражает более длительную задержку в процессе просмотра. Для перегруженного сервера конференц-связи могут наблюдаться более высокие средние значения задержки. Значение по умолчанию равно 200 мс.</span><span class="sxs-lookup"><span data-stu-id="1dc3b-p111">A high average reflects a longer delay in the viewing experience. An overloaded conferencing server may experience higher average delays. The default value is 200ms.</span></span></p>
<p><span data-ttu-id="1dc3b-180">Столбец был введен в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1dc3b-180">The column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

