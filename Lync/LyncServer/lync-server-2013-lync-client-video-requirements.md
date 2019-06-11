---
title: 'Lync Server 2013: требования к клиентскому видеоролику Lync'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Lync client video requirements
ms:assetid: 8f68f4c2-3194-487c-bd2f-fbe71ba8ad70
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688132(v=OCS.15)
ms:contentKeyID: 49733731
ms.date: 01/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 56743abd386cb59b177806eed3d441aaf587ccce
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833930"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="lync-client-video-requirements-for-lync-server-2013"></a><span data-ttu-id="6347e-102">Требования к видео в Lync для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6347e-102">Lync client video requirements for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6347e-103">_**Тема последнего изменения:** 2016-01-29_</span><span class="sxs-lookup"><span data-stu-id="6347e-103">_**Topic Last Modified:** 2016-01-29_</span></span>

<span data-ttu-id="6347e-104">В этом разделе рассказывается о поддержке видео для видеозвонков Lync 2013 и описано, как определить ожидаемое качество видео для различных конфигураций компьютера, планшета и мобильных устройств.</span><span class="sxs-lookup"><span data-stu-id="6347e-104">This section describes video hardware support for Lync 2013 video calls and describes how to determine the expected video quality for various computer, tablet, and mobile device configurations.</span></span>

<div>

## <a name="windows-desktop-and-tablet-video-requirements-and-capabilities"></a><span data-ttu-id="6347e-105">Требования и возможности для настольных систем Windows и планшетных видео</span><span class="sxs-lookup"><span data-stu-id="6347e-105">Windows Desktop and Tablet Video Requirements and Capabilities</span></span>

<span data-ttu-id="6347e-106">Lync 2013 представляет аппаратное ускорение для кодирования и декодирования видео, основанное на стандарте H. 264/MPEG-4 части 10 расширенного кодирования видео.</span><span class="sxs-lookup"><span data-stu-id="6347e-106">Lync 2013 introduces hardware acceleration for video encoding and decoding based on the H.264/MPEG-4 Part 10 Advanced Video Coding standard.</span></span> <span data-ttu-id="6347e-107">Эта возможность позволяет компьютерам с более низкой скоростью ЦП кодировать и декодировать видео с более высоким разрешением.</span><span class="sxs-lookup"><span data-stu-id="6347e-107">This feature allows computers with lower CPU clock speeds to encode and decode higher resolution video.</span></span> <span data-ttu-id="6347e-108">Требования к видеоустройствам зависят от конфигурации компьютера и необходимого разрешения видео.</span><span class="sxs-lookup"><span data-stu-id="6347e-108">Video hardware requirements vary depending on the computer configuration and the video resolution wanted.</span></span>

<div>

## <a name="video-hardware-requirements"></a><span data-ttu-id="6347e-109">Требования к видеооборудованию</span><span class="sxs-lookup"><span data-stu-id="6347e-109">Video Hardware Requirements</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6347e-110">Функция</span><span class="sxs-lookup"><span data-stu-id="6347e-110">Feature</span></span></th>
<th><span data-ttu-id="6347e-111">Требование</span><span class="sxs-lookup"><span data-stu-id="6347e-111">Requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6347e-112">Аппаратное ускорение декодирования H.264 с помощью DirectX Video Acceleration (DXVA)</span><span class="sxs-lookup"><span data-stu-id="6347e-112">Hardware accelerated H.264 decoding using DirectX Video Acceleration (DXVA)</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="6347e-113">Графическая карта должна поддерживать DirectX 9.0 и работать в режиме декодирования DXVA2_ModeH264_VLD_NoFGT.</span><span class="sxs-lookup"><span data-stu-id="6347e-113">Graphics card must support DirectX 9.0 and must expose the DXVA2_ModeH264_VLD_NoFGT decoding mode.</span></span></p></li>
<li><p><span data-ttu-id="6347e-114">Должен быть установлен последний драйвер графической карты.</span><span class="sxs-lookup"><span data-stu-id="6347e-114">The latest graphics card driver must be installed.</span></span></p></li>
</ul>
<div>

