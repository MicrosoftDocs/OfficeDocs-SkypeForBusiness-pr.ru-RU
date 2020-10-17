---
title: Сайты Lync Server 2013
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
ms.openlocfilehash: 7193d657ad1e585b1a82ba8e934e5bf99d83e65b
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48519616"
---
# <a name="lync-server-sites-for-lync-server-2013"></a><span data-ttu-id="9dab4-102">Сайты Lync Server для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9dab4-102">Lync Server sites for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9dab4-103">_**Последнее изменение темы:** 2012-10-16_</span><span class="sxs-lookup"><span data-stu-id="9dab4-103">_**Topic Last Modified:** 2012-10-16_</span></span>

<span data-ttu-id="9dab4-104">В Lync Server вы определяете *сайты* в сети, содержащие компоненты Lync Server.</span><span class="sxs-lookup"><span data-stu-id="9dab4-104">In Lync Server, you define *sites* on your network that contain Lync Server components.</span></span> <span data-ttu-id="9dab4-105">Сайт — это набор компьютеров, соединенных с помощью сети с высокой пропускной способностью и низкой задержкой, например локальной сети, или две сети, соединенные с помощью высокоскоростного оптоволоконного канала.</span><span class="sxs-lookup"><span data-stu-id="9dab4-105">A site is a set of computers that is well-connected by a high-speed, low-latency network, such as a single local area network (LAN) or two networks connected by a high-speed fiber optic network.</span></span> <span data-ttu-id="9dab4-106">Обратите внимание, что сайты Lync Server — это отдельная концепция сайтов доменных служб Active Directory и сайтов Microsoft Exchange Server.</span><span class="sxs-lookup"><span data-stu-id="9dab4-106">Note that Lync Server sites are a separate concept from Active Directory Domain Services sites and Microsoft Exchange Server sites.</span></span> <span data-ttu-id="9dab4-107">Сайты Lync Server не обязаны соответствовать сайтам Active Directory.</span><span class="sxs-lookup"><span data-stu-id="9dab4-107">Your Lync Server sites do not need to correspond to your Active Directory sites.</span></span>

<div>

## <a name="site-types"></a><span data-ttu-id="9dab4-108">Типы сайтов</span><span class="sxs-lookup"><span data-stu-id="9dab4-108">Site Types</span></span>

<span data-ttu-id="9dab4-109">Каждый сайт является *центральным сайтом*, который содержит по крайней мере один интерфейсный пул или сервер Standard Edition или *сайт филиала*.</span><span class="sxs-lookup"><span data-stu-id="9dab4-109">Each site is either a *central site*, which contains at least one Front End pool or a Standard Edition server, or a *branch site*.</span></span> <span data-ttu-id="9dab4-110">Каждый сайт филиала связан с одним центральным сайтом, а пользователи на сайте филиала получают большинство функций Lync Server с серверов на связанном центральном сайте.</span><span class="sxs-lookup"><span data-stu-id="9dab4-110">Each branch site is associated with exactly one central site, and the users at the branch site get most of their Lync Server functionality from the servers at the associated central site.</span></span>

<span data-ttu-id="9dab4-111">Каждый сайт филиала содержит один из следующих компонентов.</span><span class="sxs-lookup"><span data-stu-id="9dab4-111">Each branch site contains one of the following:</span></span>

  - <span data-ttu-id="9dab4-112">Устройство для обеспечения связи в *филиалах (SBA)*, представляющее собой промышленный блейд-сервер с регистратором Lync Server и сервер-посредник, работающий под управлением Windows Server.</span><span class="sxs-lookup"><span data-stu-id="9dab4-112">A *Survivable Branch Appliance (SBA)*, which is an industry-standard blade server with a Lync Server Registrar and a Mediation Server running on Windows Server.</span></span> <span data-ttu-id="9dab4-113">Устройство для обеспечения связи в филиалах также содержит шлюз телефонной сети общего пользования (PSTN).</span><span class="sxs-lookup"><span data-stu-id="9dab4-113">The Survivable Branch Appliance also contains a public switched telephone network (PSTN) gateway.</span></span> <span data-ttu-id="9dab4-114">Устройство для обеспечения связи в филиалах предназначено для сайтов филиалов от 25 до 1000 пользователей.</span><span class="sxs-lookup"><span data-stu-id="9dab4-114">The Survivable Branch Appliance is designed for branch sites with between 25 and 1000 users.</span></span>

  - <span data-ttu-id="9dab4-115">Сервер обеспечения связи в *филиалах (SBS)*— это сервер под управлением Windows Server, который соответствует указанным требованиям к оборудованию и на котором установлено программное обеспечение сервера-посредника и регистратора Lync Server.</span><span class="sxs-lookup"><span data-stu-id="9dab4-115">A *Survivable Branch Server (SBS)*, which is a server running Windows Server that meets specified hardware requirements, and that has Lync Server Registrar and Mediation Server software installed on it.</span></span> <span data-ttu-id="9dab4-116">Он должен быть подключен к шлюзу ТСОП или магистрали SIP с поставщиком услуг телефонной связи.</span><span class="sxs-lookup"><span data-stu-id="9dab4-116">It must connect to either a PSTN gateway or a SIP trunk to a telephone service provider.</span></span> <span data-ttu-id="9dab4-117">Сервер для обеспечения связи в филиалах предназначен для филиалов с количеством пользователей от 1000 до 5000.</span><span class="sxs-lookup"><span data-stu-id="9dab4-117">The Survivable Branch Server is designed for branch sites with between 1000 and 5000 users.</span></span>

  - <span data-ttu-id="9dab4-118">Шлюз ТСОП и (необязательно) *сервер-посредник*.</span><span class="sxs-lookup"><span data-stu-id="9dab4-118">A PSTN gateway, and, optionally, a *Mediation Server*.</span></span> <span data-ttu-id="9dab4-119">Сведения об этих и других ролях серверов приведены в статье [Server Roles in Lync server 2013](lync-server-2013-server-roles.md).</span><span class="sxs-lookup"><span data-stu-id="9dab4-119">For details on this and other server roles, see [Server roles in Lync Server 2013](lync-server-2013-server-roles.md).</span></span>

