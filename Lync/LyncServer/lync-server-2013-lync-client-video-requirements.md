---
title: 'Lync Server 2013: требования к видео для клиента Lync'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync client video requirements
ms:assetid: 8f68f4c2-3194-487c-bd2f-fbe71ba8ad70
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688132(v=OCS.15)
ms:contentKeyID: 49733731
ms.date: 01/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c15eb698babcce1cd104dd7206c037b95d402992
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42186352"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="lync-client-video-requirements-for-lync-server-2013"></a><span data-ttu-id="73faa-102">Требования к видео для клиента Lync для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="73faa-102">Lync client video requirements for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="73faa-103">_**Последнее изменение темы:** 2016-01-29_</span><span class="sxs-lookup"><span data-stu-id="73faa-103">_**Topic Last Modified:** 2016-01-29_</span></span>

<span data-ttu-id="73faa-104">В этом разделе описывается поддержка видеоустройств для видеовызовов Lync 2013 и описывается, как определить ожидаемое качество видео для различных конфигураций компьютера, планшета и мобильного устройства.</span><span class="sxs-lookup"><span data-stu-id="73faa-104">This section describes video hardware support for Lync 2013 video calls and describes how to determine the expected video quality for various computer, tablet, and mobile device configurations.</span></span>

<div>

## <a name="windows-desktop-and-tablet-video-requirements-and-capabilities"></a><span data-ttu-id="73faa-105">Требования и возможности для настольных ПК и видео на планшете Windows</span><span class="sxs-lookup"><span data-stu-id="73faa-105">Windows Desktop and Tablet Video Requirements and Capabilities</span></span>

<span data-ttu-id="73faa-106">Lync 2013 содержит аппаратное ускорение для кодирования и декодирования видео в зависимости от стандарта H. 264/MPEG-4 в части 10 Advanced Video кодирования.</span><span class="sxs-lookup"><span data-stu-id="73faa-106">Lync 2013 introduces hardware acceleration for video encoding and decoding based on the H.264/MPEG-4 Part 10 Advanced Video Coding standard.</span></span> <span data-ttu-id="73faa-107">Эта возможность позволяет компьютерам с более низкой скоростью ЦП кодировать и декодировать видео с более высоким разрешением.</span><span class="sxs-lookup"><span data-stu-id="73faa-107">This feature allows computers with lower CPU clock speeds to encode and decode higher resolution video.</span></span> <span data-ttu-id="73faa-108">Требования к видеоустройствам зависят от конфигурации компьютера и необходимого разрешения видео.</span><span class="sxs-lookup"><span data-stu-id="73faa-108">Video hardware requirements vary depending on the computer configuration and the video resolution wanted.</span></span>

<div>

## <a name="video-hardware-requirements"></a><span data-ttu-id="73faa-109">Требования к видеоустройствам</span><span class="sxs-lookup"><span data-stu-id="73faa-109">Video Hardware Requirements</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="73faa-110">Функция</span><span class="sxs-lookup"><span data-stu-id="73faa-110">Feature</span></span></th>
<th><span data-ttu-id="73faa-111">Требование</span><span class="sxs-lookup"><span data-stu-id="73faa-111">Requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="73faa-112">Аппаратное ускорение декодирования H.264 с помощью DirectX Video Acceleration (DXVA)</span><span class="sxs-lookup"><span data-stu-id="73faa-112">Hardware accelerated H.264 decoding using DirectX Video Acceleration (DXVA)</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="73faa-113">Графическая карта должна поддерживать DirectX 9.0 и работать в режиме декодирования DXVA2_ModeH264_VLD_NoFGT.</span><span class="sxs-lookup"><span data-stu-id="73faa-113">Graphics card must support DirectX 9.0 and must expose the DXVA2_ModeH264_VLD_NoFGT decoding mode.</span></span></p></li>
<li><p><span data-ttu-id="73faa-114">Должен быть установлен последний драйвер графической карты.</span><span class="sxs-lookup"><span data-stu-id="73faa-114">The latest graphics card driver must be installed.</span></span></p></li>
</ul>
<div>

