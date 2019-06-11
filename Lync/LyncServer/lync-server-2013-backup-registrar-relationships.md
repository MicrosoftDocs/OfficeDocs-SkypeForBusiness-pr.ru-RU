---
title: 'Lync Server 2013: связи с регистраторами резервного копирования'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Backup Registrar relationships
ms:assetid: 7e078271-84b9-4666-989c-c4507a0cdf4a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205033(v=OCS.15)
ms:contentKeyID: 48184631
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3a642c8d8872b2c0d1372a209c9c05dac704ee20
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34841741"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="backup-registrar-relationships-in-lync-server-2013"></a><span data-ttu-id="79aeb-102">Связи с регистраторами резервного копирования в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="79aeb-102">Backup Registrar relationships in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="79aeb-103">_**Тема последнего изменения:** 2012-06-28_</span><span class="sxs-lookup"><span data-stu-id="79aeb-103">_**Topic Last Modified:** 2012-06-28_</span></span>

<span data-ttu-id="79aeb-104">Помимо обеспечения возможности аварийного восстановления два парных пула служат как резервные регистраторы друг для друга.</span><span class="sxs-lookup"><span data-stu-id="79aeb-104">In addition to providing disaster recovery ability, two paired pools serve as the backup Registrars for each other.</span></span> <span data-ttu-id="79aeb-105">В Lync Server 2013 связи регистратора резервного копирования между интерфейсными пулами будут всегда 1:1 и обратно.</span><span class="sxs-lookup"><span data-stu-id="79aeb-105">In Lync Server 2013, backup Registrar relationships between Front End pools are always 1:1 and reciprocal.</span></span> <span data-ttu-id="79aeb-106">Это означает, что если P1 — резервная копия для P2, то P2 должен быть резервной копией для P1, и ни один из них не может быть резервной копией для другого пула переднего плана.</span><span class="sxs-lookup"><span data-stu-id="79aeb-106">This means that if P1 is the backup for P2, then P2 must be the backup for P1, and neither can be the backup for any other Front End pool.</span></span> <span data-ttu-id="79aeb-107">Это изменение из Lync Server 2010, в котором интерфейс резервного копирования пула переднего плана может находиться в нескольких отношениях.</span><span class="sxs-lookup"><span data-stu-id="79aeb-107">This is a change from Lync Server 2010, in which Front End pool backup relationships could be many to one.</span></span>

<span data-ttu-id="79aeb-108">Несмотря на то, что резервные копии двух пулов переднего плана должны быть 1:1 и симметрично, каждый пул переднего плана может также быть регистратором резервных копий для любого количества бесперебойных филиалов, как в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="79aeb-108">Even though backup relationships between two Front End pools must be 1:1 and symmetrical, each Front End pool can still also be the backup registrar for any number of Survivable Branch Appliances, just as in Lync Server 2010.</span></span>

<span data-ttu-id="79aeb-109">Обратите внимание, что в Lync Server 2013 не поддерживается поддержка аварийного восстановления для пользователей, размещенных на устройстве с бесперебойной подразделением.</span><span class="sxs-lookup"><span data-stu-id="79aeb-109">Note that Lync Server 2013 does not extend disaster recovery support to users homed on a Survivable Branch Appliance.</span></span> <span data-ttu-id="79aeb-110">Если пул переднего плана, который используется как резервная копия для бесперебойно работающего устройства филиала, отключается, пользователи, выполнившие вход в работающее устройство филиала, попадают в режим устойчивости даже после отказа пользователей, подключенных к пулу переднего плана, в пул резервной копии.</span><span class="sxs-lookup"><span data-stu-id="79aeb-110">If a Front End pool that serves as the backup for a Survivable Branch Appliance goes down, users signed into the Survivable Branch Appliance fall into resiliency mode even after users homed on the Front End pool are failed over to the backup Front End pool.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

