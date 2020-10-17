---
title: 'Lync Server 2013: Мониторинг производительности сети'
description: 'Lync Server 2013: Мониторинг производительности сети.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Monitoring network performance
ms:assetid: bc3a01da-91eb-4c0c-9598-35e5e46b00f6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720923(v=OCS.15)
ms:contentKeyID: 63969647
ms.date: 04/27/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0ead7e3f9001b06c783c9b22327581e795a20322
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48549455"
---
# <a name="monitoring-network-performance-in-lync-server-2013"></a><span data-ttu-id="de647-103">Мониторинг производительности сети в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="de647-103">Monitoring network performance in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="de647-104">_**Последнее изменение темы:** 2016-04-27_</span><span class="sxs-lookup"><span data-stu-id="de647-104">_**Topic Last Modified:** 2016-04-27_</span></span>

<span data-ttu-id="de647-105">Lync Server 2013 — это технология связи в режиме реального времени, которая в значительной степени использует сеть для обеспечения связи между пользователями (с помощью обмена мгновенными сообщениями, голосовых вызовов или видеосвязи).</span><span class="sxs-lookup"><span data-stu-id="de647-105">Lync Server 2013 is a real-time communications technology that relies heavily on the network to enable communication between users—either through instant messaging (IM), voice calls, or video communication.</span></span> <span data-ttu-id="de647-106">Поэтому важно постоянно отслеживать производительность сети, чтобы гарантировать, что выбранная модальность связи пользователя обеспечивает максимально возможный интерфейс.</span><span class="sxs-lookup"><span data-stu-id="de647-106">It is therefore important to monitor the network performance continuously to help guarantee that a user’s chosen communication modality provides the best possible experience.</span></span>

<span data-ttu-id="de647-107">Производительность сети можно измерять на двух уровнях:</span><span class="sxs-lookup"><span data-stu-id="de647-107">Network performance can be measured at two levels:</span></span>

  - <span data-ttu-id="de647-108">**Общая производительность сети**     Этот уровень оценки производительности позволит Организации создавать представление своей сети "большой рисунок" и обычно реализуется с помощью сторонних систем мониторинга сети.</span><span class="sxs-lookup"><span data-stu-id="de647-108">**Overall network performance**   This level of performance measurement will allow an organization to create a "big-picture" view of their network and is usually implemented through third-party network monitoring systems.</span></span> <span data-ttu-id="de647-109">Эти системы будут получать данные о производительности и емкости с удаленных сетевых устройств, таких как маршрутизаторы и которые переключаются по всей сети, чтобы позволить администраторам определять работоспособность любого конкретного сетевого компонента в любое время суток.</span><span class="sxs-lookup"><span data-stu-id="de647-109">These systems will receive performance and capacity data from remote network devices such as routers and switched throughout the network to allow administrators to determine the health of any given network component at any time of day.</span></span>

  - <span data-ttu-id="de647-110">**Производительность**     отдельных серверов Этот уровень измерения производительности ограничен определенным сервером и поможет администраторам гаугинг производительность сети определенного сервера, чтобы помочь в устранении определенных проблем с производительностью или оценки производительности соответствующего сервера за определенный период в рамках процесса планирования мощности.</span><span class="sxs-lookup"><span data-stu-id="de647-110">**Individual server performance**   This level of performance measurement is limited to a specific server and will help administrators with gauging the network performance of a specific server to either help with troubleshooting a specific performance issue or to gauge the respective server’s performance over a given period as part of a capacity planning process.</span></span>

<span data-ttu-id="de647-111">Вы можете отслеживать сеть с помощью средств, описанных в следующих разделах.</span><span class="sxs-lookup"><span data-stu-id="de647-111">You can monitor the network by using the tools described in the following sections.</span></span>

<div>

## <a name="tools-for-overall-network-performance-monitoring"></a><span data-ttu-id="de647-112">Средства для общего мониторинга производительности сети</span><span class="sxs-lookup"><span data-stu-id="de647-112">Tools for Overall Network Performance Monitoring</span></span>

<div>

## <a name="system-center-operations-manager-2012"></a><span data-ttu-id="de647-113">System Center Operations Manager 2012</span><span class="sxs-lookup"><span data-stu-id="de647-113">System Center Operations Manager 2012</span></span>

