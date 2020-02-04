---
title: Настройка маршрутов федерации и трафика мультимедиа
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
ms.openlocfilehash: 9cd9cf1c7c61261e4e1a6974498f9f9dff980169
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723249"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-federation-routes-and-media-traffic"></a><span data-ttu-id="ca7be-102">Настройка маршрутов федерации и трафика мультимедиа</span><span class="sxs-lookup"><span data-stu-id="ca7be-102">Configure federation routes and media traffic</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ca7be-103">_**Тема последнего изменения:** 2012-10-15_</span><span class="sxs-lookup"><span data-stu-id="ca7be-103">_**Topic Last Modified:** 2012-10-15_</span></span>

<span data-ttu-id="ca7be-104">Федерация — это отношение доверия между двумя или более доменами SIP, позволяющее пользователям в разных организациях взаимодействовать через границы сети.</span><span class="sxs-lookup"><span data-stu-id="ca7be-104">Federation is a trust relationship between two or more SIP domains that permits users in separate organizations to communicate across network boundaries.</span></span> <span data-ttu-id="ca7be-105">После перехода на сервер пилотного пула Lync Server 2013 вы должны перейти с маршрута Федерации сервера Lync Server 2010 пограничного сервера на маршрут Федерации сервера Lync Server 2013 пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="ca7be-105">After you migrate to your Lync Server 2013 pilot pool, you need to transition from the federation route of your Lync Server 2010 Edge Servers to the federation route of your Lync Server 2013 Edge Servers.</span></span>

<span data-ttu-id="ca7be-106">Выполните указанные ниже действия, чтобы перенести маршрут Федерации и трафик мультимедиа с сервера Lync Server 2010 и режиссера на сервер Lync Server 2013 Edge для развертывания на одном сайте.</span><span class="sxs-lookup"><span data-stu-id="ca7be-106">Use the following procedures to transition the federation route and the media traffic route from your Lync Server 2010 Edge Server and Director to your Lync Server 2013 Edge Server, for a single-site deployment.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="ca7be-107">Для изменения маршрута Федерации и маршрутизации трафика мультимедиа требуется запланировать время бездействия на обслуживание для серверов Lync Server 2013 и Lync Server 2010 Edge.</span><span class="sxs-lookup"><span data-stu-id="ca7be-107">Changing the federation route and media traffic route requires that you schedule maintenance downtime for the Lync Server 2013 and Lync Server 2010 Edge Servers.</span></span> <span data-ttu-id="ca7be-108">Весь процесс перехода также означает, что федеративное Access будет недоступен в течение сбоя.</span><span class="sxs-lookup"><span data-stu-id="ca7be-108">This entire transition process also means that federated access will be unavailable for the duration of the outage.</span></span> <span data-ttu-id="ca7be-109">Вы должны планировать время простоя, когда ожидается минимальная активность пользователей.</span><span class="sxs-lookup"><span data-stu-id="ca7be-109">You should schedule the downtime for a time when you expect minimal user activity.</span></span> <span data-ttu-id="ca7be-110">Кроме того, вы должны предоставить вам достаточное уведомление для конечных пользователей.</span><span class="sxs-lookup"><span data-stu-id="ca7be-110">You should also provide sufficient notification to your end users.</span></span> <span data-ttu-id="ca7be-111">Спланируйте этот сбой и настройте соответствующие ожидания в Организации.</span><span class="sxs-lookup"><span data-stu-id="ca7be-111">Plan accordingly for this outage and set appropriate expectations within your organization.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="ca7be-112">Если ваш традиционный сервер Lync Server 2010 настроен на использование того же полного доменного имени для службы пограничного доступа, службы Edge для веб-конференций и службы EDGE, то процедуры в этом разделе не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="ca7be-112">If your legacy Lync Server 2010 Edge Server is configured to use the same FQDN for the Access Edge service, Web Conferencing Edge service, and the A/V Edge service, the procedures in this section are not supported.</span></span> <span data-ttu-id="ca7be-113">Если стандартные службы Edge настроены на использование одного полного доменного имени, необходимо сначала перенести всех пользователей из Lync Server 2010 в Lync Server 2013, а затем списать сервер Lync Server 2010 Edge Server перед включением Федерации на пограничном сервере Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ca7be-113">If the legacy Edge services are configured to use the same FQDN, you must first migrate all your users from Lync Server 2010 to Lync Server 2013, then decommission the Lync Server 2010 Edge Server before enabling federation on the Lync Server 2013 Edge Server.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="ca7be-114">Если КСМПП Федерация направляется через граничный сервер Lync Server 2013, пользователи из устаревшего сервера Lync Server 2010 не смогут взаимодействовать с федеративными партнерами КСМПП, пока все пользователи не будут перенесены на Lync Server 2013, КСМПП политики и сертификаты будут на Lync Server 2013 была настроена служба федеративного партнера КСМПП и последние записи DNS были обновлены.</span><span class="sxs-lookup"><span data-stu-id="ca7be-114">If your XMPP federation is routed through a Lync Server 2013 Edge Server, legacy Lync Server 2010 users will not be able to communicate with the XMPP federated partner until all users have been moved to Lync Server 2013, XMPP policies and certificates have been configured, the XMPP federated partner has been configured on Lync Server 2013, and lastly the DNS entries have been updated.</span></span>



