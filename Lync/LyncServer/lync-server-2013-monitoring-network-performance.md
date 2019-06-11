---
title: 'Lync Server 2013: мониторинг производительности сети'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Monitoring network performance
ms:assetid: bc3a01da-91eb-4c0c-9598-35e5e46b00f6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720923(v=OCS.15)
ms:contentKeyID: 63969647
ms.date: 04/27/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a2fa3c2685b4da32d5f2e3f123a938920b5ce9f7
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34826719"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="monitoring-network-performance-in-lync-server-2013"></a><span data-ttu-id="20bc5-102">Мониторинг производительности сети в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="20bc5-102">Monitoring network performance in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="20bc5-103">_**Тема последнего изменения:** 2016-04-27_</span><span class="sxs-lookup"><span data-stu-id="20bc5-103">_**Topic Last Modified:** 2016-04-27_</span></span>

<span data-ttu-id="20bc5-104">Lync Server 2013 — это технология связи в реальном времени, которая в значительной степени используется в сети для обмена данными между пользователями — с помощью обмена мгновенными сообщениями, голосовых вызовов и видеосвязи.</span><span class="sxs-lookup"><span data-stu-id="20bc5-104">Lync Server 2013 is a real-time communications technology that relies heavily on the network to enable communication between users—either through instant messaging (IM), voice calls, or video communication.</span></span> <span data-ttu-id="20bc5-105">Поэтому важно постоянно отслеживать производительность сети, чтобы гарантировать, что выбранная для пользователя модальность соединения обеспечивает максимально возможный опыт.</span><span class="sxs-lookup"><span data-stu-id="20bc5-105">It is therefore important to monitor the network performance continuously to help guarantee that a user’s chosen communication modality provides the best possible experience.</span></span>

<span data-ttu-id="20bc5-106">Производительность сети может измеряться на двух уровнях:</span><span class="sxs-lookup"><span data-stu-id="20bc5-106">Network performance can be measured at two levels:</span></span>

  - <span data-ttu-id="20bc5-107">**Общая производительность**   сети. Этот уровень оценки производительности позволяет организациям создавать представления своей сети с большим изображением и обычно реализуется с помощью сторонних систем мониторинга сети.</span><span class="sxs-lookup"><span data-stu-id="20bc5-107">**Overall network performance**   This level of performance measurement will allow an organization to create a "big-picture" view of their network and is usually implemented through third-party network monitoring systems.</span></span> <span data-ttu-id="20bc5-108">Эти системы будут получать данные о производительности и емкости с удаленных сетевых устройств, таких как маршрутизаторы и переключаются по всей сети, чтобы позволить администраторам определять работоспособность любого конкретного сетевого компонента в любое время суток.</span><span class="sxs-lookup"><span data-stu-id="20bc5-108">These systems will receive performance and capacity data from remote network devices such as routers and switched throughout the network to allow administrators to determine the health of any given network component at any time of day.</span></span>

  - <span data-ttu-id="20bc5-109">**Производительность отдельных серверов**   . Этот уровень оценки производительности ограничивается конкретным сервером и поможет администраторам с гаугинг производительность сети определенного сервера, чтобы помочь вам в устранении неполадок с определенной производительностью. или оценить производительность соответствующего сервера в течение определенного периода в рамках процесса планирования мощностей.</span><span class="sxs-lookup"><span data-stu-id="20bc5-109">**Individual server performance**   This level of performance measurement is limited to a specific server and will help administrators with gauging the network performance of a specific server to either help with troubleshooting a specific performance issue or to gauge the respective server’s performance over a given period as part of a capacity planning process.</span></span>

<span data-ttu-id="20bc5-110">Вы можете наблюдать за работой сети с помощью средств, описанных в следующих разделах.</span><span class="sxs-lookup"><span data-stu-id="20bc5-110">You can monitor the network by using the tools described in the following sections.</span></span>

<div>

## <a name="tools-for-overall-network-performance-monitoring"></a><span data-ttu-id="20bc5-111">Инструменты для общего мониторинга производительности сети</span><span class="sxs-lookup"><span data-stu-id="20bc5-111">Tools for Overall Network Performance Monitoring</span></span>

<div>

## <a name="system-center-operations-manager-2012"></a><span data-ttu-id="20bc5-112">System Center Operations Manager 2012</span><span class="sxs-lookup"><span data-stu-id="20bc5-112">System Center Operations Manager 2012</span></span>

