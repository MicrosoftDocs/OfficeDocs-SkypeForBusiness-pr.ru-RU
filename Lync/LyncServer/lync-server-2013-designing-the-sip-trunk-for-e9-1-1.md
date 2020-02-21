---
title: 'Lync Server 2013: Разработка магистрали SIP для E9 – 1 — 1'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Designing the SIP trunk for E9-1-1
ms:assetid: 4f93b974-b460-45c7-a4a8-6f38e34840f5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398323(v=OCS.15)
ms:contentKeyID: 48184096
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6c4191ed20497b4136b4e836da112054bef5a446
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42204385"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="designing-the-sip-trunk-for-e9-1-1-in-lync-server-2013"></a><span data-ttu-id="75b42-102">Проектирование магистрали SIP для E9 – 1 – 1 в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="75b42-102">Designing the SIP trunk for E9-1-1 in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="75b42-103">_**Последнее изменение темы:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="75b42-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="75b42-104">Lync Server использует магистральные линии SIP для подключения экстренных вызовов к поставщику услуг E9 – 1 – 1.</span><span class="sxs-lookup"><span data-stu-id="75b42-104">Lync Server uses SIP trunks to connect an emergency call to the E9-1-1 service provider.</span></span> <span data-ttu-id="75b42-105">Вы можете настроить магистральные магистрали SIP для E9-1-1 на одном центральном сайте, на нескольких центральных сайтах или на каждом сайте филиала.</span><span class="sxs-lookup"><span data-stu-id="75b42-105">You can set up emergency service SIP trunks for E9-1-1 at one central site, at multiple central sites, or at each branch site.</span></span> <span data-ttu-id="75b42-106">Тем не менее, если канал WAN между сайтом вызывающего абонента и сайтом, на котором размещается магистраль SIP службы аварийной службы, недоступен, то вызов, размещенный пользователем на отключенном сайте, должен иметь специальную запись об использовании телефона в политике голосовой связи пользователя, которая будет направлять вызов в ECRC через шлюз телефонной сети общего пользования (PSTN).</span><span class="sxs-lookup"><span data-stu-id="75b42-106">However, if the WAN link between the caller’s site and the site that hosts the emergency service SIP trunk is unavailable, then a call placed by a user at the disconnected site will need a special phone usage record in the user’s voice policy that will route the call to the ECRC through the local public switched telephone network (PSTN) gateway.</span></span> <span data-ttu-id="75b42-107">То же самое справедливо, если действуют одновременные пределы вызовов контроля допуска звонков.</span><span class="sxs-lookup"><span data-stu-id="75b42-107">The same is true if call admission control concurrent call limits are in effect.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="75b42-108">Существует два способа реализации магистрали SIP в среде Lync Server.</span><span class="sxs-lookup"><span data-stu-id="75b42-108">There are two ways to implement a SIP trunk in a Lync Server environment:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="75b42-109">Используйте многосетевые серверы-посредники, использующие общедоступные интерфейсы с общедоступными маршрутами, для взаимодействия с поставщиком магистрали SIP.</span><span class="sxs-lookup"><span data-stu-id="75b42-109">Use multihomed Mediation Servers that use their outward-facing publicly-routed interfaces to communicate with the SIP trunk provider.</span></span></P>
> <LI>
> <P><span data-ttu-id="75b42-110">Используйте локальный пограничный контроллер сеансов (SBC) для обеспечения безопасной точки точки разграничения между серверами-посредниками и службами поставщика магистрали SIP.</span><span class="sxs-lookup"><span data-stu-id="75b42-110">Use an on-premises Session Border Controller (SBC) to provide a secure demarcation point between the Mediation Servers and the SIP trunk provider’s services.</span></span></P></LI></UL><span data-ttu-id="75b42-111">Если вы выбираете последний способ, убедитесь, что выбранная вами модель была сертифицирована и поддерживает передачу данных о местонахождения в виде объекта местонахождения, использующего формат данных о присутствии (PIDF-LO), в составе SIP INVITE.</span><span class="sxs-lookup"><span data-stu-id="75b42-111">If you choose the latter method, be sure that the SBC make and model that you choose has been certified and supports passing Presence Information Data Format Location Object (PIDF-LO) location data as part of its SIP INVITE.</span></span> <span data-ttu-id="75b42-112">В противном случае звонки будут приходить поставщику услуг экстренных служб без информации о местоположении.</span><span class="sxs-lookup"><span data-stu-id="75b42-112">Otherwise, the calls will arrive at the emergency services service provider stripped of their location information.</span></span> <span data-ttu-id="75b42-113">Сведения о сертификате, сертифицированном для SBCs, приведены в <A href="https://go.microsoft.com/fwlink/p/?linkid=248425">https://go.microsoft.com/fwlink/p/?LinkId=248425</A>разделе "инфраструктура, квалифицированная для Microsoft Lync".</span><span class="sxs-lookup"><span data-stu-id="75b42-113">For details about certified SBCs, see "Infrastructure Qualified for Microsoft Lync" at <A href="https://go.microsoft.com/fwlink/p/?linkid=248425">https://go.microsoft.com/fwlink/p/?LinkId=248425</A>.</span></span><BR><span data-ttu-id="75b42-114">В целях избыточности поставщики услуг E9-1-1 предоставляют вам доступ к паре пограничных контроллеров сеансов.</span><span class="sxs-lookup"><span data-stu-id="75b42-114">E9-1-1 service providers supply you with access to a pair of SBCs for redundancy.</span></span> <span data-ttu-id="75b42-115">Необходимо принять несколько решений относительно топологии сервера-посредника и конфигурации маршрутизации вызовов.</span><span class="sxs-lookup"><span data-stu-id="75b42-115">You need to make several decisions regarding the Mediation Server topology and call routing configuration.</span></span> <span data-ttu-id="75b42-116">Будете ли вы рассматривать оба пограничных контроллера сеансов в качестве равноправных кэширующих узлов и использовать метод маршрутизации с циклическим перебором для звонков между ними или назначите один пограничный контроллер сеансов в качестве основного, а другой — в качестве дополнительного?</span><span class="sxs-lookup"><span data-stu-id="75b42-116">Will you treat both SBCs as equal peers and use round-robin routing for calls between them, or will you designate one SBC as primary and the other as secondary?</span></span>



