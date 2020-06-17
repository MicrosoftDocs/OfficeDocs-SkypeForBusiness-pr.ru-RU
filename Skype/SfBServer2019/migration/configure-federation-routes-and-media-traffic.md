---
title: Настройка маршрутов федерации и трафика мультимедиа
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
description: Федерация — это доверительные отношения между двумя или более SIP-доменами, которые позволяют пользователям в различных организациях обмениваться информацией через сетевые границы. После миграции в пилотный пул необходимо выполнить переход с маршрута Федерации предыдущих версий пограничных серверов на маршрут Федерации пограничных серверов Skype для бизнеса Server 2019.
ms.openlocfilehash: 2fafe991b8d09a477d084bdf2081d240e4830589
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/16/2020
ms.locfileid: "44754039"
---
# <a name="configure-federation-routes-and-media-traffic"></a><span data-ttu-id="641b9-104">Настройка маршрутов федерации и трафика мультимедиа</span><span class="sxs-lookup"><span data-stu-id="641b9-104">Configure federation routes and media traffic</span></span>

<span data-ttu-id="641b9-105">Федерация — это доверительные отношения между двумя или более SIP-доменами, которые позволяют пользователям в различных организациях обмениваться информацией через сетевые границы.</span><span class="sxs-lookup"><span data-stu-id="641b9-105">Federation is a trust relationship between two or more SIP domains that permits users in separate organizations to communicate across network boundaries.</span></span> <span data-ttu-id="641b9-106">После миграции в пилотный пул необходимо перейти от маршрута Федерации пограничных серверов предыдущей версии к маршруту Федерации пограничных серверов Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="641b9-106">After you migrate to your pilot pool, you need to transition from the federation route of your previous version's Edge Servers to the federation route of your Skype for Business Server 2019 Edge Servers.</span></span>
  
<span data-ttu-id="641b9-107">Используйте следующие процедуры для переноса маршрута Федерации и маршрута передачи данных с пограничного сервера и директора на пограничный сервер Skype для бизнеса Server 2019 для развертывания с одним сайтом.</span><span class="sxs-lookup"><span data-stu-id="641b9-107">Use the following procedures to transition the federation route and the media traffic route from your previous version's Edge Server and Director to your Skype for Business Server 2019 Edge Server, for a single-site deployment.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="641b9-108">Для изменения маршрута Федерации и маршрута трафика мультимедиа необходимо запланировать время простоя обслуживания для пограничных серверов Skype для бизнеса Server 2019 и предыдущих версий.</span><span class="sxs-lookup"><span data-stu-id="641b9-108">Changing the federation route and media traffic route requires that you schedule maintenance downtime for the Skype for Business Server 2019 and previous version Edge Servers.</span></span> <span data-ttu-id="641b9-109">Весь процесс перехода также означает, что федеративный доступ будет отключен во время простоя.</span><span class="sxs-lookup"><span data-stu-id="641b9-109">This entire transition process also means that federated access will be unavailable for the duration of the outage.</span></span> <span data-ttu-id="641b9-110">Следует запланировать простой на период, когда активность пользователей будет минимальной.</span><span class="sxs-lookup"><span data-stu-id="641b9-110">You should schedule the downtime for a time when you expect minimal user activity.</span></span> <span data-ttu-id="641b9-111">Также следует реализовать своевременное уведомление конечных пользователей.</span><span class="sxs-lookup"><span data-stu-id="641b9-111">You should also provide sufficient notification to your end users.</span></span> <span data-ttu-id="641b9-112">Тщательно запланируйте простой и задайте соответствующие ожидания в организации.</span><span class="sxs-lookup"><span data-stu-id="641b9-112">Plan accordingly for this outage and set appropriate expectations within your organization.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="641b9-113">Если устаревший пограничный сервер настроен на использование того же полного доменного имени для пограничной службы доступа, пограничной службы веб-конференций и пограничной службы аудио-и видеоданных, процедуры, описанные в этом разделе, не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="641b9-113">If your legacy Edge Server is configured to use the same FQDN for the Access Edge service, Web Conferencing Edge service, and the A/V Edge service, the procedures in this section are not supported.</span></span> <span data-ttu-id="641b9-114">Если устаревшие пограничные службы настроены на использование одного полного доменного имени, необходимо сначала перенести всех пользователей, а затем списать пограничный сервер предыдущих версий перед включением Федерации на пограничном сервере Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="641b9-114">If the legacy Edge services are configured to use the same FQDN, you must first migrate all your users, then decommission the previous versions Edge Server before enabling federation on the Skype for Business Server 2019 Edge Server.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="641b9-115">Если Федерация XMPP направляется через пограничный сервер Skype для бизнеса Server 2019, пользователи предыдущей версии не смогут общаться с федеративным партнером XMPP до тех пор, пока все пользователи не будут перемещены в Skype для бизнеса Server 2019, политики XMPP и сертификаты настроены, а федеративный партнер XMPP настроен на Skype для бизнеса Server 2019 , а наконец, записи DNS были обновлены.</span><span class="sxs-lookup"><span data-stu-id="641b9-115">If your XMPP federation is routed through a Skype for Business Server 2019 Edge Server, users on the previous version will not be able to communicate with the XMPP federated partner until all users have been moved to Skype for Business Server 2019, XMPP policies and certificates have been configured, the XMPP federated partner has been configured on Skype for Business Server 2019, and, lastly, the DNS entries have been updated.</span></span> 
  
