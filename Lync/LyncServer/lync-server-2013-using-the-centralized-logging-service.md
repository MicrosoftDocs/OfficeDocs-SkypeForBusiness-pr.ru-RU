---
title: 'Lync Server 2013: использование службы централизованного ведения журналов'
description: 'Lync Server 2013: использование службы централизованного ведения журналов.'
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
ms.openlocfilehash: 3f8b9edf839de889e9f0b01c10311f6b5c70ced8
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48548525"
---
# <a name="using-the-centralized-logging-service-in-lync-server-2013"></a><span data-ttu-id="e0be9-103">Использование централизованной службы ведения журналов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e0be9-103">Using the Centralized Logging Service in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e0be9-104">_**Последнее изменение темы:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="e0be9-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="e0be9-105">Централизованная служба ведения журналов — это новая функция в Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e0be9-105">The Centralized Logging Service is a new feature in Lync Server 2013.</span></span> <span data-ttu-id="e0be9-106">Это улучшенная замена средств **OCSLogger** и **OCSTracer**, представленных в предыдущих версиях.</span><span class="sxs-lookup"><span data-stu-id="e0be9-106">It is an enhanced replacement for the **OCSLogger** and **OCSTracer** tools that were provided in previous releases.</span></span> <span data-ttu-id="e0be9-107">Службу централизованного ведения журналов можно использовать для выполнения следующих задач:</span><span class="sxs-lookup"><span data-stu-id="e0be9-107">You can use the Centralized Logging Service to perform the following tasks:</span></span>

  - <span data-ttu-id="e0be9-108">запуск ведения журнала на одном или нескольких компьютерах и в пулах из одного расположения с помощью одной команды;</span><span class="sxs-lookup"><span data-stu-id="e0be9-108">Start logging on one or more computers and pools from a single location and command.</span></span>

  - <span data-ttu-id="e0be9-109">остановка ведения журнала на одном или нескольких компьютерах и в пулах из одного расположения с помощью одной команды;</span><span class="sxs-lookup"><span data-stu-id="e0be9-109">Stop logging on one or more computers and pools from a single location and command.</span></span>

  - <span data-ttu-id="e0be9-p102">поиск в журналах на одном или нескольких компьютерах и в пулах из одного расположения с помощью одной команды. Вы можете настроить команду поиска, чтобы возвращать все журналы, записанные и сохраненные на всех компьютерах, или возвращать сокращенные результаты с определенными данными.</span><span class="sxs-lookup"><span data-stu-id="e0be9-p102">Search logs on one or more computers and pools for a single location and command. You can tailor the search command to return the entire aggregation of logs that were captured and stored on all machines, or return a trimmed-down result that captures specific data.</span></span>

  - <span data-ttu-id="e0be9-112">Настройте сеансы ведения журналов следующим образом:</span><span class="sxs-lookup"><span data-stu-id="e0be9-112">Configure logging sessions as follows:</span></span>
    
      - <span data-ttu-id="e0be9-113">Определите **сценарий** или используйте сценарий по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="e0be9-113">Define a **Scenario**, or use a default scenario.</span></span> <span data-ttu-id="e0be9-114">*Сценарий* в службе централизованного ведения журналов состоит из области (Глобальная или site), имени сценария для определения назначения сценария и одного или нескольких поставщиков.</span><span class="sxs-lookup"><span data-stu-id="e0be9-114">A *scenario* in Centralized Logging Service is made up of scope (global or site), a scenario name to identify the purpose of the scenario, and one or more providers.</span></span> <span data-ttu-id="e0be9-115">На одном компьютере одновременно можно запускать два сценария.</span><span class="sxs-lookup"><span data-stu-id="e0be9-115">You can run two scenarios at any given time on a computer.</span></span>
    
      - <span data-ttu-id="e0be9-p104">Используйте существующий *поставщик* или создайте новый. *Поставщик* определяет, что собирает сеанс ведения журналов, каков уровень детализации, какие компоненты отслеживаются и какие флаги применяются.</span><span class="sxs-lookup"><span data-stu-id="e0be9-p104">Use an existing *provider* or create a new provider. A *provider* defines what the logging session collects, what level of detail, what components to trace, and what flags are applied.</span></span>
        
        <div>
        

        > [!TIP]  
        > <span data-ttu-id="e0be9-118">Если вы знакомы с OCSLogger, термин <EM>поставщики</EM> означает коллекцию <STRONG>компонентов</STRONG> (например, S4, SIPStack), <STRONG>тип ведения журнала</STRONG> (например, WPP, EventLog или IIS logfile), <STRONG>уровень трассировки</STRONG> (например, All, verbose, debug) и <STRONG>флаги</STRONG> (например, TF_COMPONENT, TF_DIAG).</span><span class="sxs-lookup"><span data-stu-id="e0be9-118">If you are familiar with OCSLogger, the term <EM>providers</EM> refers to the collection of <STRONG>components</STRONG> (for example, S4, SIPStack), a <STRONG>logging type</STRONG> (for example, WPP, EventLog, or IIS logfile), a <STRONG>tracing level</STRONG> (for example, All, verbose, debug), and <STRONG>flags</STRONG> (for example, TF_COMPONENT, TF_DIAG).</span></span> <span data-ttu-id="e0be9-119">Эти элементы определены в поставщике (переменная Windows PowerShell) и передаются в команду централизованной службы ведения журналов.</span><span class="sxs-lookup"><span data-stu-id="e0be9-119">These items are defined in the provider (a Windows PowerShell variable) and passed into the Centralized Logging Service command.</span></span>

        
        </div>
    
      - <span data-ttu-id="e0be9-120">Настройте компьютеры и пулы, из которых вы будете собирать данные.</span><span class="sxs-lookup"><span data-stu-id="e0be9-120">Configure the computers and pools that you want to collect logs from.</span></span>
    
      - <span data-ttu-id="e0be9-121">Определите узел сеанса ведения журналов в параметрах **Узел** (сбор данных только с компьютеров в этом узле) или **Глобальный** (сбор данных со всех компьютеров в развертывании).</span><span class="sxs-lookup"><span data-stu-id="e0be9-121">Define the scope for the logging session from the options **Site** (run logging captures on computers in that site only), or **Global** (run logging capture on all computers in the deployment).</span></span>

