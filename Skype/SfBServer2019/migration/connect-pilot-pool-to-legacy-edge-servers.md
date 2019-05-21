---
title: Подключение пилотного пула к старым пограничным серверам
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: После развертывания Skype для бизнеса Server 2019 необходимо настроить маршрут Федерации для вашего сайта. Чтобы использовать федеративный маршрут, который используется в устаревшем экземпляре, необходимо настроить Skype для Business Server 2019 на использование этого маршрута.
ms.openlocfilehash: 20aacda86c6c49b319859d6f1c175ce6258caddb
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34288630"
---
# <a name="connect-pilot-pool-to-legacy-edge-servers"></a><span data-ttu-id="d0aa9-104">Подключение пилотного пула к старым пограничным серверам</span><span class="sxs-lookup"><span data-stu-id="d0aa9-104">Connect pilot pool to legacy Edge Servers</span></span>

<span data-ttu-id="d0aa9-105">После развертывания Skype для бизнеса Server 2019 необходимо настроить маршрут Федерации для вашего сайта.</span><span class="sxs-lookup"><span data-stu-id="d0aa9-105">After deploying Skype for Business Server 2019, you need to configure a federation route for your site.</span></span> <span data-ttu-id="d0aa9-106">Чтобы использовать федеративный маршрут, который используется в устаревшем экземпляре, необходимо настроить Skype для Business Server 2019 на использование этого маршрута.</span><span class="sxs-lookup"><span data-stu-id="d0aa9-106">In order to use the federated route that is being used by the legacy installation, Skype for Business Server 2019 must be configured to use this route.</span></span> 
  
<span data-ttu-id="d0aa9-107">Чтобы на сайте Skype для бизнеса Server 2019 можно было использовать режиссер и Edge-сервер для развертывания устаревшего пула EDGE, используйте Topology Builder.</span><span class="sxs-lookup"><span data-stu-id="d0aa9-107">To enable the Skype for Business Server 2019 site to use the Director and Edge Server of the legacy deployment, use Topology Builder to associate the legacy Edge pool.</span></span>
  
### <a name="to-associate-the-legacy-edge-pool-by-using-topology-builder"></a><span data-ttu-id="d0aa9-108">Связывание устаревшего пула Edge с помощью построителя топологии</span><span class="sxs-lookup"><span data-stu-id="d0aa9-108">To associate the legacy Edge pool by using Topology Builder</span></span>

1. <span data-ttu-id="d0aa9-109">Открытие построителя топологии.</span><span class="sxs-lookup"><span data-stu-id="d0aa9-109">Open Topology Builder.</span></span> 
    
2. <span data-ttu-id="d0aa9-110">Выберите сайт, который находится непосредственно под узлом **Skype для бизнеса Server** .</span><span class="sxs-lookup"><span data-stu-id="d0aa9-110">Select your site, which is directly below the **Skype for Business Server** node.</span></span> 
    
3. <span data-ttu-id="d0aa9-111">В меню **действия** выберите команду **изменить свойства**.</span><span class="sxs-lookup"><span data-stu-id="d0aa9-111">On the **Actions** menu, click **Edit Properties**.</span></span>
    
4. <span data-ttu-id="d0aa9-112">На левой панели выберите **маршрут Федерации**.</span><span class="sxs-lookup"><span data-stu-id="d0aa9-112">In the left pane, select **Federation route**.</span></span>
    
5. <span data-ttu-id="d0aa9-113">В разделе **назначение маршрута Федерации сайтов**выберите **включить федерацию SIP**, а затем — режиссер старой версии или сервер старой версии, если в списке нет режиссера.</span><span class="sxs-lookup"><span data-stu-id="d0aa9-113">Under **Site federation route assignment**, select **Enable SIP federation**, and then select the legacy Director, or the legacy Edge Server if no Director is listed.</span></span>
  
6. <span data-ttu-id="d0aa9-114">Нажмите кнопку **ОК** , чтобы закрыть страницу **изменение свойств** .</span><span class="sxs-lookup"><span data-stu-id="d0aa9-114">Click **OK** to close the **Edit Properties** page.</span></span> 
    
7. <span data-ttu-id="d0aa9-115">В построителе топологии в разделе Skype для бизнеса Server 2019 перейдите к пулам **сервер стандартных** выпусков или **корпоративным интерфейсом Enterprise Edition**, щелкните пул правой кнопкой мыши и выберите команду **изменить свойства**.</span><span class="sxs-lookup"><span data-stu-id="d0aa9-115">In Topology Builder, under the Skype for Business Server 2019 node, navigate to the **Standard Edition server** or **Enterprise Edition Front End pools**, right-click the pool, and then click **Edit Properties**.</span></span>
    
8. <span data-ttu-id="d0aa9-116">В разделе **связи**установите флажок **связать пул граничного пула (для компонентов мультимедиа)**.</span><span class="sxs-lookup"><span data-stu-id="d0aa9-116">Under **Associations**, select the check box next to **Associate Edge pool (for media components)**.</span></span> 
    
9. <span data-ttu-id="d0aa9-117">Выберите в списке старый сервер пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="d0aa9-117">From the list, select the legacy Edge Server.</span></span> 
  
10. <span data-ttu-id="d0aa9-118">Нажмите кнопку **ОК** , чтобы закрыть страницу **изменение свойств** .</span><span class="sxs-lookup"><span data-stu-id="d0aa9-118">Click **OK** to close the **Edit Properties** page.</span></span> 
    
11. <span data-ttu-id="d0aa9-119">В **построителе топологии**выберите самый верхний узел, **Skype для бизнеса Server**.</span><span class="sxs-lookup"><span data-stu-id="d0aa9-119">In **Topology Builder**, select the top-most node, **Skype for Business Server**.</span></span>
    
12. <span data-ttu-id="d0aa9-120">В меню **действие** выберите пункт **топология публикации**и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="d0aa9-120">From the **Action** menu, click **Publish Topology**, and then click **Next**.</span></span>
    
13. <span data-ttu-id="d0aa9-121">После завершения работы **мастера публикации** нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="d0aa9-121">When the **Publishing wizard** completes, click **Finish**.</span></span>
    