<span data-ttu-id="de647-114">System Center Operations Manager обеспечивает комплексное управление службами, которое легко настраивать и расширять для улучшения уровней обслуживания в ИТ-среде.</span><span class="sxs-lookup"><span data-stu-id="de647-114">System Center Operations Manager provides end-to-end service management that is easy to customize and extend for improved service levels across an IT environment.</span></span> <span data-ttu-id="de647-115">Это позволяет Teams и IT Management Teams определять и устранять проблемы, влияющие на работоспособность распределенных ИТ служб.</span><span class="sxs-lookup"><span data-stu-id="de647-115">This enables Operations and IT Management teams to identify, and resolve issues affecting the health of distributed IT services.</span></span> <span data-ttu-id="de647-116">Комплексное управление службами не ограничено средами на основе Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="de647-116">End-to-end service management is not restricted to Microsoft-based environments.</span></span> <span data-ttu-id="de647-117">Поддержка веб-служб для управления (WS-Management), протокола SNMP и партнерских решений позволяет системам, на которых не работают операционные системы и оборудование Майкрософт, включаться в наблюдение за службами в System Center Operations Manager 2012.</span><span class="sxs-lookup"><span data-stu-id="de647-117">Support for Web Services for Management (WS-Management), Simple Network Management Protocol (SNMP), and partner solutions allow for systems that do not run Microsoft operating systems and hardware to be included in service monitoring within System Center Operations Manager 2012.</span></span>

</div>

<div>

## <a name="system-center-operations-manager-2012-and-third-party-network-management-solutions"></a><span data-ttu-id="de647-118">System Center Operations Manager 2012 и сторонние решения для управления сетью</span><span class="sxs-lookup"><span data-stu-id="de647-118">System Center Operations Manager 2012 and Third-Party Network Management Solutions</span></span>

<span data-ttu-id="de647-119">Интеллектуальные» для **EMC**     Решения EMC для Operations Manager помогают быстро устранять проблемы, затрагивающие уровни обслуживания по всему.</span><span class="sxs-lookup"><span data-stu-id="de647-119">**EMC Smarts**   EMC Solutions for Operations Manager help you quickly resolve issues affecting service levels throughout.</span></span> <span data-ttu-id="de647-120">С помощью решений EMC для Operations Manager вы можете управлять всей своей цепочкой ИТ, используя одно интегрированное автоматизированное решение.</span><span class="sxs-lookup"><span data-stu-id="de647-120">By using EMC Solutions for Operations Manager, you can manage and monitor your whole IT service chain with one integrated, automated solution.</span></span> <span data-ttu-id="de647-121">Вы можете легко определить основные причины проблем с производительностью и доступностью и устранить их быстрее, что сокращает влияние и затраты.</span><span class="sxs-lookup"><span data-stu-id="de647-121">You'll easily identify the root causes of performance and availability issues, and resolve them faster which reduces effects and costs.</span></span> <span data-ttu-id="de647-122">К ключевым преимуществам относятся следующие:</span><span class="sxs-lookup"><span data-stu-id="de647-122">Key benefits include the following:</span></span>

  - <span data-ttu-id="de647-123">Расширенное, простое в использовании фокусирование управления для обеспечения стратегической бизнес-ценности вместо ручного сортировки и фильтрации непонятных оповещений.</span><span class="sxs-lookup"><span data-stu-id="de647-123">Advanced, easy-to-use management   Focus on delivering strategic business value instead of manually sorting and filtering confusing alerts.</span></span>

  - <span data-ttu-id="de647-124">**Более быстрое решение**     Решение ИТ-проблем и реагирование на потребности бизнеса ускоряется, уменьшая последствия и стоимость.</span><span class="sxs-lookup"><span data-stu-id="de647-124">**Faster resolution**   Solve IT issues and respond to business needs faster, reducing effect and cost.</span></span>

  - <span data-ttu-id="de647-125">**Оптимизированные операции**     Избегайте сложностей, объединив несколько средств управления, приложений и терминалов.</span><span class="sxs-lookup"><span data-stu-id="de647-125">**Streamlined operations**   Avoid IT complexity by combining multiple management tools, applications, and terminals.</span></span>

<span data-ttu-id="de647-126">Дополнительные сведения можно найти здесь:</span><span class="sxs-lookup"><span data-stu-id="de647-126">More information can be found here:</span></span>

