---
title: 'Lync Server 2013: Настройка примеров видеороликов'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring video example scenarios
ms:assetid: da0d61a2-7ac4-4562-bf6a-18473a29acb2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205297(v=OCS.15)
ms:contentKeyID: 48185536
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 085a87d24efed3f9f5e1a5d2d30c29c9b8461693
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42029962"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-video-example-scenarios-for-lync-server-2013"></a><span data-ttu-id="719c6-102">Настройка примеров видеороликов для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="719c6-102">Configuring video example scenarios for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="719c6-103">_**Последнее изменение темы:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="719c6-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="719c6-104">Lync 2013 добавляет новые функции видео для поддержки видеоролика и видеоролика в формате High Definition 1920 x 1080 (HD).</span><span class="sxs-lookup"><span data-stu-id="719c6-104">Lync 2013 adds new video features to support 1920 x 1080 full high definition (HD) video and Gallery View video.</span></span> <span data-ttu-id="719c6-105">Измерения, основанные на данных о клиентах, показывают, что обычная пропускная способность видеосвязи увеличивается только в Lync 2010, но максимальная пропускная способность видеопотока увеличилась в связи с полной поддержкой HD (Дополнительные сведения см. в разделе "использование сети трафика мультимедиа" [требования к пропускной способности сети для трафика мультимедиа в Lync Server 2013](lync-server-2013-network-bandwidth-requirements-for-media-traffic.md)).</span><span class="sxs-lookup"><span data-stu-id="719c6-105">Measurements based on customer data show that the typical video bandwidth increased only slightly compared to Lync 2010, but the maximum video stream bandwidth has increased due to full HD support (for details, see the "Media Traffic Network Usage" section in [Network bandwidth requirements for media traffic in Lync Server 2013](lync-server-2013-network-bandwidth-requirements-for-media-traffic.md)).</span></span> <span data-ttu-id="719c6-106">Поэтому администраторам, возможно, потребуется ограничить полосу пропускания видео для определенных пользователей (например, для сотрудников филиалов, которым требуется меньшее потребление сети) при одновременном сохранении оптимального качества видео для других пользователей (например, для руководителей).</span><span class="sxs-lookup"><span data-stu-id="719c6-106">Therefore, administrators may want to restrict video bandwidth for certain users (such as users in a branch office that has less network capacity) and help to ensure the best possible video quality for other users (such as executives).</span></span>

<span data-ttu-id="719c6-p102">В следующей таблице представлен список рекомендуемых параметров для настройки видео в зависимости от требуемой полосы пропускания сети. Эти параметры позволяют ограничить возможности передачи и приема видео высокого разрешения для отдельных пользователей (см. самый правый столбец). Установка минимального значения приводит к тому, что режим «Развернутый вид» становится недоступным в связи с установкой минимальной полосы пропускания.</span><span class="sxs-lookup"><span data-stu-id="719c6-p102">The following table provides a list of recommended settings for configuring video for different network capacities. These settings will restrict some user scenarios from sending and receiving higher resolution videos (see rightmost column). The minimum setting will result in Gallery Video being unavailable, due to the low maximum receive network bandwidth.</span></span>

### <a name="recommended-video-settings"></a><span data-ttu-id="719c6-110">Рекомендуемые параметры видео Параметры</span><span class="sxs-lookup"><span data-stu-id="719c6-110">Recommended Video Settings</span></span>

