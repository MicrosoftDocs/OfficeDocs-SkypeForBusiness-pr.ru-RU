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
description: В этом разделе выделены параметры конфигурации, которые необходимо знать перед развертыванием skype для бизнеса Server 2019 Edge Server. Процессы развертывания и настройки Skype для бизнеса Server 2019 очень похожи на skype для бизнеса Server 2015. В этом разделе рассматриваются только ключевые моменты, которые следует учитывать при развертывании пилотной версии пула. Дополнительные сведения см. в статье "Развертывание доступа внешних пользователей в Skype для бизнеса Server 2019" документации по развертыванию, которая описывает процесс развертывания, а также предоставляет сведения о конфигурации для доступа внешних пользователей.
ms.openlocfilehash: 00c371b917f2649dba9011fbbce6162b153822d1
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752871"
---
# <a name="deploy-pilot-edge-server"></a><span data-ttu-id="0c5ff-106">Развертывание пилотного пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="0c5ff-106">Deploy pilot Edge Server</span></span>

<span data-ttu-id="0c5ff-107">В этом разделе выделены параметры конфигурации, которые необходимо знать перед развертыванием skype для бизнеса Server 2019 Edge Server.</span><span class="sxs-lookup"><span data-stu-id="0c5ff-107">This topic highlights configuration settings you should be aware of before deploying your Skype for Business Server 2019 Edge Server.</span></span> <span data-ttu-id="0c5ff-108">Процессы развертывания и настройки Skype для бизнеса Server 2019 очень похожи на skype для бизнеса Server 2015.</span><span class="sxs-lookup"><span data-stu-id="0c5ff-108">The deployment and configuration processes for Skype for Business Server 2019 are very similar to Skype for Business Server 2015.</span></span> <span data-ttu-id="0c5ff-109">В этом разделе рассматриваются только ключевые моменты, которые следует учитывать при развертывании пилотной версии пула.</span><span class="sxs-lookup"><span data-stu-id="0c5ff-109">This section only highlights key points you should consider as part of your pilot pool deployment.</span></span> <!-- For detailed steps, see 
 [Deploying external user access in Skype for Business Server 2019](../deployment/deploying-external-user-access/deploying-external-user-access.md) in the Deployment documentation, which describes the deployment process and also gives configuration information for external user access.  -->
  
<span data-ttu-id="0c5ff-p103">По мере перехода по страницам мастера **Определение нового пограничного пула** анализируйте основные параметры конфигурации, показанные на следующих шагах. Обратите внимание, что показано лишь несколько страниц мастера **Определение нового пограничного пула**.</span><span class="sxs-lookup"><span data-stu-id="0c5ff-p103">As you navigate through the **Define New Edge Pool** wizard, review the key configuration settings shown in the following steps. Note that only a few pages of the **Define New Edge Pool** wizard are shown.</span></span> 
  
### <a name="to-define-an-edge-pool"></a><span data-ttu-id="0c5ff-112">Определение пула</span><span class="sxs-lookup"><span data-stu-id="0c5ff-112">To define an Edge Pool</span></span>

1. <span data-ttu-id="0c5ff-113">Войдите в систему компьютера, на котором построитель топологий установлен как член группы администраторов доменов и группы RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="0c5ff-113">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>
    
2. <span data-ttu-id="0c5ff-114">Перейдите к узлу Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="0c5ff-114">Navigate to the Skype for Business Server 2019 node.</span></span> <span data-ttu-id="0c5ff-115">Щелкните правой кнопкой мыши пункт **Пограничные пулы** и выберите в контекстном меню команду **Создать пограничный пул**.</span><span class="sxs-lookup"><span data-stu-id="0c5ff-115">Right-click **Edge pools**, and click **New Edge pool**.</span></span>
    
     ![Диалоговое окно "Определение нового пула по краям"](../media/migration_ocs_topo_edgepool_page1.JPG)
  
3. <span data-ttu-id="0c5ff-117">Пограничный пул может представлять собой **Пул нескольких компьютеров** или **Пул одиночного компьютера**.</span><span class="sxs-lookup"><span data-stu-id="0c5ff-117">An Edge pool can be a **Multiple computer pool** or **Single computer pool**.</span></span>
    
     ![Диалоговое окно определения FQDN пула](../media/migration_ocs_topo_edgepool_page2.JPG)
  
