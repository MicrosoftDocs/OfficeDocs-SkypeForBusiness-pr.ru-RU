---
title: 'Lync Server 2013: мониторинг ограничений объема памяти сервера'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Monitoring for server memory capacity limits
ms:assetid: 1697ea71-6fcf-480d-b4e9-cd79f94d247e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh689982(v=OCS.15)
ms:contentKeyID: 48183506
ms.date: 12/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 68728c85b14231644b445569857896f34abe535f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34826733"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="monitoring-for-server-memory-capacity-limits-in-lync-server-2013"></a><span data-ttu-id="b3b5f-102">Наблюдение за пределами объема памяти сервера в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b3b5f-102">Monitoring for server memory capacity limits in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b3b5f-103">_**Тема последнего изменения:** 2016-12-08_</span><span class="sxs-lookup"><span data-stu-id="b3b5f-103">_**Topic Last Modified:** 2016-12-08_</span></span>

    Some information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

<div>


> [!WARNING]  
> <span data-ttu-id="b3b5f-104">Информация, приведенная в этой статье, относится к планированию производственных мощностей только для мобильных клиентов Lync 2010 и службы Mobility Service (МККС).</span><span class="sxs-lookup"><span data-stu-id="b3b5f-104">The information in this topic that refers to Capacity Planning pertains only to Lync 2010 Mobile clients and the Mobility Service (Mcx).</span></span> <span data-ttu-id="b3b5f-105">Планирование ресурсов для веб-API единой системы обмена сообщениями (УКВА), используемого мобильными клиентами Lync 2013, предоставляется с помощью средства планирования Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b3b5f-105">Capacity Planning for the Unified Communications Web API (UCWA), used by the Lync 2013 Mobile clients, is provided by the Lync Server 2013, Planning Tool.</span></span>



</div>

<span data-ttu-id="b3b5f-106">С помощью двух счетчиков производительности для мобильных устройств вы можете определить текущее использование и помочь вам спланировать емкость для службы Lync Server 2013 Mobility Service (МККС), а также отслеживать использование памяти для УКВА.</span><span class="sxs-lookup"><span data-stu-id="b3b5f-106">Two mobility performance counters can help you to determine your current usage and help you plan capacity for the Lync Server 2013 Mobility Service (Mcx), as well as to monitor memory usage for UCWA.</span></span> <span data-ttu-id="b3b5f-107">Для UCWA счетчик имеет категорию **LS:WEB – UCWA**.</span><span class="sxs-lookup"><span data-stu-id="b3b5f-107">For UCWA, the counter category is **LS:WEB – UCWA**.</span></span> <span data-ttu-id="b3b5f-108">Для службы Mobility Service (Mcx) счетчики относятся к категории **LS:WEB — Mobile Communication Service**.</span><span class="sxs-lookup"><span data-stu-id="b3b5f-108">For the Mobility Service (Mcx), the counters are under the category **LS:WEB - Mobile Communication Service**.</span></span> <span data-ttu-id="b3b5f-109">Отслеживаемые счетчики:</span><span class="sxs-lookup"><span data-stu-id="b3b5f-109">The counters to monitor are:</span></span>

  - <span data-ttu-id="b3b5f-110">**Currently Active Session Count with Active Presence Subscriptions** (Число активных в настоящее время сеансов с активными подписками отслеживания присутствия), который обозначает текущее число конечных точек, зарегистрированных через UCWA или службу Mobility Service, с активными подписками отслеживания присутствия (число мобильных пользователей с постоянным подключением).</span><span class="sxs-lookup"><span data-stu-id="b3b5f-110">**Currently Active Session Count with Active Presence Subscriptions**, which is the current number of endpoints registered through UCWA or the Mobility Service (Mcx) that have active presence subscriptions (number of always-connected mobile users)</span></span>

  - <span data-ttu-id="b3b5f-111">**Currently Active Session Count** (Число активных сеансов в настоящее время), который обозначает текущее число конечных точек, зарегистрированных через UCWA или службу Mobility Service.</span><span class="sxs-lookup"><span data-stu-id="b3b5f-111">**Currently Active Session Count**, which is the current number of endpoints registered through UCWA or the Mobility Service</span></span>

