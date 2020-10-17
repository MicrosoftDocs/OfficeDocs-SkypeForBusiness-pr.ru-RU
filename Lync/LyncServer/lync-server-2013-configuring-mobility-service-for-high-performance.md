---
title: 'Lync Server 2013: Настройка службы Mobility Service для высокой производительности'
description: 'Lync Server 2013: Настройка службы Mobility Service для высокой производительности.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Mobility Service for high performance
ms:assetid: c2b8aadb-cffb-49f0-ba7a-e8541a1ff475
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690042(v=OCS.15)
ms:contentKeyID: 48185332
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4732d9f6a92c383a105a6f0d7162c9b6c798de24
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48556985"
---
# <a name="configuring-mobility-service-for-high-performance-in-lync-server-2013"></a><span data-ttu-id="d67bc-103">Настройка службы Mobility Service для высокой производительности в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d67bc-103">Configuring Mobility Service for high performance in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d67bc-104">_**Последнее изменение темы:** 2013-02-17_</span><span class="sxs-lookup"><span data-stu-id="d67bc-104">_**Topic Last Modified:** 2013-02-17_</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="d67bc-105">Этот раздел относится только к службе Mobility Service 2013 для Lync Server и не относится к веб-API объединенных коммуникаций (UCWA), как доставляется в накопительные пакеты обновления для Lync Server 2013: Февраль 2013.</span><span class="sxs-lookup"><span data-stu-id="d67bc-105">This topic applies only to the Lync Server 2013 Mobility Service (Mcx), and does not apply to Unified Communications Web API (UCWA), as delivered in the Cumulative Updates for Lync Server 2013: February 2013.</span></span>



</div>

<span data-ttu-id="d67bc-106">При установке службы Mobility Service (MCX) в службах IIS 7,5 программа установки службы Mobility Service настраивает некоторые параметры производительности на сервере переднего плана.</span><span class="sxs-lookup"><span data-stu-id="d67bc-106">When you install the Mobility Service (Mcx) on Internet Information Services (IIS) 7.5, the Mobility Service installer configures some performance settings on the Front End Server.</span></span> <span data-ttu-id="d67bc-107">Мы рекомендуем использовать IIS 7.5 для Mobility Service.</span><span class="sxs-lookup"><span data-stu-id="d67bc-107">We recommend that you use IIS 7.5 for mobility.</span></span> <span data-ttu-id="d67bc-108">Параметры влияют на максимальное число одновременных запросов пользователей и максимальное число потоков, которые разрешены для Mobility Service.</span><span class="sxs-lookup"><span data-stu-id="d67bc-108">The settings affect the maximum number of concurrent user requests and the maximum number of threads that are allowed for the Mobility Service.</span></span>

<span data-ttu-id="d67bc-109">Ниже приведены параметры производительности.</span><span class="sxs-lookup"><span data-stu-id="d67bc-109">Here are the performance settings:</span></span>

<div>

## <a name="settings-for-mcx-on-iis-75"></a><span data-ttu-id="d67bc-110">Параметры MCX в службах IIS 7,5</span><span class="sxs-lookup"><span data-stu-id="d67bc-110">Settings for Mcx on IIS 7.5</span></span>

1.  <span data-ttu-id="d67bc-111">**maxConcurrentThreadsPerCPU** имеет значение нуль (0).</span><span class="sxs-lookup"><span data-stu-id="d67bc-111">**maxConcurrentThreadsPerCPU** is set to zero (0).</span></span>

2.  <span data-ttu-id="d67bc-112">**maxConcurrentRequestsPerCPU** имеет значение нуль (0).</span><span class="sxs-lookup"><span data-stu-id="d67bc-112">**maxConcurrentRequestsPerCPU** is set to zero (0).</span></span>

3.  <span data-ttu-id="d67bc-113">Процессная модель ASP.NET имеет значение AutoConfig (только для IIS 7.5).</span><span class="sxs-lookup"><span data-stu-id="d67bc-113">ASP.NET process model is set to AutoConfig (for IIS 7.5 only).</span></span>

4.  <span data-ttu-id="d67bc-114">Предел очереди HTTP.sys имеет значение 1000 (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="d67bc-114">HTTP.sys queue limit is set to 1,000 (by default).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

