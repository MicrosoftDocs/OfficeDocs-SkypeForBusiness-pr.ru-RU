---
title: 'Lync Server 2013: создание связей между областями сети'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create network region links
ms:assetid: f8163910-8935-475d-88a2-3aa44feb9dbe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413047(v=OCS.15)
ms:contentKeyID: 48185873
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1af9c2d6b651fd127986d89d521e99745e1af384
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42205595"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-network-region-links-in-lync-server-2013"></a><span data-ttu-id="a42d5-102">Создание связей между областями сети в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a42d5-102">Create network region links in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a42d5-103">_**Последнее изменение темы:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="a42d5-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="a42d5-p101">Регионы в сети связываются с помощью физического подключения глобальной сети. *Связь между областями сети* создает канал между двумя областями, настроенными для контроля допуска звонков (CAC), и задает ограничения пропускной способности трафика аудио- и видеоданных между этими областями.</span><span class="sxs-lookup"><span data-stu-id="a42d5-p101">Regions within a network are linked through physical WAN connectivity. A *network region link* creates a link between two regions configured for call admission control (CAC) and sets the bandwidth limitations on audio and video traffic between these regions.</span></span>

<span data-ttu-id="a42d5-106">Для получения подробных сведений о работе с ссылками на область сети обратитесь к документации по командной консоли Lync Server для следующих командлетов:</span><span class="sxs-lookup"><span data-stu-id="a42d5-106">For details about working with network region links, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - [<span data-ttu-id="a42d5-107">New — Кснетворкрегионлинк</span><span class="sxs-lookup"><span data-stu-id="a42d5-107">New-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegionLink)

  - [<span data-ttu-id="a42d5-108">Get — Кснетворкрегионлинк</span><span class="sxs-lookup"><span data-stu-id="a42d5-108">Get-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink)

  - [<span data-ttu-id="a42d5-109">Set — Кснетворкрегионлинк</span><span class="sxs-lookup"><span data-stu-id="a42d5-109">Set-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkRegionLink)

  - [<span data-ttu-id="a42d5-110">Remove — Кснетворкрегионлинк</span><span class="sxs-lookup"><span data-stu-id="a42d5-110">Remove-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkRegionLink)

<span data-ttu-id="a42d5-111">Пример топологии содержит ссылку между регионами "Северная Америка" и "APAC" и ссылку между регионами "EMEA" и "APAC".</span><span class="sxs-lookup"><span data-stu-id="a42d5-111">The example topology has a link between the North America and APAC regions, and a link between the EMEA and APAC regions.</span></span> <span data-ttu-id="a42d5-112">Каждая из этих связей между регионами ограничена пропускной способностью WAN, как описано в таблице сведения о пропускной способности канала связи в [примере: сбор требований для контроля допуска звонков в разделе Lync Server 2013](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md) в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="a42d5-112">Each of these region links is constrained by WAN bandwidth, as described in Region Link Bandwidth Information table in the [Example: Gathering your requirements for call admission control in Lync Server 2013](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md) section of the Planning documentation.</span></span>

<div>

## <a name="to-create-network-region-links-by-using-lync-server-management-shell"></a><span data-ttu-id="a42d5-113">Создание связей между областями с помощью командной консоли Lync Server</span><span class="sxs-lookup"><span data-stu-id="a42d5-113">To create network region links by using Lync Server Management Shell</span></span>

1.  <span data-ttu-id="a42d5-114">Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="a42d5-114">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="a42d5-p103">Запустите командлет New-CsNetworkRegionLink, чтобы создать связи между областями и примените соответствующие профили политики пропускной способности. Например, выполните командлет:</span><span class="sxs-lookup"><span data-stu-id="a42d5-p103">Run the New-CsNetworkRegionLink cmdlet to create the region links and apply appropriate bandwidth policy profiles. For example, run:</span></span>
    
      ```powershell
        New-CsNetworkRegionLink -NetworkRegionLinkID NA-EMEA-LINK -NetworkRegionID1 NorthAmerica -NetworkRegionID2 EMEA -BWPolicyProfileID 50Mb_Link
      ```
    
      ```powershell
        New-CsNetworkRegionLink -NetworkRegionLinkID EMEA-APAC-LINK -NetworkRegionID1 EMEA -NetworkRegionID2 APAC -BWPolicyProfileID 25Mb_Link
      ```

