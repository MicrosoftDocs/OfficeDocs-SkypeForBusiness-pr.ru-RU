---
title: 'Lync Server 2013: создание или изменение сетевого региона'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create or modify a network region
ms:assetid: bf7a3dc4-71a2-4559-a547-d90305d4f904
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412933(v=OCS.15)
ms:contentKeyID: 48185281
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 21a9b7a8adbb4ca4c0853aa7013662433701201d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834795"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-network-region-in-lync-server-2013"></a><span data-ttu-id="f8c23-102">Создание или изменение сетевого региона в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f8c23-102">Create or modify a network region in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f8c23-103">_**Тема последнего изменения:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="f8c23-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="f8c23-104">*Регионы сетей* — это сетевые разветвители и одинарные кости, используемые в настройке управления допуском звонков, E9-1-1 и мультимедийными пропусками.</span><span class="sxs-lookup"><span data-stu-id="f8c23-104">*Network regions* are the network hubs or backbones used in the configuration of call admission control, E9-1-1, and media bypass.</span></span> <span data-ttu-id="f8c23-105">Для создания и изменения областей сети выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="f8c23-105">Use the following procedures to create or modify network regions.</span></span> <span data-ttu-id="f8c23-106">Например, если вы уже создали сетевые регионы для одной голосовой связи, вам не нужно создавать новые сетевые регионы; другие дополнительные функции для корпоративной голосовой связи будут использовать те же сетевые регионы.</span><span class="sxs-lookup"><span data-stu-id="f8c23-106">For example, if you have already created network regions for one Voice feature, you do not need to create new network regions; other advanced Enterprise Voice features will use those same network regions.</span></span> <span data-ttu-id="f8c23-107">Однако вам может потребоваться изменить существующее определение области сети для применения параметров, относящихся к функции.</span><span class="sxs-lookup"><span data-stu-id="f8c23-107">You may, however, need to modify an existing network region definition to apply feature-specific settings.</span></span> <span data-ttu-id="f8c23-108">Например, если вы создали области сети для службы E9-1-1, для которой не требуется связанный центральный сайт, и затем развернули службу контроля допуска звонков, вам потребуется изменить определения областей сети, чтобы указать центральный сайт.</span><span class="sxs-lookup"><span data-stu-id="f8c23-108">For example, if you have created network regions for E9-1-1 (which do not require an associated central site) and you then deploy call admission control, you need to modify the network region definitions to specify a central site.</span></span> <span data-ttu-id="f8c23-109">Подробности можно найти [в разделе Настройка регионов сети для CAC в Lync Server 2013](lync-server-2013-configure-network-regions-for-cac.md).</span><span class="sxs-lookup"><span data-stu-id="f8c23-109">For details, see [Configure network regions for CAC in Lync Server 2013](lync-server-2013-configure-network-regions-for-cac.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f8c23-110">Любые особые требования к функциональным возможностям для определений сетевых областей описаны в разделе Развертывание для этой функции.</span><span class="sxs-lookup"><span data-stu-id="f8c23-110">Any feature-specific requirements for network region definitions are documented in the Deployment topics for the feature.</span></span>



</div>

<span data-ttu-id="f8c23-111">Дополнительные сведения о работе с сетевыми областями можно найти в документации по оболочке Lync Server Management Shell для следующих командлетов:</span><span class="sxs-lookup"><span data-stu-id="f8c23-111">For details about working with network regions, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - [<span data-ttu-id="f8c23-112">New-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="f8c23-112">New-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegion)

  - [<span data-ttu-id="f8c23-113">Get-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="f8c23-113">Get-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink)

  - [<span data-ttu-id="f8c23-114">Set-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="f8c23-114">Set-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkRegion)

  - [<span data-ttu-id="f8c23-115">Remove-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="f8c23-115">Remove-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkRegion)

<div>

## <a name="create-a-network-region"></a><span data-ttu-id="f8c23-116">Создание сетевого региона</span><span class="sxs-lookup"><span data-stu-id="f8c23-116">Create a Network Region</span></span>

<span data-ttu-id="f8c23-117">Создание сетевого региона, который может использоваться для управления допуском звонков, E9-1-1 или мультимедийного обхода.</span><span class="sxs-lookup"><span data-stu-id="f8c23-117">Create a network region that can be used by call admission control, E9-1-1, or media bypass.</span></span>

<div>