## <a name="to-remove-the-legacy-federation-association-from-skype-for-business-server-2019-sites"></a><span data-ttu-id="641b9-116">Удаление устаревшей связи Федерации на сайтах Skype для бизнеса Server 2019</span><span class="sxs-lookup"><span data-stu-id="641b9-116">To remove the legacy federation association from Skype for Business Server 2019 sites</span></span>

1. <span data-ttu-id="641b9-117">На сервере переднего плана Skype для бизнеса Server 2019 откройте существующую топологию в построителе топологий.</span><span class="sxs-lookup"><span data-stu-id="641b9-117">On the Skype for Business Server 2019 Front End server, open the existing topology in Topology Builder.</span></span> 
    
2. <span data-ttu-id="641b9-118">В левой области перейдите к узлу сайта, расположенному непосредственно под **Skype для бизнеса Server**.</span><span class="sxs-lookup"><span data-stu-id="641b9-118">In the left pane, navigate to the site node, which is located directly below **Skype for Business Server**.</span></span>
    
3. <span data-ttu-id="641b9-119">Щелкните сайт правой кнопкой мыши и выберите команду **Изменить свойства**.</span><span class="sxs-lookup"><span data-stu-id="641b9-119">Right-click the site, and then click **Edit Properties**.</span></span>
    
4. <span data-ttu-id="641b9-120">В левой области выберите **Федеративный маршрут**.</span><span class="sxs-lookup"><span data-stu-id="641b9-120">In the left pane, select **Federation route**.</span></span> 
    
5. <span data-ttu-id="641b9-121">В разделе **назначение федеративного маршрута сайта**снимите флажок **включить SIP-Федерацию** , чтобы отключить маршрутизацию Федерации через устаревшую среду.</span><span class="sxs-lookup"><span data-stu-id="641b9-121">Under **Site federation route assignment**, clear the **Enable SIP federation** check box to disable the federation route through the legacy environment.</span></span> 
  
6. <span data-ttu-id="641b9-122">Нажмите кнопку **ОК**, чтобы закрыть страницу "Изменение свойств".</span><span class="sxs-lookup"><span data-stu-id="641b9-122">Click **OK** to close the Edit Properties page.</span></span> 
    
7. <span data-ttu-id="641b9-123">В **построителе топологий**выберите верхний узел в **Skype для бизнеса Server**.</span><span class="sxs-lookup"><span data-stu-id="641b9-123">From **Topology Builder**, select the top node **Skype for Business Server**.</span></span>
    
8. <span data-ttu-id="641b9-124">В меню **Действие** выберите пункт **Опубликовать топологию**.</span><span class="sxs-lookup"><span data-stu-id="641b9-124">From the **Action** menu, click **Publish Topology**.</span></span>
    
9. <span data-ttu-id="641b9-125">Нажмите кнопку **Далее** , чтобы завершить процесс публикации, а затем нажмите кнопку **Готово** после завершения процесса публикации.</span><span class="sxs-lookup"><span data-stu-id="641b9-125">Click **Next** to complete the publishing process, and then click **Finish** when the publishing process has completed.</span></span> 
    