<table style="width:100%;">
<colgroup>
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
</colgroup>
<thead>
<tr class="header">
<th>-</th>
<th><span data-ttu-id="719c6-111">алловмултивиев</span><span class="sxs-lookup"><span data-stu-id="719c6-111">AllowMultiView</span></span></th>
<th><span data-ttu-id="719c6-112">Для параметра enablemultiviewjoin</span><span class="sxs-lookup"><span data-stu-id="719c6-112">EnableMultiViewJoin</span></span></th>
<th><span data-ttu-id="719c6-113">видеобитратекб</span><span class="sxs-lookup"><span data-stu-id="719c6-113">VideoBitRateKB</span></span></th>
<th><span data-ttu-id="719c6-114">Параметра totalreceivevideobitratekb задано</span><span class="sxs-lookup"><span data-stu-id="719c6-114">TotalReceiveVideoBitRateKB</span></span></th>
<th><span data-ttu-id="719c6-115">Ожидаемое разрешение видео для обеспечения передачи высокого качества</span><span class="sxs-lookup"><span data-stu-id="719c6-115">Expected video resolution for good quality video</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="719c6-116">Лучший</span><span class="sxs-lookup"><span data-stu-id="719c6-116">Best</span></span></p></td>
<td><p><span data-ttu-id="719c6-117">Да</span><span class="sxs-lookup"><span data-stu-id="719c6-117">True</span></span></p></td>
<td><p><span data-ttu-id="719c6-118">Да</span><span class="sxs-lookup"><span data-stu-id="719c6-118">True</span></span></p></td>
<td><p><span data-ttu-id="719c6-119">8000</span><span class="sxs-lookup"><span data-stu-id="719c6-119">8000</span></span></p></td>
<td><p><span data-ttu-id="719c6-120">8000</span><span class="sxs-lookup"><span data-stu-id="719c6-120">8000</span></span></p></td>
<td><p><span data-ttu-id="719c6-121">Одноранговая передача: разрешение видео до 1920 x 1080</span><span class="sxs-lookup"><span data-stu-id="719c6-121">Peer-to-peer: Up to 1920 x 1080 video resolution</span></span></p>
<p><span data-ttu-id="719c6-122">Расширенный вид: до двух видео с разрешением 1920 x 1080 или несколько видео с более низким разрешением</span><span class="sxs-lookup"><span data-stu-id="719c6-122">Gallery View: Up to two 1920 x 1080 videos or multiple smaller resolution videos</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="719c6-123">Good</span><span class="sxs-lookup"><span data-stu-id="719c6-123">Good</span></span></p></td>
<td><p><span data-ttu-id="719c6-124">Да</span><span class="sxs-lookup"><span data-stu-id="719c6-124">True</span></span></p></td>
<td><p><span data-ttu-id="719c6-125">Да</span><span class="sxs-lookup"><span data-stu-id="719c6-125">True</span></span></p></td>
<td><p><span data-ttu-id="719c6-126">2500</span><span class="sxs-lookup"><span data-stu-id="719c6-126">2500</span></span></p></td>
<td><p><span data-ttu-id="719c6-127">2500</span><span class="sxs-lookup"><span data-stu-id="719c6-127">2500</span></span></p></td>
<td><p><span data-ttu-id="719c6-128">Одноранговая передача: разрешение видео до 1280 x 720</span><span class="sxs-lookup"><span data-stu-id="719c6-128">Peer-to-peer: Up to 1280 x 720 video resolution</span></span></p>
<p><span data-ttu-id="719c6-129">Расширенный вид: до пяти видео с разрешением 640 x 360</span><span class="sxs-lookup"><span data-stu-id="719c6-129">Gallery View: Up to five 640 x 360 resolution videos</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="719c6-130">Средние</span><span class="sxs-lookup"><span data-stu-id="719c6-130">Medium</span></span></p></td>
<td><p><span data-ttu-id="719c6-131">Да</span><span class="sxs-lookup"><span data-stu-id="719c6-131">True</span></span></p></td>
<td><p><span data-ttu-id="719c6-132">Да</span><span class="sxs-lookup"><span data-stu-id="719c6-132">True</span></span></p></td>
<td><p><span data-ttu-id="719c6-133">1000</span><span class="sxs-lookup"><span data-stu-id="719c6-133">1000</span></span></p></td>
<td><p><span data-ttu-id="719c6-134">1000</span><span class="sxs-lookup"><span data-stu-id="719c6-134">1000</span></span></p></td>
<td><p><span data-ttu-id="719c6-135">Одноранговая передача: разрешение видео до 960 x 540</span><span class="sxs-lookup"><span data-stu-id="719c6-135">Peer-to-peer: Up to 960 x 540 video resolution</span></span></p>
<p><span data-ttu-id="719c6-136">Расширенный вид: до пяти видео с разрешением 424 x 240</span><span class="sxs-lookup"><span data-stu-id="719c6-136">Gallery View: Up to five 424 x 240 resolution videos</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="719c6-137">Минимальные</span><span class="sxs-lookup"><span data-stu-id="719c6-137">Minimum</span></span></p></td>
<td><p><span data-ttu-id="719c6-138">Верно</span><span class="sxs-lookup"><span data-stu-id="719c6-138">True</span></span></p></td>
<td><p><span data-ttu-id="719c6-139">False</span><span class="sxs-lookup"><span data-stu-id="719c6-139">False</span></span></p></td>
<td><p><span data-ttu-id="719c6-140">350</span><span class="sxs-lookup"><span data-stu-id="719c6-140">350</span></span></p></td>
<td><p><span data-ttu-id="719c6-141">350</span><span class="sxs-lookup"><span data-stu-id="719c6-141">350</span></span></p></td>
<td><p><span data-ttu-id="719c6-142">Одноранговая передача: разрешение видео до 424 x 240</span><span class="sxs-lookup"><span data-stu-id="719c6-142">Peer-to-peer: Up to 424 x 240 video resolution</span></span></p>
<p><span data-ttu-id="719c6-143">Расширенный вид: недоступен</span><span class="sxs-lookup"><span data-stu-id="719c6-143">Gallery View: Unavailable</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="719c6-144">Информацию, представленную в предыдущей таблице, можно использовать для развертывания новых функций конференц-связи «Видео в формате HD» и «Развернутый вид» для некоторых пользователей в организации с поддержкой другого разрешения для остальных пользователей.</span><span class="sxs-lookup"><span data-stu-id="719c6-144">You can use the information in the preceding table to deploy the new HD video and Gallery View video conferencing features for some users in your organization, while allowing different video resolutions for others.</span></span>

