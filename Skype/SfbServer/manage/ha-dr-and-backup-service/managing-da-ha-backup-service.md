---
title: Управление службой аварийного восстановления, высокой доступности и резервного копирования
ms.reviewer: ''
author: cichur
ms.author: v-cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Узнайте о процедурах для операций аварийного восстановления, а также о обслуживании службы резервного копирования, которая синхронизирует данные в сопряженных пулах переднего плану.
ms.openlocfilehash: e486a71203b64b4fc351888869ac64a24689ba7b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817159"
---
# <a name="managing-skype-for-business-server-disaster-recovery-high-availability-and-backup-service"></a><span data-ttu-id="af786-103">Управление службой аварийного восстановления, высокой доступности и резервного копирования Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="af786-103">Managing Skype for Business Server disaster recovery, high availability, and Backup Service</span></span>

<span data-ttu-id="af786-104">В этом разделе содержатся процедуры для операций аварийного восстановления, а также для обслуживания службы резервного копирования, которая синхронизирует данные в сопряженных пулах переднего план.</span><span class="sxs-lookup"><span data-stu-id="af786-104">This section contains procedures for disaster recovery operations, as well as for maintaining the Backup Service, which synchronizes the data in paired Front End pools.</span></span>

<span data-ttu-id="af786-p101">Процедуры аварийного восстановления, как отработка отказа, так и восстановление размещения, выполняются вручную. Если произошла авария, администратор должен вручную выполнять процедуры отработки отказа. То же самое относится и к восстановлению размещения после восстановления пула.</span><span class="sxs-lookup"><span data-stu-id="af786-p101">Disaster recovery procedures, both failover and failback, are manual. If there is a disaster, the administrator must manually invoke the failover procedures. The same applies to failback after the pool is repaired.</span></span>

<span data-ttu-id="af786-108">В процедурах аварийного восстановления в этом разделе предполагается следующее:</span><span class="sxs-lookup"><span data-stu-id="af786-108">The disaster recovery procedures in this section assume the following:</span></span>

  - <span data-ttu-id="af786-109">У вас есть развертывание с сопряженными пулами переднего плана, расположенными на разных сайтах, как описано в плане высокой доступности и [аварийного восстановления.](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)</span><span class="sxs-lookup"><span data-stu-id="af786-109">You have a deployment with paired Front End pools, located in different sites, as described in [Plan for high availability and disaster recovery](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).</span></span> <span data-ttu-id="af786-110">Служба резервного копирования работает в этих сопряженных пулах для поддержания их синхронизации.</span><span class="sxs-lookup"><span data-stu-id="af786-110">The Backup Service has been running on these paired pools to keep them synchronized.</span></span>

  - <span data-ttu-id="af786-111">Если центральное хранилище управления размещено в обоих пулах, оно устанавливается и работает в обоих сопряженных пулах, в одном из этих пулов размещен активный хозяин, а в другом — в резервном.</span><span class="sxs-lookup"><span data-stu-id="af786-111">If the Central Management store is hosted on either pool, it is installed and running on both of the paired pools, with one of those pools hosting the active master and the other pool hosting the standby.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="af786-p103">В последующих процедурах параметр *PoolFQDN* указывает на полное доменное имя пула, затронутого аварией, а не того пула, с которого перенаправляются затронутые пользователи. Для одного набора затронутых пользователей он указывает на один и тот же пул в командлетах отработки отказа и восстановления размещения (то есть на пул, который первым принял пользователей перед отработкой отказа).</span><span class="sxs-lookup"><span data-stu-id="af786-p103">In the following procedures, the *PoolFQDN* parameter refers to the FQDN of the pool that is affected by disaster, not the pool that affected users are being redirected from. For the same set of affected users, it refers to the same pool in both failover and failback cmdlets (that is, the pool that first homed the users before the failover).</span></span><BR><br><span data-ttu-id="af786-p104">Например, представьте себе ситуацию, когда для всех пользователей, размещенных в пуле P1, была выполнена отработка отказа в резервный пул P2. Если администратор хочет переместить всех пользователей, в данный момент обслуживаемых пулом P2, в пул P1, ему следует выполнить следующие действия:</span><span class="sxs-lookup"><span data-stu-id="af786-p104">For example, assume a case in which all users homed on a pool P1 were failed over to the backup pool, P2. If the administrator wants to move all the users currently serviced by P2 to be serviced by P1, the administrator must perform the following steps:</span></span> 
> <OL>
> <LI>
> <P><span data-ttu-id="af786-p105">Выполнить восстановление размещения для всех пользователей, изначально размещенных в пуле P1, из пула P2 в пул P1 с помощью соответствующего командлета. В этом случае параметр *PoolFQDN* обозначает полное доменное имя пула P1.</span><span class="sxs-lookup"><span data-stu-id="af786-p105">Fail back all the users originally homed on P1 from P2 to P1 using the failback cmdlet. In this case, the *PoolFQDN* is P1’s FQDN.</span></span></P>
> <LI>
> <P><span data-ttu-id="af786-118">Выполнить отработку отказа для всех пользователей, изначально размещенных в пуле P2, в пул P1 с помощью соответствующего командлета.</span><span class="sxs-lookup"><span data-stu-id="af786-118">Fail over all the users originally homed on P2 to P1 using the failover cmdlet.</span></span> <span data-ttu-id="af786-119">В этом случае параметр PoolFQDN обозначает полное доменное имя пула P2.</span><span class="sxs-lookup"><span data-stu-id="af786-119">In this case, the PoolFQDN is P2’s FQDN.</span></span></P>
> <LI>
> <P><span data-ttu-id="af786-120">Если позднее администратор хочет выполнить восстановление размещения для этих пользователей P2 обратно в пул P2, параметр PoolFQDN обозначает полное доменное имя пула P2.</span><span class="sxs-lookup"><span data-stu-id="af786-120">If the administrator later wants to fail back those P2 users back to P2, the PoolFQDN is P2’s FQDN.</span></span></P></LI></OL><br><span data-ttu-id="af786-p107">Обратите внимание на то, что описанное выше действие 1 следует выполнять перед действием 2 для сохранения целостности пула. Если попытаться выполнить действие 2 перед действием 2, произойдет сбой командлета.</span><span class="sxs-lookup"><span data-stu-id="af786-p107">Note that step 1 above must be performed before step 2 to preserve pool integrity. If you try step 2 before step 1, the step 2 cmdlet will fail.</span></span>


## <a name="see-also"></a><span data-ttu-id="af786-123">См. также</span><span class="sxs-lookup"><span data-stu-id="af786-123">See Also</span></span>

[<span data-ttu-id="af786-124">Планирование высокой доступности и аварийного восстановления</span><span class="sxs-lookup"><span data-stu-id="af786-124">Plan for high availability and disaster recovery</span></span>](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md) 
  
