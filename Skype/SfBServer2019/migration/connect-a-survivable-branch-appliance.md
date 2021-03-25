---
title: Подключение Survivable Branch Appliance
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
description: Каждый остающийся в живых прибор филиала (SBA) связан с пулом переднего конца, который служит резервным регистратором для SBA. При переносе пула переднего конца в Skype для бизнеса Server 2019 SBA необходимо отсоединяя от пула переднего конца при обновлении пула. После переноса пула в Skype для бизнеса Server 2019 SBA может быть повторно связан с обновленным пулом переднего конца. Это включает удаление SBA из устаревшей топологии в Topology Builder и добавление SBA в топологию Skype для бизнеса Server 2019. Пользователи, уехав на устаревшую SBA, сначала должны быть перемещены в другой пул переднего конца, а затем удалить SBA из топологии. После того как SBA будет добавлена в топологию Skype для бизнеса Server 2019, эти пользователи могут быть перемещены обратно в SBA. Эти действия приведены ниже.
ms.openlocfilehash: e56bae1631a315b6f42042fb6a7bedd4f144a1b6
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51113345"
---
# <a name="connect-a-survivable-branch-appliance"></a><span data-ttu-id="ee3ff-108">Подключение Survivable Branch Appliance</span><span class="sxs-lookup"><span data-stu-id="ee3ff-108">Connect a Survivable Branch Appliance</span></span>

<span data-ttu-id="ee3ff-109">Каждый остающийся в живых устройство филиала (SBA) связан с пулом переднего конца, который служит резервным регистратором для SBA.</span><span class="sxs-lookup"><span data-stu-id="ee3ff-109">Every Survivable Branch Appliance (SBA) is associated with a Front End pool that serves as a backup registrar for the SBA.</span></span> <span data-ttu-id="ee3ff-110">При переносе пула переднего конца в Skype для бизнеса Server 2019 SBA необходимо отсоединяя от пула переднего конца при обновлении пула.</span><span class="sxs-lookup"><span data-stu-id="ee3ff-110">When the Front End pool is migrated to Skype for Business Server 2019, the SBA must be disassociated from the Front End pool while the pool is upgraded.</span></span> <span data-ttu-id="ee3ff-111">После переноса пула в Skype для бизнеса Server 2019 SBA может быть повторно связан с обновленным пулом переднего конца.</span><span class="sxs-lookup"><span data-stu-id="ee3ff-111">After the pool has been migrated to Skype for Business Server 2019, the SBA can be re-associated with the upgraded Front End pool.</span></span> <span data-ttu-id="ee3ff-112">Это включает удаление SBA из устаревшей топологии в Topology Builder и добавление SBA в топологию Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="ee3ff-112">This involves deleting the SBA from the legacy topology in Topology Builder and then adding the SBA to the Skype for Business Server 2019 topology.</span></span> <span data-ttu-id="ee3ff-113">Пользователи, уехав на устаревшую SBA, сначала должны быть перемещены в другой пул переднего конца, а затем удалить SBA из топологии.</span><span class="sxs-lookup"><span data-stu-id="ee3ff-113">Users homed on the legacy SBA must first be moved to another Front End pool before removing the SBA from the topology.</span></span> <span data-ttu-id="ee3ff-114">После того как SBA будет добавлена в топологию Skype для бизнеса Server 2019, эти пользователи могут быть перемещены обратно в SBA.</span><span class="sxs-lookup"><span data-stu-id="ee3ff-114">After the SBA is added to the Skype for Business Server 2019 topology, those users can be moved back to the SBA.</span></span> <span data-ttu-id="ee3ff-115">Эти действия приведены ниже.</span><span class="sxs-lookup"><span data-stu-id="ee3ff-115">These steps are summarized below:</span></span>
  
1. <span data-ttu-id="ee3ff-116">Перемещение пользователей филиалов, которые были в устаревшем SBA, в другой пул переднего конца.</span><span class="sxs-lookup"><span data-stu-id="ee3ff-116">Move branch users homed on the legacy SBA to another Front End pool.</span></span>
    
2. <span data-ttu-id="ee3ff-117">Удалите SBA из устаревшей топологии, чтобы отключить существующий пул переднего конца в качестве резервного регистратора.</span><span class="sxs-lookup"><span data-stu-id="ee3ff-117">Remove SBA from the legacy topology to disconnect the existing Front End pool as a backup registrar.</span></span>
    
3. <span data-ttu-id="ee3ff-118">Добавьте SBA в топологию Skype для бизнеса Server 2019 и настройте этот новый пул переднего конца в качестве регистратора резервного копирования.</span><span class="sxs-lookup"><span data-stu-id="ee3ff-118">Add SBA to the Skype for Business Server 2019 topology and configure this new Front End pool as the backup registrar.</span></span> 
    
4. <span data-ttu-id="ee3ff-119">Перемещение пользователей филиала в новую SBA Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="ee3ff-119">Move the branch users to the new Skype for Business Server 2019 SBA.</span></span>
    
### <a name="add-legacy-sba-branch-site-to-your-topology"></a><span data-ttu-id="ee3ff-120">Добавление устаревшего сайта филиала SBA в топологию</span><span class="sxs-lookup"><span data-stu-id="ee3ff-120">Add legacy SBA branch site to your topology</span></span>

1. <span data-ttu-id="ee3ff-121">Откройте **построитель топологий**.</span><span class="sxs-lookup"><span data-stu-id="ee3ff-121">Open **Topology Builder**.</span></span>
    
2. <span data-ttu-id="ee3ff-122">В левой области щелкните правой кнопкой мыши **Ветви** сайты, а затем нажмите **кнопку New Branch Site**.</span><span class="sxs-lookup"><span data-stu-id="ee3ff-122">In the left pane, right-click **Branch sites**, and then click **New Branch Site**.</span></span>
    
