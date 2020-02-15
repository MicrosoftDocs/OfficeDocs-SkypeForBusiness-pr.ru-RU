---
title: 'Lync Server 2013: Настройка сетевых сайтов для контроля допуска звонков'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure network sites for CAC
ms:assetid: afcea38f-5789-45ec-97af-c6e38364950c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412840(v=OCS.15)
ms:contentKeyID: 48185144
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f449d26515c6790ec8582676ca57ed897f12dc40
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030823"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-network-sites-for-cac-in-lync-server-2013"></a><span data-ttu-id="96fcc-102">Настройка сетевых сайтов для контроля допуска звонков в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="96fcc-102">Configure network sites for CAC in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="96fcc-103">_**Последнее изменение темы:** 2012-09-05_</span><span class="sxs-lookup"><span data-stu-id="96fcc-103">_**Topic Last Modified:** 2012-09-05_</span></span>

<div class=" ">


> [!IMPORTANT]  
> <span data-ttu-id="96fcc-104">Если вы уже создали сетевые сайты для службы E9-1-1 или обхода сервера-посредника, то вы можете применить к ним профиль политики пропускной способности с помощью командлета <STRONG>Set-CsNetworkSite</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="96fcc-104">If you have already created network sites for E9-1-1 or media bypass, you can modify the existing network sites to apply a bandwidth policy profile by using the <STRONG>Set-CsNetworkSite</STRONG> cmdlet.</span></span> <span data-ttu-id="96fcc-105">Пример изменения сетевого сайта представлен <A href="lync-server-2013-create-or-modify-a-network-site.md">в статье Создание или изменение сетевого сайта в Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="96fcc-105">For an example of how to modify a network site, see <A href="lync-server-2013-create-or-modify-a-network-site.md">Create or modify a network site in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="96fcc-p102">*Сетевые сайты* — это офисы или расположения в каждой области сети контроля допуска звонков, E9-1-1 и обхода сервера-посредника. Чтобы создать сетевые сайты, соответствующие примеру топологии сети для контроля допуска звонков, используйте следующие процедуры. В этих процедурах демонстрируется создание и настройка сетевых сайтов, на которые распространяется ограничение пропускной способности глобальной сети. Следовательно, для этих сетевых сайтов требуются политики пропускной способности, которые ограничивают трафик звуковых и видеоданных в режиме реального времени.</span><span class="sxs-lookup"><span data-stu-id="96fcc-p102">*Network sites* are the offices or locations within each network region of call admission control (CAC), E9-1-1, and media bypass deployments. Use the following procedures to create network sites that align to network sites in the example network topology for CAC. These procedures show how to create and configure network sites that are constrained by WAN bandwidth and therefore require bandwidth policies that limit real-time audio or video traffic flow.</span></span>

<span data-ttu-id="96fcc-109">В примере развертывания контроля допуска звонков регион Северная Америка содержит 6 сайтов.</span><span class="sxs-lookup"><span data-stu-id="96fcc-109">In the example CAC deployment, the North America region has six sites.</span></span> <span data-ttu-id="96fcc-110">На 3 сайта распространяется ограничение пропускной способности глобальной сети: Рино, Портленд и Альбукерке.</span><span class="sxs-lookup"><span data-stu-id="96fcc-110">Three of these sites are constrained by WAN bandwidth: Reno, Portland, and Albuquerque.</span></span> <span data-ttu-id="96fcc-111">На оставшиеся 3 сайта ограничение пропускной способности глобальной сети *не* действует: Нью-Йорк, Чикаго и Детройт.</span><span class="sxs-lookup"><span data-stu-id="96fcc-111">The other three sites, which are *not* constrained by WAN bandwidth: New York, Chicago, and Detroit.</span></span> <span data-ttu-id="96fcc-112">Пример создания или изменения этих других сетевых сайтов представлен [в статье Создание или изменение сетевого сайта в Lync Server 2013](lync-server-2013-create-or-modify-a-network-site.md).</span><span class="sxs-lookup"><span data-stu-id="96fcc-112">For an example of how to create or modify those other network sites, see [Create or modify a network site in Lync Server 2013](lync-server-2013-create-or-modify-a-network-site.md).</span></span>

<span data-ttu-id="96fcc-113">Пример сетевой топологии представлен в статье [Пример: сбор требований для контроля допуска звонков в Lync Server 2013](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md) в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="96fcc-113">To view the example network topology, see [Example: Gathering your requirements for call admission control in Lync Server 2013](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md) in the Planning documentation.</span></span>

<div class=" ">


> [!NOTE]  
> <span data-ttu-id="96fcc-114">В следующей процедуре для создания сетевого сайта используется Командная консоль Lync Server.</span><span class="sxs-lookup"><span data-stu-id="96fcc-114">In the following procedure, Lync Server Management Shell is used to create a network site.</span></span> <span data-ttu-id="96fcc-115">Дополнительные сведения об использовании панели управления Lync Server для создания сетевого сайта можно узнать <A href="lync-server-2013-create-or-modify-a-network-site.md">в статье Создание или изменение сетевого сайта в Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="96fcc-115">For details about using Lync Server Control Panel to create a network site, see <A href="lync-server-2013-create-or-modify-a-network-site.md">Create or modify a network site in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-create-network-sites-for-call-admission-control"></a><span data-ttu-id="96fcc-116">Создание сетевых узлов для контроля допуска звонков</span><span class="sxs-lookup"><span data-stu-id="96fcc-116">To create network sites for call admission control</span></span>

1.  <span data-ttu-id="96fcc-117">Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="96fcc-117">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="96fcc-118">Чтобы создать сетевые сайты и применить требуемый профиль политики пропускной способности для каждого сайта, выполните командлет **New-CsNetworkSite**.</span><span class="sxs-lookup"><span data-stu-id="96fcc-118">Run the **New-CsNetworkSite** cmdlet to create network sites and apply an appropriate bandwidth policy profile to each site.</span></span> <span data-ttu-id="96fcc-119">Пример:</span><span class="sxs-lookup"><span data-stu-id="96fcc-119">For example, run:</span></span>
    
       ```powershell
        New-CsNetworkSite -NetworkSiteID Reno -Description "NA:Branch office for sales force" -NetworkRegionID NorthAmerica -BWPolicyProfileID 10MB_Link
       ```
    
       ```powershell
        New-CsNetworkSite -NetworkSiteID Portland -Description "NA:Branch office for marketing force" -NetworkRegionID NorthAmerica -BWPolicyProfileID 5MB_Link
       ```
    
       ```powershell
        New-CsNetworkSite -NetworkSiteID Albuquerque -Description "NA:Branch office for SouthWest sales" -NetworkRegionID EMEA -BWPolicyProfileID 10MB_Link
       ```

3.  <span data-ttu-id="96fcc-120">Чтобы завершить создание сетевых сайтов для всего примера топологии, повторите шаг 2 для сетевых сайтов с ограничением пропускной способности, расположенных в Европе, на Ближнем Востоке и в Африке, а также в Азиатско-тихоокеанском регионе.</span><span class="sxs-lookup"><span data-stu-id="96fcc-120">To finish creating network sites for the entire example topology, repeat step 2 for the bandwidth-constrained network sites in the EMEA and APAC regions.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

