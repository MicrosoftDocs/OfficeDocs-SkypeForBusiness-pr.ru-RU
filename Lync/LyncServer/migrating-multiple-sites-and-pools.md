---
title: Перенос нескольких сайтов и пулов
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Migrating multiple sites and pools
ms:assetid: a6d726d2-564d-4b39-a97c-5656a673292a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205165(v=OCS.15)
ms:contentKeyID: 48185079
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c7759c52051dfe4ca4a46e105e6a33f3284f334e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849011"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrating-multiple-sites-and-pools"></a><span data-ttu-id="a22e4-102">Перенос нескольких сайтов и пулов</span><span class="sxs-lookup"><span data-stu-id="a22e4-102">Migrating multiple sites and pools</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a22e4-103">_**Тема последнего изменения:** 2012-09-17_</span><span class="sxs-lookup"><span data-stu-id="a22e4-103">_**Topic Last Modified:** 2012-09-17_</span></span>

<span data-ttu-id="a22e4-104">Lync Server 2013 поддерживает развертывание с несколькими сайтами и несколькими пулами.</span><span class="sxs-lookup"><span data-stu-id="a22e4-104">Lync Server 2013 supports multi-site and multi-pool deployments.</span></span> <span data-ttu-id="a22e4-105">Процесс миграции нескольких пулов с Lync Server 2010 на Lync Server 2013 требует указанных ниже факторов.</span><span class="sxs-lookup"><span data-stu-id="a22e4-105">The process of migrating multiple pools from Lync Server 2010 to Lync Server 2013 requires the following considerations:</span></span>

1.  <span data-ttu-id="a22e4-106">После развертывания пула Lync Server 2013 Pilot вы должны определить подмножество пользователей пилотной версии, которые будут перенесены в пул Lync Server 2013, и методологию для проверки функциональных возможностей пользователей.</span><span class="sxs-lookup"><span data-stu-id="a22e4-106">After deploying a Lync Server 2013 pilot pool, you need to define a subset of pilot users that will be moved to the Lync Server 2013 pool, and a methodology for validating the functionality of the users.</span></span> <span data-ttu-id="a22e4-107">Например, после перемещения пользователя в пилотный пул убедитесь, что политика конференции пользователя перешла на Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a22e4-107">For example, after moving a user to the pilot pool, verify the user’s conference policy has moved to Lync Server 2013.</span></span>

2.  <span data-ttu-id="a22e4-108">После развертывания пограничного сервера в пилотном пуле необходимо проверить, могут и внешние пользователи взаимодействовать с пулом Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a22e4-108">After deploying an Edge Server in the pilot pool, you need to validate that external users can communicate with the Lync Server 2013 pool.</span></span>

3.  <span data-ttu-id="a22e4-109">После перевода федеративных маршрутов с сервера Lync Server 2010 EDGE на пробную подложку Lync Server 2013 Edges необходимо проверить, что Федеративные пользователи смогут взаимодействовать с пулом Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a22e4-109">After transitioning the federated routes from Lync Server 2010 Edge Servers to the pilot Lync Server 2013 Edge Servers, you need to validate that federated users can communicate with the Lync Server 2013 pool.</span></span>

4.  <span data-ttu-id="a22e4-110">После перемещения всех пользователей и объектов контактных лиц, не являющихся пользователями, необходимо проверить, что пул Lync Server 2010 пуст.</span><span class="sxs-lookup"><span data-stu-id="a22e4-110">After moving all the users and non-user contact objects, you need to validate that the Lync Server 2010 pool is empty.</span></span>

5.  <span data-ttu-id="a22e4-111">После того как вы убедитесь в том, что пул Lync Server 2010 пуст, вы можете деактивировать пул.</span><span class="sxs-lookup"><span data-stu-id="a22e4-111">After verifying that the Lync Server 2010 pool is empty, you can then deactivate the pool.</span></span>
    
    <span data-ttu-id="a22e4-112">Подробнее об отключении устаревшего пула и серверов Lync Server 2010 вы можете найти в разделе [Этап 8: списание стандартных пулов](phase-8-decommission-legacy-pools.md).</span><span class="sxs-lookup"><span data-stu-id="a22e4-112">For details about how to deactivate the legacy Lync Server 2010 pool and servers, see [Phase 8: Decommission legacy pools](phase-8-decommission-legacy-pools.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

