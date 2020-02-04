---
title: 'Lync Server 2013: создание ссылок на сетевой регион'
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
ms.openlocfilehash: f40b9d569cbc571fe931a53b6f399b6273efd055
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740249"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-network-region-links-in-lync-server-2013"></a><span data-ttu-id="5b729-102">Создание ссылок на сетевой регион в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5b729-102">Create network region links in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5b729-103">_**Тема последнего изменения:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="5b729-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="5b729-104">Регионы в сети связываются с помощью физического подключения глобальной сети.</span><span class="sxs-lookup"><span data-stu-id="5b729-104">Regions within a network are linked through physical WAN connectivity.</span></span> <span data-ttu-id="5b729-105">*Связь по сетевому региону* создает связь между двумя областями, настроенными для управления допуском звонков (CAC), и определяет ограничения пропускной способности для звуковых и видеофайлов в этих регионах.</span><span class="sxs-lookup"><span data-stu-id="5b729-105">A *network region link* creates a link between two regions configured for call admission control (CAC) and sets the bandwidth limitations on audio and video traffic between these regions.</span></span>

<span data-ttu-id="5b729-106">Дополнительные сведения о работе с ссылками на сетевой регион можно найти в документации по оболочке Lync Server Management Shell для следующих командлетов:</span><span class="sxs-lookup"><span data-stu-id="5b729-106">For details about working with network region links, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - [<span data-ttu-id="5b729-107">New-CsNetworkRegionLink</span><span class="sxs-lookup"><span data-stu-id="5b729-107">New-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegionLink)

  - [<span data-ttu-id="5b729-108">Get-CsNetworkRegionLink</span><span class="sxs-lookup"><span data-stu-id="5b729-108">Get-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink)

  - [<span data-ttu-id="5b729-109">Set-CsNetworkRegionLink</span><span class="sxs-lookup"><span data-stu-id="5b729-109">Set-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkRegionLink)

  - [<span data-ttu-id="5b729-110">Remove-CsNetworkRegionLink</span><span class="sxs-lookup"><span data-stu-id="5b729-110">Remove-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkRegionLink)

<span data-ttu-id="5b729-111">В примере топологии есть связь между областями "Северная Америка" и "APAC", а также ссылкой между регионами EMEA и APAC.</span><span class="sxs-lookup"><span data-stu-id="5b729-111">The example topology has a link between the North America and APAC regions, and a link between the EMEA and APAC regions.</span></span> <span data-ttu-id="5b729-112">Каждая из этих связей между регионами ограничена пропускной способностью по сети, как описано в таблице сведения о пропускной способности связи по регионам в [примере: сбор требований для управления допуском звонков в Lync Server 2013 в](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md) разделе Документация по планированию.</span><span class="sxs-lookup"><span data-stu-id="5b729-112">Each of these region links is constrained by WAN bandwidth, as described in Region Link Bandwidth Information table in the [Example: Gathering your requirements for call admission control in Lync Server 2013](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md) section of the Planning documentation.</span></span>

<div>

## <a name="to-create-network-region-links-by-using-lync-server-management-shell"></a><span data-ttu-id="5b729-113">Создание ссылок на сетевой регион с помощью среды управления Lync Server</span><span class="sxs-lookup"><span data-stu-id="5b729-113">To create network region links by using Lync Server Management Shell</span></span>

1.  <span data-ttu-id="5b729-114">Запустите командную консоль Lync Server Management Shell: нажмите кнопку **Пуск**, выберите **все программы**, а затем — **Microsoft Lync Server 2013**, а затем — **Командная консоль Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="5b729-114">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="5b729-115">Запустите командлет New-CsNetworkRegionLink, чтобы создать связи между областями и примените соответствующие профили политики пропускной способности.</span><span class="sxs-lookup"><span data-stu-id="5b729-115">Run the New-CsNetworkRegionLink cmdlet to create the region links and apply appropriate bandwidth policy profiles.</span></span> <span data-ttu-id="5b729-116">Например, выполните командлет:</span><span class="sxs-lookup"><span data-stu-id="5b729-116">For example, run:</span></span>
    
      ```powershell
        New-CsNetworkRegionLink -NetworkRegionLinkID NA-EMEA-LINK -NetworkRegionID1 NorthAmerica -NetworkRegionID2 EMEA -BWPolicyProfileID 50Mb_Link
      ```
    
      ```powershell
        New-CsNetworkRegionLink -NetworkRegionLinkID EMEA-APAC-LINK -NetworkRegionID1 EMEA -NetworkRegionID2 APAC -BWPolicyProfileID 25Mb_Link
      ```

