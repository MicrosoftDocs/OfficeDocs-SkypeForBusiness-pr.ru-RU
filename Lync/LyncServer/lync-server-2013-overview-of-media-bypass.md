---
title: 'Lync Server 2013: обзор обхода мультимедиа'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Overview of media bypass
ms:assetid: 9ea090b3-f607-46f7-97dd-2510052524e5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412740(v=OCS.15)
ms:contentKeyID: 48184924
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a04bc9dfa250bc399f10a56ef58f78462044f5cc
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34825417"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-media-bypass-in-lync-server-2013"></a><span data-ttu-id="c722f-102">Общие сведения об обходном пропуске мультимедиа в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c722f-102">Overview of media bypass in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c722f-103">_**Тема последнего изменения:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="c722f-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="c722f-104">Обход мультимедиа полезен, если вы хотите минимизировать количество развернутых серверов исправлений.</span><span class="sxs-lookup"><span data-stu-id="c722f-104">Media bypass is useful when you want to minimize the number of Mediation Servers deployed.</span></span> <span data-ttu-id="c722f-105">Обычно пул серверов-посредников будет развернут на центральном сайте, и он будет управлять шлюзами на сайтах филиалов.</span><span class="sxs-lookup"><span data-stu-id="c722f-105">Typically, a Mediation Server pool will be deployed at a central site, and it will control gateways at branch sites.</span></span> <span data-ttu-id="c722f-106">Включение обхода сервера-посредника позволяет проходить мультимедиа для вызовов ТСОП от клиентов на сайтах филиалов непосредственно через шлюзы на этих сайтах.</span><span class="sxs-lookup"><span data-stu-id="c722f-106">Enabling media bypass allows media for public switched telephone network (PSTN) calls from clients at branch sites to flow directly through the gateways at those sites.</span></span> <span data-ttu-id="c722f-107">В Lync Server 2013 маршруты исходящих вызовов и политики корпоративной голосовой связи должны быть настроены правильно, так что звонки между клиентами на сайте филиала направляются на соответствующий шлюз.</span><span class="sxs-lookup"><span data-stu-id="c722f-107">Lync Server 2013 outbound call routes and Enterprise Voice policies must be properly configured so that PSTN calls from clients at a branch site are routed to the appropriate gateway.</span></span>

<span data-ttu-id="c722f-p102">В сетях Wi-Fi обычно теряется больше пакетов, чем в проводных сетах. Восстановление от этой потери пакетов обычно не может быть обеспечено шлюзами. Таким образом, рекомендуется оценить качество сети Wi-Fi, прежде чем принимать решение о включении обхода сервера-посредника для беспроводной подсети. Также стоит оценить выгоду от сокращения задержек по сравнению с негативным эффектом от потери пакетов. Кодек RTAudio, доступный для вызовов без обхода серверов-посредников, лучше всего подходит для обработки потери пакетов.</span><span class="sxs-lookup"><span data-stu-id="c722f-p102">Wi-Fi networks typically experience more packet loss than wired networks. Recovery from this packet loss is not typically something that can be accommodated by gateways. Therefore, we recommend that you evaluate the quality of a Wi-Fi network before determining whether bypass should be enabled for a wireless subnet. There is a tradeoff in latency reduction versus recovery from packet loss to consider, as well. RTAudio, a codec which is available for calls that do not bypass the Mediation Server, is better suited for handling packet loss.</span></span>

<span data-ttu-id="c722f-113">После того как ваша корпоративная структура голосовых команд установлена, планирование обхода мультимедиа является просто.</span><span class="sxs-lookup"><span data-stu-id="c722f-113">After your Enterprise Voice structure is in place, planning for media bypass is straightforward.</span></span>

  - <span data-ttu-id="c722f-114">Если имеется централизованная топология без связей WAN с сайтами филиалов, можно включить глобальный обход сервера-посредника, поскольку детальный контроль не требуется.</span><span class="sxs-lookup"><span data-stu-id="c722f-114">If you have a centralized topology without WAN links to branch sites, you can enable global media bypass, because fine-tuned control is unnecessary.</span></span>

  - <span data-ttu-id="c722f-115">Если имеется распределенная топология, состоящая из одной или нескольких областей сети и присоединенных к ним сайтов филиалов, определите следующие моменты.</span><span class="sxs-lookup"><span data-stu-id="c722f-115">If you have a distributed topology that consists of one or more network regions and their affiliated branch sites, determine the following:</span></span>
    
      - <span data-ttu-id="c722f-116">Могут ли кэширующие узлы сервера-посредника поддерживать возможности, необходимые для обхода сервера-посредника.</span><span class="sxs-lookup"><span data-stu-id="c722f-116">Whether your Mediation Server peers are able to support the capabilities required for media bypass.</span></span>
    
      - <span data-ttu-id="c722f-117">Какие сайты в каждой области сети имеют хорошее подключение.</span><span class="sxs-lookup"><span data-stu-id="c722f-117">Which sites in each network region are well-connected.</span></span>
    
      - <span data-ttu-id="c722f-118">Какая комбинация обхода сервера-посредника и контроля допуска звонков подходит для вашей сети.</span><span class="sxs-lookup"><span data-stu-id="c722f-118">Which combination of media bypass and call admission control is appropriate for your network.</span></span>

