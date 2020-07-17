---
title: Проверка устаревшей среды
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
description: Перед развертыванием Skype для бизнеса Server 2019 в состоянии сосуществования необходимо убедиться, что устаревшие службы настроены и запущены. Важно определить ключевые службы и функции, которые существуют в устаревшей среде, прежде чем развертывать пилотный пул Skype для бизнеса Server 2019. Перед развертыванием Microsoft Skype для бизнеса Server 2019 XMPP в состоянии сосуществования с развертыванием устаревшей версии XMPP необходимо убедиться, что устаревшие службы XMPP настроены и запущены, и определить, какой федеративный партнер поддерживает конфигурацию устаревшей XMPP.
ms.openlocfilehash: 2600cc2e6f4fac258431bcf505af10d1f8c212fe
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/16/2020
ms.locfileid: "44751681"
---
# <a name="verify-the-legacy-environment"></a><span data-ttu-id="ae4c5-105">Проверка устаревшей среды</span><span class="sxs-lookup"><span data-stu-id="ae4c5-105">Verify the legacy environment</span></span>

<span data-ttu-id="ae4c5-106">Перед развертыванием Skype для бизнеса Server 2019 в состоянии сосуществования необходимо убедиться, что устаревшие службы настроены и запущены.</span><span class="sxs-lookup"><span data-stu-id="ae4c5-106">Before deploying Skype for Business Server 2019 in a coexistence state, you need to verify that legacy services have been configured and started.</span></span> <span data-ttu-id="ae4c5-107">Важно определить ключевые службы и функции, которые существуют в устаревшей среде перед развертыванием пула пилотного проекта Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="ae4c5-107">It is important to identify key services and features that exist in your legacy environment prior to deploying a Skype for Business Server 2019 pilot pool.</span></span> <span data-ttu-id="ae4c5-108">Перед развертыванием Microsoft Skype для бизнеса Server 2019 XMPP в режиме сосуществования с развертыванием устаревшей версии XMPP необходимо убедиться, что устаревшие службы XMPP настроены и запущены, и определить, какой федеративный партнер поддерживает конфигурацию устаревшей XMPP.</span><span class="sxs-lookup"><span data-stu-id="ae4c5-108">Before deploying Microsoft Skype for Business Server 2019 XMPP in a coexistence state with a legacy XMPP deployment, you need to verify that the legacy XMPP services have been configured and started, and identify which federated partner the legacy XMPP configuration is supporting.</span></span> <span data-ttu-id="ae4c5-109">Проверка развертывания прежних версий включает следующие компоненты:</span><span class="sxs-lookup"><span data-stu-id="ae4c5-109">Verifying your legacy deployment entails the following:</span></span>
  
- <span data-ttu-id="ae4c5-110">Проверка того, что службы прежних версий запущены</span><span class="sxs-lookup"><span data-stu-id="ae4c5-110">Verifying that the legacy services are started</span></span>
    
- <span data-ttu-id="ae4c5-111">Просмотр топологии и пользователей</span><span class="sxs-lookup"><span data-stu-id="ae4c5-111">Reviewing the topology and users</span></span>
    
- <span data-ttu-id="ae4c5-112">Проверка параметров Федерации и пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="ae4c5-112">Verifying the federation and Edge server settings</span></span>
    
- <span data-ttu-id="ae4c5-113">Проверка служб XMPP и федеративных партнеров</span><span class="sxs-lookup"><span data-stu-id="ae4c5-113">Verifying XMPP services and federated partners</span></span>
    
## <a name="verify-that-legacy-services-are-started"></a><span data-ttu-id="ae4c5-114">Проверка того, что запущены устаревшие службы</span><span class="sxs-lookup"><span data-stu-id="ae4c5-114">Verify that legacy services are started</span></span>

1. <span data-ttu-id="ae4c5-115">На сервере переднего плана прежних версий перейдите в приложение администрирования средств и служб.</span><span class="sxs-lookup"><span data-stu-id="ae4c5-115">From the legacy Front End Server, navigate to the Administrative Tools\Services applet.</span></span>
    
2. <span data-ttu-id="ae4c5-116">Убедитесь, что на сервере переднего плана запущены следующие службы:</span><span class="sxs-lookup"><span data-stu-id="ae4c5-116">Verify that the following services are running on the Front End Server:</span></span>
    
     ![Список служб, запущенных на сервере переднего плана](../media/migration_lyncserver_config_w14_services.jpg)
  
## <a name="review-the-legacy-topology-in-skype-for-business-server-control-panel"></a><span data-ttu-id="ae4c5-118">Проверка устаревшей топологии в панели управления Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="ae4c5-118">Review the legacy topology in Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="ae4c5-119">Войдите на сервер переднего плана с использованием учетной записи, входящей в группу RTCUniversalServerAdmins или связанной с административной ролью CsAdministrator или CsUserAdministrator.</span><span class="sxs-lookup"><span data-stu-id="ae4c5-119">Log on to the Front End Server with an account that is a member of the RTCUniversalServerAdmins group or a member of the CsAdministrator or CsUserAdministrator administrative role.</span></span>
    
