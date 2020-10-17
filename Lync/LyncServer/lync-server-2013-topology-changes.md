---
title: Изменения в топологии Lync Server 2013
description: Изменения в топологии Lync Server 2013.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Topology changes
ms:assetid: 9e40ef93-9ab0-498c-9bbf-f94584353e53
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688153(v=OCS.15)
ms:contentKeyID: 49733756
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 562766eae939e4510a0d3af20e40b4731c361040
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48549105"
---
# <a name="topology-changes-in-lync-server-2013"></a><span data-ttu-id="c018c-103">Изменения топологии в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c018c-103">Topology changes in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c018c-104">_**Последнее изменение темы:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="c018c-104">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="c018c-105">Требования к топологии и рекомендации для Lync Server 2013 отличаются от требований для более ранних выпусков, как описано в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="c018c-105">Topology requirements and considerations for Lync Server 2013 are different from those for earlier releases, as described in this section.</span></span>

<div>

## <a name="new-front-end-pools-architecture"></a><span data-ttu-id="c018c-106">Новая архитектура интерфейсных пулов</span><span class="sxs-lookup"><span data-stu-id="c018c-106">New Front End Pools Architecture</span></span>

<span data-ttu-id="c018c-107">В Lync Server 2013 архитектура интерфейсных пулов Enterprise Edition изменилась на архитектуру распределенных систем.</span><span class="sxs-lookup"><span data-stu-id="c018c-107">In Lync Server 2013, the architecture of Enterprise Edition Front End pools has changed to a distributed systems architecture.</span></span>

<span data-ttu-id="c018c-p101">В новой архитектуре тыловая база данных больше не является хранилищем данных, работающим в режиме реального времени в пуле. Сведения об отдельных пользователях хранятся на трех серверах переднего плана в пуле. Для каждого пользователя один сервер переднего плана действует как основное хранилище данных, а два других — как реплики. При отказе основного сервера его функции автоматически начинает выполнять один из серверов-реплик.</span><span class="sxs-lookup"><span data-stu-id="c018c-p101">With this new architecture, the Back End database is no longer the real-time data store in a pool. Information about a particular user is kept on three Front End Servers in the pool. For each user, one Front End Server acts as the master for that user’s information, and two other Front End Servers serve as replicas. If a Front End Server goes down, another Front End Server which served as a replica is automatically promoted to master.</span></span>

<span data-ttu-id="c018c-112">Это происходит в фоновом режиме и администраторам необязательно знать, какие серверы переднего плана являются основными для определенных пользователей.</span><span class="sxs-lookup"><span data-stu-id="c018c-112">This happens behind the scenes, and administrators do not need to know which Front End Servers are the masters for which users.</span></span> <span data-ttu-id="c018c-113">Это распределение хранения данных повышает производительность и масштабируемость пула, а также исключает одну точку отказа одного внутреннего сервера.</span><span class="sxs-lookup"><span data-stu-id="c018c-113">This distribution of data storage improves performance and scalability within the pool, and eliminates the single point of failure of a single Back End Server.</span></span>

<span data-ttu-id="c018c-114">Тыловой сервер действует как хранилище резервной копии пользовательских данных и данных конференций, а также как основное хранилище других баз данных, таких как база данных группы ответа.</span><span class="sxs-lookup"><span data-stu-id="c018c-114">The Back End Server serves as backup storage for user and conference data, and is also the primary storage for other databases such as the Response Group database.</span></span>

