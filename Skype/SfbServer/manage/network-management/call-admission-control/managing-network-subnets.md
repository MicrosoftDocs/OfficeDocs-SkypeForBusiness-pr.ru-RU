---
title: Управление сетевыми подсетями
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: В большинстве развертывании Skype для бизнеса Server, где реализуется управление приемом вызовов (CAC), обычно существует большое количество подсетей. Из-за этого часто лучше всего настраивать подсети из оболочки управления Skype для бизнес-серверов.
ms.openlocfilehash: ef771ad78f00085374038203e1049790a9179e88
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51122443"
---
# <a name="managing-network-subnets-in-skype-for-business-server"></a><span data-ttu-id="598c4-104">Управление подсетями в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="598c4-104">Managing network subnets in Skype for Business Server</span></span>

<span data-ttu-id="598c4-105">Для управления сетевыми подсетями можно использовать панель управления Skype для бизнес-серверов или оболочку управления бизнес-серверами Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="598c4-105">You can use either the Skype for Business Server Control Panel or the Skype for Business Server Management Shell to manage network subnets.</span></span> <span data-ttu-id="598c4-106">В большинстве развертывании Skype для бизнеса Server, где реализуется управление приемом вызовов (CAC), обычно существует большое количество подсетей.</span><span class="sxs-lookup"><span data-stu-id="598c4-106">In most deployments of Skype for Business Server where call admission control (CAC) is implemented, there will typically be a large number of subnets.</span></span> <span data-ttu-id="598c4-107">Из-за этого часто лучше всего настраивать подсети из оболочки управления Skype для бизнес-серверов.</span><span class="sxs-lookup"><span data-stu-id="598c4-107">Because of this, it is often best to configure subnets from the Skype for Business Server Management Shell.</span></span>

<span data-ttu-id="598c4-108">Используйте разделы в этой статье для просмотра данных сетевой подсети или создания, изменения или удаления сетевых подсетей.</span><span class="sxs-lookup"><span data-stu-id="598c4-108">Use the sections in this article to view network subnet information or create, modify, or delete network subnets.</span></span> 

## <a name="view-network-subnet-information"></a><span data-ttu-id="598c4-109">Просмотр данных сетевой подсети</span><span class="sxs-lookup"><span data-stu-id="598c4-109">View network subnet information</span></span> 

<span data-ttu-id="598c4-110">Для просмотра сетевой подсети можно использовать следующую процедуру.</span><span class="sxs-lookup"><span data-stu-id="598c4-110">You can use the following procedure to view a network subnet.</span></span> <span data-ttu-id="598c4-111">С панели управления Skype для бизнес-серверов можно создать, изменить или удалить подсети сети.</span><span class="sxs-lookup"><span data-stu-id="598c4-111">From the Skype for Business Server Control Panel, you can create, modify, or delete a network subnet.</span></span> 

### <a name="to-view-a-network-subnet"></a><span data-ttu-id="598c4-112">Чтобы просмотреть подсеть</span><span class="sxs-lookup"><span data-stu-id="598c4-112">To view a network subnet</span></span>

1.  <span data-ttu-id="598c4-113">С учетной записи пользователя, которая входит в группу RTCUniversalServerAdmins (или имеет эквивалентные права пользователя) или назначена роли CsAdministrator, войдите на любой компьютер во внутреннем развертывании.</span><span class="sxs-lookup"><span data-stu-id="598c4-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="598c4-114">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Skype для бизнес-серверов.</span><span class="sxs-lookup"><span data-stu-id="598c4-114">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="598c4-115">В левой панели навигации щелкните **Конфигурация сети** и нажмите **кнопку Subnet**.</span><span class="sxs-lookup"><span data-stu-id="598c4-115">In the left navigation bar, click **Network Configuration**, and then click **Subnet**.</span></span>

4.  <span data-ttu-id="598c4-116">На странице **Подсеть** щелкните подсеть, которую следует просмотреть.</span><span class="sxs-lookup"><span data-stu-id="598c4-116">On the **Subnet** page, click the subnet that you want to view.</span></span>
 
    > [!NOTE]  
    > <span data-ttu-id="598c4-117">Одновременно можно просматривать только одну подсеть.</span><span class="sxs-lookup"><span data-stu-id="598c4-117">You can only view one subnet at a time.</span></span>

