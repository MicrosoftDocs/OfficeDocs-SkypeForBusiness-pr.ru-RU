---
title: 'Lync Server 2013: создание или изменение сетевого сайта'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a network site
ms:assetid: 14e24856-9996-4da4-9f31-300940bdf5aa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398218(v=OCS.15)
ms:contentKeyID: 48183488
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 11ad625834682e8d5d6a820c999a14a19e79b863
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42154391"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-network-site-in-lync-server-2013"></a><span data-ttu-id="892f6-102">Создание или изменение сетевого сайта в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="892f6-102">Create or modify a network site in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="892f6-103">_**Последнее изменение темы:** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="892f6-103">_**Topic Last Modified:** 2013-02-24_</span></span>

<span data-ttu-id="892f6-104">Развертывания контроля допуска звонков (CAC), E9-1-1 и обхода сервера-посредника зависят от конфигурации *сетевых узлов*, которые задаются в областях сети и всегда с ними связаны.</span><span class="sxs-lookup"><span data-stu-id="892f6-104">Call admission control (CAC), E9-1-1, and media bypass deployments rely on the configuration of *network sites* which are defined within and always associated with a network region.</span></span> <span data-ttu-id="892f6-105">Сетевой сайт представляет местонахождение филиала, набор зданий или кампуса.</span><span class="sxs-lookup"><span data-stu-id="892f6-105">A network site represents a branch office location, a set of buildings, or a campus.</span></span> <span data-ttu-id="892f6-106">Сетевые узлы представляют наборы подсетей с одинаковой пропускной способностью.</span><span class="sxs-lookup"><span data-stu-id="892f6-106">Network sites represent collections of subnets with similar bandwidth.</span></span>

<span data-ttu-id="892f6-p102">Для создания или изменения сетевых узлов используются следующие процедуры. Например, если для одной функции голосовой связи уже созданы сетевые узлы, не требуется создавать новые сетевые узлы; другие функции голосовой связи будут использовать те же самые узлы. Однако может потребоваться изменить определение существующего сетевого узла, чтобы применить параметры, относящиеся к определенной функции. Например, если создан сетевой узел для E9-1-1, то во время развертывания контроля допуска звонков придется изменить этот сетевой узел, чтобы применить профиль политики пропускной способности.</span><span class="sxs-lookup"><span data-stu-id="892f6-p102">Use the following procedures to create or modify network sites. For example, if you have already created network sites for one Voice feature, you do not need to create new network sites; other Voice features will use those same sites. You may, however, need to modify an existing network site definition to apply feature-specific settings. For example, if you created a network site for E9-1-1, you need to modify the network site during deployment of call admission control to apply a bandwidth policy profile.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="892f6-111">Если конкретные примеры и требования для сетевых узлов существуют, то поскольку они касаются расширенной функции голосовой связи, их можно найти в документации по развертыванию каждой функции.</span><span class="sxs-lookup"><span data-stu-id="892f6-111">Where they exist, you can find specific examples and requirements for network sites as they pertain to an advanced Voice feature in the Deployment documentation for each feature:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="892f6-112"><A href="lync-server-2013-configure-network-sites-for-cac.md">Настройка сетевых сайтов для контроля допуска звонков в Lync Server 2013</A></span><span class="sxs-lookup"><span data-stu-id="892f6-112"><A href="lync-server-2013-configure-network-sites-for-cac.md">Configure network sites for CAC in Lync Server 2013</A></span></span></P></LI></UL>



</div>

