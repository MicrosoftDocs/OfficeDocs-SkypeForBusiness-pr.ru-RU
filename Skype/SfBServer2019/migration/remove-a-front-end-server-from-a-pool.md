---
title: Удаление сервера переднего плана из пула
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Сервер переднего сервера не может существовать как автономный компьютер. Его необходимо определить как пул переднего входа, даже если в пуле имеется только один компьютер.
ms.openlocfilehash: 7675ba119fa2937d765d5f4e497fca0a040b3b62
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752321"
---
# <a name="remove-a-front-end-server-from-a-pool"></a><span data-ttu-id="829a9-104">Удаление сервера переднего плана из пула</span><span class="sxs-lookup"><span data-stu-id="829a9-104">Remove a Front End Server from a pool</span></span>

<span data-ttu-id="829a9-105">Сервер переднего сервера не может существовать как автономный компьютер.</span><span class="sxs-lookup"><span data-stu-id="829a9-105">The Front End Server cannot exist as a stand-alone computer.</span></span> <span data-ttu-id="829a9-106">Его необходимо определить как пул переднего входа, даже если в пуле имеется только один компьютер.</span><span class="sxs-lookup"><span data-stu-id="829a9-106">It must be defined as a Front End pool, even if there is only a single computer in the pool.</span></span>
  
<span data-ttu-id="829a9-107">В этом разделе вы можете удалить отдельный сервер переднего сервера из существующего пула переднего сервера.</span><span class="sxs-lookup"><span data-stu-id="829a9-107">This topic guides you through the process of removing an individual Front End Server from an existing Front End pool.</span></span> <span data-ttu-id="829a9-108">Если сервер переднего сервера является последним сервером в пуле или пул полностью удаляется, см. "Удаление пула переднего сервера" или сервера [Standard Edition.](remove-front-end-pool-or-standard-edition-server.md)</span><span class="sxs-lookup"><span data-stu-id="829a9-108">If the Front End Server is the last server in the pool or if you are removing the pool completely, see [Remove Front End pool or Standard Edition server](remove-front-end-pool-or-standard-edition-server.md).</span></span> <span data-ttu-id="829a9-109">Нет необходимости удалять отдельные серверы переднего сервера перед удалением пула переднего сервера.</span><span class="sxs-lookup"><span data-stu-id="829a9-109">There is no need to remove the individual Front End Servers before you remove the Front End pool.</span></span> <span data-ttu-id="829a9-110">При удалите пул, удалите каждый сервер переднего сервера.</span><span class="sxs-lookup"><span data-stu-id="829a9-110">When you remove the pool, you remove each Front End Server.</span></span>
  
### <a name="to-remove-a-front-end-server-from-a-pool"></a><span data-ttu-id="829a9-111">Удаление сервера переднего плана из пула</span><span class="sxs-lookup"><span data-stu-id="829a9-111">To remove a Front End Server from a pool</span></span>

1. <span data-ttu-id="829a9-112">On the Skype for Business Server 2019 Front End Server, open Topology Builder.</span><span class="sxs-lookup"><span data-stu-id="829a9-112">On the Skype for Business Server 2019 Front End Server, open Topology Builder.</span></span>
    
2. <span data-ttu-id="829a9-113">Перейдите к устаревшему узлу установки.</span><span class="sxs-lookup"><span data-stu-id="829a9-113">Navigate to the legacy install node.</span></span>
    
3. <span data-ttu-id="829a9-114">Развернув пулы переднего сервера **Enterprise Edition,** развернув пул переднего сервера с сервером переднего сервера, который нужно удалить, щелкните правой кнопкой мыши сервер переднего сервера, который нужно удалить, и выберите "Удалить". </span><span class="sxs-lookup"><span data-stu-id="829a9-114">Expand **Enterprise Edition Front End pools**, expand the Front End pool with the Front End Server that you want to remove, right-click the Front End Server that you want to remove, and then click **Delete**.</span></span>
    

