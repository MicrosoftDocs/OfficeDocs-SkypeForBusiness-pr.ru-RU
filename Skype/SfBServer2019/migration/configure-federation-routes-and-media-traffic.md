---
title: Настройка маршрутов федерации и трафика мультимедиа
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Федерация — это отношение доверия между двумя или более доменами SIP, которое разрешает пользователям в разных организациях поддерживать связь по границам сети. После миграции в пилотном пуле вам нужно перехода от федеративного маршрута к предыдущих версий пограничных серверов для федеративного маршрута к Скайп для Business Server 2019 пограничных серверов.
ms.openlocfilehash: 607d98c3c831ae9fd911b9fd2782490dcfb0e4f4
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "32238746"
---
# <a name="configure-federation-routes-and-media-traffic"></a><span data-ttu-id="5a722-104">Настройка маршрутов федерации и трафика мультимедиа</span><span class="sxs-lookup"><span data-stu-id="5a722-104">Configure federation routes and media traffic</span></span>

<span data-ttu-id="5a722-105">Федерация — это отношение доверия между двумя или более доменами SIP, которое разрешает пользователям в разных организациях поддерживать связь по границам сети.</span><span class="sxs-lookup"><span data-stu-id="5a722-105">Federation is a trust relationship between two or more SIP domains that permits users in separate organizations to communicate across network boundaries.</span></span> <span data-ttu-id="5a722-106">После миграции в пилотном пуле необходимо перехода от федеративный маршрут с предыдущей версии пограничных серверов для федеративного маршрута к Скайп для Business Server 2019 пограничных серверов.</span><span class="sxs-lookup"><span data-stu-id="5a722-106">After you migrate to your pilot pool, you need to transition from the federation route of your previous version's Edge Servers to the federation route of your Skype for Business Server 2019 Edge Servers.</span></span>
  
<span data-ttu-id="5a722-107">Используйте следующие процедуры для переноса федеративного маршрута и маршрута мультимедиа-трафика с пограничного сервера и директора предыдущей версии для вашей Скайп Business Server 2019 пограничного сервера для развертывания одним сайтом.</span><span class="sxs-lookup"><span data-stu-id="5a722-107">Use the following procedures to transition the federation route and the media traffic route from your previous version's Edge Server and Director to your Skype for Business Server 2019 Edge Server, for a single-site deployment.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="5a722-108">Изменение федеративного маршрута и маршрута мультимедиа-трафика необходимо запланировать время простоя обслуживания Скайп Business Server 2019 и предыдущей версии пограничных серверов.</span><span class="sxs-lookup"><span data-stu-id="5a722-108">Changing the federation route and media traffic route requires that you schedule maintenance downtime for the Skype for Business Server 2019 and previous version Edge Servers.</span></span> <span data-ttu-id="5a722-109">Этот процесс перехода всей также означает, что федеративного доступа будут недоступны во время выполнения во время отказа.</span><span class="sxs-lookup"><span data-stu-id="5a722-109">This entire transition process also means that federated access will be unavailable for the duration of the outage.</span></span> <span data-ttu-id="5a722-110">Следует планировать время простоя в течение времени, когда ожидать действие минимальной пользователя.</span><span class="sxs-lookup"><span data-stu-id="5a722-110">You should schedule the downtime for a time when you expect minimal user activity.</span></span> <span data-ttu-id="5a722-111">Необходимо также предоставить достаточно уведомления конечных пользователей.</span><span class="sxs-lookup"><span data-stu-id="5a722-111">You should also provide sufficient notification to your end users.</span></span> <span data-ttu-id="5a722-112">Составьте соответствующий план для этого сбоя и набор подходят ожиданиям вашей организации.</span><span class="sxs-lookup"><span data-stu-id="5a722-112">Plan accordingly for this outage and set appropriate expectations within your organization.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="5a722-113">Если устаревшего пограничного сервера настроены на использование того же полное доменное имя для пограничной службы доступа, служба пограничного сервера конференц-связи Web и A аудио- и видеоконференций, процедур, описанных в этом разделе, не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="5a722-113">If your legacy Edge Server is configured to use the same FQDN for the Access Edge service, Web Conferencing Edge service, and the A/V Edge service, the procedures in this section are not supported.</span></span> <span data-ttu-id="5a722-114">Если устаревших служб пограничного сервера настроены на использование того же полное доменное имя, необходимо сначала перенос всех пользователей, а затем ликвидация предыдущих версий пограничного сервера перед включением федерации на Скайп Business Server 2019 пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="5a722-114">If the legacy Edge services are configured to use the same FQDN, you must first migrate all your users, then decommission the previous versions Edge Server before enabling federation on the Skype for Business Server 2019 Edge Server.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="5a722-115">Если ваше федерации XMPP маршрутизированы через Скайп Business Server 2019 пограничного сервера, пользователи из предыдущей версии не смогут для взаимодействия с федеративного партнера XMPP, пока все пользователи были перемещены в Скайп для 2019 Business Server, политики XMPP и сертификаты были настроены, федеративного партнера XMPP настроен на Скайп для Business Server 2019 и, наконец, были обновлены DNS-записи.</span><span class="sxs-lookup"><span data-stu-id="5a722-115">If your XMPP federation is routed through a Skype for Business Server 2019 Edge Server, users on the previous version will not be able to communicate with the XMPP federated partner until all users have been moved to Skype for Business Server 2019, XMPP policies and certificates have been configured, the XMPP federated partner has been configured on Skype for Business Server 2019, and, lastly, the DNS entries have been updated.</span></span> 
  
