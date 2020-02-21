---
title: 'Lync Server 2013: мониторинг группового чата'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Monitoring group chat
ms:assetid: bddcf0be-ebf3-46bc-90c7-2576877734fb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720924(v=OCS.15)
ms:contentKeyID: 63969648
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8c8d2a544c9a20e16e9a9f6510002ef5dd3e695e
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42184752"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="monitoring-group-chat-in-lync-server-2013"></a><span data-ttu-id="9069f-102">Отслеживание чата группового чата в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9069f-102">Monitoring group chat in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9069f-103">_**Последнее изменение темы:** 2014-08-04_</span><span class="sxs-lookup"><span data-stu-id="9069f-103">_**Topic Last Modified:** 2014-08-04_</span></span>

<span data-ttu-id="9069f-104">Мы настоятельно рекомендуем запускать самый последний [накопительный пакет обновления на сервере](https://support.microsoft.com/kb/968802) , доступный в центре загрузки Майкрософт, чтобы повысить производительность.</span><span class="sxs-lookup"><span data-stu-id="9069f-104">We highly recommend running the most recent [Cumulative Server Update Installer](https://support.microsoft.com/kb/968802) available on the Microsoft Download Center for performance improvements.</span></span>

<span data-ttu-id="9069f-105">Если вы используете Последнее накопительное обновление, воспользуйтесь следующей таблицей нагрузочного тестирования для получения метрик, чтобы определить, работают ли серверы группового чата в оптимальной работоспособности.</span><span class="sxs-lookup"><span data-stu-id="9069f-105">Assuming you are running latest cumulative update, use the following stress test table for metrics to understand if your Group Chat Servers are running at optimal health.</span></span>

### <a name="test-environment-and-user-model"></a><span data-ttu-id="9069f-106">Тестовая среда и пользовательская модель</span><span class="sxs-lookup"><span data-stu-id="9069f-106">Test environment and user model</span></span>

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th> </th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9069f-107">Три сервера группового чата в пуле группового чата, каждая из которых имеет 8 ГБ памяти и 8 процессоров.</span><span class="sxs-lookup"><span data-stu-id="9069f-107">Three Group Chat Servers in a Group Chat pool, each with 8 GB memory and 8 processors.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9069f-108">Два интерфейсных сервера Lync Server 2013 в Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="9069f-108">Two Lync Server 2013 Front Ends in Enterprise Edition.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9069f-109">60 000 одновременно работающих пользователей на трех серверах группового чата.</span><span class="sxs-lookup"><span data-stu-id="9069f-109">60,000 concurrent users across three Group Chat Servers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9069f-110">25 000 каналы, размещенные по пулу группового чата.</span><span class="sxs-lookup"><span data-stu-id="9069f-110">25,000 channels hosted by Group Chat Pool.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9069f-111">Размер канала:</span><span class="sxs-lookup"><span data-stu-id="9069f-111">Channel Size:</span></span></p>
<ul>
<li><p><span data-ttu-id="9069f-112">Малый размер канала: 30</span><span class="sxs-lookup"><span data-stu-id="9069f-112">Small Channel Size: 30</span></span></p></li>
<li><p><span data-ttu-id="9069f-113">Средний размер канала: 150</span><span class="sxs-lookup"><span data-stu-id="9069f-113">Medium Channel Size: 150</span></span></p></li>
<li><p><span data-ttu-id="9069f-114">Большой размер канала: 2500</span><span class="sxs-lookup"><span data-stu-id="9069f-114">Large Channel Size: 2500</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9069f-115">Число каналов:</span><span class="sxs-lookup"><span data-stu-id="9069f-115">Channel Count:</span></span></p>
<ul>
<li><p><span data-ttu-id="9069f-116">Число маленьких каналов: 24 000</span><span class="sxs-lookup"><span data-stu-id="9069f-116">Number small channels: 24,000</span></span></p></li>
<li><p><span data-ttu-id="9069f-117">Число средних каналов 800</span><span class="sxs-lookup"><span data-stu-id="9069f-117">Number medium channels 800</span></span></p></li>
<li><p><span data-ttu-id="9069f-118">Число больших каналов 24</span><span class="sxs-lookup"><span data-stu-id="9069f-118">Number large channels 24</span></span></p></li>
<li><p><span data-ttu-id="9069f-119">Общее число каналов 24 824</span><span class="sxs-lookup"><span data-stu-id="9069f-119">Total Channels 24,824</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9069f-120">Каналы приглашений:</span><span class="sxs-lookup"><span data-stu-id="9069f-120">Invite channels:</span></span></p>
<ul>
<li><p><span data-ttu-id="9069f-121">Половина каналов были приглашены каналы</span><span class="sxs-lookup"><span data-stu-id="9069f-121">Half the channels were invite channels</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9069f-122">Число каналов, к которым присоединяется пользователь:</span><span class="sxs-lookup"><span data-stu-id="9069f-122">Number of channels a user joins:</span></span></p>
<ul>
<li><p><span data-ttu-id="9069f-123">Малый размер: 12</span><span class="sxs-lookup"><span data-stu-id="9069f-123">Small: 12</span></span></p></li>
<li><p><span data-ttu-id="9069f-124">Средний: 2</span><span class="sxs-lookup"><span data-stu-id="9069f-124">Medium: 2</span></span></p></li>
<li><p><span data-ttu-id="9069f-125">Крупный: 1</span><span class="sxs-lookup"><span data-stu-id="9069f-125">Large: 1</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9069f-126">Скорость соединения:</span><span class="sxs-lookup"><span data-stu-id="9069f-126">Join rate:</span></span></p>
<ul>
<li><p><span data-ttu-id="9069f-127">10, каждую секунду, в секунду на один сервер</span><span class="sxs-lookup"><span data-stu-id="9069f-127">10 total/second, 3.33/second per server</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9069f-128">Скорость выхода:</span><span class="sxs-lookup"><span data-stu-id="9069f-128">Logout rate:</span></span></p>
<ul>
<li><p><span data-ttu-id="9069f-129">10, каждую секунду, в секунду на один сервер</span><span class="sxs-lookup"><span data-stu-id="9069f-129">10 total/second, 3.33/second per server</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9069f-130">Частота чата:</span><span class="sxs-lookup"><span data-stu-id="9069f-130">Chat rate:</span></span></p>
<ul>
<li><p><span data-ttu-id="9069f-131">20 всего в секунду, 6.66/сек на сервер</span><span class="sxs-lookup"><span data-stu-id="9069f-131">20 total/second, 6.66/second per server</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


<div>


> [!IMPORTANT]  
> <span data-ttu-id="9069f-132">Следующие номера счетчиков производительности, скорее всего, будут отличаться при использовании различных спецификаций оборудования или профилей пользователей.</span><span class="sxs-lookup"><span data-stu-id="9069f-132">The following performance counter numbers will likely vary when different hardware specifications or user profiles are used.</span></span>



</div>

### <a name="performance-counter-to-be-monitored"></a><span data-ttu-id="9069f-133">Отслеживаемый счетчик производительности</span><span class="sxs-lookup"><span data-stu-id="9069f-133">Performance counter to be monitored</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9069f-134">Счетчик производительности</span><span class="sxs-lookup"><span data-stu-id="9069f-134">Performance Counter</span></span></th>
<th><span data-ttu-id="9069f-135">Пороговые значения</span><span class="sxs-lookup"><span data-stu-id="9069f-135">Thresholds</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9069f-136">Процесс (Чаннелсервице)-&gt;% загруженности процессора</span><span class="sxs-lookup"><span data-stu-id="9069f-136">Process(ChannelService)-&gt;%Processor Time</span></span></p></td>
<td><p><span data-ttu-id="9069f-137">Минимум: 0</span><span class="sxs-lookup"><span data-stu-id="9069f-137">Min: 0</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

