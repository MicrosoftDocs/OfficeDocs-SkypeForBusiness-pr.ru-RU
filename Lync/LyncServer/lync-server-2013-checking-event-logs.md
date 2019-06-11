---
title: 'Lync Server 2013: проверка журналов событий'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Checking event logs
ms:assetid: 5500720d-c628-4dbd-84bc-a5becc39b99c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720914(v=OCS.15)
ms:contentKeyID: 63969602
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1506f94f0a049a6bb4fdd90875dae50548b5f516
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34841574"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="checking-event-logs-in-lync-server-2013"></a><span data-ttu-id="ce55b-102">Проверка журналов событий в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ce55b-102">Checking event logs in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ce55b-103">_**Тема последнего изменения:** 2014-08-06_</span><span class="sxs-lookup"><span data-stu-id="ce55b-103">_**Topic Last Modified:** 2014-08-06_</span></span>

<span data-ttu-id="ce55b-104">Вы можете использовать [средство просмотра событий Windows](http://go.microsoft.com/fwlink/p/?linkid=314067) для просмотра журналов событий и получения сведений о сбоях служб, ошибках репликации в СЛУЖБАХ AD DS и предупреждениях о системных ресурсах, таких как виртуальная память и место на диске.</span><span class="sxs-lookup"><span data-stu-id="ce55b-104">You can use [Windows Event Viewer](http://go.microsoft.com/fwlink/p/?linkid=314067) to view event logs and obtain information about service failures, replication errors in the AD DS, and warnings about system resources such as virtual memory and disk space.</span></span> <span data-ttu-id="ce55b-105">Средство просмотра событий входит в состав Windows Server 2008 и 2012.</span><span class="sxs-lookup"><span data-stu-id="ce55b-105">Event Viewer is included with Windows Server 2008 and 2012.</span></span>

<span data-ttu-id="ce55b-106">В средстве ведения журнала Lync Server 2013 по завершении сеанса отладки выберите пункт **Анализ файлов журнала** для просмотра файлов журнала с помощью средства снупер.</span><span class="sxs-lookup"><span data-stu-id="ce55b-106">In the Lync Server 2013 Logging Tool, when you end the debug session, click **Analyze Log Files** to view the log files by using the Snooper tool.</span></span>

<span data-ttu-id="ce55b-107">В средстве просмотра событий хранятся журналы событий приложений, безопасности и системы.</span><span class="sxs-lookup"><span data-stu-id="ce55b-107">Event Viewer maintains logs about application, security, and system events on the computer.</span></span> <span data-ttu-id="ce55b-108">В журналах событий в приложениях Lync Server 2013 и Windows выводятся предупреждения и условия возникновения ошибок.</span><span class="sxs-lookup"><span data-stu-id="ce55b-108">Both Lync Server 2013 and Windows report warnings and error conditions to the event logs.</span></span> <span data-ttu-id="ce55b-109">Поэтому следует просматривать журналы событий ежедневно.</span><span class="sxs-lookup"><span data-stu-id="ce55b-109">Therefore, review event logs daily.</span></span>

<span data-ttu-id="ce55b-110">С помощью средства просмотра событий можно выполнять следующие действия:</span><span class="sxs-lookup"><span data-stu-id="ce55b-110">Use Event Viewer to:</span></span>

  - <span data-ttu-id="ce55b-111">Просмотр журналов событий и управление ими.</span><span class="sxs-lookup"><span data-stu-id="ce55b-111">View and manage event logs.</span></span>

  - <span data-ttu-id="ce55b-112">Получение сведений о проблемах оборудования, программного обеспечения и системы, которые необходимо устранить.</span><span class="sxs-lookup"><span data-stu-id="ce55b-112">Obtain information about hardware, software, and system issues that must be resolved.</span></span>

  - <span data-ttu-id="ce55b-113">Определение тенденций, требующих дальнейших действий.</span><span class="sxs-lookup"><span data-stu-id="ce55b-113">Identify trends that require future action.</span></span>

<span data-ttu-id="ce55b-114">Сервер, на котором работает Lync Server в операционной системе Windows Server, записывает события из четырех типов журналов.</span><span class="sxs-lookup"><span data-stu-id="ce55b-114">A server that is running Lync Server on a Windows Server operating system records events in four types of logs:</span></span>

  - <span data-ttu-id="ce55b-115">**Журналы**   приложений содержат события, записанные приложениями или программами.</span><span class="sxs-lookup"><span data-stu-id="ce55b-115">**Application logs**   The Application log contains events logged by applications or programs.</span></span> <span data-ttu-id="ce55b-116">Разработчики определяют, какие события нужно заносить в журнал.</span><span class="sxs-lookup"><span data-stu-id="ce55b-116">Developers determine which events to log.</span></span> <span data-ttu-id="ce55b-117">Например, программа для базы данных может записать ошибку файла в журнал приложений.</span><span class="sxs-lookup"><span data-stu-id="ce55b-117">For example, a database program might record a file error in the Application log.</span></span> <span data-ttu-id="ce55b-118">Большинство событий, связанных с Lync Server 2013, отображаются в журнале приложений.</span><span class="sxs-lookup"><span data-stu-id="ce55b-118">Most Lync Server 2013-related events appear in the Application log.</span></span>

  - <span data-ttu-id="ce55b-119">**Журналы безопасности.**   в журнал безопасности регистрируются события, такие как допустимые и недопустимые попытки входа, а также события, связанные с использованием ресурсов, такие как создание, открытие и удаление файлов или других объектов.</span><span class="sxs-lookup"><span data-stu-id="ce55b-119">**Security logs**   The Security log records events such as valid and not valid logon tries in addition to events related to resource use such as creating, opening, or deleting files or other objects.</span></span> <span data-ttu-id="ce55b-120">Например, если включен аудит входа, попытки входа в систему записываются в журнал безопасности.</span><span class="sxs-lookup"><span data-stu-id="ce55b-120">For example, if logon auditing is enabled, attempts to log on to the system are recorded in the Security log.</span></span>

  - <span data-ttu-id="ce55b-121">**Система регистрирует**   журнал системы, в которой содержатся события, зафиксированные системными компонентами Windows.</span><span class="sxs-lookup"><span data-stu-id="ce55b-121">**System logs**   The System log contains events logged by Windows system components.</span></span> <span data-ttu-id="ce55b-122">Например, сбой драйвера или другого системного компонента для загрузки при запуске записывается в системный журнал.</span><span class="sxs-lookup"><span data-stu-id="ce55b-122">For example, the failure of a driver or other system component to load during startup is recorded in the System log.</span></span> <span data-ttu-id="ce55b-123">Типы событий, зафиксированных компонентами системы, предварительно определены сервером.</span><span class="sxs-lookup"><span data-stu-id="ce55b-123">The event types logged by system components are predetermined by the server.</span></span>

  - <span data-ttu-id="ce55b-124">**Lync Server 2013**   средство ведения журнала регистрирует важные события, связанные с проверкой подлинности, соединениями и действиями пользователей.</span><span class="sxs-lookup"><span data-stu-id="ce55b-124">**Lync Server 2013**   The logging tool records significant events related to authentication, connections, and user actions.</span></span> <span data-ttu-id="ce55b-125">После включения диагностического протоколирования вы можете просматривать записи в журнале в средстве просмотра событий.</span><span class="sxs-lookup"><span data-stu-id="ce55b-125">After enabling diagnostic logging, you can view the log entries in Event Viewer.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ce55b-126">Мы не рекомендуем использовать параметры максимального ведения журнала, если только вы не предоставили это в службе поддержки пользователей корпорации Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="ce55b-126">We do not recommend that you use the maximum logging settings unless you are instructed to do this by Microsoft Customer Support Services.</span></span> <span data-ttu-id="ce55b-127">При максимальном ведении журнала загружаются существенные ресурсы, а также все "ложные положительные", то есть ошибки, которые регистрируются только при максимальном ведении журнала, но являются ожидаемыми и не являются причиной проблемы.</span><span class="sxs-lookup"><span data-stu-id="ce55b-127">Maximum logging drains significant resources and can give many “false positives,” that is, errors that get logged only at maximum logging but are really expected and are not a cause of concern.</span></span> <span data-ttu-id="ce55b-128">Кроме того, мы рекомендуем не включать функцию диагностического протоколирования без возможности восстановления.</span><span class="sxs-lookup"><span data-stu-id="ce55b-128">We also recommend that you do not enable diagnostic logging permanently.</span></span> <span data-ttu-id="ce55b-129">Используйте его только при устранении неполадок.</span><span class="sxs-lookup"><span data-stu-id="ce55b-129">Use it only when troubleshooting.</span></span>



</div>

<span data-ttu-id="ce55b-130">В каждом журнале средства просмотра событий в Lync Server 2013 записываются информационные и предупреждающие сообщения и события ошибок.</span><span class="sxs-lookup"><span data-stu-id="ce55b-130">Within each Event Viewer log, Lync Server 2013 records informational, warning, and error events.</span></span> <span data-ttu-id="ce55b-131">Тщательно отслеживайте эти журналы, чтобы отслеживать типы транзакций, выполняемых на серверах Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ce55b-131">Monitor these logs closely to track the types of transactions being conducted on the Lync Server 2013 servers.</span></span> <span data-ttu-id="ce55b-132">Вы должны периодически архивировать журналы или использовать автоматическую смену, чтобы не заполнять место.</span><span class="sxs-lookup"><span data-stu-id="ce55b-132">You should periodically archive the logs or use automatic rollover to avoid running out of space.</span></span> <span data-ttu-id="ce55b-133">Поскольку файлы журнала могут занимать конечное пространство, следует увеличивать размер журнала (например, до 50 МБ) и настроить его на перезапись, чтобы сервер Lync Server 2013 мог продолжать создавать новые события.</span><span class="sxs-lookup"><span data-stu-id="ce55b-133">Because log files can occupy a finite amount of space, increase the log size (for example, to 50 MB) and set it to overwrite so that the Lync Server 2013 Server can continue to write new events.</span></span>

<span data-ttu-id="ce55b-134">Вы также можете автоматизировать администрирование журнала событий с помощью следующих средств и технологий:</span><span class="sxs-lookup"><span data-stu-id="ce55b-134">You can also automate event log administration by using the following tools and technologies:</span></span>

  - <span data-ttu-id="ce55b-135">System Center Operations Manager наблюдает за работоспособностью и использованием серверов Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ce55b-135">System Center Operations Manager monitors the health and use of Lync Server 2013 servers.</span></span> <span data-ttu-id="ce55b-136">Пакет управления Lync Server 2013 для Operations Manager расширяет возможности Operations Manager, предоставляя специализированный мониторинг для серверов, на которых запущен Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ce55b-136">Lync Server 2013 Management Pack for Operations Manager extends Operations Manager by providing specialized monitoring for servers that are running Lync Server 2013.</span></span>

  - <span data-ttu-id="ce55b-137">Пакет управления Lync Server 2013 для Operations Manager наблюдает за стандартом и корпоративным выпуском Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ce55b-137">The Lync Server 2013 Management Pack for Operations Manager monitors Standard and Enterprise Edition of Lync Server 2013.</span></span> <span data-ttu-id="ce55b-138">Кроме того, в этом выпуске установлен пакет управления качеством качества (QoE), который ранее был создан в отдельном пакете управления.</span><span class="sxs-lookup"><span data-stu-id="ce55b-138">This release also incorporates the Quality of Experience (QoE) Management Pack which was previously a separate management pack.</span></span>

<span data-ttu-id="ce55b-139">Отслеживаемые типы — это записи журнала событий, счетчики производительности и мониторинг состояния QoE.</span><span class="sxs-lookup"><span data-stu-id="ce55b-139">Monitored types are event log entries, performance counters and stateful monitoring of QoE.</span></span> <span data-ttu-id="ce55b-140">Эта версия пакета управления наблюдает только для Lync Server 2013 и 2010 и не может использоваться для мониторинга Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="ce55b-140">This version of the management pack only monitors Lync Server 2013 and 2010, and cannot be used to monitor Office Communications Server 2007.</span></span>

<span data-ttu-id="ce55b-141">Пакет управления предоставляет следующие возможности:</span><span class="sxs-lookup"><span data-stu-id="ce55b-141">The management pack provides the following features:</span></span>

  - <span data-ttu-id="ce55b-142">Оповещения о событиях, влияющих на обслуживание</span><span class="sxs-lookup"><span data-stu-id="ce55b-142">Alerts indicating service affecting events</span></span>

  - <span data-ttu-id="ce55b-143">Оповещения, указывающие на конфигурацию и другие проблемы, не связанные с обслуживанием</span><span class="sxs-lookup"><span data-stu-id="ce55b-143">Alerts indicating configuration, and other non-service impacting issues</span></span>

  - <span data-ttu-id="ce55b-144">Наблюдение за состоянием служб Lync Server</span><span class="sxs-lookup"><span data-stu-id="ce55b-144">State monitoring of Lync Server services</span></span>

  - <span data-ttu-id="ce55b-145">Сведения о продукте: причина и решение обнаруженных проблем</span><span class="sxs-lookup"><span data-stu-id="ce55b-145">Product knowledge: Cause and resolution of identified issues</span></span>

<span data-ttu-id="ce55b-146">Дополнительные сведения о пакете управления Lync Server 2013 можно найти в разделе [мониторинг сервера Lync server 2013 с помощью System Center Operations Manager](lync-server-2013-monitoring-lync-server-with-system-center-operations-manager.md).</span><span class="sxs-lookup"><span data-stu-id="ce55b-146">For more information about Lync Server 2013 Management Pack, refer to [Monitoring Lync Server 2013 with System Center Operations Manager](lync-server-2013-monitoring-lync-server-with-system-center-operations-manager.md).</span></span>

<span data-ttu-id="ce55b-147">**Объединение**   событий. инструмент «объединение событий» позволяет собрать определенные события из журналов событий нескольких компьютеров в единое место.</span><span class="sxs-lookup"><span data-stu-id="ce55b-147">**Event Comb**   The Event Comb tool collects specific events from the event logs of several computers to one central location.</span></span> <span data-ttu-id="ce55b-148">Он позволяет сообщать только о кодах событий и их источниках событий.</span><span class="sxs-lookup"><span data-stu-id="ce55b-148">It lets you report on only the event IDs or event sources it specifies.</span></span> <span data-ttu-id="ce55b-149">Дополнительные сведения о событии можно найти на веб-сайте [блокировки учетных записей и средств управления](http://go.microsoft.com/fwlink/?linkid=35607) .</span><span class="sxs-lookup"><span data-stu-id="ce55b-149">For more information about Event Comb, see the [Account Lockout and Management Tools](http://go.microsoft.com/fwlink/?linkid=35607) website.</span></span>

<span data-ttu-id="ce55b-150">**Триггеры событий в**   Windows Server 2012 вы можете "прикрепить задачу к этому событию" в окне просмотра событий Windows, где администратор может либо запустить программу, либо отправить сообщение электронной почты или отобразить сообщение на экране.</span><span class="sxs-lookup"><span data-stu-id="ce55b-150">**Event triggers**   In Windows Server 2012 you can "Attach a Task to This Event" within the Windows Event Viewer—where an administrator can either run a program, send an email message or display an on-screen message.</span></span> <span data-ttu-id="ce55b-151">Дополнительные сведения об этой функции можно найти в разделе Windows Server 2008 R2 [выполнение задачи в ответ на данное событие](http://technet.microsoft.com/en-us/library/cc748900.aspx).</span><span class="sxs-lookup"><span data-stu-id="ce55b-151">For more information about this feature, see the Windows Server 2008 R2 topic [Run a Task in Response to a Given Event](http://technet.microsoft.com/en-us/library/cc748900.aspx).</span></span> <span data-ttu-id="ce55b-152">Кроме того, вы можете использовать средства командной строки, такие как EventTrigger. exe, для создания журналов событий и запросов к ним программ с определенным протоколированием событий.</span><span class="sxs-lookup"><span data-stu-id="ce55b-152">You can also use command-line tools such as ‘Eventtrigger.exe’ to create and query event logs and associate programs with particular logged events.</span></span> <span data-ttu-id="ce55b-153">С помощью Евенттригжерс. exe вы можете создавать триггеры событий, которые запускают программы при возникновении конкретных событий.</span><span class="sxs-lookup"><span data-stu-id="ce55b-153">By using Eventtriggers.exe, you can create event triggers that run programs when specific events occur.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="ce55b-154">См. также</span><span class="sxs-lookup"><span data-stu-id="ce55b-154">See Also</span></span>


[<span data-ttu-id="ce55b-155">Средство просмотра событий Windows</span><span class="sxs-lookup"><span data-stu-id="ce55b-155">Windows Event Viewer</span></span>](http://go.microsoft.com/fwlink/p/?linkid=314067)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

