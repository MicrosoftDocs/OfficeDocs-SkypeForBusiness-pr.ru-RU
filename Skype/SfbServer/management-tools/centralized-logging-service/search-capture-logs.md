---
title: Поиск записей в журналах, созданных службой централизованного ведения журналов в Skype для бизнеса Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 12/20/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 1b75b218-d84f-47a7-8a0a-b7e016b1cc79
description: 'Сводка: Узнайте, как поиск и просмотр записей журналов службы централизованного ведения журналов в Скайп для Business Server 2015.'
ms.openlocfilehash: ccf9827848d190179b5f942646a74947047c02c5
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="search-capture-logs-created-by-the-centralized-logging-service-in-skype-for-business-server-2015"></a><span data-ttu-id="951cd-103">Поиск записей в журналах, созданных службой централизованного ведения журналов в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="951cd-103">Search capture logs created by the Centralized Logging Service in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="951cd-104">**Сводка:** Узнайте, как поиск и просмотр записей журналов службы централизованного ведения журналов в Скайп для Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="951cd-104">**Summary:** Learn how to search and read Centralized Logging Service capture logs in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="951cd-105">Функции поиска в службы централизованного ведения журналов являются очень полезных по следующим причинам:</span><span class="sxs-lookup"><span data-stu-id="951cd-105">The search features in the Centralized Logging Service are useful and powerful for the following reasons:</span></span> 
  
- <span data-ttu-id="951cd-106">Процесс и результаты поиска выполняются на одном компьютере, в пуле, на сайте или в глобальной области в зависимости от заданных критериев.</span><span class="sxs-lookup"><span data-stu-id="951cd-106">Your searches and the results are run on a single computer, a pool, a site, or a global scope, based on the criteria you define.</span></span>
    
- <span data-ttu-id="951cd-107">Поиск может изначально выполняться в широком диапазоне с последующим уточнением до более узких критериев (время, компонент или компьютер).</span><span class="sxs-lookup"><span data-stu-id="951cd-107">Your searches can be initially broad and then narrowed down to more targeted criteria such as time, component, or computer.</span></span> <span data-ttu-id="951cd-108">Поиск для одной журналов и не требуется для запуска сеанса ведения журнала еще раз при изменении условий поиска.</span><span class="sxs-lookup"><span data-stu-id="951cd-108">You search against the same logs and don't need to run a logging session again when the search criteria changes.</span></span>
    
- <span data-ttu-id="951cd-p102">Выполняется сбор результатов поиска со всех компьютеров и из пулов в области, создание коллекции и объединение результатов поисков в единый файл вывода, представляющий результаты использования условий поиска (с ограничением до выполняемых сценариев и данных, получаемых сценариями). При этом для чтения файла вывода и сообщений трассировки во всей среде используется хорошо знакомый инструмент (например, **Snooper** или **Блокнот**).</span><span class="sxs-lookup"><span data-stu-id="951cd-p102">The results of your search are gathered from all computers and pools in the scope, collected and aggregated into a single output file that represents all results of the search criteria (limited to the scenarios that have been running and the data captured by the scenarios). You use familiar tools such as **Snooper** or **Notepad** to read the output file and the trace messages from across your deployment.</span></span>
    
<span data-ttu-id="951cd-p103">CLSAgent на каждом отдельном компьютере создает журналы в соответствии со сценарием или сценариями (в любое время на компьютере можно выполнять одновременно два сценария). Управление журналами и связанными с ними файлы индекса и кэша осуществляется посредством CLSAgent. При определении критериев и выполнении поиска команда поиска сообщает CLSAgent, какие данные требуется получить. CLSAgent направляет запрос в файлы журнала, кэша и индекса и возвращает результаты поиска в CLSContoller. CLSController получает результаты поиска от всех компьютеров и объединяет их в пул в области поиска. Затем CLSController объединяет журналы и помещает их в порядке изменения времени (первыми идут самые старые записи, последними - самые новые).</span><span class="sxs-lookup"><span data-stu-id="951cd-p103">The CLSAgent on each individual computer creates the logs based on the scenario or scenarios (two scenarios per computer can be running at any given time). The logs and their associated index and cache files are managed by the CLSAgent. When you define and execute a search, the search command instructs the CLSAgent on what information should be retrieved. The CLSAgent executes the query against the log files, cache files, and index files and returns the results of the search to the CLSContoller. The CLSController receives the search results from all computers and pools in the scope of the search. The CLSController then aggregates (combines) the logs and puts them into time delta order, oldest entry first, and proceeding in time to the most recent entry last.</span></span>
  
