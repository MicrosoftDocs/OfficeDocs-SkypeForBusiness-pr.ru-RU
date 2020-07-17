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
description: Каждое устройство для обеспечения связи в филиалах (SBA) связано с пулом переднего плана, который выступает в качестве регистратора резервных копий для SBA. Когда интерфейсный пул переносится в Skype для бизнеса Server 2019, SBA должен быть связан с пулом переднего плана при его обновлении, после переноса пула в Skype для бизнеса Server 2019, SBA можно повторно связать с обновленным интерфейсным пулом. Это включает удаление SBA из устаревшей топологии в построителе топологий и добавление SBA в топологию Skype для бизнеса Server 2019. Пользователи, размещенные на устаревшем SBA, сначала должны быть перемещены в другой пул переднего плана перед удалением SBA из топологии. После добавления SBA в топологию Skype для бизнеса Server 2019 эти пользователи могут быть возвращены в SBA. Эти действия приведены ниже.
ms.openlocfilehash: 23fea7694a754b82ecad684d2ea02b603a6c7299
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/16/2020
ms.locfileid: "44751551"
---
# <a name="connect-a-survivable-branch-appliance"></a><span data-ttu-id="33133-108">Подключение Survivable Branch Appliance</span><span class="sxs-lookup"><span data-stu-id="33133-108">Connect a Survivable Branch Appliance</span></span>

<span data-ttu-id="33133-109">Каждое устройство для обеспечения связи в филиалах (SBA) связано с пулом переднего плана, который выступает в качестве регистратора резервных копий для SBA.</span><span class="sxs-lookup"><span data-stu-id="33133-109">Every Survivable Branch Appliance (SBA) is associated with a Front End pool that serves as a backup registrar for the SBA.</span></span> <span data-ttu-id="33133-110">После переноса пула переднего плана в Skype для бизнеса Server 2019 SBA должен быть связан с интерфейсным пулом при его обновлении.</span><span class="sxs-lookup"><span data-stu-id="33133-110">When the Front End pool is migrated to Skype for Business Server 2019, the SBA must be disassociated from the Front End pool while the pool is upgraded.</span></span> <span data-ttu-id="33133-111">После переноса пула в Skype для бизнеса Server 2019 SBA может быть повторно связан с обновленным интерфейсным пулом.</span><span class="sxs-lookup"><span data-stu-id="33133-111">After the pool has been migrated to Skype for Business Server 2019, the SBA can be re-associated with the upgraded Front End pool.</span></span> <span data-ttu-id="33133-112">Это включает удаление SBA из устаревшей топологии в построителе топологий и добавление SBA в топологию Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="33133-112">This involves deleting the SBA from the legacy topology in Topology Builder and then adding the SBA to the Skype for Business Server 2019 topology.</span></span> <span data-ttu-id="33133-113">Пользователи, размещенные на устаревшем SBA, сначала должны быть перемещены в другой пул переднего плана перед удалением SBA из топологии.</span><span class="sxs-lookup"><span data-stu-id="33133-113">Users homed on the legacy SBA must first be moved to another Front End pool before removing the SBA from the topology.</span></span> <span data-ttu-id="33133-114">После добавления SBA в топологию Skype для бизнеса Server 2019 эти пользователи могут быть возвращены в SBA.</span><span class="sxs-lookup"><span data-stu-id="33133-114">After the SBA is added to the Skype for Business Server 2019 topology, those users can be moved back to the SBA.</span></span> <span data-ttu-id="33133-115">Эти действия приведены ниже.</span><span class="sxs-lookup"><span data-stu-id="33133-115">These steps are summarized below:</span></span>
  
1. <span data-ttu-id="33133-116">Переместите пользователей филиалов, размещенных на устаревшем SBA, в другой интерфейсный пул.</span><span class="sxs-lookup"><span data-stu-id="33133-116">Move branch users homed on the legacy SBA to another Front End pool.</span></span>
    
2. <span data-ttu-id="33133-117">Удалите SBA из устаревшей топологии, чтобы отключить существующий интерфейсный пул в качестве регистратора резервных копий.</span><span class="sxs-lookup"><span data-stu-id="33133-117">Remove SBA from the legacy topology to disconnect the existing Front End pool as a backup registrar.</span></span>
    
3. <span data-ttu-id="33133-118">Добавьте SBA в топологию Skype для бизнеса Server 2019 и настройте этот новый интерфейсный пул в качестве регистратора резервных копий.</span><span class="sxs-lookup"><span data-stu-id="33133-118">Add SBA to the Skype for Business Server 2019 topology and configure this new Front End pool as the backup registrar.</span></span> 
    
4. <span data-ttu-id="33133-119">Переместите пользователей филиала на новый сервер Skype для бизнеса 2019 SBA.</span><span class="sxs-lookup"><span data-stu-id="33133-119">Move the branch users to the new Skype for Business Server 2019 SBA.</span></span>
    
### <a name="add-legacy-sba-branch-site-to-your-topology"></a><span data-ttu-id="33133-120">Добавление устаревшего сайта филиала SBA к топологии</span><span class="sxs-lookup"><span data-stu-id="33133-120">Add legacy SBA branch site to your topology</span></span>

1. <span data-ttu-id="33133-121">Откройте **построитель топологий**.</span><span class="sxs-lookup"><span data-stu-id="33133-121">Open **Topology Builder**.</span></span>
    
