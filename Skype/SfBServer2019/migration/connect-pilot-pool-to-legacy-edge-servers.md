---
title: Подключение пилотного пула к старым пограничным серверам
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: После развертывания Skype для бизнеса Server 2019 необходимо настроить маршрут Федерации для вашего сайта. Чтобы использовать федеративный маршрут, который используется в устаревшем экземпляре, необходимо настроить Skype для Business Server 2019 на использование этого маршрута.
ms.openlocfilehash: 6cc49da3cb27679ef295c7bbeca122aea5a89d10
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813707"
---
# <a name="connect-pilot-pool-to-legacy-edge-servers"></a><span data-ttu-id="d7d8e-104">Подключение пилотного пула к старым пограничным серверам</span><span class="sxs-lookup"><span data-stu-id="d7d8e-104">Connect pilot pool to legacy Edge Servers</span></span>

<span data-ttu-id="d7d8e-105">После развертывания Skype для бизнеса Server 2019 необходимо настроить маршрут Федерации для вашего сайта.</span><span class="sxs-lookup"><span data-stu-id="d7d8e-105">After deploying Skype for Business Server 2019, you need to configure a federation route for your site.</span></span> <span data-ttu-id="d7d8e-106">Чтобы использовать федеративный маршрут, который используется в устаревшем экземпляре, необходимо настроить Skype для Business Server 2019 на использование этого маршрута.</span><span class="sxs-lookup"><span data-stu-id="d7d8e-106">In order to use the federated route that is being used by the legacy installation, Skype for Business Server 2019 must be configured to use this route.</span></span> 
  
<span data-ttu-id="d7d8e-107">Чтобы на сайте Skype для бизнеса Server 2019 можно было использовать режиссер и Edge-сервер для развертывания устаревшего пула EDGE, используйте Topology Builder.</span><span class="sxs-lookup"><span data-stu-id="d7d8e-107">To enable the Skype for Business Server 2019 site to use the Director and Edge Server of the legacy deployment, use Topology Builder to associate the legacy Edge pool.</span></span>
  
### <a name="to-associate-the-legacy-edge-pool-by-using-topology-builder"></a><span data-ttu-id="d7d8e-108">Связывание устаревшего пула Edge с помощью построителя топологии</span><span class="sxs-lookup"><span data-stu-id="d7d8e-108">To associate the legacy Edge pool by using Topology Builder</span></span>

1. <span data-ttu-id="d7d8e-109">Открытие построителя топологии.</span><span class="sxs-lookup"><span data-stu-id="d7d8e-109">Open Topology Builder.</span></span> 
    
2. <span data-ttu-id="d7d8e-110">Выберите сайт, который находится непосредственно под узлом **Skype для бизнеса Server** .</span><span class="sxs-lookup"><span data-stu-id="d7d8e-110">Select your site, which is directly below the **Skype for Business Server** node.</span></span> 
    
3. <span data-ttu-id="d7d8e-111">В меню **действия** выберите команду **изменить свойства**.</span><span class="sxs-lookup"><span data-stu-id="d7d8e-111">On the **Actions** menu, click **Edit Properties**.</span></span>
    
4. <span data-ttu-id="d7d8e-112">На левой панели выберите **маршрут Федерации**.</span><span class="sxs-lookup"><span data-stu-id="d7d8e-112">In the left pane, select **Federation route**.</span></span>
    
5. <span data-ttu-id="d7d8e-113">В разделе **назначение маршрута Федерации сайтов**выберите **включить федерацию SIP**, а затем — режиссер старой версии или сервер старой версии, если в списке нет режиссера.</span><span class="sxs-lookup"><span data-stu-id="d7d8e-113">Under **Site federation route assignment**, select **Enable SIP federation**, and then select the legacy Director, or the legacy Edge Server if no Director is listed.</span></span>
  
6. <span data-ttu-id="d7d8e-114">Нажмите кнопку **ОК** , чтобы закрыть страницу **изменение свойств** .</span><span class="sxs-lookup"><span data-stu-id="d7d8e-114">Click **OK** to close the **Edit Properties** page.</span></span> 
    
7. <span data-ttu-id="d7d8e-115">В построителе топологии в разделе Skype для бизнеса Server 2019 перейдите к пулам **сервер стандартных выпусков** или **корпоративным интерфейсом Enterprise Edition**, щелкните пул правой кнопкой мыши и выберите команду **изменить свойства**.</span><span class="sxs-lookup"><span data-stu-id="d7d8e-115">In Topology Builder, under the Skype for Business Server 2019 node, navigate to the **Standard Edition server** or **Enterprise Edition Front End pools**, right-click the pool, and then click **Edit Properties**.</span></span>
    
8. <span data-ttu-id="d7d8e-116">В разделе **связи**установите флажок **связать пул граничного пула (для компонентов мультимедиа)**.</span><span class="sxs-lookup"><span data-stu-id="d7d8e-116">Under **Associations**, select the check box next to **Associate Edge pool (for media components)**.</span></span> 
    
9. <span data-ttu-id="d7d8e-117">Выберите в списке старый сервер пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="d7d8e-117">From the list, select the legacy Edge Server.</span></span> 
  
10. <span data-ttu-id="d7d8e-118">Нажмите кнопку **ОК** , чтобы закрыть страницу **изменение свойств** .</span><span class="sxs-lookup"><span data-stu-id="d7d8e-118">Click **OK** to close the **Edit Properties** page.</span></span> 
    
11. <span data-ttu-id="d7d8e-119">В **построителе топологии**выберите самый верхний узел, **Skype для бизнеса Server**.</span><span class="sxs-lookup"><span data-stu-id="d7d8e-119">In **Topology Builder**, select the top-most node, **Skype for Business Server**.</span></span>
    
12. <span data-ttu-id="d7d8e-120">В меню **действие** выберите пункт **топология публикации**и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="d7d8e-120">From the **Action** menu, click **Publish Topology**, and then click **Next**.</span></span>
    
13. <span data-ttu-id="d7d8e-121">После завершения работы **мастера публикации** нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="d7d8e-121">When the **Publishing wizard** completes, click **Finish**.</span></span>
    

