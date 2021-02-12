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
description: Федерация — это доверительные отношения между двумя или более SIP-доменами, которые позволяют пользователям в различных организациях обмениваться информацией через сетевые границы. После миграции в пилотный пул необходимо перейти с федера>федера>маршрутов серверов предыдущих версий на федерательный маршрут для ваших серверов Skype для бизнеса Server 2019.
ms.openlocfilehash: 2fafe991b8d09a477d084bdf2081d240e4830589
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/16/2020
ms.locfileid: "44754039"
---
# <a name="configure-federation-routes-and-media-traffic"></a><span data-ttu-id="c177f-104">Настройка маршрутов федерации и трафика мультимедиа</span><span class="sxs-lookup"><span data-stu-id="c177f-104">Configure federation routes and media traffic</span></span>

<span data-ttu-id="c177f-105">Федерация — это доверительные отношения между двумя или более SIP-доменами, которые позволяют пользователям в различных организациях обмениваться информацией через сетевые границы.</span><span class="sxs-lookup"><span data-stu-id="c177f-105">Federation is a trust relationship between two or more SIP domains that permits users in separate organizations to communicate across network boundaries.</span></span> <span data-ttu-id="c177f-106">После миграции в пилотный пул необходимо перейти с федера>федера>маршрутов серверов предыдущей версии на федерательный маршрут для ваших серверов Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="c177f-106">After you migrate to your pilot pool, you need to transition from the federation route of your previous version's Edge Servers to the federation route of your Skype for Business Server 2019 Edge Servers.</span></span>
  
<span data-ttu-id="c177f-107">Используйте следующие процедуры для перехода федератора и маршрута трафика мультимедиа с сервера и директора предыдущей версии на сервер Skype для бизнеса Server 2019 для развертывания на одном сайте.</span><span class="sxs-lookup"><span data-stu-id="c177f-107">Use the following procedures to transition the federation route and the media traffic route from your previous version's Edge Server and Director to your Skype for Business Server 2019 Edge Server, for a single-site deployment.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="c177f-108">Для изменения маршрута федерации и маршрута трафика мультимедиа необходимо запланировать простои обслуживания для skype для бизнеса Server 2019 и серверов предыдущей версии.</span><span class="sxs-lookup"><span data-stu-id="c177f-108">Changing the federation route and media traffic route requires that you schedule maintenance downtime for the Skype for Business Server 2019 and previous version Edge Servers.</span></span> <span data-ttu-id="c177f-109">Весь процесс перехода также означает, что федеративный доступ будет отключен во время простоя.</span><span class="sxs-lookup"><span data-stu-id="c177f-109">This entire transition process also means that federated access will be unavailable for the duration of the outage.</span></span> <span data-ttu-id="c177f-110">Следует запланировать простой на период, когда активность пользователей будет минимальной.</span><span class="sxs-lookup"><span data-stu-id="c177f-110">You should schedule the downtime for a time when you expect minimal user activity.</span></span> <span data-ttu-id="c177f-111">Также следует реализовать своевременное уведомление конечных пользователей.</span><span class="sxs-lookup"><span data-stu-id="c177f-111">You should also provide sufficient notification to your end users.</span></span> <span data-ttu-id="c177f-112">Тщательно запланируйте простой и задайте соответствующие ожидания в организации.</span><span class="sxs-lookup"><span data-stu-id="c177f-112">Plan accordingly for this outage and set appropriate expectations within your organization.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="c177f-113">Если устаревший edge-сервер настроен на использование одного и того же FQDN для службы доступа, службы веб-службы и службы A/V Edge, процедуры в этом разделе не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="c177f-113">If your legacy Edge Server is configured to use the same FQDN for the Access Edge service, Web Conferencing Edge service, and the A/V Edge service, the procedures in this section are not supported.</span></span> <span data-ttu-id="c177f-114">If the legacy Edge services are configured to use the same FQDN, you must first migrate all your users, then decommission the previous versions Edge Server before enabling federation on the Skype for Business Server 2019 Edge Server.</span><span class="sxs-lookup"><span data-stu-id="c177f-114">If the legacy Edge services are configured to use the same FQDN, you must first migrate all your users, then decommission the previous versions Edge Server before enabling federation on the Skype for Business Server 2019 Edge Server.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="c177f-115">If your XMPP federation is routed through a Skype for Business Server 2019 Edge Server, users on the previous version will not be able to communicate with the XMPP federated partner until all users have been moved to Skype for Business Server 2019, XMPP policies and certificates have been configured, the XMPP federated partner has been configured on Skype for Business Server 2019 , и, наконец, были обновлены записи DNS.</span><span class="sxs-lookup"><span data-stu-id="c177f-115">If your XMPP federation is routed through a Skype for Business Server 2019 Edge Server, users on the previous version will not be able to communicate with the XMPP federated partner until all users have been moved to Skype for Business Server 2019, XMPP policies and certificates have been configured, the XMPP federated partner has been configured on Skype for Business Server 2019, and, lastly, the DNS entries have been updated.</span></span> 
  
