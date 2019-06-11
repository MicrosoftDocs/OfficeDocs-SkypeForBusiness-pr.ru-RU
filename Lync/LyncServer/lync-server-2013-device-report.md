---
title: 'Сервер Lync Server 2013: отчет о устройстве'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Device Report
ms:assetid: f42e4d60-699b-4870-8bb5-13b51bb6eb2b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615049(v=OCS.15)
ms:contentKeyID: 48185807
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e172837622c4ad40a29cca74dcaf42497c4b2bd5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834448"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="device-report-in-lync-server-2013"></a><span data-ttu-id="2ad9a-102">Отчет об устройстве в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2ad9a-102">Device Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2ad9a-103">_**Тема последнего изменения:** 2013-11-12_</span><span class="sxs-lookup"><span data-stu-id="2ad9a-103">_**Topic Last Modified:** 2013-11-12_</span></span>

<span data-ttu-id="2ad9a-104">Отчет по устройствам можно скорее назвать отчетом по микрофонам и динамикам, так как отчет по устройствам используется для получения показателей, относящихся к вызовам (включая проценты вызовов низкого качества, эхосигналы и время коммутации вызовов) и сгруппированных по микрофонам и динамикам, которые использовались в ходе вызова.</span><span class="sxs-lookup"><span data-stu-id="2ad9a-104">The Device Report might be better titled the Microphone and Speakers Report; that's because the Device Report retrieves call-related metrics (such as poor call percentage, echo, and voice switch time) grouped by the microphones and speakers used in the call.</span></span> <span data-ttu-id="2ad9a-105">Если вы заинтересованы в IP-телефонах (также называемых "устройствам"), используйте [отчет о запасах IP-телефона в Lync Server 2013](lync-server-2013-ip-phone-inventory-report.md) .</span><span class="sxs-lookup"><span data-stu-id="2ad9a-105">If you are interested in IP phones (also commonly referred to as "devices"), use the [IP Phone Inventory Report in Lync Server 2013](lync-server-2013-ip-phone-inventory-report.md) instead.</span></span>

<span data-ttu-id="2ad9a-p102">Отчет по устройствам крайне полезен для администраторов, так как он позволяет определить, не поступает ли на определенный тип устройств большее количество вызовов низкого качества, чем на другие устройства. В свою очередь, это может влиять на любые решения, которые необходимо принимать при покупке новых устройств или замене существующих.</span><span class="sxs-lookup"><span data-stu-id="2ad9a-p102">The Device Report is extremely useful for administrators in determining if a specific type of device is experiencing high volumes of poor quality calls than others. In turn, this could influence any decisions you must make when it comes time to buy new devices or to replace existing devices.</span></span>

<span data-ttu-id="2ad9a-p103">По умолчанию информация, отображаемая в отчете по устройствам, также основывается на показателях микрофона (устройства захвата) и динамиков/наушников (устройство обработки), используемых в ходе вызова. Например, предположим, что несколько пользователей используют следующее устройство захвата и устройство обработки: По умолчанию информация, отображаемая в отчете по устройствам, также основывается на показателях микрофона (устройства захвата) и динамиков/наушников (устройство обработки), используемых в ходе вызова. Например, предположим, что несколько пользователей используют следующее устройство захвата и устройство обработки:</span><span class="sxs-lookup"><span data-stu-id="2ad9a-p103">By default, the information displayed in the Device Report is also based on the microphone (the capture device) and speakers/headset (the render device) used in the call. For example, suppose you have several users who use the following capture device and the following render device: By default, the information displayed in the Device Report is also based on the microphone (the capture device) and speakers/headset (the render device) used in the call. For example, suppose you have several users who use the following capture device and the following render device:</span></span>

  - <span data-ttu-id="2ad9a-111">Устройство захвата – микрофон (SoundMAX Integrated Digital HD Audio)</span><span class="sxs-lookup"><span data-stu-id="2ad9a-111">Capture device -- Microphone (SoundMAX Integrated Digital HD Audio)</span></span>

  - <span data-ttu-id="2ad9a-112">Устройство обработки – наушники гарнитуры (Microsoft LifeChat LX-3000)</span><span class="sxs-lookup"><span data-stu-id="2ad9a-112">Render device -- Headset Earphone (Microsoft LifeChat LX-3000)</span></span>

