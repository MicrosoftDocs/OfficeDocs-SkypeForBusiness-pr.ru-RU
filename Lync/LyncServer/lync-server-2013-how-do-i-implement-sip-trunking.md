---
title: 'Lync Server 2013: как реализовать магистральные линии SIP?'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: How do I implement SIP trunking?
ms:assetid: 273a22b1-8a4c-4187-acf8-c57d5c6598ce
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425743(v=OCS.15)
ms:contentKeyID: 48183666
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 062eb44fb79d6ecfa33f449e62341003bbed571b
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42050451"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="how-do-i-implement-sip-trunking-in-lync-server-2013"></a><span data-ttu-id="52d3b-102">Как реализовать магистральные линии SIP в Lync Server 2013?</span><span class="sxs-lookup"><span data-stu-id="52d3b-102">How do I implement SIP trunking in Lync Server 2013?</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="52d3b-103">_**Последнее изменение темы:** 2013-03-18_</span><span class="sxs-lookup"><span data-stu-id="52d3b-103">_**Topic Last Modified:** 2013-03-18_</span></span>

<span data-ttu-id="52d3b-104">Для реализации распределения каналов SIP необходимо маршрутизировать подключение через сервер-посредник, который выступает в качестве прокси-сервера для сеансов связи между клиентами Lync Server 2013 и поставщиком услуг и транспортным носителем (при необходимости).</span><span class="sxs-lookup"><span data-stu-id="52d3b-104">To implement SIP trunking, you must route the connection through a Mediation Server, which acts as a proxy for communications sessions between Lync Server 2013 clients and the service provider and transcodes media, when necessary.</span></span>

<span data-ttu-id="52d3b-105">Каждый сервер-посредник имеет внутренний сетевой интерфейс и внешний сетевой интерфейс.</span><span class="sxs-lookup"><span data-stu-id="52d3b-105">Each Mediation Server has an internal network interface and an external network interface.</span></span> <span data-ttu-id="52d3b-106">Внутренний интерфейс подключается к серверам переднего плана.</span><span class="sxs-lookup"><span data-stu-id="52d3b-106">The internal interface connects to the Front End Servers.</span></span> <span data-ttu-id="52d3b-107">Внешний интерфейс обычно называется интерфейсом шлюза, так как он традиционно использовался для подключения сервера-посредника к шлюзу телефонной сети общего пользования (PSTN) или IP-УАТС.</span><span class="sxs-lookup"><span data-stu-id="52d3b-107">The external interface is commonly called the gateway interface because it has traditionally been used to connect the Mediation Server to a public switched telephone network (PSTN) gateway or an IP-PBX.</span></span> <span data-ttu-id="52d3b-108">Для реализации магистрали SIP Внешний интерфейс сервера-посредника подключается к внешнему пограничному компоненту ITSP.</span><span class="sxs-lookup"><span data-stu-id="52d3b-108">To implement a SIP trunk, you connect the external interface of the Mediation Server to the external edge component of the ITSP.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="52d3b-109">Внешний пограничный компонент ITSP может быть пограничным контроллером сеансов, маршрутизатором или шлюзом.</span><span class="sxs-lookup"><span data-stu-id="52d3b-109">The external edge component of the ITSP could be a Session Border Controller (SBC), a router, or a gateway.</span></span>



</div>

<span data-ttu-id="52d3b-110">Дополнительные сведения о серверах-посредниках см. [в компоненте сервера-посредника в Lync Server 2013](lync-server-2013-mediation-server-component.md).</span><span class="sxs-lookup"><span data-stu-id="52d3b-110">For details about Mediation Servers, see [Mediation Server component in Lync Server 2013](lync-server-2013-mediation-server-component.md).</span></span>

<div>

## <a name="centralized-vs-distributed-sip-trunking"></a><span data-ttu-id="52d3b-111">Централизованные и распределенные SIP-магистрали</span><span class="sxs-lookup"><span data-stu-id="52d3b-111">Centralized vs. Distributed SIP Trunking</span></span>

