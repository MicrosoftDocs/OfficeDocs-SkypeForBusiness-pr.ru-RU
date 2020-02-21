---
title: Настройка маршрутов Федерации и трафика мультимедиа
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Configure federation routes and media traffic
ms:assetid: 8b2f5f81-a955-4ad1-ad74-397322ff9521
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688121(v=OCS.15)
ms:contentKeyID: 49733720
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1f5b3e0a775af649b7210dd75dcf90d012f2e421
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42180922"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-federation-routes-and-media-traffic"></a><span data-ttu-id="4e7b3-102">Настройка маршрутов Федерации и трафика мультимедиа</span><span class="sxs-lookup"><span data-stu-id="4e7b3-102">Configure federation routes and media traffic</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4e7b3-103">_**Последнее изменение темы:** 2012-10-15_</span><span class="sxs-lookup"><span data-stu-id="4e7b3-103">_**Topic Last Modified:** 2012-10-15_</span></span>

<span data-ttu-id="4e7b3-104">Федерация — это доверительные отношения между двумя или более SIP-доменами, которые позволяют пользователям в различных организациях обмениваться информацией через сетевые границы.</span><span class="sxs-lookup"><span data-stu-id="4e7b3-104">Federation is a trust relationship between two or more SIP domains that permits users in separate organizations to communicate across network boundaries.</span></span> <span data-ttu-id="4e7b3-105">После миграции в пилотный пул Lync Server 2013 необходимо перейти с маршрута Федерации пограничных серверов Lync Server 2010 на маршрут Федерации на пограничных серверах Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4e7b3-105">After you migrate to your Lync Server 2013 pilot pool, you need to transition from the federation route of your Lync Server 2010 Edge Servers to the federation route of your Lync Server 2013 Edge Servers.</span></span>

<span data-ttu-id="4e7b3-106">Используйте следующие процедуры для переноса маршрута Федерации и маршрута трафика мультимедиа с пограничного сервера Lync Server 2010 и директора на пограничный сервер Lync Server 2013 на пограничный сервер Lync Server для развертывания на едином сайте.</span><span class="sxs-lookup"><span data-stu-id="4e7b3-106">Use the following procedures to transition the federation route and the media traffic route from your Lync Server 2010 Edge Server and Director to your Lync Server 2013 Edge Server, for a single-site deployment.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="4e7b3-107">Для изменения маршрута Федерации и маршрута трафика мультимедиа необходимо запланировать время простоя обслуживания для пограничных серверов Lync Server 2013 и Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="4e7b3-107">Changing the federation route and media traffic route requires that you schedule maintenance downtime for the Lync Server 2013 and Lync Server 2010 Edge Servers.</span></span> <span data-ttu-id="4e7b3-108">Весь процесс перехода также означает, что федеративный доступ будет отключен во время простоя.</span><span class="sxs-lookup"><span data-stu-id="4e7b3-108">This entire transition process also means that federated access will be unavailable for the duration of the outage.</span></span> <span data-ttu-id="4e7b3-109">Следует запланировать простой на период, когда активность пользователей будет минимальной.</span><span class="sxs-lookup"><span data-stu-id="4e7b3-109">You should schedule the downtime for a time when you expect minimal user activity.</span></span> <span data-ttu-id="4e7b3-110">Также следует реализовать своевременное уведомление конечных пользователей.</span><span class="sxs-lookup"><span data-stu-id="4e7b3-110">You should also provide sufficient notification to your end users.</span></span> <span data-ttu-id="4e7b3-111">Тщательно запланируйте простой и задайте соответствующие ожидания в организации.</span><span class="sxs-lookup"><span data-stu-id="4e7b3-111">Plan accordingly for this outage and set appropriate expectations within your organization.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="4e7b3-112">Если устаревший пограничный сервер Lync Server 2010 настроен на использование того же полного доменного имени для пограничной службы доступа, пограничной службы веб-конференций и пограничной службы аудио-и видеоданных, процедуры, описанные в этом разделе, не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="4e7b3-112">If your legacy Lync Server 2010 Edge Server is configured to use the same FQDN for the Access Edge service, Web Conferencing Edge service, and the A/V Edge service, the procedures in this section are not supported.</span></span> <span data-ttu-id="4e7b3-113">Если устаревшие пограничные службы настроены на использование одного полного доменного имени, необходимо сначала перенести всех пользователей из Lync Server 2010 в Lync Server 2013, а затем списать пограничный сервер Lync Server 2010, прежде чем включить федерацию на пограничный сервер Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4e7b3-113">If the legacy Edge services are configured to use the same FQDN, you must first migrate all your users from Lync Server 2010 to Lync Server 2013, then decommission the Lync Server 2010 Edge Server before enabling federation on the Lync Server 2013 Edge Server.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="4e7b3-114">Если Федерация XMPP направляется через пограничный сервер Lync Server 2013, устаревшие Пользователи Lync Server 2010 не смогут общаться с федеративным партнером XMPP до тех пор, пока все пользователи не будут перемещены в Lync Server 2013, политики и сертификаты XMPP настроено, федеративный партнер XMPP настроен на Lync Server 2013, а последние записи DNS были обновлены.</span><span class="sxs-lookup"><span data-stu-id="4e7b3-114">If your XMPP federation is routed through a Lync Server 2013 Edge Server, legacy Lync Server 2010 users will not be able to communicate with the XMPP federated partner until all users have been moved to Lync Server 2013, XMPP policies and certificates have been configured, the XMPP federated partner has been configured on Lync Server 2013, and lastly the DNS entries have been updated.</span></span>



