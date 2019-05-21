---
title: Назначение области политики местоположения в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: e4c66517-c593-4253-b900-7b4dd8bddf2f
description: Планирование политик местоположений для развертывания E9-1-1 в корпоративной голосовой связи Skype для бизнеса Server.
ms.openlocfilehash: 04eb04733649e2967980e0121d17cf71221f5387
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34276742"
---
# <a name="assign-location-policy-scope-in-skype-for-business-server"></a><span data-ttu-id="bcf67-103">Назначение области политики местоположения в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="bcf67-103">Assign location policy scope in Skype for Business Server</span></span>
 
<span data-ttu-id="bcf67-104">Планирование политик местоположений для развертывания E9-1-1 в корпоративной голосовой связи Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="bcf67-104">Planning location policies for an E9-1-1 deployment in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="bcf67-105">Как и в других политиках Skype для бизнеса Server, политики расположения можно назначать на нескольких уровнях областей: глобальном, сайте и пользовательском.</span><span class="sxs-lookup"><span data-stu-id="bcf67-105">As with other Skype for Business Server policies, location policies can be assigned at multiple scope levels: global, site, and user.</span></span> <span data-ttu-id="bcf67-106">Тем не менее область действия политик расположения на уровне пользователя не отличается от других политик в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="bcf67-106">However, the scope of user-level location policies behaves a bit differently than with other Skype for Business Server policies.</span></span> <span data-ttu-id="bcf67-107">К объектам конечных точек (например, пользователям и контактам по распространенным телефонным номерам) можно применять не только политики расположения пользователей, но также и для сетевых сайтов Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="bcf67-107">Not only can per-user location policies be applied to endpoint objects (such as Users and Common Area Phone contact objects), they can also be applied to Skype for Business Server network sites.</span></span> <span data-ttu-id="bcf67-108">Сетевые сайты — это группы клиентских подсетей, связанных с географическим расположением (но это необязательно все подсети на всем центральном сайте или сайте филиала).</span><span class="sxs-lookup"><span data-stu-id="bcf67-108">Network sites are groupings of client subnets associated with a geographical location (but may not necessarily be all subnets in an entire central site or branch site).</span></span> <span data-ttu-id="bcf67-109">Все клиенты, подключенные к подсетям на сетевом сайте, автоматически применяют политику расположения, назначенную этому сетевому сайту.</span><span class="sxs-lookup"><span data-stu-id="bcf67-109">Any clients connected to the subnets in a network site automatically pick up the location policy assigned to that network site.</span></span> <span data-ttu-id="bcf67-110">Если политика расположения на уровне пользователя назначена пользователю и сетевому сайту, то политика расположения сетевого сайта имеет более высокий приоритет, чем политика на уровне пользователя.</span><span class="sxs-lookup"><span data-stu-id="bcf67-110">In cases where a user-level location policy is assigned both to a user and to a network site, the network site-based location policy overrides any per-user policy setting.</span></span>
  
<span data-ttu-id="bcf67-111">Каждому сетевому сайту назначена политика расположения, а каждой политике назначены разные значения использования ТСОП, URI уведомлений и URI конференций.</span><span class="sxs-lookup"><span data-stu-id="bcf67-111">Each network site has a location policy assigned to it, and each policy will have different PSTN Usages, Notification URIs, and Conference URIs values assigned to it.</span></span>
  
> [!NOTE]
> <span data-ttu-id="bcf67-112">Такое поведение области политики используется для того, чтобы когда пользователь, размещенный в пуле на одном сайте, посещал другой сайт и совершал экстренный вызов, применялись параметры маршрутизации вызовов E9-1-1, соответствующие этому сетевому сайту, независимо от того, какому сайту или пулу назначен пользователь.</span><span class="sxs-lookup"><span data-stu-id="bcf67-112">The reason for this special policy scoping behavior is so that when a user homed on a pool at one office site visits another site and has to make an emergency call, the E9-1-1 call routing settings appropriate to that network site will apply no matter what pool or site the user is assigned to.</span></span> 
  

