---
title: 'Lync Server 2013: отслеживание группового чата'
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
ms.openlocfilehash: fa350924503f430ec0494cc5e1eb17f7878084a1
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756853"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="monitoring-group-chat-in-lync-server-2013"></a><span data-ttu-id="86898-102">Мониторинг группового чата в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="86898-102">Monitoring group chat in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="86898-103">_**Тема последнего изменения:** 2014-08-04_</span><span class="sxs-lookup"><span data-stu-id="86898-103">_**Topic Last Modified:** 2014-08-04_</span></span>

<span data-ttu-id="86898-104">Мы настоятельно рекомендуем использовать последнюю версию [общего установщика обновлений на сервере](http://support.microsoft.com/kb/968802) , доступную в центре загрузки Майкрософт, для повышения производительности.</span><span class="sxs-lookup"><span data-stu-id="86898-104">We highly recommend running the most recent [Cumulative Server Update Installer](http://support.microsoft.com/kb/968802) available on the Microsoft Download Center for performance improvements.</span></span>

<span data-ttu-id="86898-105">Предполагается, что вы используете Последнее накопительное обновление, для метрики, чтобы понять, работают ли серверы группового чата в оптимальной работоспособности, используйте следующую таблицу с нагрузочным тестированием.</span><span class="sxs-lookup"><span data-stu-id="86898-105">Assuming you are running latest cumulative update, use the following stress test table for metrics to understand if your Group Chat Servers are running at optimal health.</span></span>

### <a name="test-environment-and-user-model"></a><span data-ttu-id="86898-106">Тестовая среда и пользовательская модель</span><span class="sxs-lookup"><span data-stu-id="86898-106">Test environment and user model</span></span>

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
<td><p><span data-ttu-id="86898-107">Три сервера группового чата в пуле группового чата, каждый из которых имеет 8 ГБ памяти и 8 процессоров.</span><span class="sxs-lookup"><span data-stu-id="86898-107">Three Group Chat Servers in a Group Chat pool, each with 8 GB memory and 8 processors.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86898-108">Два внешних сервера Lync Server 2013 в выпуске Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="86898-108">Two Lync Server 2013 Front Ends in Enterprise Edition.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86898-109">60 000 одновременные пользователи на трех серверах группового чата.</span><span class="sxs-lookup"><span data-stu-id="86898-109">60,000 concurrent users across three Group Chat Servers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86898-110">каналы 25 000, размещенные по группе группового чата.</span><span class="sxs-lookup"><span data-stu-id="86898-110">25,000 channels hosted by Group Chat Pool.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86898-111">Размер канала:</span><span class="sxs-lookup"><span data-stu-id="86898-111">Channel Size:</span></span></p>
<ul>
<li><p><span data-ttu-id="86898-112">Размер мелкого канала: 30</span><span class="sxs-lookup"><span data-stu-id="86898-112">Small Channel Size: 30</span></span></p></li>
<li><p><span data-ttu-id="86898-113">Средний размер канала: 150</span><span class="sxs-lookup"><span data-stu-id="86898-113">Medium Channel Size: 150</span></span></p></li>
<li><p><span data-ttu-id="86898-114">Размер большого канала: 2500</span><span class="sxs-lookup"><span data-stu-id="86898-114">Large Channel Size: 2500</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86898-115">Число каналов:</span><span class="sxs-lookup"><span data-stu-id="86898-115">Channel Count:</span></span></p>
<ul>
<li><p><span data-ttu-id="86898-116">Число малых каналов: 24 000</span><span class="sxs-lookup"><span data-stu-id="86898-116">Number small channels: 24,000</span></span></p></li>
<li><p><span data-ttu-id="86898-117">Число средних каналов 800</span><span class="sxs-lookup"><span data-stu-id="86898-117">Number medium channels 800</span></span></p></li>
<li><p><span data-ttu-id="86898-118">Число больших каналов 24</span><span class="sxs-lookup"><span data-stu-id="86898-118">Number large channels 24</span></span></p></li>
<li><p><span data-ttu-id="86898-119">Всего каналов 24 824</span><span class="sxs-lookup"><span data-stu-id="86898-119">Total Channels 24,824</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86898-120">Пригласите каналы:</span><span class="sxs-lookup"><span data-stu-id="86898-120">Invite channels:</span></span></p>
<ul>
<li><p><span data-ttu-id="86898-121">Половина каналов согласитесь с каналами</span><span class="sxs-lookup"><span data-stu-id="86898-121">Half the channels were invite channels</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86898-122">Количество каналов, к которым пользователь присоединяется:</span><span class="sxs-lookup"><span data-stu-id="86898-122">Number of channels a user joins:</span></span></p>
<ul>
<li><p><span data-ttu-id="86898-123">Мелкий: 12</span><span class="sxs-lookup"><span data-stu-id="86898-123">Small: 12</span></span></p></li>
<li><p><span data-ttu-id="86898-124">Средний: 2</span><span class="sxs-lookup"><span data-stu-id="86898-124">Medium: 2</span></span></p></li>
<li><p><span data-ttu-id="86898-125">Крупный: 1</span><span class="sxs-lookup"><span data-stu-id="86898-125">Large: 1</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86898-126">Скорость соединения:</span><span class="sxs-lookup"><span data-stu-id="86898-126">Join rate:</span></span></p>
<ul>
<li><p><span data-ttu-id="86898-127">10 всего за секунду, с 3,33 на сервер</span><span class="sxs-lookup"><span data-stu-id="86898-127">10 total/second, 3.33/second per server</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86898-128">Скорость выхода:</span><span class="sxs-lookup"><span data-stu-id="86898-128">Logout rate:</span></span></p>
<ul>
<li><p><span data-ttu-id="86898-129">10 всего за секунду, с 3,33 на сервер</span><span class="sxs-lookup"><span data-stu-id="86898-129">10 total/second, 3.33/second per server</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86898-130">Ставка чата:</span><span class="sxs-lookup"><span data-stu-id="86898-130">Chat rate:</span></span></p>
<ul>
<li><p><span data-ttu-id="86898-131">20 всего в секунду, 6.66/сек на сервер</span><span class="sxs-lookup"><span data-stu-id="86898-131">20 total/second, 6.66/second per server</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


<div>


> [!IMPORTANT]  
> <span data-ttu-id="86898-132">Указанные ниже номера счетчиков производительности, как правило, зависят от конфигурации разных аппаратных спецификаций или профилей пользователей.</span><span class="sxs-lookup"><span data-stu-id="86898-132">The following performance counter numbers will likely vary when different hardware specifications or user profiles are used.</span></span>



</div>

### <a name="performance-counter-to-be-monitored"></a><span data-ttu-id="86898-133">Счетчик производительности для наблюдения</span><span class="sxs-lookup"><span data-stu-id="86898-133">Performance counter to be monitored</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="86898-134">Счетчик производительности</span><span class="sxs-lookup"><span data-stu-id="86898-134">Performance Counter</span></span></th>
<th><span data-ttu-id="86898-135">Пороговые значения</span><span class="sxs-lookup"><span data-stu-id="86898-135">Thresholds</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="86898-136">Процесс (Чаннелсервице)-&gt;% Processor Time</span><span class="sxs-lookup"><span data-stu-id="86898-136">Process(ChannelService)-&gt;%Processor Time</span></span></p></td>
<td><p><span data-ttu-id="86898-137">Минимум: 0</span><span class="sxs-lookup"><span data-stu-id="86898-137">Min: 0</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

