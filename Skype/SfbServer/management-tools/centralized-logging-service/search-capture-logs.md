---
title: Поиск записей в журналах, созданных службой централизованного ведения журналов в Skype для бизнеса Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 12/20/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 1b75b218-d84f-47a7-8a0a-b7e016b1cc79
description: 'Сводка: Узнайте, как искать и читать централизованные журналы захвата службы ведения журналов в Skype для бизнеса Server 2015.'
ms.openlocfilehash: 563f2c5e08da0830c3bd03e562d0d94052fa359b
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991454"
---
# <a name="search-capture-logs-created-by-the-centralized-logging-service-in-skype-for-business-server-2015"></a><span data-ttu-id="2eeb4-103">Поиск записей в журналах, созданных службой централизованного ведения журналов в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="2eeb4-103">Search capture logs created by the Centralized Logging Service in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="2eeb4-104">**Сводка:** Узнайте, как искать и читать централизованные журналы захвата службы ведения журналов в Skype для бизнеса Server 2015.</span><span class="sxs-lookup"><span data-stu-id="2eeb4-104">**Summary:** Learn how to search and read Centralized Logging Service capture logs in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="2eeb4-105">Функции поиска в централизованной службе ведения журналов полезны и мощно по следующим причинам:</span><span class="sxs-lookup"><span data-stu-id="2eeb4-105">The search features in the Centralized Logging Service are useful and powerful for the following reasons:</span></span> 
  
- <span data-ttu-id="2eeb4-106">Процесс и результаты поиска выполняются на одном компьютере, в пуле, на сайте или в глобальной области в зависимости от заданных критериев.</span><span class="sxs-lookup"><span data-stu-id="2eeb4-106">Your searches and the results are run on a single computer, a pool, a site, or a global scope, based on the criteria you define.</span></span>
    
- <span data-ttu-id="2eeb4-107">Поиск может изначально выполняться в широком диапазоне с последующим уточнением до более узких критериев (время, компонент или компьютер).</span><span class="sxs-lookup"><span data-stu-id="2eeb4-107">Your searches can be initially broad and then narrowed down to more targeted criteria such as time, component, or computer.</span></span> <span data-ttu-id="2eeb4-108">Вы можете выполнить поиск по одному и тому же журналу и больше не нужно запускать сеанс ведения журнала при изменении условий поиска.</span><span class="sxs-lookup"><span data-stu-id="2eeb4-108">You search against the same logs and don't need to run a logging session again when the search criteria changes.</span></span>
    
- <span data-ttu-id="2eeb4-p102">Выполняется сбор результатов поиска со всех компьютеров и из пулов в области, создание коллекции и объединение результатов поисков в единый файл вывода, представляющий результаты использования условий поиска (с ограничением до выполняемых сценариев и данных, получаемых сценариями). При этом для чтения файла вывода и сообщений трассировки во всей среде используется хорошо знакомый инструмент (например, **Snooper** или **Блокнот**).</span><span class="sxs-lookup"><span data-stu-id="2eeb4-p102">The results of your search are gathered from all computers and pools in the scope, collected and aggregated into a single output file that represents all results of the search criteria (limited to the scenarios that have been running and the data captured by the scenarios). You use familiar tools such as **Snooper** or **Notepad** to read the output file and the trace messages from across your deployment.</span></span>
    
<span data-ttu-id="2eeb4-p103">CLSAgent на каждом отдельном компьютере создает журналы в соответствии со сценарием или сценариями (в любое время на компьютере можно выполнять одновременно два сценария). Управление журналами и связанными с ними файлы индекса и кэша осуществляется посредством CLSAgent. При определении критериев и выполнении поиска команда поиска сообщает CLSAgent, какие данные требуется получить. CLSAgent направляет запрос в файлы журнала, кэша и индекса и возвращает результаты поиска в CLSContoller. CLSController получает результаты поиска от всех компьютеров и объединяет их в пул в области поиска. Затем CLSController объединяет журналы и помещает их в порядке изменения времени (первыми идут самые старые записи, последними - самые новые).</span><span class="sxs-lookup"><span data-stu-id="2eeb4-p103">The CLSAgent on each individual computer creates the logs based on the scenario or scenarios (two scenarios per computer can be running at any given time). The logs and their associated index and cache files are managed by the CLSAgent. When you define and execute a search, the search command instructs the CLSAgent on what information should be retrieved. The CLSAgent executes the query against the log files, cache files, and index files and returns the results of the search to the CLSContoller. The CLSController receives the search results from all computers and pools in the scope of the search. The CLSController then aggregates (combines) the logs and puts them into time delta order, oldest entry first, and proceeding in time to the most recent entry last.</span></span>
  