</div>

<div>

## <a name="to-remove-the-legacy-federation-association-from-lync-server-2013-sites"></a><span data-ttu-id="4e7b3-115">Удаление устаревшей связи федерации на сайтах Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4e7b3-115">To remove the legacy federation association from Lync Server 2013 sites</span></span>

1.  <span data-ttu-id="4e7b3-116">На сервере переднего плана Lync Server 2013 откройте существующую топологию в построителе топологий.</span><span class="sxs-lookup"><span data-stu-id="4e7b3-116">On the Lync Server 2013 Front End server, open the existing topology in Topology Builder.</span></span>

2.  <span data-ttu-id="4e7b3-117">В левой области перейдите к узлу сайта, расположенному непосредственно под **Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="4e7b3-117">In the left pane, navigate to the site node, which is located directly below **Lync Server**.</span></span>

3.  <span data-ttu-id="4e7b3-118">Щелкните сайт правой кнопкой мыши и выберите команду **Изменить свойства**.</span><span class="sxs-lookup"><span data-stu-id="4e7b3-118">Right-click the site and then click **Edit Properties**.</span></span>

4.  <span data-ttu-id="4e7b3-119">В левой области, выберите **Федеративный маршрут**.</span><span class="sxs-lookup"><span data-stu-id="4e7b3-119">In the left pane, select **Federation route**.</span></span>

5.  <span data-ttu-id="4e7b3-120">В разделе **назначение федеративного маршрута сайта**снимите флажок **включить SIP-Федерацию** , чтобы отключить маршрутизацию Федерации через устаревшую среду Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="4e7b3-120">Under **Site federation route assignment**, clear the **Enable SIP federation** check box to disable the federation route through the legacy Lync Server 2010 environment.</span></span>
    
    <span data-ttu-id="4e7b3-121">![Диалоговое окно "изменение свойств", страница "маршрут Федерации"](images/JJ688121.8d755ae0-fc7d-4253-b0db-0cf31b863c55(OCS.15).jpg "Диалоговое окно "изменение свойств", страница "маршрут Федерации"")</span><span class="sxs-lookup"><span data-stu-id="4e7b3-121">![Edit Properties dialog, Federation route page](images/JJ688121.8d755ae0-fc7d-4253-b0db-0cf31b863c55(OCS.15).jpg "Edit Properties dialog, Federation route page")</span></span>

6.  <span data-ttu-id="4e7b3-122">Нажмите кнопку **ОК**, чтобы закрыть страницу "Изменение свойств".</span><span class="sxs-lookup"><span data-stu-id="4e7b3-122">Click **OK** to close the Edit Properties page.</span></span>

7.  <span data-ttu-id="4e7b3-123">В **построителе топологии** выберите верхний узел **Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="4e7b3-123">From **Topology Builder**, select the top node **Lync Server**.</span></span>

8.  <span data-ttu-id="4e7b3-124">В меню **Действие** выберите пункт **Опубликовать топологию**.</span><span class="sxs-lookup"><span data-stu-id="4e7b3-124">From the **Action** menu, click **Publish Topology**.</span></span>

