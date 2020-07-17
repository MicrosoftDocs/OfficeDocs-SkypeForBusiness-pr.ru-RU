---
title: Перенос нескольких сайтов и пулов
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
ms.openlocfilehash: bee98cdc88a836be8b629d76b5bed57af402a3ca
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/16/2020
ms.locfileid: "44756588"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migrating-multiple-sites-and-pools"></a><span data-ttu-id="41a30-102">Перенос нескольких сайтов и пулов</span><span class="sxs-lookup"><span data-stu-id="41a30-102">Migrating multiple sites and pools</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="41a30-103">_**Последнее изменение темы:** 2012-09-17_</span><span class="sxs-lookup"><span data-stu-id="41a30-103">_**Topic Last Modified:** 2012-09-17_</span></span>

<span data-ttu-id="41a30-104">Lync Server 2013 поддерживает развертывание с несколькими сайтами и несколькими пулами.</span><span class="sxs-lookup"><span data-stu-id="41a30-104">Lync Server 2013 supports multi-site and multi-pool deployments.</span></span> <span data-ttu-id="41a30-105">Процесс переноса нескольких пулов с Lync Server 2010 на Lync Server 2013 требует следующих факторов:</span><span class="sxs-lookup"><span data-stu-id="41a30-105">The process of migrating multiple pools from Lync Server 2010 to Lync Server 2013 requires the following considerations:</span></span>

1.  <span data-ttu-id="41a30-106">После развертывания пилотного пула Lync Server 2013 необходимо определить подмножество пилотных пользователей, которые будут перемещены в пул Lync Server 2013, и методологию для проверки функциональных возможностей пользователей.</span><span class="sxs-lookup"><span data-stu-id="41a30-106">After deploying a Lync Server 2013 pilot pool, you need to define a subset of pilot users that will be moved to the Lync Server 2013 pool, and a methodology for validating the functionality of the users.</span></span> <span data-ttu-id="41a30-107">Например, после перемещения пользователя в пилотный пул убедитесь, что политика конференции пользователя перемещена в Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="41a30-107">For example, after moving a user to the pilot pool, verify the user’s conference policy has moved to Lync Server 2013.</span></span>

2.  <span data-ttu-id="41a30-108">После развертывания пограничного сервера в пилотном пуле необходимо убедиться, что внешние пользователи могут связываться с пулом Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="41a30-108">After deploying an Edge Server in the pilot pool, you need to validate that external users can communicate with the Lync Server 2013 pool.</span></span>

3.  <span data-ttu-id="41a30-109">После переноса федеративных маршрутов с пограничных серверов Lync Server 2010 на пилотный проект Lync Server 2013 пограничные серверы необходимо проверить, что Федеративные пользователи могут связываться с пулом Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="41a30-109">After transitioning the federated routes from Lync Server 2010 Edge Servers to the pilot Lync Server 2013 Edge Servers, you need to validate that federated users can communicate with the Lync Server 2013 pool.</span></span>

4.  <span data-ttu-id="41a30-110">После перемещения всех пользователей и объектов контактов, не являющихся пользователями, необходимо проверить, что пул Lync Server 2010 не заполнен.</span><span class="sxs-lookup"><span data-stu-id="41a30-110">After moving all the users and non-user contact objects, you need to validate that the Lync Server 2010 pool is empty.</span></span>

5.  <span data-ttu-id="41a30-111">После проверки того, что пул Lync Server 2010 является пустым, вы можете отключить пул.</span><span class="sxs-lookup"><span data-stu-id="41a30-111">After verifying that the Lync Server 2010 pool is empty, you can then deactivate the pool.</span></span>
    
    <span data-ttu-id="41a30-112">Сведения об отключении устаревшего пула и серверов Lync Server 2010 приведены в статье [Этап 8: списание устаревших пулов](phase-8-decommission-legacy-pools.md).</span><span class="sxs-lookup"><span data-stu-id="41a30-112">For details about how to deactivate the legacy Lync Server 2010 pool and servers, see [Phase 8: Decommission legacy pools](phase-8-decommission-legacy-pools.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