2. <span data-ttu-id="33133-122">В левой области щелкните правой кнопкой мыши **сайты филиалов**, а затем выберите пункт **создать сайт филиала**.</span><span class="sxs-lookup"><span data-stu-id="33133-122">In the left pane, right-click **Branch sites**, and then click **New Branch Site**.</span></span>
    
3. <span data-ttu-id="33133-123">В диалоговом окне **Определение нового сайта филиала для сайта** щелкните элемент **Имя**, а затем введите имя сайта филиала.</span><span class="sxs-lookup"><span data-stu-id="33133-123">In the **Define New Branch Site** dialog box, click **Name**, and then type the name of the branch site.</span></span>
    
4. <span data-ttu-id="33133-124">(Необязательно) Щелкните элемент **Описание**, а затем введите содержательное описание для сайта филиала.</span><span class="sxs-lookup"><span data-stu-id="33133-124">(Optional) Click **Description**, and then type a meaningful description for the branch site.</span></span>
    
5. <span data-ttu-id="33133-125">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="33133-125">Click **Next**.</span></span>
    
6. <span data-ttu-id="33133-126">(Необязательно) В следующем диалоговом окне **Определение нового сайта филиала для сайта** выполните любое из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="33133-126">(Optional) In the next **Define New Branch Site** dialog box, do any of the following:</span></span> 
    
    1. <span data-ttu-id="33133-127">Щелкните элемент **Город**, а затем введите название города, в котором расположен сайт филиала.</span><span class="sxs-lookup"><span data-stu-id="33133-127">Click **City**, and then type the name of the city in which the branch site is located.</span></span>
    
    2. <span data-ttu-id="33133-128">Щелкните элемент **Регион**, а затем введите название региона или области, где расположен сайт филиала.</span><span class="sxs-lookup"><span data-stu-id="33133-128">Click **State/Region**, and then type the name of the state or region in which the branch site is located.</span></span>
    
    3. <span data-ttu-id="33133-129">Щелкните элемент **Код страны**, а затем введите двузначный вызывной код для страны/региона, где расположен сайт филиала.</span><span class="sxs-lookup"><span data-stu-id="33133-129">Click **Country Code**, and then type the two-digit calling code for the country/region in which the branch site is located.</span></span>
    
7. <span data-ttu-id="33133-130">Нажмите кнопку **Далее**, а затем, если вы используете устройство или сервер для обеспечения связи в филиалах на этом сайте, не забудьте снять флажок Открыть новый список доступных для установки, **когда мастер закроется** .</span><span class="sxs-lookup"><span data-stu-id="33133-130">Click **Next**, and then, if you are using a Survivable Branch Appliance or Server at this site, be sure to clear the **Open the New Survivable Wizard when this wizard closes** check box.</span></span> <span data-ttu-id="33133-131">Нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="33133-131">Click **Finish**.</span></span>
    
8. <span data-ttu-id="33133-132">Чтобы сопоставить устаревшую SBA с интерфейсным пулом Skype для бизнеса Server 2019, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="33133-132">To associate the legacy SBA to the Skype for Business Server 2019 Front End pool:</span></span>
    
    1. <span data-ttu-id="33133-133">Разверните созданный сайт филиала.</span><span class="sxs-lookup"><span data-stu-id="33133-133">Expand the branch site that has been created.</span></span> 
    
    2. <span data-ttu-id="33133-134">Щелкните правой кнопкой мыши старую версию и выберите команду **создать**.</span><span class="sxs-lookup"><span data-stu-id="33133-134">Right-click on legacy version, and then click **New**.</span></span>
    
    3. <span data-ttu-id="33133-135">Щелкните устройство для обеспечения связи в **филиалах**.</span><span class="sxs-lookup"><span data-stu-id="33133-135">Click **Survivable Branch Appliance**.</span></span>
    
9. <span data-ttu-id="33133-136">Следуйте указаниям открывшегося мастера.</span><span class="sxs-lookup"><span data-stu-id="33133-136">Follow the directions in the wizard that opens.</span></span> <span data-ttu-id="33133-137">Сведения об элементах мастера можно найти в статье</span><span class="sxs-lookup"><span data-stu-id="33133-137">For information about wizard items, see</span></span>    
   <!-- [Define a Survivable Branch Appliance or Server in Lync 2013](https://technet.microsoft.com/library/gg398280(v=ocs.15).aspx). -->
   <!-- The above link points to un-rebranded 2013 content we will need to discuss rebrand or bring forward -->
    
    > [!NOTE]
    > <span data-ttu-id="33133-138">Устройство для обеспечения связи в филиалах может быть связано только с хранилищем данных мониторинга.</span><span class="sxs-lookup"><span data-stu-id="33133-138">A Survivable Branch Appliance can only be associated with a Monitoring Store.</span></span> 
  
10. <span data-ttu-id="33133-139">Если вы не используете на этом сайте устройство или сервер для обеспечения связи в филиалах, снимите флажок **Открыть мастер создания устройства для обеспечения связи в филиалах после завершения работы этого мастера**. а затем нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="33133-139">If you are not using a Survivable Branch Appliance or Server at this site, clear the **Open the New Survivable Wizard when this wizard closes** check box, and then click **Finish**.</span></span>
    
11. <span data-ttu-id="33133-140">Повторите перечисленные выше действия для каждого сайта филиала, который вы хотите добавить в топологию.</span><span class="sxs-lookup"><span data-stu-id="33133-140">Repeat the previous steps for each branch site you want to add to the topology.</span></span>
    

