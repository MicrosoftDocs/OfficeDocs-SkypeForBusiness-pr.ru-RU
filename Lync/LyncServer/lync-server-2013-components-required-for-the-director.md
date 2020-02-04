---
title: 'Lync Server 2013: компоненты, необходимые для директора'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Components required for the Director
ms:assetid: 15c7c8d4-b93f-4386-b2d1-d76dab8f801e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398228(v=OCS.15)
ms:contentKeyID: 48183502
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 12db97a72a9882964727edd3084e0bd598527358
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757093"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="components-required-for-the-director-in-lync-server-2013"></a><span data-ttu-id="c2ec5-102">Компоненты, необходимые для директора в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c2ec5-102">Components required for the Director in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c2ec5-103">_**Тема последнего изменения:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="c2ec5-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="c2ec5-104">Единственный компонент, необходимый для создания и настройки режиссера, — это развертывание роли "Режиссерный сервер".</span><span class="sxs-lookup"><span data-stu-id="c2ec5-104">The only component required to create and configure a Director is to deploy the Director server role.</span></span> <span data-ttu-id="c2ec5-105">Это можно сделать, воспользовавшись построителем топологии и определив один или несколько пулов компьютеров в узле режиссера пула.</span><span class="sxs-lookup"><span data-stu-id="c2ec5-105">You do this by using Topology Builder and define either a single computer pool or a multiple computer pool in the Director pool node.</span></span> <span data-ttu-id="c2ec5-106">Определив пул режиссеров или режиссера, запустите мастер развертывания Lync Server на компьютере, который будет режиссером.</span><span class="sxs-lookup"><span data-stu-id="c2ec5-106">After you have defined the Director or Director pool, run the Lync Server Deployment Wizard on the computer that will be a Director.</span></span> <span data-ttu-id="c2ec5-107">В случае с режиссером пула вы запускаете мастер развертывания Lync Server на каждом сервере, который будет входить в пул.</span><span class="sxs-lookup"><span data-stu-id="c2ec5-107">In the case of a Director pool, you run the Lync Server Deployment Wizard on each server that will be a member of the pool.</span></span>

<div>

## <a name="topologies"></a><span data-ttu-id="c2ec5-108">Топологий</span><span class="sxs-lookup"><span data-stu-id="c2ec5-108">Topologies</span></span>

<span data-ttu-id="c2ec5-109">Вы можете внедрить один и тот же Режиссерный сервер или пул.</span><span class="sxs-lookup"><span data-stu-id="c2ec5-109">You can implement a single Director server or a Director pool.</span></span> <span data-ttu-id="c2ec5-110">Режиссер всегда является отдельным сервером или пулом, но не может быть размещен с другой ролью сервера в Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c2ec5-110">The Director is always a separate server or pool, not collocated with any other server role in Lync Server 2013.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c2ec5-111">Если вы не развертываете режиссеров, роль директора будет возлагаться на сервер переднего плана или пул внешних интерфейсов.</span><span class="sxs-lookup"><span data-stu-id="c2ec5-111">If you do not deploy Directors, the Front End Server or Front End pool will assume the Director role.</span></span>



</div>

<span data-ttu-id="c2ec5-112">Пул директоров должен быть сбалансированно загружен.</span><span class="sxs-lookup"><span data-stu-id="c2ec5-112">A pool of Directors must be load balanced.</span></span> <span data-ttu-id="c2ec5-113">Вы можете выполнить одно из указанных ниже действий.</span><span class="sxs-lookup"><span data-stu-id="c2ec5-113">You can do one of the following:</span></span>

  - <span data-ttu-id="c2ec5-114">Создайте топологию, использующую аппаратную подсистему балансировки нагрузки для веб-служб и балансировки нагрузки DNS для других типов трафика.</span><span class="sxs-lookup"><span data-stu-id="c2ec5-114">Create a topology that uses a hardware load balancer for web services and Domain Name System (DNS) load balancing for the other traffic types.</span></span>
    
    [<span data-ttu-id="c2ec5-115">Масштабируемый пул директоров — балансировка нагрузки на DNS и аппаратный балансировщик нагрузки в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c2ec5-115">Scaled Director pool - DNS load balancing and hardware load balancer in Lync Server 2013</span></span>](lync-server-2013-scaled-director-pool-dns-load-balancing-and-hardware-load-balancer.md)

  - <span data-ttu-id="c2ec5-116">Создание топологии, использующей аппаратный балансировщик нагрузки для балансировки нагрузки, необходимый для пула ресурсов.</span><span class="sxs-lookup"><span data-stu-id="c2ec5-116">Create a topology that uses a hardware load balancer for load balancing needed for the Director pool.</span></span>
    
    [<span data-ttu-id="c2ec5-117">Масштабируемый пул директоров — аппаратный балансировщик нагрузки в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c2ec5-117">Scaled Director pool - hardware load balancer in Lync Server 2013</span></span>](lync-server-2013-scaled-director-pool-hardware-load-balancer.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

