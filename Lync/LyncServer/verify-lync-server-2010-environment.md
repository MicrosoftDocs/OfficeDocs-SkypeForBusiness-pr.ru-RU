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
ms.openlocfilehash: 72b04170df1a616aec595f72dce74cd15e8059b0
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42188952"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="verify-lync-server-2010-environment"></a><span data-ttu-id="3c0cb-102">Проверка среды Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="3c0cb-102">Verify Lync Server 2010 environment</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3c0cb-103">_**Последнее изменение темы:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="3c0cb-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="3c0cb-104">Перед развертыванием Lync Server 2013 в режиме сосуществования с Lync Server 2010 необходимо убедиться, что службы Lync Server 2010 настроены и запущены.</span><span class="sxs-lookup"><span data-stu-id="3c0cb-104">Before deploying Lync Server 2013 in a coexistence state with Lync Server 2010, you need to verify that Lync Server 2010 services have been configured and started.</span></span> <span data-ttu-id="3c0cb-105">Важно определить ключевые службы и функции, которые существуют в устаревшей среде, прежде чем развертывать пилотный пул Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3c0cb-105">It is important to identify key services and features that exist in your legacy environment, prior to deploying a Lync Server 2013 pilot pool.</span></span> <span data-ttu-id="3c0cb-106">Перед развертыванием Microsoft Lync Server 2013 XMPP в состоянии сосуществования с развертыванием устаревшей версии XMPP необходимо убедиться, что устаревшие службы XMPP настроены и запущены, и определить, какой федеративный партнер поддерживает конфигурацию прежних версий XMPP.</span><span class="sxs-lookup"><span data-stu-id="3c0cb-106">Before deploying Microsoft Lync Server 2013 XMPP in a coexistence state with a legacy XMPP deployment, you need to verify the legacy XMPP services have been configured and started, and identify which federated partner the legacy XMPP configuration is supporting.</span></span> <span data-ttu-id="3c0cb-107">Проверка развертывания унаследованного сервера Lync Server 2010 включает следующие компоненты:</span><span class="sxs-lookup"><span data-stu-id="3c0cb-107">Verifying your legacy Lync Server 2010 deployment entails the following:</span></span>

  - <span data-ttu-id="3c0cb-108">Проверка запуска служб Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="3c0cb-108">Verifying the Lync Server 2010 services are started</span></span>

  - <span data-ttu-id="3c0cb-109">Просмотр топологии и пользователей в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="3c0cb-109">Reviewing the topology and users in Lync Server 2010.</span></span>

  - <span data-ttu-id="3c0cb-110">проверку параметров федерации и пограничных серверов;</span><span class="sxs-lookup"><span data-stu-id="3c0cb-110">Verifying the federation and Edge server settings.</span></span>

  - <span data-ttu-id="3c0cb-111">проверку служб XMPP и федеративных партнеров.</span><span class="sxs-lookup"><span data-stu-id="3c0cb-111">Verifying XMPP services and federated partners.</span></span>

<span data-ttu-id="3c0cb-112">**Проверка запуска служб Lync Server 2010**</span><span class="sxs-lookup"><span data-stu-id="3c0cb-112">**Verify Lync Server 2010 Services are started**</span></span>

1.  <span data-ttu-id="3c0cb-113">На сервере переднего плана Lync Server 2010 перейдите к компоненту "Администрирование\\служб".</span><span class="sxs-lookup"><span data-stu-id="3c0cb-113">From the Lync Server 2010 Front End Server, navigate to the Administrative Tools\\Services applet.</span></span>

2.  <span data-ttu-id="3c0cb-114">Убедитесь, что на сервере переднего плана запущены следующие службы:</span><span class="sxs-lookup"><span data-stu-id="3c0cb-114">Verify that the following services are running on the Front End Server:</span></span>
    
    <span data-ttu-id="3c0cb-115">![Список служб, запущенных на сервере переднего плана](images/JJ205231.639f2729-b759-4d8e-b4ad-59d7f68adcd2(OCS.15).jpg "Список служб, запущенных на сервере переднего плана")</span><span class="sxs-lookup"><span data-stu-id="3c0cb-115">![List of services running on Front End Server](images/JJ205231.639f2729-b759-4d8e-b4ad-59d7f68adcd2(OCS.15).jpg "List of services running on Front End Server")</span></span>

