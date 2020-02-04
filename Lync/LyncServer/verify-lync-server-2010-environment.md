---
title: Проверка среды Lync Server 2010
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Verify Lync Server 2010 environment
ms:assetid: bfc7c620-556a-43cd-b1ed-2c268ec2b5cc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205231(v=OCS.15)
ms:contentKeyID: 48185301
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2a871955f53515491ed09ece5e5da21ef7a9fef8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730919"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-lync-server-2010-environment"></a><span data-ttu-id="2573c-102">Проверка среды Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="2573c-102">Verify Lync Server 2010 environment</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2573c-103">_**Тема последнего изменения:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="2573c-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="2573c-104">Перед развертыванием Lync Server 2013 в состоянии сосуществования с помощью Lync Server 2010 необходимо убедиться, что службы Lync Server 2010 настроены и запущены.</span><span class="sxs-lookup"><span data-stu-id="2573c-104">Before deploying Lync Server 2013 in a coexistence state with Lync Server 2010, you need to verify that Lync Server 2010 services have been configured and started.</span></span> <span data-ttu-id="2573c-105">Важно определить ключевые службы и компоненты, которые существуют в устаревшей среде, перед развертыванием пула Lync Server 2013 Pilot.</span><span class="sxs-lookup"><span data-stu-id="2573c-105">It is important to identify key services and features that exist in your legacy environment, prior to deploying a Lync Server 2013 pilot pool.</span></span> <span data-ttu-id="2573c-106">Перед развертыванием Microsoft Lync Server 2013 КСМПП в состоянии косуществования с помощью устаревшего КСМПП развертывания необходимо убедиться, что устаревшие службы КСМПП настроены и запущены, и определить, для какого федеративного партнера поддерживается конфигурация устаревшего КСМПП.</span><span class="sxs-lookup"><span data-stu-id="2573c-106">Before deploying Microsoft Lync Server 2013 XMPP in a coexistence state with a legacy XMPP deployment, you need to verify the legacy XMPP services have been configured and started, and identify which federated partner the legacy XMPP configuration is supporting.</span></span> <span data-ttu-id="2573c-107">Проверка развертывания устаревшего сервера Lync Server 2010 включает следующие компоненты:</span><span class="sxs-lookup"><span data-stu-id="2573c-107">Verifying your legacy Lync Server 2010 deployment entails the following:</span></span>

  - <span data-ttu-id="2573c-108">Проверка того, что запущены службы Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="2573c-108">Verifying the Lync Server 2010 services are started</span></span>

  - <span data-ttu-id="2573c-109">Просмотр топологии и пользователей в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="2573c-109">Reviewing the topology and users in Lync Server 2010.</span></span>

  - <span data-ttu-id="2573c-110">Проверка параметров Федерации и пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="2573c-110">Verifying the federation and Edge server settings.</span></span>

  - <span data-ttu-id="2573c-111">Проверка служб КСМПП и федеративных партнеров.</span><span class="sxs-lookup"><span data-stu-id="2573c-111">Verifying XMPP services and federated partners.</span></span>

<span data-ttu-id="2573c-112">**Проверка того, что службы Lync Server 2010 запущены**</span><span class="sxs-lookup"><span data-stu-id="2573c-112">**Verify Lync Server 2010 Services are started**</span></span>

1.  <span data-ttu-id="2573c-113">На сервере Lync Server 2010 с интерфейсом front end перейдите к апплету\\администрирование служб.</span><span class="sxs-lookup"><span data-stu-id="2573c-113">From the Lync Server 2010 Front End Server, navigate to the Administrative Tools\\Services applet.</span></span>

2.  <span data-ttu-id="2573c-114">Убедитесь в том, что на сервере переднего плана запущены следующие службы:</span><span class="sxs-lookup"><span data-stu-id="2573c-114">Verify that the following services are running on the Front End Server:</span></span>
    
    <span data-ttu-id="2573c-115">![Список служб, запущенных на сервере переднего плана](images/JJ205231.639f2729-b759-4d8e-b4ad-59d7f68adcd2(OCS.15).jpg "Список служб, запущенных на сервере переднего плана")</span><span class="sxs-lookup"><span data-stu-id="2573c-115">![List of services running on Front End Server](images/JJ205231.639f2729-b759-4d8e-b4ad-59d7f68adcd2(OCS.15).jpg "List of services running on Front End Server")</span></span>