<span data-ttu-id="2ad9a-113">Если эти пользователи в общей сложности выполнили 254 вызова, в отчете будет отображаться запись, аналогичная следующей:</span><span class="sxs-lookup"><span data-stu-id="2ad9a-113">If those users made a total of 254 calls you'll see an entry like this in the report:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2ad9a-114">Устройства захвата</span><span class="sxs-lookup"><span data-stu-id="2ad9a-114">Capture device</span></span></th>
<th><span data-ttu-id="2ad9a-115">Устройства обработки</span><span class="sxs-lookup"><span data-stu-id="2ad9a-115">Render device</span></span></th>
<th><span data-ttu-id="2ad9a-116">Громкость вызова</span><span class="sxs-lookup"><span data-stu-id="2ad9a-116">Call volume</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2ad9a-117">Микрофон (SoundMAX Integrated Digital HD Audio)</span><span class="sxs-lookup"><span data-stu-id="2ad9a-117">Microphone (SoundMAX Integrated Digital HD Audio)</span></span></p></td>
<td><p><span data-ttu-id="2ad9a-118">Наушники гарнитуры (Microsoft LifeChat LX-3000)</span><span class="sxs-lookup"><span data-stu-id="2ad9a-118">Headset Earphone (Microsoft LifeChat LX-3000)</span></span></p></td>
<td><p><span data-ttu-id="2ad9a-119">254</span><span class="sxs-lookup"><span data-stu-id="2ad9a-119">254</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="2ad9a-p104">Теперь предположим, что определенное количество пользователей используют одно и то же устройство захвата, но разные устройства обработки. В этом случае отчет будет включать вторую строку для данного уникального сочетания устройства захвата и устройства обработки.</span><span class="sxs-lookup"><span data-stu-id="2ad9a-p104">Now, suppose you have a number of users who use that same capture device but a different render device. In that case, you'll have a second line entry in the report, one for that unique combination of capture device and render device:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2ad9a-122">Устройства захвата</span><span class="sxs-lookup"><span data-stu-id="2ad9a-122">Capture device</span></span></th>
<th><span data-ttu-id="2ad9a-123">Устройства обработки</span><span class="sxs-lookup"><span data-stu-id="2ad9a-123">Render device</span></span></th>
<th><span data-ttu-id="2ad9a-124">Громкость вызова</span><span class="sxs-lookup"><span data-stu-id="2ad9a-124">Call volume</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2ad9a-125">Микрофон (SoundMAX Integrated Digital HD Audio)</span><span class="sxs-lookup"><span data-stu-id="2ad9a-125">Microphone (SoundMAX Integrated Digital HD Audio)</span></span></p></td>
<td><p><span data-ttu-id="2ad9a-126">Наушники гарнитуры (Microsoft LifeChat LX-3000)</span><span class="sxs-lookup"><span data-stu-id="2ad9a-126">Headset Earphone (Microsoft LifeChat LX-3000)</span></span></p></td>
<td><p><span data-ttu-id="2ad9a-127">254</span><span class="sxs-lookup"><span data-stu-id="2ad9a-127">254</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2ad9a-128">Микрофон (SoundMAX Integrated Digital HD Audio)</span><span class="sxs-lookup"><span data-stu-id="2ad9a-128">Microphone (SoundMAX Integrated Digital HD Audio)</span></span></p></td>
<td><p><span data-ttu-id="2ad9a-129">Динамики (SoundMAX Integrated Digital HD Audio)</span><span class="sxs-lookup"><span data-stu-id="2ad9a-129">Speakers (SoundMAX Integrated Digital HD Audio)</span></span></p></td>
<td><p><span data-ttu-id="2ad9a-130">319</span><span class="sxs-lookup"><span data-stu-id="2ad9a-130">319</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="2ad9a-p105">Если вам требуются сводные показатели для конкретного устройства (например, для устройства захвата SoundMAX вне зависимости от используемого устройства обработки), выберите нужный вариант в раскрывающемся списке «Тип устройства» (либо устройство захвата, либо устройство обработки). При выборе устройства захвата в этом примере результат будет аналогичен следующему:</span><span class="sxs-lookup"><span data-stu-id="2ad9a-p105">If you would rather see combined totals for a given device (for example, for the SoundMAX capture device, regardless of the render device used), select the appropriate option from the Device type dropdown list (either Capture device or Render device). If you select Capture device in this example, that will give you output similar to this:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2ad9a-133">Устройства захвата</span><span class="sxs-lookup"><span data-stu-id="2ad9a-133">Capture device</span></span></th>
<th><span data-ttu-id="2ad9a-134">Громкость вызова</span><span class="sxs-lookup"><span data-stu-id="2ad9a-134">Call volume</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2ad9a-135">Микрофон (SoundMAX Integrated Digital HD Audio)</span><span class="sxs-lookup"><span data-stu-id="2ad9a-135">Microphone (SoundMAX Integrated Digital HD Audio)</span></span></p></td>
<td><p><span data-ttu-id="2ad9a-136">573</span><span class="sxs-lookup"><span data-stu-id="2ad9a-136">573</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="accessing-the-device-report"></a><span data-ttu-id="2ad9a-137">Доступ к отчету по устройствам</span><span class="sxs-lookup"><span data-stu-id="2ad9a-137">Accessing the Device Report</span></span>

<span data-ttu-id="2ad9a-138">Доступ к отчету по устройствам обычно осуществляется с главной страницы отчетов наблюдения.</span><span class="sxs-lookup"><span data-stu-id="2ad9a-138">The Device Report is typically accessed from the Monitoring Reports home page.</span></span> <span data-ttu-id="2ad9a-139">Тем не менее, если вы просматриваете [подробный отчет о звонке в Lync Server 2013](lync-server-2013-call-detail-report.md) , вы можете перейти к отчету об устройствах для определенного устройства, щелкнув один из указанных ниже метрик.</span><span class="sxs-lookup"><span data-stu-id="2ad9a-139">However, if you are viewing the [Call Detail Report in Lync Server 2013](lync-server-2013-call-detail-report.md) you can drill down to the Device Report for a specific device by clicking either of the following metrics:</span></span>

  - <span data-ttu-id="2ad9a-140">Устройства захвата</span><span class="sxs-lookup"><span data-stu-id="2ad9a-140">Capture Device</span></span>

  - <span data-ttu-id="2ad9a-141">Устройства обработки</span><span class="sxs-lookup"><span data-stu-id="2ad9a-141">Render Device</span></span>

<span data-ttu-id="2ad9a-142">В отчете об устройстве вы можете детализировать отчет "список обзвона" [в Lync Server 2013](lync-server-2013-call-list-report.md) , щелкнув один из указанных ниже метрик.</span><span class="sxs-lookup"><span data-stu-id="2ad9a-142">From the Device Report you can drill down to the [Call List Report in Lync Server 2013](lync-server-2013-call-list-report.md) by clicking either of the following metrics:</span></span>

  - <span data-ttu-id="2ad9a-143">Громкость вызова</span><span class="sxs-lookup"><span data-stu-id="2ad9a-143">Call volume</span></span>

  - <span data-ttu-id="2ad9a-144">Процент звонков низкого качества</span><span class="sxs-lookup"><span data-stu-id="2ad9a-144">Poor call percentage</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-device-report"></a><span data-ttu-id="2ad9a-145">Эффективное использование отчета по устройству</span><span class="sxs-lookup"><span data-stu-id="2ad9a-145">Making the Best Use of the Device Report</span></span>

