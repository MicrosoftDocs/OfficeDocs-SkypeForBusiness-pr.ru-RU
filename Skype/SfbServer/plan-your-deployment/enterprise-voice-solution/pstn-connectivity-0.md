---
title: Планирование подключения к STN в Skype для бизнеса Server
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
ms.assetid: 280f684a-740a-443d-8ecf-574241382a42
description: Планирование подключения к STN в Корпоративная голосовая связь Skype для бизнеса Server.
ms.openlocfilehash: 492f4e2cc71644cb1e9957f407a549cce5dbc31d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813569"
---
# <a name="plan-for-pstn-connectivity-in-skype-for-business-server"></a><span data-ttu-id="79072-103">Планирование подключения к STN в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="79072-103">Plan for PSTN connectivity in Skype for Business Server</span></span>
 
<span data-ttu-id="79072-104">Планирование подключения к STN в Корпоративная голосовая связь Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="79072-104">Plan for PSTN connectivity in Enterprise Voice in Skype for Business Server.</span></span>
  
<span data-ttu-id="79072-105">Решение VoIP корпоративного уровня должно обеспечивать вызовы в телефонную сеть общего пользования (ТСОП) и обратно без ухудшения качества обслуживания (QoS).</span><span class="sxs-lookup"><span data-stu-id="79072-105">An enterprise-grade VoIP solution must provide for calls to and from the public switched telephone network (PSTN) without any decline in Quality of Service (QoS).</span></span> <span data-ttu-id="79072-106">Пользователи, которые звонят и получают звонки, не должны знать об этой технологии: с точки зрения пользователя вызов между инфраструктурой Корпоративная голосовая связь и STN должен выглядеть как другой телефонный звонок.</span><span class="sxs-lookup"><span data-stu-id="79072-106">Users who place and receive calls should not be aware of the underlying technology: from the user's perspective, a call between the Enterprise Voice infrastructure and the PSTN should seem like just another phone call.</span></span>
  
<span data-ttu-id="79072-107">Skype для бизнеса Server обеспечивает надежное масштабируемое подключение к STN с помощью следующих параметров:</span><span class="sxs-lookup"><span data-stu-id="79072-107">Skype for Business Server provides reliable, scalable PSTN connectivity by using the following options:</span></span>
  
- <span data-ttu-id="79072-108">**SIP-магистрали** для поставщика услуг Интернет-телефонии (ITSP);</span><span class="sxs-lookup"><span data-stu-id="79072-108">**SIP trunks** to an Internet telephony service provider (ITSP)</span></span>
    
- <span data-ttu-id="79072-109">**прямые SIP-подключения** для шлюза ТСОП;</span><span class="sxs-lookup"><span data-stu-id="79072-109">**Direct SIP connections** to a PSTN gateway</span></span>
    
- <span data-ttu-id="79072-110">**прямые SIP-подключения** для УАТС.</span><span class="sxs-lookup"><span data-stu-id="79072-110">**Direct SIP connections** to a PBX</span></span>
    
<span data-ttu-id="79072-111">В зависимости от размера, географического покрытия и существующей инфраструктуры системы голосовой связи предприятия могут использовать один, два или даже все три этих варианта в различных местоположениях.</span><span class="sxs-lookup"><span data-stu-id="79072-111">Depending on its size, geographic coverage, and existing voice infrastructure, an enterprise may use one, two, or even all three of these options at various locations.</span></span> <span data-ttu-id="79072-112">Подробные сведения об этих параметрах см. в следующих разделах.</span><span class="sxs-lookup"><span data-stu-id="79072-112">For details about these options, see the following sections.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="79072-113">В этом разделе:</span><span class="sxs-lookup"><span data-stu-id="79072-113">In this section</span></span>

- [<span data-ttu-id="79072-114">Транкинг SIP в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="79072-114">SIP trunking in Skype for Business Server</span></span>](sip-trunking.md)
    
- [<span data-ttu-id="79072-115">Прямые подключения SIP в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="79072-115">Direct SIP connections in Skype for Business Server</span></span>](direct-sip.md)
    
- [<span data-ttu-id="79072-116">Магистраль M:N в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="79072-116">M:N trunk in Skype for Business Server</span></span>](m-n-trunk.md)
    
- [<span data-ttu-id="79072-117">Правила трансляции в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="79072-117">Translation rules in Skype for Business Server</span></span>](translation-rules.md)
    
- [<span data-ttu-id="79072-118">Планирование маршрутной исходящие голосовой почты в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="79072-118">Plan for outbound voice routing in Skype for Business Server</span></span>](outbound-voice-routing.md)
    