<span data-ttu-id="52d3b-112">*Централизованная* Распределение каналов SIP маршрутизирует весь трафик по протоколу VoIP, включая трафик сайта филиала, через центральный сайт.</span><span class="sxs-lookup"><span data-stu-id="52d3b-112">*Centralized* SIP trunking routes all Voice over Internet Protocol (VoIP) traffic, including branch site traffic, through your central site.</span></span> <span data-ttu-id="52d3b-113">Централизованная модель развертывания является простой, экономичной и обычно является рекомендуемым способом реализации магистральных каналов SIP с помощью Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="52d3b-113">The centralized deployment model is simple, cost-effective, and is generally the recommended approach for implementing SIP trunks with Lync Server 2013.</span></span>

<span data-ttu-id="52d3b-114">*Распространяется* Распределение каналов SIP — это модель развертывания, в которой вы реализуете локальную магистраль SIP на одном или нескольких сайтах филиалов.</span><span class="sxs-lookup"><span data-stu-id="52d3b-114">*Distributed* SIP trunking is a deployment model in which you implement a local SIP trunk at one or more branch sites.</span></span> <span data-ttu-id="52d3b-115">Затем трафик VoIP перенаправляется от сайта филиала непосредственно поставщику услуг без необходимости проходить через центральный сайт.</span><span class="sxs-lookup"><span data-stu-id="52d3b-115">VoIP traffic is then routed from the branch site directly to a service provider without going through the central site.</span></span>

<span data-ttu-id="52d3b-116">Распределенные SIP-магистрали требуются только в следующих случаях:</span><span class="sxs-lookup"><span data-stu-id="52d3b-116">Distributed SIP trunking is required only in the following cases:</span></span>

  - <span data-ttu-id="52d3b-117">Сайту филиала требуется безотказное телефонное подключение (например, на случай выхода из строя сети WAN).</span><span class="sxs-lookup"><span data-stu-id="52d3b-117">The branch site requires survivable phone connectivity (for example, if the WAN goes down).</span></span> <span data-ttu-id="52d3b-118">Это требование необходимо проанализировать для каждого сайта филиала; для некоторых ветвей может потребоваться избыточность и отработка отказа, в то время как другие могут отключаться.</span><span class="sxs-lookup"><span data-stu-id="52d3b-118">This requirement should be analyzed for each branch site; some of your branches may require redundancy and failover, whereas others may not.</span></span>

  - <span data-ttu-id="52d3b-119">Между двумя центральными сайтами необходима устойчивость.</span><span class="sxs-lookup"><span data-stu-id="52d3b-119">Resiliency is required between two central sites.</span></span> <span data-ttu-id="52d3b-120">Необходимо убедиться, что магистральная линия SIP завершается на каждом центральном сайте.</span><span class="sxs-lookup"><span data-stu-id="52d3b-120">You need to make sure that a SIP trunk terminates at each central site.</span></span> <span data-ttu-id="52d3b-121">Например, если у вас есть сайты Dublin и Таквила, и оба используют только одну магистраль SIP сайта, то при отключении магистрали другие пользователи сайта не смогут совершать звонки по протоколу PSTN.</span><span class="sxs-lookup"><span data-stu-id="52d3b-121">For example, if you have Dublin and Tukwila central sites and both use only one site’s SIP trunk, if the trunk goes down, the other site’s users cannot make PSTN calls.</span></span>

  - <span data-ttu-id="52d3b-122">Сайт филиала и центральный сайт находятся в разных странах или регионах.</span><span class="sxs-lookup"><span data-stu-id="52d3b-122">The branch site and central site are in different countries/regions.</span></span> <span data-ttu-id="52d3b-123">По причинам обеспечения совместимости и по юридическим резонам требуется по крайней мере одна SIP-магистраль на страну или регион.</span><span class="sxs-lookup"><span data-stu-id="52d3b-123">For compatibility and legal reasons, you need at least one SIP trunk per country/region.</span></span> <span data-ttu-id="52d3b-124">Например, в Евросоюзе коммуникации не могут покинуть страну или регион не завершившись в централизованной точке.</span><span class="sxs-lookup"><span data-stu-id="52d3b-124">For example, in the European Union, communications cannot leave a country/region without terminating locally at a centralized point.</span></span>

