---
title: Настройка маршрутов федерации и трафика мультимедиа
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Configure federation routes and media traffic
ms:assetid: ed6cb922-7863-453a-adce-2ce0ba761d74
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721925(v=OCS.15)
ms:contentKeyID: 49733860
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4542ae02cc72dfbac05dfa982e2fbda7f2924919
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34841784"
---
# <a name="configure-federation-routes-and-media-traffic"></a><span data-ttu-id="bbbdd-102">Настройка маршрутов федерации и трафика мультимедиа</span><span class="sxs-lookup"><span data-stu-id="bbbdd-102">Configure federation routes and media traffic</span></span>

 


<span data-ttu-id="bbbdd-103">Федерация — это отношение доверия между двумя или более доменами SIP, позволяющее пользователям в разных организациях взаимодействовать через границы сети.</span><span class="sxs-lookup"><span data-stu-id="bbbdd-103">Federation is a trust relationship between two or more SIP domains that permits users in separate organizations to communicate across network boundaries.</span></span> <span data-ttu-id="bbbdd-104">После перехода на пилотный пул Lync Server 2013 Pilot необходимо перейти с маршрута Федерации сервера Microsoft Office Communications Server 2007 R2 на маршрут Федерации сервера Lync Server 2013 пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="bbbdd-104">After you migrate to your Lync Server 2013 pilot pool, you need to transition from the federation route of your Microsoft Office Communications Server 2007 R2 Edge Servers to the federation route of your Lync Server 2013 Edge Servers.</span></span>

<span data-ttu-id="bbbdd-105">Воспользуйтесь приведенными ниже инструкциями для перехода между маршрутом Федерации и трафиком мультимедиа с сервера Office Communications Server 2007 R2 и режиссера на сервер Lync Server 2013 Edge для развертывания на одном сайте.</span><span class="sxs-lookup"><span data-stu-id="bbbdd-105">Use the procedures that follow to transition the federation route and the media traffic route from your Office Communications Server 2007 R2 Edge Server and Director to your Lync Server 2013 Edge Server, for a single-site deployment.</span></span>


> [!IMPORTANT]  
> <span data-ttu-id="bbbdd-106">Чтобы изменить маршрут Федерации и трафик мультимедиа, необходимо запланировать время бездействия на обслуживание для Lync Server 2013 и Office Communications Server 2007 R2 пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="bbbdd-106">Changing the federation route and media traffic route requires that you schedule maintenance downtime for the Lync Server 2013 and Office Communications Server 2007 R2 Edge Servers.</span></span> <span data-ttu-id="bbbdd-107">Весь процесс перехода также означает, что федеративное Access будет недоступен в течение сбоя.</span><span class="sxs-lookup"><span data-stu-id="bbbdd-107">This entire transition process also means that federated access will be unavailable for the duration of the outage.</span></span> <span data-ttu-id="bbbdd-108">Вы должны планировать время простоя, когда ожидается минимальная активность пользователей.</span><span class="sxs-lookup"><span data-stu-id="bbbdd-108">You should schedule the downtime for a time when you expect minimal user activity.</span></span> <span data-ttu-id="bbbdd-109">Кроме того, вы должны предоставить вам достаточное уведомление для конечных пользователей.</span><span class="sxs-lookup"><span data-stu-id="bbbdd-109">You should also provide sufficient notification to your end users.</span></span> <span data-ttu-id="bbbdd-110">Спланируйте этот сбой и настройте соответствующие ожидания в Организации.</span><span class="sxs-lookup"><span data-stu-id="bbbdd-110">Plan accordingly for this outage and set appropriate expectations within your organization.</span></span>




> [!IMPORTANT]  
> <span data-ttu-id="bbbdd-111">Если старый сервер Office Communications Server 2007 R2 настроен на использование того же полного доменного имени для службы пограничного доступа, службы Edge для веб-конференций и службы EDGE (A/V), процедуры из этого раздела приводят к переходу параметров Федерации на сервер Lync Server. 2013 пограничного сервера не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="bbbdd-111">If your legacy Office Communications Server 2007 R2 Edge Server is configured to use the same FQDN for the Access Edge service, Web Conferencing Edge service, and the A/V Edge service, the procedures in this section to transition the federation setting to a Lync Server 2013 Edge Server are not supported.</span></span> <span data-ttu-id="bbbdd-112">Если стандартные службы Edge настроены на использование одного полного доменного имени, необходимо сначала перенести всех пользователей из Office Communications Server 2007 R2 на Lync Server 2013, а затем списать сервер Office Communications Server 2007 R2 Edge Server до включения Федерации Сервер Lync Server 2013 Edge.</span><span class="sxs-lookup"><span data-stu-id="bbbdd-112">If the legacy Edge services are configured to use the same FQDN, you must first migrate all your users from Office Communications Server 2007 R2 to Lync Server 2013, then decommission the Office Communications Server 2007 R2 Edge Server before enabling federation on the Lync Server 2013 Edge Server.</span></span> <span data-ttu-id="bbbdd-113">For details, see the following topics:</span><span class="sxs-lookup"><span data-stu-id="bbbdd-113">For details, see the following topics:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="bbbdd-114"><A href="move-remaining-users-to-lync-server-2013_1.md">Перемещение оставшихся пользователей на Lync Server 2013</A></span><span class="sxs-lookup"><span data-stu-id="bbbdd-114"><A href="move-remaining-users-to-lync-server-2013_1.md">Move remaining users to Lync Server 2013</A></span></span></P>
> <LI>
> <P><span data-ttu-id="bbbdd-115">"Удаление серверов и ролей сервера" в<A href="http://go.microsoft.com/fwlink/p/?linkid=268790">http://go.microsoft.com/fwlink/p/?LinkId=268790</A></span><span class="sxs-lookup"><span data-stu-id="bbbdd-115">"Remove Servers and Server Roles" at <A href="http://go.microsoft.com/fwlink/p/?linkid=268790">http://go.microsoft.com/fwlink/p/?LinkId=268790</A></span></span></P></LI></UL>




