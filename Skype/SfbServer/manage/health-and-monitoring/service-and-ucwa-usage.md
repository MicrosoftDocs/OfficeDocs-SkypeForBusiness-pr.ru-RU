---
title: Мониторинг использования mobility Service и UCWA в Skype для бизнеса Server
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
ms.assetid: 8389b37a-ca3e-4047-8b51-85bc07da87e8
description: Сводка. Управление службой Mobility Service (Mcx) и веб-API объединенных коммуникаций (UCWA) в Skype для бизнеса Server.
ms.openlocfilehash: 76bcf8727d3abbb417595f033ce9a59ec00a39ff
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814249"
---
# <a name="monitor-mobility-service-and-ucwa-usage-in-skype-for-business-server"></a><span data-ttu-id="9e7db-103">Мониторинг использования mobility Service и UCWA в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="9e7db-103">Monitor Mobility Service and UCWA usage in Skype for Business Server</span></span>
 
<span data-ttu-id="9e7db-104">**Сводка:** Управление службой Mobility Service (Mcx) и веб-API объединенных коммуникаций (UCWA) в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="9e7db-104">**Summary:** Manage the Mobility Service (Mcx) and the Unified Communications Web API (UCWA) in Skype for Business Server.</span></span>

> [!NOTE]
> <span data-ttu-id="9e7db-105">Поддержка MCX (Mobility Service) для устаревших мобильных клиентов больше недоступна в Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="9e7db-105">MCX (Mobility Service) support for legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="9e7db-106">Все текущие мобильные клиенты Skype для бизнеса уже используют веб-API объединенных коммуникаций (UCWA) для поддержки обмена мгновенными сообщениями, присутствия и контактов.</span><span class="sxs-lookup"><span data-stu-id="9e7db-106">All current Skype for Business mobile clients already use Unified Communications Web API (UCWA) to support instant messaging (IM), presence, and contacts.</span></span> <span data-ttu-id="9e7db-107">Пользователям с устаревшими клиентами, использующими MCX, потребуется обновиться до текущего клиента.</span><span class="sxs-lookup"><span data-stu-id="9e7db-107">Users with legacy clients using MCX will need to upgrade to a current client.</span></span>
  
<span data-ttu-id="9e7db-108">Необходимо постоянно отслеживать ЦП и память, используемые Skype для бизнеса Server Mobility Service (Mcx) и веб-API объединенных коммуникаций (UCWA).</span><span class="sxs-lookup"><span data-stu-id="9e7db-108">On an ongoing basis, you should monitor the CPU and memory that is used by the Skype for Business Server Mobility Service (Mcx) and the Unified Communications Web API (UCWA).</span></span> <span data-ttu-id="9e7db-109">Для отслеживания использования можно использовать следующее:</span><span class="sxs-lookup"><span data-stu-id="9e7db-109">To monitor usage, you can use the following:</span></span>
  
 <span data-ttu-id="9e7db-110">**Для веб-API объединенных коммуникаций (UCWA):**</span><span class="sxs-lookup"><span data-stu-id="9e7db-110">**For Unified Communications Web API (UCWA):**</span></span>
  
- <span data-ttu-id="9e7db-111">Рабочий **процесс LyncUcwa** в диспетчере служб IIS.</span><span class="sxs-lookup"><span data-stu-id="9e7db-111">The **LyncUcwa** worker process in Internet Information Services (IIS) Manager.</span></span> <span data-ttu-id="9e7db-112">На панели **Рабочие процессы** изучите столбцы **ЦП %** и **Частные байты (КБ)** (память).</span><span class="sxs-lookup"><span data-stu-id="9e7db-112">In the **Worker Processes** pane, look at the **CPU %** and **Private Bytes (KB)** (memory) columns.</span></span>
    
- <span data-ttu-id="9e7db-113">Счетчики производительности **ЦП** и **Процессор**.</span><span class="sxs-lookup"><span data-stu-id="9e7db-113">The **CPU** and **Processor** performance counters.</span></span>
    
