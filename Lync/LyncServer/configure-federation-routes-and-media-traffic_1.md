---
title: Настройка маршрутов федерации и трафика мультимедиа
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Configure federation routes and media traffic
ms:assetid: ed6cb922-7863-453a-adce-2ce0ba761d74
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721925(v=OCS.15)
ms:contentKeyID: 49733860
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0d6af77188809b092050629c1b74cdab8b20a2cc
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/16/2020
ms.locfileid: "44754965"
---
# <a name="configure-federation-routes-and-media-traffic"></a><span data-ttu-id="629de-102">Настройка маршрутов федерации и трафика мультимедиа</span><span class="sxs-lookup"><span data-stu-id="629de-102">Configure federation routes and media traffic</span></span>

 


<span data-ttu-id="629de-103">Федерация — это доверительные отношения между двумя или более SIP-доменами, которые позволяют пользователям в различных организациях обмениваться информацией через сетевые границы.</span><span class="sxs-lookup"><span data-stu-id="629de-103">Federation is a trust relationship between two or more SIP domains that permits users in separate organizations to communicate across network boundaries.</span></span> <span data-ttu-id="629de-104">После миграции в пилотный пул Lync Server 2013 вам необходимо перейти с маршрута Федерации на пограничные серверы Microsoft Office Communications Server 2007 R2 к маршруту Федерации на пограничных серверах Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="629de-104">After you migrate to your Lync Server 2013 pilot pool, you need to transition from the federation route of your Microsoft Office Communications Server 2007 R2 Edge Servers to the federation route of your Lync Server 2013 Edge Servers.</span></span>

<span data-ttu-id="629de-105">Используйте приведенные ниже процедуры для переноса маршрута Федерации и маршрута трафика мультимедиа с пограничного сервера Office Communications Server 2007 R2 на пограничный сервер Lync Server 2013 на пограничный сервер Lync Server для развертывания на едином сайте.</span><span class="sxs-lookup"><span data-stu-id="629de-105">Use the procedures that follow to transition the federation route and the media traffic route from your Office Communications Server 2007 R2 Edge Server and Director to your Lync Server 2013 Edge Server, for a single-site deployment.</span></span>


> [!IMPORTANT]  
> <span data-ttu-id="629de-106">Для изменения маршрута Федерации и маршрута трафика мультимедиа необходимо запланировать время простоя обслуживания для пограничных серверов Lync Server 2013 и Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="629de-106">Changing the federation route and media traffic route requires that you schedule maintenance downtime for the Lync Server 2013 and Office Communications Server 2007 R2 Edge Servers.</span></span> <span data-ttu-id="629de-107">Весь процесс перехода также означает, что федеративный доступ будет отключен во время простоя.</span><span class="sxs-lookup"><span data-stu-id="629de-107">This entire transition process also means that federated access will be unavailable for the duration of the outage.</span></span> <span data-ttu-id="629de-108">Следует запланировать простой на период, когда активность пользователей будет минимальной.</span><span class="sxs-lookup"><span data-stu-id="629de-108">You should schedule the downtime for a time when you expect minimal user activity.</span></span> <span data-ttu-id="629de-109">Также следует реализовать своевременное уведомление конечных пользователей.</span><span class="sxs-lookup"><span data-stu-id="629de-109">You should also provide sufficient notification to your end users.</span></span> <span data-ttu-id="629de-110">Тщательно запланируйте простой и задайте соответствующие ожидания в организации.</span><span class="sxs-lookup"><span data-stu-id="629de-110">Plan accordingly for this outage and set appropriate expectations within your organization.</span></span>




> [!IMPORTANT]  
> <span data-ttu-id="629de-111">Если устаревший пограничный сервер Office Communications Server 2007 R2 настроен на использование того же полного доменного имени для пограничной службы доступа, пограничной службы веб-конференций и пограничной службы аудио-и видеоданных, процедуры, описанные в этом разделе, не поддерживают перенос параметров Федерации на пограничный сервер Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="629de-111">If your legacy Office Communications Server 2007 R2 Edge Server is configured to use the same FQDN for the Access Edge service, Web Conferencing Edge service, and the A/V Edge service, the procedures in this section to transition the federation setting to a Lync Server 2013 Edge Server are not supported.</span></span> <span data-ttu-id="629de-112">Если устаревшие пограничные службы настроены на использование одного полного доменного имени, необходимо сначала перенести всех пользователей из Office Communications Server 2007 R2 в Lync Server 2013, а затем списать пограничный сервер Office Communications Server 2007 R2 перед включением Федерации на пограничном сервере Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="629de-112">If the legacy Edge services are configured to use the same FQDN, you must first migrate all your users from Office Communications Server 2007 R2 to Lync Server 2013, then decommission the Office Communications Server 2007 R2 Edge Server before enabling federation on the Lync Server 2013 Edge Server.</span></span> <span data-ttu-id="629de-113">Дополнительные сведения см. в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="629de-113">For details, see the following topics:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="629de-114"><A href="move-remaining-users-to-lync-server-2013_1.md">Перемещение оставшихся пользователей на Lync Server 2013</A></span><span class="sxs-lookup"><span data-stu-id="629de-114"><A href="move-remaining-users-to-lync-server-2013_1.md">Move remaining users to Lync Server 2013</A></span></span></P>
> <LI>
> <P><span data-ttu-id="629de-115">"Удаление серверов и ролей серверов" по адресу<A href="https://go.microsoft.com/fwlink/p/?linkid=268790">https://go.microsoft.com/fwlink/p/?LinkId=268790</A></span><span class="sxs-lookup"><span data-stu-id="629de-115">"Remove Servers and Server Roles" at <A href="https://go.microsoft.com/fwlink/p/?linkid=268790">https://go.microsoft.com/fwlink/p/?LinkId=268790</A></span></span></P></LI></UL>