## <a name="to-configure-the-legacy-edge-server-as-a-non-federating-edge-server"></a><span data-ttu-id="641b9-126">Настройка устаревшего пограничного сервера в качестве пограничного сервера без федерации</span><span class="sxs-lookup"><span data-stu-id="641b9-126">To configure the legacy Edge Server as a non-federating Edge Server</span></span>

1. <span data-ttu-id="641b9-127">В левой области перейдите к узлу установка прежних версий, а затем к узлу **пограничные пулы** .</span><span class="sxs-lookup"><span data-stu-id="641b9-127">In the left pane, navigate to the legacy install node and then to the **Edge pools** node.</span></span> 
    
2. <span data-ttu-id="641b9-128">Щелкните правой кнопкой мыши пограничный сервер и выберите в контекстном меню пункт **Изменить свойства**.</span><span class="sxs-lookup"><span data-stu-id="641b9-128">Right-click the Edge server, and then click **Edit Properties**.</span></span>
    
3. <span data-ttu-id="641b9-129">Выберите **Общие** в левой панели.</span><span class="sxs-lookup"><span data-stu-id="641b9-129">Select **General** in the left pane.</span></span> 
    
4. <span data-ttu-id="641b9-130">Снимите флажок **включить федерацию для этого пограничного пула (порт 5061)** и нажмите кнопку **ОК** , чтобы закрыть страницу.</span><span class="sxs-lookup"><span data-stu-id="641b9-130">Clear the **Enable federation for this Edge pool (port 5061)** check box and select **OK** to close the page.</span></span> 
  
5. <span data-ttu-id="641b9-131">В меню **Действие** выберите пункт **Публикация топологии**, а затем щелкните **Далее**.</span><span class="sxs-lookup"><span data-stu-id="641b9-131">From the **Action** menu, select **Publish Topology**, and then click **Next**.</span></span>
    
6. <span data-ttu-id="641b9-132">После завершения работы **мастера публикации**, нажмите кнопку **Готово**, чтобы закрыть мастер.</span><span class="sxs-lookup"><span data-stu-id="641b9-132">When the **Publishing wizard** completes, click **Finish** to close the wizard.</span></span> 
    
7. <span data-ttu-id="641b9-133">Убедитесь, что в построителе топологий отключена Федерация для устаревшего пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="641b9-133">Verify that federation for the legacy Edge server is disabled in Topology Builder.</span></span>
  
## <a name="to-configure-certificates-on-the-legacy-edge-server"></a><span data-ttu-id="641b9-134">Настройка сертификатов на пограничных серверах прежних версий</span><span class="sxs-lookup"><span data-stu-id="641b9-134">To configure certificates on the legacy Edge Server</span></span>

1. <span data-ttu-id="641b9-135">Экспортируйте сертификат прокси внешнего доступа с закрытым ключом из устаревшего пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="641b9-135">Export the external Access Proxy certificate, with the private key, from the legacy Edge Server.</span></span> 
    
2. <span data-ttu-id="641b9-136">На пограничном сервере Skype для бизнеса Server 2019 и импортируйте внешний сертификат прокси-сервера доступа из предыдущего действия.</span><span class="sxs-lookup"><span data-stu-id="641b9-136">On the Skype for Business Server 2019 Edge Server, and import the Access Proxy external certificate from the previous step.</span></span>
    
3. <span data-ttu-id="641b9-137">Назначьте внешний сертификат прокси-сервера доступа внешнему интерфейсу сервера пограничного сервера Skype для бизнеса 2019.</span><span class="sxs-lookup"><span data-stu-id="641b9-137">Assign the Access Proxy external certificate to the Skype for Business Server 2019 external interface of the Edge Server.</span></span>
    
4. <span data-ttu-id="641b9-138">Сертификат внутреннего интерфейса пограничного сервера Skype для бизнеса Server 2019 должен быть запрошен доверенным центром сертификации и назначен.</span><span class="sxs-lookup"><span data-stu-id="641b9-138">The internal interface certificate of the Skype for Business Server 2019 Edge Server should be requested from a trusted CA and assigned.</span></span> 
    