<span data-ttu-id="2573c-116">**Проверка топологии сервера Lync Server 2010 на панели управления Lync Server**</span><span class="sxs-lookup"><span data-stu-id="2573c-116">**Review the Lync Server 2010 topology in Lync Server Control Panel**</span></span>

1.  <span data-ttu-id="2573c-117">Войдите на сервер переднего плана с помощью учетной записи, являющейся членом группы RTCUniversalServerAdmins или членом административной роли CsAdministrator или CsUserAdministrator.</span><span class="sxs-lookup"><span data-stu-id="2573c-117">Log on to the Front End Server with an account that is a member of the RTCUniversalServerAdmins group or a member of the CsAdministrator or CsUserAdministrator administrative role.</span></span>

2.  <span data-ttu-id="2573c-118">Откройте панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="2573c-118">Open the Lync Server Control Panel.</span></span>

3.  <span data-ttu-id="2573c-119">Выберите **Topology (топология**).</span><span class="sxs-lookup"><span data-stu-id="2573c-119">Select **Topology**.</span></span> <span data-ttu-id="2573c-120">Убедитесь, что в списке развертывания Lync Server 2010 указаны различные серверы.</span><span class="sxs-lookup"><span data-stu-id="2573c-120">Verify that the various servers in your Lync Server 2010 deployment are listed.</span></span>
    
    <span data-ttu-id="2573c-121">![Страница топологии панели управления Lync Server 2010](images/JJ205231.338ce4fb-2162-4176-a249-ec4ae021fa6a(OCS.15).jpg "Страница топологии панели управления Lync Server 2010")</span><span class="sxs-lookup"><span data-stu-id="2573c-121">![Lync Server 2010 Control Panel topology page](images/JJ205231.338ce4fb-2162-4176-a249-ec4ae021fa6a(OCS.15).jpg "Lync Server 2010 Control Panel topology page")</span></span>

<span data-ttu-id="2573c-122">**Просмотр пользователей Lync Server 2010 на панели управления Lync Server**</span><span class="sxs-lookup"><span data-stu-id="2573c-122">**To review Lync Server 2010 users in Lync Server Control Panel**</span></span>

1.  <span data-ttu-id="2573c-123">Откройте панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="2573c-123">Open the Lync Server Control Panel.</span></span>

2.  <span data-ttu-id="2573c-124">Выберите пункт **Пользователи** , а затем — **найти**.</span><span class="sxs-lookup"><span data-stu-id="2573c-124">Select **Users** and then click **Find**.</span></span>

3.  <span data-ttu-id="2573c-125">Убедитесь, что столбец **пула регистратора** указывает на пул Lync Server 2010 для каждого пользователя, указанного в списке.</span><span class="sxs-lookup"><span data-stu-id="2573c-125">Verify that the **Registrar Pool** column points to the Lync Server 2010 pool for each user listed.</span></span>
    
    <span data-ttu-id="2573c-126">![Пользователи, которые заводят список пользователей Lync Server 2010 панели управления](images/JJ205231.a9378c40-7a52-4c78-ad83-1463847c9edb(OCS.15).jpg "Пользователи, которые заводят список пользователей Lync Server 2010 панели управления")</span><span class="sxs-lookup"><span data-stu-id="2573c-126">![Lync Server 2010 Control Panel listing users](images/JJ205231.a9378c40-7a52-4c78-ad83-1463847c9edb(OCS.15).jpg "Lync Server 2010 Control Panel listing users")</span></span>

<span data-ttu-id="2573c-127">**Проверка параметров EDGE и Federation Lync Server 2010**</span><span class="sxs-lookup"><span data-stu-id="2573c-127">**To verify Lync Server 2010 Edge and Federation Settings**</span></span>

1.  <span data-ttu-id="2573c-128">Запустите построитель топологии.</span><span class="sxs-lookup"><span data-stu-id="2573c-128">Start Topology Builder.</span></span>

2.  <span data-ttu-id="2573c-129">Выберите пункт **топология скачивания из существующего развертывания**.</span><span class="sxs-lookup"><span data-stu-id="2573c-129">Select **Download Topology from existing deployment**.</span></span>

3.  <span data-ttu-id="2573c-130">Выберите имя файла и сохраните топологию с типом файла Default. тбксмл.</span><span class="sxs-lookup"><span data-stu-id="2573c-130">Choose a file name and save the topology with the default .tbxml file type.</span></span>