> [!IMPORTANT]  
> <span data-ttu-id="629de-116">Если Федерация XMPP направляется через пограничный сервер Lync Server 2013, устаревшие пользователи Office Communications Server 2007 R2 не смогут общаться с федеративным партнером XMPP до тех пор, пока все пользователи не будут перемещены в Lync Server 2013, XMPP политики и сертификаты настроены, федеративный партнер XMPP настроен на Lync Server 2013, а последние DNS-записи были обновлены.</span><span class="sxs-lookup"><span data-stu-id="629de-116">If your XMPP federation is routed through a Lync Server 2013 Edge Server, legacy Office Communications Server 2007 R2 users will not be able to communicate with the XMPP federated partner until all users have been moved to Lync Server 2013, XMPP policies and certificates have been configured, the XMPP federated partner has been configured on Lync Server 2013, and lastly the DNS entries have been updated.</span></span>



<span data-ttu-id="629de-117">Чтобы успешно опубликовать, включить, или выключить топологию при добавлении или удалении роли сервера, необходимо войти в систему как пользователь, являющийся участником групп RTCUniversalServerAdmins и "Администраторы домена".</span><span class="sxs-lookup"><span data-stu-id="629de-117">To successfully publish, enable, or disable a topology when adding or removing a server role, you should be logged in as a user who is a member of the RTCUniversalServerAdmins and Domain Admins groups.</span></span> <span data-ttu-id="629de-118">Также для добавления ролей сервера можно делегировать соответствующие права и разрешения пользователя.</span><span class="sxs-lookup"><span data-stu-id="629de-118">It is also possible to delegate the proper user rights and permissions for adding server roles.</span></span> <span data-ttu-id="629de-119">Для получения дополнительных сведений обратитесь к разделу [Делегирование разрешений на установку в Lync Server 2013](lync-server-2013-delegate-setup-permissions.md) в документации по развертыванию сервера Standard Edition или Enterprise Edition Server.</span><span class="sxs-lookup"><span data-stu-id="629de-119">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md) in the Standard Edition server or Enterprise Edition server Deployment documentation.</span></span> <span data-ttu-id="629de-120">Для других изменений конфигурации требуется только участие в группе RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="629de-120">For other configuration changes, only membership in the RTCUniversalServerAdmins group is required.</span></span>

## <a name="to-remove-the-legacy-federation-association-from-lync-server-2013-sites"></a><span data-ttu-id="629de-121">Удаление устаревшей связи федерации на сайтах Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="629de-121">To remove the legacy federation association from Lync Server 2013 sites</span></span>

1.  <span data-ttu-id="629de-122">Откройте топологию пилотного пула с помощью построителя топологии.</span><span class="sxs-lookup"><span data-stu-id="629de-122">Open the pilot pool topology using Topology Builder.</span></span>

2.  <span data-ttu-id="629de-123">В левой области перейдите к узлу сайта.</span><span class="sxs-lookup"><span data-stu-id="629de-123">In the left pane, navigate to the site node.</span></span>

3.  <span data-ttu-id="629de-124">Щелкните сайт правой кнопкой мыши и выберите команду **Изменить свойства**.</span><span class="sxs-lookup"><span data-stu-id="629de-124">Right-click the site, and then click **Edit Properties**.</span></span>

4.  <span data-ttu-id="629de-125">Выберите параметр **Федеративный маршрут** в левой панели.</span><span class="sxs-lookup"><span data-stu-id="629de-125">Select **Federation route** in the left pane.</span></span>