> [!NOTE]  
> <span data-ttu-id="73faa-115">Подробные сведения о режимах декодирования приведены <A href="https://go.microsoft.com/fwlink/p/?linkid=268530">https://go.microsoft.com/fwlink/p/?LinkId=268530</A>в разделе.</span><span class="sxs-lookup"><span data-stu-id="73faa-115">For details about decoding modes, see <A href="https://go.microsoft.com/fwlink/p/?linkid=268530">https://go.microsoft.com/fwlink/p/?LinkId=268530</A>.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="73faa-116">Аппаратное ускорение кодирования H.264: требования к набору микросхем</span><span class="sxs-lookup"><span data-stu-id="73faa-116">Hardware accelerated H.264 encoding: Chipset Requirements</span></span></p></td>
<td><p><span data-ttu-id="73faa-117">Поддерживаются следующие решения для кодирования видео с аппаратным ускорением Intel:</span><span class="sxs-lookup"><span data-stu-id="73faa-117">The following Intel hardware accelerated video encoding solutions are supported:</span></span></p>
<ul>
<li><p><span data-ttu-id="73faa-118">Наборы микросхем второго и третьего поколения Intel HD Graphics 2000, 2500, 3000 и 4000 (или более поздние версии) со встроенными аппаратными кодировщиками видео.</span><span class="sxs-lookup"><span data-stu-id="73faa-118">Second and third generation Intel HD Graphics 2000, 2500, 3000, and 4000 chipsets (or later versions) with integrated hardware video encoders.</span></span> <span data-ttu-id="73faa-119">Необходимо установить драйвер 15.28.9.2884 для графической подсистемы Intel HD или последнюю версию драйвера, включающую следующее:</span><span class="sxs-lookup"><span data-stu-id="73faa-119">Installation of the Intel HD Graphics driver 15.28.9.2884 or the latest driver containing the following is required:</span></span></p>
<ul>
<li><p><span data-ttu-id="73faa-120">Драйвер дисплея 9.17.10.2884 или последний драйвер</span><span class="sxs-lookup"><span data-stu-id="73faa-120">Display driver 9.17.10.2884 or the latest driver</span></span></p></li>
<li><p><span data-ttu-id="73faa-121">Преобразование оборудования Media Foundation (ХМФТ) версии 3.12.10.31 или последней версии ХМФТ</span><span class="sxs-lookup"><span data-stu-id="73faa-121">Hardware media foundation transform (HMFT) version 3.12.10.31 or the latest HMFT</span></span></p></li>
</ul></li>
</ul>
<p><span data-ttu-id="73faa-122">Поддерживаются следующие решения для кодирования видео с аппаратным ускорением AMD (требуется обновление CU1 для Lync Server 2013):</span><span class="sxs-lookup"><span data-stu-id="73faa-122">The following AMD hardware accelerated video encoding solutions are supported (requires CU1 Updates for Lync Server 2013):</span></span></p>
<ul>
<li><p><span data-ttu-id="73faa-123">Модуль видеокодека AMD, доступный на нескольких отдельных графических платах и в интегрированных процессорах с ускоренной обработкой процессоров AMD серии с ускорением серии AMD.</span><span class="sxs-lookup"><span data-stu-id="73faa-123">AMD Video Codec Engine, which is available in several discrete graphics cards and in integrated accelerated processing units of AMD A-Series Accelerated Processors.</span></span> <span data-ttu-id="73faa-124">Должен быть установлен драйвер ядра видеокодека AMD 9.12.0.0 или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="73faa-124">The AMD Video Codec Engine driver 9.12.0.0 or higher must be installed.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="73faa-125">Аппаратное ускорение кодирования H.264: требования к камере</span><span class="sxs-lookup"><span data-stu-id="73faa-125">Hardware accelerated H.264 encoding: Camera Requirements</span></span></p></td>
<td><p><span data-ttu-id="73faa-126">Видеокамеры USB со встроенным аппаратным кодировщиком H.264, поддерживающие спецификацию USB Video Class (UVC) версии 1.5.</span><span class="sxs-lookup"><span data-stu-id="73faa-126">USB video cameras with integrated H.264 hardware encoder that conforms to the USB Video Class (UVC) specification version 1.5.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="73faa-127">Lync 2013 поддерживает камеры UVC 1,5 с Windows 8 или Windows 8,1, в том числе поддержка UVC 1,5.</span><span class="sxs-lookup"><span data-stu-id="73faa-127">Lync 2013 supports UVC 1.5 cameras with Windows 8 or Windows 8.1, which includes support for UVC 1.5.</span></span> <span data-ttu-id="73faa-128">Поскольку в Windows 7 не включена поддержка UVC 1.5, Lync 2013 работает с камерами UVC 1.5 как с обычными камерами без поддержки аппаратного кодирования.</span><span class="sxs-lookup"><span data-stu-id="73faa-128">Because Windows 7 does not include support for UVC 1.5, Lync 2013 treats UVC 1.5 cameras as regular cameras with no hardware encoding support.</span></span>