## <a name="to-remove-the-legacy-federation-association-from-skype-for-business-server-2019-sites"></a><span data-ttu-id="5a722-116">Удаление устаревшей связи федерации из Скайп для сайтов Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="5a722-116">To remove the legacy federation association from Skype for Business Server 2019 sites</span></span>

1. <span data-ttu-id="5a722-117">На Скайп для сервера переднего плана Business Server 2019 откройте существующую топологию в построителе топологий.</span><span class="sxs-lookup"><span data-stu-id="5a722-117">On the Skype for Business Server 2019 Front End server, open the existing topology in Topology Builder.</span></span> 
    
2. <span data-ttu-id="5a722-118">В левой области перейдите к узлу сайта, расположенному непосредственно под **Скайп для Business Server**.</span><span class="sxs-lookup"><span data-stu-id="5a722-118">In the left pane, navigate to the site node, which is located directly below **Skype for Business Server**.</span></span>
    
3. <span data-ttu-id="5a722-119">Щелкните сайт правой кнопкой мыши и выберите команду **Изменить свойства**.</span><span class="sxs-lookup"><span data-stu-id="5a722-119">Right-click the site, and then click **Edit Properties**.</span></span>
    
4. <span data-ttu-id="5a722-120">В левой области выберите **Федеративный маршрут**.</span><span class="sxs-lookup"><span data-stu-id="5a722-120">In the left pane, select **Federation route**.</span></span> 
    
5. <span data-ttu-id="5a722-121">В разделе **Назначение федеративного маршрута сайта**снимите флажок **Включить SIP-федерацию** , чтобы отключить федеративный маршрут с помощью старой среды.</span><span class="sxs-lookup"><span data-stu-id="5a722-121">Under **Site federation route assignment**, clear the **Enable SIP federation** check box to disable the federation route through the legacy environment.</span></span> 
  
6. <span data-ttu-id="5a722-122">Нажмите **кнопку ОК** , чтобы закрыть страницу изменения свойств.</span><span class="sxs-lookup"><span data-stu-id="5a722-122">Click **OK** to close the Edit Properties page.</span></span> 
    
7. <span data-ttu-id="5a722-123">В **Построителе топологии**выберите верхний узел **Скайп для Business Server**.</span><span class="sxs-lookup"><span data-stu-id="5a722-123">From **Topology Builder**, select the top node **Skype for Business Server**.</span></span>
    
8. <span data-ttu-id="5a722-124">В меню **Действие** выберите пункт **Опубликовать топологию**.</span><span class="sxs-lookup"><span data-stu-id="5a722-124">From the **Action** menu, click **Publish Topology**.</span></span>
    
