---
title: 'Lync Server 2013: Настройка обхода сервера мультимедиа'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure media bypass
ms:assetid: f50a7a13-c6a0-48f1-bee1-e45fa2b2f9b8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413028(v=OCS.15)
ms:contentKeyID: 48185836
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6153be57ec60e58b404370ece2c2214ae33083c1
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48520648"
---
# <a name="configure-media-bypass-in-lync-server-2013"></a><span data-ttu-id="009e1-102">Настройка обхода сервера мультимедиа в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="009e1-102">Configure media bypass in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="009e1-103">_**Последнее изменение темы:** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="009e1-103">_**Topic Last Modified:** 2013-02-24_</span></span>

<span data-ttu-id="009e1-104">В этом разделе предполагается, что вы уже опубликовали и настроили один или несколько серверов-посредников (как описано в разделе [Определение сервера-посредника в построителе топологий в Lync server 2013](lync-server-2013-define-a-mediation-server-in-topology-builder.md) и [Публикация топологии в Lync Server 2013](lync-server-2013-publish-the-topology.md), а также на странице [Определение и Настройка пула переднего плана или сервера Standard Edition в Lync Server 2013](lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md) и [опубликуйте топологию в Lync Server 2013](lync-server-2013-publish-the-topology.md), соответственно,</span><span class="sxs-lookup"><span data-stu-id="009e1-104">This section assumes that you have already published and configured either at least one or more Mediation Servers (as described in [Define a Mediation Server in Topology Builder in Lync Server 2013](lync-server-2013-define-a-mediation-server-in-topology-builder.md) and [Publish the topology in Lync Server 2013](lync-server-2013-publish-the-topology.md), or in [Define and configure a Front End pool or Standard Edition server in Lync Server 2013](lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md) and [Publish the topology in Lync Server 2013](lync-server-2013-publish-the-topology.md), respectively, all in the Deployment documentation).</span></span>

<span data-ttu-id="009e1-105">В этом разделе также предполагается, что вы определили по крайней мере один узел шлюза для обеспечения подключения PSTN, как описано в разделе [определение шлюза в построителе топологий в Lync Server 2013](lync-server-2013-define-a-gateway-in-topology-builder.md).</span><span class="sxs-lookup"><span data-stu-id="009e1-105">This section also assumes that you have defined at least one gateway peer to provide PSTN connectivity, as described in [Define a gateway in Topology Builder in Lync Server 2013](lync-server-2013-define-a-gateway-in-topology-builder.md).</span></span> <span data-ttu-id="009e1-106">Если одноранговый узел, к которому вы подключаетесь, является SBC поставщика распределения каналов SIP, убедитесь, что поставщик является квалифицированным поставщиком и что поставщик поддерживает обход сервера-посредника.</span><span class="sxs-lookup"><span data-stu-id="009e1-106">If the peer you connect to is the SBC of a SIP trunking provider, make sure that the provider is a qualified provider and that the provider supports media bypass.</span></span> <span data-ttu-id="009e1-107">Например, многие поставщики распределения каналов SIP допускают прием устройством SBC трафика только от сервера-посредника.</span><span class="sxs-lookup"><span data-stu-id="009e1-107">For example, many SIP trunking providers will only allow their SBC to receive traffic from the Mediation Server.</span></span> <span data-ttu-id="009e1-108">В этом случае обход не должен быть разрешен для данной магистрали.</span><span class="sxs-lookup"><span data-stu-id="009e1-108">If so, then bypass must not be enabled for the trunk in question.</span></span> <span data-ttu-id="009e1-109">Кроме того, вы не можете включить обход сервера-посредника, если организация не предоставляет IP-адреса внутренней сети поставщику распределения каналов SIP.</span><span class="sxs-lookup"><span data-stu-id="009e1-109">Also, you cannot enable media bypass unless your organization reveals its internal network IP addresses to the SIP trunking provider.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="009e1-110">Функция обхода сервера-посредника взаимодействует не со всеми шлюзами ТСОП, IP-УАТС и SBC.</span><span class="sxs-lookup"><span data-stu-id="009e1-110">Media bypass will not interoperate with every PSTN gateway, IP-PBX, and SBC.</span></span> <span data-ttu-id="009e1-111">Корпорация Майкрософт протестировала ряд шлюзов ТСОП и SBC с сертифицированными партнерами и выполнила некоторые тесты с IP-УАТС компании Cisco.</span><span class="sxs-lookup"><span data-stu-id="009e1-111">Microsoft has tested a set of PSTN gateways and SBCs with certified partners and has done some testing with Cisco IP-PBXs.</span></span> <span data-ttu-id="009e1-112">Обход сервера-посредника поддерживается только для продуктов и версий, перечисленных в общедоступной программе для взаимодействия с единой системой обмена сообщениями — Lync Server по адресу <A href="https://go.microsoft.com/fwlink/p/?linkid=214406">https://go.microsoft.com/fwlink/p/?linkId=214406</A> .</span><span class="sxs-lookup"><span data-stu-id="009e1-112">Media bypass is supported only with products and versions listed on Unified Communications Open Interoperability Program – Lync Server at <A href="https://go.microsoft.com/fwlink/p/?linkid=214406">https://go.microsoft.com/fwlink/p/?linkId=214406</A>.</span></span>



</div>

<span data-ttu-id="009e1-113">В этом разделе приведено описание процесса обхода сервера-посредника для уменьшения объема обработки, которую должен выполнять сервер-посредник.</span><span class="sxs-lookup"><span data-stu-id="009e1-113">This section describes how to enable media bypass to reduce the processing required of the Mediation Server.</span></span> <span data-ttu-id="009e1-114">Перед включением обхода сервера мультимедиа убедитесь, что ваша среда соответствует условиям, необходимым для поддержки обхода сервера мультимедиа, как описано в статье Планирование [обхода сервера мультимедиа в Lync Server 2013](lync-server-2013-planning-for-media-bypass.md) в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="009e1-114">Before you enable media bypass, make sure that your environment meets the conditions required to support media bypass, as described in [Planning for media bypass in Lync Server 2013](lync-server-2013-planning-for-media-bypass.md) in the Planning documentation.</span></span> <span data-ttu-id="009e1-115">Кроме того, убедитесь, что вы использовали сведения о [планировании обхода сервера-посредника в Lync Server 2013](lync-server-2013-planning-for-media-bypass.md) , чтобы решить, следует ли включать глобальные параметры обхода сервера-посредника для постоянного обхода сервера-посредника или для использования сведений о сайте и регионе при определении необходимости обхода сервера-посредника.</span><span class="sxs-lookup"><span data-stu-id="009e1-115">Also make sure that you used the information in [Planning for media bypass in Lync Server 2013](lync-server-2013-planning-for-media-bypass.md) to decide whether to enable media bypass global settings to always bypass the Mediation Server or to use site and region information when determining whether to bypass the Mediation Server.</span></span>

<span data-ttu-id="009e1-p104">Если вы уже дополнительно настроили контроль допуска звонков (CAC), другую расширенную функцию Enterprise Voice, обратите внимание на то, что резервирование полосы пропускания, выполняемое функцией контроля допуска звонков, не распространяется на какие-либо вызовы, для которых используется обход сервера-посредника. Сначала выполняется проверка того, используется ли обход сервера-посредника, и, если обход используется, функция контроля допуска звонков не применяется для вызовов; только если проверка обхода сервера-посредника возвращает отказ, выполняется проверка на использование функции контроля допуска звонков. Эти две функции являются взаимоисключающими для любого отдельного вызова, передаваемого на ТСОП. Это логично, поскольку обход сервера-посредника предполагает, что полоса пропускания между конечными точками, участвующими в вызове, не ограничена; обход сервера-посредника не выполняется при наличии ограничений. В результате при вызове ТСОП возможно возникновение одной их следующих ситуаций: а) выполняется обход сервера-посредника, а функция контроля допуска звонков не резервирует полосу пропускания для вызова; или б) функция контроля допуска звонков применяет резервирование полосы пропускания, а сервер-посредником, которые участвует в вызове, выполняет обработку.</span><span class="sxs-lookup"><span data-stu-id="009e1-p104">If you have already optionally configured call admission control (CAC), another advanced Enterprise Voice feature, note that the bandwidth reservation performed by call admission control does not apply to any calls for which media bypass is employed. The verification of whether to employ media bypass is performed first, and if media bypass is employed, call admission control is not used for the call; only if the media bypass check fails is the check performed for call admission control. The two features are thus mutually exclusive for any particular call that is routed to the PSTN. This is the logic because media bypass assumes that bandwidth constraints do not exist between the media endpoints on a call; media bypass cannot be performed on links with restricted bandwidth. As a result, one of the following will apply to a PSTN call: a) media bypasses the Mediation Server, and call admission control does not reserve bandwidth for the call; or b) call admission control applies bandwidth reservation to the call, and media is processed by the Mediation Server involved in the call.</span></span>

