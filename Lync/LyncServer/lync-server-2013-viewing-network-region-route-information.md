---
title: 'Lync Server 2013: Просмотр сведений о маршруте областей сети'
description: 'Lync Server 2013: Просмотр сведений о маршруте области сети.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Viewing network region route information
ms:assetid: 34dd9fa3-e695-4680-b244-3019298b5009
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688021(v=OCS.15)
ms:contentKeyID: 49733611
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3eca6348ecb13cd0b0b28950d57c741c056c1bd7
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48549845"
---
# <a name="viewing-network-region-route-information-in-lync-server-2013"></a><span data-ttu-id="e5d3f-103">Просмотр сведений о маршруте области сети в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e5d3f-103">Viewing network region route information in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e5d3f-104">_**Последнее изменение темы:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="e5d3f-104">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="e5d3f-105">Каждому региону в конфигурации контроля допуска звонков (CAC) необходимо предоставить возможность доступа к каждой другой области.</span><span class="sxs-lookup"><span data-stu-id="e5d3f-105">Every region within a call admission control (CAC) configuration must have some way to access every other region.</span></span> <span data-ttu-id="e5d3f-106">Связи между регионами накладывают определенные ограничения на пропускную способность, доступную подключениям между областями, и также представляют собой физические соединения; маршруты же определяют путь, который должны пройти подключения от одной области до другой.</span><span class="sxs-lookup"><span data-stu-id="e5d3f-106">While region links set bandwidth limitations on the connections between regions and also represent the physical links, a route determines which linked path the connection will traverse from one region to another.</span></span> <span data-ttu-id="e5d3f-107">Используйте следующие процедуры для просмотра существующих маршрутов областей сети в панели управления Lync Server 2013 или консоли управления Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e5d3f-107">Use the following procedures to view existing network region routes in Lync Server 2013 Control Panel or Lync Server 2013 Management Shell.</span></span> <span data-ttu-id="e5d3f-108">Дополнительные сведения о создании или изменении маршрутов для областей сети см [в статье Создание или изменение маршрутов для областей сети в Lync Server 2013](lync-server-2013-creating-or-modifying-network-region-routes.md).</span><span class="sxs-lookup"><span data-stu-id="e5d3f-108">For details about creating or modifying network region routes, see [Creating or modifying network region routes in Lync Server 2013](lync-server-2013-creating-or-modifying-network-region-routes.md).</span></span>

<div>

## <a name="to-view-network-region-route-information-in-lync-server-control-panel"></a><span data-ttu-id="e5d3f-109">Просмотр сведений о маршруте области сети в панели управления Lync Server</span><span class="sxs-lookup"><span data-stu-id="e5d3f-109">To view network region route information in Lync Server Control Panel</span></span>

1.  <span data-ttu-id="e5d3f-110">Из учетной записи пользователя, которая является членом группы RTCUniversalServerAdmins (или имеет эквивалентные права пользователя) или назначается роли CsAdministrator, войдите на любой компьютер во внутреннем развертывании.</span><span class="sxs-lookup"><span data-stu-id="e5d3f-110">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="e5d3f-111">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="e5d3f-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="e5d3f-112">Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="e5d3f-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="e5d3f-113">На левой панели навигации выберите **Настройка сети**, а затем щелкните **Маршрут региона**.</span><span class="sxs-lookup"><span data-stu-id="e5d3f-113">In the left navigation bar, click **Network Configuration** and then click **Region Route**.</span></span>

4.  <span data-ttu-id="e5d3f-114">На странице **Маршрут региона** выберите маршрут области, который хотите просмотреть.</span><span class="sxs-lookup"><span data-stu-id="e5d3f-114">On the **Region Route** page, click the region route that you want to view.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="e5d3f-115">Можно просматривать только один маршрут за один раз.</span><span class="sxs-lookup"><span data-stu-id="e5d3f-115">You can only view one region route at a time.</span></span>

    
    </div>

5.  <span data-ttu-id="e5d3f-116">В меню **Изменить** щелкните **Подробнее**.</span><span class="sxs-lookup"><span data-stu-id="e5d3f-116">On the **Edit** menu, click **Show details**.</span></span>

</div>

<div>

## <a name="viewing-network-region-route-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="e5d3f-117">Просмотр сведений о маршруте между областями сети с помощью командлетов Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="e5d3f-117">Viewing Network Region Route Information by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="e5d3f-118">Сведения о маршруте области сети можно просмотреть с помощью Windows PowerShell и командлета Get-CsNetworkInterRegionRoute.</span><span class="sxs-lookup"><span data-stu-id="e5d3f-118">Network region route information can be viewed by using Windows PowerShell and the Get-CsNetworkInterRegionRoute cmdlet.</span></span> <span data-ttu-id="e5d3f-119">Этот командлет можно запустить либо из командной консоли Lync Server 2013, либо из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e5d3f-119">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="e5d3f-120">Сведения об использовании удаленной оболочки Windows PowerShell для подключения к Lync Server приведены в статье "Краткое руководство по управлению Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" в статье Lync Server Windows PowerShell в блоге [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .</span><span class="sxs-lookup"><span data-stu-id="e5d3f-120">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-view-network-region-route-information"></a><span data-ttu-id="e5d3f-121">Просмотр сведений о маршруте между областями сети</span><span class="sxs-lookup"><span data-stu-id="e5d3f-121">To view network region route information</span></span>

  - <span data-ttu-id="e5d3f-122">Чтобы просмотреть сведения о всех маршрутах областей сети, введите следующую команду в командной консоли Lync Server и нажмите клавишу ВВОД:</span><span class="sxs-lookup"><span data-stu-id="e5d3f-122">To view information about all your network region routes, type the following command in the Lync Server Management Shell and then press ENTER:</span></span>
    
        Get-CsNetworkInterRegionRoute
    
    <span data-ttu-id="e5d3f-123">Это приведет к возврату приблизительно такой информации:</span><span class="sxs-lookup"><span data-stu-id="e5d3f-123">That will return information similar to this:</span></span>
    
        Identity                  : TransAmericaRoute
        NetworkRegionLinks        : {NorthwestToNortheast}
        InterNetworkRegionRouteID : TransAmericaRoute
        NetworkRegionID1          : Pacific Northwest
        NetworkRegionID2          : Northeast

</div>

<span data-ttu-id="e5d3f-124">Дополнительные сведения см. в разделе справки по командлету [Get-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterRegionRoute).</span><span class="sxs-lookup"><span data-stu-id="e5d3f-124">For more information, see the help topic for the [Get-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterRegionRoute) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="e5d3f-125">См. также</span><span class="sxs-lookup"><span data-stu-id="e5d3f-125">See Also</span></span>


[<span data-ttu-id="e5d3f-126">Создание или изменение маршрутов областей сети в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e5d3f-126">Creating or modifying network region routes in Lync Server 2013</span></span>](lync-server-2013-creating-or-modifying-network-region-routes.md)  
[<span data-ttu-id="e5d3f-127">Удаление существующих маршрутов областей сети в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e5d3f-127">Deleting existing network region routes in Lync Server 2013</span></span>](lync-server-2013-deleting-existing-network-region-routes.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

