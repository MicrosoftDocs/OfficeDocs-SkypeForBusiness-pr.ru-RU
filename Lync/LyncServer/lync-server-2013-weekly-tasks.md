---
title: 'Lync Server 2013: еженедельные задачи'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Weekly tasks
ms:assetid: d564839b-b49d-4c5d-b67e-dc5abb0f6980
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn722432(v=OCS.15)
ms:contentKeyID: 63969650
ms.date: 08/20/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 87d3f87b37b8c0fe29c4dee76467a9e07931551a
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42041218"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="weekly-tasks-in-lync-server-2013"></a><span data-ttu-id="a0c67-102">Еженедельные задачи в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a0c67-102">Weekly tasks in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a0c67-103">_**Последнее изменение темы:** 2015-08-17_</span><span class="sxs-lookup"><span data-stu-id="a0c67-103">_**Topic Last Modified:** 2015-08-17_</span></span>

<span data-ttu-id="a0c67-104">Еженедельные задачи обычно связаны с сбором и анализом журналов и отчетов.</span><span class="sxs-lookup"><span data-stu-id="a0c67-104">Weekly tasks are generally related to collecting and analyzing logs and reports.</span></span>

<div>

## <a name="archive-event-logs"></a><span data-ttu-id="a0c67-105">Архивные журналы событий</span><span class="sxs-lookup"><span data-stu-id="a0c67-105">Archive event logs</span></span>

<span data-ttu-id="a0c67-106">Если журналы событий не настроены на соответствующую перезапись событий, их необходимо регулярно архивировать и удалять.</span><span class="sxs-lookup"><span data-stu-id="a0c67-106">If event logs are not configured to overwrite events as required, they must be regularly archived and deleted.</span></span> <span data-ttu-id="a0c67-107">Выполнение этой задачи является особенно важным для журналов безопасности, которые могут потребоваться при расследовании преднамеренных нарушений безопасности.</span><span class="sxs-lookup"><span data-stu-id="a0c67-107">This action is especially important for security logs, which may be required when investigating attempted security breaches.</span></span>

<span data-ttu-id="a0c67-108">Организация должна определять политики и процедуры для архивации журналов.</span><span class="sxs-lookup"><span data-stu-id="a0c67-108">Your organization will have to define policies and procedures for log archiving.</span></span>

</div>

<div>

## <a name="create-reports"></a><span data-ttu-id="a0c67-109">Создание отчетов</span><span class="sxs-lookup"><span data-stu-id="a0c67-109">Create reports</span></span>

<span data-ttu-id="a0c67-110">Создайте отчеты о состоянии, которые помогут при планировании мощности, анализе соглашений об уровне обслуживания и анализе производительности.</span><span class="sxs-lookup"><span data-stu-id="a0c67-110">Create status reports to help with capacity planning, SLA reviews, and performance analysis.</span></span> <span data-ttu-id="a0c67-111">Используйте ежедневные данные из журнала событий и системного монитора для создания отчетов на диске, памяти и загрузка ЦП.</span><span class="sxs-lookup"><span data-stu-id="a0c67-111">Use daily data from event log and System Monitor to create reports on disk, memory, and CPU usage.</span></span> <span data-ttu-id="a0c67-112">Используйте System Center Operations Manager для создания отчетов о времени работы и доступности.</span><span class="sxs-lookup"><span data-stu-id="a0c67-112">Use System Center Operations Manager to generate uptime and availability reports.</span></span>

<span data-ttu-id="a0c67-113">Организация должна определять политики и процедуры для отчетов о состоянии.</span><span class="sxs-lookup"><span data-stu-id="a0c67-113">Your organization will have to define policies and procedures for status reports.</span></span>

</div>

<div>

## <a name="incident-reports"></a><span data-ttu-id="a0c67-114">Отчеты об инцидентах</span><span class="sxs-lookup"><span data-stu-id="a0c67-114">Incident reports</span></span>

