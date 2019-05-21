---
title: Управление аварийным восстановлением, высокой доступностью и службой резервного копирования
ms.reviewer: ''
author: lanachin
ms.author: v-lanac
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Сведения о возможностях аварийного восстановления, а также о том, как поддерживать службу резервного копирования, которая синхронизирует данные в подключенных интерфейсных пулах.
ms.openlocfilehash: 9664a7d9d48ca084232e2a0473a15d29d970cea6
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34303900"
---
# <a name="managing-skype-for-business-server-disaster-recovery-high-availability-and-backup-service"></a><span data-ttu-id="3249c-103">Управление аварийным восстановлением в Skype для бизнеса Server, высокой доступностью и службой резервного копирования</span><span class="sxs-lookup"><span data-stu-id="3249c-103">Managing Skype for Business Server disaster recovery, high availability, and Backup Service</span></span>

<span data-ttu-id="3249c-104">В этом разделе содержатся процедуры для операций аварийного восстановления, а также обслуживания службы резервного копирования, которое синхронизирует данные в подключенных внешних пулах.</span><span class="sxs-lookup"><span data-stu-id="3249c-104">This section contains procedures for disaster recovery operations, as well as for maintaining the Backup Service, which synchronizes the data in paired Front End pools.</span></span>

<span data-ttu-id="3249c-105">Процедуры аварийного восстановления, как в случае сбоя, так и для перемещения после сбоя, выполняются вручную.</span><span class="sxs-lookup"><span data-stu-id="3249c-105">Disaster recovery procedures, both failover and failback, are manual.</span></span> <span data-ttu-id="3249c-106">При возникновении аварии администратор должен вручную вызвать процедуры перемещения.</span><span class="sxs-lookup"><span data-stu-id="3249c-106">If there is a disaster, the administrator must manually invoke the failover procedures.</span></span> <span data-ttu-id="3249c-107">Это применимо к восстановлению после восстановления пула.</span><span class="sxs-lookup"><span data-stu-id="3249c-107">The same applies to failback after the pool is repaired.</span></span>

<span data-ttu-id="3249c-108">Процедуры аварийного восстановления, описанные в этом разделе, предполагают следующее:</span><span class="sxs-lookup"><span data-stu-id="3249c-108">The disaster recovery procedures in this section assume the following:</span></span>

  - <span data-ttu-id="3249c-109">У вас есть развертывание с подключенными пулами переднего плана, расположенными на разных сайтах, как описано в разделе [Планирование высокого уровня доступности и аварийного восстановления](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).</span><span class="sxs-lookup"><span data-stu-id="3249c-109">You have a deployment with paired Front End pools, located in different sites, as described in [Plan for high availability and disaster recovery](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).</span></span> <span data-ttu-id="3249c-110">Служба архивации запущена на этих подключенных пулах, чтобы синхронизировать их.</span><span class="sxs-lookup"><span data-stu-id="3249c-110">The Backup Service has been running on these paired pools to keep them synchronized.</span></span>

  - <span data-ttu-id="3249c-111">Если хранилище Центрального управления размещено на любом из пулов, оно установлено и запущено на обоих из них, с одним из них, где размещается активный хозяин, и другой пул, на котором размещается резерв.</span><span class="sxs-lookup"><span data-stu-id="3249c-111">If the Central Management store is hosted on either pool, it is installed and running on both of the paired pools, with one of those pools hosting the active master and the other pool hosting the standby.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3249c-112">В описанных ниже процедурах параметр *пулфкдн* указывает на полное доменное имя пула, на которое влияет авария, а не тот, на который перенаправлены пользователи, а не в пул.</span><span class="sxs-lookup"><span data-stu-id="3249c-112">In the following procedures, the *PoolFQDN* parameter refers to the FQDN of the pool that is affected by disaster, not the pool that affected users are being redirected from.</span></span> <span data-ttu-id="3249c-113">Для одного и того же набора затронутых пользователей он ссылается на один и тот же пул командлетов перемещения при сбое и восстановления размещения (то есть, пул, который сначала размещает пользователей перед переходом на другой ресурс).</span><span class="sxs-lookup"><span data-stu-id="3249c-113">For the same set of affected users, it refers to the same pool in both failover and failback cmdlets (that is, the pool that first homed the users before the failover).</span></span><BR><br><span data-ttu-id="3249c-114">Например, предположим, что для всех пользователей, использующих пул P1, не удалось выполнить резервное копирование в распределенный пул P2.</span><span class="sxs-lookup"><span data-stu-id="3249c-114">For example, assume a case in which all users homed on a pool P1 were failed over to the backup pool, P2.</span></span> <span data-ttu-id="3249c-115">Если администратор хочет переместить всех пользователей, обслуживаемых в P2, для обслуживания с помощью P1, администратор должен выполнить указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="3249c-115">If the administrator wants to move all the users currently serviced by P2 to be serviced by P1, the administrator must perform the following steps:</span></span> 
> <OL>
> <LI>
> <P><span data-ttu-id="3249c-116">Не удается вернуть все пользователи, изначально размещенные в P1, из P2 в P1 с помощью командлета восстановления размещения.</span><span class="sxs-lookup"><span data-stu-id="3249c-116">Fail back all the users originally homed on P1 from P2 to P1 using the failback cmdlet.</span></span> <span data-ttu-id="3249c-117">В этом случае *пулфкдн* — P1's FQDN.</span><span class="sxs-lookup"><span data-stu-id="3249c-117">In this case, the *PoolFQDN* is P1’s FQDN.</span></span></P>
> <LI>
> <P><span data-ttu-id="3249c-118">Отработка отказа всех пользователей, первоначально подключенных к P2, с помощью командлета failover.</span><span class="sxs-lookup"><span data-stu-id="3249c-118">Fail over all the users originally homed on P2 to P1 using the failover cmdlet.</span></span> <span data-ttu-id="3249c-119">В этом случае Пулфкдн — P2's FQDN.</span><span class="sxs-lookup"><span data-stu-id="3249c-119">In this case, the PoolFQDN is P2’s FQDN.</span></span></P>
> <LI>
> <P><span data-ttu-id="3249c-120">Если в дальнейшем администратор хочет вернуть пользователей P2 в P2, Пулфкдн — P2's FQDN.</span><span class="sxs-lookup"><span data-stu-id="3249c-120">If the administrator later wants to fail back those P2 users back to P2, the PoolFQDN is P2’s FQDN.</span></span></P></LI></OL><br><span data-ttu-id="3249c-121">Обратите внимание, что шаг 1 описанный выше должен выполняться перед шагом 2, чтобы сохранить целостность пула.</span><span class="sxs-lookup"><span data-stu-id="3249c-121">Note that step 1 above must be performed before step 2 to preserve pool integrity.</span></span> <span data-ttu-id="3249c-122">Если вы попытаетесь выполнить действие 2 перед шагом 1, командлет Step 2 завершится сбоем.</span><span class="sxs-lookup"><span data-stu-id="3249c-122">If you try step 2 before step 1, the step 2 cmdlet will fail.</span></span>


## <a name="see-also"></a><span data-ttu-id="3249c-123">См. также</span><span class="sxs-lookup"><span data-stu-id="3249c-123">See Also</span></span>

[<span data-ttu-id="3249c-124">Планирование высокой доступности и аварийного восстановления</span><span class="sxs-lookup"><span data-stu-id="3249c-124">Plan for high availability and disaster recovery</span></span>](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md) 
  
