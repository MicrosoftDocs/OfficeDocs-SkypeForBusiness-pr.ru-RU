---
title: Настройка службы Mobility Service для высокой производительности в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: c2b8aadb-cffb-49f0-ba7a-e8541a1ff475
description: Сводка. Сведения о службе Mobility Service в Skype для бизнеса Server.
ms.openlocfilehash: 83d8d6dc7a32b05a58c738deddc8c92e43bd5557
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817039"
---
# <a name="configure-mobility-service-for-high-performance-in-skype-for-business-server"></a><span data-ttu-id="071aa-103">Настройка службы Mobility Service для высокой производительности в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="071aa-103">Configure Mobility Service for high performance in Skype for Business Server</span></span>
 
<span data-ttu-id="071aa-104">**Сводка:** Узнайте о службе Mobility Service в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="071aa-104">**Summary:** Learn about the Mobility Service in Skype for Business Server.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="071aa-105">Этот раздел относится только к Skype для бизнеса Server Mobility Service (Mcx) и не относится к веб-API объединенных коммуникаций (UCWA), как пошаговые обновления для Lync Server 2013: февраль 2013 г.</span><span class="sxs-lookup"><span data-stu-id="071aa-105">This topic applies only to the Skype for Business Server Mobility Service (Mcx), and does not apply to Unified Communications Web API (UCWA), as delivered in the Cumulative Updates for Lync Server 2013: February 2013.</span></span> 
  
<span data-ttu-id="071aa-106">При установке службы Mobility Service (Mcx) в службах IIS 7.5 установщик Службы Mobility Service настраивает некоторые параметры производительности на сервере переднего сервера.</span><span class="sxs-lookup"><span data-stu-id="071aa-106">When you install the Mobility Service (Mcx) on Internet Information Services (IIS) 7.5, the Mobility Service installer configures some performance settings on the Front End Server.</span></span> <span data-ttu-id="071aa-107">Мы рекомендуем использовать IIS 7.5 для Mobility Service.</span><span class="sxs-lookup"><span data-stu-id="071aa-107">We recommend that you use IIS 7.5 for mobility.</span></span> <span data-ttu-id="071aa-108">Параметры влияют на максимальное число одновременных запросов пользователей и максимальное число потоков, которые разрешены для Mobility Service.</span><span class="sxs-lookup"><span data-stu-id="071aa-108">The settings affect the maximum number of concurrent user requests and the maximum number of threads that are allowed for the Mobility Service.</span></span>
  
<span data-ttu-id="071aa-109">Ниже параметров производительности.</span><span class="sxs-lookup"><span data-stu-id="071aa-109">Here are the performance settings:</span></span>
  
### <a name="settings-for-mcx-on-iis-75"></a><span data-ttu-id="071aa-110">Параметры для Mcx в IIS 7.5</span><span class="sxs-lookup"><span data-stu-id="071aa-110">Settings for Mcx on IIS 7.5</span></span>

1. <span data-ttu-id="071aa-111">**maxConcurrentThreadsPerCPU** имеет значение нуль (0).</span><span class="sxs-lookup"><span data-stu-id="071aa-111">**maxConcurrentThreadsPerCPU** is set to zero (0).</span></span>
    
2. <span data-ttu-id="071aa-112">**maxConcurrentRequestsPerCPU** имеет значение нуль (0).</span><span class="sxs-lookup"><span data-stu-id="071aa-112">**maxConcurrentRequestsPerCPU** is set to zero (0).</span></span>
    
3. <span data-ttu-id="071aa-113">Процессная модель ASP.NET имеет значение AutoConfig (только для IIS 7.5).</span><span class="sxs-lookup"><span data-stu-id="071aa-113">ASP.NET process model is set to AutoConfig (for IIS 7.5 only).</span></span>
    
4. <span data-ttu-id="071aa-114">Предел очереди HTTP.sys имеет значение 1000 (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="071aa-114">HTTP.sys queue limit is set to 1,000 (by default).</span></span>
    

