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
description: Сервер переднего плана не может существовать как изолированный компьютер. Он должен быть определен как интерфейсный пул, даже если в пуле только один компьютер.
ms.openlocfilehash: 7675ba119fa2937d765d5f4e497fca0a040b3b62
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752321"
---
# <a name="remove-a-front-end-server-from-a-pool"></a><span data-ttu-id="bf30e-104">Удаление сервера переднего плана из пула</span><span class="sxs-lookup"><span data-stu-id="bf30e-104">Remove a Front End Server from a pool</span></span>

<span data-ttu-id="bf30e-105">Сервер переднего плана не может существовать как изолированный компьютер.</span><span class="sxs-lookup"><span data-stu-id="bf30e-105">The Front End Server cannot exist as a stand-alone computer.</span></span> <span data-ttu-id="bf30e-106">Он должен быть определен как интерфейсный пул, даже если в пуле только один компьютер.</span><span class="sxs-lookup"><span data-stu-id="bf30e-106">It must be defined as a Front End pool, even if there is only a single computer in the pool.</span></span>
  
<span data-ttu-id="bf30e-107">В этом разделе описывается процесс удаления отдельного сервера переднего плана из существующего интерфейсного пула.</span><span class="sxs-lookup"><span data-stu-id="bf30e-107">This topic guides you through the process of removing an individual Front End Server from an existing Front End pool.</span></span> <span data-ttu-id="bf30e-108">Если сервер переднего плана является последним в пуле или если вы полностью удаляете пул, обратитесь к разделу [Удаление пула переднего плана или сервера Standard Edition](remove-front-end-pool-or-standard-edition-server.md).</span><span class="sxs-lookup"><span data-stu-id="bf30e-108">If the Front End Server is the last server in the pool or if you are removing the pool completely, see [Remove Front End pool or Standard Edition server](remove-front-end-pool-or-standard-edition-server.md).</span></span> <span data-ttu-id="bf30e-109">Перед удалением интерфейсного пула нет необходимости удалять отдельные серверы переднего плана.</span><span class="sxs-lookup"><span data-stu-id="bf30e-109">There is no need to remove the individual Front End Servers before you remove the Front End pool.</span></span> <span data-ttu-id="bf30e-110">При удалении пула необходимо удалить все серверы переднего плана.</span><span class="sxs-lookup"><span data-stu-id="bf30e-110">When you remove the pool, you remove each Front End Server.</span></span>
  
### <a name="to-remove-a-front-end-server-from-a-pool"></a><span data-ttu-id="bf30e-111">Удаление сервера переднего плана из пула</span><span class="sxs-lookup"><span data-stu-id="bf30e-111">To remove a Front End Server from a pool</span></span>

1. <span data-ttu-id="bf30e-112">На сервере переднего плана Skype для бизнеса Server 2019 откройте построитель топологий.</span><span class="sxs-lookup"><span data-stu-id="bf30e-112">On the Skype for Business Server 2019 Front End Server, open Topology Builder.</span></span>
    
2. <span data-ttu-id="bf30e-113">Перейдите к устаревшему узлу установки.</span><span class="sxs-lookup"><span data-stu-id="bf30e-113">Navigate to the legacy install node.</span></span>
    
3. <span data-ttu-id="bf30e-114">Разверните **Пулы переднего плана Enterprise Edition**, разверните пул переднего плана с сервером переднего плана, который требуется удалить, щелкните правой кнопкой мыши сервер переднего плана, который нужно удалить, и выберите команду **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="bf30e-114">Expand **Enterprise Edition Front End pools**, expand the Front End pool with the Front End Server that you want to remove, right-click the Front End Server that you want to remove, and then click **Delete**.</span></span>
    

