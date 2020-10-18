---
title: 'Lync Server 2013: отчет об устройстве'
description: 'Lync Server 2013: отчет об устройстве.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Device Report
ms:assetid: f42e4d60-699b-4870-8bb5-13b51bb6eb2b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615049(v=OCS.15)
ms:contentKeyID: 48185807
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a8bff8e973d5c3e2d96c18992a2a2d917d4deb1c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48575125"
---
# <a name="device-report-in-lync-server-2013"></a><span data-ttu-id="65a1c-103">Отчет по устройствам в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="65a1c-103">Device Report in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="65a1c-104">_**Последнее изменение темы:** 2013-11-12_</span><span class="sxs-lookup"><span data-stu-id="65a1c-104">_**Topic Last Modified:** 2013-11-12_</span></span>

<span data-ttu-id="65a1c-105">Отчет по устройствам можно скорее назвать отчетом по микрофонам и динамикам, так как отчет по устройствам используется для получения показателей, относящихся к вызовам (включая проценты вызовов низкого качества, эхосигналы и время коммутации вызовов) и сгруппированных по микрофонам и динамикам, которые использовались в ходе вызова.</span><span class="sxs-lookup"><span data-stu-id="65a1c-105">The Device Report might be better titled the Microphone and Speakers Report; that's because the Device Report retrieves call-related metrics (such as poor call percentage, echo, and voice switch time) grouped by the microphones and speakers used in the call.</span></span> <span data-ttu-id="65a1c-106">Если вы заинтересованы в IP-телефонах (также называемых «устройствами»), используйте отчет по [IP-телефонам в Lync Server 2013](lync-server-2013-ip-phone-inventory-report.md) .</span><span class="sxs-lookup"><span data-stu-id="65a1c-106">If you are interested in IP phones (also commonly referred to as "devices"), use the [IP Phone Inventory Report in Lync Server 2013](lync-server-2013-ip-phone-inventory-report.md) instead.</span></span>

<span data-ttu-id="65a1c-p102">Отчет по устройствам крайне полезен для администраторов, так как он позволяет определить, не поступает ли на определенный тип устройств большее количество вызовов низкого качества, чем на другие устройства. В свою очередь, это может влиять на любые решения, которые необходимо принимать при покупке новых устройств или замене существующих.</span><span class="sxs-lookup"><span data-stu-id="65a1c-p102">The Device Report is extremely useful for administrators in determining if a specific type of device is experiencing high volumes of poor quality calls than others. In turn, this could influence any decisions you must make when it comes time to buy new devices or to replace existing devices.</span></span>

<span data-ttu-id="65a1c-p103">По умолчанию информация, отображаемая в отчете по устройствам, также основывается на показателях микрофона (устройства захвата) и динамиков/наушников (устройство обработки), используемых в ходе вызова. Например, предположим, что несколько пользователей используют следующее устройство захвата и устройство обработки: По умолчанию информация, отображаемая в отчете по устройствам, также основывается на показателях микрофона (устройства захвата) и динамиков/наушников (устройство обработки), используемых в ходе вызова. Например, предположим, что несколько пользователей используют следующее устройство захвата и устройство обработки:</span><span class="sxs-lookup"><span data-stu-id="65a1c-p103">By default, the information displayed in the Device Report is also based on the microphone (the capture device) and speakers/headset (the render device) used in the call. For example, suppose you have several users who use the following capture device and the following render device: By default, the information displayed in the Device Report is also based on the microphone (the capture device) and speakers/headset (the render device) used in the call. For example, suppose you have several users who use the following capture device and the following render device:</span></span>

  - <span data-ttu-id="65a1c-112">Устройство захвата — микрофон (SoundMAX Integrated Digital HD Audio)</span><span class="sxs-lookup"><span data-stu-id="65a1c-112">Capture device -- Microphone (SoundMAX Integrated Digital HD Audio)</span></span>

  - <span data-ttu-id="65a1c-113">Устройство обработки — наушники гарнитуры (Microsoft LifeChat LX-3000)</span><span class="sxs-lookup"><span data-stu-id="65a1c-113">Render device -- Headset Earphone (Microsoft LifeChat LX-3000)</span></span>

