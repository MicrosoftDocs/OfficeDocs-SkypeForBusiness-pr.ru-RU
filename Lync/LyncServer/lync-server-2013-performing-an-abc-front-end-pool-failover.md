---
title: 'Lync Server 2013: выполнение отработки отказа для пула переднего плана ABC'
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
ms.openlocfilehash: ebffd5b4e1b4cca1cb815f37f569aebd6a241ccd
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42215645"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="performing-an-abc-front-end-pool-failover-in-lync-server-2013"></a><span data-ttu-id="6caa2-102">Выполнение отработки отказа для пула переднего плана ABC в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6caa2-102">Performing an ABC Front End pool failover in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6caa2-103">_**Последнее изменение темы:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="6caa2-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="6caa2-104">В двух подразделах этого раздела описывается процедура выполнения отработки отказа для пула ABC в Lync Server 2013, где есть связанные пулы переднего плана Lync Server A и B, а пул "а" становится невосстанавливаемым.</span><span class="sxs-lookup"><span data-stu-id="6caa2-104">The two topics in this section describe the procedure for performing an ABC pool failover in Lync Server 2013, where there are paired Lync Server Front End pools A and B, and pool A becomes unrecoverable.</span></span> <span data-ttu-id="6caa2-105">С помощью этой процедуры вы создадите новый пул переднего плана C с новым полным доменным именем (FQDN).</span><span class="sxs-lookup"><span data-stu-id="6caa2-105">Using this procedure, you create a new Front End pool C with a new fully qualified domain name (FQDN).</span></span> <span data-ttu-id="6caa2-106">Пул C строится на основе информации из сбоя пула A. Кроме того, эта процедура включает в себя объединение пулов B и C.</span><span class="sxs-lookup"><span data-stu-id="6caa2-106">Pool C is constructed from the information from failed pool A. The procedure also includes pairing together pools B and C.</span></span>

  - [<span data-ttu-id="6caa2-107">Необходимые условия резервного копирования для отработки отказа для пула ABC в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6caa2-107">Backup prerequisites for ABC pool failover in Lync Server 2013</span></span>](lync-server-2013-backup-prerequisites-for-abc-pool-failover.md)

  - [<span data-ttu-id="6caa2-108">Процедура отработки отказа для пула переднего плана ABC в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6caa2-108">Front End pool ABC failover procedure in Lync Server 2013</span></span>](lync-server-2013-front-end-pool-abc-failover-procedure.md)

</div>

<span> </span>

</div>

</div>

</div>

