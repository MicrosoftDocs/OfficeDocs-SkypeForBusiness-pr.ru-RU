---
title: 'Lync Server 2013: Добавление или удаление сервера переднего плана'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Add or remove a Front End Server
ms:assetid: ab748733-6bad-4c93-8dda-db8d5271653d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205153(v=OCS.15)
ms:contentKeyID: 48185050
ms.date: 01/21/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5e358415b086594b67fabdc5ed74706a510e2f82
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42191462"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="add-or-remove-a-front-end-server-in-lync-server-2013"></a><span data-ttu-id="c972b-102">Добавление или удаление сервера переднего плана в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c972b-102">Add or remove a Front End Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c972b-103">_**Последнее изменение темы:** 2016-01-21_</span><span class="sxs-lookup"><span data-stu-id="c972b-103">_**Topic Last Modified:** 2016-01-21_</span></span>

<span data-ttu-id="c972b-p101">Когда вы добавляете в пул или удаляете из пула сервер переднего плана, вам необходимо перезапустить пул. Чтобы предотвратить перебои в обслуживании пользователей при добавлении или удалении сервера переднего плана, используйте следующую процедуру.</span><span class="sxs-lookup"><span data-stu-id="c972b-p101">When you add a Front End Server to a pool, or remove a Front End Server from a pool, you then need to restart the pool. To prevent any interruption of service to users, use the following procedure when adding or removing a Front End Server.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c972b-106">Если вы добавляете в пул новые серверы, обновите новые серверы пула так, чтобы они были на том же накопительном уровне обновления, что и существующие серверы в пуле.</span><span class="sxs-lookup"><span data-stu-id="c972b-106">If you're adding new servers to the pool, update your new pool servers to be at the same Cumulative Update level as the existing servers in the Pool.</span></span>



</div>

<div>

## <a name="to-add-or-remove-front-end-servers"></a><span data-ttu-id="c972b-107">Добавление и удаление серверов переднего плана</span><span class="sxs-lookup"><span data-stu-id="c972b-107">To add or remove Front End servers</span></span>

1.  <span data-ttu-id="c972b-p102">Если вы удаляете серверы переднего плана, сначала запретите новые подключения к ним. Для этого вы можете использовать следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="c972b-p102">If you are removing any Front End Servers, first stop new connections to those servers. To do so, you can use the following cmdlet:</span></span>
    
        Stop-CsWindowsServices -Graceful

2.  <span data-ttu-id="c972b-110">Если на удаляемых серверах нет текущих сеансов, остановите на них службы Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c972b-110">When the servers being removed have no current sessions, stop Lync Server services on them.</span></span>

3.  <span data-ttu-id="c972b-111">Откройте построитель топологий и добавьте или удалите требуемые серверы.</span><span class="sxs-lookup"><span data-stu-id="c972b-111">Open Topology Builder, and add or remove the necessary servers.</span></span>

4.  <span data-ttu-id="c972b-112">Опубликуйте топологию.</span><span class="sxs-lookup"><span data-stu-id="c972b-112">Publish the topology.</span></span>

5.  <span data-ttu-id="c972b-113">Если для пула не было двух серверов переднего плана, более двух, или более двух серверов, в точности два, необходимо ввести следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="c972b-113">If the pool has gone from having two Front End Servers to more than two, or gone from more than two servers to exactly two, you need to type the following cmdlet:</span></span>
    
        Reset-CsPoolRegistrarState-ResetType FullReset -PoolFqdn <PoolFqdn>
    
    <span data-ttu-id="c972b-114">Если в пуле три или более серверов, то по крайней мере три сервера должны работать, когда вы выполняете этот командлет.</span><span class="sxs-lookup"><span data-stu-id="c972b-114">If the pool has three or more servers, then at least three of those servers must be running when you type this cmdlet.</span></span>

6.  <span data-ttu-id="c972b-115">Перезапустите все серверы переднего плана в пуле по одному.</span><span class="sxs-lookup"><span data-stu-id="c972b-115">Restart all Front End Servers in the pool, one at a time.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