</div>

<div>

## <a name="to-create-network-region-links-by-using-lync-server-control-panel"></a><span data-ttu-id="5b729-117">Создание ссылок на сетевой регион с помощью панели управления Lync Server</span><span class="sxs-lookup"><span data-stu-id="5b729-117">To create network region links by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="5b729-118">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="5b729-118">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="5b729-119">Дополнительные сведения о различных способах, которые можно использовать для запуска панели управления Lync Server, приведены в разделе [Открытие меню администрирования Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="5b729-119">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

2.  <span data-ttu-id="5b729-120">В левой области навигации щелкните элемент **Конфигурация сети**.</span><span class="sxs-lookup"><span data-stu-id="5b729-120">In the left navigation bar, click **Network Configuration**.</span></span>

3.  <span data-ttu-id="5b729-121">Нажмите кнопку навигации **Связь между областями**.</span><span class="sxs-lookup"><span data-stu-id="5b729-121">Click the **Region Link** navigation button.</span></span>

4.  <span data-ttu-id="5b729-122">Выберите **Создать**.</span><span class="sxs-lookup"><span data-stu-id="5b729-122">Click **New**.</span></span>

5.  <span data-ttu-id="5b729-123">На странице **Создание связи между областями** щелкните поле **Имя** и введите имя для связи между областями сети.</span><span class="sxs-lookup"><span data-stu-id="5b729-123">On the **New Region Link** page, click **Name** and then type a name for the network region link.</span></span>

6.  <span data-ttu-id="5b729-124">Щелкните **сетевую \#область 1**, а затем щелкните в списке сетевой регион, который вы хотите связать с сетевым регионом \#2.</span><span class="sxs-lookup"><span data-stu-id="5b729-124">Click **Network Region \#1**, and then click the network region in the list that you want to link to Network Region \#2.</span></span>

7.  <span data-ttu-id="5b729-125">Щелкните **Сетевое \#окружение 2**, а затем щелкните сетевой регион в списке, который вы хотите связать с сетевым регионом \#1.</span><span class="sxs-lookup"><span data-stu-id="5b729-125">Click **Network Region \#2**, and then click a network region in the list that you want to link to Network Region \#1.</span></span>

8.  <span data-ttu-id="5b729-126">Кроме того, можно щелкнуть элемент **Политика пропускной способности**, а затем выбрать профиль политики пропускной способности, который требуется применить к связи между областями сети.</span><span class="sxs-lookup"><span data-stu-id="5b729-126">Optionally, click **Bandwidth policy**, and then select the bandwidth policy profile that you want to apply to the network region link.</span></span>
    
    <div class=" ">
    

    > [!NOTE]  
    > <span data-ttu-id="5b729-127">Применять политику пропускной способности следует только в том случае, если для связи между областями сети имеются ограничения полосы пропускания и требуется использовать CAC для управления трафиком среды по этому каналу.</span><span class="sxs-lookup"><span data-stu-id="5b729-127">Apply a bandwidth policy only if the network region link is bandwidth-constrained and you want to use CAC to control media traffic on that link.</span></span>

    
    </div>

9.  <span data-ttu-id="5b729-128">Нажмите **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="5b729-128">Click **Commit**.</span></span>

10. <span data-ttu-id="5b729-129">Чтобы завершить создание связи между областями сети для топологии, повторите шаги с 4 по 9 с настройками для других областей.</span><span class="sxs-lookup"><span data-stu-id="5b729-129">To finish creating network region links for your topology, repeat steps 4 through 9 with settings for other regions.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>
