---
title: Мониторинг использования службы Mobility Service и UCWA в Скайп для Business Server
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8389b37a-ca3e-4047-8b51-85bc07da87e8
description: 'Сводка: Управление Mobility Service (Mcx) и веб-объединенных коммуникаций API (UCWA) в Скайп для Business Server.'
ms.openlocfilehash: 79516ec6cf5371061a0287e70e6ed81f8b2a5395
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2019
ms.locfileid: "30884952"
---
# <a name="monitor-mobility-service-and-ucwa-usage-in-skype-for-business-server"></a><span data-ttu-id="185a0-103">Мониторинг использования службы Mobility Service и UCWA в Скайп для Business Server</span><span class="sxs-lookup"><span data-stu-id="185a0-103">Monitor Mobility Service and UCWA usage in Skype for Business Server</span></span>
 
<span data-ttu-id="185a0-104">**Сводка:** Управление Mobility Service (Mcx) и веб-объединенных коммуникаций API (UCWA) в Скайп для Business Server.</span><span class="sxs-lookup"><span data-stu-id="185a0-104">**Summary:** Manage the Mobility Service (Mcx) and the Unified Communications Web API (UCWA) in Skype for Business Server.</span></span>

> [!NOTE]
> <span data-ttu-id="185a0-105">Поддержка устаревших мобильных клиентов MCX (Mobility Service) больше не доступен в Скайп для Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="185a0-105">MCX (Mobility Service) support for legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="185a0-106">Все текущей Скайп для мобильных клиентов Business уже используете Unified Communications Web API (UCWA) для поддержки мгновенного обмена Мгновенными сообщениями, сведения о присутствии и контакты.</span><span class="sxs-lookup"><span data-stu-id="185a0-106">All current Skype for Business mobile clients already use Unified Communications Web API (UCWA) to support instant messaging (IM), presence, and contacts.</span></span> <span data-ttu-id="185a0-107">Пользователи с прежних версий клиентов, использующих MCX потребуется обновить до текущего клиента.</span><span class="sxs-lookup"><span data-stu-id="185a0-107">Users with legacy clients using MCX will need to upgrade to a current client.</span></span>
  
<span data-ttu-id="185a0-108">На постоянной основе следует отслеживать ЦП и памяти, используемый Скайп для службы Mobility Business Server (Mcx) и Unified Communications Web API (UCWA).</span><span class="sxs-lookup"><span data-stu-id="185a0-108">On an ongoing basis, you should monitor the CPU and memory that is used by the Skype for Business Server Mobility Service (Mcx) and the Unified Communications Web API (UCWA).</span></span> <span data-ttu-id="185a0-109">Чтобы отслеживать использование, прибегите к одному из следующих способов:</span><span class="sxs-lookup"><span data-stu-id="185a0-109">To monitor usage, you can use the following:</span></span>
  
 <span data-ttu-id="185a0-110">**Для веб-интерфейса API объединенных коммуникаций (UCWA):**</span><span class="sxs-lookup"><span data-stu-id="185a0-110">**For Unified Communications Web API (UCWA):**</span></span>
  
- <span data-ttu-id="185a0-111">Рабочий процесс **LyncUcwa** в диспетчере Internet Information Services (IIS).</span><span class="sxs-lookup"><span data-stu-id="185a0-111">The **LyncUcwa** worker process in Internet Information Services (IIS) Manager.</span></span> <span data-ttu-id="185a0-112">На панели **Рабочие процессы** изучите столбцы **ЦП %** и **Частные байты (КБ)** (память).</span><span class="sxs-lookup"><span data-stu-id="185a0-112">In the **Worker Processes** pane, look at the **CPU %** and **Private Bytes (KB)** (memory) columns.</span></span>
    
- <span data-ttu-id="185a0-113">Счетчики производительности **ЦП** и **Процессор**.</span><span class="sxs-lookup"><span data-stu-id="185a0-113">The **CPU** and **Processor** performance counters.</span></span>
    
