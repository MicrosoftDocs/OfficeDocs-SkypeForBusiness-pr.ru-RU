---
title: Развертывание сервера-посредника в построителе топологий в Скайп для Business Server
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/7/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 59d8f5ba-5064-4ea5-b4bf-2b9736e0fedd
description: 'Сводка: Узнайте, как определять и развертывание сервера-посредника в построителе топологий в Скайп for Business Server.'
ms.openlocfilehash: fd83ecb44726f151dea83c19b9745446653ca33b
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2018
ms.locfileid: "23883726"
---
# <a name="deploy-a-mediation-server-in-topology-builder-in-skype-for-business-server"></a><span data-ttu-id="7568d-103">Развертывание сервера-посредника в построителе топологий в Скайп для Business Server</span><span class="sxs-lookup"><span data-stu-id="7568d-103">Deploy a Mediation Server in Topology Builder in Skype for Business Server</span></span>
 
<span data-ttu-id="7568d-104">**Сводка:** Узнайте, как определять и развертывание сервера-посредника в построителе топологий в Скайп for Business Server.</span><span class="sxs-lookup"><span data-stu-id="7568d-104">**Summary:** Learn how to define and deploy a Mediation Server in Topology Builder in Skype for Business Server.</span></span>
  
<span data-ttu-id="7568d-105">Рабочей нагрузки корпоративной голосовой связи, телефонных конференций и сложных приложений корпоративной голосовой связи (приложение группы ответа, приложение парковки вызовов, контроль допуска звонков (CAC) и т. д.), доступны в пулов переднего плана.</span><span class="sxs-lookup"><span data-stu-id="7568d-105">The Enterprise Voice workload, dial-in conferencing, and advanced Enterprise Voice applications (Response Group application, Call Park application, call admission control (CAC), and so on), are available in Front End pools.</span></span> <span data-ttu-id="7568d-106">Функциональность сервера-посредника, встроенная в сервер переднего плана.</span><span class="sxs-lookup"><span data-stu-id="7568d-106">The functionality of the Mediation Server is built into the Front End Server.</span></span> <span data-ttu-id="7568d-107">Отдельный автономный сервер-посредник не требуется.</span><span class="sxs-lookup"><span data-stu-id="7568d-107">A separate stand-alone Mediation Server is not necessary.</span></span> 
  
<span data-ttu-id="7568d-108">Единственное исключение, если настроить канала SIP для подключения к пограничный контроллер сеансов для поставщика услуг телефонии.</span><span class="sxs-lookup"><span data-stu-id="7568d-108">The only exception is if you configure a SIP trunk to connect to a Session Border Controller for an Internet Telephony Service Provider.</span></span> <span data-ttu-id="7568d-109">Для подключения к поставщику магистрали SIP вашей инфраструктурой корпоративной голосовой связи, должен быть развернут на отдельный сервер-посредник.</span><span class="sxs-lookup"><span data-stu-id="7568d-109">To connect your Enterprise Voice infrastructure to your SIP trunk provider, a separate Mediation Server must be deployed.</span></span>
  
<span data-ttu-id="7568d-110">Соединение между Скайп для Business Server (промежуточный сервер с совместным размещением пула переднего плана или автономный сервер-посредник) и шлюз представляет собой логические связи, называется магистрали.</span><span class="sxs-lookup"><span data-stu-id="7568d-110">The connection between Skype for Business Server (either a Mediation Server collocated on a Front End pool or stand-alone Mediation Server) and a gateway is defined as a logical association called a trunk.</span></span> <span data-ttu-id="7568d-111">В этом разделе описываются способы определения магистрали и развертывание автономный сервер-посредник, если подключение к магистрали SIP.</span><span class="sxs-lookup"><span data-stu-id="7568d-111">The topics in this section describe how to define a trunk and how to deploy a stand-alone Mediation Server, if you connect to a SIP trunk.</span></span>
  
## <a name="define-a-mediation-server-in-topology-builder"></a><span data-ttu-id="7568d-112">Определение сервера-посредника в построителе топологий</span><span class="sxs-lookup"><span data-stu-id="7568d-112">Define a Mediation Server in Topology Builder</span></span>

<span data-ttu-id="7568d-113">Можно добавить сервер-посредник в качестве выровненных ролей в пуле переднего плана или определить отдельные автономного пула серверов-посредников.</span><span class="sxs-lookup"><span data-stu-id="7568d-113">You can add Mediation Server as a collocated role on a Front End pool, or define a separate standalone Mediation Server pool.</span></span>
  
### <a name="to-add-a-mediation-server-to-a-front-end-pool"></a><span data-ttu-id="7568d-114">Добавление сервера-посредника для пула переднего плана</span><span class="sxs-lookup"><span data-stu-id="7568d-114">To add a Mediation Server to a Front End pool</span></span>

