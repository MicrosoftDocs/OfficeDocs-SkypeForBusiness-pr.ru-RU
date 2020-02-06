---
title: Мониторинг производительности в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 9c831c63-9a7d-48ec-9118-f8a7e80ddd04
description: 'Сводка: сведения о службе Mobility Service (МККС) и веб-интерфейсе API единой системы обмена сообщениями (УКВА) в Skype для бизнеса Server.'
ms.openlocfilehash: 4d604c46704881a055385336f8b1ff32862d929a
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817838"
---
# <a name="monitor-mobility-for-performance-in-skype-for-business-server"></a><span data-ttu-id="dc9a5-103">Мониторинг производительности в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="dc9a5-103">Monitor mobility for performance in Skype for Business Server</span></span>
 
<span data-ttu-id="dc9a5-104">**Сводка:** Узнайте о службе Mobility Service (МККС) и веб-API единой системы обмена сообщениями (УКВА) в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="dc9a5-104">**Summary:** Learn about the Mobility Service (Mcx) and the Unified Communications Web API (UCWA) in Skype for Business Server.</span></span>
  
<span data-ttu-id="dc9a5-105">Служба Mobility Service в Skype для бизнеса Server (МККС) и веб-интерфейс единой системы обмена сообщениями (УКВА) увеличивают нагрузку на сервер переднего плана и пулы интерфейсов.</span><span class="sxs-lookup"><span data-stu-id="dc9a5-105">The Skype for Business Server Mobility Service (Mcx) and the Unified Communications Web API (UCWA) increase the load on Front End Servers and Front End pools.</span></span> <span data-ttu-id="dc9a5-106">Мобильные устройства, поддерживающие подключение к серверу даже в том случае, если мобильное приложение свернуто, например устройства Android и Nokia, работающие под управлением Lync 2010 Mobile, а также устройства Android и Apple, работающие под управлением Lync 2013 для мобильных устройств, выпускают больше нагрузки, чем устройства, которые прерывать соединение с сервером, когда мобильное приложение свернуто.</span><span class="sxs-lookup"><span data-stu-id="dc9a5-106">Mobile devices that maintain a connection to the server even when the mobile application is minimized, such as Android and Nokia devices running Lync 2010 Mobile, as well as Android and Apple devices running Lync 2013 Mobile, impose a greater load than devices that terminate their connection to the server when the mobile application is minimized.</span></span> <span data-ttu-id="dc9a5-107">As your mobility usage increases, you must monitor mobility performance to determine when you need to increase your capacity.</span><span class="sxs-lookup"><span data-stu-id="dc9a5-107">As your mobility usage increases, you must monitor mobility performance to determine when you need to increase your capacity.</span></span>

> [!NOTE]
> <span data-ttu-id="dc9a5-108">Поддержка МККС (служба Mobility Service) для устаревших мобильных клиентов больше не доступна в Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="dc9a5-108">MCX (Mobility Service) support for legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="dc9a5-109">На всех текущих мобильных клиентах Skype для бизнеса уже используется веб-API единой системы обмена сообщениями (УКВА) для поддержки мгновенных сообщений, присутствия и контактов.</span><span class="sxs-lookup"><span data-stu-id="dc9a5-109">All current Skype for Business mobile clients already use Unified Communications Web API (UCWA) to support instant messaging (IM), presence, and contacts.</span></span> <span data-ttu-id="dc9a5-110">Пользователи с устаревшими клиентами, использующими МККС, должны обновиться до текущего клиента.</span><span class="sxs-lookup"><span data-stu-id="dc9a5-110">Users with legacy clients using MCX will need to upgrade to a current client.</span></span>
  
<span data-ttu-id="dc9a5-111">Некоторые ограничения, влияющие на производительность мобильности:</span><span class="sxs-lookup"><span data-stu-id="dc9a5-111">Several limits influence mobility performance:</span></span> 
  
- <span data-ttu-id="dc9a5-112">доступная память;</span><span class="sxs-lookup"><span data-stu-id="dc9a5-112">Available memory</span></span>
    
- <span data-ttu-id="dc9a5-113">ограничение очереди запросов;</span><span class="sxs-lookup"><span data-stu-id="dc9a5-113">Request queue limit</span></span>
    
- <span data-ttu-id="dc9a5-114">одновременные подключения;</span><span class="sxs-lookup"><span data-stu-id="dc9a5-114">Concurrent connections</span></span>
    
- <span data-ttu-id="dc9a5-115">длина очереди IIS.</span><span class="sxs-lookup"><span data-stu-id="dc9a5-115">IIS queue length</span></span>
    
<span data-ttu-id="dc9a5-p103">Кроме того, на производительность мобильности могут влиять следующие ограничения на серверах: не более 12 одновременных входов, проверок подлинности, а также возобновлений и прекращений сеансов. В большинстве развертываний эти максимальные значения не нуждаются в изменении.</span><span class="sxs-lookup"><span data-stu-id="dc9a5-p103">Other limits on servers that can influence mobility performance are a maximum of 12 concurrent sign-ins, authentications, session renewals, and terminations. These maximums do not need to be modified for most deployments.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="dc9a5-118">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="dc9a5-118">In this section</span></span>

- [<span data-ttu-id="dc9a5-119">Наблюдение за ограничениями объема памяти сервера в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="dc9a5-119">Monitor for server memory capacity limits in Skype for Business Server</span></span>](server-memory-capacity-limits.md)
    
- [<span data-ttu-id="dc9a5-120">Мониторинг службы Mobility Service и использование УКВА в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="dc9a5-120">Monitor Mobility Service and UCWA usage in Skype for Business Server</span></span>](service-and-ucwa-usage.md)
    
- [<span data-ttu-id="dc9a5-121">Настройка службы Mobility Service для высокой производительности в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="dc9a5-121">Configure Mobility Service for high performance in Skype for Business Server</span></span>](configure-service.md)
    
- [<span data-ttu-id="dc9a5-122">Мониторинг файлов журнала трассировки запросов IIS в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="dc9a5-122">Monitoring IIS request tracing log files in Skype for Business Server</span></span>](iis-request-tracing-log-files.md)
    
- [<span data-ttu-id="dc9a5-123">Счетчики производительности мобильных устройств в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="dc9a5-123">Mobility performance counters in Skype for Business Server</span></span>](performance-counters.md)
    

