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
description: After deploying Skype for Business Server 2019, you need to configure a federation route for your site. Чтобы использовать федераированный маршрут, используемый устаревшей установкой, необходимо настроить Skype для бизнеса Server 2019 на использование этого маршрута.
ms.openlocfilehash: 8243ebbf9540587dedd8e4ae3a51e22f9a315728
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/16/2020
ms.locfileid: "44753929"
---
# <a name="connect-pilot-pool-to-legacy-edge-servers"></a><span data-ttu-id="6307c-104">Подключение пилотного пула к старым пограничным серверам</span><span class="sxs-lookup"><span data-stu-id="6307c-104">Connect pilot pool to legacy Edge Servers</span></span>

<span data-ttu-id="6307c-105">After deploying Skype for Business Server 2019, you need to configure a federation route for your site.</span><span class="sxs-lookup"><span data-stu-id="6307c-105">After deploying Skype for Business Server 2019, you need to configure a federation route for your site.</span></span> <span data-ttu-id="6307c-106">Чтобы использовать федераированный маршрут, используемый устаревшей установкой, необходимо настроить Skype для бизнеса Server 2019 на использование этого маршрута.</span><span class="sxs-lookup"><span data-stu-id="6307c-106">In order to use the federated route that is being used by the legacy installation, Skype for Business Server 2019 must be configured to use this route.</span></span> 
  
<span data-ttu-id="6307c-107">Чтобы позволить сайту Skype для бизнеса Server 2019 использовать директор и edge-сервер устаревшего развертывания, используйте построитель топологий для связывание устаревшего пула.</span><span class="sxs-lookup"><span data-stu-id="6307c-107">To enable the Skype for Business Server 2019 site to use the Director and Edge Server of the legacy deployment, use Topology Builder to associate the legacy Edge pool.</span></span>
  
### <a name="to-associate-the-legacy-edge-pool-by-using-topology-builder"></a><span data-ttu-id="6307c-108">Связь устаревшего пограничного пула с помощью построителя топологий</span><span class="sxs-lookup"><span data-stu-id="6307c-108">To associate the legacy Edge pool by using Topology Builder</span></span>

1. <span data-ttu-id="6307c-109">Откройте построитель топологий.</span><span class="sxs-lookup"><span data-stu-id="6307c-109">Open Topology Builder.</span></span> 
    
2. <span data-ttu-id="6307c-110">Выберите свой сайт, который находится непосредственно под узлом **Skype для бизнеса Server.**</span><span class="sxs-lookup"><span data-stu-id="6307c-110">Select your site, which is directly below the **Skype for Business Server** node.</span></span> 
    
3. <span data-ttu-id="6307c-111">В меню **Actions** (Действия) выберите команду **Изменить свойства**.</span><span class="sxs-lookup"><span data-stu-id="6307c-111">On the **Actions** menu, click **Edit Properties**.</span></span>
    
4. <span data-ttu-id="6307c-112">В левой области выберите **Федеративный маршрут**.</span><span class="sxs-lookup"><span data-stu-id="6307c-112">In the left pane, select **Federation route**.</span></span>
    
5. <span data-ttu-id="6307c-113">В **области назначения маршрута** федерации сайта выберите "Включить **федерацию SIP",** а затем выберите устаревший директор или устаревший сервер, если директор не указан.</span><span class="sxs-lookup"><span data-stu-id="6307c-113">Under **Site federation route assignment**, select **Enable SIP federation**, and then select the legacy Director, or the legacy Edge Server if no Director is listed.</span></span>
  
6. <span data-ttu-id="6307c-114">Нажмите кнопку **ОК**, чтобы закрыть страницу **изменения свойств**.</span><span class="sxs-lookup"><span data-stu-id="6307c-114">Click **OK** to close the **Edit Properties** page.</span></span> 
    
7. <span data-ttu-id="6307c-115">In Topology Builder, under the Skype for Business Server 2019 node, navigate to the **Standard Edition server** or Enterprise Edition Front End **pools,** right-click the pool, and then click **Edit Properties**.</span><span class="sxs-lookup"><span data-stu-id="6307c-115">In Topology Builder, under the Skype for Business Server 2019 node, navigate to the **Standard Edition server** or **Enterprise Edition Front End pools**, right-click the pool, and then click **Edit Properties**.</span></span>
    
8. <span data-ttu-id="6307c-116">В разделе **Associations** (Связи) установите флажок **Associate Edge pool (for media components)** (Связать пограничный пул (для компонентов медиа)).</span><span class="sxs-lookup"><span data-stu-id="6307c-116">Under **Associations**, select the check box next to **Associate Edge pool (for media components)**.</span></span> 
    
9. <span data-ttu-id="6307c-117">Выберите в списке устаревший пограничный сервер.</span><span class="sxs-lookup"><span data-stu-id="6307c-117">From the list, select the legacy Edge Server.</span></span> 
  
10. <span data-ttu-id="6307c-118">Нажмите кнопку **ОК**, чтобы закрыть страницу **изменения свойств**.</span><span class="sxs-lookup"><span data-stu-id="6307c-118">Click **OK** to close the **Edit Properties** page.</span></span> 
    
11. <span data-ttu-id="6307c-119">In **Topology Builder**, select the top-most node, **Skype for Business Server**.</span><span class="sxs-lookup"><span data-stu-id="6307c-119">In **Topology Builder**, select the top-most node, **Skype for Business Server**.</span></span>
    
12. <span data-ttu-id="6307c-120">В меню **Action** (Действие) выберите команду **Publish Topology** (Опубликовать топологию) и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="6307c-120">From the **Action** menu, click **Publish Topology**, and then click **Next**.</span></span>
    
13. <span data-ttu-id="6307c-121">Когда **мастер публикации** завершит работу, нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="6307c-121">When the **Publishing wizard** completes, click **Finish**.</span></span>
    