<span data-ttu-id="951cd-117">После каждой операции поиска выполните командлет **Sync-CsClsLogging** и очисток кэша, позволяет путем поиска (не следует путать с файлами кэша, задаваемые с помощью CLSAgent).</span><span class="sxs-lookup"><span data-stu-id="951cd-117">After each search, the **Sync-CsClsLogging** cmdlet is run and it flushes the cache used by searches (not to be confused with the cache files maintained by the CLSAgent).</span></span> <span data-ttu-id="951cd-118">Очистка кэша позволяет убедиться в том, что журнал и буфер записи файлов трассировки в CLSController свободны для следующей операции поиска.</span><span class="sxs-lookup"><span data-stu-id="951cd-118">Flushing the cache helps to ensure that there is a clean log and trace file capture buffer at the CLSController for the next search operation.</span></span>
  
<span data-ttu-id="951cd-119">Для извлечения максимальной выгоды из службы централизованного ведения журналов, необходимо понять способы настройки поиска для возвращения только сообщения трассировки из журналов компьютера и пула, относящиеся к проблемы, исследование.</span><span class="sxs-lookup"><span data-stu-id="951cd-119">To get the most benefit from the Centralized Logging Service, you need a good understanding of how to configure search to return only trace messages from the computer and pool logs that are relevant to the issue that you are researching.</span></span> <span data-ttu-id="951cd-120">проблемы</span><span class="sxs-lookup"><span data-stu-id="951cd-120">issues</span></span>
  
<span data-ttu-id="951cd-121">Для запуска функции поиска службы централизованного ведения журналов с помощью Скайп для консоли Business Server, должна быть членом CsAdministrator или групп безопасности CsServerAdministrator доступом на основе ролей (RBAC) элемента управления или настраиваемые роли RBAC который содержит любой из этих двух групп.</span><span class="sxs-lookup"><span data-stu-id="951cd-121">To run the Centralized Logging Service search functions by using the Skype for Business Server Management Shell, you must be a member of either the CsAdministrator or the CsServerAdministrator role-based access control (RBAC) security groups, or a custom RBAC role that contains either of these two groups.</span></span> <span data-ttu-id="951cd-122">Чтобы получить список всех ролей RBAC, этот командлет был назначен (включая любые пользовательские роли RBAC, созданные самостоятельно), выполните следующую команду из Скайп для консоли Business Server или в командной строке Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="951cd-122">To return a list of all the RBAC roles that this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Skype for Business Server Management Shell or the Windows PowerShell prompt:</span></span>
  
```
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Skype for Business Server 2015 cmdlet"}
```

<span data-ttu-id="951cd-123">Например:</span><span class="sxs-lookup"><span data-stu-id="951cd-123">For example:</span></span>
  
```
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}
```

<span data-ttu-id="951cd-124">Остальная часть данного раздела посвящена способам определения критериев поиска в целях оптимизации диагностики.</span><span class="sxs-lookup"><span data-stu-id="951cd-124">The remainder of this topic focuses on how to define a search to optimize your troubleshooting.</span></span>
  
### <a name="to-run-a-basic-search-by-using-the-centralized-logging-service"></a><span data-ttu-id="951cd-125">Выполнение базового поиска с использованием службы централизованного ведения журналов</span><span class="sxs-lookup"><span data-stu-id="951cd-125">To run a basic search by using the Centralized Logging Service</span></span>

1. <span data-ttu-id="951cd-126">Запустите командную консоль Skype для бизнеса: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Skype для бизнеса 2015** и щелкните элемент **Командная консоль Skype для бизнеса**.</span><span class="sxs-lookup"><span data-stu-id="951cd-126">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="951cd-127">Убедитесь в том, что в глобальной области среды выполняется сценарий AlwaysOn, после чего введите в командной строке следующее:</span><span class="sxs-lookup"><span data-stu-id="951cd-127">Make sure that you have the AlwaysOn scenario running in your deployment at the global scope and then type the following at a command prompt:</span></span>
    
  ```
  Search-CsClsLogging -OutputFilePath <string value of path and file to write the output file>
  ```

