---
title: 'Lync Server 2013: использование централизованной службы ведения журналов'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using the Centralized Logging Service
ms:assetid: 7b05aaef-f0ea-4649-ba8a-02e68b0cdf23
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688101(v=OCS.15)
ms:contentKeyID: 49733700
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2fb3687d036f7d72160c8af0e168a40d09c84e4b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41743979"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-the-centralized-logging-service-in-lync-server-2013"></a><span data-ttu-id="1b50d-102">Использование централизованной службы ведения журналов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1b50d-102">Using the Centralized Logging Service in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1b50d-103">_**Тема последнего изменения:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="1b50d-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="1b50d-104">Служба централизованного ведения журналов — это новая функция в Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1b50d-104">The Centralized Logging Service is a new feature in Lync Server 2013.</span></span> <span data-ttu-id="1b50d-105">Это улучшенная замена средств **окслогжер** и **окстрацер** , которые были указаны в предыдущих выпусках.</span><span class="sxs-lookup"><span data-stu-id="1b50d-105">It is an enhanced replacement for the **OCSLogger** and **OCSTracer** tools that were provided in previous releases.</span></span> <span data-ttu-id="1b50d-106">С помощью централизованной службы ведения журнала можно выполнять следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="1b50d-106">You can use the Centralized Logging Service to perform the following tasks:</span></span>

  - <span data-ttu-id="1b50d-107">Начните вести вход на одном или нескольких компьютерах и пулах из одного места и из одной команды.</span><span class="sxs-lookup"><span data-stu-id="1b50d-107">Start logging on one or more computers and pools from a single location and command.</span></span>

  - <span data-ttu-id="1b50d-108">Прекращение ведения журнала на одном или нескольких компьютерах и пулах из одного места и команды.</span><span class="sxs-lookup"><span data-stu-id="1b50d-108">Stop logging on one or more computers and pools from a single location and command.</span></span>

  - <span data-ttu-id="1b50d-109">Поиск в журналах на одном или нескольких компьютерах и пулах для одного места и команды.</span><span class="sxs-lookup"><span data-stu-id="1b50d-109">Search logs on one or more computers and pools for a single location and command.</span></span> <span data-ttu-id="1b50d-110">Вы можете настроить команду поиска так, чтобы она возвращала все агрегированные журналы, которые были собраны и сохранены на всех компьютерах, или вернуть сокращенные результаты, которые захватывают определенные данные.</span><span class="sxs-lookup"><span data-stu-id="1b50d-110">You can tailor the search command to return the entire aggregation of logs that were captured and stored on all machines, or return a trimmed-down result that captures specific data.</span></span>

  - <span data-ttu-id="1b50d-111">Настройте сеансы ведения журналов следующим образом:</span><span class="sxs-lookup"><span data-stu-id="1b50d-111">Configure logging sessions as follows:</span></span>
    
      - <span data-ttu-id="1b50d-112">Define a **Scenario**, or use a default scenario.</span><span class="sxs-lookup"><span data-stu-id="1b50d-112">Define a **Scenario**, or use a default scenario.</span></span> <span data-ttu-id="1b50d-113">*Сценарий* централизованной службы ведения журнала состоит из области охвата (Global или site), имени сценария для идентификации назначения сценария и одного или нескольких поставщиков.</span><span class="sxs-lookup"><span data-stu-id="1b50d-113">A *scenario* in Centralized Logging Service is made up of scope (global or site), a scenario name to identify the purpose of the scenario, and one or more providers.</span></span> <span data-ttu-id="1b50d-114">Вы можете запускать два сценария в любой момент на компьютере.</span><span class="sxs-lookup"><span data-stu-id="1b50d-114">You can run two scenarios at any given time on a computer.</span></span>
    
      - <span data-ttu-id="1b50d-p104">Используйте существующего *поставщика* или создайте нового. *Поставщик* определяет, что собирает сеанс ведения журналов, каков уровень детализации, какие компоненты отслеживаются и какие флаги применяются.</span><span class="sxs-lookup"><span data-stu-id="1b50d-p104">Use an existing *provider* or create a new provider. A *provider* defines what the logging session collects, what level of detail, what components to trace, and what flags are applied.</span></span>
        
        <div>
        

        > [!TIP]  
        > <span data-ttu-id="1b50d-117">If you are familiar with OCSLogger, the term <EM>providers</EM> refers to the collection of <STRONG>components</STRONG> (for example, S4, SIPStack), a <STRONG>logging type</STRONG> (for example, WPP, EventLog, or IIS logfile), a <STRONG>tracing level</STRONG> (for example, All, verbose, debug), and <STRONG>flags</STRONG> (for example, TF_COMPONENT, TF_DIAG).</span><span class="sxs-lookup"><span data-stu-id="1b50d-117">If you are familiar with OCSLogger, the term <EM>providers</EM> refers to the collection of <STRONG>components</STRONG> (for example, S4, SIPStack), a <STRONG>logging type</STRONG> (for example, WPP, EventLog, or IIS logfile), a <STRONG>tracing level</STRONG> (for example, All, verbose, debug), and <STRONG>flags</STRONG> (for example, TF_COMPONENT, TF_DIAG).</span></span> <span data-ttu-id="1b50d-118">Эти элементы определяются в поставщике (переменной Windows PowerShell) и передаются команде централизованной службы ведения журнала.</span><span class="sxs-lookup"><span data-stu-id="1b50d-118">These items are defined in the provider (a Windows PowerShell variable) and passed into the Centralized Logging Service command.</span></span>

        
        </div>
    
      - <span data-ttu-id="1b50d-119">Настройте компьютеры и пулы, из которых вы хотите собирать журналы.</span><span class="sxs-lookup"><span data-stu-id="1b50d-119">Configure the computers and pools that you want to collect logs from.</span></span>
    
      - <span data-ttu-id="1b50d-120">Определите область для сеанса ведения журнала на **сайте** параметров (ведение журнала для всех компьютеров только на этом сайте) или **Global** (выполните ведение журнала на всех компьютерах в развертывании).</span><span class="sxs-lookup"><span data-stu-id="1b50d-120">Define the scope for the logging session from the options **Site** (run logging captures on computers in that site only), or **Global** (run logging capture on all computers in the deployment).</span></span>