## <a name="to-change-the-previous-versions-federation-route-to-use-skype-for-business-server-2019-edge-server"></a><span data-ttu-id="641b9-139">Изменение маршрута Федерации предыдущей версии для использования пограничного сервера Skype для бизнеса Server 2019</span><span class="sxs-lookup"><span data-stu-id="641b9-139">To change the previous version's federation route to use Skype for Business Server 2019 Edge Server</span></span>

1. <span data-ttu-id="641b9-140">На левой панели построителя топологий перейдите к узлу **2019 Skype для бизнеса Server** , а затем к узлу **пограничные пулы** .</span><span class="sxs-lookup"><span data-stu-id="641b9-140">From Topology Builder, in the left pane, navigate to the **Skype for Business Server 2019** node and then to the **Edge pools** node.</span></span> 
    
2. <span data-ttu-id="641b9-141">Щелкните правой кнопкой мыши пограничный сервер и выберите в контекстном меню пункт **Изменить свойства**.</span><span class="sxs-lookup"><span data-stu-id="641b9-141">Right-click the Edge server, and then click **Edit Properties**.</span></span>
    
3. <span data-ttu-id="641b9-142">Выберите **Общие** в левой панели.</span><span class="sxs-lookup"><span data-stu-id="641b9-142">Select **General** in the left pane.</span></span> 
    
4. <span data-ttu-id="641b9-143">Установите флажок **включить федерацию для этого пограничного пула (порт 5061)**, а затем нажмите кнопку **ОК** , чтобы закрыть страницу.</span><span class="sxs-lookup"><span data-stu-id="641b9-143">Select the check box for **Enable federation for this Edge pool (port 5061)**, and then click **OK** to close the page.</span></span> 
  
5. <span data-ttu-id="641b9-144">В меню **Действие** выберите пункт **Публикация топологии**, а затем щелкните **Далее**.</span><span class="sxs-lookup"><span data-stu-id="641b9-144">From the **Action** menu, select **Publish Topology**, and then click **Next**.</span></span>
    
6. <span data-ttu-id="641b9-145">После завершения работы **мастера публикации**, нажмите кнопку **Готово**, чтобы закрыть мастер.</span><span class="sxs-lookup"><span data-stu-id="641b9-145">When the **Publishing wizard** completes, click **Finish** to close the wizard.</span></span> 
    
7. <span data-ttu-id="641b9-146">Убедитесь, что в построителе топологий для **Федерации (порт 5061)** задано значение **включено** .</span><span class="sxs-lookup"><span data-stu-id="641b9-146">Verify that **Federation (port 5061)** is set to **Enabled** in Topology Builder.</span></span>
    
  
## <a name="to-update-skype-for-business-server-2019-edge-server-federation-next-hop"></a><span data-ttu-id="641b9-147">Обновление следующего прыжка для Федерации пограничного сервера в Skype для бизнеса Server 2019</span><span class="sxs-lookup"><span data-stu-id="641b9-147">To update Skype for Business Server 2019 Edge Server federation next hop</span></span>

1. <span data-ttu-id="641b9-148">На левой панели построителя топологий перейдите к узлу **2019 Skype для бизнеса Server** , а затем к узлу **пограничные пулы** .</span><span class="sxs-lookup"><span data-stu-id="641b9-148">From Topology Builder, in the left pane, navigate to the **Skype for Business Server 2019** node and then to the **Edge pools** node.</span></span> 
    
2. <span data-ttu-id="641b9-149">Разверните узел, щелкните правой кнопкой указанный пограничный сервер и выберите команду **Изменить свойства**.</span><span class="sxs-lookup"><span data-stu-id="641b9-149">Expand the node, right-click the Edge Server listed, and then click **Edit Properties**.</span></span> 
    
3. <span data-ttu-id="641b9-150">На странице **Общие** в разделе **Выбор следующего прыжка**выберите в раскрывающемся списке пул Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="641b9-150">On the **General** page, under **Next hop selection**, select from the drop-down list the Skype for Business Server 2019 pool.</span></span>
  
4. <span data-ttu-id="641b9-151">Нажмите кнопку **ОК**, чтобы закрыть страницу "Изменение свойств".</span><span class="sxs-lookup"><span data-stu-id="641b9-151">Click **OK** to close the Edit Properties page.</span></span> 
    
