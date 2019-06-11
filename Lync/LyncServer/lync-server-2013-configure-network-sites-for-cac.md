---
title: 'Lync Server 2013: Настройка сетевых сайтов для CAC'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure network sites for CAC
ms:assetid: afcea38f-5789-45ec-97af-c6e38364950c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412840(v=OCS.15)
ms:contentKeyID: 48185144
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 528ed67243fb0ab0451abf504a458afc420d94ea
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34841341"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-network-sites-for-cac-in-lync-server-2013"></a><span data-ttu-id="c3366-102">Настройка сетевых сайтов для CAC в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c3366-102">Configure network sites for CAC in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c3366-103">_**Тема последнего изменения:** 2012-09-05_</span><span class="sxs-lookup"><span data-stu-id="c3366-103">_**Topic Last Modified:** 2012-09-05_</span></span>

<div class=" ">


> [!IMPORTANT]  
> <span data-ttu-id="c3366-104">Если вы уже создали сайты сети для E9-1 или мультимедиа, вы можете изменить существующие сайты сети, чтобы применить профиль политики пропускной способности с помощью командлета <STRONG>Set-кснетворксите</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="c3366-104">If you have already created network sites for E9-1-1 or media bypass, you can modify the existing network sites to apply a bandwidth policy profile by using the <STRONG>Set-CsNetworkSite</STRONG> cmdlet.</span></span> <span data-ttu-id="c3366-105">Пример изменения сайта сети можно найти <A href="lync-server-2013-create-or-modify-a-network-site.md">в разделе Создание или изменение сайта сети в Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="c3366-105">For an example of how to modify a network site, see <A href="lync-server-2013-create-or-modify-a-network-site.md">Create or modify a network site in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="c3366-106">*Сетевые сайты* — это офисы или места в каждом сетевом регионе управления допуском звонков (CAC), E9-1-1, а также с помощью мультимедийных развертываний.</span><span class="sxs-lookup"><span data-stu-id="c3366-106">*Network sites* are the offices or locations within each network region of call admission control (CAC), E9-1-1, and media bypass deployments.</span></span> <span data-ttu-id="c3366-107">Для создания сайтов сети, которые выравниваются по сетевым сайтам в примере топологии сети для CAC, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="c3366-107">Use the following procedures to create network sites that align to network sites in the example network topology for CAC.</span></span> <span data-ttu-id="c3366-108">В этих процедурах показано, как создавать и настраивать сетевые сайты, ограниченные с помощью глобальной сети, и поэтому требуют политики пропускной способности, которые ограничивают поток аудио-или видеоканала в режиме реального времени.</span><span class="sxs-lookup"><span data-stu-id="c3366-108">These procedures show how to create and configure network sites that are constrained by WAN bandwidth and therefore require bandwidth policies that limit real-time audio or video traffic flow.</span></span>

<span data-ttu-id="c3366-109">В примере развертывания CAC для Северной Америки регион "Северная Америка" состоит из шести сайтов.</span><span class="sxs-lookup"><span data-stu-id="c3366-109">In the example CAC deployment, the North America region has six sites.</span></span> <span data-ttu-id="c3366-110">На три из этих сайтов наложено пропускная способность глобальной сети: Рено, Портленде и Альбукерке.</span><span class="sxs-lookup"><span data-stu-id="c3366-110">Three of these sites are constrained by WAN bandwidth: Reno, Portland, and Albuquerque.</span></span> <span data-ttu-id="c3366-111">Другие три сайта, *не* ограниченные пропускной СПОСОБНОСТЬЮ глобальной сети: Нью-Йорк, Чикаго и Детройт.</span><span class="sxs-lookup"><span data-stu-id="c3366-111">The other three sites, which are *not* constrained by WAN bandwidth: New York, Chicago, and Detroit.</span></span> <span data-ttu-id="c3366-112">Пример создания или изменения этих сайтов сети можно найти [в разделе Создание или изменение сетевого сайта в Lync Server 2013](lync-server-2013-create-or-modify-a-network-site.md).</span><span class="sxs-lookup"><span data-stu-id="c3366-112">For an example of how to create or modify those other network sites, see [Create or modify a network site in Lync Server 2013](lync-server-2013-create-or-modify-a-network-site.md).</span></span>

<span data-ttu-id="c3366-113">Пример топологии сети вы можете найти в статье [пример. сбор требований для управления допуском звонков в Lync Server 2013](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md) в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="c3366-113">To view the example network topology, see [Example: Gathering your requirements for call admission control in Lync Server 2013](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md) in the Planning documentation.</span></span>

<div class=" ">


> [!NOTE]  
> <span data-ttu-id="c3366-114">В описанной ниже процедуре для создания сайта сети используется Командная консоль Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="c3366-114">In the following procedure, Lync Server Management Shell is used to create a network site.</span></span> <span data-ttu-id="c3366-115">Дополнительные сведения об использовании панели управления Lync Server для создания сайта можно найти в разделе <A href="lync-server-2013-create-or-modify-a-network-site.md">Создание или изменение сайта сети в Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="c3366-115">For details about using Lync Server Control Panel to create a network site, see <A href="lync-server-2013-create-or-modify-a-network-site.md">Create or modify a network site in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-create-network-sites-for-call-admission-control"></a><span data-ttu-id="c3366-116">Создание сетевых сайтов для управления допуском звонков</span><span class="sxs-lookup"><span data-stu-id="c3366-116">To create network sites for call admission control</span></span>

1.  <span data-ttu-id="c3366-117">Запустите командную консоль Lync Server Management Shell: нажмите кнопку **Пуск**, выберите **все программы**, а затем — **Microsoft Lync Server 2013**, а затем — **Командная консоль Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="c3366-117">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="c3366-118">Запустите командлет **New-кснетворксите** для создания сайтов сети и применения к каждому сайту соответствующего профиля политики пропускной способности.</span><span class="sxs-lookup"><span data-stu-id="c3366-118">Run the **New-CsNetworkSite** cmdlet to create network sites and apply an appropriate bandwidth policy profile to each site.</span></span> <span data-ttu-id="c3366-119">Например, выполните командлет:</span><span class="sxs-lookup"><span data-stu-id="c3366-119">For example, run:</span></span>
    
       ```
        New-CsNetworkSite -NetworkSiteID Reno -Description "NA:Branch office for sales force" -NetworkRegionID NorthAmerica -BWPolicyProfileID 10MB_Link
       ```
    
       ```
        New-CsNetworkSite -NetworkSiteID Portland -Description "NA:Branch office for marketing force" -NetworkRegionID NorthAmerica -BWPolicyProfileID 5MB_Link
       ```
    
       ```
        New-CsNetworkSite -NetworkSiteID Albuquerque -Description "NA:Branch office for SouthWest sales" -NetworkRegionID EMEA -BWPolicyProfileID 10MB_Link
       ```

3.  <span data-ttu-id="c3366-120">Чтобы завершить создание сайтов сети для всей топологии примера, повторите шаг 2 для сайтов сети с ограниченным доступом в регионах EMEA и APAC.</span><span class="sxs-lookup"><span data-stu-id="c3366-120">To finish creating network sites for the entire example topology, repeat step 2 for the bandwidth-constrained network sites in the EMEA and APAC regions.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

