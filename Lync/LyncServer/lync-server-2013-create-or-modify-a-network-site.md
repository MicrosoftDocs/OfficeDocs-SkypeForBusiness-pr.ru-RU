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
ms.openlocfilehash: ed721a48b12a497b25d58e7ebb65ff3a91980904
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41722578"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-network-site-in-lync-server-2013"></a><span data-ttu-id="1002e-102">Создание или изменение сетевого сайта в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1002e-102">Create or modify a network site in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1002e-103">_**Тема последнего изменения:** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="1002e-103">_**Topic Last Modified:** 2013-02-24_</span></span>

<span data-ttu-id="1002e-104">Управление допуском звонков (CAC), E9-1-1, а для обхода мультимедийных развертываний используются *Сетевые сайты* , определенные внутри и всегда связанные с сетевым регионом.</span><span class="sxs-lookup"><span data-stu-id="1002e-104">Call admission control (CAC), E9-1-1, and media bypass deployments rely on the configuration of *network sites* which are defined within and always associated with a network region.</span></span> <span data-ttu-id="1002e-105">Сетевой сайт представляет местонахождение офиса подразделения, набор зданий или кампус.</span><span class="sxs-lookup"><span data-stu-id="1002e-105">A network site represents a branch office location, a set of buildings, or a campus.</span></span> <span data-ttu-id="1002e-106">Сетевые сайты представляют собой коллекции подсетей с одинаковой пропускной способностью.</span><span class="sxs-lookup"><span data-stu-id="1002e-106">Network sites represent collections of subnets with similar bandwidth.</span></span>

<span data-ttu-id="1002e-107">Чтобы создать или изменить сетевые сайты, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="1002e-107">Use the following procedures to create or modify network sites.</span></span> <span data-ttu-id="1002e-108">Например, если вы уже создали сетевые сайты для одной голосовой связи, вам не нужно создавать новые сетевые сайты; другие функции голосовой связи будут использовать те же сайты.</span><span class="sxs-lookup"><span data-stu-id="1002e-108">For example, if you have already created network sites for one Voice feature, you do not need to create new network sites; other Voice features will use those same sites.</span></span> <span data-ttu-id="1002e-109">You may, however, need to modify an existing network site definition to apply feature-specific settings.</span><span class="sxs-lookup"><span data-stu-id="1002e-109">You may, however, need to modify an existing network site definition to apply feature-specific settings.</span></span> <span data-ttu-id="1002e-110">For example, if you created a network site for E9-1-1, you need to modify the network site during deployment of call admission control to apply a bandwidth policy profile.</span><span class="sxs-lookup"><span data-stu-id="1002e-110">For example, if you created a network site for E9-1-1, you need to modify the network site during deployment of call admission control to apply a bandwidth policy profile.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="1002e-111">Там, где они есть, вы можете найти конкретные примеры и требования к сетевым сайтам, которые относятся к дополнительным функциям голосовой связи в документации по развертыванию для каждой из функций.</span><span class="sxs-lookup"><span data-stu-id="1002e-111">Where they exist, you can find specific examples and requirements for network sites as they pertain to an advanced Voice feature in the Deployment documentation for each feature:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="1002e-112"><A href="lync-server-2013-configure-network-sites-for-cac.md">Настройка сетевых сайтов для CAC в Lync Server 2013</A></span><span class="sxs-lookup"><span data-stu-id="1002e-112"><A href="lync-server-2013-configure-network-sites-for-cac.md">Configure network sites for CAC in Lync Server 2013</A></span></span></P></LI></UL>



</div>

