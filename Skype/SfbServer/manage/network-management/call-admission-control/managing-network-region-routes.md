---
title: Управление маршрутами регионов сети
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Маршрут между областями сети определяет путь между парой сетевых областей. Для каждой пары сетевых областей в развертывании контроля допуска звонков необходим маршрут между областями сети.
ms.openlocfilehash: c91f46ff45dd50f638cdb4f256fb93f2d33781ec
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51118558"
---
# <a name="managing-network-region-routes-in-skype-for-business-server"></a><span data-ttu-id="a5eaa-104">Управление маршрутами областей сети в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="a5eaa-104">Managing network region routes in Skype for Business Server</span></span>

<span data-ttu-id="a5eaa-105">*Маршрут между областями сети* определяет путь между парой сетевых областей.</span><span class="sxs-lookup"><span data-stu-id="a5eaa-105">A *network region route* defines the route between a pair of network regions.</span></span> <span data-ttu-id="a5eaa-106">Для каждой пары сетевых областей в развертывании контроля допуска звонков необходим маршрут между областями сети.</span><span class="sxs-lookup"><span data-stu-id="a5eaa-106">Each pair of network regions in your call admission control deployment requires a network region route.</span></span> <span data-ttu-id="a5eaa-107">Благодаря этому каждая область сети в рамках развертывания может получить доступ к каждой другой области.</span><span class="sxs-lookup"><span data-stu-id="a5eaa-107">This enables every network region within the deployment to access every other region.</span></span> <span data-ttu-id="a5eaa-108">Используйте процедуры в этой области для просмотра, создания, изменения или удаления маршрутов сетевого региона.</span><span class="sxs-lookup"><span data-stu-id="a5eaa-108">Use the procedures in this artilce to view, create, modify, or delete network region routes.</span></span>

## <a name="view-network-region-route-information"></a><span data-ttu-id="a5eaa-109">Просмотр сведений о маршруте сетевого региона</span><span class="sxs-lookup"><span data-stu-id="a5eaa-109">View network region route information</span></span> 

<span data-ttu-id="a5eaa-110">Каждому региону в конфигурации контроля допуска звонков (CAC) необходимо предоставить возможность доступа к каждой другой области.</span><span class="sxs-lookup"><span data-stu-id="a5eaa-110">Every region within a call admission control (CAC) configuration must have some way to access every other region.</span></span> <span data-ttu-id="a5eaa-111">Связи между регионами накладывают определенные ограничения на пропускную способность, доступную подключениям между областями, и также представляют собой физические соединения; маршруты же определяют путь, который должны пройти подключения от одной области до другой.</span><span class="sxs-lookup"><span data-stu-id="a5eaa-111">While region links set bandwidth limitations on the connections between regions and also represent the physical links, a route determines which linked path the connection will traverse from one region to another.</span></span> <span data-ttu-id="a5eaa-112">Используйте следующие процедуры, чтобы просмотреть существующие маршруты регионов сети в панели управления Skype для бизнес-серверов или в панели управления Skype для бизнес-серверов.</span><span class="sxs-lookup"><span data-stu-id="a5eaa-112">Use the following procedures to view existing network region routes in Skype for Business Server Control Panel or Skype for Business Server Management Shell.</span></span> 

### <a name="to-view-network-region-route-information-in-skype-for-business-server-control-panel"></a><span data-ttu-id="a5eaa-113">Просмотр сведений о маршруте маршрутов в Skype для панели управления бизнес-серверами</span><span class="sxs-lookup"><span data-stu-id="a5eaa-113">To view network region route information in Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="a5eaa-114">С учетной записи пользователя, которая входит в группу RTCUniversalServerAdmins (или имеет эквивалентные права пользователя) или назначена роли CsAdministrator, войдите на любой компьютер во внутреннем развертывании.</span><span class="sxs-lookup"><span data-stu-id="a5eaa-114">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="a5eaa-115">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Skype для бизнес-серверов.</span><span class="sxs-lookup"><span data-stu-id="a5eaa-115">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="a5eaa-116">В левой панели навигации нажмите **кнопку Конфигурация** сети, а затем щелкните **Маршрут региона**.</span><span class="sxs-lookup"><span data-stu-id="a5eaa-116">In the left navigation bar, click **Network Configuration**, and then click **Region Route**.</span></span>