<span data-ttu-id="2ad9a-146">Отчет по устройствам является крайне подробным с точки зрения названий устройств; например, предположим, что у вас есть следующие устройства захвата:</span><span class="sxs-lookup"><span data-stu-id="2ad9a-146">When it comes to device names, the Device Report is extremely detailed; for example, suppose you have the following capture devices:</span></span>

  - <span data-ttu-id="2ad9a-147">Микрофон Aastra 3002 (2- Aastra 3002)</span><span class="sxs-lookup"><span data-stu-id="2ad9a-147">Aastra 3002 Microphone (2- Aastra 3002)</span></span>

  - <span data-ttu-id="2ad9a-148">Микрофон Aastra 3002 (3- Aastra 3002)</span><span class="sxs-lookup"><span data-stu-id="2ad9a-148">Aastra 3002 Microphone (3- Aastra 3002)</span></span>

  - <span data-ttu-id="2ad9a-149">Микрофон Aastra 3002 (Aastra 3002)</span><span class="sxs-lookup"><span data-stu-id="2ad9a-149">Aastra 3002 Microphone (Aastra 3002)</span></span>

  - <span data-ttu-id="2ad9a-150">Aastra 6725ip</span><span class="sxs-lookup"><span data-stu-id="2ad9a-150">Aastra 6725ip</span></span>

  - <span data-ttu-id="2ad9a-151">Микрофон Aastra 6725ip (10- Aastra 6725ip)</span><span class="sxs-lookup"><span data-stu-id="2ad9a-151">Aastra 6725ip Microphone (10- Aastra 6725ip)</span></span>

  - <span data-ttu-id="2ad9a-152">Микрофон Aastra 6725ip (10- Aastra 6725ip)-V0</span><span class="sxs-lookup"><span data-stu-id="2ad9a-152">Aastra 6725ip Microphone (10- Aastra 6725ip)-V0</span></span>

  - <span data-ttu-id="2ad9a-153">Микрофон Aastra 6725ip (2- Aastra 6725ip)</span><span class="sxs-lookup"><span data-stu-id="2ad9a-153">Aastra 6725ip Microphone (2- Aastra 6725ip)</span></span>

  - <span data-ttu-id="2ad9a-154">Микрофон Aastra 6725ip (3- Aastra 6725ip)</span><span class="sxs-lookup"><span data-stu-id="2ad9a-154">Aastra 6725ip Microphone (3- Aastra 6725ip)</span></span>

  - <span data-ttu-id="2ad9a-155">Микрофон Aastra 6725ip (4- Aastra 6725ip)</span><span class="sxs-lookup"><span data-stu-id="2ad9a-155">Aastra 6725ip Microphone (4- Aastra 6725ip)</span></span>

  - <span data-ttu-id="2ad9a-156">Микрофон Aastra 6725ip (5- Aastra 6725ip)</span><span class="sxs-lookup"><span data-stu-id="2ad9a-156">Aastra 6725ip Microphone (5- Aastra 6725ip)</span></span>

  - <span data-ttu-id="2ad9a-157">Микрофон Aastra 6725ip (6- Aastra 6725ip)</span><span class="sxs-lookup"><span data-stu-id="2ad9a-157">Aastra 6725ip Microphone (6- Aastra 6725ip)</span></span>

  - <span data-ttu-id="2ad9a-158">Микрофон Aastra 6725ip (7- Aastra 6725ip)</span><span class="sxs-lookup"><span data-stu-id="2ad9a-158">Aastra 6725ip Microphone (7- Aastra 6725ip)</span></span>

  - <span data-ttu-id="2ad9a-159">Микрофон Aastra 6725ip (9- Aastra 6725ip)</span><span class="sxs-lookup"><span data-stu-id="2ad9a-159">Aastra 6725ip Microphone (9- Aastra 6725ip)</span></span>

  - <span data-ttu-id="2ad9a-160">Микрофон Aastra 6725ip (9- Aastra 6725ip)-V0</span><span class="sxs-lookup"><span data-stu-id="2ad9a-160">Aastra 6725ip Microphone (9- Aastra 6725ip)-V0</span></span>

  - <span data-ttu-id="2ad9a-161">Микрофон Aastra 6725ip (Aastra 6725ip)</span><span class="sxs-lookup"><span data-stu-id="2ad9a-161">Aastra 6725ip Microphone (Aastra 6725ip)</span></span>

  - <span data-ttu-id="2ad9a-162">Микрофон Aastra 6725ip (Aastra 6725ip)-V0</span><span class="sxs-lookup"><span data-stu-id="2ad9a-162">Aastra 6725ip Microphone (Aastra 6725ip)-V0</span></span>

  - <span data-ttu-id="2ad9a-163">Микрофон Aastra 6725ip (аудиоустройство USB)</span><span class="sxs-lookup"><span data-stu-id="2ad9a-163">Aastra 6725ip Microphone (USB Audio Device)</span></span>

  - <span data-ttu-id="2ad9a-164">Микрофон Aastra 6725ip (аудиоустройство USB)-V0</span><span class="sxs-lookup"><span data-stu-id="2ad9a-164">Aastra 6725ip Microphone (USB Audio Device)-V0</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="2ad9a-165">Имейте в виду, что при работе с локализованными версиями Lync Server 2013 могут возникнуть разные имена устройств захвата.</span><span class="sxs-lookup"><span data-stu-id="2ad9a-165">Keep in mind that capture device names might not be the same if you are running localized versions of Lync Server 2013.</span></span> <span data-ttu-id="2ad9a-166">Устройство с именем "Aastra 6725ip Microphone (Aastra 6725ip)-V0" на английском языке (США) может называться по-другому на французском или испанском языке.</span><span class="sxs-lookup"><span data-stu-id="2ad9a-166">A device named Aastra 6725ip Microphone (Aastra 6725ip)-V0 in US English could have a different name in French or Spanish.</span></span>



