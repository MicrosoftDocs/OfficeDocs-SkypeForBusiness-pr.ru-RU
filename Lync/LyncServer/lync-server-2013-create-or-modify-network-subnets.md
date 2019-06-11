---
title: 'Lync Server 2013: создание и изменение подсетей сети'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create or modify network subnets
ms:assetid: 1ba8c4e3-fbc7-4758-88ac-d651fef17bed
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520957(v=OCS.15)
ms:contentKeyID: 48183548
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f27088b59745bac580990b3e898f485d34dcad57
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834783"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-network-subnets-in-lync-server-2013"></a><span data-ttu-id="647ab-102">Создание и изменение подсетей сети в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="647ab-102">Create or modify network subnets in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="647ab-103">_**Тема последнего изменения:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="647ab-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="647ab-104">Сетевая подсеть должна быть связана с сетевым сайтом в целях определения географического расположения узла, принадлежащего данной подсети.</span><span class="sxs-lookup"><span data-stu-id="647ab-104">A network subnet must be associated with a network site for the purposes of determining the geographic location of the host belonging to this subnet.</span></span> <span data-ttu-id="647ab-105">Вы можете настроить подсети с помощью панели управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="647ab-105">You can use Lync Server Control Panel to configure subnets.</span></span> <span data-ttu-id="647ab-106">С помощью панели управления Lync Server вы можете создавать, изменять и удалять сетевые подсети.</span><span class="sxs-lookup"><span data-stu-id="647ab-106">From the Lync Server Control Panel, you can create, modify, or delete a network subnet.</span></span> <span data-ttu-id="647ab-107">Подробнее об удалении подсетей сети можно узнать в разделе Удаление подсетей сети [в Lync Server 2013](lync-server-2013-deleting-network-subnets.md).</span><span class="sxs-lookup"><span data-stu-id="647ab-107">For details about deleting network subnets, see [Deleting network subnets in Lync Server 2013](lync-server-2013-deleting-network-subnets.md).</span></span>

<span data-ttu-id="647ab-108">В большинстве развертываний Microsoft Lync Server 2013 там, где реализовано управление допуском звонков (CAC), обычно это большое количество подсетей.</span><span class="sxs-lookup"><span data-stu-id="647ab-108">In most deployments of Microsoft Lync Server 2013 where call admission control (CAC) is implemented, there will typically be a large number of subnets.</span></span> <span data-ttu-id="647ab-109">По этой причине лучше всего настроить подсети из командной консоли Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="647ab-109">Because of this, it is often best to configure subnets from the Lync Server Management Shell.</span></span> <span data-ttu-id="647ab-110">Из него вы можете вызвать **New-кснетворксубнет** в сочетании с командлетом Windows PowerShell **Import-CSV**.</span><span class="sxs-lookup"><span data-stu-id="647ab-110">From there you can call **New-CsNetworkSubnet** in conjunction with the Windows PowerShell cmdlet **Import-CSV**.</span></span> <span data-ttu-id="647ab-111">Используя эти командлеты вместе, вы можете прочитать параметры подсети из CSV-файла и одновременно создать несколько подсетей.</span><span class="sxs-lookup"><span data-stu-id="647ab-111">By using these cmdlets together, you can read in subnet settings from a comma-separated values (.csv) file and create multiple subnets at the same time.</span></span> <span data-ttu-id="647ab-112">Примеры создания подсетей из CSV-файла можно найти в разделе [New-кснетворксубнет](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet).</span><span class="sxs-lookup"><span data-stu-id="647ab-112">For examples of how to create subnets from a .csv file, see [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet).</span></span>

<div>

## <a name="to-create-a-network-subnet"></a><span data-ttu-id="647ab-113">Создание сетевой подсети</span><span class="sxs-lookup"><span data-stu-id="647ab-113">To create a network subnet</span></span>

