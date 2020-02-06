---
title: Управление сетевыми подсетями
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: В большинстве случаев, когда реализовано управление допуском вызовов (CAC) в Skype для бизнеса Server, обычно это большое количество подсетей. По этой причине лучше всего настроить подсети из командной консоли Skype для бизнеса Server.
ms.openlocfilehash: fd7d71b3971b176939967830ca3e071ef4c77dbf
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817468"
---
# <a name="managing-network-subnets-in-skype-for-business-server"></a><span data-ttu-id="61396-104">Управление подсетями в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="61396-104">Managing network subnets in Skype for Business Server</span></span>

<span data-ttu-id="61396-105">Для управления сетевыми подсетями можно использовать серверную панель управления Skype для бизнеса или консоль управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="61396-105">You can use either the Skype for Business Server Control Panel or the Skype for Business Server Management Shell to manage network subnets.</span></span> <span data-ttu-id="61396-106">В большинстве случаев, когда реализовано управление допуском вызовов (CAC) в Skype для бизнеса Server, обычно это большое количество подсетей.</span><span class="sxs-lookup"><span data-stu-id="61396-106">In most deployments of Skype for Business Server where call admission control (CAC) is implemented, there will typically be a large number of subnets.</span></span> <span data-ttu-id="61396-107">По этой причине лучше всего настроить подсети из командной консоли Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="61396-107">Because of this, it is often best to configure subnets from the Skype for Business Server Management Shell.</span></span>

<span data-ttu-id="61396-108">В этой статье описаны разделы, которые можно использовать для просмотра сведений о сетевой подсети, а также для создания, изменения и удаления сетевых подсетей.</span><span class="sxs-lookup"><span data-stu-id="61396-108">Use the sections in this article to view network subnet information or create, modify, or delete network subnets.</span></span> 

## <a name="view-network-subnet-information"></a><span data-ttu-id="61396-109">Просмотр сведений о сетевой подсети</span><span class="sxs-lookup"><span data-stu-id="61396-109">View network subnet information</span></span> 

<span data-ttu-id="61396-110">Вы можете использовать описанную ниже процедуру для просмотра сетевой подсети.</span><span class="sxs-lookup"><span data-stu-id="61396-110">You can use the following procedure to view a network subnet.</span></span> <span data-ttu-id="61396-111">С помощью панели управления Skype для бизнеса Server вы можете создавать, изменять и удалять сетевые подсети.</span><span class="sxs-lookup"><span data-stu-id="61396-111">From the Skype for Business Server Control Panel, you can create, modify, or delete a network subnet.</span></span> 

### <a name="to-view-a-network-subnet"></a><span data-ttu-id="61396-112">Просмотр сетевой подсети</span><span class="sxs-lookup"><span data-stu-id="61396-112">To view a network subnet</span></span>

1.  <span data-ttu-id="61396-113">Войдите на любой компьютер, находящийся во внутреннем развертывании, с использованием учетной записи, входящей в группу RTCUniversalServerAdmins (или имеющей равнозначные права пользователя) либо назначенной роли CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="61396-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="61396-114">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="61396-114">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="61396-115">На панели навигации слева выберите пункт **Настройка сети**, а затем — **подсеть**.</span><span class="sxs-lookup"><span data-stu-id="61396-115">In the left navigation bar, click **Network Configuration**, and then click **Subnet**.</span></span>

4.  <span data-ttu-id="61396-116">На странице **Subnet (подсеть** ) выберите подсеть, которую вы хотите просмотреть.</span><span class="sxs-lookup"><span data-stu-id="61396-116">On the **Subnet** page, click the subnet that you want to view.</span></span>
 
    > [!NOTE]  
    > <span data-ttu-id="61396-117">Вы можете просматривать только одну подсеть за один раз.</span><span class="sxs-lookup"><span data-stu-id="61396-117">You can only view one subnet at a time.</span></span>

5.  <span data-ttu-id="61396-118">В меню **Правка** щелкните **Подробнее**.</span><span class="sxs-lookup"><span data-stu-id="61396-118">On the **Edit** menu, click **Show details**.</span></span>

### <a name="view-network-subnet-configuration-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="61396-119">Просмотр сведений о конфигурации сетевой подсети с помощью командлетов Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="61396-119">View network subnet configuration information by Using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="61396-120">Сведения о сетевой подсети можно просмотреть с помощью Windows PowerShell и командлета Get-Кснетворксубнет.</span><span class="sxs-lookup"><span data-stu-id="61396-120">Network subnet information can be viewed by using Windows PowerShell and the Get-CsNetworkSubnet cmdlet.</span></span> <span data-ttu-id="61396-121">Этот командлет можно выполнить либо из командной консоли Skype для бизнеса Server, либо из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="61396-121">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