</div>

<div>

## <a name="to-remove-the-legacy-federation-association-from-lync-server-2013-sites"></a><span data-ttu-id="ca7be-115">Удаление устаревшей связи Федерации с сайтов Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ca7be-115">To remove the legacy federation association from Lync Server 2013 sites</span></span>

1.  <span data-ttu-id="ca7be-116">На сервере переднего плана Lync Server 2013 откройте существующую топологию в построителе топологии.</span><span class="sxs-lookup"><span data-stu-id="ca7be-116">On the Lync Server 2013 Front End server, open the existing topology in Topology Builder.</span></span>

2.  <span data-ttu-id="ca7be-117">На левой панели перейдите к узлу сайта, расположенному непосредственно под пунктом **Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="ca7be-117">In the left pane, navigate to the site node, which is located directly below **Lync Server**.</span></span>

3.  <span data-ttu-id="ca7be-118">Щелкните сайт правой кнопкой мыши и выберите команду **изменить свойства**.</span><span class="sxs-lookup"><span data-stu-id="ca7be-118">Right-click the site and then click **Edit Properties**.</span></span>

4.  <span data-ttu-id="ca7be-119">На левой панели выберите **маршрут Федерации**.</span><span class="sxs-lookup"><span data-stu-id="ca7be-119">In the left pane, select **Federation route**.</span></span>

5.  <span data-ttu-id="ca7be-120">В разделе **назначение маршрутов Федерации сайтов**снимите флажок **включить федерацию SIP** , чтобы отключить маршрут Федерации в устаревшей среде Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="ca7be-120">Under **Site federation route assignment**, clear the **Enable SIP federation** check box to disable the federation route through the legacy Lync Server 2010 environment.</span></span>
    
    <span data-ttu-id="ca7be-121">![Диалоговое окно "изменение свойств", страница "маршрут Федерации"](images/JJ688121.8d755ae0-fc7d-4253-b0db-0cf31b863c55(OCS.15).jpg "Диалоговое окно "изменение свойств", страница "маршрут Федерации"")</span><span class="sxs-lookup"><span data-stu-id="ca7be-121">![Edit Properties dialog, Federation route page](images/JJ688121.8d755ae0-fc7d-4253-b0db-0cf31b863c55(OCS.15).jpg "Edit Properties dialog, Federation route page")</span></span>

6.  <span data-ttu-id="ca7be-122">Нажмите кнопку **ОК** , чтобы закрыть страницу Изменение свойств.</span><span class="sxs-lookup"><span data-stu-id="ca7be-122">Click **OK** to close the Edit Properties page.</span></span>

7.  <span data-ttu-id="ca7be-123">В **построителе топологии**выберите верхний узел **Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="ca7be-123">From **Topology Builder**, select the top node **Lync Server**.</span></span>

8.  <span data-ttu-id="ca7be-124">В меню **действия** выберите пункт **топология публикации**.</span><span class="sxs-lookup"><span data-stu-id="ca7be-124">From the **Action** menu, click **Publish Topology**.</span></span>

