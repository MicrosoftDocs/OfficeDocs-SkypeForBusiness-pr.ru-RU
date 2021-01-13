---
title: Отслеживание мобильности для повышения производительности в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 9c831c63-9a7d-48ec-9118-f8a7e80ddd04
description: Сводка. Сведения о службе Mobility Service (Mcx) и веб-API объединенных коммуникаций (UCWA) в Skype для бизнеса Server.
ms.openlocfilehash: d7473d22f2de0576bf6214ae43719c8bfc70d49a
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816839"
---
# <a name="monitor-mobility-for-performance-in-skype-for-business-server"></a><span data-ttu-id="2e08c-103">Отслеживание мобильности для повышения производительности в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="2e08c-103">Monitor mobility for performance in Skype for Business Server</span></span>
 
<span data-ttu-id="2e08c-104">**Сводка:** Узнайте о службе Mobility Service (Mcx) и веб-API объединенных коммуникаций (UCWA) в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="2e08c-104">**Summary:** Learn about the Mobility Service (Mcx) and the Unified Communications Web API (UCWA) in Skype for Business Server.</span></span>
  
<span data-ttu-id="2e08c-105">Skype для бизнеса Server Mobility Service (Mcx) и веб-API объединенных коммуникаций (UCWA) увеличивают нагрузку на серверы переднего сервера и пулы переднего сервера.</span><span class="sxs-lookup"><span data-stu-id="2e08c-105">The Skype for Business Server Mobility Service (Mcx) and the Unified Communications Web API (UCWA) increase the load on Front End Servers and Front End pools.</span></span> <span data-ttu-id="2e08c-106">Мобильные устройства, которые поддерживают подключение к серверу, даже если мобильное приложение свернуто, например устройства Android и Nokia под управлением Lync 2010 Mobile, а также устройства с Android и Apple под управлением Lync 2013 Mobile, налагают большую нагрузку, чем устройства, которые прерывают подключение к серверу, когда мобильное приложение свернуто.</span><span class="sxs-lookup"><span data-stu-id="2e08c-106">Mobile devices that maintain a connection to the server even when the mobile application is minimized, such as Android and Nokia devices running Lync 2010 Mobile, as well as Android and Apple devices running Lync 2013 Mobile, impose a greater load than devices that terminate their connection to the server when the mobile application is minimized.</span></span> <span data-ttu-id="2e08c-107">По мере увеличения использования мобильной работы необходимо отслеживать производительность мобильности, чтобы определить, когда необходимо увеличить емкость.</span><span class="sxs-lookup"><span data-stu-id="2e08c-107">As your mobility usage increases, you must monitor mobility performance to determine when you need to increase your capacity.</span></span>

> [!NOTE]
> <span data-ttu-id="2e08c-108">Поддержка СЛУЖБЫ MCX (Mobility Service) для устаревших мобильных клиентов больше недоступна в Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="2e08c-108">MCX (Mobility Service) support for legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="2e08c-109">Все текущие мобильные клиенты Skype для бизнеса уже используют веб-API объединенных коммуникаций (UCWA) для поддержки обмена мгновенными сообщениями, присутствия и контактов.</span><span class="sxs-lookup"><span data-stu-id="2e08c-109">All current Skype for Business mobile clients already use Unified Communications Web API (UCWA) to support instant messaging (IM), presence, and contacts.</span></span> <span data-ttu-id="2e08c-110">Пользователям с устаревшими клиентами, использующими MCX, потребуется обновиться до текущего клиента.</span><span class="sxs-lookup"><span data-stu-id="2e08c-110">Users with legacy clients using MCX will need to upgrade to a current client.</span></span>
  
<span data-ttu-id="2e08c-111">Некоторые ограничения, влияющие на производительность мобильности:</span><span class="sxs-lookup"><span data-stu-id="2e08c-111">Several limits influence mobility performance:</span></span> 
  
- <span data-ttu-id="2e08c-112">доступная память;</span><span class="sxs-lookup"><span data-stu-id="2e08c-112">Available memory</span></span>
    
- <span data-ttu-id="2e08c-113">ограничение очереди запросов;</span><span class="sxs-lookup"><span data-stu-id="2e08c-113">Request queue limit</span></span>
    
- <span data-ttu-id="2e08c-114">одновременные подключения;</span><span class="sxs-lookup"><span data-stu-id="2e08c-114">Concurrent connections</span></span>
    
- <span data-ttu-id="2e08c-115">длина очереди IIS.</span><span class="sxs-lookup"><span data-stu-id="2e08c-115">IIS queue length</span></span>
    
<span data-ttu-id="2e08c-116">Другие ограничения на серверах, которые могут влиять на производительность мобильности, — это не более 12 одновременно входов, проверки подлинности, возобновлений сеансов и прекращений.</span><span class="sxs-lookup"><span data-stu-id="2e08c-116">Other limits on servers that can influence mobility performance are a maximum of 12 concurrent sign-ins, authentications, session renewals, and terminations.</span></span> <span data-ttu-id="2e08c-117">В большинстве развертываний эти максимальные значения не нуждаются в изменении.</span><span class="sxs-lookup"><span data-stu-id="2e08c-117">These maximums do not need to be modified for most deployments.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="2e08c-118">В этом разделе:</span><span class="sxs-lookup"><span data-stu-id="2e08c-118">In this section</span></span>

- [<span data-ttu-id="2e08c-119">Отслеживание ограничений емкости памяти сервера в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="2e08c-119">Monitor for server memory capacity limits in Skype for Business Server</span></span>](server-memory-capacity-limits.md)
    
- [<span data-ttu-id="2e08c-120">Мониторинг использования mobility Service и UCWA в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="2e08c-120">Monitor Mobility Service and UCWA usage in Skype for Business Server</span></span>](service-and-ucwa-usage.md)
    
- [<span data-ttu-id="2e08c-121">Настройка службы Mobility Service для высокой производительности в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="2e08c-121">Configure Mobility Service for high performance in Skype for Business Server</span></span>](configure-service.md)
    
- [<span data-ttu-id="2e08c-122">Мониторинг файлов журнала трасситуры запросов IIS в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="2e08c-122">Monitoring IIS request tracing log files in Skype for Business Server</span></span>](iis-request-tracing-log-files.md)
    
- [<span data-ttu-id="2e08c-123">Счетчики производительности мобильности в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="2e08c-123">Mobility performance counters in Skype for Business Server</span></span>](performance-counters.md)
    

