---
title: Управление подсетями
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: В большинстве развертываний Скайп для Business Server, где реализуется контроля допуска звонков (CAC) как правило будет большое число подсети. Таким образом чаще всего наиболее Настройка подсетей с Скайп для консоли Business Server.
ms.openlocfilehash: 7b09428f3bdc44f8626cac072b5f4838e08f9efc
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "33913358"
---
# <a name="managing-network-subnets-in-skype-for-business-server"></a><span data-ttu-id="cadfc-104">Управление подсетями в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="cadfc-104">Managing network subnets in Skype for Business Server</span></span>

<span data-ttu-id="cadfc-105">Можно использовать либо Скайп для панели управления Business Server или Скайп для консоли Business Server для управления подсетей.</span><span class="sxs-lookup"><span data-stu-id="cadfc-105">You can use either the Skype for Business Server Control Panel or the Skype for Business Server Management Shell to manage network subnets.</span></span> <span data-ttu-id="cadfc-106">В большинстве развертываний Скайп для Business Server, где реализуется контроля допуска звонков (CAC) как правило будет большое число подсети.</span><span class="sxs-lookup"><span data-stu-id="cadfc-106">In most deployments of Skype for Business Server where call admission control (CAC) is implemented, there will typically be a large number of subnets.</span></span> <span data-ttu-id="cadfc-107">Таким образом чаще всего наиболее Настройка подсетей с Скайп для консоли Business Server.</span><span class="sxs-lookup"><span data-stu-id="cadfc-107">Because of this, it is often best to configure subnets from the Skype for Business Server Management Shell.</span></span>

<span data-ttu-id="cadfc-108">Используйте разделы в этой статье для просмотра сведений о подсети или создание, изменение и удаление подсетей.</span><span class="sxs-lookup"><span data-stu-id="cadfc-108">Use the sections in this article to view network subnet information or create, modify, or delete network subnets.</span></span> 

## <a name="view-network-subnet-information"></a><span data-ttu-id="cadfc-109">Просмотр сведений о подсети</span><span class="sxs-lookup"><span data-stu-id="cadfc-109">View network subnet information</span></span> 

<span data-ttu-id="cadfc-110">Можно использовать следующую процедуру, чтобы просмотреть подсеть.</span><span class="sxs-lookup"><span data-stu-id="cadfc-110">You can use the following procedure to view a network subnet.</span></span> <span data-ttu-id="cadfc-111">Из Скайп для панели управления Business Server создание, изменение или удаление подсети.</span><span class="sxs-lookup"><span data-stu-id="cadfc-111">From the Skype for Business Server Control Panel, you can create, modify, or delete a network subnet.</span></span> 

### <a name="to-view-a-network-subnet"></a><span data-ttu-id="cadfc-112">Чтобы просмотреть подсеть</span><span class="sxs-lookup"><span data-stu-id="cadfc-112">To view a network subnet</span></span>

1.  <span data-ttu-id="cadfc-113">Войдите на любой компьютер, находящийся во внутреннем развертывании, с использованием учетной записи, входящей в группу RTCUniversalServerAdmins (или имеющей равнозначные права пользователя) либо назначенной роли CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="cadfc-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="cadfc-114">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть Скайп для панели управления Business Server.</span><span class="sxs-lookup"><span data-stu-id="cadfc-114">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="cadfc-115">В левой панели навигации щелкните **Конфигурация сети**и выберите команду **подсети**.</span><span class="sxs-lookup"><span data-stu-id="cadfc-115">In the left navigation bar, click **Network Configuration**, and then click **Subnet**.</span></span>

4.  <span data-ttu-id="cadfc-116">На странице **подсеть** щелкните подсеть, который требуется просмотреть.</span><span class="sxs-lookup"><span data-stu-id="cadfc-116">On the **Subnet** page, click the subnet that you want to view.</span></span>
 
    > [!NOTE]  
    > <span data-ttu-id="cadfc-117">Можно просматривать только одну подсеть.</span><span class="sxs-lookup"><span data-stu-id="cadfc-117">You can only view one subnet at a time.</span></span>