## <a name="to-remove-the-legacy-federation-association-from-skype-for-business-server-2019-sites"></a><span data-ttu-id="c177f-116">Удаление устаревшей связи федерации с сайтов Skype для бизнеса Server 2019</span><span class="sxs-lookup"><span data-stu-id="c177f-116">To remove the legacy federation association from Skype for Business Server 2019 sites</span></span>

1. <span data-ttu-id="c177f-117">На сервере переднего сервера Skype для бизнеса Server 2019 откройте существующую топологию в построителье топологий.</span><span class="sxs-lookup"><span data-stu-id="c177f-117">On the Skype for Business Server 2019 Front End server, open the existing topology in Topology Builder.</span></span> 
    
2. <span data-ttu-id="c177f-118">В левой области перейдите к узлу сайта, расположенного непосредственно под **Skype для бизнеса Server.**</span><span class="sxs-lookup"><span data-stu-id="c177f-118">In the left pane, navigate to the site node, which is located directly below **Skype for Business Server**.</span></span>
    
3. <span data-ttu-id="c177f-119">Щелкните сайт правой кнопкой мыши и выберите команду **Изменить свойства**.</span><span class="sxs-lookup"><span data-stu-id="c177f-119">Right-click the site, and then click **Edit Properties**.</span></span>
    
4. <span data-ttu-id="c177f-120">В левой области выберите **Федеративный маршрут**.</span><span class="sxs-lookup"><span data-stu-id="c177f-120">In the left pane, select **Federation route**.</span></span> 
    
5. <span data-ttu-id="c177f-121">В области назначения маршрута  федерации **сайта** с помощью этого окне с помощью этого окне необходимо отключить федерацийный маршрут через устаревшую среду.</span><span class="sxs-lookup"><span data-stu-id="c177f-121">Under **Site federation route assignment**, clear the **Enable SIP federation** check box to disable the federation route through the legacy environment.</span></span> 
  
6. <span data-ttu-id="c177f-122">Нажмите кнопку **ОК**, чтобы закрыть страницу "Изменение свойств".</span><span class="sxs-lookup"><span data-stu-id="c177f-122">Click **OK** to close the Edit Properties page.</span></span> 
    
7. <span data-ttu-id="c177f-123">В **построителье** топологий выберите верхний узел **Skype для бизнеса Server.**</span><span class="sxs-lookup"><span data-stu-id="c177f-123">From **Topology Builder**, select the top node **Skype for Business Server**.</span></span>
    
8. <span data-ttu-id="c177f-124">В меню **Действие** выберите пункт **Опубликовать топологию**.</span><span class="sxs-lookup"><span data-stu-id="c177f-124">From the **Action** menu, click **Publish Topology**.</span></span>
    
9. <span data-ttu-id="c177f-125">Нажмите **кнопку** "Далее", чтобы завершить процесс публикации, а затем нажмите кнопку **"Готово"** после завершения публикации.</span><span class="sxs-lookup"><span data-stu-id="c177f-125">Click **Next** to complete the publishing process, and then click **Finish** when the publishing process has completed.</span></span> 
    