<span data-ttu-id="2eeb4-117">После каждой операции поиска запускается командлет **Sync-CsClsLogging**, который выполняет очистку кэша, используемого операциями поиска (не следует путать с файлами кэша, обслуживаемыми CLSAgent).</span><span class="sxs-lookup"><span data-stu-id="2eeb4-117">After each search, the **Sync-CsClsLogging** cmdlet is run and it flushes the cache used by searches (not to be confused with the cache files maintained by the CLSAgent).</span></span> <span data-ttu-id="2eeb4-118">Очистка кэша позволяет убедиться в том, что журнал и буфер записи файлов трассировки в CLSController свободны для следующей операции поиска.</span><span class="sxs-lookup"><span data-stu-id="2eeb4-118">Flushing the cache helps to ensure that there is a clean log and trace file capture buffer at the CLSController for the next search operation.</span></span>
  
<span data-ttu-id="2eeb4-119">Чтобы получить наибольшую пользу от централизованной службы ведения журналов, вам нужно хорошо понять, как настроить поиск, чтобы возвращать только сообщения трассировки из журналов компьютера и пула, которые связаны с проблемой, которую вы ищете.</span><span class="sxs-lookup"><span data-stu-id="2eeb4-119">To get the most benefit from the Centralized Logging Service, you need a good understanding of how to configure search to return only trace messages from the computer and pool logs that are relevant to the issue that you are researching.</span></span> <span data-ttu-id="2eeb4-120">issues</span><span class="sxs-lookup"><span data-stu-id="2eeb4-120">issues</span></span>
  
<span data-ttu-id="2eeb4-121">Чтобы запустить функцию централизованного поиска службы ведения журналов с помощью командной консоли Skype для бизнеса Server, вы должны быть членом группы безопасности Ксадминистратор или Кссерверадминистратор (или настраиваемой роли RBAC) для управления доступом на основе ролей. содержащая одну из этих двух групп.</span><span class="sxs-lookup"><span data-stu-id="2eeb4-121">To run the Centralized Logging Service search functions by using the Skype for Business Server Management Shell, you must be a member of either the CsAdministrator or the CsServerAdministrator role-based access control (RBAC) security groups, or a custom RBAC role that contains either of these two groups.</span></span> <span data-ttu-id="2eeb4-122">Чтобы возвратить список всех ролей RBAC, которым был назначен этот командлет (включая любые пользовательские роли RBAC, созданные пользователем), выполните следующую команду в командной консоли управления Skype для бизнеса Server или Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2eeb4-122">To return a list of all the RBAC roles that this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Skype for Business Server Management Shell or the Windows PowerShell prompt:</span></span>
  
```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Skype for Business Server 2015 cmdlet"}
```

<span data-ttu-id="2eeb4-123">Например:</span><span class="sxs-lookup"><span data-stu-id="2eeb4-123">For example:</span></span>
  
```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}
```

<span data-ttu-id="2eeb4-124">Остальная часть данного раздела посвящена способам определения критериев поиска в целях оптимизации диагностики.</span><span class="sxs-lookup"><span data-stu-id="2eeb4-124">The remainder of this topic focuses on how to define a search to optimize your troubleshooting.</span></span>
  
### <a name="to-run-a-basic-search-by-using-the-centralized-logging-service"></a><span data-ttu-id="2eeb4-125">Выполнение простого поиска с помощью централизованной службы ведения журналов</span><span class="sxs-lookup"><span data-stu-id="2eeb4-125">To run a basic search by using the Centralized Logging Service</span></span>

1. <span data-ttu-id="2eeb4-126">Запустите командную консоль Skype для бизнеса: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Skype для бизнеса 2015** и щелкните элемент **Командная консоль Skype для бизнеса**.</span><span class="sxs-lookup"><span data-stu-id="2eeb4-126">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="2eeb4-127">Убедитесь в том, что в глобальной области среды выполняется сценарий AlwaysOn, после чего введите в командной строке следующее:</span><span class="sxs-lookup"><span data-stu-id="2eeb4-127">Make sure that you have the AlwaysOn scenario running in your deployment at the global scope and then type the following at a command prompt:</span></span>
    
   ```PowerShell
   Search-CsClsLogging -OutputFilePath <string value of path and file to write the output file>
   ```

