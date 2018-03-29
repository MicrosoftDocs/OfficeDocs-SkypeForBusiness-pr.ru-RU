---
title: Отслеживание использования службы Mobility Service и UCWA в Skype для бизнеса Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8389b37a-ca3e-4047-8b51-85bc07da87e8
description: 'Сводка: Управление Mobility Service (Mcx) и веб-API (UCWA) объединенных коммуникаций в Скайп для Business Server 2015.'
ms.openlocfilehash: e71d18fe90eb9a7f2fd7b6563e6d6930f2473e74
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="monitor-mobility-service-and-ucwa-usage-in-skype-for-business-server-2015"></a><span data-ttu-id="30283-103">Отслеживание использования службы Mobility Service и UCWA в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="30283-103">Monitor Mobility Service and UCWA usage in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="30283-104">**Сводка:** Управление Mobility Service (Mcx) и веб-API (UCWA) объединенных коммуникаций в Скайп Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="30283-104">**Summary:** Manage the Mobility Service (Mcx) and the Unified Communications Web API (UCWA) in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="30283-105">На постоянной основе следует отслеживать ЦП и памяти, используемый Скайп для службы Mobility Business Server (Mcx) и Unified Communications Web API (UCWA).</span><span class="sxs-lookup"><span data-stu-id="30283-105">On an ongoing basis, you should monitor the CPU and memory that is used by the Skype for Business Server Mobility Service (Mcx) and the Unified Communications Web API (UCWA).</span></span> <span data-ttu-id="30283-106">Чтобы отслеживать использование, прибегите к одному из следующих способов:</span><span class="sxs-lookup"><span data-stu-id="30283-106">To monitor usage, you can use the following:</span></span>
  
 <span data-ttu-id="30283-107">**Для веб-интерфейса API объединенных коммуникаций (UCWA):**</span><span class="sxs-lookup"><span data-stu-id="30283-107">**For Unified Communications Web API (UCWA):**</span></span>
  
- <span data-ttu-id="30283-108">Рабочий процесс **LyncUcwa** в диспетчере Internet Information Services (IIS).</span><span class="sxs-lookup"><span data-stu-id="30283-108">The **LyncUcwa** worker process in Internet Information Services (IIS) Manager.</span></span> <span data-ttu-id="30283-109">На панели **Рабочие процессы** изучите столбцы **ЦП %** и **Частные байты (КБ)** (память).</span><span class="sxs-lookup"><span data-stu-id="30283-109">In the **Worker Processes** pane, look at the **CPU %** and **Private Bytes (KB)** (memory) columns.</span></span>
    
- <span data-ttu-id="30283-110">Счетчики производительности **ЦП** и **Процессор**.</span><span class="sxs-lookup"><span data-stu-id="30283-110">The **CPU** and **Processor** performance counters.</span></span>
    
<span data-ttu-id="30283-111">В большинстве развертываний ресурсы ЦП, задействованные UCWA, не должны в среднем превышать 15 %.</span><span class="sxs-lookup"><span data-stu-id="30283-111">For most deployments, UCWA CPU usage should be below 15 percent on average.</span></span> <span data-ttu-id="30283-112">Использование памяти следует попадают в рамках, описанных в [мониторе ограничений емкости памяти сервера в Скайп для Business Server 2015](server-memory-capacity-limits.md).</span><span class="sxs-lookup"><span data-stu-id="30283-112">Memory usage should fall within the limits described in [Monitor for server memory capacity limits in Skype for Business Server 2015](server-memory-capacity-limits.md).</span></span>
  
<span data-ttu-id="30283-113">Помимо счетчиков использования ЦП и памяти можно использовать следующие счетчики производительности, которые позволят определить степень перегрузки сервера запросами:</span><span class="sxs-lookup"><span data-stu-id="30283-113">In addition to CPU and memory usage counters, you can use the following performance counters to help determine when a server is overloaded with requests:</span></span>
  
- <span data-ttu-id="30283-114">**LS:WEB - регулирование и Authentication\WEB — общее количество запросов в обработке**, который указывает число ожидающих веб-запросов на сервере.</span><span class="sxs-lookup"><span data-stu-id="30283-114">**LS:WEB - Throttling and Authentication\WEB - Total Requests in Processing**, which indicates the number of pending web requests on the server.</span></span> <span data-ttu-id="30283-115">Если этот счетчик достигает 10 000, последующие запросы завершаются с ошибкой "503 — служба недоступна".</span><span class="sxs-lookup"><span data-stu-id="30283-115">When this counter reaches 10,000, subsequent requests will fail, with the error message, "503 - Service Unavailable."</span></span>
    
- <span data-ttu-id="30283-116">**ASP.NET\Requests Queued** (всегда должно быть равно нулю).</span><span class="sxs-lookup"><span data-stu-id="30283-116">**ASP.NET\Requests Queued** (should always be zero).</span></span>
    
