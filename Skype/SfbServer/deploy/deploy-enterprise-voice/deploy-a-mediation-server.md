---
title: Развертывание сервера-посредника в построителье топологий в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/7/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 59d8f5ba-5064-4ea5-b4bf-2b9736e0fedd
description: Сводка. Узнайте, как определить и развернуть сервер-посредник в построитель топологий в Skype для бизнеса Server.
ms.openlocfilehash: b74819d7e68f76392beaa89427b3cf76f24b82d9
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49836919"
---
# <a name="deploy-a-mediation-server-in-topology-builder-in-skype-for-business-server"></a><span data-ttu-id="b765c-103">Развертывание сервера-посредника в построителье топологий в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="b765c-103">Deploy a Mediation Server in Topology Builder in Skype for Business Server</span></span>
 
<span data-ttu-id="b765c-104">**Сводка:** Узнайте, как определить и развернуть сервер-посредник в построитель топологий в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="b765c-104">**Summary:** Learn how to define and deploy a Mediation Server in Topology Builder in Skype for Business Server.</span></span>
  
<span data-ttu-id="b765c-105">Рабочая нагрузка Корпоративная голосовая связь, видеоконференция и расширенные приложения Корпоративная голосовая связь (приложение группы ответа, приложение парковки вызовов, контроль допуска вызовов и так далее) доступны в пулах переднего входа.</span><span class="sxs-lookup"><span data-stu-id="b765c-105">The Enterprise Voice workload, dial-in conferencing, and advanced Enterprise Voice applications (Response Group application, Call Park application, call admission control (CAC), and so on), are available in Front End pools.</span></span> <span data-ttu-id="b765c-106">Функциональность сервера-посредника встроена в сервер переднего сервера.</span><span class="sxs-lookup"><span data-stu-id="b765c-106">The functionality of the Mediation Server is built into the Front End Server.</span></span> <span data-ttu-id="b765c-107">Отдельный автономный сервер-посредник не требуется.</span><span class="sxs-lookup"><span data-stu-id="b765c-107">A separate stand-alone Mediation Server is not necessary.</span></span> 
  
<span data-ttu-id="b765c-108">Единственное исключение из данного правила — настройка магистрали SIP для подключения к пограничному контроллеру сеансов для поставщика услуг интернет-телефонии.</span><span class="sxs-lookup"><span data-stu-id="b765c-108">The only exception is if you configure a SIP trunk to connect to a Session Border Controller for an Internet Telephony Service Provider.</span></span> <span data-ttu-id="b765c-109">Чтобы подключить инфраструктуру Корпоративная голосовая связь к поставщику магистрали SIP, необходимо развернуть отдельный сервер-посредник.</span><span class="sxs-lookup"><span data-stu-id="b765c-109">To connect your Enterprise Voice infrastructure to your SIP trunk provider, a separate Mediation Server must be deployed.</span></span>
  
<span data-ttu-id="b765c-110">Соединение между Skype для бизнеса Server (сервером-посредником, который размещен в пуле переднего сервера или автономным сервером-посредником) и шлюзом определяется как логическая связь, называемая магистралью.</span><span class="sxs-lookup"><span data-stu-id="b765c-110">The connection between Skype for Business Server (either a Mediation Server collocated on a Front End pool or stand-alone Mediation Server) and a gateway is defined as a logical association called a trunk.</span></span> <span data-ttu-id="b765c-111">В этом разделе даны инструкции по определению магистрали и развертыванию отдельного сервера-посредника при подключении к магистрали SIP.</span><span class="sxs-lookup"><span data-stu-id="b765c-111">The topics in this section describe how to define a trunk and how to deploy a stand-alone Mediation Server, if you connect to a SIP trunk.</span></span>
  
## <a name="define-a-mediation-server-in-topology-builder"></a><span data-ttu-id="b765c-112">Определение сервера-посредника в построителе топологий</span><span class="sxs-lookup"><span data-stu-id="b765c-112">Define a Mediation Server in Topology Builder</span></span>

