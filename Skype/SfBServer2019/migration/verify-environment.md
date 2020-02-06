---
title: Проверка устаревшей среды
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
description: Перед развертыванием Skype для бизнеса Server 2019 в состоянии сосуществования необходимо убедиться, что устаревшие службы настроены и запущены. Важно определить ключевые службы и компоненты, которые существуют в устаревшей среде, перед развертыванием пула пилотных проектов в Skype для бизнеса Server 2019. Перед развертыванием приложения Microsoft Skype для бизнеса Server 2019 КСМПП в состоянии сосуществования с помощью устаревшего КСМПП развертывания необходимо проверить, настроены ли устаревшие службы КСМПП и они запущены, а также определить, для какого федеративного партнера установлена устаревшая конфигурация КСМПП пояснитель.
ms.openlocfilehash: 34c9ecbc4fe9863c09b2648145ff46c1628ef655
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41812697"
---
# <a name="verify-the-legacy-environment"></a><span data-ttu-id="e626e-105">Проверка прежней среды</span><span class="sxs-lookup"><span data-stu-id="e626e-105">Verify the legacy environment</span></span>

<span data-ttu-id="e626e-106">Перед развертыванием Skype для бизнеса Server 2019 в состоянии сосуществования необходимо убедиться, что устаревшие службы настроены и запущены.</span><span class="sxs-lookup"><span data-stu-id="e626e-106">Before deploying Skype for Business Server 2019 in a coexistence state, you need to verify that legacy services have been configured and started.</span></span> <span data-ttu-id="e626e-107">Важно определить ключевые службы и компоненты, которые существуют в устаревшей среде перед развертыванием пула пилотных проектов в Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="e626e-107">It is important to identify key services and features that exist in your legacy environment prior to deploying a Skype for Business Server 2019 pilot pool.</span></span> <span data-ttu-id="e626e-108">Перед развертыванием приложения Microsoft Skype для бизнеса Server 2019 КСМПП в состоянии сосуществования с помощью устаревшего КСМПП развертывания необходимо убедиться в том, что устаревшие службы КСМПП настроены и запущены, а также определить, для какого федеративного партнера установлен устаревший КСМПП Поддержка конфигурации.</span><span class="sxs-lookup"><span data-stu-id="e626e-108">Before deploying Microsoft Skype for Business Server 2019 XMPP in a coexistence state with a legacy XMPP deployment, you need to verify that the legacy XMPP services have been configured and started, and identify which federated partner the legacy XMPP configuration is supporting.</span></span> <span data-ttu-id="e626e-109">Проверка развертывания устаревшего режима включает следующие компоненты:</span><span class="sxs-lookup"><span data-stu-id="e626e-109">Verifying your legacy deployment entails the following:</span></span>
  
- <span data-ttu-id="e626e-110">Проверка того, что старые службы запущены</span><span class="sxs-lookup"><span data-stu-id="e626e-110">Verifying that the legacy services are started</span></span>
    
- <span data-ttu-id="e626e-111">Просмотр топологии и пользователей</span><span class="sxs-lookup"><span data-stu-id="e626e-111">Reviewing the topology and users</span></span>
    
- <span data-ttu-id="e626e-112">Проверка параметров Федерации и пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="e626e-112">Verifying the federation and Edge server settings</span></span>
    
- <span data-ttu-id="e626e-113">Проверка служб КСМПП и федеративных партнеров</span><span class="sxs-lookup"><span data-stu-id="e626e-113">Verifying XMPP services and federated partners</span></span>
    
## <a name="verify-that-legacy-services-are-started"></a><span data-ttu-id="e626e-114">Проверка того, что запущены устаревшие службы</span><span class="sxs-lookup"><span data-stu-id="e626e-114">Verify that legacy services are started</span></span>

1. <span data-ttu-id="e626e-115">На сервере переднего плана Legacy перейдите к апплету администрирования Тулс\сервицес.</span><span class="sxs-lookup"><span data-stu-id="e626e-115">From the legacy Front End Server, navigate to the Administrative Tools\Services applet.</span></span>
    
2. <span data-ttu-id="e626e-116">Убедитесь в том, что на сервере переднего плана запущены следующие службы:</span><span class="sxs-lookup"><span data-stu-id="e626e-116">Verify that the following services are running on the Front End Server:</span></span>
    
     ![Список служб, запущенных на сервере переднего плана](../media/migration_lyncserver_config_w14_services.jpg)
  
## <a name="review-the-legacy-topology-in-skype-for-business-server-control-panel"></a><span data-ttu-id="e626e-118">Проверка устаревших топологий на панели управления в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="e626e-118">Review the legacy topology in Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="e626e-119">Войдите на сервер переднего плана с помощью учетной записи, являющейся членом группы RTCUniversalServerAdmins или членом административной роли CsAdministrator или CsUserAdministrator.</span><span class="sxs-lookup"><span data-stu-id="e626e-119">Log on to the Front End Server with an account that is a member of the RTCUniversalServerAdmins group or a member of the CsAdministrator or CsUserAdministrator administrative role.</span></span>
    
