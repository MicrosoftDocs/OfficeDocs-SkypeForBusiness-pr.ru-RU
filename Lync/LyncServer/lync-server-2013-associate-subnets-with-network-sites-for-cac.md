---
title: 'Lync Server 2013: связывание подсетей с сетевыми сайтами для CAC'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Associate subnets with network sites for CAC
ms:assetid: a749c9b3-15f3-4e74-9f43-1507d3c2c940
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412786(v=OCS.15)
ms:contentKeyID: 48185017
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9c00205e8aa070eacb7b5d99ec724ad8b67fa2ae
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34841913"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="associate-subnets-with-network-sites-for-cac-in-lync-server-2013"></a><span data-ttu-id="cc271-102">Связывание подсетей с сетевыми сайтами для CAC в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cc271-102">Associate subnets with network sites for CAC in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cc271-103">_**Тема последнего изменения:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="cc271-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="cc271-104">Каждая подсеть в сети должна быть связана с определенным сетевым сайтом.</span><span class="sxs-lookup"><span data-stu-id="cc271-104">Every subnet in your network must be associated with a specific network site.</span></span> <span data-ttu-id="cc271-105">Это связано с тем, что сведения о подсети используются для определения сетевого сайта, на котором находится конечная точка.</span><span class="sxs-lookup"><span data-stu-id="cc271-105">This is because subnet information is used to determine the network site on which an endpoint is located.</span></span> <span data-ttu-id="cc271-106">Если известно расположение обеих сторон сеанса, управление допуском звонков (CAC) может определить, достаточно ли пропускной способности для установления звонка.</span><span class="sxs-lookup"><span data-stu-id="cc271-106">When the locations of both parties in a session are known, call admission control (CAC) can determine if there is sufficient bandwidth to establish a call.</span></span>

<span data-ttu-id="cc271-107">Для управления допуском звонков не требуются особые требования для сопоставления подсетей с сетевыми сайтами.</span><span class="sxs-lookup"><span data-stu-id="cc271-107">Call admission control does not have any special requirements for associating subnets with network sites.</span></span> <span data-ttu-id="cc271-108">Чтобы создать связь между подсетями и сетевыми сайтами в вашей топологии, выполните действия, описанные в разделе [связывание подсети с сетевым сайтом в Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md).</span><span class="sxs-lookup"><span data-stu-id="cc271-108">To create an association between the subnets and network sites in your topology, follow the procedures in [Associate a subnet with a network site in Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md).</span></span> <span data-ttu-id="cc271-109">Чтобы просмотреть сетевые сайты (и соответствующие им подсети) в примере топологии сети для управления допуском звонков, ознакомьтесь с [примером: сбор требований для управления допуском звонков в Lync Server 2013](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md) в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="cc271-109">To view the network sites (and their respective subnets) in the example network topology for call admission control, see [Example: Gathering your requirements for call admission control in Lync Server 2013](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md) in the Planning documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