9. <span data-ttu-id="5a722-125">Нажмите кнопку **Далее** для завершения процесса публикации и нажмите кнопку **Готово** после завершения процесса публикации.</span><span class="sxs-lookup"><span data-stu-id="5a722-125">Click **Next** to complete the publishing process, and then click **Finish** when the publishing process has completed.</span></span> 
    
## <a name="to-configure-the-legacy-edge-server-as-a-non-federating-edge-server"></a><span data-ttu-id="5a722-126">Настройка устаревшего пограничного сервера без федерации пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="5a722-126">To configure the legacy Edge Server as a non-federating Edge Server</span></span>

1. <span data-ttu-id="5a722-127">В левой области перейдите к узлу установки прежних версий, а затем к узлу **пограничные пулы** .</span><span class="sxs-lookup"><span data-stu-id="5a722-127">In the left pane, navigate to the legacy install node and then to the **Edge pools** node.</span></span> 
    
2. <span data-ttu-id="5a722-128">Щелкните правой кнопкой мыши пограничный сервер и выберите команду **Изменить свойства**.</span><span class="sxs-lookup"><span data-stu-id="5a722-128">Right-click the Edge server, and then click **Edit Properties**.</span></span>
    
3. <span data-ttu-id="5a722-129">В левой области выберите пункт **Общие** .</span><span class="sxs-lookup"><span data-stu-id="5a722-129">Select **General** in the left pane.</span></span> 
    
4. <span data-ttu-id="5a722-130">Снимите флажок **Включение федерации для этого пограничного пула (порт 5061)** и выберите **кнопку ОК** , чтобы закрыть диалоговое окно.</span><span class="sxs-lookup"><span data-stu-id="5a722-130">Clear the **Enable federation for this Edge pool (port 5061)** check box and select **OK** to close the page.</span></span> 
  
5. <span data-ttu-id="5a722-131">В меню **Действие** выберите команду **Опубликовать топологию**и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="5a722-131">From the **Action** menu, select **Publish Topology**, and then click **Next**.</span></span>
    
6. <span data-ttu-id="5a722-132">После завершения работы **мастера публикации** , нажмите кнопку **Готово** , чтобы закрыть мастер.</span><span class="sxs-lookup"><span data-stu-id="5a722-132">When the **Publishing wizard** completes, click **Finish** to close the wizard.</span></span> 
    
7. <span data-ttu-id="5a722-133">Убедитесь в том, что федерация для устаревшего пограничного сервера отключена в построителе топологий.</span><span class="sxs-lookup"><span data-stu-id="5a722-133">Verify that federation for the legacy Edge server is disabled in Topology Builder.</span></span>
  
## <a name="to-configure-certificates-on-the-legacy-edge-server"></a><span data-ttu-id="5a722-134">Настройка сертификатов на устаревшего пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="5a722-134">To configure certificates on the legacy Edge Server</span></span>

1. <span data-ttu-id="5a722-135">Экспортируйте внешний сертификат прокси-сервера доступа с закрытым ключом из устаревшего пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="5a722-135">Export the external Access Proxy certificate, with the private key, from the legacy Edge Server.</span></span> 
    
2. <span data-ttu-id="5a722-136">На Скайп для пограничного сервера Business Server 2019 и Импорт внешних прокси-сервера доступа сертификата из предыдущего шага.</span><span class="sxs-lookup"><span data-stu-id="5a722-136">On the Skype for Business Server 2019 Edge Server, and import the Access Proxy external certificate from the previous step.</span></span>
    
3. <span data-ttu-id="5a722-137">Назначьте внешний сертификат прокси-сервера доступа Скайп для Business Server 2019 внешний интерфейс пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="5a722-137">Assign the Access Proxy external certificate to the Skype for Business Server 2019 external interface of the Edge Server.</span></span>
    
4. <span data-ttu-id="5a722-138">Сертификат внутреннего интерфейса Скайп для пограничного сервера Business Server 2019 следует запросить у доверенного центра сертификации и назначен.</span><span class="sxs-lookup"><span data-stu-id="5a722-138">The internal interface certificate of the Skype for Business Server 2019 Edge Server should be requested from a trusted CA and assigned.</span></span> 
    