3. <span data-ttu-id="ee3ff-123">В диалоговом окне **Определение нового сайта филиала для сайта** щелкните элемент **Имя**, а затем введите имя сайта филиала.</span><span class="sxs-lookup"><span data-stu-id="ee3ff-123">In the **Define New Branch Site** dialog box, click **Name**, and then type the name of the branch site.</span></span>
    
4. <span data-ttu-id="ee3ff-124">(Необязательно) Щелкните элемент **Описание**, а затем введите содержательное описание для сайта филиала.</span><span class="sxs-lookup"><span data-stu-id="ee3ff-124">(Optional) Click **Description**, and then type a meaningful description for the branch site.</span></span>
    
5. <span data-ttu-id="ee3ff-125">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="ee3ff-125">Click **Next**.</span></span>
    
6. <span data-ttu-id="ee3ff-126">(Необязательно) В следующем диалоговом окне **Определение нового сайта филиала для сайта** выполните любое из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="ee3ff-126">(Optional) In the next **Define New Branch Site** dialog box, do any of the following:</span></span> 
    
    1. <span data-ttu-id="ee3ff-127">Щелкните элемент **Город**, а затем введите название города, в котором расположен сайт филиала.</span><span class="sxs-lookup"><span data-stu-id="ee3ff-127">Click **City**, and then type the name of the city in which the branch site is located.</span></span>
    
    2. <span data-ttu-id="ee3ff-128">Щелкните элемент **Регион**, а затем введите название региона или области, где расположен сайт филиала.</span><span class="sxs-lookup"><span data-stu-id="ee3ff-128">Click **State/Region**, and then type the name of the state or region in which the branch site is located.</span></span>
    
    3. <span data-ttu-id="ee3ff-129">Щелкните элемент **Код страны**, а затем введите двузначный вызывной код для страны/региона, где расположен сайт филиала.</span><span class="sxs-lookup"><span data-stu-id="ee3ff-129">Click **Country Code**, and then type the two-digit calling code for the country/region in which the branch site is located.</span></span>
    
7. <span data-ttu-id="ee3ff-130">Нажмите **кнопку** Далее, а затем, если на этом сайте используется устройство или сервер филиала, убедитесь, что при закрытии контрольного окна откройте мастер Open **the New Survivable Wizard.**</span><span class="sxs-lookup"><span data-stu-id="ee3ff-130">Click **Next**, and then, if you are using a Survivable Branch Appliance or Server at this site, be sure to clear the **Open the New Survivable Wizard when this wizard closes** check box.</span></span> <span data-ttu-id="ee3ff-131">Нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="ee3ff-131">Click **Finish**.</span></span>
    
8. <span data-ttu-id="ee3ff-132">Чтобы связать устаревшую SBA с пулом передней части Skype для бизнеса Server 2019:</span><span class="sxs-lookup"><span data-stu-id="ee3ff-132">To associate the legacy SBA to the Skype for Business Server 2019 Front End pool:</span></span>
    
    1. <span data-ttu-id="ee3ff-133">Разверните созданный сайт филиала.</span><span class="sxs-lookup"><span data-stu-id="ee3ff-133">Expand the branch site that has been created.</span></span> 
    
    2. <span data-ttu-id="ee3ff-134">Щелкните правой кнопкой мыши по устаревшей версии, а затем нажмите **кнопку New**.</span><span class="sxs-lookup"><span data-stu-id="ee3ff-134">Right-click on legacy version, and then click **New**.</span></span>
    
    3. <span data-ttu-id="ee3ff-135">Нажмите **кнопку "Сохранимая ветвь".**</span><span class="sxs-lookup"><span data-stu-id="ee3ff-135">Click **Survivable Branch Appliance**.</span></span>
    
9. <span data-ttu-id="ee3ff-136">Следуйте указаниям открывшегося мастера.</span><span class="sxs-lookup"><span data-stu-id="ee3ff-136">Follow the directions in the wizard that opens.</span></span> <span data-ttu-id="ee3ff-137">Сведения о предметах мастера см. в</span><span class="sxs-lookup"><span data-stu-id="ee3ff-137">For information about wizard items, see</span></span>    
   <!-- [Define a Survivable Branch Appliance or Server in Lync 2013](/previous-versions/office/lync-server-2013/lync-server-2013-define-a-survivable-branch-appliance-or-server). -->
   <!-- The above link points to un-rebranded 2013 content we will need to discuss rebrand or bring forward -->
    
    > [!NOTE]
    > <span data-ttu-id="ee3ff-138">Уцелевшая ветвная техника может быть связана только с хранилищем мониторинга.</span><span class="sxs-lookup"><span data-stu-id="ee3ff-138">A Survivable Branch Appliance can only be associated with a Monitoring Store.</span></span> 
  
10. <span data-ttu-id="ee3ff-139">Если вы не используете на этом сайте устройство или сервер для обеспечения связи в филиалах, снимите флажок **Открыть мастер создания устройства для обеспечения связи в филиалах после завершения работы этого мастера**. а затем нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="ee3ff-139">If you are not using a Survivable Branch Appliance or Server at this site, clear the **Open the New Survivable Wizard when this wizard closes** check box, and then click **Finish**.</span></span>
    
11. <span data-ttu-id="ee3ff-140">Повторите перечисленные выше действия для каждого сайта филиала, который вы хотите добавить в топологию.</span><span class="sxs-lookup"><span data-stu-id="ee3ff-140">Repeat the previous steps for each branch site you want to add to the topology.</span></span>
