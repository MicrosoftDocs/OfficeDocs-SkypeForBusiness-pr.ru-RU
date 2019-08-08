---
title: Подключение Survivable Branch Appliance
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Каждое работающее устройство филиала (СБА) связано с пулом переднего плана, который выступает в качестве регистратора резервных копий для СБА. Когда пул переднего плана переносится в Skype для бизнеса Server 2019, СБА должен быть связан с пулом переднего плана при обновлении пула, после того как пул будет перенесен в Skype для бизнеса Server 2019, СБА может быть повторно связан с обновленным интерфейсом E. пул ND. Это связано с тем, что удаление СБА из старой топологии в построителе топологии и добавление СБА в топологию 2019 в Skype для бизнеса Server. Пользователи, размещенные на устаревшем СБА, должны сначала переместиться в другой пул переднего плана, прежде чем удалять СБА из топологии. После добавления СБА в топологию Skype для бизнеса Server 2019 эти пользователи могут затем возвращаться в СБА. Эти действия описаны ниже.
ms.openlocfilehash: e5545a2de4eddd65790f425ab888b8fd07faf970
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/07/2019
ms.locfileid: "36239286"
---
# <a name="connect-a-survivable-branch-appliance"></a><span data-ttu-id="ba467-108">Подключение Survivable Branch Appliance</span><span class="sxs-lookup"><span data-stu-id="ba467-108">Connect a Survivable Branch Appliance</span></span>

<span data-ttu-id="ba467-109">Каждое работающее устройство филиала (СБА) связано с пулом переднего плана, который выступает в качестве регистратора резервных копий для СБА.</span><span class="sxs-lookup"><span data-stu-id="ba467-109">Every Survivable Branch Appliance (SBA) is associated with a Front End pool that serves as a backup registrar for the SBA.</span></span> <span data-ttu-id="ba467-110">Когда пул переднего плана переносится в Skype для бизнеса Server 2019, СБА необходимо разорвать связь с пулом переднего плана, пока он не будет обновлен.</span><span class="sxs-lookup"><span data-stu-id="ba467-110">When the Front End pool is migrated to Skype for Business Server 2019, the SBA must be disassociated from the Front End pool while the pool is upgraded.</span></span> <span data-ttu-id="ba467-111">После того как пул будет перенесен на Skype для бизнеса Server 2019, СБА может быть повторно связан с обновленным пулом интерфейсов.</span><span class="sxs-lookup"><span data-stu-id="ba467-111">After the pool has been migrated to Skype for Business Server 2019, the SBA can be re-associated with the upgraded Front End pool.</span></span> <span data-ttu-id="ba467-112">Это связано с тем, что удаление СБА из старой топологии в построителе топологии и добавление СБА в топологию 2019 в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="ba467-112">This involves deleting the SBA from the legacy topology in Topology Builder and then adding the SBA to the Skype for Business Server 2019 topology.</span></span> <span data-ttu-id="ba467-113">Пользователи, размещенные на устаревшем СБА, должны сначала переместиться в другой пул переднего плана, прежде чем удалять СБА из топологии.</span><span class="sxs-lookup"><span data-stu-id="ba467-113">Users homed on the legacy SBA must first be moved to another Front End pool before removing the SBA from the topology.</span></span> <span data-ttu-id="ba467-114">После добавления СБА в топологию 2019 в Skype для бизнеса Server эти пользователи могут быть возвращены в СБА.</span><span class="sxs-lookup"><span data-stu-id="ba467-114">After the SBA is added to the Skype for Business Server 2019 topology, those users can be moved back to the SBA.</span></span> <span data-ttu-id="ba467-115">Эти действия описаны ниже.</span><span class="sxs-lookup"><span data-stu-id="ba467-115">These steps are summarized below:</span></span>
  
1. <span data-ttu-id="ba467-116">Переместить пользователей филиалов, расположенные на устаревшем СБА, в другой пул переднего плана.</span><span class="sxs-lookup"><span data-stu-id="ba467-116">Move branch users homed on the legacy SBA to another Front End pool.</span></span>
    
2. <span data-ttu-id="ba467-117">Удалите СБА из старой топологии, чтобы отключить существующий пул переднего плана в качестве регистратора резервных копий.</span><span class="sxs-lookup"><span data-stu-id="ba467-117">Remove SBA from the legacy topology to disconnect the existing Front End pool as a backup registrar.</span></span>
    
3. <span data-ttu-id="ba467-118">Добавьте СБА в топологию 2019 в Skype для бизнеса Server и настройте этот новый пул переднего плана в качестве регистратора резервных копий.</span><span class="sxs-lookup"><span data-stu-id="ba467-118">Add SBA to the Skype for Business Server 2019 topology and configure this new Front End pool as the backup registrar.</span></span> 
    
4. <span data-ttu-id="ba467-119">Переместите пользователей филиалов на новый Skype для бизнеса Server 2019 СБА.</span><span class="sxs-lookup"><span data-stu-id="ba467-119">Move the branch users to the new Skype for Business Server 2019 SBA.</span></span>
    
### <a name="add-legacy-sba-branch-site-to-your-topology"></a><span data-ttu-id="ba467-120">Добавление в топологию устаревшего сайта филиала СБА</span><span class="sxs-lookup"><span data-stu-id="ba467-120">Add legacy SBA branch site to your topology</span></span>

1. <span data-ttu-id="ba467-121">Открытие **построителя топологии**.</span><span class="sxs-lookup"><span data-stu-id="ba467-121">Open **Topology Builder**.</span></span>
    
