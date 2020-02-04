---
title: 'Lync Server 2013: выполнение отработки отказа для пула электронной стороны ABC'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Performing an ABC Front End pool failover
ms:assetid: 81ecd26d-49e3-4c72-a66e-02748efb513b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945637(v=OCS.15)
ms:contentKeyID: 51541489
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 155d8224b80e614ac8609c007a16072e9d3a5c60
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755279"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="performing-an-abc-front-end-pool-failover-in-lync-server-2013"></a><span data-ttu-id="57f66-102">Выполнение отработки отказа в пуле переднего плана для электронной стороны в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="57f66-102">Performing an ABC Front End pool failover in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="57f66-103">_**Тема последнего изменения:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="57f66-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="57f66-104">В двух темах этого раздела описаны процедуры выполнения отработки отказа для пула ABC в Lync Server 2013, где есть Объединенные серверные пулы Lync Server A и B, а пул A становится невосстанавливаемым.</span><span class="sxs-lookup"><span data-stu-id="57f66-104">The two topics in this section describe the procedure for performing an ABC pool failover in Lync Server 2013, where there are paired Lync Server Front End pools A and B, and pool A becomes unrecoverable.</span></span> <span data-ttu-id="57f66-105">С помощью этой процедуры вы создаете новый пул переднего плана C с новым полным доменным именем (FQDN).</span><span class="sxs-lookup"><span data-stu-id="57f66-105">Using this procedure, you create a new Front End pool C with a new fully qualified domain name (FQDN).</span></span> <span data-ttu-id="57f66-106">Пул C строится на основе данных, которые не удалось получить из пула. Эта процедура также включает в себя пару групп B и C.</span><span class="sxs-lookup"><span data-stu-id="57f66-106">Pool C is constructed from the information from failed pool A. The procedure also includes pairing together pools B and C.</span></span>

  - [<span data-ttu-id="57f66-107">Требования для резервного копирования для отработки отказа в пуле ABC в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="57f66-107">Backup prerequisites for ABC pool failover in Lync Server 2013</span></span>](lync-server-2013-backup-prerequisites-for-abc-pool-failover.md)

  - [<span data-ttu-id="57f66-108">Простая процедура отработки отказа для интерфейсного пула в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="57f66-108">Front End pool ABC failover procedure in Lync Server 2013</span></span>](lync-server-2013-front-end-pool-abc-failover-procedure.md)

</div>

<span> </span>

</div>

</div>

</div>

