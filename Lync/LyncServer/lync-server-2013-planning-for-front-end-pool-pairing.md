---
title: 'Lync Server 2013: планирование связывания пула переднего плана'
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
ms.openlocfilehash: 10d45434bf34cc5e7e158039851e8a7fb2cbd6e1
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42184342"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="planning-for-front-end-pool-pairing-in-lync-server-2013"></a><span data-ttu-id="bed82-102">Планирование связывания пула переднего плана в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bed82-102">Planning for Front End pool pairing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bed82-103">_**Последнее изменение темы:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="bed82-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="bed82-104">Для достижения наилучших возможностей аварийного восстановления в Lync Server 2013 разверните пары интерфейсных пулов на двух географически распределенных сайтах.</span><span class="sxs-lookup"><span data-stu-id="bed82-104">For the best disaster recovery abilities in Lync Server 2013, deploy pairs of Front End pools across two geographically dispersed sites.</span></span> <span data-ttu-id="bed82-105">Каждый из них должен содержать интерфейсный пул, сопряженный с соответствующим интерфейсным пулом в другом узле.</span><span class="sxs-lookup"><span data-stu-id="bed82-105">Each site contains a Front End pool which is paired with a corresponding Front End pool in the other site.</span></span> <span data-ttu-id="bed82-106">Оба сайта активны, а служба резервного копирования Lync Server обеспечивает репликацию данных в режиме реального времени для синхронизации пулов.</span><span class="sxs-lookup"><span data-stu-id="bed82-106">Both sites are active, and the Lync Server Backup Service provides real-time data replication to keep the pools synchronized.</span></span> <span data-ttu-id="bed82-107">Служба резервного копирования — это новая функция в Lync Server 2013, предназначенная для поддержки решения по аварийному восстановлению.</span><span class="sxs-lookup"><span data-stu-id="bed82-107">The Backup Service is a new feature in Lync Server 2013, designed to support the disaster recovery solution.</span></span> <span data-ttu-id="bed82-108">Она устанавливается в интерфейсном пуле при соединении его с другим интерфейсным пулом.</span><span class="sxs-lookup"><span data-stu-id="bed82-108">It is installed on a Front End pool when you pair the pool with another Front End pool.</span></span>

<span data-ttu-id="bed82-p102">Если пул в одном узле становится недоступным, вы можете перевести пользователей из этого пула в другой пул в другом узле, который предоставляет услуги для всех пользователей в обоих пулах. Для планирования емкости каждый пул должен проектироваться таким образом, чтобы обрабатывать рабочие нагрузки всех пользователей в обоих пулах в случае аварии.</span><span class="sxs-lookup"><span data-stu-id="bed82-p102">If the pool in one site fails, you can fail over the users from that pool to the pool in the other site, which then provides services to all the users in both pools. For capacity planning purposes, each pool should be designed to handle the workloads of all users in both pools in the event of a disaster.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="bed82-111">Содержание</span><span class="sxs-lookup"><span data-stu-id="bed82-111">In This Section</span></span>

  - [<span data-ttu-id="bed82-112">Поддерживаемые варианты связывания пулов и рекомендации для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bed82-112">Supported pool pairing options and best practices for Lync Server 2013</span></span>](lync-server-2013-supported-pool-pairing-options-and-best-practices.md)

  - [<span data-ttu-id="bed82-113">Связи регистратора резервного копирования в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bed82-113">Backup Registrar relationships in Lync Server 2013</span></span>](lync-server-2013-backup-registrar-relationships.md)

  - [<span data-ttu-id="bed82-114">Время восстановления для отработки отказа пула и восстановления размещения пула в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bed82-114">Recovery time for pool failover and pool failback in Lync Server 2013</span></span>](lync-server-2013-recovery-time-for-pool-failover-and-pool-failback.md)

  - [<span data-ttu-id="bed82-115">Отработка отказа центрального хранилища управления в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bed82-115">Central Management store failover in Lync Server 2013</span></span>](lync-server-2013-central-management-store-failover.md)

  - [<span data-ttu-id="bed82-116">Безопасность данных связывания пула переднего плана в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bed82-116">Front End pool pairing data security in Lync Server 2013</span></span>](lync-server-2013-front-end-pool-pairing-data-security.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

