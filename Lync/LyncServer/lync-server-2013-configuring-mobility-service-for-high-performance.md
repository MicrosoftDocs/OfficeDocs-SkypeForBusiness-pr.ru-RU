---
title: 'Lync Server 2013: Настройка службы Mobility Service для высокой производительности'
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
ms.openlocfilehash: 9d587444dfd1fbe4fae8898438a51bc9cfb2b5ff
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48526956"
---
# <a name="configuring-mobility-service-for-high-performance-in-lync-server-2013"></a><span data-ttu-id="36f6e-102">Настройка службы Mobility Service для высокой производительности в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="36f6e-102">Configuring Mobility Service for high performance in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="36f6e-103">_**Последнее изменение темы:** 2013-02-17_</span><span class="sxs-lookup"><span data-stu-id="36f6e-103">_**Topic Last Modified:** 2013-02-17_</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="36f6e-104">Этот раздел относится только к службе Mobility Service 2013 для Lync Server и не относится к веб-API объединенных коммуникаций (UCWA), как доставляется в накопительные пакеты обновления для Lync Server 2013: Февраль 2013.</span><span class="sxs-lookup"><span data-stu-id="36f6e-104">This topic applies only to the Lync Server 2013 Mobility Service (Mcx), and does not apply to Unified Communications Web API (UCWA), as delivered in the Cumulative Updates for Lync Server 2013: February 2013.</span></span>



</div>

<span data-ttu-id="36f6e-105">При установке службы Mobility Service (MCX) в службах IIS 7,5 программа установки службы Mobility Service настраивает некоторые параметры производительности на сервере переднего плана.</span><span class="sxs-lookup"><span data-stu-id="36f6e-105">When you install the Mobility Service (Mcx) on Internet Information Services (IIS) 7.5, the Mobility Service installer configures some performance settings on the Front End Server.</span></span> <span data-ttu-id="36f6e-106">Мы рекомендуем использовать IIS 7.5 для Mobility Service.</span><span class="sxs-lookup"><span data-stu-id="36f6e-106">We recommend that you use IIS 7.5 for mobility.</span></span> <span data-ttu-id="36f6e-107">Параметры влияют на максимальное число одновременных запросов пользователей и максимальное число потоков, которые разрешены для Mobility Service.</span><span class="sxs-lookup"><span data-stu-id="36f6e-107">The settings affect the maximum number of concurrent user requests and the maximum number of threads that are allowed for the Mobility Service.</span></span>

<span data-ttu-id="36f6e-108">Ниже приведены параметры производительности.</span><span class="sxs-lookup"><span data-stu-id="36f6e-108">Here are the performance settings:</span></span>

<div>

## <a name="settings-for-mcx-on-iis-75"></a><span data-ttu-id="36f6e-109">Параметры MCX в службах IIS 7,5</span><span class="sxs-lookup"><span data-stu-id="36f6e-109">Settings for Mcx on IIS 7.5</span></span>

1.  <span data-ttu-id="36f6e-110">**maxConcurrentThreadsPerCPU** имеет значение нуль (0).</span><span class="sxs-lookup"><span data-stu-id="36f6e-110">**maxConcurrentThreadsPerCPU** is set to zero (0).</span></span>

2.  <span data-ttu-id="36f6e-111">**maxConcurrentRequestsPerCPU** имеет значение нуль (0).</span><span class="sxs-lookup"><span data-stu-id="36f6e-111">**maxConcurrentRequestsPerCPU** is set to zero (0).</span></span>

3.  <span data-ttu-id="36f6e-112">Процессная модель ASP.NET имеет значение AutoConfig (только для IIS 7.5).</span><span class="sxs-lookup"><span data-stu-id="36f6e-112">ASP.NET process model is set to AutoConfig (for IIS 7.5 only).</span></span>

4.  <span data-ttu-id="36f6e-113">Предел очереди HTTP.sys имеет значение 1000 (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="36f6e-113">HTTP.sys queue limit is set to 1,000 (by default).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