</div>

<span data-ttu-id="2ad9a-167">Часто вам требуется этот уровень детализации; в других случаях, однако, вас может интересовать только количество вызовов, выполненных с помощью какого-либо микрофона Aastra, вне зависимости от номера модели.</span><span class="sxs-lookup"><span data-stu-id="2ad9a-167">Often times you'll want that level of detail; at other times, however, you might only be interested in how many calls use any Aastra microphone, regardless of model number.</span></span> <span data-ttu-id="2ad9a-168">Один из способов получить такую информацию — экспортировать данные отчета о устройстве в Microsoft Excel, а затем сохранить их в файле значений с разделителями-запятыми (например, C:\\Data\\Devices\_. csv).</span><span class="sxs-lookup"><span data-stu-id="2ad9a-168">One way to get information like that is to export the Device Report data to Microsoft Excel and then save that data to a comma-separated values file (for example, C:\\Data\\Devices\_Report.csv).</span></span> <span data-ttu-id="2ad9a-169">Затем можно использовать набор аналогичных команд для импорта CSV-файла в Windows PowerShell и получения полного числа вызовов, выполненных с помощью устройства захвата Aastra:</span><span class="sxs-lookup"><span data-stu-id="2ad9a-169">You can then use a set of commands similar to these to import the .CSV file into Windows PowerShell and report back the total number of calls made using an Aastra capture device:</span></span>

    $devices = Import-Csv "C:\Data\Device_Report.csv
    $sum = $devices | Where-Object {$_."Capture device" -match "Aastra"}
    $sum | foreach-object {[Int]$x = [Int]$x + [Int]$_."call volume"}
    $x

<span data-ttu-id="2ad9a-p109">Это приведет к возврату одного значения, которое представляет собой общее число вызовов, выполненных с помощью устройства захвата Aastra. Например:</span><span class="sxs-lookup"><span data-stu-id="2ad9a-p109">That will return a single value representing the total number of calls made using an Aastra capture device. For example:</span></span>

    384

</div>

<div>

## <a name="filters"></a><span data-ttu-id="2ad9a-172">Фильтры</span><span class="sxs-lookup"><span data-stu-id="2ad9a-172">Filters</span></span>

<span data-ttu-id="2ad9a-p110">Фильтры предоставляют способ возврата более точного набора данных в соответствии с заданными критериями или просмотра возвращенных данных другими способами. Например, отчет по устройствам позволяет выполнить фильтрацию по таким критериям, как тип вызова (то есть был ли данный вызов вызовом клиента), конференц-вызов или вызов по телефонной сети общего пользования (ТСОП). Можно также выбрать способ группировки данных. В этом случае устройства группируются по часу, дню, неделе или месяце.</span><span class="sxs-lookup"><span data-stu-id="2ad9a-p110">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. For example, the Device Report enables you to filter on such things as call type (that is, was the call a client call), a conference call, or a public switched telephone network (PSTN) call. You can also choose how data should be grouped. In this case, devices are grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="2ad9a-177">В следующей таблице перечислены фильтры, которые можно использовать с отчетом по устройствам.</span><span class="sxs-lookup"><span data-stu-id="2ad9a-177">The following table lists the filters that you can use with the Device Report.</span></span>

