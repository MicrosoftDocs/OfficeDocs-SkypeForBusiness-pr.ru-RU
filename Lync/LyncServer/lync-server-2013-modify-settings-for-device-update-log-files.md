---
title: 'Lync Server 2013: изменение параметров для файлов журнала обновления устройств'
description: 'Lync Server 2013: изменение параметров для файлов журнала обновления устройств.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Modify settings for Device Update log files
ms:assetid: 9b57f126-1853-43b3-bbd4-06401e6498bd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182554(v=OCS.15)
ms:contentKeyID: 48184975
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4c2086e11a67207a00ca99773cc818106b16d05c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566975"
---
# <a name="modify-settings-for-device-update-log-files-in-lync-server-2013"></a><span data-ttu-id="a132d-103">Изменение параметров для файлов журнала обновления устройств в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a132d-103">Modify settings for Device Update log files in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a132d-104">_**Последнее изменение темы:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="a132d-104">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="a132d-105">С помощью панели управления Lync Server или командной консоли Lync Server можно изменить параметры регистрации сведений об обновлениях устройств в Организации.</span><span class="sxs-lookup"><span data-stu-id="a132d-105">You can change settings for how device update information is logged in your organization by using Lync Server Control Panel or Lync Server Management Shell.</span></span> <span data-ttu-id="a132d-106">В следующей таблице приведены параметры, доступные для изменения, а также средства, используемые для изменения параметров.</span><span class="sxs-lookup"><span data-stu-id="a132d-106">The following table shows which settings are modifiable, and which tool(s) you use to modify the settings.</span></span>

<span data-ttu-id="a132d-107">Параметры журнала можно изменять и применять глобально или на уровне сайта.</span><span class="sxs-lookup"><span data-stu-id="a132d-107">Log settings can be changed and applied globally, or per site.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a132d-108">Чтобы изменить</span><span class="sxs-lookup"><span data-stu-id="a132d-108">To change</span></span></th>
<th><span data-ttu-id="a132d-109">Использование</span><span class="sxs-lookup"><span data-stu-id="a132d-109">Use</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a132d-110">Максимальный размер файла журнала (в байтах)</span><span class="sxs-lookup"><span data-stu-id="a132d-110">The maximum size (in bytes) for a log file</span></span></p></td>
<td><p><span data-ttu-id="a132d-111">Панель управления сервера Lync</span><span class="sxs-lookup"><span data-stu-id="a132d-111">Lync Server Control Panel</span></span></p>
<p><span data-ttu-id="a132d-112">-или-</span><span class="sxs-lookup"><span data-stu-id="a132d-112">-or-</span></span></p>
<p><span data-ttu-id="a132d-113">Командная консоль Lync Server</span><span class="sxs-lookup"><span data-stu-id="a132d-113">Lync Server Management Shell</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a132d-114">Максимальный объем данных (в байтах), которые могут храниться в кэше</span><span class="sxs-lookup"><span data-stu-id="a132d-114">The maximum amount of information (in bytes) that can be held in the cache</span></span></p></td>
<td><p><span data-ttu-id="a132d-115">Панель управления сервера Lync</span><span class="sxs-lookup"><span data-stu-id="a132d-115">Lync Server Control Panel</span></span></p>
<p><span data-ttu-id="a132d-116">-или-</span><span class="sxs-lookup"><span data-stu-id="a132d-116">-or-</span></span></p>
<p><span data-ttu-id="a132d-117">Командная консоль Lync Server</span><span class="sxs-lookup"><span data-stu-id="a132d-117">Lync Server Management Shell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a132d-118">Частота записи кэшированных данных в файл журнала (в минутах)</span><span class="sxs-lookup"><span data-stu-id="a132d-118">How often (in minutes) to write cached information to the log file</span></span></p></td>
<td><p><span data-ttu-id="a132d-119">Панель управления сервера Lync</span><span class="sxs-lookup"><span data-stu-id="a132d-119">Lync Server Control Panel</span></span></p>
<p><span data-ttu-id="a132d-120">-или-</span><span class="sxs-lookup"><span data-stu-id="a132d-120">-or-</span></span></p>
<p><span data-ttu-id="a132d-121">Командная консоль Lync Server</span><span class="sxs-lookup"><span data-stu-id="a132d-121">Lync Server Management Shell</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a132d-122">Срок хранения файлов журнала (в днях)</span><span class="sxs-lookup"><span data-stu-id="a132d-122">How long (in days) to keep log files</span></span></p></td>
<td><p><span data-ttu-id="a132d-123">Панель управления сервера Lync</span><span class="sxs-lookup"><span data-stu-id="a132d-123">Lync Server Control Panel</span></span></p>
<p><span data-ttu-id="a132d-124">-или-</span><span class="sxs-lookup"><span data-stu-id="a132d-124">-or-</span></span></p>
<p><span data-ttu-id="a132d-125">Командная консоль Lync Server</span><span class="sxs-lookup"><span data-stu-id="a132d-125">Lync Server Management Shell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a132d-126">Время (в днях) проверки просроченных файлов, которые следует удалить</span><span class="sxs-lookup"><span data-stu-id="a132d-126">When (time of day) to check for expired files that should be deleted</span></span></p></td>
<td><p><span data-ttu-id="a132d-127">Командная консоль Lync Server</span><span class="sxs-lookup"><span data-stu-id="a132d-127">Lync Server Management Shell</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a132d-128">Какие расширения файлов журналов разрешаются</span><span class="sxs-lookup"><span data-stu-id="a132d-128">What log file extensions to permit</span></span></p></td>
<td><p><span data-ttu-id="a132d-129">Командная консоль Lync Server</span><span class="sxs-lookup"><span data-stu-id="a132d-129">Lync Server Management Shell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a132d-130">Типы файлов журналов, которые необходимо сохранить</span><span class="sxs-lookup"><span data-stu-id="a132d-130">Which log file types to retain</span></span></p></td>
<td><p><span data-ttu-id="a132d-131">Командная консоль Lync Server</span><span class="sxs-lookup"><span data-stu-id="a132d-131">Lync Server Management Shell</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="to-change-logging-settings-by-using-lync-server-control-panel"></a><span data-ttu-id="a132d-132">Изменение параметров ведения журнала с помощью панели управления Lync Server</span><span class="sxs-lookup"><span data-stu-id="a132d-132">To change logging settings by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="a132d-133">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="a132d-133">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="a132d-134">Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="a132d-134">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

