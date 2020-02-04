---
title: 'Lync Server 2013: мониторинг операционной системы'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Monitoring operating system
ms:assetid: 72406d3e-54c8-4796-8d6d-2144a5b6f030
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720918(v=OCS.15)
ms:contentKeyID: 63969617
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 42ac03f61fca5717d279d39e703a8ffa97e8c2cf
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756793"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="monitoring-operating-system-in-lync-server-2013"></a><span data-ttu-id="5daee-102">Мониторинг операционной системы в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5daee-102">Monitoring operating system in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5daee-103">_**Тема последнего изменения:** 2015-01-26_</span><span class="sxs-lookup"><span data-stu-id="5daee-103">_**Topic Last Modified:** 2015-01-26_</span></span>

<span data-ttu-id="5daee-104">Необходимо следить за производительностью всех серверов и компонентов в Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5daee-104">You must monitor the performance of all servers and components in the Lync Server 2013.</span></span> <span data-ttu-id="5daee-105">Очевидно, что самыми важными компонентами является сама операционная система.</span><span class="sxs-lookup"><span data-stu-id="5daee-105">Obviously, one of the most important components is the operating system itself.</span></span> <span data-ttu-id="5daee-106">Lync Server 2013 поддерживает 64-разрядные версии:</span><span class="sxs-lookup"><span data-stu-id="5daee-106">Lync Server 2013 supports x64 editions of:</span></span>

  - <span data-ttu-id="5daee-107">Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="5daee-107">Windows Server 2008 R2</span></span>

  - <span data-ttu-id="5daee-108">Windows Server 2012 и Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="5daee-108">Windows Server 2012 and Windows Server 2012 R2</span></span>

<span data-ttu-id="5daee-109">Наиболее прозрачный способ наблюдения за операционной системой — это использование пакета управления операционной системой Windows Server.</span><span class="sxs-lookup"><span data-stu-id="5daee-109">The most transparent way to monitor an operating system is by using Windows Server Operating System Management Pack.</span></span> <span data-ttu-id="5daee-110">Он обеспечивает основные основы наблюдения, такие как производительность, работоспособность и доступность для компьютеров под управлением Windows Server 2012, Windows Server 2012 R2 и Windows Server 2008 R2.</span><span class="sxs-lookup"><span data-stu-id="5daee-110">It provides the fundamental monitoring basics, such as performance, health, and availability for computers that are running Windows Server 2012, Windows Server 2012 R2, and Windows Server 2008 R2.</span></span>

<span data-ttu-id="5daee-111">Выполняя, уведомляя и автоматически реагируя на важные события и индикаторы производительности, эти пакеты управления уменьшают значения времени разрешения проблем и увеличивают общую доступность и производительность систем под управлением Windows Server. операционные системы.</span><span class="sxs-lookup"><span data-stu-id="5daee-111">By detecting, alerting, and automatically responding to important events and performance indicators, these management packs reduce resolution times for issues and increase the overall availability and performance of systems that are running the Windows Server operating systems.</span></span>

<span data-ttu-id="5daee-112">Помимо необходимых пакетов управления Windows Server для System Center Operations Manager, для наблюдения за работоспособностью операционной системы (в зависимости от версии операционной системы) можно использовать следующие служебные программы и ресурсы.</span><span class="sxs-lookup"><span data-stu-id="5daee-112">Apart from relevant Windows Server management packs for System Center Operations Manager, the following system tools and resources can be used to monitor the health of the operating system (depending on the operating system version).</span></span>

<div>

## <a name="windows-server2008r2"></a><span data-ttu-id="5daee-113">Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="5daee-113">Windows Server 2008 R2</span></span>