<span data-ttu-id="65a1c-114">Если эти пользователи в общей сложности выполнили 254 вызова, в отчете будет отображаться запись, аналогичная следующей:</span><span class="sxs-lookup"><span data-stu-id="65a1c-114">If those users made a total of 254 calls you'll see an entry like this in the report:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="65a1c-115">Устройства захвата</span><span class="sxs-lookup"><span data-stu-id="65a1c-115">Capture device</span></span></th>
<th><span data-ttu-id="65a1c-116">Устройства обработки</span><span class="sxs-lookup"><span data-stu-id="65a1c-116">Render device</span></span></th>
<th><span data-ttu-id="65a1c-117">Громкость вызова</span><span class="sxs-lookup"><span data-stu-id="65a1c-117">Call volume</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="65a1c-118">Микрофон (SoundMAX Integrated Digital HD Audio)</span><span class="sxs-lookup"><span data-stu-id="65a1c-118">Microphone (SoundMAX Integrated Digital HD Audio)</span></span></p></td>
<td><p><span data-ttu-id="65a1c-119">Наушники гарнитуры (Microsoft LifeChat LX-3000)</span><span class="sxs-lookup"><span data-stu-id="65a1c-119">Headset Earphone (Microsoft LifeChat LX-3000)</span></span></p></td>
<td><p><span data-ttu-id="65a1c-120">254</span><span class="sxs-lookup"><span data-stu-id="65a1c-120">254</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="65a1c-p104">Теперь предположим, что определенное количество пользователей используют одно и то же устройство захвата, но разные устройства обработки. В этом случае отчет будет включать вторую строку для данного уникального сочетания устройства захвата и устройства обработки.</span><span class="sxs-lookup"><span data-stu-id="65a1c-p104">Now, suppose you have a number of users who use that same capture device but a different render device. In that case, you'll have a second line entry in the report, one for that unique combination of capture device and render device:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="65a1c-123">Устройства захвата</span><span class="sxs-lookup"><span data-stu-id="65a1c-123">Capture device</span></span></th>
<th><span data-ttu-id="65a1c-124">Устройства обработки</span><span class="sxs-lookup"><span data-stu-id="65a1c-124">Render device</span></span></th>
<th><span data-ttu-id="65a1c-125">Громкость вызова</span><span class="sxs-lookup"><span data-stu-id="65a1c-125">Call volume</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="65a1c-126">Микрофон (SoundMAX Integrated Digital HD Audio)</span><span class="sxs-lookup"><span data-stu-id="65a1c-126">Microphone (SoundMAX Integrated Digital HD Audio)</span></span></p></td>
<td><p><span data-ttu-id="65a1c-127">Наушники гарнитуры (Microsoft LifeChat LX-3000)</span><span class="sxs-lookup"><span data-stu-id="65a1c-127">Headset Earphone (Microsoft LifeChat LX-3000)</span></span></p></td>
<td><p><span data-ttu-id="65a1c-128">254</span><span class="sxs-lookup"><span data-stu-id="65a1c-128">254</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="65a1c-129">Микрофон (SoundMAX Integrated Digital HD Audio)</span><span class="sxs-lookup"><span data-stu-id="65a1c-129">Microphone (SoundMAX Integrated Digital HD Audio)</span></span></p></td>
<td><p><span data-ttu-id="65a1c-130">Динамики (SoundMAX Integrated Digital HD Audio)</span><span class="sxs-lookup"><span data-stu-id="65a1c-130">Speakers (SoundMAX Integrated Digital HD Audio)</span></span></p></td>
<td><p><span data-ttu-id="65a1c-131">319</span><span class="sxs-lookup"><span data-stu-id="65a1c-131">319</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="65a1c-p105">Если вам требуются сводные показатели для конкретного устройства (например, для устройства захвата SoundMAX вне зависимости от используемого устройства обработки), выберите нужный вариант в раскрывающемся списке «Тип устройства» (либо устройство захвата, либо устройство обработки). При выборе устройства захвата в этом примере результат будет аналогичен следующему:</span><span class="sxs-lookup"><span data-stu-id="65a1c-p105">If you would rather see combined totals for a given device (for example, for the SoundMAX capture device, regardless of the render device used), select the appropriate option from the Device type dropdown list (either Capture device or Render device). If you select Capture device in this example, that will give you output similar to this:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="65a1c-134">Устройства захвата</span><span class="sxs-lookup"><span data-stu-id="65a1c-134">Capture device</span></span></th>
<th><span data-ttu-id="65a1c-135">Громкость вызова</span><span class="sxs-lookup"><span data-stu-id="65a1c-135">Call volume</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="65a1c-136">Микрофон (SoundMAX Integrated Digital HD Audio)</span><span class="sxs-lookup"><span data-stu-id="65a1c-136">Microphone (SoundMAX Integrated Digital HD Audio)</span></span></p></td>
<td><p><span data-ttu-id="65a1c-137">573</span><span class="sxs-lookup"><span data-stu-id="65a1c-137">573</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="accessing-the-device-report"></a><span data-ttu-id="65a1c-138">Доступ к отчету по устройствам</span><span class="sxs-lookup"><span data-stu-id="65a1c-138">Accessing the Device Report</span></span>

<span data-ttu-id="65a1c-139">Доступ к отчету по устройствам обычно осуществляется с главной страницы отчетов наблюдения.</span><span class="sxs-lookup"><span data-stu-id="65a1c-139">The Device Report is typically accessed from the Monitoring Reports home page.</span></span> <span data-ttu-id="65a1c-140">Тем не менее, если вы просматриваете [подробный отчет по вызовам в Lync Server 2013](lync-server-2013-call-detail-report.md) , вы можете перейти к отчету по устройствам для определенного устройства, щелкнув один из следующих показателей:</span><span class="sxs-lookup"><span data-stu-id="65a1c-140">However, if you are viewing the [Call Detail Report in Lync Server 2013](lync-server-2013-call-detail-report.md) you can drill down to the Device Report for a specific device by clicking either of the following metrics:</span></span>

  - <span data-ttu-id="65a1c-141">Устройства захвата</span><span class="sxs-lookup"><span data-stu-id="65a1c-141">Capture Device</span></span>

  - <span data-ttu-id="65a1c-142">Устройства обработки</span><span class="sxs-lookup"><span data-stu-id="65a1c-142">Render Device</span></span>

<span data-ttu-id="65a1c-143">В отчете по устройствам можно перейти к [отчету по списку обзвона в Lync Server 2013](lync-server-2013-call-list-report.md) , щелкнув один из следующих показателей:</span><span class="sxs-lookup"><span data-stu-id="65a1c-143">From the Device Report you can drill down to the [Call List Report in Lync Server 2013](lync-server-2013-call-list-report.md) by clicking either of the following metrics:</span></span>

  - <span data-ttu-id="65a1c-144">Объем звонков</span><span class="sxs-lookup"><span data-stu-id="65a1c-144">Call volume</span></span>

  - <span data-ttu-id="65a1c-145">Процент звонков низкого качества</span><span class="sxs-lookup"><span data-stu-id="65a1c-145">Poor call percentage</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-device-report"></a><span data-ttu-id="65a1c-146">Эффективное использование отчета по устройству</span><span class="sxs-lookup"><span data-stu-id="65a1c-146">Making the Best Use of the Device Report</span></span>

