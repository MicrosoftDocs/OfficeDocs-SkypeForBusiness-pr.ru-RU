---
title: Мониторинг использования службы Mobility Service и UCWA в Скайп для Business Server
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8389b37a-ca3e-4047-8b51-85bc07da87e8
description: 'Сводка: Управление Mobility Service (Mcx) и веб-объединенных коммуникаций API (UCWA) в Скайп для Business Server.'
ms.openlocfilehash: 780d8fca068a78ec08312551d03dbdb5327df90e
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2018
ms.locfileid: "20975951"
---
# <a name="monitor-mobility-service-and-ucwa-usage-in-skype-for-business-server"></a><span data-ttu-id="8bb46-103">Мониторинг использования службы Mobility Service и UCWA в Скайп для Business Server</span><span class="sxs-lookup"><span data-stu-id="8bb46-103">Monitor Mobility Service and UCWA usage in Skype for Business Server</span></span>
 
<span data-ttu-id="8bb46-104">**Сводка:** Управление Mobility Service (Mcx) и веб-объединенных коммуникаций API (UCWA) в Скайп для Business Server.</span><span class="sxs-lookup"><span data-stu-id="8bb46-104">**Summary:** Manage the Mobility Service (Mcx) and the Unified Communications Web API (UCWA) in Skype for Business Server.</span></span>

> [!NOTE]
> <span data-ttu-id="8bb46-105">Поддержка MCX для устаревших мобильных клиентов больше не доступен в Скайп для Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="8bb46-105">MCX support for legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="8bb46-106">Пользователям необходимо обновить до текущего клиента.</span><span class="sxs-lookup"><span data-stu-id="8bb46-106">Your users will need to upgrade to a current client.</span></span>
  
<span data-ttu-id="8bb46-107">На постоянной основе следует отслеживать ЦП и памяти, используемый Скайп для службы Mobility Business Server (Mcx) и Unified Communications Web API (UCWA).</span><span class="sxs-lookup"><span data-stu-id="8bb46-107">On an ongoing basis, you should monitor the CPU and memory that is used by the Skype for Business Server Mobility Service (Mcx) and the Unified Communications Web API (UCWA).</span></span> <span data-ttu-id="8bb46-108">Чтобы отслеживать использование, прибегите к одному из следующих способов:</span><span class="sxs-lookup"><span data-stu-id="8bb46-108">To monitor usage, you can use the following:</span></span>
  
 <span data-ttu-id="8bb46-109">**Для веб-интерфейса API объединенных коммуникаций (UCWA):**</span><span class="sxs-lookup"><span data-stu-id="8bb46-109">**For Unified Communications Web API (UCWA):**</span></span>
  
- <span data-ttu-id="8bb46-110">Рабочий процесс **LyncUcwa** в диспетчере Internet Information Services (IIS).</span><span class="sxs-lookup"><span data-stu-id="8bb46-110">The **LyncUcwa** worker process in Internet Information Services (IIS) Manager.</span></span> <span data-ttu-id="8bb46-111">На панели **Рабочие процессы** изучите столбцы **ЦП %** и **Частные байты (КБ)** (память).</span><span class="sxs-lookup"><span data-stu-id="8bb46-111">In the **Worker Processes** pane, look at the **CPU %** and **Private Bytes (KB)** (memory) columns.</span></span>
    
- <span data-ttu-id="8bb46-112">Счетчики производительности **ЦП** и **Процессор**.</span><span class="sxs-lookup"><span data-stu-id="8bb46-112">The **CPU** and **Processor** performance counters.</span></span>
    
<span data-ttu-id="8bb46-113">В большинстве развертываний ресурсы ЦП, задействованные UCWA, не должны в среднем превышать 15 %.</span><span class="sxs-lookup"><span data-stu-id="8bb46-113">For most deployments, UCWA CPU usage should be below 15 percent on average.</span></span> <span data-ttu-id="8bb46-114">Использование памяти следует попадают в рамках, описанных в [мониторе ограничений емкости памяти сервера в Скайп для Business Server](server-memory-capacity-limits.md).</span><span class="sxs-lookup"><span data-stu-id="8bb46-114">Memory usage should fall within the limits described in [Monitor for server memory capacity limits in Skype for Business Server](server-memory-capacity-limits.md).</span></span>
  
<span data-ttu-id="8bb46-115">Помимо счетчиков использования ЦП и памяти можно использовать следующие счетчики производительности, которые позволят определить степень перегрузки сервера запросами:</span><span class="sxs-lookup"><span data-stu-id="8bb46-115">In addition to CPU and memory usage counters, you can use the following performance counters to help determine when a server is overloaded with requests:</span></span>
  
- <span data-ttu-id="8bb46-116">**LS:WEB - регулирование и Authentication\WEB — общее количество запросов в обработке**, который указывает число ожидающих веб-запросов на сервере.</span><span class="sxs-lookup"><span data-stu-id="8bb46-116">**LS:WEB - Throttling and Authentication\WEB - Total Requests in Processing**, which indicates the number of pending web requests on the server.</span></span> <span data-ttu-id="8bb46-117">Если этот счетчик достигает 10 000, последующие запросы завершаются с ошибкой "503 — служба недоступна".</span><span class="sxs-lookup"><span data-stu-id="8bb46-117">When this counter reaches 10,000, subsequent requests will fail, with the error message, "503 - Service Unavailable."</span></span>
    
