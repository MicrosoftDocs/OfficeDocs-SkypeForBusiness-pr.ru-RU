---
title: 'Lync Server 2013: таблица Аппшарингстреам'
description: 'Lync Server 2013: таблица Аппшарингстреам.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: AppSharingStream table
ms:assetid: 391490cb-d7b8-44ca-b4d1-429600da909c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204808(v=OCS.15)
ms:contentKeyID: 48183852
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b530af5b489e090e5d0d00fbb01b2b950bafbe5a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48574725"
---
# <a name="appsharingstream-table-in-lync-server-2013"></a><span data-ttu-id="2a974-103">Таблица Аппшарингстреам в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2a974-103">AppSharingStream table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2a974-104">_**Последнее изменение темы:** 2014-02-21_</span><span class="sxs-lookup"><span data-stu-id="2a974-104">_**Topic Last Modified:** 2014-02-21_</span></span>

<span data-ttu-id="2a974-105">В таблице AppSharingStream содержатся показатели качества взаимодействия для сетевых потоков, используемых для общего доступа к приложениям.</span><span class="sxs-lookup"><span data-stu-id="2a974-105">The AppSharingStream table contains Quality of Experience metrics for the network streams used for application sharing.</span></span> <span data-ttu-id="2a974-106">Эта таблица была введена в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2a974-106">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2a974-107"><strong>Column</strong></span><span class="sxs-lookup"><span data-stu-id="2a974-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="2a974-108"><strong>Тип данных</strong></span><span class="sxs-lookup"><span data-stu-id="2a974-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="2a974-109"><strong>Ключ или индекс</strong></span><span class="sxs-lookup"><span data-stu-id="2a974-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="2a974-110"><strong>Details</strong></span><span class="sxs-lookup"><span data-stu-id="2a974-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2a974-111"><strong>конференцедатетиме</strong></span><span class="sxs-lookup"><span data-stu-id="2a974-111"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="2a974-112">dateTime</span><span class="sxs-lookup"><span data-stu-id="2a974-112">dateTime</span></span></p></td>
<td><p><span data-ttu-id="2a974-113">Основной, внешний</span><span class="sxs-lookup"><span data-stu-id="2a974-113">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="2a974-114">Дата и время начала сеанса.</span><span class="sxs-lookup"><span data-stu-id="2a974-114">Date and time that the session started.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a974-115"><strong>сессионсек</strong></span><span class="sxs-lookup"><span data-stu-id="2a974-115"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="2a974-116">int</span><span class="sxs-lookup"><span data-stu-id="2a974-116">int</span></span></p></td>
<td><p><span data-ttu-id="2a974-117">Основной, внешний</span><span class="sxs-lookup"><span data-stu-id="2a974-117">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="2a974-118">Порядковый идентификатор, используемый для используется для проведения различия между сеансами, которые начались в один и тот же день и в одно и то же время.</span><span class="sxs-lookup"><span data-stu-id="2a974-118">Sequential identifier used to distinguish between sessions that started on the same date and at the same time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a974-119"><strong>медиалинелабел</strong></span><span class="sxs-lookup"><span data-stu-id="2a974-119"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="2a974-120">tinyint</span><span class="sxs-lookup"><span data-stu-id="2a974-120">tinyint</span></span></p></td>
<td><p><span data-ttu-id="2a974-121">Основной, внешний</span><span class="sxs-lookup"><span data-stu-id="2a974-121">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="2a974-p102">Представляет тип видеоканала, используемого для звонка. Допускаются следующие значения:</span><span class="sxs-lookup"><span data-stu-id="2a974-p102">Represents the type of video line used in the call. Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="2a974-124">0 — звук</span><span class="sxs-lookup"><span data-stu-id="2a974-124">0 – Audio</span></span></p></li>
<li><p><span data-ttu-id="2a974-125">1 — видео</span><span class="sxs-lookup"><span data-stu-id="2a974-125">1 – Video</span></span></p></li>
<li><p><span data-ttu-id="2a974-126">2 — панорамное видео</span><span class="sxs-lookup"><span data-stu-id="2a974-126">2 – Panoramic video</span></span></p></li>
<li><p><span data-ttu-id="2a974-127">3 — общий доступ к приложениям и рабочим столам</span><span class="sxs-lookup"><span data-stu-id="2a974-127">3 –Application/Desktop Sharing</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a974-128"><strong>стреамид</strong></span><span class="sxs-lookup"><span data-stu-id="2a974-128"><strong>StreamID</strong></span></span></p></td>
<td><p><span data-ttu-id="2a974-129">int</span><span class="sxs-lookup"><span data-stu-id="2a974-129">int</span></span></p></td>
<td><p><span data-ttu-id="2a974-130">Primary</span><span class="sxs-lookup"><span data-stu-id="2a974-130">Primary</span></span></p></td>
<td><p><span data-ttu-id="2a974-131">Уникальный идентификатор потока общего доступа к приложениям.</span><span class="sxs-lookup"><span data-stu-id="2a974-131">Unique identifier of the application sharing stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a974-132"><strong>життеринтерарривал</strong></span><span class="sxs-lookup"><span data-stu-id="2a974-132"><strong>JitterInterArrival</strong></span></span></p></td>
<td><p><span data-ttu-id="2a974-133">int</span><span class="sxs-lookup"><span data-stu-id="2a974-133">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2a974-134">Среднее значение колебаний, зарегистрированных между прибытиями пакетов RTP.</span><span class="sxs-lookup"><span data-stu-id="2a974-134">Average jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="2a974-135">(Колебание — это мера &quot; вибрирования &quot; вызова.) Большие значения колебаний обычно вызваны перегрузкой или перегрузкой сервера мультимедиа, что приводит к искажению или потере звука.</span><span class="sxs-lookup"><span data-stu-id="2a974-135">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a974-136"><strong>життеринтерарривалмакс</strong></span><span class="sxs-lookup"><span data-stu-id="2a974-136"><strong>JitterInterArrivalMax</strong></span></span></p></td>
<td><p><span data-ttu-id="2a974-137">int</span><span class="sxs-lookup"><span data-stu-id="2a974-137">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2a974-138">Максимальное значение колебаний, зарегистрированных между прибытиями пакетов RTP.</span><span class="sxs-lookup"><span data-stu-id="2a974-138">Maximum jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="2a974-139">(Колебание — это мера &quot; вибрирования &quot; вызова.) Большие значения колебаний обычно вызваны перегрузкой или перегрузкой сервера мультимедиа, что приводит к искажению или потере звука.</span><span class="sxs-lookup"><span data-stu-id="2a974-139">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a974-140"><strong>Обработки</strong></span><span class="sxs-lookup"><span data-stu-id="2a974-140"><strong>RoundTrip</strong></span></span></p></td>
<td><p><span data-ttu-id="2a974-141">int</span><span class="sxs-lookup"><span data-stu-id="2a974-141">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2a974-p105">Среднее время (в миллисекундах), необходимое для перемещения пакета Real-Time Transport Protocol в другую конечную точку и его возврата. Приемлемым считается время двусторонней передачи, равное 200 мс (или менее).</span><span class="sxs-lookup"><span data-stu-id="2a974-p105">Average amount of (in milliseconds) required for a Real-Time Transport Protocol packet to travel to another endpoint and then back. Round-trip times of 200 milliseconds or less are considered of acceptable quality.</span></span></p>
<p><span data-ttu-id="2a974-p106">Высокие значения времени двусторонней передачи могут быть обусловлены международной маршрутизацией вызовов, неправильной конфигурацией маршрутизации или перегрузкой сервера-посредника. Длительное время двусторонней передачи приводит к возникновению проблем при двусторонних аудиоразговорах в режиме реального времени.</span><span class="sxs-lookup"><span data-stu-id="2a974-p106">High round-trip values can be caused by international call routing; a routing misconfiguration; or an overloaded media server. High round-trip times result in difficulties with two-way, real-time audio conversations.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a974-146"><strong>раундтрипмакс</strong></span><span class="sxs-lookup"><span data-stu-id="2a974-146"><strong>RoundTripMax</strong></span></span></p></td>
<td><p><span data-ttu-id="2a974-147">int</span><span class="sxs-lookup"><span data-stu-id="2a974-147">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2a974-p107">Максимальное время (в миллисекундах), необходимое для перемещения пакета Real-Time Transport Protocol в другую конечную точку и его возврата. Приемлемым считается время двусторонней передачи, равное 200 мс (или менее).</span><span class="sxs-lookup"><span data-stu-id="2a974-p107">Maximum amount of (in milliseconds) required for a Real-Time Transport Protocol packet to travel to another endpoint and then back. Round-trip times of 200 milliseconds or less are considered of acceptable quality.</span></span></p>
<p><span data-ttu-id="2a974-p108">Высокие значения времени двусторонней передачи могут быть обусловлены международной маршрутизацией вызовов, неправильной конфигурацией маршрутизации или перегрузкой сервера-посредника. Длительное время двусторонней передачи приводит к возникновению проблем при двусторонних аудиоразговорах в режиме реального времени.</span><span class="sxs-lookup"><span data-stu-id="2a974-p108">High round-trip values can be caused by international call routing; a routing misconfiguration; or an overloaded media server. High round-trip times result in difficulties with two-way, real-time audio conversations.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a974-152"><strong>паккетлоссрате</strong></span><span class="sxs-lookup"><span data-stu-id="2a974-152"><strong>PacketLossRate</strong></span></span></p></td>
<td><p><span data-ttu-id="2a974-153">float</span><span class="sxs-lookup"><span data-stu-id="2a974-153">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2a974-p109">Средняя частота потери пакетов RTP. (Потеря пакетов происходит, когда пакеты RTP (Real-Time Transport Protocol — протокол, используемый для передачи аудио- и видеопакетов через Интернет) не достигают места назначения.) Высокие показатели потерь обычно вызваны перегрузкой, недостаточной полосой пропускания, помехами или перегрузкой беспроводной сети, а также перегрузкой сервера-посредника. Потеря пакетов обычно приводит к искажению звука или потере аудиосигналов.</span><span class="sxs-lookup"><span data-stu-id="2a974-p109">Average rate of Real-Time Transport Protocol (RTP) packet loss. (Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion; lack of bandwidth; wireless congestion or interference; or an overloaded media server. Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a974-157"><strong>паккетлоссратемакс</strong></span><span class="sxs-lookup"><span data-stu-id="2a974-157"><strong>PacketLossRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="2a974-158">float</span><span class="sxs-lookup"><span data-stu-id="2a974-158">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2a974-p110">Максимальная частота потери пакетов RTP. (Потеря пакетов происходит, когда пакеты RTP (Real-Time Transport Protocol — протокол, используемый для передачи аудио- и видеопакетов через Интернет) не достигают места назначения.) Высокие показатели потерь обычно вызваны перегрузкой, недостаточной полосой пропускания, помехами или перегрузкой беспроводной сети, а также перегрузкой сервера-посредника. Потеря пакетов обычно приводит к искажению звука или потере аудиосигналов.</span><span class="sxs-lookup"><span data-stu-id="2a974-p110">Maximum rate of Real-Time Transport Protocol (RTP) packet loss. (Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion; lack of bandwidth; wireless congestion or interference; or an overloaded media server. Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a974-162"><strong>паккетутилизатион</strong></span><span class="sxs-lookup"><span data-stu-id="2a974-162"><strong>PacketUtilization</strong></span></span></p></td>
<td><p><span data-ttu-id="2a974-163">int</span><span class="sxs-lookup"><span data-stu-id="2a974-163">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2a974-164">Количество отправленных пакетов.</span><span class="sxs-lookup"><span data-stu-id="2a974-164">Number of packets sent.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a974-165"><strong>Самый полоса пропускания</strong></span><span class="sxs-lookup"><span data-stu-id="2a974-165"><strong>BandwidthEst</strong></span></span></p></td>
<td><p><span data-ttu-id="2a974-166">int</span><span class="sxs-lookup"><span data-stu-id="2a974-166">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2a974-p111">Предполагаемая полоса пропускания для односторонней передачи, доступная в конце сеанса. Измеряется в битах в секунду.</span><span class="sxs-lookup"><span data-stu-id="2a974-p111">Estimated one-way bandwidth available at the end of the session. Reported in bits per second.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a974-169"><strong>аппшарингпайлоаддескриптион</strong></span><span class="sxs-lookup"><span data-stu-id="2a974-169"><strong>AppSharingPayloadDescription</strong></span></span></p></td>
<td><p><span data-ttu-id="2a974-170">int</span><span class="sxs-lookup"><span data-stu-id="2a974-170">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2a974-171">Описание загрузки общего доступа к приложениям.</span><span class="sxs-lookup"><span data-stu-id="2a974-171">Description of the application sharing payload.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a974-172"><strong>релативеоневайтотал</strong></span><span class="sxs-lookup"><span data-stu-id="2a974-172"><strong>RelativeOneWayTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="2a974-173">float</span><span class="sxs-lookup"><span data-stu-id="2a974-173">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2a974-p112">Общая величина односторонней задержки. Относительная односторонняя задержка измеряет задержку между клиентом и сервером.</span><span class="sxs-lookup"><span data-stu-id="2a974-p112">Total amount of one-way latency. Relative one-way latency measures the delay between the client and the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a974-176"><strong>релативеоневайавераже</strong></span><span class="sxs-lookup"><span data-stu-id="2a974-176"><strong>RelativeOneWayAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="2a974-177">float</span><span class="sxs-lookup"><span data-stu-id="2a974-177">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2a974-p113">Средняя величина односторонней задержки. Относительная односторонняя задержка измеряет задержку между клиентом и сервером</span><span class="sxs-lookup"><span data-stu-id="2a974-p113">Average amount of one-way latency. Relative one-way latency measures the delay between the client and the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a974-180"><strong>релативеоневаймакс</strong></span><span class="sxs-lookup"><span data-stu-id="2a974-180"><strong>RelativeOneWayMax</strong></span></span></p></td>
<td><p><span data-ttu-id="2a974-181">float</span><span class="sxs-lookup"><span data-stu-id="2a974-181">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2a974-p114">Максимальная величина односторонней задержки. Относительная односторонняя задержка измеряет задержку между клиентом и сервером</span><span class="sxs-lookup"><span data-stu-id="2a974-p114">Maximum amount of one-way latency. Relative one-way latency measures the delay between the client and the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a974-184"><strong>релативеоневайбурстоккурренцес</strong></span><span class="sxs-lookup"><span data-stu-id="2a974-184"><strong>RelativeOneWayBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="2a974-185">int</span><span class="sxs-lookup"><span data-stu-id="2a974-185">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2a974-p115">Общее число повторов пакетов в одну сторону. "Пакетная" передача представляет собой передачу, при которой данные передаются посредством случайных пакетов, а не в виде устойчивого потока. С помощью этой метрики измеряется поток данных между клиентом и сервером.</span><span class="sxs-lookup"><span data-stu-id="2a974-p115">Total one-way burst occurrences. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream. This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a974-189"><strong>релативеоневайбурстденсити</strong></span><span class="sxs-lookup"><span data-stu-id="2a974-189"><strong>RelativeOneWayBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="2a974-190">float</span><span class="sxs-lookup"><span data-stu-id="2a974-190">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2a974-p116">Общая плотность пакетов в одну сторону. "Пакетная" передача представляет собой передачу, при которой данные передаются посредством случайных пакетов, а не в виде устойчивого потока. С помощью этой метрики измеряется поток данных между клиентом и сервером.</span><span class="sxs-lookup"><span data-stu-id="2a974-p116">Total one-way burst density. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream. This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a974-194"><strong>релативеоневайбурстдуратион</strong></span><span class="sxs-lookup"><span data-stu-id="2a974-194"><strong>RelativeOneWayBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="2a974-195">float</span><span class="sxs-lookup"><span data-stu-id="2a974-195">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2a974-p117">Общая длительность пакетов в одну сторону. "Пакетная" передача представляет собой передачу, при которой данные передаются посредством случайных пакетов, а не в виде устойчивого потока. С помощью этой метрики измеряется поток данных между клиентом и сервером.</span><span class="sxs-lookup"><span data-stu-id="2a974-p117">Total one-way burst duration. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream. This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a974-199"><strong>релативеоневайгапоккурренцес</strong></span><span class="sxs-lookup"><span data-stu-id="2a974-199"><strong>RelativeOneWayGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="2a974-200">int</span><span class="sxs-lookup"><span data-stu-id="2a974-200">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2a974-p118">Общее число повторов разрывов в одну сторону. "Пакетная" передача представляет собой передачу, при которой данные передаются посредством случайных пакетов, а не в виде устойчивого потока; разрывы указывают задержку между этими пакетами. С помощью данной метрики измеряется поток данных между клиентом и сервером.</span><span class="sxs-lookup"><span data-stu-id="2a974-p118">Total one-way gap occurrences. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts. This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a974-204"><strong>релативеоневайгапденсити</strong></span><span class="sxs-lookup"><span data-stu-id="2a974-204"><strong>RelativeOneWayGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="2a974-205">float</span><span class="sxs-lookup"><span data-stu-id="2a974-205">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2a974-p119">Общая плотность разрывов в одну сторону. "Пакетная" передача представляет собой передачу, при которой данные передаются посредством случайных пакетов, а не в виде устойчивого потока; разрывы указывают задержку между этими пакетами. С помощью данной метрики измеряется поток данных между клиентом и сервером.</span><span class="sxs-lookup"><span data-stu-id="2a974-p119">Total one-way gap density. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts. This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a974-209"><strong>релативеоневайгапдуратион</strong></span><span class="sxs-lookup"><span data-stu-id="2a974-209"><strong>RelativeOneWayGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="2a974-210">float</span><span class="sxs-lookup"><span data-stu-id="2a974-210">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2a974-p120">Общая длительность разрывов в одну сторону. "Пакетная" передача представляет собой передачу, при которой данные передаются посредством случайных пакетов, а не в виде устойчивого потока; разрывы указывают задержку между этими пакетами. С помощью данной метрики измеряется поток данных между клиентом и сервером.</span><span class="sxs-lookup"><span data-stu-id="2a974-p120">Total one-way gap duration. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts. This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a974-214"><strong>аппликатионшарингтипе</strong></span><span class="sxs-lookup"><span data-stu-id="2a974-214"><strong>ApplicationSharingType</strong></span></span></p></td>
<td><p><span data-ttu-id="2a974-215">varChar (256)</span><span class="sxs-lookup"><span data-stu-id="2a974-215">varChar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2a974-216">Роль приложения (средство предоставления доступа и средство просмотра) и тип содержимого.</span><span class="sxs-lookup"><span data-stu-id="2a974-216">Application role (Sharer or Viewer) and content type.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a974-217"><strong>рдптилепроцессинглатенцитотал</strong></span><span class="sxs-lookup"><span data-stu-id="2a974-217"><strong>RDPTileProcessingLatencyTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="2a974-218">float</span><span class="sxs-lookup"><span data-stu-id="2a974-218">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2a974-p121">Общее время обработки заголовков RDP. Чем больше общее значение, тем длиннее задержки при просмотре.</span><span class="sxs-lookup"><span data-stu-id="2a974-p121">Total processing time for remote desktop protocol (RDP) tiles. A higher total equates to a longer delay in the viewing experience.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a974-221"><strong>рдптилепроцессинглатенциавераже</strong></span><span class="sxs-lookup"><span data-stu-id="2a974-221"><strong>RDPTileProcessingLatencyAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="2a974-222">float</span><span class="sxs-lookup"><span data-stu-id="2a974-222">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2a974-p122">Среднее время обработки заголовков RDP. Чем больше общее значение, тем длиннее задержки при просмотре.</span><span class="sxs-lookup"><span data-stu-id="2a974-p122">Average processing time for remote desktop protocol (RDP) tiles. A higher total equates to a longer delay in the viewing experience.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a974-225"><strong>рдптилепроцессинглатенцимакс</strong></span><span class="sxs-lookup"><span data-stu-id="2a974-225"><strong>RDPTileProcessingLatencyMax</strong></span></span></p></td>
<td><p><span data-ttu-id="2a974-226">float</span><span class="sxs-lookup"><span data-stu-id="2a974-226">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2a974-p123">Максимальное время обработки заголовков RDP. Чем больше общее значение, тем длиннее задержки при просмотре.</span><span class="sxs-lookup"><span data-stu-id="2a974-p123">Maximum processing time for remote desktop protocol (RDP) tiles. A higher total equates to a longer delay in the viewing experience.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a974-229"><strong>рдптилепроцессинглатенцибурстоккурренцес</strong></span><span class="sxs-lookup"><span data-stu-id="2a974-229"><strong>RDPTileProcessingLatencyBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="2a974-230">int</span><span class="sxs-lookup"><span data-stu-id="2a974-230">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2a974-p124">Повторы пакетов во время обработки заголовков RDP. Передача с повторами пакетов — это передача, при которой данные передаются случайными пакетами, а не равномерным потоком.</span><span class="sxs-lookup"><span data-stu-id="2a974-p124">Burst occurrences in the processing time for remote desktop protocol (RDP) tiles. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a974-233"><strong>рдптилепроцессинглатенцибурстденсити</strong></span><span class="sxs-lookup"><span data-stu-id="2a974-233"><strong>RDPTileProcessingLatencyBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="2a974-234">float</span><span class="sxs-lookup"><span data-stu-id="2a974-234">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2a974-p125">Плотность пакетов во время обработки заголовков RDP. Передача с повторами пакетов — это передача, при которой данные передаются случайными пакетами, а не равномерным потоком.</span><span class="sxs-lookup"><span data-stu-id="2a974-p125">Burst density in the processing time for remote desktop protocol (RDP) tiles. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a974-237"><strong>рдптилепроцессинглатенцибурстдуратион</strong></span><span class="sxs-lookup"><span data-stu-id="2a974-237"><strong>RDPTileProcessingLatencyBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="2a974-238">float</span><span class="sxs-lookup"><span data-stu-id="2a974-238">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2a974-p126">Продолжительность пакетной передачи во время обработки заголовков RDP. Передача с повторами пакетов — это передача, при которой данные передаются случайными пакетами, а не равномерным потоком.</span><span class="sxs-lookup"><span data-stu-id="2a974-p126">Burst duration in the processing time for remote desktop protocol (RDP) tiles. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a974-241"><strong>рдптилепроцессинглатенцигапоккурренцес</strong></span><span class="sxs-lookup"><span data-stu-id="2a974-241"><strong>RDPTileProcessingLatencyGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="2a974-242">int</span><span class="sxs-lookup"><span data-stu-id="2a974-242">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2a974-243">Разрывы во время обработки заголовков RDP.</span><span class="sxs-lookup"><span data-stu-id="2a974-243">Gap occurrences in the processing time for remote desktop protocol (RDP) tiles.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a974-244"><strong>рдптилепроцессинглатенцигапденсити</strong></span><span class="sxs-lookup"><span data-stu-id="2a974-244"><strong>RDPTileProcessingLatencyGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="2a974-245">float</span><span class="sxs-lookup"><span data-stu-id="2a974-245">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2a974-p127">Плотность разрывов во время обработки заголовков RDP. Чем ниже плотность разрывов, тем лучше просмотр.</span><span class="sxs-lookup"><span data-stu-id="2a974-p127">Gap density in the processing time for remote desktop protocol (RDP) tiles. Low gap density equates to a better viewing experience.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a974-248"><strong>рдптилепроцессинглатенцигапдуратион</strong></span><span class="sxs-lookup"><span data-stu-id="2a974-248"><strong>RDPTileProcessingLatencyGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="2a974-249">float</span><span class="sxs-lookup"><span data-stu-id="2a974-249">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2a974-p128">Продолжительность разрывов во время обработки заголовков RDP. Чем ниже продолжительность разрывов, тем лучше просмотр.</span><span class="sxs-lookup"><span data-stu-id="2a974-p128">Gap duration in the processing time for remote desktop protocol (RDP) tiles. Short gap durations equate to a better viewing experience.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a974-252"><strong>каптуретилератетотал</strong></span><span class="sxs-lookup"><span data-stu-id="2a974-252"><strong>CaptureTileRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="2a974-253">float</span><span class="sxs-lookup"><span data-stu-id="2a974-253">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2a974-254">Общая частота захвата заголовков (заголовков в секунду).</span><span class="sxs-lookup"><span data-stu-id="2a974-254">Total rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a974-255"><strong>каптуретилератеавераже</strong></span><span class="sxs-lookup"><span data-stu-id="2a974-255"><strong>CaptureTileRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="2a974-256">float</span><span class="sxs-lookup"><span data-stu-id="2a974-256">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2a974-257">Средняя частота захвата заголовков (заголовков в секунду).</span><span class="sxs-lookup"><span data-stu-id="2a974-257">Average rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a974-258"><strong>каптуретилератемакс</strong></span><span class="sxs-lookup"><span data-stu-id="2a974-258"><strong>CaptureTileRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="2a974-259">float</span><span class="sxs-lookup"><span data-stu-id="2a974-259">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2a974-260">Максимальная частота захвата заголовков (заголовков в секунду).</span><span class="sxs-lookup"><span data-stu-id="2a974-260">Maximum rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a974-261"><strong>каптуретилератебурстоккурренцес</strong></span><span class="sxs-lookup"><span data-stu-id="2a974-261"><strong>CaptureTileRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="2a974-262">целое</span><span class="sxs-lookup"><span data-stu-id="2a974-262">in t</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2a974-263">Повторы пакетов в частоте захвата заголовков (заголовков в секунду).</span><span class="sxs-lookup"><span data-stu-id="2a974-263">Burst occurrences in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a974-264"><strong>каптуретилератебурстденсити</strong></span><span class="sxs-lookup"><span data-stu-id="2a974-264"><strong>CaptureTileRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="2a974-265">float</span><span class="sxs-lookup"><span data-stu-id="2a974-265">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2a974-266">Плотность повторов пакетов в частоте захвата заголовков (заголовков в секунду).</span><span class="sxs-lookup"><span data-stu-id="2a974-266">Burst density in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a974-267"><strong>каптуретилератебурстдуратион</strong></span><span class="sxs-lookup"><span data-stu-id="2a974-267"><strong>CaptureTileRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="2a974-268">float</span><span class="sxs-lookup"><span data-stu-id="2a974-268">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2a974-269">Продолжительность повторов пакетов в частоте захвата заголовков (заголовков в секунду).</span><span class="sxs-lookup"><span data-stu-id="2a974-269">Burst duration in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a974-270"><strong>каптуретилератегапоккурренцес</strong></span><span class="sxs-lookup"><span data-stu-id="2a974-270"><strong>CaptureTileRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="2a974-271">int</span><span class="sxs-lookup"><span data-stu-id="2a974-271">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2a974-272">Разрывы в частоте захвата заголовков (заголовков в секунду).</span><span class="sxs-lookup"><span data-stu-id="2a974-272">Gap occurrences in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a974-273"><strong>каптуретилератегапденсити</strong></span><span class="sxs-lookup"><span data-stu-id="2a974-273"><strong>CaptureTileRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="2a974-274">float</span><span class="sxs-lookup"><span data-stu-id="2a974-274">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2a974-275">Плотность разрывов в частоте захвата заголовков (заголовков в секунду).</span><span class="sxs-lookup"><span data-stu-id="2a974-275">Gap density in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a974-276"><strong>каптуретилератегапдуратион</strong></span><span class="sxs-lookup"><span data-stu-id="2a974-276"><strong>CaptureTileRateGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="2a974-277">float</span><span class="sxs-lookup"><span data-stu-id="2a974-277">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2a974-278">Продолжительность разрывов в частоте захвата заголовков (заголовков в секунду).</span><span class="sxs-lookup"><span data-stu-id="2a974-278">Gap duration in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a974-279"><strong>споиледтилеперценттотал</strong></span><span class="sxs-lookup"><span data-stu-id="2a974-279"><strong>SpoiledTilePercentTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="2a974-280">float</span><span class="sxs-lookup"><span data-stu-id="2a974-280">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2a974-281">Общее процентное соотношение контента, не достигшего средства просмотра и отброшенного или перезаписанного новым контентом.</span><span class="sxs-lookup"><span data-stu-id="2a974-281">Total percentage of the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a974-282"><strong>споиледтилеперцентавераже</strong></span><span class="sxs-lookup"><span data-stu-id="2a974-282"><strong>SpoiledTilePercentAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="2a974-283">float</span><span class="sxs-lookup"><span data-stu-id="2a974-283">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2a974-284">Среднее процентное соотношение контента, не достигшего средства просмотра и отброшенного или перезаписанного новым контентом.</span><span class="sxs-lookup"><span data-stu-id="2a974-284">Average percentage of the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a974-285"><strong>споиледтилеперцентмакс</strong></span><span class="sxs-lookup"><span data-stu-id="2a974-285"><strong>SpoiledTilePercentMax</strong></span></span></p></td>
<td><p><span data-ttu-id="2a974-286">float</span><span class="sxs-lookup"><span data-stu-id="2a974-286">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2a974-287">Максимальное процентное соотношение контента, не достигшего средства просмотра и отброшенного или перезаписанного новым контентом.</span><span class="sxs-lookup"><span data-stu-id="2a974-287">Maximum percentage of the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a974-288"><strong>споиледтилеперцентбурстоккурренцес</strong></span><span class="sxs-lookup"><span data-stu-id="2a974-288"><strong>SpoiledTilePercentBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="2a974-289">int</span><span class="sxs-lookup"><span data-stu-id="2a974-289">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2a974-290">Повторы пакетов контента, не достигшего средства просмотра и отброшенного или перезаписанного новым контентом.</span><span class="sxs-lookup"><span data-stu-id="2a974-290">Burst occurrences for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a974-291"><strong>споиледтилеперцентбурстденсити</strong></span><span class="sxs-lookup"><span data-stu-id="2a974-291"><strong>SpoiledTilePercentBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="2a974-292">float</span><span class="sxs-lookup"><span data-stu-id="2a974-292">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2a974-293">Плотность повторов пакетов контента, не достигшего средства просмотра и отброшенного или перезаписанного новым контентом.</span><span class="sxs-lookup"><span data-stu-id="2a974-293">Burst density for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a974-294"><strong>споиледтилеперцентбурстдуратион</strong></span><span class="sxs-lookup"><span data-stu-id="2a974-294"><strong>SpoiledTilePercentBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="2a974-295">float</span><span class="sxs-lookup"><span data-stu-id="2a974-295">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2a974-296">Продолжительность повторов пакетов контента, не достигшего средства просмотра и отброшенного или перезаписанного новым контентом.</span><span class="sxs-lookup"><span data-stu-id="2a974-296">Burst duration for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a974-297"><strong>споиледтилеперцентгапоккурренцес</strong></span><span class="sxs-lookup"><span data-stu-id="2a974-297"><strong>SpoiledTilePercentGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="2a974-298">int</span><span class="sxs-lookup"><span data-stu-id="2a974-298">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2a974-299">Разрывы контента, не достигшего средства просмотра и отброшенного или перезаписанного новым контентом.</span><span class="sxs-lookup"><span data-stu-id="2a974-299">Gap occurrences for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a974-300"><strong>споиледтилеперцентгапденсити</strong></span><span class="sxs-lookup"><span data-stu-id="2a974-300"><strong>SpoiledTilePercentGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="2a974-301">float</span><span class="sxs-lookup"><span data-stu-id="2a974-301">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2a974-302">Плотность разрывов контента, не достигшего средства просмотра и отброшенного или перезаписанного новым контентом.</span><span class="sxs-lookup"><span data-stu-id="2a974-302">Gap density for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a974-303"><strong>споиледтилеперцентгапдуратион</strong></span><span class="sxs-lookup"><span data-stu-id="2a974-303"><strong>SpoiledTilePercentGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="2a974-304">float</span><span class="sxs-lookup"><span data-stu-id="2a974-304">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2a974-305">Продолжительность разрывов контента, не достигшего средства просмотра и отброшенного или перезаписанного новым контентом.</span><span class="sxs-lookup"><span data-stu-id="2a974-305">Gap duration for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a974-306"><strong>скрапингфрамератетотал</strong></span><span class="sxs-lookup"><span data-stu-id="2a974-306"><strong>ScrapingFrameRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="2a974-307">float</span><span class="sxs-lookup"><span data-stu-id="2a974-307">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2a974-308">Общее количество кадров, исключенных из источника графики.</span><span class="sxs-lookup"><span data-stu-id="2a974-308">Total number of frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a974-309"><strong>скрапингфрамератеавераже</strong></span><span class="sxs-lookup"><span data-stu-id="2a974-309"><strong>ScrapingFrameRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="2a974-310">float</span><span class="sxs-lookup"><span data-stu-id="2a974-310">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2a974-311">Среднее количество кадров, исключенных из источника графики.</span><span class="sxs-lookup"><span data-stu-id="2a974-311">Average number of frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a974-312"><strong>скрапингфрамератемакс</strong></span><span class="sxs-lookup"><span data-stu-id="2a974-312"><strong>ScrapingFrameRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="2a974-313">float</span><span class="sxs-lookup"><span data-stu-id="2a974-313">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2a974-314">Максимальное количество кадров, исключенных из источника графики.</span><span class="sxs-lookup"><span data-stu-id="2a974-314">Maximum number of frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a974-315"><strong>скрапингфрамератебурстоккурренцес</strong></span><span class="sxs-lookup"><span data-stu-id="2a974-315"><strong>ScrapingFrameRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="2a974-316">int</span><span class="sxs-lookup"><span data-stu-id="2a974-316">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2a974-317">Повторы пакетов в кадрах, исключенных из источника графики.</span><span class="sxs-lookup"><span data-stu-id="2a974-317">Burst occurrences in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a974-318"><strong>скрапингфрамератебурстденсити</strong></span><span class="sxs-lookup"><span data-stu-id="2a974-318"><strong>ScrapingFrameRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="2a974-319">float</span><span class="sxs-lookup"><span data-stu-id="2a974-319">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2a974-320">Плотность повторов пакетов в кадрах, исключенных из источника графики.</span><span class="sxs-lookup"><span data-stu-id="2a974-320">Burst density in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a974-321"><strong>скрапингфрамератебурстдуратион</strong></span><span class="sxs-lookup"><span data-stu-id="2a974-321"><strong>ScrapingFrameRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="2a974-322">float</span><span class="sxs-lookup"><span data-stu-id="2a974-322">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2a974-323">Продолжительность повторов пакетов в кадрах, исключенных из источника графики.</span><span class="sxs-lookup"><span data-stu-id="2a974-323">Burst duration in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a974-324"><strong>скрапингфрамератегапоккурренцес</strong></span><span class="sxs-lookup"><span data-stu-id="2a974-324"><strong>ScrapingFrameRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="2a974-325">int</span><span class="sxs-lookup"><span data-stu-id="2a974-325">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2a974-326">Разрывы в кадрах, исключенных из источника графики.</span><span class="sxs-lookup"><span data-stu-id="2a974-326">Gap occurrences in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a974-327"><strong>скрапингфрамератегапденсити</strong></span><span class="sxs-lookup"><span data-stu-id="2a974-327"><strong>ScrapingFrameRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="2a974-328">float</span><span class="sxs-lookup"><span data-stu-id="2a974-328">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2a974-329">Плотность разрывов в кадрах, исключенных из источника графики.</span><span class="sxs-lookup"><span data-stu-id="2a974-329">Gap density in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a974-330"><strong>скрапингфрамератегапдуратион</strong></span><span class="sxs-lookup"><span data-stu-id="2a974-330"><strong>ScrapingFrameRateGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="2a974-331">float</span><span class="sxs-lookup"><span data-stu-id="2a974-331">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2a974-332">Продолжительность разрывов в кадрах, исключенных из источника графики.</span><span class="sxs-lookup"><span data-stu-id="2a974-332">Gap duration in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a974-333"><strong>инкомингтилератетотал</strong></span><span class="sxs-lookup"><span data-stu-id="2a974-333"><strong>IncomingTileRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="2a974-334">float</span><span class="sxs-lookup"><span data-stu-id="2a974-334">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2a974-335">Общая частота кадров, получаемых средством просмотра.</span><span class="sxs-lookup"><span data-stu-id="2a974-335">Total incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a974-336"><strong>инкомингтилератеавераже</strong></span><span class="sxs-lookup"><span data-stu-id="2a974-336"><strong>IncomingTileRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="2a974-337">float</span><span class="sxs-lookup"><span data-stu-id="2a974-337">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2a974-338">Средняя частота кадров, получаемых средством просмотра.</span><span class="sxs-lookup"><span data-stu-id="2a974-338">Average incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a974-339"><strong>инкомингтилератемакс</strong></span><span class="sxs-lookup"><span data-stu-id="2a974-339"><strong>IncomingTileRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="2a974-340">float</span><span class="sxs-lookup"><span data-stu-id="2a974-340">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2a974-341">Максимальная частота заголовков, получаемых средством просмотра.</span><span class="sxs-lookup"><span data-stu-id="2a974-341">Maximum incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a974-342"><strong>инкомингтилератебурстоккурренцес</strong></span><span class="sxs-lookup"><span data-stu-id="2a974-342"><strong>IncomingTileRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="2a974-343">int</span><span class="sxs-lookup"><span data-stu-id="2a974-343">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2a974-344">Повторы пакетов относительно частоты входящих заголовков, получаемых средством просмотра.</span><span class="sxs-lookup"><span data-stu-id="2a974-344">Burst occurrences in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a974-345"><strong>инкомингтилератебурстденсити</strong></span><span class="sxs-lookup"><span data-stu-id="2a974-345"><strong>IncomingTileRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="2a974-346">float</span><span class="sxs-lookup"><span data-stu-id="2a974-346">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2a974-347">Плотность повторов пакетов относительно частоты входящих заголовков, получаемых средством просмотра.</span><span class="sxs-lookup"><span data-stu-id="2a974-347">Burst density in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a974-348"><strong>инкомингтилератебурстдуратион</strong></span><span class="sxs-lookup"><span data-stu-id="2a974-348"><strong>IncomingTileRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="2a974-349">float</span><span class="sxs-lookup"><span data-stu-id="2a974-349">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2a974-350">Продолжительность повторов пакетов относительно частоты входящих заголовков, получаемых средством просмотра.</span><span class="sxs-lookup"><span data-stu-id="2a974-350">Burst duration in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a974-351"><strong>инкомингтилератегапоккурренцес</strong></span><span class="sxs-lookup"><span data-stu-id="2a974-351"><strong>IncomingTileRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="2a974-352">int</span><span class="sxs-lookup"><span data-stu-id="2a974-352">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2a974-353">Разрывы относительно частоты входящих заголовков, получаемых средством просмотра.</span><span class="sxs-lookup"><span data-stu-id="2a974-353">Gap occurrences in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a974-354"><strong>инкомингтилератегапденсити</strong></span><span class="sxs-lookup"><span data-stu-id="2a974-354"><strong>IncomingTileRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="2a974-355">float</span><span class="sxs-lookup"><span data-stu-id="2a974-355">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2a974-356">Плотность разрывов относительно частоты входящих заголовков, получаемых средством просмотра.</span><span class="sxs-lookup"><span data-stu-id="2a974-356">Gap density in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a974-357"><strong>инкомингтилератегапдуратион</strong></span><span class="sxs-lookup"><span data-stu-id="2a974-357"><strong>IncomingTileRateGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="2a974-358">float</span><span class="sxs-lookup"><span data-stu-id="2a974-358">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2a974-359">Продолжительность разрывов относительно частоты входящих заголовков, получаемых средством просмотра.</span><span class="sxs-lookup"><span data-stu-id="2a974-359">Gap duration in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a974-360"><strong>инкомингфрамератетотал</strong></span><span class="sxs-lookup"><span data-stu-id="2a974-360"><strong>IncomingFrameRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="2a974-361">float</span><span class="sxs-lookup"><span data-stu-id="2a974-361">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2a974-362">Общая частота кадров, получаемых средством просмотра.</span><span class="sxs-lookup"><span data-stu-id="2a974-362">Total incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a974-363"><strong>инкомингфрамератеавераже</strong></span><span class="sxs-lookup"><span data-stu-id="2a974-363"><strong>IncomingFrameRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="2a974-364">float</span><span class="sxs-lookup"><span data-stu-id="2a974-364">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2a974-365">Средняя частота кадров, получаемых средством просмотра.</span><span class="sxs-lookup"><span data-stu-id="2a974-365">Average incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a974-366"><strong>инкомингфрамератемакс</strong></span><span class="sxs-lookup"><span data-stu-id="2a974-366"><strong>IncomingFrameRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="2a974-367">float</span><span class="sxs-lookup"><span data-stu-id="2a974-367">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2a974-368">Максимальная входящая частота кадров, получаемых средством просмотра.</span><span class="sxs-lookup"><span data-stu-id="2a974-368">Maximum incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a974-369"><strong>инкомингфрамератебурстоккурренцес</strong></span><span class="sxs-lookup"><span data-stu-id="2a974-369"><strong>IncomingFrameRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="2a974-370">int</span><span class="sxs-lookup"><span data-stu-id="2a974-370">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2a974-371">Повторы пакетов относительно частоты входящих кадров, получаемых средством просмотра.</span><span class="sxs-lookup"><span data-stu-id="2a974-371">Burst occurrences in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a974-372"><strong>инкомингфрамератебурстденсити</strong></span><span class="sxs-lookup"><span data-stu-id="2a974-372"><strong>IncomingFrameRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="2a974-373">float</span><span class="sxs-lookup"><span data-stu-id="2a974-373">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2a974-374">Плотность повторов пакетов относительно частоты входящих кадров, получаемых средством просмотра.</span><span class="sxs-lookup"><span data-stu-id="2a974-374">Burst density in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a974-375"><strong>инкомингфрамератебурстдуратион</strong></span><span class="sxs-lookup"><span data-stu-id="2a974-375"><strong>IncomingFrameRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="2a974-376">float</span><span class="sxs-lookup"><span data-stu-id="2a974-376">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2a974-377">Продолжительность повторов пакетов относительно частоты входящих кадров, получаемых средством просмотра.</span><span class="sxs-lookup"><span data-stu-id="2a974-377">Burst duration in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a974-378"><strong>инкомингфрамератегапоккурренцес</strong></span><span class="sxs-lookup"><span data-stu-id="2a974-378"><strong>IncomingFrameRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="2a974-379">int</span><span class="sxs-lookup"><span data-stu-id="2a974-379">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2a974-380">Разрывы относительно частоты входящих кадров, получаемых средством просмотра.</span><span class="sxs-lookup"><span data-stu-id="2a974-380">Gap occurrences in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a974-381"><strong>инкомингфрамератегапденсити</strong></span><span class="sxs-lookup"><span data-stu-id="2a974-381"><strong>IncomingFrameRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="2a974-382">float</span><span class="sxs-lookup"><span data-stu-id="2a974-382">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2a974-383">Плотность разрывов относительно частоты входящих кадров, получаемых средством просмотра.</span><span class="sxs-lookup"><span data-stu-id="2a974-383">Gap density in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a974-384"><strong>инкомингфрамератедуратион</strong></span><span class="sxs-lookup"><span data-stu-id="2a974-384"><strong>IncomingFrameRateDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="2a974-385">float</span><span class="sxs-lookup"><span data-stu-id="2a974-385">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2a974-386">Продолжительность разрывов относительно частоты входящих кадров, получаемых средством просмотра.</span><span class="sxs-lookup"><span data-stu-id="2a974-386">Gap duration in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a974-387"><strong>аутгоингтилератетотал</strong></span><span class="sxs-lookup"><span data-stu-id="2a974-387"><strong>OutgoingTileRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="2a974-388">float</span><span class="sxs-lookup"><span data-stu-id="2a974-388">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2a974-389">Общая частота исходящих заголовков для отправителя.</span><span class="sxs-lookup"><span data-stu-id="2a974-389">Total outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a974-390"><strong>аутгоингтилератеавераже</strong></span><span class="sxs-lookup"><span data-stu-id="2a974-390"><strong>OutgoingTileRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="2a974-391">float</span><span class="sxs-lookup"><span data-stu-id="2a974-391">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2a974-392">Средняя частота исходящих заголовков для отправителя.</span><span class="sxs-lookup"><span data-stu-id="2a974-392">Average outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a974-393"><strong>аутгоингтилератемакс</strong></span><span class="sxs-lookup"><span data-stu-id="2a974-393"><strong>OutgoingTileRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="2a974-394">float</span><span class="sxs-lookup"><span data-stu-id="2a974-394">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2a974-395">Максимальная частота исходящих заголовков для отправителя.</span><span class="sxs-lookup"><span data-stu-id="2a974-395">Maximum outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a974-396"><strong>аутгоингтилератебурстоккурренцес</strong></span><span class="sxs-lookup"><span data-stu-id="2a974-396"><strong>OutgoingTileRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="2a974-397">int</span><span class="sxs-lookup"><span data-stu-id="2a974-397">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2a974-398">Повторы пакетов относительно частоты исходящих заголовков для отправителя.</span><span class="sxs-lookup"><span data-stu-id="2a974-398">Burst occurrences in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a974-399"><strong>аутгоингтилератебурстденсити</strong></span><span class="sxs-lookup"><span data-stu-id="2a974-399"><strong>OutgoingTileRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="2a974-400">float</span><span class="sxs-lookup"><span data-stu-id="2a974-400">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2a974-401">Плотность повторов пакетов относительно частоты исходящих заголовков для отправителя.</span><span class="sxs-lookup"><span data-stu-id="2a974-401">Burst density in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a974-402"><strong>аутгоингтилератебурстдуратион</strong></span><span class="sxs-lookup"><span data-stu-id="2a974-402"><strong>OutgoingTileRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="2a974-403">float</span><span class="sxs-lookup"><span data-stu-id="2a974-403">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2a974-404">Продолжительность повторов пакетов относительно частоты исходящих заголовков для отправителя.</span><span class="sxs-lookup"><span data-stu-id="2a974-404">Burst duration in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a974-405"><strong>аутгоингтилератегапоккурренцес</strong></span><span class="sxs-lookup"><span data-stu-id="2a974-405"><strong>OutgoingTileRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="2a974-406">int</span><span class="sxs-lookup"><span data-stu-id="2a974-406">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2a974-407">Разрывы относительно частоты исходящих заголовков для отправителя.</span><span class="sxs-lookup"><span data-stu-id="2a974-407">Gap occurrences in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a974-408"><strong>аутгоингтилератегапденсити</strong></span><span class="sxs-lookup"><span data-stu-id="2a974-408"><strong>OutgoingTileRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="2a974-409">float</span><span class="sxs-lookup"><span data-stu-id="2a974-409">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2a974-410">Плотность разрывов относительно частоты исходящих заголовков для отправителя.</span><span class="sxs-lookup"><span data-stu-id="2a974-410">Gap density in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a974-411"><strong>аутгоингтилератегапдуратион</strong></span><span class="sxs-lookup"><span data-stu-id="2a974-411"><strong>OutgoingTileRateGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="2a974-412">float</span><span class="sxs-lookup"><span data-stu-id="2a974-412">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2a974-413">Продолжительность разрывов относительно частоты исходящих заголовков для отправителя.</span><span class="sxs-lookup"><span data-stu-id="2a974-413">Gap duration in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a974-414"><strong>аутгоингфрамератетотал</strong></span><span class="sxs-lookup"><span data-stu-id="2a974-414"><strong>OutgoingFrameRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="2a974-415">float</span><span class="sxs-lookup"><span data-stu-id="2a974-415">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2a974-416">Общая частота исходящих кадров для отправителя.</span><span class="sxs-lookup"><span data-stu-id="2a974-416">Total outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a974-417"><strong>аутгоингфрамератеавераже</strong></span><span class="sxs-lookup"><span data-stu-id="2a974-417"><strong>OutgoingFrameRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="2a974-418">float</span><span class="sxs-lookup"><span data-stu-id="2a974-418">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2a974-419">Средняя частота исходящих кадров для отправителя.</span><span class="sxs-lookup"><span data-stu-id="2a974-419">average outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a974-420"><strong>аутгоингфрамератемакс</strong></span><span class="sxs-lookup"><span data-stu-id="2a974-420"><strong>OutgoingFrameRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="2a974-421">float</span><span class="sxs-lookup"><span data-stu-id="2a974-421">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2a974-422">Максимальная частота исходящих кадров для отправителя.</span><span class="sxs-lookup"><span data-stu-id="2a974-422">Maximum outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a974-423"><strong>аутгоингфрамератебурстоккурренцес</strong></span><span class="sxs-lookup"><span data-stu-id="2a974-423"><strong>OutgoingFrameRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="2a974-424">int</span><span class="sxs-lookup"><span data-stu-id="2a974-424">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2a974-425">Повторы пакетов относительно частоты исходящих кадров для отправителя.</span><span class="sxs-lookup"><span data-stu-id="2a974-425">Burst occurrences in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a974-426"><strong>аутгоингфрамератебурстденсити</strong></span><span class="sxs-lookup"><span data-stu-id="2a974-426"><strong>OutgoingFrameRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="2a974-427">float</span><span class="sxs-lookup"><span data-stu-id="2a974-427">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2a974-428">Плотность повторов пакетов относительно частоты исходящих кадров для отправителя.</span><span class="sxs-lookup"><span data-stu-id="2a974-428">Burst density in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a974-429"><strong>аутгоингфрамератебурстдуратион</strong></span><span class="sxs-lookup"><span data-stu-id="2a974-429"><strong>OutgoingFrameRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="2a974-430">float</span><span class="sxs-lookup"><span data-stu-id="2a974-430">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2a974-431">Продолжительность повторов пакетов относительно частоты исходящих кадров для отправителя.</span><span class="sxs-lookup"><span data-stu-id="2a974-431">Burst duration in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a974-432"><strong>аутгоингфрамератегапоккурренцес</strong></span><span class="sxs-lookup"><span data-stu-id="2a974-432"><strong>OutgoingFrameRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="2a974-433">int</span><span class="sxs-lookup"><span data-stu-id="2a974-433">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2a974-434">Разрывы относительно частоты исходящих кадров для отправителя.</span><span class="sxs-lookup"><span data-stu-id="2a974-434">Gap occurrences in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a974-435"><strong>аутгоингфрамератегапденсити</strong></span><span class="sxs-lookup"><span data-stu-id="2a974-435"><strong>OutgoingFrameRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="2a974-436">float</span><span class="sxs-lookup"><span data-stu-id="2a974-436">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2a974-437">Плотность разрывов относительно частоты исходящих кадров для отправителя.</span><span class="sxs-lookup"><span data-stu-id="2a974-437">Gap density in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a974-438"><strong>аутгоингфрамератегапдуратион</strong></span><span class="sxs-lookup"><span data-stu-id="2a974-438"><strong>OutgoingFrameRateGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="2a974-439">float</span><span class="sxs-lookup"><span data-stu-id="2a974-439">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2a974-440">Продолжительность разрывов относительно частоты исходящих кадров для отправителя.</span><span class="sxs-lookup"><span data-stu-id="2a974-440">Gap duration in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a974-441"><strong>аверажеректанглехеигхт</strong></span><span class="sxs-lookup"><span data-stu-id="2a974-441"><strong>AverageRectangleHeight</strong></span></span></p></td>
<td><p><span data-ttu-id="2a974-442">int</span><span class="sxs-lookup"><span data-stu-id="2a974-442">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2a974-443">Средняя высота разрешения видео в пикселах.</span><span class="sxs-lookup"><span data-stu-id="2a974-443">Average video resolution height, in pixels.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a974-444"><strong>аверажеректанглевидс</strong></span><span class="sxs-lookup"><span data-stu-id="2a974-444"><strong>AverageRectangleWidth</strong></span></span></p></td>
<td><p><span data-ttu-id="2a974-445">int</span><span class="sxs-lookup"><span data-stu-id="2a974-445">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2a974-446">Средняя ширина разрешения видео в пикселах.</span><span class="sxs-lookup"><span data-stu-id="2a974-446">Average video resolution width, in pixels.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a974-447"><strong>Получение</strong></span><span class="sxs-lookup"><span data-stu-id="2a974-447"><strong>Inbound</strong></span></span></p></td>
<td><p><span data-ttu-id="2a974-448">Битовая</span><span class="sxs-lookup"><span data-stu-id="2a974-448">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2a974-449">Средняя частота кадров (в кадрах в секунду) для передачи входящих.</span><span class="sxs-lookup"><span data-stu-id="2a974-449">Average frame rate (in frames per second) for inbound transmissions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a974-450"><strong>Прав</strong></span><span class="sxs-lookup"><span data-stu-id="2a974-450"><strong>Outbound</strong></span></span></p></td>
<td><p><span data-ttu-id="2a974-451">Битовая</span><span class="sxs-lookup"><span data-stu-id="2a974-451">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2a974-452">Средняя частота кадров (в кадрах в секунду) для передачи исходящих пакетов.</span><span class="sxs-lookup"><span data-stu-id="2a974-452">Average frame rate (in frames per second) for outbound transmissions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a974-453"><strong>сендерискаллерпаи</strong></span><span class="sxs-lookup"><span data-stu-id="2a974-453"><strong>SenderIsCallerPAI</strong></span></span></p></td>
<td><p><span data-ttu-id="2a974-454">Битовая</span><span class="sxs-lookup"><span data-stu-id="2a974-454">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2a974-455">1 означает направление потока от вызывающего абонента вызываемому абоненту.</span><span class="sxs-lookup"><span data-stu-id="2a974-455">1 means the stream direction is from the caller to callee.</span></span></p>
<p><span data-ttu-id="2a974-456">0 означает направление потока от вызываемого абонента вызывающему абоненту.</span><span class="sxs-lookup"><span data-stu-id="2a974-456">0 means the stream direction is from the callee to the caller.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