</div></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="determining-h264-video-encoding-and-decoding-capabilities"></a><span data-ttu-id="73faa-129">Определение возможностей кодирования и декодирования видео H.264</span><span class="sxs-lookup"><span data-stu-id="73faa-129">Determining H.264 Video Encoding and Decoding Capabilities</span></span>

<span data-ttu-id="73faa-130">В общем случае максимальная производительность кодирования и декодирования для конкретной конфигурации компьютера определяется четырьмя основными факторами:</span><span class="sxs-lookup"><span data-stu-id="73faa-130">Generally, there are four major factors that determine the maximum encoding and decoding capability of a particular computer configuration:</span></span>

  - <span data-ttu-id="73faa-131">поддержка аппаратного ускорения декодирования с помощью DXVA;</span><span class="sxs-lookup"><span data-stu-id="73faa-131">Support for hardware accelerated decoding by using DXVA</span></span>

  - <span data-ttu-id="73faa-132">поддержка аппаратного ускорения кодирования;</span><span class="sxs-lookup"><span data-stu-id="73faa-132">Support for hardware accelerated encoding</span></span>

  - <span data-ttu-id="73faa-133">количество физических ядер;</span><span class="sxs-lookup"><span data-stu-id="73faa-133">Number of physical cores</span></span>

  - <span data-ttu-id="73faa-134">индекс производительности Windows (WEI).</span><span class="sxs-lookup"><span data-stu-id="73faa-134">Windows Experience Index (WEI)</span></span>

<span data-ttu-id="73faa-135">Средство оценки производительности WinSAT определяет индекс WEI.</span><span class="sxs-lookup"><span data-stu-id="73faa-135">The Windows System Assessment Tool (WinSAT) determines the WEI.</span></span> <span data-ttu-id="73faa-136">При запуске средства WinSAT создается формальный XML-документ с оценкой на компьютере в каталоге хранилища данных% WINDIR%\\с производительностью\\WinSAT\\.</span><span class="sxs-lookup"><span data-stu-id="73faa-136">When you run the WinSAT tool, it generates a Formal.Assessment XML document on the computer in the %windir%\\Performance\\WinSAT\\DataStore directory.</span></span> <span data-ttu-id="73faa-137">В этом XML-файле представлены два показателя, на основании которых можно определить возможности кодирования и декодирования:</span><span class="sxs-lookup"><span data-stu-id="73faa-137">This XML file contains the following two scores that are of particular importance for determining encoding and decoding capabilities:</span></span>

  - <span data-ttu-id="73faa-138">значение VideoEncodeScore показывает производительность компьютера по программному кодированию видео;</span><span class="sxs-lookup"><span data-stu-id="73faa-138">The VideoEncodeScore indicates the software-based video encoding capability of the computer.</span></span>

  - <span data-ttu-id="73faa-139">значение GraphicsScore показывает производительность компьютера по кодированию видео с аппаратным ускорением.</span><span class="sxs-lookup"><span data-stu-id="73faa-139">The GraphicsScore value indicates the hardware accelerated encoding capability of the computer.</span></span>

