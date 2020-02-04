---
title: 'Lync Server 2013: назначение области политики расположения'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assigning location policy scope
ms:assetid: e4c66517-c593-4253-b900-7b4dd8bddf2f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205360(v=OCS.15)
ms:contentKeyID: 48185734
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 395b8a4271338231b4c2c1927f7e40fb21a1cb14
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734029"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="assigning-location-policy-scope-in-lync-server-2013"></a><span data-ttu-id="2a559-102">Назначение области политики расположения в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2a559-102">Assigning location policy scope in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2a559-103">_**Тема последнего изменения:** 2012-06-06_</span><span class="sxs-lookup"><span data-stu-id="2a559-103">_**Topic Last Modified:** 2012-06-06_</span></span>

<span data-ttu-id="2a559-104">Как и другие политики сервера Lync, политики расположения можно назначать на нескольких уровнях областей: глобальном, сайте и пользовательском.</span><span class="sxs-lookup"><span data-stu-id="2a559-104">As with other Lync Server policies, location policies can be assigned at multiple scope levels: global, site, and user.</span></span> <span data-ttu-id="2a559-105">Тем не менее область действия политик расположения на уровне пользователя не отличается от других политик Lync Server.</span><span class="sxs-lookup"><span data-stu-id="2a559-105">However, the scope of user-level location policies behaves a bit differently than with other Lync Server policies.</span></span> <span data-ttu-id="2a559-106">К объектам конечных точек (например, пользователям и контактам по распространенным телефонным объектам) можно применять не только политики местоположения пользователей, но и их также для сетевых сайтов Lync Server.</span><span class="sxs-lookup"><span data-stu-id="2a559-106">Not only can per-user location policies be applied to endpoint objects (such as Users and Common Area Phone contact objects), they can also be applied to Lync Server network sites.</span></span> <span data-ttu-id="2a559-107">Сетевые сайты — это группы клиентских подсетей, связанных с географическим расположением (но это необязательно все подсети на всем центральном сайте или сайте филиала).</span><span class="sxs-lookup"><span data-stu-id="2a559-107">Network sites are groupings of client subnets associated with a geographical location (but may not necessarily be all subnets in an entire central site or branch site).</span></span> <span data-ttu-id="2a559-108">Все клиенты, подключенные к подсетям на сетевом сайте, автоматически применяют политику расположения, назначенную этому сетевому сайту.</span><span class="sxs-lookup"><span data-stu-id="2a559-108">Any clients connected to the subnets in a network site automatically pick up the location policy assigned to that network site.</span></span> <span data-ttu-id="2a559-109">Если политика расположения на уровне пользователя назначена пользователю и сетевому сайту, то политика расположения сетевого сайта имеет более высокий приоритет, чем политика на уровне пользователя.</span><span class="sxs-lookup"><span data-stu-id="2a559-109">In cases where a user-level location policy is assigned both to a user and to a network site, the network site-based location policy overrides any per-user policy setting.</span></span>

<span data-ttu-id="2a559-110">Каждому сетевому сайту назначена политика расположения, а каждой политике назначены разные значения использования ТСОП, URI уведомлений и URI конференций.</span><span class="sxs-lookup"><span data-stu-id="2a559-110">Each network site has a location policy assigned to it, and each policy will have different PSTN Usages, Notification URIs, and Conference URIs values assigned to it.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="2a559-111">Такое поведение области политики используется для того, чтобы когда пользователь, размещенный в пуле на одном сайте, посещал другой сайт и совершал экстренный вызов, применялись параметры маршрутизации вызовов E9-1-1, соответствующие этому сетевому сайту, независимо от того, какому сайту или пулу назначен пользователь.</span><span class="sxs-lookup"><span data-stu-id="2a559-111">The reason for this special policy scoping behavior is so that when a user homed on a pool at one office site visits another site and has to make an emergency call, the E9-1-1 call routing settings appropriate to that network site will apply no matter what pool or site the user is assigned to.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

