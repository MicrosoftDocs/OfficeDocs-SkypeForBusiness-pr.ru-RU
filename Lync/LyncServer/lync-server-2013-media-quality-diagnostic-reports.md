---
title: 'Lync Server 2013: диагностические отчеты по качеству мультимедиа'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Media Quality Diagnostic Reports
ms:assetid: ea61428e-a1d5-4189-aae6-3db19ddc5cf2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615044(v=OCS.15)
ms:contentKeyID: 48185935
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 058c12ed9f1b07df885e9e7b90f43780043cdf56
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48500696"
---
# <a name="media-quality-diagnostic-reports-in-lync-server-2013"></a><span data-ttu-id="dda71-102">Диагностические отчеты по качеству мультимедиа в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dda71-102">Media Quality Diagnostic Reports in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dda71-103">_**Последнее изменение темы:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="dda71-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="dda71-104">Диагностический отчет по качеству мультимедиа предоставляет сведения о качестве вызовов, а также диагностические сведения для неудачных вызовов.</span><span class="sxs-lookup"><span data-stu-id="dda71-104">The Media Quality Diagnostic Reports provide information about call quality, and diagnostic and troubleshooting information for failed calls.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="dda71-105">Содержание</span><span class="sxs-lookup"><span data-stu-id="dda71-105">In This Section</span></span>

  - <span data-ttu-id="dda71-106">[Сводный отчет по качеству мультимедиа в Lync Server 2013](lync-server-2013-media-quality-summary-report.md)     Предоставляет общие данные о качестве конечных точек, в том числе одноранговые вызовы для корпоративной голосовой связи, звонки корпоративной голосовой связи и вызовы, которые зависят, по крайней мере, частично в телефонной сети общего пользования (PSTN).</span><span class="sxs-lookup"><span data-stu-id="dda71-106">[Media Quality Summary Report in Lync Server 2013](lync-server-2013-media-quality-summary-report.md)   Provides overall quality data for different endpoint types, including Enterprise Voice peer-to-peer calls, Enterprise Voice conference calls, and calls that rely, at least in part, on the public switched telephone network (PSTN).</span></span>

  - <span data-ttu-id="dda71-107">[Отчет по сравнению качества мультимедиа в Lync Server 2013](lync-server-2013-media-quality-comparison-report.md)     Обеспечивает сравнение значений качества звонков для различных типов голосовых вызовов (например, звонки, совершенные по беспроводной сети и звонки, выполняемые через проводное подключение).</span><span class="sxs-lookup"><span data-stu-id="dda71-107">[Media Quality Comparison Report in Lync Server 2013](lync-server-2013-media-quality-comparison-report.md)   Provides a comparison of call quality values for different types of audio calls (for example, calls made over a wireless network vs. calls made across a wired connection).</span></span>

  - <span data-ttu-id="dda71-108">[Отчет о производительности сервера в Lync server 2013](lync-server-2013-server-performance-report.md)     Список серверов, на которых возникли проблемы в большинстве случаев, на основе измерений таких ключевых показателей качества, как снижение замедления, потери пакетов и колебаний.</span><span class="sxs-lookup"><span data-stu-id="dda71-108">[Server Performance Report in Lync Server 2013](lync-server-2013-server-performance-report.md)   Lists the servers that have experienced the most problems, based on measurements of such key quality metrics as degradation, packet loss, and jitter.</span></span>

  - <span data-ttu-id="dda71-109">[Отчет о местоположении в Lync Server 2013](lync-server-2013-location-report.md)     Содержит список сетевых расположений и сводку по качеству мультимедиа вызовов, происходящих в каждом расположении.</span><span class="sxs-lookup"><span data-stu-id="dda71-109">[Location Report in Lync Server 2013](lync-server-2013-location-report.md)   Provides a list of network locations and a summary of the media quality of the calls that occur at each location.</span></span> <span data-ttu-id="dda71-110">В данном отчете расположения основываются на IP-адресах подсетей.</span><span class="sxs-lookup"><span data-stu-id="dda71-110">For purposes of this report, locations are based on IP subnets.</span></span>

  - <span data-ttu-id="dda71-111">[Отчет по устройствам в Lync Server 2013](lync-server-2013-device-report.md)     Предоставляет сводку по устройствам, используемым для вызовов корпоративной голосовой связи, и включает в себя среднее качество передачи звонков по устройствам.</span><span class="sxs-lookup"><span data-stu-id="dda71-111">[Device Report in Lync Server 2013](lync-server-2013-device-report.md)   Provides a summary of devices that are used for Enterprise Voice calls and it includes the average media quality of the calls by device.</span></span>

  - <span data-ttu-id="dda71-112">[Отчет по списку обзвона в Lync Server 2013](lync-server-2013-call-list-report.md)     Предоставляет подробные сведения о телефонных вызовах, выполненных или полученных в Организации.</span><span class="sxs-lookup"><span data-stu-id="dda71-112">[Call List Report in Lync Server 2013](lync-server-2013-call-list-report.md)   Provides detailed information about phone calls made or received within your organization.</span></span>

  - <span data-ttu-id="dda71-113">[Подробный отчет о вызовах в Lync Server 2013](lync-server-2013-call-detail-report.md)     Предоставляет подробные сведения о телефонных вызовах, выполненных или полученных в Организации.</span><span class="sxs-lookup"><span data-stu-id="dda71-113">[Call Detail Report in Lync Server 2013](lync-server-2013-call-detail-report.md)   Provides detailed information about phone calls made from or received within your organization.</span></span>

  - <span data-ttu-id="dda71-114">[Отчет по тенденциям качества мультимедиа на сервере в Lync Server 2013](lync-server-2013-server-media-quality-trend-report.md)     Предоставляет способ для графического сравнения до 5 серверов на таких метриках качества взаимодействия, как громкость вызовов, процент неудовлетворительных вызовов, потеря пакетов и колебание.</span><span class="sxs-lookup"><span data-stu-id="dda71-114">[Server Media Quality Trend Report in Lync Server 2013](lync-server-2013-server-media-quality-trend-report.md)   Provides a way for you to graphically compare up to 5 servers on Quality of Experience metrics such as call volume, poor call percentage, packet loss, and jitter.</span></span>

  - <span data-ttu-id="dda71-115">[Отчет по распределению метрик качества мультимедиа в Lync Server 2013](lync-server-2013-media-quality-metrics-distribution-report.md)     Предоставляет график, отображающий значения распространения для метрики качества взаимодействия, такие как нарушение или потеря пакетов.</span><span class="sxs-lookup"><span data-stu-id="dda71-115">[The Media Quality Metrics Distribution Report in Lync Server 2013](lync-server-2013-media-quality-metrics-distribution-report.md)   Provides a graph that shows the distribution values for a Quality of Experience metric such as jitter or packet loss.</span></span>

  - <span data-ttu-id="dda71-116">[Отчет о тенденциях расположения в Lync Server 2013](lync-server-2013-location-trend-report.md)     Предоставляет сведения о тенденциях качества звонков для сетевых расположений.</span><span class="sxs-lookup"><span data-stu-id="dda71-116">[Location Trend Report in Lync Server 2013](lync-server-2013-location-trend-report.md)   Provides call quality trend information for network locations.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