9.  <span data-ttu-id="ca7be-125">Нажмите кнопку **Далее** , чтобы завершить процесс публикации, а затем нажмите кнопку **Готово** после завершения процесса публикации.</span><span class="sxs-lookup"><span data-stu-id="ca7be-125">Click **Next** to complete the publishing process and then click **Finish** when the publishing process has completed.</span></span>

</div>

<div>

## <a name="to-configure-the-legacy-edge-server-as-a-non-federating-edge-server"></a><span data-ttu-id="ca7be-126">Настройка устаревшего пограничного сервера в качестве пограничного сервера без поддержки Федерации</span><span class="sxs-lookup"><span data-stu-id="ca7be-126">To configure the legacy Edge Server as a non-federating Edge Server</span></span>

1.  <span data-ttu-id="ca7be-127">В левой области перейдите на узел **Lync Server 2010** , а затем в узел **Пулы Edge** .</span><span class="sxs-lookup"><span data-stu-id="ca7be-127">In the left pane, navigate to the **Lync Server 2010** node and then to the **Edge pools** node.</span></span>

2.  <span data-ttu-id="ca7be-128">Щелкните правой кнопкой мыши пограничный сервер и выберите команду **изменить свойства**.</span><span class="sxs-lookup"><span data-stu-id="ca7be-128">Right-click the Edge server, and then click **Edit Properties**.</span></span>

3.  <span data-ttu-id="ca7be-129">На левой панели выберите **Общие** .</span><span class="sxs-lookup"><span data-stu-id="ca7be-129">Select **General** in the left pane.</span></span>

4.  <span data-ttu-id="ca7be-130">Снимите флажок **включить федерацию для этого пограничного пула (порт 5061)** и нажмите кнопку **ОК** , чтобы закрыть страницу.</span><span class="sxs-lookup"><span data-stu-id="ca7be-130">Clear the **Enable federation for this Edge pool (port 5061)** check box entry and select **OK** to close the page.</span></span>
    
    <span data-ttu-id="ca7be-131">![Изменение свойств, общее, Clear включить федерацию](images/JJ688121.3be2c8c0-9ed9-4544-bafd-b7694271fafc(OCS.15).jpg "Изменение свойств, общее, Clear включить федерацию")</span><span class="sxs-lookup"><span data-stu-id="ca7be-131">![Edit Properties, General, clear Enable federation](images/JJ688121.3be2c8c0-9ed9-4544-bafd-b7694271fafc(OCS.15).jpg "Edit Properties, General, clear Enable federation")</span></span>

5.  <span data-ttu-id="ca7be-132">В меню **действие** выберите пункт **топология публикации**и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="ca7be-132">From the **Action** menu, select **Publish Topology**, and then click **Next**.</span></span>

6.  <span data-ttu-id="ca7be-133">После завершения работы **мастера публикации** нажмите кнопку **Готово** , чтобы закрыть окно мастера.</span><span class="sxs-lookup"><span data-stu-id="ca7be-133">When the **Publishing wizard** completes, click **Finish** to close the wizard.</span></span>

7.  <span data-ttu-id="ca7be-134">Убедитесь, что отключена Федерация для устаревшего пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="ca7be-134">Verify federation for the legacy Edge server is disabled.</span></span>
    
    <span data-ttu-id="ca7be-135">![Построитель топологии, граничный пул, Федерация отключена](images/JJ688121.a2948438-d51a-4aeb-9eaa-d899ca950758(OCS.15).jpg "Построитель топологии, граничный пул, Федерация отключена")</span><span class="sxs-lookup"><span data-stu-id="ca7be-135">![Topology Builder, Edge pool, federation disabled](images/JJ688121.a2948438-d51a-4aeb-9eaa-d899ca950758(OCS.15).jpg "Topology Builder, Edge pool, federation disabled")</span></span>

</div>

<div>

## <a name="to-configure-certificates-on-the-lync-server-2010-edge-server"></a><span data-ttu-id="ca7be-136">Настройка сертификатов на пограничном сервере Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="ca7be-136">To configure certificates on the Lync Server 2010 Edge Server</span></span>

1.  <span data-ttu-id="ca7be-137">Экспортируйте сертификат прокси внешнего доступа с закрытым ключом с старого сервера Lync Server 2010 Edge.</span><span class="sxs-lookup"><span data-stu-id="ca7be-137">Export the external Access Proxy certificate, with the private key, from the legacy Lync Server 2010 Edge Server.</span></span>