### <a name="to-view-network-subnet-information"></a><span data-ttu-id="61396-122">Просмотр сведений о сетевой подсети</span><span class="sxs-lookup"><span data-stu-id="61396-122">To view network subnet information</span></span>

  - <span data-ttu-id="61396-123">Чтобы просмотреть сведения о всех сетевых подсетях, введите в командной консоли Skype для Business Server следующую команду и нажмите клавишу ВВОД:</span><span class="sxs-lookup"><span data-stu-id="61396-123">To view information about all your network subnets, type the following command in the Skype for Business Server Management Shell and then press ENTER:</span></span>
    
        Get-CsNetworkSubnet
    
    <span data-ttu-id="61396-124">Команда возвращает примерно следующую информацию:</span><span class="sxs-lookup"><span data-stu-id="61396-124">That will return information similar to this:</span></span>
    
        Identity      : 172.11.15.0
        MaskBits      : 28
        Description   :
        NetworkSiteID : Redmond
        SubnetID      : 172.11.15.0


<span data-ttu-id="61396-125">Дополнительные сведения можно найти в разделе справки по командлету [Get-кснетворксубнет](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSubnet) .</span><span class="sxs-lookup"><span data-stu-id="61396-125">For more information, see the help topic for the [Get-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSubnet) cmdlet.</span></span>


## <a name="create-or-modify-network-subnets"></a><span data-ttu-id="61396-126">Создание и изменение подсетей сети</span><span class="sxs-lookup"><span data-stu-id="61396-126">Create or modify network subnets</span></span> 

<span data-ttu-id="61396-127">Сетевая подсеть должна быть связана с сетевым сайтом в целях определения географического расположения узла, принадлежащего данной подсети.</span><span class="sxs-lookup"><span data-stu-id="61396-127">A network subnet must be associated with a network site for the purposes of determining the geographic location of the host belonging to this subnet.</span></span> <span data-ttu-id="61396-128">Вы можете настроить подсети с помощью панели управления сервера Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="61396-128">You can use the Skype for Business Server Control Panel to configure subnets.</span></span> <span data-ttu-id="61396-129">С помощью панели управления Skype для бизнеса Server вы можете создавать, изменять и удалять сетевые подсети.</span><span class="sxs-lookup"><span data-stu-id="61396-129">From the Skype for Business Server Control Panel, you can create, modify, or delete a network subnet.</span></span> 

<span data-ttu-id="61396-130">В большинстве случаев, когда реализовано управление допуском вызовов (CAC) в Skype для бизнеса Server, обычно это большое количество подсетей.</span><span class="sxs-lookup"><span data-stu-id="61396-130">In most deployments of Skype for Business Server where call admission control (CAC) is implemented, there will typically be a large number of subnets.</span></span> <span data-ttu-id="61396-131">По этой причине лучше всего настроить подсети из командной консоли Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="61396-131">Because of this, it is often best to configure subnets from the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="61396-132">Из него вы можете вызвать **New-кснетворксубнет** в сочетании с командлетом Windows PowerShell **Import-CSV**.</span><span class="sxs-lookup"><span data-stu-id="61396-132">From there you can call **New-CsNetworkSubnet** in conjunction with the Windows PowerShell cmdlet **Import-CSV**.</span></span> <span data-ttu-id="61396-133">Используя эти командлеты вместе, вы можете прочитать параметры подсети из CSV-файла и одновременно создать несколько подсетей.</span><span class="sxs-lookup"><span data-stu-id="61396-133">By using these cmdlets together, you can read in subnet settings from a comma-separated values (.csv) file and create multiple subnets at the same time.</span></span> <span data-ttu-id="61396-134">Примеры создания подсетей из CSV-файла можно найти в разделе [New-кснетворксубнет](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet).</span><span class="sxs-lookup"><span data-stu-id="61396-134">For examples of how to create subnets from a .csv file, see [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet).</span></span>


### <a name="to-create-a-network-subnet"></a><span data-ttu-id="61396-135">Создание сетевой подсети</span><span class="sxs-lookup"><span data-stu-id="61396-135">To create a network subnet</span></span>

1.  <span data-ttu-id="61396-136">Войдите на любой компьютер, находящийся во внутреннем развертывании, с использованием учетной записи, входящей в группу RTCUniversalServerAdmins (или имеющей равнозначные права пользователя) либо назначенной роли CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="61396-136">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="61396-137">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="61396-137">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="61396-138">На панели навигации слева выберите пункт **Настройка сети**, а затем — **подсеть**.</span><span class="sxs-lookup"><span data-stu-id="61396-138">In the left navigation bar, click **Network Configuration**, and then click **Subnet**.</span></span>

