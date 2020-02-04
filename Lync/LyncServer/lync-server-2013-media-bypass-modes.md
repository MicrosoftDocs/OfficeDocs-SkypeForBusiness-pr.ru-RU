---
title: 'Lync Server 2013: режимы обхода сервера-посредника'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Media bypass modes
ms:assetid: 38c06c81-7e45-4423-9e00-7fbfa4befe46
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425862(v=OCS.15)
ms:contentKeyID: 48183898
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4f92d45099f39ec96724f8d0f6025f58e2dbccb2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41761955"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="media-bypass-modes-in-lync-server-2013"></a><span data-ttu-id="5bd82-102">Режимы обхода сервера-посредника в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5bd82-102">Media bypass modes in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5bd82-103">_**Тема последнего изменения:** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="5bd82-103">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="5bd82-p101">Обход сервера-посредника необходимо настроить как глобально, так и для каждого отдельного канала ТСОП. При включении обхода сервера-посредника на глобальном уровне имеются два варианта: **Обходить всегда** и **Использовать сведения о сайте и области**.</span><span class="sxs-lookup"><span data-stu-id="5bd82-p101">You must configure media bypass both globally and for each individual PSTN trunk. When enabling media bypass globally, you have two choices: **Always Bypass** and **Use Site and Region Information**.</span></span>

<span data-ttu-id="5bd82-p102">Как можно предположить из названия, параметр **Обходить всегда** означает, что попытки обхода сервера-посредника будут предприниматься для всех вызовов ТСОП. Параметр **Обходить всегда** используется в развертываниях, в которых не требуется ни включать контроль допуска звонков, ни указывать подробные сведения о конфигурации, касающиеся того, когда следует пытаться обходить сервер-посредник. Кроме того, параметр **Обходить всегда** используется, когда имеется полное подключение между клиентами и шлюзами ТСОП. В такой конфигурации все подсети ставятся в соответствие одному и только одному идентификатору обхода, который вычисляется системой.</span><span class="sxs-lookup"><span data-stu-id="5bd82-p102">As the name suggests, **Always Bypass** means that bypass will be attempted for all PSTN calls. **Always Bypass** is used for deployments where there is no need to enable call admission control, nor is there a need to specify detailed configuration information regarding when to attempt media bypass. Furthermore, **Always Bypass** is used when there is full connectivity between clients and PSTN gateways. In this configuration, all subnets are mapped to one and only one bypass ID, which is computed by the system.</span></span>

<span data-ttu-id="5bd82-p103">При выборе параметра **Использовать сведения о сайте и области** для принятия решения об обходе используется идентификатор обхода, связанный с конфигурацией сайта и области. Эта конфигурация обеспечивает гибкость настройки обхода для большинства распространенных топологий, поскольку предоставляет возможность детального контроля над тем, когда происходит обход, в дополнение к поддержке взаимодействий с контролем допуска звонков. Система пытается облегчить вашу задачу, автоматические назначая идентификатор обхода следующим образом.</span><span class="sxs-lookup"><span data-stu-id="5bd82-p103">With **Use Site and Region Information**, the bypass ID associated with site and region configuration is used to make the bypass decision. This configuration provides the flexibility to configure bypass for most common topologies, as it gives you fine-grained control over when bypass happens, in addition to supporting interactions with call admission control (CAC). The system tries to ease your task by automatically assigning bypass IDs as follows.</span></span>

  - <span data-ttu-id="5bd82-113">Система автоматически назначает один уникальный идентификатор обхода каждой области.</span><span class="sxs-lookup"><span data-stu-id="5bd82-113">The system automatically assigns a single unique bypass ID to each region.</span></span>

  - <span data-ttu-id="5bd82-114">Любой сайт, связанный с областью посредством связи WAN без ограничений пропускной способности, наследует идентификатор обхода области.</span><span class="sxs-lookup"><span data-stu-id="5bd82-114">Any site connected to a region over a WAN link without bandwidth constraints inherits the same bypass ID as the region.</span></span>

  - <span data-ttu-id="5bd82-115">Сайту, связанному с областью посредством связи WAN с ограниченной пропускной способностью, назначается идентификатор обхода, отличный от идентификатора обхода области.</span><span class="sxs-lookup"><span data-stu-id="5bd82-115">A site associated with the region over a WAN link with constrained bandwidth is assigned a different bypass ID from that of the region.</span></span>

  - <span data-ttu-id="5bd82-116">Подсети, связанные с каждым сайтом, наследуют идентификатор обхода этого сайта.</span><span class="sxs-lookup"><span data-stu-id="5bd82-116">Subnets associated with each site inherit the bypass ID for that site.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="5bd82-117">См. также</span><span class="sxs-lookup"><span data-stu-id="5bd82-117">See Also</span></span>


[<span data-ttu-id="5bd82-118">Общие сведения об обходном пропуске мультимедиа в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5bd82-118">Overview of media bypass in Lync Server 2013</span></span>](lync-server-2013-overview-of-media-bypass.md)  
[<span data-ttu-id="5bd82-119">Обход сервера-посредника и контроль допуска звонков в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5bd82-119">Media bypass and call admission control in Lync Server 2013</span></span>](lync-server-2013-media-bypass-and-call-admission-control.md)  
[<span data-ttu-id="5bd82-120">Технические требования для сервера-посредника в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5bd82-120">Technical requirements for media bypass in Lync Server 2013</span></span>](lync-server-2013-technical-requirements-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

