---
title: 'Lync Server 2013: изменения топологии'
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
ms.openlocfilehash: c4453a9b5b8a5fcd60eaad1e437fd4800caddfba
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745179"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="topology-changes-in-lync-server-2013"></a><span data-ttu-id="17242-102">Изменения топологии в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="17242-102">Topology changes in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="17242-103">_**Тема последнего изменения:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="17242-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="17242-104">Требования к топологии и рекомендации для Lync Server 2013 отличаются от требований для более ранних выпусков, описанных в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="17242-104">Topology requirements and considerations for Lync Server 2013 are different from those for earlier releases, as described in this section.</span></span>

<div>

## <a name="new-front-end-pools-architecture"></a><span data-ttu-id="17242-105">Новая архитектура пулов интерфейсов на стороне сервера</span><span class="sxs-lookup"><span data-stu-id="17242-105">New Front End Pools Architecture</span></span>

<span data-ttu-id="17242-106">В Lync Server 2013 архитектура высокоинтерфейсных пулов Enterprise Edition изменилась на архитектуру распределенных систем.</span><span class="sxs-lookup"><span data-stu-id="17242-106">In Lync Server 2013, the architecture of Enterprise Edition Front End pools has changed to a distributed systems architecture.</span></span>

<span data-ttu-id="17242-107">В этой новой архитектуре база данных "сервер" больше не является хранилищем данных в режиме реального времени в пуле.</span><span class="sxs-lookup"><span data-stu-id="17242-107">With this new architecture, the Back End database is no longer the real-time data store in a pool.</span></span> <span data-ttu-id="17242-108">Сведения о конкретном пользователе хранятся на трех серверах переднего плана в пуле.</span><span class="sxs-lookup"><span data-stu-id="17242-108">Information about a particular user is kept on three Front End Servers in the pool.</span></span> <span data-ttu-id="17242-109">Для каждого пользователя один сервер переднего плана действует как образец для сведений о пользователе, а два других сервера переднего плана служат репликами.</span><span class="sxs-lookup"><span data-stu-id="17242-109">For each user, one Front End Server acts as the master for that user’s information, and two other Front End Servers serve as replicas.</span></span> <span data-ttu-id="17242-110">Если сервер переднего плана отключается, то другой сервер переднего плана, который послужил репликой, будет автоматически выдвинут на главную роль.</span><span class="sxs-lookup"><span data-stu-id="17242-110">If a Front End Server goes down, another Front End Server which served as a replica is automatically promoted to master.</span></span>

<span data-ttu-id="17242-111">Это происходит в фоновом режиме, и администраторам не нужно знать, какие серверы переднего плана являются хозяевами, для которых пользователи.</span><span class="sxs-lookup"><span data-stu-id="17242-111">This happens behind the scenes, and administrators do not need to know which Front End Servers are the masters for which users.</span></span> <span data-ttu-id="17242-112">Это распределение хранилища данных повышает производительность и масштабируемость пула и устраняет единственную точку сбоя на одном сервере.</span><span class="sxs-lookup"><span data-stu-id="17242-112">This distribution of data storage improves performance and scalability within the pool, and eliminates the single point of failure of a single Back End Server.</span></span>

<span data-ttu-id="17242-113">Сервер может служить хранилищем резервных копий для данных пользователей и конференций, а также основным хранилищем для других баз данных, таких как база данных группы ответа.</span><span class="sxs-lookup"><span data-stu-id="17242-113">The Back End Server serves as backup storage for user and conference data, and is also the primary storage for other databases such as the Response Group database.</span></span>

