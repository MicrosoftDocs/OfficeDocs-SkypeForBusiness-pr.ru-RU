---
title: Перенос нескольких сайтов и пулов
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
description: 'Skype для бизнеса Server 2019 поддерживает развертывание с несколькими сайтами и несколькими пулами. Процесс переноса нескольких пулов в Skype для бизнеса Server 2019 требует следующих факторов:'
ms.openlocfilehash: 4906b05138d546e685a06acecc4f7adc4e88516e
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752661"
---
# <a name="migrating-multiple-sites-and-pools"></a><span data-ttu-id="31613-104">Перенос нескольких сайтов и пулов</span><span class="sxs-lookup"><span data-stu-id="31613-104">Migrating multiple sites and pools</span></span>

<span data-ttu-id="31613-105">Skype для бизнеса Server 2019 поддерживает развертывание с несколькими сайтами и несколькими пулами.</span><span class="sxs-lookup"><span data-stu-id="31613-105">Skype for Business Server 2019 supports multi-site and multi-pool deployments.</span></span> <span data-ttu-id="31613-106">Процесс переноса нескольких пулов в Skype для бизнеса Server 2019 требует следующих факторов:</span><span class="sxs-lookup"><span data-stu-id="31613-106">The process of migrating multiple pools to Skype for Business Server 2019 requires the following considerations:</span></span> 
  
1. <span data-ttu-id="31613-107">After deploying a Skype for Business Server 2019 pilot pool, you need to define a subset of pilot users that will be moved to the Skype for Business Server 2019 pool, and a methodology for validating the functionality of the users.</span><span class="sxs-lookup"><span data-stu-id="31613-107">After deploying a Skype for Business Server 2019 pilot pool, you need to define a subset of pilot users that will be moved to the Skype for Business Server 2019 pool, and a methodology for validating the functionality of the users.</span></span> <span data-ttu-id="31613-108">Например, после перемещения пользователя в пилотный пул убедитесь, что политика конференций пользователя перемещена в Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="31613-108">For example, after moving a user to the pilot pool, verify that the user's conference policy has moved to Skype for Business Server 2019.</span></span> 
    
2. <span data-ttu-id="31613-109">After deploying an Edge Server in the pilot pool, you need to validate that external users can communicate with the Skype for Business Server 2019 pool.</span><span class="sxs-lookup"><span data-stu-id="31613-109">After deploying an Edge Server in the pilot pool, you need to validate that external users can communicate with the Skype for Business Server 2019 pool.</span></span>

3. <span data-ttu-id="31613-110">Функции сохраняемого чата, зеркального SQL и XMPP не являются устаревшими в Skype для бизнеса Server 2019 и больше не доступны в качестве функций Skype для бизнеса Server 2019, но их можно продолжить в среде сосуществования, если они ранее были развернуты в устаревшей среде.</span><span class="sxs-lookup"><span data-stu-id="31613-110">Persistent Chat, SQL Mirroring, and XMPP functionality are deprecated in Skype for Business Server 2019 and no longer available as Skype for Business Server 2019 features, but they can be continued in a coexistence environment if they were previously deployed in a legacy environment.</span></span> <span data-ttu-id="31613-111">Если вы хотите продолжать использовать эти функции, следует запланировать продолжение работы в среде сосуществования, в которой некоторые пользователи останутся в устаревших пулах.</span><span class="sxs-lookup"><span data-stu-id="31613-111">If you want to continue using these features, you should plan to continue with a coexistence environment where certain users will remain in legacy pools.</span></span>
    
4. <span data-ttu-id="31613-112">After transitioning the federated routes' Edge Servers to the pilot Skype for Business Server 2019 Edge Server, you need to validate that federated users can communicate with the Skype for Business Server 2019 pool.</span><span class="sxs-lookup"><span data-stu-id="31613-112">After transitioning the federated routes' Edge Servers to the pilot Skype for Business Server 2019 Edge Servers, you need to validate that federated users can communicate with the Skype for Business Server 2019 pool.</span></span>
    
5. <span data-ttu-id="31613-113">После перемещения всех пользователей и контактных объектов, не относящихся к пользователям, необходимо проверить, пуст ли устаревший пул.</span><span class="sxs-lookup"><span data-stu-id="31613-113">After moving all users and non-user contact objects, you need to validate that the legacy pool is empty.</span></span>
    
6. <span data-ttu-id="31613-114">После проверки того, что устаревший пул пуст, его можно отключить.</span><span class="sxs-lookup"><span data-stu-id="31613-114">After verifying that the legacy pool is empty, you can then deactivate the pool.</span></span> 
    
    <span data-ttu-id="31613-115">Сведения о деактивации устаревших пулов и серверов см. в этапе 8. Списание [устаревших пулов.](phase-8-decommission-legacy-pools.md)</span><span class="sxs-lookup"><span data-stu-id="31613-115">For details about how to deactivate the legacy pool and servers, see [Phase 8: Decommission legacy pools](phase-8-decommission-legacy-pools.md).</span></span>
    

