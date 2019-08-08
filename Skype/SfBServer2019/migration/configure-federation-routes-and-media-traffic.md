---
title: Настройка маршрутов федерации и трафика мультимедиа
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Федерация — это отношение доверия между двумя или более доменами SIP, позволяющее пользователям в разных организациях взаимодействовать через границы сети. После того как вы перейдете на пилотный проект, вам нужно будет перейти с маршрута Федерации предыдущих версий пограничного сервера на маршрут Федерации сервера пограничных серверов в Skype для бизнеса Server 2019.
ms.openlocfilehash: 50c10a4dced237e59c8dad12b5bdee1ef7d970fe
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/07/2019
ms.locfileid: "36239364"
---
# <a name="configure-federation-routes-and-media-traffic"></a><span data-ttu-id="a49b1-104">Настройка маршрутов федерации и трафика мультимедиа</span><span class="sxs-lookup"><span data-stu-id="a49b1-104">Configure federation routes and media traffic</span></span>

<span data-ttu-id="a49b1-105">Федерация — это отношение доверия между двумя или более доменами SIP, позволяющее пользователям в разных организациях взаимодействовать через границы сети.</span><span class="sxs-lookup"><span data-stu-id="a49b1-105">Federation is a trust relationship between two or more SIP domains that permits users in separate organizations to communicate across network boundaries.</span></span> <span data-ttu-id="a49b1-106">После того как вы перейдете на пилотный проект, вам нужно будет перейти с маршрута Федерации на пограничных серверах предыдущей версии на маршрут Федерации на сервере пограничного сервера Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="a49b1-106">After you migrate to your pilot pool, you need to transition from the federation route of your previous version's Edge Servers to the federation route of your Skype for Business Server 2019 Edge Servers.</span></span>
  
<span data-ttu-id="a49b1-107">Выполните указанные ниже действия, чтобы перенести маршрут Федерации и трафик мультимедиа с пограничного сервера и режиссера на сервер в Skype для бизнеса Server 2019 для развертывания с одним сайтом.</span><span class="sxs-lookup"><span data-stu-id="a49b1-107">Use the following procedures to transition the federation route and the media traffic route from your previous version's Edge Server and Director to your Skype for Business Server 2019 Edge Server, for a single-site deployment.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="a49b1-108">Для изменения маршрута Федерации и маршрутизации трафика мультимедиа требуется запланировать время бездействия на обслуживание для серверов Skype для бизнеса Server 2019 и более ранних версий.</span><span class="sxs-lookup"><span data-stu-id="a49b1-108">Changing the federation route and media traffic route requires that you schedule maintenance downtime for the Skype for Business Server 2019 and previous version Edge Servers.</span></span> <span data-ttu-id="a49b1-109">Весь процесс перехода также означает, что федеративное Access будет недоступен в течение сбоя.</span><span class="sxs-lookup"><span data-stu-id="a49b1-109">This entire transition process also means that federated access will be unavailable for the duration of the outage.</span></span> <span data-ttu-id="a49b1-110">Вы должны планировать время простоя, когда ожидается минимальная активность пользователей.</span><span class="sxs-lookup"><span data-stu-id="a49b1-110">You should schedule the downtime for a time when you expect minimal user activity.</span></span> <span data-ttu-id="a49b1-111">Кроме того, вы должны предоставить вам достаточное уведомление для конечных пользователей.</span><span class="sxs-lookup"><span data-stu-id="a49b1-111">You should also provide sufficient notification to your end users.</span></span> <span data-ttu-id="a49b1-112">Спланируйте этот сбой и настройте соответствующие ожидания в Организации.</span><span class="sxs-lookup"><span data-stu-id="a49b1-112">Plan accordingly for this outage and set appropriate expectations within your organization.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="a49b1-113">Если сервер старой версии пограничного сервера настроен на использование того же полного доменного имени для службы пограничного доступа, службы Edge для веб-конференций и службы EDGE, то процедуры, описанные в этом разделе, не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="a49b1-113">If your legacy Edge Server is configured to use the same FQDN for the Access Edge service, Web Conferencing Edge service, and the A/V Edge service, the procedures in this section are not supported.</span></span> <span data-ttu-id="a49b1-114">Если для устаревших служб пограничного приложения задано то же полное доменное имя, необходимо сначала перенести всех пользователей, а затем списать более ранние версии пограничного сервера, прежде чем включить федерацию на пограничный сервер Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="a49b1-114">If the legacy Edge services are configured to use the same FQDN, you must first migrate all your users, then decommission the previous versions Edge Server before enabling federation on the Skype for Business Server 2019 Edge Server.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="a49b1-115">Если КСМПП Федерация передается через пограничный сервер Skype для бизнеса Server 2019, пользователи из предыдущей версии не смогут общаться с федеративными партнерами КСМПП, пока все пользователи не будут перемещены в Skype для бизнеса Server 2019, КСМПП политики и сертификаты настроены: КСМПП федеративный партнер настроен на странице Skype для бизнеса Server 2019, а наконец, записи DNS были обновлены.</span><span class="sxs-lookup"><span data-stu-id="a49b1-115">If your XMPP federation is routed through a Skype for Business Server 2019 Edge Server, users on the previous version will not be able to communicate with the XMPP federated partner until all users have been moved to Skype for Business Server 2019, XMPP policies and certificates have been configured, the XMPP federated partner has been configured on Skype for Business Server 2019, and, lastly, the DNS entries have been updated.</span></span> 
  