<span data-ttu-id="65a1c-147">Отчет по устройствам является крайне подробным с точки зрения названий устройств; например, предположим, что у вас есть следующие устройства захвата:</span><span class="sxs-lookup"><span data-stu-id="65a1c-147">When it comes to device names, the Device Report is extremely detailed; for example, suppose you have the following capture devices:</span></span>

  - <span data-ttu-id="65a1c-148">Микрофон Aastra 3002 (2- Aastra 3002)</span><span class="sxs-lookup"><span data-stu-id="65a1c-148">Aastra 3002 Microphone (2- Aastra 3002)</span></span>

  - <span data-ttu-id="65a1c-149">Микрофон Aastra 3002 (3- Aastra 3002)</span><span class="sxs-lookup"><span data-stu-id="65a1c-149">Aastra 3002 Microphone (3- Aastra 3002)</span></span>

  - <span data-ttu-id="65a1c-150">Микрофон Aastra 3002 (Aastra 3002)</span><span class="sxs-lookup"><span data-stu-id="65a1c-150">Aastra 3002 Microphone (Aastra 3002)</span></span>

  - <span data-ttu-id="65a1c-151">Aastra 6725ip</span><span class="sxs-lookup"><span data-stu-id="65a1c-151">Aastra 6725ip</span></span>

  - <span data-ttu-id="65a1c-152">Микрофон Aastra 6725ip (10- Aastra 6725ip)</span><span class="sxs-lookup"><span data-stu-id="65a1c-152">Aastra 6725ip Microphone (10- Aastra 6725ip)</span></span>

  - <span data-ttu-id="65a1c-153">Микрофон Aastra 6725ip (10- Aastra 6725ip)-V0</span><span class="sxs-lookup"><span data-stu-id="65a1c-153">Aastra 6725ip Microphone (10- Aastra 6725ip)-V0</span></span>

  - <span data-ttu-id="65a1c-154">Микрофон Aastra 6725ip (2- Aastra 6725ip)</span><span class="sxs-lookup"><span data-stu-id="65a1c-154">Aastra 6725ip Microphone (2- Aastra 6725ip)</span></span>

  - <span data-ttu-id="65a1c-155">Микрофон Aastra 6725ip (3- Aastra 6725ip)</span><span class="sxs-lookup"><span data-stu-id="65a1c-155">Aastra 6725ip Microphone (3- Aastra 6725ip)</span></span>

  - <span data-ttu-id="65a1c-156">Микрофон Aastra 6725ip (4- Aastra 6725ip)</span><span class="sxs-lookup"><span data-stu-id="65a1c-156">Aastra 6725ip Microphone (4- Aastra 6725ip)</span></span>

  - <span data-ttu-id="65a1c-157">Микрофон Aastra 6725ip (5- Aastra 6725ip)</span><span class="sxs-lookup"><span data-stu-id="65a1c-157">Aastra 6725ip Microphone (5- Aastra 6725ip)</span></span>

  - <span data-ttu-id="65a1c-158">Микрофон Aastra 6725ip (6- Aastra 6725ip)</span><span class="sxs-lookup"><span data-stu-id="65a1c-158">Aastra 6725ip Microphone (6- Aastra 6725ip)</span></span>

  - <span data-ttu-id="65a1c-159">Микрофон Aastra 6725ip (7- Aastra 6725ip)</span><span class="sxs-lookup"><span data-stu-id="65a1c-159">Aastra 6725ip Microphone (7- Aastra 6725ip)</span></span>

  - <span data-ttu-id="65a1c-160">Микрофон Aastra 6725ip (9- Aastra 6725ip)</span><span class="sxs-lookup"><span data-stu-id="65a1c-160">Aastra 6725ip Microphone (9- Aastra 6725ip)</span></span>

  - <span data-ttu-id="65a1c-161">Микрофон Aastra 6725ip (9- Aastra 6725ip)-V0</span><span class="sxs-lookup"><span data-stu-id="65a1c-161">Aastra 6725ip Microphone (9- Aastra 6725ip)-V0</span></span>

  - <span data-ttu-id="65a1c-162">Микрофон Aastra 6725ip (Aastra 6725ip)</span><span class="sxs-lookup"><span data-stu-id="65a1c-162">Aastra 6725ip Microphone (Aastra 6725ip)</span></span>

  - <span data-ttu-id="65a1c-163">Микрофон Aastra 6725ip (Aastra 6725ip)-V0</span><span class="sxs-lookup"><span data-stu-id="65a1c-163">Aastra 6725ip Microphone (Aastra 6725ip)-V0</span></span>

  - <span data-ttu-id="65a1c-164">Микрофон Aastra 6725ip (аудиоустройство USB)</span><span class="sxs-lookup"><span data-stu-id="65a1c-164">Aastra 6725ip Microphone (USB Audio Device)</span></span>

  - <span data-ttu-id="65a1c-165">Микрофон Aastra 6725ip (аудиоустройство USB)-V0</span><span class="sxs-lookup"><span data-stu-id="65a1c-165">Aastra 6725ip Microphone (USB Audio Device)-V0</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="65a1c-166">Имейте в виду, что при использовании локализованных версий Lync Server 2013 могут не совпадать имена устройств записи.</span><span class="sxs-lookup"><span data-stu-id="65a1c-166">Keep in mind that capture device names might not be the same if you are running localized versions of Lync Server 2013.</span></span> <span data-ttu-id="65a1c-167">Устройство с именем «Aastra 6725ip Microphone (Aastra 6725ip)-V0» на английском языке (США) может называться по-другому на французском или испанском языке.</span><span class="sxs-lookup"><span data-stu-id="65a1c-167">A device named Aastra 6725ip Microphone (Aastra 6725ip)-V0 in US English could have a different name in French or Spanish.</span></span>