> [!IMPORTANT]  
> <span data-ttu-id="bbbdd-116">Если Федерация КСМППа передается через сервер Lync Server 2013, устаревшие пользователи Office Communications Server 2007 R2 не смогут общаться с федеративным партнером КСМПП, пока все пользователи не будут перенесены на Lync Server 2013, КСМПП политики и на сервере Lync Server 2013 настроена служба федеративного партнера КСМПП и последние записи DNS были обновлены.</span><span class="sxs-lookup"><span data-stu-id="bbbdd-116">If your XMPP federation is routed through a Lync Server 2013 Edge Server, legacy Office Communications Server 2007 R2 users will not be able to communicate with the XMPP federated partner until all users have been moved to Lync Server 2013, XMPP policies and certificates have been configured, the XMPP federated partner has been configured on Lync Server 2013, and lastly the DNS entries have been updated.</span></span>



<span data-ttu-id="bbbdd-117">Чтобы успешно публиковать, включать и отключать топологию при добавлении или удалении роли сервера, вы должны войти в систему как пользователь, который является членом группы администраторов Рткуниверсалсерверадминс и domain.</span><span class="sxs-lookup"><span data-stu-id="bbbdd-117">To successfully publish, enable, or disable a topology when adding or removing a server role, you should be logged in as a user who is a member of the RTCUniversalServerAdmins and Domain Admins groups.</span></span> <span data-ttu-id="bbbdd-118">Кроме того, вы можете делегировать права и разрешения пользователей для добавления ролей сервера.</span><span class="sxs-lookup"><span data-stu-id="bbbdd-118">It is also possible to delegate the proper user rights and permissions for adding server roles.</span></span> <span data-ttu-id="bbbdd-119">Дополнительные сведения можно найти [в разделе Делегирование разрешений на настройку в Lync Server 2013](lync-server-2013-delegate-setup-permissions.md) в документации по развертыванию сервера Standard Edition Server или Enterprise Edition Server.</span><span class="sxs-lookup"><span data-stu-id="bbbdd-119">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md) in the Standard Edition server or Enterprise Edition server Deployment documentation.</span></span> <span data-ttu-id="bbbdd-120">Для других изменений конфигурации требуется только членство в группе Рткуниверсалсерверадминс.</span><span class="sxs-lookup"><span data-stu-id="bbbdd-120">For other configuration changes, only membership in the RTCUniversalServerAdmins group is required.</span></span>

## <a name="to-remove-the-legacy-federation-association-from-lync-server-2013-sites"></a><span data-ttu-id="bbbdd-121">Удаление устаревшей связи Федерации с сайтов Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bbbdd-121">To remove the legacy federation association from Lync Server 2013 sites</span></span>

1.  <span data-ttu-id="bbbdd-122">Откройте топологию пула пилотных проектов с помощью построителя топологии.</span><span class="sxs-lookup"><span data-stu-id="bbbdd-122">Open the pilot pool topology using Topology Builder.</span></span>

2.  <span data-ttu-id="bbbdd-123">На левой панели перейдите к узлу сайта.</span><span class="sxs-lookup"><span data-stu-id="bbbdd-123">In the left pane, navigate to the site node.</span></span>

3.  <span data-ttu-id="bbbdd-124">Щелкните сайт правой кнопкой мыши и выберите команду **изменить свойства**.</span><span class="sxs-lookup"><span data-stu-id="bbbdd-124">Right-click the site, and then click **Edit Properties**.</span></span>

4.  <span data-ttu-id="bbbdd-125">На левой панели выберите **маршрут Федерации** .</span><span class="sxs-lookup"><span data-stu-id="bbbdd-125">Select **Federation route** in the left pane.</span></span>

5.  <span data-ttu-id="bbbdd-126">В разделе Назначение маршрутов Федерации сайтов снимите флажок **включить федерацию SIP** , чтобы отключить маршрут Федерации через **бакккомпатсите**.</span><span class="sxs-lookup"><span data-stu-id="bbbdd-126">Under Site federation route assignment, clear the check box next to **Enable SIP federation** to disable the federation route through the **BackCompatSite**.</span></span>
    
    <span data-ttu-id="bbbdd-127">![Диалоговое окно "изменение свойств", маршрут Федерации] (images/JJ721925.2a80c103-c0cc-43ed-ba00-420f9add006a(OCS.15).jpg "Диалоговое окно \"изменение свойств\", маршрут Федерации")</span><span class="sxs-lookup"><span data-stu-id="bbbdd-127">![Edit Properties dialog, Federation route](images/JJ721925.2a80c103-c0cc-43ed-ba00-420f9add006a(OCS.15).jpg "Edit Properties dialog, Federation route")</span></span>