</div>

<span data-ttu-id="75b42-117">Сведения о развертывании магистральной линии SIP в Lync Server приведены [в статье как реализовать магистраль SIP в Lync server 2013?](lync-server-2013-how-do-i-implement-sip-trunking.md).</span><span class="sxs-lookup"><span data-stu-id="75b42-117">For details about deploying a SIP trunk in Lync Server, see [How do I implement SIP trunking in Lync Server 2013?](lync-server-2013-how-do-i-implement-sip-trunking.md).</span></span> <span data-ttu-id="75b42-118">приведенные ниже вопросы помогут вам принять решение о способе развертывания магистралей SIP для E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="75b42-118">The following questions will help you decide how to deploy the SIP trunks for E9-1-1.</span></span>

  - <span data-ttu-id="75b42-119">**Следует ли развернуть магистраль SIP на базе выделенного или общего подключения к Интернету?**</span><span class="sxs-lookup"><span data-stu-id="75b42-119">**Should you deploy the SIP trunk over a dedicated leased or a shared internet connection?**</span></span>  
    <span data-ttu-id="75b42-p105">Для экстренных вызовов важно обеспечить постоянное подключение. Выделенная линия предоставляет соединение, на которое не будет влиять остальной трафик в сети, и позволяет реализовать качество обслуживания. Помните о том, что если при подключении к поставщикам услуг экстренных служб через общедоступное соединение с Интернетом вам требуется гарантировать конфиденциальность экстренных звонков, то требуется шифрование IPSec.</span><span class="sxs-lookup"><span data-stu-id="75b42-p105">It is important that emergency calls always connect. A dedicated line provides a connection that will not be preempted by other traffic on the network, and gives you the ability to implement Quality of Service (QoS). Remember that if you are connecting to emergency services service providers over the public Internet and you need to guarantee the confidentiality of emergency calls, IPSec encryption is required.</span></span>