<span data-ttu-id="52d3b-125">В зависимости от географического расположения сайтов и объема трафика, который вы планируете использовать в Организации, может быть нежелательно маршрутизировать всех пользователей через центральную магистральную линию SIP, или вы можете выбрать маршрутизацию некоторых пользователей через магистраль SIP на своем сайте филиала.</span><span class="sxs-lookup"><span data-stu-id="52d3b-125">Depending on the geographical location of sites and how much traffic you anticipate within your enterprise, you may not want to route all users through the central SIP trunk, or you may opt to route some users through a SIP trunk at their branch site.</span></span> <span data-ttu-id="52d3b-126">Для анализа ваших потребностей, ответьте на следующие вопросы:</span><span class="sxs-lookup"><span data-stu-id="52d3b-126">To analyze your needs, answer the following questions:</span></span>

  - <span data-ttu-id="52d3b-127">Каков размер каждого сайта (то есть количество пользователей, для которых включена Корпоративная голосовая связь)?</span><span class="sxs-lookup"><span data-stu-id="52d3b-127">How big is each site (that is, how many users are enabled for Enterprise Voice)?</span></span>

  - <span data-ttu-id="52d3b-128">Сколько номеров прямого входного набора на каждом участке получает больше всего телефонных звонков?</span><span class="sxs-lookup"><span data-stu-id="52d3b-128">Which direct inward dialing (DID) numbers at each site get the most phone calls?</span></span>

<span data-ttu-id="52d3b-129">Принятие решения о развертывании централизованных или распределенных SIP-магистралей требует проведения функционально-стоимостного анализа.</span><span class="sxs-lookup"><span data-stu-id="52d3b-129">The decision whether to deploy centralized or distributed SIP trunking requires a cost-benefit analysis.</span></span> <span data-ttu-id="52d3b-130">В некоторых случаях лучше использовать распределенные магистрали, даже если это не является обязательным.</span><span class="sxs-lookup"><span data-stu-id="52d3b-130">In some cases, it may be advantageous to opt for the distributed deployment model even if it is not required.</span></span> <span data-ttu-id="52d3b-131">В полностью централизованном развертывании весь трафик сайтов филиалов маршрутизируется через каналы связи WAN.</span><span class="sxs-lookup"><span data-stu-id="52d3b-131">In a completely centralized deployment, all branch site traffic is routed over WAN links.</span></span> <span data-ttu-id="52d3b-132">Чтобы не оплачивать пропускную способность, необходимую для каналов связи WAN, вы можете предпочесть воспользоваться распространенным распределением каналов SIP.</span><span class="sxs-lookup"><span data-stu-id="52d3b-132">Instead of paying for the bandwidth required for WAN linking, you may want to use distributed SIP trunking.</span></span> <span data-ttu-id="52d3b-133">Например, может потребоваться развернуть сервер Standard Edition на сайте филиала с федерациюм на центральном сайте или развернуть устройство для обеспечения связи в филиалах или сервер для обеспечения связи в филиалах с небольшим шлюзом.</span><span class="sxs-lookup"><span data-stu-id="52d3b-133">For example, you may want to deploy a Standard Edition server at a branch site with federation to the central site, or you may want to deploy a Survivable Branch Appliance or a Survivable Branch Server with a small gateway.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="52d3b-134">Подробные сведения о распределенной магистральной линии SIP можно найти <A href="lync-server-2013-branch-site-sip-trunking.md">в разделе Branch SIP site Branch в Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="52d3b-134">For details about distributed SIP trunking, see <A href="lync-server-2013-branch-site-sip-trunking.md">Branch site SIP trunking in Lync Server 2013</A>.</span></span>



</div>

</div>

<div>

## <a name="supported-sip-trunking-connection-types"></a><span data-ttu-id="52d3b-135">Поддерживаемые типы подключений SIP-магистралей</span><span class="sxs-lookup"><span data-stu-id="52d3b-135">Supported SIP Trunking Connection Types</span></span>