> [!NOTE]
> <span data-ttu-id="951cd-128">По умолчанию Search-CsClsLogging отправляет результаты поиска на консоль.</span><span class="sxs-lookup"><span data-stu-id="951cd-128">By default, Search-CsClsLogging sends the results of the search to the console.</span></span> <span data-ttu-id="951cd-129">Если вы хотите сохранить результаты поиска в файл, используйте - OutputFilePath _ \<строку полный путь\>_.</span><span class="sxs-lookup"><span data-stu-id="951cd-129">If you want to save the search results to a file, use -OutputFilePath  _\<string fully qualified file path\>_.</span></span> <span data-ttu-id="951cd-130">Чтобы определить параметр - OutputFilePath, укажите путь и имя файла как часть параметра в строковом формате, заключенной в кавычки (например, C:\LogFiles\SearchOutput.txt).</span><span class="sxs-lookup"><span data-stu-id="951cd-130">To define the -OutputFilePath parameter, supply a path and a filename as part of the parameter in a string format enclosed in quotation marks (for example; C:\LogFiles\SearchOutput.txt).</span></span> <span data-ttu-id="951cd-131">В этом примере необходимо убедиться в том, что каталог C:\LogFiles существует, и у вас есть разрешения для чтения и записи файлов в этот каталог (разрешение NTFS Modify).</span><span class="sxs-lookup"><span data-stu-id="951cd-131">In this example, you must ensure that the directory C:\LogFiles exists and that you have permissions to Read and Write (NTFS permission Modify) files in the folder.</span></span> <span data-ttu-id="951cd-132">Выполняется добавление выходных данных, но не их перезапись.</span><span class="sxs-lookup"><span data-stu-id="951cd-132">The output is appended to and is not overwritten.</span></span> <span data-ttu-id="951cd-133">Чтобы создать отдельные файлы, определите уникально идентифицируемое имя файлы для каждой операции поиска.</span><span class="sxs-lookup"><span data-stu-id="951cd-133">If you need separate files, define a distinct file name for each search.</span></span> 
  
<span data-ttu-id="951cd-134">Например:</span><span class="sxs-lookup"><span data-stu-id="951cd-134">For example:</span></span>
    
  ```
  Search-CsClsLogging -OutputFilePath "C:\LogFiles\logfile.txt"
  ```

### <a name="to-run-a-basic-search-on-a-pool-or-computer-by-using-the-centralized-logging-service"></a><span data-ttu-id="951cd-135">Выполнение базового поиска в пуле или компьютер с использованием службы централизованного ведения журналов</span><span class="sxs-lookup"><span data-stu-id="951cd-135">To run a basic search on a pool or computer by using the Centralized Logging Service</span></span>

1. <span data-ttu-id="951cd-136">Чтобы ограничить поиск для конкретного пула или компьютера, используйте параметр - компьютеров с компьютера определяется полное имя компьютера, заключенной в кавычки и разделенных точкой с запятой, как показано ниже:</span><span class="sxs-lookup"><span data-stu-id="951cd-136">To limit the search to a specific pool or computer, use the -Computers parameter with the computer defined by a computer fully qualified name, enclosed in quotation marks and separated by a comma as follows:</span></span>
    
  ```
  Search-CsClsLogging -Computers <string value of computer names> -OutputFilePath <string value of path and file to write the output file>
  ```

<span data-ttu-id="951cd-137">Например:</span><span class="sxs-lookup"><span data-stu-id="951cd-137">For example:</span></span>
    
  ```
  Search-CsClsLogging -Computers "fe01.contoso.net" -OutputFilePath "C:\LogFiles\logfile.txt"
  ```

2. <span data-ttu-id="951cd-138">Чтобы выполнить поиск по нескольким компьютерам, введите несколько имен компьютеров в кавычках с разделением запятыми. Например:</span><span class="sxs-lookup"><span data-stu-id="951cd-138">To search more than one computer, type multiple computer names enclosed in quotation marks and separated by commas, such as the following:</span></span>
    
  ```
  Search-CsClsLogging -Computers "fe01.contoso.net", "fe02.contoso.net", "fe03.contoso.net" -OutputFilePath "C:\LogFiles\logfile.txt"
  ```

3. <span data-ttu-id="951cd-139">Если вам нужно найти весь пул, а не отдельный компьютер, измените параметр - компьютеров для - пулов, remove имя компьютера и заменить ее с помощью пула или пулов в кавычки, разделив их запятыми.</span><span class="sxs-lookup"><span data-stu-id="951cd-139">If you need to search an entire pool instead of a single computer, change the -Computers parameter to -Pools, remove the computer name, and replace it with the pool or pools in quotation marks separated by commas.</span></span>
    
    <span data-ttu-id="951cd-140">Например:</span><span class="sxs-lookup"><span data-stu-id="951cd-140">For example:</span></span>
    
  ```
  Search-CsClsLogging -Pools "pool01.contoso.net" -OutputFilePath "C:\Logfiles\logfile.txt"
  ```

