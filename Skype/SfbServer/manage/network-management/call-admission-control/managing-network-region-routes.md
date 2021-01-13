---
title: Управление маршрутами между областями сети
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
ms.openlocfilehash: 23dec126511b941ff3e25b22c37cbba0854b13bc
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816439"
---
# <a name="managing-network-region-routes-in-skype-for-business-server"></a><span data-ttu-id="7b9c9-104">Управление маршрутами областей сети в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="7b9c9-104">Managing network region routes in Skype for Business Server</span></span>

<span data-ttu-id="7b9c9-105">*Маршрут между областями сети* определяет путь между парой сетевых областей.</span><span class="sxs-lookup"><span data-stu-id="7b9c9-105">A *network region route* defines the route between a pair of network regions.</span></span> <span data-ttu-id="7b9c9-106">Для каждой пары сетевых областей в развертывании контроля допуска звонков необходим маршрут между областями сети.</span><span class="sxs-lookup"><span data-stu-id="7b9c9-106">Each pair of network regions in your call admission control deployment requires a network region route.</span></span> <span data-ttu-id="7b9c9-107">Благодаря этому каждая область сети в рамках развертывания может получить доступ к каждой другой области.</span><span class="sxs-lookup"><span data-stu-id="7b9c9-107">This enables every network region within the deployment to access every other region.</span></span> <span data-ttu-id="7b9c9-108">Используйте процедуры, рассматриваемые в этом объекте, для просмотра, создания, изменения или удаления маршрутов областей сети.</span><span class="sxs-lookup"><span data-stu-id="7b9c9-108">Use the procedures in this artilce to view, create, modify, or delete network region routes.</span></span>

## <a name="view-network-region-route-information"></a><span data-ttu-id="7b9c9-109">Просмотр сведений о маршруте области сети</span><span class="sxs-lookup"><span data-stu-id="7b9c9-109">View network region route information</span></span> 

<span data-ttu-id="7b9c9-110">Каждому региону в конфигурации контроля допуска звонков (CAC) необходимо предоставить возможность доступа к каждой другой области.</span><span class="sxs-lookup"><span data-stu-id="7b9c9-110">Every region within a call admission control (CAC) configuration must have some way to access every other region.</span></span> <span data-ttu-id="7b9c9-111">Связи между регионами накладывают определенные ограничения на пропускную способность, доступную подключениям между областями, и также представляют собой физические соединения; маршруты же определяют путь, который должны пройти подключения от одной области до другой.</span><span class="sxs-lookup"><span data-stu-id="7b9c9-111">While region links set bandwidth limitations on the connections between regions and also represent the physical links, a route determines which linked path the connection will traverse from one region to another.</span></span> <span data-ttu-id="7b9c9-112">Используйте следующие процедуры для просмотра существующих маршрутов между областями сети в панели управления Skype для бизнеса Server или в оболочке управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="7b9c9-112">Use the following procedures to view existing network region routes in Skype for Business Server Control Panel or Skype for Business Server Management Shell.</span></span> 

### <a name="to-view-network-region-route-information-in-skype-for-business-server-control-panel"></a><span data-ttu-id="7b9c9-113">Просмотр сведений о маршруте между областями сети на панели управления Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="7b9c9-113">To view network region route information in Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="7b9c9-114">Из учетной записи пользователя, которая является членом группы RTCUniversalServerAdmins (или имеет эквивалентные права пользователя) или назначена роли CsAdministrator, войдите на любой компьютер во внутреннем развертывании.</span><span class="sxs-lookup"><span data-stu-id="7b9c9-114">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="7b9c9-115">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="7b9c9-115">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="7b9c9-116">В левой панели навигации щелкните **"Конфигурация** сети" и выберите **"Маршрут региона".**</span><span class="sxs-lookup"><span data-stu-id="7b9c9-116">In the left navigation bar, click **Network Configuration**, and then click **Region Route**.</span></span>

4.  <span data-ttu-id="7b9c9-117">На странице **Маршрут региона** выберите маршрут области, который хотите просмотреть.</span><span class="sxs-lookup"><span data-stu-id="7b9c9-117">On the **Region Route** page, click the region route that you want to view.</span></span>


    > [!NOTE]  
    > <span data-ttu-id="7b9c9-118">Можно просматривать только один маршрут за один раз.</span><span class="sxs-lookup"><span data-stu-id="7b9c9-118">You can only view one region route at a time.</span></span>


5.  <span data-ttu-id="7b9c9-119">В меню **Изменить** щелкните **Подробнее**.</span><span class="sxs-lookup"><span data-stu-id="7b9c9-119">On the **Edit** menu, click **Show details**.</span></span>