<span data-ttu-id="5daee-114">В Windows Server 2008 R2 включены следующие дополнительные возможности и средства, помогающие администраторам в основном контроле и управлении операционной системой.</span><span class="sxs-lookup"><span data-stu-id="5daee-114">Windows Server 2008 R2 includes the following additional features and tools to help administrators with basic operating system monitoring and management:</span></span>

  - <span data-ttu-id="5daee-p103">**Мониторинг ресурсов Windows** является мощным инструментом для понимания того, как процессы и службы используют системные ресурсы. В дополнение к отслеживанию использования ресурсов в режиме реального времени мониторинг ресурсов помогает в анализе неотвечающих процессов, определении использующих файл приложений, а также контроле процессов и служб.</span><span class="sxs-lookup"><span data-stu-id="5daee-p103">**Windows Resource Monitor** is a powerful tool for understanding how system resources are used by processes and services. In addition to monitoring resource usage in real time, a Resource Monitor can help analyze unresponsive processes, identify which applications are using files, and control processes and services.</span></span>

  - <span data-ttu-id="5daee-p104">**Компонент анализа надежности** является встроенным агентом, который предоставляет подробную информацию о взаимодействии в рамках использования и надежности системы. Данная информация раскрывается посредством интерфейса WMI с целью предоставления доступности для процесса потребления с помощью систем портативного считывания. Воздействуя на компонент анализа надежности с помощью интерфейса WMI, разработчики могут выполнять мониторинг и анализ приложений при одновременном повышении уровня надежности и производительности.</span><span class="sxs-lookup"><span data-stu-id="5daee-p104">**Reliability Analysis Component** is an in-box agent that provides detailed experience information on system usage and reliability. This information is exposed through a WMI interface to make it available for consumption by Portable Readers Systems. By exposing Reliability Analysis Component through a WMI interface, developers can monitor and analyze applications, increasing reliability and performance.</span></span>

  - <span data-ttu-id="5daee-120">**Windows Server 2008 R2** использует встроенный компонент анализа надежности для вычисления индекса надежности, который предоставляет сведения об общем использовании системы и стабильности в течение определенного времени.</span><span class="sxs-lookup"><span data-stu-id="5daee-120">**Windows Server 2008 R2** uses the built-in Reliability Analysis Component to calculate a reliability index, which provides information about overall system usage and stability over time.</span></span> <span data-ttu-id="5daee-121">The Reliability Analysis Component also keeps track of any important changes to the system that are likely to influence stability, such as Windows updates and application installations.</span><span class="sxs-lookup"><span data-stu-id="5daee-121">The Reliability Analysis Component also keeps track of any important changes to the system that are likely to influence stability, such as Windows updates and application installations.</span></span>

</div>

<div>

## <a name="windows-server2008-windows-reliability-and-performance-monitor"></a><span data-ttu-id="5daee-122">Монитор надежности и производительности Windows Server 2008</span><span class="sxs-lookup"><span data-stu-id="5daee-122">Windows Server 2008 Windows Reliability and Performance Monitor</span></span>

<span data-ttu-id="5daee-p106">Мониторинг надежности и производительности Windows является оснасткой MMC, которая объединяет в себе возможности предыдущих автономных инструментов, включая журналы и оповещения о производительности, советника по производительности сервера и мониторинг системы. Также предоставляет графический интерфейс для настройки сбора данных производительности и сеансов трассировки событий.</span><span class="sxs-lookup"><span data-stu-id="5daee-p106">Windows Reliability and Performance Monitor is an MMC Snap-in that combines the functionality of previous stand-alone tools including Performance Logs and Alerts, Server Performance Advisor, and System Monitor. It provides a graphical interface for customizing performance data collection and Event Trace Sessions.</span></span>

<span data-ttu-id="5daee-125">Функциональность также включает в себя мониторинг надежности, оснастку MMC, которая отслеживает изменения в системе и сравнивает их в рамках системной надежности, и предоставляет графический вид данных связей.</span><span class="sxs-lookup"><span data-stu-id="5daee-125">It also includes Reliability Monitor, an MMC Snap-in that tracks changes to the system and compares them to changes in system stability, and it provides a graphical view of their relationship.</span></span>

</div>

<div>

## <a name="windows-reliability-and-performance-monitor"></a><span data-ttu-id="5daee-126">Мониторинг надежности и производительности Windows</span><span class="sxs-lookup"><span data-stu-id="5daee-126">Windows Reliability and Performance Monitor</span></span>

<span data-ttu-id="5daee-127">Несмотря на то, что монитор стабильности и производительности сочетает в себе функциональные возможности некоторых оригинальных автономных инструментов, таких как журналы производительности и оповещения, а также системный монитор и советник по производительности сервера, он предоставляет новые функции для Windows Server 2008 и Windows Server 2008 R2, например:</span><span class="sxs-lookup"><span data-stu-id="5daee-127">While Windows Reliability and Performance Monitor combine functionalities of some former stand-alone tools such as Performance Logs and Alerts, and System Monitor and Server Performance Advisor, it also provides some new functionality to Windows Server 2008 and Windows Server 2008 R2, such as the following:</span></span>

  - <span data-ttu-id="5daee-128">Наборы сборщика данных</span><span class="sxs-lookup"><span data-stu-id="5daee-128">Data Collector Sets</span></span>

  - <span data-ttu-id="5daee-129">Обзор ресурсов</span><span class="sxs-lookup"><span data-stu-id="5daee-129">Resource View</span></span>

  - <span data-ttu-id="5daee-130">Мониторинг надежности</span><span class="sxs-lookup"><span data-stu-id="5daee-130">Reliability Monitor</span></span>

  - <span data-ttu-id="5daee-131">Мастера и шаблоны для создания журналов</span><span class="sxs-lookup"><span data-stu-id="5daee-131">Wizards and templates for creating logs</span></span>