> [!NOTE]  
> <span data-ttu-id="6347e-115">Подробные сведения о режимах декодирования можно <A href="http://go.microsoft.com/fwlink/p/?linkid=268530">http://go.microsoft.com/fwlink/p/?LinkId=268530</A>найти в разделе.</span><span class="sxs-lookup"><span data-stu-id="6347e-115">For details about decoding modes, see <A href="http://go.microsoft.com/fwlink/p/?linkid=268530">http://go.microsoft.com/fwlink/p/?LinkId=268530</A>.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6347e-116">Аппаратное ускорение кодирования H.264: требования к набору микросхем</span><span class="sxs-lookup"><span data-stu-id="6347e-116">Hardware accelerated H.264 encoding: Chipset Requirements</span></span></p></td>
<td><p><span data-ttu-id="6347e-117">Поддерживаются перечисленные ниже решения Intel для кодирования видео с аппаратным ускорением.</span><span class="sxs-lookup"><span data-stu-id="6347e-117">The following Intel hardware accelerated video encoding solutions are supported:</span></span></p>
<ul>
<li><p><span data-ttu-id="6347e-118">Вторая и третья графическая плата Intel HD 2000, 2500, 3000 и 4000 наборы микросхем (или более поздних версий) с интегрированными аппаратными кодировщиками.</span><span class="sxs-lookup"><span data-stu-id="6347e-118">Second and third generation Intel HD Graphics 2000, 2500, 3000, and 4000 chipsets (or later versions) with integrated hardware video encoders.</span></span> <span data-ttu-id="6347e-119">Требуется установка драйвера Intel HD Graphics 15.28.9.2884 или более поздней версии с перечисленными ниже компонентами</span><span class="sxs-lookup"><span data-stu-id="6347e-119">Installation of the Intel HD Graphics driver 15.28.9.2884 or the latest driver containing the following is required:</span></span></p>
<ul>
<li><p><span data-ttu-id="6347e-120">Драйвер дисплея 9.17.10.2884 или более поздней версии</span><span class="sxs-lookup"><span data-stu-id="6347e-120">Display driver 9.17.10.2884 or the latest driver</span></span></p></li>
<li><p><span data-ttu-id="6347e-121">Платформа HMFT 3.12.10.31 или последней версии</span><span class="sxs-lookup"><span data-stu-id="6347e-121">Hardware media foundation transform (HMFT) version 3.12.10.31 or the latest HMFT</span></span></p></li>
</ul></li>
</ul>
<p><span data-ttu-id="6347e-122">Поддерживаются следующие решения для кодирования видео с аппаратным ускорением AMD (требуется обновление CU1 для Lync Server 2013).</span><span class="sxs-lookup"><span data-stu-id="6347e-122">The following AMD hardware accelerated video encoding solutions are supported (requires CU1 Updates for Lync Server 2013):</span></span></p>
<ul>
<li><p><span data-ttu-id="6347e-p103">Модуль видеокодеков AMD Video Codec Engine, имеющийся в некоторых адаптерах дискретной графики, а также во встроенных блоках ускоренной обработки серии AMD A-Series Accelerated Processors. Должен быть установлен драйвер AMD Video Codec Engine 9.12.0.0 или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="6347e-p103">AMD Video Codec Engine, which is available in several discrete graphics cards and in integrated accelerated processing units of AMD A-Series Accelerated Processors. The AMD Video Codec Engine driver 9.12.0.0 or higher must be installed.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6347e-125">Аппаратное ускорение кодирования H.264: требования к камере</span><span class="sxs-lookup"><span data-stu-id="6347e-125">Hardware accelerated H.264 encoding: Camera Requirements</span></span></p></td>
<td><p><span data-ttu-id="6347e-126">Видеокамеры USB со встроенным аппаратным кодировщиком H.264, поддерживающие спецификацию USB Video Class (UVC) версии 1.5.</span><span class="sxs-lookup"><span data-stu-id="6347e-126">USB video cameras with integrated H.264 hardware encoder that conforms to the USB Video Class (UVC) specification version 1.5.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="6347e-127">Lync 2013 поддерживает камеры УВК 1,5 в Windows 8 или Windows 8,1, в том числе поддержка УВК 1,5.</span><span class="sxs-lookup"><span data-stu-id="6347e-127">Lync 2013 supports UVC 1.5 cameras with Windows 8 or Windows 8.1, which includes support for UVC 1.5.</span></span> <span data-ttu-id="6347e-128">Так как в Windows 7 не входит поддержка УВК 1,5, Lync 2013 рассматривает камеры УВК 1,5 как обычные камеры без поддержки аппаратной кодировки.</span><span class="sxs-lookup"><span data-stu-id="6347e-128">Because Windows 7 does not include support for UVC 1.5, Lync 2013 treats UVC 1.5 cameras as regular cameras with no hardware encoding support.</span></span>


