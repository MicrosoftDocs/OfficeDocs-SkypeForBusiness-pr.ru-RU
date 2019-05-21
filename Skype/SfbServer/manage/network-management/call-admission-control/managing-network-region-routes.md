---
title: Управление маршрутами сетевого региона
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Маршрут к сетевому региону определяет маршрут между парой областей сети. Для каждой пары областей сети в развертывании средства управления допуском звонков требуется маршрут к сетевому региону.
ms.openlocfilehash: 174fdd021655f3e338001582a1409107b266582e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34279510"
---
# <a name="managing-network-region-routes-in-skype-for-business-server"></a><span data-ttu-id="532de-104">Управление маршрутами сетевых областей в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="532de-104">Managing network region routes in Skype for Business Server</span></span>

<span data-ttu-id="532de-105">*Маршрут* к сетевому региону определяет маршрут между парой областей сети.</span><span class="sxs-lookup"><span data-stu-id="532de-105">A *network region route* defines the route between a pair of network regions.</span></span> <span data-ttu-id="532de-106">Для каждой пары областей сети в развертывании средства управления допуском звонков требуется маршрут к сетевому региону.</span><span class="sxs-lookup"><span data-stu-id="532de-106">Each pair of network regions in your call admission control deployment requires a network region route.</span></span> <span data-ttu-id="532de-107">Это позволяет каждому региону сети в рамках развертывания осуществлять доступ к любому другому региону.</span><span class="sxs-lookup"><span data-stu-id="532de-107">This enables every network region within the deployment to access every other region.</span></span> <span data-ttu-id="532de-108">Используйте процедуры, описанные в этом артилце, для просмотра, создания, изменения и удаления маршрутов сетевого региона.</span><span class="sxs-lookup"><span data-stu-id="532de-108">Use the procedures in this artilce to view, create, modify, or delete network region routes.</span></span>

## <a name="view-network-region-route-information"></a><span data-ttu-id="532de-109">Просмотр сведений о маршруте сетевого региона</span><span class="sxs-lookup"><span data-stu-id="532de-109">View network region route information</span></span> 

<span data-ttu-id="532de-110">Каждый регион в конфигурации управления допуском звонков (CAC) должен иметь какой-либо способ получить доступ ко всем остальным регионам.</span><span class="sxs-lookup"><span data-stu-id="532de-110">Every region within a call admission control (CAC) configuration must have some way to access every other region.</span></span> <span data-ttu-id="532de-111">Несмотря на то, что ссылки на области устанавливают ограничения пропускной способности для подключений между регионами и представляют собой физические ссылки, маршрут определяет связанный путь, который будет проходить соединение между двумя областями.</span><span class="sxs-lookup"><span data-stu-id="532de-111">While region links set bandwidth limitations on the connections between regions and also represent the physical links, a route determines which linked path the connection will traverse from one region to another.</span></span> <span data-ttu-id="532de-112">Воспользуйтесь приведенными ниже инструкциями, чтобы просмотреть существующие маршруты к сетевым областям на панели управления в Skype для бизнеса Server или в командной консоли управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="532de-112">Use the following procedures to view existing network region routes in Skype for Business Server Control Panel or Skype for Business Server Management Shell.</span></span> 

### <a name="to-view-network-region-route-information-in-skype-for-business-server-control-panel"></a><span data-ttu-id="532de-113">Просмотр сведений о маршруте на сетевом регионе на панели управления Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="532de-113">To view network region route information in Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="532de-114">Войдите на любой компьютер, находящийся во внутреннем развертывании, с использованием учетной записи, входящей в группу RTCUniversalServerAdmins (или имеющей равнозначные права пользователя) либо назначенной роли CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="532de-114">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="532de-115">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="532de-115">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="532de-116">На панели навигации слева выберите пункт **Настройка сети**, а затем — пункт **путь**к региону.</span><span class="sxs-lookup"><span data-stu-id="532de-116">In the left navigation bar, click **Network Configuration**, and then click **Region Route**.</span></span>

4.  <span data-ttu-id="532de-117">На странице " **регион** " щелкните маршрут области, который вы хотите просмотреть.</span><span class="sxs-lookup"><span data-stu-id="532de-117">On the **Region Route** page, click the region route that you want to view.</span></span>


    > [!NOTE]  
    > <span data-ttu-id="532de-118">Вы можете просматривать только один маршрут области за раз.</span><span class="sxs-lookup"><span data-stu-id="532de-118">You can only view one region route at a time.</span></span>


5.  <span data-ttu-id="532de-119">В меню **Правка** щелкните **Подробнее**.</span><span class="sxs-lookup"><span data-stu-id="532de-119">On the **Edit** menu, click **Show details**.</span></span>


