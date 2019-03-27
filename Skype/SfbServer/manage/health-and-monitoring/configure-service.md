---
title: Настройка службы мобильности для повышения производительности в Скайп для Business Server
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c2b8aadb-cffb-49f0-ba7a-e8541a1ff475
description: ': Сводка сведения о службе мобильности в Скайп для Business Server.'
ms.openlocfilehash: 3e3f0df7550a64236335108453f0c35d902a1713
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2019
ms.locfileid: "30876410"
---
# <a name="configure-mobility-service-for-high-performance-in-skype-for-business-server"></a><span data-ttu-id="b0ac3-103">Настройка службы мобильности для повышения производительности в Скайп для Business Server</span><span class="sxs-lookup"><span data-stu-id="b0ac3-103">Configure Mobility Service for high performance in Skype for Business Server</span></span>
 
<span data-ttu-id="b0ac3-104">**Сводка:** Сведения о службе мобильности в Скайп для Business Server.</span><span class="sxs-lookup"><span data-stu-id="b0ac3-104">**Summary:** Learn about the Mobility Service in Skype for Business Server.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="b0ac3-105">В этом разделе относятся только к Скайп для службы Mobility Business Server (Mcx) и не применяется к Unified Communications Web API (UCWA), как в накопительные пакеты обновления для Lync Server 2013: февраля 2013 г.</span><span class="sxs-lookup"><span data-stu-id="b0ac3-105">This topic applies only to the Skype for Business Server Mobility Service (Mcx), and does not apply to Unified Communications Web API (UCWA), as delivered in the Cumulative Updates for Lync Server 2013: February 2013.</span></span> 
  
<span data-ttu-id="b0ac3-106">При установке службы мобильной связи (Mcx) на Internet Information Services (IIS) 7.5 установщика Mobility Service настраивает некоторые параметры производительности на сервере переднего плана.</span><span class="sxs-lookup"><span data-stu-id="b0ac3-106">When you install the Mobility Service (Mcx) on Internet Information Services (IIS) 7.5, the Mobility Service installer configures some performance settings on the Front End Server.</span></span> <span data-ttu-id="b0ac3-107">We recommend that you use IIS 7.5 for mobility.</span><span class="sxs-lookup"><span data-stu-id="b0ac3-107">We recommend that you use IIS 7.5 for mobility.</span></span> <span data-ttu-id="b0ac3-108">The settings affect the maximum number of concurrent user requests and the maximum number of threads that are allowed for the Mobility Service.</span><span class="sxs-lookup"><span data-stu-id="b0ac3-108">The settings affect the maximum number of concurrent user requests and the maximum number of threads that are allowed for the Mobility Service.</span></span>
  
<span data-ttu-id="b0ac3-109">Далее представлены параметры производительности:</span><span class="sxs-lookup"><span data-stu-id="b0ac3-109">Here are the performance settings:</span></span>
  
### <a name="settings-for-mcx-on-iis-75"></a><span data-ttu-id="b0ac3-110">Параметры для Mcx в службе IIS 7.5</span><span class="sxs-lookup"><span data-stu-id="b0ac3-110">Settings for Mcx on IIS 7.5</span></span>

1. <span data-ttu-id="b0ac3-111">**maxConcurrentThreadsPerCPU** имеет значение нуля (0).</span><span class="sxs-lookup"><span data-stu-id="b0ac3-111">**maxConcurrentThreadsPerCPU** is set to zero (0).</span></span>
    
2. <span data-ttu-id="b0ac3-112">**maxConcurrentRequestsPerCPU** имеет значение нуля (0).</span><span class="sxs-lookup"><span data-stu-id="b0ac3-112">**maxConcurrentRequestsPerCPU** is set to zero (0).</span></span>
    
3. <span data-ttu-id="b0ac3-113">Процессная модель ASP.NET имеет значение AutoConfig (только для IIS 7.5).</span><span class="sxs-lookup"><span data-stu-id="b0ac3-113">ASP.NET process model is set to AutoConfig (for IIS 7.5 only).</span></span>
    
4. <span data-ttu-id="b0ac3-114">Предел очереди HTTP.sys имеет значение 1000 (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="b0ac3-114">HTTP.sys queue limit is set to 1,000 (by default).</span></span>
    

