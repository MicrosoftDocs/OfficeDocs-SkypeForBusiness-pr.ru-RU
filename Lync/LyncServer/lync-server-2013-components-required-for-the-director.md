---
title: 'Lync Server 2013: компоненты, необходимые для директора'
description: 'Lync Server 2013: компоненты, необходимые для директора.'
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
ms.openlocfilehash: 57f717b9ddb9557f212321cdab075713a4b85c2d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48549505"
---
# <a name="components-required-for-the-director-in-lync-server-2013"></a><span data-ttu-id="ccfb1-103">Компоненты, необходимые для директора в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ccfb1-103">Components required for the Director in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ccfb1-104">_**Последнее изменение темы:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="ccfb1-104">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="ccfb1-105">Единственным компонентом, необходимым для создания и настройки директора, является развертывание роли сервера Director.</span><span class="sxs-lookup"><span data-stu-id="ccfb1-105">The only component required to create and configure a Director is to deploy the Director server role.</span></span> <span data-ttu-id="ccfb1-106">Это можно сделать с помощью построителя топологий и определить один пул компьютеров или пул из нескольких компьютеров в узле "директор пула".</span><span class="sxs-lookup"><span data-stu-id="ccfb1-106">You do this by using Topology Builder and define either a single computer pool or a multiple computer pool in the Director pool node.</span></span> <span data-ttu-id="ccfb1-107">Определив директор или пул директоров, запустите мастер развертывания Lync Server на компьютере, который будет директор.</span><span class="sxs-lookup"><span data-stu-id="ccfb1-107">After you have defined the Director or Director pool, run the Lync Server Deployment Wizard on the computer that will be a Director.</span></span> <span data-ttu-id="ccfb1-108">В случае пула директоров мастер развертывания Lync Server запускается на каждом сервере, который будет участником пула.</span><span class="sxs-lookup"><span data-stu-id="ccfb1-108">In the case of a Director pool, you run the Lync Server Deployment Wizard on each server that will be a member of the pool.</span></span>

<div>

## <a name="topologies"></a><span data-ttu-id="ccfb1-109">Топологии</span><span class="sxs-lookup"><span data-stu-id="ccfb1-109">Topologies</span></span>

<span data-ttu-id="ccfb1-110">Вы можете реализовать один сервер директоров или пул директоров.</span><span class="sxs-lookup"><span data-stu-id="ccfb1-110">You can implement a single Director server or a Director pool.</span></span> <span data-ttu-id="ccfb1-111">Директор всегда является отдельным сервером или пулом, но не связан с какой-либо другой ролью сервера в Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ccfb1-111">The Director is always a separate server or pool, not collocated with any other server role in Lync Server 2013.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ccfb1-112">Если вы не развертываете режиссеров, роль директора будет возлагаться на сервер переднего плана или интерфейсный пул.</span><span class="sxs-lookup"><span data-stu-id="ccfb1-112">If you do not deploy Directors, the Front End Server or Front End pool will assume the Director role.</span></span>



</div>

<span data-ttu-id="ccfb1-113">Необходимо сбалансировать балансировку нагрузки для пула директоров.</span><span class="sxs-lookup"><span data-stu-id="ccfb1-113">A pool of Directors must be load balanced.</span></span> <span data-ttu-id="ccfb1-114">Для этого можно выполнить одно из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="ccfb1-114">You can do one of the following:</span></span>

  - <span data-ttu-id="ccfb1-115">Создать топологию, которая использует аппаратный балансировщик нагрузки для веб-служб и балансировку нагрузки на DNS для остальных типов трафика.</span><span class="sxs-lookup"><span data-stu-id="ccfb1-115">Create a topology that uses a hardware load balancer for web services and Domain Name System (DNS) load balancing for the other traffic types.</span></span>
    
    [<span data-ttu-id="ccfb1-116">Масштабируемый пул директоров — балансировка нагрузки на DNS и аппаратный балансировщик нагрузки в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ccfb1-116">Scaled Director pool - DNS load balancing and hardware load balancer in Lync Server 2013</span></span>](lync-server-2013-scaled-director-pool-dns-load-balancing-and-hardware-load-balancer.md)

  - <span data-ttu-id="ccfb1-117">Создайте топологию, использующую аппаратную подсистему балансировки нагрузки для балансировки нагрузки, необходимой для пула директоров.</span><span class="sxs-lookup"><span data-stu-id="ccfb1-117">Create a topology that uses a hardware load balancer for load balancing needed for the Director pool.</span></span>
    
    [<span data-ttu-id="ccfb1-118">Масштабируемый пул директоров — аппаратный балансировщик нагрузки в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ccfb1-118">Scaled Director pool - hardware load balancer in Lync Server 2013</span></span>](lync-server-2013-scaled-director-pool-hardware-load-balancer.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

