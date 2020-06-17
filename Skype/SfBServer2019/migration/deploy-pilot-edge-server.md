---
title: Развертывание пилотного пограничного сервера
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
description: В этом разделе описываются параметры конфигурации, которые следует знать перед развертыванием пограничного сервера Skype для бизнеса Server 2019. Процессы развертывания и настройки Skype для бизнеса Server 2019 очень похожи на Skype для бизнеса Server 2015. В этом разделе рассматриваются только ключевые моменты, которые следует учитывать при развертывании пилотной версии пула. Подробные инструкции приведены в документации по развертыванию, в которой описывается процесс развертывания, а также сведения о конфигурации для доступа внешних пользователей в Skype для бизнеса Server 2019 в документации по развертыванию.
ms.openlocfilehash: 00c371b917f2649dba9011fbbce6162b153822d1
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752871"
---
# <a name="deploy-pilot-edge-server"></a><span data-ttu-id="d4a62-106">Развертывание пилотного пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="d4a62-106">Deploy pilot Edge Server</span></span>

<span data-ttu-id="d4a62-107">В этом разделе описываются параметры конфигурации, которые следует знать перед развертыванием пограничного сервера Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="d4a62-107">This topic highlights configuration settings you should be aware of before deploying your Skype for Business Server 2019 Edge Server.</span></span> <span data-ttu-id="d4a62-108">Процессы развертывания и настройки Skype для бизнеса Server 2019 очень похожи на Skype для бизнеса Server 2015.</span><span class="sxs-lookup"><span data-stu-id="d4a62-108">The deployment and configuration processes for Skype for Business Server 2019 are very similar to Skype for Business Server 2015.</span></span> <span data-ttu-id="d4a62-109">В этом разделе рассматриваются только ключевые моменты, которые следует учитывать при развертывании пилотной версии пула.</span><span class="sxs-lookup"><span data-stu-id="d4a62-109">This section only highlights key points you should consider as part of your pilot pool deployment.</span></span> <!-- For detailed steps, see 
 [Deploying external user access in Skype for Business Server 2019](../deployment/deploying-external-user-access/deploying-external-user-access.md) in the Deployment documentation, which describes the deployment process and also gives configuration information for external user access.  -->
  
<span data-ttu-id="d4a62-110">As you navigate through the **Define New Edge Pool** wizard, review the key configuration settings shown in the following steps.</span><span class="sxs-lookup"><span data-stu-id="d4a62-110">As you navigate through the **Define New Edge Pool** wizard, review the key configuration settings shown in the following steps.</span></span> <span data-ttu-id="d4a62-111">Note that only a few pages of the **Define New Edge Pool** wizard are shown.</span><span class="sxs-lookup"><span data-stu-id="d4a62-111">Note that only a few pages of the **Define New Edge Pool** wizard are shown.</span></span> 
  
### <a name="to-define-an-edge-pool"></a><span data-ttu-id="d4a62-112">Определение пограничного пула</span><span class="sxs-lookup"><span data-stu-id="d4a62-112">To define an Edge Pool</span></span>

1. <span data-ttu-id="d4a62-113">Войдите в систему компьютера, на котором построитель топологий установлен как член группы администраторов доменов и группы RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="d4a62-113">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>
    
2. <span data-ttu-id="d4a62-114">Перейдите на узел Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="d4a62-114">Navigate to the Skype for Business Server 2019 node.</span></span> <span data-ttu-id="d4a62-115">Щелкните правой кнопкой мыши пункт **Пограничные пулы** и выберите в контекстном меню команду **Создать пограничный пул**.</span><span class="sxs-lookup"><span data-stu-id="d4a62-115">Right-click **Edge pools**, and click **New Edge pool**.</span></span>
    
     ![Диалоговое окно "определение нового пограничного пула"](../media/migration_ocs_topo_edgepool_page1.JPG)
  
3. <span data-ttu-id="d4a62-117">Пограничный пул может представлять собой **Пул нескольких компьютеров** или **Пул одиночного компьютера**.</span><span class="sxs-lookup"><span data-stu-id="d4a62-117">An Edge pool can be a **Multiple computer pool** or **Single computer pool**.</span></span>
    
     ![Диалоговое окно "Определение полного доменного имени пограничного пула"](../media/migration_ocs_topo_edgepool_page2.JPG)
  