## <a name="to-create-a-network-region-using-lync-server-management-shell"></a><span data-ttu-id="f8c23-118">Создание сетевого региона с помощью командной консоли Lync Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="f8c23-118">To create a network region using Lync Server Management Shell</span></span>

1.  <span data-ttu-id="f8c23-119">Запустите командную консоль Lync Server Management Shell: нажмите кнопку **Пуск**, выберите **все программы**, а затем — **Microsoft Lync Server 2013**, а затем — **Командная консоль Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="f8c23-119">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="f8c23-120">Чтобы создать области сети, используйте командлет New-CsNetworkRegion.</span><span class="sxs-lookup"><span data-stu-id="f8c23-120">Run the New-CsNetworkRegion cmdlet to create network regions:</span></span>
    
        New-CsNetworkRegion -Identity <String> -CentralSite <String>
    
    <span data-ttu-id="f8c23-121">Например:</span><span class="sxs-lookup"><span data-stu-id="f8c23-121">For example:</span></span>
    
        New-CsNetworkRegion -Identity NorthAmerica -CentralSite CHICAGO -Description "All North America Locations"
    
    <span data-ttu-id="f8c23-122">В этом примере показано создание области сети "NorthAmerica", которая связана с центральным сайтом с ИД CHICAGO.</span><span class="sxs-lookup"><span data-stu-id="f8c23-122">In this example, you created a network region called “NorthAmerica” that is associated with a central site with site ID CHICAGO.</span></span>

3.  <span data-ttu-id="f8c23-123">Чтобы завершить создание областей сети для вашей топологии, повторите шаг 2, указав требуемые параметры для каждой области сети.</span><span class="sxs-lookup"><span data-stu-id="f8c23-123">To finish creating network regions for your topology, repeat step 2 with settings for each network region.</span></span>

</div>

<div>

## <a name="to-create-a-network-region-using-lync-server-control-panel"></a><span data-ttu-id="f8c23-124">Создание сетевого региона с помощью панели управления Lync Server</span><span class="sxs-lookup"><span data-stu-id="f8c23-124">To create a network region using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="f8c23-125">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f8c23-125">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="f8c23-126">Дополнительные сведения о различных способах, которые можно использовать для запуска панели управления Lync Server, приведены в разделе [Открытие меню администрирования Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="f8c23-126">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

2.  <span data-ttu-id="f8c23-127">В левой области навигации щелкните элемент **Конфигурация сети**.</span><span class="sxs-lookup"><span data-stu-id="f8c23-127">In the left navigation bar, click **Network Configuration**.</span></span>

3.  <span data-ttu-id="f8c23-128">Щелкните **Область**.</span><span class="sxs-lookup"><span data-stu-id="f8c23-128">Click **Region**.</span></span>

4.  <span data-ttu-id="f8c23-129">Выберите **Создать**.</span><span class="sxs-lookup"><span data-stu-id="f8c23-129">Click **New**.</span></span>

5.  <span data-ttu-id="f8c23-130">На странице **Создание области** введите имя области сети в поле **Имя**.</span><span class="sxs-lookup"><span data-stu-id="f8c23-130">On the **New Region** page, click **Name** and then type a name for the network region.</span></span>

6.  <span data-ttu-id="f8c23-131">Щелкните **Центральный сайт**, затем выберите центральный сайт в списке.</span><span class="sxs-lookup"><span data-stu-id="f8c23-131">Click **Central site**, and then click a central site in the list.</span></span>

7.  <span data-ttu-id="f8c23-132">В поле **Описание** введите дополнительные сведения об области сети (необязательно).</span><span class="sxs-lookup"><span data-stu-id="f8c23-132">Optionally, click **Description**, and then type additional information to describe this network site.</span></span>

8.  <span data-ttu-id="f8c23-133">Нажмите **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="f8c23-133">Click **Commit**.</span></span>

9.  <span data-ttu-id="f8c23-134">Чтобы завершить создание областей сети для вашей топологии, повторите шаги с 4 по 8, указав требуемые параметры для остальных областей.</span><span class="sxs-lookup"><span data-stu-id="f8c23-134">To finish creating network regions for your topology, repeat steps 4 through 8 with settings for other regions.</span></span>

</div>

</div>

<div>

## <a name="modify-a-network-region"></a><span data-ttu-id="f8c23-135">Изменение сетевого региона</span><span class="sxs-lookup"><span data-stu-id="f8c23-135">Modify a Network Region</span></span>

