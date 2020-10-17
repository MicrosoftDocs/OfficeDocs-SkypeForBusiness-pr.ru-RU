---
title: Использование поиска для журналов захвата, созданных службой централизованного ведения журналов
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using search on capture logs created by the Centralized Logging Service
ms:assetid: 1b75b218-d84f-47a7-8a0a-b7e016b1cc79
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687982(v=OCS.15)
ms:contentKeyID: 49733571
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b054f3ea8a1054be1e920fbbacbfe2e88b157ba7
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48518766"
---
# <a name="using-search-on-capture-logs-created-by-the-centralized-logging-service-in-lync-server-2013"></a><span data-ttu-id="64bea-102">Использование поиска для журналов захвата, созданных службой централизованного ведения журналов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="64bea-102">Using search on capture logs created by the Centralized Logging Service in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="64bea-103">_**Последнее изменение темы:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="64bea-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="64bea-104">Функции поиска в централизованной службе ведения журналов полезны и являются мощными по следующим причинам:</span><span class="sxs-lookup"><span data-stu-id="64bea-104">The search features in the Centralized Logging Service are useful and powerful for the following reasons:</span></span>

  - <span data-ttu-id="64bea-105">Процесс и результаты поиска выполняются на одном компьютере, в пуле, на сайте или в глобальной области в зависимости от заданных критериев.</span><span class="sxs-lookup"><span data-stu-id="64bea-105">Your searches and the results are run on a single computer, a pool, a site, or a global scope, based on the criteria you define.</span></span>

  - <span data-ttu-id="64bea-p101">Поиск может изначально выполняться в широком диапазоне с последующим уточнением до более узких критериев (время, компонент или компьютер). Поиск выполняется по тем же журналам, и запуск сеанса ведения журнала при изменении условий поиска не требуется.</span><span class="sxs-lookup"><span data-stu-id="64bea-p101">Your searches can be initially broad and then narrowed down to more targeted criteria such as time, component, or computer. You search against the same logs and don’t need to run a logging session again when the search criteria changes.</span></span>

  - <span data-ttu-id="64bea-p102">Выполняется сбор результатов поиска со всех компьютеров и из пулов в области, создание коллекции и объединение результатов поисков в единый файл вывода, представляющий результаты использования условий поиска (с ограничением до выполняемых сценариев и данных, получаемых сценариями). При этом для чтения файла вывода и сообщений трассировки во всей среде используется хорошо знакомый инструмент (например, **Snooper** или **Блокнот**).</span><span class="sxs-lookup"><span data-stu-id="64bea-p102">The results of your search are gathered from all computers and pools in the scope, collected and aggregated into a single output file that represents all results of the search criteria (limited to the scenarios that have been running and the data captured by the scenarios). You use familiar tools such as **Snooper** or **Notepad** to read the output file and the trace messages from across your deployment.</span></span>

<span data-ttu-id="64bea-p103">CLSAgent на каждом отдельном компьютере создает журналы в соответствии со сценарием или сценариями (в любое время на компьютере можно выполнять одновременно два сценария). Управление журналами и связанными с ними файлы индекса и кэша осуществляется посредством CLSAgent. При определении критериев и выполнении поиска команда поиска сообщает CLSAgent, какие данные требуется получить. CLSAgent направляет запрос в файлы журнала, кэша и индекса и возвращает результаты поиска в CLSContoller. CLSController получает результаты поиска от всех компьютеров и объединяет их в пул в области поиска. Затем CLSController объединяет журналы и помещает их в порядке изменения времени (первыми идут самые старые записи, последними - самые новые).</span><span class="sxs-lookup"><span data-stu-id="64bea-p103">The CLSAgent on each individual computer creates the logs based on the scenario or scenarios (two scenarios per computer can be running at any given time). The logs and their associated index and cache files are managed by the CLSAgent. When you define and execute a search, the search command instructs the CLSAgent on what information should be retrieved. The CLSAgent executes the query against the log files, cache files, and index files and returns the results of the search to the CLSContoller. The CLSController receives the search results from all computers and pools in the scope of the search. The CLSController then aggregates (combines) the logs and puts them into time delta order, oldest entry first, and proceeding in time to the most recent entry last.</span></span>