<span data-ttu-id="719c6-p103">В следующем примере администратор разворачивает новые функции передачи видео с максимальным качеством только для руководителей. Для сотрудников удаленного филиала с низкой пропускной способностью устанавливается только минимальное значение из приведенной выше таблицы. Для всех других сотрудников устанавливается значение «Хорошее» из приведенной выше таблицы</span><span class="sxs-lookup"><span data-stu-id="719c6-p103">In the following example, the administrator rolls out the new video features with the highest video quality available only to executives. For employees in a remote branch office that has low network capacity, only the minimum setting from the preceding table is deployed. For all other employees, the "Good" setting from the preceding table is deployed.</span></span>

<span data-ttu-id="719c6-p104">Чтобы выполнить развертывание новых функций для руководителей, администратор создает политику конференц-связи с именем ExecutiveVideo. Эта политика конференц-связи включает следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="719c6-p104">To roll out the new features to the executives, the administrator creates a conferencing policy named ExecutiveVideo. This conferencing policy has the following settings:</span></span>

  - <span data-ttu-id="719c6-150">для параметра VideoBitRateKB задано значение 8000 кбит/с;</span><span class="sxs-lookup"><span data-stu-id="719c6-150">VideoBitRateKB is set to 8000 Kbps</span></span>

  - <span data-ttu-id="719c6-151">для параметра TotalReceiveVideoBitRateKB задано значение 8000 кбит/с;</span><span class="sxs-lookup"><span data-stu-id="719c6-151">TotalReceiveVideoBitRateKB is set to 8000 Kbps</span></span>

  - <span data-ttu-id="719c6-152">для параметра AllowMultiview задано значение True;</span><span class="sxs-lookup"><span data-stu-id="719c6-152">AllowMultiview is set to True</span></span>

  - <span data-ttu-id="719c6-153">для параметра EnableMultiviewJoin задано значение True.</span><span class="sxs-lookup"><span data-stu-id="719c6-153">EnableMultiviewJoin is set to True</span></span>

<span data-ttu-id="719c6-p105">Для сотрудников филиала администратор создает политику конференц-связи с именем BranchOfficeVideo. Эта политика конференц-связи включает следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="719c6-p105">For employees in the branch office, the administrator creates a conferencing policy named BranchOfficeVideo. This conferencing policy has the following settings:</span></span>

  - <span data-ttu-id="719c6-156">для параметра VideoBitRateKB задано значение 350 кбит/с;</span><span class="sxs-lookup"><span data-stu-id="719c6-156">VideoBitRateKB is set to 350 Kbps</span></span>

  - <span data-ttu-id="719c6-157">для параметра TotalReceiveVideoBitRateKB задано значение 350 кбит/с;</span><span class="sxs-lookup"><span data-stu-id="719c6-157">TotalReceiveVideoBitRateKB is set to 350 Kbps</span></span>

  - <span data-ttu-id="719c6-158">для параметра AllowMultiview задано значение True;</span><span class="sxs-lookup"><span data-stu-id="719c6-158">AllowMultiview is set to True</span></span>

  - <span data-ttu-id="719c6-159">для параметра EnableMultiviewJoin задано значение False.</span><span class="sxs-lookup"><span data-stu-id="719c6-159">EnableMultiviewJoin is set to False</span></span>

