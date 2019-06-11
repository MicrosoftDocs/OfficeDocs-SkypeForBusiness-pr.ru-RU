---
title: 'Lync Server 2013: наблюдение за службой Mobility Service и использование УКВА'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Monitoring Mobility Service and UCWA usage
ms:assetid: 8389b37a-ca3e-4047-8b51-85bc07da87e8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690025(v=OCS.15)
ms:contentKeyID: 48184683
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 758fef9e3f2c31bec88927c75b271808d5bbc43c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34826705"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="monitoring-mobility-service-and-ucwa-usage-in-lync-server-2013"></a><span data-ttu-id="05811-102">Наблюдение за работой службы Mobility Service и использованием УКВА в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="05811-102">Monitoring Mobility Service and UCWA usage in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="05811-103">_**Тема последнего изменения:** 2013-02-14_</span><span class="sxs-lookup"><span data-stu-id="05811-103">_**Topic Last Modified:** 2013-02-14_</span></span>

<span data-ttu-id="05811-104">В настоящее время вы должны наблюдать за ЦП и памятью, используемой службой Lync Server Mobility Service (МККС), и веб-API единой системы обмена сообщениями (УКВА).</span><span class="sxs-lookup"><span data-stu-id="05811-104">On an ongoing basis, you should monitor the CPU and memory that is used by the Lync Server Mobility Service (Mcx) and the Unified Communications Web API (UCWA).</span></span> <span data-ttu-id="05811-105">Чтобы отслеживать использование, прибегите к одному из следующих способов:</span><span class="sxs-lookup"><span data-stu-id="05811-105">To monitor usage, you can use the following:</span></span>

<span data-ttu-id="05811-106">**Для веб-интерфейса API объединенных коммуникаций (UCWA):**</span><span class="sxs-lookup"><span data-stu-id="05811-106">**For Unified Communications Web API (UCWA):**</span></span>

  - <span data-ttu-id="05811-107">Рабочий процесс **линкуква** в диспетчере информационных служб Интернета (IIS).</span><span class="sxs-lookup"><span data-stu-id="05811-107">The **LyncUcwa** worker process in Internet Information Services (IIS) Manager.</span></span> <span data-ttu-id="05811-108">На панели **Рабочие процессы** изучите столбцы **ЦП %** и **Частные байты (КБ)** (память).</span><span class="sxs-lookup"><span data-stu-id="05811-108">In the **Worker Processes** pane, look at the **CPU %** and **Private Bytes (KB)** (memory) columns.</span></span>

  - <span data-ttu-id="05811-109">Счетчики производительности **ЦП** и **Процессор**.</span><span class="sxs-lookup"><span data-stu-id="05811-109">The **CPU** and **Processor** performance counters.</span></span>

<span data-ttu-id="05811-110">В большинстве развертываний ресурсы ЦП, задействованные UCWA, не должны в среднем превышать 15 %.</span><span class="sxs-lookup"><span data-stu-id="05811-110">For most deployments, UCWA CPU usage should be below 15 percent on average.</span></span> <span data-ttu-id="05811-111">Использование памяти должно попадать в пределы, описанные в разделе Наблюдение за ограничениями объема [памяти сервера в Lync server 2013](lync-server-2013-monitoring-for-server-memory-capacity-limits.md).</span><span class="sxs-lookup"><span data-stu-id="05811-111">Memory usage should fall within the limits described in [Monitoring for server memory capacity limits in Lync Server 2013](lync-server-2013-monitoring-for-server-memory-capacity-limits.md).</span></span>

<span data-ttu-id="05811-112">Помимо счетчиков использования ЦП и памяти можно использовать следующие счетчики производительности, которые позволят определить степень перегрузки сервера запросами:</span><span class="sxs-lookup"><span data-stu-id="05811-112">In addition to CPU and memory usage counters, you can use the following performance counters to help determine when a server is overloaded with requests:</span></span>

  - <span data-ttu-id="05811-113">**Ls: веб — запросы на регулирование и\\проверку подлинности — общее количество запросов в обработке**, которое указывает число ожидающих веб-запросов на сервере.</span><span class="sxs-lookup"><span data-stu-id="05811-113">**LS:WEB – Throttling and Authentication\\WEB – Total Requests in Processing**, which indicates the number of pending web requests on the server.</span></span> <span data-ttu-id="05811-114">Если этот счетчик достигает 10 000, последующие запросы завершаются с ошибкой "503 — служба недоступна".</span><span class="sxs-lookup"><span data-stu-id="05811-114">When this counter reaches 10,000, subsequent requests will fail, with the error message, "503 - Service Unavailable."</span></span>

  - <span data-ttu-id="05811-115">**Запросов\\ASP.NET в очереди** (всегда должен равняться нулю).</span><span class="sxs-lookup"><span data-stu-id="05811-115">**ASP.NET\\Requests Queued** (should always be zero).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="05811-116">Если вы отвечаете или превышают эти значения, вы должны повторно посещать и пересчитывать планирование мощностей для правильного размера ЦП, количества ядер и памяти для компьютеров, на которых размещается веб-службы.</span><span class="sxs-lookup"><span data-stu-id="05811-116">If you meet or exceed these values, you should revisit and re-compute your capacity planning for the correct sizing of CPU, number of cores and memory for the computers hosting the Web services.</span></span>