> [!NOTE]
> <span data-ttu-id="2eeb4-128">По умолчанию Search-CsClsLogging отправляет результаты поиска на консоль.</span><span class="sxs-lookup"><span data-stu-id="2eeb4-128">By default, Search-CsClsLogging sends the results of the search to the console.</span></span> <span data-ttu-id="2eeb4-129">Если вы хотите сохранить результаты поиска в файле, используйте полный _ \<путь\>к файлу в строке_аутпутфилепас.</span><span class="sxs-lookup"><span data-stu-id="2eeb4-129">If you want to save the search results to a file, use -OutputFilePath  _\<string fully qualified file path\>_.</span></span> <span data-ttu-id="2eeb4-130">Чтобы определить параметр-Аутпутфилепас, укажите путь и имя файла в виде части параметра в строковом формате, заключенном в кавычки (например, К:\логфилес\сеарчаутпут.ткст).</span><span class="sxs-lookup"><span data-stu-id="2eeb4-130">To define the -OutputFilePath parameter, supply a path and a filename as part of the parameter in a string format enclosed in quotation marks (for example; C:\LogFiles\SearchOutput.txt).</span></span> <span data-ttu-id="2eeb4-131">В этом примере необходимо убедиться в том, что каталог C:\LogFiles существует, и у вас есть разрешения для чтения и записи файлов в этот каталог (разрешение NTFS Modify).</span><span class="sxs-lookup"><span data-stu-id="2eeb4-131">In this example, you must ensure that the directory C:\LogFiles exists and that you have permissions to Read and Write (NTFS permission Modify) files in the folder.</span></span> <span data-ttu-id="2eeb4-132">Выполняется добавление выходных данных, но не их перезапись.</span><span class="sxs-lookup"><span data-stu-id="2eeb4-132">The output is appended to and is not overwritten.</span></span> <span data-ttu-id="2eeb4-133">Чтобы создать отдельные файлы, определите уникально идентифицируемое имя файлы для каждой операции поиска.</span><span class="sxs-lookup"><span data-stu-id="2eeb4-133">If you need separate files, define a distinct file name for each search.</span></span> 
  
<span data-ttu-id="2eeb4-134">Например:</span><span class="sxs-lookup"><span data-stu-id="2eeb4-134">For example:</span></span>
    
  ```PowerShell
  Search-CsClsLogging -OutputFilePath "C:\LogFiles\logfile.txt"
  ```

### <a name="to-run-a-basic-search-on-a-pool-or-computer-by-using-the-centralized-logging-service"></a><span data-ttu-id="2eeb4-135">Выполнение простого поиска в пуле или на компьютере с помощью централизованной службы ведения журналов</span><span class="sxs-lookup"><span data-stu-id="2eeb4-135">To run a basic search on a pool or computer by using the Centralized Logging Service</span></span>

1. <span data-ttu-id="2eeb4-136">Чтобы ограничить поиск определенным пулом или компьютером, используйте параметр-Computers на компьютере, определенном полным именем компьютера, заключенным в кавычки и разделив их запятыми, как описано ниже.</span><span class="sxs-lookup"><span data-stu-id="2eeb4-136">To limit the search to a specific pool or computer, use the -Computers parameter with the computer defined by a computer fully qualified name, enclosed in quotation marks and separated by a comma as follows:</span></span>
    
   ```PowerShell
   Search-CsClsLogging -Computers <string value of computer names> -OutputFilePath <string value of path and file to write the output file>
   ```

<span data-ttu-id="2eeb4-137">Например:</span><span class="sxs-lookup"><span data-stu-id="2eeb4-137">For example:</span></span>
    
  ```PowerShell
  Search-CsClsLogging -Computers "fe01.contoso.net" -OutputFilePath "C:\LogFiles\logfile.txt"
  ```

2. <span data-ttu-id="2eeb4-138">Чтобы выполнить поиск по нескольким компьютерам, введите несколько имен компьютеров в кавычках с разделением запятыми. Например:</span><span class="sxs-lookup"><span data-stu-id="2eeb4-138">To search more than one computer, type multiple computer names enclosed in quotation marks and separated by commas, such as the following:</span></span>
    
   ```PowerShell
   Search-CsClsLogging -Computers "fe01.contoso.net", "fe02.contoso.net", "fe03.contoso.net" -OutputFilePath "C:\LogFiles\logfile.txt"
   ```

3. <span data-ttu-id="2eeb4-139">Если вы хотите выполнить поиск всего пула, а не отдельного компьютера, измените параметр-Computers на-Pools, удалите имя компьютера и замените его пулом или пулами в кавычках, разделенных запятыми.</span><span class="sxs-lookup"><span data-stu-id="2eeb4-139">If you need to search an entire pool instead of a single computer, change the -Computers parameter to -Pools, remove the computer name, and replace it with the pool or pools in quotation marks separated by commas.</span></span>
    
    <span data-ttu-id="2eeb4-140">Например:</span><span class="sxs-lookup"><span data-stu-id="2eeb4-140">For example:</span></span>
    
   ```PowerShell
   Search-CsClsLogging -Pools "pool01.contoso.net" -OutputFilePath "C:\Logfiles\logfile.txt"
   ```