<span data-ttu-id="b765c-113">Вы можете добавить сервер-посредник в качестве роли с ролью совме-в пуле переднего плана или определить отдельный автономный пул серверов-посредников.</span><span class="sxs-lookup"><span data-stu-id="b765c-113">You can add Mediation Server as a collocated role on a Front End pool, or define a separate standalone Mediation Server pool.</span></span>
  
### <a name="to-add-a-mediation-server-to-a-front-end-pool"></a><span data-ttu-id="b765c-114">Добавление сервера-посредника в пул переднего сервера</span><span class="sxs-lookup"><span data-stu-id="b765c-114">To add a Mediation Server to a Front End pool</span></span>

1. <span data-ttu-id="b765c-115">Start Topology Builder: Click **Start**, click **All Programs**, click **Skype for Business Server 2015**, and then click Skype for Business Server **2015Topology Builder**.</span><span class="sxs-lookup"><span data-stu-id="b765c-115">Start Topology Builder: Click **Start**, click **All Programs**, click **Skype for Business Server 2015**, and then click **Skype for Business Server 2015Topology Builder**.</span></span>
    
2. <span data-ttu-id="b765c-116">В построителье топологий в дереве консоли развяжем имя сайта, для которого необходимо определить пул переднего входа.</span><span class="sxs-lookup"><span data-stu-id="b765c-116">In Topology Builder, in the console tree, expand the name of the site for which you want to define a Front End pool.</span></span>
    
3. <span data-ttu-id="b765c-117">В дереве консоли щелкните правой кнопкой мыши нужный тип пула переднего вида, а затем выберите "Новый **пул переднего входа".**</span><span class="sxs-lookup"><span data-stu-id="b765c-117">In the console tree, right-click the type of Front End pool you want, and then click **New Front End pool..**.</span></span>
    
4. <span data-ttu-id="b765c-118">Перемещайтесь по мастеру **Определение нового пула переднего плана**, пока не откроете страницу **Выбор ролей серверов с совмещенным расположением**.</span><span class="sxs-lookup"><span data-stu-id="b765c-118">Navigate through the **Define New Front End Pool** wizard until you reach the **Select collocated server roles** page.</span></span>
    
5. <span data-ttu-id="b765c-119">В **параметре "Выбор ролей сервера-посредника** с выполнив роль сервера-посредника", выберите параметр "Выполнив **выполнив** роль сервера-посредника</span><span class="sxs-lookup"><span data-stu-id="b765c-119">In **Select collocated server roles**, check the option **Collocate Mediation Server**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="b765c-120">Если выбран тип пула переднего сервера Enterprise Edition, компонент сервера-посредника будет установлен на всех серверах переднего сервера этого пула переднего сервера.</span><span class="sxs-lookup"><span data-stu-id="b765c-120">If the type of Front End pool you selected is the Enterprise Edition, then the Mediation Server component will be installed on all the Front End Servers of that Front End pool.</span></span> 
  
    > [!NOTE]
    > <span data-ttu-id="b765c-121">Пул **следующего прыжка, используемый** сервером-посредником, будет пулом переднего сервера, в котором размещен сервер-посредник.</span><span class="sxs-lookup"><span data-stu-id="b765c-121">The **Next hop pool** used by the Mediation Server will be the Front End pool where the Mediation Server is collocated on.</span></span>
  
    > [!NOTE]
    > <span data-ttu-id="b765c-122">Пул, **используемый** сервером-посредником, будет тем же пулом, связанным с пулом переднего сервера, в котором размещен сервер-посредник.</span><span class="sxs-lookup"><span data-stu-id="b765c-122">The **Edge pool** used by the Mediation Server will be the same Edge pool associated with the Front End pool where the Mediation Server is collocated on.</span></span>
  
