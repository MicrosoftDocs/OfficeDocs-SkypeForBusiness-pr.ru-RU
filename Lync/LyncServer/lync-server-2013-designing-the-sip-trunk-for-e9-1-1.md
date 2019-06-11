---
title: 'Lync Server 2013: Разработка магистральной магистрали SIP для E9-1-1'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Designing the SIP trunk for E9-1-1
ms:assetid: 4f93b974-b460-45c7-a4a8-6f38e34840f5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398323(v=OCS.15)
ms:contentKeyID: 48184096
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2bee3985efd3510b62bfe43b3aa5742f63679093
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834462"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="designing-the-sip-trunk-for-e9-1-1-in-lync-server-2013"></a><span data-ttu-id="43ce1-102">Проектирование магистральной магистрали SIP для E9-1-1 в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="43ce1-102">Designing the SIP trunk for E9-1-1 in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="43ce1-103">_**Тема последнего изменения:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="43ce1-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="43ce1-104">Lync Server использует магистральные магистрали SIP для связи с экстренным звонком с поставщиком услуг E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="43ce1-104">Lync Server uses SIP trunks to connect an emergency call to the E9-1-1 service provider.</span></span> <span data-ttu-id="43ce1-105">Вы можете установить магистрали SIP экстренной службы для E9-1-1 на одном центральном сайте, на нескольких центральных сайтах или на каждом сайте филиалов.</span><span class="sxs-lookup"><span data-stu-id="43ce1-105">You can set up emergency service SIP trunks for E9-1-1 at one central site, at multiple central sites, or at each branch site.</span></span> <span data-ttu-id="43ce1-106">Но в случае недоступности WAN-канала между сайтом вызывающего абонента и сайтом, где размещается магистраль SIP экстренной службы, вызову пользователя на разъединенном сайте потребуется наличие в политике голосовой связи телефонной записи специального значения, которая перенаправит вызов в ECRC через локальный шлюз телефонной сети общего пользования (ТСОП).</span><span class="sxs-lookup"><span data-stu-id="43ce1-106">However, if the WAN link between the caller’s site and the site that hosts the emergency service SIP trunk is unavailable, then a call placed by a user at the disconnected site will need a special phone usage record in the user’s voice policy that will route the call to the ECRC through the local public switched telephone network (PSTN) gateway.</span></span> <span data-ttu-id="43ce1-107">Это также относится к ситуации, когда для вызовов действуют совместные ограничения функции контроля допуска звонков.</span><span class="sxs-lookup"><span data-stu-id="43ce1-107">The same is true if call admission control concurrent call limits are in effect.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="43ce1-108">Существует два способа реализации магистральной магистрали SIP в среде Lync Server.</span><span class="sxs-lookup"><span data-stu-id="43ce1-108">There are two ways to implement a SIP trunk in a Lync Server environment:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="43ce1-109">Используйте серверы многосетевого посредника, которые используют одноранговые интерфейсы с общедоступными маршрутами для связи с провайдером магистрали SIP.</span><span class="sxs-lookup"><span data-stu-id="43ce1-109">Use multihomed Mediation Servers that use their outward-facing publicly-routed interfaces to communicate with the SIP trunk provider.</span></span></P>
> <LI>
> <P><span data-ttu-id="43ce1-110">Используйте локальный контроллер внешней связи (SBC) для обеспечения безопасной точки демаркатион между серверами исправлений и службами провайдера магистральной сети SIP.</span><span class="sxs-lookup"><span data-stu-id="43ce1-110">Use an on-premises Session Border Controller (SBC) to provide a secure demarcation point between the Mediation Servers and the SIP trunk provider’s services.</span></span></P></LI></UL><span data-ttu-id="43ce1-111">Если вы выбираете последний способ, убедитесь, что образец SBS и выбранная вами модель были сертифицирована и поддерживали передачу данных расположения в виде PIDF-LO (объекта расположения, использующий формат данных о присутствии), в составе SIP INVITE.</span><span class="sxs-lookup"><span data-stu-id="43ce1-111">If you choose the latter method, be sure that the SBC make and model that you choose has been certified and supports passing Presence Information Data Format Location Object (PIDF-LO) location data as part of its SIP INVITE.</span></span> <span data-ttu-id="43ce1-112">В противном случае вызовы будут приходить поставщику услуг экстренных служб без информации о расположении.</span><span class="sxs-lookup"><span data-stu-id="43ce1-112">Otherwise, the calls will arrive at the emergency services service provider stripped of their location information.</span></span> <span data-ttu-id="43ce1-113">Подробные сведения о сертификате SBCs можно найти в <A href="http://go.microsoft.com/fwlink/p/?linkid=248425">http://go.microsoft.com/fwlink/p/?LinkId=248425</A>разделе "инфраструктура, определенная для Microsoft Lync".</span><span class="sxs-lookup"><span data-stu-id="43ce1-113">For details about certified SBCs, see "Infrastructure Qualified for Microsoft Lync" at <A href="http://go.microsoft.com/fwlink/p/?linkid=248425">http://go.microsoft.com/fwlink/p/?LinkId=248425</A>.</span></span><BR><span data-ttu-id="43ce1-114">Для подстраховки поставщики услуг E9-1-1 предоставляют доступ к паре пограничных контроллеров сеансов.</span><span class="sxs-lookup"><span data-stu-id="43ce1-114">E9-1-1 service providers supply you with access to a pair of SBCs for redundancy.</span></span> <span data-ttu-id="43ce1-115">Вам необходимо принять несколько решений относительно топологии сервера «исправление» и настройки маршрутизации звонков.</span><span class="sxs-lookup"><span data-stu-id="43ce1-115">You need to make several decisions regarding the Mediation Server topology and call routing configuration.</span></span> <span data-ttu-id="43ce1-116">Будете ли вы рассматривать оба пограничных контроллера SBC в качестве равноправных одноранговых узлов сети и применять метод маршрутизации с циклическим перебором для звонков между ними или же назначите один пограничный контроллер SBC в качестве основного, а другой — в качестве дополнительного?</span><span class="sxs-lookup"><span data-stu-id="43ce1-116">Will you treat both SBCs as equal peers and use round-robin routing for calls between them, or will you designate one SBC as primary and the other as secondary?</span></span>