4. <span data-ttu-id="2eeb4-141">При использовании команд поиска пулы могут быть любым пулом в развертывании, например в пулах интерфейсов, пулах EDGE, пулах серверов сохраняемого чата или других, которые определяются как пул в развертывании.</span><span class="sxs-lookup"><span data-stu-id="2eeb4-141">When using the search commands, pools can be any pool in your deployment, such as Front End pools, Edge pools, Persistent Chat Server pools, or others that are defined as a pool in your deployment.</span></span>
    
    <span data-ttu-id="2eeb4-142">Например:</span><span class="sxs-lookup"><span data-stu-id="2eeb4-142">For example:</span></span>
    
   ```PowerShell
   Search-CsClsLogging -Pools "pool01.contoso.net", "pchatpool01.contoso.net", "intedgepool01.contoso.net" -OutputFilePath "C:\Logfiles\logfile.txt"
   ```

### <a name="to-run-a-search-by-using-time-parameters"></a><span data-ttu-id="2eeb4-143">Выполнение поиска с использованием параметров времени</span><span class="sxs-lookup"><span data-stu-id="2eeb4-143">To run a search by using time parameters</span></span>

1. <span data-ttu-id="2eeb4-144">Запустите командную консоль Skype для бизнеса: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Skype для бизнеса 2015** и щелкните элемент **Командная консоль Skype для бизнеса**.</span><span class="sxs-lookup"><span data-stu-id="2eeb4-144">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="2eeb4-145">По умолчанию время начала для параметров времени поиска — 25 минут до и пять минут после инициации поиска.</span><span class="sxs-lookup"><span data-stu-id="2eeb4-145">By default, the beginning time for a search's time-specific parameters is 25 minutes prior to five minutes after the time you initiate the search.</span></span> <span data-ttu-id="2eeb4-146">Иными словами, если поиск выполняется в 16:00, время начала поиска отображается с 15:35:00 до 16:05:00.</span><span class="sxs-lookup"><span data-stu-id="2eeb4-146">In other words, if we search at 4:00:00 PM, then the search start time will show as 3:35:00 PM to 4:05:00 PM.</span></span> <span data-ttu-id="2eeb4-147">Если вам нужно найти 60 минут или 3 часа до текущего времени, используйте параметр-StartTime и задайте строку даты и времени, указывающую время начала поиска.</span><span class="sxs-lookup"><span data-stu-id="2eeb4-147">If you need to search 60 minutes or 3 hours prior to the current time, use the -StartTime parameter and set the date and time string to indicate the time you want the search to start.</span></span> 
    
    <span data-ttu-id="2eeb4-148">Например, с помощью функции-StartTime и-EndTime для определения диапазона времени и даты можно задать поиск в диапазоне от 8 до 9 AM 11/20/2012 в пуле.</span><span class="sxs-lookup"><span data-stu-id="2eeb4-148">For example, by using -StartTime and -EndTime to define a time and date range, you can define a search between 8 AM and 9 AM on 11/20/2012 on your pool.</span></span> <span data-ttu-id="2eeb4-149">Также можно задать путь для записи результатов в файл с именем :\logfile.txt:</span><span class="sxs-lookup"><span data-stu-id="2eeb4-149">You can set the output path to write the results to a file named c:\logfile.txt as follows:</span></span>
    
   ```PowerShell
   Search-CsClsLogging -Pools "pool01.contoso.net" -StartTime "11/20/2012 08:00:00 AM" -EndTime "11/20/2012 09:00:00 AM" -OutputFilePath "C:\Logfiles\logfile.txt"
   ```

> [!NOTE]
> <span data-ttu-id="2eeb4-150">Заданная строка времени и даты может быть указана в формате "дата-время" или "время-дата".</span><span class="sxs-lookup"><span data-stu-id="2eeb4-150">The time and date string that you specify can be "date time" or "time date.</span></span> <span data-ttu-id="2eeb4-151">"Команда проанализирует строку и применяет соответствующие значения даты и времени, а также региональных стандартов и региональных параметров на компьютере, с которого вы запускаете командлет.</span><span class="sxs-lookup"><span data-stu-id="2eeb4-151">" The command will parse the string and use the appropriate values for date and time and your locale and culture settings on the machine you are running cmdlet from.</span></span> 
  