<span data-ttu-id="5daee-p107">**Набор сборщика данных** группирует сборщиков данных в повторно используемые элементы для применения в разных сценариях мониторинга производительности. После сохранения группы сборщиков данных как набора сборщика данных операции, такие как планирование, могут быть применены ко всему набору через изменение одного свойства. Мониторинг надежности и производительности Windows содержит стандартные шаблоны набора сборщика данных для помощи системным администраторам в незамедлительном начале сбора данных производительности, которые характерны для серверной роли или сценария мониторинга.</span><span class="sxs-lookup"><span data-stu-id="5daee-p107">**Data Collector Set** groups data collectors into reusable elements for use with different performance monitoring scenarios. After a group of data collectors are stored as a Data Collector Set, operations such as scheduling can be applied to the whole set through a single property change.Windows Reliability and Performance Monitor includes default Data Collector Set templates to help system administrators begin immediately collecting performance data that is specific to a server role or monitoring scenario.</span></span>

<span data-ttu-id="5daee-p108">Главная страница мониторинга надежности и производительности Windows является новым экраном **обзора ресурсов**, на котором представлен графический обзор ЦП в режиме реального времени, дисков, сети и использования памяти. Разворачивая каждый из этих отслеживаемых элементов, системные администраторы могут определить процессы, которые используют определенные ресурсы. В более ранних версиях Windows эти характерные для процесса текущие данные были доступны только в ограниченной форме в диспетчере задач.</span><span class="sxs-lookup"><span data-stu-id="5daee-p108">The home page of Windows Reliability and Performance Monitor is the new **Resource View** screen, which provides a real-time graphical overview of CPU, disk, network, and memory usage. By expanding each of these monitored elements, system administrators can identify which processes are using which resources. In earlier versions of Windows, this real-time, process-specific data was available only in limited form in Task Manager.</span></span>

<span data-ttu-id="5daee-p109">**Мониторинг надежности** вычисляет индекс стабильности системы, который отражает, понизили ли непредвиденные проблемы уровень надежности системы. График индекса стабильности со временем быстро определяет данные при возникновении проблем. Сопутствующий отчет о стабильности системы предоставляет сведения для устранения причин понижения уровня надежности. С помощью просмотра изменений в системе (установка или удаление приложений, обновлений ОС, добавления или изменения драйверов) совместно со сбоями в работе (ошибки приложений, сбои ОС или аппаратные сбои) можно быстро разработать стратегию по решению данных неполадок.</span><span class="sxs-lookup"><span data-stu-id="5daee-p109">**Reliability Monitor** calculates a System Stability Index that reflects whether unexpected issues reduced the reliability of the system. A graph of the Stability Index over time quickly identifies dates when issues began to occur. The accompanying System Stability Report provides details to help troubleshoot the cause of reduced reliability. By viewing changes to the system (installation or removal of applications, updates to the operating system, or addition or modification of drivers) side by side with failures (application failures, operating system crashes, or hardware failures), a strategy for addressing the issues can be developed quickly.</span></span>

<span data-ttu-id="5daee-p110">Добавление счетчиков в файлы журнала и планирование их запуска, остановки или длительности теперь можно выполнять с помощью **интерфейса мастера**. Кроме того, сохранение данной конфигурации как шаблона позволяет системным администраторам собирать один и тот же журнал на других компьютерах без повторения выбора сборщика данных и процессов планирования. Возможности журналов производительности и оповещений были встроены в мониторинг надежности и производительности Windows для использования с любым сборщиком данных.</span><span class="sxs-lookup"><span data-stu-id="5daee-p110">Adding counters to log files and scheduling their start, stop, and duration can now be performed through a **Wizard interface**. In addition, saving this configuration as a template enables system administrators to collect the same log on other computers without repeating the data collector selection and scheduling processes. Performance Logs and Alerts features were incorporated into the Windows Reliability and Performance Monitor for use with any Data Collector Set.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

