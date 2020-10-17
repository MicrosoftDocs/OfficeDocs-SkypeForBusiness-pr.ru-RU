---
title: 'Lync Server 2013: создание или изменение сетевых подсетей'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify network subnets
ms:assetid: 1ba8c4e3-fbc7-4758-88ac-d651fef17bed
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520957(v=OCS.15)
ms:contentKeyID: 48183548
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2e7d5822438b1907cf718e2ea0365d9e9dad0814
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48501666"
---
# <a name="create-or-modify-network-subnets-in-lync-server-2013"></a><span data-ttu-id="e3a82-102">Создание или изменение сетевых подсетей в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e3a82-102">Create or modify network subnets in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e3a82-103">_**Последнее изменение темы:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="e3a82-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="e3a82-104">Сеть должна быть сопоставлена с сетевым узлом для определения географического расположения узла, принадлежащего этой подсети.</span><span class="sxs-lookup"><span data-stu-id="e3a82-104">A network subnet must be associated with a network site for the purposes of determining the geographic location of the host belonging to this subnet.</span></span> <span data-ttu-id="e3a82-105">Для настройки подсетей можно использовать панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="e3a82-105">You can use Lync Server Control Panel to configure subnets.</span></span> <span data-ttu-id="e3a82-106">С помощью панели управления Lync Server можно создавать, изменять и удалять подсеть.</span><span class="sxs-lookup"><span data-stu-id="e3a82-106">From the Lync Server Control Panel, you can create, modify, or delete a network subnet.</span></span> <span data-ttu-id="e3a82-107">Более подробную информацию об удалении подсетей можно узнать в статье Удаление подсетей сети [в Lync Server 2013](lync-server-2013-deleting-network-subnets.md).</span><span class="sxs-lookup"><span data-stu-id="e3a82-107">For details about deleting network subnets, see [Deleting network subnets in Lync Server 2013](lync-server-2013-deleting-network-subnets.md).</span></span>

<span data-ttu-id="e3a82-108">В большинстве развертываний Microsoft Lync Server 2013, где реализован контроль допуска звонков (CAC), как правило, существует большое количество подсетей.</span><span class="sxs-lookup"><span data-stu-id="e3a82-108">In most deployments of Microsoft Lync Server 2013 where call admission control (CAC) is implemented, there will typically be a large number of subnets.</span></span> <span data-ttu-id="e3a82-109">Поэтому часто лучше настроить подсети из командной консоли Lync Server.</span><span class="sxs-lookup"><span data-stu-id="e3a82-109">Because of this, it is often best to configure subnets from the Lync Server Management Shell.</span></span> <span data-ttu-id="e3a82-110">Отсюда вы можете вызвать командлет **New-CsNetworkSubnet** в сочетании с командлетом Windows PowerShell **Import-CSV**.</span><span class="sxs-lookup"><span data-stu-id="e3a82-110">From there you can call **New-CsNetworkSubnet** in conjunction with the Windows PowerShell cmdlet **Import-CSV**.</span></span> <span data-ttu-id="e3a82-111">Используя эти командлеты, вы можете считывать параметры подсетей из файла данных с разделителями-запятыми  (CSV) и одновременно создавать несколько сетей.</span><span class="sxs-lookup"><span data-stu-id="e3a82-111">By using these cmdlets together, you can read in subnet settings from a comma-separated values (.csv) file and create multiple subnets at the same time.</span></span> <span data-ttu-id="e3a82-112">Примеры создания подсетей из файла CSV см. в разделе [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet).</span><span class="sxs-lookup"><span data-stu-id="e3a82-112">For examples of how to create subnets from a .csv file, see [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet).</span></span>

<div>

## <a name="to-create-a-network-subnet"></a><span data-ttu-id="e3a82-113">Создание подсети</span><span class="sxs-lookup"><span data-stu-id="e3a82-113">To create a network subnet</span></span>

1.  <span data-ttu-id="e3a82-114">Из учетной записи пользователя, которая является членом группы RTCUniversalServerAdmins (или имеет эквивалентные права пользователя) или назначается роли CsAdministrator, войдите на любой компьютер во внутреннем развертывании.</span><span class="sxs-lookup"><span data-stu-id="e3a82-114">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="e3a82-115">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="e3a82-115">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="e3a82-116">Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="e3a82-116">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="e3a82-117">В левой панели навигации щелкните элемент **Network Configuration** (Параметры сети), а затем **Subnet** (Подсеть).</span><span class="sxs-lookup"><span data-stu-id="e3a82-117">In the left navigation bar, click **Network Configuration** and then click **Subnet**.</span></span>

4.  <span data-ttu-id="e3a82-118">На странице **Subnet** (Подсеть) нажмите кнопку **New** (Создать).</span><span class="sxs-lookup"><span data-stu-id="e3a82-118">On the **Subnet** page, click **New**.</span></span>