3. <span data-ttu-id="2eeb4-152">Если вы хотите получить журналы, начиная с 11:00:00 на 11/20/2012, вы определяете параметр-StartTime.</span><span class="sxs-lookup"><span data-stu-id="2eeb4-152">If you want to retrieve logs beginning at 11:00:00 AM on 11/20/2012, you define the -StartTime.</span></span> <span data-ttu-id="2eeb4-153">Диапазон времени по умолчанию для поиска составляет 30 минут, пока не будет определено конкретное значение.</span><span class="sxs-lookup"><span data-stu-id="2eeb4-153">The default time range for the search is 30 minutes unless you define a specific -EndTime.</span></span> <span data-ttu-id="2eeb4-154">В результате поиск возвращает журналы с определенного компьютера или пула за период с 11:00 до 11:30.</span><span class="sxs-lookup"><span data-stu-id="2eeb4-154">The resulting search will return logs from the defined computer or pools from 11:00:00 AM to 11:30:00 AM.</span></span>
    
<span data-ttu-id="2eeb4-155">Например:</span><span class="sxs-lookup"><span data-stu-id="2eeb4-155">For example:</span></span>
    
  ```PowerShell
  Search-CsClsLogging -Pools "pool01.contoso.net" -StartTime "11/20/2012 11:00:00 AM" -OutputFilePath "C:\Logfiles\logfile.txt"
  ```

4. <span data-ttu-id="2eeb4-156">Чтобы выполнить поиск журналов в течение определенного периода времени, определите a-StartTime и a-EndTime.</span><span class="sxs-lookup"><span data-stu-id="2eeb4-156">To conduct a search of logs within a specific period of time, define a -StartTime and an -EndTime.</span></span> <span data-ttu-id="2eeb4-157">Потребуются журналы за период с 13:00 до 14:45 для компьютера edge01.contoso.net.</span><span class="sxs-lookup"><span data-stu-id="2eeb4-157">You need logs from 1 PM to 2:45 PM on the computer edge01.contoso.net.</span></span> 
    
<span data-ttu-id="2eeb4-158">Например:</span><span class="sxs-lookup"><span data-stu-id="2eeb4-158">For example:</span></span>
    
  ```
  Search-CsClsLogging -Computers "edge01.contoso.net" -StartTime "11/20/2012 1:00:00 PM" -EndTime "11/20/2012 2:45:00 PM" -OutputFilePath "C:\Logfiles\logfile.txt"
  ```

### <a name="to-run-an-advanced-search-by-using-other-criteria-and-matching-options"></a><span data-ttu-id="2eeb4-159">Выполнение расширенного поиска с использованием других критериев и параметров сопоставления</span><span class="sxs-lookup"><span data-stu-id="2eeb4-159">To run an advanced search by using other criteria and matching options</span></span>

1. <span data-ttu-id="2eeb4-160">Запустите командную консоль Skype для бизнеса: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Skype для бизнеса 2015** и щелкните элемент **Командная консоль Skype для бизнеса**.</span><span class="sxs-lookup"><span data-stu-id="2eeb4-160">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="2eeb4-161">Чтобы выполнить команду сбора трассировок для заданных компонентов, введите следующий текст:</span><span class="sxs-lookup"><span data-stu-id="2eeb4-161">To run a command to collect traces for specific components, type the following:</span></span>
    
   ```PowerShell
   Search-CsClsLogging -Components <components to search on> -OutputFilePath <fully qualified path to output logs>
   ```

<span data-ttu-id="2eeb4-162">Например:</span><span class="sxs-lookup"><span data-stu-id="2eeb4-162">For example:</span></span>
    
  ```PowerShell
  Search-CsClsLogging -Components "SIPStack","S4","UserServices" -OutputFilePath "C:\Logfiles\logfile.txt"
  ```

<span data-ttu-id="2eeb4-163">В результате поиск возвращает все записи в журнале, которые содержат компоненты трассировки для SIPStack, S4 и UserServices, для всех компьютеров и пулов в среде за последние 30 минут.</span><span class="sxs-lookup"><span data-stu-id="2eeb4-163">The resulting search returns all log entries that have trace components for SIPStack, S4, and UserServices on all computers and pools in your deployment for the past 30 minutes.</span></span>
    
3. <span data-ttu-id="2eeb4-164">Чтобы ограничить поиск одними и теми же компонентами в пуле переднего плана с именем pool01.contoso.net, введите:</span><span class="sxs-lookup"><span data-stu-id="2eeb4-164">To limit the search with the same components to just your Front End pool named pool01.contoso.net, type:</span></span>
    
   ```PowerShell
   Search-CsClsLogging -Components "SIPStack","S4","UserServices" -OutputFilePath "C:\Logfiles\logfile.txt"
   ```