4. <span data-ttu-id="d4a62-119">На странице **Выбор компонентов** не включайте ни федерацию, ни федерацию XMPP.</span><span class="sxs-lookup"><span data-stu-id="d4a62-119">On the **Select features** page, do not enable federation or XMPP federation.</span></span> <span data-ttu-id="d4a62-120">Федерации Федерации и XMPP в настоящее время направляются через устаревший пограничный сервер.</span><span class="sxs-lookup"><span data-stu-id="d4a62-120">Federation and XMPP federation are both currently routed through the legacy Edge Server.</span></span> <span data-ttu-id="d4a62-121">Эти компоненты настраиваются на более позднем этапе миграции.</span><span class="sxs-lookup"><span data-stu-id="d4a62-121">These features will be configured in a later phase of migration.</span></span> 

  
5. <span data-ttu-id="d4a62-122">Продолжайте выполнение следующих страниц мастера: **Внешние полные доменные имена**, **определение внутреннего IP-адреса**и **Определение внешнего IP-адреса**.</span><span class="sxs-lookup"><span data-stu-id="d4a62-122">Continue completing the following wizard pages: **External FQDNs**, **Define the internal IP address**, and **Define the external IP address**.</span></span>
    
6. <span data-ttu-id="d4a62-123">На странице **Определение сервера следующего прыжка** выберите директор для следующего прыжка устаревшего пограничного пула.</span><span class="sxs-lookup"><span data-stu-id="d4a62-123">On the **Define the next hop server** page, select the Director for the next hop of the legacy Edge pool.</span></span> 
    
     ![Диалоговое окно "определение следующего прыжка"](../media/migration_ocs_topo_edgepool_page7.JPG)
  
7. <span data-ttu-id="d4a62-125">На странице " **сопоставление интерфейсных серверов или пулов-посредников** " не связывайте пул с этим пограничным пулом в данный момент.</span><span class="sxs-lookup"><span data-stu-id="d4a62-125">On the **Associate Front End or Mediation pools** page, do not associate a pool with this Edge pool at this time.</span></span> <span data-ttu-id="d4a62-126">Внешний трафик мультимедиа в настоящее время направляется через устаревший пограничный сервер.</span><span class="sxs-lookup"><span data-stu-id="d4a62-126">External media traffic is currently routed through the legacy Edge Server.</span></span> <span data-ttu-id="d4a62-127">Этот параметр настраивается на более позднем этапе миграции.</span><span class="sxs-lookup"><span data-stu-id="d4a62-127">This setting will be configured in a later phase of migration.</span></span> 
    
     ![Диалоговое окно "Связывание интерфейсных пулов"](../media/migration_ocs_topo_edgepool_page8.JPG)
  
8. <span data-ttu-id="d4a62-129">Нажмите кнопку **Готово**, а затем **опубликуйте** топологию.</span><span class="sxs-lookup"><span data-stu-id="d4a62-129">Click **Finish**, and then **Publish** the topology.</span></span> 
    
9. <span data-ttu-id="d4a62-130">Выполните действия, описанные в документации по развертыванию, чтобы установить файлы на новый пограничный сервер, настроить сертификаты и запустить службы.</span><span class="sxs-lookup"><span data-stu-id="d4a62-130">Follow the steps in the Deployment documentation to install the files on the new Edge Server, configure certificates, and start the services.</span></span> 
<!-- [Install Edge Servers for Skype for Business Server 2019](../deployment/deploying-external-user-access/install-edge-servers.md) in -->
    
<span data-ttu-id="d4a62-131">Очень важно следовать рекомендациям, изложенным в разделах документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="d4a62-131">It's very important that you follow the guidelines in the topics in the Deployment documentation.</span></span> <span data-ttu-id="d4a62-132">В этом разделе приводятся только некоторые указания по параметрам конфигурации при установке данных серверных ролей.</span><span class="sxs-lookup"><span data-stu-id="d4a62-132">This section merely provided some guidance on configuration settings when installing these server roles.</span></span> 
<!-- [Deploying external user access in Skype for Business Server 2019](../deployment/deploying-external-user-access/deploying-external-user-access.md) -->
  
<span data-ttu-id="d4a62-133">Теперь необходимо развернуть устаревший пограничный сервер параллельно с развертыванием пограничного сервера Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="d4a62-133">You should now have a legacy Edge Server deployed in parallel with a Skype for Business Server 2019 Edge server deployment.</span></span> <span data-ttu-id="d4a62-134">Перед переходом на следующий этап убедитесь, что оба развертывания функционируют должным образом, службы запущены и вы можете осуществлять управление каждым развертыванием.</span><span class="sxs-lookup"><span data-stu-id="d4a62-134">Verify that both deployments are running properly, services are started, and you can administer each deployment prior to moving to the next phase.</span></span> 
  