[<span data-ttu-id="de647-127">Microsoft System Center Operations Manager</span><span class="sxs-lookup"><span data-stu-id="de647-127">Microsoft System Center Operations Manager</span></span>](https://go.microsoft.com/fwlink/p/?linkid=243651)

[<span data-ttu-id="de647-128">Решения для Microsoft System Center Operations Manager</span><span class="sxs-lookup"><span data-stu-id="de647-128">Solutions for Microsoft System Center Operations Manager</span></span>](http://www.emc.com/collateral/software/data-sheet/h6135-server-manager-ds.pdf)

</div>

<div>

## <a name="third-party-solutions"></a><span data-ttu-id="de647-129">Сторонние решения</span><span class="sxs-lookup"><span data-stu-id="de647-129">Third-Party Solutions</span></span>

<span data-ttu-id="de647-130">**HP Network Management Center (ранее известной как HP опенвиев)**   [HP Network Management Center](http://www8.hp.com/us/en/software-solutions/network-management/index.html?%26zn=bto%26cp=1-11-15-119_4000_100__) обеспечивает интегрированное управление сбоями и производительностью для повышения доступности и производительности сети.</span><span class="sxs-lookup"><span data-stu-id="de647-130">**HP Network Management Center (previously known as HP OpenView)**   [HP Network Management Center](http://www8.hp.com/us/en/software-solutions/network-management/index.html?%26zn=bto%26cp=1-11-15-119_4000_100__) provides integrated fault and performance management to improve network availability and performance.</span></span> <span data-ttu-id="de647-131">Центр управления сетью является частью автоматизированного решения по управлению сетью HP, которое объединяет сбои, производительность, конфигурацию и управление изменениями.</span><span class="sxs-lookup"><span data-stu-id="de647-131">Network Management Center is part of the HP automated network management solution that unifies fault, performance, configuration, and change management.</span></span>

<span data-ttu-id="de647-132">**Cisco Network Management and Automation Products**     Для предприятия Cisco имеет несколько продуктов управления, включая решение Цисковоркс LAN Management и модуль анализа Cisco Network для повышения эффективности работы и снижения простоя сети.</span><span class="sxs-lookup"><span data-stu-id="de647-132">**Cisco Network Management and Automation products**   For the Enterprise, Cisco has several management products available including CiscoWorks LAN Management Solution and Cisco Network Analysis Module, to help improve operational efficiency and reduce network downtime.</span></span> <span data-ttu-id="de647-133">За дополнительными сведениями об этих продуктах обращайтесь на веб-сайт Cisco по адресу [https://www.cisco.com/en/US/products/sw/netmgtsw/index.html](https://www.cisco.com/en/us/products/sw/netmgtsw/index.html) .</span><span class="sxs-lookup"><span data-stu-id="de647-133">For additional data on these products, refer to the Cisco website at [https://www.cisco.com/en/US/products/sw/netmgtsw/index.html](https://www.cisco.com/en/us/products/sw/netmgtsw/index.html).</span></span>

<span data-ttu-id="de647-134">Протокол SNMP (Simple Network Management Protocol) — это стандарт управления сетью, определяющий стратегию управления сетями TCP/IP.</span><span class="sxs-lookup"><span data-stu-id="de647-134">Simple Network Management Protocol (SNMP)   Simple Network Management Protocol (SNMP) is a network management standard that defines a strategy for managing TCP/IP networks.</span></span> <span data-ttu-id="de647-135">SNMP позволяет записывать конфигурацию и сведения о состоянии сети, а также отправлять данные на указанный компьютер для отслеживания событий.</span><span class="sxs-lookup"><span data-stu-id="de647-135">SNMP enables you to capture configuration and status information about the network, and send the information to a designated computer for event monitoring.</span></span> <span data-ttu-id="de647-136">Этот протокол управления сетью на основе стандартов использует распределенную архитектуру, которая включает следующие компоненты:</span><span class="sxs-lookup"><span data-stu-id="de647-136">This standards based network management protocol uses a distributed architecture that includes the following:</span></span>

  - <span data-ttu-id="de647-137">Несколько управляемых узлов, каждый из которых имеет объект SNMP, называемый агентом, который обеспечивает удаленный доступ к инструментарию управления.</span><span class="sxs-lookup"><span data-stu-id="de647-137">Multiple managed nodes, each with an SNMP entity called an agent which provides remote access to management instrumentation.</span></span>

  - <span data-ttu-id="de647-138">По крайней мере один объект SNMP, известный как диспетчер, который запускает приложения управления для мониторинга и управления управляемыми элементами.</span><span class="sxs-lookup"><span data-stu-id="de647-138">At least one SNMP entity known as a manager which runs management applications to monitor and control managed elements.</span></span> <span data-ttu-id="de647-139">Управляемые элементы — это устройства, такие как hosts, routers и т. д.</span><span class="sxs-lookup"><span data-stu-id="de647-139">Managed elements are devices such as hosts, routers, and so on.</span></span> <span data-ttu-id="de647-140">Мониторинг и управление ими осуществляется путем доступа к сведениям об управлении.</span><span class="sxs-lookup"><span data-stu-id="de647-140">They are monitored and controlled by accessing their management information.</span></span>

  - <span data-ttu-id="de647-141">Протокол управления SNMP используется для передачи сведений об управлении между станциями и агентами управления.</span><span class="sxs-lookup"><span data-stu-id="de647-141">A management protocol, SNMP, is used to communicate management information between the management stations and agents.</span></span> <span data-ttu-id="de647-142">Сведения об управлении относятся к набору управляемых объектов, которые находятся в виртуальном банке данных, называемом информационной базой данных управления (MIB).</span><span class="sxs-lookup"><span data-stu-id="de647-142">Management information refers to a collection of managed objects that live in a virtual information store called a Management Information Base (MIB).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="de647-143">Ниже приведены примеры решений мониторинга сети сторонних производителей.</span><span class="sxs-lookup"><span data-stu-id="de647-143">Examples of third-party network monitoring solutions are provided above.</span></span> <span data-ttu-id="de647-144">Этот список не имеет определенного приоритета, а корпорация Майкрософт не предпочитает какое-либо конкретное решение поставщика.</span><span class="sxs-lookup"><span data-stu-id="de647-144">This list is not definitive and Microsoft does not favor any specific vendor solution.</span></span> <span data-ttu-id="de647-145">Обратитесь к поставщику сетевых услуг и соответствующему поставщику услуг, чтобы определить оптимальное решение для мониторинга сети в Организации.</span><span class="sxs-lookup"><span data-stu-id="de647-145">Consult with a network service provider and or your respective technology provider to determine the best network monitoring solution for your organization.</span></span>



</div>

</div>

</div>

<div>

## <a name="tools-for-monitoring-individual-server-network-performance"></a><span data-ttu-id="de647-146">Средства мониторинга производительности сети отдельных серверов</span><span class="sxs-lookup"><span data-stu-id="de647-146">Tools for Monitoring Individual Server Network Performance</span></span>

<div>

## <a name="system-center-operations-manager-2012"></a><span data-ttu-id="de647-147">System Center Operations Manager 2012</span><span class="sxs-lookup"><span data-stu-id="de647-147">System Center Operations Manager 2012</span></span>

<span data-ttu-id="de647-148">System Center Operations Manager 2012 позволит администраторам просматривать производительность сети отдельных серверов с помощью пакета управления Windows Server 2012: пакет управления операционной системой Windows Server включает пакет управления "производительность", который позволяет администраторам отслеживать производительность и работоспособность адаптера.</span><span class="sxs-lookup"><span data-stu-id="de647-148">System Center Operations Manager 2012 would allow administrators to view network performance of individual servers through the Windows Server 2012 Management Pack: The Windows Server operating system management pack includes a "Performance" management pack that would allow administrators to monitor Network Adapter performance and adapter health.</span></span>

</div>

<div>

## <a name="windows-network-monitor"></a><span data-ttu-id="de647-149">Сетевой монитор Windows</span><span class="sxs-lookup"><span data-stu-id="de647-149">Windows Network Monitor</span></span>

<span data-ttu-id="de647-150">Собирает, отображает, анализирует использование ресурсов на сервере и измеряет сетевой трафик.</span><span class="sxs-lookup"><span data-stu-id="de647-150">Collects, displays, analyzes resource usage on a server, and measures network traffic.</span></span> <span data-ttu-id="de647-151">Сетевой монитор монопольно отслеживает активность сети.</span><span class="sxs-lookup"><span data-stu-id="de647-151">Network Monitor exclusively monitors network activity.</span></span> <span data-ttu-id="de647-152">Выполняя сбор и анализ сетевых данных, а также использование этих данных с журналами производительности, вы можете определить использование сети, определить сетевые проблемы и прогнозировать будущие потребности в сети.</span><span class="sxs-lookup"><span data-stu-id="de647-152">By capturing and analyzing network data, and using this data with performance logs, you can determine the network usage, identify network issues, and forecast future network needs.</span></span>

<span data-ttu-id="de647-153">Для получения дополнительных сведений о сетевом мониторе 3,4, а также о том, как установить и настроить сетевой монитор, а также записывать и анализировать данные, просмотрите этот сеанс: Обзор сетевого монитора 3,3.</span><span class="sxs-lookup"><span data-stu-id="de647-153">For more information about Network Monitor 3.4, and to learn how to install and configure Network Monitor and capture and analyze data, review this session: Network Monitor 3.3 Overview.</span></span> <span data-ttu-id="de647-154">Кроме того, ознакомьтесь с [блогом сетевого монитора](https://blogs.technet.com/b/netmon/).</span><span class="sxs-lookup"><span data-stu-id="de647-154">Also, review the [Network Monitor blog](https://blogs.technet.com/b/netmon/).</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

