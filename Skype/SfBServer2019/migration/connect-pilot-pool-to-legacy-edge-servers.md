---
title: Подключение пилотного пула к старым пограничным серверам
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: После развертывания Skype для бизнеса Server 2019 необходимо настроить маршрут Федерации для сайта. Чтобы использовать федеративный маршрут, который используется устаревшей установкой, необходимо настроить Skype для бизнеса Server 2019 для использования этого маршрута.
ms.openlocfilehash: 8243ebbf9540587dedd8e4ae3a51e22f9a315728
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/16/2020
ms.locfileid: "44753929"
---
# <a name="connect-pilot-pool-to-legacy-edge-servers"></a><span data-ttu-id="774ea-104">Подключение пилотного пула к старым пограничным серверам</span><span class="sxs-lookup"><span data-stu-id="774ea-104">Connect pilot pool to legacy Edge Servers</span></span>

<span data-ttu-id="774ea-105">После развертывания Skype для бизнеса Server 2019 необходимо настроить маршрут Федерации для сайта.</span><span class="sxs-lookup"><span data-stu-id="774ea-105">After deploying Skype for Business Server 2019, you need to configure a federation route for your site.</span></span> <span data-ttu-id="774ea-106">Чтобы использовать федеративный маршрут, который используется устаревшей установкой, необходимо настроить Skype для бизнеса Server 2019 для использования этого маршрута.</span><span class="sxs-lookup"><span data-stu-id="774ea-106">In order to use the federated route that is being used by the legacy installation, Skype for Business Server 2019 must be configured to use this route.</span></span> 
  
<span data-ttu-id="774ea-107">Чтобы разрешить сайту Skype для бизнеса Server 2019 использовать директор и пограничный сервер развертывания прежних версий, используйте построитель топологий для связи устаревшего пограничного пула.</span><span class="sxs-lookup"><span data-stu-id="774ea-107">To enable the Skype for Business Server 2019 site to use the Director and Edge Server of the legacy deployment, use Topology Builder to associate the legacy Edge pool.</span></span>
  
### <a name="to-associate-the-legacy-edge-pool-by-using-topology-builder"></a><span data-ttu-id="774ea-108">Связь устаревшего пограничного пула с помощью построителя топологий</span><span class="sxs-lookup"><span data-stu-id="774ea-108">To associate the legacy Edge pool by using Topology Builder</span></span>

1. <span data-ttu-id="774ea-109">Откройте построитель топологий.</span><span class="sxs-lookup"><span data-stu-id="774ea-109">Open Topology Builder.</span></span> 
    
2. <span data-ttu-id="774ea-110">Выберите сайт, который находится непосредственно под узлом **Skype для бизнеса Server** .</span><span class="sxs-lookup"><span data-stu-id="774ea-110">Select your site, which is directly below the **Skype for Business Server** node.</span></span> 
    
3. <span data-ttu-id="774ea-111">В меню **Actions** (Действия) выберите команду **Изменить свойства**.</span><span class="sxs-lookup"><span data-stu-id="774ea-111">On the **Actions** menu, click **Edit Properties**.</span></span>
    
4. <span data-ttu-id="774ea-112">В левой области выберите **Федеративный маршрут**.</span><span class="sxs-lookup"><span data-stu-id="774ea-112">In the left pane, select **Federation route**.</span></span>
    
5. <span data-ttu-id="774ea-113">В разделе **назначение федеративного маршрута сайта**выберите **включить федерацию SIP**, а затем выберите директор прежних версий или пограничный сервер прежних версий (если в списке нет директоров).</span><span class="sxs-lookup"><span data-stu-id="774ea-113">Under **Site federation route assignment**, select **Enable SIP federation**, and then select the legacy Director, or the legacy Edge Server if no Director is listed.</span></span>
  
6. <span data-ttu-id="774ea-114">Нажмите кнопку **ОК**, чтобы закрыть страницу **изменения свойств**.</span><span class="sxs-lookup"><span data-stu-id="774ea-114">Click **OK** to close the **Edit Properties** page.</span></span> 
    
7. <span data-ttu-id="774ea-115">В построителе топологий в узле Skype для бизнеса Server 2019 перейдите к **интерфейсным пулам** **Standard Edition Server** или Enterprise Edition, щелкните пул правой кнопкой мыши и выберите команду **изменить свойства**.</span><span class="sxs-lookup"><span data-stu-id="774ea-115">In Topology Builder, under the Skype for Business Server 2019 node, navigate to the **Standard Edition server** or **Enterprise Edition Front End pools**, right-click the pool, and then click **Edit Properties**.</span></span>
    
8. <span data-ttu-id="774ea-116">В разделе **Associations** (Связи) установите флажок **Associate Edge pool (for media components)** (Связать пограничный пул (для компонентов медиа)).</span><span class="sxs-lookup"><span data-stu-id="774ea-116">Under **Associations**, select the check box next to **Associate Edge pool (for media components)**.</span></span> 
    
9. <span data-ttu-id="774ea-117">Выберите в списке устаревший пограничный сервер.</span><span class="sxs-lookup"><span data-stu-id="774ea-117">From the list, select the legacy Edge Server.</span></span> 
  
10. <span data-ttu-id="774ea-118">Нажмите кнопку **ОК**, чтобы закрыть страницу **изменения свойств**.</span><span class="sxs-lookup"><span data-stu-id="774ea-118">Click **OK** to close the **Edit Properties** page.</span></span> 
    
11. <span data-ttu-id="774ea-119">В **построителе топологий**выберите самый верхний узел, **Skype для бизнеса Server**.</span><span class="sxs-lookup"><span data-stu-id="774ea-119">In **Topology Builder**, select the top-most node, **Skype for Business Server**.</span></span>
    
12. <span data-ttu-id="774ea-120">В меню **Action** (Действие) выберите команду **Publish Topology** (Опубликовать топологию) и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="774ea-120">From the **Action** menu, click **Publish Topology**, and then click **Next**.</span></span>
    
13. <span data-ttu-id="774ea-121">Когда **мастер публикации** завершит работу, нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="774ea-121">When the **Publishing wizard** completes, click **Finish**.</span></span>
    