<span data-ttu-id="9e7db-114">В большинстве развертывании использование ЦП UCWA в среднем должно быть меньше 15 процентов.</span><span class="sxs-lookup"><span data-stu-id="9e7db-114">For most deployments, UCWA CPU usage should be below 15 percent on average.</span></span> <span data-ttu-id="9e7db-115">Использование памяти должно подпадать под ограничения, описанные в описании монитора для ограничения емкости памяти сервера [в Skype для бизнеса Server.](server-memory-capacity-limits.md)</span><span class="sxs-lookup"><span data-stu-id="9e7db-115">Memory usage should fall within the limits described in [Monitor for server memory capacity limits in Skype for Business Server](server-memory-capacity-limits.md).</span></span>
  
<span data-ttu-id="9e7db-116">Помимо счетчиков использования ЦП и памяти, можно использовать следующие счетчики производительности, чтобы определить, когда сервер перегружен запросами:</span><span class="sxs-lookup"><span data-stu-id="9e7db-116">In addition to CPU and memory usage counters, you can use the following performance counters to help determine when a server is overloaded with requests:</span></span>
  
- <span data-ttu-id="9e7db-117">**LS:WEB — регулирование** и проверка подлинности\WEB — общее число запросов в обработке, которое указывает количество ожидающих веб-запросов на сервере.</span><span class="sxs-lookup"><span data-stu-id="9e7db-117">**LS:WEB - Throttling and Authentication\WEB - Total Requests in Processing**, which indicates the number of pending web requests on the server.</span></span> <span data-ttu-id="9e7db-118">Если этот счетчик достигает 10 000, последующие запросы будут неуспешными с сообщением об ошибке "503 — служба недоступна".</span><span class="sxs-lookup"><span data-stu-id="9e7db-118">When this counter reaches 10,000, subsequent requests will fail, with the error message, "503 - Service Unavailable."</span></span>
    
- <span data-ttu-id="9e7db-119">**ASP.NET\Requests Queued** (значение всегда должно быть равно нулю)</span><span class="sxs-lookup"><span data-stu-id="9e7db-119">**ASP.NET\Requests Queued** (should always be zero).</span></span>
    
> [!NOTE]
> <span data-ttu-id="9e7db-120">Если эти значения соответствуют или превышаются, следует пересмотреть и заново вычислить планирование мощности для правильного изменения размеров ЦП, количества ядер и памяти для компьютеров, на которых размещены веб-службы.</span><span class="sxs-lookup"><span data-stu-id="9e7db-120">If you meet or exceed these values, you should revisit and re-compute your capacity planning for the correct sizing of CPU, number of cores and memory for the computers hosting the web services.</span></span> 
  
 <span data-ttu-id="9e7db-121">**Для службы Mobility Service (Mcx):**</span><span class="sxs-lookup"><span data-stu-id="9e7db-121">**For the Mobility Service (Mcx):**</span></span>
  
- <span data-ttu-id="9e7db-122">Рабочие **процессы CSIntMcxAppPool** и **CSExtMcxAppPool** в диспетчере служб IIS.</span><span class="sxs-lookup"><span data-stu-id="9e7db-122">The **CSIntMcxAppPool** and **CSExtMcxAppPool** worker processes in Internet Information Services (IIS) Manager.</span></span> <span data-ttu-id="9e7db-123">На панели **Рабочие процессы** изучите столбцы **ЦП %** и **Частные байты (КБ)** (память).</span><span class="sxs-lookup"><span data-stu-id="9e7db-123">In the **Worker Processes** pane, look at the **CPU %** and **Private Bytes (KB)** (memory) columns.</span></span>
    
- <span data-ttu-id="9e7db-124">Счетчики производительности **ЦП** и **Процессор**.</span><span class="sxs-lookup"><span data-stu-id="9e7db-124">The **CPU** and **Processor** performance counters.</span></span>
    
