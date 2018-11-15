---
title: Перенос нескольких сайтов и пулов
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 'Скайп для Business Server 2019 поддерживает развертывание на нескольких сайтах и несколькими пула. Процесс миграции несколько пулов в Скайп for Business Server 2019 требуются следующие вопросы:'
ms.openlocfilehash: 74c622c1cde4a01c51749c6942c898e11e1551f9
ms.sourcegitcommit: 30620021ceba916a505437ab641a23393f55827a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/15/2018
ms.locfileid: "26531766"
---
# <a name="migrating-multiple-sites-and-pools"></a><span data-ttu-id="4c3ae-104">Перенос нескольких сайтов и пулов</span><span class="sxs-lookup"><span data-stu-id="4c3ae-104">Migrating multiple sites and pools</span></span>

<span data-ttu-id="4c3ae-105">Скайп для Business Server 2019 поддерживает развертывание на нескольких сайтах и несколькими пула.</span><span class="sxs-lookup"><span data-stu-id="4c3ae-105">Skype for Business Server 2019 supports multi-site and multi-pool deployments.</span></span> <span data-ttu-id="4c3ae-106">Процесс миграции несколько пулов в Скайп for Business Server 2019 требуются следующие вопросы:</span><span class="sxs-lookup"><span data-stu-id="4c3ae-106">The process of migrating multiple pools to Skype for Business Server 2019 requires the following considerations:</span></span> 
  
1. <span data-ttu-id="4c3ae-107">После развертывания Скайп для пилотного пула Business Server 2019, необходимо определить подмножество пилотных пользователей, которые планируется переместить Скайп для пула Business Server 2019 и методики для проверки правильности работы пользователей.</span><span class="sxs-lookup"><span data-stu-id="4c3ae-107">After deploying a Skype for Business Server 2019 pilot pool, you need to define a subset of pilot users that will be moved to the Skype for Business Server 2019 pool, and a methodology for validating the functionality of the users.</span></span> <span data-ttu-id="4c3ae-108">Например после перемещения пользователей в пилотный пул проверить политике конференции перемещения Скайп для Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="4c3ae-108">For example, after moving a user to the pilot pool, verify that the user's conference policy has moved to Skype for Business Server 2019.</span></span> 
    
2. <span data-ttu-id="4c3ae-109">После развертывания пограничного сервера в пилотном пуле необходимо проверить возможность связи внешних пользователей с Скайп для пула Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="4c3ae-109">After deploying an Edge Server in the pilot pool, you need to validate that external users can communicate with the Skype for Business Server 2019 pool.</span></span>

3. <span data-ttu-id="4c3ae-110">Сохраняемый чат, зеркальное отображение SQL и функциональные возможности XMPP не рекомендуемые для использования в Скайп для Business Server 2019 и больше не доступен в качестве Скайп для функций Business Server 2019, но может быть продолжен в среде сосуществования, развернутых в старой среды.</span><span class="sxs-lookup"><span data-stu-id="4c3ae-110">Persistent Chat, SQL Mirroring, and XMPP functionality are deprecated in Skype for Business Server 2019 and no longer available as Skype for Business Server 2019 features, but they can be continued in a coexistence environment if they were previously deployed in a legacy environment.</span></span> <span data-ttu-id="4c3ae-111">Если вы хотите продолжить использовать эти функции, необходимо продолжить работу в среде совместной работы, где определенные пользователи будут оставаться в старых пулов.</span><span class="sxs-lookup"><span data-stu-id="4c3ae-111">If you want to continue using these features, you should plan to continue with a coexistence environment where certain users will remain in legacy pools.</span></span>
    
4. <span data-ttu-id="4c3ae-112">После преобразования маршрутов федерации пограничных серверов для пилотного Скайп для Business Server 2019 пограничных серверов, необходимо проверить возможность связи федеративных пользователей с Скайп для пула Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="4c3ae-112">After transitioning the federated routes' Edge Servers to the pilot Skype for Business Server 2019 Edge Servers, you need to validate that federated users can communicate with the Skype for Business Server 2019 pool.</span></span>
    
5. <span data-ttu-id="4c3ae-113">После перемещения всех пользователей и контактных объектов не пользователем, необходимо проверить, что устаревшие пул пуст.</span><span class="sxs-lookup"><span data-stu-id="4c3ae-113">After moving all users and non-user contact objects, you need to validate that the legacy pool is empty.</span></span>
    
6. <span data-ttu-id="4c3ae-114">Убедившись, что устаревшего пула пуст, вы можете отключить пула.</span><span class="sxs-lookup"><span data-stu-id="4c3ae-114">After verifying that the legacy pool is empty, you can then deactivate the pool.</span></span> 
    
    <span data-ttu-id="4c3ae-115">Дополнительные сведения о том, как отключить устаревшего пула и серверы см [Этап 8: ликвидация старых пулов](phase-8-decommission-legacy-pools.md).</span><span class="sxs-lookup"><span data-stu-id="4c3ae-115">For details about how to deactivate the legacy pool and servers, see [Phase 8: Decommission legacy pools](phase-8-decommission-legacy-pools.md).</span></span>
    

