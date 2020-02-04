---
title: 'Lync Server 2013: время восстановления при отработке отказа пулом и восстановления пула после сбоя'
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
ms.openlocfilehash: 3fff6f74b5d486c05d01bcd3a911ae674b4f0708
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724458"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="recovery-time-for-pool-failover-and-pool-failback-in-lync-server-2013"></a><span data-ttu-id="1da47-102">Время восстановления при отработке отказа пулом и восстановления пула после сбоя в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1da47-102">Recovery time for pool failover and pool failback in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1da47-103">_**Тема последнего изменения:** 2012-09-10_</span><span class="sxs-lookup"><span data-stu-id="1da47-103">_**Topic Last Modified:** 2012-09-10_</span></span>

<span data-ttu-id="1da47-104">Для цели обслуживания отказов в пуле и восстановления размещения в пуле необходимо 30 минут, так как Целевая цель проектирования для времени восстановления (RTO).</span><span class="sxs-lookup"><span data-stu-id="1da47-104">For pool failover and pool failback, the engineering target for recovery time objective (RTO) is 30 minutes.</span></span> <span data-ttu-id="1da47-105">Это время, необходимое для выполнения отработки отказа, после того как администраторы определили аварии и инициировали процедуры перехода на другой ресурс.</span><span class="sxs-lookup"><span data-stu-id="1da47-105">This is the time required for the failover to happen, after administrators have determined there was a disaster and initiated the failover procedures.</span></span> <span data-ttu-id="1da47-106">Этот срок не включает в себя время, необходимое администраторам для оценки ситуации и принятия решения, а также не включает в себя время, необходимое пользователям для повторного входа после завершения отработки отказа.</span><span class="sxs-lookup"><span data-stu-id="1da47-106">It does not include the time for administrators to assess the situation and make a decision, nor does it include the time for users to sign in again after failover is complete.</span></span>

<span data-ttu-id="1da47-107">В случае отработки отказа пула и восстановления из пула, Целевая цель разработки для цели точки восстановления (RPO) составляет 30 минут.</span><span class="sxs-lookup"><span data-stu-id="1da47-107">For pool failover and pool failback, the engineering target for recovery point objective (RPO) is 30 minutes.</span></span> <span data-ttu-id="1da47-108">Она представляет временную меру данных, которые могут быть потеряны вследствие аварии в связи с задержкой репликации данных службы резервного копирования.</span><span class="sxs-lookup"><span data-stu-id="1da47-108">This represents the time measure of data that could be lost due to the disaster, due to replication latency of the Backup Service.</span></span> <span data-ttu-id="1da47-109">Например, если пул переходит на 10:00 утра, а RPO составляет 30 минут, данные из него записываются в пул между 9:30 утра.</span><span class="sxs-lookup"><span data-stu-id="1da47-109">For example, if a pool goes down at 10:00 A.M., and the RPO is 30 minutes, data written to the pool between 9:30 A.M.</span></span> <span data-ttu-id="1da47-110">и 10:00 A. м. возможно, она не была реплицирована в пул резервных копий и будет потеряна.</span><span class="sxs-lookup"><span data-stu-id="1da47-110">and 10:00 A.M.might not have replicated to the backup pool, and would be lost.</span></span>

<span data-ttu-id="1da47-111">В настоящем документе для всех значений RTO и RPO предполагается, что два центра обработки данных размещены в одном мировом регионе с высокоскоростным транспортом без задержек между двумя узлами.</span><span class="sxs-lookup"><span data-stu-id="1da47-111">All RTO and RPO numbers in this document assume that the two data centers are located within the same world region with high-speed, low-latency transport between the two sites.</span></span> <span data-ttu-id="1da47-112">Эти значения измеряются для пула с 40 000 одновременно активных пользователей и 200 000 пользователей, активированных для применения Lync в соответствии с предварительно заданной моделью пользователей, в которой при репликации данных нет невыполненных операций.</span><span class="sxs-lookup"><span data-stu-id="1da47-112">These numbers are measured for a pool with 40,000 concurrently active users and 200,000 users enabled for Lync with respect to a pre-defined user model where there is no backlog in data replication.</span></span> <span data-ttu-id="1da47-113">Они могут изменяться после тестирования производительности и проверки.</span><span class="sxs-lookup"><span data-stu-id="1da47-113">They are subject to change based on performance testing and validation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