### <a name="viewing-network-region-route-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="532de-120">Просмотр сведений о маршруте сетевого региона с помощью командлетов Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="532de-120">Viewing Network Region Route Information by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="532de-121">Сведения о маршруте сетевого региона можно просмотреть с помощью Windows PowerShell и командлета Get-Кснетворкинтеррегионрауте.</span><span class="sxs-lookup"><span data-stu-id="532de-121">Network region route information can be viewed by using Windows PowerShell and the Get-CsNetworkInterRegionRoute cmdlet.</span></span> <span data-ttu-id="532de-122">Этот командлет можно выполнить либо из командной консоли Skype для бизнеса Server, либо из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="532de-122">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

### <a name="to-view-network-region-route-information"></a><span data-ttu-id="532de-123">Просмотр сведений о маршруте сетевого региона</span><span class="sxs-lookup"><span data-stu-id="532de-123">To view network region route information</span></span>

  - <span data-ttu-id="532de-124">Чтобы просмотреть сведения о всех маршрутах сетевого региона, введите в командной консоли Skype для Business Server указанную ниже команду и нажмите клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="532de-124">To view information about all your network region routes, type the following command in the Skype for Business Server Management Shell, and then press ENTER:</span></span>
    
        Get-CsNetworkInterRegionRoute
    
    <span data-ttu-id="532de-125">Команда возвращает примерно следующую информацию:</span><span class="sxs-lookup"><span data-stu-id="532de-125">That will return information similar to this:</span></span>
    
        Identity                  : TransAmericaRoute
        NetworkRegionLinks        : {NorthwestToNortheast}
        InterNetworkRegionRouteID : TransAmericaRoute
        NetworkRegionID1          : Pacific Northwest
        NetworkRegionID2          : Northeast

<span data-ttu-id="532de-126">Дополнительные сведения можно найти в разделе справки по командлету [Get-кснетворкинтеррегионрауте](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterRegionRoute) .</span><span class="sxs-lookup"><span data-stu-id="532de-126">For more information, see the help topic for the [Get-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterRegionRoute) cmdlet.</span></span>


## <a name="create-or-modify-network-region-routes"></a><span data-ttu-id="532de-127">Создание и изменение маршрутов сетевого региона</span><span class="sxs-lookup"><span data-stu-id="532de-127">Create or modify network region routes</span></span>

<span data-ttu-id="532de-128">Каждый регион в конфигурации управления допуском звонков (CAC) должен иметь какой-либо способ получить доступ ко всем остальным регионам.</span><span class="sxs-lookup"><span data-stu-id="532de-128">Every region within a call admission control (CAC) configuration must have some way to access every other region.</span></span> <span data-ttu-id="532de-129">Несмотря на то, что ссылки на области устанавливают ограничения пропускной способности для подключений между регионами и представляют собой физические ссылки, маршрут определяет связанный путь, который будет проходить соединение между двумя областями.</span><span class="sxs-lookup"><span data-stu-id="532de-129">While region links set bandwidth limitations on the connections between regions and also represent the physical links, a route determines which linked path the connection will traverse from one region to another.</span></span> <span data-ttu-id="532de-130">Настроить маршруты к сетевым регионам можно с помощью панели управления "Skype для бизнеса" на сервере.</span><span class="sxs-lookup"><span data-stu-id="532de-130">You can use the Skype for Business Server Control Panel to configure network region routes.</span></span> <span data-ttu-id="532de-131">С помощью панели управления Skype для бизнеса Server вы можете создавать, изменять и удалять маршруты сетевого региона.</span><span class="sxs-lookup"><span data-stu-id="532de-131">From the Skype for Business Server Control Panel, you can create, modify, or delete a network region route.</span></span> <span data-ttu-id="532de-132">Этот раздел используется для создания и изменения маршрута сетевого региона.</span><span class="sxs-lookup"><span data-stu-id="532de-132">Use this topic to create or modify a network region route.</span></span> 

### <a name="to-create-a-network-region-route"></a><span data-ttu-id="532de-133">Чтобы создать маршрут к сетевому региону</span><span class="sxs-lookup"><span data-stu-id="532de-133">To create a network region route</span></span>

1.  <span data-ttu-id="532de-134">Войдите на любой компьютер, находящийся во внутреннем развертывании, с использованием учетной записи, входящей в группу RTCUniversalServerAdmins (или имеющей равнозначные права пользователя) либо назначенной роли CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="532de-134">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="532de-135">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="532de-135">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="532de-136">На панели навигации слева выберите пункт **Настройка сети**, а затем — пункт **путь**к региону.</span><span class="sxs-lookup"><span data-stu-id="532de-136">In the left navigation bar, click **Network Configuration**, and then click **Region Route**.</span></span>

