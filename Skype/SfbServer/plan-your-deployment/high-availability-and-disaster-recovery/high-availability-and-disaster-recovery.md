---
title: Планирование высокой доступности и аварийного восстановления в Skype для бизнеса Server 2015
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 1/29/2018
ms.audience: ITPro
ms.topic: conceptual
f1_keywords:
- ms.lync.plan.HighAvailabilityType
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 3543eb40-54f4-49ef-a058-03aceed4773a
description: Скайп для Business Server предлагает высокой доступности с помощью пула аварийного восстановления с помощью связывания пула и нескольких режимах Тыловой сервер высокой доступности, включая группы обеспечения доступности AlwaysOn, зеркальное отображение базы данных и отказоустойчивый кластер SQL server.
ms.openlocfilehash: e2e433112146e3be771abb12ef50e09749e8e325
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="plan-for-high-availability-and-disaster-recovery-in-skype-for-business-server-2015"></a><span data-ttu-id="a8d0a-103">Планирование высокой доступности и аварийного восстановления в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="a8d0a-103">Plan for high availability and disaster recovery in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="a8d0a-104">Скайп для Business Server предлагает высокой доступности с помощью пула аварийного восстановления с помощью связывания пула и нескольких режимах Тыловой сервер высокой доступности, включая группы обеспечения доступности AlwaysOn, зеркальное отображение базы данных и отказоустойчивый кластер SQL server.</span><span class="sxs-lookup"><span data-stu-id="a8d0a-104">Skype for Business Server offers high availability with server pooling, disaster recovery with pool pairing, and several modes of Back End Server high availability, including AlwaysOn Availability groups, database mirroring, and SQL failover clustering.</span></span> 
  
<span data-ttu-id="a8d0a-105">Высокая доступность относится к проверке того, что Скайп для служб Business Server доступны даже в том случае, если один или несколько серверов, тем ниже.</span><span class="sxs-lookup"><span data-stu-id="a8d0a-105">High availability refers to making sure that Skype for Business Server services are available even if one or more servers goes down.</span></span> <span data-ttu-id="a8d0a-106">Аварийное восстановление означает поддержку работы служб в случае природного или антропогенного бедствия, а также сохранение по возможности большого количества данных, созданных до бедствия.</span><span class="sxs-lookup"><span data-stu-id="a8d0a-106">Disaster recovery refers to keeping services going in the event of a natural or human-caused disaster, and preserving as much data from before the disaster as possible.</span></span>
  
<span data-ttu-id="a8d0a-107">Как и в предыдущих версиях Lync Server компонент основной высокой доступности для большинства ролей сервера в Скайп для Business Server — избыточности сервера с помощью пула.</span><span class="sxs-lookup"><span data-stu-id="a8d0a-107">As in previous versions of Lync Server, the main high availability feature for most server roles in Skype for Business Server is server redundancy via pooling.</span></span> <span data-ttu-id="a8d0a-108">Если сервер, на котором работает определенная роль, завершает работу со сбоем, другие серверы в пуле, выполняющие ту же самую роль, берут на себя нагрузку первого сервера.</span><span class="sxs-lookup"><span data-stu-id="a8d0a-108">If a server running a certain server role fails, the other servers in the pool running the same role take the load of that server.</span></span> <span data-ttu-id="a8d0a-109">Это применимо к интерфейсным серверам, пограничным серверам, серверам-посредникам и директорам.</span><span class="sxs-lookup"><span data-stu-id="a8d0a-109">This applies to Front End Servers, Edge Servers, Mediation Servers, and Directors.</span></span>
  
<span data-ttu-id="a8d0a-110">Скайп для Business Server также приводятся аварийного восстановления для пулов переднего плана.</span><span class="sxs-lookup"><span data-stu-id="a8d0a-110">Skype for Business Server also provides disaster recovery options for Front End pools.</span></span> <span data-ttu-id="a8d0a-111">Можно установить два пула в разных географических регионах, чтобы каждый из них был резервным для другого.</span><span class="sxs-lookup"><span data-stu-id="a8d0a-111">You can set up two pools in different geographical areas to serve as backups for each other.</span></span> <span data-ttu-id="a8d0a-112">В случае выхода из строя одного пула или сайта резервный пул может продолжить предоставлять службу пользователям на обоих узлах.</span><span class="sxs-lookup"><span data-stu-id="a8d0a-112">Then if you have an entire pool or site go down, the backup pool can continue to provide service to users at both sites.</span></span>
  
<span data-ttu-id="a8d0a-113">Скайп для Business Server также поддерживает четыре режима высокой доступности для вашей внутренними серверами: зеркальное отображение базы данных, группы обеспечения доступности AlwaysOn, экземпляры кластера AlwaysOn отработки отказа (FCI) и SQL отказоустойчивого кластера.</span><span class="sxs-lookup"><span data-stu-id="a8d0a-113">Skype for Business Server also supports four modes of high availability for your Back End Servers: database mirroring, AlwaysOn Availability Groups, AlwaysOn Failover Cluster Instances (FCI), and SQL failover clustering.</span></span>
  
> [!NOTE]
> <span data-ttu-id="a8d0a-114">Группы обеспечения доступности AlwaysOn с серверов сохраняемого сеанса беседы не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="a8d0a-114">AlwaysOn Availability Groups are not supported with Persistent Chat Servers.</span></span> 
  
<span data-ttu-id="a8d0a-115">В этом разделе рассматриваются эти функции, а также действия по обеспечению высокого уровня доступности и аварийного восстановления для остальных серверных ролей.</span><span class="sxs-lookup"><span data-stu-id="a8d0a-115">This section explains these features, and also covers what steps you can take for high availability and disaster recovery for some of your other server roles.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="a8d0a-116">См. также</span><span class="sxs-lookup"><span data-stu-id="a8d0a-116">See also</span></span>

#### 

[<span data-ttu-id="a8d0a-117">Высокая доступность сервера переднего плана и управления</span><span class="sxs-lookup"><span data-stu-id="a8d0a-117">Front End Pool high availability and management</span></span>](high-availability.md)
  
[<span data-ttu-id="a8d0a-118">Переднего плана пула аварийного восстановления в Скайп для Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="a8d0a-118">Front End pool disaster recovery in Skype for Business Server 2015</span></span>](disaster-recovery.md)
  
[<span data-ttu-id="a8d0a-119">Взаимодействие с пользователем во время сбоя пула в Скайп для Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="a8d0a-119">User experience during pool failure in Skype for Business Server 2015</span></span>](user-experience.md)
  
[<span data-ttu-id="a8d0a-120">Назад высокой доступности внутреннего сервера в Скайп для Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="a8d0a-120">Back End Server high availability in Skype for Business Server 2015</span></span>](back-end-server.md)
  
[<span data-ttu-id="a8d0a-121">Общий доступ к файлам высокой доступности в Скайп для Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="a8d0a-121">File sharing high availability in Skype for Business Server 2015</span></span>](file-sharing.md)