2.  <span data-ttu-id="ca7be-138">На пограничном сервере Lync Server 2013 импортируйте внешний сертификат прокси-сервера доступа на предыдущем этапе.</span><span class="sxs-lookup"><span data-stu-id="ca7be-138">On the Lync Server 2013 Edge Server, import the Access Proxy external certificate from the previous step.</span></span>

3.  <span data-ttu-id="ca7be-139">Назначьте внешний интерфейс для доступа к внешним данным прокси-сервера для Lync Server 2013 внешний сервер пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="ca7be-139">Assign the Access Proxy external certificate to the Lync Server 2013 external interface of the Edge Server.</span></span>

4.  <span data-ttu-id="ca7be-140">Сертификат внутреннего интерфейса сервера Lync Server 2013 Edge должен быть указан в доверенном центре сертификации и назначен.</span><span class="sxs-lookup"><span data-stu-id="ca7be-140">The internal interface certificate of the Lync Server 2013 Edge Server should be requested from a trusted CA and assigned.</span></span>

</div>

<div>

## <a name="to-change-lync-server-2010-federation-route-to-use-lync-server-2013-edge-server"></a><span data-ttu-id="ca7be-141">Изменение маршрута Федерации Lync Server 2010 на использование сервера Lync Server 2013 Edge Server</span><span class="sxs-lookup"><span data-stu-id="ca7be-141">To change Lync Server 2010 federation route to use Lync Server 2013 Edge Server</span></span>

1.  <span data-ttu-id="ca7be-142">Из построителя топологии в левой области перейдите на узел **Lync Server 2013** , а затем в узел **Пулы Edge** .</span><span class="sxs-lookup"><span data-stu-id="ca7be-142">From Topology Builder, in the left pane, navigate to the **Lync Server 2013** node and then to the **Edge pools** node.</span></span>

2.  <span data-ttu-id="ca7be-143">Щелкните правой кнопкой мыши пограничный сервер и выберите команду **изменить свойства**.</span><span class="sxs-lookup"><span data-stu-id="ca7be-143">Right-click the Edge server, and then click **Edit Properties**.</span></span>

3.  <span data-ttu-id="ca7be-144">На левой панели выберите **Общие** .</span><span class="sxs-lookup"><span data-stu-id="ca7be-144">Select **General** in the left pane.</span></span>

4.  <span data-ttu-id="ca7be-145">Установите флажок **включить федерацию для этого пограничного пула (порт 5061)** и нажмите кнопку **ОК** , чтобы закрыть страницу.</span><span class="sxs-lookup"><span data-stu-id="ca7be-145">Select the check box entry for **Enable federation for this Edge pool (port 5061)** and then click **OK** to close the page.</span></span>
    
    <span data-ttu-id="ca7be-146">![Диалоговое окно "изменение свойств", страница "Общие"](images/JJ688121.cc79a88c-cce4-4cab-80ad-4f70325dc7c4(OCS.15).jpg "Диалоговое окно "изменение свойств", страница "Общие"")</span><span class="sxs-lookup"><span data-stu-id="ca7be-146">![Edit Properties dialog, General page](images/JJ688121.cc79a88c-cce4-4cab-80ad-4f70325dc7c4(OCS.15).jpg "Edit Properties dialog, General page")</span></span>

5.  <span data-ttu-id="ca7be-147">В меню **действие** выберите пункт **топология публикации**и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="ca7be-147">From the **Action** menu, select **Publish Topology**, and then click **Next**.</span></span>

6.  <span data-ttu-id="ca7be-148">После завершения работы **мастера публикации** нажмите кнопку **Готово** , чтобы закрыть окно мастера.</span><span class="sxs-lookup"><span data-stu-id="ca7be-148">When the **Publishing wizard** completes, click **Finish** to close the wizard.</span></span>