</div>

<div>

## <a name="to-create-network-region-links-by-using-lync-server-control-panel"></a><span data-ttu-id="a42d5-117">Создание связей между областями с помощью панели управления Lync Server</span><span class="sxs-lookup"><span data-stu-id="a42d5-117">To create network region links by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="a42d5-118">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="a42d5-118">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="a42d5-119">Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="a42d5-119">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

2.  <span data-ttu-id="a42d5-120">В левой области навигации щелкните элемент **Конфигурация сети**.</span><span class="sxs-lookup"><span data-stu-id="a42d5-120">In the left navigation bar, click **Network Configuration**.</span></span>

3.  <span data-ttu-id="a42d5-121">Нажмите кнопку навигации **Region Link** (Связь между областями).</span><span class="sxs-lookup"><span data-stu-id="a42d5-121">Click the **Region Link** navigation button.</span></span>

4.  <span data-ttu-id="a42d5-122">Нажмите кнопку **Создать**.</span><span class="sxs-lookup"><span data-stu-id="a42d5-122">Click **New**.</span></span>

5.  <span data-ttu-id="a42d5-123">На странице **New Region Link** (Создание связи между областями) щелкните поле **Имя** и введите имя для связи между областями сети.</span><span class="sxs-lookup"><span data-stu-id="a42d5-123">On the **New Region Link** page, click **Name** and then type a name for the network region link.</span></span>

6.  <span data-ttu-id="a42d5-124">Щелкните **область \#сети 1**, а затем выберите в списке область сети, которую требуется связать с областью \#сети 2.</span><span class="sxs-lookup"><span data-stu-id="a42d5-124">Click **Network Region \#1**, and then click the network region in the list that you want to link to Network Region \#2.</span></span>

7.  <span data-ttu-id="a42d5-125">Щелкните **область \#сети 2**, а затем выберите регион сети в списке, который необходимо связать с областью \#сети 1.</span><span class="sxs-lookup"><span data-stu-id="a42d5-125">Click **Network Region \#2**, and then click a network region in the list that you want to link to Network Region \#1.</span></span>

8.  <span data-ttu-id="a42d5-126">Кроме того, можно щелкнуть элемент **Bandwidth policy** (Политика пропускной способности), а затем выбрать профиль политики пропускной способности, который требуется применить к связи между областями сети.</span><span class="sxs-lookup"><span data-stu-id="a42d5-126">Optionally, click **Bandwidth policy**, and then select the bandwidth policy profile that you want to apply to the network region link.</span></span>
    
    <div class=" ">
    

    > [!NOTE]  
    > <span data-ttu-id="a42d5-127">Применять политику пропускной способности следует только в том случае, если для связи между областями сети имеются ограничения полосы пропускания и требуется использовать CAC для управления трафиком среды по этому каналу.</span><span class="sxs-lookup"><span data-stu-id="a42d5-127">Apply a bandwidth policy only if the network region link is bandwidth-constrained and you want to use CAC to control media traffic on that link.</span></span>

    
    </div>

9.  <span data-ttu-id="a42d5-128">Нажмите кнопку **Зафиксировать**.</span><span class="sxs-lookup"><span data-stu-id="a42d5-128">Click **Commit**.</span></span>

10. <span data-ttu-id="a42d5-129">Чтобы завершить создание связи между областями сети для топологии, повторите шаги с 4 по 9 с настройками для других областей.</span><span class="sxs-lookup"><span data-stu-id="a42d5-129">To finish creating network region links for your topology, repeat steps 4 through 9 with settings for other regions.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>
