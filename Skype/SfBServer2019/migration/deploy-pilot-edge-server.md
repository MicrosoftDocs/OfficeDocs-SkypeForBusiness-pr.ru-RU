---
title: Развертывание пилотного пограничного сервера
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: В этом разделе рассматриваются параметры конфигурации, которые следует обратить внимание перед развертыванием вашей Скайп Business Server 2019 пограничного сервера. Процессы развертывания и настройки для Скайп для Business Server 2019 очень похожи на Скайп для Business Server 2015. В данном разделе рассматриваются только ключевые моменты, которые следует рассматривать как часть развертывания пилотного пула. Подробное описание действий см развертывание доступа внешних пользователей в Скайп для Business Server 2019 в документации по развертыванию, которая описывает процесс развертывания, а также предоставляет сведения о конфигурации для доступа внешних пользователей.
ms.openlocfilehash: 3ae1508c56ac3240cfb9904415090ff1bdf18677
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2018
ms.locfileid: "25029862"
---
# <a name="deploy-pilot-edge-server"></a><span data-ttu-id="f6c1d-106">Развертывание пилотного пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="f6c1d-106">Deploy pilot Edge Server</span></span>

<span data-ttu-id="f6c1d-107">В этом разделе рассматриваются параметры конфигурации, которые вам следует знать перед развертыванием вашей Скайп Business Server 2019 пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="f6c1d-107">This topic highlights configuration settings you should be aware of before deploying your Skype for Business Server 2019 Edge Server.</span></span> <span data-ttu-id="f6c1d-108">Процессы развертывания и настройки для Скайп для Business Server 2019 очень похожи на Скайп для Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="f6c1d-108">The deployment and configuration processes for Skype for Business Server 2019 are very similar to Skype for Business Server 2015.</span></span> <span data-ttu-id="f6c1d-109">В данном разделе рассматриваются только ключевые моменты, которые следует рассматривать как часть развертывания пилотного пула.</span><span class="sxs-lookup"><span data-stu-id="f6c1d-109">This section only highlights key points you should consider as part of your pilot pool deployment.</span></span> <!-- For detailed steps, see 
 [Deploying external user access in Skype for Business Server 2019](../deployment/deploying-external-user-access/deploying-external-user-access.md) in the Deployment documentation, which describes the deployment process and also gives configuration information for external user access.  -->
  
<span data-ttu-id="f6c1d-110">При работе с мастером **Определение нового пограничного пула** , просмотрите параметры ключа конфигурации показано на следующем этапе.</span><span class="sxs-lookup"><span data-stu-id="f6c1d-110">As you navigate through the **Define New Edge Pool** wizard, review the key configuration settings shown in the following steps.</span></span> <span data-ttu-id="f6c1d-111">Обратите внимание, что отображаются только несколько страниц мастер **Определение нового пограничного пула** .</span><span class="sxs-lookup"><span data-stu-id="f6c1d-111">Note that only a few pages of the **Define New Edge Pool** wizard are shown.</span></span> 
  
### <a name="to-define-an-edge-pool"></a><span data-ttu-id="f6c1d-112">Определение пограничного пула</span><span class="sxs-lookup"><span data-stu-id="f6c1d-112">To define an Edge Pool</span></span>

1. <span data-ttu-id="f6c1d-113">Войдите на компьютер, где установлен построитель топологий, с использованием учетной записи, входящей в группу администраторов домена и группу RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="f6c1d-113">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>
    
2. <span data-ttu-id="f6c1d-114">Перейдите к Скайп для узла Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="f6c1d-114">Navigate to the Skype for Business Server 2019 node.</span></span> <span data-ttu-id="f6c1d-115">Щелкните правой кнопкой мыши **пограничные пулы**и выберите команду **новый пограничный пул**.</span><span class="sxs-lookup"><span data-stu-id="f6c1d-115">Right-click **Edge pools**, and click **New Edge pool**.</span></span>
    
     ![Диалоговое окно нового пограничного пула](../media/migration_ocs_topo_edgepool_page1.JPG)
  
3. <span data-ttu-id="f6c1d-117">Пограничный пул может быть **пул на нескольких компьютерах** или **пул из одного компьютера**.</span><span class="sxs-lookup"><span data-stu-id="f6c1d-117">An Edge pool can be a **Multiple computer pool** or **Single computer pool**.</span></span>
    
     ![Диалоговое окно полное доменное имя пограничного пула](../media/migration_ocs_topo_edgepool_page2.JPG)
  