5.  <span data-ttu-id="e3a82-p104">Введите значение в поле **Subnet ID** (Идентификатор подсети) окна **New Subnet** (Новая подсеть). Это должен быть IP-адрес (например, 174.11.12.0), и он должен быть первым адресом из диапазона IP-адресов, определенного этой подсетью.</span><span class="sxs-lookup"><span data-stu-id="e3a82-p104">In **New Subnet**, enter a value in the **Subnet ID** field. This must be an IP address (for example, 174.11.12.0), and it must be the first address in the IP address range defined by the subnet.</span></span>

6.  <span data-ttu-id="e3a82-121">В поле **Mask** (Маска) введите числовое значение от 1 до 32.</span><span class="sxs-lookup"><span data-stu-id="e3a82-121">In the **Mask** field, enter a numeric value from 1 through 32.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="e3a82-122">Это значение является битовой маской, применяемой к создаваемой подсети.</span><span class="sxs-lookup"><span data-stu-id="e3a82-122">This value is the bitmask that is to be applied to the subnet being created.</span></span>

    
    </div>

7.  <span data-ttu-id="e3a82-123">В области **Network site ID** (Идентификатор сетевого узла) выберите узел, к которому относится данная подсеть.</span><span class="sxs-lookup"><span data-stu-id="e3a82-123">In **Network site ID**, select the site to which this subnet belongs.</span></span>

8.  <span data-ttu-id="e3a82-124">(Необязательно) Введите значение в поле **Description** (Описание), чтобы предоставить дополнительную информацию о данной подсети, которую нельзя выразить одним только именем.</span><span class="sxs-lookup"><span data-stu-id="e3a82-124">(Optional) Type a value in the **Description** field to provide more information about this subnet that cannot be expressed by the name alone.</span></span>

9.  <span data-ttu-id="e3a82-125">Щелкните элемент **Commit** (Зафиксировать).</span><span class="sxs-lookup"><span data-stu-id="e3a82-125">Click **Commit**.</span></span>

</div>

<div>

## <a name="to-modify-a-network-subnet"></a><span data-ttu-id="e3a82-126">Изменение подсети</span><span class="sxs-lookup"><span data-stu-id="e3a82-126">To modify a network subnet</span></span>

1.  <span data-ttu-id="e3a82-127">Из учетной записи пользователя, которая является членом группы RTCUniversalServerAdmins (или имеет эквивалентные права пользователя) или назначается роли CsAdministrator, войдите на любой компьютер во внутреннем развертывании.</span><span class="sxs-lookup"><span data-stu-id="e3a82-127">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="e3a82-128">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="e3a82-128">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="e3a82-129">Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="e3a82-129">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="e3a82-130">В левой панели навигации щелкните элемент **Network Configuration** (Параметры сети), а затем **Subnet** (Подсеть).</span><span class="sxs-lookup"><span data-stu-id="e3a82-130">In the left navigation bar, click **Network Configuration** and then click **Subnet**.</span></span>

4.  <span data-ttu-id="e3a82-131">На странице **Subnet** (Подсеть) щелкните подсеть, которую хотите изменить.</span><span class="sxs-lookup"><span data-stu-id="e3a82-131">On the **Subnet** page, click the subnet that you want to modify.</span></span>

5.  <span data-ttu-id="e3a82-132">В меню **Edit** (Правка) щелкните пункт  **Show details** (Показать подробности).</span><span class="sxs-lookup"><span data-stu-id="e3a82-132">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="e3a82-p106">На странице **Edit Subnet** (Изменение подсети) вы можете изменить битовую маску, сопоставленную с сетевым узлом, или описание. При изменении битовой маски помните о том, что параметр идентификатора подсети должен оставаться первым адресом из диапазона IP-адресов, определенного этой подсетью.</span><span class="sxs-lookup"><span data-stu-id="e3a82-p106">On the **Edit Subnet** page, you can modify the bitmask, associated network site, or description. If you modify the bitmask, keep in mind that the Subnet ID must still be the first address in the IP address range defined by the subnet.</span></span>

7.  <span data-ttu-id="e3a82-135">Щелкните элемент **Commit** (Зафиксировать).</span><span class="sxs-lookup"><span data-stu-id="e3a82-135">Click **Commit**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="e3a82-136">См. также</span><span class="sxs-lookup"><span data-stu-id="e3a82-136">See Also</span></span>


[<span data-ttu-id="e3a82-137">Удаление сетевых подсетей в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e3a82-137">Deleting network subnets in Lync Server 2013</span></span>](lync-server-2013-deleting-network-subnets.md)  


[<span data-ttu-id="e3a82-138">Сведения о регионах сети, сайтах и подсетях в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e3a82-138">About network regions, sites, and subnets in Lync Server 2013</span></span>](lync-server-2013-about-network-regions-sites-and-subnets.md)  


[<span data-ttu-id="e3a82-139">New — CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="e3a82-139">New-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet)  
[<span data-ttu-id="e3a82-140">Set — CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="e3a82-140">Set-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkSubnet)  
[<span data-ttu-id="e3a82-141">Remove — CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="e3a82-141">Remove-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkSubnet)  
[<span data-ttu-id="e3a82-142">Get — CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="e3a82-142">Get-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSubnet)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

