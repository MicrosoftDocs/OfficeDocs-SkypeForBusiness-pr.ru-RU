---
title: 'Lync Server 2013: создание или изменение области сети'
description: 'Lync Server 2013: создание или изменение области сети.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a network region
ms:assetid: bf7a3dc4-71a2-4559-a547-d90305d4f904
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412933(v=OCS.15)
ms:contentKeyID: 48185281
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a149a668f64df804d2631243d9bb63401bd8a284
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48562235"
---
# <a name="create-or-modify-a-network-region-in-lync-server-2013"></a><span data-ttu-id="00ae6-103">Создание или изменение области сети в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="00ae6-103">Create or modify a network region in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="00ae6-104">_**Последнее изменение темы:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="00ae6-104">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="00ae6-105">*Области сети* представляют сетевые концентраторы или магистрали, используемые при настройке контроля допуска звонков, службы E9-1-1 и обхода сервера-посредника.</span><span class="sxs-lookup"><span data-stu-id="00ae6-105">*Network regions* are the network hubs or backbones used in the configuration of call admission control, E9-1-1, and media bypass.</span></span> <span data-ttu-id="00ae6-106">Для создания и изменения областей сети используйте процедуры, описанные в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="00ae6-106">Use the following procedures to create or modify network regions.</span></span> <span data-ttu-id="00ae6-107">Например, если вы уже создали области сети для одной функции голосовой связи, то вам не потребуется создавать новые области сети, поскольку остальные функции корпоративной голосовой связи будут использовать имеющиеся области сети.</span><span class="sxs-lookup"><span data-stu-id="00ae6-107">For example, if you have already created network regions for one Voice feature, you do not need to create new network regions; other advanced Enterprise Voice features will use those same network regions.</span></span> <span data-ttu-id="00ae6-108">Тем не менее, возможно, потребуется изменить существующее определение области сети, чтобы применить специальные настройки для конкретных компонентов.</span><span class="sxs-lookup"><span data-stu-id="00ae6-108">You may, however, need to modify an existing network region definition to apply feature-specific settings.</span></span> <span data-ttu-id="00ae6-109">Например, когда после создания областей сети для системы E9-1-1 (которой не требуется связанный центральный сайт) выполняется развертывание системы контроля допуска звонков, потребуется изменить определения области сети для указания центрального сайта.</span><span class="sxs-lookup"><span data-stu-id="00ae6-109">For example, if you have created network regions for E9-1-1 (which do not require an associated central site) and you then deploy call admission control, you need to modify the network region definitions to specify a central site.</span></span> <span data-ttu-id="00ae6-110">Дополнительные сведения см. [в статье configure Network regions for CAC в Lync Server 2013](lync-server-2013-configure-network-regions-for-cac.md).</span><span class="sxs-lookup"><span data-stu-id="00ae6-110">For details, see [Configure network regions for CAC in Lync Server 2013](lync-server-2013-configure-network-regions-for-cac.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="00ae6-111">Все специальные требования в отношении определений области сети для конкретных компонентов указаны в документации по развертыванию данных компонентов.</span><span class="sxs-lookup"><span data-stu-id="00ae6-111">Any feature-specific requirements for network region definitions are documented in the Deployment topics for the feature.</span></span>



</div>

<span data-ttu-id="00ae6-112">Для получения подробных сведений о работе с областями сети обратитесь к документации по командной консоли Lync Server для следующих командлетов:</span><span class="sxs-lookup"><span data-stu-id="00ae6-112">For details about working with network regions, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - [<span data-ttu-id="00ae6-113">New — CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="00ae6-113">New-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegion)

  - [<span data-ttu-id="00ae6-114">Get — CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="00ae6-114">Get-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink)

  - [<span data-ttu-id="00ae6-115">Set — CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="00ae6-115">Set-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkRegion)

  - [<span data-ttu-id="00ae6-116">Remove — CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="00ae6-116">Remove-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkRegion)

<div>

## <a name="create-a-network-region"></a><span data-ttu-id="00ae6-117">Создание области сети</span><span class="sxs-lookup"><span data-stu-id="00ae6-117">Create a Network Region</span></span>

<span data-ttu-id="00ae6-118">Создание области сети, которая может использоваться службой контроля допуска звонков, службой E9-1-1 или при обходе сервера-посредника.</span><span class="sxs-lookup"><span data-stu-id="00ae6-118">Create a network region that can be used by call admission control, E9-1-1, or media bypass.</span></span>

