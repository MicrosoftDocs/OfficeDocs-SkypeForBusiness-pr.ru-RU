---
title: 'Lync Server 2013: Планирование высокой доступности и аварийного восстановления'
description: 'Lync Server 2013: Планирование высокой доступности и аварийного восстановления.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for high availability and disaster recovery
ms:assetid: 15a72073-0336-45dd-b2a0-35e7522c6000
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204703(v=OCS.15)
ms:contentKeyID: 48183497
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6bb5f430201c48738421c4fbe72151ca58173898
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48571845"
---
# <a name="planning-for-high-availability-and-disaster-recovery-in-lync-server-2013"></a><span data-ttu-id="a1598-103">Планирование обеспечения высокой доступности и аварийного восстановления в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a1598-103">Planning for high availability and disaster recovery in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a1598-104">_**Последнее изменение темы:** 2013-10-31_</span><span class="sxs-lookup"><span data-stu-id="a1598-104">_**Topic Last Modified:** 2013-10-31_</span></span>

<span data-ttu-id="a1598-105">Как и в Lync Server 2010, основная схема высокой доступности для большинства ролей серверов в Lync Server 2013 основана на избыточности сервера посредством пула.</span><span class="sxs-lookup"><span data-stu-id="a1598-105">As in Lync Server 2010, the main high availability scheme for most server roles in Lync Server 2013 is based on server redundancy via pooling.</span></span> <span data-ttu-id="a1598-106">При сбое сервера с определенными ролями остальные серверы в пуле с такими же ролями берут на себя нагрузку этого сервера.</span><span class="sxs-lookup"><span data-stu-id="a1598-106">If a server running a certain server role fails, the other servers in the pool running the same role take the load of that server.</span></span> <span data-ttu-id="a1598-107">Это касается серверов переднего плана, пограничных серверов, серверов-посредников и Директоров.</span><span class="sxs-lookup"><span data-stu-id="a1598-107">This applies to Front End Servers, Edge Servers, Mediation Servers, and Directors.</span></span>

<span data-ttu-id="a1598-108">Lync Server 2013 добавляет новые меры аварийного восстановления для пулов переднего плана с помощью географических распределения серверов в двух центрах обработки данных, чтобы обеспечить продолжение обслуживания всего одного пула или сайта.</span><span class="sxs-lookup"><span data-stu-id="a1598-108">Lync Server 2013 adds new disaster recovery measures for Front End pools by introducing geographical dispersement of your servers into two data centers to provide continuation of service should one entire pool or site go down.</span></span>

<span data-ttu-id="a1598-109">Lync Server 2013 также повышает высокую доступность внутреннего сервера за счет поддержки синхронного зеркального отображения SQL для серверных баз данных.</span><span class="sxs-lookup"><span data-stu-id="a1598-109">Lync Server 2013 also enhances Back End Server high availability, by supporting synchronous SQL mirroring for your Back End databases.</span></span>

<span data-ttu-id="a1598-110">В этом разделе объясняются основные функции обеспечения высокого уровня доступности и аварийного восстановления, а также описываются действия, которые можно выполнить для обеспечения высокой доступности и аварийного восстановления для других ролей сервера.</span><span class="sxs-lookup"><span data-stu-id="a1598-110">This section explains these major high availability and disaster recovery features, and also covers what steps you can take for high availability and disaster recovery for your other server roles as well.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="a1598-111">Содержание</span><span class="sxs-lookup"><span data-stu-id="a1598-111">In This Section</span></span>

  - [<span data-ttu-id="a1598-112">Аварийное восстановление пула переднего плана в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a1598-112">Front End pool disaster recovery in Lync Server 2013</span></span>](lync-server-2013-front-end-pool-disaster-recovery.md)

  - [<span data-ttu-id="a1598-113">Аварийное восстановление пограничного сервера в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a1598-113">Edge Server disaster recovery in Lync Server 2013</span></span>](lync-server-2013-edge-server-disaster-recovery.md)

  - [<span data-ttu-id="a1598-114">Планирование устойчивости корпоративной голосовой связи в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a1598-114">Planning for Enterprise Voice resiliency in Lync Server 2013</span></span>](lync-server-2013-planning-for-enterprise-voice-resiliency.md)

  - [<span data-ttu-id="a1598-115">Функции управления вызовами для аварийного восстановления в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a1598-115">Call management features for disaster recovery in Lync Server 2013</span></span>](lync-server-2013-call-management-features-for-disaster-recovery.md)

  - [<span data-ttu-id="a1598-116">Настройка сервера сохраняемого чата для обеспечения высокой доступности и аварийного восстановления в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a1598-116">Configuring Persistent Chat Server for high availability and disaster recovery in Lync Server 2013</span></span>](lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md)

  - [<span data-ttu-id="a1598-117">Устойчивость сайта Lync Server 2010 для городового сайта</span><span class="sxs-lookup"><span data-stu-id="a1598-117">Lync Server 2010 metropolitan site resiliency</span></span>](lync-server-2013-compatibility-with-lync-server-2010-metropolitan-site-resiliency.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