## <a name="to-remove-the-legacy-federation-association-from-skype-for-business-server-2019-sites"></a><span data-ttu-id="a49b1-116">Удаление устаревшего сопоставления Федерации из сайта Skype для бизнеса Server 2019</span><span class="sxs-lookup"><span data-stu-id="a49b1-116">To remove the legacy federation association from Skype for Business Server 2019 sites</span></span>

1. <span data-ttu-id="a49b1-117">На сервере переднего плана Skype для бизнеса Server 2019 откройте существующую топологию в построителе топологии.</span><span class="sxs-lookup"><span data-stu-id="a49b1-117">On the Skype for Business Server 2019 Front End server, open the existing topology in Topology Builder.</span></span> 
    
2. <span data-ttu-id="a49b1-118">На левой панели перейдите к узлу сайта, расположенному непосредственно под **Skype для Business Server**.</span><span class="sxs-lookup"><span data-stu-id="a49b1-118">In the left pane, navigate to the site node, which is located directly below **Skype for Business Server**.</span></span>
    
3. <span data-ttu-id="a49b1-119">Щелкните сайт правой кнопкой мыши и выберите команду **изменить свойства**.</span><span class="sxs-lookup"><span data-stu-id="a49b1-119">Right-click the site, and then click **Edit Properties**.</span></span>
    
4. <span data-ttu-id="a49b1-120">На левой панели выберите **маршрут Федерации**.</span><span class="sxs-lookup"><span data-stu-id="a49b1-120">In the left pane, select **Federation route**.</span></span> 
    
5. <span data-ttu-id="a49b1-121">В разделе **назначение маршрута Федерации сайтов**снимите флажок **включить федерацию SIP** , чтобы отключить маршрут Федерации в устаревшей среде.</span><span class="sxs-lookup"><span data-stu-id="a49b1-121">Under **Site federation route assignment**, clear the **Enable SIP federation** check box to disable the federation route through the legacy environment.</span></span> 
  
6. <span data-ttu-id="a49b1-122">Нажмите кнопку **ОК** , чтобы закрыть страницу Изменение свойств.</span><span class="sxs-lookup"><span data-stu-id="a49b1-122">Click **OK** to close the Edit Properties page.</span></span> 
    
7. <span data-ttu-id="a49b1-123">В **построителе топологии**выберите верхний узел в **Skype для бизнеса Server**.</span><span class="sxs-lookup"><span data-stu-id="a49b1-123">From **Topology Builder**, select the top node **Skype for Business Server**.</span></span>
    
8. <span data-ttu-id="a49b1-124">В меню **действия** выберите пункт **топология публикации**.</span><span class="sxs-lookup"><span data-stu-id="a49b1-124">From the **Action** menu, click **Publish Topology**.</span></span>
    
