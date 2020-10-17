---
title: 'Lync Server 2013: мониторинг операционной системы'
description: 'Lync Server 2013: мониторинг операционной системы.'
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
ms.openlocfilehash: d9454b91a5f55467f93b41752686b4b0d727d935
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48548065"
---
# <a name="monitoring-operating-system-in-lync-server-2013"></a><span data-ttu-id="12b32-103">Мониторинг операционной системы в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="12b32-103">Monitoring operating system in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="12b32-104">_**Последнее изменение темы:** 2015-01-26_</span><span class="sxs-lookup"><span data-stu-id="12b32-104">_**Topic Last Modified:** 2015-01-26_</span></span>

<span data-ttu-id="12b32-105">Необходимо следить за производительностью всех серверов и компонентов в Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="12b32-105">You must monitor the performance of all servers and components in the Lync Server 2013.</span></span> <span data-ttu-id="12b32-106">Очевидно, что одним из самых важных компонентов является сама операционная система.</span><span class="sxs-lookup"><span data-stu-id="12b32-106">Obviously, one of the most important components is the operating system itself.</span></span> <span data-ttu-id="12b32-107">Lync Server 2013 поддерживает 64-разрядные выпуски:</span><span class="sxs-lookup"><span data-stu-id="12b32-107">Lync Server 2013 supports x64 editions of:</span></span>

  - <span data-ttu-id="12b32-108">Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="12b32-108">Windows Server 2008 R2</span></span>

  - <span data-ttu-id="12b32-109">Windows Server 2012 и Windows Server 2012 R2.</span><span class="sxs-lookup"><span data-stu-id="12b32-109">Windows Server 2012 and Windows Server 2012 R2</span></span>

<span data-ttu-id="12b32-110">Самый прозрачный способ отслеживания операционной системы — использование пакета управления операционной системой Windows Server.</span><span class="sxs-lookup"><span data-stu-id="12b32-110">The most transparent way to monitor an operating system is by using Windows Server Operating System Management Pack.</span></span> <span data-ttu-id="12b32-111">Он предоставляет базовые основные сведения о мониторинге, такие как производительность, работоспособность и доступность для компьютеров под управлением Windows Server 2012, Windows Server 2012 R2 и Windows Server 2008 R2.</span><span class="sxs-lookup"><span data-stu-id="12b32-111">It provides the fundamental monitoring basics, such as performance, health, and availability for computers that are running Windows Server 2012, Windows Server 2012 R2, and Windows Server 2008 R2.</span></span>

<span data-ttu-id="12b32-112">Выполняя обнаружение, оповещение и автоматическое реагирование на важные события и индикаторы производительности, эти пакеты управления уменьшают время разрешения проблем и увеличивают общую доступность и производительность систем, работающих под управлением операционных систем Windows Server.</span><span class="sxs-lookup"><span data-stu-id="12b32-112">By detecting, alerting, and automatically responding to important events and performance indicators, these management packs reduce resolution times for issues and increase the overall availability and performance of systems that are running the Windows Server operating systems.</span></span>

<span data-ttu-id="12b32-113">Помимо соответствующих пакетов управления Windows Server для System Center Operations Manager, для наблюдения за работоспособностью операционной системы можно использовать следующие системные средства и ресурсы (в зависимости от версии операционной системы).</span><span class="sxs-lookup"><span data-stu-id="12b32-113">Apart from relevant Windows Server management packs for System Center Operations Manager, the following system tools and resources can be used to monitor the health of the operating system (depending on the operating system version).</span></span>

<div>

## <a name="windows-server2008r2"></a><span data-ttu-id="12b32-114">Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="12b32-114">Windows Server 2008 R2</span></span>