5.  <span data-ttu-id="cadfc-118">В меню **Правка** щелкните **Подробнее**.</span><span class="sxs-lookup"><span data-stu-id="cadfc-118">On the **Edit** menu, click **Show details**.</span></span>

### <a name="view-network-subnet-configuration-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="cadfc-119">Просмотр сведений о конфигурации подсети с командлетов с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="cadfc-119">View network subnet configuration information by Using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="cadfc-120">Можно просматривать сведения о подсети сети с помощью командлета Get-CsNetworkSubnet и Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="cadfc-120">Network subnet information can be viewed by using Windows PowerShell and the Get-CsNetworkSubnet cmdlet.</span></span> <span data-ttu-id="cadfc-121">Этот командлет можно запустить из Скайп для консоли Business Server или из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="cadfc-121">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

### <a name="to-view-network-subnet-information"></a><span data-ttu-id="cadfc-122">Для просмотра сведений о подсети</span><span class="sxs-lookup"><span data-stu-id="cadfc-122">To view network subnet information</span></span>

  - <span data-ttu-id="cadfc-123">Чтобы просмотреть сведения обо всех подсетях, введите следующую команду в Скайп для консоли Business Server и нажмите клавишу ВВОД:</span><span class="sxs-lookup"><span data-stu-id="cadfc-123">To view information about all your network subnets, type the following command in the Skype for Business Server Management Shell and then press ENTER:</span></span>
    
        Get-CsNetworkSubnet
    
    <span data-ttu-id="cadfc-124">Команда возвращает примерно следующую информацию:</span><span class="sxs-lookup"><span data-stu-id="cadfc-124">That will return information similar to this:</span></span>
    
        Identity      : 172.11.15.0
        MaskBits      : 28
        Description   :
        NetworkSiteID : Redmond
        SubnetID      : 172.11.15.0


<span data-ttu-id="cadfc-125">Для получения дополнительных сведений см раздел справки для командлета [Get-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSubnet) .</span><span class="sxs-lookup"><span data-stu-id="cadfc-125">For more information, see the help topic for the [Get-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSubnet) cmdlet.</span></span>


## <a name="create-or-modify-network-subnets"></a><span data-ttu-id="cadfc-126">Создание или изменение подсетей</span><span class="sxs-lookup"><span data-stu-id="cadfc-126">Create or modify network subnets</span></span> 

<span data-ttu-id="cadfc-127">Подсети должен быть связан с сетевым узлом в целях определения географическое положение узла, относящегося к данной подсети.</span><span class="sxs-lookup"><span data-stu-id="cadfc-127">A network subnet must be associated with a network site for the purposes of determining the geographic location of the host belonging to this subnet.</span></span> <span data-ttu-id="cadfc-128">Скайп для панели управления Business Server можно использовать для настройки подсети.</span><span class="sxs-lookup"><span data-stu-id="cadfc-128">You can use the Skype for Business Server Control Panel to configure subnets.</span></span> <span data-ttu-id="cadfc-129">Из Скайп для панели управления Business Server создание, изменение или удаление подсети.</span><span class="sxs-lookup"><span data-stu-id="cadfc-129">From the Skype for Business Server Control Panel, you can create, modify, or delete a network subnet.</span></span> 