### <a name="viewing-network-region-route-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="7b9c9-120">Просмотр сведений о маршруте между областями сети с Windows PowerShell с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="7b9c9-120">Viewing Network Region Route Information by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="7b9c9-121">Сведения о маршруте между областями сети можно просмотреть с помощью Windows PowerShell и Get-CsNetworkInterRegionRoute сети.</span><span class="sxs-lookup"><span data-stu-id="7b9c9-121">Network region route information can be viewed by using Windows PowerShell and the Get-CsNetworkInterRegionRoute cmdlet.</span></span> <span data-ttu-id="7b9c9-122">Этот cmdlet можно запустить в оболочке управления Skype для бизнеса Server или в удаленном сеансе Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7b9c9-122">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

### <a name="to-view-network-region-route-information"></a><span data-ttu-id="7b9c9-123">Просмотр сведений о маршруте области сети</span><span class="sxs-lookup"><span data-stu-id="7b9c9-123">To view network region route information</span></span>

  - <span data-ttu-id="7b9c9-124">Чтобы просмотреть сведения обо всех маршрутах между областями сети, введите следующую команду в командной оболочке Skype для бизнеса Server и нажмите ввод:</span><span class="sxs-lookup"><span data-stu-id="7b9c9-124">To view information about all your network region routes, type the following command in the Skype for Business Server Management Shell, and then press ENTER:</span></span>
    
        Get-CsNetworkInterRegionRoute
    
    <span data-ttu-id="7b9c9-125">Это приведет к возврату приблизительно такой информации:</span><span class="sxs-lookup"><span data-stu-id="7b9c9-125">That will return information similar to this:</span></span>
    
        Identity                  : TransAmericaRoute
        NetworkRegionLinks        : {NorthwestToNortheast}
        InterNetworkRegionRouteID : TransAmericaRoute
        NetworkRegionID1          : Pacific Northwest
        NetworkRegionID2          : Northeast

<span data-ttu-id="7b9c9-126">Дополнительные сведения см. в разделе справки по командлету [Get-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterRegionRoute).</span><span class="sxs-lookup"><span data-stu-id="7b9c9-126">For more information, see the help topic for the [Get-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterRegionRoute) cmdlet.</span></span>


## <a name="create-or-modify-network-region-routes"></a><span data-ttu-id="7b9c9-127">Создание или изменение маршрутов областей сети</span><span class="sxs-lookup"><span data-stu-id="7b9c9-127">Create or modify network region routes</span></span>

<span data-ttu-id="7b9c9-128">Каждому региону в конфигурации контроля допуска звонков (CAC) необходимо предоставить возможность доступа к каждой другой области.</span><span class="sxs-lookup"><span data-stu-id="7b9c9-128">Every region within a call admission control (CAC) configuration must have some way to access every other region.</span></span> <span data-ttu-id="7b9c9-129">Связи между регионами накладывают определенные ограничения на пропускную способность, доступную подключениям между областями, и также представляют собой физические соединения; маршруты же определяют путь, который должны пройти подключения от одной области до другой.</span><span class="sxs-lookup"><span data-stu-id="7b9c9-129">While region links set bandwidth limitations on the connections between regions and also represent the physical links, a route determines which linked path the connection will traverse from one region to another.</span></span> <span data-ttu-id="7b9c9-130">Для настройки маршрутов между областями сети можно использовать панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="7b9c9-130">You can use the Skype for Business Server Control Panel to configure network region routes.</span></span> <span data-ttu-id="7b9c9-131">На панели управления Skype для бизнеса Server можно создать, изменить или удалить маршрут между областями сети.</span><span class="sxs-lookup"><span data-stu-id="7b9c9-131">From the Skype for Business Server Control Panel, you can create, modify, or delete a network region route.</span></span> <span data-ttu-id="7b9c9-132">Используйте этот раздел для создания или изменения маршрута маршрут между областями сети.</span><span class="sxs-lookup"><span data-stu-id="7b9c9-132">Use this topic to create or modify a network region route.</span></span> 

### <a name="to-create-a-network-region-route"></a><span data-ttu-id="7b9c9-133">Создание маршрута к регионами сети</span><span class="sxs-lookup"><span data-stu-id="7b9c9-133">To create a network region route</span></span>

1.  <span data-ttu-id="7b9c9-134">Из учетной записи пользователя, которая является членом группы RTCUniversalServerAdmins (или имеет эквивалентные права пользователя) или назначена роли CsAdministrator, войдите на любой компьютер во внутреннем развертывании.</span><span class="sxs-lookup"><span data-stu-id="7b9c9-134">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="7b9c9-135">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="7b9c9-135">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="7b9c9-136">В левой панели навигации щелкните **"Конфигурация** сети" и выберите **"Маршрут региона".**</span><span class="sxs-lookup"><span data-stu-id="7b9c9-136">In the left navigation bar, click **Network Configuration**, and then click **Region Route**.</span></span>

