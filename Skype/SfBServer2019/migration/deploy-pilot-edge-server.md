---
title: Развертывание пилотного пограничного сервера
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: В этом разделе описываются параметры конфигурации, которые следует знать перед развертыванием пограничного сервера Skype для бизнеса Server 2019. Процессы развертывания и настройки в Skype для бизнеса Server 2019 очень похожи на Skype для бизнеса Server 2015. В этом разделе выделены только ключевые моменты, которые следует принимать во время развертывания пилотного пула. Подробные инструкции можно найти в статье Развертывание внешних пользователей Access в Skype для бизнеса Server 2019 в документации по развертыванию, в котором описан процесс развертывания, а также сведения о конфигурации для доступа внешних пользователей.
ms.openlocfilehash: c2beb22e2cce608b692884ad9b49fef40cb87058
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813657"
---
# <a name="deploy-pilot-edge-server"></a><span data-ttu-id="b364a-106">Развертывание пилотного пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="b364a-106">Deploy pilot Edge Server</span></span>

<span data-ttu-id="b364a-107">В этом разделе описываются параметры конфигурации, которые следует знать перед развертыванием пограничного сервера Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="b364a-107">This topic highlights configuration settings you should be aware of before deploying your Skype for Business Server 2019 Edge Server.</span></span> <span data-ttu-id="b364a-108">Процессы развертывания и настройки в Skype для бизнеса Server 2019 очень похожи на Skype для бизнеса Server 2015.</span><span class="sxs-lookup"><span data-stu-id="b364a-108">The deployment and configuration processes for Skype for Business Server 2019 are very similar to Skype for Business Server 2015.</span></span> <span data-ttu-id="b364a-109">В этом разделе выделены только ключевые моменты, которые следует принимать во время развертывания пилотного пула.</span><span class="sxs-lookup"><span data-stu-id="b364a-109">This section only highlights key points you should consider as part of your pilot pool deployment.</span></span> <!-- For detailed steps, see 
 [Deploying external user access in Skype for Business Server 2019](../deployment/deploying-external-user-access/deploying-external-user-access.md) in the Deployment documentation, which describes the deployment process and also gives configuration information for external user access.  -->
  
<span data-ttu-id="b364a-110">При переходе по экрану **Определение нового пула Edge** Просмотрите основные параметры конфигурации, описанные ниже.</span><span class="sxs-lookup"><span data-stu-id="b364a-110">As you navigate through the **Define New Edge Pool** wizard, review the key configuration settings shown in the following steps.</span></span> <span data-ttu-id="b364a-111">Обратите внимание, что показаны только несколько страниц мастера **Определение нового пула Edge** .</span><span class="sxs-lookup"><span data-stu-id="b364a-111">Note that only a few pages of the **Define New Edge Pool** wizard are shown.</span></span> 
  
### <a name="to-define-an-edge-pool"></a><span data-ttu-id="b364a-112">Определение пограничного пула</span><span class="sxs-lookup"><span data-stu-id="b364a-112">To define an Edge Pool</span></span>

1. <span data-ttu-id="b364a-113">Войдите на компьютер, где установлен построитель топологий, с использованием учетной записи, входящей в группу администраторов домена и группу RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="b364a-113">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>
    
2. <span data-ttu-id="b364a-114">Перейдите на узел 2019 в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="b364a-114">Navigate to the Skype for Business Server 2019 node.</span></span> <span data-ttu-id="b364a-115">Щелкните правой кнопкой мыши пункт **Пулы кромок**и выберите команду **создать пул пограничных серверов**.</span><span class="sxs-lookup"><span data-stu-id="b364a-115">Right-click **Edge pools**, and click **New Edge pool**.</span></span>
    
     ![Диалоговое окно "определение нового пула Edge"](../media/migration_ocs_topo_edgepool_page1.JPG)
  
3. <span data-ttu-id="b364a-117">Граничный пул может представлять собой **несколько групп компьютеров** или **один пул компьютеров**.</span><span class="sxs-lookup"><span data-stu-id="b364a-117">An Edge pool can be a **Multiple computer pool** or **Single computer pool**.</span></span>
    
     ![Диалоговое окно "Определение полного доменного имени" для пула Edge](../media/migration_ocs_topo_edgepool_page2.JPG)
  
