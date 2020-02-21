---
title: 'Lync Server 2013: назначение области действия политики расположения'
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
ms.openlocfilehash: b436c52b89ce9e396d93669c09cdadeef10260e3
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42203295"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="assigning-location-policy-scope-in-lync-server-2013"></a><span data-ttu-id="23999-102">Назначение области действия политики расположения в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="23999-102">Assigning location policy scope in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="23999-103">_**Последнее изменение темы:** 2012-06-06_</span><span class="sxs-lookup"><span data-stu-id="23999-103">_**Topic Last Modified:** 2012-06-06_</span></span>

<span data-ttu-id="23999-104">Как и в случае с другими политиками Lync Server, политики расположения можно назначать на нескольких уровнях областей: глобально, на уровне сайта и на уровне пользователя.</span><span class="sxs-lookup"><span data-stu-id="23999-104">As with other Lync Server policies, location policies can be assigned at multiple scope levels: global, site, and user.</span></span> <span data-ttu-id="23999-105">Однако область применения политик расположений на уровне пользователей немного отличается от других политик Lync Server.</span><span class="sxs-lookup"><span data-stu-id="23999-105">However, the scope of user-level location policies behaves a bit differently than with other Lync Server policies.</span></span> <span data-ttu-id="23999-106">Для объектов конечных точек (таких как пользователи и объекты контактных телефонов общего типа) можно не только применять политики расположения на уровне пользователей, но и на сетевые сайты Lync Server.</span><span class="sxs-lookup"><span data-stu-id="23999-106">Not only can per-user location policies be applied to endpoint objects (such as Users and Common Area Phone contact objects), they can also be applied to Lync Server network sites.</span></span> <span data-ttu-id="23999-107">Сетевые узлы — это группы клиентских подсетей, связанных с географическим расположением (но это необязательно все подсети во всем центральном узле или узле филиала).</span><span class="sxs-lookup"><span data-stu-id="23999-107">Network sites are groupings of client subnets associated with a geographical location (but may not necessarily be all subnets in an entire central site or branch site).</span></span> <span data-ttu-id="23999-108">Все клиенты, подключенные к подсетям в сетевом узле, автоматически применяют политику местоположения, назначенную этому сетевому узлу.</span><span class="sxs-lookup"><span data-stu-id="23999-108">Any clients connected to the subnets in a network site automatically pick up the location policy assigned to that network site.</span></span> <span data-ttu-id="23999-109">Если политика местоположения на уровне пользователя назначена пользователю и сетевому узлу, то политика местоположения сетевого узла имеет более высокий приоритет, чем политика на уровне пользователя.</span><span class="sxs-lookup"><span data-stu-id="23999-109">In cases where a user-level location policy is assigned both to a user and to a network site, the network site-based location policy overrides any per-user policy setting.</span></span>

<span data-ttu-id="23999-110">Каждому сетевому узлу назначена политика местоположения, а каждой политике назначены разные значения использования ТСОП, URI уведомлений и URI конференций.</span><span class="sxs-lookup"><span data-stu-id="23999-110">Each network site has a location policy assigned to it, and each policy will have different PSTN Usages, Notification URIs, and Conference URIs values assigned to it.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="23999-111">Такое поведение области политики используется для того, чтобы когда пользователь, размещенный в пуле в одном узле, посещал другой узел и совершал экстренный вызов, применялись параметры маршрутизации вызовов E9-1-1, соответствующие этому сетевому узлу, независимо от того, какому узлу или пулу назначен пользователь.</span><span class="sxs-lookup"><span data-stu-id="23999-111">The reason for this special policy scoping behavior is so that when a user homed on a pool at one office site visits another site and has to make an emergency call, the E9-1-1 call routing settings appropriate to that network site will apply no matter what pool or site the user is assigned to.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