<span data-ttu-id="1002e-113">Дополнительные сведения о работе с сетевыми сайтами можно найти в документации по оболочке Lync Server Management Shell для следующих командлетов:</span><span class="sxs-lookup"><span data-stu-id="1002e-113">For details about working with network sites, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - [<span data-ttu-id="1002e-114">New-CsNetworkSite</span><span class="sxs-lookup"><span data-stu-id="1002e-114">New-CsNetworkSite</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSite)

  - [<span data-ttu-id="1002e-115">Get-CsNetworkSite</span><span class="sxs-lookup"><span data-stu-id="1002e-115">Get-CsNetworkSite</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSite)

  - [<span data-ttu-id="1002e-116">Set-CsNetworkSite</span><span class="sxs-lookup"><span data-stu-id="1002e-116">Set-CsNetworkSite</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkSite)

  - [<span data-ttu-id="1002e-117">Remove-CsNetworkSite</span><span class="sxs-lookup"><span data-stu-id="1002e-117">Remove-CsNetworkSite</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkSite)

<div>

## <a name="create-a-network-site"></a><span data-ttu-id="1002e-118">Создание сайта сети</span><span class="sxs-lookup"><span data-stu-id="1002e-118">Create a Network Site</span></span>

<span data-ttu-id="1002e-119">Создание сетевого региона, который может использоваться для управления допуском звонков, E9-1-1 или мультимедийного обхода.</span><span class="sxs-lookup"><span data-stu-id="1002e-119">Create a network region that can be used by call admission control, E9-1-1, or media bypass.</span></span>

<div>

## <a name="to-create-a-network-site-by-using-management-shell"></a><span data-ttu-id="1002e-120">Создание сетевого сайта с помощью командной консоли</span><span class="sxs-lookup"><span data-stu-id="1002e-120">To create a network site by using Management Shell</span></span>

1.  <span data-ttu-id="1002e-121">Запустите командную консоль Lync Server Management Shell: нажмите кнопку **Пуск**, выберите **все программы**, а затем — **Microsoft Lync Server 2013**, а затем — **Командная консоль Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="1002e-121">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="1002e-122">Выполните командлет New-CsNetworkSite для создания областей сети:</span><span class="sxs-lookup"><span data-stu-id="1002e-122">Run the New-CsNetworkSite cmdlet to create network sites:</span></span>
    
        New-CsNetworkSite -NetworkSiteID <string>
    
    <span data-ttu-id="1002e-123">Например:</span><span class="sxs-lookup"><span data-stu-id="1002e-123">For example:</span></span>
    
        New-CsNetworkSite -NetworkSiteID Chicago -Description "Corporate headquarters"-NetworkRegionID NorthAmerica
    
    <span data-ttu-id="1002e-124">В этом примере создается сетевой узел с именем "Chicago" в области сети "NorthAmerica".</span><span class="sxs-lookup"><span data-stu-id="1002e-124">In this example, you created a network site called “Chicago” that is in the “NorthAmerica” network region.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="1002e-125">Чтобы эта команда выполнилась успешно, область сети NorthAmerica должна уже быть создана.</span><span class="sxs-lookup"><span data-stu-id="1002e-125">The NorthAmerica network region must already exist for this command to run successfully.</span></span>

    
    </div>

3.  <span data-ttu-id="1002e-126">Чтобы закончить создание сетевых узлов для вашей топологии, повторите действие 2 с параметрами других узлов.</span><span class="sxs-lookup"><span data-stu-id="1002e-126">To finish creating network sites for your topology, repeat step 2 with settings for other sites.</span></span>

</div>

<div>

## <a name="to-create-a-network-site-by-using-lync-server-control-panel"></a><span data-ttu-id="1002e-127">Создание сайта сети с помощью панели управления Lync Server</span><span class="sxs-lookup"><span data-stu-id="1002e-127">To create a network site by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="1002e-128">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="1002e-128">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="1002e-129">Дополнительные сведения о различных способах, которые можно использовать для запуска панели управления Lync Server, приведены в разделе [Открытие меню администрирования Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="1002e-129">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

2.  <span data-ttu-id="1002e-130">В левой области навигации щелкните элемент **Конфигурация сети**.</span><span class="sxs-lookup"><span data-stu-id="1002e-130">In the left navigation bar, click **Network Configuration**.</span></span>

3.  <span data-ttu-id="1002e-131">Нажмите кнопку навигации **Сайт**.</span><span class="sxs-lookup"><span data-stu-id="1002e-131">Click the **Site** navigation button.</span></span>

