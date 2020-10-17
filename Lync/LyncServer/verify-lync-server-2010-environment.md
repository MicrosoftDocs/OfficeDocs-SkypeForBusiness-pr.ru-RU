---
title: Проверка среды Lync Server 2010
description: Проверка среды Lync Server 2010.
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
ms.openlocfilehash: 570fd2a9efdc90899ff4f91146b7aeb1991f6764
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48555585"
---
# <a name="verify-lync-server-2010-environment"></a><span data-ttu-id="3f685-103">Проверка среды Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="3f685-103">Verify Lync Server 2010 environment</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3f685-104">_**Последнее изменение темы:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="3f685-104">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="3f685-105">Перед развертыванием Lync Server 2013 в режиме сосуществования с Lync Server 2010 необходимо убедиться, что службы Lync Server 2010 настроены и запущены.</span><span class="sxs-lookup"><span data-stu-id="3f685-105">Before deploying Lync Server 2013 in a coexistence state with Lync Server 2010, you need to verify that Lync Server 2010 services have been configured and started.</span></span> <span data-ttu-id="3f685-106">Важно определить ключевые службы и функции, которые существуют в устаревшей среде, прежде чем развертывать пилотный пул Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3f685-106">It is important to identify key services and features that exist in your legacy environment, prior to deploying a Lync Server 2013 pilot pool.</span></span> <span data-ttu-id="3f685-107">Перед развертыванием Microsoft Lync Server 2013 XMPP в состоянии сосуществования с развертыванием устаревшей версии XMPP необходимо убедиться, что устаревшие службы XMPP настроены и запущены, и определить, какой федеративный партнер поддерживает конфигурацию прежних версий XMPP.</span><span class="sxs-lookup"><span data-stu-id="3f685-107">Before deploying Microsoft Lync Server 2013 XMPP in a coexistence state with a legacy XMPP deployment, you need to verify the legacy XMPP services have been configured and started, and identify which federated partner the legacy XMPP configuration is supporting.</span></span> <span data-ttu-id="3f685-108">Проверка развертывания унаследованного сервера Lync Server 2010 включает следующие компоненты:</span><span class="sxs-lookup"><span data-stu-id="3f685-108">Verifying your legacy Lync Server 2010 deployment entails the following:</span></span>

  - <span data-ttu-id="3f685-109">Проверка запуска служб Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="3f685-109">Verifying the Lync Server 2010 services are started</span></span>

  - <span data-ttu-id="3f685-110">Просмотр топологии и пользователей в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="3f685-110">Reviewing the topology and users in Lync Server 2010.</span></span>

  - <span data-ttu-id="3f685-111">проверку параметров федерации и пограничных серверов;</span><span class="sxs-lookup"><span data-stu-id="3f685-111">Verifying the federation and Edge server settings.</span></span>

  - <span data-ttu-id="3f685-112">проверку служб XMPP и федеративных партнеров.</span><span class="sxs-lookup"><span data-stu-id="3f685-112">Verifying XMPP services and federated partners.</span></span>

<span data-ttu-id="3f685-113">**Проверка запуска служб Lync Server 2010**</span><span class="sxs-lookup"><span data-stu-id="3f685-113">**Verify Lync Server 2010 Services are started**</span></span>

1.  <span data-ttu-id="3f685-114">На сервере переднего плана Lync Server 2010 перейдите к компоненту "Администрирование \\ служб".</span><span class="sxs-lookup"><span data-stu-id="3f685-114">From the Lync Server 2010 Front End Server, navigate to the Administrative Tools\\Services applet.</span></span>

2.  <span data-ttu-id="3f685-115">Убедитесь, что на сервере переднего плана запущены следующие службы:</span><span class="sxs-lookup"><span data-stu-id="3f685-115">Verify that the following services are running on the Front End Server:</span></span>
    
    <span data-ttu-id="3f685-116">![Список служб, запущенных на сервере переднего плана](images/JJ205231.639f2729-b759-4d8e-b4ad-59d7f68adcd2(OCS.15).jpg "Список служб, запущенных на сервере переднего плана")</span><span class="sxs-lookup"><span data-stu-id="3f685-116">![List of services running on Front End Server](images/JJ205231.639f2729-b759-4d8e-b4ad-59d7f68adcd2(OCS.15).jpg "List of services running on Front End Server")</span></span>

