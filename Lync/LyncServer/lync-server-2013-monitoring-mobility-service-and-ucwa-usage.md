---
title: 'Lync Server 2013: Мониторинг службы Mobility Service и использования UCWA'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Monitoring Mobility Service and UCWA usage
ms:assetid: 8389b37a-ca3e-4047-8b51-85bc07da87e8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690025(v=OCS.15)
ms:contentKeyID: 48184683
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0c3975d91ab3dc53b7bfd240d6aa6b863360db6e
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42184742"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="monitoring-mobility-service-and-ucwa-usage-in-lync-server-2013"></a><span data-ttu-id="2809b-102">Мониторинг службы Mobility Service и использования UCWA в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2809b-102">Monitoring Mobility Service and UCWA usage in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2809b-103">_**Последнее изменение темы:** 2013-02-14_</span><span class="sxs-lookup"><span data-stu-id="2809b-103">_**Topic Last Modified:** 2013-02-14_</span></span>

<span data-ttu-id="2809b-104">На постоянной основе необходимо отслеживать ресурсы ЦП и памяти, используемые службой Mobility Server Mobility Service (MCX), и веб-API объединенных коммуникаций (UCWA).</span><span class="sxs-lookup"><span data-stu-id="2809b-104">On an ongoing basis, you should monitor the CPU and memory that is used by the Lync Server Mobility Service (Mcx) and the Unified Communications Web API (UCWA).</span></span> <span data-ttu-id="2809b-105">Для мониторинга использования можно использовать следующие компоненты:</span><span class="sxs-lookup"><span data-stu-id="2809b-105">To monitor usage, you can use the following:</span></span>

<span data-ttu-id="2809b-106">**Для веб-интерфейса API объединенных коммуникаций (UCWA):**</span><span class="sxs-lookup"><span data-stu-id="2809b-106">**For Unified Communications Web API (UCWA):**</span></span>

  - <span data-ttu-id="2809b-107">Рабочий процесс **линкуква** в ДИСПЕТЧЕРЕ служб IIS.</span><span class="sxs-lookup"><span data-stu-id="2809b-107">The **LyncUcwa** worker process in Internet Information Services (IIS) Manager.</span></span> <span data-ttu-id="2809b-108">На панели **Рабочие процессы** изучите столбцы **ЦП %** и **Частные байты (КБ)** (память).</span><span class="sxs-lookup"><span data-stu-id="2809b-108">In the **Worker Processes** pane, look at the **CPU %** and **Private Bytes (KB)** (memory) columns.</span></span>

  - <span data-ttu-id="2809b-109">Счетчики производительности **ЦП** и **Процессор**.</span><span class="sxs-lookup"><span data-stu-id="2809b-109">The **CPU** and **Processor** performance counters.</span></span>

<span data-ttu-id="2809b-110">Для большинства развертываний использование ЦП UCWA должно быть менее 15% в среднем.</span><span class="sxs-lookup"><span data-stu-id="2809b-110">For most deployments, UCWA CPU usage should be below 15 percent on average.</span></span> <span data-ttu-id="2809b-111">Использование памяти должно попадать в пределы, описанные в разделе [наблюдение за пределами объема памяти сервера в Lync server 2013](lync-server-2013-monitoring-for-server-memory-capacity-limits.md).</span><span class="sxs-lookup"><span data-stu-id="2809b-111">Memory usage should fall within the limits described in [Monitoring for server memory capacity limits in Lync Server 2013](lync-server-2013-monitoring-for-server-memory-capacity-limits.md).</span></span>

<span data-ttu-id="2809b-112">В дополнение к счетчикам использования ЦП и памяти можно использовать следующие счетчики производительности, чтобы определить, когда сервер перегружается с запросами.</span><span class="sxs-lookup"><span data-stu-id="2809b-112">In addition to CPU and memory usage counters, you can use the following performance counters to help determine when a server is overloaded with requests:</span></span>

  - <span data-ttu-id="2809b-113">**Ls: веб — регулирование и веб-\\сайт проверки подлинности — общее количество обрабатываемых запросов**, которое указывает количество ожидающих веб-запросов на сервере.</span><span class="sxs-lookup"><span data-stu-id="2809b-113">**LS:WEB – Throttling and Authentication\\WEB – Total Requests in Processing**, which indicates the number of pending web requests on the server.</span></span> <span data-ttu-id="2809b-114">Когда этот счетчик достигает 10 000, последующие запросы завершатся неудачей с сообщением об ошибке "503 — Служба недоступна".</span><span class="sxs-lookup"><span data-stu-id="2809b-114">When this counter reaches 10,000, subsequent requests will fail, with the error message, "503 - Service Unavailable."</span></span>

  - <span data-ttu-id="2809b-115">**Число\\запросов ASP.NET в очереди** (всегда должно быть равно нулю).</span><span class="sxs-lookup"><span data-stu-id="2809b-115">**ASP.NET\\Requests Queued** (should always be zero).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="2809b-116">Если вы удовлетворяете или превышаете эти значения, необходимо повторно посетить и повторно вычислить планирование мощности для правильного определения размера ЦП, количества ядер и памяти для компьютеров, на которых размещаются веб-службы.</span><span class="sxs-lookup"><span data-stu-id="2809b-116">If you meet or exceed these values, you should revisit and re-compute your capacity planning for the correct sizing of CPU, number of cores and memory for the computers hosting the Web services.</span></span>