4.  <span data-ttu-id="61396-139">На странице " **подсеть** " нажмите кнопку " **создать**".</span><span class="sxs-lookup"><span data-stu-id="61396-139">On the **Subnet** page, click **New**.</span></span>

5.  <span data-ttu-id="61396-140">В разделе **Новая подсеть**введите значение в поле **код подсети** .</span><span class="sxs-lookup"><span data-stu-id="61396-140">In **New Subnet**, enter a value in the **Subnet ID** field.</span></span> <span data-ttu-id="61396-141">Это должен быть IP-адрес (например, 174.11.12.0), и он должен быть первым адресом в диапазоне IP-адресов, определенном подсетью.</span><span class="sxs-lookup"><span data-stu-id="61396-141">This must be an IP address (for example, 174.11.12.0), and it must be the first address in the IP address range defined by the subnet.</span></span>

6.  <span data-ttu-id="61396-142">В поле " **Маска** " введите числовое значение от 1 до 32.</span><span class="sxs-lookup"><span data-stu-id="61396-142">In the **Mask** field, enter a numeric value from 1 through 32.</span></span>

    > [!NOTE]  
    > <span data-ttu-id="61396-143">Это значение — битовая маска, применяемая к создаваемой подсети.</span><span class="sxs-lookup"><span data-stu-id="61396-143">This value is the bitmask that is to be applied to the subnet being created.</span></span>

7.  <span data-ttu-id="61396-144">В поле " **код сайта сети**" выберите сайт, к которому относится эта подсеть.</span><span class="sxs-lookup"><span data-stu-id="61396-144">In **Network site ID**, select the site to which this subnet belongs.</span></span>

8.  <span data-ttu-id="61396-145">Необязательно Введите значение в поле **Описание** , чтобы получить дополнительные сведения о подсети, которые нельзя выразить только именем.</span><span class="sxs-lookup"><span data-stu-id="61396-145">(Optional) Type a value in the **Description** field to provide more information about this subnet that cannot be expressed by the name alone.</span></span>

9.  <span data-ttu-id="61396-146">Нажмите **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="61396-146">Click **Commit**.</span></span>


### <a name="to-modify-a-network-subnet"></a><span data-ttu-id="61396-147">Изменение подсети сети</span><span class="sxs-lookup"><span data-stu-id="61396-147">To modify a network subnet</span></span>

1.  <span data-ttu-id="61396-148">Войдите на любой компьютер, находящийся во внутреннем развертывании, с использованием учетной записи, входящей в группу RTCUniversalServerAdmins (или имеющей равнозначные права пользователя) либо назначенной роли CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="61396-148">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="61396-149">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="61396-149">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="61396-150">На панели навигации слева выберите пункт **Настройка сети**, а затем — **подсеть**.</span><span class="sxs-lookup"><span data-stu-id="61396-150">In the left navigation bar, click **Network Configuration**, and then click **Subnet**.</span></span>

4.  <span data-ttu-id="61396-151">На странице **Subnet (подсеть** ) выберите подсеть, которую вы хотите изменить.</span><span class="sxs-lookup"><span data-stu-id="61396-151">On the **Subnet** page, click the subnet that you want to modify.</span></span>

5.  <span data-ttu-id="61396-152">В меню **Правка** щелкните **Подробнее**.</span><span class="sxs-lookup"><span data-stu-id="61396-152">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="61396-153">На странице **Изменение подсети** вы можете изменить битовую маску, связанный сетевой сайт или описание.</span><span class="sxs-lookup"><span data-stu-id="61396-153">On the **Edit Subnet** page, you can modify the bitmask, associated network site, or description.</span></span> <span data-ttu-id="61396-154">Если вы измените битовую маску, имейте в виду, что идентификатор подсети по-прежнему должен быть первым в диапазоне IP-адресов, определенном подсетью.</span><span class="sxs-lookup"><span data-stu-id="61396-154">If you modify the bitmask, keep in mind that the Subnet ID must still be the first address in the IP address range defined by the subnet.</span></span>

7.  <span data-ttu-id="61396-155">Нажмите **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="61396-155">Click **Commit**.</span></span>

## <a name="delete-network-subnets"></a><span data-ttu-id="61396-156">Удаление подсетей сети</span><span class="sxs-lookup"><span data-stu-id="61396-156">Delete network subnets</span></span>

