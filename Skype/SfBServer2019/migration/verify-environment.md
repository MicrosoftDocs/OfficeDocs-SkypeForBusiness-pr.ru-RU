---
title: Проверка старой среды
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Перед развертыванием Скайп для Business Server 2019 в состоянии сосуществования, необходимо убедиться, что настройки и работы устаревших служб. Очень важно для определения основных служб и компонентов, существующих в старой среды, перед развертыванием Скайп для пилотного пула Business Server 2019. Прежде чем развертывание Скайп Microsoft Business Server 2019 XMPP в состоянии сосуществования с устаревшее развертывание XMPP, необходимо проверить, были настроены и запущены устаревших служб XMPP и определение федеративного партнера, которому устаревшей конфигурации XMPP Поддержка.
ms.openlocfilehash: 0f9812efe966d72eba1eeead9d74780f2ba16661
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2019
ms.locfileid: "30887351"
---
# <a name="verify-the-legacy-environment"></a><span data-ttu-id="1e193-105">Проверка старой среды</span><span class="sxs-lookup"><span data-stu-id="1e193-105">Verify the legacy environment</span></span>

<span data-ttu-id="1e193-106">Перед развертыванием Скайп для Business Server 2019 в состоянии сосуществования, необходимо убедиться, что настройки и работы устаревших служб.</span><span class="sxs-lookup"><span data-stu-id="1e193-106">Before deploying Skype for Business Server 2019 in a coexistence state, you need to verify that legacy services have been configured and started.</span></span> <span data-ttu-id="1e193-107">Очень важно для определения основных служб и компонентов, существующих в старой среды перед развертыванием Скайп для пилотного пула Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="1e193-107">It is important to identify key services and features that exist in your legacy environment prior to deploying a Skype for Business Server 2019 pilot pool.</span></span> <span data-ttu-id="1e193-108">Прежде чем развертывание Скайп Microsoft Business Server 2019 XMPP в состоянии сосуществования с устаревшее развертывание XMPP, необходимо убедиться, что настройки и работы устаревших служб XMPP и определение которой федеративных партнеров XMPP прежних версий Поддержка настройки.</span><span class="sxs-lookup"><span data-stu-id="1e193-108">Before deploying Microsoft Skype for Business Server 2019 XMPP in a coexistence state with a legacy XMPP deployment, you need to verify that the legacy XMPP services have been configured and started, and identify which federated partner the legacy XMPP configuration is supporting.</span></span> <span data-ttu-id="1e193-109">Проверка устаревшее развертывание влечет за собой следующее:</span><span class="sxs-lookup"><span data-stu-id="1e193-109">Verifying your legacy deployment entails the following:</span></span>
  
- <span data-ttu-id="1e193-110">Проверка того, запущены устаревших служб</span><span class="sxs-lookup"><span data-stu-id="1e193-110">Verifying that the legacy services are started</span></span>
    
- <span data-ttu-id="1e193-111">Просмотр топологии и пользователей</span><span class="sxs-lookup"><span data-stu-id="1e193-111">Reviewing the topology and users</span></span>
    
- <span data-ttu-id="1e193-112">Проверка федерации и параметров пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="1e193-112">Verifying the federation and Edge server settings</span></span>
    
- <span data-ttu-id="1e193-113">Проверку служб XMPP и федеративных партнеров</span><span class="sxs-lookup"><span data-stu-id="1e193-113">Verifying XMPP services and federated partners</span></span>
    
## <a name="verify-that-legacy-services-are-started"></a><span data-ttu-id="1e193-114">Убедитесь, что запущены службы прежних версий</span><span class="sxs-lookup"><span data-stu-id="1e193-114">Verify that legacy services are started</span></span>

1. <span data-ttu-id="1e193-115">Из устаревшего сервера переднего плана перейдите в приложение административных средств и служб.</span><span class="sxs-lookup"><span data-stu-id="1e193-115">From the legacy Front End Server, navigate to the Administrative Tools\Services applet.</span></span>
    
2. <span data-ttu-id="1e193-116">Убедитесь, что на сервере переднего плана запущены следующие службы:</span><span class="sxs-lookup"><span data-stu-id="1e193-116">Verify that the following services are running on the Front End Server:</span></span>
    
     ![Список служб, работающих на сервере переднего плана](../media/migration_lyncserver_config_w14_services.jpg)
  
## <a name="review-the-legacy-topology-in-skype-for-business-server-control-panel"></a><span data-ttu-id="1e193-118">Просмотрите прежних версий топологии в Скайп для панели управления Business Server</span><span class="sxs-lookup"><span data-stu-id="1e193-118">Review the legacy topology in Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="1e193-119">Войдите на сервер переднего плана с помощью учетной записи, являющейся членом группы RTCUniversalServerAdmins или членом административной роли CsAdministrator или CsUserAdministrator.</span><span class="sxs-lookup"><span data-stu-id="1e193-119">Log on to the Front End Server with an account that is a member of the RTCUniversalServerAdmins group or a member of the CsAdministrator or CsUserAdministrator administrative role.</span></span>
    