<span data-ttu-id="73faa-p106">В следующих таблицах приводится максимальная производительность кодирования и декодирования для нескольких типов ПК в зависимости от поддержки аппаратного ускорения. Для разрешения 640x360 и выше максимальная поддерживаемая частота кадров составляет 30 кадров в секунду (кадр/с). Для разрешений ниже 640x360 максимальная поддерживаемая частота кадров составляет 15 кадр/с.</span><span class="sxs-lookup"><span data-stu-id="73faa-p106">The following three tables explain the maximum encoding and decoding capability for different PC types depending on what hardware acceleration they support. For resolutions of 640x360 and higher, the maximum supported frame rate is 30 frames per second (fps). For resolutions lower than 640x360, the maximum supported frame rate is 15 fps.</span></span>

### <a name="computer-without-dxva-and-without-hardware-accelerated-encoder"></a><span data-ttu-id="73faa-143">Компьютер без DXVA и без аппаратного ускорения кодирования</span><span class="sxs-lookup"><span data-stu-id="73faa-143">Computer Without DXVA And Without Hardware Accelerated Encoder</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="73faa-144">Поддерживаемое разрешение кодировщика</span><span class="sxs-lookup"><span data-stu-id="73faa-144">Capable Encoder Resolution</span></span></th>
<th><span data-ttu-id="73faa-145">Поддерживаемое разрешение декодера</span><span class="sxs-lookup"><span data-stu-id="73faa-145">Capable Decoder Resolution</span></span></th>
<th><span data-ttu-id="73faa-146">Требование</span><span class="sxs-lookup"><span data-stu-id="73faa-146">Requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="73faa-147">424x240</span><span class="sxs-lookup"><span data-stu-id="73faa-147">424x240</span></span></p></td>
<td><p><span data-ttu-id="73faa-148">424x240 (640x360 при 15 кадр/с только для приема)</span><span class="sxs-lookup"><span data-stu-id="73faa-148">424x240 (640x360 at 15fps for receive only scenarios)</span></span></p></td>
<td><p><span data-ttu-id="73faa-149">1 ядро и VideoEncodeScore ≥ 4,0</span><span class="sxs-lookup"><span data-stu-id="73faa-149">1 Core and VideoEncodeScore ≥ 4.0</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="73faa-150">640x360</span><span class="sxs-lookup"><span data-stu-id="73faa-150">640x360</span></span></p></td>
<td><p><span data-ttu-id="73faa-151">640x360</span><span class="sxs-lookup"><span data-stu-id="73faa-151">640x360</span></span></p></td>
<td><p><span data-ttu-id="73faa-152">2 ядра и VideoEncodeScore ≥ 4,5</span><span class="sxs-lookup"><span data-stu-id="73faa-152">2 Cores and VideoEncodeScore ≥ 4.5</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="73faa-153">640x360</span><span class="sxs-lookup"><span data-stu-id="73faa-153">640x360</span></span></p></td>
<td><p><span data-ttu-id="73faa-154">1280X720</span><span class="sxs-lookup"><span data-stu-id="73faa-154">1280x720</span></span></p></td>
<td><p><span data-ttu-id="73faa-155">2 ядра и VideoEncodeScore ≥ 4,5</span><span class="sxs-lookup"><span data-stu-id="73faa-155">2 Cores and VideoEncodeScore ≥ 4.5</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="73faa-156">640x360</span><span class="sxs-lookup"><span data-stu-id="73faa-156">640x360</span></span></p></td>
<td><p><span data-ttu-id="73faa-157">1920x1080</span><span class="sxs-lookup"><span data-stu-id="73faa-157">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="73faa-158">4 ядра и VideoEncodeScore ≥ 4,5</span><span class="sxs-lookup"><span data-stu-id="73faa-158">4 Cores and VideoEncodeScore ≥ 4.5</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="73faa-159">1280X720</span><span class="sxs-lookup"><span data-stu-id="73faa-159">1280x720</span></span></p></td>
<td><p><span data-ttu-id="73faa-160">1280X720</span><span class="sxs-lookup"><span data-stu-id="73faa-160">1280x720</span></span></p></td>
<td><p><span data-ttu-id="73faa-161">4 ядра и VideoEncodeScore ≥ 7,3</span><span class="sxs-lookup"><span data-stu-id="73faa-161">4 Cores and VideoEncodeScore ≥ 7.3</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="73faa-162">1280X720</span><span class="sxs-lookup"><span data-stu-id="73faa-162">1280x720</span></span></p></td>
<td><p><span data-ttu-id="73faa-163">1920x1080</span><span class="sxs-lookup"><span data-stu-id="73faa-163">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="73faa-164">4 ядра и VideoEncodeScore ≥ 7,3</span><span class="sxs-lookup"><span data-stu-id="73faa-164">4 Cores and VideoEncodeScore ≥ 7.3</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="73faa-165">1920x1080</span><span class="sxs-lookup"><span data-stu-id="73faa-165">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="73faa-166">1920x1080</span><span class="sxs-lookup"><span data-stu-id="73faa-166">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="73faa-167">Н/Д</span><span class="sxs-lookup"><span data-stu-id="73faa-167">N/A</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="computer-with-dxva-but-without-hardware-accelerated-encoder"></a><span data-ttu-id="73faa-168">Компьютер с DXVA, но без аппаратного ускорения кодирования</span><span class="sxs-lookup"><span data-stu-id="73faa-168">Computer With DXVA But Without Hardware Accelerated Encoder</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="73faa-169">Поддерживаемое разрешение кодировщика</span><span class="sxs-lookup"><span data-stu-id="73faa-169">Capable Encoder Resolution</span></span></th>
<th><span data-ttu-id="73faa-170">Поддерживаемое разрешение декодера</span><span class="sxs-lookup"><span data-stu-id="73faa-170">Capable Decoder Resolution</span></span></th>
<th><span data-ttu-id="73faa-171">Требование</span><span class="sxs-lookup"><span data-stu-id="73faa-171">Requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="73faa-172">424x240</span><span class="sxs-lookup"><span data-stu-id="73faa-172">424x240</span></span></p></td>
<td><p><span data-ttu-id="73faa-173">1920x1080</span><span class="sxs-lookup"><span data-stu-id="73faa-173">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="73faa-174">1 ядро и VideoEncodeScore ≥ 3,0</span><span class="sxs-lookup"><span data-stu-id="73faa-174">1 Core and VideoEncodeScore ≥ 3.0</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="73faa-175">640x360</span><span class="sxs-lookup"><span data-stu-id="73faa-175">640x360</span></span></p></td>
<td><p><span data-ttu-id="73faa-176">1920x1080</span><span class="sxs-lookup"><span data-stu-id="73faa-176">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="73faa-177">2 ядра и VideoEncodeScore ≥ 4,5</span><span class="sxs-lookup"><span data-stu-id="73faa-177">2 Cores and VideoEncodeScore ≥ 4.5</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="73faa-178">960x540</span><span class="sxs-lookup"><span data-stu-id="73faa-178">960x540</span></span></p></td>
<td><p><span data-ttu-id="73faa-179">1920x1080</span><span class="sxs-lookup"><span data-stu-id="73faa-179">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="73faa-180">2 ядра и VideoEncodeScore ≥ 6,0</span><span class="sxs-lookup"><span data-stu-id="73faa-180">2 Cores and VideoEncodeScore ≥ 6.0</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="73faa-181">1280X720</span><span class="sxs-lookup"><span data-stu-id="73faa-181">1280x720</span></span></p></td>
<td><p><span data-ttu-id="73faa-182">1920x1080</span><span class="sxs-lookup"><span data-stu-id="73faa-182">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="73faa-183">4 ядра и VideoEncodeScore ≥ 6,7</span><span class="sxs-lookup"><span data-stu-id="73faa-183">4 Cores and VideoEncodeScore ≥ 6.7</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="73faa-184">1920x1080</span><span class="sxs-lookup"><span data-stu-id="73faa-184">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="73faa-185">1920x1080</span><span class="sxs-lookup"><span data-stu-id="73faa-185">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="73faa-186">4 ядра и VideoEncodeScore ≥ 8,2</span><span class="sxs-lookup"><span data-stu-id="73faa-186">4 Cores and VideoEncodeScore ≥ 8.2</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="73faa-187">Оценка WinSAT в Windows 7 ограничена до 7,9.</span><span class="sxs-lookup"><span data-stu-id="73faa-187">The WinSAT score on Windows 7 is limited to a maximum of 7.9.</span></span> <span data-ttu-id="73faa-188">Таким образом, возможность кодирования для компьютера без аппаратного ускорения кодировщика может быть достигнута только в Windows 8 или Windows 8,1, где максимальный показатель WinSAT равен 9,9.</span><span class="sxs-lookup"><span data-stu-id="73faa-188">Therefore, the encoding capability for a computer without a hardware accelerated encoder can only be achieved on Windows 8 or Windows 8.1, where the maximum WinSAT score is 9.9.</span></span>



