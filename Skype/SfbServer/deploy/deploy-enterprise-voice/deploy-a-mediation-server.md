---
title: Развертывание сервера-посредника в построителе топологии в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/7/2018
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 59d8f5ba-5064-4ea5-b4bf-2b9736e0fedd
description: 'Сводка: сведения о том, как определить и развернуть сервер-посредник в построителе топологии в Skype для бизнеса Server.'
ms.openlocfilehash: 61b90bb874d96579d975a1672238a7427350a5dc
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34284650"
---
# <a name="deploy-a-mediation-server-in-topology-builder-in-skype-for-business-server"></a><span data-ttu-id="8e73d-103">Развертывание сервера-посредника в построителе топологии в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="8e73d-103">Deploy a Mediation Server in Topology Builder in Skype for Business Server</span></span>
 
<span data-ttu-id="8e73d-104">**Сводка:** Сведения о том, как определить и развернуть сервер-посредник в построителе топологии в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="8e73d-104">**Summary:** Learn how to define and deploy a Mediation Server in Topology Builder in Skype for Business Server.</span></span>
  
<span data-ttu-id="8e73d-105">Корпоративная рабочая нагрузка, Конференц-связь с телефонным подключением и сложные приложения для корпоративной голосовой связи (приложение группы ответа, приложение для допуска звонков (CAC) и т. д.) можно использовать в пулах интерфейсного сервера.</span><span class="sxs-lookup"><span data-stu-id="8e73d-105">The Enterprise Voice workload, dial-in conferencing, and advanced Enterprise Voice applications (Response Group application, Call Park application, call admission control (CAC), and so on), are available in Front End pools.</span></span> <span data-ttu-id="8e73d-106">Функциональные возможности сервера обновлений встроены на сервер переднего плана.</span><span class="sxs-lookup"><span data-stu-id="8e73d-106">The functionality of the Mediation Server is built into the Front End Server.</span></span> <span data-ttu-id="8e73d-107">Отдельный сервер обновлений не требуется.</span><span class="sxs-lookup"><span data-stu-id="8e73d-107">A separate stand-alone Mediation Server is not necessary.</span></span> 
  
<span data-ttu-id="8e73d-108">Единственным исключением является настройка магистральной магистрали SIP для подключения к контроллеру границ сеанса для поставщика услуг телефонной связи через Интернет.</span><span class="sxs-lookup"><span data-stu-id="8e73d-108">The only exception is if you configure a SIP trunk to connect to a Session Border Controller for an Internet Telephony Service Provider.</span></span> <span data-ttu-id="8e73d-109">Чтобы подключить корпоративную инфраструктуру голосовой связи к провайдеру магистральной магистрали SIP, необходимо развернуть отдельный сервер-посредник.</span><span class="sxs-lookup"><span data-stu-id="8e73d-109">To connect your Enterprise Voice infrastructure to your SIP trunk provider, a separate Mediation Server must be deployed.</span></span>
  
<span data-ttu-id="8e73d-110">Соединение между Skype для бизнеса Server (сервер-посредник, выровненный по внешнему интерфейсу пула или изолированному серверу-посредником) и шлюз — это логическая ассоциация, называемая магистральной.</span><span class="sxs-lookup"><span data-stu-id="8e73d-110">The connection between Skype for Business Server (either a Mediation Server collocated on a Front End pool or stand-alone Mediation Server) and a gateway is defined as a logical association called a trunk.</span></span> <span data-ttu-id="8e73d-111">В этом разделе объясняется, как определить магистраль и как развернуть отдельный сервер-посредник, если вы подключаетесь к магистрали SIP.</span><span class="sxs-lookup"><span data-stu-id="8e73d-111">The topics in this section describe how to define a trunk and how to deploy a stand-alone Mediation Server, if you connect to a SIP trunk.</span></span>
  