5. <span data-ttu-id="641b9-152">В **построителе топологий**выберите верхний узел в **Skype для бизнеса Server**.</span><span class="sxs-lookup"><span data-stu-id="641b9-152">From **Topology Builder**, select the top node **Skype for Business Server**.</span></span> 
    
6. <span data-ttu-id="641b9-153">В меню **Действие** выберите команду **Опубликовать топологию** и завершите работу мастера.</span><span class="sxs-lookup"><span data-stu-id="641b9-153">From the **Action** menu, click **Publish Topology** and complete the wizard.</span></span> 
    
## <a name="to-configure-skype-for-business-server-2019-edge-server-outbound-media-path"></a><span data-ttu-id="641b9-154">Настройка пути исходящей почты для сервера пограничного сервера Skype для бизнеса Server 2019</span><span class="sxs-lookup"><span data-stu-id="641b9-154">To configure Skype for Business Server 2019 Edge Server outbound media path</span></span>

1. <span data-ttu-id="641b9-155">На левой панели построителя топологий перейдите к узлу **Skype для бизнеса Server 2019** , а затем к пулу под **стандартным интерфейсным сервером Standard Edition** или **интерфейсным пулам Enterprise Edition**.</span><span class="sxs-lookup"><span data-stu-id="641b9-155">From Topology Builder, in the left pane, navigate to the **Skype for Business Server 2019** node and then to the pool below **Standard Edition Front End Servers** or **Enterprise Edition Front End pools**.</span></span>
    
2. <span data-ttu-id="641b9-156">Щелкните пул правой кнопкой мыши и выберите команду **Изменить свойства**.</span><span class="sxs-lookup"><span data-stu-id="641b9-156">Right-click the pool, and then click **Edit Properties**.</span></span>
    
3. <span data-ttu-id="641b9-157">В разделе **Связи** установите флажок **Связать пограничный пул (для компонентов мультимедиа)**.</span><span class="sxs-lookup"><span data-stu-id="641b9-157">In the **Associations** section, select the **Associate Edge pool (for media components)** check box.</span></span> 
  
4. <span data-ttu-id="641b9-158">В раскрывающемся списке выберите Пограничный сервер Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="641b9-158">From the drop-down box, select the Skype for Business Server 2019 Edge Server.</span></span>
    
5. <span data-ttu-id="641b9-159">Нажмите кнопку **ОК**, чтобы закрыть страницу **изменения свойств**.</span><span class="sxs-lookup"><span data-stu-id="641b9-159">Click **OK** to close the **Edit Properties** page.</span></span> 
    
## <a name="to-turn-on-skype-for-business-server-2019-edge-server-federation"></a><span data-ttu-id="641b9-160">Включение Федерации пограничного сервера в Skype для бизнеса Server 2019</span><span class="sxs-lookup"><span data-stu-id="641b9-160">To turn on Skype for Business Server 2019 Edge Server federation</span></span>

1. <span data-ttu-id="641b9-161">На левой панели построителя топологий перейдите к узлу **2019 Skype для бизнеса Server** , а затем к узлу **пограничные пулы** .</span><span class="sxs-lookup"><span data-stu-id="641b9-161">From Topology Builder, in the left pane, navigate to the **Skype for Business Server 2019** node and then to the **Edge pools** node.</span></span> 
    
2. <span data-ttu-id="641b9-162">Разверните узел, щелкните правой кнопкой указанный пограничный сервер и выберите команду **Изменить свойства**.</span><span class="sxs-lookup"><span data-stu-id="641b9-162">Expand the node, right-click the Edge Server listed, and then click **Edit Properties**.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="641b9-163">Федерация можно включить только для одного пограничного пула.</span><span class="sxs-lookup"><span data-stu-id="641b9-163">Federation can only be enabled for a single Edge pool.</span></span> <span data-ttu-id="641b9-164">Если у вас несколько пограничных пулов, выберите один из них, который будет использоваться в качестве Федерации пограничного пула.</span><span class="sxs-lookup"><span data-stu-id="641b9-164">If you have multiple Edge pools, select one to use as the federating Edge pool.</span></span> 
  