4. <span data-ttu-id="0c5ff-119">На странице **Выбор компонентов** не включайте ни федерацию, ни федерацию XMPP.</span><span class="sxs-lookup"><span data-stu-id="0c5ff-119">On the **Select features** page, do not enable federation or XMPP federation.</span></span> <span data-ttu-id="0c5ff-120">Федерация и федерация XMPP в настоящее время маршруты через устаревший сервер.</span><span class="sxs-lookup"><span data-stu-id="0c5ff-120">Federation and XMPP federation are both currently routed through the legacy Edge Server.</span></span> <span data-ttu-id="0c5ff-121">Эти компоненты настраиваются на более позднем этапе миграции.</span><span class="sxs-lookup"><span data-stu-id="0c5ff-121">These features will be configured in a later phase of migration.</span></span> 

  
5. <span data-ttu-id="0c5ff-122">Продолжите заполнение следующих страниц мастера: внешние **FQDNs,** определение внутреннего **IP-адреса** и **определение внешнего IP-адреса.**</span><span class="sxs-lookup"><span data-stu-id="0c5ff-122">Continue completing the following wizard pages: **External FQDNs**, **Define the internal IP address**, and **Define the external IP address**.</span></span>
    
6. <span data-ttu-id="0c5ff-123">На странице **"Определение сервера следующего прыжка"** выберите директор для следующего прыжка устаревшего пула.</span><span class="sxs-lookup"><span data-stu-id="0c5ff-123">On the **Define the next hop server** page, select the Director for the next hop of the legacy Edge pool.</span></span> 
    
     ![Диалоговое окно "Определение следующего перехода"](../media/migration_ocs_topo_edgepool_page7.JPG)
  
7. <span data-ttu-id="0c5ff-125">На странице **"Связать пулы переднего края"** или "Пулы-посредники" не связывать пул с этим пулом в данный момент.</span><span class="sxs-lookup"><span data-stu-id="0c5ff-125">On the **Associate Front End or Mediation pools** page, do not associate a pool with this Edge pool at this time.</span></span> <span data-ttu-id="0c5ff-126">В настоящее время внешний трафик мультимедиа проходит через устаревший сервер.</span><span class="sxs-lookup"><span data-stu-id="0c5ff-126">External media traffic is currently routed through the legacy Edge Server.</span></span> <span data-ttu-id="0c5ff-127">Этот параметр настраивается на более позднем этапе миграции.</span><span class="sxs-lookup"><span data-stu-id="0c5ff-127">This setting will be configured in a later phase of migration.</span></span> 
    
     ![Диалоговое окно "Связывать пулы переднего ящика"](../media/migration_ocs_topo_edgepool_page8.JPG)
  
8. <span data-ttu-id="0c5ff-129">Нажмите **кнопку "Готово",** а **затем опубликуем** топологию.</span><span class="sxs-lookup"><span data-stu-id="0c5ff-129">Click **Finish**, and then **Publish** the topology.</span></span> 
    
9. <span data-ttu-id="0c5ff-130">Следуйте шагам в документации по развертыванию, чтобы установить файлы на новом сервере, настроить сертификаты и запустить службы.</span><span class="sxs-lookup"><span data-stu-id="0c5ff-130">Follow the steps in the Deployment documentation to install the files on the new Edge Server, configure certificates, and start the services.</span></span> 
<!-- [Install Edge Servers for Skype for Business Server 2019](../deployment/deploying-external-user-access/install-edge-servers.md) in -->
    
<span data-ttu-id="0c5ff-131">Очень важно следовать рекомендациям в темах документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="0c5ff-131">It's very important that you follow the guidelines in the topics in the Deployment documentation.</span></span> <span data-ttu-id="0c5ff-132">В этом разделе приводятся только некоторые указания по параметрам конфигурации при установке данных серверных ролей.</span><span class="sxs-lookup"><span data-stu-id="0c5ff-132">This section merely provided some guidance on configuration settings when installing these server roles.</span></span> 
<!-- [Deploying external user access in Skype for Business Server 2019](../deployment/deploying-external-user-access/deploying-external-user-access.md) -->
  
<span data-ttu-id="0c5ff-133">Теперь у вас должен быть устаревший сервер, развернутый параллельно с развертыванием сервера Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="0c5ff-133">You should now have a legacy Edge Server deployed in parallel with a Skype for Business Server 2019 Edge server deployment.</span></span> <span data-ttu-id="0c5ff-134">Перед переходом на следующий этап убедитесь, что оба развертывания функционируют должным образом, службы запущены и вы можете осуществлять управление каждым развертыванием.</span><span class="sxs-lookup"><span data-stu-id="0c5ff-134">Verify that both deployments are running properly, services are started, and you can administer each deployment prior to moving to the next phase.</span></span> 
  