4. <span data-ttu-id="f6c1d-119">На странице " **Выбор компонентов** " не следует включать федерации или федерации XMPP.</span><span class="sxs-lookup"><span data-stu-id="f6c1d-119">On the **Select features** page, do not enable federation or XMPP federation.</span></span> <span data-ttu-id="f6c1d-120">Федерации и федерации XMPP оба в настоящее время направляются через устаревшего пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="f6c1d-120">Federation and XMPP federation are both currently routed through the legacy Edge Server.</span></span> <span data-ttu-id="f6c1d-121">Эти функции будет настраиваться в более позднем этапе миграции.</span><span class="sxs-lookup"><span data-stu-id="f6c1d-121">These features will be configured in a later phase of migration.</span></span> 

  
5. <span data-ttu-id="f6c1d-122">Продолжение выполнения на следующих страницах мастера: **Внешние полные доменные имена**, **Определение внутреннего IP-адреса**и **Определение внешнего IP-адреса**.</span><span class="sxs-lookup"><span data-stu-id="f6c1d-122">Continue completing the following wizard pages: **External FQDNs**, **Define the internal IP address**, and **Define the external IP address**.</span></span>
    
6. <span data-ttu-id="f6c1d-123">На странице **Определение сервера следующего прыжка** установите для следующего прыжка старого пограничного пула директора.</span><span class="sxs-lookup"><span data-stu-id="f6c1d-123">On the **Define the next hop server** page, select the Director for the next hop of the legacy Edge pool.</span></span> 
    
     ![Диалоговое окно следующего прыжка](../media/migration_ocs_topo_edgepool_page7.JPG)
  
7. <span data-ttu-id="f6c1d-125">На странице **связать переднего плана или пулы-посредники** не сопоставляйте пул с этого пограничного пула в данный момент.</span><span class="sxs-lookup"><span data-stu-id="f6c1d-125">On the **Associate Front End or Mediation pools** page, do not associate a pool with this Edge pool at this time.</span></span> <span data-ttu-id="f6c1d-126">Внешний носитель трафика в настоящее время направляются через устаревшего пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="f6c1d-126">External media traffic is currently routed through the legacy Edge Server.</span></span> <span data-ttu-id="f6c1d-127">Этот параметр настраивается в более позднем этапе миграции.</span><span class="sxs-lookup"><span data-stu-id="f6c1d-127">This setting will be configured in a later phase of migration.</span></span> 
    
     ![Связывание диалоговое окно пулов переднего плана](../media/migration_ocs_topo_edgepool_page8.JPG)
  
8. <span data-ttu-id="f6c1d-129">Нажмите кнопку **Готово**, а затем **Опубликовать** эту топологию.</span><span class="sxs-lookup"><span data-stu-id="f6c1d-129">Click **Finish**, and then **Publish** the topology.</span></span> 
    
9. <span data-ttu-id="f6c1d-130">Следуйте указаниям в документации по развертыванию, чтобы установить файлы на новом сервере пограничного сервера, настроить сертификаты и запустить службы.</span><span class="sxs-lookup"><span data-stu-id="f6c1d-130">Follow the steps in the Deployment documentation to install the files on the new Edge Server, configure certificates, and start the services.</span></span> 
<!-- [Install Edge Servers for Skype for Business Server 2019](../deployment/deploying-external-user-access/install-edge-servers.md) in -->
    
<span data-ttu-id="f6c1d-131">Очень важно следовать правилам разделов в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="f6c1d-131">It's very important that you follow the guidelines in the topics in the Deployment documentation.</span></span> <span data-ttu-id="f6c1d-132">В этом разделе просто рассматриваются некоторые рекомендации параметров конфигурации в при установке ролей сервера.</span><span class="sxs-lookup"><span data-stu-id="f6c1d-132">This section merely provided some guidance on configuration settings when installing these server roles.</span></span> 
<!-- [Deploying external user access in Skype for Business Server 2019](../deployment/deploying-external-user-access/deploying-external-user-access.md) -->
  
<span data-ttu-id="f6c1d-133">У вас должна получиться устаревшего пограничного сервера развертывания параллельно с Скайп для развертывания Business Server 2019 пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="f6c1d-133">You should now have a legacy Edge Server deployed in parallel with a Skype for Business Server 2019 Edge server deployment.</span></span> <span data-ttu-id="f6c1d-134">Убедитесь, что оба развертываний работают должным образом, запущены ли службы, и можно выполнять задачи администрирования каждое развертывание перед переносом к следующему этапу.</span><span class="sxs-lookup"><span data-stu-id="f6c1d-134">Verify that both deployments are running properly, services are started, and you can administer each deployment prior to moving to the next phase.</span></span> 
  