9. <span data-ttu-id="a49b1-125">Нажмите кнопку **Далее** , чтобы завершить процесс публикации, а затем нажмите кнопку **Готово** после завершения процесса публикации.</span><span class="sxs-lookup"><span data-stu-id="a49b1-125">Click **Next** to complete the publishing process, and then click **Finish** when the publishing process has completed.</span></span> 
    
## <a name="to-configure-the-legacy-edge-server-as-a-non-federating-edge-server"></a><span data-ttu-id="a49b1-126">Настройка устаревшего пограничного сервера в качестве пограничного сервера без поддержки Федерации</span><span class="sxs-lookup"><span data-stu-id="a49b1-126">To configure the legacy Edge Server as a non-federating Edge Server</span></span>

1. <span data-ttu-id="a49b1-127">На левой панели перейдите к старому узлу установки, а затем — узлу **группы Edges** .</span><span class="sxs-lookup"><span data-stu-id="a49b1-127">In the left pane, navigate to the legacy install node and then to the **Edge pools** node.</span></span> 
    
2. <span data-ttu-id="a49b1-128">Щелкните правой кнопкой мыши пограничный сервер и выберите команду **изменить свойства**.</span><span class="sxs-lookup"><span data-stu-id="a49b1-128">Right-click the Edge server, and then click **Edit Properties**.</span></span>
    
3. <span data-ttu-id="a49b1-129">На левой панели выберите **Общие** .</span><span class="sxs-lookup"><span data-stu-id="a49b1-129">Select **General** in the left pane.</span></span> 
    
4. <span data-ttu-id="a49b1-130">Снимите флажок **включить федерацию для этого пограничного пула (порт 5061)** и нажмите кнопку **ОК** , чтобы закрыть страницу.</span><span class="sxs-lookup"><span data-stu-id="a49b1-130">Clear the **Enable federation for this Edge pool (port 5061)** check box and select **OK** to close the page.</span></span> 
  
5. <span data-ttu-id="a49b1-131">В меню **действие** выберите пункт **топология публикации**и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="a49b1-131">From the **Action** menu, select **Publish Topology**, and then click **Next**.</span></span>
    
6. <span data-ttu-id="a49b1-132">После завершения работы **мастера публикации** нажмите кнопку **Готово** , чтобы закрыть окно мастера.</span><span class="sxs-lookup"><span data-stu-id="a49b1-132">When the **Publishing wizard** completes, click **Finish** to close the wizard.</span></span> 
    
7. <span data-ttu-id="a49b1-133">Убедитесь в том, что в построителе топологии отключена Федерация для устаревшего пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="a49b1-133">Verify that federation for the legacy Edge server is disabled in Topology Builder.</span></span>
  
## <a name="to-configure-certificates-on-the-legacy-edge-server"></a><span data-ttu-id="a49b1-134">Настройка сертификатов для устаревшего пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="a49b1-134">To configure certificates on the legacy Edge Server</span></span>

1. <span data-ttu-id="a49b1-135">Экспортируйте сертификат прокси внешнего доступа с закрытым ключом с прежнего пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="a49b1-135">Export the external Access Proxy certificate, with the private key, from the legacy Edge Server.</span></span> 
    
2. <span data-ttu-id="a49b1-136">На пограничном сервере Skype для бизнеса Server 2019 и импортируйте внешний сертификат прокси-сервера доступа на предыдущем этапе.</span><span class="sxs-lookup"><span data-stu-id="a49b1-136">On the Skype for Business Server 2019 Edge Server, and import the Access Proxy external certificate from the previous step.</span></span>
    
3. <span data-ttu-id="a49b1-137">Назначьте внешний сертификат прокси-сервера доступа внешнему интерфейсу Skype для бизнеса Server 2019 на пограничном сервере.</span><span class="sxs-lookup"><span data-stu-id="a49b1-137">Assign the Access Proxy external certificate to the Skype for Business Server 2019 external interface of the Edge Server.</span></span>
    
4. <span data-ttu-id="a49b1-138">Сертификат внутренней сети Skype для Business Server 2019, пограничного сервера должен быть указан в центре сертификации и назначен.</span><span class="sxs-lookup"><span data-stu-id="a49b1-138">The internal interface certificate of the Skype for Business Server 2019 Edge Server should be requested from a trusted CA and assigned.</span></span> 
    
