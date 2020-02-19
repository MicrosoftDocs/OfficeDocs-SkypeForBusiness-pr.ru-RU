---
title: 'Lync Server 2013: Просмотр сведений о подсети сети'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Viewing network subnet information
ms:assetid: 46f165f2-efe3-4cc1-9fee-a78b7f2ed41e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688044(v=OCS.15)
ms:contentKeyID: 49733636
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7c0877db4871403c93dffe2fabd0c30df495b9ae
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42138110"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="viewing-network-subnet-information-in-lync-server-2013"></a><span data-ttu-id="66ef0-102">Просмотр сведений о подсети в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="66ef0-102">Viewing network subnet information in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="66ef0-103">_**Последнее изменение темы:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="66ef0-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="66ef0-104">Для просмотра сетевой подсети можно использовать следующую процедуру.</span><span class="sxs-lookup"><span data-stu-id="66ef0-104">You can use the following procedure to view a network subnet.</span></span> <span data-ttu-id="66ef0-105">С помощью панели управления Lync Server можно создавать, изменять и удалять подсеть.</span><span class="sxs-lookup"><span data-stu-id="66ef0-105">From the Lync Server Control Panel, you can create, modify, or delete a network subnet.</span></span> <span data-ttu-id="66ef0-106">Дополнительные сведения о создании или изменении подсетей сети приведены [в статье Создание или изменение подсетей сети в Lync Server 2013](lync-server-2013-create-or-modify-network-subnets.md).</span><span class="sxs-lookup"><span data-stu-id="66ef0-106">For details about creating or modifying network subnets, see [Create or modify network subnets in Lync Server 2013](lync-server-2013-create-or-modify-network-subnets.md).</span></span>

<div>

## <a name="to-view-a-network-subnet"></a><span data-ttu-id="66ef0-107">Чтобы просмотреть подсеть</span><span class="sxs-lookup"><span data-stu-id="66ef0-107">To view a network subnet</span></span>

1.  <span data-ttu-id="66ef0-108">Из учетной записи пользователя, которая является членом группы RTCUniversalServerAdmins (или имеет эквивалентные права пользователя) или назначается роли CsAdministrator, войдите на любой компьютер во внутреннем развертывании.</span><span class="sxs-lookup"><span data-stu-id="66ef0-108">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="66ef0-109">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="66ef0-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="66ef0-110">Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="66ef0-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="66ef0-111">На левой панели навигации щелкните **Конфигурация сети**, затем **Подсеть**.</span><span class="sxs-lookup"><span data-stu-id="66ef0-111">In the left navigation bar, click **Network Configuration** and then click **Subnet**.</span></span>

4.  <span data-ttu-id="66ef0-112">На странице **Подсеть** щелкните подсеть, которую следует просмотреть.</span><span class="sxs-lookup"><span data-stu-id="66ef0-112">On the **Subnet** page, click the subnet that you want to view.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="66ef0-113">Одновременно можно просматривать только одну подсеть.</span><span class="sxs-lookup"><span data-stu-id="66ef0-113">You can only view one subnet at a time.</span></span>

    
    </div>

5.  <span data-ttu-id="66ef0-114">В меню **Изменить** щелкните **Показать сведения**.</span><span class="sxs-lookup"><span data-stu-id="66ef0-114">On the **Edit** menu, click **Show details…**.</span></span>

</div>

<div>

## <a name="viewing-network-subnet-configuration-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="66ef0-115">Просмотр сведений о конфигурации подсети с помощью командлетов Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="66ef0-115">Viewing Network Subnet Configuration Information by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="66ef0-116">Сведения о подсети можно просмотреть с помощью Windows PowerShell и командлета Get – CsNetworkSubnet.</span><span class="sxs-lookup"><span data-stu-id="66ef0-116">Network subnet information can be viewed by using Windows PowerShell and the Get-CsNetworkSubnet cmdlet.</span></span> <span data-ttu-id="66ef0-117">Этот командлет можно запустить либо из командной консоли Lync Server 2013, либо из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="66ef0-117">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="66ef0-118">Сведения об использовании удаленной оболочки Windows PowerShell для подключения к Lync Server приведены в статье "Краткое руководство по управлению Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" в [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)статье Lync Server Windows PowerShell в блоге.</span><span class="sxs-lookup"><span data-stu-id="66ef0-118">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-view-network-subnet-information"></a><span data-ttu-id="66ef0-119">Просмотр сведений о подсети</span><span class="sxs-lookup"><span data-stu-id="66ef0-119">To view network subnet information</span></span>

  - <span data-ttu-id="66ef0-120">Чтобы просмотреть сведения о всех сетевых подсетях, введите в командной консоли Lync Server следующую команду и нажмите клавишу ВВОД:</span><span class="sxs-lookup"><span data-stu-id="66ef0-120">To view information about all your network subnets, type the following command in the Lync Server Management Shell and then press ENTER:</span></span>
    
        Get-CsNetworkSubnet
    
    <span data-ttu-id="66ef0-121">Это приведет к возврату приблизительно такой информации:</span><span class="sxs-lookup"><span data-stu-id="66ef0-121">That will return information similar to this:</span></span>
    
        Identity      : 172.11.15.0
        MaskBits      : 28
        Description   :
        NetworkSiteID : Redmond
        SubnetID      : 172.11.15.0

</div>

<span data-ttu-id="66ef0-122">Дополнительные сведения см. в разделе справки по командлету [Get-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSubnet).</span><span class="sxs-lookup"><span data-stu-id="66ef0-122">For more information, see the help topic for the [Get-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSubnet) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="66ef0-123">См. также</span><span class="sxs-lookup"><span data-stu-id="66ef0-123">See Also</span></span>


[<span data-ttu-id="66ef0-124">Создание или изменение сетевых подсетей в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="66ef0-124">Create or modify network subnets in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-network-subnets.md)  
[<span data-ttu-id="66ef0-125">Удаление сетевых подсетей в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="66ef0-125">Deleting network subnets in Lync Server 2013</span></span>](lync-server-2013-deleting-network-subnets.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