<span data-ttu-id="cadfc-130">В большинстве развертываний Скайп для Business Server, где реализуется контроля допуска звонков (CAC) как правило будет большое число подсети.</span><span class="sxs-lookup"><span data-stu-id="cadfc-130">In most deployments of Skype for Business Server where call admission control (CAC) is implemented, there will typically be a large number of subnets.</span></span> <span data-ttu-id="cadfc-131">Таким образом чаще всего наиболее Настройка подсетей с Скайп для консоли Business Server.</span><span class="sxs-lookup"><span data-stu-id="cadfc-131">Because of this, it is often best to configure subnets from the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="cadfc-132">Отсюда можно вызвать **New-CsNetworkSubnet** в сочетании с помощью командлета Windows PowerShell **Import-CSV**.</span><span class="sxs-lookup"><span data-stu-id="cadfc-132">From there you can call **New-CsNetworkSubnet** in conjunction with the Windows PowerShell cmdlet **Import-CSV**.</span></span> <span data-ttu-id="cadfc-133">При совместном использовании эти командлеты можно читать в параметрах подсети из файла с разделителями-запятыми (CSV) и создавать несколько подсетей в то же время.</span><span class="sxs-lookup"><span data-stu-id="cadfc-133">By using these cmdlets together, you can read in subnet settings from a comma-separated values (.csv) file and create multiple subnets at the same time.</span></span> <span data-ttu-id="cadfc-134">Примеры того, как создание подсети из CSV-файла в разделе [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet).</span><span class="sxs-lookup"><span data-stu-id="cadfc-134">For examples of how to create subnets from a .csv file, see [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet).</span></span>


### <a name="to-create-a-network-subnet"></a><span data-ttu-id="cadfc-135">Создание подсети</span><span class="sxs-lookup"><span data-stu-id="cadfc-135">To create a network subnet</span></span>

1.  <span data-ttu-id="cadfc-136">Войдите на любой компьютер, находящийся во внутреннем развертывании, с использованием учетной записи, входящей в группу RTCUniversalServerAdmins (или имеющей равнозначные права пользователя) либо назначенной роли CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="cadfc-136">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="cadfc-137">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть Скайп для панели управления Business Server.</span><span class="sxs-lookup"><span data-stu-id="cadfc-137">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="cadfc-138">В левой панели навигации щелкните **Конфигурация сети**и выберите команду **подсети**.</span><span class="sxs-lookup"><span data-stu-id="cadfc-138">In the left navigation bar, click **Network Configuration**, and then click **Subnet**.</span></span>

4.  <span data-ttu-id="cadfc-139">На странице **подсеть** щелкните **Создать**.</span><span class="sxs-lookup"><span data-stu-id="cadfc-139">On the **Subnet** page, click **New**.</span></span>

5.  <span data-ttu-id="cadfc-140">В **Новой подсети**введите значение в поле **Subnet ID** .</span><span class="sxs-lookup"><span data-stu-id="cadfc-140">In **New Subnet**, enter a value in the **Subnet ID** field.</span></span> <span data-ttu-id="cadfc-141">Это должен быть IP-адрес (например, 174.11.12.0), и он должен быть первый адрес в диапазон IP-адресов, определенный в подсети.</span><span class="sxs-lookup"><span data-stu-id="cadfc-141">This must be an IP address (for example, 174.11.12.0), and it must be the first address in the IP address range defined by the subnet.</span></span>

6.  <span data-ttu-id="cadfc-142">В поле **Mask** введите числовое значение от 1 до 32.</span><span class="sxs-lookup"><span data-stu-id="cadfc-142">In the **Mask** field, enter a numeric value from 1 through 32.</span></span>

    > [!NOTE]  
    > <span data-ttu-id="cadfc-143">Это значение — Битовая маска, применяемая к создаваемой подсети.</span><span class="sxs-lookup"><span data-stu-id="cadfc-143">This value is the bitmask that is to be applied to the subnet being created.</span></span>

7.  <span data-ttu-id="cadfc-144">В **ИД сетевого узла**выберите сайт, к которому относится данная подсеть.</span><span class="sxs-lookup"><span data-stu-id="cadfc-144">In **Network site ID**, select the site to which this subnet belongs.</span></span>

