---
title: Мониторинг службы Mobility Service и использование УКВА в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 8389b37a-ca3e-4047-8b51-85bc07da87e8
description: 'Сводка: Управление службой Mobility Service (МККС) и веб-API единой системы обмена сообщениями (УКВА) в Skype для бизнеса Server.'
ms.openlocfilehash: 7c41e92b144e1bd4d198c5e9d9f90913ce41400e
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817688"
---
# <a name="monitor-mobility-service-and-ucwa-usage-in-skype-for-business-server"></a><span data-ttu-id="a13bb-103">Мониторинг службы Mobility Service и использование УКВА в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="a13bb-103">Monitor Mobility Service and UCWA usage in Skype for Business Server</span></span>
 
<span data-ttu-id="a13bb-104">**Сводка:** Управление службой Mobility Service (МККС) и веб-API единой системы обмена сообщениями (УКВА) в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="a13bb-104">**Summary:** Manage the Mobility Service (Mcx) and the Unified Communications Web API (UCWA) in Skype for Business Server.</span></span>

> [!NOTE]
> <span data-ttu-id="a13bb-105">Поддержка МККС (служба Mobility Service) для устаревших мобильных клиентов больше не доступна в Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="a13bb-105">MCX (Mobility Service) support for legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="a13bb-106">На всех текущих мобильных клиентах Skype для бизнеса уже используется веб-API единой системы обмена сообщениями (УКВА) для поддержки мгновенных сообщений, присутствия и контактов.</span><span class="sxs-lookup"><span data-stu-id="a13bb-106">All current Skype for Business mobile clients already use Unified Communications Web API (UCWA) to support instant messaging (IM), presence, and contacts.</span></span> <span data-ttu-id="a13bb-107">Пользователи с устаревшими клиентами, использующими МККС, должны обновиться до текущего клиента.</span><span class="sxs-lookup"><span data-stu-id="a13bb-107">Users with legacy clients using MCX will need to upgrade to a current client.</span></span>
  
<span data-ttu-id="a13bb-108">В настоящее время вы должны наблюдать за ЦП и памятью, используемой службой Mobility Service в Skype для бизнеса Server (МККС) и веб-API единой системы обмена сообщениями (УКВА).</span><span class="sxs-lookup"><span data-stu-id="a13bb-108">On an ongoing basis, you should monitor the CPU and memory that is used by the Skype for Business Server Mobility Service (Mcx) and the Unified Communications Web API (UCWA).</span></span> <span data-ttu-id="a13bb-109">Чтобы отслеживать использование, прибегите к одному из следующих способов:</span><span class="sxs-lookup"><span data-stu-id="a13bb-109">To monitor usage, you can use the following:</span></span>
  
 <span data-ttu-id="a13bb-110">**Для веб-интерфейса API объединенных коммуникаций (UCWA):**</span><span class="sxs-lookup"><span data-stu-id="a13bb-110">**For Unified Communications Web API (UCWA):**</span></span>
  
- <span data-ttu-id="a13bb-111">Рабочий процесс **линкуква** в диспетчере информационных служб Интернета (IIS).</span><span class="sxs-lookup"><span data-stu-id="a13bb-111">The **LyncUcwa** worker process in Internet Information Services (IIS) Manager.</span></span> <span data-ttu-id="a13bb-112">На панели **Рабочие процессы** изучите столбцы **ЦП %** и **Частные байты (КБ)** (память).</span><span class="sxs-lookup"><span data-stu-id="a13bb-112">In the **Worker Processes** pane, look at the **CPU %** and **Private Bytes (KB)** (memory) columns.</span></span>
    
- <span data-ttu-id="a13bb-113">Счетчики производительности **ЦП** и **Процессор**.</span><span class="sxs-lookup"><span data-stu-id="a13bb-113">The **CPU** and **Processor** performance counters.</span></span>
    