<span data-ttu-id="3f685-117">**Проверка топологии Lync Server 2010 в панели управления Lync Server**</span><span class="sxs-lookup"><span data-stu-id="3f685-117">**Review the Lync Server 2010 topology in Lync Server Control Panel**</span></span>

1.  <span data-ttu-id="3f685-118">Войдите на сервер переднего плана с использованием учетной записи, входящей в группу RTCUniversalServerAdmins или связанной с административной ролью CsAdministrator или CsUserAdministrator.</span><span class="sxs-lookup"><span data-stu-id="3f685-118">Log on to the Front End Server with an account that is a member of the RTCUniversalServerAdmins group or a member of the CsAdministrator or CsUserAdministrator administrative role.</span></span>

2.  <span data-ttu-id="3f685-119">Откройте панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="3f685-119">Open the Lync Server Control Panel.</span></span>

3.  <span data-ttu-id="3f685-120">Выберите элемент **Топология**.</span><span class="sxs-lookup"><span data-stu-id="3f685-120">Select **Topology**.</span></span> <span data-ttu-id="3f685-121">Убедитесь, что указаны различные серверы в развертывании Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="3f685-121">Verify that the various servers in your Lync Server 2010 deployment are listed.</span></span>
    
    <span data-ttu-id="3f685-122">![Страница топология панели управления Lync Server 2010](images/JJ205231.338ce4fb-2162-4176-a249-ec4ae021fa6a(OCS.15).jpg "Страница топология панели управления Lync Server 2010")</span><span class="sxs-lookup"><span data-stu-id="3f685-122">![Lync Server 2010 Control Panel topology page](images/JJ205231.338ce4fb-2162-4176-a249-ec4ae021fa6a(OCS.15).jpg "Lync Server 2010 Control Panel topology page")</span></span>

<span data-ttu-id="3f685-123">**Просмотр пользователей Lync Server 2010 в панели управления Lync Server**</span><span class="sxs-lookup"><span data-stu-id="3f685-123">**To review Lync Server 2010 users in Lync Server Control Panel**</span></span>

1.  <span data-ttu-id="3f685-124">Откройте панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="3f685-124">Open the Lync Server Control Panel.</span></span>

2.  <span data-ttu-id="3f685-125">Выберите элемент **Пользователи** и нажмите кнопку **Find** (Поиск).</span><span class="sxs-lookup"><span data-stu-id="3f685-125">Select **Users** and then click **Find**.</span></span>

3.  <span data-ttu-id="3f685-126">Убедитесь, что столбец **пул регистратора** указывает на пул Lync Server 2010 для каждого пользователя в списке.</span><span class="sxs-lookup"><span data-stu-id="3f685-126">Verify that the **Registrar Pool** column points to the Lync Server 2010 pool for each user listed.</span></span>
    
    <span data-ttu-id="3f685-127">![Список пользователей в панели управления Lync Server 2010](images/JJ205231.a9378c40-7a52-4c78-ad83-1463847c9edb(OCS.15).jpg "Список пользователей в панели управления Lync Server 2010")</span><span class="sxs-lookup"><span data-stu-id="3f685-127">![Lync Server 2010 Control Panel listing users](images/JJ205231.a9378c40-7a52-4c78-ad83-1463847c9edb(OCS.15).jpg "Lync Server 2010 Control Panel listing users")</span></span>

<span data-ttu-id="3f685-128">**Проверка параметров пограничного сервера Lync Server 2010 и параметров Федерации**</span><span class="sxs-lookup"><span data-stu-id="3f685-128">**To verify Lync Server 2010 Edge and Federation Settings**</span></span>

1.  <span data-ttu-id="3f685-129">Запустите построитель топологий.</span><span class="sxs-lookup"><span data-stu-id="3f685-129">Start Topology Builder.</span></span>

2.  <span data-ttu-id="3f685-130">Выберите пункт **Download Topology from existing deployment** (Загрузить топологию из существующего развертывания).</span><span class="sxs-lookup"><span data-stu-id="3f685-130">Select **Download Topology from existing deployment**.</span></span>

3.  <span data-ttu-id="3f685-131">Выберите имя файла и сохраните топологию в файле с типом TBXML по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="3f685-131">Choose a file name and save the topology with the default .tbxml file type.</span></span>

