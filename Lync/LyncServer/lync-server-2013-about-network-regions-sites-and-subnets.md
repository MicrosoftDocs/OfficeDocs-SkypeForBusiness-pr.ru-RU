---
title: 'Lync Server 2013: о сетевых областях, сайтах и подсетях'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: About network regions, sites, and subnets
ms:assetid: 6662123a-d011-408c-a290-92b2a8589943
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398467(v=OCS.15)
ms:contentKeyID: 48184335
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ef6601a0baafd1226f4e283d62a8cbdb410064ff
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34841979"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="about-network-regions-sites-and-subnets-in-lync-server-2013"></a><span data-ttu-id="35170-102">О сетевых областях, сайтах и подсетях в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="35170-102">About network regions, sites, and subnets in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="35170-103">_**Тема последнего изменения:** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="35170-103">_**Topic Last Modified:** 2013-02-24_</span></span>

<span data-ttu-id="35170-104">В этой статье описаны дополнительные требования к конфигурации для регионов сети, сайтов сети и подсетей.</span><span class="sxs-lookup"><span data-stu-id="35170-104">The advanced Enterprise Voice features described in this section share certain configuration requirements for network regions, network sites, and subnets.</span></span> <span data-ttu-id="35170-105">Например, для всех трех дополнительных функций требуется, чтобы каждая подсеть в топологии была связана с конкретным *сетевым сайтом*, а каждый сетевой сайт должен быть связан с *сетевым регионом*.</span><span class="sxs-lookup"><span data-stu-id="35170-105">For example, all three advanced features require that each subnet in your topology be associated with a specific *network site*, and each network site must be associated with a *network region*.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="35170-106">Прежде чем приступить к настройке сети для управления допуском звонков, E9-1-1 или мультимедиа, убедитесь, что вы просматриваете дополнительные сведения о параметрах сети в <A href="lync-server-2013-network-settings-for-the-advanced-enterprise-voice-features.md">параметрах сети для расширенных функций голосовой связи в Lync Server 2013</A> . раздел в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="35170-106">Before you begin network configuration for call admission control, E9-1-1, or media bypass, make sure that you reviewed additional information about network settings in the <A href="lync-server-2013-network-settings-for-the-advanced-enterprise-voice-features.md">Network settings for the advanced Enterprise Voice features in Lync Server 2013</A> topic in the Planning documentation.</span></span> <span data-ttu-id="35170-107">Сведения о конфигурации сети в основном для управления допуском звонков также можно найти <A href="lync-server-2013-defining-your-requirements-for-call-admission-control.md">в разделе Определение требований к управлению допуском звонков в Lync Server 2013</A> в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="35170-107">For details about network configuration primarily about call admission control, also see <A href="lync-server-2013-defining-your-requirements-for-call-admission-control.md">Defining your requirements for call admission control in Lync Server 2013</A> in the Planning documentation.</span></span>



</div>

<span data-ttu-id="35170-108">На контроль допуска звонков и E9-1-1 распространяются дополнительные требования относительно конфигурации для сетевых сайтов:</span><span class="sxs-lookup"><span data-stu-id="35170-108">Call admission control and E9-1-1 have additional configuration requirements for network sites:</span></span>

  - <span data-ttu-id="35170-109">Для использования функции контроля допуска звонков необходимо указать *профиль политики пропускной способности* для каждого сайта, на который распространяются ограничения полосы пропускания WAN.</span><span class="sxs-lookup"><span data-stu-id="35170-109">Call admission control requires that a *bandwidth policy profile* be specified for each site that is constrained by WAN bandwidth limitations.</span></span> <span data-ttu-id="35170-110">Если вы планируете развернуть управление допуском звонков, необходимо [создать профили политики пропускной способности в Lync Server 2013](lync-server-2013-create-bandwidth-policy-profiles.md) перед настройкой сайтов сети.</span><span class="sxs-lookup"><span data-stu-id="35170-110">If you plan to deploy call admission control, you must [Create bandwidth policy profiles in Lync Server 2013](lync-server-2013-create-bandwidth-policy-profiles.md) before you configure your network sites.</span></span>

  - <span data-ttu-id="35170-111">Для использования E9-1-1 необходимо указать *политику расположения* для каждого сайта.</span><span class="sxs-lookup"><span data-stu-id="35170-111">E9-1-1 requires that a *location policy* be specified for each site.</span></span> <span data-ttu-id="35170-112">Если вы планируете развернуть E9-1-1, необходимо [создать политики местоположений в Lync Server 2013](lync-server-2013-create-location-policies.md) перед настройкой сетевых сайтов.</span><span class="sxs-lookup"><span data-stu-id="35170-112">If you plan to deploy E9-1-1, you must [Create location policies in Lync Server 2013](lync-server-2013-create-location-policies.md) before you configure your network sites.</span></span>

<div>

## <a name="create-or-modify-network-regions-network-sites-and-subnets"></a><span data-ttu-id="35170-113">Создание и изменение регионов сети, сайтов сети и подсетей</span><span class="sxs-lookup"><span data-stu-id="35170-113">Create or Modify Network Regions, Network Sites, and Subnets</span></span>

<span data-ttu-id="35170-114">Ниже описаны действия, которые можно использовать для создания и изменения областей сети и сетевых сайтов, а также для сопоставления подсетей с сетевыми сайтами.</span><span class="sxs-lookup"><span data-stu-id="35170-114">The following topics provide steps to create or modify network regions and network sites, and to associate subnets with network sites.</span></span> <span data-ttu-id="35170-115">Эти темы не относятся к конкретным дополнительным функциям расширенной корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="35170-115">These topics are not specific to any particular advanced Enterprise Voice feature.</span></span>

  - [<span data-ttu-id="35170-116">Создание или изменение сетевого региона в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="35170-116">Create or modify a network region in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-network-region.md)

  - [<span data-ttu-id="35170-117">Создание или изменение сетевого сайта в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="35170-117">Create or modify a network site in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-network-site.md)

  - [<span data-ttu-id="35170-118">Связь подсети с сетевым сайтом в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="35170-118">Associate a subnet with a network site in Lync Server 2013</span></span>](lync-server-2013-associate-a-subnet-with-a-network-site.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