4.  <span data-ttu-id="a5eaa-117">На странице **Маршрут региона** выберите маршрут области, который хотите просмотреть.</span><span class="sxs-lookup"><span data-stu-id="a5eaa-117">On the **Region Route** page, click the region route that you want to view.</span></span>


    > [!NOTE]  
    > <span data-ttu-id="a5eaa-118">Можно просматривать только один маршрут за один раз.</span><span class="sxs-lookup"><span data-stu-id="a5eaa-118">You can only view one region route at a time.</span></span>


5.  <span data-ttu-id="a5eaa-119">В меню **Изменить** щелкните **Подробнее**.</span><span class="sxs-lookup"><span data-stu-id="a5eaa-119">On the **Edit** menu, click **Show details**.</span></span>


### <a name="viewing-network-region-route-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="a5eaa-120">Просмотр сведений о маршруте сетевого региона с помощью Windows PowerShell cmdlets</span><span class="sxs-lookup"><span data-stu-id="a5eaa-120">Viewing Network Region Route Information by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="a5eaa-121">Сведения о маршруте сетевого региона можно просмотреть с помощью Windows PowerShell и Get-CsNetworkInterRegionRoute.</span><span class="sxs-lookup"><span data-stu-id="a5eaa-121">Network region route information can be viewed by using Windows PowerShell and the Get-CsNetworkInterRegionRoute cmdlet.</span></span> <span data-ttu-id="a5eaa-122">Этот комлет можно выполнить либо из оболочки управления skype для бизнес-серверов, либо из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a5eaa-122">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

### <a name="to-view-network-region-route-information"></a><span data-ttu-id="a5eaa-123">Просмотр сведений о маршруте сетевого региона</span><span class="sxs-lookup"><span data-stu-id="a5eaa-123">To view network region route information</span></span>

  - <span data-ttu-id="a5eaa-124">Чтобы просмотреть сведения обо всех маршрутах сетевого региона, введите следующую команду в командной оболочке Skype для бизнес-серверов и нажмите кнопку ENTER:</span><span class="sxs-lookup"><span data-stu-id="a5eaa-124">To view information about all your network region routes, type the following command in the Skype for Business Server Management Shell, and then press ENTER:</span></span>
    
        Get-CsNetworkInterRegionRoute
    
    <span data-ttu-id="a5eaa-125">Это приведет к возврату приблизительно такой информации:</span><span class="sxs-lookup"><span data-stu-id="a5eaa-125">That will return information similar to this:</span></span>
    
        Identity                  : TransAmericaRoute
        NetworkRegionLinks        : {NorthwestToNortheast}
        InterNetworkRegionRouteID : TransAmericaRoute
        NetworkRegionID1          : Pacific Northwest
        NetworkRegionID2          : Northeast

<span data-ttu-id="a5eaa-126">Дополнительные сведения см. в разделе справки по командлету [Get-CsNetworkInterRegionRoute](/powershell/module/skype/Get-CsNetworkInterRegionRoute).</span><span class="sxs-lookup"><span data-stu-id="a5eaa-126">For more information, see the help topic for the [Get-CsNetworkInterRegionRoute](/powershell/module/skype/Get-CsNetworkInterRegionRoute) cmdlet.</span></span>


## <a name="create-or-modify-network-region-routes"></a><span data-ttu-id="a5eaa-127">Создание или изменение маршрутов сетевого региона</span><span class="sxs-lookup"><span data-stu-id="a5eaa-127">Create or modify network region routes</span></span>

