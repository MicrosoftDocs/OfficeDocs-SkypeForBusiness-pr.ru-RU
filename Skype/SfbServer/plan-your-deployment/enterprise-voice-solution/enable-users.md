---
title: Включение пользователей для E9-1-1 в Скайп для Business Server
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
ms.assetid: 3cc64f5b-492e-4c47-9713-3c376f2aad02
description: Решения для политики расположения для развертывания E9-1-1 в Скайп для Business Server корпоративной голосовой связи, включая пользователей, которые для включения и как для поддержки перемещаемых профилей пользователей.
ms.openlocfilehash: c5dbbc7904313ffc1706615f2aec506032e20074
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2018
ms.locfileid: "20997196"
---
# <a name="enable-users-for-e9-1-1-in-skype-for-business-server"></a><span data-ttu-id="57bda-103">Включение пользователей для E9-1-1 в Скайп для Business Server</span><span class="sxs-lookup"><span data-stu-id="57bda-103">Enable users for E9-1-1 in Skype for Business Server</span></span>
 
<span data-ttu-id="57bda-104">Решения для политики расположения для развертывания E9-1-1 в Скайп для Business Server корпоративной голосовой связи, включая пользователей, которые для включения и как для поддержки перемещаемых профилей пользователей.</span><span class="sxs-lookup"><span data-stu-id="57bda-104">Decisions necessary for the location policy for an E9-1-1 deployment in Skype for Business Server Enterprise Voice, including which users to enable and how to support roaming users.</span></span>
  
<span data-ttu-id="57bda-105">Во время регистрации клиента Скайп для Business Server использует политику расположения для настройки свойств E9-1-1 для пользователей с включенной поддержкой корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="57bda-105">During client registration, Skype for Business Server uses a location policy to configure the E9-1-1 properties for Enterprise Voice-enabled users.</span></span> <span data-ttu-id="57bda-106">Эта политика содержит параметры, которые определяют способ реализации E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="57bda-106">This policy contains the settings that define how E9-1-1 is implemented.</span></span> <span data-ttu-id="57bda-107">Например политика расположения содержит информацию, например строка набора аварийного, а также ли пользователь должен будет вручную ввести в расположение, если службе информирования о местонахождении не автоматически предоставлять один.</span><span class="sxs-lookup"><span data-stu-id="57bda-107">For example, the location policy contains information such as the emergency dial string, and whether or not a user is required to manually enter a location if the Location Information service does not automatically provide one.</span></span> <span data-ttu-id="57bda-108">Полное определение политики расположения в разделе [планирование политики расположения для Скайп для Business Server](location-policies.md).</span><span class="sxs-lookup"><span data-stu-id="57bda-108">For a complete definition of a location policy, see [Plan location policies for Skype for Business Server](location-policies.md).</span></span>
  
<span data-ttu-id="57bda-109">Скайп для Business Server можно назначить политику расположения на основании подсети или пользователям глобальная, на основе отдельных веб-сайтов или политики уровня пользователя.</span><span class="sxs-lookup"><span data-stu-id="57bda-109">Skype for Business Server can assign a location policy to clients based on subnet, or to users based on a global, per-site, or per-user policy.</span></span> <span data-ttu-id="57bda-110">Чтобы облегчить принятие решения о способе реализации такой поддержки для пользователей, вам следует сначала ответить на следующие вопросы.</span><span class="sxs-lookup"><span data-stu-id="57bda-110">To help decide how you will enable users, you should first answer the following questions.</span></span>
  
 <span data-ttu-id="57bda-111">**Вы планируете включить поддержку для всех пользователей или ограничить ее отдельными географическими областями в рамках предприятия?**</span><span class="sxs-lookup"><span data-stu-id="57bda-111">**Do you plan to enable all users, or limit support to specific geographic areas of the enterprise?**</span></span>
  
> <span data-ttu-id="57bda-112">Вы можете назначить расположение всем пользователям предприятия с помощью глобальной политики расположения.</span><span class="sxs-lookup"><span data-stu-id="57bda-112">You can assign a location to all users in your enterprise by using a global location policy.</span></span> <span data-ttu-id="57bda-113">Тем не менее, назначение политики расположения для Скайп для сетевого узла Business Server, а затем добавьте подсети к сайту, можно ограничить поддержку E9-1-1 для выбранного расположения в рамках предприятия и указать поведение маршрутизации E9-1-1 на каждом узле.</span><span class="sxs-lookup"><span data-stu-id="57bda-113">However, by assigning a location policy to a Skype for Business Server network site and then adding subnets to the site, you can limit E9-1-1 support to selected locations within the enterprise and specify E9-1-1 routing behavior on a per-site basis.</span></span> 
    
 <span data-ttu-id="57bda-114">**Планируете ли вы включить поддержку для отдельных пользователей с помощью ?**</span><span class="sxs-lookup"><span data-stu-id="57bda-114">**Do you plan to enable individual users through a user policy?**</span></span>
  
> <span data-ttu-id="57bda-115">Для настройки поддержки E9-1-1 вы можете назначать политики расположения непосредственно отдельным пользователям или контактным объектам телефона общего доступа.</span><span class="sxs-lookup"><span data-stu-id="57bda-115">You can assign location policies directly to specific users or common area phone contact objects if you want to customize their E9-1-1 support.</span></span>
    
 <span data-ttu-id="57bda-116">**Следует ли включать поддержку E9-1-1 для клиентов, которые находятся в роуминге за пределами сети или подключаются из неопределенной подсети?**</span><span class="sxs-lookup"><span data-stu-id="57bda-116">**When clients roam outside the network or connect from an undefined subnet, should the clients still be enabled for E9-1-1?**</span></span>
  
> <span data-ttu-id="57bda-117">Если пользователи назначаются глобального, веб-сайтов, или политики расположения уровня пользователя, они могут быть необходимо вручную ввести в расположение в клиент, если клиент не расположен в определенном подсети или нет расположение не было найдено службой сведения о расположении.</span><span class="sxs-lookup"><span data-stu-id="57bda-117">If users are assigned a global, site, or per-user location policy, they can be required to manually enter a location into the client if the client is not located within a defined subnet or no location has been found by the Location Information service.</span></span> <span data-ttu-id="57bda-118">Дополнительные сведения см [Определение пользовательского интерфейса для получения местоположения в Скайп для Business Server вручную](manually-acquiring-a-location.md).</span><span class="sxs-lookup"><span data-stu-id="57bda-118">For details, see [Define the user experience for manually acquiring a location in Skype for Business Server](manually-acquiring-a-location.md).</span></span>
    