3. <span data-ttu-id="641b9-165">На странице " **Общие** " убедитесь, что установлен флажок **включить федерацию для этого пограничного пула (порт 5061)** .</span><span class="sxs-lookup"><span data-stu-id="641b9-165">On the **General** page, verify that the **Enable federation for this Edge pool (Port 5061)** check box is selected.</span></span> 
  
4. <span data-ttu-id="641b9-166">Нажмите кнопку **ОК**, чтобы закрыть страницу "Изменение свойств".</span><span class="sxs-lookup"><span data-stu-id="641b9-166">Click **OK** to close the Edit Properties page.</span></span> 
    
5. <span data-ttu-id="641b9-167">Перейдите к узлу сайта.</span><span class="sxs-lookup"><span data-stu-id="641b9-167">Navigate to the site node.</span></span> 
    
6. <span data-ttu-id="641b9-168">Щелкните сайт правой кнопкой мыши и выберите команду **Изменить свойства**.</span><span class="sxs-lookup"><span data-stu-id="641b9-168">Right-click the site, and then click **Edit Properties**.</span></span>
    
7. <span data-ttu-id="641b9-169">В левой области, выберите **Федеративный маршрут**.</span><span class="sxs-lookup"><span data-stu-id="641b9-169">In the left pane, click **Federation route**.</span></span>
    
8. <span data-ttu-id="641b9-170">В разделе **назначение федеративного маршрута сайта**выберите **включить федерацию SIP**, а затем в списке выберите в списке пограничный сервер Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="641b9-170">Under **Site federation route assignment**, select **Enable SIP federation**, and then from the list select the Skype for Business Server 2019 Edge Server listed.</span></span> 
  
9. <span data-ttu-id="641b9-171">Нажмите кнопку **ОК**, чтобы закрыть страницу **Изменение свойств**.</span><span class="sxs-lookup"><span data-stu-id="641b9-171">Click **OK** to close the **Edit Properties** page.</span></span> 
    
     <span data-ttu-id="641b9-172">В случае развертывании с несколькими сайтами выполните эту процедуру на каждом сайте.</span><span class="sxs-lookup"><span data-stu-id="641b9-172">For multi-site deployments, complete this procedure at each site.</span></span> 
    
## <a name="to-publish-edge-server-configuration-changes"></a><span data-ttu-id="641b9-173">Публикация изменений конфигурации пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="641b9-173">To publish Edge Server configuration changes</span></span>

1. <span data-ttu-id="641b9-174">В **построителе топологий**выберите верхний узел в **Skype для бизнеса Server**.</span><span class="sxs-lookup"><span data-stu-id="641b9-174">From **Topology Builder**, select the top node **Skype for Business Server**.</span></span> 
    
2. <span data-ttu-id="641b9-175">В меню **Действие** выберите команду **Опубликовать топологию** и завершите работу мастера.</span><span class="sxs-lookup"><span data-stu-id="641b9-175">From the **Action** menu, select **Publish Topology** and complete the wizard.</span></span> 
    
3. <span data-ttu-id="641b9-176">Дождитесь выполнения репликации Active Directory во всех пулах в развертывании.</span><span class="sxs-lookup"><span data-stu-id="641b9-176">Wait for Active Directory replication to occur to all pools in the deployment.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="641b9-177">Вы можете увидеть следующее сообщение: **Предупреждение: Топология содержит более одного федеративного пограничного сервера. Это может произойти во время миграции до более поздней версии продукта. В этом случае только один пограничный сервер будет активно использоваться для Федерации. Убедитесь, что внешняя запись SRV DNS указывает на правильный пограничный сервер. Если вы хотите одновременно развернуть несколько пограничных серверов федерации (то есть не в сценарии миграции), убедитесь, что все Федеративные партнеры используют Skype для бизнеса Server. Убедитесь, что внешняя запись DNS SRV содержит все пограничные серверы с включенной поддержкой Федерации.**</span><span class="sxs-lookup"><span data-stu-id="641b9-177">You may see the following message: **Warning: The topology contains more than one Federated Edge Server. This can occur during migration to a more recent version of the product. In that case, only one Edge Server would be actively used for federation. Verify that the external DNS SRV record points to the correct Edge Server. If you want to deploy multiple federation Edge Server to be active concurrently (that is, not a migration scenario), verify that all federated partners are using Skype for Business Server. Verify that the external DNS SRV record lists all federation enabled Edge Servers.**</span></span> <span data-ttu-id="641b9-178">Появление этого предупреждения ожидаемое и его можно спокойно проигнорировать.</span><span class="sxs-lookup"><span data-stu-id="641b9-178">This warning is expected and can be safely ignored.</span></span> 
  