<span data-ttu-id="12b32-115">Windows Server 2008 R2 включает следующие дополнительные функции и средства, помогающие администраторам с базовой системой мониторинга и управления операционной системой.</span><span class="sxs-lookup"><span data-stu-id="12b32-115">Windows Server 2008 R2 includes the following additional features and tools to help administrators with basic operating system monitoring and management:</span></span>

  - <span data-ttu-id="12b32-116">**Монитор ресурсов Windows** — это мощное средство для понимания того, как системные ресурсы используются процессами и службами.</span><span class="sxs-lookup"><span data-stu-id="12b32-116">**Windows Resource Monitor** is a powerful tool for understanding how system resources are used by processes and services.</span></span> <span data-ttu-id="12b32-117">В дополнение к мониторингу использования ресурсов в режиме реального времени монитор ресурсов помогает анализировать процессы, которые не отвечают на запросы, определять, какие приложения используют файлы, а также управлять процессами и службами.</span><span class="sxs-lookup"><span data-stu-id="12b32-117">In addition to monitoring resource usage in real time, a Resource Monitor can help analyze unresponsive processes, identify which applications are using files, and control processes and services.</span></span>

  - <span data-ttu-id="12b32-118">**Компонент анализа надежности** — это встроенный агент, предоставляющий подробные сведения об использовании и надежности системы.</span><span class="sxs-lookup"><span data-stu-id="12b32-118">**Reliability Analysis Component** is an in-box agent that provides detailed experience information on system usage and reliability.</span></span> <span data-ttu-id="12b32-119">Эти сведения предоставляются через интерфейс WMI, чтобы сделать его доступным для использования портативными системами чтения.</span><span class="sxs-lookup"><span data-stu-id="12b32-119">This information is exposed through a WMI interface to make it available for consumption by Portable Readers Systems.</span></span> <span data-ttu-id="12b32-120">Предоставляя компонент анализа надежности с помощью интерфейса WMI, разработчики могут отслеживать и анализировать приложения, повышая надежность и производительность.</span><span class="sxs-lookup"><span data-stu-id="12b32-120">By exposing Reliability Analysis Component through a WMI interface, developers can monitor and analyze applications, increasing reliability and performance.</span></span>

  - <span data-ttu-id="12b32-121">**Windows Server 2008 R2** использует встроенный компонент анализа надежности для вычисления индекса надежности, который предоставляет сведения об общем использовании и стабильности системы с течением времени.</span><span class="sxs-lookup"><span data-stu-id="12b32-121">**Windows Server 2008 R2** uses the built-in Reliability Analysis Component to calculate a reliability index, which provides information about overall system usage and stability over time.</span></span> <span data-ttu-id="12b32-122">Компонент анализа надежности также отслеживает все важные изменения в системе, которые могут повлиять на стабильность, такие как обновления Windows и установка приложений.</span><span class="sxs-lookup"><span data-stu-id="12b32-122">The Reliability Analysis Component also keeps track of any important changes to the system that are likely to influence stability, such as Windows updates and application installations.</span></span>

</div>

<div>

## <a name="windows-server2008-windows-reliability-and-performance-monitor"></a><span data-ttu-id="12b32-123">Мониторинг надежности и производительности Windows Server 2008 Windows</span><span class="sxs-lookup"><span data-stu-id="12b32-123">Windows Server 2008 Windows Reliability and Performance Monitor</span></span>

<span data-ttu-id="12b32-124">Монитор надежности и производительности Windows — это оснастка консоли управления (MMC), которая сочетает в себе функции предыдущих автономных средств, включая журналы и оповещения производительности, советник по производительности сервера и системный монитор.</span><span class="sxs-lookup"><span data-stu-id="12b32-124">Windows Reliability and Performance Monitor is an MMC Snap-in that combines the functionality of previous stand-alone tools including Performance Logs and Alerts, Server Performance Advisor, and System Monitor.</span></span> <span data-ttu-id="12b32-125">Он предоставляет графический интерфейс для настройки сбора данных о производительности и сеансов трассировки событий.</span><span class="sxs-lookup"><span data-stu-id="12b32-125">It provides a graphical interface for customizing performance data collection and Event Trace Sessions.</span></span>

<span data-ttu-id="12b32-126">Кроме того, он также включает монитор стабильности, оснастку консоли управления (MMC), которая отслеживает изменения в системе и сравнивает их с изменениями в стабильности системы и предоставляет графическое представление их связи.</span><span class="sxs-lookup"><span data-stu-id="12b32-126">It also includes Reliability Monitor, an MMC Snap-in that tracks changes to the system and compares them to changes in system stability, and it provides a graphical view of their relationship.</span></span>

</div>

<div>

## <a name="windows-reliability-and-performance-monitor"></a><span data-ttu-id="12b32-127">Мониторинг надежности и производительности Windows</span><span class="sxs-lookup"><span data-stu-id="12b32-127">Windows Reliability and Performance Monitor</span></span>

<span data-ttu-id="12b32-128">Несмотря на то, что в мониторе стабильности и производительности Windows объединены функции некоторых прежних автономных средств, таких как журналы производительности и оповещения, а также системный монитор и советник по производительности сервера, он также предоставляет ряд новых функций для Windows Server 2008 и Windows Server 2008 R2, таких как следующие:</span><span class="sxs-lookup"><span data-stu-id="12b32-128">While Windows Reliability and Performance Monitor combine functionalities of some former stand-alone tools such as Performance Logs and Alerts, and System Monitor and Server Performance Advisor, it also provides some new functionality to Windows Server 2008 and Windows Server 2008 R2, such as the following:</span></span>

  - <span data-ttu-id="12b32-129">Группы сборщиков данных</span><span class="sxs-lookup"><span data-stu-id="12b32-129">Data Collector Sets</span></span>

  - <span data-ttu-id="12b32-130">Представление ресурсов</span><span class="sxs-lookup"><span data-stu-id="12b32-130">Resource View</span></span>

  - <span data-ttu-id="12b32-131">Монитор стабильности</span><span class="sxs-lookup"><span data-stu-id="12b32-131">Reliability Monitor</span></span>

  - <span data-ttu-id="12b32-132">Мастера и шаблоны для создания журналов</span><span class="sxs-lookup"><span data-stu-id="12b32-132">Wizards and templates for creating logs</span></span>

