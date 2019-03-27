---
title: Планирование подключения к ТСОП в Скайп Business Server
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 280f684a-740a-443d-8ecf-574241382a42
description: Планирование подключения к ТСОП в корпоративной голосовой связи в Скайп Business Server.
ms.openlocfilehash: d98955795ef5172065027a1fab9030091ee11b11
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2019
ms.locfileid: "30878037"
---
# <a name="plan-for-pstn-connectivity-in-skype-for-business-server"></a><span data-ttu-id="0d4a1-103">Планирование подключения к ТСОП в Скайп Business Server</span><span class="sxs-lookup"><span data-stu-id="0d4a1-103">Plan for PSTN connectivity in Skype for Business Server</span></span>
 
<span data-ttu-id="0d4a1-104">Планирование подключения к ТСОП в корпоративной голосовой связи в Скайп Business Server.</span><span class="sxs-lookup"><span data-stu-id="0d4a1-104">Plan for PSTN connectivity in Enterprise Voice in Skype for Business Server.</span></span>
  
<span data-ttu-id="0d4a1-105">Решение VoIP корпоративного уровня должно предусматривать входящие и исходящие вызовы на телефонную сеть общего пользования (ТСОП) без какого-либо снижения качества обслуживания (QoS).</span><span class="sxs-lookup"><span data-stu-id="0d4a1-105">An enterprise-grade VoIP solution must provide for calls to and from the public switched telephone network (PSTN) without any decline in Quality of Service (QoS).</span></span> <span data-ttu-id="0d4a1-106">Пользователи, выполнять и принимать вызовы его не следует принять во внимание базовую технологию: с точки зрения пользователя инфраструктурой корпоративной голосовой связи и наоборот PSTN должны показаться любой другой телефонный звонок.</span><span class="sxs-lookup"><span data-stu-id="0d4a1-106">Users who place and receive calls should not be aware of the underlying technology: from the user's perspective, a call between the Enterprise Voice infrastructure and the PSTN should seem like just another phone call.</span></span>
  
<span data-ttu-id="0d4a1-107">Скайп для Business Server обеспечивает надежное, масштабируемое подключение к ТСОП с помощью следующих параметров:</span><span class="sxs-lookup"><span data-stu-id="0d4a1-107">Skype for Business Server provides reliable, scalable PSTN connectivity by using the following options:</span></span>
  
- <span data-ttu-id="0d4a1-108">**магистрали SIP**, соединяющие с оператором телефонной связи по сети Интернет;</span><span class="sxs-lookup"><span data-stu-id="0d4a1-108">**SIP trunks** to an Internet telephony service provider (ITSP)</span></span>
    
- <span data-ttu-id="0d4a1-109">**прямые подключения SIP** к шлюзу ТСОП;</span><span class="sxs-lookup"><span data-stu-id="0d4a1-109">**Direct SIP connections** to a PSTN gateway</span></span>
    
- <span data-ttu-id="0d4a1-110">**прямые подключения SIP** к УАТС.</span><span class="sxs-lookup"><span data-stu-id="0d4a1-110">**Direct SIP connections** to a PBX</span></span>
    
<span data-ttu-id="0d4a1-p102">В зависимости от размеров предприятия, охватываемой территории и существующей инфраструктуры голосовой связи можно применять один и тот же способ на всем предприятии либо два или все три способа в разных подразделениях. Сведения о каждом способе см. в следующих разделах.</span><span class="sxs-lookup"><span data-stu-id="0d4a1-p102">Depending on its size, geographic coverage, and existing voice infrastructure, an enterprise may use one, two, or even all three of these options at various locations. For details about these options, see the following sections.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="0d4a1-113">Содержание</span><span class="sxs-lookup"><span data-stu-id="0d4a1-113">In this section</span></span>

- [<span data-ttu-id="0d4a1-114">SIP-магистрали в Скайп для Business Server</span><span class="sxs-lookup"><span data-stu-id="0d4a1-114">SIP trunking in Skype for Business Server</span></span>](sip-trunking.md)
    
- [<span data-ttu-id="0d4a1-115">Прямые SIP-подключения в Скайп для Business Server</span><span class="sxs-lookup"><span data-stu-id="0d4a1-115">Direct SIP connections in Skype for Business Server</span></span>](direct-sip.md)
    
- [<span data-ttu-id="0d4a1-116">Магистраль m: n в Скайп для Business Server</span><span class="sxs-lookup"><span data-stu-id="0d4a1-116">M:N trunk in Skype for Business Server</span></span>](m-n-trunk.md)
    
- [<span data-ttu-id="0d4a1-117">Правила преобразования в Скайп для Business Server</span><span class="sxs-lookup"><span data-stu-id="0d4a1-117">Translation rules in Skype for Business Server</span></span>](translation-rules.md)
    
- [<span data-ttu-id="0d4a1-118">Планирование маршрутизации исходящей голосовой почты в Скайп для Business Server</span><span class="sxs-lookup"><span data-stu-id="0d4a1-118">Plan for outbound voice routing in Skype for Business Server</span></span>](outbound-voice-routing.md)
    