## <a name="to-change-the-previous-versions-federation-route-to-use-skype-for-business-server-2019-edge-server"></a><span data-ttu-id="a49b1-139">Изменение маршрута Федерации для предыдущей версии на использование Skype для Business Server 2019 Edge Server</span><span class="sxs-lookup"><span data-stu-id="a49b1-139">To change the previous version's federation route to use Skype for Business Server 2019 Edge Server</span></span>

1. <span data-ttu-id="a49b1-140">Из построителя топологии в левой области перейдите на узел **Skype для бизнеса Server 2019** , а затем в узел **пулов Edge** .</span><span class="sxs-lookup"><span data-stu-id="a49b1-140">From Topology Builder, in the left pane, navigate to the **Skype for Business Server 2019** node and then to the **Edge pools** node.</span></span> 
    
2. <span data-ttu-id="a49b1-141">Щелкните правой кнопкой мыши пограничный сервер и выберите команду **изменить свойства**.</span><span class="sxs-lookup"><span data-stu-id="a49b1-141">Right-click the Edge server, and then click **Edit Properties**.</span></span>
    
3. <span data-ttu-id="a49b1-142">На левой панели выберите **Общие** .</span><span class="sxs-lookup"><span data-stu-id="a49b1-142">Select **General** in the left pane.</span></span> 
    
4. <span data-ttu-id="a49b1-143">Установите флажок **включить федерацию для этого пограничного пула (порт 5061)**, а затем нажмите кнопку **ОК** , чтобы закрыть страницу.</span><span class="sxs-lookup"><span data-stu-id="a49b1-143">Select the check box for **Enable federation for this Edge pool (port 5061)**, and then click **OK** to close the page.</span></span> 
  
5. <span data-ttu-id="a49b1-144">В меню **действие** выберите пункт **топология публикации**и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="a49b1-144">From the **Action** menu, select **Publish Topology**, and then click **Next**.</span></span>
    
6. <span data-ttu-id="a49b1-145">После завершения работы **мастера публикации** нажмите кнопку **Готово** , чтобы закрыть окно мастера.</span><span class="sxs-lookup"><span data-stu-id="a49b1-145">When the **Publishing wizard** completes, click **Finish** to close the wizard.</span></span> 
    
7. <span data-ttu-id="a49b1-146">Убедитесь в том, что для **Федерации (порт 5061)** задано значение **Enabled** в построителе топологии.</span><span class="sxs-lookup"><span data-stu-id="a49b1-146">Verify that **Federation (port 5061)** is set to **Enabled** in Topology Builder.</span></span>
    
  
## <a name="to-update-skype-for-business-server-2019-edge-server-federation-next-hop"></a><span data-ttu-id="a49b1-147">Обновление следующего прыжка для Федерации Skype для бизнеса Server 2019 (пограничного сервера)</span><span class="sxs-lookup"><span data-stu-id="a49b1-147">To update Skype for Business Server 2019 Edge Server federation next hop</span></span>

1. <span data-ttu-id="a49b1-148">Из построителя топологии в левой области перейдите на узел **Skype для бизнеса Server 2019** , а затем в узел **пулов Edge** .</span><span class="sxs-lookup"><span data-stu-id="a49b1-148">From Topology Builder, in the left pane, navigate to the **Skype for Business Server 2019** node and then to the **Edge pools** node.</span></span> 
    
2. <span data-ttu-id="a49b1-149">Разверните узел, щелкните правой кнопкой мыши пограничный сервер в списке и выберите команду **изменить свойства**.</span><span class="sxs-lookup"><span data-stu-id="a49b1-149">Expand the node, right-click the Edge Server listed, and then click **Edit Properties**.</span></span> 
    
3. <span data-ttu-id="a49b1-150">На странице **Общие** в разделе **следующий**Переход выберите пункт из раскрывающегося списка в группе Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="a49b1-150">On the **General** page, under **Next hop selection**, select from the drop-down list the Skype for Business Server 2019 pool.</span></span>
  
4. <span data-ttu-id="a49b1-151">Нажмите кнопку **ОК** , чтобы закрыть страницу Изменение свойств.</span><span class="sxs-lookup"><span data-stu-id="a49b1-151">Click **OK** to close the Edit Properties page.</span></span> 
    
