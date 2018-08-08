---
title: Назначение области политики расположения в Скайп для Business Server
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: e4c66517-c593-4253-b900-7b4dd8bddf2f
description: Планирование политик расположения для развертывания E9-1-1 в Скайп Business Server корпоративной голосовой связи.
ms.openlocfilehash: 26d621877a61f372a6f40d20f8253954e3d43e5d
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2018
ms.locfileid: "20966280"
---
# <a name="assign-location-policy-scope-in-skype-for-business-server"></a><span data-ttu-id="2d6f8-103">Назначение области политики расположения в Скайп для Business Server</span><span class="sxs-lookup"><span data-stu-id="2d6f8-103">Assign location policy scope in Skype for Business Server</span></span>
 
<span data-ttu-id="2d6f8-104">Планирование политик расположения для развертывания E9-1-1 в Скайп Business Server корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="2d6f8-104">Planning location policies for an E9-1-1 deployment in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="2d6f8-105">Как с другими Скайп Business Server политик для политик расположения может быть назначен на нескольких уровнях области: глобальная, на уровне пользователей и сайтов.</span><span class="sxs-lookup"><span data-stu-id="2d6f8-105">As with other Skype for Business Server policies, location policies can be assigned at multiple scope levels: global, site, and user.</span></span> <span data-ttu-id="2d6f8-106">Тем не менее область политики расположения уровня пользователя ведет себя несколько иначе, чем с другими Скайп для политик Business Server.</span><span class="sxs-lookup"><span data-stu-id="2d6f8-106">However, the scope of user-level location policies behaves a bit differently than with other Skype for Business Server policies.</span></span> <span data-ttu-id="2d6f8-107">Не только политики расположения уровня пользователя применимы к объектам конечной точки (например, пользователей и общие объекты контактов региональный телефон), они могут применяться для Скайп для сетевых узлов Business Server.</span><span class="sxs-lookup"><span data-stu-id="2d6f8-107">Not only can per-user location policies be applied to endpoint objects (such as Users and Common Area Phone contact objects), they can also be applied to Skype for Business Server network sites.</span></span> <span data-ttu-id="2d6f8-108">Сетевые сайты — это группы клиентских подсетей, связанных с географическим расположением (но это необязательно все подсети на всем центральном сайте или сайте филиала).</span><span class="sxs-lookup"><span data-stu-id="2d6f8-108">Network sites are groupings of client subnets associated with a geographical location (but may not necessarily be all subnets in an entire central site or branch site).</span></span> <span data-ttu-id="2d6f8-109">Все клиенты, подключенные к подсетям на сетевом сайте, автоматически применяют политику расположения, назначенную этому сетевому сайту.</span><span class="sxs-lookup"><span data-stu-id="2d6f8-109">Any clients connected to the subnets in a network site automatically pick up the location policy assigned to that network site.</span></span> <span data-ttu-id="2d6f8-110">Если политика расположения на уровне пользователя назначена пользователю и сетевому сайту, то политика расположения сетевого сайта имеет более высокий приоритет, чем политика на уровне пользователя.</span><span class="sxs-lookup"><span data-stu-id="2d6f8-110">In cases where a user-level location policy is assigned both to a user and to a network site, the network site-based location policy overrides any per-user policy setting.</span></span>
  
<span data-ttu-id="2d6f8-111">Каждому сетевому сайту назначена политика расположения, а каждой политике назначены разные значения использования ТСОП, URI уведомлений и URI конференций.</span><span class="sxs-lookup"><span data-stu-id="2d6f8-111">Each network site has a location policy assigned to it, and each policy will have different PSTN Usages, Notification URIs, and Conference URIs values assigned to it.</span></span>
  
> [!NOTE]
> <span data-ttu-id="2d6f8-112">Такое поведение области политики используется для того, чтобы когда пользователь, размещенный в пуле на одном сайте, посещал другой сайт и совершал экстренный вызов, применялись параметры маршрутизации вызовов E9-1-1, соответствующие этому сетевому сайту, независимо от того, какому сайту или пулу назначен пользователь.</span><span class="sxs-lookup"><span data-stu-id="2d6f8-112">The reason for this special policy scoping behavior is so that when a user homed on a pool at one office site visits another site and has to make an emergency call, the E9-1-1 call routing settings appropriate to that network site will apply no matter what pool or site the user is assigned to.</span></span> 
  