<span data-ttu-id="a13bb-114">В большинстве развертываний ресурсы ЦП, задействованные UCWA, не должны в среднем превышать 15 %.</span><span class="sxs-lookup"><span data-stu-id="a13bb-114">For most deployments, UCWA CPU usage should be below 15 percent on average.</span></span> <span data-ttu-id="a13bb-115">Использование памяти должно попадать в пределы, описанные в разделе [наблюдение за ограничениями объема памяти сервера в Skype для бизнеса Server](server-memory-capacity-limits.md).</span><span class="sxs-lookup"><span data-stu-id="a13bb-115">Memory usage should fall within the limits described in [Monitor for server memory capacity limits in Skype for Business Server](server-memory-capacity-limits.md).</span></span>
  
<span data-ttu-id="a13bb-116">Помимо счетчиков использования ЦП и памяти можно использовать следующие счетчики производительности, которые позволят определить степень перегрузки сервера запросами:</span><span class="sxs-lookup"><span data-stu-id="a13bb-116">In addition to CPU and memory usage counters, you can use the following performance counters to help determine when a server is overloaded with requests:</span></span>
  
- <span data-ttu-id="a13bb-117">**Ls: веб-регулирование и аусентикатион\веб — общее количество запросов в обработке**, которое указывает число ожидающих веб-запросов на сервере.</span><span class="sxs-lookup"><span data-stu-id="a13bb-117">**LS:WEB - Throttling and Authentication\WEB - Total Requests in Processing**, which indicates the number of pending web requests on the server.</span></span> <span data-ttu-id="a13bb-118">Если этот счетчик достигает 10 000, последующие запросы завершаются с ошибкой "503 — служба недоступна".</span><span class="sxs-lookup"><span data-stu-id="a13bb-118">When this counter reaches 10,000, subsequent requests will fail, with the error message, "503 - Service Unavailable."</span></span>
    
- <span data-ttu-id="a13bb-119">**ASP.NET\Requests Queued** (значение всегда должно быть равно нулю).</span><span class="sxs-lookup"><span data-stu-id="a13bb-119">**ASP.NET\Requests Queued** (should always be zero).</span></span>
    
> [!NOTE]
> <span data-ttu-id="a13bb-120">При достижении или превышении этих значений следует вернуться к планированию мощности и повторно выполнить расчет, чтобы определить правильные значения тактовой частоты ЦП, числа ядер и объема памяти для компьютеров, на которых размещаются веб-службы.</span><span class="sxs-lookup"><span data-stu-id="a13bb-120">If you meet or exceed these values, you should revisit and re-compute your capacity planning for the correct sizing of CPU, number of cores and memory for the computers hosting the web services.</span></span> 
  
 <span data-ttu-id="a13bb-121">**Для службы Mobility Service (Mcx):**</span><span class="sxs-lookup"><span data-stu-id="a13bb-121">**For the Mobility Service (Mcx):**</span></span>
  
- <span data-ttu-id="a13bb-122">Рабочие процессы **ксинтмкксапппул** и **ксекстмкксапппул** в диспетчере информационных служб Интернета (IIS).</span><span class="sxs-lookup"><span data-stu-id="a13bb-122">The **CSIntMcxAppPool** and **CSExtMcxAppPool** worker processes in Internet Information Services (IIS) Manager.</span></span> <span data-ttu-id="a13bb-123">На панели **Рабочие процессы** изучите столбцы **ЦП %** и **Частные байты (КБ)** (память).</span><span class="sxs-lookup"><span data-stu-id="a13bb-123">In the **Worker Processes** pane, look at the **CPU %** and **Private Bytes (KB)** (memory) columns.</span></span>
    
- <span data-ttu-id="a13bb-124">Счетчики производительности **ЦП** и **Процессор**.</span><span class="sxs-lookup"><span data-stu-id="a13bb-124">The **CPU** and **Processor** performance counters.</span></span>
    