## <a name="define-a-mediation-server-in-topology-builder"></a><span data-ttu-id="8e73d-112">Определение сервера-посредника в построителе топологий</span><span class="sxs-lookup"><span data-stu-id="8e73d-112">Define a Mediation Server in Topology Builder</span></span>

<span data-ttu-id="8e73d-113">Вы можете добавить сервер-посредник в качестве размещенной роли в пуле переднего плана или определить отдельный пул серверов автономных исправлений.</span><span class="sxs-lookup"><span data-stu-id="8e73d-113">You can add Mediation Server as a collocated role on a Front End pool, or define a separate standalone Mediation Server pool.</span></span>
  
### <a name="to-add-a-mediation-server-to-a-front-end-pool"></a><span data-ttu-id="8e73d-114">Добавление сервера-исправления в пул переднего плана</span><span class="sxs-lookup"><span data-stu-id="8e73d-114">To add a Mediation Server to a Front End pool</span></span>

1. <span data-ttu-id="8e73d-115">Запустить построитель топологии: нажмите кнопку **Пуск**, выберите пункт **все программы**, а затем — skype для бизнеса **Server 2015**и выберите пункт Построитель **Skype для бизнеса Server 2015Topology**.</span><span class="sxs-lookup"><span data-stu-id="8e73d-115">Start Topology Builder: Click **Start**, click **All Programs**, click **Skype for Business Server 2015**, and then click **Skype for Business Server 2015Topology Builder**.</span></span>
    
2. <span data-ttu-id="8e73d-116">В построителе топологии в дереве консоли разверните узел с именем сайта, для которого нужно определить пул переднего плана.</span><span class="sxs-lookup"><span data-stu-id="8e73d-116">In Topology Builder, in the console tree, expand the name of the site for which you want to define a Front End pool.</span></span>
    
3. <span data-ttu-id="8e73d-117">В дереве консоли щелкните правой кнопкой мыши тип пула переднего плана, а затем выберите команду **создать пул переднего плана..**.</span><span class="sxs-lookup"><span data-stu-id="8e73d-117">In the console tree, right-click the type of Front End pool you want, and then click **New Front End pool..**.</span></span>
    
4. <span data-ttu-id="8e73d-118">Перемещайтесь по мастеру **Определение нового пула переднего плана**, пока не откроете страницу **Выбор ролей серверов с совмещенным расположением**.</span><span class="sxs-lookup"><span data-stu-id="8e73d-118">Navigate through the **Define New Front End Pool** wizard until you reach the **Select collocated server roles** page.</span></span>
    
5. <span data-ttu-id="8e73d-119">В разделе Выбор размещенных **ролей сервера**установите флажок размещенный **сервер исправлений**.</span><span class="sxs-lookup"><span data-stu-id="8e73d-119">In **Select collocated server roles**, check the option **Collocate Mediation Server**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="8e73d-120">Если вы выбрали тип переднего плана для выпуска Enterprise Edition, серверный компонент будет установлен на всех серверах переднего плана в пуле внешних интерфейсов.</span><span class="sxs-lookup"><span data-stu-id="8e73d-120">If the type of Front End pool you selected is the Enterprise Edition, then the Mediation Server component will be installed on all the Front End Servers of that Front End pool.</span></span> 
  
    > [!NOTE]
    > <span data-ttu-id="8e73d-121">**Пул следующего прыжка** , используемый сервером, будет являться пулом переднего плана, на котором размещен сервер для исправлений.</span><span class="sxs-lookup"><span data-stu-id="8e73d-121">The **Next hop pool** used by the Mediation Server will be the Front End pool where the Mediation Server is collocated on.</span></span>
  
    > [!NOTE]
    > <span data-ttu-id="8e73d-122">**Пул пограничного** сервера, используемый сервером обновлений, будет таким же, как и пул переднего плана, связанный с пулом интерфейсов, на котором размещен сервер исправлений.</span><span class="sxs-lookup"><span data-stu-id="8e73d-122">The **Edge pool** used by the Mediation Server will be the same Edge pool associated with the Front End pool where the Mediation Server is collocated on.</span></span>
  