## <a name="to-configure-the-legacy-edge-server-as-a-non-federating-edge-server"></a><span data-ttu-id="c177f-126">Настройка устаревшего пограничного сервера в качестве пограничного сервера без федерации</span><span class="sxs-lookup"><span data-stu-id="c177f-126">To configure the legacy Edge Server as a non-federating Edge Server</span></span>

1. <span data-ttu-id="c177f-127">В левой области перейдите к устаревшему узлу установки, а затем к узлу **"Пулы edge".**</span><span class="sxs-lookup"><span data-stu-id="c177f-127">In the left pane, navigate to the legacy install node and then to the **Edge pools** node.</span></span> 
    
2. <span data-ttu-id="c177f-128">Щелкните правой кнопкой мыши пограничный сервер и выберите в контекстном меню пункт **Изменить свойства**.</span><span class="sxs-lookup"><span data-stu-id="c177f-128">Right-click the Edge server, and then click **Edit Properties**.</span></span>
    
3. <span data-ttu-id="c177f-129">Выберите **Общие** в левой панели.</span><span class="sxs-lookup"><span data-stu-id="c177f-129">Select **General** in the left pane.</span></span> 
    
4. <span data-ttu-id="c177f-130">Clear the **Enable federation for this Edge pool (port 5061)** check box and select **OK** to close the page.</span><span class="sxs-lookup"><span data-stu-id="c177f-130">Clear the **Enable federation for this Edge pool (port 5061)** check box and select **OK** to close the page.</span></span> 
  
5. <span data-ttu-id="c177f-131">В меню **Действие** выберите пункт **Публикация топологии**, а затем щелкните **Далее**.</span><span class="sxs-lookup"><span data-stu-id="c177f-131">From the **Action** menu, select **Publish Topology**, and then click **Next**.</span></span>
    
6. <span data-ttu-id="c177f-132">После завершения работы **мастера публикации**, нажмите кнопку **Готово**, чтобы закрыть мастер.</span><span class="sxs-lookup"><span data-stu-id="c177f-132">When the **Publishing wizard** completes, click **Finish** to close the wizard.</span></span> 
    
7. <span data-ttu-id="c177f-133">Убедитесь, что федерация для устаревшего сервера в построителье топологий отключена.</span><span class="sxs-lookup"><span data-stu-id="c177f-133">Verify that federation for the legacy Edge server is disabled in Topology Builder.</span></span>
  
## <a name="to-configure-certificates-on-the-legacy-edge-server"></a><span data-ttu-id="c177f-134">Настройка сертификатов на устаревшем сервере</span><span class="sxs-lookup"><span data-stu-id="c177f-134">To configure certificates on the legacy Edge Server</span></span>

1. <span data-ttu-id="c177f-135">Экспортировать сертификат внешнего прокси-сервера доступа с закрытым ключом с устаревшего сервера.</span><span class="sxs-lookup"><span data-stu-id="c177f-135">Export the external Access Proxy certificate, with the private key, from the legacy Edge Server.</span></span> 
    
2. <span data-ttu-id="c177f-136">На сервере Skype для бизнеса Server 2019 и импортировать внешний сертификат прокси-сервера Доступа из предыдущего шага.</span><span class="sxs-lookup"><span data-stu-id="c177f-136">On the Skype for Business Server 2019 Edge Server, and import the Access Proxy external certificate from the previous step.</span></span>
    
3. <span data-ttu-id="c177f-137">Назначьте внешний сертификат прокси-сервера доступа внешнему интерфейсу Skype для бизнеса Server 2019 на edge Server.</span><span class="sxs-lookup"><span data-stu-id="c177f-137">Assign the Access Proxy external certificate to the Skype for Business Server 2019 external interface of the Edge Server.</span></span>
    
4. <span data-ttu-id="c177f-138">Сертификат внутреннего интерфейса сервера Skype для бизнеса Server 2019 необходимо запросить у доверенного ЦС и на назначенном ему.</span><span class="sxs-lookup"><span data-stu-id="c177f-138">The internal interface certificate of the Skype for Business Server 2019 Edge Server should be requested from a trusted CA and assigned.</span></span> 
    