9.  <span data-ttu-id="4e7b3-125">Нажмите кнопку **Далее**, чтобы завершить публикацию, и нажмите кнопку **Готово** после завершения процесса публикации.</span><span class="sxs-lookup"><span data-stu-id="4e7b3-125">Click **Next** to complete the publishing process and then click **Finish** when the publishing process has completed.</span></span>

</div>

<div>

## <a name="to-configure-the-legacy-edge-server-as-a-non-federating-edge-server"></a><span data-ttu-id="4e7b3-126">Настройка устаревшего пограничного сервера в качестве пограничного сервера без федерации</span><span class="sxs-lookup"><span data-stu-id="4e7b3-126">To configure the legacy Edge Server as a non-federating Edge Server</span></span>

1.  <span data-ttu-id="4e7b3-127">В левой области перейдите к узлу **Lync Server 2010**, а затем к узлу **Пограничные пулы**.</span><span class="sxs-lookup"><span data-stu-id="4e7b3-127">In the left pane, navigate to the **Lync Server 2010** node and then to the **Edge pools** node.</span></span>

2.  <span data-ttu-id="4e7b3-128">Щелкните правой кнопкой мыши пограничный сервер и выберите в контекстном меню пункт **Изменить свойства**.</span><span class="sxs-lookup"><span data-stu-id="4e7b3-128">Right-click the Edge server, and then click **Edit Properties**.</span></span>

3.  <span data-ttu-id="4e7b3-129">Выберите **Общие** в левой панели.</span><span class="sxs-lookup"><span data-stu-id="4e7b3-129">Select **General** in the left pane.</span></span>

4.  <span data-ttu-id="4e7b3-130">Снимите флажок **Включение федерации для этого пограничного пула (порт 5061)** и нажмите **ОК**, чтобы закрыть страницу.</span><span class="sxs-lookup"><span data-stu-id="4e7b3-130">Clear the **Enable federation for this Edge pool (port 5061)** check box entry and select **OK** to close the page.</span></span>
    
    <span data-ttu-id="4e7b3-131">![Изменение свойств, общие, очистка включение Федерации](images/JJ688121.3be2c8c0-9ed9-4544-bafd-b7694271fafc(OCS.15).jpg "Изменение свойств, общие, очистка включение Федерации")</span><span class="sxs-lookup"><span data-stu-id="4e7b3-131">![Edit Properties, General, clear Enable federation](images/JJ688121.3be2c8c0-9ed9-4544-bafd-b7694271fafc(OCS.15).jpg "Edit Properties, General, clear Enable federation")</span></span>

5.  <span data-ttu-id="4e7b3-132">В меню **Действие** выберите пункт **Публикация топологии**, а затем щелкните **Далее**.</span><span class="sxs-lookup"><span data-stu-id="4e7b3-132">From the **Action** menu, select **Publish Topology**, and then click **Next**.</span></span>

6.  <span data-ttu-id="4e7b3-133">После завершения работы **мастера публикации**, нажмите кнопку **Готово**, чтобы закрыть мастер.</span><span class="sxs-lookup"><span data-stu-id="4e7b3-133">When the **Publishing wizard** completes, click **Finish** to close the wizard.</span></span>

7.  <span data-ttu-id="4e7b3-134">Убедитесь, что федерация для устаревшего пограничного сервера отключена.</span><span class="sxs-lookup"><span data-stu-id="4e7b3-134">Verify federation for the legacy Edge server is disabled.</span></span>
    
    <span data-ttu-id="4e7b3-135">![Построитель топологий, пограничный пул, Федерация отключена](images/JJ688121.a2948438-d51a-4aeb-9eaa-d899ca950758(OCS.15).jpg "Построитель топологий, пограничный пул, Федерация отключена")</span><span class="sxs-lookup"><span data-stu-id="4e7b3-135">![Topology Builder, Edge pool, federation disabled](images/JJ688121.a2948438-d51a-4aeb-9eaa-d899ca950758(OCS.15).jpg "Topology Builder, Edge pool, federation disabled")</span></span>

</div>

<div>

## <a name="to-configure-certificates-on-the-lync-server-2010-edge-server"></a><span data-ttu-id="4e7b3-136">Настройка сертификатов на пограничном сервере Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="4e7b3-136">To configure certificates on the Lync Server 2010 Edge Server</span></span>

