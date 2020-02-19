---
title: 'Lync Server 2013: Просмотр сведений о связи между областями сети'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Viewing network region link information
ms:assetid: 7b6b2ea2-83d8-4376-afb2-70e5d2cf6444
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688102(v=OCS.15)
ms:contentKeyID: 49733701
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 12e6cb2ec4d86f24e169bfd925c9dcdf08973646
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42138140"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="viewing-network-region-link-information-in-lync-server-2013"></a><span data-ttu-id="7c853-102">Просмотр сведений о связи между областями сети в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7c853-102">Viewing network region link information in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7c853-103">_**Последнее изменение темы:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="7c853-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="7c853-104">Вы можете просмотреть каналы между двумя областями сети как часть контроля допуска звонков (CAC).</span><span class="sxs-lookup"><span data-stu-id="7c853-104">You can view links between two network regions as part of call admission control (CAC).</span></span> <span data-ttu-id="7c853-105">Регионы в сети связываются с помощью физического подключения глобальной сети.</span><span class="sxs-lookup"><span data-stu-id="7c853-105">Regions within a network are linked through physical wide area network (WAN) connectivity.</span></span> <span data-ttu-id="7c853-106">Вы можете использовать панель управления Lync Server для просмотра существующей связи между двумя областями сети.</span><span class="sxs-lookup"><span data-stu-id="7c853-106">You can use the Lync Server Control Panel to view an existing link between two network regions.</span></span> <span data-ttu-id="7c853-107">Дополнительные сведения о создании или изменении связи между областями сети содержатся [в разделе Настройка связей между областями сети в Lync Server 2013](lync-server-2013-configuring-network-region-links.md).</span><span class="sxs-lookup"><span data-stu-id="7c853-107">For details about creating or modifying network region link, see [Configuring network region links in Lync Server 2013](lync-server-2013-configuring-network-region-links.md).</span></span>

<div>

## <a name="to-view-a-network-region-link-in-lync-server-control-panel"></a><span data-ttu-id="7c853-108">Просмотр связи между областями сети в панели управления Lync Server</span><span class="sxs-lookup"><span data-stu-id="7c853-108">To view a network region link in Lync Server Control Panel</span></span>

1.  <span data-ttu-id="7c853-109">Из учетной записи пользователя, которая является членом группы RTCUniversalServerAdmins (или имеет эквивалентные права пользователя) или назначается роли CsAdministrator, войдите на любой компьютер во внутреннем развертывании.</span><span class="sxs-lookup"><span data-stu-id="7c853-109">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="7c853-110">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="7c853-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="7c853-111">Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="7c853-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="7c853-112">В левой панели навигации щелкните **Конфигурация сети**, а затем щелкните **Связь между областями**.</span><span class="sxs-lookup"><span data-stu-id="7c853-112">In the left navigation bar, click **Network Configuration** and then click **Region Link**.</span></span>

4.  <span data-ttu-id="7c853-113">На странице **Канал области** щелкните канал области, который нужно просмотреть.</span><span class="sxs-lookup"><span data-stu-id="7c853-113">On the **Region Link** page, click the region link that you want to view.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="7c853-114">За один раз вы можете просмотреть сведения только об одном канале области.</span><span class="sxs-lookup"><span data-stu-id="7c853-114">You can only view information about one region link at a time.</span></span>

    
    </div>

5.  <span data-ttu-id="7c853-115">В меню **Правка** щелкните пункт **Показать подробности**.</span><span class="sxs-lookup"><span data-stu-id="7c853-115">From the **Edit** menu, select **Show details**.</span></span>

</div>

<div>

## <a name="viewing-network-region-link-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="7c853-116">Просмотр сведений о связи между областями сети с помощью командлетов Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="7c853-116">Viewing Network Region Link Information by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="7c853-117">Вы можете просматривать связи между областями сети с помощью Windows PowerShell и командлета **Get – кснетворкрегионлинк** .</span><span class="sxs-lookup"><span data-stu-id="7c853-117">You can view network region links by using Windows PowerShell and the **Get-CsNetworkRegionLink** cmdlet.</span></span> <span data-ttu-id="7c853-118">Этот командлет можно выполнить из командной консоли Lync Server 2013 или из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7c853-118">You can run this cmdlet from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="7c853-119">Сведения об использовании удаленной оболочки Windows PowerShell для подключения к Lync Server приведены в статье "Краткое руководство по управлению Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" в [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)статье Lync Server Windows PowerShell в блоге.</span><span class="sxs-lookup"><span data-stu-id="7c853-119">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-view-network-region-link-information"></a><span data-ttu-id="7c853-120">Просмотр сведений о канале области сети</span><span class="sxs-lookup"><span data-stu-id="7c853-120">To view network region link information</span></span>

  - <span data-ttu-id="7c853-121">Чтобы просмотреть сведения о всех ссылках на область сети, введите следующую команду в командной консоли Lync Server и нажмите клавишу ВВОД:</span><span class="sxs-lookup"><span data-stu-id="7c853-121">To view information about all your network region links, type the following command in the Lync Server Management Shell and then press ENTER:</span></span>
    
        Get-CsNetworkRegionLink
    
    <span data-ttu-id="7c853-122">Этой командой возвращается информация, аналогичная следующим сведениям:</span><span class="sxs-lookup"><span data-stu-id="7c853-122">This command returns information similar to the following:</span></span>
    
        Identity            : NorthwestToCalifornia
        BWPolicyProfileID   :
        NetworkRegionLinkID : NorthwestToCalifornia
        NetworkRegionID1    : Pacific Northwest
        NetworkRegionID2    : California

</div>

<span data-ttu-id="7c853-123">Дополнительные сведения см. в разделе [Get-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink).</span><span class="sxs-lookup"><span data-stu-id="7c853-123">For details, see [Get-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="7c853-124">См. также</span><span class="sxs-lookup"><span data-stu-id="7c853-124">See Also</span></span>


[<span data-ttu-id="7c853-125">Настройка связей между сетевыми сайтами в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7c853-125">Configuring network site links in Lync Server 2013</span></span>](lync-server-2013-configuring-network-site-links.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

