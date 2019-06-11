---
title: Подключение Survivable Branch Appliance к пулу переднего плана Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Connecting Survivable Branch Appliance to Lync Server 2013 Front End pool
ms:assetid: 3c7ca33f-5295-4d82-9152-41d8bc6f35cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688026(v=OCS.15)
ms:contentKeyID: 49733616
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 77d22a71272ae7dd3c426b0439f7a3765ca6848c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34841145"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="connecting-survivable-branch-appliance-to-lync-server-2013-front-end-pool"></a><span data-ttu-id="4f3cc-102">Подключение Survivable Branch Appliance к пулу переднего плана Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4f3cc-102">Connecting Survivable Branch Appliance to Lync Server 2013 Front End pool</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4f3cc-103">_**Тема последнего изменения:** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="4f3cc-103">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="4f3cc-104">Каждое работающее устройство филиала (СБА) связано с пулом переднего плана, который выступает в качестве регистратора резервных копий для СБА.</span><span class="sxs-lookup"><span data-stu-id="4f3cc-104">Every Survivable Branch Appliance (SBA) is associated with a Front End pool, which serves as a backup Registrar for the SBA.</span></span> <span data-ttu-id="4f3cc-105">Когда пул переднего плана обновляется до Lync Server 2013, СБА должен быть связан с пулом переднего плана, пока пул переднего плана будет обновлен.</span><span class="sxs-lookup"><span data-stu-id="4f3cc-105">When the Front End pool is upgraded to Lync Server 2013, the SBA must be disassociated from the Front End pool while the Front End pool is upgraded.</span></span> <span data-ttu-id="4f3cc-106">После обновления пула переднего плана СБА можно связать с пулом переднего плана.</span><span class="sxs-lookup"><span data-stu-id="4f3cc-106">After the Front End pool is upgraded, the SBA can be reassociated with the Front End pool.</span></span> <span data-ttu-id="4f3cc-107">Это связано с тем, что удаление СБА из топологии в построителе топологии и повторное добавление СБА для Topology Builder.</span><span class="sxs-lookup"><span data-stu-id="4f3cc-107">This involves deleting the SBA from the topology in Topology Builder and then adding the SBA, again, to Topology Builder.</span></span> <span data-ttu-id="4f3cc-108">Пользователи, размещенные на СБА, должны быть перемещены в другой пул переднего плана, прежде чем удалять СБА из топологии.</span><span class="sxs-lookup"><span data-stu-id="4f3cc-108">Users homed on the SBA must be moved to another Front End pool before removing the SBA from the topology.</span></span> <span data-ttu-id="4f3cc-109">После того как СБА снова добавится в топологию, эти пользователи могут быть возвращены в СБА.</span><span class="sxs-lookup"><span data-stu-id="4f3cc-109">After the SBA is added back to the topology, those users can be moved back to the SBA.</span></span>

<span data-ttu-id="4f3cc-110">Эти действия описаны ниже.</span><span class="sxs-lookup"><span data-stu-id="4f3cc-110">These steps are summarized below:</span></span>

1.  <span data-ttu-id="4f3cc-111">Перемещение пользователей филиалов, размещенных на СБА, в другой пул переднего плана.</span><span class="sxs-lookup"><span data-stu-id="4f3cc-111">Move branch users homed on SBA to another Front End pool.</span></span>

2.  <span data-ttu-id="4f3cc-112">Удалите СБА из топологии, чтобы разорвать существующий пул переднего плана в качестве регистратора резервных копий.</span><span class="sxs-lookup"><span data-stu-id="4f3cc-112">Remove SBA from your topology to disassociate the existing Front End pool as the backup Registrar.</span></span>

3.  <span data-ttu-id="4f3cc-113">Обновите пул переднего плана до Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4f3cc-113">Upgrade Front End pool to Microsoft Lync Server 2013.</span></span>

4.  <span data-ttu-id="4f3cc-114">Добавьте СБА обратно в топологию.</span><span class="sxs-lookup"><span data-stu-id="4f3cc-114">Add SBA back into your topology.</span></span>

5.  <span data-ttu-id="4f3cc-115">Свяжите новый пул переднего плана с СБА в качестве регистратора резервных копий.</span><span class="sxs-lookup"><span data-stu-id="4f3cc-115">Associate the new Front End pool to the SBA as a backup Registrar.</span></span>

6.  <span data-ttu-id="4f3cc-116">Переместить пользователей филиалов обратно в СБА.</span><span class="sxs-lookup"><span data-stu-id="4f3cc-116">Move branch users back to the SBA.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="4f3cc-117">Содержание</span><span class="sxs-lookup"><span data-stu-id="4f3cc-117">In This Section</span></span>

  - [<span data-ttu-id="4f3cc-118">Добавление в топологию сайта филиала устройства для обеспечения связи в филиалах Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4f3cc-118">Add Lync Server 2013 Survivable Branch Appliance branch site to your topology</span></span>](lync-server-2013-add-lync-server-2013-survivable-branch-appliance-branch-site-to-your-topology.md)

  - [<span data-ttu-id="4f3cc-119">Добавление сайта филиала Lync Server 2010 Survivable Branch Appliance в топологию</span><span class="sxs-lookup"><span data-stu-id="4f3cc-119">Add Lync Server 2010 Survivable Branch Appliance branch site to your topology</span></span>](lync-server-2013-add-lync-server-2010-survivable-branch-appliance-branch-site-to-your-topology.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