<span data-ttu-id="3c0cb-116">**Проверка топологии Lync Server 2010 в панели управления Lync Server**</span><span class="sxs-lookup"><span data-stu-id="3c0cb-116">**Review the Lync Server 2010 topology in Lync Server Control Panel**</span></span>

1.  <span data-ttu-id="3c0cb-117">Войдите на сервер переднего плана с использованием учетной записи, входящей в группу RTCUniversalServerAdmins или связанной с административной ролью CsAdministrator или CsUserAdministrator.</span><span class="sxs-lookup"><span data-stu-id="3c0cb-117">Log on to the Front End Server with an account that is a member of the RTCUniversalServerAdmins group or a member of the CsAdministrator or CsUserAdministrator administrative role.</span></span>

2.  <span data-ttu-id="3c0cb-118">Откройте панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="3c0cb-118">Open the Lync Server Control Panel.</span></span>

3.  <span data-ttu-id="3c0cb-119">Выберите элемент **Топология**.</span><span class="sxs-lookup"><span data-stu-id="3c0cb-119">Select **Topology**.</span></span> <span data-ttu-id="3c0cb-120">Убедитесь, что указаны различные серверы в развертывании Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="3c0cb-120">Verify that the various servers in your Lync Server 2010 deployment are listed.</span></span>
    
    <span data-ttu-id="3c0cb-121">![Страница топология панели управления Lync Server 2010](images/JJ205231.338ce4fb-2162-4176-a249-ec4ae021fa6a(OCS.15).jpg "Страница топология панели управления Lync Server 2010")</span><span class="sxs-lookup"><span data-stu-id="3c0cb-121">![Lync Server 2010 Control Panel topology page](images/JJ205231.338ce4fb-2162-4176-a249-ec4ae021fa6a(OCS.15).jpg "Lync Server 2010 Control Panel topology page")</span></span>

<span data-ttu-id="3c0cb-122">**Просмотр пользователей Lync Server 2010 в панели управления Lync Server**</span><span class="sxs-lookup"><span data-stu-id="3c0cb-122">**To review Lync Server 2010 users in Lync Server Control Panel**</span></span>

1.  <span data-ttu-id="3c0cb-123">Откройте панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="3c0cb-123">Open the Lync Server Control Panel.</span></span>

2.  <span data-ttu-id="3c0cb-124">Выберите элемент **Пользователи** и нажмите кнопку **Find** (Поиск).</span><span class="sxs-lookup"><span data-stu-id="3c0cb-124">Select **Users** and then click **Find**.</span></span>

3.  <span data-ttu-id="3c0cb-125">Убедитесь, что столбец **пул регистратора** указывает на пул Lync Server 2010 для каждого пользователя в списке.</span><span class="sxs-lookup"><span data-stu-id="3c0cb-125">Verify that the **Registrar Pool** column points to the Lync Server 2010 pool for each user listed.</span></span>
    
    <span data-ttu-id="3c0cb-126">![Список пользователей в панели управления Lync Server 2010](images/JJ205231.a9378c40-7a52-4c78-ad83-1463847c9edb(OCS.15).jpg "Список пользователей в панели управления Lync Server 2010")</span><span class="sxs-lookup"><span data-stu-id="3c0cb-126">![Lync Server 2010 Control Panel listing users](images/JJ205231.a9378c40-7a52-4c78-ad83-1463847c9edb(OCS.15).jpg "Lync Server 2010 Control Panel listing users")</span></span>

<span data-ttu-id="3c0cb-127">**Проверка параметров пограничного сервера Lync Server 2010 и параметров Федерации**</span><span class="sxs-lookup"><span data-stu-id="3c0cb-127">**To verify Lync Server 2010 Edge and Federation Settings**</span></span>

1.  <span data-ttu-id="3c0cb-128">Запустите построитель топологий.</span><span class="sxs-lookup"><span data-stu-id="3c0cb-128">Start Topology Builder.</span></span>

2.  <span data-ttu-id="3c0cb-129">Выберите пункт **Download Topology from existing deployment** (Загрузить топологию из существующего развертывания).</span><span class="sxs-lookup"><span data-stu-id="3c0cb-129">Select **Download Topology from existing deployment**.</span></span>

3.  <span data-ttu-id="3c0cb-130">Выберите имя файла и сохраните топологию в файле с типом TBXML по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="3c0cb-130">Choose a file name and save the topology with the default .tbxml file type.</span></span>

4.  <span data-ttu-id="3c0cb-131">Разверните узел Lync Server 2010, чтобы отобразить различные роли сервера в развертывании.</span><span class="sxs-lookup"><span data-stu-id="3c0cb-131">Expand the Lync Server 2010 node to reveal the various server roles in the deployment.</span></span>