6. <span data-ttu-id="b765c-123">Нажмите **кнопку "По** умолчанию", чтобы использовать этот пул переднего входа для маршрутов вызовов в STN.</span><span class="sxs-lookup"><span data-stu-id="b765c-123">Click **Make Default** to use this Front End pool to route calls to the PSTN.</span></span>
    
7. <span data-ttu-id="b765c-124">Нажмите **кнопку** "Готово", когда закончите связывание одного или более одноранговых одноранговых узла с пулом переднего входа.</span><span class="sxs-lookup"><span data-stu-id="b765c-124">Click **Finish** when you are finished associating one or more peers to the Front End pool.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="b765c-125">Перед тем как перейти к следующему шагу в процессе развертывания Корпоративная голосовая связь, убедитесь, что пул серверов-посредников (то есть пул переднего сервера с компонентом сервера-посредника) использует указанные FQDNs.</span><span class="sxs-lookup"><span data-stu-id="b765c-125">Before you proceed to the next step in the Enterprise Voice deployment process, make sure that the Mediation Server pool (i.e. Front End pool with the Mediation Server component collocated) is using the FQDNs that you specified.</span></span> 
  
8. <span data-ttu-id="b765c-126">Щелкните правой кнопкой мыши узел **Skype для бизнеса Server 2015** и выберите "Опубликовать **топологию".**</span><span class="sxs-lookup"><span data-stu-id="b765c-126">Right-click the **Skype for Business Server 2015** node, and then click **Publish Topology**.</span></span>
    
### <a name="to-add-a-standalone-mediation-server"></a><span data-ttu-id="b765c-127">Добавление автономных серверов-посредников</span><span class="sxs-lookup"><span data-stu-id="b765c-127">To add a standalone Mediation Server</span></span>

1. <span data-ttu-id="b765c-128">Start Topology Builder: Click **Start**, click **All Programs**, click **Skype for Business Server 2015**, and then click Skype for Business Server **2015Topology Builder**.</span><span class="sxs-lookup"><span data-stu-id="b765c-128">Start Topology Builder: Click **Start**, click **All Programs**, click **Skype for Business Server 2015**, and then click **Skype for Business Server 2015Topology Builder**.</span></span>
    
2. <span data-ttu-id="b765c-129">В построителье топологий в дереве консоли разкруте имя сайта, для которого необходимо определить сервер-посредник.</span><span class="sxs-lookup"><span data-stu-id="b765c-129">In Topology Builder, in the console tree, expand the name of the site for which you want to define a Mediation Server.</span></span>
    
3. <span data-ttu-id="b765c-130">В дереве консоли щелкните  правой кнопкой мыши узел пулов-посредников и выберите пул **серверов-посредников.**</span><span class="sxs-lookup"><span data-stu-id="b765c-130">In the console tree, right-click the **Mediation pools** node, and then click **Mediation Server pool**.</span></span>
    
4. <span data-ttu-id="b765c-131">В **области "Определение нового пула-посредника"** введите полное доменное имя пула серверов-посредников.</span><span class="sxs-lookup"><span data-stu-id="b765c-131">In **Define New Mediation Pool**, type the Mediation Server pool fully qualified domain name (FQDN).</span></span>
    