<span data-ttu-id="a5eaa-128">Каждому региону в конфигурации контроля допуска звонков (CAC) необходимо предоставить возможность доступа к каждой другой области.</span><span class="sxs-lookup"><span data-stu-id="a5eaa-128">Every region within a call admission control (CAC) configuration must have some way to access every other region.</span></span> <span data-ttu-id="a5eaa-129">Связи между регионами накладывают определенные ограничения на пропускную способность, доступную подключениям между областями, и также представляют собой физические соединения; маршруты же определяют путь, который должны пройти подключения от одной области до другой.</span><span class="sxs-lookup"><span data-stu-id="a5eaa-129">While region links set bandwidth limitations on the connections between regions and also represent the physical links, a route determines which linked path the connection will traverse from one region to another.</span></span> <span data-ttu-id="a5eaa-130">Для настройки маршрутов сетевого региона можно использовать панель управления Skype для бизнес-серверов.</span><span class="sxs-lookup"><span data-stu-id="a5eaa-130">You can use the Skype for Business Server Control Panel to configure network region routes.</span></span> <span data-ttu-id="a5eaa-131">С панели управления Skype для бизнес-серверов можно создать, изменить или удалить маршрут сетевого региона.</span><span class="sxs-lookup"><span data-stu-id="a5eaa-131">From the Skype for Business Server Control Panel, you can create, modify, or delete a network region route.</span></span> <span data-ttu-id="a5eaa-132">Используйте этот раздел для создания или изменения маршрута маршрут между областями сети.</span><span class="sxs-lookup"><span data-stu-id="a5eaa-132">Use this topic to create or modify a network region route.</span></span> 

### <a name="to-create-a-network-region-route"></a><span data-ttu-id="a5eaa-133">Создание маршрута к регионами сети</span><span class="sxs-lookup"><span data-stu-id="a5eaa-133">To create a network region route</span></span>

1.  <span data-ttu-id="a5eaa-134">С учетной записи пользователя, которая входит в группу RTCUniversalServerAdmins (или имеет эквивалентные права пользователя) или назначена роли CsAdministrator, войдите на любой компьютер во внутреннем развертывании.</span><span class="sxs-lookup"><span data-stu-id="a5eaa-134">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="a5eaa-135">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Skype для бизнес-серверов.</span><span class="sxs-lookup"><span data-stu-id="a5eaa-135">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="a5eaa-136">В левой панели навигации нажмите **кнопку Конфигурация** сети, а затем щелкните **Маршрут региона**.</span><span class="sxs-lookup"><span data-stu-id="a5eaa-136">In the left navigation bar, click **Network Configuration**, and then click **Region Route**.</span></span>

4.  <span data-ttu-id="a5eaa-137">На странице **Маршрут к региону** щелкните **Создать**.</span><span class="sxs-lookup"><span data-stu-id="a5eaa-137">On the **Region Route** page, click **New**.</span></span>

5.  <span data-ttu-id="a5eaa-138">В области **Новый маршрут к региону** введите значение в поле **Имя**.</span><span class="sxs-lookup"><span data-stu-id="a5eaa-138">In **New Region Route**, type a value in the **Name** field.</span></span>
   
    > [!NOTE]  
    > <span data-ttu-id="a5eaa-139">Это значение должно быть уникальным в развертывании Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="a5eaa-139">This value must be unique within your Skype for Business Server deployment.</span></span>

6.  <span data-ttu-id="a5eaa-140">Из выпадаемого списка "Область сети **\# 1"** выберите один из двух областей, подключенных по этому маршруту.</span><span class="sxs-lookup"><span data-stu-id="a5eaa-140">From the **Network region \#1** drop-down list, select one of the two regions to be connected by this route.</span></span>

7.  <span data-ttu-id="a5eaa-141">Из выпадаемого списка "Область сети **\# 2"** выберите другой регион для этого маршрута.</span><span class="sxs-lookup"><span data-stu-id="a5eaa-141">From the **Network region \#2** drop-down list, select the other region for this route.</span></span> <span data-ttu-id="a5eaa-142">Этот регион должен быть отличается от региона, выбранного для области Сети \# 1.</span><span class="sxs-lookup"><span data-stu-id="a5eaa-142">This region must be different from the region selected for Network region \#1.</span></span>