<span data-ttu-id="a0c67-115">Выполнение еженедельного аудита отчетов об инцидентах Организации, относящихся к Lync Server.</span><span class="sxs-lookup"><span data-stu-id="a0c67-115">Perform a weekly audit of your organization’s incident reports that relate to Lync Server.</span></span> <span data-ttu-id="a0c67-116">Этот аудит должен включать следующие компоненты:</span><span class="sxs-lookup"><span data-stu-id="a0c67-116">This audit should include the following:</span></span>

  - <span data-ttu-id="a0c67-117">Топ созданных, разрешенных и ожидающих инцидентов.</span><span class="sxs-lookup"><span data-stu-id="a0c67-117">The top generated, resolved, and pending incidents.</span></span>

  - <span data-ttu-id="a0c67-118">Решения для неразрешенных происшествий.</span><span class="sxs-lookup"><span data-stu-id="a0c67-118">Solutions for unresolved incidents.</span></span>

  - <span data-ttu-id="a0c67-119">Обновление отчетов с добавлением новых билетов на проблемы.</span><span class="sxs-lookup"><span data-stu-id="a0c67-119">Updating reports to include new trouble tickets.</span></span>

  - <span data-ttu-id="a0c67-120">Обновление репозитория документов для руководства по устранению неполадок и устранение неисправностей в отношении простоев.</span><span class="sxs-lookup"><span data-stu-id="a0c67-120">Updating a document repository for troubleshooting guides and post mortems about outages.</span></span>

<span data-ttu-id="a0c67-121">Так как система отслеживания инцидентов вашей организации не зависит от Lync Server, конкретные инструкции или указатели недоступны.</span><span class="sxs-lookup"><span data-stu-id="a0c67-121">Since your organization’s incident tracking system is a choice independent of Lync Server, specific instructions or pointers are not available.</span></span> <span data-ttu-id="a0c67-122">Обратитесь к документации по системе, выбранной вашей организацией.</span><span class="sxs-lookup"><span data-stu-id="a0c67-122">Consult the documentation for the system your organization chose.</span></span>

</div>

<div>

## <a name="check-iis-logs-and-performance"></a><span data-ttu-id="a0c67-123">Проверка журналов и производительности IIS</span><span class="sxs-lookup"><span data-stu-id="a0c67-123">Check IIS logs and performance</span></span>

