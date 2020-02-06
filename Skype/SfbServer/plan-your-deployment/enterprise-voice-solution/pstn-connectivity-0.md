---
title: Планирование подключения к PSTN в Skype для бизнеса Server
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
ms.assetid: 280f684a-740a-443d-8ecf-574241382a42
description: Планирование подключений PSTN в корпоративной голосовой связи в Skype для бизнеса Server.
ms.openlocfilehash: 12c18ba0be3f01651fb72ff325d7e51566da86ae
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802549"
---
# <a name="plan-for-pstn-connectivity-in-skype-for-business-server"></a><span data-ttu-id="61478-103">Планирование подключения к PSTN в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="61478-103">Plan for PSTN connectivity in Skype for Business Server</span></span>
 
<span data-ttu-id="61478-104">Планирование подключений PSTN в корпоративной голосовой связи в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="61478-104">Plan for PSTN connectivity in Enterprise Voice in Skype for Business Server.</span></span>
  
<span data-ttu-id="61478-105">Решение VoIP корпоративного уровня должно предусматривать входящие и исходящие вызовы на телефонную сеть общего пользования (ТСОП) без какого-либо снижения качества обслуживания (QoS).</span><span class="sxs-lookup"><span data-stu-id="61478-105">An enterprise-grade VoIP solution must provide for calls to and from the public switched telephone network (PSTN) without any decline in Quality of Service (QoS).</span></span> <span data-ttu-id="61478-106">Пользователи, которые размещаются и принимают звонки, не должны знать о базовой технологии: с точки зрения пользователя, Звонок между корпоративной инфраструктурой голосовой связи и PSTN должен казаться просто другим телефонным звонком.</span><span class="sxs-lookup"><span data-stu-id="61478-106">Users who place and receive calls should not be aware of the underlying technology: from the user's perspective, a call between the Enterprise Voice infrastructure and the PSTN should seem like just another phone call.</span></span>
  
<span data-ttu-id="61478-107">Skype для бизнеса Server обеспечивает надежную и масштабируемую КОММУТИРУЕМую связь с помощью следующих параметров:</span><span class="sxs-lookup"><span data-stu-id="61478-107">Skype for Business Server provides reliable, scalable PSTN connectivity by using the following options:</span></span>
  
- <span data-ttu-id="61478-108">**магистрали SIP**, соединяющие с оператором телефонной связи по сети Интернет;</span><span class="sxs-lookup"><span data-stu-id="61478-108">**SIP trunks** to an Internet telephony service provider (ITSP)</span></span>
    
- <span data-ttu-id="61478-109">**прямые подключения SIP** к шлюзу ТСОП;</span><span class="sxs-lookup"><span data-stu-id="61478-109">**Direct SIP connections** to a PSTN gateway</span></span>
    
- <span data-ttu-id="61478-110">**прямые подключения SIP** к УАТС.</span><span class="sxs-lookup"><span data-stu-id="61478-110">**Direct SIP connections** to a PBX</span></span>
    
<span data-ttu-id="61478-p102">В зависимости от размеров предприятия, охватываемой территории и существующей инфраструктуры голосовой связи можно применять один и тот же способ на всем предприятии либо два или все три способа в разных подразделениях. Сведения о каждом способе см. в следующих разделах.</span><span class="sxs-lookup"><span data-stu-id="61478-p102">Depending on its size, geographic coverage, and existing voice infrastructure, an enterprise may use one, two, or even all three of these options at various locations. For details about these options, see the following sections.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="61478-113">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="61478-113">In this section</span></span>

- [<span data-ttu-id="61478-114">Магистральные линии SIP в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="61478-114">SIP trunking in Skype for Business Server</span></span>](sip-trunking.md)
    
- [<span data-ttu-id="61478-115">Прямая связь по SIP в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="61478-115">Direct SIP connections in Skype for Business Server</span></span>](direct-sip.md)
    
- [<span data-ttu-id="61478-116">М:Н магистраль в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="61478-116">M:N trunk in Skype for Business Server</span></span>](m-n-trunk.md)
    
- [<span data-ttu-id="61478-117">Правила трансляции в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="61478-117">Translation rules in Skype for Business Server</span></span>](translation-rules.md)
    
- [<span data-ttu-id="61478-118">Планирование исходящей голосовой маршрутизации в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="61478-118">Plan for outbound voice routing in Skype for Business Server</span></span>](outbound-voice-routing.md)
    