</div></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="determining-h264-video-encoding-and-decoding-capabilities"></a><span data-ttu-id="6347e-129">Определение возможностей кодирования и декодирования видео в 264</span><span class="sxs-lookup"><span data-stu-id="6347e-129">Determining H.264 Video Encoding and Decoding Capabilities</span></span>

<span data-ttu-id="6347e-130">В общем случае максимальная производительность кодирования и декодирования для конкретной конфигурации компьютера определяется четырьмя основными факторами:</span><span class="sxs-lookup"><span data-stu-id="6347e-130">Generally, there are four major factors that determine the maximum encoding and decoding capability of a particular computer configuration:</span></span>

  - <span data-ttu-id="6347e-131">поддержка аппаратного ускорения декодирования с помощью DXVA;</span><span class="sxs-lookup"><span data-stu-id="6347e-131">Support for hardware accelerated decoding by using DXVA</span></span>

  - <span data-ttu-id="6347e-132">поддержка аппаратного ускорения кодирования;</span><span class="sxs-lookup"><span data-stu-id="6347e-132">Support for hardware accelerated encoding</span></span>

  - <span data-ttu-id="6347e-133">количество физических ядер;</span><span class="sxs-lookup"><span data-stu-id="6347e-133">Number of physical cores</span></span>

  - <span data-ttu-id="6347e-134">индекс производительности Windows (WEI).</span><span class="sxs-lookup"><span data-stu-id="6347e-134">Windows Experience Index (WEI)</span></span>

<span data-ttu-id="6347e-135">Средство оценки производительности WinSAT определяет индекс WEI.</span><span class="sxs-lookup"><span data-stu-id="6347e-135">The Windows System Assessment Tool (WinSAT) determines the WEI.</span></span> <span data-ttu-id="6347e-136">При запуске средства WinSAT создается формальный XML-документ. Оценка на компьютере в каталоге% WINDIR%\\с производительностью\\WinSAT\\с хранилищем хранилищ.</span><span class="sxs-lookup"><span data-stu-id="6347e-136">When you run the WinSAT tool, it generates a Formal.Assessment XML document on the computer in the %windir%\\Performance\\WinSAT\\DataStore directory.</span></span> <span data-ttu-id="6347e-137">В этом XML-файле представлены два показателя, на основании которых можно определить возможности кодирования и декодирования:</span><span class="sxs-lookup"><span data-stu-id="6347e-137">This XML file contains the following two scores that are of particular importance for determining encoding and decoding capabilities:</span></span>

  - <span data-ttu-id="6347e-138">значение VideoEncodeScore показывает производительность компьютера по программному кодированию видео;</span><span class="sxs-lookup"><span data-stu-id="6347e-138">The VideoEncodeScore indicates the software-based video encoding capability of the computer.</span></span>

  - <span data-ttu-id="6347e-139">значение GraphicsScore показывает производительность компьютера по кодированию видео с аппаратным ускорением.</span><span class="sxs-lookup"><span data-stu-id="6347e-139">The GraphicsScore value indicates the hardware accelerated encoding capability of the computer.</span></span>

