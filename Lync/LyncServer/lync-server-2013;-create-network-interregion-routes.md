---
title: Lync Server 2013; Создание маршрутов между межсетевыми областями
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
audience: admin
manager: serdars
f1.keywords:
- NOCSH
TOCTitle: Create network interregion routes
ms:assetid: 5555262a-a502-4b01-9593-836dd30064f5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398368(v=OCS.15)
ms:contentKeyID: 48184159
ms.date: 07/23/2014
mtps_version: v=OCS.15
ms.openlocfilehash: 2890d903df512e2f7eef26e6d1c22fa5bc029839
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48508536"
---
# <a name="create-network-interregion-routes-in-lync-server-2013"></a><span data-ttu-id="4c8d5-102">Создание маршрутов между межсетевыми областями в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4c8d5-102">Create network interregion routes in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4c8d5-103">_**Последнее изменение темы:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="4c8d5-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="4c8d5-p101">*Маршрут между регионами сети* определяет маршрут между парой регионов сети. Маршрут между регионами сети требуется для каждой пары регионов сети в развертывании службы контроля допуска звонков. Это позволяет каждому региону сети в рамках развертывания осуществлять доступ к любому другому региону.</span><span class="sxs-lookup"><span data-stu-id="4c8d5-p101">A *network interregion route* defines the route between a pair of network regions. Each pair of network regions in your call admission control deployment requires a network interregion route. This enables every network region within the deployment to access every other region.</span></span>

<span data-ttu-id="4c8d5-107">Связи между регионами накладывают определенные ограничения на пропускную способность, доступную подключениям между регионами; маршруты же определяют путь, который должны пройти подключения от одного региона до другого.</span><span class="sxs-lookup"><span data-stu-id="4c8d5-107">While region links set bandwidth limitations on the connections between regions, an interregion route determines which linked path the connection will traverse from one region to another.</span></span>

<span data-ttu-id="4c8d5-108">Для получения подробных сведений о работе с маршрутами между сетевыми областями обратитесь к документации по командной консоли Lync Server для следующих командлетов:</span><span class="sxs-lookup"><span data-stu-id="4c8d5-108">For details about working with network interregion routes, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - [<span data-ttu-id="4c8d5-109">New — Кснетворкинтеррегионрауте</span><span class="sxs-lookup"><span data-stu-id="4c8d5-109">New-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterRegionRoute)

  - [<span data-ttu-id="4c8d5-110">Get — Кснетворкинтеррегионрауте</span><span class="sxs-lookup"><span data-stu-id="4c8d5-110">Get-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterRegionRoute)

  - [<span data-ttu-id="4c8d5-111">Set — Кснетворкинтеррегионрауте</span><span class="sxs-lookup"><span data-stu-id="4c8d5-111">Set-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterRegionRoute)

  - [<span data-ttu-id="4c8d5-112">Remove — Кснетворкинтеррегионрауте</span><span class="sxs-lookup"><span data-stu-id="4c8d5-112">Remove-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterRegionRoute)

<span data-ttu-id="4c8d5-113">В этом примере топологии необходимо определить маршруты между регионами сети для каждой пары регионов из трех: Северная Америка/EMEA, APAC/EMEA и APAC/Северная Америка.</span><span class="sxs-lookup"><span data-stu-id="4c8d5-113">In the example topology, network interregion routes must be defined for each of the three region pairs: North America/EMEA, EMEA/APAC, and North America/APAC.</span></span>

<div>

## <a name="to-create-network-interregion-routes-by-using-lync-server-management-shell"></a><span data-ttu-id="4c8d5-114">Создание маршрутов между сетевыми областями с помощью командной консоли Lync Server</span><span class="sxs-lookup"><span data-stu-id="4c8d5-114">To create network interregion routes by using Lync Server Management Shell</span></span>