6. <span data-ttu-id="8e73d-123">Щелкните **по умолчанию** , чтобы использовать этот пул переднего плана для маршрутизации звонков в КТСОП.</span><span class="sxs-lookup"><span data-stu-id="8e73d-123">Click **Make Default** to use this Front End pool to route calls to the PSTN.</span></span>
    
7. <span data-ttu-id="8e73d-124">Нажмите кнопку **Готово** , после того как вы завершите связывание одного или нескольких одноранговых элементов с пулом переднего плана.</span><span class="sxs-lookup"><span data-stu-id="8e73d-124">Click **Finish** when you are finished associating one or more peers to the Front End pool.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="8e73d-125">Прежде чем перейти к следующему этапу в процессе развертывания Enterprise Voice, убедитесь в том, что в пуле сервера-посредника (то есть в пуле переднего плана с развернутым компонентом сервера-посредником) используются указанные полные доменные имена.</span><span class="sxs-lookup"><span data-stu-id="8e73d-125">Before you proceed to the next step in the Enterprise Voice deployment process, make sure that the Mediation Server pool (i.e. Front End pool with the Mediation Server component collocated) is using the FQDNs that you specified.</span></span> 
  
8. <span data-ttu-id="8e73d-126">Щелкните правой кнопкой мыши узел **2015 в Skype для бизнеса Server** и выберите пункт **топология публикации**.</span><span class="sxs-lookup"><span data-stu-id="8e73d-126">Right-click the **Skype for Business Server 2015** node, and then click **Publish Topology**.</span></span>
    
### <a name="to-add-a-standalone-mediation-server"></a><span data-ttu-id="8e73d-127">Добавление автономного сервера-посредника</span><span class="sxs-lookup"><span data-stu-id="8e73d-127">To add a standalone Mediation Server</span></span>

1. <span data-ttu-id="8e73d-128">Запустить построитель топологии: нажмите кнопку **Пуск**, выберите пункт **все программы**, а затем — skype для бизнеса **Server 2015**и выберите пункт Построитель **Skype для бизнеса Server 2015Topology**.</span><span class="sxs-lookup"><span data-stu-id="8e73d-128">Start Topology Builder: Click **Start**, click **All Programs**, click **Skype for Business Server 2015**, and then click **Skype for Business Server 2015Topology Builder**.</span></span>
    
2. <span data-ttu-id="8e73d-129">В построителе топологии в дереве консоли разверните узел с именем сайта, для которого нужно определить сервер-посредник.</span><span class="sxs-lookup"><span data-stu-id="8e73d-129">In Topology Builder, in the console tree, expand the name of the site for which you want to define a Mediation Server.</span></span>
    
3. <span data-ttu-id="8e73d-130">В дереве консоли щелкните правой кнопкой мыши узел **Пулы** ресурсов и выберите пункт **пул серверных обновлений**.</span><span class="sxs-lookup"><span data-stu-id="8e73d-130">In the console tree, right-click the **Mediation pools** node, and then click **Mediation Server pool**.</span></span>
    
4. <span data-ttu-id="8e73d-131">В разделе **Определение нового пула исправлений**введите полное доменное имя пула серверов обновлений (FQDN).</span><span class="sxs-lookup"><span data-stu-id="8e73d-131">In **Define New Mediation Pool**, type the Mediation Server pool fully qualified domain name (FQDN).</span></span>
    
