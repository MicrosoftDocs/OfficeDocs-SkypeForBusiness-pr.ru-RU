---
title: Планирование высокой доступности и аварийного восстановления в Скайп Business Server
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
f1_keywords:
- ms.lync.plan.HighAvailabilityType
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 3543eb40-54f4-49ef-a058-03aceed4773a
description: Скайп для Business Server предлагает высокой доступности с помощью пула аварийного восстановления с помощью связывания пула и нескольких режимах Тыловой сервер высокой доступности, включая группы обеспечения доступности AlwaysOn, зеркальное отображение базы данных и отказоустойчивый кластер SQL server.
ms.openlocfilehash: 9e48fa65572dea5c0e6a297397d2a502cefcdc36
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "32214063"
---
# <a name="plan-for-high-availability-and-disaster-recovery-in-skype-for-business-server"></a><span data-ttu-id="f1d5d-103">Планирование высокой доступности и аварийного восстановления в Скайп Business Server</span><span class="sxs-lookup"><span data-stu-id="f1d5d-103">Plan for high availability and disaster recovery in Skype for Business Server</span></span>
 
<span data-ttu-id="f1d5d-104">Скайп для Business Server предлагает высокой доступности с помощью пула аварийного восстановления с помощью связывания пула и нескольких режимах Тыловой сервер высокой доступности, включая группы обеспечения доступности AlwaysOn, зеркальное отображение базы данных и отказоустойчивый кластер SQL server.</span><span class="sxs-lookup"><span data-stu-id="f1d5d-104">Skype for Business Server offers high availability with server pooling, disaster recovery with pool pairing, and several modes of Back End Server high availability, including AlwaysOn Availability groups, database mirroring, and SQL failover clustering.</span></span> 
  
<span data-ttu-id="f1d5d-105">Высокая доступность относится к проверке того, что Скайп для служб Business Server доступны даже в том случае, если один или несколько серверов, тем ниже.</span><span class="sxs-lookup"><span data-stu-id="f1d5d-105">High availability refers to making sure that Skype for Business Server services are available even if one or more servers goes down.</span></span> <span data-ttu-id="f1d5d-106">Аварийное восстановление подразумевает поддержание служб в работоспособном состоянии в случае природной или антропогенной катастрофы с сохранением целостности как можно большего объема данных.</span><span class="sxs-lookup"><span data-stu-id="f1d5d-106">Disaster recovery refers to keeping services going in the event of a natural or human-caused disaster, and preserving as much data from before the disaster as possible.</span></span>
  
<span data-ttu-id="f1d5d-107">Как и в предыдущих версиях Lync Server компонент основной высокой доступности для большинства ролей сервера в Скайп для Business Server — избыточности сервера с помощью пула.</span><span class="sxs-lookup"><span data-stu-id="f1d5d-107">As in previous versions of Lync Server, the main high availability feature for most server roles in Skype for Business Server is server redundancy via pooling.</span></span> <span data-ttu-id="f1d5d-108">Если сервер, на котором работает определенная роль, завершает работу со сбоем, другие серверы в пуле, выполняющие ту же самую роль, берут на себя нагрузку первого сервера.</span><span class="sxs-lookup"><span data-stu-id="f1d5d-108">If a server running a certain server role fails, the other servers in the pool running the same role take the load of that server.</span></span> <span data-ttu-id="f1d5d-109">Это применимо к интерфейсным серверам, пограничным серверам, серверам-посредникам и директорам.</span><span class="sxs-lookup"><span data-stu-id="f1d5d-109">This applies to Front End Servers, Edge Servers, Mediation Servers, and Directors.</span></span>
  
