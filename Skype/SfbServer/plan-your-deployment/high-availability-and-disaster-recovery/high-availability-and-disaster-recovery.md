---
title: Планирование высокой доступности и аварийного восстановления в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.custom:
- ms.lync.plan.HighAvailabilityType
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 3543eb40-54f4-49ef-a058-03aceed4773a
description: Skype для бизнеса Server поддерживает высокий уровень доступности с группировкой серверов, аварийного восстановления с помощью связывания групп, а также несколькими режимами высокой доступности серверной части, в том числе групп доступности AlwaysOn, зеркального отображения баз данных и отказоустойчивого кластера SQL.
ms.openlocfilehash: 521ddaa9878ba660e509f248d2f2ffb944608d87
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815927"
---
# <a name="plan-for-high-availability-and-disaster-recovery-in-skype-for-business-server"></a><span data-ttu-id="50c39-103">Планирование высокой доступности и аварийного восстановления в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="50c39-103">Plan for high availability and disaster recovery in Skype for Business Server</span></span>
 
<span data-ttu-id="50c39-104">Skype для бизнеса Server поддерживает высокий уровень доступности с группировкой серверов, аварийного восстановления с помощью связывания групп, а также несколькими режимами высокой доступности серверной части, в том числе групп доступности AlwaysOn, зеркального отображения баз данных и отказоустойчивого кластера SQL.</span><span class="sxs-lookup"><span data-stu-id="50c39-104">Skype for Business Server offers high availability with server pooling, disaster recovery with pool pairing, and several modes of Back End Server high availability, including AlwaysOn Availability groups, database mirroring, and SQL failover clustering.</span></span> 
  
<span data-ttu-id="50c39-105">Высокий уровень доступности — это обеспечение доступности служб Skype для бизнеса Server даже в том случае, если один или несколько серверов отключаются.</span><span class="sxs-lookup"><span data-stu-id="50c39-105">High availability refers to making sure that Skype for Business Server services are available even if one or more servers goes down.</span></span> <span data-ttu-id="50c39-106">Аварийное восстановление подразумевает поддержание служб в работоспособном состоянии в случае природной или антропогенной катастрофы с сохранением целостности как можно большего объема данных.</span><span class="sxs-lookup"><span data-stu-id="50c39-106">Disaster recovery refers to keeping services going in the event of a natural or human-caused disaster, and preserving as much data from before the disaster as possible.</span></span>
  
<span data-ttu-id="50c39-107">Как и в предыдущих версиях Lync Server, основная функция высокой доступности для большинства ролей сервера в Skype для бизнеса Server — это избыточность сервера посредством группировки.</span><span class="sxs-lookup"><span data-stu-id="50c39-107">As in previous versions of Lync Server, the main high availability feature for most server roles in Skype for Business Server is server redundancy via pooling.</span></span> <span data-ttu-id="50c39-108">При сбое сервера с определенными ролями остальные серверы в пуле с такими же ролями берут на себя нагрузку этого сервера.</span><span class="sxs-lookup"><span data-stu-id="50c39-108">If a server running a certain server role fails, the other servers in the pool running the same role take the load of that server.</span></span> <span data-ttu-id="50c39-109">Это касается серверов переднего плана, пограничных серверов, серверов-посредников и Директоров.</span><span class="sxs-lookup"><span data-stu-id="50c39-109">This applies to Front End Servers, Edge Servers, Mediation Servers, and Directors.</span></span>
  
<span data-ttu-id="50c39-110">Skype для бизнеса Server также предоставляет возможности аварийного восстановления для пулов интерфейсов с внешним интерфейсом.</span><span class="sxs-lookup"><span data-stu-id="50c39-110">Skype for Business Server also provides disaster recovery options for Front End pools.</span></span> <span data-ttu-id="50c39-111">Можно установить два пула в разных географических регионах, чтобы каждый из них был резервным для другого.</span><span class="sxs-lookup"><span data-stu-id="50c39-111">You can set up two pools in different geographical areas to serve as backups for each other.</span></span> <span data-ttu-id="50c39-112">В случае выхода из строя одного пула или сайта резервный пул может продолжить предоставлять службу пользователям на обоих узлах.</span><span class="sxs-lookup"><span data-stu-id="50c39-112">Then if you have an entire pool or site go down, the backup pool can continue to provide service to users at both sites.</span></span>
  
<span data-ttu-id="50c39-113">Skype для бизнеса Server также поддерживает четыре режима высокой доступности серверных серверов: зеркальные наборы данных SQL, группы доступности AlwaysOn, экземпляры отказоустойчивого кластера AlwaysOn (FCI) и отказоустойчивая кластеризация SQL.</span><span class="sxs-lookup"><span data-stu-id="50c39-113">Skype for Business Server also supports four modes of high availability for your Back End Servers: SQL mirroring, AlwaysOn Availability Groups, AlwaysOn Failover Cluster Instances (FCI), and SQL failover clustering.</span></span>
  
> [!NOTE]
> <span data-ttu-id="50c39-114">Зеркальное отображение SQL доступно в Skype для бизнеса Server 2015, но больше не поддерживается в Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="50c39-114">SQL Mirroring is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="50c39-115">В Skype для бизнеса Server 2019 рекомендуется использовать группы доступности AlwaysOn, экземпляры отказоустойчивых кластеров AlwaysOn (FCI), и методы отказоустойчивой кластеризации SQL.</span><span class="sxs-lookup"><span data-stu-id="50c39-115">The  AlwaysOn Availability Groups, AlwaysOn Failover Cluster Instances (FCI), and SQL failover clustering methods are preferred with Skype for Business Server 2019.</span></span>

> [!NOTE]
> <span data-ttu-id="50c39-116">Группы доступности AlwaysOn не поддерживаются на серверах сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="50c39-116">AlwaysOn Availability Groups are not supported with Persistent Chat Servers.</span></span> 
  
<span data-ttu-id="50c39-117">В этом разделе рассматриваются эти функции, а также действия по обеспечению высокого уровня доступности и аварийного восстановления для остальных серверных ролей.</span><span class="sxs-lookup"><span data-stu-id="50c39-117">This section explains these features, and also covers what steps you can take for high availability and disaster recovery for some of your other server roles.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="50c39-118">См. также</span><span class="sxs-lookup"><span data-stu-id="50c39-118">See also</span></span>

[<span data-ttu-id="50c39-119">Высокая доступность и управление пулом переднего плана</span><span class="sxs-lookup"><span data-stu-id="50c39-119">Front End Pool high availability and management</span></span>](high-availability.md)
  
[<span data-ttu-id="50c39-120">Внешнее аварийное восстановление пула в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="50c39-120">Front End pool disaster recovery in Skype for Business Server</span></span>](disaster-recovery.md)
  
[<span data-ttu-id="50c39-121">Взаимодействие с пользователем при сбое пула в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="50c39-121">User experience during pool failure in Skype for Business Server</span></span>](user-experience.md)
  
[<span data-ttu-id="50c39-122">Высокий доступ к серверу в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="50c39-122">Back End Server high availability in Skype for Business Server</span></span>](back-end-server.md)
  
[<span data-ttu-id="50c39-123">Общий доступ к файлам с высокой доступностью в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="50c39-123">File sharing high availability in Skype for Business Server</span></span>](file-sharing.md)