<span data-ttu-id="e0be9-122">Централизованная служба ведения журналов является чрезвычайно мощной и может удовлетворить практически все потребности в устранении неполадок — крупный или малый.</span><span class="sxs-lookup"><span data-stu-id="e0be9-122">The Centralized Logging Service is extremely powerful and can meet nearly all of the needs for troubleshooting problems—large or small.</span></span> <span data-ttu-id="e0be9-123">Из анализа основных причин на проблемы с производительностью централизованная служба ведения журналов может быть важным средством для любого администратора.</span><span class="sxs-lookup"><span data-stu-id="e0be9-123">From root cause analysis to performance problems, the Centralized Logging Service can be an important tool for any administrator.</span></span> <span data-ttu-id="e0be9-124">Все примеры показаны с помощью командной консоли Lync Server.</span><span class="sxs-lookup"><span data-stu-id="e0be9-124">All examples are shown using the Lync Server Management Shell.</span></span> <span data-ttu-id="e0be9-125">Для централизованной службы ведения журналов под названием " **CLSController.exe**" существует компонент командной строки.</span><span class="sxs-lookup"><span data-stu-id="e0be9-125">There is a command-line component for the Centralized Logging Service called **CLSController.exe**.</span></span> <span data-ttu-id="e0be9-126">Справка для этого средства предоставлена в самом компоненте.</span><span class="sxs-lookup"><span data-stu-id="e0be9-126">Help is provided for the command-line tool through the tool itself.</span></span> <span data-ttu-id="e0be9-127">Однако из командной строки можно использовать только ограниченный набор функций.</span><span class="sxs-lookup"><span data-stu-id="e0be9-127">However, there is a limited set of functions that you can execute from the command line.</span></span> <span data-ttu-id="e0be9-128">С помощью командной консоли Lync Server вы можете получить доступ к гораздо больше настраиваемого набора функций.</span><span class="sxs-lookup"><span data-stu-id="e0be9-128">By using Lync Server Management Shell, you have access to a much larger and much more configurable set of features.</span></span> <span data-ttu-id="e0be9-129">При использовании централизованной службы ведения журналов всегда следует использовать командную консоль Lync Server в качестве первого и самого метода.</span><span class="sxs-lookup"><span data-stu-id="e0be9-129">You should always consider Lync Server Management Shell as the first and foremost method when using the Centralized Logging Service.</span></span>

<span data-ttu-id="e0be9-130">В подразделах этого раздела описывается использование централизованной службы ведения журналов и приводятся примеры того, как использовать ее многие функции.</span><span class="sxs-lookup"><span data-stu-id="e0be9-130">The topics in this section explain how to use the Centralized Logging Service and examples of how to use its many features.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="e0be9-131">Содержание</span><span class="sxs-lookup"><span data-stu-id="e0be9-131">In This Section</span></span>

  - [<span data-ttu-id="e0be9-132">Обзор централизованной службы ведения журналов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e0be9-132">Overview of the Centralized Logging Service in Lync Server 2013</span></span>](lync-server-2013-overview-of-the-centralized-logging-service.md)

  - [<span data-ttu-id="e0be9-133">Управление параметрами конфигурации централизованной службы ведения журналов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e0be9-133">Managing the Centralized Logging Service configuration settings in Lync Server 2013</span></span>](lync-server-2013-managing-the-centralized-logging-service-configuration-settings.md)

  - [<span data-ttu-id="e0be9-134">Общие сведения о параметрах конфигурации службы централизованного ведения журналов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e0be9-134">Understanding Centralized Logging Service configuration settings in Lync Server 2013</span></span>](lync-server-2013-understanding-centralized-logging-service-configuration-settings.md)

  - [<span data-ttu-id="e0be9-135">Использование Start для централизованной службы ведения журналов для захвата журналов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e0be9-135">Using Start for the Centralized Logging Service to capture logs in Lync Server 2013</span></span>](lync-server-2013-using-start-for-the-centralized-logging-service-to-capture-logs.md)

  - [<span data-ttu-id="e0be9-136">Использование Stop для централизованной службы ведения журналов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e0be9-136">Using Stop for the Centralized Logging Service in Lync Server 2013</span></span>](lync-server-2013-using-stop-for-the-centralized-logging-service.md)

  - [<span data-ttu-id="e0be9-137">Использование поиска для журналов захвата, созданных службой централизованного ведения журналов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e0be9-137">Using search on capture logs created by the Centralized Logging Service in Lync Server 2013</span></span>](lync-server-2013-using-search-on-capture-logs-created-by-the-centralized-logging-service.md)

  - [<span data-ttu-id="e0be9-138">Чтение журналов записи из службы централизованного ведения журналов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e0be9-138">Reading capture logs from the Centralized Logging Service in Lync Server 2013</span></span>](lync-server-2013-reading-capture-logs-from-the-centralized-logging-service.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