4. <span data-ttu-id="b364a-119">На странице **Выбор компонентов** не включайте Федерацию или КСМПП Федерация.</span><span class="sxs-lookup"><span data-stu-id="b364a-119">On the **Select features** page, do not enable federation or XMPP federation.</span></span> <span data-ttu-id="b364a-120">Федерация Федерации и КСМПП в настоящее время пересылаются через старый сервер пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="b364a-120">Federation and XMPP federation are both currently routed through the legacy Edge Server.</span></span> <span data-ttu-id="b364a-121">Эти функции будут настроены на более поздней стадии миграции.</span><span class="sxs-lookup"><span data-stu-id="b364a-121">These features will be configured in a later phase of migration.</span></span> 

  
5. <span data-ttu-id="b364a-122">Продолжайте выполнение следующих страниц мастера: **Внешние полные доменные имена**, **Определите внутренний IP-адрес**и **Определите внешний IP-адрес**.</span><span class="sxs-lookup"><span data-stu-id="b364a-122">Continue completing the following wizard pages: **External FQDNs**, **Define the internal IP address**, and **Define the external IP address**.</span></span>
    
6. <span data-ttu-id="b364a-123">На странице **Определение сервера следующего прыжка** выберите режиссера для следующего прыжка пула из устаревшего Edge.</span><span class="sxs-lookup"><span data-stu-id="b364a-123">On the **Define the next hop server** page, select the Director for the next hop of the legacy Edge pool.</span></span> 
    
     ![Диалоговое окно «Определение следующего прыжка»](../media/migration_ocs_topo_edgepool_page7.JPG)
  
7. <span data-ttu-id="b364a-125">На странице " **сопоставление интерфейсов и пулов** ресурсов" не сопоставлены пул с этим пулом Edge.</span><span class="sxs-lookup"><span data-stu-id="b364a-125">On the **Associate Front End or Mediation pools** page, do not associate a pool with this Edge pool at this time.</span></span> <span data-ttu-id="b364a-126">Внешний трафик мультимедиа в настоящее время пересылается через старый сервер пограничного устройства.</span><span class="sxs-lookup"><span data-stu-id="b364a-126">External media traffic is currently routed through the legacy Edge Server.</span></span> <span data-ttu-id="b364a-127">Этот параметр будет настроен на более поздней стадии миграции.</span><span class="sxs-lookup"><span data-stu-id="b364a-127">This setting will be configured in a later phase of migration.</span></span> 
    
     ![Диалоговое окно «связывание внешних пулов»](../media/migration_ocs_topo_edgepool_page8.JPG)
  
8. <span data-ttu-id="b364a-129">Нажмите кнопку **Готово**, а затем **опубликуйте** топологию.</span><span class="sxs-lookup"><span data-stu-id="b364a-129">Click **Finish**, and then **Publish** the topology.</span></span> 
    
9. <span data-ttu-id="b364a-130">Выполните действия, описанные в документации по развертыванию, чтобы установить файлы на новый пограничный сервер, настроить сертификаты и запустить службы.</span><span class="sxs-lookup"><span data-stu-id="b364a-130">Follow the steps in the Deployment documentation to install the files on the new Edge Server, configure certificates, and start the services.</span></span> 
<!-- [Install Edge Servers for Skype for Business Server 2019](../deployment/deploying-external-user-access/install-edge-servers.md) in -->
    
<span data-ttu-id="b364a-131">Очень важно следовать рекомендациям, изложенным в разделе Документация по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="b364a-131">It's very important that you follow the guidelines in the topics in the Deployment documentation.</span></span> <span data-ttu-id="b364a-132">В этом разделе приведены рекомендации по настройке конфигурации при установке этих ролей сервера.</span><span class="sxs-lookup"><span data-stu-id="b364a-132">This section merely provided some guidance on configuration settings when installing these server roles.</span></span> 
<!-- [Deploying external user access in Skype for Business Server 2019](../deployment/deploying-external-user-access/deploying-external-user-access.md) -->
  
<span data-ttu-id="b364a-133">Теперь у вас должен быть параллельный развертывание устаревшего пограничного сервера при развертывании сервера Edge в Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="b364a-133">You should now have a legacy Edge Server deployed in parallel with a Skype for Business Server 2019 Edge server deployment.</span></span> <span data-ttu-id="b364a-134">Убедитесь, что оба развертывания выполняются правильно, службы запущены и вы можете администрировать каждое развертывание перед переходом к следующему этапу.</span><span class="sxs-lookup"><span data-stu-id="b364a-134">Verify that both deployments are running properly, services are started, and you can administer each deployment prior to moving to the next phase.</span></span> 
  