<span data-ttu-id="1b50d-121">Централизованная служба ведения журнала является чрезвычайно мощной и может значительно отвечать за проблемы, возникающие при устранении неполадок — крупный или малый.</span><span class="sxs-lookup"><span data-stu-id="1b50d-121">The Centralized Logging Service is extremely powerful and can meet nearly all of the needs for troubleshooting problems—large or small.</span></span> <span data-ttu-id="1b50d-122">После анализа корневой причины проблем с производительностью централизованная служба ведения журналов может быть важным инструментом для любого администратора.</span><span class="sxs-lookup"><span data-stu-id="1b50d-122">From root cause analysis to performance problems, the Centralized Logging Service can be an important tool for any administrator.</span></span> <span data-ttu-id="1b50d-123">Все примеры отображаются в командной консоли Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="1b50d-123">All examples are shown using the Lync Server Management Shell.</span></span> <span data-ttu-id="1b50d-124">Для централизованной службы ведения журналов под названием **клсконтроллер. exe**есть компонент командной строки.</span><span class="sxs-lookup"><span data-stu-id="1b50d-124">There is a command-line component for the Centralized Logging Service called **CLSController.exe**.</span></span> <span data-ttu-id="1b50d-125">Справка предоставляется для средства командной строки с помощью самого инструмента.</span><span class="sxs-lookup"><span data-stu-id="1b50d-125">Help is provided for the command-line tool through the tool itself.</span></span> <span data-ttu-id="1b50d-126">Тем не менее, в командной строке можно выполнить ограниченный набор функций.</span><span class="sxs-lookup"><span data-stu-id="1b50d-126">However, there is a limited set of functions that you can execute from the command line.</span></span> <span data-ttu-id="1b50d-127">С помощью командной консоли Lync Server вы можете получить доступ к гораздо большему и более настраиваемому набору функций.</span><span class="sxs-lookup"><span data-stu-id="1b50d-127">By using Lync Server Management Shell, you have access to a much larger and much more configurable set of features.</span></span> <span data-ttu-id="1b50d-128">При использовании централизованной службы ведения журналов следует использовать командную консоль Lync Server в качестве первой и самой основной функции.</span><span class="sxs-lookup"><span data-stu-id="1b50d-128">You should always consider Lync Server Management Shell as the first and foremost method when using the Centralized Logging Service.</span></span>

<span data-ttu-id="1b50d-129">В этом разделе объясняется, как использовать централизованную службу ведения журналов и примеры того, как пользоваться ее многими функциями.</span><span class="sxs-lookup"><span data-stu-id="1b50d-129">The topics in this section explain how to use the Centralized Logging Service and examples of how to use its many features.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="1b50d-130">Содержание</span><span class="sxs-lookup"><span data-stu-id="1b50d-130">In This Section</span></span>

  - [<span data-ttu-id="1b50d-131">Общие сведения об централизованной службе ведения журналов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1b50d-131">Overview of the Centralized Logging Service in Lync Server 2013</span></span>](lync-server-2013-overview-of-the-centralized-logging-service.md)

  - [<span data-ttu-id="1b50d-132">Управление централизованными параметрами конфигурации службы ведения журналов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1b50d-132">Managing the Centralized Logging Service configuration settings in Lync Server 2013</span></span>](lync-server-2013-managing-the-centralized-logging-service-configuration-settings.md)

  - [<span data-ttu-id="1b50d-133">Общие сведения о централизованных параметрах конфигурации службы ведения журналов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1b50d-133">Understanding Centralized Logging Service configuration settings in Lync Server 2013</span></span>](lync-server-2013-understanding-centralized-logging-service-configuration-settings.md)

  - [<span data-ttu-id="1b50d-134">Использование команды Start для централизованной службы ведения журналов для захвата журналов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1b50d-134">Using Start for the Centralized Logging Service to capture logs in Lync Server 2013</span></span>](lync-server-2013-using-start-for-the-centralized-logging-service-to-capture-logs.md)

  - [<span data-ttu-id="1b50d-135">Использование функции "остановить" для централизованной службы ведения журналов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1b50d-135">Using Stop for the Centralized Logging Service in Lync Server 2013</span></span>](lync-server-2013-using-stop-for-the-centralized-logging-service.md)

  - [<span data-ttu-id="1b50d-136">Использование функции поиска в журналах захвата, созданных службой централизованного ведения журналов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1b50d-136">Using search on capture logs created by the Centralized Logging Service in Lync Server 2013</span></span>](lync-server-2013-using-search-on-capture-logs-created-by-the-centralized-logging-service.md)

  - [<span data-ttu-id="1b50d-137">Чтение журналов захвата из службы централизованного ведения журналов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1b50d-137">Reading capture logs from the Centralized Logging Service in Lync Server 2013</span></span>](lync-server-2013-reading-capture-logs-from-the-centralized-logging-service.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