<span data-ttu-id="20bc5-113">System Center Operations Manager обеспечивает комплексное управление службами, которое легко настраивать и расширять для улучшенных уровней обслуживания в ИТ-среде.</span><span class="sxs-lookup"><span data-stu-id="20bc5-113">System Center Operations Manager provides end-to-end service management that is easy to customize and extend for improved service levels across an IT environment.</span></span> <span data-ttu-id="20bc5-114">Это позволяет разработчикам управлять работой и обменяться группами, а также устранять проблемы, влияющие на работоспособность распределенных ИТ – служб.</span><span class="sxs-lookup"><span data-stu-id="20bc5-114">This enables Operations and IT Management teams to identify, and resolve issues affecting the health of distributed IT services.</span></span> <span data-ttu-id="20bc5-115">Сквозное управление службой не ограничивается только средой Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="20bc5-115">End-to-end service management is not restricted to Microsoft-based environments.</span></span> <span data-ttu-id="20bc5-116">Поддержка веб-служб для управления (WS-Management), протоколов SNMP и партнеров допускает компьютеры, на которых не работают операционные системы и оборудование Microsoft, которые можно включить в наблюдение за обслуживанием в System Center. Operations Manager 2012.</span><span class="sxs-lookup"><span data-stu-id="20bc5-116">Support for Web Services for Management (WS-Management), Simple Network Management Protocol (SNMP), and partner solutions allow for systems that do not run Microsoft operating systems and hardware to be included in service monitoring within System Center Operations Manager 2012.</span></span>

</div>

<div>

## <a name="system-center-operations-manager-2012-and-third-party-network-management-solutions"></a><span data-ttu-id="20bc5-117">System Center Operations Manager 2012 и сторонние решения для сетевых управления</span><span class="sxs-lookup"><span data-stu-id="20bc5-117">System Center Operations Manager 2012 and Third-Party Network Management Solutions</span></span>

<span data-ttu-id="20bc5-118">\*\*\*\*   Решения EMC SMARTING Operations Manager помогут вам быстро устранить проблемы, влияющие на уровни обслуживания в рамках.</span><span class="sxs-lookup"><span data-stu-id="20bc5-118">**EMC Smarts**   EMC Solutions for Operations Manager help you quickly resolve issues affecting service levels throughout.</span></span> <span data-ttu-id="20bc5-119">С помощью решений EMC для Operations Manager вы можете управлять всей цепочкой ИТ и отслеживать ее в рамках единого интегрированного автоматизированного решения.</span><span class="sxs-lookup"><span data-stu-id="20bc5-119">By using EMC Solutions for Operations Manager, you can manage and monitor your whole IT service chain with one integrated, automated solution.</span></span> <span data-ttu-id="20bc5-120">Вы можете легко выявить основные причины проблем с производительностью и доступностью и устранить их быстрее, что снижает последствия и затраты.</span><span class="sxs-lookup"><span data-stu-id="20bc5-120">You'll easily identify the root causes of performance and availability issues, and resolve them faster which reduces effects and costs.</span></span> <span data-ttu-id="20bc5-121">Основные преимущества включают следующее:</span><span class="sxs-lookup"><span data-stu-id="20bc5-121">Key benefits include the following:</span></span>

  - <span data-ttu-id="20bc5-122">Улучшенное и простое в использовании управление для предоставления стратегических бизнес-значений вместо ручной сортировки и фильтрации непонятных оповещений.</span><span class="sxs-lookup"><span data-stu-id="20bc5-122">Advanced, easy-to-use management   Focus on delivering strategic business value instead of manually sorting and filtering confusing alerts.</span></span>

  - <span data-ttu-id="20bc5-123">**Более быстрое разрешение**   помогает ИТ-вопросам и реагировать на потребности предприятий быстрее, уменьшая эффект и стоимость.</span><span class="sxs-lookup"><span data-stu-id="20bc5-123">**Faster resolution**   Solve IT issues and respond to business needs faster, reducing effect and cost.</span></span>

  - <span data-ttu-id="20bc5-124">**Оптимизированные операции**   , чтобы избежать сложностей, объединяя несколько средств управления, приложений и терминалов.</span><span class="sxs-lookup"><span data-stu-id="20bc5-124">**Streamlined operations**   Avoid IT complexity by combining multiple management tools, applications, and terminals.</span></span>

<span data-ttu-id="20bc5-125">Дополнительные сведения можно найти здесь:</span><span class="sxs-lookup"><span data-stu-id="20bc5-125">More information can be found here:</span></span>