2. <span data-ttu-id="ba467-122">На левой панели щелкните правой кнопкой мыши пункт **сайты филиалов**и выберите команду **создать сайт филиала**.</span><span class="sxs-lookup"><span data-stu-id="ba467-122">In the left pane, right-click **Branch sites**, and then click **New Branch Site**.</span></span>
    
3. <span data-ttu-id="ba467-123">В диалоговом окне **Определение нового сайта ветви** щелкните **имя**и введите имя сайта ветви.</span><span class="sxs-lookup"><span data-stu-id="ba467-123">In the **Define New Branch Site** dialog box, click **Name**, and then type the name of the branch site.</span></span>
    
4. <span data-ttu-id="ba467-124">Необязательно Нажмите кнопку **Описание**и введите понятное описание сайта филиала.</span><span class="sxs-lookup"><span data-stu-id="ba467-124">(Optional) Click **Description**, and then type a meaningful description for the branch site.</span></span>
    
5. <span data-ttu-id="ba467-125">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="ba467-125">Click **Next**.</span></span>
    
6. <span data-ttu-id="ba467-126">Необязательно В диалоговом окне **Определение нового сайта ветви** выполните одно из указанных ниже действий.</span><span class="sxs-lookup"><span data-stu-id="ba467-126">(Optional) In the next **Define New Branch Site** dialog box, do any of the following:</span></span> 
    
    1. <span data-ttu-id="ba467-127">Щелкните **город**и введите имя города, в котором находится сайт филиала.</span><span class="sxs-lookup"><span data-stu-id="ba467-127">Click **City**, and then type the name of the city in which the branch site is located.</span></span>
    
    2. <span data-ttu-id="ba467-128">Щелкните область или **регион**, а затем введите имя состояния или региона, в котором находится сайт филиала.</span><span class="sxs-lookup"><span data-stu-id="ba467-128">Click **State/Region**, and then type the name of the state or region in which the branch site is located.</span></span>
    
    3. <span data-ttu-id="ba467-129">Щелкните **код страны**, а затем введите четырехзначный код звонка для страны или региона, в котором расположен сайт филиала.</span><span class="sxs-lookup"><span data-stu-id="ba467-129">Click **Country Code**, and then type the two-digit calling code for the country/region in which the branch site is located.</span></span>
    
7. <span data-ttu-id="ba467-130">Нажмите кнопку **Далее**, а затем, если вы используете устройство с бесперебойной ветвью или сервер на этом сайте, не забудьте снять флажок **открывать новый бесперебойный мастер, когда этот мастер** закроется.</span><span class="sxs-lookup"><span data-stu-id="ba467-130">Click **Next**, and then, if you are using a Survivable Branch Appliance or Server at this site, be sure to clear the **Open the New Survivable Wizard when this wizard closes** check box.</span></span> <span data-ttu-id="ba467-131">Нажмите **Готово**.</span><span class="sxs-lookup"><span data-stu-id="ba467-131">Click **Finish**.</span></span>
    
8. <span data-ttu-id="ba467-132">Чтобы связать старые СБА с пулом интерфейсов Skype для бизнеса Server 2019, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="ba467-132">To associate the legacy SBA to the Skype for Business Server 2019 Front End pool:</span></span>
    
    1. <span data-ttu-id="ba467-133">Разверните созданный сайт ветви.</span><span class="sxs-lookup"><span data-stu-id="ba467-133">Expand the branch site that has been created.</span></span> 
    
    2. <span data-ttu-id="ba467-134">Щелкните старую версию правой кнопкой мыши и выберите команду **создать**.</span><span class="sxs-lookup"><span data-stu-id="ba467-134">Right-click on legacy version, and then click **New**.</span></span>
    
    3. <span data-ttu-id="ba467-135">Щелкните **устройство**для бесперебойной ветви.</span><span class="sxs-lookup"><span data-stu-id="ba467-135">Click **Survivable Branch Appliance**.</span></span>
    
9. <span data-ttu-id="ba467-136">Следуйте указаниям в открывшемся мастере.</span><span class="sxs-lookup"><span data-stu-id="ba467-136">Follow the directions in the wizard that opens.</span></span> <span data-ttu-id="ba467-137">Сведения об элементах мастера можно найти в разделе</span><span class="sxs-lookup"><span data-stu-id="ba467-137">For information about wizard items, see</span></span>    
   <!-- [Define a Survivable Branch Appliance or Server in Lync 2013](https://technet.microsoft.com/en-us/library/gg398280(v=ocs.15).aspx). -->
   <!-- The above link points to un-rebranded 2013 content we will need to discuss rebrand or bring forward -->
    
    > [!NOTE]
    > <span data-ttu-id="ba467-138">Бесперебойно работающее устройство филиала можно связать только с хранилищем мониторинга.</span><span class="sxs-lookup"><span data-stu-id="ba467-138">A Survivable Branch Appliance can only be associated with a Monitoring Store.</span></span> 
  
10. <span data-ttu-id="ba467-139">Если вы не используете бесперебойно работающее устройство или сервер филиала на этом сайте, снимите флажок **открыть новый бесперебойный мастер, когда мастер** закроется, и нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="ba467-139">If you are not using a Survivable Branch Appliance or Server at this site, clear the **Open the New Survivable Wizard when this wizard closes** check box, and then click **Finish**.</span></span>
    
11. <span data-ttu-id="ba467-140">Повторите описанные выше действия для всех сайтов филиалов, которые нужно добавить в топологию.</span><span class="sxs-lookup"><span data-stu-id="ba467-140">Repeat the previous steps for each branch site you want to add to the topology.</span></span>
    