<span data-ttu-id="c018c-115">Эти улучшения привели к изменению планирования и обслуживания пулов.</span><span class="sxs-lookup"><span data-stu-id="c018c-115">These improvements also mean there are changes in how you plan and maintain your pools.</span></span> <span data-ttu-id="c018c-116">Для всех интерфейсных пулов Enterprise Edition рекомендуется включить по крайней мере три сервера переднего плана, чтобы обеспечить полное количество реплик, для которых предназначена архитектура пула переднего плана.</span><span class="sxs-lookup"><span data-stu-id="c018c-116">We recommend that all your Enterprise Edition Front End pools include at least three Front End Servers, to provide the full number of replicas that the Front End pool architecture is designed for.</span></span> <span data-ttu-id="c018c-117">Кроме того, необходимо выполнить определенные процедуры при добавлении серверов в пул переднего плана, удалении серверов из него или обновлении серверов.</span><span class="sxs-lookup"><span data-stu-id="c018c-117">Additionally, you must follow certain procedures when adding servers to a Front End pool, removing servers from it, or upgrading servers.</span></span> <span data-ttu-id="c018c-118">Для получения дополнительных сведений см [топология и компоненты для серверов переднего плана, обмена мгновенными сообщениями и сведений о присутствии в Lync Server 2013](lync-server-2013-topologies-and-components-for-front-end-servers-instant-messaging-and-presence.md).</span><span class="sxs-lookup"><span data-stu-id="c018c-118">For more information, see [Topologies and components for Front End Servers, instant messaging, and presence in Lync Server 2013](lync-server-2013-topologies-and-components-for-front-end-servers-instant-messaging-and-presence.md).</span></span>

<div>

## <a name="server-role-topology-changes"></a><span data-ttu-id="c018c-119">Изменения топологии ролей сервера</span><span class="sxs-lookup"><span data-stu-id="c018c-119">Server Role Topology Changes</span></span>

<span data-ttu-id="c018c-120">Некоторые роли сервера, которые раньше выполнялись на отдельных серверах, теперь объединены в роли сервера переднего плана. Это позволяет сократить расходы на оборудование.</span><span class="sxs-lookup"><span data-stu-id="c018c-120">Some server roles that previously ran on separate servers are now consolidated into the Front End Server role, enabling you to save on hardware costs</span></span>

  - <span data-ttu-id="c018c-121">В Lync Server 2013 сервер аудио-и видеоконференций всегда размещен на сервере переднего плана.</span><span class="sxs-lookup"><span data-stu-id="c018c-121">In Lync Server 2013, A/V Conferencing Server is always collocated with Front End Server.</span></span>

  - <span data-ttu-id="c018c-p104">Интерфейсы мониторинга и архивации теперь размещаются совместно с сервером переднего плана. Для мониторинга и архивации по-прежнему требуются отдельные серверные базы данных, которые могут быть размещены на одном сервере в качестве тыловой базы данных интерфейсного пула или на отдельных тыловых серверах.</span><span class="sxs-lookup"><span data-stu-id="c018c-p104">The front ends for both Monitoring and Archiving are now always collocated with Front End Server. Monitoring and Archiving each still require a separate Back-End Database, which can be collocated on the same server as the Front End Pool’s back-end database, or can be hosted on separate Back-End Servers.</span></span>

  - <span data-ttu-id="c018c-124">Теперь сервер сохраняемого чата является ролью сервера.</span><span class="sxs-lookup"><span data-stu-id="c018c-124">Persistent Chat Server is now a server role.</span></span> <span data-ttu-id="c018c-125">В Microsoft Lync Server 2010 сервер групповой чат являлся сторонним доверенным приложением для Microsoft Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="c018c-125">In Microsoft Lync Server 2010, Group Chat Server was a third-party trusted application for Microsoft Lync Server 2010.</span></span> <span data-ttu-id="c018c-126">В Lync Server 2013 функции сервера сохраняемого чата реализованы с помощью трех новых ролей сервера:</span><span class="sxs-lookup"><span data-stu-id="c018c-126">In Lync Server 2013, Persistent Chat Server functionality is implemented using three new server roles:</span></span>
    
      - <span data-ttu-id="c018c-127">**PersistentChatService:** Основные службы сервера сохраняемого чата, реализованные в роли сервера переднего плана</span><span class="sxs-lookup"><span data-stu-id="c018c-127">**PersistentChatService:** Main Persistent Chat Server services implemented as a front end role</span></span>
    
      - <span data-ttu-id="c018c-128">**PersistentChatStore:** Роль внутреннего сервера</span><span class="sxs-lookup"><span data-stu-id="c018c-128">**PersistentChatStore:** Back End Server role</span></span>
    
      - <span data-ttu-id="c018c-129">**PersistentChatComplianceStore:** Роль внутреннего сервера для обеспечения соответствия сохраняемого чата</span><span class="sxs-lookup"><span data-stu-id="c018c-129">**PersistentChatComplianceStore:** Back End Server role for Persistent Chat Compliance</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