<span data-ttu-id="9e7db-125">В большинстве развертывании использование ЦП Службы Mobility Service в среднем должно быть меньше 15 процентов.</span><span class="sxs-lookup"><span data-stu-id="9e7db-125">For most deployments, Mobility Service CPU usage should be below 15 percent, on average.</span></span> <span data-ttu-id="9e7db-126">Использование памяти должно подпадать под ограничения, описанные в описании монитора для ограничения емкости памяти сервера [в Skype для бизнеса Server.](server-memory-capacity-limits.md)</span><span class="sxs-lookup"><span data-stu-id="9e7db-126">Memory usage should fall within the limits described in [Monitor for server memory capacity limits in Skype for Business Server](server-memory-capacity-limits.md).</span></span>
  
<span data-ttu-id="9e7db-127">Помимо счетчиков производительности ЦП и памяти можно использовать следующие счетчики производительности ASP.NET, которые позволят определить степень перегрузки сервера запросами.</span><span class="sxs-lookup"><span data-stu-id="9e7db-127">In addition to CPU and memory usage counters, you can use the following ASP.NET performance counters to help determine when a server is overloaded with requests:</span></span>
  
- <span data-ttu-id="9e7db-128">**ASP.NET v2.0.50727\Requests Current** показывает количество веб-запросов сервера в очереди.</span><span class="sxs-lookup"><span data-stu-id="9e7db-128">**ASP.NET v2.0.50727\Requests Current**, which indicates the number of pending web requests on the server.</span></span> <span data-ttu-id="9e7db-129">Когда этот счетчик достигает 5000, последующие запросы не будут отправляться с сообщением об ошибке "503 — служба недоступна".</span><span class="sxs-lookup"><span data-stu-id="9e7db-129">When this counter reaches 5,000, subsequent requests will fail with the error message, "503 - Service Unavailable."</span></span>
    
- <span data-ttu-id="9e7db-130">**ASP.NET\Requests Queued** (значение всегда должно быть равно нулю)</span><span class="sxs-lookup"><span data-stu-id="9e7db-130">**ASP.NET\Requests Queued** (should always be zero).</span></span>
    
> [!NOTE]
> <span data-ttu-id="9e7db-131">Если эти значения соответствуют или превышаются, следует пересмотреть и откорректировать планирование мощности для правильного изменения размеров ЦП, количества ядер и памяти для компьютеров, на которых размещены веб-службы.</span><span class="sxs-lookup"><span data-stu-id="9e7db-131">If you meet or exceed these values, you should revisit and recompute your capacity planning for the correct sizing of CPU, number of cores, and memory for the computers hosting the web services.</span></span> 

> [!NOTE]
> <span data-ttu-id="9e7db-132">Поддержка MCX (Mobility Service) для устаревших мобильных клиентов больше недоступна в Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="9e7db-132">MCX (Mobility Service) support for legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="9e7db-133">Все текущие мобильные клиенты Skype для бизнеса уже используют веб-API объединенных коммуникаций (UCWA) для поддержки обмена мгновенными сообщениями, присутствия и контактов.</span><span class="sxs-lookup"><span data-stu-id="9e7db-133">All current Skype for Business mobile clients already use Unified Communications Web API (UCWA) to support instant messaging (IM), presence, and contacts.</span></span> <span data-ttu-id="9e7db-134">Пользователям с устаревшими клиентами, использующими MCX, потребуется обновиться до текущего клиента.</span><span class="sxs-lookup"><span data-stu-id="9e7db-134">Users with legacy clients using MCX will need to upgrade to a current client.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="9e7db-135">См. также</span><span class="sxs-lookup"><span data-stu-id="9e7db-135">See also</span></span>

[<span data-ttu-id="9e7db-136">Отслеживание ограничений емкости памяти сервера в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="9e7db-136">Monitor for server memory capacity limits in Skype for Business Server</span></span>](server-memory-capacity-limits.md)