## <a name="to-change-the-previous-versions-federation-route-to-use-skype-for-business-server-2019-edge-server"></a><span data-ttu-id="5a722-139">Изменение федеративного маршрута предыдущей версии в целях Скайп Business Server 2019 пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="5a722-139">To change the previous version's federation route to use Skype for Business Server 2019 Edge Server</span></span>

1. <span data-ttu-id="5a722-140">В построителе топологий в левой области перейдите к узлу **Скайп для Business Server 2019** , а затем к узлу **пограничные пулы** .</span><span class="sxs-lookup"><span data-stu-id="5a722-140">From Topology Builder, in the left pane, navigate to the **Skype for Business Server 2019** node and then to the **Edge pools** node.</span></span> 
    
2. <span data-ttu-id="5a722-141">Щелкните правой кнопкой мыши пограничный сервер и выберите команду **Изменить свойства**.</span><span class="sxs-lookup"><span data-stu-id="5a722-141">Right-click the Edge server, and then click **Edit Properties**.</span></span>
    
3. <span data-ttu-id="5a722-142">В левой области выберите пункт **Общие** .</span><span class="sxs-lookup"><span data-stu-id="5a722-142">Select **General** in the left pane.</span></span> 
    
4. <span data-ttu-id="5a722-143">Установите флажок для **включения федерации для этого пограничного пула (порт 5061)** и нажмите кнопку **ОК** , чтобы закрыть диалоговое окно.</span><span class="sxs-lookup"><span data-stu-id="5a722-143">Select the check box for **Enable federation for this Edge pool (port 5061)**, and then click **OK** to close the page.</span></span> 
  
5. <span data-ttu-id="5a722-144">В меню **Действие** выберите команду **Опубликовать топологию**и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="5a722-144">From the **Action** menu, select **Publish Topology**, and then click **Next**.</span></span>
    
6. <span data-ttu-id="5a722-145">После завершения работы **мастера публикации** , нажмите кнопку **Готово** , чтобы закрыть мастер.</span><span class="sxs-lookup"><span data-stu-id="5a722-145">When the **Publishing wizard** completes, click **Finish** to close the wizard.</span></span> 
    
7. <span data-ttu-id="5a722-146">Убедитесь, что **Федерация (порт 5061)** задано значение **включено** в построителе топологий.</span><span class="sxs-lookup"><span data-stu-id="5a722-146">Verify that **Federation (port 5061)** is set to **Enabled** in Topology Builder.</span></span>
    
  
## <a name="to-update-skype-for-business-server-2019-edge-server-federation-next-hop"></a><span data-ttu-id="5a722-147">Для обновления Скайп для следующего перехода федерации пограничного сервера Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="5a722-147">To update Skype for Business Server 2019 Edge Server federation next hop</span></span>

1. <span data-ttu-id="5a722-148">В построителе топологий в левой области перейдите к узлу **Скайп для Business Server 2019** , а затем к узлу **пограничные пулы** .</span><span class="sxs-lookup"><span data-stu-id="5a722-148">From Topology Builder, in the left pane, navigate to the **Skype for Business Server 2019** node and then to the **Edge pools** node.</span></span> 
    
2. <span data-ttu-id="5a722-149">Разверните узел, щелкните правой кнопкой указанный пограничный сервер и выберите команду **Изменить свойства**.</span><span class="sxs-lookup"><span data-stu-id="5a722-149">Expand the node, right-click the Edge Server listed, and then click **Edit Properties**.</span></span> 
    
3. <span data-ttu-id="5a722-150">На странице " **Общие** " в разделе **Выбор узла следующего перехода**выберите в раскрывающемся списке Скайп для пула Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="5a722-150">On the **General** page, under **Next hop selection**, select from the drop-down list the Skype for Business Server 2019 pool.</span></span>
  
4. <span data-ttu-id="5a722-151">Нажмите **кнопку ОК** , чтобы закрыть страницу изменения свойств.</span><span class="sxs-lookup"><span data-stu-id="5a722-151">Click **OK** to close the Edit Properties page.</span></span> 
    