7.  <span data-ttu-id="ca7be-149">Убедитесь в том, что для **Федерации (порт 5061)** задано значение **Enabled (включено**).</span><span class="sxs-lookup"><span data-stu-id="ca7be-149">Verify **Federation (port 5061)** is set to **Enabled**.</span></span>
    
    <span data-ttu-id="ca7be-150">![Построитель топологии, пограничный пул, включена Федерация](images/JJ688121.e8ccdada-23f4-47e5-a99d-5bf795fefc48(OCS.15).jpg "Построитель топологии, пограничный пул, включена Федерация")</span><span class="sxs-lookup"><span data-stu-id="ca7be-150">![Topology Builder, Edge pool, Federation enabled](images/JJ688121.e8ccdada-23f4-47e5-a99d-5bf795fefc48(OCS.15).jpg "Topology Builder, Edge pool, Federation enabled")</span></span>

</div>

<div>

## <a name="to-update-lync-server-2013-edge-server-federation-next-hop"></a><span data-ttu-id="ca7be-151">Обновление следующего прыжка для интеграции Lync Server 2013 Edge Server</span><span class="sxs-lookup"><span data-stu-id="ca7be-151">To update Lync Server 2013 Edge Server federation next hop</span></span>

1.  <span data-ttu-id="ca7be-152">Из построителя топологии в левой области перейдите на узел **Lync Server 2013** , а затем в узел **Пулы Edge** .</span><span class="sxs-lookup"><span data-stu-id="ca7be-152">From Topology Builder, in the left pane, navigate to the **Lync Server 2013** node and then to the **Edge pools** node.</span></span>

2.  <span data-ttu-id="ca7be-153">Разверните узел, щелкните правой кнопкой мыши пограничный сервер в списке и выберите команду **изменить свойства**.</span><span class="sxs-lookup"><span data-stu-id="ca7be-153">Expand the node, right-click the Edge Server listed, and then click **Edit Properties**.</span></span>

3.  <span data-ttu-id="ca7be-154">На странице **Общие** в разделе Переход к **следующему прыжку**выберите из раскрывающегося списка в группе Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ca7be-154">On the **General** page, under **Next hop selection**, select from the drop-down list the Lync Server 2013  pool.</span></span>
    
    <span data-ttu-id="ca7be-155">![Диалоговое окно "изменение свойств", страница следующего прыжка](images/JJ688121.5741b9a8-e729-4457-9f62-38f08a2c5b02(OCS.15).jpg "Диалоговое окно "изменение свойств", страница следующего прыжка")</span><span class="sxs-lookup"><span data-stu-id="ca7be-155">![Edit Properties dialog, Next hop page](images/JJ688121.5741b9a8-e729-4457-9f62-38f08a2c5b02(OCS.15).jpg "Edit Properties dialog, Next hop page")</span></span>

4.  <span data-ttu-id="ca7be-156">Нажмите кнопку **ОК** , чтобы закрыть страницу Изменение свойств.</span><span class="sxs-lookup"><span data-stu-id="ca7be-156">Click **OK** to close the Edit Properties page.</span></span>

5.  <span data-ttu-id="ca7be-157">В **построителе топологии**выберите верхний узел **Lync Server** .</span><span class="sxs-lookup"><span data-stu-id="ca7be-157">From **Topology Builder**, select the top node **Lync Server** .</span></span>

6.  <span data-ttu-id="ca7be-158">В меню **действия** выберите команду **топология публикации** и завершите работу мастера.</span><span class="sxs-lookup"><span data-stu-id="ca7be-158">From the **Action** menu, click **Publish Topology** and complete the wizard.</span></span>

</div>

<div>

## <a name="to-configure-lync-server-2013-edge-server-outbound-media-path"></a><span data-ttu-id="ca7be-159">Настройка пути исходящего носителя для Lync Server 2013 Edge Server</span><span class="sxs-lookup"><span data-stu-id="ca7be-159">To configure Lync Server 2013 Edge Server outbound media path</span></span>

1.  <span data-ttu-id="ca7be-160">Из построителя топологии в левой области перейдите на узел **Lync Server 2013** , а затем в пул под **стандартными серверами переднего плана выпуска Standard Edition** или **корпоративным интерфейсом Enterprise Edition**.</span><span class="sxs-lookup"><span data-stu-id="ca7be-160">From Topology Builder, in the left pane, navigate to the **Lync Server 2013** node and then to the pool below **Standard Edition Front End Servers** or **Enterprise Edition Front End pools**.</span></span>