</div>

<span data-ttu-id="65a1c-168">Часто вам требуется этот уровень детализации; в других случаях, однако, вас может интересовать только количество вызовов, выполненных с помощью какого-либо микрофона Aastra, вне зависимости от номера модели.</span><span class="sxs-lookup"><span data-stu-id="65a1c-168">Often times you'll want that level of detail; at other times, however, you might only be interested in how many calls use any Aastra microphone, regardless of model number.</span></span> <span data-ttu-id="65a1c-169">Один из способов получения таких сведений — экспорт данных отчета об устройствах в Microsoft Excel, а затем сохранение этих данных в файле с разделителями-запятыми (например, C: \\ Data \\ devices \_Report.csv).</span><span class="sxs-lookup"><span data-stu-id="65a1c-169">One way to get information like that is to export the Device Report data to Microsoft Excel and then save that data to a comma-separated values file (for example, C:\\Data\\Devices\_Report.csv).</span></span> <span data-ttu-id="65a1c-170">Затем можно использовать набор аналогичных команд для импорта CSV-файла в Windows PowerShell и получения полного числа вызовов, выполненных с помощью устройства захвата Aastra:</span><span class="sxs-lookup"><span data-stu-id="65a1c-170">You can then use a set of commands similar to these to import the .CSV file into Windows PowerShell and report back the total number of calls made using an Aastra capture device:</span></span>

    $devices = Import-Csv "C:\Data\Device_Report.csv
    $sum = $devices | Where-Object {$_."Capture device" -match "Aastra"}
    $sum | foreach-object {[Int]$x = [Int]$x + [Int]$_."call volume"}
    $x

<span data-ttu-id="65a1c-p109">Это приведет к возврату одного значения, которое представляет собой общее число вызовов, выполненных с помощью устройства захвата Aastra. Например:</span><span class="sxs-lookup"><span data-stu-id="65a1c-p109">That will return a single value representing the total number of calls made using an Aastra capture device. For example:</span></span>

    384

</div>

<div>

## <a name="filters"></a><span data-ttu-id="65a1c-173">Фильтры</span><span class="sxs-lookup"><span data-stu-id="65a1c-173">Filters</span></span>

<span data-ttu-id="65a1c-p110">Фильтры предоставляют способ возврата более точного набора данных в соответствии с заданными критериями или просмотра возвращенных данных другими способами. Например, отчет по устройствам позволяет выполнить фильтрацию по таким критериям, как тип вызова (то есть был ли данный вызов вызовом клиента), конференц-вызов или вызов по телефонной сети общего пользования (ТСОП). Можно также выбрать способ группировки данных. В этом случае устройства группируются по часу, дню, неделе или месяце.</span><span class="sxs-lookup"><span data-stu-id="65a1c-p110">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. For example, the Device Report enables you to filter on such things as call type (that is, was the call a client call), a conference call, or a public switched telephone network (PSTN) call. You can also choose how data should be grouped. In this case, devices are grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="65a1c-178">В следующей таблице перечислены фильтры, которые можно использовать с отчетом по устройствам.</span><span class="sxs-lookup"><span data-stu-id="65a1c-178">The following table lists the filters that you can use with the Device Report.</span></span>