<span data-ttu-id="9dab4-120">В филиале, подключенном к центральному сайту с помощью отказоустойчивого канала глобальной сети, может использоваться третий вариант (шлюз ТСОП и (необязательно) сервер-посредник).</span><span class="sxs-lookup"><span data-stu-id="9dab4-120">A branch office with a resilient wide area network (WAN) link to a central site can use the third option—a PSTN gateway, and, optionally, a Mediation Server.</span></span> <span data-ttu-id="9dab4-121">Сайты филиалов с менее гибкими связями должны использовать устройство для обеспечения связи в филиалах или сервер для обеспечения связи в филиалах, что обеспечивает устойчивость в периоды сбоя глобальной сети.</span><span class="sxs-lookup"><span data-stu-id="9dab4-121">Branch office sites with less-resilient links should use a Survivable Branch Appliance or Survivable Branch Server, which provide resiliency in times of wide-area network failures.</span></span> <span data-ttu-id="9dab4-122">Например, на сайте, где развернуто устройство для обеспечения связи в филиалах или сервере для обеспечения связи в филиалах, пользователи по-прежнему могут выполнять и принимать вызовы корпоративной голосовой связи, если глобальная сеть, соединяющая сайт филиала с центральным сайтом, не работает.</span><span class="sxs-lookup"><span data-stu-id="9dab4-122">For example, in a site with a Survivable Branch Appliance or Survivable Branch Server deployed, users can still make and receive Enterprise Voice calls if the WAN connecting the branch site to the central site is down.</span></span> <span data-ttu-id="9dab4-123">Сведения о том, как устройство для обеспечения связи в филиалах, обеспечения связи в филиалах и устойчивость, приведены в статье [Планирование устойчивости корпоративной голосовой связи в Lync Server 2013](lync-server-2013-planning-for-enterprise-voice-resiliency.md) в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="9dab4-123">For details about the Survivable Branch Appliance, Survivable Branch Server, and resiliency, see [Planning for Enterprise Voice resiliency in Lync Server 2013](lync-server-2013-planning-for-enterprise-voice-resiliency.md) in the Planning documentation.</span></span>

</div>

<div>

## <a name="site-topologies"></a><span data-ttu-id="9dab4-124">Топологии сайтов</span><span class="sxs-lookup"><span data-stu-id="9dab4-124">Site Topologies</span></span>

<span data-ttu-id="9dab4-125">Развертывание должно содержать, по крайней мере, один центральный сайт и может содержать ни одного или несколько филиалов.</span><span class="sxs-lookup"><span data-stu-id="9dab4-125">Your deployment must include at least one central site, and can include zero to many branch sites.</span></span> <span data-ttu-id="9dab4-126">Каждый филиал связан с одним центральным узлом.</span><span class="sxs-lookup"><span data-stu-id="9dab4-126">Each branch site is affiliated with one central site.</span></span> <span data-ttu-id="9dab4-127">Центральный сайт предоставляет службы Lync Server для сайта филиала, который не размещается локально на сайте филиала, например сведения о присутствии и конференциях.</span><span class="sxs-lookup"><span data-stu-id="9dab4-127">The central site provides the Lync Server services to the branch site that are not hosted locally at the branch site, such as presence and conferencing.</span></span>

<span data-ttu-id="9dab4-128">При использовании нескольких сайтов можно привязать друг к другу интерфейсные пулы на различных сайтах, чтобы предоставить возможности аварийного восстановления.</span><span class="sxs-lookup"><span data-stu-id="9dab4-128">If you have multiple sites, you can pair together the Front End pools at different sites to enable disaster recovery abilities.</span></span> <span data-ttu-id="9dab4-129">Дополнительные сведения см. [в статье поддержка обеспечения высокой доступности и аварийного восстановления в Lync Server 2013](lync-server-2013-high-availability-and-disaster-recovery-support.md).</span><span class="sxs-lookup"><span data-stu-id="9dab4-129">For details, see [High availability and disaster recovery support in Lync Server 2013](lync-server-2013-high-availability-and-disaster-recovery-support.md).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="9dab4-130">См. также</span><span class="sxs-lookup"><span data-stu-id="9dab4-130">See Also</span></span>


[<span data-ttu-id="9dab4-131">Роли сервера в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9dab4-131">Server roles in Lync Server 2013</span></span>](lync-server-2013-server-roles.md)  
[<span data-ttu-id="9dab4-132">Поддержка высокого уровня доступности и аварийного восстановления в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9dab4-132">High availability and disaster recovery support in Lync Server 2013</span></span>](lync-server-2013-high-availability-and-disaster-recovery-support.md)  


[<span data-ttu-id="9dab4-133">Планирование устойчивости корпоративной голосовой связи в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9dab4-133">Planning for Enterprise Voice resiliency in Lync Server 2013</span></span>](lync-server-2013-planning-for-enterprise-voice-resiliency.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