8.  <span data-ttu-id="a5eaa-p107">Используйте поле со списком **Связи регионов сети**, чтобы добавить в маршрут связи с регионами. Щелкните кнопку **Добавить** для отображения страницы **Связь с регионом**. Щелкните связь с регионом, чтобы добавить ее в маршрут, и щелкните **ОК**.</span><span class="sxs-lookup"><span data-stu-id="a5eaa-p107">Use the **Network region links** list box to add region links to the route. Click the **Add** button to display the **Region Link** page. Click a region link to add to this route, and then click **OK**.</span></span>
    
    > [!NOTE]  
    > <span data-ttu-id="a5eaa-146">Нажимайте кнопку **Добавить**, чтобы добавить дополнительные связи, или выберите связь и щелкните **Удалить** для удаления соединения.</span><span class="sxs-lookup"><span data-stu-id="a5eaa-146">Continue to click the **Add** button to add more links, or select a link and click **Remove** to remove a link.</span></span>

9.  <span data-ttu-id="a5eaa-147">Щелкните **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="a5eaa-147">Click **Commit**.</span></span>


### <a name="to-modify-a-network-region-route"></a><span data-ttu-id="a5eaa-148">Изменение маршрута к региону сети</span><span class="sxs-lookup"><span data-stu-id="a5eaa-148">To modify a network region route</span></span>

1.  <span data-ttu-id="a5eaa-149">С учетной записи пользователя, которая входит в группу RTCUniversalServerAdmins (или имеет эквивалентные права пользователя) или назначена роли CsAdministrator, войдите на любой компьютер во внутреннем развертывании.</span><span class="sxs-lookup"><span data-stu-id="a5eaa-149">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="a5eaa-150">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Skype для бизнес-серверов.</span><span class="sxs-lookup"><span data-stu-id="a5eaa-150">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="a5eaa-151">В левой панели навигации нажмите **кнопку Конфигурация** сети, а затем щелкните **Маршрут региона**.</span><span class="sxs-lookup"><span data-stu-id="a5eaa-151">In the left navigation bar, click **Network Configuration**, and then click **Region Route**.</span></span>

4.  <span data-ttu-id="a5eaa-152">На странице **Маршрут к региону** щелкните маршрут к региону, который необходимо изменить.</span><span class="sxs-lookup"><span data-stu-id="a5eaa-152">On the **Region Route** page, click the region route that you want to modify.</span></span>

5.  <span data-ttu-id="a5eaa-153">В меню **Правка** щелкните **Показать подробности**.</span><span class="sxs-lookup"><span data-stu-id="a5eaa-153">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="a5eaa-154">В области **Изменить маршрут к региону** можно изменить регионы, соединенные этим маршрутом, и связи с регионами, назначенные маршруту.</span><span class="sxs-lookup"><span data-stu-id="a5eaa-154">In **Edit Region Route**, you can modify the regions joined by this route and the region links associated with the route.</span></span>

7.  <span data-ttu-id="a5eaa-155">Щелкните **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="a5eaa-155">Click **Commit**.</span></span>


## <a name="delete-existing-network-region-routes"></a><span data-ttu-id="a5eaa-156">Удаление существующих маршрутов сетевого региона</span><span class="sxs-lookup"><span data-stu-id="a5eaa-156">Delete existing network region routes</span></span>

<span data-ttu-id="a5eaa-157">Каждому региону в конфигурации контроля допуска звонков (CAC) необходимо предоставить возможность доступа к каждой другой области.</span><span class="sxs-lookup"><span data-stu-id="a5eaa-157">Every region within a call admission control (CAC) configuration must have some way to access every other region.</span></span> <span data-ttu-id="a5eaa-158">Связи между регионами накладывают определенные ограничения на пропускную способность, доступную подключениям между областями, и также представляют собой физические соединения; маршруты же определяют путь, который должны пройти подключения от одной области до другой.</span><span class="sxs-lookup"><span data-stu-id="a5eaa-158">While region links set bandwidth limitations on the connections between regions and also represent the physical links, a route determines which linked path the connection will traverse from one region to another.</span></span> <span data-ttu-id="a5eaa-159">Для настройки маршрутов сетевого региона можно использовать панель управления Skype для бизнес-серверов.</span><span class="sxs-lookup"><span data-stu-id="a5eaa-159">You can use the Skype for Business Server Control Panel to configure network region routes.</span></span> <span data-ttu-id="a5eaa-160">С панели управления Skype для бизнес-серверов можно создать, изменить или удалить маршрут сетевого региона.</span><span class="sxs-lookup"><span data-stu-id="a5eaa-160">From the Skype for Business Server Control Panel, you can create, modify, or delete a network region route.</span></span> <span data-ttu-id="a5eaa-161">С помощью инструкций, приведенных в этом разделе, можно удалить существующие маршруты сетевых регионов.</span><span class="sxs-lookup"><span data-stu-id="a5eaa-161">Use this topic to delete existing network region routes.</span></span> 

