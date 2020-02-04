---
title: Планирование высокой доступности и аварийного восстановления в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
f1.keywords:
- ms.lync.plan.HighAvailabilityType
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 3543eb40-54f4-49ef-a058-03aceed4773a
description: Skype для бизнеса Server поддерживает высокий уровень доступности с группировкой серверов, аварийного восстановления с помощью связывания групп, а также несколькими режимами высокой доступности серверной части, в том числе групп доступности AlwaysOn, зеркального отображения баз данных и отказоустойчивого кластера SQL.
ms.openlocfilehash: 31059936249aa4e691f3e6b4b467841fd66a04ea
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2020
ms.locfileid: "41695974"
---
# <a name="plan-for-high-availability-and-disaster-recovery-in-skype-for-business-server"></a><span data-ttu-id="5abb1-103">Планирование высокой доступности и аварийного восстановления в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="5abb1-103">Plan for high availability and disaster recovery in Skype for Business Server</span></span>
 
<span data-ttu-id="5abb1-104">Skype для бизнеса Server поддерживает высокий уровень доступности с группировкой серверов, аварийного восстановления с помощью связывания групп, а также несколькими режимами высокой доступности серверной части, в том числе групп доступности AlwaysOn, зеркального отображения баз данных и отказоустойчивого кластера SQL.</span><span class="sxs-lookup"><span data-stu-id="5abb1-104">Skype for Business Server offers high availability with server pooling, disaster recovery with pool pairing, and several modes of Back End Server high availability, including AlwaysOn Availability groups, database mirroring, and SQL failover clustering.</span></span> 
  
<span data-ttu-id="5abb1-105">Высокий уровень доступности — это обеспечение доступности служб Skype для бизнеса Server даже в том случае, если один или несколько серверов отключаются.</span><span class="sxs-lookup"><span data-stu-id="5abb1-105">High availability refers to making sure that Skype for Business Server services are available even if one or more servers goes down.</span></span> <span data-ttu-id="5abb1-106">Аварийное восстановление подразумевает поддержание служб в работоспособном состоянии в случае природной или антропогенной катастрофы с сохранением целостности как можно большего объема данных.</span><span class="sxs-lookup"><span data-stu-id="5abb1-106">Disaster recovery refers to keeping services going in the event of a natural or human-caused disaster, and preserving as much data from before the disaster as possible.</span></span>
  
<span data-ttu-id="5abb1-107">Как и в предыдущих версиях Lync Server, основная функция высокой доступности для большинства ролей сервера в Skype для бизнеса Server — это избыточность сервера посредством группировки.</span><span class="sxs-lookup"><span data-stu-id="5abb1-107">As in previous versions of Lync Server, the main high availability feature for most server roles in Skype for Business Server is server redundancy via pooling.</span></span> <span data-ttu-id="5abb1-108">При сбое сервера с определенными ролями остальные серверы в пуле с такими же ролями берут на себя нагрузку этого сервера.</span><span class="sxs-lookup"><span data-stu-id="5abb1-108">If a server running a certain server role fails, the other servers in the pool running the same role take the load of that server.</span></span> <span data-ttu-id="5abb1-109">Это касается серверов переднего плана, пограничных серверов, серверов-посредников и Директоров.</span><span class="sxs-lookup"><span data-stu-id="5abb1-109">This applies to Front End Servers, Edge Servers, Mediation Servers, and Directors.</span></span>
  
<span data-ttu-id="5abb1-110">Skype для бизнеса Server также предоставляет возможности аварийного восстановления для пулов интерфейсов с внешним интерфейсом.</span><span class="sxs-lookup"><span data-stu-id="5abb1-110">Skype for Business Server also provides disaster recovery options for Front End pools.</span></span> <span data-ttu-id="5abb1-111">Можно установить два пула в разных географических регионах, чтобы каждый из них был резервным для другого.</span><span class="sxs-lookup"><span data-stu-id="5abb1-111">You can set up two pools in different geographical areas to serve as backups for each other.</span></span> <span data-ttu-id="5abb1-112">В случае выхода из строя одного пула или сайта резервный пул может продолжить предоставлять службу пользователям на обоих узлах.</span><span class="sxs-lookup"><span data-stu-id="5abb1-112">Then if you have an entire pool or site go down, the backup pool can continue to provide service to users at both sites.</span></span>
  
<span data-ttu-id="5abb1-113">Skype для бизнеса Server также поддерживает четыре режима высокой доступности серверных серверов: зеркальные наборы данных SQL, группы доступности AlwaysOn, экземпляры отказоустойчивого кластера AlwaysOn (FCI) и отказоустойчивая кластеризация SQL.</span><span class="sxs-lookup"><span data-stu-id="5abb1-113">Skype for Business Server also supports four modes of high availability for your Back End Servers: SQL mirroring, AlwaysOn Availability Groups, AlwaysOn Failover Cluster Instances (FCI), and SQL failover clustering.</span></span>
  
> [!NOTE]
> <span data-ttu-id="5abb1-114">Зеркальное отображение SQL доступно в Skype для бизнеса Server 2015, но больше не поддерживается в Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="5abb1-114">SQL Mirroring is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="5abb1-115">В Skype для бизнеса Server 2019 рекомендуется использовать группы доступности AlwaysOn, экземпляры отказоустойчивых кластеров AlwaysOn (FCI), и методы отказоустойчивой кластеризации SQL.</span><span class="sxs-lookup"><span data-stu-id="5abb1-115">The  AlwaysOn Availability Groups, AlwaysOn Failover Cluster Instances (FCI), and SQL failover clustering methods are preferred with Skype for Business Server 2019.</span></span>

> [!NOTE]
> <span data-ttu-id="5abb1-116">Группы доступности AlwaysOn не поддерживаются на серверах сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="5abb1-116">AlwaysOn Availability Groups are not supported with Persistent Chat Servers.</span></span> 
  
<span data-ttu-id="5abb1-117">В этом разделе рассматриваются эти функции, а также действия по обеспечению высокого уровня доступности и аварийного восстановления для остальных серверных ролей.</span><span class="sxs-lookup"><span data-stu-id="5abb1-117">This section explains these features, and also covers what steps you can take for high availability and disaster recovery for some of your other server roles.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="5abb1-118">См. также</span><span class="sxs-lookup"><span data-stu-id="5abb1-118">See also</span></span>

[<span data-ttu-id="5abb1-119">Высокая доступность и управление пулом переднего плана</span><span class="sxs-lookup"><span data-stu-id="5abb1-119">Front End Pool high availability and management</span></span>](high-availability.md)
  
[<span data-ttu-id="5abb1-120">Внешнее аварийное восстановление пула в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="5abb1-120">Front End pool disaster recovery in Skype for Business Server</span></span>](disaster-recovery.md)
  
[<span data-ttu-id="5abb1-121">Взаимодействие с пользователем при сбое пула в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="5abb1-121">User experience during pool failure in Skype for Business Server</span></span>](user-experience.md)
  
[<span data-ttu-id="5abb1-122">Высокий доступ к серверу в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="5abb1-122">Back End Server high availability in Skype for Business Server</span></span>](back-end-server.md)
  
[<span data-ttu-id="5abb1-123">Общий доступ к файлам с высокой доступностью в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="5abb1-123">File sharing high availability in Skype for Business Server</span></span>](file-sharing.md)
