---
title: Создание межрегиональных сетевых маршрутов в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 5555262a-a502-4b01-9593-836dd30064f5
description: Создание или изменение межрегиональных сетевых маршрутов, которые используются Корпоративная голосовая связь контроля допуска звонков в Skype для бизнеса Server.
ms.openlocfilehash: 86b7cf9e41cb20d82f0c3c6edd6bcbd74331d553
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49822499"
---
# <a name="create-network-interregional-routes-in-skype-for-business-server"></a><span data-ttu-id="a3a13-103">Создание межрегиональных сетевых маршрутов в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="a3a13-103">Create network interregional routes in Skype for Business Server</span></span>
 
<span data-ttu-id="a3a13-104">Создание или изменение межрегиональных сетевых маршрутов, которые используются Корпоративная голосовая связь контроля допуска звонков в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="a3a13-104">Create or modify network interregional routes, which are used by Enterprise Voice call admission control in Skype for Business Server.</span></span> 
  
<span data-ttu-id="a3a13-105">Межрегиональный сетевой маршрут определяет маршрут между двумя областями сети.</span><span class="sxs-lookup"><span data-stu-id="a3a13-105">A network interregional route defines the route between a pair of network regions.</span></span> <span data-ttu-id="a3a13-106">Для каждой пары регионов сети в развертывании контроля допуска вызовов требуется межрегиональный сетевой маршрут.</span><span class="sxs-lookup"><span data-stu-id="a3a13-106">Each pair of network regions in your call admission control deployment requires a network interregional route.</span></span> <span data-ttu-id="a3a13-107">Благодаря этому каждая область сети в рамках развертывания может получить доступ к каждой другой области.</span><span class="sxs-lookup"><span data-stu-id="a3a13-107">This enables every network region within the deployment to access every other region.</span></span>
  
<span data-ttu-id="a3a13-108">Хотя связи между областями устанавливают ограничения пропускной способности для подключений между регионами, межрегиональный маршрут определяет, какой связанный путь будет проходить соединение между областями.</span><span class="sxs-lookup"><span data-stu-id="a3a13-108">While region links set bandwidth limitations on the connections between regions, an interregional route determines which linked path the connection will traverse from one region to another.</span></span>
  
<span data-ttu-id="a3a13-109">В примере топологии необходимо определить межрегиональные сетевые маршруты для каждой из трех пар регионов: Северная Америка/EMEA, EMEA/APAC и Северная Америка/APAC.</span><span class="sxs-lookup"><span data-stu-id="a3a13-109">In the example topology, network interregional routes must be defined for each of the three region pairs: North America/EMEA, EMEA/APAC, and North America/APAC.</span></span> 
  
### <a name="to-create-network-interregional-routes-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="a3a13-110">Создание межрегиональных сетевых маршрутов с помощью skype для бизнеса Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="a3a13-110">To create network interregional routes by using Skype for Business Server Management Shell</span></span>

1. <span data-ttu-id="a3a13-111">Запустите оболочку управления Skype для бизнеса Server: нажмите кнопку "Начните", выберите "Все программы", "Skype для бизнеса **2015",** а затем щелкните "Skype для бизнеса Server Management **Shell".**</span><span class="sxs-lookup"><span data-stu-id="a3a13-111">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="a3a13-112">Выполните командлет **New-CsNetworkInterRegionRoute**, чтобы определить необходимые маршруты.</span><span class="sxs-lookup"><span data-stu-id="a3a13-112">Run the **New-CsNetworkInterRegionRoute** cmdlet to define the required routes.</span></span> <span data-ttu-id="a3a13-113">Например, выполните команду:</span><span class="sxs-lookup"><span data-stu-id="a3a13-113">For example, run:</span></span>
    
   ```powershell
   New-CsNetworkInterRegionRoute -Identity NorthAmerica_EMEA_Route -NetworkRegionID1 NorthAmerica -NetworkRegionID2 EMEA -NetworkRegionLinkIDs "NA-EMEA-LINK"
   ```

   ```powershell
   New-CsNetworkInterRegionRoute -Identity NorthAmerica_APAC_Route -NetworkRegionID1 NorthAmerica -NetworkRegionID2 APAC -NetworkRegionLinkIDs "NA-EMEA-LINK, EMEA-APAC-LINK"
   ```

   ```powershell
   New-CsNetworkInterRegionRoute -Identity EMEA_APAC_Route -NetworkRegionID1 EMEA -NetworkRegionID2 APAC -NetworkRegionLinkIDs "EMEA-APAC-LINK"
   ```

    > [!NOTE]
    > <span data-ttu-id="a3a13-114">Межрегиональный сетевой маршрут "Северная Америка/ APAC" требует двух связей между областями сети, так как между ними нет прямой связи между областями сети.</span><span class="sxs-lookup"><span data-stu-id="a3a13-114">The North America/APAC network interregional route requires two network region links because there is no direct network region link between them.</span></span> 
  