<span data-ttu-id="6347e-p106">В следующих таблицах приводится максимальная производительность кодирования и декодирования для нескольких типов ПК в зависимости от поддержки аппаратного ускорения. Для разрешения 640x360 и выше максимальная поддерживаемая частота кадров составляет 30 кадров в секунду (кадр/с). Для разрешений ниже 640x360 максимальная поддерживаемая частота кадров составляет 15 кадр/с.</span><span class="sxs-lookup"><span data-stu-id="6347e-p106">The following three tables explain the maximum encoding and decoding capability for different PC types depending on what hardware acceleration they support. For resolutions of 640x360 and higher, the maximum supported frame rate is 30 frames per second (fps). For resolutions lower than 640x360, the maximum supported frame rate is 15 fps.</span></span>

### <a name="computer-without-dxva-and-without-hardware-accelerated-encoder"></a><span data-ttu-id="6347e-143">Компьютер без DXVA и без аппаратного ускорения кодирования</span><span class="sxs-lookup"><span data-stu-id="6347e-143">Computer Without DXVA And Without Hardware Accelerated Encoder</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6347e-144">Поддерживаемое разрешение кодировщика</span><span class="sxs-lookup"><span data-stu-id="6347e-144">Capable Encoder Resolution</span></span></th>
<th><span data-ttu-id="6347e-145">Поддерживаемое разрешение декодера</span><span class="sxs-lookup"><span data-stu-id="6347e-145">Capable Decoder Resolution</span></span></th>
<th><span data-ttu-id="6347e-146">Требование</span><span class="sxs-lookup"><span data-stu-id="6347e-146">Requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6347e-147">424x240</span><span class="sxs-lookup"><span data-stu-id="6347e-147">424x240</span></span></p></td>
<td><p><span data-ttu-id="6347e-148">424x240 (640x360 при 15 кадр/с только для приема)</span><span class="sxs-lookup"><span data-stu-id="6347e-148">424x240 (640x360 at 15fps for receive only scenarios)</span></span></p></td>
<td><p><span data-ttu-id="6347e-149">1 ядро и VideoEncodeScore ≥ 4.0</span><span class="sxs-lookup"><span data-stu-id="6347e-149">1 Core and VideoEncodeScore ≥ 4.0</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6347e-150">640x360</span><span class="sxs-lookup"><span data-stu-id="6347e-150">640x360</span></span></p></td>
<td><p><span data-ttu-id="6347e-151">640x360</span><span class="sxs-lookup"><span data-stu-id="6347e-151">640x360</span></span></p></td>
<td><p><span data-ttu-id="6347e-152">2 ядра и VideoEncodeScore ≥ 4.5</span><span class="sxs-lookup"><span data-stu-id="6347e-152">2 Cores and VideoEncodeScore ≥ 4.5</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6347e-153">640x360</span><span class="sxs-lookup"><span data-stu-id="6347e-153">640x360</span></span></p></td>
<td><p><span data-ttu-id="6347e-154">1280x720</span><span class="sxs-lookup"><span data-stu-id="6347e-154">1280x720</span></span></p></td>
<td><p><span data-ttu-id="6347e-155">2 ядра и VideoEncodeScore ≥ 4.5</span><span class="sxs-lookup"><span data-stu-id="6347e-155">2 Cores and VideoEncodeScore ≥ 4.5</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6347e-156">640x360</span><span class="sxs-lookup"><span data-stu-id="6347e-156">640x360</span></span></p></td>
<td><p><span data-ttu-id="6347e-157">1920x1080</span><span class="sxs-lookup"><span data-stu-id="6347e-157">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="6347e-158">4 ядра и VideoEncodeScore ≥ 4.5</span><span class="sxs-lookup"><span data-stu-id="6347e-158">4 Cores and VideoEncodeScore ≥ 4.5</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6347e-159">1280x720</span><span class="sxs-lookup"><span data-stu-id="6347e-159">1280x720</span></span></p></td>
<td><p><span data-ttu-id="6347e-160">1280x720</span><span class="sxs-lookup"><span data-stu-id="6347e-160">1280x720</span></span></p></td>
<td><p><span data-ttu-id="6347e-161">4 ядра и VideoEncodeScore ≥ 7.3</span><span class="sxs-lookup"><span data-stu-id="6347e-161">4 Cores and VideoEncodeScore ≥ 7.3</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6347e-162">1280x720</span><span class="sxs-lookup"><span data-stu-id="6347e-162">1280x720</span></span></p></td>
<td><p><span data-ttu-id="6347e-163">1920x1080</span><span class="sxs-lookup"><span data-stu-id="6347e-163">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="6347e-164">4 ядра и VideoEncodeScore ≥ 7.3</span><span class="sxs-lookup"><span data-stu-id="6347e-164">4 Cores and VideoEncodeScore ≥ 7.3</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6347e-165">1920x1080</span><span class="sxs-lookup"><span data-stu-id="6347e-165">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="6347e-166">1920x1080</span><span class="sxs-lookup"><span data-stu-id="6347e-166">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="6347e-167">Н/Д</span><span class="sxs-lookup"><span data-stu-id="6347e-167">N/A</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="computer-with-dxva-but-without-hardware-accelerated-encoder"></a><span data-ttu-id="6347e-168">Компьютер с DXVA, но без аппаратного ускорения кодирования</span><span class="sxs-lookup"><span data-stu-id="6347e-168">Computer With DXVA But Without Hardware Accelerated Encoder</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6347e-169">Поддерживаемое разрешение кодировщика</span><span class="sxs-lookup"><span data-stu-id="6347e-169">Capable Encoder Resolution</span></span></th>
<th><span data-ttu-id="6347e-170">Поддерживаемое разрешение декодера</span><span class="sxs-lookup"><span data-stu-id="6347e-170">Capable Decoder Resolution</span></span></th>
<th><span data-ttu-id="6347e-171">Требование</span><span class="sxs-lookup"><span data-stu-id="6347e-171">Requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6347e-172">424x240</span><span class="sxs-lookup"><span data-stu-id="6347e-172">424x240</span></span></p></td>
<td><p><span data-ttu-id="6347e-173">1920x1080</span><span class="sxs-lookup"><span data-stu-id="6347e-173">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="6347e-174">1 ядро и VideoEncodeScore ≥ 3.0</span><span class="sxs-lookup"><span data-stu-id="6347e-174">1 Core and VideoEncodeScore ≥ 3.0</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6347e-175">640x360</span><span class="sxs-lookup"><span data-stu-id="6347e-175">640x360</span></span></p></td>
<td><p><span data-ttu-id="6347e-176">1920x1080</span><span class="sxs-lookup"><span data-stu-id="6347e-176">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="6347e-177">2 ядра и VideoEncodeScore ≥ 4.5</span><span class="sxs-lookup"><span data-stu-id="6347e-177">2 Cores and VideoEncodeScore ≥ 4.5</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6347e-178">960x540</span><span class="sxs-lookup"><span data-stu-id="6347e-178">960x540</span></span></p></td>
<td><p><span data-ttu-id="6347e-179">1920x1080</span><span class="sxs-lookup"><span data-stu-id="6347e-179">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="6347e-180">2 ядра и VideoEncodeScore ≥ 6.0</span><span class="sxs-lookup"><span data-stu-id="6347e-180">2 Cores and VideoEncodeScore ≥ 6.0</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6347e-181">1280x720</span><span class="sxs-lookup"><span data-stu-id="6347e-181">1280x720</span></span></p></td>
<td><p><span data-ttu-id="6347e-182">1920x1080</span><span class="sxs-lookup"><span data-stu-id="6347e-182">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="6347e-183">4 ядра и VideoEncodeScore ≥ 6.7</span><span class="sxs-lookup"><span data-stu-id="6347e-183">4 Cores and VideoEncodeScore ≥ 6.7</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6347e-184">1920x1080</span><span class="sxs-lookup"><span data-stu-id="6347e-184">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="6347e-185">1920x1080</span><span class="sxs-lookup"><span data-stu-id="6347e-185">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="6347e-186">4 ядра и VideoEncodeScore ≥ 8.2</span><span class="sxs-lookup"><span data-stu-id="6347e-186">4 Cores and VideoEncodeScore ≥ 8.2</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="6347e-p107">В Windows 7 максимальное значение показателя WinSAT составляет 7,9, поэтому такая производительность кодирования для компьютера без аппаратного ускорения может быть достигнута только в Windows 8 или Windows 8.1, где максимальное значение показателя WinSAT составляет 9,9.</span><span class="sxs-lookup"><span data-stu-id="6347e-p107">The WinSAT score on Windows 7 is limited to a maximum of 7.9. Therefore, the encoding capability for a computer without a hardware accelerated encoder can only be achieved on Windows 8 or Windows 8.1, where the maximum WinSAT score is 9.9.</span></span>