## <a name="to-configure-skype-for-business-server-2019-edge-server"></a><span data-ttu-id="641b9-179">Настройка пограничного сервера Skype для бизнеса Server 2019</span><span class="sxs-lookup"><span data-stu-id="641b9-179">To configure Skype for Business Server 2019 Edge Server</span></span>

1. <span data-ttu-id="641b9-180">Перевод всех пограничных серверов Skype для бизнеса Server 2019 в оперативный режим.</span><span class="sxs-lookup"><span data-stu-id="641b9-180">Bring all of the Skype for Business Server 2019 Edge Servers online.</span></span> 
    
2. <span data-ttu-id="641b9-181">Обновите правила маршрутизации внешних брандмауэров или параметры аппаратного балансировщика нагрузки, чтобы отправлять трафик SIP для внешнего доступа (обычно это порт 443) и Федерацию (обычно это порт 5061) на пограничный сервер Skype для бизнеса Server 2019 вместо устаревшего пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="641b9-181">Update the external firewall routing rules or the hardware load balancer settings to send SIP traffic for external access (usually port 443) and federation (usually port 5061) to the Skype for Business Server 2019 Edge Server, instead of the legacy Edge Server.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="641b9-182">Если у вас нет аппаратной подсистемы балансировки нагрузки, необходимо обновить запись DNS A для Федерации, чтобы устранить проблему с новым пограничным сервером доступа Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="641b9-182">If you do not have a hardware load balancer, you need to update the DNS A record for federation to resolve to the new Skype for Business Server Access Edge server.</span></span> <span data-ttu-id="641b9-183">Чтобы сделать это в минимальном случае, уменьшите значение ТЛЛ для внешнего полного доменного имени доступа Skype для бизнеса Server, чтобы при обновлении DNS до ссылки на новый сервер пограничного доступа Skype для бизнеса Server, Федерация и удаленный доступ будут быстро обновлены.</span><span class="sxs-lookup"><span data-stu-id="641b9-183">To accomplish this with minimal disruption, reduce the TLL value for the external Skype for Business Server Access Edge FQDN so that when DNS is updated to point to the new Skype for Business Server Access Edge, federation and remote access will be updated quickly.</span></span> 
  
3. <span data-ttu-id="641b9-184">Остановите пограничный сервер **для доступа к Skype для бизнеса Server** с каждого компьютера пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="641b9-184">Stop the **Skype for Business Server Access Edge** from each Edge Server computer.</span></span> 
    
4. <span data-ttu-id="641b9-185">На каждом компьютере пограничного сервера пограничного сервера откройте приложение **службы** в **средстве администрирования**.</span><span class="sxs-lookup"><span data-stu-id="641b9-185">From each legacy Edge Server computer, open the **Services** applet from the **Administrative Tools**.</span></span>
    
5. <span data-ttu-id="641b9-186">В списке служб найдите **пограничный сервер доступа Skype для бизнеса Server**.</span><span class="sxs-lookup"><span data-stu-id="641b9-186">In the services list, find **Skype for Business Server Access Edge**.</span></span>
    
6. <span data-ttu-id="641b9-187">Щелкните правой кнопкой имя служб, а затем выберите команду **Остановить**, чтобы остановить службу.</span><span class="sxs-lookup"><span data-stu-id="641b9-187">Right-click the services name, and then select **Stop** to stop the service.</span></span> 
    
7. <span data-ttu-id="641b9-188">Выберите тип запуска **Отключено**.</span><span class="sxs-lookup"><span data-stu-id="641b9-188">Set the Startup type to **Disabled**.</span></span> 
    
8. <span data-ttu-id="641b9-189">Нажмите кнопку **ОК**, чтобы закрыть окно **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="641b9-189">Click **OK** to close the **Properties** window.</span></span> 
    