</div>

### <a name="computer-with-dxva-and-with-intel-hd-graphics-hardware-accelerated-encoder"></a><span data-ttu-id="73faa-189">Компьютер с DXVA и с аппаратным ускорителем кодирования Intel HD Graphics</span><span class="sxs-lookup"><span data-stu-id="73faa-189">Computer With DXVA And With Intel HD Graphics Hardware Accelerated Encoder</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="73faa-190">Поддерживаемое разрешение кодировщика</span><span class="sxs-lookup"><span data-stu-id="73faa-190">Capable Encoder Resolution</span></span></th>
<th><span data-ttu-id="73faa-191">Поддерживаемое разрешение декодера</span><span class="sxs-lookup"><span data-stu-id="73faa-191">Capable Decoder Resolution</span></span></th>
<th><span data-ttu-id="73faa-192">Требование</span><span class="sxs-lookup"><span data-stu-id="73faa-192">Requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="73faa-193">1280X720</span><span class="sxs-lookup"><span data-stu-id="73faa-193">1280x720</span></span></p></td>
<td><p><span data-ttu-id="73faa-194">1920x1080</span><span class="sxs-lookup"><span data-stu-id="73faa-194">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="73faa-195">Все графические карты Intel HD Graphics второго и третьего поколения</span><span class="sxs-lookup"><span data-stu-id="73faa-195">All 2nd and 3rd generation Intel HD Graphics</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="73faa-196">1920x1080</span><span class="sxs-lookup"><span data-stu-id="73faa-196">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="73faa-197">1920x1080</span><span class="sxs-lookup"><span data-stu-id="73faa-197">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="73faa-198">Графические карты Intel HD Graphics второго и третьего поколения и GraphicsScore ≥ 5,0</span><span class="sxs-lookup"><span data-stu-id="73faa-198">2nd and 3rd generation Intel HD Graphics and GraphicsScore ≥ 5.0</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<div>