1.  <span data-ttu-id="4e7b3-137">Экспортируйте сертификат прокси внешнего доступа с закрытым ключом из устаревшего пограничного сервера Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="4e7b3-137">Export the external Access Proxy certificate, with the private key, from the legacy Lync Server 2010 Edge Server.</span></span>

2.  <span data-ttu-id="4e7b3-138">На пограничном сервере Lync Server 2013 импортируйте внешний сертификат прокси-сервера доступа из предыдущего шага.</span><span class="sxs-lookup"><span data-stu-id="4e7b3-138">On the Lync Server 2013 Edge Server, import the Access Proxy external certificate from the previous step.</span></span>

3.  <span data-ttu-id="4e7b3-139">Назначьте внешний сертификат прокси-сервера доступа внешнему интерфейсу Lync Server 2013 пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="4e7b3-139">Assign the Access Proxy external certificate to the Lync Server 2013 external interface of the Edge Server.</span></span>

4.  <span data-ttu-id="4e7b3-140">Сертификат внутреннего интерфейса пограничного сервера Lync Server 2013 должен быть запрошен доверенным центром сертификации и назначен.</span><span class="sxs-lookup"><span data-stu-id="4e7b3-140">The internal interface certificate of the Lync Server 2013 Edge Server should be requested from a trusted CA and assigned.</span></span>

</div>

<div>

## <a name="to-change-lync-server-2010-federation-route-to-use-lync-server-2013-edge-server"></a><span data-ttu-id="4e7b3-141">Изменение федеративного маршрута Lync Server 2010 для использования пограничного сервера Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4e7b3-141">To change Lync Server 2010 federation route to use Lync Server 2013 Edge Server</span></span>

1.  <span data-ttu-id="4e7b3-142">В левой панели построителя топологий перейдите к узлу **Lync Server 2013**, а затем к узлу **Пограничные пулы**.</span><span class="sxs-lookup"><span data-stu-id="4e7b3-142">From Topology Builder, in the left pane, navigate to the **Lync Server 2013** node and then to the **Edge pools** node.</span></span>

2.  <span data-ttu-id="4e7b3-143">Щелкните правой кнопкой мыши пограничный сервер и выберите в контекстном меню пункт **Изменить свойства**.</span><span class="sxs-lookup"><span data-stu-id="4e7b3-143">Right-click the Edge server, and then click **Edit Properties**.</span></span>

3.  <span data-ttu-id="4e7b3-144">Выберите **Общие** в левой панели.</span><span class="sxs-lookup"><span data-stu-id="4e7b3-144">Select **General** in the left pane.</span></span>

4.  <span data-ttu-id="4e7b3-145">Установите флажок **Включение федерации для этого пограничного пула (порт 5061)** и нажмите **ОК**, чтобы закрыть страницу.</span><span class="sxs-lookup"><span data-stu-id="4e7b3-145">Select the check box entry for **Enable federation for this Edge pool (port 5061)** and then click **OK** to close the page.</span></span>
    
    <span data-ttu-id="4e7b3-146">![Диалоговое окно "изменение свойств", страница "Общие"](images/JJ688121.cc79a88c-cce4-4cab-80ad-4f70325dc7c4(OCS.15).jpg "Диалоговое окно "изменение свойств", страница "Общие"")</span><span class="sxs-lookup"><span data-stu-id="4e7b3-146">![Edit Properties dialog, General page](images/JJ688121.cc79a88c-cce4-4cab-80ad-4f70325dc7c4(OCS.15).jpg "Edit Properties dialog, General page")</span></span>

5.  <span data-ttu-id="4e7b3-147">В меню **Действие** выберите пункт **Публикация топологии**, а затем щелкните **Далее**.</span><span class="sxs-lookup"><span data-stu-id="4e7b3-147">From the **Action** menu, select **Publish Topology**, and then click **Next**.</span></span>

6.  <span data-ttu-id="4e7b3-148">После завершения работы **мастера публикации**, нажмите кнопку **Готово**, чтобы закрыть мастер.</span><span class="sxs-lookup"><span data-stu-id="4e7b3-148">When the **Publishing wizard** completes, click **Finish** to close the wizard.</span></span>