5. <span data-ttu-id="b765c-132">Затем выполните одно из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="b765c-132">Next, do one of the following:</span></span>
    
   - <span data-ttu-id="b765c-133">Если вы хотите развернуть несколько серверов-посредников в пуле для обеспечения высокой доступности, выберите пул **из нескольких компьютеров.**</span><span class="sxs-lookup"><span data-stu-id="b765c-133">If you want to deploy multiple Mediation Servers in the pool to provide high availability, then select **Multiple computer pool**.</span></span>
    
     > [!NOTE]
     > <span data-ttu-id="b765c-134">Необходимо развернуть [для поддержки](../../plan-your-deployment/network-requirements/load-balancing.md#BKMK_DNSLoadBalancing) пулов серверов-посредников с несколькими серверами-посредниками.</span><span class="sxs-lookup"><span data-stu-id="b765c-134">You must [deploy](../../plan-your-deployment/network-requirements/load-balancing.md#BKMK_DNSLoadBalancing) to support Mediation Server pools that have multiple Mediation Servers.</span></span>
  
   - <span data-ttu-id="b765c-135">Если требуется развернуть в пуле только один сервер-посредник, так как высокая доступность не требуется, выберите пул **из одного компьютера.**</span><span class="sxs-lookup"><span data-stu-id="b765c-135">If you want to deploy only one Mediation Server in the pool because you do not require high availability, then select **Single computer pool**.</span></span> <span data-ttu-id="b765c-136">Пропустите следующий шаг.</span><span class="sxs-lookup"><span data-stu-id="b765c-136">Skip the following step.</span></span>
    
6. <span data-ttu-id="b765c-137">Если на предыдущем шаге вы выбрали вариант **Пул на нескольких компьютерах**, в разделе **Определение компьютеров в этом пуле** щелкните поле **Полное доменное имя компьютера**, введите полное доменное имя каждого сервера в пуле и нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="b765c-137">If you selected **Multiple computer pool** in the previous step, on the **Define the computers in this pool** item, click **Computer FQDN**, type the FQDN of each server in the pool, and then click **Add**.</span></span> <span data-ttu-id="b765c-138">Повторите этот шаг для всех остальных серверов-посредников, которые нужно добавить в пул.</span><span class="sxs-lookup"><span data-stu-id="b765c-138">Repeat this step for all other Mediation Servers that you want to add to the pool.</span></span> <span data-ttu-id="b765c-139">Определив все компьютеры в пуле, нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="b765c-139">When you have defined all the computers in the pool, click **Next**.</span></span>
    
7. <span data-ttu-id="b765c-140">На странице "Выбор **следующего** прыжка" выберите пул следующего **перехода,** щелкните FQDN пула переднего сервера, который будет использовать этот пул серверов-посредников, а затем нажмите кнопку **"Далее".**</span><span class="sxs-lookup"><span data-stu-id="b765c-140">On the **Select the next hop** page, click **Next hop pool**, click the FQDN of the Front End pool that will use this Mediation Server pool, and then click **Next**.</span></span>
    
8. <span data-ttu-id="b765c-141">На странице **Выбор пограничного сервера** выполните одно из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="b765c-141">On the **Select an Edge Server** page, do one of the following:</span></span>
    
   - <span data-ttu-id="b765c-142">Если вы хотите предоставить подключение к STN внешним пользователям, включенным для Корпоративная голосовая связь, в области выбора пула, используемого этим сервером-посредником, щелкните FQDN пула серверов-посредников, который будет использовать этот пул серверов-посредников для обеспечения связи с этими внешними пользователями, а затем нажмите кнопку **"Далее".**</span><span class="sxs-lookup"><span data-stu-id="b765c-142">If you want to provide PSTN connectivity to external users enabled for Enterprise Voice, under **Select Edge Pool used by this Mediation Server**, click the FQDN of the Edge Server pool that will use this Mediation Server pool to provide PSTN connectivity to those external users, and then click **Next**.</span></span>
    
   - <span data-ttu-id="b765c-143">Если вы не планируете включить внешних пользователей для Корпоративная голосовая связь или если вы не хотите предоставлять пользователям возможность подключения к STN, когда они находятся за пределами внутренней сети, нажмите кнопку **"Далее".**</span><span class="sxs-lookup"><span data-stu-id="b765c-143">If you do not plan to enable external users for Enterprise Voice, or if you do not want to provide PSTN connectivity to users when they are outside the internal network, click **Next**.</span></span>
    
9. <span data-ttu-id="b765c-144">Щелкните правой кнопкой мыши узел **Skype для бизнеса Server 2015** и выберите "Опубликовать **топологию".**</span><span class="sxs-lookup"><span data-stu-id="b765c-144">Right-click the **Skype for Business Server 2015** node, and then click **Publish Topology**.</span></span>
    
## <a name="define-the-mediation-server-listening-ports"></a><span data-ttu-id="b765c-145">Определение портов прослушивания сервера-посредника</span><span class="sxs-lookup"><span data-stu-id="b765c-145">Define the Mediation Server Listening Ports</span></span>

<span data-ttu-id="b765c-146">Выполните действия, которые необходимо предпринять в этом разделе, чтобы использовать построитель топологий для определения портов прослушивания, которые сервер-посредник или пул будут принимать входящие подключения от одноранговых шлюзов.</span><span class="sxs-lookup"><span data-stu-id="b765c-146">Follow the steps in this topic to use Topology Builder to define the listening ports a Mediation Server or pool will accept incoming connections from a gateway peer.</span></span>
  
### <a name="to-modify-the-mediation-server-listening-ports"></a><span data-ttu-id="b765c-147">Изменение портов прослушивания сервера-посредника</span><span class="sxs-lookup"><span data-stu-id="b765c-147">To Modify the Mediation Server Listening Ports</span></span>

1. <span data-ttu-id="b765c-148">Start Topology Builder: Click **Start**, click **All Programs**, click **Skype for Business Server 2015**, and then click Skype for Business Server **2015Topology Builder**.</span><span class="sxs-lookup"><span data-stu-id="b765c-148">Start Topology Builder: Click **Start**, click **All Programs**, click **Skype for Business Server 2015**, and then click **Skype for Business Server 2015Topology Builder**.</span></span>
    
2. <span data-ttu-id="b765c-149">В построителье топологий  в дереве консоли разйдите узел пулов-посредников и щелкните правой кнопкой мыши ранее созданный сервер-посредник.</span><span class="sxs-lookup"><span data-stu-id="b765c-149">In Topology Builder, in the console tree, expand the **Mediation pools** node, and right-click the Mediation Server previously created.</span></span>
    
3. <span data-ttu-id="b765c-150">По умолчанию SIP-порты прослушивания на сервере-посреднике имеют значение 5070 для трафика TLS из Skype для бизнеса Server и 5067 для трафика TLS от одноранговых серверов (например, шлюзов, УАЦ или SBCs).</span><span class="sxs-lookup"><span data-stu-id="b765c-150">By default, the SIP listening ports on the Mediation Server are 5070 for TLS traffic from Skype for Business Server, and 5067 for TLS traffic from peers (such as gateways, PBXes, or SBCs).</span></span> <span data-ttu-id="b765c-151">TCP-порт по умолчанию отключен.</span><span class="sxs-lookup"><span data-stu-id="b765c-151">TCP port is disabled by default.</span></span> <span data-ttu-id="b765c-152">Необходимо включить TCP-порт, если имеются шлюзы, не поддерживающие TLS.</span><span class="sxs-lookup"><span data-stu-id="b765c-152">You must enable TCP port if you have gateways that do not support TLS.</span></span>
    
4. <span data-ttu-id="b765c-153">Укажите нужный диапазон портов прослушивания TLS или TCP, который сервер-посредник будет принимать входящие подключения от шлюзов STN.</span><span class="sxs-lookup"><span data-stu-id="b765c-153">Specify the desired TLS or TCP listening port range the Mediation Server will accept incoming connections from PSTN gateways.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="b765c-154">Ввод диапазона портов TCP не является обязательным, если не установлен флажок  **Включить порт TCP**.</span><span class="sxs-lookup"><span data-stu-id="b765c-154">Entering a TCP port range is not required if **Enable TCP port** is not checked.</span></span> <span data-ttu-id="b765c-155">Эта запись не является обязательной.</span><span class="sxs-lookup"><span data-stu-id="b765c-155">This setting is optional.</span></span>
  