<span data-ttu-id="a0c67-124">Еженедельный обзор журналов и производительности служб IIS.</span><span class="sxs-lookup"><span data-stu-id="a0c67-124">Perform a weekly review of Internet Information Services (IIS) logs and performance.</span></span> <span data-ttu-id="a0c67-125">Дополнительные сведения о мониторинге журналов и производительности IIS можно найти в статье [описание ведения журнала событий служб IIS для Windows Server 2003](http://go.microsoft.com/fwlink/?linkid=36077).</span><span class="sxs-lookup"><span data-stu-id="a0c67-125">For more information about how to monitor IIS logs and performance, see [Windows Server 2003 Internet Information Services (IIS) Event Logging Overview](http://go.microsoft.com/fwlink/?linkid=36077).</span></span> <span data-ttu-id="a0c67-126">Проверка должна включать следующее:</span><span class="sxs-lookup"><span data-stu-id="a0c67-126">The review should include the following:</span></span>

  - <span data-ttu-id="a0c67-127">Счетчики кэша веб-службы для мониторинга кэша службы WWW.</span><span class="sxs-lookup"><span data-stu-id="a0c67-127">Web Service Cache counters to monitor the WWW service cache.</span></span>

  - <span data-ttu-id="a0c67-128">Счетчики страниц Active Server (АСПС) для мониторинга приложений, запускаемых как АСПС.</span><span class="sxs-lookup"><span data-stu-id="a0c67-128">Active Server Pages (ASPs) counters to monitor applications that run as ASPs.</span></span>

</div>

<div>

## <a name="generate-database-reports"></a><span data-ttu-id="a0c67-129">Создание отчетов базы данных</span><span class="sxs-lookup"><span data-stu-id="a0c67-129">Generate database reports</span></span>

<span data-ttu-id="a0c67-130">**Создание отчетов для базы данных SQL**</span><span class="sxs-lookup"><span data-stu-id="a0c67-130">**To generate reports on the SQL Database**</span></span>

1.  <span data-ttu-id="a0c67-131">Откройте Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a0c67-131">Open Lync Server 2013.</span></span>

2.  <span data-ttu-id="a0c67-132">В дереве консоли разверните узел лес, разверните узел **Пулы предприятий**и выберите пул, для которого необходимо создать отчет базы данных.</span><span class="sxs-lookup"><span data-stu-id="a0c67-132">In the console tree, expand the forest node, expand **Enterprise pools**, and then click the pool for which you want to generate a database report.</span></span>

3.  <span data-ttu-id="a0c67-133">В области сведений перейдите на вкладку **база данных** .</span><span class="sxs-lookup"><span data-stu-id="a0c67-133">In the details pane, click the **Database** tab.</span></span>

4.  <span data-ttu-id="a0c67-134">На вкладке **база данных** выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="a0c67-134">On the **Database** tab, do the following:</span></span>
    
    1.  <span data-ttu-id="a0c67-135">Чтобы просмотреть имя базы данных, разверните раздел **Общие параметры**и просмотрите имя базы данных.</span><span class="sxs-lookup"><span data-stu-id="a0c67-135">To view the name of the database, expand **General Settings**, and view the database name.</span></span>
    
    2.  <span data-ttu-id="a0c67-136">Чтобы получить сводную статистику по текущему пользователю для пула, разверните раздел **Сводные отчеты пользователя**, щелкните **Перейти**и просмотрите результаты.</span><span class="sxs-lookup"><span data-stu-id="a0c67-136">To retrieve current user summary statistics for the pool, expand **User Summary Reports**, click **Go**, and view the results.</span></span>
    
    3.  <span data-ttu-id="a0c67-137">Для получения текущих данных для отдельного пользователя пула разверните узел **отчеты для каждого пользователя**, введите URI SIP, нажмите кнопку **Перейти**и просмотрите результаты.</span><span class="sxs-lookup"><span data-stu-id="a0c67-137">To retrieve current per-user data for a single user of the pool, expand **Per-User Reports**, type the user’s SIP URI, click **Go**, and view the results.</span></span>

<span data-ttu-id="a0c67-138">Чтобы получить текущую сводную статистику для пула, разверните раздел **Сводные отчеты по конференциям**, нажмите кнопку **Перейти**и просмотрите результаты.</span><span class="sxs-lookup"><span data-stu-id="a0c67-138">To retrieve current conference summary statistics for the pool, expand **Conference Summary Reports**, click **Go**, and view the results.</span></span>

</div>

<div>

## <a name="check-for-security-and-lync-server-updates"></a><span data-ttu-id="a0c67-139">Проверка на наличие обновлений для системы безопасности и Lync Server</span><span class="sxs-lookup"><span data-stu-id="a0c67-139">Check for security and Lync Server updates</span></span>

<span data-ttu-id="a0c67-140">Проверьте наличие новых пакетов обновления, исправлений или обновлений.</span><span class="sxs-lookup"><span data-stu-id="a0c67-140">Identify any new service packs, hotfixes, or updates.</span></span> <span data-ttu-id="a0c67-141">При необходимости протестируйте их в тестовой лаборатории и используйте процедуры управления изменениями для упорядочения развертывания на рабочих серверах.</span><span class="sxs-lookup"><span data-stu-id="a0c67-141">If appropriate, test these in a test lab, and use the change control procedures to arrange for deployment to the production servers.</span></span> <span data-ttu-id="a0c67-142">Кроме того, обновления компонентов Lync Server теперь доступны в составе центра обновления Windows.</span><span class="sxs-lookup"><span data-stu-id="a0c67-142">Also, Lync Server component updates are now available as part of Windows update.</span></span> <span data-ttu-id="a0c67-143">Все обновления компонентов Lync Server необходимо одновременно обновить на всех серверах, на которых работает Lync Server, к которым применяются обновления.</span><span class="sxs-lookup"><span data-stu-id="a0c67-143">All Lync Server component updates must be updated at the same time on all of the servers that are running Lync Server for which the updates are applicable.</span></span>

</div>

<div>

## <a name="run-the-lync-server-2013-best-practice-analyzer"></a><span data-ttu-id="a0c67-144">Запуск анализатора соответствия рекомендациям для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a0c67-144">Run the Lync Server 2013 Best Practice Analyzer</span></span>

<span data-ttu-id="a0c67-145">Анализатор соответствия рекомендациям Lync Server 2013 — средство диагностики, которое собирает сведения о конфигурации и определяет, настроена ли конфигурация в соответствии с рекомендациями Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="a0c67-145">The Lync Server 2013 Best Practices Analyzer Tool is a diagnostic tool that collects configuration information and determines whether the configuration is set according to Microsoft best practices.</span></span> <span data-ttu-id="a0c67-146">Документация для этого средства находится в [анализаторе соответствия рекомендациям Lync Server 2013](lync-server-2013-lync-server-best-practices-analyzer.md).</span><span class="sxs-lookup"><span data-stu-id="a0c67-146">Documentation for this tool is at [Lync Server 2013 Best Practices Analyzer](lync-server-2013-lync-server-best-practices-analyzer.md).</span></span>

<span data-ttu-id="a0c67-147">Средство сравнивает данные конфигурации развертывания с набором предопределенных правил для Lync Server и сообщает о возможных проблемах.</span><span class="sxs-lookup"><span data-stu-id="a0c67-147">The tool compares your deployment’s configuration data against a set of pre-defined rules for Lync Server, and reports potential issues.</span></span> <span data-ttu-id="a0c67-148">Для всех обнаруженных ошибок средство предоставляет текущую конфигурацию в среде Lync Server и рекомендуемую конфигурацию.</span><span class="sxs-lookup"><span data-stu-id="a0c67-148">For every issue reported, the tool provides the current configuration in the Lync Server environment, and the recommended configuration.</span></span>

<span data-ttu-id="a0c67-149">При правильном доступе к сети средство может проверить службы AD DS и серверы, на которых работает Lync Server 2013, для выполнения следующих действий:</span><span class="sxs-lookup"><span data-stu-id="a0c67-149">With the correct network access, the tool can examine your AD DS and servers that are running Lync Server 2013 to do the following:</span></span>

  - <span data-ttu-id="a0c67-150">Упреждающее выполнение проверок работоспособности, проверка того, что конфигурация настроена в соответствии с рекомендуемыми рекомендациями</span><span class="sxs-lookup"><span data-stu-id="a0c67-150">Proactively perform health checks, verifying that the configuration is set according to recommended best practices</span></span>

  - <span data-ttu-id="a0c67-151">Создание списка проблем, таких как Неоптимальные параметры конфигурации или неподдерживаемые или не рекомендуемые варианты</span><span class="sxs-lookup"><span data-stu-id="a0c67-151">Generate a list of issues, such as suboptimal configuration settings or unsupported or not recommended options</span></span>

  - <span data-ttu-id="a0c67-152">Оценить общую работоспособность системы</span><span class="sxs-lookup"><span data-stu-id="a0c67-152">Judge the general health of a system</span></span>

  - <span data-ttu-id="a0c67-153">Помощь в устранении определенных проблем</span><span class="sxs-lookup"><span data-stu-id="a0c67-153">Help troubleshoot specific issues</span></span>

  - <span data-ttu-id="a0c67-154">Запрос на скачивание обновлений, если они доступны</span><span class="sxs-lookup"><span data-stu-id="a0c67-154">Prompt you to download updates if they are available</span></span>

  - <span data-ttu-id="a0c67-155">Предоставление интерактивной и локальной документации по отчетным вопросам и включение советов по устранению неполадок</span><span class="sxs-lookup"><span data-stu-id="a0c67-155">Provide online and local documentation about reported issues, and include troubleshooting tips</span></span>

  - <span data-ttu-id="a0c67-156">Создание сведений о конфигурации, которые можно записать для последующего просмотра</span><span class="sxs-lookup"><span data-stu-id="a0c67-156">Generate configuration information that can be captured for later review</span></span>

<span data-ttu-id="a0c67-157">Убедитесь, что РТКБПА. msi установлен на всех серверах Lync Server 2013 и создает отчет о работоспособности еженедельной проверки работоспособности.</span><span class="sxs-lookup"><span data-stu-id="a0c67-157">Ensure that the RTCBPA.msi is installed on all Lync Server 2013 servers, and generate a weekly Health Check Report.</span></span> <span data-ttu-id="a0c67-158">Запишите результаты и при необходимости измените их.</span><span class="sxs-lookup"><span data-stu-id="a0c67-158">Note the results and correct, if necessary.</span></span>

</div>

<div>

## <a name="review-sla-performance-figures"></a><span data-ttu-id="a0c67-159">Обзор показателей производительности SLA</span><span class="sxs-lookup"><span data-stu-id="a0c67-159">Review SLA performance figures</span></span>

<span data-ttu-id="a0c67-160">Проверьте ключевые данные о производительности за предыдущую неделю.</span><span class="sxs-lookup"><span data-stu-id="a0c67-160">Check the key performance data for the previous week.</span></span> <span data-ttu-id="a0c67-161">Проанализируйте производительность в соответствии с требованиями соглашения об уровне обслуживания.</span><span class="sxs-lookup"><span data-stu-id="a0c67-161">Review performance against the requirements of the SLA.</span></span> <span data-ttu-id="a0c67-162">Определите тенденции развития и элементы, не достигшие своих целевых показателей.</span><span class="sxs-lookup"><span data-stu-id="a0c67-162">Identify trends and items that have not met their targets.</span></span>

</div>

<div>

## <a name="review-system-center-operations-manager-management-pack-and-quality-of-experience-reports"></a><span data-ttu-id="a0c67-163">Обзор отчетов по пакету управления System Center Operations Manager и качеству взаимодействия</span><span class="sxs-lookup"><span data-stu-id="a0c67-163">Review System Center Operations Manager Management Pack and quality of experience reports</span></span>

<span data-ttu-id="a0c67-164">Получите и изучите отчеты по пакету управления Lync Server 2013 и качества взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="a0c67-164">Obtain and review Lync Server 2013 Management Pack and Quality of Experience reports.</span></span>

</div>

<div>

## <a name="generating-and-viewing-database-reports-for-enterprise-pools"></a><span data-ttu-id="a0c67-165">Создание и просмотр отчетов базы данных для корпоративных пулов</span><span class="sxs-lookup"><span data-stu-id="a0c67-165">Generating and viewing database reports for enterprise pools</span></span>

<span data-ttu-id="a0c67-166">**Создание отчетов пула**</span><span class="sxs-lookup"><span data-stu-id="a0c67-166">**To generate pool reports**</span></span>

1.  <span data-ttu-id="a0c67-167">Откройте Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a0c67-167">Open Lync Server 2013.</span></span>

2.  <span data-ttu-id="a0c67-168">В дереве консоли разверните узел лес, разверните узел **Пулы предприятий**и выберите пул, для которого необходимо создать отчет базы данных.</span><span class="sxs-lookup"><span data-stu-id="a0c67-168">In the console tree, expand the forest node, expand **Enterprise pools**, and then click the pool for which you want to generate a database report.</span></span>

3.  <span data-ttu-id="a0c67-169">В области сведений перейдите на вкладку **база данных** .</span><span class="sxs-lookup"><span data-stu-id="a0c67-169">In the details pane, click the **Database** tab.</span></span>

4.  <span data-ttu-id="a0c67-170">На вкладке **база данных** выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="a0c67-170">On the **Database** tab, do the following:</span></span>
    
    1.  <span data-ttu-id="a0c67-171">Чтобы просмотреть имя базы данных, разверните раздел **Общие параметры**и просмотрите имя базы данных.</span><span class="sxs-lookup"><span data-stu-id="a0c67-171">To view the name of the database, expand **General Settings**, and view the database name.</span></span>
    
    2.  <span data-ttu-id="a0c67-172">Чтобы получить сводную статистику по текущему пользователю для пула, разверните раздел **Сводные отчеты пользователя**, щелкните **Перейти**и просмотрите результаты.</span><span class="sxs-lookup"><span data-stu-id="a0c67-172">To retrieve current user summary statistics for the pool, expand **User Summary Reports**, click **Go**, and view the results.</span></span>
    
    3.  <span data-ttu-id="a0c67-173">Для получения текущих данных для отдельного пользователя пула разверните узел **отчеты для каждого пользователя**, введите URI SIP, нажмите кнопку **Перейти**и просмотрите результаты.</span><span class="sxs-lookup"><span data-stu-id="a0c67-173">To retrieve current per-user data for a single user of the pool, expand **Per-User Reports**, type the user’s SIP URI, click **Go**, and view the results.</span></span>

<span data-ttu-id="a0c67-174">Чтобы получить текущую сводную статистику для пула, разверните раздел **Сводные отчеты по конференциям**, нажмите кнопку **Перейти**и просмотрите результаты.</span><span class="sxs-lookup"><span data-stu-id="a0c67-174">To retrieve current conference summary statistics for the pool, expand **Conference Summary Reports**, click **Go**, and view the results.</span></span>

<span data-ttu-id="a0c67-175">Для каждого корпоративного пула администраторы могут использовать вкладку " **база данных** " для просмотра имени базы данных и извлечения и просмотра отчетов из базы данных.</span><span class="sxs-lookup"><span data-stu-id="a0c67-175">For each Enterprise Pool, administrators can use the **Database** tab to view the database name and retrieve and view reports from the database.</span></span>

### <a name="database-reports-and-descriptions"></a><span data-ttu-id="a0c67-176">Отчеты и описания баз данных</span><span class="sxs-lookup"><span data-stu-id="a0c67-176">Database Reports and Descriptions</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a0c67-177">Раздел</span><span class="sxs-lookup"><span data-stu-id="a0c67-177">Section</span></span></th>
<th><span data-ttu-id="a0c67-178">Описание</span><span class="sxs-lookup"><span data-stu-id="a0c67-178">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a0c67-179">Сводные отчеты по пользователям</span><span class="sxs-lookup"><span data-stu-id="a0c67-179">User Summary Reports</span></span></p></td>
<td><p><span data-ttu-id="a0c67-180">Dbanalyze/v/Report: DIAG [/склсервер: значение]</span><span class="sxs-lookup"><span data-stu-id="a0c67-180">Dbanalyze /v /report:diag [/sqlserver:value]</span></span></p>
<p><span data-ttu-id="a0c67-181">В этом разделе отображаются статистические сведения о пользователях в пуле, например количество включенных пользователей, среднее количество контактов на пользователя и число пользователей для определенных функций.</span><span class="sxs-lookup"><span data-stu-id="a0c67-181">This section displays aggregate information about users in a pool, such as the number of enabled users, the average number of contacts per user, and the number of users for specific features.</span></span></p>
<p><span data-ttu-id="a0c67-182">При использовании этих отчетов могут быть полезны следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="a0c67-182">When using these reports, the following information may be helpful:</span></span></p>
<ul>
<li><p><span data-ttu-id="a0c67-183">Включенный пользователь — это пользователь, для которого включена поддержка Lync Server 2013, с помощью оснастки "пользователи и компьютеры Active Directory".</span><span class="sxs-lookup"><span data-stu-id="a0c67-183">An enabled user is a user who is enabled for Lync Server 2013 by using the Active Directory Users and Computers Snap-in.</span></span></p></li>
<li><p><span data-ttu-id="a0c67-184">Активный пользователь — это пользователь, который вошел в систему или зарегистрировался.</span><span class="sxs-lookup"><span data-stu-id="a0c67-184">An active user is a user who has logged on or registered.</span></span></p></li>
<li><p><span data-ttu-id="a0c67-185">В сводных отчетах также предлагается набор статистических сведений о контактах.</span><span class="sxs-lookup"><span data-stu-id="a0c67-185">The summary reports also offer a set of statistical information about contacts.</span></span> <span data-ttu-id="a0c67-186">Эти статистические данные действительны только для тех пользователей, которые входили в систему хотя бы один раз и имеют по крайней мере один контакт.</span><span class="sxs-lookup"><span data-stu-id="a0c67-186">These statistics are only valid for the population of users who have logged on at least one time, and who have at least one contact.</span></span> <span data-ttu-id="a0c67-187">Следовательно, обычно не отображается минимальное количество контактов 0.</span><span class="sxs-lookup"><span data-stu-id="a0c67-187">Consequently, you'll typically not see a minimum number of contacts of 0.</span></span> <span data-ttu-id="a0c67-188">В связи с этим поведением, если пользователь не имеет контактов (но активен, если пользователь зарегистрировался), вы можете увидеть: &lt;Empty&gt; для некоторых полей статистики.</span><span class="sxs-lookup"><span data-stu-id="a0c67-188">Because of this behavior, if a user has no contacts (but is active, in that the user has registered), you may see: &lt;empty&gt; for some statistics fields.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a0c67-189">Отчеты для отдельных пользователей</span><span class="sxs-lookup"><span data-stu-id="a0c67-189">Per-User Reports</span></span></p></td>
<td><p><span data-ttu-id="a0c67-190">Dbanalyze/v/Report: диск [/склсервер: значение]</span><span class="sxs-lookup"><span data-stu-id="a0c67-190">Dbanalyze /v /report:disk [/sqlserver:value]</span></span></p>
<p><span data-ttu-id="a0c67-191">В отличие от сводных отчетов, вычисляемых при заполнении пользователей, они представляют собой отчеты об определенном пользователе.</span><span class="sxs-lookup"><span data-stu-id="a0c67-191">Unlike the summary reports, which are calculated over a user population, these are reports about a specific user.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a0c67-192">Сводные отчеты по конференциям</span><span class="sxs-lookup"><span data-stu-id="a0c67-192">Conference Summary Reports</span></span></p></td>
<td><p><span data-ttu-id="a0c67-193">Dbanalyze/v/Report: conf [/склсервер: значение]</span><span class="sxs-lookup"><span data-stu-id="a0c67-193">Dbanalyze /v /report:conf [/sqlserver:value]</span></span></p>
<p><span data-ttu-id="a0c67-194">В этом разделе отображаются сводные сведения о статистике собраний по конференциям для пула, например количество активных конференций и общее количество участников.</span><span class="sxs-lookup"><span data-stu-id="a0c67-194">This section displays aggregate information about conference summary statistics for the pool, such as the number of active conferences and total number of participants.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="running-bandwidth-utilization-analyzer"></a><span data-ttu-id="a0c67-195">Запуск анализатора использования полосы пропускания</span><span class="sxs-lookup"><span data-stu-id="a0c67-195">Running Bandwidth Utilization Analyzer</span></span>

<span data-ttu-id="a0c67-196">Анализатор использования полосы пропускания — это средство, которое создает отчеты о различных режимах использования полосы пропускания в конечных точках UC по каналам глобальной сети в корпоративной сети.</span><span class="sxs-lookup"><span data-stu-id="a0c67-196">Bandwidth Utilization Analyzer is a tool that creates reports about various views of bandwidth consumption by the UC endpoints across WAN links in the enterprise network.</span></span> <span data-ttu-id="a0c67-197">Эти отчеты можно использовать для ознакомления с текущей моделью потребления полосы пропускания и для планирования пропускной способности.</span><span class="sxs-lookup"><span data-stu-id="a0c67-197">These reports can be used to understand the current bandwidth consumption pattern and to help with bandwidth capacity planning.</span></span> <span data-ttu-id="a0c67-198">Кроме того, он выполняет итерацию по пропускной способности, назначенной различным каналам.</span><span class="sxs-lookup"><span data-stu-id="a0c67-198">It also iterates on the bandwidth capacity that is assigned to various links.</span></span>

<span data-ttu-id="a0c67-199">Это средство выполняет следующие действия:</span><span class="sxs-lookup"><span data-stu-id="a0c67-199">This tool does the following:</span></span>

  - <span data-ttu-id="a0c67-200">Создает конкретные отчеты по использованию звука в сети</span><span class="sxs-lookup"><span data-stu-id="a0c67-200">Generates specific reports for audio usage over the network</span></span>

  - <span data-ttu-id="a0c67-201">Способствует более эффективному планированию емкости и итерации по емкости полосы пропускания, назначенной различным связям</span><span class="sxs-lookup"><span data-stu-id="a0c67-201">Helps with more effective capacity planning and iteration on the bandwidth capacity that is assigned to various links</span></span>

<span data-ttu-id="a0c67-202">Анализатор использования полосы пропускания может создавать графические графики для отчетов о емкости и использовании полосы пропускания.</span><span class="sxs-lookup"><span data-stu-id="a0c67-202">Bandwidth Utilization Analyzer can generate graphical plots of bandwidth capacity and usage reports.</span></span> <span data-ttu-id="a0c67-203">��� �������� ��������� �������:</span><span class="sxs-lookup"><span data-stu-id="a0c67-203">They are as follows:</span></span>

  - <span data-ttu-id="a0c67-204">Все связи WAN в корпоративной сети</span><span class="sxs-lookup"><span data-stu-id="a0c67-204">All the WAN links in the enterprise network</span></span>

  - <span data-ttu-id="a0c67-205">Фильтрация по выбранным выбранным каналам глобальной сети</span><span class="sxs-lookup"><span data-stu-id="a0c67-205">Filtered by selected WAN links that were chosen</span></span>

  - <span data-ttu-id="a0c67-206">Фильтрация по каналам WAN с превышением установленной емкости канала</span><span class="sxs-lookup"><span data-stu-id="a0c67-206">Filtered by WAN links that have exceeded link capacity</span></span>

  - <span data-ttu-id="a0c67-207">Фильтрация по каналам WAN с использованием подготовленной полосы пропускания</span><span class="sxs-lookup"><span data-stu-id="a0c67-207">Filtered by WAN links that were under-using the provisioned bandwidth</span></span>

  - <span data-ttu-id="a0c67-208">Фильтрация по каналам глобальной сети, которые достигли критического уровня (использование пропускной способности превышает 90% от пропускной способности канала WAN)</span><span class="sxs-lookup"><span data-stu-id="a0c67-208">Filter by WAN links that were reaching critical levels (a bandwidth usage that is greater than 90 percent of bandwidth capacity of the WAN link)</span></span>

  - <span data-ttu-id="a0c67-209">Фильтрация по типу канала WAN — связи сайтов сети, взаимосвязи между регионами и ссылки на сайте</span><span class="sxs-lookup"><span data-stu-id="a0c67-209">Filtered by WAN link type—network-site links, interregional links, and links inside a site</span></span>

  - <span data-ttu-id="a0c67-210">Фильтрация по области сети</span><span class="sxs-lookup"><span data-stu-id="a0c67-210">Filtered by network region</span></span>

<span data-ttu-id="a0c67-211">Документация для этого средства доступна в [документации по средствам набора ресурсов Lync Server 2013](http://go.microsoft.com/fwlink/?linkid=623245).</span><span class="sxs-lookup"><span data-stu-id="a0c67-211">Documentation for this tool is available at [Lync Server 2013 Resource Kit Tools Documentation](http://go.microsoft.com/fwlink/?linkid=623245).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="a0c67-212">См. также</span><span class="sxs-lookup"><span data-stu-id="a0c67-212">See Also</span></span>


[<span data-ttu-id="a0c67-213">Контрольный список еженедельных задач</span><span class="sxs-lookup"><span data-stu-id="a0c67-213">Weekly task checklist</span></span>](lync-server-2013-operations-checklists.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