6.  <span data-ttu-id="bbbdd-128">Нажмите кнопку **ОК** , чтобы закрыть страницу Изменение свойств.</span><span class="sxs-lookup"><span data-stu-id="bbbdd-128">Click **OK** to close the Edit Properties page.</span></span>

7.  <span data-ttu-id="bbbdd-129">В **построителе топологии**выберите верхний узел **Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="bbbdd-129">From **Topology Builder**, select the top node **Lync Server**.</span></span>

8.  <span data-ttu-id="bbbdd-130">В меню **действия** выберите команду **топология публикации** и завершите работу мастера.</span><span class="sxs-lookup"><span data-stu-id="bbbdd-130">From the **Action** menu, click **Publish Topology** and complete the wizard.</span></span>

## <a name="to-configure-the-legacy-edge-server-as-a-non-federating-edge-server"></a><span data-ttu-id="bbbdd-131">Настройка устаревшего пограничного сервера в качестве пограничного сервера без поддержки Федерации</span><span class="sxs-lookup"><span data-stu-id="bbbdd-131">To configure the legacy Edge Server as a non-federating Edge Server</span></span>

1.  <span data-ttu-id="bbbdd-132">В **построителе топологии**в меню " **действия** " выберите команду " **Слияние топологии Office Communications Server 2007 R2**".</span><span class="sxs-lookup"><span data-stu-id="bbbdd-132">From **Topology Builder**, from the **Action** menu click **Merge Office Communications Server 2007 R2 Topology**.</span></span>

2.  <span data-ttu-id="bbbdd-133">Для продолжения нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="bbbdd-133">Click **Next** to continue.</span></span>

3.  <span data-ttu-id="bbbdd-134">На странице **задать настройку Edge**выберите **внутреннее доменное имя пограничного сервера** , которое сейчас настроено для Федерации, и нажмите кнопку **изменить**.</span><span class="sxs-lookup"><span data-stu-id="bbbdd-134">On the **Specify Edge Setup**, select the **Edge Server Internal FQDN** that is currently configured for federation, and then click **Change**.</span></span>
    
    <span data-ttu-id="bbbdd-135">![Топология слиянием для OCS 2007 R2, указание параметров ребра] (images/JJ721925.42c15aaf-c1ac-4fb1-a086-665835c57b23(OCS.15).jpg "Топология слиянием для OCS 2007 R2, указание параметров ребра")</span><span class="sxs-lookup"><span data-stu-id="bbbdd-135">![Merge OCS 2007 R2 Topology, Specify Edge Setup](images/JJ721925.42c15aaf-c1ac-4fb1-a086-665835c57b23(OCS.15).jpg "Merge OCS 2007 R2 Topology, Specify Edge Setup")</span></span>

4.  <span data-ttu-id="bbbdd-136">Нажмите кнопку **Далее** и подтвердите параметры по умолчанию, пока не перейдите на страницу **задать внешний край** .</span><span class="sxs-lookup"><span data-stu-id="bbbdd-136">Click **Next** and accept the default settings until you get to the **Specify External Edge** page:</span></span>
    
    <span data-ttu-id="bbbdd-137">![Построитель топологии. Выбор внешней страницы пограничного сервера] (images/JJ721925.e36f3a1f-3655-456e-9e6d-4814c37da0bf(OCS.15).jpg "Построитель топологии. Выбор внешней страницы пограничного сервера")</span><span class="sxs-lookup"><span data-stu-id="bbbdd-137">![Topology Builder Specify External Edge page](images/JJ721925.e36f3a1f-3655-456e-9e6d-4814c37da0bf(OCS.15).jpg "Topology Builder Specify External Edge page")</span></span>

5.  <span data-ttu-id="bbbdd-138">В поле **задать внешний край**снимите флажок **этот пул Edge используется для подключения к службам федерации и общедоступного обмена мгновенными сообщениями** .</span><span class="sxs-lookup"><span data-stu-id="bbbdd-138">In **Specify External Edge**, clear the **This Edge pool is used for federation and public IM connectivity** check box.</span></span> <span data-ttu-id="bbbdd-139">Связь Федерации с Бакккомпатсите будет удалена.</span><span class="sxs-lookup"><span data-stu-id="bbbdd-139">This will remove the federation association with the BackCompatSite.</span></span>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="bbbdd-140">Этот этап важен.</span><span class="sxs-lookup"><span data-stu-id="bbbdd-140">This step is important.</span></span> <span data-ttu-id="bbbdd-141">Вы должны снять этот флажок, чтобы удалить устаревшее сопоставление Федерации.</span><span class="sxs-lookup"><span data-stu-id="bbbdd-141">You must clear this option to remove the legacy federation association.</span></span>



6.  <span data-ttu-id="bbbdd-142">Нажмите кнопку **Далее** и подтвердите параметры по умолчанию на остальных страницах мастера.</span><span class="sxs-lookup"><span data-stu-id="bbbdd-142">Click **Next** and accept the default settings of the remaining pages of the wizard.</span></span>