<span data-ttu-id="52d3b-136">Lync Server поддерживает следующие типы подключений для распределения каналов SIP:</span><span class="sxs-lookup"><span data-stu-id="52d3b-136">Lync Server supports the following connection types for SIP trunking:</span></span>

  - <span data-ttu-id="52d3b-p109">Технология мультипротокольной коммутации по меткам (MPLS) — это частная сеть, которая переносит и направляет данные из одного узла сети в следующий. Полоса пропускания MPLS-сети разделяется с другими подписчиками и каждому пакету данных назначается метка для различения данных одного подписчика от других пакетов. Для данного типа подключения виртуальная частная сеть (VPN) не требуется. Потенциальный недостаток — большое количество IP-трафика может сказаться на работе протокола VoIP, если последнему не дан приоритет.</span><span class="sxs-lookup"><span data-stu-id="52d3b-p109">Multiprotocol Label Switching (MPLS) is a private network that directs and carries data from one network node to the next. The bandwidth in an MPLS network is shared with other subscribers, and each data packet is assigned a label to distinguish one subscriber’s data from another’s. This connection type does not require a virtual private network (VPN). A potential drawback is that excessive IP traffic can interfere with VoIP operation unless VoIP traffic is given priority.</span></span>

  - <span data-ttu-id="52d3b-p110">Частное подключение без другого трафика, например арендованное оптоволоконное подключение или линия T1 обычно является наиболее надежным и безопасным методом подключения. Данный тип обеспечивает самую высокую способность выдерживать нагрузку, но и является самым дорогим. VPN-сеть не требуется. Частные подключения подходят для организаций с большим объемом звонков или строгими требованиями к безопасности и доступности.</span><span class="sxs-lookup"><span data-stu-id="52d3b-p110">A private connection with no other traffic—for example, a leased fiber-optic connection or T1 line—is typically the most reliable and secure connection type. This connection type provides the highest call-carrying capacity, but it is typically the most expensive. VPN is not required. Private connections are appropriate for organizations with high call volumes or stringent security and availability requirements.</span></span>

  - <span data-ttu-id="52d3b-145">Internet — наименее дорогой тип подключения, но и самый ненадежный.</span><span class="sxs-lookup"><span data-stu-id="52d3b-145">The Internet is the least expensive connection type, but it is also the least reliable.</span></span> <span data-ttu-id="52d3b-146">Подключение к Интернету это единственный тип подключения к магистрали SIP Lync Server, требующий VPN.</span><span class="sxs-lookup"><span data-stu-id="52d3b-146">Internet connection is the only Lync Server SIP trunking connection type that requires VPN.</span></span>

<div>

## <a name="selecting-a-connection-type"></a><span data-ttu-id="52d3b-147">Выбор типа подключения</span><span class="sxs-lookup"><span data-stu-id="52d3b-147">Selecting a Connection Type</span></span>

<span data-ttu-id="52d3b-148">Наиболее подходящий для вашей организации тип подключения зависит от ваших потребностей и бюджета.</span><span class="sxs-lookup"><span data-stu-id="52d3b-148">The most appropriate SIP trunking connection type for your enterprise depends on your needs and your budget.</span></span>

  - <span data-ttu-id="52d3b-p112">Для средних и больших предприятий MPLS-сеть обычно подходит лучше всего. Она обеспечивает необходимую полосу пропускания по меньшей цене, чем специализированная частная сеть.</span><span class="sxs-lookup"><span data-stu-id="52d3b-p112">For a mid-size or larger enterprise, an MPLS network usually provides the greatest value. It can provide the necessary bandwidth at a cheaper rate than a specialized private network.</span></span>

  - <span data-ttu-id="52d3b-151">Для больших предприятий может потребовать отдельный оптоволоконный канал, линия T1, T3 или более высокого класса (E1, E3 или выше в Евросоюзе).</span><span class="sxs-lookup"><span data-stu-id="52d3b-151">Large enterprises may require a private fiber-optic, T1, T3 or higher connection (E1, E3 or higher in the European Union).</span></span>

  - <span data-ttu-id="52d3b-152">Для небольших предприятий и филиалов с низкой интенсивностью вызовов наилучшим вариантом может оказаться распределение каналов SIP через Интернет.</span><span class="sxs-lookup"><span data-stu-id="52d3b-152">For a small enterprise or branch site with low call volume, SIP trunking through the Internet may be the best choice.</span></span> <span data-ttu-id="52d3b-153">Данный тип подключения не рекомендуется для участков среднего и большого размера.</span><span class="sxs-lookup"><span data-stu-id="52d3b-153">This connection type is not recommended for mid-size or larger sites.</span></span>

</div>

</div>

<div>

## <a name="bandwidth-requirements"></a><span data-ttu-id="52d3b-154">Требования к полосе пропускания</span><span class="sxs-lookup"><span data-stu-id="52d3b-154">Bandwidth Requirements</span></span>