4. <span data-ttu-id="951cd-141">При использовании команд поиска, пулов можно указать любые в среде, например пулов переднего плана, пограничные пулы, пулы серверов сохраняемого чата или любые другие, определенные как пул в вашем развертывании.</span><span class="sxs-lookup"><span data-stu-id="951cd-141">When using the search commands, pools can be any pool in your deployment, such as Front End pools, Edge pools, Persistent Chat Server pools, or others that are defined as a pool in your deployment.</span></span>
    
    <span data-ttu-id="951cd-142">Например:</span><span class="sxs-lookup"><span data-stu-id="951cd-142">For example:</span></span>
    
  ```
  Search-CsClsLogging -Pools "pool01.contoso.net", "pchatpool01.contoso.net", "intedgepool01.contoso.net" -OutputFilePath "C:\Logfiles\logfile.txt"
  ```

### <a name="to-run-a-search-by-using-time-parameters"></a><span data-ttu-id="951cd-143">Выполнение поиска с использованием параметров времени</span><span class="sxs-lookup"><span data-stu-id="951cd-143">To run a search by using time parameters</span></span>

1. <span data-ttu-id="951cd-144">Запустите командную консоль Skype для бизнеса: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Skype для бизнеса 2015** и щелкните элемент **Командная консоль Skype для бизнеса**.</span><span class="sxs-lookup"><span data-stu-id="951cd-144">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="951cd-145">По умолчанию время начала для параметров времени поиска — 25 минут до и пять минут после инициации поиска.</span><span class="sxs-lookup"><span data-stu-id="951cd-145">By default, the beginning time for a search's time-specific parameters is 25 minutes prior to five minutes after the time you initiate the search.</span></span> <span data-ttu-id="951cd-146">Иными словами, если поиск выполняется в 16:00, время начала поиска отображается с 15:35:00 до 16:05:00.</span><span class="sxs-lookup"><span data-stu-id="951cd-146">In other words, if we search at 4:00:00 PM, then the search start time will show as 3:35:00 PM to 4:05:00 PM.</span></span> <span data-ttu-id="951cd-147">Если вам требуется выполнять поиск 60 минут или 3 часа до текущего времени, используйте параметр - StartTime и параметры строки даты и времени для указания времени, поиск, чтобы запустить.</span><span class="sxs-lookup"><span data-stu-id="951cd-147">If you need to search 60 minutes or 3 hours prior to the current time, use the -StartTime parameter and set the date and time string to indicate the time you want the search to start.</span></span> 
    
    <span data-ttu-id="951cd-148">К примеру с помощью - StartTime и - EndTime определение диапазон даты и времени, можно определить поиска между 8 AM и 9: 00 на 11/20/2012 на пул.</span><span class="sxs-lookup"><span data-stu-id="951cd-148">For example, by using -StartTime and -EndTime to define a time and date range, you can define a search between 8 AM and 9 AM on 11/20/2012 on your pool.</span></span> <span data-ttu-id="951cd-149">Также можно задать путь для записи результатов в файл с именем :\logfile.txt:</span><span class="sxs-lookup"><span data-stu-id="951cd-149">You can set the output path to write the results to a file named c:\logfile.txt as follows:</span></span>
    
  ```
  Search-CsClsLogging -Pools "pool01.contoso.net" -StartTime "11/20/2012 08:00:00 AM" -EndTime "11/20/2012 09:00:00 AM" -OutputFilePath "C:\Logfiles\logfile.txt"
  ```

> [!NOTE]
> <span data-ttu-id="951cd-150">Заданная строка времени и даты может быть указана в формате "дата-время" или "время-дата".</span><span class="sxs-lookup"><span data-stu-id="951cd-150">The time and date string that you specify can be "date time" or "time date.</span></span> <span data-ttu-id="951cd-151">«Команда будет анализа строки и используйте соответствующие значения для даты и времени и параметры языка и региональных параметров на компьютере, на котором выполняется командлет.</span><span class="sxs-lookup"><span data-stu-id="951cd-151">" The command will parse the string and use the appropriate values for date and time and your locale and culture settings on the machine you are running cmdlet from.</span></span> 
  