7.  <span data-ttu-id="bbbdd-143">В разделе **Сводка**нажмите кнопку **Далее** , чтобы начать объединение топологий.</span><span class="sxs-lookup"><span data-stu-id="bbbdd-143">In **Summary**, click **Next** to begin merging the topologies.</span></span>

8.  <span data-ttu-id="bbbdd-144">В столбце **Status (состояние** ) убедитесь, что значение **успешно**, а затем нажмите кнопку **Готово** , чтобы закрыть окно мастера.</span><span class="sxs-lookup"><span data-stu-id="bbbdd-144">In the **Status** column, verify that the value is **Success**, and then click **Finish** to close the wizard.</span></span>

9.  <span data-ttu-id="bbbdd-145">В меню **действие** выберите пункт **топология публикации**и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="bbbdd-145">From the **Action** menu, select **Publish Topology**, and then click **Next**.</span></span>

10. <span data-ttu-id="bbbdd-146">После завершения работы **мастера публикации** нажмите кнопку **Готово** , чтобы закрыть окно мастера.</span><span class="sxs-lookup"><span data-stu-id="bbbdd-146">When the **Publishing wizard** completes, click **Finish** to close the wizard.</span></span>
    
    <span data-ttu-id="bbbdd-147">![Построитель топологии с отображением сайта после слияния] (images/JJ721925.92b679ad-332f-49aa-b4e2-19f939b711ca(OCS.15).jpg "Построитель топологии с отображением сайта после слияния")</span><span class="sxs-lookup"><span data-stu-id="bbbdd-147">![Topology Builder with site displayed after merge](images/JJ721925.92b679ad-332f-49aa-b4e2-19f939b711ca(OCS.15).jpg "Topology Builder with site displayed after merge")</span></span>
    
    <span data-ttu-id="bbbdd-148">Как показано на предыдущем рисунке, **Федерация SIP** , расположенная в разделе **назначение маршрутов Федерации сайтов** , имеет значение " **отключено**".</span><span class="sxs-lookup"><span data-stu-id="bbbdd-148">As shown in the previous figure, the **SIP federation** located under **Site federation route assignment** is set to **Disabled**.</span></span>

## <a name="to-configure-certificates-on-the-lync-server-2013-edge-server"></a><span data-ttu-id="bbbdd-149">Настройка сертификатов на пограничном сервере Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bbbdd-149">To configure certificates on the Lync Server 2013 Edge Server</span></span>

1.  <span data-ttu-id="bbbdd-150">Экспортируйте сертификат прокси внешнего доступа с закрытым ключом из устаревшего пограничного сервера Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="bbbdd-150">Export the external Access Proxy certificate, with the private key, from the legacy Office Communications Server 2007 R2 Edge Server.</span></span>

2.  <span data-ttu-id="bbbdd-151">На пограничном сервере Lync Server 2013 импортируйте внешний сертификат прокси-сервера доступа на предыдущем этапе.</span><span class="sxs-lookup"><span data-stu-id="bbbdd-151">On the Lync Server 2013 Edge Server, import the Access Proxy external certificate from the previous step.</span></span>

3.  <span data-ttu-id="bbbdd-152">Назначьте внешний интерфейс для доступа к внешним данным прокси-сервера для Lync Server 2013 внешний сервер пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="bbbdd-152">Assign the Access Proxy external certificate to the Lync Server 2013 external interface of the Edge Server.</span></span>

4.  <span data-ttu-id="bbbdd-153">Сертификат внутреннего интерфейса сервера Lync Server 2013 EDGE не должен изменяться.</span><span class="sxs-lookup"><span data-stu-id="bbbdd-153">The internal interface certificate of the Lync Server 2013 Edge Server should not be changed.</span></span>

## <a name="to-change-office-communications-server-2007-r2-federation-route-to-use-lync-server-2013-edge-server"></a><span data-ttu-id="bbbdd-154">Изменение маршрута Федерации Office Communications Server 2007 R2 для использования Lync Server 2013 Edge Server</span><span class="sxs-lookup"><span data-stu-id="bbbdd-154">To change Office Communications Server 2007 R2 federation route to use Lync Server 2013 Edge Server</span></span>

1.  <span data-ttu-id="bbbdd-155">На сервере Office Communications Server 2007 R2 Standard Edition или сервере переднего плана откройте средство администрирования Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="bbbdd-155">On the Office Communications Server 2007 R2 Standard Edition server or Front End Server, open the Office Communications Server 2007 R2 Administrative tool.</span></span>

2.  <span data-ttu-id="bbbdd-156">На левой панели разверните верхний узел и щелкните правой кнопкой мыши узел **леса** .</span><span class="sxs-lookup"><span data-stu-id="bbbdd-156">In the left pane, expand the top node, and then right-click the **Forest** node.</span></span> <span data-ttu-id="bbbdd-157">Нажмите кнопку **Свойства**, а затем — **глобальные свойства**.</span><span class="sxs-lookup"><span data-stu-id="bbbdd-157">Select **Properties**, and then click **Global Properties**.</span></span>