<span data-ttu-id="64bea-116">После каждой операции поиска запускается командлет **Sync-CsClsLogging**, который выполняет очистку кэша, используемого операциями поиска (не следует путать с файлами кэша, обслуживаемыми CLSAgent).</span><span class="sxs-lookup"><span data-stu-id="64bea-116">After each search, the **Sync-CsClsLogging** cmdlet is run and it flushes the cache used by searches (not to be confused with the cache files maintained by the CLSAgent).</span></span> <span data-ttu-id="64bea-117">Очистка кэша позволяет убедиться в том, что журнал и буфер записи файлов трассировки в CLSController свободны для следующей операции поиска.</span><span class="sxs-lookup"><span data-stu-id="64bea-117">Flushing the cache helps to ensure that there is a clean log and trace file capture buffer at the CLSController for the next search operation.</span></span>

<span data-ttu-id="64bea-118">Чтобы получить наибольшую пользу от централизованной службы ведения журналов, необходимо хорошо понимать, как настроить поиск, чтобы возвратить только сообщения трассировки из журналов компьютера и пула, которые относятся к возникшей ошибке.</span><span class="sxs-lookup"><span data-stu-id="64bea-118">To get the most benefit from the Centralized Logging Service, you need a good understanding of how to configure search to return only trace messages from the computer and pool logs that are relevant to the issue that you are researching.</span></span> <span data-ttu-id="64bea-119">ошибки</span><span class="sxs-lookup"><span data-stu-id="64bea-119">issues</span></span>

<span data-ttu-id="64bea-120">Чтобы запустить функции Службы централизованного ведения журналов с помощью командной консоли Lync Server, необходимо быть членом группы безопасности CsAdministrator или CsServerAdministrator с контролем на основе ролей (RBAC) или настраиваемой ролью RBAC, которая содержит любую из этих двух групп.</span><span class="sxs-lookup"><span data-stu-id="64bea-120">To run the Centralized Logging Service search functions by using the Lync Server Management Shell, you must be a member of either the CsAdministrator or the CsServerAdministrator role-based access control (RBAC) security groups, or a custom RBAC role that contains either of these two groups.</span></span> <span data-ttu-id="64bea-121">Чтобы получить список всех ролей RBAC, которым назначен этот командлет (включая все самостоятельно созданные роли RBAC), выполните следующую команду в командной консоли Lync Server или в командной строке Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="64bea-121">To return a list of all the RBAC roles that this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Lync Server Management Shell or the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Lync Server 2013 cmdlet"}

<span data-ttu-id="64bea-122">Пример:</span><span class="sxs-lookup"><span data-stu-id="64bea-122">For example:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}

<span data-ttu-id="64bea-123">Остальная часть данного раздела посвящена способам определения критериев поиска в целях оптимизации диагностики.</span><span class="sxs-lookup"><span data-stu-id="64bea-123">The remainder of this topic focuses on how to define a search to optimize your troubleshooting.</span></span>

<div>

## <a name="to-run-a-basic-search-by-using-the-centralized-logging-service"></a><span data-ttu-id="64bea-124">Выполнение базового поиска с помощью централизованной службы ведения журналов</span><span class="sxs-lookup"><span data-stu-id="64bea-124">To run a basic search by using the Centralized Logging Service</span></span>

1.  <span data-ttu-id="64bea-125">Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="64bea-125">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="64bea-126">Убедитесь в том, что в глобальной области среды выполняется сценарий AlwaysOn, после чего введите в командной строке следующее:</span><span class="sxs-lookup"><span data-stu-id="64bea-126">Make sure that you have the AlwaysOn scenario running in your deployment at the global scope and then type the following at a command prompt:</span></span>
    
        Search-CsClsLogging -OutputFilePath <string value of path and file to write the output file>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="64bea-127">По умолчанию Search-CsClsLogging отправляет результаты поиска на консоль.</span><span class="sxs-lookup"><span data-stu-id="64bea-127">By default, Search-CsClsLogging sends the results of the search to the console.</span></span> <span data-ttu-id="64bea-128">Если вы хотите сохранить результаты поиска в файл, используйте параметр – OutputFilePath &lt; String полностью полный путь к файлу &gt; .</span><span class="sxs-lookup"><span data-stu-id="64bea-128">If you want to save the search results to a file, use –OutputFilePath &lt;string fully qualified file path&gt;.</span></span> <span data-ttu-id="64bea-129">Чтобы определить параметр –OutputFilePath, необходимо указать в параметре путь и имя файла в строковом формате и в кавычках (например: C:\LogFiles\SearchOutput.txt).</span><span class="sxs-lookup"><span data-stu-id="64bea-129">To define the –OutputFilePath parameter, supply a path and a filename as part of the parameter in a string format enclosed in quotation marks (for example; C:\LogFiles\SearchOutput.txt).</span></span> <span data-ttu-id="64bea-130">В этом примере необходимо убедиться в том, что каталог C:\LogFiles существует, и у вас есть разрешения для чтения и записи файлов в этот каталог (разрешение NTFS Modify).</span><span class="sxs-lookup"><span data-stu-id="64bea-130">In this example, you must ensure that the directory C:\LogFiles exists and that you have permissions to Read and Write (NTFS permission Modify) files in the folder.</span></span> <span data-ttu-id="64bea-131">Выполняется добавление выходных данных, но не их перезапись.</span><span class="sxs-lookup"><span data-stu-id="64bea-131">The output is appended to and is not overwritten.</span></span> <span data-ttu-id="64bea-132">Чтобы создать отдельные файлы, определите уникально идентифицируемое имя файлы для каждой операции поиска.</span><span class="sxs-lookup"><span data-stu-id="64bea-132">If you need separate files, define a distinct file name for each search.</span></span>

    
    </div>
    
    <span data-ttu-id="64bea-133">Пример:</span><span class="sxs-lookup"><span data-stu-id="64bea-133">For example:</span></span>
    
        Search-CsClsLogging -OutputFilePath "C:\LogFiles\logfile.txt"

