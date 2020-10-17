---
title: Удаление сервера переднего плана из пула
description: Удаление сервера переднего плана из пула.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Remove a Front End Server from a pool
ms:assetid: 767225c9-7c0b-4d54-a407-d77134ba2abe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688095(v=OCS.15)
ms:contentKeyID: 49733694
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 45560a6f43288b47c0f85f880a190e31f2c8c04d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48551305"
---
# <a name="remove-a-front-end-server-from-a-pool"></a><span data-ttu-id="8303f-103">Удаление сервера переднего плана из пула</span><span class="sxs-lookup"><span data-stu-id="8303f-103">Remove a Front End Server from a pool</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8303f-104">_**Последнее изменение темы:** 2012-10-04_</span><span class="sxs-lookup"><span data-stu-id="8303f-104">_**Topic Last Modified:** 2012-10-04_</span></span>

<span data-ttu-id="8303f-105">Сервер переднего плана Microsoft Lync Server 2010 Enterprise Edition не может существовать как изолированный компьютер.</span><span class="sxs-lookup"><span data-stu-id="8303f-105">The Microsoft Lync Server 2010 Enterprise Edition Front End Server cannot exist as a stand-alone computer.</span></span> <span data-ttu-id="8303f-106">Он должен быть определен как интерфейсный пул, даже если в пуле только один компьютер.</span><span class="sxs-lookup"><span data-stu-id="8303f-106">It must be defined as a Front End pool, even if there is only a single computer in the pool.</span></span>

<span data-ttu-id="8303f-107">В этом разделе описывается процесс удаления отдельного сервера переднего плана из существующего интерфейсного пула.</span><span class="sxs-lookup"><span data-stu-id="8303f-107">This topic guides you through the process of removing an individual Front End Server from an existing Front End pool.</span></span> <span data-ttu-id="8303f-108">Если сервер переднего плана является последним в пуле или если вы полностью удаляете пул, обратитесь к разделу [Удаление пула переднего плана или сервера Standard Edition](remove-front-end-pool-or-standard-edition-server.md).</span><span class="sxs-lookup"><span data-stu-id="8303f-108">If the Front End Server is the last server in the pool or if you are removing the pool completely, see [Remove Front End pool or Standard Edition server](remove-front-end-pool-or-standard-edition-server.md).</span></span> <span data-ttu-id="8303f-109">Перед удалением интерфейсного пула нет необходимости удалять отдельные серверы переднего плана.</span><span class="sxs-lookup"><span data-stu-id="8303f-109">There is no need to remove the individual Front End Servers before you remove the Front End pool.</span></span> <span data-ttu-id="8303f-110">При удалении пула необходимо удалить все серверы переднего плана.</span><span class="sxs-lookup"><span data-stu-id="8303f-110">When you remove the pool, you remove each Front End Server.</span></span>

<div>

## <a name="to-remove-a-front-end-server-from-a-pool"></a><span data-ttu-id="8303f-111">Удаление сервера переднего плана из пула</span><span class="sxs-lookup"><span data-stu-id="8303f-111">To remove a Front End Server from a pool</span></span>

1.  <span data-ttu-id="8303f-112">Откройте сервер переднего плана Lync Server 2013, откройте построитель топологий.</span><span class="sxs-lookup"><span data-stu-id="8303f-112">Open the Lync Server 2013 Front End Server, open Topology Builder.</span></span>

2.  <span data-ttu-id="8303f-113">Перейдите к узлу Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="8303f-113">Navigate to the Lync Server 2010 node.</span></span>

3.  <span data-ttu-id="8303f-114">Разверните **Пулы переднего плана Enterprise Edition**, разверните пул переднего плана с сервером переднего плана, который требуется удалить, щелкните правой кнопкой мыши сервер переднего плана, который нужно удалить, и выберите команду **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="8303f-114">Expand **Enterprise Edition Front End pools**, expand the Front End pool with the Front End Server that you want to remove, right-click the Front End Server that you want to remove, and then click **Delete**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