## <a name="to-change-the-previous-versions-federation-route-to-use-skype-for-business-server-2019-edge-server"></a><span data-ttu-id="c177f-139">Изменение маршрута федерации предыдущей версии на использование skype для бизнеса Server 2019 Edge Server</span><span class="sxs-lookup"><span data-stu-id="c177f-139">To change the previous version's federation route to use Skype for Business Server 2019 Edge Server</span></span>

1. <span data-ttu-id="c177f-140">From Topology Builder, in the left pane, navigate to the **Skype for Business Server 2019** node and then to the Edge **pools** node.</span><span class="sxs-lookup"><span data-stu-id="c177f-140">From Topology Builder, in the left pane, navigate to the **Skype for Business Server 2019** node and then to the **Edge pools** node.</span></span> 
    
2. <span data-ttu-id="c177f-141">Щелкните правой кнопкой мыши пограничный сервер и выберите в контекстном меню пункт **Изменить свойства**.</span><span class="sxs-lookup"><span data-stu-id="c177f-141">Right-click the Edge server, and then click **Edit Properties**.</span></span>
    
3. <span data-ttu-id="c177f-142">Выберите **Общие** в левой панели.</span><span class="sxs-lookup"><span data-stu-id="c177f-142">Select **General** in the left pane.</span></span> 
    
4. <span data-ttu-id="c177f-143">Выберите для этого пула **(порт 5061)** включить федерацию, а затем нажмите кнопку "ОК", чтобы закрыть страницу. </span><span class="sxs-lookup"><span data-stu-id="c177f-143">Select the check box for **Enable federation for this Edge pool (port 5061)**, and then click **OK** to close the page.</span></span> 
  
5. <span data-ttu-id="c177f-144">В меню **Действие** выберите пункт **Публикация топологии**, а затем щелкните **Далее**.</span><span class="sxs-lookup"><span data-stu-id="c177f-144">From the **Action** menu, select **Publish Topology**, and then click **Next**.</span></span>
    
6. <span data-ttu-id="c177f-145">После завершения работы **мастера публикации**, нажмите кнопку **Готово**, чтобы закрыть мастер.</span><span class="sxs-lookup"><span data-stu-id="c177f-145">When the **Publishing wizard** completes, click **Finish** to close the wizard.</span></span> 
    
7. <span data-ttu-id="c177f-146">**Убедитесь, что для федерации (порт 5061)** установлено **"Включено"** в построителье топологий.</span><span class="sxs-lookup"><span data-stu-id="c177f-146">Verify that **Federation (port 5061)** is set to **Enabled** in Topology Builder.</span></span>
    
  
## <a name="to-update-skype-for-business-server-2019-edge-server-federation-next-hop"></a><span data-ttu-id="c177f-147">Обновление следующего перехода федерации для skype для бизнеса Server 2019</span><span class="sxs-lookup"><span data-stu-id="c177f-147">To update Skype for Business Server 2019 Edge Server federation next hop</span></span>

1. <span data-ttu-id="c177f-148">From Topology Builder, in the left pane, navigate to the **Skype for Business Server 2019** node and then to the Edge **pools** node.</span><span class="sxs-lookup"><span data-stu-id="c177f-148">From Topology Builder, in the left pane, navigate to the **Skype for Business Server 2019** node and then to the **Edge pools** node.</span></span> 
    
2. <span data-ttu-id="c177f-149">Разверните узел, щелкните правой кнопкой указанный пограничный сервер и выберите команду **Изменить свойства**.</span><span class="sxs-lookup"><span data-stu-id="c177f-149">Expand the node, right-click the Edge Server listed, and then click **Edit Properties**.</span></span> 
    
3. <span data-ttu-id="c177f-150">On the **General** page, under **Next hop selection,** select from the drop-down list the Skype for Business Server 2019 pool.</span><span class="sxs-lookup"><span data-stu-id="c177f-150">On the **General** page, under **Next hop selection**, select from the drop-down list the Skype for Business Server 2019 pool.</span></span>
  
4. <span data-ttu-id="c177f-151">Нажмите кнопку **ОК**, чтобы закрыть страницу "Изменение свойств".</span><span class="sxs-lookup"><span data-stu-id="c177f-151">Click **OK** to close the Edit Properties page.</span></span> 
    
