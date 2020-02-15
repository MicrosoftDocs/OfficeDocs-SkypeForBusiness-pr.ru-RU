---
title: Рекомендации по сосуществованию
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Coexistence considerations
ms:assetid: 9d1a3c0f-492a-4e37-bc2f-63509e328785
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205131(v=OCS.15)
ms:contentKeyID: 48184990
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 155e6d07f2e9ccd4315471ca02cd21075b1ded71
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2020
ms.locfileid: "42000894"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="coexistence-considerations"></a><span data-ttu-id="5d655-102">Рекомендации по сосуществованию</span><span class="sxs-lookup"><span data-stu-id="5d655-102">Coexistence considerations</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5d655-103">_**Последнее изменение темы:** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="5d655-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="5d655-104">После миграции будет существовать только сервер Lync Server 2013, пул серверов сохраняемого чата, и вы можете списать устаревшее развертывание.</span><span class="sxs-lookup"><span data-stu-id="5d655-104">After migration, only a Lync Server 2013, Persistent Chat Server pool will exist, and you can decommission your legacy deployment.</span></span>

<span data-ttu-id="5d655-105">Перед завершением миграции и полным списанием текущего развертывания сервера группового чата вы можете использовать любое из следующих развертываний:</span><span class="sxs-lookup"><span data-stu-id="5d655-105">Before migration completes and before you have decommissioned your current Group Chat Server deployment completely, you may have any of the following deployments:</span></span>

  - <span data-ttu-id="5d655-106">Lync Server 2013, пул серверов сохраняемого чата, который должен быть размещен в пуле Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5d655-106">Lync Server 2013, Persistent Chat Server pool, which must be homed on a Lync Server 2013 pool.</span></span>

  - <span data-ttu-id="5d655-107">Lync Server 2010, пул группового чата, который должен быть размещен в пуле Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="5d655-107">Lync Server 2010, Group Chat pool, which must be homed on a Lync Server 2010 pool.</span></span>

  - <span data-ttu-id="5d655-108">Пул группового чата Office Communications Server 2007 R2, который должен быть размещен в пуле Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="5d655-108">Office Communications Server 2007 R2 Group Chat pool, which must be homed on an Office Communications Server 2007 R2 pool.</span></span>

<span data-ttu-id="5d655-p101">Эти развертывания могут существовать параллельно, но категории, комнаты и надстройки в разных развертываниях не могут взаимодействовать между собой.</span><span class="sxs-lookup"><span data-stu-id="5d655-p101">These deployments can exist side by side. However the categories, rooms, and add-ins in one deployment do not interact with those in the accompanying deployment.</span></span>

<span data-ttu-id="5d655-111">При использовании ручной настройки клиент для Office Communications Server 2007 R2, Lync Server 2010, Group Chat или Lync Server 2013 может подключаться к одному пулу за раз.</span><span class="sxs-lookup"><span data-stu-id="5d655-111">Using manual configuration, a legacy client (Group Chat client) can connect to one pool at a time for Office Communications Server 2007 R2, Lync Server 2010, Group Chat, or Lync Server 2013.</span></span>

<span data-ttu-id="5d655-112">Lync 2013 (клиент) может взаимодействовать только с пулом серверов Lync Server 2013, persistent Chat, а не с устаревшими пулами серверов группового чата.</span><span class="sxs-lookup"><span data-stu-id="5d655-112">The Lync 2013 (client) can interact only with the Lync Server 2013, Persistent Chat Server pool, not with legacy Group Chat Server pools.</span></span> <span data-ttu-id="5d655-113">Чтобы использовать сохраняемый чат в Lync 2013 (клиент), пользователь должен быть размещен в Lync 2013 и включен в соответствии с политикой.</span><span class="sxs-lookup"><span data-stu-id="5d655-113">To use Persistent Chat in a Lync 2013 (client), the user must be homed on Lync 2013 and enabled by policy.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

