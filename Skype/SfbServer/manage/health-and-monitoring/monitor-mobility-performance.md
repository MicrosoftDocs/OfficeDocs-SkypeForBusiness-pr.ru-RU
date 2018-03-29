---
title: Мониторинг производительности для мобильных устройств в Skype для бизнеса Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9c831c63-9a7d-48ec-9118-f8a7e80ddd04
description: 'Сводка: Сведения о Mobility Service (Mcx) и веб-API (UCWA) объединенных коммуникаций в Скайп для Business Server 2015.'
ms.openlocfilehash: 1981bff8398f3fab9206f9dab748c545268f7edf
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="monitor-mobility-for-performance-in-skype-for-business-server-2015"></a><span data-ttu-id="13ff1-103">Мониторинг производительности для мобильных устройств в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="13ff1-103">Monitor mobility for performance in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="13ff1-104">**Сводка:** Описание службы Mobility Service (Mcx) и веб-API (UCWA) объединенных коммуникаций в Скайп для Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="13ff1-104">**Summary:** Learn about the Mobility Service (Mcx) and the Unified Communications Web API (UCWA) in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="13ff1-105">Скайп для службы Mobility Business Server (Mcx) и Unified Communications Web API (UCWA) увеличивают нагрузку на пулов переднего плана и серверов переднего плана.</span><span class="sxs-lookup"><span data-stu-id="13ff1-105">The Skype for Business Server Mobility Service (Mcx) and the Unified Communications Web API (UCWA) increase the load on Front End Servers and Front End pools.</span></span> <span data-ttu-id="13ff1-106">Мобильных устройств, которые поддерживают подключение к серверу даже в том случае, если свернутого мобильных приложений, таких как Android и Nokia устройств под управлением Lync 2010 Mobile, а также Android и Apple устройств под управлением Lync 2013 Mobile применяться дополнительную нагрузку, чем устройств, прерывания их подключения к серверу при свернутом окне мобильных приложений.</span><span class="sxs-lookup"><span data-stu-id="13ff1-106">Mobile devices that maintain a connection to the server even when the mobile application is minimized, such as Android and Nokia devices running Lync 2010 Mobile, as well as Android and Apple devices running Lync 2013 Mobile, impose a greater load than devices that terminate their connection to the server when the mobile application is minimized.</span></span> <span data-ttu-id="13ff1-107">С увеличением использования мобильных устройств должны отслеживать производительность мобильности, чтобы определить, когда следует увеличить емкость.</span><span class="sxs-lookup"><span data-stu-id="13ff1-107">As your mobility usage increases, you must monitor mobility performance to determine when you need to increase your capacity.</span></span>
  
<span data-ttu-id="13ff1-108">Некоторые ограничения, влияющие на производительность мобильности:</span><span class="sxs-lookup"><span data-stu-id="13ff1-108">Several limits influence mobility performance:</span></span> 
  
- <span data-ttu-id="13ff1-109">доступная память;</span><span class="sxs-lookup"><span data-stu-id="13ff1-109">Available memory</span></span>
    
- <span data-ttu-id="13ff1-110">ограничение очереди запросов;</span><span class="sxs-lookup"><span data-stu-id="13ff1-110">Request queue limit</span></span>
    
- <span data-ttu-id="13ff1-111">одновременные подключения;</span><span class="sxs-lookup"><span data-stu-id="13ff1-111">Concurrent connections</span></span>
    
- <span data-ttu-id="13ff1-112">длина очереди IIS.</span><span class="sxs-lookup"><span data-stu-id="13ff1-112">IIS queue length</span></span>
    
<span data-ttu-id="13ff1-p102">Кроме того, на производительность мобильности могут влиять следующие ограничения на серверах: не более 12 одновременных входов, проверок подлинности, а также возобновлений и прекращений сеансов. В большинстве развертываний эти максимальные значения не нуждаются в изменении.</span><span class="sxs-lookup"><span data-stu-id="13ff1-p102">Other limits on servers that can influence mobility performance are a maximum of 12 concurrent sign-ins, authentications, session renewals, and terminations. These maximums do not need to be modified for most deployments.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="13ff1-115">Содержание</span><span class="sxs-lookup"><span data-stu-id="13ff1-115">In this section</span></span>

- [<span data-ttu-id="13ff1-116">Монитор ограничений емкости памяти сервера в Скайп для Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="13ff1-116">Monitor for server memory capacity limits in Skype for Business Server 2015</span></span>](server-memory-capacity-limits.md)
    
- [<span data-ttu-id="13ff1-117">Мониторинг использования службы Mobility Service и UCWA в Скайп для Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="13ff1-117">Monitor Mobility Service and UCWA usage in Skype for Business Server 2015</span></span>](service-and-ucwa-usage.md)
    
- [<span data-ttu-id="13ff1-118">Настройка службы мобильности для повышения производительности в Скайп для Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="13ff1-118">Configure Mobility Service for high performance in Skype for Business Server 2015</span></span>](configure-service.md)
    
- [<span data-ttu-id="13ff1-119">Мониторинга IIS запросить файлы журнала трассировки в Скайп для Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="13ff1-119">Monitoring IIS request tracing log files in Skype for Business Server 2015</span></span>](iis-request-tracing-log-files.md)
    
- [<span data-ttu-id="13ff1-120">Счетчики производительности мобильности в Скайп для Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="13ff1-120">Mobility performance counters in Skype for Business Server 2015</span></span>](performance-counters.md)
    