3.  <span data-ttu-id="bbbdd-158">Откройте вкладку **Федерация** .</span><span class="sxs-lookup"><span data-stu-id="bbbdd-158">Click the **Federation** tab.</span></span>

4.  <span data-ttu-id="bbbdd-159">Установите флажок, чтобы включить функцию подключения к службам федерации и общедоступного обмена мгновенными сообщениями.</span><span class="sxs-lookup"><span data-stu-id="bbbdd-159">Select the check box to enable federation and Public IM connectivity.</span></span>

5.  <span data-ttu-id="bbbdd-160">Введите полное доменное имя Lync Server 2013, а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="bbbdd-160">Enter the FQDN of the Lync Server 2013 Edge Server, and then click **OK**.</span></span>
    
    <span data-ttu-id="bbbdd-161">![Глобальные свойства OCS, вкладка "Федерация"] (images/JJ721925.da633f72-43c6-4dac-8d37-ccd0dcde79c9(OCS.15).jpg "Глобальные свойства OCS, вкладка \"Федерация\"")</span><span class="sxs-lookup"><span data-stu-id="bbbdd-161">![OCS Global Properties, Federation tab](images/JJ721925.da633f72-43c6-4dac-8d37-ccd0dcde79c9(OCS.15).jpg "OCS Global Properties, Federation tab")</span></span>

## <a name="to-turn-on-lync-server-2013-edge-server-federation"></a><span data-ttu-id="bbbdd-162">Включение интеграции сервера Lync Server 2013 Edge Server</span><span class="sxs-lookup"><span data-stu-id="bbbdd-162">To turn on Lync Server 2013 Edge Server federation</span></span>

1.  <span data-ttu-id="bbbdd-163">Из построителя топологии на левой панели перейдите к узлу пулы Lync Server 2013 **Edge** .</span><span class="sxs-lookup"><span data-stu-id="bbbdd-163">From Topology Builder, in the left pane, navigate to the Lync Server 2013 **Edge pools** node.</span></span>

2.  <span data-ttu-id="bbbdd-164">Разверните узел, щелкните правой кнопкой мыши пограничный сервер в списке и выберите команду **изменить свойства**.</span><span class="sxs-lookup"><span data-stu-id="bbbdd-164">Expand the node, right-click the Edge Server listed, and then click **Edit Properties**.</span></span>
    

    > [!NOTE]  
    > <span data-ttu-id="bbbdd-165">Интеграция может быть включена только для одного пула пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="bbbdd-165">Federation can only be enabled for a single Edge pool.</span></span> <span data-ttu-id="bbbdd-166">Если у вас несколько пулов EDGE, выберите один из них, чтобы использовать его в качестве пула пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="bbbdd-166">If you have multiple Edge pools, select one to use as the federating Edge pool.</span></span>



3.  <span data-ttu-id="bbbdd-167">На странице " **Общие** " установите флажок **включить федерацию для этого пула Edge (порт 5061)** .</span><span class="sxs-lookup"><span data-stu-id="bbbdd-167">On the **General** page, select the **Enable federation for this Edge pool (Port 5061)** check box.</span></span>
    
    <span data-ttu-id="bbbdd-168">![Изменение свойств, общее, включение пограничного Федерации] (images/JJ721925.2aeb5958-da55-4910-b3d7-2124e144a2f0(OCS.15).jpg "Изменение свойств, общее, включение пограничного Федерации")</span><span class="sxs-lookup"><span data-stu-id="bbbdd-168">![Edit Properties, General, Enable Edge Federation](images/JJ721925.2aeb5958-da55-4910-b3d7-2124e144a2f0(OCS.15).jpg "Edit Properties, General, Enable Edge Federation")</span></span>

4.  <span data-ttu-id="bbbdd-169">Нажмите кнопку **ОК** , чтобы закрыть страницу Изменение свойств.</span><span class="sxs-lookup"><span data-stu-id="bbbdd-169">Click **OK** to close the Edit Properties page.</span></span>

5.  <span data-ttu-id="bbbdd-170">Затем перейдите к узлу сайта.</span><span class="sxs-lookup"><span data-stu-id="bbbdd-170">Next, navigate to the site node.</span></span>

6.  <span data-ttu-id="bbbdd-171">Щелкните сайт правой кнопкой мыши и выберите команду **изменить свойства**.</span><span class="sxs-lookup"><span data-stu-id="bbbdd-171">Right-click the site, and then click **Edit Properties**.</span></span>

7.  <span data-ttu-id="bbbdd-172">В левой области выберите пункт **маршрут Федерации**.</span><span class="sxs-lookup"><span data-stu-id="bbbdd-172">In the left pane, click **Federation route**.</span></span>

8.  <span data-ttu-id="bbbdd-173">В разделе **назначение маршрута Федерации сайтов**выберите **включить федерацию SIP**, а затем в списке выберите пункт Пограничный сервер Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="bbbdd-173">Under **Site federation route assignment**, select **Enable SIP federation**, and then from the list select the Lync Server 2013 Edge Server listed.</span></span>