1.  <span data-ttu-id="647ab-114">Войдите на любой компьютер, находящийся во внутреннем развертывании, с использованием учетной записи, входящей в группу RTCUniversalServerAdmins (или имеющей равнозначные права пользователя) либо назначенной роли CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="647ab-114">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="647ab-115">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="647ab-115">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="647ab-116">Дополнительные сведения о различных способах, которые можно использовать для запуска панели управления Lync Server, приведены в разделе [Открытие меню администрирования Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="647ab-116">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="647ab-117">На панели навигации слева выберите пункт **Настройка сети** , а затем — **подсеть**.</span><span class="sxs-lookup"><span data-stu-id="647ab-117">In the left navigation bar, click **Network Configuration** and then click **Subnet**.</span></span>

4.  <span data-ttu-id="647ab-118">На странице \*\*\*\* "подсеть" нажмите кнопку " **создать**".</span><span class="sxs-lookup"><span data-stu-id="647ab-118">On the **Subnet** page, click **New**.</span></span>

5.  <span data-ttu-id="647ab-119">В разделе **Новая подсеть**введите значение в поле **код подсети** .</span><span class="sxs-lookup"><span data-stu-id="647ab-119">In **New Subnet**, enter a value in the **Subnet ID** field.</span></span> <span data-ttu-id="647ab-120">Это должен быть IP-адрес (например, 174.11.12.0), и он должен быть первым адресом в диапазоне IP-адресов, определенном подсетью.</span><span class="sxs-lookup"><span data-stu-id="647ab-120">This must be an IP address (for example, 174.11.12.0), and it must be the first address in the IP address range defined by the subnet.</span></span>

6.  <span data-ttu-id="647ab-121">В поле " **Маска** " введите числовое значение от 1 до 32.</span><span class="sxs-lookup"><span data-stu-id="647ab-121">In the **Mask** field, enter a numeric value from 1 through 32.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="647ab-122">Это значение — битовая маска, применяемая к создаваемой подсети.</span><span class="sxs-lookup"><span data-stu-id="647ab-122">This value is the bitmask that is to be applied to the subnet being created.</span></span>

    
    </div>

7.  <span data-ttu-id="647ab-123">В поле " **код сайта сети**" выберите сайт, к которому относится эта подсеть.</span><span class="sxs-lookup"><span data-stu-id="647ab-123">In **Network site ID**, select the site to which this subnet belongs.</span></span>

8.  <span data-ttu-id="647ab-124">Необязательно Введите значение в поле **Описание** , чтобы получить дополнительные сведения о подсети, которые нельзя выразить только именем.</span><span class="sxs-lookup"><span data-stu-id="647ab-124">(Optional) Type a value in the **Description** field to provide more information about this subnet that cannot be expressed by the name alone.</span></span>

9.  <span data-ttu-id="647ab-125">Нажмите **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="647ab-125">Click **Commit**.</span></span>

</div>

<div>

## <a name="to-modify-a-network-subnet"></a><span data-ttu-id="647ab-126">Изменение подсети сети</span><span class="sxs-lookup"><span data-stu-id="647ab-126">To modify a network subnet</span></span>

1.  <span data-ttu-id="647ab-127">Войдите на любой компьютер, находящийся во внутреннем развертывании, с использованием учетной записи, входящей в группу RTCUniversalServerAdmins (или имеющей равнозначные права пользователя) либо назначенной роли CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="647ab-127">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="647ab-128">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="647ab-128">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="647ab-129">Дополнительные сведения о различных способах, которые можно использовать для запуска панели управления Lync Server, приведены в разделе [Открытие меню администрирования Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="647ab-129">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="647ab-130">На панели навигации слева выберите пункт **Настройка сети** , а затем — **подсеть**.</span><span class="sxs-lookup"><span data-stu-id="647ab-130">In the left navigation bar, click **Network Configuration** and then click **Subnet**.</span></span>

4.  <span data-ttu-id="647ab-131">На странице **Subnet** (подсеть) выберите подсеть, которую вы хотите изменить.</span><span class="sxs-lookup"><span data-stu-id="647ab-131">On the **Subnet** page, click the subnet that you want to modify.</span></span>

5.  <span data-ttu-id="647ab-132">В меню **Правка** щелкните **Подробнее**.</span><span class="sxs-lookup"><span data-stu-id="647ab-132">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="647ab-133">На странице **Изменение подсети** вы можете изменить битовую маску, связанный сетевой сайт или описание.</span><span class="sxs-lookup"><span data-stu-id="647ab-133">On the **Edit Subnet** page, you can modify the bitmask, associated network site, or description.</span></span> <span data-ttu-id="647ab-134">Если вы измените битовую маску, имейте в виду, что идентификатор подсети по-прежнему должен быть первым в диапазоне IP-адресов, определенном подсетью.</span><span class="sxs-lookup"><span data-stu-id="647ab-134">If you modify the bitmask, keep in mind that the Subnet ID must still be the first address in the IP address range defined by the subnet.</span></span>

7.  <span data-ttu-id="647ab-135">Нажмите **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="647ab-135">Click **Commit**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="647ab-136">См. также</span><span class="sxs-lookup"><span data-stu-id="647ab-136">See Also</span></span>


[<span data-ttu-id="647ab-137">Удаление подсетей сети в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="647ab-137">Deleting network subnets in Lync Server 2013</span></span>](lync-server-2013-deleting-network-subnets.md)  


[<span data-ttu-id="647ab-138">О сетевых областях, сайтах и подсетях в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="647ab-138">About network regions, sites, and subnets in Lync Server 2013</span></span>](lync-server-2013-about-network-regions-sites-and-subnets.md)  


[<span data-ttu-id="647ab-139">New-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="647ab-139">New-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet)  
[<span data-ttu-id="647ab-140">Set-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="647ab-140">Set-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkSubnet)  
[<span data-ttu-id="647ab-141">Remove-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="647ab-141">Remove-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkSubnet)  
[<span data-ttu-id="647ab-142">Get-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="647ab-142">Get-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSubnet)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