5.  <span data-ttu-id="629de-126">В разделе "Назначение федеративного маршрута сайта" снимите флажок **Включить SIP-федерацию**, чтобы отключить федеративный маршрут с помощью **BackCompatSite**.</span><span class="sxs-lookup"><span data-stu-id="629de-126">Under Site federation route assignment, clear the check box next to **Enable SIP federation** to disable the federation route through the **BackCompatSite**.</span></span>
    
    <span data-ttu-id="629de-127">![Диалоговое окно изменения свойств, маршрут Федерации](images/JJ721925.2a80c103-c0cc-43ed-ba00-420f9add006a(OCS.15).jpg "Диалоговое окно изменения свойств, маршрут Федерации")</span><span class="sxs-lookup"><span data-stu-id="629de-127">![Edit Properties dialog, Federation route](images/JJ721925.2a80c103-c0cc-43ed-ba00-420f9add006a(OCS.15).jpg "Edit Properties dialog, Federation route")</span></span>

6.  <span data-ttu-id="629de-128">Нажмите кнопку **ОК**, чтобы закрыть страницу "Изменение свойств".</span><span class="sxs-lookup"><span data-stu-id="629de-128">Click **OK** to close the Edit Properties page.</span></span>

7.  <span data-ttu-id="629de-129">В **построителе топологии** выберите верхний узел **Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="629de-129">From **Topology Builder**, select the top node **Lync Server**.</span></span>

8.  <span data-ttu-id="629de-130">В меню **Действие** выберите команду **Опубликовать топологию** и завершите работу мастера.</span><span class="sxs-lookup"><span data-stu-id="629de-130">From the **Action** menu, click **Publish Topology** and complete the wizard.</span></span>

## <a name="to-configure-the-legacy-edge-server-as-a-non-federating-edge-server"></a><span data-ttu-id="629de-131">Настройка устаревшего пограничного сервера в качестве пограничного сервера без федерации</span><span class="sxs-lookup"><span data-stu-id="629de-131">To configure the legacy Edge Server as a non-federating Edge Server</span></span>

1.  <span data-ttu-id="629de-132">В **построителе топологий** в меню **Действие** щелкните **Объединить топологию Office Communications Server 2007 R2**.</span><span class="sxs-lookup"><span data-stu-id="629de-132">From **Topology Builder**, from the **Action** menu click **Merge Office Communications Server 2007 R2 Topology**.</span></span>

2.  <span data-ttu-id="629de-133">Для продолжения нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="629de-133">Click **Next** to continue.</span></span>

3.  <span data-ttu-id="629de-134">На странице **Настройка пограничного сервера** выберите параметр **Внутреннее полное доменное имя пограничного сервера**, которое в настоящий момент настроено для федерации, а затем нажмите кнопку **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="629de-134">On the **Specify Edge Setup**, select the **Edge Server Internal FQDN** that is currently configured for federation, and then click **Change**.</span></span>
    
    <span data-ttu-id="629de-135">![Слияние топологии OCS 2007 R2, указание параметров пограничного сервера](images/JJ721925.42c15aaf-c1ac-4fb1-a086-665835c57b23(OCS.15).jpg "Слияние топологии OCS 2007 R2, указание параметров пограничного сервера")</span><span class="sxs-lookup"><span data-stu-id="629de-135">![Merge OCS 2007 R2 Topology, Specify Edge Setup](images/JJ721925.42c15aaf-c1ac-4fb1-a086-665835c57b23(OCS.15).jpg "Merge OCS 2007 R2 Topology, Specify Edge Setup")</span></span>

4.  <span data-ttu-id="629de-136">Нажмите кнопку **Далее** и принимайте параметры по умолчанию, пока вы не попадете на страницу **Укажите внешний пограничный сервер**:</span><span class="sxs-lookup"><span data-stu-id="629de-136">Click **Next** and accept the default settings until you get to the **Specify External Edge** page:</span></span>
    
    <span data-ttu-id="629de-137">![Построитель топологий Указание внешнего пограничной страницы](images/JJ721925.e36f3a1f-3655-456e-9e6d-4814c37da0bf(OCS.15).jpg "Построитель топологий Указание внешнего пограничной страницы")</span><span class="sxs-lookup"><span data-stu-id="629de-137">![Topology Builder Specify External Edge page](images/JJ721925.e36f3a1f-3655-456e-9e6d-4814c37da0bf(OCS.15).jpg "Topology Builder Specify External Edge page")</span></span>

5.  <span data-ttu-id="629de-p105">В окне **Укажите внешний пограничный сервер** снимите флажок **Этот пограничный пул используется для федерации и подключения к общедоступным службам обмена мгновенными сообщениями**. При этом будет удалена федеративная связь с BackCompatSite.</span><span class="sxs-lookup"><span data-stu-id="629de-p105">In **Specify External Edge**, clear the **This Edge pool is used for federation and public IM connectivity** check box. This will remove the federation association with the BackCompatSite.</span></span>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="629de-p106">Этот шаг очень важен. Следует снять этот флажок, чтобы удалить старую федеративную связь.</span><span class="sxs-lookup"><span data-stu-id="629de-p106">This step is important. You must clear this option to remove the legacy federation association.</span></span>



6.  <span data-ttu-id="629de-142">Нажмите кнопку **Далее** и примите настройки по умолчанию на оставшихся страницах мастера.</span><span class="sxs-lookup"><span data-stu-id="629de-142">Click **Next** and accept the default settings of the remaining pages of the wizard.</span></span>