</div>

<span data-ttu-id="43ce1-117">Дополнительные сведения о развертывании магистральной магистрали SIP в Lync Server можно найти [в статье реализация МАГИСТРАЛИ SIP в Lync server 2013?](lync-server-2013-how-do-i-implement-sip-trunking.md).</span><span class="sxs-lookup"><span data-stu-id="43ce1-117">For details about deploying a SIP trunk in Lync Server, see [How do I implement SIP trunking in Lync Server 2013?](lync-server-2013-how-do-i-implement-sip-trunking.md).</span></span> <span data-ttu-id="43ce1-118">Следующие вопросы помогут вам принять решение о способе развертывания магистралей SIP для E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="43ce1-118">The following questions will help you decide how to deploy the SIP trunks for E9-1-1.</span></span>

  - <span data-ttu-id="43ce1-119">**Следует ли развернуть магистраль SIP на базе выделенного или общего подключения к Интернету?**</span><span class="sxs-lookup"><span data-stu-id="43ce1-119">**Should you deploy the SIP trunk over a dedicated leased or a shared internet connection?**</span></span>  
    <span data-ttu-id="43ce1-p105">Для экстренных вызовов важно обеспечить постоянное подключение. Выделенная линия предоставляет соединение, на которое не будет влиять остальной трафик в сети, и позволяет реализовать качество обслуживания. Помните о том, что если при подключении к поставщикам услуг экстренных служб через общедоступное соединение с Интернетом требуется гарантировать конфиденциальность экстренных звонков, то требуется шифрование IPSec.</span><span class="sxs-lookup"><span data-stu-id="43ce1-p105">It is important that emergency calls always connect. A dedicated line provides a connection that will not be preempted by other traffic on the network, and gives you the ability to implement Quality of Service (QoS). Remember that if you are connecting to emergency services service providers over the public Internet and you need to guarantee the confidentiality of emergency calls, IPSec encryption is required.</span></span>

