---
title: Управление аварийное восстановление, высокая доступность и службы резервного копирования
ms.reviewer: ''
author: lanachin
ms.author: v-lanac
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Описание процедуры по аварийному восстановлению, а также по обслуживанию службы резервного копирования, которая синхронизирует данные в связанных интерфейсных пулах.
ms.openlocfilehash: 9215dba11b388b3ffbd3e5c0f3de4ccf1cb85c7d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "33903132"
---
# <a name="managing-skype-for-business-server-disaster-recovery-high-availability-and-backup-service"></a><span data-ttu-id="7817f-103">Управление Скайп для Business Server аварийное восстановление, высокая доступность и службы резервного копирования</span><span class="sxs-lookup"><span data-stu-id="7817f-103">Managing Skype for Business Server disaster recovery, high availability, and Backup Service</span></span>

<span data-ttu-id="7817f-104">В этом разделе представлены процедуры по аварийному восстановлению, а также по обслуживанию службы резервного копирования, которая синхронизирует данные в связанных интерфейсных пулах.</span><span class="sxs-lookup"><span data-stu-id="7817f-104">This section contains procedures for disaster recovery operations, as well as for maintaining the Backup Service, which synchronizes the data in paired Front End pools.</span></span>

<span data-ttu-id="7817f-105">Процедуры аварийного восстановления, отработки отказа и восстановления размещения, вручную.</span><span class="sxs-lookup"><span data-stu-id="7817f-105">Disaster recovery procedures, both failover and failback, are manual.</span></span> <span data-ttu-id="7817f-106">В случае аварии администратор должен вручную вызова процедуры отработки отказа.</span><span class="sxs-lookup"><span data-stu-id="7817f-106">If there is a disaster, the administrator must manually invoke the failover procedures.</span></span> <span data-ttu-id="7817f-107">То же самое применяется к восстановления размещения после восстановления пула.</span><span class="sxs-lookup"><span data-stu-id="7817f-107">The same applies to failback after the pool is repaired.</span></span>

<span data-ttu-id="7817f-108">Процедуры аварийного восстановления в этом разделе, предполагается следующее:</span><span class="sxs-lookup"><span data-stu-id="7817f-108">The disaster recovery procedures in this section assume the following:</span></span>

  - <span data-ttu-id="7817f-109">У вас есть развертывания с помощью связанных интерфейсных пулах, расположены на разных сайтах, как описано в [Планирование высокой доступности и аварийного восстановления](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).</span><span class="sxs-lookup"><span data-stu-id="7817f-109">You have a deployment with paired Front End pools, located in different sites, as described in [Plan for high availability and disaster recovery](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).</span></span> <span data-ttu-id="7817f-110">На этих парных пулов, чтобы синхронизировать их запуска службы резервного копирования.</span><span class="sxs-lookup"><span data-stu-id="7817f-110">The Backup Service has been running on these paired pools to keep them synchronized.</span></span>

  - <span data-ttu-id="7817f-111">Если центральное хранилище управления размещено на любого из пула, будет установлен и работает на обоих парных пулов, с одним из этих пулов размещения active главных и пула, размещения резервная.</span><span class="sxs-lookup"><span data-stu-id="7817f-111">If the Central Management store is hosted on either pool, it is installed and running on both of the paired pools, with one of those pools hosting the active master and the other pool hosting the standby.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7817f-112">В следующих процедурах параметр *PoolFQDN* ссылается на полное доменное имя пула, которые были затронуты аварии, не пула, в котором влияет на пользователи перенаправляются из.</span><span class="sxs-lookup"><span data-stu-id="7817f-112">In the following procedures, the *PoolFQDN* parameter refers to the FQDN of the pool that is affected by disaster, not the pool that affected users are being redirected from.</span></span> <span data-ttu-id="7817f-113">Для одного набора заинтересованных пользователей она ссылается на тот же самый пул в командлетах отработки отказа и восстановления размещения (то есть пула, в котором сначала, размещенных пользователей перед выполнением отработки отказа).</span><span class="sxs-lookup"><span data-stu-id="7817f-113">For the same set of affected users, it refers to the same pool in both failover and failback cmdlets (that is, the pool that first homed the users before the failover).</span></span><BR><br><span data-ttu-id="7817f-114">Например предположим случая, в котором всех пользователей, размещенных в пуле, P1 были отработка отказа для резервных копий пула P2.</span><span class="sxs-lookup"><span data-stu-id="7817f-114">For example, assume a case in which all users homed on a pool P1 were failed over to the backup pool, P2.</span></span> <span data-ttu-id="7817f-115">Если администратор хочет перемещение всех пользователей, в настоящее время обслуживаемых P2 обслуживаемого P1, администратор должен выполнить следующие действия:</span><span class="sxs-lookup"><span data-stu-id="7817f-115">If the administrator wants to move all the users currently serviced by P2 to be serviced by P1, the administrator must perform the following steps:</span></span> 
> <OL>
> <LI>
> <P><span data-ttu-id="7817f-116">Сбой резервного всех пользователей, размещенных на P1 из P2 для P1 изначально с помощью командлета восстановления размещения.</span><span class="sxs-lookup"><span data-stu-id="7817f-116">Fail back all the users originally homed on P1 from P2 to P1 using the failback cmdlet.</span></span> <span data-ttu-id="7817f-117">В данном случае *PoolFQDN* является P1 его полное доменное имя.</span><span class="sxs-lookup"><span data-stu-id="7817f-117">In this case, the *PoolFQDN* is P1’s FQDN.</span></span></P>
> <LI>
> <P><span data-ttu-id="7817f-118">Отработки отказа всех пользователей, размещенных на P2 для P1 изначально с помощью командлета отработки отказа.</span><span class="sxs-lookup"><span data-stu-id="7817f-118">Fail over all the users originally homed on P2 to P1 using the failover cmdlet.</span></span> <span data-ttu-id="7817f-119">В этом случае в параметре PoolFQDN будет P2 полное доменное имя.</span><span class="sxs-lookup"><span data-stu-id="7817f-119">In this case, the PoolFQDN is P2’s FQDN.</span></span></P>
> <LI>
> <P><span data-ttu-id="7817f-120">Если позднее администратор хочет выполнить восстановление размещения для этих пользователей P2 обратно в P2, то в параметре PoolFQDN будет P2 полное доменное имя.</span><span class="sxs-lookup"><span data-stu-id="7817f-120">If the administrator later wants to fail back those P2 users back to P2, the PoolFQDN is P2’s FQDN.</span></span></P></LI></OL><br><span data-ttu-id="7817f-121">Обратите внимание, что шаг 1 выше должны быть выполнены перед шаг 2, чтобы сохранить целостность пула.</span><span class="sxs-lookup"><span data-stu-id="7817f-121">Note that step 1 above must be performed before step 2 to preserve pool integrity.</span></span> <span data-ttu-id="7817f-122">При попытке шаг 2 до шаг 1, командлет шаг 2 не будет выполнен.</span><span class="sxs-lookup"><span data-stu-id="7817f-122">If you try step 2 before step 1, the step 2 cmdlet will fail.</span></span>


## <a name="see-also"></a><span data-ttu-id="7817f-123">См. также</span><span class="sxs-lookup"><span data-stu-id="7817f-123">See Also</span></span>

[<span data-ttu-id="7817f-124">Планирование высокой доступности и аварийного восстановления</span><span class="sxs-lookup"><span data-stu-id="7817f-124">Plan for high availability and disaster recovery</span></span>](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md) 
  
