---
title: Управление маршрутов между сетевыми областями
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Маршрута области сети определяет маршрут между парой областей сети. Каждой парой областей сети в вашего развертывания контроля допуска звонков необходимо маршрута области сети.
ms.openlocfilehash: 12e8d9072df3affdb6e47b6ddb0452e0ee5982a5
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2019
ms.locfileid: "30898125"
---
# <a name="managing-network-region-routes-in-skype-for-business-server"></a><span data-ttu-id="fa5d0-104">Управление маршрутами сетевых областей в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="fa5d0-104">Managing network region routes in Skype for Business Server</span></span>

<span data-ttu-id="fa5d0-105">*Маршрут к региону сети* определяет маршрут между парой областей сети.</span><span class="sxs-lookup"><span data-stu-id="fa5d0-105">A *network region route* defines the route between a pair of network regions.</span></span> <span data-ttu-id="fa5d0-106">Каждой парой областей сети в вашего развертывания контроля допуска звонков необходимо маршрута области сети.</span><span class="sxs-lookup"><span data-stu-id="fa5d0-106">Each pair of network regions in your call admission control deployment requires a network region route.</span></span> <span data-ttu-id="fa5d0-107">Это позволяет каждому региону сети в рамках развертывания осуществлять доступ к любому другому региону.</span><span class="sxs-lookup"><span data-stu-id="fa5d0-107">This enables every network region within the deployment to access every other region.</span></span> <span data-ttu-id="fa5d0-108">Используйте процедуры, описанные в этом artilce для просмотра, создания, изменения или удаления маршрутов между сетевыми областями.</span><span class="sxs-lookup"><span data-stu-id="fa5d0-108">Use the procedures in this artilce to view, create, modify, or delete network region routes.</span></span>

## <a name="view-network-region-route-information"></a><span data-ttu-id="fa5d0-109">Просмотр информации о маршруте между областями сети</span><span class="sxs-lookup"><span data-stu-id="fa5d0-109">View network region route information</span></span> 

<span data-ttu-id="fa5d0-110">Каждого региона в конфигурации контроля допуска допуска звонков необходимо определить, какой метод для доступа к любая область.</span><span class="sxs-lookup"><span data-stu-id="fa5d0-110">Every region within a call admission control (CAC) configuration must have some way to access every other region.</span></span> <span data-ttu-id="fa5d0-111">Хотя связей между областями значение ограничения пропускной способности для подключений между областями, а также представляют физические ссылки, маршрут определяют путь, который должны пройти подключения от одного региона в другой.</span><span class="sxs-lookup"><span data-stu-id="fa5d0-111">While region links set bandwidth limitations on the connections between regions and also represent the physical links, a route determines which linked path the connection will traverse from one region to another.</span></span> <span data-ttu-id="fa5d0-112">Используйте следующие процедуры для просмотра существующих маршрутов областей сети в Скайп для панели управления Business Server или Скайп для консоли Business Server.</span><span class="sxs-lookup"><span data-stu-id="fa5d0-112">Use the following procedures to view existing network region routes in Skype for Business Server Control Panel or Skype for Business Server Management Shell.</span></span> 

### <a name="to-view-network-region-route-information-in-skype-for-business-server-control-panel"></a><span data-ttu-id="fa5d0-113">Для просмотра информации о маршруте между областями сети в Скайп для панели управления Business Server</span><span class="sxs-lookup"><span data-stu-id="fa5d0-113">To view network region route information in Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="fa5d0-114">Войдите на любой компьютер, находящийся во внутреннем развертывании, с использованием учетной записи, входящей в группу RTCUniversalServerAdmins (или имеющей равнозначные права пользователя) либо назначенной роли CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="fa5d0-114">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="fa5d0-115">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть Скайп для панели управления Business Server.</span><span class="sxs-lookup"><span data-stu-id="fa5d0-115">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="fa5d0-116">В левой панели навигации щелкните **Конфигурация сети**и затем щелкните **Маршрут региона**.</span><span class="sxs-lookup"><span data-stu-id="fa5d0-116">In the left navigation bar, click **Network Configuration**, and then click **Region Route**.</span></span>