<!-- end list -->

  - <span data-ttu-id="43ce1-123">**Является ли ваша E9 развертывание более 1-1, разработанной для погрешности в сбоях?**</span><span class="sxs-lookup"><span data-stu-id="43ce1-123">**Is your E9-1-1 deployment designed for disaster tolerance?**</span></span>  
    <span data-ttu-id="43ce1-124">Поскольку это решение для экстренных ситуаций, устойчивость имеет важное значение.</span><span class="sxs-lookup"><span data-stu-id="43ce1-124">Because this is an emergency solution, resiliency is important.</span></span> <span data-ttu-id="43ce1-125">Развертывание основного и дополнительного серверов исправлений и магистральных каналов SIP в отказоустойчивом местоположении.</span><span class="sxs-lookup"><span data-stu-id="43ce1-125">Deploy your primary and secondary Mediation Servers and SIP trunks in disaster tolerant locations.</span></span> <span data-ttu-id="43ce1-126">Рекомендуется развертывать основной сервер-посредник ближе всего к пользователям, которые он поддерживает, и перенаправлять вызовы отработки отказа с помощью сервера-получателя (расположенного в другом географическом расположении).</span><span class="sxs-lookup"><span data-stu-id="43ce1-126">It is a good idea to deploy your primary Mediation Server closest to the users that it is supporting, and route failover calls through the secondary Mediation Server (located in a different geographic location).</span></span>

<!-- end list -->

  - <span data-ttu-id="43ce1-127">**Следует ли вам развернуть отдельную магистраль SIP для каждого филиала?**</span><span class="sxs-lookup"><span data-stu-id="43ce1-127">**Should you deploy a separate SIP trunk for each branch office?**</span></span>  
    <span data-ttu-id="43ce1-128">Lync Server предоставляет несколько стратегий для обработки устойчивости голоса в филиалах, в том числе для обеспечения устойчивых сетей обработки данных, развертывания магистральной магистрали SIP на каждой ветви или принудительного звонка к локальному шлюзу во время простоя.</span><span class="sxs-lookup"><span data-stu-id="43ce1-128">Lync Server provides several strategies for handling voice resiliency in branch offices, including: having resilient data networks, deploying a SIP trunk at each branch, or pushing calls out to the local gateway during outages.</span></span> <span data-ttu-id="43ce1-129">Дополнительные сведения можно найти [в разделе Настройка МАГИСТРАЛИ SIP на сайте филиала в Lync Server 2013](lync-server-2013-branch-site-sip-trunking.md).</span><span class="sxs-lookup"><span data-stu-id="43ce1-129">For details, see [Branch site SIP trunking in Lync Server 2013](lync-server-2013-branch-site-sip-trunking.md).</span></span>

<!-- end list -->

  - <span data-ttu-id="43ce1-130">**Включается ли контроль допуска звонков?**</span><span class="sxs-lookup"><span data-stu-id="43ce1-130">**Is call admission control (CAC) enabled?**</span></span>  
    <span data-ttu-id="43ce1-131">Lync Server не работает с вызовом экстренной помощи не так, как обычный звонок.</span><span class="sxs-lookup"><span data-stu-id="43ce1-131">Lync Server does not handle emergency calls any differently than an ordinary call.</span></span> <span data-ttu-id="43ce1-132">Поэтому управление пропускной способностью или контроль допуска звонков могут оказывать негативное влияние на конфигурацию E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="43ce1-132">For this reason, bandwidth management, or call admission control (CAC), can have a negative impact on an E9-1-1 configuration.</span></span> <span data-ttu-id="43ce1-133">При включенном контроле допуска звонков экстренные вызовы будут блокироваться или перенаправляться на локальный шлюз ТСОП, а на канале, куда перенаправляются экстренные звонки, будет превышен заданный предел.</span><span class="sxs-lookup"><span data-stu-id="43ce1-133">Emergency calls will be blocked or routed to the local PSTN gateway if a CAC is enabled and the configured limit is exceeded on a link where emergency calls are being routed.</span></span> <span data-ttu-id="43ce1-134">Как уже было указано выше в этом подразделе, такие звонки не будут содержать данных о расположении, и их следует вручную перенаправлять в ECRC.</span><span class="sxs-lookup"><span data-stu-id="43ce1-134">As indicated earlier in this topic, such calls will not have location data and must be manually routed to the ECRC.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