2. <span data-ttu-id="1e193-120">Откройте Скайп для панели управления Business Server.</span><span class="sxs-lookup"><span data-stu-id="1e193-120">Open the Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="1e193-121">Выбор **топологии**.</span><span class="sxs-lookup"><span data-stu-id="1e193-121">Select **Topology**.</span></span> <span data-ttu-id="1e193-122">Убедитесь, что включены в список различных серверах в развертывании прежних версий.</span><span class="sxs-lookup"><span data-stu-id="1e193-122">Verify that the various servers in your legacy deployment are listed.</span></span>
    
     ![Страница топологии в панели управления](../media/migration_lyncserver_2010_topology.JPG)
  
## <a name="review-legacy-users-in-skype-for-business-server-control-panel"></a><span data-ttu-id="1e193-124">Обзор устаревших пользователей в Скайп для панели управления Business Server</span><span class="sxs-lookup"><span data-stu-id="1e193-124">Review legacy users in Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="1e193-125">Откройте Скайп для панели управления Business Server.</span><span class="sxs-lookup"><span data-stu-id="1e193-125">Open the Skype for Business Server Control Panel.</span></span>
    
2. <span data-ttu-id="1e193-126">Выбор **пользователей**и нажмите кнопку **Найти**.</span><span class="sxs-lookup"><span data-stu-id="1e193-126">Select **Users**, and then click **Find**.</span></span>
    
3. <span data-ttu-id="1e193-127">Убедитесь, что столбец **Пул регистратора** указывает на устаревшем пуле для каждого перечисленного пользователя.</span><span class="sxs-lookup"><span data-stu-id="1e193-127">Verify that the **Registrar Pool** column points to the legacy pool for each user listed.</span></span> 
    
     ![Панель управления, перечисление пользователей](../media/migration_lyncserver_2010_allusers.JPG)
  
## <a name="verify-legacy-edge-and-federation-settings"></a><span data-ttu-id="1e193-129">Проверьте параметры из прежних версий и пограничного сервера федерации</span><span class="sxs-lookup"><span data-stu-id="1e193-129">Verify legacy Edge and federation settings</span></span>

1. <span data-ttu-id="1e193-130">Запустите построитель топологий.</span><span class="sxs-lookup"><span data-stu-id="1e193-130">Start Topology Builder.</span></span>
    
2. <span data-ttu-id="1e193-131">Выберите **Загрузить топологию из существующего развертывания**.</span><span class="sxs-lookup"><span data-stu-id="1e193-131">Select **Download Topology from existing deployment**.</span></span>
    
3. <span data-ttu-id="1e193-132">Выберите имя файла и сохраните топологию с типом файла tbxml по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="1e193-132">Choose a file name, and save the topology with the default .tbxml file type.</span></span>
    
4. <span data-ttu-id="1e193-133">Разверните узел устаревшим установкам, чтобы показать различные роли сервера в развертывании.</span><span class="sxs-lookup"><span data-stu-id="1e193-133">Expand the legacy installs node to reveal the various server roles in the deployment.</span></span>
    
5. <span data-ttu-id="1e193-134">Выберите узел сайта и убедитесь, что задано значение **Назначение федеративного маршрута сайта** .</span><span class="sxs-lookup"><span data-stu-id="1e193-134">Select the site node and verify that a **Site federation route assignment** value is set.</span></span> 
    
     ![Построитель топологий, федеративного маршрута сайта](../media/migration_lyncserver_w14_federation.jpg)
  
6. <span data-ttu-id="1e193-136">Выберите пул переднего плана Standard Edition или Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="1e193-136">Select the Standard Edition Server or Enterprise Edition front end pool.</span></span> <span data-ttu-id="1e193-137">Определите, настроены ли пограничный пул для мультимедиа ниже **связей**.</span><span class="sxs-lookup"><span data-stu-id="1e193-137">Determine whether an Edge pool has been configured for media below **Associations**.</span></span> 
    
     ![Отображение серверов и пулов построитель топологий](../media/migration_lyncserver_w14_edgepool_media.jpg)
  
7. <span data-ttu-id="1e193-139">Выберите пограничный пул и определите, будет ли пул следующих прыжков настроена под **Выбор узла следующего перехода**.</span><span class="sxs-lookup"><span data-stu-id="1e193-139">Select the Edge pool and identify whether a Next hop pool is configured below **Next hop selection**.</span></span>
    
     ![Построитель топологий, Выбор узла следующего перехода](../media/migration_lyncserver_w14_nexthop.jpg)
  
## <a name="verify-legacy-xmpp-federated-partner-configuration"></a><span data-ttu-id="1e193-141">Проверка устаревших федеративного партнера XMPP конфигурации</span><span class="sxs-lookup"><span data-stu-id="1e193-141">Verify legacy XMPP federated partner Configuration</span></span>

1. <span data-ttu-id="1e193-142">Из устаревшего сервера XMPP перейдите в приложение административных средств и служб.</span><span class="sxs-lookup"><span data-stu-id="1e193-142">From the legacy XMPP server, navigate to the Administrative Tools\Services applet.</span></span>
    
2. <span data-ttu-id="1e193-143">Убедитесь, что запущена служба шлюза XMPP Office Communications Server.</span><span class="sxs-lookup"><span data-stu-id="1e193-143">Verify that the Office Communications Server XMPP Gateway service is started.</span></span> 
    
     ![Служба шлюза Office Communications Server XMPP](../media/migration_lyncserver_15_xmpp_legacyservicesstarted.JPG)
  

