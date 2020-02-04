---
title: 'Lync Server 2013: резервное копирование и восстановление сервера Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Backing up and restoring Lync Server 2013
ms:assetid: 07dc1f5e-af66-4e18-bf39-881dceff8bc3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202160(v=OCS.15)
ms:contentKeyID: 51541443
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 43a96f47bfe9d28fdbc37eea0ae62ef6cd763098
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740149"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="backing-up-and-restoring-lync-server-2013"></a><span data-ttu-id="d25a0-102">Резервное копирование и восстановление Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d25a0-102">Backing up and restoring Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d25a0-103">_**Тема последнего изменения:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="d25a0-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="d25a0-104">В этом разделе вы найдете рекомендации по резервному созданию данных Lync Server 2013 и их восстановления в случае сбоя.</span><span class="sxs-lookup"><span data-stu-id="d25a0-104">In this section, you’ll find the best practices for backing up your Lync Server 2013 data, and for restoring it if you have a failure.</span></span> <span data-ttu-id="d25a0-105">Эти рекомендации относятся к следующим ситуациям:</span><span class="sxs-lookup"><span data-stu-id="d25a0-105">These best practices apply to the following situations:</span></span>

  - <span data-ttu-id="d25a0-106">Весь пул серверов Lync Server любого типа (сервер переднего плана, пограничный сервер, сервер-посредник, сервер, на котором сохранен чат или режиссер) или отдельный сервер в одном из этих пулов.</span><span class="sxs-lookup"><span data-stu-id="d25a0-106">An entire Lync Server pool of any type (Front End Server, Edge Server, Mediation Server, Persistent Chat Server, or Director), or an individual server in one of these pools.</span></span>

  - <span data-ttu-id="d25a0-107">Центральный сервер управления</span><span class="sxs-lookup"><span data-stu-id="d25a0-107">The Central Management Server</span></span>

  - <span data-ttu-id="d25a0-108">Сервер стандартных выпусков</span><span class="sxs-lookup"><span data-stu-id="d25a0-108">A Standard Edition server</span></span>

  - <span data-ttu-id="d25a0-109">Сервер заднего выпуска Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="d25a0-109">An Enterprise Edition Back End Server</span></span>

  - <span data-ttu-id="d25a0-110">Хранилище файлов</span><span class="sxs-lookup"><span data-stu-id="d25a0-110">A File Store</span></span>

  - <span data-ttu-id="d25a0-111">База данных для архивации, база данных мониторинга или сохраняемая база данных чата</span><span class="sxs-lookup"><span data-stu-id="d25a0-111">An Archiving database, Monitoring database, or Persistent Chat database</span></span>

<span data-ttu-id="d25a0-112">Этот раздел не содержит сведений о восстановлении сайта целиком или для разработки резервного сайта.</span><span class="sxs-lookup"><span data-stu-id="d25a0-112">This section does not include information about restoring an entire site or for developing a standby site.</span></span> <span data-ttu-id="d25a0-113">Сведения о разработке решения аварийного восстановления с подключенными внешними пулами можно найти [в разделе Планирование обеспечения высокой доступности и аварийного восстановления в Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span><span class="sxs-lookup"><span data-stu-id="d25a0-113">For details about developing a disaster recovery solution with paired Front End pools, see [Planning for high availability and disaster recovery in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span></span> <span data-ttu-id="d25a0-114">Это рекомендуемый способ планирования аварийного восстановления.</span><span class="sxs-lookup"><span data-stu-id="d25a0-114">This is the recommended method for planning for disaster recovery.</span></span>

<span data-ttu-id="d25a0-115">Если вы развернули Объединенные пулы интерфейсных элементов, то если один из этих пулов завершается сбоем и становится невосстанавливаемым, вы можете восстановить его с помощью нового полного доменного имени (FQDN) из его парного пула.</span><span class="sxs-lookup"><span data-stu-id="d25a0-115">If you have deployed paired Front End pools, if one of these pools fails and becomes unrecoverable, you can restore this pool with a new fully qualified domain name (FQDN) from its paired pool.</span></span> <span data-ttu-id="d25a0-116">Подробнее о том, как выполнить это восстановление, можно найти [в статье отказ пула в Lync Server 2013](lync-server-2013-failing-over-a-pool.md).</span><span class="sxs-lookup"><span data-stu-id="d25a0-116">For details on the steps to perform this recovery, see [Failing over a pool in Lync Server 2013](lync-server-2013-failing-over-a-pool.md).</span></span> <span data-ttu-id="d25a0-117">Кроме того, если позже вам потребуется повторно создать Невосстановленный пул, который являлся частью пары интерфейсов, вы можете выполнить действия, описанные в разделе [выполнение отработки отказа в пуле для интерфейса ABC на Lync Server 2013](lync-server-2013-performing-an-abc-front-end-pool-failover.md).</span><span class="sxs-lookup"><span data-stu-id="d25a0-117">Additionally, if you later want to recreate a failed and unrecoverable pool that was part of a Front End pair, you can use the steps in [Performing an ABC Front End pool failover in Lync Server 2013](lync-server-2013-performing-an-abc-front-end-pool-failover.md).</span></span>

<span data-ttu-id="d25a0-118">В описанной в этом документе методологии используются специальные моменты на этапе планирования.</span><span class="sxs-lookup"><span data-stu-id="d25a0-118">The methodology described in this document involves special considerations during the planning phase.</span></span> <span data-ttu-id="d25a0-119">Подробные сведения можно найти [в разделе Создание резервной копии и плана восстановления для Lync Server 2013](lync-server-2013-establishing-a-backup-and-restoration-plan.md).</span><span class="sxs-lookup"><span data-stu-id="d25a0-119">For details, see [Establishing a backup and restoration plan for Lync Server 2013](lync-server-2013-establishing-a-backup-and-restoration-plan.md).</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="d25a0-120">Содержание</span><span class="sxs-lookup"><span data-stu-id="d25a0-120">In This Section</span></span>

  - [<span data-ttu-id="d25a0-121">Подготовка к резервному копированию и восстановлению для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d25a0-121">Preparing for Lync Server 2013 backup and restoration</span></span>](lync-server-2013-preparing-for-lync-server-backup-and-restoration.md)

  - [<span data-ttu-id="d25a0-122">Резервное копирование данных и параметров в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d25a0-122">Backing up data and settings in Lync Server 2013</span></span>](lync-server-2013-backing-up-data-and-settings.md)

  - [<span data-ttu-id="d25a0-123">Восстановление данных и параметров в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d25a0-123">Restoring data and settings in Lync Server 2013</span></span>](lync-server-2013-restoring-data-and-settings.md)

  - [<span data-ttu-id="d25a0-124">Журналы резервного копирования и восстановления для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d25a0-124">Backup and restoration worksheets for Lync Server 2013</span></span>](lync-server-2013-backup-and-restoration-worksheets.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

