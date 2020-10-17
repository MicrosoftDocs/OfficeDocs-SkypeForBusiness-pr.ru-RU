---
title: 'Lync Server 2013: Просмотр сведений о сетевом сайте'
description: 'Lync Server 2013: Просмотр сведений о сетевом сайте.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Viewing network site information
ms:assetid: 24a97d98-b168-4016-81bf-c2c478092b87
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687996(v=OCS.15)
ms:contentKeyID: 49733586
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b46dc91510cb5ff737977871470033374573ba8c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48546225"
---
# <a name="viewing-network-site-information-in-lync-server-2013"></a><span data-ttu-id="16cf5-103">Просмотр сведений о сетевом сайте в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="16cf5-103">Viewing network site information in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="16cf5-104">_**Последнее изменение темы:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="16cf5-104">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="16cf5-105">Сетевые узлы — это офисы или места, настроенные в каждой области развертывания контроля допуска звонков (CAC) или Enhanced 9-1-1.</span><span class="sxs-lookup"><span data-stu-id="16cf5-105">Network sites are the offices or locations configured within each region of a call admission control (CAC) or Enhanced 9-1-1 deployment.</span></span> <span data-ttu-id="16cf5-106">Сведения о сетевом сайте можно просматривать либо в панели управления Lync Server 2013, либо в командной консоли Lync Server.</span><span class="sxs-lookup"><span data-stu-id="16cf5-106">You can view network site information in either Lync Server 2013 Control Panel or Lync Server Management Shell .</span></span> <span data-ttu-id="16cf5-107">Дополнительные сведения о создании или изменении сетевых сайтов можно найти [в статье Создание или изменение сетевых сайтов в Lync Server 2013](lync-server-2013-creating-or-modifying-network-sites.md).</span><span class="sxs-lookup"><span data-stu-id="16cf5-107">For details about creating or modifying network sites, see [Creating or modifying network sites in Lync Server 2013](lync-server-2013-creating-or-modifying-network-sites.md).</span></span>

<div>

## <a name="to-view-network-site-information-in-lync-server-control-panel"></a><span data-ttu-id="16cf5-108">Просмотр сведений о сетевом сайте в панели управления Lync Server</span><span class="sxs-lookup"><span data-stu-id="16cf5-108">To view network site information in Lync Server Control Panel</span></span>

1.  <span data-ttu-id="16cf5-109">Из учетной записи пользователя, которая является членом группы RTCUniversalServerAdmins (или имеет эквивалентные права пользователя) или назначается роли CsAdministrator, войдите на любой компьютер во внутреннем развертывании.</span><span class="sxs-lookup"><span data-stu-id="16cf5-109">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="16cf5-110">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="16cf5-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="16cf5-111">Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="16cf5-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="16cf5-112">На левой панели навигации щелкните **Конфигурация сети** и выберите **Сайт**.</span><span class="sxs-lookup"><span data-stu-id="16cf5-112">In the left navigation bar, click **Network Configuration** and then click **Site**.</span></span>

4.  <span data-ttu-id="16cf5-113">На странице **Сайт** выберите сайт, который хотите просмотреть.</span><span class="sxs-lookup"><span data-stu-id="16cf5-113">On the **Site** page, click the site that you want to view.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="16cf5-114">Допускается одновременный просмотр данных только для одного сайта.</span><span class="sxs-lookup"><span data-stu-id="16cf5-114">You can only view information for one site at a time.</span></span>

    
    </div>

5.  <span data-ttu-id="16cf5-115">В меню **Правка** щелкните **Показать подробности**.</span><span class="sxs-lookup"><span data-stu-id="16cf5-115">On the **Edit** menu, click **Show details**.</span></span>

</div>

<div>

## <a name="viewing-network-site-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="16cf5-116">Просмотр сведений о сетевом сайте с помощью командлетов Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="16cf5-116">Viewing Network Site Information by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="16cf5-117">Сведения о сетевом сайте можно просмотреть с помощью Windows PowerShell и командлета Get-CsNetworkSite.</span><span class="sxs-lookup"><span data-stu-id="16cf5-117">You can view network site information by using Windows PowerShell and the Get-CsNetworkSite cmdlet.</span></span> <span data-ttu-id="16cf5-118">Этот командлет можно запустить либо из командной консоли Lync Server 2013, либо из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="16cf5-118">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="16cf5-119">Сведения об использовании удаленной оболочки Windows PowerShell для подключения к Lync Server приведены в статье "Краткое руководство по управлению Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" в статье Lync Server Windows PowerShell в блоге [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .</span><span class="sxs-lookup"><span data-stu-id="16cf5-119">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-view-network-site-information"></a><span data-ttu-id="16cf5-120">Просмотр сведений о сетевом сайте</span><span class="sxs-lookup"><span data-stu-id="16cf5-120">To view network site information</span></span>

  - <span data-ttu-id="16cf5-121">Чтобы просмотреть сведения обо всех сетевых сайтах, введите в командной консоли Lync Server следующую команду и нажмите клавишу ВВОД:</span><span class="sxs-lookup"><span data-stu-id="16cf5-121">To view information about all your network sites, type the following command in the Lync Server Management Shell and then press ENTER:</span></span>
    
        Get-CsNetworkSite
    
    <span data-ttu-id="16cf5-122">Это приведет к возврату приблизительно такой информации:</span><span class="sxs-lookup"><span data-stu-id="16cf5-122">That will return information similar to this:</span></span>
    
        Identity          : Redmond
        NetworkSiteID     : Redmond
        Description       :
        NetworkRegionID   : Pacific Northwest
        BypassID          : 3b232b84-2c1d-4da2-8181-e9330bafebe9
        BWPolicyProfileID :
        LocationPolicy    :

</div>

<span data-ttu-id="16cf5-123">Дополнительные сведения см. в разделе справки для командлета [Get-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSite).</span><span class="sxs-lookup"><span data-stu-id="16cf5-123">For more information, see the help topic for the [Get-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSite) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="16cf5-124">См. также</span><span class="sxs-lookup"><span data-stu-id="16cf5-124">See Also</span></span>


[<span data-ttu-id="16cf5-125">Создание или изменение сетевых сайтов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="16cf5-125">Creating or modifying network sites in Lync Server 2013</span></span>](lync-server-2013-creating-or-modifying-network-sites.md)  
[<span data-ttu-id="16cf5-126">Удаление существующего сетевого сайта в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="16cf5-126">Deleting an existing network site in Lync Server 2013</span></span>](lync-server-2013-deleting-an-existing-network-site.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

