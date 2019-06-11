---
title: 'Lync Server 2013: таблица Аппшарингстреам'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: AppSharingStream table
ms:assetid: 391490cb-d7b8-44ca-b4d1-429600da909c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204808(v=OCS.15)
ms:contentKeyID: 48183852
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 56f23e214ffcffad8613d413924a53ffe571883d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34841783"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="appsharingstream-table-in-lync-server-2013"></a><span data-ttu-id="c40fa-102">Таблица Аппшарингстреам в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c40fa-102">AppSharingStream table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c40fa-103">_**Тема последнего изменения:** 2014-02-21_</span><span class="sxs-lookup"><span data-stu-id="c40fa-103">_**Topic Last Modified:** 2014-02-21_</span></span>

<span data-ttu-id="c40fa-104">В таблице Аппшарингстреам содержатся показатели качества взаимодействия для сетевых потоков, используемых для совместного использования приложений.</span><span class="sxs-lookup"><span data-stu-id="c40fa-104">The AppSharingStream table contains Quality of Experience metrics for the network streams used for application sharing.</span></span> <span data-ttu-id="c40fa-105">Эта таблица введена в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c40fa-105">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c40fa-106"><strong>Столбец</strong></span><span class="sxs-lookup"><span data-stu-id="c40fa-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="c40fa-107"><strong>Тип данных</strong></span><span class="sxs-lookup"><span data-stu-id="c40fa-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="c40fa-108"><strong>Ключ/индекс</strong></span><span class="sxs-lookup"><span data-stu-id="c40fa-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="c40fa-109"><strong>Сведения</strong></span><span class="sxs-lookup"><span data-stu-id="c40fa-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c40fa-110"><strong>Конференцедатетиме</strong></span><span class="sxs-lookup"><span data-stu-id="c40fa-110"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="c40fa-111">Датой</span><span class="sxs-lookup"><span data-stu-id="c40fa-111">dateTime</span></span></p></td>
<td><p><span data-ttu-id="c40fa-112">Основной, внешний</span><span class="sxs-lookup"><span data-stu-id="c40fa-112">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="c40fa-113">Дата и время начала сеанса.</span><span class="sxs-lookup"><span data-stu-id="c40fa-113">Date and time that the session started.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c40fa-114"><strong>Сессионсек</strong></span><span class="sxs-lookup"><span data-stu-id="c40fa-114"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="c40fa-115">целое</span><span class="sxs-lookup"><span data-stu-id="c40fa-115">int</span></span></p></td>
<td><p><span data-ttu-id="c40fa-116">Основной, внешний</span><span class="sxs-lookup"><span data-stu-id="c40fa-116">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="c40fa-117">Последовательный идентификатор, который используется для различения сеансов, запущенных в одну и ту же дату.</span><span class="sxs-lookup"><span data-stu-id="c40fa-117">Sequential identifier used to distinguish between sessions that started on the same date and at the same time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c40fa-118"><strong>Медиалинелабел</strong></span><span class="sxs-lookup"><span data-stu-id="c40fa-118"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="c40fa-119">tinyint</span><span class="sxs-lookup"><span data-stu-id="c40fa-119">tinyint</span></span></p></td>
<td><p><span data-ttu-id="c40fa-120">Основной, внешний</span><span class="sxs-lookup"><span data-stu-id="c40fa-120">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="c40fa-121">Представляет тип видеостроки, используемой в звонке.</span><span class="sxs-lookup"><span data-stu-id="c40fa-121">Represents the type of video line used in the call.</span></span> <span data-ttu-id="c40fa-122">Допустимые значения:</span><span class="sxs-lookup"><span data-stu-id="c40fa-122">Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="c40fa-123">0 – звук</span><span class="sxs-lookup"><span data-stu-id="c40fa-123">0 – Audio</span></span></p></li>
<li><p><span data-ttu-id="c40fa-124">1 – видео</span><span class="sxs-lookup"><span data-stu-id="c40fa-124">1 – Video</span></span></p></li>
<li><p><span data-ttu-id="c40fa-125">2 — панорамное видео</span><span class="sxs-lookup"><span data-stu-id="c40fa-125">2 – Panoramic video</span></span></p></li>
<li><p><span data-ttu-id="c40fa-126">3 — общий доступ к приложениям и рабочим столам</span><span class="sxs-lookup"><span data-stu-id="c40fa-126">3 –Application/Desktop Sharing</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c40fa-127"><strong>Стреамид</strong></span><span class="sxs-lookup"><span data-stu-id="c40fa-127"><strong>StreamID</strong></span></span></p></td>
<td><p><span data-ttu-id="c40fa-128">целое</span><span class="sxs-lookup"><span data-stu-id="c40fa-128">int</span></span></p></td>
<td><p><span data-ttu-id="c40fa-129">Primary</span><span class="sxs-lookup"><span data-stu-id="c40fa-129">Primary</span></span></p></td>
<td><p><span data-ttu-id="c40fa-130">Уникальный идентификатор потока общего просмотра приложения.</span><span class="sxs-lookup"><span data-stu-id="c40fa-130">Unique identifier of the application sharing stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c40fa-131"><strong>JitterInterArrival</strong></span><span class="sxs-lookup"><span data-stu-id="c40fa-131"><strong>JitterInterArrival</strong></span></span></p></td>
<td><p><span data-ttu-id="c40fa-132">целое</span><span class="sxs-lookup"><span data-stu-id="c40fa-132">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c40fa-133">Среднее значение колебаний, зарегистрированных между прибытиями пакетов RTP.</span><span class="sxs-lookup"><span data-stu-id="c40fa-133">Average jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="c40fa-134">(Колебание — это мера &quot;шакинесс&quot; звонка). Обычно значения с высокой степенью колебаний заключаются в результате перегруженности или перегруженного сервера мультимедиа, что приводит к искажению или потере звука.</span><span class="sxs-lookup"><span data-stu-id="c40fa-134">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c40fa-135"><strong>Життеринтерарривалмакс</strong></span><span class="sxs-lookup"><span data-stu-id="c40fa-135"><strong>JitterInterArrivalMax</strong></span></span></p></td>
<td><p><span data-ttu-id="c40fa-136">целое</span><span class="sxs-lookup"><span data-stu-id="c40fa-136">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c40fa-137">Обнаружена максимальная колебание между поступлением пакетов RTP.</span><span class="sxs-lookup"><span data-stu-id="c40fa-137">Maximum jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="c40fa-138">(Колебание — это мера &quot;шакинесс&quot; звонка). Обычно значения с высокой степенью колебаний заключаются в результате перегруженности или перегруженного сервера мультимедиа, что приводит к искажению или потере звука.</span><span class="sxs-lookup"><span data-stu-id="c40fa-138">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c40fa-139"><strong>RoundTrip</strong></span><span class="sxs-lookup"><span data-stu-id="c40fa-139"><strong>RoundTrip</strong></span></span></p></td>
<td><p><span data-ttu-id="c40fa-140">целое</span><span class="sxs-lookup"><span data-stu-id="c40fa-140">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c40fa-p105">Среднее время (в миллисекундах), необходимое для перемещения пакета Real-Time Transport Protocol в другую конечную точку и его возврата. Приемлемым считается время двусторонней передачи, равное 200 мс (или менее).</span><span class="sxs-lookup"><span data-stu-id="c40fa-p105">Average amount of (in milliseconds) required for a Real-Time Transport Protocol packet to travel to another endpoint and then back. Round-trip times of 200 milliseconds or less are considered of acceptable quality.</span></span></p>
<p><span data-ttu-id="c40fa-p106">Высокие значения времени двусторонней передачи могут быть обусловлены международной маршрутизацией вызовов, неправильной конфигурацией маршрутизации или перегрузкой сервера-посредника. Длительное время двусторонней передачи приводит к возникновению проблем при двусторонних аудиоразговорах в режиме реального времени.</span><span class="sxs-lookup"><span data-stu-id="c40fa-p106">High round-trip values can be caused by international call routing; a routing misconfiguration; or an overloaded media server. High round-trip times result in difficulties with two-way, real-time audio conversations.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c40fa-145"><strong>Раундтрипмакс</strong></span><span class="sxs-lookup"><span data-stu-id="c40fa-145"><strong>RoundTripMax</strong></span></span></p></td>
<td><p><span data-ttu-id="c40fa-146">целое</span><span class="sxs-lookup"><span data-stu-id="c40fa-146">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c40fa-147">Максимальный объем (в миллисекундах), необходимый для того, чтобы Пакетный протокол передачи данных в реальном времени перейдет на другую конечную точку, а затем снова.</span><span class="sxs-lookup"><span data-stu-id="c40fa-147">Maximum amount of (in milliseconds) required for a Real-Time Transport Protocol packet to travel to another endpoint and then back.</span></span> <span data-ttu-id="c40fa-148">Приемлемым считается время двусторонней передачи, равное 200 мс (или менее).</span><span class="sxs-lookup"><span data-stu-id="c40fa-148">Round-trip times of 200 milliseconds or less are considered of acceptable quality.</span></span></p>
<p><span data-ttu-id="c40fa-p108">Высокие значения времени двусторонней передачи могут быть обусловлены международной маршрутизацией вызовов, неправильной конфигурацией маршрутизации или перегрузкой сервера-посредника. Длительное время двусторонней передачи приводит к возникновению проблем при двусторонних аудиоразговорах в режиме реального времени.</span><span class="sxs-lookup"><span data-stu-id="c40fa-p108">High round-trip values can be caused by international call routing; a routing misconfiguration; or an overloaded media server. High round-trip times result in difficulties with two-way, real-time audio conversations.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c40fa-151"><strong>PacketLossRate</strong></span><span class="sxs-lookup"><span data-stu-id="c40fa-151"><strong>PacketLossRate</strong></span></span></p></td>
<td><p><span data-ttu-id="c40fa-152">число с плавающей точкой</span><span class="sxs-lookup"><span data-stu-id="c40fa-152">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c40fa-p109">Средняя частота потери пакетов RTP. (Потеря пакетов происходит, когда пакеты RTP (Real-Time Transport Protocol — протокол, используемый для передачи аудио- и видеопакетов через Интернет) не достигают места назначения.) Высокие показатели потерь обычно вызваны перегрузкой, недостаточной полосой пропускания, помехами или перегрузкой беспроводной сети, а также перегрузкой сервера-посредника. Потеря пакетов обычно приводит к искажению звука или потере аудиосигналов.</span><span class="sxs-lookup"><span data-stu-id="c40fa-p109">Average rate of Real-Time Transport Protocol (RTP) packet loss. (Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion; lack of bandwidth; wireless congestion or interference; or an overloaded media server. Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c40fa-156"><strong>Паккетлоссратемакс</strong></span><span class="sxs-lookup"><span data-stu-id="c40fa-156"><strong>PacketLossRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="c40fa-157">число с плавающей точкой</span><span class="sxs-lookup"><span data-stu-id="c40fa-157">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c40fa-158">Максимальная частота потери пакетов протокола передачи данных в реальном времени (RTP).</span><span class="sxs-lookup"><span data-stu-id="c40fa-158">Maximum rate of Real-Time Transport Protocol (RTP) packet loss.</span></span> <span data-ttu-id="c40fa-159">(Потеря пакетов происходит, когда пакеты RTP, протокол, используемый для передачи звука и видео через Интернет, не достигают места назначения.) Обычно тарифы на высокую степень потерь обусловлены перегрузкой; отсутствие пропускной способности; перегрузка беспроводной сети или помехи; или перегруженный сервер мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="c40fa-159">(Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion; lack of bandwidth; wireless congestion or interference; or an overloaded media server.</span></span> <span data-ttu-id="c40fa-160">Обычно это приводит к искажению или потере аудиосигнала.</span><span class="sxs-lookup"><span data-stu-id="c40fa-160">Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c40fa-161"><strong>Паккетутилизатион</strong></span><span class="sxs-lookup"><span data-stu-id="c40fa-161"><strong>PacketUtilization</strong></span></span></p></td>
<td><p><span data-ttu-id="c40fa-162">целое</span><span class="sxs-lookup"><span data-stu-id="c40fa-162">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c40fa-163">Количество отправленных пакетов.</span><span class="sxs-lookup"><span data-stu-id="c40fa-163">Number of packets sent.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c40fa-164"><strong>Самый пропускная способность</strong></span><span class="sxs-lookup"><span data-stu-id="c40fa-164"><strong>BandwidthEst</strong></span></span></p></td>
<td><p><span data-ttu-id="c40fa-165">целое</span><span class="sxs-lookup"><span data-stu-id="c40fa-165">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c40fa-166">Предполагаемая односторонняя пропускная способность, доступная в конце сеанса.</span><span class="sxs-lookup"><span data-stu-id="c40fa-166">Estimated one-way bandwidth available at the end of the session.</span></span> <span data-ttu-id="c40fa-167">Указывается в битах в секунду.</span><span class="sxs-lookup"><span data-stu-id="c40fa-167">Reported in bits per second.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c40fa-168"><strong>Аппшарингпайлоаддескриптион</strong></span><span class="sxs-lookup"><span data-stu-id="c40fa-168"><strong>AppSharingPayloadDescription</strong></span></span></p></td>
<td><p><span data-ttu-id="c40fa-169">целое</span><span class="sxs-lookup"><span data-stu-id="c40fa-169">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c40fa-170">Описание полезных данных для общего использования приложений.</span><span class="sxs-lookup"><span data-stu-id="c40fa-170">Description of the application sharing payload.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c40fa-171"><strong>Релативеоневайтотал</strong></span><span class="sxs-lookup"><span data-stu-id="c40fa-171"><strong>RelativeOneWayTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="c40fa-172">число с плавающей точкой</span><span class="sxs-lookup"><span data-stu-id="c40fa-172">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c40fa-173">Общая сумма односторонней задержки.</span><span class="sxs-lookup"><span data-stu-id="c40fa-173">Total amount of one-way latency.</span></span> <span data-ttu-id="c40fa-174">Относительная односторонняя задержка измеряет задержку между клиентом и сервером.</span><span class="sxs-lookup"><span data-stu-id="c40fa-174">Relative one-way latency measures the delay between the client and the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c40fa-175"><strong>Релативеоневайавераже</strong></span><span class="sxs-lookup"><span data-stu-id="c40fa-175"><strong>RelativeOneWayAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="c40fa-176">число с плавающей точкой</span><span class="sxs-lookup"><span data-stu-id="c40fa-176">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c40fa-177">Средняя величина односторонней задержки.</span><span class="sxs-lookup"><span data-stu-id="c40fa-177">Average amount of one-way latency.</span></span> <span data-ttu-id="c40fa-178">Относительная односторонняя задержка измеряет задержку между клиентом и сервером.</span><span class="sxs-lookup"><span data-stu-id="c40fa-178">Relative one-way latency measures the delay between the client and the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c40fa-179"><strong>Релативеоневаймакс</strong></span><span class="sxs-lookup"><span data-stu-id="c40fa-179"><strong>RelativeOneWayMax</strong></span></span></p></td>
<td><p><span data-ttu-id="c40fa-180">число с плавающей точкой</span><span class="sxs-lookup"><span data-stu-id="c40fa-180">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c40fa-181">Максимальная сумма односторонняя задержка.</span><span class="sxs-lookup"><span data-stu-id="c40fa-181">Maximum amount of one-way latency.</span></span> <span data-ttu-id="c40fa-182">Относительная односторонняя задержка измеряет задержку между клиентом и сервером.</span><span class="sxs-lookup"><span data-stu-id="c40fa-182">Relative one-way latency measures the delay between the client and the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c40fa-183"><strong>Релативеоневайбурстоккурренцес</strong></span><span class="sxs-lookup"><span data-stu-id="c40fa-183"><strong>RelativeOneWayBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="c40fa-184">целое</span><span class="sxs-lookup"><span data-stu-id="c40fa-184">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c40fa-185">Общее количество односторонних вхождений.</span><span class="sxs-lookup"><span data-stu-id="c40fa-185">Total one-way burst occurrences.</span></span> <span data-ttu-id="c40fa-186">Одновременная передача данных — это передача, при которой данные передаются в непредсказуемые пакеты, а не в устойчивый поток.</span><span class="sxs-lookup"><span data-stu-id="c40fa-186">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span> <span data-ttu-id="c40fa-187">Этот показатель измеряет поток данных между клиентом и сервером.</span><span class="sxs-lookup"><span data-stu-id="c40fa-187">This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c40fa-188"><strong>Релативеоневайбурстденсити</strong></span><span class="sxs-lookup"><span data-stu-id="c40fa-188"><strong>RelativeOneWayBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="c40fa-189">число с плавающей точкой</span><span class="sxs-lookup"><span data-stu-id="c40fa-189">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c40fa-190">Общая односторонняя плотность нагрузки.</span><span class="sxs-lookup"><span data-stu-id="c40fa-190">Total one-way burst density.</span></span> <span data-ttu-id="c40fa-191">Одновременная передача данных — это передача, при которой данные передаются в непредсказуемые пакеты, а не в устойчивый поток.</span><span class="sxs-lookup"><span data-stu-id="c40fa-191">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span> <span data-ttu-id="c40fa-192">Этот показатель измеряет поток данных между клиентом и сервером.</span><span class="sxs-lookup"><span data-stu-id="c40fa-192">This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c40fa-193"><strong>Релативеоневайбурстдуратион</strong></span><span class="sxs-lookup"><span data-stu-id="c40fa-193"><strong>RelativeOneWayBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="c40fa-194">число с плавающей точкой</span><span class="sxs-lookup"><span data-stu-id="c40fa-194">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c40fa-195">Общая продолжительность односторонней длительности.</span><span class="sxs-lookup"><span data-stu-id="c40fa-195">Total one-way burst duration.</span></span> <span data-ttu-id="c40fa-196">Одновременная передача данных — это передача, при которой данные передаются в непредсказуемые пакеты, а не в устойчивый поток.</span><span class="sxs-lookup"><span data-stu-id="c40fa-196">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span> <span data-ttu-id="c40fa-197">Этот показатель измеряет поток данных между клиентом и сервером.</span><span class="sxs-lookup"><span data-stu-id="c40fa-197">This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c40fa-198"><strong>Релативеоневайгапоккурренцес</strong></span><span class="sxs-lookup"><span data-stu-id="c40fa-198"><strong>RelativeOneWayGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="c40fa-199">целое</span><span class="sxs-lookup"><span data-stu-id="c40fa-199">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c40fa-200">Общее количество односторонних вхождений.</span><span class="sxs-lookup"><span data-stu-id="c40fa-200">Total one-way gap occurrences.</span></span> <span data-ttu-id="c40fa-201">Одновременная передача данных — это передача, при которой данные передаются в непредсказуемые пакеты, а не в устойчивый поток. зазоры указывают на задержку между этими пакетами.</span><span class="sxs-lookup"><span data-stu-id="c40fa-201">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts.</span></span> <span data-ttu-id="c40fa-202">Этот показатель измеряет поток данных между клиентом и сервером.</span><span class="sxs-lookup"><span data-stu-id="c40fa-202">This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c40fa-203"><strong>Релативеоневайгапденсити</strong></span><span class="sxs-lookup"><span data-stu-id="c40fa-203"><strong>RelativeOneWayGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="c40fa-204">число с плавающей точкой</span><span class="sxs-lookup"><span data-stu-id="c40fa-204">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c40fa-205">Общая плотность односторонних зазоров.</span><span class="sxs-lookup"><span data-stu-id="c40fa-205">Total one-way gap density.</span></span> <span data-ttu-id="c40fa-206">Одновременная передача данных — это передача, при которой данные передаются в непредсказуемые пакеты, а не в устойчивый поток. зазоры указывают на задержку между этими пакетами.</span><span class="sxs-lookup"><span data-stu-id="c40fa-206">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts.</span></span> <span data-ttu-id="c40fa-207">Этот показатель измеряет поток данных между клиентом и сервером.</span><span class="sxs-lookup"><span data-stu-id="c40fa-207">This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c40fa-208"><strong>Релативеоневайгапдуратион</strong></span><span class="sxs-lookup"><span data-stu-id="c40fa-208"><strong>RelativeOneWayGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="c40fa-209">число с плавающей точкой</span><span class="sxs-lookup"><span data-stu-id="c40fa-209">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c40fa-210">Общая продолжительность односторонних промежутков.</span><span class="sxs-lookup"><span data-stu-id="c40fa-210">Total one-way gap duration.</span></span> <span data-ttu-id="c40fa-211">Одновременная передача данных — это передача, при которой данные передаются в непредсказуемые пакеты, а не в устойчивый поток. зазоры указывают на задержку между этими пакетами.</span><span class="sxs-lookup"><span data-stu-id="c40fa-211">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts.</span></span> <span data-ttu-id="c40fa-212">Этот показатель измеряет поток данных между клиентом и сервером.</span><span class="sxs-lookup"><span data-stu-id="c40fa-212">This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c40fa-213"><strong>Аппликатионшарингтипе</strong></span><span class="sxs-lookup"><span data-stu-id="c40fa-213"><strong>ApplicationSharingType</strong></span></span></p></td>
<td><p><span data-ttu-id="c40fa-214">varChar (256)</span><span class="sxs-lookup"><span data-stu-id="c40fa-214">varChar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c40fa-215">Роль приложения (общий доступ или средство просмотра) и тип контента.</span><span class="sxs-lookup"><span data-stu-id="c40fa-215">Application role (Sharer or Viewer) and content type.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c40fa-216"><strong>Рдптилепроцессинглатенцитотал</strong></span><span class="sxs-lookup"><span data-stu-id="c40fa-216"><strong>RDPTileProcessingLatencyTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="c40fa-217">число с плавающей точкой</span><span class="sxs-lookup"><span data-stu-id="c40fa-217">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c40fa-218">Общее время обработки плиток протокола удаленного рабочего стола (RDP).</span><span class="sxs-lookup"><span data-stu-id="c40fa-218">Total processing time for remote desktop protocol (RDP) tiles.</span></span> <span data-ttu-id="c40fa-219">Общая сумма равна более длительной задержке при просмотре.</span><span class="sxs-lookup"><span data-stu-id="c40fa-219">A higher total equates to a longer delay in the viewing experience.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c40fa-220"><strong>Рдптилепроцессинглатенциавераже</strong></span><span class="sxs-lookup"><span data-stu-id="c40fa-220"><strong>RDPTileProcessingLatencyAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="c40fa-221">число с плавающей точкой</span><span class="sxs-lookup"><span data-stu-id="c40fa-221">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c40fa-222">Среднее время обработки плиток протокола удаленного рабочего стола (RDP).</span><span class="sxs-lookup"><span data-stu-id="c40fa-222">Average processing time for remote desktop protocol (RDP) tiles.</span></span> <span data-ttu-id="c40fa-223">Общая сумма равна более длительной задержке при просмотре.</span><span class="sxs-lookup"><span data-stu-id="c40fa-223">A higher total equates to a longer delay in the viewing experience.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c40fa-224"><strong>Рдптилепроцессинглатенцимакс</strong></span><span class="sxs-lookup"><span data-stu-id="c40fa-224"><strong>RDPTileProcessingLatencyMax</strong></span></span></p></td>
<td><p><span data-ttu-id="c40fa-225">число с плавающей точкой</span><span class="sxs-lookup"><span data-stu-id="c40fa-225">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c40fa-226">Максимальное время обработки плиток протокола удаленного рабочего стола (RDP).</span><span class="sxs-lookup"><span data-stu-id="c40fa-226">Maximum processing time for remote desktop protocol (RDP) tiles.</span></span> <span data-ttu-id="c40fa-227">Общая сумма равна более длительной задержке при просмотре.</span><span class="sxs-lookup"><span data-stu-id="c40fa-227">A higher total equates to a longer delay in the viewing experience.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c40fa-228"><strong>Рдптилепроцессинглатенцибурстоккурренцес</strong></span><span class="sxs-lookup"><span data-stu-id="c40fa-228"><strong>RDPTileProcessingLatencyBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="c40fa-229">целое</span><span class="sxs-lookup"><span data-stu-id="c40fa-229">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c40fa-230">Пакетное повторение на время обработки плиток протокола удаленного рабочего стола (RDP).</span><span class="sxs-lookup"><span data-stu-id="c40fa-230">Burst occurrences in the processing time for remote desktop protocol (RDP) tiles.</span></span> <span data-ttu-id="c40fa-231">Одновременная передача данных — это передача, при которой данные передаются в непредсказуемые пакеты, а не в устойчивый поток.</span><span class="sxs-lookup"><span data-stu-id="c40fa-231">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c40fa-232"><strong>Рдптилепроцессинглатенцибурстденсити</strong></span><span class="sxs-lookup"><span data-stu-id="c40fa-232"><strong>RDPTileProcessingLatencyBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="c40fa-233">число с плавающей точкой</span><span class="sxs-lookup"><span data-stu-id="c40fa-233">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c40fa-234">Ускоренная плотность плиток протокола удаленного рабочего стола (RDP) на время обработки.</span><span class="sxs-lookup"><span data-stu-id="c40fa-234">Burst density in the processing time for remote desktop protocol (RDP) tiles.</span></span> <span data-ttu-id="c40fa-235">Одновременная передача данных — это передача, при которой данные передаются в непредсказуемые пакеты, а не в устойчивый поток.</span><span class="sxs-lookup"><span data-stu-id="c40fa-235">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c40fa-236"><strong>Рдптилепроцессинглатенцибурстдуратион</strong></span><span class="sxs-lookup"><span data-stu-id="c40fa-236"><strong>RDPTileProcessingLatencyBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="c40fa-237">число с плавающей точкой</span><span class="sxs-lookup"><span data-stu-id="c40fa-237">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c40fa-238">Продолжительность разбивки на время обработки плиток протокола удаленного рабочего стола (RDP).</span><span class="sxs-lookup"><span data-stu-id="c40fa-238">Burst duration in the processing time for remote desktop protocol (RDP) tiles.</span></span> <span data-ttu-id="c40fa-239">Одновременная передача данных — это передача, при которой данные передаются в непредсказуемые пакеты, а не в устойчивый поток.</span><span class="sxs-lookup"><span data-stu-id="c40fa-239">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c40fa-240"><strong>Рдптилепроцессинглатенцигапоккурренцес</strong></span><span class="sxs-lookup"><span data-stu-id="c40fa-240"><strong>RDPTileProcessingLatencyGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="c40fa-241">целое</span><span class="sxs-lookup"><span data-stu-id="c40fa-241">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c40fa-242">Случаи пропуска на момент обработки плиток протокола удаленного рабочего стола (RDP).</span><span class="sxs-lookup"><span data-stu-id="c40fa-242">Gap occurrences in the processing time for remote desktop protocol (RDP) tiles.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c40fa-243"><strong>Рдптилепроцессинглатенцигапденсити</strong></span><span class="sxs-lookup"><span data-stu-id="c40fa-243"><strong>RDPTileProcessingLatencyGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="c40fa-244">число с плавающей точкой</span><span class="sxs-lookup"><span data-stu-id="c40fa-244">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c40fa-245">Плотность зазоров во время обработки плиток протокола удаленного рабочего стола (RDP).</span><span class="sxs-lookup"><span data-stu-id="c40fa-245">Gap density in the processing time for remote desktop protocol (RDP) tiles.</span></span> <span data-ttu-id="c40fa-246">Плотность неограниченного промежутка означает более качественный просмотр.</span><span class="sxs-lookup"><span data-stu-id="c40fa-246">Low gap density equates to a better viewing experience.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c40fa-247"><strong>Рдптилепроцессинглатенцигапдуратион</strong></span><span class="sxs-lookup"><span data-stu-id="c40fa-247"><strong>RDPTileProcessingLatencyGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="c40fa-248">число с плавающей точкой</span><span class="sxs-lookup"><span data-stu-id="c40fa-248">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c40fa-249">Продолжительность пропуска для плиток протокола удаленного рабочего стола (RDP).</span><span class="sxs-lookup"><span data-stu-id="c40fa-249">Gap duration in the processing time for remote desktop protocol (RDP) tiles.</span></span> <span data-ttu-id="c40fa-250">Продолжительность коротких промежутков эквивалентна более качественному просмотру.</span><span class="sxs-lookup"><span data-stu-id="c40fa-250">Short gap durations equate to a better viewing experience.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c40fa-251"><strong>Каптуретилератетотал</strong></span><span class="sxs-lookup"><span data-stu-id="c40fa-251"><strong>CaptureTileRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="c40fa-252">число с плавающей точкой</span><span class="sxs-lookup"><span data-stu-id="c40fa-252">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c40fa-253">Общая частота захваченных плиток (в плитках в секунду).</span><span class="sxs-lookup"><span data-stu-id="c40fa-253">Total rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c40fa-254"><strong>Каптуретилератеавераже</strong></span><span class="sxs-lookup"><span data-stu-id="c40fa-254"><strong>CaptureTileRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="c40fa-255">число с плавающей точкой</span><span class="sxs-lookup"><span data-stu-id="c40fa-255">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c40fa-256">Средняя скорость захваченных плиток (в плитках в секунду).</span><span class="sxs-lookup"><span data-stu-id="c40fa-256">Average rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c40fa-257"><strong>Каптуретилератемакс</strong></span><span class="sxs-lookup"><span data-stu-id="c40fa-257"><strong>CaptureTileRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="c40fa-258">число с плавающей точкой</span><span class="sxs-lookup"><span data-stu-id="c40fa-258">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c40fa-259">Максимальная частота захваченных плиток (в плитках в секунду).</span><span class="sxs-lookup"><span data-stu-id="c40fa-259">Maximum rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c40fa-260"><strong>Каптуретилератебурстоккурренцес</strong></span><span class="sxs-lookup"><span data-stu-id="c40fa-260"><strong>CaptureTileRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="c40fa-261">в t</span><span class="sxs-lookup"><span data-stu-id="c40fa-261">in t</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c40fa-262">Пакетное повторение в частоте захваченных плиток (в плитках в секунду).</span><span class="sxs-lookup"><span data-stu-id="c40fa-262">Burst occurrences in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c40fa-263"><strong>Каптуретилератебурстденсити</strong></span><span class="sxs-lookup"><span data-stu-id="c40fa-263"><strong>CaptureTileRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="c40fa-264">число с плавающей точкой</span><span class="sxs-lookup"><span data-stu-id="c40fa-264">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c40fa-265">Плотность разбивки на захваченные плитки (в плитках в секунду).</span><span class="sxs-lookup"><span data-stu-id="c40fa-265">Burst density in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c40fa-266"><strong>Каптуретилератебурстдуратион</strong></span><span class="sxs-lookup"><span data-stu-id="c40fa-266"><strong>CaptureTileRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="c40fa-267">число с плавающей точкой</span><span class="sxs-lookup"><span data-stu-id="c40fa-267">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c40fa-268">Продолжительность разбивки на собранные плитки (в плитках в секунду).</span><span class="sxs-lookup"><span data-stu-id="c40fa-268">Burst duration in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c40fa-269"><strong>Каптуретилератегапоккурренцес</strong></span><span class="sxs-lookup"><span data-stu-id="c40fa-269"><strong>CaptureTileRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="c40fa-270">целое</span><span class="sxs-lookup"><span data-stu-id="c40fa-270">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c40fa-271">Количество повторений в частоте захваченных плиток (в плитках в секунду).</span><span class="sxs-lookup"><span data-stu-id="c40fa-271">Gap occurrences in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c40fa-272"><strong>Каптуретилератегапденсити</strong></span><span class="sxs-lookup"><span data-stu-id="c40fa-272"><strong>CaptureTileRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="c40fa-273">число с плавающей точкой</span><span class="sxs-lookup"><span data-stu-id="c40fa-273">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c40fa-274">Плотность зазоров в процентах захваченных плиток (в плитках в секунду).</span><span class="sxs-lookup"><span data-stu-id="c40fa-274">Gap density in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c40fa-275"><strong>Каптуретилератегапдуратион</strong></span><span class="sxs-lookup"><span data-stu-id="c40fa-275"><strong>CaptureTileRateGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="c40fa-276">число с плавающей точкой</span><span class="sxs-lookup"><span data-stu-id="c40fa-276">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c40fa-277">Продолжительность зазора в процентах собранных плиток (в плитках в секунду).</span><span class="sxs-lookup"><span data-stu-id="c40fa-277">Gap duration in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c40fa-278"><strong>Споиледтилеперценттотал</strong></span><span class="sxs-lookup"><span data-stu-id="c40fa-278"><strong>SpoiledTilePercentTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="c40fa-279">число с плавающей точкой</span><span class="sxs-lookup"><span data-stu-id="c40fa-279">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c40fa-280">Общий процент содержимого, которое не было получено средством просмотра, но было бы удалено и заменено новым содержимым.</span><span class="sxs-lookup"><span data-stu-id="c40fa-280">Total percentage of the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c40fa-281"><strong>Споиледтилеперцентавераже</strong></span><span class="sxs-lookup"><span data-stu-id="c40fa-281"><strong>SpoiledTilePercentAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="c40fa-282">число с плавающей точкой</span><span class="sxs-lookup"><span data-stu-id="c40fa-282">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c40fa-283">Средний процент содержимого, которое не достиго средства просмотра, но было удалено и заменено новым содержимым.</span><span class="sxs-lookup"><span data-stu-id="c40fa-283">Average percentage of the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c40fa-284"><strong>Споиледтилеперцентмакс</strong></span><span class="sxs-lookup"><span data-stu-id="c40fa-284"><strong>SpoiledTilePercentMax</strong></span></span></p></td>
<td><p><span data-ttu-id="c40fa-285">число с плавающей точкой</span><span class="sxs-lookup"><span data-stu-id="c40fa-285">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c40fa-286">Максимальный процент содержимого, которое не было получено средством просмотра, но было бы удалено и заменено новым содержимым.</span><span class="sxs-lookup"><span data-stu-id="c40fa-286">Maximum percentage of the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c40fa-287"><strong>Споиледтилеперцентбурстоккурренцес</strong></span><span class="sxs-lookup"><span data-stu-id="c40fa-287"><strong>SpoiledTilePercentBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="c40fa-288">целое</span><span class="sxs-lookup"><span data-stu-id="c40fa-288">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c40fa-289">Пакетное повторение для содержимого, которое не достиго средства просмотра, а было удалено и заменено новым содержимым.</span><span class="sxs-lookup"><span data-stu-id="c40fa-289">Burst occurrences for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c40fa-290"><strong>Споиледтилеперцентбурстденсити</strong></span><span class="sxs-lookup"><span data-stu-id="c40fa-290"><strong>SpoiledTilePercentBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="c40fa-291">число с плавающей точкой</span><span class="sxs-lookup"><span data-stu-id="c40fa-291">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c40fa-292">Для содержимого, которое не достигают средства просмотра, оно было удалено и заменено новым содержимым.</span><span class="sxs-lookup"><span data-stu-id="c40fa-292">Burst density for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c40fa-293"><strong>Споиледтилеперцентбурстдуратион</strong></span><span class="sxs-lookup"><span data-stu-id="c40fa-293"><strong>SpoiledTilePercentBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="c40fa-294">число с плавающей точкой</span><span class="sxs-lookup"><span data-stu-id="c40fa-294">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c40fa-295">Продолжительность разбивки на содержимое, которое не было получено средством просмотра, но было бы удалено и заменено новым содержимым.</span><span class="sxs-lookup"><span data-stu-id="c40fa-295">Burst duration for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c40fa-296"><strong>Споиледтилеперцентгапоккурренцес</strong></span><span class="sxs-lookup"><span data-stu-id="c40fa-296"><strong>SpoiledTilePercentGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="c40fa-297">целое</span><span class="sxs-lookup"><span data-stu-id="c40fa-297">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c40fa-298">Повторение для содержимого, которое не достиго средства просмотра, но было удалено и заменено новым содержимым.</span><span class="sxs-lookup"><span data-stu-id="c40fa-298">Gap occurrences for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c40fa-299"><strong>Споиледтилеперцентгапденсити</strong></span><span class="sxs-lookup"><span data-stu-id="c40fa-299"><strong>SpoiledTilePercentGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="c40fa-300">число с плавающей точкой</span><span class="sxs-lookup"><span data-stu-id="c40fa-300">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c40fa-301">Плотность зазоров для содержимого, которое не достиго средства просмотра, но было удалено и заменено новым содержимым.</span><span class="sxs-lookup"><span data-stu-id="c40fa-301">Gap density for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c40fa-302"><strong>Споиледтилеперцентгапдуратион</strong></span><span class="sxs-lookup"><span data-stu-id="c40fa-302"><strong>SpoiledTilePercentGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="c40fa-303">число с плавающей точкой</span><span class="sxs-lookup"><span data-stu-id="c40fa-303">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c40fa-304">Продолжительность зазора для содержимого, которое не достиго средства просмотра, но было удалено и заменено новым содержимым.</span><span class="sxs-lookup"><span data-stu-id="c40fa-304">Gap duration for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c40fa-305"><strong>Скрапингфрамератетотал</strong></span><span class="sxs-lookup"><span data-stu-id="c40fa-305"><strong>ScrapingFrameRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="c40fa-306">число с плавающей точкой</span><span class="sxs-lookup"><span data-stu-id="c40fa-306">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c40fa-307">Общее количество кадров, набракованных из источника графики.</span><span class="sxs-lookup"><span data-stu-id="c40fa-307">Total number of frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c40fa-308"><strong>Скрапингфрамератеавераже</strong></span><span class="sxs-lookup"><span data-stu-id="c40fa-308"><strong>ScrapingFrameRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="c40fa-309">число с плавающей точкой</span><span class="sxs-lookup"><span data-stu-id="c40fa-309">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c40fa-310">Среднее количество кадров, набракованных из источника графики.</span><span class="sxs-lookup"><span data-stu-id="c40fa-310">Average number of frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c40fa-311"><strong>Скрапингфрамератемакс</strong></span><span class="sxs-lookup"><span data-stu-id="c40fa-311"><strong>ScrapingFrameRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="c40fa-312">число с плавающей точкой</span><span class="sxs-lookup"><span data-stu-id="c40fa-312">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c40fa-313">Предельное число кадров, которые не побраковано от источника графики.</span><span class="sxs-lookup"><span data-stu-id="c40fa-313">Maximum number of frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c40fa-314"><strong>Скрапингфрамератебурстоккурренцес</strong></span><span class="sxs-lookup"><span data-stu-id="c40fa-314"><strong>ScrapingFrameRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="c40fa-315">целое</span><span class="sxs-lookup"><span data-stu-id="c40fa-315">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c40fa-316">Пакетное повторение в кадре побраковано от источника графики.</span><span class="sxs-lookup"><span data-stu-id="c40fa-316">Burst occurrences in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c40fa-317"><strong>Скрапингфрамератебурстденсити</strong></span><span class="sxs-lookup"><span data-stu-id="c40fa-317"><strong>ScrapingFrameRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="c40fa-318">число с плавающей точкой</span><span class="sxs-lookup"><span data-stu-id="c40fa-318">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c40fa-319">Ускоренная плотность кадров в кадрах, побракованных из источника графики.</span><span class="sxs-lookup"><span data-stu-id="c40fa-319">Burst density in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c40fa-320"><strong>Скрапингфрамератебурстдуратион</strong></span><span class="sxs-lookup"><span data-stu-id="c40fa-320"><strong>ScrapingFrameRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="c40fa-321">число с плавающей точкой</span><span class="sxs-lookup"><span data-stu-id="c40fa-321">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c40fa-322">Продолжительность разбивки кадров в кадре, побракованная от источника графики.</span><span class="sxs-lookup"><span data-stu-id="c40fa-322">Burst duration in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c40fa-323"><strong>Скрапингфрамератегапоккурренцес</strong></span><span class="sxs-lookup"><span data-stu-id="c40fa-323"><strong>ScrapingFrameRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="c40fa-324">целое</span><span class="sxs-lookup"><span data-stu-id="c40fa-324">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c40fa-325">Случаи разрывов в кадрах оббракованы из источника графики.</span><span class="sxs-lookup"><span data-stu-id="c40fa-325">Gap occurrences in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c40fa-326"><strong>Скрапингфрамератегапденсити</strong></span><span class="sxs-lookup"><span data-stu-id="c40fa-326"><strong>ScrapingFrameRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="c40fa-327">число с плавающей точкой</span><span class="sxs-lookup"><span data-stu-id="c40fa-327">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c40fa-328">Плотность зазоров в кадрах, побракованных из источника графики.</span><span class="sxs-lookup"><span data-stu-id="c40fa-328">Gap density in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c40fa-329"><strong>Скрапингфрамератегапдуратион</strong></span><span class="sxs-lookup"><span data-stu-id="c40fa-329"><strong>ScrapingFrameRateGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="c40fa-330">число с плавающей точкой</span><span class="sxs-lookup"><span data-stu-id="c40fa-330">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c40fa-331">Продолжительность зазора в кадрах, побракованных из источника графики.</span><span class="sxs-lookup"><span data-stu-id="c40fa-331">Gap duration in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c40fa-332"><strong>Инкомингтилератетотал</strong></span><span class="sxs-lookup"><span data-stu-id="c40fa-332"><strong>IncomingTileRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="c40fa-333">число с плавающей точкой</span><span class="sxs-lookup"><span data-stu-id="c40fa-333">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c40fa-334">Общая частота входящих кадров, полученных средством просмотра.</span><span class="sxs-lookup"><span data-stu-id="c40fa-334">Total incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c40fa-335"><strong>Инкомингтилератеавераже</strong></span><span class="sxs-lookup"><span data-stu-id="c40fa-335"><strong>IncomingTileRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="c40fa-336">число с плавающей точкой</span><span class="sxs-lookup"><span data-stu-id="c40fa-336">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c40fa-337">Средняя частота входящих кадров, полученная средством просмотра.</span><span class="sxs-lookup"><span data-stu-id="c40fa-337">Average incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c40fa-338"><strong>Инкомингтилератемакс</strong></span><span class="sxs-lookup"><span data-stu-id="c40fa-338"><strong>IncomingTileRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="c40fa-339">число с плавающей точкой</span><span class="sxs-lookup"><span data-stu-id="c40fa-339">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c40fa-340">Максимальное количество входящих частот плиток, полученных средством просмотра.</span><span class="sxs-lookup"><span data-stu-id="c40fa-340">Maximum incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c40fa-341"><strong>Инкомингтилератебурстоккурренцес</strong></span><span class="sxs-lookup"><span data-stu-id="c40fa-341"><strong>IncomingTileRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="c40fa-342">целое</span><span class="sxs-lookup"><span data-stu-id="c40fa-342">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c40fa-343">Пакетное повторение входящего, полученного средством просмотра частоты плиток.</span><span class="sxs-lookup"><span data-stu-id="c40fa-343">Burst occurrences in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c40fa-344"><strong>Инкомингтилератебурстденсити</strong></span><span class="sxs-lookup"><span data-stu-id="c40fa-344"><strong>IncomingTileRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="c40fa-345">число с плавающей точкой</span><span class="sxs-lookup"><span data-stu-id="c40fa-345">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c40fa-346">Многоуровневая плотность во входящих частотах плиток, полученных средством просмотра.</span><span class="sxs-lookup"><span data-stu-id="c40fa-346">Burst density in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c40fa-347"><strong>Инкомингтилератебурстдуратион</strong></span><span class="sxs-lookup"><span data-stu-id="c40fa-347"><strong>IncomingTileRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="c40fa-348">число с плавающей точкой</span><span class="sxs-lookup"><span data-stu-id="c40fa-348">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c40fa-349">Продолжительность пакетной обработки на входящем частоте плиток, полученной средством просмотра.</span><span class="sxs-lookup"><span data-stu-id="c40fa-349">Burst duration in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c40fa-350"><strong>Инкомингтилератегапоккурренцес</strong></span><span class="sxs-lookup"><span data-stu-id="c40fa-350"><strong>IncomingTileRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="c40fa-351">целое</span><span class="sxs-lookup"><span data-stu-id="c40fa-351">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c40fa-352">Количество вхождений во входящих частотах плиток, полученных средством просмотра.</span><span class="sxs-lookup"><span data-stu-id="c40fa-352">Gap occurrences in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c40fa-353"><strong>Инкомингтилератегапденсити</strong></span><span class="sxs-lookup"><span data-stu-id="c40fa-353"><strong>IncomingTileRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="c40fa-354">число с плавающей точкой</span><span class="sxs-lookup"><span data-stu-id="c40fa-354">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c40fa-355">Плотность просветов во входящих частотах плиток, полученных средством просмотра.</span><span class="sxs-lookup"><span data-stu-id="c40fa-355">Gap density in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c40fa-356"><strong>Инкомингтилератегапдуратион</strong></span><span class="sxs-lookup"><span data-stu-id="c40fa-356"><strong>IncomingTileRateGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="c40fa-357">число с плавающей точкой</span><span class="sxs-lookup"><span data-stu-id="c40fa-357">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c40fa-358">Длительность пропуска во входящих частотах плиток, полученных средством просмотра.</span><span class="sxs-lookup"><span data-stu-id="c40fa-358">Gap duration in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c40fa-359"><strong>Инкомингфрамератетотал</strong></span><span class="sxs-lookup"><span data-stu-id="c40fa-359"><strong>IncomingFrameRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="c40fa-360">число с плавающей точкой</span><span class="sxs-lookup"><span data-stu-id="c40fa-360">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c40fa-361">Общая частота входящих кадров, полученных средством просмотра.</span><span class="sxs-lookup"><span data-stu-id="c40fa-361">Total incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c40fa-362"><strong>Инкомингфрамератеавераже</strong></span><span class="sxs-lookup"><span data-stu-id="c40fa-362"><strong>IncomingFrameRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="c40fa-363">число с плавающей точкой</span><span class="sxs-lookup"><span data-stu-id="c40fa-363">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c40fa-364">Средняя частота входящих кадров, полученная средством просмотра.</span><span class="sxs-lookup"><span data-stu-id="c40fa-364">Average incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c40fa-365"><strong>Инкомингфрамератемакс</strong></span><span class="sxs-lookup"><span data-stu-id="c40fa-365"><strong>IncomingFrameRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="c40fa-366">число с плавающей точкой</span><span class="sxs-lookup"><span data-stu-id="c40fa-366">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c40fa-367">Максимальная частота поступающих кадров, полученных средством просмотра.</span><span class="sxs-lookup"><span data-stu-id="c40fa-367">Maximum incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c40fa-368"><strong>Инкомингфрамератебурстоккурренцес</strong></span><span class="sxs-lookup"><span data-stu-id="c40fa-368"><strong>IncomingFrameRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="c40fa-369">целое</span><span class="sxs-lookup"><span data-stu-id="c40fa-369">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c40fa-370">Пакетное повторение во входящих частотах кадров, полученных средством просмотра.</span><span class="sxs-lookup"><span data-stu-id="c40fa-370">Burst occurrences in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c40fa-371"><strong>Инкомингфрамератебурстденсити</strong></span><span class="sxs-lookup"><span data-stu-id="c40fa-371"><strong>IncomingFrameRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="c40fa-372">число с плавающей точкой</span><span class="sxs-lookup"><span data-stu-id="c40fa-372">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c40fa-373">Многоуровневая плотность во входящих частотах кадров, полученных средством просмотра.</span><span class="sxs-lookup"><span data-stu-id="c40fa-373">Burst density in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c40fa-374"><strong>Инкомингфрамератебурстдуратион</strong></span><span class="sxs-lookup"><span data-stu-id="c40fa-374"><strong>IncomingFrameRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="c40fa-375">число с плавающей точкой</span><span class="sxs-lookup"><span data-stu-id="c40fa-375">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c40fa-376">Продолжительность многочастотной обработки кадров, полученная средством просмотра.</span><span class="sxs-lookup"><span data-stu-id="c40fa-376">Burst duration in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c40fa-377"><strong>Инкомингфрамератегапоккурренцес</strong></span><span class="sxs-lookup"><span data-stu-id="c40fa-377"><strong>IncomingFrameRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="c40fa-378">целое</span><span class="sxs-lookup"><span data-stu-id="c40fa-378">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c40fa-379">Пропуск вхождений во входной частоте кадров, полученной средством просмотра.</span><span class="sxs-lookup"><span data-stu-id="c40fa-379">Gap occurrences in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c40fa-380"><strong>Инкомингфрамератегапденсити</strong></span><span class="sxs-lookup"><span data-stu-id="c40fa-380"><strong>IncomingFrameRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="c40fa-381">число с плавающей точкой</span><span class="sxs-lookup"><span data-stu-id="c40fa-381">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c40fa-382">Плотность зазоров во входящих частотах кадров, полученных средством просмотра.</span><span class="sxs-lookup"><span data-stu-id="c40fa-382">Gap density in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c40fa-383"><strong>Инкомингфрамератедуратион</strong></span><span class="sxs-lookup"><span data-stu-id="c40fa-383"><strong>IncomingFrameRateDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="c40fa-384">число с плавающей точкой</span><span class="sxs-lookup"><span data-stu-id="c40fa-384">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c40fa-385">Длительность промежутка во входящих частотах кадров, полученных средством просмотра.</span><span class="sxs-lookup"><span data-stu-id="c40fa-385">Gap duration in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c40fa-386"><strong>Аутгоингтилератетотал</strong></span><span class="sxs-lookup"><span data-stu-id="c40fa-386"><strong>OutgoingTileRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="c40fa-387">число с плавающей точкой</span><span class="sxs-lookup"><span data-stu-id="c40fa-387">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c40fa-388">Общая частота исходящих плиток для отправителя.</span><span class="sxs-lookup"><span data-stu-id="c40fa-388">Total outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c40fa-389"><strong>Аутгоингтилератеавераже</strong></span><span class="sxs-lookup"><span data-stu-id="c40fa-389"><strong>OutgoingTileRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="c40fa-390">число с плавающей точкой</span><span class="sxs-lookup"><span data-stu-id="c40fa-390">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c40fa-391">Средняя исходящая частота плиток для отправителя.</span><span class="sxs-lookup"><span data-stu-id="c40fa-391">Average outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c40fa-392"><strong>Аутгоингтилератемакс</strong></span><span class="sxs-lookup"><span data-stu-id="c40fa-392"><strong>OutgoingTileRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="c40fa-393">число с плавающей точкой</span><span class="sxs-lookup"><span data-stu-id="c40fa-393">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c40fa-394">Максимальная исходящая ставка плиток для отправителя.</span><span class="sxs-lookup"><span data-stu-id="c40fa-394">Maximum outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c40fa-395"><strong>Аутгоингтилератебурстоккурренцес</strong></span><span class="sxs-lookup"><span data-stu-id="c40fa-395"><strong>OutgoingTileRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="c40fa-396">целое</span><span class="sxs-lookup"><span data-stu-id="c40fa-396">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c40fa-397">Пакетное повторение исходящих плиток для отправителя.</span><span class="sxs-lookup"><span data-stu-id="c40fa-397">Burst occurrences in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c40fa-398"><strong>Аутгоингтилератебурстденсити</strong></span><span class="sxs-lookup"><span data-stu-id="c40fa-398"><strong>OutgoingTileRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="c40fa-399">число с плавающей точкой</span><span class="sxs-lookup"><span data-stu-id="c40fa-399">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c40fa-400">Плотность разбивки на выходящую частоту плиток для отправителя.</span><span class="sxs-lookup"><span data-stu-id="c40fa-400">Burst density in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c40fa-401"><strong>Аутгоингтилератебурстдуратион</strong></span><span class="sxs-lookup"><span data-stu-id="c40fa-401"><strong>OutgoingTileRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="c40fa-402">число с плавающей точкой</span><span class="sxs-lookup"><span data-stu-id="c40fa-402">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c40fa-403">Продолжительность разбивки на исходящую частоту плиток для отправителя.</span><span class="sxs-lookup"><span data-stu-id="c40fa-403">Burst duration in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c40fa-404"><strong>Аутгоингтилератегапоккурренцес</strong></span><span class="sxs-lookup"><span data-stu-id="c40fa-404"><strong>OutgoingTileRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="c40fa-405">целое</span><span class="sxs-lookup"><span data-stu-id="c40fa-405">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c40fa-406">Количество повторений в исходящих частотах плиток для отправителя.</span><span class="sxs-lookup"><span data-stu-id="c40fa-406">Gap occurrences in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c40fa-407"><strong>Аутгоингтилератегапденсити</strong></span><span class="sxs-lookup"><span data-stu-id="c40fa-407"><strong>OutgoingTileRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="c40fa-408">число с плавающей точкой</span><span class="sxs-lookup"><span data-stu-id="c40fa-408">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c40fa-409">Плотность зазоров для отправителя за исходящую частоту плиток.</span><span class="sxs-lookup"><span data-stu-id="c40fa-409">Gap density in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c40fa-410"><strong>Аутгоингтилератегапдуратион</strong></span><span class="sxs-lookup"><span data-stu-id="c40fa-410"><strong>OutgoingTileRateGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="c40fa-411">число с плавающей точкой</span><span class="sxs-lookup"><span data-stu-id="c40fa-411">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c40fa-412">Продолжительность зазора для отправителя с исходящим рейтингом.</span><span class="sxs-lookup"><span data-stu-id="c40fa-412">Gap duration in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c40fa-413"><strong>Аутгоингфрамератетотал</strong></span><span class="sxs-lookup"><span data-stu-id="c40fa-413"><strong>OutgoingFrameRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="c40fa-414">число с плавающей точкой</span><span class="sxs-lookup"><span data-stu-id="c40fa-414">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c40fa-415">Общая частота исходящих кадров для отправителя.</span><span class="sxs-lookup"><span data-stu-id="c40fa-415">Total outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c40fa-416"><strong>Аутгоингфрамератеавераже</strong></span><span class="sxs-lookup"><span data-stu-id="c40fa-416"><strong>OutgoingFrameRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="c40fa-417">число с плавающей точкой</span><span class="sxs-lookup"><span data-stu-id="c40fa-417">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c40fa-418">средняя исходящая частота кадров для отправителя.</span><span class="sxs-lookup"><span data-stu-id="c40fa-418">average outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c40fa-419"><strong>Аутгоингфрамератемакс</strong></span><span class="sxs-lookup"><span data-stu-id="c40fa-419"><strong>OutgoingFrameRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="c40fa-420">число с плавающей точкой</span><span class="sxs-lookup"><span data-stu-id="c40fa-420">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c40fa-421">Максимальная исходящая частота кадров для отправителя.</span><span class="sxs-lookup"><span data-stu-id="c40fa-421">Maximum outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c40fa-422"><strong>Аутгоингфрамератебурстоккурренцес</strong></span><span class="sxs-lookup"><span data-stu-id="c40fa-422"><strong>OutgoingFrameRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="c40fa-423">целое</span><span class="sxs-lookup"><span data-stu-id="c40fa-423">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c40fa-424">Пакетное повторение в исходящих частотах кадров для отправителя.</span><span class="sxs-lookup"><span data-stu-id="c40fa-424">Burst occurrences in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c40fa-425"><strong>Аутгоингфрамератебурстденсити</strong></span><span class="sxs-lookup"><span data-stu-id="c40fa-425"><strong>OutgoingFrameRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="c40fa-426">число с плавающей точкой</span><span class="sxs-lookup"><span data-stu-id="c40fa-426">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c40fa-427">В исходящих частотах кадров для отправителя — это пакетная плотность.</span><span class="sxs-lookup"><span data-stu-id="c40fa-427">Burst density in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c40fa-428"><strong>Аутгоингфрамератебурстдуратион</strong></span><span class="sxs-lookup"><span data-stu-id="c40fa-428"><strong>OutgoingFrameRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="c40fa-429">число с плавающей точкой</span><span class="sxs-lookup"><span data-stu-id="c40fa-429">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c40fa-430">Продолжительность разбивки кадров в исходящей частотной скорости для отправителя.</span><span class="sxs-lookup"><span data-stu-id="c40fa-430">Burst duration in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c40fa-431"><strong>Аутгоингфрамератегапоккурренцес</strong></span><span class="sxs-lookup"><span data-stu-id="c40fa-431"><strong>OutgoingFrameRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="c40fa-432">целое</span><span class="sxs-lookup"><span data-stu-id="c40fa-432">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c40fa-433">Количество повторений в исходящей частоте кадров для отправителя.</span><span class="sxs-lookup"><span data-stu-id="c40fa-433">Gap occurrences in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c40fa-434"><strong>Аутгоингфрамератегапденсити</strong></span><span class="sxs-lookup"><span data-stu-id="c40fa-434"><strong>OutgoingFrameRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="c40fa-435">число с плавающей точкой</span><span class="sxs-lookup"><span data-stu-id="c40fa-435">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c40fa-436">Плотность зазоров в исходящих частотах кадров для отправителя.</span><span class="sxs-lookup"><span data-stu-id="c40fa-436">Gap density in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c40fa-437"><strong>Аутгоингфрамератегапдуратион</strong></span><span class="sxs-lookup"><span data-stu-id="c40fa-437"><strong>OutgoingFrameRateGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="c40fa-438">число с плавающей точкой</span><span class="sxs-lookup"><span data-stu-id="c40fa-438">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c40fa-439">Длительность промежутка в исходящих частотах кадров для отправителя.</span><span class="sxs-lookup"><span data-stu-id="c40fa-439">Gap duration in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c40fa-440"><strong>Аверажеректанглехеигхт</strong></span><span class="sxs-lookup"><span data-stu-id="c40fa-440"><strong>AverageRectangleHeight</strong></span></span></p></td>
<td><p><span data-ttu-id="c40fa-441">целое</span><span class="sxs-lookup"><span data-stu-id="c40fa-441">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c40fa-442">Средняя высота разрешающей способности видео (в пикселях).</span><span class="sxs-lookup"><span data-stu-id="c40fa-442">Average video resolution height, in pixels.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c40fa-443"><strong>Аверажеректанглевидс</strong></span><span class="sxs-lookup"><span data-stu-id="c40fa-443"><strong>AverageRectangleWidth</strong></span></span></p></td>
<td><p><span data-ttu-id="c40fa-444">целое</span><span class="sxs-lookup"><span data-stu-id="c40fa-444">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c40fa-445">Средняя ширина разрешающей способности видео в пикселях.</span><span class="sxs-lookup"><span data-stu-id="c40fa-445">Average video resolution width, in pixels.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c40fa-446"><strong>443</strong></span><span class="sxs-lookup"><span data-stu-id="c40fa-446"><strong>Inbound</strong></span></span></p></td>
<td><p><span data-ttu-id="c40fa-447">бит</span><span class="sxs-lookup"><span data-stu-id="c40fa-447">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c40fa-448">Средняя частота кадров (в кадрах в секунду) для входящих передач.</span><span class="sxs-lookup"><span data-stu-id="c40fa-448">Average frame rate (in frames per second) for inbound transmissions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c40fa-449"><strong>Исходящее</strong></span><span class="sxs-lookup"><span data-stu-id="c40fa-449"><strong>Outbound</strong></span></span></p></td>
<td><p><span data-ttu-id="c40fa-450">бит</span><span class="sxs-lookup"><span data-stu-id="c40fa-450">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c40fa-451">Средняя частота кадров (в кадрах в секунду) для исходящих передач.</span><span class="sxs-lookup"><span data-stu-id="c40fa-451">Average frame rate (in frames per second) for outbound transmissions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c40fa-452"><strong>Сендерискаллерпаи</strong></span><span class="sxs-lookup"><span data-stu-id="c40fa-452"><strong>SenderIsCallerPAI</strong></span></span></p></td>
<td><p><span data-ttu-id="c40fa-453">бит</span><span class="sxs-lookup"><span data-stu-id="c40fa-453">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c40fa-454">1 — направление потока для вызываемого абонента.</span><span class="sxs-lookup"><span data-stu-id="c40fa-454">1 means the stream direction is from the caller to callee.</span></span></p>
<p><span data-ttu-id="c40fa-455">0 — направление потока из вызываемого объекта вызывающему абоненту.</span><span class="sxs-lookup"><span data-stu-id="c40fa-455">0 means the stream direction is from the callee to the caller.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