</div>

<div>

## <a name="to-run-a-basic-search-on-a-pool-or-computer-by-using-the-centralized-logging-service"></a><span data-ttu-id="64bea-134">Выполнение базового поиска для пула или компьютера с помощью централизованной службы ведения журналов</span><span class="sxs-lookup"><span data-stu-id="64bea-134">To run a basic search on a pool or computer by using the Centralized Logging Service</span></span>

1.  <span data-ttu-id="64bea-135">Чтобы ограничить область поиска конкретным пулом или компьютером, используется параметр –Computers, в котором компьютер определяется полным именем, заключенным в кавычки, с разделением запятыми:</span><span class="sxs-lookup"><span data-stu-id="64bea-135">To limit the search to a specific pool or computer, use the –Computers parameter with the computer defined by a computer fully qualified name, enclosed in quotation marks and separated by a comma as follows:</span></span>
    
        Search-CsClsLogging -Computers <string value of computer names> -OutputFilePath <string value of path and file to write the output file>
    
    <span data-ttu-id="64bea-136">Пример:</span><span class="sxs-lookup"><span data-stu-id="64bea-136">For example:</span></span>
    
        Search-CsClsLogging -Computers "fe01.contoso.net" -OutputFilePath "C:\LogFiles\logfile.txt"

2.  <span data-ttu-id="64bea-137">Чтобы выполнить поиск по нескольким компьютерам, введите несколько имен компьютеров в кавычках с разделением запятыми. Например:</span><span class="sxs-lookup"><span data-stu-id="64bea-137">To search more than one computer, type multiple computer names enclosed in quotation marks and separated by commas, such as the following:</span></span>
    
        Search-CsClsLogging -Computers "fe01.contoso.net", "fe02.contoso.net", "fe03.contoso.net" -OutputFilePath "C:\LogFiles\logfile.txt"

3.  <span data-ttu-id="64bea-138">Чтобы выполнить поиск по всему пулу, а не по одному компьютеру, измените параметр –Computers на –Pools, удалите имя компьютера и замените его на имя пула или пулов в кавычках с разделением запятыми.</span><span class="sxs-lookup"><span data-stu-id="64bea-138">If you need to search an entire pool instead of a single computer, change the –Computers parameter to –Pools, remove the computer name, and replace it with the pool or pools in quotation marks separated by commas.</span></span>
    
    <span data-ttu-id="64bea-139">Пример:</span><span class="sxs-lookup"><span data-stu-id="64bea-139">For example:</span></span>
    
        Search-CsClsLogging -Pools "pool01.contoso.net" -OutputFilePath "C:\Logfiles\logfile.txt"

4.  <span data-ttu-id="64bea-140">При использовании команд поиска пулы могут представлять собой любой пул в развертывании, например интерфейсные пулы, пограничные пулы, пулы серверов сохраняемого чата или другие, которые определены как пул в развертывании.</span><span class="sxs-lookup"><span data-stu-id="64bea-140">When using the search commands, pools can be any pool in your deployment, such as Front End pools, Edge pools, Persistent Chat Server pools, or others that are defined as a pool in your deployment.</span></span>
    
    <span data-ttu-id="64bea-141">Пример:</span><span class="sxs-lookup"><span data-stu-id="64bea-141">For example:</span></span>
    
        Search-CsClsLogging -Pools "pool01.contoso.net", "pchatpool01.contoso.net", "intedgepool01.contoso.net" -OutputFilePath "C:\Logfiles\logfile.txt"