<span data-ttu-id="52d3b-p114">Требуемая полоса пропускания зависит от количества одновременных звонков, которая система должна быть способна обрабатывать. Следует учитывать доступность полосы для реализации в полной мере максимальной пропускной способности, за которую вы платите. Используйте следующую формулу для расчета требований к максимальной пропускной способности для SIP-магистрали:</span><span class="sxs-lookup"><span data-stu-id="52d3b-p114">The amount of bandwidth your implementation requires depends on call capacity (the number of concurrent calls you must be able to support). You need to consider bandwidth availability, so that you can take full advantage of the peak capacity that you have paid for. Use the following formula to calculate SIP trunk peak bandwidth requirement:</span></span>

<span data-ttu-id="52d3b-158">Максимальная пропускная способность SIP-магистрали = Макс. кол-во одновременных звонков x (64 кбит + размер заголовка)</span><span class="sxs-lookup"><span data-stu-id="52d3b-158">SIP Trunk Peak Bandwidth = Max Simultaneous Calls x (64 kbps + header size)</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="52d3b-159">Размер заголовка максимум 20 байт</span><span class="sxs-lookup"><span data-stu-id="52d3b-159">Header size is 20 bytes maximum.</span></span>



</div>

</div>

<div>

## <a name="codec-support"></a><span data-ttu-id="52d3b-160">Поддерживаемые кодеки</span><span class="sxs-lookup"><span data-stu-id="52d3b-160">Codec Support</span></span>

<span data-ttu-id="52d3b-161">Lync Server 2013 поддерживает только следующие кодеки:</span><span class="sxs-lookup"><span data-stu-id="52d3b-161">Lync Server 2013 supports only the following codecs:</span></span>

  - <span data-ttu-id="52d3b-162">G.711 a-law (в основном используется за пределами Северной Америки)</span><span class="sxs-lookup"><span data-stu-id="52d3b-162">G.711 a-law (used primarily outside North America)</span></span>

  - <span data-ttu-id="52d3b-163">G.711 µ-law (используется в Северной Америке)</span><span class="sxs-lookup"><span data-stu-id="52d3b-163">G.711 µ-law (used in North America)</span></span>

</div>

<div>

## <a name="internet-telephony-service-provider"></a><span data-ttu-id="52d3b-164">Оператор Интернет-телефонии</span><span class="sxs-lookup"><span data-stu-id="52d3b-164">Internet Telephony Service Provider</span></span>

<span data-ttu-id="52d3b-165">Реализация подключения SIP-магистрали к стороне оператора зависит от оператора.</span><span class="sxs-lookup"><span data-stu-id="52d3b-165">How you implement the service provider side of a SIP trunk connection varies from one ITSP to another.</span></span> <span data-ttu-id="52d3b-166">Для получения сведения о развертывания, свяжитесь с вашим оператором.</span><span class="sxs-lookup"><span data-stu-id="52d3b-166">For deployment information, contact your service provider.</span></span> <span data-ttu-id="52d3b-167">Список сертифицированных поставщиков услуг распределения каналов SIP представлен на [веб-сайте Microsoft Unified Communications Open Program](http://go.microsoft.com/fwlink/?linkid=287029).</span><span class="sxs-lookup"><span data-stu-id="52d3b-167">For a list of certified SIP trunking service providers, see [Microsoft Unified Communications Open Interoperability Program website](http://go.microsoft.com/fwlink/?linkid=287029).</span></span>

<span data-ttu-id="52d3b-168">Дополнительные. сведения о сертифицированных Майкрософтом операторах SIP-магистралей можно получить, связавшись с вашим представителем Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="52d3b-168">For details about Microsoft certified SIP trunking providers, contact your Microsoft representative.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="52d3b-p116">Вам следует работать с сертифицированным оператором, чтобы обеспечить весь функционал SIP-магистрали (например, должны поддерживаться функции настройки и управления сессиями и всех расширенных служб VoIP). Техническая поддержка Майкрософт не распространяется на конфигурации, в которых используются услуги не сертифицированных операторов. Если в данный момент вы используете оператора Интернет-телефонии, не сертифицированного для SIP-магистралей, вы можете оставить его в качестве Интернет-оператора, и перейти к использования оператора для SIP-магистралей, сертифицированного Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="52d3b-p116">You must use a Microsoft certified service provider to ensure that your ITSP supports all of the functionality that traverses the SIP trunk (for example, setting up and managing sessions and supporting all of the extended VoIP services). Microsoft technical support does not extend to configurations that use noncertified providers. If you currently use an Internet service provider that is not certified for SIP trunking, you can opt to continue using that provider as your ISP and use a provider certified by Microsoft for SIP trunking.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

