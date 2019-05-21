---
title: Перенос нескольких сайтов и пулов
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Skype для бизнеса Server 2019 поддерживает развертывание с несколькими сайтами и несколькими пулами. Процесс миграции нескольких пулов в Skype для бизнеса Server 2019 требует указанных ниже факторов.
ms.openlocfilehash: 05a94cb47568b9dfc3834f65f960353ad2933b03
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34298185"
---
# <a name="migrating-multiple-sites-and-pools"></a><span data-ttu-id="9575f-104">Перенос нескольких сайтов и пулов</span><span class="sxs-lookup"><span data-stu-id="9575f-104">Migrating multiple sites and pools</span></span>

<span data-ttu-id="9575f-105">Skype для бизнеса Server 2019 поддерживает развертывание с несколькими сайтами и несколькими пулами.</span><span class="sxs-lookup"><span data-stu-id="9575f-105">Skype for Business Server 2019 supports multi-site and multi-pool deployments.</span></span> <span data-ttu-id="9575f-106">Процесс миграции нескольких пулов в Skype для бизнеса Server 2019 требует указанных ниже факторов.</span><span class="sxs-lookup"><span data-stu-id="9575f-106">The process of migrating multiple pools to Skype for Business Server 2019 requires the following considerations:</span></span> 
  
1. <span data-ttu-id="9575f-107">После развертывания пула пилотных проектов в Skype для бизнеса Server 2019 необходимо определить подмножество пользователей, которые будут перенесены в пул Skype для бизнеса Server 2019, и методологию для проверки функциональных возможностей пользователей.</span><span class="sxs-lookup"><span data-stu-id="9575f-107">After deploying a Skype for Business Server 2019 pilot pool, you need to define a subset of pilot users that will be moved to the Skype for Business Server 2019 pool, and a methodology for validating the functionality of the users.</span></span> <span data-ttu-id="9575f-108">Например, после перемещения пользователя в пилотный пул убедитесь в том, что политика конференции пользователя перемещена в Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="9575f-108">For example, after moving a user to the pilot pool, verify that the user's conference policy has moved to Skype for Business Server 2019.</span></span> 
    
2. <span data-ttu-id="9575f-109">После развертывания пограничного сервера в пилотном пуле необходимо проверить, могут и внешние пользователи общаться с пулом 2019 Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="9575f-109">After deploying an Edge Server in the pilot pool, you need to validate that external users can communicate with the Skype for Business Server 2019 pool.</span></span>

3. <span data-ttu-id="9575f-110">Функция сохраняемый чат, SQL Mirroring и КСМПП устарела в Skype для бизнеса Server 2019 и больше не доступна в качестве функций Skype для бизнеса Server 2019, но их можно продолжать в среде сосуществования, если ранее они были развернуты в устаревшая среда.</span><span class="sxs-lookup"><span data-stu-id="9575f-110">Persistent Chat, SQL Mirroring, and XMPP functionality are deprecated in Skype for Business Server 2019 and no longer available as Skype for Business Server 2019 features, but they can be continued in a coexistence environment if they were previously deployed in a legacy environment.</span></span> <span data-ttu-id="9575f-111">Если вы хотите продолжить использование этих функций, следует планировать работу среды сосуществования, в которой некоторые пользователи будут храниться в старых пулах.</span><span class="sxs-lookup"><span data-stu-id="9575f-111">If you want to continue using these features, you should plan to continue with a coexistence environment where certain users will remain in legacy pools.</span></span>
    
4. <span data-ttu-id="9575f-112">После перехода на пограничные серверы федеративных маршрутов на пограничные серверы в Skype для бизнеса Server 2019 необходимо подтвердить, что Федеративные пользователи смогут взаимодействовать с пулом Microsoft Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="9575f-112">After transitioning the federated routes' Edge Servers to the pilot Skype for Business Server 2019 Edge Servers, you need to validate that federated users can communicate with the Skype for Business Server 2019 pool.</span></span>
    
5. <span data-ttu-id="9575f-113">После перемещения всех пользователей и объектов контактов, не являющихся пользователями, необходимо подтвердить, что устаревший пул пуст.</span><span class="sxs-lookup"><span data-stu-id="9575f-113">After moving all users and non-user contact objects, you need to validate that the legacy pool is empty.</span></span>
    
6. <span data-ttu-id="9575f-114">После того как вы убедитесь в том, что устаревший пул пуст, вы можете деактивировать пул.</span><span class="sxs-lookup"><span data-stu-id="9575f-114">After verifying that the legacy pool is empty, you can then deactivate the pool.</span></span> 
    
    <span data-ttu-id="9575f-115">Подробнее об отключении устаревшего пула и серверов вы можете найти в статье [Этап 8: списание устаревших пулов](phase-8-decommission-legacy-pools.md).</span><span class="sxs-lookup"><span data-stu-id="9575f-115">For details about how to deactivate the legacy pool and servers, see [Phase 8: Decommission legacy pools](phase-8-decommission-legacy-pools.md).</span></span>
    