7.  <span data-ttu-id="629de-143">В окне **Сводка** нажмите кнопку **Далее**, чтобы начать слияние топологий.</span><span class="sxs-lookup"><span data-stu-id="629de-143">In **Summary**, click **Next** to begin merging the topologies.</span></span>

8.  <span data-ttu-id="629de-144">В столбце **состояние** убедитесь, что значение является **успешным**, а затем нажмите кнопку **Готово** , чтобы закрыть мастер.</span><span class="sxs-lookup"><span data-stu-id="629de-144">In the **Status** column, verify that the value is **Success**, and then click **Finish** to close the wizard.</span></span>

9.  <span data-ttu-id="629de-145">В меню **Действие** выберите пункт **Публикация топологии**, а затем щелкните **Далее**.</span><span class="sxs-lookup"><span data-stu-id="629de-145">From the **Action** menu, select **Publish Topology**, and then click **Next**.</span></span>

10. <span data-ttu-id="629de-146">После завершения работы **мастера публикации**, нажмите кнопку **Готово**, чтобы закрыть мастер.</span><span class="sxs-lookup"><span data-stu-id="629de-146">When the **Publishing wizard** completes, click **Finish** to close the wizard.</span></span>
    
    <span data-ttu-id="629de-147">![Построитель топологий с сайтом, отображаемым после слияния](images/JJ721925.92b679ad-332f-49aa-b4e2-19f939b711ca(OCS.15).jpg "Построитель топологий с сайтом, отображаемым после слияния")</span><span class="sxs-lookup"><span data-stu-id="629de-147">![Topology Builder with site displayed after merge](images/JJ721925.92b679ad-332f-49aa-b4e2-19f939b711ca(OCS.15).jpg "Topology Builder with site displayed after merge")</span></span>
    
    <span data-ttu-id="629de-148">Как показано на предыдущем рисунке, для параметра **SIP-федерация**, расположенное в разделе **Назначение федеративного маршрута к узлу** задано значение **Отключено**.</span><span class="sxs-lookup"><span data-stu-id="629de-148">As shown in the previous figure, the **SIP federation** located under **Site federation route assignment** is set to **Disabled**.</span></span>

## <a name="to-configure-certificates-on-the-lync-server-2013-edge-server"></a><span data-ttu-id="629de-149">Настройка сертификатов на пограничном сервере Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="629de-149">To configure certificates on the Lync Server 2013 Edge Server</span></span>

1.  <span data-ttu-id="629de-150">Экспортируйте сертификат прокси внешнего доступа с закрытым ключом из устаревшего пограничного сервера Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="629de-150">Export the external Access Proxy certificate, with the private key, from the legacy Office Communications Server 2007 R2 Edge Server.</span></span>

2.  <span data-ttu-id="629de-151">На пограничном сервере Lync Server 2013 импортируйте внешний сертификат прокси-сервера доступа из предыдущего шага.</span><span class="sxs-lookup"><span data-stu-id="629de-151">On the Lync Server 2013 Edge Server, import the Access Proxy external certificate from the previous step.</span></span>

3.  <span data-ttu-id="629de-152">Назначьте внешний сертификат прокси-сервера доступа внешнему интерфейсу Lync Server 2013 пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="629de-152">Assign the Access Proxy external certificate to the Lync Server 2013 external interface of the Edge Server.</span></span>

4.  <span data-ttu-id="629de-153">Сертификат внутреннего интерфейса пограничного сервера Lync Server 2013 не должен изменяться.</span><span class="sxs-lookup"><span data-stu-id="629de-153">The internal interface certificate of the Lync Server 2013 Edge Server should not be changed.</span></span>

## <a name="to-change-office-communications-server-2007-r2-federation-route-to-use-lync-server-2013-edge-server"></a><span data-ttu-id="629de-154">Изменение федеративного маршрута Office Communications Server 2007 R2 для использования пограничного сервера Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="629de-154">To change Office Communications Server 2007 R2 federation route to use Lync Server 2013 Edge Server</span></span>

1.  <span data-ttu-id="629de-155">На сервере Office Communications Server 2007 R2 Standard Edition или сервере переднего плана откройте средство администрирования Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="629de-155">On the Office Communications Server 2007 R2 Standard Edition server or Front End Server, open the Office Communications Server 2007 R2 Administrative tool.</span></span>

2.  <span data-ttu-id="629de-p107">В левой области, разверните верхний узел, а затем правой кнопкой мыши щелкните узел **Лес**. Выберите **Свойства**, а затем щелкните **Глобальные свойства**.</span><span class="sxs-lookup"><span data-stu-id="629de-p107">In the left pane, expand the top node, and then right-click the **Forest** node. Select **Properties**, and then click **Global Properties**.</span></span>

