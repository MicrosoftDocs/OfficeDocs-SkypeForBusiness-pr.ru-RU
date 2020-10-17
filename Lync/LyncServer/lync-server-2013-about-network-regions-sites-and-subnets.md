---
title: 'Lync Server 2013: сведения об областях сети, сайтах и подсетях'
description: 'Lync Server 2013: сведения об областях сети, сайтах и подсетях.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: About network regions, sites, and subnets
ms:assetid: 6662123a-d011-408c-a290-92b2a8589943
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398467(v=OCS.15)
ms:contentKeyID: 48184335
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a3c7f660f3c72003527e0721c3f9702865e9b9b4
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48568935"
---
# <a name="about-network-regions-sites-and-subnets-in-lync-server-2013"></a><span data-ttu-id="68a6a-103">Сведения о регионах сети, сайтах и подсетях в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="68a6a-103">About network regions, sites, and subnets in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="68a6a-104">_**Последнее изменение темы:** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="68a6a-104">_**Topic Last Modified:** 2013-02-24_</span></span>

<span data-ttu-id="68a6a-p101">На расширенные функции корпоративной голосовой связи, описанные в этом разделе, распространяются общие определенные требования относительно конфигурации для регионов сети, сетевых сайтов и подсетей. Например, для всех трех расширенных функций необходимо, чтобы каждая подсеть в топологии была связана с определенным *сетевым сайтом*, а каждый сетевой сайт был связан с *регионом сети*.</span><span class="sxs-lookup"><span data-stu-id="68a6a-p101">The advanced Enterprise Voice features described in this section share certain configuration requirements for network regions, network sites, and subnets. For example, all three advanced features require that each subnet in your topology be associated with a specific *network site*, and each network site must be associated with a *network region*.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="68a6a-107">Прежде чем приступить к настройке сети для контроля допуска звонков, E9 – 1 – 1 или обхода сервера мультимедиа, убедитесь в том, что вы проверили дополнительные сведения о параметрах сети в <A href="lync-server-2013-network-settings-for-the-advanced-enterprise-voice-features.md">параметрах сети для функций расширенной корпоративной голосовой связи в статье Lync Server 2013</A> в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="68a6a-107">Before you begin network configuration for call admission control, E9-1-1, or media bypass, make sure that you reviewed additional information about network settings in the <A href="lync-server-2013-network-settings-for-the-advanced-enterprise-voice-features.md">Network settings for the advanced Enterprise Voice features in Lync Server 2013</A> topic in the Planning documentation.</span></span> <span data-ttu-id="68a6a-108">Сведения о конфигурации сети в основном об управлении допуском звонков также приведены в статье <A href="lync-server-2013-defining-your-requirements-for-call-admission-control.md">Определение требований для контроля допуска звонков в Lync Server 2013</A> в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="68a6a-108">For details about network configuration primarily about call admission control, also see <A href="lync-server-2013-defining-your-requirements-for-call-admission-control.md">Defining your requirements for call admission control in Lync Server 2013</A> in the Planning documentation.</span></span>



</div>

<span data-ttu-id="68a6a-109">На контроль допуска звонков и E9-1-1 распространяются дополнительные требования относительно конфигурации для сетевых сайтов:</span><span class="sxs-lookup"><span data-stu-id="68a6a-109">Call admission control and E9-1-1 have additional configuration requirements for network sites:</span></span>

  - <span data-ttu-id="68a6a-110">Для использования функции контроля допуска звонков необходимо указать *профиль политики пропускной способности* для каждого сайта, на который распространяются ограничения полосы пропускания WAN.</span><span class="sxs-lookup"><span data-stu-id="68a6a-110">Call admission control requires that a *bandwidth policy profile* be specified for each site that is constrained by WAN bandwidth limitations.</span></span> <span data-ttu-id="68a6a-111">Если вы планируете развернуть контроль допуска звонков, необходимо [создать профили политики пропускной способности в Lync Server 2013](lync-server-2013-create-bandwidth-policy-profiles.md) перед настройкой сетевых сайтов.</span><span class="sxs-lookup"><span data-stu-id="68a6a-111">If you plan to deploy call admission control, you must [Create bandwidth policy profiles in Lync Server 2013](lync-server-2013-create-bandwidth-policy-profiles.md) before you configure your network sites.</span></span>

  - <span data-ttu-id="68a6a-112">Для использования E9-1-1 необходимо указать *политику расположения* для каждого сайта.</span><span class="sxs-lookup"><span data-stu-id="68a6a-112">E9-1-1 requires that a *location policy* be specified for each site.</span></span> <span data-ttu-id="68a6a-113">Если вы планируете развернуть E9-1-1, необходимо [создать политики расположения в Lync Server 2013](lync-server-2013-create-location-policies.md) перед настройкой сетевых сайтов.</span><span class="sxs-lookup"><span data-stu-id="68a6a-113">If you plan to deploy E9-1-1, you must [Create location policies in Lync Server 2013](lync-server-2013-create-location-policies.md) before you configure your network sites.</span></span>

<div>

## <a name="create-or-modify-network-regions-network-sites-and-subnets"></a><span data-ttu-id="68a6a-114">Создание или изменение регионов сети, сетевых сайтов и подсетей</span><span class="sxs-lookup"><span data-stu-id="68a6a-114">Create or Modify Network Regions, Network Sites, and Subnets</span></span>

<span data-ttu-id="68a6a-p105">В следующих разделах приведены процедуры создания или изменения регионов сети и сетевых сайтов, а также сопоставления подсетей с сетевыми сайтами. В этих разделах не рассматриваются какие-либо определенные расширенные функции корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="68a6a-p105">The following topics provide steps to create or modify network regions and network sites, and to associate subnets with network sites. These topics are not specific to any particular advanced Enterprise Voice feature.</span></span>

  - [<span data-ttu-id="68a6a-117">Создание или изменение области сети в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="68a6a-117">Create or modify a network region in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-network-region.md)

  - [<span data-ttu-id="68a6a-118">Создание или изменение сетевого сайта в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="68a6a-118">Create or modify a network site in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-network-site.md)

  - [<span data-ttu-id="68a6a-119">Связывание подсети с сетевым сайтом в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="68a6a-119">Associate a subnet with a network site in Lync Server 2013</span></span>](lync-server-2013-associate-a-subnet-with-a-network-site.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

