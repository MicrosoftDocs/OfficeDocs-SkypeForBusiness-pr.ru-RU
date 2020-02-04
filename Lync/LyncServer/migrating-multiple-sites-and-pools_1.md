---
title: Перенос нескольких сайтов и пулов
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migrating multiple sites and pools
ms:assetid: 3bf677d4-a5af-4f73-8fad-1abf5b668cc1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688025(v=OCS.15)
ms:contentKeyID: 49733615
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 71ff9164dcd824d6b836577b04783954cb81b067
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41731059"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrating-multiple-sites-and-pools"></a><span data-ttu-id="efa0d-102">Перенос нескольких сайтов и пулов</span><span class="sxs-lookup"><span data-stu-id="efa0d-102">Migrating multiple sites and pools</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="efa0d-103">_**Тема последнего изменения:** 2012-08-26_</span><span class="sxs-lookup"><span data-stu-id="efa0d-103">_**Topic Last Modified:** 2012-08-26_</span></span>

<span data-ttu-id="efa0d-104">Lync Server 2013 поддерживает развертывание с несколькими сайтами и несколькими пулами.</span><span class="sxs-lookup"><span data-stu-id="efa0d-104">Lync Server 2013 supports multi-site and multi-pool deployments.</span></span> <span data-ttu-id="efa0d-105">Процесс миграции нескольких пулов из Office Communications Server 2007 R2 на Lync Server 2013 требует указанных ниже факторов.</span><span class="sxs-lookup"><span data-stu-id="efa0d-105">The process of migrating multiple pools from Office Communications Server 2007 R2 to Lync Server 2013 requires the following considerations:</span></span>

1.  <span data-ttu-id="efa0d-106">После развертывания пула Lync Server 2013 Pilot вы должны определить подмножество пользователей пилотной версии, которые будут перенесены в пул Lync Server 2013, и методологию для проверки функциональных возможностей пользователей.</span><span class="sxs-lookup"><span data-stu-id="efa0d-106">After deploying a Lync Server 2013 pilot pool, you need to define a subset of pilot users that will be moved to the Lync Server 2013 pool, and a methodology for validating the functionality of the users.</span></span>

2.  <span data-ttu-id="efa0d-107">После развертывания пограничного сервера в пилотном пуле необходимо проверить, могут и внешние пользователи взаимодействовать с пулом Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="efa0d-107">After deploying an Edge Server in the pilot pool, you need to validate that external users can communicate with the Lync Server 2013 pool.</span></span>

3.  <span data-ttu-id="efa0d-108">После перевода федеративных маршрутов с Office Communications Server 2007 R2 Edge Server на пробный проект Lync Server 2013 пограничные серверы, вам нужно подтвердить, что Федеративные пользователи смогут взаимодействовать с пулом Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="efa0d-108">After transitioning the federated routes from Office Communications Server 2007 R2 Edge Servers to the pilot Lync Server 2013 Edge Servers, you need to validate that federated users can communicate with the Lync Server 2013 pool.</span></span>

4.  <span data-ttu-id="efa0d-109">После перемещения всех пользователей и объектов контактов, не являющихся пользователями, нужно проверить, что пул Office Communications Server 2007 R2 пуст.</span><span class="sxs-lookup"><span data-stu-id="efa0d-109">After moving all the users and non-user contact objects, you need to validate that the Office Communications Server 2007 R2 pool is empty.</span></span>

5.  <span data-ttu-id="efa0d-110">После того как вы убедитесь в том, что пул Office Communications Server 2007 R2 пуст, вы можете деактивировать пул.</span><span class="sxs-lookup"><span data-stu-id="efa0d-110">After verifying that the Office Communications Server 2007 R2 pool is empty, you can then deactivate the pool.</span></span>
    
    <span data-ttu-id="efa0d-111">Подробнее об отключении устаревшего пула и серверов Office Communications Server 2007 R2 вы можете найти в статье [этап 10: списание устаревшего сайта](phase-10-decommission-legacy-site.md).</span><span class="sxs-lookup"><span data-stu-id="efa0d-111">For details about how to deactivate the legacy Office Communications Server 2007 R2 pool and servers, see [Phase 10: Decommission legacy site](phase-10-decommission-legacy-site.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