### <a name="device-report-filters"></a><span data-ttu-id="65a1c-179">Фильтры отчета по устройствам</span><span class="sxs-lookup"><span data-stu-id="65a1c-179">Device Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="65a1c-180">Имя</span><span class="sxs-lookup"><span data-stu-id="65a1c-180">Name</span></span></th>
<th><span data-ttu-id="65a1c-181">Описание</span><span class="sxs-lookup"><span data-stu-id="65a1c-181">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="65a1c-182"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="65a1c-182"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="65a1c-p111">Дата и время начала диапазона. Чтобы просмотреть данные по часам, введите дату и время начала в следующем формате:</span><span class="sxs-lookup"><span data-stu-id="65a1c-p111">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="65a1c-185">7/7/2012 13:00.</span><span class="sxs-lookup"><span data-stu-id="65a1c-185">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="65a1c-p112">Если не указать время начала, автоматически будет выбрано время 00:00 указанного дня. Чтобы просмотреть данные по дням, просто введите дату:</span><span class="sxs-lookup"><span data-stu-id="65a1c-p112">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="65a1c-188">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="65a1c-188">7/7/2012</span></span></p>
<p><span data-ttu-id="65a1c-189">Для просмотра по неделям или по месяцам введите дату, выпадающую на любой день недели или месяца, который вы хотите просмотреть (это необязательно должен быть первый день недели или месяца):</span><span class="sxs-lookup"><span data-stu-id="65a1c-189">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="65a1c-190">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="65a1c-190">7/3/2012</span></span></p>
<p><span data-ttu-id="65a1c-191">Неделя всегда начинается с воскресения и заканчивается субботой.</span><span class="sxs-lookup"><span data-stu-id="65a1c-191">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="65a1c-192"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="65a1c-192"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="65a1c-p113">Дата и время окончания диапазона. Чтобы просмотреть данные по часам, введите дату и время окончания в следующем формате:</span><span class="sxs-lookup"><span data-stu-id="65a1c-p113">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="65a1c-195">7/7/2012 13:00.</span><span class="sxs-lookup"><span data-stu-id="65a1c-195">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="65a1c-p114">Если не указать время окончания, автоматически будет выбрано время 00:00 указанного дня. Чтобы просмотреть данные по дням, просто введите дату:</span><span class="sxs-lookup"><span data-stu-id="65a1c-p114">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="65a1c-198">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="65a1c-198">7/7/2012</span></span></p>
<p><span data-ttu-id="65a1c-199">Для просмотра по неделям или по месяцам введите дату, выпадающую на любой день недели или месяца, который вы хотите просмотреть (это необязательно должен быть первый день недели или месяца):</span><span class="sxs-lookup"><span data-stu-id="65a1c-199">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="65a1c-200">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="65a1c-200">7/3/2012</span></span></p>
<p><span data-ttu-id="65a1c-201">Неделя всегда начинается в воскресенье и заканчивается в субботу.</span><span class="sxs-lookup"><span data-stu-id="65a1c-201">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="65a1c-202"><strong>Причина голосовой коммутации</strong></span><span class="sxs-lookup"><span data-stu-id="65a1c-202"><strong>Voice switch cause</strong></span></span></p></td>
<td><p><span data-ttu-id="65a1c-p115">Причина, по которой вызов был переведен в полудуплексный режим в целях предотвращения эха. В полудуплексном режиме взаимодействие может осуществляться только в одном направлении в каждый определенный момент времени аналогично тому, как пользователи по очереди слушают и говорят при связи по рации. Выберите один из следующих вариантов:</span><span class="sxs-lookup"><span data-stu-id="65a1c-p115">Reason why a call had to be placed into half duplex mode in order to prevent echo. In half duplex mode, communication can travel in only one direction at a time, similar to the way users take turns when communicating with a walkie-talkie. Select one of the following:</span></span></p>
<dl>
<dt><span></span></dt>
<dd><p><span data-ttu-id="65a1c-206">Ко</span><span class="sxs-lookup"><span data-stu-id="65a1c-206">[All]</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="65a1c-207">Нет</span><span class="sxs-lookup"><span data-stu-id="65a1c-207">None</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="65a1c-208">Плохая метка времени</span><span class="sxs-lookup"><span data-stu-id="65a1c-208">Bad timestamp</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="65a1c-209">Эхо</span><span class="sxs-lookup"><span data-stu-id="65a1c-209">Echo</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="65a1c-210">DNLP (динамический нелинейный процессор)</span><span class="sxs-lookup"><span data-stu-id="65a1c-210">DNLP (dynamic nonlinear processor)</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="65a1c-211">Низкая сложность</span><span class="sxs-lookup"><span data-stu-id="65a1c-211">Low complexity</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="65a1c-212">Плохо состояния устройства</span><span class="sxs-lookup"><span data-stu-id="65a1c-212">Bad device state</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="65a1c-213">Эхо после AEC (акустическое эхоподавление)</span><span class="sxs-lookup"><span data-stu-id="65a1c-213">Post-AEC echo (acoustic echo cancellation)</span></span></p>
</dd>
</dl></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="65a1c-214"><strong>Причина эхо</strong></span><span class="sxs-lookup"><span data-stu-id="65a1c-214"><strong>Echo cause</strong></span></span></p></td>
<td><p><span data-ttu-id="65a1c-p116">Причина, по которой в ходе вызова эхосигналы превысили допустимый уровень (Когда речь идет о телекоммуникациях, под эхо подразумевается отражение звука, то есть явление, аналогичное тому, которое возникает, когда вы кричите в глубокий колодец.) Выберите один из следующих вариантов:</span><span class="sxs-lookup"><span data-stu-id="65a1c-p116">Reason why echo above the accepted level was detected in a call. (In telecommunications, echo is a reflection of sound, the same phenomenon you will hear if you yell down to the bottom of a well.) Select one of the following:</span></span></p>
<dl>
<dt><span></span></dt>
<dd><p><span data-ttu-id="65a1c-217">Ко</span><span class="sxs-lookup"><span data-stu-id="65a1c-217">[All]</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="65a1c-218">Нет</span><span class="sxs-lookup"><span data-stu-id="65a1c-218">None</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="65a1c-219">Плохая метка времени</span><span class="sxs-lookup"><span data-stu-id="65a1c-219">Bad timestamp</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="65a1c-220">Эхо после AEC (акустическое эхоподавление)</span><span class="sxs-lookup"><span data-stu-id="65a1c-220">Post-AEC echo (acoustic echo cancellation)</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="65a1c-221">ANLP (адаптивный нелинейный процессор)</span><span class="sxs-lookup"><span data-stu-id="65a1c-221">ANLP (adaptive nonlinear processor)</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="65a1c-222">DNLP (динамический нелинейный процессор)</span><span class="sxs-lookup"><span data-stu-id="65a1c-222">DNLP (dynamic nonlinear processor)</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="65a1c-223">Отсечка микрофона</span><span class="sxs-lookup"><span data-stu-id="65a1c-223">Microphone clipping</span></span></p>
</dd>
</dl></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="65a1c-224"><strong> Тип вызова </strong></span><span class="sxs-lookup"><span data-stu-id="65a1c-224"><strong>Call type</strong></span></span></p></td>
<td><p><span data-ttu-id="65a1c-p117">Определяет тип выполненного вызова. Выберите один из следующих вариантов:</span><span class="sxs-lookup"><span data-stu-id="65a1c-p117">Indicates the type of call that was made. Select one of the following:</span></span></p>
<dl>
<dt><span></span></dt>
<dd><p><span data-ttu-id="65a1c-227">Ко</span><span class="sxs-lookup"><span data-stu-id="65a1c-227">[All]</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="65a1c-228">Вызов клиента</span><span class="sxs-lookup"><span data-stu-id="65a1c-228">Client call</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="65a1c-229">Вызов ТСОП</span><span class="sxs-lookup"><span data-stu-id="65a1c-229">PSTN call</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="65a1c-230">Конференц-связь</span><span class="sxs-lookup"><span data-stu-id="65a1c-230">Conference call</span></span></p>
</dd>
</dl></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="65a1c-231"><strong> Тип доступа </strong></span><span class="sxs-lookup"><span data-stu-id="65a1c-231"><strong>Access type</strong></span></span></p></td>
<td><p><span data-ttu-id="65a1c-p118">Указывает, вошел ли клиент из внутренней или внешней сети при выполнении звонка. Выберите одно из значений:</span><span class="sxs-lookup"><span data-stu-id="65a1c-p118">Indicates whether the client was logged on to the internal network or the external network when the call was placed. Select one of the following:</span></span></p>
<dl>
<dt><span></span></dt>
<dd><p><span data-ttu-id="65a1c-234">Ко</span><span class="sxs-lookup"><span data-stu-id="65a1c-234">[All]</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="65a1c-235">Внутренний</span><span class="sxs-lookup"><span data-stu-id="65a1c-235">Internal</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="65a1c-236">Внешний</span><span class="sxs-lookup"><span data-stu-id="65a1c-236">External</span></span></p>
</dd>
</dl></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="65a1c-237"><strong>Тип сети</strong></span><span class="sxs-lookup"><span data-stu-id="65a1c-237"><strong>Network type</strong></span></span></p></td>
<td><p><span data-ttu-id="65a1c-p119">Указание типа сети, к которой был подключен клиент при выполнении вызова. Выберите одно из значений:</span><span class="sxs-lookup"><span data-stu-id="65a1c-p119">Indicates the type of network the client was connected to when the call was placed. Select one of the following:</span></span></p>
<dl>
<dt><span></span></dt>
<dd><p><span data-ttu-id="65a1c-240">Ко</span><span class="sxs-lookup"><span data-stu-id="65a1c-240">[All]</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="65a1c-241">Политик</span><span class="sxs-lookup"><span data-stu-id="65a1c-241">Wired</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="65a1c-242">Инфракрас</span><span class="sxs-lookup"><span data-stu-id="65a1c-242">Wireless</span></span></p>
</dd>
</dl></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="65a1c-243"><strong>VPN</strong></span><span class="sxs-lookup"><span data-stu-id="65a1c-243"><strong>VPN</strong></span></span></p></td>
<td><p><span data-ttu-id="65a1c-p120">Указывает, использовал ли внешний клиент VPN-подключение при выполнении звонка. Выберите одно из значений:</span><span class="sxs-lookup"><span data-stu-id="65a1c-p120">Indicates whether an external client was using a virtual private network (VPN) connection when the call was placed. Select one of the following:</span></span></p>
<dl>
<dt><span></span></dt>
<dd><p><span data-ttu-id="65a1c-246">Ко</span><span class="sxs-lookup"><span data-stu-id="65a1c-246">[All]</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="65a1c-247">VPN</span><span class="sxs-lookup"><span data-stu-id="65a1c-247">VPN</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="65a1c-248">Не VPN</span><span class="sxs-lookup"><span data-stu-id="65a1c-248">Non-VPN</span></span></p>
</dd>
</dl></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="65a1c-249"><strong> Тип устройства </strong></span><span class="sxs-lookup"><span data-stu-id="65a1c-249"><strong>Device type</strong></span></span></p></td>
<td><p><span data-ttu-id="65a1c-p121">Определяет тип устройства. Выберите один из следующих вариантов:</span><span class="sxs-lookup"><span data-stu-id="65a1c-p121">Indicates the type of device. Select one of the following:</span></span></p>
<dl>
<dt><span></span></dt>
<dd><p><span data-ttu-id="65a1c-252">Устройства захвата</span><span class="sxs-lookup"><span data-stu-id="65a1c-252">Capture device</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="65a1c-253">Устройства обработки</span><span class="sxs-lookup"><span data-stu-id="65a1c-253">Render device</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="65a1c-254">Пара устройств захвата/обработки</span><span class="sxs-lookup"><span data-stu-id="65a1c-254">Capture/Render device pair</span></span></p>
</dd>
</dl></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="65a1c-255"><strong> Имя устройства </strong></span><span class="sxs-lookup"><span data-stu-id="65a1c-255"><strong>Device name</strong></span></span></p></td>
<td><p><span data-ttu-id="65a1c-p122">Имя устройства захвата или обработки. Можно ввести полное имя устройства или любую часть имени. Например, чтобы найти устройство «Микрофон» (Microsoft LifeCam VX-1000.), можно ввести полное имя устройства в следующем формате:</span><span class="sxs-lookup"><span data-stu-id="65a1c-p122">Name of the capture or render device. You can enter the complete device name or any portion of the device name. For example, to find the device Microphone (Microsoft LifeCam VX-1000.), you can enter the complete device name as follows:</span></span></p>
<p><span data-ttu-id="65a1c-259">Микрофон (Microsoft LifeCam VX-1000.)</span><span class="sxs-lookup"><span data-stu-id="65a1c-259">Microphone (Microsoft LifeCam VX-1000.)</span></span></p>
<p><span data-ttu-id="65a1c-p123">Или вы можете ввести только часть имени. Пример:</span><span class="sxs-lookup"><span data-stu-id="65a1c-p123">Or, you can enter just a portion of the name. For example:</span></span></p>
<p><span data-ttu-id="65a1c-262">LifeCam</span><span class="sxs-lookup"><span data-stu-id="65a1c-262">LifeCam</span></span></p>
<p><span data-ttu-id="65a1c-263">Обратите внимание, что предыдущий фильтр возвращает любое устройство, содержащее строку &quot; LifeCam &quot; в любом месте его имени.</span><span class="sxs-lookup"><span data-stu-id="65a1c-263">Note that the preceding filter returns any device that contains the string &quot;LifeCam&quot; anywhere in its name.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="65a1c-264">Метрики</span><span class="sxs-lookup"><span data-stu-id="65a1c-264">Metrics</span></span>