</div>

### <a name="computer-with-dxva-and-with-intel-hd-graphics-hardware-accelerated-encoder"></a><span data-ttu-id="6347e-189">Компьютер с DXVA и с аппаратным ускорителем кодирования Intel HD Graphics</span><span class="sxs-lookup"><span data-stu-id="6347e-189">Computer With DXVA And With Intel HD Graphics Hardware Accelerated Encoder</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6347e-190">Поддерживаемое разрешение кодировщика</span><span class="sxs-lookup"><span data-stu-id="6347e-190">Capable Encoder Resolution</span></span></th>
<th><span data-ttu-id="6347e-191">Поддерживаемое разрешение декодера</span><span class="sxs-lookup"><span data-stu-id="6347e-191">Capable Decoder Resolution</span></span></th>
<th><span data-ttu-id="6347e-192">Требование</span><span class="sxs-lookup"><span data-stu-id="6347e-192">Requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6347e-193">1280x720</span><span class="sxs-lookup"><span data-stu-id="6347e-193">1280x720</span></span></p></td>
<td><p><span data-ttu-id="6347e-194">1920x1080</span><span class="sxs-lookup"><span data-stu-id="6347e-194">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="6347e-195">Все графические карты Intel HD Graphics второго и третьего поколения</span><span class="sxs-lookup"><span data-stu-id="6347e-195">All 2nd and 3rd generation Intel HD Graphics</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6347e-196">1920x1080</span><span class="sxs-lookup"><span data-stu-id="6347e-196">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="6347e-197">1920x1080</span><span class="sxs-lookup"><span data-stu-id="6347e-197">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="6347e-198">Графические карты Intel HD Graphics второго и третьего поколения и GraphicsScore ≥ 5.0</span><span class="sxs-lookup"><span data-stu-id="6347e-198">2nd and 3rd generation Intel HD Graphics and GraphicsScore ≥ 5.0</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<div>