1. <span data-ttu-id="7568d-115">Запустите построитель топологий: Нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы**, щелкните **Скайп для Business Server 2015**и нажмите кнопку **Скайп для построителя 2015Topology Business Server**.</span><span class="sxs-lookup"><span data-stu-id="7568d-115">Start Topology Builder: Click **Start**, click **All Programs**, click **Skype for Business Server 2015**, and then click **Skype for Business Server 2015Topology Builder**.</span></span>
    
2. <span data-ttu-id="7568d-116">В построителе топологий в дереве консоли разверните имя сайта, для которого нужно определить пула переднего плана.</span><span class="sxs-lookup"><span data-stu-id="7568d-116">In Topology Builder, in the console tree, expand the name of the site for which you want to define a Front End pool.</span></span>
    
3. <span data-ttu-id="7568d-117">В дереве консоли щелкните правой кнопкой мыши тип интерфейсного пула, который будет и нажмите кнопку **новый интерфейсный пул..**.</span><span class="sxs-lookup"><span data-stu-id="7568d-117">In the console tree, right-click the type of Front End pool you want, and then click **New Front End pool..**.</span></span>
    
4. <span data-ttu-id="7568d-118">Перемещайтесь по мастеру **Определение нового пула переднего плана**, пока не откроете страницу **Выбор ролей серверов с совмещенным расположением**.</span><span class="sxs-lookup"><span data-stu-id="7568d-118">Navigate through the **Define New Front End Pool** wizard until you reach the **Select collocated server roles** page.</span></span>
    
5. <span data-ttu-id="7568d-119">**Выберите сервер выровненных ролей**установите флажок **Совместно размещать сервера-посредника**.</span><span class="sxs-lookup"><span data-stu-id="7568d-119">In **Select collocated server roles**, check the option **Collocate Mediation Server**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="7568d-120">Если тип пула переднего плана, выбранном Enterprise Edition, компонент сервера-посредника должны устанавливаться на всех серверах переднего плана из пула переднего плана.</span><span class="sxs-lookup"><span data-stu-id="7568d-120">If the type of Front End pool you selected is the Enterprise Edition, then the Mediation Server component will be installed on all the Front End Servers of that Front End pool.</span></span> 
  
    > [!NOTE]
    > <span data-ttu-id="7568d-121">**Пул узла следующего перехода** , используемый сервером-посредником, будет пула переднего плана, где сервер-посредник совмещен.</span><span class="sxs-lookup"><span data-stu-id="7568d-121">The **Next hop pool** used by the Mediation Server will be the Front End pool where the Mediation Server is collocated on.</span></span>
  
    > [!NOTE]
    > <span data-ttu-id="7568d-122">**Пограничный пул** , используемый сервером-посредником, будет же пограничного пула, связанного с пулом переднего плана, где сервер-посредник совмещен.</span><span class="sxs-lookup"><span data-stu-id="7568d-122">The **Edge pool** used by the Mediation Server will be the same Edge pool associated with the Front End pool where the Mediation Server is collocated on.</span></span>
  
6. <span data-ttu-id="7568d-123">Нажмите кнопку **Использовать по умолчанию** , чтобы использовать этот пул переднего плана для маршрутизации вызовов в ТСОП.</span><span class="sxs-lookup"><span data-stu-id="7568d-123">Click **Make Default** to use this Front End pool to route calls to the PSTN.</span></span>
    
7. <span data-ttu-id="7568d-124">Когда связав один или несколько одноранговых пула переднего плана, нажмите кнопку **Готово** .</span><span class="sxs-lookup"><span data-stu-id="7568d-124">Click **Finish** when you are finished associating one or more peers to the Front End pool.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="7568d-125">Прежде чем перейти к следующему шагу в процессе развертывания корпоративной голосовой связи, убедитесь в том, что пула серверов-посредников (то есть переднего плана пула с компонентом сервера-посредника, совмещенного) — это с помощью полных доменных имен, указанных.</span><span class="sxs-lookup"><span data-stu-id="7568d-125">Before you proceed to the next step in the Enterprise Voice deployment process, make sure that the Mediation Server pool (i.e. Front End pool with the Mediation Server component collocated) is using the FQDNs that you specified.</span></span> 
  
8. <span data-ttu-id="7568d-126">Щелкните правой кнопкой мыши узел **Скайп для Business Server 2015** и нажмите кнопку **Опубликовать топологию**.</span><span class="sxs-lookup"><span data-stu-id="7568d-126">Right-click the **Skype for Business Server 2015** node, and then click **Publish Topology**.</span></span>
    
### <a name="to-add-a-standalone-mediation-server"></a><span data-ttu-id="7568d-127">Добавление автономного сервера-посредника</span><span class="sxs-lookup"><span data-stu-id="7568d-127">To add a standalone Mediation Server</span></span>

