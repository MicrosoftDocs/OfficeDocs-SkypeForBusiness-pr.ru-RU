---
title: 'Lync Server 2013: удаление существующих маршрутов между сетевыми областями'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deleting existing network region routes
ms:assetid: 6256ff80-5f1e-48b4-928b-24aeb3c1a0e7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688074(v=OCS.15)
ms:contentKeyID: 49733669
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 91a8674e635bb5663ebbca994d7d8f865601a193
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42206965"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deleting-existing-network-region-routes-in-lync-server-2013"></a><span data-ttu-id="12df7-102">Удаление существующих маршрутов областей сети в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="12df7-102">Deleting existing network region routes in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="12df7-103">_**Последнее изменение темы:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="12df7-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="12df7-104">Каждому региону в конфигурации контроля допуска звонков (CAC) необходимо предоставить возможность доступа к каждой другой области.</span><span class="sxs-lookup"><span data-stu-id="12df7-104">Every region within a call admission control (CAC) configuration must have some way to access every other region.</span></span> <span data-ttu-id="12df7-105">Связи между регионами накладывают определенные ограничения на пропускную способность, доступную подключениям между областями, и также представляют собой физические соединения; маршруты же определяют путь, который должны пройти подключения от одной области до другой.</span><span class="sxs-lookup"><span data-stu-id="12df7-105">While region links set bandwidth limitations on the connections between regions and also represent the physical links, a route determines which linked path the connection will traverse from one region to another.</span></span> <span data-ttu-id="12df7-106">Для настройки маршрутов областей сети можно использовать панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="12df7-106">You can use Lync Server Control Panel to configure network region routes.</span></span> <span data-ttu-id="12df7-107">С помощью панели управления Lync Server вы можете создать, изменить или удалить маршрут области сети.</span><span class="sxs-lookup"><span data-stu-id="12df7-107">From Lync Server Control Panel, you can create, modify, or delete a network region route.</span></span> <span data-ttu-id="12df7-108">С помощью инструкций, приведенных в этом разделе, можно удалить существующие маршруты сетевых регионов.</span><span class="sxs-lookup"><span data-stu-id="12df7-108">Use this topic to delete existing network region routes.</span></span> <span data-ttu-id="12df7-109">Дополнительные сведения о создании или изменении маршрутов для областей сети см [в статье Создание или изменение маршрутов для областей сети в Lync Server 2013](lync-server-2013-creating-or-modifying-network-region-routes.md).</span><span class="sxs-lookup"><span data-stu-id="12df7-109">For details about creating or modifying network region routes, see [Creating or modifying network region routes in Lync Server 2013](lync-server-2013-creating-or-modifying-network-region-routes.md).</span></span>

<div>

## <a name="to-delete-a-network-region-route"></a><span data-ttu-id="12df7-110">Чтобы удалить маршрут сетевого региона</span><span class="sxs-lookup"><span data-stu-id="12df7-110">To delete a network region route</span></span>

1.  <span data-ttu-id="12df7-111">Из учетной записи пользователя, которая является членом группы RTCUniversalServerAdmins (или имеет эквивалентные права пользователя) или назначается роли CsAdministrator, войдите на любой компьютер во внутреннем развертывании.</span><span class="sxs-lookup"><span data-stu-id="12df7-111">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="12df7-112">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="12df7-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="12df7-113">Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="12df7-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="12df7-114">В панели навигации выберите **Настройка сети**, а затем щелкните **Маршрут региона**.</span><span class="sxs-lookup"><span data-stu-id="12df7-114">In the left navigation bar, click **Network Configuration** and then click **Region Route**.</span></span>

4.  <span data-ttu-id="12df7-115">На странице **Маршрут региона** щелкните маршрут, который следует удалить.</span><span class="sxs-lookup"><span data-stu-id="12df7-115">On the **Region Route** page, click the region route that you want to delete.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="12df7-p103">Одновременно можно удалить сразу несколько маршрутов регионов. Для этого нажмите и удерживайте клавишу CTRL, одновременно выбирая несколько маршрутов регионов. Или щелкните пункт <STRONG>Выделить все</STRONG> в меню <STRONG>Изменить</STRONG> для выбора сразу нескольких маршрутов.</span><span class="sxs-lookup"><span data-stu-id="12df7-p103">You can delete more than one region route at a time. To do this, press CTRL and select multiple region routes while holding down the CTRL key. Or, to select all region routes, click <STRONG>Select all</STRONG> on the <STRONG>Edit</STRONG> menu.</span></span>

    
    </div>

5.  <span data-ttu-id="12df7-119">В меню **Изменить** щелкните **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="12df7-119">On the **Edit** menu, click **Delete**.</span></span>

6.  <span data-ttu-id="12df7-120">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="12df7-120">Click **OK**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="12df7-121">См. также</span><span class="sxs-lookup"><span data-stu-id="12df7-121">See Also</span></span>


[<span data-ttu-id="12df7-122">Создание или изменение маршрутов областей сети в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="12df7-122">Creating or modifying network region routes in Lync Server 2013</span></span>](lync-server-2013-creating-or-modifying-network-region-routes.md)  


<span data-ttu-id="12df7-123">[Настройка маршрута области сети](https://technet.microsoft.com/library/gg133706\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="12df7-123">[Configure a Network Region Route](https://technet.microsoft.com/library/gg133706\(v=ocs.15\))</span></span>  


[<span data-ttu-id="12df7-124">New — Кснетворкинтеррегионрауте</span><span class="sxs-lookup"><span data-stu-id="12df7-124">New-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterRegionRoute)  
[<span data-ttu-id="12df7-125">Set — Кснетворкинтеррегионрауте</span><span class="sxs-lookup"><span data-stu-id="12df7-125">Set-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterRegionRoute)  
[<span data-ttu-id="12df7-126">Remove — Кснетворкинтеррегионрауте</span><span class="sxs-lookup"><span data-stu-id="12df7-126">Remove-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterRegionRoute)  
[<span data-ttu-id="12df7-127">Get — Кснетворкинтеррегионрауте</span><span class="sxs-lookup"><span data-stu-id="12df7-127">Get-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterRegionRoute)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

