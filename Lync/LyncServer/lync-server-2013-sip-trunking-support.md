---
title: 'Lync Server 2013: поддержка распределения каналов SIP'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: SIP trunking support
ms:assetid: e3042831-e8d8-4ea2-baa2-1a697401ffa0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399005(v=OCS.15)
ms:contentKeyID: 48185714
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 58108df8795aaae8d431b320125d34d14ee3a275
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41731949"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="sip-trunking-support-in-lync-server-2013"></a><span data-ttu-id="cf03f-102">Поддержка распределения каналов SIP в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cf03f-102">SIP trunking support in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cf03f-103">_**Тема последнего изменения:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="cf03f-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="cf03f-104">Если вы планируете использовать корпоративный голосовой звонок с помощью магистральной магистрали SIP, необходимо развернуть сервер-посредник и убедиться, что другие инфраструктуры и компоненты соответствуют требованиям, предъявляемым к вашей модели развертывания.</span><span class="sxs-lookup"><span data-stu-id="cf03f-104">If you plan to use Enterprise Voice with SIP trunking, you must deploy a Mediation Server and make sure that other infrastructure and components meet the support requirements appropriate to your deployment model.</span></span> <span data-ttu-id="cf03f-105">Подробные сведения о том, как определить, следует ли реализовывать магистральные линии SIP, можно найти [в статье Обзор МАГИСТРАЛИ SIP в Lync Server 2013](lync-server-2013-overview-of-sip-trunking.md) в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="cf03f-105">For details about determining whether to implement SIP trunking, see [Overview of SIP trunking in Lync Server 2013](lync-server-2013-overview-of-sip-trunking.md) in the Planning documentation.</span></span>

