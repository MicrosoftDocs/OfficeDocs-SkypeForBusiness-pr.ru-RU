---
title: Включение пользователей для E9-1-1 в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: Решения, необходимые для политики местоположения для развертывания E9-1-1 в корпоративной среде Skype для бизнеса Server Enterprise, включая сведения о том, какие пользователи должны включать и как поддерживать перемещаемые пользователи.
ms.openlocfilehash: 717b127a94fbac966476c681cfb7f6e81d91bde9
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802959"
---
# <a name="enable-users-for-e9-1-1-in-skype-for-business-server"></a><span data-ttu-id="45db2-103">Включение пользователей для E9-1-1 в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="45db2-103">Enable users for E9-1-1 in Skype for Business Server</span></span>
 
<span data-ttu-id="45db2-104">Решения, необходимые для политики местоположения для развертывания E9-1-1 в корпоративной среде Skype для бизнеса Server Enterprise, включая сведения о том, какие пользователи должны включать и как поддерживать перемещаемые пользователи.</span><span class="sxs-lookup"><span data-stu-id="45db2-104">Decisions necessary for the location policy for an E9-1-1 deployment in Skype for Business Server Enterprise Voice, including which users to enable and how to support roaming users.</span></span>
  
<span data-ttu-id="45db2-105">Во время регистрации клиента в Skype для бизнеса Server используется политика расположения для настройки свойств E9-1-1 для пользователей, поддерживающих поддержку корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="45db2-105">During client registration, Skype for Business Server uses a location policy to configure the E9-1-1 properties for Enterprise Voice-enabled users.</span></span> <span data-ttu-id="45db2-106">Эта политика содержит параметры, которые определяют способ реализации E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="45db2-106">This policy contains the settings that define how E9-1-1 is implemented.</span></span> <span data-ttu-id="45db2-107">Например, политика "расположение" содержит такие сведения, как строка набора номера, а также укажите, требуется ли пользователю вручную вводить расположение, если служба сведений о расположении не предоставляет ее автоматически.</span><span class="sxs-lookup"><span data-stu-id="45db2-107">For example, the location policy contains information such as the emergency dial string, and whether or not a user is required to manually enter a location if the Location Information service does not automatically provide one.</span></span> <span data-ttu-id="45db2-108">Полное определение политики местоположения можно найти в разделе [политики расположения планов для Skype для бизнеса Server](location-policies.md).</span><span class="sxs-lookup"><span data-stu-id="45db2-108">For a complete definition of a location policy, see [Plan location policies for Skype for Business Server](location-policies.md).</span></span>
  
<span data-ttu-id="45db2-109">Skype для бизнеса Server может назначать политику расположения клиентам в зависимости от подсети, а также пользователям, основанным на глобальном или отдельном сайте или политике пользователя.</span><span class="sxs-lookup"><span data-stu-id="45db2-109">Skype for Business Server can assign a location policy to clients based on subnet, or to users based on a global, per-site, or per-user policy.</span></span> <span data-ttu-id="45db2-110">Чтобы облегчить принятие решения о способе реализации такой поддержки для пользователей, вам следует сначала ответить на следующие вопросы.</span><span class="sxs-lookup"><span data-stu-id="45db2-110">To help decide how you will enable users, you should first answer the following questions.</span></span>
  
 <span data-ttu-id="45db2-111">**Вы планируете включить поддержку для всех пользователей или ограничить ее отдельными географическими областями в рамках предприятия?**</span><span class="sxs-lookup"><span data-stu-id="45db2-111">**Do you plan to enable all users, or limit support to specific geographic areas of the enterprise?**</span></span>
  
> <span data-ttu-id="45db2-112">Вы можете назначить расположение всем пользователям предприятия с помощью глобальной политики расположения.</span><span class="sxs-lookup"><span data-stu-id="45db2-112">You can assign a location to all users in your enterprise by using a global location policy.</span></span> <span data-ttu-id="45db2-113">Тем не менее, назначая политику местоположений на сетевом сайте Skype для бизнеса Server и затем добавляя подсети на сайт, вы можете ограничить поддержку E9-1-1 для выбранных расположений в рамках предприятия и задать E9-1-1 процесс маршрутизации для каждого сайта.</span><span class="sxs-lookup"><span data-stu-id="45db2-113">However, by assigning a location policy to a Skype for Business Server network site and then adding subnets to the site, you can limit E9-1-1 support to selected locations within the enterprise and specify E9-1-1 routing behavior on a per-site basis.</span></span> 
    
 <span data-ttu-id="45db2-114">**Планируете ли вы включить поддержку для отдельных пользователей с помощью ?**</span><span class="sxs-lookup"><span data-stu-id="45db2-114">**Do you plan to enable individual users through a user policy?**</span></span>
  
> <span data-ttu-id="45db2-115">Для настройки поддержки E9-1-1 вы можете назначать политики расположения непосредственно отдельным пользователям или контактным объектам телефона общего доступа.</span><span class="sxs-lookup"><span data-stu-id="45db2-115">You can assign location policies directly to specific users or common area phone contact objects if you want to customize their E9-1-1 support.</span></span>
    
 <span data-ttu-id="45db2-116">**Следует ли включать поддержку E9-1-1 для клиентов, которые находятся в роуминге за пределами сети или подключаются из неопределенной подсети?**</span><span class="sxs-lookup"><span data-stu-id="45db2-116">**When clients roam outside the network or connect from an undefined subnet, should the clients still be enabled for E9-1-1?**</span></span>
  
> <span data-ttu-id="45db2-117">Если пользователям назначены глобальные, сайты или индивидуальные параметры, они могут быть необходимы для того, чтобы вручную указать расположение в клиенте, если клиент не находится в определенной подсети или расположение не обнаружено службой сведений о расположении.</span><span class="sxs-lookup"><span data-stu-id="45db2-117">If users are assigned a global, site, or per-user location policy, they can be required to manually enter a location into the client if the client is not located within a defined subnet or no location has been found by the Location Information service.</span></span> <span data-ttu-id="45db2-118">Подробности можно найти [в разделе Определение взаимодействия с пользователем, чтобы вручную получить место в Skype для бизнеса Server](manually-acquiring-a-location.md).</span><span class="sxs-lookup"><span data-stu-id="45db2-118">For details, see [Define the user experience for manually acquiring a location in Skype for Business Server](manually-acquiring-a-location.md).</span></span>
    

