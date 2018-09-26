---
title: Удаление сервера переднего плана из пула
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Сервер переднего плана не могут существовать в качестве изолированный компьютер. Он должен быть определен как пулом переднего плана, даже при наличии только на одном компьютере в пуле.
ms.openlocfilehash: a9f0adc991355b6f79b20365795ffaf92fa230e2
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2018
ms.locfileid: "25028945"
---
# <a name="remove-a-front-end-server-from-a-pool"></a><span data-ttu-id="3b65c-104">Удаление сервера переднего плана из пула</span><span class="sxs-lookup"><span data-stu-id="3b65c-104">Remove a Front End Server from a pool</span></span>

<span data-ttu-id="3b65c-105">Сервер переднего плана не могут существовать в качестве изолированный компьютер.</span><span class="sxs-lookup"><span data-stu-id="3b65c-105">The Front End Server cannot exist as a stand-alone computer.</span></span> <span data-ttu-id="3b65c-106">Он должен быть определен как пулом переднего плана, даже при наличии только на одном компьютере в пуле.</span><span class="sxs-lookup"><span data-stu-id="3b65c-106">It must be defined as a Front End pool, even if there is only a single computer in the pool.</span></span>
  
<span data-ttu-id="3b65c-107">В этом разделе описывается процесс удаления отдельного сервера переднего плана из существующего пула переднего плана.</span><span class="sxs-lookup"><span data-stu-id="3b65c-107">This topic guides you through the process of removing an individual Front End Server from an existing Front End pool.</span></span> <span data-ttu-id="3b65c-108">Если сервер переднего плана — это последний сервер в пуле, а также при удалении пула полностью просмотрите [Удаление интерфейсного пула или сервера Standard Edition](remove-front-end-pool-or-standard-edition-server.md).</span><span class="sxs-lookup"><span data-stu-id="3b65c-108">If the Front End Server is the last server in the pool or if you are removing the pool completely, see [Remove Front End pool or Standard Edition server](remove-front-end-pool-or-standard-edition-server.md).</span></span> <span data-ttu-id="3b65c-109">Нет необходимости для удаления отдельных серверов переднего плана, прежде чем удалять пула переднего плана.</span><span class="sxs-lookup"><span data-stu-id="3b65c-109">There is no need to remove the individual Front End Servers before you remove the Front End pool.</span></span> <span data-ttu-id="3b65c-110">При удалении пула, удалите каждого сервера переднего плана.</span><span class="sxs-lookup"><span data-stu-id="3b65c-110">When you remove the pool, you remove each Front End Server.</span></span>
  
### <a name="to-remove-a-front-end-server-from-a-pool"></a><span data-ttu-id="3b65c-111">Удаление сервера переднего плана из пула</span><span class="sxs-lookup"><span data-stu-id="3b65c-111">To remove a Front End Server from a pool</span></span>

1. <span data-ttu-id="3b65c-112">На Скайп для сервера переднего плана Business Server 2019 откройте построитель топологий.</span><span class="sxs-lookup"><span data-stu-id="3b65c-112">On the Skype for Business Server 2019 Front End Server, open Topology Builder.</span></span>
    
2. <span data-ttu-id="3b65c-113">Перейдите к узлу установки прежних версий.</span><span class="sxs-lookup"><span data-stu-id="3b65c-113">Navigate to the legacy install node.</span></span>
    
3. <span data-ttu-id="3b65c-114">Разверните **Пулы переднего плана Enterprise Edition**, разверните пул переднего плана с сервером переднего плана, которую требуется удалить, щелкните правой кнопкой мыши сервер переднего плана, который требуется удалить и выберите команду **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="3b65c-114">Expand **Enterprise Edition Front End pools**, expand the Front End pool with the Front End Server that you want to remove, right-click the Front End Server that you want to remove, and then click **Delete**.</span></span>
    

