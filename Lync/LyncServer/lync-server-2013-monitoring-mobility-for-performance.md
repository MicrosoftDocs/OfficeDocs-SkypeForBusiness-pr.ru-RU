---
title: 'Lync Server 2013: наблюдение за производительностью мобильных устройств'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Monitoring mobility for performance
ms:assetid: 9c831c63-9a7d-48ec-9118-f8a7e80ddd04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690033(v=OCS.15)
ms:contentKeyID: 48184908
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3532a6ebb8d8b095383f0737083d4b070e3aa882
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42149298"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="monitoring-mobility-for-performance-in-lync-server-2013"></a><span data-ttu-id="bfb30-102">Наблюдение за производительностью мобильных устройств в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bfb30-102">Monitoring mobility for performance in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bfb30-103">_**Последнее изменение темы:** 2013-02-14_</span><span class="sxs-lookup"><span data-stu-id="bfb30-103">_**Topic Last Modified:** 2013-02-14_</span></span>

<span data-ttu-id="bfb30-104">Служба Mobility Server Mobility Service (MCX) и веб-API объединенных коммуникаций (UCWA) увеличивают нагрузку на серверы переднего плана и пулы переднего плана.</span><span class="sxs-lookup"><span data-stu-id="bfb30-104">The Lync Server Mobility Service (Mcx) and the Unified Communications Web API (UCWA) increase the load on Front End Servers and Front End pools.</span></span> <span data-ttu-id="bfb30-105">Мобильные устройства, которые поддерживают подключение к серверу, даже если мобильное приложение свернуто, например устройства Android и Nokia, работающие под управлением Lync 2010 Mobile, а также устройства с Android и Apple, работающие под управлением Lync 2013 Mobile, накладывают большую нагрузку, чем устройства, которые разрыв подключения к серверу, когда мобильное приложение свернуто.</span><span class="sxs-lookup"><span data-stu-id="bfb30-105">Mobile devices that maintain a connection to the server even when the mobile application is minimized, such as Android and Nokia devices running Lync 2010 Mobile, as well as Android and Apple devices running Lync 2013 Mobile, impose a greater load than devices that terminate their connection to the server when the mobile application is minimized.</span></span> <span data-ttu-id="bfb30-106">По мере роста использования мобильных устройств необходимо следить за производительностью мобильных устройств, чтобы определить, когда нужно увеличить емкость.</span><span class="sxs-lookup"><span data-stu-id="bfb30-106">As your mobility usage increases, you must monitor mobility performance to determine when you need to increase your capacity.</span></span>

<span data-ttu-id="bfb30-107">Некоторые ограничения, влияющие на производительность мобильности:</span><span class="sxs-lookup"><span data-stu-id="bfb30-107">Several limits influence mobility performance:</span></span>

  - <span data-ttu-id="bfb30-108">доступная память;</span><span class="sxs-lookup"><span data-stu-id="bfb30-108">Available memory</span></span>

  - <span data-ttu-id="bfb30-109">ограничение очереди запросов;</span><span class="sxs-lookup"><span data-stu-id="bfb30-109">Request queue limit</span></span>

  - <span data-ttu-id="bfb30-110">одновременные подключения;</span><span class="sxs-lookup"><span data-stu-id="bfb30-110">Concurrent connections</span></span>

  - <span data-ttu-id="bfb30-111">длина очереди IIS.</span><span class="sxs-lookup"><span data-stu-id="bfb30-111">IIS queue length</span></span>

<span data-ttu-id="bfb30-112">Другие ограничения на серверах, которые могут повлиять на производительность мобильных устройств, могут быть не более двенадцати, чем двенадцать одновременных входов, проверки подлинности, продления сеанса и завершения.</span><span class="sxs-lookup"><span data-stu-id="bfb30-112">Other limits on servers that can influence mobility performance are a maximum of twelve concurrent sign-ins, authentications, session renewals, and terminations.</span></span> <span data-ttu-id="bfb30-113">В большинстве развертываний эти максимальные значения не нуждаются в изменении.</span><span class="sxs-lookup"><span data-stu-id="bfb30-113">These maximums do not need to be modified for most deployments.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="bfb30-114">Содержание</span><span class="sxs-lookup"><span data-stu-id="bfb30-114">In This Section</span></span>

  - [<span data-ttu-id="bfb30-115">Мониторинг пределов объема памяти сервера в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bfb30-115">Monitoring for server memory capacity limits in Lync Server 2013</span></span>](lync-server-2013-monitoring-for-server-memory-capacity-limits.md)

  - [<span data-ttu-id="bfb30-116">Мониторинг службы Mobility Service и использования UCWA в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bfb30-116">Monitoring Mobility Service and UCWA usage in Lync Server 2013</span></span>](lync-server-2013-monitoring-mobility-service-and-ucwa-usage.md)

  - [<span data-ttu-id="bfb30-117">Настройка службы Mobility Service для высокой производительности в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bfb30-117">Configuring Mobility Service for high performance in Lync Server 2013</span></span>](lync-server-2013-configuring-mobility-service-for-high-performance.md)

  - [<span data-ttu-id="bfb30-118">Мониторинг файлов журнала трассировки запросов IIS в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bfb30-118">Monitoring IIS request tracing log files in Lync Server 2013</span></span>](lync-server-2013-monitoring-iis-request-tracing-log-files.md)

  - [<span data-ttu-id="bfb30-119">Счетчики производительности мобильных устройств в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bfb30-119">Mobility performance counters in Lync Server 2013</span></span>](lync-server-2013-mobility-performance-counters.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