</div>

<div>

## <a name="to-run-a-search-by-using-time-parameters"></a><span data-ttu-id="64bea-142">Выполнение поиска с использованием параметров времени</span><span class="sxs-lookup"><span data-stu-id="64bea-142">To run a search by using time parameters</span></span>

1.  <span data-ttu-id="64bea-143">Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="64bea-143">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="64bea-p108">По умолчанию время начала для параметров времени поиска — 30 минут до инициации поиска. Иными словами, если поиск инициируется в 16:00, поиск выполняется по журналам тех компьютеров и пулов, которые определены в интервале от 15:30 до 16:00. Чтобы выполнить поиск в интервале 1-3 часа до текущего времени, необходимо использовать параметр –StartTime и задать строку времени и даты, чтобы определить желаемое время начала поиска.</span><span class="sxs-lookup"><span data-stu-id="64bea-p108">By default, the beginning time for a search's time-specific parameters is 30 minutes prior to the time you initiate the search. In other words, if you initiate your search at 4:00:00 PM, the search will search the logs for the computers and pools that you define from 3:30:00 PM until 4:00:00 PM. If you need to search 60 minutes or 3 hours prior to the current time, use the –StartTime parameter and set the date and time string to indicate the time you want the search to start.</span></span>
    
    <span data-ttu-id="64bea-147">Например, при использовании параметров –StartTime и –EndTime для определения времени и диапазона данных можно задать поиск по своему пулу в интервале 20:00 и 9:00 20.11.12.</span><span class="sxs-lookup"><span data-stu-id="64bea-147">For example, by using –StartTime and –EndTime to define a time and date range, you can define a search between 8 AM and 9 AM on 11/20/2012 on your pool.</span></span> <span data-ttu-id="64bea-148">Можно задать выходной путь для записи результатов в файл с именем c: \\logfile.txt следующим образом:</span><span class="sxs-lookup"><span data-stu-id="64bea-148">You can set the output path to write the results to a file named c:\\logfile.txt as follows:</span></span>
    
        Search-CsClsLogging -Pools "pool01.contoso.net" -StartTime "11/20/2012 08:00:00 AM" -EndTime "11/20/2012 09:00:00 AM" -OutputFilePath "C:\Logfiles\logfile.txt"
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="64bea-149">Указанная строка времени и даты может иметь значение "Дата и время".</span><span class="sxs-lookup"><span data-stu-id="64bea-149">The time and date string that you specify can be "date time" or "time date.</span></span> <span data-ttu-id="64bea-150">"Команда будет анализировать строку и использовать соответствующие значения даты и времени.</span><span class="sxs-lookup"><span data-stu-id="64bea-150">" The command will parse the string and use the appropriate values for date and time.</span></span>

    
    </div>

3.  <span data-ttu-id="64bea-p111">Для получения журналов за период, начиная с 11:00 20.11.12, необходимо задать параметр –StartTime. Для интервала времени по умолчанию установлено значение 30 минут, если не определен параметр –EndTime. В результате поиск возвращает журналы с определенного компьютера или пула за период с 11:00 до 11:30.</span><span class="sxs-lookup"><span data-stu-id="64bea-p111">If you want to retrieve logs beginning at 11:00:00 AM on 11/20/2012, you define the –StartTime. The default time range for the search is 30 minutes unless you define a specific –EndTime. The resulting search will return logs from the defined computer or pools from 11:00:00 AM to 11:30:00 AM.</span></span>
    
    <span data-ttu-id="64bea-154">Пример:</span><span class="sxs-lookup"><span data-stu-id="64bea-154">For example:</span></span>
    
        Search-CsClsLogging -Pools "pool01.contoso.net" -StartTime "11/20/2012 11:00:00 AM" -OutputFilePath "C:\Logfiles\logfile.txt"

4.  <span data-ttu-id="64bea-p112">Чтобы выполнить поиск по журналам в заданный период, необходимо определить параметры –StartTime и –EndTime. Потребуются журналы за период с 13:00 до 14:45 для компьютера edge01.contoso.net.</span><span class="sxs-lookup"><span data-stu-id="64bea-p112">To conduct a search of logs within a specific period of time, define a –StartTime and an –EndTime. You need logs from 1 PM to 2:45 PM on the computer edge01.contoso.net.</span></span>
    
    <span data-ttu-id="64bea-157">Пример:</span><span class="sxs-lookup"><span data-stu-id="64bea-157">For example:</span></span>
    
        Search-CsClsLogging -Computers "edge01.contoso.net" -StartTime "11/20/2012 1:00:00 PM" -EndTime "11/20/2012 2:45:00 PM" -OutputFilePath "C:\Logfiles\logfile.txt"

