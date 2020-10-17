---
title: 'Lync Server 2013: мониторинг пределов объема памяти сервера'
description: 'Lync Server 2013: мониторинг пределов объема памяти для сервера.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Monitoring for server memory capacity limits
ms:assetid: 1697ea71-6fcf-480d-b4e9-cd79f94d247e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh689982(v=OCS.15)
ms:contentKeyID: 48183506
ms.date: 12/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6561908af2c8f2f7b5fb9e347cc6247f7ca6642e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48562055"
---
# <a name="monitoring-for-server-memory-capacity-limits-in-lync-server-2013"></a><span data-ttu-id="61835-103">Мониторинг пределов объема памяти сервера в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="61835-103">Monitoring for server memory capacity limits in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="61835-104">_**Последнее изменение темы:** 2016-12-08_</span><span class="sxs-lookup"><span data-stu-id="61835-104">_**Topic Last Modified:** 2016-12-08_</span></span>

    Some information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

<div>


> [!WARNING]  
> <span data-ttu-id="61835-105">Сведения, приведенные в этом разделе, относятся к планированию мощности только для мобильных клиентов Lync 2010 и службы Mobility Service (MCX).</span><span class="sxs-lookup"><span data-stu-id="61835-105">The information in this topic that refers to Capacity Planning pertains only to Lync 2010 Mobile clients and the Mobility Service (Mcx).</span></span> <span data-ttu-id="61835-106">Планирование емкости для веб-интерфейса API объединенных коммуникаций (UCWA), используемого мобильными клиентами Lync 2013, предоставляется в средстве Lync Server 2013, Planning Tool.</span><span class="sxs-lookup"><span data-stu-id="61835-106">Capacity Planning for the Unified Communications Web API (UCWA), used by the Lync 2013 Mobile clients, is provided by the Lync Server 2013, Planning Tool.</span></span>



</div>

<span data-ttu-id="61835-107">Два счетчика производительности мобильности помогут вам определить текущее использование и помочь вам спланировать мощность для службы Mobility Lync Server 2013 (MCX), а также для мониторинга использования памяти для UCWA.</span><span class="sxs-lookup"><span data-stu-id="61835-107">Two mobility performance counters can help you to determine your current usage and help you plan capacity for the Lync Server 2013 Mobility Service (Mcx), as well as to monitor memory usage for UCWA.</span></span> <span data-ttu-id="61835-108">Для UCWA Категория счетчика — **Ls: Web — UCWA**.</span><span class="sxs-lookup"><span data-stu-id="61835-108">For UCWA, the counter category is **LS:WEB – UCWA**.</span></span> <span data-ttu-id="61835-109">Для службы Mobility Service (MCX) счетчики находятся в категории **Ls: Web — Mobile Communication Service**.</span><span class="sxs-lookup"><span data-stu-id="61835-109">For the Mobility Service (Mcx), the counters are under the category **LS:WEB - Mobile Communication Service**.</span></span> <span data-ttu-id="61835-110">Счетчики для отслеживания:</span><span class="sxs-lookup"><span data-stu-id="61835-110">The counters to monitor are:</span></span>

  - <span data-ttu-id="61835-111">Число **активных активных сеансов с активными подписками на присутствие**, которые являются текущим количеством конечных точек, зарегистрированных с помощью UCWA, или службой Mobility Service (MCX), которые имеют активные подписки на присутствие (число мобильных пользователей с постоянным подключением)</span><span class="sxs-lookup"><span data-stu-id="61835-111">**Currently Active Session Count with Active Presence Subscriptions**, which is the current number of endpoints registered through UCWA or the Mobility Service (Mcx) that have active presence subscriptions (number of always-connected mobile users)</span></span>

  - <span data-ttu-id="61835-112">Текущее число **активных сеансов**(текущее число конечных точек, зарегистрированных с помощью UCWA или службы Mobility Service)</span><span class="sxs-lookup"><span data-stu-id="61835-112">**Currently Active Session Count**, which is the current number of endpoints registered through UCWA or the Mobility Service</span></span>

<span data-ttu-id="61835-113">Если разница между **числом текущих активных сеансов с активными подписками на присутствие** и **числом активных сеансов** невелика по времени, это означает, что большинство пользователей мобильных устройств имеют постоянное подключенное устройство, такое как Android или Nokia Mobile Device (только для MCX).</span><span class="sxs-lookup"><span data-stu-id="61835-113">If the difference between **Currently Active Session Count with Active Presence Subscriptions** and **Currently Active Session Count** is small over time, this means that most mobile device users have an always-connected device, such as an Android or Nokia mobile device (for Mcx only).</span></span> <span data-ttu-id="61835-114">UCWA Always-Connected Devices включают устройства Apple и Android, работающие под управлением Lync 2013 Mobile Clients.</span><span class="sxs-lookup"><span data-stu-id="61835-114">UCWA always-connected devices include Apple and Android devices running Lync 2013 Mobile clients).</span></span> <span data-ttu-id="61835-115">Если **текущее активное число сеансов** превышает **число активных в настоящее время сеансов с активными подписками на присутствие**, это указывает на то, что больше пользователей используется устройство фоновой конечной точки, такое как устройство Apple iOS или Windows Phone в разделе MCX.</span><span class="sxs-lookup"><span data-stu-id="61835-115">If **Currently Active Session Count** is much higher than **Currently Active Session Count with Active Presence Subscriptions**, this indicates that more users are using a background endpoint device, such as an Apple iOS device or Windows Phone under Mcx.</span></span> <span data-ttu-id="61835-116">(Windows Phone — единственный мобильный клиент Lync 2013, который будет зарегистрирован в качестве этого).</span><span class="sxs-lookup"><span data-stu-id="61835-116">(Windows Phone is the only Lync 2013 Mobile client that will register as this).</span></span>