4. <span data-ttu-id="2eeb4-165">По умолчанию для команд, содержащих несколько параметров, используется следующая логика поиска: логический оператор OR с каждым из определенных параметров.</span><span class="sxs-lookup"><span data-stu-id="2eeb4-165">The default search logic for commands with multiple parameters is to use the logical OR with each of the defined parameters.</span></span> <span data-ttu-id="2eeb4-166">Это поведение можно изменить, указав параметр **-матчалл** .</span><span class="sxs-lookup"><span data-stu-id="2eeb4-166">You can change this behavior by specifying the **-MatchAll** parameter.</span></span> <span data-ttu-id="2eeb4-167">Для этого введите следующий текст:</span><span class="sxs-lookup"><span data-stu-id="2eeb4-167">To do this, type the following:</span></span>
    
   ```PowerShell
   Search-CsClsLogging -CallId "d0af828e49fa4dcb99f5f80223a634bc" -Components "SIPStack","S4","UserServices" -MatchAll -OutputFilePath "C:\Logfiles\logfile.txt"
   ```

5. <span data-ttu-id="2eeb4-p114">Если для сценариев задано постоянное выполнение (например, AlwaysOn), или определены сценарии длительного выполнения, журналы могут быть перемещены с локального компьютера в сетевую общую папку. Общая папка определяется параметром CacheFileNetworkFolder с использованием командлета New-CsClsConfiguration для создания новой или изменения текущей конфигурации с помощью Set-CsClsConfiguration. Если включать общую папку в коллекцию журналов для поиска не требуется, используйте параметр SkipNetworkLogs, как показано далее:</span><span class="sxs-lookup"><span data-stu-id="2eeb4-p114">If your scenarios are set to run constantly, such as AlwaysOn, or you have defined a long-running scenario logs may roll off of the local machine onto the file share. You define the file share by using the CacheFileNetworkFolder parameter by using New-CsClsConfiguration to create a new configuration or modifying an existing configuration with Set-CsClsConfiguration. If you do not want the search to include the file share in the collection of logs to search, use the SkipNetworkLogs parameter as follows:</span></span>
    
   ```PowerShell
   Search-CsClsLogging -Components "SIPStack","S4","UserServices" -StartTime "11/1/2012 00:00:01 AM" -EndTime "11/20/2012 2:45:00 PM" -SkipNetworkLogs -OutputFilePath "C:\Logfiles\logfile.txt"
   ```

## <a name="read-capture-logs-from-the-centralized-logging-service"></a><span data-ttu-id="2eeb4-171">Чтение записей журналов службы централизованного ведения журналов</span><span class="sxs-lookup"><span data-stu-id="2eeb4-171">Read capture logs from the Centralized Logging Service</span></span>