### <a name="device-report-filters"></a><span data-ttu-id="2ad9a-178">Фильтры отчета по устройствам</span><span class="sxs-lookup"><span data-stu-id="2ad9a-178">Device Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2ad9a-179">Имя</span><span class="sxs-lookup"><span data-stu-id="2ad9a-179">Name</span></span></th>
<th><span data-ttu-id="2ad9a-180">Описание</span><span class="sxs-lookup"><span data-stu-id="2ad9a-180">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2ad9a-181"><strong>От</strong></span><span class="sxs-lookup"><span data-stu-id="2ad9a-181"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="2ad9a-p111">Начальные дата/время для временного диапазона. Чтобы просмотреть данные по часам, введите начальные дату и время следующим образом:</span><span class="sxs-lookup"><span data-stu-id="2ad9a-p111">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="2ad9a-184">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="2ad9a-184">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="2ad9a-p112">Если вы не вводите начальное время, отчет автоматически начинается с 12:00 AM указанного дня. Чтобы просмотреть данные по дням, просто введите дату:</span><span class="sxs-lookup"><span data-stu-id="2ad9a-p112">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="2ad9a-187">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="2ad9a-187">7/7/2012</span></span></p>
<p><span data-ttu-id="2ad9a-188">Чтобы просмотреть данные за неделю или месяц, введите дату, выпадающую на любое время в рамках недели или месяца, которые вы хотите просмотреть (вам не требуется вводить первый день недели или месяца):</span><span class="sxs-lookup"><span data-stu-id="2ad9a-188">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="2ad9a-189">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="2ad9a-189">7/3/2012</span></span></p>
<p><span data-ttu-id="2ad9a-190">Недели всегда отсчитываются с воскресенья по субботу.</span><span class="sxs-lookup"><span data-stu-id="2ad9a-190">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2ad9a-191"><strong>До</strong></span><span class="sxs-lookup"><span data-stu-id="2ad9a-191"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="2ad9a-p113">Конечные дата/время для временного диапазона. Чтобы просмотреть данные по часам, введите конечные дату и время следующим образом:</span><span class="sxs-lookup"><span data-stu-id="2ad9a-p113">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="2ad9a-194">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="2ad9a-194">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="2ad9a-p114">Если вы не вводите конечное время, отчет автоматически заканчивается в 12:00 AM указанного дня. Чтобы просмотреть данные по дням, просто введите дату:</span><span class="sxs-lookup"><span data-stu-id="2ad9a-p114">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="2ad9a-197">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="2ad9a-197">7/7/2012</span></span></p>
<p><span data-ttu-id="2ad9a-198">Чтобы просмотреть данные за неделю или месяц, введите дату, выпадающую на любое время в рамках недели или месяца, которые вы хотите просмотреть (вам не требуется вводить первый день недели или месяца):</span><span class="sxs-lookup"><span data-stu-id="2ad9a-198">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="2ad9a-199">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="2ad9a-199">7/3/2012</span></span></p>
<p><span data-ttu-id="2ad9a-200">Недели всегда отсчитываются с воскресенья по субботу.</span><span class="sxs-lookup"><span data-stu-id="2ad9a-200">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2ad9a-201"><strong>Причина голосовой коммутации</strong></span><span class="sxs-lookup"><span data-stu-id="2ad9a-201"><strong>Voice switch cause</strong></span></span></p></td>
<td><p><span data-ttu-id="2ad9a-p115">Причина, по которой вызов был переведен в полудуплексный режим в целях предотвращения эха. В полудуплексном режиме взаимодействие может осуществляться только в одном направлении в каждый определенный момент времени аналогично тому, как пользователи по очереди слушают и говорят при связи по рации. Выберите один из следующих вариантов:</span><span class="sxs-lookup"><span data-stu-id="2ad9a-p115">Reason why a call had to be placed into half duplex mode in order to prevent echo. In half duplex mode, communication can travel in only one direction at a time, similar to the way users take turns when communicating with a walkie-talkie. Select one of the following:</span></span></p>
<dl>
<dt><span></span></dt>
<dd><p><span data-ttu-id="2ad9a-205">[All] (Все)</span><span class="sxs-lookup"><span data-stu-id="2ad9a-205">[All]</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="2ad9a-206">Отсутствуют</span><span class="sxs-lookup"><span data-stu-id="2ad9a-206">None</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="2ad9a-207">Плохая метка времени</span><span class="sxs-lookup"><span data-stu-id="2ad9a-207">Bad timestamp</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="2ad9a-208">Эхо</span><span class="sxs-lookup"><span data-stu-id="2ad9a-208">Echo</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="2ad9a-209">DNLP (динамический нелинейный процессор)</span><span class="sxs-lookup"><span data-stu-id="2ad9a-209">DNLP (dynamic nonlinear processor)</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="2ad9a-210">Низкая сложность</span><span class="sxs-lookup"><span data-stu-id="2ad9a-210">Low complexity</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="2ad9a-211">Плохо состояния устройства</span><span class="sxs-lookup"><span data-stu-id="2ad9a-211">Bad device state</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="2ad9a-212">Эхо после AEC (акустическое эхоподавление)</span><span class="sxs-lookup"><span data-stu-id="2ad9a-212">Post-AEC echo (acoustic echo cancellation)</span></span></p>
</dd>
</dl></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2ad9a-213"><strong>Причина эхо</strong></span><span class="sxs-lookup"><span data-stu-id="2ad9a-213"><strong>Echo cause</strong></span></span></p></td>
<td><p><span data-ttu-id="2ad9a-p116">Причина, по которой в ходе вызова эхосигналы превысили допустимый уровень (Когда речь идет о телекоммуникациях, под эхо подразумевается отражение звука, то есть явление, аналогичное тому, которое возникает, когда вы кричите в глубокий колодец.) Выберите один из следующих вариантов:</span><span class="sxs-lookup"><span data-stu-id="2ad9a-p116">Reason why echo above the accepted level was detected in a call. (In telecommunications, echo is a reflection of sound, the same phenomenon you will hear if you yell down to the bottom of a well.) Select one of the following:</span></span></p>
<dl>
<dt><span></span></dt>
<dd><p><span data-ttu-id="2ad9a-216">[All] (Все)</span><span class="sxs-lookup"><span data-stu-id="2ad9a-216">[All]</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="2ad9a-217">Отсутствуют</span><span class="sxs-lookup"><span data-stu-id="2ad9a-217">None</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="2ad9a-218">Плохая метка времени</span><span class="sxs-lookup"><span data-stu-id="2ad9a-218">Bad timestamp</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="2ad9a-219">Эхо после AEC (акустическое эхоподавление)</span><span class="sxs-lookup"><span data-stu-id="2ad9a-219">Post-AEC echo (acoustic echo cancellation)</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="2ad9a-220">ANLP (адаптивный нелинейный процессор)</span><span class="sxs-lookup"><span data-stu-id="2ad9a-220">ANLP (adaptive nonlinear processor)</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="2ad9a-221">DNLP (динамический нелинейный процессор)</span><span class="sxs-lookup"><span data-stu-id="2ad9a-221">DNLP (dynamic nonlinear processor)</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="2ad9a-222">Отсечка микрофона</span><span class="sxs-lookup"><span data-stu-id="2ad9a-222">Microphone clipping</span></span></p>
</dd>
</dl></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2ad9a-223"><strong>Тип вызова</strong></span><span class="sxs-lookup"><span data-stu-id="2ad9a-223"><strong>Call type</strong></span></span></p></td>
<td><p><span data-ttu-id="2ad9a-p117">Определяет тип выполненного вызова. Выберите один из следующих вариантов:</span><span class="sxs-lookup"><span data-stu-id="2ad9a-p117">Indicates the type of call that was made. Select one of the following:</span></span></p>
<dl>
<dt><span></span></dt>
<dd><p><span data-ttu-id="2ad9a-226">[All] (Все)</span><span class="sxs-lookup"><span data-stu-id="2ad9a-226">[All]</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="2ad9a-227">Вызов клиента</span><span class="sxs-lookup"><span data-stu-id="2ad9a-227">Client call</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="2ad9a-228">Вызов ТСОП</span><span class="sxs-lookup"><span data-stu-id="2ad9a-228">PSTN call</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="2ad9a-229">Конференц-связь</span><span class="sxs-lookup"><span data-stu-id="2ad9a-229">Conference call</span></span></p>
</dd>
</dl></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2ad9a-230"><strong>Тип доступа</strong></span><span class="sxs-lookup"><span data-stu-id="2ad9a-230"><strong>Access type</strong></span></span></p></td>
<td><p><span data-ttu-id="2ad9a-p118">Определяет, был ли клиент зарегистрирован во внутренней сети или внешней сети при выполнении вызова. Выберите один из следующих вариантов:</span><span class="sxs-lookup"><span data-stu-id="2ad9a-p118">Indicates whether the client was logged on to the internal network or the external network when the call was placed. Select one of the following:</span></span></p>
<dl>
<dt><span></span></dt>
<dd><p><span data-ttu-id="2ad9a-233">[All] (Все)</span><span class="sxs-lookup"><span data-stu-id="2ad9a-233">[All]</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="2ad9a-234">Internal</span><span class="sxs-lookup"><span data-stu-id="2ad9a-234">Internal</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="2ad9a-235">Внешняя</span><span class="sxs-lookup"><span data-stu-id="2ad9a-235">External</span></span></p>
</dd>
</dl></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2ad9a-236"><strong>Тип сети</strong></span><span class="sxs-lookup"><span data-stu-id="2ad9a-236"><strong>Network type</strong></span></span></p></td>
<td><p><span data-ttu-id="2ad9a-p119">Определяет тип сети, к которой был подключен клиент при выполнении вызова. Выберите один из следующих вариантов:</span><span class="sxs-lookup"><span data-stu-id="2ad9a-p119">Indicates the type of network the client was connected to when the call was placed. Select one of the following:</span></span></p>
<dl>
<dt><span></span></dt>
<dd><p><span data-ttu-id="2ad9a-239">[All] (Все)</span><span class="sxs-lookup"><span data-stu-id="2ad9a-239">[All]</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="2ad9a-240">Проводная</span><span class="sxs-lookup"><span data-stu-id="2ad9a-240">Wired</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="2ad9a-241">Беспроводная</span><span class="sxs-lookup"><span data-stu-id="2ad9a-241">Wireless</span></span></p>
</dd>
</dl></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2ad9a-242"><strong>VPN</strong></span><span class="sxs-lookup"><span data-stu-id="2ad9a-242"><strong>VPN</strong></span></span></p></td>
<td><p><span data-ttu-id="2ad9a-p120">Указывает, использовал ли внешний клиент подключение посредством виртуальной частной сети (VPN) при выполнении вызова. Выберите один из следующих вариантов:</span><span class="sxs-lookup"><span data-stu-id="2ad9a-p120">Indicates whether an external client was using a virtual private network (VPN) connection when the call was placed. Select one of the following:</span></span></p>
<dl>
<dt><span></span></dt>
<dd><p><span data-ttu-id="2ad9a-245">[All] (Все)</span><span class="sxs-lookup"><span data-stu-id="2ad9a-245">[All]</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="2ad9a-246">VPN;</span><span class="sxs-lookup"><span data-stu-id="2ad9a-246">VPN</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="2ad9a-247">Не VPN</span><span class="sxs-lookup"><span data-stu-id="2ad9a-247">Non-VPN</span></span></p>
</dd>
</dl></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2ad9a-248"><strong>Тип устройства</strong></span><span class="sxs-lookup"><span data-stu-id="2ad9a-248"><strong>Device type</strong></span></span></p></td>
<td><p><span data-ttu-id="2ad9a-p121">Определяет тип устройства. Выберите один из следующих вариантов:</span><span class="sxs-lookup"><span data-stu-id="2ad9a-p121">Indicates the type of device. Select one of the following:</span></span></p>
<dl>
<dt><span></span></dt>
<dd><p><span data-ttu-id="2ad9a-251">Устройства захвата</span><span class="sxs-lookup"><span data-stu-id="2ad9a-251">Capture device</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="2ad9a-252">Устройства обработки</span><span class="sxs-lookup"><span data-stu-id="2ad9a-252">Render device</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="2ad9a-253">Пара устройств захвата/обработки</span><span class="sxs-lookup"><span data-stu-id="2ad9a-253">Capture/Render device pair</span></span></p>
</dd>
</dl></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2ad9a-254"><strong>Имя устройства</strong></span><span class="sxs-lookup"><span data-stu-id="2ad9a-254"><strong>Device name</strong></span></span></p></td>
<td><p><span data-ttu-id="2ad9a-p122">Имя устройства захвата или обработки. Можно ввести полное имя устройства или любую часть имени. Например, чтобы найти устройство «Микрофон» (Microsoft LifeCam VX-1000.), можно ввести полное имя устройства в следующем формате:</span><span class="sxs-lookup"><span data-stu-id="2ad9a-p122">Name of the capture or render device. You can enter the complete device name or any portion of the device name. For example, to find the device Microphone (Microsoft LifeCam VX-1000.), you can enter the complete device name as follows:</span></span></p>
<p><span data-ttu-id="2ad9a-258">Микрофон (Microsoft LifeCam VX-1000.)</span><span class="sxs-lookup"><span data-stu-id="2ad9a-258">Microphone (Microsoft LifeCam VX-1000.)</span></span></p>
<p><span data-ttu-id="2ad9a-p123">Или вы можете ввести только часть имени. Пример:</span><span class="sxs-lookup"><span data-stu-id="2ad9a-p123">Or, you can enter just a portion of the name. For example:</span></span></p>
<p><span data-ttu-id="2ad9a-261">LifeCam</span><span class="sxs-lookup"><span data-stu-id="2ad9a-261">LifeCam</span></span></p>
<p><span data-ttu-id="2ad9a-262">Обратите внимание, что предыдущий фильтр возвращает любое устройство, содержащее &quot;строку&quot; , LifeCam в любом месте ее имени.</span><span class="sxs-lookup"><span data-stu-id="2ad9a-262">Note that the preceding filter returns any device that contains the string &quot;LifeCam&quot; anywhere in its name.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="2ad9a-263">Показатели</span><span class="sxs-lookup"><span data-stu-id="2ad9a-263">Metrics</span></span>

