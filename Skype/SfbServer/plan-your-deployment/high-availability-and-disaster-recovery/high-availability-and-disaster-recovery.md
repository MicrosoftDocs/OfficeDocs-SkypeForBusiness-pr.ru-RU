---
title: Планирование высокой доступности и аварийного восстановления в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
f1_keywords:
- ms.lync.plan.HighAvailabilityType
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 3543eb40-54f4-49ef-a058-03aceed4773a
description: Skype для бизнеса Server поддерживает высокий уровень доступности с группировкой серверов, аварийного восстановления с помощью связывания групп, а также несколькими режимами высокой доступности серверной части, в том числе групп доступности AlwaysOn, зеркального отображения баз данных и отказоустойчивого кластера SQL.
ms.openlocfilehash: 3ed1a3e5eff5d793f835c901e2cc5683da22bc77
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34297465"
---
# <a name="plan-for-high-availability-and-disaster-recovery-in-skype-for-business-server"></a><span data-ttu-id="23be9-103">Планирование высокой доступности и аварийного восстановления в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="23be9-103">Plan for high availability and disaster recovery in Skype for Business Server</span></span>
 
<span data-ttu-id="23be9-104">Skype для бизнеса Server поддерживает высокий уровень доступности с группировкой серверов, аварийного восстановления с помощью связывания групп, а также несколькими режимами высокой доступности серверной части, в том числе групп доступности AlwaysOn, зеркального отображения баз данных и отказоустойчивого кластера SQL.</span><span class="sxs-lookup"><span data-stu-id="23be9-104">Skype for Business Server offers high availability with server pooling, disaster recovery with pool pairing, and several modes of Back End Server high availability, including AlwaysOn Availability groups, database mirroring, and SQL failover clustering.</span></span> 
  
<span data-ttu-id="23be9-105">Высокий уровень доступности — это обеспечение доступности служб Skype для бизнеса Server даже в том случае, если один или несколько серверов отключаются.</span><span class="sxs-lookup"><span data-stu-id="23be9-105">High availability refers to making sure that Skype for Business Server services are available even if one or more servers goes down.</span></span> <span data-ttu-id="23be9-106">Аварийное восстановление подразумевает поддержание служб в работоспособном состоянии в случае природной или антропогенной катастрофы с сохранением целостности как можно большего объема данных.</span><span class="sxs-lookup"><span data-stu-id="23be9-106">Disaster recovery refers to keeping services going in the event of a natural or human-caused disaster, and preserving as much data from before the disaster as possible.</span></span>
  
<span data-ttu-id="23be9-107">Как и в предыдущих версиях Lync Server, основная функция высокой доступности для большинства ролей сервера в Skype для бизнеса Server — это избыточность сервера посредством группировки.</span><span class="sxs-lookup"><span data-stu-id="23be9-107">As in previous versions of Lync Server, the main high availability feature for most server roles in Skype for Business Server is server redundancy via pooling.</span></span> <span data-ttu-id="23be9-108">Если сервер, на котором работает определенная роль, завершает работу со сбоем, другие серверы в пуле, выполняющие ту же самую роль, берут на себя нагрузку первого сервера.</span><span class="sxs-lookup"><span data-stu-id="23be9-108">If a server running a certain server role fails, the other servers in the pool running the same role take the load of that server.</span></span> <span data-ttu-id="23be9-109">Это применимо к интерфейсным серверам, пограничным серверам, серверам-посредникам и директорам.</span><span class="sxs-lookup"><span data-stu-id="23be9-109">This applies to Front End Servers, Edge Servers, Mediation Servers, and Directors.</span></span>
  
<span data-ttu-id="23be9-110">Skype для бизнеса Server также предоставляет возможности аварийного восстановления для пулов интерфейсов с внешним интерфейсом.</span><span class="sxs-lookup"><span data-stu-id="23be9-110">Skype for Business Server also provides disaster recovery options for Front End pools.</span></span> <span data-ttu-id="23be9-111">Можно установить два пула в разных географических регионах, чтобы каждый из них был резервным для другого.</span><span class="sxs-lookup"><span data-stu-id="23be9-111">You can set up two pools in different geographical areas to serve as backups for each other.</span></span> <span data-ttu-id="23be9-112">В случае выхода из строя одного пула или сайта резервный пул может продолжить предоставлять службу пользователям на обоих узлах.</span><span class="sxs-lookup"><span data-stu-id="23be9-112">Then if you have an entire pool or site go down, the backup pool can continue to provide service to users at both sites.</span></span>
  
<span data-ttu-id="23be9-113">Skype для бизнеса Server также поддерживает четыре режима высокой доступности серверных серверов: зеркальные наборы данных SQL, группы доступности AlwaysOn, экземпляры отказоустойчивого кластера AlwaysOn (FCI) и отказоустойчивая кластеризация SQL.</span><span class="sxs-lookup"><span data-stu-id="23be9-113">Skype for Business Server also supports four modes of high availability for your Back End Servers: SQL mirroring, AlwaysOn Availability Groups, AlwaysOn Failover Cluster Instances (FCI), and SQL failover clustering.</span></span>
  
> [!NOTE]
> <span data-ttu-id="23be9-114">Зеркальное отображение SQL доступно в Skype для бизнеса Server 2015, но больше не поддерживается в Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="23be9-114">SQL Mirroring is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="23be9-115">Группы доступности AlwaysOn, экземпляры отказоустойчивого кластера AlwaysOn (FCI) и методы отказоустойчивой кластеризации SQL являются предпочтительными в Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="23be9-115">The  AlwaysOn Availability Groups, AlwaysOn Failover Cluster Instances (FCI), and SQL failover clustering methods are preferred with Skype for Business Server 2019.</span></span>

> [!NOTE]
> <span data-ttu-id="23be9-116">Группы доступности AlwaysOn не поддерживаются на серверах сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="23be9-116">AlwaysOn Availability Groups are not supported with Persistent Chat Servers.</span></span> 
  
<span data-ttu-id="23be9-117">В этом разделе рассматриваются эти функции, а также действия по обеспечению высокого уровня доступности и аварийного восстановления для остальных серверных ролей.</span><span class="sxs-lookup"><span data-stu-id="23be9-117">This section explains these features, and also covers what steps you can take for high availability and disaster recovery for some of your other server roles.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="23be9-118">См. также</span><span class="sxs-lookup"><span data-stu-id="23be9-118">See also</span></span>

[<span data-ttu-id="23be9-119">Высокая доступность и управление пулом переднего плана</span><span class="sxs-lookup"><span data-stu-id="23be9-119">Front End Pool high availability and management</span></span>](high-availability.md)
  
[<span data-ttu-id="23be9-120">Внешнее аварийное восстановление пула в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="23be9-120">Front End pool disaster recovery in Skype for Business Server</span></span>](disaster-recovery.md)
  
[<span data-ttu-id="23be9-121">Взаимодействие с пользователем при сбое пула в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="23be9-121">User experience during pool failure in Skype for Business Server</span></span>](user-experience.md)
  
[<span data-ttu-id="23be9-122">Высокий доступ к серверу в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="23be9-122">Back End Server high availability in Skype for Business Server</span></span>](back-end-server.md)
  
[<span data-ttu-id="23be9-123">Общий доступ к файлам с высокой доступностью в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="23be9-123">File sharing high availability in Skype for Business Server</span></span>](file-sharing.md)