3. <span data-ttu-id="951cd-152">Если вы хотите загрузить журналы, начиная с 11:00:00: 00 на 11/20/2012 г., можно определить время начала.</span><span class="sxs-lookup"><span data-stu-id="951cd-152">If you want to retrieve logs beginning at 11:00:00 AM on 11/20/2012, you define the -StartTime.</span></span> <span data-ttu-id="951cd-153">Диапазон времени по умолчанию для поиска можно 30 минут, если определение конкретного - EndTime.</span><span class="sxs-lookup"><span data-stu-id="951cd-153">The default time range for the search is 30 minutes unless you define a specific -EndTime.</span></span> <span data-ttu-id="951cd-154">В результате поиск возвращает журналы с определенного компьютера или пула за период с 11:00 до 11:30.</span><span class="sxs-lookup"><span data-stu-id="951cd-154">The resulting search will return logs from the defined computer or pools from 11:00:00 AM to 11:30:00 AM.</span></span>
    
<span data-ttu-id="951cd-155">Например:</span><span class="sxs-lookup"><span data-stu-id="951cd-155">For example:</span></span>
    
  ```
  Search-CsClsLogging -Pools "pool01.contoso.net" -StartTime "11/20/2012 11:00:00 AM" -OutputFilePath "C:\Logfiles\logfile.txt"
  ```

4. <span data-ttu-id="951cd-156">Чтобы выполнять поиск журналов в течение определенного периода времени, определите - StartTime и - EndTime.</span><span class="sxs-lookup"><span data-stu-id="951cd-156">To conduct a search of logs within a specific period of time, define a -StartTime and an -EndTime.</span></span> <span data-ttu-id="951cd-157">Потребуются журналы за период с 13:00 до 14:45 для компьютера edge01.contoso.net.</span><span class="sxs-lookup"><span data-stu-id="951cd-157">You need logs from 1 PM to 2:45 PM on the computer edge01.contoso.net.</span></span> 
    
<span data-ttu-id="951cd-158">Например:</span><span class="sxs-lookup"><span data-stu-id="951cd-158">For example:</span></span>
    
  ```
  Search-CsClsLogging -Computers "edge01.contoso.net" -StartTime "11/20/2012 1:00:00 PM" -EndTime "11/20/2012 2:45:00 PM" -OutputFilePath "C:\Logfiles\logfile.txt"
  ```

### <a name="to-run-an-advanced-search-by-using-other-criteria-and-matching-options"></a><span data-ttu-id="951cd-159">Выполнение расширенного поиска с использованием других критериев и параметров сопоставления</span><span class="sxs-lookup"><span data-stu-id="951cd-159">To run an advanced search by using other criteria and matching options</span></span>

1. <span data-ttu-id="951cd-160">Запустите командную консоль Skype для бизнеса: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Skype для бизнеса 2015** и щелкните элемент **Командная консоль Skype для бизнеса**.</span><span class="sxs-lookup"><span data-stu-id="951cd-160">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="951cd-161">Чтобы выполнить команду сбора трассировок для заданных компонентов, введите следующий текст:</span><span class="sxs-lookup"><span data-stu-id="951cd-161">To run a command to collect traces for specific components, type the following:</span></span>
    
  ```
  Search-CsClsLogging -Components <components to search on> -OutputFilePath <fully qualified path to output logs>
  ```

<span data-ttu-id="951cd-162">Например:</span><span class="sxs-lookup"><span data-stu-id="951cd-162">For example:</span></span>
    
  ```
  Search-CsClsLogging -Components "SIPStack","S4","UserServices" -OutputFilePath "C:\Logfiles\logfile.txt"
  ```

<span data-ttu-id="951cd-163">В результате поиск возвращает все записи в журнале, которые содержат компоненты трассировки для SIPStack, S4 и UserServices, для всех компьютеров и пулов в среде за последние 30 минут.</span><span class="sxs-lookup"><span data-stu-id="951cd-163">The resulting search returns all log entries that have trace components for SIPStack, S4, and UserServices on all computers and pools in your deployment for the past 30 minutes.</span></span>
    
3. <span data-ttu-id="951cd-164">Чтобы ограничить поиск теми же компонентами, просто пул переднего плана с именем pool01.contoso.net, введите:</span><span class="sxs-lookup"><span data-stu-id="951cd-164">To limit the search with the same components to just your Front End pool named pool01.contoso.net, type:</span></span>
    
  ```
  Search-CsClsLogging -Components "SIPStack","S4","UserServices" -OutputFilePath "C:\Logfiles\logfile.txt"
  ```