4.  <span data-ttu-id="fa5d0-117">На странице **Маршрут к региону** щелкните маршрут к региону, который требуется просмотреть.</span><span class="sxs-lookup"><span data-stu-id="fa5d0-117">On the **Region Route** page, click the region route that you want to view.</span></span>


    > [!NOTE]  
    > <span data-ttu-id="fa5d0-118">Одновременно можно просматривать только один маршрут.</span><span class="sxs-lookup"><span data-stu-id="fa5d0-118">You can only view one region route at a time.</span></span>


5.  <span data-ttu-id="fa5d0-119">В меню **Правка** щелкните **Подробнее**.</span><span class="sxs-lookup"><span data-stu-id="fa5d0-119">On the **Edit** menu, click **Show details**.</span></span>


### <a name="viewing-network-region-route-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="fa5d0-120">Просмотр сведений о маршруте между областями сети с помощью командлетов Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="fa5d0-120">Viewing Network Region Route Information by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="fa5d0-121">Информации о маршруте между областями сети можно просматривать с помощью командлета Get-CsNetworkInterRegionRoute и Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fa5d0-121">Network region route information can be viewed by using Windows PowerShell and the Get-CsNetworkInterRegionRoute cmdlet.</span></span> <span data-ttu-id="fa5d0-122">Этот командлет можно запустить из Скайп для консоли Business Server или из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fa5d0-122">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

### <a name="to-view-network-region-route-information"></a><span data-ttu-id="fa5d0-123">Для просмотра информации о маршруте между областями сети</span><span class="sxs-lookup"><span data-stu-id="fa5d0-123">To view network region route information</span></span>

  - <span data-ttu-id="fa5d0-124">Чтобы просмотреть сведения обо всех маршрутах между областями сети, введите следующую команду в Скайп для консоли Business Server и нажмите клавишу ВВОД:</span><span class="sxs-lookup"><span data-stu-id="fa5d0-124">To view information about all your network region routes, type the following command in the Skype for Business Server Management Shell, and then press ENTER:</span></span>
    
        Get-CsNetworkInterRegionRoute
    
    <span data-ttu-id="fa5d0-125">Команда возвращает примерно следующую информацию:</span><span class="sxs-lookup"><span data-stu-id="fa5d0-125">That will return information similar to this:</span></span>
    
        Identity                  : TransAmericaRoute
        NetworkRegionLinks        : {NorthwestToNortheast}
        InterNetworkRegionRouteID : TransAmericaRoute
        NetworkRegionID1          : Pacific Northwest
        NetworkRegionID2          : Northeast

<span data-ttu-id="fa5d0-126">Для получения дополнительных сведений см раздел справки для командлета [Get-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterRegionRoute) .</span><span class="sxs-lookup"><span data-stu-id="fa5d0-126">For more information, see the help topic for the [Get-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterRegionRoute) cmdlet.</span></span>


## <a name="create-or-modify-network-region-routes"></a><span data-ttu-id="fa5d0-127">Создание или изменение маршрутов между сетевыми областями</span><span class="sxs-lookup"><span data-stu-id="fa5d0-127">Create or modify network region routes</span></span>