<span data-ttu-id="17242-114">Эти улучшения также означают, как вы планируете и собираетесь управлять пулами.</span><span class="sxs-lookup"><span data-stu-id="17242-114">These improvements also mean there are changes in how you plan and maintain your pools.</span></span> <span data-ttu-id="17242-115">Для обеспечения полного количества реплик, для которых разработана архитектура пула переднего плана, рекомендуется использовать по крайней мере три внешних сервера в корпоративном выпуске.</span><span class="sxs-lookup"><span data-stu-id="17242-115">We recommend that all your Enterprise Edition Front End pools include at least three Front End Servers, to provide the full number of replicas that the Front End pool architecture is designed for.</span></span> <span data-ttu-id="17242-116">Кроме того, при добавлении серверов в пул переднего плана, удалении серверов или обновлении серверов необходимо выполнить определенные действия.</span><span class="sxs-lookup"><span data-stu-id="17242-116">Additionally, you must follow certain procedures when adding servers to a Front End pool, removing servers from it, or upgrading servers.</span></span> <span data-ttu-id="17242-117">Дополнительные сведения можно найти [в разделе топологии и компоненты для серверов переднего плана, обмена мгновенными сообщениями и присутствия в Lync Server 2013](lync-server-2013-topologies-and-components-for-front-end-servers-instant-messaging-and-presence.md).</span><span class="sxs-lookup"><span data-stu-id="17242-117">For more information, see [Topologies and components for Front End Servers, instant messaging, and presence in Lync Server 2013](lync-server-2013-topologies-and-components-for-front-end-servers-instant-messaging-and-presence.md).</span></span>

<div>

## <a name="server-role-topology-changes"></a><span data-ttu-id="17242-118">Изменения топологии ролей сервера</span><span class="sxs-lookup"><span data-stu-id="17242-118">Server Role Topology Changes</span></span>

<span data-ttu-id="17242-119">Некоторые роли сервера, которые раньше выполнялись на отдельных серверах, теперь консолидируются в роль сервера переднего плана, что позволяет экономить аппаратные затраты</span><span class="sxs-lookup"><span data-stu-id="17242-119">Some server roles that previously ran on separate servers are now consolidated into the Front End Server role, enabling you to save on hardware costs</span></span>

  - <span data-ttu-id="17242-120">В Lync Server 2013 сервер конференц-связи с интерфейсом/V всегда размещается на сервере переднего плана.</span><span class="sxs-lookup"><span data-stu-id="17242-120">In Lync Server 2013, A/V Conferencing Server is always collocated with Front End Server.</span></span>

  - <span data-ttu-id="17242-121">Передний план для обоих мониторов и архивирования теперь всегда размещаются вместе с интерфейсом сервера переднего плана.</span><span class="sxs-lookup"><span data-stu-id="17242-121">The front ends for both Monitoring and Archiving are now always collocated with Front End Server.</span></span> <span data-ttu-id="17242-122">Для наблюдения и архивации по-прежнему требуется отдельная серверная база данных, которая может быть размещена на одном сервере с серверной базой данных пула и может находиться на разных серверах.</span><span class="sxs-lookup"><span data-stu-id="17242-122">Monitoring and Archiving each still require a separate Back-End Database, which can be collocated on the same server as the Front End Pool’s back-end database, or can be hosted on separate Back-End Servers.</span></span>

  - <span data-ttu-id="17242-123">Теперь сохраняемый сервер чата является ролью сервера.</span><span class="sxs-lookup"><span data-stu-id="17242-123">Persistent Chat Server is now a server role.</span></span> <span data-ttu-id="17242-124">В Microsoft Lync Server 2010 для Microsoft Lync Server 2010 сервер группового чата был сторонним доверенным приложением.</span><span class="sxs-lookup"><span data-stu-id="17242-124">In Microsoft Lync Server 2010, Group Chat Server was a third-party trusted application for Microsoft Lync Server 2010.</span></span> <span data-ttu-id="17242-125">В Lync Server 2013 функции сервера сохраняемого чата реализованы с помощью трех новых ролей сервера:</span><span class="sxs-lookup"><span data-stu-id="17242-125">In Lync Server 2013, Persistent Chat Server functionality is implemented using three new server roles:</span></span>
    
      - <span data-ttu-id="17242-126">**Персистентчатсервице:** Основные службы сервера сохраняемого чата, реализованные как роли переднего плана</span><span class="sxs-lookup"><span data-stu-id="17242-126">**PersistentChatService:** Main Persistent Chat Server services implemented as a front end role</span></span>
    
      - <span data-ttu-id="17242-127">**Персистентчатсторе:** Роль сервера серверной части</span><span class="sxs-lookup"><span data-stu-id="17242-127">**PersistentChatStore:** Back End Server role</span></span>
    
      - <span data-ttu-id="17242-128">**Персистентчаткомплианцесторе:** Серверная роль сервера для обеспечения соответствия требованиям сохраняемого чата</span><span class="sxs-lookup"><span data-stu-id="17242-128">**PersistentChatComplianceStore:** Back End Server role for Persistent Chat Compliance</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

