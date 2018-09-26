---
title: Подключение пилотного пула к прежних версий пограничных серверов
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: После развертывания Скайп для Business Server 2019, необходимо настроить федеративный маршрут для вашего сайта. Перед использованием федеративного маршрута, используемый прежних версий установки, Скайп для Business Server 2019 должен быть настроен для использования этим маршрутом.
ms.openlocfilehash: 6766034cf54fd867c9b270324cb1db8ad2d644d5
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2018
ms.locfileid: "25030569"
---
# <a name="connect-pilot-pool-to-legacy-edge-servers"></a><span data-ttu-id="8a2b4-104">Подключение пилотного пула к прежних версий пограничных серверов</span><span class="sxs-lookup"><span data-stu-id="8a2b4-104">Connect pilot pool to legacy Edge Servers</span></span>

<span data-ttu-id="8a2b4-105">После развертывания Скайп для Business Server 2019, необходимо настроить федеративный маршрут для вашего сайта.</span><span class="sxs-lookup"><span data-stu-id="8a2b4-105">After deploying Skype for Business Server 2019, you need to configure a federation route for your site.</span></span> <span data-ttu-id="8a2b4-106">Перед использованием федеративного маршрута, используемый прежних версий установки, Скайп для Business Server 2019 должен быть настроен для использования этим маршрутом.</span><span class="sxs-lookup"><span data-stu-id="8a2b4-106">In order to use the federated route that is being used by the legacy installation, Skype for Business Server 2019 must be configured to use this route.</span></span> 
  
<span data-ttu-id="8a2b4-107">Чтобы включить Скайп Business Server 2019 сайта для использования директора и пограничного сервера устаревшее развертывание, сопоставление старого пограничного пула с помощью построителя топологии.</span><span class="sxs-lookup"><span data-stu-id="8a2b4-107">To enable the Skype for Business Server 2019 site to use the Director and Edge Server of the legacy deployment, use Topology Builder to associate the legacy Edge pool.</span></span>
  
### <a name="to-associate-the-legacy-edge-pool-by-using-topology-builder"></a><span data-ttu-id="8a2b4-108">Чтобы связать старого пограничного пула с помощью построителя топологий</span><span class="sxs-lookup"><span data-stu-id="8a2b4-108">To associate the legacy Edge pool by using Topology Builder</span></span>

1. <span data-ttu-id="8a2b4-109">Откройте построитель топологий.</span><span class="sxs-lookup"><span data-stu-id="8a2b4-109">Open Topology Builder.</span></span> 
    
2. <span data-ttu-id="8a2b4-110">Выберите сайт, который находится сразу под узел **Скайп для Business Server** .</span><span class="sxs-lookup"><span data-stu-id="8a2b4-110">Select your site, which is directly below the **Skype for Business Server** node.</span></span> 
    
3. <span data-ttu-id="8a2b4-111">В меню **действия** выберите команду **Изменить свойства**.</span><span class="sxs-lookup"><span data-stu-id="8a2b4-111">On the **Actions** menu, click **Edit Properties**.</span></span>
    
4. <span data-ttu-id="8a2b4-112">В левой области выберите **Федеративный маршрут**.</span><span class="sxs-lookup"><span data-stu-id="8a2b4-112">In the left pane, select **Federation route**.</span></span>
    
5. <span data-ttu-id="8a2b4-113">В разделе **Назначение федеративного маршрута сайта**выберите **Включить федерацию SIP**и выберите прежних версий директора или устаревшего пограничного сервера, если директор отсутствует в списке.</span><span class="sxs-lookup"><span data-stu-id="8a2b4-113">Under **Site federation route assignment**, select **Enable SIP federation**, and then select the legacy Director, or the legacy Edge Server if no Director is listed.</span></span>
  
6. <span data-ttu-id="8a2b4-114">Нажмите **кнопку ОК** , чтобы закрыть страницу **Изменения свойств** .</span><span class="sxs-lookup"><span data-stu-id="8a2b4-114">Click **OK** to close the **Edit Properties** page.</span></span> 
    
7. <span data-ttu-id="8a2b4-115">В построителе топологий, в разделе Скайп для узла Business Server 2019 перейдите на **сервере Standard Edition** или **Пулы переднего плана Enterprise Edition**, щелкните пул правой кнопкой мыши и выберите команду **Изменить свойства**.</span><span class="sxs-lookup"><span data-stu-id="8a2b4-115">In Topology Builder, under the Skype for Business Server 2019 node, navigate to the **Standard Edition server** or **Enterprise Edition Front End pools**, right-click the pool, and then click **Edit Properties**.</span></span>
    
8. <span data-ttu-id="8a2b4-116">В разделе **связи**установите флажок рядом с пунктом **сопоставить пограничный пул (для компонентов мультимедиа)**.</span><span class="sxs-lookup"><span data-stu-id="8a2b4-116">Under **Associations**, select the check box next to **Associate Edge pool (for media components)**.</span></span> 
    
9. <span data-ttu-id="8a2b4-117">В списке выберите устаревшего пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="8a2b4-117">From the list, select the legacy Edge Server.</span></span> 
  
10. <span data-ttu-id="8a2b4-118">Нажмите **кнопку ОК** , чтобы закрыть страницу **Изменения свойств** .</span><span class="sxs-lookup"><span data-stu-id="8a2b4-118">Click **OK** to close the **Edit Properties** page.</span></span> 
    
11. <span data-ttu-id="8a2b4-119">В **Построителе топологий**выберите узел верхнего уровня, **Скайп для Business Server**.</span><span class="sxs-lookup"><span data-stu-id="8a2b4-119">In **Topology Builder**, select the top-most node, **Skype for Business Server**.</span></span>
    
12. <span data-ttu-id="8a2b4-120">В меню **Действие** щелкните **Опубликовать топологию**и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="8a2b4-120">From the **Action** menu, click **Publish Topology**, and then click **Next**.</span></span>
    
13. <span data-ttu-id="8a2b4-121">После завершения работы **мастера публикации** , нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="8a2b4-121">When the **Publishing wizard** completes, click **Finish**.</span></span>
    