<span data-ttu-id="fa5d0-128">Каждого региона в конфигурации контроля допуска допуска звонков необходимо определить, какой метод для доступа к любая область.</span><span class="sxs-lookup"><span data-stu-id="fa5d0-128">Every region within a call admission control (CAC) configuration must have some way to access every other region.</span></span> <span data-ttu-id="fa5d0-129">Хотя связей между областями значение ограничения пропускной способности для подключений между областями, а также представляют физические ссылки, маршрут определяют путь, который должны пройти подключения от одного региона в другой.</span><span class="sxs-lookup"><span data-stu-id="fa5d0-129">While region links set bandwidth limitations on the connections between regions and also represent the physical links, a route determines which linked path the connection will traverse from one region to another.</span></span> <span data-ttu-id="fa5d0-130">Скайп для панели управления Business Server можно использовать для настройки маршрутов между сетевыми областями.</span><span class="sxs-lookup"><span data-stu-id="fa5d0-130">You can use the Skype for Business Server Control Panel to configure network region routes.</span></span> <span data-ttu-id="fa5d0-131">Из Скайп для панели управления Business Server создание, изменение или удаление маршрута области сети.</span><span class="sxs-lookup"><span data-stu-id="fa5d0-131">From the Skype for Business Server Control Panel, you can create, modify, or delete a network region route.</span></span> <span data-ttu-id="fa5d0-132">Используйте этот раздел для создания или изменения маршрута области сети.</span><span class="sxs-lookup"><span data-stu-id="fa5d0-132">Use this topic to create or modify a network region route.</span></span> 

### <a name="to-create-a-network-region-route"></a><span data-ttu-id="fa5d0-133">Создание маршрута области сети</span><span class="sxs-lookup"><span data-stu-id="fa5d0-133">To create a network region route</span></span>

1.  <span data-ttu-id="fa5d0-134">Войдите на любой компьютер, находящийся во внутреннем развертывании, с использованием учетной записи, входящей в группу RTCUniversalServerAdmins (или имеющей равнозначные права пользователя) либо назначенной роли CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="fa5d0-134">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="fa5d0-135">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть Скайп для панели управления Business Server.</span><span class="sxs-lookup"><span data-stu-id="fa5d0-135">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="fa5d0-136">В левой панели навигации щелкните **Конфигурация сети**и затем щелкните **Маршрут региона**.</span><span class="sxs-lookup"><span data-stu-id="fa5d0-136">In the left navigation bar, click **Network Configuration**, and then click **Region Route**.</span></span>

4.  <span data-ttu-id="fa5d0-137">На странице **Маршрут** к региону нажмите кнопку **Создать**.</span><span class="sxs-lookup"><span data-stu-id="fa5d0-137">On the **Region Route** page, click **New**.</span></span>

5.  <span data-ttu-id="fa5d0-138">В области **новый маршрут к региону**введите значение в поле **имя** .</span><span class="sxs-lookup"><span data-stu-id="fa5d0-138">In **New Region Route**, type a value in the **Name** field.</span></span>
   
    > [!NOTE]  
    > <span data-ttu-id="fa5d0-139">Это значение должно быть уникальным в рамках вашей Скайп для развертывания Business Server.</span><span class="sxs-lookup"><span data-stu-id="fa5d0-139">This value must be unique within your Skype for Business Server deployment.</span></span>

6.  <span data-ttu-id="fa5d0-140">Из **области сети \#1** раскрывающегося списка, выберите один из двух регионов для подключения по этому маршруту.</span><span class="sxs-lookup"><span data-stu-id="fa5d0-140">From the **Network region \#1** drop-down list, select one of the two regions to be connected by this route.</span></span>

7.  <span data-ttu-id="fa5d0-141">Из **области сети \#2** раскрывающегося списка выберите другие области для маршрута.</span><span class="sxs-lookup"><span data-stu-id="fa5d0-141">From the **Network region \#2** drop-down list, select the other region for this route.</span></span> <span data-ttu-id="fa5d0-142">Эта область должно отличаться от региона, выбранного для области сети \#1.</span><span class="sxs-lookup"><span data-stu-id="fa5d0-142">This region must be different from the region selected for Network region \#1.</span></span>

