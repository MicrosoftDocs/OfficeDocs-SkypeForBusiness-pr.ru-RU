---
title: Подключение Survivable Branch Appliance
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Каждые для обеспечения связи в филиалах Appliance (SBA) связан с пулом переднего плана, который выступает в качестве резервного регистратора для SBA. Когда переднего плана миграции пула Скайп для 2019 Business Server, устройство должно отделяется от пула переднего плана, во время обновления пула после пула были перенесены на Скайп для Business Server 2019, устройство может быть повторно связано с обновленных переднего E Вторая пула. Данная операция подразумевает удаление SBA из устаревшего топологии в построителе топологий и добавляя SBA Скайп для топологии Business Server 2019. Пользователей, размещенных на устаревший SBA необходимо сначала перемещены в другой пул переднего плана перед удалением на устройство из топологии. После добавления SBA для Скайп для топологии Business Server 2019 этих пользователей можно затем перемещать обратно на устройство. Эти действия приведены ниже.
ms.openlocfilehash: 6de2b8c228ef9e65f57b70451ac33350a2d8a456
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2018
ms.locfileid: "25030583"
---
# <a name="connect-a-survivable-branch-appliance"></a><span data-ttu-id="936a7-108">Подключение Survivable Branch Appliance</span><span class="sxs-lookup"><span data-stu-id="936a7-108">Connect a Survivable Branch Appliance</span></span>

<span data-ttu-id="936a7-109">Каждые для обеспечения связи в филиалах Appliance (SBA) связан с пулом переднего плана, который выступает в качестве резервного регистратора для SBA.</span><span class="sxs-lookup"><span data-stu-id="936a7-109">Every Survivable Branch Appliance (SBA) is associated with a Front End pool that serves as a backup registrar for the SBA.</span></span> <span data-ttu-id="936a7-110">При переносе пула переднего плана Скайп для Business Server 2019 SBA необходимо отделяется от пула переднего плана, во время обновления пула.</span><span class="sxs-lookup"><span data-stu-id="936a7-110">When the Front End pool is migrated to Skype for Business Server 2019, the SBA must be disassociated from the Front End pool while the pool is upgraded.</span></span> <span data-ttu-id="936a7-111">После пула уже перенесены в Скайп для Business Server 2019, устройство можно повторно связать с обновленных пула переднего плана.</span><span class="sxs-lookup"><span data-stu-id="936a7-111">After the pool has been migrated to Skype for Business Server 2019, the SBA can be re-associated with the upgraded Front End pool.</span></span> <span data-ttu-id="936a7-112">Данная операция подразумевает удаление SBA из устаревшего топологии в построителе топологий и добавляя SBA Скайп для топологии Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="936a7-112">This involves deleting the SBA from the legacy topology in Topology Builder and then adding the SBA to the Skype for Business Server 2019 topology.</span></span> <span data-ttu-id="936a7-113">Пользователей, размещенных на устаревший SBA необходимо сначала перемещены в другой пул переднего плана перед удалением на устройство из топологии.</span><span class="sxs-lookup"><span data-stu-id="936a7-113">Users homed on the legacy SBA must first be moved to another Front End pool before removing the SBA from the topology.</span></span> <span data-ttu-id="936a7-114">После добавления SBA Скайп для Business Server 2019 топологии, этих пользователей можно перемещать обратно на устройство.</span><span class="sxs-lookup"><span data-stu-id="936a7-114">After the SBA is added to the Skype for Business Server 2019 topology, those users can be moved back to the SBA.</span></span> <span data-ttu-id="936a7-115">Эти действия приведены ниже.</span><span class="sxs-lookup"><span data-stu-id="936a7-115">These steps are summarized below:</span></span>
  
1. <span data-ttu-id="936a7-116">Переместите пользователей филиала, размещенных на устаревшее устройство в другой пул переднего плана.</span><span class="sxs-lookup"><span data-stu-id="936a7-116">Move branch users homed on the legacy SBA to another Front End pool.</span></span>
    
2. <span data-ttu-id="936a7-117">Удалите устройство из устаревшего топологии для отключения существующего пула переднего плана в качестве резервного регистратора.</span><span class="sxs-lookup"><span data-stu-id="936a7-117">Remove SBA from the legacy topology to disconnect the existing Front End pool as a backup registrar.</span></span>
    
3. <span data-ttu-id="936a7-118">Добавьте устройство для Скайп для топологии Business Server 2019 и настройка этого нового пула переднего плана в качестве резервного регистратора.</span><span class="sxs-lookup"><span data-stu-id="936a7-118">Add SBA to the Skype for Business Server 2019 topology and configure this new Front End pool as the backup registrar.</span></span> 
    
4. <span data-ttu-id="936a7-119">Переместите пользователей филиала новые Скайп для Business Server 2019 SBA.</span><span class="sxs-lookup"><span data-stu-id="936a7-119">Move the branch users to the new Skype for Business Server 2019 SBA.</span></span>
    
### <a name="add-legacy-sba-branch-site-to-your-topology"></a><span data-ttu-id="936a7-120">Добавление сайта филиала прежних версий SBA в топологию</span><span class="sxs-lookup"><span data-stu-id="936a7-120">Add legacy SBA branch site to your topology</span></span>

1. <span data-ttu-id="936a7-121">Откройте **Построитель топологий**.</span><span class="sxs-lookup"><span data-stu-id="936a7-121">Open **Topology Builder**.</span></span>
    
2. <span data-ttu-id="936a7-122">В левой области щелкните правой кнопкой мыши **сайтов филиалов**и выберите команду **Создать сайт филиала**.</span><span class="sxs-lookup"><span data-stu-id="936a7-122">In the left pane, right-click **Branch sites**, and then click **New Branch Site**.</span></span>
    
