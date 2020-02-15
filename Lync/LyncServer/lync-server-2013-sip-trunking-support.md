---
title: Lync Server 2013 поддержка распределения каналов SIP
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
ms.openlocfilehash: 2fd2bd6d66b8b4f040e654f2412f86027071f9ac
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42039049"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="sip-trunking-support-in-lync-server-2013"></a><span data-ttu-id="4d091-102">Поддержка распределения каналов SIP в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4d091-102">SIP trunking support in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4d091-103">_**Последнее изменение темы:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="4d091-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="4d091-104">Если вы планируете использовать корпоративную голосовую связь с магистральной магистралью SIP, необходимо развернуть сервер-посредник и убедиться, что другие инфраструктура и компоненты удовлетворяют требованиям поддержки, соответствующим модели развертывания.</span><span class="sxs-lookup"><span data-stu-id="4d091-104">If you plan to use Enterprise Voice with SIP trunking, you must deploy a Mediation Server and make sure that other infrastructure and components meet the support requirements appropriate to your deployment model.</span></span> <span data-ttu-id="4d091-105">Сведения о том, как определить, следует ли реализовать магистральную линию SIP, можно найти в статье [Обзор распределения каналов SIP в Lync Server 2013](lync-server-2013-overview-of-sip-trunking.md) в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="4d091-105">For details about determining whether to implement SIP trunking, see [Overview of SIP trunking in Lync Server 2013](lync-server-2013-overview-of-sip-trunking.md) in the Planning documentation.</span></span>

