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
description: Каждое устройство для связи в филиалах (SBA) связано с пулом переднего план, который выступает в качестве резервного регистратора для SBA. When the Front End pool is migrated to Skype for Business Server 2019, the SBA must be disassociated from the Front End pool while the pool is upgraded. Once the pool has been migrated to Skype for Business Server 2019, the SBA can be re-associated with the upgraded Front End pool. Для этого необходимо удалить SBA из устаревшей топологии в построитель топологий, а затем добавить SBA в топологию Skype для бизнеса Server 2019. Прежде чем удалять SBA из топологии, пользователей, которые были в устаревшем SBA, необходимо сначала удалить в другой пул переднего входа. После того как SBA будет добавлена в топологию Skype для бизнеса Server 2019, эти пользователи могут быть перемещены обратно в SBA. Эти действия приведены ниже.
ms.openlocfilehash: 23fea7694a754b82ecad684d2ea02b603a6c7299
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/16/2020
ms.locfileid: "44751551"
---
# <a name="connect-a-survivable-branch-appliance"></a><span data-ttu-id="82e4a-108">Подключение Survivable Branch Appliance</span><span class="sxs-lookup"><span data-stu-id="82e4a-108">Connect a Survivable Branch Appliance</span></span>

<span data-ttu-id="82e4a-109">Каждое устройство для связи в филиалах (SBA) связано с пулом переднего план, который выступает в качестве резервного регистратора для SBA.</span><span class="sxs-lookup"><span data-stu-id="82e4a-109">Every Survivable Branch Appliance (SBA) is associated with a Front End pool that serves as a backup registrar for the SBA.</span></span> <span data-ttu-id="82e4a-110">When the Front End pool is migrated to Skype for Business Server 2019, the SBA must be disassociated from the Front End pool while the pool is upgraded.</span><span class="sxs-lookup"><span data-stu-id="82e4a-110">When the Front End pool is migrated to Skype for Business Server 2019, the SBA must be disassociated from the Front End pool while the pool is upgraded.</span></span> <span data-ttu-id="82e4a-111">После переноса пула в Skype для бизнеса Server 2019, SBA можно повторно примедить с обновленным пулом переднего сервера.</span><span class="sxs-lookup"><span data-stu-id="82e4a-111">After the pool has been migrated to Skype for Business Server 2019, the SBA can be re-associated with the upgraded Front End pool.</span></span> <span data-ttu-id="82e4a-112">Для этого необходимо удалить SBA из устаревшей топологии в построитель топологий, а затем добавить SBA в топологию Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="82e4a-112">This involves deleting the SBA from the legacy topology in Topology Builder and then adding the SBA to the Skype for Business Server 2019 topology.</span></span> <span data-ttu-id="82e4a-113">Прежде чем удалять SBA из топологии, пользователей, которые были в устаревшем SBA, необходимо сначала удалить в другой пул переднего входа.</span><span class="sxs-lookup"><span data-stu-id="82e4a-113">Users homed on the legacy SBA must first be moved to another Front End pool before removing the SBA from the topology.</span></span> <span data-ttu-id="82e4a-114">После того как SBA будет добавлена в топологию Skype для бизнеса Server 2019, эти пользователи могут быть перемещены обратно в SBA.</span><span class="sxs-lookup"><span data-stu-id="82e4a-114">After the SBA is added to the Skype for Business Server 2019 topology, those users can be moved back to the SBA.</span></span> <span data-ttu-id="82e4a-115">Эти действия приведены ниже.</span><span class="sxs-lookup"><span data-stu-id="82e4a-115">These steps are summarized below:</span></span>
  
1. <span data-ttu-id="82e4a-116">Переместить пользователей филиала, которые были в устаревшем SBA, в другой пул переднего входа.</span><span class="sxs-lookup"><span data-stu-id="82e4a-116">Move branch users homed on the legacy SBA to another Front End pool.</span></span>
    
2. <span data-ttu-id="82e4a-117">Удалите SBA из устаревшей топологии, чтобы отключить существующий пул переднего план в качестве резервного регистратора.</span><span class="sxs-lookup"><span data-stu-id="82e4a-117">Remove SBA from the legacy topology to disconnect the existing Front End pool as a backup registrar.</span></span>
    
3. <span data-ttu-id="82e4a-118">Добавьте SBA в топологию Skype для бизнеса Server 2019 и настройте этот новый пул переднего сервера в качестве резервного регистратора.</span><span class="sxs-lookup"><span data-stu-id="82e4a-118">Add SBA to the Skype for Business Server 2019 topology and configure this new Front End pool as the backup registrar.</span></span> 
    
4. <span data-ttu-id="82e4a-119">Перемещение пользователей филиала в новую SBA Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="82e4a-119">Move the branch users to the new Skype for Business Server 2019 SBA.</span></span>
    
### <a name="add-legacy-sba-branch-site-to-your-topology"></a><span data-ttu-id="82e4a-120">Добавление устаревшего сайта филиала SBA в топологию</span><span class="sxs-lookup"><span data-stu-id="82e4a-120">Add legacy SBA branch site to your topology</span></span>

1. <span data-ttu-id="82e4a-121">Откройте **построитель топологий**.</span><span class="sxs-lookup"><span data-stu-id="82e4a-121">Open **Topology Builder**.</span></span>
    
2. <span data-ttu-id="82e4a-122">В левой области щелкните правой кнопкой мыши сайты **филиалов** и выберите **"Новый сайт филиала".**</span><span class="sxs-lookup"><span data-stu-id="82e4a-122">In the left pane, right-click **Branch sites**, and then click **New Branch Site**.</span></span>
    