4.  <span data-ttu-id="1002e-132">Выберите **Создать**.</span><span class="sxs-lookup"><span data-stu-id="1002e-132">Click **New**.</span></span>

5.  <span data-ttu-id="1002e-133">На странице **Создать сайт** выберите поле **Имя** и введите имя для сетевого сайта.</span><span class="sxs-lookup"><span data-stu-id="1002e-133">On the **New Site** page, click **Name** and then type a name for the network site.</span></span>

6.  <span data-ttu-id="1002e-134">Нажмите пункт **Область** и выберите в списке нужную область.</span><span class="sxs-lookup"><span data-stu-id="1002e-134">Click **Region**, and then click a region in the list.</span></span>

7.  <span data-ttu-id="1002e-135">Дополнительно можно выбрать пункт **Политика пропускной способности** и выбрать нужную политику в списке.</span><span class="sxs-lookup"><span data-stu-id="1002e-135">Optionally, click **Bandwidth policy**, and then click a bandwidth policy in the list.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="1002e-136">Политика пропускной способности требуется только в том случае, если в узле разворачивается контроль допуска звонков.</span><span class="sxs-lookup"><span data-stu-id="1002e-136">Bandwidth policy is required only if you deploy call admission control at the site.</span></span>

    
    </div>

8.  <span data-ttu-id="1002e-137">Дополнительно можно выбрать пункт **Политика местонахождения** и выбрать нужную политику местонахождения в списке.</span><span class="sxs-lookup"><span data-stu-id="1002e-137">Optionally, click **Location policy**, and then click a location policy in the list.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="1002e-138">Политика местонахождения требуется только в том случае, если в узле разворачивается служба E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="1002e-138">Location policy is required only if you deploy E9-1-1 at the site.</span></span>

    
    </div>

9.  <span data-ttu-id="1002e-139">В поле **Описание** введите дополнительные сведения об области сети (необязательно).</span><span class="sxs-lookup"><span data-stu-id="1002e-139">Optionally, click **Description**, and then type additional information to describe this network site.</span></span>

10. <span data-ttu-id="1002e-140">Нажмите **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="1002e-140">Click **Commit**.</span></span>

11. <span data-ttu-id="1002e-141">Чтобы завершить создание сетевых узлов для вашей топологии, повторите действия с 4 по 10 с параметрами для других узлов.</span><span class="sxs-lookup"><span data-stu-id="1002e-141">To finish creating network sites for your topology, repeat steps 4 through 10 with settings for other sites.</span></span>

</div>

</div>

<div>

## <a name="modify-a-network-site"></a><span data-ttu-id="1002e-142">Изменение сетевого сайта</span><span class="sxs-lookup"><span data-stu-id="1002e-142">Modify a Network Site</span></span>

<span data-ttu-id="1002e-143">Изменение сетевого региона, который может использоваться для управления допуском звонков, E9-1-1 или мультимедийного обхода.</span><span class="sxs-lookup"><span data-stu-id="1002e-143">Modify a network region that can be used by call admission control, E9-1-1, or media bypass.</span></span>

<div>

## <a name="to-modify-a-network-site"></a><span data-ttu-id="1002e-144">Изменение сетевого сайта</span><span class="sxs-lookup"><span data-stu-id="1002e-144">To modify a network site</span></span>