2. <span data-ttu-id="ae4c5-120">Откройте панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="ae4c5-120">Open the Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="ae4c5-121">Выберите элемент **Топология**.</span><span class="sxs-lookup"><span data-stu-id="ae4c5-121">Select **Topology**.</span></span> <span data-ttu-id="ae4c5-122">Убедитесь в том, что указаны различные серверы в устаревшем развертывании.</span><span class="sxs-lookup"><span data-stu-id="ae4c5-122">Verify that the various servers in your legacy deployment are listed.</span></span>
    
     ![Страница топологии панели управления](../media/migration_lyncserver_2010_topology.JPG)
  
## <a name="review-legacy-users-in-skype-for-business-server-control-panel"></a><span data-ttu-id="ae4c5-124">Просмотр устаревших пользователей на панели управления Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="ae4c5-124">Review legacy users in Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="ae4c5-125">Откройте панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="ae4c5-125">Open the Skype for Business Server Control Panel.</span></span>
    
2. <span data-ttu-id="ae4c5-126">Выберите пункт **Пользователи**, а затем нажмите кнопку **найти**.</span><span class="sxs-lookup"><span data-stu-id="ae4c5-126">Select **Users**, and then click **Find**.</span></span>
    
3. <span data-ttu-id="ae4c5-127">Убедитесь, что столбец **пул регистратора** указывает на пул прежних версий для каждого пользователя в списке.</span><span class="sxs-lookup"><span data-stu-id="ae4c5-127">Verify that the **Registrar Pool** column points to the legacy pool for each user listed.</span></span> 
    
     ![Список пользователей в панели управления](../media/migration_lyncserver_2010_allusers.JPG)
  
## <a name="verify-legacy-edge-and-federation-settings"></a><span data-ttu-id="ae4c5-129">Проверка устаревших пограничных параметров и параметров Федерации</span><span class="sxs-lookup"><span data-stu-id="ae4c5-129">Verify legacy Edge and federation settings</span></span>

1. <span data-ttu-id="ae4c5-130">Запустите построитель топологий.</span><span class="sxs-lookup"><span data-stu-id="ae4c5-130">Start Topology Builder.</span></span>
    
2. <span data-ttu-id="ae4c5-131">Выберите пункт **Download Topology from existing deployment** (Загрузить топологию из существующего развертывания).</span><span class="sxs-lookup"><span data-stu-id="ae4c5-131">Select **Download Topology from existing deployment**.</span></span>
    
3. <span data-ttu-id="ae4c5-132">Выберите имя файла и сохраните топологию с типом файла Default. тбксмл.</span><span class="sxs-lookup"><span data-stu-id="ae4c5-132">Choose a file name, and save the topology with the default .tbxml file type.</span></span>
    
4. <span data-ttu-id="ae4c5-133">Разверните узел устаревшие установки, чтобы отобразить различные роли сервера в развертывании.</span><span class="sxs-lookup"><span data-stu-id="ae4c5-133">Expand the legacy installs node to reveal the various server roles in the deployment.</span></span>
    
5. <span data-ttu-id="ae4c5-134">Выберите узел сайта и убедитесь, что задано значение **назначения маршрута Федерации сайта** .</span><span class="sxs-lookup"><span data-stu-id="ae4c5-134">Select the site node and verify that a **Site federation route assignment** value is set.</span></span> 
    
     ![Построитель топологий, маршрут Федерации сайтов](../media/migration_lyncserver_w14_federation.jpg)
  
6. <span data-ttu-id="ae4c5-136">Выберите пул переднего плана сервера Standard Edition или корпоративный выпуск Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="ae4c5-136">Select the Standard Edition Server or Enterprise Edition front end pool.</span></span> <span data-ttu-id="ae4c5-137">Определите, настроен ли пограничный пул для носителей ниже **связей**.</span><span class="sxs-lookup"><span data-stu-id="ae4c5-137">Determine whether an Edge pool has been configured for media below **Associations**.</span></span> 
    
     ![Построитель топологий, демонстрирующий серверы и пулы](../media/migration_lyncserver_w14_edgepool_media.jpg)
  
7. <span data-ttu-id="ae4c5-139">Выберите Пограничный пул и определите, настроен ли следующий пул прыжков при **выборе следующего прыжка**.</span><span class="sxs-lookup"><span data-stu-id="ae4c5-139">Select the Edge pool and identify whether a Next hop pool is configured below **Next hop selection**.</span></span>
    
     ![Построитель топологий, выбор следующего прыжка](../media/migration_lyncserver_w14_nexthop.jpg)
  
## <a name="verify-legacy-xmpp-federated-partner-configuration"></a><span data-ttu-id="ae4c5-141">Проверка устаревшей конфигурации федеративных партнеров XMPP</span><span class="sxs-lookup"><span data-stu-id="ae4c5-141">Verify legacy XMPP federated partner Configuration</span></span>

1. <span data-ttu-id="ae4c5-142">Из устаревшего сервера XMPP перейдите в приложение административных средств и служб.</span><span class="sxs-lookup"><span data-stu-id="ae4c5-142">From the legacy XMPP server, navigate to the Administrative Tools\Services applet.</span></span>
    
2. <span data-ttu-id="ae4c5-143">Убедитесь, что служба шлюза XMPP Office Communications Server запущена.</span><span class="sxs-lookup"><span data-stu-id="ae4c5-143">Verify that the Office Communications Server XMPP Gateway service is started.</span></span> 
    
     ![Служба шлюза XMPP для Office Communications Server](../media/migration_lyncserver_15_xmpp_legacyservicesstarted.JPG)
  