5.  <span data-ttu-id="598c4-118">В меню **Edit** (Правка) щелкните пункт  **Show details** (Показать подробности).</span><span class="sxs-lookup"><span data-stu-id="598c4-118">On the **Edit** menu, click **Show details**.</span></span>

### <a name="view-network-subnet-configuration-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="598c4-119">Просмотр сведений о конфигурации сетевой подсети с помощью Windows PowerShell-кодлетов</span><span class="sxs-lookup"><span data-stu-id="598c4-119">View network subnet configuration information by Using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="598c4-120">Сведения о сетевой подсети можно просматривать с помощью Windows PowerShell и Get-CsNetworkSubnet.</span><span class="sxs-lookup"><span data-stu-id="598c4-120">Network subnet information can be viewed by using Windows PowerShell and the Get-CsNetworkSubnet cmdlet.</span></span> <span data-ttu-id="598c4-121">Этот комлет можно выполнить либо из оболочки управления skype для бизнес-серверов, либо из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="598c4-121">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

### <a name="to-view-network-subnet-information"></a><span data-ttu-id="598c4-122">Просмотр данных сетевой подсети</span><span class="sxs-lookup"><span data-stu-id="598c4-122">To view network subnet information</span></span>

  - <span data-ttu-id="598c4-123">Чтобы просмотреть сведения обо всех сетевых подсетях, введите следующую команду в командной оболочке Skype для бизнес-серверов и нажмите кнопку ENTER:</span><span class="sxs-lookup"><span data-stu-id="598c4-123">To view information about all your network subnets, type the following command in the Skype for Business Server Management Shell and then press ENTER:</span></span>
    
        Get-CsNetworkSubnet
    
    <span data-ttu-id="598c4-124">Это приведет к возврату приблизительно такой информации:</span><span class="sxs-lookup"><span data-stu-id="598c4-124">That will return information similar to this:</span></span>
    
        Identity      : 172.11.15.0
        MaskBits      : 28
        Description   :
        NetworkSiteID : Redmond
        SubnetID      : 172.11.15.0


<span data-ttu-id="598c4-125">Дополнительные сведения см. в разделе справки по командлету [Get-CsNetworkSubnet](/powershell/module/skype/Get-CsNetworkSubnet).</span><span class="sxs-lookup"><span data-stu-id="598c4-125">For more information, see the help topic for the [Get-CsNetworkSubnet](/powershell/module/skype/Get-CsNetworkSubnet) cmdlet.</span></span>


## <a name="create-or-modify-network-subnets"></a><span data-ttu-id="598c4-126">Создание или изменение сетевых подсетей</span><span class="sxs-lookup"><span data-stu-id="598c4-126">Create or modify network subnets</span></span> 

<span data-ttu-id="598c4-127">Сеть должна быть сопоставлена с сетевым узлом для определения географического расположения узла, принадлежащего этой подсети.</span><span class="sxs-lookup"><span data-stu-id="598c4-127">A network subnet must be associated with a network site for the purposes of determining the geographic location of the host belonging to this subnet.</span></span> <span data-ttu-id="598c4-128">Для настройки подсетей можно использовать панель управления Skype для бизнес-серверов.</span><span class="sxs-lookup"><span data-stu-id="598c4-128">You can use the Skype for Business Server Control Panel to configure subnets.</span></span> <span data-ttu-id="598c4-129">С панели управления Skype для бизнес-серверов можно создать, изменить или удалить подсети сети.</span><span class="sxs-lookup"><span data-stu-id="598c4-129">From the Skype for Business Server Control Panel, you can create, modify, or delete a network subnet.</span></span> 

