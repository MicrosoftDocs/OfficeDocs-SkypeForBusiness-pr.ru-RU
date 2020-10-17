---
title: 'Lync Server 2013: таблица Аппшарингстреам'
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
ms.openlocfilehash: 9b729112aa0fb064a518c50212a6a041a6661be3
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48499506"
---
# <a name="appsharingstream-table-in-lync-server-2013"></a><span data-ttu-id="38071-102">Таблица Аппшарингстреам в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="38071-102">AppSharingStream table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="38071-103">_**Последнее изменение темы:** 2014-02-21_</span><span class="sxs-lookup"><span data-stu-id="38071-103">_**Topic Last Modified:** 2014-02-21_</span></span>

<span data-ttu-id="38071-104">В таблице AppSharingStream содержатся показатели качества взаимодействия для сетевых потоков, используемых для общего доступа к приложениям.</span><span class="sxs-lookup"><span data-stu-id="38071-104">The AppSharingStream table contains Quality of Experience metrics for the network streams used for application sharing.</span></span> <span data-ttu-id="38071-105">Эта таблица была введена в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="38071-105">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="38071-106"><strong>Column</strong></span><span class="sxs-lookup"><span data-stu-id="38071-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="38071-107"><strong>Тип данных</strong></span><span class="sxs-lookup"><span data-stu-id="38071-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="38071-108"><strong>Ключ или индекс</strong></span><span class="sxs-lookup"><span data-stu-id="38071-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="38071-109"><strong>Details</strong></span><span class="sxs-lookup"><span data-stu-id="38071-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="38071-110"><strong>конференцедатетиме</strong></span><span class="sxs-lookup"><span data-stu-id="38071-110"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="38071-111">dateTime</span><span class="sxs-lookup"><span data-stu-id="38071-111">dateTime</span></span></p></td>
<td><p><span data-ttu-id="38071-112">Основной, внешний</span><span class="sxs-lookup"><span data-stu-id="38071-112">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="38071-113">Дата и время начала сеанса.</span><span class="sxs-lookup"><span data-stu-id="38071-113">Date and time that the session started.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="38071-114"><strong>сессионсек</strong></span><span class="sxs-lookup"><span data-stu-id="38071-114"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="38071-115">int</span><span class="sxs-lookup"><span data-stu-id="38071-115">int</span></span></p></td>
<td><p><span data-ttu-id="38071-116">Основной, внешний</span><span class="sxs-lookup"><span data-stu-id="38071-116">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="38071-117">Порядковый идентификатор, используемый для используется для проведения различия между сеансами, которые начались в один и тот же день и в одно и то же время.</span><span class="sxs-lookup"><span data-stu-id="38071-117">Sequential identifier used to distinguish between sessions that started on the same date and at the same time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="38071-118"><strong>медиалинелабел</strong></span><span class="sxs-lookup"><span data-stu-id="38071-118"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="38071-119">tinyint</span><span class="sxs-lookup"><span data-stu-id="38071-119">tinyint</span></span></p></td>
<td><p><span data-ttu-id="38071-120">Основной, внешний</span><span class="sxs-lookup"><span data-stu-id="38071-120">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="38071-p102">Представляет тип видеоканала, используемого для звонка. Допускаются следующие значения:</span><span class="sxs-lookup"><span data-stu-id="38071-p102">Represents the type of video line used in the call. Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="38071-123">0 — звук</span><span class="sxs-lookup"><span data-stu-id="38071-123">0 – Audio</span></span></p></li>
<li><p><span data-ttu-id="38071-124">1 — видео</span><span class="sxs-lookup"><span data-stu-id="38071-124">1 – Video</span></span></p></li>
<li><p><span data-ttu-id="38071-125">2 — панорамное видео</span><span class="sxs-lookup"><span data-stu-id="38071-125">2 – Panoramic video</span></span></p></li>
<li><p><span data-ttu-id="38071-126">3 — общий доступ к приложениям и рабочим столам</span><span class="sxs-lookup"><span data-stu-id="38071-126">3 –Application/Desktop Sharing</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="38071-127"><strong>стреамид</strong></span><span class="sxs-lookup"><span data-stu-id="38071-127"><strong>StreamID</strong></span></span></p></td>
<td><p><span data-ttu-id="38071-128">int</span><span class="sxs-lookup"><span data-stu-id="38071-128">int</span></span></p></td>
<td><p><span data-ttu-id="38071-129">Primary</span><span class="sxs-lookup"><span data-stu-id="38071-129">Primary</span></span></p></td>
<td><p><span data-ttu-id="38071-130">Уникальный идентификатор потока общего доступа к приложениям.</span><span class="sxs-lookup"><span data-stu-id="38071-130">Unique identifier of the application sharing stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="38071-131"><strong>життеринтерарривал</strong></span><span class="sxs-lookup"><span data-stu-id="38071-131"><strong>JitterInterArrival</strong></span></span></p></td>
<td><p><span data-ttu-id="38071-132">int</span><span class="sxs-lookup"><span data-stu-id="38071-132">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="38071-133">Среднее значение колебаний, зарегистрированных между прибытиями пакетов RTP.</span><span class="sxs-lookup"><span data-stu-id="38071-133">Average jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="38071-134">(Колебание — это мера &quot; вибрирования &quot; вызова.) Большие значения колебаний обычно вызваны перегрузкой или перегрузкой сервера мультимедиа, что приводит к искажению или потере звука.</span><span class="sxs-lookup"><span data-stu-id="38071-134">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="38071-135"><strong>життеринтерарривалмакс</strong></span><span class="sxs-lookup"><span data-stu-id="38071-135"><strong>JitterInterArrivalMax</strong></span></span></p></td>
<td><p><span data-ttu-id="38071-136">int</span><span class="sxs-lookup"><span data-stu-id="38071-136">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="38071-137">Максимальное значение колебаний, зарегистрированных между прибытиями пакетов RTP.</span><span class="sxs-lookup"><span data-stu-id="38071-137">Maximum jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="38071-138">(Колебание — это мера &quot; вибрирования &quot; вызова.) Большие значения колебаний обычно вызваны перегрузкой или перегрузкой сервера мультимедиа, что приводит к искажению или потере звука.</span><span class="sxs-lookup"><span data-stu-id="38071-138">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="38071-139"><strong>Обработки</strong></span><span class="sxs-lookup"><span data-stu-id="38071-139"><strong>RoundTrip</strong></span></span></p></td>
<td><p><span data-ttu-id="38071-140">int</span><span class="sxs-lookup"><span data-stu-id="38071-140">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="38071-p105">Среднее время (в миллисекундах), необходимое для перемещения пакета Real-Time Transport Protocol в другую конечную точку и его возврата. Приемлемым считается время двусторонней передачи, равное 200 мс (или менее).</span><span class="sxs-lookup"><span data-stu-id="38071-p105">Average amount of (in milliseconds) required for a Real-Time Transport Protocol packet to travel to another endpoint and then back. Round-trip times of 200 milliseconds or less are considered of acceptable quality.</span></span></p>
<p><span data-ttu-id="38071-p106">Высокие значения времени двусторонней передачи могут быть обусловлены международной маршрутизацией вызовов, неправильной конфигурацией маршрутизации или перегрузкой сервера-посредника. Длительное время двусторонней передачи приводит к возникновению проблем при двусторонних аудиоразговорах в режиме реального времени.</span><span class="sxs-lookup"><span data-stu-id="38071-p106">High round-trip values can be caused by international call routing; a routing misconfiguration; or an overloaded media server. High round-trip times result in difficulties with two-way, real-time audio conversations.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="38071-145"><strong>раундтрипмакс</strong></span><span class="sxs-lookup"><span data-stu-id="38071-145"><strong>RoundTripMax</strong></span></span></p></td>
<td><p><span data-ttu-id="38071-146">int</span><span class="sxs-lookup"><span data-stu-id="38071-146">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="38071-p107">Максимальное время (в миллисекундах), необходимое для перемещения пакета Real-Time Transport Protocol в другую конечную точку и его возврата. Приемлемым считается время двусторонней передачи, равное 200 мс (или менее).</span><span class="sxs-lookup"><span data-stu-id="38071-p107">Maximum amount of (in milliseconds) required for a Real-Time Transport Protocol packet to travel to another endpoint and then back. Round-trip times of 200 milliseconds or less are considered of acceptable quality.</span></span></p>
<p><span data-ttu-id="38071-p108">Высокие значения времени двусторонней передачи могут быть обусловлены международной маршрутизацией вызовов, неправильной конфигурацией маршрутизации или перегрузкой сервера-посредника. Длительное время двусторонней передачи приводит к возникновению проблем при двусторонних аудиоразговорах в режиме реального времени.</span><span class="sxs-lookup"><span data-stu-id="38071-p108">High round-trip values can be caused by international call routing; a routing misconfiguration; or an overloaded media server. High round-trip times result in difficulties with two-way, real-time audio conversations.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="38071-151"><strong>паккетлоссрате</strong></span><span class="sxs-lookup"><span data-stu-id="38071-151"><strong>PacketLossRate</strong></span></span></p></td>
<td><p><span data-ttu-id="38071-152">float</span><span class="sxs-lookup"><span data-stu-id="38071-152">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="38071-p109">Средняя частота потери пакетов RTP. (Потеря пакетов происходит, когда пакеты RTP (Real-Time Transport Protocol — протокол, используемый для передачи аудио- и видеопакетов через Интернет) не достигают места назначения.) Высокие показатели потерь обычно вызваны перегрузкой, недостаточной полосой пропускания, помехами или перегрузкой беспроводной сети, а также перегрузкой сервера-посредника. Потеря пакетов обычно приводит к искажению звука или потере аудиосигналов.</span><span class="sxs-lookup"><span data-stu-id="38071-p109">Average rate of Real-Time Transport Protocol (RTP) packet loss. (Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion; lack of bandwidth; wireless congestion or interference; or an overloaded media server. Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="38071-156"><strong>паккетлоссратемакс</strong></span><span class="sxs-lookup"><span data-stu-id="38071-156"><strong>PacketLossRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="38071-157">float</span><span class="sxs-lookup"><span data-stu-id="38071-157">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="38071-p110">Максимальная частота потери пакетов RTP. (Потеря пакетов происходит, когда пакеты RTP (Real-Time Transport Protocol — протокол, используемый для передачи аудио- и видеопакетов через Интернет) не достигают места назначения.) Высокие показатели потерь обычно вызваны перегрузкой, недостаточной полосой пропускания, помехами или перегрузкой беспроводной сети, а также перегрузкой сервера-посредника. Потеря пакетов обычно приводит к искажению звука или потере аудиосигналов.</span><span class="sxs-lookup"><span data-stu-id="38071-p110">Maximum rate of Real-Time Transport Protocol (RTP) packet loss. (Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion; lack of bandwidth; wireless congestion or interference; or an overloaded media server. Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="38071-161"><strong>паккетутилизатион</strong></span><span class="sxs-lookup"><span data-stu-id="38071-161"><strong>PacketUtilization</strong></span></span></p></td>
<td><p><span data-ttu-id="38071-162">int</span><span class="sxs-lookup"><span data-stu-id="38071-162">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="38071-163">Количество отправленных пакетов.</span><span class="sxs-lookup"><span data-stu-id="38071-163">Number of packets sent.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="38071-164"><strong>Самый полоса пропускания</strong></span><span class="sxs-lookup"><span data-stu-id="38071-164"><strong>BandwidthEst</strong></span></span></p></td>
<td><p><span data-ttu-id="38071-165">int</span><span class="sxs-lookup"><span data-stu-id="38071-165">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="38071-p111">Предполагаемая полоса пропускания для односторонней передачи, доступная в конце сеанса. Измеряется в битах в секунду.</span><span class="sxs-lookup"><span data-stu-id="38071-p111">Estimated one-way bandwidth available at the end of the session. Reported in bits per second.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="38071-168"><strong>аппшарингпайлоаддескриптион</strong></span><span class="sxs-lookup"><span data-stu-id="38071-168"><strong>AppSharingPayloadDescription</strong></span></span></p></td>
<td><p><span data-ttu-id="38071-169">int</span><span class="sxs-lookup"><span data-stu-id="38071-169">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="38071-170">Описание загрузки общего доступа к приложениям.</span><span class="sxs-lookup"><span data-stu-id="38071-170">Description of the application sharing payload.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="38071-171"><strong>релативеоневайтотал</strong></span><span class="sxs-lookup"><span data-stu-id="38071-171"><strong>RelativeOneWayTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="38071-172">float</span><span class="sxs-lookup"><span data-stu-id="38071-172">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="38071-p112">Общая величина односторонней задержки. Относительная односторонняя задержка измеряет задержку между клиентом и сервером.</span><span class="sxs-lookup"><span data-stu-id="38071-p112">Total amount of one-way latency. Relative one-way latency measures the delay between the client and the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="38071-175"><strong>релативеоневайавераже</strong></span><span class="sxs-lookup"><span data-stu-id="38071-175"><strong>RelativeOneWayAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="38071-176">float</span><span class="sxs-lookup"><span data-stu-id="38071-176">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="38071-p113">Средняя величина односторонней задержки. Относительная односторонняя задержка измеряет задержку между клиентом и сервером</span><span class="sxs-lookup"><span data-stu-id="38071-p113">Average amount of one-way latency. Relative one-way latency measures the delay between the client and the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="38071-179"><strong>релативеоневаймакс</strong></span><span class="sxs-lookup"><span data-stu-id="38071-179"><strong>RelativeOneWayMax</strong></span></span></p></td>
<td><p><span data-ttu-id="38071-180">float</span><span class="sxs-lookup"><span data-stu-id="38071-180">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="38071-p114">Максимальная величина односторонней задержки. Относительная односторонняя задержка измеряет задержку между клиентом и сервером</span><span class="sxs-lookup"><span data-stu-id="38071-p114">Maximum amount of one-way latency. Relative one-way latency measures the delay between the client and the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="38071-183"><strong>релативеоневайбурстоккурренцес</strong></span><span class="sxs-lookup"><span data-stu-id="38071-183"><strong>RelativeOneWayBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="38071-184">int</span><span class="sxs-lookup"><span data-stu-id="38071-184">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="38071-p115">Общее число повторов пакетов в одну сторону. "Пакетная" передача представляет собой передачу, при которой данные передаются посредством случайных пакетов, а не в виде устойчивого потока. С помощью этой метрики измеряется поток данных между клиентом и сервером.</span><span class="sxs-lookup"><span data-stu-id="38071-p115">Total one-way burst occurrences. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream. This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="38071-188"><strong>релативеоневайбурстденсити</strong></span><span class="sxs-lookup"><span data-stu-id="38071-188"><strong>RelativeOneWayBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="38071-189">float</span><span class="sxs-lookup"><span data-stu-id="38071-189">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="38071-p116">Общая плотность пакетов в одну сторону. "Пакетная" передача представляет собой передачу, при которой данные передаются посредством случайных пакетов, а не в виде устойчивого потока. С помощью этой метрики измеряется поток данных между клиентом и сервером.</span><span class="sxs-lookup"><span data-stu-id="38071-p116">Total one-way burst density. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream. This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="38071-193"><strong>релативеоневайбурстдуратион</strong></span><span class="sxs-lookup"><span data-stu-id="38071-193"><strong>RelativeOneWayBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="38071-194">float</span><span class="sxs-lookup"><span data-stu-id="38071-194">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="38071-p117">Общая длительность пакетов в одну сторону. "Пакетная" передача представляет собой передачу, при которой данные передаются посредством случайных пакетов, а не в виде устойчивого потока. С помощью этой метрики измеряется поток данных между клиентом и сервером.</span><span class="sxs-lookup"><span data-stu-id="38071-p117">Total one-way burst duration. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream. This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="38071-198"><strong>релативеоневайгапоккурренцес</strong></span><span class="sxs-lookup"><span data-stu-id="38071-198"><strong>RelativeOneWayGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="38071-199">int</span><span class="sxs-lookup"><span data-stu-id="38071-199">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="38071-p118">Общее число повторов разрывов в одну сторону. "Пакетная" передача представляет собой передачу, при которой данные передаются посредством случайных пакетов, а не в виде устойчивого потока; разрывы указывают задержку между этими пакетами. С помощью данной метрики измеряется поток данных между клиентом и сервером.</span><span class="sxs-lookup"><span data-stu-id="38071-p118">Total one-way gap occurrences. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts. This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="38071-203"><strong>релативеоневайгапденсити</strong></span><span class="sxs-lookup"><span data-stu-id="38071-203"><strong>RelativeOneWayGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="38071-204">float</span><span class="sxs-lookup"><span data-stu-id="38071-204">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="38071-p119">Общая плотность разрывов в одну сторону. "Пакетная" передача представляет собой передачу, при которой данные передаются посредством случайных пакетов, а не в виде устойчивого потока; разрывы указывают задержку между этими пакетами. С помощью данной метрики измеряется поток данных между клиентом и сервером.</span><span class="sxs-lookup"><span data-stu-id="38071-p119">Total one-way gap density. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts. This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="38071-208"><strong>релативеоневайгапдуратион</strong></span><span class="sxs-lookup"><span data-stu-id="38071-208"><strong>RelativeOneWayGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="38071-209">float</span><span class="sxs-lookup"><span data-stu-id="38071-209">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="38071-p120">Общая длительность разрывов в одну сторону. "Пакетная" передача представляет собой передачу, при которой данные передаются посредством случайных пакетов, а не в виде устойчивого потока; разрывы указывают задержку между этими пакетами. С помощью данной метрики измеряется поток данных между клиентом и сервером.</span><span class="sxs-lookup"><span data-stu-id="38071-p120">Total one-way gap duration. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts. This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="38071-213"><strong>аппликатионшарингтипе</strong></span><span class="sxs-lookup"><span data-stu-id="38071-213"><strong>ApplicationSharingType</strong></span></span></p></td>
<td><p><span data-ttu-id="38071-214">varChar (256)</span><span class="sxs-lookup"><span data-stu-id="38071-214">varChar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="38071-215">Роль приложения (средство предоставления доступа и средство просмотра) и тип содержимого.</span><span class="sxs-lookup"><span data-stu-id="38071-215">Application role (Sharer or Viewer) and content type.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="38071-216"><strong>рдптилепроцессинглатенцитотал</strong></span><span class="sxs-lookup"><span data-stu-id="38071-216"><strong>RDPTileProcessingLatencyTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="38071-217">float</span><span class="sxs-lookup"><span data-stu-id="38071-217">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="38071-p121">Общее время обработки заголовков RDP. Чем больше общее значение, тем длиннее задержки при просмотре.</span><span class="sxs-lookup"><span data-stu-id="38071-p121">Total processing time for remote desktop protocol (RDP) tiles. A higher total equates to a longer delay in the viewing experience.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="38071-220"><strong>рдптилепроцессинглатенциавераже</strong></span><span class="sxs-lookup"><span data-stu-id="38071-220"><strong>RDPTileProcessingLatencyAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="38071-221">float</span><span class="sxs-lookup"><span data-stu-id="38071-221">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="38071-p122">Среднее время обработки заголовков RDP. Чем больше общее значение, тем длиннее задержки при просмотре.</span><span class="sxs-lookup"><span data-stu-id="38071-p122">Average processing time for remote desktop protocol (RDP) tiles. A higher total equates to a longer delay in the viewing experience.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="38071-224"><strong>рдптилепроцессинглатенцимакс</strong></span><span class="sxs-lookup"><span data-stu-id="38071-224"><strong>RDPTileProcessingLatencyMax</strong></span></span></p></td>
<td><p><span data-ttu-id="38071-225">float</span><span class="sxs-lookup"><span data-stu-id="38071-225">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="38071-p123">Максимальное время обработки заголовков RDP. Чем больше общее значение, тем длиннее задержки при просмотре.</span><span class="sxs-lookup"><span data-stu-id="38071-p123">Maximum processing time for remote desktop protocol (RDP) tiles. A higher total equates to a longer delay in the viewing experience.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="38071-228"><strong>рдптилепроцессинглатенцибурстоккурренцес</strong></span><span class="sxs-lookup"><span data-stu-id="38071-228"><strong>RDPTileProcessingLatencyBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="38071-229">int</span><span class="sxs-lookup"><span data-stu-id="38071-229">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="38071-p124">Повторы пакетов во время обработки заголовков RDP. Передача с повторами пакетов — это передача, при которой данные передаются случайными пакетами, а не равномерным потоком.</span><span class="sxs-lookup"><span data-stu-id="38071-p124">Burst occurrences in the processing time for remote desktop protocol (RDP) tiles. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="38071-232"><strong>рдптилепроцессинглатенцибурстденсити</strong></span><span class="sxs-lookup"><span data-stu-id="38071-232"><strong>RDPTileProcessingLatencyBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="38071-233">float</span><span class="sxs-lookup"><span data-stu-id="38071-233">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="38071-p125">Плотность пакетов во время обработки заголовков RDP. Передача с повторами пакетов — это передача, при которой данные передаются случайными пакетами, а не равномерным потоком.</span><span class="sxs-lookup"><span data-stu-id="38071-p125">Burst density in the processing time for remote desktop protocol (RDP) tiles. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="38071-236"><strong>рдптилепроцессинглатенцибурстдуратион</strong></span><span class="sxs-lookup"><span data-stu-id="38071-236"><strong>RDPTileProcessingLatencyBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="38071-237">float</span><span class="sxs-lookup"><span data-stu-id="38071-237">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="38071-p126">Продолжительность пакетной передачи во время обработки заголовков RDP. Передача с повторами пакетов — это передача, при которой данные передаются случайными пакетами, а не равномерным потоком.</span><span class="sxs-lookup"><span data-stu-id="38071-p126">Burst duration in the processing time for remote desktop protocol (RDP) tiles. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="38071-240"><strong>рдптилепроцессинглатенцигапоккурренцес</strong></span><span class="sxs-lookup"><span data-stu-id="38071-240"><strong>RDPTileProcessingLatencyGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="38071-241">int</span><span class="sxs-lookup"><span data-stu-id="38071-241">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="38071-242">Разрывы во время обработки заголовков RDP.</span><span class="sxs-lookup"><span data-stu-id="38071-242">Gap occurrences in the processing time for remote desktop protocol (RDP) tiles.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="38071-243"><strong>рдптилепроцессинглатенцигапденсити</strong></span><span class="sxs-lookup"><span data-stu-id="38071-243"><strong>RDPTileProcessingLatencyGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="38071-244">float</span><span class="sxs-lookup"><span data-stu-id="38071-244">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="38071-p127">Плотность разрывов во время обработки заголовков RDP. Чем ниже плотность разрывов, тем лучше просмотр.</span><span class="sxs-lookup"><span data-stu-id="38071-p127">Gap density in the processing time for remote desktop protocol (RDP) tiles. Low gap density equates to a better viewing experience.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="38071-247"><strong>рдптилепроцессинглатенцигапдуратион</strong></span><span class="sxs-lookup"><span data-stu-id="38071-247"><strong>RDPTileProcessingLatencyGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="38071-248">float</span><span class="sxs-lookup"><span data-stu-id="38071-248">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="38071-p128">Продолжительность разрывов во время обработки заголовков RDP. Чем ниже продолжительность разрывов, тем лучше просмотр.</span><span class="sxs-lookup"><span data-stu-id="38071-p128">Gap duration in the processing time for remote desktop protocol (RDP) tiles. Short gap durations equate to a better viewing experience.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="38071-251"><strong>каптуретилератетотал</strong></span><span class="sxs-lookup"><span data-stu-id="38071-251"><strong>CaptureTileRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="38071-252">float</span><span class="sxs-lookup"><span data-stu-id="38071-252">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="38071-253">Общая частота захвата заголовков (заголовков в секунду).</span><span class="sxs-lookup"><span data-stu-id="38071-253">Total rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="38071-254"><strong>каптуретилератеавераже</strong></span><span class="sxs-lookup"><span data-stu-id="38071-254"><strong>CaptureTileRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="38071-255">float</span><span class="sxs-lookup"><span data-stu-id="38071-255">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="38071-256">Средняя частота захвата заголовков (заголовков в секунду).</span><span class="sxs-lookup"><span data-stu-id="38071-256">Average rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="38071-257"><strong>каптуретилератемакс</strong></span><span class="sxs-lookup"><span data-stu-id="38071-257"><strong>CaptureTileRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="38071-258">float</span><span class="sxs-lookup"><span data-stu-id="38071-258">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="38071-259">Максимальная частота захвата заголовков (заголовков в секунду).</span><span class="sxs-lookup"><span data-stu-id="38071-259">Maximum rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="38071-260"><strong>каптуретилератебурстоккурренцес</strong></span><span class="sxs-lookup"><span data-stu-id="38071-260"><strong>CaptureTileRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="38071-261">целое</span><span class="sxs-lookup"><span data-stu-id="38071-261">in t</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="38071-262">Повторы пакетов в частоте захвата заголовков (заголовков в секунду).</span><span class="sxs-lookup"><span data-stu-id="38071-262">Burst occurrences in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="38071-263"><strong>каптуретилератебурстденсити</strong></span><span class="sxs-lookup"><span data-stu-id="38071-263"><strong>CaptureTileRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="38071-264">float</span><span class="sxs-lookup"><span data-stu-id="38071-264">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="38071-265">Плотность повторов пакетов в частоте захвата заголовков (заголовков в секунду).</span><span class="sxs-lookup"><span data-stu-id="38071-265">Burst density in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="38071-266"><strong>каптуретилератебурстдуратион</strong></span><span class="sxs-lookup"><span data-stu-id="38071-266"><strong>CaptureTileRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="38071-267">float</span><span class="sxs-lookup"><span data-stu-id="38071-267">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="38071-268">Продолжительность повторов пакетов в частоте захвата заголовков (заголовков в секунду).</span><span class="sxs-lookup"><span data-stu-id="38071-268">Burst duration in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="38071-269"><strong>каптуретилератегапоккурренцес</strong></span><span class="sxs-lookup"><span data-stu-id="38071-269"><strong>CaptureTileRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="38071-270">int</span><span class="sxs-lookup"><span data-stu-id="38071-270">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="38071-271">Разрывы в частоте захвата заголовков (заголовков в секунду).</span><span class="sxs-lookup"><span data-stu-id="38071-271">Gap occurrences in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="38071-272"><strong>каптуретилератегапденсити</strong></span><span class="sxs-lookup"><span data-stu-id="38071-272"><strong>CaptureTileRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="38071-273">float</span><span class="sxs-lookup"><span data-stu-id="38071-273">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="38071-274">Плотность разрывов в частоте захвата заголовков (заголовков в секунду).</span><span class="sxs-lookup"><span data-stu-id="38071-274">Gap density in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="38071-275"><strong>каптуретилератегапдуратион</strong></span><span class="sxs-lookup"><span data-stu-id="38071-275"><strong>CaptureTileRateGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="38071-276">float</span><span class="sxs-lookup"><span data-stu-id="38071-276">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="38071-277">Продолжительность разрывов в частоте захвата заголовков (заголовков в секунду).</span><span class="sxs-lookup"><span data-stu-id="38071-277">Gap duration in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="38071-278"><strong>споиледтилеперценттотал</strong></span><span class="sxs-lookup"><span data-stu-id="38071-278"><strong>SpoiledTilePercentTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="38071-279">float</span><span class="sxs-lookup"><span data-stu-id="38071-279">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="38071-280">Общее процентное соотношение контента, не достигшего средства просмотра и отброшенного или перезаписанного новым контентом.</span><span class="sxs-lookup"><span data-stu-id="38071-280">Total percentage of the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="38071-281"><strong>споиледтилеперцентавераже</strong></span><span class="sxs-lookup"><span data-stu-id="38071-281"><strong>SpoiledTilePercentAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="38071-282">float</span><span class="sxs-lookup"><span data-stu-id="38071-282">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="38071-283">Среднее процентное соотношение контента, не достигшего средства просмотра и отброшенного или перезаписанного новым контентом.</span><span class="sxs-lookup"><span data-stu-id="38071-283">Average percentage of the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="38071-284"><strong>споиледтилеперцентмакс</strong></span><span class="sxs-lookup"><span data-stu-id="38071-284"><strong>SpoiledTilePercentMax</strong></span></span></p></td>
<td><p><span data-ttu-id="38071-285">float</span><span class="sxs-lookup"><span data-stu-id="38071-285">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="38071-286">Максимальное процентное соотношение контента, не достигшего средства просмотра и отброшенного или перезаписанного новым контентом.</span><span class="sxs-lookup"><span data-stu-id="38071-286">Maximum percentage of the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="38071-287"><strong>споиледтилеперцентбурстоккурренцес</strong></span><span class="sxs-lookup"><span data-stu-id="38071-287"><strong>SpoiledTilePercentBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="38071-288">int</span><span class="sxs-lookup"><span data-stu-id="38071-288">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="38071-289">Повторы пакетов контента, не достигшего средства просмотра и отброшенного или перезаписанного новым контентом.</span><span class="sxs-lookup"><span data-stu-id="38071-289">Burst occurrences for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="38071-290"><strong>споиледтилеперцентбурстденсити</strong></span><span class="sxs-lookup"><span data-stu-id="38071-290"><strong>SpoiledTilePercentBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="38071-291">float</span><span class="sxs-lookup"><span data-stu-id="38071-291">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="38071-292">Плотность повторов пакетов контента, не достигшего средства просмотра и отброшенного или перезаписанного новым контентом.</span><span class="sxs-lookup"><span data-stu-id="38071-292">Burst density for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="38071-293"><strong>споиледтилеперцентбурстдуратион</strong></span><span class="sxs-lookup"><span data-stu-id="38071-293"><strong>SpoiledTilePercentBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="38071-294">float</span><span class="sxs-lookup"><span data-stu-id="38071-294">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="38071-295">Продолжительность повторов пакетов контента, не достигшего средства просмотра и отброшенного или перезаписанного новым контентом.</span><span class="sxs-lookup"><span data-stu-id="38071-295">Burst duration for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="38071-296"><strong>споиледтилеперцентгапоккурренцес</strong></span><span class="sxs-lookup"><span data-stu-id="38071-296"><strong>SpoiledTilePercentGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="38071-297">int</span><span class="sxs-lookup"><span data-stu-id="38071-297">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="38071-298">Разрывы контента, не достигшего средства просмотра и отброшенного или перезаписанного новым контентом.</span><span class="sxs-lookup"><span data-stu-id="38071-298">Gap occurrences for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="38071-299"><strong>споиледтилеперцентгапденсити</strong></span><span class="sxs-lookup"><span data-stu-id="38071-299"><strong>SpoiledTilePercentGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="38071-300">float</span><span class="sxs-lookup"><span data-stu-id="38071-300">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="38071-301">Плотность разрывов контента, не достигшего средства просмотра и отброшенного или перезаписанного новым контентом.</span><span class="sxs-lookup"><span data-stu-id="38071-301">Gap density for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="38071-302"><strong>споиледтилеперцентгапдуратион</strong></span><span class="sxs-lookup"><span data-stu-id="38071-302"><strong>SpoiledTilePercentGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="38071-303">float</span><span class="sxs-lookup"><span data-stu-id="38071-303">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="38071-304">Продолжительность разрывов контента, не достигшего средства просмотра и отброшенного или перезаписанного новым контентом.</span><span class="sxs-lookup"><span data-stu-id="38071-304">Gap duration for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="38071-305"><strong>скрапингфрамератетотал</strong></span><span class="sxs-lookup"><span data-stu-id="38071-305"><strong>ScrapingFrameRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="38071-306">float</span><span class="sxs-lookup"><span data-stu-id="38071-306">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="38071-307">Общее количество кадров, исключенных из источника графики.</span><span class="sxs-lookup"><span data-stu-id="38071-307">Total number of frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="38071-308"><strong>скрапингфрамератеавераже</strong></span><span class="sxs-lookup"><span data-stu-id="38071-308"><strong>ScrapingFrameRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="38071-309">float</span><span class="sxs-lookup"><span data-stu-id="38071-309">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="38071-310">Среднее количество кадров, исключенных из источника графики.</span><span class="sxs-lookup"><span data-stu-id="38071-310">Average number of frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="38071-311"><strong>скрапингфрамератемакс</strong></span><span class="sxs-lookup"><span data-stu-id="38071-311"><strong>ScrapingFrameRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="38071-312">float</span><span class="sxs-lookup"><span data-stu-id="38071-312">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="38071-313">Максимальное количество кадров, исключенных из источника графики.</span><span class="sxs-lookup"><span data-stu-id="38071-313">Maximum number of frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="38071-314"><strong>скрапингфрамератебурстоккурренцес</strong></span><span class="sxs-lookup"><span data-stu-id="38071-314"><strong>ScrapingFrameRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="38071-315">int</span><span class="sxs-lookup"><span data-stu-id="38071-315">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="38071-316">Повторы пакетов в кадрах, исключенных из источника графики.</span><span class="sxs-lookup"><span data-stu-id="38071-316">Burst occurrences in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="38071-317"><strong>скрапингфрамератебурстденсити</strong></span><span class="sxs-lookup"><span data-stu-id="38071-317"><strong>ScrapingFrameRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="38071-318">float</span><span class="sxs-lookup"><span data-stu-id="38071-318">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="38071-319">Плотность повторов пакетов в кадрах, исключенных из источника графики.</span><span class="sxs-lookup"><span data-stu-id="38071-319">Burst density in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="38071-320"><strong>скрапингфрамератебурстдуратион</strong></span><span class="sxs-lookup"><span data-stu-id="38071-320"><strong>ScrapingFrameRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="38071-321">float</span><span class="sxs-lookup"><span data-stu-id="38071-321">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="38071-322">Продолжительность повторов пакетов в кадрах, исключенных из источника графики.</span><span class="sxs-lookup"><span data-stu-id="38071-322">Burst duration in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="38071-323"><strong>скрапингфрамератегапоккурренцес</strong></span><span class="sxs-lookup"><span data-stu-id="38071-323"><strong>ScrapingFrameRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="38071-324">int</span><span class="sxs-lookup"><span data-stu-id="38071-324">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="38071-325">Разрывы в кадрах, исключенных из источника графики.</span><span class="sxs-lookup"><span data-stu-id="38071-325">Gap occurrences in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="38071-326"><strong>скрапингфрамератегапденсити</strong></span><span class="sxs-lookup"><span data-stu-id="38071-326"><strong>ScrapingFrameRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="38071-327">float</span><span class="sxs-lookup"><span data-stu-id="38071-327">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="38071-328">Плотность разрывов в кадрах, исключенных из источника графики.</span><span class="sxs-lookup"><span data-stu-id="38071-328">Gap density in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="38071-329"><strong>скрапингфрамератегапдуратион</strong></span><span class="sxs-lookup"><span data-stu-id="38071-329"><strong>ScrapingFrameRateGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="38071-330">float</span><span class="sxs-lookup"><span data-stu-id="38071-330">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="38071-331">Продолжительность разрывов в кадрах, исключенных из источника графики.</span><span class="sxs-lookup"><span data-stu-id="38071-331">Gap duration in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="38071-332"><strong>инкомингтилератетотал</strong></span><span class="sxs-lookup"><span data-stu-id="38071-332"><strong>IncomingTileRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="38071-333">float</span><span class="sxs-lookup"><span data-stu-id="38071-333">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="38071-334">Общая частота кадров, получаемых средством просмотра.</span><span class="sxs-lookup"><span data-stu-id="38071-334">Total incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="38071-335"><strong>инкомингтилератеавераже</strong></span><span class="sxs-lookup"><span data-stu-id="38071-335"><strong>IncomingTileRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="38071-336">float</span><span class="sxs-lookup"><span data-stu-id="38071-336">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="38071-337">Средняя частота кадров, получаемых средством просмотра.</span><span class="sxs-lookup"><span data-stu-id="38071-337">Average incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="38071-338"><strong>инкомингтилератемакс</strong></span><span class="sxs-lookup"><span data-stu-id="38071-338"><strong>IncomingTileRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="38071-339">float</span><span class="sxs-lookup"><span data-stu-id="38071-339">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="38071-340">Максимальная частота заголовков, получаемых средством просмотра.</span><span class="sxs-lookup"><span data-stu-id="38071-340">Maximum incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="38071-341"><strong>инкомингтилератебурстоккурренцес</strong></span><span class="sxs-lookup"><span data-stu-id="38071-341"><strong>IncomingTileRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="38071-342">int</span><span class="sxs-lookup"><span data-stu-id="38071-342">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="38071-343">Повторы пакетов относительно частоты входящих заголовков, получаемых средством просмотра.</span><span class="sxs-lookup"><span data-stu-id="38071-343">Burst occurrences in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="38071-344"><strong>инкомингтилератебурстденсити</strong></span><span class="sxs-lookup"><span data-stu-id="38071-344"><strong>IncomingTileRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="38071-345">float</span><span class="sxs-lookup"><span data-stu-id="38071-345">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="38071-346">Плотность повторов пакетов относительно частоты входящих заголовков, получаемых средством просмотра.</span><span class="sxs-lookup"><span data-stu-id="38071-346">Burst density in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="38071-347"><strong>инкомингтилератебурстдуратион</strong></span><span class="sxs-lookup"><span data-stu-id="38071-347"><strong>IncomingTileRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="38071-348">float</span><span class="sxs-lookup"><span data-stu-id="38071-348">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="38071-349">Продолжительность повторов пакетов относительно частоты входящих заголовков, получаемых средством просмотра.</span><span class="sxs-lookup"><span data-stu-id="38071-349">Burst duration in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="38071-350"><strong>инкомингтилератегапоккурренцес</strong></span><span class="sxs-lookup"><span data-stu-id="38071-350"><strong>IncomingTileRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="38071-351">int</span><span class="sxs-lookup"><span data-stu-id="38071-351">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="38071-352">Разрывы относительно частоты входящих заголовков, получаемых средством просмотра.</span><span class="sxs-lookup"><span data-stu-id="38071-352">Gap occurrences in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="38071-353"><strong>инкомингтилератегапденсити</strong></span><span class="sxs-lookup"><span data-stu-id="38071-353"><strong>IncomingTileRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="38071-354">float</span><span class="sxs-lookup"><span data-stu-id="38071-354">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="38071-355">Плотность разрывов относительно частоты входящих заголовков, получаемых средством просмотра.</span><span class="sxs-lookup"><span data-stu-id="38071-355">Gap density in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="38071-356"><strong>инкомингтилератегапдуратион</strong></span><span class="sxs-lookup"><span data-stu-id="38071-356"><strong>IncomingTileRateGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="38071-357">float</span><span class="sxs-lookup"><span data-stu-id="38071-357">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="38071-358">Продолжительность разрывов относительно частоты входящих заголовков, получаемых средством просмотра.</span><span class="sxs-lookup"><span data-stu-id="38071-358">Gap duration in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="38071-359"><strong>инкомингфрамератетотал</strong></span><span class="sxs-lookup"><span data-stu-id="38071-359"><strong>IncomingFrameRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="38071-360">float</span><span class="sxs-lookup"><span data-stu-id="38071-360">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="38071-361">Общая частота кадров, получаемых средством просмотра.</span><span class="sxs-lookup"><span data-stu-id="38071-361">Total incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="38071-362"><strong>инкомингфрамератеавераже</strong></span><span class="sxs-lookup"><span data-stu-id="38071-362"><strong>IncomingFrameRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="38071-363">float</span><span class="sxs-lookup"><span data-stu-id="38071-363">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="38071-364">Средняя частота кадров, получаемых средством просмотра.</span><span class="sxs-lookup"><span data-stu-id="38071-364">Average incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="38071-365"><strong>инкомингфрамератемакс</strong></span><span class="sxs-lookup"><span data-stu-id="38071-365"><strong>IncomingFrameRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="38071-366">float</span><span class="sxs-lookup"><span data-stu-id="38071-366">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="38071-367">Максимальная входящая частота кадров, получаемых средством просмотра.</span><span class="sxs-lookup"><span data-stu-id="38071-367">Maximum incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="38071-368"><strong>инкомингфрамератебурстоккурренцес</strong></span><span class="sxs-lookup"><span data-stu-id="38071-368"><strong>IncomingFrameRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="38071-369">int</span><span class="sxs-lookup"><span data-stu-id="38071-369">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="38071-370">Повторы пакетов относительно частоты входящих кадров, получаемых средством просмотра.</span><span class="sxs-lookup"><span data-stu-id="38071-370">Burst occurrences in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="38071-371"><strong>инкомингфрамератебурстденсити</strong></span><span class="sxs-lookup"><span data-stu-id="38071-371"><strong>IncomingFrameRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="38071-372">float</span><span class="sxs-lookup"><span data-stu-id="38071-372">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="38071-373">Плотность повторов пакетов относительно частоты входящих кадров, получаемых средством просмотра.</span><span class="sxs-lookup"><span data-stu-id="38071-373">Burst density in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="38071-374"><strong>инкомингфрамератебурстдуратион</strong></span><span class="sxs-lookup"><span data-stu-id="38071-374"><strong>IncomingFrameRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="38071-375">float</span><span class="sxs-lookup"><span data-stu-id="38071-375">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="38071-376">Продолжительность повторов пакетов относительно частоты входящих кадров, получаемых средством просмотра.</span><span class="sxs-lookup"><span data-stu-id="38071-376">Burst duration in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="38071-377"><strong>инкомингфрамератегапоккурренцес</strong></span><span class="sxs-lookup"><span data-stu-id="38071-377"><strong>IncomingFrameRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="38071-378">int</span><span class="sxs-lookup"><span data-stu-id="38071-378">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="38071-379">Разрывы относительно частоты входящих кадров, получаемых средством просмотра.</span><span class="sxs-lookup"><span data-stu-id="38071-379">Gap occurrences in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="38071-380"><strong>инкомингфрамератегапденсити</strong></span><span class="sxs-lookup"><span data-stu-id="38071-380"><strong>IncomingFrameRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="38071-381">float</span><span class="sxs-lookup"><span data-stu-id="38071-381">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="38071-382">Плотность разрывов относительно частоты входящих кадров, получаемых средством просмотра.</span><span class="sxs-lookup"><span data-stu-id="38071-382">Gap density in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="38071-383"><strong>инкомингфрамератедуратион</strong></span><span class="sxs-lookup"><span data-stu-id="38071-383"><strong>IncomingFrameRateDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="38071-384">float</span><span class="sxs-lookup"><span data-stu-id="38071-384">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="38071-385">Продолжительность разрывов относительно частоты входящих кадров, получаемых средством просмотра.</span><span class="sxs-lookup"><span data-stu-id="38071-385">Gap duration in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="38071-386"><strong>аутгоингтилератетотал</strong></span><span class="sxs-lookup"><span data-stu-id="38071-386"><strong>OutgoingTileRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="38071-387">float</span><span class="sxs-lookup"><span data-stu-id="38071-387">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="38071-388">Общая частота исходящих заголовков для отправителя.</span><span class="sxs-lookup"><span data-stu-id="38071-388">Total outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="38071-389"><strong>аутгоингтилератеавераже</strong></span><span class="sxs-lookup"><span data-stu-id="38071-389"><strong>OutgoingTileRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="38071-390">float</span><span class="sxs-lookup"><span data-stu-id="38071-390">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="38071-391">Средняя частота исходящих заголовков для отправителя.</span><span class="sxs-lookup"><span data-stu-id="38071-391">Average outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="38071-392"><strong>аутгоингтилератемакс</strong></span><span class="sxs-lookup"><span data-stu-id="38071-392"><strong>OutgoingTileRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="38071-393">float</span><span class="sxs-lookup"><span data-stu-id="38071-393">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="38071-394">Максимальная частота исходящих заголовков для отправителя.</span><span class="sxs-lookup"><span data-stu-id="38071-394">Maximum outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="38071-395"><strong>аутгоингтилератебурстоккурренцес</strong></span><span class="sxs-lookup"><span data-stu-id="38071-395"><strong>OutgoingTileRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="38071-396">int</span><span class="sxs-lookup"><span data-stu-id="38071-396">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="38071-397">Повторы пакетов относительно частоты исходящих заголовков для отправителя.</span><span class="sxs-lookup"><span data-stu-id="38071-397">Burst occurrences in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="38071-398"><strong>аутгоингтилератебурстденсити</strong></span><span class="sxs-lookup"><span data-stu-id="38071-398"><strong>OutgoingTileRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="38071-399">float</span><span class="sxs-lookup"><span data-stu-id="38071-399">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="38071-400">Плотность повторов пакетов относительно частоты исходящих заголовков для отправителя.</span><span class="sxs-lookup"><span data-stu-id="38071-400">Burst density in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="38071-401"><strong>аутгоингтилератебурстдуратион</strong></span><span class="sxs-lookup"><span data-stu-id="38071-401"><strong>OutgoingTileRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="38071-402">float</span><span class="sxs-lookup"><span data-stu-id="38071-402">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="38071-403">Продолжительность повторов пакетов относительно частоты исходящих заголовков для отправителя.</span><span class="sxs-lookup"><span data-stu-id="38071-403">Burst duration in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="38071-404"><strong>аутгоингтилератегапоккурренцес</strong></span><span class="sxs-lookup"><span data-stu-id="38071-404"><strong>OutgoingTileRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="38071-405">int</span><span class="sxs-lookup"><span data-stu-id="38071-405">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="38071-406">Разрывы относительно частоты исходящих заголовков для отправителя.</span><span class="sxs-lookup"><span data-stu-id="38071-406">Gap occurrences in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="38071-407"><strong>аутгоингтилератегапденсити</strong></span><span class="sxs-lookup"><span data-stu-id="38071-407"><strong>OutgoingTileRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="38071-408">float</span><span class="sxs-lookup"><span data-stu-id="38071-408">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="38071-409">Плотность разрывов относительно частоты исходящих заголовков для отправителя.</span><span class="sxs-lookup"><span data-stu-id="38071-409">Gap density in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="38071-410"><strong>аутгоингтилератегапдуратион</strong></span><span class="sxs-lookup"><span data-stu-id="38071-410"><strong>OutgoingTileRateGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="38071-411">float</span><span class="sxs-lookup"><span data-stu-id="38071-411">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="38071-412">Продолжительность разрывов относительно частоты исходящих заголовков для отправителя.</span><span class="sxs-lookup"><span data-stu-id="38071-412">Gap duration in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="38071-413"><strong>аутгоингфрамератетотал</strong></span><span class="sxs-lookup"><span data-stu-id="38071-413"><strong>OutgoingFrameRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="38071-414">float</span><span class="sxs-lookup"><span data-stu-id="38071-414">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="38071-415">Общая частота исходящих кадров для отправителя.</span><span class="sxs-lookup"><span data-stu-id="38071-415">Total outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="38071-416"><strong>аутгоингфрамератеавераже</strong></span><span class="sxs-lookup"><span data-stu-id="38071-416"><strong>OutgoingFrameRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="38071-417">float</span><span class="sxs-lookup"><span data-stu-id="38071-417">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="38071-418">Средняя частота исходящих кадров для отправителя.</span><span class="sxs-lookup"><span data-stu-id="38071-418">average outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="38071-419"><strong>аутгоингфрамератемакс</strong></span><span class="sxs-lookup"><span data-stu-id="38071-419"><strong>OutgoingFrameRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="38071-420">float</span><span class="sxs-lookup"><span data-stu-id="38071-420">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="38071-421">Максимальная частота исходящих кадров для отправителя.</span><span class="sxs-lookup"><span data-stu-id="38071-421">Maximum outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="38071-422"><strong>аутгоингфрамератебурстоккурренцес</strong></span><span class="sxs-lookup"><span data-stu-id="38071-422"><strong>OutgoingFrameRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="38071-423">int</span><span class="sxs-lookup"><span data-stu-id="38071-423">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="38071-424">Повторы пакетов относительно частоты исходящих кадров для отправителя.</span><span class="sxs-lookup"><span data-stu-id="38071-424">Burst occurrences in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="38071-425"><strong>аутгоингфрамератебурстденсити</strong></span><span class="sxs-lookup"><span data-stu-id="38071-425"><strong>OutgoingFrameRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="38071-426">float</span><span class="sxs-lookup"><span data-stu-id="38071-426">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="38071-427">Плотность повторов пакетов относительно частоты исходящих кадров для отправителя.</span><span class="sxs-lookup"><span data-stu-id="38071-427">Burst density in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="38071-428"><strong>аутгоингфрамератебурстдуратион</strong></span><span class="sxs-lookup"><span data-stu-id="38071-428"><strong>OutgoingFrameRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="38071-429">float</span><span class="sxs-lookup"><span data-stu-id="38071-429">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="38071-430">Продолжительность повторов пакетов относительно частоты исходящих кадров для отправителя.</span><span class="sxs-lookup"><span data-stu-id="38071-430">Burst duration in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="38071-431"><strong>аутгоингфрамератегапоккурренцес</strong></span><span class="sxs-lookup"><span data-stu-id="38071-431"><strong>OutgoingFrameRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="38071-432">int</span><span class="sxs-lookup"><span data-stu-id="38071-432">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="38071-433">Разрывы относительно частоты исходящих кадров для отправителя.</span><span class="sxs-lookup"><span data-stu-id="38071-433">Gap occurrences in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="38071-434"><strong>аутгоингфрамератегапденсити</strong></span><span class="sxs-lookup"><span data-stu-id="38071-434"><strong>OutgoingFrameRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="38071-435">float</span><span class="sxs-lookup"><span data-stu-id="38071-435">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="38071-436">Плотность разрывов относительно частоты исходящих кадров для отправителя.</span><span class="sxs-lookup"><span data-stu-id="38071-436">Gap density in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="38071-437"><strong>аутгоингфрамератегапдуратион</strong></span><span class="sxs-lookup"><span data-stu-id="38071-437"><strong>OutgoingFrameRateGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="38071-438">float</span><span class="sxs-lookup"><span data-stu-id="38071-438">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="38071-439">Продолжительность разрывов относительно частоты исходящих кадров для отправителя.</span><span class="sxs-lookup"><span data-stu-id="38071-439">Gap duration in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="38071-440"><strong>аверажеректанглехеигхт</strong></span><span class="sxs-lookup"><span data-stu-id="38071-440"><strong>AverageRectangleHeight</strong></span></span></p></td>
<td><p><span data-ttu-id="38071-441">int</span><span class="sxs-lookup"><span data-stu-id="38071-441">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="38071-442">Средняя высота разрешения видео в пикселах.</span><span class="sxs-lookup"><span data-stu-id="38071-442">Average video resolution height, in pixels.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="38071-443"><strong>аверажеректанглевидс</strong></span><span class="sxs-lookup"><span data-stu-id="38071-443"><strong>AverageRectangleWidth</strong></span></span></p></td>
<td><p><span data-ttu-id="38071-444">int</span><span class="sxs-lookup"><span data-stu-id="38071-444">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="38071-445">Средняя ширина разрешения видео в пикселах.</span><span class="sxs-lookup"><span data-stu-id="38071-445">Average video resolution width, in pixels.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="38071-446"><strong>Получение</strong></span><span class="sxs-lookup"><span data-stu-id="38071-446"><strong>Inbound</strong></span></span></p></td>
<td><p><span data-ttu-id="38071-447">Битовая</span><span class="sxs-lookup"><span data-stu-id="38071-447">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="38071-448">Средняя частота кадров (в кадрах в секунду) для передачи входящих.</span><span class="sxs-lookup"><span data-stu-id="38071-448">Average frame rate (in frames per second) for inbound transmissions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="38071-449"><strong>Прав</strong></span><span class="sxs-lookup"><span data-stu-id="38071-449"><strong>Outbound</strong></span></span></p></td>
<td><p><span data-ttu-id="38071-450">Битовая</span><span class="sxs-lookup"><span data-stu-id="38071-450">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="38071-451">Средняя частота кадров (в кадрах в секунду) для передачи исходящих пакетов.</span><span class="sxs-lookup"><span data-stu-id="38071-451">Average frame rate (in frames per second) for outbound transmissions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="38071-452"><strong>сендерискаллерпаи</strong></span><span class="sxs-lookup"><span data-stu-id="38071-452"><strong>SenderIsCallerPAI</strong></span></span></p></td>
<td><p><span data-ttu-id="38071-453">Битовая</span><span class="sxs-lookup"><span data-stu-id="38071-453">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="38071-454">1 означает направление потока от вызывающего абонента вызываемому абоненту.</span><span class="sxs-lookup"><span data-stu-id="38071-454">1 means the stream direction is from the caller to callee.</span></span></p>
<p><span data-ttu-id="38071-455">0 означает направление потока от вызываемого абонента вызывающему абоненту.</span><span class="sxs-lookup"><span data-stu-id="38071-455">0 means the stream direction is from the callee to the caller.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