<div>

## <a name="next-steps-enable-media-bypass-on-the-trunk-connection"></a><span data-ttu-id="009e1-121">Дальнейшие действия: включение обхода сервера-посредника на магистральном соединении</span><span class="sxs-lookup"><span data-stu-id="009e1-121">Next Steps: Enable Media Bypass on the Trunk Connection</span></span>

<span data-ttu-id="009e1-122">После настройки начальных параметров подключения по протоколу PSTN (абонентские группы, политики голосовой связи, записи использования PSTN, маршруты исходящих вызовов и правила преобразования) начинайте процесс включения обхода сервера-посредника, выполнив действия, описанные в разделе [Настройка магистрали с обходом сервера-посредника в Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md).</span><span class="sxs-lookup"><span data-stu-id="009e1-122">After configuring initial settings for PSTN connectivity (dial plans, voice policies, PSTN usage records, outbound call routes, and translation rules), begin the process of enabling media bypass by using the steps in [Configure a trunk with media bypass in Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="009e1-123">См. также</span><span class="sxs-lookup"><span data-stu-id="009e1-123">See Also</span></span>


[<span data-ttu-id="009e1-124">Настройка магистрали с обходом сервера мультимедиа в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="009e1-124">Configure a trunk with media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-with-media-bypass.md)  
[<span data-ttu-id="009e1-125">Настройка обхода сервера-посредника в Lync Server 2013 для постоянного обхода сервера-посредника</span><span class="sxs-lookup"><span data-stu-id="009e1-125">Configure media bypass in Lync Server 2013 to always bypass the Mediation Server</span></span>](lync-server-2013-configure-media-bypass-to-always-bypass-the-mediation-server.md)  
[<span data-ttu-id="009e1-126">Настройка глобальных параметров обхода сервера-посредника в Lync Server 2013 для использования сведений о сайте и регионе</span><span class="sxs-lookup"><span data-stu-id="009e1-126">Configure media bypass global settings in Lync Server 2013 to use site and region information</span></span>](lync-server-2013-configure-media-bypass-global-settings-to-use-site-and-region-information.md)  


[<span data-ttu-id="009e1-127">Глобальные параметры обхода мультимедиа в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="009e1-127">Global media bypass options in Lync Server 2013</span></span>](lync-server-2013-global-media-bypass-options.md)  


[<span data-ttu-id="009e1-128">Планирование обхода сервера мультимедиа в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="009e1-128">Planning for media bypass in Lync Server 2013</span></span>](lync-server-2013-planning-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