4.  <span data-ttu-id="2573c-131">Разверните узел Lync Server 2010, чтобы увидеть различные роли сервера в развертывании.</span><span class="sxs-lookup"><span data-stu-id="2573c-131">Expand the Lync Server 2010 node to reveal the various server roles in the deployment.</span></span>

5.  <span data-ttu-id="2573c-132">Выберите узел сайта и проверьте, задано ли для него значение **назначения маршрута Федерации сайта** .</span><span class="sxs-lookup"><span data-stu-id="2573c-132">Select the site node and verify if a **Site federation route assignment** value is set.</span></span>
    
    <span data-ttu-id="2573c-133">![Построитель топологии, маршрут Федерации сайтов](images/JJ205231.87de3735-af7e-4280-8d72-c42cb0ea1c05(OCS.15).jpg "Построитель топологии, маршрут Федерации сайтов")</span><span class="sxs-lookup"><span data-stu-id="2573c-133">![Topology Builder, Site Federation Route](images/JJ205231.87de3735-af7e-4280-8d72-c42cb0ea1c05(OCS.15).jpg "Topology Builder, Site Federation Route")</span></span>

6.  <span data-ttu-id="2573c-134">Затем выберите пул переднего плана сервера стандартной версии или выпуска Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="2573c-134">Next, select the Standard Edition Server or Enterprise Edition front end pool.</span></span> <span data-ttu-id="2573c-135">Определение конфигурации пограничного пула для носителей под **связями**.</span><span class="sxs-lookup"><span data-stu-id="2573c-135">Determine if an Edge pool has been configured for Media below **Associations**.</span></span>
    
    <span data-ttu-id="2573c-136">![Построитель топологии с отображением серверов и пулов](images/JJ205231.5ad5ea3b-b122-44dd-8968-f1147d6d45f1(OCS.15).jpg "Построитель топологии с отображением серверов и пулов")</span><span class="sxs-lookup"><span data-stu-id="2573c-136">![Topology Builder showing servers and pools](images/JJ205231.5ad5ea3b-b122-44dd-8968-f1147d6d45f1(OCS.15).jpg "Topology Builder showing servers and pools")</span></span>

7.  <span data-ttu-id="2573c-137">Наконец, выберите пул EDGE и укажите, будет ли следующий пул прыжков настроен ниже **следующего прыжка**.</span><span class="sxs-lookup"><span data-stu-id="2573c-137">Finally, select the Edge pool and identify if a Next hop pool is configured below **Next hop selection**.</span></span>
    
    <span data-ttu-id="2573c-138">![Построитель топологии, выбор следующего прыжка](images/JJ205231.3121e723-fba7-498e-a786-bde7be1a55e2(OCS.15).jpg "Построитель топологии, выбор следующего прыжка")</span><span class="sxs-lookup"><span data-stu-id="2573c-138">![Topology Builder, Next hop selection](images/JJ205231.3121e723-fba7-498e-a786-bde7be1a55e2(OCS.15).jpg "Topology Builder, Next hop selection")</span></span>

<span data-ttu-id="2573c-139">**Проверка конфигурации устаревшего КСМПП федеративного партнера**</span><span class="sxs-lookup"><span data-stu-id="2573c-139">**Verify legacy XMPP Federated Partner Configuration**</span></span>

1.  <span data-ttu-id="2573c-140">Из устаревшего сервера КСМПП перейдите на вкладку Администрирование\\служб.</span><span class="sxs-lookup"><span data-stu-id="2573c-140">From the legacy XMPP server, navigate to the Administrative Tools\\Services applet.</span></span>

2.  <span data-ttu-id="2573c-141">Убедитесь, что служба шлюза Office Communications Server КСМПП запущена.</span><span class="sxs-lookup"><span data-stu-id="2573c-141">Verify that the Office Communications Server XMPP Gateway service is started.</span></span>
    
    <span data-ttu-id="2573c-142">![Служба шлюза Office Communications Server КСМПП](images/JJ721906.23223724-3c4b-4cb9-ace2-1cab2c3c91c3(OCS.15).jpg "Служба шлюза Office Communications Server КСМПП")</span><span class="sxs-lookup"><span data-stu-id="2573c-142">![Office Communications Server XMPP Gateway Service](images/JJ721906.23223724-3c4b-4cb9-ace2-1cab2c3c91c3(OCS.15).jpg "Office Communications Server XMPP Gateway Service")</span></span>

</div>

<span> </span>

</div>

</div>

</div>