4.  <span data-ttu-id="7b9c9-137">На странице **Маршрут к региону** щелкните **Создать**.</span><span class="sxs-lookup"><span data-stu-id="7b9c9-137">On the **Region Route** page, click **New**.</span></span>

5.  <span data-ttu-id="7b9c9-138">В области **Новый маршрут к региону** введите значение в поле **Имя**.</span><span class="sxs-lookup"><span data-stu-id="7b9c9-138">In **New Region Route**, type a value in the **Name** field.</span></span>
   
    > [!NOTE]  
    > <span data-ttu-id="7b9c9-139">Это значение должно быть уникальным в развертывании Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="7b9c9-139">This value must be unique within your Skype for Business Server deployment.</span></span>

6.  <span data-ttu-id="7b9c9-140">В **выпадаемом \# списке** "Область сети 1" выберите одну из двух областей, которые будут подключены по этому маршруту.</span><span class="sxs-lookup"><span data-stu-id="7b9c9-140">From the **Network region \#1** drop-down list, select one of the two regions to be connected by this route.</span></span>

7.  <span data-ttu-id="7b9c9-141">В **выпадаемом \# списке** "Регион сети 2" выберите другой регион для этого маршрута.</span><span class="sxs-lookup"><span data-stu-id="7b9c9-141">From the **Network region \#2** drop-down list, select the other region for this route.</span></span> <span data-ttu-id="7b9c9-142">Этот регион должен быть отличается от региона, выбранного для области сети \# 1.</span><span class="sxs-lookup"><span data-stu-id="7b9c9-142">This region must be different from the region selected for Network region \#1.</span></span>

8.  <span data-ttu-id="7b9c9-p107">Используйте поле со списком **Связи регионов сети**, чтобы добавить в маршрут связи с регионами. Щелкните кнопку **Добавить** для отображения страницы **Связь с регионом**. Щелкните связь с регионом, чтобы добавить ее в маршрут, и щелкните **ОК**.</span><span class="sxs-lookup"><span data-stu-id="7b9c9-p107">Use the **Network region links** list box to add region links to the route. Click the **Add** button to display the **Region Link** page. Click a region link to add to this route, and then click **OK**.</span></span>
    
    > [!NOTE]  
    > <span data-ttu-id="7b9c9-146">Нажимайте кнопку **Добавить**, чтобы добавить дополнительные связи, или выберите связь и щелкните **Удалить** для удаления соединения.</span><span class="sxs-lookup"><span data-stu-id="7b9c9-146">Continue to click the **Add** button to add more links, or select a link and click **Remove** to remove a link.</span></span>

9.  <span data-ttu-id="7b9c9-147">Щелкните **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="7b9c9-147">Click **Commit**.</span></span>


### <a name="to-modify-a-network-region-route"></a><span data-ttu-id="7b9c9-148">Изменение маршрута к региону сети</span><span class="sxs-lookup"><span data-stu-id="7b9c9-148">To modify a network region route</span></span>

1.  <span data-ttu-id="7b9c9-149">Из учетной записи пользователя, которая является членом группы RTCUniversalServerAdmins (или имеет эквивалентные права пользователя) или назначена роли CsAdministrator, войдите на любой компьютер во внутреннем развертывании.</span><span class="sxs-lookup"><span data-stu-id="7b9c9-149">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="7b9c9-150">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="7b9c9-150">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="7b9c9-151">В левой панели навигации щелкните **"Конфигурация** сети" и выберите **"Маршрут региона".**</span><span class="sxs-lookup"><span data-stu-id="7b9c9-151">In the left navigation bar, click **Network Configuration**, and then click **Region Route**.</span></span>

4.  <span data-ttu-id="7b9c9-152">На странице **Маршрут к региону** щелкните маршрут к региону, который необходимо изменить.</span><span class="sxs-lookup"><span data-stu-id="7b9c9-152">On the **Region Route** page, click the region route that you want to modify.</span></span>

5.  <span data-ttu-id="7b9c9-153">В меню **Правка** щелкните **Показать подробности**.</span><span class="sxs-lookup"><span data-stu-id="7b9c9-153">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="7b9c9-154">В области **Изменить маршрут к региону** можно изменить регионы, соединенные этим маршрутом, и связи с регионами, назначенные маршруту.</span><span class="sxs-lookup"><span data-stu-id="7b9c9-154">In **Edit Region Route**, you can modify the regions joined by this route and the region links associated with the route.</span></span>

7.  <span data-ttu-id="7b9c9-155">Щелкните **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="7b9c9-155">Click **Commit**.</span></span>