<span data-ttu-id="a13bb-125">В большинстве развертываний ресурсы ЦП, задействованные службой Mobility Service, не должны в среднем превышать 15 %.</span><span class="sxs-lookup"><span data-stu-id="a13bb-125">For most deployments, Mobility Service CPU usage should be below 15 percent, on average.</span></span> <span data-ttu-id="a13bb-126">Использование памяти должно попадать в пределы, описанные в разделе [наблюдение за ограничениями объема памяти сервера в Skype для бизнеса Server](server-memory-capacity-limits.md).</span><span class="sxs-lookup"><span data-stu-id="a13bb-126">Memory usage should fall within the limits described in [Monitor for server memory capacity limits in Skype for Business Server](server-memory-capacity-limits.md).</span></span>
  
<span data-ttu-id="a13bb-127">Помимо счетчиков производительности ЦП и памяти можно использовать следующие счетчики производительности ASP.NET, которые позволят определить степень перегрузки сервера запросами.</span><span class="sxs-lookup"><span data-stu-id="a13bb-127">In addition to CPU and memory usage counters, you can use the following ASP.NET performance counters to help determine when a server is overloaded with requests:</span></span>
  
- <span data-ttu-id="a13bb-128">**ASP.NET v2.0.50727\Requests Current** показывает количество веб-запросов сервера в очереди.</span><span class="sxs-lookup"><span data-stu-id="a13bb-128">**ASP.NET v2.0.50727\Requests Current**, which indicates the number of pending web requests on the server.</span></span> <span data-ttu-id="a13bb-129">Если этот счетчик достигает 5 000, последующие запросы завершаются с ошибкой "503 — служба недоступна".</span><span class="sxs-lookup"><span data-stu-id="a13bb-129">When this counter reaches 5,000, subsequent requests will fail with the error message, "503 - Service Unavailable."</span></span>
    
- <span data-ttu-id="a13bb-130">**ASP.NET\Requests Queued** (значение всегда должно быть равно нулю).</span><span class="sxs-lookup"><span data-stu-id="a13bb-130">**ASP.NET\Requests Queued** (should always be zero).</span></span>
    
> [!NOTE]
> <span data-ttu-id="a13bb-131">При достижении или превышении этих значений следует вернуться к планированию мощности и повторно выполнить расчет, чтобы определить правильные значения тактовой частоты ЦП, числа ядер и объема памяти для компьютеров, на которых размещаются веб-службы.</span><span class="sxs-lookup"><span data-stu-id="a13bb-131">If you meet or exceed these values, you should revisit and recompute your capacity planning for the correct sizing of CPU, number of cores, and memory for the computers hosting the web services.</span></span> 

> [!NOTE]
> <span data-ttu-id="a13bb-132">Поддержка МККС (служба Mobility Service) для устаревших мобильных клиентов больше не доступна в Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="a13bb-132">MCX (Mobility Service) support for legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="a13bb-133">На всех текущих мобильных клиентах Skype для бизнеса уже используется веб-API единой системы обмена сообщениями (УКВА) для поддержки мгновенных сообщений, присутствия и контактов.</span><span class="sxs-lookup"><span data-stu-id="a13bb-133">All current Skype for Business mobile clients already use Unified Communications Web API (UCWA) to support instant messaging (IM), presence, and contacts.</span></span> <span data-ttu-id="a13bb-134">Пользователи с устаревшими клиентами, использующими МККС, должны обновиться до текущего клиента.</span><span class="sxs-lookup"><span data-stu-id="a13bb-134">Users with legacy clients using MCX will need to upgrade to a current client.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="a13bb-135">См. также</span><span class="sxs-lookup"><span data-stu-id="a13bb-135">See also</span></span>

[<span data-ttu-id="a13bb-136">Наблюдение за ограничениями объема памяти сервера в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="a13bb-136">Monitor for server memory capacity limits in Skype for Business Server</span></span>](server-memory-capacity-limits.md)