2.  <span data-ttu-id="ca7be-161">Щелкните пул правой кнопкой мыши и выберите команду **изменить свойства**.</span><span class="sxs-lookup"><span data-stu-id="ca7be-161">Right-click the pool, and then click **Edit Properties**.</span></span>

3.  <span data-ttu-id="ca7be-162">В разделе " **связи** " установите флажок " **связать пул EDGE (для компонентов мультимедиа)** ".</span><span class="sxs-lookup"><span data-stu-id="ca7be-162">In the **Associations** section, select the **Associate Edge pool (for media components)** check box.</span></span>
    
    <span data-ttu-id="ca7be-163">![Изменение свойств, общее, связывание пограничного пула](images/JJ688121.fd9b18ca-fda2-4764-9bf0-726bf39f6a12(OCS.15).jpg "Изменение свойств, общее, связывание пограничного пула")</span><span class="sxs-lookup"><span data-stu-id="ca7be-163">![Edit Properties, General, Associate Edge pool](images/JJ688121.fd9b18ca-fda2-4764-9bf0-726bf39f6a12(OCS.15).jpg "Edit Properties, General, Associate Edge pool")</span></span>

4.  <span data-ttu-id="ca7be-164">В раскрывающемся списке выберите Lync Server 2013 Edge Server.</span><span class="sxs-lookup"><span data-stu-id="ca7be-164">From the drop down box, select the Lync Server 2013 Edge Server.</span></span>

5.  <span data-ttu-id="ca7be-165">Нажмите кнопку **ОК** , чтобы закрыть страницу **изменение свойств** .</span><span class="sxs-lookup"><span data-stu-id="ca7be-165">Click **OK** to close the **Edit Properties** page.</span></span>

</div>

<div>

## <a name="to-turn-on-lync-server-2013-edge-server-federation"></a><span data-ttu-id="ca7be-166">Включение интеграции сервера Lync Server 2013 Edge Server</span><span class="sxs-lookup"><span data-stu-id="ca7be-166">To turn on Lync Server 2013 Edge Server federation</span></span>

1.  <span data-ttu-id="ca7be-167">Из построителя топологии в левой области перейдите на узел **Lync Server 2013** , а затем в узел **Пулы Edge** .</span><span class="sxs-lookup"><span data-stu-id="ca7be-167">From Topology Builder, in the left pane, navigate to the **Lync Server 2013** node and then to the **Edge pools** node.</span></span>

2.  <span data-ttu-id="ca7be-168">Разверните узел, щелкните правой кнопкой мыши пограничный сервер в списке и выберите команду **изменить свойства**.</span><span class="sxs-lookup"><span data-stu-id="ca7be-168">Expand the node, right-click the Edge Server listed, and then click **Edit Properties**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="ca7be-169">Интеграция может быть включена только для одного пула пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="ca7be-169">Federation can only be enabled for a single Edge pool.</span></span> <span data-ttu-id="ca7be-170">Если у вас несколько пулов EDGE, выберите один из них, чтобы использовать его в качестве пула пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="ca7be-170">If you have multiple Edge pools, select one to use as the federating Edge pool.</span></span>

    
    </div>

3.  <span data-ttu-id="ca7be-171">На странице **General (общие** ) установите флажок **включить федерацию для этого пограничного пула (порт 5061)** .</span><span class="sxs-lookup"><span data-stu-id="ca7be-171">On the **General** page, verify the **Enable federation for this Edge pool (Port 5061)** setting is checked.</span></span>
    
    <span data-ttu-id="ca7be-172">![Диалоговое окно "изменение свойств", страница "Общие"](images/JJ688121.cc79a88c-cce4-4cab-80ad-4f70325dc7c4(OCS.15).jpg "Диалоговое окно "изменение свойств", страница "Общие"")</span><span class="sxs-lookup"><span data-stu-id="ca7be-172">![Edit Properties dialog, General page](images/JJ688121.cc79a88c-cce4-4cab-80ad-4f70325dc7c4(OCS.15).jpg "Edit Properties dialog, General page")</span></span>

4.  <span data-ttu-id="ca7be-173">Нажмите кнопку **ОК** , чтобы закрыть страницу Изменение свойств.</span><span class="sxs-lookup"><span data-stu-id="ca7be-173">Click **OK** to close the Edit Properties page.</span></span>