8.  <span data-ttu-id="fa5d0-143">Используйте список **связей между областями** для добавления связей между областями маршруту.</span><span class="sxs-lookup"><span data-stu-id="fa5d0-143">Use the **Network region links** list box to add region links to the route.</span></span> <span data-ttu-id="fa5d0-144">Нажмите кнопку **Добавить** , чтобы отобразить страницу **Связь между областями** .</span><span class="sxs-lookup"><span data-stu-id="fa5d0-144">Click the **Add** button to display the **Region Link** page.</span></span> <span data-ttu-id="fa5d0-145">Щелкните связь между областями, чтобы добавить этот маршрут и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="fa5d0-145">Click a region link to add to this route, and then click **OK**.</span></span>
    
    > [!NOTE]  
    > <span data-ttu-id="fa5d0-146">Продолжайте, нажмите кнопку **Добавить** , чтобы добавить дополнительные связи, или выберите связь и нажмите кнопку **Удалить** для удаления соединения.</span><span class="sxs-lookup"><span data-stu-id="fa5d0-146">Continue to click the **Add** button to add more links, or select a link and click **Remove** to remove a link.</span></span>

9.  <span data-ttu-id="fa5d0-147">Нажмите **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="fa5d0-147">Click **Commit**.</span></span>


### <a name="to-modify-a-network-region-route"></a><span data-ttu-id="fa5d0-148">Изменение маршрута области сети</span><span class="sxs-lookup"><span data-stu-id="fa5d0-148">To modify a network region route</span></span>

1.  <span data-ttu-id="fa5d0-149">Войдите на любой компьютер, находящийся во внутреннем развертывании, с использованием учетной записи, входящей в группу RTCUniversalServerAdmins (или имеющей равнозначные права пользователя) либо назначенной роли CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="fa5d0-149">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="fa5d0-150">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть Скайп для панели управления Business Server.</span><span class="sxs-lookup"><span data-stu-id="fa5d0-150">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="fa5d0-151">В левой панели навигации щелкните **Конфигурация сети**и затем щелкните **Маршрут региона**.</span><span class="sxs-lookup"><span data-stu-id="fa5d0-151">In the left navigation bar, click **Network Configuration**, and then click **Region Route**.</span></span>

4.  <span data-ttu-id="fa5d0-152">На странице **Маршрут к региону** щелкните маршрут к региону, который требуется изменить.</span><span class="sxs-lookup"><span data-stu-id="fa5d0-152">On the **Region Route** page, click the region route that you want to modify.</span></span>

5.  <span data-ttu-id="fa5d0-153">В меню **Правка** щелкните **Подробнее**.</span><span class="sxs-lookup"><span data-stu-id="fa5d0-153">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="fa5d0-154">В области **изменить маршрут к региону**можно изменить регионы, соединенные этим маршрутом и связи с регионами маршрут.</span><span class="sxs-lookup"><span data-stu-id="fa5d0-154">In **Edit Region Route**, you can modify the regions joined by this route and the region links associated with the route.</span></span>

7.  <span data-ttu-id="fa5d0-155">Нажмите **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="fa5d0-155">Click **Commit**.</span></span>


## <a name="delete-existing-network-region-routes"></a><span data-ttu-id="fa5d0-156">Удаление существующих маршрутов областей сети</span><span class="sxs-lookup"><span data-stu-id="fa5d0-156">Delete existing network region routes</span></span>

<span data-ttu-id="fa5d0-157">Каждого региона в конфигурации контроля допуска допуска звонков необходимо определить, какой метод для доступа к любая область.</span><span class="sxs-lookup"><span data-stu-id="fa5d0-157">Every region within a call admission control (CAC) configuration must have some way to access every other region.</span></span> <span data-ttu-id="fa5d0-158">Хотя связей между областями значение ограничения пропускной способности для подключений между областями, а также представляют физические ссылки, маршрут определяют путь, который должны пройти подключения от одного региона в другой.</span><span class="sxs-lookup"><span data-stu-id="fa5d0-158">While region links set bandwidth limitations on the connections between regions and also represent the physical links, a route determines which linked path the connection will traverse from one region to another.</span></span> <span data-ttu-id="fa5d0-159">Скайп для панели управления Business Server можно использовать для настройки маршрутов между сетевыми областями.</span><span class="sxs-lookup"><span data-stu-id="fa5d0-159">You can use the Skype for Business Server Control Panel to configure network region routes.</span></span> <span data-ttu-id="fa5d0-160">Из Скайп для панели управления Business Server создание, изменение или удаление маршрута области сети.</span><span class="sxs-lookup"><span data-stu-id="fa5d0-160">From the Skype for Business Server Control Panel, you can create, modify, or delete a network region route.</span></span> <span data-ttu-id="fa5d0-161">Используйте этот раздел для удаления существующих маршрутов областей сети.</span><span class="sxs-lookup"><span data-stu-id="fa5d0-161">Use this topic to delete existing network region routes.</span></span> 

