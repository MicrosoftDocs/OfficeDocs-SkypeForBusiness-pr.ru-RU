---
title: Сайты Lync Server 2013
description: Сайты Lync Server 2013.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Sites
ms:assetid: 022cb6dd-37e2-4882-a53e-5ddfdbc6f53a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398076(v=OCS.15)
ms:contentKeyID: 48183233
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 59739c5a81fca1f1f3ab5c1b83a23f0be0a5ee2d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48558965"
---
# <a name="lync-server-sites-for-lync-server-2013"></a><span data-ttu-id="86098-103">Сайты Lync Server для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="86098-103">Lync Server sites for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="86098-104">_**Последнее изменение темы:** 2012-10-16_</span><span class="sxs-lookup"><span data-stu-id="86098-104">_**Topic Last Modified:** 2012-10-16_</span></span>

<span data-ttu-id="86098-105">В Lync Server вы определяете *сайты* в сети, содержащие компоненты Lync Server.</span><span class="sxs-lookup"><span data-stu-id="86098-105">In Lync Server, you define *sites* on your network that contain Lync Server components.</span></span> <span data-ttu-id="86098-106">Сайт — это набор компьютеров, соединенных с помощью сети с высокой пропускной способностью и низкой задержкой, например локальной сети, или две сети, соединенные с помощью высокоскоростного оптоволоконного канала.</span><span class="sxs-lookup"><span data-stu-id="86098-106">A site is a set of computers that is well-connected by a high-speed, low-latency network, such as a single local area network (LAN) or two networks connected by a high-speed fiber optic network.</span></span> <span data-ttu-id="86098-107">Обратите внимание, что сайты Lync Server — это отдельная концепция сайтов доменных служб Active Directory и сайтов Microsoft Exchange Server.</span><span class="sxs-lookup"><span data-stu-id="86098-107">Note that Lync Server sites are a separate concept from Active Directory Domain Services sites and Microsoft Exchange Server sites.</span></span> <span data-ttu-id="86098-108">Сайты Lync Server не обязаны соответствовать сайтам Active Directory.</span><span class="sxs-lookup"><span data-stu-id="86098-108">Your Lync Server sites do not need to correspond to your Active Directory sites.</span></span>

<div>

## <a name="site-types"></a><span data-ttu-id="86098-109">Типы сайтов</span><span class="sxs-lookup"><span data-stu-id="86098-109">Site Types</span></span>

<span data-ttu-id="86098-110">Каждый сайт является *центральным сайтом*, который содержит по крайней мере один интерфейсный пул или сервер Standard Edition или *сайт филиала*.</span><span class="sxs-lookup"><span data-stu-id="86098-110">Each site is either a *central site*, which contains at least one Front End pool or a Standard Edition server, or a *branch site*.</span></span> <span data-ttu-id="86098-111">Каждый сайт филиала связан с одним центральным сайтом, а пользователи на сайте филиала получают большинство функций Lync Server с серверов на связанном центральном сайте.</span><span class="sxs-lookup"><span data-stu-id="86098-111">Each branch site is associated with exactly one central site, and the users at the branch site get most of their Lync Server functionality from the servers at the associated central site.</span></span>

<span data-ttu-id="86098-112">Каждый сайт филиала содержит один из следующих компонентов.</span><span class="sxs-lookup"><span data-stu-id="86098-112">Each branch site contains one of the following:</span></span>

  - <span data-ttu-id="86098-113">Устройство для обеспечения связи в *филиалах (SBA)*, представляющее собой промышленный блейд-сервер с регистратором Lync Server и сервер-посредник, работающий под управлением Windows Server.</span><span class="sxs-lookup"><span data-stu-id="86098-113">A *Survivable Branch Appliance (SBA)*, which is an industry-standard blade server with a Lync Server Registrar and a Mediation Server running on Windows Server.</span></span> <span data-ttu-id="86098-114">Устройство для обеспечения связи в филиалах также содержит шлюз телефонной сети общего пользования (PSTN).</span><span class="sxs-lookup"><span data-stu-id="86098-114">The Survivable Branch Appliance also contains a public switched telephone network (PSTN) gateway.</span></span> <span data-ttu-id="86098-115">Устройство для обеспечения связи в филиалах предназначено для сайтов филиалов от 25 до 1000 пользователей.</span><span class="sxs-lookup"><span data-stu-id="86098-115">The Survivable Branch Appliance is designed for branch sites with between 25 and 1000 users.</span></span>

  - <span data-ttu-id="86098-116">Сервер обеспечения связи в *филиалах (SBS)*— это сервер под управлением Windows Server, который соответствует указанным требованиям к оборудованию и на котором установлено программное обеспечение сервера-посредника и регистратора Lync Server.</span><span class="sxs-lookup"><span data-stu-id="86098-116">A *Survivable Branch Server (SBS)*, which is a server running Windows Server that meets specified hardware requirements, and that has Lync Server Registrar and Mediation Server software installed on it.</span></span> <span data-ttu-id="86098-117">Он должен быть подключен к шлюзу ТСОП или магистрали SIP с поставщиком услуг телефонной связи.</span><span class="sxs-lookup"><span data-stu-id="86098-117">It must connect to either a PSTN gateway or a SIP trunk to a telephone service provider.</span></span> <span data-ttu-id="86098-118">Сервер для обеспечения связи в филиалах предназначен для филиалов с количеством пользователей от 1000 до 5000.</span><span class="sxs-lookup"><span data-stu-id="86098-118">The Survivable Branch Server is designed for branch sites with between 1000 and 5000 users.</span></span>

  - <span data-ttu-id="86098-119">Шлюз ТСОП и (необязательно) *сервер-посредник*.</span><span class="sxs-lookup"><span data-stu-id="86098-119">A PSTN gateway, and, optionally, a *Mediation Server*.</span></span> <span data-ttu-id="86098-120">Сведения об этих и других ролях серверов приведены в статье [Server Roles in Lync server 2013](lync-server-2013-server-roles.md).</span><span class="sxs-lookup"><span data-stu-id="86098-120">For details on this and other server roles, see [Server roles in Lync Server 2013](lync-server-2013-server-roles.md).</span></span>