<span data-ttu-id="12b32-133">**Группа сборщиков данных** группирует сборщиков данных в многократно используемые элементы для использования с различными сценариями мониторинга производительности.</span><span class="sxs-lookup"><span data-stu-id="12b32-133">**Data Collector Set** groups data collectors into reusable elements for use with different performance monitoring scenarios.</span></span> <span data-ttu-id="12b32-134">После хранения группы сборщиков данных в качестве группы сборщиков данных такие операции, как планирование, можно применять ко всему набору через одно изменение свойства. Монитор производительности и стабильности Windows включает шаблоны групп сборщиков данных по умолчанию, которые помогают системным администраторам немедленно начать сбор данных о производительности, характерных для роли сервера или сценария мониторинга.</span><span class="sxs-lookup"><span data-stu-id="12b32-134">After a group of data collectors are stored as a Data Collector Set, operations such as scheduling can be applied to the whole set through a single property change.Windows Reliability and Performance Monitor includes default Data Collector Set templates to help system administrators begin immediately collecting performance data that is specific to a server role or monitoring scenario.</span></span>

<span data-ttu-id="12b32-135">Домашняя страница монитора производительности и стабильности Windows — это новый экран **представления ресурсов** , который предоставляет графический обзор ЦП, диска, сети и использования памяти в режиме реального времени.</span><span class="sxs-lookup"><span data-stu-id="12b32-135">The home page of Windows Reliability and Performance Monitor is the new **Resource View** screen, which provides a real-time graphical overview of CPU, disk, network, and memory usage.</span></span> <span data-ttu-id="12b32-136">Развернув каждый из этих отслеживаемых элементов, системные администраторы могут определить, какие именно процессы используют ресурсы.</span><span class="sxs-lookup"><span data-stu-id="12b32-136">By expanding each of these monitored elements, system administrators can identify which processes are using which resources.</span></span> <span data-ttu-id="12b32-137">В более ранних версиях Windows эти данные, зависящие от процесса, были доступны только в ограниченной форме в диспетчере задач.</span><span class="sxs-lookup"><span data-stu-id="12b32-137">In earlier versions of Windows, this real-time, process-specific data was available only in limited form in Task Manager.</span></span>

<span data-ttu-id="12b32-138">**Монитор стабильности** системы вычисляет индекс стабильности системы, отражающий снижение надежности системы при непредвиденных проблемах.</span><span class="sxs-lookup"><span data-stu-id="12b32-138">**Reliability Monitor** calculates a System Stability Index that reflects whether unexpected issues reduced the reliability of the system.</span></span> <span data-ttu-id="12b32-139">График индекса стабильности со временем быстро определяет даты, когда возникают проблемы.</span><span class="sxs-lookup"><span data-stu-id="12b32-139">A graph of the Stability Index over time quickly identifies dates when issues began to occur.</span></span> <span data-ttu-id="12b32-140">В отчете о стабильности системы представлены сведения, помогающие устранить причину снижения надежности.</span><span class="sxs-lookup"><span data-stu-id="12b32-140">The accompanying System Stability Report provides details to help troubleshoot the cause of reduced reliability.</span></span> <span data-ttu-id="12b32-141">Просматривая изменения в системе (установка или удаление приложений, обновление операционной системы или добавление или изменение драйверов) параллельно со сбоями (сбои приложений, сбои операционной системы или аппаратные сбои), можно быстро разработать стратегию решения проблем.</span><span class="sxs-lookup"><span data-stu-id="12b32-141">By viewing changes to the system (installation or removal of applications, updates to the operating system, or addition or modification of drivers) side by side with failures (application failures, operating system crashes, or hardware failures), a strategy for addressing the issues can be developed quickly.</span></span>

<span data-ttu-id="12b32-142">Добавление счетчиков в файлы журнала и планирование их запуска, остановки и длительности теперь можно выполнить с помощью **интерфейса мастера**.</span><span class="sxs-lookup"><span data-stu-id="12b32-142">Adding counters to log files and scheduling their start, stop, and duration can now be performed through a **Wizard interface**.</span></span> <span data-ttu-id="12b32-143">Кроме того, сохранение этой конфигурации в качестве шаблона позволяет системным администраторам собирать один и тот же журнал на других компьютерах без повторения выбора и планирования сборщиков данных.</span><span class="sxs-lookup"><span data-stu-id="12b32-143">In addition, saving this configuration as a template enables system administrators to collect the same log on other computers without repeating the data collector selection and scheduling processes.</span></span> <span data-ttu-id="12b32-144">Функции журналов и оповещений производительности были включены в монитор надежности и производительности Windows для использования с любой группой сборщиков данных.</span><span class="sxs-lookup"><span data-stu-id="12b32-144">Performance Logs and Alerts features were incorporated into the Windows Reliability and Performance Monitor for use with any Data Collector Set.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