<span data-ttu-id="f8c23-136">Измените параметры существующего сетевого региона, чтобы внести изменения в основные сведения о регионе или изменения, необходимые для новой функции.</span><span class="sxs-lookup"><span data-stu-id="f8c23-136">Modify settings for an existing network region to accommodate changes to the basic region information or changes required by a new feature.</span></span>

<div>

## <a name="to-modify-a-network-region-using-lync-server-management-shell"></a><span data-ttu-id="f8c23-137">Изменение сетевого региона с помощью командной консоли Lync Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="f8c23-137">To modify a network region using Lync Server Management Shell</span></span>

1.  <span data-ttu-id="f8c23-138">Запустите командную консоль Lync Server Management Shell: нажмите кнопку **Пуск**, выберите **все программы**, а затем — **Microsoft Lync Server 2013**, а затем — **Командная консоль Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="f8c23-138">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="f8c23-139">Чтобы изменить существующую область сети, выполните командлет Set-CsNetworkRegion.</span><span class="sxs-lookup"><span data-stu-id="f8c23-139">Run the Set-CsNetworkRegion cmdlet to modify an existing network region:</span></span>
    
        Set-CsNetworkRegion -Identity <String> -CentralSite <String>
    
    <span data-ttu-id="f8c23-140">Например:</span><span class="sxs-lookup"><span data-stu-id="f8c23-140">For example:</span></span>
    
        Set-CsNetworkRegion -Identity NorthAmerica -CentralSite CHICAGO -Description "North American Region"
    
    <span data-ttu-id="f8c23-p103">В этом примере показано изменение описания области сети "NorthAmerica", созданной ранее. Если для области "NorthAmerica" описание уже задано, оно будет перезаписано; в противном случае описание будет задано.</span><span class="sxs-lookup"><span data-stu-id="f8c23-p103">In this example, you modified an existing network region called “NorthAmerica” (created using the procedures earlier in this topic) by changing the description. If a description existed for the “NorthAmerica” region, this command overwrites it with this value; if no description had been set, then this command sets it.</span></span>

3.  <span data-ttu-id="f8c23-143">Чтобы изменить остальные области сети, повторите шаг 2, указав параметры для остальных областей.</span><span class="sxs-lookup"><span data-stu-id="f8c23-143">To modify other network regions, repeat step 2 with settings for other regions.</span></span>

</div>

<div>

## <a name="to-modify-a-network-region-using-lync-server-control-panel"></a><span data-ttu-id="f8c23-144">Изменение сетевого региона с помощью панели управления Lync Server</span><span class="sxs-lookup"><span data-stu-id="f8c23-144">To modify a network region using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="f8c23-145">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f8c23-145">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="f8c23-146">Дополнительные сведения о различных способах, которые можно использовать для запуска панели управления Lync Server, приведены в разделе [Открытие меню администрирования Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="f8c23-146">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

2.  <span data-ttu-id="f8c23-147">В левой области навигации щелкните элемент **Конфигурация сети**.</span><span class="sxs-lookup"><span data-stu-id="f8c23-147">In the left navigation bar, click **Network Configuration**.</span></span>

3.  <span data-ttu-id="f8c23-148">Нажмите кнопку навигации **Область**.</span><span class="sxs-lookup"><span data-stu-id="f8c23-148">Click the **Region** navigation button.</span></span>

4.  <span data-ttu-id="f8c23-149">В таблице щелкните область сети, которую требуется изменить.</span><span class="sxs-lookup"><span data-stu-id="f8c23-149">In the table, click the network region that you want to modify.</span></span>

5.  <span data-ttu-id="f8c23-150">Щелкните **Изменить**, затем щелкните **Подробнее**.</span><span class="sxs-lookup"><span data-stu-id="f8c23-150">Click **Edit**, and then click **Show details…**.</span></span>

6.  <span data-ttu-id="f8c23-151">На странице **Изменение области** измените требуемые параметры области сети.</span><span class="sxs-lookup"><span data-stu-id="f8c23-151">On the **Edit Region** page, change the values for this network region’s settings as appropriate.</span></span>

7.  <span data-ttu-id="f8c23-152">Нажмите **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="f8c23-152">Click **Commit**.</span></span>

8.  <span data-ttu-id="f8c23-153">Чтобы завершить изменение областей сети, повторите шаги 4–7, используя параметры для других областей.</span><span class="sxs-lookup"><span data-stu-id="f8c23-153">To finish modify network regions, repeat steps 4 through 7 with settings for other regions.</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

