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
ms.openlocfilehash: d65d06ac9c72e776eee51b9b3dff6c6db3a59031
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044451"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="backing-up-and-restoring-lync-server-2013"></a><span data-ttu-id="e0277-102">Резервное копирование и восстановление Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e0277-102">Backing up and restoring Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e0277-103">_**Последнее изменение темы:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="e0277-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="e0277-104">В этом разделе вы найдете рекомендации по резервному копированию данных Lync Server 2013 и их восстановлению в случае сбоя.</span><span class="sxs-lookup"><span data-stu-id="e0277-104">In this section, you’ll find the best practices for backing up your Lync Server 2013 data, and for restoring it if you have a failure.</span></span> <span data-ttu-id="e0277-105">Эти рекомендации применимы к следующим ситуациям:</span><span class="sxs-lookup"><span data-stu-id="e0277-105">These best practices apply to the following situations:</span></span>

  - <span data-ttu-id="e0277-106">Весь пул Lync Server любого типа (сервер переднего плана, пограничный сервер, сервер-посредник, сервер сохраняемого чата или директор) или отдельный сервер в одном из этих пулов.</span><span class="sxs-lookup"><span data-stu-id="e0277-106">An entire Lync Server pool of any type (Front End Server, Edge Server, Mediation Server, Persistent Chat Server, or Director), or an individual server in one of these pools.</span></span>

  - <span data-ttu-id="e0277-107">Центральный сервер управления</span><span class="sxs-lookup"><span data-stu-id="e0277-107">The Central Management Server</span></span>

  - <span data-ttu-id="e0277-108">Сервер Standard Edition</span><span class="sxs-lookup"><span data-stu-id="e0277-108">A Standard Edition server</span></span>

  - <span data-ttu-id="e0277-109">Сервер переднего план выпуска Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="e0277-109">An Enterprise Edition Back End Server</span></span>

  - <span data-ttu-id="e0277-110">Хранилище файлов</span><span class="sxs-lookup"><span data-stu-id="e0277-110">A File Store</span></span>

  - <span data-ttu-id="e0277-111">База данных архивации, база данных мониторинга или база данных сохраняемого чата</span><span class="sxs-lookup"><span data-stu-id="e0277-111">An Archiving database, Monitoring database, or Persistent Chat database</span></span>

<span data-ttu-id="e0277-112">В этом разделе не представлены сведения о восстановлении всего сайта или для разработки резервного сайта.</span><span class="sxs-lookup"><span data-stu-id="e0277-112">This section does not include information about restoring an entire site or for developing a standby site.</span></span> <span data-ttu-id="e0277-113">Подробные сведения о разработке решения аварийного восстановления с подключенными интерфейсными пулами приведены [в статье Планирование обеспечения высокой доступности и аварийного восстановления в Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span><span class="sxs-lookup"><span data-stu-id="e0277-113">For details about developing a disaster recovery solution with paired Front End pools, see [Planning for high availability and disaster recovery in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span></span> <span data-ttu-id="e0277-114">Это рекомендуемый способ планирования аварийного восстановления.</span><span class="sxs-lookup"><span data-stu-id="e0277-114">This is the recommended method for planning for disaster recovery.</span></span>

<span data-ttu-id="e0277-115">Если вы развернули связанные пулы переднего плана, если один из этих пулов отказывается и становится невосстанавливаемым, можно восстановить пул с новым полным доменным именем (FQDN) из соответствующего пула.</span><span class="sxs-lookup"><span data-stu-id="e0277-115">If you have deployed paired Front End pools, if one of these pools fails and becomes unrecoverable, you can restore this pool with a new fully qualified domain name (FQDN) from its paired pool.</span></span> <span data-ttu-id="e0277-116">Подробные сведения о действиях, выполняемых для выполнения этого восстановления, приведены в разделе Failing of The Pool of the [Lync Server 2013](lync-server-2013-failing-over-a-pool.md).</span><span class="sxs-lookup"><span data-stu-id="e0277-116">For details on the steps to perform this recovery, see [Failing over a pool in Lync Server 2013](lync-server-2013-failing-over-a-pool.md).</span></span> <span data-ttu-id="e0277-117">Кроме того, если позднее потребуется повторно создать неисправной и невосстанавливаемый пул, который являлся частью многосерверной связи, можно выполнить действия, описанные в статье [выполнение отработки отказа для пула переднего плана ABC в Lync Server 2013](lync-server-2013-performing-an-abc-front-end-pool-failover.md).</span><span class="sxs-lookup"><span data-stu-id="e0277-117">Additionally, if you later want to recreate a failed and unrecoverable pool that was part of a Front End pair, you can use the steps in [Performing an ABC Front End pool failover in Lync Server 2013](lync-server-2013-performing-an-abc-front-end-pool-failover.md).</span></span>

<span data-ttu-id="e0277-118">В методологии, описанной в этом документе, используются особые рекомендации на этапе планирования.</span><span class="sxs-lookup"><span data-stu-id="e0277-118">The methodology described in this document involves special considerations during the planning phase.</span></span> <span data-ttu-id="e0277-119">Сведения о [создании плана резервного копирования и восстановления для Lync Server 2013](lync-server-2013-establishing-a-backup-and-restoration-plan.md).</span><span class="sxs-lookup"><span data-stu-id="e0277-119">For details, see [Establishing a backup and restoration plan for Lync Server 2013](lync-server-2013-establishing-a-backup-and-restoration-plan.md).</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="e0277-120">Содержание</span><span class="sxs-lookup"><span data-stu-id="e0277-120">In This Section</span></span>

  - [<span data-ttu-id="e0277-121">Подготовка к резервному копированию и восстановлению Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e0277-121">Preparing for Lync Server 2013 backup and restoration</span></span>](lync-server-2013-preparing-for-lync-server-backup-and-restoration.md)

  - [<span data-ttu-id="e0277-122">Резервное копирование данных и параметров в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e0277-122">Backing up data and settings in Lync Server 2013</span></span>](lync-server-2013-backing-up-data-and-settings.md)

  - [<span data-ttu-id="e0277-123">Восстановление данных и параметров в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e0277-123">Restoring data and settings in Lync Server 2013</span></span>](lync-server-2013-restoring-data-and-settings.md)

  - [<span data-ttu-id="e0277-124">Таблицы резервного копирования и восстановления для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e0277-124">Backup and restoration worksheets for Lync Server 2013</span></span>](lync-server-2013-backup-and-restoration-worksheets.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

