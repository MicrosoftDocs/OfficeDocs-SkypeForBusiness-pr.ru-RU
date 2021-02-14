---
title: Управление подсетями
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
description: В большинстве развертывании Skype для бизнеса Server, где реализован контроль допуска звонков (CAC), обычно имеется большое количество подсетей. По этой причине зачастую лучше всего настраивать подсети из оболочки управления Skype для бизнеса Server.
ms.openlocfilehash: e2ac69190ab93b4b6d81fed13538cc6fcaa91f20
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816399"
---
# <a name="managing-network-subnets-in-skype-for-business-server"></a><span data-ttu-id="104ad-104">Управление подсетями в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="104ad-104">Managing network subnets in Skype for Business Server</span></span>

<span data-ttu-id="104ad-105">Для управления подсетями можно использовать панель управления Skype для бизнеса Server или skype для бизнеса Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="104ad-105">You can use either the Skype for Business Server Control Panel or the Skype for Business Server Management Shell to manage network subnets.</span></span> <span data-ttu-id="104ad-106">В большинстве развертывании Skype для бизнеса Server, где реализован контроль допуска звонков (CAC), обычно имеется большое количество подсетей.</span><span class="sxs-lookup"><span data-stu-id="104ad-106">In most deployments of Skype for Business Server where call admission control (CAC) is implemented, there will typically be a large number of subnets.</span></span> <span data-ttu-id="104ad-107">По этой причине зачастую лучше всего настраивать подсети из оболочки управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="104ad-107">Because of this, it is often best to configure subnets from the Skype for Business Server Management Shell.</span></span>

<span data-ttu-id="104ad-108">Разделы этой статьи используются для просмотра сведений о подсети или создания, изменения или удаления подсетей.</span><span class="sxs-lookup"><span data-stu-id="104ad-108">Use the sections in this article to view network subnet information or create, modify, or delete network subnets.</span></span> 

## <a name="view-network-subnet-information"></a><span data-ttu-id="104ad-109">Просмотр сведений о подсети</span><span class="sxs-lookup"><span data-stu-id="104ad-109">View network subnet information</span></span> 

<span data-ttu-id="104ad-110">Для просмотра подсети можно использовать следующую процедуру.</span><span class="sxs-lookup"><span data-stu-id="104ad-110">You can use the following procedure to view a network subnet.</span></span> <span data-ttu-id="104ad-111">На панели управления Skype для бизнеса Server можно создавать, изменять или удалять сетевую подсеть.</span><span class="sxs-lookup"><span data-stu-id="104ad-111">From the Skype for Business Server Control Panel, you can create, modify, or delete a network subnet.</span></span> 

### <a name="to-view-a-network-subnet"></a><span data-ttu-id="104ad-112">Чтобы просмотреть подсеть</span><span class="sxs-lookup"><span data-stu-id="104ad-112">To view a network subnet</span></span>

1.  <span data-ttu-id="104ad-113">Из учетной записи пользователя, которая является членом группы RTCUniversalServerAdmins (или имеет эквивалентные права пользователя) или назначена роли CsAdministrator, войдите на любой компьютер во внутреннем развертывании.</span><span class="sxs-lookup"><span data-stu-id="104ad-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="104ad-114">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="104ad-114">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="104ad-115">В левой панели навигации щелкните **"Конфигурация** сети" и выберите **"Подсеть".**</span><span class="sxs-lookup"><span data-stu-id="104ad-115">In the left navigation bar, click **Network Configuration**, and then click **Subnet**.</span></span>

4.  <span data-ttu-id="104ad-116">На странице **Подсеть** щелкните подсеть, которую следует просмотреть.</span><span class="sxs-lookup"><span data-stu-id="104ad-116">On the **Subnet** page, click the subnet that you want to view.</span></span>
 
    > [!NOTE]  
    > <span data-ttu-id="104ad-117">Одновременно можно просматривать только одну подсеть.</span><span class="sxs-lookup"><span data-stu-id="104ad-117">You can only view one subnet at a time.</span></span>

5.  <span data-ttu-id="104ad-118">В меню **Edit** (Правка) щелкните пункт  **Show details** (Показать подробности).</span><span class="sxs-lookup"><span data-stu-id="104ad-118">On the **Edit** menu, click **Show details**.</span></span>

### <a name="view-network-subnet-configuration-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="104ad-119">Просмотр сведений о конфигурации подсети с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="104ad-119">View network subnet configuration information by Using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="104ad-120">Сведения о подсети можно просмотреть с помощью Windows PowerShell и Get-CsNetworkSubnet сети.</span><span class="sxs-lookup"><span data-stu-id="104ad-120">Network subnet information can be viewed by using Windows PowerShell and the Get-CsNetworkSubnet cmdlet.</span></span> <span data-ttu-id="104ad-121">Этот cmdlet можно запустить в оболочке управления Skype для бизнеса Server или в удаленном сеансе Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="104ad-121">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