<span data-ttu-id="c722f-p103">Когда вы включаете обход сервера-посредника, автоматически создается уникальный идентификатор обхода для области сети и для всех сетевых узлов без ограничений пропускной способности в этой области. Каждому узлу с ограничениями пропускной способности в этой области и узлу, подключенному к области с помощью связи WAN с ограничениями пропускной способности, назначается свой собственный уникальный идентификатор обхода.</span><span class="sxs-lookup"><span data-stu-id="c722f-p103">When you enable media bypass, a unique bypass ID is automatically generated for a network region, and for all network sites without bandwidth constraints within that region. Sites with bandwidth constraints within the region and sites connected to the region over WAN links with bandwidth constraints are each assigned their own unique bypass IDs.</span></span>

<span data-ttu-id="c722f-121">Когда пользователь выполняет звонок в КТСОП, сервер-посредник сравнивает идентификатор обхода подсети клиента с ИДЕНТИФИКАТОРом обхода подсети шлюза.</span><span class="sxs-lookup"><span data-stu-id="c722f-121">When a user makes a call to the PSTN, the Mediation Server compares the bypass ID of the client subnet with the bypass ID of the gateway subnet.</span></span> <span data-ttu-id="c722f-122">Если сопоставлены два идентификатора обхода, для вызова используется обход мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="c722f-122">If the two bypass IDs match, media bypass is used for the call.</span></span> <span data-ttu-id="c722f-123">Если идентификаторы обхода не совпадают, носители для звонка должны проходить через сервер.</span><span class="sxs-lookup"><span data-stu-id="c722f-123">If the bypass IDs do not match, media for the call must flow through the Mediation Server.</span></span>

<span data-ttu-id="c722f-124">Когда пользователь получает вызов из ТСОП, клиент пользователя сравнивает его идентификатор обхода с идентификатором обхода шлюза ТСОП.</span><span class="sxs-lookup"><span data-stu-id="c722f-124">When a user receives a call from the PSTN, the user’s client compares its bypass ID to that of the PSTN gateway.</span></span> <span data-ttu-id="c722f-125">Если два идентификатора обхода не совпадают, потоки мультимедиа переходят непосредственно с шлюза на клиент, минуя сервер обновлений.</span><span class="sxs-lookup"><span data-stu-id="c722f-125">If the two bypass IDs match, media flows directly from the gateway to the client, bypassing the Mediation Server.</span></span>

<span data-ttu-id="c722f-126">Только клиенты Lync 2010 или более поздней версии и устройства поддерживают взаимодействие без мультимедиа с сервера-посредника.</span><span class="sxs-lookup"><span data-stu-id="c722f-126">Only Lync 2010 or above clients and devices support media bypass interactions with a Mediation Server.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="c722f-p106">Кроме включения обхода сервера-посредника на глобальном уровне, необходимо включить обход сервера-посредника индивидуально в каждом канале ТСОП. Если обход включен на глобальном уровне, но не включен для конкретного канала ТСОП, то обход сервера-посредника не будет вызываться для любых вызовов, использующих этот канал ТСОП. Кроме того, если для обхода сервера-посредника установлен параметр <STRONG>Использовать сведения узла и области</STRONG>, необходимо сопоставить все маршрутизируемые подсети с узлами, в которых они расположены. Если в узле имеются маршрутизируемые подсети, для которых обход нежелателен, то эти подсети необходимо сгруппировать в новый узел перед включением обхода сервера-посредника. Это будет гарантировать, что немаршрутизируемым сетям будут назначены разные идентификаторы обхода.</span><span class="sxs-lookup"><span data-stu-id="c722f-p106">In addition to enabling media bypass globally, you must enable media bypass individually on each PSTN trunk. If bypass is enabled globally, but is not enabled for a particular PSTN trunk, media bypass will not be invoked for any calls involving that PSTN trunk. In addition, when media bypass is set to <STRONG>Use Site and Region Information</STRONG>, you must associate all routable subnets with the sites in which they are located. If there are routable subnets within a site for which bypass is not wanted, these subnets should be grouped within a new site before you enable media bypass. Doing so will assure that the unroutable subnets are assigned a different bypass ID.</span></span>



</div>

<div>

## <a name="see-also"></a><span data-ttu-id="c722f-132">См. также</span><span class="sxs-lookup"><span data-stu-id="c722f-132">See Also</span></span>


[<span data-ttu-id="c722f-133">Режимы обхода сервера-посредника в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c722f-133">Media bypass modes in Lync Server 2013</span></span>](lync-server-2013-media-bypass-modes.md)  
[<span data-ttu-id="c722f-134">Обход сервера-посредника и контроль допуска звонков в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c722f-134">Media bypass and call admission control in Lync Server 2013</span></span>](lync-server-2013-media-bypass-and-call-admission-control.md)  
[<span data-ttu-id="c722f-135">Технические требования для сервера-посредника в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c722f-135">Technical requirements for media bypass in Lync Server 2013</span></span>](lync-server-2013-technical-requirements-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

