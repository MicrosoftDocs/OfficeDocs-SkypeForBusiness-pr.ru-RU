---
title: Мобильность монитора производительности в Скайп для Business Server
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9c831c63-9a7d-48ec-9118-f8a7e80ddd04
description: 'Сводка: Сведения о Mobility Service (Mcx) и веб-объединенных коммуникаций API (UCWA) в Скайп для Business Server.'
ms.openlocfilehash: 4affcb532697f24c87d62e18fc26552639dc00e1
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2018
ms.locfileid: "20990639"
---
# <a name="monitor-mobility-for-performance-in-skype-for-business-server"></a><span data-ttu-id="45fb1-103">Мобильность монитора производительности в Скайп для Business Server</span><span class="sxs-lookup"><span data-stu-id="45fb1-103">Monitor mobility for performance in Skype for Business Server</span></span>
 
<span data-ttu-id="45fb1-104">**Сводка:** Сведения о службе Mobility Service (Mcx) и веб-объединенных коммуникаций API (UCWA) в Скайп для Business Server.</span><span class="sxs-lookup"><span data-stu-id="45fb1-104">**Summary:** Learn about the Mobility Service (Mcx) and the Unified Communications Web API (UCWA) in Skype for Business Server.</span></span>
  
<span data-ttu-id="45fb1-105">Скайп для службы Mobility Business Server (Mcx) и Unified Communications Web API (UCWA) увеличивают нагрузку на пулов переднего плана и серверов переднего плана.</span><span class="sxs-lookup"><span data-stu-id="45fb1-105">The Skype for Business Server Mobility Service (Mcx) and the Unified Communications Web API (UCWA) increase the load on Front End Servers and Front End pools.</span></span> <span data-ttu-id="45fb1-106">Мобильных устройств, которые поддерживают подключение к серверу даже в том случае, если свернутого мобильных приложений, таких как Android и Nokia устройств под управлением Lync 2010 Mobile, а также Android и Apple устройств под управлением Lync 2013 Mobile применяться дополнительную нагрузку, чем устройств, прерывания их подключения к серверу при свернутом окне мобильных приложений.</span><span class="sxs-lookup"><span data-stu-id="45fb1-106">Mobile devices that maintain a connection to the server even when the mobile application is minimized, such as Android and Nokia devices running Lync 2010 Mobile, as well as Android and Apple devices running Lync 2013 Mobile, impose a greater load than devices that terminate their connection to the server when the mobile application is minimized.</span></span> <span data-ttu-id="45fb1-107">С увеличением использования мобильных устройств должны отслеживать производительность мобильности, чтобы определить, когда следует увеличить емкость.</span><span class="sxs-lookup"><span data-stu-id="45fb1-107">As your mobility usage increases, you must monitor mobility performance to determine when you need to increase your capacity.</span></span>

> [!NOTE]
> <span data-ttu-id="45fb1-108">Поддержка MCX для устаревших мобильных клиентов больше не доступен в Скайп для Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="45fb1-108">MCX support for legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="45fb1-109">Пользователям необходимо обновить до текущего клиента.</span><span class="sxs-lookup"><span data-stu-id="45fb1-109">Your users will need to upgrade to a current client.</span></span>
  
<span data-ttu-id="45fb1-110">Некоторые ограничения, влияющие на производительность мобильности:</span><span class="sxs-lookup"><span data-stu-id="45fb1-110">Several limits influence mobility performance:</span></span> 
  
- <span data-ttu-id="45fb1-111">доступная память;</span><span class="sxs-lookup"><span data-stu-id="45fb1-111">Available memory</span></span>
    
- <span data-ttu-id="45fb1-112">ограничение очереди запросов;</span><span class="sxs-lookup"><span data-stu-id="45fb1-112">Request queue limit</span></span>
    
- <span data-ttu-id="45fb1-113">одновременные подключения;</span><span class="sxs-lookup"><span data-stu-id="45fb1-113">Concurrent connections</span></span>
    
- <span data-ttu-id="45fb1-114">длина очереди IIS.</span><span class="sxs-lookup"><span data-stu-id="45fb1-114">IIS queue length</span></span>
    
<span data-ttu-id="45fb1-p103">Кроме того, на производительность мобильности могут влиять следующие ограничения на серверах: не более 12 одновременных входов, проверок подлинности, а также возобновлений и прекращений сеансов. В большинстве развертываний эти максимальные значения не нуждаются в изменении.</span><span class="sxs-lookup"><span data-stu-id="45fb1-p103">Other limits on servers that can influence mobility performance are a maximum of 12 concurrent sign-ins, authentications, session renewals, and terminations. These maximums do not need to be modified for most deployments.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="45fb1-117">Содержание</span><span class="sxs-lookup"><span data-stu-id="45fb1-117">In this section</span></span>

- [<span data-ttu-id="45fb1-118">Монитор ограничений емкости памяти сервера в Скайп для Business Server</span><span class="sxs-lookup"><span data-stu-id="45fb1-118">Monitor for server memory capacity limits in Skype for Business Server</span></span>](server-memory-capacity-limits.md)
    
- [<span data-ttu-id="45fb1-119">Мониторинг использования службы Mobility Service и UCWA в Скайп для Business Server</span><span class="sxs-lookup"><span data-stu-id="45fb1-119">Monitor Mobility Service and UCWA usage in Skype for Business Server</span></span>](service-and-ucwa-usage.md)
    
- [<span data-ttu-id="45fb1-120">Настройка службы мобильности для повышения производительности в Скайп для Business Server</span><span class="sxs-lookup"><span data-stu-id="45fb1-120">Configure Mobility Service for high performance in Skype for Business Server</span></span>](configure-service.md)
    
- [<span data-ttu-id="45fb1-121">Мониторинг файлов журнала в Скайп трассировки для сервера запросов IIS</span><span class="sxs-lookup"><span data-stu-id="45fb1-121">Monitoring IIS request tracing log files in Skype for Business Server</span></span>](iis-request-tracing-log-files.md)
    
- [<span data-ttu-id="45fb1-122">Счетчики производительности мобильности в Скайп для Business Server</span><span class="sxs-lookup"><span data-stu-id="45fb1-122">Mobility performance counters in Skype for Business Server</span></span>](performance-counters.md)
    