### <a name="to-view-network-subnet-information"></a><span data-ttu-id="104ad-122">Просмотр сведений о подсети</span><span class="sxs-lookup"><span data-stu-id="104ad-122">To view network subnet information</span></span>

  - <span data-ttu-id="104ad-123">Чтобы просмотреть сведения обо всех подсетях, введите следующую команду в командной оболочке Skype для бизнеса Server и нажмите ввод:</span><span class="sxs-lookup"><span data-stu-id="104ad-123">To view information about all your network subnets, type the following command in the Skype for Business Server Management Shell and then press ENTER:</span></span>
    
        Get-CsNetworkSubnet
    
    <span data-ttu-id="104ad-124">Это приведет к возврату приблизительно такой информации:</span><span class="sxs-lookup"><span data-stu-id="104ad-124">That will return information similar to this:</span></span>
    
        Identity      : 172.11.15.0
        MaskBits      : 28
        Description   :
        NetworkSiteID : Redmond
        SubnetID      : 172.11.15.0


<span data-ttu-id="104ad-125">Дополнительные сведения см. в разделе справки по командлету [Get-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSubnet).</span><span class="sxs-lookup"><span data-stu-id="104ad-125">For more information, see the help topic for the [Get-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSubnet) cmdlet.</span></span>


## <a name="create-or-modify-network-subnets"></a><span data-ttu-id="104ad-126">Создание или изменение подсетей сети</span><span class="sxs-lookup"><span data-stu-id="104ad-126">Create or modify network subnets</span></span> 

<span data-ttu-id="104ad-127">Сеть должна быть сопоставлена с сетевым узлом для определения географического расположения узла, принадлежащего этой подсети.</span><span class="sxs-lookup"><span data-stu-id="104ad-127">A network subnet must be associated with a network site for the purposes of determining the geographic location of the host belonging to this subnet.</span></span> <span data-ttu-id="104ad-128">Для настройки подсетей можно использовать панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="104ad-128">You can use the Skype for Business Server Control Panel to configure subnets.</span></span> <span data-ttu-id="104ad-129">На панели управления Skype для бизнеса Server можно создавать, изменять или удалять сетевую подсеть.</span><span class="sxs-lookup"><span data-stu-id="104ad-129">From the Skype for Business Server Control Panel, you can create, modify, or delete a network subnet.</span></span> 

<span data-ttu-id="104ad-130">В большинстве развертывании Skype для бизнеса Server, где реализован контроль допуска звонков (CAC), обычно имеется большое количество подсетей.</span><span class="sxs-lookup"><span data-stu-id="104ad-130">In most deployments of Skype for Business Server where call admission control (CAC) is implemented, there will typically be a large number of subnets.</span></span> <span data-ttu-id="104ad-131">По этой причине зачастую лучше всего настраивать подсети из оболочки управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="104ad-131">Because of this, it is often best to configure subnets from the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="104ad-132">Оттуда вы можете вызвать **New-CsNetworkSubnet** в сочетании с командлетом Windows PowerShell **Import-CSV.**</span><span class="sxs-lookup"><span data-stu-id="104ad-132">From there you can call **New-CsNetworkSubnet** in conjunction with the Windows PowerShell cmdlet **Import-CSV**.</span></span> <span data-ttu-id="104ad-133">Используя эти командлеты, вы можете считывать параметры подсетей из файла данных с разделителями-запятыми  (CSV) и одновременно создавать несколько сетей.</span><span class="sxs-lookup"><span data-stu-id="104ad-133">By using these cmdlets together, you can read in subnet settings from a comma-separated values (.csv) file and create multiple subnets at the same time.</span></span> <span data-ttu-id="104ad-134">Примеры создания подсетей из файла CSV см. в разделе [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet).</span><span class="sxs-lookup"><span data-stu-id="104ad-134">For examples of how to create subnets from a .csv file, see [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet).</span></span>


### <a name="to-create-a-network-subnet"></a><span data-ttu-id="104ad-135">Создание подсети</span><span class="sxs-lookup"><span data-stu-id="104ad-135">To create a network subnet</span></span>

1.  <span data-ttu-id="104ad-136">Из учетной записи пользователя, которая является членом группы RTCUniversalServerAdmins (или имеет эквивалентные права пользователя) или назначена роли CsAdministrator, войдите на любой компьютер во внутреннем развертывании.</span><span class="sxs-lookup"><span data-stu-id="104ad-136">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="104ad-137">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="104ad-137">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="104ad-138">В левой панели навигации щелкните **"Конфигурация** сети" и выберите **"Подсеть".**</span><span class="sxs-lookup"><span data-stu-id="104ad-138">In the left navigation bar, click **Network Configuration**, and then click **Subnet**.</span></span>