- <span data-ttu-id="8bb46-118">**ASP.NET\Requests Queued** (всегда должно быть равно нулю).</span><span class="sxs-lookup"><span data-stu-id="8bb46-118">**ASP.NET\Requests Queued** (should always be zero).</span></span>
    
> [!NOTE]
> <span data-ttu-id="8bb46-119">При достижении или превышении этих значений следует вернуться к планированию мощности и повторно выполнить расчет, чтобы определить правильные значения тактовой частоты ЦП, числа ядер и объема памяти для компьютеров, на которых размещаются веб-службы.</span><span class="sxs-lookup"><span data-stu-id="8bb46-119">If you meet or exceed these values, you should revisit and re-compute your capacity planning for the correct sizing of CPU, number of cores and memory for the computers hosting the web services.</span></span> 
  
 <span data-ttu-id="8bb46-120">**Для службы Mobility Service (Mcx):**</span><span class="sxs-lookup"><span data-stu-id="8bb46-120">**For the Mobility Service (Mcx):**</span></span>
  
- <span data-ttu-id="8bb46-121">**CSIntMcxAppPool** и **CSExtMcxAppPool** рабочие процессы в диспетчере Internet Information Services (IIS).</span><span class="sxs-lookup"><span data-stu-id="8bb46-121">The **CSIntMcxAppPool** and **CSExtMcxAppPool** worker processes in Internet Information Services (IIS) Manager.</span></span> <span data-ttu-id="8bb46-122">На панели **Рабочие процессы** изучите столбцы **ЦП %** и **Частные байты (КБ)** (память).</span><span class="sxs-lookup"><span data-stu-id="8bb46-122">In the **Worker Processes** pane, look at the **CPU %** and **Private Bytes (KB)** (memory) columns.</span></span>
    
- <span data-ttu-id="8bb46-123">Счетчики производительности **ЦП** и **Процессор**.</span><span class="sxs-lookup"><span data-stu-id="8bb46-123">The **CPU** and **Processor** performance counters.</span></span>
    
<span data-ttu-id="8bb46-124">В большинстве развертываний ресурсы ЦП, задействованные службой Mobility Service, не должны в среднем превышать 15 %.</span><span class="sxs-lookup"><span data-stu-id="8bb46-124">For most deployments, Mobility Service CPU usage should be below 15 percent, on average.</span></span> <span data-ttu-id="8bb46-125">Использование памяти следует попадают в рамках, описанных в [мониторе ограничений емкости памяти сервера в Скайп для Business Server](server-memory-capacity-limits.md).</span><span class="sxs-lookup"><span data-stu-id="8bb46-125">Memory usage should fall within the limits described in [Monitor for server memory capacity limits in Skype for Business Server](server-memory-capacity-limits.md).</span></span>
  
<span data-ttu-id="8bb46-126">Помимо счетчиков производительности ЦП и памяти можно использовать следующие счетчики производительности ASP.NET, которые позволят определить степень перегрузки сервера запросами.</span><span class="sxs-lookup"><span data-stu-id="8bb46-126">In addition to CPU and memory usage counters, you can use the following ASP.NET performance counters to help determine when a server is overloaded with requests:</span></span>
  
- <span data-ttu-id="8bb46-127">**ASP.NET v2.0.50727\Requests текущего**, который указывает число ожидающих веб-запросов на сервере.</span><span class="sxs-lookup"><span data-stu-id="8bb46-127">**ASP.NET v2.0.50727\Requests Current**, which indicates the number of pending web requests on the server.</span></span> <span data-ttu-id="8bb46-128">Если этот счетчик достигает 5 000, последующие запросы завершаются с ошибкой "503 — служба недоступна".</span><span class="sxs-lookup"><span data-stu-id="8bb46-128">When this counter reaches 5,000, subsequent requests will fail with the error message, "503 - Service Unavailable."</span></span>
    
- <span data-ttu-id="8bb46-129">**ASP.NET\Requests Queued** (всегда должно быть равно нулю).</span><span class="sxs-lookup"><span data-stu-id="8bb46-129">**ASP.NET\Requests Queued** (should always be zero).</span></span>
    
> [!NOTE]
> <span data-ttu-id="8bb46-130">При достижении или превышении этих значений следует вернуться к планированию мощности и повторно выполнить расчет, чтобы определить правильные значения тактовой частоты ЦП, числа ядер и объема памяти для компьютеров, на которых размещаются веб-службы.</span><span class="sxs-lookup"><span data-stu-id="8bb46-130">If you meet or exceed these values, you should revisit and recompute your capacity planning for the correct sizing of CPU, number of cores, and memory for the computers hosting the web services.</span></span> 

> [!NOTE]
> <span data-ttu-id="8bb46-131">Поддержка MCX для устаревших мобильных клиентов больше не доступен в Скайп для Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="8bb46-131">MCX support for legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="8bb46-132">Пользователям необходимо обновить до текущего клиента.</span><span class="sxs-lookup"><span data-stu-id="8bb46-132">Your users will need to upgrade to a current client.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="8bb46-133">См. также</span><span class="sxs-lookup"><span data-stu-id="8bb46-133">See also</span></span>

[<span data-ttu-id="8bb46-134">Монитор ограничений емкости памяти сервера в Скайп для Business Server</span><span class="sxs-lookup"><span data-stu-id="8bb46-134">Monitor for server memory capacity limits in Skype for Business Server</span></span>](server-memory-capacity-limits.md)