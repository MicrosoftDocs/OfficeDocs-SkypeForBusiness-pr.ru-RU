---
title: 'Lync Server 2013: изменение параметров для файлов журнала обновления устройства'
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
ms.openlocfilehash: 88d75086f0532205c2897f7e86d49f50072aaa89
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756933"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="modify-settings-for-device-update-log-files-in-lync-server-2013"></a><span data-ttu-id="0cbeb-102">Изменение параметров для файлов журнала обновления устройства в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0cbeb-102">Modify settings for Device Update log files in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0cbeb-103">_**Тема последнего изменения:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="0cbeb-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="0cbeb-104">Вы можете изменить параметры, которые будут регистрироваться в вашей организации с помощью панели управления Lync Server или консоли управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="0cbeb-104">You can change settings for how device update information is logged in your organization by using Lync Server Control Panel or Lync Server Management Shell.</span></span> <span data-ttu-id="0cbeb-105">В приведенной ниже таблице показано, какие параметры можно изменять, а также какие инструменты используются для изменения параметров.</span><span class="sxs-lookup"><span data-stu-id="0cbeb-105">The following table shows which settings are modifiable, and which tool(s) you use to modify the settings.</span></span>

<span data-ttu-id="0cbeb-106">Параметры журнала можно изменять и применять глобально или на уровне отдельных сайтов.</span><span class="sxs-lookup"><span data-stu-id="0cbeb-106">Log settings can be changed and applied globally, or per site.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0cbeb-107">Для изменения</span><span class="sxs-lookup"><span data-stu-id="0cbeb-107">To change</span></span></th>
<th><span data-ttu-id="0cbeb-108">Использование</span><span class="sxs-lookup"><span data-stu-id="0cbeb-108">Use</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0cbeb-109">Максимальный размер файла журнала (в байтах)</span><span class="sxs-lookup"><span data-stu-id="0cbeb-109">The maximum size (in bytes) for a log file</span></span></p></td>
<td><p><span data-ttu-id="0cbeb-110">Панель управления Lync Server</span><span class="sxs-lookup"><span data-stu-id="0cbeb-110">Lync Server Control Panel</span></span></p>
<p><span data-ttu-id="0cbeb-111">/</span><span class="sxs-lookup"><span data-stu-id="0cbeb-111">-or-</span></span></p>
<p><span data-ttu-id="0cbeb-112">Командная консоль Lync Server</span><span class="sxs-lookup"><span data-stu-id="0cbeb-112">Lync Server Management Shell</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0cbeb-113">Максимальный объем данных (в байтах), которые могут храниться в кэше</span><span class="sxs-lookup"><span data-stu-id="0cbeb-113">The maximum amount of information (in bytes) that can be held in the cache</span></span></p></td>
<td><p><span data-ttu-id="0cbeb-114">Панель управления Lync Server</span><span class="sxs-lookup"><span data-stu-id="0cbeb-114">Lync Server Control Panel</span></span></p>
<p><span data-ttu-id="0cbeb-115">/</span><span class="sxs-lookup"><span data-stu-id="0cbeb-115">-or-</span></span></p>
<p><span data-ttu-id="0cbeb-116">Командная консоль Lync Server</span><span class="sxs-lookup"><span data-stu-id="0cbeb-116">Lync Server Management Shell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0cbeb-117">Частота записи кэшированных данных в файл журнала (в минутах)</span><span class="sxs-lookup"><span data-stu-id="0cbeb-117">How often (in minutes) to write cached information to the log file</span></span></p></td>
<td><p><span data-ttu-id="0cbeb-118">Панель управления Lync Server</span><span class="sxs-lookup"><span data-stu-id="0cbeb-118">Lync Server Control Panel</span></span></p>
<p><span data-ttu-id="0cbeb-119">/</span><span class="sxs-lookup"><span data-stu-id="0cbeb-119">-or-</span></span></p>
<p><span data-ttu-id="0cbeb-120">Командная консоль Lync Server</span><span class="sxs-lookup"><span data-stu-id="0cbeb-120">Lync Server Management Shell</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0cbeb-121">Продолжительность хранения файлов журнала (в днях)</span><span class="sxs-lookup"><span data-stu-id="0cbeb-121">How long (in days) to keep log files</span></span></p></td>
<td><p><span data-ttu-id="0cbeb-122">Панель управления Lync Server</span><span class="sxs-lookup"><span data-stu-id="0cbeb-122">Lync Server Control Panel</span></span></p>
<p><span data-ttu-id="0cbeb-123">/</span><span class="sxs-lookup"><span data-stu-id="0cbeb-123">-or-</span></span></p>
<p><span data-ttu-id="0cbeb-124">Командная консоль Lync Server</span><span class="sxs-lookup"><span data-stu-id="0cbeb-124">Lync Server Management Shell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0cbeb-125">Время (в днях) для проверки просроченных файлов, которые нужно удалить</span><span class="sxs-lookup"><span data-stu-id="0cbeb-125">When (time of day) to check for expired files that should be deleted</span></span></p></td>
<td><p><span data-ttu-id="0cbeb-126">Командная консоль Lync Server</span><span class="sxs-lookup"><span data-stu-id="0cbeb-126">Lync Server Management Shell</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0cbeb-127">Какие расширения файлов журналов разрешаются</span><span class="sxs-lookup"><span data-stu-id="0cbeb-127">What log file extensions to permit</span></span></p></td>
<td><p><span data-ttu-id="0cbeb-128">Командная консоль Lync Server</span><span class="sxs-lookup"><span data-stu-id="0cbeb-128">Lync Server Management Shell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0cbeb-129">Типы файлов журналов, которые нужно сохранить</span><span class="sxs-lookup"><span data-stu-id="0cbeb-129">Which log file types to retain</span></span></p></td>
<td><p><span data-ttu-id="0cbeb-130">Командная консоль Lync Server</span><span class="sxs-lookup"><span data-stu-id="0cbeb-130">Lync Server Management Shell</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="to-change-logging-settings-by-using-lync-server-control-panel"></a><span data-ttu-id="0cbeb-131">Изменение параметров ведения журнала с помощью панели управления Lync Server</span><span class="sxs-lookup"><span data-stu-id="0cbeb-131">To change logging settings by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="0cbeb-132">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="0cbeb-132">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="0cbeb-133">Дополнительные сведения о различных способах, которые можно использовать для запуска панели управления Lync Server, приведены в разделе [Открытие меню администрирования Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="0cbeb-133">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

2.  <span data-ttu-id="0cbeb-134">На панели навигации слева выберите пункт **Клиенты**, а затем — **Конфигурация журнала устройств**.</span><span class="sxs-lookup"><span data-stu-id="0cbeb-134">In the left navigation bar, click **Clients**, and then click **Device Log Configuration**.</span></span>

3.  <span data-ttu-id="0cbeb-135">На странице **конфигурации журнала устройства** дважды щелкните конфигурацию, которую вы хотите изменить.</span><span class="sxs-lookup"><span data-stu-id="0cbeb-135">On the **Device Log Configuration** page, double-click the configuration that you want to change.</span></span>

4.  <span data-ttu-id="0cbeb-136">В диалоговом окне **изменение параметров журнала** измените любые из указанных ниже параметров.</span><span class="sxs-lookup"><span data-stu-id="0cbeb-136">In the **Edit Log Setting** dialog box, change any of the following settings:</span></span>
    
      - <span data-ttu-id="0cbeb-137">**Максимальный размер файла (в байтах)**   — максимальный размер, который может быть указан в файле журнала до его очистки.</span><span class="sxs-lookup"><span data-stu-id="0cbeb-137">**Maximum file size (bytes)**   Specifies the maximum size a log file can become before it is purged.</span></span> <span data-ttu-id="0cbeb-138">Значение по умолчанию — 1 024 000 байт (1 МБ).</span><span class="sxs-lookup"><span data-stu-id="0cbeb-138">The default is 1,024,000 bytes (1 MB).</span></span>
    
      - <span data-ttu-id="0cbeb-139">**Максимальный размер кэша (в байтах)**   — максимальный объем данных (в байтах), которые могут храниться в кэше файлов журналов, прежде чем этот кэш должен быть очищен и данные записываются в файл журнала.</span><span class="sxs-lookup"><span data-stu-id="0cbeb-139">**Maximum cache size (bytes)**   Specifies the maximum amount of information (in bytes) that can be held in the log file cache before that cache must be cleared and the data is written to a log file.</span></span> <span data-ttu-id="0cbeb-140">Значение по умолчанию — 512 000 байт (0,5 МБ).</span><span class="sxs-lookup"><span data-stu-id="0cbeb-140">The default is 512,000 bytes (0.5 MB).</span></span>
    
      - <span data-ttu-id="0cbeb-141">**Количество минут для кэша очистки (1-60)**   показывает, как часто данные, хранящиеся в кэше файлов журналов, записываются в файл журнала.</span><span class="sxs-lookup"><span data-stu-id="0cbeb-141">**Number of minutes to flush cache (1-60)**   Indicates how often information stored in the log file cache is written to the actual log file.</span></span> <span data-ttu-id="0cbeb-142">После того как данные записываются в журнал, кэш очищается.</span><span class="sxs-lookup"><span data-stu-id="0cbeb-142">After the data is logged, the cache is cleared.</span></span> <span data-ttu-id="0cbeb-143">По умолчанию используется значение 5 минут.</span><span class="sxs-lookup"><span data-stu-id="0cbeb-143">The default is five minutes.</span></span>
    
      - <span data-ttu-id="0cbeb-144">**Число дней для хранения файлов журнала (1-365)**   указывает количество дней, в течение которых хранятся файлы журнала, прежде чем они будут очищены.</span><span class="sxs-lookup"><span data-stu-id="0cbeb-144">**Number of days to keep log files (1-365)**   Specifies the number of days the log files are kept before they are purged.</span></span> <span data-ttu-id="0cbeb-145">Значение по умолчанию — 10 дней.</span><span class="sxs-lookup"><span data-stu-id="0cbeb-145">The default is 10 days.</span></span>

5.  <span data-ttu-id="0cbeb-146">Нажмите **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="0cbeb-146">Click **Commit**.</span></span>

</div>

<div>

## <a name="changing-logging-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="0cbeb-147">Изменение параметров ведения журнала с помощью командлетов Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="0cbeb-147">Changing Logging Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="0cbeb-148">Параметры файла журнала обновления устройства можно изменить с помощью Windows PowerShell и командлета **Set-ксдевицеупдатеконфигуратион** .</span><span class="sxs-lookup"><span data-stu-id="0cbeb-148">Device update log file settings can be modified by using Windows PowerShell and the **Set-CsDeviceUpdateConfiguration** cmdlet.</span></span> <span data-ttu-id="0cbeb-149">Этот командлет можно выполнить либо из управляющей оболочки Lync Server 2013, либо из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0cbeb-149">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="0cbeb-150">Подробнее об использовании удаленной оболочки Windows PowerShell для подключения к серверу Lync Server можно найти в статье "Краткое руководство по работе с Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" на <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>веб-сервере Lync Server Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0cbeb-150">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>.</span></span>



</div>

<span data-ttu-id="0cbeb-151">В следующих примерах показано несколько способов использования **Set-ксдевицеупдатеконфигуратион** для изменения параметров.</span><span class="sxs-lookup"><span data-stu-id="0cbeb-151">The following examples show a couple of the ways that you can use **Set-CsDeviceUpdateConfiguration** to modify settings.</span></span>

<div>

## <a name="to-modify-the-maximum-log-file-size-and-the-log-cleanup-interval"></a><span data-ttu-id="0cbeb-152">Изменение максимального размера файла журнала и интервала очистки журнала</span><span class="sxs-lookup"><span data-stu-id="0cbeb-152">To modify the maximum log file size and the log cleanup interval</span></span>

  - <span data-ttu-id="0cbeb-153">Следующая команда изменяет параметры журнала обновления устройства, примененные к сайту Redmond.</span><span class="sxs-lookup"><span data-stu-id="0cbeb-153">The following command modifies the device update log settings applied to the Redmond site.</span></span> <span data-ttu-id="0cbeb-154">В этом примере для максимального размера файла журнала задано значение 204800 байт, а для интервала очистки журнала установлено значение 14 дней.</span><span class="sxs-lookup"><span data-stu-id="0cbeb-154">In this example, the maximum log file size is set to 204800 bytes and the log cleanup interval is set to 14 days.</span></span>
    
        Set-CsDeviceUpdateConfiguration -Identity "site:Redmond" -MaxLogFileSize 204800 -LogCleanUpInterval 14.00:00:00

</div>

<div>

## <a name="to-modify-the-log-cleanup-time-of-day"></a><span data-ttu-id="0cbeb-155">Изменение времени очистки журнала за день</span><span class="sxs-lookup"><span data-stu-id="0cbeb-155">To modify the log cleanup time of day</span></span>

  - <span data-ttu-id="0cbeb-156">Эта команда задает время очистки журнала для сайта Redmond на 3:00 AM.</span><span class="sxs-lookup"><span data-stu-id="0cbeb-156">This command sets the log cleanup time for the Redmond site to 3:00 AM.</span></span>
    
        Set-CsDeviceUpdateConfiguration -Identity "site:Redmond" -LogCleanupTimeOfDay 03:00

</div>

<span data-ttu-id="0cbeb-157">Дополнительные сведения можно найти в разделе справки по командлету [Set-ксдевицеупдатеконфигуратион](https://docs.microsoft.com/powershell/module/skype/Set-CsDeviceUpdateConfiguration) .</span><span class="sxs-lookup"><span data-stu-id="0cbeb-157">For details, see the Help topic for the [Set-CsDeviceUpdateConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsDeviceUpdateConfiguration) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