## <a name="mobile-device-video-capabilities"></a><span data-ttu-id="73faa-199">Возможности видео мобильных устройств</span><span class="sxs-lookup"><span data-stu-id="73faa-199">Mobile Device Video Capabilities</span></span>

<span data-ttu-id="73faa-200">В следующей таблице описаны максимальные возможности видео для поддерживаемых мобильных устройств.</span><span class="sxs-lookup"><span data-stu-id="73faa-200">The following table describes the maximum video capabilities for supported mobile devices.</span></span> <span data-ttu-id="73faa-201">Дополнительные сведения о поддержке мобильных устройств приведены в статье [планирование для мобильных клиентов в Lync Server 2013](lync-server-2013-planning-for-mobile-clients.md).</span><span class="sxs-lookup"><span data-stu-id="73faa-201">For more information about mobile device support, see [Planning for mobile clients in Lync Server 2013](lync-server-2013-planning-for-mobile-clients.md).</span></span>


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
<th><span data-ttu-id="73faa-202">Функция</span><span class="sxs-lookup"><span data-stu-id="73faa-202">Feature</span></span></th>
<th><span data-ttu-id="73faa-203">Windows Phone</span><span class="sxs-lookup"><span data-stu-id="73faa-203">Windows Phone</span></span></th>
<th><span data-ttu-id="73faa-204">iPhone</span><span class="sxs-lookup"><span data-stu-id="73faa-204">iPhone</span></span></th>
<th><span data-ttu-id="73faa-205">iPad</span><span class="sxs-lookup"><span data-stu-id="73faa-205">iPad</span></span></th>
<th><span data-ttu-id="73faa-206">Android</span><span class="sxs-lookup"><span data-stu-id="73faa-206">Android</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="73faa-207">Максимальное разрешение кодирования H. 264</span><span class="sxs-lookup"><span data-stu-id="73faa-207">H.264 encoding maximum resolution</span></span></p></td>
<td><p><span data-ttu-id="73faa-208">АДАПТЕР</span><span class="sxs-lookup"><span data-stu-id="73faa-208">VGA</span></span></p></td>
<td><p><span data-ttu-id="73faa-209">КВГА: iPhone 4S</span><span class="sxs-lookup"><span data-stu-id="73faa-209">QVGA: iPhone 4S</span></span></p>
<p><span data-ttu-id="73faa-210">VGA: iPhone 5</span><span class="sxs-lookup"><span data-stu-id="73faa-210">VGA: iPhone 5</span></span></p>
<p><span data-ttu-id="73faa-211">720p: iPhone 5S и более поздних версий</span><span class="sxs-lookup"><span data-stu-id="73faa-211">720p: iPhone 5S and later</span></span></p></td>
<td><p><span data-ttu-id="73faa-212">VGA: iPad 2 и более поздних версий/iPad Mini 1 и более поздних версий</span><span class="sxs-lookup"><span data-stu-id="73faa-212">VGA: iPad 2 and later/iPad mini 1 and later</span></span></p>
<p><span data-ttu-id="73faa-213">720p: iPad Air/iPad Mini 2/iPad Pro и более поздние версии</span><span class="sxs-lookup"><span data-stu-id="73faa-213">720p: iPad Air/iPad mini 2/iPad Pro and later</span></span></p></td>
<td><p><span data-ttu-id="73faa-214">До VGA в зависимости от модели устройства</span><span class="sxs-lookup"><span data-stu-id="73faa-214">Up to VGA depending on device model</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="73faa-215">Максимальное разрешение при декодировании H. 264</span><span class="sxs-lookup"><span data-stu-id="73faa-215">H.264 decoding maximum resolution</span></span></p></td>
<td><p><span data-ttu-id="73faa-216">АДАПТЕР</span><span class="sxs-lookup"><span data-stu-id="73faa-216">VGA</span></span></p></td>
<td><p><span data-ttu-id="73faa-217">КВГА: iPhone 4S</span><span class="sxs-lookup"><span data-stu-id="73faa-217">QVGA: iPhone 4S</span></span></p>
<p><span data-ttu-id="73faa-218">VGA: iPhone 5</span><span class="sxs-lookup"><span data-stu-id="73faa-218">VGA: iPhone 5</span></span></p>
<p><span data-ttu-id="73faa-219">720p: iPhone 5S и более поздних версий</span><span class="sxs-lookup"><span data-stu-id="73faa-219">720p: iPhone 5S and later</span></span></p></td>
<td><p><span data-ttu-id="73faa-220">VGA: iPad 2 и более поздних версий/iPad Mini 1 и более поздних версий</span><span class="sxs-lookup"><span data-stu-id="73faa-220">VGA: iPad 2 and later/iPad mini 1 and later</span></span></p>
<p><span data-ttu-id="73faa-221">720p: iPad Air/iPad Mini 2/iPad Pro и более поздние версии</span><span class="sxs-lookup"><span data-stu-id="73faa-221">720p: iPad Air/iPad mini 2/iPad Pro and later</span></span></p></td>
<td><p><span data-ttu-id="73faa-222">До VGA в зависимости от модели устройства</span><span class="sxs-lookup"><span data-stu-id="73faa-222">Up to VGA depending on device model</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