1.  <span data-ttu-id="1002e-145">Запустите командную консоль Lync Server Management Shell: нажмите кнопку **Пуск**, выберите **все программы**, а затем — **Microsoft Lync Server 2013**, а затем — **Командная консоль Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="1002e-145">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="1002e-146">Чтобы изменить сетевые узлы, выполните командлет Set-CsNetworkSite:</span><span class="sxs-lookup"><span data-stu-id="1002e-146">Run the Set-CsNetworkSite cmdlet to modify network sites:</span></span>
    
        Set-CsNetworkSite -Identity <string>
    
    <span data-ttu-id="1002e-147">Например:</span><span class="sxs-lookup"><span data-stu-id="1002e-147">For example:</span></span>
    
        Set-CsNetworkSite -Identity Albuquerque -NetworkRegionID NorthAmerica
    
    <span data-ttu-id="1002e-p104">В данном примере узел с именем "Albuquerque" перемещается в область сети "NorthAmerica". Чтобы изменить конфигурацию этого сетевого узла для развертывания контроля допуска звонков, E9-1-1 или обхода сервера-посредника, измените параметры сетевого узла, выполнив командлет Set-CsNetworkSite с параметром BWPolicyProfileID или LocationPolicy соответственно.</span><span class="sxs-lookup"><span data-stu-id="1002e-p104">In this example, the site called “Albuquerque” is moved to the “NorthAmerica” network region. To modify the network site configuration to deploy call admission control, E9-1-1, or media bypass, modify the network site settings by running the Set-CsNetworkSite cmdlet with the BWPolicyProfileID or LocationPolicy parameter, respectively.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="1002e-p105">Хотя для обхода сервера-посредника существует параметр BypassID, настоятельно рекомендуется не переопределять автоматически созданные идентификаторы обхода. Чтобы настроить сетевой узел для обхода сервера-посредника, указывать дополнительные параметры не требуется.</span><span class="sxs-lookup"><span data-stu-id="1002e-p105">Although the BypassID parameter exists for media bypass, we strongly recommend that you do not override automatically generated bypass IDs. You do not need to specify additional parameters to configure a network site for media bypass.</span></span>

    
    </div>

3.  <span data-ttu-id="1002e-152">Чтобы закончить изменение сетевых узлов для вашей топологии, повторите действие 2 с параметрами других узлов.</span><span class="sxs-lookup"><span data-stu-id="1002e-152">To finish modifying network sites for your topology, repeat step 2 with settings for other sites.</span></span>

</div>

<div>

## <a name="to-modify-a-network-site-by-using-lync-server-control-panel"></a><span data-ttu-id="1002e-153">Изменение сетевого сайта с помощью панели управления Lync Server</span><span class="sxs-lookup"><span data-stu-id="1002e-153">To modify a network site by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="1002e-154">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="1002e-154">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="1002e-155">Дополнительные сведения о различных способах, которые можно использовать для запуска панели управления Lync Server, приведены в разделе [Открытие меню администрирования Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="1002e-155">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

2.  <span data-ttu-id="1002e-156">В левой области навигации щелкните элемент **Конфигурация сети**.</span><span class="sxs-lookup"><span data-stu-id="1002e-156">In the left navigation bar, click **Network Configuration**.</span></span>

3.  <span data-ttu-id="1002e-157">Нажмите кнопку навигации **Сайт**.</span><span class="sxs-lookup"><span data-stu-id="1002e-157">Click the **Site** navigation button.</span></span>

4.  <span data-ttu-id="1002e-158">Выберите в таблице сетевой узел, который требуется изменить.</span><span class="sxs-lookup"><span data-stu-id="1002e-158">In the table, click the network site that you want to modify.</span></span>

5.  <span data-ttu-id="1002e-159">Щелкните **Изменить**, затем щелкните **Подробнее**.</span><span class="sxs-lookup"><span data-stu-id="1002e-159">Click **Edit**, and then click **Show details…**.</span></span>

6.  <span data-ttu-id="1002e-160">На странице **Изменение сайта** соответствующим образом измените значения параметров для этого сетевого узла.</span><span class="sxs-lookup"><span data-stu-id="1002e-160">On the **Edit Site** page, change the values for this network site’s settings as appropriate.</span></span>

7.  <span data-ttu-id="1002e-161">Нажмите **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="1002e-161">Click **Commit**.</span></span>

8.  <span data-ttu-id="1002e-162">Чтобы завершить изменение сетевых узлов, повторите действия с 4 по 7 с параметрами для других узлов.</span><span class="sxs-lookup"><span data-stu-id="1002e-162">To finish modify network sites, repeat steps 4 through 7 with settings for other sites.</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