<span data-ttu-id="185a0-114">В большинстве развертываний ресурсы ЦП, задействованные UCWA, не должны в среднем превышать 15 %.</span><span class="sxs-lookup"><span data-stu-id="185a0-114">For most deployments, UCWA CPU usage should be below 15 percent on average.</span></span> <span data-ttu-id="185a0-115">Использование памяти следует попадают в рамках, описанных в [мониторе ограничений емкости памяти сервера в Скайп для Business Server](server-memory-capacity-limits.md).</span><span class="sxs-lookup"><span data-stu-id="185a0-115">Memory usage should fall within the limits described in [Monitor for server memory capacity limits in Skype for Business Server](server-memory-capacity-limits.md).</span></span>
  
<span data-ttu-id="185a0-116">Помимо счетчиков использования ЦП и памяти можно использовать следующие счетчики производительности, которые позволят определить степень перегрузки сервера запросами:</span><span class="sxs-lookup"><span data-stu-id="185a0-116">In addition to CPU and memory usage counters, you can use the following performance counters to help determine when a server is overloaded with requests:</span></span>
  
- <span data-ttu-id="185a0-117">**LS:WEB - регулирование и Authentication\WEB — общее количество запросов в обработке**, который указывает число ожидающих веб-запросов на сервере.</span><span class="sxs-lookup"><span data-stu-id="185a0-117">**LS:WEB - Throttling and Authentication\WEB - Total Requests in Processing**, which indicates the number of pending web requests on the server.</span></span> <span data-ttu-id="185a0-118">Если этот счетчик достигает 10 000, последующие запросы завершаются с ошибкой "503 — служба недоступна".</span><span class="sxs-lookup"><span data-stu-id="185a0-118">When this counter reaches 10,000, subsequent requests will fail, with the error message, "503 - Service Unavailable."</span></span>
    
- <span data-ttu-id="185a0-119">**ASP.NET\Requests Queued** (значение всегда должно быть равно нулю).</span><span class="sxs-lookup"><span data-stu-id="185a0-119">**ASP.NET\Requests Queued** (should always be zero).</span></span>
    
> [!NOTE]
> <span data-ttu-id="185a0-120">При достижении или превышении этих значений следует вернуться к планированию мощности и повторно выполнить расчет, чтобы определить правильные значения тактовой частоты ЦП, числа ядер и объема памяти для компьютеров, на которых размещаются веб-службы.</span><span class="sxs-lookup"><span data-stu-id="185a0-120">If you meet or exceed these values, you should revisit and re-compute your capacity planning for the correct sizing of CPU, number of cores and memory for the computers hosting the web services.</span></span> 
  
 <span data-ttu-id="185a0-121">**Для службы Mobility Service (Mcx):**</span><span class="sxs-lookup"><span data-stu-id="185a0-121">**For the Mobility Service (Mcx):**</span></span>
  
- <span data-ttu-id="185a0-122">**CSIntMcxAppPool** и **CSExtMcxAppPool** рабочие процессы в диспетчере Internet Information Services (IIS).</span><span class="sxs-lookup"><span data-stu-id="185a0-122">The **CSIntMcxAppPool** and **CSExtMcxAppPool** worker processes in Internet Information Services (IIS) Manager.</span></span> <span data-ttu-id="185a0-123">На панели **Рабочие процессы** изучите столбцы **ЦП %** и **Частные байты (КБ)** (память).</span><span class="sxs-lookup"><span data-stu-id="185a0-123">In the **Worker Processes** pane, look at the **CPU %** and **Private Bytes (KB)** (memory) columns.</span></span>
    
- <span data-ttu-id="185a0-124">Счетчики производительности **ЦП** и **Процессор**.</span><span class="sxs-lookup"><span data-stu-id="185a0-124">The **CPU** and **Processor** performance counters.</span></span>
    