3.  <span data-ttu-id="629de-158">Перейдите на вкладку \*\* Федерация\*\*.</span><span class="sxs-lookup"><span data-stu-id="629de-158">Click the **Federation** tab.</span></span>

4.  <span data-ttu-id="629de-159">Установите флажок, чтобы включить федерацию и подключение к общедоступным службам обмена мгновенными сообщениями.</span><span class="sxs-lookup"><span data-stu-id="629de-159">Select the check box to enable federation and Public IM connectivity.</span></span>

5.  <span data-ttu-id="629de-160">Введите полное доменное имя пограничного сервера Lync Server 2013 и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="629de-160">Enter the FQDN of the Lync Server 2013 Edge Server, and then click **OK**.</span></span>
    
    <span data-ttu-id="629de-161">![Глобальные свойства OCS, вкладка "Федерация"](images/JJ721925.da633f72-43c6-4dac-8d37-ccd0dcde79c9(OCS.15).jpg "Глобальные свойства OCS, вкладка "Федерация"")</span><span class="sxs-lookup"><span data-stu-id="629de-161">![OCS Global Properties, Federation tab](images/JJ721925.da633f72-43c6-4dac-8d37-ccd0dcde79c9(OCS.15).jpg "OCS Global Properties, Federation tab")</span></span>

## <a name="to-turn-on-lync-server-2013-edge-server-federation"></a><span data-ttu-id="629de-162">Включение федерации пограничного сервера Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="629de-162">To turn on Lync Server 2013 Edge Server federation</span></span>

1.  <span data-ttu-id="629de-163">В области слева построителя топологий перейдите к узлу Lync Server 2013 **Edge Pools** .</span><span class="sxs-lookup"><span data-stu-id="629de-163">From Topology Builder, in the left pane, navigate to the Lync Server 2013 **Edge pools** node.</span></span>

2.  <span data-ttu-id="629de-164">Разверните узел, щелкните правой кнопкой указанный пограничный сервер и выберите команду **Изменить свойства**.</span><span class="sxs-lookup"><span data-stu-id="629de-164">Expand the node, right-click the Edge Server listed, and then click **Edit Properties**.</span></span>
    

    > [!NOTE]  
    > <span data-ttu-id="629de-165">Федерация можно включить только для одного пограничного пула.</span><span class="sxs-lookup"><span data-stu-id="629de-165">Federation can only be enabled for a single Edge pool.</span></span> <span data-ttu-id="629de-166">Если у вас несколько пограничных пулов, выберите один из них, который будет использоваться в качестве Федерации пограничного пула.</span><span class="sxs-lookup"><span data-stu-id="629de-166">If you have multiple Edge pools, select one to use as the federating Edge pool.</span></span>



3.  <span data-ttu-id="629de-167">На странице **Общие** установите флажок **Включение федерации для этого пограничного пула (порт 5061)**.</span><span class="sxs-lookup"><span data-stu-id="629de-167">On the **General** page, select the **Enable federation for this Edge pool (Port 5061)** check box.</span></span>
    
    <span data-ttu-id="629de-168">![Изменение свойств, общие, включение пограничной Федерации](images/JJ721925.2aeb5958-da55-4910-b3d7-2124e144a2f0(OCS.15).jpg "Изменение свойств, общие, включение пограничной Федерации")</span><span class="sxs-lookup"><span data-stu-id="629de-168">![Edit Properties, General, Enable Edge Federation](images/JJ721925.2aeb5958-da55-4910-b3d7-2124e144a2f0(OCS.15).jpg "Edit Properties, General, Enable Edge Federation")</span></span>

4.  <span data-ttu-id="629de-169">Нажмите кнопку **ОК**, чтобы закрыть страницу "Изменение свойств".</span><span class="sxs-lookup"><span data-stu-id="629de-169">Click **OK** to close the Edit Properties page.</span></span>

5.  <span data-ttu-id="629de-170">Затем перейдите к узлу сайта.</span><span class="sxs-lookup"><span data-stu-id="629de-170">Next, navigate to the site node.</span></span>

6.  <span data-ttu-id="629de-171">Щелкните сайт правой кнопкой мыши и выберите команду **Изменить свойства**.</span><span class="sxs-lookup"><span data-stu-id="629de-171">Right-click the site, and then click **Edit Properties**.</span></span>

7.  <span data-ttu-id="629de-172">В левой области, выберите **Федеративный маршрут**.</span><span class="sxs-lookup"><span data-stu-id="629de-172">In the left pane, click **Federation route**.</span></span>

8.  <span data-ttu-id="629de-173">В разделе **назначение федеративного маршрута сайта**выберите **включить федерацию SIP**, а затем выберите в списке пункт Пограничный сервер Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="629de-173">Under **Site federation route assignment**, select **Enable SIP federation**, and then from the list select the Lync Server 2013 Edge Server listed.</span></span>

