---
title: Удаление сервера переднего плана из пула
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Remove a Front End Server from a pool
ms:assetid: 767225c9-7c0b-4d54-a407-d77134ba2abe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688095(v=OCS.15)
ms:contentKeyID: 49733694
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e0637754c6e7b1a03c233025703297c182dc3099
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41727319"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="remove-a-front-end-server-from-a-pool"></a><span data-ttu-id="75f10-102">Удаление сервера переднего плана из пула</span><span class="sxs-lookup"><span data-stu-id="75f10-102">Remove a Front End Server from a pool</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="75f10-103">_**Тема последнего изменения:** 2012-10-04_</span><span class="sxs-lookup"><span data-stu-id="75f10-103">_**Topic Last Modified:** 2012-10-04_</span></span>

<span data-ttu-id="75f10-104">Сервер переднего плана Microsoft Lync Server 2010 Enterprise Edition не может существовать как автономный компьютер.</span><span class="sxs-lookup"><span data-stu-id="75f10-104">The Microsoft Lync Server 2010 Enterprise Edition Front End Server cannot exist as a stand-alone computer.</span></span> <span data-ttu-id="75f10-105">Он должен быть определен как пул переднего плана, даже если в пуле есть только один компьютер.</span><span class="sxs-lookup"><span data-stu-id="75f10-105">It must be defined as a Front End pool, even if there is only a single computer in the pool.</span></span>

<span data-ttu-id="75f10-106">В этой статье описывается процесс удаления отдельного сервера переднего плана из существующего пула переднего плана.</span><span class="sxs-lookup"><span data-stu-id="75f10-106">This topic guides you through the process of removing an individual Front End Server from an existing Front End pool.</span></span> <span data-ttu-id="75f10-107">Если сервер переднего плана является последним в пуле или полностью удален, ознакомьтесь со сведениями [Удаление пула переднего плана или сервера Standard Edition](remove-front-end-pool-or-standard-edition-server.md).</span><span class="sxs-lookup"><span data-stu-id="75f10-107">If the Front End Server is the last server in the pool or if you are removing the pool completely, see [Remove Front End pool or Standard Edition server](remove-front-end-pool-or-standard-edition-server.md).</span></span> <span data-ttu-id="75f10-108">Перед удалением пула переднего плана вам не нужно удалять отдельные серверы переднего плана.</span><span class="sxs-lookup"><span data-stu-id="75f10-108">There is no need to remove the individual Front End Servers before you remove the Front End pool.</span></span> <span data-ttu-id="75f10-109">При удалении пула удаляется каждый сервер переднего плана.</span><span class="sxs-lookup"><span data-stu-id="75f10-109">When you remove the pool, you remove each Front End Server.</span></span>

<div>

## <a name="to-remove-a-front-end-server-from-a-pool"></a><span data-ttu-id="75f10-110">Удаление сервера переднего плана из пула</span><span class="sxs-lookup"><span data-stu-id="75f10-110">To remove a Front End Server from a pool</span></span>

1.  <span data-ttu-id="75f10-111">Откройте сервер клиентского доступа Lync Server 2013, откройте построитель топологии.</span><span class="sxs-lookup"><span data-stu-id="75f10-111">Open the Lync Server 2013 Front End Server, open Topology Builder.</span></span>

2.  <span data-ttu-id="75f10-112">Перейдите на узел Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="75f10-112">Navigate to the Lync Server 2010 node.</span></span>

3.  <span data-ttu-id="75f10-113">Разверните **Пулы переднего плана Enterprise Edition**, разверните пул переднего плана с сервером переднего плана, который вы хотите удалить, щелкните правой кнопкой мыши сервер переднего плана, который вы хотите удалить, и выберите команду **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="75f10-113">Expand **Enterprise Edition Front End pools**, expand the Front End pool with the Front End Server that you want to remove, right-click the Front End Server that you want to remove, and then click **Delete**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