7.  <span data-ttu-id="4e7b3-149">Убедитесь, что для параметра **Федерация (порт 5061)** задано значение **Включено**.</span><span class="sxs-lookup"><span data-stu-id="4e7b3-149">Verify **Federation (port 5061)** is set to **Enabled**.</span></span>
    
    <span data-ttu-id="4e7b3-150">![Построитель топологий, пограничный пул, Федерация включен](images/JJ688121.e8ccdada-23f4-47e5-a99d-5bf795fefc48(OCS.15).jpg "Построитель топологий, пограничный пул, Федерация включен")</span><span class="sxs-lookup"><span data-stu-id="4e7b3-150">![Topology Builder, Edge pool, Federation enabled](images/JJ688121.e8ccdada-23f4-47e5-a99d-5bf795fefc48(OCS.15).jpg "Topology Builder, Edge pool, Federation enabled")</span></span>

</div>

<div>

## <a name="to-update-lync-server-2013-edge-server-federation-next-hop"></a><span data-ttu-id="4e7b3-151">Обновление узла следующего перехода федерации пограничного сервера Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4e7b3-151">To update Lync Server 2013 Edge Server federation next hop</span></span>

1.  <span data-ttu-id="4e7b3-152">В левой панели построителя топологий перейдите к узлу **Lync Server 2013**, а затем к узлу **Пограничные пулы**.</span><span class="sxs-lookup"><span data-stu-id="4e7b3-152">From Topology Builder, in the left pane, navigate to the **Lync Server 2013** node and then to the **Edge pools** node.</span></span>

2.  <span data-ttu-id="4e7b3-153">Разверните узел, щелкните правой кнопкой указанный пограничный сервер и выберите команду **Изменить свойства**.</span><span class="sxs-lookup"><span data-stu-id="4e7b3-153">Expand the node, right-click the Edge Server listed, and then click **Edit Properties**.</span></span>

3.  <span data-ttu-id="4e7b3-154">На странице **Общие** в разделе **Выбор следующего прыжка**выберите в раскрывающемся списке пул Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4e7b3-154">On the **General** page, under **Next hop selection**, select from the drop-down list the Lync Server 2013  pool.</span></span>
    
    <span data-ttu-id="4e7b3-155">![Диалоговое окно "изменение свойств", страница следующего прыжка](images/JJ688121.5741b9a8-e729-4457-9f62-38f08a2c5b02(OCS.15).jpg "Диалоговое окно "изменение свойств", страница следующего прыжка")</span><span class="sxs-lookup"><span data-stu-id="4e7b3-155">![Edit Properties dialog, Next hop page](images/JJ688121.5741b9a8-e729-4457-9f62-38f08a2c5b02(OCS.15).jpg "Edit Properties dialog, Next hop page")</span></span>

4.  <span data-ttu-id="4e7b3-156">Нажмите кнопку **ОК**, чтобы закрыть страницу "Изменение свойств".</span><span class="sxs-lookup"><span data-stu-id="4e7b3-156">Click **OK** to close the Edit Properties page.</span></span>

5.  <span data-ttu-id="4e7b3-157">В **построителе топологий**выберите верхний узел **Lync Server** .</span><span class="sxs-lookup"><span data-stu-id="4e7b3-157">From **Topology Builder**, select the top node **Lync Server** .</span></span>

6.  <span data-ttu-id="4e7b3-158">В меню **Действие** выберите команду **Опубликовать топологию** и завершите работу мастера.</span><span class="sxs-lookup"><span data-stu-id="4e7b3-158">From the **Action** menu, click **Publish Topology** and complete the wizard.</span></span>

</div>

<div>

## <a name="to-configure-lync-server-2013-edge-server-outbound-media-path"></a><span data-ttu-id="4e7b3-159">Настройка исходящего пути к мультимедиа пограничного сервера Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4e7b3-159">To configure Lync Server 2013 Edge Server outbound media path</span></span>

1.  <span data-ttu-id="4e7b3-160">На левой панели построителя топологий перейдите к узлу **Lync Server 2013** , а затем к пулу под **серверами переднего плана Standard Edition** или **интерфейсным пулам Enterprise Edition**.</span><span class="sxs-lookup"><span data-stu-id="4e7b3-160">From Topology Builder, in the left pane, navigate to the **Lync Server 2013** node and then to the pool below **Standard Edition Front End Servers** or **Enterprise Edition Front End pools**.</span></span>

