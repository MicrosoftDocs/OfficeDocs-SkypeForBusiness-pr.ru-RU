---
title: Сайты Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Sites
ms:assetid: 022cb6dd-37e2-4882-a53e-5ddfdbc6f53a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398076(v=OCS.15)
ms:contentKeyID: 48183233
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e1843ac4256e71723abf59fa272155ced2010e72
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849655"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="lync-server-sites-for-lync-server-2013"></a><span data-ttu-id="77b6f-102">Сайты Lync Server для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="77b6f-102">Lync Server sites for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="77b6f-103">_**Тема последнего изменения:** 2012-10-16_</span><span class="sxs-lookup"><span data-stu-id="77b6f-103">_**Topic Last Modified:** 2012-10-16_</span></span>

<span data-ttu-id="77b6f-104">В Lync Server вы определяете *сайты* в сети, которые содержат компоненты Lync Server.</span><span class="sxs-lookup"><span data-stu-id="77b6f-104">In Lync Server, you define *sites* on your network that contain Lync Server components.</span></span> <span data-ttu-id="77b6f-105">A site is a set of computers that is well-connected by a high-speed, low-latency network, such as a single local area network (LAN) or two networks connected by a high-speed fiber optic network.</span><span class="sxs-lookup"><span data-stu-id="77b6f-105">A site is a set of computers that is well-connected by a high-speed, low-latency network, such as a single local area network (LAN) or two networks connected by a high-speed fiber optic network.</span></span> <span data-ttu-id="77b6f-106">Обратите внимание, что сайты Lync Server — это отдельная концепция сайтов доменных служб Active Directory и серверов Microsoft Exchange.</span><span class="sxs-lookup"><span data-stu-id="77b6f-106">Note that Lync Server sites are a separate concept from Active Directory Domain Services sites and Microsoft Exchange Server sites.</span></span> <span data-ttu-id="77b6f-107">Сайты вашего сервера Lync Server не должны соответствовать вашим сайтам службы каталогов Active Directory.</span><span class="sxs-lookup"><span data-stu-id="77b6f-107">Your Lync Server sites do not need to correspond to your Active Directory sites.</span></span>

<div>

## <a name="site-types"></a><span data-ttu-id="77b6f-108">Типы сайтов</span><span class="sxs-lookup"><span data-stu-id="77b6f-108">Site Types</span></span>

<span data-ttu-id="77b6f-109">Каждый сайт — это *центральный сайт*, который содержит по крайней мере один пул переднего плана либо сервер Standard Edition либо *сайт филиала*.</span><span class="sxs-lookup"><span data-stu-id="77b6f-109">Each site is either a *central site*, which contains at least one Front End pool or a Standard Edition server, or a *branch site*.</span></span> <span data-ttu-id="77b6f-110">Каждый сайт филиала связан только с одним центральным сайтом, а пользователи на сайте филиала получают большинство функций сервера Lync Server с серверов на соответствующем центральном сайте.</span><span class="sxs-lookup"><span data-stu-id="77b6f-110">Each branch site is associated with exactly one central site, and the users at the branch site get most of their Lync Server functionality from the servers at the associated central site.</span></span>

<span data-ttu-id="77b6f-111">Каждый сайт филиала имеет один из следующих вариантов:</span><span class="sxs-lookup"><span data-stu-id="77b6f-111">Each branch site contains one of the following:</span></span>

  - <span data-ttu-id="77b6f-112">Работающее *устройство филиала (СБА)*, которое является отраслевым стандартным блейд-сервером с помощью регистратора Lync Server и сервера-посредника под управлением Windows Server.</span><span class="sxs-lookup"><span data-stu-id="77b6f-112">A *Survivable Branch Appliance (SBA)*, which is an industry-standard blade server with a Lync Server Registrar and a Mediation Server running on Windows Server.</span></span> <span data-ttu-id="77b6f-113">Бесперебойно работающее устройство филиала также включает коммутируемый коммутируемой телефонной сети (PSTN).</span><span class="sxs-lookup"><span data-stu-id="77b6f-113">The Survivable Branch Appliance also contains a public switched telephone network (PSTN) gateway.</span></span> <span data-ttu-id="77b6f-114">Бесперебойно работающее устройство филиалов предназначено для сайтов филиалов, имеющих от 25 до 1000 пользователей.</span><span class="sxs-lookup"><span data-stu-id="77b6f-114">The Survivable Branch Appliance is designed for branch sites with between 25 and 1000 users.</span></span>

  - <span data-ttu-id="77b6f-115">Бесперебойно используемый *сервер филиала (SBS)*— сервер под управлением Windows Server, соответствующий указанным требованиям к оборудованию, на котором установлено программное обеспечение сервера регистратора Lync Server и сервер-посредника.</span><span class="sxs-lookup"><span data-stu-id="77b6f-115">A *Survivable Branch Server (SBS)*, which is a server running Windows Server that meets specified hardware requirements, and that has Lync Server Registrar and Mediation Server software installed on it.</span></span> <span data-ttu-id="77b6f-116">Он должен подключаться через ТСОП-шлюз или SIP-магистраль к телефонному оператору.</span><span class="sxs-lookup"><span data-stu-id="77b6f-116">It must connect to either a PSTN gateway or a SIP trunk to a telephone service provider.</span></span> <span data-ttu-id="77b6f-117">Бесперебойный сервер филиалов разработан для сайтов филиалов с помощью пользователей 1000 и 5000.</span><span class="sxs-lookup"><span data-stu-id="77b6f-117">The Survivable Branch Server is designed for branch sites with between 1000 and 5000 users.</span></span>

  - <span data-ttu-id="77b6f-118">Шлюз PSTN и, при необходимости, *сервер-посредник*.</span><span class="sxs-lookup"><span data-stu-id="77b6f-118">A PSTN gateway, and, optionally, a *Mediation Server*.</span></span> <span data-ttu-id="77b6f-119">Подробнее об этой и других ролях сервера можно узнать [в разделе роли сервера в Lync server 2013](lync-server-2013-server-roles.md).</span><span class="sxs-lookup"><span data-stu-id="77b6f-119">For details on this and other server roles, see [Server roles in Lync Server 2013](lync-server-2013-server-roles.md).</span></span>

