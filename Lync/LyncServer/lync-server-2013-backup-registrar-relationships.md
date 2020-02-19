---
title: Связи с резервным регистратором Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Backup Registrar relationships
ms:assetid: 7e078271-84b9-4666-989c-c4507a0cdf4a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205033(v=OCS.15)
ms:contentKeyID: 48184631
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 07380cbea030f5c9219cef2654b4761f215988e2
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42140652"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="backup-registrar-relationships-in-lync-server-2013"></a><span data-ttu-id="fafdd-102">Связи регистратора резервного копирования в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fafdd-102">Backup Registrar relationships in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fafdd-103">_**Последнее изменение темы:** 2012-06-28_</span><span class="sxs-lookup"><span data-stu-id="fafdd-103">_**Topic Last Modified:** 2012-06-28_</span></span>

<span data-ttu-id="fafdd-104">Помимо обеспечения возможности аварийного восстановления, два сопряженных пула служат как резервные регистраторы друг для друга.</span><span class="sxs-lookup"><span data-stu-id="fafdd-104">In addition to providing disaster recovery ability, two paired pools serve as the backup Registrars for each other.</span></span> <span data-ttu-id="fafdd-105">В Lync Server 2013 отношения регистратора резервного копирования между интерфейсными пулами всегда являются 1:1 и обратными.</span><span class="sxs-lookup"><span data-stu-id="fafdd-105">In Lync Server 2013, backup Registrar relationships between Front End pools are always 1:1 and reciprocal.</span></span> <span data-ttu-id="fafdd-106">Это означает, что если П1 является резервным для П2, то П2 должен быть резервным для П1, и не может быть резервным ни для какого другого интерфейсного пула.</span><span class="sxs-lookup"><span data-stu-id="fafdd-106">This means that if P1 is the backup for P2, then P2 must be the backup for P1, and neither can be the backup for any other Front End pool.</span></span> <span data-ttu-id="fafdd-107">Это изменение из Lync Server 2010, в котором отношения резервного копирования пула переднего плана могут иметь не более одного.</span><span class="sxs-lookup"><span data-stu-id="fafdd-107">This is a change from Lync Server 2010, in which Front End pool backup relationships could be many to one.</span></span>

<span data-ttu-id="fafdd-108">Несмотря на то, что отношения резервного копирования между двумя интерфейсными пулами должны быть 1:1 и симметричными, каждый интерфейсный пул по-прежнему также может быть резервным регистратором для любого количества устройств для обеспечения связи в филиалах, как и в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="fafdd-108">Even though backup relationships between two Front End pools must be 1:1 and symmetrical, each Front End pool can still also be the backup registrar for any number of Survivable Branch Appliances, just as in Lync Server 2010.</span></span>

<span data-ttu-id="fafdd-109">Обратите внимание, что Lync Server 2013 не расширяет поддержку аварийного восстановления для пользователей, размещенных на устройстве для обеспечения связи в филиалах.</span><span class="sxs-lookup"><span data-stu-id="fafdd-109">Note that Lync Server 2013 does not extend disaster recovery support to users homed on a Survivable Branch Appliance.</span></span> <span data-ttu-id="fafdd-110">Если интерфейсный пул, который выступает в качестве резервного устройства для обеспечения связи в филиалах, отключается, пользователи, воходящие в устройство для обеспечения связи в филиалах, переходят в режим устойчивости даже после отказа пользователей, размещенных в пуле переднего плана, на резервный пул.</span><span class="sxs-lookup"><span data-stu-id="fafdd-110">If a Front End pool that serves as the backup for a Survivable Branch Appliance goes down, users signed into the Survivable Branch Appliance fall into resiliency mode even after users homed on the Front End pool are failed over to the backup Front End pool.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