<div>

## <a name="to-create-a-network-region-using-lync-server-management-shell"></a><span data-ttu-id="00ae6-119">Создание области сети с помощью консоли управления Lync Server</span><span class="sxs-lookup"><span data-stu-id="00ae6-119">To create a network region using Lync Server Management Shell</span></span>

1.  <span data-ttu-id="00ae6-120">Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="00ae6-120">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="00ae6-121">Чтобы создать области сети, используйте командлет New-CsNetworkRegion.</span><span class="sxs-lookup"><span data-stu-id="00ae6-121">Run the New-CsNetworkRegion cmdlet to create network regions:</span></span>
    
        New-CsNetworkRegion -Identity <String> -CentralSite <String>
    
    <span data-ttu-id="00ae6-122">Пример:</span><span class="sxs-lookup"><span data-stu-id="00ae6-122">For example:</span></span>
    
        New-CsNetworkRegion -Identity NorthAmerica -CentralSite CHICAGO -Description "All North America Locations"
    
    <span data-ttu-id="00ae6-123">В этом примере показано создание области сети "NorthAmerica", которая связана с центральным сайтом с ИД CHICAGO.</span><span class="sxs-lookup"><span data-stu-id="00ae6-123">In this example, you created a network region called “NorthAmerica” that is associated with a central site with site ID CHICAGO.</span></span>

3.  <span data-ttu-id="00ae6-124">Чтобы завершить создание областей сети для вашей топологии, повторите шаг 2, указав требуемые параметры для каждой области сети.</span><span class="sxs-lookup"><span data-stu-id="00ae6-124">To finish creating network regions for your topology, repeat step 2 with settings for each network region.</span></span>

</div>

<div>

## <a name="to-create-a-network-region-using-lync-server-control-panel"></a><span data-ttu-id="00ae6-125">Создание области сети с помощью панели управления Lync Server</span><span class="sxs-lookup"><span data-stu-id="00ae6-125">To create a network region using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="00ae6-126">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="00ae6-126">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="00ae6-127">Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="00ae6-127">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

2.  <span data-ttu-id="00ae6-128">В левой панели навигации щелкните **Network Configuration** (Параметры сети).</span><span class="sxs-lookup"><span data-stu-id="00ae6-128">In the left navigation bar, click **Network Configuration**.</span></span>

3.  <span data-ttu-id="00ae6-129">Щелкните **Region** (Область).</span><span class="sxs-lookup"><span data-stu-id="00ae6-129">Click **Region**.</span></span>

4.  <span data-ttu-id="00ae6-130">Щелкните **New** (Создать).</span><span class="sxs-lookup"><span data-stu-id="00ae6-130">Click **New**.</span></span>

5.  <span data-ttu-id="00ae6-131">На странице **New Region** (Создание области) введите имя области сети в поле **Name** (Имя).</span><span class="sxs-lookup"><span data-stu-id="00ae6-131">On the **New Region** page, click **Name** and then type a name for the network region.</span></span>

6.  <span data-ttu-id="00ae6-132">Щелкните **Central site** (Центральный сайт) и затем выберите центральный сайт в списке.</span><span class="sxs-lookup"><span data-stu-id="00ae6-132">Click **Central site**, and then click a central site in the list.</span></span>

7.  <span data-ttu-id="00ae6-133">В поле **Description** (Описание) введите дополнительные сведения об области сети (необязательно).</span><span class="sxs-lookup"><span data-stu-id="00ae6-133">Optionally, click **Description**, and then type additional information to describe this network site.</span></span>

8.  <span data-ttu-id="00ae6-134">Щелкните **Commit** (Применить).</span><span class="sxs-lookup"><span data-stu-id="00ae6-134">Click **Commit**.</span></span>

9.  <span data-ttu-id="00ae6-135">Чтобы завершить создание областей сети для вашей топологии, повторите шаги с 4 по 8, указав требуемые параметры для остальных областей.</span><span class="sxs-lookup"><span data-stu-id="00ae6-135">To finish creating network regions for your topology, repeat steps 4 through 8 with settings for other regions.</span></span>

</div>

</div>

<div>

## <a name="modify-a-network-region"></a><span data-ttu-id="00ae6-136">Изменение области сети</span><span class="sxs-lookup"><span data-stu-id="00ae6-136">Modify a Network Region</span></span>

