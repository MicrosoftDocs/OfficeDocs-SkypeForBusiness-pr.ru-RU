---
title: 'Lync Server 2013: восстановление пула сервера Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Restoring a Lync Server pool
ms:assetid: 6fe80fb3-38ad-4931-a07b-1763b61aa448
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202176(v=OCS.15)
ms:contentKeyID: 51541488
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4035ddb27b77e165d612be9e35cbb02970892c8b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823058"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="restoring-a-lync-server-pool-in-lync-server-2013"></a><span data-ttu-id="a6fa6-102">Восстановление пула сервера Lync Server в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a6fa6-102">Restoring a Lync Server pool in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a6fa6-103">_**Тема последнего изменения:** 2013-02-18_</span><span class="sxs-lookup"><span data-stu-id="a6fa6-103">_**Topic Last Modified:** 2013-02-18_</span></span>

<span data-ttu-id="a6fa6-104">Развертывание Lync Server может включать следующие типы пулов:</span><span class="sxs-lookup"><span data-stu-id="a6fa6-104">Your Lync Server deployment may include any of the following types of pools:</span></span>

  - <span data-ttu-id="a6fa6-105">переднего плана</span><span class="sxs-lookup"><span data-stu-id="a6fa6-105">Front End Server</span></span>

  - <span data-ttu-id="a6fa6-106">посредник</span><span class="sxs-lookup"><span data-stu-id="a6fa6-106">Mediation Server</span></span>

  - <span data-ttu-id="a6fa6-107">Сервер сохраняемого чата</span><span class="sxs-lookup"><span data-stu-id="a6fa6-107">Persistent Chat Server</span></span>

  - <span data-ttu-id="a6fa6-108">пограничный сервер</span><span class="sxs-lookup"><span data-stu-id="a6fa6-108">Edge Server</span></span>

<span data-ttu-id="a6fa6-109">Если в пуле всего происходит отключение, выполните следующие действия для каждого сервера в пуле.</span><span class="sxs-lookup"><span data-stu-id="a6fa6-109">If an entire pool experiences an outage, follow these procedures for each member server in the pool.</span></span>

  - <span data-ttu-id="a6fa6-110">Для пула переднего плана сначала восстановите сервер обратного доступа, а затем восстановите каждый сервер переднего плана.</span><span class="sxs-lookup"><span data-stu-id="a6fa6-110">For a Front End pool, restore the Back End Server first, and then restore each Front End Server.</span></span> <span data-ttu-id="a6fa6-111">Дополнительные сведения можно найти [в разделе Восстановление сервера выпуска Enterprise Edition в Lync server 2013](lync-server-2013-restoring-an-enterprise-edition-back-end-server.md) и [Восстановление рядового сервера Enterprise Edition в Lync Server 2013](lync-server-2013-restoring-an-enterprise-edition-member-server.md).</span><span class="sxs-lookup"><span data-stu-id="a6fa6-111">For details, see [Restoring an Enterprise Edition Back End Server in Lync Server 2013](lync-server-2013-restoring-an-enterprise-edition-back-end-server.md) and [Restoring an Enterprise Edition member server in Lync Server 2013](lync-server-2013-restoring-an-enterprise-edition-member-server.md).</span></span>

  - <span data-ttu-id="a6fa6-112">Для всех остальных типов пулов, восстановите каждый сервер участника.</span><span class="sxs-lookup"><span data-stu-id="a6fa6-112">For all other types of pools, restore each member server.</span></span> <span data-ttu-id="a6fa6-113">Подробные сведения можно найти [в разделе Восстановление сервера в составе корпоративного выпуска Lync server 2013](lync-server-2013-restoring-an-enterprise-edition-member-server.md).</span><span class="sxs-lookup"><span data-stu-id="a6fa6-113">For details, see [Restoring an Enterprise Edition member server in Lync Server 2013](lync-server-2013-restoring-an-enterprise-edition-member-server.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