8.  <span data-ttu-id="cadfc-145">(Необязательно) Введите значение в поле **Описание** , чтобы предоставить дополнительную информацию о данной подсети, которые не могут быть выражены одним именем.</span><span class="sxs-lookup"><span data-stu-id="cadfc-145">(Optional) Type a value in the **Description** field to provide more information about this subnet that cannot be expressed by the name alone.</span></span>

9.  <span data-ttu-id="cadfc-146">Нажмите **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="cadfc-146">Click **Commit**.</span></span>


### <a name="to-modify-a-network-subnet"></a><span data-ttu-id="cadfc-147">Изменение подсети</span><span class="sxs-lookup"><span data-stu-id="cadfc-147">To modify a network subnet</span></span>

1.  <span data-ttu-id="cadfc-148">Войдите на любой компьютер, находящийся во внутреннем развертывании, с использованием учетной записи, входящей в группу RTCUniversalServerAdmins (или имеющей равнозначные права пользователя) либо назначенной роли CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="cadfc-148">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="cadfc-149">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть Скайп для панели управления Business Server.</span><span class="sxs-lookup"><span data-stu-id="cadfc-149">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="cadfc-150">В левой панели навигации щелкните **Конфигурация сети**и выберите команду **подсети**.</span><span class="sxs-lookup"><span data-stu-id="cadfc-150">In the left navigation bar, click **Network Configuration**, and then click **Subnet**.</span></span>

4.  <span data-ttu-id="cadfc-151">На странице **подсеть** щелкните подсеть, которую требуется изменить.</span><span class="sxs-lookup"><span data-stu-id="cadfc-151">On the **Subnet** page, click the subnet that you want to modify.</span></span>

5.  <span data-ttu-id="cadfc-152">В меню **Правка** щелкните **Подробнее**.</span><span class="sxs-lookup"><span data-stu-id="cadfc-152">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="cadfc-153">На странице " **Изменение подсети** " можно изменить Битовая маска, связанные с ними сетевой узел или описание.</span><span class="sxs-lookup"><span data-stu-id="cadfc-153">On the **Edit Subnet** page, you can modify the bitmask, associated network site, or description.</span></span> <span data-ttu-id="cadfc-154">При изменении Битовая маска, которая помните, что идентификатор подсети по-прежнему должен быть первый адрес в диапазон IP-адресов, определенный в подсети.</span><span class="sxs-lookup"><span data-stu-id="cadfc-154">If you modify the bitmask, keep in mind that the Subnet ID must still be the first address in the IP address range defined by the subnet.</span></span>

7.  <span data-ttu-id="cadfc-155">Нажмите **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="cadfc-155">Click **Commit**.</span></span>

## <a name="delete-network-subnets"></a><span data-ttu-id="cadfc-156">Удаление подсетей</span><span class="sxs-lookup"><span data-stu-id="cadfc-156">Delete network subnets</span></span>

<span data-ttu-id="cadfc-157">Можно использовать следующую процедуру для удаления подсети.</span><span class="sxs-lookup"><span data-stu-id="cadfc-157">You can use the following procedure to delete a subnet.</span></span> <span data-ttu-id="cadfc-158">Из Скайп для панели управления Business Server создание, изменение или удаление подсети.</span><span class="sxs-lookup"><span data-stu-id="cadfc-158">From the Skype for Business Server Control Panel, you can create, modify, or delete a network subnet.</span></span> 