4.  <span data-ttu-id="104ad-139">На странице **Subnet** (Подсеть) нажмите кнопку **New** (Создать).</span><span class="sxs-lookup"><span data-stu-id="104ad-139">On the **Subnet** page, click **New**.</span></span>

5.  <span data-ttu-id="104ad-p107">Введите значение в поле **Subnet ID** (Идентификатор подсети) окна **New Subnet** (Новая подсеть). Это должен быть IP-адрес (например, 174.11.12.0), и он должен быть первым адресом из диапазона IP-адресов, определенного этой подсетью.</span><span class="sxs-lookup"><span data-stu-id="104ad-p107">In **New Subnet**, enter a value in the **Subnet ID** field. This must be an IP address (for example, 174.11.12.0), and it must be the first address in the IP address range defined by the subnet.</span></span>

6.  <span data-ttu-id="104ad-142">В поле **Mask** (Маска) введите числовое значение от 1 до 32.</span><span class="sxs-lookup"><span data-stu-id="104ad-142">In the **Mask** field, enter a numeric value from 1 through 32.</span></span>

    > [!NOTE]  
    > <span data-ttu-id="104ad-143">Это значение является битовой маской, применяемой к создаваемой подсети.</span><span class="sxs-lookup"><span data-stu-id="104ad-143">This value is the bitmask that is to be applied to the subnet being created.</span></span>

7.  <span data-ttu-id="104ad-144">В области **Network site ID** (Идентификатор сетевого узла) выберите узел, к которому относится данная подсеть.</span><span class="sxs-lookup"><span data-stu-id="104ad-144">In **Network site ID**, select the site to which this subnet belongs.</span></span>

8.  <span data-ttu-id="104ad-145">(Необязательно) Введите значение в поле **Description** (Описание), чтобы предоставить дополнительную информацию о данной подсети, которую нельзя выразить одним только именем.</span><span class="sxs-lookup"><span data-stu-id="104ad-145">(Optional) Type a value in the **Description** field to provide more information about this subnet that cannot be expressed by the name alone.</span></span>

9.  <span data-ttu-id="104ad-146">Щелкните элемент **Commit** (Зафиксировать).</span><span class="sxs-lookup"><span data-stu-id="104ad-146">Click **Commit**.</span></span>


### <a name="to-modify-a-network-subnet"></a><span data-ttu-id="104ad-147">Изменение подсети</span><span class="sxs-lookup"><span data-stu-id="104ad-147">To modify a network subnet</span></span>

1.  <span data-ttu-id="104ad-148">Из учетной записи пользователя, которая является членом группы RTCUniversalServerAdmins (или имеет эквивалентные права пользователя) или назначена роли CsAdministrator, войдите на любой компьютер во внутреннем развертывании.</span><span class="sxs-lookup"><span data-stu-id="104ad-148">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="104ad-149">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="104ad-149">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="104ad-150">В левой панели навигации щелкните **"Конфигурация** сети" и выберите **"Подсеть".**</span><span class="sxs-lookup"><span data-stu-id="104ad-150">In the left navigation bar, click **Network Configuration**, and then click **Subnet**.</span></span>

4.  <span data-ttu-id="104ad-151">На странице **Subnet** (Подсеть) щелкните подсеть, которую хотите изменить.</span><span class="sxs-lookup"><span data-stu-id="104ad-151">On the **Subnet** page, click the subnet that you want to modify.</span></span>

5.  <span data-ttu-id="104ad-152">В меню **Edit** (Правка) щелкните пункт  **Show details** (Показать подробности).</span><span class="sxs-lookup"><span data-stu-id="104ad-152">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="104ad-p108">На странице **Edit Subnet** (Изменение подсети) вы можете изменить битовую маску, сопоставленную с сетевым узлом, или описание. При изменении битовой маски помните о том, что параметр идентификатора подсети должен оставаться первым адресом из диапазона IP-адресов, определенного этой подсетью.</span><span class="sxs-lookup"><span data-stu-id="104ad-p108">On the **Edit Subnet** page, you can modify the bitmask, associated network site, or description. If you modify the bitmask, keep in mind that the Subnet ID must still be the first address in the IP address range defined by the subnet.</span></span>

7.  <span data-ttu-id="104ad-155">Щелкните элемент **Commit** (Зафиксировать).</span><span class="sxs-lookup"><span data-stu-id="104ad-155">Click **Commit**.</span></span>