<span data-ttu-id="00ae6-137">Изменение параметров существующей области сети в соответствии с изменениями основных сведений об области сети или требованиями новой функции.</span><span class="sxs-lookup"><span data-stu-id="00ae6-137">Modify settings for an existing network region to accommodate changes to the basic region information or changes required by a new feature.</span></span>

<div>

## <a name="to-modify-a-network-region-using-lync-server-management-shell"></a><span data-ttu-id="00ae6-138">Изменение области сети с помощью командной консоли Lync Server</span><span class="sxs-lookup"><span data-stu-id="00ae6-138">To modify a network region using Lync Server Management Shell</span></span>

1.  <span data-ttu-id="00ae6-139">Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="00ae6-139">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="00ae6-140">Чтобы изменить существующую область сети, выполните командлет Set-CsNetworkRegion.</span><span class="sxs-lookup"><span data-stu-id="00ae6-140">Run the Set-CsNetworkRegion cmdlet to modify an existing network region:</span></span>
    
        Set-CsNetworkRegion -Identity <String> -CentralSite <String>
    
    <span data-ttu-id="00ae6-141">Пример:</span><span class="sxs-lookup"><span data-stu-id="00ae6-141">For example:</span></span>
    
        Set-CsNetworkRegion -Identity NorthAmerica -CentralSite CHICAGO -Description "North American Region"
    
    <span data-ttu-id="00ae6-p103">В этом примере показано изменение описания области сети "NorthAmerica", созданной ранее. Если для области "NorthAmerica" описание уже задано, оно будет перезаписано; в противном случае описание будет задано.</span><span class="sxs-lookup"><span data-stu-id="00ae6-p103">In this example, you modified an existing network region called “NorthAmerica” (created using the procedures earlier in this topic) by changing the description. If a description existed for the “NorthAmerica” region, this command overwrites it with this value; if no description had been set, then this command sets it.</span></span>

3.  <span data-ttu-id="00ae6-144">Чтобы изменить остальные области сети, повторите шаг 2, указав параметры для остальных областей.</span><span class="sxs-lookup"><span data-stu-id="00ae6-144">To modify other network regions, repeat step 2 with settings for other regions.</span></span>

</div>

<div>

## <a name="to-modify-a-network-region-using-lync-server-control-panel"></a><span data-ttu-id="00ae6-145">Изменение области сети с помощью панели управления Lync Server</span><span class="sxs-lookup"><span data-stu-id="00ae6-145">To modify a network region using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="00ae6-146">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="00ae6-146">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="00ae6-147">Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="00ae6-147">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

2.  <span data-ttu-id="00ae6-148">В левой панели навигации щелкните **Network Configuration** (Параметры сети).</span><span class="sxs-lookup"><span data-stu-id="00ae6-148">In the left navigation bar, click **Network Configuration**.</span></span>

3.  <span data-ttu-id="00ae6-149">Нажмите кнопку навигации **Region** (Область).</span><span class="sxs-lookup"><span data-stu-id="00ae6-149">Click the **Region** navigation button.</span></span>

4.  <span data-ttu-id="00ae6-150">В таблице щелкните область сети, которую требуется изменить.</span><span class="sxs-lookup"><span data-stu-id="00ae6-150">In the table, click the network region that you want to modify.</span></span>

5.  <span data-ttu-id="00ae6-151">Щелкните **Edit** (Изменить) и затем щелкните **Show details** (Показать сведения).</span><span class="sxs-lookup"><span data-stu-id="00ae6-151">Click **Edit**, and then click **Show details…**.</span></span>

6.  <span data-ttu-id="00ae6-152">На странице **Edit Region** (Изменение области) измените требуемые параметры области сети.</span><span class="sxs-lookup"><span data-stu-id="00ae6-152">On the **Edit Region** page, change the values for this network region’s settings as appropriate.</span></span>

7.  <span data-ttu-id="00ae6-153">Щелкните **Commit** (Применить).</span><span class="sxs-lookup"><span data-stu-id="00ae6-153">Click **Commit**.</span></span>

8.  <span data-ttu-id="00ae6-154">Чтобы завершить изменение областей сети, повторите шаги 4–7, используя параметры для других областей.</span><span class="sxs-lookup"><span data-stu-id="00ae6-154">To finish modify network regions, repeat steps 4 through 7 with settings for other regions.</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

