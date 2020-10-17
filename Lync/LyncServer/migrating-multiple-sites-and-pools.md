---
title: Перенос нескольких сайтов и пулов
description: Перенос нескольких сайтов и пулов.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migrating multiple sites and pools
ms:assetid: a6d726d2-564d-4b39-a97c-5656a673292a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205165(v=OCS.15)
ms:contentKeyID: 48185079
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7efaa6f038286ff9138e631f23da88bb445e20f1
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543255"
---
# <a name="migrating-multiple-sites-and-pools"></a><span data-ttu-id="5bbf7-103">Перенос нескольких сайтов и пулов</span><span class="sxs-lookup"><span data-stu-id="5bbf7-103">Migrating multiple sites and pools</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5bbf7-104">_**Последнее изменение темы:** 2012-09-17_</span><span class="sxs-lookup"><span data-stu-id="5bbf7-104">_**Topic Last Modified:** 2012-09-17_</span></span>

<span data-ttu-id="5bbf7-105">Lync Server 2013 поддерживает развертывание с несколькими сайтами и несколькими пулами.</span><span class="sxs-lookup"><span data-stu-id="5bbf7-105">Lync Server 2013 supports multi-site and multi-pool deployments.</span></span> <span data-ttu-id="5bbf7-106">Процесс переноса нескольких пулов с Lync Server 2010 на Lync Server 2013 требует следующих факторов:</span><span class="sxs-lookup"><span data-stu-id="5bbf7-106">The process of migrating multiple pools from Lync Server 2010 to Lync Server 2013 requires the following considerations:</span></span>

1.  <span data-ttu-id="5bbf7-107">После развертывания пилотного пула Lync Server 2013 необходимо определить подмножество пилотных пользователей, которые будут перемещены в пул Lync Server 2013, и методологию для проверки функциональных возможностей пользователей.</span><span class="sxs-lookup"><span data-stu-id="5bbf7-107">After deploying a Lync Server 2013 pilot pool, you need to define a subset of pilot users that will be moved to the Lync Server 2013 pool, and a methodology for validating the functionality of the users.</span></span> <span data-ttu-id="5bbf7-108">Например, после перемещения пользователя в пилотный пул убедитесь, что политика конференции пользователя перемещена в Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5bbf7-108">For example, after moving a user to the pilot pool, verify the user’s conference policy has moved to Lync Server 2013.</span></span>

2.  <span data-ttu-id="5bbf7-109">После развертывания пограничного сервера в пилотном пуле необходимо убедиться, что внешние пользователи могут связываться с пулом Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5bbf7-109">After deploying an Edge Server in the pilot pool, you need to validate that external users can communicate with the Lync Server 2013 pool.</span></span>

3.  <span data-ttu-id="5bbf7-110">После переноса федеративных маршрутов с пограничных серверов Lync Server 2010 на пилотный проект Lync Server 2013 пограничные серверы необходимо проверить, что Федеративные пользователи могут связываться с пулом Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5bbf7-110">After transitioning the federated routes from Lync Server 2010 Edge Servers to the pilot Lync Server 2013 Edge Servers, you need to validate that federated users can communicate with the Lync Server 2013 pool.</span></span>

4.  <span data-ttu-id="5bbf7-111">После перемещения всех пользователей и объектов контактов, не являющихся пользователями, необходимо проверить, что пул Lync Server 2010 не заполнен.</span><span class="sxs-lookup"><span data-stu-id="5bbf7-111">After moving all the users and non-user contact objects, you need to validate that the Lync Server 2010 pool is empty.</span></span>

5.  <span data-ttu-id="5bbf7-112">После проверки того, что пул Lync Server 2010 является пустым, вы можете отключить пул.</span><span class="sxs-lookup"><span data-stu-id="5bbf7-112">After verifying that the Lync Server 2010 pool is empty, you can then deactivate the pool.</span></span>
    
    <span data-ttu-id="5bbf7-113">Сведения об отключении устаревшего пула и серверов Lync Server 2010 приведены в статье [Этап 8: списание устаревших пулов](phase-8-decommission-legacy-pools.md).</span><span class="sxs-lookup"><span data-stu-id="5bbf7-113">For details about how to deactivate the legacy Lync Server 2010 pool and servers, see [Phase 8: Decommission legacy pools](phase-8-decommission-legacy-pools.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

