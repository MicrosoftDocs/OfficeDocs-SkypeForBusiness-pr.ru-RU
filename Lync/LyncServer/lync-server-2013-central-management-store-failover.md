---
title: Отработка отказа центрального хранилища управления Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Central Management store failover
ms:assetid: f464d715-68a4-462c-9584-00f41ab10db0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205376(v=OCS.15)
ms:contentKeyID: 48185809
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 675f5b8e2880303a99897da18f44047c73961e4a
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48508046"
---
# <a name="central-management-store-failover-in-lync-server-2013"></a><span data-ttu-id="b56aa-102">Отработка отказа центрального хранилища управления в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b56aa-102">Central Management store failover in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b56aa-103">_**Последнее изменение темы:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="b56aa-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="b56aa-104">Центральное хранилище управления содержит данные о конфигурации серверов и служб в развертывании Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="b56aa-104">The Central Management store contains configuration data about servers and services in your Lync 2013 deployment.</span></span> <span data-ttu-id="b56aa-105">Он предоставляет надежное хранилище схематизированные данных, необходимое для определения, настройки, обслуживания, администрирования, описания и работы с развертыванием Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="b56aa-105">It provides a robust, schematized storage of the data needed to define, set up, maintain, administer, describe, and operate a Lync 2013 deployment.</span></span> <span data-ttu-id="b56aa-106">Оно также проверяет данные, чтобы обеспечить согласованность конфигурации.</span><span class="sxs-lookup"><span data-stu-id="b56aa-106">It also validates the data to ensure configuration consistency.</span></span>

<span data-ttu-id="b56aa-107">Каждое развертывание Lync включает в себя одно центральное хранилище управления, которое размещается на внутреннем сервере одного интерфейсного пула.</span><span class="sxs-lookup"><span data-stu-id="b56aa-107">Each Lync deployment includes one Central Management store, which is hosted by the Back End Server of one Front End pool.</span></span>

<span data-ttu-id="b56aa-108">При создании связи пула, включающей в себя пул, в котором размещается центральное хранилище управления, в резервном пуле настраивается база данных централизованного хранилища управления, а в обоих пулах устанавливаются службы центрального хранилища управления.</span><span class="sxs-lookup"><span data-stu-id="b56aa-108">When you establish a pool pairing that includes the pool hosting the Central Management store, a backup Central Management store database is set up in the backup pool, and Central Management store services are installed in both pools.</span></span> <span data-ttu-id="b56aa-109">В любой момент времени одна из двух баз данных центрального хранилища управления является активной основной, а другая — резервным.</span><span class="sxs-lookup"><span data-stu-id="b56aa-109">At any point in time, one of the two Central Management store databases is the active master, and the other is a standby.</span></span> <span data-ttu-id="b56aa-110">Служба резервного копирования осуществляет репликацию данных из активного образца на резервный.</span><span class="sxs-lookup"><span data-stu-id="b56aa-110">The content is replicated by the Backup Service from the active master to the standby.</span></span>

<span data-ttu-id="b56aa-111">Во время отработки отказа пула, включающей в себя пулы, в которых размещается центральное хранилище управления, администратору необходимо отработка отказа центрального хранилища управления перед отработкой отказа на интерфейсный пул.</span><span class="sxs-lookup"><span data-stu-id="b56aa-111">During a pool failover that involves the pools hosting the Central Management store, the administrator must fail over the Central Management store before failing over the Front End pool.</span></span>

<span data-ttu-id="b56aa-112">После восстановления аварийного восстановления не требуется возникнет ошибка восстановления центрального хранилища управления.</span><span class="sxs-lookup"><span data-stu-id="b56aa-112">After the disaster is repaired, it is not necessary to fail back the Central Management store.</span></span> <span data-ttu-id="b56aa-113">После восстановления центральное хранилище управления в исходном резервном пуле может быть активным.</span><span class="sxs-lookup"><span data-stu-id="b56aa-113">After repair, the Central Management store in the original backup pool can remain as the active master.</span></span>

<span data-ttu-id="b56aa-114">При отработке отказа центрального хранилища управления используются целевые целевые целевые показатели времени восстановления (RTO) и 5 минут для цели точки восстановления (RPO).</span><span class="sxs-lookup"><span data-stu-id="b56aa-114">The engineering targets for Central Management store failover are 5 minutes for recovery time objective (RTO) and 5 minutes for recovery point objective (RPO).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