## <a name="mobile-device-video-capabilities"></a><span data-ttu-id="6347e-199">Видео о возможностях мобильных устройств</span><span class="sxs-lookup"><span data-stu-id="6347e-199">Mobile Device Video Capabilities</span></span>

<span data-ttu-id="6347e-200">В следующей таблице описываются максимальные возможности видеосвязи для поддерживаемых мобильных устройств.</span><span class="sxs-lookup"><span data-stu-id="6347e-200">The following table describes the maximum video capabilities for supported mobile devices.</span></span> <span data-ttu-id="6347e-201">Дополнительные сведения о поддержке мобильных устройств можно найти [в разделе Планирование мобильных клиентов в Lync Server 2013](lync-server-2013-planning-for-mobile-clients.md).</span><span class="sxs-lookup"><span data-stu-id="6347e-201">For more information about mobile device support, see [Planning for mobile clients in Lync Server 2013](lync-server-2013-planning-for-mobile-clients.md).</span></span>


<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6347e-202">Функция</span><span class="sxs-lookup"><span data-stu-id="6347e-202">Feature</span></span></th>
<th><span data-ttu-id="6347e-203">Windows Phone</span><span class="sxs-lookup"><span data-stu-id="6347e-203">Windows Phone</span></span></th>
<th><span data-ttu-id="6347e-204">iPhone</span><span class="sxs-lookup"><span data-stu-id="6347e-204">iPhone</span></span></th>
<th><span data-ttu-id="6347e-205">iPad</span><span class="sxs-lookup"><span data-stu-id="6347e-205">iPad</span></span></th>
<th><span data-ttu-id="6347e-206">Android</span><span class="sxs-lookup"><span data-stu-id="6347e-206">Android</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6347e-207">Максимальное разрешение при кодировании H.264</span><span class="sxs-lookup"><span data-stu-id="6347e-207">H.264 encoding maximum resolution</span></span></p></td>
<td><p><span data-ttu-id="6347e-208">VGA</span><span class="sxs-lookup"><span data-stu-id="6347e-208">VGA</span></span></p></td>
<td><p><span data-ttu-id="6347e-209">QVGA: iPhone 4S</span><span class="sxs-lookup"><span data-stu-id="6347e-209">QVGA: iPhone 4S</span></span></p>
<p><span data-ttu-id="6347e-210">VGA: iPhone 5</span><span class="sxs-lookup"><span data-stu-id="6347e-210">VGA: iPhone 5</span></span></p>
<p><span data-ttu-id="6347e-211">720p: iPhone 5S и более новые модели</span><span class="sxs-lookup"><span data-stu-id="6347e-211">720p: iPhone 5S and later</span></span></p></td>
<td><p><span data-ttu-id="6347e-212">VGA: iPad 2 и более новые модели/iPad mini 1 и более новые модели</span><span class="sxs-lookup"><span data-stu-id="6347e-212">VGA: iPad 2 and later/iPad mini 1 and later</span></span></p>
<p><span data-ttu-id="6347e-213">720p: iPad Air/iPad mini 2/iPad Pro и более новые модели</span><span class="sxs-lookup"><span data-stu-id="6347e-213">720p: iPad Air/iPad mini 2/iPad Pro and later</span></span></p></td>
<td><p><span data-ttu-id="6347e-214">До VGA (в зависимости от модели устройства)</span><span class="sxs-lookup"><span data-stu-id="6347e-214">Up to VGA depending on device model</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6347e-215">Максимальное разрешение при декодировании H.264</span><span class="sxs-lookup"><span data-stu-id="6347e-215">H.264 decoding maximum resolution</span></span></p></td>
<td><p><span data-ttu-id="6347e-216">VGA</span><span class="sxs-lookup"><span data-stu-id="6347e-216">VGA</span></span></p></td>
<td><p><span data-ttu-id="6347e-217">QVGA: iPhone 4S</span><span class="sxs-lookup"><span data-stu-id="6347e-217">QVGA: iPhone 4S</span></span></p>
<p><span data-ttu-id="6347e-218">VGA: iPhone 5</span><span class="sxs-lookup"><span data-stu-id="6347e-218">VGA: iPhone 5</span></span></p>
<p><span data-ttu-id="6347e-219">720p: iPhone 5S и более новые модели</span><span class="sxs-lookup"><span data-stu-id="6347e-219">720p: iPhone 5S and later</span></span></p></td>
<td><p><span data-ttu-id="6347e-220">VGA: iPad 2 и более новые модели/iPad mini 1 и более новые модели</span><span class="sxs-lookup"><span data-stu-id="6347e-220">VGA: iPad 2 and later/iPad mini 1 and later</span></span></p>
<p><span data-ttu-id="6347e-221">720p: iPad Air/iPad mini 2/iPad Pro и более новые модели</span><span class="sxs-lookup"><span data-stu-id="6347e-221">720p: iPad Air/iPad mini 2/iPad Pro and later</span></span></p></td>
<td><p><span data-ttu-id="6347e-222">До VGA (в зависимости от модели устройства)</span><span class="sxs-lookup"><span data-stu-id="6347e-222">Up to VGA depending on device model</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

