---
title: Время восстановления Lync Server 2013 для отработки отказа пула и восстановления размещения в пуле
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Recovery time for pool failover and pool failback
ms:assetid: 902c658f-8442-4d0d-b3ad-bf795ecd550d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205079(v=OCS.15)
ms:contentKeyID: 48184786
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fb165fa762b23bd271dde56c0846ccb18adfbf7f
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42183252"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="recovery-time-for-pool-failover-and-pool-failback-in-lync-server-2013"></a><span data-ttu-id="37bfc-102">Время восстановления для отработки отказа пула и восстановления размещения пула в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="37bfc-102">Recovery time for pool failover and pool failback in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="37bfc-103">_**Последнее изменение темы:** 2012-09-10_</span><span class="sxs-lookup"><span data-stu-id="37bfc-103">_**Topic Last Modified:** 2012-09-10_</span></span>

<span data-ttu-id="37bfc-p101">Для отработки отказа и восстановления размещения пула целевым временем восстановления (RTO) является 30 минут. Это время, необходимое для отработки отказа, после того, как администраторы определили наличие аварии и инициировали процедуру отработки отказа. Оно не учитывает время, необходимое администраторам для оценки ситуации и принятия решения, а также не учитывает время, необходимое пользователям для повторного входа после завершения отработки отказа.</span><span class="sxs-lookup"><span data-stu-id="37bfc-p101">For pool failover and pool failback, the engineering target for recovery time objective (RTO) is 30 minutes. This is the time required for the failover to happen, after administrators have determined there was a disaster and initiated the failover procedures. It does not include the time for administrators to assess the situation and make a decision, nor does it include the time for users to sign in again after failover is complete.</span></span>

<span data-ttu-id="37bfc-107">Для отработки отказа и восстановления размещения пула целевым значением точки восстановления (RPO) является 30 минут.</span><span class="sxs-lookup"><span data-stu-id="37bfc-107">For pool failover and pool failback, the engineering target for recovery point objective (RPO) is 30 minutes.</span></span> <span data-ttu-id="37bfc-108">Оно представляет временную меру данных, которые могут быть потеряны вследствие аварии из-за задержки репликации службы резервного копирования.</span><span class="sxs-lookup"><span data-stu-id="37bfc-108">This represents the time measure of data that could be lost due to the disaster, due to replication latency of the Backup Service.</span></span> <span data-ttu-id="37bfc-109">Например, если пул переключается на 10:00 утра, а RPO составляет 30 минут, данные, записанные в пул между 9:30 утра</span><span class="sxs-lookup"><span data-stu-id="37bfc-109">For example, if a pool goes down at 10:00 A.M., and the RPO is 30 minutes, data written to the pool between 9:30 A.M.</span></span> <span data-ttu-id="37bfc-110">и 10:00 A. M, возможно, не реплицированы в резервный пул и будут потеряны.</span><span class="sxs-lookup"><span data-stu-id="37bfc-110">and 10:00 A.M.might not have replicated to the backup pool, and would be lost.</span></span>

<span data-ttu-id="37bfc-111">Все значения RTO и RPO в этом документе предполагают, что два центра обработки данных размещены в одном мировом регионе с высокоскоростным транспортом без задержек между двумя узлами.</span><span class="sxs-lookup"><span data-stu-id="37bfc-111">All RTO and RPO numbers in this document assume that the two data centers are located within the same world region with high-speed, low-latency transport between the two sites.</span></span> <span data-ttu-id="37bfc-112">Эти числа измерялись для пула с 40 000 параллельно активных пользователей и 200 000, поддерживающих Lync, с учетом предопределенной модели пользователей, в которой отсутствует невыполненная работа в процессе репликации данных.</span><span class="sxs-lookup"><span data-stu-id="37bfc-112">These numbers are measured for a pool with 40,000 concurrently active users and 200,000 users enabled for Lync with respect to a pre-defined user model where there is no backlog in data replication.</span></span> <span data-ttu-id="37bfc-113">Они могут изменяться после тестирования производительности и проверки.</span><span class="sxs-lookup"><span data-stu-id="37bfc-113">They are subject to change based on performance testing and validation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