## <a name="delete-network-subnets"></a><span data-ttu-id="104ad-156">Удаление подсетей</span><span class="sxs-lookup"><span data-stu-id="104ad-156">Delete network subnets</span></span>

<span data-ttu-id="104ad-157">Для удаления подсети можно использовать следующую процедуру.</span><span class="sxs-lookup"><span data-stu-id="104ad-157">You can use the following procedure to delete a subnet.</span></span> <span data-ttu-id="104ad-158">На панели управления Skype для бизнеса Server можно создавать, изменять или удалять сетевую подсеть.</span><span class="sxs-lookup"><span data-stu-id="104ad-158">From the Skype for Business Server Control Panel, you can create, modify, or delete a network subnet.</span></span> 

<span data-ttu-id="104ad-159">В большинстве развертывании Skype для бизнеса Server, где реализован контроль допуска звонков (CAC), обычно имеется большое количество подсетей.</span><span class="sxs-lookup"><span data-stu-id="104ad-159">In most deployments of Skype for Business Server where call admission control (CAC) is implemented, there will typically be a large number of subnets.</span></span> <span data-ttu-id="104ad-160">По этой причине зачастую лучше всего настраивать подсети из оболочки управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="104ad-160">Because of this, it is often best to configure subnets from the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="104ad-161">Оттуда вы можете вызвать **New-CsNetworkSubnet** в сочетании с командлетом Windows PowerShell **Import-CSV.**</span><span class="sxs-lookup"><span data-stu-id="104ad-161">From there you can call **New-CsNetworkSubnet** in conjunction with the Windows PowerShell cmdlet **Import-CSV**.</span></span> <span data-ttu-id="104ad-162">Используя эти командлеты, вы можете считывать параметры подсетей из файла данных с разделителями-запятыми  (CSV) и одновременно создавать несколько сетей.</span><span class="sxs-lookup"><span data-stu-id="104ad-162">By using these cmdlets together, you can read in subnet settings from a comma-separated values (.csv) file and create multiple subnets at the same time.</span></span> <span data-ttu-id="104ad-163">Примеры создания подсетей из CSV-файла см. в разделе [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet).</span><span class="sxs-lookup"><span data-stu-id="104ad-163">For examples of how to create subnets from a .csv file, see [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet).</span></span>


### <a name="to-delete-a-network-subnet"></a><span data-ttu-id="104ad-164">Удаление подсети</span><span class="sxs-lookup"><span data-stu-id="104ad-164">To delete a network subnet</span></span>

1.  <span data-ttu-id="104ad-165">Из учетной записи пользователя, которая является членом группы RTCUniversalServerAdmins (или имеет эквивалентные права пользователя) или назначена роли CsAdministrator, войдите на любой компьютер во внутреннем развертывании.</span><span class="sxs-lookup"><span data-stu-id="104ad-165">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="104ad-166">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="104ad-166">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="104ad-167">В левой панели навигации щелкните **"Конфигурация** сети" и выберите **"Подсеть".**</span><span class="sxs-lookup"><span data-stu-id="104ad-167">In the left navigation bar, click **Network Configuration**, and then click **Subnet**.</span></span>

4.  <span data-ttu-id="104ad-168">На странице **подсетей** щелкните подсеть, которую следует удалить.</span><span class="sxs-lookup"><span data-stu-id="104ad-168">On the **Subnet** page, click the subnet that you want to delete.</span></span>
 
    > [!NOTE]  
    > <span data-ttu-id="104ad-p111">Можно одновременно удалять несколько подсетей. Для этого нажмите клавишу CTRL и выберите несколько подсетей, удерживая клавишу CTRL нажатой. Можно также выбрать все подсети, нажав пункт **Выбрать все** в меню **Правка**.</span><span class="sxs-lookup"><span data-stu-id="104ad-p111">You can delete more than one subnet at a time. To do this, press CTRL and select multiple subnets while holding down the CTRL key. Or, to select all subnets, click **Select all** on the **Edit** menu.</span></span>

5.  <span data-ttu-id="104ad-172">В меню **Правка** выберите команду **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="104ad-172">On the **Edit** menu, click **Delete**.</span></span>

6.  <span data-ttu-id="104ad-173">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="104ad-173">Click **OK**.</span></span>


## <a name="see-also"></a><span data-ttu-id="104ad-174">См. также</span><span class="sxs-lookup"><span data-stu-id="104ad-174">See Also</span></span>

[<span data-ttu-id="104ad-175">New-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="104ad-175">New-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet)  

[<span data-ttu-id="104ad-176">Set-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="104ad-176">Set-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkSubnet)  

[<span data-ttu-id="104ad-177">Remove-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="104ad-177">Remove-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkSubnet)  

[<span data-ttu-id="104ad-178">Get-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="104ad-178">Get-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSubnet)  