<span data-ttu-id="f1d5d-110">Скайп для Business Server также приводятся аварийного восстановления для пулов переднего плана.</span><span class="sxs-lookup"><span data-stu-id="f1d5d-110">Skype for Business Server also provides disaster recovery options for Front End pools.</span></span> <span data-ttu-id="f1d5d-111">Можно установить два пула в разных географических регионах, чтобы каждый из них был резервным для другого.</span><span class="sxs-lookup"><span data-stu-id="f1d5d-111">You can set up two pools in different geographical areas to serve as backups for each other.</span></span> <span data-ttu-id="f1d5d-112">В случае выхода из строя одного пула или сайта резервный пул может продолжить предоставлять службу пользователям на обоих узлах.</span><span class="sxs-lookup"><span data-stu-id="f1d5d-112">Then if you have an entire pool or site go down, the backup pool can continue to provide service to users at both sites.</span></span>
  
<span data-ttu-id="f1d5d-113">Скайп для Business Server также поддерживает четыре режима высокой доступности для вашей внутренними серверами: зеркального отображения, группы обеспечения доступности AlwaysOn, экземпляры кластера AlwaysOn отработки отказа (FCI) и SQL отказоустойчивый кластер SQL.</span><span class="sxs-lookup"><span data-stu-id="f1d5d-113">Skype for Business Server also supports four modes of high availability for your Back End Servers: SQL mirroring, AlwaysOn Availability Groups, AlwaysOn Failover Cluster Instances (FCI), and SQL failover clustering.</span></span>
  
> [!NOTE]
> <span data-ttu-id="f1d5d-114">Зеркальное отображение SQL доступна в Скайп для Business Server 2015, но в Скайп Business Server 2019 больше не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="f1d5d-114">SQL Mirroring is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="f1d5d-115">Методы кластеризации отработки отказа группы обеспечения доступности AlwaysOn, экземпляры кластера AlwaysOn отработки отказа (FCI) и SQL, являются предпочтительными с Скайп для Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="f1d5d-115">The  AlwaysOn Availability Groups, AlwaysOn Failover Cluster Instances (FCI), and SQL failover clustering methods are preferred with Skype for Business Server 2019.</span></span>

> [!NOTE]
> <span data-ttu-id="f1d5d-116">Группы обеспечения доступности AlwaysOn с серверов сохраняемого сеанса беседы не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="f1d5d-116">AlwaysOn Availability Groups are not supported with Persistent Chat Servers.</span></span> 
  
<span data-ttu-id="f1d5d-117">В этом разделе рассматриваются эти функции, а также действия по обеспечению высокого уровня доступности и аварийного восстановления для остальных серверных ролей.</span><span class="sxs-lookup"><span data-stu-id="f1d5d-117">This section explains these features, and also covers what steps you can take for high availability and disaster recovery for some of your other server roles.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="f1d5d-118">См. также</span><span class="sxs-lookup"><span data-stu-id="f1d5d-118">See also</span></span>

[<span data-ttu-id="f1d5d-119">Высокая доступность и управление пулом переднего плана</span><span class="sxs-lookup"><span data-stu-id="f1d5d-119">Front End Pool high availability and management</span></span>](high-availability.md)
  
[<span data-ttu-id="f1d5d-120">Переднего плана пула аварийного восстановления в Скайп для Business Server</span><span class="sxs-lookup"><span data-stu-id="f1d5d-120">Front End pool disaster recovery in Skype for Business Server</span></span>](disaster-recovery.md)
  
[<span data-ttu-id="f1d5d-121">Взаимодействие с пользователем во время сбоя пула в Скайп для Business Server</span><span class="sxs-lookup"><span data-stu-id="f1d5d-121">User experience during pool failure in Skype for Business Server</span></span>](user-experience.md)
  
[<span data-ttu-id="f1d5d-122">Назад высокой доступности внутреннего сервера в Скайп для Business Server</span><span class="sxs-lookup"><span data-stu-id="f1d5d-122">Back End Server high availability in Skype for Business Server</span></span>](back-end-server.md)
  
[<span data-ttu-id="f1d5d-123">Общий доступ к файлам высокой доступности в Скайп для Business Server</span><span class="sxs-lookup"><span data-stu-id="f1d5d-123">File sharing high availability in Skype for Business Server</span></span>](file-sharing.md)