### <a name="to-delete-a-network-region-route"></a><span data-ttu-id="a5eaa-162">Чтобы удалить маршрут сетевого региона</span><span class="sxs-lookup"><span data-stu-id="a5eaa-162">To delete a network region route</span></span>

1.  <span data-ttu-id="a5eaa-163">С учетной записи пользователя, которая входит в группу RTCUniversalServerAdmins (или имеет эквивалентные права пользователя) или назначена роли CsAdministrator, войдите на любой компьютер во внутреннем развертывании.</span><span class="sxs-lookup"><span data-stu-id="a5eaa-163">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="a5eaa-164">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Skype для бизнес-серверов.</span><span class="sxs-lookup"><span data-stu-id="a5eaa-164">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="a5eaa-165">В левой панели навигации нажмите **кнопку Конфигурация** сети, а затем щелкните **Маршрут региона**.</span><span class="sxs-lookup"><span data-stu-id="a5eaa-165">In the left navigation bar, click **Network Configuration**, and then click **Region Route**.</span></span>

4.  <span data-ttu-id="a5eaa-166">На странице **Маршрут региона** щелкните маршрут, который следует удалить.</span><span class="sxs-lookup"><span data-stu-id="a5eaa-166">On the **Region Route** page, click the region route that you want to delete.</span></span>

    > [!NOTE]  
    > <span data-ttu-id="a5eaa-p109">Одновременно можно удалить сразу несколько маршрутов регионов. Для этого нажмите и удерживайте клавишу CTRL, одновременно выбирая несколько маршрутов регионов. Или щелкните пункт **Выделить все** в меню **Изменить** для выбора сразу нескольких маршрутов.</span><span class="sxs-lookup"><span data-stu-id="a5eaa-p109">You can delete more than one region route at a time. To do this, press CTRL and select multiple region routes while holding down the CTRL key. Or, to select all region routes, click **Select all** on the **Edit** menu.</span></span>

5.  <span data-ttu-id="a5eaa-170">В меню **Изменить** щелкните **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="a5eaa-170">On the **Edit** menu, click **Delete**.</span></span>

6.  <span data-ttu-id="a5eaa-171">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="a5eaa-171">Click **OK**.</span></span>



## <a name="see-also"></a><span data-ttu-id="a5eaa-172">См. также</span><span class="sxs-lookup"><span data-stu-id="a5eaa-172">See Also</span></span>

[<span data-ttu-id="a5eaa-173">Управление сетевыми областями в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="a5eaa-173">Managing network regions in Skype for Business Server</span></span>](managing-network-regions.md)

[<span data-ttu-id="a5eaa-174">New-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="a5eaa-174">New-CsNetworkInterRegionRoute</span></span>](/powershell/module/skype/New-CsNetworkInterRegionRoute)  

[<span data-ttu-id="a5eaa-175">Set-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="a5eaa-175">Set-CsNetworkInterRegionRoute</span></span>](/powershell/module/skype/Set-CsNetworkInterRegionRoute) 
 
[<span data-ttu-id="a5eaa-176">Remove-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="a5eaa-176">Remove-CsNetworkInterRegionRoute</span></span>](/powershell/module/skype/Remove-CsNetworkInterRegionRoute)  

[<span data-ttu-id="a5eaa-177">Get-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="a5eaa-177">Get-CsNetworkInterRegionRoute</span></span>](/powershell/module/skype/Get-CsNetworkInterRegionRoute)