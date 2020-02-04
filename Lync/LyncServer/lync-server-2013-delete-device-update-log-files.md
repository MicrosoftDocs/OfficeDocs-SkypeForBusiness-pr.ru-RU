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
ms.openlocfilehash: c684978445f727dc155fade59654ff6e2866f084
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734209"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-device-update-log-files-in-lync-server-2013"></a><span data-ttu-id="408fa-102">Удаление файлов журнала обновления устройств в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="408fa-102">Delete Device Update log files in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="408fa-103">_**Тема последнего изменения:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="408fa-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="408fa-104">Веб-служба обновления устройства хранит обширный набор файлов журнала.</span><span class="sxs-lookup"><span data-stu-id="408fa-104">The Device Update Web service keeps an extensive collection of log files.</span></span> <span data-ttu-id="408fa-105">Эта коллекция включает оба журнала аудита, выполненных самой службой, и файлы журналов, загруженные с клиентских устройств.</span><span class="sxs-lookup"><span data-stu-id="408fa-105">This collection includes both audit logs conducted by the service itself and log files uploaded from client devices.</span></span> <span data-ttu-id="408fa-106">Чтобы не допустить, чтобы сервер запускался с журналами веб-службы обновления устройств, вы, возможно, захотите очистить файлы журнала, которые использовались в течение определенного числа дней.</span><span class="sxs-lookup"><span data-stu-id="408fa-106">To prevent the server from filling up with Device Update Web service logs, you’ll probably want to clear it of log files that have been around for a certain number of days.</span></span> <span data-ttu-id="408fa-107">Задать это количество дней на основе действий по обновлению и количества клиентских устройств в вашей организации, а также с помощью панели управления Lync Server или командной консоли Lync Server Management.</span><span class="sxs-lookup"><span data-stu-id="408fa-107">Set this number of days based on update activity and the number of client devices in your organization, and by using Lync Server Control Panel or Lync Server Management Shell.</span></span>

<div>

## <a name="to-clear-the-device-update-log-by-using-lync-server-control-panel"></a><span data-ttu-id="408fa-108">Очистка журнала обновления устройства с помощью панели управления Lync Server</span><span class="sxs-lookup"><span data-stu-id="408fa-108">To clear the device update log by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="408fa-109">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="408fa-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="408fa-110">Дополнительные сведения о различных способах, которые можно использовать для запуска панели управления Lync Server, приведены в разделе [Открытие меню администрирования Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="408fa-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

2.  <span data-ttu-id="408fa-111">На панели навигации слева выберите пункт **Клиенты**, а затем — **Конфигурация журнала устройств**.</span><span class="sxs-lookup"><span data-stu-id="408fa-111">In the left navigation bar, click **Clients**, and then click **Device Log Configuration**.</span></span>

3.  <span data-ttu-id="408fa-112">На странице **конфигурации журнала устройства** дважды щелкните конфигурацию, которую вы хотите изменить.</span><span class="sxs-lookup"><span data-stu-id="408fa-112">On the **Device Log Configuration** page, double-click the configuration that you want to change.</span></span>

4.  <span data-ttu-id="408fa-113">В диалоговом окне **изменение параметров журнала** введите количество дней, в **течение которых нужно хранить файлы журнала (1-365)**.</span><span class="sxs-lookup"><span data-stu-id="408fa-113">In the **Edit Log Setting** dialog box, in **Number of days to keep log files (1-365)**, specifiy a number of days.</span></span>

5.  <span data-ttu-id="408fa-114">Нажмите **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="408fa-114">Click **Commit**.</span></span> <span data-ttu-id="408fa-115">Все файлы, которые были на сервере больше указанного количества дней, удаляются.</span><span class="sxs-lookup"><span data-stu-id="408fa-115">All files that have been on the server for more than the specified number of day are deleted.</span></span> <span data-ttu-id="408fa-116">Этот параметр будет применяться к этой конфигурации, пока вы не измените ее.</span><span class="sxs-lookup"><span data-stu-id="408fa-116">This setting will apply to this configuration until you change it.</span></span>

</div>

<div>

## <a name="clearing-the-device-update-log-by-using-the-windows-powershell-cmdlets"></a><span data-ttu-id="408fa-117">Очистка журнала обновления устройства с помощью командлетов Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="408fa-117">Clearing the Device Update Log by Using the Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="408fa-118">Вы можете очистить журналы обновления устройства с помощью Windows PowerShell и командлета **clear-ксдевицеупдателог** .</span><span class="sxs-lookup"><span data-stu-id="408fa-118">You can clear device update logs by using Windows PowerShell and the **Clear-CsDeviceUpdateLog** cmdlet.</span></span> <span data-ttu-id="408fa-119">Этот командлет можно выполнить либо из управляющей оболочки Lync Server 2013, либо из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="408fa-119">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="408fa-120">Подробнее об использовании удаленной оболочки Windows PowerShell для подключения к серверу Lync Server можно найти в статье "Краткое руководство по работе с Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" на <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>веб-сервере Lync Server Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="408fa-120">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>.</span></span>



</div>

<div>

## <a name="to-clear-device-update-logs-on-one-server"></a><span data-ttu-id="408fa-121">Очистка журналов обновления устройства на одном сервере</span><span class="sxs-lookup"><span data-stu-id="408fa-121">To clear device update logs on one server</span></span>

  - <span data-ttu-id="408fa-122">Следующая команда очищает журнал обновления устройства на веб-сервере atl-cs-001.litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="408fa-122">The following command clears the device update log on the Web server atl-cs-001.litwareinc.com.</span></span> <span data-ttu-id="408fa-123">Все записи журнала более 10 дней устарели (значение, указанное в параметре Дайсбакк), будет удалено из журнала.</span><span class="sxs-lookup"><span data-stu-id="408fa-123">All log entries more than 10 days old (the value specified by the DaysBack parameter) will be removed from the log.</span></span>
    
        Clear-CsDeviceUpdateLog -Identity "service:WebServer:atl-cs-001.litwareinc.com" -DaysBack 10

</div>

<div>

## <a name="to-clear-all-device-update-logs"></a><span data-ttu-id="408fa-124">Очистка всех журналов обновлений устройств</span><span class="sxs-lookup"><span data-stu-id="408fa-124">To clear all device update logs</span></span>

  - <span data-ttu-id="408fa-125">Эта команда используется для удаления устаревших записей (в данном примере — более 10 дней назад) из всех журналов обновлений для каждого обновления устройства, которые в настоящее время используются в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="408fa-125">This command removes outdated entries (in this example, entries more than 10 days old) from all the device update logs currently in use in your organization.</span></span>
    
        Get-CsService -WebServer | Foreach-Object {Clear-CsDeviceUpdateLog -Identity $_.Identity -DaysBack 10}

</div>

<span data-ttu-id="408fa-126">Дополнительные сведения можно найти в разделе справки по командлету [clear-ксдевицеупдателог](https://docs.microsoft.com/powershell/module/skype/Clear-CsDeviceUpdateLog) .</span><span class="sxs-lookup"><span data-stu-id="408fa-126">For details, see the Help topic for the [Clear-CsDeviceUpdateLog](https://docs.microsoft.com/powershell/module/skype/Clear-CsDeviceUpdateLog) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

