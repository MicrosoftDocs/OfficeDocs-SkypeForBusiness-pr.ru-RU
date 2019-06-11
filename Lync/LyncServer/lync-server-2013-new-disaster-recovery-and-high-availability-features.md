---
title: 'Lync Server 2013: новые возможности высокой доступности и аварийного восстановления'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: New disaster recovery and high availability features
ms:assetid: 4fa7cd0f-784b-4d3f-b839-432c2ecaf7c1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204892(v=OCS.15)
ms:contentKeyID: 48184130
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e93e2265d401c6dca16f5c00c339fbdc893aba0a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34826341"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="new-disaster-recovery-and-high-availability-features-in-lync-server-2013"></a><span data-ttu-id="05c8b-102">Новые возможности высокой доступности и аварийного восстановления в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="05c8b-102">New disaster recovery and high availability features in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="05c8b-103">_**Тема последнего изменения:** 2012-09-20_</span><span class="sxs-lookup"><span data-stu-id="05c8b-103">_**Topic Last Modified:** 2012-09-20_</span></span>

<span data-ttu-id="05c8b-104">Как и в Lync Server 2010, основная схема высокой доступности для Lync Server 2013 основывается на избыточности сервера посредством группировки.</span><span class="sxs-lookup"><span data-stu-id="05c8b-104">As in Lync Server 2010, the main high availability (HA) scheme for Lync Server 2013 is based on server redundancy via pooling.</span></span> <span data-ttu-id="05c8b-105">Если сервер, на котором работает определенная роль, завершает работу со сбоем, другие серверы в пуле, выполняющие ту же самую роль, берут на себя нагрузку первого сервера.</span><span class="sxs-lookup"><span data-stu-id="05c8b-105">If a server running a certain server role fails, the other servers in the pool running the same role take the load of that server.</span></span> <span data-ttu-id="05c8b-106">Это применимо к интерфейсным серверам, пограничным серверам, серверам-посредникам и директорам.</span><span class="sxs-lookup"><span data-stu-id="05c8b-106">This applies to Front End Servers, Edge Servers, Mediation Servers, and Directors.</span></span>

<span data-ttu-id="05c8b-107">Lync Server 2013 добавляет новые показатели аварийного восстановления, позволяя связывать пулы интерфейсов, расположенные в двух центрах обработки данных.</span><span class="sxs-lookup"><span data-stu-id="05c8b-107">Lync Server 2013 adds new disaster recovery measures by enabling you to pair Front End pools located in two datacenters.</span></span> <span data-ttu-id="05c8b-108">Если один из сопоставленных пулов выходит из строя, администратор может перенести пользователей из этого пула в другой пул в паре для предоставления возможности продолжения обслуживания.</span><span class="sxs-lookup"><span data-stu-id="05c8b-108">If one of the paired pools goes down, an administrator can fail over the users from that pool to the other pool in the pair, to provide continuation of service.</span></span> <span data-ttu-id="05c8b-109">Эта функция не требует дорогостоящих сетевых и аппаратных решений, таких как сети хранения данных или общие диски.</span><span class="sxs-lookup"><span data-stu-id="05c8b-109">This functionality does not require expensive network or hardware solutions such as storage networks or shared disks.</span></span>

<span data-ttu-id="05c8b-110">Lync Server 2013 также добавляет полную доступность сервера для серверной части.</span><span class="sxs-lookup"><span data-stu-id="05c8b-110">Lync Server 2013 also adds Back End Server high availability.</span></span> <span data-ttu-id="05c8b-111">Это необязательная топология, в которой развертывается два серверных сервера для пула переднего плана, а также синхронное зеркальное отображение SQL для всех баз данных Lync, запущенных на серверном сервере.</span><span class="sxs-lookup"><span data-stu-id="05c8b-111">This is an optional topology in which you deploy two Back End Servers for a Front End pool, and set up synchronous SQL mirroring for all the Lync databases running on the Back End Servers.</span></span> <span data-ttu-id="05c8b-112">Вы можете выбрать, нужно ли развертывать следящий сервер для зеркала.</span><span class="sxs-lookup"><span data-stu-id="05c8b-112">You may choose whether to deploy a witness for the mirror.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="05c8b-113">См. также</span><span class="sxs-lookup"><span data-stu-id="05c8b-113">See Also</span></span>


[<span data-ttu-id="05c8b-114">Планирование высокой доступности и аварийного восстановления в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="05c8b-114">Planning for high availability and disaster recovery in Lync Server 2013</span></span>](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