9.  <span data-ttu-id="629de-174">Нажмите кнопку **ОК**, чтобы закрыть страницу **изменения свойств**.</span><span class="sxs-lookup"><span data-stu-id="629de-174">Click **OK** to close the **Edit Properties** page.</span></span>
    
    <span data-ttu-id="629de-175">![Изменение свойств, общие, сопоставление пограничного пула](images/JJ721925.33d43297-10cd-412e-bf4a-a1d9a84b9009(OCS.15).jpg "Изменение свойств, общие, сопоставление пограничного пула")</span><span class="sxs-lookup"><span data-stu-id="629de-175">![Edit Properties, General, Associate Edge pool](images/JJ721925.33d43297-10cd-412e-bf4a-a1d9a84b9009(OCS.15).jpg "Edit Properties, General, Associate Edge pool")</span></span>
    
    <span data-ttu-id="629de-176">В случае развертывании с несколькими сайтами выполните эту процедуру на каждом сайте.</span><span class="sxs-lookup"><span data-stu-id="629de-176">For multi-site deployments, complete this procedure at each site.</span></span>

## <a name="to-configure-lync-server-2013-edge-server-outbound-media-path"></a><span data-ttu-id="629de-177">Настройка исходящего пути к мультимедиа пограничного сервера Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="629de-177">To configure Lync Server 2013 Edge Server outbound media path</span></span>

1.  <span data-ttu-id="629de-178">В **построителе топологий**перейдите к пулу Lync Server 2013 под **стандартным сервером переднего плана Standard Edition** или **интерфейсным пулам Enterprise Edition**.</span><span class="sxs-lookup"><span data-stu-id="629de-178">From **Topology Builder**, navigate to the Lync Server 2013 pool below **Standard Edition Front End Servers** or **Enterprise Edition Front End pools**.</span></span>

2.  <span data-ttu-id="629de-179">Щелкните пул правой кнопкой мыши и выберите команду **Изменить свойства**.</span><span class="sxs-lookup"><span data-stu-id="629de-179">Right-click the pool, and then click **Edit Properties**.</span></span>

3.  <span data-ttu-id="629de-180">В разделе **Связи** установите флажок **Связать пограничный пул (для компонентов мультимедиа)**.</span><span class="sxs-lookup"><span data-stu-id="629de-180">In the **Associations** section, select the **Associate Edge pool (for media components)** check box.</span></span>

4.  <span data-ttu-id="629de-181">В раскрывающемся списке выберите Lync Server 2013 Edge Server.</span><span class="sxs-lookup"><span data-stu-id="629de-181">From the drop down box, select the Lync Server 2013 Edge Server.</span></span>
    
    <span data-ttu-id="629de-182">![Диалоговое окно "изменение свойств" с сопоставлением пограничного пула](images/JJ721925.0cb76b08-5923-4972-8d7a-a829cb77136b(OCS.15).jpg "Диалоговое окно "изменение свойств" с сопоставлением пограничного пула")</span><span class="sxs-lookup"><span data-stu-id="629de-182">![Edit Properties dialog, Associate Edge Pool](images/JJ721925.0cb76b08-5923-4972-8d7a-a829cb77136b(OCS.15).jpg "Edit Properties dialog, Associate Edge Pool")</span></span>

5.  <span data-ttu-id="629de-183">Нажмите кнопку **ОК**, чтобы закрыть страницу **Изменение свойств**.</span><span class="sxs-lookup"><span data-stu-id="629de-183">Click **OK** to close the **Edit Properties** page.</span></span>

## <a name="to-publish-edge-server-configuration-changes"></a><span data-ttu-id="629de-184">Публикация изменений конфигурации пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="629de-184">To publish Edge Server configuration changes</span></span>

1.  <span data-ttu-id="629de-185">В **построителе топологии** выберите верхний узел **Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="629de-185">From **Topology Builder**, select the top node **Lync Server**.</span></span>

2.  <span data-ttu-id="629de-186">В меню **Действие** выберите команду **Опубликовать топологию** и завершите работу мастера.</span><span class="sxs-lookup"><span data-stu-id="629de-186">From the **Action** menu, select **Publish Topology** and complete the wizard.</span></span>

