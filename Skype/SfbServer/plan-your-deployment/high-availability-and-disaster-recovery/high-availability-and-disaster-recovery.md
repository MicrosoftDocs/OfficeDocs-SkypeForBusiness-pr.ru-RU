---
title: Планирование высокой доступности и аварийного восстановления в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: Skype для бизнеса Server обеспечивает высокую доступность с помощью пула серверов, аварийного восстановления с сопряжением пулов и нескольких режимов высокой доступности тыловой части сервера, включая группы доступности AlwaysOn, зеркальное зеркальное отражение баз данных и SQL отключаемую кластерию.
ms.openlocfilehash: 61b720bc9dce5bc8dc54a6c493429b0a3c9b27d2
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802819"
---
# <a name="plan-for-high-availability-and-disaster-recovery-in-skype-for-business-server"></a><span data-ttu-id="962be-103">Планирование высокой доступности и аварийного восстановления в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="962be-103">Plan for high availability and disaster recovery in Skype for Business Server</span></span>
 
<span data-ttu-id="962be-104">Skype для бизнеса Server обеспечивает высокую доступность с помощью пула серверов, аварийного восстановления с сопряжением пулов и нескольких режимов высокой доступности тыловой части сервера, включая группы доступности AlwaysOn, зеркальное зеркальное отражение баз данных и SQL отключаемую кластерию.</span><span class="sxs-lookup"><span data-stu-id="962be-104">Skype for Business Server offers high availability with server pooling, disaster recovery with pool pairing, and several modes of Back End Server high availability, including AlwaysOn Availability groups, database mirroring, and SQL failover clustering.</span></span> 
  
<span data-ttu-id="962be-105">Высокий уровень доступности означает, что службы Skype для бизнеса Server доступны, даже если один или несколько серверов не будут доступны.</span><span class="sxs-lookup"><span data-stu-id="962be-105">High availability refers to making sure that Skype for Business Server services are available even if one or more servers goes down.</span></span> <span data-ttu-id="962be-106">Аварийное восстановление означает, что службы будут поддерживаться в случае естественной или вызванной человеком аварии и сохранять как можно больше данных до аварии.</span><span class="sxs-lookup"><span data-stu-id="962be-106">Disaster recovery refers to keeping services going in the event of a natural or human-caused disaster, and preserving as much data from before the disaster as possible.</span></span>
  
<span data-ttu-id="962be-107">Как и в предыдущих версиях Lync Server, основной функцией высокой доступности для большинства ролей сервера в Skype для бизнеса Server является избыточность серверов посредством пула.</span><span class="sxs-lookup"><span data-stu-id="962be-107">As in previous versions of Lync Server, the main high availability feature for most server roles in Skype for Business Server is server redundancy via pooling.</span></span> <span data-ttu-id="962be-108">При сбое сервера с определенными ролями остальные серверы в пуле с такими же ролями берут на себя нагрузку этого сервера.</span><span class="sxs-lookup"><span data-stu-id="962be-108">If a server running a certain server role fails, the other servers in the pool running the same role take the load of that server.</span></span> <span data-ttu-id="962be-109">Это касается серверов переднего плана, пограничных серверов, серверов-посредников и Директоров.</span><span class="sxs-lookup"><span data-stu-id="962be-109">This applies to Front End Servers, Edge Servers, Mediation Servers, and Directors.</span></span>
  
<span data-ttu-id="962be-110">Skype для бизнеса Server также предоставляет варианты аварийного восстановления для пулов переднего сервера.</span><span class="sxs-lookup"><span data-stu-id="962be-110">Skype for Business Server also provides disaster recovery options for Front End pools.</span></span> <span data-ttu-id="962be-111">Вы можете настроить два пула в разных географических областях для друг друга в качестве резервных копий.</span><span class="sxs-lookup"><span data-stu-id="962be-111">You can set up two pools in different geographical areas to serve as backups for each other.</span></span> <span data-ttu-id="962be-112">Затем, если весь пул или сайт отойдут из системы, резервный пул может продолжать предоставлять службы пользователям на обоих сайтах.</span><span class="sxs-lookup"><span data-stu-id="962be-112">Then if you have an entire pool or site go down, the backup pool can continue to provide service to users at both sites.</span></span>
  
<span data-ttu-id="962be-113">Skype для бизнеса Server также поддерживает четыре режима высокой доступности для тыловые серверы: зеркальное зеркальное SQL, группы доступности AlwaysOn, экземпляры кластера для отбойных вызовов AlwaysOn (FCI) и SQL отбойной кластерации.</span><span class="sxs-lookup"><span data-stu-id="962be-113">Skype for Business Server also supports four modes of high availability for your Back End Servers: SQL mirroring, AlwaysOn Availability Groups, AlwaysOn Failover Cluster Instances (FCI), and SQL failover clustering.</span></span>
  
> [!NOTE]
> <span data-ttu-id="962be-114">SQL зеркальное отражение доступно в Skype для бизнеса Server 2015, но больше не поддерживается в Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="962be-114">SQL Mirroring is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="962be-115">В Skype для бизнеса Server 2019 предпочтительнее использовать группы доступности AlwaysOn, экземпляры кластера для отокрутки AlwaysOn и SQL кластеров.</span><span class="sxs-lookup"><span data-stu-id="962be-115">The  AlwaysOn Availability Groups, AlwaysOn Failover Cluster Instances (FCI), and SQL failover clustering methods are preferred with Skype for Business Server 2019.</span></span>

> [!NOTE]
> <span data-ttu-id="962be-116">Группы доступности AlwaysOn не поддерживаются серверами сохраняемой беседы.</span><span class="sxs-lookup"><span data-stu-id="962be-116">AlwaysOn Availability Groups are not supported with Persistent Chat Servers.</span></span> 
  
<span data-ttu-id="962be-117">В этом разделе поясняется, какие действия можно предпринять для высокой доступности и аварийного восстановления для некоторых других ролей сервера.</span><span class="sxs-lookup"><span data-stu-id="962be-117">This section explains these features, and also covers what steps you can take for high availability and disaster recovery for some of your other server roles.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="962be-118">См. также</span><span class="sxs-lookup"><span data-stu-id="962be-118">See also</span></span>

[<span data-ttu-id="962be-119">Высокая доступность и управление пулом переднего уровня</span><span class="sxs-lookup"><span data-stu-id="962be-119">Front End Pool high availability and management</span></span>](high-availability.md)
  
[<span data-ttu-id="962be-120">Аварийное восстановление пула переднего сервера в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="962be-120">Front End pool disaster recovery in Skype for Business Server</span></span>](disaster-recovery.md)
  
[<span data-ttu-id="962be-121">Пользовательский интерфейс во время сбоя пула в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="962be-121">User experience during pool failure in Skype for Business Server</span></span>](user-experience.md)
  
[<span data-ttu-id="962be-122">Высокая доступность серверов в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="962be-122">Back End Server high availability in Skype for Business Server</span></span>](back-end-server.md)
  
[<span data-ttu-id="962be-123">Высокая доступность общего доступа к файлам в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="962be-123">File sharing high availability in Skype for Business Server</span></span>](file-sharing.md)