5. <span data-ttu-id="c177f-152">В **построителье** топологий выберите верхний узел **Skype для бизнеса Server.**</span><span class="sxs-lookup"><span data-stu-id="c177f-152">From **Topology Builder**, select the top node **Skype for Business Server**.</span></span> 
    
6. <span data-ttu-id="c177f-153">В меню **Действие** выберите команду **Опубликовать топологию** и завершите работу мастера.</span><span class="sxs-lookup"><span data-stu-id="c177f-153">From the **Action** menu, click **Publish Topology** and complete the wizard.</span></span> 
    
## <a name="to-configure-skype-for-business-server-2019-edge-server-outbound-media-path"></a><span data-ttu-id="c177f-154">Настройка пути исходящие мультимедиа для сервера Skype для бизнеса Server 2019</span><span class="sxs-lookup"><span data-stu-id="c177f-154">To configure Skype for Business Server 2019 Edge Server outbound media path</span></span>

1. <span data-ttu-id="c177f-155">From Topology Builder, in the left pane, navigate to the **Skype for Business Server 2019** node and then to the pool below Standard Edition Front End **Servers** or **Enterprise Edition Front End pools**.</span><span class="sxs-lookup"><span data-stu-id="c177f-155">From Topology Builder, in the left pane, navigate to the **Skype for Business Server 2019** node and then to the pool below **Standard Edition Front End Servers** or **Enterprise Edition Front End pools**.</span></span>
    
2. <span data-ttu-id="c177f-156">Щелкните пул правой кнопкой мыши и выберите команду **Изменить свойства**.</span><span class="sxs-lookup"><span data-stu-id="c177f-156">Right-click the pool, and then click **Edit Properties**.</span></span>
    
3. <span data-ttu-id="c177f-157">В разделе **Связи** установите флажок **Связать пограничный пул (для компонентов мультимедиа)**.</span><span class="sxs-lookup"><span data-stu-id="c177f-157">In the **Associations** section, select the **Associate Edge pool (for media components)** check box.</span></span> 
  
4. <span data-ttu-id="c177f-158">В выпадаемом поле выберите сервер Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="c177f-158">From the drop-down box, select the Skype for Business Server 2019 Edge Server.</span></span>
    
5. <span data-ttu-id="c177f-159">Нажмите кнопку **ОК**, чтобы закрыть страницу **изменения свойств**.</span><span class="sxs-lookup"><span data-stu-id="c177f-159">Click **OK** to close the **Edit Properties** page.</span></span> 
    
## <a name="to-turn-on-skype-for-business-server-2019-edge-server-federation"></a><span data-ttu-id="c177f-160">Чтобы включить федерацию skype для бизнеса Server 2019 Edge Server</span><span class="sxs-lookup"><span data-stu-id="c177f-160">To turn on Skype for Business Server 2019 Edge Server federation</span></span>

1. <span data-ttu-id="c177f-161">From Topology Builder, in the left pane, navigate to the **Skype for Business Server 2019** node and then to the Edge **pools** node.</span><span class="sxs-lookup"><span data-stu-id="c177f-161">From Topology Builder, in the left pane, navigate to the **Skype for Business Server 2019** node and then to the **Edge pools** node.</span></span> 
    
2. <span data-ttu-id="c177f-162">Разверните узел, щелкните правой кнопкой указанный пограничный сервер и выберите команду **Изменить свойства**.</span><span class="sxs-lookup"><span data-stu-id="c177f-162">Expand the node, right-click the Edge Server listed, and then click **Edit Properties**.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="c177f-163">Федерацию можно включить только для одного пула.</span><span class="sxs-lookup"><span data-stu-id="c177f-163">Federation can only be enabled for a single Edge pool.</span></span> <span data-ttu-id="c177f-164">Если у вас несколько пулов, выберите один из них, который будет использовать в качестве федерательных пулов.</span><span class="sxs-lookup"><span data-stu-id="c177f-164">If you have multiple Edge pools, select one to use as the federating Edge pool.</span></span> 
  
