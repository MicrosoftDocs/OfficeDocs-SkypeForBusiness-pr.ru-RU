---
title: Настройка службы Mobility Service для высокой производительности в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c2b8aadb-cffb-49f0-ba7a-e8541a1ff475
description: 'Сводка: сведения о службе Mobility Service в Skype для бизнеса Server.'
ms.openlocfilehash: 35e04fa080964495ccd9abed28c0688dd7be45a9
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34305845"
---
# <a name="configure-mobility-service-for-high-performance-in-skype-for-business-server"></a><span data-ttu-id="73405-103">Настройка службы Mobility Service для высокой производительности в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="73405-103">Configure Mobility Service for high performance in Skype for Business Server</span></span>
 
<span data-ttu-id="73405-104">**Сводка:** Узнайте о службе Mobility Service в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="73405-104">**Summary:** Learn about the Mobility Service in Skype for Business Server.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="73405-105">Этот раздел относится только к службе Mobility Service в Skype для бизнеса Server (МККС) и не применяется к веб-API единой системы обмена сообщениями (УКВА), как доставляется в накопительные обновления для Lync Server 2013: Февраль 2013.</span><span class="sxs-lookup"><span data-stu-id="73405-105">This topic applies only to the Skype for Business Server Mobility Service (Mcx), and does not apply to Unified Communications Web API (UCWA), as delivered in the Cumulative Updates for Lync Server 2013: February 2013.</span></span> 
  
<span data-ttu-id="73405-106">При установке службы Mobility Service (МККС) в службах IIS 7,5 программа установки службы Mobility Service настраивает некоторые параметры быстродействия на сервере переднего плана.</span><span class="sxs-lookup"><span data-stu-id="73405-106">When you install the Mobility Service (Mcx) on Internet Information Services (IIS) 7.5, the Mobility Service installer configures some performance settings on the Front End Server.</span></span> <span data-ttu-id="73405-107">We recommend that you use IIS 7.5 for mobility.</span><span class="sxs-lookup"><span data-stu-id="73405-107">We recommend that you use IIS 7.5 for mobility.</span></span> <span data-ttu-id="73405-108">The settings affect the maximum number of concurrent user requests and the maximum number of threads that are allowed for the Mobility Service.</span><span class="sxs-lookup"><span data-stu-id="73405-108">The settings affect the maximum number of concurrent user requests and the maximum number of threads that are allowed for the Mobility Service.</span></span>
  
<span data-ttu-id="73405-109">Далее представлены параметры производительности:</span><span class="sxs-lookup"><span data-stu-id="73405-109">Here are the performance settings:</span></span>
  
### <a name="settings-for-mcx-on-iis-75"></a><span data-ttu-id="73405-110">Параметры для Mcx в службе IIS 7.5</span><span class="sxs-lookup"><span data-stu-id="73405-110">Settings for Mcx on IIS 7.5</span></span>

1. <span data-ttu-id="73405-111">**maxConcurrentThreadsPerCPU** имеет значение нуля (0).</span><span class="sxs-lookup"><span data-stu-id="73405-111">**maxConcurrentThreadsPerCPU** is set to zero (0).</span></span>
    
2. <span data-ttu-id="73405-112">**maxConcurrentRequestsPerCPU** имеет значение нуля (0).</span><span class="sxs-lookup"><span data-stu-id="73405-112">**maxConcurrentRequestsPerCPU** is set to zero (0).</span></span>
    
3. <span data-ttu-id="73405-113">Процессная модель ASP.NET имеет значение AutoConfig (только для IIS 7.5).</span><span class="sxs-lookup"><span data-stu-id="73405-113">ASP.NET process model is set to AutoConfig (for IIS 7.5 only).</span></span>
    
4. <span data-ttu-id="73405-114">Предел очереди HTTP.sys имеет значение 1000 (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="73405-114">HTTP.sys queue limit is set to 1,000 (by default).</span></span>
    