3.  <span data-ttu-id="629de-187">Дождитесь выполнения репликации Active Directory во всех пулах в развертывании.</span><span class="sxs-lookup"><span data-stu-id="629de-187">Wait for Active Directory replication to occur to all pools in the deployment.</span></span>
    

    > [!NOTE]  
    > <span data-ttu-id="629de-188">Может появиться следующее сообщение:</span><span class="sxs-lookup"><span data-stu-id="629de-188">You may see the following message:</span></span><BR><span data-ttu-id="629de-189"><STRONG>Предупреждение. Топология содержит несколько федеративных пограничных серверов. Это может произойти в процессе перехода на новую версию продукта. В таком случае только один пограничный сервер будет активно использоваться для федерации. Убедитесь, что внешняя SRV-запись DNS указывает на правильный пограничный сервер. Если требуется развернуть несколько одновременно активных пограничных серверов федерации (то есть, это не сценарий миграции), убедитесь, что все федеративные партнеры используют Office Communications Server 2007 R2 или Lync Server. Убедитесь, что во внешней SRV-записи DNS перечислены все пограничные серверы с поддержкой федерации.</STRONG></span><span class="sxs-lookup"><span data-stu-id="629de-189"><STRONG>Warning: The topology contains more than one Federated Edge Server. This can occur during migration to a more recent version of the product. In that case, only one Edge Server would be actively used for federation. Verify that the external DNS SRV record points to the correct Edge Server. If you want to deploy multiple federation Edge Server to be active concurrently (that is, not a migration scenario), verify that all federated partners are using Office Communications Server 2007 R2 or Lync Server. Verify that the external DNS SRV record lists all federation enabled Edge Servers.</STRONG></span></span><BR><span data-ttu-id="629de-190">Появление этого предупреждения ожидаемое и его можно спокойно проигнорировать.</span><span class="sxs-lookup"><span data-stu-id="629de-190">This warning is expected and can be safely ignored.</span></span>



## <a name="to-verify-federation-and-remote-access-for-external-users"></a><span data-ttu-id="629de-191">Проверка федерации и удаленного доступа для внешних пользователей</span><span class="sxs-lookup"><span data-stu-id="629de-191">To verify federation and remote access for external users</span></span>

1.  <span data-ttu-id="629de-192">На сервере переднего плана Lync Server 2013 откройте консоль управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="629de-192">From the Lync Server 2013 Front End Server, open the Lync Server Management Shell.</span></span>

2.  <span data-ttu-id="629de-193">Для проверки состояния федерации и удаленного доступа в командной строке введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="629de-193">To verify the status of federation and remote access, from the command line, type the following:</span></span>
    
        Get-CsAccessEdgeConfiguration

