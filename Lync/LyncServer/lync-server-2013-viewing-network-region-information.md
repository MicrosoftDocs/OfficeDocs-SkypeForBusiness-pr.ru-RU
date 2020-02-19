---
title: 'Lync Server 2013: Просмотр сведений о области сети'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Viewing network region information
ms:assetid: 665740d0-a3ed-460f-8337-5ed945f90589
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688076(v=OCS.15)
ms:contentKeyID: 49733672
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8ba46c4ab3ed7fd6930faf359bc964605285a953
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42138150"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="viewing-network-region-information-in-lync-server-2013"></a><span data-ttu-id="2b5ce-102">Просмотр сведений о области сети в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2b5ce-102">Viewing network region information in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2b5ce-103">_**Последнее изменение темы:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="2b5ce-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="2b5ce-104">Область сети связывает части сети, расположенные в различных географических районах.</span><span class="sxs-lookup"><span data-stu-id="2b5ce-104">A network region interconnects various parts of a network across multiple geographic areas.</span></span> <span data-ttu-id="2b5ce-105">Каждый регион сети должен быть связан с центральным сайтом.</span><span class="sxs-lookup"><span data-stu-id="2b5ce-105">Every network region must be associated with a central site.</span></span> <span data-ttu-id="2b5ce-106">Центральный сайт — это сайт центра обработки данных, на котором выполняется служба политики пропускной способности для контроля допуска звонков.</span><span class="sxs-lookup"><span data-stu-id="2b5ce-106">The central site is the data center site on which the call admission control (CAC) bandwidth policy service is running.</span></span> <span data-ttu-id="2b5ce-107">Для просмотра областей сети можно использовать панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="2b5ce-107">You can use Lync Server Control Panel to view network regions.</span></span> <span data-ttu-id="2b5ce-108">Области сети включают параметры, которые определяют, разрешены ли альтернативные пути через Интернет для аудио- и видеоподключений.</span><span class="sxs-lookup"><span data-stu-id="2b5ce-108">Network regions include settings that determine whether alternate paths through the Internet are allowed for audio and video connections.</span></span> <span data-ttu-id="2b5ce-109">Используйте этот раздел для просмотра существующих областей сети.</span><span class="sxs-lookup"><span data-stu-id="2b5ce-109">Use this topic to view existing network regions.</span></span> <span data-ttu-id="2b5ce-110">Сведения о создании или изменении существующих областей сети приведены в статье [Создание или изменение областей сети в Lync Server 2013](lync-server-2013-creating-or-modifying-network-regions.md).</span><span class="sxs-lookup"><span data-stu-id="2b5ce-110">For details about creating or modifying existing network regions, see [Creating or modifying network regions in Lync Server 2013](lync-server-2013-creating-or-modifying-network-regions.md).</span></span>

<div>

## <a name="to-view-information-about-a-network-region-with-lync-server-control-panel"></a><span data-ttu-id="2b5ce-111">Просмотр сведений о области сети с помощью панели управления Lync Server</span><span class="sxs-lookup"><span data-stu-id="2b5ce-111">To view information about a network region with Lync Server Control Panel</span></span>

1.  <span data-ttu-id="2b5ce-112">Из учетной записи пользователя, которая является членом группы RTCUniversalServerAdmins (или имеет эквивалентные права пользователя) или назначается роли CsAdministrator, войдите на любой компьютер во внутреннем развертывании.</span><span class="sxs-lookup"><span data-stu-id="2b5ce-112">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="2b5ce-113">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="2b5ce-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="2b5ce-114">Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="2b5ce-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="2b5ce-115">На левой панели навигации щелкните **Конфигурация сети**, затем **Регион**.</span><span class="sxs-lookup"><span data-stu-id="2b5ce-115">In the left navigation bar, click **Network Configuration** and then click **Region**.</span></span>

4.  <span data-ttu-id="2b5ce-116">На странице **Регион** щелкните регион, который следует просмотреть.</span><span class="sxs-lookup"><span data-stu-id="2b5ce-116">On the **Region** page, click the region you want to view.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="2b5ce-117">одновременно можно просматривать только один регион.</span><span class="sxs-lookup"><span data-stu-id="2b5ce-117">You can only view one region at a time.</span></span>

    
    </div>

5.  <span data-ttu-id="2b5ce-118">В меню **Изменить** щелкните **Показать сведения**.</span><span class="sxs-lookup"><span data-stu-id="2b5ce-118">On the **Edit** menu, click **Show details**.</span></span>

</div>

<div>

## <a name="viewing-network-region-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="2b5ce-119">Просмотр сведений о области сети с помощью командлетов Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="2b5ce-119">Viewing Network Region Information by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="2b5ce-120">Сведения о области сети можно просмотреть с помощью Windows PowerShell и командлета **Get – CsNetworkRegion** .</span><span class="sxs-lookup"><span data-stu-id="2b5ce-120">You can view network region information by using Windows PowerShell and the **Get-CsNetworkRegion** cmdlet.</span></span> <span data-ttu-id="2b5ce-121">Этот командлет можно выполнить либо из командной консоли Lync Server 2013, либо из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2b5ce-121">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="2b5ce-122">Сведения об использовании удаленной оболочки Windows PowerShell для подключения к Lync Server приведены в статье "Краткое руководство по управлению Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" в [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)статье Lync Server Windows PowerShell в блоге.</span><span class="sxs-lookup"><span data-stu-id="2b5ce-122">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-view-network-region-information"></a><span data-ttu-id="2b5ce-123">Просмотр сведений о области сети</span><span class="sxs-lookup"><span data-stu-id="2b5ce-123">To view network region information</span></span>

  - <span data-ttu-id="2b5ce-124">Чтобы просмотреть сведения обо всех регионах сети, введите следующую команду в командной консоли Lync Server, а затем нажмите клавишу ВВОД:</span><span class="sxs-lookup"><span data-stu-id="2b5ce-124">To view information about all your network regions, type the following command in the Lync Server Management Shell and then press ENTER:</span></span>
    
        Get-CsNetworkRegion
    
    <span data-ttu-id="2b5ce-125">Это приведет к возврату приблизительно такой информации:</span><span class="sxs-lookup"><span data-stu-id="2b5ce-125">That will return information similar to this:</span></span>
    
        Identity         : Pacific Northwest
        Description      :
        BypassID         : 3b232b84-2c1d-4da2-8181-e9330bafebe9
        CentralSite      : Site:Redmond1
        BWAlternatePaths : {BWPolicyModality=Audio;AlternatePath=True, 
                           BWPolicyModality=Video;AlternatePath=True}
        NetworkRegionID  : Pacific Northwest

</div>

<span data-ttu-id="2b5ce-126">Дополнительные сведения см. в разделе справки по командлету [Get-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink).</span><span class="sxs-lookup"><span data-stu-id="2b5ce-126">For more information, see the help topic for the [Get-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="2b5ce-127">См. также</span><span class="sxs-lookup"><span data-stu-id="2b5ce-127">See Also</span></span>


[<span data-ttu-id="2b5ce-128">Создание или изменение областей сети в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2b5ce-128">Creating or modifying network regions in Lync Server 2013</span></span>](lync-server-2013-creating-or-modifying-network-regions.md)  
[<span data-ttu-id="2b5ce-129">Удаление существующих областей сети в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2b5ce-129">Deleting existing network regions in Lync Server 2013</span></span>](lync-server-2013-deleting-existing-network-regions.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