<span data-ttu-id="892f6-113">Для получения подробных сведений о работе с сетевыми сайтами обратитесь к документации по командной консоли Lync Server для следующих командлетов:</span><span class="sxs-lookup"><span data-stu-id="892f6-113">For details about working with network sites, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - [<span data-ttu-id="892f6-114">New — CsNetworkSite</span><span class="sxs-lookup"><span data-stu-id="892f6-114">New-CsNetworkSite</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSite)

  - [<span data-ttu-id="892f6-115">Get — CsNetworkSite</span><span class="sxs-lookup"><span data-stu-id="892f6-115">Get-CsNetworkSite</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSite)

  - [<span data-ttu-id="892f6-116">Set — CsNetworkSite</span><span class="sxs-lookup"><span data-stu-id="892f6-116">Set-CsNetworkSite</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkSite)

  - [<span data-ttu-id="892f6-117">Remove — CsNetworkSite</span><span class="sxs-lookup"><span data-stu-id="892f6-117">Remove-CsNetworkSite</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkSite)

<div>

## <a name="create-a-network-site"></a><span data-ttu-id="892f6-118">Создание сетевого узла</span><span class="sxs-lookup"><span data-stu-id="892f6-118">Create a Network Site</span></span>

<span data-ttu-id="892f6-119">Создайте область сети, которая может использоваться контролем допуска звонков, E9-1-1 или обходом сервера-посредника.</span><span class="sxs-lookup"><span data-stu-id="892f6-119">Create a network region that can be used by call admission control, E9-1-1, or media bypass.</span></span>

<div>

## <a name="to-create-a-network-site-by-using-management-shell"></a><span data-ttu-id="892f6-120">Создание области сети с помощью командной консоли</span><span class="sxs-lookup"><span data-stu-id="892f6-120">To create a network site by using Management Shell</span></span>

1.  <span data-ttu-id="892f6-121">Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="892f6-121">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="892f6-122">Выполните командлет New-CsNetworkSite для создания областей сети:</span><span class="sxs-lookup"><span data-stu-id="892f6-122">Run the New-CsNetworkSite cmdlet to create network sites:</span></span>
    
        New-CsNetworkSite -NetworkSiteID <string>
    
    <span data-ttu-id="892f6-123">Например:</span><span class="sxs-lookup"><span data-stu-id="892f6-123">For example:</span></span>
    
        New-CsNetworkSite -NetworkSiteID Chicago -Description "Corporate headquarters"-NetworkRegionID NorthAmerica
    
    <span data-ttu-id="892f6-124">В этом примере создается сетевой узел с именем “Chicago” в области сети “NorthAmerica”.</span><span class="sxs-lookup"><span data-stu-id="892f6-124">In this example, you created a network site called “Chicago” that is in the “NorthAmerica” network region.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="892f6-125">Чтобы эта команда выполнилась успешно, область сети NorthAmerica должна уже быть создана.</span><span class="sxs-lookup"><span data-stu-id="892f6-125">The NorthAmerica network region must already exist for this command to run successfully.</span></span>

    
    </div>

3.  <span data-ttu-id="892f6-126">Чтобы закончить создание сетевых узлов для вашей топологии, повторите действие 2 с параметрами других узлов.</span><span class="sxs-lookup"><span data-stu-id="892f6-126">To finish creating network sites for your topology, repeat step 2 with settings for other sites.</span></span>

</div>

<div>

## <a name="to-create-a-network-site-by-using-lync-server-control-panel"></a><span data-ttu-id="892f6-127">Создание сетевого узла с помощью панели управления Lync Server</span><span class="sxs-lookup"><span data-stu-id="892f6-127">To create a network site by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="892f6-128">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="892f6-128">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="892f6-129">Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="892f6-129">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

2.  <span data-ttu-id="892f6-130">В левой панели навигации выберите пункт **Конфигурация сети**.</span><span class="sxs-lookup"><span data-stu-id="892f6-130">In the left navigation bar, click **Network Configuration**.</span></span>

3.  <span data-ttu-id="892f6-131">Нажмите кнопку навигации **Узел**.</span><span class="sxs-lookup"><span data-stu-id="892f6-131">Click the **Site** navigation button.</span></span>

