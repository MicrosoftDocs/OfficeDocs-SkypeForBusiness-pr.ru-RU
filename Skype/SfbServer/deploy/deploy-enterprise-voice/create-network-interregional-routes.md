---
title: Создание межрегиональных сетевых маршрутов в Skype для бизнеса Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 5555262a-a502-4b01-9593-836dd30064f5
description: Создание или изменение маршрутов interregional сети, которые используются контроля допуска звонков корпоративной голосовой связи в Скайп Business Server.
ms.openlocfilehash: 112c74c07956073fee3e51a6e0856d875b6268ff
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="create-network-interregional-routes-in-skype-for-business-server-2015"></a><span data-ttu-id="c53ff-103">Создание межрегиональных сетевых маршрутов в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="c53ff-103">Create network interregional routes in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="c53ff-104">Создание или изменение маршрутов interregional сети, которые используются контроля допуска звонков корпоративной голосовой связи в Скайп Business Server.</span><span class="sxs-lookup"><span data-stu-id="c53ff-104">Create or modify network interregional routes, which are used by Enterprise Voice call admission control in Skype for Business Server.</span></span> 
  
<span data-ttu-id="c53ff-105">Сетевой маршрут interregional определяет маршрут между парой областей сети.</span><span class="sxs-lookup"><span data-stu-id="c53ff-105">A network interregional route defines the route between a pair of network regions.</span></span> <span data-ttu-id="c53ff-106">Маршрут между регионами сети требуется для каждой пары регионов сети в развертывании службы контроля допуска звонков.</span><span class="sxs-lookup"><span data-stu-id="c53ff-106">Each pair of network regions in your call admission control deployment requires a network interregional route.</span></span> <span data-ttu-id="c53ff-107">Это позволяет каждому региону сети в рамках развертывания осуществлять доступ к любому другому региону.</span><span class="sxs-lookup"><span data-stu-id="c53ff-107">This enables every network region within the deployment to access every other region.</span></span>
  
<span data-ttu-id="c53ff-108">Связи между регионами накладывают определенные ограничения на пропускную способность, доступную подключениям между регионами; маршруты же определяют путь, который должны пройти подключения от одного региона до другого.</span><span class="sxs-lookup"><span data-stu-id="c53ff-108">While region links set bandwidth limitations on the connections between regions, an interregional route determines which linked path the connection will traverse from one region to another.</span></span>
  
<span data-ttu-id="c53ff-109">В этом примере топологии необходимо определить маршруты между регионами сети для каждой пары регионов из трех: Северная Америка/EMEA, APAC/EMEA и APAC/Северная Америка.</span><span class="sxs-lookup"><span data-stu-id="c53ff-109">In the example topology, network interregional routes must be defined for each of the three region pairs: North America/EMEA, EMEA/APAC, and North America/APAC.</span></span> 
  
### <a name="to-create-network-interregional-routes-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="c53ff-110">Создание сетевой interregional маршрутов с помощью Скайп для консоли Business Server</span><span class="sxs-lookup"><span data-stu-id="c53ff-110">To create network interregional routes by using Skype for Business Server Management Shell</span></span>

1. <span data-ttu-id="c53ff-111">Запустите командную консоль Skype для бизнеса: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Skype для бизнеса 2015** и щелкните элемент **Командная консоль Skype для бизнеса**.</span><span class="sxs-lookup"><span data-stu-id="c53ff-111">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="c53ff-112">Выполните командлет **New-CsNetworkInterRegionRoute** , чтобы определить необходимые маршруты.</span><span class="sxs-lookup"><span data-stu-id="c53ff-112">Run the **New-CsNetworkInterRegionRoute** cmdlet to define the required routes.</span></span> <span data-ttu-id="c53ff-113">Например, выполните:</span><span class="sxs-lookup"><span data-stu-id="c53ff-113">For example, run:</span></span>
    
   ```
   New-CsNetworkInterRegionRoute -Identity NorthAmerica_EMEA_Route -NetworkRegionID1 NorthAmerica -NetworkRegionID2 EMEA -NetworkRegionLinkIDs "NA-EMEA-LINK"
   ```

   ```
   New-CsNetworkInterRegionRoute -Identity NorthAmerica_APAC_Route -NetworkRegionID1 NorthAmerica -NetworkRegionID2 APAC -NetworkRegionLinkIDs "NA-EMEA-LINK, EMEA-APAC-LINK"
   ```

   ```
   New-CsNetworkInterRegionRoute -Identity EMEA_APAC_Route -NetworkRegionID1 EMEA -NetworkRegionID2 APAC -NetworkRegionLinkIDs "EMEA-APAC-LINK"
   ```

    > [!NOTE]
    > <span data-ttu-id="c53ff-114">Для маршрута между регионами "Северная Америка/APAC" требуются две связи между регионами сети, поскольку прямая сетевая связь между этими регионами отсутствует.</span><span class="sxs-lookup"><span data-stu-id="c53ff-114">The North America/APAC network interregional route requires two network region links because there is no direct network region link between them.</span></span> 
  