4. <span data-ttu-id="951cd-165">По умолчанию для команд, содержащих несколько параметров, используется следующая логика поиска: логический оператор OR с каждым из определенных параметров.</span><span class="sxs-lookup"><span data-stu-id="951cd-165">The default search logic for commands with multiple parameters is to use the logical OR with each of the defined parameters.</span></span> <span data-ttu-id="951cd-166">Можно изменить это поведение, значение параметра **- MatchAll** .</span><span class="sxs-lookup"><span data-stu-id="951cd-166">You can change this behavior by specifying the **-MatchAll** parameter.</span></span> <span data-ttu-id="951cd-167">Для этого введите следующий текст:</span><span class="sxs-lookup"><span data-stu-id="951cd-167">To do this, type the following:</span></span>
    
  ```
  Search-CsClsLogging -CallId "d0af828e49fa4dcb99f5f80223a634bc" -Components "SIPStack","S4","UserServices" -MatchAll -OutputFilePath "C:\Logfiles\logfile.txt"
  ```

5. <span data-ttu-id="951cd-p114">Если для сценариев задано постоянное выполнение (например, AlwaysOn), или определены сценарии длительного выполнения, журналы могут быть перемещены с локального компьютера в сетевую общую папку. Общая папка определяется параметром CacheFileNetworkFolder с использованием командлета New-CsClsConfiguration для создания новой или изменения текущей конфигурации с помощью Set-CsClsConfiguration. Если включать общую папку в коллекцию журналов для поиска не требуется, используйте параметр SkipNetworkLogs, как показано далее:</span><span class="sxs-lookup"><span data-stu-id="951cd-p114">If your scenarios are set to run constantly, such as AlwaysOn, or you have defined a long-running scenario logs may roll off of the local machine onto the file share. You define the file share by using the CacheFileNetworkFolder parameter by using New-CsClsConfiguration to create a new configuration or modifying an existing configuration with Set-CsClsConfiguration. If you do not want the search to include the file share in the collection of logs to search, use the SkipNetworkLogs parameter as follows:</span></span>
    
  ```
  Search-CsClsLogging -Components "SIPStack","S4","UserServices" -StartTime "11/1/2012 00:00:01 AM" -EndTime "11/20/2012 2:45:00 PM" -SkipNetworkLogs -OutputFilePath "C:\Logfiles\logfile.txt"

  ```

## <a name="read-capture-logs-from-the-centralized-logging-service"></a><span data-ttu-id="951cd-171">Чтение записей журналов службы централизованного ведения журналов</span><span class="sxs-lookup"><span data-stu-id="951cd-171">Read capture logs from the Centralized Logging Service</span></span>