<span data-ttu-id="4d091-106">Вы можете использовать программу открытого взаимодействия объединенных коммуникаций Майкрософт (Microsoft Unified Communications Open Interoperability Program) для телефонной инфраструктуры предприятия, чтобы найти соответствующие шлюзы ТСОП, IP-УАТС и службы распределения каналов SIP, включая проверенных поставщиков услуг IP-телефонии.</span><span class="sxs-lookup"><span data-stu-id="4d091-106">You can use the Microsoft Unified Communications Open Interoperability Program for enterprise telephony infrastructure to find qualified public switched telephone network (PSTN) gateways, IP-PBXs, and SIP trunking services, including qualified IP telephony service providers.</span></span> <span data-ttu-id="4d091-107">Для получения дополнительных сведений посетите веб-сайт с открытым взаимодействием Microsoft [http://go.microsoft.com/fwlink/p/?LinkId=203309](http://go.microsoft.com/fwlink/p/?linkid=203309)Unified Communications.</span><span class="sxs-lookup"><span data-stu-id="4d091-107">For details, see the Microsoft Unified Communications Open Interoperability Program website at [http://go.microsoft.com/fwlink/p/?LinkId=203309](http://go.microsoft.com/fwlink/p/?linkid=203309).</span></span>

<div>

## <a name="mediation-server-support"></a><span data-ttu-id="4d091-108">Поддержка серверов-посредников</span><span class="sxs-lookup"><span data-stu-id="4d091-108">Mediation Server Support</span></span>

<span data-ttu-id="4d091-109">Для реализации распределения каналов SIP необходимо маршрутизировать подключение через сервер-посредник, который выступает в качестве прокси-сервера для сеансов связи между клиентами Lync Server 2013 и поставщиком услуг.</span><span class="sxs-lookup"><span data-stu-id="4d091-109">To implement SIP trunking, you must route the connection through a Mediation Server, which acts as a proxy for communications sessions between Lync Server 2013 clients and the service provider.</span></span> <span data-ttu-id="4d091-110">Сервер-посредник декодирует трафик мультимедиа от клиентов и серверов, а затем снова кодирует его перед отправкой поставщику услуг.</span><span class="sxs-lookup"><span data-stu-id="4d091-110">The Mediation Server decodes the media traffic from clients and servers and re-encodes it before sending it to the service provider.</span></span> <span data-ttu-id="4d091-111">Повторное кодирование требуется потому, что каналы SIP не поддерживают некоторые используемые кодеки, такие как RTA или согласование протоколов ICE для обхода брандмауэра.</span><span class="sxs-lookup"><span data-stu-id="4d091-111">The re-encoding is needed because SIP trunks do not support some codecs used, such as Real Time Audio (RTA) or Interactive Connectivity Establishment (ICE) protocol negotiation for firewall traversal.</span></span>

<span data-ttu-id="4d091-p104">Каждый сервер-посредник может иметь два сетевых адаптера, предоставляющих внутренний и внешний сетевой интерфейс. Внешний интерфейс обычно называется интерфейсом шлюза, поскольку он традиционно использовался для подключения к шлюзу ТСОП или IP-УАТС. Для реализации каналов SIP выполняется подключение внешнего интерфейса к пограничному контроллеру сеансов (SBC) поставщика услуг.</span><span class="sxs-lookup"><span data-stu-id="4d091-p104">Each Mediation Server can have two network adapters, which provide an internal and an external network interface. The external interface is commonly called the gateway interface because, traditionally, it has been used to connect to a PSTN gateway or an IP-PBX. To implement a SIP trunk, you connect the external interface to a Session Border Controller (SBC) at a service provider.</span></span>

</div>

<div>

## <a name="centralized-vs-distributed-sip-trunking"></a><span data-ttu-id="4d091-115">Централизованное и распространенное распределение каналов SIP</span><span class="sxs-lookup"><span data-stu-id="4d091-115">Centralized vs. Distributed SIP Trunking</span></span>

<span data-ttu-id="4d091-116">*Централизованная* Распределение каналов SIP маршрутизирует весь трафик по протоколу VoIP, включая трафик сайта филиала, через центр обработки данных.</span><span class="sxs-lookup"><span data-stu-id="4d091-116">*Centralized* SIP trunking routes all Voice over Internet Protocol (VoIP) traffic, including branch site traffic, through your data center.</span></span> <span data-ttu-id="4d091-117">Централизованная модель развертывания является простой и экономичной и обычно является предпочтительным подходом для реализации магистральных каналов SIP с Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4d091-117">The centralized deployment model is simple, cost-effective, and is generally the preferred approach for implementing SIP trunks with Lync Server 2013.</span></span>

<span data-ttu-id="4d091-p106">В зависимости от шаблонов использования, существующих на предприятии, маршрутизация всех пользователей через централизованный канал SIP может быть нежелательна. Чтобы проанализировать ваши потребности, ответьте на следующие вопросы.</span><span class="sxs-lookup"><span data-stu-id="4d091-p106">Depending on usage patterns within your enterprise, you may not want to route all users through the centralized SIP trunk. To analyze your needs, answer the following questions:</span></span>

  - <span data-ttu-id="4d091-p107">Насколько велик каждый сайт? Сколько пользователей?</span><span class="sxs-lookup"><span data-stu-id="4d091-p107">How big is each site? How many users?</span></span>

  - <span data-ttu-id="4d091-122">На какие номера прямого входящего набора на каждом сайте выполняется большинство телефонных вызовов?</span><span class="sxs-lookup"><span data-stu-id="4d091-122">Which Direct Inward Dialing (DID) numbers at each site get the most phone calls?</span></span>

<span data-ttu-id="4d091-p108">*Распространенное* распределение каналов SIP — это модель развертывания, в которой реализуется локальный канал SIP на одном или нескольких сайтах филиалов. Затем трафик VoIP направляется из такого сайта филиала непосредственно его поставщику услуг, без прохода через центр обработки данных.</span><span class="sxs-lookup"><span data-stu-id="4d091-p108">*Distributed* SIP trunking is a deployment model in which you implement a local SIP trunk at one or more branch sites. VoIP traffic is then routed from the branch site directly to their service provider, without going through your data center.</span></span>

<span data-ttu-id="4d091-125">Распространенное распределение каналов SIP требуется только в следующих случаях.</span><span class="sxs-lookup"><span data-stu-id="4d091-125">Distributed SIP trunking is required only in the following cases:</span></span>

  - <span data-ttu-id="4d091-p109">Сайту филиала требуется безотказное телефонное подключение (например, на случай выхода из строя сети WAN). Если филиалу действительно требуется избыточность и отказоустойчивость, то необходимо учесть, что поставщик услуг выставит счет на большую сумму, и конфигурация займет больше времени. Это следует проанализировать для каждого сайта филиала. Одним филиалам может требоваться избыточность и отказоустойчивость, другим нет.</span><span class="sxs-lookup"><span data-stu-id="4d091-p109">The branch site requires survivable phone connectivity (for example, if the WAN goes down). If the branch does need redundancy and failover, the service provider will charge more and the configuration will take longer. This should be analyzed for each branch site. Some of your branches may require redundancy and failover, while others may not.</span></span>

  - <span data-ttu-id="4d091-p110">Сайт филиала и центр обработки данных находятся в разных странах или регионах. Для обеспечения совместимости и соблюдения правовых норм потребуется по крайней мере по одному каналу SIP на страну или регион.</span><span class="sxs-lookup"><span data-stu-id="4d091-p110">The branch site and data center are in different countries/regions. For compatibility and legal reasons, you need at least one SIP trunk per country/region.</span></span>

<span data-ttu-id="4d091-p111">Для принятия решения о развертывании централизованного или распространенного распределения каналов SIP необходимо выполнить анализ затрат и выгод. В некоторых случаях может оказаться выгоднее согласиться на режим распространенного развертывания, ладе если она не требуется. В полностью централизованном развертывании весь трафик сайтов филиалов маршрутизируется через каналы связи WAN. Чтобы не оплачивать пропускную способность, необходимую для каналов связи WAN, вы можете предпочесть воспользоваться распространенным распределением каналов SIP.</span><span class="sxs-lookup"><span data-stu-id="4d091-p111">Deciding whether to deploy centralized or distributed SIP trunking requires a cost-benefit analysis. In some cases, it may be advantageous to opt for the distributed deployment mode, even if it is not required. In a completely centralized deployment, all branch site traffic is routed over WAN links. Instead of paying for the bandwidth required for WAN linking, you may want to use distributed SIP trunking.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="4d091-136">Сведения о том, почему и как можно использовать распределенную магистральную магистральную линию SIP, можно найти в статье Планирование распределения <A href="lync-server-2013-branch-site-sip-trunking.md">каналов SIP на сайте филиала в Lync Server 2013</A> .</span><span class="sxs-lookup"><span data-stu-id="4d091-136">For details about why and how you might use distributed SIP trunking, see <A href="lync-server-2013-branch-site-sip-trunking.md">Branch site SIP trunking in Lync Server 2013</A> in the Planning documentation.</span></span>



</div>

</div>

<div>

## <a name="supported-sip-trunking-connection-types"></a><span data-ttu-id="4d091-137">Поддерживаемые типы подключений SIP-магистралей</span><span class="sxs-lookup"><span data-stu-id="4d091-137">Supported SIP Trunking Connection Types</span></span>

<span data-ttu-id="4d091-138">Lync Server 2013 поддерживает следующие типы подключений для распределения каналов SIP:</span><span class="sxs-lookup"><span data-stu-id="4d091-138">Lync Server 2013 supports the following connection types for SIP trunking:</span></span>

  - <span data-ttu-id="4d091-p112">Сеть многопротокольной коммутации по меткам (MPLS) — это частная сеть, которая направляет и передает данные от одного сетевого узла к следующему. Пропускная способность в сети MPLS совместно используется с другими подписчиками, и каждому пакету данных назначается метка, чтобы отличать данные одного подписчика от данных другого подписчика. Для такого типа подключения не требуется VPN. Потенциальный недостаток состоит в том, что избыточный IP-трафик может препятствовать работе VoIP, пока трафик VoIP не получит приоритет.</span><span class="sxs-lookup"><span data-stu-id="4d091-p112">Multiprotocol Label Switching (MPLS) is a private network that directs and carries data from one network node to the next. The bandwidth in an MPLS network is shared with other subscribers, and each data packet is assigned a label to distinguish one subscriber’s data from another’s. This connection type does not require VPN. A potential drawback is that excessive IP traffic can interfere with VoIP operation unless VoIP traffic is given priority.</span></span>

  - <span data-ttu-id="4d091-p113">Частное подключение без постороннего трафика обычно оказывается более надежным и безопасным типом подключения (например, это может быть выделенное оптоволоконное подключение или линия Т1). Такой тип подключения обеспечивает наивысший объем передачи вызовов, но обычно является наиболее затратным. VPN не требуется. Частные подключения подходят для организаций с большими объемами вызовов или с жесткими требованиями к безопасности и доступности.</span><span class="sxs-lookup"><span data-stu-id="4d091-p113">A private connection with no other traffic is typically the most reliable and secure connection type (for example, a leased fiber-optic connection or T1 line). This connection type provides the highest call-carrying capacity, but is typically the most expensive. VPN is not required. Private connections are appropriate for organizations with high call volumes or stringent security and availability requirements.</span></span>

  - <span data-ttu-id="4d091-p114">Общедоступный Интернет — это самый экономичный тип подключения, но также и наименее надежный, и с самым низким объемом переданных вызовов. Ваш поставщик услуг Интернет-телефонии может содействовать защите этого типа подключения каналов SIP, если поддерживает TLS и протокол SRTP для шифрования передачи сигналов и трафика мультимедиа. Если отсутствует возможность настройки подключения каналов SIP по Интернету с использованием TLS и протокола SRTP, мы настоятельно рекомендуем задействовать VPN-туннель, чтобы обеспечить более безопасное подключение. Обратитесь к вашему поставщику услуг Интернет-телефонии, чтобы узнать, поддерживает ли он TLS с протоколом SRTP.</span><span class="sxs-lookup"><span data-stu-id="4d091-p114">The public Internet is the least expensive connection type, but also the least reliable, and the one with the lowest call-carrying capacity. Your Internet Telephony Service Provider (ITSP) can help secure this SIP trunk connection type if it supports Transport Layer Security (TLS) and Secure Real-Time Transport Protocol (SRTP) to encrypt signaling and media traffic. If you cannot configure a SIP trunk connection through the Internet to use TLS and SRTP, we strongly recommend that you use a VPN tunnel to provide a more secure connection. Contact your ITSP to determine whether it provides support for TLS with SRTP.</span></span>

<div>

## <a name="selecting-a-connection-type"></a><span data-ttu-id="4d091-151">Выбор типа подключения</span><span class="sxs-lookup"><span data-stu-id="4d091-151">Selecting a Connection Type</span></span>

<span data-ttu-id="4d091-152">Наиболее подходящий для вашего предприятия тип подключения каналов SIP зависит от ваших потребностей и бюджета.</span><span class="sxs-lookup"><span data-stu-id="4d091-152">The most appropriate SIP trunking connection type for your enterprise depends on your needs and your budget.</span></span>

  - <span data-ttu-id="4d091-p115">Как правило, для средних и крупных предприятий наилучшим образом подходит сеть MPLS. Она может обеспечить необходимую пропускную способность при более низкой стоимости, чем специальная частная сеть.</span><span class="sxs-lookup"><span data-stu-id="4d091-p115">For a mid-size or larger enterprise, an MPLS network generally provides the most value. It can provide the necessary bandwidth at a cheaper rate than a specialized private network.</span></span>

  - <span data-ttu-id="4d091-155">Крупным предприятиям может требоваться частное подключение по оптоволоконной линии или линии Т1.</span><span class="sxs-lookup"><span data-stu-id="4d091-155">Large enterprises may require a private fiber-optic or T1 connection.</span></span>

  - <span data-ttu-id="4d091-p116">Для небольших предприятий и филиалов с низкой интенсивностью вызовов наилучшим вариантом может оказаться распределение каналов SIP через Интернет. Однако такой тип подключения не рекомендуется для средних и крупных сайтов.</span><span class="sxs-lookup"><span data-stu-id="4d091-p116">For a small enterprise or branch site with low call volume, SIP trunking through the Internet may be the best choice. However, this connection type is not recommended for mid-size or larger sites.</span></span>

</div>

</div>

<div>

## <a name="codec-support"></a><span data-ttu-id="4d091-158">Поддержка кодеков</span><span class="sxs-lookup"><span data-stu-id="4d091-158">Codec Support</span></span>

<span data-ttu-id="4d091-159">Прокси-сервер поставщика услуг должен поддерживать следующие кодеки:</span><span class="sxs-lookup"><span data-stu-id="4d091-159">The service provider proxy must support the following codecs:</span></span>

  - <span data-ttu-id="4d091-160">G.711 a-law (в основном используется за пределами Серверной Америки);</span><span class="sxs-lookup"><span data-stu-id="4d091-160">G.711 a-law (used primarily outside North America)</span></span>

  - <span data-ttu-id="4d091-161">G.711 µ-law (используется в Северной Америке).</span><span class="sxs-lookup"><span data-stu-id="4d091-161">G.711 µ-law (used in North America)</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