<span data-ttu-id="77b6f-120">Офис подразделения с ссылкой на глобальную глобальную сеть (WAN) может использовать третий вариант — шлюз PSTN и, при необходимости, сервер-посредник.</span><span class="sxs-lookup"><span data-stu-id="77b6f-120">A branch office with a resilient wide area network (WAN) link to a central site can use the third option—a PSTN gateway, and, optionally, a Mediation Server.</span></span> <span data-ttu-id="77b6f-121">Сайты филиалов с менее гибкими связями должны использовать бесперебойно работающее устройство филиалов или отказоустойчивый сервер филиалов, который обеспечивает устойчивость во время сбоев в глобальной сети.</span><span class="sxs-lookup"><span data-stu-id="77b6f-121">Branch office sites with less-resilient links should use a Survivable Branch Appliance or Survivable Branch Server, which provide resiliency in times of wide-area network failures.</span></span> <span data-ttu-id="77b6f-122">Например, на сайте с бесперебойно работающим управляющим устройством или развернутым филиалом пользователи по-прежнему могут совершать и принимать вызовы голосовой связи, если глобальная сеть, соединяющая сайт филиала с центральным сайтом, не работает.</span><span class="sxs-lookup"><span data-stu-id="77b6f-122">For example, in a site with a Survivable Branch Appliance or Survivable Branch Server deployed, users can still make and receive Enterprise Voice calls if the WAN connecting the branch site to the central site is down.</span></span> <span data-ttu-id="77b6f-123">Подробные сведения о работающем устройстве филиала, работающем сервере филиалов и устойчивости можно найти [в разделе Планирование устойчивости корпоративной голосовой связи в Lync Server 2013](lync-server-2013-planning-for-enterprise-voice-resiliency.md) в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="77b6f-123">For details about the Survivable Branch Appliance, Survivable Branch Server, and resiliency, see [Planning for Enterprise Voice resiliency in Lync Server 2013](lync-server-2013-planning-for-enterprise-voice-resiliency.md) in the Planning documentation.</span></span>

</div>

<div>

## <a name="site-topologies"></a><span data-ttu-id="77b6f-124">Топологии сайтов</span><span class="sxs-lookup"><span data-stu-id="77b6f-124">Site Topologies</span></span>

<span data-ttu-id="77b6f-125">Развертывание должно включать хотя бы один центральный сайт и может включать нуль для многих сайтов филиалов.</span><span class="sxs-lookup"><span data-stu-id="77b6f-125">Your deployment must include at least one central site, and can include zero to many branch sites.</span></span> <span data-ttu-id="77b6f-126">Каждый сайт филиалов связан с одним центральным сайтом.</span><span class="sxs-lookup"><span data-stu-id="77b6f-126">Each branch site is affiliated with one central site.</span></span> <span data-ttu-id="77b6f-127">Центральный сайт предоставляет службы Lync Server на сайт филиала, не размещенный локально на сайте филиала, например присутствие и конференц-связь.</span><span class="sxs-lookup"><span data-stu-id="77b6f-127">The central site provides the Lync Server services to the branch site that are not hosted locally at the branch site, such as presence and conferencing.</span></span>

<span data-ttu-id="77b6f-128">Если у вас несколько сайтов, вы можете объединить пулы переднего плана на разных сайтах, чтобы включить возможности аварийного восстановления.</span><span class="sxs-lookup"><span data-stu-id="77b6f-128">If you have multiple sites, you can pair together the Front End pools at different sites to enable disaster recovery abilities.</span></span> <span data-ttu-id="77b6f-129">Подробные сведения можно найти [в разделе Поддержка высокого уровня доступности и аварийного восстановления в Lync Server 2013](lync-server-2013-high-availability-and-disaster-recovery-support.md).</span><span class="sxs-lookup"><span data-stu-id="77b6f-129">For details, see [High availability and disaster recovery support in Lync Server 2013](lync-server-2013-high-availability-and-disaster-recovery-support.md).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="77b6f-130">См. также</span><span class="sxs-lookup"><span data-stu-id="77b6f-130">See Also</span></span>


[<span data-ttu-id="77b6f-131">Роли сервера в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="77b6f-131">Server roles in Lync Server 2013</span></span>](lync-server-2013-server-roles.md)  
[<span data-ttu-id="77b6f-132">Поддержка высокой доступности и аварийного восстановления в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="77b6f-132">High availability and disaster recovery support in Lync Server 2013</span></span>](lync-server-2013-high-availability-and-disaster-recovery-support.md)  


[<span data-ttu-id="77b6f-133">Планирование устойчивости корпоративной голосовой связи в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="77b6f-133">Planning for Enterprise Voice resiliency in Lync Server 2013</span></span>](lync-server-2013-planning-for-enterprise-voice-resiliency.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