5. <span data-ttu-id="5a722-152">В **Построителе топологии**выберите верхний узел **Скайп для Business Server**.</span><span class="sxs-lookup"><span data-stu-id="5a722-152">From **Topology Builder**, select the top node **Skype for Business Server**.</span></span> 
    
6. <span data-ttu-id="5a722-153">В меню **Действие** щелкните **Опубликовать топологию** и завершите работу мастера.</span><span class="sxs-lookup"><span data-stu-id="5a722-153">From the **Action** menu, click **Publish Topology** and complete the wizard.</span></span> 
    
## <a name="to-configure-skype-for-business-server-2019-edge-server-outbound-media-path"></a><span data-ttu-id="5a722-154">Настройка Скайп для пограничного сервера Business Server 2019 исходящего пути к мультимедиа</span><span class="sxs-lookup"><span data-stu-id="5a722-154">To configure Skype for Business Server 2019 Edge Server outbound media path</span></span>

1. <span data-ttu-id="5a722-155">В построителе топологий в левой области перейдите к узлу **Скайп для Business Server 2019** , а затем к пулу под **Standard Edition серверы переднего плана** или **Пулы переднего плана Enterprise Edition**.</span><span class="sxs-lookup"><span data-stu-id="5a722-155">From Topology Builder, in the left pane, navigate to the **Skype for Business Server 2019** node and then to the pool below **Standard Edition Front End Servers** or **Enterprise Edition Front End pools**.</span></span>
    
2. <span data-ttu-id="5a722-156">Щелкните пул правой кнопкой мыши и выберите команду **Изменить свойства**.</span><span class="sxs-lookup"><span data-stu-id="5a722-156">Right-click the pool, and then click **Edit Properties**.</span></span>
    
3. <span data-ttu-id="5a722-157">В разделе **связи** установите флажок **сопоставить пограничный пул (для компонентов мультимедиа)** .</span><span class="sxs-lookup"><span data-stu-id="5a722-157">In the **Associations** section, select the **Associate Edge pool (for media components)** check box.</span></span> 
  
4. <span data-ttu-id="5a722-158">Из раскрывающегося списка выберите Скайп Business Server 2019 пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="5a722-158">From the drop-down box, select the Skype for Business Server 2019 Edge Server.</span></span>
    
5. <span data-ttu-id="5a722-159">Нажмите **кнопку ОК** , чтобы закрыть страницу **Изменения свойств** .</span><span class="sxs-lookup"><span data-stu-id="5a722-159">Click **OK** to close the **Edit Properties** page.</span></span> 
    
## <a name="to-turn-on-skype-for-business-server-2019-edge-server-federation"></a><span data-ttu-id="5a722-160">Чтобы включить Скайп Business Server 2019 пограничного сервера федерации</span><span class="sxs-lookup"><span data-stu-id="5a722-160">To turn on Skype for Business Server 2019 Edge Server federation</span></span>

1. <span data-ttu-id="5a722-161">В построителе топологий в левой области перейдите к узлу **Скайп для Business Server 2019** , а затем к узлу **пограничные пулы** .</span><span class="sxs-lookup"><span data-stu-id="5a722-161">From Topology Builder, in the left pane, navigate to the **Skype for Business Server 2019** node and then to the **Edge pools** node.</span></span> 
    
2. <span data-ttu-id="5a722-162">Разверните узел, щелкните правой кнопкой указанный пограничный сервер и выберите команду **Изменить свойства**.</span><span class="sxs-lookup"><span data-stu-id="5a722-162">Expand the node, right-click the Edge Server listed, and then click **Edit Properties**.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="5a722-163">Федерации можно включить только для одного пограничного пула.</span><span class="sxs-lookup"><span data-stu-id="5a722-163">Federation can only be enabled for a single Edge pool.</span></span> <span data-ttu-id="5a722-164">Если у вас есть несколько пулов пограничного сервера, выберите один для использования в качестве federating пограничного пула.</span><span class="sxs-lookup"><span data-stu-id="5a722-164">If you have multiple Edge pools, select one to use as the federating Edge pool.</span></span> 
  