4.  <span data-ttu-id="532de-137">На странице " **регион** " нажмите кнопку **создать**.</span><span class="sxs-lookup"><span data-stu-id="532de-137">On the **Region Route** page, click **New**.</span></span>

5.  <span data-ttu-id="532de-138">В разделе **Новый маршрут**введите значение в поле **имя** .</span><span class="sxs-lookup"><span data-stu-id="532de-138">In **New Region Route**, type a value in the **Name** field.</span></span>
   
    > [!NOTE]  
    > <span data-ttu-id="532de-139">Это значение должно быть уникальным в рамках развертывания Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="532de-139">This value must be unique within your Skype for Business Server deployment.</span></span>

6.  <span data-ttu-id="532de-140">В раскрывающемся списке **сетевой регион \#1** выберите один из двух областей, которые должны быть соединены этим маршрутом.</span><span class="sxs-lookup"><span data-stu-id="532de-140">From the **Network region \#1** drop-down list, select one of the two regions to be connected by this route.</span></span>

7.  <span data-ttu-id="532de-141">В раскрывающемся списке **сетевой регион \#2** выберите другой регион для этого маршрута.</span><span class="sxs-lookup"><span data-stu-id="532de-141">From the **Network region \#2** drop-down list, select the other region for this route.</span></span> <span data-ttu-id="532de-142">Этот регион должен отличаться от региона, выбранного для сетевого региона \#1.</span><span class="sxs-lookup"><span data-stu-id="532de-142">This region must be different from the region selected for Network region \#1.</span></span>

8.  <span data-ttu-id="532de-143">С помощью списка " **сетевой регион** " можно добавить в маршрут ссылки на регион.</span><span class="sxs-lookup"><span data-stu-id="532de-143">Use the **Network region links** list box to add region links to the route.</span></span> <span data-ttu-id="532de-144">Нажмите кнопку " **Добавить** ", чтобы открыть страницу **ссылки "регион** ".</span><span class="sxs-lookup"><span data-stu-id="532de-144">Click the **Add** button to display the **Region Link** page.</span></span> <span data-ttu-id="532de-145">Щелкните ссылку на регион, чтобы добавить в этот маршрут, и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="532de-145">Click a region link to add to this route, and then click **OK**.</span></span>
    
    > [!NOTE]  
    > <span data-ttu-id="532de-146">Нажмите кнопку **Добавить** , чтобы добавить ссылки, или выберите ссылку, а затем нажмите кнопку **Удалить** , чтобы удалить ссылку.</span><span class="sxs-lookup"><span data-stu-id="532de-146">Continue to click the **Add** button to add more links, or select a link and click **Remove** to remove a link.</span></span>

9.  <span data-ttu-id="532de-147">Нажмите **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="532de-147">Click **Commit**.</span></span>


### <a name="to-modify-a-network-region-route"></a><span data-ttu-id="532de-148">Изменение маршрута сетевого региона</span><span class="sxs-lookup"><span data-stu-id="532de-148">To modify a network region route</span></span>

1.  <span data-ttu-id="532de-149">Войдите на любой компьютер, находящийся во внутреннем развертывании, с использованием учетной записи, входящей в группу RTCUniversalServerAdmins (или имеющей равнозначные права пользователя) либо назначенной роли CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="532de-149">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="532de-150">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="532de-150">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="532de-151">На панели навигации слева выберите пункт **Настройка сети**, а затем — пункт **путь**к региону.</span><span class="sxs-lookup"><span data-stu-id="532de-151">In the left navigation bar, click **Network Configuration**, and then click **Region Route**.</span></span>

4.  <span data-ttu-id="532de-152">На странице " **регион** " щелкните маршрут региона, который вы хотите изменить.</span><span class="sxs-lookup"><span data-stu-id="532de-152">On the **Region Route** page, click the region route that you want to modify.</span></span>

5.  <span data-ttu-id="532de-153">В меню **Правка** щелкните **Подробнее**.</span><span class="sxs-lookup"><span data-stu-id="532de-153">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="532de-154">В окне " **изменить маршрут области**" можно изменить регионы, Соединенные этим маршрутом, и ссылки на области, связанные с этим маршрутом.</span><span class="sxs-lookup"><span data-stu-id="532de-154">In **Edit Region Route**, you can modify the regions joined by this route and the region links associated with the route.</span></span>

7.  <span data-ttu-id="532de-155">Нажмите **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="532de-155">Click **Commit**.</span></span>