5. <span data-ttu-id="8e73d-132">Затем выполните одно из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="8e73d-132">Next, do one of the following:</span></span>
    
   - <span data-ttu-id="8e73d-133">Если вы хотите развернуть несколько серверов обновлений в пуле для обеспечения высокой доступности, выберите пункт **несколько пулов компьютеров**.</span><span class="sxs-lookup"><span data-stu-id="8e73d-133">If you want to deploy multiple Mediation Servers in the pool to provide high availability, then select **Multiple computer pool**.</span></span>
    
     > [!NOTE]
     > <span data-ttu-id="8e73d-134">Необходимо [развернуть](../../plan-your-deployment/network-requirements/load-balancing.md#BKMK_DNSLoadBalancing) группу серверов "исправления", которая содержит несколько серверов обновлений.</span><span class="sxs-lookup"><span data-stu-id="8e73d-134">You must [deploy](../../plan-your-deployment/network-requirements/load-balancing.md#BKMK_DNSLoadBalancing) to support Mediation Server pools that have multiple Mediation Servers.</span></span>
  
   - <span data-ttu-id="8e73d-135">Если вы хотите развернуть только один сервер-посредник в пуле, так как вам не требуется высокая доступность, выберите **один пул компьютеров**.</span><span class="sxs-lookup"><span data-stu-id="8e73d-135">If you want to deploy only one Mediation Server in the pool because you do not require high availability, then select **Single computer pool**.</span></span> <span data-ttu-id="8e73d-136">Пропустите описанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="8e73d-136">Skip the following step.</span></span>
    
6. <span data-ttu-id="8e73d-137">If you selected **Multiple computer pool** in the previous step, on the **Define the computers in this pool** item, click **Computer FQDN**, type the FQDN of each server in the pool, and then click **Add**.</span><span class="sxs-lookup"><span data-stu-id="8e73d-137">If you selected **Multiple computer pool** in the previous step, on the **Define the computers in this pool** item, click **Computer FQDN**, type the FQDN of each server in the pool, and then click **Add**.</span></span> <span data-ttu-id="8e73d-138">Повторите этот шаг для всех других серверов, которые вы хотите добавить в пул.</span><span class="sxs-lookup"><span data-stu-id="8e73d-138">Repeat this step for all other Mediation Servers that you want to add to the pool.</span></span> <span data-ttu-id="8e73d-139">When you have defined all the computers in the pool, click **Next**.</span><span class="sxs-lookup"><span data-stu-id="8e73d-139">When you have defined all the computers in the pool, click **Next**.</span></span>
    
7. <span data-ttu-id="8e73d-140">На странице **Выбор следующего прыжка** щелкните **пул очередного прыжка**, выберите полное доменное имя пула, который будет использоваться этим пулом серверов исправлений, и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="8e73d-140">On the **Select the next hop** page, click **Next hop pool**, click the FQDN of the Front End pool that will use this Mediation Server pool, and then click **Next**.</span></span>
    
8. <span data-ttu-id="8e73d-141">На странице **Выбор пограничного сервера** выполните одно из указанных ниже действий.</span><span class="sxs-lookup"><span data-stu-id="8e73d-141">On the **Select an Edge Server** page, do one of the following:</span></span>
    
   - <span data-ttu-id="8e73d-142">Если вы хотите обеспечить подключение к сети PSTN для внешних пользователей, для которых разрешено использование корпоративной голосовой связи, в разделе **Выбор пула EDGE, используемого этим сервером исправлений**, выберите полное доменное имя пула пограничного сервера, который будет использоваться этим пулом серверов, для предоставления возможности подключения к сети PSTN внешние пользователи и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="8e73d-142">If you want to provide PSTN connectivity to external users enabled for Enterprise Voice, under **Select Edge Pool used by this Mediation Server**, click the FQDN of the Edge Server pool that will use this Mediation Server pool to provide PSTN connectivity to those external users, and then click **Next**.</span></span>
    
   - <span data-ttu-id="8e73d-143">Если вы не планируете включать внешних пользователей для корпоративной голосовой связи или не хотите предоставлять доступ к КТСОП для пользователей за пределами внутренней сети, нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="8e73d-143">If you do not plan to enable external users for Enterprise Voice, or if you do not want to provide PSTN connectivity to users when they are outside the internal network, click **Next**.</span></span>
    
9. <span data-ttu-id="8e73d-144">Щелкните правой кнопкой мыши узел **2015 в Skype для бизнеса Server** и выберите пункт **топология публикации**.</span><span class="sxs-lookup"><span data-stu-id="8e73d-144">Right-click the **Skype for Business Server 2015** node, and then click **Publish Topology**.</span></span>
    
## <a name="define-the-mediation-server-listening-ports"></a><span data-ttu-id="8e73d-145">Определение Прослушивающихх портов сервера</span><span class="sxs-lookup"><span data-stu-id="8e73d-145">Define the Mediation Server Listening Ports</span></span>

<span data-ttu-id="8e73d-146">Выполните действия, описанные в этом разделе, чтобы определить порты прослушивания сервер или группа, которые будут получать входящие соединения от кэширующего узла шлюза.</span><span class="sxs-lookup"><span data-stu-id="8e73d-146">Follow the steps in this topic to use Topology Builder to define the listening ports a Mediation Server or pool will accept incoming connections from a gateway peer.</span></span>
  
### <a name="to-modify-the-mediation-server-listening-ports"></a><span data-ttu-id="8e73d-147">Изменение портов для прослушивания сервера исправлений</span><span class="sxs-lookup"><span data-stu-id="8e73d-147">To Modify the Mediation Server Listening Ports</span></span>

1. <span data-ttu-id="8e73d-148">Запустить построитель топологии: нажмите кнопку **Пуск**, выберите пункт **все программы**, а затем — skype для бизнеса **Server 2015**и выберите пункт Построитель **Skype для бизнеса Server 2015Topology**.</span><span class="sxs-lookup"><span data-stu-id="8e73d-148">Start Topology Builder: Click **Start**, click **All Programs**, click **Skype for Business Server 2015**, and then click **Skype for Business Server 2015Topology Builder**.</span></span>
    
2. <span data-ttu-id="8e73d-149">В построителе топологии в дереве консоли разверните узел **Пулы исправлений** и щелкните правой кнопкой мыши сервер-посредника, который вы создали ранее.</span><span class="sxs-lookup"><span data-stu-id="8e73d-149">In Topology Builder, in the console tree, expand the **Mediation pools** node, and right-click the Mediation Server previously created.</span></span>
    
3. <span data-ttu-id="8e73d-150">По умолчанию порт прослушивания SIP на сервере-посреднике составляет 5070 для трафика TLS из Skype для бизнеса Server и 5067 для TLS-трафика от одноранговых узлов (например, Gateways, Пбксес или SBCs).</span><span class="sxs-lookup"><span data-stu-id="8e73d-150">By default, the SIP listening ports on the Mediation Server are 5070 for TLS traffic from Skype for Business Server, and 5067 for TLS traffic from peers (such as gateways, PBXes, or SBCs).</span></span> <span data-ttu-id="8e73d-151">TCP-порт по умолчанию отключен.</span><span class="sxs-lookup"><span data-stu-id="8e73d-151">TCP port is disabled by default.</span></span> <span data-ttu-id="8e73d-152">Необходимо включить TCP-порт, если имеются шлюзы, не поддерживающие TLS.</span><span class="sxs-lookup"><span data-stu-id="8e73d-152">You must enable TCP port if you have gateways that do not support TLS.</span></span>
    
4. <span data-ttu-id="8e73d-153">Укажите требуемый диапазон портов для прослушивания TLS или TCP. сервер исправлений будет принимать входящие подключения от шлюзов PSTN.</span><span class="sxs-lookup"><span data-stu-id="8e73d-153">Specify the desired TLS or TCP listening port range the Mediation Server will accept incoming connections from PSTN gateways.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="8e73d-p107">Ввод диапазона портов TCP не обязателен, если не установлен флажок **Включить порт TCP**. Это настройка не обязательна.</span><span class="sxs-lookup"><span data-stu-id="8e73d-p107">Entering a TCP port range is not required if **Enable TCP port** is not checked. This setting is optional.</span></span>
  

