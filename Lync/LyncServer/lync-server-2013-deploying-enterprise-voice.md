---
title: 'Lync Server 2013: развертывание корпоративной голосовой связи'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deploying Enterprise Voice
ms:assetid: b5b593a6-ac30-461c-8c8c-0041e2c9ab04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412876(v=OCS.15)
ms:contentKeyID: 48185207
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ae445d954bd1be7c956d76aa48da2ad7854c6a54
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834561"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-enterprise-voice-in-lync-server-2013"></a><span data-ttu-id="e9128-102">Развертывание корпоративной голосовой связи в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e9128-102">Deploying Enterprise Voice in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e9128-103">_**Тема последнего изменения:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="e9128-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="e9128-104">Lync Server 2013, корпоративный голос является частью инфраструктуры Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e9128-104">Lync Server 2013, Enterprise Voice is part of the Lync Server 2013 infrastructure.</span></span>

<span data-ttu-id="e9128-105">Для развертывания корпоративной голосовой связи необходимо:</span><span class="sxs-lookup"><span data-stu-id="e9128-105">Deploying Enterprise Voice requires that you:</span></span>

<div id="sectionSection0" class="section">

1.  <span data-ttu-id="e9128-106">Ознакомьтесь с разделом [планирование для корпоративного голосовой связи в Lync Server 2013 в](lync-server-2013-planning-for-enterprise-voice.md) документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="e9128-106">Review the [Planning for Enterprise Voice in Lync Server 2013](lync-server-2013-planning-for-enterprise-voice.md) section of the Planning documentation.</span></span>

2.  <span data-ttu-id="e9128-107">Завершайте планы для функций и компонентов, которые развертываются вместе с этой рабочей нагрузкой.</span><span class="sxs-lookup"><span data-stu-id="e9128-107">Finalize plans for features and components to deploy with this workload.</span></span>

3.  <span data-ttu-id="e9128-108">Запустите средство планирования, чтобы спроектировать топологию, отражающую ваши решения по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="e9128-108">Run Planning Tool to design a topology that reflects your deployment decisions.</span></span>

4.  <span data-ttu-id="e9128-109">Откройте структуру топологии в построителе топологии, как описано в разделе [Определение и Настройка топологии в Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md) в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="e9128-109">Open the topology design in Topology Builder, as described in [Defining and configuring the topology in Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md) in the Deployment documentation.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="e9128-110">Установка Topology Builder входит в процесс развертывания внутреннего пула.</span><span class="sxs-lookup"><span data-stu-id="e9128-110">Installation of Topology Builder is part of the deployment process for the internal pool.</span></span> <span data-ttu-id="e9128-111">Подробности можно найти в разделе <A href="lync-server-2013-install-lync-server-administrative-tools.md">Установка средств администрирования Lync Server 2013</A> в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="e9128-111">For details, see <A href="lync-server-2013-install-lync-server-administrative-tools.md">Install Lync Server 2013 administrative tools</A> in the Deployment documentation.</span></span>

    
    </div>

<span data-ttu-id="e9128-112">Кроме того, вы должны иметь уже развернутые Lync Server, Enterprise Edition на центральных сайтах и сайтах филиалов, которые соответствуют топологии ссылок, которую вы выбираете для развертывания.</span><span class="sxs-lookup"><span data-stu-id="e9128-112">Additionally, you must have already deployed Lync Server, Enterprise Edition at central sites and branch sites that correspond to the reference topology that you choose to deploy.</span></span> <span data-ttu-id="e9128-113">Вы не можете внедрять корпоративные голосовые компоненты, пока не будет определен, опубликован и не установлен ни один из внутренних файлов, а для определения и публикации внутреннего пула необходимо использовать Topology Builder.</span><span class="sxs-lookup"><span data-stu-id="e9128-113">You can’t deploy Enterprise Voice components until you have defined, published, and installed files for at least one internal pool, and you must use Topology Builder to define and publish an internal pool.</span></span>

</div>

<div id="sectionSection1" class="section">

<div class="subSection">

<span data-ttu-id="e9128-114">Для просмотра эталонных топологий с примерами того, где разрешается развертывание ролей корпоративного голосового сервера (и их связь друг с другом и другими ролями сервера Lync Server 2013), ознакомьтесь с [эталонными топологиями в Lync server 2013](lync-server-2013-reference-topologies.md) в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="e9128-114">To view reference topologies with examples of where Enterprise Voice server roles can be deployed (and their relationship to one another and other Lync Server 2013 server roles), see [Reference topologies in Lync Server 2013](lync-server-2013-reference-topologies.md) in the Planning documentation.</span></span>

<span data-ttu-id="e9128-115">Для просмотра топологии ссылок, в которой показано, а также объясняется пример развертывания элемента управления допуском звонков, включая регионы сети, сетевые сайты и подсети, смотрите [пример. сбор требований для управления допуском звонков в Lync Server 2013](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md) в Документация по планированию.</span><span class="sxs-lookup"><span data-stu-id="e9128-115">To view a reference topology that illustrates and explains a sample call admission control deployment, including network regions, network sites, and subnets, see [Example: Gathering your requirements for call admission control in Lync Server 2013](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md) in the Planning documentation.</span></span>

