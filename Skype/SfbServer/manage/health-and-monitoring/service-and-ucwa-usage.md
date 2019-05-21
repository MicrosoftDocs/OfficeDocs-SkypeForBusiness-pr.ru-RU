---
title: Мониторинг службы Mobility Service и использование УКВА в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8389b37a-ca3e-4047-8b51-85bc07da87e8
description: 'Сводка: Управление службой Mobility Service (МККС) и веб-API единой системы обмена сообщениями (УКВА) в Skype для бизнеса Server.'
ms.openlocfilehash: 5447eb0ac8ffe468fd52c7011824cc1f2f2f7b55
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34279797"
---
# <a name="monitor-mobility-service-and-ucwa-usage-in-skype-for-business-server"></a><span data-ttu-id="b9421-103">Мониторинг службы Mobility Service и использование УКВА в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="b9421-103">Monitor Mobility Service and UCWA usage in Skype for Business Server</span></span>
 
<span data-ttu-id="b9421-104">**Сводка:** Управление службой Mobility Service (МККС) и веб-API единой системы обмена сообщениями (УКВА) в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="b9421-104">**Summary:** Manage the Mobility Service (Mcx) and the Unified Communications Web API (UCWA) in Skype for Business Server.</span></span>

> [!NOTE]
> <span data-ttu-id="b9421-105">Поддержка МККС (служба Mobility Service) для устаревших мобильных клиентов больше не доступна в Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="b9421-105">MCX (Mobility Service) support for legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="b9421-106">На всех текущих мобильных клиентах Skype для бизнеса уже используется веб-API единой системы обмена сообщениями (УКВА) для поддержки мгновенных сообщений, присутствия и контактов.</span><span class="sxs-lookup"><span data-stu-id="b9421-106">All current Skype for Business mobile clients already use Unified Communications Web API (UCWA) to support instant messaging (IM), presence, and contacts.</span></span> <span data-ttu-id="b9421-107">Пользователи с устаревшими клиентами, использующими МККС, должны обновиться до текущего клиента.</span><span class="sxs-lookup"><span data-stu-id="b9421-107">Users with legacy clients using MCX will need to upgrade to a current client.</span></span>
  
<span data-ttu-id="b9421-108">В настоящее время вы должны наблюдать за ЦП и памятью, используемой службой Mobility Service в Skype для бизнеса Server (МККС) и веб-API единой системы обмена сообщениями (УКВА).</span><span class="sxs-lookup"><span data-stu-id="b9421-108">On an ongoing basis, you should monitor the CPU and memory that is used by the Skype for Business Server Mobility Service (Mcx) and the Unified Communications Web API (UCWA).</span></span> <span data-ttu-id="b9421-109">Чтобы отслеживать использование, прибегите к одному из следующих способов:</span><span class="sxs-lookup"><span data-stu-id="b9421-109">To monitor usage, you can use the following:</span></span>
  
 <span data-ttu-id="b9421-110">**Для веб-интерфейса API объединенных коммуникаций (UCWA):**</span><span class="sxs-lookup"><span data-stu-id="b9421-110">**For Unified Communications Web API (UCWA):**</span></span>
  
- <span data-ttu-id="b9421-111">Рабочий процесс **линкуква** в диспетчере информационных служб Интернета (IIS).</span><span class="sxs-lookup"><span data-stu-id="b9421-111">The **LyncUcwa** worker process in Internet Information Services (IIS) Manager.</span></span> <span data-ttu-id="b9421-112">На панели **Рабочие процессы** изучите столбцы **ЦП %** и **Частные байты (КБ)** (память).</span><span class="sxs-lookup"><span data-stu-id="b9421-112">In the **Worker Processes** pane, look at the **CPU %** and **Private Bytes (KB)** (memory) columns.</span></span>
    
- <span data-ttu-id="b9421-113">Счетчики производительности **ЦП** и **Процессор**.</span><span class="sxs-lookup"><span data-stu-id="b9421-113">The **CPU** and **Processor** performance counters.</span></span>
    