3. <span data-ttu-id="82e4a-123">В диалоговом окне **Определение нового сайта филиала для сайта** щелкните элемент **Имя**, а затем введите имя сайта филиала.</span><span class="sxs-lookup"><span data-stu-id="82e4a-123">In the **Define New Branch Site** dialog box, click **Name**, and then type the name of the branch site.</span></span>
    
4. <span data-ttu-id="82e4a-124">(Необязательно) Щелкните элемент **Описание**, а затем введите содержательное описание для сайта филиала.</span><span class="sxs-lookup"><span data-stu-id="82e4a-124">(Optional) Click **Description**, and then type a meaningful description for the branch site.</span></span>
    
5. <span data-ttu-id="82e4a-125">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="82e4a-125">Click **Next**.</span></span>
    
6. <span data-ttu-id="82e4a-126">(Необязательно) В следующем диалоговом окне **Определение нового сайта филиала для сайта** выполните любое из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="82e4a-126">(Optional) In the next **Define New Branch Site** dialog box, do any of the following:</span></span> 
    
    1. <span data-ttu-id="82e4a-127">Щелкните элемент **Город**, а затем введите название города, в котором расположен сайт филиала.</span><span class="sxs-lookup"><span data-stu-id="82e4a-127">Click **City**, and then type the name of the city in which the branch site is located.</span></span>
    
    2. <span data-ttu-id="82e4a-128">Щелкните элемент **Регион**, а затем введите название региона или области, где расположен сайт филиала.</span><span class="sxs-lookup"><span data-stu-id="82e4a-128">Click **State/Region**, and then type the name of the state or region in which the branch site is located.</span></span>
    
    3. <span data-ttu-id="82e4a-129">Щелкните элемент **Код страны**, а затем введите двузначный вызывной код для страны/региона, где расположен сайт филиала.</span><span class="sxs-lookup"><span data-stu-id="82e4a-129">Click **Country Code**, and then type the two-digit calling code for the country/region in which the branch site is located.</span></span>
    
7. <span data-ttu-id="82e4a-130">Нажмите **кнопку**"Далее", а затем, если вы используете устройство или сервер для связи в филиалах на этом сайте, не забудьте очистить мастер открытия нового устройства для связи в филиалах, когда этот мастер закроет **этот** контроль.</span><span class="sxs-lookup"><span data-stu-id="82e4a-130">Click **Next**, and then, if you are using a Survivable Branch Appliance or Server at this site, be sure to clear the **Open the New Survivable Wizard when this wizard closes** check box.</span></span> <span data-ttu-id="82e4a-131">Нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="82e4a-131">Click **Finish**.</span></span>
    
8. <span data-ttu-id="82e4a-132">Чтобы связать устаревшую SBA с пулом переднего сервера Skype для бизнеса Server 2019:</span><span class="sxs-lookup"><span data-stu-id="82e4a-132">To associate the legacy SBA to the Skype for Business Server 2019 Front End pool:</span></span>
    
    1. <span data-ttu-id="82e4a-133">Разверните созданный сайт филиала.</span><span class="sxs-lookup"><span data-stu-id="82e4a-133">Expand the branch site that has been created.</span></span> 
    
    2. <span data-ttu-id="82e4a-134">Щелкните правой кнопкой мыши устаревшую версию и выберите **"Новый".**</span><span class="sxs-lookup"><span data-stu-id="82e4a-134">Right-click on legacy version, and then click **New**.</span></span>
    
    3. <span data-ttu-id="82e4a-135">Щелкните **устройство для survivable branch appliance**.</span><span class="sxs-lookup"><span data-stu-id="82e4a-135">Click **Survivable Branch Appliance**.</span></span>
    
9. <span data-ttu-id="82e4a-136">Следуйте указаниям открывшегося мастера.</span><span class="sxs-lookup"><span data-stu-id="82e4a-136">Follow the directions in the wizard that opens.</span></span> <span data-ttu-id="82e4a-137">Сведения об элементе мастера см. в</span><span class="sxs-lookup"><span data-stu-id="82e4a-137">For information about wizard items, see</span></span>    
   <!-- [Define a Survivable Branch Appliance or Server in Lync 2013](https://technet.microsoft.com/library/gg398280(v=ocs.15).aspx). -->
   <!-- The above link points to un-rebranded 2013 content we will need to discuss rebrand or bring forward -->
    
    > [!NOTE]
    > <span data-ttu-id="82e4a-138">Устройство для связи в филиалах может быть связано только с хранилищем мониторинга.</span><span class="sxs-lookup"><span data-stu-id="82e4a-138">A Survivable Branch Appliance can only be associated with a Monitoring Store.</span></span> 
  
10. <span data-ttu-id="82e4a-139">Если вы не используете на этом сайте устройство или сервер для обеспечения связи в филиалах, снимите флажок **Открыть мастер создания устройства для обеспечения связи в филиалах после завершения работы этого мастера**. а затем нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="82e4a-139">If you are not using a Survivable Branch Appliance or Server at this site, clear the **Open the New Survivable Wizard when this wizard closes** check box, and then click **Finish**.</span></span>
    
11. <span data-ttu-id="82e4a-140">Повторите перечисленные выше действия для каждого сайта филиала, который вы хотите добавить в топологию.</span><span class="sxs-lookup"><span data-stu-id="82e4a-140">Repeat the previous steps for each branch site you want to add to the topology.</span></span>
    

