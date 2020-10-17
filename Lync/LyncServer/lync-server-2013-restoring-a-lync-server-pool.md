---
title: 'Lync Server 2013: восстановление пула Lync Server'
description: 'Lync Server 2013: восстановление пула Lync Server.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Restoring a Lync Server pool
ms:assetid: 6fe80fb3-38ad-4931-a07b-1763b61aa448
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202176(v=OCS.15)
ms:contentKeyID: 51541488
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 02e92b4e7af9cf782d49c265425006e0118b9161
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543815"
---
# <a name="restoring-a-lync-server-pool-in-lync-server-2013"></a><span data-ttu-id="64d88-103">Восстановление пула Lync Server в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="64d88-103">Restoring a Lync Server pool in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="64d88-104">_**Последнее изменение темы:** 2013-02-18_</span><span class="sxs-lookup"><span data-stu-id="64d88-104">_**Topic Last Modified:** 2013-02-18_</span></span>

<span data-ttu-id="64d88-105">Развертывание Lync Server может включать в себя любой из следующих типов пулов:</span><span class="sxs-lookup"><span data-stu-id="64d88-105">Your Lync Server deployment may include any of the following types of pools:</span></span>

  - <span data-ttu-id="64d88-106">Сервер переднего плана</span><span class="sxs-lookup"><span data-stu-id="64d88-106">Front End Server</span></span>

  - <span data-ttu-id="64d88-107">Mediation Server (Сервер-посредник);</span><span class="sxs-lookup"><span data-stu-id="64d88-107">Mediation Server</span></span>

  - <span data-ttu-id="64d88-108">Сервер сохраняемого чата</span><span class="sxs-lookup"><span data-stu-id="64d88-108">Persistent Chat Server</span></span>

  - <span data-ttu-id="64d88-109">Пограничный сервер</span><span class="sxs-lookup"><span data-stu-id="64d88-109">Edge Server</span></span>

<span data-ttu-id="64d88-110">Если происходит сбой всего пула, выполните следующие действия для каждого из рядовых серверов в пуле.</span><span class="sxs-lookup"><span data-stu-id="64d88-110">If an entire pool experiences an outage, follow these procedures for each member server in the pool.</span></span>

  - <span data-ttu-id="64d88-111">Для пула переднего плана сначала восстановите сервер внутреннего сервера, а затем восстановите каждый сервер переднего плана.</span><span class="sxs-lookup"><span data-stu-id="64d88-111">For a Front End pool, restore the Back End Server first, and then restore each Front End Server.</span></span> <span data-ttu-id="64d88-112">Дополнительные сведения приведены [в статье восстановление внутреннего сервера Enterprise Edition в Lync server 2013](lync-server-2013-restoring-an-enterprise-edition-back-end-server.md) и [Восстановление рядового сервера Enterprise Edition в Lync Server 2013](lync-server-2013-restoring-an-enterprise-edition-member-server.md).</span><span class="sxs-lookup"><span data-stu-id="64d88-112">For details, see [Restoring an Enterprise Edition Back End Server in Lync Server 2013](lync-server-2013-restoring-an-enterprise-edition-back-end-server.md) and [Restoring an Enterprise Edition member server in Lync Server 2013](lync-server-2013-restoring-an-enterprise-edition-member-server.md).</span></span>

  - <span data-ttu-id="64d88-113">Для всех остальных типов пулов восстановите каждый сервер участника.</span><span class="sxs-lookup"><span data-stu-id="64d88-113">For all other types of pools, restore each member server.</span></span> <span data-ttu-id="64d88-114">Дополнительную информацию можно узнать [в статье Восстановление рядового сервера Enterprise Edition в Lync server 2013](lync-server-2013-restoring-an-enterprise-edition-member-server.md).</span><span class="sxs-lookup"><span data-stu-id="64d88-114">For details, see [Restoring an Enterprise Edition member server in Lync Server 2013](lync-server-2013-restoring-an-enterprise-edition-member-server.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