<span data-ttu-id="b9421-114">В большинстве развертываний ресурсы ЦП, задействованные UCWA, не должны в среднем превышать 15 %.</span><span class="sxs-lookup"><span data-stu-id="b9421-114">For most deployments, UCWA CPU usage should be below 15 percent on average.</span></span> <span data-ttu-id="b9421-115">Использование памяти должно попадать в пределы, описанные в разделе Наблюдение за ограничениями объема [памяти сервера в Skype для бизнеса Server](server-memory-capacity-limits.md).</span><span class="sxs-lookup"><span data-stu-id="b9421-115">Memory usage should fall within the limits described in [Monitor for server memory capacity limits in Skype for Business Server](server-memory-capacity-limits.md).</span></span>
  
<span data-ttu-id="b9421-116">Помимо счетчиков использования ЦП и памяти можно использовать следующие счетчики производительности, которые позволят определить степень перегрузки сервера запросами:</span><span class="sxs-lookup"><span data-stu-id="b9421-116">In addition to CPU and memory usage counters, you can use the following performance counters to help determine when a server is overloaded with requests:</span></span>
  
- <span data-ttu-id="b9421-117">**Ls: веб-регулирование и аусентикатион\веб — общее количество запросов в обработке**, которое указывает число ожидающих веб-запросов на сервере.</span><span class="sxs-lookup"><span data-stu-id="b9421-117">**LS:WEB - Throttling and Authentication\WEB - Total Requests in Processing**, which indicates the number of pending web requests on the server.</span></span> <span data-ttu-id="b9421-118">Если этот счетчик достигает 10 000, последующие запросы завершаются с ошибкой "503 — служба недоступна".</span><span class="sxs-lookup"><span data-stu-id="b9421-118">When this counter reaches 10,000, subsequent requests will fail, with the error message, "503 - Service Unavailable."</span></span>
    
- <span data-ttu-id="b9421-119">**ASP.NET\Requests Queued** (значение всегда должно быть равно нулю).</span><span class="sxs-lookup"><span data-stu-id="b9421-119">**ASP.NET\Requests Queued** (should always be zero).</span></span>
    
> [!NOTE]
> <span data-ttu-id="b9421-120">При достижении или превышении этих значений следует вернуться к планированию мощности и повторно выполнить расчет, чтобы определить правильные значения тактовой частоты ЦП, числа ядер и объема памяти для компьютеров, на которых размещаются веб-службы.</span><span class="sxs-lookup"><span data-stu-id="b9421-120">If you meet or exceed these values, you should revisit and re-compute your capacity planning for the correct sizing of CPU, number of cores and memory for the computers hosting the web services.</span></span> 
  
 <span data-ttu-id="b9421-121">**Для службы Mobility Service (Mcx):**</span><span class="sxs-lookup"><span data-stu-id="b9421-121">**For the Mobility Service (Mcx):**</span></span>
  
- <span data-ttu-id="b9421-122">Рабочие процессы **ксинтмкксапппул** и **ксекстмкксапппул** в диспетчере информационных служб Интернета (IIS).</span><span class="sxs-lookup"><span data-stu-id="b9421-122">The **CSIntMcxAppPool** and **CSExtMcxAppPool** worker processes in Internet Information Services (IIS) Manager.</span></span> <span data-ttu-id="b9421-123">На панели **Рабочие процессы** изучите столбцы **ЦП %** и **Частные байты (КБ)** (память).</span><span class="sxs-lookup"><span data-stu-id="b9421-123">In the **Worker Processes** pane, look at the **CPU %** and **Private Bytes (KB)** (memory) columns.</span></span>
    
- <span data-ttu-id="b9421-124">Счетчики производительности **ЦП** и **Процессор**.</span><span class="sxs-lookup"><span data-stu-id="b9421-124">The **CPU** and **Processor** performance counters.</span></span>
    