2.  <span data-ttu-id="4e7b3-161">Щелкните пул правой кнопкой мыши и выберите команду **Изменить свойства**.</span><span class="sxs-lookup"><span data-stu-id="4e7b3-161">Right-click the pool, and then click **Edit Properties**.</span></span>

3.  <span data-ttu-id="4e7b3-162">В разделе **Связи** установите флажок **Связать пограничный пул (для компонентов мультимедиа)**.</span><span class="sxs-lookup"><span data-stu-id="4e7b3-162">In the **Associations** section, select the **Associate Edge pool (for media components)** check box.</span></span>
    
    <span data-ttu-id="4e7b3-163">![Изменение свойств, общие, сопоставление пограничного пула](images/JJ688121.fd9b18ca-fda2-4764-9bf0-726bf39f6a12(OCS.15).jpg "Изменение свойств, общие, сопоставление пограничного пула")</span><span class="sxs-lookup"><span data-stu-id="4e7b3-163">![Edit Properties, General, Associate Edge pool](images/JJ688121.fd9b18ca-fda2-4764-9bf0-726bf39f6a12(OCS.15).jpg "Edit Properties, General, Associate Edge pool")</span></span>

4.  <span data-ttu-id="4e7b3-164">В раскрывающемся списке выберите Lync Server 2013 Edge Server.</span><span class="sxs-lookup"><span data-stu-id="4e7b3-164">From the drop down box, select the Lync Server 2013 Edge Server.</span></span>

5.  <span data-ttu-id="4e7b3-165">Нажмите кнопку **ОК**, чтобы закрыть страницу **изменения свойств**.</span><span class="sxs-lookup"><span data-stu-id="4e7b3-165">Click **OK** to close the **Edit Properties** page.</span></span>

</div>

<div>

## <a name="to-turn-on-lync-server-2013-edge-server-federation"></a><span data-ttu-id="4e7b3-166">Включение федерации пограничного сервера Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4e7b3-166">To turn on Lync Server 2013 Edge Server federation</span></span>

1.  <span data-ttu-id="4e7b3-167">В левой панели построителя топологий перейдите к узлу **Lync Server 2013**, а затем к узлу **Пограничные пулы**.</span><span class="sxs-lookup"><span data-stu-id="4e7b3-167">From Topology Builder, in the left pane, navigate to the **Lync Server 2013** node and then to the **Edge pools** node.</span></span>

2.  <span data-ttu-id="4e7b3-168">Разверните узел, щелкните правой кнопкой указанный пограничный сервер и выберите команду **Изменить свойства**.</span><span class="sxs-lookup"><span data-stu-id="4e7b3-168">Expand the node, right-click the Edge Server listed, and then click **Edit Properties**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="4e7b3-169">Федерация можно включить только для одного пограничного пула.</span><span class="sxs-lookup"><span data-stu-id="4e7b3-169">Federation can only be enabled for a single Edge pool.</span></span> <span data-ttu-id="4e7b3-170">Если у вас несколько пограничных пулов, выберите один из них, который будет использоваться в качестве Федерации пограничного пула.</span><span class="sxs-lookup"><span data-stu-id="4e7b3-170">If you have multiple Edge pools, select one to use as the federating Edge pool.</span></span>

    
    </div>

3.  <span data-ttu-id="4e7b3-171">На странице **Общие** убедитесь, что флажок **Включение федерации для этого пограничного пула (порт 5061)** установлен.</span><span class="sxs-lookup"><span data-stu-id="4e7b3-171">On the **General** page, verify the **Enable federation for this Edge pool (Port 5061)** setting is checked.</span></span>
    
    <span data-ttu-id="4e7b3-172">![Диалоговое окно "изменение свойств", страница "Общие"](images/JJ688121.cc79a88c-cce4-4cab-80ad-4f70325dc7c4(OCS.15).jpg "Диалоговое окно "изменение свойств", страница "Общие"")</span><span class="sxs-lookup"><span data-stu-id="4e7b3-172">![Edit Properties dialog, General page](images/JJ688121.cc79a88c-cce4-4cab-80ad-4f70325dc7c4(OCS.15).jpg "Edit Properties dialog, General page")</span></span>