1.  <span data-ttu-id="4c8d5-115">Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="4c8d5-115">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="4c8d5-116">Выполните командлет **New-CsNetworkInterRegionRoute**, чтобы определить необходимые маршруты.</span><span class="sxs-lookup"><span data-stu-id="4c8d5-116">Run the **New-CsNetworkInterRegionRoute** cmdlet to define the required routes.</span></span> <span data-ttu-id="4c8d5-117">Например, выполните:</span><span class="sxs-lookup"><span data-stu-id="4c8d5-117">For example, run:</span></span>
    
       ```PowerShell
        New-CsNetworkInterRegionRoute -Identity NorthAmerica_EMEA_Route -NetworkRegionID1 NorthAmerica -NetworkRegionID2 EMEA -NetworkRegionLinkIDs "NA-EMEA-LINK"
       ```
    
       ```PowerShell
        New-CsNetworkInterRegionRoute -Identity NorthAmerica_APAC_Route -NetworkRegionID1 NorthAmerica -NetworkRegionID2 APAC -NetworkRegionLinkIDs "NA-EMEA-LINK, EMEA-APAC-LINK"
       ```
    
       ```PowerShell
        New-CsNetworkInterRegionRoute -Identity EMEA_APAC_Route -NetworkRegionID1 EMEA -NetworkRegionID2 APAC -NetworkRegionLinkIDs "EMEA-APAC-LINK"
       ```
    
    <div class=" ">
    

    > [!NOTE]  
    > <span data-ttu-id="4c8d5-118">Для маршрута между регионами «Северная Америка/APAC» требуются две связи между регионами сети, поскольку прямая сетевая связь между этими регионами отсутствует.</span><span class="sxs-lookup"><span data-stu-id="4c8d5-118">The North America/APAC network interregion route requires two network region links because there is no direct network region link between them.</span></span>

    
    </div>

</div>

<div>

## <a name="to-create-network-interregion-routes-by-using-lync-server-control-panel"></a><span data-ttu-id="4c8d5-119">Создание маршрутов между сетевыми областями с помощью панели управления Lync Server</span><span class="sxs-lookup"><span data-stu-id="4c8d5-119">To create network interregion routes by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="4c8d5-120">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="4c8d5-120">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="4c8d5-121">Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="4c8d5-121">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

2.  <span data-ttu-id="4c8d5-122">На левой панели навигации щелкните **Конфигурация сети**.</span><span class="sxs-lookup"><span data-stu-id="4c8d5-122">In the left navigation bar, click **Network Configuration**.</span></span>

3.  <span data-ttu-id="4c8d5-123">Щелкните кнопку навигации **Маршрут региона**.</span><span class="sxs-lookup"><span data-stu-id="4c8d5-123">Click the **Region Route** navigation button.</span></span>

4.  <span data-ttu-id="4c8d5-124">Щелкните **Создать**.</span><span class="sxs-lookup"><span data-stu-id="4c8d5-124">Click **New**.</span></span>

5.  <span data-ttu-id="4c8d5-125">На странице **Новый маршрут региона** щелкните **Имя**, а затем введите имя для маршрута между регионами сети.</span><span class="sxs-lookup"><span data-stu-id="4c8d5-125">On the **New Region Route** page, click **Name** and then type a name for the network interregion route.</span></span>

6.  <span data-ttu-id="4c8d5-126">Щелкните **область сети \# 1**, а затем выберите в списке область сети, которую нужно маршрутизировать в область сети \# 2.</span><span class="sxs-lookup"><span data-stu-id="4c8d5-126">Click **Network Region \#1**, and then click a network region in the list that you want to route to Network Region \#2.</span></span>

7.  <span data-ttu-id="4c8d5-127">Щелкните **область сети \# 2**, а затем выберите в списке область сети, которую нужно перенаправить в область сети \# 1.</span><span class="sxs-lookup"><span data-stu-id="4c8d5-127">Click **Network Region \#2**, and then click a network region in the list that you want to route to Network Region \#1.</span></span>

8.  <span data-ttu-id="4c8d5-128">Щелкните **Добавить** рядом с полем **Связи между регионами сети**, а затем добавьте связь с регионом сети, которая будет использоваться в маршруте между регионами сети.</span><span class="sxs-lookup"><span data-stu-id="4c8d5-128">Click **Add** beside the **Network Region Links** field, and then add a network region link that will be used in the network interregion route.</span></span>
    
    <div class=" ">
    

    > [!NOTE]  
    > <span data-ttu-id="4c8d5-p104">При создании маршрута между двумя регионами сети, между которыми отсутствует прямая связь, необходимо добавить все необходимые связи для создания полного маршрута. Например, для создания маршрута между регионами сети «Северная Америка» и «APAC» требуются две связи между сетевыми регионами, так как между ними отсутствует прямая связь.</span><span class="sxs-lookup"><span data-stu-id="4c8d5-p104">If you are creating a route for two network regions that do not have a direct network region link between them, you must add all the necessary links to complete the route. For example, the North America/APAC network interregion route requires two network region links because there is no direct network region link between them.</span></span>

    
    </div>

9.  <span data-ttu-id="4c8d5-131">Щелкните **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="4c8d5-131">Click **Commit**.</span></span>

10. <span data-ttu-id="4c8d5-132">Чтобы завершить создание маршрутов между регионами сети, повторите шаги с 4 по 9 с указанием настроек для других маршрутов между сетевыми регионами.</span><span class="sxs-lookup"><span data-stu-id="4c8d5-132">To finish creating network interregion routes for your topology, repeat steps 4 through 9 with settings for other network interregion routes.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

