---
title: 'Lync Server 2013: отработка отказа центральным хранилищем управления'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Central Management store failover
ms:assetid: f464d715-68a4-462c-9584-00f41ab10db0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205376(v=OCS.15)
ms:contentKeyID: 48185809
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5b320b3313f37a1912b909d018bbe37de5a997be
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34841665"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="central-management-store-failover-in-lync-server-2013"></a><span data-ttu-id="cfcf7-102">Отработка отказа центральным хранилищем управления в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cfcf7-102">Central Management store failover in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cfcf7-103">_**Тема последнего изменения:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="cfcf7-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="cfcf7-104">В хранилище Центрального управления содержатся данные о конфигурации серверов и служб в развертывании Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="cfcf7-104">The Central Management store contains configuration data about servers and services in your Lync 2013 deployment.</span></span> <span data-ttu-id="cfcf7-105">Она предоставляет надежное хранилище счематизед данных, необходимых для определения, настройки, обслуживания, администрирования, описания и работы с развертыванием Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="cfcf7-105">It provides a robust, schematized storage of the data needed to define, set up, maintain, administer, describe, and operate a Lync 2013 deployment.</span></span> <span data-ttu-id="cfcf7-106">Кроме того, оно обеспечивает проверку этих данных на предмет внутренней согласованности.</span><span class="sxs-lookup"><span data-stu-id="cfcf7-106">It also validates the data to ensure configuration consistency.</span></span>

<span data-ttu-id="cfcf7-107">Каждое развертывание Lync включает в себя единое центральное хранилище, которое размещается на сервере переднего плана для первого пула.</span><span class="sxs-lookup"><span data-stu-id="cfcf7-107">Each Lync deployment includes one Central Management store, which is hosted by the Back End Server of one Front End pool.</span></span>

<span data-ttu-id="cfcf7-108">Если вы установили пару пулов, включающую пул, в котором размещено хранилище Центрального управления, в пуле архивации настраивается база данных централизованного управления резервным копированием, а также в обоих пулах устанавливаются службы централизованного управления хранилищем.</span><span class="sxs-lookup"><span data-stu-id="cfcf7-108">When you establish a pool pairing that includes the pool hosting the Central Management store, a backup Central Management store database is set up in the backup pool, and Central Management store services are installed in both pools.</span></span> <span data-ttu-id="cfcf7-109">В любой момент времени одна из двух баз данных центрального хранилища может быть активной, а другая — в режиме ожидания.</span><span class="sxs-lookup"><span data-stu-id="cfcf7-109">At any point in time, one of the two Central Management store databases is the active master, and the other is a standby.</span></span> <span data-ttu-id="cfcf7-110">Содержимое реплицируется службой резервного копирования из активного образца в ждущий режим.</span><span class="sxs-lookup"><span data-stu-id="cfcf7-110">The content is replicated by the Backup Service from the active master to the standby.</span></span>

<span data-ttu-id="cfcf7-111">Во время отработки отказа пула, включающего в себя пулы, в которых размещено центральное хранилище, администратор должен отдать сбой на центральное хранилище управления, прежде чем переходить на пул переднего плана.</span><span class="sxs-lookup"><span data-stu-id="cfcf7-111">During a pool failover that involves the pools hosting the Central Management store, the administrator must fail over the Central Management store before failing over the Front End pool.</span></span>

<span data-ttu-id="cfcf7-112">После ликвидации аварийной ситуации восстановление размещения центрального хранилища управления не требуется.</span><span class="sxs-lookup"><span data-stu-id="cfcf7-112">After the disaster is repaired, it is not necessary to fail back the Central Management store.</span></span> <span data-ttu-id="cfcf7-113">После восстановления хранилище Центрального управления в исходном пуле резервных копий может оставаться активным.</span><span class="sxs-lookup"><span data-stu-id="cfcf7-113">After repair, the Central Management store in the original backup pool can remain as the active master.</span></span>

<span data-ttu-id="cfcf7-114">В соответствии с проектными задачами при отработке отказа для центрального хранилища управления целевое время восстановления (RTO) составляет 5 минут, а целевая точка восстановления (RPO) — 5 минут.</span><span class="sxs-lookup"><span data-stu-id="cfcf7-114">The engineering targets for Central Management store failover are 5 minutes for recovery time objective (RTO) and 5 minutes for recovery point objective (RPO).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

