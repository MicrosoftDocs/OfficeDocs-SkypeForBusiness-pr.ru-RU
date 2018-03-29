---
title: Настройка высокой производительности службы Mobility Service в Skype для бизнеса Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c2b8aadb-cffb-49f0-ba7a-e8541a1ff475
description: ': Сводка сведения о службе мобильности в Скайп для Business Server 2015.'
ms.openlocfilehash: 12f64ed75195bb94365686d76cdfca841e6c9c8e
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="configure-mobility-service-for-high-performance-in-skype-for-business-server-2015"></a><span data-ttu-id="abd87-103">Настройка высокой производительности службы Mobility Service в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="abd87-103">Configure Mobility Service for high performance in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="abd87-104">**Сводка:** Сведения о службе мобильности в Скайп для Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="abd87-104">**Summary:** Learn about the Mobility Service in Skype for Business Server 2015.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="abd87-105">В этом разделе относятся только к Скайп для службы Mobility 2015 Business Server (Mcx) и не применяется к Unified Communications Web API (UCWA), как в накопительные пакеты обновления для Lync Server 2013: февраля 2013 г.</span><span class="sxs-lookup"><span data-stu-id="abd87-105">This topic applies only to the Skype for Business Server 2015 Mobility Service (Mcx), and does not apply to Unified Communications Web API (UCWA), as delivered in the Cumulative Updates for Lync Server 2013: February 2013.</span></span> 
  
<span data-ttu-id="abd87-106">При установке службы мобильной связи (Mcx) на Internet Information Services (IIS) 7.5 установщика Mobility Service настраивает некоторые параметры производительности на сервере переднего плана.</span><span class="sxs-lookup"><span data-stu-id="abd87-106">When you install the Mobility Service (Mcx) on Internet Information Services (IIS) 7.5, the Mobility Service installer configures some performance settings on the Front End Server.</span></span> <span data-ttu-id="abd87-107">Мы рекомендуем использовать IIS 7.5 для мобильных устройств.</span><span class="sxs-lookup"><span data-stu-id="abd87-107">We recommend that you use IIS 7.5 for mobility.</span></span> <span data-ttu-id="abd87-108">Параметры влияют на максимальное число параллельных пользователей запросов и максимальное число потоков, разрешенных для службы Mobility Service.</span><span class="sxs-lookup"><span data-stu-id="abd87-108">The settings affect the maximum number of concurrent user requests and the maximum number of threads that are allowed for the Mobility Service.</span></span>
  
<span data-ttu-id="abd87-109">Далее представлены параметры производительности:</span><span class="sxs-lookup"><span data-stu-id="abd87-109">Here are the performance settings:</span></span>
  
### <a name="settings-for-mcx-on-iis-75"></a><span data-ttu-id="abd87-110">Параметры для Mcx в службе IIS 7.5</span><span class="sxs-lookup"><span data-stu-id="abd87-110">Settings for Mcx on IIS 7.5</span></span>

1. <span data-ttu-id="abd87-111">**maxConcurrentThreadsPerCPU** имеет значение нуль (0).</span><span class="sxs-lookup"><span data-stu-id="abd87-111">**maxConcurrentThreadsPerCPU** is set to zero (0).</span></span>
    
2. <span data-ttu-id="abd87-112">**maxConcurrentRequestsPerCPU** имеет значение нуль (0).</span><span class="sxs-lookup"><span data-stu-id="abd87-112">**maxConcurrentRequestsPerCPU** is set to zero (0).</span></span>
    
3. <span data-ttu-id="abd87-113">Процессная модель ASP.NET имеет значение AutoConfig (только для IIS 7.5).</span><span class="sxs-lookup"><span data-stu-id="abd87-113">ASP.NET process model is set to AutoConfig (for IIS 7.5 only).</span></span>
    
4. <span data-ttu-id="abd87-114">Предел очереди HTTP.sys имеет значение 1000 (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="abd87-114">HTTP.sys queue limit is set to 1,000 (by default).</span></span>
    

