---
title: 'Lync Server 2013: наблюдение за производительностью мобильных устройств'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Monitoring mobility for performance
ms:assetid: 9c831c63-9a7d-48ec-9118-f8a7e80ddd04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690033(v=OCS.15)
ms:contentKeyID: 48184908
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b3b6cbdefcb7c78f68fe8838109dea3be5b8203d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34826635"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="monitoring-mobility-for-performance-in-lync-server-2013"></a><span data-ttu-id="2614f-102">Мониторинг мобильных устройств для повышения производительности в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2614f-102">Monitoring mobility for performance in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2614f-103">_**Тема последнего изменения:** 2013-02-14_</span><span class="sxs-lookup"><span data-stu-id="2614f-103">_**Topic Last Modified:** 2013-02-14_</span></span>

<span data-ttu-id="2614f-104">Служба мобильной связи Lync Server (МККС) и веб-интерфейс единой системы обмена сообщениями (УКВА) увеличивают нагрузку на сервер переднего плана и пулы интерфейсов.</span><span class="sxs-lookup"><span data-stu-id="2614f-104">The Lync Server Mobility Service (Mcx) and the Unified Communications Web API (UCWA) increase the load on Front End Servers and Front End pools.</span></span> <span data-ttu-id="2614f-105">Мобильные устройства, поддерживающие подключение к серверу даже в том случае, если мобильное приложение свернуто, например устройства Android и Nokia, работающие под управлением Lync 2010 Mobile, а также устройства Android и Apple, работающие под управлением Lync 2013 для мобильных устройств, выпускают больше нагрузки, чем устройства, которые прерывать соединение с сервером, когда мобильное приложение свернуто.</span><span class="sxs-lookup"><span data-stu-id="2614f-105">Mobile devices that maintain a connection to the server even when the mobile application is minimized, such as Android and Nokia devices running Lync 2010 Mobile, as well as Android and Apple devices running Lync 2013 Mobile, impose a greater load than devices that terminate their connection to the server when the mobile application is minimized.</span></span> <span data-ttu-id="2614f-106">As your mobility usage increases, you must monitor mobility performance to determine when you need to increase your capacity.</span><span class="sxs-lookup"><span data-stu-id="2614f-106">As your mobility usage increases, you must monitor mobility performance to determine when you need to increase your capacity.</span></span>

<span data-ttu-id="2614f-107">Некоторые ограничения, влияющие на производительность мобильности:</span><span class="sxs-lookup"><span data-stu-id="2614f-107">Several limits influence mobility performance:</span></span>

  - <span data-ttu-id="2614f-108">доступная память;</span><span class="sxs-lookup"><span data-stu-id="2614f-108">Available memory</span></span>

  - <span data-ttu-id="2614f-109">ограничение очереди запросов;</span><span class="sxs-lookup"><span data-stu-id="2614f-109">Request queue limit</span></span>

  - <span data-ttu-id="2614f-110">одновременные подключения;</span><span class="sxs-lookup"><span data-stu-id="2614f-110">Concurrent connections</span></span>

  - <span data-ttu-id="2614f-111">длина очереди IIS.</span><span class="sxs-lookup"><span data-stu-id="2614f-111">IIS queue length</span></span>

<span data-ttu-id="2614f-112">Другие ограничения на серверах, которые могут повлиять на производительность мобильных устройств, задаются максимум двенадцать одновременных входов, проверок подлинности, продления сеансов и прекращений.</span><span class="sxs-lookup"><span data-stu-id="2614f-112">Other limits on servers that can influence mobility performance are a maximum of twelve concurrent sign-ins, authentications, session renewals, and terminations.</span></span> <span data-ttu-id="2614f-113">В большинстве развертываний эти максимальные значения не нуждаются в изменении.</span><span class="sxs-lookup"><span data-stu-id="2614f-113">These maximums do not need to be modified for most deployments.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="2614f-114">Содержание</span><span class="sxs-lookup"><span data-stu-id="2614f-114">In This Section</span></span>

  - [<span data-ttu-id="2614f-115">Наблюдение за пределами объема памяти сервера в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2614f-115">Monitoring for server memory capacity limits in Lync Server 2013</span></span>](lync-server-2013-monitoring-for-server-memory-capacity-limits.md)

  - [<span data-ttu-id="2614f-116">Наблюдение за работой службы Mobility Service и использованием УКВА в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2614f-116">Monitoring Mobility Service and UCWA usage in Lync Server 2013</span></span>](lync-server-2013-monitoring-mobility-service-and-ucwa-usage.md)

  - [<span data-ttu-id="2614f-117">Настройка службы Mobility Service для высокой производительности в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2614f-117">Configuring Mobility Service for high performance in Lync Server 2013</span></span>](lync-server-2013-configuring-mobility-service-for-high-performance.md)

  - [<span data-ttu-id="2614f-118">Мониторинг файлов журнала трассировки запросов IIS в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2614f-118">Monitoring IIS request tracing log files in Lync Server 2013</span></span>](lync-server-2013-monitoring-iis-request-tracing-log-files.md)

  - [<span data-ttu-id="2614f-119">Счетчики производительности мобильных устройств в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2614f-119">Mobility performance counters in Lync Server 2013</span></span>](lync-server-2013-mobility-performance-counters.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

