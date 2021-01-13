---
title: Развертывание функций высокой доступности и аварийного восстановления
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 21007bad-62ce-4553-98e0-02aaa1345781
description: Skype для бизнеса Server обеспечивает высокую доступность с помощью пула серверов, аварийного восстановления с сопряжением пулов и нескольких режимов высокой доступности тыловой части сервера, включая группы доступности AlwaysOn, зеркальное зеркальное отражение баз данных и SQL отключаемую кластерию.
ms.openlocfilehash: 68baae183ff45571e38e922035d287e733bcc930
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830619"
---
# <a name="deploy-high-availability-and-disaster-recovery"></a><span data-ttu-id="9c317-103">Развертывание функций высокой доступности и аварийного восстановления</span><span class="sxs-lookup"><span data-stu-id="9c317-103">Deploy high availability and disaster recovery</span></span>
 
<span data-ttu-id="9c317-104">Skype для бизнеса Server обеспечивает высокую доступность с помощью пула серверов, аварийного восстановления с сопряжением пулов и нескольких режимов высокой доступности тыловой части сервера, включая группы доступности AlwaysOn, зеркальное зеркальное отражение баз данных и SQL отключаемую кластерию.</span><span class="sxs-lookup"><span data-stu-id="9c317-104">Skype for Business Server offers high availability with server pooling, disaster recovery with pool pairing, and several modes of Back End Server high availability, including AlwaysOn Availability groups, database mirroring, and SQL failover clustering.</span></span> 
  
<span data-ttu-id="9c317-105">Высокий уровень доступности означает, что службы Skype для бизнеса Server доступны, даже если один или несколько серверов не будут доступны. Аварийное восстановление означает, что службы будут поддерживаться в случае естественной или вызванной человеком аварии и сохранять как можно больше данных до аварии.</span><span class="sxs-lookup"><span data-stu-id="9c317-105">High availability refers to making sure that Skype for Business Server services are available even if one or more servers goes down.Disaster recovery refers to keeping services going in the event of a natural or human-caused disaster, and preserving as much data from before the disaster as possible.</span></span>
  
<span data-ttu-id="9c317-106">В этом разделе рассказывается, как развернуть эти функции, а также описывается, какие действия можно предпринять для высокой доступности и аварийного восстановления для некоторых других ролей сервера.</span><span class="sxs-lookup"><span data-stu-id="9c317-106">This section tells how to deploy these features, and also covers what steps you can take for high availability and disaster recovery for some of your other server roles.</span></span>

> [!NOTE]
> <span data-ttu-id="9c317-107">SQL зеркальное отражение доступно в Skype для бизнеса Server 2015, но больше не поддерживается в Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="9c317-107">SQL Mirroring is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="9c317-108">В Skype для бизнеса Server 2019 предпочтительнее использовать группы доступности AlwaysOn, экземпляры кластера для отстройки AlwaysOn и SQL кластеров.</span><span class="sxs-lookup"><span data-stu-id="9c317-108">The  AlwaysOn Availability Groups, AlwaysOn Failover Cluster Instances (FCI), and SQL failover clustering methods are preferred with Skype for Business Server 2019.</span></span>
  
## <a name="related-sections"></a><span data-ttu-id="9c317-109">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="9c317-109">Related sections</span></span>

[<span data-ttu-id="9c317-110">Планирование высокой доступности и аварийного восстановления в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="9c317-110">Plan for high availability and disaster recovery in Skype for Business Server</span></span>](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)
  
## <a name="see-also"></a><span data-ttu-id="9c317-111">См. также</span><span class="sxs-lookup"><span data-stu-id="9c317-111">See also</span></span>

[<span data-ttu-id="9c317-112">Развертывание группы доступности AlwaysOn на тыловом сервере в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="9c317-112">Deploy an AlwaysOn Availability Group on a Back End Server in Skype for Business Server</span></span>](alwayson-availability-group.md)

[<span data-ttu-id="9c317-113">Развертывание сопряженных пулов переднего сервера для аварийного восстановления в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="9c317-113">Deploy paired Front End pools for disaster recovery in Skype for Business Server</span></span>](front-end-pools-for-disaster-recovery.md)
  
[<span data-ttu-id="9c317-114">Развертывание SQL зеркального отражания для высокой доступности серверов в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="9c317-114">Deploy SQL mirroring for Back End Server high availability in Skype for Business Server 2015</span></span>](sql-mirroring-for-high-availability.md)
  