9.  <span data-ttu-id="bbbdd-174">Нажмите кнопку **ОК** , чтобы закрыть страницу **изменение свойств** .</span><span class="sxs-lookup"><span data-stu-id="bbbdd-174">Click **OK** to close the **Edit Properties** page.</span></span>
    
    <span data-ttu-id="bbbdd-175">![Изменение свойств, общее, связывание пограничного пула] (images/JJ721925.33d43297-10cd-412e-bf4a-a1d9a84b9009(OCS.15).jpg "Изменение свойств, общее, связывание пограничного пула")</span><span class="sxs-lookup"><span data-stu-id="bbbdd-175">![Edit Properties, General, Associate Edge pool](images/JJ721925.33d43297-10cd-412e-bf4a-a1d9a84b9009(OCS.15).jpg "Edit Properties, General, Associate Edge pool")</span></span>
    
    <span data-ttu-id="bbbdd-176">Для развертываний с несколькими сайтами выполните эту процедуру на каждом сайте.</span><span class="sxs-lookup"><span data-stu-id="bbbdd-176">For multi-site deployments, complete this procedure at each site.</span></span>

## <a name="to-configure-lync-server-2013-edge-server-outbound-media-path"></a><span data-ttu-id="bbbdd-177">Настройка пути исходящего носителя для Lync Server 2013 Edge Server</span><span class="sxs-lookup"><span data-stu-id="bbbdd-177">To configure Lync Server 2013 Edge Server outbound media path</span></span>

1.  <span data-ttu-id="bbbdd-178">В **построителе топологии**перейдите на пул Lync Server 2013 ниже **стандартных внешних серверов выпуска** и пулов предварительных **интерфейсов Enterprise Edition**.</span><span class="sxs-lookup"><span data-stu-id="bbbdd-178">From **Topology Builder**, navigate to the Lync Server 2013 pool below **Standard Edition Front End Servers** or **Enterprise Edition Front End pools**.</span></span>

2.  <span data-ttu-id="bbbdd-179">Щелкните пул правой кнопкой мыши и выберите команду **изменить свойства**.</span><span class="sxs-lookup"><span data-stu-id="bbbdd-179">Right-click the pool, and then click **Edit Properties**.</span></span>

3.  <span data-ttu-id="bbbdd-180">В разделе " **связи** " установите флажок " **связать пул EDGE (для компонентов мультимедиа)** ".</span><span class="sxs-lookup"><span data-stu-id="bbbdd-180">In the **Associations** section, select the **Associate Edge pool (for media components)** check box.</span></span>