5.  <span data-ttu-id="ca7be-174">Затем перейдите к узлу сайта.</span><span class="sxs-lookup"><span data-stu-id="ca7be-174">Next, navigate to the site node.</span></span>

6.  <span data-ttu-id="ca7be-175">Щелкните сайт правой кнопкой мыши и выберите команду **изменить свойства**.</span><span class="sxs-lookup"><span data-stu-id="ca7be-175">Right-click the site, and then click **Edit Properties**.</span></span>

7.  <span data-ttu-id="ca7be-176">В левой области выберите пункт **маршрут Федерации**.</span><span class="sxs-lookup"><span data-stu-id="ca7be-176">In the left pane, click **Federation route**.</span></span>

8.  <span data-ttu-id="ca7be-177">В разделе **назначение маршрута Федерации сайтов**выберите **включить федерацию SIP**, а затем в списке выберите пункт Пограничный сервер Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ca7be-177">Under **Site federation route assignment**, select **Enable SIP federation**, and then from the list select the Lync Server 2013 Edge Server listed.</span></span>
    
    <span data-ttu-id="ca7be-178">![Страница "изменение свойств", "маршрут Федерации"](images/JJ688121.c50c13b8-0859-4e3e-8793-45c431a5b4b5(OCS.15).jpg "Страница "изменение свойств", "маршрут Федерации"")</span><span class="sxs-lookup"><span data-stu-id="ca7be-178">![Edit Properties, Federation route page](images/JJ688121.c50c13b8-0859-4e3e-8793-45c431a5b4b5(OCS.15).jpg "Edit Properties, Federation route page")</span></span>

9.  <span data-ttu-id="ca7be-179">Нажмите кнопку **ОК** , чтобы закрыть страницу **изменение свойств** .</span><span class="sxs-lookup"><span data-stu-id="ca7be-179">Click **OK** to close the **Edit Properties** page.</span></span>
    
    <span data-ttu-id="ca7be-180">Для развертываний с несколькими сайтами выполните эту процедуру на каждом сайте.</span><span class="sxs-lookup"><span data-stu-id="ca7be-180">For multi-site deployments, complete this procedure at each site.</span></span>

</div>

<div>

## <a name="to-publish-edge-server-configuration-changes"></a><span data-ttu-id="ca7be-181">Публикация изменений в конфигурации пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="ca7be-181">To publish Edge Server configuration changes</span></span>

1.  <span data-ttu-id="ca7be-182">В **построителе топологии**выберите верхний узел **Lync Server** .</span><span class="sxs-lookup"><span data-stu-id="ca7be-182">From **Topology Builder**, select the top node **Lync Server** .</span></span>

2.  <span data-ttu-id="ca7be-183">В меню **действия** выберите пункт **топология публикации** и завершите работу мастера.</span><span class="sxs-lookup"><span data-stu-id="ca7be-183">From the **Action** menu, select **Publish Topology** and complete the wizard.</span></span>

3.  <span data-ttu-id="ca7be-184">Дождитесь, когда репликация службы каталогов Active Directory будет выполняться для всех пулов в развертывании.</span><span class="sxs-lookup"><span data-stu-id="ca7be-184">Wait for Active Directory replication to occur to all pools in the deployment.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="ca7be-185">Может появиться следующее сообщение:</span><span class="sxs-lookup"><span data-stu-id="ca7be-185">You may see the following message:</span></span><BR><span data-ttu-id="ca7be-186"><STRONG>Предупреждение: топология состоит из нескольких федеративных пограничного сервера. Это может происходить при миграции в более позднюю версию продукта. В этом случае только один сервер пограничного сервера используется только для Федерации. Убедитесь, что внешняя SRV-запись DNS указывает на правильный пограничный сервер. Если вы хотите одновременно развернуть несколько пограничного сервера федерации (то есть не сценарий миграции), убедитесь в том, что все Федеративные партнеры используют Lync Server. Убедитесь, что внешняя SRV-запись содержит все пограничные серверы, поддерживающие Федерацию.</STRONG></span><span class="sxs-lookup"><span data-stu-id="ca7be-186"><STRONG>Warning: The topology contains more than one Federated Edge Server. This can occur during migration to a more recent version of the product. In that case, only one Edge Server would be actively used for federation. Verify that the external DNS SRV record points to the correct Edge Server. If you want to deploy multiple federation Edge Server to be active concurrently (that is, not a migration scenario), verify that all federated partners are using Lync Server. Verify that the external DNS SRV record lists all federation enabled Edge Servers.</STRONG></span></span><BR><span data-ttu-id="ca7be-187">Это предупреждение ожидается, и его можно игнорировать.</span><span class="sxs-lookup"><span data-stu-id="ca7be-187">This warning is expected and can be safely ignored.</span></span>

    
    </div>