<span data-ttu-id="b3b5f-112">Если разница между счетчиками **Currently Active Session Count with Active Presence Subscriptions** (Число активных в настоящее время сеансов с активными подписками отслеживания присутствия) и **Currently Active Session Count** (Число активных сеансов в настоящее время) небольшая, это означает, что у большинства пользователей мобильных устройств есть постоянно подключенное устройство, например устройство Android или Nokia (только для Mcx).</span><span class="sxs-lookup"><span data-stu-id="b3b5f-112">If the difference between **Currently Active Session Count with Active Presence Subscriptions** and **Currently Active Session Count** is small over time, this means that most mobile device users have an always-connected device, such as an Android or Nokia mobile device (for Mcx only).</span></span> <span data-ttu-id="b3b5f-113">УКВА всегда подключенные устройства включают устройства Apple и Android, которые работают с мобильными клиентами Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="b3b5f-113">UCWA always-connected devices include Apple and Android devices running Lync 2013 Mobile clients).</span></span> <span data-ttu-id="b3b5f-114">Если значение **Currently Active Session Count** (Число активных сеансов в настоящее время) гораздо больше значения **Currently Active Session Count with Active Presence Subscriptions** (Число активных в настоящее время сеансов с активными подписками отслеживания присутствия), это означает, что большее число пользователей применяют в Mcx фоновое оконечное устройство, такое как устройство с Apple IOS или Windows Phone.</span><span class="sxs-lookup"><span data-stu-id="b3b5f-114">If **Currently Active Session Count** is much higher than **Currently Active Session Count with Active Presence Subscriptions**, this indicates that more users are using a background endpoint device, such as an Apple iOS device or Windows Phone under Mcx.</span></span> <span data-ttu-id="b3b5f-115">(Windows Phone — единственный мобильный клиент Lync 2013, который будет зарегистрирован как это).</span><span class="sxs-lookup"><span data-stu-id="b3b5f-115">(Windows Phone is the only Lync 2013 Mobile client that will register as this).</span></span>

<span data-ttu-id="b3b5f-116">Вы должны установить ограничение на **текущий активный счетчик сеансов с активными подписками** на открытые и активные \*\*\*\* счетчики производительности в соответствии с ожидаемым использованием, результатами планирования мощности и текущим мониторингом Служба Mobility Service и другие счетчики серверного переднего плана.</span><span class="sxs-lookup"><span data-stu-id="b3b5f-116">You should set a limit on the **Currently Active Session Count with Active Presence Subscriptions** and **Currently Active Session Count** performance counters based on your expected usage, capacity planning results, and ongoing monitoring of Mobility Service and other Front End Server counters.</span></span> <span data-ttu-id="b3b5f-117">Установленные ограничения должны позволять вам оценить мощность сервера и создать оповещения при ее превышении.</span><span class="sxs-lookup"><span data-stu-id="b3b5f-117">The limits you set should enable you to evaluate server capacity and raise alerts when capacity is exceeded.</span></span>

<span data-ttu-id="b3b5f-118">Чтобы определить соответствующие ограничения, необходимо сначала определить объем памяти, доступной на сервере переднего плана для службы Mobility Service.</span><span class="sxs-lookup"><span data-stu-id="b3b5f-118">To determine the appropriate limits, you need to first determine how much memory is available on the Front End Server for the Mobility Service.</span></span> <span data-ttu-id="b3b5f-119">Отслеживайте счетчики, чтобы определить, когда требуется запланировать дополнительную емкость в соответствии со следующей формулой:</span><span class="sxs-lookup"><span data-stu-id="b3b5f-119">Monitor the counters to determine when you need to plan for extra capacity, according to the following formula:</span></span>