</div>

<span data-ttu-id="05811-117">**Для службы Mobility Service (Mcx):**</span><span class="sxs-lookup"><span data-stu-id="05811-117">**For the Mobility Service (Mcx):**</span></span>

  - <span data-ttu-id="05811-118">Рабочие процессы **ксинтмкксапппул** и **ксекстмкксапппул** в диспетчере информационных служб Интернета (IIS).</span><span class="sxs-lookup"><span data-stu-id="05811-118">The **CSIntMcxAppPool** and **CSExtMcxAppPool** worker processes in Internet Information Services (IIS) Manager.</span></span> <span data-ttu-id="05811-119">На панели **Рабочие процессы** изучите столбцы **ЦП %** и **Частные байты (КБ)** (память).</span><span class="sxs-lookup"><span data-stu-id="05811-119">In the **Worker Processes** pane, look at the **CPU %** and **Private Bytes (KB)** (memory) columns.</span></span>

  - <span data-ttu-id="05811-120">Счетчики производительности **ЦП** и **Процессор**.</span><span class="sxs-lookup"><span data-stu-id="05811-120">The **CPU** and **Processor** performance counters.</span></span>

<span data-ttu-id="05811-121">В большинстве развертываний ресурсы ЦП, задействованные службой Mobility Service, не должны в среднем превышать 15 %.</span><span class="sxs-lookup"><span data-stu-id="05811-121">For most deployments, Mobility Service CPU usage should be below 15 percent, on average.</span></span> <span data-ttu-id="05811-122">Использование памяти должно попадать в пределы, описанные в разделе Наблюдение за ограничениями объема [памяти сервера в Lync server 2013](lync-server-2013-monitoring-for-server-memory-capacity-limits.md).</span><span class="sxs-lookup"><span data-stu-id="05811-122">Memory usage should fall within the limits described in [Monitoring for server memory capacity limits in Lync Server 2013](lync-server-2013-monitoring-for-server-memory-capacity-limits.md).</span></span>

<span data-ttu-id="05811-123">Помимо счетчиков производительности ЦП и памяти можно использовать следующие счетчики производительности ASP.NET, которые позволят определить степень перегрузки сервера запросами.</span><span class="sxs-lookup"><span data-stu-id="05811-123">In addition to CPU and memory usage counters, you can use the following ASP.NET performance counters to help determine when a server is overloaded with requests:</span></span>

  - <span data-ttu-id="05811-124">**Запросы ASP.NET v\\2.0.50727 Current**, обозначающие количество ожидающих веб-запросов на сервере.</span><span class="sxs-lookup"><span data-stu-id="05811-124">**ASP.NET v2.0.50727\\Requests Current**, which indicates the number of pending web requests on the server.</span></span> <span data-ttu-id="05811-125">Если этот счетчик достигает 5 000, последующие запросы завершаются с ошибкой "503 — служба недоступна".</span><span class="sxs-lookup"><span data-stu-id="05811-125">When this counter reaches 5,000, subsequent requests will fail with the error message, "503 - Service Unavailable."</span></span>

  - <span data-ttu-id="05811-126">**Запросов\\ASP.NET в очереди** (всегда должен равняться нулю).</span><span class="sxs-lookup"><span data-stu-id="05811-126">**ASP.NET\\Requests Queued** (should always be zero).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="05811-127">Если вы отвечаете или превышают эти значения, вы должны повторно посещать и повторно вычислять планирование производительности для правильного размера ЦП, количества ядер и памяти для компьютеров, на которых размещается веб-службы.</span><span class="sxs-lookup"><span data-stu-id="05811-127">If you meet or exceed these values, you should revisit and recompute your capacity planning for the correct sizing of CPU, number of cores, and memory for the computers hosting the Web services.</span></span>



</div>

<div>

## <a name="see-also"></a><span data-ttu-id="05811-128">См. также</span><span class="sxs-lookup"><span data-stu-id="05811-128">See Also</span></span>


[<span data-ttu-id="05811-129">Наблюдение за пределами объема памяти сервера в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="05811-129">Monitoring for server memory capacity limits in Lync Server 2013</span></span>](lync-server-2013-monitoring-for-server-memory-capacity-limits.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