### <a name="to-delete-a-network-region-route"></a><span data-ttu-id="fa5d0-162">Удаление маршрута области сети</span><span class="sxs-lookup"><span data-stu-id="fa5d0-162">To delete a network region route</span></span>

1.  <span data-ttu-id="fa5d0-163">Войдите на любой компьютер, находящийся во внутреннем развертывании, с использованием учетной записи, входящей в группу RTCUniversalServerAdmins (или имеющей равнозначные права пользователя) либо назначенной роли CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="fa5d0-163">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="fa5d0-164">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть Скайп для панели управления Business Server.</span><span class="sxs-lookup"><span data-stu-id="fa5d0-164">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="fa5d0-165">В левой панели навигации щелкните **Конфигурация сети**и затем щелкните **Маршрут региона**.</span><span class="sxs-lookup"><span data-stu-id="fa5d0-165">In the left navigation bar, click **Network Configuration**, and then click **Region Route**.</span></span>

4.  <span data-ttu-id="fa5d0-166">На странице **Маршрут к региону** щелкните маршрут к региону, который требуется удалить.</span><span class="sxs-lookup"><span data-stu-id="fa5d0-166">On the **Region Route** page, click the region route that you want to delete.</span></span>

    > [!NOTE]  
    > <span data-ttu-id="fa5d0-167">Можно удалить более чем один маршрут за раз.</span><span class="sxs-lookup"><span data-stu-id="fa5d0-167">You can delete more than one region route at a time.</span></span> <span data-ttu-id="fa5d0-168">Для этого нажмите клавишу CTRL и выберите несколько маршрутов между областями, удерживая нажатой клавишу CTRL.</span><span class="sxs-lookup"><span data-stu-id="fa5d0-168">To do this, press CTRL and select multiple region routes while holding down the CTRL key.</span></span> <span data-ttu-id="fa5d0-169">Или, чтобы выбрать все маршруты области, нажмите кнопку **Выбрать все** в меню **Правка** .</span><span class="sxs-lookup"><span data-stu-id="fa5d0-169">Or, to select all region routes, click **Select all** on the **Edit** menu.</span></span>

5.  <span data-ttu-id="fa5d0-170">В меню **Правка** выберите пункт **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="fa5d0-170">On the **Edit** menu, click **Delete**.</span></span>

6.  <span data-ttu-id="fa5d0-171">Нажмите **ОК**.</span><span class="sxs-lookup"><span data-stu-id="fa5d0-171">Click **OK**.</span></span>



## <a name="see-also"></a><span data-ttu-id="fa5d0-172">См. также</span><span class="sxs-lookup"><span data-stu-id="fa5d0-172">See Also</span></span>

[<span data-ttu-id="fa5d0-173">Управление сетевыми областями в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="fa5d0-173">Managing network regions in Skype for Business Server</span></span>](managing-network-regions.md)

[<span data-ttu-id="fa5d0-174">New-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="fa5d0-174">New-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterRegionRoute)  

[<span data-ttu-id="fa5d0-175">Set-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="fa5d0-175">Set-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterRegionRoute) 
 
[<span data-ttu-id="fa5d0-176">Remove-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="fa5d0-176">Remove-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterRegionRoute)  

[<span data-ttu-id="fa5d0-177">Get-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="fa5d0-177">Get-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterRegionRoute)  