4.  <span data-ttu-id="892f6-132">Нажмите **New (Создать)**.</span><span class="sxs-lookup"><span data-stu-id="892f6-132">Click **New**.</span></span>

5.  <span data-ttu-id="892f6-133">На странице **Новый узел** выберите поле **Имя** и введите имя для сетевого узла.</span><span class="sxs-lookup"><span data-stu-id="892f6-133">On the **New Site** page, click **Name** and then type a name for the network site.</span></span>

6.  <span data-ttu-id="892f6-134">Нажмите пункт **Область** и выберите в списке нужную область.</span><span class="sxs-lookup"><span data-stu-id="892f6-134">Click **Region**, and then click a region in the list.</span></span>

7.  <span data-ttu-id="892f6-135">Дополнительно можно выбрать пункт **Политика пропускной способности** и выбрать нужную политику в списке.</span><span class="sxs-lookup"><span data-stu-id="892f6-135">Optionally, click **Bandwidth policy**, and then click a bandwidth policy in the list.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="892f6-136">Политика пропускной способности требуется только в том случае, если в узле разворачивается контроль допуска звонков.</span><span class="sxs-lookup"><span data-stu-id="892f6-136">Bandwidth policy is required only if you deploy call admission control at the site.</span></span>

    
    </div>

8.  <span data-ttu-id="892f6-137">Дополнительно можно выбрать пункт **Политика местонахождения** и выбрать нужную политику местонахождения в списке.</span><span class="sxs-lookup"><span data-stu-id="892f6-137">Optionally, click **Location policy**, and then click a location policy in the list.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="892f6-138">Политика местонахождения требуется только в том случае, если в узле разворачивается служба E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="892f6-138">Location policy is required only if you deploy E9-1-1 at the site.</span></span>

    
    </div>

9.  <span data-ttu-id="892f6-139">Дополнительно можно выбрать пункт **Описание** и ввести дополнительные сведения для описания данного узла сети.</span><span class="sxs-lookup"><span data-stu-id="892f6-139">Optionally, click **Description**, and then type additional information to describe this network site.</span></span>

10. <span data-ttu-id="892f6-140">Щелкните **Commit** (Применить).</span><span class="sxs-lookup"><span data-stu-id="892f6-140">Click **Commit**.</span></span>

11. <span data-ttu-id="892f6-141">Чтобы завершить создание сетевых узлов для вашей топологии, повторите действия с 4 по 10 с параметрами для других узлов.</span><span class="sxs-lookup"><span data-stu-id="892f6-141">To finish creating network sites for your topology, repeat steps 4 through 10 with settings for other sites.</span></span>

</div>

</div>

<div>

## <a name="modify-a-network-site"></a><span data-ttu-id="892f6-142">Изменение сетевого узла</span><span class="sxs-lookup"><span data-stu-id="892f6-142">Modify a Network Site</span></span>

<span data-ttu-id="892f6-143">Измените область сети, которая может использоваться контролем допуска звонков, службой E9-1-1 или обходом сервера-посредника.</span><span class="sxs-lookup"><span data-stu-id="892f6-143">Modify a network region that can be used by call admission control, E9-1-1, or media bypass.</span></span>

<div>

## <a name="to-modify-a-network-site"></a><span data-ttu-id="892f6-144">Изменение сетевого узла</span><span class="sxs-lookup"><span data-stu-id="892f6-144">To modify a network site</span></span>