<span data-ttu-id="598c4-130">В большинстве развертывании Skype для бизнеса Server, где реализуется управление приемом вызовов (CAC), обычно существует большое количество подсетей.</span><span class="sxs-lookup"><span data-stu-id="598c4-130">In most deployments of Skype for Business Server where call admission control (CAC) is implemented, there will typically be a large number of subnets.</span></span> <span data-ttu-id="598c4-131">Из-за этого часто лучше всего настраивать подсети из оболочки управления Skype для бизнес-серверов.</span><span class="sxs-lookup"><span data-stu-id="598c4-131">Because of this, it is often best to configure subnets from the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="598c4-132">Оттуда можно вызвать **New-CsNetworkSubnet** совместно с командлетом Windows PowerShell **Import-CSV.**</span><span class="sxs-lookup"><span data-stu-id="598c4-132">From there you can call **New-CsNetworkSubnet** in conjunction with the Windows PowerShell cmdlet **Import-CSV**.</span></span> <span data-ttu-id="598c4-133">Используя эти командлеты, вы можете считывать параметры подсетей из файла данных с разделителями-запятыми  (CSV) и одновременно создавать несколько сетей.</span><span class="sxs-lookup"><span data-stu-id="598c4-133">By using these cmdlets together, you can read in subnet settings from a comma-separated values (.csv) file and create multiple subnets at the same time.</span></span> <span data-ttu-id="598c4-134">Примеры создания подсетей из файла CSV см. в разделе [New-CsNetworkSubnet](/powershell/module/skype/New-CsNetworkSubnet).</span><span class="sxs-lookup"><span data-stu-id="598c4-134">For examples of how to create subnets from a .csv file, see [New-CsNetworkSubnet](/powershell/module/skype/New-CsNetworkSubnet).</span></span>


### <a name="to-create-a-network-subnet"></a><span data-ttu-id="598c4-135">Создание подсети</span><span class="sxs-lookup"><span data-stu-id="598c4-135">To create a network subnet</span></span>

1.  <span data-ttu-id="598c4-136">С учетной записи пользователя, которая входит в группу RTCUniversalServerAdmins (или имеет эквивалентные права пользователя) или назначена роли CsAdministrator, войдите на любой компьютер во внутреннем развертывании.</span><span class="sxs-lookup"><span data-stu-id="598c4-136">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="598c4-137">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Skype для бизнес-серверов.</span><span class="sxs-lookup"><span data-stu-id="598c4-137">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="598c4-138">В левой панели навигации щелкните **Конфигурация сети** и нажмите **кнопку Subnet**.</span><span class="sxs-lookup"><span data-stu-id="598c4-138">In the left navigation bar, click **Network Configuration**, and then click **Subnet**.</span></span>

4.  <span data-ttu-id="598c4-139">На странице **Subnet** (Подсеть) нажмите кнопку **New** (Создать).</span><span class="sxs-lookup"><span data-stu-id="598c4-139">On the **Subnet** page, click **New**.</span></span>

5.  <span data-ttu-id="598c4-p107">Введите значение в поле **Subnet ID** (Идентификатор подсети) окна **New Subnet** (Новая подсеть). Это должен быть IP-адрес (например, 174.11.12.0), и он должен быть первым адресом из диапазона IP-адресов, определенного этой подсетью.</span><span class="sxs-lookup"><span data-stu-id="598c4-p107">In **New Subnet**, enter a value in the **Subnet ID** field. This must be an IP address (for example, 174.11.12.0), and it must be the first address in the IP address range defined by the subnet.</span></span>

6.  <span data-ttu-id="598c4-142">В поле **Mask** (Маска) введите числовое значение от 1 до 32.</span><span class="sxs-lookup"><span data-stu-id="598c4-142">In the **Mask** field, enter a numeric value from 1 through 32.</span></span>

    > [!NOTE]  
    > <span data-ttu-id="598c4-143">Это значение является битовой маской, применяемой к создаваемой подсети.</span><span class="sxs-lookup"><span data-stu-id="598c4-143">This value is the bitmask that is to be applied to the subnet being created.</span></span>

7.  <span data-ttu-id="598c4-144">В области **Network site ID** (Идентификатор сетевого узла) выберите узел, к которому относится данная подсеть.</span><span class="sxs-lookup"><span data-stu-id="598c4-144">In **Network site ID**, select the site to which this subnet belongs.</span></span>