<span data-ttu-id="65a1c-265">Следующая таблица содержит сведения, приведенные в отчете по устройству.</span><span class="sxs-lookup"><span data-stu-id="65a1c-265">The following table lists the information provided in the Device Report.</span></span>

### <a name="device-report-metrics"></a><span data-ttu-id="65a1c-266">Метрики отчета по устройству</span><span class="sxs-lookup"><span data-stu-id="65a1c-266">Device Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="65a1c-267">Имя</span><span class="sxs-lookup"><span data-stu-id="65a1c-267">Name</span></span></th>
<th><span data-ttu-id="65a1c-268">Возможность сортировки по этому показателю</span><span class="sxs-lookup"><span data-stu-id="65a1c-268">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="65a1c-269">Описание</span><span class="sxs-lookup"><span data-stu-id="65a1c-269">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="65a1c-270"><strong>Устройства захвата</strong></span><span class="sxs-lookup"><span data-stu-id="65a1c-270"><strong>Capture device</strong></span></span></p></td>
<td><p><span data-ttu-id="65a1c-271">Да</span><span class="sxs-lookup"><span data-stu-id="65a1c-271">Yes</span></span></p></td>
<td><p><span data-ttu-id="65a1c-272">Устройство (например, микрофон или веб-камера), используемое для передачи аудиосигналов.</span><span class="sxs-lookup"><span data-stu-id="65a1c-272">Device (for example, a microphone or webcam) used for transmitting audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="65a1c-273"><strong>Устройства обработки</strong></span><span class="sxs-lookup"><span data-stu-id="65a1c-273"><strong>Render device</strong></span></span></p></td>
<td><p><span data-ttu-id="65a1c-274">Да</span><span class="sxs-lookup"><span data-stu-id="65a1c-274">Yes</span></span></p></td>
<td><p><span data-ttu-id="65a1c-275">Устройство (например, наушники или динамики), используемые для приема аудиосигналов.</span><span class="sxs-lookup"><span data-stu-id="65a1c-275">Device (for example, a headset or speakers) used for receiving audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="65a1c-276"><strong>Громкость вызова</strong></span><span class="sxs-lookup"><span data-stu-id="65a1c-276"><strong>Call volume</strong></span></span></p></td>
<td><p><span data-ttu-id="65a1c-277">Да</span><span class="sxs-lookup"><span data-stu-id="65a1c-277">Yes</span></span></p></td>
<td><p><span data-ttu-id="65a1c-278">Общее количество выполненных вызовов.</span><span class="sxs-lookup"><span data-stu-id="65a1c-278">Total number of calls placed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="65a1c-279"><strong>Процент звонков низкого качества</strong></span><span class="sxs-lookup"><span data-stu-id="65a1c-279"><strong>Poor call percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="65a1c-280">Да</span><span class="sxs-lookup"><span data-stu-id="65a1c-280">Yes</span></span></p></td>
<td><p><span data-ttu-id="65a1c-281">Процент звонков, которые были классифицированы как &quot; неудовлетворительные. &quot; Плохим вызовом является любой вызов, для которого по крайней мере одна измеренная метрика превысила допустимое значение (например, вызов с чрезмерным колебанием).</span><span class="sxs-lookup"><span data-stu-id="65a1c-281">Percentage of calls that were classified as &quot;poor.&quot; A poor call is any call which at least one of the measured metrics exceeded the allowed value (for example, a call that experienced excessive jitter).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="65a1c-282"><strong> Уникальные пользователи </strong></span><span class="sxs-lookup"><span data-stu-id="65a1c-282"><strong>Unique users</strong></span></span></p></td>
<td><p><span data-ttu-id="65a1c-283">Да</span><span class="sxs-lookup"><span data-stu-id="65a1c-283">Yes</span></span></p></td>
<td><p><span data-ttu-id="65a1c-p124">Уникальные пользователи, которые использовали устройство. Если пользователь использовал устройство 13 раз, он расценивается как один уникальный пользователь,как и пользователь, который использовал устройство только один раз.</span><span class="sxs-lookup"><span data-stu-id="65a1c-p124">Unique users who used the device. If a user used the device 13 times he or she would count as one unique user, the same as a user who only used the device a single time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="65a1c-286"><strong>Соотношение времени голосовой коммутации</strong></span><span class="sxs-lookup"><span data-stu-id="65a1c-286"><strong>Ratio of voice switch time</strong></span></span></p></td>
<td><p><span data-ttu-id="65a1c-287">Да</span><span class="sxs-lookup"><span data-stu-id="65a1c-287">Yes</span></span></p></td>
<td><p><span data-ttu-id="65a1c-p125">Процент вызова, который должен был осуществляться в полудуплексном режиме в целях предотвращения эхосигналов. В полудуплексном режиме взаимодействие может осуществляться только в одном направлении в каждый определенный момент времени аналогично тому, как пользователи по очереди слушают и говорят при связи по рации.</span><span class="sxs-lookup"><span data-stu-id="65a1c-p125">Percentage of the call that had to be conducted in half duplex mode in order to prevent echo. In half duplex mode, communication can travel in only one direction at a time, similar to the way users take turns when communicating with a walkie-talkie.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="65a1c-290"><strong>Процент времени отказа микрофона</strong></span><span class="sxs-lookup"><span data-stu-id="65a1c-290"><strong>Ratio of microphone not functioning</strong></span></span></p></td>
<td><p><span data-ttu-id="65a1c-291">Да</span><span class="sxs-lookup"><span data-stu-id="65a1c-291">Yes</span></span></p></td>
<td><p><span data-ttu-id="65a1c-p126">Процент вызова, в ходе которого устройство захвата не работало на приемлемом уровне. Высокие значения указывают на то, что проблемы, связанные с качеством связи при вызове, были главным образом обусловлены тем, что устройство захвата не функционировало должным образом.</span><span class="sxs-lookup"><span data-stu-id="65a1c-p126">Percentage of the call in which the capture device was not functioning at an acceptable level. A high values suggests that quality issues with the call were primarily due to the capture device not working as expected.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="65a1c-294"><strong>Процент времени отказа динамика</strong></span><span class="sxs-lookup"><span data-stu-id="65a1c-294"><strong>Ratio of speaker not functioning</strong></span></span></p></td>
<td><p><span data-ttu-id="65a1c-295">Да</span><span class="sxs-lookup"><span data-stu-id="65a1c-295">Yes</span></span></p></td>
<td><p><span data-ttu-id="65a1c-p127">Процент вызова, в ходе которого устройство обработки звука не работало на приемлемом уровне. Высокие значения указывают на то, что проблемы, связанные с качеством связи при вызове, были главным образом обусловлены тем, что устройство обработки звука не функционировало должным образом.</span><span class="sxs-lookup"><span data-stu-id="65a1c-p127">Percentage of the call in which the render device was not functioning at an acceptable level. A high values suggests that quality issues with the call were primarily due to the render device not working as expected.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="65a1c-298"><strong>Вызовы с голосовой коммутацией (%)</strong></span><span class="sxs-lookup"><span data-stu-id="65a1c-298"><strong>Calls with voice switch (%)</strong></span></span></p></td>
<td><p><span data-ttu-id="65a1c-299">Да</span><span class="sxs-lookup"><span data-stu-id="65a1c-299">Yes</span></span></p></td>
<td><p><span data-ttu-id="65a1c-p128">Процент общего количества вызовов, которые были выполнены в полудуплексном режиме. В полудуплексном режиме взаимодействие может осуществляться только в одном направлении в каждый определенный момент времени аналогично тому, как пользователи по очереди слушают и говорят при связи по рации.</span><span class="sxs-lookup"><span data-stu-id="65a1c-p128">Percentage of the total calls which had to be placed into half duplex mode. In half duplex mode, communication can travel in only one direction at a time, similar to the way users take turns when communicating with a walkie-talkie.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="65a1c-302"><strong>Эхо микрофона в (%)</strong></span><span class="sxs-lookup"><span data-stu-id="65a1c-302"><strong>Echo microphone in (%)</strong></span></span></p></td>
<td><p><span data-ttu-id="65a1c-303">Да</span><span class="sxs-lookup"><span data-stu-id="65a1c-303">Yes</span></span></p></td>
<td><p><span data-ttu-id="65a1c-304">Процент времени, когда в потоке записи микрофона обнаружено эхо-сообщений.</span><span class="sxs-lookup"><span data-stu-id="65a1c-304">Percentage of time when echo was detected in the microphone capture stream.</span></span> <span data-ttu-id="65a1c-305">Как правило, низкие значения для гарнитур и телефонов, а также для телефонов динамиков или отдельных динамиков.</span><span class="sxs-lookup"><span data-stu-id="65a1c-305">Typically, values are low for headsets or handsets, and higher for speaker phones or stand-alone speakers.</span></span> <span data-ttu-id="65a1c-306">Для устройств, поддерживающих встроенную отдавление акустического эха, высокие значения указывают на наличие потерь эха.</span><span class="sxs-lookup"><span data-stu-id="65a1c-306">For devices that support on-board acoustic echo cancellation, high values indicate echo leak.</span></span> <span data-ttu-id="65a1c-307">Для других устройств эта метрика не должна использоваться для оценки качества устройства.</span><span class="sxs-lookup"><span data-stu-id="65a1c-307">For other devices, this metric should not be used to evaluate device quality.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="65a1c-308"><strong>Переданные эхосигналы (%)</strong></span><span class="sxs-lookup"><span data-stu-id="65a1c-308"><strong>Echo send (%)</strong></span></span></p></td>
<td><p><span data-ttu-id="65a1c-309">Да</span><span class="sxs-lookup"><span data-stu-id="65a1c-309">Yes</span></span></p></td>
<td><p><span data-ttu-id="65a1c-310">Процент эхосигналов, переданных другим пользователям.</span><span class="sxs-lookup"><span data-stu-id="65a1c-310">Percentage of echo transmitted to other users.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="65a1c-311"><strong>Вызовы с эхо (%)</strong></span><span class="sxs-lookup"><span data-stu-id="65a1c-311"><strong>Calls with echo (%)</strong></span></span></p></td>
<td><p><span data-ttu-id="65a1c-312">Да</span><span class="sxs-lookup"><span data-stu-id="65a1c-312">Yes</span></span></p></td>
<td><p><span data-ttu-id="65a1c-313">Процент общего количества вызовов, в ходе которых эхосигналы превысили допустимый уровень.</span><span class="sxs-lookup"><span data-stu-id="65a1c-313">Percentage of the total calls that had echo exceeding the acceptable level.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