<span data-ttu-id="2eeb4-172">Вы осознаете реальное преимущество централизованной службы ведения журналов после выполнения поиска и наличии файла, который можно использовать для отслеживания обнаруженной проблемы.</span><span class="sxs-lookup"><span data-stu-id="2eeb4-172">You realize the real benefit of the Centralized Logging Service after you run the search and you have a file that you can use to track down a reported problem.</span></span> <span data-ttu-id="2eeb4-173">There are a number of ways that you can read the file.</span><span class="sxs-lookup"><span data-stu-id="2eeb4-173">There are a number of ways that you can read the file.</span></span> <span data-ttu-id="2eeb4-174">The output file is in a standard text format and you can use Notepad.exe or any other programs that will allow you to open and read a text file.</span><span class="sxs-lookup"><span data-stu-id="2eeb4-174">The output file is in a standard text format and you can use Notepad.exe or any other programs that will allow you to open and read a text file.</span></span> <span data-ttu-id="2eeb4-175">Для больших файлов и более сложных проблем можно использовать средство, например Снупер. exe, которое предназначено для чтения и анализа результатов ведения журнала из централизованной службы ведения журнала.</span><span class="sxs-lookup"><span data-stu-id="2eeb4-175">For larger files and more complex issues, you could use a tool like Snooper.exe that is designed to read and parse the logging output from the Centralized Logging Service.</span></span> <span data-ttu-id="2eeb4-176">Snooper is included with the Debug Tools that are available as a separate download.</span><span class="sxs-lookup"><span data-stu-id="2eeb4-176">Snooper is included with the Debug Tools that are available as a separate download.</span></span> <span data-ttu-id="2eeb4-177">Вы можете скачать инструменты отладки здесь: [https://go.microsoft.com/fwlink/?LinkId=285257](https://go.microsoft.com/fwlink/?LinkId=285257).</span><span class="sxs-lookup"><span data-stu-id="2eeb4-177">You can download the Debug Tools here: [https://go.microsoft.com/fwlink/?LinkId=285257](https://go.microsoft.com/fwlink/?LinkId=285257).</span></span> <span data-ttu-id="2eeb4-178">При установке средств отладки не создаются короткие команды и элементы меню.</span><span class="sxs-lookup"><span data-stu-id="2eeb4-178">When you install the Debug Tools, short cuts and menu items are not created.</span></span> <span data-ttu-id="2eeb4-179">После установки средств отладки откройте проводник Windows, окно командной строки или консоль управления в Skype для бизнеса Server и перейдите в каталог (расположение по умолчанию) C:\Program Филес\скипе для Business Server 2015 \ инструменты отладки.</span><span class="sxs-lookup"><span data-stu-id="2eeb4-179">After you install the Debug Tools, open Windows Explorer, a command-line window, or Skype for Business Server Management Shell and go to the directory (default location) C:\Program Files\Skype for Business Server 2015\Debugging Tools.</span></span> <span data-ttu-id="2eeb4-180">Дважды щелкните Снупер. exe или введите Снупер. exe, а затем нажмите клавишу ВВОД, если вы используете командную строку или консоль управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="2eeb4-180">Double-click Snooper.exe or type Snooper.exe, and then press ENTER if you are using the command line or Skype for Business Server Management Shell.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="2eeb4-181">В цели этого раздела не входит подробное обсуждение методов диагностики.</span><span class="sxs-lookup"><span data-stu-id="2eeb4-181">The intent of this topic is not to detail and discuss troubleshooting techniques.</span></span> <span data-ttu-id="2eeb4-182">Диагностика и сопутствующие процессы являются сложной темой.</span><span class="sxs-lookup"><span data-stu-id="2eeb4-182">Troubleshooting and the processes around it is a complex subject.</span></span> <span data-ttu-id="2eeb4-183">Подробные сведения об устранении неполадок и устранении неполадок при определенных нагрузках можно найти в книге набор ресурсов Microsoft [https://go.microsoft.com/fwlink/p/?linkId=211003](https://go.microsoft.com/fwlink/p/?linkId=211003)Lync Server 2010 по адресу.</span><span class="sxs-lookup"><span data-stu-id="2eeb4-183">For details about troubleshooting basics and troubleshooting specific workloads, see the Microsoft Lync Server 2010 Resource Kit book at [https://go.microsoft.com/fwlink/p/?linkId=211003](https://go.microsoft.com/fwlink/p/?linkId=211003).</span></span> <span data-ttu-id="2eeb4-184">Процессы и процедуры по-прежнему применяются к Skype для бизнеса Server 2015.</span><span class="sxs-lookup"><span data-stu-id="2eeb4-184">The processes and procedures still apply to Skype for Business Server 2015.</span></span> 
  
### <a name="to-open-a-log-file-in-snooper"></a><span data-ttu-id="2eeb4-185">Открытие файла журнала в Snooper</span><span class="sxs-lookup"><span data-stu-id="2eeb4-185">To open a log file in Snooper</span></span>

1. <span data-ttu-id="2eeb4-p117">Для использования Snooper и открытия файлов журналов требуется доступ на чтение файлов журналов. Чтобы использовать Snooper и получить доступ к файлам журналов, необходимо быть членом группы безопасности управления доступом на основе ролей (RBAC) CsAdministrator или CsServerAdministrator либо членом настраиваемой роли RBAC, содержащей эти две группы.</span><span class="sxs-lookup"><span data-stu-id="2eeb4-p117">To use Snooper and open log files, you need read access to the log files. To use Snooper and access the log files you must be a member of the CsAdministrator or the CsServerAdministrator role-based access control (RBAC) security groups, or a custom RBAC role that contains either of these two groups.</span></span> 
    
2. <span data-ttu-id="2eeb4-188">После установки средств отладки (LyncDebugTools.msi) перейдите в каталог расположения Snooper.exe с помощью проводника или из командной строки.</span><span class="sxs-lookup"><span data-stu-id="2eeb4-188">After the installation of the Debugging Tools (LyncDebugTools.msi), change directory to the location of Snooper.exe using Windows Explorer or from the command line.</span></span> <span data-ttu-id="2eeb4-189">По умолчанию инструменты отладки находятся в папке C:\Program Филес\скипе для Business Server 2015 \.</span><span class="sxs-lookup"><span data-stu-id="2eeb4-189">By default, the debugging tools are located in C:\Program Files\Skype for Business Server 2015\Debugging Tools.</span></span> <span data-ttu-id="2eeb4-190">Дважды щелкните файл Snooper.exe или запустите его.</span><span class="sxs-lookup"><span data-stu-id="2eeb4-190">Double-click or run Snooper.exe.</span></span>
    
3. <span data-ttu-id="2eeb4-191">После открытия Snooper щелкните правой кнопкой мыши пункт **File** (Файл), выберите пункт **Open File** (Открыть файл), найдите файлы журнала, выберите нужный файл в диалоговом окне **открытия файла** и нажмите кнопку **Open** (Открыть).</span><span class="sxs-lookup"><span data-stu-id="2eeb4-191">After Snooper is open, right-click **File**, click **OpenFile**, find your log files, select a file in the **Open** dialog box, and then click **Open**.</span></span>
    
4. <span data-ttu-id="2eeb4-192">Сообщения **трассировки** файла журнала отображаются на вкладке **Трассировка** . чтобы просмотреть содержимое сообщений собранных трассировок, откройте вкладку **сообщения** .</span><span class="sxs-lookup"><span data-stu-id="2eeb4-192">The log file's **Trace** messages are displayed on the **Trace** tab. Click the **Messages** tab to view the message contents of the collected traces.</span></span>
    
### <a name="to-display-a-call-flow-diagram"></a><span data-ttu-id="2eeb4-193">Отображение схемы потока вызовов</span><span class="sxs-lookup"><span data-stu-id="2eeb4-193">To display a call flow diagram</span></span>

1. <span data-ttu-id="2eeb4-p119">Для использования Snooper и открытия файлов журналов требуется доступ на чтение файлов журналов. Чтобы использовать Snooper и получить доступ к файлам журналов, вы должны быть членом группы безопасности управления доступом на основе ролей (RBAC) CsAdministrator или CsServerAdministrator либо членом настраиваемой роли RBAC, содержащей эти две группы.</span><span class="sxs-lookup"><span data-stu-id="2eeb4-p119">To use Snooper and open log files, you need read access to the log files. To use Snooper and access the log files, you need to be a member of the CsAdministrator or the CsServerAdministrator role-based access control (RBAC) security groups, or a custom RBAC role that contains either of these two groups.</span></span>
    
2. <span data-ttu-id="2eeb4-196">Откройте файл журнала и перейдите на вкладку **Messages** (Сообщения); выберите беседу в представлении сообщений или выберите компонент трассировки на вкладке **Trace** (Трассировка).</span><span class="sxs-lookup"><span data-stu-id="2eeb4-196">Open a log file and click the **Messages** tab, select a conversation in the messages view or select a trace component on the **Trace** tab.</span></span>
    
3. <span data-ttu-id="2eeb4-197">Нажмите **Call Flow** (Поток вызовов).</span><span class="sxs-lookup"><span data-stu-id="2eeb4-197">Click **Call Flow**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="2eeb4-198">Если щелкнуть сообщение или трассировку, которая не является частью потока, схема не появится, и в нижней части Снупер появляется сообщение о состоянии "это сообщение не подходит для каллфов".</span><span class="sxs-lookup"><span data-stu-id="2eeb4-198">If you click on a message or trace that is not part of a call flow, the diagram will not appear and a status message appears at the bottom of Snooper stating "This message is not eligible for callfow".</span></span> <span data-ttu-id="2eeb4-199">Выберите другое сообщение или трассировку, и если это сообщение или трассировка является частью потока вызовов, то появится поток вызовов.</span><span class="sxs-lookup"><span data-stu-id="2eeb4-199">Choose another message or trace and the call flow will appear if the message or trace is part of a call flow.</span></span> 
  
4. <span data-ttu-id="2eeb4-200">Пройдите по строкам сообщений или трассировки и обратите внимание, отображают ли обновления или изменения схемы потока вызовов новую схему.</span><span class="sxs-lookup"><span data-stu-id="2eeb4-200">Move through the Messages or the Trace lines and note whether the call flow diagram updates or changes to display a new diagram.</span></span>
    
5. <span data-ttu-id="2eeb4-201">Помещайте указатель мыши поверх элементов, чтобы получить сведения о сообщениях, конечных точках и других компонентах вызовов.</span><span class="sxs-lookup"><span data-stu-id="2eeb4-201">Hover over elements to get information about call messages, endpoints, and other components.</span></span>
