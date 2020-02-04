---
title: 'Lync Server 2013: Просмотр сведений о связи с сетевым регионом'
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
ms.openlocfilehash: 935d1a98bd4f446ec8861ae8382eb724611a945f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757283"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="viewing-network-region-link-information-in-lync-server-2013"></a><span data-ttu-id="14a44-102">Просмотр сведений о связи по сетевому региону в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="14a44-102">Viewing network region link information in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="14a44-103">_**Тема последнего изменения:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="14a44-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="14a44-104">Вы можете просматривать ссылки между двумя сетевыми областями в рамках управления допуском звонков (CAC).</span><span class="sxs-lookup"><span data-stu-id="14a44-104">You can view links between two network regions as part of call admission control (CAC).</span></span> <span data-ttu-id="14a44-105">Регионы в сети связаны по ГЛОБАЛЬным сетевым подключениям.</span><span class="sxs-lookup"><span data-stu-id="14a44-105">Regions within a network are linked through physical wide area network (WAN) connectivity.</span></span> <span data-ttu-id="14a44-106">Вы можете просмотреть существующую ссылку между двумя областями сети с помощью панели управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="14a44-106">You can use the Lync Server Control Panel to view an existing link between two network regions.</span></span> <span data-ttu-id="14a44-107">Дополнительные сведения о создании и изменении ссылки на сетевой регион можно найти [в разделе Настройка ссылок на сетевые регионы в Lync Server 2013](lync-server-2013-configuring-network-region-links.md).</span><span class="sxs-lookup"><span data-stu-id="14a44-107">For details about creating or modifying network region link, see [Configuring network region links in Lync Server 2013](lync-server-2013-configuring-network-region-links.md).</span></span>

<div>

## <a name="to-view-a-network-region-link-in-lync-server-control-panel"></a><span data-ttu-id="14a44-108">Просмотр ссылки на сетевой регион на панели управления Lync Server</span><span class="sxs-lookup"><span data-stu-id="14a44-108">To view a network region link in Lync Server Control Panel</span></span>

1.  <span data-ttu-id="14a44-109">Войдите на любой компьютер, находящийся во внутреннем развертывании, с использованием учетной записи, входящей в группу RTCUniversalServerAdmins (или имеющей равнозначные права пользователя) либо назначенной роли CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="14a44-109">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="14a44-110">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="14a44-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="14a44-111">Дополнительные сведения о различных способах, которые можно использовать для запуска панели управления Lync Server, приведены в разделе [Открытие меню администрирования Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="14a44-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="14a44-112">На панели навигации слева выберите пункт **Настройка сети** , а затем щелкните **ссылку Region (регион**).</span><span class="sxs-lookup"><span data-stu-id="14a44-112">In the left navigation bar, click **Network Configuration** and then click **Region Link**.</span></span>

4.  <span data-ttu-id="14a44-113">На странице " **ссылка на регион** " щелкните ссылку "регион", которую вы хотите просмотреть.</span><span class="sxs-lookup"><span data-stu-id="14a44-113">On the **Region Link** page, click the region link that you want to view.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="14a44-114">Вы можете просматривать сведения только о одной ссылке на регион за один раз.</span><span class="sxs-lookup"><span data-stu-id="14a44-114">You can only view information about one region link at a time.</span></span>

    
    </div>

5.  <span data-ttu-id="14a44-115">В меню **Правка** выберите пункт **Показать подробности**.</span><span class="sxs-lookup"><span data-stu-id="14a44-115">From the **Edit** menu, select **Show details**.</span></span>

</div>

<div>

## <a name="viewing-network-region-link-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="14a44-116">Просмотр сведений о связи по сетевому региону с помощью командлетов Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="14a44-116">Viewing Network Region Link Information by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="14a44-117">Вы можете просматривать ссылки на сетевую область с помощью Windows PowerShell и командлета **Get-кснетворкрегионлинк** .</span><span class="sxs-lookup"><span data-stu-id="14a44-117">You can view network region links by using Windows PowerShell and the **Get-CsNetworkRegionLink** cmdlet.</span></span> <span data-ttu-id="14a44-118">Этот командлет можно выполнить из управляющей оболочки Lync Server 2013 или из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="14a44-118">You can run this cmdlet from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="14a44-119">Подробнее об использовании удаленной оболочки Windows PowerShell для подключения к серверу Lync Server можно найти в статье "Краткое руководство по работе с Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" на [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)веб-сервере Lync Server Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="14a44-119">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-view-network-region-link-information"></a><span data-ttu-id="14a44-120">Просмотр сведений о связи по сетевому региону</span><span class="sxs-lookup"><span data-stu-id="14a44-120">To view network region link information</span></span>

  - <span data-ttu-id="14a44-121">Чтобы просмотреть сведения о ссылках на сетевой регион, введите следующую команду в командной консоли Lync Server Management Shell и нажмите клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="14a44-121">To view information about all your network region links, type the following command in the Lync Server Management Shell and then press ENTER:</span></span>
    
        Get-CsNetworkRegionLink
    
    <span data-ttu-id="14a44-122">Этой командой возвращается информация, аналогичная следующим сведениям:</span><span class="sxs-lookup"><span data-stu-id="14a44-122">This command returns information similar to the following:</span></span>
    
        Identity            : NorthwestToCalifornia
        BWPolicyProfileID   :
        NetworkRegionLinkID : NorthwestToCalifornia
        NetworkRegionID1    : Pacific Northwest
        NetworkRegionID2    : California

</div>

<span data-ttu-id="14a44-123">Подробности можно найти в [статьях Get-кснетворкрегионлинк](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink).</span><span class="sxs-lookup"><span data-stu-id="14a44-123">For details, see [Get-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="14a44-124">См. также</span><span class="sxs-lookup"><span data-stu-id="14a44-124">See Also</span></span>


[<span data-ttu-id="14a44-125">Настройка связей сайтов сети в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="14a44-125">Configuring network site links in Lync Server 2013</span></span>](lync-server-2013-configuring-network-site-links.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

