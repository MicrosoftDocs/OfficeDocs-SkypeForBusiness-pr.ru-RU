---
title: Удаление сервера переднего плана из пула
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Сервер переднего плана не может быть автономным компьютером. Он должен быть определен как пул переднего плана, даже если в пуле есть только один компьютер.
ms.openlocfilehash: 64f0c4134f690005815591bce88b8d058c1bd007
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/07/2019
ms.locfileid: "36244297"
---
# <a name="remove-a-front-end-server-from-a-pool"></a><span data-ttu-id="b3ab1-104">Удаление сервера переднего плана из пула</span><span class="sxs-lookup"><span data-stu-id="b3ab1-104">Remove a Front End Server from a pool</span></span>

<span data-ttu-id="b3ab1-105">Сервер переднего плана не может быть автономным компьютером.</span><span class="sxs-lookup"><span data-stu-id="b3ab1-105">The Front End Server cannot exist as a stand-alone computer.</span></span> <span data-ttu-id="b3ab1-106">Он должен быть определен как пул переднего плана, даже если в пуле есть только один компьютер.</span><span class="sxs-lookup"><span data-stu-id="b3ab1-106">It must be defined as a Front End pool, even if there is only a single computer in the pool.</span></span>
  
<span data-ttu-id="b3ab1-107">В этой статье описывается процесс удаления отдельного сервера переднего плана из существующего пула переднего плана.</span><span class="sxs-lookup"><span data-stu-id="b3ab1-107">This topic guides you through the process of removing an individual Front End Server from an existing Front End pool.</span></span> <span data-ttu-id="b3ab1-108">Если сервер переднего плана является последним в пуле или полностью удален, ознакомьтесь со сведениями [Удаление пула переднего плана или сервера Standard Edition](remove-front-end-pool-or-standard-edition-server.md).</span><span class="sxs-lookup"><span data-stu-id="b3ab1-108">If the Front End Server is the last server in the pool or if you are removing the pool completely, see [Remove Front End pool or Standard Edition server](remove-front-end-pool-or-standard-edition-server.md).</span></span> <span data-ttu-id="b3ab1-109">Перед удалением пула переднего плана вам не нужно удалять отдельные серверы переднего плана.</span><span class="sxs-lookup"><span data-stu-id="b3ab1-109">There is no need to remove the individual Front End Servers before you remove the Front End pool.</span></span> <span data-ttu-id="b3ab1-110">При удалении пула удаляется каждый сервер переднего плана.</span><span class="sxs-lookup"><span data-stu-id="b3ab1-110">When you remove the pool, you remove each Front End Server.</span></span>
  
### <a name="to-remove-a-front-end-server-from-a-pool"></a><span data-ttu-id="b3ab1-111">Удаление сервера переднего плана из пула</span><span class="sxs-lookup"><span data-stu-id="b3ab1-111">To remove a Front End Server from a pool</span></span>

1. <span data-ttu-id="b3ab1-112">На сервере клиентского доступа Skype для бизнеса Server 2019 откройте конфигуратор топологии.</span><span class="sxs-lookup"><span data-stu-id="b3ab1-112">On the Skype for Business Server 2019 Front End Server, open Topology Builder.</span></span>
    
2. <span data-ttu-id="b3ab1-113">Перейдите к устаревшему узлу установки.</span><span class="sxs-lookup"><span data-stu-id="b3ab1-113">Navigate to the legacy install node.</span></span>
    
3. <span data-ttu-id="b3ab1-114">Разверните **Пулы переднего плана Enterprise Edition**, разверните пул переднего плана с сервером переднего плана, который вы хотите удалить, щелкните правой кнопкой мыши сервер переднего плана, который вы хотите удалить, и выберите команду **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="b3ab1-114">Expand **Enterprise Edition Front End pools**, expand the Front End pool with the Front End Server that you want to remove, right-click the Front End Server that you want to remove, and then click **Delete**.</span></span>
    