4.  <span data-ttu-id="4e7b3-173">Нажмите кнопку **ОК**, чтобы закрыть страницу "Изменение свойств".</span><span class="sxs-lookup"><span data-stu-id="4e7b3-173">Click **OK** to close the Edit Properties page.</span></span>

5.  <span data-ttu-id="4e7b3-174">Затем перейдите к узлу сайта.</span><span class="sxs-lookup"><span data-stu-id="4e7b3-174">Next, navigate to the site node.</span></span>

6.  <span data-ttu-id="4e7b3-175">Щелкните сайт правой кнопкой мыши и выберите команду **Изменить свойства**.</span><span class="sxs-lookup"><span data-stu-id="4e7b3-175">Right-click the site, and then click **Edit Properties**.</span></span>

7.  <span data-ttu-id="4e7b3-176">В левой области, выберите **Федеративный маршрут**.</span><span class="sxs-lookup"><span data-stu-id="4e7b3-176">In the left pane, click **Federation route**.</span></span>

8.  <span data-ttu-id="4e7b3-177">В разделе **назначение федеративного маршрута сайта**выберите **включить федерацию SIP**, а затем выберите в списке пункт Пограничный сервер Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4e7b3-177">Under **Site federation route assignment**, select **Enable SIP federation**, and then from the list select the Lync Server 2013 Edge Server listed.</span></span>
    
    <span data-ttu-id="4e7b3-178">![Страница "изменить свойства", "маршрут Федерации"](images/JJ688121.c50c13b8-0859-4e3e-8793-45c431a5b4b5(OCS.15).jpg "Страница "изменить свойства", "маршрут Федерации"")</span><span class="sxs-lookup"><span data-stu-id="4e7b3-178">![Edit Properties, Federation route page](images/JJ688121.c50c13b8-0859-4e3e-8793-45c431a5b4b5(OCS.15).jpg "Edit Properties, Federation route page")</span></span>

9.  <span data-ttu-id="4e7b3-179">Нажмите кнопку **ОК**, чтобы закрыть страницу **Изменение свойств**.</span><span class="sxs-lookup"><span data-stu-id="4e7b3-179">Click **OK** to close the **Edit Properties** page.</span></span>
    
    <span data-ttu-id="4e7b3-180">В случае развертывании с несколькими сайтами выполните эту процедуру на каждом сайте.</span><span class="sxs-lookup"><span data-stu-id="4e7b3-180">For multi-site deployments, complete this procedure at each site.</span></span>

</div>

<div>

## <a name="to-publish-edge-server-configuration-changes"></a><span data-ttu-id="4e7b3-181">Публикация изменений конфигурации пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="4e7b3-181">To publish Edge Server configuration changes</span></span>

1.  <span data-ttu-id="4e7b3-182">В **построителе топологий**выберите верхний узел **Lync Server** .</span><span class="sxs-lookup"><span data-stu-id="4e7b3-182">From **Topology Builder**, select the top node **Lync Server** .</span></span>

2.  <span data-ttu-id="4e7b3-183">В меню **Действие** выберите команду **Опубликовать топологию** и завершите работу мастера.</span><span class="sxs-lookup"><span data-stu-id="4e7b3-183">From the **Action** menu, select **Publish Topology** and complete the wizard.</span></span>

3.  <span data-ttu-id="4e7b3-184">Дождитесь выполнения репликации Active Directory во всех пулах в развертывании.</span><span class="sxs-lookup"><span data-stu-id="4e7b3-184">Wait for Active Directory replication to occur to all pools in the deployment.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="4e7b3-185">Может появиться следующее сообщение:</span><span class="sxs-lookup"><span data-stu-id="4e7b3-185">You may see the following message:</span></span><BR><span data-ttu-id="4e7b3-186"><STRONG>Предупреждение. Топология содержит несколько федеративных пограничных серверов. Это может произойти в процессе перехода на новую версию продукта. В таком случае только один пограничный сервер будет активно использоваться для федерации. Убедитесь, что внешняя SRV-запись DNS указывает на правильный пограничный сервер. Если требуется развернуть несколько одновременно активных пограничных серверов федерации (то есть, это не сценарий миграции), убедитесь, что все федеративные партнеры используют Lync Server. Убедитесь, что во внешней SRV-записи DNS перечислены все пограничные серверы с поддержкой федерации.</STRONG></span><span class="sxs-lookup"><span data-stu-id="4e7b3-186"><STRONG>Warning: The topology contains more than one Federated Edge Server. This can occur during migration to a more recent version of the product. In that case, only one Edge Server would be actively used for federation. Verify that the external DNS SRV record points to the correct Edge Server. If you want to deploy multiple federation Edge Server to be active concurrently (that is, not a migration scenario), verify that all federated partners are using Lync Server. Verify that the external DNS SRV record lists all federation enabled Edge Servers.</STRONG></span></span><BR><span data-ttu-id="4e7b3-187">Появление этого предупреждения ожидаемое и его можно спокойно проигнорировать.</span><span class="sxs-lookup"><span data-stu-id="4e7b3-187">This warning is expected and can be safely ignored.</span></span>

    
    </div>