> [!NOTE]
> <span data-ttu-id="30283-117">При достижении или превышении этих значений следует вернуться к планированию мощности и повторно выполнить расчет, чтобы определить правильные значения тактовой частоты ЦП, числа ядер и объема памяти для компьютеров, на которых размещаются веб-службы.</span><span class="sxs-lookup"><span data-stu-id="30283-117">If you meet or exceed these values, you should revisit and re-compute your capacity planning for the correct sizing of CPU, number of cores and memory for the computers hosting the web services.</span></span> 
  
 <span data-ttu-id="30283-118">**Для службы Mobility Service (Mcx):**</span><span class="sxs-lookup"><span data-stu-id="30283-118">**For the Mobility Service (Mcx):**</span></span>
  
- <span data-ttu-id="30283-119">**CSIntMcxAppPool** и **CSExtMcxAppPool** рабочие процессы в диспетчере Internet Information Services (IIS).</span><span class="sxs-lookup"><span data-stu-id="30283-119">The **CSIntMcxAppPool** and **CSExtMcxAppPool** worker processes in Internet Information Services (IIS) Manager.</span></span> <span data-ttu-id="30283-120">На панели **Рабочие процессы** изучите столбцы **ЦП %** и **Частные байты (КБ)** (память).</span><span class="sxs-lookup"><span data-stu-id="30283-120">In the **Worker Processes** pane, look at the **CPU %** and **Private Bytes (KB)** (memory) columns.</span></span>
    
- <span data-ttu-id="30283-121">Счетчики производительности **ЦП** и **Процессор**.</span><span class="sxs-lookup"><span data-stu-id="30283-121">The **CPU** and **Processor** performance counters.</span></span>
    
<span data-ttu-id="30283-122">В большинстве развертываний ресурсы ЦП, задействованные службой Mobility Service, не должны в среднем превышать 15 %.</span><span class="sxs-lookup"><span data-stu-id="30283-122">For most deployments, Mobility Service CPU usage should be below 15 percent, on average.</span></span> <span data-ttu-id="30283-123">Использование памяти следует попадают в рамках, описанных в [мониторе ограничений емкости памяти сервера в Скайп для Business Server 2015](server-memory-capacity-limits.md).</span><span class="sxs-lookup"><span data-stu-id="30283-123">Memory usage should fall within the limits described in [Monitor for server memory capacity limits in Skype for Business Server 2015](server-memory-capacity-limits.md).</span></span>
  
<span data-ttu-id="30283-124">Помимо счетчиков производительности ЦП и памяти можно использовать следующие счетчики производительности ASP.NET, которые позволят определить степень перегрузки сервера запросами.</span><span class="sxs-lookup"><span data-stu-id="30283-124">In addition to CPU and memory usage counters, you can use the following ASP.NET performance counters to help determine when a server is overloaded with requests:</span></span>
  
- <span data-ttu-id="30283-125">**ASP.NET v2.0.50727\Requests текущего**, который указывает число ожидающих веб-запросов на сервере.</span><span class="sxs-lookup"><span data-stu-id="30283-125">**ASP.NET v2.0.50727\Requests Current**, which indicates the number of pending web requests on the server.</span></span> <span data-ttu-id="30283-126">Если этот счетчик достигает 5 000, последующие запросы завершаются с ошибкой "503 — служба недоступна".</span><span class="sxs-lookup"><span data-stu-id="30283-126">When this counter reaches 5,000, subsequent requests will fail with the error message, "503 - Service Unavailable."</span></span>
    
- <span data-ttu-id="30283-127">**ASP.NET\Requests Queued** (всегда должно быть равно нулю).</span><span class="sxs-lookup"><span data-stu-id="30283-127">**ASP.NET\Requests Queued** (should always be zero).</span></span>
    
> [!NOTE]
> <span data-ttu-id="30283-128">При достижении или превышении этих значений следует вернуться к планированию мощности и повторно выполнить расчет, чтобы определить правильные значения тактовой частоты ЦП, числа ядер и объема памяти для компьютеров, на которых размещаются веб-службы.</span><span class="sxs-lookup"><span data-stu-id="30283-128">If you meet or exceed these values, you should revisit and recompute your capacity planning for the correct sizing of CPU, number of cores, and memory for the computers hosting the web services.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="30283-129">См. также</span><span class="sxs-lookup"><span data-stu-id="30283-129">See also</span></span>

#### 

[<span data-ttu-id="30283-130">Монитор ограничений емкости памяти сервера в Скайп для Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="30283-130">Monitor for server memory capacity limits in Skype for Business Server 2015</span></span>](server-memory-capacity-limits.md)