<span data-ttu-id="61396-157">Для удаления подсети вы можете использовать описанную ниже процедуру.</span><span class="sxs-lookup"><span data-stu-id="61396-157">You can use the following procedure to delete a subnet.</span></span> <span data-ttu-id="61396-158">С помощью панели управления Skype для бизнеса Server вы можете создавать, изменять и удалять сетевые подсети.</span><span class="sxs-lookup"><span data-stu-id="61396-158">From the Skype for Business Server Control Panel, you can create, modify, or delete a network subnet.</span></span> 

<span data-ttu-id="61396-159">В большинстве случаев, когда реализовано управление допуском вызовов (CAC) в Skype для бизнеса Server, обычно это большое количество подсетей.</span><span class="sxs-lookup"><span data-stu-id="61396-159">In most deployments of Skype for Business Server where call admission control (CAC) is implemented, there will typically be a large number of subnets.</span></span> <span data-ttu-id="61396-160">По этой причине лучше всего настроить подсети из командной консоли Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="61396-160">Because of this, it is often best to configure subnets from the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="61396-161">Из него вы можете вызвать **New-кснетворксубнет** в сочетании с командлетом Windows PowerShell **Import-CSV**.</span><span class="sxs-lookup"><span data-stu-id="61396-161">From there you can call **New-CsNetworkSubnet** in conjunction with the Windows PowerShell cmdlet **Import-CSV**.</span></span> <span data-ttu-id="61396-162">Используя эти командлеты вместе, вы можете прочитать параметры подсети из CSV-файла и одновременно создать несколько подсетей.</span><span class="sxs-lookup"><span data-stu-id="61396-162">By using these cmdlets together, you can read in subnet settings from a comma-separated values (.csv) file and create multiple subnets at the same time.</span></span> <span data-ttu-id="61396-163">Примеры создания подсетей из CSV-файла можно найти в разделе [New-кснетворксубнет](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet).</span><span class="sxs-lookup"><span data-stu-id="61396-163">For examples of how to create subnets from a .csv file, see [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet).</span></span>


### <a name="to-delete-a-network-subnet"></a><span data-ttu-id="61396-164">Удаление сетевой подсети</span><span class="sxs-lookup"><span data-stu-id="61396-164">To delete a network subnet</span></span>

1.  <span data-ttu-id="61396-165">Войдите на любой компьютер, находящийся во внутреннем развертывании, с использованием учетной записи, входящей в группу RTCUniversalServerAdmins (или имеющей равнозначные права пользователя) либо назначенной роли CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="61396-165">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="61396-166">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="61396-166">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="61396-167">На панели навигации слева выберите пункт **Настройка сети**, а затем — **подсеть**.</span><span class="sxs-lookup"><span data-stu-id="61396-167">In the left navigation bar, click **Network Configuration**, and then click **Subnet**.</span></span>

4.  <span data-ttu-id="61396-168">На странице **Subnet (подсеть** ) выберите подсеть, которую вы хотите удалить.</span><span class="sxs-lookup"><span data-stu-id="61396-168">On the **Subnet** page, click the subnet that you want to delete.</span></span>
 
    > [!NOTE]  
    > <span data-ttu-id="61396-169">Вы можете удалить более одной подсети за один раз.</span><span class="sxs-lookup"><span data-stu-id="61396-169">You can delete more than one subnet at a time.</span></span> <span data-ttu-id="61396-170">Для этого нажмите клавишу CTRL и выберите несколько подсетей, удерживая нажатой клавишу CTRL.</span><span class="sxs-lookup"><span data-stu-id="61396-170">To do this, press CTRL and select multiple subnets while holding down the CTRL key.</span></span> <span data-ttu-id="61396-171">Кроме того, чтобы выбрать все подсети, в меню **Правка** выберите команду **выделить все** .</span><span class="sxs-lookup"><span data-stu-id="61396-171">Or, to select all subnets, click **Select all** on the **Edit** menu.</span></span>

5.  <span data-ttu-id="61396-172">В меню **Правка** выберите команду **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="61396-172">On the **Edit** menu, click **Delete**.</span></span>

6.  <span data-ttu-id="61396-173">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="61396-173">Click **OK**.</span></span>


## <a name="see-also"></a><span data-ttu-id="61396-174">См. также</span><span class="sxs-lookup"><span data-stu-id="61396-174">See Also</span></span>

[<span data-ttu-id="61396-175">New-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="61396-175">New-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet)  

[<span data-ttu-id="61396-176">Set-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="61396-176">Set-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkSubnet)  

[<span data-ttu-id="61396-177">Remove-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="61396-177">Remove-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkSubnet)  

[<span data-ttu-id="61396-178">Get-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="61396-178">Get-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSubnet)  
