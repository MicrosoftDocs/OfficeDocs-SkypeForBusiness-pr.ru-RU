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
# <a name="migrating-multiple-sites-and-pools"></a><span data-ttu-id="00280-104">Перенос нескольких сайтов и пулов</span><span class="sxs-lookup"><span data-stu-id="00280-104">Migrating multiple sites and pools</span></span>

<span data-ttu-id="00280-105">Skype для бизнеса Server 2019 поддерживает развертывание с несколькими сайтами и несколькими пулами.</span><span class="sxs-lookup"><span data-stu-id="00280-105">Skype for Business Server 2019 supports multi-site and multi-pool deployments.</span></span> <span data-ttu-id="00280-106">Процесс переноса нескольких пулов в Skype для бизнеса Server 2019 требует следующих факторов:</span><span class="sxs-lookup"><span data-stu-id="00280-106">The process of migrating multiple pools to Skype for Business Server 2019 requires the following considerations:</span></span> 
  
1. <span data-ttu-id="00280-107">После развертывания пилотного пула Skype для бизнеса Server 2019 необходимо определить подмножество пилотных пользователей, которые будут перемещены в пул Skype для бизнеса Server 2019, и методологию для проверки функциональных возможностей пользователей.</span><span class="sxs-lookup"><span data-stu-id="00280-107">After deploying a Skype for Business Server 2019 pilot pool, you need to define a subset of pilot users that will be moved to the Skype for Business Server 2019 pool, and a methodology for validating the functionality of the users.</span></span> <span data-ttu-id="00280-108">Например, после перемещения пользователя в пилотный пул убедитесь, что политика конференц-связи пользователя перемещена в Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="00280-108">For example, after moving a user to the pilot pool, verify that the user's conference policy has moved to Skype for Business Server 2019.</span></span> 
    
2. <span data-ttu-id="00280-109">После развертывания пограничного сервера в пилотном пуле необходимо убедиться, что внешние пользователи могут связываться с пулом Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="00280-109">After deploying an Edge Server in the pilot pool, you need to validate that external users can communicate with the Skype for Business Server 2019 pool.</span></span>

3. <span data-ttu-id="00280-110">Функции сохраняемого чата, зеркального отображения SQL и XMPP являются устаревшими в Skype для бизнеса Server 2019 и больше недоступны в качестве функций Skype для бизнеса Server 2019, но они могут возобновленовать в среде сосуществования, если они были развернуты ранее в устаревшей среде.</span><span class="sxs-lookup"><span data-stu-id="00280-110">Persistent Chat, SQL Mirroring, and XMPP functionality are deprecated in Skype for Business Server 2019 and no longer available as Skype for Business Server 2019 features, but they can be continued in a coexistence environment if they were previously deployed in a legacy environment.</span></span> <span data-ttu-id="00280-111">Если вы хотите продолжить использовать эти функции, следует запланировать продолжение работы в среде сосуществования, в которой определенные пользователи останутся в устаревших пулах.</span><span class="sxs-lookup"><span data-stu-id="00280-111">If you want to continue using these features, you should plan to continue with a coexistence environment where certain users will remain in legacy pools.</span></span>
    
4. <span data-ttu-id="00280-112">После переноса пограничных серверов федеративных маршрутов на пограничные серверы Skype для бизнеса Server 2019 необходимо убедиться, что Федеративные пользователи могут связываться с пулом Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="00280-112">After transitioning the federated routes' Edge Servers to the pilot Skype for Business Server 2019 Edge Servers, you need to validate that federated users can communicate with the Skype for Business Server 2019 pool.</span></span>
    
5. <span data-ttu-id="00280-113">После перемещения всех пользователей и объектов контактов, не являющихся пользователями, необходимо проверить, что устаревший пул пуст.</span><span class="sxs-lookup"><span data-stu-id="00280-113">After moving all users and non-user contact objects, you need to validate that the legacy pool is empty.</span></span>
    
6. <span data-ttu-id="00280-114">После проверки того, что устаревший пул пуст, вы можете отключить пул.</span><span class="sxs-lookup"><span data-stu-id="00280-114">After verifying that the legacy pool is empty, you can then deactivate the pool.</span></span> 
    
    <span data-ttu-id="00280-115">Дополнительные сведения об отключении устаревшего пула и серверов приведены в статье [Этап 8: списание устаревших пулов](phase-8-decommission-legacy-pools.md).</span><span class="sxs-lookup"><span data-stu-id="00280-115">For details about how to deactivate the legacy pool and servers, see [Phase 8: Decommission legacy pools](phase-8-decommission-legacy-pools.md).</span></span>
    

