---
title: 'Lync Server 2013: планирование высокой доступности и аварийного восстановления'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Planning for high availability and disaster recovery
ms:assetid: 15a72073-0336-45dd-b2a0-35e7522c6000
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204703(v=OCS.15)
ms:contentKeyID: 48183497
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 092e59813f76690233a950cd8ce914df47146d37
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34824955"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-high-availability-and-disaster-recovery-in-lync-server-2013"></a><span data-ttu-id="6fde3-102">Планирование высокой доступности и аварийного восстановления в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6fde3-102">Planning for high availability and disaster recovery in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6fde3-103">_**Тема последнего изменения:** 2013-10-31_</span><span class="sxs-lookup"><span data-stu-id="6fde3-103">_**Topic Last Modified:** 2013-10-31_</span></span>

<span data-ttu-id="6fde3-104">Как и в Lync Server 2010, основная схема высокой доступности для большинства ролей сервера в Lync Server 2013 базируется на избыточности сервера посредством группировки.</span><span class="sxs-lookup"><span data-stu-id="6fde3-104">As in Lync Server 2010, the main high availability scheme for most server roles in Lync Server 2013 is based on server redundancy via pooling.</span></span> <span data-ttu-id="6fde3-105">Если сервер, на котором работает определенная роль, завершает работу со сбоем, другие серверы в пуле, выполняющие ту же самую роль, берут на себя нагрузку первого сервера.</span><span class="sxs-lookup"><span data-stu-id="6fde3-105">If a server running a certain server role fails, the other servers in the pool running the same role take the load of that server.</span></span> <span data-ttu-id="6fde3-106">Это применимо к интерфейсным серверам, пограничным серверам, серверам-посредникам и директорам.</span><span class="sxs-lookup"><span data-stu-id="6fde3-106">This applies to Front End Servers, Edge Servers, Mediation Servers, and Directors.</span></span>

<span data-ttu-id="6fde3-107">Lync Server 2013 добавляет новые показатели аварийного восстановления для пулов переднего плана с помощью географических дисперсемент серверов в двух центрах обработки данных для предоставления услуг по продолжению всего пула или сайта.</span><span class="sxs-lookup"><span data-stu-id="6fde3-107">Lync Server 2013 adds new disaster recovery measures for Front End pools by introducing geographical dispersement of your servers into two data centers to provide continuation of service should one entire pool or site go down.</span></span>

<span data-ttu-id="6fde3-108">Lync Server 2013 также повышает уровень высокой доступности сервера благодаря поддержке синхронного зеркального отображения SQL для серверных баз данных.</span><span class="sxs-lookup"><span data-stu-id="6fde3-108">Lync Server 2013 also enhances Back End Server high availability, by supporting synchronous SQL mirroring for your Back End databases.</span></span>

<span data-ttu-id="6fde3-109">В этом разделе объясняются основные возможности высокой доступности и аварийного восстановления, а также описаны действия, которые можно выполнить для обеспечения высокой доступности и аварийного восстановления для других ролей сервера.</span><span class="sxs-lookup"><span data-stu-id="6fde3-109">This section explains these major high availability and disaster recovery features, and also covers what steps you can take for high availability and disaster recovery for your other server roles as well.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="6fde3-110">Содержание</span><span class="sxs-lookup"><span data-stu-id="6fde3-110">In This Section</span></span>

  - [<span data-ttu-id="6fde3-111">Аварийное восстановление пула переднего плана в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6fde3-111">Front End pool disaster recovery in Lync Server 2013</span></span>](lync-server-2013-front-end-pool-disaster-recovery.md)

  - [<span data-ttu-id="6fde3-112">Аварийное восстановление пограничного сервера в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6fde3-112">Edge Server disaster recovery in Lync Server 2013</span></span>](lync-server-2013-edge-server-disaster-recovery.md)

  - [<span data-ttu-id="6fde3-113">Планирование устойчивости корпоративной голосовой связи в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6fde3-113">Planning for Enterprise Voice resiliency in Lync Server 2013</span></span>](lync-server-2013-planning-for-enterprise-voice-resiliency.md)

  - [<span data-ttu-id="6fde3-114">Функции управления вызовами для аварийного восстановления в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6fde3-114">Call management features for disaster recovery in Lync Server 2013</span></span>](lync-server-2013-call-management-features-for-disaster-recovery.md)

  - [<span data-ttu-id="6fde3-115">Настройка сервера сохраняемого чата для обеспечения высокой доступности и аварийного восстановления в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6fde3-115">Configuring Persistent Chat Server for high availability and disaster recovery in Lync Server 2013</span></span>](lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md)

  - [<span data-ttu-id="6fde3-116">Устойчивость главного сайта Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="6fde3-116">Lync Server 2010 metropolitan site resiliency</span></span>](lync-server-2013-compatibility-with-lync-server-2010-metropolitan-site-resiliency.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