4.  <span data-ttu-id="3f685-132">Разверните узел Lync Server 2010, чтобы отобразить различные роли сервера в развертывании.</span><span class="sxs-lookup"><span data-stu-id="3f685-132">Expand the Lync Server 2010 node to reveal the various server roles in the deployment.</span></span>

5.  <span data-ttu-id="3f685-133">Выберите узел сайта и проверьте, установлено ли значение **Site federation route assignment** (Назначение федеративного маршрута к узлу).</span><span class="sxs-lookup"><span data-stu-id="3f685-133">Select the site node and verify if a **Site federation route assignment** value is set.</span></span>
    
    <span data-ttu-id="3f685-134">![Построитель топологий, маршрут Федерации сайтов](images/JJ205231.87de3735-af7e-4280-8d72-c42cb0ea1c05(OCS.15).jpg "Построитель топологий, маршрут Федерации сайтов")</span><span class="sxs-lookup"><span data-stu-id="3f685-134">![Topology Builder, Site Federation Route](images/JJ205231.87de3735-af7e-4280-8d72-c42cb0ea1c05(OCS.15).jpg "Topology Builder, Site Federation Route")</span></span>

6.  <span data-ttu-id="3f685-p103">Затем выберите сервер Standard Edition или интерфейсный пул Enterprise Edition. Определите, настроен ли пограничный пул для мультимедиа в разделе **Associations** (Связи).</span><span class="sxs-lookup"><span data-stu-id="3f685-p103">Next, select the Standard Edition Server or Enterprise Edition front end pool. Determine if an Edge pool has been configured for Media below **Associations**.</span></span>
    
    <span data-ttu-id="3f685-137">![Построитель топологий, демонстрирующий серверы и пулы](images/JJ205231.5ad5ea3b-b122-44dd-8968-f1147d6d45f1(OCS.15).jpg "Построитель топологий, демонстрирующий серверы и пулы")</span><span class="sxs-lookup"><span data-stu-id="3f685-137">![Topology Builder showing servers and pools](images/JJ205231.5ad5ea3b-b122-44dd-8968-f1147d6d45f1(OCS.15).jpg "Topology Builder showing servers and pools")</span></span>

7.  <span data-ttu-id="3f685-138">Наконец, выберите пограничный пул и определите, настроен ли пул следующих прыжков в разделе **Next hop selection** (Выбор следующего прыжка).</span><span class="sxs-lookup"><span data-stu-id="3f685-138">Finally, select the Edge pool and identify if a Next hop pool is configured below **Next hop selection**.</span></span>
    
    <span data-ttu-id="3f685-139">![Построитель топологий, выбор следующего прыжка](images/JJ205231.3121e723-fba7-498e-a786-bde7be1a55e2(OCS.15).jpg "Построитель топологий, выбор следующего прыжка")</span><span class="sxs-lookup"><span data-stu-id="3f685-139">![Topology Builder, Next hop selection](images/JJ205231.3121e723-fba7-498e-a786-bde7be1a55e2(OCS.15).jpg "Topology Builder, Next hop selection")</span></span>

<span data-ttu-id="3f685-140">**Проверка устаревшей конфигурации федеративного партнера XMPP**</span><span class="sxs-lookup"><span data-stu-id="3f685-140">**Verify legacy XMPP Federated Partner Configuration**</span></span>

1.  <span data-ttu-id="3f685-141">Из устаревшего сервера XMPP перейдите к \\ апплету администрирование служб.</span><span class="sxs-lookup"><span data-stu-id="3f685-141">From the legacy XMPP server, navigate to the Administrative Tools\\Services applet.</span></span>

2.  <span data-ttu-id="3f685-142">Убедитесь, что служба шлюза XMPP Office Communications Server запущена.</span><span class="sxs-lookup"><span data-stu-id="3f685-142">Verify that the Office Communications Server XMPP Gateway service is started.</span></span>
    
    <span data-ttu-id="3f685-143">![Служба шлюза XMPP для Office Communications Server](images/JJ721906.23223724-3c4b-4cb9-ace2-1cab2c3c91c3(OCS.15).jpg "Служба шлюза XMPP для Office Communications Server")</span><span class="sxs-lookup"><span data-stu-id="3f685-143">![Office Communications Server XMPP Gateway Service](images/JJ721906.23223724-3c4b-4cb9-ace2-1cab2c3c91c3(OCS.15).jpg "Office Communications Server XMPP Gateway Service")</span></span>

</div>

<span> </span>

</div>

</div>

</div>