<span data-ttu-id="185a0-125">В большинстве развертываний ресурсы ЦП, задействованные службой Mobility Service, не должны в среднем превышать 15 %.</span><span class="sxs-lookup"><span data-stu-id="185a0-125">For most deployments, Mobility Service CPU usage should be below 15 percent, on average.</span></span> <span data-ttu-id="185a0-126">Использование памяти следует попадают в рамках, описанных в [мониторе ограничений емкости памяти сервера в Скайп для Business Server](server-memory-capacity-limits.md).</span><span class="sxs-lookup"><span data-stu-id="185a0-126">Memory usage should fall within the limits described in [Monitor for server memory capacity limits in Skype for Business Server](server-memory-capacity-limits.md).</span></span>
  
<span data-ttu-id="185a0-127">Помимо счетчиков производительности ЦП и памяти можно использовать следующие счетчики производительности ASP.NET, которые позволят определить степень перегрузки сервера запросами.</span><span class="sxs-lookup"><span data-stu-id="185a0-127">In addition to CPU and memory usage counters, you can use the following ASP.NET performance counters to help determine when a server is overloaded with requests:</span></span>
  
- <span data-ttu-id="185a0-128">**ASP.NET v2.0.50727\Requests Current** показывает количество веб-запросов сервера в очереди.</span><span class="sxs-lookup"><span data-stu-id="185a0-128">**ASP.NET v2.0.50727\Requests Current**, which indicates the number of pending web requests on the server.</span></span> <span data-ttu-id="185a0-129">Если этот счетчик достигает 5 000, последующие запросы завершаются с ошибкой "503 — служба недоступна".</span><span class="sxs-lookup"><span data-stu-id="185a0-129">When this counter reaches 5,000, subsequent requests will fail with the error message, "503 - Service Unavailable."</span></span>
    
- <span data-ttu-id="185a0-130">**ASP.NET\Requests Queued** (значение всегда должно быть равно нулю).</span><span class="sxs-lookup"><span data-stu-id="185a0-130">**ASP.NET\Requests Queued** (should always be zero).</span></span>
    
> [!NOTE]
> <span data-ttu-id="185a0-131">При достижении или превышении этих значений следует вернуться к планированию мощности и повторно выполнить расчет, чтобы определить правильные значения тактовой частоты ЦП, числа ядер и объема памяти для компьютеров, на которых размещаются веб-службы.</span><span class="sxs-lookup"><span data-stu-id="185a0-131">If you meet or exceed these values, you should revisit and recompute your capacity planning for the correct sizing of CPU, number of cores, and memory for the computers hosting the web services.</span></span> 

> [!NOTE]
> <span data-ttu-id="185a0-132">Поддержка устаревших мобильных клиентов MCX (Mobility Service) больше не доступен в Скайп для Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="185a0-132">MCX (Mobility Service) support for legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="185a0-133">Все текущей Скайп для мобильных клиентов Business уже используете Unified Communications Web API (UCWA) для поддержки мгновенного обмена Мгновенными сообщениями, сведения о присутствии и контакты.</span><span class="sxs-lookup"><span data-stu-id="185a0-133">All current Skype for Business mobile clients already use Unified Communications Web API (UCWA) to support instant messaging (IM), presence, and contacts.</span></span> <span data-ttu-id="185a0-134">Пользователи с прежних версий клиентов, использующих MCX потребуется обновить до текущего клиента.</span><span class="sxs-lookup"><span data-stu-id="185a0-134">Users with legacy clients using MCX will need to upgrade to a current client.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="185a0-135">См. также</span><span class="sxs-lookup"><span data-stu-id="185a0-135">See also</span></span>

[<span data-ttu-id="185a0-136">Монитор ограничений емкости памяти сервера в Скайп для Business Server</span><span class="sxs-lookup"><span data-stu-id="185a0-136">Monitor for server memory capacity limits in Skype for Business Server</span></span>](server-memory-capacity-limits.md)