2. <span data-ttu-id="e626e-120">Откройте панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="e626e-120">Open the Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="e626e-121">Выберите **Topology (топология**).</span><span class="sxs-lookup"><span data-stu-id="e626e-121">Select **Topology**.</span></span> <span data-ttu-id="e626e-122">Убедитесь в том, что в списке устаревших развертываний указаны различные серверы.</span><span class="sxs-lookup"><span data-stu-id="e626e-122">Verify that the various servers in your legacy deployment are listed.</span></span>
    
     ![Страница топологии панели управления](../media/migration_lyncserver_2010_topology.JPG)
  
## <a name="review-legacy-users-in-skype-for-business-server-control-panel"></a><span data-ttu-id="e626e-124">Просмотр устаревших пользователей на панели управления Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="e626e-124">Review legacy users in Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="e626e-125">Откройте панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="e626e-125">Open the Skype for Business Server Control Panel.</span></span>
    
2. <span data-ttu-id="e626e-126">Выберите пункт **Пользователи**, а затем — **найти**.</span><span class="sxs-lookup"><span data-stu-id="e626e-126">Select **Users**, and then click **Find**.</span></span>
    
3. <span data-ttu-id="e626e-127">Убедитесь, что столбец **пула регистратора** указывает на пул старых пользователей для каждого пользователя в списке.</span><span class="sxs-lookup"><span data-stu-id="e626e-127">Verify that the **Registrar Pool** column points to the legacy pool for each user listed.</span></span> 
    
     ![Список пользователей на панели управления](../media/migration_lyncserver_2010_allusers.JPG)
  
## <a name="verify-legacy-edge-and-federation-settings"></a><span data-ttu-id="e626e-129">Проверка параметров унаследованного края и Федерации</span><span class="sxs-lookup"><span data-stu-id="e626e-129">Verify legacy Edge and federation settings</span></span>

1. <span data-ttu-id="e626e-130">Запустите построитель топологии.</span><span class="sxs-lookup"><span data-stu-id="e626e-130">Start Topology Builder.</span></span>
    
2. <span data-ttu-id="e626e-131">Выберите пункт **топология скачивания из существующего развертывания**.</span><span class="sxs-lookup"><span data-stu-id="e626e-131">Select **Download Topology from existing deployment**.</span></span>
    
3. <span data-ttu-id="e626e-132">Выберите имя файла и сохраните топологию с типом файла Default. тбксмл.</span><span class="sxs-lookup"><span data-stu-id="e626e-132">Choose a file name, and save the topology with the default .tbxml file type.</span></span>
    
4. <span data-ttu-id="e626e-133">Разверните узел устаревшая установка, чтобы увидеть различные роли сервера в развертывании.</span><span class="sxs-lookup"><span data-stu-id="e626e-133">Expand the legacy installs node to reveal the various server roles in the deployment.</span></span>
    
5. <span data-ttu-id="e626e-134">Выберите узел сайта и убедитесь, что для него задано значение **назначения маршрута Федерации сайта** .</span><span class="sxs-lookup"><span data-stu-id="e626e-134">Select the site node and verify that a **Site federation route assignment** value is set.</span></span> 
    
     ![Построитель топологии, маршрут Федерации сайтов](../media/migration_lyncserver_w14_federation.jpg)
  
6. <span data-ttu-id="e626e-136">Выберите стандартный сервер или пул переднего плана Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="e626e-136">Select the Standard Edition Server or Enterprise Edition front end pool.</span></span> <span data-ttu-id="e626e-137">Определите, настроен ли для пула пограничного устройства носитель для **связей**.</span><span class="sxs-lookup"><span data-stu-id="e626e-137">Determine whether an Edge pool has been configured for media below **Associations**.</span></span> 
    
     ![Построитель топологии с отображением серверов и пулов](../media/migration_lyncserver_w14_edgepool_media.jpg)
  
7. <span data-ttu-id="e626e-139">Выберите пул EDGE и укажите, будет ли следующий пул прыжков настраиваться ниже **следующего прыжка**.</span><span class="sxs-lookup"><span data-stu-id="e626e-139">Select the Edge pool and identify whether a Next hop pool is configured below **Next hop selection**.</span></span>
    
     ![Построитель топологии, выбор следующего прыжка](../media/migration_lyncserver_w14_nexthop.jpg)
  
## <a name="verify-legacy-xmpp-federated-partner-configuration"></a><span data-ttu-id="e626e-141">Проверка конфигурации устаревшего КСМПП федеративного партнера</span><span class="sxs-lookup"><span data-stu-id="e626e-141">Verify legacy XMPP federated partner Configuration</span></span>

1. <span data-ttu-id="e626e-142">Из устаревшего сервера КСМПП перейдите в приложение администрирование Тулс\сервицес.</span><span class="sxs-lookup"><span data-stu-id="e626e-142">From the legacy XMPP server, navigate to the Administrative Tools\Services applet.</span></span>
    
2. <span data-ttu-id="e626e-143">Убедитесь, что служба шлюза Office Communications Server КСМПП запущена.</span><span class="sxs-lookup"><span data-stu-id="e626e-143">Verify that the Office Communications Server XMPP Gateway service is started.</span></span> 
    
     ![Служба шлюза Office Communications Server КСМПП](../media/migration_lyncserver_15_xmpp_legacyservicesstarted.JPG)
  