5. <span data-ttu-id="a49b1-152">В **построителе топологии**выберите верхний узел в **Skype для бизнеса Server**.</span><span class="sxs-lookup"><span data-stu-id="a49b1-152">From **Topology Builder**, select the top node **Skype for Business Server**.</span></span> 
    
6. <span data-ttu-id="a49b1-153">В меню **действия** выберите команду **топология публикации** и завершите работу мастера.</span><span class="sxs-lookup"><span data-stu-id="a49b1-153">From the **Action** menu, click **Publish Topology** and complete the wizard.</span></span> 
    
## <a name="to-configure-skype-for-business-server-2019-edge-server-outbound-media-path"></a><span data-ttu-id="a49b1-154">Настройка пути к исходящему носителю в Skype для бизнеса Server 2019 для пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="a49b1-154">To configure Skype for Business Server 2019 Edge Server outbound media path</span></span>

1. <span data-ttu-id="a49b1-155">Из построителя топологии в левой области перейдите на узел **Skype для бизнеса Server 2019** , а затем в пул ниже **стандартных внешних серверов выпуска** и пулов предварительной **версии Enterprise Edition**.</span><span class="sxs-lookup"><span data-stu-id="a49b1-155">From Topology Builder, in the left pane, navigate to the **Skype for Business Server 2019** node and then to the pool below **Standard Edition Front End Servers** or **Enterprise Edition Front End pools**.</span></span>
    
2. <span data-ttu-id="a49b1-156">Щелкните пул правой кнопкой мыши и выберите команду **изменить свойства**.</span><span class="sxs-lookup"><span data-stu-id="a49b1-156">Right-click the pool, and then click **Edit Properties**.</span></span>
    
3. <span data-ttu-id="a49b1-157">В разделе " **связи** " установите флажок " **связать пул EDGE (для компонентов мультимедиа)** ".</span><span class="sxs-lookup"><span data-stu-id="a49b1-157">In the **Associations** section, select the **Associate Edge pool (for media components)** check box.</span></span> 
  
4. <span data-ttu-id="a49b1-158">В раскрывающемся списке выберите пункт Пограничный сервер Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="a49b1-158">From the drop-down box, select the Skype for Business Server 2019 Edge Server.</span></span>
    
5. <span data-ttu-id="a49b1-159">Нажмите кнопку **ОК** , чтобы закрыть страницу **изменение свойств** .</span><span class="sxs-lookup"><span data-stu-id="a49b1-159">Click **OK** to close the **Edit Properties** page.</span></span> 
    
## <a name="to-turn-on-skype-for-business-server-2019-edge-server-federation"></a><span data-ttu-id="a49b1-160">Включение поддержки интеграции Skype для бизнеса Server 2019 Server Edge</span><span class="sxs-lookup"><span data-stu-id="a49b1-160">To turn on Skype for Business Server 2019 Edge Server federation</span></span>

1. <span data-ttu-id="a49b1-161">Из построителя топологии в левой области перейдите на узел **Skype для бизнеса Server 2019** , а затем в узел **пулов Edge** .</span><span class="sxs-lookup"><span data-stu-id="a49b1-161">From Topology Builder, in the left pane, navigate to the **Skype for Business Server 2019** node and then to the **Edge pools** node.</span></span> 
    
2. <span data-ttu-id="a49b1-162">Разверните узел, щелкните правой кнопкой мыши пограничный сервер в списке и выберите команду **изменить свойства**.</span><span class="sxs-lookup"><span data-stu-id="a49b1-162">Expand the node, right-click the Edge Server listed, and then click **Edit Properties**.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="a49b1-163">Интеграция может быть включена только для одного пула пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="a49b1-163">Federation can only be enabled for a single Edge pool.</span></span> <span data-ttu-id="a49b1-164">Если у вас несколько пулов EDGE, выберите один из них, чтобы использовать его в качестве пула пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="a49b1-164">If you have multiple Edge pools, select one to use as the federating Edge pool.</span></span> 
  
3. <span data-ttu-id="a49b1-165">Убедитесь, что на странице " **Общие** " установлен флажок **включить федерацию для этого пула Edge (порт 5061)** .</span><span class="sxs-lookup"><span data-stu-id="a49b1-165">On the **General** page, verify that the **Enable federation for this Edge pool (Port 5061)** check box is selected.</span></span> 
  