4.  <span data-ttu-id="bbbdd-181">В раскрывающемся списке выберите Lync Server 2013 Edge Server.</span><span class="sxs-lookup"><span data-stu-id="bbbdd-181">From the drop down box, select the Lync Server 2013 Edge Server.</span></span>
    
    <span data-ttu-id="bbbdd-182">![Диалоговое окно "изменение свойств", "связать пул Edge] " (images/JJ721925.0cb76b08-5923-4972-8d7a-a829cb77136b(OCS.15).jpg "Диалоговое окно \"изменение свойств\", \"связать пул Edge") "</span><span class="sxs-lookup"><span data-stu-id="bbbdd-182">![Edit Properties dialog, Associate Edge Pool](images/JJ721925.0cb76b08-5923-4972-8d7a-a829cb77136b(OCS.15).jpg "Edit Properties dialog, Associate Edge Pool")</span></span>

5.  <span data-ttu-id="bbbdd-183">Нажмите кнопку **ОК** , чтобы закрыть страницу **изменение свойств** .</span><span class="sxs-lookup"><span data-stu-id="bbbdd-183">Click **OK** to close the **Edit Properties** page.</span></span>

## <a name="to-publish-edge-server-configuration-changes"></a><span data-ttu-id="bbbdd-184">Публикация изменений в конфигурации пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="bbbdd-184">To publish Edge Server configuration changes</span></span>

1.  <span data-ttu-id="bbbdd-185">В **построителе топологии**выберите верхний узел **Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="bbbdd-185">From **Topology Builder**, select the top node **Lync Server**.</span></span>

2.  <span data-ttu-id="bbbdd-186">В меню **действия** выберите пункт **топология публикации** и завершите работу мастера.</span><span class="sxs-lookup"><span data-stu-id="bbbdd-186">From the **Action** menu, select **Publish Topology** and complete the wizard.</span></span>

3.  <span data-ttu-id="bbbdd-187">Дождитесь, когда репликация службы каталогов Active Directory будет выполняться для всех пулов в развертывании.</span><span class="sxs-lookup"><span data-stu-id="bbbdd-187">Wait for Active Directory replication to occur to all pools in the deployment.</span></span>
    

    > [!NOTE]  
    > <span data-ttu-id="bbbdd-188">Может появиться следующее сообщение:</span><span class="sxs-lookup"><span data-stu-id="bbbdd-188">You may see the following message:</span></span><BR><span data-ttu-id="bbbdd-189"><STRONG>Предупреждение: топология состоит из нескольких федеративных пограничного сервера. Это может происходить при миграции в более позднюю версию продукта. В этом случае только один сервер пограничного сервера используется только для Федерации. Убедитесь, что внешняя SRV-запись DNS указывает на правильный пограничный сервер. Если вы хотите одновременно использовать несколько одновременных пограничного сервера федерации (то есть не для миграции), убедитесь в том, что все Федеративные партнеры используют Office Communications Server 2007 R2 или Lync Server. Убедитесь, что внешняя SRV-запись содержит все пограничные серверы, поддерживающие Федерацию.</STRONG></span><span class="sxs-lookup"><span data-stu-id="bbbdd-189"><STRONG>Warning: The topology contains more than one Federated Edge Server. This can occur during migration to a more recent version of the product. In that case, only one Edge Server would be actively used for federation. Verify that the external DNS SRV record points to the correct Edge Server. If you want to deploy multiple federation Edge Server to be active concurrently (that is, not a migration scenario), verify that all federated partners are using Office Communications Server 2007 R2 or Lync Server. Verify that the external DNS SRV record lists all federation enabled Edge Servers.</STRONG></span></span><BR><span data-ttu-id="bbbdd-190">Это предупреждение ожидается, и его можно игнорировать.</span><span class="sxs-lookup"><span data-stu-id="bbbdd-190">This warning is expected and can be safely ignored.</span></span>



## <a name="to-verify-federation-and-remote-access-for-external-users"></a><span data-ttu-id="bbbdd-191">Проверка Федерации и удаленного доступа для внешних пользователей</span><span class="sxs-lookup"><span data-stu-id="bbbdd-191">To verify federation and remote access for external users</span></span>

1.  <span data-ttu-id="bbbdd-192">На сервере переднего плана Lync Server 2013 откройте командную консоль Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="bbbdd-192">From the Lync Server 2013 Front End Server, open the Lync Server Management Shell.</span></span>

2.  <span data-ttu-id="bbbdd-193">Чтобы проверить состояние Федерации и удаленного доступа, в командной строке введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="bbbdd-193">To verify the status of federation and remote access, from the command line, type the following:</span></span>
    
        Get-CsAccessEdgeConfiguration

3.  <span data-ttu-id="bbbdd-194">Чтобы включить федерацию и удаленный доступ, в командной строке введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="bbbdd-194">To enable federation and remote access, from the command line, type the following:</span></span>
    
        Set-CsAccessEdgeConfiguration
    
    <span data-ttu-id="bbbdd-195">Дополнительные сведения об этих командлетах можно найти в следующих статьях: [Get-ксакцесседжеконфигуратион](https://technet.microsoft.com/en-us/library/gg398574\(v=ocs.15\)) и [Set-ксакцесседжеконфигуратион](https://technet.microsoft.com/en-us/library/gg413017\(v=ocs.15\)).</span><span class="sxs-lookup"><span data-stu-id="bbbdd-195">For more information on these cmdlets, see the following topics: [Get-CsAccessEdgeConfiguration](https://technet.microsoft.com/en-us/library/gg398574\(v=ocs.15\)) and [Set-CsAccessEdgeConfiguration](https://technet.microsoft.com/en-us/library/gg413017\(v=ocs.15\)).</span></span>

4.  <span data-ttu-id="bbbdd-196">Дождитесь завершения репликации, прежде чем приступить к переходу на Интернет-сервер Lync Server 2013 и протестировать Федерацию и внешний доступ.</span><span class="sxs-lookup"><span data-stu-id="bbbdd-196">Wait until replication has completed before bringing the Lync Server 2013 Edge servers online, and testing federation and external access.</span></span>

## <a name="to-configure-lync-server-2013-edge-server"></a><span data-ttu-id="bbbdd-197">Настройка пограничного сервера Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bbbdd-197">To configure Lync Server 2013 Edge Server</span></span>

1.  <span data-ttu-id="bbbdd-198">Выведите все серверы Lync Server 2013 Edge-in Online.</span><span class="sxs-lookup"><span data-stu-id="bbbdd-198">Bring all of the Lync Server 2013 Edge Servers online.</span></span>

2.  <span data-ttu-id="bbbdd-199">Обновите правила маршрутизации внешних брандмауэров или параметры подсистемы балансировки нагрузки оборудования, чтобы отправить трафик SIP для внешнего доступа (обычно это порт 443) и Федерацию (обычно это порт 5061) на пограничный сервер Lync Server 2013 вместо устаревшего пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="bbbdd-199">Update the external firewall routing rules or the hardware load balancer settings to send SIP traffic for external access (usually port 443) and federation (usually port 5061) to the Lync Server 2013 Edge Server, instead of the legacy Edge Server.</span></span>
    

    > [!NOTE]  
    > <span data-ttu-id="bbbdd-200">Если у вас нет аппаратной подсистемы балансировки нагрузки, вам нужно обновить запись DNS A для Федерации, чтобы разрешить новый пограничный сервер Lync Server Access.</span><span class="sxs-lookup"><span data-stu-id="bbbdd-200">If you do not have a hardware load balancer, you need to update the DNS A record for federation to resolve the new Lync Server Access Edge server.</span></span> <span data-ttu-id="bbbdd-201">Чтобы сделать это с минимальным нарушением, сократите значение TTL для внешнего полного доменного имени сервера Lync Server, чтобы при обновлении DNS указывался на новый сервер пограничного сервера Lync Server Access, служба Федерации и удаленный доступ будут быстро обновлены.</span><span class="sxs-lookup"><span data-stu-id="bbbdd-201">To accomplish this with minimum disruption, reduce the TTL value for the external Lync Server Access Edge FQDN so that when DNS is updated to point to the new Lync Server Access Edge server, federation and remote access will be updated quickly.</span></span>



3.  <span data-ttu-id="bbbdd-202">Затем остановите **границу доступа Lync Server** с каждого компьютера пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="bbbdd-202">Next, stop the **Lync Server Access Edge** from each Edge Server computer.</span></span>

4.  <span data-ttu-id="bbbdd-203">На каждом компьютере пограничного серверного сервера откройте приложение " **службы** " из **меню**"Администрирование".</span><span class="sxs-lookup"><span data-stu-id="bbbdd-203">From each legacy Edge Server computer, open the **Services** applet from the **Administrative Tools**.</span></span>

5.  <span data-ttu-id="bbbdd-204">В списке Services (службы) найдите элемент **Office Communications Server Access Edge**.</span><span class="sxs-lookup"><span data-stu-id="bbbdd-204">In the services list, find **Office Communications Server Access Edge**.</span></span>

6.  <span data-ttu-id="bbbdd-205">Щелкните правой кнопкой мыши имя службы, а затем выберите команду **остановить** , чтобы остановить службу.</span><span class="sxs-lookup"><span data-stu-id="bbbdd-205">Right-click the services name, and then select **Stop** to stop the service.</span></span>

7.  <span data-ttu-id="bbbdd-206">Установите для типа запуска значение **отключено**.</span><span class="sxs-lookup"><span data-stu-id="bbbdd-206">Set the Startup type to **Disabled**.</span></span>

8.  <span data-ttu-id="bbbdd-207">Нажмите кнопку **ОК** , чтобы закрыть окно " **свойства** ".</span><span class="sxs-lookup"><span data-stu-id="bbbdd-207">Click **OK** to close the **Properties** window.</span></span>

## <a name="to-test-connectivity-of-external-users-and-external-access"></a><span data-ttu-id="bbbdd-208">Проверка подключения внешних пользователей и внешнего доступа</span><span class="sxs-lookup"><span data-stu-id="bbbdd-208">To Test Connectivity of External Users and External access</span></span>

  - <span data-ttu-id="bbbdd-209">Пользователи, у которых есть хотя бы один федеративный домен, внутренний пользователь на Lync Server 2013 и пользователь в Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="bbbdd-209">Users from at least one federated domain, an internal user on Lync Server 2013 and a user on Office Communications Server 2007 R2.</span></span> <span data-ttu-id="bbbdd-210">Протестируйте обмен мгновенными сообщениями, присутствие, звук и видео (A/V) и общий доступ к рабочему столу.</span><span class="sxs-lookup"><span data-stu-id="bbbdd-210">Test instant messaging (IM), presence, audio/video (A/V), and desktop sharing.</span></span>

  - <span data-ttu-id="bbbdd-211">Пользователи всех общедоступных служб обмена мгновенными сообщениями, которые поддерживаются вашей организацией (и для которых была выполнена подготовка) взаимодействия с пользователем в Lync Server 2013 и пользователем в Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="bbbdd-211">Users of each public IM service provider that your organization supports (and for which provisioning has been completed) communicating with a user on Lync Server 2013 and a user on Office Communications Server 2007 R2.</span></span>

  - <span data-ttu-id="bbbdd-212">Убедитесь в том, что анонимные пользователи смогут присоединиться к конференциям.</span><span class="sxs-lookup"><span data-stu-id="bbbdd-212">Verify anonymous users are able to join conferences.</span></span>

  - <span data-ttu-id="bbbdd-213">Пользователь, размещенный на сервере Office Communications Server 2007 R2 с удаленным доступом пользователей (вход в Office Communications Server 2007 R2 из-за пределов интрасети, но не VPN) с пользователем Lync Server 2013 и пользователем в Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="bbbdd-213">A user hosted on Office Communications Server 2007 R2 using remote user access (logging into Office Communications Server 2007 R2 from outside the intranet but without VPN) with a user on Lync Server 2013, and a user on Office Communications Server 2007 R2.</span></span> <span data-ttu-id="bbbdd-214">Проверка обмена мгновенными сообщениями, сведений о присутствии, а/V и совместном использовании рабочего стола.</span><span class="sxs-lookup"><span data-stu-id="bbbdd-214">Test IM, presence, A/V, and desktop sharing.</span></span>

  - <span data-ttu-id="bbbdd-215">Пользователь, размещенный на Lync Server 2013 с удаленным доступом пользователей (вход в Lync Server 2013 из-за пределов интрасети, но не VPN) с пользователем на Lync Server 2013 и пользователем в Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="bbbdd-215">A user hosted on Lync Server 2013 using remote user access (logging into Lync Server 2013 from outside the intranet but without VPN) with a user on Lync Server 2013, and a user on Office Communications Server 2007 R2.</span></span> <span data-ttu-id="bbbdd-216">Проверка обмена мгновенными сообщениями, сведений о присутствии, а/V и совместном использовании рабочего стола.</span><span class="sxs-lookup"><span data-stu-id="bbbdd-216">Test IM, presence, A/V, and desktop sharing.</span></span>