<span data-ttu-id="61835-117">Необходимо установить предельное число текущих **активных сеансов с активными подписками** и счетчиками производительности текущих **активных сеансов** в зависимости от ожидаемого использования, результатов планирования мощности и постоянного мониторинга службы Mobility Service и других счетчиков сервера переднего плана.</span><span class="sxs-lookup"><span data-stu-id="61835-117">You should set a limit on the **Currently Active Session Count with Active Presence Subscriptions** and **Currently Active Session Count** performance counters based on your expected usage, capacity planning results, and ongoing monitoring of Mobility Service and other Front End Server counters.</span></span> <span data-ttu-id="61835-118">Заданные вами пределы должны позволять вам оценивать емкость сервера и создавать оповещения при превышении емкости.</span><span class="sxs-lookup"><span data-stu-id="61835-118">The limits you set should enable you to evaluate server capacity and raise alerts when capacity is exceeded.</span></span>

<span data-ttu-id="61835-119">Чтобы определить соответствующие пределы, необходимо сначала определить объем памяти, доступной на сервере переднего плана для службы Mobility Service.</span><span class="sxs-lookup"><span data-stu-id="61835-119">To determine the appropriate limits, you need to first determine how much memory is available on the Front End Server for the Mobility Service.</span></span> <span data-ttu-id="61835-120">Следите за счетчиками, чтобы определить, когда необходимо запланировать дополнительную емкость в соответствии со следующей формулой:</span><span class="sxs-lookup"><span data-stu-id="61835-120">Monitor the counters to determine when you need to plan for extra capacity, according to the following formula:</span></span>

<span data-ttu-id="61835-121">Общий объем памяти, используемой службой Mobility MCX (МБ) = 164 + (400 + 134)/1024 \* **число активных сеансов с активными подписками о присутствии** + 400/1024 \* (**текущие активные счетчики сеансов** — **текущее активное число сеансов с активными подписками на присутствие**)</span><span class="sxs-lookup"><span data-stu-id="61835-121">Total memory used by the Mcx Mobility Service (MB) = 164 + (400 + 134) / 1024 \* **Currently Active Session Count with Active Presence Subscriptions** + 400 / 1024 \* (**Currently Active Session Count** – **Currently Active Session Count with Active Presence Subscriptions**)</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="61835-122">Калькулятор емкости Microsoft Lync Server 2010 — это электронная таблица, которая заполняется всеми формулами, которые позволяют планировщику определить требования к серверам, в том числе ЦП, память и жесткий диск.</span><span class="sxs-lookup"><span data-stu-id="61835-122">The Microsoft Lync Server 2010 Capacity Calculator is a spreadsheet that is prepopulated with all of the formulas that enable a planner to determine what the requirements will be for the servers, including CPU, memory, and hard drive.</span></span> <span data-ttu-id="61835-123">Вы можете скачать электронную таблицу и соответствующий документ по адресу: <A href="https://go.microsoft.com/fwlink/p/?linkid=212657">https://go.microsoft.com/fwlink/p/?LinkID=212657</A></span><span class="sxs-lookup"><span data-stu-id="61835-123">You can download the spreadsheet and an associated document at: <A href="https://go.microsoft.com/fwlink/p/?linkid=212657">https://go.microsoft.com/fwlink/p/?LinkID=212657</A></span></span>



</div>

<span data-ttu-id="61835-124">На сервере переднего плана требуется достаточно памяти для поддержки службы Mobility Service в ситуациях отработки отказа.</span><span class="sxs-lookup"><span data-stu-id="61835-124">The Front End Server needs enough available memory to support the Mobility Service in failover situations.</span></span> <span data-ttu-id="61835-125">Вы можете отслеживать текущую доступную память на сервере переднего плана с помощью счетчика **Мбайт памяти, \\ доступного для памяти** , или с помощью уравнения, упомянутого ранее, для планирования объема памяти, который будет использоваться службой Mobility Service.</span><span class="sxs-lookup"><span data-stu-id="61835-125">You can monitor the current available memory on the Front End Server by using the **Memory\\Available Mbytes** counter, or by using the equation mentioned earlier, to plan for the amount of memory that you expect the Mobility Service to use.</span></span>

<span data-ttu-id="61835-126">Если объем доступной памяти на сервере переднего плана ниже 1 500 МБ при планировании ожидаемого числа пользователей мобильных устройств, необходимо добавить оборудование для поддержки службы Mobility Service.</span><span class="sxs-lookup"><span data-stu-id="61835-126">If the amount of memory available on the Front End Server is lower than 1,500 MB when you plan for the expected number of mobility users, you need to add more hardware to support the Mobility Service.</span></span> <span data-ttu-id="61835-127">Более подробную информацию можно узнать [в статье мониторинг мобильности в целях повышения производительности в Lync Server 2013](lync-server-2013-monitoring-mobility-for-performance.md) в документации по операциям.</span><span class="sxs-lookup"><span data-stu-id="61835-127">For more details, see [Monitoring mobility for performance in Lync Server 2013](lync-server-2013-monitoring-mobility-for-performance.md) in the Operations documentation.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="61835-128">См. также</span><span class="sxs-lookup"><span data-stu-id="61835-128">See Also</span></span>


[<span data-ttu-id="61835-129">Наблюдение за производительностью мобильных устройств в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="61835-129">Monitoring mobility for performance in Lync Server 2013</span></span>](lync-server-2013-monitoring-mobility-for-performance.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

