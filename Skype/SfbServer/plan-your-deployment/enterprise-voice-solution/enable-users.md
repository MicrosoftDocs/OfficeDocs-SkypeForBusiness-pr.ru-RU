---
title: Enable users for E9-1-1 in Skype for Business Server
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
ms.assetid: 3cc64f5b-492e-4c47-9713-3c376f2aad02
description: Решения, необходимые для политики расположения для развертывания E9-1-1 в Skype для бизнеса Server Корпоративная голосовая связь, включая пользователей, которых необходимо включить и как поддерживать перемещающихся пользователей.
ms.openlocfilehash: 9a2ced694357b9225555a05c10e93a1006a771b4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825749"
---
# <a name="enable-users-for-e9-1-1-in-skype-for-business-server"></a><span data-ttu-id="31fcb-103">Enable users for E9-1-1 in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="31fcb-103">Enable users for E9-1-1 in Skype for Business Server</span></span>
 
<span data-ttu-id="31fcb-104">Решения, необходимые для политики расположения для развертывания E9-1-1 в Skype для бизнеса Server Корпоративная голосовая связь, включая пользователей, которые необходимо включить и как поддерживать перемещающихся пользователей.</span><span class="sxs-lookup"><span data-stu-id="31fcb-104">Decisions necessary for the location policy for an E9-1-1 deployment in Skype for Business Server Enterprise Voice, including which users to enable and how to support roaming users.</span></span>
  
<span data-ttu-id="31fcb-105">Во время регистрации клиента Skype для бизнеса Server использует политику расположения для настройки свойств E9-1-1 для Корпоративная голосовая связь пользователей с включенной поддержкой.</span><span class="sxs-lookup"><span data-stu-id="31fcb-105">During client registration, Skype for Business Server uses a location policy to configure the E9-1-1 properties for Enterprise Voice-enabled users.</span></span> <span data-ttu-id="31fcb-106">Эта политика содержит параметры, которые определяют способ реализации E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="31fcb-106">This policy contains the settings that define how E9-1-1 is implemented.</span></span> <span data-ttu-id="31fcb-107">Например, политика расположения содержит такие сведения, как строка набора номера для экстренного экстренного обслуживания, а также сведения о том, требуется ли пользователю вручную вводить расположение, если служба сведений о расположении не предоставляет его автоматически.</span><span class="sxs-lookup"><span data-stu-id="31fcb-107">For example, the location policy contains information such as the emergency dial string, and whether or not a user is required to manually enter a location if the Location Information service does not automatically provide one.</span></span> <span data-ttu-id="31fcb-108">Полное определение политики расположений см. в подголеве "Планирование политик расположения [для Skype для бизнеса Server".](location-policies.md)</span><span class="sxs-lookup"><span data-stu-id="31fcb-108">For a complete definition of a location policy, see [Plan location policies for Skype for Business Server](location-policies.md).</span></span>
  
<span data-ttu-id="31fcb-109">Skype для бизнеса Server может назначать политику расположения клиентам на основе подсети или пользователям на основе глобальной политики, политики на уровне сайта или пользователя.</span><span class="sxs-lookup"><span data-stu-id="31fcb-109">Skype for Business Server can assign a location policy to clients based on subnet, or to users based on a global, per-site, or per-user policy.</span></span> <span data-ttu-id="31fcb-110">Чтобы облегчить принятие решения о способе реализации такой поддержки для пользователей, вам следует сначала ответить на следующие вопросы.</span><span class="sxs-lookup"><span data-stu-id="31fcb-110">To help decide how you will enable users, you should first answer the following questions.</span></span>
  
 <span data-ttu-id="31fcb-111">**Вы планируете включить поддержку для всех пользователей или ограничить ее отдельными географическими областями в рамках предприятия?**</span><span class="sxs-lookup"><span data-stu-id="31fcb-111">**Do you plan to enable all users, or limit support to specific geographic areas of the enterprise?**</span></span>
  
> <span data-ttu-id="31fcb-112">Вы можете назначить местоположение всем пользователям предприятия с помощью глобальной политики определения местоположения.</span><span class="sxs-lookup"><span data-stu-id="31fcb-112">You can assign a location to all users in your enterprise by using a global location policy.</span></span> <span data-ttu-id="31fcb-113">Однако, назначив политику расположения сетевому сайту Skype для бизнеса Server и добавив к сайту подсети, вы можете ограничить поддержку E9-1-1 выбранными расположениями на предприятии и задать поведение маршрутизации E9-1-1 для каждого сайта.</span><span class="sxs-lookup"><span data-stu-id="31fcb-113">However, by assigning a location policy to a Skype for Business Server network site and then adding subnets to the site, you can limit E9-1-1 support to selected locations within the enterprise and specify E9-1-1 routing behavior on a per-site basis.</span></span> 
    
 <span data-ttu-id="31fcb-114">**Планируете ли вы включить поддержку для отдельных пользователей с помощью ?**</span><span class="sxs-lookup"><span data-stu-id="31fcb-114">**Do you plan to enable individual users through a user policy?**</span></span>
  
> <span data-ttu-id="31fcb-115">Для настройки поддержки E9-1-1 вы можете назначать политики определения местоположения непосредственно отдельным пользователям или объектам-контактам телефона общего доступа.</span><span class="sxs-lookup"><span data-stu-id="31fcb-115">You can assign location policies directly to specific users or common area phone contact objects if you want to customize their E9-1-1 support.</span></span>
    
 <span data-ttu-id="31fcb-116">**Следует ли включать поддержку E9-1-1 для клиентов, которые находятся в роуминге за пределами сети или подключаются из неопределенной подсети?**</span><span class="sxs-lookup"><span data-stu-id="31fcb-116">**When clients roam outside the network or connect from an undefined subnet, should the clients still be enabled for E9-1-1?**</span></span>
  
> <span data-ttu-id="31fcb-117">Если пользователям назначена глобальная политика, политика расположения на уровне сайта или пользователя, им может потребоваться вручную ввести расположение в клиент, если клиент не находится в определенной подсети или служба сведений о расположении не обнаружила ни одного расположения.</span><span class="sxs-lookup"><span data-stu-id="31fcb-117">If users are assigned a global, site, or per-user location policy, they can be required to manually enter a location into the client if the client is not located within a defined subnet or no location has been found by the Location Information service.</span></span> <span data-ttu-id="31fcb-118">For details, [see Define the user experience for manually acquiring a location in Skype for Business Server.](manually-acquiring-a-location.md)</span><span class="sxs-lookup"><span data-stu-id="31fcb-118">For details, see [Define the user experience for manually acquiring a location in Skype for Business Server](manually-acquiring-a-location.md).</span></span>
    

