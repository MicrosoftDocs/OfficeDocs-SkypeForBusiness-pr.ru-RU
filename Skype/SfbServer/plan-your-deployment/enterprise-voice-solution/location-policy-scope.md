---
title: Назначение области политики расположения в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: e4c66517-c593-4253-b900-7b4dd8bddf2f
description: Планирование политик расположения для развертывания E9-1-1 в Skype для бизнеса Server Корпоративная голосовая связь.
ms.openlocfilehash: 586aabe919ea4236dc724446da717b5f300d88e9
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825529"
---
# <a name="assign-location-policy-scope-in-skype-for-business-server"></a><span data-ttu-id="6fe50-103">Назначение области политики расположения в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="6fe50-103">Assign location policy scope in Skype for Business Server</span></span>
 
<span data-ttu-id="6fe50-104">Планирование политик расположения для развертывания E9-1-1 в Skype для бизнеса Server Корпоративная голосовая связь.</span><span class="sxs-lookup"><span data-stu-id="6fe50-104">Planning location policies for an E9-1-1 deployment in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="6fe50-105">Как и в других политиках Skype для бизнеса Server, политики расположения могут быть назначены на нескольких уровнях: на глобальном уровне, на уровне сайта и на уровне пользователя.</span><span class="sxs-lookup"><span data-stu-id="6fe50-105">As with other Skype for Business Server policies, location policies can be assigned at multiple scope levels: global, site, and user.</span></span> <span data-ttu-id="6fe50-106">Однако область применения политик расположения на уровне пользователя ведет себя немного иначе, чем в других политиках Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="6fe50-106">However, the scope of user-level location policies behaves a bit differently than with other Skype for Business Server policies.</span></span> <span data-ttu-id="6fe50-107">Политики расположения на пользователя можно применять не только к объектам конечных точек (например, объектам контактов "Пользователи" и "Телефон общего звонков"), но и к сетевым сайтам Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="6fe50-107">Not only can per-user location policies be applied to endpoint objects (such as Users and Common Area Phone contact objects), they can also be applied to Skype for Business Server network sites.</span></span> <span data-ttu-id="6fe50-108">Сетевые узлы — это группы клиентских подсетей, связанных с географическим расположением (но это необязательно все подсети во всем центральном узле или узле филиала).</span><span class="sxs-lookup"><span data-stu-id="6fe50-108">Network sites are groupings of client subnets associated with a geographical location (but may not necessarily be all subnets in an entire central site or branch site).</span></span> <span data-ttu-id="6fe50-109">Все клиенты, подключенные к подсетям в сетевом узле, автоматически применяют политику местоположения, назначенную этому сетевому узлу.</span><span class="sxs-lookup"><span data-stu-id="6fe50-109">Any clients connected to the subnets in a network site automatically pick up the location policy assigned to that network site.</span></span> <span data-ttu-id="6fe50-110">Если политика местоположения на уровне пользователя назначена пользователю и сетевому узлу, то политика местоположения сетевого узла имеет более высокий приоритет, чем политика на уровне пользователя.</span><span class="sxs-lookup"><span data-stu-id="6fe50-110">In cases where a user-level location policy is assigned both to a user and to a network site, the network site-based location policy overrides any per-user policy setting.</span></span>
  
<span data-ttu-id="6fe50-111">Каждому сетевому узлу назначена политика местоположения, а каждой политике назначены разные значения использования ТСОП, URI уведомлений и URI конференций.</span><span class="sxs-lookup"><span data-stu-id="6fe50-111">Each network site has a location policy assigned to it, and each policy will have different PSTN Usages, Notification URIs, and Conference URIs values assigned to it.</span></span>
  
> [!NOTE]
> <span data-ttu-id="6fe50-112">Такое поведение области политики используется для того, чтобы когда пользователь, размещенный в пуле в одном узле, посещал другой узел и совершал экстренный вызов, применялись параметры маршрутизации вызовов E9-1-1, соответствующие этому сетевому узлу, независимо от того, какому узлу или пулу назначен пользователь.</span><span class="sxs-lookup"><span data-stu-id="6fe50-112">The reason for this special policy scoping behavior is so that when a user homed on a pool at one office site visits another site and has to make an emergency call, the E9-1-1 call routing settings appropriate to that network site will apply no matter what pool or site the user is assigned to.</span></span> 
  