</div>

<div>

## <a name="to-configure-lync-server-2013-edge-server"></a><span data-ttu-id="4e7b3-188">Настройка пограничного сервера Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4e7b3-188">To configure Lync Server 2013 Edge Server</span></span>

1.  <span data-ttu-id="4e7b3-189">Переведите все пограничные серверы Lync Server 2013 в оперативный режим.</span><span class="sxs-lookup"><span data-stu-id="4e7b3-189">Bring all of the Lync Server 2013 Edge Servers online.</span></span>

2.  <span data-ttu-id="4e7b3-190">Обновите правила маршрутизации внешних брандмауэров или параметры аппаратного балансировщика нагрузки, чтобы отправлять трафик SIP для внешнего доступа (обычно это порт 443) и Федерацию (обычно это порт 5061) на пограничный сервер Lync Server 2013 вместо устаревшего пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="4e7b3-190">Update the external firewall routing rules or the hardware load balancer settings to send SIP traffic for external access (usually port 443) and federation (usually port 5061) to the Lync Server 2013 Edge Server, instead of the legacy Edge Server.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="4e7b3-p105">Если у вас нет аппаратной подсистемы балансировки нагрузки, следует обновить запись DNS A для федерации, чтобы разрешить новый пограничный сервер Lync Server. Для этого с минимальным вмешательством уменьшите значение TTL для внешнего полного доменного имени Lync Server Access Edge, чтобы после обновления DNS для указания на новый сервер Lync Server Access Edge федерация и удаленный доступ были быстро обновлены.</span><span class="sxs-lookup"><span data-stu-id="4e7b3-p105">If you do not have a hardware load balancer, you need to update the DNS A record for federation to resolve to the new Lync Server Access Edge server. To accomplish this with minimum disruption, reduce the TLL value for the external Lync Server Access Edge FQDN so that when DNS is updated to point to the new Lync Server Access Edge, federation and remote access will be updated quickly.</span></span>

    
    </div>

3.  <span data-ttu-id="4e7b3-193">После этого остановите пограничный сервер **Lync Server** на каждом компьютере пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="4e7b3-193">Next, stop the **Lync Server Access Edge** from each Edge Server computer.</span></span>

4.  <span data-ttu-id="4e7b3-194">На каждом компьютере пограничного сервера пограничного сервера откройте приложение **службы** в **средстве администрирования**.</span><span class="sxs-lookup"><span data-stu-id="4e7b3-194">From each legacy Edge Server computer, open the **Services** applet from the **Administrative Tools**.</span></span>

5.  <span data-ttu-id="4e7b3-195">В списке служб найдите **Lync Server Access Edge**.</span><span class="sxs-lookup"><span data-stu-id="4e7b3-195">In the services list, find **Lync Server Access Edge**.</span></span>

6.  <span data-ttu-id="4e7b3-196">Щелкните правой кнопкой имя служб, а затем выберите команду **Остановить**, чтобы остановить службу.</span><span class="sxs-lookup"><span data-stu-id="4e7b3-196">Right-click the services name, and then select **Stop** to stop the service.</span></span>

7.  <span data-ttu-id="4e7b3-197">Выберите тип запуска **Отключено**.</span><span class="sxs-lookup"><span data-stu-id="4e7b3-197">Set the Startup type to **Disabled**.</span></span>

8.  <span data-ttu-id="4e7b3-198">Нажмите кнопку **ОК**, чтобы закрыть окно **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="4e7b3-198">Click **OK** to close the **Properties** window.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