## <a name="delete-existing-network-region-routes"></a><span data-ttu-id="7b9c9-156">Удаление существующих маршрутов между областями сети</span><span class="sxs-lookup"><span data-stu-id="7b9c9-156">Delete existing network region routes</span></span>

<span data-ttu-id="7b9c9-157">Каждому региону в конфигурации контроля допуска звонков (CAC) необходимо предоставить возможность доступа к каждой другой области.</span><span class="sxs-lookup"><span data-stu-id="7b9c9-157">Every region within a call admission control (CAC) configuration must have some way to access every other region.</span></span> <span data-ttu-id="7b9c9-158">Связи между регионами накладывают определенные ограничения на пропускную способность, доступную подключениям между областями, и также представляют собой физические соединения; маршруты же определяют путь, который должны пройти подключения от одной области до другой.</span><span class="sxs-lookup"><span data-stu-id="7b9c9-158">While region links set bandwidth limitations on the connections between regions and also represent the physical links, a route determines which linked path the connection will traverse from one region to another.</span></span> <span data-ttu-id="7b9c9-159">Для настройки маршрутов между областями сети можно использовать панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="7b9c9-159">You can use the Skype for Business Server Control Panel to configure network region routes.</span></span> <span data-ttu-id="7b9c9-160">На панели управления Skype для бизнеса Server можно создать, изменить или удалить маршрут между областями сети.</span><span class="sxs-lookup"><span data-stu-id="7b9c9-160">From the Skype for Business Server Control Panel, you can create, modify, or delete a network region route.</span></span> <span data-ttu-id="7b9c9-161">С помощью инструкций, приведенных в этом разделе, можно удалить существующие маршруты сетевых регионов.</span><span class="sxs-lookup"><span data-stu-id="7b9c9-161">Use this topic to delete existing network region routes.</span></span> 

### <a name="to-delete-a-network-region-route"></a><span data-ttu-id="7b9c9-162">Чтобы удалить маршрут сетевого региона</span><span class="sxs-lookup"><span data-stu-id="7b9c9-162">To delete a network region route</span></span>

1.  <span data-ttu-id="7b9c9-163">Из учетной записи пользователя, которая является членом группы RTCUniversalServerAdmins (или имеет эквивалентные права пользователя) или назначена роли CsAdministrator, войдите на любой компьютер во внутреннем развертывании.</span><span class="sxs-lookup"><span data-stu-id="7b9c9-163">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="7b9c9-164">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="7b9c9-164">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="7b9c9-165">В левой панели навигации щелкните **"Конфигурация** сети" и выберите **"Маршрут региона".**</span><span class="sxs-lookup"><span data-stu-id="7b9c9-165">In the left navigation bar, click **Network Configuration**, and then click **Region Route**.</span></span>

4.  <span data-ttu-id="7b9c9-166">На странице **Маршрут региона** щелкните маршрут, который следует удалить.</span><span class="sxs-lookup"><span data-stu-id="7b9c9-166">On the **Region Route** page, click the region route that you want to delete.</span></span>

    > [!NOTE]  
    > <span data-ttu-id="7b9c9-p109">Одновременно можно удалить сразу несколько маршрутов регионов. Для этого нажмите и удерживайте клавишу CTRL, одновременно выбирая несколько маршрутов регионов. Или щелкните пункт **Выделить все** в меню **Изменить** для выбора сразу нескольких маршрутов.</span><span class="sxs-lookup"><span data-stu-id="7b9c9-p109">You can delete more than one region route at a time. To do this, press CTRL and select multiple region routes while holding down the CTRL key. Or, to select all region routes, click **Select all** on the **Edit** menu.</span></span>

5.  <span data-ttu-id="7b9c9-170">В меню **Изменить** щелкните **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="7b9c9-170">On the **Edit** menu, click **Delete**.</span></span>

6.  <span data-ttu-id="7b9c9-171">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="7b9c9-171">Click **OK**.</span></span>



## <a name="see-also"></a><span data-ttu-id="7b9c9-172">См. также</span><span class="sxs-lookup"><span data-stu-id="7b9c9-172">See Also</span></span>

[<span data-ttu-id="7b9c9-173">Управление сетевыми областями в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="7b9c9-173">Managing network regions in Skype for Business Server</span></span>](managing-network-regions.md)

[<span data-ttu-id="7b9c9-174">New-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="7b9c9-174">New-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterRegionRoute)  

[<span data-ttu-id="7b9c9-175">Set-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="7b9c9-175">Set-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterRegionRoute) 
 
[<span data-ttu-id="7b9c9-176">Remove-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="7b9c9-176">Remove-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterRegionRoute)  

[<span data-ttu-id="7b9c9-177">Get-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="7b9c9-177">Get-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterRegionRoute)  