[<span data-ttu-id="20bc5-126">Microsoft System Center Operations Manager</span><span class="sxs-lookup"><span data-stu-id="20bc5-126">Microsoft System Center Operations Manager</span></span>](http://go.microsoft.com/fwlink/p/?linkid=243651)

[<span data-ttu-id="20bc5-127">Решения для Microsoft System Center Operations Manager</span><span class="sxs-lookup"><span data-stu-id="20bc5-127">Solutions for Microsoft System Center Operations Manager</span></span>](http://www.emc.com/collateral/software/data-sheet/h6135-server-manager-ds.pdf)

</div>

<div>

## <a name="third-party-solutions"></a><span data-ttu-id="20bc5-128">Сторонние решения</span><span class="sxs-lookup"><span data-stu-id="20bc5-128">Third-Party Solutions</span></span>

<span data-ttu-id="20bc5-129">**HP Network Management Center (ранее называлась HP OpenView)**    [HP Network Management Center](http://www8.hp.com/us/en/software-solutions/network-management/index.html?%26zn=bto%26cp=1-11-15-119_4000_100__) обеспечивает интегрированное управление неполадками и производительностью для повышения доступности и производительности сети.</span><span class="sxs-lookup"><span data-stu-id="20bc5-129">**HP Network Management Center (previously known as HP OpenView)**   [HP Network Management Center](http://www8.hp.com/us/en/software-solutions/network-management/index.html?%26zn=bto%26cp=1-11-15-119_4000_100__) provides integrated fault and performance management to improve network availability and performance.</span></span> <span data-ttu-id="20bc5-130">Центр управления сетью — это компонент автоматического сетевого управления HP, который объединяет ошибки, производительность, конфигурацию и управление изменениями.</span><span class="sxs-lookup"><span data-stu-id="20bc5-130">Network Management Center is part of the HP automated network management solution that unifies fault, performance, configuration, and change management.</span></span>

<span data-ttu-id="20bc5-131">**Продукты Skype Network Management и автоматизации**   для предприятий компании Cisco есть несколько программных продуктов, в том числе решение для управления Цисковоркс локальной сети и модуль анализа сети Cisco, помогающие повысить эффективность работы и уменьшение времени простоя сети.</span><span class="sxs-lookup"><span data-stu-id="20bc5-131">**Cisco Network Management and Automation products**   For the Enterprise, Cisco has several management products available including CiscoWorks LAN Management Solution and Cisco Network Analysis Module, to help improve operational efficiency and reduce network downtime.</span></span> <span data-ttu-id="20bc5-132">Дополнительные сведения об этих продуктах можно найти на веб-сайте Cisco [http://www.cisco.com/en/US/products/sw/netmgtsw/index.html](http://www.cisco.com/en/us/products/sw/netmgtsw/index.html).</span><span class="sxs-lookup"><span data-stu-id="20bc5-132">For additional data on these products, refer to the Cisco website at [http://www.cisco.com/en/US/products/sw/netmgtsw/index.html](http://www.cisco.com/en/us/products/sw/netmgtsw/index.html).</span></span>

<span data-ttu-id="20bc5-133">Протокол SNMP (Simple Network Management Protocol) — это стандарт сетевого управления, который определяет стратегию управления сетями TCP/IP.</span><span class="sxs-lookup"><span data-stu-id="20bc5-133">Simple Network Management Protocol (SNMP)   Simple Network Management Protocol (SNMP) is a network management standard that defines a strategy for managing TCP/IP networks.</span></span> <span data-ttu-id="20bc5-134">SNMP позволяет собирать сведения о конфигурации и состоянии сети, а также отправлять сведения для отслеживания событий на компьютере, на который он указывает.</span><span class="sxs-lookup"><span data-stu-id="20bc5-134">SNMP enables you to capture configuration and status information about the network, and send the information to a designated computer for event monitoring.</span></span> <span data-ttu-id="20bc5-135">Протокол управления сетью на основе стандартов использует распределенную архитектуру, которая включает следующие функции:</span><span class="sxs-lookup"><span data-stu-id="20bc5-135">This standards based network management protocol uses a distributed architecture that includes the following:</span></span>

  - <span data-ttu-id="20bc5-136">Несколько управляемых узлов, каждый из которых имеет объект SNMP, называемый агентом, который предоставляет удаленный доступ к инструментарию управления.</span><span class="sxs-lookup"><span data-stu-id="20bc5-136">Multiple managed nodes, each with an SNMP entity called an agent which provides remote access to management instrumentation.</span></span>

  - <span data-ttu-id="20bc5-137">По крайней мере один SNMP-объект, известный как диспетчер, который запускает приложения управления для мониторинга управляемых элементов и управления ими.</span><span class="sxs-lookup"><span data-stu-id="20bc5-137">At least one SNMP entity known as a manager which runs management applications to monitor and control managed elements.</span></span> <span data-ttu-id="20bc5-138">Управляемые элементы — это устройства, такие как узлы, маршрутизаторы и т. д.</span><span class="sxs-lookup"><span data-stu-id="20bc5-138">Managed elements are devices such as hosts, routers, and so on.</span></span> <span data-ttu-id="20bc5-139">Они отслеживаются и контролируются за счет доступа к сведениям об управлении.</span><span class="sxs-lookup"><span data-stu-id="20bc5-139">They are monitored and controlled by accessing their management information.</span></span>

  - <span data-ttu-id="20bc5-140">Протокол управления SNMP используется для обмена сведениями об управлении между станциями управления и агентами.</span><span class="sxs-lookup"><span data-stu-id="20bc5-140">A management protocol, SNMP, is used to communicate management information between the management stations and agents.</span></span> <span data-ttu-id="20bc5-141">Сведения об управлении относятся к коллекции управляемых объектов, которые хранятся в виртуальном хранилище данных, которое называется базой MIB (Information Management Base).</span><span class="sxs-lookup"><span data-stu-id="20bc5-141">Management information refers to a collection of managed objects that live in a virtual information store called a Management Information Base (MIB).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="20bc5-142">Ниже приведены примеры решений для мониторинга сети сторонних производителей.</span><span class="sxs-lookup"><span data-stu-id="20bc5-142">Examples of third-party network monitoring solutions are provided above.</span></span> <span data-ttu-id="20bc5-143">Этот список не является окончательным, и Microsoft не подходит ни одному конкретному решению поставщика.</span><span class="sxs-lookup"><span data-stu-id="20bc5-143">This list is not definitive and Microsoft does not favor any specific vendor solution.</span></span> <span data-ttu-id="20bc5-144">Обратитесь к поставщику услуг сети и поставщику соответствующих технологий, чтобы определить оптимальное решение для мониторинга сети для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="20bc5-144">Consult with a network service provider and or your respective technology provider to determine the best network monitoring solution for your organization.</span></span>



</div>

</div>

</div>

<div>

## <a name="tools-for-monitoring-individual-server-network-performance"></a><span data-ttu-id="20bc5-145">Средства мониторинга производительности сети на отдельных серверах</span><span class="sxs-lookup"><span data-stu-id="20bc5-145">Tools for Monitoring Individual Server Network Performance</span></span>

<div>

## <a name="system-center-operations-manager-2012"></a><span data-ttu-id="20bc5-146">System Center Operations Manager 2012</span><span class="sxs-lookup"><span data-stu-id="20bc5-146">System Center Operations Manager 2012</span></span>

<span data-ttu-id="20bc5-147">System Center Operations Manager 2012 позволит администраторам просматривать производительность сети отдельных серверов с помощью пакета управления Windows Server 2012: пакет управления операционной системой Windows Server включает пакет управления "производительность". Это позволит администраторам отслеживать производительность сетевого адаптера и исправность адаптера.</span><span class="sxs-lookup"><span data-stu-id="20bc5-147">System Center Operations Manager 2012 would allow administrators to view network performance of individual servers through the Windows Server 2012 Management Pack: The Windows Server operating system management pack includes a "Performance" management pack that would allow administrators to monitor Network Adapter performance and adapter health.</span></span>

</div>

<div>

## <a name="windows-network-monitor"></a><span data-ttu-id="20bc5-148">Сетевой монитор Windows</span><span class="sxs-lookup"><span data-stu-id="20bc5-148">Windows Network Monitor</span></span>

<span data-ttu-id="20bc5-149">Собирает, отображает, анализирует использование ресурсов на сервере и измеряет сетевой трафик.</span><span class="sxs-lookup"><span data-stu-id="20bc5-149">Collects, displays, analyzes resource usage on a server, and measures network traffic.</span></span> <span data-ttu-id="20bc5-150">Сетевой монитор наблюдает за работой сети в монопольном режиме.</span><span class="sxs-lookup"><span data-stu-id="20bc5-150">Network Monitor exclusively monitors network activity.</span></span> <span data-ttu-id="20bc5-151">Выбирая и анализируя данные сети и используя эти данные в журналах производительности, вы можете определять использование сети, определять сетевые проблемы и прогнозировать будущие потребности в сети.</span><span class="sxs-lookup"><span data-stu-id="20bc5-151">By capturing and analyzing network data, and using this data with performance logs, you can determine the network usage, identify network issues, and forecast future network needs.</span></span>

<span data-ttu-id="20bc5-152">Для получения дополнительных сведений о сетевом мониторе 3,4, а также о том, как устанавливать и настраивать сетевой монитор и собирать и анализировать данные, ознакомьтесь с этим сеансом: Обзор сетевого монитора 3,3.</span><span class="sxs-lookup"><span data-stu-id="20bc5-152">For more information about Network Monitor 3.4, and to learn how to install and configure Network Monitor and capture and analyze data, review this session: Network Monitor 3.3 Overview.</span></span> <span data-ttu-id="20bc5-153">Кроме того, проверьте [блог сетевого монитора](http://blogs.technet.com/b/netmon/).</span><span class="sxs-lookup"><span data-stu-id="20bc5-153">Also, review the [Network Monitor blog](http://blogs.technet.com/b/netmon/).</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

