---
title: 'Lync Server 2013: Добавление и удаление серверного переднего плана'
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
ms.openlocfilehash: 078c3d8eed34e7fb6fd98d2d7c12014b87a0497b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724019"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="add-or-remove-a-front-end-server-in-lync-server-2013"></a><span data-ttu-id="e8719-102">Add or remove a Front End Server in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e8719-102">Add or remove a Front End Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e8719-103">_**Тема последнего изменения:** 2016-01-21_</span><span class="sxs-lookup"><span data-stu-id="e8719-103">_**Topic Last Modified:** 2016-01-21_</span></span>

<span data-ttu-id="e8719-104">Если вы добавите сервер переднего плана в пул или удалите сервер переднего плана из пула, необходимо перезапустить пул.</span><span class="sxs-lookup"><span data-stu-id="e8719-104">When you add a Front End Server to a pool, or remove a Front End Server from a pool, you then need to restart the pool.</span></span> <span data-ttu-id="e8719-105">Чтобы предотвратить прерывание обслуживания для пользователей, выполните описанные ниже действия при добавлении или удалении сервера переднего плана.</span><span class="sxs-lookup"><span data-stu-id="e8719-105">To prevent any interruption of service to users, use the following procedure when adding or removing a Front End Server.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e8719-106">При добавлении в пул новых серверов их уровень накопительного пакета обновления должен быть таким же, как у существующих серверов в пуле.</span><span class="sxs-lookup"><span data-stu-id="e8719-106">If you're adding new servers to the pool, update your new pool servers to be at the same Cumulative Update level as the existing servers in the Pool.</span></span>



</div>

<div>

## <a name="to-add-or-remove-front-end-servers"></a><span data-ttu-id="e8719-107">Добавление и удаление серверов переднего плана</span><span class="sxs-lookup"><span data-stu-id="e8719-107">To add or remove Front End servers</span></span>

1.  <span data-ttu-id="e8719-108">Если удаляются все серверы переднего плана, сначала необходимо остановить новые подключения к этим серверам.</span><span class="sxs-lookup"><span data-stu-id="e8719-108">If you are removing any Front End Servers, first stop new connections to those servers.</span></span> <span data-ttu-id="e8719-109">Для этого вы можете использовать следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="e8719-109">To do so, you can use the following cmdlet:</span></span>
    
        Stop-CsWindowsServices -Graceful

2.  <span data-ttu-id="e8719-110">Если удаляемые серверы не имеют текущих сеансов, остановите на них службы Lync Server.</span><span class="sxs-lookup"><span data-stu-id="e8719-110">When the servers being removed have no current sessions, stop Lync Server services on them.</span></span>

3.  <span data-ttu-id="e8719-111">Откройте построитель топологии и добавьте или удалите необходимые серверы.</span><span class="sxs-lookup"><span data-stu-id="e8719-111">Open Topology Builder, and add or remove the necessary servers.</span></span>

4.  <span data-ttu-id="e8719-112">Опубликуйте топологию.</span><span class="sxs-lookup"><span data-stu-id="e8719-112">Publish the topology.</span></span>

5.  <span data-ttu-id="e8719-113">Если в пуле не было двух серверов переднего плана, более двух, или более двух серверов, необходимо ввести следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="e8719-113">If the pool has gone from having two Front End Servers to more than two, or gone from more than two servers to exactly two, you need to type the following cmdlet:</span></span>
    
        Reset-CsPoolRegistrarState-ResetType FullReset -PoolFqdn <PoolFqdn>
    
    <span data-ttu-id="e8719-114">Если в пуле есть три или более серверов, при вводе этого командлета на компьютере должно быть запущено по крайней мере три сервера.</span><span class="sxs-lookup"><span data-stu-id="e8719-114">If the pool has three or more servers, then at least three of those servers must be running when you type this cmdlet.</span></span>

6.  <span data-ttu-id="e8719-115">Перезапустите все серверы переднего плана в пуле, по одному за один раз.</span><span class="sxs-lookup"><span data-stu-id="e8719-115">Restart all Front End Servers in the pool, one at a time.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