3. <span data-ttu-id="936a7-123">В диалоговом окне **Определение нового сайта филиала** щелкните **имя**и введите имя сайта филиала.</span><span class="sxs-lookup"><span data-stu-id="936a7-123">In the **Define New Branch Site** dialog box, click **Name**, and then type the name of the branch site.</span></span>
    
4. <span data-ttu-id="936a7-124">(Необязательно) Щелкните **Описание**и затем введите содержательное описание для сайта филиала.</span><span class="sxs-lookup"><span data-stu-id="936a7-124">(Optional) Click **Description**, and then type a meaningful description for the branch site.</span></span>
    
5. <span data-ttu-id="936a7-125">Нажмите **Далее**.</span><span class="sxs-lookup"><span data-stu-id="936a7-125">Click **Next**.</span></span>
    
6. <span data-ttu-id="936a7-126">(Необязательно) В следующем диалоговом окне **Определение нового сайта филиала** выполните одно из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="936a7-126">(Optional) In the next **Define New Branch Site** dialog box, do any of the following:</span></span> 
    
    1. <span data-ttu-id="936a7-127">Щелкните элемент **Город**и затем введите название города, в котором расположен сайт филиала.</span><span class="sxs-lookup"><span data-stu-id="936a7-127">Click **City**, and then type the name of the city in which the branch site is located.</span></span>
    
    2. <span data-ttu-id="936a7-128">Щелкните регион \*\*\*\*, а затем введите имя области или региона, в котором расположен сайт филиала.</span><span class="sxs-lookup"><span data-stu-id="936a7-128">Click **State/Region**, and then type the name of the state or region in which the branch site is located.</span></span>
    
    3. <span data-ttu-id="936a7-129">Выберите **Код страны**и затем введите двузначный вызывающий код для страны или региона, в котором расположен сайт филиала.</span><span class="sxs-lookup"><span data-stu-id="936a7-129">Click **Country Code**, and then type the two-digit calling code for the country/region in which the branch site is located.</span></span>
    
7. <span data-ttu-id="936a7-130">Нажмите кнопку **Далее**, а затем, если вы используете для обеспечения связи в филиалах или сервере на этом сайте, убедитесь, снимите флажок **Открыть мастер создания для обеспечения связи при закрытии этого мастера** .</span><span class="sxs-lookup"><span data-stu-id="936a7-130">Click **Next**, and then, if you are using a Survivable Branch Appliance or Server at this site, be sure to clear the **Open the New Survivable Wizard when this wizard closes** check box.</span></span> <span data-ttu-id="936a7-131">Нажмите кнопку \*\*Готово \*\*.</span><span class="sxs-lookup"><span data-stu-id="936a7-131">Click **Finish**.</span></span>
    
8. <span data-ttu-id="936a7-132">Чтобы сопоставить устаревшее устройство для Скайп для пула переднего плана Business Server 2019:</span><span class="sxs-lookup"><span data-stu-id="936a7-132">To associate the legacy SBA to the Skype for Business Server 2019 Front End pool:</span></span>
    
    1. <span data-ttu-id="936a7-133">Разверните узел филиала, который был создан.</span><span class="sxs-lookup"><span data-stu-id="936a7-133">Expand the branch site that has been created.</span></span> 
    
    2. <span data-ttu-id="936a7-134">Щелкните правой кнопкой мыши на старой версии и нажмите кнопку **Создать**.</span><span class="sxs-lookup"><span data-stu-id="936a7-134">Right-click on legacy version, and then click **New**.</span></span>
    
    3. <span data-ttu-id="936a7-135">Выберите **устройство для обеспечения связи в филиалах**.</span><span class="sxs-lookup"><span data-stu-id="936a7-135">Click **Survivable Branch Appliance**.</span></span>
    
9. <span data-ttu-id="936a7-136">Следуйте инструкциям в открывшемся мастере создания.</span><span class="sxs-lookup"><span data-stu-id="936a7-136">Follow the directions in the wizard that opens.</span></span> <span data-ttu-id="936a7-137">Сведения об элементах мастера см.</span><span class="sxs-lookup"><span data-stu-id="936a7-137">For information about wizard items, see</span></span>    
<!-- [Define a Survivable Branch Appliance or Server in Lync 2013](https://technet.microsoft.com/en-us/library/gg398280(v=ocs.15).aspx). -->
 <!-- The above link points to un-rebranded 2013 content we will need to discuss rebrand or bring forward -->
    
    > [!NOTE]
    > <span data-ttu-id="936a7-138">Устройство для обеспечения связи в филиалах может быть связано только с хранилищем данных наблюдения.</span><span class="sxs-lookup"><span data-stu-id="936a7-138">A Survivable Branch Appliance can only be associated with a Monitoring Store.</span></span> 
  
10. <span data-ttu-id="936a7-139">Если вы не используете устройства для обеспечения связи в филиалах или сервере на этом сайте, снимите флажок **Открыть мастер создания для обеспечения связи при закрытии этого мастера** и нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="936a7-139">If you are not using a Survivable Branch Appliance or Server at this site, clear the **Open the New Survivable Wizard when this wizard closes** check box, and then click **Finish**.</span></span>
    
11. <span data-ttu-id="936a7-140">Повторите предыдущие действия для каждого сайта филиала, который требуется добавить в топологию.</span><span class="sxs-lookup"><span data-stu-id="936a7-140">Repeat the previous steps for each branch site you want to add to the topology.</span></span>
    