3. <span data-ttu-id="5a722-165">На странице " **Общие** " Убедитесь, что установлен флажок **Включение федерации для этого пограничного пула (порт 5061)** .</span><span class="sxs-lookup"><span data-stu-id="5a722-165">On the **General** page, verify that the **Enable federation for this Edge pool (Port 5061)** check box is selected.</span></span> 
  
4. <span data-ttu-id="5a722-166">Нажмите **кнопку ОК** , чтобы закрыть страницу изменения свойств.</span><span class="sxs-lookup"><span data-stu-id="5a722-166">Click **OK** to close the Edit Properties page.</span></span> 
    
5. <span data-ttu-id="5a722-167">Перейдите к узлу сайта.</span><span class="sxs-lookup"><span data-stu-id="5a722-167">Navigate to the site node.</span></span> 
    
6. <span data-ttu-id="5a722-168">Щелкните сайт правой кнопкой мыши и выберите команду **Изменить свойства**.</span><span class="sxs-lookup"><span data-stu-id="5a722-168">Right-click the site, and then click **Edit Properties**.</span></span>
    
7. <span data-ttu-id="5a722-169">В левой области выберите **Федеративный маршрут**.</span><span class="sxs-lookup"><span data-stu-id="5a722-169">In the left pane, click **Federation route**.</span></span>
    
8. <span data-ttu-id="5a722-170">В разделе **Назначение федеративного маршрута сайта**выберите **Включить федерацию SIP**и выберите в списке Скайп Business Server 2019 пограничного сервера из списка.</span><span class="sxs-lookup"><span data-stu-id="5a722-170">Under **Site federation route assignment**, select **Enable SIP federation**, and then from the list select the Skype for Business Server 2019 Edge Server listed.</span></span> 
  
9. <span data-ttu-id="5a722-171">Нажмите **кнопку ОК** , чтобы закрыть страницу **Изменения свойств** .</span><span class="sxs-lookup"><span data-stu-id="5a722-171">Click **OK** to close the **Edit Properties** page.</span></span> 
    
     <span data-ttu-id="5a722-172">Для развертывания нескольких сайтах выполните эту процедуру на каждом сайте.</span><span class="sxs-lookup"><span data-stu-id="5a722-172">For multi-site deployments, complete this procedure at each site.</span></span> 
    
## <a name="to-publish-edge-server-configuration-changes"></a><span data-ttu-id="5a722-173">Публикация изменений конфигурации пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="5a722-173">To publish Edge Server configuration changes</span></span>

1. <span data-ttu-id="5a722-174">В **Построителе топологии**выберите верхний узел **Скайп для Business Server**.</span><span class="sxs-lookup"><span data-stu-id="5a722-174">From **Topology Builder**, select the top node **Skype for Business Server**.</span></span> 
    
2. <span data-ttu-id="5a722-175">В меню **Действие** выберите команду **Опубликовать топологию** и завершите работу мастера.</span><span class="sxs-lookup"><span data-stu-id="5a722-175">From the **Action** menu, select **Publish Topology** and complete the wizard.</span></span> 
    
3. <span data-ttu-id="5a722-176">Дождитесь репликации Active Directory во всех пулах в развертывании.</span><span class="sxs-lookup"><span data-stu-id="5a722-176">Wait for Active Directory replication to occur to all pools in the deployment.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="5a722-177">Может появиться следующее сообщение: **Предупреждение: топология содержит более одного федеративного пограничного сервера. Это может произойти при переходе к более поздней версии продукта. В этом случае только один пограничного сервера активно используется для федерации. Убедитесь, что внешние DNS-запись SRV указывает на правильные пограничный сервер. Если вы хотите развернуть несколько федерации пограничного сервера, чтобы быть одновременно активный (то есть не сценарий миграции), убедитесь, что все федеративных партнеров Скайп для используются Business Server. Убедитесь, что внешние DNS-запись SRV перечислены все пограничные серверы включена функция федерации.**</span><span class="sxs-lookup"><span data-stu-id="5a722-177">You may see the following message: **Warning: The topology contains more than one Federated Edge Server. This can occur during migration to a more recent version of the product. In that case, only one Edge Server would be actively used for federation. Verify that the external DNS SRV record points to the correct Edge Server. If you want to deploy multiple federation Edge Server to be active concurrently (that is, not a migration scenario), verify that all federated partners are using Skype for Business Server. Verify that the external DNS SRV record lists all federation enabled Edge Servers.**</span></span> <span data-ttu-id="5a722-178">Появление этого предупреждения ожидаемое и его можно спокойно проигнорировать.</span><span class="sxs-lookup"><span data-stu-id="5a722-178">This warning is expected and can be safely ignored.</span></span> 
  