## <a name="delete-existing-network-region-routes"></a><span data-ttu-id="532de-156">Удаление существующих маршрутов сетевого региона</span><span class="sxs-lookup"><span data-stu-id="532de-156">Delete existing network region routes</span></span>

<span data-ttu-id="532de-157">Каждый регион в конфигурации управления допуском звонков (CAC) должен иметь какой-либо способ получить доступ ко всем остальным регионам.</span><span class="sxs-lookup"><span data-stu-id="532de-157">Every region within a call admission control (CAC) configuration must have some way to access every other region.</span></span> <span data-ttu-id="532de-158">Несмотря на то, что ссылки на области устанавливают ограничения пропускной способности для подключений между регионами и представляют собой физические ссылки, маршрут определяет связанный путь, который будет проходить соединение между двумя областями.</span><span class="sxs-lookup"><span data-stu-id="532de-158">While region links set bandwidth limitations on the connections between regions and also represent the physical links, a route determines which linked path the connection will traverse from one region to another.</span></span> <span data-ttu-id="532de-159">Настроить маршруты к сетевым регионам можно с помощью панели управления "Skype для бизнеса" на сервере.</span><span class="sxs-lookup"><span data-stu-id="532de-159">You can use the Skype for Business Server Control Panel to configure network region routes.</span></span> <span data-ttu-id="532de-160">С помощью панели управления Skype для бизнеса Server вы можете создавать, изменять и удалять маршруты сетевого региона.</span><span class="sxs-lookup"><span data-stu-id="532de-160">From the Skype for Business Server Control Panel, you can create, modify, or delete a network region route.</span></span> <span data-ttu-id="532de-161">Этот раздел используется для удаления существующих маршрутов сетевого региона.</span><span class="sxs-lookup"><span data-stu-id="532de-161">Use this topic to delete existing network region routes.</span></span> 

### <a name="to-delete-a-network-region-route"></a><span data-ttu-id="532de-162">Удаление маршрута сетевого региона</span><span class="sxs-lookup"><span data-stu-id="532de-162">To delete a network region route</span></span>

1.  <span data-ttu-id="532de-163">Войдите на любой компьютер, находящийся во внутреннем развертывании, с использованием учетной записи, входящей в группу RTCUniversalServerAdmins (или имеющей равнозначные права пользователя) либо назначенной роли CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="532de-163">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="532de-164">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="532de-164">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="532de-165">На панели навигации слева выберите пункт **Настройка сети**, а затем — пункт **путь**к региону.</span><span class="sxs-lookup"><span data-stu-id="532de-165">In the left navigation bar, click **Network Configuration**, and then click **Region Route**.</span></span>

4.  <span data-ttu-id="532de-166">На странице " **регион** " щелкните маршрут региона, который вы хотите удалить.</span><span class="sxs-lookup"><span data-stu-id="532de-166">On the **Region Route** page, click the region route that you want to delete.</span></span>

    > [!NOTE]  
    > <span data-ttu-id="532de-167">За один раз можно удалить сразу несколько маршрутов.</span><span class="sxs-lookup"><span data-stu-id="532de-167">You can delete more than one region route at a time.</span></span> <span data-ttu-id="532de-168">Для этого нажмите клавишу CTRL и, удерживая нажатой клавишу CTRL, выберите один из нескольких маршрутов областей.</span><span class="sxs-lookup"><span data-stu-id="532de-168">To do this, press CTRL and select multiple region routes while holding down the CTRL key.</span></span> <span data-ttu-id="532de-169">Кроме того, чтобы выделить все маршруты областей, в меню **Правка** выберите команду **выделить все** .</span><span class="sxs-lookup"><span data-stu-id="532de-169">Or, to select all region routes, click **Select all** on the **Edit** menu.</span></span>

5.  <span data-ttu-id="532de-170">В меню **Правка** выберите команду **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="532de-170">On the **Edit** menu, click **Delete**.</span></span>

6.  <span data-ttu-id="532de-171">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="532de-171">Click **OK**.</span></span>



## <a name="see-also"></a><span data-ttu-id="532de-172">См. также</span><span class="sxs-lookup"><span data-stu-id="532de-172">See Also</span></span>

[<span data-ttu-id="532de-173">Управление сетевыми областями в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="532de-173">Managing network regions in Skype for Business Server</span></span>](managing-network-regions.md)

[<span data-ttu-id="532de-174">New-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="532de-174">New-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterRegionRoute)  

[<span data-ttu-id="532de-175">Set-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="532de-175">Set-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterRegionRoute) 
 
[<span data-ttu-id="532de-176">Remove-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="532de-176">Remove-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterRegionRoute)  

[<span data-ttu-id="532de-177">Get-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="532de-177">Get-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterRegionRoute)  
