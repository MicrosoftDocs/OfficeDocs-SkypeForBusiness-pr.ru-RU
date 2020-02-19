---
title: 'Lync Server 2013: включение записи сведений о вызовах'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable call detail recording
ms:assetid: 3b28e432-596f-45a5-a070-577d6fa748d9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520980(v=OCS.15)
ms:contentKeyID: 48183865
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1c66c63b4890c011be91236516a15a32c0065a8f
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42136286"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="enable-call-detail-recording-in-lync-server-2013"></a><span data-ttu-id="92831-102">Включение регистрации вызовов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="92831-102">Enable call detail recording in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="92831-103">_**Последнее изменение темы:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="92831-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="92831-p101">Функция регистрации вызовов (CDR) записывает сведения об использовании и диагностические данные для одноранговых операций, включая обмен мгновенными сообщениями, звонки VoIP, общий доступ к приложениям, передачу файлов и собрания. С помощью данных об использовании можно вычислить рентабельность инвестиций, а диагностические данные можно использовать при поиске и устранении проблем с одноранговыми операциями и собраниями.</span><span class="sxs-lookup"><span data-stu-id="92831-p101">Call detail recording (CDR) records usage and diagnostic information about peer-to-peer activities including instance messaging, Voice over Internet Protocol (VoIP) calls, application sharing, file transfer, and meetings. The usage data can be used to calculate return on investment (ROI) and the diagnostic data can be used to troubleshoot peer-to-peer activities and meetings.</span></span>

<span data-ttu-id="92831-106">Используйте следующую процедуру, чтобы включить регистрацию вызовов для всей своей организации или каждого ее сайта.</span><span class="sxs-lookup"><span data-stu-id="92831-106">Use the following procedure to enable CDR for your whole organization or each site in your organization.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="92831-107">Чтобы включить CDR, необходимо сначала настроить мониторинг и базу данных мониторинга.</span><span class="sxs-lookup"><span data-stu-id="92831-107">In order to enable CDR you must configure monitoring and a monitoring database.</span></span> <span data-ttu-id="92831-108">Дополнительные сведения см <A href="lync-server-2013-deploying-monitoring.md">в разделе Deploying Monitoring in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="92831-108">For details, see <A href="lync-server-2013-deploying-monitoring.md">Deploying monitoring in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-enable-cdr-with-lync-server-control-panel"></a><span data-ttu-id="92831-109">Включение CDR с помощью панели управления Lync Server</span><span class="sxs-lookup"><span data-stu-id="92831-109">To enable CDR with Lync Server Control Panel</span></span>

1.  <span data-ttu-id="92831-110">Из учетной записи пользователя, которая является членом группы RTCUniversalServerAdmins (или имеет эквивалентные права пользователя) или назначается роли CsServerAdministrator или CsAdministrator, войдите на любой компьютер в сети, в которой развернут Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="92831-110">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="92831-111">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="92831-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="92831-112">Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="92831-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="92831-113">В левой панели навигации щелкните элемент **Мониторинг и архивация**, затем **Служба регистрации вызовов**.</span><span class="sxs-lookup"><span data-stu-id="92831-113">In the left navigation bar, click **Monitoring and Archiving**, and then click **Call Detail Recording**.</span></span>

4.  <span data-ttu-id="92831-114">На странице **Служба регистрации вызовов** выберите соответствующий сайт в таблице, щелкните элемент **Действие** и затем **Включить CDR**.</span><span class="sxs-lookup"><span data-stu-id="92831-114">On the **Call Detail Recording** page, click the appropriate site from the table, click **Action**, and then click **Enable CDR**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="92831-115">По умолчанию функция CDR включена.</span><span class="sxs-lookup"><span data-stu-id="92831-115">CDR is enabled by default.</span></span>

    
    </div>

</div>

<div>

## <a name="enabling-cdr-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="92831-116">Включение CDR с помощью командлетов Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="92831-116">Enabling CDR by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="92831-117">Вы можете включить CDR с помощью Windows PowerShell и командлета **Set – CsCdrConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="92831-117">You can enable CDR by using Windows PowerShell and the **Set-CsCdrConfiguration** cmdlet.</span></span> <span data-ttu-id="92831-118">Этот командлет можно выполнить либо из командной консоли Lync Server 2013, либо из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="92831-118">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="92831-119">Сведения об использовании удаленной оболочки Windows PowerShell для подключения к Lync Server приведены в статье "Краткое руководство по управлению Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" в [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)статье Lync Server Windows PowerShell в блоге.</span><span class="sxs-lookup"><span data-stu-id="92831-119">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-enable-cdr-for-a-single-location"></a><span data-ttu-id="92831-120">Включение CDR для отдельного места</span><span class="sxs-lookup"><span data-stu-id="92831-120">To enable CDR for a single location</span></span>

  - <span data-ttu-id="92831-121">Чтобы отключить CDR, задайте для параметра EnableCDR значение True ($True).</span><span class="sxs-lookup"><span data-stu-id="92831-121">To disable CDR, set the EnableCDR parameter to True ($True).</span></span>
    
        Set-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $True

</div>

<div>

## <a name="to-disable-cdr-for-a-single-location"></a><span data-ttu-id="92831-122">Чтобы отключить CDR для отдельного места</span><span class="sxs-lookup"><span data-stu-id="92831-122">To disable CDR for a single location</span></span>

  - <span data-ttu-id="92831-123">Чтобы отключить CDR, задайте для параметра EnableCDR значение False ($False).</span><span class="sxs-lookup"><span data-stu-id="92831-123">To disable CDR, set the EnableCDR parameter to False ($False).</span></span> <span data-ttu-id="92831-124">Отключение CDR не приводит к удалению мониторинга.</span><span class="sxs-lookup"><span data-stu-id="92831-124">Disabling CDR does not uninstall monitoring.</span></span> <span data-ttu-id="92831-125">Он приостанавливает сбор и хранение данных CDR.</span><span class="sxs-lookup"><span data-stu-id="92831-125">It pauses the collection and storage of CDR data.</span></span>
    
        Set-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $False

</div>

<div>

## <a name="to-use-a-single-command-to-enable-cdr-in-multiple-locations"></a><span data-ttu-id="92831-126">Чтобы использовать отдельную команду для включения CDR в нескольких местах, выполните следующие действия</span><span class="sxs-lookup"><span data-stu-id="92831-126">To use a single command to enable CDR in multiple locations</span></span>

  - <span data-ttu-id="92831-127">Эта команда включает CDR для всех параметров конфигурации CDR, используемых в настоящее время в организации.</span><span class="sxs-lookup"><span data-stu-id="92831-127">This command enables CDR for all the CDR configuration settings currently in use in your organization.</span></span>
    
        Get-CsCdrConfiguration | Set-CsCdrConfiguration "site:Redmond" -EnableCDR $True

</div>

<span data-ttu-id="92831-128">Для получения дополнительных сведений обратитесь к разделу "Справка" для командлета [Set – CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsCdrConfiguration) .</span><span class="sxs-lookup"><span data-stu-id="92831-128">For more information, see the help topic for the [Set-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsCdrConfiguration) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="92831-129">См. также</span><span class="sxs-lookup"><span data-stu-id="92831-129">See Also</span></span>


[<span data-ttu-id="92831-130">Планирование мониторинга в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="92831-130">Planning for monitoring in Lync Server 2013</span></span>](lync-server-2013-planning-for-monitoring.md)  
[<span data-ttu-id="92831-131">Развертывание мониторинга в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="92831-131">Deploying monitoring in Lync Server 2013</span></span>](lync-server-2013-deploying-monitoring.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