<span data-ttu-id="86098-121">В филиале, подключенном к центральному сайту с помощью отказоустойчивого канала глобальной сети, может использоваться третий вариант (шлюз ТСОП и (необязательно) сервер-посредник).</span><span class="sxs-lookup"><span data-stu-id="86098-121">A branch office with a resilient wide area network (WAN) link to a central site can use the third option—a PSTN gateway, and, optionally, a Mediation Server.</span></span> <span data-ttu-id="86098-122">Сайты филиалов с менее гибкими связями должны использовать устройство для обеспечения связи в филиалах или сервер для обеспечения связи в филиалах, что обеспечивает устойчивость в периоды сбоя глобальной сети.</span><span class="sxs-lookup"><span data-stu-id="86098-122">Branch office sites with less-resilient links should use a Survivable Branch Appliance or Survivable Branch Server, which provide resiliency in times of wide-area network failures.</span></span> <span data-ttu-id="86098-123">Например, на сайте, где развернуто устройство для обеспечения связи в филиалах или сервере для обеспечения связи в филиалах, пользователи по-прежнему могут выполнять и принимать вызовы корпоративной голосовой связи, если глобальная сеть, соединяющая сайт филиала с центральным сайтом, не работает.</span><span class="sxs-lookup"><span data-stu-id="86098-123">For example, in a site with a Survivable Branch Appliance or Survivable Branch Server deployed, users can still make and receive Enterprise Voice calls if the WAN connecting the branch site to the central site is down.</span></span> <span data-ttu-id="86098-124">Сведения о том, как устройство для обеспечения связи в филиалах, обеспечения связи в филиалах и устойчивость, приведены в статье [Планирование устойчивости корпоративной голосовой связи в Lync Server 2013](lync-server-2013-planning-for-enterprise-voice-resiliency.md) в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="86098-124">For details about the Survivable Branch Appliance, Survivable Branch Server, and resiliency, see [Planning for Enterprise Voice resiliency in Lync Server 2013](lync-server-2013-planning-for-enterprise-voice-resiliency.md) in the Planning documentation.</span></span>

</div>

<div>

## <a name="site-topologies"></a><span data-ttu-id="86098-125">Топологии сайтов</span><span class="sxs-lookup"><span data-stu-id="86098-125">Site Topologies</span></span>

<span data-ttu-id="86098-126">Развертывание должно содержать, по крайней мере, один центральный сайт и может содержать ни одного или несколько филиалов.</span><span class="sxs-lookup"><span data-stu-id="86098-126">Your deployment must include at least one central site, and can include zero to many branch sites.</span></span> <span data-ttu-id="86098-127">Каждый филиал связан с одним центральным узлом.</span><span class="sxs-lookup"><span data-stu-id="86098-127">Each branch site is affiliated with one central site.</span></span> <span data-ttu-id="86098-128">Центральный сайт предоставляет службы Lync Server для сайта филиала, который не размещается локально на сайте филиала, например сведения о присутствии и конференциях.</span><span class="sxs-lookup"><span data-stu-id="86098-128">The central site provides the Lync Server services to the branch site that are not hosted locally at the branch site, such as presence and conferencing.</span></span>

<span data-ttu-id="86098-129">При использовании нескольких сайтов можно привязать друг к другу интерфейсные пулы на различных сайтах, чтобы предоставить возможности аварийного восстановления.</span><span class="sxs-lookup"><span data-stu-id="86098-129">If you have multiple sites, you can pair together the Front End pools at different sites to enable disaster recovery abilities.</span></span> <span data-ttu-id="86098-130">Дополнительные сведения см. [в статье поддержка обеспечения высокой доступности и аварийного восстановления в Lync Server 2013](lync-server-2013-high-availability-and-disaster-recovery-support.md).</span><span class="sxs-lookup"><span data-stu-id="86098-130">For details, see [High availability and disaster recovery support in Lync Server 2013](lync-server-2013-high-availability-and-disaster-recovery-support.md).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="86098-131">См. также</span><span class="sxs-lookup"><span data-stu-id="86098-131">See Also</span></span>


[<span data-ttu-id="86098-132">Роли сервера в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="86098-132">Server roles in Lync Server 2013</span></span>](lync-server-2013-server-roles.md)  
[<span data-ttu-id="86098-133">Поддержка высокого уровня доступности и аварийного восстановления в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="86098-133">High availability and disaster recovery support in Lync Server 2013</span></span>](lync-server-2013-high-availability-and-disaster-recovery-support.md)  


[<span data-ttu-id="86098-134">Планирование устойчивости корпоративной голосовой связи в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="86098-134">Planning for Enterprise Voice resiliency in Lync Server 2013</span></span>](lync-server-2013-planning-for-enterprise-voice-resiliency.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