8.  <span data-ttu-id="598c4-145">(Необязательно) Введите значение в поле **Description** (Описание), чтобы предоставить дополнительную информацию о данной подсети, которую нельзя выразить одним только именем.</span><span class="sxs-lookup"><span data-stu-id="598c4-145">(Optional) Type a value in the **Description** field to provide more information about this subnet that cannot be expressed by the name alone.</span></span>

9.  <span data-ttu-id="598c4-146">Щелкните элемент **Commit** (Зафиксировать).</span><span class="sxs-lookup"><span data-stu-id="598c4-146">Click **Commit**.</span></span>


### <a name="to-modify-a-network-subnet"></a><span data-ttu-id="598c4-147">Изменение подсети</span><span class="sxs-lookup"><span data-stu-id="598c4-147">To modify a network subnet</span></span>

1.  <span data-ttu-id="598c4-148">С учетной записи пользователя, которая входит в группу RTCUniversalServerAdmins (или имеет эквивалентные права пользователя) или назначена роли CsAdministrator, войдите на любой компьютер во внутреннем развертывании.</span><span class="sxs-lookup"><span data-stu-id="598c4-148">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="598c4-149">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Skype для бизнес-серверов.</span><span class="sxs-lookup"><span data-stu-id="598c4-149">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="598c4-150">В левой панели навигации щелкните **Конфигурация сети** и нажмите **кнопку Subnet**.</span><span class="sxs-lookup"><span data-stu-id="598c4-150">In the left navigation bar, click **Network Configuration**, and then click **Subnet**.</span></span>

4.  <span data-ttu-id="598c4-151">На странице **Subnet** (Подсеть) щелкните подсеть, которую хотите изменить.</span><span class="sxs-lookup"><span data-stu-id="598c4-151">On the **Subnet** page, click the subnet that you want to modify.</span></span>

5.  <span data-ttu-id="598c4-152">В меню **Edit** (Правка) щелкните пункт  **Show details** (Показать подробности).</span><span class="sxs-lookup"><span data-stu-id="598c4-152">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="598c4-p108">На странице **Edit Subnet** (Изменение подсети) вы можете изменить битовую маску, сопоставленную с сетевым узлом, или описание. При изменении битовой маски помните о том, что параметр идентификатора подсети должен оставаться первым адресом из диапазона IP-адресов, определенного этой подсетью.</span><span class="sxs-lookup"><span data-stu-id="598c4-p108">On the **Edit Subnet** page, you can modify the bitmask, associated network site, or description. If you modify the bitmask, keep in mind that the Subnet ID must still be the first address in the IP address range defined by the subnet.</span></span>

7.  <span data-ttu-id="598c4-155">Щелкните элемент **Commit** (Зафиксировать).</span><span class="sxs-lookup"><span data-stu-id="598c4-155">Click **Commit**.</span></span>

## <a name="delete-network-subnets"></a><span data-ttu-id="598c4-156">Удаление сетевых подсетей</span><span class="sxs-lookup"><span data-stu-id="598c4-156">Delete network subnets</span></span>

<span data-ttu-id="598c4-157">Для удаления подсети можно использовать следующую процедуру.</span><span class="sxs-lookup"><span data-stu-id="598c4-157">You can use the following procedure to delete a subnet.</span></span> <span data-ttu-id="598c4-158">С панели управления Skype для бизнес-серверов можно создать, изменить или удалить подсети сети.</span><span class="sxs-lookup"><span data-stu-id="598c4-158">From the Skype for Business Server Control Panel, you can create, modify, or delete a network subnet.</span></span> 