<span data-ttu-id="b9421-125">В большинстве развертываний ресурсы ЦП, задействованные службой Mobility Service, не должны в среднем превышать 15 %.</span><span class="sxs-lookup"><span data-stu-id="b9421-125">For most deployments, Mobility Service CPU usage should be below 15 percent, on average.</span></span> <span data-ttu-id="b9421-126">Использование памяти должно попадать в пределы, описанные в разделе Наблюдение за ограничениями объема [памяти сервера в Skype для бизнеса Server](server-memory-capacity-limits.md).</span><span class="sxs-lookup"><span data-stu-id="b9421-126">Memory usage should fall within the limits described in [Monitor for server memory capacity limits in Skype for Business Server](server-memory-capacity-limits.md).</span></span>
  
<span data-ttu-id="b9421-127">Помимо счетчиков производительности ЦП и памяти можно использовать следующие счетчики производительности ASP.NET, которые позволят определить степень перегрузки сервера запросами.</span><span class="sxs-lookup"><span data-stu-id="b9421-127">In addition to CPU and memory usage counters, you can use the following ASP.NET performance counters to help determine when a server is overloaded with requests:</span></span>
  
- <span data-ttu-id="b9421-128">**ASP.NET v2.0.50727\Requests Current** показывает количество веб-запросов сервера в очереди.</span><span class="sxs-lookup"><span data-stu-id="b9421-128">**ASP.NET v2.0.50727\Requests Current**, which indicates the number of pending web requests on the server.</span></span> <span data-ttu-id="b9421-129">Если этот счетчик достигает 5 000, последующие запросы завершаются с ошибкой "503 — служба недоступна".</span><span class="sxs-lookup"><span data-stu-id="b9421-129">When this counter reaches 5,000, subsequent requests will fail with the error message, "503 - Service Unavailable."</span></span>
    
- <span data-ttu-id="b9421-130">**ASP.NET\Requests Queued** (значение всегда должно быть равно нулю).</span><span class="sxs-lookup"><span data-stu-id="b9421-130">**ASP.NET\Requests Queued** (should always be zero).</span></span>
    
> [!NOTE]
> <span data-ttu-id="b9421-131">При достижении или превышении этих значений следует вернуться к планированию мощности и повторно выполнить расчет, чтобы определить правильные значения тактовой частоты ЦП, числа ядер и объема памяти для компьютеров, на которых размещаются веб-службы.</span><span class="sxs-lookup"><span data-stu-id="b9421-131">If you meet or exceed these values, you should revisit and recompute your capacity planning for the correct sizing of CPU, number of cores, and memory for the computers hosting the web services.</span></span> 

> [!NOTE]
> <span data-ttu-id="b9421-132">Поддержка МККС (служба Mobility Service) для устаревших мобильных клиентов больше не доступна в Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="b9421-132">MCX (Mobility Service) support for legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="b9421-133">На всех текущих мобильных клиентах Skype для бизнеса уже используется веб-API единой системы обмена сообщениями (УКВА) для поддержки мгновенных сообщений, присутствия и контактов.</span><span class="sxs-lookup"><span data-stu-id="b9421-133">All current Skype for Business mobile clients already use Unified Communications Web API (UCWA) to support instant messaging (IM), presence, and contacts.</span></span> <span data-ttu-id="b9421-134">Пользователи с устаревшими клиентами, использующими МККС, должны обновиться до текущего клиента.</span><span class="sxs-lookup"><span data-stu-id="b9421-134">Users with legacy clients using MCX will need to upgrade to a current client.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="b9421-135">См. также</span><span class="sxs-lookup"><span data-stu-id="b9421-135">See also</span></span>

[<span data-ttu-id="b9421-136">Наблюдение за ограничениями объема памяти сервера в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="b9421-136">Monitor for server memory capacity limits in Skype for Business Server</span></span>](server-memory-capacity-limits.md)