5.  <span data-ttu-id="3c0cb-132">Выберите узел сайта и проверьте, установлено ли значение **Site federation route assignment** (Назначение федеративного маршрута к узлу).</span><span class="sxs-lookup"><span data-stu-id="3c0cb-132">Select the site node and verify if a **Site federation route assignment** value is set.</span></span>
    
    <span data-ttu-id="3c0cb-133">![Построитель топологий, маршрут Федерации сайтов](images/JJ205231.87de3735-af7e-4280-8d72-c42cb0ea1c05(OCS.15).jpg "Построитель топологий, маршрут Федерации сайтов")</span><span class="sxs-lookup"><span data-stu-id="3c0cb-133">![Topology Builder, Site Federation Route](images/JJ205231.87de3735-af7e-4280-8d72-c42cb0ea1c05(OCS.15).jpg "Topology Builder, Site Federation Route")</span></span>

6.  <span data-ttu-id="3c0cb-p103">Затем выберите сервер Standard Edition или интерфейсный пул Enterprise Edition. Определите, настроен ли пограничный пул для мультимедиа в разделе **Associations** (Связи).</span><span class="sxs-lookup"><span data-stu-id="3c0cb-p103">Next, select the Standard Edition Server or Enterprise Edition front end pool. Determine if an Edge pool has been configured for Media below **Associations**.</span></span>
    
    <span data-ttu-id="3c0cb-136">![Построитель топологий, демонстрирующий серверы и пулы](images/JJ205231.5ad5ea3b-b122-44dd-8968-f1147d6d45f1(OCS.15).jpg "Построитель топологий, демонстрирующий серверы и пулы")</span><span class="sxs-lookup"><span data-stu-id="3c0cb-136">![Topology Builder showing servers and pools](images/JJ205231.5ad5ea3b-b122-44dd-8968-f1147d6d45f1(OCS.15).jpg "Topology Builder showing servers and pools")</span></span>

7.  <span data-ttu-id="3c0cb-137">Наконец, выберите пограничный пул и определите, настроен ли пул следующих прыжков в разделе **Next hop selection** (Выбор следующего прыжка).</span><span class="sxs-lookup"><span data-stu-id="3c0cb-137">Finally, select the Edge pool and identify if a Next hop pool is configured below **Next hop selection**.</span></span>
    
    <span data-ttu-id="3c0cb-138">![Построитель топологий, выбор следующего прыжка](images/JJ205231.3121e723-fba7-498e-a786-bde7be1a55e2(OCS.15).jpg "Построитель топологий, выбор следующего прыжка")</span><span class="sxs-lookup"><span data-stu-id="3c0cb-138">![Topology Builder, Next hop selection](images/JJ205231.3121e723-fba7-498e-a786-bde7be1a55e2(OCS.15).jpg "Topology Builder, Next hop selection")</span></span>

<span data-ttu-id="3c0cb-139">**Проверка устаревшей конфигурации федеративного партнера XMPP**</span><span class="sxs-lookup"><span data-stu-id="3c0cb-139">**Verify legacy XMPP Federated Partner Configuration**</span></span>

1.  <span data-ttu-id="3c0cb-140">Из устаревшего сервера XMPP перейдите к апплету администрирование\\служб.</span><span class="sxs-lookup"><span data-stu-id="3c0cb-140">From the legacy XMPP server, navigate to the Administrative Tools\\Services applet.</span></span>

2.  <span data-ttu-id="3c0cb-141">Убедитесь, что служба шлюза XMPP Office Communications Server запущена.</span><span class="sxs-lookup"><span data-stu-id="3c0cb-141">Verify that the Office Communications Server XMPP Gateway service is started.</span></span>
    
    <span data-ttu-id="3c0cb-142">![Служба шлюза XMPP для Office Communications Server](images/JJ721906.23223724-3c4b-4cb9-ace2-1cab2c3c91c3(OCS.15).jpg "Служба шлюза XMPP для Office Communications Server")</span><span class="sxs-lookup"><span data-stu-id="3c0cb-142">![Office Communications Server XMPP Gateway Service](images/JJ721906.23223724-3c4b-4cb9-ace2-1cab2c3c91c3(OCS.15).jpg "Office Communications Server XMPP Gateway Service")</span></span>

</div>

<span> </span>

</div>

</div>

</div>

