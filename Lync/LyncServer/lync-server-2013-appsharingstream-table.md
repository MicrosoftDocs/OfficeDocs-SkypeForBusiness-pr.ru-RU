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
ms.openlocfilehash: c00a606981ab09d370d5aac390aa244a31063f24
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41738419"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="appsharingstream-table-in-lync-server-2013"></a><span data-ttu-id="68b20-102">Таблица Аппшарингстреам в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="68b20-102">AppSharingStream table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="68b20-103">_**Тема последнего изменения:** 2014-02-21_</span><span class="sxs-lookup"><span data-stu-id="68b20-103">_**Topic Last Modified:** 2014-02-21_</span></span>

<span data-ttu-id="68b20-104">В таблице Аппшарингстреам содержатся показатели качества взаимодействия для сетевых потоков, используемых для совместного использования приложений.</span><span class="sxs-lookup"><span data-stu-id="68b20-104">The AppSharingStream table contains Quality of Experience metrics for the network streams used for application sharing.</span></span> <span data-ttu-id="68b20-105">Эта таблица введена в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="68b20-105">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="68b20-106"><strong>Столбец</strong></span><span class="sxs-lookup"><span data-stu-id="68b20-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="68b20-107"><strong>Тип данных</strong></span><span class="sxs-lookup"><span data-stu-id="68b20-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="68b20-108"><strong>Ключ/индекс</strong></span><span class="sxs-lookup"><span data-stu-id="68b20-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="68b20-109"><strong>Сведения</strong></span><span class="sxs-lookup"><span data-stu-id="68b20-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="68b20-110"><strong>конференцедатетиме</strong></span><span class="sxs-lookup"><span data-stu-id="68b20-110"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="68b20-111">Датой</span><span class="sxs-lookup"><span data-stu-id="68b20-111">dateTime</span></span></p></td>
<td><p><span data-ttu-id="68b20-112">Основной, внешний</span><span class="sxs-lookup"><span data-stu-id="68b20-112">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="68b20-113">Дата и время начала сеанса.</span><span class="sxs-lookup"><span data-stu-id="68b20-113">Date and time that the session started.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68b20-114"><strong>сессионсек</strong></span><span class="sxs-lookup"><span data-stu-id="68b20-114"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="68b20-115">целое</span><span class="sxs-lookup"><span data-stu-id="68b20-115">int</span></span></p></td>
<td><p><span data-ttu-id="68b20-116">Основной, внешний</span><span class="sxs-lookup"><span data-stu-id="68b20-116">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="68b20-117">Последовательный идентификатор, который используется для различения сеансов, запущенных в одну и ту же дату.</span><span class="sxs-lookup"><span data-stu-id="68b20-117">Sequential identifier used to distinguish between sessions that started on the same date and at the same time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68b20-118"><strong>медиалинелабел</strong></span><span class="sxs-lookup"><span data-stu-id="68b20-118"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="68b20-119">tinyint</span><span class="sxs-lookup"><span data-stu-id="68b20-119">tinyint</span></span></p></td>
<td><p><span data-ttu-id="68b20-120">Основной, внешний</span><span class="sxs-lookup"><span data-stu-id="68b20-120">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="68b20-121">Представляет тип видеостроки, используемой в звонке.</span><span class="sxs-lookup"><span data-stu-id="68b20-121">Represents the type of video line used in the call.</span></span> <span data-ttu-id="68b20-122">Допустимые значения:</span><span class="sxs-lookup"><span data-stu-id="68b20-122">Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="68b20-123">0 – звук</span><span class="sxs-lookup"><span data-stu-id="68b20-123">0 – Audio</span></span></p></li>
<li><p><span data-ttu-id="68b20-124">1 – видео</span><span class="sxs-lookup"><span data-stu-id="68b20-124">1 – Video</span></span></p></li>
<li><p><span data-ttu-id="68b20-125">2 — панорамное видео</span><span class="sxs-lookup"><span data-stu-id="68b20-125">2 – Panoramic video</span></span></p></li>
<li><p><span data-ttu-id="68b20-126">3 — общий доступ к приложениям и рабочим столам</span><span class="sxs-lookup"><span data-stu-id="68b20-126">3 –Application/Desktop Sharing</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68b20-127"><strong>стреамид</strong></span><span class="sxs-lookup"><span data-stu-id="68b20-127"><strong>StreamID</strong></span></span></p></td>
<td><p><span data-ttu-id="68b20-128">целое</span><span class="sxs-lookup"><span data-stu-id="68b20-128">int</span></span></p></td>
<td><p><span data-ttu-id="68b20-129">Primary</span><span class="sxs-lookup"><span data-stu-id="68b20-129">Primary</span></span></p></td>
<td><p><span data-ttu-id="68b20-130">Уникальный идентификатор потока общего просмотра приложения.</span><span class="sxs-lookup"><span data-stu-id="68b20-130">Unique identifier of the application sharing stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68b20-131"><strong>JitterInterArrival</strong></span><span class="sxs-lookup"><span data-stu-id="68b20-131"><strong>JitterInterArrival</strong></span></span></p></td>
<td><p><span data-ttu-id="68b20-132">целое</span><span class="sxs-lookup"><span data-stu-id="68b20-132">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="68b20-133">Среднее значение колебаний, зарегистрированных между прибытиями пакетов RTP.</span><span class="sxs-lookup"><span data-stu-id="68b20-133">Average jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="68b20-134">(Колебание — это мера &quot;шакинесс&quot; звонка). Обычно значения с высокой степенью колебаний заключаются в результате перегруженности или перегруженного сервера мультимедиа, что приводит к искажению или потере звука.</span><span class="sxs-lookup"><span data-stu-id="68b20-134">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68b20-135"><strong>життеринтерарривалмакс</strong></span><span class="sxs-lookup"><span data-stu-id="68b20-135"><strong>JitterInterArrivalMax</strong></span></span></p></td>
<td><p><span data-ttu-id="68b20-136">целое</span><span class="sxs-lookup"><span data-stu-id="68b20-136">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="68b20-137">Обнаружена максимальная колебание между поступлением пакетов RTP.</span><span class="sxs-lookup"><span data-stu-id="68b20-137">Maximum jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="68b20-138">(Колебание — это мера &quot;шакинесс&quot; звонка). Обычно значения с высокой степенью колебаний заключаются в результате перегруженности или перегруженного сервера мультимедиа, что приводит к искажению или потере звука.</span><span class="sxs-lookup"><span data-stu-id="68b20-138">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68b20-139"><strong>RoundTrip</strong></span><span class="sxs-lookup"><span data-stu-id="68b20-139"><strong>RoundTrip</strong></span></span></p></td>
<td><p><span data-ttu-id="68b20-140">целое</span><span class="sxs-lookup"><span data-stu-id="68b20-140">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="68b20-p105">Среднее время (в миллисекундах), необходимое для перемещения пакета Real-Time Transport Protocol в другую конечную точку и его возврата. Приемлемым считается время двусторонней передачи, равное 200 мс (или менее).</span><span class="sxs-lookup"><span data-stu-id="68b20-p105">Average amount of (in milliseconds) required for a Real-Time Transport Protocol packet to travel to another endpoint and then back. Round-trip times of 200 milliseconds or less are considered of acceptable quality.</span></span></p>
<p><span data-ttu-id="68b20-p106">Высокие значения времени двусторонней передачи могут быть обусловлены международной маршрутизацией вызовов, неправильной конфигурацией маршрутизации или перегрузкой сервера-посредника. Длительное время двусторонней передачи приводит к возникновению проблем при двусторонних аудиоразговорах в режиме реального времени.</span><span class="sxs-lookup"><span data-stu-id="68b20-p106">High round-trip values can be caused by international call routing; a routing misconfiguration; or an overloaded media server. High round-trip times result in difficulties with two-way, real-time audio conversations.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68b20-145"><strong>раундтрипмакс</strong></span><span class="sxs-lookup"><span data-stu-id="68b20-145"><strong>RoundTripMax</strong></span></span></p></td>
<td><p><span data-ttu-id="68b20-146">целое</span><span class="sxs-lookup"><span data-stu-id="68b20-146">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="68b20-147">Максимальный объем (в миллисекундах), необходимый для того, чтобы Пакетный протокол передачи данных в реальном времени перейдет на другую конечную точку, а затем снова.</span><span class="sxs-lookup"><span data-stu-id="68b20-147">Maximum amount of (in milliseconds) required for a Real-Time Transport Protocol packet to travel to another endpoint and then back.</span></span> <span data-ttu-id="68b20-148">Приемлемым считается время двусторонней передачи, равное 200 мс (или менее).</span><span class="sxs-lookup"><span data-stu-id="68b20-148">Round-trip times of 200 milliseconds or less are considered of acceptable quality.</span></span></p>
<p><span data-ttu-id="68b20-p108">Высокие значения времени двусторонней передачи могут быть обусловлены международной маршрутизацией вызовов, неправильной конфигурацией маршрутизации или перегрузкой сервера-посредника. Длительное время двусторонней передачи приводит к возникновению проблем при двусторонних аудиоразговорах в режиме реального времени.</span><span class="sxs-lookup"><span data-stu-id="68b20-p108">High round-trip values can be caused by international call routing; a routing misconfiguration; or an overloaded media server. High round-trip times result in difficulties with two-way, real-time audio conversations.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68b20-151"><strong>PacketLossRate</strong></span><span class="sxs-lookup"><span data-stu-id="68b20-151"><strong>PacketLossRate</strong></span></span></p></td>
<td><p><span data-ttu-id="68b20-152">число с плавающей точкой</span><span class="sxs-lookup"><span data-stu-id="68b20-152">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="68b20-p109">Средняя частота потери пакетов RTP. (Потеря пакетов происходит, когда пакеты RTP (Real-Time Transport Protocol — протокол, используемый для передачи аудио- и видеопакетов через Интернет) не достигают места назначения.) Высокие показатели потерь обычно вызваны перегрузкой, недостаточной полосой пропускания, помехами или перегрузкой беспроводной сети, а также перегрузкой сервера-посредника. Потеря пакетов обычно приводит к искажению звука или потере аудиосигналов.</span><span class="sxs-lookup"><span data-stu-id="68b20-p109">Average rate of Real-Time Transport Protocol (RTP) packet loss. (Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion; lack of bandwidth; wireless congestion or interference; or an overloaded media server. Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68b20-156"><strong>паккетлоссратемакс</strong></span><span class="sxs-lookup"><span data-stu-id="68b20-156"><strong>PacketLossRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="68b20-157">число с плавающей точкой</span><span class="sxs-lookup"><span data-stu-id="68b20-157">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="68b20-158">Максимальная частота потери пакетов протокола передачи данных в реальном времени (RTP).</span><span class="sxs-lookup"><span data-stu-id="68b20-158">Maximum rate of Real-Time Transport Protocol (RTP) packet loss.</span></span> <span data-ttu-id="68b20-159">(Потеря пакетов происходит, когда пакеты RTP, протокол, используемый для передачи звука и видео через Интернет, не достигают места назначения.) Обычно тарифы на высокую степень потерь обусловлены перегрузкой; отсутствие пропускной способности; перегрузка беспроводной сети или помехи; или перегруженный сервер мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="68b20-159">(Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion; lack of bandwidth; wireless congestion or interference; or an overloaded media server.</span></span> <span data-ttu-id="68b20-160">Обычно это приводит к искажению или потере аудиосигнала.</span><span class="sxs-lookup"><span data-stu-id="68b20-160">Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68b20-161"><strong>паккетутилизатион</strong></span><span class="sxs-lookup"><span data-stu-id="68b20-161"><strong>PacketUtilization</strong></span></span></p></td>
<td><p><span data-ttu-id="68b20-162">целое</span><span class="sxs-lookup"><span data-stu-id="68b20-162">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="68b20-163">Количество отправленных пакетов.</span><span class="sxs-lookup"><span data-stu-id="68b20-163">Number of packets sent.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68b20-164"><strong>Самый пропускная способность</strong></span><span class="sxs-lookup"><span data-stu-id="68b20-164"><strong>BandwidthEst</strong></span></span></p></td>
<td><p><span data-ttu-id="68b20-165">целое</span><span class="sxs-lookup"><span data-stu-id="68b20-165">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="68b20-166">Предполагаемая односторонняя пропускная способность, доступная в конце сеанса.</span><span class="sxs-lookup"><span data-stu-id="68b20-166">Estimated one-way bandwidth available at the end of the session.</span></span> <span data-ttu-id="68b20-167">Указывается в битах в секунду.</span><span class="sxs-lookup"><span data-stu-id="68b20-167">Reported in bits per second.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68b20-168"><strong>аппшарингпайлоаддескриптион</strong></span><span class="sxs-lookup"><span data-stu-id="68b20-168"><strong>AppSharingPayloadDescription</strong></span></span></p></td>
<td><p><span data-ttu-id="68b20-169">целое</span><span class="sxs-lookup"><span data-stu-id="68b20-169">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="68b20-170">Описание полезных данных для общего использования приложений.</span><span class="sxs-lookup"><span data-stu-id="68b20-170">Description of the application sharing payload.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68b20-171"><strong>релативеоневайтотал</strong></span><span class="sxs-lookup"><span data-stu-id="68b20-171"><strong>RelativeOneWayTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="68b20-172">число с плавающей точкой</span><span class="sxs-lookup"><span data-stu-id="68b20-172">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="68b20-173">Общая сумма односторонней задержки.</span><span class="sxs-lookup"><span data-stu-id="68b20-173">Total amount of one-way latency.</span></span> <span data-ttu-id="68b20-174">Относительная односторонняя задержка измеряет задержку между клиентом и сервером.</span><span class="sxs-lookup"><span data-stu-id="68b20-174">Relative one-way latency measures the delay between the client and the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68b20-175"><strong>релативеоневайавераже</strong></span><span class="sxs-lookup"><span data-stu-id="68b20-175"><strong>RelativeOneWayAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="68b20-176">число с плавающей точкой</span><span class="sxs-lookup"><span data-stu-id="68b20-176">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="68b20-177">Средняя величина односторонней задержки.</span><span class="sxs-lookup"><span data-stu-id="68b20-177">Average amount of one-way latency.</span></span> <span data-ttu-id="68b20-178">Относительная односторонняя задержка измеряет задержку между клиентом и сервером.</span><span class="sxs-lookup"><span data-stu-id="68b20-178">Relative one-way latency measures the delay between the client and the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68b20-179"><strong>релативеоневаймакс</strong></span><span class="sxs-lookup"><span data-stu-id="68b20-179"><strong>RelativeOneWayMax</strong></span></span></p></td>
<td><p><span data-ttu-id="68b20-180">число с плавающей точкой</span><span class="sxs-lookup"><span data-stu-id="68b20-180">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="68b20-181">Максимальная сумма односторонняя задержка.</span><span class="sxs-lookup"><span data-stu-id="68b20-181">Maximum amount of one-way latency.</span></span> <span data-ttu-id="68b20-182">Относительная односторонняя задержка измеряет задержку между клиентом и сервером.</span><span class="sxs-lookup"><span data-stu-id="68b20-182">Relative one-way latency measures the delay between the client and the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68b20-183"><strong>релативеоневайбурстоккурренцес</strong></span><span class="sxs-lookup"><span data-stu-id="68b20-183"><strong>RelativeOneWayBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="68b20-184">целое</span><span class="sxs-lookup"><span data-stu-id="68b20-184">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="68b20-185">Общее количество односторонних вхождений.</span><span class="sxs-lookup"><span data-stu-id="68b20-185">Total one-way burst occurrences.</span></span> <span data-ttu-id="68b20-186">Одновременная передача данных — это передача, при которой данные передаются в непредсказуемые пакеты, а не в устойчивый поток.</span><span class="sxs-lookup"><span data-stu-id="68b20-186">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span> <span data-ttu-id="68b20-187">Этот показатель измеряет поток данных между клиентом и сервером.</span><span class="sxs-lookup"><span data-stu-id="68b20-187">This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68b20-188"><strong>релативеоневайбурстденсити</strong></span><span class="sxs-lookup"><span data-stu-id="68b20-188"><strong>RelativeOneWayBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="68b20-189">число с плавающей точкой</span><span class="sxs-lookup"><span data-stu-id="68b20-189">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="68b20-190">Общая односторонняя плотность нагрузки.</span><span class="sxs-lookup"><span data-stu-id="68b20-190">Total one-way burst density.</span></span> <span data-ttu-id="68b20-191">Одновременная передача данных — это передача, при которой данные передаются в непредсказуемые пакеты, а не в устойчивый поток.</span><span class="sxs-lookup"><span data-stu-id="68b20-191">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span> <span data-ttu-id="68b20-192">Этот показатель измеряет поток данных между клиентом и сервером.</span><span class="sxs-lookup"><span data-stu-id="68b20-192">This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68b20-193"><strong>релативеоневайбурстдуратион</strong></span><span class="sxs-lookup"><span data-stu-id="68b20-193"><strong>RelativeOneWayBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="68b20-194">число с плавающей точкой</span><span class="sxs-lookup"><span data-stu-id="68b20-194">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="68b20-195">Общая продолжительность односторонней длительности.</span><span class="sxs-lookup"><span data-stu-id="68b20-195">Total one-way burst duration.</span></span> <span data-ttu-id="68b20-196">Одновременная передача данных — это передача, при которой данные передаются в непредсказуемые пакеты, а не в устойчивый поток.</span><span class="sxs-lookup"><span data-stu-id="68b20-196">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span> <span data-ttu-id="68b20-197">Этот показатель измеряет поток данных между клиентом и сервером.</span><span class="sxs-lookup"><span data-stu-id="68b20-197">This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68b20-198"><strong>релативеоневайгапоккурренцес</strong></span><span class="sxs-lookup"><span data-stu-id="68b20-198"><strong>RelativeOneWayGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="68b20-199">целое</span><span class="sxs-lookup"><span data-stu-id="68b20-199">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="68b20-200">Общее количество односторонних вхождений.</span><span class="sxs-lookup"><span data-stu-id="68b20-200">Total one-way gap occurrences.</span></span> <span data-ttu-id="68b20-201">Одновременная передача данных — это передача, при которой данные передаются в непредсказуемые пакеты, а не в устойчивый поток. зазоры указывают на задержку между этими пакетами.</span><span class="sxs-lookup"><span data-stu-id="68b20-201">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts.</span></span> <span data-ttu-id="68b20-202">Этот показатель измеряет поток данных между клиентом и сервером.</span><span class="sxs-lookup"><span data-stu-id="68b20-202">This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68b20-203"><strong>релативеоневайгапденсити</strong></span><span class="sxs-lookup"><span data-stu-id="68b20-203"><strong>RelativeOneWayGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="68b20-204">число с плавающей точкой</span><span class="sxs-lookup"><span data-stu-id="68b20-204">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="68b20-205">Общая плотность односторонних зазоров.</span><span class="sxs-lookup"><span data-stu-id="68b20-205">Total one-way gap density.</span></span> <span data-ttu-id="68b20-206">Одновременная передача данных — это передача, при которой данные передаются в непредсказуемые пакеты, а не в устойчивый поток. зазоры указывают на задержку между этими пакетами.</span><span class="sxs-lookup"><span data-stu-id="68b20-206">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts.</span></span> <span data-ttu-id="68b20-207">Этот показатель измеряет поток данных между клиентом и сервером.</span><span class="sxs-lookup"><span data-stu-id="68b20-207">This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68b20-208"><strong>релативеоневайгапдуратион</strong></span><span class="sxs-lookup"><span data-stu-id="68b20-208"><strong>RelativeOneWayGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="68b20-209">число с плавающей точкой</span><span class="sxs-lookup"><span data-stu-id="68b20-209">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="68b20-210">Общая продолжительность односторонних промежутков.</span><span class="sxs-lookup"><span data-stu-id="68b20-210">Total one-way gap duration.</span></span> <span data-ttu-id="68b20-211">Одновременная передача данных — это передача, при которой данные передаются в непредсказуемые пакеты, а не в устойчивый поток. зазоры указывают на задержку между этими пакетами.</span><span class="sxs-lookup"><span data-stu-id="68b20-211">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts.</span></span> <span data-ttu-id="68b20-212">Этот показатель измеряет поток данных между клиентом и сервером.</span><span class="sxs-lookup"><span data-stu-id="68b20-212">This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68b20-213"><strong>аппликатионшарингтипе</strong></span><span class="sxs-lookup"><span data-stu-id="68b20-213"><strong>ApplicationSharingType</strong></span></span></p></td>
<td><p><span data-ttu-id="68b20-214">varChar (256)</span><span class="sxs-lookup"><span data-stu-id="68b20-214">varChar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="68b20-215">Роль приложения (общий доступ или средство просмотра) и тип контента.</span><span class="sxs-lookup"><span data-stu-id="68b20-215">Application role (Sharer or Viewer) and content type.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68b20-216"><strong>рдптилепроцессинглатенцитотал</strong></span><span class="sxs-lookup"><span data-stu-id="68b20-216"><strong>RDPTileProcessingLatencyTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="68b20-217">число с плавающей точкой</span><span class="sxs-lookup"><span data-stu-id="68b20-217">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="68b20-218">Общее время обработки плиток протокола удаленного рабочего стола (RDP).</span><span class="sxs-lookup"><span data-stu-id="68b20-218">Total processing time for remote desktop protocol (RDP) tiles.</span></span> <span data-ttu-id="68b20-219">Общая сумма равна более длительной задержке при просмотре.</span><span class="sxs-lookup"><span data-stu-id="68b20-219">A higher total equates to a longer delay in the viewing experience.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68b20-220"><strong>рдптилепроцессинглатенциавераже</strong></span><span class="sxs-lookup"><span data-stu-id="68b20-220"><strong>RDPTileProcessingLatencyAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="68b20-221">число с плавающей точкой</span><span class="sxs-lookup"><span data-stu-id="68b20-221">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="68b20-222">Среднее время обработки плиток протокола удаленного рабочего стола (RDP).</span><span class="sxs-lookup"><span data-stu-id="68b20-222">Average processing time for remote desktop protocol (RDP) tiles.</span></span> <span data-ttu-id="68b20-223">Общая сумма равна более длительной задержке при просмотре.</span><span class="sxs-lookup"><span data-stu-id="68b20-223">A higher total equates to a longer delay in the viewing experience.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68b20-224"><strong>рдптилепроцессинглатенцимакс</strong></span><span class="sxs-lookup"><span data-stu-id="68b20-224"><strong>RDPTileProcessingLatencyMax</strong></span></span></p></td>
<td><p><span data-ttu-id="68b20-225">число с плавающей точкой</span><span class="sxs-lookup"><span data-stu-id="68b20-225">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="68b20-226">Максимальное время обработки плиток протокола удаленного рабочего стола (RDP).</span><span class="sxs-lookup"><span data-stu-id="68b20-226">Maximum processing time for remote desktop protocol (RDP) tiles.</span></span> <span data-ttu-id="68b20-227">Общая сумма равна более длительной задержке при просмотре.</span><span class="sxs-lookup"><span data-stu-id="68b20-227">A higher total equates to a longer delay in the viewing experience.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68b20-228"><strong>рдптилепроцессинглатенцибурстоккурренцес</strong></span><span class="sxs-lookup"><span data-stu-id="68b20-228"><strong>RDPTileProcessingLatencyBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="68b20-229">целое</span><span class="sxs-lookup"><span data-stu-id="68b20-229">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="68b20-230">Пакетное повторение на время обработки плиток протокола удаленного рабочего стола (RDP).</span><span class="sxs-lookup"><span data-stu-id="68b20-230">Burst occurrences in the processing time for remote desktop protocol (RDP) tiles.</span></span> <span data-ttu-id="68b20-231">Одновременная передача данных — это передача, при которой данные передаются в непредсказуемые пакеты, а не в устойчивый поток.</span><span class="sxs-lookup"><span data-stu-id="68b20-231">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68b20-232"><strong>рдптилепроцессинглатенцибурстденсити</strong></span><span class="sxs-lookup"><span data-stu-id="68b20-232"><strong>RDPTileProcessingLatencyBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="68b20-233">число с плавающей точкой</span><span class="sxs-lookup"><span data-stu-id="68b20-233">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="68b20-234">Ускоренная плотность плиток протокола удаленного рабочего стола (RDP) на время обработки.</span><span class="sxs-lookup"><span data-stu-id="68b20-234">Burst density in the processing time for remote desktop protocol (RDP) tiles.</span></span> <span data-ttu-id="68b20-235">Одновременная передача данных — это передача, при которой данные передаются в непредсказуемые пакеты, а не в устойчивый поток.</span><span class="sxs-lookup"><span data-stu-id="68b20-235">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68b20-236"><strong>рдптилепроцессинглатенцибурстдуратион</strong></span><span class="sxs-lookup"><span data-stu-id="68b20-236"><strong>RDPTileProcessingLatencyBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="68b20-237">число с плавающей точкой</span><span class="sxs-lookup"><span data-stu-id="68b20-237">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="68b20-238">Продолжительность разбивки на время обработки плиток протокола удаленного рабочего стола (RDP).</span><span class="sxs-lookup"><span data-stu-id="68b20-238">Burst duration in the processing time for remote desktop protocol (RDP) tiles.</span></span> <span data-ttu-id="68b20-239">Одновременная передача данных — это передача, при которой данные передаются в непредсказуемые пакеты, а не в устойчивый поток.</span><span class="sxs-lookup"><span data-stu-id="68b20-239">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68b20-240"><strong>рдптилепроцессинглатенцигапоккурренцес</strong></span><span class="sxs-lookup"><span data-stu-id="68b20-240"><strong>RDPTileProcessingLatencyGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="68b20-241">целое</span><span class="sxs-lookup"><span data-stu-id="68b20-241">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="68b20-242">Случаи пропуска на момент обработки плиток протокола удаленного рабочего стола (RDP).</span><span class="sxs-lookup"><span data-stu-id="68b20-242">Gap occurrences in the processing time for remote desktop protocol (RDP) tiles.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68b20-243"><strong>рдптилепроцессинглатенцигапденсити</strong></span><span class="sxs-lookup"><span data-stu-id="68b20-243"><strong>RDPTileProcessingLatencyGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="68b20-244">число с плавающей точкой</span><span class="sxs-lookup"><span data-stu-id="68b20-244">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="68b20-245">Плотность зазоров во время обработки плиток протокола удаленного рабочего стола (RDP).</span><span class="sxs-lookup"><span data-stu-id="68b20-245">Gap density in the processing time for remote desktop protocol (RDP) tiles.</span></span> <span data-ttu-id="68b20-246">Плотность неограниченного промежутка означает более качественный просмотр.</span><span class="sxs-lookup"><span data-stu-id="68b20-246">Low gap density equates to a better viewing experience.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68b20-247"><strong>рдптилепроцессинглатенцигапдуратион</strong></span><span class="sxs-lookup"><span data-stu-id="68b20-247"><strong>RDPTileProcessingLatencyGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="68b20-248">число с плавающей точкой</span><span class="sxs-lookup"><span data-stu-id="68b20-248">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="68b20-249">Продолжительность пропуска для плиток протокола удаленного рабочего стола (RDP).</span><span class="sxs-lookup"><span data-stu-id="68b20-249">Gap duration in the processing time for remote desktop protocol (RDP) tiles.</span></span> <span data-ttu-id="68b20-250">Продолжительность коротких промежутков эквивалентна более качественному просмотру.</span><span class="sxs-lookup"><span data-stu-id="68b20-250">Short gap durations equate to a better viewing experience.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68b20-251"><strong>каптуретилератетотал</strong></span><span class="sxs-lookup"><span data-stu-id="68b20-251"><strong>CaptureTileRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="68b20-252">число с плавающей точкой</span><span class="sxs-lookup"><span data-stu-id="68b20-252">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="68b20-253">Общая частота захваченных плиток (в плитках в секунду).</span><span class="sxs-lookup"><span data-stu-id="68b20-253">Total rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68b20-254"><strong>каптуретилератеавераже</strong></span><span class="sxs-lookup"><span data-stu-id="68b20-254"><strong>CaptureTileRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="68b20-255">число с плавающей точкой</span><span class="sxs-lookup"><span data-stu-id="68b20-255">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="68b20-256">Средняя скорость захваченных плиток (в плитках в секунду).</span><span class="sxs-lookup"><span data-stu-id="68b20-256">Average rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68b20-257"><strong>каптуретилератемакс</strong></span><span class="sxs-lookup"><span data-stu-id="68b20-257"><strong>CaptureTileRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="68b20-258">число с плавающей точкой</span><span class="sxs-lookup"><span data-stu-id="68b20-258">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="68b20-259">Максимальная частота захваченных плиток (в плитках в секунду).</span><span class="sxs-lookup"><span data-stu-id="68b20-259">Maximum rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68b20-260"><strong>каптуретилератебурстоккурренцес</strong></span><span class="sxs-lookup"><span data-stu-id="68b20-260"><strong>CaptureTileRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="68b20-261">в t</span><span class="sxs-lookup"><span data-stu-id="68b20-261">in t</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="68b20-262">Пакетное повторение в частоте захваченных плиток (в плитках в секунду).</span><span class="sxs-lookup"><span data-stu-id="68b20-262">Burst occurrences in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68b20-263"><strong>каптуретилератебурстденсити</strong></span><span class="sxs-lookup"><span data-stu-id="68b20-263"><strong>CaptureTileRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="68b20-264">число с плавающей точкой</span><span class="sxs-lookup"><span data-stu-id="68b20-264">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="68b20-265">Плотность разбивки на захваченные плитки (в плитках в секунду).</span><span class="sxs-lookup"><span data-stu-id="68b20-265">Burst density in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68b20-266"><strong>каптуретилератебурстдуратион</strong></span><span class="sxs-lookup"><span data-stu-id="68b20-266"><strong>CaptureTileRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="68b20-267">число с плавающей точкой</span><span class="sxs-lookup"><span data-stu-id="68b20-267">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="68b20-268">Продолжительность разбивки на собранные плитки (в плитках в секунду).</span><span class="sxs-lookup"><span data-stu-id="68b20-268">Burst duration in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68b20-269"><strong>каптуретилератегапоккурренцес</strong></span><span class="sxs-lookup"><span data-stu-id="68b20-269"><strong>CaptureTileRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="68b20-270">целое</span><span class="sxs-lookup"><span data-stu-id="68b20-270">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="68b20-271">Количество повторений в частоте захваченных плиток (в плитках в секунду).</span><span class="sxs-lookup"><span data-stu-id="68b20-271">Gap occurrences in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68b20-272"><strong>каптуретилератегапденсити</strong></span><span class="sxs-lookup"><span data-stu-id="68b20-272"><strong>CaptureTileRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="68b20-273">число с плавающей точкой</span><span class="sxs-lookup"><span data-stu-id="68b20-273">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="68b20-274">Плотность зазоров в процентах захваченных плиток (в плитках в секунду).</span><span class="sxs-lookup"><span data-stu-id="68b20-274">Gap density in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68b20-275"><strong>каптуретилератегапдуратион</strong></span><span class="sxs-lookup"><span data-stu-id="68b20-275"><strong>CaptureTileRateGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="68b20-276">число с плавающей точкой</span><span class="sxs-lookup"><span data-stu-id="68b20-276">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="68b20-277">Продолжительность зазора в процентах собранных плиток (в плитках в секунду).</span><span class="sxs-lookup"><span data-stu-id="68b20-277">Gap duration in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68b20-278"><strong>споиледтилеперценттотал</strong></span><span class="sxs-lookup"><span data-stu-id="68b20-278"><strong>SpoiledTilePercentTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="68b20-279">число с плавающей точкой</span><span class="sxs-lookup"><span data-stu-id="68b20-279">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="68b20-280">Общий процент содержимого, которое не было получено средством просмотра, но было бы удалено и заменено новым содержимым.</span><span class="sxs-lookup"><span data-stu-id="68b20-280">Total percentage of the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68b20-281"><strong>споиледтилеперцентавераже</strong></span><span class="sxs-lookup"><span data-stu-id="68b20-281"><strong>SpoiledTilePercentAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="68b20-282">число с плавающей точкой</span><span class="sxs-lookup"><span data-stu-id="68b20-282">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="68b20-283">Средний процент содержимого, которое не достиго средства просмотра, но было удалено и заменено новым содержимым.</span><span class="sxs-lookup"><span data-stu-id="68b20-283">Average percentage of the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68b20-284"><strong>споиледтилеперцентмакс</strong></span><span class="sxs-lookup"><span data-stu-id="68b20-284"><strong>SpoiledTilePercentMax</strong></span></span></p></td>
<td><p><span data-ttu-id="68b20-285">число с плавающей точкой</span><span class="sxs-lookup"><span data-stu-id="68b20-285">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="68b20-286">Максимальный процент содержимого, которое не было получено средством просмотра, но было бы удалено и заменено новым содержимым.</span><span class="sxs-lookup"><span data-stu-id="68b20-286">Maximum percentage of the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68b20-287"><strong>споиледтилеперцентбурстоккурренцес</strong></span><span class="sxs-lookup"><span data-stu-id="68b20-287"><strong>SpoiledTilePercentBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="68b20-288">целое</span><span class="sxs-lookup"><span data-stu-id="68b20-288">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="68b20-289">Пакетное повторение для содержимого, которое не достиго средства просмотра, а было удалено и заменено новым содержимым.</span><span class="sxs-lookup"><span data-stu-id="68b20-289">Burst occurrences for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68b20-290"><strong>споиледтилеперцентбурстденсити</strong></span><span class="sxs-lookup"><span data-stu-id="68b20-290"><strong>SpoiledTilePercentBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="68b20-291">число с плавающей точкой</span><span class="sxs-lookup"><span data-stu-id="68b20-291">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="68b20-292">Для содержимого, которое не достигают средства просмотра, оно было удалено и заменено новым содержимым.</span><span class="sxs-lookup"><span data-stu-id="68b20-292">Burst density for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68b20-293"><strong>споиледтилеперцентбурстдуратион</strong></span><span class="sxs-lookup"><span data-stu-id="68b20-293"><strong>SpoiledTilePercentBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="68b20-294">число с плавающей точкой</span><span class="sxs-lookup"><span data-stu-id="68b20-294">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="68b20-295">Продолжительность разбивки на содержимое, которое не было получено средством просмотра, но было бы удалено и заменено новым содержимым.</span><span class="sxs-lookup"><span data-stu-id="68b20-295">Burst duration for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68b20-296"><strong>споиледтилеперцентгапоккурренцес</strong></span><span class="sxs-lookup"><span data-stu-id="68b20-296"><strong>SpoiledTilePercentGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="68b20-297">целое</span><span class="sxs-lookup"><span data-stu-id="68b20-297">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="68b20-298">Повторение для содержимого, которое не достиго средства просмотра, но было удалено и заменено новым содержимым.</span><span class="sxs-lookup"><span data-stu-id="68b20-298">Gap occurrences for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68b20-299"><strong>споиледтилеперцентгапденсити</strong></span><span class="sxs-lookup"><span data-stu-id="68b20-299"><strong>SpoiledTilePercentGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="68b20-300">число с плавающей точкой</span><span class="sxs-lookup"><span data-stu-id="68b20-300">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="68b20-301">Плотность зазоров для содержимого, которое не достиго средства просмотра, но было удалено и заменено новым содержимым.</span><span class="sxs-lookup"><span data-stu-id="68b20-301">Gap density for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68b20-302"><strong>споиледтилеперцентгапдуратион</strong></span><span class="sxs-lookup"><span data-stu-id="68b20-302"><strong>SpoiledTilePercentGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="68b20-303">число с плавающей точкой</span><span class="sxs-lookup"><span data-stu-id="68b20-303">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="68b20-304">Продолжительность зазора для содержимого, которое не достиго средства просмотра, но было удалено и заменено новым содержимым.</span><span class="sxs-lookup"><span data-stu-id="68b20-304">Gap duration for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68b20-305"><strong>скрапингфрамератетотал</strong></span><span class="sxs-lookup"><span data-stu-id="68b20-305"><strong>ScrapingFrameRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="68b20-306">число с плавающей точкой</span><span class="sxs-lookup"><span data-stu-id="68b20-306">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="68b20-307">Общее количество кадров, набракованных из источника графики.</span><span class="sxs-lookup"><span data-stu-id="68b20-307">Total number of frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68b20-308"><strong>скрапингфрамератеавераже</strong></span><span class="sxs-lookup"><span data-stu-id="68b20-308"><strong>ScrapingFrameRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="68b20-309">число с плавающей точкой</span><span class="sxs-lookup"><span data-stu-id="68b20-309">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="68b20-310">Среднее количество кадров, набракованных из источника графики.</span><span class="sxs-lookup"><span data-stu-id="68b20-310">Average number of frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68b20-311"><strong>скрапингфрамератемакс</strong></span><span class="sxs-lookup"><span data-stu-id="68b20-311"><strong>ScrapingFrameRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="68b20-312">число с плавающей точкой</span><span class="sxs-lookup"><span data-stu-id="68b20-312">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="68b20-313">Предельное число кадров, которые не побраковано от источника графики.</span><span class="sxs-lookup"><span data-stu-id="68b20-313">Maximum number of frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68b20-314"><strong>скрапингфрамератебурстоккурренцес</strong></span><span class="sxs-lookup"><span data-stu-id="68b20-314"><strong>ScrapingFrameRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="68b20-315">целое</span><span class="sxs-lookup"><span data-stu-id="68b20-315">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="68b20-316">Пакетное повторение в кадре побраковано от источника графики.</span><span class="sxs-lookup"><span data-stu-id="68b20-316">Burst occurrences in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68b20-317"><strong>скрапингфрамератебурстденсити</strong></span><span class="sxs-lookup"><span data-stu-id="68b20-317"><strong>ScrapingFrameRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="68b20-318">число с плавающей точкой</span><span class="sxs-lookup"><span data-stu-id="68b20-318">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="68b20-319">Ускоренная плотность кадров в кадрах, побракованных из источника графики.</span><span class="sxs-lookup"><span data-stu-id="68b20-319">Burst density in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68b20-320"><strong>скрапингфрамератебурстдуратион</strong></span><span class="sxs-lookup"><span data-stu-id="68b20-320"><strong>ScrapingFrameRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="68b20-321">число с плавающей точкой</span><span class="sxs-lookup"><span data-stu-id="68b20-321">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="68b20-322">Продолжительность разбивки кадров в кадре, побракованная от источника графики.</span><span class="sxs-lookup"><span data-stu-id="68b20-322">Burst duration in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68b20-323"><strong>скрапингфрамератегапоккурренцес</strong></span><span class="sxs-lookup"><span data-stu-id="68b20-323"><strong>ScrapingFrameRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="68b20-324">целое</span><span class="sxs-lookup"><span data-stu-id="68b20-324">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="68b20-325">Случаи разрывов в кадрах оббракованы из источника графики.</span><span class="sxs-lookup"><span data-stu-id="68b20-325">Gap occurrences in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68b20-326"><strong>скрапингфрамератегапденсити</strong></span><span class="sxs-lookup"><span data-stu-id="68b20-326"><strong>ScrapingFrameRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="68b20-327">число с плавающей точкой</span><span class="sxs-lookup"><span data-stu-id="68b20-327">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="68b20-328">Плотность зазоров в кадрах, побракованных из источника графики.</span><span class="sxs-lookup"><span data-stu-id="68b20-328">Gap density in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68b20-329"><strong>скрапингфрамератегапдуратион</strong></span><span class="sxs-lookup"><span data-stu-id="68b20-329"><strong>ScrapingFrameRateGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="68b20-330">число с плавающей точкой</span><span class="sxs-lookup"><span data-stu-id="68b20-330">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="68b20-331">Продолжительность зазора в кадрах, побракованных из источника графики.</span><span class="sxs-lookup"><span data-stu-id="68b20-331">Gap duration in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68b20-332"><strong>инкомингтилератетотал</strong></span><span class="sxs-lookup"><span data-stu-id="68b20-332"><strong>IncomingTileRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="68b20-333">число с плавающей точкой</span><span class="sxs-lookup"><span data-stu-id="68b20-333">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="68b20-334">Общая частота входящих кадров, полученных средством просмотра.</span><span class="sxs-lookup"><span data-stu-id="68b20-334">Total incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68b20-335"><strong>инкомингтилератеавераже</strong></span><span class="sxs-lookup"><span data-stu-id="68b20-335"><strong>IncomingTileRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="68b20-336">число с плавающей точкой</span><span class="sxs-lookup"><span data-stu-id="68b20-336">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="68b20-337">Средняя частота входящих кадров, полученная средством просмотра.</span><span class="sxs-lookup"><span data-stu-id="68b20-337">Average incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68b20-338"><strong>инкомингтилератемакс</strong></span><span class="sxs-lookup"><span data-stu-id="68b20-338"><strong>IncomingTileRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="68b20-339">число с плавающей точкой</span><span class="sxs-lookup"><span data-stu-id="68b20-339">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="68b20-340">Максимальное количество входящих частот плиток, полученных средством просмотра.</span><span class="sxs-lookup"><span data-stu-id="68b20-340">Maximum incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68b20-341"><strong>инкомингтилератебурстоккурренцес</strong></span><span class="sxs-lookup"><span data-stu-id="68b20-341"><strong>IncomingTileRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="68b20-342">целое</span><span class="sxs-lookup"><span data-stu-id="68b20-342">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="68b20-343">Пакетное повторение входящего, полученного средством просмотра частоты плиток.</span><span class="sxs-lookup"><span data-stu-id="68b20-343">Burst occurrences in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68b20-344"><strong>инкомингтилератебурстденсити</strong></span><span class="sxs-lookup"><span data-stu-id="68b20-344"><strong>IncomingTileRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="68b20-345">число с плавающей точкой</span><span class="sxs-lookup"><span data-stu-id="68b20-345">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="68b20-346">Многоуровневая плотность во входящих частотах плиток, полученных средством просмотра.</span><span class="sxs-lookup"><span data-stu-id="68b20-346">Burst density in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68b20-347"><strong>инкомингтилератебурстдуратион</strong></span><span class="sxs-lookup"><span data-stu-id="68b20-347"><strong>IncomingTileRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="68b20-348">число с плавающей точкой</span><span class="sxs-lookup"><span data-stu-id="68b20-348">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="68b20-349">Продолжительность пакетной обработки на входящем частоте плиток, полученной средством просмотра.</span><span class="sxs-lookup"><span data-stu-id="68b20-349">Burst duration in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68b20-350"><strong>инкомингтилератегапоккурренцес</strong></span><span class="sxs-lookup"><span data-stu-id="68b20-350"><strong>IncomingTileRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="68b20-351">целое</span><span class="sxs-lookup"><span data-stu-id="68b20-351">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="68b20-352">Количество вхождений во входящих частотах плиток, полученных средством просмотра.</span><span class="sxs-lookup"><span data-stu-id="68b20-352">Gap occurrences in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68b20-353"><strong>инкомингтилератегапденсити</strong></span><span class="sxs-lookup"><span data-stu-id="68b20-353"><strong>IncomingTileRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="68b20-354">число с плавающей точкой</span><span class="sxs-lookup"><span data-stu-id="68b20-354">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="68b20-355">Плотность просветов во входящих частотах плиток, полученных средством просмотра.</span><span class="sxs-lookup"><span data-stu-id="68b20-355">Gap density in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68b20-356"><strong>инкомингтилератегапдуратион</strong></span><span class="sxs-lookup"><span data-stu-id="68b20-356"><strong>IncomingTileRateGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="68b20-357">число с плавающей точкой</span><span class="sxs-lookup"><span data-stu-id="68b20-357">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="68b20-358">Длительность пропуска во входящих частотах плиток, полученных средством просмотра.</span><span class="sxs-lookup"><span data-stu-id="68b20-358">Gap duration in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68b20-359"><strong>инкомингфрамератетотал</strong></span><span class="sxs-lookup"><span data-stu-id="68b20-359"><strong>IncomingFrameRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="68b20-360">число с плавающей точкой</span><span class="sxs-lookup"><span data-stu-id="68b20-360">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="68b20-361">Общая частота входящих кадров, полученных средством просмотра.</span><span class="sxs-lookup"><span data-stu-id="68b20-361">Total incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68b20-362"><strong>инкомингфрамератеавераже</strong></span><span class="sxs-lookup"><span data-stu-id="68b20-362"><strong>IncomingFrameRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="68b20-363">число с плавающей точкой</span><span class="sxs-lookup"><span data-stu-id="68b20-363">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="68b20-364">Средняя частота входящих кадров, полученная средством просмотра.</span><span class="sxs-lookup"><span data-stu-id="68b20-364">Average incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68b20-365"><strong>инкомингфрамератемакс</strong></span><span class="sxs-lookup"><span data-stu-id="68b20-365"><strong>IncomingFrameRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="68b20-366">число с плавающей точкой</span><span class="sxs-lookup"><span data-stu-id="68b20-366">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="68b20-367">Максимальная частота поступающих кадров, полученных средством просмотра.</span><span class="sxs-lookup"><span data-stu-id="68b20-367">Maximum incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68b20-368"><strong>инкомингфрамератебурстоккурренцес</strong></span><span class="sxs-lookup"><span data-stu-id="68b20-368"><strong>IncomingFrameRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="68b20-369">целое</span><span class="sxs-lookup"><span data-stu-id="68b20-369">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="68b20-370">Пакетное повторение во входящих частотах кадров, полученных средством просмотра.</span><span class="sxs-lookup"><span data-stu-id="68b20-370">Burst occurrences in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68b20-371"><strong>инкомингфрамератебурстденсити</strong></span><span class="sxs-lookup"><span data-stu-id="68b20-371"><strong>IncomingFrameRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="68b20-372">число с плавающей точкой</span><span class="sxs-lookup"><span data-stu-id="68b20-372">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="68b20-373">Многоуровневая плотность во входящих частотах кадров, полученных средством просмотра.</span><span class="sxs-lookup"><span data-stu-id="68b20-373">Burst density in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68b20-374"><strong>инкомингфрамератебурстдуратион</strong></span><span class="sxs-lookup"><span data-stu-id="68b20-374"><strong>IncomingFrameRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="68b20-375">число с плавающей точкой</span><span class="sxs-lookup"><span data-stu-id="68b20-375">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="68b20-376">Продолжительность многочастотной обработки кадров, полученная средством просмотра.</span><span class="sxs-lookup"><span data-stu-id="68b20-376">Burst duration in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68b20-377"><strong>инкомингфрамератегапоккурренцес</strong></span><span class="sxs-lookup"><span data-stu-id="68b20-377"><strong>IncomingFrameRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="68b20-378">целое</span><span class="sxs-lookup"><span data-stu-id="68b20-378">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="68b20-379">Пропуск вхождений во входной частоте кадров, полученной средством просмотра.</span><span class="sxs-lookup"><span data-stu-id="68b20-379">Gap occurrences in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68b20-380"><strong>инкомингфрамератегапденсити</strong></span><span class="sxs-lookup"><span data-stu-id="68b20-380"><strong>IncomingFrameRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="68b20-381">число с плавающей точкой</span><span class="sxs-lookup"><span data-stu-id="68b20-381">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="68b20-382">Плотность зазоров во входящих частотах кадров, полученных средством просмотра.</span><span class="sxs-lookup"><span data-stu-id="68b20-382">Gap density in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68b20-383"><strong>инкомингфрамератедуратион</strong></span><span class="sxs-lookup"><span data-stu-id="68b20-383"><strong>IncomingFrameRateDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="68b20-384">число с плавающей точкой</span><span class="sxs-lookup"><span data-stu-id="68b20-384">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="68b20-385">Длительность промежутка во входящих частотах кадров, полученных средством просмотра.</span><span class="sxs-lookup"><span data-stu-id="68b20-385">Gap duration in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68b20-386"><strong>аутгоингтилератетотал</strong></span><span class="sxs-lookup"><span data-stu-id="68b20-386"><strong>OutgoingTileRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="68b20-387">число с плавающей точкой</span><span class="sxs-lookup"><span data-stu-id="68b20-387">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="68b20-388">Общая частота исходящих плиток для отправителя.</span><span class="sxs-lookup"><span data-stu-id="68b20-388">Total outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68b20-389"><strong>аутгоингтилератеавераже</strong></span><span class="sxs-lookup"><span data-stu-id="68b20-389"><strong>OutgoingTileRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="68b20-390">число с плавающей точкой</span><span class="sxs-lookup"><span data-stu-id="68b20-390">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="68b20-391">Средняя исходящая частота плиток для отправителя.</span><span class="sxs-lookup"><span data-stu-id="68b20-391">Average outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68b20-392"><strong>аутгоингтилератемакс</strong></span><span class="sxs-lookup"><span data-stu-id="68b20-392"><strong>OutgoingTileRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="68b20-393">число с плавающей точкой</span><span class="sxs-lookup"><span data-stu-id="68b20-393">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="68b20-394">Максимальная исходящая ставка плиток для отправителя.</span><span class="sxs-lookup"><span data-stu-id="68b20-394">Maximum outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68b20-395"><strong>аутгоингтилератебурстоккурренцес</strong></span><span class="sxs-lookup"><span data-stu-id="68b20-395"><strong>OutgoingTileRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="68b20-396">целое</span><span class="sxs-lookup"><span data-stu-id="68b20-396">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="68b20-397">Пакетное повторение исходящих плиток для отправителя.</span><span class="sxs-lookup"><span data-stu-id="68b20-397">Burst occurrences in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68b20-398"><strong>аутгоингтилератебурстденсити</strong></span><span class="sxs-lookup"><span data-stu-id="68b20-398"><strong>OutgoingTileRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="68b20-399">число с плавающей точкой</span><span class="sxs-lookup"><span data-stu-id="68b20-399">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="68b20-400">Плотность разбивки на выходящую частоту плиток для отправителя.</span><span class="sxs-lookup"><span data-stu-id="68b20-400">Burst density in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68b20-401"><strong>аутгоингтилератебурстдуратион</strong></span><span class="sxs-lookup"><span data-stu-id="68b20-401"><strong>OutgoingTileRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="68b20-402">число с плавающей точкой</span><span class="sxs-lookup"><span data-stu-id="68b20-402">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="68b20-403">Продолжительность разбивки на исходящую частоту плиток для отправителя.</span><span class="sxs-lookup"><span data-stu-id="68b20-403">Burst duration in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68b20-404"><strong>аутгоингтилератегапоккурренцес</strong></span><span class="sxs-lookup"><span data-stu-id="68b20-404"><strong>OutgoingTileRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="68b20-405">целое</span><span class="sxs-lookup"><span data-stu-id="68b20-405">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="68b20-406">Количество повторений в исходящих частотах плиток для отправителя.</span><span class="sxs-lookup"><span data-stu-id="68b20-406">Gap occurrences in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68b20-407"><strong>аутгоингтилератегапденсити</strong></span><span class="sxs-lookup"><span data-stu-id="68b20-407"><strong>OutgoingTileRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="68b20-408">число с плавающей точкой</span><span class="sxs-lookup"><span data-stu-id="68b20-408">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="68b20-409">Плотность зазоров для отправителя за исходящую частоту плиток.</span><span class="sxs-lookup"><span data-stu-id="68b20-409">Gap density in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68b20-410"><strong>аутгоингтилератегапдуратион</strong></span><span class="sxs-lookup"><span data-stu-id="68b20-410"><strong>OutgoingTileRateGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="68b20-411">число с плавающей точкой</span><span class="sxs-lookup"><span data-stu-id="68b20-411">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="68b20-412">Продолжительность зазора для отправителя с исходящим рейтингом.</span><span class="sxs-lookup"><span data-stu-id="68b20-412">Gap duration in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68b20-413"><strong>аутгоингфрамератетотал</strong></span><span class="sxs-lookup"><span data-stu-id="68b20-413"><strong>OutgoingFrameRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="68b20-414">число с плавающей точкой</span><span class="sxs-lookup"><span data-stu-id="68b20-414">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="68b20-415">Общая частота исходящих кадров для отправителя.</span><span class="sxs-lookup"><span data-stu-id="68b20-415">Total outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68b20-416"><strong>аутгоингфрамератеавераже</strong></span><span class="sxs-lookup"><span data-stu-id="68b20-416"><strong>OutgoingFrameRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="68b20-417">число с плавающей точкой</span><span class="sxs-lookup"><span data-stu-id="68b20-417">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="68b20-418">средняя исходящая частота кадров для отправителя.</span><span class="sxs-lookup"><span data-stu-id="68b20-418">average outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68b20-419"><strong>аутгоингфрамератемакс</strong></span><span class="sxs-lookup"><span data-stu-id="68b20-419"><strong>OutgoingFrameRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="68b20-420">число с плавающей точкой</span><span class="sxs-lookup"><span data-stu-id="68b20-420">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="68b20-421">Максимальная исходящая частота кадров для отправителя.</span><span class="sxs-lookup"><span data-stu-id="68b20-421">Maximum outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68b20-422"><strong>аутгоингфрамератебурстоккурренцес</strong></span><span class="sxs-lookup"><span data-stu-id="68b20-422"><strong>OutgoingFrameRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="68b20-423">целое</span><span class="sxs-lookup"><span data-stu-id="68b20-423">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="68b20-424">Пакетное повторение в исходящих частотах кадров для отправителя.</span><span class="sxs-lookup"><span data-stu-id="68b20-424">Burst occurrences in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68b20-425"><strong>аутгоингфрамератебурстденсити</strong></span><span class="sxs-lookup"><span data-stu-id="68b20-425"><strong>OutgoingFrameRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="68b20-426">число с плавающей точкой</span><span class="sxs-lookup"><span data-stu-id="68b20-426">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="68b20-427">В исходящих частотах кадров для отправителя — это пакетная плотность.</span><span class="sxs-lookup"><span data-stu-id="68b20-427">Burst density in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68b20-428"><strong>аутгоингфрамератебурстдуратион</strong></span><span class="sxs-lookup"><span data-stu-id="68b20-428"><strong>OutgoingFrameRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="68b20-429">число с плавающей точкой</span><span class="sxs-lookup"><span data-stu-id="68b20-429">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="68b20-430">Продолжительность разбивки кадров в исходящей частотной скорости для отправителя.</span><span class="sxs-lookup"><span data-stu-id="68b20-430">Burst duration in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68b20-431"><strong>аутгоингфрамератегапоккурренцес</strong></span><span class="sxs-lookup"><span data-stu-id="68b20-431"><strong>OutgoingFrameRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="68b20-432">целое</span><span class="sxs-lookup"><span data-stu-id="68b20-432">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="68b20-433">Количество повторений в исходящей частоте кадров для отправителя.</span><span class="sxs-lookup"><span data-stu-id="68b20-433">Gap occurrences in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68b20-434"><strong>аутгоингфрамератегапденсити</strong></span><span class="sxs-lookup"><span data-stu-id="68b20-434"><strong>OutgoingFrameRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="68b20-435">число с плавающей точкой</span><span class="sxs-lookup"><span data-stu-id="68b20-435">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="68b20-436">Плотность зазоров в исходящих частотах кадров для отправителя.</span><span class="sxs-lookup"><span data-stu-id="68b20-436">Gap density in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68b20-437"><strong>аутгоингфрамератегапдуратион</strong></span><span class="sxs-lookup"><span data-stu-id="68b20-437"><strong>OutgoingFrameRateGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="68b20-438">число с плавающей точкой</span><span class="sxs-lookup"><span data-stu-id="68b20-438">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="68b20-439">Длительность промежутка в исходящих частотах кадров для отправителя.</span><span class="sxs-lookup"><span data-stu-id="68b20-439">Gap duration in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68b20-440"><strong>аверажеректанглехеигхт</strong></span><span class="sxs-lookup"><span data-stu-id="68b20-440"><strong>AverageRectangleHeight</strong></span></span></p></td>
<td><p><span data-ttu-id="68b20-441">целое</span><span class="sxs-lookup"><span data-stu-id="68b20-441">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="68b20-442">Средняя высота разрешающей способности видео (в пикселях).</span><span class="sxs-lookup"><span data-stu-id="68b20-442">Average video resolution height, in pixels.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68b20-443"><strong>аверажеректанглевидс</strong></span><span class="sxs-lookup"><span data-stu-id="68b20-443"><strong>AverageRectangleWidth</strong></span></span></p></td>
<td><p><span data-ttu-id="68b20-444">целое</span><span class="sxs-lookup"><span data-stu-id="68b20-444">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="68b20-445">Средняя ширина разрешающей способности видео в пикселях.</span><span class="sxs-lookup"><span data-stu-id="68b20-445">Average video resolution width, in pixels.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68b20-446"><strong>443</strong></span><span class="sxs-lookup"><span data-stu-id="68b20-446"><strong>Inbound</strong></span></span></p></td>
<td><p><span data-ttu-id="68b20-447">бит</span><span class="sxs-lookup"><span data-stu-id="68b20-447">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="68b20-448">Средняя частота кадров (в кадрах в секунду) для входящих передач.</span><span class="sxs-lookup"><span data-stu-id="68b20-448">Average frame rate (in frames per second) for inbound transmissions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68b20-449"><strong>Исходящее</strong></span><span class="sxs-lookup"><span data-stu-id="68b20-449"><strong>Outbound</strong></span></span></p></td>
<td><p><span data-ttu-id="68b20-450">бит</span><span class="sxs-lookup"><span data-stu-id="68b20-450">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="68b20-451">Средняя частота кадров (в кадрах в секунду) для исходящих передач.</span><span class="sxs-lookup"><span data-stu-id="68b20-451">Average frame rate (in frames per second) for outbound transmissions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68b20-452"><strong>сендерискаллерпаи</strong></span><span class="sxs-lookup"><span data-stu-id="68b20-452"><strong>SenderIsCallerPAI</strong></span></span></p></td>
<td><p><span data-ttu-id="68b20-453">бит</span><span class="sxs-lookup"><span data-stu-id="68b20-453">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="68b20-454">1 — направление потока для вызываемого абонента.</span><span class="sxs-lookup"><span data-stu-id="68b20-454">1 means the stream direction is from the caller to callee.</span></span></p>
<p><span data-ttu-id="68b20-455">0 — направление потока из вызываемого объекта вызывающему абоненту.</span><span class="sxs-lookup"><span data-stu-id="68b20-455">0 means the stream direction is from the callee to the caller.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