<span data-ttu-id="2ad9a-264">Следующая таблица содержит сведения, приведенные в отчете по устройству.</span><span class="sxs-lookup"><span data-stu-id="2ad9a-264">The following table lists the information provided in the Device Report.</span></span>

### <a name="device-report-metrics"></a><span data-ttu-id="2ad9a-265">Метрики отчета по устройству</span><span class="sxs-lookup"><span data-stu-id="2ad9a-265">Device Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2ad9a-266">Имя</span><span class="sxs-lookup"><span data-stu-id="2ad9a-266">Name</span></span></th>
<th><span data-ttu-id="2ad9a-267">Поддержка сортировки</span><span class="sxs-lookup"><span data-stu-id="2ad9a-267">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="2ad9a-268">Описание</span><span class="sxs-lookup"><span data-stu-id="2ad9a-268">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2ad9a-269"><strong>Устройства захвата</strong></span><span class="sxs-lookup"><span data-stu-id="2ad9a-269"><strong>Capture device</strong></span></span></p></td>
<td><p><span data-ttu-id="2ad9a-270">Да</span><span class="sxs-lookup"><span data-stu-id="2ad9a-270">Yes</span></span></p></td>
<td><p><span data-ttu-id="2ad9a-271">Устройство (например, микрофон или веб-камера), используемое для передачи аудиосигналов.</span><span class="sxs-lookup"><span data-stu-id="2ad9a-271">Device (for example, a microphone or webcam) used for transmitting audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2ad9a-272"><strong>Устройства обработки</strong></span><span class="sxs-lookup"><span data-stu-id="2ad9a-272"><strong>Render device</strong></span></span></p></td>
<td><p><span data-ttu-id="2ad9a-273">Да</span><span class="sxs-lookup"><span data-stu-id="2ad9a-273">Yes</span></span></p></td>
<td><p><span data-ttu-id="2ad9a-274">Устройство (например, наушники или динамики), используемые для приема аудиосигналов.</span><span class="sxs-lookup"><span data-stu-id="2ad9a-274">Device (for example, a headset or speakers) used for receiving audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2ad9a-275"><strong>Громкость вызова</strong></span><span class="sxs-lookup"><span data-stu-id="2ad9a-275"><strong>Call volume</strong></span></span></p></td>
<td><p><span data-ttu-id="2ad9a-276">Да</span><span class="sxs-lookup"><span data-stu-id="2ad9a-276">Yes</span></span></p></td>
<td><p><span data-ttu-id="2ad9a-277">Общее количество выполненных вызовов.</span><span class="sxs-lookup"><span data-stu-id="2ad9a-277">Total number of calls placed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2ad9a-278"><strong>Процент звонков низкого качества</strong></span><span class="sxs-lookup"><span data-stu-id="2ad9a-278"><strong>Poor call percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="2ad9a-279">Да</span><span class="sxs-lookup"><span data-stu-id="2ad9a-279">Yes</span></span></p></td>
<td><p><span data-ttu-id="2ad9a-280">Процент звонков, которые были классифицированы &quot;как плохие. &quot; Неудовлетворительный звонок — это любой вызов, для которого по крайней мере одна из измеряемых показателей превысила разрешенное значение (например, вызов с избыточной колебанием).</span><span class="sxs-lookup"><span data-stu-id="2ad9a-280">Percentage of calls that were classified as &quot;poor.&quot; A poor call is any call which at least one of the measured metrics exceeded the allowed value (for example, a call that experienced excessive jitter).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2ad9a-281"><strong>Уникальные пользователи</strong></span><span class="sxs-lookup"><span data-stu-id="2ad9a-281"><strong>Unique users</strong></span></span></p></td>
<td><p><span data-ttu-id="2ad9a-282">Да</span><span class="sxs-lookup"><span data-stu-id="2ad9a-282">Yes</span></span></p></td>
<td><p><span data-ttu-id="2ad9a-p124">Уникальные пользователи, которые использовали устройство. Если пользователь использовал устройство 13 раз, он расценивается как один уникальный пользователь,как и пользователь, который использовал устройство только один раз.</span><span class="sxs-lookup"><span data-stu-id="2ad9a-p124">Unique users who used the device. If a user used the device 13 times he or she would count as one unique user, the same as a user who only used the device a single time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2ad9a-285"><strong>Соотношение времени голосовой коммутации</strong></span><span class="sxs-lookup"><span data-stu-id="2ad9a-285"><strong>Ratio of voice switch time</strong></span></span></p></td>
<td><p><span data-ttu-id="2ad9a-286">Да</span><span class="sxs-lookup"><span data-stu-id="2ad9a-286">Yes</span></span></p></td>
<td><p><span data-ttu-id="2ad9a-p125">Процент вызова, который должен был осуществляться в полудуплексном режиме в целях предотвращения эхосигналов. В полудуплексном режиме взаимодействие может осуществляться только в одном направлении в каждый определенный момент времени аналогично тому, как пользователи по очереди слушают и говорят при связи по рации.</span><span class="sxs-lookup"><span data-stu-id="2ad9a-p125">Percentage of the call that had to be conducted in half duplex mode in order to prevent echo. In half duplex mode, communication can travel in only one direction at a time, similar to the way users take turns when communicating with a walkie-talkie.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2ad9a-289"><strong>Процент времени отказа микрофона</strong></span><span class="sxs-lookup"><span data-stu-id="2ad9a-289"><strong>Ratio of microphone not functioning</strong></span></span></p></td>
<td><p><span data-ttu-id="2ad9a-290">Да</span><span class="sxs-lookup"><span data-stu-id="2ad9a-290">Yes</span></span></p></td>
<td><p><span data-ttu-id="2ad9a-p126">Процент вызова, в ходе которого устройство захвата не работало на приемлемом уровне. Высокие значения указывают на то, что проблемы, связанные с качеством связи при вызове, были главным образом обусловлены тем, что устройство захвата не функционировало должным образом.</span><span class="sxs-lookup"><span data-stu-id="2ad9a-p126">Percentage of the call in which the capture device was not functioning at an acceptable level. A high values suggests that quality issues with the call were primarily due to the capture device not working as expected.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2ad9a-293"><strong>Процент времени отказа динамика</strong></span><span class="sxs-lookup"><span data-stu-id="2ad9a-293"><strong>Ratio of speaker not functioning</strong></span></span></p></td>
<td><p><span data-ttu-id="2ad9a-294">Да</span><span class="sxs-lookup"><span data-stu-id="2ad9a-294">Yes</span></span></p></td>
<td><p><span data-ttu-id="2ad9a-p127">Процент вызова, в ходе которого устройство обработки звука не работало на приемлемом уровне. Высокие значения указывают на то, что проблемы, связанные с качеством связи при вызове, были главным образом обусловлены тем, что устройство обработки звука не функционировало должным образом.</span><span class="sxs-lookup"><span data-stu-id="2ad9a-p127">Percentage of the call in which the render device was not functioning at an acceptable level. A high values suggests that quality issues with the call were primarily due to the render device not working as expected.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2ad9a-297"><strong>Вызовы с голосовой коммутацией (%)</strong></span><span class="sxs-lookup"><span data-stu-id="2ad9a-297"><strong>Calls with voice switch (%)</strong></span></span></p></td>
<td><p><span data-ttu-id="2ad9a-298">Да</span><span class="sxs-lookup"><span data-stu-id="2ad9a-298">Yes</span></span></p></td>
<td><p><span data-ttu-id="2ad9a-p128">Процент общего количества вызовов, которые были выполнены в полудуплексном режиме. В полудуплексном режиме взаимодействие может осуществляться только в одном направлении в каждый определенный момент времени аналогично тому, как пользователи по очереди слушают и говорят при связи по рации.</span><span class="sxs-lookup"><span data-stu-id="2ad9a-p128">Percentage of the total calls which had to be placed into half duplex mode. In half duplex mode, communication can travel in only one direction at a time, similar to the way users take turns when communicating with a walkie-talkie.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2ad9a-301"><strong>Эхо микрофона в (%)</strong></span><span class="sxs-lookup"><span data-stu-id="2ad9a-301"><strong>Echo microphone in (%)</strong></span></span></p></td>
<td><p><span data-ttu-id="2ad9a-302">Да</span><span class="sxs-lookup"><span data-stu-id="2ad9a-302">Yes</span></span></p></td>
<td><p><span data-ttu-id="2ad9a-p129">Процент времени, когда в потоке захвата микрофоном обнаруживался эхосигнал. Обычно низкие значения отображаются для гарнитур или телефонных трубок, а высокие значения – для телефонных или автономных динамиков. Для устройств, которые поддерживают встроенную возможность подавления акустического эхосигнала, высокие значения указывают утечку эхосигнала. Для других устройств эти единицы измерения не должны использоваться для оценки качества устройства.</span><span class="sxs-lookup"><span data-stu-id="2ad9a-p129">Percentage of time when echo was detected in the microphone capture stream. Typically, values are low for headsets or handsets, and higher for speaker phones or stand-alone speakers. For devices that support on-board acoustic echo cancellation, high values indicate echo leak. For other devices, this metric should not be used to evaluate device quality.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2ad9a-307"><strong>Переданные эхосигналы (%)</strong></span><span class="sxs-lookup"><span data-stu-id="2ad9a-307"><strong>Echo send (%)</strong></span></span></p></td>
<td><p><span data-ttu-id="2ad9a-308">Да</span><span class="sxs-lookup"><span data-stu-id="2ad9a-308">Yes</span></span></p></td>
<td><p><span data-ttu-id="2ad9a-309">Процент эхосигналов, переданных другим пользователям.</span><span class="sxs-lookup"><span data-stu-id="2ad9a-309">Percentage of echo transmitted to other users.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2ad9a-310"><strong>Вызовы с эхо (%)</strong></span><span class="sxs-lookup"><span data-stu-id="2ad9a-310"><strong>Calls with echo (%)</strong></span></span></p></td>
<td><p><span data-ttu-id="2ad9a-311">Да</span><span class="sxs-lookup"><span data-stu-id="2ad9a-311">Yes</span></span></p></td>
<td><p><span data-ttu-id="2ad9a-312">Процент общего количества вызовов, в ходе которых эхосигналы превысили допустимый уровень.</span><span class="sxs-lookup"><span data-stu-id="2ad9a-312">Percentage of the total calls that had echo exceeding the acceptable level.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