<span data-ttu-id="598c4-159">В большинстве развертывании Skype для бизнеса Server, где реализуется управление приемом вызовов (CAC), обычно существует большое количество подсетей.</span><span class="sxs-lookup"><span data-stu-id="598c4-159">In most deployments of Skype for Business Server where call admission control (CAC) is implemented, there will typically be a large number of subnets.</span></span> <span data-ttu-id="598c4-160">Из-за этого часто лучше всего настраивать подсети из оболочки управления Skype для бизнес-серверов.</span><span class="sxs-lookup"><span data-stu-id="598c4-160">Because of this, it is often best to configure subnets from the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="598c4-161">Оттуда можно вызвать **New-CsNetworkSubnet** совместно с командлетом Windows PowerShell **Import-CSV.**</span><span class="sxs-lookup"><span data-stu-id="598c4-161">From there you can call **New-CsNetworkSubnet** in conjunction with the Windows PowerShell cmdlet **Import-CSV**.</span></span> <span data-ttu-id="598c4-162">Используя эти командлеты, вы можете считывать параметры подсетей из файла данных с разделителями-запятыми  (CSV) и одновременно создавать несколько сетей.</span><span class="sxs-lookup"><span data-stu-id="598c4-162">By using these cmdlets together, you can read in subnet settings from a comma-separated values (.csv) file and create multiple subnets at the same time.</span></span> <span data-ttu-id="598c4-163">Примеры создания подсетей из CSV-файла см. в разделе [New-CsNetworkSubnet](/powershell/module/skype/New-CsNetworkSubnet).</span><span class="sxs-lookup"><span data-stu-id="598c4-163">For examples of how to create subnets from a .csv file, see [New-CsNetworkSubnet](/powershell/module/skype/New-CsNetworkSubnet).</span></span>


### <a name="to-delete-a-network-subnet"></a><span data-ttu-id="598c4-164">Удаление подсети</span><span class="sxs-lookup"><span data-stu-id="598c4-164">To delete a network subnet</span></span>

1.  <span data-ttu-id="598c4-165">С учетной записи пользователя, которая входит в группу RTCUniversalServerAdmins (или имеет эквивалентные права пользователя) или назначена роли CsAdministrator, войдите на любой компьютер во внутреннем развертывании.</span><span class="sxs-lookup"><span data-stu-id="598c4-165">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="598c4-166">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Skype для бизнес-серверов.</span><span class="sxs-lookup"><span data-stu-id="598c4-166">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="598c4-167">В левой панели навигации щелкните **Конфигурация сети** и нажмите **кнопку Subnet**.</span><span class="sxs-lookup"><span data-stu-id="598c4-167">In the left navigation bar, click **Network Configuration**, and then click **Subnet**.</span></span>

4.  <span data-ttu-id="598c4-168">На странице **подсетей** щелкните подсеть, которую следует удалить.</span><span class="sxs-lookup"><span data-stu-id="598c4-168">On the **Subnet** page, click the subnet that you want to delete.</span></span>
 
    > [!NOTE]  
    > <span data-ttu-id="598c4-p111">Можно одновременно удалять несколько подсетей. Для этого нажмите клавишу CTRL и выберите несколько подсетей, удерживая клавишу CTRL нажатой. Можно также выбрать все подсети, нажав пункт **Выбрать все** в меню **Правка**.</span><span class="sxs-lookup"><span data-stu-id="598c4-p111">You can delete more than one subnet at a time. To do this, press CTRL and select multiple subnets while holding down the CTRL key. Or, to select all subnets, click **Select all** on the **Edit** menu.</span></span>

5.  <span data-ttu-id="598c4-172">В меню **Правка** выберите команду **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="598c4-172">On the **Edit** menu, click **Delete**.</span></span>

6.  <span data-ttu-id="598c4-173">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="598c4-173">Click **OK**.</span></span>


## <a name="see-also"></a><span data-ttu-id="598c4-174">См. также</span><span class="sxs-lookup"><span data-stu-id="598c4-174">See Also</span></span>

[<span data-ttu-id="598c4-175">New-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="598c4-175">New-CsNetworkSubnet</span></span>](/powershell/module/skype/New-CsNetworkSubnet)  

[<span data-ttu-id="598c4-176">Set-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="598c4-176">Set-CsNetworkSubnet</span></span>](/powershell/module/skype/Set-CsNetworkSubnet)  

[<span data-ttu-id="598c4-177">Remove-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="598c4-177">Remove-CsNetworkSubnet</span></span>](/powershell/module/skype/Remove-CsNetworkSubnet)  

[<span data-ttu-id="598c4-178">Get-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="598c4-178">Get-CsNetworkSubnet</span></span>](/powershell/module/skype/Get-CsNetworkSubnet)