<span data-ttu-id="b3b5f-120">Общий объем памяти, используемой службой Mobility МККС (MB) = 164 + (400 + 134)/ \* 1024 **число сеансов в настоящее время с активными подпиской на присутствие** + 400/1024 \* (**текущее активное число сеансов** — **текущее активное количество сеанса) с активными подписками на присутствие**)</span><span class="sxs-lookup"><span data-stu-id="b3b5f-120">Total memory used by the Mcx Mobility Service (MB) = 164 + (400 + 134) / 1024 \* **Currently Active Session Count with Active Presence Subscriptions** + 400 / 1024 \* (**Currently Active Session Count** – **Currently Active Session Count with Active Presence Subscriptions**)</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="b3b5f-121">Калькулятор Microsoft Lync Server 2010 Capacity — это электронная таблица, в которой предварительно заполнены все формулы, позволяющие планирующему определять требования к серверам, в том числе к ЦП, памяти и жесткому диску.</span><span class="sxs-lookup"><span data-stu-id="b3b5f-121">The Microsoft Lync Server 2010 Capacity Calculator is a spreadsheet that is prepopulated with all of the formulas that enable a planner to determine what the requirements will be for the servers, including CPU, memory, and hard drive.</span></span> <span data-ttu-id="b3b5f-122">Вы можете загрузить электронную таблицу и связанный документ по адресу:<A href="https://go.microsoft.com/fwlink/p/?linkid=212657">https://go.microsoft.com/fwlink/p/?LinkID=212657</A></span><span class="sxs-lookup"><span data-stu-id="b3b5f-122">You can download the spreadsheet and an associated document at: <A href="https://go.microsoft.com/fwlink/p/?linkid=212657">https://go.microsoft.com/fwlink/p/?LinkID=212657</A></span></span>



</div>

<span data-ttu-id="b3b5f-123">На сервере переднего плана достаточно памяти, чтобы обеспечить поддержку службы Mobility Service в случае отказа.</span><span class="sxs-lookup"><span data-stu-id="b3b5f-123">The Front End Server needs enough available memory to support the Mobility Service in failover situations.</span></span> <span data-ttu-id="b3b5f-124">Вы можете отслеживать текущую доступную память на сервере переднего плана с помощью счетчика **объемом памяти\\** , доступного в мегабайтах, или с помощью упомянутого выше уравнения, чтобы спланировать объем памяти, который ожидается в службе Mobility Service.</span><span class="sxs-lookup"><span data-stu-id="b3b5f-124">You can monitor the current available memory on the Front End Server by using the **Memory\\Available Mbytes** counter, or by using the equation mentioned earlier, to plan for the amount of memory that you expect the Mobility Service to use.</span></span>

<span data-ttu-id="b3b5f-125">Если объем памяти, доступный на сервере переднего плана, не превышает 1 500 МБ, то при планировании количества пользователей мобильных устройств необходимо добавить дополнительное оборудование для поддержки службы Mobility Service.</span><span class="sxs-lookup"><span data-stu-id="b3b5f-125">If the amount of memory available on the Front End Server is lower than 1,500 MB when you plan for the expected number of mobility users, you need to add more hardware to support the Mobility Service.</span></span> <span data-ttu-id="b3b5f-126">Дополнительные сведения можно найти [в разделе Наблюдение за производительностью мобильных устройств в Lync Server 2013](lync-server-2013-monitoring-mobility-for-performance.md) в документации по эксплуатации.</span><span class="sxs-lookup"><span data-stu-id="b3b5f-126">For more details, see [Monitoring mobility for performance in Lync Server 2013](lync-server-2013-monitoring-mobility-for-performance.md) in the Operations documentation.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="b3b5f-127">См. также</span><span class="sxs-lookup"><span data-stu-id="b3b5f-127">See Also</span></span>


[<span data-ttu-id="b3b5f-128">Мониторинг мобильных устройств для повышения производительности в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b3b5f-128">Monitoring mobility for performance in Lync Server 2013</span></span>](lync-server-2013-monitoring-mobility-for-performance.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