1. <span data-ttu-id="7568d-128">Запустите построитель топологий: Нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы**, щелкните **Скайп для Business Server 2015**и нажмите кнопку **Скайп для построителя 2015Topology Business Server**.</span><span class="sxs-lookup"><span data-stu-id="7568d-128">Start Topology Builder: Click **Start**, click **All Programs**, click **Skype for Business Server 2015**, and then click **Skype for Business Server 2015Topology Builder**.</span></span>
    
2. <span data-ttu-id="7568d-129">В построителе топологий в дереве консоли разверните имя сайта, для которого нужно определить сервера-посредника.</span><span class="sxs-lookup"><span data-stu-id="7568d-129">In Topology Builder, in the console tree, expand the name of the site for which you want to define a Mediation Server.</span></span>
    
3. <span data-ttu-id="7568d-130">В дереве консоли щелкните правой кнопкой мыши узел **Пулы-посредники** и нажмите кнопку **пула серверов-посредников**.</span><span class="sxs-lookup"><span data-stu-id="7568d-130">In the console tree, right-click the **Mediation pools** node, and then click **Mediation Server pool**.</span></span>
    
4. <span data-ttu-id="7568d-131">**Определение нового пула-посредника**введите полное доменное имя (FQDN) пула сервера-посредника.</span><span class="sxs-lookup"><span data-stu-id="7568d-131">In **Define New Mediation Pool**, type the Mediation Server pool fully qualified domain name (FQDN).</span></span>
    