### <a name="to-create-network-interregional-routes-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="a3a13-115">Создание межрегиональных сетевых маршрутов с помощью панели управления Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="a3a13-115">To create network interregional routes by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="a3a13-116">Откройте панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="a3a13-116">Open Skype for Business Server Control Panel.</span></span>
    
2. <span data-ttu-id="a3a13-117">На левой панели навигации щелкните **Конфигурация сети**.</span><span class="sxs-lookup"><span data-stu-id="a3a13-117">In the left navigation bar, click **Network Configuration**.</span></span>
    
3. <span data-ttu-id="a3a13-118">Щелкните кнопку навигации **Маршрут региона**.</span><span class="sxs-lookup"><span data-stu-id="a3a13-118">Click the **Region Route** navigation button.</span></span>
    
4. <span data-ttu-id="a3a13-119">Щелкните **Создать**.</span><span class="sxs-lookup"><span data-stu-id="a3a13-119">Click **New**.</span></span>
    
5. <span data-ttu-id="a3a13-120">На странице **"Новый маршрут области"** щелкните **"Имя",** а затем введите имя для межрегионального сетевого маршрута.</span><span class="sxs-lookup"><span data-stu-id="a3a13-120">On the **New Region Route** page, click **Name** and then type a name for the network interregional route.</span></span>
    
6. <span data-ttu-id="a3a13-121">Щелкните **Регион сети №1**, а затем выберите регион сети в списке, для которого нужно проложить маршрут к региону сети №2.</span><span class="sxs-lookup"><span data-stu-id="a3a13-121">Click **Network Region #1**, and then click a network region in the list that you want to route to Network Region #2.</span></span>
    
7. <span data-ttu-id="a3a13-122">Щелкните **Регион сети №2**, а затем выберите регион сети в списке, для которого нужно проложить маршрут к региону сети №1.</span><span class="sxs-lookup"><span data-stu-id="a3a13-122">Click **Network Region #2**, and then click a network region in the list that you want to route to Network Region #1.</span></span>
    
8. <span data-ttu-id="a3a13-123">Нажмите **кнопку** "Добавить" рядом с полем "Связи между областями сети", а затем добавьте связь между регионами сети, которая будет использоваться в маршруте между регионами сети. </span><span class="sxs-lookup"><span data-stu-id="a3a13-123">Click **Add** beside the **Network Region Links** field, and then add a network region link that will be used in the network interregional route.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="a3a13-124">При создании маршрута между двумя регионами сети, между которыми отсутствует прямая связь, необходимо добавить все необходимые связи для создания полного маршрута.</span><span class="sxs-lookup"><span data-stu-id="a3a13-124">If you are creating a route for two network regions that do not have a direct network region link between them, you must add all the necessary links to complete the route.</span></span> <span data-ttu-id="a3a13-125">Например, для межрегионального маршрута сети "Северная Америка" или APAC требуются две связи между областями сети, так как между ними нет прямой связи между областями сети.</span><span class="sxs-lookup"><span data-stu-id="a3a13-125">For example, the North America/APAC network interregional route requires two network region links because there is no direct network region link between them.</span></span> 
  
9. <span data-ttu-id="a3a13-126">Щелкните **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="a3a13-126">Click **Commit**.</span></span>
    
10. <span data-ttu-id="a3a13-127">Чтобы завершить создание межрегиональных сетевых маршрутов для топологии, повторите шаги с 4 по 9 с настройками для других межрегиональных сетевых маршрутов.</span><span class="sxs-lookup"><span data-stu-id="a3a13-127">To finish creating network interregional routes for your topology, repeat steps 4 through 9 with settings for other network interregional routes.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="a3a13-128">См. также</span><span class="sxs-lookup"><span data-stu-id="a3a13-128">See also</span></span>

[<span data-ttu-id="a3a13-129">New-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="a3a13-129">New-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csnetworkinterregionroute?view=skype-ps)
  
[<span data-ttu-id="a3a13-130">Get-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="a3a13-130">Get-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csnetworkinterregionroute?view=skype-ps)
  
[<span data-ttu-id="a3a13-131">Set-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="a3a13-131">Set-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csnetworkinterregionroute?view=skype-ps)
  
[<span data-ttu-id="a3a13-132">Remove-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="a3a13-132">Remove-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csnetworkinterregionroute?view=skype-ps)