</div>

<div>

## <a name="to-run-an-advanced-search-by-using-other-criteria-and-matching-options"></a><span data-ttu-id="64bea-158">Выполнение расширенного поиска с использованием других критериев и параметров сопоставления</span><span class="sxs-lookup"><span data-stu-id="64bea-158">To run an advanced search by using other criteria and matching options</span></span>

1.  <span data-ttu-id="64bea-159">Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="64bea-159">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="64bea-160">Чтобы выполнить команду сбора трассировок для заданных компонентов, введите следующий текст:</span><span class="sxs-lookup"><span data-stu-id="64bea-160">To run a command to collect traces for specific components, type the following:</span></span>
    
        Search-CsClsLogging -Components <components to search on> -OutputFilePath <fully qualified path to output logs>
    
    <span data-ttu-id="64bea-161">Пример:</span><span class="sxs-lookup"><span data-stu-id="64bea-161">For example:</span></span>
    
        Search-CsClsLogging -Components "SIPStack","S4","UserServices" -OutputFilePath "C:\Logfiles\logfile.txt"
    
    <span data-ttu-id="64bea-162">В результате поиск возвращает все записи в журнале, которые содержат компоненты трассировки для SIPStack, S4 и UserServices, для всех компьютеров и пулов в среде за последние 30 минут.</span><span class="sxs-lookup"><span data-stu-id="64bea-162">The resulting search returns all log entries that have trace components for SIPStack, S4, and UserServices on all computers and pools in your deployment for the past 30 minutes.</span></span>

3.  <span data-ttu-id="64bea-163">Чтобы ограничить поиск теми же компонентами, что и пул переднего плана с именем pool01.contoso.net, введите:</span><span class="sxs-lookup"><span data-stu-id="64bea-163">To limit the search with the same components to just your Front End pool named pool01.contoso.net, type:</span></span>
    
        Search-CsClsLogging -Components "SIPStack","S4","UserServices" -OutputFilePath "C:\Logfiles\logfile.txt"

4.  <span data-ttu-id="64bea-p113">По умолчанию для команд, содержащих несколько параметров, используется следующая логика поиска: логический оператор OR с каждым из определенных параметров. Можно изменить данное поведение, задав параметр **–MatchAll**. Для этого введите следующий текст:</span><span class="sxs-lookup"><span data-stu-id="64bea-p113">The default search logic for commands with multiple parameters is to use the logical OR with each of the defined parameters. You can change this behavior by specifying the **–MatchAll** parameter. To do this, type the following:</span></span>
    
        Search-CsClsLogging -CallId "d0af828e49fa4dcb99f5f80223a634bc" -Components "SIPStack","S4","UserServices" -MatchAll -OutputFilePath "C:\Logfiles\logfile.txt"

5.  <span data-ttu-id="64bea-p114">Если для сценариев задано постоянное выполнение (например, AlwaysOn), или определены сценарии длительного выполнения, журналы могут быть перемещены с локального компьютера в сетевую общую папку. Общая папка определяется параметром CacheFileNetworkFolder с использованием командлета New-CsClsConfiguration для создания новой или изменения текущей конфигурации с помощью Set-CsClsConfiguration. Если включать общую папку в коллекцию журналов для поиска не требуется, используйте параметр SkipNetworkLogs, как показано далее:</span><span class="sxs-lookup"><span data-stu-id="64bea-p114">If your scenarios are set to run constantly, such as AlwaysOn, or you have defined a long-running scenario logs may roll off of the local machine onto the file share. You define the file share by using the CacheFileNetworkFolder parameter by using New-CsClsConfiguration to create a new configuration or modifying an existing configuration with Set-CsClsConfiguration. If you do not want the search to include the file share in the collection of logs to search, use the SkipNetworkLogs parameter as follows:</span></span>
    
        Search-CsClsLogging -Components "SIPStack","S4","UserServices" -StartTime "11/1/2012 00:00:01 AM" -EndTime "11/20/2012 2:45:00 PM" -SkipNetworkLogs -OutputFilePath "C:\Logfiles\logfile.txt"

</div>

</div>

<span> </span>

</div>

</div>

</div>