</div>

<span data-ttu-id="2809b-117">**Для службы Mobility Service (MCX):**</span><span class="sxs-lookup"><span data-stu-id="2809b-117">**For the Mobility Service (Mcx):**</span></span>

  - <span data-ttu-id="2809b-118">Рабочие процессы **ксинтмкксапппул** и **Ксекстмкксапппул** в диспетчере служб IIS.</span><span class="sxs-lookup"><span data-stu-id="2809b-118">The **CSIntMcxAppPool** and **CSExtMcxAppPool** worker processes in Internet Information Services (IIS) Manager.</span></span> <span data-ttu-id="2809b-119">На панели **Рабочие процессы** изучите столбцы **ЦП %** и **Частные байты (КБ)** (память).</span><span class="sxs-lookup"><span data-stu-id="2809b-119">In the **Worker Processes** pane, look at the **CPU %** and **Private Bytes (KB)** (memory) columns.</span></span>

  - <span data-ttu-id="2809b-120">Счетчики производительности **ЦП** и **Процессор**.</span><span class="sxs-lookup"><span data-stu-id="2809b-120">The **CPU** and **Processor** performance counters.</span></span>

<span data-ttu-id="2809b-121">Для большинства развертываний загрузка ЦП службы Mobility Service должна быть менее 15% в среднем.</span><span class="sxs-lookup"><span data-stu-id="2809b-121">For most deployments, Mobility Service CPU usage should be below 15 percent, on average.</span></span> <span data-ttu-id="2809b-122">Использование памяти должно попадать в пределы, описанные в разделе [наблюдение за пределами объема памяти сервера в Lync server 2013](lync-server-2013-monitoring-for-server-memory-capacity-limits.md).</span><span class="sxs-lookup"><span data-stu-id="2809b-122">Memory usage should fall within the limits described in [Monitoring for server memory capacity limits in Lync Server 2013](lync-server-2013-monitoring-for-server-memory-capacity-limits.md).</span></span>

<span data-ttu-id="2809b-123">Помимо счетчиков производительности ЦП и памяти можно использовать следующие счетчики производительности ASP.NET, которые позволят определить степень перегрузки сервера запросами.</span><span class="sxs-lookup"><span data-stu-id="2809b-123">In addition to CPU and memory usage counters, you can use the following ASP.NET performance counters to help determine when a server is overloaded with requests:</span></span>

  - <span data-ttu-id="2809b-124">**Текущее количество запросов\\ASP.NET v 2.0.50727**, которое указывает количество ожидающих веб-запросов на сервере.</span><span class="sxs-lookup"><span data-stu-id="2809b-124">**ASP.NET v2.0.50727\\Requests Current**, which indicates the number of pending web requests on the server.</span></span> <span data-ttu-id="2809b-125">Когда значение этого счетчика достигнет значения 5 000, последующие запросы завершатся неудачей с сообщением об ошибке "503 — Служба недоступна".</span><span class="sxs-lookup"><span data-stu-id="2809b-125">When this counter reaches 5,000, subsequent requests will fail with the error message, "503 - Service Unavailable."</span></span>

  - <span data-ttu-id="2809b-126">**Число\\запросов ASP.NET в очереди** (всегда должно быть равно нулю).</span><span class="sxs-lookup"><span data-stu-id="2809b-126">**ASP.NET\\Requests Queued** (should always be zero).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="2809b-127">Если вы отвечаете или превышают эти значения, необходимо повторно посетить и повторно вычислить планирование мощности для правильного определения размера ЦП, количества ядер и памяти для компьютеров, на которых размещаются веб-службы.</span><span class="sxs-lookup"><span data-stu-id="2809b-127">If you meet or exceed these values, you should revisit and recompute your capacity planning for the correct sizing of CPU, number of cores, and memory for the computers hosting the Web services.</span></span>



</div>

<div>

## <a name="see-also"></a><span data-ttu-id="2809b-128">См. также</span><span class="sxs-lookup"><span data-stu-id="2809b-128">See Also</span></span>


[<span data-ttu-id="2809b-129">Мониторинг пределов объема памяти сервера в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2809b-129">Monitoring for server memory capacity limits in Lync Server 2013</span></span>](lync-server-2013-monitoring-for-server-memory-capacity-limits.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