</div>

<div>

## <a name="to-configure-lync-server-2013-edge-server"></a><span data-ttu-id="ca7be-188">Настройка пограничного сервера Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ca7be-188">To configure Lync Server 2013 Edge Server</span></span>

1.  <span data-ttu-id="ca7be-189">Выведите все серверы Lync Server 2013 Edge-in Online.</span><span class="sxs-lookup"><span data-stu-id="ca7be-189">Bring all of the Lync Server 2013 Edge Servers online.</span></span>

2.  <span data-ttu-id="ca7be-190">Обновите правила маршрутизации внешних брандмауэров или параметры подсистемы балансировки нагрузки оборудования, чтобы отправить трафик SIP для внешнего доступа (обычно это порт 443) и Федерацию (обычно это порт 5061) на пограничный сервер Lync Server 2013 вместо устаревшего пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="ca7be-190">Update the external firewall routing rules or the hardware load balancer settings to send SIP traffic for external access (usually port 443) and federation (usually port 5061) to the Lync Server 2013 Edge Server, instead of the legacy Edge Server.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="ca7be-191">Если у вас нет аппаратной подсистемы балансировки нагрузки, вам нужно обновить запись DNS A для Федерации, чтобы устранить проблему с новым сервером пограничного доступа Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ca7be-191">If you do not have a hardware load balancer, you need to update the DNS A record for federation to resolve to the new Lync Server Access Edge server.</span></span> <span data-ttu-id="ca7be-192">Чтобы добиться этого с минимальным перерывом, уменьшите значение ТЛЛ для внешнего полного доменного имени Lync Server, чтобы при обновлении DNS для указания на новый край доступа к Lync Server вы сможете быстро обновлять Федерацию и удаленный доступ.</span><span class="sxs-lookup"><span data-stu-id="ca7be-192">To accomplish this with minimum disruption, reduce the TLL value for the external Lync Server Access Edge FQDN so that when DNS is updated to point to the new Lync Server Access Edge, federation and remote access will be updated quickly.</span></span>

    
    </div>

3.  <span data-ttu-id="ca7be-193">Затем остановите **границу доступа Lync Server** с каждого компьютера пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="ca7be-193">Next, stop the **Lync Server Access Edge** from each Edge Server computer.</span></span>

4.  <span data-ttu-id="ca7be-194">На каждом компьютере пограничного серверного сервера откройте приложение " **службы** " из **меню**"Администрирование".</span><span class="sxs-lookup"><span data-stu-id="ca7be-194">From each legacy Edge Server computer, open the **Services** applet from the **Administrative Tools**.</span></span>

5.  <span data-ttu-id="ca7be-195">В списке услуги найдите **край доступа к Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="ca7be-195">In the services list, find **Lync Server Access Edge**.</span></span>

6.  <span data-ttu-id="ca7be-196">Щелкните правой кнопкой мыши имя службы, а затем выберите команду **остановить** , чтобы остановить службу.</span><span class="sxs-lookup"><span data-stu-id="ca7be-196">Right-click the services name, and then select **Stop** to stop the service.</span></span>

7.  <span data-ttu-id="ca7be-197">Установите для типа запуска значение **отключено**.</span><span class="sxs-lookup"><span data-stu-id="ca7be-197">Set the Startup type to **Disabled**.</span></span>

8.  <span data-ttu-id="ca7be-198">Нажмите кнопку **ОК** , чтобы закрыть окно " **свойства** ".</span><span class="sxs-lookup"><span data-stu-id="ca7be-198">Click **OK** to close the **Properties** window.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