2.  <span data-ttu-id="a132d-135">В левой области навигации последовательно выберите пункты **Клиенты** и **Конфигурация журналов устройств**.</span><span class="sxs-lookup"><span data-stu-id="a132d-135">In the left navigation bar, click **Clients**, and then click **Device Log Configuration**.</span></span>

3.  <span data-ttu-id="a132d-136">На странице **Конфигурация журналов устройств** дважды щелкните конфигурацию, которую требуется изменить.</span><span class="sxs-lookup"><span data-stu-id="a132d-136">On the **Device Log Configuration** page, double-click the configuration that you want to change.</span></span>

4.  <span data-ttu-id="a132d-137">В диалоговом окне **изменение параметров журнала** измените любой из следующих параметров:</span><span class="sxs-lookup"><span data-stu-id="a132d-137">In the **Edit Log Setting** dialog box, change any of the following settings:</span></span>
    
      - <span data-ttu-id="a132d-138">**Максимальный размер файла (в байтах)**     Задает максимальный размер файла журнала до его очистки.</span><span class="sxs-lookup"><span data-stu-id="a132d-138">**Maximum file size (bytes)**   Specifies the maximum size a log file can become before it is purged.</span></span> <span data-ttu-id="a132d-139">Значение по умолчанию 1 024 000 байт (1 МБ).</span><span class="sxs-lookup"><span data-stu-id="a132d-139">The default is 1,024,000 bytes (1 MB).</span></span>
    
      - <span data-ttu-id="a132d-140">**Максимальный размер кэша (в байтах)**     Задает максимальный объем данных (в байтах), которые могут храниться в кэше файлов журнала до очистки этого кэша и записи данных в файл журнала.</span><span class="sxs-lookup"><span data-stu-id="a132d-140">**Maximum cache size (bytes)**   Specifies the maximum amount of information (in bytes) that can be held in the log file cache before that cache must be cleared and the data is written to a log file.</span></span> <span data-ttu-id="a132d-141">Значение по умолчанию 512 000 байт (0,5 МБ).</span><span class="sxs-lookup"><span data-stu-id="a132d-141">The default is 512,000 bytes (0.5 MB).</span></span>
    
      - <span data-ttu-id="a132d-142">**Количество минут до очистки кэша (1-60)**     Указывает, как часто данные, хранящиеся в кэше файлов журналов, записываются в фактический файл журнала.</span><span class="sxs-lookup"><span data-stu-id="a132d-142">**Number of minutes to flush cache (1-60)**   Indicates how often information stored in the log file cache is written to the actual log file.</span></span> <span data-ttu-id="a132d-143">После того как данные заносятся в журнал, кэш очищается.</span><span class="sxs-lookup"><span data-stu-id="a132d-143">After the data is logged, the cache is cleared.</span></span> <span data-ttu-id="a132d-144">Значение по умолчанию 5 минут.</span><span class="sxs-lookup"><span data-stu-id="a132d-144">The default is five minutes.</span></span>
    
      - <span data-ttu-id="a132d-145">**Число дней хранения файлов журнала (1-365)**     Указывает количество дней, в течение которых файлы журнала хранятся до очистки.</span><span class="sxs-lookup"><span data-stu-id="a132d-145">**Number of days to keep log files (1-365)**   Specifies the number of days the log files are kept before they are purged.</span></span> <span data-ttu-id="a132d-146">Значение по умолчанию — 10 дней.</span><span class="sxs-lookup"><span data-stu-id="a132d-146">The default is 10 days.</span></span>

