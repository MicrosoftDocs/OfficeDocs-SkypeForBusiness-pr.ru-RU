---
title: 'Lync Server 2013: удаление файлов журнала обновления устройств'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete Device Update log files
ms:assetid: 58d4097f-5bbf-4824-a04d-2a6555cd93c3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994039(v=OCS.15)
ms:contentKeyID: 51803949
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 576daa823dfd5bb8e6e7eb8c6bedeaa689780dbe
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48514466"
---
# <a name="delete-device-update-log-files-in-lync-server-2013"></a><span data-ttu-id="3e856-102">Удаление файлов журнала обновления устройств в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3e856-102">Delete Device Update log files in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3e856-103">_**Последнее изменение темы:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="3e856-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="3e856-104">Веб-служба обновления устройств хранит обширный набор файлов журналов.</span><span class="sxs-lookup"><span data-stu-id="3e856-104">The Device Update Web service keeps an extensive collection of log files.</span></span> <span data-ttu-id="3e856-105">Эта коллекция включает оба журнала аудита, выполненных самой службой, а также файлами журналов, отправленных с клиентских устройств.</span><span class="sxs-lookup"><span data-stu-id="3e856-105">This collection includes both audit logs conducted by the service itself and log files uploaded from client devices.</span></span> <span data-ttu-id="3e856-106">Чтобы не допустить переполнения сервера с помощью журналов веб-службы обновления устройств, вы, вероятно, захотите очистить файл журнала, который выполнялся в течение определенного числа дней.</span><span class="sxs-lookup"><span data-stu-id="3e856-106">To prevent the server from filling up with Device Update Web service logs, you’ll probably want to clear it of log files that have been around for a certain number of days.</span></span> <span data-ttu-id="3e856-107">Установите это количество дней в соответствии с действиями по обновлению и числом клиентских устройств в Организации, а также с помощью панели управления Lync Server или командной консоли Lync Server.</span><span class="sxs-lookup"><span data-stu-id="3e856-107">Set this number of days based on update activity and the number of client devices in your organization, and by using Lync Server Control Panel or Lync Server Management Shell.</span></span>

<div>

## <a name="to-clear-the-device-update-log-by-using-lync-server-control-panel"></a><span data-ttu-id="3e856-108">Очистка журнала обновлений устройств с помощью панели управления Lync Server</span><span class="sxs-lookup"><span data-stu-id="3e856-108">To clear the device update log by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="3e856-109">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="3e856-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="3e856-110">Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="3e856-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

2.  <span data-ttu-id="3e856-111">В левой области навигации последовательно выберите пункты **Клиенты** и **Конфигурация журналов устройств**.</span><span class="sxs-lookup"><span data-stu-id="3e856-111">In the left navigation bar, click **Clients**, and then click **Device Log Configuration**.</span></span>

3.  <span data-ttu-id="3e856-112">На странице **Конфигурация журналов устройств** дважды щелкните конфигурацию, которую требуется изменить.</span><span class="sxs-lookup"><span data-stu-id="3e856-112">On the **Device Log Configuration** page, double-click the configuration that you want to change.</span></span>

4.  <span data-ttu-id="3e856-113">В диалоговом окне **изменение параметров журнала** в поле **число дней хранения файлов журнала (1-365)** укажите количество дней.</span><span class="sxs-lookup"><span data-stu-id="3e856-113">In the **Edit Log Setting** dialog box, in **Number of days to keep log files (1-365)**, specifiy a number of days.</span></span>

5.  <span data-ttu-id="3e856-114">Щелкните **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="3e856-114">Click **Commit**.</span></span> <span data-ttu-id="3e856-115">Все файлы, находились на сервере дольше указанного числа дней, удаляются.</span><span class="sxs-lookup"><span data-stu-id="3e856-115">All files that have been on the server for more than the specified number of day are deleted.</span></span> <span data-ttu-id="3e856-116">Этот параметр применяется к этой конфигурации, пока не будет изменен.</span><span class="sxs-lookup"><span data-stu-id="3e856-116">This setting will apply to this configuration until you change it.</span></span>

</div>

<div>

## <a name="clearing-the-device-update-log-by-using-the-windows-powershell-cmdlets"></a><span data-ttu-id="3e856-117">Очистка журнала обновлений устройств с помощью командлетов Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="3e856-117">Clearing the Device Update Log by Using the Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="3e856-118">Вы можете очистить журналы обновления устройств с помощью Windows PowerShell и командлета **clear – ксдевицеупдателог** .</span><span class="sxs-lookup"><span data-stu-id="3e856-118">You can clear device update logs by using Windows PowerShell and the **Clear-CsDeviceUpdateLog** cmdlet.</span></span> <span data-ttu-id="3e856-119">Этот командлет можно запустить либо из командной консоли Lync Server 2013, либо из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3e856-119">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="3e856-120">Сведения об использовании удаленной оболочки Windows PowerShell для подключения к Lync Server приведены в статье "Краткое руководство по управлению Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" в статье Lync Server Windows PowerShell в блоге <A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A> .</span><span class="sxs-lookup"><span data-stu-id="3e856-120">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at <A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A>.</span></span>



</div>

<div>

## <a name="to-clear-device-update-logs-on-one-server"></a><span data-ttu-id="3e856-121">Очистка журналов обновления устройств на одном сервере</span><span class="sxs-lookup"><span data-stu-id="3e856-121">To clear device update logs on one server</span></span>

  - <span data-ttu-id="3e856-122">Следующая команда очищает журнал обновлений устройств на веб-сервере atl-cs-001.litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="3e856-122">The following command clears the device update log on the Web server atl-cs-001.litwareinc.com.</span></span> <span data-ttu-id="3e856-123">Все записи журнала старше 10 дней (значение, указанное параметром Дайсбакк), будет удалено из журнала.</span><span class="sxs-lookup"><span data-stu-id="3e856-123">All log entries more than 10 days old (the value specified by the DaysBack parameter) will be removed from the log.</span></span>
    
        Clear-CsDeviceUpdateLog -Identity "service:WebServer:atl-cs-001.litwareinc.com" -DaysBack 10

</div>

<div>

## <a name="to-clear-all-device-update-logs"></a><span data-ttu-id="3e856-124">Очистка всех журналов обновлений устройств</span><span class="sxs-lookup"><span data-stu-id="3e856-124">To clear all device update logs</span></span>

  - <span data-ttu-id="3e856-125">Эта команда удаляет устаревшие записи (в данном примере записи старше 10 дней) из всех журналов обновления устройств, используемых в настоящее время в Организации.</span><span class="sxs-lookup"><span data-stu-id="3e856-125">This command removes outdated entries (in this example, entries more than 10 days old) from all the device update logs currently in use in your organization.</span></span>
    
        Get-CsService -WebServer | Foreach-Object {Clear-CsDeviceUpdateLog -Identity $_.Identity -DaysBack 10}

</div>

<span data-ttu-id="3e856-126">Дополнительные сведения см. в разделе справки для командлета [clear – ксдевицеупдателог](https://docs.microsoft.com/powershell/module/skype/Clear-CsDeviceUpdateLog) .</span><span class="sxs-lookup"><span data-stu-id="3e856-126">For details, see the Help topic for the [Clear-CsDeviceUpdateLog](https://docs.microsoft.com/powershell/module/skype/Clear-CsDeviceUpdateLog) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

