---
title: 'Lync Server 2013: планирование сопоставления для пула переднего плана'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for Front End pool pairing
ms:assetid: cca5773d-57ff-45ce-a7b4-f82ae697c477
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205293(v=OCS.15)
ms:contentKeyID: 48185508
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d85f6e19f3aa74c09a522e737d1223095f17d7c1
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41725399"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-front-end-pool-pairing-in-lync-server-2013"></a><span data-ttu-id="19de4-102">Планирование сопоставления для пула переднего плана в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="19de4-102">Planning for Front End pool pairing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="19de4-103">_**Тема последнего изменения:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="19de4-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="19de4-104">Для обеспечения наилучшей возможной аварии в Lync Server 2013 разверните пары пулов переднего плана на двух географически распределенных сайтах.</span><span class="sxs-lookup"><span data-stu-id="19de4-104">For the best disaster recovery abilities in Lync Server 2013, deploy pairs of Front End pools across two geographically dispersed sites.</span></span> <span data-ttu-id="19de4-105">Каждый сайт содержит пул переднего плана, связанный с соответствующим пулом переднего плана на другом сайте.</span><span class="sxs-lookup"><span data-stu-id="19de4-105">Each site contains a Front End pool which is paired with a corresponding Front End pool in the other site.</span></span> <span data-ttu-id="19de4-106">Оба сайта активны, и служба резервного копирования в Lync Server обеспечивает репликацию данных в режиме реального времени, чтобы синхронизировать их с пулами.</span><span class="sxs-lookup"><span data-stu-id="19de4-106">Both sites are active, and the Lync Server Backup Service provides real-time data replication to keep the pools synchronized.</span></span> <span data-ttu-id="19de4-107">Служба резервного копирования — это новая функция в Lync Server 2013, разработанная для поддержки решения аварийного восстановления.</span><span class="sxs-lookup"><span data-stu-id="19de4-107">The Backup Service is a new feature in Lync Server 2013, designed to support the disaster recovery solution.</span></span> <span data-ttu-id="19de4-108">Он устанавливается на пул переднего плана при связывании пула с другим пулом переднего плана.</span><span class="sxs-lookup"><span data-stu-id="19de4-108">It is installed on a Front End pool when you pair the pool with another Front End pool.</span></span>

<span data-ttu-id="19de4-109">Если пул на одном из сайтов завершается сбоем, вы можете перенести пользователей из этого пула в пул на другом сайте, который предоставляет доступ к службам для всех пользователей в обоих пулах.</span><span class="sxs-lookup"><span data-stu-id="19de4-109">If the pool in one site fails, you can fail over the users from that pool to the pool in the other site, which then provides services to all the users in both pools.</span></span> <span data-ttu-id="19de4-110">Для планирования производственных мощностей каждый пул должен быть спроектирован таким образом, чтобы обрабатывались рабочие нагрузки всех пользователей в обоих пулах в случае аварии.</span><span class="sxs-lookup"><span data-stu-id="19de4-110">For capacity planning purposes, each pool should be designed to handle the workloads of all users in both pools in the event of a disaster.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="19de4-111">Содержание</span><span class="sxs-lookup"><span data-stu-id="19de4-111">In This Section</span></span>

  - [<span data-ttu-id="19de4-112">Поддерживаемые варианты связывания пулов и рекомендации для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="19de4-112">Supported pool pairing options and best practices for Lync Server 2013</span></span>](lync-server-2013-supported-pool-pairing-options-and-best-practices.md)

  - [<span data-ttu-id="19de4-113">Связи с регистраторами резервного копирования в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="19de4-113">Backup Registrar relationships in Lync Server 2013</span></span>](lync-server-2013-backup-registrar-relationships.md)

  - [<span data-ttu-id="19de4-114">Время восстановления при отработке отказа пулом и восстановления пула после сбоя в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="19de4-114">Recovery time for pool failover and pool failback in Lync Server 2013</span></span>](lync-server-2013-recovery-time-for-pool-failover-and-pool-failback.md)

  - [<span data-ttu-id="19de4-115">Отработка отказа центральным хранилищем управления в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="19de4-115">Central Management store failover in Lync Server 2013</span></span>](lync-server-2013-central-management-store-failover.md)

  - [<span data-ttu-id="19de4-116">Безопасность спаренных данных пула переднего плана в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="19de4-116">Front End pool pairing data security in Lync Server 2013</span></span>](lync-server-2013-front-end-pool-pairing-data-security.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