<span data-ttu-id="cadfc-159">В большинстве развертываний Скайп для Business Server, где реализуется контроля допуска звонков (CAC) как правило будет большое число подсети.</span><span class="sxs-lookup"><span data-stu-id="cadfc-159">In most deployments of Skype for Business Server where call admission control (CAC) is implemented, there will typically be a large number of subnets.</span></span> <span data-ttu-id="cadfc-160">Таким образом чаще всего наиболее Настройка подсетей с Скайп для консоли Business Server.</span><span class="sxs-lookup"><span data-stu-id="cadfc-160">Because of this, it is often best to configure subnets from the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="cadfc-161">Отсюда можно вызвать **New-CsNetworkSubnet** в сочетании с помощью командлета Windows PowerShell **Import-CSV**.</span><span class="sxs-lookup"><span data-stu-id="cadfc-161">From there you can call **New-CsNetworkSubnet** in conjunction with the Windows PowerShell cmdlet **Import-CSV**.</span></span> <span data-ttu-id="cadfc-162">При совместном использовании эти командлеты можно читать в параметрах подсети из файла с разделителями-запятыми (CSV) и создавать несколько подсетей в то же время.</span><span class="sxs-lookup"><span data-stu-id="cadfc-162">By using these cmdlets together, you can read in subnet settings from a comma-separated values (.csv) file and create multiple subnets at the same time.</span></span> <span data-ttu-id="cadfc-163">Примеры того, как создание подсети из CSV-файла в разделе [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet).</span><span class="sxs-lookup"><span data-stu-id="cadfc-163">For examples of how to create subnets from a .csv file, see [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet).</span></span>


### <a name="to-delete-a-network-subnet"></a><span data-ttu-id="cadfc-164">Удаление подсети</span><span class="sxs-lookup"><span data-stu-id="cadfc-164">To delete a network subnet</span></span>

1.  <span data-ttu-id="cadfc-165">Войдите на любой компьютер, находящийся во внутреннем развертывании, с использованием учетной записи, входящей в группу RTCUniversalServerAdmins (или имеющей равнозначные права пользователя) либо назначенной роли CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="cadfc-165">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="cadfc-166">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть Скайп для панели управления Business Server.</span><span class="sxs-lookup"><span data-stu-id="cadfc-166">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="cadfc-167">В левой панели навигации щелкните **Конфигурация сети**и выберите команду **подсети**.</span><span class="sxs-lookup"><span data-stu-id="cadfc-167">In the left navigation bar, click **Network Configuration**, and then click **Subnet**.</span></span>

4.  <span data-ttu-id="cadfc-168">На странице **подсеть** щелкните подсеть, которую требуется удалить.</span><span class="sxs-lookup"><span data-stu-id="cadfc-168">On the **Subnet** page, click the subnet that you want to delete.</span></span>
 
    > [!NOTE]  
    > <span data-ttu-id="cadfc-169">Одновременно можно удалить несколько подсетей.</span><span class="sxs-lookup"><span data-stu-id="cadfc-169">You can delete more than one subnet at a time.</span></span> <span data-ttu-id="cadfc-170">Для этого нажмите клавишу CTRL и выберите несколько подсетей, удерживая нажатой клавишу CTRL.</span><span class="sxs-lookup"><span data-stu-id="cadfc-170">To do this, press CTRL and select multiple subnets while holding down the CTRL key.</span></span> <span data-ttu-id="cadfc-171">Или, чтобы выбрать все подсети, нажмите кнопку **Выбрать все** в меню **Правка** .</span><span class="sxs-lookup"><span data-stu-id="cadfc-171">Or, to select all subnets, click **Select all** on the **Edit** menu.</span></span>

5.  <span data-ttu-id="cadfc-172">В меню **Правка** выберите пункт **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="cadfc-172">On the **Edit** menu, click **Delete**.</span></span>

6.  <span data-ttu-id="cadfc-173">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="cadfc-173">Click **OK**.</span></span>


## <a name="see-also"></a><span data-ttu-id="cadfc-174">См. также</span><span class="sxs-lookup"><span data-stu-id="cadfc-174">See Also</span></span>

[<span data-ttu-id="cadfc-175">New-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="cadfc-175">New-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet)  

[<span data-ttu-id="cadfc-176">Set-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="cadfc-176">Set-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkSubnet)  

[<span data-ttu-id="cadfc-177">Remove-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="cadfc-177">Remove-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkSubnet)  

[<span data-ttu-id="cadfc-178">Get-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="cadfc-178">Get-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSubnet)  