<span data-ttu-id="719c6-p106">Для всех остальных сотрудников администратор создает политику конференц-связи с именем StandardVideo. Для этой политики конференц-связи установлены следующие значения:</span><span class="sxs-lookup"><span data-stu-id="719c6-p106">For all other employees, the administrator creates a conferencing policy named StandardVideo. This conferencing policy has the following settings:</span></span>

  - <span data-ttu-id="719c6-162">для параметра VideoBitRateKB задано значение 2500 кбит/с;</span><span class="sxs-lookup"><span data-stu-id="719c6-162">VideoBitRateKB is set to 2500 Kbps</span></span>

  - <span data-ttu-id="719c6-163">для параметра TotalReceiveVideoBitRateKB задано значение 2500 кбит/с;</span><span class="sxs-lookup"><span data-stu-id="719c6-163">TotalReceiveVideoBitRateKB is set to 2500 Kbps</span></span>

  - <span data-ttu-id="719c6-164">для параметра AllowMultiview задано значение True;</span><span class="sxs-lookup"><span data-stu-id="719c6-164">AllowMultiview is set to True</span></span>

  - <span data-ttu-id="719c6-165">для параметра EnableMultiviewJoin задано значение True.</span><span class="sxs-lookup"><span data-stu-id="719c6-165">EnableMultiviewJoin is set to True</span></span>

<span data-ttu-id="719c6-166">Администратор назначает политику конференц-связи пользователям следующим образом.</span><span class="sxs-lookup"><span data-stu-id="719c6-166">The administrator assigns conferencing policy to users as follows:</span></span>

  - <span data-ttu-id="719c6-167">Политика конференц-связи ExecutiveVideo назначается руководителям.</span><span class="sxs-lookup"><span data-stu-id="719c6-167">The ExecutiveVideo conferencing policy is assigned to the executives.</span></span>

  - <span data-ttu-id="719c6-168">Политика конференц-связи BranchOfficeVideo назначается всем остальным сотрудникам филиала.</span><span class="sxs-lookup"><span data-stu-id="719c6-168">The BranchOfficeVideo conferencing policy is assigned to all employees in the branch office.</span></span>

  - <span data-ttu-id="719c6-169">Политика конференц-связи StandardVideo назначается всем остальным сотрудникам.</span><span class="sxs-lookup"><span data-stu-id="719c6-169">The StandardVideo conferencing policy is assigned to all other employees.</span></span>

<span data-ttu-id="719c6-170">После назначения этих политик для пользователей будут доступны следующие возможности.</span><span class="sxs-lookup"><span data-stu-id="719c6-170">These conferencing policy assignments result in the following user experience:</span></span>

  - <span data-ttu-id="719c6-171">Все конференции, организованные любым пользователем, поддерживают функцию расширенного вида, но сотрудники филиала не могут ее использовать.</span><span class="sxs-lookup"><span data-stu-id="719c6-171">All conferences organized by any user support Gallery View, but employees in the branch office cannot experience Gallery View.</span></span>

  - <span data-ttu-id="719c6-172">Руководители могут передавать видео с разрешением 1920 x 1080 в формате «full HD» (при условии, что его поддерживает оборудование и сетевой канал) для любых двусторонних и многосторонних конференций, если их также поддерживают клиенты других участников.</span><span class="sxs-lookup"><span data-stu-id="719c6-172">For any two-party or multiparty conferences, executives can send 1920 x 1080 full HD video, if their hardware and network link supports it, and can receive 1920 x 1080 full HD video where the other participant clients support it.</span></span>

  - <span data-ttu-id="719c6-173">Сотрудники, которые не являются руководителями, просматривают видео с более низким (но все равно хорошим) разрешением, чем руководители, при участии в двусторонних или многосторонних конференциях.</span><span class="sxs-lookup"><span data-stu-id="719c6-173">Employees who are not executives experience lower resolutions than the executives in their two-party or multiparty conferences, but still get good resolution.</span></span>

  - <span data-ttu-id="719c6-174">Сотрудники, находящиеся в филиалах, будут получать хорошее качество видео в двух вызовах, когда Lync отображает размер окна видео по умолчанию; Однако если окно Lync развернуто на весь экран, разрешение экрана не увеличится.</span><span class="sxs-lookup"><span data-stu-id="719c6-174">Employees who are in the branch office will get good video quality in two-party calls when Lync displays the default video window size; however, if the Lync window is maximized to full screen, the video resolution will not increase.</span></span> <span data-ttu-id="719c6-175">При участии в многосторонних конференциях сотрудники филиала видят только одно активное видео.</span><span class="sxs-lookup"><span data-stu-id="719c6-175">For multiparty conferences, the employees in the branch office will see only one active video.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

