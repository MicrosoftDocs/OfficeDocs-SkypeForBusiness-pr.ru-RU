---
title: 'Lync Server 2013: отчеты диагностики качества мультимедиа'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Media Quality Diagnostic Reports
ms:assetid: ea61428e-a1d5-4189-aae6-3db19ddc5cf2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615044(v=OCS.15)
ms:contentKeyID: 48185935
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 05836ea853c89b132d39eaaba1b66056fa958072
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34827335"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="media-quality-diagnostic-reports-in-lync-server-2013"></a><span data-ttu-id="75278-102">Отчеты диагностики качества мультимедиа в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="75278-102">Media Quality Diagnostic Reports in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="75278-103">_**Тема последнего изменения:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="75278-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="75278-104">Диагностический отчет по качеству мультимедиа предоставляет сведения о качестве вызовов, а также диагностические сведения для неудачных вызовов.</span><span class="sxs-lookup"><span data-stu-id="75278-104">The Media Quality Diagnostic Reports provide information about call quality, and diagnostic and troubleshooting information for failed calls.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="75278-105">Содержание</span><span class="sxs-lookup"><span data-stu-id="75278-105">In This Section</span></span>

  - <span data-ttu-id="75278-106">[Сводный отчет о качестве качества мультимедиа в Lync Server 2013](lync-server-2013-media-quality-summary-report.md)   обеспечивает общие данные по качеству для разных типов конечных точек, в том числе одноранговые звонки в корпоративную голосовую почту, а также звонки по крайней мере в частях общедоступной сети. Коммутируемая телефонная сеть (КТСОП).</span><span class="sxs-lookup"><span data-stu-id="75278-106">[Media Quality Summary Report in Lync Server 2013](lync-server-2013-media-quality-summary-report.md)   Provides overall quality data for different endpoint types, including Enterprise Voice peer-to-peer calls, Enterprise Voice conference calls, and calls that rely, at least in part, on the public switched telephone network (PSTN).</span></span>

  - <span data-ttu-id="75278-107">[Отчет о сравнении качества мультимедиа в Lync Server 2013](lync-server-2013-media-quality-comparison-report.md)   обеспечивает сравнение значений качества звонков для разных типов голосовых звонков (например, звонков в рамках беспроводной сети и звонков через проводное соединение).</span><span class="sxs-lookup"><span data-stu-id="75278-107">[Media Quality Comparison Report in Lync Server 2013](lync-server-2013-media-quality-comparison-report.md)   Provides a comparison of call quality values for different types of audio calls (for example, calls made over a wireless network vs. calls made across a wired connection).</span></span>

  - <span data-ttu-id="75278-108">[Отчет о производительности сервера в Lync Server 2013](lync-server-2013-server-performance-report.md)   содержит перечень серверов, которые столкнулись с большинством проблем, основываясь на измерениях таких показателей качества, как снижение замедлений, потерь пакетов и колебаний.</span><span class="sxs-lookup"><span data-stu-id="75278-108">[Server Performance Report in Lync Server 2013](lync-server-2013-server-performance-report.md)   Lists the servers that have experienced the most problems, based on measurements of such key quality metrics as degradation, packet loss, and jitter.</span></span>

  - <span data-ttu-id="75278-109">[Отчет о расположении в Lync Server 2013](lync-server-2013-location-report.md)   содержит список сетевых расположений и сводку о качестве их качества при звонках, происходящих в каждом месте.</span><span class="sxs-lookup"><span data-stu-id="75278-109">[Location Report in Lync Server 2013](lync-server-2013-location-report.md)   Provides a list of network locations and a summary of the media quality of the calls that occur at each location.</span></span> <span data-ttu-id="75278-110">В данном отчете расположения основываются на IP-адресах подсетей.</span><span class="sxs-lookup"><span data-stu-id="75278-110">For purposes of this report, locations are based on IP subnets.</span></span>

  - <span data-ttu-id="75278-111">[Отчет об устройствах в Lync Server 2013](lync-server-2013-device-report.md)   предоставляет сводку по устройствам, которые используются для корпоративных голосовых звонков, а также среднее качество звонков на устройстве.</span><span class="sxs-lookup"><span data-stu-id="75278-111">[Device Report in Lync Server 2013](lync-server-2013-device-report.md)   Provides a summary of devices that are used for Enterprise Voice calls and it includes the average media quality of the calls by device.</span></span>

  - <span data-ttu-id="75278-112">[Отчет "список обзвона" в Lync Server 2013](lync-server-2013-call-list-report.md)   содержит подробную информацию о телефонных звонках, совершенных и полученных в Организации.</span><span class="sxs-lookup"><span data-stu-id="75278-112">[Call List Report in Lync Server 2013](lync-server-2013-call-list-report.md)   Provides detailed information about phone calls made or received within your organization.</span></span>

  - <span data-ttu-id="75278-113">[Подробный отчет о звонке в Lync Server 2013](lync-server-2013-call-detail-report.md)   предоставляет подробные сведения о телефонных звонках, совершенных из вашей организации или полученных внутри нее.</span><span class="sxs-lookup"><span data-stu-id="75278-113">[Call Detail Report in Lync Server 2013](lync-server-2013-call-detail-report.md)   Provides detailed information about phone calls made from or received within your organization.</span></span>

  - <span data-ttu-id="75278-114">[Отчет о тенденциях качества передачи данных сервера в Lync Server 2013](lync-server-2013-server-media-quality-trend-report.md)   предоставляет способ для графического сравнения до 5 серверов в метриках качества взаимодействия, таких как громкость звонка, процент неудовлетворительного звонка, потеря пакетов и нарушение колебаний.</span><span class="sxs-lookup"><span data-stu-id="75278-114">[Server Media Quality Trend Report in Lync Server 2013](lync-server-2013-server-media-quality-trend-report.md)   Provides a way for you to graphically compare up to 5 servers on Quality of Experience metrics such as call volume, poor call percentage, packet loss, and jitter.</span></span>

  - <span data-ttu-id="75278-115">[Отчет о распределении показателей качества мультимедиа в Lync Server 2013](lync-server-2013-media-quality-metrics-distribution-report.md)   предоставляет граф, отображающий значения распределения для метрики качества взаимодействия, такие как нарушение или потеря пакетов.</span><span class="sxs-lookup"><span data-stu-id="75278-115">[The Media Quality Metrics Distribution Report in Lync Server 2013](lync-server-2013-media-quality-metrics-distribution-report.md)   Provides a graph that shows the distribution values for a Quality of Experience metric such as jitter or packet loss.</span></span>

  - <span data-ttu-id="75278-116">[Отчет о тенденциях расположения в Lync Server 2013](lync-server-2013-location-trend-report.md)   обеспечивает сведения о тенденциях качества связи для сетевых расположений.</span><span class="sxs-lookup"><span data-stu-id="75278-116">[Location Trend Report in Lync Server 2013](lync-server-2013-location-trend-report.md)   Provides call quality trend information for network locations.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