</div>

</div>

<div id="sectionSection2" class="section">

<div>


> [!IMPORTANT]  
> <span data-ttu-id="e9128-116">Чтобы развернуть корпоративную голосовую почту на центральном сайте, продолжите чтение тем в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="e9128-116">To deploy Enterprise Voice at a central site, continue reading the topics in this section.</span></span> <span data-ttu-id="e9128-117">Чтобы развернуть корпоративную голосовую почту на сайте филиала, перейдите к разделу <A href="lync-server-2013-deploying-branch-sites.md">Развертывание сайтов филиалов в Lync Server 2013</A> в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="e9128-117">To deploy Enterprise Voice at a branch site, skip to <A href="lync-server-2013-deploying-branch-sites.md">Deploying branch sites in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<span data-ttu-id="e9128-118">В этом разделе описываются варианты развертывания с размещением сервера-посредника на каждом сервере переднего плана или сервере Standard Edition (рекомендуется), а также варианты развертывания отдельного пула cерверов-посредников.</span><span class="sxs-lookup"><span data-stu-id="e9128-118">This section includes procedures for deployments in which a Mediation Server is collocated on each Front End Server or Standard Edition server, as recommended, and also for deployments with a stand-alone Mediation Server pool.</span></span>

<span data-ttu-id="e9128-119">Вы можете пропустить следующее содержимое, если вы используете Topology Builder, чтобы определить и опубликовать топологию, которая будет высвоена серверу-посреднику на каждом сервере переднего плана или стандартном сервере выпуска Standard Edition, так как мастер развертывания уже автоматически установил файлы для Сервер для устранения проблем при установке файлов для пула серверов переднего плана или стандартного выпуска сервера:</span><span class="sxs-lookup"><span data-stu-id="e9128-119">You can skip the following content if you used Topology Builder to define and publish a topology that collocates a Mediation Server on each Front End Server or Standard Edition server, because Deployment Wizard already automatically installed the files for Mediation Server when you installed files for your Front End Server pool or Standard Edition server:</span></span>

  - [<span data-ttu-id="e9128-120">Конфигурация магистралей в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e9128-120">Configuring trunks in Lync Server 2013</span></span>](lync-server-2013-configuring-trunks.md)

<span data-ttu-id="e9128-121">Если вы использовали Topology Builder для определения и публикации сервера-посредника в отдельном пуле, вы можете использовать следующее содержимое:</span><span class="sxs-lookup"><span data-stu-id="e9128-121">If you used Topology Builder to define and publish a Mediation Server in a stand-alone pool, you can use the following content:</span></span>

  - <span data-ttu-id="e9128-122">Убедитесь, что ваша топология соответствует требованиям к программному обеспечению и среде, как описано в разделе [требования к корпоративной голосовой связи для Lync Server 2013](lync-server-2013-enterprise-voice-prerequisites.md).</span><span class="sxs-lookup"><span data-stu-id="e9128-122">Verify that your topology meets the software and environment prerequisites, as described in [Enterprise Voice prerequisites for Lync Server 2013](lync-server-2013-enterprise-voice-prerequisites.md).</span></span>

</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="e9128-123">Содержание</span><span class="sxs-lookup"><span data-stu-id="e9128-123">In This Section</span></span>

  - <span></span>  
    [<span data-ttu-id="e9128-124">Необходимые условия для корпоративной голосовой связи в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e9128-124">Enterprise Voice prerequisites for Lync Server 2013</span></span>](lync-server-2013-enterprise-voice-prerequisites.md)

  - <span></span>  
    [<span data-ttu-id="e9128-125">Развертывание серверов-посредников и определение одноранговых узлов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e9128-125">Deploying Mediation Servers and defining peers in Lync Server 2013</span></span>](lync-server-2013-deploying-mediation-servers-and-defining-peers.md)

  - <span></span>  
    [<span data-ttu-id="e9128-126">Конфигурация магистралей в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e9128-126">Configuring trunks in Lync Server 2013</span></span>](lync-server-2013-configuring-trunks.md)

  - <span></span>  
    [<span data-ttu-id="e9128-127">Настройка абонентских групп в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e9128-127">Configuring dial plans in Lync Server 2013</span></span>](lync-server-2013-configuring-dial-plans.md)

  - <span></span>  
    [<span data-ttu-id="e9128-128">Настройка политик голосовой связи, записей использования КТСОП и голосовых маршрутов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e9128-128">Configuring voice policies, PSTN usage records, and voice routes in Lync Server 2013</span></span>](lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md)

  - <span></span>  
    [<span data-ttu-id="e9128-129">Экспорт и импорт конфигурации маршрутизации голосовой связи в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e9128-129">Exporting and importing voice routing configuration in Lync Server 2013</span></span>](lync-server-2013-exporting-and-importing-voice-routing-configuration.md)

  - <span></span>  
    [<span data-ttu-id="e9128-130">Тестирование голосовой маршрутизации в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e9128-130">Test voice routing in Lync Server 2013</span></span>](lync-server-2013-test-voice-routing.md)

  - <span></span>  
    [<span data-ttu-id="e9128-131">Публикация ожидающих изменений в конфигурации голосовой маршрутизации в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e9128-131">Publish pending changes to the voice routing configuration in Lync Server 2013</span></span>](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)

  - <span></span>  
    [<span data-ttu-id="e9128-132">Развертывание локальной единой системы обмена сообщениями Exchange для предоставления голосовой почты Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e9128-132">Deploying on-premises Exchange UM to provide Lync Server 2013 voice mail</span></span>](lync-server-2013-deploying-on-premises-exchange-um-to-provide-lync-server-2013-voice-mail.md)

  - <span></span>  
    [<span data-ttu-id="e9128-133">Предоставление пользователям Lync Server 2013 голосовой почты в размещенной единой системе обмена сообщениями Exchange</span><span class="sxs-lookup"><span data-stu-id="e9128-133">Providing Lync Server 2013 users voice mail on hosted Exchange UM</span></span>](lync-server-2013-providing-lync-server-users-voice-mail-on-hosted-exchange-um.md)

  - <span></span>  
    [<span data-ttu-id="e9128-134">Настройка локальной интеграции Lync Server 2013 с Exchange Online</span><span class="sxs-lookup"><span data-stu-id="e9128-134">Configuring on-premises Lync Server 2013 integration with Exchange Online</span></span>](lync-server-2013-configuring-on-premises-lync-server-integration-with-exchange-online.md)

  - <span></span>  
    [<span data-ttu-id="e9128-135">Развертывание улучшенных функций голосовой связи в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e9128-135">Deploying advanced Enterprise Voice features in Lync Server 2013</span></span>](lync-server-2013-deploying-advanced-enterprise-voice-features.md)
    
      - [<span data-ttu-id="e9128-136">О сетевых областях, сайтах и подсетях в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e9128-136">About network regions, sites, and subnets in Lync Server 2013</span></span>](lync-server-2013-about-network-regions-sites-and-subnets.md)
    
      - [<span data-ttu-id="e9128-137">Создание или изменение сетевого региона в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e9128-137">Create or modify a network region in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-network-region.md)
    
      - [<span data-ttu-id="e9128-138">Создание или изменение сетевого сайта в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e9128-138">Create or modify a network site in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-network-site.md)
    
      - [<span data-ttu-id="e9128-139">Связь подсети с сетевым сайтом в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e9128-139">Associate a subnet with a network site in Lync Server 2013</span></span>](lync-server-2013-associate-a-subnet-with-a-network-site.md)
    
      - [<span data-ttu-id="e9128-140">Настройка управления допуском звонков в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e9128-140">Configure call admission control in Lync Server 2013</span></span>](lync-server-2013-configure-call-admission-control.md)
    
      - [<span data-ttu-id="e9128-141">Настройка службы Enhanced 9-1-1 в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e9128-141">Configure Enhanced 9-1-1 in Lync Server 2013</span></span>](lync-server-2013-configure-enhanced-9-1-1.md)
    
      - [<span data-ttu-id="e9128-142">Настройка обхода сервера-посредника в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e9128-142">Configure media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-media-bypass.md)

  - <span></span>  
    [<span data-ttu-id="e9128-143">Включение пользователей корпоративной голосовой связи в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e9128-143">Enable users for Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-enable-users-for-enterprise-voice.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="e9128-144">См. также</span><span class="sxs-lookup"><span data-stu-id="e9128-144">See Also</span></span>


[<span data-ttu-id="e9128-145">Развертывание сайтов филиалов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e9128-145">Deploying branch sites in Lync Server 2013</span></span>](lync-server-2013-deploying-branch-sites.md)  
[<span data-ttu-id="e9128-146">Настройка конференц-связи с телефонным подключением в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e9128-146">Configuring dial-in conferencing in Lync Server 2013</span></span>](lync-server-2013-configuring-dial-in-conferencing.md)  
[<span data-ttu-id="e9128-147">Настройка парковки вызовов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e9128-147">Configuring Call Park in Lync Server 2013</span></span>](lync-server-2013-configuring-call-park.md)  
[<span data-ttu-id="e9128-148">Настройка объявлений для неназначенных номеров в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e9128-148">Configuring announcements for unassigned numbers in Lync Server 2013</span></span>](lync-server-2013-configuring-announcements-for-unassigned-numbers.md)  
[<span data-ttu-id="e9128-149">Развертывание мониторинга в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e9128-149">Deploying monitoring in Lync Server 2013</span></span>](lync-server-2013-deploying-monitoring.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