1.  <span data-ttu-id="892f6-145">Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="892f6-145">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="892f6-146">Чтобы изменить сетевые узлы, выполните командлет Set-CsNetworkSite:</span><span class="sxs-lookup"><span data-stu-id="892f6-146">Run the Set-CsNetworkSite cmdlet to modify network sites:</span></span>
    
        Set-CsNetworkSite -Identity <string>
    
    <span data-ttu-id="892f6-147">Например:</span><span class="sxs-lookup"><span data-stu-id="892f6-147">For example:</span></span>
    
        Set-CsNetworkSite -Identity Albuquerque -NetworkRegionID NorthAmerica
    
    <span data-ttu-id="892f6-p104">В данном примере узел с именем “Albuquerque” перемещается в область сети “NorthAmerica”. Чтобы изменить конфигурацию этого сетевого узла для развертывания контроля допуска звонков, E9-1-1 или обхода сервера-посредника, измените параметры сетевого узла, выполнив командлет Set-CsNetworkSite с параметром BWPolicyProfileID или LocationPolicy соответственно.</span><span class="sxs-lookup"><span data-stu-id="892f6-p104">In this example, the site called “Albuquerque” is moved to the “NorthAmerica” network region. To modify the network site configuration to deploy call admission control, E9-1-1, or media bypass, modify the network site settings by running the Set-CsNetworkSite cmdlet with the BWPolicyProfileID or LocationPolicy parameter, respectively.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="892f6-p105">Хотя для обхода сервера-посредника существует параметр BypassID, настоятельно рекомендуется не переопределять автоматически созданные идентификаторы обхода. Чтобы настроить сетевой узел для обхода сервера-посредника, указывать дополнительные параметры не требуется.</span><span class="sxs-lookup"><span data-stu-id="892f6-p105">Although the BypassID parameter exists for media bypass, we strongly recommend that you do not override automatically generated bypass IDs. You do not need to specify additional parameters to configure a network site for media bypass.</span></span>

    
    </div>

3.  <span data-ttu-id="892f6-152">Чтобы закончить изменение сетевых узлов для вашей топологии, повторите действие 2 с параметрами других узлов.</span><span class="sxs-lookup"><span data-stu-id="892f6-152">To finish modifying network sites for your topology, repeat step 2 with settings for other sites.</span></span>

</div>

<div>

## <a name="to-modify-a-network-site-by-using-lync-server-control-panel"></a><span data-ttu-id="892f6-153">Изменение сетевого узла с помощью панели управления Lync Server</span><span class="sxs-lookup"><span data-stu-id="892f6-153">To modify a network site by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="892f6-154">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="892f6-154">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="892f6-155">Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="892f6-155">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

2.  <span data-ttu-id="892f6-156">В левой панели навигации выберите пункт **Конфигурация сети**.</span><span class="sxs-lookup"><span data-stu-id="892f6-156">In the left navigation bar, click **Network Configuration**.</span></span>

3.  <span data-ttu-id="892f6-157">Нажмите кнопку навигации **Узел**.</span><span class="sxs-lookup"><span data-stu-id="892f6-157">Click the **Site** navigation button.</span></span>

4.  <span data-ttu-id="892f6-158">Выберите в таблице сетевой узел, который требуется изменить.</span><span class="sxs-lookup"><span data-stu-id="892f6-158">In the table, click the network site that you want to modify.</span></span>

5.  <span data-ttu-id="892f6-159">Нажмите **Изменить**, а затем нажмите **Показать детали...**.</span><span class="sxs-lookup"><span data-stu-id="892f6-159">Click **Edit**, and then click **Show details…**.</span></span>

6.  <span data-ttu-id="892f6-160">На странице **Изменение узла** соответствующим образом измените значения параметров для этого сетевого узла.</span><span class="sxs-lookup"><span data-stu-id="892f6-160">On the **Edit Site** page, change the values for this network site’s settings as appropriate.</span></span>

7.  <span data-ttu-id="892f6-161">Нажмите кнопку **Зафиксировать**.</span><span class="sxs-lookup"><span data-stu-id="892f6-161">Click **Commit**.</span></span>

8.  <span data-ttu-id="892f6-162">Чтобы завершить изменение сетевых узлов, повторите действия с 4 по 7 с параметрами для других узлов.</span><span class="sxs-lookup"><span data-stu-id="892f6-162">To finish modify network sites, repeat steps 4 through 7 with settings for other sites.</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