<!-- end list -->

  - <span data-ttu-id="75b42-123">**Является ваше развертывание E9-1-1, предназначенное для отказоустойчивости?**</span><span class="sxs-lookup"><span data-stu-id="75b42-123">**Is your E9-1-1 deployment designed for disaster tolerance?**</span></span>  
    <span data-ttu-id="75b42-124">Поскольку это решение для экстренных ситуаций, устойчивость имеет важное значение.</span><span class="sxs-lookup"><span data-stu-id="75b42-124">Because this is an emergency solution, resiliency is important.</span></span> <span data-ttu-id="75b42-125">Разверните основной и дополнительный серверы-посредники и магистральные линии SIP в отказоустойчивых расположениях.</span><span class="sxs-lookup"><span data-stu-id="75b42-125">Deploy your primary and secondary Mediation Servers and SIP trunks in disaster tolerant locations.</span></span> <span data-ttu-id="75b42-126">Рекомендуется развертывать основной сервер-посредник ближе к пользователям, которые он поддерживает, и маршрутизировать вызовы отработки отказа через сервер-посредник, расположенный в другом географическом расположении.</span><span class="sxs-lookup"><span data-stu-id="75b42-126">It is a good idea to deploy your primary Mediation Server closest to the users that it is supporting, and route failover calls through the secondary Mediation Server (located in a different geographic location).</span></span>

<!-- end list -->

  - <span data-ttu-id="75b42-127">**Следует ли вам развернуть отдельную магистраль SIP для каждого филиала?**</span><span class="sxs-lookup"><span data-stu-id="75b42-127">**Should you deploy a separate SIP trunk for each branch office?**</span></span>  
    <span data-ttu-id="75b42-128">Lync Server предоставляет несколько стратегий обработки устойчивости голосовой связи в филиалах, в том числе: наличие отказоустойчивых сетей данных, развертывание магистрали SIP в каждой ветви или принудительная передача вызовов на локальный шлюз во время простоя.</span><span class="sxs-lookup"><span data-stu-id="75b42-128">Lync Server provides several strategies for handling voice resiliency in branch offices, including: having resilient data networks, deploying a SIP trunk at each branch, or pushing calls out to the local gateway during outages.</span></span> <span data-ttu-id="75b42-129">Дополнительные сведения см. [магистральные МАГИСТРАЛИ SIP для сайта филиала в Lync Server 2013](lync-server-2013-branch-site-sip-trunking.md).</span><span class="sxs-lookup"><span data-stu-id="75b42-129">For details, see [Branch site SIP trunking in Lync Server 2013](lync-server-2013-branch-site-sip-trunking.md).</span></span>

<!-- end list -->

  - <span data-ttu-id="75b42-130">**Включается ли контроль допуска звонков?**</span><span class="sxs-lookup"><span data-stu-id="75b42-130">**Is call admission control (CAC) enabled?**</span></span>  
    <span data-ttu-id="75b42-131">Lync Server не обрабатывает экстренные вызовы иначе, чем обычный вызов.</span><span class="sxs-lookup"><span data-stu-id="75b42-131">Lync Server does not handle emergency calls any differently than an ordinary call.</span></span> <span data-ttu-id="75b42-132">По этой причине управление пропускной способностью или контроль допуска звонков (CAC) может негативно повлиять на конфигурацию E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="75b42-132">For this reason, bandwidth management, or call admission control (CAC), can have a negative impact on an E9-1-1 configuration.</span></span> <span data-ttu-id="75b42-133">Экстренные вызовы блокируются или направляются на местный шлюз PSTN, если включена функция CAC, и превышено заданное ограничение на канале маршрутизации экстренных вызовов.</span><span class="sxs-lookup"><span data-stu-id="75b42-133">Emergency calls will be blocked or routed to the local PSTN gateway if a CAC is enabled and the configured limit is exceeded on a link where emergency calls are being routed.</span></span> <span data-ttu-id="75b42-134">Как было указано ранее в этой статье, такие звонки не будут содержать данные о расположении и должны быть перенаправлены в ECRC вручную.</span><span class="sxs-lookup"><span data-stu-id="75b42-134">As indicated earlier in this topic, such calls will not have location data and must be manually routed to the ECRC.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