4. <span data-ttu-id="a49b1-166">Нажмите кнопку **ОК** , чтобы закрыть страницу Изменение свойств.</span><span class="sxs-lookup"><span data-stu-id="a49b1-166">Click **OK** to close the Edit Properties page.</span></span> 
    
5. <span data-ttu-id="a49b1-167">Перейдите к узлу сайта.</span><span class="sxs-lookup"><span data-stu-id="a49b1-167">Navigate to the site node.</span></span> 
    
6. <span data-ttu-id="a49b1-168">Щелкните сайт правой кнопкой мыши и выберите команду **изменить свойства**.</span><span class="sxs-lookup"><span data-stu-id="a49b1-168">Right-click the site, and then click **Edit Properties**.</span></span>
    
7. <span data-ttu-id="a49b1-169">В левой области выберите пункт **маршрут Федерации**.</span><span class="sxs-lookup"><span data-stu-id="a49b1-169">In the left pane, click **Federation route**.</span></span>
    
8. <span data-ttu-id="a49b1-170">В разделе **назначение маршрута Федерации сайтов**выберите **включить федерацию SIP**, а затем в списке выберите пункт Пограничный сервер Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="a49b1-170">Under **Site federation route assignment**, select **Enable SIP federation**, and then from the list select the Skype for Business Server 2019 Edge Server listed.</span></span> 
  
9. <span data-ttu-id="a49b1-171">Нажмите кнопку **ОК** , чтобы закрыть страницу **изменение свойств** .</span><span class="sxs-lookup"><span data-stu-id="a49b1-171">Click **OK** to close the **Edit Properties** page.</span></span> 
    
     <span data-ttu-id="a49b1-172">Для развертываний с несколькими сайтами выполните эту процедуру на каждом сайте.</span><span class="sxs-lookup"><span data-stu-id="a49b1-172">For multi-site deployments, complete this procedure at each site.</span></span> 
    
## <a name="to-publish-edge-server-configuration-changes"></a><span data-ttu-id="a49b1-173">Публикация изменений в конфигурации пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="a49b1-173">To publish Edge Server configuration changes</span></span>

1. <span data-ttu-id="a49b1-174">В **построителе топологии**выберите верхний узел в **Skype для бизнеса Server**.</span><span class="sxs-lookup"><span data-stu-id="a49b1-174">From **Topology Builder**, select the top node **Skype for Business Server**.</span></span> 
    
2. <span data-ttu-id="a49b1-175">В меню **действия** выберите пункт **топология публикации** и завершите работу мастера.</span><span class="sxs-lookup"><span data-stu-id="a49b1-175">From the **Action** menu, select **Publish Topology** and complete the wizard.</span></span> 
    
3. <span data-ttu-id="a49b1-176">Дождитесь, когда репликация службы каталогов Active Directory будет выполняться для всех пулов в развертывании.</span><span class="sxs-lookup"><span data-stu-id="a49b1-176">Wait for Active Directory replication to occur to all pools in the deployment.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="a49b1-177">Может появиться следующее сообщение: **Предупреждение: топология состоит из нескольких федеративных пограничных серверов. Это может происходить при миграции в более позднюю версию продукта. В этом случае только один сервер пограничного сервера используется только для Федерации. Убедитесь, что внешняя SRV-запись DNS указывает на правильный пограничный сервер. Если вы хотите одновременно развернуть несколько пограничного сервера федерации (то есть не сценарий миграции), убедитесь, что все Федеративные партнеры используют Skype для бизнеса Server. Убедитесь, что внешняя SRV-запись содержит все пограничные серверы, поддерживающие Федерацию.**</span><span class="sxs-lookup"><span data-stu-id="a49b1-177">You may see the following message: **Warning: The topology contains more than one Federated Edge Server. This can occur during migration to a more recent version of the product. In that case, only one Edge Server would be actively used for federation. Verify that the external DNS SRV record points to the correct Edge Server. If you want to deploy multiple federation Edge Server to be active concurrently (that is, not a migration scenario), verify that all federated partners are using Skype for Business Server. Verify that the external DNS SRV record lists all federation enabled Edge Servers.**</span></span> <span data-ttu-id="a49b1-178">Это предупреждение ожидается, и его можно игнорировать.</span><span class="sxs-lookup"><span data-stu-id="a49b1-178">This warning is expected and can be safely ignored.</span></span> 
  
