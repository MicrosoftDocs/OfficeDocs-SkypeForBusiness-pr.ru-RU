---
title: 'Lync Server 2013: проверка журналов событий'
description: 'Lync Server 2013: проверка журналов событий.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Checking event logs
ms:assetid: 5500720d-c628-4dbd-84bc-a5becc39b99c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720914(v=OCS.15)
ms:contentKeyID: 63969602
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6617bde846fd38ab3282fd023b16e0a921f48920
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48570985"
---
# <a name="checking-event-logs-in-lync-server-2013"></a><span data-ttu-id="610d6-103">Проверка журналов событий в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="610d6-103">Checking event logs in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="610d6-104">_**Последнее изменение темы:** 2014-08-06_</span><span class="sxs-lookup"><span data-stu-id="610d6-104">_**Topic Last Modified:** 2014-08-06_</span></span>

<span data-ttu-id="610d6-105">С помощью [средства просмотра событий Windows](https://go.microsoft.com/fwlink/p/?linkid=314067) можно просматривать журналы событий и получать сведения об отказах служб, ошибках репликации в ДОМЕНных СЛУЖБАХ Active Directory и предупреждениях о системных ресурсах, таких как виртуальная память и дисковое пространство.</span><span class="sxs-lookup"><span data-stu-id="610d6-105">You can use [Windows Event Viewer](https://go.microsoft.com/fwlink/p/?linkid=314067) to view event logs and obtain information about service failures, replication errors in the AD DS, and warnings about system resources such as virtual memory and disk space.</span></span> <span data-ttu-id="610d6-106">Средство просмотра событий входит в состав Windows Server 2008 и 2012.</span><span class="sxs-lookup"><span data-stu-id="610d6-106">Event Viewer is included with Windows Server 2008 and 2012.</span></span>

<span data-ttu-id="610d6-107">В средстве ведения журнала Lync Server 2013 при завершении сеанса отладки щелкните **Анализ файлов журнала** для просмотра файлов журнала с помощью средства snooper.</span><span class="sxs-lookup"><span data-stu-id="610d6-107">In the Lync Server 2013 Logging Tool, when you end the debug session, click **Analyze Log Files** to view the log files by using the Snooper tool.</span></span>

<span data-ttu-id="610d6-108">В средстве просмотра событий хранятся журналы событий приложений, безопасности и системных событий компьютера.</span><span class="sxs-lookup"><span data-stu-id="610d6-108">Event Viewer maintains logs about application, security, and system events on the computer.</span></span> <span data-ttu-id="610d6-109">В журналы событий выводятся предупреждения и сообщения об ошибках в Lync Server 2013 и Windows.</span><span class="sxs-lookup"><span data-stu-id="610d6-109">Both Lync Server 2013 and Windows report warnings and error conditions to the event logs.</span></span> <span data-ttu-id="610d6-110">Поэтому просмотрите журналы событий ежедневно.</span><span class="sxs-lookup"><span data-stu-id="610d6-110">Therefore, review event logs daily.</span></span>

<span data-ttu-id="610d6-111">С помощью средства просмотра событий можно выполнять следующие действия:</span><span class="sxs-lookup"><span data-stu-id="610d6-111">Use Event Viewer to:</span></span>

  - <span data-ttu-id="610d6-112">Просмотр журналов событий и управление ими.</span><span class="sxs-lookup"><span data-stu-id="610d6-112">View and manage event logs.</span></span>

  - <span data-ttu-id="610d6-113">Получение сведений о неполадках оборудования, программного обеспечения и системы, которые необходимо устранить.</span><span class="sxs-lookup"><span data-stu-id="610d6-113">Obtain information about hardware, software, and system issues that must be resolved.</span></span>

  - <span data-ttu-id="610d6-114">Определите тенденции, для которых требуется будущее действие.</span><span class="sxs-lookup"><span data-stu-id="610d6-114">Identify trends that require future action.</span></span>

<span data-ttu-id="610d6-115">Сервер, на котором работает Lync Server, в операционной системе Windows Server записывает события в четырех типах журналов:</span><span class="sxs-lookup"><span data-stu-id="610d6-115">A server that is running Lync Server on a Windows Server operating system records events in four types of logs:</span></span>

  - <span data-ttu-id="610d6-116">**Журналы приложений**     Журнал приложений содержит события, регистрируемые приложениями или программами.</span><span class="sxs-lookup"><span data-stu-id="610d6-116">**Application logs**   The Application log contains events logged by applications or programs.</span></span> <span data-ttu-id="610d6-117">События, регистрируемые в журнале, определяют разработчики.</span><span class="sxs-lookup"><span data-stu-id="610d6-117">Developers determine which events to log.</span></span> <span data-ttu-id="610d6-118">Например, СУБД может регистрировать в журнале приложений ошибки, возникшие при работе с файлами.</span><span class="sxs-lookup"><span data-stu-id="610d6-118">For example, a database program might record a file error in the Application log.</span></span> <span data-ttu-id="610d6-119">Большинство событий, связанных с Lync Server 2013, отображаются в журнале приложений.</span><span class="sxs-lookup"><span data-stu-id="610d6-119">Most Lync Server 2013-related events appear in the Application log.</span></span>

  - <span data-ttu-id="610d6-120">**Журналы безопасности**     Журнал безопасности регистрирует события, такие как допустимые и недопустимые попытки входа, в дополнение к событиям, связанным с использованием ресурсов, таких как создание, открытие или удаление файлов или других объектов.</span><span class="sxs-lookup"><span data-stu-id="610d6-120">**Security logs**   The Security log records events such as valid and not valid logon tries in addition to events related to resource use such as creating, opening, or deleting files or other objects.</span></span> <span data-ttu-id="610d6-121">Например, если включен аудит входа в систему, попытки входа в систему будут регистрироваться в журнале безопасности.</span><span class="sxs-lookup"><span data-stu-id="610d6-121">For example, if logon auditing is enabled, attempts to log on to the system are recorded in the Security log.</span></span>

  - <span data-ttu-id="610d6-122">**Системные журналы**     Системный журнал содержит события, регистрируемые системными компонентами Windows.</span><span class="sxs-lookup"><span data-stu-id="610d6-122">**System logs**   The System log contains events logged by Windows system components.</span></span> <span data-ttu-id="610d6-123">Например, в системном журнале регистрируются сбои при загрузке драйвера или другого системного компонента.</span><span class="sxs-lookup"><span data-stu-id="610d6-123">For example, the failure of a driver or other system component to load during startup is recorded in the System log.</span></span> <span data-ttu-id="610d6-124">Типы событий, регистрируемых системными компонентами, предопределены сервером.</span><span class="sxs-lookup"><span data-stu-id="610d6-124">The event types logged by system components are predetermined by the server.</span></span>

  - <span data-ttu-id="610d6-125">**Lync Server 2013**     Средство ведения журнала записывает важные события, связанные с проверкой подлинности, подключениями и действиями пользователя.</span><span class="sxs-lookup"><span data-stu-id="610d6-125">**Lync Server 2013**   The logging tool records significant events related to authentication, connections, and user actions.</span></span> <span data-ttu-id="610d6-126">После включения сбора данных диагностики можно просмотреть записи журнала в средстве просмотра событий.</span><span class="sxs-lookup"><span data-stu-id="610d6-126">After enabling diagnostic logging, you can view the log entries in Event Viewer.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="610d6-127">Не рекомендуется использовать параметры максимального числа журналов, если вы не хотите делать это в службе поддержки пользователей Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="610d6-127">We do not recommend that you use the maximum logging settings unless you are instructed to do this by Microsoft Customer Support Services.</span></span> <span data-ttu-id="610d6-128">Ведение максимального журнала приводит к потере значительных ресурсов и может дать множество ложных срабатываний, то есть ошибки, заносимые в журнал только в течение максимального числа событий, но которые являются ожидаемыми и не являются причиной проблем.</span><span class="sxs-lookup"><span data-stu-id="610d6-128">Maximum logging drains significant resources and can give many “false positives,” that is, errors that get logged only at maximum logging but are really expected and are not a cause of concern.</span></span> <span data-ttu-id="610d6-129">Кроме того, рекомендуется не включать функцию сбора данных диагностики без возможности восстановления.</span><span class="sxs-lookup"><span data-stu-id="610d6-129">We also recommend that you do not enable diagnostic logging permanently.</span></span> <span data-ttu-id="610d6-130">Включайте эту функцию только для устранения неполадок.</span><span class="sxs-lookup"><span data-stu-id="610d6-130">Use it only when troubleshooting.</span></span>



</div>

<span data-ttu-id="610d6-131">В каждом журнале просмотра событий в Lync Server 2013 записывается информация о событиях, предупреждениях и ошибках.</span><span class="sxs-lookup"><span data-stu-id="610d6-131">Within each Event Viewer log, Lync Server 2013 records informational, warning, and error events.</span></span> <span data-ttu-id="610d6-132">Внимательно отслеживайте эти журналы, чтобы отслеживать типы транзакций, выполняемых на серверах Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="610d6-132">Monitor these logs closely to track the types of transactions being conducted on the Lync Server 2013 servers.</span></span> <span data-ttu-id="610d6-133">Во избежание нехватки свободного места на дисках следует периодически архивировать журналы или использовать функцию их автоматической перезаписи.</span><span class="sxs-lookup"><span data-stu-id="610d6-133">You should periodically archive the logs or use automatic rollover to avoid running out of space.</span></span> <span data-ttu-id="610d6-134">Так как файлы журналов могут занимать ограниченный объем пространства, увеличьте размер журнала (например, до 50 МБ) и присвойте ему значение overwrite, чтобы сервер Lync Server 2013 мог продолжать создавать новые события.</span><span class="sxs-lookup"><span data-stu-id="610d6-134">Because log files can occupy a finite amount of space, increase the log size (for example, to 50 MB) and set it to overwrite so that the Lync Server 2013 Server can continue to write new events.</span></span>

<span data-ttu-id="610d6-135">Кроме того, можно автоматизировать администрирование журнала событий с помощью следующих средств и технологий:</span><span class="sxs-lookup"><span data-stu-id="610d6-135">You can also automate event log administration by using the following tools and technologies:</span></span>

  - <span data-ttu-id="610d6-136">System Center Operations Manager отслеживает работоспособность и использование серверов Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="610d6-136">System Center Operations Manager monitors the health and use of Lync Server 2013 servers.</span></span> <span data-ttu-id="610d6-137">Пакет управления Lync Server 2013 для Operations Manager расширяет Operations Manager, предоставляя специализированный мониторинг для серверов, на которых работает Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="610d6-137">Lync Server 2013 Management Pack for Operations Manager extends Operations Manager by providing specialized monitoring for servers that are running Lync Server 2013.</span></span>

  - <span data-ttu-id="610d6-138">Пакет управления Lync Server 2013 для мониторинга Operations Manager выполняет мониторинг стандартного и корпоративного выпуска Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="610d6-138">The Lync Server 2013 Management Pack for Operations Manager monitors Standard and Enterprise Edition of Lync Server 2013.</span></span> <span data-ttu-id="610d6-139">Кроме того, этот выпуск включает пакет управления качества взаимодействия (QoE), который ранее был пакетом управления.</span><span class="sxs-lookup"><span data-stu-id="610d6-139">This release also incorporates the Quality of Experience (QoE) Management Pack which was previously a separate management pack.</span></span>

<span data-ttu-id="610d6-140">Отслеживаемые типы — это записи в журнале событий, счетчики производительности и мониторинг состояния QoE.</span><span class="sxs-lookup"><span data-stu-id="610d6-140">Monitored types are event log entries, performance counters and stateful monitoring of QoE.</span></span> <span data-ttu-id="610d6-141">Эта версия пакета управления только отслеживает Lync Server 2013 и 2010 и не может использоваться для мониторинга Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="610d6-141">This version of the management pack only monitors Lync Server 2013 and 2010, and cannot be used to monitor Office Communications Server 2007.</span></span>

<span data-ttu-id="610d6-142">Пакет управления предоставляет следующие возможности:</span><span class="sxs-lookup"><span data-stu-id="610d6-142">The management pack provides the following features:</span></span>

  - <span data-ttu-id="610d6-143">Оповещения, указывающие на события, затрагивающие службы</span><span class="sxs-lookup"><span data-stu-id="610d6-143">Alerts indicating service affecting events</span></span>

  - <span data-ttu-id="610d6-144">Оповещения, указывающие на конфигурацию и другие проблемы, не связанные с обслуживанием</span><span class="sxs-lookup"><span data-stu-id="610d6-144">Alerts indicating configuration, and other non-service impacting issues</span></span>

  - <span data-ttu-id="610d6-145">Мониторинг состояния служб Lync Server</span><span class="sxs-lookup"><span data-stu-id="610d6-145">State monitoring of Lync Server services</span></span>

  - <span data-ttu-id="610d6-146">Сведения о продукте: причина и решение обнаруженных проблем</span><span class="sxs-lookup"><span data-stu-id="610d6-146">Product knowledge: Cause and resolution of identified issues</span></span>

<span data-ttu-id="610d6-147">Для получения дополнительных сведений о пакете управления Lync Server 2013 обратитесь к разделу [Monitoring Lync server 2013 с System Center Operations Manager](lync-server-2013-monitoring-lync-server-with-system-center-operations-manager.md).</span><span class="sxs-lookup"><span data-stu-id="610d6-147">For more information about Lync Server 2013 Management Pack, refer to [Monitoring Lync Server 2013 with System Center Operations Manager](lync-server-2013-monitoring-lync-server-with-system-center-operations-manager.md).</span></span>

<span data-ttu-id="610d6-148">**Объединение событий**     Инструмент "объединение событий" собирает определенные события из журналов событий нескольких компьютеров в одно центральное расположение.</span><span class="sxs-lookup"><span data-stu-id="610d6-148">**Event Comb**   The Event Comb tool collects specific events from the event logs of several computers to one central location.</span></span> <span data-ttu-id="610d6-149">Он позволяет сообщать только о кодах событий или источниках событий, которые он указывает.</span><span class="sxs-lookup"><span data-stu-id="610d6-149">It lets you report on only the event IDs or event sources it specifies.</span></span> <span data-ttu-id="610d6-150">Дополнительные сведения о событии с объединением событий можно найти на веб-сайте " [Блокировка учетных записей и средства управления](https://go.microsoft.com/fwlink/?linkid=35607) ".</span><span class="sxs-lookup"><span data-stu-id="610d6-150">For more information about Event Comb, see the [Account Lockout and Management Tools](https://go.microsoft.com/fwlink/?linkid=35607) website.</span></span>

<span data-ttu-id="610d6-151">**Триггеры событий**     В Windows Server 2012 вы можете "присоединить задачу к этому событию" в окне просмотра событий Windows, где администратор может запустить программу, отправить сообщение электронной почты или отобразить сообщение на экране.</span><span class="sxs-lookup"><span data-stu-id="610d6-151">**Event triggers**   In Windows Server 2012 you can "Attach a Task to This Event" within the Windows Event Viewer—where an administrator can either run a program, send an email message or display an on-screen message.</span></span> <span data-ttu-id="610d6-152">Дополнительные сведения об этой функции можно найти в разделе Windows Server 2008 R2 [выполнение задачи в ответ на определенное событие](https://technet.microsoft.com/library/cc748900.aspx).</span><span class="sxs-lookup"><span data-stu-id="610d6-152">For more information about this feature, see the Windows Server 2008 R2 topic [Run a Task in Response to a Given Event](https://technet.microsoft.com/library/cc748900.aspx).</span></span> <span data-ttu-id="610d6-153">Кроме того, вы можете использовать средства командной строки, такие как "Eventtrigger.exe", для создания журналов событий и запросов к ним, а также для связывания программ с определенными событиями в журнале.</span><span class="sxs-lookup"><span data-stu-id="610d6-153">You can also use command-line tools such as ‘Eventtrigger.exe’ to create and query event logs and associate programs with particular logged events.</span></span> <span data-ttu-id="610d6-154">С помощью Eventtriggers.exe можно создавать триггеры событий, которые запускают программы при возникновении определенных событий.</span><span class="sxs-lookup"><span data-stu-id="610d6-154">By using Eventtriggers.exe, you can create event triggers that run programs when specific events occur.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="610d6-155">См. также</span><span class="sxs-lookup"><span data-stu-id="610d6-155">See Also</span></span>


[<span data-ttu-id="610d6-156">Средство просмотра событий Windows</span><span class="sxs-lookup"><span data-stu-id="610d6-156">Windows Event Viewer</span></span>](https://go.microsoft.com/fwlink/p/?linkid=314067)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

