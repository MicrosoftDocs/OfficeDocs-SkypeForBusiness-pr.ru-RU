---
title: Подключение Survivable Branch Appliance к пулу переднего плана Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Connecting Survivable Branch Appliance to Lync Server 2013 Front End pool
ms:assetid: 3c7ca33f-5295-4d82-9152-41d8bc6f35cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688026(v=OCS.15)
ms:contentKeyID: 49733616
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b7a637716f1e5b1a2082f694554951d42f36978f
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48502026"
---
# <a name="connecting-survivable-branch-appliance-to-lync-server-2013-front-end-pool"></a><span data-ttu-id="c29b7-102">Подключение Survivable Branch Appliance к пулу переднего плана Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c29b7-102">Connecting Survivable Branch Appliance to Lync Server 2013 Front End pool</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c29b7-103">_**Последнее изменение темы:** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="c29b7-103">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="c29b7-104">Каждое устройство для обеспечения связи в филиалах (SBA) связано с пулом переднего плана, который выступает в качестве регистратора резервных копий для SBA.</span><span class="sxs-lookup"><span data-stu-id="c29b7-104">Every Survivable Branch Appliance (SBA) is associated with a Front End pool, which serves as a backup Registrar for the SBA.</span></span> <span data-ttu-id="c29b7-105">После обновления пула переднего плана до Lync Server 2013 SBA должен быть связан с интерфейсным пулом во время обновления пула переднего плана.</span><span class="sxs-lookup"><span data-stu-id="c29b7-105">When the Front End pool is upgraded to Lync Server 2013, the SBA must be disassociated from the Front End pool while the Front End pool is upgraded.</span></span> <span data-ttu-id="c29b7-106">После обновления пула переднего плана SBA может быть связан с пулом переднего плана.</span><span class="sxs-lookup"><span data-stu-id="c29b7-106">After the Front End pool is upgraded, the SBA can be reassociated with the Front End pool.</span></span> <span data-ttu-id="c29b7-107">Сюда входит удаление устройства обеспечения связи в филиалах из топологии в построителе топологий и повторное добавление этого устройства в построителе.</span><span class="sxs-lookup"><span data-stu-id="c29b7-107">This involves deleting the SBA from the topology in Topology Builder and then adding the SBA, again, to Topology Builder.</span></span> <span data-ttu-id="c29b7-108">Пользователи, размещенные в SBA, должны быть перемещены в другой интерфейсный пул перед удалением SBA из топологии.</span><span class="sxs-lookup"><span data-stu-id="c29b7-108">Users homed on the SBA must be moved to another Front End pool before removing the SBA from the topology.</span></span> <span data-ttu-id="c29b7-109">После повторного добавления устройства в топологию можно переместить этих пользователей обратно на данное устройство обеспечения связи в филиалах.</span><span class="sxs-lookup"><span data-stu-id="c29b7-109">After the SBA is added back to the topology, those users can be moved back to the SBA.</span></span>

<span data-ttu-id="c29b7-110">Эти действия приведены ниже.</span><span class="sxs-lookup"><span data-stu-id="c29b7-110">These steps are summarized below:</span></span>

1.  <span data-ttu-id="c29b7-111">Перемещение пользователей филиалов, размещенных в SBA, в другой интерфейсный пул.</span><span class="sxs-lookup"><span data-stu-id="c29b7-111">Move branch users homed on SBA to another Front End pool.</span></span>

2.  <span data-ttu-id="c29b7-112">Удалите SBA из топологии, чтобы разорвать существующий интерфейсный пул в качестве регистратора резервных копий.</span><span class="sxs-lookup"><span data-stu-id="c29b7-112">Remove SBA from your topology to disassociate the existing Front End pool as the backup Registrar.</span></span>

3.  <span data-ttu-id="c29b7-113">Обновите интерфейсный пул до Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c29b7-113">Upgrade Front End pool to Microsoft Lync Server 2013.</span></span>

4.  <span data-ttu-id="c29b7-114">Добавьте устройство обеспечения связи в филиалах обратно в топологию.</span><span class="sxs-lookup"><span data-stu-id="c29b7-114">Add SBA back into your topology.</span></span>

5.  <span data-ttu-id="c29b7-115">Свяжите новый интерфейсный пул с SBA в качестве регистратора резервных копий.</span><span class="sxs-lookup"><span data-stu-id="c29b7-115">Associate the new Front End pool to the SBA as a backup Registrar.</span></span>

6.  <span data-ttu-id="c29b7-116">Переместите пользователей филиала обратно на устройство.</span><span class="sxs-lookup"><span data-stu-id="c29b7-116">Move branch users back to the SBA.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="c29b7-117">Содержание</span><span class="sxs-lookup"><span data-stu-id="c29b7-117">In This Section</span></span>

  - [<span data-ttu-id="c29b7-118">Добавление сайта филиала Lync Server 2013 для обеспечения связи в филиалах к топологии</span><span class="sxs-lookup"><span data-stu-id="c29b7-118">Add Lync Server 2013 Survivable Branch Appliance branch site to your topology</span></span>](lync-server-2013-add-lync-server-2013-survivable-branch-appliance-branch-site-to-your-topology.md)

  - [<span data-ttu-id="c29b7-119">Добавление сайта филиала Lync Server 2010 для обеспечения связи в филиалах к топологии</span><span class="sxs-lookup"><span data-stu-id="c29b7-119">Add Lync Server 2010 Survivable Branch Appliance branch site to your topology</span></span>](lync-server-2013-add-lync-server-2010-survivable-branch-appliance-branch-site-to-your-topology.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