5.  <span data-ttu-id="a132d-147">Нажмите кнопку **Зафиксировать**.</span><span class="sxs-lookup"><span data-stu-id="a132d-147">Click **Commit**.</span></span>

</div>

<div>

## <a name="changing-logging-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="a132d-148">Изменение параметров ведения журналов с помощью командлетов Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="a132d-148">Changing Logging Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="a132d-149">Параметры файла журнала обновления устройств можно изменить с помощью Windows PowerShell и командлета **Set – CsDeviceUpdateConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="a132d-149">Device update log file settings can be modified by using Windows PowerShell and the **Set-CsDeviceUpdateConfiguration** cmdlet.</span></span> <span data-ttu-id="a132d-150">Этот командлет можно запустить либо из командной консоли Lync Server 2013, либо из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a132d-150">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a132d-151">Сведения об использовании удаленной оболочки Windows PowerShell для подключения к Lync Server приведены в статье "Краткое руководство по управлению Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" в статье Lync Server Windows PowerShell в блоге <A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A> .</span><span class="sxs-lookup"><span data-stu-id="a132d-151">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at <A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A>.</span></span>



</div>

<span data-ttu-id="a132d-152">В следующих примерах показаны несколько способов, которые можно использовать для изменения параметров **Set – CsDeviceUpdateConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="a132d-152">The following examples show a couple of the ways that you can use **Set-CsDeviceUpdateConfiguration** to modify settings.</span></span>

<div>

## <a name="to-modify-the-maximum-log-file-size-and-the-log-cleanup-interval"></a><span data-ttu-id="a132d-153">Изменение максимального размера файла журнала и интервала очистки журнала</span><span class="sxs-lookup"><span data-stu-id="a132d-153">To modify the maximum log file size and the log cleanup interval</span></span>

  - <span data-ttu-id="a132d-154">Следующая команда изменяет параметры журнала обновления устройств, применяемые к сайту Redmond.</span><span class="sxs-lookup"><span data-stu-id="a132d-154">The following command modifies the device update log settings applied to the Redmond site.</span></span> <span data-ttu-id="a132d-155">В этом примере для максимального размера файла журнала задано значение 204800 байт, а для интервала очистки журнала задано значение 14 дней.</span><span class="sxs-lookup"><span data-stu-id="a132d-155">In this example, the maximum log file size is set to 204800 bytes and the log cleanup interval is set to 14 days.</span></span>
    
        Set-CsDeviceUpdateConfiguration -Identity "site:Redmond" -MaxLogFileSize 204800 -LogCleanUpInterval 14.00:00:00

</div>

<div>

## <a name="to-modify-the-log-cleanup-time-of-day"></a><span data-ttu-id="a132d-156">Изменение времени очистки журнала в день</span><span class="sxs-lookup"><span data-stu-id="a132d-156">To modify the log cleanup time of day</span></span>

  - <span data-ttu-id="a132d-157">Эта команда задает время очистки журнала для сайта Redmond равным 3:00 AM.</span><span class="sxs-lookup"><span data-stu-id="a132d-157">This command sets the log cleanup time for the Redmond site to 3:00 AM.</span></span>
    
        Set-CsDeviceUpdateConfiguration -Identity "site:Redmond" -LogCleanupTimeOfDay 03:00

</div>

<span data-ttu-id="a132d-158">Дополнительные сведения см. в разделе справки для командлета [Set – CsDeviceUpdateConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsDeviceUpdateConfiguration) .</span><span class="sxs-lookup"><span data-stu-id="a132d-158">For details, see the Help topic for the [Set-CsDeviceUpdateConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsDeviceUpdateConfiguration) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