## <a name="to-configure-skype-for-business-server-2019-edge-server"></a><span data-ttu-id="a49b1-179">Настройка пограничного сервера Skype для бизнеса Server 2019</span><span class="sxs-lookup"><span data-stu-id="a49b1-179">To configure Skype for Business Server 2019 Edge Server</span></span>

1. <span data-ttu-id="a49b1-180">Переведите все серверы в Skype для бизнеса Server 2019 в Интернете.</span><span class="sxs-lookup"><span data-stu-id="a49b1-180">Bring all of the Skype for Business Server 2019 Edge Servers online.</span></span> 
    
2. <span data-ttu-id="a49b1-181">Обновите правила маршрутизации внешних брандмауэров или подсистемы балансировки нагрузки оборудования, чтобы отправлять трафик SIP для внешнего доступа (обычно это порт 443) и Федерацию (обычно это порт 5061) на пограничный сервер Skype для бизнеса Server 2019 вместо устаревшего пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="a49b1-181">Update the external firewall routing rules or the hardware load balancer settings to send SIP traffic for external access (usually port 443) and federation (usually port 5061) to the Skype for Business Server 2019 Edge Server, instead of the legacy Edge Server.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="a49b1-182">Если у вас нет аппаратной подсистемы балансировки нагрузки, вам нужно обновить запись DNS A для Федерации, чтобы устранить проблему с новым сервером пограничного доступа к Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="a49b1-182">If you do not have a hardware load balancer, you need to update the DNS A record for federation to resolve to the new Skype for Business Server Access Edge server.</span></span> <span data-ttu-id="a49b1-183">Для выполнения этой задачи с минимальным пределами, уменьшите значение ТЛЛ для внешнего доменного имени для доступа в Skype для бизнеса Server, чтобы при обновлении DNS для указания на новый сервер доступа к Skype для бизнеса Server были быстро обновлены службы федерации и удаленного доступа.</span><span class="sxs-lookup"><span data-stu-id="a49b1-183">To accomplish this with minimal disruption, reduce the TLL value for the external Skype for Business Server Access Edge FQDN so that when DNS is updated to point to the new Skype for Business Server Access Edge, federation and remote access will be updated quickly.</span></span> 
  
3. <span data-ttu-id="a49b1-184">Остановите **доступ к серверу Skype для бизнеса Server** с каждого компьютера пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="a49b1-184">Stop the **Skype for Business Server Access Edge** from each Edge Server computer.</span></span> 
    
4. <span data-ttu-id="a49b1-185">На каждом компьютере пограничного серверного сервера откройте приложение " **службы** " из **меню**"Администрирование".</span><span class="sxs-lookup"><span data-stu-id="a49b1-185">From each legacy Edge Server computer, open the **Services** applet from the **Administrative Tools**.</span></span>
    
5. <span data-ttu-id="a49b1-186">В списке услуги найдите элемент **доступ к серверу Skype для бизнеса Server**.</span><span class="sxs-lookup"><span data-stu-id="a49b1-186">In the services list, find **Skype for Business Server Access Edge**.</span></span>
    
6. <span data-ttu-id="a49b1-187">Щелкните правой кнопкой мыши имя службы, а затем выберите команду **остановить** , чтобы остановить службу.</span><span class="sxs-lookup"><span data-stu-id="a49b1-187">Right-click the services name, and then select **Stop** to stop the service.</span></span> 
    
7. <span data-ttu-id="a49b1-188">Установите для типа запуска значение **отключено**.</span><span class="sxs-lookup"><span data-stu-id="a49b1-188">Set the Startup type to **Disabled**.</span></span> 
    
8. <span data-ttu-id="a49b1-189">Нажмите кнопку **ОК** , чтобы закрыть окно " **свойства** ".</span><span class="sxs-lookup"><span data-stu-id="a49b1-189">Click **OK** to close the **Properties** window.</span></span> 
    