5. <span data-ttu-id="7568d-132">Затем выполните одно из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="7568d-132">Next, do one of the following:</span></span>
    
   - <span data-ttu-id="7568d-133">Если вы хотите развернуть несколько серверов-посредников в пуле, чтобы обеспечить высокую доступность, выберите пункт **пул на нескольких компьютерах**.</span><span class="sxs-lookup"><span data-stu-id="7568d-133">If you want to deploy multiple Mediation Servers in the pool to provide high availability, then select **Multiple computer pool**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="7568d-134">Необходимо [Развернуть](../../plan-your-deployment/network-requirements/load-balancing.md#BKMK_DNSLoadBalancing) для поддержки сервера-посредника пулы, которые имеют несколько серверов-посредников.</span><span class="sxs-lookup"><span data-stu-id="7568d-134">You must [deploy](../../plan-your-deployment/network-requirements/load-balancing.md#BKMK_DNSLoadBalancing) to support Mediation Server pools that have multiple Mediation Servers.</span></span>
  
   - <span data-ttu-id="7568d-135">Если вы хотите развернуть только один сервер-посредник в пуле, так как не требуется высокий уровень доступности, выберите пункт **пул из одного компьютера**.</span><span class="sxs-lookup"><span data-stu-id="7568d-135">If you want to deploy only one Mediation Server in the pool because you do not require high availability, then select **Single computer pool**.</span></span> <span data-ttu-id="7568d-136">Пропустите следующее действие.</span><span class="sxs-lookup"><span data-stu-id="7568d-136">Skip the following step.</span></span>
    
6. <span data-ttu-id="7568d-137">Если вы выбрали **пул на нескольких компьютерах** на предыдущем шаге, в элементе **Определение компьютеров в этом пуле** нажмите кнопку **Полное доменное имя компьютера**, введите полное доменное имя каждого сервера в пуле и нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="7568d-137">If you selected **Multiple computer pool** in the previous step, on the **Define the computers in this pool** item, click **Computer FQDN**, type the FQDN of each server in the pool, and then click **Add**.</span></span> <span data-ttu-id="7568d-138">Повторите это действие для всех других серверов-посредников, которые нужно добавить в пул.</span><span class="sxs-lookup"><span data-stu-id="7568d-138">Repeat this step for all other Mediation Servers that you want to add to the pool.</span></span> <span data-ttu-id="7568d-139">После определения всех компьютеров в пуле, нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="7568d-139">When you have defined all the computers in the pool, click **Next**.</span></span>
    
7. <span data-ttu-id="7568d-140">На странице **Выбор следующего прыжка** щелкните **пул следующих прыжков**, полное доменное имя пула переднего плана, который будет использовать этот пул сервера-посредника и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="7568d-140">On the **Select the next hop** page, click **Next hop pool**, click the FQDN of the Front End pool that will use this Mediation Server pool, and then click **Next**.</span></span>
    
8. <span data-ttu-id="7568d-141">На странице **Выбор пограничного сервера** выполните одно из указанных ниже действий.</span><span class="sxs-lookup"><span data-stu-id="7568d-141">On the **Select an Edge Server** page, do one of the following:</span></span>
    
   - <span data-ttu-id="7568d-142">Если вы хотите предоставить подключение ТСОП для внешних пользователей, включены для корпоративной голосовой связи, в разделе **Выбор пограничного пула, используемого с этого сервера-посредника**, выберите полное доменное имя пула пограничных серверов, которую будет использовать этот пул сервера-посредника для подключений ТСОП к эти внешние пользователи и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="7568d-142">If you want to provide PSTN connectivity to external users enabled for Enterprise Voice, under **Select Edge Pool used by this Mediation Server**, click the FQDN of the Edge Server pool that will use this Mediation Server pool to provide PSTN connectivity to those external users, and then click **Next**.</span></span>
    
   - <span data-ttu-id="7568d-143">Если вы не планируете предоставление внешним пользователям корпоративной голосовой связи, или если вы не хотите предоставить подключение ТСОП для пользователей, находящихся за пределами внутренней сети, нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="7568d-143">If you do not plan to enable external users for Enterprise Voice, or if you do not want to provide PSTN connectivity to users when they are outside the internal network, click **Next**.</span></span>
    
9. <span data-ttu-id="7568d-144">Щелкните правой кнопкой мыши узел **Скайп для Business Server 2015** и нажмите кнопку **Опубликовать топологию**.</span><span class="sxs-lookup"><span data-stu-id="7568d-144">Right-click the **Skype for Business Server 2015** node, and then click **Publish Topology**.</span></span>
    
## <a name="define-the-mediation-server-listening-ports"></a><span data-ttu-id="7568d-145">Определение портов прослушивания Mediation Server</span><span class="sxs-lookup"><span data-stu-id="7568d-145">Define the Mediation Server Listening Ports</span></span>

<span data-ttu-id="7568d-146">Выполните действия, описанные в этом разделе, чтобы использовать построитель топологий для определения портов прослушивания на сервер-посредник или пул будут принимать входящие подключения от однорангового шлюза.</span><span class="sxs-lookup"><span data-stu-id="7568d-146">Follow the steps in this topic to use Topology Builder to define the listening ports a Mediation Server or pool will accept incoming connections from a gateway peer.</span></span>
  
### <a name="to-modify-the-mediation-server-listening-ports"></a><span data-ttu-id="7568d-147">Чтобы изменить порты прослушивания сервера посредника</span><span class="sxs-lookup"><span data-stu-id="7568d-147">To Modify the Mediation Server Listening Ports</span></span>

1. <span data-ttu-id="7568d-148">Запустите построитель топологий: Нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы**, щелкните **Скайп для Business Server 2015**и нажмите кнопку **Скайп для построителя 2015Topology Business Server**.</span><span class="sxs-lookup"><span data-stu-id="7568d-148">Start Topology Builder: Click **Start**, click **All Programs**, click **Skype for Business Server 2015**, and then click **Skype for Business Server 2015Topology Builder**.</span></span>
    
2. <span data-ttu-id="7568d-149">В построителе топологий, в дереве консоли разверните узел **Пулы-посредники** и щелкните правой кнопкой мыши ранее созданный сервер-посредник.</span><span class="sxs-lookup"><span data-stu-id="7568d-149">In Topology Builder, in the console tree, expand the **Mediation pools** node, and right-click the Mediation Server previously created.</span></span>
    
3. <span data-ttu-id="7568d-150">По умолчанию портов прослушивания SIP на сервер-посредник, 5070 TLS трафика из Скайп для Business Server и 5067 для TLS-трафика от коллег (например, шлюзы, PBXes или SBC).</span><span class="sxs-lookup"><span data-stu-id="7568d-150">By default, the SIP listening ports on the Mediation Server are 5070 for TLS traffic from Skype for Business Server, and 5067 for TLS traffic from peers (such as gateways, PBXes, or SBCs).</span></span> <span data-ttu-id="7568d-151">TCP-порт по умолчанию отключен.</span><span class="sxs-lookup"><span data-stu-id="7568d-151">TCP port is disabled by default.</span></span> <span data-ttu-id="7568d-152">Необходимо включить TCP-порт, если имеются шлюзы, не поддерживающие TLS.</span><span class="sxs-lookup"><span data-stu-id="7568d-152">You must enable TCP port if you have gateways that do not support TLS.</span></span>
    
4. <span data-ttu-id="7568d-153">Укажите желаемую TLS или TCP диапазон портов прослушивания сервера-посредника будет принимать входящие подключения от шлюзов ТСОП.</span><span class="sxs-lookup"><span data-stu-id="7568d-153">Specify the desired TLS or TCP listening port range the Mediation Server will accept incoming connections from PSTN gateways.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="7568d-p107">Ввод диапазона портов TCP не обязателен, если не установлен флажок **Включить порт TCP**. Это настройка не обязательна.</span><span class="sxs-lookup"><span data-stu-id="7568d-p107">Entering a TCP port range is not required if **Enable TCP port** is not checked. This setting is optional.</span></span>
  