### <a name="to-create-network-interregional-routes-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="c53ff-115">Создание сетевой interregional маршрутов с помощью Скайп для панели управления Business Server</span><span class="sxs-lookup"><span data-stu-id="c53ff-115">To create network interregional routes by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="c53ff-116">Откройте Скайп для панели управления Business Server.</span><span class="sxs-lookup"><span data-stu-id="c53ff-116">Open Skype for Business Server Control Panel.</span></span>
    
2. <span data-ttu-id="c53ff-117">В левой области навигации щелкните элемент **Конфигурация сети**.</span><span class="sxs-lookup"><span data-stu-id="c53ff-117">In the left navigation bar, click **Network Configuration**.</span></span>
    
3. <span data-ttu-id="c53ff-118">Щелкните кнопку навигации **Маршрут региона**.</span><span class="sxs-lookup"><span data-stu-id="c53ff-118">Click the **Region Route** navigation button.</span></span>
    
4. <span data-ttu-id="c53ff-119">Выберите **Создать**.</span><span class="sxs-lookup"><span data-stu-id="c53ff-119">Click **New**.</span></span>
    
5. <span data-ttu-id="c53ff-120">На странице **Новый маршрут региона** щелкните **Имя**, а затем введите имя для маршрута между регионами сети.</span><span class="sxs-lookup"><span data-stu-id="c53ff-120">On the **New Region Route** page, click **Name** and then type a name for the network interregional route.</span></span>
    
6. <span data-ttu-id="c53ff-121">Щелкните **Регион сети №1**, а затем выберите регион сети в списке, для которого нужно проложить маршрут к региону сети №2.</span><span class="sxs-lookup"><span data-stu-id="c53ff-121">Click **Network Region #1**, and then click a network region in the list that you want to route to Network Region #2.</span></span>
    
7. <span data-ttu-id="c53ff-122">Щелкните **Регион сети №2**, а затем выберите регион сети в списке, для которого нужно проложить маршрут к региону сети №2.</span><span class="sxs-lookup"><span data-stu-id="c53ff-122">Click **Network Region #2**, and then click a network region in the list that you want to route to Network Region #1.</span></span>
    
8. <span data-ttu-id="c53ff-123">Щелкните **Добавить** рядом с полем **Связи между регионами сети**, а затем добавьте связь с регионом сети, которая будет использоваться в маршруте между регионами сети.</span><span class="sxs-lookup"><span data-stu-id="c53ff-123">Click **Add** beside the **Network Region Links** field, and then add a network region link that will be used in the network interregional route.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="c53ff-p103">При создании маршрута между двумя регионами сети, между которыми отсутствует прямая связь, необходимо добавить все необходимые связи для создания полного маршрута. Например, для создания маршрута между регионами сети "Северная Америка" и "APAC" требуются две связи между сетевыми регионами, так как между ними отсутствует прямая связь.</span><span class="sxs-lookup"><span data-stu-id="c53ff-p103">If you are creating a route for two network regions that do not have a direct network region link between them, you must add all the necessary links to complete the route. For example, the North America/APAC network interregional route requires two network region links because there is no direct network region link between them.</span></span> 
  
9. <span data-ttu-id="c53ff-126">Нажмите **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="c53ff-126">Click **Commit**.</span></span>
    
10. <span data-ttu-id="c53ff-127">Чтобы завершить создание маршрутов между регионами сети, повторите шаги с 4 по 9 с указанием настроек для других маршрутов между сетевыми регионами.</span><span class="sxs-lookup"><span data-stu-id="c53ff-127">To finish creating network interregional routes for your topology, repeat steps 4 through 9 with settings for other network interregional routes.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="c53ff-128">См. также</span><span class="sxs-lookup"><span data-stu-id="c53ff-128">See also</span></span>

#### 

[<span data-ttu-id="c53ff-129">Новый CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="c53ff-129">New-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csnetworkinterregionroute?view=skype-ps)
  
[<span data-ttu-id="c53ff-130">Get-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="c53ff-130">Get-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csnetworkinterregionroute?view=skype-ps)
  
[<span data-ttu-id="c53ff-131">SET-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="c53ff-131">Set-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csnetworkinterregionroute?view=skype-ps)
  
[<span data-ttu-id="c53ff-132">Remove-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="c53ff-132">Remove-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csnetworkinterregionroute?view=skype-ps)