## <a name="to-configure-skype-for-business-server-2019-edge-server"></a><span data-ttu-id="5a722-179">Чтобы настроить Скайп Business Server 2019 пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="5a722-179">To configure Skype for Business Server 2019 Edge Server</span></span>

1. <span data-ttu-id="5a722-180">Переведите все Скайп Интернет-версия для Business Server 2019 пограничных серверов.</span><span class="sxs-lookup"><span data-stu-id="5a722-180">Bring all of the Skype for Business Server 2019 Edge Servers online.</span></span> 
    
2. <span data-ttu-id="5a722-181">Обновление правил маршрутизации внешний брандмауэр или параметры балансировки нагрузки оборудования для отправки трафик SIP для внешнего доступа (обычно это порт 443) и федерации (обычно это порт 5061) для Скайп Business Server 2019 пограничного сервера, вместо устаревшего пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="5a722-181">Update the external firewall routing rules or the hardware load balancer settings to send SIP traffic for external access (usually port 443) and federation (usually port 5061) to the Skype for Business Server 2019 Edge Server, instead of the legacy Edge Server.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="5a722-182">Если у вас аппаратный балансировщик нагрузки, вам потребуется обновить запись DNS A для федерации для решения новый Скайп для сервера Business Server Access Edge.</span><span class="sxs-lookup"><span data-stu-id="5a722-182">If you do not have a hardware load balancer, you need to update the DNS A record for federation to resolve to the new Skype for Business Server Access Edge server.</span></span> <span data-ttu-id="5a722-183">Для выполнения этой задачи мешая уменьшите значение TLL для внешних Скайп для полного доменного ИМЕНИ пограничного сервера доступа Business Server, чтобы при обновлении DNS для указания на новый Скайп для пограничного сервера доступа Business сервера федерации и удаленного доступа будут обновлены быстро.</span><span class="sxs-lookup"><span data-stu-id="5a722-183">To accomplish this with minimal disruption, reduce the TLL value for the external Skype for Business Server Access Edge FQDN so that when DNS is updated to point to the new Skype for Business Server Access Edge, federation and remote access will be updated quickly.</span></span> 
  
3. <span data-ttu-id="5a722-184">Остановите **Скайп для Business Server Access Edge** на каждом компьютере пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="5a722-184">Stop the **Skype for Business Server Access Edge** from each Edge Server computer.</span></span> 
    
4. <span data-ttu-id="5a722-185">На каждом компьютере устаревшего пограничного сервера откройте приложение **службы** в меню **Администрирование**.</span><span class="sxs-lookup"><span data-stu-id="5a722-185">From each legacy Edge Server computer, open the **Services** applet from the **Administrative Tools**.</span></span>
    
5. <span data-ttu-id="5a722-186">В списке служб найдите **Скайп для пограничного сервера доступа Business Server**.</span><span class="sxs-lookup"><span data-stu-id="5a722-186">In the services list, find **Skype for Business Server Access Edge**.</span></span>
    
6. <span data-ttu-id="5a722-187">Щелкните правой кнопкой мыши имя службы и выберите пункт **Остановить** , чтобы остановить службу.</span><span class="sxs-lookup"><span data-stu-id="5a722-187">Right-click the services name, and then select **Stop** to stop the service.</span></span> 
    
7. <span data-ttu-id="5a722-188">Задайте тип запуска **отключено**.</span><span class="sxs-lookup"><span data-stu-id="5a722-188">Set the Startup type to **Disabled**.</span></span> 
    
8. <span data-ttu-id="5a722-189">Нажмите **кнопку ОК** , чтобы закрыть окно **свойств** .</span><span class="sxs-lookup"><span data-stu-id="5a722-189">Click **OK** to close the **Properties** window.</span></span> 
    

