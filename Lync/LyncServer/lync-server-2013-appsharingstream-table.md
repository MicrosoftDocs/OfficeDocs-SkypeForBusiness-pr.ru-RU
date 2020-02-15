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
ms.openlocfilehash: 31a75ddd223816c57a69bd0c9e88b48845d4374e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42029310"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="appsharingstream-table-in-lync-server-2013"></a><span data-ttu-id="f2923-102">Таблица Аппшарингстреам в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f2923-102">AppSharingStream table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f2923-103">_**Последнее изменение темы:** 2014-02-21_</span><span class="sxs-lookup"><span data-stu-id="f2923-103">_**Topic Last Modified:** 2014-02-21_</span></span>

<span data-ttu-id="f2923-104">В таблице AppSharingStream содержатся показатели качества взаимодействия для сетевых потоков, используемых для общего доступа к приложениям.</span><span class="sxs-lookup"><span data-stu-id="f2923-104">The AppSharingStream table contains Quality of Experience metrics for the network streams used for application sharing.</span></span> <span data-ttu-id="f2923-105">Эта таблица была введена в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f2923-105">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f2923-106"><strong>Column</strong></span><span class="sxs-lookup"><span data-stu-id="f2923-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="f2923-107"><strong>Тип данных</strong></span><span class="sxs-lookup"><span data-stu-id="f2923-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="f2923-108"><strong>Ключ или индекс</strong></span><span class="sxs-lookup"><span data-stu-id="f2923-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="f2923-109"><strong>Details</strong></span><span class="sxs-lookup"><span data-stu-id="f2923-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f2923-110"><strong>конференцедатетиме</strong></span><span class="sxs-lookup"><span data-stu-id="f2923-110"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="f2923-111">dateTime</span><span class="sxs-lookup"><span data-stu-id="f2923-111">dateTime</span></span></p></td>
<td><p><span data-ttu-id="f2923-112">Основной, Внешний</span><span class="sxs-lookup"><span data-stu-id="f2923-112">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="f2923-113">Дата и время начала сеанса.</span><span class="sxs-lookup"><span data-stu-id="f2923-113">Date and time that the session started.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2923-114"><strong>сессионсек</strong></span><span class="sxs-lookup"><span data-stu-id="f2923-114"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="f2923-115">int</span><span class="sxs-lookup"><span data-stu-id="f2923-115">int</span></span></p></td>
<td><p><span data-ttu-id="f2923-116">Основной, Внешний</span><span class="sxs-lookup"><span data-stu-id="f2923-116">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="f2923-117">Порядковый идентификатор, используемый для используется для проведения различия между сеансами, которые начались в один и тот же день и в одно и то же время.</span><span class="sxs-lookup"><span data-stu-id="f2923-117">Sequential identifier used to distinguish between sessions that started on the same date and at the same time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2923-118"><strong>медиалинелабел</strong></span><span class="sxs-lookup"><span data-stu-id="f2923-118"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="f2923-119">tinyint</span><span class="sxs-lookup"><span data-stu-id="f2923-119">tinyint</span></span></p></td>
<td><p><span data-ttu-id="f2923-120">Основной, внешний</span><span class="sxs-lookup"><span data-stu-id="f2923-120">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="f2923-p102">Представляет тип видеоканала, используемого для звонка. Допускаются следующие значения:</span><span class="sxs-lookup"><span data-stu-id="f2923-p102">Represents the type of video line used in the call. Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="f2923-123">0 — звук</span><span class="sxs-lookup"><span data-stu-id="f2923-123">0 – Audio</span></span></p></li>
<li><p><span data-ttu-id="f2923-124">1 — видео</span><span class="sxs-lookup"><span data-stu-id="f2923-124">1 – Video</span></span></p></li>
<li><p><span data-ttu-id="f2923-125">2 — панорамное видео</span><span class="sxs-lookup"><span data-stu-id="f2923-125">2 – Panoramic video</span></span></p></li>
<li><p><span data-ttu-id="f2923-126">3 — общий доступ к приложениям и рабочим столам</span><span class="sxs-lookup"><span data-stu-id="f2923-126">3 –Application/Desktop Sharing</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2923-127"><strong>стреамид</strong></span><span class="sxs-lookup"><span data-stu-id="f2923-127"><strong>StreamID</strong></span></span></p></td>
<td><p><span data-ttu-id="f2923-128">int</span><span class="sxs-lookup"><span data-stu-id="f2923-128">int</span></span></p></td>
<td><p><span data-ttu-id="f2923-129">Primary</span><span class="sxs-lookup"><span data-stu-id="f2923-129">Primary</span></span></p></td>
<td><p><span data-ttu-id="f2923-130">Уникальный идентификатор потока общего доступа к приложениям.</span><span class="sxs-lookup"><span data-stu-id="f2923-130">Unique identifier of the application sharing stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2923-131"><strong>життеринтерарривал</strong></span><span class="sxs-lookup"><span data-stu-id="f2923-131"><strong>JitterInterArrival</strong></span></span></p></td>
<td><p><span data-ttu-id="f2923-132">int</span><span class="sxs-lookup"><span data-stu-id="f2923-132">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f2923-133">Среднее значение колебаний, зарегистрированных между прибытиями пакетов RTP.</span><span class="sxs-lookup"><span data-stu-id="f2923-133">Average jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="f2923-134">(Колебание — это мера &quot;вибрирования&quot; вызова.) Большие значения колебаний обычно вызваны перегрузкой или перегрузкой сервера мультимедиа, что приводит к искажению или потере звука.</span><span class="sxs-lookup"><span data-stu-id="f2923-134">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2923-135"><strong>життеринтерарривалмакс</strong></span><span class="sxs-lookup"><span data-stu-id="f2923-135"><strong>JitterInterArrivalMax</strong></span></span></p></td>
<td><p><span data-ttu-id="f2923-136">int</span><span class="sxs-lookup"><span data-stu-id="f2923-136">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f2923-137">Максимальное значение колебаний, зарегистрированных между прибытиями пакетов RTP.</span><span class="sxs-lookup"><span data-stu-id="f2923-137">Maximum jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="f2923-138">(Колебание — это мера &quot;вибрирования&quot; вызова.) Большие значения колебаний обычно вызваны перегрузкой или перегрузкой сервера мультимедиа, что приводит к искажению или потере звука.</span><span class="sxs-lookup"><span data-stu-id="f2923-138">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2923-139"><strong>Обработки</strong></span><span class="sxs-lookup"><span data-stu-id="f2923-139"><strong>RoundTrip</strong></span></span></p></td>
<td><p><span data-ttu-id="f2923-140">int</span><span class="sxs-lookup"><span data-stu-id="f2923-140">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f2923-p105">Среднее время (в миллисекундах), необходимое для перемещения пакета Real-Time Transport Protocol в другую конечную точку и его возврата. Приемлемым считается время двусторонней передачи, равное 200 мс (или менее).</span><span class="sxs-lookup"><span data-stu-id="f2923-p105">Average amount of (in milliseconds) required for a Real-Time Transport Protocol packet to travel to another endpoint and then back. Round-trip times of 200 milliseconds or less are considered of acceptable quality.</span></span></p>
<p><span data-ttu-id="f2923-p106">Высокие значения времени кругового пути могут быть вызваны международной маршрутизацией звонков; неправильной настройкой кругового пути; или перегрузкой сервера мультимедиа. Высокие значения времени кругового пути приводят к сложностям в двухсторонних аудиобеседах в реальном времени.</span><span class="sxs-lookup"><span data-stu-id="f2923-p106">High round-trip values can be caused by international call routing; a routing misconfiguration; or an overloaded media server. High round-trip times result in difficulties with two-way, real-time audio conversations.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2923-145"><strong>раундтрипмакс</strong></span><span class="sxs-lookup"><span data-stu-id="f2923-145"><strong>RoundTripMax</strong></span></span></p></td>
<td><p><span data-ttu-id="f2923-146">int</span><span class="sxs-lookup"><span data-stu-id="f2923-146">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f2923-p107">Максимальное время (в миллисекундах), необходимое для перемещения пакета Real-Time Transport Protocol в другую конечную точку и его возврата. Приемлемым считается время двусторонней передачи, равное 200 мс (или менее).</span><span class="sxs-lookup"><span data-stu-id="f2923-p107">Maximum amount of (in milliseconds) required for a Real-Time Transport Protocol packet to travel to another endpoint and then back. Round-trip times of 200 milliseconds or less are considered of acceptable quality.</span></span></p>
<p><span data-ttu-id="f2923-p108">Высокие значения времени двусторонней передачи могут быть обусловлены международной маршрутизацией вызовов, неправильной конфигурацией маршрутизации или перегрузкой сервера-посредника. Длительное время двусторонней передачи приводит к возникновению проблем при двусторонних аудиоразговорах в режиме реального времени.</span><span class="sxs-lookup"><span data-stu-id="f2923-p108">High round-trip values can be caused by international call routing; a routing misconfiguration; or an overloaded media server. High round-trip times result in difficulties with two-way, real-time audio conversations.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2923-151"><strong>паккетлоссрате</strong></span><span class="sxs-lookup"><span data-stu-id="f2923-151"><strong>PacketLossRate</strong></span></span></p></td>
<td><p><span data-ttu-id="f2923-152">с плавающей запятой</span><span class="sxs-lookup"><span data-stu-id="f2923-152">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f2923-p109">Средняя частота потери пакетов RTP. (Потеря пакетов происходит, когда пакеты RTP (Real-Time Transport Protocol — протокол, используемый для передачи аудио- и видеопакетов через Интернет) не достигают места назначения.) Высокие показатели потерь обычно вызваны перегрузкой, недостаточной полосой пропускания, помехами или перегрузкой беспроводной сети, а также перегрузкой сервера-посредника. Потеря пакетов обычно приводит к искажению звука или потере аудиосигналов.</span><span class="sxs-lookup"><span data-stu-id="f2923-p109">Average rate of Real-Time Transport Protocol (RTP) packet loss. (Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion; lack of bandwidth; wireless congestion or interference; or an overloaded media server. Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2923-156"><strong>паккетлоссратемакс</strong></span><span class="sxs-lookup"><span data-stu-id="f2923-156"><strong>PacketLossRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="f2923-157">с плавающей запятой</span><span class="sxs-lookup"><span data-stu-id="f2923-157">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f2923-p110">Максимальная частота потери пакетов RTP. (Потеря пакетов происходит, когда пакеты RTP (Real-Time Transport Protocol — протокол, используемый для передачи аудио- и видеопакетов через Интернет) не достигают места назначения.) Высокие показатели потерь обычно вызваны перегрузкой, недостаточной полосой пропускания, помехами или перегрузкой беспроводной сети, а также перегрузкой сервера-посредника. Потеря пакетов обычно приводит к искажению звука или потере аудиосигналов.</span><span class="sxs-lookup"><span data-stu-id="f2923-p110">Maximum rate of Real-Time Transport Protocol (RTP) packet loss. (Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion; lack of bandwidth; wireless congestion or interference; or an overloaded media server. Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2923-161"><strong>паккетутилизатион</strong></span><span class="sxs-lookup"><span data-stu-id="f2923-161"><strong>PacketUtilization</strong></span></span></p></td>
<td><p><span data-ttu-id="f2923-162">int</span><span class="sxs-lookup"><span data-stu-id="f2923-162">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f2923-163">Количество отправленных пакетов.</span><span class="sxs-lookup"><span data-stu-id="f2923-163">Number of packets sent.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2923-164"><strong>Самый полоса пропускания</strong></span><span class="sxs-lookup"><span data-stu-id="f2923-164"><strong>BandwidthEst</strong></span></span></p></td>
<td><p><span data-ttu-id="f2923-165">int</span><span class="sxs-lookup"><span data-stu-id="f2923-165">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f2923-p111">Предполагаемая полоса пропускания для односторонней передачи, доступная в конце сеанса. Измеряется в битах в секунду.</span><span class="sxs-lookup"><span data-stu-id="f2923-p111">Estimated one-way bandwidth available at the end of the session. Reported in bits per second.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2923-168"><strong>аппшарингпайлоаддескриптион</strong></span><span class="sxs-lookup"><span data-stu-id="f2923-168"><strong>AppSharingPayloadDescription</strong></span></span></p></td>
<td><p><span data-ttu-id="f2923-169">int</span><span class="sxs-lookup"><span data-stu-id="f2923-169">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f2923-170">Описание загрузки общего доступа к приложениям.</span><span class="sxs-lookup"><span data-stu-id="f2923-170">Description of the application sharing payload.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2923-171"><strong>релативеоневайтотал</strong></span><span class="sxs-lookup"><span data-stu-id="f2923-171"><strong>RelativeOneWayTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="f2923-172">с плавающей запятой</span><span class="sxs-lookup"><span data-stu-id="f2923-172">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f2923-p112">Общая величина односторонней задержки. Относительная односторонняя задержка измеряет задержку между клиентом и сервером.</span><span class="sxs-lookup"><span data-stu-id="f2923-p112">Total amount of one-way latency. Relative one-way latency measures the delay between the client and the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2923-175"><strong>релативеоневайавераже</strong></span><span class="sxs-lookup"><span data-stu-id="f2923-175"><strong>RelativeOneWayAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="f2923-176">с плавающей запятой</span><span class="sxs-lookup"><span data-stu-id="f2923-176">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f2923-p113">Средняя величина односторонней задержки. Относительная односторонняя задержка измеряет задержку между клиентом и сервером</span><span class="sxs-lookup"><span data-stu-id="f2923-p113">Average amount of one-way latency. Relative one-way latency measures the delay between the client and the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2923-179"><strong>релативеоневаймакс</strong></span><span class="sxs-lookup"><span data-stu-id="f2923-179"><strong>RelativeOneWayMax</strong></span></span></p></td>
<td><p><span data-ttu-id="f2923-180">с плавающей запятой</span><span class="sxs-lookup"><span data-stu-id="f2923-180">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f2923-p114">Максимальная величина односторонней задержки. Относительная односторонняя задержка измеряет задержку между клиентом и сервером</span><span class="sxs-lookup"><span data-stu-id="f2923-p114">Maximum amount of one-way latency. Relative one-way latency measures the delay between the client and the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2923-183"><strong>релативеоневайбурстоккурренцес</strong></span><span class="sxs-lookup"><span data-stu-id="f2923-183"><strong>RelativeOneWayBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="f2923-184">int</span><span class="sxs-lookup"><span data-stu-id="f2923-184">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f2923-p115">Общее число повторов пакетов в одну сторону. "Пакетная" передача представляет собой передачу, при которой данные передаются посредством случайных пакетов, а не в виде устойчивого потока. С помощью этой метрики измеряется поток данных между клиентом и сервером.</span><span class="sxs-lookup"><span data-stu-id="f2923-p115">Total one-way burst occurrences. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream. This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2923-188"><strong>релативеоневайбурстденсити</strong></span><span class="sxs-lookup"><span data-stu-id="f2923-188"><strong>RelativeOneWayBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="f2923-189">с плавающей запятой</span><span class="sxs-lookup"><span data-stu-id="f2923-189">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f2923-p116">Общая плотность пакетов в одну сторону. "Пакетная" передача представляет собой передачу, при которой данные передаются посредством случайных пакетов, а не в виде устойчивого потока. С помощью этой метрики измеряется поток данных между клиентом и сервером.</span><span class="sxs-lookup"><span data-stu-id="f2923-p116">Total one-way burst density. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream. This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2923-193"><strong>релативеоневайбурстдуратион</strong></span><span class="sxs-lookup"><span data-stu-id="f2923-193"><strong>RelativeOneWayBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="f2923-194">с плавающей запятой</span><span class="sxs-lookup"><span data-stu-id="f2923-194">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f2923-p117">Общая длительность пакетов в одну сторону. "Пакетная" передача представляет собой передачу, при которой данные передаются посредством случайных пакетов, а не в виде устойчивого потока. С помощью этой метрики измеряется поток данных между клиентом и сервером.</span><span class="sxs-lookup"><span data-stu-id="f2923-p117">Total one-way burst duration. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream. This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2923-198"><strong>релативеоневайгапоккурренцес</strong></span><span class="sxs-lookup"><span data-stu-id="f2923-198"><strong>RelativeOneWayGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="f2923-199">int</span><span class="sxs-lookup"><span data-stu-id="f2923-199">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f2923-p118">Общее число повторов разрывов в одну сторону. "Пакетная" передача представляет собой передачу, при которой данные передаются посредством случайных пакетов, а не в виде устойчивого потока; разрывы указывают задержку между этими пакетами. С помощью данной метрики измеряется поток данных между клиентом и сервером.</span><span class="sxs-lookup"><span data-stu-id="f2923-p118">Total one-way gap occurrences. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts. This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2923-203"><strong>релативеоневайгапденсити</strong></span><span class="sxs-lookup"><span data-stu-id="f2923-203"><strong>RelativeOneWayGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="f2923-204">с плавающей запятой</span><span class="sxs-lookup"><span data-stu-id="f2923-204">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f2923-p119">Общая плотность разрывов в одну сторону. "Пакетная" передача представляет собой передачу, при которой данные передаются посредством случайных пакетов, а не в виде устойчивого потока; разрывы указывают задержку между этими пакетами. С помощью данной метрики измеряется поток данных между клиентом и сервером.</span><span class="sxs-lookup"><span data-stu-id="f2923-p119">Total one-way gap density. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts. This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2923-208"><strong>релативеоневайгапдуратион</strong></span><span class="sxs-lookup"><span data-stu-id="f2923-208"><strong>RelativeOneWayGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="f2923-209">с плавающей запятой</span><span class="sxs-lookup"><span data-stu-id="f2923-209">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f2923-p120">Общая длительность разрывов в одну сторону. "Пакетная" передача представляет собой передачу, при которой данные передаются посредством случайных пакетов, а не в виде устойчивого потока; разрывы указывают задержку между этими пакетами. С помощью данной метрики измеряется поток данных между клиентом и сервером.</span><span class="sxs-lookup"><span data-stu-id="f2923-p120">Total one-way gap duration. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts. This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2923-213"><strong>аппликатионшарингтипе</strong></span><span class="sxs-lookup"><span data-stu-id="f2923-213"><strong>ApplicationSharingType</strong></span></span></p></td>
<td><p><span data-ttu-id="f2923-214">varChar (256)</span><span class="sxs-lookup"><span data-stu-id="f2923-214">varChar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f2923-215">Роль приложения (средство предоставления доступа и средство просмотра) и тип содержимого.</span><span class="sxs-lookup"><span data-stu-id="f2923-215">Application role (Sharer or Viewer) and content type.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2923-216"><strong>рдптилепроцессинглатенцитотал</strong></span><span class="sxs-lookup"><span data-stu-id="f2923-216"><strong>RDPTileProcessingLatencyTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="f2923-217">с плавающей запятой</span><span class="sxs-lookup"><span data-stu-id="f2923-217">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f2923-p121">Общее время обработки заголовков RDP. Чем больше общее значение, тем длиннее задержки при просмотре.</span><span class="sxs-lookup"><span data-stu-id="f2923-p121">Total processing time for remote desktop protocol (RDP) tiles. A higher total equates to a longer delay in the viewing experience.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2923-220"><strong>рдптилепроцессинглатенциавераже</strong></span><span class="sxs-lookup"><span data-stu-id="f2923-220"><strong>RDPTileProcessingLatencyAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="f2923-221">с плавающей запятой</span><span class="sxs-lookup"><span data-stu-id="f2923-221">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f2923-p122">Среднее время обработки заголовков RDP. Чем больше общее значение, тем длиннее задержки при просмотре.</span><span class="sxs-lookup"><span data-stu-id="f2923-p122">Average processing time for remote desktop protocol (RDP) tiles. A higher total equates to a longer delay in the viewing experience.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2923-224"><strong>рдптилепроцессинглатенцимакс</strong></span><span class="sxs-lookup"><span data-stu-id="f2923-224"><strong>RDPTileProcessingLatencyMax</strong></span></span></p></td>
<td><p><span data-ttu-id="f2923-225">с плавающей запятой</span><span class="sxs-lookup"><span data-stu-id="f2923-225">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f2923-p123">Максимальное время обработки заголовков RDP. Чем больше общее значение, тем длиннее задержки при просмотре.</span><span class="sxs-lookup"><span data-stu-id="f2923-p123">Maximum processing time for remote desktop protocol (RDP) tiles. A higher total equates to a longer delay in the viewing experience.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2923-228"><strong>рдптилепроцессинглатенцибурстоккурренцес</strong></span><span class="sxs-lookup"><span data-stu-id="f2923-228"><strong>RDPTileProcessingLatencyBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="f2923-229">int</span><span class="sxs-lookup"><span data-stu-id="f2923-229">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f2923-p124">Повторы пакетов во время обработки заголовков RDP. Передача с повторами пакетов — это передача, при которой данные передаются случайными пакетами, а не равномерным потоком.</span><span class="sxs-lookup"><span data-stu-id="f2923-p124">Burst occurrences in the processing time for remote desktop protocol (RDP) tiles. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2923-232"><strong>рдптилепроцессинглатенцибурстденсити</strong></span><span class="sxs-lookup"><span data-stu-id="f2923-232"><strong>RDPTileProcessingLatencyBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="f2923-233">с плавающей запятой</span><span class="sxs-lookup"><span data-stu-id="f2923-233">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f2923-p125">Плотность пакетов во время обработки заголовков RDP. Передача с повторами пакетов — это передача, при которой данные передаются случайными пакетами, а не равномерным потоком.</span><span class="sxs-lookup"><span data-stu-id="f2923-p125">Burst density in the processing time for remote desktop protocol (RDP) tiles. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2923-236"><strong>рдптилепроцессинглатенцибурстдуратион</strong></span><span class="sxs-lookup"><span data-stu-id="f2923-236"><strong>RDPTileProcessingLatencyBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="f2923-237">с плавающей запятой</span><span class="sxs-lookup"><span data-stu-id="f2923-237">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f2923-p126">Продолжительность пакетной передачи во время обработки заголовков RDP. Передача с повторами пакетов — это передача, при которой данные передаются случайными пакетами, а не равномерным потоком.</span><span class="sxs-lookup"><span data-stu-id="f2923-p126">Burst duration in the processing time for remote desktop protocol (RDP) tiles. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2923-240"><strong>рдптилепроцессинглатенцигапоккурренцес</strong></span><span class="sxs-lookup"><span data-stu-id="f2923-240"><strong>RDPTileProcessingLatencyGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="f2923-241">int</span><span class="sxs-lookup"><span data-stu-id="f2923-241">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f2923-242">Разрывы во время обработки заголовков RDP.</span><span class="sxs-lookup"><span data-stu-id="f2923-242">Gap occurrences in the processing time for remote desktop protocol (RDP) tiles.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2923-243"><strong>рдптилепроцессинглатенцигапденсити</strong></span><span class="sxs-lookup"><span data-stu-id="f2923-243"><strong>RDPTileProcessingLatencyGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="f2923-244">с плавающей запятой</span><span class="sxs-lookup"><span data-stu-id="f2923-244">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f2923-p127">Плотность разрывов во время обработки заголовков RDP. Чем ниже плотность разрывов, тем лучше просмотр.</span><span class="sxs-lookup"><span data-stu-id="f2923-p127">Gap density in the processing time for remote desktop protocol (RDP) tiles. Low gap density equates to a better viewing experience.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2923-247"><strong>рдптилепроцессинглатенцигапдуратион</strong></span><span class="sxs-lookup"><span data-stu-id="f2923-247"><strong>RDPTileProcessingLatencyGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="f2923-248">с плавающей запятой</span><span class="sxs-lookup"><span data-stu-id="f2923-248">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f2923-p128">Продолжительность разрывов во время обработки заголовков RDP. Чем ниже продолжительность разрывов, тем лучше просмотр.</span><span class="sxs-lookup"><span data-stu-id="f2923-p128">Gap duration in the processing time for remote desktop protocol (RDP) tiles. Short gap durations equate to a better viewing experience.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2923-251"><strong>каптуретилератетотал</strong></span><span class="sxs-lookup"><span data-stu-id="f2923-251"><strong>CaptureTileRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="f2923-252">с плавающей запятой</span><span class="sxs-lookup"><span data-stu-id="f2923-252">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f2923-253">Общая частота захвата заголовков (заголовков в секунду).</span><span class="sxs-lookup"><span data-stu-id="f2923-253">Total rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2923-254"><strong>каптуретилератеавераже</strong></span><span class="sxs-lookup"><span data-stu-id="f2923-254"><strong>CaptureTileRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="f2923-255">с плавающей запятой</span><span class="sxs-lookup"><span data-stu-id="f2923-255">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f2923-256">Средняя частота захвата заголовков (заголовков в секунду).</span><span class="sxs-lookup"><span data-stu-id="f2923-256">Average rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2923-257"><strong>каптуретилератемакс</strong></span><span class="sxs-lookup"><span data-stu-id="f2923-257"><strong>CaptureTileRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="f2923-258">с плавающей запятой</span><span class="sxs-lookup"><span data-stu-id="f2923-258">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f2923-259">Максимальная частота захвата заголовков (заголовков в секунду).</span><span class="sxs-lookup"><span data-stu-id="f2923-259">Maximum rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2923-260"><strong>каптуретилератебурстоккурренцес</strong></span><span class="sxs-lookup"><span data-stu-id="f2923-260"><strong>CaptureTileRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="f2923-261">целое</span><span class="sxs-lookup"><span data-stu-id="f2923-261">in t</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f2923-262">Повторы пакетов в частоте захвата заголовков (заголовков в секунду).</span><span class="sxs-lookup"><span data-stu-id="f2923-262">Burst occurrences in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2923-263"><strong>каптуретилератебурстденсити</strong></span><span class="sxs-lookup"><span data-stu-id="f2923-263"><strong>CaptureTileRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="f2923-264">с плавающей запятой</span><span class="sxs-lookup"><span data-stu-id="f2923-264">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f2923-265">Плотность повторов пакетов в частоте захвата заголовков (заголовков в секунду).</span><span class="sxs-lookup"><span data-stu-id="f2923-265">Burst density in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2923-266"><strong>каптуретилератебурстдуратион</strong></span><span class="sxs-lookup"><span data-stu-id="f2923-266"><strong>CaptureTileRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="f2923-267">с плавающей запятой</span><span class="sxs-lookup"><span data-stu-id="f2923-267">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f2923-268">Продолжительность повторов пакетов в частоте захвата заголовков (заголовков в секунду).</span><span class="sxs-lookup"><span data-stu-id="f2923-268">Burst duration in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2923-269"><strong>каптуретилератегапоккурренцес</strong></span><span class="sxs-lookup"><span data-stu-id="f2923-269"><strong>CaptureTileRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="f2923-270">int</span><span class="sxs-lookup"><span data-stu-id="f2923-270">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f2923-271">Разрывы в частоте захвата заголовков (заголовков в секунду).</span><span class="sxs-lookup"><span data-stu-id="f2923-271">Gap occurrences in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2923-272"><strong>каптуретилератегапденсити</strong></span><span class="sxs-lookup"><span data-stu-id="f2923-272"><strong>CaptureTileRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="f2923-273">с плавающей запятой</span><span class="sxs-lookup"><span data-stu-id="f2923-273">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f2923-274">Плотность разрывов в частоте захвата заголовков (заголовков в секунду).</span><span class="sxs-lookup"><span data-stu-id="f2923-274">Gap density in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2923-275"><strong>каптуретилератегапдуратион</strong></span><span class="sxs-lookup"><span data-stu-id="f2923-275"><strong>CaptureTileRateGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="f2923-276">с плавающей запятой</span><span class="sxs-lookup"><span data-stu-id="f2923-276">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f2923-277">Продолжительность разрывов в частоте захвата заголовков (заголовков в секунду).</span><span class="sxs-lookup"><span data-stu-id="f2923-277">Gap duration in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2923-278"><strong>споиледтилеперценттотал</strong></span><span class="sxs-lookup"><span data-stu-id="f2923-278"><strong>SpoiledTilePercentTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="f2923-279">с плавающей запятой</span><span class="sxs-lookup"><span data-stu-id="f2923-279">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f2923-280">Общее процентное соотношение контента, не достигшего средства просмотра и отброшенного или перезаписанного новым контентом.</span><span class="sxs-lookup"><span data-stu-id="f2923-280">Total percentage of the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2923-281"><strong>споиледтилеперцентавераже</strong></span><span class="sxs-lookup"><span data-stu-id="f2923-281"><strong>SpoiledTilePercentAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="f2923-282">с плавающей запятой</span><span class="sxs-lookup"><span data-stu-id="f2923-282">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f2923-283">Среднее процентное соотношение контента, не достигшего средства просмотра и отброшенного или перезаписанного новым контентом.</span><span class="sxs-lookup"><span data-stu-id="f2923-283">Average percentage of the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2923-284"><strong>споиледтилеперцентмакс</strong></span><span class="sxs-lookup"><span data-stu-id="f2923-284"><strong>SpoiledTilePercentMax</strong></span></span></p></td>
<td><p><span data-ttu-id="f2923-285">с плавающей запятой</span><span class="sxs-lookup"><span data-stu-id="f2923-285">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f2923-286">Максимальное процентное соотношение контента, не достигшего средства просмотра и отброшенного или перезаписанного новым контентом.</span><span class="sxs-lookup"><span data-stu-id="f2923-286">Maximum percentage of the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2923-287"><strong>споиледтилеперцентбурстоккурренцес</strong></span><span class="sxs-lookup"><span data-stu-id="f2923-287"><strong>SpoiledTilePercentBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="f2923-288">int</span><span class="sxs-lookup"><span data-stu-id="f2923-288">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f2923-289">Повторы пакетов контента, не достигшего средства просмотра и отброшенного или перезаписанного новым контентом.</span><span class="sxs-lookup"><span data-stu-id="f2923-289">Burst occurrences for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2923-290"><strong>споиледтилеперцентбурстденсити</strong></span><span class="sxs-lookup"><span data-stu-id="f2923-290"><strong>SpoiledTilePercentBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="f2923-291">с плавающей запятой</span><span class="sxs-lookup"><span data-stu-id="f2923-291">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f2923-292">Плотность повторов пакетов контента, не достигшего средства просмотра и отброшенного или перезаписанного новым контентом.</span><span class="sxs-lookup"><span data-stu-id="f2923-292">Burst density for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2923-293"><strong>споиледтилеперцентбурстдуратион</strong></span><span class="sxs-lookup"><span data-stu-id="f2923-293"><strong>SpoiledTilePercentBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="f2923-294">с плавающей запятой</span><span class="sxs-lookup"><span data-stu-id="f2923-294">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f2923-295">Продолжительность повторов пакетов контента, не достигшего средства просмотра и отброшенного или перезаписанного новым контентом.</span><span class="sxs-lookup"><span data-stu-id="f2923-295">Burst duration for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2923-296"><strong>споиледтилеперцентгапоккурренцес</strong></span><span class="sxs-lookup"><span data-stu-id="f2923-296"><strong>SpoiledTilePercentGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="f2923-297">int</span><span class="sxs-lookup"><span data-stu-id="f2923-297">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f2923-298">Разрывы контента, не достигшего средства просмотра и отброшенного или перезаписанного новым контентом.</span><span class="sxs-lookup"><span data-stu-id="f2923-298">Gap occurrences for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2923-299"><strong>споиледтилеперцентгапденсити</strong></span><span class="sxs-lookup"><span data-stu-id="f2923-299"><strong>SpoiledTilePercentGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="f2923-300">с плавающей запятой</span><span class="sxs-lookup"><span data-stu-id="f2923-300">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f2923-301">Плотность разрывов контента, не достигшего средства просмотра и отброшенного или перезаписанного новым контентом.</span><span class="sxs-lookup"><span data-stu-id="f2923-301">Gap density for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2923-302"><strong>споиледтилеперцентгапдуратион</strong></span><span class="sxs-lookup"><span data-stu-id="f2923-302"><strong>SpoiledTilePercentGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="f2923-303">с плавающей запятой</span><span class="sxs-lookup"><span data-stu-id="f2923-303">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f2923-304">Продолжительность разрывов контента, не достигшего средства просмотра и отброшенного или перезаписанного новым контентом.</span><span class="sxs-lookup"><span data-stu-id="f2923-304">Gap duration for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2923-305"><strong>скрапингфрамератетотал</strong></span><span class="sxs-lookup"><span data-stu-id="f2923-305"><strong>ScrapingFrameRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="f2923-306">с плавающей запятой</span><span class="sxs-lookup"><span data-stu-id="f2923-306">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f2923-307">Общее количество кадров, исключенных из источника графики.</span><span class="sxs-lookup"><span data-stu-id="f2923-307">Total number of frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2923-308"><strong>скрапингфрамератеавераже</strong></span><span class="sxs-lookup"><span data-stu-id="f2923-308"><strong>ScrapingFrameRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="f2923-309">с плавающей запятой</span><span class="sxs-lookup"><span data-stu-id="f2923-309">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f2923-310">Среднее количество кадров, исключенных из источника графики.</span><span class="sxs-lookup"><span data-stu-id="f2923-310">Average number of frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2923-311"><strong>скрапингфрамератемакс</strong></span><span class="sxs-lookup"><span data-stu-id="f2923-311"><strong>ScrapingFrameRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="f2923-312">с плавающей запятой</span><span class="sxs-lookup"><span data-stu-id="f2923-312">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f2923-313">Максимальное количество кадров, исключенных из источника графики.</span><span class="sxs-lookup"><span data-stu-id="f2923-313">Maximum number of frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2923-314"><strong>скрапингфрамератебурстоккурренцес</strong></span><span class="sxs-lookup"><span data-stu-id="f2923-314"><strong>ScrapingFrameRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="f2923-315">int</span><span class="sxs-lookup"><span data-stu-id="f2923-315">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f2923-316">Повторы пакетов в кадрах, исключенных из источника графики.</span><span class="sxs-lookup"><span data-stu-id="f2923-316">Burst occurrences in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2923-317"><strong>скрапингфрамератебурстденсити</strong></span><span class="sxs-lookup"><span data-stu-id="f2923-317"><strong>ScrapingFrameRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="f2923-318">с плавающей запятой</span><span class="sxs-lookup"><span data-stu-id="f2923-318">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f2923-319">Плотность повторов пакетов в кадрах, исключенных из источника графики.</span><span class="sxs-lookup"><span data-stu-id="f2923-319">Burst density in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2923-320"><strong>скрапингфрамератебурстдуратион</strong></span><span class="sxs-lookup"><span data-stu-id="f2923-320"><strong>ScrapingFrameRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="f2923-321">с плавающей запятой</span><span class="sxs-lookup"><span data-stu-id="f2923-321">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f2923-322">Продолжительность повторов пакетов в кадрах, исключенных из источника графики.</span><span class="sxs-lookup"><span data-stu-id="f2923-322">Burst duration in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2923-323"><strong>скрапингфрамератегапоккурренцес</strong></span><span class="sxs-lookup"><span data-stu-id="f2923-323"><strong>ScrapingFrameRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="f2923-324">int</span><span class="sxs-lookup"><span data-stu-id="f2923-324">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f2923-325">Разрывы в кадрах, исключенных из источника графики.</span><span class="sxs-lookup"><span data-stu-id="f2923-325">Gap occurrences in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2923-326"><strong>скрапингфрамератегапденсити</strong></span><span class="sxs-lookup"><span data-stu-id="f2923-326"><strong>ScrapingFrameRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="f2923-327">с плавающей запятой</span><span class="sxs-lookup"><span data-stu-id="f2923-327">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f2923-328">Плотность разрывов в кадрах, исключенных из источника графики.</span><span class="sxs-lookup"><span data-stu-id="f2923-328">Gap density in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2923-329"><strong>скрапингфрамератегапдуратион</strong></span><span class="sxs-lookup"><span data-stu-id="f2923-329"><strong>ScrapingFrameRateGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="f2923-330">с плавающей запятой</span><span class="sxs-lookup"><span data-stu-id="f2923-330">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f2923-331">Продолжительность разрывов в кадрах, исключенных из источника графики.</span><span class="sxs-lookup"><span data-stu-id="f2923-331">Gap duration in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2923-332"><strong>инкомингтилератетотал</strong></span><span class="sxs-lookup"><span data-stu-id="f2923-332"><strong>IncomingTileRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="f2923-333">с плавающей запятой</span><span class="sxs-lookup"><span data-stu-id="f2923-333">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f2923-334">Общая частота кадров, получаемых средством просмотра.</span><span class="sxs-lookup"><span data-stu-id="f2923-334">Total incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2923-335"><strong>инкомингтилератеавераже</strong></span><span class="sxs-lookup"><span data-stu-id="f2923-335"><strong>IncomingTileRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="f2923-336">с плавающей запятой</span><span class="sxs-lookup"><span data-stu-id="f2923-336">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f2923-337">Средняя частота кадров, получаемых средством просмотра.</span><span class="sxs-lookup"><span data-stu-id="f2923-337">Average incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2923-338"><strong>инкомингтилератемакс</strong></span><span class="sxs-lookup"><span data-stu-id="f2923-338"><strong>IncomingTileRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="f2923-339">с плавающей запятой</span><span class="sxs-lookup"><span data-stu-id="f2923-339">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f2923-340">Максимальная частота заголовков, получаемых средством просмотра.</span><span class="sxs-lookup"><span data-stu-id="f2923-340">Maximum incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2923-341"><strong>инкомингтилератебурстоккурренцес</strong></span><span class="sxs-lookup"><span data-stu-id="f2923-341"><strong>IncomingTileRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="f2923-342">int</span><span class="sxs-lookup"><span data-stu-id="f2923-342">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f2923-343">Повторы пакетов относительно частоты входящих заголовков, получаемых средством просмотра.</span><span class="sxs-lookup"><span data-stu-id="f2923-343">Burst occurrences in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2923-344"><strong>инкомингтилератебурстденсити</strong></span><span class="sxs-lookup"><span data-stu-id="f2923-344"><strong>IncomingTileRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="f2923-345">с плавающей запятой</span><span class="sxs-lookup"><span data-stu-id="f2923-345">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f2923-346">Плотность повторов пакетов относительно частоты входящих заголовков, получаемых средством просмотра.</span><span class="sxs-lookup"><span data-stu-id="f2923-346">Burst density in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2923-347"><strong>инкомингтилератебурстдуратион</strong></span><span class="sxs-lookup"><span data-stu-id="f2923-347"><strong>IncomingTileRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="f2923-348">с плавающей запятой</span><span class="sxs-lookup"><span data-stu-id="f2923-348">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f2923-349">Продолжительность повторов пакетов относительно частоты входящих заголовков, получаемых средством просмотра.</span><span class="sxs-lookup"><span data-stu-id="f2923-349">Burst duration in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2923-350"><strong>инкомингтилератегапоккурренцес</strong></span><span class="sxs-lookup"><span data-stu-id="f2923-350"><strong>IncomingTileRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="f2923-351">int</span><span class="sxs-lookup"><span data-stu-id="f2923-351">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f2923-352">Разрывы относительно частоты входящих заголовков, получаемых средством просмотра.</span><span class="sxs-lookup"><span data-stu-id="f2923-352">Gap occurrences in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2923-353"><strong>инкомингтилератегапденсити</strong></span><span class="sxs-lookup"><span data-stu-id="f2923-353"><strong>IncomingTileRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="f2923-354">с плавающей запятой</span><span class="sxs-lookup"><span data-stu-id="f2923-354">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f2923-355">Плотность разрывов относительно частоты входящих заголовков, получаемых средством просмотра.</span><span class="sxs-lookup"><span data-stu-id="f2923-355">Gap density in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2923-356"><strong>инкомингтилератегапдуратион</strong></span><span class="sxs-lookup"><span data-stu-id="f2923-356"><strong>IncomingTileRateGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="f2923-357">с плавающей запятой</span><span class="sxs-lookup"><span data-stu-id="f2923-357">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f2923-358">Продолжительность разрывов относительно частоты входящих заголовков, получаемых средством просмотра.</span><span class="sxs-lookup"><span data-stu-id="f2923-358">Gap duration in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2923-359"><strong>инкомингфрамератетотал</strong></span><span class="sxs-lookup"><span data-stu-id="f2923-359"><strong>IncomingFrameRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="f2923-360">с плавающей запятой</span><span class="sxs-lookup"><span data-stu-id="f2923-360">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f2923-361">Общая частота кадров, получаемых средством просмотра.</span><span class="sxs-lookup"><span data-stu-id="f2923-361">Total incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2923-362"><strong>инкомингфрамератеавераже</strong></span><span class="sxs-lookup"><span data-stu-id="f2923-362"><strong>IncomingFrameRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="f2923-363">с плавающей запятой</span><span class="sxs-lookup"><span data-stu-id="f2923-363">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f2923-364">Средняя частота кадров, получаемых средством просмотра.</span><span class="sxs-lookup"><span data-stu-id="f2923-364">Average incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2923-365"><strong>инкомингфрамератемакс</strong></span><span class="sxs-lookup"><span data-stu-id="f2923-365"><strong>IncomingFrameRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="f2923-366">с плавающей запятой</span><span class="sxs-lookup"><span data-stu-id="f2923-366">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f2923-367">Максимальная входящая частота кадров, получаемых средством просмотра.</span><span class="sxs-lookup"><span data-stu-id="f2923-367">Maximum incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2923-368"><strong>инкомингфрамератебурстоккурренцес</strong></span><span class="sxs-lookup"><span data-stu-id="f2923-368"><strong>IncomingFrameRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="f2923-369">int</span><span class="sxs-lookup"><span data-stu-id="f2923-369">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f2923-370">Повторы пакетов относительно частоты входящих кадров, получаемых средством просмотра.</span><span class="sxs-lookup"><span data-stu-id="f2923-370">Burst occurrences in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2923-371"><strong>инкомингфрамератебурстденсити</strong></span><span class="sxs-lookup"><span data-stu-id="f2923-371"><strong>IncomingFrameRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="f2923-372">с плавающей запятой</span><span class="sxs-lookup"><span data-stu-id="f2923-372">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f2923-373">Плотность повторов пакетов относительно частоты входящих кадров, получаемых средством просмотра.</span><span class="sxs-lookup"><span data-stu-id="f2923-373">Burst density in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2923-374"><strong>инкомингфрамератебурстдуратион</strong></span><span class="sxs-lookup"><span data-stu-id="f2923-374"><strong>IncomingFrameRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="f2923-375">с плавающей запятой</span><span class="sxs-lookup"><span data-stu-id="f2923-375">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f2923-376">Продолжительность повторов пакетов относительно частоты входящих кадров, получаемых средством просмотра.</span><span class="sxs-lookup"><span data-stu-id="f2923-376">Burst duration in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2923-377"><strong>инкомингфрамератегапоккурренцес</strong></span><span class="sxs-lookup"><span data-stu-id="f2923-377"><strong>IncomingFrameRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="f2923-378">int</span><span class="sxs-lookup"><span data-stu-id="f2923-378">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f2923-379">Разрывы относительно частоты входящих кадров, получаемых средством просмотра.</span><span class="sxs-lookup"><span data-stu-id="f2923-379">Gap occurrences in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2923-380"><strong>инкомингфрамератегапденсити</strong></span><span class="sxs-lookup"><span data-stu-id="f2923-380"><strong>IncomingFrameRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="f2923-381">с плавающей запятой</span><span class="sxs-lookup"><span data-stu-id="f2923-381">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f2923-382">Плотность разрывов относительно частоты входящих кадров, получаемых средством просмотра.</span><span class="sxs-lookup"><span data-stu-id="f2923-382">Gap density in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2923-383"><strong>инкомингфрамератедуратион</strong></span><span class="sxs-lookup"><span data-stu-id="f2923-383"><strong>IncomingFrameRateDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="f2923-384">с плавающей запятой</span><span class="sxs-lookup"><span data-stu-id="f2923-384">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f2923-385">Продолжительность разрывов относительно частоты входящих кадров, получаемых средством просмотра.</span><span class="sxs-lookup"><span data-stu-id="f2923-385">Gap duration in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2923-386"><strong>аутгоингтилератетотал</strong></span><span class="sxs-lookup"><span data-stu-id="f2923-386"><strong>OutgoingTileRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="f2923-387">с плавающей запятой</span><span class="sxs-lookup"><span data-stu-id="f2923-387">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f2923-388">Общая частота исходящих заголовков для отправителя.</span><span class="sxs-lookup"><span data-stu-id="f2923-388">Total outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2923-389"><strong>аутгоингтилератеавераже</strong></span><span class="sxs-lookup"><span data-stu-id="f2923-389"><strong>OutgoingTileRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="f2923-390">с плавающей запятой</span><span class="sxs-lookup"><span data-stu-id="f2923-390">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f2923-391">Средняя частота исходящих заголовков для отправителя.</span><span class="sxs-lookup"><span data-stu-id="f2923-391">Average outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2923-392"><strong>аутгоингтилератемакс</strong></span><span class="sxs-lookup"><span data-stu-id="f2923-392"><strong>OutgoingTileRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="f2923-393">с плавающей запятой</span><span class="sxs-lookup"><span data-stu-id="f2923-393">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f2923-394">Максимальная частота исходящих заголовков для отправителя.</span><span class="sxs-lookup"><span data-stu-id="f2923-394">Maximum outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2923-395"><strong>аутгоингтилератебурстоккурренцес</strong></span><span class="sxs-lookup"><span data-stu-id="f2923-395"><strong>OutgoingTileRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="f2923-396">int</span><span class="sxs-lookup"><span data-stu-id="f2923-396">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f2923-397">Повторы пакетов относительно частоты исходящих заголовков для отправителя.</span><span class="sxs-lookup"><span data-stu-id="f2923-397">Burst occurrences in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2923-398"><strong>аутгоингтилератебурстденсити</strong></span><span class="sxs-lookup"><span data-stu-id="f2923-398"><strong>OutgoingTileRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="f2923-399">с плавающей запятой</span><span class="sxs-lookup"><span data-stu-id="f2923-399">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f2923-400">Плотность повторов пакетов относительно частоты исходящих заголовков для отправителя.</span><span class="sxs-lookup"><span data-stu-id="f2923-400">Burst density in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2923-401"><strong>аутгоингтилератебурстдуратион</strong></span><span class="sxs-lookup"><span data-stu-id="f2923-401"><strong>OutgoingTileRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="f2923-402">с плавающей запятой</span><span class="sxs-lookup"><span data-stu-id="f2923-402">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f2923-403">Продолжительность повторов пакетов относительно частоты исходящих заголовков для отправителя.</span><span class="sxs-lookup"><span data-stu-id="f2923-403">Burst duration in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2923-404"><strong>аутгоингтилератегапоккурренцес</strong></span><span class="sxs-lookup"><span data-stu-id="f2923-404"><strong>OutgoingTileRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="f2923-405">int</span><span class="sxs-lookup"><span data-stu-id="f2923-405">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f2923-406">Разрывы относительно частоты исходящих заголовков для отправителя.</span><span class="sxs-lookup"><span data-stu-id="f2923-406">Gap occurrences in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2923-407"><strong>аутгоингтилератегапденсити</strong></span><span class="sxs-lookup"><span data-stu-id="f2923-407"><strong>OutgoingTileRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="f2923-408">с плавающей запятой</span><span class="sxs-lookup"><span data-stu-id="f2923-408">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f2923-409">Плотность разрывов относительно частоты исходящих заголовков для отправителя.</span><span class="sxs-lookup"><span data-stu-id="f2923-409">Gap density in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2923-410"><strong>аутгоингтилератегапдуратион</strong></span><span class="sxs-lookup"><span data-stu-id="f2923-410"><strong>OutgoingTileRateGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="f2923-411">с плавающей запятой</span><span class="sxs-lookup"><span data-stu-id="f2923-411">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f2923-412">Продолжительность разрывов относительно частоты исходящих заголовков для отправителя.</span><span class="sxs-lookup"><span data-stu-id="f2923-412">Gap duration in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2923-413"><strong>аутгоингфрамератетотал</strong></span><span class="sxs-lookup"><span data-stu-id="f2923-413"><strong>OutgoingFrameRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="f2923-414">с плавающей запятой</span><span class="sxs-lookup"><span data-stu-id="f2923-414">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f2923-415">Общая частота исходящих кадров для отправителя.</span><span class="sxs-lookup"><span data-stu-id="f2923-415">Total outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2923-416"><strong>аутгоингфрамератеавераже</strong></span><span class="sxs-lookup"><span data-stu-id="f2923-416"><strong>OutgoingFrameRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="f2923-417">с плавающей запятой</span><span class="sxs-lookup"><span data-stu-id="f2923-417">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f2923-418">Средняя частота исходящих кадров для отправителя.</span><span class="sxs-lookup"><span data-stu-id="f2923-418">average outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2923-419"><strong>аутгоингфрамератемакс</strong></span><span class="sxs-lookup"><span data-stu-id="f2923-419"><strong>OutgoingFrameRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="f2923-420">с плавающей запятой</span><span class="sxs-lookup"><span data-stu-id="f2923-420">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f2923-421">Максимальная частота исходящих кадров для отправителя.</span><span class="sxs-lookup"><span data-stu-id="f2923-421">Maximum outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2923-422"><strong>аутгоингфрамератебурстоккурренцес</strong></span><span class="sxs-lookup"><span data-stu-id="f2923-422"><strong>OutgoingFrameRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="f2923-423">int</span><span class="sxs-lookup"><span data-stu-id="f2923-423">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f2923-424">Повторы пакетов относительно частоты исходящих кадров для отправителя.</span><span class="sxs-lookup"><span data-stu-id="f2923-424">Burst occurrences in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2923-425"><strong>аутгоингфрамератебурстденсити</strong></span><span class="sxs-lookup"><span data-stu-id="f2923-425"><strong>OutgoingFrameRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="f2923-426">с плавающей запятой</span><span class="sxs-lookup"><span data-stu-id="f2923-426">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f2923-427">Плотность повторов пакетов относительно частоты исходящих кадров для отправителя.</span><span class="sxs-lookup"><span data-stu-id="f2923-427">Burst density in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2923-428"><strong>аутгоингфрамератебурстдуратион</strong></span><span class="sxs-lookup"><span data-stu-id="f2923-428"><strong>OutgoingFrameRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="f2923-429">с плавающей запятой</span><span class="sxs-lookup"><span data-stu-id="f2923-429">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f2923-430">Продолжительность повторов пакетов относительно частоты исходящих кадров для отправителя.</span><span class="sxs-lookup"><span data-stu-id="f2923-430">Burst duration in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2923-431"><strong>аутгоингфрамератегапоккурренцес</strong></span><span class="sxs-lookup"><span data-stu-id="f2923-431"><strong>OutgoingFrameRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="f2923-432">int</span><span class="sxs-lookup"><span data-stu-id="f2923-432">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f2923-433">Разрывы относительно частоты исходящих кадров для отправителя.</span><span class="sxs-lookup"><span data-stu-id="f2923-433">Gap occurrences in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2923-434"><strong>аутгоингфрамератегапденсити</strong></span><span class="sxs-lookup"><span data-stu-id="f2923-434"><strong>OutgoingFrameRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="f2923-435">с плавающей запятой</span><span class="sxs-lookup"><span data-stu-id="f2923-435">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f2923-436">Плотность разрывов относительно частоты исходящих кадров для отправителя.</span><span class="sxs-lookup"><span data-stu-id="f2923-436">Gap density in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2923-437"><strong>аутгоингфрамератегапдуратион</strong></span><span class="sxs-lookup"><span data-stu-id="f2923-437"><strong>OutgoingFrameRateGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="f2923-438">с плавающей запятой</span><span class="sxs-lookup"><span data-stu-id="f2923-438">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f2923-439">Продолжительность разрывов относительно частоты исходящих кадров для отправителя.</span><span class="sxs-lookup"><span data-stu-id="f2923-439">Gap duration in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2923-440"><strong>аверажеректанглехеигхт</strong></span><span class="sxs-lookup"><span data-stu-id="f2923-440"><strong>AverageRectangleHeight</strong></span></span></p></td>
<td><p><span data-ttu-id="f2923-441">int</span><span class="sxs-lookup"><span data-stu-id="f2923-441">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f2923-442">Средняя высота разрешения видео в пикселах.</span><span class="sxs-lookup"><span data-stu-id="f2923-442">Average video resolution height, in pixels.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2923-443"><strong>аверажеректанглевидс</strong></span><span class="sxs-lookup"><span data-stu-id="f2923-443"><strong>AverageRectangleWidth</strong></span></span></p></td>
<td><p><span data-ttu-id="f2923-444">int</span><span class="sxs-lookup"><span data-stu-id="f2923-444">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f2923-445">Средняя ширина разрешения видео в пикселах.</span><span class="sxs-lookup"><span data-stu-id="f2923-445">Average video resolution width, in pixels.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2923-446"><strong>Получение</strong></span><span class="sxs-lookup"><span data-stu-id="f2923-446"><strong>Inbound</strong></span></span></p></td>
<td><p><span data-ttu-id="f2923-447">Битовая</span><span class="sxs-lookup"><span data-stu-id="f2923-447">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f2923-448">Средняя частота кадров (в кадрах в секунду) для передачи входящих.</span><span class="sxs-lookup"><span data-stu-id="f2923-448">Average frame rate (in frames per second) for inbound transmissions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2923-449"><strong>Прав</strong></span><span class="sxs-lookup"><span data-stu-id="f2923-449"><strong>Outbound</strong></span></span></p></td>
<td><p><span data-ttu-id="f2923-450">Битовая</span><span class="sxs-lookup"><span data-stu-id="f2923-450">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f2923-451">Средняя частота кадров (в кадрах в секунду) для передачи исходящих пакетов.</span><span class="sxs-lookup"><span data-stu-id="f2923-451">Average frame rate (in frames per second) for outbound transmissions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2923-452"><strong>сендерискаллерпаи</strong></span><span class="sxs-lookup"><span data-stu-id="f2923-452"><strong>SenderIsCallerPAI</strong></span></span></p></td>
<td><p><span data-ttu-id="f2923-453">Битовая</span><span class="sxs-lookup"><span data-stu-id="f2923-453">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f2923-454">1 означает направление потока от вызывающего абонента вызываемому абоненту.</span><span class="sxs-lookup"><span data-stu-id="f2923-454">1 means the stream direction is from the caller to callee.</span></span></p>
<p><span data-ttu-id="f2923-455">0 означает направление потока от вызываемого абонента вызывающему абоненту.</span><span class="sxs-lookup"><span data-stu-id="f2923-455">0 means the stream direction is from the callee to the caller.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