3. <span data-ttu-id="c177f-165">На странице **"Общие"** убедитесь, что для этого пула **(порт 5061)** выбрана федерация.</span><span class="sxs-lookup"><span data-stu-id="c177f-165">On the **General** page, verify that the **Enable federation for this Edge pool (Port 5061)** check box is selected.</span></span> 
  
4. <span data-ttu-id="c177f-166">Нажмите кнопку **ОК**, чтобы закрыть страницу "Изменение свойств".</span><span class="sxs-lookup"><span data-stu-id="c177f-166">Click **OK** to close the Edit Properties page.</span></span> 
    
5. <span data-ttu-id="c177f-167">Перейдите к узлу сайта.</span><span class="sxs-lookup"><span data-stu-id="c177f-167">Navigate to the site node.</span></span> 
    
6. <span data-ttu-id="c177f-168">Щелкните сайт правой кнопкой мыши и выберите команду **Изменить свойства**.</span><span class="sxs-lookup"><span data-stu-id="c177f-168">Right-click the site, and then click **Edit Properties**.</span></span>
    
7. <span data-ttu-id="c177f-169">В левой области, выберите **Федеративный маршрут**.</span><span class="sxs-lookup"><span data-stu-id="c177f-169">In the left pane, click **Federation route**.</span></span>
    
8. <span data-ttu-id="c177f-170">Under **Site federation route assignment**, select Enable **SIP federation**, and then from the list select the Skype for Business Server 2019 Edge Server listed.</span><span class="sxs-lookup"><span data-stu-id="c177f-170">Under **Site federation route assignment**, select **Enable SIP federation**, and then from the list select the Skype for Business Server 2019 Edge Server listed.</span></span> 
  
9. <span data-ttu-id="c177f-171">Нажмите кнопку **ОК**, чтобы закрыть страницу **Изменение свойств**.</span><span class="sxs-lookup"><span data-stu-id="c177f-171">Click **OK** to close the **Edit Properties** page.</span></span> 
    
     <span data-ttu-id="c177f-172">В случае развертывании с несколькими сайтами выполните эту процедуру на каждом сайте.</span><span class="sxs-lookup"><span data-stu-id="c177f-172">For multi-site deployments, complete this procedure at each site.</span></span> 
    
## <a name="to-publish-edge-server-configuration-changes"></a><span data-ttu-id="c177f-173">Публикация изменений конфигурации пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="c177f-173">To publish Edge Server configuration changes</span></span>

1. <span data-ttu-id="c177f-174">В **построителье** топологий выберите верхний узел **Skype для бизнеса Server.**</span><span class="sxs-lookup"><span data-stu-id="c177f-174">From **Topology Builder**, select the top node **Skype for Business Server**.</span></span> 
    
2. <span data-ttu-id="c177f-175">В меню **Действие** выберите команду **Опубликовать топологию** и завершите работу мастера.</span><span class="sxs-lookup"><span data-stu-id="c177f-175">From the **Action** menu, select **Publish Topology** and complete the wizard.</span></span> 
    
3. <span data-ttu-id="c177f-176">Дождитесь выполнения репликации Active Directory во всех пулах в развертывании.</span><span class="sxs-lookup"><span data-stu-id="c177f-176">Wait for Active Directory replication to occur to all pools in the deployment.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="c177f-177">Может появиться следующее сообщение: **Warning: The topology contains more than one Federated Edge Server. Это может произойти во время миграции на более новую версию продукта. В этом случае для федерации будет активно использоваться только один сервер. Убедитесь, что внешняя запись DNS SRV указывает на правильный сервер. Если вы хотите одновременно развернуть несколько федературных edge server (т. е. не сценарий миграции), убедитесь, что все федературные партнеры используют Skype для бизнеса Server. Убедитесь, что внешняя запись DNS SRV содержит список всех включенных в федерацию серверов.**</span><span class="sxs-lookup"><span data-stu-id="c177f-177">You may see the following message: **Warning: The topology contains more than one Federated Edge Server. This can occur during migration to a more recent version of the product. In that case, only one Edge Server would be actively used for federation. Verify that the external DNS SRV record points to the correct Edge Server. If you want to deploy multiple federation Edge Server to be active concurrently (that is, not a migration scenario), verify that all federated partners are using Skype for Business Server. Verify that the external DNS SRV record lists all federation enabled Edge Servers.**</span></span> <span data-ttu-id="c177f-178">Появление этого предупреждения ожидаемое и его можно спокойно проигнорировать.</span><span class="sxs-lookup"><span data-stu-id="c177f-178">This warning is expected and can be safely ignored.</span></span> 
  