3.  <span data-ttu-id="629de-194">Чтобы включить федерацию и удаленный доступ в командной строке введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="629de-194">To enable federation and remote access, from the command line, type the following:</span></span>
    
        Set-CsAccessEdgeConfiguration
    
    <span data-ttu-id="629de-195">Дополнительные сведения об этих командлетах приведены в следующих разделах: [Get – CsAccessEdgeConfiguration](https://technet.microsoft.com/library/gg398574\(v=ocs.15\)) и [Set/CsAccessEdgeConfiguration](https://technet.microsoft.com/library/gg413017\(v=ocs.15\)).</span><span class="sxs-lookup"><span data-stu-id="629de-195">For more information on these cmdlets, see the following topics: [Get-CsAccessEdgeConfiguration](https://technet.microsoft.com/library/gg398574\(v=ocs.15\)) and [Set-CsAccessEdgeConfiguration](https://technet.microsoft.com/library/gg413017\(v=ocs.15\)).</span></span>

4.  <span data-ttu-id="629de-196">Дождитесь завершения репликации, прежде чем переводить пограничные серверы Lync Server 2013 в оперативный режим и протестировать Федерацию и внешний доступ.</span><span class="sxs-lookup"><span data-stu-id="629de-196">Wait until replication has completed before bringing the Lync Server 2013 Edge servers online, and testing federation and external access.</span></span>

## <a name="to-configure-lync-server-2013-edge-server"></a><span data-ttu-id="629de-197">Настройка пограничного сервера Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="629de-197">To configure Lync Server 2013 Edge Server</span></span>

1.  <span data-ttu-id="629de-198">Переведите все пограничные серверы Lync Server 2013 в оперативный режим.</span><span class="sxs-lookup"><span data-stu-id="629de-198">Bring all of the Lync Server 2013 Edge Servers online.</span></span>

2.  <span data-ttu-id="629de-199">Обновите правила маршрутизации внешних брандмауэров или параметры аппаратного балансировщика нагрузки, чтобы отправлять трафик SIP для внешнего доступа (обычно это порт 443) и Федерацию (обычно это порт 5061) на пограничный сервер Lync Server 2013 вместо устаревшего пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="629de-199">Update the external firewall routing rules or the hardware load balancer settings to send SIP traffic for external access (usually port 443) and federation (usually port 5061) to the Lync Server 2013 Edge Server, instead of the legacy Edge Server.</span></span>
    

    > [!NOTE]  
    > <span data-ttu-id="629de-p109">Если у вас нет аппаратной подсистемы балансировки нагрузки, следует обновить запись DNS A для федерации, чтобы разрешить новый пограничный сервер Lync Server. Для этого с минимальным вмешательством уменьшите значение TTL для внешнего полного доменного имени Lync Server Access Edge, чтобы после обновления DNS для указания на новый сервер Lync Server Access Edge федерация и удаленный доступ были быстро обновлены.</span><span class="sxs-lookup"><span data-stu-id="629de-p109">If you do not have a hardware load balancer, you need to update the DNS A record for federation to resolve the new Lync Server Access Edge server. To accomplish this with minimum disruption, reduce the TTL value for the external Lync Server Access Edge FQDN so that when DNS is updated to point to the new Lync Server Access Edge server, federation and remote access will be updated quickly.</span></span>



3.  <span data-ttu-id="629de-202">После этого остановите пограничный сервер **Lync Server** на каждом компьютере пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="629de-202">Next, stop the **Lync Server Access Edge** from each Edge Server computer.</span></span>

4.  <span data-ttu-id="629de-203">На каждом компьютере пограничного сервера пограничного сервера откройте приложение **службы** в **средстве администрирования**.</span><span class="sxs-lookup"><span data-stu-id="629de-203">From each legacy Edge Server computer, open the **Services** applet from the **Administrative Tools**.</span></span>

5.  <span data-ttu-id="629de-204">В списке служб найдите **Office Communications Server Access Edge**.</span><span class="sxs-lookup"><span data-stu-id="629de-204">In the services list, find **Office Communications Server Access Edge**.</span></span>

6.  <span data-ttu-id="629de-205">Щелкните правой кнопкой имя служб, а затем выберите команду **Остановить**, чтобы остановить службу.</span><span class="sxs-lookup"><span data-stu-id="629de-205">Right-click the services name, and then select **Stop** to stop the service.</span></span>

7.  <span data-ttu-id="629de-206">Выберите тип запуска **Отключено**.</span><span class="sxs-lookup"><span data-stu-id="629de-206">Set the Startup type to **Disabled**.</span></span>

8.  <span data-ttu-id="629de-207">Нажмите кнопку **ОК**, чтобы закрыть окно **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="629de-207">Click **OK** to close the **Properties** window.</span></span>

## <a name="to-test-connectivity-of-external-users-and-external-access"></a><span data-ttu-id="629de-208">Проверка возможностей подключения внешних пользователей и внешнего доступа</span><span class="sxs-lookup"><span data-stu-id="629de-208">To Test Connectivity of External Users and External access</span></span>

  - <span data-ttu-id="629de-209">Пользователи, по крайней мере, один федеративный домен, внутренний пользователь Lync Server 2013 и пользователь в Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="629de-209">Users from at least one federated domain, an internal user on Lync Server 2013 and a user on Office Communications Server 2007 R2.</span></span> <span data-ttu-id="629de-210">Проверьте мгновенные сообщения, сведения о присутствии, аудио-видео и совместное использование рабочего стола.</span><span class="sxs-lookup"><span data-stu-id="629de-210">Test instant messaging (IM), presence, audio/video (A/V), and desktop sharing.</span></span>

  - <span data-ttu-id="629de-211">Пользователи каждого общедоступного поставщика услуг обмена мгновенными сообщениями, поддерживаемого организацией (и для которого была выполнена подготовка), взаимодействуют с пользователем Lync Server 2013 и пользователем Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="629de-211">Users of each public IM service provider that your organization supports (and for which provisioning has been completed) communicating with a user on Lync Server 2013 and a user on Office Communications Server 2007 R2.</span></span>

  - <span data-ttu-id="629de-212">Проверьте возможность анонимных пользователей присоединяться к конференциям.</span><span class="sxs-lookup"><span data-stu-id="629de-212">Verify anonymous users are able to join conferences.</span></span>

  - <span data-ttu-id="629de-213">Пользователь, размещенный на сервере Office Communications Server 2007 R2, использующий удаленный доступ пользователей (вход в Office Communications Server 2007 R2 извне интрасети, но без VPN) с пользователем в Lync Server 2013 и пользователь в Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="629de-213">A user hosted on Office Communications Server 2007 R2 using remote user access (logging into Office Communications Server 2007 R2 from outside the intranet but without VPN) with a user on Lync Server 2013, and a user on Office Communications Server 2007 R2.</span></span> <span data-ttu-id="629de-214">Проверьте мгновенные сообщения, сведения о присутствии, аудио-видео и совместное использование рабочего стола.</span><span class="sxs-lookup"><span data-stu-id="629de-214">Test IM, presence, A/V, and desktop sharing.</span></span>

  - <span data-ttu-id="629de-215">Пользователь, размещенный на Lync Server 2013, использующий удаленный доступ пользователей (вход в Lync Server 2013 извне интрасети, но без VPN) с пользователем в Lync Server 2013 и пользователь в Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="629de-215">A user hosted on Lync Server 2013 using remote user access (logging into Lync Server 2013 from outside the intranet but without VPN) with a user on Lync Server 2013, and a user on Office Communications Server 2007 R2.</span></span> <span data-ttu-id="629de-216">Проверьте мгновенные сообщения, сведения о присутствии, аудио-видео и совместное использование рабочего стола.</span><span class="sxs-lookup"><span data-stu-id="629de-216">Test IM, presence, A/V, and desktop sharing.</span></span>