<span data-ttu-id="951cd-172">Реальное преимущество службы централизованного ведения журналов реализовать после запуска поиска и у вас есть файлов, которые можно использовать для отслеживания обнаруженной проблемы.</span><span class="sxs-lookup"><span data-stu-id="951cd-172">You realize the real benefit of the Centralized Logging Service after you run the search and you have a file that you can use to track down a reported problem.</span></span> <span data-ttu-id="951cd-173">Существует несколько способов чтения файла.</span><span class="sxs-lookup"><span data-stu-id="951cd-173">There are a number of ways that you can read the file.</span></span> <span data-ttu-id="951cd-174">— Это файл выходных данных в виде обычного текста и могут использоваться Notepad.exe или других программ, которые можно открыть и чтение в текстовый файл.</span><span class="sxs-lookup"><span data-stu-id="951cd-174">The output file is in a standard text format and you can use Notepad.exe or any other programs that will allow you to open and read a text file.</span></span> <span data-ttu-id="951cd-175">Файлы большего размера и более сложные проблемы можно использовать средство вроде Snooper.exe, предназначенный для чтения и синтаксического анализа журналов выходные данные службы централизованного ведения журналов.</span><span class="sxs-lookup"><span data-stu-id="951cd-175">For larger files and more complex issues, you could use a tool like Snooper.exe that is designed to read and parse the logging output from the Centralized Logging Service.</span></span> <span data-ttu-id="951cd-176">Snooper входит в состав средства отладки, доступны в виде отдельной загрузки.</span><span class="sxs-lookup"><span data-stu-id="951cd-176">Snooper is included with the Debug Tools that are available as a separate download.</span></span> <span data-ttu-id="951cd-177">Вы можете скачать здесь средств отладки: [https://go.microsoft.com/fwlink/?LinkId=285257](https://go.microsoft.com/fwlink/?LinkId=285257).</span><span class="sxs-lookup"><span data-stu-id="951cd-177">You can download the Debug Tools here: [https://go.microsoft.com/fwlink/?LinkId=285257](https://go.microsoft.com/fwlink/?LinkId=285257).</span></span> <span data-ttu-id="951cd-178">При установке средства отладки, ярлыки и пункты меню не создаются.</span><span class="sxs-lookup"><span data-stu-id="951cd-178">When you install the Debug Tools, short cuts and menu items are not created.</span></span> <span data-ttu-id="951cd-179">После установки средства отладки, откройте проводник Windows, окно командной строки или Скайп для консоли Business Server и перейдите к каталог (расположение по умолчанию) Files\Skype C:\Program 2015\Debugging средства Business Server.</span><span class="sxs-lookup"><span data-stu-id="951cd-179">After you install the Debug Tools, open Windows Explorer, a command-line window, or Skype for Business Server Management Shell and go to the directory (default location) C:\Program Files\Skype for Business Server 2015\Debugging Tools.</span></span> <span data-ttu-id="951cd-180">Дважды щелкните Snooper.exe или введите Snooper.exe и нажмите клавишу ВВОД, если вы используете командной строки или Скайп для консоли Business Server.</span><span class="sxs-lookup"><span data-stu-id="951cd-180">Double-click Snooper.exe or type Snooper.exe, and then press ENTER if you are using the command line or Skype for Business Server Management Shell.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="951cd-181">В цели этого раздела не входит подробное обсуждение методов диагностики.</span><span class="sxs-lookup"><span data-stu-id="951cd-181">The intent of this topic is not to detail and discuss troubleshooting techniques.</span></span> <span data-ttu-id="951cd-182">Диагностика и сопутствующие процессы являются сложной темой.</span><span class="sxs-lookup"><span data-stu-id="951cd-182">Troubleshooting and the processes around it is a complex subject.</span></span> <span data-ttu-id="951cd-183">Подробные сведения о основы Устранение неполадок и устранение неполадок конкретных нагрузок книги пакет ресурсов Microsoft Lync Server 2010 в [https://go.microsoft.com/fwlink/p/?linkId=211003](https://go.microsoft.com/fwlink/p/?linkId=211003).</span><span class="sxs-lookup"><span data-stu-id="951cd-183">For details about troubleshooting basics and troubleshooting specific workloads, see the Microsoft Lync Server 2010 Resource Kit book at [https://go.microsoft.com/fwlink/p/?linkId=211003](https://go.microsoft.com/fwlink/p/?linkId=211003).</span></span> <span data-ttu-id="951cd-184">Процессы и процедуры по-прежнему применяется к Скайп для Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="951cd-184">The processes and procedures still apply to Skype for Business Server 2015.</span></span> 
  
### <a name="to-open-a-log-file-in-snooper"></a><span data-ttu-id="951cd-185">Открытие файла журнала в Snooper</span><span class="sxs-lookup"><span data-stu-id="951cd-185">To open a log file in Snooper</span></span>

1. <span data-ttu-id="951cd-p117">Для использования Snooper и открытия файлов журналов требуется доступ на чтение файлов журналов. Чтобы использовать Snooper и получить доступ к файлам журналов, необходимо быть членом группы безопасности управления доступом на основе ролей (RBAC) CsAdministrator или CsServerAdministrator либо членом настраиваемой роли RBAC, содержащей эти две группы.</span><span class="sxs-lookup"><span data-stu-id="951cd-p117">To use Snooper and open log files, you need read access to the log files. To use Snooper and access the log files you must be a member of the CsAdministrator or the CsServerAdministrator role-based access control (RBAC) security groups, or a custom RBAC role that contains either of these two groups.</span></span> 
    
2. <span data-ttu-id="951cd-188">После установки средств отладки (LyncDebugTools.msi) перейдите в каталог расположения Snooper.exe с помощью проводника или из командной строки.</span><span class="sxs-lookup"><span data-stu-id="951cd-188">After the installation of the Debugging Tools (LyncDebugTools.msi), change directory to the location of Snooper.exe using Windows Explorer or from the command line.</span></span> <span data-ttu-id="951cd-189">По умолчанию средства отладки, находятся в C:\Program Files\Skype средства 2015\Debugging Business Server.</span><span class="sxs-lookup"><span data-stu-id="951cd-189">By default, the debugging tools are located in C:\Program Files\Skype for Business Server 2015\Debugging Tools.</span></span> <span data-ttu-id="951cd-190">Дважды щелкните файл Snooper.exe или запустите его.</span><span class="sxs-lookup"><span data-stu-id="951cd-190">Double-click or run Snooper.exe.</span></span>
    
3. <span data-ttu-id="951cd-191">После открытия Snooper щелкните правой кнопкой мыши пункт **File** (Файл), выберите пункт **Open File** (Открыть файл), найдите файлы журнала, выберите нужный файл в диалоговом окне **открытия файла** и нажмите кнопку **Open** (Открыть).</span><span class="sxs-lookup"><span data-stu-id="951cd-191">After Snooper is open, right-click **File**, click **OpenFile**, find your log files, select a file in the **Open** dialog box, and then click **Open**.</span></span>
    
4. <span data-ttu-id="951cd-192">Файл журнала **трассировки** сообщения на **трассировки** вкладку перейдите на вкладку **сообщений** , чтобы просмотреть содержимое сообщения трассировки, собранные.</span><span class="sxs-lookup"><span data-stu-id="951cd-192">The log file's **Trace** messages are displayed on the **Trace** tab. Click the **Messages** tab to view the message contents of the collected traces.</span></span>
    
### <a name="to-display-a-call-flow-diagram"></a><span data-ttu-id="951cd-193">Отображение схемы потока вызовов</span><span class="sxs-lookup"><span data-stu-id="951cd-193">To display a call flow diagram</span></span>

1. <span data-ttu-id="951cd-p119">Для использования Snooper и открытия файлов журналов требуется доступ на чтение файлов журналов. Чтобы использовать Snooper и получить доступ к файлам журналов, вы должны быть членом группы безопасности управления доступом на основе ролей (RBAC) CsAdministrator или CsServerAdministrator либо членом настраиваемой роли RBAC, содержащей эти две группы.</span><span class="sxs-lookup"><span data-stu-id="951cd-p119">To use Snooper and open log files, you need read access to the log files. To use Snooper and access the log files, you need to be a member of the CsAdministrator or the CsServerAdministrator role-based access control (RBAC) security groups, or a custom RBAC role that contains either of these two groups.</span></span>
    
2. <span data-ttu-id="951cd-196">Откройте файл журнала и перейдите на вкладку **Messages** (Сообщения); выберите беседу в представлении сообщений или выберите компонент трассировки на вкладке **Trace** (Трассировка).</span><span class="sxs-lookup"><span data-stu-id="951cd-196">Open a log file and click the **Messages** tab, select a conversation in the messages view or select a trace component on the **Trace** tab.</span></span>
    
3. <span data-ttu-id="951cd-197">Нажмите **Call Flow** (Поток вызовов).</span><span class="sxs-lookup"><span data-stu-id="951cd-197">Click **Call Flow**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="951cd-198">Если щелкнуть сообщение или трассировки, который не является частью поток вызовов, диаграмма не будет выглядеть и появится сообщение о состоянии в нижней части Snooper о том, «это сообщение не подходит для callfow».</span><span class="sxs-lookup"><span data-stu-id="951cd-198">If you click on a message or trace that is not part of a call flow, the diagram will not appear and a status message appears at the bottom of Snooper stating "This message is not eligible for callfow".</span></span> <span data-ttu-id="951cd-199">Выберите другое сообщение или трассировку, и если это сообщение или трассировка является частью потока вызовов, то появится поток вызовов.</span><span class="sxs-lookup"><span data-stu-id="951cd-199">Choose another message or trace and the call flow will appear if the message or trace is part of a call flow.</span></span> 
  
4. <span data-ttu-id="951cd-200">Пройдите по строкам сообщений или трассировки и обратите внимание, отображают ли обновления или изменения схемы потока вызовов новую схему.</span><span class="sxs-lookup"><span data-stu-id="951cd-200">Move through the Messages or the Trace lines and note whether the call flow diagram updates or changes to display a new diagram.</span></span>
    
5. <span data-ttu-id="951cd-201">Помещайте указатель мыши поверх элементов, чтобы получить сведения о сообщениях, конечных точках и других компонентах вызовов.</span><span class="sxs-lookup"><span data-stu-id="951cd-201">Hover over elements to get information about call messages, endpoints, and other components.</span></span>