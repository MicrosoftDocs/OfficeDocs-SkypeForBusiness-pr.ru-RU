---
title: 'Lync Server 2013: отработка отказа пула'
description: 'Lync Server 2013: отработка отказа пула.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Failing back a pool
ms:assetid: 6232b644-ef57-4c9c-abec-14ff8ffc9fe7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204945(v=OCS.15)
ms:contentKeyID: 48184289
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1c1fc0ea4514d2f951dd936521590d47b809db38
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48567745"
---
# <a name="failing-back-a-pool-in-lync-server-2013"></a><span data-ttu-id="e1bc1-103">Отработка отказа пула в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e1bc1-103">Failing back a pool in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e1bc1-104">_**Последнее изменение темы:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="e1bc1-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="e1bc1-105">После возврата пула, в котором возникла аварийная ситуация, в режим работы (в данном примере это Pool1) выполните следующие действия для восстановления обычного рабочего состояния развертывания.</span><span class="sxs-lookup"><span data-stu-id="e1bc1-105">After the pool that experienced the disaster is back online (that is, Pool1 in this example), take the following steps to restore your deployment to regular working status.</span></span>

<span data-ttu-id="e1bc1-p101">Обратите внимание, что процедура отработки отказа занимает несколько минут. В качестве справки: отработка отказа для пула в 20000 пользователей занимает до 60 минут.</span><span class="sxs-lookup"><span data-stu-id="e1bc1-p101">Note that the failback process takes several minute to complete.  For reference, it is expected to take up to 60 minutes for a pool of 20,000 users.</span></span>

1.  <span data-ttu-id="e1bc1-108">Восстановите размещение пользователей, которые изначально размещались в пуле Pool1 и были переключены на пул Pool2; для этого введите следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="e1bc1-108">Fail back the users who were originally homed in Pool1 and have been failed over to Pool2 by typing the following cmdlet:</span></span>
    
        Invoke-CsPoolFailback -PoolFQDN <Pool1 FQDN> -Verbose

<span data-ttu-id="e1bc1-109">Другие действия не требуются.</span><span class="sxs-lookup"><span data-stu-id="e1bc1-109">No other steps are necessary.</span></span> <span data-ttu-id="e1bc1-110">Если вы отработка отказа на центральном сервере управления, вы можете оставить ее в Pool2.</span><span class="sxs-lookup"><span data-stu-id="e1bc1-110">If you failed over the Central Management Server, you can leave it in Pool2.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