## <a name="to-configure-skype-for-business-server-2019-edge-server"></a><span data-ttu-id="c177f-179">Настройка skype для бизнеса Server 2019 Edge Server</span><span class="sxs-lookup"><span data-stu-id="c177f-179">To configure Skype for Business Server 2019 Edge Server</span></span>

1. <span data-ttu-id="c177f-180">Перенесите все серверы Skype для бизнеса Server 2019 в сетевой режим.</span><span class="sxs-lookup"><span data-stu-id="c177f-180">Bring all of the Skype for Business Server 2019 Edge Servers online.</span></span> 
    
2. <span data-ttu-id="c177f-181">Обновите правила маршрутки внешнего брандмауэра или параметры аппаратного балансира нагрузки, чтобы отправлять трафик SIP для внешнего доступа (обычно порт 443) и федерации (обычно порт 5061) на сервер Skype для бизнеса Server 2019, а не на устаревший сервер.</span><span class="sxs-lookup"><span data-stu-id="c177f-181">Update the external firewall routing rules or the hardware load balancer settings to send SIP traffic for external access (usually port 443) and federation (usually port 5061) to the Skype for Business Server 2019 Edge Server, instead of the legacy Edge Server.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="c177f-182">If you do not have a hardware load balancer, you need to update the DNS A record for federation to resolve to the new Skype for Business Server Access Edge server.</span><span class="sxs-lookup"><span data-stu-id="c177f-182">If you do not have a hardware load balancer, you need to update the DNS A record for federation to resolve to the new Skype for Business Server Access Edge server.</span></span> <span data-ttu-id="c177f-183">To accomplish this with minimal disruption, reduce the TLL value for the external Skype for Business Server Access Edge FQDN so that when DNS is updated to point to the new Skype for Business Server Access Edge, federation and remote access will be updated quickly.</span><span class="sxs-lookup"><span data-stu-id="c177f-183">To accomplish this with minimal disruption, reduce the TLL value for the external Skype for Business Server Access Edge FQDN so that when DNS is updated to point to the new Skype for Business Server Access Edge, federation and remote access will be updated quickly.</span></span> 
  
3. <span data-ttu-id="c177f-184">Остановите **по краям доступа Skype для бизнеса Server** на каждом компьютере с edge Server.</span><span class="sxs-lookup"><span data-stu-id="c177f-184">Stop the **Skype for Business Server Access Edge** from each Edge Server computer.</span></span> 
    
4. <span data-ttu-id="c177f-185">На каждом компьютере устаревшего сервера edge server откройте applet **служб** из средства **администрирования.**</span><span class="sxs-lookup"><span data-stu-id="c177f-185">From each legacy Edge Server computer, open the **Services** applet from the **Administrative Tools**.</span></span>
    
5. <span data-ttu-id="c177f-186">In the services list, find **Skype for Business Server Access Edge**.</span><span class="sxs-lookup"><span data-stu-id="c177f-186">In the services list, find **Skype for Business Server Access Edge**.</span></span>
    
6. <span data-ttu-id="c177f-187">Щелкните правой кнопкой имя служб, а затем выберите команду **Остановить**, чтобы остановить службу.</span><span class="sxs-lookup"><span data-stu-id="c177f-187">Right-click the services name, and then select **Stop** to stop the service.</span></span> 
    
7. <span data-ttu-id="c177f-188">Выберите тип запуска **Отключено**.</span><span class="sxs-lookup"><span data-stu-id="c177f-188">Set the Startup type to **Disabled**.</span></span> 
    
8. <span data-ttu-id="c177f-189">Нажмите кнопку **ОК**, чтобы закрыть окно **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="c177f-189">Click **OK** to close the **Properties** window.</span></span> 
    

