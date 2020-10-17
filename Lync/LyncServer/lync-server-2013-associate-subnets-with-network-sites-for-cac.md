---
title: 'Lync Server 2013: связывание подсетей с сетевыми сайтами для контроля допуска звонков'
description: 'Lync Server 2013: связывание подсетей с сетевыми сайтами для CAC.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Associate subnets with network sites for CAC
ms:assetid: a749c9b3-15f3-4e74-9f43-1507d3c2c940
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412786(v=OCS.15)
ms:contentKeyID: 48185017
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8d68607c1674bb964c27c8408583be7f5e092f4c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48560505"
---
# <a name="associate-subnets-with-network-sites-for-cac-in-lync-server-2013"></a><span data-ttu-id="52275-103">Связывание подсетей с сетевыми сайтами для контроля допуска звонков в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="52275-103">Associate subnets with network sites for CAC in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="52275-104">_**Последнее изменение темы:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="52275-104">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="52275-p101">Каждая подсеть должна быть связана с определенным сетевым узлом. Это требование связано с тем, что данные подсети используются для определения сетевого узла, в котором расположена конечная точка. Имея сведения о расположении обоих участников сеанса, служба контроля допуска звонков может определить, достаточно ли пропускной способности сети для выполнения вызова.</span><span class="sxs-lookup"><span data-stu-id="52275-p101">Every subnet in your network must be associated with a specific network site. This is because subnet information is used to determine the network site on which an endpoint is located. When the locations of both parties in a session are known, call admission control (CAC) can determine if there is sufficient bandwidth to establish a call.</span></span>

<span data-ttu-id="52275-108">Служба контроля допуска звонков не предъявляет никаких требований к связи подсетей с сетевыми узлами.</span><span class="sxs-lookup"><span data-stu-id="52275-108">Call admission control does not have any special requirements for associating subnets with network sites.</span></span> <span data-ttu-id="52275-109">Чтобы создать связь между подсетями и сетевыми сайтами в топологии, выполните процедуры, описанные в разделе [связывание подсети с сетевым сайтом в Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md).</span><span class="sxs-lookup"><span data-stu-id="52275-109">To create an association between the subnets and network sites in your topology, follow the procedures in [Associate a subnet with a network site in Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md).</span></span> <span data-ttu-id="52275-110">Чтобы просмотреть сетевые сайты (и соответствующие подсети) в примере сетевой топологии для контроля допуска звонков, обратитесь к разделу [Пример: сбор требований для контроля допуска звонков в Lync Server 2013](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md) в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="52275-110">To view the network sites (and their respective subnets) in the example network topology for call admission control, see [Example: Gathering your requirements for call admission control in Lync Server 2013](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md) in the Planning documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