<span data-ttu-id="cf03f-106">Для поиска шлюзов, использующих коммутируемые коммутируемые телефонные сети, IP-АТС и службы магистрали SIP, включая полные IP-телефоны, можно использовать открытую программу взаимодействия Microsoft Unified Communications. поставщики услуг.</span><span class="sxs-lookup"><span data-stu-id="cf03f-106">You can use the Microsoft Unified Communications Open Interoperability Program for enterprise telephony infrastructure to find qualified public switched telephone network (PSTN) gateways, IP-PBXs, and SIP trunking services, including qualified IP telephony service providers.</span></span> <span data-ttu-id="cf03f-107">Дополнительные сведения можно найти на веб-сайте Microsoft Unified Communications Open для программы [http://go.microsoft.com/fwlink/p/?LinkId=203309](http://go.microsoft.com/fwlink/p/?linkid=203309)взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="cf03f-107">For details, see the Microsoft Unified Communications Open Interoperability Program website at [http://go.microsoft.com/fwlink/p/?LinkId=203309](http://go.microsoft.com/fwlink/p/?linkid=203309).</span></span>

<div>

## <a name="mediation-server-support"></a><span data-ttu-id="cf03f-108">Поддержка сервера исправлений</span><span class="sxs-lookup"><span data-stu-id="cf03f-108">Mediation Server Support</span></span>

<span data-ttu-id="cf03f-109">Для реализации магистральной магистрали SIP необходимо маршрутизировать соединение с помощью сервера-посредника, который выступает в качестве прокси-сервера для сеансов связи между клиентами Lync Server 2013 и поставщиком услуг.</span><span class="sxs-lookup"><span data-stu-id="cf03f-109">To implement SIP trunking, you must route the connection through a Mediation Server, which acts as a proxy for communications sessions between Lync Server 2013 clients and the service provider.</span></span> <span data-ttu-id="cf03f-110">Сервер-посредник декодирует трафик мультимедиа от клиентов и серверов и повторно кодирует его перед отправкой поставщику услуг.</span><span class="sxs-lookup"><span data-stu-id="cf03f-110">The Mediation Server decodes the media traffic from clients and servers and re-encodes it before sending it to the service provider.</span></span> <span data-ttu-id="cf03f-111">Повторная кодировка необходима, так как магистральные линии SIP не поддерживают некоторые кодеки, такие как использование звука в режиме реального времени (рта), а также согласование протоколов ICE для прохождения межсетевого экрана.</span><span class="sxs-lookup"><span data-stu-id="cf03f-111">The re-encoding is needed because SIP trunks do not support some codecs used, such as Real Time Audio (RTA) or Interactive Connectivity Establishment (ICE) protocol negotiation for firewall traversal.</span></span>

<span data-ttu-id="cf03f-112">Каждый сервер исправлений может иметь два сетевых адаптера, которые предоставляют внутренний и внешний сетевой интерфейс.</span><span class="sxs-lookup"><span data-stu-id="cf03f-112">Each Mediation Server can have two network adapters, which provide an internal and an external network interface.</span></span> <span data-ttu-id="cf03f-113">Внешний интерфейс обычно называется интерфейсом Gateway, так как он обычно используется для подключения к шлюзу КТСОП или IP-УАТС.</span><span class="sxs-lookup"><span data-stu-id="cf03f-113">The external interface is commonly called the gateway interface because, traditionally, it has been used to connect to a PSTN gateway or an IP-PBX.</span></span> <span data-ttu-id="cf03f-114">Для реализации магистральной магистрали SIP вы подключаете внешний интерфейс к контроллеру границ сеанса (SBC) на поставщике услуг.</span><span class="sxs-lookup"><span data-stu-id="cf03f-114">To implement a SIP trunk, you connect the external interface to a Session Border Controller (SBC) at a service provider.</span></span>

</div>

<div>

## <a name="centralized-vs-distributed-sip-trunking"></a><span data-ttu-id="cf03f-115">Централизованные и распределенные магистрали SIP</span><span class="sxs-lookup"><span data-stu-id="cf03f-115">Centralized vs. Distributed SIP Trunking</span></span>

<span data-ttu-id="cf03f-116">*Централизованная* В центре обработки данных каждый трафик по протоколу VoIP, включая трафик сайтов филиалов, перенаправляется по сети SIP.</span><span class="sxs-lookup"><span data-stu-id="cf03f-116">*Centralized* SIP trunking routes all Voice over Internet Protocol (VoIP) traffic, including branch site traffic, through your data center.</span></span> <span data-ttu-id="cf03f-117">Централизованная модель развертывания – это простой и экономичный подход, который обычно является предпочтительным для реализации каналов SIP с помощью Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="cf03f-117">The centralized deployment model is simple, cost-effective, and is generally the preferred approach for implementing SIP trunks with Lync Server 2013.</span></span>

<span data-ttu-id="cf03f-118">В зависимости от закономерностей использования на предприятии может потребоваться не перенаправлять всех пользователей с помощью централизованной магистрали SIP.</span><span class="sxs-lookup"><span data-stu-id="cf03f-118">Depending on usage patterns within your enterprise, you may not want to route all users through the centralized SIP trunk.</span></span> <span data-ttu-id="cf03f-119">Для анализа своих потребностей, ответьте на следующие вопросы.</span><span class="sxs-lookup"><span data-stu-id="cf03f-119">To analyze your needs, answer the following questions:</span></span>

  - <span data-ttu-id="cf03f-120">Насколько сильно каждый сайт?</span><span class="sxs-lookup"><span data-stu-id="cf03f-120">How big is each site?</span></span> <span data-ttu-id="cf03f-121">Сколько пользователей?</span><span class="sxs-lookup"><span data-stu-id="cf03f-121">How many users?</span></span>

  - <span data-ttu-id="cf03f-122">Какие номера на каждом из сайтов по своему направлению не получится звонить?</span><span class="sxs-lookup"><span data-stu-id="cf03f-122">Which Direct Inward Dialing (DID) numbers at each site get the most phone calls?</span></span>

<span data-ttu-id="cf03f-123">*Распространяется* Магистраль SIP — это модель развертывания, в которой вы реализуете локальную магистральную сеть SIP для одного или нескольких сайтов филиалов.</span><span class="sxs-lookup"><span data-stu-id="cf03f-123">*Distributed* SIP trunking is a deployment model in which you implement a local SIP trunk at one or more branch sites.</span></span> <span data-ttu-id="cf03f-124">Затем трафик VoIP перенаправляется непосредственно на сайт филиала прямо своему поставщику услуг, не проходясь в центре обработки данных.</span><span class="sxs-lookup"><span data-stu-id="cf03f-124">VoIP traffic is then routed from the branch site directly to their service provider, without going through your data center.</span></span>

<span data-ttu-id="cf03f-125">Распределенные магистрали SIP требуются только в следующих случаях.</span><span class="sxs-lookup"><span data-stu-id="cf03f-125">Distributed SIP trunking is required only in the following cases:</span></span>

  - <span data-ttu-id="cf03f-126">Для сайта филиала требуется бесперебойная телефонная связь (например, при отключении глобальной сети).</span><span class="sxs-lookup"><span data-stu-id="cf03f-126">The branch site requires survivable phone connectivity (for example, if the WAN goes down).</span></span> <span data-ttu-id="cf03f-127">Если для филиала требуется избыточность и отработка отказа, поставщик услуг будет взимать дополнительные деньги, а настройка может занять больше времени.</span><span class="sxs-lookup"><span data-stu-id="cf03f-127">If the branch does need redundancy and failover, the service provider will charge more and the configuration will take longer.</span></span> <span data-ttu-id="cf03f-128">Это необходимо проанализировать для каждого сайта филиала.</span><span class="sxs-lookup"><span data-stu-id="cf03f-128">This should be analyzed for each branch site.</span></span> <span data-ttu-id="cf03f-129">Некоторые из них могут потребовать избыточности и отработки отказа, в то время как другие могут не работать.</span><span class="sxs-lookup"><span data-stu-id="cf03f-129">Some of your branches may require redundancy and failover, while others may not.</span></span>

  - <span data-ttu-id="cf03f-130">Сайт филиала и центр обработки данных находятся в разных странах или регионах.</span><span class="sxs-lookup"><span data-stu-id="cf03f-130">The branch site and data center are in different countries/regions.</span></span> <span data-ttu-id="cf03f-131">По причинам обеспечения совместимости, а также по причинам правового характера требуется по крайней мере одна магистраль SIP на страну или регион.</span><span class="sxs-lookup"><span data-stu-id="cf03f-131">For compatibility and legal reasons, you need at least one SIP trunk per country/region.</span></span>

<span data-ttu-id="cf03f-132">Если вы решите, нужно ли развертывать централизованную или распределенную магистральную для SIP, требуется анализ затрат.</span><span class="sxs-lookup"><span data-stu-id="cf03f-132">Deciding whether to deploy centralized or distributed SIP trunking requires a cost-benefit analysis.</span></span> <span data-ttu-id="cf03f-133">В некоторых случаях может оказаться целесообразным отказаться от использования режима распределенного развертывания, даже если он не требуется.</span><span class="sxs-lookup"><span data-stu-id="cf03f-133">In some cases, it may be advantageous to opt for the distributed deployment mode, even if it is not required.</span></span> <span data-ttu-id="cf03f-134">В полностью централизованном развертывании трафик сайтов филиалов маршрутизируется по ссылкам WAN.</span><span class="sxs-lookup"><span data-stu-id="cf03f-134">In a completely centralized deployment, all branch site traffic is routed over WAN links.</span></span> <span data-ttu-id="cf03f-135">Вместо того, чтобы платить за полосу пропускания, необходимую для связи с WAN-каналами, возможно, вы предпочтете использование распределенных магистралей SIP.</span><span class="sxs-lookup"><span data-stu-id="cf03f-135">Instead of paying for the bandwidth required for WAN linking, you may want to use distributed SIP trunking.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="cf03f-136">Сведения о том, почему и как можно использовать распределенную магистральную сеть SIP, можно найти в разделе Планирование <A href="lync-server-2013-branch-site-sip-trunking.md">магистральных каналов SIP на сайте Lync Server 2013</A> в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="cf03f-136">For details about why and how you might use distributed SIP trunking, see <A href="lync-server-2013-branch-site-sip-trunking.md">Branch site SIP trunking in Lync Server 2013</A> in the Planning documentation.</span></span>



</div>

</div>

<div>

## <a name="supported-sip-trunking-connection-types"></a><span data-ttu-id="cf03f-137">Поддерживаемые типы подключений для магистралей SIP</span><span class="sxs-lookup"><span data-stu-id="cf03f-137">Supported SIP Trunking Connection Types</span></span>

<span data-ttu-id="cf03f-138">Lync Server 2013 поддерживает следующие типы подключений для магистральной магистрали SIP:</span><span class="sxs-lookup"><span data-stu-id="cf03f-138">Lync Server 2013 supports the following connection types for SIP trunking:</span></span>

  - <span data-ttu-id="cf03f-139">Технология мультипротокольной коммутации по меткам (MPLS) — это частная сеть, которая переносит и направляет данные из одного сетевого сайта на следующий.</span><span class="sxs-lookup"><span data-stu-id="cf03f-139">Multiprotocol Label Switching (MPLS) is a private network that directs and carries data from one network node to the next.</span></span> <span data-ttu-id="cf03f-140">Полоса пропускания MPLS-сети разделяется с другими подписчиками, и каждому пакету данных назначается метка для различения данных одного подписчика от других пакетов.</span><span class="sxs-lookup"><span data-stu-id="cf03f-140">The bandwidth in an MPLS network is shared with other subscribers, and each data packet is assigned a label to distinguish one subscriber’s data from another’s.</span></span> <span data-ttu-id="cf03f-141">Этот тип подключения не требует VPN.</span><span class="sxs-lookup"><span data-stu-id="cf03f-141">This connection type does not require VPN.</span></span> <span data-ttu-id="cf03f-142">Потенциальный недостаток — большое количество IP-трафика может сказаться на работе протокола VoIP, если последнему не дан приоритет.</span><span class="sxs-lookup"><span data-stu-id="cf03f-142">A potential drawback is that excessive IP traffic can interfere with VoIP operation unless VoIP traffic is given priority.</span></span>

  - <span data-ttu-id="cf03f-143">Личное соединение без другого трафика обычно является наиболее надежным и безопасным типом соединения (например, арендованным соединением с оптоволоконным каналом или линией T1).</span><span class="sxs-lookup"><span data-stu-id="cf03f-143">A private connection with no other traffic is typically the most reliable and secure connection type (for example, a leased fiber-optic connection or T1 line).</span></span> <span data-ttu-id="cf03f-144">Этот тип соединения обеспечивает максимальную емкость звонка, но обычно является наиболее дорогостоящей.</span><span class="sxs-lookup"><span data-stu-id="cf03f-144">This connection type provides the highest call-carrying capacity, but is typically the most expensive.</span></span> <span data-ttu-id="cf03f-145">VPN-сеть не требуется.</span><span class="sxs-lookup"><span data-stu-id="cf03f-145">VPN is not required.</span></span> <span data-ttu-id="cf03f-146">Частные подключения подходят для организаций с большим объемом звонков или строгими требованиями к безопасности и доступности.</span><span class="sxs-lookup"><span data-stu-id="cf03f-146">Private connections are appropriate for organizations with high call volumes or stringent security and availability requirements.</span></span>

  - <span data-ttu-id="cf03f-147">Общедоступный Интернет – это самый ресурсоемкий тип подключения, но и наименьший из них, но и тот, что и с минимальной емкостью звонков.</span><span class="sxs-lookup"><span data-stu-id="cf03f-147">The public Internet is the least expensive connection type, but also the least reliable, and the one with the lowest call-carrying capacity.</span></span> <span data-ttu-id="cf03f-148">Поставщик услуг телефонной связи через Интернет (ИТСП) может помочь защитить этот тип магистральной магистрали SIP, если он поддерживает TLS и защищенный транспортный протокол в реальном времени (SRTP) для шифрования сигналов и мультимедийного трафика.</span><span class="sxs-lookup"><span data-stu-id="cf03f-148">Your Internet Telephony Service Provider (ITSP) can help secure this SIP trunk connection type if it supports Transport Layer Security (TLS) and Secure Real-Time Transport Protocol (SRTP) to encrypt signaling and media traffic.</span></span> <span data-ttu-id="cf03f-149">Если вы не можете настроить подключение по магистрали SIP через Интернет для использования TLS и SRTP, мы настоятельно рекомендуем использовать туннель VPN для обеспечения более безопасного соединения.</span><span class="sxs-lookup"><span data-stu-id="cf03f-149">If you cannot configure a SIP trunk connection through the Internet to use TLS and SRTP, we strongly recommend that you use a VPN tunnel to provide a more secure connection.</span></span> <span data-ttu-id="cf03f-150">Обратитесь к своему ИТСПу, чтобы узнать, поддерживает ли он поддержку протокола TLS с SRTP.</span><span class="sxs-lookup"><span data-stu-id="cf03f-150">Contact your ITSP to determine whether it provides support for TLS with SRTP.</span></span>

<div>

## <a name="selecting-a-connection-type"></a><span data-ttu-id="cf03f-151">Выбор типа подключения</span><span class="sxs-lookup"><span data-stu-id="cf03f-151">Selecting a Connection Type</span></span>

<span data-ttu-id="cf03f-152">Наиболее подходящий для вашей организации тип подключения зависит от ваших потребностей и бюджета.</span><span class="sxs-lookup"><span data-stu-id="cf03f-152">The most appropriate SIP trunking connection type for your enterprise depends on your needs and your budget.</span></span>

  - <span data-ttu-id="cf03f-153">Для среднего или более крупного предприятия MPLS сеть, как правило, предоставляет наибольшее значение.</span><span class="sxs-lookup"><span data-stu-id="cf03f-153">For a mid-size or larger enterprise, an MPLS network generally provides the most value.</span></span> <span data-ttu-id="cf03f-154">Она обеспечивает необходимую полосу пропускания по меньшей цене, чем специализированная частная сеть.</span><span class="sxs-lookup"><span data-stu-id="cf03f-154">It can provide the necessary bandwidth at a cheaper rate than a specialized private network.</span></span>

  - <span data-ttu-id="cf03f-155">Для крупных предприятий может потребоваться частный оптоволоконный и оптоволоконный канал или линия T1.</span><span class="sxs-lookup"><span data-stu-id="cf03f-155">Large enterprises may require a private fiber-optic or T1 connection.</span></span>

  - <span data-ttu-id="cf03f-156">Для небольших организаций или сайтов филиалов с низким уровнем громкости звонка для этого лучше использовать функцию выбора SIP через Интернет.</span><span class="sxs-lookup"><span data-stu-id="cf03f-156">For a small enterprise or branch site with low call volume, SIP trunking through the Internet may be the best choice.</span></span> <span data-ttu-id="cf03f-157">Тем не менее, этот тип подключения не рекомендуется для сайтов среднего и более крупных размеров.</span><span class="sxs-lookup"><span data-stu-id="cf03f-157">However, this connection type is not recommended for mid-size or larger sites.</span></span>

</div>

</div>

<div>

## <a name="codec-support"></a><span data-ttu-id="cf03f-158">Поддерживаемые кодеки</span><span class="sxs-lookup"><span data-stu-id="cf03f-158">Codec Support</span></span>

<span data-ttu-id="cf03f-159">Прокси-сервер поставщика услуг должен поддерживать следующие кодеки:</span><span class="sxs-lookup"><span data-stu-id="cf03f-159">The service provider proxy must support the following codecs:</span></span>

  - <span data-ttu-id="cf03f-160">G.711 a-law (в основном используется за пределами Северной Америки)</span><span class="sxs-lookup"><span data-stu-id="cf03f-160">G.711 a-law (used primarily outside North America)</span></span>

  - <span data-ttu-id="cf03f-161">G.711 µ-law (используется в Северной Америке)</span><span class="sxs-lookup"><span data-stu-id="cf03f-161">G.711 µ-law (used in North America)</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

